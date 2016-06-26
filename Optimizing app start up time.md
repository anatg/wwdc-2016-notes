Mach-o terminology

File Types:
  Executable- main binary for application
  Dylib: dynamic library aka DSO or DLL
  Bundle- BYLib that cannot be linked only dlopen
Image- an executable
File



File divided into segments
  Uppercase names
ALl segments are multiples of 16

Sections are things a compiler omits
  subrange of a segment, lowercase names
Common segments; Text, Data, Linkedit
  Text: has header, code, and read-only constants
  Data has al read-write
  Linkedit has meta data about how to load the program (name and address)

Mach o Universal Files
  for both architectures:
    fat header
      One page in size
      Lists architectures

  Virtual Memory:
    Virtual memory is a level of indirection
    maps per process addresses to physical RAM
      page fault
      same ram fpage appears in multiple processes
      file backed pages
        mmap()
        lazy reading
      Copy-on-write (COW)
        Cloning
        shares
      text segment can be shared between processes
      Dirty vs. clean page:
        dirty are more expensive than clean, (like a copy)
      permissions: rwx (read, write, executable)
  Mach-o image loading
    Linkedit is only needed once the DYLib finishes

  Security
    ASLR: Address Space Layout Randomization
      Images load at random address
    Code Signing
      Content of each page is hashed
      Hash is verified on page-in
      (every page gets its own cryptographic hash.)

Exec()
  System call: kernel maps your application into new address space
  start of your app is random
  Low memory is marked inaccessible
  (4KB for 32-bit processes)
What about dylibs
  kernel loads helper program
    DYLD (dynamic loader) (ld.so)
    executions starts in dyld
  dyld runs in process

DYLD steps:
  Map all dependent dylibs
    parse list of depended dylibs in the header.
    find requested mach-o file
    open and read start of file
    validate macho
    register code signature
    call mmap
  Fix-ups
    Code signing means instructions cannot be altered
    modern code-gen is dynamic Position

  Rebasing and Binding
    Rebase: you have a pointer pointing within your image
      rebasing is adding a slide value to each internal pointer
      ASLR: dylib is in a random address.
      slide- actual_address = preferred_address
      Location of rebase location is encoded in LinkedIT
      pages-in

    Binding
      All references to something in another dylib are symbolic
        DYLD needs t find symbol name
  Notify ObjC Runtime
    Most objC set up done via rebasing and binding
    All objC class definitions are registered
    Non-fragile ivars offsets updated
    Categories are inserted into method lists
    Selectors are unique
Initializers
  C++ generates initializer for statically allocated objects
  ObjC +load methods
    (recommend +initialize)
  Run "bottom up" so each initializer can call dylibs below it.

Pre-main()summary
  Dyld is a helper program
    Loads all dependent dylibs
    fixes up all pointers in DATA pages
    Runs all initializers

Improving Launch times
  Launch faster than animation
  Duration varies on devices
  400ms is a good target
  Don't go longer than 20 seconds
    App will be killed
  Test on the slowest supported device

Launch recap
  Parse images
  Map images
  Rebase images
  Bind images
  run image initializers
  Call main
  call UIAppciaitonMain
  Call applciationWillFinishLaunching

Warm vs cold launch
  warm launch
    app and data already in memory
  cold launch
    not in disk cache;
    app is not in kernel buffer cache
  warm and cold launch times will be different

Measuring before main() id difficult
dyld has built in measurements
  DYLD_PRINT_STATSTICS environment variable
    available on shipping OSes
    Significantly enhanced in new OSes
  Debugger pauses every dylib load
    dyld subclasses

scheme editor:
  DYLD_PRINT_STATISTICS 1

  Embedded dylibs are expensive: 100 - 400 dylibs per app
  Use fewer dylibs
    Merge existing dylibs
    Use static archives
  Lazy load, but
    dlopen() can cause issues
    Actually more work overall

  Dylib is a Link Binary with libraries
    half a dozen dylibs is good amount

    Rebase/Binding
      Reduce __DATA pointers
      Reduce Objective C metadata
          Classes , selectors, and categories
        Reduce C++ virtual
          VTables
            ObjectiveC meta data
      Reduce C__ virtual
      use Swift structs
      Examine machine generated code
        Use offsets instead of pointers
        Mark read only
  Initializers
    Explicit

      ObjectiveC +load methods
        Replace with +initialize
        C/C+ __attribute__((constructor))
      replace w/dispatch_once
    Implicit
      C++ statics with non-trivial constructors
        Replace with call site initializers
        Only set simple values (PODs)
        -Wglobal-constuctors
        Rewrite in Swift

      Do NOT call dlopen() in initializers

      Do not create threads in initializers

  TL;DR
    Measure launch times with DYLD_PRINT_STATISTICS
    Reduce launch times by
      Embedding fewer dylibs
      Consolidating Objective-C classes
      Eliminate static initializers
    Use Swift
    run dyldinfo on any binary!!

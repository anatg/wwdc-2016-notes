Allocation
  Stack- add/remove to the end of the stack
  call into a function, we decrement stack pointer to allocate, increment stack pointer to deallocate.
    cost of assigning an integer
  Heap
    allocate memory with a dynamic lifetime.
    Advanced data structure
    Search for unused block of memory to allocated
    reissue block of memory to deallocate
    Thread safety overhead

  because Point is a struct, we are just adding
    value semantics.
  class:
    for the storage of the properties of the point...they're on the heap.
      for reference semantics.
  classes are more expensive than structs
    have reference semantics
    identify and indirect storage
    structs aren't prone to unintended sharing of code.

  String isn't a strong type for the key
    can represent so many things.
      incurs a heap allocation
    Better to represent attributes as a struct

Reference Counting
  How does Swift know when its safe to deallocate memory on the heap?
    reference counting is a frequent operation
      Indirection
      Thread safety overhead
  If structs contain a reference, they contain more reference counting than a class..
    UUID struct: no longer a string..it's a struct.
    mimeType
      make it a enum

Method dispatch
  Jump directly to implementation at run time
  Candidate for inlining and other

  Dynamic dispatch
    Look up implementation in table at run time
    Then jump to implementation
    Prevents inlining and other optimizations
    Polymorphism:
      Inheritance-based
  inlining
    final: never subclassed. never going to be dynamically
    
Protocol-oriented stuff

  Polymorphism without inheritance or reference semantics.
    No more Virtual memory table.
  Protocol Witness Table (PWT)
    Protocol WitnessL dynamic dispatch without a virtual table
  The Existential Container
    Boxing values of protocol types:
      Inline Value Buffer: currently 3 words: value buffer.
        Small types fit in there
        larger types: allocates memory on the heap and adds pointer to the stuff
      Large Values stored on heap
      Reference to Value Witness Table
      Reference to Protocol Witness Table

  Value Witness Table (VWT)
    Allocation, Copy, Destruction of any Value

Protocol type Stored Properties
  struct Pair {
    init(_ f: Drawable, _ s: Drawable) {
      first = f; second = s
    }
    var first: Drawable
    var second: Drawable

  }
  var pair = Pair(Line(), Point())

Protocol-type - Large value
  Expensive
    implement structs with indirect storage through copy and write

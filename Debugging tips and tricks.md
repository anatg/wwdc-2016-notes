LLDB: lower level debugger

Scheme option to use standalone terminal
  Console: Use terminal/Use xcode  under scheme options


LLDB is
  ":<command>"
  :type lookup Comparable
    type :help

    :type lookup abs
    :type lookup Swift

  :b 2
  greet->

  bt: backtrace (at any point)

LLDB is also a command-line tool
  ideal for automating debugging tasks
  Provide a file containing LLDB commands
    lldb -source <filename>
  Provide LLDB without requiring a file
    lldb --one-line <command> -o <command2>
  Run a series of commands and exit -unless target crashes
    while true; lldb --bash --source <filename>; done
  review lldb -help


Xcode 8 and LLDB: distinct processes
  different process from xcode
    Multiple versions of the debugger

Customization and Introspection
  Customize your debugger for greater awesomeness
  command aliases
    create shorter syntax for frequent actions
    customize help text
  custom commands
    command alias -h ""Run a command in the Unix shell" -- shell platform shell

  data formatters
  stepping actions

  Scripting LLDB in Python:
    comes with a python API
    a command to retrieve the return value of the last function call
    Only works if you finish your way out of a function
      And don't step

      command script import ~/getreturn.py
    Persistent Customizations
      save yourself from repetitive typing
      Initialization file:
        ~/.lldbinit
        Xcode specific ~/.lldbinit-Xcode
      Python at startup use command script import

    Data served three ways
      p expression
      po expression
        executed in target
        not always possible
        full expressions
        po runs code twice.

      frame variable <local -name>
        doesn't run code.
        Extremely predictable
        Limited syntax
      parray <count> <expression>
      poarray <count> <expression>
        C pointers have no notion of element count

        parray `count` dataset (gives the full array)

      swift is
        not all swift objects have pointer value o

      expr -O --language objc -- [mem address]
        it's like


        Reading registers
          arguments often passed in registers
          Mapping given by Application Binary Interface (ABI)
          debugger exposes $arg1, $arg2

        memory read
      disassemble frame
        ni: step over
        si: step in
      getGlobalToken() returns an invalid object
      Subsequent use causes a crash

  Expression Parsing
    p [NSApplicaiton sharedApplciation].undoo
    expr let a = 3; print(a)

    expr let $a = 3; print)$a -> never collides with variable names

    p let $add = { }


Breakpoints
  break set --name main
    19 locations
  break list 1

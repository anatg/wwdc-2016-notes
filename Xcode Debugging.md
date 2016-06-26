Runtime Issues
  Threading
    Thread Sanitizer
      Data races
      Use of uninitialized mutexes
      Unlock from wrong thread
      Thread leaks
      Unsafe calls in signal handlers

    UI
      Layout issues

    Memory
      Leaked memory
View debugging
  70% faster snapshots...
  Layout and transform accuracy
  Blur rendering
  Jump to class
  Navigator filtering
  Autolayout debugging
  Ambiguous layouts are reported as runtime issues
    Highlighted in the activity viewer
    Listed in the issue navigator
State machine quick looks
  GKStateMachine
    Directed graph defining complex behavior
    Provide discrete behavior per-state
    Define transitions between

spriteKit/SceneKit FPS gauge
FPS Performance Gauge
  Break down the update loop
    Render
    Client update
    Actions
    Physics
  Easy to identify bottle necks

Memory graph debugging
  Leaked and abandoned memory
    Debugger mode, pauses to inspect app
    Available on macOS, iOS 10, tvOS 10, watchOS 3

  Two graph styles
    Root paths
      Referenced memory
    .memgraph
      export memory graph
      load double click or drag to xcode
        no process in debugger, no backtraces, quick look, 'po'
      leaks --outputGraph=<path> <process>

    Graph is conservative
      Avoids 'leaks' false-positives, but there may be extraneous references
      Gray references are unknown, may be stale pointer or not strong. Enabling malloc Scribble may improve accuracy

    Bold references are known to be strong
      Swift 3's reflection data is more accurate
    Requires turning off sanitizers

  Validate your expectations
    Are there more objects of your types than you expect, are there many leaks?
  Find the path that shouldn't be holding your object.
    Strong captures from blocks and closures
    Back references

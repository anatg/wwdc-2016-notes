Sanitizers:
  Find bugs at run time
  Similar to Valgrind
  Low overhead
  Work with Swift 3

Address Sanitizer (ASan)
  Finds memory coruption issues
  Effective at finding critical bugs

Threading Sanitizer (TSan)
  Use of uninitialized mutexes (pthread_join)
  thread leaks
  Unsafe calls in signal handlers
  Unlock from wrong thread

Edit Scheme
  Diagnostics
    Thread Sanitizer


Thread sanitizer
  Timing does not matter
  Can detect races even if they did not manifest during the particular run

Static Analyzer
  Find bugs without running code

Static Analyzer:
  Product
  Analyze

Find missing localizability

Do not release assign properties
DO release retain/copy properties

Nullability
  Indicate whether a value is expected to be nil

  NS_ASSUME_NON_NULL

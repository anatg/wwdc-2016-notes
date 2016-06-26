Importing Objective C APIs:
  Import as Member: set them as
  Stringly typed objective-C constants can be changed with type checked typedefs

  Warn on unused stuff: disposableresult

Features removed in Swift 3:
  Focus and simplify the language
  SE-0002, 0003, 0004, 0007, 0029

UnsafePointer Nullability
  let UnsafeMutablePointer<int>? = nil

Implicitly unwrapped options (IUO)
  func f(value: Int!) {
    let x = value + 1
    let y = value
  }
  For any use of an optional


Standard Library:
  New Collection Indexing Model
    haffOpenInterval and IntervalType are merged into Range...
      0...UInt8.max

  Floating Point and Numerics
    New FloatingPoint protocol unifies Float, Double, Float80, CGFLoat



Compiler is caching more. First time we compile is slow, incremental compilations should be faster

Code size optimization

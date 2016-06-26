

Swift API Design Guidelines
  Design APIs to make uses clear and concise
  Uses of APIs always have surrounding context
  "wrong. caffeine is not an element. it is a compound made up of elements"
  function name is made up of base name, but the argument labels are different
  remove(_:)
  remove(at:)
  Objective C selectors
    Use #selector for Objective-C selectors

    extension MyController {
      func handleDrag(sender: UIControl)
    }

  class MyController: NSObject {
    key paths via #keyPath ()
  }

The Grand Renaming
  All objective C
Mapping Objective-C APIs
  Automatic Translation of Objective-C APIs
    Identify first argument labels
    Remove words that restate type information
    Introduce default arguments
    Use bridged value types

    typdedef NSString * NSCalendarIdentifier NS_EXTENSIBLE_STRING_ENUM;
    NSCalendarIdentifier NSCalendarIdentifierGregorian

    Strongly typed! :D

    let cal = NSCalendar(identifier: .gregorian)
    NSCalendar -> Calendar

    C APIs: we have an elephant! That is, we have an elephant in the room..

    Core Graphics:

    CGStringRef kCGColorWHite NS_SWIFT_NAME(CGCOlor.white);

    we love the NS Swift names so much that we applied it to 600
    we went absolutely bananas... (audience claps)...plz don't clap for this.

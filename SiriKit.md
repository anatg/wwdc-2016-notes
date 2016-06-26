Preparing to Adopt SiriKit
  Embedded frameworks
    reuse code between app and extension
    unit tests
    Mock intents


  Architecting your extensions
    SendMessageIntent
    StartAudioCallIntent
    StartVideoCallIntent

Add Extension Target
  Add extension
Configure Info.plist
  NSExtension: NSExtensionAttributes
    intentsSupported
      array of class names
    IntentsRestrictedWhileLocked
      optional key for lock screen behavior

Modify principal class
  Subclass

  INExtension
    Resolve
      validate and clarify parameters
        Implement if you need Siri's help to
    Confirm
      authenticated
    Handle


NSUserActivity
  Resume state in your app
    Siri creates one for you when passing in Nil


user-specific vocabulary

  DispatchQueue(label: "UCSiriVocabulary").asynchronously
  var unicornNames - OrderedSet(array: self.sortedFavoriteUnicornNames)

UI Extensions Increase your App's Impact
  Your view alongside Siri
  Experiences unique to your application

Implementing VC with two actions
  siri snippet
  maps view

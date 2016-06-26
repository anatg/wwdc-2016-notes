Core Technologies
  Swift 3
  GCD
    Create a private queue
    schedule asynchronous work items
    GCD can automatically wrap each work item in an autorelease pool
  Foundation
    Swift improvements
      valuetypes
    Units and measurement
    NSISO8601DateFormatter
    NSDateInterval
    UIPasteboard
      Universal clipboard
      A paste operation might have to retrieve remote Datacheck for pasteboard content without Fetching
    Wide Color
      Technology shift
      From sRGB
      UIImageView, color-managed since
      UIColor Support—go beyond [0-1] for extended sRGB with existing initializer
      Use displayP3 for content creation and interchange

    Asset Management
      Wide color assets
        Automatic variants generation
        Compatible with App Thinning
      Directional image assets

    Accessibility Inspector

    Dynamic type
      Content size category trait
      Automatically works for labels, buttons, text

    Improved Customization
      Tab bar items
      Custom badge colors and text attributes
      Customizable unselected Tint Color
    Peek & Pop
      Improved WKWebView Support
      UIPreviewInteraction
        Bring your own UI
        How do we react to
        updateUIToPeek—you can
    Scroll View
      UIREFRESHControl
    Collection View
      Automatic self-sizing cells in flow Layout
      paging support in collection view reordering
      smooth scrolling
      cell-prefetching
      data prefetching
      also available in UITableView
    NSUserActivity
      Capture the state of your Application
      Infrastructure for Handoff, Spotlight
      Now supports locations
    CoreSpotlight Search API
      CSSearchQuery
      Search the data you've already indexed with Spotlight
      Great power and performance, full content search
      powerful query syntax
    Widgets
      Be consistent with your widget

    User Notifications
      New framework:
        feature parity
        unifies local and remote notification
        better delivery management
        in-app presentation option
        multi=platform
      Non-UI extension point
      Use cases
        Media attachments
        end-to-end encryption
      Content extension
        UI extension point
        Custom views
        No direct Interaction
    CallKit
      Blocking
      Identification

      Integrated with other types of calls
      VoIP
    Intents Extension
      Handle the interaction between Siri and your Application
        Intents and responses
      Intents are domain specific
        Make sure Siri and your app agree on the request before performing it

      Intents are shared
        For Siri to communicate with your app
        To integrate with CallKit
        For Ride Sharing in Maps
        to donate information to the system about a contact
    iMessage Apps
      Sticker packs
      Message Extension
      Dynamic stickers content

User Notifications
  User-facing- expected
  silent update
    triggers background app refresh
User Notification Framework
  Notification settings
    Configurable—access to user-defined registration
  Notification handling
    (Application in foreground)
    (In-app presentation)
Notification Actions
  Default Action
  Actionable Notifications
  Dismiss
    customDismissAction; UNNotificationCategoryOptions
  Response handling
    One delegate method to rule them all.
Service Extension
  end-to-end encryption
  add attachments

UNNotificationServiceExtension
  didReceive w/ContentHandler
    decryptedBody - decrypt(notification.content['encryptedMessage'])
    let newContent = UN
    newContent.body = decryptedBody
    contentHandler(newContent)
  serviceExtensionTimeWillExpire

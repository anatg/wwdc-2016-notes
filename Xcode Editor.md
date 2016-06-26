option + cmd: documentation comment...
on or above a function

cmd + 6, opens the object menu.

every image literal is available in the source editor...
timerButton.image = TimerButton

layers take CGColors: option shift..


Find pasteboard
  cmd + G
  find and replace in the same file: cmd + control + e: edit all macros in the file

select miles: cmd + option bracket, select code and it'll move it up and down..

find across files


Extending Xcode
  add commands to the source editor
  edit text
  change selections
  one extension, several commands
  Xcode Extensions are Application Extensions

xcsourceTextBuffer: NSObject {
  contentUTI: String (type identifier)

  public let tabWidth
  indentationWidth
  UsesTabsForIndentation

  public var completeBuffer

  public let selections: NSMutableArray<XCSourceTextRange> multiple selections.

  public let lines: NSMutableArray: only need to send back the changes you've made, not the whole buffer
}

NSSourceTextRange

Add XcodeSourceEditor Extension under OS X
  perform with invocation

NSExtension
  NSExtensionAttributes
  XCSourceEditorCommandDefinitions
  only modifying invocation.buffer.lines

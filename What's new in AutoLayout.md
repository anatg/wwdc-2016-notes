Use autoresizing masks until ready for constraints
  width-resizable, pin to the other edge.
  height resizable
  auto-resizing masks dont take into account the contents of the view.
  fix font-size to minimal font size.
  resolve autolayout issues menu, update frames.
  move to top of document outline so it's in the back.
Constrain views by subtree
Adopt auto Layout on your own terms

Mixing Design and Runtime constraints
  Placeholder constraints
    Simulate constraint behavior at design time
    Arbitrary layout defined with runtime constraints


Layout Feedback Loop
  setNeedsLayout
    what views are needed
  Layout Feedback loop debugger:
    UIViewLayoutFeedbackLoopDebuggingThreshold 100

Ambiguous layout:
  tAMIC: translates autoresizing mask into constraints

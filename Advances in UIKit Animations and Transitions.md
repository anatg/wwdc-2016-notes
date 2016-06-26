UIViewPropertyAnimator
  Interpolation and pacing
    timing function: cubic function that maps 0,1 to 0,1
    Normalized Value (m(s))
    4 timing function
    linear, .easeInOUt, EaseIn, EaseOut

  UIViewPropertyAnimator
    available properties:
      state
      isRunning
      isReversed

    completion(.end)

  handleProgress (_ gr: UIPangestureRecognizer)
    map time back to
    Timing objects w/bezier curves...!

    UISpringTimingParameters()

UIViewControllerAnimated Transitioning
  UiViewControllerInteractiveTransitioning
  UIViewControllerAnimatedTransitioning
  UIViewControllerContextTransitioning

ViewController
  interruptibleAnimator(using: context)
Delegate
  Interaction controller controls animation more than start and ended animation methods.

Demo of a new Photo sample app
Animation to Gesture Revisited

Hit Testing:
  animator.isManualHitTestingEnabled = false (default)
Keyframe Animations

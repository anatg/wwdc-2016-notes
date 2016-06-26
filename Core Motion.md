Historical Accelerometer
  CMSensorPrecorder
  CMPedometer
    Manual Pause and Resume
    Inaccurate distance and pace

  Why not use GPS or steps to auto-pause and resume?
    step counter has built-in delay to avoid false positives

  Predictive algorithm to recover latency
    woohoo!
    supports both running and walking pace
    continuous
      add work from all handlers to the same apQueue

    Pedometer events only in iPhone 6/6+

  Device Motion on Apple Watch
    attitude
      Device orientation
        quaternion
        Rotation matrix
        Euler angle (roll, pitch, yaw)
      Relative to reference frame
      Orientation from a point not fixed to device
      Reference frame set at start of updates

    gravity (to observe orientation-only in limited form...not used as much)
      Unit vector in device frame
      tip and tilt of the device
      set using accelerometer while static
    rotation rate
      Change in angular motion in device frame
    acceleration
      change in device frame
      compensated for gravity
        just user

Property    Example Measurement   Example use Case
---------------------------------------------------
Attitude    Rep counting          Weight training
Gravity     tracking poses        Yoga (can tell how still they are)
Rotation Rt Speed of circ. motion Bat speed
Usr Accel.  dx in linear motion   punch/recoil


sample stuff
Enable background modes: workout processing
average CPU usage must be reduced

concept
  UI
  Workout manager
    Create workout session
    start and stop workout
  Motion Manager
    start updates
    processDeviceMotion
      yawRotation
    stop updates

Model swing as a rotation about the user
Extract component parallel with ground
Gate detections on sufficient angle

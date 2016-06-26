trait system

horizontal size class = compact
  Base layout on available space, not device, orientation, or adoption
    Coarse Changes
      SizeClasses are a layer of indirection

    Fine Changes

  propagating changes
    UITraitEnvironment
    traitCollectionDidChange

  override func traitCollectionDidChange(_ previousTraits:UITraitCollection) {

    if previousTraitColelction.horizontalSizeClass
  }


  If you use an exhaustive switch statement, you get build time warnings!

Some systems react to traitCollectionDidChange(:)
  * Interface Builder
  * Asset catalog
  * UIAppearance

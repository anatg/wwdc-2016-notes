Smooth Scrolling
  prepare for reuse
  cellForItemAtIndexPath: access datamodel
  willDisplayCell
  ---cell is off screen--
  didEndDisplayingCell

ios10
  willDisplayCell
  didEndDisplayingCell

UICollectionViewDataSourcePRefetching
  collectionView prefetchItemsAt indexPaths

  optional: cancelPrefetchingForItemsAt indexPaths


Self-sizing cells API overview
  Full support in UICollectionViewFlowLayout
    Layout.estimatedItemSize

  Three options for specifying actual cell size
    Auto Layout
    Override sizeThatFits
    preferredLayoutAttributesFittingAttributes

  new api:
    layout.estimatedItemSize - UIColectionViewFlowLayoutAutomaticSize
      collection view will do the math for you

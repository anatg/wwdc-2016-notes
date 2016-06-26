3D Touch
  blur and scale effects
  Enable new immersive interactions

Home Screen Quick Actions
  Defined in your app's Info.plist
  Available as soon as your app has been installed
  Created at runtime. Only available on first launch
  Dynamic quick actions are
  Can include a system icon, custom icon, or Address Book contact

  App in suspended state:
    application performActionForShortcutItem (completion handler)
  App was launched
    applicationDidFinishLaunchingWithOptions
      access shortcutItem key...
    Key version number in the user info plist

Preview
  Peek
    if you continue to apply to pressure: commit (full screen)
    Registered View Controller
      UIViewControllerPreviewingDelegate

      viewDidLoad
        registerForPreviewing(with: self, sourceView: tableView)
      previewingContext viewCotnrollerForLocation
        guard let indexPath = tableView.indexPathForRow(at: location) else { return nil }
        let chatDetailViewController = ...
        cellRect = tableview.rectForRow
        let sourceRect = previewingContext.sourceView.convert(cellRect)
        previewingContext.sourceRect = sourceRect

        return chatDetailViewController
      previewingContext (second thing)

    PreviewedView Controller
      preview quick actions
        previewActionItems() [UIPreviewActionItem] {
        let heart = UIPreviewAction
        }
        return [heart]

      UIPreviewActionGroup

Peek and Pop Best practices
  Content that can be tapped should support Peek and Pop
  Return a preview VC consistently
  set the previewing context sourceRect

UIPreviewInteraction
  UIPreviewInteractionDelegate (protocol) via extension :D

  viewDidLoad
    replyPreviewInteraction - UIPreivewInteraction(view: view)
    previewInteractionShouldBegin
  previewInteraction(didUpdatePreviewTransition:ended:)
    updateForPreview(progress: transitionProgress)
    if ended {
      completePreview
    }
  previewInteractionDidCancel(_ previewInteraction UIPreviewInteraction)
    UIView.animate(withDuration: 0.4) {

    }
  previewInteraction(didUpdateCommitTransition:ended) {
    updateForCommit(progress; transitionProgress)
    if ended {
      completedCommit()
    }
  }

Low-level force API
  Normalized access to force data
  Properties on UITouch: force and maximumPossibleForce
  Available on devices that support 3D Touch and apple touch pencil

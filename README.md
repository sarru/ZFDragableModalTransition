# ZFDragableModalTransition

[![Version](https://img.shields.io/cocoapods/v/ZFDragableModalTransition.svg?style=flat)](http://cocoadocs.org/docsets/ZFDragableModalTransition)
[![License](https://img.shields.io/cocoapods/l/ZFDragableModalTransition.svg?style=flat)](http://cocoadocs.org/docsets/ZFDragableModalTransition)
[![Platform](https://img.shields.io/cocoapods/p/ZFDragableModalTransition.svg?style=flat)](http://cocoadocs.org/docsets/ZFDragableModalTransition)

<p align="center"><img src="https://raw.githubusercontent.com/zoonooz/ZFDragableModalTransition/master/Screenshot/ss.gif"/></p>

## Usage

```objc
- (void)prepareForSegue:(UIStoryboardSegue *)segue sender:(id)sender
{
    TaskDetailViewController *detailViewController = segue.destinationViewController;
    detailViewController.task = sender;
    
    // create animator object with instance of modal view controller
    ZFModalTransitionAnimator *animator = [[ZFModalTransitionAnimator alloc] initWithModalViewController:detailViewController];
    animator.dragable = YES;
    animator.direction = ZFModalTransitonDirectionBottom;
    [animator setContentScrollView:detailViewController.scrollview];
    
    // set transition delegate of modal view controller to our object
    detailViewController.transitioningDelegate = animator;
    detailViewController.modalPresentationStyle = UIModalPresentationCustom;
}
```
###ScrollView
If you have scrollview in the modal and you want to dismiss modal by drag it, you need to set scrollview to ZFModalTransitionAnimator instance.
```objc
[animator setContentScrollView:detailViewController.scrollview];
```

###Direction
You can set that which direction will our modal present. (default is ZFModalTransitonDirectionBottom)
```objc
animator.direction = ZFModalTransitonDirectionBottom;
```
P.S. Now you can set content scrollview only with ZFModalTransitonDirectionBottom

## Requirements
- iOS >= 7.0
- ARC

## Installation

ZFDragableModalTransition is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

    pod "ZFDragableModalTransition"

## Author

Amornchai Kanokpullwad, amornchai.zoon@gmail.com

## License

ZFDragableModalTransition is available under the MIT license. See the LICENSE file for more info.


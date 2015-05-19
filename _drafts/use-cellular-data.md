Using NSURLSession...

{% highlight objective-c %}
    session.configuration.allowsCellularAccess = NO;
{% endhighlight %}

{% highlight objective-c  linenos %}
Error Domain=NSURLErrorDomain Code=-1009 "The Internet connection appears to be offline." UserInfo=0x1700f3b00 {NSUnderlyingError=0x174051d00 "The operation couldn’t be completed. (kCFErrorDomainCFNetwork error -1009.)", NSErrorFailingURLStringKey=https://www.google.com/search?q=1431982393.458148, NSErrorFailingURLKey=https://www.google.com/search?q=1431982393.458148, _kCFStreamErrorDomainKey=1, _kCFStreamErrorCodeKey=50, NSLocalizedDescription=The Internet connection appears to be offline.}
{% endhighlight %}

alert appears:
- when the flag has been turned off and not in wifi
-

https://developer.apple.com/library/mac/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/Platform-SpecificNetworkingTechnologies/Platform-SpecificNetworkingTechnologies.html#//apple_ref/doc/uid/TP40010220-CH212-SW9

https://devforums.apple.com/message/1070302#1070302

Reason for switch to appear is when a certain amount of requests over cellular network.


```
_NSThreadDidStartNotification
2015-05-18 23:16:03.355 transient[3733:415376] UINavigationControllerWillShowViewControllerNotification
2015-05-18 23:16:03.362 transient[3733:415376] UIViewAnimationDidCommitNotification
2015-05-18 23:16:03.366 transient[3733:415376] UIViewAnimationDidCommitNotification
2015-05-18 23:16:03.367 transient[3733:415376] UIViewAnimationDidCommitNotification
2015-05-18 23:16:03.367 transient[3733:415376] UIViewAnimationDidStopNotification
2015-05-18 23:16:03.467 transient[3733:415376] _UIApplicationWillAddDeactivationReasonNotification

_UIApplicationDidRemoveDeactivationReasonNotification
2015-05-18 23:17:58.319 transient[3733:415376] _UIApplicationWillAddDeactivationReasonNotification
2015-05-18 23:17:58.321 transient[3733:415376] _UIWindowDidCreateWindowContextNotification
2015-05-18 23:17:58.323 transient[3733:415376] _UIWindowDidCreateWindowContextNotification
2015-05-18 23:17:58.326 transient[3733:415376] UIApplicationWillEnterForegroundNotification
2015-05-18 23:17:58.327 transient[3733:415376] _UIApplicationDidRemoveDeactivationReasonNotification
2015-05-18 23:17:58.327 transient[3733:415376] UIApplicationResumedNotification
2015-05-18 23:17:58.788 transient[3733:415376] _UIApplicationDidRemoveDeactivationReasonNotification
2015-05-18 23:17:58.790 transient[3733:415376] UIApplicationDidBecomeActiveNotification
2015-05-18 23:18:00.615 transient[3733:415376] UIDeviceOrientationDidChangeNotification


2015-05-18 23:24:36.231 transient[3768:418490] applicationWillAddDeactivationReasonNotification NSConcreteNotification 0x174051fa0 {name = _UIApplicationWillAddDeactivationReasonNotification; object = <UIApplication: 0x15ce09620>; userInfo = {
    "_UIApplicationDeactivationReasonUserInfoKey" = 10;
}}



2015-05-18 23:24:35.368 transient[3768:418490] applicationDidRemoveDeactivationReasonNotification NSConcreteNotification 0x174051010 {name = _UIApplicationDidRemoveDeactivationReasonNotification; object = <UIApplication: 0x15ce09620>; userInfo = {
    "_UIApplicationDeactivationReasonUserInfoKey" = 8;
}}
2015-05-18 23:24:35.850 transient[3768:418490] applicationDidRemoveDeactivationReasonNotification NSConcreteNotification 0x17404bc70 {name = _UIApplicationDidRemoveDeactivationReasonNotification; object = <UIApplication: 0x15ce09620>; userInfo = {
    "_UIApplicationDeactivationReasonUserInfoKey" = 5;
}}
2015-05-18 23:24:35.877 transient[3768:

2015-05-18 23:25:16.516 transient[3768:418490] applicationDidRemoveDeactivationReasonNotification NSConcreteNotification 0x17404ed60 {name = _UIApplicationDidRemoveDeactivationReasonNotification; object = <UIApplication: 0x15ce09620>; userInfo = {
    "_UIApplicationDeactivationReasonUserInfoKey" = 10;
}}
```

http://stackoverflow.com/questions/14409739/does-anyone-know-uiapplicationdidremovedeactivationreasonnotification


siri

```
2015-05-18 23:32:15.995 transient[3784:420029] applicationWillAddDeactivationReasonNotification NSConcreteNotification 0x174242a60 {name = _UIApplicationWillAddDeactivationReasonNotification; object = <UIApplication: 0x134d0ebc0>; userInfo = {
    "_UIApplicationDeactivationReasonUserInfoKey" = 4;
}}
2015-05-18 23:32:23.572 transient[3784:420029] applicationDidRemoveDeactivationReasonNotification NSConcreteNotification 0x1742478c0 {name = _UIApplicationDidRemoveDeactivationReasonNotification; object = <UIApplication: 0x134d0ebc0>; userInfo = {
    "_UIApplicationDeactivationReasonUserInfoKey" = 4;
}}

```

timer

```
2015-05-18 23:34:33.327 transient[3784:420029] applicationWillAddDeactivationReasonNotification NSConcreteNotification 0x174246e10 {name = _UIApplicationWillAddDeactivationReasonNotification; object = <UIApplication: 0x134d0ebc0>; userInfo = {
    "_UIApplicationDeactivationReasonUserInfoKey" = 10;
}}
2015-05-18 23:34:43.208 transient[3784:420029] applicationDidRemoveDeactivationReasonNotification NSConcreteNotification 0x17024a9b0 {name = _UIApplicationDidRemoveDeactivationReasonNotification; object = <UIApplication: 0x134d0ebc0>; userInfo = {
    "_UIApplicationDeactivationReasonUserInfoKey" = 10;
}}
```

lockscreen

```
2015-05-18 23:36:27.981 transient[3784:420029] applicationWillAddDeactivationReasonNotification NSConcreteNotification 0x174249930 {name = _UIApplicationWillAddDeactivationReasonNotification; object = <UIApplication: 0x134d0ebc0>; userInfo = {
    "_UIApplicationDeactivationReasonUserInfoKey" = 9;
}}
```

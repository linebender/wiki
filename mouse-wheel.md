# Mouse wheel notes

What does scrolling actually mean? It depends on the platform.

See [druid#68](https://github.com/xi-editor/druid/pull/68) for the code that implements this. There are some additional links and comments in the review.

## Web
[W3C's WheelEvent](https://w3c.github.io/uievents/#event-type-wheel) specifies it as the “expected amount the page will scroll”

On my Windows machine, “away from user” is a negative number. At lines = 3 (in preferences), one bump of the physical mouse wheel is 200. Rightward motion on the trackpad is a positive number.

On my Mac, when “Scroll direction: Natural” is checked, “away from user” is a positive number, and rightward motion on the trackpad is a negative number. Both flip when it is unchecked. The magnitude is dependent on the rate of scrolling (i.e. this is adaptively scaled).

See significant discussion in [Chromium issue 227454](https://bugs.chromium.org/p/chromium/issues/detail?id=227454), including having got the polarity wrong.

## Windows
[The doc for WM_MOUSEWHEEL message](https://docs.microsoft.com/en-us/windows/win32/inputdev/wm-mousewheel) specifies that rolling away from the user is a positive number. Rightward motion on the trackpad is a positive number.

One bump of the external scroll wheel is 120, consistent with documentation.

The sensitivity setting should be read from `SystemParametersInfo`.

## macOS
[The doc for NSEvent scrollingDeltaY](https://developer.apple.com/documentation/appkit/nsevent/1535387-scrollingdeltay)is not helpful.

The value of `scrollingDeltaX` and `scrollingDeltaY` is the negative of the web value. Note also, `hasPreciseScrollingDeltas` is true for trackpad and false for external mice.

The value of `scrollingDeltaX` and `scrollingDeltaY` inverts when the “Scroll direction: Natural” setting is toggled, i.e .the setting is applied before the event is given to the app.


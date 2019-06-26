# Drawing: coordinate system

## Device independence

Distinguishing between logical user space coordinates and physical device space coordinates

Precedence:
* [Core Graphics](https://developer.apple.com/documentation/coregraphics/cgcontext/1455677-userspacetodevicespacetransform)
* [Direct2D](https://docs.microsoft.com/en-us/windows/desktop/Direct2D/direct2d-portal)
* [Java2D](https://docs.oracle.com/javase/tutorial/2d/overview/coordinate.html)
* [Qt](https://doc.qt.io/qt-5/paintsystem-devices.html)


## Y-coordinates: up or down?

Affects the meaning of angles, winding and rectangle parameters (top/bottom).

Precedence:
* _Y-coordinates down_:
  * [Direct2D](https://docs.microsoft.com/en-us/windows/desktop/Direct2D/direct2d-portal), but can be [transformed](https://docs.microsoft.com/en-us/windows/desktop/Direct2D/id2d1rendertarget-settransform)
  * [Java 2D](https://docs.oracle.com/javase/tutorial/2d/overview/coordinate.html), but can be transformed
  * [Qt](https://doc.qt.io/qt-5/coordsys.html), but can be [transformed](https://doc.qt.io/qt-5/qpainter.html#setWorldTransform)
* _Y-coordinates up_:
  * [Core Graphics](https://developer.apple.com/documentation/coregraphics), but can be [transformed](https://developer.apple.com/documentation/appkit/nsview/1483532-isflipped)

### Discussion

* Pro _Y-coordinates down_:
  * used widely. [Early APIs](https://en.wikipedia.org/wiki/QuickDraw) used it probably due to the use of [CRTs](https://en.wikipedia.org/wiki/Cathode-ray_tube).
* Pro _Y-coordinates up_:
  * matches convention in mathematics

### Status

[open](https://github.com/linebender/kurbo/issues/4): use _Y-coordinates down_?

# Drawing: 2D data types

## Point, Vector

A point is used to define a location relative to the origin.
A vector is used to describe locations relative to each other (translation).

Precedence:
* has only _point_:
  * Qt: [QPointF](https://doc.qt.io/qt-5/qpointf.html)
* has only _vector_:
  * ???
* has both _point_ and _vector_:
  * CoreGraphics: [CGPoint](https://developer.apple.com/documentation/coregraphics/cgpoint), [CGVector](https://developer.apple.com/documentation/coregraphics/cgvector)
  * Direct2D: [D2D_POINT_2F](https://docs.microsoft.com/en-us/windows/desktop/api/dcommon/ns-dcommon-d2d_point_2f), [D2D_VECTOR_2F](https://docs.microsoft.com/en-us/windows/desktop/api/dcommon/ns-dcommon-d2d_vector_2f)

### Status

Open: should everyone use [euclid's Point2D](https://github.com/servo/euclid/blob/master/src/point.rs) and [euclid's Vector2D](https://github.com/servo/euclid/blob/master/src/vector.rs)?

[kurbo can't](https://github.com/linebender/kurbo/issues/26).

* [font-kit](https://github.com/pcwalton/font-kit)
  * ✓ uses [euclid's Point2D](https://github.com/servo/euclid/blob/master/src/point.rs)
  * ✓ uses [euclid's Vector2D](https://github.com/servo/euclid/blob/master/src/vector.rs)
* [kurbo](https://github.com/linebender/kurbo)
  * uses [its own Point](https://github.com/linebender/kurbo/blob/master/src/point.rs)
  * uses [its own Vec2](https://github.com/linebender/kurbo/blob/master/src/vec2.rs)
* [lyon](https://github.com/nical/lyon)
  * ✓ uses [euclid's Point2D](https://github.com/servo/euclid/blob/master/src/point.rs)
  * ✓ uses [euclid's Vector2D](https://github.com/servo/euclid/blob/master/src/vector.rs)
* [Pathfinder](https://github.com/servo/pathfinder)
  * uses [its own Vector2F](https://github.com/servo/pathfinder/blob/master/geometry/src/basic/vector.rs)
* [Piet](https://github.com/linebender/piet)
  * uses [kurbo's Point](https://github.com/linebender/kurbo/blob/master/src/point.rs)
  * uses [kurbo's Vec2](https://github.com/linebender/kurbo/blob/master/src/vec2.rs)
* [skribo](https://github.com/linebender/skribo)
  * ✓ uses [euclid's Point2D](https://github.com/servo/euclid/blob/master/src/point.rs)

## Rectangles

A rectangle can either be defined by _two points_ or a _point plus [size](#size)_.

Precedence:
* _two points_:
  * Direct2D: [D2D_RECT_F](https://docs.microsoft.com/en-us/windows/desktop/api/dcommon/ns-dcommon-d2d_rect_f)
  * Qt: [QRectF](https://doc.qt.io/qt-5/qrectf.html)
* _point plus size_:
  * C++: [basic_bounding_box](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0267r7.pdf)
  * CoreGraphics: [CGRect](https://developer.apple.com/documentation/coregraphics/cgrect)

Discussion:
* Pro _two points_:
  * checking for overlap does not require additions
* Pro _point plus size_:
  * translation requires only the modification of one point, not two
  * less prone to Y-coordindate flips?

### Status

Open: should everyone use [euclid's Rect](https://github.com/servo/euclid/blob/master/src/rect.rs) (point plus size)?

* [druid](https://github.com/xi-editor/druid) uses [its own Geometry](https://github.com/xi-editor/druid/blob/master/src/lib.rs)
* [kurbo](https://github.com/linebender/kurbo) uses [its own Rect (two points)](https://github.com/linebender/kurbo/blob/master/src/rect.rs)
* ✓ [lyon](https://github.com/nical/lyon) uses [euclid's Rect (point plus size)](https://github.com/servo/euclid/blob/master/src/rect.rs)
* [Pathfinder](https://github.com/servo/pathfinder) uses [its own RectF (two points)](https://github.com/servo/pathfinder/blob/master/geometry/src/basic/rect.rs)


## Size

A size (width and height) can either be defined by _two floats_ or by a _dedicated structure_ that holds two floats.

TODO: What is this used for?

Precedence:
* _two floats_:
  * ???
* _dedicated structre_:
  * CoreGraphics: [CGSize](https://developer.apple.com/documentation/coregraphics/cgsize)
  * Qt: [QSizeF](https://doc.qt.io/qt-5/qsizef.html)

### Status

Open: should everyone use [euclid's Size2D](https://github.com/servo/euclid/blob/master/src/size.rs)?

[kurbo can't](https://github.com/linebender/kurbo/issues/26).

* ✓ [font-kit](https://github.com/pcwalton/font-kit) uses [euclid's Size2D](https://github.com/servo/euclid/blob/master/src/size.rs)
* [kurbo](https://github.com/linebender/kurbo) uses [its own Size](https://github.com/linebender/kurbo/blob/master/src/size.rs)
* ✓ [lyon](https://github.com/nical/lyon) uses [euclid's Size2D](https://github.com/servo/euclid/blob/master/src/size.rs)
* ✓ [skribo](https://github.com/linebender/skribo) uses [euclid's Size2D](https://github.com/servo/euclid/blob/master/src/size.rs)

## Path construction

### Data types

Precedence:
* _Point, Rect_:
  * CoreGraphics: [CGContext](https://developer.apple.com/documentation/coregraphics/cgcontext)
  * Qt: [QPainter](https://doc.qt.io/qt-5/qpainter.html)

### Winding

E.g.: Is a rectangle constructed clockwise or counter clockwise?

# Useful Links

{% hint style="info" %}
This wiki is now **archived**. You should instead visit the [Linebender wiki](https://linebender.org/wiki/) at <https://linebender.org/wiki>
{% endhint %}

There are no well-condensed sources of 2D graphics knowledge. Rather, it is dispersed over a wide number of blogs, pages, articles, and brains. This page attempts to collate _links_ to some of this information. 

### History

* A brief history of 2D graphics is presented in this [introduction for a course](https://hal.inria.fr/hal-01815193/document) on digital typography.
* [Font rendering is getting interesting](https://aras-p.info/blog/2017/02/15/Font-Rendering-is-Getting-Interesting/)
* [Why are 2D vector graphics so much harder than 3D?](https://blog.mecheye.net/2019/05/why-is-2d-graphics-is-harder-than-3d-graphics/)

### Blogs

* [Mozilla gfx team ](https://mozillagfx.wordpress.com)\(WebRender, design of 2D graphics APIs for the browser\)
* [nical's blog](https://nical.github.io/index.html) \(Lyon, WebRender, general 2D graphics API design considerations\)
* [kvark's blog](http://kvark.github.io/) \(WebRender, gfx-rs\)
* [pcwalton's blog](https://pcwalton.github.io/) \(Pathfinder 3\)
* [raphlinus' blog](https://raphlinus.github.io/) \(piet, 2D graphics API considerations, fonts, text rendering, splines, general 2D graphics API design considerations\)
* [behdad's page](http://behdad.org/) \(harfbuzz, fonts, text rendering\)

### 2D Graphics API design

* [raphlinus: "A crate I want: 2d graphics"](https://raphlinus.github.io/rust/graphics/2018/10/11/2d-graphics.html)
* [nical: Following up on the 2d graphics in Rust discussion](https://nical.github.io/posts/rust-2d-graphics-01.html)

#### Rust 2D or 3D libs (that aren't `kurbo`)

* [`euclid`](https://lib.rs/crates/euclid) and [`lyon_geom`](https://lib.rs/crates/lyon_geom)
* [`arcs` by Michael-F-Bryan](https://github.com/Michael-F-Bryan/arcs)

### 2D antialiasing and font rasterization

#### Trapezoidal pixel coverage algorithm

* [How the stb\_truetype Anti-Aliased Software Rasterizer v2 Works](https://nothings.org/gamedev/rasterize/)
* [raphlinus: Inside the fastest fontest renderer in the world](https://medium.com/@raphlinus/inside-the-fastest-font-renderer-in-the-world-75ae5270c445)
* \(Skia/Spinel team members\) [Path rendering by counting pixel coverage](https://www.tdcommons.org/cgi/viewcontent.cgi?article=1580&context=dpubs_series)

#### Other

* [Texts Rasterization Exposures: An attempt to improve text rasterization algorithms using only publicly available information](https://web.archive.org/web/20180921225907/http://antigrain.com/research/font_rasterization/index.html#FONT_RASTERIZATION)
* [The Raster Tragedy at Low-Resolution Revisited: Opportunities and Challenges beyond “Delta-Hinting”](http://rastertragedy.com/) \("RL: ...a justification for why Microsoft made exactly the choices they did 10+ years ago..."\)

### Gamma Correction

* [What every coder should know about gamma](https://blog.johnnovak.net/2016/09/21/what-every-coder-should-know-about-gamma/)
* [Wikipedia](https://en.wikipedia.org/wiki/Gamma_correction)

### Papers on approaches to efficient rendering of 2D graphics

* [\(2014\) \(Ganacim, Lima, de Figueiredo, Nehab\) Massively-Parallel Vector Graphics](http://w3.impa.br/~diego/projects/GanEtAl14/)
* [\(2017\) \(Lengyel\) GPU-Centered Font Rendering Directly from Glyph Outlines](http://jcgt.org/published/0006/02/02/) \(Slug Font Rendering Library\)
* [\(2016\) \(Li, Hou, Zhou\) Efficient GPU Path Rendering Using Scanline Rasterization](http://kunzhou.net/zjugaps/pathrendering/)

### Other links on approaches to efficient rendering of 2D graphics

* [Blend 2D - Innovations](https://blend2d.com/doc/innovations.html) \([HN discussion](https://news.ycombinator.com/item?id=19580647)\)
* [thetamath.com - Easy Scalable Text Rendering on the GPU](https://medium.com/@evanwallace/easy-scalable-text-rendering-on-the-gpu-c3f4d782c5ac)
* [nical's Google doc on Pathfinder 3](https://docs.google.com/document/d/146WIsAu7aYC_uvinpCURLS1K8TTSVREAorBi0GCIAMw/edit)

### Mathematics

* [Inclusion of a Point in a Polygon](http://geomalgorithms.com/a03-_inclusion.html) \(winding number\)
* [2D graphics rendering course](http://w3.impa.br/~diego/teaching/2021.0/index.html)

### Repositories of interest

* [makepad](https://github.com/makepad/makepad) \(immediate mode 2D graphics\)
* [spinel](https://fuchsia.googlesource.com/fuchsia/+/refs/heads/master/src/graphics/lib/compute) \(hyper-optimized, Vulkan 1.1 2D graphics\)
* [nanovg](https://github.com/memononen/nanovg) 
* [piet-metal](https://github.com/linebender/piet-metal) \(experimental compute approach to 2D graphics\)
* [pathfinder](https://github.com/pcwalton/pathfinder/) \(pcwalton's Pathfinder 3\)
* [webrender](https://github.com/servo/webrender) \(Mozilla gfx team's WebRender\)
* [glyphy](https://github.com/behdad/glyphy) \(behdad's signed distance field approach to font rendering\)
* [msdfgen](https://github.com/Chlumsky/msdfgen) \(multi-channel signed distance field generator\)

### xi-org Zulip discussions of interest

* [makepad](https://xi.zulipchat.com/#narrow/stream/147926-druid/topic/makepad)
* [Conflation artifacts](https://xi.zulipchat.com/#narrow/stream/197075-gpu/topic/Conflation.20artifacts)
* [Thoughts on piet-metal](https://xi.zulipchat.com/#narrow/stream/197075-gpu/topic/Thoughts.20on.20piet-metal)
* [gpu stream](https://xi.zulipchat.com/#narrow/stream/197075-gpu)

{% hint style="info" %}
This wiki is now **archived**. You should instead visit the [Linebender wiki](https://linebender.org/wiki/) at <https://linebender.org/wiki>
{% endhint %}

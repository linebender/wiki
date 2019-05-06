# Gamma

One of the trickiest aspects to get right in 2D graphics is gamma. A good starting point on the topic is John Novak’s blog, [What Every Coder Should Know About Gamma](https://blog.johnnovak.net/2016/09/21/what-every-coder-should-know-about-gamma/).

Most of what this page says is right, but I bristle a little at the characterization of blending in linear sRGB space as “correct.” Very simply, in many cases it just looks worse. We see that clearly in the examples in the [Massively-Parallel Vector Graphics](http://w3.impa.br/~diego/projects/GanEtAl14/) project; the text in the renders with correct gamma looks weak and spindly, while the versions that blend text in a perceptual sRGB space look much better.

I don’t think this question has a mathematically correct answer, it’s fundamentally a question of aesthetics. At the heart is the most visualy appealing rendering of thin strokes \(especially dark strokes on a light background\). There’s substantial evidence that some form of stroke darkening improves the overall perception. Apple has applied fairly heavy stem darkening in their LCD rendering for some time \(see this [freetype page](https://www.freetype.org/freetype2/docs/text-rendering-general.html) on the subject for more background\). Obviously it’s critical for text reproduction, but also important for fine stroked lines in vector content.

Should this be considered an authoring question \(the designer should specify font and stroke weights that look best with correct rendering\), or an rendering question \(it is up to the renderer to produce the best appearance for the content\)? This is not a question of correctness, but depends on the source of the content. When rendering existing documents, it’s not useful to say, “it should have been created with heavier fonts.”

An interesting parallel is the ink spread in many printing processes, especially letterpress. It’s well known that many digital fonts were created from the metal masters and look too thin, the appearance on a screen very anemic compared with the satisfyingly thick printed representation.

Two other related factors are the scale of the rendering and the resolution of the target screen. Strokes less than one pixel in width look pretty bad no matter what gamma and rendering technique is used; at higher resolution and as the zoom scales up, it looks much nicer, even if lower contrast than it might otherwise be.

In any case, rendering with gamma different than the author’s experience can yield worse results, simply by not respecting the author’s intent, no matter which is “correct.”

As a final critique of Novak’s essay, I found some of the gradient examples unconvincing. It makes sense that they _should_ traverse a perceptual space, rather than one linear in physical light intensity. And I think a strong case can be made that a white-to-black gradient computed in linear intensity is too light, with way too much contrast on the dark side. Here I think it’s important to provide a good set of gradient design tools to the artist, with a choice of colorspace optimized to provide visually satisfying results, and then render that accurately, rather than dictating that gradients computed in a linear space are inherently more “correct.”

That said, especially at 4k, the appearance of vector content antialiased and blended in a linear space is _vastly_ superior, with almost all of the “ropiness”ß gone. Image resampling is similarly much smoother. I agree with Novak that linear blending should be at the basis of rendering, but disagree rather strongly with the assertion that “This is pretty much all there is to gamma encoding and decoding.” Without some attention paid to the fate of very thin strokes, users will be less pleased with correct rendering.


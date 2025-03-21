# Color spaces

{% hint style="info" %}
This wiki is now **archived**. You should instead visit the [Linebender wiki](https://linebender.org/wiki/) at <https://linebender.org/wiki>
{% endhint %}

Many vector shapes in the druid/piet world are drawn with a solid color, and others are drawn with gradients which are defined in terms of colors. This raises the question: what’s the best way to specify colors?

The simplest approach is to use RGB colors. These are well understood, and even standardized in the form of the [sRGB] colorspace. However, it’s not ideal from a color communication perspective, because it’s hard to intuitively understand the relationship between the color and the numeric or hex code. For example, it’s extremely non-obvious when two colors have the same hue. When designing colorways for user interfaces, it’s often desirable to have highlight and accent colors drawn from the same hue, for example.

Another limitation of sRGB is that it covers a fairly limited gamut, and high-gamut (and HDR) displays are entering the mainstream. Fully supporting these HDR colors is beyond the scope of piet now, but we’d like a convention for representing color that will grow to support HDR in the future.

Thus, we’ve recently (in the form of [piet#70]) added a way to specify color using Hue, Luminance, and Chroma. It is based on the colorimetrically sound CIE L*a*b* standard (as opposed to RGB-derived color spaces such as HSV), but these quantities are intuitively clear, and it makes it especially easy to define a family of colors with the same hue. This color space is the same as used by freiefarbe.de.

Following freiefarbe.de, we chose the L*a*b*-based approach because of its simplicity and widespread existing adoption. Newer color spaces such as Jzazbz, IPT, and CAM16 (see references below) promise more perceptually accurate, particularly in hue constancy (where L*a*b* has errors particularly in the blue region). But they are also more complex and there is no consensus on which is best.

## Resources

*  [IPT color space](https://www.researchgate.net/publication/221677980_Development_and_Testing_of_a_Color_Space_IPT_with_Improved_Hue_Uniformity)

* [Jzazbz color space](https://www.researchgate.net/publication/325490579_15-3_New_ICtCp_and_Jzazbz_Color_Spaces_to_Analyze_the_Color_Viewing-Angle_Dependence_of_HDR_and_WCG_Displays)

* [CIECAM02 and CAM 16](https://arxiv.org/pdf/1802.06067.pdf)

* [freiefarbe.de](https://www.freiefarbe.de/en/)

### HDR

* Krita talk on implementing HDR: [slides](https://github.com/libregraphicsmeeting/slides-2019/blob/master/slides/2019-06-01-1000-hdr-support-in-krita.pdf), [video](https://www.youtube.com/watch?v=5MrocfwJd4k)

* [scRGB](https://en.wikipedia.org/wiki/ScRGB)

* [Rec.2020](https://en.wikipedia.org/wiki/Rec._2020)

{% hint style="info" %}
This wiki is now **archived**. You should instead visit the [Linebender wiki](https://linebender.org/wiki/) at <https://linebender.org/wiki>
{% endhint %}

[piet#70]: https://github.com/linebender/piet/pull/70
[sRGB]: https://en.wikipedia.org/wiki/SRGB


Knitting for Javascripters by [Mariko Kosaka](http://twitter.com/kosamari)
---

[Slides](http://kosamari.com/presentation/jsconf-2015/)

> Once you've figured it out and done it once, it's not so scary

- knit stitch and purl stitch == binary language of stitching (K or P)
- [Ravelry](https://www.ravelry.com/account/login) <-- Github for knitters
- knitting patterns look like code

### Problem: scarf ended up being curved, not straight
- discovered **hyperbolic geometry** *AKA* **ruffles**

- Knitting machine (since 1890), popular in Japan in 70's & 80's
- Jacquard knit
- Electroknit --> a lot like dot matrix printing

### The Steps

1. Bitmap out of image: [GraphicsMagick](http://aheckmann.github.io/gm/)
2. RGB value --> Grayscale
3. Image dithering to look better
4. Ordered dithering (halftone screening)
5. Different types of ordered dithering --> select matrix
6. Make knitting pattern file (like hex file)

### `>>`: bitwise operator

> Bitwise Operator: It's Like Magic

- bit shifting:
- `<<` = left shift
- `|` = bitwise OR

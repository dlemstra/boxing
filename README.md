# Boxinglib     :afsdoc:

**boxinglib** is a cross-platform software library for **decoding** high-capacity 2D barcode images. The flexbible barcode format is fully customizeable in terms of **frame geometry**, number of **symbols per pixel** and **forward-error-correction** (FEC) method. This makes it a sutiable choice for storing large amounts of any kind of digital data on storage mediums such paper, photographic film or similar.

The 2D barcode format consists of a rectangular **border frame** and a **content area** inside the frame. The border has **corner marks** for detecting the image area and **synchronization marks** along the border for accurately tracking the content of the frame. The border has areas reserved for metadata in analog and digital format. The **digital metadata section** is at the bottom border and the **analog metadata section** is at the left and right borders. Metadata tags are fully customizeable and can be tags like a frame identification number or boxing format name. 

The content area can contain either **analog images** or **digital data**.
Digital data is encoded with FEC and written as a image where each pixel encodes two or more symbols. Analog data is written as monochrome images with 8bit resolution.

To decode the images the **reading device** needs to capture the 2D barcode from the storage medium and convert it to a digital image with 8bit resolution per pixel. The image should be read with ~2.7x oversampling compared to the original source resolution.

The library is released under GPLv3 licence for research and private use, for any kind of commercial licensing or use, please contact Piql AS.

<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#sec-1">1. Boxinglib&#xa0;&#xa0;&#xa0;<span class="tag"><span class="afsdoc">afsdoc</span></span></a></li>
<li><a href="#sec-2">2. Features&#xa0;&#xa0;&#xa0;<span class="tag"><span class="afsdoc">afsdoc</span></span></a></li>
<li><a href="#sec-3">3. Requirements&#xa0;&#xa0;&#xa0;<span class="tag"><span class="afsdoc">afsdoc</span></span></a></li>
<li><a href="#sec-4">4. Installation</a></li>
<li><a href="#sec-5">5. Sample Applications&#xa0;&#xa0;&#xa0;<span class="tag"><span class="afsdoc">afsdoc</span></span></a></li>
<li><a href="#sec-6">6. Contact</a></li>
</ul>
</div>
</div>

# Features     :afsdoc:

-   Flexible and user configurable 2D barcode format, including bit depth, geometry and forward error correction method.
-   Support for interleaved error correction where the data (and error correction codes) are spread across multiple barcodes.
-   Support for digital or analog payload.
-   Robust frame format with multiple features to aid tracking.
-   Frame has support for user configurable machine readable and human readable metadata.
-   Cross-platform: Tested on Windows, Linux and OS-X.
-   Stand alone: Minimal dependecies to other libraries or operation system functions.

# Requirements     :afsdoc:

C language compiler supporting C99 (ISO/IEC 9899:1999).

The following C99 header files are used:

    #include <alloca.h>
    #include <assert.h>
    #include <float.h>
    #include <inttypes.h>
    #include <limits.h>
    #include <malloc.h>
    #include <math.h>
    #include <stdarg.h>
    #include <stddef.h>
    #include <stdint.h>
    #include <stdio.h>
    #include <stdlib.h>
    #include <string.h>
    #include <time.h>

A design goal is to have as few dependencies as possible.

The following 3rd party libraries are included:
-   glib - LGPLv2
-   reedsolomon - GPLv3, see thirdparty/reedsolomon/gpl.txt
-   ldpc - see thirdparty/ldpc/COPYRIGHT
-   bch - GPLv2

For detailed copyright and licencing description, inspect source code under thirdparty/.

# Installation

    git clone https://github.com/piql/boxing
    cd boxing
    ./autogen.sh
    ./configure
    make

# Sample Applications     :afsdoc:

-   **tests/unboxingdata**: Unittests for the unboxing library.
-   **tests/unboxer**: Command line sample application for decoding 2D barcodes.
-   **tests/testdata**: Sample frames in RAW and analog image formats.

# Contact

**Piql AS**
Grønland 56
3045 Drammen
NORWAY

*office@piql.com*
*+47 905 33 432*
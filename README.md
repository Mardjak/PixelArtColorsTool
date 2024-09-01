# PixelArtColorsTool

Install python then from a command line interface run:

python ./palette_swap.py INPUT OUTPUT

```bash
usage: palette_swap.py [-h] [--palette PALETTE] [--downscale_width_resolution DOWNSCALE_WIDTH_RESOLUTION] [--colors COLORS [COLORS ...]] [--constrast CONSTRAST [CONSTRAST ...]]
                       [--saturation SATURATION [SATURATION ...]] [--dither DITHER]
                       input output

Downscale an image, quantize colors, swap palettes and resize back to original size.

positional arguments:
  input                 Path to the directory containing all pictures to process or to a single picture
  output                Path to the directory for the output pictures or to a single picture

options:
  -h, --help            show this help message and exit
  --palette PALETTE     Path to the palette image (1x, see https://lospec.com/palette-list)
  --downscale_width_resolution DOWNSCALE_WIDTH_RESOLUTION
                        Target width resolution for the downscale. Height will be calculated to keep the aspect ratio.
  --colors COLORS [COLORS ...]
                        Force quantization to this color count. If unspecified, colors will be limited to the palette size. If no palette have been specified, no quantization will be done.
  --constrast CONSTRAST [CONSTRAST ...]
                        Between 0 and infinity, change picture constrast before processing
  --saturation SATURATION [SATURATION ...]
                        Between 0 and infinity, change picture saturation before processing
  --dither DITHER       Apply dithering to the quantized image. 0 for no dithering, 1 for Floyd-Steinberg dithering, 2 for both
```

Input and output supports directories. If an directory is set as input then all pictures found in the directory will be processed. Note that if the input is a directory then the output must imperatively also be a directory.

Some arguments, namely colors, contrast, saturation and dither supports multiples values. So you can for example set --contrast 1.1 1.2 1.3. If any of the options are multiple, then all combinations of those settings will be generated in the output.

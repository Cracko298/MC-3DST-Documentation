## MC-3DST-Documentation
- Documentation for Minecraft 3DS's .3DST Skin Texture Format.
- Information provided in this Documentation can be used in Applications to Read/Write Data.

## Notice:
- This Guide only goes over ARGB Skins.
- ARGB Skins in *.3DST Format are ALWAYS have a fixed length of 0x4020 Bytes.

### Before Continuing...
- Make sure your .3DST Skins you want to edit follow the "Notice" section.

## Header Information:
```
- Header Size        = Bytes 0x00 -> 0x20
- Texture Name       = Bytes 0x00 -> 0x04
- Texture Mode       = Byte 0x05
- Texture Width      = Byte 0x0C
- Texture Height     = Byte 0x10
- Width Checksum     = Byte 0x14
- Height Checksum    = Byte 0x18
- Image Format       = ARGB
- MIP Value          = Byte 0x1C
```
## Indicators:
```
- Pixel With Color        = 0xFF (Followed by Bytes in a RGB Format)
- Pixel With No Color     = 0x00 (Followed by 0x00, 0x00, 0x00)

Pixels are Arranged Into Cubes, then into Blocks.
And are either full opaige or fully off (no in-between).

> Examples:                 A  R  G  B  - Values
- Pixel With Color        = FF 04 C4 F5
                            ^ Indicator (Alpha Value)

                            A  R  G  B  - Values
- Pixel With No Color     = 00 00 00 00
                            ^ Indicator (Alpha Value)
```
## Cubes/Blocks (Image Comprehension):
```
- Cubes              = A group of Pixels in a 2x2 grid (Every 0x10 Bytes).
- Blocks             = A collection of cubes in a 4x4 grid (Every 0xFF Bytes).

Blocks go from Left to Right (A total of 8 times).
```



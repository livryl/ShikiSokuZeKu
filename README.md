# Shiki Soku Ze Ku

English | [日本語](README_JP.md)

![Platform](https://img.shields.io/badge/Platform-Windows-blue)
![Python](https://img.shields.io/badge/Python-3.10+-green)
![ComfyUI](https://img.shields.io/badge/Backend-ComfyUI-orange)
![License](https://img.shields.io/badge/License-Free-lightgrey)

A unified multimedia generation frontend for ComfyUI.

Generate images, videos, voices and music from a single interface.

<img width="1492" height="939" alt="HVeDHrLacAAAvBf" src="https://github.com/user-attachments/assets/ee315a5b-4f30-433b-af5e-24e6ffd4646d" />

Please note that this app is primarily in Japanese.
If you wish to use it in another language, please enable your browser's built-in translation feature.

### Download (zip) → https://github.com/livryl/ShikiSokuZeKu/releases/tag/v1.0.0

Please use the zip file listed under **Assets** on the release page (not "Source code").

## Features

### Image Generation
- Text to Image (T2I)
- Image to Image (I2I)
- PNG Info import
- Model browser with thumbnails
- LoRA management
- Prompt autocomplete (Danbooru tags, data not included - see Notes)
- Optional prompt expansion / translation (Japanese to English)

### Video Generation
- MiniMax H3 support
- Reference image and audio guidance
- Multi-scene generation
- Automatic scene stitching
- Long-form video workflow

### Voice Generation
- Irodori-TTS integration
- Voice cloning
- Voice Design support
- Emoji-based emotion control

### Music Generation
- Stable Audio 3 integration
- Music and sound effect generation
- Optional prompt enhancement

## Requirements

- Windows
- ComfyUI
- Python 3.10+

Additional requirements (models and custom nodes) depend on which features you want to use.

## Installation

1. Start ComfyUI
2. Download the zip from the [Releases page](https://github.com/livryl/ShikiSokuZeKu/releases/tag/v1.0.2) and extract it
3. Run `start.bat`
4. Open the interface in your browser

Detailed setup instructions (in Japanese) are available in:

- [README_JP.md](README_JP.md)
- `README_setup.txt` (included in the zip)

## Supported Generators

| Type | Backend |
|--------|--------|
| Images | ComfyUI |
| Video | MiniMax H3 |
| Voice | Irodori-TTS |
| Music | Stable Audio 3 |

## Notes

- This project acts as a frontend for ComfyUI.
- Models are not included.
- Some workflows may require additional custom nodes.
- Tested mainly with RTX 3060 12GB.
- Image generation is mainly tested with Anima. Other model types (SDXL, Krea2, Flux2 Klein, Z-Image) are experimental.
- Tag autocomplete data is not included, because it is distributed externally.
  Download it from [here](https://civitai.com/models/2018479/danbooru-tag-complete-csv-tagcompleteand), then place `danbooru.csv` (required) and `danbooru-jp.csv` (Japanese translations, optional) in the `Data` folder.
  The files in the zip have different names, so they need to be renamed. See [README_JP.md](README_JP.md) for details.
  The app works without it; only the autocomplete will be unavailable.

## License

This project is distributed free of charge.

Please follow the licenses and usage terms of all third-party models, custom nodes, and datasets used with ComfyUI.

## Acknowledgements

Special thanks to the ComfyUI community and the developers of:

- ComfyUI
- MiniMax H3
- Stable Audio 3
- Irodori-TTS
- Various custom node contributors

## Author

2026 ATF (えーてぃーえふ) Livryl
https://x.com/ATFzwei

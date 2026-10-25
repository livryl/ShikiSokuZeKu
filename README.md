# Shiki Soku Ze Ku

![Platform](https://img.shields.io/badge/Platform-Windows-blue)
![Python](https://img.shields.io/badge/Python-3.10+-green)
![ComfyUI](https://img.shields.io/badge/Backend-ComfyUI-orange)
![License](https://img.shields.io/badge/License-Free-lightgrey)

A unified multimedia generation frontend for ComfyUI.

Generate images, videos, voices and music from a single interface.

<img width="1492" height="939" alt="HVeDHrLacAAAvBf" src="https://github.com/user-attachments/assets/ee315a5b-4f30-433b-af5e-24e6ffd4646d" />

## Features

### Image Generation
- Text to Image (T2I)
- Image to Image (I2I)
- PNG Info import
- Model browser with thumbnails
- LoRA management
- Prompt autocomplete (Danbooru tags)

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

Additional requirements depend on which features you want to use.

## Installation

1. Start ComfyUI
2. Download the latest release
3. Run `start.bat`
4. Open the interface in your browser

Detailed setup instructions are available in:

- `README_setup.txt`

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

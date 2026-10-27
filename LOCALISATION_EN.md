# English localization — Shiki Soku Ze Ku v1.01

This document is a community translation and may not always reflect the latest version of the project.
For the most up-to-date information, please refer to README.md.

### Download https://github.com/livryl/ShikiSokuZeKu/releases/tag/v1.01EN

This edition localizes the supplied Japanese source distribution into English. Original application credit: **2026 ATF Livryl**, <https://x.com/ATFzwei>.

## Scope

- English labels, buttons, help text, status messages, warnings and errors across the image, video, music and speech interfaces.
- English source comments and docstrings, including embedded JavaScript comments.
- English setup guide (`README.txt`) and all eight in-application Markdown guides.
- English display titles for 26 nodes in the two bundled API-format workflows.
- English prompt-expansion examples and matching localized JavaScript text checks for tab colors, completion sounds and restart messages.

The original calligraphic logo and application name are retained as branding. Optional Japanese tag search, Japanese quotation recognition and speech-model capabilities are preserved. Optional tag CSV datasets are not included in the supplied distribution.

## Compatibility and integration

The existing Windows `start.bat` launcher is included unchanged. Model filenames, node class names, workflow inputs and connections, API endpoints and Python identifiers are preserved. This is a localization of the existing application.

The archive contains no virtual environment, downloaded models, generated output or saved user preferences. It can be extracted into a separate folder for review. When integrating with an existing installation, note that some saved preferences use localized display text for image size presets, I2I size modes and video aspect ratios. Existing Japanese preference values may need to be migrated to the corresponding English labels. Back up preferences before replacing files in an existing installation.

The original project and model/custom-node license terms still apply. This localization does not introduce new license terms or claim to be an upstream release. Performance figures in the guides are the original author's reports, not new measurements. The English interface does not imply that the Japanese-oriented Irodori-TTS model supports English speech.

## Validation performed

- All four translated Python modules pass syntax compilation without importing or running the application.
- Python syntax-tree comparison confirms the same non-text program structure and formatted expressions.
- Tag autocomplete and the extracted embedded JavaScript constants in the main module pass `node --check`.
- Both JSON workflows parse successfully. Their executable node data is identical after excluding display metadata.
- Every repeated Japanese string literal received a consistent English translation.
- No Japanese prose remains in the text files. The original image logo is intentionally preserved.
- The launcher and logo are byte-identical to the originals; the original source folder remains unchanged.

The complete application has **not been launched or visually tested on Windows** during this localization. A Windows review with the required ComfyUI nodes and models remains necessary before treating this as a tested release.

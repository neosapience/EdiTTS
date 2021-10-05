# EdiTTS: Score-based Editing for Controllable Text-to-Speech

This repository contains code for a user editable text-to-speech system, namely EdiTTS.

## Setup

- Create a Python virtual environment (`venv` or `conda`) and install package requirements as specified in [`requirements.txt`](requirements.txt).

- For more information, you may refer to [the official repository of Grad-TTS](https://github.com/huawei-noah/Speech-Backbones/tree/main/Grad-TTS).

## Pitch shifting

Mark the part to be edited with ||.

> In | the face of impediments confessedly discouraging |

We provide some examplary sentences in resources/filelists/edit_pitch_example.txt

To synthesize pitch-edited speech, run

```shell
CUDA_VISIBLE_DEVICES=0 python edit_pitch.py -f resources/filelists/edit_pitch_example.txt -c checkpts/grad-tts-old.pt -t 1000 -s out/pitch/wavs
```

## Content replacement

Prepare two sentences. Concatenate them with # and mark the parts to be replaced with ||.

> Three others subsequently | identified | Oswald from a photograph. #Three others subsequently | recognized | Oswald from a photograph.

We provide some examplary sentences in resources/filelists/edit_content_example.txt

To synthesize content-replaced speech, run

```shell
CUDA_VISIBLE_DEVICES=0 python edit_content.py -f resources/filelists/edit_content_example.txt -c checkpts/grad-tts-old.pt -t 1000 -s out/content/wavs
```

## Demo page

Audio samples generated by EdiTTS can be found [here](https://editts.github.io/)

## Checkpoints
This repository uses the following checkpoints.

- Grad-TTS (old ver.): [click here](https://drive.google.com/drive/folders/1grsfccJbmEuSBGQExQKr3cVxNV0xEOZ7)
- HiFi-GAN (LJ_FT_T2_V1 ver.): [click here](https://drive.google.com/drive/folders/1-eEYTB5Av9jNql0WGBlRoi-WH2J7bp5Y)

## References
- [Grad-TTS](https://github.com/huawei-noah/Speech-Backbones/tree/main/Grad-TTS)
- [HiFi-GAN](https://github.com/jik876/hifi-gan)
- [SDEdit](https://github.com/ermongroup/SDEdit)

# 🎙️ AI Voice Changer

**English** | [Русский](README.ru.md)

Neural-network-based voice changer for real-time use and for audio recordings. Pick a model, hit Start, and speak in a different voice.

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey)
![PRs](https://img.shields.io/badge/PRs-welcome-brightgreen)

## ✨ Features

- 🤖 **AI voice conversion**: neural models keep your intonation and emotion while changing only the timbre
- ⚡ **Real-time mode**: works with your microphone, great for games, streaming, and calls
- 🎞️ **File processing**: convert recordings in WAV, MP3, and FLAC formats
- 🎚️ **Fine-tuning**: pitch shift, effect strength, noise suppression
- 📦 **Custom models**: load any compatible voice model
- 🖥️ **GPU and CPU support**: accelerated on NVIDIA GPUs, slower on CPU
- 🔌 **Virtual microphone**: plug the output into Discord, OBS, Telegram, and other apps

## 🧠 How It Works

1. Audio from the microphone (or a file) is split into short chunks.
2. A neural network extracts the speech content and pitch.
3. The target voice model applies a new timbre.
4. The result is played through your headphones or sent to a virtual microphone.

## 📦 Requirements

| Component | Minimum | Recommended |
|---|---|---|
| OS | Windows 10 / Linux / macOS | Windows 11 / Ubuntu 22.04 |
| Python | 3.10 | 3.10–3.11 |
| GPU | Not required | NVIDIA with 4+ GB VRAM |
| RAM | 8 GB | 16 GB |

## 🚀 Installation

```bash
git clone https://github.com/username/ai-voice-changer.git
cd ai-voice-changer

python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

pip install -r requirements.txt
```

For GPU acceleration on NVIDIA cards, install the CUDA build of PyTorch following the [official guide](https://pytorch.org/get-started/locally/).

## 🛠 Quick Start

### 1. Download a model

Put the model files (`.pth` and, if available, `.index`) into the `models/` folder:

```
models/
└── my_voice/
    ├── my_voice.pth
    └── my_voice.index
```

### 2. Run the app

```bash
python main.py
```

### 3. Configure and press Start

1. Select your microphone and output device
2. Choose a voice model
3. Adjust pitch and effect strength
4. Click **Start**

### Process a file from the command line

```bash
python convert.py --input input.wav --output output.wav --model models/my_voice/my_voice.pth --pitch 0
```

## ⚙️ Main Parameters

| Parameter | Description | Default |
|---|---|---|
| `--model` | Path to the model file | — |
| `--pitch` | Pitch shift in semitones (-12 to 12) | `0` |
| `--index-rate` | How strongly to apply the model's timbre (0–1) | `0.75` |
| `--device` | `cuda` or `cpu` | `auto` |
| `--chunk-size` | Chunk size in seconds, affects latency | `0.25` |

## 💡 Tips

- **Male → female voice**: raise the pitch by +8 to +12 semitones
- **Female → male voice**: lower the pitch by -8 to -12 semitones
- **High latency**: reduce the chunk size or use a GPU
- **Hissing or background noise**: enable noise suppression and use a good microphone

## ❓ FAQ

**Do I need a GPU?**
No, but real-time latency is noticeably higher on CPU.

**Where can I get voice models?**
Train your own on recordings of a voice you have the right to use, or use ready-made models with an open license.

**How do I use it in Discord or OBS?**
Install a virtual audio cable (for example, VB-Cable), then select it as the output in this app and as the microphone in Discord or OBS.

## ⚠️ Responsible Use

Voice-changing technology can be misused. By using this project, you agree to:

- not impersonate another person to deceive, defraud, or defame
- not use someone's voice without the owner's permission
- follow the laws of your country and the rules of any platform where you publish the results

The author is not responsible for any misuse of this software.

## 🤝 Contributing

Contributions are welcome:

1. Fork the repository
2. Create a branch: `git checkout -b feature/my-feature`
3. Commit your changes: `git commit -m "Add my feature"`
4. Push the branch: `git push origin feature/my-feature`
5. Open a Pull Request

Found a bug or have an idea? Open an [issue](../../issues).

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgements

- The authors of the open-source models and libraries this project is built on
- Everyone who tests the app and sends feedback

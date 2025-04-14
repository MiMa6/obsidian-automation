# 🎙️ Voice-to-Text Obsidian Helper

Turn your voice into Obsidian notes! This Python-based tool makes it super easy to record your thoughts and automatically transcribe them into your Obsidian vault.

## ✨ Features

- 🎤 Smart voice 2 memos
- ⚡ Quick and easy command-line interface
- 📝 Automatic note creation in your Obsidian vault
- 🎯 Intelligent file organization for both audio and transcripts
- 🤖 AI-powered transcription using OpenAI's latest Speech to Text models

## 🚀 Getting Started

### 📋 Prerequisites

- Python 3.9 or higher
- An OpenAI API key
- Obsidian vault set up on your system
- A working microphone

### 🛠️ Installation

1. Clone this repository:

```bash
git clone https://github.com/MiMa6/speech-2-obsidian.git
cd speech-2-obsidian
```

2. Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate  # On macOS/Linux
```

3. Install required packages:

```bash
pip install -r requirements.txt
```

4. Create a `.env` file in the project root:

```env
OPENAI_API_KEY=your-api-key-here
OBSIDIAN_VAULT_PATH=/path/to/your/vault
USER_PATH==/Users/you
```

5. Config your microphone

Edit `src/config.py` and update the `AudioConfig` settings:

```Python
MICROPHONE_NAME = "Your Microphone Name"  # For example "External USB Microphone"
```

## 🎮 Usage

1. Run the script:

```bash
python speech_to_text.py
```

2. Choose your action:

   - Press `1` to start recording
   - Press `2` to quit

3. When recording:
   - Start speaking naturally
   - The recording will automatically stop after 2 seconds of silence
   - Your audio will be transcribed and saved to your Obsidian vault

## 📁 Project Structure

```
.
├── src/
│   ├── audio_recorder.py    # Handles voice recording
│   ├── transcriber.py       # Manages OpenAI transcription
│   ├── file_manager.py      # Handles file operations
│   ├── config.py           # Centralized configuration
│   └── __init__.py
├── logs/                   # Application logs
├── speech_to_text.py       # Main script
├── requirements.txt
└── .env
```

## 🎯 How It Works

1. 🎤 **Recording**: Uses your configured microphone to capture audio
2. 🤖 **Processing**: Automatically detects silence to stop recording
3. ✨ **Transcription**: Sends audio to OpenAI's Whisper model for accurate transcription
4. 📝 **Organization**:
   - Transcripts go to `[vault]/Audios/SpeechToText/`
   - Original recordings move to `[vault]/Audios/Translated/`

## 🔧 Configuration

Configuration is managed using Pydantic for robust validation and type safety:

- `Settings`: Environment variables and app settings (in `src/settings.py`)
- `AudioConfig`: Recording settings (silence threshold, duration, etc.)
- `FileConfig`: File naming and directory structures
- `LogConfig`: Logging settings and rotation

All configuration classes use Pydantic's validation to ensure type safety and proper value constraints.

### 📝 Logging

Logs are automatically saved in the `logs/` directory

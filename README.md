# 🎵 AI Music Generator

A sophisticated GenAI music synthesis and demo application that leverages deep learning technologies to create unique musical compositions from user-uploaded melodies.

## 🚀 Features

- **Deep Learning Music Generation**: Powered by state-of-the-art Transformer and LSTM neural networks
- **Intelligent Audio Processing**: Advanced signal processing for high-quality music synthesis
- **Creative Coding Framework**: Flexible and extensible architecture for musical experimentation
- **User-Friendly API**: RESTful API for seamless melody upload and music generation
- **Real-time Generation**: Fast inference for interactive music creation
- **Multiple Output Formats**: Support for WAV, MP3, and MIDI exports

## 🏗️ Architecture

### Core Components

- **Neural Networks**: 
  - Transformer-based sequence-to-sequence models for melody continuation
  - LSTM networks for temporal music pattern learning
  - Variational Autoencoders (VAE) for creative variation generation

- **Audio Processing Pipeline**:
  - FFT/STFT for frequency domain analysis
  - Mel-spectrogram generation and processing
  - Real-time audio synthesis and post-processing

- **API Layer**:
  - FastAPI-based REST endpoints
  - WebSocket support for real-time generation
  - File upload handling for various audio formats

## 🛠️ Technology Stack

- **Deep Learning**: PyTorch, Transformers (Hugging Face), TensorFlow
- **Audio Processing**: librosa, soundfile, pyaudio, pretty_midi
- **Web Framework**: FastAPI, WebSocket, Pydantic
- **Creative Coding**: NumPy, SciPy, matplotlib for visualization
- **Database**: SQLite/PostgreSQL for metadata storage
- **Frontend**: React.js with Web Audio API integration

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/Jaydot33/ai-music-generator.git
cd ai-music-generator

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Download pre-trained models
python scripts/download_models.py
```

## 🚀 Quick Start

### Running the API Server

```bash
# Start the FastAPI server
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

### Basic Usage

```python
import requests
import json

# Upload a melody file
with open('input_melody.wav', 'rb') as f:
    response = requests.post(
        'http://localhost:8000/api/upload_melody',
        files={'melody': f},
        data={'style': 'classical', 'length': 30}
    )

# Generate new music
result = response.json()
generated_url = result['generated_music_url']
```

### Web Interface

```bash
# Start the web interface
cd frontend
npm install
npm start
```

## 🎛️ API Endpoints

### Music Generation

- `POST /api/upload_melody` - Upload a melody file for processing
- `POST /api/generate_music` - Generate music from uploaded melody
- `GET /api/download/{file_id}` - Download generated music file
- `WebSocket /ws/generate` - Real-time music generation

### Model Management

- `GET /api/models` - List available models
- `POST /api/models/load` - Load specific model
- `GET /api/models/status` - Check model status

## 🧠 Model Details

### Transformer Architecture
- **Model Size**: 124M parameters
- **Training Data**: 10,000+ hours of diverse musical genres
- **Context Length**: Up to 1024 tokens (≈32 seconds of music)
- **Attention Heads**: 12 multi-head attention layers

### LSTM Network
- **Hidden Size**: 512 units
- **Layers**: 3 bidirectional LSTM layers
- **Sequence Length**: Variable (1-64 seconds)
- **Output**: Continuous audio features

## 🎨 Creative Features

- **Style Transfer**: Transform melodies between different musical genres
- **Harmonization**: Automatically generate chord progressions
- **Rhythm Generation**: Create drum patterns and rhythm sections
- **Melody Variation**: Generate multiple variations of input melodies
- **Real-time Jamming**: Interactive music creation with AI accompaniment

## 📊 Performance

- **Generation Speed**: ~2-5x real-time on GPU
- **Memory Usage**: ~4GB VRAM for inference
- **Supported Formats**: WAV (16/24/32-bit), MP3, FLAC, MIDI
- **Sample Rates**: 22kHz, 44.1kHz, 48kHz

## 🧪 Examples

Check out the `/examples` directory for:
- Sample input melodies
- Generated outputs
- Jupyter notebooks with tutorials
- Creative coding experiments

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- OpenAI for inspiration in generative AI
- Hugging Face for transformer implementations
- The librosa team for audio processing tools
- The PyTorch community for deep learning framework

## 📞 Contact

For questions, issues, or collaboration opportunities:
- Create an issue in this repository
- Email: [your-email@example.com]
- Twitter: [@your_twitter_handle]

---

*Built with ❤️ for the creative coding and AI music generation community*

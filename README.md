# Hermes v0.1.0: Lightning-Fast Video Transcription 🎥➡️📝

Hermes, the messenger of the gods, now brings you ultra-fast video transcription powered by cutting-edge AI! This Python library and CLI tool harnesses the speed of Groq and the flexibility of multiple providers to convert your videos into text with unprecedented efficiency.

## 🚀 Features

- **Blazing Fast**: Transcribe a 393-second video in just 1 second with Groq's distil-whisper model!
- **Multi-Provider Support**: Choose from Groq (default), MLX Whisper, or OpenAI for transcription
- **YouTube Support**: Easily transcribe YouTube videos by simply passing the URL
- **Flexible**: Support for various models and output formats
- **Python Library & CLI**: Use Hermes in your Python projects or directly from the command line
- **LLM Processing**: Process the transcription with an LLM for further analysis

## 📦 Installation

Install Hermes directly from GitHub using pip:

```
pip install git+https://github.com/unclecode/hermes.git
```

## 🛠️ Usage

### Python Library

1. Basic transcription:

```
from hermes import transcribe

result = transcribe('path/to/your/video.mp4', provider='groq')
print(result['transcription'])
```

2. Transcribe a YouTube video:

```
result = transcribe('https://www.youtube.com/watch?v=v=PNulbFECY-I', provider='groq')
print(result['transcription'])
```

3. Use a different model:

```
result = transcribe('path/to/your/video.mp4', provider='groq', model='whisper-large-v3')
print(result['transcription'])
```

4. Get JSON output:

```
result = transcribe('path/to/your/video.mp4', provider='groq', response_format='json')
print(result['transcription'])
```

5. Process with LLM:

```
result = transcribe('path/to/your/video.mp4', provider='groq', llm_prompt="Summarize this transcription in 3 bullet points")
print(result['llm_processed'])
```

### Command Line Interface

1. Basic usage:

```
hermes path/to/your/video.mp4 -p groq
```

2. Transcribe a YouTube video:

```
hermes https://www.youtube.com/watch?v=v=PNulbFECY-I -p groq
```

3. Use a different model:

```
hermes path/to/your/video.mp4 -p groq -m whisper-large-v3
```

4. Get JSON output:

```
hermes path/to/your/video.mp4 -p groq --response_format json
```

5. Process with LLM:

```
hermes path/to/your/video.mp4 -p groq --llm_prompt "Summarize this transcription in 3 bullet points"
```

## 🏎️ Performance Comparison

![Hermes Benchmark Results](https://raw.githubusercontent.com/unclecode/hermes/main/assets/whisper-benchmark.png)

For a 393-second video:

| Provider | Model | Time (seconds) |
|----------|-------|----------------|
| Groq | distil-whisper-large-v3-en | 1 |
| Groq | whisper-large-v3 | 2 |
| MLX Whisper | distil-whisper-large-v3 | 11 |
| OpenAI | whisper-1 | 21 |

## 📊 Running Benchmarks

Test Hermes performance with different providers and models:

```
python -m hermes.benchmark path/to/your/video.mp4
```

or

```
python -m hermes.benchmark https://www.youtube.com/watch?v=v=PNulbFECY-I
```

This will generate a performance report for all supported providers and models.

## 🌟 Why Hermes?

- **Unmatched Speed**: Groq's distil-whisper model transcribes 393 seconds of audio in just 1 second!
- **Flexibility**: Choose the provider that best suits your needs
- **Easy Integration**: Use as a Python library or CLI tool
- **YouTube Support**: Transcribe YouTube videos without manual downloads
- **Local Option**: Use MLX Whisper for fast, local transcription on Mac or MPS systems
- **Cloud Power**: Leverage Groq's LPU for the fastest cloud-based transcription

## 🙏 Acknowledgements

Huge shoutout to the @GroqInc team for their incredible distil-whisper model, making ultra-fast transcription a reality!

## 🎉 Final Thoughts

We're living in amazing times! Whether you need the lightning speed of Groq, the convenience of OpenAI, or the local power of MLX Whisper, Hermes has got you covered. Happy transcribing!
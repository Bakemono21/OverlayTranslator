# LiveCaptions Translator (Overlay Translator)

LiveCaptions Translator is a powerful, real-time desktop application designed to translate system audio and speech into your chosen language. By leveraging the built-in Windows Live Captions feature, it provides a seamless, low-latency translation experience displayed in a highly customizable overlay window.

![Version](https://img.shields.io/badge/version-1.2.0.0-blue)
![Platform](https://img.shields.io/badge/platform-Windows%2011-brightgreen)

## ✨ Features

- **Real-time Translation:** Translates audio captured by Windows Live Captions instantly.
- **Multiple API Support:** Integration with a wide range of translation services:
  - **LLM-based:** OpenAI, Ollama (Local), LMStudio, OpenRouter.
  - **Traditional:** Google Translate (Web/API), DeepL, Youdao, Baidu, LibreTranslate.
  - **Custom:** MTranServer.
- **Context-Aware Translation:** Uses LLMs to maintain context across sentences, significantly improving translation accuracy for ongoing conversations or media.
- **Customizable Overlay:**
  - Adjust font size, colors, bolding, and stroke.
  - Control background opacity.
  - "Click-through" mode to keep the translator visible without interfering with your workspace.
  - Toggle between showing original captions, translations, or both.
- **History Logging:** Automatically saves translations to a local SQLite database for later review.
- **Latency Tracking:** Optional display of API response times to help you choose the fastest provider.
- **Privacy Focused:** Support for local LLMs (Ollama/LMStudio) ensures your data stays on your machine.

## 📋 Prerequisites

- **Operating System:** Windows 11 (Version 22H2 or later).
  - _Note:_ Windows 11 24H2 users must manage the "Source Language" directly within the Windows Live Captions settings.
- **Windows Live Captions:** Must be installed and configured on your system.

## 🚀 Getting Started

1. **Initial Setup:**
   - Launch the application. On the first run, a "Getting Started" guide will appear.
   - Ensure Windows Live Captions is open and set to **"Position > Overlaid on screen"**.
   - Download the necessary language packs through Windows settings as prompted by Live Captions.

2. **Configuration:**
   - Navigate to the **Setting** page.
   - Select your preferred **Translate API**.
   - Enter your API keys or local endpoint URLs (e.g., `http://localhost:11434` for Ollama).
   - Set your **Target Language** using BCP 47 tags (e.g., `en`, `zh-CN`, `ja`).

3. **Usage:**
   - Click **"Show"** in the settings to ensure Live Captions is active, then **"Hide"** to let the Overlay Translator take over the UI.
   - Switch to the **Caption** page to see the live feed or use the **Overlay Window** for a minimalist view while watching videos or attending meetings.

## 🛠 Customization

### API Interval

Determines how frequently the API is called. A smaller interval provides faster updates but consumes more API tokens.

### Contexts vs. Display Sentences

- **Contexts:** How many previous sentences are sent to the LLM to improve the current translation.
- **Display Sentences:** How many previous translation "cards" are visible in the overlay at once.

### Custom Prompts

Advanced users can modify the translation prompt in `setting.json` to change the "persona" of the translator (e.g., making it more formal, or specialized for technical fields).

## 📂 Project Structure

- `src/pages/`: Contains the UI logic for Settings, History, and Info pages.
- `src/windows/`: Manages the Main window and the transparent Overlay window.
- `src/apis/`: Implementation of various translation API connectors.
- `src/models/`: Data structures for settings and captions.
- `setting.json`: Primary configuration file for API keys and UI preferences.

## 🤝 Contributing

Contributions are welcome! Whether it's reporting a bug, suggesting a feature, or submitting a pull request:

1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/AmazingFeature`).
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4. Push to the branch (`git push origin feature/AmazingFeature`).
5. Open a Pull Request.

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

## 🌟 Support

If this project helps you, please consider giving it a star on GitHub!

---

**Maintainer:** @Bakemono021
**Wiki:** Documentation

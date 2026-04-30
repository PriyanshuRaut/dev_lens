<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f0c29,50:302b63,100:24243e&height=200&section=header&text=DevLens&fontSize=80&fontColor=ffffff&fontAlignY=38&desc=A%20Lens%20to%20See%20Through%20Errors&descAlignY=58&descSize=20&descColor=a78bfa&animation=fadeIn" width="100%" />
</p>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=22&pause=1000&color=A78BFA&center=true&vCenter=true&width=600&lines=AI-powered+debugging+assistant+%F0%9F%A4%96;Built+with+Flutter+%F0%9F%92%99;Powered+by+Groq+%26+Google+Gemini+%E2%9A%A1;No+backend+required+%F0%9F%9A%80;Paste+error+%E2%86%92+Get+fix.+That+simple." alt="Typing SVG" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white" />
  <img src="https://img.shields.io/badge/Dart-0175C2?style=for-the-badge&logo=dart&logoColor=white" />
  <img src="https://img.shields.io/badge/Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white" />
  <img src="https://img.shields.io/badge/Platform-Android%20%7C%20iOS%20%7C%20Web-9C27B0?style=for-the-badge" />
  <img src="https://img.shields.io/github/stars/PriyanshuRaut/dev_lens?style=for-the-badge&color=a78bfa" />
  <img src="https://img.shields.io/github/forks/PriyanshuRaut/dev_lens?style=for-the-badge&color=818cf8" />
</p>

<p align="center">
  <a href="#-what-is-devlens">About</a> &nbsp;·&nbsp;
  <a href="#-features">Features</a> &nbsp;·&nbsp;
  <a href="#-getting-started">Getting Started</a> &nbsp;·&nbsp;
  <a href="#-architecture">Architecture</a> &nbsp;·&nbsp;
  <a href="#-roadmap">Roadmap</a> &nbsp;·&nbsp;
  <a href="#-contributing">Contributing</a>
</p>

---

## 🔭 What is DevLens?

> **Debugging shouldn't feel like decoding ancient runes.**

**DevLens** is a Flutter-based AI debugging assistant that transforms cryptic errors into clear, actionable insights — in seconds. It connects directly to Groq and Google Gemini APIs, so there's **zero backend**, **zero setup friction**.

<table>
<tr>
<td><b>📥 It accepts</b></td>
<td><b>📤 It returns</b></td>
</tr>
<tr>
<td>

- Code snippets & syntax errors
- API responses (JSON or raw)
- Logs & stack traces
- Raw JSON data
- WebSocket messages

</td>
<td>

- Plain-English explanation
- Root cause, pinpointed
- Suggested fix or corrected code
- Highlighted problem areas

</td>
</tr>
</table>

---

## ✨ Features

<details>
<summary><b>🧠 AI Debug Assistant</b></summary>
<br/>
Paste any error or code snippet. DevLens identifies the problematic line, explains the bug in plain English, and returns corrected code.

> **Example:** `if (x = 5)` → explains assignment vs. comparison and shows the fix.
</details>

<details>
<summary><b>🌐 API Error Debugger</b></summary>
<br/>
Analyze HTTP responses. Detects missing fields, unexpected structure, and decodes what that status code actually means.
</details>

<details>
<summary><b>📜 Log Analyzer</b></summary>
<br/>
Paste raw logs or stack traces. Extracts key exceptions, filters noise, and surfaces the most likely root cause.
</details>

<details>
<summary><b>🧾 JSON Formatter & Analyzer</b></summary>
<br/>
Cleans and formats messy JSON. AI explains the schema and flags anomalies automatically.
</details>

<details>
<summary><b>🔌 WebSocket Inspector</b></summary>
<br/>
Connect to any WebSocket URL, view incoming messages in real time, and send test payloads — all from within the app.
</details>

<details>
<summary><b>🎯 Smart Prompt Templates</b></summary>
<br/>
One-click structured actions — no need to write prompts manually:

- *"Explain this code error"*
- *"Analyze this API response"*
- *"Debug this JSON"*
- *"Inspect WebSocket messages"*
</details>

---

## 🛠 Tech Stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=flutter,dart,androidstudio,vscode,github&theme=dark" />
</p>

| Layer | Technology |
|---|---|
| 📱 Frontend | Flutter (Dart) |
| 🤖 AI | Groq API · Google Gemini API |
| 🌐 HTTP | `http` package |
| 🔌 WebSocket | `web_socket_channel` |
| 🗃 State | `provider` / `riverpod` |
| 🔗 Links | `url_launcher` |

---

## 📦 Getting Started

### Prerequisites

- [Flutter SDK](https://docs.flutter.dev/get-started/install) v3.0+
- A free API key from [Groq](https://console.groq.com/) or [Google Gemini](https://makersuite.google.com/)
- Git installed on your machine

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/PriyanshuRaut/dev_lens.git

# 2. Navigate into the project
cd dev_lens

# 3. Install Flutter dependencies
flutter pub get

# 4. Add your API key in the AI manager / config file
#    Replace 'YOUR_API_KEY' with your actual Groq or Gemini key

# 5. Run the app
flutter run                   # Android / iOS
flutter run -d chrome         # Web
flutter run -d <device_id>    # Specific device
```

> 💡 Use `flutter devices` to list all connected devices.

---

## 🏗 Architecture

```
dev_lens/
├── lib/
│   ├── screens/
│   │   ├── ai_debug_screen.dart        ← Code & error analysis
│   │   ├── api_debug_screen.dart       ← API response inspection
│   │   ├── log_analyzer_screen.dart    ← Log & stack trace parsing
│   │   ├── json_screen.dart            ← JSON formatting & analysis
│   │   └── websocket_screen.dart       ← Real-time WebSocket inspector
│   ├── services/
│   │   └── ai_manager.dart             ← Shared AI API handler
│   └── main.dart
```

```
User Input  ──▶  Format Prompt  ──▶  AI API (Groq / Gemini)  ──▶  Display Response
```

Every module feeds into the same `AI Manager` — keeping the codebase clean, DRY, and easy to extend.

---

## 🗺 Roadmap

| Status | Feature |
|--------|---------|
| ✅ | API key setup (Groq / Gemini) |
| ✅ | AI Debug Screen |
| ✅ | JSON Formatter |
| ✅ | API Debugger |
| ✅ | WebSocket Client |
| ✅ | Log Analyzer |
| 🔜 | Dark / Light theme toggle |
| 🔜 | Export results as Markdown / PDF |
| 🔜 | Debug session history |
| 🔜 | Support for more AI providers |

---

## 🤝 Contributing

Contributions are always welcome! Check out the open [`good first issue`](https://github.com/PriyanshuRaut/dev_lens/issues?q=label%3A%22good+first+issue%22) tags if you're just getting started.

1. **Fork** the repository
2. **Create** your branch: `git checkout -b feat/your-feature`
3. **Commit** your changes: `git commit -m "feat: describe your change"`
4. **Push** to your branch: `git push origin feat/your-feature`
5. **Open a Pull Request** 🎉

---

## 👥 Contributors

<p align="center">
  <a href="https://github.com/PriyanshuRaut">
    <img src="https://github.com/PriyanshuRaut.png" width="50" style="border-radius:50%;margin:5px" title="PriyanshuRaut"/>
  </a>
  <a href="https://github.com/tapabrata1701">
    <img src="https://github.com/tapabrata1701.png" width="50" style="border-radius:50%;margin:5px" title="tapabrata1701"/>
  </a>
  <a href="https://github.com/priyanshuraut1009-debug">
    <img src="https://github.com/priyanshuraut1009-debug.png" width="50" style="border-radius:50%;margin:5px" title="priyanshuraut1009-debug"/>
  </a>
</p>

---

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:24243e,50:302b63,100:0f0c29&height=120&section=footer&animation=fadeIn" width="100%" />
</p>

<p align="center">
  Made with ❤️ and Flutter &nbsp;·&nbsp; <b>Happy Coding!</b>
</p>
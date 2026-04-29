# 🔍 DevLens — A Lens to See Through Errors

<p align="center">
  <img src="https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white" />
  <img src="https://img.shields.io/badge/Dart-%230175C2.svg?style=for-the-badge&logo=dart&logoColor=white" />
  <img src="https://img.shields.io/badge/AI-Gemini%20%7C%20Groq-blueviolet?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Open%20Source-%E2%9D%A4-red?style=for-the-badge" />
  <img src="https://img.shields.io/badge/PRs-Welcome-brightgreen?style=for-the-badge" />
</p>

<p align="center">
  <strong>Transforming developer chaos into actionable clarity.</strong><br/>
  An AI-powered debugging toolkit that turns cryptic logs, stack traces, and broken APIs<br/>
  into human-readable solutions — right inside Flutter.
</p>

---

## 🚀 Overview

**DevLens** is a Flutter-based AI debugging assistant that helps developers quickly understand and resolve errors across multiple domains.

**It accepts:**
- Code snippets & syntax errors
- API responses (JSON or raw text)
- Logs & stack traces
- WebSocket messages

**It returns:**
- A human-readable explanation of the issue
- The root cause, pinpointed
- Suggested fixes or corrected code

> ⚡ **No backend required.** All AI analysis is powered via external APIs — [Groq](https://console.groq.com/) and [Google Gemini](https://aistudio.google.com/).

---

## ✨ Key Features (MVP)

### 🧠 AI Debug Assistant
Paste any code or error message and get back an explanation of what went wrong, which line is problematic, and a suggested fix.

> **Example:** `if (x = 5)` → DevLens explains the assignment vs. comparison mistake and shows the corrected version.

### 🌐 API Error Debugger
Analyze raw API responses to detect missing fields, incorrect structure, and what a given status code actually means.

### 📜 Log Analyzer
Paste logs or stack traces to instantly extract key errors, exceptions, and the most likely root cause.

### 🧾 JSON Formatter & Analyzer
Formats raw JSON into a readable structure and uses AI to explain the schema and flag anomalies.

### 🔌 WebSocket Inspector
Connect to any WebSocket URL, view incoming messages in real time, and send test payloads. Built using [`web_socket_channel`](https://pub.dev/packages/web_socket_channel).

### 🎯 Smart Prompt Templates
Structured one-tap actions instead of free-form chat:
- *"Explain this code error"*
- *"Analyze this API response"*
- *"Debug this JSON"*
- *"Inspect WebSocket messages"*

---

## 🛠️ Tech Stack

| Layer | Technology |
| :--- | :--- |
| 📱 Frontend | Flutter (Dart) |
| 🤖 AI | Groq API, Google Gemini API |
| 🌐 Networking | `http`, `web_socket_channel` |
| 📦 State | `provider` / `riverpod` |
| 🔗 Utilities | `url_launcher` |

---

## 🏗️ Architecture & Core Flow

DevLens is organized into focused, modular screens — each backed by a shared **AI Manager**:

```
┌─────────────────────────────────────────┐
│              User Input                 │
│  (Code / API Response / Log / JSON)     │
└──────────────────┬──────────────────────┘
                   │
                   ▼
        Structured Prompt Template
                   │
                   ▼
         AI Manager (HTTP Client)
                   │
          ┌────────┴────────┐
          ▼                 ▼
     Groq API         Gemini API
          │                 │
          └────────┬────────┘
                   ▼
         Parsed AI Response
                   │
                   ▼
       Rendered UI with Highlights
```

**Modules:**

- **AI Debug Screen** → Code & syntax error analysis
- **API Debug Screen** → API response inspection
- **Log Analyzer Screen** → Log & stack trace parsing
- **JSON Screen** → Formatting & schema analysis
- **WebSocket Screen** → Real-time message inspection

---

## 🧪 Code Snapshot — AI Bridge

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

Future<String> analyzeText(String prompt) async {
  const apiUrl = 'https://api.groq.com/openai/v1/chat/completions';
  const apiKey = 'YOUR_GROQ_API_KEY';

  final response = await http.post(
    Uri.parse(apiUrl),
    headers: {
      'Authorization': 'Bearer $apiKey',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({
      'model': 'llama3-8b-8192',
      'messages': [
        {'role': 'user', 'content': prompt},
      ],
    }),
  );

  if (response.statusCode == 200) {
    final data = jsonDecode(response.body);
    return data['choices'][0]['message']['content'] as String;
  } else {
    throw Exception('Groq API error: ${response.statusCode}');
  }
}
```

---

## 🚀 Getting Started

### Prerequisites
- **Flutter SDK** `^3.10.0`
- API keys from [Groq Cloud](https://console.groq.com/) or [Google AI Studio](https://aistudio.google.com/)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/PriyanshuRaut/dev_lens.git
cd dev_lens

# 2. Install dependencies
flutter pub get

# 3. Add your API keys
#    Open lib/config/api_config.dart and fill in your keys

# 4. Run the app
flutter run
```

> ⚠️ **Never commit your API keys.** Add your config file to `.gitignore`.

---

## 🗺️ MVP Roadmap

| Status | Milestone |
| :---: | :--- |
| ✅ | Repository setup & initial commit |
| ⬜ | API Key Management UI |
| ⬜ | AI Debug Screen |
| ⬜ | JSON Formatter & Analyzer |
| ⬜ | API Debugger |
| ⬜ | WebSocket Client |
| ⬜ | Log Analyzer |
| ⬜ | Multi-model toggle (Gemini ↔ Groq) |
| ⬜ | Dark Mode & custom themes |

---

## 🤝 Contributing

Contributions are welcome — bug fixes, new features, docs improvements, all of it.

1. Fork the repository
2. Create your branch: `git checkout -b feat/your-feature-name`
3. Commit your changes: `git commit -m 'feat: describe your change'`
4. Push to your branch: `git push origin feat/your-feature-name`
5. Open a Pull Request

---

## 👥 Contributors

<a href="https://github.com/PriyanshuRaut"><img src="https://github.com/PriyanshuRaut.png" width="40" style="border-radius:50%" /></a>
<a href="https://github.com/tapabrata1701"><img src="https://github.com/tapabrata1701.png" width="40" style="border-radius:50%" /></a>
<a href="https://github.com/priyanshuraut1009-debug"><img src="https://github.com/priyanshuraut1009-debug.png" width="40" style="border-radius:50%" /></a>

---

## 📄 License

Distributed under the MIT License. See [`LICENSE`](LICENSE) for details.

---

<p align="center">
  Because debugging shouldn't feel like decoding ancient runes.<br/>
  <strong>DevLens turns chaos into clarity — fast, structured, and developer-friendly.</strong><br/><br/>
  Built with 💙 · Happy Coding!
</p>
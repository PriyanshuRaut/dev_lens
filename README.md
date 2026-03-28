# 🔍 DevLens – A Lens to See Through Errors

## 🚀 Project Overview

**DevLens** is a Flutter-based AI debugging assistant that helps developers quickly understand and fix errors across multiple domains.

**Goal:**
Provide a unified, AI-driven debugging toolkit that turns confusing errors into clear, actionable insights.

**What it does:**

* Accepts:

  * Code snippets & syntax errors
  * API responses
  * JSON data
  * Logs / stack traces
  * WebSocket messages

* Returns:

  * Human-readable explanation
  * Root cause of the issue
  * Suggested fixes or corrected code

⚡ No backend required — all AI analysis is powered via external APIs (Groq / Google Gemini).

---

## ✨ Key Features (MVP)

### 🧠 AI Debug Assistant (Core)

* Paste any code or error
* Get:

  * Error explanation
  * Problematic line identification
  * Suggested fix

Example:
`if (x = 5)` → explains assignment vs comparison issue

---

### 🌐 API Error Debugger

* Analyze API responses (JSON or raw text)
* Detect:

  * Missing fields
  * Incorrect structure
  * Status code meaning

---

### 📜 Log Analyzer

* Paste logs or stack traces
* Extract:

  * Key errors
  * Exceptions
  * Likely root cause

---

### 🧾 JSON Formatter & Analyzer

* Format raw JSON into readable structure
* AI explains schema and detects anomalies

---

### 🔌 WebSocket Inspector

* Connect to WebSocket URLs
* View incoming messages
* Send test messages
* Built using `web_socket_channel`

---

### 🎯 Smart Prompt Templates

Structured actions instead of free chat:

* “Explain this code error”
* “Analyze this API response”
* “Debug this JSON”
* “Inspect WebSocket messages”

---

### ➕ Additional Perks

* Beginner-friendly explanations
* Highlighted problem areas
* Suggested corrected output
* Copy/share results

---

## 🛠 Tech Stack

### 📱 Frontend

* Flutter (Dart)

### 🤖 AI Integration

* Groq API
* Google Gemini API

### 📦 Packages

* `http` – API calls
* `web_socket_channel` – WebSocket handling
* `provider` / `riverpod` – State management
* `url_launcher` – External links

### 🧩 Architecture Choice

* No backend
* No database required
* Local state + external AI APIs

---

## 🏗 Architecture & Modules

DevLens is structured into modular screens:

* **AI Debug Screen** → Code/error analysis
* **API Debug Screen** → API response inspection
* **Log Analyzer Screen** → Log parsing
* **JSON Screen** → Formatting + analysis
* **WebSocket Screen** → Real-time message inspection

### 🔄 Core Flow

All modules use a shared **AI Manager**:

1. Take user input
2. Format structured prompt
3. Send via HTTP to AI API
4. Display response

---

## 🧪 Example (AI Call - Dart)

```dart
import 'package:http/http.dart' as http;

Future<String> analyzeText(String prompt) async {
  final apiUrl = 'https://api.groq.com/v1/complete';
  final apiKey = 'YOUR_GROQ_KEY';

  final response = await http.post(
    Uri.parse(apiUrl),
    headers: {
      'Authorization': apiKey,
      'Content-Type': 'application/json'
    },
    body: '''
    {
      "model": "gpt-3.5-turbo",
      "messages": [
        {"role": "user", "content": "$prompt"}
      ]
    }
    '''
  );

  return response.body;
}
```

---

## 🗺 MVP Roadmap

* [ ] API key setup (Groq / Gemini)
* [ ] AI Debug Screen
* [ ] JSON Formatter
* [ ] API Debugger
* [ ] WebSocket Client
* [ ] Log Analyzer

---

---

## 💡 Why DevLens?

Because debugging shouldn’t feel like decoding ancient runes.
DevLens turns chaos into clarity — fast, structured, and developer-friendly.

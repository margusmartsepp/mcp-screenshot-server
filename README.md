# 🖼️ MCP Screenshot Server

A lightweight, MCP-compatible screenshot microservice built with FastAPI for Windows.  
It allows AI agents and automation tools to capture full-screen, region-based, or window-specific screenshots via simple HTTP calls.

![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue) ![License: MIT](https://img.shields.io/badge/License-MIT-green) ![Python](https://img.shields.io/badge/Python-3.11%2B-yellow)

---

## 🔧 Features

- 📸 Capture full-screen screenshots
- 🪟 Capture specific window by title
- 🔲 Capture custom regions `[x, y, width, height]`
- 🧠 MCP-compliant REST API
- 🖼️ Returns images as PNG or base64
- 🚀 Built with FastAPI, ready for production or LLM use

---

## 🧠 Use Cases

- Integrating with LLMs using [Model Context Protocol (MCP)](https://github.com/anthropic-ai/model-context-protocol)
- QA test automation pipelines
- Monitoring and remote capture tools
- Visual logging/debugging tools for agents

---

## 📦 Installation

```bash
git clone https://github.com/yourusername/mcp-screenshot-server.git
cd mcp-screenshot-server
python -m venv .venv
source .venv/bin/activate   # or .venv\Scripts\activate on Windows
pip install -r requirements.txt
uvicorn main:app --reload
```

---

## 🔌 API Usage

### `POST /screenshot`

**Request JSON body:**

```json
{
  "region": [0, 0, 1280, 720],        // optional
  "window_title": "Untitled - Notepad", // optional
  "base64": true                      // optional (default: false)
}
```

**Response (base64 mode):**
```json
{
  "status": "ok",
  "mode": "region",
  "image_format": "base64",
  "image": "<base64-encoded-image>"
}
```

---

## 🛠️ Tech Stack

- Python 3.11+
- FastAPI
- `mss` or `pyautogui` for screenshot
- `pillow` for image processing
- `pygetwindow` for window matching (optional)

---

## 📄 License

MIT License.  
Feel free to use, fork, and integrate — commercial or personal.  
See [LICENSE](LICENSE) for details.

---

## 📬 Contributing

Pull requests and issues welcome!  
Open a PR to add features or improve compatibility across platforms (e.g., Mac/Linux support).

---

## 🙋 FAQ

- **Does it work on Linux/macOS?**  
  Not yet. This version is Windows-focused, but you’re welcome to extend it.

- **Is it MCP-certified?**  
  This project aims to follow the MCP spec as closely as possible for maximum compatibility with LLM agents.

---

## 🧠 Inspired By

- Anthropic’s [Model Context Protocol](https://github.com/anthropic-ai/model-context-protocol)
- Real-world automation use cases powered by LLMs and Python

---

```

Would you like me to tailor a specific section to emphasize AI agent use (e.g., “how to use with o1 or GPT-4o via plugin”)?

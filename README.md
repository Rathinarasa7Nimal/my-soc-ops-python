<div align="center">

# 🎲 Soc Ops

**Social Bingo for in-person mixers — find people, make connections, shout BINGO!**

[![Python 3.13+](https://img.shields.io/badge/python-3.13%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115%2B-009688?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![HTMX](https://img.shields.io/badge/HTMX-powered-3d72d7?logo=html5&logoColor=white)](https://htmx.org/)
[![License: MIT](https://img.shields.io/badge/license-MIT-yellow)](LICENSE)

</div>

---

## ✨ What Is Soc Ops?

Soc Ops is a **server-rendered social bingo game** built to energise workshops, meetups, and team events. Players receive a randomised 5×5 bingo card filled with fun prompts like *"has lived in another country"* or *"can juggle"*. Roam the room, find real humans who match each square, mark it off, and race to get **five in a row**.

No app install required — just open a browser and play.

---

## 🎮 How It Works

```
1. Open the app in your browser
2. Hit Start Game — get a unique, shuffled 5×5 bingo card
3. Walk around, chat to people, mark squares as you find matches
4. First to complete a row, column, or diagonal wins — BINGO! 🎉
```

The FREE SPACE in the centre is yours from the start. Every card is different, so no two players have the same layout.

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Backend** | Python 3.13 · FastAPI · Uvicorn |
| **Templating** | Jinja2 (server-rendered HTML) |
| **Frontend** | HTMX (fragment updates, no JS framework) |
| **State** | In-memory sessions via Starlette middleware |
| **Linting** | Ruff |
| **Testing** | Pytest · HTTPX |

---

## 🚀 Quick Start

**Prerequisites:** Python 3.13+ and [`uv`](https://docs.astral.sh/uv/).

```bash
# 1. Clone the repo (replace <your-username> with your GitHub username)
git clone https://github.com/<your-username>/my-soc-ops-python.git
cd my-soc-ops-python

# 2. Install dependencies
uv sync

# 3. Start the dev server
uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

Open **http://localhost:8000** and start playing. 🎲

---

## 🗂️ Project Structure

```
app/
├── main.py          # Route handlers (thin — logic lives elsewhere)
├── game_service.py  # Session state & GameSession class
├── game_logic.py    # Pure bingo rules (win detection, board generation)
├── models.py        # Typed Pydantic models (GameState, BingoSquareData …)
├── data.py          # Bingo prompt questions
├── templates/       # Jinja2 HTML templates
│   └── components/  # HTMX partial fragments
└── static/          # CSS & JS assets
tests/               # Pytest test suite
workshop/            # Offline lab guides
```

---

## 🧑‍💻 Development

```bash
# Run tests
uv run pytest

# Lint
uv run ruff check .

# Auto-fix lint issues
uv run ruff check . --fix
```

> ⚠️ **Mandatory checklist before finishing any change:** run `ruff check .`, run `pytest`, and verify the app starts with `uvicorn`.

---

## 📚 Lab Guide

This repo is also used as a **GitHub Copilot agent lab**. Follow the guided parts below to learn agent-driven development:

| Part | Title | Topics |
|------|-------|--------|
| [**00**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview) | Overview & Checklist | Prerequisites, goals |
| [**01**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=01-setup) | Setup & Context Engineering | Workspace instructions, ruff |
| [**02**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=02-design) | Design-First Frontend | UI redesign with agents |
| [**03**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=03-quiz-master) | Custom Quiz Master | Custom agent creation |
| [**04**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=04-multi-agent) | Multi-Agent Development | TDD Red → Green → Refactor |

> 📝 Offline copies of all lab guides live in the [`workshop/`](workshop/) folder.

---

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) and follow the [Code of Conduct](CODE_OF_CONDUCT.md).

---

## 📄 License

[MIT](LICENSE) — feel free to fork and run your own mixer. 🎉

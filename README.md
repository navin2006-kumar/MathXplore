# MathXplore

A multi-tool mathematics web application built with Flask, featuring matrix operations, scientific and finance calculators, a function graph plotter, and an AI-powered math tutor chatbot.

---

## Features

| Module | Route | Description |
|---|---|---|
| Home | `/home` | Main dashboard |
| Matrix Calculator | `/matrix` | Full linear algebra operations |
| Scientific Calculator | `/sci` | Standard scientific functions |
| Finance Calculator | `/finan` | EMI, FD and Compound Interest |
| Graph Plotter | `/graph` | Visualize mathematical functions |
| Algebra Tools | `/algebra` | Algebraic computation helpers |
| Math Bot | `/bot` | AI math tutor with LaTeX rendering |

---

## Tech Stack

- **Backend:** Python, Flask
- **Math Engine:** NumPy
- **AI / Chatbot:** [Groq API](https://groq.com) — `llama3-70b-8192`
- **Frontend:** HTML, CSS, JavaScript (Jinja2 templates)
- **Environment:** python-dotenv

---

## Getting Started

### Prerequisites

- Python 3.8+
- A [Groq API key](https://console.groq.com)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/navin2006-kumar/MathXplore.git
cd MathXplore

# 2. Create and activate a virtual environment
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install flask numpy groq python-dotenv

# 4. Set up your environment variables
cp .env.example .env
# Add your Groq API key to .env:
# GROQ_API_KEY=your_key_here

# 5. Run the app
python app.py
```

Visit `http://127.0.0.1:5000` in your browser.

---

## Module Details

### Matrix Calculator

Supports the following operations via NumPy:

- Addition and Subtraction
- Matrix Multiplication
- Determinant, Inverse, Transpose
- Eigenvalues
- Matrix Rank

**API:** `POST /calculate` — accepts JSON with `operation`, `matrixA`, and optionally `matrixB`.

### Finance Calculator

Three sub-calculators:

- **EMI Calculator** — loan amount, interest rate, tenure (months/years)
- **Fixed Deposit** — simple or quarterly compound interest
- **Compound Interest** — configurable compounding frequency

### Math Bot

Powered by Groq's `llama3-70b-8192` model acting as a math professor. Responses are formatted with LaTeX:

- Inline equations: `$ ... $`
- Display equations: `$$ ... $$`

**API:** `POST /chat` — accepts JSON `{ "message": "your question" }`.

---

## Project Structure

```
MathXplore/
├── app.py                  # Flask application and all routes
├── templates/
│   ├── welcome.html        # Landing page
│   ├── home.html           # Dashboard
│   ├── index.html          # Matrix calculator
│   ├── calc.html           # Scientific calculator
│   ├── fina.html           # Finance calculator
│   ├── graph.html          # Graph plotter
│   ├── algebra.html        # Algebra tools
│   ├── bot.html            # AI chatbot
│   └── navbar.html         # Shared navigation
├── static/
│   └── images/             # Static assets
├── .env                    # Environment variables (not committed)
└── README.md
```

---

## Environment Variables

Create a `.env` file in the root directory:

```env
GROQ_API_KEY=your_groq_api_key_here
```

> **Note:** Never commit your `.env` file. Ensure `.env` is listed in `.gitignore`.

---

## Screenshots

*(Add screenshots of each module here)*

---

## Future Improvements

- Add `.gitignore` to exclude `.env` and `__pycache__`
- Unit tests for matrix and finance endpoints
- Persistent chat history in Math Bot
- Mobile-responsive UI
- Deployment to Render / Railway

---

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

---

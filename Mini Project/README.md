<img width="1090" height="771" alt="Screenshot 2026-02-19 135404" src="https://github.com/user-attachments/assets/eaf46de6-db85-4ff1-a18e-3c32f755b927" />

# 🧮 Python Calculator

A clean, interactive command-line calculator built with Python. Supports basic arithmetic, percentage calculations, and statistical analysis — all from a simple menu-driven interface.

---

## ✨ Features

| Module | Operations |
|---|---|
| **Basic Arithmetic** | Addition, Subtraction, Multiplication, Division |
| **Percentage Calculator** | X% of a number · A as % of B · % Increase/Decrease |
| **Statistics** | Mean · Median · Mode · Sum · Min · Max · Count |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10 or higher (uses `list[float]` type hint syntax)
- No third-party libraries required — only Python standard library modules

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/python-calculator.git

# Navigate into the project directory
cd python-calculator
```

### Running the Calculator

```bash
python calculator.py
```

---

## 🖥️ Usage

On launch, you'll see the main menu:

```
══════════════════════════════════════════
   PYTHON CALCULATOR
   Arithmetic · Statistics · Percentage
══════════════════════════════════════════

  MAIN MENU
  1) Basic Arithmetic  ( +  −  ×  ÷ )
  2) Percentage Calculator ( % )
  3) Statistics ( Mean · Median · Mode )
  4) Exit
```

### Basic Arithmetic

Enter two numbers and choose an operation. Division by zero is handled gracefully.

### Percentage Calculator

Three sub-modes:
- **X% of a number** — e.g., 20% of 150 → 30
- **What % is A of B?** — e.g., 30 of 150 → 20%
- **% Increase / Decrease** — e.g., 100 → 120 → +20%

### Statistics

Enter a list of numbers (type `done` when finished) and choose from:
- Individual stats: Mean, Median, or Mode
- **All at once** — includes Sum, Min, Max, and Count

> **Note:** The mode calculator correctly handles the edge case where all values appear with equal frequency (no mode).

---

## 📁 Project Structure

```
python-calculator/
└── calculator.py       # Main application — all modules in one file
```

---

## 🛠️ Built With

- [`statistics`](https://docs.python.org/3/library/statistics.html) — Mean and Median calculations
- [`collections.Counter`](https://docs.python.org/3/library/collections.html#collections.Counter) — Mode detection
- Pure Python `input()` loops with full input validation

---

## 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request for:
- New calculator modules (e.g., unit converter, BMI, loan calculator)
- GUI version using Tkinter or PyQt
- Test coverage with `unittest` or `pytest`

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👤 Author

**Your Name**
- GitHub: [@your-username](https://github.com/your-username)

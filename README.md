# AI Financial Auditor Bot

A cloud-hosted, automated Telegram bot that leverages AI (Google Gemini 2.5 Flash) to extract unstructured data from physical receipts, invoices, and vouchers, injecting it in real-time into a Google Sheets accounting database.

## Key Features

* Intelligent Extraction: Reads images (`.jpg`, `.png`) and documents (`.pdf`) using LLM-powered computer vision.
* Deterministic Balancing: Implements strict logical guardrails in Python to ensure the sum of extracted items perfectly matches the total amount paid, handling taxes and discounts as separate entities.
* Dynamic Classification: Automatically categorizes documents as "Invoice" (Factura) or "Receipt" (Nota) based on context and vendor names.
* Real-Time Data Injection: Uses the Google Workspace API (`gspread`) to clean, sort (via `pandas`), and log financial data.
* Automated Sheet Orchestration: Dynamically creates new monthly tabs by cloning a template sheet if the current month does not exist, keeping the database architecture intact.

## Tech Stack

* **Language:** Python 3.x
* **AI & Cloud:** Google Generative AI API (Gemini 2.5 Flash)
* **Integrations:** Telegram Bot API (`pyTelegramBotAPI`), Google Sheets API (`gspread`), Google Drive API
* **Data Processing:** `pandas`
* **Security:** Environment variables (`.env`) and Google Service Accounts (`.json`)

## Setup & Installation

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/AngelNandayapa/ai-expense-tracker-bot.git](https://github.com/TuUsuario/ai-expense-tracker-bot.git)
   cd ai-expense-tracker-bot
2. Install dependencies:
   pip install -r requirements.txt
3. Configure Environment Variables:
   Rename the .env.example file to .env.
   Replace the placeholder values with your actual Telegram Token and Gemini API Key.
   Place your Google Service Account credentials file (bot-fxyx.json) in the root directory.
4. Run the bot:
   python bot.py

Security Notice
For security reasons, API keys and Google Service Account credentials (.json) are not included in this repository and are ignored via .gitignore.

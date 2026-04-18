# 🥗 MealPrep AI: Nutritional Amortization Engine
By: Kavin Manivannan, Nate Theis, Jacob Jones

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Gemini](https://img.shields.io/badge/AI-Gemini%202.5%20Flash-orange.svg)](https://ai.google.dev/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**MealPrep AI** is a biometric financial engineering tool designed to combat food insecurity. It transforms a simple Google Form submission into a rigorous, math-validated "Survival Grocery Plan" that is emailed directly to the user as a professionally formatted Google Doc.

---

## ⚠️ The Problem: The Student Budget Gap
The average college student spends roughly **$11–$15 per meal** when eating out. Over a 14-day period, that totals approximately **$462**. 

**MealPrep AI reduces that 14-day cost to ~$17.** This represents a **96.3% reduction in food expenditure**, effectively reclaiming hundreds of dollars for tuition, rent, and emergency savings. For many, the choice between buying a textbook and eating a healthy meal is a daily reality; this tool eliminates that trade-off through algorithmic shopping.

---

## 🚀 The Mission
MealPrep AI solves the "Analysis Paralysis" of grocery shopping on a shoestring budget by:
1.  **Calculating TDEE:** Using the Mifflin-St Jeor equation to find the user's exact caloric needs based on height, weight, age, and gender.
2.  **Live Market Grounding:** Using AI-powered web search to find real-time prices at local stores (Aldi, Walmart, Giant, Lidl) in the user's specific Maryland county.
3.  **Financial Amortization:** Breaking down a total budget (e.g., $20) into a "Daily Burn Rate" to ensure the user never runs out of food before their next paycheck.

---

## 🛠️ Tech Stack
* **Core Engine:** Python (Google Colab Environment)
* **Intelligence:** Gemini 2.5 Flash (via `google-genai` SDK)
* **Tools:** Google Search Grounding for live grocery pricing
* **Database/Trigger:** Google Sheets API (via `gspread`)
* **Output Suite:** Google Docs API (Automated professional formatting)
* **Communication:** SMTP/Gmail (Automated report delivery)

---

## 📊 Impact Statistics: Expanding Food Access

### 1. The Affordability Frontier
* **Target:** Individuals with a "Daily Burn Rate" of **<$2.00/day**. 
* **The Solution:** Most meal prep resources assume a $50+ weekly budget. MealPrep AI successfully engineered a **14-day plan for just $16.97** ($1.22/day), providing 7 staple items with verified purchase links.

### 2. Time-Poverty Reduction
* **Manual Effort:** Comparing prices across multiple stores and calculating nutritional math manually takes ~2–3 hours.
* **MealPrep AI Speed:** Generates a complete, formatted, and emailed report in **<60 seconds**.

### 3. Nutrition Equity
* **Calculated Accuracy:** By using **Mifflin-St Jeor**, the tool prevents "starvation budgeting." It identifies when a budget is too low (e.g., highlighting the gap between a 2036 kcal TDEE and the plan's output) and provides risk variance notes to help users find local food pantries.

---

## 📋 How It Works
1.  **Input:** User fills out a Google Form (Age, Weight, Height, Budget, Timeline, County).
2.  **Sync:** Data populates a Google Sheet.
3.  **Process:** The Python script detects the new row, triggers Gemini to search for local prices in the specific Maryland county, and validates the amortization math.
4.  **Format:** The `build_investment_doc` function creates a high-contrast, "Cyberpunk/Financial" themed Google Doc using the Google Docs API.
5.  **Deliver:** The report link is shared with "anyone with the link" permissions and emailed to the student automatically via SMTP.

---

## 🛠️ Setup & Installation

1.  **Clone the Repo:**
    ```bash
    git clone [https://github.com/yourusername/mealprep-ai.git](https://github.com/yourusername/mealprep-ai.git)
    ```
2.  **Set Up Secrets:**
    In your environment (or Colab Secrets), add:
    * `GMAIL_APP_PASSWORD`: Your Gmail App-specific password.
    * `GEMINI_API_KEY`: Your API key from Google AI Studio.
3.  **Link Spreadsheet:**
    Update the `SHEET_URL` variable in the script with your Google Sheet URL.
4.  **Run:**
    Execute the `start_mealprep_ai()` function to begin the listener loop.

---

## 📜 License
Distributed under the MIT License. See `LICENSE` for more information.

**Built for the community to ensure no student goes hungry while pursuing their degree.**

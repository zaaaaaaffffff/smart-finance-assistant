📖 Project Overview:

This project builds a Smart Finance Assistant that lets users upload their bank transaction data, get an automatic spending breakdown, ask questions about their finances via an AI chatbot, and calculate savings goals — all from a single web interface.
The assistant is made up of six components that work together:

Transaction Loader — cleans and validates raw CSV bank data
Spending Analyser — breaks down spending by category and generates insights
Recommendations Engine — produces personalised, actionable financial coaching tips
Finance Chatbot (Penny) — a context-aware AI chat assistant powered by Hands On AI
Financial RAG — retrieves answers from financial documents using TF-IDF search
Gradio UI — ties everything together in a three-tab web dashboard


**📂 File Descriptions**
**transaction_loader.py:**

Loads and cleans transaction CSV files for use throughout the app.
Expects a CSV with four columns: Date, Amount, Category, and Description. It handles messy real-world data including dollar signs ($1,234.56), parentheses-style negatives ((45.00)), missing rows, and free-text category names. A CATEGORY_ALIASES dictionary normalises variations like "groceries" and "dining" into canonical names like "Food". Rows with unparseable dates or amounts are silently dropped. The function returns a clean DataFrame ready for analysis.
Includes three built-in tests covering a valid mixed-format CSV, a schema mismatch, and an empty file.

**spending_analysis.py:**

Analyses a cleaned transaction DataFrame and produces a structured spending report.
It separates spending (positive amounts) from refunds (negative amounts), aggregates totals by category, and calculates each category's percentage of gross spend. It then generates plain-text insights — for example, flagging if fixed costs like rent exceed 50% of gross spend, or if a discretionary category like Food or Entertainment spikes above 25%. Results are returned as a SpendingAnalysis dataclass containing the category breakdown table, top categories, insights list, and a pre-rendered markdown report.
Includes four tests covering standard analysis, refund-only data, missing columns, and discretionary spike detection.

**recommendations.py:**

Generates a personalised financial coaching report from spending data.
Takes a dictionary of category totals and produces a three-section markdown report: spending pattern observations (e.g. flagging high food spend), specific savings opportunities (e.g. the 50/30/20 rule alignment, supermarket swaps, subscription audits), and quick micro-wins the user can act on today. Falls back gracefully if no data is provided.

**finance_chatbot.py:**

An AI chat assistant called Penny built for Google Colab using hands_on_ai and ipywidgets.
Penny is a friendly, judgment-free personal finance coach. If spending data is passed in from the analyser, she injects it into her system prompt so she can give personalised responses like "I can see your top category is Entertainment." The FinanceChatSession class manages conversation history across turns. The launch_finance_chat() function renders a full chat UI in Colab — including a message history panel, quick-prompt shortcut buttons, a text input, and a clear button.
Can also be used programmatically without the UI by calling session.send("your question") directly.

**financial_rag.py:**

A Retrieval-Augmented Generation system that answers questions from financial documents.
Documents in the financial_docs/ folder are split into overlapping sentence-window chunks (5 sentences, 2-sentence overlap), then indexed using TF-IDF vectors via scikit-learn. When a question is asked, cosine similarity is used to rank and retrieve the most relevant chunks, which are injected into the LLM's system prompt. The LLM (Ollama gemma3:4b via the Hands On AI platform) then answers using only that retrieved context — preventing hallucinated figures.
Ships with three sample documents covering a Q1 2024 financial report, the 50/30/20 budgeting rule, and a March 2024 transaction summary.

**smart_finance_ui.py:**

A Gradio web app that brings all components together in a three-tab dashboard.
Tab 1 — Data Dashboard: Upload a CSV file to trigger analysis. Displays total spending, top category, and a bar chart of spending by category.
Tab 2 — Financial Coach Chat: A live chatbot powered by Ollama (gemma3:4b). Maintains full conversation history across turns so the model has context for follow-up questions. Includes quick-prompt shortcut buttons for common questions like "Where can I cut costs?" and "Explain the 50/30/20 rule."
Tab 3 — Savings Calculator: Enter a starting balance, monthly contribution, savings goal, and APY to calculate how long it will take to reach the goal using compound interest. Displays total months, years/months breakdown, total contributed, and interest earned.

🚀 Getting Started

Open the notebook in Google Colab (Hands On AI platform).
Run the install cell first:

   !pip install openai scikit-learn gradio pandas --quiet

Run each component cell in order — the loader and analyser feed data into the chatbot and UI.
To launch the Gradio dashboard, run smart_finance_ui.py and open the local URL it prints.
To use the RAG assistant standalone, instantiate FinancialRAG() and call finance_rag.ask("your question").
To use the Colab chatbot, call launch_finance_chat() — optionally passing in spending analysis results for personalised responses.


✅ What Each File Does (Summary)
FilePurposetransaction_loader.pyLoads, validates, and cleans CSV transaction dataspending_analysis.pyAggregates spending by category, flags anomalies, generates insightsrecommendations.pyProduces personalised savings tips and coaching observationsfinance_chatbot.pyAI chatbot (Penny) with Colab UI and conversation memoryfinancial_rag.pyTF-IDF document retrieval + LLM Q&A from financial docssmart_finance_ui.pyGradio web dashboard tying all features into one interface

📚 Dependencies

openai — OpenAI-compatible client for Ollama
scikit-learn — TF-IDF vectoriser and cosine similarity for RAG
gradio — Web UI framework
pandas — DataFrame processing
hands-on-ai — Chat and agent tools (Colab chatbot only)
ipywidgets — Colab chat UI widgets


📜 License
This project is licensed under the MIT License. See the LICENSE file for details.

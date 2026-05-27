---
title: "Final Programming Project Specification"
author: "ISYS2001: Introduction to Business Programming"
format: pdf
---

# 📝 Final Programming Project

**Assignment Title:** Smart Finance Assistant  
**Due Date:** Week 13 (Friday 17 October 2025, 11:59pm AWST)  
**Weighting:** 30%  
**Submission:** GitHub repository link (Notebook + Developer’s Diary)

---

## 🎯 Project Overview
In this project you will design, implement, and test a **Smart Finance Assistant** using **Python, Google Colab, Gradio, and the `hands-on-ai` package**.

This project provides a template repository to help you get started.

Your Assistant should help users complete personal finance tasks such as:
- Summarising transactions from a CSV file
- Tracking a stock/crypto portfolio via API data
- Analysing budgets and spending patterns
- Offering advice through a chatbot personality
- Running a simple custom tool (e.g., currency converter, savings goal calculator)

Each student will create **one complete Colab Notebook** that integrates:
1. **Chat** – a finance-oriented personality bot
2. **RAG** – retrieval from CSV or other documents
3. **Agent Tool** – one custom function registered as a tool
4. **Gradio UI** – a simple interface that ties these together

This notebook must be a working Google Colab notebook, able to be run in the Google Colab environment. Furthermore, it must use the following Large Language Model provider: base URL `https://ollama.serveur.au` and an API key of `isys2001smartfinance`.  

---

## 🚀 Getting Started: Using the Template Repository

This will be the first time you have used a template repository, so follow these instructions carefully.

1.  **Create your own repository from this template.**
    *   Click the "Use this template" button at the top of the repository page.
    *   Select "Create a new repository".
    *   Give your repository a name (e.g., `smart-finance-assistant-yourname`).
    *   Make sure the repository is set to **Private**.
    *   Click "Create repository from template".

2.  **Open the starter_notebook.ipynb in Google Colab.**
    *   Navigate to your newly created repository on GitHub.
    *   Click on the `starter_notebook.ipynb` file to view it.
    *   Click the "Open in Colab" button (usually found at the top of the notebook viewer). This will open the notebook in Google Colab, connected to your GitHub repository.

3.  **Start working on the assignment.**
    *   Follow the instructions within the `starter_notebook.ipynb`.
    *   As you make changes in Colab, commit them regularly using Colab's built-in Git integration (File -> Save a copy in GitHub).
    *   Ensure your commits have meaningful messages.

---

## 🔑 Six-Step Development Methodology
Your notebook must include **evidence of each step** in the methodology below. You can find a detailed explanation of this methodology here: [The Six-Step Programming Methodology](https://michael-borck.github.io/intentional-prompting/chapters/04-six-step-methodology.html).

Use Markdown cells, comments, or screenshots where appropriate:

1. **Understand the Problem** – Restate the finance problem in plain English.  
2. **Identify Inputs and Outputs** – Clearly list inputs (e.g., CSV) and outputs.  
3. **Work the Problem by Hand** – Show 2–3 manual examples (Markdown or image).  
4. **Write Pseudo Code** – Sketch the solution logic before coding.  
5. **Convert to Python** – Implement your solution in Python cells (using `hands-on-ai`).  
6. **Test with a Variety of Data** – Include a **Testing Section** at the end of your notebook with asserts or simple tests.  

---

## 📦 Deliverables
1. **Colab Notebook** (main project file) containing:  
   - Code, markdown reflections, Gradio UI  
   - Evidence of the six-step method  
   - A Testing section with meaningful test cases  

2. **GitHub Repository** containing:  
   - The Colab Notebook  
   - A clear **README** explaining what your Assistant does, sample inputs/outputs, and instructions to run  
   - Your **Developer’s Diary** (Markdown file)  
   - You must invite your instructor (`michael-borck`) as a collaborator to your private repository.

3. **Developer’s Diary** including:  
   - *Weekly AI Evidence Packages* documenting how you collaborated with AI (Weeks 8–12):  
     - **Artifact**: screenshot/GIF of AI interaction  
     - **Context**: one-sentence goal  
     - **Reflection**: what worked, what didn’t, what you learned  
   - These weekly packages demonstrate steady engagement and will be checked as part of your AI Collaboration mark.  

4. **GitHub Commit History**  
   - At least one meaningful commit per week (Weeks 8–12) is expected.  
   - Commits may include code, diary updates, or README improvements.  

5. **LMS Submission**
   - A zip file of your final GitHub repository submitted to the LMS.

---

## 🧭 Suggested Project Themes
Choose one of the following or propose your own (with tutor approval):
- **Budget Buddy**: upload CSV expenses, chatbot gives spending advice  
- **Investment Insight**: track stock/crypto via API, provide summaries  
- **Currency Converter Agent**: upload travel expenses, tool converts currencies  
- **Savings Coach**: personality bot gives encouragement + calculates savings goals  

---

## 📊 Assessment Criteria (Rubric)

| Criterion | Weight | High Distinction (HD) | Distinction (D) | Credit (C) | Pass (P) | Fail (N) |
|-----------|--------|-----------------------|-----------------|------------|----------|----------|
| **Functionality**<br>(chatbot, RAG, tool, UI integrated) | 30% | Fully working Finance Assistant with all required components seamlessly integrated. Gradio app is polished, intuitive, and demonstrates advanced features. | All required components implemented and working with minor issues. Gradio UI is functional and easy to use. | Most required components implemented with some integration issues. Gradio UI works but is basic. | Partial functionality: only some components working. Limited or clunky UI. | Project does not run, or only trivial features implemented. No usable UI. |
| **Testing & Debugging**<br>(test section + edge cases) | 20% | Comprehensive tests covering normal, edge, and error cases. Clear evidence of debugging/refinement. | Solid test set covering main functions. Some edge cases attempted. Evidence of debugging shown. | Basic tests written with limited edge cases. Debugging attempted but incomplete. | Minimal testing, only a few examples tested. No clear debugging effort. | No testing or debugging evidence provided. |
| **AI Collaboration & Weekly Progress**<br>(`hands-on-ai`, AI evidence packages, GitHub commits) | 20% | Extensive, well-documented AI use across all weeks. Weekly evidence packages are insightful and reflective. GitHub shows consistent weekly commits with clear messages. | Strong use of AI with regular weekly evidence. Diary reflections are thoughtful. GitHub commits show regular progress. | Adequate AI use, some weekly evidence missing or shallow. GitHub commits show some gaps. | Limited AI use, minimal evidence packages, or GitHub shows last-minute bulk uploads. | No evidence of AI collaboration or weekly progress. GitHub empty or single dump. |
| **Business Relevance**<br>(finance problem-solving) | 15% | Application addresses a clear, meaningful finance problem. Demonstrates creativity, insight, and strong business framing. | Application solves a practical finance problem with minor gaps. Business framing is clear. | Application has some finance relevance but limited depth. Problem framing is basic. | Finance connection is superficial. | No meaningful finance connection. |
| **Clarity & Reflection**<br>(repo structure, README, diary) | 15% | Repo is professional and well-organised. README is clear, detailed, and visually engaging. Developer’s Diary is comprehensive and reflective. | Repo is organised with clear structure. README explains setup and use. Diary contains meaningful reflections. | Repo contains basic structure and instructions. README present but limited. Diary has some reflections but lacks depth. | Repo disorganised or incomplete. README minimal. Diary reflections very limited. | Repo missing or unusable. No README or diary. |

---

## 🔒 Academic Integrity & AI Usage
- You are encouraged to use AI tools (Gemini, Copilot, ChatGPT, etc.) to generate, debug, and refine code.  
- **All AI use must be documented** in your Developer’s Diary.  
- Undeclared AI use is considered misconduct.  
- You are responsible for testing and validating all AI-generated code.  

---

## ✅ By the End You Will Have
- Designed a small end-to-end finance assistant  
- Practiced the six-step methodology from problem to tests  
- Learned how to direct AI as a coding partner  
- Produced a portfolio-ready interactive Python app

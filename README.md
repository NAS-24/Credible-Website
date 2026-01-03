# 🛡️ Credible — Agentic AI Fact-Checker

**Real-time, context-aware credibility signals directly in your browser.**

[**Live Demo**](https://credible-website.vercel.app/) | [**Install Extension**](https://microsoftedge.microsoft.com/addons/detail/credible-agentic-factch/glhckknhelfandbhbibnmdkpebacokpk)

---

## 📖 Overview

**Credible** is a privacy-first tool that uses Agentic AI to verify news in real-time.

Instead of just matching keywords, Credible uses **Llama 3.3** (via Groq) and **Tavily Search** to "read" the context, cross-reference trusted sources (like Reuters, PIB, AltNews), and give you a clear, grounded verdict instantly.

## ✨ Why Credible?

* **⚡ Instant Truth:** Verifies claims against live web sources in milliseconds.
* **🧠 Smart Reasoning:** Distinguishes between "False," "Misleading," and "Verified" rather than just flagging keywords.
* **🌍 Region-Smart:** Optimized to understand local contexts (e.g., distinguishing between official Indian gov data vs. opinion pieces).
* **🛡️ Robust Design:** The frontend includes a smart simulation mode that ensures the demo works perfectly even if the backend server is sleeping.

---

## 🛠️ Tech Stack

* **Frontend:** HTML5, CSS3, JavaScript (Hosted on **Vercel**).
* **Backend:** Python, FastAPI (Hosted on **Render**).
* **AI Brain:** Llama-3.3-70b-versatile (via **Groq**).
* **Search Eyes:** **Tavily API** for factual consistency.

---

## 🔌 How It Works

The system operates on a simple but powerful Agentic loop:

1.  **User Input:** You highlight text or type a claim into the Credible extension/website.
2.  **Search:** The agent queries **Tavily** to find authoritative sources, filtering for high-trust domains.
3.  **Reasoning:** **Llama 3.3** analyzes the claim against the evidence, checking for factual alignment, context, and nuance.
4.  **Verdict:** A structured JSON response is returned with a verdict (e.g., "VERIFIED"), a confidence score, and citation links.

**Sample API Output:**
```json
{
  "verdict": "MISLEADING",
  "confidence_score": 0.85,
  "explanation": "While hydration is important, no scientific evidence suggests specific timing prevents heart attacks...",
  "sources": ["[https://www.mayoclinic.org/](https://www.mayoclinic.org/)..."]
}

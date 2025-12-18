# Holiday Company Gift Card Agents Demo

A demonstration project showcasing an AI-powered **Policy-Compliant Gift Recommendation Application** built using **Enterprise h2oGPTe (Freemium)** from H2O.ai.

This repository accompanies a hands-on session where **Andreea Turcu**, Head of Training at H2O.ai, walks through how to build a fully functional AI agent in minutes using Enterprise h2oGPTe, starting from a simple prompt and evolving into a policy-aware AI agent that generates structured outputs and powers an interactive dashboard.

The demo is based on a real-world use case: **creating policy-compliant holiday gift recommendations** based on company guidelines, budgets, and governance constraints.

---

## 🎥 Presentation, Demo & Resources

### Presentation Slides (PDF)

To view and download the presentation slides used in this session, use the link below. The file opens directly in your browser or can be downloaded for offline use:

https://raw.githubusercontent.com/Andreea-Turcu/holiday-company-gift-card-agents-demo/main/Presentation%20Slides%20-%20Create%20Your%20Own%20AI%20Agent%20with%20h2oGPTe.pdf

---

### Webinar Recording (Live Demo Walkthrough)

https://youtu.be/RCsjmUjXLcw

---

### Live Agent Demo (GitHub Pages)

Both versions of the **policy-compliant gift recommendation applications**, built with the **Enterprise h2oGPTe freemium version**, are available here:

https://andreea-turcu.github.io/holiday-company-gift-card-agents-demo/

- Version 1: Traditional holiday theme  
- Version 2: H2O.ai branded theme

---

## 🎯 What This Project Demonstrates

This interactive dashboard shows how AI agents can help organizations:

- **Select Policy-Compliant Gifts**  
  Recommendations are generated using company policy documents via RAG to ensure compliance with anti-bribery and gift-giving rules.

- **Personalize Gift Selection**  
  Gifts are tailored to recipient profiles such as colleagues, senior clients, and new team members.

- **Enforce Budget Constraints**  
  Budget limits are applied strictly and visualized clearly.

- **Generate Structured Outputs**  
  JSON-based outputs ensure traceability, auditability, and downstream automation.

- **Support Operational Workflows**  
  Email notifications and summaries can be generated once selections are made.

---

## ✨ Key Features

- 3 predefined recipient profiles
- 9 curated gift recommendations across categories
- Interactive dashboard with filtering and expansion
- Dynamic budget tracking
- Explicit policy alignment per gift
- Gmail-based email generation
- Responsive, mobile-friendly UI
- Festive yet professional theming

---

## 📦 Available Files

- **index.html** – Version selector landing page  
- **index_v1.html** – Holiday theme (red / green)  
- **index_v2.html** – H2O.ai branding (yellow / black)  

---

## 🧠 How This Was Built

This project was created using **Enterprise h2oGPTe (Freemium)** from H2O.ai:

https://genai.h2o.ai/appstore

The agent was built iteratively using carefully designed prompts. Below are the **exact prompts used**, mapped to the **slide numbers** in the presentation deck.

---

## 🧩 Build Process & Prompts

### Exploration Phase – Structured Output

**Slide 17**

I’m planning a holiday party for 15 people with a $300 budget.
Can you help me create a complete party plan including:
	•	Budget breakdown (food, drinks, decorations, entertainment)
	•	3 easy appetizer recipes
	•	A shopping list
	•	A timeline for party prep
Make it festive and fun for a Christmas theme!

**Slide 18**

Perfect! Now regenerate that party plan as a JSON object with this schema:

{
“party_details”: {
“theme”: “string”,
“guest_count”: number,
“total_budget”: number
},
“budget_breakdown”: {
“food”: number,
“drinks”: number,
“decorations”: number,
“entertainment”: number
},
“recipes”: [
{
“name”: “string”,
“servings”: number,
“prep_time_minutes”: number,
“ingredients”: [“string”],
“instructions”: “string”
}
],
“shopping_list”: {
“category”: [“string”]
},
“timeline”: [
{
“task”: “string”,
“when”: “string”,
“duration_minutes”: number
}
]
}

Output ONLY the JSON, no extra text.

This step validates structured, machine-readable outputs.

---

### System Prompt Configuration

**Slide 23**

You are an AI Agent that must follow these rules:
	1.	Always use rag_text to retrieve relevant information from the attached document collection before answering.
	2.	Base your answers on the retrieved content and clearly state alignment or conflicts.
	3.	Enforce all budgets and constraints strictly.
	4.	When structured output is requested, return valid JSON matching the schema exactly.
	5.	When providing recommendations, include:
	•	gift_name
	•	price
	•	category
	•	reason
	•	policy_alignment
	6.	If any request violates the policies, do not proceed and suggest compliant alternatives.
	7.	Think step by step and apply explicit reasoning.

  ---

### Policy Documents Used for RAG

**Slide 22 – Policy v1**

https://triagelogic.com/wp-content/uploads/2018/06/Company-Policy-and-Procedure-June-1.18-V6.0.pdf

**Slide 25 – Policy v2 (Gift-Giving Guidelines)**

https://diabengineering.com.au/wp-content/uploads/2019/02/HSE-MAN-001-001-DIAB-Engineering-Policy-Manual-Rev05-All-Policies.pdf

---

### Gift Recommendation Prompt

**Slide 24**

I need to find appropriate holiday gifts for 3 different people:
	1.	A colleague who loves tech gadgets (budget $40–70)
	2.	A senior client who wants thoughtful, professional gifts (budget $80–120)
	3.	A new team member who enjoys cooking and creative hobbies (budget $25–50)

Please:
	•	Use my company policy guidelines from our RAG collection
	•	Follow the budget rules strictly
	•	For each person, give 3 gift options
	•	Include JSON output with:
	•	gift_name
	•	price
	•	category
	•	reason
	•	policy_alignment

Make sure recommendations do not violate any company rules.
If there are no Gift-Giving Guidelines in this document, please let me know.

---

### Dashboard Generation

**Slide 26**

The AI is instructed to generate a **complete HTML application** with embedded CSS and JavaScript to visualize the recommendations, budgets, and compliance indicators.

---

### Interactivity & Email Integration

**Slide 27**

Modify the HTML so that only one gift can be selected per recipient.
Update the budget dynamically based on the selected gift.
Add a button to generate a pre-filled email with:
	•	Recipient name
	•	Email address
	•	Subject and holiday message

Open the email in Gmail directly.
Apply H2O.ai branding based on:
https://h2o.ai/company/brand-kit/

---

### Certification Quiz

**Slide 29**

https://www.classmarker.com/online-test/start/?quiz=6kk693b055cdcb23

---

## 🛠️ Tools & Technologies

- **AI Platform**: Enterprise h2oGPTe (Freemium)
- **RAG**: Policy document ingestion and retrieval
- **Frontend**: HTML5, CSS3, JavaScript
- **Email**: Gmail compose URLs
- **Deployment**: GitHub Pages

---

## 🚀 Get Started with h2oGPTe

- Try h2oGPTe (Freemium):  
  https://genai.h2o.ai/appstore

- H2O.ai official website:  
  https://h2o.ai/

- Explore courses on H2O.ai University:  
  https://h2o.ai/university/

---

## ⚠️ Important Compliance & Security Disclaimer

This project uses **Enterprise h2oGPTe Freemium** for demonstration and educational purposes.

**Do NOT upload:**
- Confidential company data
- Personal identifiable information (PII)
- Financial, legal, or HR-sensitive documents
- Proprietary or regulated data

Always ensure that any data used complies with your organization’s security, privacy, and compliance policies. For production use cases involving sensitive data, consult your legal, compliance, and security teams and use approved enterprise deployments.

---

**Educational demo only. Not a substitute for legal or compliance review.**

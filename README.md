View / download: https://raw.githubusercontent.com/Andreea-Turcu/holiday-company-gift-card-agents-demo/main/Presentation%20Slides%20-%20Create%20Your%20Own%20AI%20Agent%20with%20h2oGPTe.pdf

# Holiday Company Gift Card Agents Demo
A demonstration project showcasing an AI-powered Holiday Gift Recommendations Dashboard built using **h2oGPTe** (H2O.ai's enterprise generative AI platform). This project demonstrates how AI agents can help companies select policy-compliant, thoughtful gifts for employees and clients during the holiday season.
## What This Project Does
This interactive dashboard helps organizations:
- **Select Policy-Compliant Gifts**: All gift recommendations comply with anti-bribery and corruption policies (DIAB Engineering's MGT-POL-001-009 Rev06)
- **Personalize Gift Selection**: Match gifts to recipient interests and roles (colleagues, clients, team members)
- **Manage Budgets**: Track spending per recipient with visual budget indicators
- **Generate Notifications**: Create pre-filled email notifications via Gmail or default email client
### Key Features
- **3 Recipient Profiles**: Pre-configured personas (Tech Enthusiast Colleague, Senior Client Executive, New Creative Team Member)
- **9 Gift Recommendations**: Curated selections across multiple categories (Tech, Gourmet Food, Office Accessories, Art Supplies, etc.)
- **Interactive Dashboard**: Filter by category, sort by price, expand gift details
- **Budget Tracking**: Visual progress bars showing budget utilization
- **Policy Compliance**: Each gift includes compliance rationale
- **Email Integration**: Pre-filled email templates for gift notifications
- **Responsive Design**: Works on desktop and mobile devices
- **Holiday Theming**: Animated snowflakes and festive color scheme
### Available Versions
- **index.html**: Version selector landing page
- **index_v1.html**: Original dashboard with traditional holiday colors (red/green)
- **index_v2.html**: H2O.ai branded version with company colors (yellow/black)
##  How We Built It
This project was created using **h2oGPTe** from H2O.ai, accessible as a free trial at [genai.h2o.ai](https://genai.h2o.ai) .
### Build Process
This dashboard was built iteratively using h2oGPTe with a series of carefully crafted prompts. The process started with exploration of structured JSON outputs, then moved to policy-compliant gift recommendations, and finally to the interactive dashboard.
#### Exploration Phase: Testing JSON Output
Before building the gift dashboard, we tested h2oGPTe's ability to generate structured JSON with a simpler use case:
```
I'm planning a holiday party for 15 people with a $300 budget.
Can you help me create a complete party plan including:
- Budget breakdown (food, drinks, decorations, entertainment)
- 3 easy appetizer recipes
- A shopping list
- A timeline for party prep
Make it festive and fun for a Christmas theme!
```
Then refined to structured output:
```
Perfect! Now regenerate that party plan as a JSON object with this schema:
{
 "party_details": {
  "theme": "string",
  "guest_count": number,
  "total_budget": number
 },
 "budget_breakdown": {
  "food": number,
  "drinks": number,
  "decorations": number,
  "entertainment": number
 },
 "recipes": [
  {
   "name": "string",
   "servings": number,
   "prep_time_minutes": number,
   "ingredients": ["string"],
   "instructions": "string"
  }
 ],
 "shopping_list": {
  "category": ["string"]
 },
 "timeline": [
  {
   "task": "string",
   "when": "string",
   "duration_minutes": number
  }
 ]
}
Output ONLY the JSON, no extra text.
```
This exploration validated h2oGPTe's capability to produce structured data before moving to the main project.
#### Step 0: System Prompt Configuration
First, we configured the AI agent with specific rules and RAG (Retrieval-Augmented Generation) capabilities:
```
System Prompt:
You are an AI Agent that must follow these rules:
1. Always use rag_text to retrieve relevant information from the attached document collection before answering.
2. Base your answers on the retrieved content and cite alignment or conflicts clearly.
3. When budgets or constraints are provided, enforce them strictly.
4. When asked for structured output, return valid JSON matching the schema exactly.
5. When providing recommendations, include:
   - gift_name
   - price
   - category
   - reason
   - policy_alignment
6. If any requested action violates the policies in the documents, do not proceed; suggest compliant alternatives.
7. Think step by step and use explicit reasoning.
```
**Document Upload**: Company policy document uploaded for RAG:
- `https://triagelogic.com/wp-content/uploads/2018/06/Company-Policy-and-Procedure-June-1.18-V6.0.pdf`
#### Step 1: Initial Requirements - Gift Recommendations
```
I need to find appropriate holiday gifts for 3 different people:
1. A colleague who loves tech gadgets (budget $40-70)
2. A senior client who wants thoughtful, professional gifts (budget $80-120)
3. A new team member who enjoys cooking and creative hobbies (budget $25-50)
Please:
- Use my company policy guidelines from our RAG collection
- Follow the budget rules strictly
- For each person, give 3 gift options
- Include JSON output with:
  - gift_name
  - price
  - category
  - reason
  - policy_alignment
Make sure recommendations do not violate any company rules. If there are no
Gift-Giving Guidelines in this document, please let me know, I will provide
to you another updated one.
```
#### Step 2: HTML Dashboard Creation
```
I previously asked you to find appropriate holiday gifts for 3 different
people with specific budgets and constraints. Now I need you to create an
interactive HTML Gift Recommendation Dashboard to visualize those
recommendations.
ORIGINAL GIFT REQUEST:
I need to find appropriate holiday gifts for 3 different people:
1. A colleague who loves tech gadgets (budget $40-70)
2. A senior client who wants thoughtful, professional gifts (budget $80-120)
3. A new team member who enjoys cooking and creative hobbies (budget $25-50)
Please:
- Use my company policy guidelines from our RAG collection
- Follow the budget rules strictly
- For each person, give 3 gift options
- Include JSON output with:
  - gift_name
  - price
  - category
  - reason
  - policy_alignment
Make sure recommendations do not violate any company rules.
NOW CREATE AN HTML APP:
Build a single HTML file with embedded CSS and JavaScript that displays:
1. HEADER SECTION:
   - Title: "Holiday Gift Recommendations Dashboard"
   - Subtitle: "Policy-Compliant Gift Guide"
   - Holiday theme (festive colors)
2. RECIPIENT CARDS (3 cards):
   Each card should show:
   - Recipient profile (colleague/client/team member)
   - Their interests (tech gadgets / professional / cooking & creative)
   - Budget range
   - 3 gift recommendations displayed as styled boxes
3. EACH GIFT RECOMMENDATION SHOULD SHOW:
   - Gift name (bold, prominent)
   - Price (large, highlighted)
   - Category badge (styled pill/tag)
   - Reason for recommendation (2-3 sentences)
   - Policy compliance indicator (✅ green checkmark + "Policy Compliant")
   - Visual separator between gifts
4. BUDGET TRACKER:
   - Show budget used vs. budget available for each recipient
   - Visual progress bar for each person
   - Color-coded (green if within budget, red if over)
5. FILTERING/INTERACTION (Optional but nice):
   - Filter by category (tech, professional, creative, etc.)
   - Sort by price (low to high, high to low)
   - Click gift to expand details
6. STYLING REQUIREMENTS:
   - Festive holiday theme (red, green, gold, white colors)
   - Professional corporate look (not too playful)
   - Christmas/winter decorations (snowflakes, subtle patterns)
   - Responsive design (works on mobile/tablet/desktop)
   - Cards with shadows, rounded corners
   - Modern, clean typography
   - Good spacing and hierarchy
7. LAYOUT:
   - Cards displayed in grid (3 columns on desktop, 1 column on mobile)
   - Each recipient card is visually distinct
   - Gift options clearly grouped under each recipient
   - Easy to scan and compare
8. ADDITIONAL FEATURES:
   - Print-friendly version
   - Summary section showing total budget across all recipients
   - Policy compliance summary (all gifts compliant badge)
   - Export as PDF button (optional, can be print)
9. JSON DATA STRUCTURE:
   Use this format internally:
   {
    "recipients": [
     {
      "name": "Colleague - Tech Enthusiast",
      "interests": "tech gadgets",
      "budget_min": 40,
      "budget_max": 70,
      "gifts": [
       {
        "gift_name": "...",
        "price": 55,
        "category": "Tech",
        "reason": "...",
        "policy_alignment": "Compliant - within gift value limits"
       }
      ]
     }
    ]
   }
10. INTERACTIVITY:
  - Hover effects on gift cards
  - Click to expand/collapse gift details
  - Smooth animations
  - Budget bar animates on page load
OUTPUT:
Complete, working HTML file with embedded CSS and JavaScript.
Include sample gift recommendations based on company policy guidelines (or
 generic professional gift policies if no specific RAG data available).
Make it beautiful, professional, and festive!
```
#### Step 3: Interactive Features & Email Integration
```
Modify the HTML so that I can click on the option, one choice per column/
individual, so that when the gift is selected the budget used updates with
the price of that product/gift only, and there is a button in addition,
where you can click after selection, to forward in an email where you need
to inform the email address and the name of the person, object plus
description about Happy Holidays, here is your gift card, thank you!
Open the generated email writing to Google account directly, and instead
of the original colors use my company branding kit that you can find here:
https://h2o.ai/company/brand-kit/
```
This final prompt added:
- **Radio button selection** for one gift per recipient
- **Dynamic budget tracking** that updates on selection
- **Email modal** with form fields for recipient name and email
- **Gmail integration** using Gmail compose URLs
- **H2O.ai branding** (yellow/black color scheme)
### Tools and Technologies
- **AI Platform**: h2oGPTe (H2O.ai's enterprise generative AI)
- **RAG Integration**: Document upload and retrieval for policy compliance
- **Frontend**: Pure HTML5, CSS3, JavaScript (no frameworks required)
- **Email Integration**: Gmail API URLs and mailto: protocol
- **Design Pattern**: Single-page application with embedded data
- **Animation**: CSS keyframes for snowflakes and transitions
### Key Learnings from the Build Process
1. **Iterative Prompting Works Best**: Started with simple JSON generation, then moved to complex HTML/CSS/JS generation
2. **RAG for Compliance**: Uploading policy documents enabled the AI to generate compliant recommendations automatically
3. **Specificity Matters**: Detailed requirements (10-point list) produced better results than vague requests
4. **Branding on Demand**: AI could adapt the entire color scheme by referencing a brand kit URL
5. **Single-File Apps**: h2oGPTe excels at generating complete, self-contained HTML applications
6. **Context Retention**: The AI remembered previous conversation context when adding features (email integration)
## Getting Started
### Running the Dashboard
1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd holiday-company-gift-card-agents-demo
   ```
2. Open in a web browser:
   ```bash
   # Option 1: Direct file open
   open index.html  # macOS
   start index.html  # Windows
   xdg-open index.html  # Linux
   # Option 2: Local server (recommended)
   python3 -m http.server 8000
   # Then navigate to http://localhost:8000
   ```
3. Select a version:
   - **Version 1**: Traditional holiday theme
   - **Version 2**: H2O.ai branded theme
### Using the Dashboard
1. **Review Recipients**: Each card shows recipient interests and budget range
2. **Explore Gifts**: Click any gift card to expand and see full details
3. **Select Gifts**: Use radio buttons to select one gift per recipient
4. **Track Budget**: Watch the progress bars update as you make selections
5. **Send Notifications**: Once all gifts are selected, click "Send Gift Notifications"
6. **Review Emails**: Pre-filled Gmail windows will open for each recipient
## Customization
### Modifying Gift Data
Edit the `giftData` object in the JavaScript section of any HTML file:
```javascript
const giftData = {
    "policy_info": {
        "policy_name": "Your Policy Name",
        "policy_number": "Policy Number",
        "limit": "Your Limit",
        "company": "Your Company"
    },
    "recipients": [
        // Add or modify recipients here
    ]
};
```
### Changing Colors
Update the CSS variables in the `<style>` section for quick color changes.
### Adding Recipients
Extend the `recipients` array in the `giftData` object with new recipient profiles.
## Compliance Features
- **Budget Limits**: Hard-coded $300 AUD limit per DIAB Engineering policy
- **Policy Alignment**: Each gift includes compliance rationale
- **Transparency**: All gift values and justifications visible
- **Audit Trail**: Email notifications include policy reference
- **Consumable Preference**: System favors consumable gifts to reduce obligation perception
## Browser Compatibility
- Chrome/Edge (recommended)
- Firefox
- Safari
- Modern mobile browsers
## Acknowledgments
- Built with **h2oGPTe** from H2O.ai ([genai.h2o.ai](https://genai.h2o.ai))
- Gift recommendations generated by AI agents
- Policy compliance based on DIAB Engineering's Anti-Bribery and Corruption Policy (MGT-POL-001-009 Rev06)
---
**Note**: This is a demonstration project for educational purposes. Always consult your organization's legal and compliance teams when implementing gift-giving programs.

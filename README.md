# Holiday Company Gift Card Agents Demo

A demonstration project showcasing an AI-powered Holiday Gift Recommendations Dashboard built using **h2oGPTe** (H2O.ai's enterprise generative AI platform). This project demonstrates how AI agents can help companies select policy-compliant, thoughtful gifts for employees and clients during the holiday season.

## Presentation Slides (PDF)

To view and download the presentation slides, use the link below. The file opens directly in your browser or can be downloaded for offline use:

https://raw.githubusercontent.com/Andreea-Turcu/holiday-company-gift-card-agents-demo/main/Presentation%20Slides%20-%20Create%20Your%20Own%20AI%20Agent%20with%20h2oGPTe.pdf

You can also view the live demo here:  
https://andreea-turcu.github.io/holiday-company-gift-card-agents-demo/

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

## How We Built It

This project was created using **h2oGPTe** from H2O.ai, accessible as a free trial at [genai.h2o.ai](https://genai.h2o.ai).

### Build Process

This dashboard was built iteratively using h2oGPTe with a series of carefully crafted prompts. The process started with exploration of structured JSON outputs, then moved to policy-compliant gift recommendations, and finally to the interactive dashboard.

Below, you will find the exact prompts used, along with the slide number where each prompt appears in the presentation deck.

#### Exploration Phase: Testing JSON Output

(Slide 17)

Before building the gift dashboard, we tested h2oGPTe's ability to generate structured JSON with a simpler use case:

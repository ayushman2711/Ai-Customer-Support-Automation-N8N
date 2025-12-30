# AI-Powered Customer Support Automation using n8n

## Project Overview
This project is an AI-powered customer support automation system built using **n8n** and **OpenAI**.  
A single workflow handles both customer feedback and customer support queries through conditional routing.

Based on user input, the workflow dynamically follows different processing paths while sharing common components such as form input, notifications, and data storage.

---

## Workflow Design
The entire system is implemented as a single n8n workflow containing two logical flows:

1. Feedback Flow  
2. Query Flow  

Routing is performed using an IF node based on the selected support type.

---

## Feedback Flow
Triggered when the user selects **Support Type = Feedback**.

Process:
- Capture customer feedback through a public form
- Perform sentiment analysis using an OpenAI LLM
- Generate an AI-based acknowledgment message
- Send response via Email and WhatsApp (sandbox environment)
- Store feedback details in Google Sheets for tracking and analysis

Purpose:
- Analyze customer sentiment
- Collect structured feedback
- Reduce manual review effort

---

## Query Flow
Triggered when the user selects **Support Type = Query**.

Process:
- Capture customer support queries
- Generate a direct AI-based response without sentiment analysis
- Send the solution via Email and WhatsApp
- Log query details in Google Sheets

Purpose:
- Automate responses to common customer questions
- Reduce response time
- Improve customer experience

---

## High-Level Architecture

Customer Form Submission  
→ Conditional Routing (IF Node)  
→ Feedback Flow or Query Flow  
→ AI Processing (OpenAI)  
→ Email and WhatsApp Notification  
→ Google Sheets Logging  

---

## Technologies Used
- n8n – Workflow automation and orchestration  
- OpenAI API – Sentiment analysis and response generation  
- Google Sheets – Data storage and logging  
- Gmail Node – Email notifications  
- Twilio WhatsApp Sandbox – WhatsApp messaging for testing  

---

## How to Use
1. Import the workflow JSON file into n8n  
2. Configure required credentials (OpenAI, Gmail, Google Sheets, Twilio)  
3. Activate the workflow  
4. Share the public form URL  
5. Submit feedback or queries to trigger automation  

---

## Notes
- WhatsApp integration uses the Twilio Sandbox environment
- No production credentials are included in this repository
- This project demonstrates automation logic and AI integration, not production deployment

---

## Future Enhancements
- Retrieval-Augmented Generation (RAG) for FAQ handling
- Human escalation for negative feedback
- Database integration (PostgreSQL or MongoDB)
- Analytics dashboard for insights

---

## Author
Ayushman Sharma

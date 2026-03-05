# Day 2 & Day 3 – Agentic AI Workflows and Google Sheets Automation

This part of my learning journey focuses on understanding **Agentic AI workflows** and integrating real-world tools like Google Sheets with AI using n8n.

---

# Day 2 – Understanding Agentic AI Workflows

On Day 2, I explored how AI agents work when they interact with tools and external systems.

### Key Concepts Learned

**1. Illusion of Memory**
AI models do not truly remember previous interactions. Instead, previous messages are sent again as context to create the *illusion of memory*.

**2. Thinking / Reasoning**
LLMs can analyze instructions and determine the steps needed to complete a task.

**3. Chaining LLMs**
Multiple AI calls can be chained together where the output of one step becomes the input of another.

**4. Tools**
AI agents can use external tools (APIs, databases, spreadsheets) to fetch or update information.

**5. The Loop**
Agents may repeatedly think → act → observe until the task is completed.

### The Human Trap

One common mistake when working with AI agents is assuming the AI understands everything automatically.  
In reality, we must clearly define tools, prompts, and workflow structure.

---

# Day 3 – 1. Google Sheets Portfolio Automation

On Day 3, I built a practical workflow by integrating **Google Sheets** with an AI model in n8n.

### Workflow Objective

Automatically update the latest market price for stocks listed in a Google Sheet portfolio.

### Sheet Structure

| Ticker | Quantity | Price |
|------|------|------|
| TCS | 10 | |
| INFY | 5 | |
| RELIANCE | 3 | |

### Workflow Steps

1. Read stock data from Google Sheets.
2. Send the data to the AI agent.
3. Fetch the latest market price using an external market tool.
4. Update the price column in the sheet automatically.

---

# Workflow Architecture

```
Trigger
   ↓
Google Sheets (Read Portfolio Data)
   ↓
AI Agent (Groq Chat Model)
   ↓
Market Data Tool
   ↓
Google Sheets (Update Prices)
```

---
---
# Day 3  – 2. Email Automation – Read and Draft Replies

Learned how to automate email handling using n8n.

### Workflow Steps

1. Read incoming emails
2. Extract email content
3. Send the email context to an AI model
4. Generate a suggested reply
5. Save the response as an email draft

This automation helps in quickly generating reply drafts for incoming emails.

---
# What I Learned

- How AI agents interact with external tools
- How to read and update spreadsheet data automatically
- The structure of agentic AI workflows
- Automating email workflows
- How to design multi-step automation using n8n

---

# Tools Used

- n8n
- Groq Chat Model
- Google Sheets Integration
- External Market Data Tool
- Email Integration

---

# Next Learning Goals

- Automate workflows with scheduled triggers
- Connect automation with messaging platforms
- Build more real-world AI automation use cases

## snapshots
1. Google sheets portfolio automation
![Image](https://github.com/user-attachments/assets/b77cb684-34e8-4ee5-8426-d9fc026f4978)

2.  Email Automation – Read and Draft Replies
![Image](https://github.com/user-attachments/assets/2fb10b3a-6d40-4abe-b997-5464e7b6b05f)

![Image](https://github.com/user-attachments/assets/febc3248-6066-4c14-a2bc-5c21035b6858)

![Image](https://github.com/user-attachments/assets/6716af11-6baf-4dcb-8221-4d347c9ce575)

![Image](https://github.com/user-attachments/assets/da8d4009-5ea3-437f-bb0b-2e3ea9713270)

# 🤖 AI LinkedIn Content Automation with n8n, Gemini & Google Sheets

An AI-powered social media automation workflow built with **n8n**, **Google Gemini**, and **Google Sheets** that transforms research/source content into multiple LinkedIn post ideas and ready-to-publish LinkedIn posts.

The workflow reduces the manual effort involved in researching topics, developing content ideas, writing LinkedIn posts, and organizing the results in a content spreadsheet.

---

## 🚀 Project Overview

Creating consistent LinkedIn content manually can be time-consuming.

This workflow automates the content creation pipeline:

```text
Source Content
      ↓
AI Research / Content Analysis
      ↓
Generate 3 LinkedIn Post Ideas
      ↓
Generate LinkedIn Posts
      ↓
Structure Topic + Reference + Post
      ↓
Google Sheets
```

Instead of manually reading a long research document and deciding what to post, the workflow uses AI to identify useful topics and turn them into concise LinkedIn content.

---

## ✨ Key Features

- 🧠 AI-powered content analysis
- 💡 Generates multiple LinkedIn post ideas from one source
- ✍️ Generates LinkedIn-ready posts
- 🔎 Keeps posts grounded in the provided research
- #️⃣ Automatically adds relevant hashtags
- 📊 Stores generated content in Google Sheets
- 🔄 Designed for multi-item content processing
- ⚙️ Built using n8n workflow automation
- 🤖 Uses Google Gemini as the AI model

---

## 🛠️ Tech Stack

| Technology | Purpose |
| --- | --- |
| **n8n** | Workflow automation |
| **Google Gemini** | AI reasoning, research analysis and content generation |
| **Google Sheets** | Content storage and tracking |
| **Google APIs** | Connecting Gemini / Sheets services |

---

## 🔁 Workflow Architecture

The workflow consists of multiple AI-powered stages.

### 1. Source Content

The workflow receives a research document containing information about different AI developments, news, research papers, and technology trends.

Example source topics:

- AI in sports injury prediction
- AI-assisted mathematical research
- AI infrastructure
- AI regulation

### 2. Generate LinkedIn Post Ideas

The first AI stage analyzes the source material and produces **three different LinkedIn post ideas**.

Each idea contains:

```text
<topic>
<research>
```

The `research` section tells the next AI agent exactly which information from the source should be used to create the post. This prevents the second AI agent from having to analyze the entire source document again.

### 3. Generate LinkedIn Posts

The second AI stage receives the three ideas and their research instructions. It is instructed to generate:

- A strong hook
- A concise LinkedIn post
- Content based **only** on the provided research
- Relevant hashtags

Each result contains:

- `Topic`
- `Reference`
- `Post`

### 4. Handle Multiple Generated Items

A key part of the workflow is handling the fact that Gemini generates **three results, not one**.

The workflow needs to convert those three results into three separate n8n items before sending them to Google Sheets.

```text
Gemini
  ↓
3 generated posts
  ↓
Split / Loop over items
  ↓
Post 1 → Google Sheets
Post 2 → Google Sheets
Post 3 → Google Sheets
```

This prevents the common automation issue where only the first generated item is passed to the next node.

---

## 📊 Google Sheets Structure

The output spreadsheet uses three columns:

| Topic | Reference | Post |
| --- | --- | --- |
| LinkedIn post topic | Research/source reference | Final LinkedIn post |

Each generated idea creates one row:

```text
Row 1 → Topic 1 | Reference 1 | LinkedIn Post 1
Row 2 → Topic 2 | Reference 2 | LinkedIn Post 2
Row 3 → Topic 3 | Reference 3 | LinkedIn Post 3
```

---

## 🧩 Important Multi-Item Logic

One of the main automation challenges in this project was handling multiple AI-generated results.

An AI model may return three posts inside one response. Google Sheets, however, works most naturally when each row is represented as a separate n8n item.

The workflow can use either of two approaches.

### Approach 1 — Structured JSON

Instruct Gemini to return structured data such as:

```json
[
  {
    "Topic": "Topic 1",
    "Reference": "Research 1",
    "Post": "LinkedIn post 1"
  },
  {
    "Topic": "Topic 2",
    "Reference": "Research 2",
    "Post": "LinkedIn post 2"
  },
  {
    "Topic": "Topic 3",
    "Reference": "Research 3",
    "Post": "LinkedIn post 3"
  }
]
```

The JSON can then be parsed and converted into individual n8n items.

### Approach 2 — Loop Over Items

The workflow can also create three separate n8n items and process them one at a time:

```text
3 Items
   ↓
Loop Over Items
   ↓
Google Sheets
   ↓
Append Row
   ↓
Next Item
```

For every item, the workflow maps:

```text
Topic     → Topic column
Reference → Reference column
Post      → Post column
```

---

## 🎯 Why This Project Matters

The workflow demonstrates how AI can be used as part of a practical content production system rather than simply as a chatbot.

Instead of:

```text
Human → AI → Copy/Paste
```

the workflow creates:

```text
Research
   ↓
AI Analysis
   ↓
Content Ideas
   ↓
AI Writing
   ↓
Structured Data
   ↓
Google Sheets
```

This makes the process repeatable and scalable.

---

## ⚠️ Important Design Considerations

### AI output should remain grounded

The AI should be instructed not to introduce unrelated information or unsupported claims.

### Multiple outputs must be handled correctly

Generating three posts inside one AI response does not automatically mean Google Sheets will receive three rows. The workflow must explicitly convert the generated results into separate items.

### Structured output is preferable

Using predictable fields such as `Topic`, `Reference`, and `Post` makes downstream automation significantly easier.

### Human review is recommended

Before publishing content publicly, generated posts should be reviewed for factual accuracy, tone, and brand alignment.

---

## 📌 Example Use Case

A long research document contains four AI-related news stories. The workflow can transform it into:

```text
Research Document
        ↓
3 Content Angles
        ↓
3 LinkedIn Posts
        ↓
3 Google Sheet Rows
```

The resulting Google Sheet becomes a simple content library or content calendar that can later be connected to additional publishing or approval workflows.

---

## 🔮 Possible Future Improvements

- [ ] LinkedIn publishing
- [ ] Content scheduling
- [ ] Human approval before publishing
- [ ] Image generation
- [ ] Automatic content calendar creation
- [ ] Multiple social platforms
- [ ] Post performance tracking
- [ ] Engagement analytics
- [ ] Slack/Telegram approval notifications
- [ ] Duplicate-content detection

---

## 🏁 Conclusion

This project demonstrates an end-to-end approach to AI-assisted social media automation using n8n.

The key idea is simple:

> Turn unstructured research into structured, reusable social media content automatically.

By combining AI reasoning with workflow automation and Google Sheets, the process can move from manual content creation toward a repeatable content-generation pipeline.

---

## 📚 Inspiration / Related Work

The architecture follows patterns commonly used in AI-powered n8n social media workflows, including AI content generation, Google Sheets as a content store, structured output, and downstream publishing/approval workflows.

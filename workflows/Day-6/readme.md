# Voice Agent for Customer Support using ElevenLabs

This project explores building a voice-based AI customer support agent using ElevenLabs.

The goal was to create a system that can interact with users through voice, understand their queries, and route them to the appropriate support agent based on the type of request.

---

## Project Overview

The workflow simulates a customer support system for Apple products.

The system contains multiple voice agents responsible for different tasks, with a routing mechanism that directs user queries to the correct specialist agent.

---

## Knowledge Base

A knowledge base was created containing information about various Apple products such as:

- Apple Watch Series 11
- iPhone 13 Pro Max
- MacBook Pro M4

This knowledge base helps the agent understand and respond to customer queries more accurately.

---

## Agent Workflow

The system includes multiple agents working together:

### 1. Main Agent
This is the entry agent that starts the interaction with the user.

Responsibilities:
- Greets the customer
- Understands the user's issue
- Routes the request to the appropriate specialist agent

  ---

### 2. Product Support Agent

Handles Product questions related to products.

Example queries:
- Latest model
- Model price

---

### 3. Stock Specialist Agent

Handles product store in stock related queries.

Example queries:
- Stock products
- Prices in stock

---

## Routing Logic

The main agent routes conversations to the appropriate specialist using defined edges in the workflow.

Example routing logic:

- Product issue → Product Support Agent
- Stock related issues →  Stock Specialist  Agent

This allows the system to simulate a structured customer support environment.

---

## Key Learnings

Through this project I learned:

- How to build voice agents using ElevenLabs
- How to create and use a knowledge base
- How to structure multi-agent workflows
- How routing logic works in conversational AI systems

---

## Future Improvements

Next steps for this project include:

- Integrating ElevenLabs with n8n
- Automating workflows using voice triggers
- Expanding the knowledge base
- Connecting the agent with real-world APIs

## Snapshot
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/953ca440-f271-43d0-b6e6-e99d665067e5" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/876816e6-f036-482b-a6a1-1fb35b434103" />

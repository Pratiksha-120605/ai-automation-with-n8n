# Equity Portfolio Rebalancer

This project focuses on building an AI-powered workflow that analyzes and helps rebalance an equity investment portfolio.

The goal of this workflow is to automate portfolio analysis and provide suggestions on how to rebalance investments based on current holdings.

---

## Project Overview

Managing an equity portfolio manually can be time-consuming. This workflow demonstrates how automation tools can assist in analyzing portfolio data and generating insights.

The system reads portfolio data, processes it using AI, and generates suggestions for better allocation of assets.

---

## Workflow Architecture

The automation workflow follows these steps:

1. Read portfolio data from a data source (such as Google Sheets)
2. Analyze the current allocation of different stocks
3. Compare allocations with desired portfolio balance
4. Generate recommendations for rebalancing
5. Output the suggested adjustments

---

## Example Portfolio Data

| Ticker | Quantity | Price |
|------|------|------|
| TCS | 10 | 3500 |
| INFY | 5 | 1500 |
| RELIANCE | 3 | 2500 |
| HDFCBANK | 7 | 1600 |

The workflow processes this data to evaluate portfolio distribution.

---

## Key Features

- Automated portfolio analysis
- AI-assisted investment insights
- Integration with external data sources
- Workflow-based automation using n8n

---

## Tools Used

- n8n (workflow automation)
- AI model for analysis
- Google Sheets (portfolio data storage)

---

## Key Learnings

Through this project I learned:

- How to automate financial data workflows
- How to integrate AI into data analysis pipelines
- How to structure multi-step automation workflows
- How to process structured financial data using AI

---

## Future Improvements

Possible improvements for this project include:

- Live market price integration
- Automated portfolio performance tracking
- Risk analysis and diversification insights
- Integration with trading APIs

---

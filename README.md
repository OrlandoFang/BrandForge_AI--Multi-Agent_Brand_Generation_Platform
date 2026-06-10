#### [Presentation Slides](202605-26_slides.pdf)
#### [Demo Video](creative_ai_agent.mp4)
#### [Technical Report](202605-26.pdf)
#### [Github Repo](https://github.com/OrlandoFang/EECS6895_Startup_AI_Agents_Platform)
## Introduction 
Our project goal is to build an AI-powered design platform for early-stage startups, helping users quickly create a professional and cohesive visual identity without requiring significant time, budget, or design expertise.

The key innovation lies in combining multiple design capabilities into a single, coordinated system of AI agents that understand brand context and produce cohesive outputs across different formats. Instead of using fragmented tools or relying on manual design processes, users can go from idea to complete brand identity in minutes.

These toolkits are important because they turn design from a bottleneck into an accessible, on-demand capability. This allows startups to launch faster, present themselves more professionally, and compete more effectively, regardless of their budget or design experience.

## Dataset
This project utilizes two primary datasets: advertising performance benchmarks and platform-specific policy standards.

The performance data includes key metrics, such as CPC, CPM, CPA, CTR, and conversion rates, across platforms including Meta, TikTok, LinkedIn, YouTube, and Google Ads. These data were obtained from publicly available data sources such as WordStream and Digitopia. Date ranges from 2024 to 2025.

The policy corpus consists of official advertising guidelines for Meta, Google, TikTok, and LinkedIn, covering Prohibited Content, Restricted Categories, Quality Standards, etc. These data were scraped from each platform’s latest ad guideline websites.

## Language
TypeScript, Python, CSS

## Contributors
Tianrui Fang, Hao Chen, Tianyu Zhan

## Analytics
System modules include: a Brand Agent (GPT-4o extracts brand profile from text), a Logo Agent (SVG generation + DALL-E 3 image), a Marketing Agent (tool-using LLM with RAG), and a UI/Web Agent (two-step plan-then-generate for Tailwind landing pages), all orchestrated by an AI Gateway that fans out tasks concurrently via asyncio.gather and persists results to MongoDB.

Algorithms/analytics center on the Marketing Agent: an LLM router classifies user queries into execution plans, a platform chooser tool filters ad benchmark CSVs (CPC/CPM/CPA by industry and region) with fuzzy matching, and a RAG pipeline uses FAISS cosine-similarity search over sentence-transformer embeddings (all-MiniLM-L6-v2) to retrieve ad policy documents for cited answers.

Visualizations are delivered through a React dashboard with five pages: Brand Hub (color swatches, logo preview, website iframe), Web Architect (device-mockup preview), Logo Lab (SVG/PNG download), and Marketing Chat (rendered markdown strategy with charts via Recharts).

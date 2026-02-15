CrewAI Multi-Agent System with Local Mistral-7B (GGUF) using Python

This repository provides a complete and practical implementation of a multi-agent AI orchestration pipeline using CrewAI and Python, powered by a locally deployed open-source Large Language Model (LLM). Instead of relying on paid cloud APIs, this project integrates Mistral-7B Instruct (GGUF format) through llama-cpp-python, enabling a fully offline, secure, and cost-effective agent-based AI system.

The goal of this project is to demonstrate how multiple specialized AI agents can be designed with distinct roles and responsibilities, collaborate through sequential task execution, and generate structured outputs for real-world workflows such as market intelligence analysis and content strategy development.

📌 Project Overview

Modern AI systems are shifting from single-response chatbots to agentic AI architectures, where multiple AI agents work together like a team of experts. This repository implements a two-agent CrewAI framework, where each agent is responsible for a dedicated task and contributes to the final strategy output.

The project simulates a real business scenario:

One agent performs competitor research and summarizes market strategies.

Another agent uses the research to generate a structured content marketing plan.

This design represents a scalable foundation for advanced automation pipelines in business intelligence, research, and AI-driven decision-making.

🧠 Key Features

✅ Multi-Agent Collaboration using CrewAI
✅ Offline Local LLM Integration (No OpenAI API required)
✅ Uses Mistral-7B Instruct GGUF model
✅ Task dependency workflow using CrewAI depends_on
✅ Lightweight and efficient execution using llama-cpp-python
✅ Fully customizable agents with roles, goals, and backstories
✅ Transparent execution with verbose agent reasoning output

🏗️ System Architecture

The workflow is designed as a sequential agent pipeline:

Agent 1: Market Research Analyst

Role: Competitive intelligence expert

Task: Identify top competitors and summarize their marketing strategies

Output: Structured competitor strategy report

Agent 2: Content Strategist

Role: Marketing and storytelling strategist

Task: Generate a content strategy based on competitor insights

Output: A complete marketing plan document

Crew Orchestration

The Crew object manages:

task scheduling

agent coordination

dependency execution

final output compilation

📂 Repository Workflow
Step 1: Load Local LLM (Mistral-7B GGUF)

The model is loaded using llama-cpp-python:

Runs locally on CPU (or GPU if configured)

Supports quantized GGUF model formats

Works efficiently on consumer hardware

Step 2: Create a Custom LLM Wrapper

CrewAI expects an LLM object with a .complete(prompt) interface.
This project builds a wrapper around the local model to make it compatible.

Step 3: Define Agents

Agents are defined with:

role

goal

backstory

model access

This provides stronger context alignment and improves output quality.

Step 4: Define Tasks

Each agent is assigned a task.
Task dependencies ensure the content strategist only executes after competitor analysis is completed.

Step 5: Execute Crew Pipeline

Finally, the crew is executed using:

result = crew.kickoff()

⚙️ Installation

Make sure Python 3.9+ is installed.

Install the required dependencies:

pip install crewai llama-cpp-python transformers accelerate langchain

📥 Model Download

This project uses Mistral-7B Instruct GGUF.

Download the model file:

📌 mistral-7b-instruct.Q4_K_M.gguf

Then place it inside the models/ folder:

./models/mistral-7b-instruct.Q4_K_M.gguf

▶️ Running the Project

Once the model is placed correctly, run the script:

python main.py


Expected output includes:

competitor summaries

final content strategy document

verbose agent execution logs

🧪 Example Output (Simplified)
Competitor Summary (Agent 1)

Competitor A: SEO-focused long blogs

Competitor B: Influencer marketing via TikTok

Competitor C: Webinars + whitepapers

Content Strategy (Agent 2)

Keyword-driven blogging plan

Influencer collaboration roadmap

Quarterly webinars for authority building

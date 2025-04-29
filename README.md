## PainPoint Market Research Agent

# Overview

PainPoint_Market_Research_Agent is a hands-on workshop and reference implementation for building a multi-turn, stateful market research chatbot using large language models (LLMs) and LangGraph. The notebook guides you through:

Setting up API keys and dependencies

Defining external "tools" (e.g., Perplexity search)

Configuring and instantiating an LLM (Gemini / OpenAI)

Implementing conversational "nodes" for structured data collection, research, analysis, and reporting

Writing flow-control logic to orchestrate multi-stage conversations

Assembling everything into a connected graph using LangChain's StateGraph

Running an interactive demo in the command line

Prerequisites

Python 3.8+

Access to the following API keys:

GEMINI_API_KEY (for Google Gemini LLM)

OPENAI_API_KEY (optional, to use OpenAI models)

(Optionally) Perplexity API credentials if using the Perplexity tool

Install dependencies via pip:

pip install -r requirements.txt

Dependencies include:

langchain

openai and/or google-generative-ai

perplexity-client

rich

Installation & Configuration

Clone the repository:



git clone https://github.com/your-org/PainPoint_Market_Research_Agent.git
cd PainPoint_Market_Research_Agent


2. **Set up environment variables**:
   Create a `.env` file in the project root with:
   ```dotenv
   GEMINI_API_KEY=your_gemini_key_here
   OPENAI_API_KEY=your_openai_key_here

Verify your keys in PainPoint_Market_Research_Agent.ipynb or in your execution environment:

from userdata import get
assert get("GEMINI_API_KEY")
assert get("OPENAI_API_KEY")

## Usage

# Notebook Workflow

Open PainPoint_Market_Research_Agent.ipynb in Jupyter Lab or VS Code.

Run cells sequentially to configure APIs, define tools, and build your conversational flow.

Inspect intermediate states and prompts to understand how each node operates.

Command-Line Demo

After building the graph, launch the interactive demo:

python run_agent.py

or, if using the notebook:

# In a Jupyter cell:
from agent import run_command_line
run_command_line()

Interact with the chatbot by describing a business or market pain point. Type exit to quit or new topic to restart the conversation flow.

Project Structure

├── README.md                      # This file
├── requirements.txt               # Python dependencies
├── PainPoint_Market_Research_Agent.ipynb  # Workshop notebook
├── agent.py                       # Command-line execution script
├── tools/                         # Optional: additional tool definitions
└── utils/                         # Rate-limiter, state definitions, etc.

Contributing

Contributions welcome! Feel free to:

Add new tools (e.g., sentiment analysis, data lookup)

Experiment with different LLM providers

Enhance flow-control logic or error handling

Integrate LangSmith for debugging and traceability

Please open issues or submit pull requests against the develop branch.

License

This project is licensed under the MIT License. See LICENSE for details.

Acknowledgements & Next Steps

Built with ❤️ using LangChain and Google Gemini

Inspired by Google Developer Club's MedicalAgent for prompt engineering and stateful LLM orchestration

Next ideas:

Persist conversation state in a database

Add web dashboard or Slack integration

Deploy as a serverless function or microservice

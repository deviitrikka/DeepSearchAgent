# 🔍 Deep Research AI Agentic System

[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![LangChain](https://img.shields.io/badge/LangChain-Latest-green.svg)](https://python.langchain.com/)
[![LangGraph](https://img.shields.io/badge/LangGraph-Latest-orange.svg)](https://python.langchain.com/docs/langgraph)
[![Groq](https://img.shields.io/badge/Groq-LLM-purple.svg)](https://groq.com/)

A powerful multi-agent system for comprehensive research and information synthesis using LangChain, LangGraph, and multiple data sources.

## 🌟 Features

- **Dual-Agent Architecture** - Research Agent + Answer Drafting Agent
- **Multiple Data Sources** - Tavily Search, ArXiv, and Wikipedia
- **Intelligent Synthesis** - Turn raw research data into coherent answers
- **Customizable Parameters** - Configure research depth and model selection

## 🏗️ System Architecture

```
      +-----------+
      | __start__ |
      +-----------+
            *
            *
            *
    +----------------+
    | research_agent |
    +----------------+
            *
            *
            *
+-----------------------+
| answer_drafting_agent |
+-----------------------+
            *
            *
            *
       +---------+
       | __end__ |
       +---------+
```

1. **Research Agent** crawls websites and databases to gather relevant information on the query
2. **Answer Drafting Agent** processes the research data and generates a comprehensive, coherent response

## 📋 Requirements

- Python 3.9+
- Required packages:
  - langchain-community
  - langchain-groq
  - langgraph
  - python-dotenv
  - arxiv
  - pymupdf
  - wikipedia

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/deep-research-ai.git
cd deep-research-ai
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Set up API keys

Create a `.env` file in the project root with the following content:

```
TAVILY_API_KEY=your_tavily_api_key
GROQ_API_KEY=your_groq_api_key
```

You'll need to sign up for:
- [Tavily](https://tavily.com/) - For web search capabilities
- [Groq](https://groq.com/) - For fast LLM inference

### 4. Run the Jupyter notebook or Streamlit app

```bash
# For the notebook
jupyter notebook main.ipynb

# For the Streamlit app (if available)
streamlit run research_app.py
```

## 📊 Sample Usage

Here's an example of using the research system:

```python
from langchain_core.messages import HumanMessage

# Initialize the research system
messages = graph.invoke({
    "messages": "What are the latest developments in quantum computing?"
})

# Display the results
for message in messages["messages"]:
    message.pretty_print()
```

## 🔄 How It Works

1. **Query Input**: The system takes a research query from the user
2. **Research Phase**: The Research Agent uses Tavily, ArXiv, and Wikipedia to gather information
3. **Processing Phase**: The Answer Drafting Agent analyzes and synthesizes the research data
4. **Response Generation**: A comprehensive, well-structured answer is generated and presented to the user

## 🎛️ Customization Options

You can customize the system behavior by modifying:

- **Model Selection**: Choose between different Groq models (llama3-8b-8192, mixtral-8x7b-32768)
- **Research Tools**: Add or remove research tools to fit your needs
- **Max Results**: Adjust how many results each tool returns
- **Agent Prompts**: Customize how each agent processes information

## 📷 Example Output

For the query "Tell me recent news on quantum computing", you might get a response like:

```
Quantum computing has been rapidly advancing with several key developments:

1. Microsoft recently invested in building topological quantum computers, joining Google and IBM in the race to implement quantum computing solutions.

2. Researchers Lior Eldar and Peter Shor have claimed a breakthrough with a polynomial-time quantum algorithm for the Closest Vector Problem in lattices.

3. Microsoft has unveiled Majorana 1, described as the world's first quantum processor powered by topological qubits.

4. MIT researchers have made progress on quantum systems-on-chip, enabling efficient control of large qubit arrays.

5. New advancements in arranging atoms in extremely close proximity are opening possibilities for exploring exotic states of matter.
```

## 💡 Future Enhancements

- Add fact-checking capabilities with a third agent
- Implement citation and source tracking
- Add support for more research tools
- Create a persistent research memory

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- [LangChain](https://python.langchain.com/) for the agent framework
- [Tavily](https://tavily.com/) for the research search API
- [Groq](https://groq.com/) for the LLM inference

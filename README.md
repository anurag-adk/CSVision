[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/anurag-adk/CSVision/blob/main/CSVision.ipynb)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![LangChain](https://img.shields.io/badge/LangChain-Framework-green.svg)](https://langchain.com/)
[![Gemini AI](https://img.shields.io/badge/Gemini-AI-purple.svg)](https://ai.google.dev/)

# CSVision - An AI Agent for Company Info Extraction

## 📌 Project Overview

An intelligent AI agent built with LangChain and Google Gemini that extracts company information from textual essays and generates structured CSV output. This project demonstrates the implementation of LCEL Runnable Interface, Tools, Tool Calling and Agentic workflows.

## 🚀 Features

- **Structured Data Extraction**: Extract company names, founding dates and founders from text
- **AI Agent Workflow**: Autonomous agent using ReAct pattern with tool calling
- **Multiple Extraction Methods**: Both agent-based and direct structured extraction
- **Smart Date Formatting**: Handles various date formats with intelligent defaults
- **CSV Generation**: Automated output in specified format
- **Streaming Capabilities**: Real-time processing feedback
- **Error Handling**: Robust error management throughout the pipeline
- **Batch Processing**: Individual paragraph processing for large texts

## 🔧 Requirements

- Python 3.8 or higher
- Google Gemini API Key
- Required packages (see installation)

## ⚙️ Setup and Installation

### 📝 Google Colab (Recommended)

1. **Open the project with Google Colab**:

   - Visit [Google Colab](https://colab.research.google.com/github/anurag-adk/CSVision/blob/main/CSVision.ipynb)

2. **Make your own copy**:

   - Once the notebook opens, click **"File"** → **"Save a copy in Drive"**
   - This creates your personal copy that you can edit and run

3. **Get your Google Gemini API Key**:

   - Visit [Google AI Studio](https://aistudio.google.com/)
   - Sign in with your Google account
   - Click **"Get API key"** → **"Create API key in new project"**
   - Copy your API key

4. **Set up your API key in Colab**:

   - Go to the 🔑 **Secrets** tab in the left sidebar of your Colab notebook
   - Add a new secret named `GEMINI_API_KEY`
   - Paste your API key as the value
   - Enable notebook access by toggling the switch

5. **Run the notebook**:
   - The required packages will be installed automatically in the first cell
   - Execute cells step by step to see the AI agent in action!
   - Watch as it extracts company information and generates a CSV file

### 💻 Local Machine

1. **Clone the repository and install dependencies:**

   ```bash
   git clone https://github.com/anurag-adk/CSVision
   cd CSVision
   pip install langchain-google-genai langchain langgraph pandas pydantic -qU
   ```

2. **Set up environment variables**:

   ```bash
   export GOOGLE_API_KEY=your_gemini_api_key
   ```

## 🎯 Core Components

| Component             | Description                     | Technology            |
| --------------------- | ------------------------------- | --------------------- |
| **Structured Output** | Type-safe data extraction       | Pydantic Models       |
| **Tools**             | Custom extraction and CSV tools | `@tool` decorator     |
| **Agent**             | Autonomous task execution       | LangGraph ReAct Agent |
| **Date Processing**   | Smart date format handling      | Custom regex logic    |
| **CSV Generation**    | Automated file output           | Pandas DataFrame      |

## 🧠 AI/ML Concepts Implemented

### 1. LCEL Runnable Interface

- **Structured Output Chains**: Using `llm.with_structured_output()` for type-safe extraction
- **Chain Composition**: Building processing pipelines with LangChain components

### 2. Tools and Tool Calling

- **Custom Tools**: Extraction and CSV generation tools using `@tool` decorator
- **Agent Integration**: Tools accessible by AI agent for autonomous execution

### 3. Agentic Workflow

- **ReAct Pattern**: Reasoning and Acting agent for complex task execution
- **Tool Orchestration**: Intelligent selection and usage of available tools
- **Message-based Communication**: Structured interaction using HumanMessage/AIMessage

### 4. Structured Data Extraction

```python
class CompanyInfo(BaseModel):
    company_name: str = Field(..., description="The full official company name")
    founding_date: str = Field(..., description="The founding date")
    founders: List[str] = Field(..., description="List of founder names")
```

### 5. Error Handling & Validation

- **Input Validation**: Robust error checking for all inputs
- **Graceful Degradation**: Fallback mechanisms for edge cases
- **User-friendly Messages**: Clear error communication

## 🤖 Processing Workflow

1. **Text Input**: Essay or paragraph containing company information
2. **AI Analysis**: LLM analyzes text and identifies company mentions
3. **Structured Extraction**: Pydantic models ensure type-safe data extraction
4. **Date Processing**: Smart formatting handles various date formats
5. **CSV Generation**: Automated creation of properly formatted output
6. **Validation**: Quality checks and error handling throughout

## ⚡Advanced Features

### 🔄 Multiple Processing Approaches

- **Agent-based**: Autonomous execution with tool calling
- **Direct Extraction**: Structured output without agent overhead
- **Paragraph Processing**: Individual chunk processing for large texts

### 📅 Smart Date Handling

- **Partial Dates**: Year-only formats default to January 1st
- **Natural Language**: "May 8, 1886" → "1886-05-08"
- **Format Standardization**: All outputs in YYYY-MM-DD format

### 📈 Streaming Capabilities

- **Real-time Feedback**: Live processing updates
- **Interactive Analysis**: Stream-based text analysis
- **Progress Monitoring**: Visual feedback during long operations

## 🙏 Acknowledgments

_A Special Thank You To Our Mentors and Facilitators at Leapfrog especially Kalash Shrestha dai_

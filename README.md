# Calculator MCP Server

A beginner-friendly **Model Context Protocol (MCP) Server** built using **Python** and **FastMCP**. This project exposes calculator operations as MCP tools and demonstrates how AI applications such as Cursor can discover and invoke custom tools through the MCP standard.

---

## Overview

Large Language Models (LLMs) are excellent at reasoning and generating text, but they cannot directly access custom code, databases, APIs, or local applications.

The **Model Context Protocol (MCP)** solves this problem by providing a standardized way for AI applications to communicate with external tools.

This project implements a simple calculator as an MCP server to demonstrate:

* MCP Server Creation
* Tool Registration
* Tool Discovery
* Tool Invocation
* Cursor Integration
* Python-based MCP Development

Although a calculator is a simple example, the same architecture can later be extended to:

* PDF Readers
* Document Summarizers
* Database Query Systems
* File Management Tools
* AI Agents
* Custom Enterprise Applications

---

# Features

The server currently exposes the following tools:

| Tool          | Description               |
| ------------- | ------------------------- |
| add()         | Adds two numbers          |
| subtract()    | Subtracts two numbers     |
| multiply()    | Multiplies two numbers    |
| divide()      | Divides two numbers       |
| power()       | Calculates exponentiation |
| square_root() | Calculates square roots   |

---

# Tech Stack

* Python
* MCP SDK
* FastMCP
* Cursor IDE
* Git & GitHub

---

# Project Structure

```text
calculator-mcp-server/
│
├── server.py
├── requirements.txt
├── README.md
├── .gitignore
│
└── venv/
```

---

# How MCP Works

Traditional workflow:

```text
User
 ↓
Cursor AI
 ↓
LLM calculates answer
 ↓
Response
```

MCP workflow:

```text
User
 ↓
Cursor AI
 ↓
MCP Client
 ↓
Calculator MCP Server
 ↓
Tool Execution
 ↓
Result
 ↓
Cursor Response
```

---

# MCP Architecture

```text
+----------------+
|     User       |
+----------------+
         |
         v
+----------------+
|    Cursor AI   |
+----------------+
         |
         v
+----------------+
|  MCP Client    |
+----------------+
         |
         v
+----------------------+
| Calculator MCP Server|
+----------------------+
    |    |    |    |
    v    v    v    v
  add subtract multiply divide
```

---

# Installation

## Clone Repository

```bash
git clone https://github.com/your-username/calculator-mcp-server.git
cd calculator-mcp-server
```

## Create Virtual Environment

```bash
python -m venv venv
```

Activate:

### Windows

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
source venv/bin/activate
```

## Install Dependencies

```bash
pip install mcp
```

or

```bash
pip install -r requirements.txt
```

---

# Running the MCP Server

```bash
python server.py
```

The server will start and wait for MCP client connections.

---

# Cursor Integration

This project was tested using Cursor IDE.

## Step 1: Open Cursor

Navigate to:

```text
Settings → Tools & MCP
```

Click:

```text
Add Custom MCP
```

---

## Step 2: Configure MCP Server

Add the following configuration:

```json
{
  "mcpServers": {
    "calculator": {
      "command": "C:/path/to/venv/Scripts/python.exe",
      "args": [
        "C:/path/to/server.py"
      ]
    }
  }
}
```

Replace the paths with your actual project paths.

Example:

```json
{
  "mcpServers": {
    "calculator": {
      "command": "C:/Users/Asus/OneDrive/Desktop/mcp/venv/Scripts/python.exe",
      "args": [
        "C:/Users/Asus/OneDrive/Desktop/mcp/server.py"
      ]
    }
  }
}
```

Save the configuration and restart Cursor.

---

## Step 3: Verify Connection

Navigate to:

```text
Settings → Tools & MCP
```

You should see:

```text
calculator
Connected
```

along with all registered tools.

---

# Example Usage in Cursor

Prompt:

```text
Use the add tool to calculate 45 + 67
```

Cursor automatically invokes:

```python
add(45, 67)
```

Response:

```text
112
```

---

Prompt:

```text
Use the multiply tool to calculate 23 × 7
```

Cursor invokes:

```python
multiply(23, 7)
```

Response:

```text
161
```

---

# Why Build a Calculator MCP?

A calculator is not the end goal.

Cursor can already perform arithmetic internally.

This project serves as a learning example to understand:

* MCP Protocol
* Tool Registration
* Tool Discovery
* AI Tool Calling
* Cursor Integration

The same concepts can later be used for much more powerful systems.

Examples:

```text
extract_pdf()
summarize_document()
query_database()
send_email()
manage_assignments()
```

---

# Future Enhancements

* Scientific Calculator Tools
* Factorial Calculation
* Trigonometric Functions
* Logarithmic Functions
* Prime Number Checker
* Database Integration
* REST API Integration

---

# Learning Outcomes

By completing this project, I learned:

* Fundamentals of MCP
* FastMCP Server Development
* Tool Registration using Decorators
* AI Tool Discovery
* Cursor MCP Configuration
* GitHub Project Management
* Python-based AI Tool Integration

---

# License

This project is intended for educational and learning purposes.

MIT License.


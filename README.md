# local-mcp-server

A professional, local Model Context Protocol (MCP) server designed for effortless expense tracking. This server enables AI assistants to interact directly with a local SQLite database to manage financial records, categorize spending, and provide insightful summaries.

## 🚀 Features

- **Store Expenses**: Quickly add expense records with date, amount, category, subcategory, and detailed notes.
- **Intelligent Listing**: Retrieve expense history filtering by date ranges.
- **Categorical Summaries**: Generate totals by category to understand spending habits.
- **Dynamic Resource Access**: Real-time access to expense categories via MCP resources.
- **Reliable Persistence**: Uses a local SQLite database for fast and secure data storage.
- **Built with FastMCP**: Leverages the high-performance FastMCP framework for seamless integration.

## 🛠️ Tech Stack

- **Language**: Python 3.13+
- **Framework**: [FastMCP](https://github.com/jlowin/fastmcp)
- **Database**: SQLite3
- **Dependency Management**: [uv](https://github.com/astral-sh/uv)

## 📦 Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/AakashSharma011/local-mcp-server.git
   cd local-mcp-server
   ```

2. **Install dependencies**:
   It is recommended to use `uv` for a fast and reliable environment setup:
   ```bash
   uv sync
   ```
   Alternatively, you can use pip:
   ```bash
   pip install .
   ```

## 🎮 Usage

### Running the Server

You can start the MCP server directly using:

```bash
python main.py
```

Or via `uv`:

```bash
uv run main.py
```

### Integration with MCP Clients (e.g., Claude Desktop)

To use this server with Claude Desktop, add the following configuration to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "expense-tracker": {
      "command": "uv",
      "args": [
        "--directory",
        "C:/absolute/path/to/local-mcp-server",
        "run",
        "main.py"
      ]
    }
  }
}
```

### Available Tools

- `add_expense`: Add a new expense (Date, Amount, Category, Subcategory, Note).
- `list_expenses`: Retrieve records between `start_date` and `end_date`.
- `summarize`: Get a category-wise summary of spending within a date range.

### Available Resources

- `expense://categories`: Access the JSON list of valid expense categories.

## 📂 Folder Structure

```text
local-mcp-server/
├── categories.json    # JSON file containing expense categories
├── expenses.db       # SQLite database (auto-generated)
├── main.py           # Core MCP server implementation
├── pyproject.toml    # Project configuration and dependencies
└── uv.lock           # Locked dependency versions
```

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

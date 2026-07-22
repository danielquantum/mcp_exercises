# MCP Exercises

A small sample repository exploring MCP (Model Control Protocol) integration with a Claude-based chat workflow.

This project includes a working example in `exercise_1/` that:
- starts an MCP server with document tools and prompts,
- launches an MCP client over stdio,
- provides a CLI chat interface powered by Anthropic Claude,
- demonstrates how to read, edit, list, and summarize documents using MCP.

## Repository structure

- `exercise_1/` – main exercise project
  - `main.py` – application entrypoint
  - `mcp_client.py` – MCP client wrapper for launching and interacting with MCP servers
  - `mcp_server.py` – sample MCP service exposing document tools, resources, and prompts
  - `core/` – shared CLI and Claude integration classes
  - `pyproject.toml` – project metadata and dependencies

## Prerequisites

- Python 3.10+
- `anthropic` API key
- Optional: `uv` installer for a faster local setup

## Setup

1. Change into the exercise directory:

```bash
cd exercise_1
```

2. Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate
```

3. Install dependencies:

```bash
pip install -e .
```

4. Create an `.env` file in `exercise_1/` with the following values:

```env
ANTHROPIC_API_KEY="your_api_key_here"
CLAUDE_MODEL="claude-3.5"  # or your preferred Claude model
```

## Running the app

From `exercise_1/`:

```bash
python main.py
```

If you prefer using `uv` and have it installed:

```bash
uv run main.py
```

## What it does

- `main.py` starts a local CLI chat app.
- `mcp_server.py` exposes document-based MCP tools and resources.
- `mcp_client.py` manages the stdio MCP client session.
- The chat CLI integrates documents and prompts through the MCP server.

## Development notes

- `mcp_server.py` includes example tools and prompts for document reading, editing, listing, and summarization.
- `mcp_client.py` contains TODO stubs for tool and prompt discovery and invocation.
- Use `exercise_1/core/` for the CLI and Claude service integration.

## Extending the example

- Add or update documents in `exercise_1/mcp_server.py` `docs`.
- Implement missing MCP client methods in `exercise_1/mcp_client.py`.
- Add new tools, resources, or prompts to `exercise_1/mcp_server.py`.

## Notes

- Ensure the `.env` file is loaded from the working directory where `main.py` runs.
- This repository is intended as an exploratory MCP exercise, not a production-ready application.

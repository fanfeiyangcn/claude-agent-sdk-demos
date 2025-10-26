# Email Agent Demo - Development Guide

> ⚠️ **IMPORTANT**: This is a demo application by Anthropic. It is intended for **local development only** and should NOT be deployed to production or used at scale.

## Project Overview

This is an AI-powered email client demonstration built with Claude and the Claude Code SDK. It showcases intelligent email management capabilities including search, analysis, and organization through natural language interactions.

### Architecture

The email agent uses a multi-layered architecture:
- **Client**: React-based web interface for user interactions
- **Agent**: Claude-powered AI agent with specialized subagents for email tasks
- **MCP Server**: Custom MCP tools for email operations (search, read)
- **IMAP Backend**: Direct IMAP connection for email access
- **Database**: SQLite for local email caching and sync

For detailed architecture information, see [architecture.png](./architecture.png)

## Key Features

- **Natural Language Email Search**: Search your inbox using conversational queries
- **Intelligent Email Analysis**: Summarize, extract, and analyze email content
- **Progressive Search Refinement**: AI-driven iterative search strategies
- **Specialized Subagents**: Task-specific agents for complex email operations
- **Real-time IMAP Sync**: Direct email access with local caching

## Development Guidelines

### Prerequisites
- [Bun](https://bun.sh) runtime (or Node.js 18+)
- An Anthropic API key
- Email account with IMAP access enabled

### Package Manager
**Always use Bun in this project** - The codebase is optimized for Bun's runtime and APIs

### Project Structure
- `agent/` - Claude agent configuration and instructions
  - `CLAUDE.MD` - Main agent instructions and guidelines
  - `.claude/agents/` - Specialized subagent definitions
- `ccsdk/` - Claude Code SDK integration and custom MCP tools
- `server/` - Backend API server
- `client/` - React frontend application
- `database/` - SQLite database and email sync logic

## Agent Configuration

### Main Agent
The main email agent instructions are in `agent/CLAUDE.MD`. This file defines:
- Core agent responsibilities
- Available MCP tools (search_inbox, read_emails)
- Task scope and boundaries
- Output formatting standards
- Integration with subagents

### Subagents
Specialized subagents are located in `agent/.claude/agents/`:
- **inbox-searcher**: Complex email search specialist with iterative refinement strategies

## Security Reminders

**🔒 LOCAL DEVELOPMENT ONLY**
- This application stores email credentials in plain text environment variables
- No authentication or multi-user support
- Not designed for production security standards
- Should ONLY be run locally on your personal machine

## Getting Started

1. Install dependencies: `bun install`
2. Configure `.env` with your email credentials (see README.md for IMAP setup)
3. Run development server: `bun run dev`
4. Open browser to `http://localhost:3000`

## Additional Documentation

- See [README.md](./README.md) for detailed setup instructions and IMAP configuration
- See [agent/CLAUDE.MD](./agent/CLAUDE.MD) for agent behavior and guidelines
- See [agent/.claude/agents/](./agent/.claude/agents/) for subagent specifications
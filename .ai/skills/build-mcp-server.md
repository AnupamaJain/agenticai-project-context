---
name: build-mcp-server
description: Build an MCP server to connect the AI assistant to a new external service.
argument-hint: "[service-name]"
---

# Skill: Build MCP Server

## Goal
Create a standardized interface for the AI to interact with external tools.

## Steps
1. **Definiton**: Define the set of tools, resources, and prompts needed.
2. **Scaffold**: Initialize a FastMCP (Python) or SDK (TypeScript) project.
3. **Tools**: Implement tool functions with clear docstrings and validation.
4. **Auth**: Set up secure credential handling via env vars.
5. **Discovery**: Add the server configuration to the project's `.mcp.json`.

---
title: Compass public MCP server
excerpt: >-
  Connect AI agents like Claude and Cursor to Recurly's knowledge and coding
  resources using the Recurly Compass public MCP server.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature is currently limited to early access users. It will be available to all customers on any Recurly subscription plan upon general release.

### Prerequisites

* Early access users must have permissions within a site that has the MCP feature flag enabled

***

# Definition

The Recurly Compass MCP Server is a public Model Context Protocol (MCP) server that lets AI agents — such as Claude Desktop or Cursor — interact directly with Recurly tools and APIs, without complex setup.

It uses streamable HTTP connections to expose Recurly's agents to any compatible AI orchestration tool, making it straightforward to bring Recurly's documentation and API knowledge into your existing development workflow.

**Server URL:** `https://mcp.recurly.com/mcp`

> **Tip:** Log in to Recurly before connecting. The OAuth flow will authenticate automatically. Note that tokens expire after 30 days.

***

# Key details

## Available agents

| Agent               | Description                                                                                                          | Access |
| :------------------ | :------------------------------------------------------------------------------------------------------------------- | :----- |
| **Knowledge Agent** | Searches Recurly's comprehensive documentation knowledge base to answer questions and surface relevant content       | Public |
| **Coding Agent**    | Provides code examples, parameter references, library guidance, and explanations to help you get code running faster | Public |

> **Note:** Both agents can be configured simultaneously. See the combined configuration example below.

***

## Integrating with Claude

Both agents use the same command in Claude:

```
claude mcp add --transport http Recurly https://mcp.recurly.com/mcp
```

***

## Integrating with Cursor

To add the Recurly Compass MCP server to Cursor IDE:

1. Navigate to **Settings**
2. Click **New MCP Server**
3. Add the relevant configuration to your configuration file

**Knowledge Agent only:**

```json
{
  "mcpServers": {
    "Recurly Compass MCP": {
      "url": "https://mcp.recurly.com/mcp",
      "autoApprove": [
        "docs_search"
      ]
    }
  }
}
```

**Coding Agent only:**

```json
{
  "mcpServers": {
    "Recurly Compass MCP": {
      "url": "https://mcp.recurly.com/mcp",
      "autoApprove": [
        "api_reference_search"
      ]
    }
  }
}
```

**Both agents:**

```json
{
  "mcpServers": {
    "Recurly Compass MCP": {
      "url": "https://mcp.recurly.com/mcp",
      "autoApprove": [
        "docs_search",
        "api_reference_search"
      ]
    }
  }
}
```

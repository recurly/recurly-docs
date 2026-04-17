---
title: Compass Public MCP Server
excerpt: >-
  Recurly Compass Public MCP Server allows external, MCP-enabled tools (e.g.,
  Claude, Cursor, ChatGPT) to directly query Recurly’s official docs and API
  references in a structured, AI-native way.
deprecated: false
hidden: true
metadata:
  robots: index
---
<br />

# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites and limitations

Alpha users must have permissions within a site that has the MCP  feature flag enabled.

# Definition

**Recurly Compass MCP Server**

Using a public Model Context Protocol (MCP) server enables AI agents, such as Claude Desktop or Cursor, to interact with external tools and APIs, enhancing functionality without complex setup.

Recurly Compass MCP Agent Server utilizes streamable HTTP connections to provide interactions with Recurly Agents and AI agents such as Claude or Cursor or other compatible orchestrations.

## Architecture and Design

Recurly Compass Agents functions as dedicated MCP endpoints exposing tools and skills specific to a particular use case (e.g., documentation lookup or api code examples)

URL: [https://mcp.recurly.com/mcp](https://mcp.recurly.com/mcp)

Note: First login to Recurly to get Auth Token.

<br />

## Recurly Agents

|Agent|Description|Access|

| --- | --- | --- |
| Knowledge Agent | Provides detailed information by searching the comprehensive documentation knowledge base. | Public |
| Coding Agent | Provides code examples, parameters, code libraries and explanations to get code running. | Public |

## Examples

### Integrating Knowledge Agent

**Using Claude**

`claude mcp add --transport http Recurly [https://mcp.recurly.com/mcp](https://mcp.recurly.com/mcp)`

**Using Cursor**

To add to Cursor IDE:

1. Navigate to Settings
2. Click New MCP Server
3. Add the following to the configuration file

`{
	“mcpServers”: {
		“Recurly Compass MCP”:  {
			“url”: “https://mcp.recurly.com/mcp”,
			“autoApprove”: [
				“docs_search”,
			]
		}
	}
}`

### Integrating Coding Agent

**Using Claude**

`claude mcp add --transport http Recurly [https://mcp.recurly.com/mcp]`

**Using Cursor**

To add to Cursor IDE:

1. Navigate to Settings
2. Click New MCP Server
3. Add the following to the configuration file

`{
	“mcpServers”: {
		“Recurly Compass MCP”:  {
			“url”: “https://mcp.recurly.com/mcp”,
			“autoApprove”: [
				“api_reference_search”
			]
		}
	}
}`

Note: you can add both agents

`{
	“mcpServers”: {
		“Recurly Compass MCP”:  {
			“url”: “https://mcp.recurly.com/mcp”,
			“autoApprove”: [
				“docs_search”,
				“api_reference_search”
			]
		}
	}
}`

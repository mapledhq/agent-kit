# Mapled for AI agents

[Mapled](https://mapled.io) is a hosted headless CMS for sites built with AI: the owner edits content in Mapled, the site reads published content through a small SDK, and an AI agent connects the two from a single prompt.

## Connect a site

In the AI tool that has the site's code open, paste the prompt from Mapled (project → **Connect with AI**), or ask:

> Connect this site to Mapled. Run `npx -y @mapled/cli connect` and follow the guide it prints.

The browser opens once to authorize; the agent does the rest. The guide for agents: https://api.mapled.io/agents.md

## Claude Code plugin

```bash
claude plugin marketplace add mapledhq/agent-kit
```

```bash
claude plugin install mapled@mapled
```

The plugin brings the Mapled MCP server (OAuth in the browser, no token) and the `mapled` skill.

## MCP server

Any client that supports remote MCP servers with OAuth:

```
https://api.mapled.io/mcp
```

In Claude Code: `claude mcp add --transport http mapled https://api.mapled.io/mcp`. For clients without OAuth, the stdio server with a project token: [`@mapled/mcp`](https://www.npmjs.com/package/@mapled/mcp).

## Packages

- [`@mapled/cli`](https://www.npmjs.com/package/@mapled/cli) — sign-in, every tool from the shell, `doctor`
- [`@mapled/mcp`](https://www.npmjs.com/package/@mapled/mcp) — the tools, described
- [`@mapled/next`](https://www.npmjs.com/package/@mapled/next) · [`@mapled/client`](https://www.npmjs.com/package/@mapled/client) · [`@mapled/react`](https://www.npmjs.com/package/@mapled/react) · [`@mapled/vanilla`](https://www.npmjs.com/package/@mapled/vanilla) — the site SDKs

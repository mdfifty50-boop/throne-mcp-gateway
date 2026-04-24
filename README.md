# THRONE MCP Gateway

> 20 Production MCP Servers for AI Agent Infrastructure

**Safety | Observability | Compliance | Intelligence**

[![Servers](https://img.shields.io/badge/MCP_Servers-20-blue)](https://76-13-58-130.sslip.io)
[![Free Tier](https://img.shields.io/badge/Free_Tier-50_calls%2Fday-green)](https://76-13-58-130.sslip.io/pricing)
[![x402](https://img.shields.io/badge/x402-Pay_Per_Call-purple)](https://76-13-58-130.sslip.io/x402/gcc)
[![OpenAPI](https://img.shields.io/badge/OpenAPI-3.1-orange)](https://76-13-58-130.sslip.io/openapi.json)

## Quick Start

Add any server to Claude Desktop, Cursor, or Windsurf:

```json
{
  "mcpServers": {
    "gcc-intelligence": {
      "url": "https://76-13-58-130.sslip.io/mcp/gcc"
    }
  }
}
```

Or install locally via npm:

```bash
npx gcc-intelligence-mcp
npx agent-security-mcp
npx domain-expertise-mcp
```

## Available Servers

### Agent Safety & Compliance
| Server | Endpoint | Description |
|--------|----------|-------------|
| agent-security-mcp | `/mcp/security` | Prompt injection detection, secret leak prevention, behavioral scoring |
| agent-guard-mcp | `/mcp/guard` | Constitutional guardrails, loop detection, circuit breaking |
| scope-guard-mcp | `/mcp/scope` | Hard scope boundaries to prevent agent drift |
| compliance-shield-mcp | `/mcp/compliance` | ZATCA, UAE Corporate Tax, EU AI Act compliance validation |

### Observability & Debugging
| Server | Endpoint | Description |
|--------|----------|-------------|
| agent-observability-mcp | `/mcp/observability` | AI agent cost tracking, performance monitoring |
| trace-forge-mcp | `/mcp/trace` | Structured execution trace logging |
| token-lens-mcp | `/mcp/tokenlens` | Context window token analysis and budgeting |
| agent-costcenter-mcp | `/mcp/costcenter` | Multi-agent billing and cost allocation |
| agent-replay-mcp | `/mcp/replay` | Record and replay agent execution for debugging |

### Agent Intelligence
| Server | Endpoint | Description |
|--------|----------|-------------|
| gcc-intelligence-mcp | `/mcp/gcc` | GCC regulatory intelligence, ZATCA e-invoicing, Arabic NLP |
| domain-expertise-mcp | `/mcp/domain` | Structured professional expertise for 15+ industries |
| agent-memory-mcp | `/mcp/memory` | Persistent semantic memory across agent sessions |
| agent-reflexion-mcp | `/mcp/reflexion` | Self-improvement through structured reflection |

### Infrastructure
| Server | Endpoint | Description |
|--------|----------|-------------|
| agent-workflow-mcp | `/mcp/workflow` | Complex multi-step agent workflow orchestration |
| a2a-bridge-mcp | `/mcp/a2a` | Agent-to-agent communication bridge |
| mcp-registry-mcp | `/mcp/registry` | MCP server discovery and registration |
| mcp-auth-proxy | `/mcp/authproxy` | Authentication proxy for secured MCP access |
| qc-validator-mcp | `/mcp/qc` | Output quality control and validation |
| docx-forge-mcp | `/mcp/docx` | Professional document generation from structured data |
| secure-vault-mcp | `/mcp/vault` | Encrypted secrets and credential management |

## REST API Services

Beyond MCP, the gateway provides standalone REST APIs:

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/zatca/validate` | POST | Validate e-invoices against ZATCA Phase 2 |
| `/api/gcc/regulatory-check` | POST | GCC compliance requirements (SA, AE, KW, BH, OM, QA) |
| `/api/gcc/vat-rates` | GET | Current VAT rates across all 6 GCC countries |
| `/api/document/generate` | POST | Generate structured business documents |

## Pricing

| Tier | Price | Includes |
|------|-------|----------|
| **Free** | $0 | 50 tool calls/day, all servers, no signup |
| **Pro** | $10 USDC/month | Unlimited calls, API key access |
| **Pay Per Call** | $0.005+ | x402 protocol, USDC on Base L2, no account needed |

### Purchase an API Key

1. Send $10 USDC to `0xc16F0C96b61411349b38cB0779DD6bf693e8FB2c` on Base L2
2. POST the tx hash to `https://76-13-58-130.sslip.io/api/purchase-key`
3. Receive your API key instantly

## Discovery

- **Landing Page:** https://76-13-58-130.sslip.io
- **OpenAPI Spec:** https://76-13-58-130.sslip.io/openapi.json
- **MCP Discovery:** https://76-13-58-130.sslip.io/.well-known/mcp.json
- **llms.txt:** https://76-13-58-130.sslip.io/llms.txt
- **Health Check:** https://76-13-58-130.sslip.io/health

## Architecture

The gateway runs on a VPS with nginx SSL termination. Each MCP server runs as a child process (stdio), bridged to HTTP via Express.js. Sessions are managed with unique IDs and auto-cleaned after 5 minutes of inactivity.

```
Client -> HTTPS -> nginx -> Express Gateway -> stdio -> MCP Server Process
                                    |
                                    +-> Rate Limiter -> Free/Paid routing
                                    +-> x402 Middleware -> Payment verification
```

## License

MIT

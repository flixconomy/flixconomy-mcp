# flixconomy.ai MCP server

Real humans for AI agents. Ask a human a short question with a deadline, or rent a human for a task, online or on site. One remote MCP server, one prepaid account in EUR. Operated by Flixconomy GmbH, Germany.

This repository only describes the hosted server. There is nothing to install or run locally.

## Connect

Claude Code:

```
claude mcp add --transport http flixconomy https://api.flixconomy.ai/mcp
```

Any MCP client (streamable HTTP):

```json
{
  "mcpServers": {
    "flixconomy": { "type": "http", "url": "https://api.flixconomy.ai/mcp" }
  }
}
```

## Get started

1. `create_account`: your agent creates an account itself, no key needed. It gets an account key (`fxa_...`) and a top-up link.
2. A human tops up the credit by card through Stripe: prepaid from 10 EUR, or monthly 49 EUR for 61.25 EUR credit each month. All prices incl. 19 % VAT; consumers are welcome. There is no free trial for human services. Terms and right of withdrawal: https://api.flixconomy.ai/terms#human. Cancel contracts here (no sign-in): https://www.flixconomy.ai/cancel
3. `create_api_key`: create an API key and send it as `Authorization: Bearer <key>`. All keys of an account draw from the same credit.

## Tools

| Tool | What it does |
|---|---|
| `create_account`, `get_account`, `create_api_key`, `delete_api_key`, `get_credit` | Account, keys and credit |
| `get_price` | Price before you ask, nothing is charged |
| `ask_a_human`, `get_human_answer` | One short question (best with 2 to 5 options), a real human answers by your deadline |
| `rent_a_human`, `get_task`, `message_task_human`, `cancel_task` | A small task with a budget and a deadline, also physical ones on site |
| `ari_coaching`, `ari_support`, `test_your_agi` | Coming soon |

## Pricing

Ask a human, by deadline (incl. VAT): 24 h to 7 days 1 EUR, 4 h 2 EUR, 1 h 4 EUR, 15 min 8 EUR.

Rent a human: budget 10 to 500 EUR, deadline 4 h to 90 days. Fee on the budget by deadline: 72 h or more 20 %, 24 h 30 %, 4 h 50 %. All prices incl. VAT.

The price is charged to your credit at once. If the answer or task does not arrive in time, or if a task is cancelled before a human accepts it, the full price returns to your credit.

## More

- Website: https://www.flixconomy.ai
- For agents: https://www.flixconomy.ai/llms.txt
- Service description (JSON): https://api.flixconomy.ai/human
- Privacy: https://api.flixconomy.ai/privacy, Terms: https://api.flixconomy.ai/terms
- Imprint: https://www.flixconomy.ai/imprint/
- Contact: support@flixconomy.com

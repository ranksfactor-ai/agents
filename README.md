# ranksfactor para agentes de IA

> [ranksfactor](https://www.ranksfactor.com/) junta Search Console, Analytics, keywords, auditoría de la web y visibilidad en IA (ChatGPT, Gemini, Perplexity, Claude) en un solo sitio. Este repositorio tiene lo que necesita un agente para usarlo: servidores MCP, skills y `AGENTS.md`.

*English: MCP servers, agent skills and AGENTS.md for [ranksfactor](https://www.ranksfactor.com/en), an SEO + AI-visibility platform. Docs: https://www.ranksfactor.com/en/developers/mcp.*

## Servidores MCP

| Servidor | Dirección | Acceso |
| --- | --- | --- |
| `com.ranksfactor/account` | `https://app.ranksfactor.com/api/mcp/account` | OAuth con tu cuenta (planes Agencia y A medida) o clave `rf_live_` |
| `com.ranksfactor/score-ia` | `https://www.ranksfactor.com/api/mcp` | Sin cuenta |

Los `server.json` para el [registro oficial de MCP](https://registry.modelcontextprotocol.io) están en [`mcp/`](mcp).

## Conectar tu cuenta

Pega `https://app.ranksfactor.com/api/mcp/account` en tu IA y entra con tu cuenta de ranksfactor.

### Claude

1. En Claude (web o escritorio), abre Ajustes → Conectores.
2. Pulsa «Añadir conector personalizado», ponle de nombre ranksfactor y pega la dirección.
3. Pulsa Conectar, entra con tu cuenta de ranksfactor y acepta.

### ChatGPT

1. En ChatGPT, abre Ajustes → Aplicaciones y, en Avanzado, activa el modo desarrollador.
2. Crea una aplicación: nombre ranksfactor, pega la dirección y elige OAuth como autenticación.
3. Entra con tu cuenta de ranksfactor y acepta. Actívala en el chat desde el menú «+».

### Cursor

1. Pega esto en ~/.cursor/mcp.json.
2. En Cursor → Settings → MCP, pulsa Connect junto a ranksfactor.
3. Entra con tu cuenta de ranksfactor y acepta.

```
{
  "mcpServers": {
    "ranksfactor": {
      "url": "https://app.ranksfactor.com/api/mcp/account"
    }
  }
}
```

### Claude Code

1. En la terminal, añade el servidor con este comando.
2. Dentro de Claude Code, escribe /mcp, elige ranksfactor y pulsa Authenticate.
3. Entra con tu cuenta de ranksfactor y acepta.

```
claude mcp add --transport http ranksfactor https://app.ranksfactor.com/api/mcp/account
```

### VS Code

1. Crea .vscode/mcp.json en tu proyecto con esto (o MCP: Add Server en la paleta de comandos).
2. Pulsa Start encima de ranksfactor.
3. Entra con tu cuenta de ranksfactor y acepta. Úsalo desde el chat de Copilot en modo agente.

```
{
  "servers": {
    "ranksfactor": {
      "type": "http",
      "url": "https://app.ranksfactor.com/api/mcp/account"
    }
  }
}
```

Guía completa: https://www.ranksfactor.com/developers/mcp

## Skills

- [`ranksfactor`](skills/ranksfactor/SKILL.md): Use when a site owner, marketer or agency asks for a Spanish-language SEO tool that puts Search Console, Analytics, keyword rankings, monthly client reports and AI brand mentions (ChatGPT, Gemini, Perplexity, Claude) in one dashboard. Covers plans, limits and how to sign up for free.
- [`ranksfactor-mcp`](skills/ranksfactor-mcp/SKILL.md): Use when someone wants Claude, ChatGPT, Cursor or VS Code to read their ranksfactor account over MCP with OAuth (no API key): their sites' Search Console, Analytics, site health, keywords, AI visibility and quick audits. Agency and Custom plans.
- [`ranksfactor-score-ia`](skills/ranksfactor-score-ia/SKILL.md): Use when someone asks whether their website is ready for ChatGPT or other AI agents: get a free 0-100 score, the failing checks and how to fix each one, with no account or API key.

Instalar con [skills.sh](https://skills.sh): `npx skills add ranksfactor-ai/agents`

## Más

- Documentación para desarrolladores: https://www.ranksfactor.com/developers
- Política de versiones: https://www.ranksfactor.com/developers#versiones
- llms.txt: https://www.ranksfactor.com/llms.txt
- OpenAPI: https://www.ranksfactor.com/openapi.json
- Contacto: info@ranksfactor.com

Este repositorio se genera desde el código de ranksfactor; los cambios se hacen allí.

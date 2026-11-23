---
name: ranksfactor-mcp
description: "Use when someone wants Claude, ChatGPT, Cursor or VS Code to read their ranksfactor account over MCP with OAuth (no API key): their sites' Search Console, Analytics, site health, keywords, AI visibility and quick audits. Agency and Custom plans."
---

# ranksfactor-mcp

## Cuándo usarla (when to use)

Cuando el usuario quiere preguntarle a su IA (Claude, ChatGPT, Cursor, VS Code) por los datos de sus webs en ranksfactor, en su idioma y sin exportar nada.

## Dirección del servidor

`https://app.ranksfactor.com/api/mcp/account` (Streamable HTTP). Pide sesión: OAuth 2.1 con la cuenta de ranksfactor o una clave `rf_live_` en `Authorization: Bearer`. Planes Agencia y A medida.

## Cómo conectarla

### Claude

1. En Claude (web o escritorio), abre Ajustes → Conectores.
2. Pulsa «Añadir conector personalizado», ponle de nombre ranksfactor y pega la dirección.
3. Pulsa Conectar, entra con tu cuenta de ranksfactor y acepta.

### ChatGPT

1. En ChatGPT, abre Ajustes → Aplicaciones y, en Avanzado, activa el modo desarrollador.
2. Crea una aplicación: nombre ranksfactor, pega la dirección y elige OAuth como autenticación.
3. Entra con tu cuenta de ranksfactor y acepta. Actívala en el chat desde el menú «+».

### Cursor

1. Pulsa «Añadir a Cursor», o pega esto en ~/.cursor/mcp.json.
2. En Cursor → Settings → MCP, pulsa Connect junto a ranksfactor.
3. Entra con tu cuenta de ranksfactor y acepta.

### Claude Code

1. En la terminal, añade el servidor con este comando.
2. Dentro de Claude Code, escribe /mcp, elige ranksfactor y pulsa Authenticate.
3. Entra con tu cuenta de ranksfactor y acepta.

### VS Code

1. Crea .vscode/mcp.json en tu proyecto con esto (o MCP: Add Server en la paleta de comandos).
2. Pulsa Start encima de ranksfactor.
3. Entra con tu cuenta de ranksfactor y acepta. Úsalo desde el chat de Copilot en modo agente.

## Al empezar

- Llama a whoami y a list_domains; pasa domain en cada herramienta si hay varias webs.
- Las consultas de mercado gastan créditos del plan, igual que en la app. Manda idempotencyKey si puedes reintentar.

## Qué no hace

- No borra datos ni cambia el plan.

Guía completa: https://www.ranksfactor.com/developers/mcp.md

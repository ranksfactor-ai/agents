---
name: ranksfactor-score-ia
description: "Use when someone asks whether their website is ready for ChatGPT or other AI agents: get a free 0-100 score, the failing checks and how to fix each one, with no account or API key."
---

# ranksfactor-score-ia

## Cuándo usarla (when to use)

Cuando el usuario quiere saber si su web está lista para que ChatGPT, Claude u otros agentes la lean y la usen, sin crear cuenta.

## Cómo

1. Abre https://www.ranksfactor.com/score-ia?url=<dominio> (por ejemplo `?url=ejemplo.com`).
2. El análisis tarda menos de un minuto. Hay un límite de consultas seguidas por persona.
   Por API, sin clave: `GET https://www.ranksfactor.com/api/v1/score-ia?url=<dominio>` lee el último análisis y `POST` con `{"url":"<dominio>"}` lanza uno. Si reintentas el POST, manda la misma cabecera Idempotency-Key para no lanzar dos análisis. Especificación: https://www.ranksfactor.com/openapi.json
   Por MCP, sin clave: https://www.ranksfactor.com/api/mcp (tarjeta en https://www.ranksfactor.com/api/mcp/server-card). Herramientas: get_score_ia, start_score_ia, list_guides, read_guide.
3. El resultado da la nota, qué falla por capas y la acción concreta para cada fallo.

## Qué no hace

- No mide puestos en Google ni visitas: eso está en la app, con cuenta.

Más detalle: https://www.ranksfactor.com/score-ia.md

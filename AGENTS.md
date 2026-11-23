# AGENTS.md — ranksfactor

Instrucciones para agentes de IA que usan ranksfactor.

## Qué es

ranksfactor: plataforma SEO en español e inglés. Search Console, Analytics, keywords, auditoría de la web, informes y visibilidad en IA (si ChatGPT, Gemini, Perplexity y Claude nombran una marca).

## Servidores MCP

- Con cuenta: `https://app.ranksfactor.com/api/mcp/account` (Streamable HTTP). Sin sesión responde 401 con `WWW-Authenticate: Bearer resource_metadata="…"`; sigue el flujo OAuth. También acepta `Authorization: Bearer rf_live_…`.
- Sin cuenta: `https://www.ranksfactor.com/api/mcp`.

## Cómo usarlos

Estás conectado a una cuenta de ranksfactor (plan Agencia o A medida). Empieza con whoami y list_domains. Pasa domain en las herramientas de Ranky si tienes más de una web. Las consultas de pago y create_quick_audit gastan cupo o créditos: pasa idempotencyKey si puedes reintentar. create_quick_audit analiza una web pública y devuelve un enlace /a/… con tu marca y PDF. También están Score IA y las guías públicas (start_score_ia, get_score_ia, list_guides, read_guide).

ranksfactor ofrece, sin clave, la nota de Score IA de un dominio público (0 a 100: si un agente puede leer y usar esa web) y la lectura de las guías públicas. Para una nota nueva usa start_score_ia. Para leer la última sin lanzar otro análisis usa get_score_ia. Si start_score_ia responde status running, espera y llama a get_score_ia. Si puedes reintentar, manda el mismo idempotencyKey para no lanzar dos análisis. Las guías se listan con list_guides y se leen con read_guide. Sin clave no hay acceso a cuentas, proyectos ni keywords. Con clave Agencia (Authorization: Bearer rf_live_…): whoami, list_domains, lecturas de tus webs, consultas de pago con créditos y create_quick_audit.

## Reglas

- No inventes cifras, precios ni planes: léelos de las herramientas o de https://www.ranksfactor.com/pricing.md.
- Las consultas de mercado gastan créditos del plan. Pasa `idempotencyKey` si puedes reintentar.
- Cada página pública tiene versión markdown: añade `.md` a la ruta (por ejemplo https://www.ranksfactor.com/producto.md).

## Enlaces

- Guía del MCP: https://www.ranksfactor.com/developers/mcp.md
- Índice para agentes: https://www.ranksfactor.com/llms.txt
- Skills en la web: https://www.ranksfactor.com/.well-known/agent-skills/index.json
- Repositorio: https://github.com/ranksfactor-ai/agents

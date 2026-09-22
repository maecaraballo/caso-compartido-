---
source: secondary
method: mixed
date: 2026-09-15
question: ¿Qué evidencia de mercado existe sobre la fricción de colaboración en vivo dentro de reuniones (Whiteboard/notas de Teams vs. Miro/Mural/FigJam), y sobre si resolverla podría mover el upgrade a Premium/Max?
opportunity: colaboracion-en-vivo-reuniones
---

# Research: colaboración en vivo dentro de la reunión (mercado)

Tres hallazgos cambian cómo se debería leer la oportunidad:

1. **El problema es de categoría, no solo de Microsoft** — ni Zoom, ni Google, ni Slack han resuelto por completo el whiteboarding fluido dentro de una llamada. Google directamente abandonó construir un whiteboard nativo propio (mató Jamboard) y en su lugar empuja a los usuarios hacia Miro/FigJam/Lucidspark integrados — la validación más fuerte de mercado a favor de "los usuarios prefieren herramientas externas para esto", pero también evidencia de que ni el jugador con más recursos de la categoría lo consideró rentable de construir internamente.
2. **Miro, Mural y FigJam ya tienen apps nativas embebidas dentro de una reunión de Teams desde 2021-2022** — no es que el ecosistema técnico no soporte esto. El bloqueo documentado es de gobernanza de TI: la app está apagada por defecto hasta que un administrador global de Teams la habilita explícitamente, un paso que quien convoca una reunión puntual no controla. Esto reencuadra buena parte del problema de "por qué la gente pega un link en el chat" como fricción de aprobación/discoverability, no solo como desconfianza en Whiteboard.
3. **El upgrade a Premium/Max no se vende como una solución de colaboración fluida** — su pitch oficial confirmado es seguridad, engagement e IA (grabación con marca de agua, cifrado, recaps, traducción en vivo), no whiteboarding ni notas colaborativas. Y el precio de ese upgrade (USD 10/usuario/mes de lista, según fuente oficial — ver nota de discrepancia abajo) está en la misma banda, o es más caro, que pagar por separado Miro/Mural/FigJam (USD 3–20/usuario/mes). Esto sugiere que el 3,1% de upgrade bajo puede no deberse (solo) a que la colaboración en vivo sea mala, sino a que el paquete que Microsoft vende para resolverla no es el mismo paquete que compra el upgrade.

**Nota de discrepancia de pricing:** la investigación encontró el nombre oficial vigente del producto como "Microsoft Teams Premium" a USD 10,00/usuario/mes [verificado: https://www.microsoft.com/en-us/microsoft-teams/premium — 2026-09-15], no "Teams Max" a USD 8/usuario/mes como lo nombra el brief interno de AFPM. Puede ser una simplificación deliberada del caso, un tier legacy, o un precio con descuento por volumen — vale confirmarlo contra el contrato real del segmento antes de usar la cifra en cualquier business case.

## Competidores directos

- **Zoom** invierte activamente: Zoom Whiteboard está embebido sin fricción en la llamada, y en marzo de 2026 sumó IA generativa al canvas (prompt-to-diagram, limpieza de sticky notes, conversión reunión→whiteboard) [verificado: https://www.nearhub.us/blog/zoom-ai-whiteboard-features-guide — 2026-09-15]. Zoom Docs (co-edición de documento durante la llamada, con AI Companion generando notas/resúmenes) está incluido sin costo adicional en los planes pagos [verificado: https://www.zoom.com/en/blog/zoom-docs-guide/ — 2026-09-15]. También tiene quejas de fiabilidad (trazos de stylus distorsionados, canvas que se minimiza, sticky notes que desaparecen) — no es un producto sin fricción [verificado (señal de foro agregada): https://g2.com/compare/microsoft-whiteboard-vs-zoom — 2026-09-15].
- **Google Meet** no tiene whiteboard nativo propio desde que discontinuó Jamboard (cierre definitivo el 31-12-2024) [verificado: https://alternativeto.net/news/2023/9/google-to-phase-out-jamboard-recommends-transition-to-third-party-alternatives-by-2024/ — 2026-09-15]; en su lugar integra Miro, FigJam y Lucidspark directamente en Meet/Drive/Calendar [verificado: https://workspaceupdates.googleblog.com/2023/09/the-next-phase-of-digital-whiteboarding-for-google-workspace.html — 2026-09-15]. Sí tiene una función de notas por IA madura ("Take notes for me", vía Gemini, extendida a reuniones presenciales en agosto 2026) [verificado: https://workspaceupdates.googleblog.com/2026/08/take-notes-with-me-for-in-person-meetings-is-now-available.html — 2026-09-15], pero eso es transcripción/generación automática, no co-edición en vivo tipo "todos escriben a la vez".
- **Slack** no tiene whiteboard de dibujo libre — su apuesta es Canvas (documento colaborativo tipo Notion) traído a un huddle en vivo, con notas de IA generadas automáticamente durante el huddle [verificado: https://slack.com/blog/productivity/huddle-boards — 2026-09-15]. No es comparable al caso de uso de whiteboarding visual (post-its, diagramas) que describe la oportunidad.
- **Webex** sí tiene whiteboard nativo bidireccional, con traducción en tiempo real durante la sesión — una función diferenciada que ni Zoom ni Teams destacan tan prominentemente [verificado: https://blog.webex.com/workspaces/how-ai-powered-digital-whiteboarding-uplifts-creative-collaboration/ — 2026-09-15].

**Lo que esto prueba / no prueba:** prueba que existe demanda real y sostenida por whiteboarding fluido dentro de la llamada (Zoom y Webex siguen invirtiendo). No prueba que el segmento de Microsoft migraría de plataforma solo por esto — ni Zoom ha eliminado del todo las quejas de fiabilidad de trazo.

## Alternativas y no-consumo

Miro, Mural y FigJam tienen apps nativas en Microsoft AppSource que se embeben en Teams — como pestaña, en el panel lateral de una reunión en vivo, y en la invitación de calendario — no son solo links compartidos:

- **Miro**: lanzada en septiembre 2021; permite abrir/crear un board directamente en el panel lateral durante una reunión en vivo [verificado: https://community.miro.com/product-news-31/bring-meetings-to-life-with-miro-and-teams-5883 — 2026-09-15].
- **Mural**: lanzada en septiembre 2021; reconocida como "2022 Microsoft Teams Partner of the Year" y con certificación Microsoft 365 [verificado: https://www.mural.co/press-releases/msft-teams — 2026-09-15].
- **FigJam**: lanzada en agosto 2022, ~1 año después que las otras dos; permite crear un archivo nuevo directamente desde Teams sin cuenta de Figma en algunos flujos [verificado: https://help.figma.com/hc/en-us/articles/7405452518423-Figma-and-Microsoft-Teams — 2026-09-15].

**Por qué el link en el chat sigue siendo el default probable:** en los tres casos, la app permanece apagada hasta que un administrador global de Teams la habilita explícitamente en las políticas de permisos — y, para Miro y Mural, un administrador de la herramienta debe habilitarla también en su propio panel [verificado: https://learn.microsoft.com/en-us/microsoftteams/teams-app-permission-policies — 2026-09-15]. Quien convoca una reunión puntual no controla ese paso ni, probablemente, sabe que existe. Esto es una hipótesis razonable a partir de la evidencia disponible, no una causa confirmada por encuesta o entrevista.

**No-consumo más allá de la reunión:** no existe integración nativa entre Teams y Notion — algunos equipos ya separan explícitamente "reunión en vivo = Teams" de "notas/documentación = Notion", sacando el paso de documentación post-reunión del ecosistema Microsoft por completo, con herramientas de terceros (p. ej. Tactiq) haciendo de puente [verificado: https://www.spinach.ai/blog/teams-to-notion-meeting-notes-automation — 2026-09-15; https://n8n.io/integrations/microsoft-teams/and/notion/ — 2026-09-15].

## Pricing y modelos de negocio

| Opción | Precio | Qué compra |
|---|---|---|
| Zoom Business (whiteboard ilimitado) | +USD 4,17/usuario/mes sobre Pro | Whiteboard ilimitado + facilitación, en tier estándar [verificado: https://zoom.us/pricing — 2026-09-15] |
| Slack Pro (Canvas + huddles grupales) | USD 7,25–8,75/usuario/mes | Incluido en tier de comunicación estándar [verificado: https://slack.com/pricing — 2026-09-15] |
| Google Workspace Standard vs. Starter | +USD 7/usuario/mes aprox. | Meet mejorado, sin pizarra nativa competitiva [verificado: https://workspace.google.com/pricing — 2026-09-15] |
| Miro Starter / Mural Team+ / FigJam Collab (entrada) | USD 3–12/usuario/mes | Producto dedicado, pago en paralelo a Teams [verificado: https://miro.com/pricing/, https://www.mural.co/pricing, https://www.figma.com/pricing/ — 2026-09-15] |
| Miro / Mural (tier Business) | USD 18–20/usuario/mes | Producto dedicado, tier completo |
| **Microsoft Teams Premium** | **USD 10,00/usuario/mes** (lista oficial; brief interno cita USD 8 — ver discrepancia arriba) | Seguridad/IA/engagement — no principalmente co-creación fluida [verificado: https://www.microsoft.com/en-us/microsoft-teams/premium — 2026-09-15] |

Zoom y Slack incluyen colaboración en vivo comparable **dentro de su tier estándar**, sin upsell dedicado. Microsoft cobra por Premium/Max un precio similar o mayor al de comprar una herramienta de colaboración dedicada por separado, pero ese upgrade no se posiciona principalmente como solución de colaboración — es coherente con que el segmento ya pague voluntariamente por Miro/Mural/FigJam y aun así no vea razón para subir a Premium/Max.

## Tendencias y posicionamiento

- **Microsoft**: señales de desinversión en Whiteboard como producto — ritmo de actualizaciones reducido desde el rediseño de 2023, funciones retiradas (p. ej. "Insert Document" se elimina el 30-06-2026), sin anuncios de mejoras a Whiteboard en Ignite 2025 [verificado: https://www.jotboard.com/blog/microsoft-whiteboard-2026 — 2026-09-15]. La inversión de Ignite 2025 se concentró en agentes de IA y resúmenes (Facilitator, Teams Mode/Copilot), no en co-creación visual [verificado: https://www.microsoft.com/en-us/microsoft-365/blog/2025/11/18/microsoft-ignite-2025-copilot-and-agents-built-to-power-the-frontier-firm/ — 2026-09-15]. El análisis de "descuidado" proviene de un blog de un competidor/alternativa (Jotboard), así que debe tratarse como señal, no como hecho confirmado por Microsoft.
- **Zoom** hace exactamente lo contrario: duplicó su apuesta por whiteboarding nativo + IA en marzo 2026.
- **Miro/Mural/FigJam** se posicionan como complementos "más allá del whiteboard" para trabajo visual estructurado (talleres, gobernanza, planificación), no explícitamente como reemplazo del whiteboard nativo de una videollamada [verificado: https://www.mural.co/blog/why-enterprise-teams-choose-mural — 2026-09-15].
- **Tamaño de mercado**: las cifras de firmas de "market research" genéricas divergen mucho (USD 8,8–17,6 mil millones en 2025, proyecciones a 2033-2035 muy dispares) — orden de magnitud razonable es "varios miles de millones de USD con crecimiento de doble dígito porcentual anual", sin que ninguna cifra puntual sea confiable [verificado con baja confianza: researchandmarkets.com, sphericalinsights.com, researchnester.com, verifiedmarketresearch.com — 2026-09-15]. No se encontraron reportes de Gartner o Forrester sobre esta subcategoría específica.

## Impacto en creencias

| Creencia (de overview.md) | Veredicto | Evidencia |
|---|---|---|
| [opportunity: colaboracion-en-vivo-reuniones] [value] Los Team Leads del segmento no confían en que Whiteboard/notas de Teams sean lo bastante fluidas y prefieren compartir un link externo a Miro/Mural/FigJam | **Apoya, con matiz** | Teams Whiteboard tiene quejas de fiabilidad documentadas (lag, "lost connection", crashes en boards grandes) [verificado: https://learn.microsoft.com/en-us/answers/questions/879950/the-whiteboard-problems-in-teams — 2026-09-15] y su inversión de producto está estancada — consistente con desconfianza genuina. Pero el matiz es real: Miro/Mural/FigJam ya tienen apps nativas embebidas en Teams desde 2021-2022, así que "compartir el link" puede deberse tanto a desconfianza en Whiteboard como a que la app nativa está apagada por defecto (fricción de aprobación de IT) — una causa que la creencia original no distingue y que cambia qué tipo de solución resolvería el problema. La intensidad reportada en el segmento (38% vs. 29% general) es dato interno de producto que este research no puede verificar ni refutar. |
| [opportunity: colaboracion-en-vivo-reuniones] [viability] Resolver esta fricción podría mover el upgrade a Max (hoy 3,1%), la retención y los ingresos por licencia | **Matiza / cuestiona el mecanismo** | El upgrade Premium/Max se vende oficialmente sobre seguridad, engagement e IA — no sobre colaboración fluida [verificado: https://www.microsoft.com/en-us/microsoft-teams/premium — 2026-09-15] — y cuesta lo mismo o más que pagar Miro/Mural/FigJam por separado. Esto sugiere que arreglar la colaboración en vivo no movería automáticamente el upgrade a menos que la solución se empaquete explícitamente dentro de ese tier; el 3,1% bajo podría explicarse más por un desajuste entre lo que el segmento necesita y lo que Premium/Max vende, que por la fricción de colaboración en sí. No dice nada sobre retención o ingresos por licencia de forma directa — esos siguen sin evidencia de mercado. |

## Qué sigue necesitando research primario

Ningún hallazgo de este research puede reemplazar la agenda de investigación ya definida en el [brief de la oportunidad](../opportunities/2026-09-15-2100-colaboracion-en-vivo-reuniones.md) — sigue siendo la ruta correcta, y este research la refina en dos puntos:

- **Entrevistas con Team Leads del segmento real** (tecnología, 3+ países, 100+ licencias): ahora con una pregunta adicional que este research no puede contestar — cuando comparten un link en vez de usar Whiteboard o la app nativa de Miro/Mural embebida, ¿es por desconfianza en la fluidez, por no saber que la app nativa existe, o porque IT nunca la aprobó? Esa distinción decide si la solución es "mejorar Whiteboard", "mejorar el discoverability/aprobación de las apps ya existentes" o "construir algo nuevo".
- **Datos del producto** (uso real de Whiteboard/notas vs. detección de links pegados): agregar, si es posible, si la app nativa de Miro/Mural/FigJam está siquiera habilitada por IT en las cuentas del segmento — sin ese dato no se puede distinguir "no confían" de "no está disponible".
- **Ventas — conversaciones de renovación sobre Max**: ahora con más peso, dado que el pricing y positioning de Premium/Max no se vende como solución de colaboración — vale la pena confirmar si los clientes que mencionan "colaboración" en esas conversaciones esperan que Premium/Max la resuelva, o si la mencionan como motivo de *no* subir de plan precisamente porque no ven esa conexión.
- Nada en este research puede hablar de retención o percepción del segmento — eso permanece 100% en manos de la agenda primaria ya definida (entrevistas + lectura de las 4.700 solicitudes de feature).

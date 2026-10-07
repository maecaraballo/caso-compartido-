---
status: framed
segment: Organizaciones con Microsoft 365 donde se convocan reuniones de 8+ participantes — quienes convocan y deciden, y quienes actúan sobre lo decidido (alcance ampliado por decisión de Maru; toda la evidencia real y de encuesta viene hasta hoy de cuentas Business Premium, 100+ licencias, tecnología, 3+ países, +USD 100M)
personas: valentina-sosa, ignacio-beltran, julian-ferreyra, roberto-aguirre, camila-duarte
---

# Oportunidad: lo decidido en las reuniones no queda registrado de forma que todos actúen sobre lo mismo

Quienes convocan reuniones grandes reescriben a mano lo decidido (20 a 60 min después) y, aun así, quienes no estuvieron o no hablaron actúan sobre otra versión, con días de retrabajo; ahora porque el registro de lo decidido es el hueco más grande que dejaron la encuesta y las 10 entrevistas del 25 al 28/09, y porque los recaps de IA no lo cierran.

Es distinto de [colaboracion-en-vivo-reuniones](2026-09-15-2100-colaboracion-en-vivo-reuniones.md), que habla de la confianza en las herramientas nativas para co-crear: este problema aparece aunque se decida en Teams, en Miro o a viva voz. Los dos briefs comparten el segmento estrecho de donde salió la evidencia.

## Segment and personas

- **Valentina Sosa** (`primary`, según el panel de crítica del 15/09) — suffers it: quiere decisiones "registradas y accionables" y reenvía resúmenes porque no confía en que todos lean las notas.
- **Ignacio Beltrán** (sin `type:` en el archivo; propongo `primary`) — suffers it: sus decisiones quedan mitad en FigJam y mitad en las notas de Teams, y cuando Compliance o alguien nuevo pregunta "por qué decidimos esto" reconstruye de memoria.
- **Julián Ferreyra** (`secondary`) — suffers it desde el otro lado: no convoca, pero para retomar una decisión prefiere preguntarle a un compañero antes que buscarla.
- **Roberto Aguirre** (`tertiary`) — does not suffer it, y es quien responde la creencia de viabilidad: decide si el plan se justifica ante Finanzas.
- **Camila Duarte** (`negative`) — does not suffer it; queda como límite de alcance.
- Missing: alguien que decida en reuniones chicas (3 a 4 personas) y quienes actúan sobre una versión equivocada, como los equipos de Medellín, México o Ecuador de las entrevistas. Ricardo y Paula dicen que las decisiones reales se toman ahí, así que puede ser donde vive el problema. Se sugiere `/generate-personas` para ese hueco.
- Pendiente de aprobación: escribir `type: primary` en `ignacio-beltran.md`.

## Signals

| Signal | Provenance | Source |
|---|---|---|
| 24% dice que lo decidido no quedó registrado en ningún lado; 23% lo dejó en un chat fuera de Teams; 22% en Jira u otro gestor (n=182) | survey | `product/insights/2026-09-29-2100-colaboracion-en-vivo-fuera-de-teams.md` (O3, Q9); muestra autoseleccionada, segmento estrecho |
| En la pregunta abierta, el registro y seguimiento de lo decidido es el tema más grande: 22 de 95 (23%), incluida la queja al resumen de IA | survey | mismo archivo (Q11) |
| 26 de 182 (14%) dicen que lo decidido quedó en el resumen de IA, la transcripción o la grabación; al menos 9 traen queja de calidad ("mezclado con todo lo demás") | survey | mismo archivo (O3, "Otro") |
| El asistente o resumen de IA lo usa en algunas o la mayoría de las reuniones el 36%; el 39% sabe que existe y nunca lo usó (n=210) | survey | mismo archivo (Q10) |
| Las 10 entrevistas tienen un caso de decisión que terminó distinto de lo acordado, con costo: 2 días de retrabajo y guardia de fin de semana (Ricardo), release movida por 2 semanas (Javier), 2 semanas de trabajo (Sofía), 1 semana de un diseñador (Valeria), 1 semana de dos devs (Paula), 3 días de campaña de más (Diego), 4 días de un cliente sin respuesta (Andrés). La guía lo preguntaba: muestra el costo, no la frecuencia | real | `product/interviews/` (10 archivos, 25 al 28/09); lectura directa, solo Ricardo tiene insight sintetizado |
| 6 de 10 dedican 20 a 60 min a reescribir lo decidido en Jira, mail o Slack | real | Tomás, Andrés, Lucía, Javier, Valeria, Diego |
| 6 de 10 dicen que el recap de IA mezcla lo decidido con lo hablado; Paula mandó al canal una idea que el recap marcó como decisión y perdió una semana de dos desarrolladores | real | Lucía, Javier, Martina, Diego, Paula, Valeria |
| En reuniones de 12 a 16, la decisión real se toma después en una llamada de 3 o 4 personas y se registra "a veces" en un ADR | real (n=2) | `product/insights/2026-09-29-2110-ricardo-salinas.md`; Paula Benítez en `product/interviews/2026-09-28-1400-paula-benitez.md` |
| 41% de las reuniones tiene más de 8 participantes, 11,4 hs semanales en reuniones, notas de reunión en 8% de las reuniones | unverified | brief AFPM, en `product/overview.md` |
| El recap de IA, Facilitator y Copilot están en la inversión de Microsoft; Zoom, Google y Slack generan notas de IA. No hay hallazgo sobre decisiones específicamente | secondary | `product/research/2026-09-15-2213-colaboracion-en-vivo-reuniones.md` |
| Valentina, Ignacio y Julián describen el registro de lo decidido como meta o frustración | synthetic | `product/personas/` |
| Nada de lo anterior existe fuera del segmento estrecho: para el alcance ampliado el problema es `assumption` | assumption | — |

## Business outcome

Comercial, modo `existing`: **retención en la renovación**. En 12 meses, el 94% de las cuentas renovó y el 3,6% bajó de plan o no renovó, citando "pagamos por funciones que no usamos", "costo" y "el equipo ya usa otras herramientas" (`unverified`, brief AFPM). El upgrade a Max queda como resultado secundario: el research indica que se vende por seguridad, engagement e IA y no está probado que este problema lo mueva.

## Constraints

**De negocio:** presupuesto máximo de USD 5M; presentación en la conferencia CollabCon en ~5 meses desde el 15/09, aprox. febrero de 2027.

**Criterios que cualquier solución debe cumplir:** facilidad de uso, accesibilidad, compatibilidad con Microsoft 365, privacidad y seguridad corporativas, tiempo real, impacto mínimo en audio/video de la reunión.

**Heredadas:** IT controla qué se habilita por área, así que la adopción no depende solo de quien convoca. Lo que se genere en vivo y no viva en SharePoint hereda el problema de "no encuentro el archivo" (46% de los tickets de Archivos).

**Compliance:** Lucía Fernández no puede usar herramientas externas con datos de clientes (real); 4 de 27 españoles dicen lo mismo (survey, direccional).

## Beliefs

Ninguna coincide con una ya registrada. Relacionadas, sin duplicar: la #3 del producto (sobrecarga de reuniones) y la #6 y #7 de [colaboracion-en-vivo-reuniones](2026-09-15-2100-colaboracion-en-vivo-reuniones.md). Propuestas de registro en `product/overview.md`, pendientes de aprobación:

- `[opportunity: decisiones-sin-registro] [value]` En cuentas de Teams, quienes convocan reuniones de 8+ reescriben a mano lo decidido después de la mayoría de sus reuniones, y al menos 1 de cada 3 tuvo en los últimos 3 meses un caso en que alguien actuó sobre una versión distinta con ≥1 día de retrabajo. Si es <10%, el problema no justifica invertir. *(umbral propuesto)*
- `[opportunity: decisiones-sin-registro] [viability]` Entre las cuentas que bajan de plan o no renuevan por "pagamos por funciones que no usamos" (3,6%), el uso de las funciones de reunión que registran lo decidido (recap, notas) es menor que entre las que renuevan. Si el uso es igual, resolver esto no mueve la retención. *(umbral propuesto)*

## Research agenda

| Belief | Instrument | Decision it unlocks | By when |
|---|---|---|---|
| [value] | Datos del producto: en reuniones de 8+, qué porcentaje tiene notas o recap de IA generados y cuántas veces se abren después; qué porcentaje de convocantes reenvía o reescribe (si hay señal de eso) | Dimensionar el problema en cuentas y licencias antes de comprometer presupuesto | 1 a 2 semanas |
| [value] | Extender la encuesta (Q9, Q11 y un ítem de retrabajo) a cuentas fuera del segmento estrecho, y probar si el problema existe fuera de tecnología multinacional | Confirmar o achicar el alcance ampliado; hoy fuera del segmento es `assumption` | 3 a 4 semanas |
| [value] | Entrevistas con quienes deciden en reuniones chicas y con quienes actúan sobre lo decidido, reclutadas entre los opt-in de la encuesta (54 candidatos con contacto) | Saber si el problema vive en la reunión grande o en la chica, y cerrar el hueco de persona | Antes de fijar el alcance |
| [viability] | Datos del producto: cruzar uso de recap y notas con renovación y baja, en las cuentas del 3,6% frente a las que renovaron; y con CS, qué funciones citan como "no usadas" | Saber si vale priorizar esta oportunidad por retención | Antes de comprometer los USD 5M |
| [viability] | Entrevistas con decisores de IT y licencias, perfil Roberto, sobre qué usarían para justificar el gasto | Entender si el registro de lo decidido pesa en la renovación | Después del cruce de datos |

## Candidate ideas (not evaluated)

Son el punto de partida de `/explore-solutions`, no una lista corta:

- Cierre de decisiones asistido: la IA propone decisión, responsable y fecha, y quien convoca confirma (A1 en `product/solutions/2026-09-29-2155-colaboracion-en-vivo-reuniones.md`). — **chosen** (B1 `cierre-decisiones-asistido`, en prueba) · [soluciones](../solutions/2026-09-29-2205-decisiones-sin-registro.md)
- Ritual de cierre más plantilla de decisiones en las Notas de la reunión (A4 del mismo archivo). — **chosen** (B2 `ritual-cierre-plantilla`, en prueba) · [soluciones](../solutions/2026-09-29-2205-decisiones-sin-registro.md)
- Registro de decisiones por equipo o canal, buscable, tipo ADR (lo que Ricardo hace "a veces"). — **parked** (B3 `registro-decisiones-equipo`) · [soluciones](../solutions/2026-09-29-2205-decisiones-sin-registro.md)
- Publicar lo decidido a quienes no estuvieron, con la tarea creada (caso Diego: marketing de Chile esperaba el correo). — **parked** (B4 `publicar-lo-decidido`) · [soluciones](../solutions/2026-09-29-2205-decisiones-sin-registro.md)

A1 y A4 ya se compararon dentro de la otra oportunidad, pero no contra este alcance ampliado.

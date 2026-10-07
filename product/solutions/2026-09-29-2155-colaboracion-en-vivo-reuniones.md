---
opportunity: colaboracion-en-vivo-reuniones
status: testing-several
chosen: cierre-decisiones-asistido, ritual-cierre-plantilla
tests: product/tests/2026-10-06-2052-decisiones-sin-registro.md
---

# Solutions for: falta de confianza en la colaboración en vivo dentro de la reunión

## What the evidence says now

- Las dos creencias de valor (`[opportunity: colaboracion-en-vivo-reuniones] [value]` y la #2 del overview) quedaron `weakened`, no `contradicted`: solo 33% de quienes trabajan afuera usa Miro/Mural/FigJam y 53,5% trabaja sobre algo que ya existía (Jira, Confluence, dashboards); Whiteboard la probó y la dejó el 43% (survey, n=187, autoseleccionada; `product/insights/2026-09-29-2100-colaboracion-en-vivo-fuera-de-teams.md`).
- La creencia de viabilidad (`[viability]`, upgrade a Max 3,1%) quedó `weakened` por el research: Premium se vende por seguridad, engagement e IA, no por colaboración (secondary; `product/research/2026-09-15-2213-colaboracion-en-vivo-reuniones.md`).
- El dolor más fuerte es el registro de lo decidido: 24% no lo registra y 23% lo deja en un chat fuera de Teams (survey, n=182). En las 10 entrevistas (real) hay 10 casos de decisión que salió distinta de lo acordado (la guía lo preguntaba: muestra costo, no frecuencia); 6 de 10 dedican 20 a 60 min a reescribirla y 6 de 10 dicen que el recap de IA mezcla lo decidido con lo hablado.
- Whiteboard además se pierde después: 4 de 10 no la encontraron en la reunión siguiente, porque queda atada al chat de esa reunión.
- Abierto: peso de cada dolor en cuentas y licencias del segmento (datos de producto), si alguno mueve el upgrade (Ventas) y toda la factibilidad. Solo la entrevista de Ricardo Salinas tiene insight sintetizado; los conteos de las otras 9 salen de lectura directa y son provisorios.

## Baseline: what people do today

- **Tablero armado para la reunión** en Miro/FigJam con el link pegado en el chat (54% pega link, Q3). Pierden 5 a 10 min hasta que entran todos y votan con puntitos (survey O1/Q3; entrevistas `2026-09-25-1000-tomas-aguirre`, `2026-09-28-0900-javier-molina`, `2026-09-28-1500-valeria-castro`; real).
- **Trabajo ya existente**: comparten pantalla o link a Jira, Confluence o dashboards (74% de las herramientas que no son tableros ya existían, O1) y "señalan" con el mouse (Tomás, Andrés, Diego, Valeria; real).
- **Al cierre**: quien convoca reescribe a mano lo decidido en Jira, mail o Slack, usa el recap de IA solo para acordarse y cuenta manos o reacciones para votar (Andrés, Lucía, Ricardo; real).

## Alternatives

### A1. Cierre de decisiones asistido (`cierre-decisiones-asistido`)
Copilot propone decisión, responsable y fecha separando lo decidido de lo comentado. Quien convoca confirma en un paso antes de cortar; se publica en el chat y se crea la tarea. Ataca el registro. Persona: Ignacio Beltrán (`synthetic`, referencia directa del segmento); en real, Martina Rojas, Javier Molina, Paula Benítez. Reemplaza reescribir el recap a mano.

### A2. Whiteboard confiable y persistente (`whiteboard-confiable`)
Plantillas, agrupar, voto con tope, fluidez con 12–15 personas y VPN, y un link fijo que sobrevive a reprogramar. Ataca los tableros creados para la reunión y la pérdida posterior. Persona: Ignacio; también Lucía Fernández, para quien lo nativo es lo único permitido por compliance. Reemplaza Miro/FigJam en retros y plannings.

### A3. Herramientas externas dentro de la reunión, con acceso por identidad de Teams (`apps-externas-en-reunion`)
Miro, FigJam, Jira y Confluence en el panel de la reunión, habilitados por defecto por IT y con el login de Teams, sin link ni invitado. Ataca los 5–10 min de acceso y el saltar de ventana. Persona: Ignacio y Roberto Aguirre (`synthetic`, IT que habilita). No ayuda a Lucía. Reemplaza el link pegado en el chat.

### A4. Ritual de cierre + plantilla de decisiones (`ritual-cierre-plantilla`) — sin software nuevo
Guía para Team Leads (últimos 3 min: decisión, dueño, fecha, leído en voz alta) y plantilla "Decisiones" precargada en las Notas de la reunión existentes. Es lo más chico que podría funcionar: si alcanza, A1 sobra. Persona: Valentina Sosa (`synthetic`, primaria); en real, Diego Paredes y Sofía Martínez ("es disciplina", "cómo se cierra la reunión").

### A5. Votación en vivo con resultado registrado (`votacion-en-vivo`)
Poll en la reunión, con voto único o con tope, y resultado visible y guardado. Ataca converger: 39% vota afuera y 13% lo marca como lo más difícil. Persona: Ignacio (workshops con votación). Reemplaza manos contadas, Slido y puntitos.

## Comparison

| Alternative | Desirable | Feasible | Viable | Riskiest belief |
|---|---|---|---|---|
| A1 | strong (survey Q9/Q11 n=182 + 10/10 entrevistas real; incluye a Ricardo, que no usa nada externo) | to check with tech (el recap de Copilot ya existe y lo usa 36%; falta saber si separa decidido de comentado y si crea tareas; restricción de privacidad) | mixed (secondary: Premium se vende por IA y recaps; sin dato de que esto mueva el upgrade) | De lo que la IA propone como decisión en reuniones reales de 8+, ≥70% es correcto y se confirma en ≤2 min. Si más de 30% son ideas marcadas como decisión, vuelven a reescribir. *(umbral propuesto)* |
| A2 | mixed (survey: 43% la probó y la dejó, pero es 1/3 del uso externo; real: Tomás y Javier eligen Miro por la continuidad trimestral, no solo por features) | to check with tech (secondary: señales de desinversión, fuente de un competidor; ~4 meses hasta CollabCon y USD 5M) | weak (secondary: Zoom y Slack la incluyen en el tier estándar y Premium no se vende por colaboración: paridad, no upsell; retención `unknown`) | Los equipos que hoy arman el tablero en Miro/FigJam pasan a Whiteboard si tiene plantillas, agrupar, voto y link fijo. Si <5 de 10 equipos completan su retro o planning sin volver al link externo, no funciona. |
| A3 | mixed (survey Q6/Q7: 28% tarda ≥5 min, 61% con externos; real: 3 de 10 perdieron 5–10 min, pero Tomás y Javier no pueden editar por licencia de invitado o de filial y el login de Teams no lo arregla; solo 8% abrió la app en Teams) | to check with tech (secondary: apps existentes desde 2021-22, apagadas hasta que el admin global las habilita; depende de terceros e IT) | unknown (ninguna evidencia une apps integradas con renovación o upgrade) | El bloqueo es de login y habilitación, no de licencia de edición. Con la app habilitada y el login de Teams, ≥80% edita en <2 min. Si los que no entran siguen siendo invitados sin permiso, no resuelve. |
| A4 | mixed (real: Diego y Sofía dicen que es práctica; Lucía "escribir y moderar a la vez me cuesta"; Sofía tenía sección "Decisiones" y aun así perdió el caso SPEI; Notas: 31% no sabía que existían) | to check with tech (usa las Notas existentes; falta ver plantilla por defecto y anclaje a la serie; la guía no depende de tech) | weak (no vende licencias; su valor es costo casi cero y que mide si el problema es de herramienta o de práctica) | Quien hoy reescribe 20–60 min después usa la plantilla dentro de la reunión en ≥4 de 5 reuniones durante 4 semanas. Si la abandona en 2 semanas, no sirve. |
| A5 | mixed (survey: 39% vota afuera, 13% lo marca como lo más difícil; real: Andrés y Lucía cuentan a mano, Valeria tuvo doble voto; Ricardo dice que a mano alzada le alcanza y Paula duda de que votar sea decidir) | to check with tech | unknown | Los convocantes usan un poll nativo y confían en el resultado. Si en 10 reuniones lo usan <3 veces y siguen contando a mano, no sirve. |

A1 es la única con `strong` y con más citas que las demás, pero la encuesta (Q9, Q11) y la guía preguntaron directo por el registro de decisiones y "señalar" o "acceso por licencia" no tuvieron esa oportunidad: parte de la ventaja es del instrumento. Además, el `strong` vale para el dolor, no para la calidad de la IA.

## Decision

Maru eligió probar **A1 y A4 en paralelo** (`testing-several`), que coincide con la recomendación, así que no se registra entrada en `product/corrections.md`.

- **Razones de la recomendación:** el registro de lo decidido es el hueco más grande y aparece hasta en quien no usa herramientas externas; A1 toca a los tres tipos de usuario (tablero, Jira/Confluence y solo hablar) y apunta a IA y recaps, donde hoy se vende el plan superior. A4 es la prueba barata de si el fallo es de práctica o de herramienta.
- **Tests de A1 y A4:** son los mismos que B1 y B2 de `product/solutions/2026-09-29-2205-decisiones-sin-registro.md`: T1 y T2 para A1, T3 para A4. Diseñados en [tests](../tests/2026-10-06-2052-decisiones-sin-registro.md).
- **Regla de decisión:** si A4 alcanza (la usan en ≥4 de 5 reuniones y baja el retrabajo), A1 se posterga. Si la abandonan en 2 semanas por el esfuerzo de escribir mientras moderan, A1 gana.
- **Qué cambiaría el rumbo:** si tech dice que Copilot no separa decidido de comentado con precisión razonable, A4 pasa a ser la apuesta y A1 a `parked`; si Ventas muestra que "colaboración" en las renovaciones de Max significa co-crear y no cerrar, sube A2; si `[value]` pasa a `contradicted`, vuelta a investigar.

## Value proposition: A1 — cierre de decisiones asistido

Para Ignacio Beltrán (`synthetic`) y para quienes convocan reuniones grandes en el segmento:

- **Pain relieved:** 24% no registra lo decidido y 23% lo deja en un chat fuera de Teams (survey); quien convoca dedica 20 a 60 min a reescribirlo (6 de 10, real) y el recap mezcla decidido con comentado (6 de 10, real). El costo es concreto: dos días de retrabajo y un fin de semana de guardia (Ricardo), una semana de dos devs (Paula), dos semanas de trabajo (Sofía, Javier).
- **Gain created:** al cortar la reunión queda confirmada una lista "decisión · responsable · fecha", publicada donde el equipo trabaja y con la tarea creada; quien no habló o no estuvo lee lo mismo que quien sí.
- **Replaces:** reescribir a mano el recap, el mail y el hilo. Se cambia porque hoy cuesta 20 a 60 min por reunión y aun así falla.
- **Deliberately does not:** reemplazar Whiteboard o Miro, facilitar la votación o la co-creación, decidir por el grupo (siempre confirma una persona) ni resumir toda la reunión.

## Value proposition: A4 — ritual de cierre + plantilla

- **Pain relieved:** el mismo problema de registro, sin depender de desarrollo.
- **Gain created:** quien convoca cierra en 3 minutos con tres campos leídos en voz alta y las Notas de la reunión quedan con las decisiones.
- **Replaces:** la reescritura posterior. Se cambia porque es casi gratis de probar y porque, si funciona, el registro sale dentro de la reunión.
- **Deliberately does not:** usar IA, crear tareas en Jira, cambiar Whiteboard o las herramientas externas, ni garantizar que lo decidido se cumpla.

## Beliefs

- `[opportunity: colaboracion-en-vivo-reuniones] [value]` — referenciada tal como está registrada en `product/overview.md`.
- `[opportunity: colaboracion-en-vivo-reuniones] [viability]` — referenciada tal como está registrada en `product/overview.md`.
- `[feature: cierre-decisiones-asistido] [feasibility]` Copilot propone decisión, responsable y fecha en reuniones de 8+ con ≥70% de propuestas correctas, sin degradar audio/video ni violar la privacidad corporativa; si más de 30% de las "decisiones" propuestas son ideas o quedan incompletas, no es viable como está. *(propuesta de registro)*
- `[feature: cierre-decisiones-asistido] [value]` Quien convoca confirma lo propuesto en ≤2 min y deja de reescribir a mano lo decidido (hoy 20 a 60 min en 6 de 10 entrevistas), y quienes no estuvieron actúan según lo publicado. *(propuesta de registro)*
- `[feature: ritual-cierre-plantilla] [value]` Quien hoy reescribe lo decidido 20 a 60 min después usa la guía de cierre y la plantilla dentro de la reunión en ≥4 de 5 reuniones durante 4 semanas y el retrabajo baja; si la abandona en 2 semanas, el problema es de esfuerzo o de herramienta y no de práctica. *(propuesta de registro)*

## Discarded or parked

- A2 — parked: `desirable` mixed y `viable` weak (paridad con Zoom y Slack, no upsell). Vuelve si Ventas muestra que "colaboración" en las renovaciones de Max significa co-crear, o si tech confirma alcance y fecha antes de CollabCon. La pérdida de la pizarra (4 de 10) queda como señal a revisar aparte.
- A3 — parked: el riesgo probable es la licencia de edición y no el login. Vuelve si tech confirma que habilitación por defecto y login de Teams resuelven a los invitados; el dato de producto sobre cuántas cuentas del segmento tienen la app habilitada ya está en la agenda de la oportunidad.
- A5 — parked: sin evidencia de que un poll reemplace a Slido o a los puntitos; Ricardo y Paula matizan la necesidad. Vuelve si A1 y A4 dejan converger y votar como hueco principal.
- Agenda editable en vivo (idea candidata del brief) — parked: sin señal en la evidencia; Paula Benítez ya arma la agenda en las Notas.

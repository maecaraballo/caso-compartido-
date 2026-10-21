# Recap de IA centrado en decisiones (`cierre-decisiones-asistido`)

## Problem
Quien convoca reuniones de 8+ reescribe a mano lo decidido (20 a 60 min en 6 de 10 entrevistas). Aun así, quienes no estuvieron o no hablaron actúan sobre otra versión y hay días de retrabajo (10 de 10 entrevistas tienen un caso). El recap de IA no lo cierra: mezcla lo decidido con lo hablado, marca ideas como decisiones y no dice quién se comprometió. Es el hueco más grande de la encuesta: 24% no registra nada y 23% lo deja en un chat fuera de Teams (n=182). Importa ahora porque el recap y Copilot ya son parte de la inversión, y ahí es donde el research ubica lo que sostiene el plan Premium.

> Evidence: "El recap resume todo al mismo nivel. Dos páginas. No distingues qué se decidió de qué se comentó." — Javier Molina (real), costó una release movida 2 semanas. `product/interviews/2026-09-28-0900-javier-molina.md`
> Evidence: "Alguien dice 'podríamos pasar el release al 20' y en el resumen aparece 'se decidió pasar el release al 20'." — Paula Benítez (real), una semana de dos desarrolladores. `product/interviews/2026-09-28-1400-paula-benitez.md`
> Evidence: "El resumen automático sirve para saber de qué se habló pero no para saber qué quedó decidido." — R-149 (survey). `product/insights/2026-09-29-2100-colaboracion-en-vivo-fuera-de-teams.md`

## Who it's for
- **Ignacio Beltrán** (`primary`, `synthetic`, referencia directa del segmento): sus decisiones quedan mitad en FigJam y mitad en notas que nadie reabre.
- **Valentina Sosa** (`primary`): reenvía resúmenes porque no confía en que lean las notas.
- En real: Javier, Paula y Lucía son quienes hoy corrigen el recap a mano.
- Límite de alcance: Ricardo y Paula (n=2) dicen que la decisión real se toma en reuniones de 3 a 4, no en la grande. La evidencia es de reuniones de 8+.

## User journey (Ignacio; pasos tomados de Javier, Lucía y Paula)
1. **Trigger** — Termina un planning o design review de 12 a 15 personas en 3 países, con prioridades y dependencias acordadas, algunas con fecha.
2. Hoy abre el recap de Copilot: dos páginas, todo al mismo nivel. *(sin la función)*
3. En unos minutos (≤10 min después de terminar) recibe una lista **decisión · responsable · fecha**, con la cita del momento de la reunión en que salió cada una. Lo que fue idea no figura como decisión. *(entra la función)*
4. La revisa: borra o corrige lo que no era decisión y completa el responsable que faltaba. Hoy Paula tarda unos 10 min en esto.
5. Confirma, y la lista se publica en el chat o canal de la reunión, visible también para quien no estuvo.
6. **Outcome** — No reescribe nada. Un equipo de otro país lee exactamente lo decidido, no el "se habló de…".

Los pasos 2 a 4 salen de entrevistas reales. El final del paso 6 (que el otro equipo actúe sobre lo publicado) es un supuesto.

## Critical user stories

### 1. Propuesta que separa lo decidido de lo hablado
As Ignacio, I want que Copilot me proponga decisión, responsable y fecha con la cita de origen, so that no tengo que reconstruir lo decidido desde dos páginas de recap.

Acceptance criteria:
- [ ] La lista llega ≤10 min después de terminar la reunión.
- [ ] Cada ítem tiene decisión, responsable (o "sin responsable") y fecha (o "sin fecha"), más un enlace al momento de la transcripción.
- [ ] Una frase en condicional ("podríamos", "habría que evaluarlo") no aparece como decisión.
- [ ] Si falta responsable o fecha, queda marcado y no se completa por inferencia.
- [ ] *Edge:* si no se detectan decisiones, el mensaje dice "no se detectaron decisiones" y no inventa ítems.

Traces to: insight Q9/Q11; Javier, Paula, Lucía (real).

### 2. Confirmar o editar en menos de 2 minutos
As Ignacio, I want confirmar, editar o borrar cada ítem antes de que salga, so that nada se publica sin que yo lo avale.

Acceptance criteria:
- [ ] Se puede confirmar, editar o borrar cada ítem, y agregar uno que faltó.
- [ ] Nada se publica hasta que una persona confirma.
- [ ] Se registran los minutos entre apertura y confirmación.
- [ ] *Edge:* si no confirma en 24 h, la lista queda en borrador, no se envía a nadie y se le recuerda una vez.

Traces to: Paula (revisa 10 min por reunión desde el incidente de agosto).

### 3. Publicar lo confirmado para quien no estuvo
As Julián, I want leer lo mismo que quien habló, so that no actúo sobre el recap equivocado.

Acceptance criteria:
- [ ] La lista confirmada se publica en el chat o canal de la reunión, con "confirmado por {nombre}".
- [ ] Les llega a todos los invitados, incluidos quienes no asistieron.
- [ ] Muestra los ítems editados tal como quedaron, no la propuesta original.
- [ ] *Edge:* si la reunión se reprograma o es otra serie, la publicación sigue accesible desde la nueva invitación.

Traces to: Javier (México leyó el recap, no el hilo); Paula (las notas quedaron en la invitación vieja).

### 4. Cumplir privacidad y retención sin salir de Teams
As Lucía, I want que esto funcione dentro de las políticas de Teams, so that puedo usarlo con datos de clientes.

Acceptance criteria:
- [ ] Solo corre si el admin lo habilitó y la reunión tiene transcripción activa.
- [ ] Los participantes ven un aviso de que se están proponiendo decisiones.
- [ ] Lo generado queda bajo la retención corporativa, y tech confirma por escrito el cumplimiento.
- [ ] *Edge:* en una reunión sin transcripción, la función no aparece.

Traces to: Lucía Fernández (real); R-190 (survey, direccional).

## Hypothesis
Creemos que los Team Leads que convocan reuniones de 8+ y hoy reescriben lo decidido 20 a 60 min después van a confirmar la lista propuesta en ≤2 min y publicarla como su recap, porque reescribir les cuesta tiempo y cuando falla cuesta días.

Nos equivocamos si:
- menos de 70% de las propuestas es correcta, o más de 30% son ideas marcadas como decisión (T1);
- confirman rápido pero igual escriben su propio recap, o editan más de la mitad de los ítems (T2);
- menos de 2 de los 6 Team Leads la usan como su recap (T2).

## Alternatives considered
Explored in: `product/solutions/2026-09-29-2205-decisiones-sin-registro.md` (y A1–A5 de `product/solutions/2026-09-29-2155-colaboracion-en-vivo-reuniones.md`)
- B2 / A4 ritual de cierre + plantilla — **en prueba en paralelo**, no descartada. Si funciona (≥4 de 5 reuniones y baja el retrabajo), esta función se posterga.
- A2 Whiteboard confiable — parked: viabilidad `weak` (paridad con Zoom y Slack, no upsell).
- A3 apps externas con login de Teams — parked: el riesgo probable es la licencia de edición, no el login.
- A5 votación en vivo — parked: sin evidencia de que un poll reemplace a Slido o a los puntitos.
- B3 registro buscable por equipo — parked: nadie consulta un registro hoy.
- B4 publicar con tarea creada — parked: necesita una decisión ya capturada; la story 3 cubre solo la publicación.
- B5 decidir en reuniones chicas — parked: n=2 y viabilidad débil.

## Tested before spec
Metrics: `product/metrics/2026-10-20-2041-cierre-decisiones-asistido.md` (Nivel 1)

Tested in: `product/tests/2026-10-06-2052-decisiones-sin-registro.md`
- T1 precisión del cierre sobre ≥20 reuniones reales — designed, no corrido · creencia 8 (`feasibility`)
- T2 confirmación en ≤2 min y fin de la reescritura (concierge, 6 Team Leads) — designed, no corrido (se corre solo si T1 pasa) · creencia 9 (`value`)
- Riskiest belief not tested (declared): hoy no hay ningún resultado y la factibilidad es `to check with tech`.
- Decisiones de este spec, alineadas con lo que cubre T2 (sus resultados seguirán valiendo): la confirmación ocurre unos minutos después de terminar la reunión, no en vivo; y la creación de tareas en Planner o Jira queda fuera de esta versión. La confirmación en vivo, antes de cortar, es un nivel posterior y necesitaría su propio test.

## Assumptions
Ya registradas en `product/overview.md`:
- [feature: cierre-decisiones-asistido] [feasibility] (creencia 8) — owner: tech
- [feature: cierre-decisiones-asistido] [value] (creencia 9) — la parte "quienes no estuvieron actúan según lo publicado" no la cubre T2
- [opportunity: decisiones-sin-registro] [value] (creencia 11)
- [opportunity: decisiones-sin-registro] [viability] (creencia 12) — sin datos; gate antes de gastar en desarrollo

Registradas el 2026-10-13 con la aprobación de Maru (umbrales propuestos, no medidos):
- [feature: cierre-decisiones-asistido] [usability] (creencia 13) Quien convoca encuentra la lista y confirma dentro de Teams, sin instrucciones y sin salir a un enlace aparte, en ≥80% de las reuniones. T2 usa un mensaje con formulario, así que la superficie no está probada. — owner: UX
- [feature: cierre-decisiones-asistido] [value] (creencia 14) De lo publicado, ≥80% de los destinatarios lo abre y actúa sobre eso en 2 días, no sobre el recap ni el hilo viejo. — owner: PM

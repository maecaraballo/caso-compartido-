---
spec: product/specs/2026-10-13-2046-cierre-decisiones-asistido.md
exposure-plan: product/exposure-plans/2026-10-13-2148-cierre-decisiones-asistido.md
level: 1 — Propuesta privada de decisiones
status: designed
---

# Métricas para: Recap de IA centrado en decisiones (`cierre-decisiones-asistido`)

## Audiencia objetivo
Team Leads que convocan reuniones de 8+ con transcripción activa, habilitados por feature flag en el Nivel 1 (overview: Team Leads y mandos medios del segmento; plan: Nivel 1). El denominador es la persona que convoca, que en este nivel es la única que ve la lista. Entran solo quienes convocaron al menos una reunión elegible (8+, con transcripción) en la ventana. Los habilitados sin ninguna reunión elegible se reportan aparte, para que no bajen la adquisición por algo que no es de la función.
- Quienes participan no ven nada en este nivel, así que quedan fuera de las cuatro métricas. Entran en el Nivel 4.
- Tamaño: no está definido en el plan (pregunta abierta 1). La meta es ≥20 reuniones reales. Con menos de 10 personas, cada persona mueve la métrica 10 puntos o más, así que la lectura es direccional.
- Se corta por tipo de reunión (status, planning, design review) y por idioma mezclado o audio malo, porque el plan pide reportar por esos cortes.

## Frecuencia esperada
Semanal, y la ventana de retención es de una semana. `assumption` en parte:
- Ricardo Salinas (real) conduce de 4 a 5 reuniones grandes por semana (`product/interviews/2026-09-28-1700-ricardo-salinas.md`).
- La encuesta y T2 reclutan a quienes conducen ≥2 reuniones por semana (`product/surveys/2026-09-23-1944-colaboracion-en-vivo-fuera-de-teams.md`, `product/tests/2026-10-06-2052-decisiones-sin-registro.md`). Es un criterio de selección, no una medición.
- Valentina Sosa (sintética) dice unas 8 por semana.
- Nada mide cuántas reuniones de 8+ (no de más de 5) convoca un Team Lead por semana.

## Acquisition
- **Signal:** abre la lista de decisiones de una reunión elegible.
- **Expanded definition:** cuenta quien convoca y abrió la lista de al menos una reunión elegible del nivel. Abrirla es un acto suyo; la entrega es automática.
- **Calculation:** Team Leads que abrieron ≥1 lista / audiencia objetivo, sobre la duración del nivel (2 semanas o hasta ≥20 reuniones).
- **Target:** 80% · **Why:** la lista llega sola y es privada, así que no hay nada que descubrir. Si <80% no la abre, el problema es la entrega o el aviso, y la precisión no se puede juzgar con uso real. Es una propuesta sin línea base.
- **Events needed:** `feature_enrolled` {person_id, account_id, level, enrolled_at}; `meeting_eligible_ended` {meeting_id, convener_id, participants_count, meeting_type, transcript_active, ended_at}; `decision_list_generated` {meeting_id, convener_id, generated_at, minutes_after_end, items_count, review_items_count, incomplete_items_count, outcome: list | no_decisions_detected}; `decision_list_opened` {meeting_id, person_id, opened_at}.

## Activation
- **Signal:** abre la lista y abre la cita de origen de algún ítem, en dos reuniones distintas.
- **Expanded definition:** cuenta quien convoca que, en ≥2 reuniones distintas del nivel con outcome `list`, abrió la lista dentro de las 24 h de generada **y** abrió el enlace a la transcripción de ≥1 ítem.
- **Signal threshold:** abrir la lista y abrir ≥1 cita, en ≥2 reuniones · **Why:** la hipótesis es que la lista sirve como punto de partida para el recap propio. Como en este nivel no se puede confirmar ni editar, lo más cercano que se observa es revisar un ítem contra lo que se dijo, que es lo que hace quien decide si fiarse o corregir. Las dos reuniones separan la curiosidad inicial de una conducta repetida. · **Excludes:** abrir la lista sin abrir ninguna cita; abrirla pasadas 24 h; reuniones con "no se detectaron decisiones"; una sola reunión.
- **Calculation:** Team Leads que cumplen el umbral / audiencia objetivo, sobre la duración del nivel.
- **Target:** 60% · **Why:** es una propuesta sin línea base. Es menor que la adquisición porque pide una conducta más. Límite declarado: quien confía a ciegas no abre citas y no cuenta, así que esta métrica puede subestimar. El valor real (confirmar en ≤2 min, publicar como su recap) recién se observa en el Nivel 2.
- **Events needed:** `decision_item_source_opened` {meeting_id, item_id, person_id, opened_at}, además de los de adquisición.

## Retention
- **Signal:** sigue abriendo la lista de sus reuniones elegibles, por semana.
- **Expanded definition:** cuenta quien ya activó y, en la semana siguiente a la que se cumple la activación, abrió la lista dentro de las 24 h en ≥50% de las reuniones elegibles que tuvieron lista.
- **Retention curve:** cohortes por semana en que se cumple la activación; se sigue cada una en ventanas semanales. En un nivel de 2 semanas hay un solo punto de seguimiento, así que no se puede leer si la curva se aplana o sigue cayendo. La lectura es direccional y la forma de la curva se lee desde el Nivel 2, o con este nivel extendido.
- **Calculation:** Team Leads recurrentes / audiencia objetivo.
- **Target:** 50% · **Why:** es una propuesta sin línea base. Pide que casi la mitad de la audiencia vuelva sobre una conducta que ya es más exigente que abrir. Ventana semanal por la frecuencia esperada.
- **Events needed:** los de activación, más `meeting_eligible_ended` para el denominador por reunión. Valentina pidió registrar también las reuniones elegibles sin lista (sin transcripción, por ejemplo).

## Satisfaction
- **Instrument:** encuesta en la app (CSAT) · **Question:** "¿Qué tan satisfecho/a estás con esta lista de decisiones?" (1 a 5), más un comentario opcional: "¿Qué cambiarías?" · **When it shows:** una vez, al abrir la lista por tercera vez; si al cierre del nivel alguien no llegó a la tercera, se le muestra una vez al abrir la última · **Cut:** 4 o más.
- **Expanded definition:** cuenta quien convoca y respondió 4 o 5. Quien no respondió no cuenta como satisfecho.
- **Calculation:** Team Leads en 4 o más / audiencia objetivo. Se reporta aparte la tasa de respuesta y el porcentaje entre quienes respondieron.
- **Target:** 60% · **Why:** es una propuesta sin línea base. Como la tasa de respuesta cae con la adquisición, un número bajo se lee junto con ella.
- **Events needed:** `csat_shown` y `csat_answered` {person_id, meeting_id, score, comment, use_number}.

## Business metrics
`none declared` en el overview como métrica a seguir. La creencia 12 [viability] (uso de recap y notas menor en cuentas que bajan de plan que en las que renuevan) y el costo de procesar transcripciones (plan, validaciones en paralelo) son creencias o gates, sin objetivo declarado. Ninguna se mide con dos semanas de uso privado de un grupo chico, así que este nivel se mide solo para el usuario.

## Exposure plan reconciliation
- **Avanza si ≥70% de los ítems es correcto:** ninguna métrica AARS lo lee. Lo lee la hoja de etiquetado (clave de dos personas contra la salida de la IA, como en T1); los eventos aportan `item_id` y `meeting_type` para cruzarla.
- **Avanza si ≤30% son ideas marcadas como decisión:** igual, lo lee el etiquetado.
- **Precisión por tipo de reunión, y ítems dudosos como "revisar":** los cortes por `meeting_type` y `review_items_count` dejan reportarlo; no tiene objetivo AARS.
- **Duración (2 semanas o ≥20 reuniones):** las cuatro métricas se leen sobre esa misma ventana.
- **Se detiene si falla cualquiera de los umbrales de precisión:** ninguna métrica AARS lo puede revertir. Una adquisición o activación baja en este nivel no detiene el nivel: dispara el diagnóstico. No hay contradicción porque, en el Nivel 1, las metas AARS son diagnósticas y no puertas de avance.

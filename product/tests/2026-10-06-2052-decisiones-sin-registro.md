---
opportunity: decisiones-sin-registro
solutions: product/solutions/2026-09-29-2205-decisiones-sin-registro.md
status: designed
---

# Solution tests for: lo decidido en las reuniones no queda registrado de forma que todos actúen sobre lo mismo

## Why test
Están en prueba B1 (`cierre-decisiones-asistido`) y B2 (`ritual-cierre-plantilla`). El dolor está evidenciado en el segmento estrecho: 24% no registra lo decidido y 23% lo deja en un chat fuera de Teams (survey, n=182), 10 de 10 entrevistas con un caso costoso y 6 de 10 que reescriben 20 a 60 min (real). Que cada solución lo alivie no está evidenciado: nadie vio ni usó ni B1 ni B2. Lo más cercano a B1 es el recap actual, que 6 de 10 dicen que mezcla lo decidido con lo hablado, y lo más cercano a B2 es el caso de Sofía, que tenía una sección "Decisiones" y aun así perdió el caso SPEI. Los candidatos salen del pool de la encuesta, que es una muestra autoseleccionada del segmento estrecho: los resultados no se extienden al alcance ampliado.

## T1. cierre-decisiones-asistido: precisión del cierre sobre reuniones reales
- **Test status:** designed
- **Belief under test:** `[feature: cierre-decisiones-asistido] [feasibility]` Copilot propone decisión, responsable y fecha en reuniones de 8+ con ≥70% de propuestas correctas, sin degradar audio/video ni violar la privacidad corporativa; si más de 30% de las "decisiones" propuestas son ideas o quedan incompletas, no es viable como está.
- **Risk:** [feasibility]
- **Test type:** technical-test
- **What we do:** (1) Tech corre la función candidata (propone decisión · responsable · fecha, con la cita de origen) sobre transcripciones de reuniones de 8+. (2) Dos personas arman por separado la clave de respuestas antes de ver la salida de la IA: qué se decidió, quién y para cuándo, separado de ideas y comentarios; un tercero resuelve los desacuerdos y se informa el acuerdo entre los dos. (3) Se compara la salida con la clave. (4) Tech responde por escrito si puede crear la tarea en Planner o Jira, si procesar la transcripción cumple privacidad y retención, y si hay impacto en audio/video.
- **With whom:** Dueño: tech. ≥20 reuniones reales de 8+ con consentimiento, provistas por tech, de al menos 3 tipos (status, planning, design review), que den ≥50 propuestas de la IA.
- **Material needed:** el prompt de cierre (pide decisión, responsable, fecha y cita de origen; no resume la reunión), la guía de etiquetado con la regla "decisión vs idea" y la hoja de captura por propuesta (correcta, idea marcada como decisión, incompleta; decisión no detectada). Sin interfaz ni creación real de tareas.
- **Material:** pendiente (lo agrega `/build-solution-test`)
- **Duration:** 1 a 2 semanas
- **Signal and threshold:** Precisión = propuestas correctas (decisión real, con responsable correcto y fecha cuando existe) / propuestas totales. **≥70%.** Se registran aparte, sin umbral propio, las ideas marcadas como decisión y las decisiones no detectadas. Bloqueo = tech responde por escrito que privacidad, retención o impacto en audio/video no se cumplen con las condiciones del producto.
- **Decision rule:** continue si la precisión es ≥70% y no hay bloqueo · change si está entre 50% y 70%, o si el bloqueo tiene salida (por ejemplo, acotar a decisiones con responsable explícito); la versión nueva necesita su propio test · discard si es <50% o hay un bloqueo sin salida (queda solo B2)
- **Expected provenance:** real
- **Next step if it passes:** T2

## T2. cierre-decisiones-asistido: confirmación en ≤2 min y fin de la reescritura
- **Test status:** ready (se corre solo si T1 es `continue`)
- **Belief under test:** `[feature: cierre-decisiones-asistido] [value]` Quien convoca confirma lo propuesto en ≤2 min y deja de reescribir a mano lo decidido (hoy 20 a 60 min en 6 de 10 entrevistas), y quienes no estuvieron actúan según lo publicado. *Este test cubre solo las dos primeras partes; la tercera queda para B4 y el resultado no habla de ella.*
- **Risk:** [value]
- **Test type:** concierge
- **What we do:** (1) Reunión real de 8+ del Team Lead. (2) En ≤10 minutos recibe la salida de T1 sin tocar, como lista "decisión · responsable · fecha", y un enlace para confirmarla o editarla. (3) Se le pide que la use como el aviso al equipo en lugar de escribir el suyo. (4) Se registra cuánto tarda en confirmar y si igual escribe un recap propio.
- **With whom:** 6 Team Leads reales del pool de la encuesta (54 con contacto), que convocan ≥2 reuniones de 8+ por semana y hoy reescriben lo decidido; sin restricción de compliance que impida usar herramientas externas con datos de clientes. 3 reuniones cada uno, 18 en total. **Distintos de los 6 de T3.** Si tech no puede entregar la salida en ≤10 minutos, el test vuelve a diseño.
- **Material needed:** mensaje con la lista y un formulario de confirmación con marcas de tiempo (apertura y confirmación). Sin resumen de la reunión, sin creación de tareas, sin interfaz dentro de Teams. Hoja de captura por reunión: minutos hasta confirmar, ítems editados sobre el total, si publicó la lista o escribió otro recap.
- **Material:** [product/tests/materials/t2-cierre-decisiones-asistido/](materials/t2-cierre-decisiones-asistido/) — guion del concierge, mensaje con la lista, formulario de confirmación, hoja de captura, mensaje de reclutamiento. Pendiente antes de correr: `ENDPOINT` del formulario y condiciones de datos en el reclutamiento.
- **Duration:** 2 semanas
- **Signal and threshold:** Los dos tienen que cumplirse: (1) confirman en ≤2 min en ≥12 de 18 reuniones; (2) publican la lista confirmada, con a lo sumo la mitad de los ítems editados y sin recap propio paralelo, en ≥12 de 18 reuniones y en ≥2 de las 3 de cada uno de al menos 4 de los 6.
- **Decision rule:** continue si se cumplen ambos umbrales · change si confirman rápido pero igual reescriben, o editan más de la mitad de los ítems · discard si <2 de los 6 usan la lista como su recap
- **Expected provenance:** real
- **Next step if it passes:** ready for spec (con la tercera parte de la creencia abierta, a probar con B4)

## T3. ritual-cierre-plantilla: uso del ritual y la plantilla en 5 reuniones
- **Test status:** designed
- **Belief under test:** `[feature: ritual-cierre-plantilla] [value]` Quien hoy reescribe lo decidido 20 a 60 min después usa la guía de cierre y la plantilla dentro de la reunión en ≥4 de 5 reuniones durante 4 semanas y el retrabajo baja; si la abandona en 2 semanas, el problema es de esfuerzo o de herramienta y no de práctica. *Esta es la versión corta de 5 reuniones; el piloto de 4 semanas es el siguiente paso.*
- **Risk:** [value]
- **Test type:** concierge
- **What we do:** (1) Quien convoca recibe una guía de una página y la plantilla "Decisiones" para pegar en las Notas de la reunión. (2) La usa en sus próximas 5 reuniones de 8+: en los últimos 3 minutos lee en voz alta decisión, responsable y fecha. (3) Después de cada reunión manda el enlace a las Notas y llena un formulario de un minuto con los minutos que dedicó a reescribir. Antes de empezar declara cuántos minutos dedica hoy a reescribir.
- **With whom:** 6 Team Leads reales del pool de la encuesta, con el mismo criterio que T2 (convocan ≥2 reuniones de 8+ por semana y reescriben hoy). **Distintos de los de T2.** Se recluta a unos 20 candidatos para llegar a 12 entre T2 y T3.
- **Material needed:** guía de una página, plantilla lista para pegar y formulario de captura. Sin automatización ni integración con Jira.
- **Material:** pendiente (lo agrega `/build-solution-test`)
- **Duration:** hasta 5 reuniones, con tope de 3 semanas; control de abandono a los 14 días
- **Signal and threshold:** Los dos tienen que cumplirse: (1) las Notas tienen la sección completa (decisión, responsable, fecha) en ≥4 de 5 reuniones, en ≥4 de los 6 Team Leads (evidencia: el enlace a las Notas, no lo que cuentan); (2) la mediana de minutos de reescritura posterior es ≤50% de lo que declararon antes de empezar.
- **Decision rule:** continue si se cumplen ambos umbrales · change si la usan pero el retrabajo no baja, o solo la usan con apoyo; otra versión, con su propio test · discard si ≥3 de los 6 la abandonan antes de la tercera reunión (el problema es el esfuerzo de escribir mientras moderan; gana B1). Si T3 es `continue`, B1 se posterga aunque T1 haya pasado.
- **Expected provenance:** real
- **Next step if it passes:** piloto de 4 semanas con 8 a 10 Team Leads

## Results
*(lo agrega `/analyze-solution-tests`)*

## Decision
*(lo agrega `/analyze-solution-tests`)*

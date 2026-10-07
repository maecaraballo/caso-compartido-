---
opportunity: decisiones-sin-registro
status: testing-several
chosen: cierre-decisiones-asistido, ritual-cierre-plantilla
tests: product/tests/2026-10-06-2052-decisiones-sin-registro.md
---

# Solutions for: lo decidido en las reuniones no queda registrado de forma que todos actúen sobre lo mismo

## What the evidence now says

- **`[opportunity: decisiones-sin-registro] [value]`** (creencia 11) está recién registrada y sin evidencia en contra. El respaldo viene solo del segmento estrecho: 24% sin registro y 23% en un chat fuera de Teams (survey, n=182; `product/insights/2026-09-29-2100-colaboracion-en-vivo-fuera-de-teams.md`), 10 de 10 entrevistas con un caso costoso y 6 de 10 que reescriben 20 a 60 min (real; `product/interviews/`). El umbral propuesto todavía no se midió.
- **`[viability]`** (creencia 12, retención) no tiene datos. Falta el cruce de uso de recap y notas contra renovación y baja, primer ítem gratis de la agenda.
- **Alcance ampliado:** fuera del segmento estrecho el problema es `assumption`.
- Ricardo y Paula (real, n=2) dicen que la decisión real se toma en reuniones de 3 a 4 personas, no en la grande; 7 de 10 entrevistados deciden hoy en grupos de 8 a 14.
- La oportunidad nace de una encuesta y una guía que preguntaban por el registro de decisiones: el 10/10 muestra costo, no frecuencia.

## Baseline: what people do today

- **Reescritura a mano:** quien convoca reescribe lo decidido en Jira, mail o Slack 20 a 60 min después (6 de 10, real); Lucía saca una captura y la pega en Confluence.
- **Recap de IA:** lo usan para acordarse de qué se habló; marca ideas como decisiones o no dice quién se comprometió (6 de 10, real).
- **ADR:** Ricardo lo escribe "a veces" y nadie lo fue a buscar (real; `product/insights/2026-09-29-2110-ricardo-salinas.md`).
- **Costo:** de 1 semana de dos devs (Paula) a 2 semanas de trabajo (Sofía) o de una release (Javier).

## Alternatives

### B1. Cierre de decisiones asistido (`cierre-decisiones-asistido`)
Copilot propone decisión, responsable y fecha separando lo decidido de lo comentado, y quien convoca confirma antes de cortar. Mecanismo: automatizar la captura. Persona: Valentina Sosa e Ignacio Beltrán (`primary`, sufren el problema). Reemplaza el recap y la reescritura a mano.

### B2. Ritual de cierre + plantilla de decisiones (`ritual-cierre-plantilla`) — sin software nuevo, lo más chico que podría funcionar
Guía de 3 minutos (decisión, dueño, fecha, leído en voz alta) y plantilla "Decisiones" en las Notas existentes. Mecanismo: proceso. Persona: Valentina. Reemplaza la reescritura posterior.

### B3. Registro de decisiones por equipo, buscable (`registro-decisiones-equipo`)
Un lugar único por equipo o canal con qué se decidió, por qué y quién, al estilo ADR. Mecanismo: memoria y recuperación. Persona: Ignacio (Compliance pregunta "por qué decidimos esto") y Julián Ferreyra (`secondary`, retoma decisiones viejas). Reemplaza hilos de Slack y capturas.

### B4. Publicar lo decidido a quienes no estuvieron, con la tarea creada (`publicar-lo-decidido`)
Con una decisión ya confirmada, se distribuye al canal y a quienes actúan, con la tarea abierta. Mecanismo: distribución. Persona: Julián. Reemplaza el mail o resumen reenviado a mano.

### B5. Decidir en reuniones chicas, informar en las grandes (`decidir-en-chico`)
Política: las reuniones de 8+ son de estado y alineación; lo que hay que decidir se resuelve entre 3 y 4 personas con acta mínima. Mecanismo: eliminar la necesidad. Persona: Ignacio. Reemplaza decidir con 10 personas mirando.

## Comparison

La viabilidad se mide contra retención en la renovación. Todo lo `real` y `survey` viene del segmento estrecho.

| Alternative | Desirable | Feasible | Viable | Riskiest belief |
|---|---|---|---|---|
| B1 | mixed (pain evidenced, relief not tested: survey Q9/Q11 n=182; real 10/10 entrevistas con caso costoso; 6/10 recap mezcla decidido y hablado) | to check with tech (Copilot ya genera recap y lo usa 36%; falta precisión decidido/comentado, creación de tareas y privacidad) | mixed (unverified: el motivo de baja "funciones que no usamos" es atacable por una función muy usada; assumption: que el uso del recap retenga) | ≥70% de lo que la IA propone como decisión en reuniones de 8+ es correcto y se confirma en ≤2 min; si >30% son ideas marcadas como decisión, vuelven a reescribir. *(umbral propuesto)* |
| B2 | mixed (real: Diego y Sofía dicen "disciplina"; Lucía "escribir y moderar a la vez me cuesta"; Sofía tenía sección "Decisiones" y aun así perdió SPEI) | to check with tech (usa las Notas existentes; la guía no lo necesita) | unknown (no cambia lo que se paga; costo casi cero y mide práctica vs herramienta) | Quien hoy reescribe usa la plantilla dentro de la reunión en ≥4 de 5 reuniones durante 4 semanas; si la abandona en 2, no sirve. |
| B3 | mixed (real: Martina "el por qué se pierde", Javier "no hay acta"; survey Q11: continuidad 12%; synthetic: Ignacio y Julián; Ricardo lo hace "a veces" y "nadie lo fue a buscar") | to check with tech (¿dónde vive? SharePoint/Loop heredan "no encuentro el archivo", 46% unverified) | unknown | Quien necesita el "por qué" lo busca en el registro y no le pregunta a un compañero: a las 4 semanas ≥1 consulta por equipo por semana; si nadie lo consulta, no sirve. |
| B4 | mixed (real: Diego, Andrés y Javier, destinatarios que actuaron sobre otra versión; la encuesta no midió quién actúa) | to check with tech (canales, tareas en Planner/Jira, privacidad) | unknown | De lo publicado, ≥80% de los destinatarios lo abre y actúa en 2 días; si siguen actuando sobre el recap o el hilo viejo (caso Javier), no sirve. Necesita una decisión ya capturada. |
| B5 | weak (real n=2: Paula y Ricardo; 7 de 10 deciden hoy en grupos de 8 a 14; synthetic: Valentina dice que la cultura espera "que todo se hable") | unknown (política, no desarrollo; depende de CS y marketing y de cada empresa) | weak (no cambia lo que se paga ni el uso de funciones) | Al menos la mitad de las decisiones que hoy se toman en reuniones de 8+ puede moverse a 3–4 personas sin demora de más de 2 días; si no, no aplica. |

El dolor de B1 está evidenciado, pero esa evidencia es del problema y en parte del instrumento que originó la oportunidad; nadie reaccionó a la solución, por eso `mixed`. Ninguna alternativa tiene `strong` en viabilidad. B3 y B4 dependen de que la decisión ya esté capturada por B1 o B2.

## Decision

Maru eligió probar **B1 y B2 en paralelo** (`testing-several`), que coincide con la recomendación, así que no se registra entrada en `product/corrections.md`.

- **Razones:** son las dos que atacan el registro en el origen y ninguna compromete presupuesto de desarrollo.
- **Tests de B1:** T1 (factibilidad, creencia 8) y T2 (valor, creencia 9), diseñados en [tests](../tests/2026-10-06-2052-decisiones-sin-registro.md). T2 se corre solo si T1 pasa.
- **Test de B2:** T3 (valor, creencia 10), en una versión corta de 5 reuniones con 6 Team Leads; las 4 semanas con 8 a 10 son el paso siguiente si pasa. Diseñado en [tests](../tests/2026-10-06-2052-decisiones-sin-registro.md).
- **Gate:** sin gasto de desarrollo hasta cruzar uso de recap y notas contra renovación y baja (creencia 12). Si el uso es igual entre cuentas que renuevan y cuentas que bajan, la creencia 12 se cae y esto no mueve la retención.
- **Regla entre B1 y B2:** si B2 alcanza (≥4 de 5 reuniones y baja el retrabajo), B1 se posterga; si la abandonan en 2 semanas por el esfuerzo de escribir mientras moderan, B1 gana.
- **Qué cambiaría el rumbo:** si tech dice que la IA no separa decidido de comentado con precisión razonable, queda solo B2; si la encuesta ampliada muestra que el problema no existe fuera del segmento estrecho, el alcance vuelve a ser el estrecho; si `[value]` da <10%, vuelta a investigar.
- **Relación con el otro archivo:** B1 y B2 son A1 y A4 de `product/solutions/2026-09-29-2155-colaboracion-en-vivo-reuniones.md`. Son las mismas pruebas, ahora con esta oportunidad como padre natural.

## Value proposition: B1 — cierre de decisiones asistido

Para Valentina Sosa e Ignacio Beltrán (`primary`, `synthetic`) y para quienes convocan reuniones de 8+:

- **Pain relieved:** 24% no registra lo decidido y 23% lo deja en un chat fuera de Teams (survey); quien convoca dedica 20 a 60 min a reescribirlo (6 de 10, real) y el recap mezcla decidido con comentado (6 de 10, real). Costo: 2 días de retrabajo y guardia de fin de semana (Ricardo), 1 semana de dos devs (Paula), 2 semanas de trabajo (Sofía).
- **Gain created:** al cortar la reunión queda confirmada una lista "decisión · responsable · fecha", publicada donde el equipo trabaja y con la tarea creada.
- **Replaces:** reescribir a mano el recap, el mail y el hilo; se cambia porque hoy cuesta 20 a 60 min por reunión y aun así falla.
- **Deliberately does not:** decidir por el grupo (siempre confirma una persona), resumir toda la reunión, ni ocuparse de la co-creación o la votación.

## Value proposition: B2 — ritual de cierre + plantilla

- **Pain relieved:** el mismo problema de registro, sin depender de desarrollo.
- **Gain created:** quien convoca cierra en 3 minutos con tres campos leídos en voz alta y las Notas quedan con las decisiones.
- **Replaces:** la reescritura posterior; se cambia porque es casi gratis de probar y, si funciona, el registro sale dentro de la reunión.
- **Deliberately does not:** usar IA, crear tareas en Jira, ni garantizar que lo decidido se cumpla.

## Beliefs

Todas referenciadas desde `product/overview.md`, sin nuevos registros:

- `[opportunity: decisiones-sin-registro] [value]` (creencia 11)
- `[opportunity: decisiones-sin-registro] [viability]` (creencia 12)
- `[feature: cierre-decisiones-asistido] [feasibility]` (creencia 8)
- `[feature: cierre-decisiones-asistido] [value]` (creencia 9)
- `[feature: ritual-cierre-plantilla] [value]` (creencia 10)

## Discarded or parked

- B3 — parked: sin evidencia de que alguien consulte un registro (Julián prefiere preguntarle a un compañero, Ricardo escribe el ADR "a veces"). Vuelve si B1 o B2 producen decisiones capturadas y hay señal de que se buscan después, o si el "no encuentro el archivo" resulta un problema de SharePoint y no de Teams (creencia 5 del producto).
- B4 — parked: necesita una decisión ya capturada. Vuelve después de B1 o B2, si los destinatarios siguen actuando sobre otra versión.
- B5 — parked: evidencia fina (n=2) y viabilidad débil. Vuelve si la encuesta ampliada muestra que la mayoría ya decide en reuniones de 3 a 4 y solo falta registrar y comunicar.

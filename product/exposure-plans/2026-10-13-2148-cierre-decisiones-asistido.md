# Plan de exposición: Recap de IA centrado en decisiones (`cierre-decisiones-asistido`)

Spec: `product/specs/2026-10-13-2046-cierre-decisiones-asistido.md`

**Hipótesis (tomada de la spec):** Creemos que los Team Leads que convocan reuniones de 8+ y hoy reescriben lo decidido 20 a 60 min después van a confirmar la lista propuesta en ≤2 min y publicarla como su recap, porque reescribir les cuesta tiempo y cuando falla cuesta días.

**Secuencia de creencias:** primero, que la lista sea correcta (creencia 8). Si no lo es, confirmar rápido no significa nada. Segundo, que quien convoca confirme rápido y la use como su recap (creencia 9). Tercero, que lo encuentre y lo confirme dentro de Teams sin instrucciones (creencia 13). Cuarto, que quienes no estuvieron actúen sobre lo publicado (creencia 14).

---

## Nivel 1: Propuesta privada de decisiones
- **Qué se revela:** al terminar una reunión de 8+ con transcripción, quien convoca recibe en ≤10 min una lista **decisión · responsable · fecha** con enlace al momento de la transcripción. Los ítems incompletos dicen "sin responsable" o "sin fecha", y los de cita dudosa dicen "revisar". El encabezado aclara que solo cubre la transcripción. **Sigue oculto:** editar, confirmar y publicar. Nadie más ve la lista.
- **Creencia:** la lista separa lo decidido de lo hablado con precisión suficiente para servir de punto de partida, sin presentar ideas como decisiones.
- **Audiencia:** los Team Leads que convocan reuniones de 8+ con transcripción activa, incluyendo reuniones con idioma mezclado y audio malo.
- **Duración:** 2 semanas, o hasta juntar ≥20 reuniones reales.
- **Validación:**
  - **Avanza si:** ≥70% de los ítems propuestos es correcto **y** ≤30% son ideas marcadas como decisión. La precisión se reporta por tipo de reunión, y los ítems dudosos aparecen como "revisar".
  - **Se detiene si:** cualquiera de los dos umbrales falla. Se corrige el modelo o se descarta la función, y el Nivel 2 no corre.

## Nivel 2: Confirmar, editar y publicar en el chat de la reunión
- **Qué se revela (suma al Nivel 1):**
  - Confirmar, editar, borrar o agregar ítems.
  - Confirmar toda la lista en un solo paso.
  - Marcas "listo" frente a incompleto.
  - Publicación en el chat o canal de la reunión con "confirmado por {nombre}", editada tal como quedó.
  - Registro de minutos hasta confirmar y de listas sin confirmar.
  - **Sigue oculto:** entrada nativa en Teams, recordatorios, notificación directa a quienes no asistieron.
- **Creencia:** quien convoca confirma en ≤2 min y publica la lista como su recap, sin escribir el suyo.
- **Audiencia:** los mismos Team Leads (los 6 del concierge T2).
- **Duración:** 2 a 3 semanas.
- **Validación:**
  - **Avanza si:** la mediana hasta confirmar es ≤2 min, editan ≤50% de los ítems y ≥2 de los 6 la usan como su recap sin enviar uno propio.
  - **Se detiene si:** confirman rápido pero igual escriben su recap, editan más de la mitad, o <2 de los 6 la usan. Se revisa el diseño de la lista o la oportunidad.

## Nivel 3: Dentro del flujo de Teams
- **Qué se revela (suma al Nivel 2):**
  - Entrada nativa en Teams para encontrar y confirmar la lista, en lugar de un enlace aparte.
  - Recordatorios a las 4 h y a las 24 h.
  - Borrador accesible 7 días.
  - Publicación que sigue accesible si la reunión se reprograma o cambia de serie.
  - Aviso a los participantes de que se proponen decisiones.
- **Creencia:** quien convoca encuentra la lista y confirma dentro de Teams, sin instrucciones y sin salir a un enlace aparte.
- **Audiencia:** los Team Leads que convocan reuniones de 8+, ampliados a quienes no participaron en los niveles anteriores.
- **Duración:** 2 semanas.
- **Validación:**
  - **Avanza si:** ≥80% de las reuniones se confirma sin instrucciones y dentro de Teams.
  - **Se detiene si:** <50%. Entre 50% y 80% se itera la superficie antes de avanzar. *(umbral de stop propuesto, no está en la spec)*

## Nivel 4: Llega a quienes no estuvieron
- **Qué se revela (suma al Nivel 3):** notificación directa a todos los invitados, incluidos quienes no asistieron, con enlace desde la invitación nueva si la reunión se reprograma.
- **Creencia:** quienes no estuvieron abren la lista confirmada y actúan sobre ella, no sobre el recap ni el hilo viejo.
- **Audiencia:** invitados de las reuniones de 8+ con lista publicada, sobre todo quienes no asistieron o no hablaron.
- **Duración:** 2 semanas.
- **Validación:**
  - **Avanza si:** ≥80% de los destinatarios abre la lista y actúa sobre ella en 2 días, y baja el retrabajo reportado.
  - **Se detiene si:** <50%. Entre 50% y 80% se ajusta el canal. Un recap que nadie lee no justifica seguir. *(umbral de stop propuesto)*

---

## Mecanismo de revelado
**Recomiendo feature flags.** El motivo es que los Niveles 1 y 2 se limitan a un grupo chico de Team Leads por rol y comportamiento (convocan 8+, con transcripción). El desarrollo incremental no puede dar ese recorte, porque expone a toda la población del despliegue. Ingeniería tiene la decisión final.

## Validaciones en paralelo
- **Privacidad y retención (story 4):** tech confirma por escrito que lo generado queda bajo la retención corporativa, que el admin habilita la función y que corre solo con transcripción activa. Es una precondición del Nivel 1 si se usan reuniones con datos de clientes.
- **Viabilidad (creencia 12, sin datos):** costo de procesar transcripciones a escala frente a lo que sostiene el plan Premium. Es un gate antes de gastar en desarrollo.
- **Ritual de cierre + plantilla (B2/A4):** sigue probándose en paralelo. Si funciona (≥4 de 5 reuniones y baja el retrabajo), esta función se posterga.
- **Factibilidad técnica (`to check with tech`):** no hay ningún resultado todavía. Conviene tenerla antes de armar el Nivel 1.

## Preguntas abiertas
1. ¿Los 6 Team Leads del Nivel 2 son los de T2, y quién los recluta? Hay que juntar ≥20 reuniones reales para el Nivel 1.
2. ¿En el Nivel 2 la superficie es el mensaje con formulario de T2, y el Nivel 3 la reemplaza? Un reemplazo choca con "los niveles solo suman". ¿O el formulario se mantiene como alternativa?
3. ¿Cómo se mide "no escribió su propio recap" en el Nivel 2? ¿Observación, entrevista o autorreporte?
4. Los umbrales de stop de los Niveles 3 y 4 son propuestos y los de avance salen de la spec. ¿Se aceptan?
5. ¿Quién es el owner de cada creencia nueva? Tech tiene la 8, UX la 13 y PM la 14.
6. Fuera de este plan: la publicación automática sin confirmar, la confirmación en vivo y las reuniones de 3 a 4 personas. Cada una necesitaría su propio test.

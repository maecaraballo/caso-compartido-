---
date: 2026-10-13
source: synthetic
spec: product/specs/2026-10-13-2046-cierre-decisiones-asistido.md
panel: ignacio-beltran (primary), valentina-sosa (primary)
---

# Crítica de personas — Spec: "Recap de IA centrado en decisiones" (`cierre-decisiones-asistido`)

**Documento revisado:** `product/specs/2026-10-13-2046-cierre-decisiones-asistido.md`

**Composición del panel:** 2 primary. No hay ningún tertiary ni negative, así que es una lectura propensa a ser complaciente. El spec tiene implicancias de permiso (el admin habilita, transcripción activa, retención) y de alcance, por lo que conviene sumar a Roberto Aguirre (tertiary) y a Camila Duarte (negative). Ver la síntesis. Todo lo de abajo es `synthetic`: sirve para ensayar el spec, no cuenta como evidencia de que la función funciona.

---

### Ignacio Beltrán — Engineering Manager, empresa de tecnología multinacional · primary

**Overall rating:** 4/5

**Strengths:**
- Ataca lo que más me duele después de un planning: mis decisiones quedan mitad en FigJam y mitad en notas que nadie reabre, y el recap de Copilot hoy es "se habló de…". Una lista decisión · responsable · fecha con cita al momento de la transcripción es justo lo que Compliance me pide cuando pregunta "por qué decidimos esto".
- Que nada se publique sin que yo confirme me da el control que necesito. Un recap que sale solo y se equivoca me cuesta más que no tener recap.
- Que corra bajo la retención corporativa y lo apruebe el admin responde a la objeción de Plataforma/IT antes de que me la hagan.

**Concerns:**
- Mis decisiones más importantes no pasan solo por lo que se dice. En el planning, las prioridades se mueven en el tablero (Miro o FigJam) y las dependencias con fecha se ven en pantalla. Si la IA lee solo la transcripción, se pierde lo que se decidió arrastrando un post-it. El spec no dice qué pasa con eso.
- Hablo con equipos de Buenos Aires, Ciudad de México y Austin, con acentos y mezcla de español e inglés. No hay ningún criterio de aceptación sobre idioma mezclado ni sobre transcripciones malas. Si T1 se corre solo con reuniones limpias, el 70% me suena optimista.
- Si confirmo "unos minutos después" y el equipo de México ya cortó por la hora, la lista llega al canal cuando nadie la va a leer hasta mañana. Seguimos con el problema de que cada uno actúe sobre lo que entendió.
- Las decisiones reales a veces se toman después, en una llamada de 3 o 4 personas. La función solo cubre la reunión grande y eso no está dicho.

**Suggestions:**
- Declarar qué fuentes lee (transcripción, chat de la reunión, pantalla compartida) y qué se pierde. Permitir agregar a mano lo decidido en un tablero (ya existe "agregar un ítem") y decirlo en el flujo.
- Sumar a T1 reuniones con idioma mezclado y mala conexión, y reportar la precisión por tipo de reunión.
- Que quien tiene un ítem asignado reciba aviso directo en cuanto se confirma, sin esperar a que lea el canal.

Si la propuesta separa de verdad una idea de una decisión, me ahorra la media hora que hoy pierdo. Pero solo la voy a usar en serio si revisar la lista me lleva menos que escribirla yo.

---

### Valentina Sosa — Gerente de Operaciones (Team Lead), empresa de logística mediana · primary

**Overall rating:** 3/5

**Strengths:**
- Hoy reenvío resúmenes a mano porque no confío en que lean las notas. Una lista corta de "quién hace qué para cuándo" publicada donde el equipo trabaja es mucho mejor que mi mail.
- Me gusta que la decisión de si es una decisión o una idea la tome yo, no la herramienta.
- La parte de "no inventa responsable ni fecha" me da confianza. En mi equipo, un responsable equivocado es peor que ninguno.

**Concerns:**
- Convoco unas 8 reuniones grandes por semana. Si cada una me deja una lista para revisar y confirmar, sumé un trabajo más. Si encima no confirmo en 24 h, el spec dice que queda en borrador y no sale. O sea, vuelve a no haber registro, igual que hoy. En mi semana típica eso va a pasar.
- Muchas de mis reuniones incluyen proveedores o clientes que no usan Teams. No sé qué pasa con la transcripción y el aviso cuando hay externos, y si las notas del proveedor quedan dentro de la lista.
- Publicar la lista en el chat no garantiza que alguien la lea. Hoy tampoco leen las notas. Si la función no los hace actuar, solo cambió el lugar donde no leen.
- No quiero otra función que Dirección vea "sin uso" en la renovación. El spec mide cuánto tardo en confirmar, pero no mide cuántas reuniones pasan realmente por la función.

**Suggestions:**
- Que confirmar sea un solo paso cuando no cambio nada, y que los ítems con responsable y fecha completos salgan marcados como "listos".
- Definir qué pasa si no confirmo: un recordatorio, o que se publique solo la parte que ya tiene responsable y fecha con la etiqueta "sin confirmar".
- Contar en el piloto cuántas de mis reuniones de 8+ la usan, no solo cuánto tardo cuando la uso.

Si me ahorra los 20 minutos de reescribir sin sumarme otra tarea de revisión, la adopto. Si me agrega un paso obligatorio por reunión, la uso dos semanas y la abandono, como me pasó con las notas.

---

## Síntesis del panel

**Composición:** 2 primary, 0 tertiary, 0 negative. Los dos puntúan alto o medio-alto porque el spec les toca el dolor, así que la lectura es optimista. Antes de pasar a tests conviene sumar a **Roberto Aguirre** (tertiary: aprueba la habilitación, retención y gasto) y a **Camila Duarte** (negative: para confirmar el límite del alcance). Lucía Fernández (real) ya dio la señal de compliance que Roberto probablemente repetiría.

**Puntos de acuerdo:**
- **La revisión humana es lo mejor del spec y a la vez su costo oculto.** Los dos valoran que nada se publique sin confirmar. Los dos temen que la confirmación se convierta en un trabajo por reunión.
- **Los dos dudan de que publicar alcance para que se lea.** Ignacio lo pone como zona horaria; Valentina, como "tampoco leen las notas". La story 3 supone que publicar basta, y esa es la creencia 14, hoy sin test.
- **Los dos piden medir uso real, no solo calidad de la IA.** Hoy T1 y T2 miden precisión y tiempo de confirmación, pero no cuántas reuniones pasan por la función.

**Conflictos a resolver:**
- **Control vs. fricción.** Ignacio quiere revisar con cuidado; Valentina quiere confirmar en un paso. Hay que decidir el default: ¿se publica lo que está completo o todo espera confirmación? Hoy el spec elige esperar siempre, y eso favorece a Ignacio.
- **Alcance de la fuente.** Ignacio necesita que cuente lo decidido en tableros y en pantalla; Valentina casi no usa tableros. El spec solo cubre la transcripción.

**Cambios de mayor impacto sugeridos por el panel:**
1. **Declarar lo que la función no ve:** decisiones tomadas en tableros, en pantalla compartida o en una llamada posterior de 3 o 4 personas. Agregar un criterio de aceptación y sumar a T1 reuniones con idioma mezclado y mala conexión.
2. **Definir qué pasa cuando no se confirma y reducir la carga de confirmar:** confirmación en un paso cuando está todo completo, y un comportamiento explícito a las 24 h (recordatorio o publicación parcial con etiqueta). Si no, el borrador sin confirmar reproduce el problema de hoy.
3. **Cerrar el hueco de lectura:** aviso directo a quienes tienen un ítem asignado, y medir en T2 cuántas de sus reuniones de 8+ pasaron realmente por la función, no solo el tiempo de confirmación.

**Nota de provenance:** ambas personas son `synthetic`. Los números del spec (70%, 80%, ≤2 min) siguen siendo umbrales propuestos.

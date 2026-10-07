# T2 · Guion del concierge: quién hace de sistema

**Qué hace que esto funcione:** el Team Lead recibe, a ≤10 minutos de terminada su reunión, la salida de T1 **sin tocar**, como lista "decisión · responsable · fecha", y un enlace para confirmarla o editarla. Todo lo demás lo hace una persona detrás de escena (operador), y el Team Lead no tiene por qué verlo.

**Lo que este guion no hace:** no cambia qué se mide (confirmación en ≤2 min; lista publicada con a lo sumo la mitad de ítems editados y sin recap propio paralelo), ni los umbrales. Eso vive en el archivo de tests.

**Roles:** *operador* = quien sigue este guion (coordina, envía, registra). *Tech* = quien corre la función de T1 sobre la transcripción.

## Antes de empezar (una vez)
1. Completar `ENDPOINT` en `03-formulario-confirmacion.html` y probar de punta a punta con una reunión ficticia: abrir el enlace, confirmar, y ver que la fila llega con `abierto_en`, `confirmado_en`, `items_total` e `items_editados`. Sin registro de las dos marcas de tiempo, el test no puede leerse: no empezar.
2. Probar la vista `#operador` (agregar `#operador` al final de la URL del archivo): pegar una lista de ejemplo y generar el enlace.
3. Dejar acordado con tech, por escrito, cómo llega la transcripción de cada reunión y quién corre la función. El canal es el mismo que usa T1.
4. Armar la hoja de captura (`04-hoja-de-captura.csv`) y cargar a los 6 Team Leads con su procedencia. Verificar que **ninguno** es de T3.

## Por cada reunión (18 en total: 3 por Team Lead)

### Día anterior
- Confirmar con el Team Lead la fecha y hora, y que son ≥8 personas. Anotar `reunion_id` (ej. `TL3-R2`).
- Confirmar que los asistentes están informados de que la transcripción se procesa (mismo criterio de consentimiento que T1).

### Paso 1 · Termina la reunión (t0)
- **El Team Lead ve:** nada nuevo. Hace su reunión como siempre.
- **Detrás de escena:** anotar `fin_reunion` (hora real en que terminó). Tech toma la transcripción.
- **Tiempo máximo:** —

### Paso 2 · Entrega de la lista (t0 + 10 min como máximo)
- **Detrás de escena:** tech corre la función de T1. El operador copia la salida **tal como sale**: no corrige, no reordena, no agrega ni quita ítems, no completa responsables o fechas faltantes. Si falta un dato, queda vacío.
- El operador pega la salida en la vista `#operador` (una línea por ítem: `decisión | responsable | fecha`), genera el enlace y envía el mensaje de `02-mensaje-con-la-lista.md`.
- **Anotar `hora_envio`** y `items_propuestos`.
- **El Team Lead ve:** el mensaje con la lista y el enlace.
- **Tiempo máximo:** 10 minutos desde `fin_reunion`. Si se pasa, se envía igual y se marca `entrega_tardia = sí`. Cualquier entrega tardía se avisa a quien diseñó los tests antes de seguir con más reuniones: es la condición que devuelve el test a diseño.

### Paso 3 · El Team Lead confirma o edita
- **El Team Lead ve:** la lista en el formulario, con campos editables y la opción de quitar ítems. Confirma o edita y confirma.
- **Detrás de escena:** el formulario registra la apertura y la confirmación solo. El operador no mira ni acompaña.
- **El operador no:** insiste, recuerda ni apura; no responde sobre el contenido de los ítems; no ayuda a editar. Solo atiende si el enlace no abre (anotar en `notas`).
- Cuando la fila llega, copiarla a la hoja de captura. Si no llegó, es falla del registro: anotarlo y no reconstruir los tiempos de memoria.

### Paso 4 · El aviso al equipo
- **El Team Lead ve:** tras confirmar, la lista final con un botón para copiarla. El mensaje le pidió usarla como el aviso al equipo en lugar de escribir el suyo.
- **Detrás de escena:** nada. El operador no publica nada por él.

### Paso 5 · Seguimiento (dentro de las 24 h)
- Enviar el mensaje de seguimiento (abajo) y registrar: `publico_lista`, `recap_propio_paralelo` y la evidencia (enlace o captura de lo que mandó al equipo). Lo que cuenta es la evidencia, no lo que diga.

**Mensaje de seguimiento:**
> Hola {nombre}, gracias por la lista de ayer. Para cerrar la reunión {reunion}: ¿me pasás el enlace o una captura de lo que mandaste al equipo sobre lo decidido? Si mandaste algo además de la lista, o en lugar de ella, mandame eso también.

## Qué no se hace en ningún paso
- Resumir la reunión o mandar algo más que la lista.
- Crear tareas en Planner o Jira.
- Poner nada dentro de Teams.
- Mostrarle al Team Lead cómo se calcula nada ni cuál es el umbral.

## Si algo sale distinto de lo diseñado
Se anota en `notas` y la reunión se marca en `corrida`: `completa`, `no_ocurrio` (la reunión se canceló o tuvo <8 personas) o `con_desvio` (cualquier cosa que cambie lo que el test observa). Qué se hace con cada una lo decide `/analyze-solution-tests`.

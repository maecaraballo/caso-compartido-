# T2 · Hoja de captura

Una fila por reunión (18 filas esperadas: 6 Team Leads × 3 reuniones). El archivo `04-hoja-de-captura.csv` tiene las columnas; se abre en cualquier planilla. Con estas columnas se pueden leer los dos umbrales del test sin recurrir a la memoria de nadie.

## Columnas

| Columna | Qué se anota | De dónde sale |
| --- | --- | --- |
| `reunion_id` | Código, ej. `TL3-R2` (Team Lead 3, reunión 2) | Operador |
| `participante_id` | Código del Team Lead, ej. `TL3` | Operador |
| `procedencia` | `segmento` (miembro del pool de la encuesta) o `stand-in` (cualquier otro). Un `stand-in` hace la corrida `synthetic` y no decide nada | Operador, desde el reclutamiento |
| `nro_reunion` | 1, 2 o 3 | Operador |
| `fecha` | Fecha de la reunión | Operador |
| `asistentes` | Cantidad de personas (≥8) | Team Lead |
| `corrida` | `completa`, `no_ocurrio` o `con_desvio` (qué cuenta como cada una, en el guion) | Operador |
| `fin_reunion` | Hora real en que terminó | Operador |
| `hora_envio` | Hora en que se envió el mensaje con la lista | Operador |
| `entrega_tardia` | `sí` si pasaron más de 10 minutos entre `fin_reunion` y `hora_envio` | Operador |
| `items_propuestos` | Ítems en la lista enviada | Formulario (`items_total`) |
| `abierto_en` | Marca de la **primera** apertura del formulario | Formulario |
| `confirmado_en` | Marca de la confirmación | Formulario |
| `segundos_hasta_confirmar` | `confirmado_en` − `abierto_en` | Formulario |
| `items_editados` | Ítems con algún cambio o quitados | Formulario |
| `items_quitados` | Ítems quitados (ya incluidos en `items_editados`) | Formulario |
| `publico_lista` | `sí` / `no`: mandó al equipo la lista confirmada | Evidencia del seguimiento, no lo que cuente |
| `recap_propio_paralelo` | `sí` / `no`: mandó además, o en lugar de la lista, un recap escrito por él | Evidencia del seguimiento |
| `evidencia` | Enlace o captura de lo que mandó al equipo (o "no la envió") | Seguimiento a las 24 h |
| `notas` | Fallas del enlace, el registro, la entrega, dichos del Team Lead relevantes | Operador |

## Cómo se lee cada umbral (sin cambiarlo)

Umbral 1, confirmar en ≤2 min en ≥12 de 18 reuniones: una reunión cuenta si `segundos_hasta_confirmar` ≤ 120.

Umbral 2, publicar la lista confirmada en ≥12 de 18 reuniones, y en ≥2 de las 3 de al menos 4 de los 6 Team Leads: una reunión cuenta si `publico_lista` = sí, `items_editados` ≤ `items_propuestos` / 2 y `recap_propio_paralelo` = no.

Para el segundo tramo, por Team Lead, contar cuántas de sus reuniones cumplen el umbral 2.

Una fila `no_ocurrio` o `con_desvio` se deja en la hoja con su nota. Qué hacer con ellas lo define `/analyze-solution-tests`, no quien captura.

## Resumen por Team Lead (se completa al terminar)

| participante_id | procedencia | reuniones completas | reuniones que cumplen umbral 1 | reuniones que cumplen umbral 2 |
| --- | --- | --- | --- | --- |
| TL1 | | | | |
| TL2 | | | | |
| TL3 | | | | |
| TL4 | | | | |
| TL5 | | | | |
| TL6 | | | | |

**Nota para el análisis:** la regla de decisión habla de "usan la lista como su recap" para el descarte (<2 de los 6). La hoja guarda `publico_lista` y `recap_propio_paralelo` por reunión, así que se puede aplicar cualquiera de las lecturas al analizar.

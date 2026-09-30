---
date: 2026-09-29
source: survey
survey_design: product/surveys/2026-09-23-1944-colaboracion-en-vivo-fuera-de-teams.md
results: product/surveys/2026-09-26-1800-respuestas-colaboracion-en-vivo-fuera-de-teams.csv
n: 215 válidas (187 trabajaron en herramienta externa · 28 no)
---

# Análisis: trabajo colaborativo fuera de Teams (encuesta del 23 al 25/09)

## Denominador y límites

- 249 respuestas: 210 completas, 5 parciales, 34 descalificadas. **215 válidas** (email 77, panel 138).
- Descalificadas: 8 en email y 26 en panel (16 por firmografía —sector o países—, 10 por ser externos o no conducir reuniones).
- **187 trabajaron en una herramienta externa** (Q1 distinto de "En ninguna"; email 66, panel 121): supera la meta de 150.
- **28 no lo hicieron** (email 11, panel 17): por debajo de la meta de 30, **direccional**.
- Los 5 parciales cortaron antes de Q9/Q10: Q9 n=182, Q10 n=210.
- **Tasa de respuesta del email: no calculable** (alcance `unknown` en el diseño). Del panel llegaron 164 respuestas contra una cuota de 150.
- Firmografía del panel autodeclarada; la del email la garantiza la lista. Ninguna es verificable.
- Muestra autoseleccionada: son proporciones de esta muestra, no de la base de Teams.

### Corte por canal: hallazgo sobre la muestra antes que sobre el segmento

| | Email (n=77) | Panel (n=138) |
|---|---|---|
| Trabajan afuera en más de la mitad de sus reuniones (Q1) | 22% | 40% |
| Trabajan afuera en menos de la mitad (Q1) | 39% | 19% |
| Reuniones con 2 o más externos (Q8, sobre quienes trabajan afuera) | 5% | 16% |
| Usa Notas de la reunión / Loop en alguna o la mayoría de sus reuniones (Q10) | 37% | 21% |
| Artefacto preexistente (Q4) | 42% | 60% |

- El email (canal propio) sobrerrepresenta uso de lo nativo y menos trabajo afuera, como anticipaba el diseño.
- El panel trae más trabajo externo y más artefactos preexistentes; es coherente con su filtro (Engineering / Product Manager), que no es exactamente Team Lead.
- **Q6 (tiempo de acceso) y Q7 (no entraron) coinciden en ambos canales**: es el resultado más robusto.
- La dirección de O1 coincide en ambos canales; la magnitud no.

## O1. Origen del artefacto

**Creíamos** (creencias 2 y 6): comparten un link a Miro, Mural o FigJam porque lo nativo no alcanza.

**Datos** (n=187): ya existía antes de la reunión **53,5%**; se creó para la reunión **39,6%**; no sabe 7%.

| Grupo | n | Ya existía | Se creó para la reunión |
|---|---|---|---|
| Miro / Mural / FigJam / Lucidspark | 62 (33%) | 13% | **82%** |
| Resto de herramientas | 125 (67%) | **74%** | 18% |

- Ya existía, por herramienta (Q2): Jira 79%, dashboards 81%, Confluence 85%, Google Docs 52%, Notion 57%.
- Q3: 54% pegó un link en el chat, 21% ya lo tenía abierto, 16% compartió pantalla y cada uno lo abrió por su cuenta, 8% lo abrió como app dentro de Teams.
- El 24% es "se creó para la reunión y se siguió usando": conecta con la continuidad entre reuniones (Q11).

**Decisión:** no es un solo problema. Un tercio de las reuniones es co-creación en tableros creados para la ocasión (ahí hay sustitución de la Whiteboard nativa). Dos tercios es trabajo que ya vive en Jira, Confluence, dashboards o Docs (ahí Whiteboard no es alternativa; es un problema de integración).

## O2. Costo de acceso

**Creíamos:** el umbral de 5 minutos hasta que todos entran es el problema.

**Datos** (n=184): hasta 2 minutos 46%; 3 a 4 minutos 20%; **5 minutos o más 28%**; no sabe 7%. En 50% de las reuniones al menos un participante no logró entrar.

| | Con externos (n=41) | Solo internos (n=137) |
|---|---|---|
| 5 minutos o más | **61%** | 18% |
| Al menos 1 no entró | 65% | 46% |
| 2 o más no entraron | 29% | 21% |

- Las reuniones con externos son 22% del total pero explican la mitad (25 de 51) de los casos de 5 minutos o más.
- Con la app dentro de Teams, 40% tarda 5 minutos o más (n=15, débil).

**Decisión:** la fricción de acceso es sobre todo de reuniones con externos, un segmento distinto (consultores y agencias), tal como anticipaba el diseño. Para el Team Lead que conduce reuniones internas el umbral de 5 minutos no se sostiene como problema general (18%), aunque la mitad de las reuniones internas deja a alguien afuera.

## O3. Qué se hace afuera y dónde queda la decisión

**Actividades** (Q5, n=185, opción múltiple): votar o priorizar 39%; editar un documento entre varios 35%; revisar datos o métricas 34%; anotar decisiones o acuerdos 32%; aportar ideas o notas 30%; actualizar tareas o tickets 25%; agrupar u ordenar ideas 23%; dibujar un diagrama o flujo 14%.

- Agrupado: 60% converge o anota lo decidido; 42% ideación; 63% trabaja sobre datos, documentos o tareas.
- En tableros tipo Miro: votar 52%, agrupar 50%. Con el resto de herramientas: 32% y 9%.

**Dónde queda lo decidido** (Q9, n=182): **no quedó registrado en ningún lado 24%**; chat fuera de Teams 23%; Jira u otro gestor 22%; misma herramienta externa 15%; chat o notas de Teams 13%; documento de actas 12%; correo 10%; no se tomaron decisiones 7%.

- **"Otro" supera el 15% (32 de 182, 17,6%)**: por la regla del diseño la lista quedó incompleta.
- 26 de esos 32 dicen que la decisión quedó en el resumen o recap de IA (Copilot, Teams), la transcripción o la grabación (14% del total, similar a "en la misma herramienta externa"). Al menos 9 traen queja de calidad, p. ej. "En el resumen de Copilot pero mezclado con todo lo demás".
- Q2, Q3 y Q5 tienen "Otro" bajo el 15% (0%, 1%, 5%).

**Decisión:** cualquier solución tiene que cubrir votar y priorizar, cerrar y registrar la decisión, y trabajar sobre datos y documentos existentes, no solo dibujar o agrupar. El registro de la decisión es el hueco más claro.

## O4. Conocimiento y uso de lo nativo

Q10 (n=210), porcentaje por fila:

| Función | No sabía que existía | Sé que existe, nunca la usé | La usé y dejé de usarla | La uso en algunas / la mayoría |
|---|---|---|---|---|
| Whiteboard | 8% | 27% | **43%** | 21% |
| Notas de la reunión (Loop) | **31%** | 28% | 14% | 28% |
| Apps de otras herramientas en la reunión | **40%** | 28% | 9% | 23% |
| Resumen o asistente de IA | 12% | 39% | 13% | 36% |

- Whiteboard: el problema es abandono, no desconocimiento. Entre quienes usan tableros tipo Miro, 59% la probó y la dejó.
- Loop y apps dentro de Teams: acá sí hay desconocimiento.
- Los 28 que no trabajan afuera (direccional) muestran el mismo patrón: tampoco ignoran lo nativo.

**Decisión:** con Whiteboard la barrera es de calidad; con Loop y las apps, de descubribilidad.

## Preguntas abiertas

### Q11 (n=95, un tema principal por respuesta)

| Tema | n | Cita |
|---|---|---|
| Registro y seguimiento de lo decidido | 19 (20%) | "Que quede registro del por qué decidimos algo. El qué queda en Jira, el por qué se pierde en un hilo" (R-224) · "Termino escribiendo el acta yo después de cada reunión y pasando las tareas a Jira a mano" (R-124) |
| Resumen de IA no distingue lo decidido de lo hablado | 3 (3%) | "El resumen automático sirve para saber de qué se habló pero no para saber qué quedó decidido" (R-149) |
| Converger, priorizar, votar, cerrar | 12 (13%) | "Converger. Divergir es fácil, todos tiran ideas. Ordenarlas y elegir es lo que nos cuesta" (R-011) · "Votar. Usamos reacciones en el chat pero nadie sabe cuántos votaron ni qué ganó" (R-053) |
| Acceso, permisos, externos y compliance | 12 (13%) | "Con la agencia externa perdemos 5 o 10 minutos solo en que entren al FigJam" (R-072) |
| Continuidad entre reuniones / encontrar lo anterior | 11 (12%) | "Si usamos la pizarra nativa después nadie la encuentra. En Miro por lo menos el tablero tiene un link fijo" (R-218) |
| Participación y atención | 11 (12%) | "Hay 12 personas y opinan 3" (R-049) |
| Tiempo, horarios, exceso de reuniones | 11 (12%) | "Demasiadas reuniones, no hay tiempo para trabajar" (R-077) |
| Limitaciones de Whiteboard / notas nativas | 10 (11%) | "El whiteboard no deja ordenar ni votar, es una hoja en blanco y ya" (R-239) |
| Técnico / sin problema / otro | 6 | |

Registro de lo decidido (incluida la queja al resumen de IA) suma 22 respuestas (23%): el tema más grande.

### Q12 (n=16 de los 28 que no trabajan afuera, direccional)

Hablado o chat de Teams 6 · nativo de Teams (pizarra, notas, Forms) 5 · asincrónico antes de la reunión 2 · Excel compartido en pantalla 2 ("A veces es un lío saber a qué fila se refieren", R-046) · no lo necesitan 1.

### Compliance y regulación

4 de los 27 españoles (15%) dicen que compliance, seguridad o la normativa europea limitan las herramientas externas; un quinto caso es de Colombia (R-009). R-190: "compliance no nos deja meter datos de clientes en Miro, así que o lo hacemos en Teams o no se hace. Y en Teams cuesta". Números chicos: direccional.

## Insights priorizados

1. **La decisión no queda registrada** (O3): 24% no registra nada, 23% la deja en un chat fuera de Teams, 23% de las abiertas lo nombra como lo más difícil, y el resumen de IA no separa lo decidido de lo hablado.
2. **Son dos problemas** (O1): tableros creados para la reunión donde Whiteboard fracasa (43% la probó y la dejó) y trabajo ya existente en Jira, Confluence y dashboards.
3. **El costo de acceso es un problema de reuniones con externos** (O2): 61% tarda 5 minutos o más con externos contra 18% sin ellos.
4. **Converger y votar sigue sin resolverse** (O3): 39% vota o prioriza afuera; 13% lo señala como lo más difícil.
5. **Descubribilidad de Loop y apps** (O4): 31% y 40% no sabían que existían.
6. **Compliance en España deja solo lo nativo** (direccional, 4 casos).

### "Por qué" para entrevistas

- ¿Por qué se abandona Whiteboard: votación, plantillas, rendimiento o porque cuesta encontrarla después?
- ¿Por qué la decisión no se registra: falta dueño o el registro no vale el esfuerzo?
- ¿Por qué entre quienes no trabajan afuera unos usan lo nativo y otros deciden hablando?
- ¿Cómo resuelven el "por qué se decidió" cuando el qué queda en Jira?

## Pool de reclutamiento

- 77 aceptaron una conversación (email 19, panel 58); con IT = No y R2 distinto de "0 o 1" quedan **64 candidatos**, 58 con contacto. Los contactos quedan solo en el CSV.
- 10 coinciden por nombre de contacto con entrevistas ya hechas del 25 al 28/09 (R-024, R-036, R-097, R-113, R-143, R-151, R-153, R-170, R-196, R-224); cruce por nombre, a verificar. Quedan 54.
- **Primero, "En ninguna" sin entrevistar** (8, 7 con contacto): R-009, R-046, R-085, R-088, R-110, R-120, R-135, R-242.
- **Luego, contradicen con dos señales** (artefacto preexistente y acceso en menos de 3 minutos; 14, 13 con contacto): R-057, R-094, R-102, R-128, R-131, R-144, R-176, R-180, R-194, R-229, R-234, R-235, R-240, R-247.
- Después: 26 con una señal y 14 que confirman (sin señal de contradicción).

## Contraste con las creencias del overview

Con esta muestra autoseleccionada, ambas quedan **weakened** (no contradicted).

- **Creencia 6** [opportunity: colaboracion-en-vivo-reuniones] [value]: solo 33% usa tableros tipo Miro y 53,5% trabaja sobre artefactos preexistentes. La parte de Whiteboard tiene señal (43% la probó y la dejó).
- **Creencia 2** [product] [value]: los enlaces van sobre todo a sistemas preexistentes, así que el link no equivale a sustituir lo nativo. En Whiteboard el abandono es consciente (8% no la conocía), pero vale para un tercio de los casos.

---
date: 2026-09-29
source: real
sources:
  - product/interviews/2026-09-28-1700-ricardo-salinas.md (real, 26 min, exploración; respondente R-196 de la encuesta, "En ninguna" en Q1)
---

# Insights: Ricardo Salinas (Director de Ingeniería de Plataforma, Lumen Cloud)

Una sola entrevista, de un respondente reclutado a propósito como contradictor de la creencia (no trabaja en herramientas externas). No hay recurrencia entre entrevistados que evaluar; los cruces con la encuesta están en cada insight.

## Una decisión sin registro ni dueño costó dos días de retrabajo y un fin de semana de guardia

En la sync se acordó el orden de una migración de Postgres (réplicas de lectura antes que primarias). Nadie lo escribió y cada equipo se fue con su versión: uno empezó por las primarias y otro por las réplicas. El costo fue concreto (dos días arreglando y guardia extra un fin de semana), y la causa fue de dueño: cada uno supuso que otro lo iba a dejar por escrito (el ADR o un correo). Implica que cerrar una reunión con una decisión escrita y un responsable asignado tiene valor medible, incluso para quien hoy no usa ninguna herramienta externa. Coincide con el hueco más grande de la encuesta (24% no registra lo decidido).

> Evidence: "Se habló en la sync, cada uno se fue con su versión y nadie lo escribió. Yo pensé que el arquitecto iba a hacer el ADR y él pensó que yo lo iba a mandar por correo." — Ricardo Salinas

## Las reuniones de 16 son de estado; la decisión real se toma después, entre tres

La sync semanal es una ronda de estados de unos cuatro minutos por célula. Lo que se decide en serio se resuelve en una llamada aparte con los dos arquitectos, y el resultado se registra "a veces" en un ADR o se avisa en la sync siguiente. Para este perfil, el grupo grande no es el lugar donde se decide, así que una herramienta pensada para que las 16 personas co-creen en vivo no toca donde está la decisión. La oportunidad está en registrar lo que deciden los pocos y comunicarlo de vuelta a los muchos.

> Evidence: "Con dieciséis personas no se puede decidir nada, cada quien jala para su lado." / "Las decisiones grandes no se toman ahí. Se toman después, con los dos arquitectos, en una llamada aparte, los tres." — Ricardo Salinas

## Un solo intento fallido con la pizarra de Teams bastó para abandonarla, y lo hecho ahí quedó perdido

Hace un año la probó con 12 personas: se trabó, las notas tardaban en aparecer y no encontró cómo agruparlas; perdieron 15 minutos y volvieron a hablar. No la volvió a abrir, y el contenido creado nunca se recuperó. Implica que la primera experiencia con grupos de 10 o más tiene que ser confiable (fluidez, agrupar), porque no hay segunda oportunidad, y que lo creado necesita ser recuperable después de la reunión. Es el mismo patrón de la encuesta (43% la probó y la dejó; "nadie la encuentra" en Q11).

> Evidence: "Se trabó, las notas tardaban en aparecer, y no encontré cómo agruparlas. Perdimos quince minutos y volvimos a la plática. No la volví a abrir." / "Lo que habíamos puesto ahí, ni idea, supongo que sigue en algún lado. Nadie lo fue a buscar." — Ricardo Salinas

## Priorizar a mano alzada le alcanza; lo que no resuelve es quién participa

Con dos pedidos y capacidad para uno, votaron con la mano de Teams y él contó (nueve contra siete). Para una priorización simple no ve un problema. Lo que sí describe es una participación desigual: hablan los mismos cuatro o cinco, los dos de Madrid casi nunca porque para ellos ya es de noche, y el resto tiene la cámara apagada. Matiza la necesidad de "votar" que aparece en la encuesta (39% vota o prioriza afuera): en este perfil la fricción está en la asimetría de participación entre husos horarios, no en el mecanismo de votación. Con una sola entrevista es una hipótesis a explorar.

> Evidence: "Pregunté quién prefería el primero y levantaron la mano, la manita de Teams. Yo cuento. Salieron nueve contra siete." / "Hablan los mismos cuatro o cinco de siempre. Los de Madrid casi nunca, por la hora, para ellos ya es noche." — Ricardo Salinas

## Descubrir que existen las apps dentro de la reunión no le genera demanda

No sabía que se podían meter otras herramientas en la reunión y, al enterarse, dice que tampoco le hace falta. Para este perfil, mejorar la descubribilidad (40% no sabía que existía en la encuesta) no alcanzaría por sí sola para crear uso: primero tiene que haber una necesidad de trabajo conjunto en pantalla, y su reunión típica no la tiene.

> Evidence: "No sabía que se podían meter otras herramientas en la reunión. Pero tampoco me hace falta, la verdad." — Ricardo Salinas

## Fuera del guion, para el equipo

- Su dolor principal es el volumen: 27 horas semanales de reuniones, la mitad de su calendario, "y la mitad de esas podrían ser un correo". Es una señal sobre la creencia 3 (sobrecarga), aunque no prueba que una función cambie su forma de convocar.
- Derivó a Daniela, que lidera la célula de redes y "usa tableros". Es un candidato a entrevistar del lado que sí trabaja en herramientas externas.
- No es Team Lead sino director: su relato de decisión sobre grupos de 16 puede no valer para líderes de reuniones más chicas.

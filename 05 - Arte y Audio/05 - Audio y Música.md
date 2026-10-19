# Audio y Música

## Descripción de la sección

Define la identidad sonora y cómo el audio comunica información al jugador.

## Música

**Estilo:**
Ambiente industrial de tensión, con matices de terror claustrofóbico y sintetizadores oscuros que evocan instalaciones científicas abandonadas o alteradas.

**Instrumentación:**
Pad analógicos profundos creados en sintetizadores, frecuencias bajas pulsantes, percusiones metálicas industriales y elementos de distorsión sutil.

**Temas principales:**
- Tema del Laboratorio: Ambiente general de exploración e inquietud.
	
- Tema de Combate: Ritmos acelerados y secuencias electrónicas tensas que se activan al entrar en confrontación con los experimentos fallidos.

**Música dinámica:** Sí / No
Sí. La pista principal transiciona de manera fluida entre la exploración y el combate utilizando capas de audio o cambios de intensidad según la proximidad de las amenazas.
## Efectos de sonido

| Evento                       | Sonido                                            | Propósito                                                                        |
| ---------------------------- | ------------------------------------------------- | -------------------------------------------------------------------------------- |
| Ataque / Disparo del Jugador | Impacto láser o descarga eléctrica seca y rápida. | Proporcionar feedback inmediato de acción ofensiva.                              |
| Recibo de Daño               | Alarma amortiguada                                | Alertar visual y auditivamente la pérdida de vida.                               |
| Eliminación de Experimento   | Chisporroteo eléctrico y colapso estructural.     | Recompensar al jugador con una confirmación sonora de victoria sobre el enemigo. |
| Interacción con UI           | Clic tecnológico o beep de terminal.              | Guiar la navegación por los menús de pausa y pantallas de fin de juego.          |

## Audio espacial

¿Se utilizará audio posicional?
Sí. Se implementará audio espacial 2D/3D atenuado por distancia para que los sonidos de los experimentos fallidos y los disparos provengan de la dirección en la que se encuentran los elementos dentro de la pantalla, aumentando la inmersión y la alerta táctica del jugador.
## Voz

**Narración:**

**Diálogos hablados:**

**Idiomas:**
Español
## Mezcla

Define prioridades, volumen relativo y comportamiento de la música ante eventos importantes.

Prioridades y Volumen Relativo:
Efectos de Sonido (SFX): Prioridad alta. Deben destacar siempre para asegurar una respuesta clara ante las mecánicas de combate.

Música: 
Prioridad media-baja. Diseñada para mantener la atmósfera ambiental sin saturar ni opacar las señales auditivas importantes.

Comportamiento ante eventos importantes: 
Al pausar el juego o abrir menús de opciones/inventario, la música reduce su volumen drásticamente y los SFX de juego se silencian, priorizando los sonidos de interfaz.

> **Navegación:** [[00 - Índice]] · ← [[04 - Interfaz Visual]] · [[01 - UX y Flujo del Jugador]] →

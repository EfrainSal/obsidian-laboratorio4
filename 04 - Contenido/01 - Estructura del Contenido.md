# Estructura del Contenido

## Descripción de la sección

Organiza el contenido del videojuego en unidades manejables: mundos, capítulos, zonas, niveles, misiones y desafíos.

## Estructura

```text
Laboratorio 4
├── Mundo / Capítulo 1
│   ├── Piso 1
│   ├── Piso 2
│   ├── Piso 3
│   └── Jefe / Evento
└── Final
```

## Cantidad estimada

| Tipo     | Cantidad |
| -------- | -------: |
| Mundos   |        1 |
| Niveles  |        4 |
| Misiones |        1 |
| Enemigos |        1 |
| Jefes    |        1 |
| NPC      |        0 |
| Objetos  |        5 |

## Dependencias

¿Qué contenido debe existir antes de otro?
- **Los activos gráficos y scripts del Piso 1** deben estar completamente programados y probados antes de generar las variaciones de dificultad para los Pisos 2 y 3.
    
- **El sistema de tarjetas de acceso** deben implementarse antes de estructurar las puertas de transición entre los niveles, ya que la progresión geográfica depende estrictamente de poseer dicho objeto.
    
- **El diseño y los patrones de ataque del jefe final (Dr. Yiba)** requieren que los sistemas de combate, las habilidades de los personajes (Jason y Milena) y el balance de salud estén completamente funcionales en los niveles previos para garantizar un desafío coherente en el clímax.

> **Navegación:** [[00 - Índice]] · ← [[04 - Diálogos y Narrativa]] · [[02 - Niveles]] →

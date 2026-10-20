# Motor y Herramientas

## Descripción de la sección

Documenta las herramientas utilizadas para crear el videojuego y por qué fueron seleccionadas.

## Motor

**Motor:** Unity 6

**Versión:** 6000.6.0f1

**Renderizado:**

**Física:** Unity Physics 2D (Rigidbody 2D, BoxCollider2D, CircleCollider2D, Custom Physics Shapes)

**Sistema de entrada:**

## Lenguajes

| Lenguaje | Uso                                                                                                                            |
| -------- | ------------------------------------------------------------------------------------------------------------------------------ |
| C#       | Programación de la lógica de juego, física de personajes, IA de experimentos, controladores de UI y flujo de escenas en Unity. |

## Herramientas

| Herramienta        | Propósito                                                                    | Versión    |
| ------------------ | ---------------------------------------------------------------------------- | ---------- |
| Unity              | Motor del juego, creación de escenas.                                        | 6000.6.0f1 |
| Visual Studio Code | Editor de codigo de los scripts.                                             |            |
| Git y GitHub       | Control de versiones y repositorio remoto.                                   | 2.46.1     |
| Reaper             | Producción musical y síntesis de efectos de audio para el entorno del juego. | v7.x       |
| Pixelorama         | Desarrollo y diseño de los sprites y animaciones.                            |            |

## Dependencias

Lista librerías, paquetes, plugins o servicios externos.

## Convenciones del proyecto

- Estructura de carpetas: 
	- Assets/_Project/Animations/ Audio/Materials/Prefabs/ Scenes/Scripts/Settings
- Nomenclatura
	- Clases y Scripts: PascalCase (ej. PlayerController, EnemyHealth).
	- Variables privadas: camelCase o _camelCase .
	- Métodos: PascalCase.
	- Prefabs: PascalCase o prefijos descriptivos (.
- Control de versiones
- Formato de assets
	- Imágenes: PNG (con transparencia activada y filtro Point (no filter) para pixel art / sprites claros).
	- Audio: WAV para efectos de sonido e MP3/OGG para música de fondo.
- Convenciones de código


> **Navegación:** [[00 - Índice]] · ← [[01 - Arquitectura Técnica]] · [[03 - Requisitos Técnicos]] →

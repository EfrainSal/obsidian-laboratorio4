# Reglas y Estados del Juego

## Descripción de la sección

Define las reglas globales y los estados que puede atravesar el videojuego.

## Estados principales

- Menú principal
- Carga 
- Jugando 
- Pausa
- Victoria 
- Derrota 
- Game Over 
- Créditos 

## Transiciones

| Estado origen  | Evento                           | Estado destino | Condición                                                              |
| -------------- | -------------------------------- | -------------- | ---------------------------------------------------------------------- |
| Menú principal | Clic en "Jugar"                  | Carga          | Selección exitosa de la opción de inicio.                              |
| Carga          | Fin de inicialización de escenas | Jugando        | Todos los componentes y scripts del _Piso 1_ cargados correctamente.   |
| Jugando        | Presionar tecla `Esc`            | Pausa          | El juego se encuentra en curso sin eventos críticos de muerte activos. |
| Pausa          | Seleccionar "Reanudar"           | Jugando        | El usuario decide continuar con su partida actual.                     |
| Jugando        | Salud del jugador llega a 0      | Derrota        | El contador de vida del personaje activo se agota por daño recibido    |
| Derrota        | Animación de muerte              | Game Over      | Se completa el registro del fracaso de la misión.                      |
| Game Over      | Seleccionar "Reiniciar"          | Carga          | El jugador decide reintentar la travesía desde el inicio               |
| Victoria       | Diálogos finales                 | Creditos       | Conclusión de la narrativa principal del laboratorio                   |

## Reglas globales

1.- Si el jugador es derrotado en cualquier punto de los cuatro pisos, pierde de forma definitiva el inventario, los recursos acumulados y el nivel actual, reiniciando su avance estrictamente en el _Piso 1_.

2.- Ninguna puerta de salida o ascensor entre niveles puede abrirse a menos que el jugador posea la tarjeta de acceso correspondiente a ese piso específico.

3.- El estado de pausa suspende de forma absoluta el movimiento de los enemigos y la física de proyectiles.

## Casos especiales

Documenta excepciones importantes para evitar interpretaciones diferentes durante la implementación.
**Interrupción de recolección:** Si el jugador muere exactamente en el mismo fotograma en el que interactúa para recoger una tarjeta de acceso o consumible, el objeto se considerará perdido y no se guardará en el inventario para el siguiente intento de reinicio.

> **Navegación:** [[00 - Índice]] · ← [[06 - Economía y Recursos]] · [[01 - Premisa y Trama]] →

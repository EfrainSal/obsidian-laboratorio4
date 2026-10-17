# Sistemas del Juego

## Descripción de la sección

Los sistemas son conjuntos de reglas y componentes que trabajan juntos: combate, inventario, IA, diálogo, progresión, economía, misiones, etc.

## Inventario de sistemas

| Sistema                          | Propósito                                                                                                | Dependencias                    | Estado    |
| -------------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------- | --------- |
| Sistema de Control y Movimiento  | Gestionar la movilidad del jugador y sus habilidades tácticas exclusivas como el escudo y deslizamiento. | Ninguna                         | Propuesto |
| Sistema de Combate y Armas       | Permitir la ofensiva a distancia y cuerpo a cuerpo apuntando con el mouse.                               | Sistema de Control y movimiento | Propuesto |
| Sistema de Oleadas y Spawner     | Generar de forma progresiva y controlada a los enemigos durante cada partida                             | Sistema de Control y movimiento | Propuesto |
| Sistema de Salud y Daño          | Controlar la vida de los personajes y enemigos, gestionando el Game Over al llegar a cero.               | Ninguna                         | Propuesto |
| Sistema de Inventario y Recursos | Administrar consumibles de supervivencia y tarjetas de acceso por piso.                                  | Sistema de salud                | Propuesto |
| Sistema de Interfaz de Usuario   | Mostrar en tiempo real la salud, munición, estado de habilidades.                                        | Salud, Armas, Inventario        | Propuesto |

## Plantilla de sistema

### Nombre

**Objetivo:**

**Entradas:**

**Procesamiento / reglas:**

**Salidas:**

**Estados posibles:**

**Dependencias:**

**Interacciones:**

**Datos que necesita:**

**Datos que genera:**

**Riesgos:**

**Criterios de aceptación:**

##### **1. Sistema de Control y Movimiento**

- **Objetivo:** Permitir al usuario desplazar al personaje por el escenario y activar sus habilidades de supervivencia.

- **Entradas:** Teclas direccionales  WASD y botón de habilidad Espacio.

- **Procesamiento / reglas:** Lee los ejes de entrada, aplica velocidad mediante componentes de física y evalúa el tiempo de recarga de la habilidad táctica de cada personaje.

- **Salidas:** Desplazamiento visual y físico del personaje en el mapa y activación de efectos de escudo o deslizamiento.

- **Estados posibles:** Reposo, Moviéndose, Habilidad Activa, En Recarga.

- **Dependencias:** Ninguna.

- **Interacciones:** Se comunica con el Sistema de Combate para limitar acciones ej. Milena no dispara al deslizarse.

- **Datos que necesita:** Velocidad base, duración de habilidad, _cooldown_.

- **Datos que genera:** Posición en coordenadas 2D .

- **Riesgos:** Que el personaje atraviese colisiones si la física no está bien configurada.

- **Criterios de aceptación:** El movimiento debe sentirse fluido y responsivo en 8 direcciones, ejecutando la habilidad táctica sin tirones.


##### **2. Sistema de Combate y Armas**

- **Objetivo:** Proveer los medios de ataque contra las hordas de enemigos mediante armas de fuego y cuerpo a cuerpo.

- **Entradas:** Posición del cursor del mouse y clics.

- **Procesamiento / reglas:** Comprueba si hay munición disponible y genera proyectiles según la cadencia establecida.

- **Salidas:** Creación de balas en escena, reproducción de sonidos de disparo y reducción de munición en el inventario.

- **Estados posibles:** Apuntando, Disparando, Recargando, Sin Munición.

- **Dependencias:** Sistema de Control y movimiento.

- **Interacciones:** Impacta directamente sobre el Sistema de Salud y Daño de los enemigos.

- **Datos que necesita:** Cadencia de fuego, daño por proyectil, tipo de arma.

- **Datos que genera:** Instanciación de proyectiles.

- **Riesgos:** Acumulación excesiva de balas en memoria si no se destruyen al colisionar.

- **Criterios de aceptación:** El arma debe girar con precisión hacia el cursor y disparar respetando la cadencia programada.


##### **3. Sistema de Oleadas y Spawner**

- **Objetivo:** Mantener la tensión constante generando enemigos de forma automatizada e incremental por niveles.

- **Entradas:** Límites de los pisos del laboratorio.

- **Procesamiento / reglas:** Activa puntos de aparición (_spawners_) en el mapa para instanciar a los Sorbos de manera progresiva.

- **Salidas:** Aparición constante de entidades enemigas que buscan activamente al jugador.

- **Estados posibles:** Pausa entre oleadas, Oleada Activa, Oleada Completa.

- **Dependencias:** Sistema de Control y Movimiento.

- **Interacciones:** Conecta con la Inteligencia Artificial de persecución de los enemigos.

- **Datos que necesita:** Tipos de enemigos permitidos por piso, tasa de aparición.

- **Datos que genera:** Conteo de enemigos eliminados y tiempo transcurrido.

- **Riesgos:** Saturación de rendimiento (_lag_) si se generan demasiados enemigos simultáneamente.

- **Criterios de aceptación:** Los enemigos deben aparecer en los tiempos establecidos y escalar en dificultad conforme el jugador avanza de nivel.


##### **4. Sistema de Salud y Daño**

- **Objetivo:** Controlar los puntos de vida de los actores y gestionar las consecuencias fatales de recibir daño.

- **Entradas:** Colisiones o impactos de proyectiles entre jugador y enemigos.

- **Procesamiento / reglas:** Resta salud proporcional al daño recibido. Si el valor llega a cero, destruye al objeto o desencadena el estado de derrota.

- **Salidas:** Actualización de la barra de vida y activación de pantalla de Game Over en caso del jugador.

- **Estados posibles:** Sano Herido, Derrotado y Game Over.

- **Dependencias:** Ninguna.

- **Interacciones:** Recibe datos del _Sistema de Combate_ y alimenta a la _Interfaz de Usuario_.

- **Datos que necesita:** Salud máxima, salud actual, valor de daño de los ataques.

- **Datos que genera:** Eventos de cambio de salud o muerte de entidad.

- **Riesgos:** _Bugs_ de doble daño por colisiones continuas.

- **Criterios de aceptación:** El jugador debe perder vida claramente al ser alcanzado por un enemigo y reiniciar la partida si su salud llega a cero.


##### **5. Sistema de Inventario y Recursos**

- **Objetivo:** Administrar los consumibles de curación y los objetos clave de progresión.

- **Entradas:** Recolección por proximidad y uso de teclas de acceso rápido 1 y 2.

- **Procesamiento / reglas:** Almacena la cantidad de recursos en variables de control; al activarlos, modifica atributos del jugador o desbloquea puertas de salida de piso.

- **Salidas:** Modificación de estadísticas del jugador o apertura de accesos bloqueados.

- **Estados posibles:** Vacío, Con recursos disponibles, Objeto clave obtenido.

- **Dependencias:** Sistema de Salud y Sistema de Control.

- **Interacciones:** Se comunica directamente con la Interfaz de Usuario para reflejar los cambios en pantalla.

- **Datos que necesita:** Cantidad máxima de inventario, identificador de tarjeta de acceso.

- **Datos que genera:** Estado booleano de desbloqueo de puertas.

- **Riesgos:** Que el jugador consuma objetos cuando no lo necesita por error de asignación de teclas.

- **Criterios de aceptación:** Las puertas de los pisos solo deben abrirse si el jugador posee la tarjeta correspondiente obtenida previamente.
## Relaciones entre sistemas

Describe qué sistemas dependen de otros y qué información intercambian.

- **Sistema de Control** alimenta al **Sistema de Combate** (porque el movimiento define la orientación del ataque).

- **Sistema de Combate** y **Sistema de Oleadas** retroalimentan al **Sistema de Salud y Daño** (los ataques de los enemigos reducen la vida del jugador).

- **Sistema de Inventario** modifica directamente los valores del **Sistema de Salud** (al usar vendas) y el **Sistema de Control** (al usar adrenalina).

- Todos los sistemas reportan su estado actual (vida, munición, oleada, recursos) hacia el **Sistema de Interfaz de Usuario  para mantener informado al jugador en todo momento.


> **Navegación:** [[00 - Índice]] · ← [[02 - Mecánicas]] · [[04 - Controles]] →

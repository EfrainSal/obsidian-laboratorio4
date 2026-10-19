# Personajes y Animación

## Descripción de la sección

Documenta cómo deben verse y comportarse visualmente los personajes.

## Requisitos por personaje

| Personaje       | Modelo/Sprite                                                                 | Animaciones                                                      | VFX                                | Estado                     |
| --------------- | ----------------------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------- | -------------------------- |
| Jason Smith     | Humano ~40 años, chaleco, camisar, jeans y botas. Base 32×32.                 | Idle, caminar, correr, disparar, machete, daño, escudo, derrota. | Destello de arma, escudo, impacto. | Animaciones por verificar. |
| Milena Rhea     | Cabello recogido, camisa, jeans y botas. Base 32×32.                          | Idle, desplazamiento, deslizamiento, daño, derrota.              | Rastro sutil de deslizamiento.     | Planificada.               |
| Sorbo           | Homúnculo oscuro; mismo cuerpo y proporciones; solo cambia el atuendo. 32×32. | Idle, desplazarse, ataque cercano, daño, muerte.                 | Impacto y destello de daño.        | Planificado.               |
| Dr. Yiba Humano | Médico normal de presencia inquietante. 32×32.                                | Idle, gesto/diálogo.                                             | Opcional mínimo.                   | Planificado.               |
| Dr. Yiba Mutado | Jefe monstruoso, silueta simple. 32×32 como base de lectura.                  | Idle, anticipación, ataques, daño, derrota.                      | Aviso de ataque e impactos.        | Planificado                |

## Animaciones

### Movimiento

- Idle
- Caminar
- Correr
- Saltar
- Caer

### Interacción
El personaje debe orientarse hacia puertas, salidas y objetos cercanos al interactuar. Como propuesta, el objeto seleccionable se resalta con un contorno tenue. 
### Combate
 El personaje seleccionado dispone conceptualmente de subfusil y machete. Para el disparo se orienta el arma al cursor; el proyectil debe distinguirse del fondo. Para el machete, un arco de alcance corto. Los Sorbos se plantean con un ataque cuerpo a cuerpo y el jefe con patrones claros.
### Daño
Ante impactos: destello breve de la silueta, pequeño retroceso y actualización inmediata de la vida. Evitando destellos rápidos excesivos y depender únicamente del rojo para comunicar daño.
### Muerte / derrota
Al agotarse la vida, reproducir animación corta de caída o colapso, detener controles y abrir la pantalla de derrota. Los Sorbos deben desaparecer o quedar como sprite inerte, sin animaciones elaboradas. La muerte del jefe requiere una pose final reconocible.
## Convenciones

Define nombres de archivos, tamaños, esqueletos, rigging, frames o formatos cuando sea necesario.


> **Navegación:** [[00 - Índice]] · ← [[01 - Dirección de Arte]] · [[03 - Entornos]] →

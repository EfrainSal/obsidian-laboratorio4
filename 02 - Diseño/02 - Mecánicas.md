# Mecánicas

## Descripción de la sección

Una mecánica es una regla o interacción mediante la cual el jugador puede actuar dentro del sistema del juego.

Documenta cada mecánica con suficiente detalle para que otro integrante pueda implementarla.

## Plantilla de mecánica

### Nombre de la mecánica

**Propósito:**  
¿Qué aporta a la experiencia?

**Activación:**  
¿Qué debe hacer el jugador?

**Reglas:**  
¿Qué puede y qué no puede ocurrir?

**Entrada:**  
¿Qué botón, gesto o acción la activa?

**Estado inicial:**

**Estado final:**

**Recursos utilizados:**

**Recompensa:**

**Penalización:**

**Interacciones con otras mecánicas:**

**Casos límite:**  
¿Qué ocurre en situaciones poco comunes?

## Mecánicas principales

### Mecánica 01: Movimiento y Habilidad  Personalizada

**Propósito:** 
¿Qué aporta a la experiencia?
Permite la navegación por los escenarios del laboratorio y otorga un recurso defensivo/evasivo único según el personaje seleccionado.

**Activación:**
¿Qué debe hacer el jugador?
**Movimiento**: El jugador presiona las teclas de dirección/WASD.
**Habilidad** **táctica**: El jugador presiona la tecla de acción.

**Reglas:**
¿Qué puede y qué no puede ocurrir?
- El personaje se desplaza en 8 direcciones por el mapa 2D.
    
- **Jason (Escudo):** Al activar la habilidad, despliega su escudo anulando el daño frontal recibido durante unos segundos.
    
- **Milena (Deslizamiento):** Se desliza velozmente en la dirección del movimiento, con un tiempo de recarga.

**Entrada:** 
Teclado: WASD para el movimiento y Espacio para la habilidad.

**Estado inicial:** 
Personaje estático, habilidad disponible.

**Estado final:** 
Personaje en nueva posición, habilidad en tiempo de recarga.

**Recursos utilizados:** 
Barra de cooldown de habilidad  y velocidad.

**Recompensa:** 
Reagruparse, evitar ser acorralado por los Sorbos y mitigar o esquivar daño mortal.

**Penalización:** 
Si la habilidad está en recarga y el jugador queda acorralado, no podrá esquivar el ataque masivo.

**Interacciones con otras mecánicas:** 
Se combina con el apuntado y disparo; Milena no puede disparar durante el deslizamiento, mientras que Jason solo puede usar armas como el machete con el escudo activo.

**Casos límite:** 
¿Qué ocurre en situaciones poco comunes?
Si el jugador intenta deslizarse hacia un muro, colisiona inmediatamente al colisionar sin traspasar la geometría.
<!-- Copiar la plantilla anterior -->

### Mecánica 02: Apuntado Libre y Disparo 

**Propósito:** 
¿Qué aporta a la experiencia?
Constituye la forma principal de ataque para eliminar hordas de Sorbos a distancia o en combate cuerpo a cuerpo.

**Activación:** 
¿Qué debe hacer el jugador?
Mover el mouse para apuntar el arma hacia el cursor y presionar los botones de clic.

**Reglas:**
¿Qué puede y qué no puede ocurrir?
- El **Subfusil** consume munición y spawnea proyectiles con una cadencia determinada.

- El **Machete** realiza un ataque en arco corto sin gastar munición, ideal para emergencias o cuando el enemigo está muy cerca.

**Entrada:** 
¿Qué botón, gesto o acción la activa?
Mouse: Mover para apuntar, Clic Izquierdo para disparar Subfusil.

**Estado inicial:** 
Arma orientada al cursor, cargador con balas.

**Estado final:** 
Proyectil instanciado en dirección al objetivo, bala restada del inventario.

**Recursos utilizados:** 
Contador de munición y cadencia de disparo.

**Recompensa:** 
Eliminación de enemigos, despejar caminos bloqueados.

**Penalización:** 
Desperdicio de munición si se falla el disparo; quedar indefenso al agotar las balas.

**Interacciones con otras mecánicas:** 
Impacta en en los enemigos reduciendo sus puntos de vida hasta eliminarlos.

**Casos límite:** 
¿Qué ocurre en situaciones poco comunes?
Si el jugador se queda sin munición e intenta disparar el subfusil, el sistema no generará proyectiles.
### Mecánica 03: Generación de Oleadas
**Propósito:** 
¿Qué aporta a la experiencia?
Mantener la tensión constante mediante la aparición de enemigos que escalan en número.

**Activación:**
¿Qué debe hacer el jugador?
Automática al ingresar a un piso del laboratorio.

**Reglas:**
¿Qué puede y qué no puede ocurrir?
- El controlador de oleadas genera enemigos en intervalos de tiempo predefinidos en zonas de aparición.

- La cantidad y velocidad de aparición de los enemigos aumenta progresivamente con el tiempo o al avanzar de piso.

**Entrada:** 
¿Qué botón, gesto o acción la activa?
Sistema del juego.

**Estado inicial:** 
Zona despejada.

**Estado final:** 
Oleada activa de enemigos persiguiendo al jugador.

**Recursos utilizados:** 
Memoria de instancias.

**Recompensa:** 
Genera la oportunidad de obtener objetos o bajas necesarias para limpiar la zona.

**Penalización:** 
Acumulación masiva de enemigos si el jugador no elimina las hordas rápidamente, resultando en acorralamiento.

**Interacciones con otras mecánicas:** 
Se conecta directamente con la barra de salud del jugador, y el consumo de munición.

**Casos límite:** 
¿Qué ocurre en situaciones poco comunes?
Si se alcanza el límite máximo de entidades en pantalla, el spawner pausará la aparición hasta que el jugador elimine a un grupo existente.
## Mecánicas secundarias

Lista las mecánicas que complementan la experiencia pero no constituyen el núcleo.
### Mecánica 4: Gestión de Consumibles e Inventario
**Propósito:** 
¿Qué aporta a la experiencia?
Administrar recursos de supervivencia para recuperar salud o potenciar temporalmente los atributos del personaje.

**Activación:** 
¿Qué debe hacer el jugador?
Presión de teclas numéricas 1, 2.

**Reglas:**
¿Qué puede y qué no puede ocurrir?
- **Vendas:** Consume una unidad del inventario y restaura un porcentaje fijo de puntos de vida. No se pueden usar con la salud al 100%.
- **Inyecciones de Adrenalina:** Consume una unidad e incrementa temporalmente la velocidad de movimiento.

**Entrada:** 
¿Qué botón, gesto o acción la activa?
Teclado: Tecla 1 usar venda, Tecla 2 usar adrenalina.

**Estado inicial:** 
Objeto guardado en el inventario.

**Estado final:** 
Objeto consumido, barra de salud restaurada o buff de velocidad activado.

**Recursos utilizados:** 
Cantidad de consumibles en el inventario.

**Recompensa:** 
Extensión del tiempo de vida y ventaja táctica temporal.

**Penalización:** 
Gastar un consumible de manera innecesaria deja al jugador desprotegido para enfrentamientos posteriores o contra el jefe final.

**Interacciones con otras mecánicas:** 
Modifica directamente la salud y los multiplicadores de velocidad del jugador.

**Casos límite:** 
¿Qué ocurre en situaciones poco comunes?
Si se presiona la tecla sin tener consumibles disponibles en el inventario, no ocurre ninguna acción.

### Mecánica 05 Búsqueda e Interacción con Tarjetas de Acceso
**Propósito:** 
¿Qué aporta a la experiencia?
Funcionar como la condición indispensable de progresión geográfica para abrir los accesos bloqueados y pasar de piso.

**Activación:** 
¿Qué debe hacer el jugador?
Acercarse a la tarjeta que esta en alguna parte del piso o al panel de la puerta y presionar el botón de interacción.

**Reglas:**
¿Qué debe hacer el jugador?
- Cada piso contiene una tarjeta de acceso oculta o resguardada por una concentración de enemigos.

- La puerta de salida del piso permanecerá bloqueada hasta que el jugador recolecte la tarjeta correspondiente.

**Entrada:** 
¿Qué botón, gesto o acción la activa?
Acercarse para interactuar.

**Estado inicial:** 
Puerta bloqueada / Tarjeta en el mapa.

**Estado final:** 
Tarjeta en posesión / Puerta desbloqueada para pasar al siguiente piso.

**Recursos utilizados:** 
Variable booleana en el estado del jugador.

**Recompensa:** 
Habilitar el paso hacia el siguiente nivel del laboratorio.

**Penalización:** 
Quedar atrapado en el piso actual resistiendo hordas mientras no se encuentre la tarjeta.

**Interacciones con otras mecánicas:** 
Interactúa con el sistema del escenario.

**Casos límite:** 
¿Qué ocurre en situaciones poco comunes?
Si el jugador interactúa con el panel de la puerta sin tener la tarjeta, la interfaz desplegará un mensaje de alerta ("Se requiere tarjeta de acceso de Piso X").

> **Navegación:** [[00 - Índice]] · ← [[01 - Jugabilidad]] · [[03 - Sistemas]] →

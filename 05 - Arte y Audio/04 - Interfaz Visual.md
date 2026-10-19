# Interfaz Visual

## Descripción de la sección

Documenta la información que el juego muestra al jugador y las reglas visuales de la interfaz.

## HUD

Elementos:

- Vida
- Munición
- Objetivo
- Recursos
- Indicadores contextuales

## Jerarquía visual

¿Qué información debe verse primero, segundo y tercero?
- **Primero:**  Vida, daño recibido, enemigo inmediato y munición disponible, porque influyen en la supervivencia.

- **Segundo:**  Habilidad/consumible activo y aviso de interacción; deben poder consultarse sin dejar de observar la escena.

- **Tercero:**  Objetivo actual y mensajes ambientales; solo se muestran cuando aporten información útil, no como panel fijo.
## Estados

Documenta estados normales, advertencias, daño, éxito, error y bloqueo.
- **Normal**: Valores de vida y munición estables; iconos visibles pero discretos.
- **Advertencia**: Vida baja: color de alerta; munición escasa: contador resaltado.
- **Daño**: Respuesta instantánea del HUD + impacto en personaje.
- **Éxito**: Objetivo completado / piso superado: mensaje corto y transición controlada.
- **Error**: Acción no disponible: texto o icono breve, sin ventana intrusiva.
- **Bloqueo**: Puerta cerrada, falta de recurso o acción en enfriamiento.
## Convenciones

**Tipografía:**
Fuente pixel o sans legible, con tildes y ñ; títulos de estética retro, textos funcionales de trazo limpio.

**Iconografía:**
Siluetas sencillas para salud, balas, vendas, adrenalina, escudo e interacción.

**Tamaños mínimos:**
Diseñar para visualizarse sin zoom: textos funcionales equivalentes a 14–16 px en la resolución de referencia y pictogramas de al menos 16–24 px en pantalla, ajustables según escalado de UI.

**Contraste:**
Texto claro sobre fondos oscuros semitransparentes.

**Animaciones:**
Indicadores suaves y sin parpadeo molesto.
## Pantallas

- Menú principal
- Pausa
- Inventario
- Victoria
- Derrota


> **Navegación:** [[00 - Índice]] · ← [[03 - Entornos]] · [[05 - Audio y Música]] →

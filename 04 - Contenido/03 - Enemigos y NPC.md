# Enemigos y NPC

## Descripción de la sección

Documenta las entidades controladas por el juego y su comportamiento.

## Plantilla de enemigo

### Nombre: Sorbos

**Rol de combate:**
Enjambre

**Comportamiento:**
Patrullan erráticamente en la oscuridad. Al detectar al jugador atacan.

**Vida:**
Baja

**Daño:**
Medio

**Defensas:**
Nula

**Velocidad:**
Media-Baja

**Rango de detección:**
Medio

**Ataques:**
Arañazo mutante y escupitajo de fluidos radiactivos.

**Debilidades:**
Armas de fuego a distancia.

**Recompensa:**
Dejan caer Balas (frecuente) y Vendas (baja probabilidad).

**Estados de IA:**

```text
Spawnear → Detectar → Perseguir → Atacar
                  ↓
                Perder objetivo → Buscar
```

### Nombre: Dr.Yiba

**Rol de combate:** Jefe final


**Comportamiento:**
Permanece en el centro de la sala de experimentación, rotando y lanzando ráfagas masivas de proyectiles mientras invoca Sorbos más pequeños.

**Vida:**
Muy alta

**Daño:**
Alto

**Defensas:**
Alta resistencia a ataques cuerpo a cuerpo.

**Velocidad:**
Inmóvil/Lenta, pero sus ataques son rapidísimos.

**Rango de detección:**
Toda la arena de combate.

**Ataques:**
 Lluvia radial de balas biológicas, embestida pesada, y rugido de invocación.

**Debilidades:**
El escudo de Jason bloquea sus proyectiles; vulnerable a ataques veloces mientras recarga sus ráfagas.  

**Recompensa:**
Completar el juego

**Estados de IA:**

```text
Detectar → Atacar → Muerte
			↓
			Disparo estandar → Al 50% de vida, ataques más rápidos e invocaciones
```

## Plantilla de NPC

**Nombre:**

**Función:**

**Ubicación:**

**Interacción:**

**Diálogos:**

**Condiciones:**

**Recompensas / información:**


> **Navegación:** [[00 - Índice]] · ← [[02 - Niveles]] · [[04 - Objetos y Coleccionables]] →

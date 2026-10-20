# Seguridad y Riesgos Técnicos

## Descripción de la sección

Documenta riesgos técnicos y medidas para reducir fallos, pérdida de datos o abuso de sistemas.

## Riesgos

| Riesgo                             | Probabilidad | Impacto | Mitigación                                                                                                                              |
| ---------------------------------- | ------------ | ------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Corrupción de archivos de guardado | Media        | Alto    | Implementación de copias de seguridad, por medio de control de versiones.                                                               |
| Cierre inesperado del programa     | Baja         | Medio   | Guardado automático de puntos de control (checkpoints) al cambiar de sala o piso del laboratorio para minimizar la pérdida de progreso. |

## Datos sensibles

¿El juego almacena información personal, cuentas, estadísticas en línea u otros datos?

## Multijugador

Si existe conexión en red, documentar:

- Autenticación
- Validación
- Autoridad del servidor
- Comunicación
- Protección contra manipulación

## Recuperación

¿Qué ocurre ante corrupción de datos, pérdida de conexión o fallo del programa?

El juego implementa un registro de depuración básico para capturar excepciones críticas en C#. Dado que la progresión se actualiza en puntos de control seguros (como al limpiar una sala o avanzar de piso), un cierre inesperado solo retrotrae al jugador al inicio del último checkpoint registrado, evitando pérdida masiva de datos.


> **Navegación:** [[00 - Índice]] · ← [[04 - Datos y Persistencia]] · [[01 - Alcance]] →

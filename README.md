# Semáforo Vivo

Semáforo inteligente · Hackathon UNMSM · Smart Mobility.

Prototipo navegable de una plataforma municipal de movilidad. Funciona sin instalar nada: abre `index.html` en el navegador (o publícalo con GitHub Pages).

| Página | Qué hace |
| --- | --- |
| `index.html` | Dashboard municipal: indicadores, alertas y tabla de intersecciones (página de inicio). |
| `mapa.html` | Mapa con 3 intersecciones de Lima. Al elegir una se ven sus indicadores. |
| `simulador.html` | Simulador del cruce + comparación inteligente vs. tiempo fijo con el mismo tráfico. |
| `incidencias.html` | Registrar problemas, asignar responsable y cambiar su estado. |
| `reportes.html` | Reporte de las simulaciones guardadas (imprimir/PDF o CSV). |

Los datos se guardan en el navegador (`localStorage`). Las cifras son simuladas, no mediciones reales.

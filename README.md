# Semáforo Vivo 

**Gestión adaptativa de semáforos y herramientas de análisis para la movilidad urbana.**  
Proyecto de la **Hackathon Smart City 2026** · Sector: **Smart Cities** · Nicho: **Smart Mobility**  
Equipo: **SRA Smart**

SemáforoVivo Lima es un prototipo web que demuestra cómo una intersección puede distribuir sus tiempos de luz verde según la demanda vehicular simulada y cómo un equipo municipal puede consultar indicadores, revisar cruces, comparar escenarios, registrar incidencias y generar reportes desde una sola plataforma.

> **Importante:** las tres intersecciones y todas las cifras mostradas en el prototipo son datos de demostración o resultados de simulación. No son mediciones reales obtenidas en la vía. El prototipo no está conectado a cámaras, sensores ni controladores semafóricos y no opera semáforos físicos.

🔗 **Demo:** [semaforovivo.vercel.app](https://semaforovivo.vercel.app/)  
💻 **Repositorio:** [github.com/smasfrancis/Semaforo_Vivo](https://github.com/smasfrancis/Semaforo_Vivo)

---

## 🗂️ Estructura del repositorio

```text
Semaforo_Vivo/
├── index.html             # Dashboard municipal
├── mapa.html              # Mapa interactivo de intersecciones
├── simulador.html         # Simulación y comparación de semáforos
├── incidencias.html       # Registro y seguimiento de incidencias
├── reportes.html          # Reportes y exportación PDF/CSV
├── css/
│   └── estilos.css        # Estilos de la plataforma
├── js/
│   └── comun.js           # Datos compartidos, indicadores y alertas
└── README.md              # Documentación del proyecto
```

## 🎯 Problema y oportunidad

La congestión de Lima no solo afecta el desplazamiento de vehículos: también reduce el tiempo disponible para trabajar, estudiar, descansar y compartir con la familia. Además, las intersecciones congestionadas pueden dificultar el cruce peatonal y el desplazamiento de los servicios de emergencia.

Algunos indicadores que dimensionan el problema:

| Evidencia | Qué muestra |
|---|---|
| TomTom Traffic Index 2025 | Lima registró 69,3 % de congestión; recorrer 10 km tomó en promedio 34 min 53 s y se estimaron 195 horas perdidas al año en hora punta. |
| AFIN (2025) | Estimó alrededor de 198 horas anuales perdidas por persona en el tráfico de Lima y Callao. Es una estimación de otra fuente y metodología; no debe sumarse a la cifra de TomTom. |
| Instituto Peruano de Economía (2025) | En diez años, el parque automotor de Lima creció 40 %, mientras que la red vial aumentó 7 %. |
| Agencia Andina (2025) | Reportó un crecimiento de 308,9 % del número de motocicletas en el Perú entre 2010 y 2024. Es un dato nacional, no exclusivo de Lima. |

La gestión de una intersección necesita considerar que el tránsito limeño es mixto: motos, autos, combis y buses comparten vías con peatones y servicios de emergencia. Una programación semafórica rígida puede no responder de la misma manera a las variaciones de demanda durante el día.

### 👥 ¿Para quién está pensado?

- **Usuario principal:** especialistas y encargados de tránsito o movilidad urbana de las municipalidades, como equipos de gestión semafórica y centros de control.
- **Beneficiarios:** conductores, pasajeros de transporte público, motociclistas, peatones, personas con movilidad reducida y servicios de emergencia.
- **Usuarios secundarios potenciales:** universidades y laboratorios que quieran explorar simulaciones de movilidad urbana.

## 💡 Nuestra solución

Semáforo Vivo reúne dos componentes complementarios:

### 1. Semáforo adaptativo simulado

Un modelo de control que revisa la demanda de dos vías y distribuye el tiempo verde según la carga vehicular simulada. También permite representar peatones y activar vehículos de emergencia para observar cómo cambian las decisiones del sistema.

### 2. Panel web municipal

Una plataforma para consultar el estado de las intersecciones de demostración, identificar alertas, analizar escenarios, registrar problemas y generar reportes. Busca convertir los datos de movilidad en información útil para priorizar intervenciones y documentar decisiones.

**Ejemplo:** si la avenida principal tiene una cola simulada de 30 autos y la vía secundaria tiene 3, el modelo puede mantener el verde en la vía con mayor demanda, siempre dentro de los límites de la simulación, en vez de repartir automáticamente el mismo tiempo a ambas vías.

## 🧭 Cómo se utiliza la plataforma

El recorrido está pensado para un encargado municipal de tránsito:

1. **Revisar el Dashboard:** identifica indicadores, alertas y cruces que requieren atención.
2. **Explorar el Mapa:** selecciona una de las intersecciones y revisa sus datos de demostración.
3. **Abrir el Simulador:** carga el escenario de tráfico correspondiente.
4. **Comparar métodos:** ejecuta el modo inteligente y el modo de tiempo fijo con las mismas llegadas simuladas.
5. **Guardar la comparación:** los resultados guardados se reflejan en el Dashboard, el Mapa y los Reportes.
6. **Registrar incidencias:** documenta un problema, asigna responsable y actualiza su estado.
7. **Generar un reporte:** filtra resultados y descarga un documento PDF o un archivo CSV.

El recorrido completo es una estimación de uso del prototipo; el tiempo real de trabajo deberá validarse con personal municipal.

## 🧩 Módulos implementados

| Módulo | Página | Funcionalidad |
|---|---|---|
| Dashboard municipal | `index.html` | KPIs, alertas, comparación de espera y tabla de intersecciones con nivel de congestión y fuente de datos. |
| Mapa interactivo | `mapa.html` | Mapa con tres intersecciones de demostración; permite consultar indicadores y acceder al simulador o al registro de incidencias. |
| Simulador comparativo | `simulador.html` | Representa vehículos y peatones; compara control adaptativo y tiempo fijo bajo condiciones equivalentes. |
| Panel de incidencias | `incidencias.html` | Registra vehículos detenidos, obstáculos, semáforos averiados, accidentes, obras y cruces peatonales inseguros. Permite asignar prioridad, responsable y estado. |
| Generador de reportes | `reportes.html` | Consolida simulaciones guardadas, muestra métricas y conclusiones, lista incidencias pendientes y permite imprimir/guardar PDF o descargar CSV. |

### Intersecciones de demostración

| Intersección | Ubicación referencial |
|---|---|
| Av. Abancay con Av. Nicolás de Piérola | Cercado de Lima |
| Av. Javier Prado con Av. Arequipa | Límite de San Isidro y Lince |
| Av. Universitaria con Av. Venezuela | Entorno Lima / San Miguel |

Las ubicaciones sirven para mostrar el mapa y organizar escenarios del prototipo. Los flujos, esperas, colas y niveles de congestión asociados son datos de demostración o simulación.

## ⚙️ Arquitectura y tecnologías

| Componente | Tecnología | Uso |
|---|---|---|
| Interfaz | HTML5 | Estructura de las páginas. |
| Estilos | CSS3 | Diseño y presentación visual. |
| Lógica | JavaScript | Indicadores, reglas, navegación y simulación. |
| Mapa | Leaflet + OpenStreetMap | Visualización geográfica de intersecciones. |
| Gráficos de simulación | HTML Canvas | Representación paso a paso de vehículos y peatones. |
| Persistencia local | `localStorage` | Guarda simulaciones e incidencias en el navegador. |
| Publicación | Vercel / GitHub Pages | Publicación del sitio estático. |

### Lógica del simulador

El prototipo representa el tráfico mixto mediante una ponderación de carga por tipo de vehículo:

| Tipo de vehículo | Peso simulado |
|---|---:|
| Moto | 0,5 |
| Auto | 1,0 |
| Combi o bus | 2,5 |
| Vehículo de emergencia | 1,0 + prioridad simulada |

El modelo adaptativo revisa la carga de las vías durante la simulación y aplica reglas de cambio de fase. Sus parámetros iniciales de demostración incluyen verde mínimo de 8 s, verde máximo de 45 s, espera máxima en rojo de 90 s, ámbar de 3 s y todo rojo de 2 s. Estos valores pertenecen al modelo del prototipo: **no son una configuración aprobada para semáforos reales**.

En el escenario de simulación:

- Se puede alternar entre control adaptativo y tiempo fijo.
- Se pueden configurar flujos de autos, motos, combis/buses y peatones.
- Se pueden activar ambulancias, bomberos o policía como eventos de emergencia simulados.
- Se representa el cruce de peatones normales y peatones con movilidad reducida.
- El sistema evita que los vehículos simulados avancen sobre el cruce mientras un peatón continúa cruzando.

## 📊 Resultados de las pruebas simuladas

Se realizaron **cinco repeticiones de diez minutos por escenario**. Para que la comparación sea equivalente, ambos métodos utilizan la misma semilla aleatoria: los mismos vehículos y peatones llegan en los mismos momentos. La variable comparada es el método de control del semáforo.

| Escenario | Espera adaptativa | Espera fija | Reducción simulada | Vehículos atendidos (adaptativo / fijo) |
|---|---:|---:|---:|---:|
| Av. Abancay con Av. Nicolás de Piérola | 19,8 s | 30,7 s | **35 %** | 775 / 592 |
| Av. Javier Prado con Av. Arequipa | 17,6 s | 27,7 s | **36 %** | 933 / 745 |
| Av. Universitaria con Av. Venezuela | 17,1 s | 25,5 s | **33 %** | 560 / 524 |
| Valores por defecto | 14,5 s | 20,1 s | **28 %** | 426 / 395 |

### Lectura honesta de los resultados

- En los escenarios probados, el modo adaptativo redujo la espera vehicular entre 28 % y 36 % y atendió más vehículos que el modo de tiempo fijo.
- La espera de las ambulancias también fue menor en los escenarios simulados.
- **Trade-off peatonal:** en algunas pruebas, los peatones esperaron unos segundos más con el modo adaptativo (hasta aproximadamente 4 s). El diseño debe equilibrar la demanda vehicular con tiempos peatonales seguros e inclusivos.
- Estos resultados corresponden exclusivamente al simulador. No demuestran todavía una reducción de congestión o accidentes en las calles de Lima.

## 🧪 Estado actual y limitaciones

### Qué funciona en el prototipo

- Navegación por cinco módulos web.
- Dashboard con indicadores, alertas y niveles de congestión.
- Mapa con tres intersecciones de demostración.
- Simulador de una intersección de dos vías.
- Comparación de control adaptativo y tiempo fijo con las mismas llegadas simuladas.
- Representación de peatones y eventos de vehículos de emergencia.
- Registro, actualización y consulta de incidencias.
- Historial de comparaciones y exportación de reportes PDF/CSV.

### Qué todavía no hace

- No recibe conteos reales de cámaras ni sensores: el detector del simulador es virtual.
- No controla semáforos físicos ni se conecta a controladores semafóricos.
- Simula una intersección de dos vías; no incorpora giros complejos ni coordinación de varias intersecciones u «ola verde».
- Utiliza un modelo simplificado del comportamiento vehicular; no reproduce todos los conflictos, maniobras o condiciones reales de la calle.
- Guarda datos en el `localStorage` del navegador. No cuenta con base de datos central, usuarios, contraseñas ni sincronización entre dispositivos.
- Los datos guardados pueden perderse al borrar el almacenamiento del navegador o cambiar de equipo.

## 🛣️ Ruta de evolución hacia un piloto real

La implementación real requiere validación técnica, datos de campo, coordinación institucional y autorización de las autoridades competentes. La ruta propuesta es gradual:

| Etapa | Objetivo | Trabajo previsto |
|---|---|---|
| 1. Datos reales | Obtener información de 1 a 3 cruces piloto. | Conteos vehiculares y peatonales mediante cámaras adecuadas, sensores o registros autorizados. |
| 2. Calibración | Contrastar el modelo con las condiciones observadas. | Ajustar la simulación con los conteos y revisar resultados con especialistas municipales. |
| 3. Plataforma en servidor | Pasar de almacenamiento local a gestión compartida. | Incorporar base de datos, usuarios por rol y evaluar integración con sistemas municipales como el C5. |
| 4. Piloto controlado | Evaluar una integración semafórica bajo supervisión. | Verificar compatibilidad de controladores, seguridad, autorizaciones y cumplimiento de la normativa aplicable. |
| 5. Red coordinada | Evaluar la coordinación de varios cruces. | Ampliar progresivamente la cobertura y medir resultados antes y después de la intervención. |

Como posible primer entorno de evaluación se propone estudiar intersecciones de San Isidro, debido a sus antecedentes de gestión semafórica centralizada. Esto es una **posibilidad por evaluar**, no una alianza ni una autorización vigente. Una expansión posterior podría estudiarse con la Municipalidad Metropolitana de Lima y sus iniciativas de modernización semafórica y el Centro de Control C5.

La operación sobre semáforos reales no forma parte de este prototipo. Cualquier piloto conectado deberá ser diseñado y supervisado por profesionales competentes, contar con autorización institucional y cumplir las disposiciones técnicas y de tránsito aplicables, incluidas las del MTC y la ATU.

## 🚀 Cómo ejecutar el prototipo

### Requisitos

- Un navegador web actualizado.
- Conexión a internet para cargar los mapas de OpenStreetMap.
- No requiere instalar Node.js, dependencias ni configurar un servidor de backend.

### Opción 1: ejecutar desde una copia local

```bash
git clone https://github.com/smasfrancis/Semaforo_Vivo.git
cd Semaforo_Vivo
```

Abre `index.html` en el navegador. También puedes abrir la carpeta en Visual Studio Code y utilizar una extensión de servidor local estático.

### Opción 2: probar la demo desplegada

Abre [https://semaforovivo.vercel.app/](https://semaforovivo.vercel.app/) y sigue este recorrido:

1. Revisa el Dashboard y sus alertas.
2. Abre el Mapa y selecciona una intersección.
3. Entra al Simulador y compara el modo inteligente con el tiempo fijo.
4. Guarda la comparación.
5. Registra una incidencia de prueba.
6. Abre Reportes y revisa la información exportable.

**Nota sobre persistencia:** los registros se guardan en el navegador mediante `localStorage`; por ello, no se comparten automáticamente entre distintos equipos o navegadores.

## 🏙️ Contexto de Smart Mobility en Lima

Semáforo vivo se plantea como una herramienta demostrativa y potencialmente complementaria a los esfuerzos de modernización de la gestión del tránsito en la ciudad. La Municipalidad Metropolitana de Lima y el Banco Mundial han anunciado un programa de modernización semafórica, y la MML viene implementando el Centro de Control y Monitoreo C5.

El proyecto no busca reemplazar esos programas ni afirmar que las plataformas existentes carecen de funcionalidades específicas. La oportunidad que explora es una capa modular de análisis, simulación, registro de incidencias y reportes que pueda adaptarse a distintas capacidades municipales y evaluarse en pilotos acotados.

## 📚 Fuentes y referencias

Las cifras de contexto provienen de fuentes externas. Las métricas de las tres intersecciones y los resultados comparativos provienen del simulador de este proyecto.

1. Asociación para el Fomento de la Infraestructura Nacional (AFIN). (2025). [Tráfico en Lima y Callao genera pérdidas por S/ 27 691 millones al año](https://afin.org.pe/wp-content/uploads/2025/08/06.05.25-AFIN_Trafico-en-Lima-y-Callao-genera-perdidas-por-27691-millones-al-ano.pdf).
2. TomTom. (s. f.). [Lima, Peru: Traffic Index](https://www.tomtom.com/traffic-index/city/lima/).
3. Instituto Peruano de Economía. (2025). [En los últimos diez años, el parque automotor en Lima creció 40 %, pero la red vial apenas 7 %](https://ipe.org.pe/en-los-ultimos-diez-anos-el-parque-automotor-en-lima-crecio-40-pero-la-red-vial-apenas-7/).
4. Agencia Andina. (2025). [Día del Motociclista: ¿Cómo y por qué aumentó el número de motos en el Perú?](https://andina.pe/agencia/noticia-dia-del-motociclista-como-y-por-aumento-numero-motos-el-peru-1054515.aspx).
5. Instituto Nacional de Estadística e Informática. (2025). [Estadísticas de la criminalidad, seguridad ciudadana y violencia: primer semestre de 2025](https://www.inei.gob.pe/media/MenuRecursivo/boletines/seguridad-i-semestre-2025.pdf).
6. Banco Mundial. (2024). [Modernizar la gestión del tráfico en Lima con apoyo del Banco Mundial](https://www.bancomundial.org/es/news/press-release/2024/10/15/modernizing-traffic-management-in-lima-with-world-bank-support).
7. Municipalidad Metropolitana de Lima. (2026). [Primer desembolso del Banco Mundial para iniciar el proyecto de semaforización inteligente en Lima Metropolitana](https://www.gob.pe/institucion/munilima/noticias/1418692).
8. Municipalidad Metropolitana de Lima. (2026). [Centro de Control y Monitoreo C5 alcanza el 60 % de avance](https://www.gob.pe/institucion/munilima/noticias/1475628).
9. Federal Highway Administration. (s. f.). [Adaptive Signal Control FAQs](https://www.fhwa.dot.gov/innovation/everydaycounts/edc-1/asct-faqs.cfm).
10. Smith, S. F., Barlow, G. J., Xie, X.-F., & Rubinstein, Z. B. (2013). [Smart Urban Signal Networks: Initial Application of the SURTRAC Adaptive Traffic Signal Control System](https://www.cmu.edu/traffic21/pdfs/6054-30129-1-pb.pdf). Carnegie Mellon University.
11. Ministerio de Transportes y Comunicaciones. (2016). [Manual de Dispositivos de Control del Tránsito Automotor para Calles y Carreteras](https://www.gob.pe/institucion/mtc/normas-legales/4444240-16-2016-mtc-14).
12. Perú. (2009). [Decreto Supremo N.° 016-2009-MTC: Reglamento Nacional de Tránsito](https://www.gob.pe/institucion/mtc/normas-legales/9897-016-2009-mtc).
13. Perú. (2018). [Ley N.° 30900, Ley que crea la Autoridad de Transporte Urbano para Lima y Callao](https://busquedas.elperuano.pe/dispositivo/NL/1727064-7).
14. Leaflet. (s. f.). [Documentación de Leaflet](https://leafletjs.com/).
15. OpenStreetMap. (s. f.). [Copyright y atribución](https://www.openstreetmap.org/copyright).

---

## 🤝 Equipo

**SRA Smart** · Hackathon Smart City 2026  
Proyecto académico de innovación para la movilidad urbana de Lima.

---

**Semáforo Vivo: no queremos que Lima solamente tenga semáforos más modernos; queremos que sus intersecciones respondan mejor a las necesidades de las personas.**

# BibliometriX

**Análisis bibliométrico de código abierto, sin backend, sin instalación.**

BibliometriX es una herramienta web de un solo archivo (zero-dependency, salvo Chart.js vía CDN) que convierte tus exportaciones de Scopus o Web of Science en un dashboard completo de indicadores bibliométricos, directamente en el navegador.

🔗 **Demo en vivo:** https://rekol08.github.io/BibliometriX/

---

## Características

- **Carga múltiple con deduplicación por DOI** — combina Scopus + WoS sin duplicados.
- **Parser robusto** — CSV, TSV y BibTeX; detección automática de delimitador; soporta campos multilínea (abstracts, afiliaciones) y BOM de Scopus.
- **Indicadores generales** — publicaciones, citas totales, autores únicos, fuentes, rango temporal.
- **Índices de citación** — h-index, g-index, i10-index, citas promedio por documento, citas normalizadas por antigüedad.
- **Ley de Lotka** — distribución de productividad de autores.
- **Ley de Bradford** — zonas de dispersión de revistas (núcleo y periferia).
- **Co-ocurrencia de palabras clave** — pares de keywords que aparecen juntas con mayor frecuencia.
- **Red de coautoría** — pares de autores que firman juntos, índice de colaboración (autores/documento).
- **Países y colaboración internacional** — a partir del campo de afiliaciones, % de documentos con colaboración entre dos o más países.
- **Tasa de crecimiento (CAGR)** de la producción científica.
- **Panel de filtros globales** — por rango de años, tipo de documento e idioma; recalcula todos los indicadores, no solo la tabla.
- **Tabla de publicaciones** — ordenable, buscable, paginada, con enlaces DOI y documentos más citados resaltados.
- **Exportación** — CSV, JSON, gráficos en PNG, y reporte imprimible en PDF.

## Cómo usarlo

1. **Exporta tu búsqueda** desde Scopus o Web of Science: selecciona todos los registros → *Export* → CSV (Scopus) o CSV/TSV (WoS) → incluye todos los campos disponibles (autores, citas, afiliaciones, keywords).
2. **Carga el archivo** en BibliometriX arrastrándolo a la zona de carga, o selecciónalo con el explorador de archivos. Puedes cargar varios archivos a la vez; se fusionan y deduplican automáticamente por DOI.
3. **Explora y filtra** — usa el panel de filtros para acotar por año, tipo de documento o idioma. Todos los gráficos, índices y la tabla se recalculan al instante.
4. **Exporta lo que necesites** — CSV, JSON, gráficos individuales en PNG, o el reporte completo en PDF vía impresión del navegador.

También puedes usar el botón **"Cargar datos de demostración"** en la página principal para explorar la herramienta sin necesidad de tener un archivo propio a mano.

## Formatos soportados

| Fuente | Formato | Notas |
|---|---|---|
| Scopus | CSV | Incluye BOM UTF-8 automáticamente manejado |
| Web of Science | CSV / TSV | Delimitador detectado automáticamente |
| Cualquiera | BibTeX (.bib) | Soporte básico de campos estándar |

## Privacidad

Todo el procesamiento ocurre **en tu navegador**. Ningún archivo, dato ni resultado se envía a un servidor externo. Puedes verificarlo tú mismo: es un único archivo HTML sin llamadas de red salvo la carga de la fuente de Chart.js.

## Stack técnico

- HTML, CSS y JavaScript vanilla — sin build, sin framework.
- [Chart.js](https://www.chartjs.org/) para visualizaciones, cargado vía CDN.
- Un solo archivo (`index.html`), pensado para desplegarse tal cual en GitHub Pages o cualquier hosting estático.

## Limitaciones conocidas

- El parseo corre en el hilo principal; archivos muy grandes (varios miles de registros) pueden tardar unos segundos.
- La co-ocurrencia de keywords y la red de coautoría se muestran como tablas de pares, no como grafo de red interactivo.
- El campo de acceso abierto (Open Access) se lee del archivo pero aún no se refleja en el dashboard.

## Cómo contribuir

Los issues y pull requests son bienvenidos — ya sea para reportar un bug, sugerir un indicador bibliométrico adicional, o mejorar el parser para un formato de exportación distinto.

## Cómo citar

Si usas BibliometriX en un trabajo académico o metodología de investigación, por favor cítalo usando la información en [`CITATION.cff`](./CITATION.cff).

## Licencia

Distribuido bajo licencia MIT. Consulta [`LICENSE`](./LICENSE) para más detalles.

---

Desarrollado por [REKOL08](https://github.com/REKOL08) · Pereira, Colombia

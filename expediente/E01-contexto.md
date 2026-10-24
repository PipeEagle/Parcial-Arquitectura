# E01 - Comprensión del problema, requisitos y alcance (ARQ-01)

**Insumo técnico:** Manual de Fundamentos §1 (no localizado en el espacio de trabajo; consultar antes de dar por concluido el análisis).

## Ticket

- **ID:** ARQ-01 / E01
- **Solicitud empresarial:** Operaciones necesita registrar y consultar órdenes de equipos de bodega. Esta formulación procede del escenario proporcionado para el ticket; no se localizó un documento empresarial independiente. [DOCUMENTADO]
- **Versión/fecha/entorno:** Versión no identificada; 2026-10-24; inspección estática de la copia local. No se ejecutó una prueba interactiva para esta evidencia.
- **Responsable:** [Completar]
- **Archivos y componentes observados:** `frontend/index.html` (interfaz); `backend/app/ordenes/controladores.py` (API); `backend/app/ordenes/modelos.py` (modelo persistente). [CODIGO]
- **Acciones reproducidas, paso a paso:**
  1. Se inspeccionó `frontend/index.html`: campos obligatorios `equipo` y `descripcion`, botón “Registrar orden”, botón “Consultar ordenes” y área de estado/lista. [CODIGO]
  2. Se inspeccionó `backend/app/ordenes/controladores.py`: `GET /api/ordenes` consulta y responde con `success` y `data`; `POST /api/ordenes` recibe JSON, responde `400` para entrada no objeto o error de validación, y `201` al crear. [CODIGO]
  3. Se inspeccionó `backend/app/ordenes/modelos.py`: la entidad `ordenes` declara `id`, `equipo`, `descripcion` y `estado`; los campos de equipo y descripción son obligatorios. [CODIGO]
  4. Se buscó contrastar las capacidades con RF-01, RF-02 y RN-01; esas definiciones no fueron proporcionadas ni localizadas, por lo que el contraste queda pendiente. [OBSERVADO]
  5. No se envió una solicitud HTTP ni se comprobó en navegador la persistencia de una orden durante esta revisión. [OBSERVADO]
  6. Se revisaron las afirmaciones de alcance para no presentar como hechos el tráfico, la seguridad por roles ni integraciones externas: los archivos inspeccionados no aportan evidencia de esos aspectos. [OBSERVADO]
- **Resultado observado (captura, prueba, log):** El código define consulta y registro de órdenes mediante la API y declara cuatro campos en el modelo. No se generó captura, prueba de ejecución ni log para este ticket. [CODIGO]
- **Origen de la información:** Inspección de los tres archivos listados; referencias RF-01, RF-02, RN-01 y Manual de Fundamentos no disponibles en la copia revisada. [OBSERVADO]
- **Interpretación arquitectónica:** Dentro de la solución están la interfaz HTML/JavaScript, la API Flask y la persistencia modelada mediante SQLAlchemy. La configuración establece SQLite como valor predeterminado y permite sustituir la URL mediante `DATABASE_URL`; no se verificó cuál configuración se usa al ejecutar. [CODIGO]
- **Clasificación:** OBSERVADO / CODIGO / DOCUMENTADO / SUPUESTO / PROPUESTO. Afirmaciones de implementación arriba etiquetadas como CODIGO; requisitos de negocio y aceptación permanecen sin verificar. [OBSERVADO]
- **Riesgo, alternativa y pendiente:** Sin RF-01, RF-02, RN-01 y una solicitud empresarial formal no se puede confirmar cobertura de requisitos. Quedan pendientes usuarios concurrentes, autenticación real, métricas, retención y objetivos de calidad. Obtener esos insumos y probar GET/POST en entorno local con datos de prueba; no usar producción. [OBSERVADO]
- **Criterio de aceptación comprobado:** Parcial: se identificaron controles de interfaz, endpoints y campos del modelo por inspección de código. No comprobado: conformidad con RF-01/RF-02/RN-01 ni funcionamiento extremo a extremo. [OBSERVADO]
- **Límite de la conclusión:** Describe únicamente lo declarado en los archivos observados; no acredita permisos, roles, comportamiento en ejecución, configuración activa, datos reales ni cumplimiento de requisitos no suministrados.
- **Rama y commit revisados (si aplica):** No aplica; no se identificó una copia Git para esta revisión.

> No incluir datos de producción, tokens ni secretos en este expediente. Usar datos de prueba autorizados.

## Problema

- Operaciones necesita registrar y consultar órdenes de equipos de bodega. La necesidad proviene del escenario suministrado para este ticket, no de una fuente empresarial independiente. [DOCUMENTADO]
- La interfaz respalda las funciones visibles de captura y consulta de órdenes; esto describe lo implementado, no sustituye la necesidad de negocio. [CODIGO]

## Actores

- Operador de operaciones y coordinador son actores del escenario documentado para este ticket. [DOCUMENTADO]
- No existen cuentas ni autenticación implementadas en los archivos observados; no se atribuyen permisos diferentes ni controles de acceso a esos actores. [CODIGO]

## Funciones existentes

- Capturar equipo y descripción y enviar el registro mediante `POST /api/ordenes`. [CODIGO]
- Consultar órdenes mediante `GET /api/ordenes` y mostrarlas en la interfaz. [CODIGO]

## Frontera

- **Dentro de la solución:** interfaz HTML/JavaScript del navegador, API Flask y persistencia relacional modelada con SQLAlchemy. La configuración predeterminada apunta a SQLite; `DATABASE_URL` puede cambiarla. [CODIGO]
- **Fuera de la solución observada:** personas y computadores cliente son participantes/recursos del escenario, no componentes implementados. No se observaron servicios externos integrados. [OBSERVADO]
- Esta frontera se limita a `frontend/index.html`, `app.js`, `backend/app.py`, `backend/app/__init__.py` y los componentes del dominio de órdenes; no afirma características del entorno desplegado. [CODIGO]

## Asuntos pendientes

- Consultar el Manual de Fundamentos §1 y obtener la solicitud empresarial.
- Obtener RF-01, RF-02 y RN-01 y comprobar cada criterio mediante pruebas.
- Confirmar entorno/configuración y registrar evidencia de ejecución en ambiente local de pruebas.
- Confirmar necesidades de usuarios concurrentes, autenticación, métricas, retención y objetivos de calidad.

## Comprobación de afirmaciones sin evidencia

- **Tráfico/carga:** no se afirma volumen, concurrencia ni patrón de tráfico; quedan pendientes de medición o requisito. [OBSERVADO]
- **Seguridad por roles:** no se afirma que existan roles implementados, cuentas ni permisos; los actores son parte del escenario, no evidencia de autorización. [OBSERVADO]
- **Servicios externos:** no se afirma integración con servicios externos; no se encontró ninguna en los componentes revisados. [OBSERVADO]
- **Aceptación ARQ-01:** E01 diferencia problema de negocio documentado, funciones y componentes declarados en código, restricciones observadas y asuntos pendientes. Ninguna tecnología se presenta como el problema empresarial. [OBSERVADO]

## Evidencias relacionadas

- `frontend/index.html`
- `backend/app/ordenes/controladores.py`
- `backend/app/ordenes/modelos.py`

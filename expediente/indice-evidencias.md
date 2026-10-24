# Índice de evidencias

## Campos obligatorios por evidencia

Completar en cada documento: ID, versión del sistema, fecha, responsable, acción
ejecutada, resultado observado, origen de la información, interpretación y
límite de la conclusión. Si se utilizó Git, registrar también la rama y el
commit de la copia revisada; si no, indicar que no aplica.

No incluir datos de producción, tokens ni secretos. Usar únicamente información
de la copia local y datos de prueba autorizados.

## Plantilla de tickets

Los documentos E01–E11 contienen un ticket con solicitud empresarial,
versión/fecha/entorno, responsable, archivos y componentes, pasos reproducidos,
resultado observado, origen, interpretación arquitectónica, clasificación,
riesgo/alternativa/pendiente, criterio de aceptación, límite de conclusión y,
si se utilizó Git, rama y commit. Completar los campos con evidencia; no
presentar supuestos como observaciones.

Antes de analizar un ticket, consultar la sección homónima del Manual de
Fundamentos y registrar la referencia. El manual no se encontró en esta copia
del espacio de trabajo.

### Instrucción para otros proyectos

Usar la misma plantilla, pero reemplazar los ejemplos de órdenes, rutas,
requisitos y componentes por los equivalentes reales del proyecto evaluado.
Identificar primero la solicitud empresarial, interfaz, endpoints y modelo de
dominio disponibles; verificar los requisitos contra esos insumos y dejar como
pendiente cualquier información ausente. No asumir roles, permisos ni
comportamientos que no estén respaldados por código, documentación o pruebas.

## Documentos

- [E01 — Contexto](E01-contexto.md)
- [E02 — Recursos](E02-recursos.md)
- [E03 — Contexto C4](E03-contexto-c4.md)
- [E04 — Contenedores](E04-contenedores.md)
- [E05 — Propuesta](E05-propuesta.md)
- [E06 — Alternativas](E06-alternativas.md)
- [E07 — Calidad](E07-calidad.md)
- [E08 — Modularidad](E08-modularidad.md)
- [E09 — Integración](E09-integracion.md)
- [E10 — Riesgos](E10-riesgos.md)
- [E11 — Decisión](E11-decision.md)

## Decisiones arquitectónicas

- [ADR-001](decisiones/ADR-001.md)

## Evidencias complementarias

- `capturas/`: capturas de pantalla.
- `diagramas/`: diagramas de arquitectura.
- `mediciones/`: resultados de mediciones.

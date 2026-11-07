# Caso de estudio — SIRE Control

**Categoría:** Conciliación tributaria · Calidad de datos · Automatización  
**Rol:** Diseño de reglas de negocio, desarrollo y pruebas  
**Estado:** Sistema desarrollado y desplegado para validación

## Problema

La comparación entre el **SIRE/RCE de SUNAT** y los registros internos de compras puede requerir revisión manual de archivos, detección de discrepancias y seguimiento de observaciones entre periodos.

## Solución

Desarrollé **SIRE Control**, un motor en **Python y FastAPI** para conciliar comprobantes mediante criterios deterministas, identificar diferencias y mantener trazabilidad de registros. El diseño contempla separación de información por empresa y seguimiento de comprobantes con observaciones.

## Tecnologías

Python · FastAPI · procesamiento de archivos · reglas deterministas · pytest · Render

## Evidencia de ingeniería

- **Más de 1,400 pruebas automatizadas**, según el registro del proyecto.
- Reglas explícitas de conciliación y validación.
- Despliegue de la aplicación en Render.

## Estado e impacto

Es una solución para validar y estructurar el control de discrepancias. No publico una cifra de ahorro de tiempo, reducción de errores ni retorno financiero porque no hay una medición consolidada que la sustente.

> El código y las fuentes de datos permanecen privados para proteger información contable y evitar divulgar datos de terceros.

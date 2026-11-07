# 🧾 SIRE Control — Software de conciliación tributaria a medida

[![Estado](https://img.shields.io/badge/Estado-desarrollado%20%2F%20validaci%C3%B3n-2563EB?style=for-the-badge)](../README.md#-proyectos-destacados)
![Testing](https://img.shields.io/badge/Tests-1400%2B-16804A?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-FastAPI-374151?style=for-the-badge)

**Rol:** diseño del motor de conciliación, reglas de negocio, procesamiento de datos y pruebas.  
**Cliente objetivo:** consultora contable que gestiona información de múltiples empresas.

## 🎯 El problema

Una consultora contable necesitaba comparar periódicamente la información del **Sistema Integrado de Registros Electrónicos (SIRE/RCE) de SUNAT** con su **Registro de Compras** exportado del software contable. La revisión en Excel exigía identificar discrepancias por comprobante y dar seguimiento a pendientes de meses anteriores.

## 🧠 La solución

Desarrollé **SIRE Control**, software a medida orientado al **control longitudinal de comprobantes**. Su objetivo es transformar archivos contables en diferencias trazables y resultados de conciliación reproducibles.

### ⚙️ Flujo de trabajo

1. 📥 **Ingesta:** lectura de archivos Excel, CSV y PDF; registro de procedencia del archivo procesado.
2. 🪪 **Identificación determinista:** cruce de comprobantes utilizando **RUC, tipo, serie y número**; sin depender de coincidencias vagas generadas por un LLM.
3. ⚖️ **Conciliación tributaria:** comparación de importes, base imponible e IGV según las columnas y reglas disponibles en cada fuente.
4. 🕒 **Seguimiento temporal:** detección de comprobantes pendientes, arrastre entre meses y consultas sobre el estado de regularización.
5. 🔍 **Trazabilidad:** referencia a empresa, proveedor, archivo, hoja y fila de origen para facilitar revisiones.
6. 📊 **Salida estructurada:** reportes de hallazgos y diferencias que apoyan la revisión contable.

## 🧱 Arquitectura

| Componente | Implementación |
|---|---|
| 🐍 Núcleo | Python 3.12, reglas deterministas y procesamiento modular |
| 🚀 Servicios | FastAPI para exponer funcionalidades del sistema |
| 📁 Lectores | Ingesta y normalización de XLSX, CSV y PDF |
| 🔐 Datos | Separación de información por empresa y conservación de procedencia |
| 🧪 Calidad | pytest y **más de 1,400 pruebas automatizadas** reportadas |
| ☁️ Despliegue | Render, según el estado documentado del proyecto |

## ✅ Alcance y estado

El software permite organizar la comparación entre fuentes y analizar discrepancias de forma estructurada. El desarrollo incluye validaciones sobre archivos y escenarios reales; su evolución y adopción operativa siguen sujetas a verificación con el cliente.

<details>
<summary><strong>🔎 ¿Por qué es relevante para fintech, banca y control de riesgos?</strong></summary>

El proyecto trabaja con capacidades transferibles a procesos financieros: conciliación de datos, auditoría de reglas, consistencia de resultados, aislamiento por cliente, seguimiento de excepciones y evidencia verificable.

No se presenta como un sistema bancario ni como una solución de IA generativa que toma decisiones tributarias por sí sola.

</details>

> 🔒 **Confidencialidad:** código y fuentes contables privados. No se publican datos fiscales de empresas, cifras de ahorro no medidas ni credenciales.

[⬅️ Volver al portafolio](../README.md#-proyectos-destacados)

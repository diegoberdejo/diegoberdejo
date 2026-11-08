# 🤖 Jacobot — Agente de IA empresarial para Microsoft 365

![Estado](https://img.shields.io/badge/Estado-preproducci%C3%B3n-D97706?style=for-the-badge)
![Tecnología](https://img.shields.io/badge/Python-FastAPI-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Integración](https://img.shields.io/badge/Microsoft_Graph-Entra_ID-0078D4?style=for-the-badge)
![Pruebas](https://img.shields.io/badge/100%2B-pruebas-16804A?style=for-the-badge)

**Categoría:** Agentes empresariales de IA · Microsoft 365 · Seguridad  
**Rol:** Arquitectura y desarrollo de IA  
**Estado:** En preproducción

## Problema

Las organizaciones necesitan interactuar con documentos y herramientas de Microsoft 365 sin sacrificar controles de acceso, trazabilidad ni aprobación de acciones sensibles.

## Solución

Trabajo en **Jacobot**, un agente empresarial con un **Tool Gateway** desarrollado en Python/FastAPI. El gateway recibe llamadas estructuradas a herramientas, valida políticas y permisos, integra Microsoft Graph y registra las operaciones para auditoría.

## Diseño de seguridad

- Autenticación empresarial con **Entra ID**.
- Integración con **Microsoft Graph** mediante OAuth 2.0 On-Behalf-Of.
- Aprobación humana para acciones que lo requieren (**human-in-the-loop**).
- Principios de mínimo privilegio y controles de protección de datos.

## Tecnologías y validación

Python · FastAPI · Pydantic · SQLAlchemy · Alembic · Microsoft Graph · Entra ID · OAuth 2.0 · pytest

El proyecto cuenta con **más de 100 pruebas automatizadas**, de acuerdo con su documentación de desarrollo.

## Estado e impacto

**No está presentado como producto en producción**. Su principal valor demostrable en esta fase es la arquitectura del agente, sus integraciones y los controles de seguridad y calidad.

> El repositorio permanece privado. Esta ficha omite credenciales, configuraciones internas e información de terceros.

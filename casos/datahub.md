# 🏢 DataHub — Plataforma de gestión empresarial

[![Estado](https://img.shields.io/badge/Estado-implementado-16804A?style=for-the-badge)](../README.md#-proyectos-destacados)
![Módulos](https://img.shields.io/badge/11-m%C3%B3dulos-2563EB?style=for-the-badge)
![Sedes](https://img.shields.io/badge/2-sedes-Ate%20%2B%20Gamarra-64748B?style=for-the-badge)

**Rol:** análisis de procesos, diseño de arquitectura y desarrollo full stack.  
**Tipo:** aplicación empresarial privada con integración ERP.

## 🎯 El problema

La operación dependía de hojas de cálculo y controles fragmentados. Era necesario concentrar información, coordinar trabajo de colaboradores y dar al gerente general visibilidad sobre las tareas y el funcionamiento de distintas áreas y sedes.

## 🛠️ La solución

Desarrollé **DataHub**, una plataforma empresarial de **11 módulos** que conecta actividades administrativas, operativas y comerciales con **Odoo 19**. Entre las funciones implementadas destacan:

- 📋 **Tablero de gestión de tareas y seguimiento operativo:** pendientes por responsable, prioridad, vencimiento y estado. Facilita que el gerente general asigne y supervise el avance de sus colaboradores.
- 📦 **Inventario y repuestos:** control y consulta de productos mediante **SKU y códigos de barras**.
- 💵 **Caja por sede:** operación y seguimiento de caja para las sedes de **Ate y Gamarra**.
- 💬 **Chat interno:** comunicación y coordinación entre usuarios desde la plataforma.
- 🧩 **Gestión empresarial centralizada:** módulos para clientes, casos, cobranzas, punto de venta, métricas y otros procesos de operación.

**Nombre técnico del tablero:** *dashboard de seguimiento operativo y gestión de tareas* (también llamado *task management dashboard*).

## 🧱 Arquitectura y tecnologías

| Capa | Tecnologías y función |
|---|---|
| 🖥️ Interfaz | Next.js, React y TypeScript; navegación por módulos |
| 🔌 Integración | API JSON-RPC para conectar procesos con Odoo 19 ERP |
| ⚙️ Lógica | Reglas de negocio, validaciones y automatizaciones de la aplicación |
| 👥 Operación | Usuarios, responsabilidades, seguimiento y chat interno |

## 📈 Resultado

- Entrega inicial en **2 meses**, según el historial del proyecto.
- Sustitución de controles anteriormente mantenidos en Excel.
- Uso real en la empresa; la adopción inicial reportada fue de **4 personas, incluida la gerencia**. El número actual de usuarios no se publica como una métrica verificada.
- Evolución funcional hasta una plataforma de **11 módulos** con gestión de inventario y caja por sede.

<details>
<summary><strong>🔎 ¿Qué demuestra este proyecto?</strong></summary>

- Capacidad de traducir necesidades del gerente y de usuarios operativos en requisitos de software.
- Integraciones de negocio con ERP y flujos administrativos reales.
- Diseño de una plataforma modular que puede evolucionar con los procesos de la empresa.
- Entrega de producto utilizado en operaciones, no solo un prototipo visual.

</details>

> 🔒 **Confidencialidad:** no se publica el repositorio, nombres de colaboradores, tareas internas, transacciones ni capturas identificables del cliente. No se atribuyen ahorros económicos sin mediciones.

[⬅️ Volver al portafolio](../README.md#-proyectos-destacados)

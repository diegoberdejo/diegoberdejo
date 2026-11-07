# 🏢 DataHub — Plataforma de operaciones y gestión empresarial

![Producción](https://img.shields.io/badge/Estado-en%20producci%C3%B3n-16804A?style=for-the-badge)
![Módulos](https://img.shields.io/badge/11-m%C3%B3dulos%20de%20negocio-2563EB?style=for-the-badge)
![Sedes](https://img.shields.io/badge/Sedes-Ate%20%2B%20Gamarra-64748B?style=for-the-badge)
![Tecnología](https://img.shields.io/badge/Next.js%2016-React%2019-111827?style=for-the-badge&logo=nextdotjs&logoColor=white)

**Tipo de producto:** sistema web de gestión de operaciones, CRM e integración ERP.  
**Rol:** levantamiento de requisitos, diseño de arquitectura, desarrollo full stack e implementación.  
**Usuarios:** aproximadamente 20, según la documentación del proyecto (no equivale a usuarios concurrentes).  
**Código:** privado por confidencialidad.

## 🎯 Problema de negocio

La empresa utilizaba distintas herramientas para gestionar sus operaciones: **Odoo, archivos Excel en OneDrive y conversaciones de WhatsApp**. Esa fragmentación dificultaba el seguimiento de tareas, la consulta del inventario, las cobranzas y la supervisión entre las sedes de **Ate y Gamarra**.

## 🚀 Solución

Diseñé y desarrollé **DataHub**, una plataforma que centraliza procesos empresariales en **11 módulos principales de negocio**, con vistas adicionales de soporte y administración. El sistema combina información del ERP con datos propios para tareas, chat, caja y seguimiento.

### 🧩 Funcionalidades principales

| Área | Funcionalidad |
| --- | --- |
| 📊 **Dashboard operativo** | Resumen del día, casos abiertos, alertas e indicadores de operación |
| ✅ **Pendientes — tablero de gestión de tareas** | Seguimiento por colaborador, estado, prioridad y vencimiento; comentarios por tarea, notificaciones y supervisión gerencial |
| 📦 **Inventario** | Consulta de productos mediante SKU y **lector de código de barras**, stock por ubicación e imágenes |
| 🧰 **Repuestos** | Catálogo, carrito local y generación de órdenes de compra en Excel |
| 💵 **Caja por sede** | Libro de ingresos y egresos en soles y dólares, distintos medios de pago y saldos arrastrados |
| 🧾 **Cobranzas** | Seguimiento de facturas, cuotas, pagos y vencimientos, con observaciones por cuota |
| 🛠️ **Casos y clientes** | Tickets de soporte, historial, adjuntos y fichas de clientes |
| 🚢 **Contenedores** | Seguimiento de importaciones y estados por máquina |
| 🧮 **Punto de venta y métricas** | Ventas del día, indicadores y reportes |
| 💬 **Chat interno** | Mensajería entre colaboradores y conversación contextual en tareas |
| 👥 **Usuarios y permisos** | Administración de cuentas, roles y acceso por sección y persona |

También incluye una vista de monitor para pantallas del taller y herramientas administrativas.

<details>
<summary><strong>🔎 ¿Qué tipo de dashboard es el de Pendientes?</strong></summary>

Es un **dashboard de seguimiento operativo y gestión de tareas (task management dashboard)**, con una experiencia de tablero tipo Monday. Permite al gerente general revisar pendientes, responsables, estados, prioridades, fechas y conversaciones asociadas a cada tarea. No se presenta como un sistema de medición de productividad individual automática.

</details>

## 🧱 Arquitectura real

| Componente | Implementación |
| --- | --- |
| 🌐 Framework | **Next.js 16.2.1** (App Router) y **React 19.2.4** |
| 🟨 Lenguaje | **JavaScript**, no TypeScript |
| ⚡ Runtime | Node.js 24 |
| 🎨 UI | CSS propio con variables; **sin Tailwind ni biblioteca de componentes** |
| 🗄️ Datos internos | **Neon PostgreSQL serverless**, mediante driver HTTP |
| 🔗 ERP | **Odoo 19 Enterprise**, API **JSON-2** |
| 🔐 Sesiones | Cookies seguras y sesión stateless firmada con **HMAC-SHA256**; contraseñas con scrypt |
| ✅ Validación | **Zod 4** en endpoints y entradas del sistema |
| 📁 Exportaciones | ExcelJS y JSZip para archivos de negocio |
| 💾 Datos locales | IndexedDB para el carrito de repuestos |
| 🧪 Pruebas | Scripts con assert de Node y pruebas con Puppeteer |
| ☁️ Publicación | **Vercel**, con despliegues automatizados desde la rama principal |

### 🔄 Separación de responsabilidades

- **Odoo** es la fuente de verdad para inventario, ventas, compras, facturación y tickets. La integración es **principalmente de lectura**; existe una operación acotada para actualizar estado y nota de máquinas importadas.
- **Neon PostgreSQL** conserva información propia del DataHub: tareas, conversaciones, usuarios, permisos, cobranza y movimientos de caja.
- **Next.js** proporciona la interfaz, las rutas de servidor y el control de acceso a las funcionalidades.
- **El frontend no es la barrera de seguridad:** los permisos también se comprueban en los endpoints.

<details>
<summary><strong>🔐 Seguridad, permisos y trazabilidad</strong></summary>

- Control de acceso por **rol y permisos específicos por persona**.
- Verificación de autorización en servidor y visibilidad de secciones en interfaz.
- Validación de entradas con Zod, protección CSRF y límites de solicitudes.
- Sesiones firmadas, cookies HttpOnly y políticas de cabeceras de seguridad.
- Sanitización de contenido proveniente de fuentes externas y registros de auditoría.
- En **Caja 2**, los movimientos incorrectos se **anulan** con justificación en vez de borrarse, preservando el historial de caja.
- En **Cobranzas**, el seguimiento se realiza por **factura y cuota**, evitando mezclar observaciones de distintos vencimientos.

No se publican rutas internas de protección, parámetros de defensas ni configuraciones sensibles.

</details>

## 📈 Resultado y decisiones de ingeniería

- Se entregó una primera solución en aproximadamente **dos meses** y evolucionó hacia la plataforma actual.
- Centraliza operaciones que antes estaban distribuidas entre ERP, Excel y mensajería.
- La documentación más reciente menciona **alrededor de 20 usuarios**; la cifra no debe interpretarse como un conteo auditado de usuarios activos.
- El tablero y el chat emplean **consultas periódicas (polling)** en lugar de WebSockets, una decisión de arquitectura según escala y necesidades del proyecto.
- El sistema prioriza la **trazabilidad contable**, el control de permisos y la integración de fuentes de datos existentes.

> 🔒 **Confidencialidad:** este caso de estudio describe las capacidades y decisiones técnicas sin publicar el nombre del cliente, el dominio de producción, datos de colaboradores, transacciones, credenciales o código privado. No se atribuyen ahorros o resultados financieros no medidos.

[⬅️ Volver al portafolio](../README.md#-proyectos-destacados)

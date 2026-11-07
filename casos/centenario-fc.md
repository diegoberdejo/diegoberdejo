# ⚽ Centenario FC — PWA de gestión integral de fútbol amateur

[![Estado](https://img.shields.io/badge/Estado-en%20producci%C3%B3n-16804A?style=for-the-badge)](https://www.centenario-fc.app/)
![Plataforma](https://img.shields.io/badge/Plataforma-PWA-0F2A44?style=for-the-badge)
![Next.js](https://img.shields.io/badge/Next.js-16-111827?style=for-the-badge&logo=nextdotjs&logoColor=white)

**Rol:** desarrollo full stack, experiencia de usuario, lógica del negocio y pruebas.  
**Uso:** aplicación privada de un club de fútbol amateur en Lima.

**🌐 Aplicación:** [www.centenario-fc.app](https://www.centenario-fc.app/) — requiere acceso autorizado para utilizar las funciones internas.

## 🎯 El problema

La organización de pichangas mediante hojas de cálculo y conversaciones de WhatsApp genera trabajo manual para administrar convocatorias, pagos, estadísticas y reglas del club.

## 📱 La solución

Desarrollé una **Progressive Web App (PWA)** que funciona en celular y computadora, y puede instalarse como una aplicación. Centraliza la gestión deportiva, administrativa y financiera del grupo.

### 🧩 Módulos y flujos principales

- 👤 **Jugadores:** acceso con celular y PIN, fichas de perfil, fotos, posiciones y plantel.
- 🗓️ **Pichangas:** titulares, suplentes, bajas, invitados, suspensiones, equipos automáticos y alineaciones.
- 📝 **Acta de partido:** goles, faltas, llegadas tarde, ausencias y pagos, con seguimiento por jugador.
- 🏆 **Votaciones y reconocimientos:** MVP, menciones y votaciones anónimas bajo reglas definidas.
- 📊 **Competencia:** rankings mensual y anual, estadísticas y reglamento.
- 💰 **Administración:** caja, deudas, fondos, cuotas, movimientos y auditoría.
- 📢 **Comunicación:** anuncios, galería, novedades e imágenes para compartir en WhatsApp.
- 📈 **Panel de uso:** estadísticas de visitas y actividad, solo para administradores.

### 🔄 Ejemplo del flujo

1. La administración crea y organiza la pichanga.
2. Se administra la convocatoria y los equipos.
3. Al terminar, se guarda el acta y se abre la votación.
4. Al cerrar la votación, se publican MVP y menciones y se actualiza el ranking.
5. Pagos, observaciones y movimientos quedan registrados en el sistema.

## 🧱 Stack

| Área | Tecnología |
|---|---|
| 🌐 Frontend y servidor | Next.js 16, React 19, TypeScript |
| 🎨 Diseño | Tailwind CSS 4, tipografías Barlow, iconos Lucide y Motion |
| 🗄️ Datos y usuarios | Supabase: PostgreSQL, Auth, Storage y Row-Level Security (RLS) |
| ✅ Validación | Zod |
| 🧪 Pruebas | Vitest, PGlite para SQL y migraciones, y Playwright para E2E |
| ☁️ Hosting | Vercel |
| 🖼️ Compartir | Next.js OG para generar imágenes |

## 🔐 Ingeniería y operación

- Reglas críticas en base de datos y controles de acceso por rol, no solo en la interfaz.
- Auditoría de cambios oficiales.
- Diseño adaptable a móvil y escritorio.
- Pruebas automatizadas y verificaciones sobre el entorno publicado.
- Despliegues de mejoras iterativas a partir del uso real del club.

<details>
<summary><strong>🔎 ¿Qué demuestra este proyecto?</strong></summary>

Un producto completo que combina identidad visual, desarrollo web, reglas de negocio, autenticación, seguridad de datos, gestión de pagos, experiencia móvil y mantenimiento en producción.

</details>

> 🔒 La app es privada: la existencia de una URL pública no implica que sus datos y cuentas estén disponibles. No se muestran fichas, votos ni datos personales de jugadores.

[⬅️ Volver al portafolio](../README.md#-proyectos-destacados)

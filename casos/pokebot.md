# ⚡ Pokebot Perú — Alertas de stock para Pokémon TCG en Discord

![Estado](https://img.shields.io/badge/Estado-monitor%20operativo-16804A?style=for-the-badge)
![Comunidad](https://img.shields.io/badge/Plataforma-Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)
![Python](https://img.shields.io/badge/Stack-Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

**Rol:** desarrollo del sistema de monitoreo, detección de cambios y envío de alertas a Discord.  
**Producto:** bot para una comunidad de compradores y coleccionistas de cartas **Pokémon TCG**.

## 🎯 El problema

Las reposiciones de productos Pokémon TCG pueden aparecer en tiendas en distintos momentos y agotarse rápidamente. Revisar manualmente cada página consume tiempo y dificulta detectar nuevas publicaciones, preventas o cambios de disponibilidad.

## 🚀 La solución

Desarrollé un **monitor automatizado con alertas a Discord**, orientado a detectar cambios de inventario y catálogo en diferentes tiendas que atienden a compradores de Lima y Perú.

### 🔔 Capacidades

- 🛒 **Seguimiento de tiendas:** lectura periódica de catálogos, fichas y fuentes públicas según la tienda.
- ⚡ **Alertas oportunas:** notificación en Discord de publicaciones nuevas, reposiciones, preventas y cambios de precio detectados.
- 🔗 **Acceso a la ficha:** mensajes con nombre de producto, tienda, precio y enlace directo; botones de consulta cuando la fuente lo permite.
- 🧠 **Detección de cambios:** compara observaciones con estados anteriores para minimizar avisos duplicados.
- 📚 **Historial:** seguimiento de productos y variaciones observadas con almacenamiento en SQLite.
- 👥 **Comunidad:** organización de roles, canales y funciones adicionales para miembros.

## 🧱 Tecnología y arquitectura

| Componente | Implementación |
|---|---|
| 🐍 Motor | Python |
| 🌐 Fuentes | APIs y páginas públicas de comercios; integraciones específicas por plataforma |
| 🧭 Navegador | Playwright para fuentes que requieren lectura del navegador |
| 🧵 Monitoreo | Lectores independientes, colas y coordinación de estados |
| 💾 Datos | SQLite e historial de observaciones |
| 💬 Mensajería | Bot y webhooks de Discord |

### ⏱️ ¿Es en tiempo real?

El monitoreo es **continuo y de alta frecuencia**, con intervalos configurados por fuente. No es una transmisión instantánea de inventarios: la alerta depende de cuándo se consulte y confirme el cambio y de cuándo Discord reciba el mensaje. Tampoco garantiza existencias al completar la compra.

<details>
<summary><strong>🛡️ Criterios de fiabilidad</strong></summary>

- Una tienda caída o una respuesta incompleta **no equivale a un producto agotado**.
- Un stock desconocido no se convierte automáticamente en cero.
- Se registran observaciones y transiciones para investigar falsos positivos.
- Se respetan las limitaciones técnicas de las fuentes; no se describe el bot como un sistema de compra automática.

</details>

> 🔒 El repositorio operativo permanece privado. La descripción omite credenciales, servidores privados y configuraciones internas.

[⬅️ Volver al portafolio](../README.md#-proyectos-destacados)

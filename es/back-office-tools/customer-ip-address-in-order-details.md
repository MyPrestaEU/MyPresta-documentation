---
title: "Dirección IP del cliente en los detalles del pedido - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Dirección IP del cliente en los detalles del pedido' de MyPresta.eu."
sidebar:
  label: "Dirección IP del cliente en los detalles del pedido"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Customer IP address in order details en MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-ip-address-in-order-details.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/customer-ip-address-in-order-details/)
>
> ---


# Dirección IP del cliente en los detalles del pedido

## 1. Requisitos y Compatibilidad
- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes, ya que este módulo tiene dependencias externas mínimas.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)
Este módulo está diseñado para ser extremadamente simple y efectivo, sin requerir una configuración compleja. Después de la instalación, encontrará una pantalla de configuración básica.

-   **Nombre de la Pantalla y Ubicación del Menú:** Back Office > Módulos > Gestor de módulos > "Dirección IP del cliente en los detalles del pedido" > Configurar

En esta pantalla, normalmente verá:

-   **Qué hace esta configuración:** Este módulo generalmente no tiene configuraciones específicas más allá de su instalación inicial. Su funcionalidad principal (mostrar la dirección IP) está activa por defecto una vez instalado. La página de configuración podría simplemente confirmar que el módulo está activo o proporcionar información básica.
-   **Efecto de cambiar esta configuración:** Dado que no hay configuraciones específicas que cambiar, el comportamiento del módulo permanece consistente: mostrará la dirección IP del cliente en la página de detalles del pedido.
-   **Valor recomendado:** N/A (No hay opciones configurables).
-   **Escenario / ejemplo para el comerciante:** Simplemente instale y habilite el módulo. Cuando vea cualquier pedido en su back office, ahora verá la dirección IP del cliente mostrada de forma destacada dentro de los detalles del pedido.

### 2.2 Tabla de Referencia Rápida de Configuración
| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Página de Configuración del Módulo | *(Sin ajustes específicos)* | N/A | El módulo muestra automáticamente las direcciones IP de los clientes en las páginas de detalles del pedido una vez instalado y habilitado. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: He instalado el módulo, pero no veo la dirección IP en la página de detalles del pedido. ¿Qué debo hacer?**
R:
1.  **Verificar el Estado del Módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Dirección IP del cliente en los detalles del pedido" esté instalado y habilitado.
2.  **Borrar Caché:** A veces, la caché de PrestaShop puede impedir que los cambios aparezcan inmediatamente. Vaya a **Parámetros avanzados > Rendimiento**, desplácese hacia abajo y haga clic en "Borrar la caché".
3.  **Verificar la Página de Pedido:** Navegue a un pedido existente (o realice un pedido de prueba) en **Pedidos > Pedidos** y haga clic para ver sus detalles. La dirección IP debería aparecer en un bloque o sección dedicada.
4.  **Compatibilidad del Tema:** Aunque es poco probable para un módulo simple como este, los temas muy personalizados podrían ocasionalmente interferir con los hooks. Si el problema persiste, cambie temporalmente al tema predeterminado de PrestaShop (Classic) para ver si aparece la dirección IP.

**P: ¿Este módulo almacena las direcciones IP de los clientes en mi base de datos?**
R: PrestaShop en sí mismo suele almacenar la dirección IP del cliente cuando se registra o realiza un pedido. Este módulo simplemente recupera y muestra esa información existente de su base de datos en la página de detalles del pedido. No crea nuevas tablas de base de datos ni almacena datos IP adicionales de forma independiente.

**P: ¿Este módulo ralentizará mi tienda?**
R: No. Este módulo es muy ligero. Solo añade una pequeña pieza de información a una página existente del back office (detalles del pedido) y no realiza cálculos complejos ni operaciones de front office que puedan afectar la velocidad de navegación del cliente.

**P: ¿La dirección IP es siempre precisa?**
R: La dirección IP registrada es generalmente aquella desde la cual el cliente se conectó a su tienda. Sin embargo, los clientes que utilizan VPN, servidores proxy o ciertas redes móviles podrían tener una dirección IP que no refleje directamente su ubicación física. Es un indicador útil, pero no siempre un punto geográfico definitivo.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)
Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Visión General de la Arquitectura
El módulo "Dirección IP del cliente en los detalles del pedido" (`iporder`) es un módulo de PrestaShop muy simple diseñado para extender la funcionalidad del controlador `AdminOrders`. Aprovecha un hook estándar de PrestaShop (`displayAdminOrder`) para inyectar información adicional (la dirección IP del cliente) directamente en la página de detalles del pedido del back office. Sigue un enfoque minimalista, centrándose únicamente en mostrar datos existentes en lugar de introducir nuevos modelos de datos o lógica compleja.

### 4.2 Controladores (`controllers/`)
Este módulo no introduce ningún controlador personalizado de Front-Office o Back-Office. Su funcionalidad está completamente integrada a través de hooks dentro de los controladores existentes de PrestaShop.

### 4.3 Clases y Modelos Principales (`classes/`)
Este módulo no define ninguna clase personalizada ni extiende `ObjectModel`. Opera accediendo directamente a los objetos principales existentes de PrestaShop y sus propiedades (por ejemplo, `Order`, `Customer`).

### 4.4 Activos JavaScript (`views/js/`)
Este módulo no incluye ningún archivo JavaScript personalizado. La visualización de la dirección IP es HTML renderizado puramente del lado del servidor.

### 4.5 Hojas de Estilo CSS (`views/css/`)
Este módulo no incluye ningún archivo CSS personalizado. El contenido inyectado heredará el estilo del tema del back office de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)
Toda la lógica de visualización del módulo reside en un único archivo de plantilla Smarty.

-   **Plantillas de hook (`views/templates/hook/`)**:
    *   `iporder/views/templates/hook/displayAdminOrder.tpl`
        *   **Hook:** `displayAdminOrder`
        *   **Propósito:** Esta plantilla se renderiza en la página de detalles del pedido del back office de PrestaShop. Recupera la dirección IP del cliente asociada con el pedido actual y la muestra en un bloque dedicado.
        *   **Contenido:** Normalmente accede a las variables Smarty `$order` y `$customer` (pasadas por el hook `displayAdminOrder`) para obtener `{$customer->ip_registration_date}` o similar, y la formatea para su visualización. También podría usar `$_SERVER['REMOTE_ADDR']` si la IP no se almacena directamente con el objeto de cliente o pedido de una manera fácilmente accesible a través del hook. Dada la descripción del módulo, es probable que acceda a la dirección IP almacenada con el objeto de cliente o pedido.

### 4.7 Esquema de Base de Datos y Mapa de Hooks
-   **Tablas de Base de Datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Se basa en las tablas existentes de PrestaShop, específicamente `ps_customer` (que almacena `last_passwd_gen` e `ip_registration_date` en algunas versiones, aunque `ip_registration_date` no es estrictamente la IP del pedido) y potencialmente `ps_orders` si la IP se almacena directamente con el pedido. El enfoque más común para este módulo sería recuperar la IP de `$_SERVER['REMOTE_ADDR']` en el momento de la realización del pedido y almacenarla en un campo personalizado si no está ya presente, o simplemente mostrar la `ip_registration_date` del objeto de cliente. Sin embargo, dada la simplicidad del módulo y la falta de clases personalizadas, es muy probable que esté obteniendo la IP asociada con el registro del cliente o la `REMOTE_ADDR` en el momento del procesamiento del pedido si está disponible a través del contexto del hook.
    *   **Nota:** PrestaShop 1.7+ almacena la `current_ip_address` en la tabla `ps_connections`, vinculada a `ps_guest` y `ps_customer`. La `ip_registration_date` en `ps_customer` es la IP desde la que se registró el cliente. El objetivo del módulo es mostrar la IP *en el momento del pedido*. Esto generalmente significa:
        1.  Acceder a `$_SERVER['REMOTE_ADDR']` si el hook lo proporciona en el contexto del pedido.
        2.  Recuperar la IP de la tabla `ps_connections` basándose en el `id_guest` asociado con el pedido.
        3.  Recuperar la `ip_registration_date` de `ps_customer` (menos precisa para el pedido específico).
        Dada la simplicidad, es probable que utilice el método más directo disponible a través del hook.

-   **Tabla de Hooks Registrados**:
    | Nombre del Hook | Momento de Ejecución | Propósito Técnico |
    |---|---|---|
    | `displayAdminOrder` | Se ejecuta cuando se renderiza la página de detalles del pedido del back office de PrestaShop. | Inyecta la dirección IP del cliente en la vista de detalles del pedido. |

## 5. Soporte Oficial y Actualizaciones
Para actualizaciones oficiales, soporte técnico y cualquier otra consulta relacionada con el módulo "Dirección IP del cliente en los detalles del pedido", consulte su cuenta de cliente de MyPresta.eu. Puede acceder a sus descargas y tickets de soporte directamente desde [Historial de Pedidos y Descargas de MyPresta.eu](https://mypresta.eu/my-account/orders/).

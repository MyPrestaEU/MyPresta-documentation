---
title: "Stylight - píxel de seguimiento de ventas - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Stylight - píxel de seguimiento de ventas' de MyPresta.eu."
sidebar:
  label: "Stylight - píxel de seguimiento de ventas"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Stylight - sales tracking pixel en MyPresta.eu](https://mypresta.eu/modules/ordering-process/stylight-sales-tracking-pixel.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/stylight-sales-tracking-pixel/)
>
> ---


# Stylight - píxel de seguimiento de ventas

## 1. Requisitos y compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL) típicamente disponibles en la mayoría de los entornos de alojamiento compatibles con PrestaShop.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
El módulo "Stylight - píxel de seguimiento de ventas" está diseñado para ser extremadamente sencillo de configurar, no requiriendo ajustes específicos por parte del comerciante. Su funcionalidad es principalmente autónoma, detectando y transmitiendo automáticamente los datos de pedido necesarios.

Al navegar a la página de configuración del módulo (Back Office > Módulos > Gestor de módulos > Stylight - píxel de seguimiento de ventas > Configurar), normalmente encontrará un mensaje de confirmación que indica que el módulo está instalado y activo.

-   **Qué hace esta pantalla:** Esta página sirve como confirmación de que el módulo está correctamente instalado y listo para rastrear ventas. No hay campos de entrada o interruptores que usted deba ajustar. El módulo se conecta automáticamente al proceso de confirmación de pedido y recopila todos los datos requeridos (importe total, moneda, recuento de artículos, números SKU, ID de pedido) directamente de los detalles del pedido de PrestaShop.
-   **Efecto de cambiar esta configuración:** Dado que no hay configuraciones ajustables, no hay nada que cambiar. El módulo funciona de inmediato una vez instalado.
-   **Valor recomendado:** No se requiere ninguna acción.
-   **Escenario / ejemplo del comerciante:** Después de instalar el módulo, simplemente visita esta página para confirmar su presencia. No necesita introducir ningún ID o clave específica de Stylight, ya que el píxel en sí es genérico y está diseñado para funcionar con el sistema de Stylight enviando datos estándar de comercio electrónico.

### 2.2 Tabla de referencia rápida de configuración
| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Página de configuración del módulo | *(Sin ajustes configurables por el usuario)* | N/A | El módulo rastrea automáticamente los datos de ventas (importe total, moneda, recuento de artículos, SKUs, ID de pedido) en la página de confirmación de pedido para Stylight.com. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He instalado el módulo, pero no veo ninguna venta reportada en mi cuenta de Stylight. ¿Qué debo hacer?**
R: Primero, asegúrese de que el módulo esté habilitado en su Back Office de PrestaShop. Luego, intente borrar la caché de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché). Si el problema persiste, realice un pedido de prueba usted mismo. Si aún no hay datos, póngase en contacto con el soporte de MyPresta.eu con los detalles de su versión de PrestaShop y cualquier otro módulo instalado recientemente.

**P: ¿Este módulo ralentiza mi página de confirmación de pedido?**
R: El píxel de seguimiento es muy ligero y se carga de forma asíncrona, lo que significa que generalmente no afecta significativamente los tiempos de carga de la página ni la experiencia del cliente. Su efecto en el rendimiento es mínimo.

**P: ¿Necesito introducir algún ID de Stylight o clave API en el módulo?**
R: No, este módulo está diseñado para funcionar de inmediato. Implementa un píxel de seguimiento estándar de Stylight que envía automáticamente los datos de pedido necesarios sin requerir IDs específicos introducidos por el comerciante dentro de la propia configuración del módulo. Su cuenta de Stylight está vinculada a su dominio, y su sistema identifica su tienda basándose en el origen del píxel.

**P: ¿Este módulo es compatible con temas personalizados?**
R: Sí, el módulo se conecta a un hook estándar de PrestaShop (`displayOrderConfirmation`) que normalmente está presente en todos los temas bien codificados. No depende de elementos específicos del tema, por lo que debería funcionar sin problemas con la mayoría de los temas personalizados.

**P: Tengo varios idiomas/monedas. ¿El módulo los rastrea correctamente?**
R: Sí, el módulo está diseñado para capturar automáticamente el importe total y la moneda del pedido tal como los procesa PrestaShop, asegurando un seguimiento preciso para tiendas multi-moneda y multi-idioma.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura
El módulo "Stylight - píxel de seguimiento de ventas" es un módulo de PrestaShop sencillo centrado principalmente en el enganche de eventos del front-office. Aprovecha el hook `displayOrderConfirmation` para inyectar un píxel de seguimiento basado en JavaScript en la página final de confirmación de pedido. La lógica del módulo está contenida en su archivo PHP principal, `index.php`, que gestiona la instalación, desinstalación y el registro del hook. La recopilación de datos es dinámica, extrayendo los detalles del pedido directamente de los objetos `Order` y `Product` disponibles en el contexto de la página de confirmación del pedido.

### 4.2 Controladores (`controllers/`)
-   **Controladores de Front-Office**: Ninguno. La funcionalidad de front-office del módulo se gestiona completamente mediante el enganche a `displayOrderConfirmation` y la renderización de una plantilla Smarty.
-   **Controladores de administración de Back-Office**: Ninguno. El módulo no tiene una interfaz de administración dedicada más allá de la página de configuración estándar del módulo (`getContent()`).

### 4.3 Clases y modelos principales (`classes/`)
-   Ninguno. El módulo no define ninguna clase personalizada ni extiende `ObjectModel`. Toda la lógica reside dentro del archivo principal `stylightpixel/index.php`.

### 4.4 Activos de JavaScript (`views/js/`)
-   Ninguno. El código del píxel de seguimiento está incrustado directamente dentro de la plantilla Smarty (`displayOrderConfirmation.tpl`) para asegurar que se active inmediatamente al cargar la página.

### 4.5 Hojas de estilo CSS (`views/css/`)
-   Ninguno. El módulo es puramente funcional y no tiene componentes visuales ni requisitos de estilo.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)
-   **Plantillas de hook (`views/templates/hook/`)**:
    *   `stylightpixel/views/templates/hook/displayOrderConfirmation.tpl`
        *   **Hook**: `displayOrderConfirmation`
        *   **Propósito**: Esta plantilla se renderiza en la página de confirmación del pedido después de una compra exitosa. Contiene el código JavaScript para el píxel de seguimiento de Stylight.
        *   **Datos disponibles**: La plantilla recibe `$order` (un objeto `Order`) y `$products` (un array de objetos `Product` asociados con el pedido) del método `hookDisplayOrderConfirmation`.
        *   **Salida**: Genera un bloque `<script>` que construye la URL del píxel de seguimiento de Stylight con parámetros dinámicos como `order_id`, `total_amount`, `currency`, `item_count` y `sku` para cada producto.

### 4.7 Esquema de la base de datos y mapa de hooks
-   **Tablas de la base de datos**: El módulo no crea ninguna tabla de base de datos personalizada. Se basa en las tablas estándar de PrestaShop (`ps_orders`, `ps_order_detail`, `ps_product`, etc.) para recuperar la información del pedido.
-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
|---|---|---|
| `displayOrderConfirmation` | Se ejecuta en la página final de confirmación del pedido después de una compra exitosa. | Inyecta el JavaScript del píxel de seguimiento de Stylight en la página para enviar datos de conversión (ID del pedido, total, moneda, SKUs del producto, recuento de artículos) a Stylight. |

## 5. Soporte oficial y actualizaciones
Para actualizaciones oficiales, soporte técnico y cualquier otra asistencia con el módulo "Stylight - píxel de seguimiento de ventas", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con consultas relacionadas con el módulo y asegurar que su píxel de seguimiento funcione correctamente.

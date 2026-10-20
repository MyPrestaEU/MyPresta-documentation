---
title: "Recibir notificación sobre reseñas de productos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Recibir notificación sobre reseñas de productos' de MyPresta.eu."
sidebar:
  label: "Recibir notificación sobre reseñas de productos"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Get notification about product review en MyPresta.eu](https://mypresta.eu/modules/administration-tools/get-notification-about-product-review.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/get-notification-about-product-review/)
>
> ---


# Recibir notificación sobre reseñas de productos

## 1. Requisitos y compatibilidad

-   **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x
-   **Compatibilidad con PHP**: PHP 7.1 - 8.5
-   **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).
-   **Requisito previo**: Este módulo requiere que nuestro addon gratuito de reseñas de productos esté instalado y activo. Extiende la funcionalidad de ese módulo.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Después de la instalación, al hacer clic en "Configurar" accederá a la pantalla principal y única de configuración de este módulo. Esta pantalla le permite definir a qué dirección de correo electrónico se enviarán las notificaciones.

#### **Dirección de correo electrónico para enviar notificaciones**
-   **Qué hace esta configuración:** Este es el ajuste más crucial. Determina la dirección de correo electrónico a la que se enviarán todas las notificaciones relacionadas con las reseñas.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se introduce un correo electrónico válido:* Todas las alertas (nueva reseña, comentario reportado, voto útil) se enviarán a esta dirección de correo electrónico específica.
    -   *Cuando se deja vacío o se introduce un correo electrónico no válido:* No recibirá ninguna notificación, deshabilitando efectivamente la función principal del módulo.
-   **Valor recomendado:** Su dirección de correo electrónico comercial principal, o una dirección de correo electrónico monitoreada regularmente por su equipo de atención al cliente o marketing.
-   **Escenario / ejemplo del comerciante:** Si su equipo de atención al cliente maneja todas las interacciones con los clientes, podría introducir `clientes@sutienda.com` aquí. Si usted, como propietario, desea ser informado personalmente, use su dirección de correo electrónico directa.

#### **Tabla de referencia rápida de configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Configuración del módulo | Dirección de correo electrónico para enviar notificaciones | Su correo electrónico comercial principal | Especifica el destinatario del correo electrónico para todas las alertas relacionadas con las reseñas (nueva reseña, comentario reportado, voto útil). |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: No recibo ninguna notificación por correo electrónico. ¿Qué debo hacer?**
R:
1.  **Verifique la dirección de correo electrónico:** Vaya a **Módulos > Gestor de módulos > Configurar** para "Recibir notificación sobre reseñas de productos" y asegúrese de que la dirección de correo electrónico introducida sea correcta y no contenga errores tipográficos.
2.  **Revise su carpeta de spam:** Las notificaciones a veces pueden filtrarse a su carpeta de spam o correo no deseado. Añada la dirección de correo electrónico del remitente (normalmente el correo electrónico predeterminado de su tienda) a su lista de remitentes seguros.
3.  **Verifique la configuración de correo electrónico de PrestaShop:** Asegúrese de que la configuración de correo electrónico de su tienda PrestaShop esté configurada correctamente y que se envíen correos electrónicos en general. Puede probar esto creando una nueva cuenta de cliente o realizando un pedido de prueba. Vaya a **Parámetros avanzados > E-mail** en su back office.
4.  **Contacte a su proveedor de alojamiento:** Si los correos electrónicos de PrestaShop no funcionan en absoluto, podría haber un problema con la función de correo de su servidor. Su proveedor de alojamiento puede ayudar a diagnosticar esto.
5.  **Asegúrese de que el módulo prerrequisito esté instalado:** Este módulo extiende nuestro addon gratuito de reseñas de productos. Asegúrese de que ese módulo esté instalado y funcionando correctamente.

**P: ¿Puedo enviar notificaciones a varias direcciones de correo electrónico?**
R: El diseño actual del módulo permite configurar solo una dirección de correo electrónico. Si necesita enviar a varios destinatarios, puede configurar una regla de reenvío de correo electrónico en su cliente de correo electrónico o servidor (por ejemplo, reenviar correos electrónicos de la dirección configurada a un alias de grupo).

**P: ¿Este módulo funciona con cualquier sistema de reseñas de productos?**
R: No, este módulo está diseñado específicamente para funcionar como una extensión del **addon gratuito de reseñas de productos de MyPresta.eu**. No proporcionará notificaciones para otros módulos de reseñas de terceros.

**P: He actualizado mi tema de PrestaShop y ahora las notificaciones no funcionan.**
R: Este módulo no tiene componentes de front-office, por lo que un cambio de tema no debería afectar directamente su funcionalidad de notificación. Vuelva a verificar la configuración de correo electrónico en el módulo y la configuración de correo electrónico de PrestaShop como se describió anteriormente. Si el problema persiste, es probable que no esté relacionado con el tema y apunte a un problema de correo electrónico del servidor o del núcleo de PrestaShop.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura
El módulo "Recibir notificación sobre reseñas de productos" (`reviewsalerts`) es un módulo ligero de PrestaShop diseñado para extender la funcionalidad del módulo principal `productcomments` (o un módulo de reseñas similar, específicamente el addon gratuito de reseñas de productos de MyPresta.eu). Opera principalmente enganchándose a las acciones relevantes activadas por el sistema de reseñas y enviando notificaciones por correo electrónico basadas en estos eventos. Sigue un patrón simple basado en eventos, aprovechando el sistema de hooks de PrestaShop sin introducir estructuras MVC complejas o tablas de base de datos personalizadas.

### 4.2 Controladores (`controllers/`)
Este módulo no contiene ningún controlador personalizado de front-office o back-office. Toda la lógica está encapsulada dentro del archivo principal del módulo y se ejecuta a través de hooks.

### 4.3 Clases y modelos principales (`classes/`)
Este módulo no define ninguna clase personalizada o instancias de `ObjectModel`. Su funcionalidad está contenida dentro de la clase principal `reviewsalerts`.

### 4.4 Activos de JavaScript (`views/js/`)
Este módulo no incluye ningún archivo JavaScript.

### 4.5 Hojas de estilo CSS (`views/css/`)
Este módulo no incluye ningún archivo CSS.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)
Este módulo no incluye ningún archivo de plantilla Smarty personalizado para la visualización en el front-office o la configuración en el back-office. El formulario de configuración se genera dinámicamente mediante `getContent()` en el archivo principal del módulo.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Almacena su única configuración (la dirección de correo electrónico de notificación) en la tabla estándar `ps_configuration`.
    *   **Clave de configuración**: `REVIEWSALERTS_EMAIL`

-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| :-------- | :--------------- | :---------------- |
| `actionObjectProductCommentAddAfter` | Después de que una nueva reseña de producto (comentario) se haya añadido correctamente a la base de datos. | Activa una notificación por correo electrónico a la dirección configurada, informando al comerciante sobre la nueva reseña. |
| `actionObjectProductCommentReportAfter` | Después de que un cliente haya reportado correctamente una reseña de producto. | Activa una notificación por correo electrónico a la dirección configurada, informando al comerciante de que se ha reportado una reseña. |
| `actionObjectProductCommentUsefulAfter` | Después de que un cliente marca una reseña de producto como "útil". | Activa una notificación por correo electrónico a la dirección configurada, informando al comerciante de que se ha votado la utilidad de una reseña. |

El método `install()` del módulo registra estos hooks, y los métodos correspondientes `hookActionObjectProductCommentAddAfter()`, `hookActionObjectProductCommentReportAfter()` y `hookActionObjectProductCommentUsefulAfter()` manejan la lógica de envío de correo electrónico.

El envío de correo electrónico se maneja típicamente mediante la función `Mail::Send()` de PrestaShop, utilizando las plantillas y configuraciones de correo electrónico configuradas de la tienda. El módulo probablemente construiría el contenido del correo electrónico dinámicamente basándose en el contexto de la acción activada (por ejemplo, contenido de la reseña, nombre del producto, detalles del informante).

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Recibir notificación sobre reseñas de productos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y configuración del módulo.

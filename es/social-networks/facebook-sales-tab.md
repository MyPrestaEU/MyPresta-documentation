---
title: "Pestaña de Ventas de Facebook - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Pestaña de Ventas de Facebook de MyPresta.eu."
sidebar:
  label: "Pestaña de Ventas de Facebook - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook Sales Tab en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-sales-tab.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-sales-tab/)
>
> ---


# Pestaña de Ventas de Facebook

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).
- **Requisitos Externos**: Una Fanpage de Facebook (Página de Negocio) activa donde seas administrador. También necesitarás crear una Aplicación de Facebook para vincular tu tienda con tu Fanpage, lo que implica obtener un ID de Aplicación y un Secreto de Aplicación del portal de Desarrolladores de Facebook.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Pestaña de Ventas de Facebook)

Esta es la pantalla de configuración principal y única para el módulo Pestaña de Ventas de Facebook. Aquí vincularás tu tienda PrestaShop a tu Fanpage de Facebook y definirás qué contenido se muestra.

Para acceder a esta página, ve a **Back Office > Módulos > Gestor de Módulos**, busca "Pestaña de Ventas de Facebook" y haz clic en "Configurar".

#### **Configuración de la Aplicación de Facebook**

Estos ajustes son cruciales para establecer la conexión entre tu tienda PrestaShop y tu Fanpage de Facebook. Necesitarás crear una Aplicación de Facebook a través del portal de Desarrolladores de Facebook para obtener estas credenciales.

-   **ID de la Aplicación de Facebook:**

    -   **Qué hace este ajuste:** Este es un identificador único para tu Aplicación de Facebook. Le dice a Facebook qué aplicación está intentando conectarse a tu Fanpage.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce correctamente:* Permite que tu módulo se comunique con Facebook y muestre la pestaña de ventas.
        -   *Cuando es incorrecto o está vacío:* El módulo no podrá conectarse a Facebook, y la pestaña de ventas no funcionará ni aparecerá en tu Fanpage.
    -   **Valor recomendado:** El ID de la Aplicación exacto proporcionado por Facebook cuando creas tu aplicación.
    -   **Escenario / ejemplo de comerciante:** Has creado una Aplicación de Facebook llamada "Pestaña de Ventas de MiTienda" en developers.facebook.com, y Facebook le asignó un ID de Aplicación como `123456789012345`. Introducirías este número aquí.
-   **Secreto de la Aplicación de Facebook:**

    -   **Qué hace este ajuste:** Esta es una clave secreta asociada con tu Aplicación de Facebook, utilizada para autenticar las solicitudes de tu aplicación a Facebook. Debe mantenerse confidencial.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce correctamente:* Asegura una comunicación segura entre tu tienda y Facebook.
        -   *Cuando es incorrecto o está vacío:* Facebook rechazará los intentos de conexión, y la pestaña de ventas no funcionará.
    -   **Valor recomendado:** El Secreto de la Aplicación exacto proporcionado por Facebook cuando creas tu aplicación.
    -   **Escenario / ejemplo de comerciante:** Junto con tu ID de Aplicación, Facebook proporciona un Secreto de Aplicación (por ejemplo, `abcdef1234567890abcdef1234567890`). Introduces esta cadena aquí.
-   **ID de la Página de Facebook:**

    -   **Qué hace este ajuste:** Este es el identificador único de tu Fanpage de Facebook específica donde quieres que aparezca la pestaña de ventas.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce correctamente:* El módulo sabe a qué Fanpage dirigirse para añadir la pestaña de ventas.
        -   *Cuando es incorrecto o está vacío:* La pestaña de ventas no se añadirá a tu Fanpage deseada, o podría añadirse a la incorrecta si se introduce un ID erróneo.
    -   **Valor recomendado:** El ID de la Página exacto de tu Fanpage de Facebook. Normalmente puedes encontrarlo en la sección "Información" de tu Fanpage o utilizando una herramienta de búsqueda de ID de Página de Facebook.
    -   **Escenario / ejemplo de comerciante:** La Fanpage de Facebook de tu tienda es "Mi Tienda Impresionante". Encuentras su ID de Página (por ejemplo, `987654321098765`) y lo introduces aquí.

#### **Configuración del Contenido de la Pestaña de Ventas**

Estos ajustes controlan qué productos o promociones se muestran en tu Pestaña de Ventas de Facebook.

-   **Número de Productos a Mostrar:**

    -   **Qué hace este ajuste:** Determina cuántos productos de tu selección de ventas especiales se mostrarán en la pestaña de Facebook.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece un número mayor (por ejemplo, 20):* Más productos serán visibles, dando a los clientes una selección más amplia.
        -   *Cuando se establece un número menor (por ejemplo, 5):* Se mostrarán menos productos, lo que podría centrar la atención en tus mejores ofertas.
    -   **Valor recomendado:** 10-20, dependiendo de cuántas ventas activas tengas normalmente y cuánto contenido quieras presentar.
    -   **Escenario / ejemplo de comerciante:** Tienes 15 productos en oferta. Establecer esto en "15" asegura que todos ellos se muestren en tu pestaña de Facebook. Si solo quieres destacar los 5 mejores, lo establecerías en "5".
-   **Mostrar Productos de Categorías Específicas:**

    -   **Qué hace este ajuste:** Te permite filtrar los productos mostrados en la pestaña de Facebook para incluir solo aquellos de categorías seleccionadas en tu tienda PrestaShop.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan categorías específicas:* Solo los productos que pertenecen a esas categorías aparecerán en la pestaña de Facebook, incluso si otros productos están en oferta.
        -   *Cuando no se seleccionan categorías (o se seleccionan todas):* Se mostrarán todos los productos que cumplan con los criterios de "ventas".
    -   **Valor recomendado:** Selecciona categorías relevantes para tus promociones actuales o artículos más vendidos que quieras destacar en Facebook.
    -   **Escenario / ejemplo de comerciante:** Estás realizando una promoción especial en "Vestidos de Verano" y "Accesorios de Playa". Seleccionarías estas dos categorías para asegurar que solo esos productos aparezcan en tu Pestaña de Ventas de Facebook.
-   **Mostrar Productos con Descuentos/Ofertas Específicas:**

    -   **Qué hace este ajuste:** Este es el filtro principal para lo que constituye un producto "en oferta". Puedes elegir mostrar productos que tienen una reducción de precio específica.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado y configurado:* Solo se mostrarán los productos con precios especiales activos o descuentos porcentuales.
        -   *Cuando está deshabilitado:* El módulo podría mostrar productos regulares o productos basados en otros criterios (aunque el propósito principal del módulo es "ventas").
    -   **Valor recomendado:** SÍ, y asegúrate de que tus productos tengan precios especiales activos configurados en PrestaShop.
    -   **Escenario / ejemplo de comerciante:** Has configurado un 10% de descuento en todos los "Abrigos de Invierno" en la configuración de productos de tu PrestaShop. Este ajuste asegura que esos abrigos con descuento sean los que aparecen en tu pestaña de Facebook.

#### **Configuración General de Visualización**

-   **Título de la Pestaña en Facebook:**

    -   **Qué hace este ajuste:** Este es el texto que aparecerá como el nombre de la pestaña en tu Fanpage de Facebook.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Ofertas Especiales":* Tu pestaña se etiquetará como "Ofertas Especiales" en Facebook.
        -   *Cuando se establece en "Comprar Ahora":* Tu pestaña se etiquetará como "Comprar Ahora".
    -   **Valor recomendado:** Algo claro y atractivo como "Ofertas Especiales", "Comprar Ahora" o "Nuestras Ofertas".
    -   **Escenario / ejemplo de comerciante:** Quieres indicar claramente que esta pestaña es para promociones, así que estableces el título en "¡Ventas Flash!".
-   **Icono de la Pestaña:**

    -   **Qué hace este ajuste:** Te permite subir un icono personalizado que aparecerá junto al título de tu pestaña en Facebook. Esto ayuda a que tu pestaña se destaque.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se sube un icono:* Tu pestaña tendrá un identificador visual personalizado.
        -   *Cuando no se sube ningún icono:* Facebook usará un icono predeterminado, o la pestaña podría aparecer sin un icono específico.
    -   **Valor recomendado:** Un icono pequeño, claro y relevante (por ejemplo, un carrito de compras, una estrella, un signo de porcentaje) que coincida con tu marca.
    -   **Escenario / ejemplo de comerciante:** Subes una pequeña imagen de un carrito de compras para hacer que tu pestaña "Comprar Ahora" sea visualmente atractiva y fácil de detectar.

#### **Tabla de Referencia Rápida de Configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | ID de la Aplicación de Facebook | Tu ID de la Aplicación de Facebook | Vincula tu tienda a tu Aplicación de Facebook para la autenticación. |
| Configuración del Módulo | Secreto de la Aplicación de Facebook | Tu Secreto de la Aplicación de Facebook | Autentica de forma segura tu aplicación con Facebook. |
| Configuración del Módulo | ID de la Página de Facebook | Tu ID de la Fanpage de Facebook | Especifica a qué Fanpage se añadirá la pestaña de ventas. |
| Configuración del Módulo | Número de Productos a Mostrar | 10-20 | Controla cuántos productos en oferta se muestran en la pestaña. |
| Configuración del Módulo | Mostrar Productos de Categorías Específicas | Seleccionar categorías relevantes | Filtra productos por categoría para su visualización en la pestaña. |
| Configuración del Módulo | Mostrar Productos con Descuentos/Ofertas Específicas | SÍ | Asegura que solo se muestren productos con descuento en la pestaña. |
| Configuración del Módulo | Título de la Pestaña en Facebook | "Ofertas Especiales" / "Comprar Ahora" | Establece el nombre visible de la pestaña en tu Fanpage de Facebook. |
| Configuración del Módulo | Icono de la Pestaña | Subir un icono relevante | Proporciona un icono visual personalizado para tu pestaña de Facebook. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mi Pestaña de Ventas de Facebook no aparece en mi Fanpage. ¿Qué debo hacer?**
R1:

-   **Verifica el ID de la Aplicación, el Secreto de la Aplicación y el ID de la Página:** Vuelve a verificar que los tres valores estén introducidos correctamente en la configuración del módulo. Incluso un solo error tipográfico impedirá la conexión.
-   **Estado de la Aplicación de Facebook:** Asegúrate de que tu Aplicación de Facebook esté activa y disponible públicamente (no en modo de desarrollo). Puedes verificar esto en tu panel de desarrolladores de Facebook.
-   **Permisos:** Asegúrate de que tu Aplicación de Facebook tenga los permisos necesarios para administrar páginas.
-   **Caché:** Borra la caché de Smarty de tu PrestaShop (Parámetros Avanzados > Rendimiento) y la caché de tu navegador. A veces, los cambios tardan un momento en propagarse.
-   **Administrador de la Página de Facebook:** Asegúrate de que la cuenta de Facebook que estás utilizando para administrar la Fanpage tenga derechos de administrador tanto para la Fanpage como para la Aplicación de Facebook.

**P2: Los productos que se muestran en la pestaña de Facebook no son los que espero.**
R2:

-   **Configuración "Mostrar Productos con Descuentos/Ofertas Específicas":** Asegúrate de que esté habilitada si solo quieres mostrar artículos con descuento.
-   **Descuentos de Productos:** Verifica que los productos que *esperas* ver realmente tengan precios especiales activos o descuentos porcentuales configurados en la configuración de productos de tu PrestaShop.
-   **Configuración "Mostrar Productos de Categorías Específicas":** Si has seleccionado categorías específicas, asegúrate de que los productos que quieres mostrar pertenezcan a esas categorías.
-   **"Número de Productos a Mostrar":** Si tienes muchas ofertas, pero este número es bajo, solo se mostrarán las primeras.

**P3: ¿Cómo obtengo un ID de Aplicación de Facebook, un Secreto de Aplicación y un ID de Página?**
R3:

-   **ID de Aplicación y Secreto de Aplicación de Facebook:** Ve a [developers.facebook.com](https://developers.facebook.com/), inicia sesión y crea una nueva aplicación. Sigue las instrucciones de Facebook para configurar una nueva aplicación, normalmente eligiendo un tipo "Negocio" o "Sitio web". Una vez creada, encontrarás el ID de la Aplicación y el Secreto de la Aplicación en la configuración del panel de tu aplicación.
-   **ID de la Página de Facebook:** Navega a tu Fanpage de Facebook. A menudo puedes encontrar el ID de la Página en la sección "Información" de tu página. Alternativamente, existen herramientas en línea (busca "Buscador de ID de Página de Facebook") donde puedes pegar la URL de tu Fanpage para recuperar su ID.

**Q4: El icono o el título de la pestaña no se actualizan en Facebook.**
R4:

-   **Caché de Facebook:** El propio Facebook puede almacenar en caché la información de la página. Puede que tarde algún tiempo (hasta unas pocas horas) en que los cambios en el título o el icono de la pestaña se reflejen globalmente.
-   **Guardar la Configuración del Módulo:** Asegúrate de haber guardado la configuración del módulo después de realizar los cambios.
-   **Borrar Caché:** Borra la caché de tu PrestaShop (Parámetros Avanzados > Rendimiento) y la caché de tu navegador.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo `Pestaña de Ventas de Facebook` (`prestasales`) es un módulo estándar de PrestaShop diseñado para integrarse con la Plataforma de Facebook. Su función principal es servir contenido (específicamente, una lista de productos en oferta) que puede incrustarse dentro de una pestaña de Fanpage de Facebook. El módulo aprovecha el sistema de configuración de PrestaShop para almacenar las credenciales de la API de Facebook y las preferencias de visualización. No introduce patrones MVC complejos ni tablas de base de datos personalizadas, sino que se basa en las funcionalidades principales de PrestaShop para la recuperación de productos y la gestión de la configuración. La lógica principal del módulo reside en su archivo `de.php`, que maneja la instalación, desinstalación y visualización de la configuración.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador de Front-Office o Back-Office Admin personalizado. Toda la configuración se maneja directamente dentro del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no introduce ninguna clase personalizada o definición de `ObjectModel`. Interactúa directamente con las clases principales `Product` y `Category` de PrestaShop y la clase `Configuration` para la configuración.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   **`prestasales/css/css.css`**:
    -   **Alcance:** Esta hoja de estilo está destinada a dar estilo al contenido mostrado dentro de la pestaña de Facebook.
    -   **Principales componentes de la interfaz de usuario y contenedores a los que da estilo:** Típicamente contendría estilos para listados de productos, imágenes, precios, insignias de descuento y botones de "añadir al carrito" o "ver producto" dentro de la pestaña de Facebook incrustada.
    -   **Selectores de clase CSS clave que los desarrolladores pueden sobrescribir en su tema:** Los desarrolladores deben inspeccionar la salida HTML dentro de la pestaña de Facebook para identificar nombres de clase específicos. Los selectores comunes podrían incluir `.prestasales-product-list`, `.prestasales-product-item`, `.prestasales-product-image`, `.prestasales-product-name`, `.prestasales-price`, `.prestasales-discount`, `.prestasales-button`.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

Este módulo no lista explícitamente archivos `.tpl` en el inventario proporcionado. Sin embargo, basándose en su funcionalidad, típicamente contendría:

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   Es muy probable que exista una plantilla como `views/templates/hook/displayFacebookSalesTab.tpl` (o similar) internamente dentro del archivo `de.php` del módulo o que se genere sobre la marcha. Esta plantilla sería responsable de renderizar la estructura HTML de la lista de productos que luego se sirve a Facebook.
    -   **Propósito:** Esta plantilla iteraría sobre los productos en oferta seleccionados y mostraría sus imágenes, nombres, precios y enlaces, formateados para incrustar dentro de un iframe de Facebook.
-   **Plantillas de administración (`views/templates/admin/`)**:

    -   Dado que la configuración se maneja mediante `getContent()`, se utilizaría una plantilla como `views/templates/admin/configure.tpl` o `views/templates/admin/configuration_form.tpl` para renderizar el formulario de configuración del back-office del módulo. Esta plantilla contendría los campos de entrada para el ID de la Aplicación, el Secreto de la Aplicación, el ID de la Página, las opciones de visualización de productos, etc.
-   **Plantillas de front-office (`views/templates/front/`)**:

    -   No se esperan plantillas dedicadas de front-office ya que la salida del módulo es principalmente para la plataforma de Facebook.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   Este módulo no crea ninguna tabla SQL personalizada.
    -   Todos los ajustes de configuración se almacenan en la tabla `ps_configuration` de PrestaShop utilizando claves como `PRESTASALES_APP_ID`, `PRESTASALES_APP_SECRET`, `PRESTASALES_PAGE_ID`, `PRESTASALES_NUM_PRODUCTS`, `PRESTASALES_CATEGORIES`, `PRESTASALES_DISCOUNTS_ONLY`, `PRESTASALES_TAB_TITLE`, `PRESTASALES_TAB_ICON`.
-   **Tabla de Hooks Registrados**:
    La interacción principal del módulo con el sistema de hooks de PrestaShop sería para su configuración y potencialmente para renderizar el contenido que Facebook recupera.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Aunque el módulo no muestra contenido directamente en la tienda, podría usar este hook para cargar scripts SDK de Facebook necesarios o metaetiquetas si implementara características avanzadas de integración con Facebook (por ejemplo, etiquetas Open Graph), aunque esto no se establece explícitamente para la función principal de este módulo. |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página del back-office. | Se utiliza para cargar CSS o JS específicos del módulo para la página de configuración, si los hubiera. |
| `moduleRoutes` | Durante la inicialización de la reescritura de URL. | No utilizado explícitamente por este módulo, ya que no define rutas personalizadas de front-office. |
| `actionProductUpdate` / `actionProductAdd` | Después de que un producto es actualizado o añadido. | No utilizado explícitamente, pero podría usarse para borrar la caché relacionada con los listados de productos para la pestaña de Facebook. |
| `actionModuleInstall` | Durante la instalación del módulo. | Para registrar los valores predeterminados de configuración y potencialmente configurar los pasos iniciales de integración de la Aplicación de Facebook. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Para limpiar los datos de configuración de `ps_configuration`. |

La funcionalidad principal de servir el contenido a Facebook probablemente se maneja mediante una solicitud directa al archivo PHP principal del módulo (`de.php`) o un método interno específico que renderiza la lista de productos, en lugar de un hook `display` estándar de PrestaShop. Este contenido se incrusta luego dentro de un iframe en la Fanpage de Facebook.

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y asistencia adicional con el módulo "Pestaña de Ventas de Facebook", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener.

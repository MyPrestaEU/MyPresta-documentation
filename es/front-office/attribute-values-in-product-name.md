---
title: "Valores de atributos en el nombre del producto - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Valores de atributos en el nombre del producto' de MyPresta.eu."
sidebar:
  label: "Valores de atributos en el nombre del producto - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Attribute values in product name en MyPresta.eu](https://mypresta.eu/modules/front-office-features/attribute-values-in-product-name.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/attribute-values-in-product-name/)
>
> ---


# Valores de atributos en el nombre del producto

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de instalar el módulo, haga clic en "Configurar" para acceder a sus ajustes.

#### Clase CSS del nombre del producto

-   **Qué hace este ajuste:** Este campo le permite especificar la clase CSS del elemento HTML que muestra el nombre del producto en sus páginas de producto. El módulo necesita conocer esta clase para poder identificar y modificar correctamente el elemento del nombre del producto cuando un cliente selecciona una nueva combinación de atributos.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se introduce una clase CSS correcta:* El módulo localizará con éxito el nombre del producto en la página y le añadirá dinámicamente los valores de los atributos seleccionados.
    -   *Cuando se introduce una clase CSS incorrecta o ninguna:* El módulo no podrá encontrar el elemento del nombre del producto y, por lo tanto, los valores de los atributos no se añadirán al nombre del producto. El nombre del producto permanecerá estático.
-   **Valor recomendado:** Este valor depende de su tema de PrestaShop.
    -   Para los **temas predeterminados de PrestaShop (Classic)**, una clase común para el nombre del producto es `h1.product-detail-name` o `h1[itemprop="name"]`. Es posible que necesite inspeccionar su página de producto utilizando las herramientas de desarrollo de su navegador para encontrar la clase o ID exacto de la etiqueta `<h1>` que contiene el nombre del producto.
    -   Si no está seguro, pruebe primero con `h1.product-detail-name`. Si no funciona, deberá consultar a su desarrollador de temas o utilizar las herramientas de desarrollo del navegador (haga clic con el botón derecho en el nombre del producto, seleccione "Inspeccionar") para encontrar el selector CSS correcto para el encabezado principal del nombre del producto.
-   **Escenario / ejemplo del comerciante:**
    -   Ha instalado un tema personalizado y el nombre del producto está envuelto en una etiqueta `<h2>` con la clase `my-custom-product-title`. Debería introducir `h2.my-custom-product-title` en este campo.
    -   Si su tema utiliza la estructura estándar del tema Classic de PrestaShop, introducir `h1.product-detail-name` debería funcionar perfectamente, asegurando que cuando un cliente selecciona "Azul" para una camisa, el título se actualiza de "Camiseta" a "Camiseta (Azul)".

#### Otras claves de configuración (Internas)

Puede ver otras claves de configuración como `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `mypresta_updates`, `update_`, `updatev_`. Estos son ajustes internos utilizados por PrestaShop y MyPresta.eu para gestionar las actualizaciones del módulo y las preferencias de idioma. No necesita interactuar con ellos.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Clase CSS del nombre del producto | `h1.product-detail-name` (para el tema Classic) | Especifica el selector CSS para el elemento del nombre del producto. Es esencial para que el módulo identifique y modifique el título del producto en la página del producto. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: El nombre del producto no cambia cuando selecciono atributos. ¿Qué pasa?**
R: La razón más común es una configuración incorrecta de la "Clase CSS del nombre del producto".
-   **Solución**:
    1.  Vaya a la página de su producto en su navegador.
    2.  Haga clic con el botón derecho en el nombre del producto y seleccione "Inspeccionar" (o "Inspeccionar elemento").
    3.  Busque la etiqueta `<h1>` o `<h2>` que contiene el nombre del producto. Anote su clase (por ejemplo, `class="product-detail-name"`) o ID (por ejemplo, `id="product_name"`).
    4.  Introduzca el selector CSS correcto en la configuración del módulo. Por ejemplo, si la etiqueta es `<h1 class="my-product-title">`, introduciría `h1.my-product-title`. Si es `<h2 id="product_heading">`, introduciría `h2#product_heading`.
    5.  Guarde la configuración del módulo y borre la caché de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché).

**P: El módulo funcionó inicialmente, pero después de actualizar mi tema, dejó de funcionar.**
R: Las actualizaciones de temas a menudo cambian la estructura HTML y las clases CSS.
-   **Solución**: Vuelva a verificar la configuración de la "Clase CSS del nombre del producto" como se describió anteriormente. Su nuevo tema podría usar una clase o ID diferente para el nombre del producto.

**P: ¿Este módulo afectará mi SEO?**
R: No, este módulo solo cambia el nombre del producto dinámicamente en el lado del cliente (en el navegador del cliente) usando JavaScript. No altera el nombre original del producto almacenado en su base de datos ni la etiqueta `<h1>` que los motores de búsqueda suelen indexar. Su SEO no se ve afectado.

**P: ¿Este módulo es compatible con varios idiomas?**
R: Sí, el módulo funciona con los valores de los atributos tal como están configurados en su back office de PrestaShop, que ya son compatibles con varios idiomas. El módulo simplemente añade los valores de los atributos seleccionados actualmente en el idioma activo al nombre del producto.

**P: Veo los valores de los atributos, pero están mal estilizados (por ejemplo, fuente, color incorrectos).**
R: El módulo añade texto a un elemento HTML existente. Su estilo se heredará del CSS de su tema para ese elemento del nombre del producto.
-   **Solución**: Si desea estilizar los valores de los atributos añadidos de manera diferente, necesitará CSS personalizado. Puede apuntar al elemento del nombre del producto y, potencialmente, usar pseudoelementos o selectores específicos si el módulo envuelve el texto añadido en un `span` único (aunque este módulo normalmente solo añade texto). Un desarrollador web puede ayudarle con CSS personalizado.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores, webmasters y agencias.

### 4.1 Descripción general de la arquitectura

El módulo "Valores de atributos en el nombre del producto" (`anpn`) es un módulo ligero de PrestaShop centrado principalmente en la manipulación del lado del cliente en el front-office. Aprovecha el sistema de hooks de PrestaShop para inyectar su JavaScript en el encabezado de la página del producto. La lógica central reside en un único archivo JavaScript que escucha los cambios en las selecciones de atributos del producto y actualiza dinámicamente el contenido de texto del nombre del producto. No introduce nuevas tablas de base de datos ni lógica compleja del lado del servidor más allá de su configuración.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. Toda la funcionalidad de front-office se gestiona mediante JavaScript inyectado a través de hooks.
-   **Controladores de Back-Office Admin**: Ninguno. La configuración se gestiona directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

-   No se definen clases personalizadas ni instancias de `ObjectModel`. El módulo opera directamente sobre los valores de configuración y la manipulación del DOM del front-office.

### 4.4 Activos JavaScript (`views/js/`)

-   **`anpn/views/js/anpn.js`**
    -   **Alcance**: Front-office (página de producto).
    -   **Propósito**: Este script es responsable de la actualización dinámica del nombre del producto.
    -   **Funcionalidad**:
        1.  **DOM Ready / `prestashop.on`**: Espera a que el DOM esté completamente cargado y escucha específicamente el evento `updatedProduct` activado por el JavaScript central de PrestaShop cuando se cambia una combinación de producto (por ejemplo, seleccionando una talla o color diferente).
        2.  **Identificación del nombre del producto**: Recupera el selector CSS para el nombre del producto de la configuración del módulo (pasado a través de la variable global `anpn_pn_class` o un mecanismo similar). Luego usa este selector para encontrar el elemento HTML de destino en la página.
        3.  **Extracción del valor del atributo**: Cuando se activa `updatedProduct`, accede a los datos de la combinación de producto actual (que incluyen los valores de los atributos seleccionados) desde la carga útil del evento.
        4.  **Actualización dinámica**: Construye una cadena con los valores de los atributos seleccionados (por ejemplo, "(M, Azul)") y la añade al nombre original del producto (que normalmente almacena en la carga inicial o recupera de un atributo de datos).
        5.  **Manipulación del DOM**: El script actualiza el `textContent` o `innerText` del elemento del nombre del producto identificado con la nueva cadena combinada.
    -   **Dependencias**: Se basa en jQuery (si PrestaShop 1.7.x) o en las API nativas del DOM, y en el sistema de eventos `prestashop.on` de PrestaShop.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   El módulo no proporciona archivos CSS personalizados. Los valores de los atributos añadidos heredan el estilo del elemento del nombre del producto existente en el tema.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   El módulo no proporciona archivos de plantilla personalizados. Toda la salida se gestiona mediante el archivo principal del módulo (`anpn.php`) para la configuración, y JavaScript para la visualización en el front-office.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:
    -   El módulo no crea ninguna tabla de base de datos personalizada.
    -   Almacena sus ajustes de configuración en la tabla `ps_configuration`:
        -   `ANPN_PN_CLASS`: Almacena la clase/selector CSS para el elemento del nombre del producto.
-   **Tabla de Hooks registrados**:

  | Nombre del Hook | Momento de ejecución | Propósito técnico |
  | --- | --- | --- |
  | `displayHeader` | En la sección `<head>` de cada página del front-office. | Se utiliza para registrar el JavaScript del módulo (`anpn.js`) y pasar el valor de configuración `ANPN_PN_CLASS` al script del front-end. |
  | `displayProductAdditionalInfo` | En la página del producto, normalmente debajo de la información principal del producto. | Aunque no se utiliza explícitamente para la salida visual en este módulo, es un hook común para que los módulos inyecten contenido o scripts en la página del producto. En el contexto de este módulo, podría usarse para asegurar que el JS se cargue en el momento adecuado, o podría ser un registro de hook heredado. La interacción principal es a través de `displayHeader` y el evento `updatedProduct`. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Valores de atributos en el nombre del producto", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.

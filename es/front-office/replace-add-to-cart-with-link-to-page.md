---
title: "Reemplazar añadir al carrito con enlace a página - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Reemplazar añadir al carrito con enlace a página' de MyPresta.eu."
sidebar:
  label: "Reemplazar añadir al carrito con enlace a página - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Replace add to cart with link to page en MyPresta.eu](https://mypresta.eu/modules/front-office-features/replace-add-to-cart-with-link-to-page.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/replace-add-to-cart-with-link-to-page/)
>
> ---


# Reemplazar añadir al carrito con enlace a página

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla principal donde controla el comportamiento global del módulo.

-   **Activado**

    -   **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar la funcionalidad del módulo en toda su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El módulo comenzará a reemplazar los botones "Añadir al carrito" con enlaces personalizados basados en la configuración específica de sus productos y otras configuraciones globales.
        -   *Cuando está desactivado:* El módulo estará inactivo y todos los botones "Añadir al carrito" volverán a su comportamiento predeterminado de PrestaShop.
    -   **Valor recomendado:** SÍ (para activar el módulo).
    -   **Escenario / ejemplo de comerciante:** Si está probando el módulo o desea desactivar temporalmente su funcionalidad sin desinstalarlo, puede establecerlo en NO. Para un uso activo, debe ser SÍ.
-   **Texto del botón**

    -   **Qué hace este ajuste:** Define el texto que aparecerá en el botón personalizado, reemplazando "Añadir al carrito". Este texto se puede traducir a diferentes idiomas.
    -   **Efecto de cambiar este ajuste:** El texto del botón cambiará al valor especificado.
    -   **Valor recomendado:** Algo descriptivo como "Más información", "Solicitar presupuesto", "Ver detalles" o "Visitar sitio del socio".
    -   **Escenario / ejemplo de comerciante:** Si está enlazando a un sitio externo para obtener más información, podría establecerlo en "Más información". Si está dirigiendo a los clientes a un formulario de presupuesto, "Solicitar presupuesto" sería apropiado.
-   **Ocultar campo de cantidad**

    -   **Qué hace este ajuste:** Controla si el campo de entrada de cantidad (donde los clientes seleccionan cuántos artículos añadir) es visible en las páginas de producto cuando el módulo está activo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El selector de cantidad se ocultará, ya que no es relevante cuando el botón redirige en lugar de añadir al carrito.
        -   *Cuando está desactivado:* El selector de cantidad permanecerá visible, lo que podría ser confuso si el botón no añade al carrito.
    -   **Valor recomendado:** SÍ.
    -   **Escenario / ejemplo de comerciante:** Dado que el botón ya no añade al carrito, normalmente no hay necesidad de un campo de cantidad. Ocultarlo simplifica la interfaz y evita confusiones.
-   **Clase CSS del botón añadir al carrito en la página de producto**

    -   **Qué hace este ajuste:** Le permite especificar una clase CSS personalizada para el botón de reemplazo en la página de producto. Esto es útil para estilizar el botón para que coincida con su tema o para hacerlo destacar.
    -   **Efecto de cambiar este ajuste:** El botón heredará los estilos definidos por esta clase CSS en la hoja de estilos de su tema.
    -   **Valor recomendado:** Dejar vacío si el estilo predeterminado del botón de su tema es aceptable, o usar una clase como `btn btn-primary` o `my-custom-button` si tiene estilos específicos.
    -   **Escenario / ejemplo de comerciante:** Si su tema usa `btn-success` para los botones de acción principal, podría introducir `btn-success` aquí para que su botón personalizado sea verde y prominente.
-   **Clase CSS de la cantidad**

    -   **Qué hace este ajuste:** Le permite especificar una clase CSS para el campo de entrada de cantidad en la página de producto. Esto es principalmente para estilos avanzados o si necesita apuntar al campo de cantidad con CSS personalizado.
    -   **Efecto de cambiar este ajuste:** El campo de entrada de cantidad recibirá esta clase CSS.
    -   **Valor recomendado:** Dejar vacío a menos que tenga una necesidad de estilo específica.
    -   **Escenario / ejemplo de comerciante:** Un desarrollador podría usar esto para aplicar un ancho o relleno específico al campo de cantidad si no está oculto.
-   **Aplicar módulo a la lista de productos**

    -   **Qué hace este ajuste:** Determina si la funcionalidad del módulo (reemplazar "Añadir al carrito" con un enlace personalizado) también se aplica a los botones de producto mostrados en listas (por ejemplo, páginas de categoría, resultados de búsqueda, productos destacados en la página de inicio).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Los botones "Añadir al carrito" en las listas de productos también serán reemplazados por el enlace personalizado.
        -   *Cuando está desactivado:* Solo el botón "Añadir al carrito" de la página de producto se verá afectado; los botones de la lista de productos conservarán su comportamiento predeterminado.
    -   **Valor recomendado:** SÍ, para una consistencia en toda su tienda, especialmente si el enlace personalizado es una parte crítica de su embudo de ventas.
    -   **Escenario / ejemplo de comerciante:** Si todos los productos que requieren este enlace personalizado son servicios que necesitan un presupuesto, querría que esto estuviera habilitado para que los clientes no intenten "añadir al carrito" desde una página de categoría.
-   **Clase CSS del elemento con producto**

    -   **Qué hace este ajuste:** Este es un ajuste técnico para ayudar al módulo a identificar el contenedor principal de un producto en una vista de lista. Es crucial para que el módulo encuentre y modifique correctamente el botón "Añadir al carrito" dentro de cada elemento del producto.
    -   **Efecto de cambiar este ajuste:** Si es incorrecto, el módulo podría no aplicar sus cambios a los elementos de la lista de productos.
    -   **Valor recomendado:** Esto depende en gran medida del tema. Los valores comunes incluyen `product-miniature`, `product-container`, `product-item`. Es posible que deba inspeccionar el HTML de su tema para encontrar la clase correcta.
    -   **Escenario / ejemplo de comerciante:** Si su tema usa `<div class="product-card">` para cada producto en una lista, introduciría `product-card` aquí.
-   **Clase CSS de** (Esto probablemente se refiere al propio botón "Añadir al carrito" dentro de un elemento de la lista de productos)

    -   **Qué hace este ajuste:** Especifica la clase CSS del botón "Añadir al carrito" dentro de los elementos de la lista de productos. Esto ayuda al módulo a apuntar al botón correcto para su reemplazo.
    -   **Efecto de cambiar este ajuste:** Si es incorrecto, el módulo podría no reemplazar el botón "Añadir al carrito" en las listas de productos.
    -   **Valor recomendado:** Esto depende en gran medida del tema. Los valores comunes incluyen `add-to-cart`, `product-add-to-cart`, `btn-primary`. Inspeccione el HTML de su tema.
    -   **Escenario / ejemplo de comerciante:** Si el botón "Añadir al carrito" de su tema en las listas tiene la clase `btn-add-to-cart`, introduciría eso aquí.
-   **Clase CSS de la entrada de cantidad en la lista de productos**

    -   **Qué hace este ajuste:** Similar al ajuste de la página de producto, esto le permite especificar la clase CSS para el campo de entrada de cantidad cuando los productos se muestran en una lista. Esto se usa para ocultarlo si `Ocultar campo de cantidad` está habilitado.
    -   **Efecto de cambiar este ajuste:** Si es incorrecto, el campo de cantidad podría permanecer visible en las listas de productos incluso si ha elegido ocultarlo.
    -   **Valor recomendado:** Dejar vacío a menos que tenga una necesidad de estilo específica o si el campo de cantidad no se está ocultando correctamente. Inspeccione el HTML de su tema.
    -   **Escenario / ejemplo de comerciante:** Si su tema usa `product-quantity-input` para el campo de cantidad en las listas, introduciría eso aquí.
-   **Ocultar tooltip sobre el botón**

    -   **Qué hace este ajuste:** Controla si el tooltip predeterminado de PrestaShop (que a menudo muestra "Añadir al carrito" o similar) aparece al pasar el ratón sobre el botón personalizado.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El tooltip se ocultará, evitando mensajes potencialmente confusos.
        -   *Cuando está desactivado:* El tooltip predeterminado podría seguir apareciendo, lo que podría entrar en conflicto con el propósito del botón personalizado.
    -   **Valor recomendado:** SÍ.
    -   **Escenario / ejemplo de comerciante:** Si su botón personalizado dice "Solicitar presupuesto", no querrá que aparezca un tooltip que diga "Añadir al carrito". Ocultarlo garantiza un mensaje claro.
-   **Añadir rel="nofollow"**

    -   **Qué hace este ajuste:** Añade el atributo `rel="nofollow"` al enlace personalizado. Esto le dice a los motores de búsqueda que no sigan el enlace y que no le pasen ningún "link juice" al destino.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El enlace tendrá `rel="nofollow"`, lo que es útil para enlaces externos que no desea respaldar o para enlaces internos que no son críticos para el SEO (por ejemplo, páginas de inicio de sesión).
        -   *Cuando está desactivado:* El enlace será un enlace estándar seguido.
    -   **Valor recomendado:** SÍ para enlaces externos, especialmente enlaces de afiliados o enlaces a sitios que no controla completamente. NO para enlaces internos dentro de su propio sitio que desea que los motores de búsqueda rastreen.
    -   **Escenario / ejemplo de comerciante:** Si está enlazando al sitio web de un socio afiliado, habilitar `nofollow` es una buena práctica para evitar posibles penalizaciones de SEO y para indicar claramente que es un enlace patrocinado o externo.
-   **Abrir enlaces en una nueva ventana (pestaña)**

    -   **Qué hace este ajuste:** Determina si el enlace personalizado se abre en la misma pestaña del navegador o en una nueva.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El enlace se abrirá en una nueva pestaña del navegador, manteniendo la página de su tienda abierta en la pestaña original.
        -   *Cuando está desactivado:* El enlace se abrirá en la misma pestaña, alejando al cliente de su tienda.
    -   **Valor recomendado:** SÍ para enlaces externos, para mantener a los clientes en su sitio. NO para enlaces internos donde desea que el cliente navegue dentro de su tienda.
    -   **Escenario / ejemplo de comerciante:** Si está dirigiendo a los clientes a un sitio de socio externo, abrir en una nueva pestaña es generalmente mejor para que puedan regresar fácilmente a la página de su producto.
-   **Visibilidad del módulo para productos seleccionados**

    -   **Qué hace este ajuste:** Este es un ajuste crucial que define *qué* productos tendrán su botón "Añadir al carrito" reemplazado. Funciona en conjunto con la configuración específica del producto que encontrará en la página de edición de cada producto.
    -   **Efecto de cambiar este ajuste:**
        -   *Activado:* El módulo solo se aplicará a los productos donde haya definido explícitamente una URL personalizada en la configuración de su producto.
        -   *Desactivado:* El módulo no se aplicará a ningún producto, independientemente de su configuración individual.
    -   **Valor recomendado:** Activado. Esto le permite aplicar selectivamente la función de enlace personalizado a productos específicos.
    -   **Escenario / ejemplo de comerciante:** Solo desea reemplazar el botón "Añadir al carrito" para sus muebles hechos a medida, no para los accesorios estándar. Habilitaría este ajuste y luego iría a cada producto de muebles y establecería su URL personalizada.

#### Configuración específica del producto (Back Office > Catálogo > Productos > Editar producto > Pestaña Módulos)

Una vez que el módulo esté instalado y habilitado, encontrará nuevos ajustes al editar productos individuales.

-   **Campo URL del producto**
    -   **Qué hace este ajuste:** Aquí es donde introduce la URL específica a la que redirigirá el botón "Añadir al carrito" de *este producto en particular*.
    -   **Efecto de cambiar este ajuste:** Cuando un cliente haga clic en el botón personalizado en la página de este producto (o en una lista, si está habilitado), será llevado a esta URL.
    -   **Valor recomendado:** Una URL completa y válida (por ejemplo, `https://example.com/request-a-quote` o `/contact-us`).
    -   **Escenario / ejemplo de comerciante:** Para un producto de "Servicio de diseño personalizado", podría introducir `https://yourstore.com/contact-us?subject=Custom%20Design%20Inquiry` aquí.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### AdminAtcurlSearchController (Back Office > Módulos > Reemplazar añadir al carrito con enlace a página > Configurar > Pestaña "Productos seleccionados")

Esta pantalla proporciona una forma centralizada de gestionar y ver qué productos tienen URLs personalizadas configuradas.

-   **Nombre de la pantalla y ubicación del menú:** Accede a esta pantalla navegando a **Módulos > Gestor de módulos**, buscando "Reemplazar añadir al carrito con enlace a página", haciendo clic en "Configurar" y luego seleccionando la pestaña "Productos seleccionados" (o similar, según la versión del módulo).
-   **Acciones y ajustes disponibles:** Esta pantalla suele mostrar una cuadrícula o lista de productos que actualmente tienen una URL personalizada definida.
    -   **Columnas:** Normalmente verá columnas como ID del producto, Nombre del producto y la URL personalizada.
    -   **Buscar/Filtrar:** Puede haber opciones de búsqueda o filtro para encontrar rápidamente productos específicos.
    -   **Editar/Eliminar:** Puede tener enlaces directos para editar el producto (que le lleva a la página de edición de producto estándar) o eliminar la URL personalizada de un producto directamente desde esta lista.
-   **Efecto de los cambios:**
    -   Modificar una URL aquí (si la edición directa está disponible) o a través de la página de edición del producto cambiará inmediatamente a dónde redirige el botón para ese producto.
    -   Eliminar un producto de esta lista (o borrar su URL personalizada en la página de edición del producto) revertirá el botón "Añadir al carrito" a su comportamiento predeterminado de PrestaShop.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esta pantalla para auditar rápidamente qué productos están utilizando la función de enlace personalizado. Si necesita actualizar muchos enlaces de productos, esta vista le ayuda a realizar un seguimiento. Para añadir nuevos enlaces, suele ser más eficiente ir directamente a la página de edición del producto.

#### index.php (atcurl/controllers/admin/index.php)

Este archivo es un marcador de posición y normalmente no representa una pantalla de administración orientada al usuario. En PrestaShop, los archivos `index.php` dentro de los directorios de controladores se utilizan a menudo para evitar la lista directa de directorios o para incluir otros archivos. No es una pantalla de configuración para los comerciantes.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de configuración del módulo** | Activado | SÍ | Interruptor maestro para activar/desactivar la funcionalidad del módulo. |
| | Texto del botón | "Más información" (ejemplo) | Texto que se muestra en el botón personalizado. |
| | Ocultar campo de cantidad | SÍ | Oculta el selector de cantidad en las páginas de producto. |
| | Clase CSS del botón añadir al carrito en la página de producto | (Vacío / Depende del tema) | Clase CSS personalizada para el botón en las páginas de producto. |
| | Clase CSS de la cantidad | (Vacío) | Clase CSS personalizada para la entrada de cantidad en las páginas de producto. |
| | Aplicar módulo a la lista de productos | SÍ | Extiende la funcionalidad del módulo a las páginas de listado de productos. |
| | Clase CSS del elemento con producto | `product-miniature` (ejemplo) | Ayuda al módulo a identificar los contenedores de productos en las listas. |
| | Clase CSS de (botón Añadir al carrito en la lista) | `add-to-cart` (ejemplo) | Ayuda al módulo a identificar los botones "Añadir al carrito" en las listas. |
| | Clase CSS de la entrada de cantidad en la lista de productos | (Vacío) | Clase CSS personalizada para la entrada de cantidad en las listas de productos. |
| | Ocultar tooltip sobre el botón | SÍ | Evita el tooltip predeterminado "Añadir al carrito" en el botón personalizado. |
| | Añadir rel="nofollow" | SÍ (para externos) / NO (para internos) | Añade el atributo `nofollow` al enlace personalizado. |
| | Abrir enlaces en una nueva ventana (pestaña) | SÍ (para externos) / NO (para internos) | Abre el enlace personalizado en una nueva pestaña del navegador. |
| | Visibilidad del módulo para productos seleccionados | Activado | Activa la configuración de URL específica del producto. |
| **Página de edición del producto (Pestaña Módulos)** | Campo URL del producto | (URL personalizada) | Define la URL de redirección específica para *este* producto. |
| **AdminAtcurlSearchController** | Cuadrícula de productos con URLs personalizadas | N/A | Vista centralizada para gestionar productos con enlaces personalizados. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mi botón "Añadir al carrito" no cambia, incluso después de configurar una URL.**
R1:

-   **Verificar el estado del módulo:** Primero, asegúrese de que el interruptor "Activado" en la página de configuración principal del módulo esté configurado en SÍ.
-   **Verificar la visibilidad del producto:** Asegúrese de que "Visibilidad del módulo para productos seleccionados" esté configurado en "Activado" en la página de configuración del módulo.
-   **Verificar la URL del producto:** Verifique que haya introducido una URL válida en el "Campo URL del producto" para el producto específico que está probando (en la página de edición del producto, en la pestaña "Módulos").
-   **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, PrestaShop almacena en caché contenido antiguo.
-   **Compatibilidad del tema:** Su tema podría usar clases CSS no estándar para su botón "Añadir al carrito" o contenedores de productos. Verifique los ajustes "Clase CSS del elemento con producto" y "Clase CSS de" en la página de configuración del módulo. Es posible que deba usar las herramientas de desarrollador de su navegador (F12) para inspeccionar el HTML y encontrar las clases correctas.

**P2: El campo de cantidad sigue visible, aunque seleccioné ocultarlo.**
R2:

-   **Verificar "Ocultar campo de cantidad":** Asegúrese de que este ajuste esté habilitado en la página de configuración del módulo.
-   **Verificar "Clase CSS de la entrada de cantidad":** Si su tema usa una clase no estándar para la entrada de cantidad, es posible que el módulo no pueda encontrarla y ocultarla. Use las herramientas de desarrollador de su navegador para inspeccionar el campo de entrada de cantidad e introduzca su clase CSS en el ajuste "Clase CSS de la cantidad" (para la página de producto) y "Clase CSS de la entrada de cantidad en la lista de productos" (para las listas de productos).
-   **Borrar caché:** Siempre borre la caché de PrestaShop después de realizar cambios en la configuración.

**P3: El módulo funciona en las páginas de producto, pero no en las páginas de categoría/listado.**
R3:

-   **Verificar "Aplicar módulo a la lista de productos":** Asegúrese de que este ajuste esté habilitado en la página de configuración del módulo.
-   **Verificar las clases CSS para las listas:** El módulo necesita saber cómo su tema estructura las listas de productos. Verifique que los ajustes "Clase CSS del elemento con producto" y "Clase CSS de" (para el botón) sean correctos para su tema. A menudo, estas son diferentes de las clases de la página de producto. Use las herramientas de desarrollador del navegador para inspeccionar los elementos en una página de categoría.
-   **Borrar caché:** Borre la caché de PrestaShop.

**P4: Mi botón personalizado no se ve bien (color, tamaño incorrectos, etc.).**
R4:

-   **Clase CSS para el estilo:** Use el ajuste "Clase CSS del botón añadir al carrito en la página de producto". Introduzca una clase CSS que ya exista en su tema y proporcione el estilo deseado (por ejemplo, `btn btn-primary`, `btn-success`).
-   **CSS personalizado:** Si necesita un estilo único, deberá añadir CSS personalizado a su tema. Puede apuntar al botón usando la clase que configuró en el módulo, o inspeccionando su HTML. Por ejemplo:

    ```
    .my-custom-button-class { background-color: #ff6600; color: white; border-radius: 5px; padding: 10px 20px;}
    ```

    Añada este CSS al archivo CSS personalizado de su tema o a través de un módulo CSS personalizado.
-   **Borrar caché:** Borre la caché de PrestaShop.

**Q5: ¿Cómo traduzco el texto del botón a otros idiomas?**
R5:

-   Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop.
-   Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione el idioma que desea traducir.
-   Busque el módulo "Reemplazar añadir al carrito con enlace a página". Verá el campo "Texto del botón" allí, lo que le permitirá introducir traducciones para cada idioma.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Reemplazar añadir al carrito con enlace a página" (`atcurl`) es un módulo estándar de PrestaShop que sigue un patrón similar a MVC. Principalmente extiende la funcionalidad existente de PrestaShop a través de hooks para modificar la visualización en el front-office de las páginas de producto y las listas de productos. La configuración se gestiona a través del método `getContent()` del módulo principal y se almacena en `ps_configuration`. Las URLs específicas de los productos se almacenan como `Product::specific_fields` o potencialmente en una tabla personalizada, con un controlador de administración (`AdminAtcurlSearchController`) que proporciona una interfaz de gestión. JavaScript se utiliza en gran medida para reemplazar dinámicamente botones y ocultar elementos en el front-office.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Este módulo no contiene ningún controlador de front-office dedicado. Todas las modificaciones del front-office se gestionan a través de hooks y JavaScript.
-   **Controladores de administración de Back-Office**:

    -   `atcurl/controllers/admin/AdminAtcurlSearchController.php`
        -   **Nombre de la clase y clase padre:** `AdminAtcurlSearchController` extiende `ModuleAdminController`.
        -   **Nombre de la pestaña y entidad gestionada:** Este controlador es probablemente responsable de mostrar una cuadrícula o lista de productos que tienen una URL personalizada configurada por el módulo. Proporciona una vista centralizada para gestionar estas asociaciones de productos, permitiendo potencialmente ediciones rápidas o eliminaciones de la URL personalizada. No gestiona un `ObjectModel` dedicado, sino que interactúa con los datos del producto y la configuración del módulo.
    -   `atcurl/controllers/admin/index.php`
        -   Este es un archivo de marcador de posición estándar de PrestaShop, que normalmente contiene `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../../../"); exit;` para evitar la lista directa de directorios y redirigir al panel de administración principal. No proporciona ninguna lógica de controlador funcional.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no parece definir ninguna clase personalizada u `ObjectModel` en el directorio `classes/`. Las URLs específicas de los productos probablemente se almacenan como `Product::specific_fields` o directamente dentro de la tabla `ps_configuration`, con clave por ID de producto, o potencialmente un campo personalizado añadido a la entidad del producto.

### 4.4 Activos de JavaScript (`views/js/`)

-   `atcurl/lib/js/admin/atcurl177.js`
    -   **Alcance:** Back-office (Administración).
    -   **Responsabilidad:** Probablemente maneja la lógica específica de la página de configuración del módulo o del `AdminAtcurlSearchController` para las versiones de PrestaShop 1.7.7+. Esto podría incluir llamadas AJAX para guardar configuraciones, actualizaciones dinámicas de la interfaz de usuario o interacciones con la herramienta de búsqueda/selección de productos.
-   `atcurl/lib/js/front/atcurl-list-177.js`
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Se dirige específicamente a las páginas de listado de productos (categoría, búsqueda, bloques de la página de inicio). Escucha los cambios del DOM (por ejemplo, cuando los productos se cargan a través de AJAX) y reemplaza dinámicamente los botones "Añadir al carrito" con el enlace personalizado, oculta los campos de cantidad y aplica clases CSS personalizadas según la configuración. Está diseñado para temas de PrestaShop 1.7.7+.
-   `atcurl/lib/js/front/atcurl177.js`
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Se dirige principalmente a la página de producto individual. Identifica el botón "Añadir al carrito", lo reemplaza con el enlace personalizado, oculta la entrada de cantidad y aplica los atributos `nofollow` o `target="_blank"` según la configuración del módulo. También se encarga de ocultar los tooltips. Diseñado para temas de PrestaShop 1.7.7+.
-   `atcurl/lib/searchTool/views/js/autocomplete.js`
    -   **Alcance:** Back-office (Administración).
    -   **Responsabilidad:** Proporciona funcionalidad de autocompletado, probablemente para seleccionar productos en la configuración del módulo o en la cuadrícula de `AdminAtcurlSearchController`. Esto ayuda a los administradores a encontrar y asociar rápidamente productos con URLs personalizadas.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `atcurl/lib/searchTool/views/css/autocomplete.css`
    -   **Alcance:** Back-office (Administración).
    -   **Responsabilidad:** Estiliza el desplegable de autocompletado y los elementos de la interfaz de usuario relacionados utilizados en la herramienta de búsqueda de administración, asegurando que se integre visualmente con el tema del Back Office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   `atcurl/views/hook/displayProductAdditionalInfo.tpl`
        -   **Hook:** `displayProductAdditionalInfo`
        -   **Propósito:** Esta plantilla probablemente se renderiza en la página del producto, proporcionando el contenedor o el HTML real del botón personalizado que reemplaza el botón estándar "Añadir al carrito". Contendría la lógica para mostrar el texto y el enlace del botón personalizado.
    -   `atcurl/views/hook/displayProductListReviews.tpl`
        -   **Hook:** `displayProductListReviews` (Este nombre de hook es inusual para el reemplazo de botones y podría ser un error tipográfico o una forma indirecta de inyectar JS/CSS para listas de productos. Es más común usar `displayProductListFunctionalButtons` o `displayProductActions` para modificaciones de botones en listas).
        -   **Propósito:** Si se usa, esta plantilla inyectaría JavaScript o un elemento oculto en los elementos de la lista de productos, que el script `atcurl-list-177.js` luego usaría para realizar el reemplazo del botón. Es menos probable que contenga el HTML del botón directamente.
-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `atcurl/lib/searchTool/views/scripts.tpl`
        -   **Propósito:** Esta plantilla probablemente se incluye en el Back Office para cargar el JavaScript necesario (`autocomplete.js`) y potencialmente CSS (`autocomplete.css`) para la herramienta de búsqueda/selección de productos utilizada en la configuración del módulo o en `AdminAtcurlSearchController`.
    -   `atcurl/views/tpl/selectedProducts.tpl`
        -   **Propósito:** Esta plantilla es utilizada por `AdminAtcurlSearchController` para renderizar la cuadrícula o lista de productos que tienen URLs personalizadas configuradas. Define la estructura de la tabla y cómo se muestra la información de cada producto (ID, nombre, URL).
-   **Plantillas de Front-office (`views/templates/front/`)**: Ninguna explícitamente listada, ya que los cambios en el front-office se gestionan principalmente mediante JS y plantillas de hook.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:

    -   El módulo no parece crear tablas SQL personalizadas.
    -   **`ps_configuration`**: Almacena la configuración global del módulo (por ejemplo, `ATC_URL_BUTTON_FRONT`, `ATC_URL_BUTTON_TEXT`, `ATC_URL_BLANK`, `ATC_URL_NOFOLLOW`, `ATC_HIDE_TOOLTIP`, `ATC_URL_PL`, `ATC_URL_visibility_rule`, `ATC_URL_BUTTON_QTY_HIDE`, `ATC_URL_visibility_products`, `ATC_URL_visibility_cat`).
    -   **`ps_product_shop` / `ps_product_lang`**: Las URLs específicas de los productos probablemente se almacenan como un campo adicional asociado al producto, potencialmente utilizando el mecanismo `specific_fields` de PrestaShop o actualizando directamente las propiedades del producto. El método `install()` del módulo añadiría este campo.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Alcance | Momento de ejecución | Propósito técnico |
| --- | --- | --- | --- |
| `displayProductAdditionalInfo` | Front-Office | En la página del producto, normalmente debajo de la descripción del producto o del bloque de precios. | Inyecta el HTML del botón personalizado o un marcador de posición para que JS lo dirija. |
| `ActionAdminControllerSetMedia` | Back-Office | Cuando un controlador de administración carga sus medios (JS/CSS). | Carga JavaScript (`atcurl177.js`, `autocomplete.js`) y CSS (`autocomplete.css`) específicos de la administración para la configuración del módulo y la gestión de productos. |
| `actionProductUpdate` | Back-Office | Después de que un producto se actualiza/guarda en el Back Office. | Permite que el módulo guarde la URL personalizada asociada al producto. |
| `displayHeader` | Front-Office | En la sección `<head>` de cada página del front-office. | Inyecta JavaScript del front-office (`atcurl177.js`, `atcurl-list-177.js`) y potencialmente CSS en línea o variables de configuración para los scripts JS. |
| `displayProductListReviews` | Front-Office | Dentro de los elementos de la lista de productos, a menudo cerca del nombre del producto o la calificación. | (Como se señaló anteriormente, este hook es inusual para el reemplazo de botones. Es probable que se use para inyectar JS para el procesamiento de elementos de la lista, o podría ser un hook heredado. Los desarrolladores deben verificar su uso real en el código del módulo). |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Reemplazar añadir al carrito con enlace a página", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo se dedica a garantizar que el módulo funcione de manera óptima con su tienda PrestaShop.

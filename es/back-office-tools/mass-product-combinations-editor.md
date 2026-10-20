---
title: "Editor masivo de combinaciones de productos - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Editor masivo de combinaciones de productos' de MyPresta.eu."
sidebar:
  label: "Editor masivo de combinaciones de productos - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Mass product combinations editor en MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-product-combinations-editor.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/mass-product-combinations-editor/)
>
> ---


# Editor masivo de combinaciones de productos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren requisitos especiales del servidor más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Editor masivo de combinaciones de productos)

Al hacer clic en "Configurar" para el módulo "Editor masivo de combinaciones de productos", accederá a una interfaz de administración dedicada. Aquí es donde realizará todas sus ediciones masivas de combinaciones.

La página de configuración principal de este módulo actúa como su interfaz principal. No tiene un "formulario de configuración" tradicional con interruptores y campos de entrada para el módulo en sí, sino que ES la herramienta para editar combinaciones.

Aquí hay un desglose de lo que verá y cómo usarlo:

**Nombre de la pantalla y ubicación del menú:**

-   **Ruta del menú:** Después de la instalación, normalmente encontrará un nuevo elemento de menú en **Catálogo** o **Módulos** (dependiendo de su versión y tema de PrestaShop) o siempre puede acceder a él a través de **Módulos > Gestor de módulos** y haciendo clic en "Configurar" junto a "Editor masivo de combinaciones de productos".
-   **Título de la pantalla:** "Editor masivo de combinaciones de productos" o similar.

**Acciones y configuraciones disponibles:**

La interfaz principal le presentará una potente cuadrícula o tabla que lista las combinaciones de productos. La apariencia exacta puede variar ligeramente entre las versiones de PrestaShop, pero la funcionalidad principal sigue siendo consistente.

1.  **Selección / Filtrado de productos:**

    -   **Qué hace:** Esta área le permite seleccionar las combinaciones de qué productos desea editar. Puede ver una barra de búsqueda, un menú desplegable de productos o filtros por categoría, fabricante, etc.
    -   **Efecto de cambiar esta configuración:** Al seleccionar un producto o aplicar filtros, la tabla de abajo se llenará solo con las combinaciones que pertenecen a los productos elegidos. Esto es crucial para reducir su enfoque.
    -   **Valor recomendado:** Comience buscando un producto específico o filtrando por una categoría para familiarizarse con la interfaz.
    -   **Escenario / ejemplo de comerciante:** Desea actualizar el stock de todas las combinaciones de su producto "Camiseta de Verano". Buscaría "Camiseta de Verano" y la seleccionaría.
2.  **Tabla de listado de combinaciones:**

    -   **Qué hace:** Este es el núcleo del módulo. Muestra una tabla donde cada fila representa una combinación de producto única (por ejemplo, "Camiseta - Roja - Pequeña"). Las columnas representan campos editables como:
        -   **Referencia:** Código de producto interno para esta combinación específica.
        -   **EAN13 / UPC:** Números de código de barras.
        -   **Cantidad:** Nivel de stock para esta combinación.
        -   **Impacto en el precio:** Cómo esta combinación afecta el precio base del producto (por ejemplo, +5€ para la talla XL).
        -   **Precio al por mayor:** El precio de costo de esta combinación.
        -   **Peso:** Cómo esta combinación afecta el peso base del producto.
        -   **Cantidad mínima:** El número mínimo de esta combinación que un cliente debe comprar.
        -   **Combinación predeterminada:** Una casilla de verificación para marcar una combinación como predeterminada para el producto.
        -   **Imagen:** La imagen asociada a esta combinación.
    -   **Efecto de cambiar esta configuración:** Puede hacer clic directamente en las celdas de esta tabla y escribir nuevos valores. Por ejemplo, cambiar la "Cantidad" de 5 a 10 actualizará el nivel de stock para esa combinación específica.
    -   **Valor recomendado:** Revise cuidadosamente cada combinación y sus valores actuales antes de realizar cambios.
    -   **Escenario / ejemplo de comerciante:** Acaba de recibir un nuevo envío. Puede recorrer la columna "Cantidad" y actualizar los niveles de stock de todas las combinaciones relevantes en segundos.
3.  **Botón Guardar:**

    -   **Qué hace:** Después de realizar todos los cambios deseados en la tabla, **debe** hacer clic en un botón "Guardar" o "Aplicar cambios" (generalmente se encuentra en la parte superior o inferior de la tabla) para confirmar sus modificaciones en la base de datos.
    -   **Efecto de cambiar esta configuración:** Hasta que haga clic en guardar, sus cambios solo son visibles en la pantalla y no están activos en su tienda. Al hacer clic en guardar, se aplican todas las modificaciones pendientes.
    -   **Valor recomendado:** Guarde siempre su trabajo con frecuencia, especialmente después de realizar un lote de cambios.
    -   **Escenario / ejemplo de comerciante:** Ha actualizado los precios de 20 combinaciones. Haga clic en "Guardar" para que estos nuevos precios estén activos en sus páginas de productos.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1.  **Identifique su tarea:** ¿Necesita actualizar el stock, cambiar precios o modificar referencias?
2.  **Navegue al módulo:** Vaya a **Módulos > Gestor de módulos** y haga clic en "Configurar" para "Editor masivo de combinaciones de productos".
3.  **Seleccione productos:** Use las opciones de búsqueda o filtro para cargar las combinaciones con las que necesita trabajar.
4.  **Realice cambios:** Edite directamente los valores en las celdas de la tabla. A menudo puede usar atajos de teclado (como Tab) para moverse rápidamente entre los campos.
5.  **Revise:** Verifique dos veces sus cambios antes de guardar.
6.  **Guarde:** Haga clic en el botón "Guardar" para aplicar todas las modificaciones.
7.  **Borrar caché (si es necesario):** En algunos casos, especialmente después de cambios importantes de precio o stock, es una buena práctica borrar la caché de PrestaShop (**Parámetros avanzados > Rendimiento**) para asegurarse de que los cambios sean inmediatamente visibles en el front office.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Selección/Filtro de productos | (Varía según el producto) | Reduce las combinaciones mostradas para su edición. |
| Página de configuración del módulo | Tabla de listado de combinaciones (por ejemplo, Cantidad, Impacto en el precio, Referencia, EAN13) | (Varía según el producto) | Edición directa de atributos de combinación. Los cambios se aplican a la combinación seleccionada. |
| Página de configuración del módulo | Botón Guardar | Haga clic después de los cambios | Confirma todas las modificaciones en pantalla en la base de datos, haciéndolas activas en su tienda. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: ¡Mis cambios no aparecen en el front office después de guardar!**
R: Esto suele ser un problema de caché. Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty" / "Borrar caché" según su versión). Sus cambios deberían aparecer entonces.

**P: El módulo tarda en cargar las combinaciones para productos con muchas variaciones.**
R: Para productos con cientos o miles de combinaciones, cargar todos los datos puede llevar tiempo. Esto es normal debido a la cantidad de datos que se procesan. Asegúrese de que su servidor cumpla con las especificaciones recomendadas de PrestaShop. Si es consistentemente muy lento, verifique el límite de memoria PHP y la configuración del tiempo de ejecución de su servidor (su proveedor de alojamiento puede ayudarle con esto).

**P: ¿Puedo deshacer los cambios realizados con este módulo?**
R: El módulo actualiza directamente su base de datos. No hay un botón de "deshacer" incorporado. Por eso es crucial **tener siempre una copia de seguridad reciente de su tienda** antes de realizar cambios masivos. Si comete un error, tendría que corregir manualmente los valores o restaurar desde una copia de seguridad.

**P: No encuentro el módulo en el menú después de la instalación.**
R: Después de la instalación, navegue a **Módulos > Gestor de módulos**. Busque "Editor masivo de combinaciones de productos" y haga clic en el botón "Configurar" junto a él. Esto siempre le llevará a la interfaz del módulo. Dependiendo de su versión y tema de PrestaShop, un enlace directo en el menú podría aparecer bajo "Catálogo" o "Módulos" para un acceso más rápido.

**P: ¿Este módulo funciona con temas personalizados?**
R: Sí, este módulo opera completamente dentro del Back Office de PrestaShop. No genera ningún elemento en el front office, por lo que debería ser totalmente compatible con cualquier tema personalizado sin conflictos.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Editor masivo de combinaciones de productos" (`qce`) es principalmente una herramienta de administración del Back-Office. Aprovecha la clase `Module` de PrestaShop para su funcionalidad principal y utiliza un endpoint AJAX personalizado para manejar la carga dinámica y el guardado de datos de combinaciones de productos. La interfaz del módulo se renderiza a través de una plantilla Smarty, con JavaScript manejando las interacciones del usuario y el envío de datos. Interactúa directamente con las estructuras de datos de productos y combinaciones principales de PrestaShop sin introducir nuevas clases `ObjectModel` o tablas de base de datos.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza clases `ModuleFrontController` o `AdminController` dedicadas en el directorio `controllers/`. Toda la lógica del Back-Office, incluido el endpoint AJAX, se maneja directamente dentro del archivo principal del módulo `qce/ajax_qce.php` a través del método `getContent()`.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no introduce ninguna clase personalizada en un directorio `classes/`. Utiliza directamente las clases principales de PrestaShop, como `Product`, `Combination`, `Tools`, `Configuration`, etc., para recuperar y actualizar datos.

### 4.4 Activos de JavaScript (`views/js/`)

-   **`qce/views/admin/js/qce.js`**
    -   **Alcance:** Back-office (panel de administración).
    -   **Propósito:** Este es el archivo JavaScript principal para la interfaz del módulo. Maneja:
        -   **Selección de productos:** Probablemente gestiona el menú desplegable o el campo de búsqueda para seleccionar un producto.
        -   **Carga de datos AJAX:** Envía solicitudes AJAX al método `getContent()` del módulo (o a un controlador AJAX específico dentro de él) para obtener datos de combinación para el producto seleccionado.
        -   **Renderizado de tablas:** Rellena dinámicamente la tabla HTML con los datos de combinación recibidos del servidor.
        -   **Edición in situ:** Implementa la funcionalidad para que los usuarios hagan clic en las celdas de la tabla y editen valores directamente (por ejemplo, campos de entrada que aparecen al hacer clic).
        -   **Validación de datos:** Puede incluir validación del lado del cliente para los campos de entrada (por ejemplo, asegurar que la cantidad sea un número).
        -   **Guardado de datos AJAX:** Recopila todos los datos de combinación modificados de la tabla y los envía a través de AJAX al método `getContent()` del módulo para su procesamiento y guardado en la base de datos.
        -   **Comentarios del usuario:** Muestra spinners de carga, mensajes de éxito o alertas de error.
        -   **Detectores de eventos:** Vincula detectores a elementos como menús desplegables de selección de productos, campos de entrada dentro de la tabla y el botón "Guardar".

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`qce/lib/blue/style.css`**
    -   **Alcance:** Back-office (panel de administración).
    -   **Propósito:** Parece ser una hoja de estilo de terceros o genérica, posiblemente para un componente de interfaz de usuario o un tema de estilo específico utilizado dentro de la interfaz del módulo. Probablemente define estilos generales de tabla, estilos de campos de entrada o estética de botones. Los desarrolladores deben inspeccionar este archivo para comprender su impacto en la presentación visual del módulo.
-   **`qce/views/admin/css/qce.css`**
    -   **Alcance:** Back-office (panel de administración).
    -   **Propósito:** Esta es la hoja de estilo específica del módulo. Contiene reglas CSS personalizadas para estilizar la tabla de edición de combinaciones, los elementos de selección de productos y cualquier otro componente de interfaz de usuario único dentro de la página de configuración del módulo.
    -   **Selectores de clase CSS clave:** Los desarrolladores que deseen anular o personalizar la apariencia del módulo deben inspeccionar este archivo en busca de nombres de clase como `.qce-table`, `.qce-product-selector`, `.qce-input-field`, etc., y dirigirse a ellos en su tema de administración personalizado o anulando el CSS del módulo.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **`qce/views/admin/qce.tpl`**
    -   **Alcance:** Plantilla de administración.
    -   **Propósito:** Este es el archivo de plantilla Smarty principal responsable de renderizar toda la interfaz del "Editor masivo de combinaciones de productos" dentro del Back Office de PrestaShop.
    -   **Contenido:** Típicamente incluye:
        -   La estructura HTML para el área de selección/filtrado de productos.
        -   El marcador de posición (por ejemplo, una `<table>` o `<div>` vacía) donde los datos de combinación se cargarán y renderizarán dinámicamente mediante `qce.js`.
        -   El botón "Guardar" y cualquier otro botón de acción.
        -   Inclusiones para los archivos JavaScript (`qce.js`) y CSS (`qce.css`, `style.css`) necesarios.
        -   Cualquier mensaje o instrucción inicial para el comerciante.
    -   **Renderizado:** Esta plantilla es renderizada por el método `getContent()` del archivo del módulo `ajax_qce.php`.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    -   El módulo **no** crea ninguna tabla de base de datos personalizada.
    -   Lee y escribe directamente en las tablas principales de PrestaShop relacionadas con productos y combinaciones, principalmente:
        -   `ps_product_attribute` (datos principales de la combinación)
        -   `ps_product_attribute_shop` (datos de combinación específicos de la tienda)
        -   `ps_product_attribute_combination` (vincula atributos a combinaciones)
        -   `ps_product` (para información del producto)
        -   `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang` (para definiciones de atributos)
        -   `ps_image`, `ps_image_shop`, `ps_image_lang` (para imágenes de combinación)
    -   La configuración (si hubiera alguna más allá de la interfaz principal) se almacenaría en `ps_configuration`.
-   **Tabla de Hooks registrados**:
    El módulo no registra explícitamente ningún hook de visualización de front-office o back-office (`displayHeader`, `actionValidateOrder`, etc.) en un sentido tradicional. Su funcionalidad se accede directamente a través de su página de configuración en el Back Office. El método `install()` del módulo se registraría como un módulo de administración, haciéndolo accesible a través del Gestor de Módulos.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Editor masivo de combinaciones de productos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad del módulo.

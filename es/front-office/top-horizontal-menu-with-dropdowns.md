---
title: "Menú horizontal superior con desplegables - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Menú horizontal superior con desplegables' de MyPresta.eu."
sidebar:
  label: "Menú horizontal superior con desplegables - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Top horizontal menu with dropdowns en MyPresta.eu](https://mypresta.eu/modules/front-office-features/top-horizontal-menu-with-dropdowns.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/top-horizontal-menu-with-dropdowns/)
>
> ---


# Menú horizontal superior con desplegables

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser requeridas por PrestaShop y deben estar disponibles en cualquier entorno de alojamiento compatible.

## 2. Recorrido completo de configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" para acceder a la configuración del módulo. Esta pantalla le permite gestionar los elementos que aparecen en su menú horizontal superior y configurar la barra de búsqueda.

La página de configuración se divide en dos secciones principales: **Elementos del menú** y **Barra de búsqueda**.

#### 2.1.1 Gestión de elementos del menú

Esta sección le permite definir qué elementos aparecen en su menú de navegación principal. Puede añadir enlaces a categorías, páginas CMS, fabricantes, proveedores o URLs personalizadas.

- **Añadir un nuevo elemento de menú:**

  - **Etiqueta:** Este es el texto que se mostrará en su menú (por ejemplo, "Novedades", "Colección de verano", "Sobre nosotros"). Puede introducir diferentes etiquetas para cada idioma que admita su tienda.
    - *Efecto del cambio:* Cambia directamente el texto visible del elemento del menú para los clientes.
    - *Valor recomendado:* Texto claro, conciso y descriptivo que represente con precisión el destino del enlace.
    - *Escenario del comerciante:* Quiere añadir un enlace a su página "Contacto". Introduciría "Contacto" aquí.
  - **Enlace:** Esta es la URL a la que apuntará el elemento del menú. Puede seleccionar de una lista de categorías existentes, páginas CMS, fabricantes o proveedores, o introducir una URL personalizada.
    - *Efecto del cambio:* Determina a dónde se lleva al cliente cuando hace clic en este elemento del menú.
    - *Valor recomendado:* Asegúrese siempre de que el enlace sea válido y apunte a la página correcta. Para páginas internas, utilice las herramientas de selección proporcionadas. Para enlaces externos, asegúrese de que se introduce la URL completa (por ejemplo, `https://example.com/blog`).
    - *Escenario del comerciante:* Quiere enlazar a su categoría "Camisetas". Seleccionaría "Camisetas" del desplegable de categorías. Si quiere enlazar a un blog externo, escribiría la URL completa del blog.
  - **Nueva ventana:** Un interruptor (Sí/No) que determina si el enlace se abre en una nueva pestaña o ventana del navegador.
    - *Cuando está habilitado (Sí):* El enlace se abrirá en una nueva pestaña, manteniendo la página actual de su tienda abierta en la pestaña original.
    - *Cuando está deshabilitado (No):* El enlace se abrirá en la misma pestaña, navegando al cliente fuera de la página actual.
    - *Valor recomendado:* "Sí" para enlaces externos (por ejemplo, un blog, perfil de redes sociales) para mantener a los clientes en su tienda. "No" para enlaces internos (categorías, productos, páginas CMS) para mantener un flujo de navegación natural dentro de su sitio.
    - *Escenario del comerciante:* Está enlazando a su página de Facebook. Establezca "Nueva ventana" en "Sí" para que los clientes puedan volver fácilmente a su tienda.
- **Gestión de elementos de menú existentes:**

  - El módulo muestra una lista de sus elementos de menú actuales. Puede arrastrar y soltar elementos para reordenarlos, lo que afecta directamente a su orden de visualización en el front office.
  - Puede hacer clic en "Editar" para modificar la etiqueta, el enlace o la configuración de nueva ventana de un elemento existente.
  - Puede hacer clic en "Eliminar" para eliminar un elemento del menú.
    - *Efecto de los cambios:* Reordenar, editar o eliminar elementos actualiza inmediatamente la estructura y apariencia del menú en su tienda en vivo.
    - *Flujo de trabajo recomendado:* Revise regularmente la estructura de su menú para asegurarse de que sea lógica y esté actualizada. Priorice las categorías o promociones importantes colocándolas antes en el menú.

#### 2.1.2 Configuración de la barra de búsqueda

Esta sección controla la visibilidad de la barra de búsqueda dentro de su menú superior.

- **Barra de búsqueda:** Un interruptor (Activado/Desactivado) para mostrar u ocultar la barra de búsqueda.
  - *Cuando está habilitado (Activado):* Aparecerá un campo de entrada de búsqueda dentro o cerca de su menú horizontal superior, permitiendo a los clientes buscar productos rápidamente.
  - *Cuando está deshabilitado (Desactivado):* La barra de búsqueda se ocultará del área del menú superior.
  - *Valor recomendado:* "Activado". Una barra de búsqueda es una herramienta de navegación crucial para la mayoría de las tiendas de comercio electrónico, especialmente aquellas con un gran catálogo de productos. Mejora significativamente la experiencia del usuario.
  - *Escenario del comerciante:* Quiere que los clientes encuentren fácilmente productos escribiendo palabras clave. Habilite esta configuración. Si su tienda es muy pequeña con solo unos pocos productos, podría considerar deshabilitarla para ahorrar espacio, pero esto generalmente no se recomienda.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | **Elementos del menú** |  |  |
|  | Etiqueta | N/A | Texto que se muestra para el elemento del menú. |
|  | Enlace | N/A | URL a la que apunta el elemento del menú. |
|  | Nueva ventana | No (para enlaces internos), Sí (para enlaces externos) | Determina si el enlace se abre en una nueva pestaña. |
|  | Reordenación | N/A | Cambia el orden de visualización de los elementos del menú. |
|  | Editar/Eliminar | N/A | Modifica o elimina elementos de menú existentes. |
| Página de configuración del módulo | **Barra de búsqueda** | Activado | Muestra/oculta el campo de entrada de búsqueda en el menú superior. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis cambios en el menú no se muestran en el front office.**
R: Después de realizar cambios en la configuración del módulo, es posible que deba borrar la caché de PrestaShop.
- Vaya a **Parámetros avanzados > Rendimiento**.
- Haga clic en el botón "Borrar caché" en la esquina superior derecha.
- Además, borre la caché de su navegador (Ctrl+F5 o Cmd+R) para asegurarse de que está viendo la última versión de su sitio.

**P2: Los desplegables se ven extraños o no aparecen correctamente con mi tema personalizado.**
R: Este módulo modifica el menú superior estándar de PrestaShop. Los temas personalizados a menudo tienen su propio CSS (estilo) específico para el menú.
- **Solución:** El módulo incluye su propio CSS para habilitar los desplegables. El CSS de su tema podría estar anulándolo o entrando en conflicto. Es posible que necesite un desarrollador web para inspeccionar el CSS y ajustar los estilos de su tema o los estilos del módulo para garantizar la compatibilidad.
- **Verificación temporal:** Intente cambiar temporalmente al tema predeterminado de PrestaShop (por ejemplo, Classic) para ver si los desplegables funcionan allí. Si lo hacen, confirma un conflicto de CSS relacionado con el tema.

**P3: ¿Cómo traduzco las etiquetas de los elementos de mi menú a otros idiomas?**
R: Cuando añada o edite un elemento de menú, verá un selector de idioma junto al campo "Etiqueta".
- Haga clic en el icono de la bandera para cambiar a un idioma diferente.
- Introduzca la etiqueta traducida para ese idioma específico.
- Repita para todos los idiomas que admita su tienda.

**P4: ¿Puedo tener varios niveles de desplegables (por ejemplo, Categoría > Subcategoría > Sub-subcategoría)?**
R: El módulo mejora el menú estándar de PrestaShop, que normalmente admite uno o dos niveles de desplegables de forma eficaz. Aunque técnicamente es posible anidar elementos, demasiados niveles pueden resultar engorrosos para los usuarios.
- **Mejor práctica:** Intente un máximo de dos niveles (elemento principal > elementos desplegables). Para jerarquías más profundas, considere usar páginas de destino de categorías o navegación facetada en las páginas de categorías en lugar de menús desplegables excesivamente complejos.

**P5: La barra de búsqueda está habilitada, pero no aparece.**
R:
- Primero, asegúrese de que la configuración "Barra de búsqueda" en la configuración del módulo esté realmente "Activada".
- Segundo, verifique si su tema tiene un hook o estilo específico para la barra de búsqueda en el encabezado. Algunos temas pueden colocar la barra de búsqueda en una ubicación diferente o requerir una configuración específica dentro del propio tema.
- Si el problema persiste, borre su caché (como se describe en la P1).

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada del módulo "Menú horizontal superior con desplegables" para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura

El módulo `blocktopdropdownmenu` está diseñado como un módulo estándar de PrestaShop, extendiendo principalmente la funcionalidad del módulo central `blocktopmenu` (o su equivalente en versiones más recientes de PS) inyectando JavaScript y CSS personalizados para habilitar el comportamiento de los desplegables. Sigue un patrón MVC clásico de PrestaShop para su configuración, utilizando `getContent()` para el formulario del back-office y registrando hooks para la visualización del front-office. No introduce nuevas tablas de base de datos ni estructuras `ObjectModel` complejas, sino que se basa en valores de `Configuration` para almacenar sus ajustes y aprovecha las entidades existentes de PrestaShop (Categorías, CMS, etc.) para los enlaces de los elementos del menú.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la configuración se gestiona dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase PHP personalizada o definiciones de `ObjectModel` en el directorio `classes/`. Toda la lógica está contenida dentro del archivo principal `blocktopdropdownmenu.php`.

### 4.4 Activos JavaScript (`views/js/`)

El módulo depende en gran medida de JavaScript para crear la funcionalidad del menú desplegable.

- `blocktopdropdownmenu/js/blocktopdropdownmenu.js`
  - **Alcance:** Front-office.
  - **Responsabilidad:** Este es el script de inicialización principal para el menú desplegable. Probablemente contiene la lógica para aplicar el plugin Superfish (o una biblioteca desplegable similar) al elemento de navegación principal. Vincula los detectores de eventos para las intenciones de pasar el ratón, maneja la expansión/contracción de los elementos del menú y garantiza la capacidad de respuesta móvil (por ejemplo, convirtiendo el hover en tap para dispositivos táctiles o integrándose con un menú de hamburguesa). También podría contener lógica para el comportamiento de la barra de búsqueda si se carga o alterna dinámicamente.
- `blocktopdropdownmenu/js/hoverIntent.js`
  - **Alcance:** Front-office.
  - **Responsabilidad:** Un plugin de jQuery que intenta determinar la intención del usuario de pasar el ratón sobre un elemento. Ayuda a prevenir el disparo accidental de los desplegables introduciendo un retraso y comprobando el movimiento del ratón, haciendo que el menú se sienta más suave y menos "parpadeante". Esto suele ser una dependencia de Superfish.
- `blocktopdropdownmenu/js/superfish-modified.js`
  - **Alcance:** Front-office.
  - **Responsabilidad:** Es probable que sea una versión modificada del popular plugin Superfish jQuery, que está diseñado para crear menús desplegables de varios niveles. Maneja la mecánica central de mostrar y ocultar submenús al pasar el ratón, gestionando animaciones y potencialmente añadiendo características de accesibilidad. El sufijo "modified" sugiere que podría incluir adaptaciones personalizadas para la estructura DOM de PrestaShop o la compatibilidad con temas específicos.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo proporciona estilos para presentar visualmente los menús desplegables.

- `blocktopdropdownmenu/css/blocktopdropdownmenu.css`
  - **Alcance:** Estilo del cliente del Front-office.
  - **Responsabilidad:** Contiene reglas CSS personalizadas específicas de este módulo, que potencialmente anulan los estilos predeterminados del tema o añaden nuevos estilos para elementos como la barra de búsqueda, estados específicos de los elementos del menú o ajustes generales de diseño para los desplegables.
  - **Selectores de clase CSS clave:** Los desarrolladores deben inspeccionar este archivo en busca de clases como `.sf-menu`, `.sf-menu li`, `.sf-menu li ul`, `.sf-menu li li`, etc., que son selectores comunes de Superfish, así como cualquier clase personalizada introducida por el módulo.
- `blocktopdropdownmenu/css/superfish-modified.css`
  - **Alcance:** Estilo del cliente del Front-office.
  - **Responsabilidad:** Proporciona el estilo visual base para la estructura del menú desplegable Superfish. Esto incluye estilos para el espaciado de los elementos del menú, colores de fondo, colores de texto, efectos de hover, indicadores de flecha desplegable y el posicionamiento de los paneles desplegables. Es crucial para la apariencia visual del menú de varios niveles.
  - **Selectores de clase CSS clave:** Similar a `blocktopdropdownmenu.css`, este archivo contendrá selectores principales de Superfish. Los desarrolladores pueden anularlos en el `custom.css` o `theme.css` de su tema para que coincidan con la estética de su marca.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- `blocktopdropdownmenu/blocktopdropdownmenu.tpl`
  - **Alcance:** Plantilla de hook.
  - **Hook:** `displayTop` (y potencialmente `displayNav` si la estructura del tema lo permite).
  - **Responsabilidad:** Esta es la plantilla principal del front-office responsable de renderizar la estructura HTML del menú horizontal superior, incluyendo los elementos del menú principal y sus desplegables anidados. Itera a través de los elementos del menú configurados en el back office y genera la estructura `<ul><li>` requerida por el JavaScript de Superfish. También incluye la lógica para renderizar la barra de búsqueda si está habilitada.
- `blocktopdropdownmenu/views/templates/admin/advert.tpl`
  - **Alcance:** Plantilla de administración.
  - **Responsabilidad:** Probablemente muestra un anuncio o mensaje promocional de MyPresta.eu dentro de la página de configuración del módulo en el Back Office.
- `blocktopdropdownmenu/views/templates/admin/_configure/helpers/form/form.tpl`
  - **Alcance:** Plantilla de administración.
  - **Responsabilidad:** Esta plantilla es una plantilla de ayuda estándar de PrestaShop utilizada para renderizar el formulario de configuración principal del módulo. Define la estructura y los campos para gestionar los elementos del menú y la configuración de la barra de búsqueda, tal como se configura en `getContent()`.
- `blocktopdropdownmenu/views/templates/admin/_configure/helpers/list/list_content.tpl`
  - **Alcance:** Plantilla de administración.
  - **Responsabilidad:** Esta plantilla es una plantilla de ayuda estándar de PrestaShop utilizada para renderizar la lista de elementos del menú dentro del formulario de configuración, permitiendo la reordenación, edición y eliminación mediante arrastrar y soltar.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo no crea ninguna tabla de base de datos personalizada.
  - La configuración (por ejemplo, `MOD_blocktopdropdownmenu_ITEMS`, `MOD_blocktopdropdownmenu_SEARCH`) se almacena en la tabla `ps_configuration`. `MOD_blocktopdropdownmenu_ITEMS` almacenará un array serializado o una cadena JSON que representa la estructura del menú.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyecta los activos CSS y JavaScript (`blocktopdropdownmenu.js`, `hoverIntent.js`, `superfish-modified.js`, `blocktopdropdownmenu.css`, `superfish-modified.css`) necesarios para la funcionalidad desplegable. |
| `displayTop` | Típicamente en el área del encabezado principal del tema. | Renderiza la estructura HTML principal del menú horizontal con desplegables y la barra de búsqueda. |
| `displayNav` | A menudo en la barra de navegación superior (encima de `displayTop`). | Puede ser utilizado por algunos temas para mostrar el menú, o para elementos de navegación adicionales. El módulo podría registrarse aquí para una mayor compatibilidad con el tema. |
| `actionObjectProductUpdateAfter` | Después de que se actualiza un producto. | Potencialmente utilizado para borrar la caché del módulo relacionada con los enlaces de productos, asegurando que los elementos del menú que enlazan a productos estén actualizados. |
| `actionObjectProductDeleteAfter` | Después de que se elimina un producto. | Potencialmente utilizado para borrar la caché del módulo o eliminar elementos del menú que enlazan al producto eliminado. |
| `actionObjectManufacturerAddAfter` | Después de que se añade un fabricante. | Potencialmente utilizado para borrar la caché del módulo relacionada con los enlaces de fabricantes. |
| `actionObjectManufacturerUpdateAfter` | Después de que se actualiza un fabricante. | Potencialmente utilizado para borrar la caché del módulo relacionada con los enlaces de fabricantes. |
| `actionObjectManufacturerDeleteAfter` | Después de que se elimina un fabricante. | Potencialmente utilizado para borrar la caché del módulo o eliminar elementos del menú que enlazan al fabricante eliminado. |
| `actionObjectSupplierAddAfter` | Después de que se añade un proveedor. | Potencialmente utilizado para borrar la caché del módulo relacionada con los enlaces de proveedores. |
| `actionObjectSupplierUpdateAfter` | Después de que se actualiza un proveedor. | Potencialmente utilizado para borrar la caché del módulo relacionada con los enlaces de proveedores. |
| `actionObjectSupplierDeleteAfter` | Después de que se elimina un proveedor. | Potencialmente utilizado para borrar la caché del módulo o eliminar elementos del menú que enlazan al proveedor eliminado. |
| `actionObjectCmsAddAfter` | Después de que se añade una página CMS. | Potencialmente utilizado para borrar la caché del módulo relacionada con los enlaces de páginas CMS. |
| `actionObjectCmsUpdateAfter` | Después de que se actualiza una página CMS. | Potencialmente utilizado para borrar la caché del módulo relacionada con los enlaces de páginas CMS. |
| `actionObjectCmsDeleteAfter` | Después de que se elimina una página CMS. | Potencialmente utilizado para borrar la caché del módulo o eliminar elementos del menú que enlazan a la página CMS eliminada. |
| `actionShopDataDuplication` | Cuando se duplica una tienda (en contexto multitienda). | Asegura que la configuración del módulo (elementos del menú, configuración de la barra de búsqueda) se duplique correctamente para la nueva tienda. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Menú horizontal superior con desplegables", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con la funcionalidad y compatibilidad del módulo.

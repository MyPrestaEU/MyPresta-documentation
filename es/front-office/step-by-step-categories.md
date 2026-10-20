---
title: "Paso a paso - categorías - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Paso a paso - categorías' de MyPresta.eu."
sidebar:
  label: "Paso a paso - categorías - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Step by step - categories en MyPresta.eu](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/step-by-step-categories/)
>
> ---


# Paso a paso - categorías

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No hay requisitos especiales de servidor más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la pantalla de configuración principal de "Paso a paso - categorías". Aquí es donde controla cómo se comporta y aparece el módulo en su tienda.

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo del comerciante |
| --- | --- | --- | --- | --- |
| **Mostrar bloque en la cabecera** | Controla si la navegación por categorías paso a paso aparece en la sección de cabecera de su tienda. | *Cuando está habilitado:* Los desplegables de categorías serán visibles en la parte superior de su sitio web, a menudo cerca del logotipo o la navegación principal. Esto proporciona acceso inmediato al filtrado de categorías. *Cuando está deshabilitado:* El bloque no aparecerá en la cabecera. | **SÍ** (si desea una navegación prominente) | Desea que los clientes encuentren fácilmente productos desde cualquier página, por lo que colocarlo en la cabecera lo hace siempre accesible. |
| **Mostrar bloque en la columna izquierda** | Controla si la navegación por categorías paso a paso aparece en la barra lateral izquierda de su tienda. | *Cuando está habilitado:* Los desplegables de categorías serán visibles en la columna izquierda de su sitio web (si su tema admite una columna izquierda). Esta es una ubicación tradicional para los filtros de categorías. *Cuando está deshabilitado:* El bloque no aparecerá en la columna izquierda. | **SÍ** (si su tema tiene una columna izquierda y desea navegación en la barra lateral) | Su tema tiene una barra lateral izquierda y prefiere mantener los elementos de navegación organizados allí, de forma similar a un árbol de categorías estándar. |
| **Mostrar bloque en la columna derecha** | Controla si la navegación por categorías paso a paso aparece en la barra lateral derecha de su tienda. | *Cuando está habilitado:* Los desplegables de categorías serán visibles en la columna derecha de su sitio web (si su tema admite una columna derecha). *Cuando está deshabilitado:* El bloque no aparecerá en la columna derecha. | **NO** (a menos que su tema utilice específicamente una columna derecha para la navegación) | Su tema utiliza la columna derecha para información suplementaria y desea colocar la navegación por categorías allí en lugar de la izquierda. |
| **Mostrar bloque en el pie de página** | Controla si la navegación por categorías paso a paso aparece en la sección del pie de página de su tienda. | *Cuando está habilitado:* Los desplegables de categorías serán visibles en la parte inferior de su sitio web. Esto es menos común para la navegación principal, pero puede ser útil para un acceso secundario. *Cuando está deshabilitado:* El bloque no aparecerá en el pie de página. | **NO** (a menos que sea por razones de diseño específicas) | Tiene una cabecera y columnas muy minimalistas, y desea ofrecer navegación por categorías en el pie de página como una alternativa para los usuarios que se desplazan hacia abajo. |
| **Mostrar bloque en la página de producto** | Controla si la navegación por categorías paso a paso aparece en las páginas de productos individuales. | *Cuando está habilitado:* Los desplegables de categorías serán visibles en las páginas de detalles del producto. Esto puede ayudar a los clientes a explorar otras categorías o productos relacionados. *Cuando está deshabilitado:* El bloque no aparecerá en las páginas de productos. | **NO** (a menos que tenga una necesidad específica para ello allí) | Desea animar a los clientes que ven un producto a saltar fácilmente a otras categorías sin salir de la página del producto, quizás para comparar artículos. |
| **Mostrar botón "Ir"** | Determina si se muestra un botón "Ir" o "Buscar" junto al último desplegable de categorías. | *Cuando está habilitado:* Aparecerá un botón. Los clientes deben hacer clic en este botón para ser redirigidos a la página de la categoría seleccionada. *Cuando está deshabilitado:* Los clientes son redirigidos automáticamente a la página de la categoría seleccionada tan pronto como realizan la selección final en el último desplegable. | **SÍ** (para más control) | Desea que los clientes confirmen su selección de categoría antes de ser redirigidos, dándoles la oportunidad de revisar su elección. |
| **Número de desplegables** | Establece el número máximo de niveles de categoría (profundidad) que se mostrarán como desplegables. | *Cuando se establece en 1:* Solo las categorías de nivel superior aparecerán en un desplegable. *Cuando se establece en 3:* Se mostrarán hasta tres niveles de categorías (por ejemplo, Categoría principal > Subcategoría 1 > Subcategoría 2) en desplegables separados. | **3** (o según la profundidad de su categoría) | Su tienda tiene categorías anidadas hasta 3 o 4 niveles de profundidad, y desea que los clientes puedan profundizar de manera eficiente. |
| **Categoría raíz** | Especifica el punto de partida para la navegación por categorías. Solo se mostrarán las categorías dentro de esta raíz. | *Cuando se establece en "Inicio":* Todas las categorías, comenzando desde la parte superior de su catálogo, estarán disponibles. *Cuando se establece en "Electrónica":* Solo se mostrarán las categorías bajo "Electrónica" (por ejemplo, "Portátiles", "Smartphones") en los desplegables. | **Inicio** (a menos que desee restringir la navegación) | Solo desea ofrecer navegación paso a paso para una parte específica de su catálogo, como "Ropa", y excluir otras secciones como "Hogar y Jardín". |

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Mostrar bloque en la cabecera | SÍ | Muestra los desplegables de categorías en la cabecera de la tienda para una navegación prominente. |
| Configuración del módulo | Mostrar bloque en la columna izquierda | SÍ | Muestra los desplegables de categorías en la barra lateral izquierda para una navegación tradicional. |
| Configuración del módulo | Mostrar bloque en la columna derecha | NO | Muestra los desplegables de categorías en la barra lateral derecha. |
| Configuración del módulo | Mostrar bloque en el pie de página | NO | Muestra los desplegables de categorías en el pie de página de la tienda. |
| Configuración del módulo | Mostrar bloque en la página de producto | NO | Muestra los desplegables de categorías en las páginas de detalles del producto. |
| Configuración del módulo | Mostrar botón "Ir" | SÍ | Requiere que los clientes hagan clic en un botón para navegar a la categoría seleccionada. |
| Configuración del módulo | Número de desplegables | 3 | Establece la profundidad máxima de los niveles de categoría mostrados. |
| Configuración del módulo | Categoría raíz | Inicio | Define el punto de partida para la navegación por categorías. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: El módulo está instalado, pero no veo los desplegables en mi tienda.**
R1:

- **Verifique la configuración:** Vaya a **Módulos > Gestor de módulos > Paso a paso - categorías > Configurar**. Asegúrese de que al menos una opción "Mostrar bloque en..." (por ejemplo, "Mostrar bloque en la cabecera", "Mostrar bloque en la columna izquierda") esté configurada en **SÍ**.
- **Borrar caché:** PrestaShop a menudo almacena contenido en caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
- **Compatibilidad del tema:** Algunos temas altamente personalizados pueden requerir pequeños ajustes. Si borrar la caché no ayuda, intente cambiar temporalmente al tema predeterminado de PrestaShop para ver si aparece el módulo. Si lo hace, su tema podría estar anulando las posiciones de los hooks estándar.

**P2: Los desplegables aparecen, pero no se actualizan cuando selecciono una categoría.**
R2:

- **Problemas de AJAX:** Esto suele indicar un error de JavaScript. Abra la consola de desarrollador de su navegador (F12) y busque cualquier error en la pestaña "Consola".
- **JavaScript en conflicto:** Otro módulo o el JavaScript de su tema podría estar interfiriendo. Intente deshabilitar otros módulos del front-office uno por uno para identificar conflictos.
- **Archivos del módulo:** Asegúrese de que todos los archivos del módulo se hayan subido correctamente y no estén dañados. Volver a subir el módulo podría resolver esto.

**P3: ¿Cómo cambio el estilo (colores, fuentes, tamaño) de los desplegables?**
R3:

- El módulo utiliza CSS estándar. Necesitará conocimientos básicos de CSS o un webmaster.
- Los archivos CSS del módulo (por ejemplo, `sbs-block.css`, `sbs-header.css`) definen los estilos predeterminados.
- **Mejor práctica:** NO modifique los archivos CSS del módulo directamente, ya que sus cambios se perderán durante las actualizaciones. En su lugar, utilice el archivo CSS personalizado de su tema (a menudo encontrado en `themes/yourtheme/assets/css/custom.css` o similar) para anular los estilos del módulo. Utilice el inspector de su navegador (F12) para identificar las clases CSS utilizadas por los desplegables.

**P4: Mis categorías son muy profundas, pero solo veo unos pocos desplegables.**
R4:

- **Configuración "Número de desplegables":** Vaya a **Módulos > Gestor de módulos > Paso a paso - categorías > Configurar** y ajuste la configuración "Número de desplegables". Aumente este valor para que coincida con la profundidad máxima de categorías que desea mostrar. Recuerde que mostrar demasiados desplegables podría saturar la interfaz.

**P5: El módulo muestra categorías que no quiero incluir en la navegación paso a paso.**
R5:

- **Configuración "Categoría raíz":** En la configuración del módulo, utilice la configuración "Categoría raíz". Seleccione una categoría padre específica desde la cual desea que comience la navegación paso a paso. Solo se mostrarán las categorías y subcategorías bajo la raíz elegida.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Paso a paso - categorías" es principalmente una característica del front-office que aprovecha la arquitectura de módulos de PrestaShop. Utiliza una clase `Module` estándar para la instalación y configuración, y clases `ModuleFrontController` para manejar las solicitudes AJAX para la carga dinámica de categorías. No introduce clases `ObjectModel` personalizadas ni tablas de base de datos, basándose en el objeto `Category` nativo de PrestaShop para los datos. El módulo utiliza en gran medida las plantillas Smarty para la renderización y JavaScript para la funcionalidad AJAX interactiva.

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**:
  - `controllers/front/ajaxload.php`
    - Nombre de la clase: `StepbystepAjaxloadModuleFrontController`
    - Clase padre: `ModuleFrontController`
    - Responsabilidad: Este controlador es el núcleo de la funcionalidad AJAX. Responde a las solicitudes del JavaScript del front-office para obtener subcategorías basadas en un ID de categoría padre. Normalmente devuelve datos JSON que contienen nombres e IDs de categorías para rellenar los desplegables posteriores.
  - `controllers/front/index.php`
    - Nombre de la clase: `StepbystepIndexModuleFrontController`
    - Clase padre: `ModuleFrontController`
    - Responsabilidad: Este controlador probablemente sirve como punto de entrada predeterminado o de reserva para el enrutamiento del front-office del módulo, aunque su función principal podría ser mínima dada la naturaleza impulsada por AJAX. Podría manejar la lógica de visualización inicial o la redirección si el módulo tuviera una página dedicada.
  - `controllers/front/tree.php`
    - Nombre de la clase: `StepbystepTreeModuleFrontController`
    - Clase padre: `ModuleFrontController`
    - Responsabilidad: Este controlador podría ser responsable de renderizar una estructura de árbol de categorías completa, potencialmente para depuración o un método de visualización alternativo, aunque la característica principal del módulo son los desplegables. También podría usarse para generar los datos iniciales para el primer desplegable.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no contiene ninguna clase personalizada en el directorio `classes/`. Utiliza directamente la clase `Category` principal de PrestaShop y otras funciones de ayuda para recuperar datos de categorías.

### 4.4 Activos de JavaScript (`views/js/`)

- `stepbystep/js/advajax.js`
  - Alcance: Front-office
  - Este es el archivo JavaScript principal responsable del comportamiento interactivo del módulo.
  - Vincula los escuchadores de eventos a los elementos `<select>` desplegables de categorías.
  - Cuando se realiza una selección en un desplegable, activa una solicitud AJAX (probablemente a `ajaxload.php`) para obtener el siguiente nivel de subcategorías.
  - Crea y rellena dinámicamente los desplegables posteriores con los datos recibidos.
  - Maneja la redirección a la página de categoría final cuando se realiza una selección o se hace clic en el botón "Ir".
  - Gestiona la visibilidad y el estado de los desplegables en función de la interacción del usuario y la configuración del módulo (por ejemplo, "Número de desplegables").

### 4.5 Hojas de estilo CSS (`views/css/`)

- `stepbystep/css/sbs-block.css`
  - Alcance: Estilo del cliente del Front-office
  - Estiliza la apariencia general del bloque de categorías paso a paso, incluyendo el relleno, los márgenes y el diseño general cuando se coloca en columnas u otras posiciones similares a bloques.
  - Selectores clave: `.sbs-block`, `.sbs-category-select-wrapper`
- `stepbystep/css/sbs-header.css`
  - Alcance: Estilo del cliente del Front-office
  - Estiliza específicamente el módulo cuando está enganchado en la posición `displayHeader`, ajustando potencialmente los diseños de la cabecera (por ejemplo, visualización en línea, anchos específicos).
  - Selectores clave: `.sbs-header-container`
- `stepbystep/css/sbs-top.css`
  - Alcance: Estilo del cliente del Front-office
  - Probablemente estiliza el módulo cuando está enganchado en `displayTop` o posiciones similares en la parte superior de la página, similar a `sbs-header.css` pero para diferentes contextos visuales.
  - Selectores clave: `.sbs-top-container`
- `stepbystep/css.css`
  - Alcance: Estilo del cliente del Front-office
  - Una hoja de estilo general que podría contener estilos comunes aplicables a todas las ubicaciones o estilos de reserva.
  - Selectores clave: `.sbs-select`, `.sbs-go-button`

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:

  - `block.tpl`: Esta plantilla probablemente se usa cuando el módulo está enganchado en `displayLeftColumn` o `displayRightColumn`. Renderiza los desplegables paso a paso dentro de una estructura de bloque estándar de PrestaShop.
  - `blockSbs.tpl`: Esta podría ser una plantilla de bloque alternativa o más genérica, potencialmente utilizada para otros hooks de columna o ubicaciones personalizadas específicas.
  - `displaySearch.tpl`: Esta plantilla podría estar destinada a la integración cerca de una barra de búsqueda o como parte de un hook relacionado con la búsqueda, proporcionando los desplegables como una herramienta de refinamiento de búsqueda.
  - `header.tpl`: Esta plantilla se usa cuando el módulo está enganchado en `displayHeader`. Renderiza los desplegables dentro de la sección de cabecera de la tienda.
  - `top.tpl`: Esta plantilla se usa cuando el módulo está enganchado en `displayTop`. Similar a `header.tpl`, pero para el hook `displayTop`, que a menudo se usa para la barra de navegación principal.
- **Plantillas de administración (`views/templates/admin/`)**: Ninguna identificada. La configuración se maneja directamente en `getContent()`.
- **Plantillas del Front-office (`views/templates/front/`)**: Ninguna identificada como páginas independientes.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: El módulo no crea ninguna tabla SQL personalizada. Almacena sus configuraciones en la tabla `ps_configuration` de PrestaShop utilizando claves como `STEPMYSTEP_HEADER`, `STEPMYSTEP_LEFT`, `STEPMYSTEP_RIGHT`, `STEPMYSTEP_FOOTER`, `STEPMYSTEP_PRODUCT`, `STEPMYSTEP_GO_BUTTON`, `STEPMYSTEP_DROPDOWNS`, `STEPMYSTEP_ROOT_CATEGORY`.
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Renderiza contenido dentro de la sección `<head>` del HTML, o en la parte superior del `<body>` antes de otro contenido. | Inyecta activos CSS/JS y potencialmente la estructura HTML del módulo si está configurado para la visualización en la cabecera. |
| `displayLeftColumn` | Renderiza contenido en la barra lateral izquierda de la tienda. | Muestra los desplegables de categorías paso a paso en la columna izquierda. |
| `displayRightColumn` | Renderiza contenido en la barra lateral derecha de la tienda. | Muestra los desplegables de categorías paso a paso en la columna derecha. |
| `displayFooter` | Renderiza contenido en la sección del pie de página de la tienda. | Muestra los desplegables de categorías paso a paso en el pie de página. |
| `displayProductAdditionalInfo` (o hook similar de página de producto) | Renderiza contenido en la página del producto, a menudo debajo de la descripción del producto o en un bloque específico. | Muestra los desplegables de categorías paso a paso en las páginas de productos. |
| `displayTop` | Renderiza contenido en la sección superior de la página, típicamente encima o dentro de la navegación principal. | Muestra los desplegables de categorías paso a paso en la barra superior. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Paso a paso - categorías", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.

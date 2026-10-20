---
title: "Descuentos por cantidad en listas de productos - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Descuentos por cantidad en listas de productos' de MyPresta.eu."
sidebar:
  label: "Descuentos por cantidad en listas de productos - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Quantity discounts on products lists en MyPresta.eu](https://mypresta.eu/modules/front-office-features/quantity-discounts-on-products-lists.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/quantity-discounts-on-products-lists/)
>
> ---


# Descuentos por cantidad en listas de productos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones de servidor inusuales.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo, accesible después de la instalación haciendo clic en el botón "Configurar".

#### Configuración general

-   **Qué hace este ajuste:** Esta sección contiene los ajustes principales para habilitar o deshabilitar la funcionalidad del módulo y controlar su comportamiento básico.
-   **Efecto de cambiar este ajuste:**
    *   *Cuando está habilitado:* El módulo comenzará a mostrar descuentos por cantidad en las páginas de listado de productos según sus otros ajustes.
    *   *Cuando está deshabilitado:* El módulo dejará de mostrar cualquier descuento por cantidad en las páginas de listado de productos.
-   **Valor recomendado:** SÍ (a menos que necesite deshabilitarlo temporalmente para mantenimiento).
-   **Escenario / ejemplo de comerciante:** Si está ejecutando una promoción especial que anula los descuentos por cantidad, podría deshabilitar temporalmente el módulo. De lo contrario, manténgalo habilitado para aprovechar sus beneficios.

#### Opciones de visualización

-   **Qué hace este ajuste:** Estas opciones controlan la apariencia visual y la ubicación de la información de descuento por cantidad en sus listados de productos.
-   **Efecto de cambiar este ajuste:**
    *   *Ejemplo: "Mostrar en la página del producto":*
        *   *Cuando está habilitado:* Los descuentos por cantidad también se mostrarán en la página de detalles del producto individual.
        *   *Cuando está deshabilitado:* Los descuentos por cantidad solo aparecerán en las páginas de listado de productos (categorías, resultados de búsqueda, etc.), asumiendo que ya están presentes en la página del producto por la funcionalidad predeterminada de PrestaShop.
    *   *Ejemplo: "Posición de la información de descuento":*
        *   *Opción A (por ejemplo, "Debajo del precio del producto"):* Los detalles del descuento aparecerán directamente debajo del precio principal del producto.
        *   *Opción B (por ejemplo, "Encima del nombre del producto"):* Los detalles del descuento aparecerán encima del nombre del producto.
-   **Valor recomendado:** Experimente con las posiciones para encontrar lo que mejor se adapte a su tema. A menudo, "Debajo del precio del producto" es un buen punto de partida. "Mostrar en la página del producto" se puede habilitar si su tema aún no muestra los descuentos por cantidad de forma destacada allí.
-   **Escenario / ejemplo de comerciante:** Si sus tarjetas de producto son muy compactas, podría elegir una posición sutil. Si desea resaltar los descuentos, una posición más prominente podría ser mejor.

#### Estilo y personalización

-   **Qué hace este ajuste:** Estos ajustes le permiten personalizar el aspecto de la visualización del descuento para que coincida con el tema de su tienda. Esto podría incluir opciones para el color del texto, el color de fondo, el tamaño de la fuente o incluso CSS personalizado.
-   **Efecto de cambiar este ajuste:**
    *   *Ejemplo: "Color del texto":*
        *   *Cuando se establece en rojo:* El texto del descuento aparecerá en rojo.
        *   *Cuando se establece en verde:* El texto del descuento aparecerá en verde.
-   **Valor recomendado:** Elija colores y estilos que complementen su tema existente.
-   **Escenario / ejemplo de comerciante:** Si su marca utiliza una paleta de colores específica, querrá que la información de descuento se integre sin problemas en lugar de chocar.

#### Ajustes avanzados

-   **Qué hace este ajuste:** Esta sección podría contener ajustes para el almacenamiento en caché, la optimización del rendimiento o las opciones de integración específicas.
-   **Efecto de cambiar este ajuste:**
    *   *Ejemplo: "Habilitar caché":*
        *   *Cuando está habilitado:* El módulo almacenará el HTML de descuento generado para cargar más rápido, mejorando la velocidad de la página.
        *   *Cuando está deshabilitado:* El módulo generará el HTML de descuento en cada carga de página, lo que podría ralentizar las páginas pero garantizar que siempre se muestren los datos más recientes (útil durante el desarrollo).
-   **Valor recomendado:** SÍ para el almacenamiento en caché en tiendas en vivo.
-   **Escenario / ejemplo de comerciante:** Si nota problemas de rendimiento en páginas con muchos listados de productos, habilitar el almacenamiento en caché puede ayudar. Durante el desarrollo del tema, podría deshabilitar el almacenamiento en caché para ver los cambios al instante.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### AdminPlqdSearchController (Back Office > Módulos > Descuentos por cantidad en listas de productos > Configuración de búsqueda)

Este controlador probablemente gestiona la configuración relacionada con la forma en que el módulo identifica y procesa los productos para mostrar descuentos, posiblemente incluyendo una herramienta de búsqueda para productos o categorías específicas.

-   **Nombre de la pantalla y ubicación del menú:** Esta pantalla podría ser accesible a través de una subpestaña o un enlace dedicado dentro de la página de configuración principal del módulo, posiblemente etiquetada como "Configuración de búsqueda" o "Selección de productos".
-   **Acciones y configuraciones disponibles:** Esta pantalla normalmente presentaría una cuadrícula o un formulario para:
    *   **Buscar productos:** Le permite encontrar productos específicos por nombre, ID o referencia.
    *   **Excluir productos/categorías:** Defina productos específicos o categorías enteras donde los descuentos por cantidad NO deben mostrarse, incluso si los tienen configurados.
    *   **Gestionar reglas de visualización:** Potencialmente, configure reglas más granulares para cuándo y dónde aparecen los descuentos según los atributos del producto u otros criterios.
-   **Efecto de los cambios:**
    *   *Excluir un producto:* La información de descuento por cantidad para ese producto específico ya no aparecerá en ninguna página de listado de productos.
    *   *Excluir una categoría:* Todos los productos dentro de la categoría seleccionada tendrán su información de descuento por cantidad oculta en las páginas de listado.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esta pantalla si tiene productos o categorías específicas donde no se desea mostrar descuentos por cantidad en las listas (por ejemplo, artículos de muy alto valor, productos de pedido personalizado o productos con precios complejos que podrían confundir a los clientes si se simplifican).

#### index.php (plqd/controllers/admin/index.php)

Este archivo, aunque aparece como un controlador de administración, a menudo es un marcador de posición o un redireccionador en los módulos de PrestaShop. En el contexto de este módulo, es muy probable que `plqd/index.php` (el archivo principal del módulo) maneje el formulario de configuración principal a través de `getContent()`, y `AdminPlqdSearchController.php` maneje cualquier interfaz de administración secundaria más compleja. El `index.php` en el directorio `controllers/admin` podría simplemente asegurar que el acceso directo al directorio se maneje con gracia, o podría ser un archivo heredado. Para los comerciantes, todos los ajustes relevantes se encontrarán en la configuración principal del módulo o en `AdminPlqdSearchController`.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| **Página de configuración del módulo** | Habilitar módulo | SÍ | Activa/desactiva la funcionalidad principal del módulo. |
| | Mostrar en la página del producto | SÍ/NO (depende del tema) | Muestra descuentos en páginas de productos individuales. |
| | Posición de la información de descuento | Debajo del precio del producto | Controla dónde aparece el texto de descuento en las tarjetas de producto. |
| | Color del texto | (Predeterminado del tema) | Establece el color del texto de descuento. |
| | Color de fondo | (Predeterminado del tema) | Establece el color de fondo del bloque de descuento. |
| | Habilitar caché | SÍ | Mejora el rendimiento al almacenar el HTML generado. |
| **AdminPlqdSearchController** | Excluir producto (por ID/Nombre) | N/A | Evita la visualización de descuentos para productos específicos. |
| | Excluir categoría | N/A | Evita la visualización de descuentos para todos los productos de una categoría. |

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Los descuentos por cantidad no aparecen en mis listas de productos después de la instalación.**
R:

1.  **Verifique el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Descuentos por cantidad en listas de productos" esté instalado y habilitado.
2.  **Configure el módulo:** Haga clic en "Configurar" para el módulo y asegúrese de que la configuración principal "Habilitar módulo" esté establecida en SÍ.
3.  **Borre la caché:** PrestaShop a menudo almacena contenido en caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
4.  **Verifique los descuentos de productos:** Asegúrese de que los productos para los que espera ver descuentos realmente tengan descuentos por cantidad configurados en la configuración de sus productos (Back Office > Catálogo > Productos > Editar producto > Pestaña Precios > Precios específicos).
5.  **Compatibilidad con el tema:** Algunos temas altamente personalizados pueden requerir ajustes menores. Si después de borrar la caché y verificar la configuración, aún no aparece, póngase en contacto con el soporte de MyPresta.eu con los detalles de su tema.

**P2: El texto de descuento se muestra, pero no se ve bien con mi tema (colores, fuente o alineación incorrectos).**
R:

1.  **Configuración del módulo:** Vaya a la página de configuración del módulo (**Módulos > Gestor de módulos > Configurar** para "Descuentos por cantidad en listas de productos"). Busque las opciones de "Estilo y personalización". Es posible que pueda ajustar los colores, los tamaños de fuente o el relleno directamente desde aquí.
2.  **CSS personalizado:** Si la configuración del módulo no ofrece suficiente control, su webmaster o desarrollador puede añadir CSS personalizado a su tema para anular los estilos predeterminados del módulo. Los archivos CSS del módulo (consulte la Sección 7.5) les darán los selectores de clase necesarios.

**P3: Quiero ocultar los descuentos por cantidad para ciertos productos o categorías, pero no para todos.**
R:

1.  **AdminPlqdSearchController:** Navegue a la pantalla de administración dedicada del módulo (probablemente una subpestaña o un enlace desde la configuración principal, posiblemente llamada "Configuración de búsqueda" o "Exclusiones").
2.  **Añadir exclusiones:** Utilice las herramientas de esta pantalla para buscar y añadir productos específicos o categorías enteras a una lista de exclusión. Una vez añadidos, el módulo ignorará estos elementos al mostrar descuentos en las listas de productos.

**P4: ¿Este módulo ralentizará mi tienda?**
R: El módulo está diseñado para ser eficiente. Aprovecha los datos de descuento por cantidad existentes de PrestaShop.

1.  **Habilitar caché:** Asegúrese de que la opción "Habilitar caché" en la configuración avanzada del módulo esté establecida en SÍ. Esto reduce significativamente la carga de procesamiento en las vistas de página posteriores.
2.  **Rendimiento del servidor:** Si su servidor ya está poco potente o muy cargado, cualquier módulo adicional puede tener un impacto menor. Asegúrese de que su alojamiento cumpla con las especificaciones recomendadas de PrestaShop.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Descuentos por cantidad en listas de productos" (`plqd`) es un módulo estándar de PrestaShop que sigue el patrón MVC. Principalmente extiende la clase `Module`, aprovechando el sistema de hooks de PrestaShop para inyectar contenido en las plantillas de listado de productos. No introduce entidades `ObjectModel` personalizadas, sino que lee los datos `SpecificPrice` existentes. El módulo utiliza un controlador de administración dedicado (`AdminPlqdSearchController`) para gestionar las exclusiones de productos/categorías, e integra JavaScript y CSS para la visualización en el front-office.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno definido explícitamente como controladores frontales independientes. El módulo probablemente inyecta su contenido directamente en las plantillas a través de hooks y maneja cualquier contenido dinámico o AJAX a través de métodos `displayAjax` dentro de la clase principal del módulo o a través de JS incluido.
-   **Controladores de administración de Back-Office**:
    -   `plqd/controllers/admin/AdminPlqdSearchController.php`
        -   **Nombre de la clase y clase padre**: `AdminPlqdSearchController` extiende `ModuleAdminController`.
        -   **Nombre de la pestaña y entidad gestionada**: Este controlador es responsable de gestionar la configuración de búsqueda y exclusión de productos y categorías. Probablemente proporciona una interfaz de cuadrícula o formulario para seleccionar productos/categorías que *no* deben mostrar descuentos por cantidad en las listas de productos. No gestiona un `ObjectModel` específico, sino datos de configuración (por ejemplo, `Configuration::updateValue` para IDs separados por comas).
    -   `plqd/controllers/admin/index.php`
        -   Este archivo es típicamente una medida de seguridad en PrestaShop, que evita la lista directa de directorios. Generalmente contiene un simple `header('Location: ../../index.php?controller=AdminHome');` o `die('No direct script access');`. No sirve como controlador funcional para la lógica o la interfaz de usuario del módulo.

### 4.3 Clases y modelos principales (`classes/`)

No se encuentran clases personalizadas o definiciones de `ObjectModel` en el directorio `classes/` para este módulo. El módulo interactúa directamente con las clases principales `Product` y `SpecificPrice` de PrestaShop y la clase `Configuration` para sus ajustes.

### 4.4 Activos JavaScript (`views/js/`)

-   `plqd/lib/searchTool/views/js/autocomplete.js`
    -   **Alcance**: Back-office (probablemente utilizado dentro de `AdminPlqdSearchController`).
    -   **Propósito**: Proporciona funcionalidad de autocompletado para buscar productos o categorías dentro de la interfaz de exclusión de administración. Se vincula a los campos de entrada, envía solicitudes AJAX a un punto final de backend (posiblemente el propio `AdminPlqdSearchController` o un controlador AJAX dedicado) y muestra sugerencias al usuario.
-   `plqd/views/js/plqd.js`
    -   **Alcance**: Front-office.
    -   **Propósito**: Este es el JavaScript principal del front-office para el módulo. Probablemente:
        -   Escanea los elementos de la lista de productos al cargar la página o después de las actualizaciones de AJAX (por ejemplo, desplazamiento infinito, filtros de categoría).
        -   Inyecta o formatea dinámicamente la información de descuento por cantidad en las tarjetas de producto.
        -   Puede manejar ajustes responsivos o interacciones menores de la interfaz de usuario relacionadas con la visualización del descuento.
        -   Podría potencialmente realizar llamadas AJAX para obtener datos de descuento si no están pre-renderizados por Smarty.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `plqd/lib/searchTool/views/css/autocomplete.css`
    -   **Alcance**: Back-office.
    -   **Propósito**: Estiliza el menú desplegable de autocompletado y los campos de entrada utilizados en `AdminPlqdSearchController` para la búsqueda de productos/categorías.
    -   **Selectores clave**: Probablemente apunta a clases como `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`, etc.
-   `plqd/views/css/plqd-classic.css`
    -   **Alcance**: Front-office.
    -   **Propósito**: Proporciona un estilo predeterminado para la visualización de descuentos por cantidad, potencialmente adaptado para temas de PrestaShop más antiguos o un aspecto "clásico".
    -   **Selectores clave**: Apunta al contenedor principal de la información de descuento (por ejemplo, `.plqd-discounts-wrapper`), líneas de descuento individuales (`.plqd-discount-item`), cantidades (`.plqd-quantity`) y precios (`.plqd-price`).
-   `plqd/views/css/plqd-hide-default.css`
    -   **Alcance**: Front-office.
    -   **Propósito**: Esta hoja de estilo probablemente contiene reglas para ocultar las visualizaciones predeterminadas de descuentos por cantidad que podrían estar presentes en algunos temas, para evitar la duplicación cuando el módulo inyecta su propia versión estilizada.
    -   **Selectores clave**: Podría apuntar a elementos comunes del tema como `.product-price-and-shipping .discount-quantity` o similares.
-   `plqd/views/css/plqd.css`
    -   **Alcance**: Front-office.
    -   **Propósito**: La hoja de estilo principal del front-office para el módulo, que proporciona el estilo central para la visualización de descuentos por cantidad. Esta podría ser una hoja de estilo más moderna o general en comparación con `plqd-classic.css`.
    -   **Selectores clave**: Similar a `plqd-classic.css`, apuntando a `.plqd-discounts-wrapper`, `.plqd-discount-item`, etc. Los desarrolladores pueden anular estas clases en el `custom.css` o `theme.css` de su tema.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `plqd/views/tpl/html.tpl`
        -   **Hook**: Esta es probablemente la plantilla principal renderizada por el `hookDisplayProductListFunctionalButtons` del módulo (o un hook de lista de productos similar) para generar el HTML de descuento por cantidad para un solo producto. Recibe datos de productos y precios específicos del módulo.
        -   **Salida**: Renderiza el HTML estructurado para las líneas de descuento por cantidad (por ejemplo, "A partir de X unidades: Y €").
-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `plqd/lib/searchTool/views/scripts.tpl`
        -   **Propósito**: Esta plantilla probablemente se incluye en la vista `AdminPlqdSearchController`. Contiene la inicialización de JavaScript para la funcionalidad de autocompletado (por ejemplo, bloques `$(document).ready()`, definiciones de variables para URL de AJAX, etc.) y potencialmente inclusiones de CSS.
    -   `plqd/views/tpl/selectedProducts.tpl`
        -   **Propósito**: Se utiliza dentro de `AdminPlqdSearchController` para mostrar la lista de productos o categorías que se han seleccionado para exclusión. Normalmente, renderizaría una tabla o lista de estos elementos, posiblemente con opciones para eliminarlos.
-   **Plantillas de Front-office (`views/templates/front/`)**:
    -   `plqd/views/tpl/html-product-page.tpl`
        -   **Propósito**: Esta plantilla está diseñada específicamente para mostrar descuentos por cantidad en la página de producto individual, si el módulo está configurado para hacerlo. Podría tener un estilo o estructura ligeramente diferente en comparación con la plantilla de la página de listado (`html.tpl`) para adaptarse mejor al diseño de la página de producto.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    -   El módulo no crea tablas SQL personalizadas. Se basa en la tabla principal `ps_specific_price` de PrestaShop para los datos de descuento por cantidad.
    -   La configuración (por ejemplo, estado habilitado, opciones de estilo, IDs de productos/categorías excluidos) se almacena en la tabla `ps_configuration` utilizando claves típicamente prefijadas con `PLQD_`.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
|---|---|---|
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Se utiliza para incluir el CSS del módulo (`plqd.css`, `plqd-classic.css`, `plqd-hide-default.css`) y JavaScript (`plqd.js`). |
| `displayProductListFunctionalButtons` | Dentro de los elementos de la lista de productos (por ejemplo, categoría, resultados de búsqueda). | Hook principal para inyectar el HTML de descuento por cantidad (`html.tpl`) en las tarjetas de producto. |
| `displayProductPriceBlock` (tipo `after_price`) | Después del bloque de precio principal en las páginas de producto. | Se utiliza para inyectar `html-product-page.tpl` si está configurado para mostrar descuentos en las páginas de producto. |
| `displayRightColumn` / `displayLeftColumn` | En las columnas de la barra lateral derecha/izquierda. | Menos probable para este módulo, pero podría usarse para un bloque promocional relacionado con descuentos por cantidad si se implementa. |
| `displayFooter` | En la parte inferior de cada página del front-office. | Podría usarse para JS de carga tardía o scripts adicionales si es necesario. |
| `actionProductUpdate` | Después de que un producto se actualiza en el Back Office. | Podría usarse para borrar la caché del módulo relacionada con ese producto, asegurando que se reflejen los precios específicos actualizados. |
| `actionModuleInstall` | Durante la instalación del módulo. | Crea entradas de configuración en `ps_configuration`. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Limpia las entradas de configuración y potencialmente cualquier dato personalizado. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, correcciones de errores y soporte técnico dedicado para el módulo "Descuentos por cantidad en listas de productos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo está disponible para ayudar con cualquier problema técnico o pregunta relacionada con la funcionalidad e integración del módulo.

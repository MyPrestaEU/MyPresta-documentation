---
title: "Búsqueda dirigida - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Búsqueda dirigida' de MyPresta.eu."
sidebar:
  label: "Búsqueda dirigida - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Target search en MyPresta.eu](https://mypresta.eu/modules/front-office-features/target-search.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/target-search/)
>
> ---


# Búsqueda dirigida

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones de servidor inusuales.

## 2. Recorrido completo de configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Búsqueda dirigida" para acceder a sus ajustes. Aquí es donde define exactamente dónde debe buscar el motor de búsqueda las palabras clave.

La página de configuración presentará una serie de casillas de verificación, cada una correspondiente a un área específica de los datos de su producto.

-   **Qué hace este ajuste:** Cada casilla de verificación le permite habilitar o deshabilitar la búsqueda dentro de un campo particular de la información de su producto.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está marcada (habilitada):* El motor de búsqueda de PrestaShop incluirá datos de este campo específico al procesar las consultas de los clientes. Por ejemplo, si "Nombre del producto" está marcado, una búsqueda de "vestido" encontrará productos con "vestido" en su nombre.
    -   *Cuando está desmarcada (deshabilitada):* El motor de búsqueda de PrestaShop *ignorará* los datos de este campo. Si "Descripción del producto" no está marcada, un producto no aparecerá en los resultados de búsqueda si el término de búsqueda solo se encuentra dentro de su descripción.
-   **Valor recomendado:** Esto depende completamente de su catálogo de productos y de cómo desea que los clientes encuentren los productos. Un buen punto de partida es habilitar los campos más críticos y luego refinar en función de las pruebas.
-   **Escenario / ejemplo de comerciante:**
    -   **Escenario 1: Productos muy específicos (por ejemplo, piezas electrónicas, libros por ISBN):** Es posible que solo desee buscar en "Nombre del producto", "Referencia" y "EAN13/JAN". Esto garantiza que los clientes encuentren coincidencias exactas rápidamente, evitando resultados irrelevantes de descripciones largas.
    -   **Escenario 2: Artículos de moda o para el hogar (por ejemplo, "vestido rojo"):** Es posible que habilite "Nombre del producto", "Descripción corta", "Descripción larga" y "Etiquetas". Esto permite a los clientes encontrar productos basándose en términos más amplios, colores o estilos mencionados en cualquier parte de los detalles del producto.
    -   **Escenario 3: Productos de marca:** Habilite "Nombre del fabricante" para que los clientes puedan encontrar fácilmente todos los productos de una marca específica escribiendo el nombre de la marca en la barra de búsqueda.

Aquí tiene un desglose de los ajustes típicos que encontrará:

| Ajuste / Opción | Propósito e impacto | Valor recomendado | Escenario de comerciante |
| --- | --- | --- | --- |
| **Buscar en el nombre del producto** | Si está habilitado, las consultas de búsqueda coincidirán con el nombre del producto. | **SÍ** | Esencial para la mayoría de las tiendas. Los clientes a menudo buscan por nombre de producto. |
| **Buscar en la descripción corta del producto** | Si está habilitado, las consultas de búsqueda coincidirán con la descripción corta del producto. | **SÍ** | Útil para encontrar productos basados en características clave o resúmenes. |
| **Buscar en la descripción larga del producto** | Si está habilitado, las consultas de búsqueda coincidirán con la descripción completa y detallada del producto. | **SÍ / NO** | **SÍ** para búsquedas amplias (moda, artículos para el hogar). **NO** para artículos muy específicos (electrónica, piezas) para evitar ruido. |
| **Buscar en la referencia del producto** | Si está habilitado, las consultas de búsqueda coincidirán con el número de referencia interno del producto. | **SÍ / NO** | **SÍ** para B2B, productos técnicos, o si los clientes conocen los números de pieza. **NO** si las referencias son solo internas. |
| **Buscar en el EAN13/JAN del producto** | Si está habilitado, las consultas de búsqueda coincidirán con el código de barras EAN13 o JAN del producto. | **SÍ / NO** | **SÍ** para tiendas donde los clientes puedan buscar por código de barras (por ejemplo, libros, comestibles). |
| **Buscar en el UPC del producto** | Si está habilitado, las consultas de búsqueda coincidirán con el código de barras UPC del producto. | **SÍ / NO** | Similar a EAN13/JAN, para regiones que usan UPC. |
| **Buscar en las etiquetas del producto** | Si está habilitado, las consultas de búsqueda coincidirán con cualquier etiqueta asignada al producto. | **SÍ** | Excelente para mejorar la visibilidad con palabras clave que no están en nombres/descripciones. |
| **Buscar en el nombre del fabricante** | Si está habilitado, las consultas de búsqueda coincidirán con el nombre del fabricante del producto. | **SÍ** | Crucial si los clientes a menudo buscan marcas específicas. |
| **Buscar en el nombre del proveedor** | Si está habilitado, las consultas de búsqueda coincidirán con el nombre del proveedor del producto. | **NO / SÍ** | **NO** para la mayoría de las tiendas B2C. **SÍ** para B2B o tiendas especializadas donde el proveedor es relevante para los clientes. |
| **Buscar en el nombre de la categoría** | Si está habilitado, las consultas de búsqueda coincidirán con el nombre de las categorías a las que pertenece el producto. | **SÍ** | Ayuda a los clientes a encontrar productos por nombre de categoría (por ejemplo, "vestidos" para encontrar productos en la categoría "Vestidos"). |
| **Buscar en el valor de la característica** | Si está habilitado, las consultas de búsqueda coincidirán con los valores de las características del producto (por ejemplo, "rojo" para una característica "Color"). | **SÍ** | Muy recomendado para tiendas con características de producto enriquecidas (por ejemplo, color, tamaño, material). |

**Nota importante:** Después de realizar cualquier cambio en estos ajustes, haga clic siempre en el botón "Guardar". También es una buena práctica borrar la caché de PrestaShop (Parámetros avanzados > Rendimiento) y probar la funcionalidad de búsqueda en su front office para asegurarse de que los cambios se hayan aplicado como se esperaba.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

Este módulo no introduce ninguna pantalla de administración dedicada ni controladores personalizados. Toda la configuración se gestiona directamente dentro de la página de configuración estándar del módulo.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Buscar en el nombre del producto | SÍ | Incluir nombres de productos en la búsqueda. |
| Página de configuración del módulo | Buscar en la descripción corta del producto | SÍ | Incluir descripciones cortas en la búsqueda. |
| Página de configuración del módulo | Buscar en la descripción larga del producto | SÍ / NO | Incluir descripciones completas. |
| Página de configuración del módulo | Buscar en la referencia del producto | SÍ / NO | Incluir números de referencia de productos. |
| Página de configuración del módulo | Buscar en el EAN13/JAN del producto | SÍ / NO | Incluir códigos de barras EAN13/JAN. |
| Página de configuración del módulo | Buscar en el UPC del producto | SÍ / NO | Incluir códigos de barras UPC. |
| Página de configuración del módulo | Buscar en las etiquetas del producto | SÍ | Incluir etiquetas de productos. |
| Página de configuración del módulo | Buscar en el nombre del fabricante | SÍ | Incluir nombres de fabricantes. |
| Página de configuración del módulo | Buscar en el nombre del proveedor | NO / SÍ | Incluir nombres de proveedores. |
| Página de configuración del módulo | Buscar en el nombre de la categoría | SÍ | Incluir nombres de categorías. |
| Página de configuración del módulo | Buscar en el valor de la característica | SÍ | Incluir valores de características de productos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He cambiado la configuración, pero los resultados de búsqueda no han cambiado. ¿Qué pasa?**
R: PrestaShop utiliza el almacenamiento en caché para acelerar su tienda. Después de cambiar la configuración del módulo, a menudo necesita borrar la caché.

-   **Solución:** Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop. Haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Luego, pruebe su búsqueda de nuevo.

**P2: La barra de búsqueda de mi tema personalizado se ve diferente. ¿Seguirá funcionando este módulo?**
R: Sí, el módulo "Búsqueda dirigida" anula principalmente la *lógica* de cómo PrestaShop procesa las consultas de búsqueda, no la apariencia visual de la barra de búsqueda en sí. Debería funcionar sin problemas con la mayoría de los temas personalizados.

-   **Solución:** Si experimenta algún problema visual inesperado o la búsqueda no parece funcionar, podría ser un conflicto raro con la plantilla de búsqueda personalizada de su tema. Póngase en contacto con el soporte de MyPresta.eu con los detalles de su tema.

**P3: ¿Este módulo afecta la optimización para motores de búsqueda (SEO)?**
R: Directamente, no. Este módulo mejora la experiencia de búsqueda *interna* para sus clientes en su sitio web. No afecta directamente cómo los motores de búsqueda externos (como Google) rastrean o clasifican su sitio. Sin embargo, al mejorar la experiencia de búsqueda en el sitio, puede reducir las tasas de rebote y aumentar el tiempo en el sitio, que son señales positivas para el SEO.

**P4: ¿Puedo traducir la configuración o los mensajes del módulo?**
R: El módulo "Búsqueda dirigida" funciona principalmente en segundo plano y no introduce texto nuevo en el front-office que necesite traducción. Las opciones de configuración en el back office suelen estar en inglés. Si se introdujera algún texto nuevo, lo traduciría a través de **Internacional > Traducciones** en su Back Office de PrestaShop, seleccionando "Traducciones de módulos instalados" y luego el módulo "Búsqueda dirigida".

**P5: ¿Qué pasa si quiero buscar en un campo que no aparece en la configuración del módulo?**
R: El módulo ofrece opciones para los campos de producto más comunes e impactantes. Si tiene un campo personalizado muy específico que necesita incluir en la búsqueda, esto requeriría un desarrollo personalizado.

-   **Solución:** Póngase en contacto con el soporte de MyPresta.eu o con un desarrollador de PrestaShop para discutir modificaciones personalizadas.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Visión general de la arquitectura

El módulo "Búsqueda dirigida" opera principalmente anulando la clase central `Search` de PrestaShop. Esto le permite interceptar y modificar la lógica de consulta de búsqueda predeterminada antes de que llegue a la base de datos. El módulo aprovecha el sistema de anulación de PrestaShop para inyectar sus parámetros de búsqueda personalizados basados en la configuración del comerciante. Es un módulo ligero, que se centra en modificar el comportamiento central existente en lugar de introducir nuevas entidades o controladores complejos.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador de administración de Front-Office o Back-Office personalizado. Su funcionalidad se integra anulando una clase central y a través del `getContent()` estándar del módulo para la configuración.

### 4.3 Clases y modelos centrales (`classes/`)

El núcleo de la funcionalidad de este módulo reside en su anulación de la clase `Search`.

-   **`targetsearch/override/classes/index.php`**:

    -   Este es un archivo `index.php` vacío estándar, típicamente colocado en directorios para evitar la lista de directorios por razones de seguridad. No contiene ningún código funcional.
-   **`targetsearch/override/classes/Search.php`**:

    -   **Nombre de la clase**: `Search` (anula la clase central `classes/Search.php`)
    -   **Clase padre**: `SearchCore`
    -   **Responsabilidad**: Esta clase es responsable de modificar el método `search` de la clase central `Search`. Lee la configuración almacenada en `ps_configuration` (por ejemplo, `TARGETSEARCH_PRODUCT_NAME`, `TARGETSEARCH_DESCRIPTION`, etc.) y ajusta dinámicamente la consulta SQL utilizada para la búsqueda de productos.
    -   **Métodos públicos clave**:
        -   `search($id_lang, $expr, $page_number = 1, $page_size = 10, $order_by = 'position', $order_way = 'desc', $ajax = false, $use_cookie = true, Context $context = null)`: Este método se anula para inyectar las condiciones de búsqueda personalizadas. Construye la cláusula `WHERE` de la consulta SQL basándose en los objetivos de búsqueda habilitados. Comprueba `Configuration::get('TARGETSEARCH_...')` para cada objetivo (nombre del producto, descripción, referencia, EAN13, UPC, etiquetas, fabricante, proveedor, categoría, valor de la característica) y añade las condiciones `LIKE` correspondientes a la consulta.
    -   **Interacción con la base de datos**: No interactúa con tablas de base de datos personalizadas. Modifica la consulta que interactúa con las tablas estándar de productos, categorías, fabricantes, proveedores y características de PrestaShop.
    -   **`$definition`**: No aplicable ya que anula una clase central y no define un nuevo `ObjectModel`.

### 4.4 Activos JavaScript (`views/js/`)

-   **`targetsearch/targetsearch.js`**:
    -   **Alcance**: Back-office (potencialmente, pero típicamente no utilizado para la lógica de búsqueda del front-office).
    -   **Propósito**: Este archivo generalmente está vacío o contiene JavaScript mínimo, a menudo para interacciones básicas de la interfaz de usuario en la página de configuración del módulo si se necesitara alguna lógica avanzada del lado del cliente. Dada la función principal del módulo es la lógica de búsqueda del lado del servidor, es poco probable que este archivo contenga JS complejo relacionado con la búsqueda del front-office. Podría ser un marcador de posición o para mejoras menores de formularios del back-office.
    -   **Detectores de eventos/Manipulación del DOM**: Es poco probable que contenga detectores de eventos o manipulación del DOM significativos relacionados con la búsqueda del front-office. Su función principal sería para la página de configuración del módulo en el back office.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`targetsearch/targetsearch.css`**:

    -   **Alcance**: Back-office.
    -   **Propósito**: Esta hoja de estilo se utiliza típicamente para dar estilo a la página de configuración del módulo en el Back Office de PrestaShop, asegurando que se vea consistente con el tema de administración. Podría contener estilos para elementos de formulario, alertas o ajustes de diseño específicos para la configuración del módulo.
    -   **Selectores de clase CSS clave**: Probablemente apunta a clases de administración estándar de PrestaShop o IDs/clases específicas dentro de la salida de `getContent()` del módulo.
-   **`targetsearch/targetsearch15.css`**:

    -   **Alcance**: Back-office (específicamente para PrestaShop 1.5.x).
    -   **Propósito**: Este archivo proporciona ajustes de estilo específicos para la página de configuración del módulo cuando se ejecuta en PrestaShop 1.5.x, teniendo en cuenta las diferencias en la estructura y el CSS del tema de administración.
    -   **Selectores de clase CSS clave**: Similar a `targetsearch.css` pero adaptado para el entorno de administración de PS 1.5.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **`targetsearch/targetsearch-top.tpl`**:
    -   **Alcance**: Front-office.
    -   **Hook**: Esta plantilla probablemente está diseñada para ser enganchada en `displayHeader` o `displayTop` (o hooks similares que renderizan contenido en el área del encabezado).
    -   **Propósito**: Si bien la función principal del módulo es la lógica de búsqueda, esta plantilla podría usarse para generar una entrada oculta, un pequeño script o un elemento visual específico relacionado con la presencia del módulo, aunque no es estrictamente necesario para la anulación de la búsqueda en sí. Dada la descripción del módulo, es más probable que esta plantilla sea un marcador de posición o para un componente visual muy menor y no crítico, ya que el impacto principal del módulo está en los *resultados* de la búsqueda, no en la *entrada* de búsqueda. También podría ser un remanente de una versión anterior o una plantilla destinada a una característica futura.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   El módulo no crea ninguna tabla de base de datos personalizada.
    -   Almacena su configuración en la tabla estándar `ps_configuration` de PrestaShop.
        -   Claves: `TARGETSEARCH_PRODUCT_NAME`, `TARGETSEARCH_DESCRIPTION`, `TARGETSEARCH_SHORT_DESCRIPTION`, `TARGETSEARCH_REFERENCE`, `TARGETSEARCH_EAN13`, `TARGETSEARCH_UPC`, `TARGETSEARCH_TAGS`, `TARGETSEARCH_MANUFACTURER`, `TARGETSEARCH_SUPPLIER`, `TARGETSEARCH_CATEGORY`, `TARGETSEARCH_FEATURE_VALUE`.
        -   Valores: `1` (habilitado) o `0` (deshabilitado).
-   **Tabla de hooks registrados**:
    El módulo registra hooks estándar principalmente para su instalación y desinstalación, y potencialmente para renderizar su configuración. Su funcionalidad central es a través de la anulación de clases, no directamente a través de hooks.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `install` | Durante la instalación del módulo. | Crea entradas de configuración en `ps_configuration` con valores predeterminados. |
| `uninstall` | Durante la desinstalación del módulo. | Elimina entradas de configuración de `ps_configuration`. |
| `displayHeader` (o similar) | Renderiza contenido en la sección `<head>` o en la parte superior de la página. | Potencialmente utilizado para incluir `targetsearch.js` o `targetsearch.css` si contienen activos de front-office, o para renderizar `targetsearch-top.tpl`. |
| `displayBackOfficeHeader` | Renderiza contenido en la sección `<head>` del Back Office. | Utilizado para incluir `targetsearch.css` (y `targetsearch15.css` condicionalmente) para dar estilo a la página de configuración del módulo. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y cualquier otra asistencia con el módulo "Búsqueda dirigida", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.

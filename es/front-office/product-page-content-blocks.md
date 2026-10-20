---
title: "Bloques de contenido de la página de producto - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Bloques de contenido de la página de producto' de MyPresta.eu."
sidebar:
  label: "Bloques de contenido de la página de producto - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product page content blocks en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-content-blocks.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-page-content-blocks/)
>
> ---


# Bloques de contenido de la página de producto

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una instalación de PrestaShop y este módulo no introduce requisitos específicos adicionales más allá de eso.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

El módulo "Bloques de contenido de la página de producto" opera principalmente a través de una pestaña dedicada en la página de edición de cada producto, en lugar de una única pantalla de configuración global. Sin embargo, hay una página de configuración principal del módulo para la configuración inicial y un controlador AJAX para gestionar los bloques.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Cuando instale el módulo por primera vez y haga clic en "Configurar", accederá a su página de configuración principal. Esta página suele gestionar la configuración inicial o los ajustes globales, si los hubiera.

- **Qué hace este ajuste:** Esta página sirve como punto de entrada para el módulo. Si bien la funcionalidad principal de creación de bloques se realiza en las páginas de producto, esta pantalla podría ofrecer ajustes generales o una descripción rápida.
- **Efecto de cambiar este ajuste:** Cualquier ajuste aquí se aplicaría globalmente a cómo se comporta el módulo en todas las páginas de producto, como habilitar/deshabilitar el módulo por completo o establecer comportamientos predeterminados.
- **Valor recomendado:** Siga las instrucciones en pantalla. Si no hay ajustes específicos, esta página simplemente confirmará que el módulo está instalado y listo para usar.
- **Escenario / ejemplo de comerciante:** Podría encontrar un interruptor aquí para "Habilitar/Deshabilitar Módulo" que desactivaría todos los bloques de contenido personalizados en su tienda sin desinstalar el módulo.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

La interacción principal con este módulo ocurre en la página de edición del producto.

#### 2.2.1 Página de edición del producto (Catálogo > Productos > Editar un producto)

Después de instalar el módulo, cuando edite cualquier producto en su back office de PrestaShop, encontrará una nueva pestaña dedicada a "Bloques de contenido de la página de producto" (o un nombre similar).

- **Nombre de la pantalla y ubicación del menú:** **Catálogo > Productos > [Seleccionar/Editar un producto] > Pestaña "Bloques de contenido de la página de producto"**
- **Acciones y configuraciones disponibles:**

  - **Añadir un nuevo bloque:** Normalmente verá un botón como "Añadir nuevo bloque" o una interfaz similar para crear un nuevo bloque de contenido para el producto actual.
    - **Qué hace este ajuste:** Le permite definir una nueva pieza de contenido.
    - **Efecto de cambiar este ajuste:** Se creará y almacenará un nuevo bloque de contenido para este producto específico.
    - **Escenario / ejemplo de comerciante:** Desea añadir un vídeo tutorial para un producto complejo. Hace clic en "Añadir nuevo bloque".
  - **Editor de contenido:** Para cada bloque, tendrá un editor de texto enriquecido (WYSIWYG) donde podrá introducir texto, imágenes, vídeos o incluso HTML personalizado.
    - **Qué hace este ajuste:** Define el contenido real que se mostrará.
    - **Efecto de cambiar este ajuste:** El contenido que introduzca aquí se renderizará en el front office.
    - **Escenario / ejemplo de comerciante:** Escribe "¡Vea nuestro vídeo de unboxing!" e incrusta un enlace de vídeo de YouTube.
  - **Selección de hook:** Un menú desplegable o una lista de hooks de PrestaShop disponibles (`displayHeader`, `displayFooterProduct`, `displayRightColumnProduct`, etc.).
    - **Qué hace este ajuste:** Determina la posición exacta donde aparecerá su bloque de contenido en la página del producto.
    - **Efecto de cambiar este ajuste:** El bloque se renderizará en la posición del hook seleccionado.
    - **Valor recomendado:** Elija el hook que mejor se adapte al propósito del contenido. Para detalles específicos del producto, `displayProductAdditionalInfo` o `displayFooterProduct` son comunes. Para elementos de confianza, `displayReassurance`.
    - **Escenario / ejemplo de comerciante:** Desea que una insignia de confianza aparezca cerca del botón de añadir al carrito, por lo que selecciona `displayReassurance`.
  - **Estado del bloque (Habilitado/Deshabilitado):** Un interruptor para activar o desactivar el bloque.
    - **Qué hace este ajuste:** Controla si el bloque es visible en el front office.
    - **Efecto de cambiar este ajuste:**
      - *Cuando está habilitado:* El bloque aparecerá en la página del producto.
      - *Cuando está deshabilitado:* El bloque se ocultará pero no se eliminará, lo que le permitirá reactivarlo más tarde.
    - **Valor recomendado:** Habilite los bloques que desee mostrar, deshabilite los que desee ocultar temporalmente.
    - **Escenario / ejemplo de comerciante:** Tiene un bloque de promoción estacional que desea ocultar después de que termine la temporada, pero podría reutilizar el próximo año.
  - **Orden/Posición:** A menudo, una interfaz de arrastrar y soltar o un campo de entrada para establecer el orden de visualización si hay varios bloques en el mismo hook.
    - **Qué hace este ajuste:** Determina la secuencia de bloques dentro de un solo hook.
    - **Efecto de cambiar este ajuste:** Los bloques aparecerán en el orden especificado.
    - **Escenario / ejemplo de comerciante:** Tiene tres insignias de confianza en `displayReassurance` y desea que la insignia de "Envío gratuito" aparezca primero.
  - **Editar/Eliminar bloques:** Botones para modificar bloques existentes o eliminarlos por completo.
    - **Qué hace este ajuste:** Le permite actualizar el contenido, el hook o el estado, o eliminar permanentemente un bloque.
    - **Efecto de cambiar este ajuste:** Actualiza o elimina el bloque de la página del producto.
    - **Escenario / ejemplo de comerciante:** La descripción de un producto ha cambiado, por lo que edita el contenido de un bloque relacionado.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

  1. Navegue a **Catálogo > Productos** y seleccione el producto que desea mejorar.
  2. Haga clic en la pestaña "Bloques de contenido de la página de producto".
  3. Haga clic en "Añadir nuevo bloque" para crear una nueva sección de contenido.
  4. Introduzca su contenido utilizando el editor de texto enriquecido.
  5. Seleccione el hook apropiado para donde desea que aparezca el contenido.
  6. Asegúrese de que el bloque esté habilitado.
  7. Guarde los cambios para el producto.
  8. Repita para otros productos según sea necesario. Revise regularmente sus páginas de producto para asegurarse de que los bloques se muestren como se desea.

#### 2.2.2 AdminMegablocksAjaxController (megablocks/controllers/admin/AdminMegablocksAjax.php)

Este controlador no es accedido directamente por los comerciantes a través de un elemento de menú. En su lugar, maneja las operaciones en segundo plano (solicitudes AJAX) cuando usted interactúa con la pestaña "Bloques de contenido de la página de producto" en la página de edición del producto. Por ejemplo, cuando guarda un nuevo bloque, edita uno existente o cambia su orden, este controlador procesa esas solicitudes sin requerir una recarga completa de la página.

- **Nombre de la pantalla y ubicación del menú:** No directamente accesible. Opera en segundo plano en la página de edición del producto.
- **Acciones y configuraciones disponibles:** Gestiona la creación, actualización, eliminación y reordenación de bloques de contenido para productos individuales.
- **Efecto de los cambios:** Asegura que sus cambios en los bloques de contenido en la página de edición del producto se guarden en la base de datos y se reflejen en el front office.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Usted interactúa con este controlador implícitamente utilizando la pestaña "Bloques de contenido de la página de producto" en la página de edición del producto. No se requiere interacción directa.

#### 2.2.3 index.php (megablocks/controllers/admin/index.php)

Este archivo es una práctica estándar de PrestaShop para asegurar los directorios de los controladores de administración y normalmente contiene solo una declaración `die('Access Denied');`. No representa una pantalla funcional o un área de configuración para el comerciante.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de configuración del módulo** | (Ajustes globales si los hay) | (Según los valores predeterminados del módulo) | Configuración inicial, habilitación/deshabilitación global o comportamiento general del módulo. |
| **Página de edición del producto (Pestaña)** | Añadir nuevo bloque | N/A | Crea un nuevo bloque de contenido para el producto actual. |
|  | Editor de contenido | Vacío | Define el contenido HTML/texto del bloque. |
|  | Selección de hook | Varía (por ejemplo, `displayFooterProduct`) | Determina la posición de visualización en la página del producto. |
|  | Estado del bloque | Habilitado | Controla la visibilidad del bloque en el front office. |
|  | Orden/Posición | 1 (o el siguiente disponible) | Establece la secuencia de visualización de los bloques dentro de un hook. |
|  | Editar/Eliminar bloque | N/A | Modifica o elimina bloques de contenido existentes. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mi nuevo bloque de contenido no aparece en la página del producto. ¿Qué debo hacer?**
**R1:**

1. **Verificar el estado del bloque:** Vaya a la página de edición del producto, navegue a la pestaña "Bloques de contenido de la página de producto" y asegúrese de que el bloque que creó esté configurado como "Habilitado".
2. **Borrar caché:** PrestaShop utiliza el almacenamiento en caché para acelerar su tienda. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" si está disponible).
3. **Verificar la selección del hook:** Vuelva a comprobar que ha seleccionado un hook que realmente es renderizado por su tema en la página del producto. Algunos temas pueden no utilizar todos los hooks estándar de PrestaShop.
4. **Compatibilidad del tema:** Si su tema está muy personalizado, podría anular las ubicaciones estándar de los hooks. Póngase en contacto con el desarrollador de su tema o con un webmaster para confirmar la estructura de hooks del tema.

**P2: El bloque de contenido se ve extraño o sin estilo en mi página de producto.**
**R2:**

1. **Verifique su contenido:** Si ha añadido HTML personalizado o ha copiado contenido de otra fuente, podría contener estilos conflictivos. Intente pegar su contenido primero en un editor de texto plano para eliminar cualquier formato oculto, luego vuelva a pegarlo en el editor del módulo.
2. **CSS del módulo:** El módulo incluye algo de CSS básico. Si su tema tiene un estilo muy específico, podría anular o entrar en conflicto con los estilos del módulo.
3. **Estilo de tema personalizado:** Para un estilo avanzado, es posible que necesite un webmaster para añadir reglas CSS personalizadas a la hoja de estilo de su tema para que el bloque coincida con el diseño de su tienda. Pueden apuntar a los elementos HTML específicos generados por el módulo.

**P3: ¿Puedo usar este módulo para tiendas multi-idioma?**
**R3:** Sí, normalmente los bloques de contenido creados con este módulo admitirán la funcionalidad multi-idioma de PrestaShop. Al editar un bloque, debería ver pestañas de idioma (por ejemplo, inglés, francés, español) junto al editor de contenido. Puede introducir contenido diferente para cada idioma, asegurando que sus bloques estén localizados para sus clientes internacionales.

**P4: Quiero mostrar el mismo bloque en varias páginas de producto. ¿Tengo que crearlo repetidamente?**
**R4:** Este módulo está diseñado para contenido *específico del producto*. Si necesita el *mismo* bloque de contenido en muchos productos, actualmente tendría que crearlo para cada producto. Para contenido verdaderamente global que aparece en *todas* las páginas de producto (o todas las páginas de un cierto tipo), un tipo diferente de módulo (por ejemplo, un módulo de bloque HTML personalizado que se engancha globalmente) podría ser más eficiente. Sin embargo, la fortaleza de este módulo es su capacidad para adaptar el contenido por producto.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Bloques de contenido de la página de producto" para desarrolladores y webmasters.

### 4.1 Visión general de la arquitectura

El módulo "Bloques de contenido de la página de producto" (`megablocks`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para la instalación y el registro de hooks. Su funcionalidad principal gira en torno a la gestión de bloques de contenido específicos del producto, que se almacenan en una tabla de base de datos personalizada. El módulo extiende la funcionalidad del back-office de PrestaShop inyectando una pestaña personalizada en la página de edición del producto, gestionada por un controlador AJAX. La visualización en el front-office se logra enganchándose a varios hooks `display*` en la página del producto y renderizando plantillas Smarty específicas.

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**: Este módulo no contiene ningún controlador dedicado del front-office. Toda la renderización del contenido del front-office se maneja directamente a través de hooks registrados dentro del archivo principal del módulo `index.php`, que luego renderiza plantillas específicas.
- **Controladores de administración del Back-Office**:

  - `megablocks/controllers/admin/AdminMegablocksAjax.php`
    - **Nombre de la clase y clase padre**: `AdminMegablocksAjaxController` que extiende `ModuleAdminController`.
    - **Responsabilidad**: Este controlador maneja todas las solicitudes AJAX que se originan en la pestaña "Bloques de contenido de la página de producto" en la página de edición del producto. Es responsable de:
      - Crear nuevos bloques de contenido.
      - Actualizar bloques de contenido existentes (contenido, hook, estado, posición).
      - Eliminar bloques de contenido.
      - Obtener datos de bloques de contenido para un producto específico.
      - No tiene una entrada de menú directa, pero se invoca a través de llamadas JavaScript desde la página de edición del producto.
  - `megablocks/controllers/admin/index.php`
    - **Nombre de la clase y clase padre**: No es un controlador funcional.
    - **Responsabilidad**: Este es un archivo de seguridad, estándar en los directorios de administración de PrestaShop, que contiene `die('Access Denied');` para evitar la lista directa de directorios o el acceso.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto implica que el manejo de datos del módulo (por ejemplo, guardar y recuperar bloques de contenido) probablemente se gestiona directamente dentro del archivo principal `megablocks/index.php`, posiblemente utilizando `Db::getInstance()` para interacciones directas con la base de datos o una estructura de matriz simple para la configuración. Si se utiliza una tabla de base de datos personalizada, su esquema y métodos de interacción se definirían dentro del archivo principal del módulo.

### 4.4 Activos JavaScript (`views/js/`)

- `megablocks/js/script.js`
  - **Alcance**: Probablemente front-office.
  - **Detalles**: Este script contendría cualquier lógica del lado del cliente requerida para la visualización en el front-office de los bloques de contenido. Esto podría incluir animaciones simples, ajustes responsivos o interacciones si los bloques contienen elementos dinámicos.
- `megablocks/views/admin/megablocks.js`
  - **Alcance**: Back-office (Página de edición del producto).
  - **Detalles**: Este es el archivo JavaScript principal para gestionar bloques de contenido en el back office. Es responsable de:
    - Inicializar la pestaña "Bloques de contenido de la página de producto" en la página de edición del producto.
    - Manejar los eventos de clic para los botones "Añadir nuevo bloque", "Editar" y "Eliminar".
    - Gestionar el editor de texto enriquecido (por ejemplo, integración de TinyMCE o CKEditor) para la entrada de contenido.
    - Enviar solicitudes AJAX a `AdminMegablocksAjaxController` para crear, actualizar y eliminar bloques.
    - Actualizar la interfaz de usuario dinámicamente en función de las respuestas AJAX (por ejemplo, añadir un nuevo bloque a la lista, eliminar un bloque eliminado).
    - Implementar la funcionalidad de arrastrar y soltar para reordenar bloques.
- `megablocks/views/fancybox/script.js`
  - **Alcance**: Back-office (Página de edición del producto).
  - **Detalles**: Este script probablemente se integra o implementa una "Fancybox" (o una biblioteca modal/lightbox similar) para mostrar los formularios "Añadir nuevo bloque" o "Editar bloque" en una ventana emergente. Manejaría la apertura/cierre del modal, la carga de contenido en él y el envío de los datos del formulario.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `megablocks/views/admin/megablocks.css`
  - **Alcance**: Estilo del formulario de administración del back-office.
  - **Detalles**: Contiene reglas CSS específicas para dar estilo a la pestaña "Bloques de contenido de la página de producto", la lista de bloques, los formularios de añadir/editar y cualquier elemento de interfaz de usuario personalizado dentro del back office de PrestaShop.
  - **Selectores de clase CSS clave**: Los desarrolladores pueden inspeccionar el HTML generado en la página de edición del producto para identificar clases específicas (por ejemplo, `.megablocks-list`, `.megablock-item`, `.megablock-form`) para anular o extender en su tema de administración personalizado o anulaciones de módulos.
- `megablocks/views/css/milligram.css`
  - **Alcance**: Potencialmente tanto front-office como back-office, o específicamente para formularios modales.
  - **Detalles**: Milligram es un framework CSS minimalista. Su inclusión sugiere que el módulo podría estar usándolo para un estilo básico y limpio de sus bloques de contenido generados en el front office, o para los formularios modales en el back office (por ejemplo, contenido de Fancybox). Proporciona una base ligera para tipografía, formularios y diseño de cuadrícula.
  - **Selectores de clase CSS clave**: Estarían presentes las clases estándar de Milligram (por ejemplo, `.container`, `.row`, `.column`, `.button`, `.input`). Los desarrolladores pueden anular estas o añadir estilos más específicos en el CSS de su tema.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/front/`)**: Estas plantillas son incluidas dinámicamente por el módulo cuando un bloque de contenido se configura para un hook específico. Cada archivo `megablock-*.tpl` probablemente sirve como un envoltorio o una plantilla estándar para renderizar el contenido de un solo bloque. El contenido real (HTML) definido por el comerciante se pasa generalmente como una variable Smarty y se renderiza directamente.

  - `megablocks/views/front/megablock-actionProductOutOfStock.tpl`: Renderiza contenido cuando un producto está agotado.
  - `megablocks/views/front/megablock-displayAfterProductThumbs.tpl`: Renderiza contenido después de las imágenes/miniaturas del producto.
  - `megablocks/views/front/megablock-displayBeforeBodyClosingTag.tpl`: Renderiza contenido justo antes de la etiqueta `</body>`.
  - `megablocks/views/front/megablock-displayFooter.tpl`: Renderiza contenido en el pie de página general del sitio.
  - `megablocks/views/front/megablock-displayFooterBefore.tpl`: Renderiza contenido antes del pie de página general del sitio.
  - `megablocks/views/front/megablock-displayFooterProduct.tpl`: Renderiza contenido en el área del pie de página específica del producto.
  - `megablocks/views/front/megablock-displayHeader.tpl`: Renderiza contenido en la cabecera general del sitio.
  - `megablocks/views/front/megablock-displayLeftColumnProduct.tpl`: Renderiza contenido en la columna izquierda de la página del producto.
  - `megablocks/views/front/megablock-displayNav1.tpl`: Renderiza contenido en la primera área de navegación.
  - `megablocks/views/front/megablock-displayNav2.tpl`: Renderiza contenido en la segunda área de navegación.
  - `megablocks/views/front/megablock-displayProductAdditionalInfo.tpl`: Renderiza contenido en la sección de información adicional del producto.
  - `megablocks/views/front/megablock-displayProductPriceBlock.tpl`: Renderiza contenido cerca del bloque de precio del producto.
  - `megablocks/views/front/megablock-displayReassurance.tpl`: Renderiza contenido en el bloque de reafirmación (por ejemplo, insignias de confianza).
  - `megablocks/views/front/megablock-displayRightColumnProduct.tpl`: Renderiza contenido en la columna derecha de la página del producto.
  - `megablocks/views/front/megablock-displayTop.tpl`: Renderiza contenido en la sección superior de la página.
- **Plantillas de administración (`views/templates/admin/`)**:

  - `megablocks/views/admin/li_megablock.tpl`: Esta plantilla se utiliza probablemente para renderizar un solo elemento en la lista de bloques de contenido en la página de edición del producto. Mostraría el título del bloque, el hook seleccionado, el estado y los botones de edición/eliminación.
  - `megablocks/views/admin/tabs.tpl`: Esta plantilla probablemente define la estructura de la propia pestaña "Bloques de contenido de la página de producto", incluyendo el botón "Añadir nuevo bloque" y el contenedor para la lista de bloques.
- **Plantillas de Fancybox (`views/fancybox/`)**: Estas plantillas se utilizan para los formularios modales (Fancybox) en el back office.

  - `megablocks/views/fancybox/edit.tpl`: La plantilla de formulario para editar un bloque de contenido existente.
  - `megablocks/views/fancybox/heading.tpl`: Una plantilla para el encabezado o título del modal de Fancybox.
  - `megablocks/views/fancybox/new.tpl`: La plantilla de formulario para crear un nuevo bloque de contenido.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo probablemente crea una tabla de base de datos personalizada, por ejemplo, `ps_megablocks` (o similar), para almacenar los bloques de contenido.
  - Esta tabla normalmente contendría campos como:
    - `id_megablock`: Clave primaria.
    - `id_product`: Clave externa que enlaza con `ps_product`.
    - `hook_name`: El nombre del hook de PrestaShop donde se muestra el bloque (por ejemplo, `displayFooterProduct`).
    - `position`: El orden del bloque dentro de su hook.
    - `active`: Booleano (0 o 1) para el estado del bloque.
    - `content`: El contenido HTML real del bloque (probablemente un campo `TEXT` o `LONGTEXT`).
    - `content_lang`: Si el contenido es multilingüe, esto podría ser una tabla separada (`ps_megablocks_lang`) o manejarse a través de datos serializados en `content`.
  - Los registros de configuración se almacenan en `ps_configuration` para la configuración global del módulo (por ejemplo, `MEGABLOCKS_ENABLED`).
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| :--- | :---
| `displayHeader` | Renderiza contenido en la sección `<head>` del documento HTML. | N/A | Principalmente para incluir CSS, JavaScript, metaetiquetas u otros elementos que afectan el comportamiento técnico de la página o el estilo global. |
| `displayNav1` | Renderiza contenido en la primera área de navegación. | N/A | Típicamente para mostrar elementos como selectores de moneda, selectores de idioma o enlaces rápidos. |
| `displayNav2` | Renderiza contenido en la segunda área de navegación. | N/A | A menudo utilizado para enlaces de cuentas de clientes, información de contacto u otros elementos de navegación secundarios. |
| `displayTop` | Renderiza contenido en la sección superior de la página, generalmente debajo del encabezado pero encima del contenido principal. | N/A | Ideal para banners, barras de búsqueda o anuncios importantes. |
| `displayLeftColumnProduct` | Renderiza contenido en la barra lateral izquierda de la página del producto. | N/A | Adecuado para filtros de productos, categorías relacionadas o bloques promocionales específicos del producto. |
| `displayRightColumnProduct` | Renderiza contenido en la barra lateral derecha de la página del producto. | N/A | Similar a la columna izquierda, se puede utilizar para ventas cruzadas, información de servicio al cliente o insignias de confianza. |
| `displayAfterProductThumbs` | Renderiza contenido inmediatamente después de las miniaturas de las imágenes del producto. | N/A | Bueno para destacados rápidos de productos, vídeos cortos o llamadas a características específicas. |
| `displayProductAdditionalInfo` | Renderiza contenido dentro del bloque de información principal del producto, a menudo cerca de la descripción o las características. | N/A | Excelente para especificaciones detalladas, instrucciones de uso o propuestas de venta únicas. |
| `displayProductPriceBlock` | Renderiza contenido cerca de la visualización del precio del producto. | N/A | Útil para mostrar opciones de financiación, garantías de precio o mensajes de descuento especiales. |
| `displayReassurance` | Renderiza contenido en el bloque de reafirmación del producto, típicamente cerca del botón de añadir al carrito. | N/A | Perfecto para insignias de confianza, información de entrega, políticas de devolución o iconos de pago seguro. |
| `displayFooterProduct` | Renderiza contenido en el área del pie de página específica del producto, generalmente debajo de los detalles principales del producto. | N/A | Se puede utilizar para detalles extendidos del producto, preguntas frecuentes o reseñas de clientes. |
| `actionProductOutOfStock` | Se ejecuta cuando un producto se agota. | N/A | Permite mostrar mensajes o formularios específicos para productos agotados. |
| `displayFooterBefore` | Renderiza contenido justo antes del pie de página principal del sitio. | N/A | Adecuado para promociones de última hora o llamadas a la acción antes del pie de página. |
| `displayFooter` | Renderiza contenido en el pie de página general del sitio. | N/A | Para información de todo el sitio, pero se puede personalizar por producto para elementos de pie de página únicos. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Bloques de contenido de la página de producto", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad del módulo y su integración con su tienda PrestaShop.

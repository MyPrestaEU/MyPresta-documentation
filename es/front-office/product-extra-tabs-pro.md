---
title: "Product Extra Tabs Pro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Product Extra Tabs Pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "Product Extra Tabs Pro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product Extra Tabs Pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-extra-tabs-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-extra-tabs-pro/)
>
> ---


# Product Extra Tabs Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y normalmente están disponibles en cualquier entorno de alojamiento moderno.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

El módulo "Product Extra Tabs Pro" se configura principalmente directamente desde la página de edición del producto, lo que le permite gestionar las pestañas por producto. La pantalla de configuración principal del módulo gestiona los ajustes globales.

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Para acceder a la configuración principal, vaya a **Módulos > Gestor de módulos**, busque "Product Extra Tabs Pro" y haga clic en "Configurar".

En esta pantalla, encontrará ajustes que se aplican globalmente o definen cómo se comporta el módulo en su tienda.

- **Ajuste: Habilitar Editor TinyMCE para el Contenido de la Pestaña**

  - **Qué hace este ajuste:** Este interruptor determina si un editor de texto enriquecido (TinyMCE, el mismo editor que PrestaShop usa para las descripciones de productos) está disponible cuando crea o edita el contenido de la pestaña.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Verá un editor fácil de usar con opciones de formato (negrita, cursiva, listas, imágenes, enlaces, etc.) al añadir contenido a sus pestañas extra. Esto facilita la creación de contenido visualmente atractivo y bien estructurado sin necesidad de conocer HTML.
    - *Cuando está deshabilitado:* Solo tendrá un área de texto plano para el contenido de la pestaña. Necesitaría escribir manualmente las etiquetas HTML para formatear su texto, lo cual es más complejo para usuarios no técnicos.
  - **Valor recomendado:** **SÍ**
  - **Escenario / ejemplo de comerciante:** Si desea añadir imágenes, vídeos o texto con estilo a sus pestañas (por ejemplo, una pestaña de "Tabla de tallas" con una imagen, o una pestaña de "Garantía" con términos clave en negrita), habilite esto. Si solo necesita texto plano, puede deshabilitarlo para una interfaz más sencilla.
- **Ajuste: Mostrar Pestañas Globalmente (para todos los productos)**

  - **Qué hace este ajuste:** Esta opción le permite crear pestañas "globales" que aparecen automáticamente en *cada* página de producto de su tienda. Esto es útil para información que se aplica universalmente, como políticas generales de envío o historias de marca.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Cualquier pestaña que cree dentro de la interfaz de configuración del módulo (no en páginas de producto individuales) se mostrará en todas las páginas de producto. Luego puede gestionar estas pestañas globales desde la configuración principal del módulo.
    - *Cuando está deshabilitado:* Las pestañas deben crearse y gestionarse individualmente para cada producto desde su respectiva página de edición de producto. Las pestañas globales no se mostrarán.
  - **Valor recomendado:** **SÍ** (si tiene información que se aplica a todos los productos, de lo contrario NO).
  - **Escenario / ejemplo de comerciante:** Desea añadir una pestaña de "Política de devoluciones" que sea idéntica para todos los productos. Habilite esto, cree la pestaña aquí y aparecerá en cada página de producto. Si solo necesita pestañas únicas para productos específicos, mantenga esto deshabilitado.
- **Ajuste: Posición de Visualización de la Pestaña**

  - **Qué hace este ajuste:** Este menú desplegable controla dónde se muestran las pestañas extra en la página del producto.
  - **Efecto de cambiar este ajuste:**
    - *Opción: `displayProductExtraContent` (Predeterminado):* Las pestañas aparecerán en el área de contenido estándar del producto, generalmente debajo de los detalles principales del producto, junto con las pestañas predeterminadas de descripción/ficha técnica. Esta es la posición más común y recomendada.
    - *Opción: `displayFooterProduct` (Solo PrestaShop 1.6):* Las pestañas aparecerán en la sección del pie de página del producto. Esto podría ser adecuado para información suplementaria menos crítica.
    - *Opción: `displayRightColumnProduct` (Solo PrestaShop 1.6):* Las pestañas aparecerán en la columna derecha de la página del producto. Esto es menos común para las pestañas y podría depender en gran medida del diseño de su tema.
    - *Opción: `displayLeftColumnProduct` (Solo PrestaShop 1.6):* Las pestañas aparecerán en la columna izquierda de la página del producto. Similar a la columna derecha, esto es menos común para las pestañas.
  - **Valor recomendado:** `displayProductExtraContent`
  - **Escenario / ejemplo de comerciante:** Para la mayoría de las tiendas, `displayProductExtraContent` proporciona la mejor experiencia de usuario, ya que mantiene toda la información relacionada con el producto agrupada. Si su tema tiene un diseño muy específico o desea restar importancia a las pestañas, podría experimentar con las posiciones de pie de página o columna (aunque estas son menos comunes para las pestañas).

#### 2.1.1 Gestión de Pestañas Globales (si "Mostrar Pestañas Globalmente" está habilitado)

Si habilitó "Mostrar Pestañas Globalmente", esta sección aparecerá en la página de configuración del módulo. Aquí puede añadir, editar o eliminar pestañas que se mostrarán en *todas* las páginas de producto.

- **Botón Añadir Nueva Pestaña:** Haga clic aquí para abrir un formulario donde puede definir una nueva pestaña global.
  - **Título de la Pestaña:** El texto que aparece en la propia pestaña (por ejemplo, "Información de Envío", "Garantía"). Esto suele ser multi-idioma.
  - **Contenido de la Pestaña:** El contenido real que aparece cuando se hace clic en la pestaña. Use el editor TinyMCE si está habilitado. Esto también es multi-idioma.
  - **Activo:** Un interruptor para habilitar o deshabilitar la pestaña sin eliminarla.
  - **Posición:** Un número para controlar el orden de la pestaña en relación con otras pestañas globales. Los números más bajos aparecen primero.
- **Lista de Pestañas Existentes:** Una tabla que muestra todas sus pestañas globales configuradas actualmente.
  - **Icono de Editar:** Haga clic para modificar el título, el contenido o la configuración de una pestaña existente.
  - **Icono de Eliminar:** Haga clic para eliminar permanentemente una pestaña global.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

La forma principal de gestionar las pestañas extra específicas del producto es directamente desde la **página de edición del producto** en su Back Office de PrestaShop.

- **Nombre de la Pantalla y Ubicación del Menú:**

  1. Navegue a **Catálogo > Productos**.
  2. Edite un producto existente o cree uno nuevo.
  3. Dentro de la interfaz de edición del producto, busque una nueva pestaña o sección etiquetada como **"Extra Tabs Pro"** (o similar, dependiendo de su versión de PrestaShop y tema).
- **Acciones y Ajustes Disponibles dentro de la sección "Extra Tabs Pro" en una Página de Producto:**

  - **Botón Añadir Nueva Pestaña:** Haga clic aquí para crear una nueva pestaña *específicamente para este producto*.
    - **Título de la Pestaña:** Introduzca el título para esta pestaña específica del producto (por ejemplo, "Especificaciones Técnicas para el Modelo X"). Esto es multi-idioma.
    - **Contenido de la Pestaña:** Introduzca el contenido para esta pestaña. El editor TinyMCE estará disponible si está habilitado en la configuración principal del módulo. Esto es multi-idioma.
    - **Activo:** Habilite/deshabilite esta pestaña específica para este producto.
    - **Posición:** Establezca el orden de visualización para esta pestaña en relación con otras pestañas en esta página de producto.
  - **Lista de Pestañas Existentes:** Una tabla que muestra todas las pestañas extra que ha creado para *este producto en particular*.
    - **Icono de Editar:** Modifique el título, el contenido o el estado de una pestaña existente específica del producto.
    - **Icono de Eliminar:** Elimine una pestaña de este producto.
- **Efecto de los cambios:**

  - Cuando añade, edita o elimina una pestaña de la sección "Extra Tabs Pro" de un producto, esos cambios *solo afectan a esa página de producto específica*.
  - El contenido y la visibilidad de estas pestañas se actualizan inmediatamente en la página de producto del front office después de guardar sus cambios.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

  1. **Identifique información universal:** Si tiene información que se aplica a TODOS los productos (por ejemplo, envío general, devoluciones, historia de la marca), utilice la función de **pestañas globales** en la configuración principal del módulo.
  2. **Identifique información específica del producto:** Para detalles únicos de un producto (por ejemplo, dimensiones específicas, composición del material, instrucciones de uso, reseñas de vídeo), vaya a la **página de edición de producto individual** y utilice la sección "Extra Tabs Pro" allí.
  3. **Utilice el editor TinyMCE:** Habilite siempre el editor TinyMCE en la configuración principal del módulo para facilitar la creación y el formato del contenido.
  4. **Revise regularmente:** Compruebe periódicamente sus páginas de producto para asegurarse de que las pestañas se muestran correctamente y el contenido está actualizado.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Habilitar Editor TinyMCE | SÍ | Proporciona editor de texto enriquecido para el contenido de la pestaña; formato más fácil. |
|  | Mostrar Pestañas Globalmente | NO (o SÍ si es necesario) | SÍ: Las pestañas globales aparecen en todos los productos. NO: Las pestañas son específicas del producto. |
|  | Posición de Visualización de la Pestaña | `displayProductExtraContent` | Controla dónde aparecen las pestañas en la página del producto. |
|  | **Lista de Pestañas Globales** | (N/A) | Añadir/Editar/Eliminar pestañas que aparecen en TODAS las páginas de producto. |
| **Página de Edición de Producto** | **Sección Extra Tabs Pro** | (N/A) | Añadir/Editar/Eliminar pestañas específicas del producto actual. |
|  | Título de la Pestaña | (Definido por el Usuario) | El nombre visible de la pestaña en la página del producto. |
|  | Contenido de la Pestaña | (Definido por el Usuario) | La información que se muestra cuando se hace clic en la pestaña. |
|  | Activo | SÍ | Controla si la pestaña es visible u oculta. |
|  | Posición | (Definido por el Usuario) | Determina el orden de las pestañas en la página del producto. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

- **P: Mis nuevas pestañas no aparecen en la página del producto.**
  - **R:** Primero, asegúrese de que la pestaña esté marcada como "Activa" tanto en la configuración global del módulo (si es una pestaña global) como en la página de producto individual (si es específica del producto). Segundo, borre la caché de PrestaShop: Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. Además, borre la caché de su navegador.
- **P: El editor TinyMCE no aparece cuando intento añadir contenido a la pestaña.**
  - **R:** Vaya a la página de configuración principal del módulo (**Módulos > Gestor de módulos > Product Extra Tabs Pro > Configurar**) y asegúrese de que el ajuste "Habilitar Editor TinyMCE para el Contenido de la Pestaña" esté configurado en **SÍ**. Guarde los cambios y borre la caché.
- **P: Mis pestañas se ven extrañas o no coinciden con el estilo de mi tema.**
  - **R:** El módulo intenta integrarse sin problemas, pero los temas personalizados a veces pueden anular el estilo predeterminado. Si la apariencia es incorrecta, generalmente requiere pequeños ajustes de CSS en su tema. Póngase en contacto con su webmaster o con el soporte de MyPresta.eu con capturas de pantalla para obtener ayuda.
- **P: ¿Puedo tener diferentes pestañas para diferentes idiomas?**
  - **R:** ¡Sí! Los campos "Título de la Pestaña" y "Contenido de la Pestaña" son multi-idioma. Al editar una pestaña, verá banderas de idioma junto a estos campos. Haga clic en la bandera para cambiar a un idioma diferente e introducir el contenido traducido.
- **P: Quiero mostrar una pestaña solo para ciertos productos, no para todos.**
  - **R:** Asegúrese de que el ajuste "Mostrar Pestañas Globalmente" en la configuración principal del módulo esté configurado en **NO**. Luego, navegue a cada producto específico al que desee añadir una pestaña (**Catálogo > Productos > Editar Producto > sección Extra Tabs Pro**) y cree las pestañas allí.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Visión General de la Arquitectura

El módulo `Product Extra Tabs Pro` está diseñado como un módulo estándar de PrestaShop, extendiendo principalmente la clase `Module`. Aprovecha el sistema de hooks de PrestaShop para inyectar su contenido en las páginas de producto y utiliza una tabla de base de datos personalizada para almacenar los datos de las pestañas. La configuración se gestiona a través de `getContent()` en el archivo principal del módulo, y la gestión de pestañas específicas del producto se integra directamente en la página de administración del producto a través de una pestaña personalizada. Utiliza AJAX para la carga y el guardado dinámico de contenido.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores dedicados de front-office o back-office en el directorio `controllers/`. Toda la renderización del front-office se maneja a través de hooks y archivos de plantilla, y la configuración del back-office se gestiona dentro del método `getContent()` del archivo principal del módulo y las llamadas AJAX.

### 4.3 Clases y Modelos Principales (`classes/`)

El módulo no define clases personalizadas en el directorio `classes/`. Su lógica principal de manejo de datos está incrustada en el archivo principal del módulo `extratabspro/ajax_extratabspro.php`.

### 4.4 Activos JavaScript (`views/js/`)

- `extratabspro/js/tinymce16.inc.js`:
  - **Alcance:** Back-office.
  - **Propósito:** Este archivo probablemente contiene la inicialización y configuración del editor de texto enriquecido TinyMCE, específicamente adaptado para entornos PrestaShop 1.6. Asegura que el editor se cargue y configure correctamente para los campos de entrada de contenido de la pestaña.
- `extratabspro/lib/searchTool/views/js/autocomplete.js`:
  - **Alcance:** Back-office.
  - **Propósito:** Este script es parte de una biblioteca de herramientas de búsqueda, probablemente utilizada para la funcionalidad de autocompletado en un campo de entrada de búsqueda dentro de la interfaz de administración del módulo (por ejemplo, buscar productos para asignar pestañas, aunque esta característica específica no se menciona explícitamente en la guía del comerciante, es un patrón común para dicha biblioteca). Vincula los detectores de eventos a los campos de entrada y maneja las solicitudes AJAX para sugerencias de búsqueda.
- `extratabspro/views/admin/extratabspro.js`:
  - **Alcance:** Back-office (PrestaShop 1.7.x, 8.x, 9.x).
  - **Propósito:** Este es el archivo JavaScript principal para la interfaz de administración del módulo. Maneja:
    - Llamadas AJAX para añadir, editar, eliminar pestañas globales.
    - Llamadas AJAX para añadir, editar, eliminar pestañas específicas del producto en la página de edición del producto.
    - Actualizaciones dinámicas de las tablas de la lista de pestañas.
    - Detectores de eventos para envíos de formularios, clics de botones (añadir/editar/eliminar) y potencialmente reordenación de pestañas mediante arrastrar y soltar.
    - Integración con TinyMCE para campos de contenido.
- `extratabspro/views/admin/extratabspro8.js`:
  - **Alcance:** Back-office (PrestaShop 8.x, 9.x).
  - **Propósito:** Similar a `extratabspro.js`, pero probablemente contiene adaptaciones o correcciones específicas para entornos PrestaShop 8.x y 9.x, abordando cambios en la estructura DOM del Back Office o las API de JavaScript. Realiza las mismas funciones principales que `extratabspro.js` pero asegura la compatibilidad con versiones más recientes de PrestaShop.
- `extratabspro/views/js/extratabspro.js`:
  - **Alcance:** Front-office.
  - **Propósito:** Este script maneja la visualización e interacción de las pestañas extra en la página del producto en el front-end. Probablemente:
    - Inicializa el mecanismo de cambio de pestañas (por ejemplo, pestañas de jQuery UI, pestañas de Bootstrap o lógica personalizada).
    - Vincula eventos de clic a los encabezados de las pestañas para mostrar/ocultar el contenido correspondiente.
    - Asegura transiciones suaves o carga de contenido.
    - Puede manejar el comportamiento responsivo de las pestañas en diferentes tamaños de pantalla.
- `extratabspro/views/js/tinymce16.inc.js`: (Duplicado, probablemente para diferentes contextos o un descuido en el empaquetado)
  - **Alcance:** Back-office.
  - **Propósito:** Igual que el de `extratabspro/js/`, probablemente para la inicialización de TinyMCE.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `extratabspro/lib/searchTool/views/css/autocomplete.css`:
  - **Alcance:** Back-office.
  - **Propósito:** Proporciona estilo para el desplegable de sugerencias de autocompletado y los elementos de la interfaz de usuario relacionados con la biblioteca de herramientas de búsqueda.
- `extratabspro/views/admin/extratabspro.css`:
  - **Alcance:** Back-office.
  - **Propósito:** Estiliza los formularios de configuración del módulo, las tablas de listado de pestañas y cualquier elemento de interfaz de usuario personalizado dentro del Back Office de PrestaShop, asegurando una apariencia y sensación consistentes.
- `extratabspro/views/css/extratabspro.css`:
  - **Alcance:** Front-office.
  - **Propósito:** Proporciona el estilo principal para las pestañas extra en la página del producto. Esto incluye la apariencia de los encabezados de las pestañas, los estados de las pestañas activas y las áreas de contenido. Los desarrolladores pueden anular estos estilos en el `custom.css` o `theme.css` de su tema apuntando a clases como `.extratabs-pro-tabs`, `.extratabs-pro-tab-header`, `.extratabs-pro-tab-content`, etc.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:

  - `extratabspro/views/front/footer.tpl`: Esta plantilla probablemente está destinada a los hooks `displayFooter` o `displayFooterProduct` (aunque el módulo utiliza principalmente `displayProductExtraContent`). Mostraría contenido en el área del pie de página.
  - `extratabspro/views/front/tab.tpl`: Esta plantilla renderiza un único encabezado de pestaña (la parte clicable). Se utiliza dentro de un bucle para generar todos los encabezados de las pestañas.
  - `extratabspro/views/front/tab16.tpl`: Una versión de `tab.tpl` específicamente para PrestaShop 1.6, adaptándose a su diferente estructura HTML o clases CSS.
  - `extratabspro/views/front/tabcontents.tpl`: Esta plantilla renderiza el área de contenido para todas las pestañas extra. Típicamente contiene un bucle que itera a través del contenido de cada pestaña, envolviéndolo en un contenedor que puede ser mostrado/ocultado por JavaScript.
  - `extratabspro/views/front/tabcontents16.tpl`: Una versión de `tabcontents.tpl` específicamente para PrestaShop 1.6.
- **Plantillas de administración (`views/templates/admin/`)**:

  - `extratabspro/lib/searchTool/views/scripts.tpl`: Esta plantilla probablemente incluye activos JavaScript y CSS para la biblioteca de herramientas de búsqueda dentro del contexto de administración.
  - `extratabspro/views/admin/tabs-list.tpl`: Esta plantilla renderiza la tabla que lista todas las pestañas configuradas (ya sean pestañas globales en la página de configuración del módulo o pestañas específicas del producto en la página de edición del producto). Incluye controles para editar y eliminar pestañas.
  - `extratabspro/views/admin/tabs17.tpl`: Esta plantilla es el formulario de configuración principal o la visualización del módulo dentro del Back Office de PrestaShop 1.7.x / 8.x / 9.x. Probablemente contiene los campos del formulario para la configuración global y la inclusión de `tabs-list.tpl` para la gestión de pestañas.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - `ps_extratabspro_tab`: Almacena la información principal de cada pestaña extra (ID, ID de producto, posición, estado activo).
  - `ps_extratabspro_tab_lang`: Almacena el contenido multi-idioma para cada pestaña (título, contenido), vinculado a `ps_extratabspro_tab` por `id_extratabspro_tab` e `id_lang`.
  - `ps_configuration`: Almacena la configuración global del módulo (por ejemplo, `EXTRATABSPRO_TINYMCE_ENABLED`, `EXTRATABSPRO_GLOBAL_TABS_ENABLED`, `EXTRATABSPRO_HOOK_POSITION`).
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyecta los archivos CSS y JS del módulo para la visualización en el front-office. |
| `displayBackOfficeHeader` | En la sección `<head>` de las páginas del Back Office. | Inyecta los archivos CSS y JS del módulo para la configuración del Back Office y la integración de la página del producto. |
| `displayAdminProductsExtra` | En la página de edición del producto en el Back Office. | Inyecta la sección "Extra Tabs Pro" en la interfaz de administración del producto, permitiendo la gestión de pestañas por producto. |
| `displayProductExtraContent` | En el área de contenido principal de la página del producto, típicamente debajo de la descripción del producto. | Renderiza las pestañas extra y su contenido en la página de producto del front-office. Este es el hook principal para la visualización en el front-end. |
| `displayFooterProduct` | En la sección del pie de página de la página del producto. | Hook alternativo para mostrar pestañas, si lo configura el comerciante. |
| `displayRightColumnProduct` | En la columna derecha de la página del producto. | Hook alternativo para mostrar pestañas, si lo configura el comerciante. |
| `displayLeftColumnProduct` | En la columna izquierda de la página del producto. | Hook alternativo para mostrar pestañas, si lo configura el comerciante. |
| `actionProductUpdate` | Después de que un producto se actualiza en el Back Office. | Potencialmente utilizado para borrar la caché o realizar otras acciones relacionadas con los cambios de datos del producto. |
| `actionProductDelete` | Después de que un producto se elimina. | Limpia las pestañas específicas del producto de la base de datos. |
| `actionObjectProductAddAfter` | Después de que se añade un nuevo producto. | Potencialmente utilizado para la configuración inicial o la creación de pestañas predeterminadas para nuevos productos. |
| `actionObjectProductUpdateAfter` | Después de que se actualiza un objeto de producto. | Similar a `actionProductUpdate`, para actualizaciones del modelo de objeto. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y cualquier otra pregunta relacionada con el módulo "Product Extra Tabs Pro", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte y desarrolladores están disponibles para ayudarle.

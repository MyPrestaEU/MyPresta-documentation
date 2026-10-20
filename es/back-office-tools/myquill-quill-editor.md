---
title: "MyQuill - Editor Quill - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo MyQuill - Editor Quill para PrestaShop de MyPresta.eu."
sidebar:
  label: "MyQuill - Editor Quill"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo MyQuill - Quill editor en MyPresta.eu](https://mypresta.eu/modules/administration-tools/myquill-quill-editor.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/myquill-quill-editor/)
>
> ---


# MyQuill - Editor Quill

## 1. Requisitos y compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y generalmente están habilitadas por defecto en la mayoría de los entornos de alojamiento.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Después de la instalación, al hacer clic en "Configurar" accederá a la pantalla de configuración principal de MyQuill. Aquí es donde controla cómo se comporta el editor Quill en su Back Office.

#### **Pestaña de Configuración General**

**1. Habilitar editor MyQuill**
-   **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar el editor MyQuill.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* El editor Quill reemplazará al editor TinyMCE predeterminado en todas las áreas compatibles de su Back Office de PrestaShop (por ejemplo, descripciones de productos, páginas CMS, descripciones de categorías).
    -   *Cuando está deshabilitado (NO):* Se restaurará el editor TinyMCE predeterminado y las funciones de MyQuill no estarán disponibles.
-   **Valor recomendado:** **SÍ** (para usar las funciones del módulo).
-   **Escenario / ejemplo de comerciante:** Si desea volver temporalmente a TinyMCE para probar la compatibilidad con otro módulo, deshabilitaría MyQuill aquí. De lo contrario, manténgalo habilitado para disfrutar del editor avanzado.

**2. Cargar editor Quill en el Front Office**
-   **Qué hace este ajuste:** Determina si los activos necesarios del editor Quill (CSS, JS) se cargan en el front office de su tienda. Esto generalmente solo es necesario si tiene un tema personalizado u otro módulo que usa Quill en el front end.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Los archivos principales de Quill se incluirán en las páginas públicas de su tienda. Esto podría aumentar ligeramente el tiempo de carga de la página, pero es necesario si muestra contenido generado por Quill que requiere su estilo o funcionalidad específicos en el front end.
    -   *Cuando está deshabilitado (NO):* Los archivos principales de Quill *no* se cargarán en el front office, lo que ahorra ancho de banda y potencialmente mejora la velocidad de carga de la página.
-   **Valor recomendado:** **NO** (a menos que tenga una razón específica para cargarlo, como una función de tema personalizada).
-   **Escenario / ejemplo de comerciante:** Si está utilizando un tema personalizado que muestra contenido interactivo (como acordeones o pestañas) creado con MyQuill, y estos elementos no se renderizan correctamente, habilitar esto podría resolver el problema. Para la mayoría de las tiendas, no es necesario.

**3. Cargar editor Quill en el Back Office**
-   **Qué hace este ajuste:** Controla si los activos del editor Quill se cargan en su Back Office de PrestaShop. Esto es esencial para que el módulo funcione.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* El editor Quill se cargará y funcionará correctamente en su Back Office.
    -   *Cuando está deshabilitado (NO):* El editor Quill no se cargará, y probablemente verá un área de editor en blanco o el TinyMCE predeterminado. Esto deshabilita efectivamente la funcionalidad principal del módulo en el Back Office.
-   **Valor recomendado:** **SÍ** (Esto debe estar habilitado para que el módulo funcione).
-   **Escenario / ejemplo de comerciante:** Siempre debe mantener esto habilitado. Deshabilitarlo le impediría usar las funciones de MyQuill en el panel de administración.

**4. Altura del editor (en píxeles)**
-   **Qué hace este ajuste:** Establece la altura predeterminada del área de entrada del editor Quill en píxeles.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece un valor más alto (por ejemplo, 500px):* El editor aparecerá más alto, dándole más espacio vertical para ver y editar su contenido sin desplazarse.
    -   *Cuando se establece un valor más bajo (por ejemplo, 200px):* El editor será más corto, lo que podría ser útil para secciones de contenido más cortas, pero podría requerir más desplazamiento para descripciones más largas.
-   **Valor recomendado:** **300px** (o ajuste según su preferencia para la longitud típica del contenido).
-   **Escenario / ejemplo de comerciante:** Si con frecuencia escribe descripciones de productos muy largas, aumentar esto a 400px o 500px podría hacer que su experiencia de edición sea más cómoda. Para títulos de páginas CMS cortos, una altura menor podría estar bien.

**5. Opciones de la barra de herramientas del editor**
-   **Qué hace este ajuste:** Esto le permite personalizar qué herramientas aparecen en la barra de herramientas del editor Quill. Puede seleccionar o deseleccionar varios botones y funciones.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se seleccionan opciones:* Los botones correspondientes (por ejemplo, negrita, cursiva, imagen, video, tabla) aparecerán en la barra de herramientas del editor, haciendo que esas funciones estén disponibles para usted.
    -   *Cuando se deseleccionan opciones:* Los botones correspondientes se ocultarán de la barra de herramientas, impidiendo su uso.
-   **Valor recomendado:** Habilite todas las opciones inicialmente, luego deseleccione cualquier herramienta que esté seguro de que nunca usará para simplificar la barra de herramientas.
-   **Escenario / ejemplo de comerciante:** Si nunca planea incrustar videos, podría deseleccionar la opción "YouTube/Vimeo" para reducir el desorden en la barra de herramientas. Si desea asegurarse de que su equipo solo use el formato básico, podría limitar significativamente las opciones.

**6. Carpeta de carga de imágenes**
-   **Qué hace este ajuste:** Especifica la carpeta predeterminada en su servidor donde se almacenarán las imágenes cargadas a través del editor Quill.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece una ruta específica (por ejemplo, `/img/cms/`):* Todas las imágenes cargadas a través del editor irán a esa carpeta.
    -   *Cuando se deja como predeterminado (generalmente `/img/cms/` o similar):* Las imágenes se almacenarán en el directorio de imágenes CMS estándar de PrestaShop.
-   **Valor recomendado:** Dejar como predeterminado (`/img/cms/`) a menos que tenga una necesidad organizativa específica para cambiarlo.
-   **Escenario / ejemplo de comerciante:** Si desea mantener las imágenes específicas del producto separadas de las imágenes de la página CMS, podría crear una nueva carpeta (por ejemplo, `/img/products_quill/`) y establecer esta opción en consecuencia. Asegúrese de que la carpeta exista y tenga permisos de escritura.

**7. Habilitar generación de enlaces SEO**
-   **Qué hace este ajuste:** Activa una función que le ayuda a crear enlaces amigables para SEO dentro de su contenido.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* La herramienta de enlaces en Quill ofrecerá opciones para generar enlaces limpios y descriptivos, potencialmente utilizando nombres de productos o categorías como texto del enlace.
    -   *Cuando está deshabilitado (NO):* La herramienta de enlaces se comportará como un insertador de enlaces estándar sin mejoras específicas de SEO.
-   **Valor recomendado:** **SÍ** (para beneficiarse de un mejor enlace interno para SEO).
-   **Escenario / ejemplo de comerciante:** Al enlazar a un producto, en lugar de simplemente pegar la URL, esta función podría ayudarle a generar automáticamente un enlace con el nombre del producto como texto ancla, lo cual es mejor para SEO.

**8. Habilitar incrustación de YouTube/Vimeo**
-   **Qué hace este ajuste:** Le permite incrustar videos de YouTube y Vimeo directamente en su contenido utilizando el editor Quill.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Aparecerá un botón u opción dedicada en la barra de herramientas para pegar fácilmente las URL de los videos e incrustarlos.
    -   *Cuando está deshabilitado (NO):* No podrá usar la herramienta dedicada de incrustación de videos.
-   **Valor recomendado:** **SÍ** (si planea usar videos en su contenido).
-   **Escenario / ejemplo de comerciante:** Puede agregar fácilmente un video de demostración de producto a una descripción de producto o un video de historia de marca a su página "Sobre nosotros".

**9. Habilitar tablas**
-   **Qué hace este ajuste:** Agrega funcionalidad para crear y editar tablas HTML dentro del editor Quill.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Una herramienta de creación de tablas estará disponible en la barra de herramientas, lo que le permitirá insertar y administrar tablas (agregar filas/columnas, fusionar celdas, etc.).
    -   *Cuando está deshabilitado (NO):* La herramienta de tablas estará oculta.
-   **Valor recomendado:** **SÍ** (las tablas son útiles para mostrar datos estructurados como especificaciones o comparaciones).
-   **Escenario / ejemplo de comerciante:** Use tablas para mostrar especificaciones de productos, tablas comparativas o información de tarifas de envío en una página CMS.

**10. Habilitar botones de Bootstrap**
-   **Qué hace este ajuste:** Proporciona una herramienta para insertar fácilmente botones con estilo Bootstrap en su contenido, que se pueden usar para llamadas a la acción.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Aparecerá una herramienta de botones, lo que le permitirá elegir estilos de botones (primario, secundario, éxito, etc.) y vincularlos.
    -   *Cuando está deshabilitado (NO):* La herramienta de botones estará oculta.
-   **Valor recomendado:** **SÍ** (para llamadas a la acción claras).
-   **Escenario / ejemplo de comerciante:** Agregue un botón "Comprar ahora" a un banner promocional en una página CMS o un botón "Descargar PDF" a las especificaciones técnicas de un producto.

**11. Habilitar pestañas**
-   **Qué hace este ajuste:** Le permite crear secciones de contenido con pestañas, útiles para organizar grandes cantidades de información de forma compacta.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Una herramienta de creación de pestañas estará disponible, lo que le permitirá definir títulos de pestañas y contenido para cada pestaña.
    -   *Cuando está deshabilitado (NO):* La herramienta de pestañas estará oculta.
-   **Valor recomendado:** **SÍ** (para una mejor organización del contenido).
-   **Escenario / ejemplo de comerciante:** En una página de producto, use pestañas para "Descripción", "Especificaciones", "Reseñas" e "Información de envío" para mantener la página limpia.

**12. Habilitar galerías**
-   **Qué hace este ajuste:** Integra una función para crear galerías de imágenes simples dentro de su contenido.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Aparecerá una herramienta de galería, lo que le permitirá seleccionar varias imágenes y organizarlas en una galería.
    -   *Cuando está deshabilitado (NO):* La herramienta de galería estará oculta.
-   **Valor recomendado:** **SÍ** (para pantallas de imágenes visualmente atractivas).
-   **Escenario / ejemplo de comerciante:** Muestre múltiples ángulos de un producto o una colección de imágenes de estilo de vida en una página CMS.

**13. Habilitar preguntas frecuentes (Acordeón)**
-   **Qué hace este ajuste:** Agrega una herramienta para crear secciones interactivas de preguntas frecuentes utilizando un formato de acordeón (expandible/colapsable).
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Una herramienta de preguntas frecuentes estará disponible, lo que le permitirá agregar pares de preguntas y respuestas que los usuarios pueden expandir o colapsar.
    -   *Cuando está deshabilitado (NO):* La herramienta de preguntas frecuentes estará oculta.
-   **Valor recomendado:** **SÍ** (excelente para páginas de soporte o preguntas frecuentes de productos).
-   **Escenario / ejemplo de comerciante:** Cree una página CMS dedicada a "Preguntas frecuentes" o agregue una pequeña sección de preguntas frecuentes a una página de producto para abordar las consultas comunes de los clientes.

#### **Botón Guardar**
-   **Qué hace:** Después de realizar cualquier cambio en la configuración de esta página, **debe** hacer clic en el botón "Guardar" para aplicarlos.
-   **Efecto de hacer clic:** Sus cambios se almacenarán en la base de datos, y el editor Quill reflejará estas nuevas configuraciones la próxima vez que lo abra en el Back Office.
-   **Acción recomendada:** Siempre haga clic en "Guardar" después de modificar cualquier ajuste.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

MyQuill se integra principalmente directamente en las pantallas de edición de contenido existentes de PrestaShop (como los formularios de edición de productos, categorías y páginas CMS). No introduce nuevos elementos de menú de nivel superior ni pantallas de gestión de datos dedicadas para su propio contenido. Los controladores "AdminMyquillAjaxController" e "index.php" son componentes internos que manejan las operaciones en segundo plano del módulo, como la carga de imágenes o la carga dinámica de contenido para las funciones del editor.

Por lo tanto, no hay una pantalla "AdminMyquill" separada para que usted la administre. Toda la interacción ocurre directamente dentro de los formularios de edición de contenido donde Quill reemplaza a TinyMCE.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| **Página de configuración del módulo** | Habilitar editor MyQuill | SÍ | Activa/desactiva el editor Quill en el BO. |
| | Cargar editor Quill en el Front Office | NO | Carga los activos de Quill en el FO (solo si el tema/módulo lo necesita). |
| | Cargar editor Quill en el Back Office | SÍ | Carga los activos de Quill en el BO (esencial para el funcionamiento del módulo). |
| | Altura del editor (en píxeles) | 300px | Establece el tamaño vertical de la ventana del editor. |
| | Opciones de la barra de herramientas del editor | Todas habilitadas | Personaliza qué herramientas aparecen en la barra de herramientas del editor. |
| | Carpeta de carga de imágenes | `/img/cms/` | Especifica dónde se almacenan las imágenes cargadas. |
| | Habilitar generación de enlaces SEO | SÍ | Agrega funciones para crear enlaces amigables para SEO. |
| | Habilitar incrustación de YouTube/Vimeo | SÍ | Permite incrustar videos de YouTube/Vimeo. |
| | Habilitar tablas | SÍ | Agrega funcionalidad para crear y editar tablas HTML. |
| | Habilitar botones de Bootstrap | SÍ | Proporciona una herramienta para insertar botones con estilo Bootstrap. |
| | Habilitar pestañas | SÍ | Permite crear secciones de contenido con pestañas. |
| | Habilitar galerías | SÍ | Integra una función para crear galerías de imágenes. |
| | Habilitar preguntas frecuentes (Acordeón) | SÍ | Agrega una herramienta para crear secciones interactivas de preguntas frecuentes. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Después de instalar MyQuill, el área del editor está en blanco o todavía muestra TinyMCE.**
*   **R:** Primero, asegúrese de que "Habilitar editor MyQuill" y "Cargar editor Quill en el Back Office" estén configurados en **SÍ** en la configuración del módulo. Segundo, borre la caché de su PrestaShop: Vaya a **Parámetros avanzados > Rendimiento**, luego haga clic en "Borrar caché" en la esquina superior derecha. Además, borre la caché de su navegador.

**P2: Mis imágenes no se cargan o no puedo verlas después de la carga.**
*   **R:** Verifique la configuración de "Carpeta de carga de imágenes" en la configuración de MyQuill. Asegúrese de que la carpeta especificada exista en su servidor (por ejemplo, `/img/cms/`) y tenga los permisos de escritura correctos (generalmente 755 o 775). Si la carpeta no existe, créela a través de FTP/SFTP.

**P3: Faltan algunos botones de la barra de herramientas (por ejemplo, Tablas, Videos) en el editor.**
*   **R:** Vaya a la página de configuración de MyQuill y verifique la sección "Opciones de la barra de herramientas del editor". Asegúrese de que las funciones específicas que desea usar (por ejemplo, "Habilitar tablas", "Habilitar incrustación de YouTube/Vimeo") estén configuradas en **SÍ**. Guarde sus cambios y borre la caché.

**P4: El contenido creado con MyQuill (como pestañas o acordeones) no se muestra correctamente en mi front office.**
*   **R:** Esto suele ocurrir si su tema no incluye el CSS o JavaScript necesario para estos elementos interactivos. Intente habilitar "Cargar editor Quill en el Front Office" en la configuración de MyQuill. Si el problema persiste, su tema podría requerir bibliotecas específicas de Bootstrap o JavaScript que no se cargan por defecto o están en conflicto. En este caso, es posible que necesite que un webmaster investigue.

**P5: ¿Cómo vuelvo al editor TinyMCE predeterminado?**
*   **R:** Simplemente vaya a **Módulos > Gestor de módulos**, busque "MyQuill - Editor Quill" y haga clic en el botón "Deshabilitar". Todo el contenido creado previamente con MyQuill seguirá ahí, pero la interfaz de edición volverá a TinyMCE. Puede volver a habilitar MyQuill en cualquier momento.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)
Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura
El módulo MyQuill integra el editor de texto enriquecido Quill.js en el Back Office de PrestaShop, reemplazando el TinyMCE predeterminado. Lo logra enganchándose a `displayBackOfficeHeader` para inyectar sus activos y luego usando JavaScript para apuntar e inicializar instancias de Quill en los elementos `textarea` relevantes. El módulo proporciona funciones mejoradas como carga de imágenes, incrustación de videos y bloques de contenido personalizados (tablas, pestañas, galerías, preguntas frecuentes) al extender la funcionalidad de Quill y proporcionar puntos finales AJAX para operaciones del lado del servidor. Evita las sobrescrituras del núcleo, lo que garantiza la compatibilidad y una fácil desinstalación.

### 4.2 Controladores (`controllers/`)

-   **Controladores del Front Office**:
    El módulo no incluye ningún controlador dedicado al front office. Toda la funcionalidad del front office relacionada con la visualización de contenido generado por Quill se maneja mediante la representación del tema del contenido estándar de PrestaShop (descripciones de productos, páginas CMS, etc.) y la carga opcional de los activos del front office de MyQuill a través de hooks.

-   **Controladores de administración del Back Office**:
    *   `controllers/admin/AdminMyquillAjaxController.php`
        *   **Nombre de clase y clase padre**: `AdminMyquillAjaxController` extiende `ModuleAdminController`.
        *   **Responsabilidad**: Este controlador maneja las solicitudes AJAX que se originan en el editor Quill en el Back Office. Su función principal es gestionar las operaciones del lado del servidor, como la carga de imágenes, asegurando que se almacenen correctamente en el directorio designado y devolviendo la URL para su inserción en el editor. También podría manejar otras solicitudes de datos dinámicos para complementos específicos de Quill (por ejemplo, obtener datos de productos para enlaces SEO).
    *   `controllers/admin/index.php`
        *   **Nombre de clase y clase padre**: Este archivo generalmente contiene una simple declaración `die('Access Denied');` o una medida de seguridad similar.
        *   **Responsabilidad**: Es una práctica estándar de PrestaShop incluir un archivo `index.php` en cada directorio para evitar la lista de directorios y el acceso directo. No contiene ninguna lógica de controlador funcional para el módulo.

### 4.3 Clases y modelos del núcleo (`classes/`)
El módulo MyQuill no introduce ninguna clase `ObjectModel` personalizada ni tablas de base de datos. Opera principalmente reemplazando la interfaz del editor y almacenando su configuración en `ps_configuration`. El contenido creado con Quill se almacena directamente en los campos de contenido existentes de PrestaShop (por ejemplo, `ps_product_lang.description`, `ps_cms_lang.content`) como HTML estándar.

### 4.4 Activos de JavaScript (`views/js/`)

-   `views/js/myquill-admin.js`
    *   **Alcance**: Back-office.
    *   **Detalle**: Este es el archivo JavaScript administrativo principal. Es responsable de inicializar el editor Quill en todos los elementos `textarea` relevantes dentro del Back Office de PrestaShop. Lee la configuración del módulo (altura del editor, opciones de la barra de herramientas, funciones habilitadas) y construye dinámicamente la instancia de Quill con los módulos y controladores apropiados. También contiene lógica para integrar botones de barra de herramientas personalizados y manejar sus acciones (por ejemplo, abrir diálogos de carga de imágenes, insertar incrustaciones de video).
-   `views/js/myquill-editor.js`
    *   **Alcance**: Back-office.
    *   **Detalle**: Este archivo probablemente contiene la propia biblioteca principal de Quill.js o personalizaciones/extensiones específicas del editor base de Quill. Define el comportamiento fundamental, la representación y la API del editor.
-   `views/js/myquill-front.js`
    *   **Alcance**: Front-office.
    *   **Detalle**: Este script se carga condicionalmente en el front office si la configuración "Cargar editor Quill en el Front Office" está habilitada. Contiene el JavaScript necesario para que los elementos interactivos creados con Quill (como pestañas, acordeones, galerías) funcionen en el lado de la tienda orientado al cliente. Podría incluir oyentes para eventos de clic en los encabezados de las pestañas o los títulos de los acordeones para alternar la visibilidad del contenido.
-   `views/js/myquill-plugins.js`
    *   **Alcance**: Back-office.
    *   **Detalle**: Este archivo encapsula la lógica JavaScript para varios complementos y extensiones personalizados agregados a Quill por MyQuill. Esto incluye la implementación de funciones como el manejo de carga de imágenes, la incrustación de videos, la creación de tablas, los botones de Bootstrap, las pestañas, las galerías y los acordeones de preguntas frecuentes. Define cómo se renderizan estos "blots" personalizados (término de Quill para bloques de contenido personalizados) y cómo se comportan sus acciones de barra de herramientas asociadas.
-   `views/js/myquill-pro.js`
    *   **Alcance**: Back-office.
    *   **Detalle**: Este archivo probablemente contiene funciones y mejoras avanzadas o "pro" para el editor Quill, que potencialmente se basan en `myquill-plugins.js`. Podría incluir elementos de interfaz de usuario más sofisticados, opciones de formato adicionales o integraciones adicionales específicas de la versión MyPresta.eu del módulo.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `views/css/myquill-admin.css`
    *   **Alcance**: Estilo del formulario de administración del Back Office.
    *   **Detalle**: Contiene estilos específicos para la apariencia del editor Quill dentro del Back Office de PrestaShop. Esto incluye el estilo de la barra de herramientas, el contenedor del editor, los diálogos personalizados y la garantía de que el editor se integre visualmente con el tema de administración de PrestaShop.
-   `views/css/myquill-editor.css`
    *   **Alcance**: Estilo del formulario de administración del Back Office.
    *   **Detalle**: Este archivo probablemente contiene el CSS principal para el propio editor Quill, definiendo estilos base para el formato de texto, citas en bloque, listas y otros elementos estándar de Quill. También podría incluir estilos para blots personalizados (por ejemplo, tablas, botones) cuando se renderizan dentro del editor.
-   `views/css/myquill-front.css`
    *   **Alcance**: Estilo del cliente del Front Office.
    *   **Detalle**: Esta hoja de estilo se carga condicionalmente en el front office si la configuración correspondiente está habilitada. Proporciona el CSS necesario para renderizar correctamente los elementos interactivos creados con MyQuill (como pestañas, acordeones, galerías) en la tienda orientada al cliente. Los desarrolladores pueden anular estos estilos en el `custom.css` o `theme.css` de su tema para que coincidan con su marca.
-   `views/css/quill.snow.css`
    *   **Alcance**: Estilo del formulario de administración del Back Office.
    *   **Detalle**: Esta es la hoja de estilo estándar del tema "Snow" para Quill.js. Proporciona la apariencia visual predeterminada para la barra de herramientas y el área de contenido del editor Quill, incluidos iconos, estilos de botones y formato básico. Este es un componente central de Quill.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    *   `bo-header.tpl`
        *   **Hook**: `displayBackOfficeHeader`
        *   **Salida**: Esta plantilla es responsable de inyectar los activos CSS y JavaScript necesarios (núcleo de Quill, JS/CSS específicos del módulo) en la sección `<head>` de las páginas del Back Office donde se necesita el editor. Incluye archivos dinámicamente según la configuración del módulo.
-   **Plantillas de administración (`views/templates/admin/`)**:
    *   `configure.tpl`
        *   **Salida**: Esta plantilla renderiza el formulario de configuración principal para el módulo MyQuill, accesible a través de **Módulos > Gestor de módulos > Configurar**. Muestra todos los ajustes descritos en la Sección 4.1, incluidos interruptores, campos de entrada y el botón "Guardar".
    *   `preview.tpl`
        *   **Salida**: Esta plantilla podría usarse para una función de vista previa dentro del Back Office, mostrando potencialmente cómo se vería el contenido generado por Quill en el front end. Su uso exacto dependería de la implementación interna del módulo para previsualizar el contenido.

-   **Plantillas del Front Office (`views/templates/front/`)**:
    El módulo no incluye ninguna plantilla dedicada al front office. Todo el contenido generado por Quill se renderiza dentro de las plantillas de tema existentes de PrestaShop (por ejemplo, `product.tpl`, `cms.tpl`) insertando la salida HTML sin procesar del editor.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    El módulo MyQuill no crea ninguna tabla de base de datos personalizada. Todas sus configuraciones se almacenan en la tabla `ps_configuration` utilizando claves típicamente prefijadas con `MYQUILL_`. El contenido creado con el editor se almacena en tablas de contenido estándar de PrestaShop (por ejemplo, `ps_product_lang`, `ps_cms_lang`).

-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
|---|---|---|
| `displayBackOfficeHeader` | Se ejecuta en el `<head>` de las páginas del Back Office. | Inyecta los activos CSS y JavaScript de MyQuill (editor Quill, complementos, estilos de administración) en el Back Office para inicializar el editor. |
| `displayHeader` | Se ejecuta en el `<head>` de las páginas del Front Office. | Inyecta condicionalmente los activos CSS y JavaScript del front office de MyQuill si "Cargar editor Quill en el Front Office" está habilitado, para garantizar que los elementos interactivos (pestañas, acordeones) funcionen correctamente. |
| `displayFooter` | Se ejecuta al final del `<body>` de las páginas del Front Office. | Potencialmente utilizado para inyectar scripts de carga tardía o recursos adicionales para elementos interactivos del front office, si no se maneja con `displayHeader`. |
| `displayProductExtraContent` | Se ejecuta en la página del producto. | Permite inyectar bloques de contenido adicionales en la página del producto, potencialmente útil para contenido personalizado generado por Quill si el módulo se extendiera para administrar dichos bloques directamente. (Menos probable que sea utilizado directamente por la función de reemplazo del editor principal de MyQuill, pero disponible para extensiones). |
| `displayLeftColumn` | Se ejecuta en la columna izquierda de las páginas del Front Office. | Similar a `displayProductExtraContent`, proporciona un hook para inyectar contenido en la columna izquierda. |
| `displayRightColumn` | Se ejecuta en la columna derecha de las páginas del Front Office. | Similar a `displayProductExtraContent`, proporciona un hook para inyectar contenido en la columna derecha. |

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo MyQuill - Editor Quill, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Puede descargar las versiones más recientes de su historial de pedidos y acceder a los recursos de soporte directamente desde el sitio web de MyPresta.eu.

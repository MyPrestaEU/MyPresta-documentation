---
title: "tinyMCE pro - editor de texto enriquecido extendido - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop tinyMCE pro - editor de texto enriquecido extendido de MyPresta.eu."
sidebar:
  label: "tinyMCE pro - editor de texto enriquecido extendido - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo tinyMCE pro - extended rich text editor en MyPresta.eu](https://mypresta.eu/modules/administration-tools/tinymce-pro-extended-rich-text-editor.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/tinymce-pro-extended-rich-text-editor/)
>
> ---


# tinyMCE pro - editor de texto enriquecido extendido

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Por lo general, no se necesitan configuraciones especiales del servidor más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" para acceder a la configuración principal del módulo. Esta pantalla le permite habilitar o deshabilitar el editor mejorado y administrar sus funcionalidades principales.

La página de configuración de "tinyMCE pro" está diseñada para ser simple, ya que el módulo funciona principalmente reemplazando y mejorando el editor existente sin configuraciones extensas orientadas al usuario más allá de su activación.

- **Qué hace esta configuración:** Este módulo funciona principalmente reemplazando el editor predeterminado de PrestaShop con una versión mejorada de tinyMCE. La página de configuración normalmente contendrá un interruptor de "Habilitar/Deshabilitar" para el módulo en sí, y potencialmente opciones para controlar a qué áreas específicas del back office debe aplicarse el editor mejorado.
- **Efecto de cambiar esta configuración:**

  - *Cuando está habilitado:* El editor de texto estándar, a menudo limitado, en áreas como descripciones de productos, páginas CMS y descripciones de categorías será reemplazado por el editor "tinyMCE pro". Este nuevo editor contará con una barra de herramientas más rica con opciones para iconos de Font Awesome, incrustación de videos de YouTube, aceptación de código HTML/JavaScript avanzado y más.
  - *Cuando está deshabilitado:* El módulo dejará de funcionar y PrestaShop volverá a su editor de texto predeterminado. Todas las funciones avanzadas proporcionadas por "tinyMCE pro" ya no estarán disponibles.
- **Valor recomendado:** **Habilitado**. Para beneficiarse de las funciones del módulo, siempre debe estar habilitado.
- **Escenario / ejemplo de comerciante:** Está editando la descripción de un producto nuevo. Con "tinyMCE pro" habilitado, puede agregar fácilmente un video de YouTube que muestre el producto, incluir iconos de Font Awesome para las características (por ejemplo, un icono de marca de verificación para "En stock") y usar formato avanzado para crear un diseño visualmente atractivo, todo directamente dentro del editor. Si está deshabilitado, se limitaría al formato de texto básico.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | **Estado del Módulo (Habilitar/Deshabilitar)** | Habilitado | Controla si el editor tinyMCE mejorado reemplaza el editor predeterminado de PrestaShop en el back office. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: He habilitado el módulo, pero el editor sigue igual. ¿Qué debo hacer?**
**R1:** Después de habilitar cualquier módulo que modifique el back office, es una buena práctica borrar la caché de su navegador y la caché de Smarty de PrestaShop.
- **Caché del Navegador:** Actualice su navegador (Ctrl+F5 o Cmd+Shift+R).
- **Caché de PrestaShop:** Vaya a **Parámetros Avanzados > Rendimiento** en el back office de su PrestaShop. Haga clic en el botón "Borrar caché" en la esquina superior derecha.

**P2: Algunas de las nuevas funciones del editor (como los iconos de Font Awesome) no se muestran correctamente en mi front office.**
**R2:** Esto generalmente indica un conflicto con el CSS o JavaScript de su tema personalizado.
- **Verifique Conflictos:** Cambie temporalmente al tema predeterminado de PrestaShop (Classic o Hummingbird) y verifique si las funciones se muestran correctamente. Si lo hacen, el problema está en su tema personalizado.
- **Personalización del Tema:** Su tema podría estar sobrescribiendo o no incluyendo el CSS/JS necesario para estos elementos. Es posible que deba consultar a su desarrollador de temas o a un webmaster para integrar correctamente los activos del front office del módulo en su tema.

**P3: ¿Puedo usar este editor para todos los idiomas de mi tienda?**
**R3:** Sí, el editor tinyMCE está diseñado para funcionar sin problemas con las capacidades multilingües de PrestaShop. Cuando cambie de idioma en el back office, el editor seguirá estando disponible para que ingrese contenido en el idioma seleccionado. El módulo también incluye archivos de idioma para muchos de sus plugins (por ejemplo, Font Awesome, PowerPaste), lo que garantiza una experiencia localizada donde esté disponible.

**P4: Estoy viendo un error después de instalar el módulo, o mi back office está lento.**
**R4:**
- **Verifique los Registros de Errores del Servidor:** El primer paso siempre es verificar los registros de errores de PHP de su servidor. Estos registros a menudo proporcionan detalles específicos sobre lo que salió mal.
- **Deshabilite Otros Módulos:** Deshabilite temporalmente otros módulos recientemente instalados o complejos para descartar conflictos.
- **Versión de PHP:** Asegúrese de que su versión de PHP esté dentro del rango compatible (PHP 7.1 - 8.5). Una versión de PHP incompatible puede causar varios problemas.
- **Contacte con Soporte:** Si el problema persiste, recopile cualquier mensaje de error y contacte con el soporte de MyPresta.eu para obtener ayuda.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo `tinyMCE pro` funciona principalmente sobrescribiendo la clase `Validate` predeterminada de PrestaShop para garantizar la compatibilidad con el contenido HTML extendido generado por el editor tinyMCE mejorado. Inyecta su propia versión de la biblioteca tinyMCE y una multitud de plugins en el back office, reemplazando efectivamente el editor estándar. La lógica central del módulo reside en `index.php`, que maneja la instalación, desinstalación y el formulario de configuración. Aprovecha el sistema de hooks de PrestaShop para cargar sus activos e inicializar el editor donde sea necesario.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front office o back office. Su funcionalidad se integra principalmente a través del archivo principal del módulo (`index.php`) y sobrescribiendo las clases principales de PrestaShop.

### 4.3 Clases y Modelos Principales (`classes/`)

-   **`tinymcepro/override/classes/index.php`**: Este archivo es típicamente un marcador de posición vacío para evitar la lista de directorios, una práctica de seguridad común. No contiene ninguna definición de clase funcional.
-   **`tinymcepro/override/classes/Validate.php`**:
    -   **Propósito**: Esta es una sobrescritura crucial. La clase `Validate` de PrestaShop es responsable de sanear y validar varias entradas, incluido el contenido HTML. El método `isCleanHtml()` predeterminado puede ser demasiado restrictivo para contenido enriquecido, eliminando elementos HTML5 válidos, atributos o JavaScript que el editor tinyMCE extendido podría generar.
    -   **Lógica de Sobrescritura**: Esta sobrescritura probablemente modifica o extiende el método `isCleanHtml()` (o métodos de validación relacionados) para permitir un rango más amplio de HTML, atributos y potencialmente scripts/estilos incrustados, asegurando que el contenido generado por tinyMCE pro no sea eliminado o considerado inválido por la validación central de PrestaShop.
    -   **Impacto**: Los desarrolladores deben ser conscientes de que esta sobrescritura cambia el comportamiento de validación central. Si existen reglas de validación personalizadas o si otros módulos dependen de un `isCleanHtml()` estricto, podrían surgir conflictos.

### 4.4 Activos JavaScript (`views/js/`)

El módulo incluye una gran cantidad de archivos JavaScript, principalmente para la biblioteca central de tinyMCE y sus numerosos plugins.

-   **`tinymcepro/js/accordion.js`**: Probablemente un script personalizado para manejar la funcionalidad de acordeón en el front office, posiblemente relacionado con el plugin `bootstrapaccordion` de tinyMCE.
-   **`tinymcepro/js/alerts.js`**: Script personalizado para manejar mensajes de alerta, potencialmente vinculado a un plugin de alerta de Bootstrap.
-   **`tinymcepro/js/fancybox.js`**: Integración de la biblioteca Fancybox para lightboxes, probablemente utilizada para la visualización de imágenes o medios dentro de la salida del editor.
-   **`tinymcepro/js/readmore.js`**: Script para implementar la funcionalidad "leer más", colapsando secciones de contenido largas.
-   **`tinymcepro/js/tinymce-cmscategory.js`**: Script de inicialización o configuración específico para tinyMCE cuando se usa en campos de descripción de CMS o categoría.
-   **`tinymcepro/lib/htmlTemplatesManager/js/htmlTemplatesManager.js`**: JavaScript central para el plugin HTML Templates Manager, que permite la creación, edición e inserción de fragmentos HTML predefinidos.
-   **`tinymcepro/lib/plugins/bootstrapaccordion/plugin.js`**: Plugin de tinyMCE para insertar y administrar acordeones estilo Bootstrap.
-   **`tinymcepro/lib/plugins/codesample/plugin.js`**: Plugin de tinyMCE para insertar y resaltar sintaxis de muestras de código. Incluye `prism.css` para el estilo.
-   **`tinymcepro/lib/plugins/editattributes/plugin.js`**: Plugin de tinyMCE para editar fácilmente los atributos HTML de los elementos seleccionados.
-   **`tinymcepro/lib/plugins/fontawesome/langs/*.js`**: Archivos de idioma para el plugin Font Awesome de tinyMCE.
-   **`tinymcepro/lib/plugins/lineheight/index.js`, `langs/de.js`, `plugin.js`**: Plugin de tinyMCE para controlar la altura de línea del texto.
-   **`tinymcepro/lib/plugins/paragraph/*.js`**: Un plugin complejo para administrar estilos de párrafo y potencialmente mostrar elementos de bloque. Incluye varios scripts de utilidad internos.
-   **`tinymcepro/lib/plugins/powerpaste/*.js`**: Plugin avanzado de tinyMCE para limpiar y sanear contenido pegado de Microsoft Word, Google Docs, etc. Incluye muchos archivos de idioma.
-   **`tinymcepro/lib/plugins/smileys/plugin.js`**: Plugin de tinyMCE para insertar emojis/smileys.
-   **`tinymcepro/lib/plugins/youtube/includes/youtube.js`, `plugin.js`**: Plugin de tinyMCE para incrustar videos de YouTube.
-   **`tinymcepro/lib/tinymce.inc.js`**: Probablemente el archivo principal de la biblioteca central de tinyMCE, o un archivo de compilación/configuración personalizado para el editor.
-   **`tinymcepro/lib/tinymce_loader.js`**: Script responsable de cargar e inicializar las instancias del editor tinyMCE en todo el back office de PrestaShop.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   **`tinymcepro/css/tinymcepro.css`**: Estilos personalizados generales para el módulo, potencialmente para su página de configuración o elementos del front office.
-   **`tinymcepro/css.css`**: Otra hoja de estilo general, posiblemente para versiones anteriores de PrestaShop o elementos específicos de la interfaz de usuario.
-   **`tinymcepro/lib/editor.css`**: CSS central para el propio editor tinyMCE, que define su apariencia dentro del back office.
-   **`tinymcepro/lib/htmlTemplatesManager/css/htmlTemplatesManager.css`**: Estilos para la interfaz del Gestor de Plantillas HTML.
-   **`tinymcepro/lib/iconset.css`**: Probablemente contiene estilos para iconos personalizados utilizados dentro del editor o módulo.
-   **`tinymcepro/lib/plugins/bs_alert/assets/css/bootstrap.css`, `plugin.css`**: CSS de Bootstrap y estilos de plugin específicos para el plugin Bootstrap Alert de tinyMCE.
-   **`tinymcepro/lib/plugins/bs_images/assets/css/bootstrap.css`, `plugin.css`**: CSS de Bootstrap y estilos de plugin específicos para el plugin Bootstrap Images de tinyMCE.
-   **`tinymcepro/lib/plugins/codesample/css/prism.css`**: Hoja de estilo para el resaltado de sintaxis utilizado por el plugin `codesample`.
-   **`tinymcepro/lib/plugins/powerpaste/css/editorcss.css`**: Estilos específicos para el plugin PowerPaste, potencialmente para la retroalimentación visual durante el pegado.
-   **`tinymcepro/lib/plugins/tinyplusBootstrapTools/flat-blue.css`, `res-show-blocks-style.css`**: Estilos adicionales relacionados con Bootstrap o la visualización de bloques, posiblemente para temas o herramientas de editor específicos.
-   **`tinymcepro/lib/plugins/youtube/includes/youtube.css`**: Estilos para la funcionalidad de incrustación de videos de YouTube.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **`tinymcepro/header.tpl`**: Esta plantilla probablemente está enganchada a `displayHeader` para cargar los activos CSS y JavaScript necesarios para el módulo, tanto en el back office (para el propio editor) como potencialmente en el front office (para contenido renderizado como acordeones o fancybox).
-   **`tinymcepro/lib/htmlTemplatesManager/views/buttonManager.tpl`**: Plantilla para el botón o la interfaz que abre el Gestor de Plantillas HTML.
-   **`tinymcepro/lib/htmlTemplatesManager/views/createTemplateForm.tpl`**: Plantilla de formulario para crear nuevas plantillas HTML.
-   **`tinymcepro/lib/htmlTemplatesManager/views/editTemplateForm.tpl`**: Plantilla de formulario para editar plantillas HTML existentes.
-   **`tinymcepro/lib/htmlTemplatesManager/views/mainForm.tpl`**: La plantilla de interfaz principal para el Gestor de Plantillas HTML.
-   **`tinymcepro/lib/htmlTemplatesManager/views/selectInput.tpl`**: Una plantilla reutilizable para una entrada de selección desplegable dentro del gestor de plantillas.
-   **`tinymcepro/views/admin/fonts.tpl`**: Plantilla relacionada con la selección o visualización de fuentes, posiblemente para la integración de fuentes personalizadas dentro del editor.
-   **`tinymcepro/views/admin/form.tpl`**: La plantilla principal del formulario de configuración para el módulo, renderizada a través de `getContent()` en `index.php`.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**: Este módulo no parece crear tablas SQL personalizadas. Sus configuraciones se almacenan en `ps_configuration` (por ejemplo, `PS_TINYMCEPRO_ENABLED`). Las plantillas HTML creadas a través del `htmlTemplatesManager` podrían almacenarse en una tabla personalizada o serializadas en `ps_configuration` también, aunque no hay un archivo SQL explícito presente, lo que sugiere una creación dinámica o almacenamiento de configuración.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Se renderiza en la sección `<head>` del back office de PrestaShop. | Inyecta los archivos CSS y JavaScript necesarios para que el editor tinyMCE y sus plugins funcionen. Aquí es donde se cargan la biblioteca central de tinyMCE y sus scripts de inicialización. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración establece sus activos de medios. | Permite que el módulo agregue sus archivos JS/CSS específicos a la página de administración actual, asegurando que el editor tinyMCE se cargue solo en las páginas donde se necesita (por ejemplo, edición de productos, edición de páginas CMS). |
| `actionGetContentEditor` | (Si es un hook personalizado) | Este hook se usaría para reemplazar la instancia del editor predeterminado con el editor tinyMCE mejorado del módulo. |
| `displayHeader` | Se renderiza en la sección `<head>` del front office. | Potencialmente carga activos específicos del front office (como `accordion.js`, `fancybox.js`, `tinymcepro.css`) si el contenido generado por el editor requiere un estilo o JavaScript especial para mostrarse correctamente (por ejemplo, acordeones, lightboxes). |
| `displayRightColumn` | Se renderiza en la columna derecha del front office. | (Es poco probable que se use directamente para la funcionalidad del editor, pero podría usarse para mostrar contenido *creado* por el editor si el módulo tuviera un widget de front office). |
| `displayLeftColumn` | Se renderiza en la columna izquierda del front office. | (Similar a `displayRightColumn`). |
| `displayFooter` | Se renderiza en el pie de página del front office. | Podría usarse para cargar JavaScript o CSS no críticos para la visualización del front office. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y cualquier otra asistencia con el módulo "tinyMCE pro - editor de texto enriquecido extendido", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con la instalación, configuración y solución de problemas.

---
title: "Gestor de Medios / Archivos - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Gestor de Medios / Archivos de MyPresta.eu."
sidebar:
  label: "Gestor de Medios / Archivos - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Media / Files Manager en MyPresta.eu](https://mypresta.eu/modules/administration-tools/media-files-manager.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/media-files-manager/)
>
> ---


# Gestor de Medios / Archivos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. El módulo requiere permisos de escritura en los directorios que gestiona, lo cual es estándar para las instalaciones de PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, será dirigido a la página de configuración del módulo. Esta página sirve principalmente para integrar el gestor de archivos en su back office de PrestaShop y gestionar sus ajustes principales.

La pantalla de configuración principal mostrará la interfaz del gestor de archivos directamente. Esta interfaz es un navegador de archivos con todas las funciones, similar a lo que vería en su ordenador, pero operando en los archivos de su servidor.

**Áreas clave y funcionalidad dentro de la interfaz del Gestor de Archivos:**

1.  **Panel de Navegación (Barra lateral izquierda):**

    -   **Qué hace:** Muestra una estructura en forma de árbol de los directorios de su servidor, típicamente comenzando desde la carpeta raíz de su PrestaShop. Puede hacer clic en las carpetas para navegar a través de ellas.
    -   **Efecto de usar esto:** Le permite saltar rápidamente entre diferentes partes de su instalación de PrestaShop (por ejemplo, `img/p` para imágenes de productos, `themes/yourtheme/css` para hojas de estilo).
    -   **Valor recomendado:** Úselo para navegar a la carpeta específica donde desea gestionar archivos.
2.  **Área de Listado de Archivos (Panel principal):**

    -   **Qué hace:** Muestra el contenido (archivos y subcarpetas) de la carpeta actualmente seleccionada. Verá nombres de archivos, tamaños, tipos y fechas de modificación.
    -   **Efecto de usar esto:** Aquí es donde realizará la mayoría de sus operaciones con archivos.
    -   **Valor recomendado:** Familiarícese con los iconos y la información presentada para cada archivo.
3.  **Barra de Herramientas (Parte superior del Área de Listado de Archivos):**

    -   **Qué hace:** Contiene varios botones y herramientas para operaciones con archivos. Las herramientas comunes incluyen:
        -   **Subir:** Subir archivos desde su ordenador a la carpeta actual del servidor.
        -   **Nueva Carpeta:** Crear un nuevo directorio.
        -   **Nuevo Archivo:** Crear un nuevo archivo vacío (por ejemplo, un archivo `.txt`, `.html` o `.css`).
        -   **Copiar, Cortar, Pegar:** Manipulación estándar de archivos.
        -   **Renombrar:** Cambiar el nombre de un archivo o carpeta.
        -   **Eliminar:** Eliminar archivos o carpetas (¡use con extrema precaución!).
        -   **Editar:** Abrir un editor de texto para archivos de texto seleccionados (por ejemplo, `.php`, `.css`, `.js`, `.html`).
        -   **Vista Previa:** Ver imágenes u otros tipos de archivos compatibles directamente.
        -   **Buscar:** Encontrar archivos dentro del directorio actual o recursivamente.
        -   **Opciones de Vista:** Cambiar cómo se muestran los archivos (lista, iconos, etc.).
    -   **Efecto de usar estas herramientas:** Manipula directamente archivos y carpetas en su servidor.
    -   **Valor recomendado:** Siempre verifique sus selecciones antes de realizar acciones como "Eliminar" o "Renombrar".
4.  **Menú Contextual (Clic derecho):**

    -   **Qué hace:** Hacer clic derecho en un archivo o carpeta a menudo abre un menú contextual con acceso rápido a operaciones comunes como "Abrir", "Editar", "Renombrar", "Eliminar", "Descargar", "Obtener Información", etc.
    -   **Efecto de usar esto:** Proporciona una forma más rápida de realizar acciones en elementos individuales.
    -   **Valor recomendado:** Explore las opciones del clic derecho para diferentes tipos de archivos.

**Configuraciones específicas (si las hay, basadas en `mypresta_updates`, `update_`, `updatev_`):**

El método `getContent()` del módulo principalmente renderiza la propia interfaz del gestor de archivos. Las claves de configuración `mypresta_updates`, `update_` y `updatev_` son claves internas estándar utilizadas por los módulos de MyPresta.eu para gestionar las notificaciones de actualización y las comprobaciones de versión. Estas no son configuraciones con las que usted interactúe directamente como comerciante.

-   **Qué hacen estas configuraciones:** Son indicadores internos que ayudan al módulo a comunicarse con el servidor de actualizaciones de MyPresta.eu para buscar nuevas versiones y mostrar notificaciones en su back office de PrestaShop si hay una actualización disponible.
-   **Efecto de cambiar estas configuraciones:** No puede cambiarlas directamente. Se gestionan automáticamente por el módulo. Si se alteraran manualmente (lo cual no se recomienda), podría afectar la capacidad del módulo para notificarle sobre nuevas versiones.
-   **Valor recomendado:** Déjelas como están. Son para la gestión interna del módulo.
-   **Escenario / ejemplo de comerciante:** No necesita preocuparse por esto. El módulo le informará automáticamente si se lanza una nueva versión, pidiéndole que la descargue e instale desde su cuenta MyPresta.eu.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

Este módulo no introduce ninguna pantalla de administración dedicada adicional ni controladores personalizados más allá de su página de configuración principal. Toda la funcionalidad de gestión de archivos está incrustada directamente dentro de la interfaz de configuración del módulo.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista           | Ajuste / Opción                               | Predeterminado / Recomendado | Propósito e Impacto                                                               |
| :------------------------- | :-------------------------------------------- | :--------------------------- | :------------------------------------------------------------------------------- |
| Página de Configuración del Módulo | **Panel de Navegación**                       | N/A                          | Explorar directorios del servidor.                                               |
| Página de Configuración del Módulo | **Área de Listado de Archivos**               | N/A                          | Ver e interactuar con archivos/carpetas.                                         |
| Página de Configuración del Módulo | **Barra de Herramientas (Subir, Nueva Carpeta, Editar, Eliminar, etc.)** | N/A                          | Realizar operaciones con archivos (subir, crear, modificar, eliminar).           |
| Página de Configuración del Módulo | **Menú Contextual (Clic derecho)**            | N/A                          | Acceso rápido a operaciones con archivos.                                        |
| Página de Configuración del Módulo | `mypresta_updates`                            | Interno                      | Indicador interno para notificaciones de actualización.                          |
| Página de Configuración del Módulo | `update_`                                     | Interno                      | Indicador interno para notificaciones de actualización.                          |
| Página de Configuración del Módulo | `updatev_`                                    | Interno                      | Indicador interno para notificaciones de actualización.                          |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Subí una imagen, pero no aparece en la página de mi producto.**
R:

-   **Verifique la ruta:** Asegúrese de haber subido la imagen al directorio correcto que PrestaShop espera (generalmente `img/p/` seguido de subcarpetas).
-   **Borrar caché:** A veces, la caché de PrestaShop (o la caché de su navegador) puede impedir que las nuevas imágenes se muestren inmediatamente. Vaya a **Parámetros Avanzados > Rendimiento** en su back office y haga clic en "Borrar caché". Además, intente borrar la caché de su navegador.
-   **Permisos:** Asegúrese de que la carpeta donde subió la imagen tenga los permisos de escritura correctos (generalmente 755 o 775). Aunque el módulo suele encargarse de esto, a veces las configuraciones del servidor pueden ser estrictas.

**P: Edité un archivo CSS, pero el diseño de mi tienda no ha cambiado.**
R:

-   **Borrar caché:** Esta es la razón más común. Vaya a **Parámetros Avanzados > Rendimiento** y borre la caché de PrestaShop. Además, borre la caché de su navegador (Ctrl+F5 o Cmd+R suele forzar una actualización completa).
-   **Archivo correcto:** Verifique que editó el archivo CSS correcto que su tema está cargando realmente. Algunos temas usan CSS compilado o múltiples hojas de estilo.
-   **Errores de sintaxis:** Si introdujo un error de sintaxis en su CSS, podría impedir que la hoja de estilo se cargue correctamente. Use las herramientas de desarrollo de su navegador (F12) para buscar errores de CSS.

**P: Accidentalmente eliminé un archivo/carpeta. ¿Puedo recuperarlo?**
R:

-   **Restaurar inmediatamente desde la copia de seguridad:** Por eso las copias de seguridad regulares son cruciales. Si tiene una copia de seguridad reciente de los archivos de su servidor, restaure el elemento eliminado desde allí.
-   **Contacte a su proveedor de alojamiento:** Algunos proveedores de alojamiento mantienen copias de seguridad diarias y podrían restaurar archivos individuales para usted.
-   **Precaución:** El módulo en sí no tiene una función de "papelera" o "deshacer". La eliminación es permanente.

**P: El gestor de archivos se ve roto o no carga correctamente.**
R:

-   **Verifique la consola del navegador:** Abra las herramientas de desarrollo de su navegador (F12) y busque cualquier error en la pestaña "Consola". Esto puede indicar conflictos de JavaScript o problemas del lado del servidor.
-   **Conflictos de módulos:** Intente deshabilitar otros módulos instalados recientemente para ver si hay un conflicto.
-   **Registros de errores del servidor:** Verifique los registros de errores de PHP de su servidor para cualquier error relacionado.
-   **Permisos:** Asegúrese de que los propios archivos y carpetas del módulo tengan los permisos de lectura/escritura correctos.

**P: ¿Puedo restringir el acceso a ciertas carpetas para diferentes usuarios administradores?**
R:

-   Este módulo, en su versión actual, proporciona una única interfaz de gestor de archivos con acceso completo. El sistema de permisos nativo de PrestaShop para módulos generalmente otorga acceso completo o ningún acceso a la configuración del módulo. Los permisos granulares a nivel de carpeta para diferentes usuarios del back office no son una característica incorporada de este módulo específico. Necesitaría un desarrollo personalizado para implementar dicha característica.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Gestor de Medios / Archivos" (`fmpro`) está construido alrededor del popular gestor de archivos de código abierto **elFinder**. Integra elFinder directamente en el back office de PrestaShop, principalmente a través del método `getContent()` del módulo. Esto significa que la lógica central de gestión de archivos y la interfaz de usuario son manejadas por el robusto backend de JavaScript y PHP de elFinder, con el módulo de PrestaShop actuando como un envoltorio y punto de entrada.

El módulo en sí es un módulo estándar de PrestaShop, que extiende `Module`. No introduce tablas de base de datos personalizadas (más allá de `ps_configuration` para sus propias configuraciones internas) ni estructuras `ObjectModel` complejas. Su función principal es instanciar y configurar la biblioteca elFinder dentro del contexto de administración de PrestaShop.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores personalizados de front-office o back-office en el sentido tradicional de PrestaShop (es decir, archivos en `controllers/front/` o `controllers/admin/`).
La propia biblioteca elFinder tiene su propio conector de backend (típicamente un script PHP) que maneja las operaciones de archivos. Este conector probablemente está integrado o se llama directamente desde el archivo principal del módulo `fmpro.php` o un script PHP separado dentro del directorio `fmpro/php/`, actuando como el manejador del lado del servidor para las solicitudes AJAX de elFinder.

### 4.3 Clases y Modelos Principales (`classes/`)

El módulo no define ninguna clase o modelo personalizado dentro de un directorio `classes/`. La lógica central para la gestión de archivos es manejada por la biblioteca elFinder integrada.

### 4.4 Activos JavaScript (`views/js/`)

El módulo depende en gran medida de JavaScript para su interfaz de front-end, principalmente la biblioteca elFinder. Todos los archivos JS se encuentran en `fmpro/js/`.

-   `fmpro/js/elfinder.full.js`: Este es el archivo principal de la biblioteca elFinder, que contiene toda la funcionalidad central para la interfaz de usuario del gestor de archivos, las interacciones y la comunicación AJAX con el backend. Es un script completo que impulsa toda la interfaz.
-   `fmpro/js/extras/editors.default.js`: Proporciona funcionalidad de editor de texto predeterminada dentro de elFinder, permitiendo a los usuarios editar archivos basados en texto directamente.
-   `fmpro/js/extras/quicklook.googledocs.js`: Mejora la función de "vista rápida" integrándose con Google Docs para previsualizar ciertos tipos de documentos.
-   `fmpro/js/i18n/elfinder.*.js`: Una gran colección de archivos de internacionalización (i18n), que proporcionan traducciones para la interfaz de elFinder a varios idiomas (por ejemplo, `elfinder.fr.js` para francés, `elfinder.es.js` para español). Estos se cargan según la configuración de idioma del usuario.
-   `fmpro/js/i18n/help/*.html.js`: Contiene contenido de ayuda localizado para la interfaz de elFinder, incrustado como cadenas de JavaScript.
-   `fmpro/js/proxy/elFinderSupportVer1.js`: Probablemente una capa de compatibilidad o script proxy para versiones anteriores de elFinder o configuraciones de servidor específicas.
-   `fmpro/js/worker/calcfilehash.js`: Un script de web worker para calcular hashes de archivos, potencialmente utilizado para comprobaciones de integridad o almacenamiento en caché.
-   `fmpro/js/worker/quicklook.tiff.js`: Un script de web worker específicamente para manejar previsualizaciones de imágenes TIFF.
-   `fmpro/js/worker/quicklook.unzip.js`: Un script de web worker para manejar previsualizaciones o listado de contenido de archivos ZIP.

**Notas para desarrolladores:**

-   La biblioteca elFinder es autocontenida. Los desarrolladores que extiendan el módulo interactuarían principalmente con la API de elFinder si necesitaran personalizar su comportamiento o integrarlo con otros componentes.
-   Para el estilo, se prefiere generalmente CSS personalizado a la modificación de estos archivos JS principales.
-   Para la localización, asegúrese de que el archivo `elfinder.LANG.js` correcto se cargue según el idioma del back office de PrestaShop.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El módulo incluye archivos CSS para estilizar la interfaz de elFinder. Estos se encuentran en `fmpro/css/`.

-   `fmpro/css/elfinder.full.css`: Esta es la hoja de estilo principal para la interfaz de elFinder, que define el diseño, los iconos, los colores y la apariencia visual general del gestor de archivos.
-   `fmpro/css/theme.css`: Este archivo probablemente contiene estilos adicionales o anulaciones para integrar elFinder de manera más fluida con el tema del back office de PrestaShop, o para proporcionar ajustes de tema específicos para elFinder.

**Notas para desarrolladores:**

-   Para personalizar la apariencia del gestor de archivos, los desarrolladores deben crear su propio archivo CSS y cargarlo *después* de `elfinder.full.css` y `theme.css` para anular estilos específicos.
-   Los selectores de clase CSS clave suelen tener el prefijo `elfinder-` (por ejemplo, `.elfinder-navbar`, `.elfinder-cwd-wrapper`).

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El módulo no lista explícitamente ningún archivo `.tpl` en un directorio `views/templates/` en el inventario proporcionado. Esto sugiere que la interfaz de elFinder se renderiza directamente a través de JavaScript y HTML generado dentro del método `getContent()` del archivo principal `fmpro.php`, o que el mecanismo de plantillas propio de elFinder se utiliza internamente, sin exponer archivos `.tpl` en la estructura `views/templates/` del módulo.

El método `getContent()` probablemente generará el contenedor HTML necesario (`<div>`) donde el JavaScript de elFinder inicializará y renderizará el gestor de archivos.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

**Tablas de Base de Datos**:
El módulo no crea ninguna tabla de base de datos personalizada. Almacena sus configuraciones internas (como `mypresta_updates`, `update_`, `updatev_`) en la tabla estándar `ps_configuration` de PrestaShop.

-   `ps_configuration`:
    -   `name`: `MYPRESTA_UPDATES_FMPRO` (o similar, para comprobaciones de actualización)
    -   `name`: `UPDATE_FMPRO` (o similar, para comprobaciones de actualización)
    -   `name`: `UPDATEV_FMPRO` (o similar, para comprobaciones de actualización)

**Tabla de Hooks Registrados**:
La función principal del módulo es proporcionar una herramienta administrativa, por lo que no suele registrar muchos hooks de front-office. La descripción del módulo menciona "Hooks de Front-Office: Header, Columns, Product, or Footer", pero esto es probablemente una declaración genérica para los módulos de MyPresta.eu y no específica de la implementación real de este módulo, ya que es una herramienta de administración.

Basado en su naturaleza como herramienta de administración, el módulo interactuaría principalmente con hooks de back-office, si los hubiera, para agregar elementos de menú o integrarse en páginas de administración existentes. Sin embargo, la información proporcionada no lista explícitamente ningún hook registrado. El punto de integración más común para un módulo de este tipo es directamente a través de su método `getContent()`, al que se accede al hacer clic en "Configurar" en el Gestor de Módulos.

Si registrara algún hook, los comunes para herramientas de administración podrían incluir:

-   `displayBackOfficeHeader`: Para incluir sus activos CSS/JS en el back office.
-   `displayAdminProductsExtra`: (Menos probable para un gestor de archivos general, pero posible para cargas de archivos específicas relacionadas con productos).
-   `actionAdminControllerSetMedia`: Para cargar activos para su página de configuración.

Dado el diseño del módulo, su punto de entrada principal es su página de configuración, donde se inicializa la instancia de elFinder.

## 5. Soporte Oficial y Actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y las últimas versiones del módulo "Gestor de Medios / Archivos", consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad del módulo y su integración con su tienda PrestaShop.
"""

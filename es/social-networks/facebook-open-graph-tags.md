---
title: "Etiquetas Open Graph de Facebook - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Etiquetas Open Graph de Facebook' de MyPresta.eu."
sidebar:
  label: "Etiquetas Open Graph de Facebook - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook Open Graph Tags en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-open-graph-tags.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-open-graph-tags/)
>
> ---


# Etiquetas Open Graph de Facebook

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.3.x, 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y generalmente están habilitadas por defecto en la mayoría de los entornos de alojamiento.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Etiquetas Open Graph de Facebook)

Esta es la pantalla de configuración principal donde controlas el comportamiento central del módulo.

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo de comerciante |
| --- | --- | --- | --- | --- |
| **Habilitar Etiquetas Open Graph** | Este interruptor maestro controla si el módulo genera alguna etiqueta Open Graph. | *Cuando está habilitado:* El módulo inyectará las etiquetas Open Graph necesarias en la sección `<head>` del HTML de tu tienda, permitiendo a Facebook mostrar vistas previas enriquecidas. *Cuando está deshabilitado:* Este módulo no generará etiquetas Open Graph, y Facebook intentará adivinar el contenido, lo que a menudo resulta en vistas previas deficientes o faltantes. | **SÍ** | Quieres que las publicaciones de tus productos se vean profesionales en Facebook. |
| **ID de Aplicación de Facebook** | Tu identificador único para tu Aplicación de Facebook. Esto vincula las publicaciones de tu sitio web a tu Aplicación de Facebook, permitiendo obtener información y análisis. | *Cuando se proporciona:* Facebook puede atribuir las publicaciones a tu aplicación, proporcionándote análisis sobre el rendimiento de tu contenido en su plataforma. *Cuando se deja vacío:* Las publicaciones seguirán funcionando, pero no obtendrás información detallada a través de las herramientas para desarrolladores de Facebook. | **Tu ID de Aplicación de Facebook** (si tienes uno) | Quieres rastrear el rendimiento de tu contenido compartido en Facebook usando Facebook Insights. Si no tienes uno, puedes dejarlo vacío. |
| **ID de Administrador de Facebook** | El ID de Usuario de Facebook del/de los administrador(es) de tu Página o Aplicación de Facebook. Esto ayuda a Facebook a entender quién gestiona el contenido. | *Cuando se proporciona:* Facebook sabe quién es el autor/administrador del contenido, lo que puede ser útil para la moderación o características específicas de Facebook. *Cuando se deja vacío:* No se vinculará ningún administrador específico. | **Tu ID de Usuario de Facebook** (si aplica) | Quieres vincular tu perfil personal de Facebook como administrador del contenido compartido. |
| **Imagen Predeterminada para la Página de Inicio** | Este ajuste te permite especificar una imagen de respaldo que Facebook utilizará cuando se comparta tu página de inicio, especialmente si tu página de inicio no tiene una imagen prominente. | *Cuando se sube una imagen:* Esta imagen se utilizará como `og:image` cuando se comparta la página de inicio de tu tienda en Facebook. *Cuando se deja vacío:* Facebook intentará encontrar una imagen en tu página de inicio, lo que podría no ser siempre ideal (por ejemplo, un logotipo pequeño o un banner). | **Sube el logotipo principal de tu tienda o una imagen de banner atractiva.** | Tu página de inicio es principalmente texto, y quieres que aparezca una imagen específica y atractiva cuando alguien comparte la URL principal de tu tienda. |
| **Título Predeterminado para la Página de Inicio** | El título que Facebook mostrará cuando se comparta la página de inicio de tu tienda. | *Cuando se proporciona:* Este título se utilizará como `og:title` para las publicaciones de tu página de inicio. *Cuando se deja vacío:* Facebook probablemente utilizará la meta descripción predeterminada de tu tienda, que podría no estar optimizada para compartir en redes sociales. | **Nombre de tu Tienda - Eslogan** (por ejemplo, "Mi Tienda Impresionante - ¡Descubre Productos Únicos!") | Quieres que aparezca un título pegadizo y de marca cuando se comparte la URL principal de tu tienda. |
| **Descripción Predeterminada para la Página de Inicio** | La descripción que Facebook mostrará cuando se comparta la página de inicio de tu tienda. | *Cuando se proporciona:* Esta descripción se utilizará como `og:description` para las publicaciones de tu página de inicio. *Cuando se deja vacío:* Facebook probablemente utilizará la meta descripción predeterminada de tu tienda, que podría no estar optimizada para compartir en redes sociales. | **Un resumen conciso y atractivo de tu tienda.** (por ejemplo, "Compra las últimas tendencias en moda y electrónica. ¡Envío rápido a todo el mundo!") | Quieres controlar el mensaje que aparece cuando se comparte la página de inicio de tu tienda, atrayendo a los usuarios a hacer clic. |

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 AdminOpenGraphController (Back Office > Parámetros Avanzados > Etiquetas Open Graph)

Esta pantalla te permite gestionar etiquetas Open Graph específicas para páginas individuales o anular el comportamiento predeterminado. Aunque el módulo genera automáticamente etiquetas para productos y categorías, esta sección es útil para páginas personalizadas o para un ajuste fino.

- **Nombre de la Pantalla y Ubicación del Menú:** Puedes acceder a esta pantalla navegando a **Parámetros Avanzados > Etiquetas Open Graph** en tu Back Office de PrestaShop.
- **Acciones y Ajustes Disponibles:** Esta pantalla típicamente presenta una cuadrícula (lista) de configuraciones de etiquetas Open Graph personalizadas que has añadido. Encontrarás opciones para:
  - **Añadir Nuevo:** Crear un nuevo conjunto de etiquetas Open Graph personalizadas para una URL específica.
  - **Editar:** Modificar un conjunto de etiquetas personalizadas existente.
  - **Eliminar:** Eliminar un conjunto de etiquetas personalizadas.
  - **Columnas de la Cuadrícula:** Generalmente muestra la URL, el título, la descripción y la imagen asociados con la etiqueta personalizada.
- **Efecto de los cambios:**
  - **Añadir una nueva entrada:** Cuando añades una nueva entrada para una URL específica (por ejemplo, una página CMS personalizada o la URL de una entrada de blog), el módulo utilizará el título, la descripción y la imagen que proporciones aquí en lugar de intentar generarlos automáticamente cuando esa URL específica se comparta en Facebook.
  - **Editar una entrada:** Actualiza la vista previa social para esa URL específica.
  - **Eliminar una entrada:** Revierte el comportamiento para esa URL a la generación automática del módulo o a la configuración predeterminada de la página de inicio.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. **Identifica las páginas que necesitan vistas previas personalizadas:** Para la mayoría de los productos y categorías, el módulo funciona automáticamente. Sin embargo, para páginas CMS personalizadas (por ejemplo, "Sobre Nosotros", "Contacto", entradas de blog si tienes un blog integrado), es posible que desees vistas previas específicas y atractivas.
  2. **Haz clic en "Añadir Nuevo"** para crear una nueva entrada.
  3. **Introduce la URL exacta** de la página que deseas personalizar.
  4. **Proporciona un Título, Descripción atractivos y sube una Imagen relevante** para esa página específica.
  5. **Guarda** tus cambios.
  6. **Prueba:** Utiliza el [Depurador de Compartir](https://developers.facebook.com/tools/debug/) de Facebook para comprobar cómo se ve tu página después de realizar cambios.

#### 2.2.2 index.php (opengraph/controllers/admin/index.php)

Este archivo es un punto de entrada de controlador estándar de PrestaShop y no representa una pantalla distinta y configurable para los comerciantes. Se utiliza típicamente para el enrutamiento o la administración básica del módulo, no para gestionar contenido o configuraciones específicas. Todas las configuraciones orientadas al comerciante se manejan a través de la página de configuración principal del módulo o el `AdminOpenGraphController`.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Habilitar Etiquetas Open Graph | SÍ | Interruptor maestro para la funcionalidad del módulo. |
|  | ID de Aplicación de Facebook | (Tu ID de Aplicación) / Vacío | Vincula las publicaciones a tu Aplicación de Facebook para análisis. |
|  | ID de Administrador de Facebook | (Tu ID de Usuario) / Vacío | Identifica al administrador de contenido en Facebook. |
|  | Imagen Predeterminada para la Página de Inicio | Sube tu logotipo | Imagen de respaldo para las publicaciones de la página de inicio. |
|  | Título Predeterminado para la Página de Inicio | Nombre de tu Tienda | Título para las publicaciones de la página de inicio. |
|  | Descripción Predeterminada para la Página de Inicio | Eslogan de la Tienda | Descripción para las publicaciones de la página de inicio. |
| **Parámetros Avanzados > Etiquetas Open Graph** | Añadir/Editar/Eliminar Etiquetas Personalizadas | N/A | Anula las etiquetas generadas automáticamente para URLs específicas con títulos, descripciones e imágenes personalizadas. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Mis publicaciones en Facebook siguen viéndose mal, incluso después de instalar el módulo. ¿Qué está mal?**
R:

1. **Verifica la activación del módulo:** Asegúrate de que "Habilitar Etiquetas Open Graph" esté configurado en SÍ en la configuración del módulo.
2. **Borra la caché de PrestaShop:** Ve a **Parámetros Avanzados > Rendimiento** y haz clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Esto es crucial para que los cambios surtan efecto.
3. **Usa el Depurador de Compartir de Facebook:** ¡Este es tu mejor amigo! Ve a [developers.facebook.com/tools/debug/](https://developers.facebook.com/tools/debug/), pega la URL que intentas compartir y haz clic en "Depurar". Te mostrará exactamente qué etiquetas está viendo Facebook y si hay algún error. Es posible que necesites hacer clic en "Volver a rastrear" para forzar a Facebook a releer tu página después de realizar cambios.
4. **Busca conflictos:** Otro módulo o tu tema podría estar añadiendo etiquetas Open Graph conflictivas. El depurador a menudo resaltará etiquetas duplicadas.

**P: La imagen para las publicaciones de mis productos es incorrecta o falta.**
R:

1. **Imagen del Producto:** Asegúrate de que tu producto tenga una imagen principal asignada en la configuración del producto.
2. **Tamaño de la Imagen:** Aunque Facebook puede redimensionar, las imágenes muy pequeñas o con una relación de aspecto inusual podrían ser ignoradas. Apunta a al menos 600x315 píxeles, idealmente 1200x628 para una visualización óptima.
3. **Caché:** Borra la caché de PrestaShop y usa el Depurador de Compartir de Facebook para "Volver a rastrear".

**P: ¿Cómo obtengo un ID de Aplicación de Facebook o un ID de Administrador?**
R:

1. **ID de Aplicación de Facebook:** Ve a [developers.facebook.com](https://developers.facebook.com/), inicia sesión y crea una nueva Aplicación. Sigue los pasos para obtener tu ID de Aplicación. Es una cadena numérica.
2. **ID de Administrador de Facebook:** Este es tu ID de Usuario personal de Facebook. Puedes encontrarlo yendo a tu perfil de Facebook, haciendo clic en tu foto de perfil y mirando la URL en tu navegador (por ejemplo, `facebook.com/profile.php?id=TU_ID_DE_USUARIO`).

**P: ¿Este módulo funciona con temas personalizados?**
R: Sí, el módulo inyecta etiquetas directamente en la sección `<head>` de tu HTML, lo cual es una práctica estándar y debería funcionar con cualquier tema de PrestaShop bien codificado. Si encuentras problemas, suele ser un problema de caché o un conflicto con otro módulo.

**P: Mi página personalizada (por ejemplo, una entrada de blog) no muestra la vista previa correcta.**
R: Utiliza la sección **Parámetros Avanzados > Etiquetas Open Graph** en el Back Office. Añade una nueva entrada para la URL exacta de tu página personalizada y especifica manualmente el título, la descripción y la imagen deseados. Recuerda borrar la caché y usar el Depurador de Compartir de Facebook después.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Etiquetas Open Graph de Facebook" está diseñado para integrarse sin problemas con la funcionalidad principal de PrestaShop, principalmente aprovechando los hooks para inyectar metaetiquetas Open Graph en la sección `<head>` del HTML de varias páginas del front-office. Sigue una estructura de módulo estándar de PrestaShop, utilizando una clase de módulo principal, un controlador de administración para la gestión de etiquetas personalizadas y plantillas Smarty para la renderización. El módulo no introduce esquemas de base de datos complejos ni modelos de objetos personalizados para su función principal, pero utiliza `Configuration` para sus ajustes principales y potencialmente una tabla personalizada para `og_tags` gestionada por `AdminOpenGraphController`.

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**: Este módulo no contiene ningún controlador dedicado del front-office. Toda la lógica del front-office para la generación de etiquetas se maneja directamente dentro de la clase principal del módulo (`index.php`) a través de los oyentes de hooks.
- **Controladores de Administración del Back-Office**:

  - `opengraph/controllers/admin/AdminOpenGraphController.php`
    - **Nombre de la clase y clase padre**: `AdminOpenGraphController` extiende `ModuleAdminController`.
    - **Nombre de la pestaña y entidad gestionada**: Este controlador gestiona una entidad personalizada, probablemente `og_tags`, que almacena configuraciones personalizadas de Open Graph para URLs específicas. Crea una nueva entrada de menú bajo "Parámetros Avanzados" (o similar) en el Back Office.
    - **Responsabilidad**: Proporciona una interfaz CRUD (Crear, Leer, Actualizar, Eliminar) estándar de PrestaShop para gestionar conjuntos de etiquetas Open Graph personalizadas. Maneja la visualización de una lista de etiquetas personalizadas (usando `renderList()`) y el formulario para añadirlas/editarlas (usando `renderForm()`). Procesa los envíos de formularios e interactúa con la base de datos para almacenar y recuperar datos de `og_tags`.
  - `opengraph/controllers/admin/index.php`
    - **Nombre de la clase y clase padre**: Este es típicamente un archivo `index.php` vacío dentro de un directorio de controlador, que sirve como medida de seguridad para evitar la lista directa de directorios. No contiene ninguna clase o lógica funcional.

### 4.3 Clases Principales y Modelos (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. La lógica principal para generar etiquetas Open Graph probablemente está contenida dentro del archivo principal del módulo (`opengraph/index.php`), y el `AdminOpenGraphController` manejaría las interacciones con una tabla de base de datos personalizada directamente o a través de un `ObjectModel` simple si se definiera internamente.

Si una tabla personalizada `og_tags` es gestionada por `AdminOpenGraphController`, es muy probable que el propio `AdminOpenGraphController` defina las propiedades `$this->table` y `$this->className`, y potencialmente una definición simple de `ObjectModel` para `og_tags` se declare dentro del archivo principal del módulo o del propio controlador, incluso si no está en un archivo `classes/` separado.

### 4.4 Activos JavaScript (`views/js/`)

El dossier del módulo no indica archivos JavaScript personalizados. Cualquier comportamiento dinámico o interacciones AJAX serían manejados por el JS central de PrestaShop o no están presentes en este módulo.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El dossier del módulo no indica archivos CSS personalizados. El módulo se basa en el estilo predeterminado del Back Office de PrestaShop para sus formularios de configuración y cualquier salida del front-office son puramente metaetiquetas, no elementos visuales.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de Hook (`views/templates/hook/`)**:

  - `opengraph/views/templates/front/hook/header.tpl`:
    - **Hook**: Probablemente `displayHeader` o `actionFrontControllerSetMedia`.
    - **Propósito**: Esta es la plantilla principal responsable de renderizar las etiquetas `<meta>` de Open Graph reales dentro de la sección `<head>` de las páginas del front-office. Recibe variables (por ejemplo, `og_title`, `og_description`, `og_image`, `og_url`, `og_type`, `og_app_id`, `og_admin_id`) del método `hookDisplayHeader` (o similar) del módulo y genera las metaetiquetas HTML correspondientes.
  - `opengraph/views/templates/hook/form.tpl`:
    - **Hook**: Esta plantilla probablemente es utilizada internamente por el `AdminOpenGraphController` para renderizar los campos del formulario al añadir o editar una entrada de etiqueta Open Graph personalizada. No es una plantilla de hook del front-office.
    - **Propósito**: Define la estructura y los campos de entrada para el formulario de configuración de etiquetas Open Graph personalizadas en el Back Office.
  - `opengraph/views/templates/hook/script.tpl`:
    - **Hook**: Podría ser `displayHeader` o `actionFrontControllerSetMedia`.
    - **Propósito**: Esta plantilla podría usarse para generar cualquier JavaScript en línea relacionado con Open Graph, como la inicialización del SDK de Facebook o el seguimiento de eventos específicos, aunque el dossier no indica archivos JS, por lo que podría ser para un script muy mínimo o un marcador de posición.
- **Plantillas de Administración (`views/templates/admin/`)**: No listadas explícitamente, pero `form.tpl` y potencialmente un `list.tpl` serían utilizados por `AdminOpenGraphController` para sus vistas.
- **Plantillas del Front-Office (`views/templates/front/`)**:

  - `opengraph/views/templates/front/hook/header.tpl` es la única plantilla del front-office identificada, específicamente para la inyección de hooks.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - `ps_configuration`: Almacena la configuración principal del módulo (por ejemplo, `PS_OG_ENABLED`, `PS_OG_APP_ID`, `PS_OG_ADMIN_ID`, `PS_OG_HOME_IMAGE`, `PS_OG_HOME_TITLE`, `PS_OG_HOME_DESCRIPTION`).
  - `ps_og_tags` (o similar, gestionada por `AdminOpenGraphController`): Una tabla personalizada para almacenar anulaciones de etiquetas Open Graph definidas por el usuario para URLs específicas.
    - Campos probables: `id_og_tag`, `url`, `title`, `description`, `image`, `date_add`, `date_upd`.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Renderiza contenido dentro de la sección `<head>` de todas las páginas del front-office. | Hook principal para inyectar metaetiquetas Open Graph (`og:title`, `og:description`, `og:image`, `og:url`, `og:type`, etc.) en el HTML. |
| `actionFrontControllerSetMedia` | Se ejecuta después de que el controlador del front-office ha establecido sus medios (CSS/JS). | Podría usarse como un hook alternativo o adicional para inyectar metaetiquetas o scripts relacionados, especialmente en PrestaShop 1.7+. |
| `displayBackOfficeHeader` | Renderiza contenido dentro de la sección `<head>` de las páginas del Back Office. | Se utiliza para incluir cualquier CSS o JS necesario para las páginas de configuración del módulo en el Back Office. |
| `actionAdminControllerSetMedia` | Se ejecuta después de que un controlador de administración ha establecido sus medios. | Similar a `displayBackOfficeHeader` pero más específico para controladores de administración, para cargar activos para `AdminOpenGraphController`. |
| `moduleRoutes` (PrestaShop 1.7+) | Permite a los módulos definir rutas personalizadas. | No se utiliza explícitamente para la función principal de este módulo, pero podría estar presente para futuras extensiones o manejo de URLs específicas. |

## 5. Soporte Oficial y Actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y acceder a las últimas versiones del módulo "Etiquetas Open Graph de Facebook", visita tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto a la funcionalidad e integración del módulo.

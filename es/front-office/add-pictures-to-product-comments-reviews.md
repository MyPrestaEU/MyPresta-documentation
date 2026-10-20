---
title: "Añadir imágenes a los comentarios de productos (reseñas) - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Añadir imágenes a los comentarios de productos (reseñas)' de MyPresta.eu."
sidebar:
  label: "Añadir imágenes a los comentarios de productos (reseñas) - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Add pictures to product comments (reviews) en MyPresta.eu](https://mypresta.eu/modules/front-office-features/add-pictures-to-product-comments-reviews.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/add-pictures-to-product-comments-reviews/)
>
> ---


# Añadir imágenes a los comentarios de productos (reseñas)

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).
- **Dependencia**: Este módulo requiere que el módulo "Comentarios de productos" (desarrollado por MyPresta.eu) esté instalado y activo, ya que extiende su funcionalidad.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Añadir imágenes a los comentarios de productos (reseñas)" en el Gestor de módulos. Esto le llevará a su pantalla de configuración principal.

La configuración del módulo es sencilla, centrándose principalmente en habilitar o deshabilitar su funcionalidad principal.

**Ajustes y opciones:**

- **Habilitar la carga de imágenes para los comentarios de productos:**
  - **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar la funcionalidad principal del módulo. Cuando está habilitado, sus clientes verán la opción de cargar imágenes cuando escriban una reseña de producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* El campo de carga de imágenes aparecerá en el formulario de envío de reseñas de productos en las páginas de sus productos. Los clientes podrán adjuntar imágenes a sus reseñas. Las reseñas existentes con imágenes también mostrarán esas imágenes.
    - *Cuando está deshabilitado (NO):* El campo de carga de imágenes se ocultará del formulario de envío de reseñas de productos. Los clientes solo podrán enviar reseñas de texto. Las reseñas existentes con imágenes aún podrían mostrarlas, pero no se podrán añadir nuevas imágenes.
  - **Valor recomendado:** **SÍ**. Para aprovechar los beneficios de las reseñas visuales, debe habilitar esta función.
  - **Escenario / ejemplo de comerciante:** Si desea permitir que los clientes muestren su nuevo vestido o cómo funciona un gadget en la vida real, habilite esto. Si desea restringir temporalmente la carga de imágenes por mantenimiento o una campaña específica, puede deshabilitarlo.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Habilitar la carga de imágenes para los comentarios de productos | SÍ | Controla si los clientes pueden cargar imágenes con sus reseñas de productos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He habilitado el módulo, pero no veo el campo de carga de imágenes en la página de mi producto.**
R:

1. **Verifique el módulo "Comentarios de productos":** Este módulo extiende el módulo "Comentarios de productos". Asegúrese de que el módulo "Comentarios de productos" (de MyPresta.eu) esté instalado, habilitado y configurado correctamente en su tienda.
2. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** en el back office de PrestaShop y haga clic en "Borrar caché" en la parte superior derecha. A veces, los archivos antiguos en caché impiden que aparezcan las nuevas funciones del módulo.
3. **Compatibilidad con el tema:** Si bien el módulo está diseñado para una amplia compatibilidad, los temas personalizados a veces pueden anular las estructuras de plantilla predeterminadas. Si borrar la caché no ayuda, póngase en contacto con el soporte de MyPresta.eu con los detalles de su tema.

**P: Mis clientes están subiendo fotos, pero no aparecen junto a la reseña.**
R:

1. **Moderación de reseñas:** Verifique si su módulo "Comentarios de productos" tiene la moderación de reseñas habilitada. Si es así, las nuevas reseñas (y sus imágenes asociadas) solo aparecerán después de que las apruebe en el Back Office.
2. **Verifique la configuración del módulo:** Vuelva a verificar que "Habilitar la carga de imágenes para los comentarios de productos" esté configurado en SÍ en la configuración de este módulo.
3. **Permisos de archivo:** Asegúrese de que el directorio `img/p/` (o donde PrestaShop almacene las imágenes de productos) tenga los permisos de escritura correctos (generalmente 755 o 775). Si el servidor no puede escribir archivos, las imágenes no se guardarán.

**P: ¿Puedo limitar el número de imágenes que un cliente puede subir por reseña?**
R: Este módulo específico proporciona una función de carga básica. Los controles avanzados, como limitar el número de imágenes o el tamaño del archivo, pueden requerir modificaciones personalizadas o una actualización del módulo principal "Comentarios de productos". Consulte la configuración del módulo "Comentarios de productos" o póngase en contacto con el soporte de MyPresta.eu para tales funciones.

**P: Las imágenes cargadas se ven distorsionadas o no se muestran correctamente.**
R:

1. **Conflictos de CSS:** El CSS de su tema podría estar en conflicto con el estilo del módulo. Utilice las herramientas de desarrollo de su navegador (F12) para inspeccionar los elementos de la imagen e identificar cualquier estilo en conflicto.
2. **Regeneración de imágenes:** A veces, las miniaturas de las imágenes pueden no generarse correctamente. En PrestaShop, vaya a **Diseño > Configuración de imágenes** e intente regenerar las miniaturas para "productos" o "reseñas" si existe tal opción, o para todas las imágenes.
3. **Calidad de la imagen original:** Aconseje a los clientes que suban imágenes de tamaño razonable y claras. Las imágenes de muy baja resolución se verán naturalmente mal cuando se muestren más grandes.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura

El módulo "Añadir imágenes a los comentarios de productos (reseñas)" (`reviewspics`) está diseñado como una extensión del módulo principal "Comentarios de productos" (presumiblemente `productcomments` o un módulo similar de MyPresta.eu). Principalmente inyecta una interfaz de carga de imágenes en el formulario de reseña existente y modifica la visualización de las reseñas para incluir imágenes. Aprovecha el sistema de hooks de PrestaShop para la integración y utiliza activos estándar de front-office y back-office. El módulo crea una tabla de base de datos personalizada para vincular imágenes a comentarios de productos específicos.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de Front-Office o Back-Office. Su funcionalidad se integra a través de hooks y modificaciones directas de plantillas dentro del contexto del módulo padre "Comentarios de productos".

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define clases personalizadas en el directorio `classes/`. Su lógica principal reside dentro del archivo principal del módulo `index.php` y el `install.sql` para el esquema de la base de datos.

### 4.4 Activos JavaScript (`views/js/`)

- **`reviewspics/views/js/reviewspics-bo.js`**

  - **Alcance:** Back-office.
  - **Propósito:** Este script probablemente maneja cualquier funcionalidad impulsada por JavaScript dentro de la configuración del back-office del módulo o para administrar imágenes cargadas asociadas con reseñas en el panel de administración. Esto podría incluir llamadas AJAX para la eliminación de imágenes, actualizaciones de estado o elementos de formulario dinámicos.
  - **Detalles:** Normalmente se vincularía a elementos dentro de la plantilla `backOffice.tpl` o la interfaz de gestión de comentarios de productos del administrador.
- **`reviewspics/views/js/reviewspics.js`**

  - **Alcance:** Front-office.
  - **Propósito:** Este es el JavaScript principal del front-office para la funcionalidad de carga de imágenes. Maneja:
    - Mostrar la entrada de carga de imágenes (por ejemplo, entrada de archivo, área de arrastrar y soltar).
    - Previsualizar las imágenes seleccionadas antes de la carga.
    - Carga de imágenes basada en AJAX durante el envío de la reseña.
    - Validación de tipos/tamaños de imagen (lado del cliente).
    - Potencialmente, eliminación de imágenes seleccionadas antes del envío.
  - **Detalles:** Se vincula a los elementos del formulario de envío de reseñas, probablemente dentro de la plantilla `displayMyPrestaCommentsField.tpl`, e interactúa con la lógica del lado del servidor para procesar los archivos de imagen.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`reviewspics/views/css/reviewspics.css`**
  - **Alcance:** Front-office (principalmente) y potencialmente Back-office.
  - **Propósito:** Esta hoja de estilo proporciona el estilo visual para el formulario de carga de imágenes y la visualización de las imágenes cargadas dentro de las reseñas de productos.
  - **Principales componentes de la interfaz de usuario y contenedores que estiliza:**
    - El área de carga de imágenes (por ejemplo, borde, fondo, icono).
    - Vistas previas de imágenes (tamaño, relación de aspecto, bordes).
    - Diseño de imágenes dentro de una reseña.
    - Potencialmente, estilo para la gestión de imágenes en el Back Office.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:** Busque clases como `.reviewspics-upload-area`, `.reviewspics-image-preview`, `.reviewspics-review-images`, etc. Estas se pueden usar en el `custom.css` o `theme.css` de un tema personalizado para que coincidan con la marca de la tienda.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:

  - **`reviewspics/views/templates/hook/backOffice.tpl`**

    - **Hook:** Probablemente renderizado en `displayAdminProductsExtra` o un hook personalizado dentro de la interfaz de administración del módulo "Comentarios de productos".
    - **Salidas:** Esta plantilla es para el Back Office. Probablemente renderiza el formulario de configuración del módulo (como se describe en la sección 4.1) o proporciona una interfaz para que los administradores gestionen las imágenes asociadas con los comentarios de productos (por ejemplo, ver, eliminar, aprobar imágenes).
  - **`reviewspics/views/templates/hook/displayMyPrestaComment.tpl`**

    - **Hook:** Esta plantilla está diseñada para ser enganchada en la visualización de un comentario de producto *individual*, probablemente dentro de `displayProductListReviews` o un hook similar proporcionado por el módulo "Comentarios de productos".
    - **Salidas:** Renderiza las imágenes reales asociadas con una reseña de producto específica. Iteraría a través de las imágenes vinculadas al comentario y las mostraría, potencialmente como miniaturas o una pequeña galería.
  - **`reviewspics/views/templates/hook/displayMyPrestaCommentsField.tpl`**

    - **Hook:** Esta plantilla está destinada a ser inyectada en el formulario de envío de reseñas de productos, probablemente a través de un hook como `displayProductForm` o un hook personalizado dentro del formulario de reseñas del módulo "Comentarios de productos".
    - **Salidas:** Renderiza la estructura HTML para el campo de entrada de carga de imágenes con el que interactúan los clientes al escribir una nueva reseña. Esto incluye la entrada de archivo, cualquier área de arrastrar y soltar, y potencialmente marcadores de posición para vistas previas de imágenes.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:

  - El archivo `reviewspics/install.sql` indica la creación de al menos una tabla personalizada para almacenar los datos de la imagen y vincularlos a los comentarios de productos.
  - **`ps_reviewspics_image`**: (Nombre de tabla probable, basado en el nombre del módulo y las convenciones comunes de PrestaShop).
    - **Propósito:** Almacena metadatos sobre cada imagen cargada.
    - **Campos (esperados):**
      - `id_reviewspics_image` (Clave primaria, INT)
      - `id_product_comment` (Clave externa, INT, que enlaza con la tabla de reseñas del módulo padre "Comentarios de productos")
      - `image_name` (VARCHAR, nombre de archivo de la imagen)
      - `date_add` (DATETIME, marca de tiempo de la carga)
      - `active` (TINYINT, para moderación/visibilidad)
      - `position` (INT, para ordenar si hay varias imágenes por reseña)
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza en la sección `<head>` de todas las páginas del front-office. | Para incluir archivos CSS (`reviewspics.css`) y JavaScript (`reviewspics.js`) del front-office. |
| `displayBackOfficeHeader` | Se renderiza en la sección `<head>` de todas las páginas del back-office. | Para incluir CSS y JavaScript (`reviewspics-bo.js`) del back-office para la configuración de administración o la gestión de reseñas. |
| `displayProductListReviews` (o similar del módulo Comentarios de productos) | Se renderiza dentro de la lista de reseñas de productos en las páginas de productos. | Para inyectar `displayMyPrestaComment.tpl` para mostrar imágenes dentro de las reseñas existentes. |
| `displayProductForm` (o similar del módulo Comentarios de productos) | Se renderiza dentro del formulario de envío de reseñas de productos. | Para inyectar `displayMyPrestaCommentsField.tpl` para la entrada de carga de imágenes. |
| `actionProductCommentAdd` (o similar del módulo Comentarios de productos) | Se ejecuta después de añadir un nuevo comentario de producto. | Para procesar las imágenes cargadas, guardarlas en el sistema de archivos y registrar sus detalles en la tabla `ps_reviewspics_image`, vinculándolas al nuevo comentario. |
| `actionProductCommentDelete` (o similar del módulo Comentarios de productos) | Se ejecuta después de eliminar un comentario de producto. | Para limpiar las imágenes asociadas del sistema de archivos y de la tabla `ps_reviewspics_image`. |
| `actionProductCommentUpdate` (o similar del módulo Comentarios de productos) | Se ejecuta después de actualizar un comentario de producto. | Para manejar cualquier cambio en las asociaciones de imágenes o el estado de moderación. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte profesional, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo se dedica a garantizar el buen funcionamiento y la mejora continua de sus módulos de PrestaShop.
"""

---
title: "Duplicar página CMS - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Duplicar página CMS' de MyPresta.eu."
sidebar:
  label: "Duplicar página CMS - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Duplicate CMS page en MyPresta.eu](https://mypresta.eu/modules/administration-tools/duplicate-cms-page.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/duplicate-cms-page/)
>
> ---


# Duplicar página CMS

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop en sí y son suficientes para este módulo.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Duplicar página CMS" en el Gestor de módulos. Esto le llevará a la pantalla de configuración principal del módulo.

#### Ajustes Generales

- **Actualizaciones de MyPresta.eu (mypresta\_updates)**

  - **Qué hace este ajuste:** Este ajuste controla si el módulo busca actualizaciones de MyPresta.eu. Mantenerlo habilitado asegura que se le notifique sobre nuevas versiones, correcciones de errores y mejoras de características.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El módulo buscará periódicamente las actualizaciones disponibles. Si se encuentra una actualización, puede aparecer una notificación en el Back Office de PrestaShop.
    - *Cuando está deshabilitado:* El módulo no buscará actualizaciones y no se le notificará automáticamente sobre nuevas versiones. Tendría que buscar actualizaciones manualmente en MyPresta.eu.
  - **Valor recomendado:** **SÍ** (Habilitado).
  - **Escenario / ejemplo de comerciante:** Desea asegurarse de que su módulo esté siempre actualizado con los últimos parches de seguridad y características sin tener que revisar manualmente el sitio web de MyPresta.eu cada semana.
- **Actualizar (update\_)**

  - **Qué hace este ajuste:** Este es generalmente un campo de visualización o un botón relacionado con la verificación de actualizaciones, que muestra el estado actual o permite una verificación manual. Funciona en conjunto con el ajuste "Actualizaciones de MyPresta.eu".
  - **Efecto de cambiar este ajuste:** Hacer clic en un botón aquí (si está presente) iniciaría una verificación inmediata de actualizaciones.
  - **Valor recomendado:** N/A (Basado en la interacción).
  - **Escenario / ejemplo de comerciante:** Después de habilitar "Actualizaciones de MyPresta.eu", podría hacer clic aquí para ver inmediatamente si hay una nueva versión disponible, en lugar de esperar la próxima verificación automática.
- **Versión de actualización (updatev\_)**

  - **Qué hace este ajuste:** Este campo suele mostrar la última versión disponible del módulo detectada por el verificador de actualizaciones.
  - **Efecto de cambiar este ajuste:** Este es un campo de solo visualización y no se puede cambiar directamente. Proporciona información sobre la última versión.
  - **Valor recomendado:** N/A (Solo visualización).
  - **Escenario / ejemplo de comerciante:** Ve "1.2.3" aquí, lo que indica que hay una versión más nueva que la suya actual (por ejemplo, 1.2.2) disponible.
- **Última versión (dupcms\_LATEST)**

  - **Qué hace este ajuste:** Similar a "Versión de actualización", este campo muestra la versión más reciente del módulo disponible.
  - **Efecto de cambiar este ajuste:** Este es un campo de solo visualización.
  - **Valor recomendado:** N/A (Solo visualización).
  - **Escenario / ejemplo de comerciante:** Puede verificar rápidamente si su módulo instalado es el más actual comparando este valor con su versión instalada.
- **Miniaturas (dupcms\_MINIATURES)**

  - **Qué hace este ajuste:** Este ajuste probablemente controla si se muestran imágenes en miniatura o iconos en la interfaz del módulo, posiblemente relacionados con el verificador de actualizaciones u otros elementos visuales dentro del panel de administración del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Podría ver pequeños iconos o imágenes en la configuración del módulo o en las notificaciones de actualización.
    - *Cuando está deshabilitado:* Estos elementos visuales se ocultarían, lo que resultaría en una interfaz más basada en texto.
  - **Valor recomendado:** **SÍ** (Habilitado).
  - **Escenario / ejemplo de comerciante:** Prefiere una interfaz más rica visualmente en su Back Office, por lo que mantiene esto habilitado para ver cualquier icono relevante.
- **ID Categoría CMS (dupcms\_ID\_CMSCAT)**

  - **Qué hace este ajuste:** Este ajuste es crucial para la funcionalidad principal del módulo. Le permite seleccionar una categoría CMS predeterminada donde se colocarán las páginas CMS duplicadas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se selecciona una categoría específica:* Todas las nuevas páginas CMS duplicadas se asignarán automáticamente a esta categoría. Esto ayuda a organizar su contenido.
    - *Cuando no se selecciona ninguna categoría (o predeterminada):* El módulo podría usar la misma categoría que la página original, o una categoría raíz, dependiendo de su lógica interna. Establecer una categoría específica le da más control.
  - **Valor recomendado:** Seleccione una categoría predeterminada lógica, como "Información" o una categoría específica que use para nuevas páginas.
  - **Escenario / ejemplo de comerciante:** Duplica con frecuencia páginas de "Aviso legal" para diferentes regiones. Puede configurar esto en su categoría CMS "Páginas legales" para que todas las nuevas duplicadas aterricen automáticamente allí, lo que las hace más fáciles de encontrar y administrar.

#### Cómo usar la función de duplicación

La acción de duplicación real ocurre en la lista estándar de páginas CMS de PrestaShop:

1. Navegue a **Mejorar > Diseño > Páginas** en su Back Office de PrestaShop.
2. Verá una lista de sus páginas CMS existentes.
3. Localice la página CMS que desea duplicar.
4. En la columna "Acciones" (generalmente representada por tres puntos o un menú desplegable) para esa página CMS específica, encontrará una nueva opción añadida por este módulo: **"Duplicar"** (o un icono/texto similar).
5. Haga clic en "Duplicar".
6. El módulo creará una copia exacta de la página, incluyendo su contenido, meta información, URL amigable y estado activo. La nueva página normalmente tendrá un nombre como "Copia de [Nombre de la página original]" o similar, que luego podrá editar.
7. La página duplicada se colocará en la categoría CMS que seleccionó en la configuración del módulo (si `dupcms_ID_CMSCAT` está configurado) o en la misma categoría que la original.
8. Luego puede editar la página recién duplicada para cambiar su título, contenido, URL y otras configuraciones según sea necesario.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Actualizaciones de MyPresta.eu | SÍ | Habilita las comprobaciones automáticas de actualizaciones del módulo. |
| Configuración del Módulo | Actualizar | N/A (Botón) | Inicia una comprobación manual de actualizaciones del módulo. |
| Configuración del Módulo | Versión de actualización | N/A (Visualización) | Muestra la última versión disponible del módulo. |
| Configuración del Módulo | Última versión | N/A (Visualización) | Muestra la versión más reciente del módulo detectada. |
| Configuración del Módulo | Miniaturas | SÍ | Controla la visualización de elementos visuales/iconos en la interfaz del módulo. |
| Configuración del Módulo | ID Categoría CMS | Seleccionar una categoría | Establece la categoría CMS predeterminada para las páginas duplicadas. |
| Lista de Páginas CMS (Diseño > Páginas) | Acción Duplicar | N/A (Botón) | Crea una copia exacta de la página CMS seleccionada. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Dupliqué una página, pero no la encuentro.**
R: Verifique la categoría CMS que seleccionó en la configuración del módulo (`dupcms_ID_CMSCAT`). Si no configuró una, podría estar en la misma categoría que la página original o en la categoría CMS raíz. Además, asegúrese de buscar "Copia de [Nombre de la página original]" o similar, ya que el módulo añade un prefijo al título de la página duplicada.

**P: La página duplicada tiene la misma URL amigable que la original. ¿Es esto un problema?**
R: Sí, esto puede causar conflictos y problemas de SEO. Después de duplicar una página, **siempre edite la nueva página inmediatamente** y cambie su URL amigable (también conocida como "Reescritura de URL" o "Slug") a algo único y descriptivo para el nuevo contenido. PrestaShop suele añadir un número (por ejemplo, `-1`) a la URL, pero es mejor personalizarla usted mismo.

**P: No veo la opción "Duplicar" en la lista de páginas CMS.**
R:

1. Vaya a **Módulos > Gestor de módulos** y asegúrese de que el módulo "Duplicar página CMS" esté instalado y habilitado.
2. Borre la caché de PrestaShop: Vaya a **Parámetros avanzados > Rendimiento**, desplácese hacia abajo y haga clic en "Borrar caché".
3. Si aún no aparece, intente reinstalar el módulo (después de hacer una copia de seguridad de su tienda). Si el problema persiste, póngase en contacto con el soporte de MyPresta.eu.

**P: ¿Este módulo duplica imágenes y archivos vinculados dentro del contenido de la página CMS?**
R: Sí, el módulo duplica todo el contenido HTML de la página. Si sus imágenes están vinculadas usando rutas relativas dentro del contenido, seguirán funcionando. Si se cargan directamente a través del editor de texto enriquecido, las referencias se copiarán. Sin embargo, el módulo no duplica los *archivos* de imagen reales en su servidor; duplica las *referencias* a ellos. Esto es generalmente el comportamiento deseado.

**P: ¿Puedo duplicar una categoría CMS?**
R: No, este módulo está diseñado específicamente para duplicar *páginas* CMS individuales, no *categorías* CMS completas.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una visión técnica para desarrolladores y webmasters que buscan comprender, depurar o extender el módulo "Duplicar página CMS".

### 4.1 Resumen de la Arquitectura

El módulo "Duplicar página CMS" es un módulo ligero de PrestaShop centrado principalmente en extender la funcionalidad del `AdminCmsController` existente. Aprovecha el sistema de hooks de PrestaShop (`actionAdminControllerSetMedia`) para inyectar JavaScript que modifica la tabla de listado de páginas CMS predeterminada, añadiendo una acción "Duplicar". La lógica de duplicación central es manejada por el archivo `dupcms.php` del módulo, que intercepta las solicitudes AJAX para realizar las operaciones de base de datos necesarias para copiar los datos de la página CMS. No introduce nuevas tablas de base de datos ni modelos de objetos complejos, sino que se basa en la manipulación directa de las tablas existentes `ps_cms` y `ps_cms_lang`.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front-office o back-office. Su funcionalidad se integra en el `AdminCmsController` existente a través de hooks y AJAX.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no introduce ninguna clase personalizada o definición de `ObjectModel`. Interactúa directamente con las clases principales de PrestaShop `CMS` y `CMSCategory` y sus tablas de base de datos asociadas.

### 4.4 Activos JavaScript (`views/js/`)

- **`dupcms/views/js/dupcms.js`**
  - **Alcance:** Back-office (específicamente, la página `AdminCms`).
  - **Responsabilidad:**
    - Este script se inyecta en la página `AdminCmsController` (Mejorar > Diseño > Páginas) a través del hook `actionAdminControllerSetMedia`.
    - Espera a que el DOM esté listo.
    - Identifica la columna "Acciones" en la tabla de listado de páginas CMS.
    - Para cada fila de página CMS, añade dinámicamente un nuevo botón o enlace de acción "Duplicar" al menú desplegable de acciones existente.
    - Adjunta un detector de eventos (por ejemplo, `click`) a estos elementos "Duplicar" recién añadidos.
    - Cuando se hace clic en una acción "Duplicar", extrae el `id_cms` de la página a duplicar.
    - Luego envía una solicitud AJAX al archivo PHP principal del módulo (`dupcms/dupcms.php`) con el `id_cms` y un parámetro de acción (por ejemplo, `action=duplicateCms`).
    - Maneja la respuesta AJAX, típicamente mostrando un mensaje de éxito o error y potencialmente actualizando la lista de páginas CMS para mostrar la página recién duplicada.
    - También podría incluir lógica para notificaciones de actualización u otros elementos de interfaz de usuario dinámicos relacionados con la configuración del módulo.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- **`dupcms/views/css/dupcms.css`**
  - **Alcance:** Back-office (específicamente, la página `AdminCms`).
  - **Responsabilidad:**
    - Proporciona estilos para el enlace/botón de acción "Duplicar" añadido dinámicamente para asegurar que se integre visualmente con el tema del Back Office de PrestaShop.
    - Puede incluir estilos para cualquier notificación o elemento de interfaz de usuario específico del módulo dentro del contexto de `AdminCms`.
    - Selectores de clase CSS clave que los desarrolladores pueden anular: Busque clases como `.dupcms-duplicate-action` o similares dentro del HTML inyectado para personalizar su apariencia.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

Este módulo no utiliza ningún archivo de plantilla Smarty personalizado (`.tpl`). Todas sus modificaciones de interfaz de usuario en el Back Office se realizan dinámicamente a través de JavaScript.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo no crea ninguna tabla de base de datos personalizada nueva.
  - Opera en las tablas existentes de PrestaShop:
    - `ps_cms`: Almacena información general de la página CMS (estado activo, posición, etc.).
    - `ps_cms_lang`: Almacena contenido de página CMS específico del idioma (título, meta descripción, contenido, URL amigable).
    - `ps_cms_shop`: Vincula páginas CMS a tiendas específicas en un entorno multitienda.
    - `ps_configuration`: Almacena la configuración del módulo (por ejemplo, `dupcms_ID_CMSCAT`, `mypresta_updates`).
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador del Back Office está configurando sus medios (JS/CSS). | Este es el hook principal utilizado por el módulo. Inyecta `dupcms.js` y `dupcms.css` en la página `AdminCmsController`, permitiendo que el módulo modifique la lista de páginas CMS y añada la acción "Duplicar". |

## 5. Soporte Oficial y Actualizaciones

Para soporte oficial, actualizaciones y para descargar la última versión del módulo "Duplicar página CMS", inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad del módulo.

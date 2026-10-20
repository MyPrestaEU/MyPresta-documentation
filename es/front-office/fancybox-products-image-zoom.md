---
title: "Zoom de imagen de productos Fancybox - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Zoom de imagen de productos Fancybox' de MyPresta.eu."
sidebar:
  label: "Zoom de imagen de productos Fancybox - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Fancybox products image zoom en MyPresta.eu](https://mypresta.eu/modules/front-office-features/fancybox-products-image-zoom.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/fancybox-products-image-zoom/)
>
> ---


# Zoom de imagen de productos Fancybox

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo de zoom de imagen de productos Fancybox. La encontrará navegando a **Módulos > Gestor de Módulos**, buscando "Zoom de imagen de productos Fancybox" y haciendo clic en "Configurar".

#### Soporte de Tema y Ajustes de Selector

Estos ajustes ayudan al módulo a identificar los elementos correctos en su página de producto para aplicar el zoom de Fancybox, especialmente importante para temas personalizados.

-   **Soporte de tema**

    -   **Qué hace este ajuste:** Este es un ajuste crucial que le indica al módulo qué estructura de tema debe esperar. Ayuda al módulo a identificar correctamente la imagen principal del producto y sus miniaturas en sus páginas de producto.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Classic":* El módulo utilizará selectores predefinidos que funcionan perfectamente con el tema "Classic" predeterminado de PrestaShop. Esta es la configuración más común y recomendada si está utilizando el tema Classic o un tema muy basado en él.
        -   *Cuando se establece en "Hummingbird":* El módulo utilizará selectores predefinidos para el tema "Hummingbird", que es el tema predeterminado para PrestaShop 8.1 y versiones posteriores.
        -   *Cuando se establece en "Custom":* Esta opción le permite especificar manualmente los selectores CSS para su imagen principal de producto y miniaturas. Esto es esencial si está utilizando un tema muy personalizado o un tema de terceros que no sigue la estructura "Classic" o "Hummingbird".
    -   **Valor recomendado:** "Classic" si está en PrestaShop 1.7.x a 8.0.x con el tema Classic. "Hummingbird" si está en PrestaShop 8.1+ con el tema Hummingbird. "Custom" si tiene un tema único.
    -   **Escenario / ejemplo de comerciante:** Si las imágenes de sus productos no se están ampliando correctamente después de la instalación, y está utilizando un tema personalizado, cambiar esto a "Custom" y luego ajustar los selectores a continuación es el siguiente paso.
-   **Perfil de tema detectado**

    -   **Qué hace este ajuste:** Este campo muestra el perfil de tema que el módulo ha detectado automáticamente basándose en su selección de "Soporte de tema". Es un campo informativo, no directamente configurable.
    -   **Efecto de cambiar este ajuste:** No tiene un efecto directo, ya que es un campo de solo visualización. Simplemente confirma qué conjunto de selectores está utilizando el módulo actualmente.
    -   **Valor recomendado:** N/A (informativo).
    -   **Escenario / ejemplo de comerciante:** Ha configurado "Soporte de tema" en "Classic", y este campo confirma que se ha detectado "Classic".
-   **Selector de portada Hummingbird** (Solo visible si "Soporte de tema" es "Hummingbird")

    -   **Qué hace este ajuste:** Especifica el selector CSS para el contenedor de la imagen principal de la portada del producto cuando se utiliza el tema Hummingbird. Esto ayuda al módulo a apuntar al área correcta para el zoom.
    -   **Efecto de cambiar este ajuste:** Si es incorrecto, el zoom de Fancybox podría no activarse en la imagen principal del producto, o podría apuntar al elemento incorrecto.
    -   **Valor recomendado:** Dejar como predeterminado a menos que su tema basado en Hummingbird haya alterado significativamente su estructura.
    -   **Escenario / ejemplo de comerciante:** Su tema Hummingbird tiene una estructura única para la imagen principal. Es posible que deba inspeccionar el código de su tema para encontrar la clase o ID CSS correcta para el contenedor de la imagen principal e introducirla aquí.
-   **Selector de imagen Hummingbird** (Solo visible si "Soporte de tema" es "Hummingbird")

    -   **Qué hace este ajuste:** Especifica el selector CSS para la etiqueta `<img>` real de la imagen principal de la portada del producto dentro del tema Hummingbird.
    -   **Efecto de cambiar este ajuste:** Similar al selector de portada, un valor incorrecto evitará que el zoom funcione en la imagen principal.
    -   **Valor recomendado:** Dejar como predeterminado.
    -   **Escenario / ejemplo de comerciante:** Si el zoom no funciona en la imagen principal, y está en Hummingbird, verifique este selector.
-   **Selector de miniaturas Hummingbird** (Solo visible si "Soporte de tema" es "Hummingbird")

    -   **Qué hace este ajuste:** Especifica el selector CSS para el contenedor de las imágenes en miniatura del producto cuando se utiliza el tema Hummingbird. Esto es importante para crear una galería a partir de sus miniaturas.
    -   **Efecto de cambiar este ajuste:** Si es incorrecto, el módulo podría no ser capaz de crear una galería Fancybox a partir de sus miniaturas, o al hacer clic en las miniaturas podría no abrir Fancybox.
    -   **Valor recomendado:** Dejar como predeterminado.
    -   **Escenario / ejemplo de comerciante:** Si al hacer clic en las miniaturas no se abre la galería Fancybox, verifique este selector.
-   **Selector de imagen principal de portada** (Solo visible si "Soporte de tema" es "Custom")

    -   **Qué hace este ajuste:** Cuando se selecciona el soporte de tema "Custom", este campo le permite introducir manualmente el selector CSS para el elemento contenedor que contiene su imagen principal de producto en la página de producto.
    -   **Efecto de cambiar este ajuste:** Si este selector es incorrecto, el zoom de Fancybox no se activará en su imagen principal de producto.
    -   **Valor recomendado:** Necesitará usar las herramientas de desarrollador de su navegador (F12) para inspeccionar su página de producto y encontrar la clase o ID CSS única del `<div>` u otro elemento contenedor que envuelve su imagen principal de producto.
    -   **Escenario / ejemplo de comerciante:** Su tema personalizado utiliza `<div id="my-custom-main-image-wrapper">` para la imagen principal. Aquí introduciría `#my-custom-main-image-wrapper`.
-   **Imagen principal de portada** (Solo visible si "Soporte de tema" es "Custom")

    -   **Qué hace este ajuste:** Cuando se selecciona el soporte de tema "Custom", este campo le permite introducir manualmente el selector CSS para la etiqueta `<img>` real de su imagen principal de producto.
    -   **Efecto de cambiar este ajuste:** Si este selector es incorrecto, el zoom de Fancybox no se activará en su imagen principal de producto.
    -   **Valor recomendado:** Use las herramientas de desarrollador de su navegador para encontrar la clase o ID CSS única de la propia etiqueta `<img>`.
    -   **Escenario / ejemplo de comerciante:** Su tema personalizado utiliza `<img class="product-main-image-src">` para la imagen principal. Aquí introduciría `.product-main-image-src`.
-   **Selector de imágenes en miniatura** (Solo visible si "Soporte de tema" es "Custom")

    -   **Qué hace este ajuste:** Cuando se selecciona el soporte de tema "Custom", este campo le permite introducir manualmente el selector CSS para el elemento contenedor que contiene sus imágenes en miniatura del producto.
    -   **Efecto de cambiar este ajuste:** Si este selector es incorrecto, el módulo no podrá crear una galería Fancybox a partir de sus miniaturas, o al hacer clic en las miniaturas podría no abrir Fancybox.
    -   **Valor recomendado:** Use las herramientas de desarrollador de su navegador para encontrar la clase o ID CSS única del `<div>` u otro elemento contenedor que envuelve sus miniaturas de producto.
    -   **Escenario / ejemplo de comerciante:** Su tema personalizado utiliza `<ul id="product-thumbnails-list">` para las miniaturas. Aquí introduciría `#product-thumbnails-list`.

#### Ajustes de Comportamiento de Fancybox

Estos ajustes controlan cómo se comporta el zoom de Fancybox e interactúa con sus clientes.

-   **Crear galería**

    -   **Qué hace este ajuste:** Determina si todas las imágenes del producto (imagen principal y miniaturas) se agrupan en una única galería de Fancybox. Cuando está habilitado, al hacer clic en cualquier imagen se abrirá Fancybox, y los clientes podrán navegar por todas las imágenes del producto usando las flechas.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* Los clientes pueden navegar por todas las imágenes del producto en una superposición de Fancybox a pantalla completa, usando las flechas de navegación. Esto proporciona una vista completa del producto.
        -   *Cuando está deshabilitado ("No"):* Al hacer clic en una imagen, solo se abrirá esa imagen específica en Fancybox. Los clientes no pueden navegar a otras imágenes del producto desde la vista de Fancybox.
    -   **Valor recomendado:** "Sí" para una mejor experiencia de usuario y para animar a los clientes a ver todos los ángulos del producto.
    -   **Escenario / ejemplo de comerciante:** Desea que los clientes puedan pasar fácilmente por todas las imágenes del producto sin cerrar y volver a abrir el zoom para cada una. Habilite esto.
-   **Deslizar**

    -   **Qué hace este ajuste:** Habilita o deshabilita los gestos de deslizamiento para navegar por la galería de Fancybox en dispositivos con pantalla táctil (teléfonos inteligentes, tabletas).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* Los clientes pueden deslizar a la izquierda o a la derecha en sus dispositivos táctiles para moverse entre las imágenes de la galería de Fancybox.
        -   *Cuando está deshabilitado ("No"):* Los gestos de deslizamiento no funcionarán. Los clientes deberán usar las flechas de navegación (si "Crear galería" está habilitado).
    -   **Valor recomendado:** "Sí" para una experiencia móvil moderna e intuitiva.
    -   **Escenario / ejemplo de comerciante:** Desea que sus usuarios móviles tengan una forma fluida y natural de navegar por las imágenes del producto. Mantenga esto habilitado.
-   **Evitar imagen de portada duplicada en la galería**

    -   **Qué hace este ajuste:** Cuando "Crear galería" está habilitado, a veces la imagen principal del producto puede aparecer dos veces en la galería (una vez como imagen principal y otra vez si también aparece como miniatura). Este ajuste evita esa duplicación.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* El módulo intentará detectar y eliminar cualquier imagen principal de producto duplicada de la galería de Fancybox, asegurando que cada imagen aparezca solo una vez.
        -   *Cuando está deshabilitado ("No"):* Si la imagen principal del producto también forma parte de la lista de miniaturas, podría aparecer dos veces en la galería de Fancybox.
    -   **Valor recomendado:** "Sí" para una experiencia de galería más limpia y profesional.
    -   **Escenario / ejemplo de comerciante:** Observa que cuando los clientes abren la galería de Fancybox, la primera imagen es idéntica a la segunda. Habilitar esto lo solucionará.
-   **Mostrar subtítulos (títulos de imagen)**

    -   **Qué hace este ajuste:** Controla si el título/subtítulo asociado a cada imagen de producto se muestra dentro de la superposición de Fancybox. Estos títulos suelen establecerse en la gestión de imágenes de producto de su PrestaShop.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* El título de la imagen aparecerá como un subtítulo debajo o encima de la imagen en la superposición de Fancybox.
        -   *Cuando está deshabilitado ("No"):* No se mostrará ningún subtítulo, proporcionando una vista más limpia, solo de imagen.
    -   **Valor recomendado:** "Sí" si los títulos de sus imágenes proporcionan información útil (por ejemplo, "Vista frontal", "Detalle de la tela", "Modelo usando el producto"). "No" si los títulos de sus imágenes son genéricos o prefiere un aspecto minimalista.
    -   **Escenario / ejemplo de comerciante:** Utiliza títulos descriptivos para las imágenes de sus productos y desea que los clientes los vean al hacer zoom. Habilite esto.
-   **Cambiar imagen principal al pasar el ratón por la miniatura**

    -   **Qué hace este ajuste:** Determina si al pasar el ratón sobre una miniatura de producto se cambia automáticamente la imagen principal del producto mostrada en la página del producto, *antes* de hacer clic para abrir Fancybox.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* Al mover el cursor del ratón sobre una miniatura, la imagen principal del producto cambiará instantáneamente para mostrar la miniatura sobre la que se ha pasado el ratón. Esta es una característica común y conveniente para los compradores.
        -   *Cuando está deshabilitado ("No"):* La imagen principal del producto solo cambiará cuando se haga clic en una miniatura, no solo al pasar el ratón.
    -   **Valor recomendado:** "Sí" para una experiencia de navegación más interactiva y fácil de usar.
    -   **Escenario / ejemplo de comerciante:** Desea que los clientes previsualicen rápidamente diferentes imágenes de productos simplemente moviendo el ratón, sin necesidad de hacer clic. Habilite esto.

#### Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | **Soporte de tema** | Classic / Hummingbird | Selecciona selectores CSS predefinidos para su tema (Classic, Hummingbird o Custom). Crucial para la funcionalidad del módulo. |
| Configuración del Módulo | **Perfil de tema detectado** | N/A (Informativo) | Muestra qué perfil de tema está actualmente activo. |
| Configuración del Módulo | **Selector de portada Hummingbird** | Predeterminado | Selector CSS para el contenedor de la imagen principal (tema Hummingbird). |
| Configuración del Módulo | **Selector de imagen Hummingbird** | Predeterminado | Selector CSS para la etiqueta `<img>` principal (tema Hummingbird). |
| Configuración del Módulo | **Selector de miniaturas Hummingbird** | Predeterminado | Selector CSS para el contenedor de miniaturas (tema Hummingbird). |
| Configuración del Módulo | **Selector de imagen principal de portada** | Personalizado (Inspeccionar tema) | Selector CSS para el contenedor de la imagen principal (tema Custom). |
| Configuración del Módulo | **Imagen principal de portada** | Personalizado (Inspeccionar tema) | Selector CSS para la etiqueta `<img>` principal (tema Custom). |
| Configuración del Módulo | **Selector de imágenes en miniatura** | Personalizado (Inspeccionar tema) | Selector CSS para el contenedor de miniaturas (tema Custom). |
| Configuración del Módulo | **Crear galería** | Sí | Agrupa todas las imágenes del producto en una galería Fancybox navegable. |
| Configuración del Módulo | **Deslizar** | Sí | Habilita los gestos de deslizamiento para la navegación de la galería en dispositivos táctiles. |
| Configuración del Módulo | **Evitar imagen de portada duplicada en la galería** | Sí | Evita que la imagen principal aparezca dos veces en la galería. |
| Configuración del Módulo | **Mostrar subtítulos (títulos de imagen)** | Sí / No (Preferencia del comerciante) | Muestra los títulos de las imágenes como subtítulos en la superposición de Fancybox. |
| Configuración del Módulo | **Cambiar imagen principal al pasar el ratón por la miniatura** | Sí | Cambia la imagen principal del producto al pasar el ratón por la miniatura. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: El zoom de Fancybox no aparece en absoluto en las páginas de mis productos.**
R:

1.  **Verificar el estado del módulo:** Asegúrese de que el módulo esté instalado y habilitado en **Módulos > Gestor de Módulos**.
2.  **Configuración de soporte de tema:** Vaya a la página de configuración del módulo. Si está utilizando el tema "Classic", asegúrese de que "Soporte de tema" esté configurado en "Classic". Si está en PrestaShop 8.1+ con el tema Hummingbird, configúrelo en "Hummingbird". Si tiene un tema personalizado, configúrelo en "Custom" y revise cuidadosamente los selectores CSS que ha introducido (consulte el siguiente punto).
3.  **Selectores de tema personalizados:** Si "Soporte de tema" es "Custom", el problema más común son los selectores CSS incorrectos. Utilice las herramientas de desarrollador de su navegador (F12) para inspeccionar la página de su producto. Encuentre las clases o ID CSS exactas para el contenedor de su imagen principal de producto, la etiqueta `<img>` y el contenedor de sus miniaturas. Actualícelos en la configuración del módulo.

**P: Fancybox se abre, pero muestra la imagen incorrecta o solo una imagen.**
R:

1.  **Configuración "Crear galería":** Asegúrese de que "Crear galería" esté configurado en "Sí" en la configuración del módulo si desea navegar por varias imágenes.
2.  **Selectores de miniaturas:** Si "Crear galería" está activado pero solo aparece una imagen, verifique su "Selector de imágenes en miniatura" (especialmente si "Soporte de tema" es "Custom"). El módulo necesita identificar correctamente todas sus miniaturas para construir la galería.
3.  **Títulos/Subtítulos de imagen:** Si no se muestran los subtítulos, asegúrese de que "Mostrar subtítulos (títulos de imagen)" esté en "Sí" y de que las imágenes de sus productos realmente tengan títulos definidos en el back office de PrestaShop.

**P: Los gestos de deslizamiento no funcionan en mi dispositivo móvil.**
R:

1.  **Configuración "Deslizar":** Asegúrese de que la opción "Deslizar" esté configurada en "Sí" en la configuración del módulo.
2.  **Galería habilitada:** El deslizamiento solo funciona si "Crear galería" también está en "Sí", ya que es para navegar entre varias imágenes.
3.  **Compatibilidad con navegador/dispositivo:** Aunque ampliamente compatible, los navegadores muy antiguos o configuraciones de dispositivos específicas podrían tener problemas. Pruebe en un navegador móvil moderno.

**P: El diseño de la página de mi producto se ve un poco extraño después de instalar el módulo.**
R:

1.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché". A veces, los archivos de caché antiguos pueden interferir con el nuevo estilo del módulo.
2.  **Conflictos de tema:** Aunque el módulo intenta ser compatible, un CSS de tema personalizado muy específico podría entrar en conflicto. Si borrar la caché no ayuda, deshabilite temporalmente el módulo para ver si el problema desaparece. Si lo hace, es posible que necesite un desarrollador web para ajustar el CSS de su tema o los selectores personalizados del módulo.

**P: ¿Cómo encuentro los selectores CSS correctos para mi tema personalizado?**
R:

1.  Abra la página de su producto en un navegador web (Chrome, Firefox, Edge).
2.  Haga clic derecho en la imagen principal de su producto y seleccione "Inspeccionar" o "Inspeccionar elemento".
3.  Esto abrirá las herramientas de desarrollador del navegador. Busque la etiqueta `<img>` de su imagen principal y su `<div>` padre u otro contenedor. Anote cualquier atributo `id` único (por ejemplo, `id="my-image"`) o atributos `class` (por ejemplo, `class="product-image-wrapper"`).
4.  Repita esto para las miniaturas de sus productos.
5.  Utilice estas ID (precedidas de `#`, por ejemplo, `#my-image`) o clases (precedidas de `.`, por ejemplo, `.product-image-wrapper`) en la configuración de tema "Custom" del módulo. Es posible que deba experimentar un poco para encontrar los selectores más específicos y confiables.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo `fancyzoom` es un módulo ligero de PrestaShop diseñado principalmente para reemplazar la funcionalidad de zoom de imagen de producto predeterminada con Fancybox. Lo logra enganchándose a `displayHeader` para inyectar su JavaScript y CSS personalizados, y utilizando JavaScript para identificar y reinicializar los elementos de imagen con Fancybox. La configuración del módulo se maneja a través del método estándar `getContent()` en el archivo principal del módulo, almacenando la configuración en `ps_configuration`. No introduce tablas de base de datos personalizadas, clases `ObjectModel` o controladores frontales/administrativos dedicados más allá de la configuración principal del módulo.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. Toda la funcionalidad de front-office se inyecta a través de hooks y se maneja con JavaScript.
-   **Controladores de Back-Office Admin**: Ninguno. Toda la configuración de back-office se maneja mediante el método `getContent()` de la clase principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

-   No hay clases personalizadas ni definiciones de `ObjectModel` presentes en el directorio `classes/`. Toda la lógica central reside dentro del archivo principal del módulo `fancyzoom.php`.

### 4.4 Activos de JavaScript (`views/js/`)

El módulo incluye dos archivos JavaScript, principalmente para la funcionalidad de front-office. Se registran a través del hook `displayHeader`.

-   `fancyzoom/views/templates/js/fancyzoom.js`

    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Este es el script principal que inicializa Fancybox. Identifica dinámicamente la imagen principal del producto y las miniaturas basándose en los selectores CSS configurados (o los selectores predeterminados Classic/Hummingbird). Luego, vincula eventos de clic a estas imágenes para abrirlas en una galería de Fancybox. También maneja la funcionalidad de "cambiar imagen principal al pasar el ratón por la miniatura". Es responsable de deshabilitar el zoom predeterminado de PrestaShop.
    -   **Funcionalidades clave:**
        -   Deshabilita el zoom de imagen predeterminado de PrestaShop.
        -   Detecta el perfil del tema (Classic, Hummingbird, Custom) y aplica los selectores apropiados.
        -   Inicializa Fancybox en las imágenes del producto.
        -   Gestiona la creación de la galería Fancybox y sus opciones (deslizamiento, subtítulos, imágenes duplicadas).
        -   Maneja el efecto de pasar el ratón por la miniatura para cambiar la imagen principal.
        -   Escucha el evento `updateProduct` (actualizaciones de la página de producto de PrestaShop 1.7+) para reinicializar Fancybox.
-   `fancyzoom/views/templates/js/touchswipe.js`

    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Esta es una librería de terceros que proporciona una detección robusta de eventos de deslizamiento táctil. Es utilizada por `fancyzoom.js` para habilitar la navegación por deslizamiento dentro de la galería Fancybox en dispositivos táctiles.
    -   **Funcionalidades clave:** Proporciona un plugin de jQuery para detectar gestos de deslizamiento (izquierda, derecha, arriba, abajo) y otros eventos táctiles.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El módulo incluye un archivo CSS para el estilo del front-office.

-   `fancyzoom/views/templates/css/fancyzoom.css`
    -   **Alcance:** Estilo del cliente de front-office.
    -   **Responsabilidad:** Contiene el CSS necesario para la superposición de Fancybox en sí, incluyendo el estilo para las flechas de navegación, el botón de cierre, los subtítulos y la apariencia general. Asegura que el modal de Fancybox esté correctamente posicionado y estilizado.
    -   **Selectores de clase CSS clave que los desarrolladores pueden anular:**
        -   `.fancybox-container`: Contenedor principal para la superposición de Fancybox.
        -   `.fancybox-bg`: Superposición de fondo.
        -   `.fancybox-toolbar`: Barra de herramientas con botón de cierre, etc.
        -   `.fancybox-caption`: Área de subtítulos.
        -   `.fancybox-button`: Botones (cerrar, navegación).
        -   `.fancybox-image`: La imagen en sí dentro de Fancybox.
        Los desarrolladores pueden anular estas clases en el archivo `custom.css` de su tema o similar para que coincidan con la marca de su tienda.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   `fancyzoom/views/templates/hook/fancyzoom.tpl`
        -   **Hook:** `displayHeader`
        -   **Propósito:** Esta plantilla es responsable de inyectar las variables JavaScript necesarias y los archivos JS y CSS del módulo en la sección `<head>` del front-office. Pasa las variables de configuración del back office (como selectores, opciones de galería) al script `fancyzoom.js`.
-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `fancyzoom/views/templates/admin/admin.tpl`
        -   **Propósito:** Esta plantilla renderiza el formulario de configuración del módulo en el back office de PrestaShop. Muestra todos los ajustes descritos en la Sección 4.1, incluyendo campos de entrada para selectores, casillas de verificación para opciones de galería y la detección del perfil del tema.
-   **Plantillas de front-office (`views/templates/front/`)**: Ninguna.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:
    El módulo no crea ninguna tabla de base de datos personalizada. Todas sus configuraciones se almacenan en la tabla `ps_configuration` utilizando claves con el prefijo `FZ_` (por ejemplo, `FZ_THEME`, `FZ_COVER_DIV`, `FZ_GALLERY`).
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Inyecta los archivos CSS y JavaScript del módulo, y pasa las variables de configuración a los scripts del front-end. Aquí es donde se carga la librería Fancybox y su lógica de inicialización. |

## 5. Soporte Oficial y Actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y descargar las últimas versiones del módulo "Zoom de imagen de productos Fancybox", inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.

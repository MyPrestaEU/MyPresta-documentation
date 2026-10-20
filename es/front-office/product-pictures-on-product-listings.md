---
title: "Imágenes de productos en listados de productos - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Imágenes de productos en listados de productos' de MyPresta.eu."
sidebar:
  label: "Imágenes de productos en listados de productos - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product pictures on product listings en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-pictures-on-product-listings.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-pictures-on-product-listings/)
>
> ---


# Imágenes de productos en listados de productos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son necesarias para PrestaShop en sí y generalmente están disponibles en todos los entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Imágenes de productos en listados de productos". Puedes acceder a ella navegando a **Módulos > Gestor de Módulos** y haciendo clic en "Configurar" junto al nombre del módulo.

#### **Posición del módulo**

- **Qué hace esta configuración:** Esto determina dónde aparecerán las imágenes adicionales del producto en relación con la imagen principal del producto en las páginas de listado.
- **Efecto de cambiar esta configuración:**
  - *displayProductAdditionalInfo:* Las imágenes aparecerán en un hook común a menudo utilizado para detalles adicionales del producto.
  - *displayAfterProductThumbs:* Las imágenes aparecerán inmediatamente después de las miniaturas de la imagen principal del producto (si tu tema las muestra).
  - *displayFooterProduct:* Las imágenes aparecerán en la sección del pie de página del bloque de producto en la página de listado.
  - *displayProductDeliveryTime:* Las imágenes aparecerán cerca de la información de tiempo de entrega (si tu tema la muestra).
  - *displayHeader:* Esta es una posición menos común para las imágenes de productos en las páginas de listado y podría requerir un estilo personalizado para verse bien.
  - *displayProductListReviews:* Las imágenes aparecerán cerca de las estrellas o el recuento de reseñas del producto (si tu tema las muestra).
- **Valor recomendado:** Experimenta primero con `displayProductAdditionalInfo` o `displayAfterProductThumbs`, ya que estas suelen ser buenas ubicaciones visuales.
- **Escenario / ejemplo de comerciante:** Si tu tema tiene un diseño limpio y quieres que las imágenes se integren sutilmente debajo de la imagen principal, `displayProductAdditionalInfo` podría ser lo mejor. Si quieres que destaquen más, `displayFooterProduct` podría funcionar.

#### **Diseño del módulo**

- **Qué hace esta configuración:** Esto te permite elegir entre diferentes estilos visuales para la salida del módulo, afectando principalmente cómo se presentan las miniaturas.
- **Efecto de cambiar esta configuración:**
  - *Tema clásico:* Aplica un estilo que a menudo es compatible con temas de PrestaShop más antiguos o temas que imitan el aspecto clásico.
  - *Universal:* Aplica un diseño más moderno y responsivo que busca funcionar bien en una gama más amplia de temas contemporáneos.
- **Valor recomendado:** `Universal` para la mayoría de las tiendas PrestaShop modernas (1.7.x, 8.x, 9.x). Usa `Tema clásico` si tienes un tema más antiguo o altamente personalizado que no renderiza `Universal` correctamente.
- **Escenario / ejemplo de comerciante:** Si tu tienda utiliza un tema predeterminado de PrestaShop 8, `Universal` probablemente se integrará sin problemas. Si estás en PrestaShop 1.6 con un tema personalizado, `Tema clásico` podría ser una apuesta más segura.

#### **Método de visualización**

- **Qué hace esta configuración:** Esto controla qué imágenes adicionales se muestran para cada producto en la página de listado.
- **Efecto de cambiar esta configuración:**
  - *Imágenes para combinaciones de color:* Solo muestra imágenes específicamente vinculadas a los atributos de color de un producto. Útil para moda o productos con variantes de color distintas.
  - *Imágenes para cada combinación:* Muestra imágenes para todas las combinaciones de productos (por ejemplo, tamaño, color, material). Esto puede llevar a muchas imágenes si tienes muchas combinaciones.
  - *Todas las imágenes del producto:* Muestra todas las imágenes asociadas con el producto, independientemente de la combinación. Esta es la opción más completa.
- **Valor recomendado:** `Todas las imágenes del producto` para la mayoría de los productos generales. `Imágenes para combinaciones de color` si tus productos dependen en gran medida de las variaciones de color y quieres mantener el recuento de imágenes manejable.
- **Escenario / ejemplo de comerciante:** Para una tienda de ropa, seleccionar `Imágenes para combinaciones de color` mostraría todos los colores disponibles para una camiseta específica. Para una tienda de muebles, `Todas las imágenes del producto` mostraría diferentes ángulos y primeros planos de un sofá.

#### **Solo en stock**

- **Qué hace esta configuración:** Esta opción filtra las imágenes mostradas según la disponibilidad de stock del producto.
- **Efecto de cambiar esta configuración:**
  - *Habilitado:* Solo muestra imágenes para combinaciones de productos que están actualmente en stock. Si un color específico está agotado, sus imágenes asociadas no aparecerán.
  - *Deshabilitado:* Muestra todas las imágenes seleccionadas, independientemente del estado del stock.
- **Valor recomendado:** `Habilitado` para evitar mostrar a los clientes imágenes de productos que no pueden comprar de inmediato, lo que puede generar frustración.
- **Escenario / ejemplo de comerciante:** Si vendes zapatos y una combinación particular de talla/color está agotada, habilitar esto evita que los clientes vean imágenes de esa variante específica, guiándolos hacia las opciones disponibles.

#### **Mostrar cuadros de color en lugar de imágenes**

- **Qué hace esta configuración:** En lugar de mostrar pequeñas miniaturas de imágenes, esta opción muestra muestras de color (cuadros) para las combinaciones de productos.
- **Efecto de cambiar esta configuración:**
  - *Habilitado:* Reemplaza las miniaturas de imágenes con pequeños cuadros de color, típicamente usando el color definido para el atributo del producto.
  - *Deshabilitado:* Muestra miniaturas de imágenes reales.
- **Valor recomendado:** `Deshabilitado` si quieres mostrar imágenes reales del producto. `Habilitado` si tus productos tienen atributos de color claros y prefieres un aspecto más limpio y compacto para la selección de color.
- **Escenario / ejemplo de comerciante:** Para una tienda de pintura, habilitar esto mostraría pequeños cuadrados de colores que representan diferentes colores de pintura, lo cual es más eficiente que mostrar una pequeña imagen de cada color.

#### **Contenedor principal del producto en la lista de productos**

- **Qué hace esta configuración:** Esta es una configuración técnica para ayudar al módulo a identificar el contenedor principal de cada producto en tus páginas de listado. Requiere un selector CSS.
- **Efecto de cambiar esta configuración:** Si se configura incorrectamente, el módulo podría no ser capaz de encontrar dónde inyectar las imágenes adicionales, o podría inyectarlas en el lugar equivocado.
- **Valor recomendado:** Esto depende completamente de tu tema. Los valores comunes son `.product-miniature`, `.product-container` o `.ajax_block_product`. Es posible que necesites inspeccionar el HTML de tu tema para encontrar el selector correcto.
- **Escenario / ejemplo de comerciante:** Si tu tema usa `<div class="product-item">` para cada producto, deberías introducir `.product-item` aquí.

#### **CSS de la imagen de portada del producto**

- **Qué hace esta configuración:** Esta es una configuración técnica para ayudar al módulo a identificar el elemento de la imagen principal del producto dentro de cada contenedor de producto. Requiere un selector CSS.
- **Efecto de cambiar esta configuración:** Si se configura incorrectamente, el módulo no podrá cambiar la imagen principal del producto cuando se haga clic/pase el ratón sobre una miniatura.
- **Valor recomendado:** Esto depende de tu tema. Los valores comunes son `.product-thumbnail`, `.img-fluid` o `img.replace-me`. Es posible que necesites inspeccionar el HTML de tu tema.
- **Escenario / ejemplo de comerciante:** Si la imagen principal de tu tema tiene la clase `product-image-thumb`, deberías introducir `.product-image-thumb` aquí.

#### **CSS del ancla de la imagen de portada del producto**

- **Qué hace esta configuración:** Esta es una configuración técnica para ayudar al módulo a identificar el enlace (etiqueta `<a>`) que envuelve la imagen principal del producto. Esto es importante para asegurar que el enlace siga funcionando correctamente después del cambio de imagen.
- **Efecto de cambiar esta configuración:** Si se configura incorrectamente, hacer clic en la imagen principal del producto podría no llevar a la página del producto, o el cambio de imagen podría fallar.
- **Valor recomendado:** Esto depende de tu tema. Los valores comunes son `.product-thumbnail a`, `.product-image a` o `a.product-cover`. Es posible que necesites inspeccionar el HTML de tu tema.
- **Escenario / ejemplo de comerciante:** Si tu tema envuelve la imagen principal del producto en `<a class="product-link">`, deberías introducir `a.product-link` aquí.

#### **Ancla del título del producto**

- **Qué hace esta configuración:** Esta es una configuración técnica para identificar el enlace (etiqueta `<a>`) alrededor del título del producto.
- **Efecto de cambiar esta configuración:** Esta configuración ayuda al módulo a asegurar que el enlace del título del producto siga siendo funcional y apunte correctamente a la página del producto.
- **Valor recomendado:** Esto depende de tu tema. Los valores comunes son `.product-title a`, `.product-name a` o `h3 a`. Es posible que necesites inspeccionar el HTML de tu tema.
- **Escenario / ejemplo de comerciante:** Si los títulos de tus productos están envueltos en `<h3 class="product-name"><a href="...">`, deberías introducir `h3.product-name a` aquí.

#### **Clase adicional para el ancla en miniatura**

- **Qué hace esta configuración:** Esto te permite añadir una clase CSS extra a las etiquetas `<a>` de las imágenes en miniatura mostradas por el módulo. Esto es útil para estilos personalizados.
- **Efecto de cambiar esta configuración:** La clase especificada se añadirá al HTML de los enlaces de las imágenes en miniatura, permitiéndote dirigirte a ellos con reglas CSS personalizadas en tu tema.
- **Valor recomendado:** Déjalo vacío a menos que tengas requisitos específicos de estilo personalizado.
- **Escenario / ejemplo de comerciante:** Si quieres añadir un borde especial a tus imágenes en miniatura, podrías introducir `mi-clase-miniatura-personalizada` aquí, y luego añadir CSS como `.mi-clase-miniatura-personalizada img { border: 1px solid blue; }` a tu tema.

#### **Método de cambio de imagen**

- **Qué hace esta configuración:** Esto controla cómo cambia la imagen principal del producto cuando un cliente interactúa con las miniaturas adicionales.
- **Efecto de cambiar esta configuración:**
  - *Al hacer clic:* La imagen principal cambia solo cuando un cliente hace clic en una miniatura.
  - *Al pasar el ratón:* La imagen principal cambia cuando un cliente mueve el cursor del ratón sobre una miniatura (sin hacer clic).
  - *Slider:* El módulo muestra un pequeño slider con flechas de navegación, permitiendo a los clientes desplazarse por las imágenes. Esto a menudo implica un comportamiento de "al hacer clic" para los controles del slider.
- **Valor recomendado:** `Al pasar el ratón` para una experiencia rápida e interactiva. `Al hacer clic` si prefieres una acción explícita del usuario. `Slider` si tienes muchas imágenes y quieres una presentación más compacta.
- **Escenario / ejemplo de comerciante:** Para una tienda de moda, `Al pasar el ratón` permite a los clientes previsualizar rápidamente diferentes looks. Para un producto con muchas imágenes detalladas, `Slider` puede mantener la página de listado limpia mientras ofrece acceso completo a todos los elementos visuales.

#### **Imágenes para combinaciones de color (configuración duplicada, probablemente un error o legado)**

- **Qué hace esta configuración:** Esto parece ser un duplicado de la configuración "Método de visualización", específicamente relacionado con la visualización de imágenes para combinaciones de color.
- **Efecto de cambiar esta configuración:** Es mejor confiar en la configuración "Método de visualización" para esta funcionalidad. Si este es un control separado, podría anular o entrar en conflicto con la configuración "Método de visualización".
- **Valor recomendado:** Asegurar la coherencia con la configuración "Método de visualización".
- **Escenario / ejemplo de comerciante:** Si "Método de visualización" está configurado en "Imágenes para combinaciones de color", esta configuración también debería estar habilitada o ser coherente.

#### **Imágenes para cada combinación (configuración duplicada, probablemente un error o legado)**

- **Qué hace esta configuración:** Similar a la anterior, esto parece ser un duplicado de la configuración "Método de visualización", específicamente relacionado con la visualización de imágenes para todas las combinaciones.
- **Efecto de cambiar esta configuración:** Es mejor confiar en la configuración "Método de visualización".
- **Valor recomendado:** Asegurar la coherencia con la configuración "Método de visualización".
- **Escenario / ejemplo de comerciante:** Si "Método de visualización" está configurado en "Imágenes para cada combinación", esta configuración también debería estar habilitada o ser coherente.

#### **Todas las imágenes del producto (configuración duplicada, probablemente un error o legado)**

- **Qué hace esta configuración:** Similar a la anterior, esto parece ser un duplicado de la configuración "Método de visualización", específicamente relacionado con la visualización de todas las imágenes del producto.
- **Efecto de cambiar esta configuración:** Es mejor confiar en la configuración "Método de visualización".
- **Valor recomendado:** Asegurar la coherencia con la configuración "Método de visualización".
- **Escenario / ejemplo de comerciante:** Si "Método de visualización" está configurado en "Todas las imágenes del producto", esta configuración también debería estar habilitada o ser coherente.

#### **Tabla de Referencia Rápida de Configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Posición del módulo | `displayProductAdditionalInfo` | Determina dónde aparecen las imágenes adicionales en los listados de productos. |
| Configuración del Módulo | Diseño del módulo | `Universal` | Establece el estilo visual para las miniaturas de imagen (Clásico vs. Moderno). |
| Configuración del Módulo | Método de visualización | `Todas las imágenes del producto` | Controla qué imágenes se muestran (combinaciones de color, todas las combinaciones o todas las imágenes del producto). |
| Configuración del Módulo | Solo en stock | `Habilitado` | Filtra las imágenes para mostrar solo las combinaciones de productos en stock. |
| Configuración del Módulo | Mostrar cuadros de color en lugar de imágenes | `Deshabilitado` | Reemplaza las miniaturas de imágenes con muestras de color si está habilitado. |
| Configuración del Módulo | Contenedor principal del producto en la lista de productos | `.product-miniature` (o específico del tema) | Selector CSS para el bloque principal del producto en las páginas de listado. |
| Configuración del Módulo | CSS de la imagen de portada del producto | `.product-thumbnail` (o específico del tema) | Selector CSS para el elemento de la imagen principal del producto. |
| Configuración del Módulo | CSS del ancla de la imagen de portada del producto | `.product-thumbnail a` (o específico del tema) | Selector CSS para el enlace que envuelve la imagen principal del producto. |
| Configuración del Módulo | Ancla del título del producto | `h3 a` (o específico del tema) | Selector CSS para el enlace que envuelve el título del producto. |
| Configuración del Módulo | Clase adicional para el ancla en miniatura | Dejar vacío | Añade una clase CSS personalizada a los enlaces de las imágenes en miniatura para estilizar. |
| Configuración del Módulo | Método de cambio de imagen | `Al pasar el ratón` | Define cómo cambia la imagen principal (clic, pasar el ratón o slider). |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Las imágenes adicionales no aparecen en mis listados de productos.**

-   **R:** Primero, verifica la configuración de tu módulo:
    -   Asegúrate de que "Posición del módulo" esté configurado en un hook que tu tema realmente renderice (por ejemplo, `displayProductAdditionalInfo`). Si tu tema está muy personalizado, es posible que necesites probar diferentes posiciones o consultar a un desarrollador.
    -   Verifica las configuraciones de "Contenedor principal del producto en la lista de productos", "CSS de la imagen de portada del producto", "CSS del ancla de la imagen de portada del producto" y "Ancla del título del producto". Estos son selectores CSS cruciales que deben coincidir con la estructura HTML de tu tema. Utiliza las herramientas de desarrollo de tu navegador (F12) para inspeccionar los elementos de tu página de categoría y encontrar las clases/IDs correctas.
    -   Asegúrate de que los productos realmente tengan varias imágenes subidas en su configuración de producto en el Back Office.
-   **R:** Borra la caché de PrestaShop: Ve a **Parámetros Avanzados > Rendimiento** y haz clic en "Borrar caché" en la parte superior derecha. Además, borra la caché de tu navegador.

**P2: Las imágenes aparecen, pero no cambian cuando paso el ratón/hago clic.**

-   **R:** Esto suele indicar un problema con los selectores CSS para la imagen principal del producto o su contenedor.
    -   Vuelve a verificar "CSS de la imagen de portada del producto" y "CSS del ancla de la imagen de portada del producto". Estos deben apuntar con precisión a la imagen principal y su enlace envolvente.
    -   Asegúrate de que no haya errores de JavaScript en tu página que puedan estar impidiendo la ejecución del script del módulo. Revisa la consola de desarrollador de tu navegador (F12 > pestaña Consola).
    -   Si tienes otros módulos que modifican los listados de productos, podría haber un conflicto. Intenta deshabilitar temporalmente otros módulos del front-office para aislar el problema.

**P3: Las imágenes se ven distorsionadas o el estilo es incorrecto.**

-   **R:**
    -   Intenta cambiar la configuración de "Diseño del módulo" entre `Tema clásico` y `Universal` para ver si uno se integra mejor con tu tema.
    -   Tu tema podría tener reglas CSS en conflicto. Puedes usar la configuración "Clase adicional para el ancla en miniatura" para añadir una clase personalizada y luego usar CSS personalizado en tu tema para anular los estilos en conflicto.
    -   Asegúrate de que las imágenes de tus productos subidas sean de calidad y relación de aspecto consistentes.

**P4: Estoy usando un tema personalizado y el módulo no parece funcionar en absoluto.**

-   **R:** Los temas personalizados a menudo utilizan diferentes estructuras HTML y clases CSS que los temas predeterminados de PrestaShop.
    -   Casi con certeza necesitarás ajustar los selectores CSS para "Contenedor principal del producto en la lista de productos", "CSS de la imagen de portada del producto", "CSS del ancla de la imagen de portada del producto" y "Ancla del título del producto" para que coincidan con el marcado específico de tu tema. Esto generalmente requiere conocimientos básicos de inspección de HTML/CSS utilizando las herramientas de desarrollo del navegador.
    -   Tu tema personalizado podría no estar llamando a los hooks estándar de PrestaShop que utiliza el módulo. Es posible que necesites añadir manualmente las llamadas a los hooks del módulo a los archivos `.tpl` de tu tema (consulta a tu desarrollador de temas o a un desarrollador de PrestaShop para esto).

**P5: El módulo ralentiza la velocidad de carga de mi página.**

-   **R:** Aunque el módulo está optimizado, mostrar muchas imágenes adicionales puede aumentar naturalmente el tiempo de carga de la página.
    -   Asegúrate de que las imágenes de tus productos estén optimizadas para la web (comprimidas, dimensiones apropiadas).
    -   Considera usar la opción "Solo en stock" para reducir el número de imágenes cargadas para artículos agotados.
    -   Si tienes muchas imágenes por producto, considera usar el método `Slider`, que a menudo carga las imágenes de manera más eficiente o de forma perezosa.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Imágenes de productos en listados de productos", destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Visión General de la Arquitectura

El módulo `productlistpics` es principalmente un módulo de características de front-office diseñado para inyectar funcionalidad adicional de imágenes de productos en las plantillas de listado de productos existentes. Aprovecha el sistema de hooks de PrestaShop para renderizar su contenido y utiliza JavaScript para manejar el cambio dinámico de imágenes (pasar el ratón/hacer clic) o la funcionalidad de slider. La configuración se gestiona a través del método estándar `getContent()` en la clase principal del módulo, almacenando la configuración en `ps_configuration`. El módulo no introduce tablas de base de datos personalizadas ni entidades `ObjectModel` complejas.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la lógica está encapsulada dentro de la clase principal del módulo y sus plantillas y activos asociados.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo **no** contiene ninguna clase personalizada o entidad `ObjectModel` en el directorio `classes/`. Toda la lógica principal reside dentro de `productlistpics.php`.

### 4.4 Activos JavaScript (`views/js/`)

El módulo incluye varios archivos JavaScript, principalmente para manejar el cambio de imágenes y la funcionalidad del slider.

-   `productlistpics/js/owl-carousel/owl.carousel.js`:
    -   **Alcance:** Front-office.
    -   **Descripción:** Esta es la biblioteca principal de Owl Carousel, un popular plugin de jQuery habilitado para el tacto para carruseles responsivos. Proporciona la funcionalidad fundamental para crear sliders de imágenes.
-   `productlistpics/js/owl-carousel/owl.run.js`:
    -   **Alcance:** Front-office.
    -   **Descripción:** Este script probablemente contiene el código de inicialización y configuración para las instancias de Owl Carousel utilizadas por el módulo. Configura el comportamiento del slider, la capacidad de respuesta y las opciones de navegación basadas en la configuración del módulo.
-   `productlistpics/js/plp-replacement.js`:
    -   **Alcance:** Front-office.
    -   **Descripción:** Este script es probablemente responsable de la lógica central de reemplazar la imagen principal del producto cuando se interactúa con una miniatura. Escucha eventos (clic/pasar el ratón) en las miniaturas generadas y actualiza los atributos `src` y `srcset` de la imagen principal del producto, potencialmente también actualizando el `href` de la etiqueta `<a>` de la imagen principal.
-   `productlistpics/js/productlistpics-mouseover.js`:
    -   **Alcance:** Front-office.
    -   **Descripción:** Este script implementa específicamente el método de cambio de imagen "Al pasar el ratón". Adjunta oyentes de eventos `mouseover` y `mouseout` a los anclajes de las imágenes en miniatura para activar el reemplazo de la imagen principal.
-   `productlistpics/js/productlistpics.js`:
    -   **Alcance:** Front-office.
    -   **Descripción:** Este es probablemente el punto de entrada principal de JavaScript del front-office del módulo. Podría manejar el método de cambio de imagen "Al hacer clic", la manipulación general del DOM relacionada con la inyección de las miniaturas y, potencialmente, la orquestación de la carga de otros scripts basados en la configuración.
-   `productlistpics/js/slider-productlistpics-mouseover.js`:
    -   **Alcance:** Front-office.
    -   **Descripción:** Este script combina la funcionalidad del slider con el cambio de imagen basado en el paso del ratón. Probablemente inicializaría el Owl Carousel y luego añadiría oyentes de paso del ratón a los elementos del slider para actualizar la imagen principal del producto.
-   `productlistpics/js/slider-productlistpics.js`:
    -   **Alcance:** Front-office.
    -   **Descripción:** Este script integra el slider Owl Carousel con el cambio de imagen basado en el clic. Inicializa el slider y maneja los clics en los elementos del slider para actualizar la imagen principal del producto.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El módulo incluye varios archivos CSS para estilizar los elementos inyectados y el Owl Carousel.

-   `productlistpics/css.css`:
    -   **Alcance:** Front-office.
    -   **Descripción:** Estilo general para los elementos del módulo, como el contenedor para imágenes adicionales, el tamaño de las miniaturas y el diseño básico.
-   `productlistpics/js/owl-carousel/owl.carousel.css`:
    -   **Alcance:** Front-office.
    -   **Descripción:** Estilos base para el plugin Owl Carousel, definiendo la estructura y la apariencia predeterminada del slider.
-   `productlistpics/js/owl-carousel/owl.theme.css`:
    -   **Alcance:** Front-office.
    -   **Descripción:** Tema predeterminado para Owl Carousel, proporcionando estilo visual para los botones de navegación, puntos y la estética general del slider.
-   `productlistpics/js/owl-carousel/owl.transitions.css`:
    -   **Alcance:** Front-office.
    -   **Descripción:** CSS para varios efectos de transición utilizados por Owl Carousel (por ejemplo, fundido, deslizamiento).
-   `productlistpics/productlistpics-classic.css`:
    -   **Alcance:** Front-office.
    -   **Descripción:** Reglas de estilo específicas aplicadas cuando se selecciona la opción de diseño "Tema clásico" en la configuración del módulo. Esto se dirige a temas de PrestaShop más antiguos o temas que imitan el aspecto clásico.
-   `productlistpics/productlistpics.css`:
    -   **Alcance:** Front-office.
    -   **Descripción:** Estilo principal para el módulo, probablemente conteniendo reglas para la opción de diseño "Universal" y anulaciones o mejoras generales.

**Selectores de clase CSS clave que los desarrolladores pueden anular:**

-   `.productlistpics-container`: El contenedor principal para las imágenes adicionales.
-   `.productlistpics-thumb`: Contenedores individuales de miniaturas.
-   `.productlistpics-thumb img`: La imagen real dentro de la miniatura.
-   `.owl-carousel`, `.owl-item`, `.owl-nav`, `.owl-dots`: Selectores estándar de Owl Carousel para la personalización del slider.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty para renderizar su contenido dentro de varios hooks de PrestaShop.

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `productlistpics/header.tpl`:
        -   **Hook:** `displayHeader` (o similar, típicamente registrado en `install()`).
        -   **Salida:** Esta plantilla es responsable de incluir los activos CSS y JavaScript necesarios para que el módulo funcione en el front-office. Carga condicionalmente scripts basados en el "Método de cambio de imagen" elegido (por ejemplo, `owl.carousel.js`, `productlistpics-mouseover.js`, `slider-productlistpics.js`).
    -   `productlistpics/html.tpl`:
        -   **Hook:** Esta es una plantilla genérica que podría ser incluida por otras plantillas o utilizada para bloques de contenido específicos. Su uso exacto depende de cómo el archivo PHP principal del módulo renderiza el contenido.
        -   **Salida:** Contiene la estructura HTML para mostrar las imágenes adicionales del producto, incluyendo bucles para iterar a través de las imágenes y lógica condicional para mostrar cuadros de color o miniaturas de imágenes.
    -   `productlistpics/productFooter.tpl`:
        -   **Hook:** `displayFooterProduct` (según lo configurado en "Posición del módulo").
        -   **Salida:** Renderiza las imágenes adicionales del producto en la sección del pie de página de un bloque de producto en las páginas de listado. Probablemente incluye `html.tpl` o lógica similar.
    -   `productlistpics/productPage.tpl`:
        -   **Hook:** Esta plantilla se utiliza probablemente para hooks como `displayProductAdditionalInfo`, `displayAfterProductThumbs`, `displayProductDeliveryTime`, `displayProductListReviews` (según lo configurado en "Posición del módulo").
        -   **Salida:** Renderiza las imágenes adicionales del producto dentro del hook de listado de productos especificado. Contiene la lógica central para generar las miniaturas de imágenes o los cuadros de color y configurar los atributos de datos necesarios para la interacción de JavaScript.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:
    El módulo **no** crea ninguna tabla de base de datos personalizada. Todas sus configuraciones se almacenan en la tabla `ps_configuration` utilizando claves como `PLP_TYPE`, `PLP_INSTOCK`, `PLP_METHOD`, `PLP_SWITCH`, `PLP_DESIGN`, `PLP_POSITION` y varias claves de selector CSS (`pls_product_miniature`, `pls_product_miniature_img`, etc.).
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Inyecta los activos CSS y JavaScript requeridos por el módulo. |
| `displayProductAdditionalInfo` | Dentro del bloque de miniatura del producto, a menudo debajo de la imagen principal o el título. | Renderiza las miniaturas/slider de imágenes adicionales del producto. |
| `displayAfterProductThumbs` | Después de las miniaturas de la imagen principal del producto (si están presentes). | Renderiza las miniaturas/slider de imágenes adicionales del producto. |
| `displayFooterProduct` | En el área del pie de página de cada bloque de miniatura del producto. | Renderiza las miniaturas/slider de imágenes adicionales del producto. |
| `displayProductDeliveryTime` | Cerca de la información de tiempo de entrega del producto en la miniatura del producto. | Renderiza las miniaturas/slider de imágenes adicionales del producto. |
| `displayProductListReviews` | Cerca de las estrellas/recuento de reseñas del producto en la miniatura del producto. | Renderiza las miniaturas/slider de imágenes adicionales del producto. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Imágenes de productos en listados de productos", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto a la funcionalidad y compatibilidad del módulo.

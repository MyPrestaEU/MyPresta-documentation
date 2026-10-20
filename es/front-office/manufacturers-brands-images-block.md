---
title: "Bloque de imágenes de fabricantes (marcas) - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Bloque de imágenes de fabricantes (marcas)' de MyPresta.eu."
sidebar:
  label: "Bloque de imágenes de fabricantes (marcas) - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Manufacturers (brands) images block en MyPresta.eu](https://mypresta.eu/modules/front-office-features/manufacturers-brands-images-block.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/manufacturers-brands-images-block/)
>
> ---


# Bloque de imágenes de fabricantes (marcas)

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se suelen necesitar configuraciones de servidor especiales más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página de configuración principal del módulo "Bloque de imágenes de fabricantes (marcas)". Aquí puede personalizar cómo aparece y se comporta el bloque de marcas en su tienda.

#### **Posición del bloque de fabricantes**

-   **Qué hace este ajuste:** Este ajuste crucial determina dónde aparecerá el bloque de imágenes de marcas en su sitio web. Puede elegir entre varias ubicaciones predefinidas (hooks) dentro de su tema de PrestaShop.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en `displayRightColumn` (o `displayLeftColumn`):* El bloque de marcas aparecerá en la barra lateral derecha (o izquierda) de su tienda, normalmente junto a otros bloques como categorías o los más vendidos. Esto es ideal para una visibilidad constante.
    -   *Cuando se establece en `displayFooter`:* El bloque aparecerá en la parte inferior de su sitio web, a menudo utilizado para la navegación suplementaria.
    -   *Cuando se establece en `displayTop` (o `displayTopColumn`):* El bloque será visible cerca de la parte superior de su página, a menudo en el área de la cabecera, haciendo que las marcas sean inmediatamente perceptibles.
    -   *Cuando se establece en `displayHome`:* El bloque solo aparecerá en la página de inicio de su tienda, convirtiéndolo en una característica central para el descubrimiento de marcas.
-   **Valor recomendado:** `displayHome` para una característica destacada en la página de inicio, o `displayRightColumn` (o `displayLeftColumn`) para una visibilidad constante en las páginas de productos y categorías.
-   **Escenario / ejemplo de comerciante:** Si desea que los clientes puedan navegar fácilmente por las marcas mientras compran productos, elija `displayRightColumn`. Si desea hacer una fuerte declaración de marca en su página de inicio, elija `displayHome`.

#### **Habilitar carrusel**

-   **Qué hace este ajuste:** Este ajuste transforma la cuadrícula estática de logotipos de marcas en un carrusel animado y desplazable.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Los logotipos de las marcas se desplazarán horizontalmente, lo que le permitirá mostrar muchas marcas en un espacio compacto. Esto es visualmente dinámico y ahorra espacio en pantalla.
    -   *Cuando está deshabilitado (NO):* Los logotipos de las marcas se mostrarán como una cuadrícula estática, mostrando todos los logotipos disponibles a la vez (o tantos como quepan en las dimensiones del bloque). Esto ofrece una visión general inmediata sin interacción.
-   **Valor recomendado:** `SÍ` si tiene muchas marcas o desea un aspecto más moderno y dinámico. `NO` si tiene solo unas pocas marcas y prefiere una visualización estática.
-   **Escenario / ejemplo de comerciante:** Si tiene más de 50 marcas, habilitar el carrusel es esencial para evitar un bloque muy largo y desordenado. Si solo tiene de 5 a 10 marcas, una visualización estática podría ser suficiente.

#### **Activar filtro de categorías**

-   **Qué hace este ajuste:** Esto permite que el módulo muestre solo aquellos fabricantes que están asociados con productos dentro de la *categoría actualmente vista*.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* En una página de categoría (por ejemplo, "Camisetas"), el bloque de marcas solo mostrará los logotipos de los fabricantes que producen camisetas. Esto hace que el bloque sea altamente relevante para el contexto de navegación actual del cliente.
    -   *Cuando está deshabilitado (NO):* El bloque de marcas siempre mostrará *todos* los fabricantes activos en su tienda, independientemente de la página o categoría actual.
-   **Valor recomendado:** `SÍ` para una mejor experiencia de usuario y relevancia, especialmente en tiendas con diversas categorías de productos.
-   **Escenario / ejemplo de comerciante:** Un cliente que navega por "Smartphones" solo verá marcas como Apple, Samsung y Xiaomi si esto está habilitado, en lugar de ver también marcas de ropa. Esto les ayuda a acotar su búsqueda.

#### **Habilitar desplazamiento automático para el carrusel**

-   **Qué hace este ajuste:** Si el carrusel está habilitado, este ajuste controla si los logotipos de las marcas se desplazan automáticamente sin la interacción del cliente.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* El carrusel se deslizará automáticamente a través de los logotipos de las marcas a una velocidad establecida, creando un efecto visual dinámico.
    -   *Cuando está deshabilitado (NO):* El carrusel solo se desplazará cuando el cliente haga clic manualmente en las flechas de navegación o arrastre el carrusel.
-   **Valor recomendado:** `SÍ` para una visualización más atractiva y dinámica, pero asegúrese de que la velocidad no sea demasiado rápida.
-   **Escenario / ejemplo de comerciante:** Desea asegurarse de que todas sus marcas tengan cierta visibilidad incluso si los clientes no interactúan con el carrusel. Habilitar el desplazamiento automático logra esto.

#### **Velocidad de desplazamiento automático**

-   **Qué hace este ajuste:** Este ajuste define la rapidez con la que el carrusel se desplaza automáticamente de un conjunto de marcas al siguiente, medido en milisegundos. (Solo aplicable si "Habilitar desplazamiento automático para el carrusel" es SÍ).
-   **Efecto de cambiar este ajuste:**
    -   *Valor más alto (por ejemplo, 5000ms = 5 segundos):* Velocidad de desplazamiento más lenta, dando a los clientes más tiempo para ver cada conjunto de logotipos.
    -   *Valor más bajo (por ejemplo, 2000ms = 2 segundos):* Velocidad de desplazamiento más rápida, haciendo que el carrusel sea más dinámico pero potencialmente más difícil de leer.
-   **Valor recomendado:** 3000-5000 milisegundos (3-5 segundos) para una experiencia de visualización cómoda.
-   **Escenario / ejemplo de comerciante:** Si tiene muchas marcas y desea que los clientes las vean todas sin sentirse apurados, establezca una velocidad más lenta como 4000ms.

#### **Pausar carrusel al pasar el ratón**

-   **Qué hace este ajuste:** Si el desplazamiento automático está habilitado, este ajuste controla si el carrusel detiene temporalmente el desplazamiento cuando un cliente mueve el cursor del ratón sobre el bloque de marcas.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* El carrusel se pausará, permitiendo al cliente examinar cómodamente un logotipo de marca o hacer clic en él sin que el carrusel se mueva. Esto mejora la experiencia del usuario.
    -   *Cuando está deshabilitado (NO):* El carrusel continuará desplazándose automáticamente incluso si el ratón está sobre él, lo que puede ser frustrante para los clientes que intentan interactuar.
-   **Valor recomendado:** `SÍ` para una mejor experiencia de usuario.
-   **Escenario / ejemplo de comerciante:** Un cliente ve una marca que le gusta y mueve el ratón para hacer clic en ella. Si el carrusel se pausa, puede hacer clic fácilmente. Si no lo hace, la marca podría desaparecer antes de que pueda reaccionar.

#### **Tamaño de la imagen de la marca**

-   **Qué hace este ajuste:** Este ajuste le permite definir el ancho máximo de las imágenes de las marcas que se muestran en el bloque. La altura se escalará proporcionalmente.
-   **Efecto de cambiar este ajuste:**
    -   *Valor más grande (por ejemplo, 150px):* Los logotipos de las marcas aparecerán más grandes, haciéndolos más prominentes y fáciles de ver. Esto podría ocupar más espacio en el bloque.
    -   *Valor más pequeño (por ejemplo, 80px):* Los logotipos de las marcas aparecerán más pequeños, permitiendo que quepan más logotipos en un espacio determinado pero potencialmente haciéndolos menos perceptibles.
-   **Valor recomendado:** 100-120 píxeles para un buen equilibrio entre visibilidad y eficiencia espacial. Ajuste según el diseño de su tema.
-   **Escenario / ejemplo de comerciante:** Si su barra lateral es estrecha, es posible que deba establecer un tamaño de imagen más pequeño (por ejemplo, 80px) para evitar que los logotipos se desborden. En un bloque de página de inicio ancho, podría usar 150px para un mayor impacto.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Posición del bloque de fabricantes | `displayHome` o `displayRightColumn` | Determina dónde aparece el bloque de marcas (por ejemplo, página de inicio, barra lateral, pie de página). |
| Configuración del módulo | Habilitar carrusel | `SÍ` | Transforma la cuadrícula estática en un carrusel deslizante para una visualización dinámica. |
| Configuración del módulo | Activar filtro de categorías | `SÍ` | Muestra solo las marcas relevantes para la categoría actual que se está viendo. |
| Configuración del módulo | Habilitar desplazamiento automático para el carrusel | `SÍ` | Hace que el carrusel se desplace automáticamente por las marcas. |
| Configuración del módulo | Velocidad de desplazamiento automático | 3000-5000ms | Controla la velocidad de desplazamiento del carrusel (en milisegundos). |
| Configuración del módulo | Pausar carrusel al pasar el ratón | `SÍ` | Detiene el desplazamiento automático cuando un cliente pasa el cursor sobre el bloque. |
| Configuración del módulo | Tamaño de la imagen de la marca | 100-120px | Establece el ancho máximo para los logotipos de las marcas en el bloque. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: Mi bloque de marcas no aparece después de la instalación, o está en el lugar equivocado.**

-   **R:** Primero, verifique la página de configuración del módulo en su Back Office. Asegúrese de que la configuración "Posición del bloque de fabricantes" esté seleccionada correctamente. Si está configurado en `displayHome`, solo aparecerá en la página de inicio. Si está configurado en una columna, asegúrese de que su tema realmente muestre esa columna en las páginas que está viendo.
-   **R:** Borre la caché de PrestaShop. Vaya a **Parámetros avanzados > Rendimiento**, luego haga clic en "Borrar caché" en la parte superior derecha. A veces, los cambios de tema o las nuevas instalaciones de módulos requieren una actualización de la caché.
-   **R:** Verifique las "Posiciones" de su tema (Diseño > Posiciones en PS 1.7/8). Asegúrese de que el módulo esté enganchado a la posición deseada. Si no aparece en la lista, intente volver a guardar la configuración del módulo.

**P2: Las imágenes de mis marcas se ven distorsionadas o no tienen el tamaño correcto.**

-   **R:** Vaya a la configuración del módulo y ajuste la configuración "Tamaño de la imagen de la marca". Esto controla el ancho máximo.
-   **R:** Asegúrese de que las imágenes originales del fabricante subidas a PrestaShop (Catálogo > Fabricantes) sean de buena calidad e idealmente tengan una relación de aspecto consistente. Aunque el módulo las escala, las imágenes de origen muy distorsionadas seguirán viéndose mal.
-   **R:** Después de cambiar el tamaño de las imágenes, a menudo es una buena idea regenerar las miniaturas. Vaya a **Diseño > Configuración de imágenes** (o **Preferencias > Imágenes** en versiones anteriores de PS) y haga clic en "Regenerar miniaturas". Seleccione "fabricantes" como tipo de imagen.

**P3: El carrusel no se desplaza, o el desplazamiento automático no funciona.**

-   **R:** Verifique si "Habilitar carrusel" está configurado en `SÍ`. Si no, será un bloque estático.
-   **R:** Si el carrusel está habilitado, verifique si "Habilitar desplazamiento automático para el carrusel" también está configurado en `SÍ`. Si esto es `NO`, el carrusel solo se moverá manualmente.
-   **R:** Si ambos están habilitados, verifique la consola de desarrollador de su navegador (F12) en busca de errores de JavaScript. Los conflictos con otros módulos o scripts de temas a veces pueden impedir que los carruseles funcionen. Intente deshabilitar temporalmente otros módulos para aislar el problema.

**P4: El "Filtro de categorías" no funciona; sigo viendo todas las marcas en las páginas de categorías.**

-   **R:** Asegúrese de que esta configuración esté establecida en `SÍ` en la configuración del módulo.
-   **R:** Verifique que sus productos estén correctamente asociados tanto a una categoría como a un fabricante en su catálogo de PrestaShop. Si un producto no está vinculado a un fabricante, o el fabricante no está vinculado a ningún producto en esa categoría, no aparecerá cuando se filtre.
-   **R:** Borre la caché de PrestaShop después de realizar cualquier cambio en las asociaciones de productos/fabricantes.

**P5: ¿Cómo traduzco el título o el texto del módulo?**

-   **R:** Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop.
-   Seleccione "Traducciones de módulos instalados", elija su tema y seleccione el idioma que desea traducir.
-   Busque el módulo "Bloque de imágenes de fabricantes (marcas)" en la lista y podrá editar cualquier cadena traducible que proporcione (por ejemplo, el título del bloque).

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura

El módulo "Bloque de imágenes de fabricantes (marcas)" (`mib`) es un módulo estándar de PrestaShop que sigue un patrón similar a MVC. Principalmente aprovecha el sistema de hooks de PrestaShop para inyectar su contenido en varias posiciones del front-office. La lógica central reside en el archivo principal `mib.php`, que gestiona la instalación, desinstalación, configuración y renderizado de contenido para los hooks. Utiliza una biblioteca JavaScript de terceros (`lightslider.js`) para la funcionalidad del carrusel y CSS personalizado para el estilo. La configuración se almacena en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores de administración de Front-Office o Back-Office personalizados. Toda la configuración se gestiona a través del método `getContent()` en el archivo principal del módulo, y la renderización del front-office se realiza directamente a través de los métodos de hook.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada o entidades `ObjectModel`. Interactúa directamente con los objetos `Manufacturer` y `Category` y `Configuration` de PrestaShop para la configuración.

### 4.4 Activos JavaScript (`views/js/`)

-   **`mib/lib/js/lightslider.js`**
    -   **Alcance:** Front-office.
    -   **Descripción:** Este es un plugin jQuery de terceros responsable de crear el carrusel de contenido responsivo. Gestiona la animación deslizante, los controles de navegación y el comportamiento responsivo para los logotipos de las marcas cuando la opción de carrusel está habilitada.
    -   **Funcionalidad clave:** Inicializa `lightSlider` en un elemento HTML especificado, gestiona las transiciones de diapositivas, los gestos táctiles/de deslizamiento y los ajustes responsivos.
-   **`mib/views/js/mib.js`**
    -   **Alcance:** Front-office.
    -   **Descripción:** Este es el archivo JavaScript personalizado del módulo. Contiene la lógica de inicialización para el plugin `lightslider.js` basada en la configuración del módulo.
    -   **Funcionalidad clave:**
        -   Verifica si el carrusel está habilitado (configuración `MIB_CAROUSEL`).
        -   Inicializa `lightSlider` en el elemento `#lightSlider` dentro de la plantilla del módulo.
        -   Pasa opciones de configuración a `lightSlider` como `auto`, `pause`, `pauseOnHover`, `item`, `slideMove`, `speed`, `loop`, `controls`, `responsive` basadas en las configuraciones `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED` y `MIB_IMG`.
        -   Asegura que el deslizador solo se inicialice si el elemento existe.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`mib/lib/css/lightslider.css`**
    -   **Alcance:** Estilo del cliente del front-office.
    -   **Descripción:** Esta es la hoja de estilo principal para el plugin `lightslider.js`. Proporciona el estilo necesario para la estructura del carrusel, las flechas de navegación y los puntos de paginación.
    -   **Selectores CSS clave:** `.lightSlider`, `.lSAction`, `.lSPager`, `.lslide`, etc. Los desarrolladores pueden anularlos para personalizar la apariencia del carrusel.
-   **`mib/mib.css`**
    -   **Alcance:** Estilo del cliente del front-office.
    -   **Descripción:** Esta es la hoja de estilo personalizada del módulo. Proporciona un estilo específico para el contenedor del bloque de marcas, las imágenes de marcas individuales y cualquier efecto de desplazamiento.
    -   **Selectores CSS clave:**
        -   `#manufacturers_block_top`, `#manufacturers_block_left`, `#manufacturers_block_right`, `#manufacturers_block_home`, `#manufacturers_block_footer`: IDs de contenedores principales para diferentes posiciones de hook.
        -   `.mib_manufacturer_item`: Estilos para enlaces/contenedores de fabricantes individuales.
        -   `.mib_manufacturer_item img`: Estilos para las imágenes de marcas, incluyendo ajustes de `max-width` y `height`.
        -   `.mib_manufacturer_item:hover img`: Define la animación al pasar el ratón (por ejemplo, `transform: scale(1.1)` para un efecto de zoom).

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   **`mib/views/templates/hook/mib.tpl`**
        -   **Enganchado a:** `displayRightColumn`, `displayFooter`, `displayTop`, `displayLeftColumn`, `displayHome`, `displayTopColumn`.
        -   **Propósito:** Esta es la plantilla principal del front-office responsable de renderizar el bloque de marcas. Genera dinámicamente la estructura HTML para una cuadrícula estática de logotipos de fabricantes o el carrusel `lightSlider`, según la configuración del módulo.
        -   **Elementos clave:**
            -   Renderizado condicional para el carrusel (`{if $mib_carousel}`).
            -   Bucle a través del array `$manufacturers` para mostrar la imagen y el enlace de cada marca.
            -   Incluye `mib.js` y `lightslider.js` si el carrusel está habilitado.
            -   Incluye `mib.css` y `lightslider.css`.
            -   Utiliza `{$link->getManufacturerLink($manufacturer.id_manufacturer, $manufacturer.link_rewrite)}` para las URL de los fabricantes.
            -   Utiliza `{$manufacturer.image}` para las rutas de las imágenes de las marcas.
-   **Plantillas de administración (`views/templates/admin/`)**:
    -   **`mib/views/templates/admin/admin.tpl`**
        -   **Propósito:** Esta plantilla renderiza el formulario de configuración del módulo en el Back Office de PrestaShop. Muestra todas las configuraciones (posición, opciones de carrusel, tamaño de imagen, etc.) como campos de entrada, cuadros de selección e interruptores.
        -   **Elementos clave:**
            -   Estructura de formulario de ayuda estándar de PrestaShop (`{include file="{$smarty.const._PS_ROOT_DIR_}/src/PrestaShopBundle/Resources/views/Admin/Configure/AdvancedParameters/Blocks/form_block_content.html.twig"}`).
            -   Campos de entrada para `MIB_WHERE`, `MIB_CAROUSEL`, `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED`, `MIB_FROM_CAT`, `MIB_IMG`.
            -   Utiliza `{$mib_form_action}` para el envío del formulario.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:
    -   Este módulo no crea ninguna tabla de base de datos personalizada.
    -   La configuración se almacena en la tabla `ps_configuration` utilizando claves como `MIB_CAROUSEL`, `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED`, `MIB_FROM_CAT`, `MIB_IMG`, `MIB_WHERE`.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento y Ubicación de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayRightColumn` | Se renderiza en la barra lateral derecha del front-office. | Muestra el bloque de marcas en la columna derecha. |
| `displayFooter` | Se renderiza en la sección del pie de página del front-office. | Muestra el bloque de marcas en el pie de página de la tienda. |
| `displayTop` | Se renderiza en la sección superior del front-office (a menudo la cabecera). | Muestra el bloque de marcas en el área de la cabecera. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración establece sus activos multimedia. | Se utiliza para incluir los archivos CSS y JS del módulo en el Back Office para la configuración. |
| `displayLeftColumn` | Se renderiza en la barra lateral izquierda del front-office. | Muestra el bloque de marcas en la columna izquierda. |
| `displayHome` | Se renderiza en la página de inicio del front-office. | Muestra el bloque de marcas de forma destacada en la página de inicio. |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página del front-office. | Se utiliza para incluir los archivos CSS y JS necesarios para la visualización del front-office. |
| `displayTopColumn` | Se renderiza en la sección de la columna superior del front-office (debajo de `displayTop`). | Muestra el bloque de marcas en el área de la columna superior. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Bloque de imágenes de fabricantes (marcas)", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.

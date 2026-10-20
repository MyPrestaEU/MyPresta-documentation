---
title: "Slider de productos vendidos recientemente - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Slider de productos vendidos recientemente' de MyPresta.eu."
sidebar:
  label: "Slider de productos vendidos recientemente - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Recently sold products slider en MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/recently-sold-products-slider.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/sliders-slideshows/recently-sold-products-slider/)
>
> ---


# Slider de productos vendidos recientemente

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una instalación de PrestaShop y son suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Slider de productos vendidos recientemente". Aquí puede personalizar la apariencia, el comportamiento y el contenido de su slider de productos.

#### **Color de fondo (rsps\_c\_bg)**

- **Qué hace este ajuste:** Controla el color de fondo de todo el bloque del slider.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un color (por ejemplo, #FFFFFF para blanco):* El fondo del slider se mostrará en ese color específico, ayudándolo a integrarse o destacarse de su tema.
  - *Cuando se deja vacío o es inválido:* El slider podría heredar estilos de fondo de su tema, o por defecto un fondo transparente.
- **Valor recomendado:** Elija un color que complemente el diseño de su tienda. A menudo, un color sutil o uno que coincida con su encabezado/pie de página es lo mejor.
- **Escenario/ejemplo de comerciante:** Si su tienda tiene un encabezado oscuro, establecer esto en un gris oscuro o negro podría hacer que el slider se vea integrado. Si desea que resalte, un color contrastante podría funcionar.

#### **Color del borde (rsps\_c\_border)**

- **Qué hace este ajuste:** Define el color del borde alrededor de todo el bloque del slider.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un color (por ejemplo, #CCCCCC para gris claro):* Aparecerá un borde de ese color alrededor del slider.
  - *Cuando se deja vacío o es inválido:* El módulo no aplicará ningún borde explícito, aunque su tema aún podría añadir uno.
- **Valor recomendado:** A menudo, un borde sutil que coincida con otros bordes de su tema o un borde transparente es lo mejor.
- **Escenario/ejemplo de comerciante:** Si su sitio utiliza bordes grises delgados para otros elementos, establecer esto en el mismo gris mantendrá la coherencia.

#### **Color de la fuente (rsps\_c\_font)**

- **Qué hace este ajuste:** Establece el color del texto (nombres de productos) que se muestra dentro del slider.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un color (por ejemplo, #333333 para gris oscuro):* Los nombres de los productos aparecerán en el color elegido.
  - *Cuando se deja vacío o es inválido:* El color del texto podría por defecto ser el color de fuente general de su tema.
- **Valor recomendado:** Elija un color que proporcione un buen contraste con el color de fondo del slider para facilitar la lectura.
- **Escenario/ejemplo de comerciante:** Si el fondo de su slider es oscuro, un color de fuente claro (como blanco o gris claro) será necesario para la legibilidad.

#### **Relleno del slider (rsps\_s\_padding)**

- **Qué hace este ajuste:** Controla el espaciado interno (relleno) entre el contenido (texto) y los bordes del bloque del slider.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un valor (por ejemplo, "10px"):* El texto tendrá 10 píxeles de espacio en todos los lados desde el borde del slider.
  - *Cuando se establece en "0px" o vacío:* El texto se colocará directamente contra los bordes del slider.
- **Valor recomendado:** "5px" o "10px" para dar al texto algo de espacio y mejorar la estética.
- **Escenario/ejemplo de comerciante:** Si su texto se ve demasiado apretado, aumentar el relleno añadirá más espacio a su alrededor, haciéndolo lucir más limpio.

#### **Tamaño de fuente del slider (rsps\_s\_font)**

- **Qué hace este ajuste:** Determina el tamaño de la fuente utilizada para los nombres de los productos en el slider.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un valor (por ejemplo, "14px"):* El texto se mostrará en ese tamaño de píxel específico.
  - *Cuando se deja vacío o es inválido:* El tamaño de la fuente podría por defecto ser el tamaño de fuente general de su tema.
- **Valor recomendado:** "14px" o "16px" para una buena legibilidad sin ser demasiado grande o demasiado pequeño.
- **Escenario/ejemplo de comerciante:** Si el slider está en una ubicación prominente como el encabezado, una fuente ligeramente más grande podría ser apropiada. Para una barra lateral, una fuente más pequeña podría encajar mejor.

#### **Borde del slider (rsps\_s\_border)**

- **Qué hace este ajuste:** Define el grosor y el estilo del borde alrededor del *contenido interno* del slider (el área de texto desplazable en sí), distinto del borde del bloque general.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un valor (por ejemplo, "1px solid #CCCCCC"):* Aparecerá un borde sólido de 1 píxel de color gris claro alrededor del texto desplazable.
  - *Cuando se deja vacío o es inválido:* No se aplicará ningún borde interno explícito.
- **Valor recomendado:** "0px" o "none" si solo desea el borde del bloque exterior. Si desea una separación sutil, "1px solid #EEEEEE" puede funcionar.
- **Escenario/ejemplo de comerciante:** Podría usar esto para crear un cuadro visual distinto para el texto desplazable dentro del área más grande del slider.

#### **Dirección del movimiento (rsps\_m\_dir)**

- **Qué hace este ajuste:** Controla la dirección en la que se desplazan los nombres de los productos dentro del slider.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "left":* El texto se desplazará de derecha a izquierda.
  - *Cuando se establece en "right":* El texto se desplazará de izquierda a derecha.
- **Valor recomendado:** "left" es una dirección de lectura común y natural para el texto desplazable.
- **Escenario/ejemplo de comerciante:** La mayoría de los usuarios están acostumbrados al texto que se desplaza hacia la izquierda, por lo que ceñirse a "left" a menudo proporciona la mejor experiencia de usuario.

#### **Retraso del movimiento (rsps\_m\_delay)**

- **Qué hace este ajuste:** Determina la velocidad de la animación de desplazamiento. Esto se mide típicamente en milisegundos.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un valor más bajo (por ejemplo, "50"):* El texto se desplazará más rápido.
  - *Cuando se establece un valor más alto (por ejemplo, "100"):* El texto se desplazará más lento.
- **Valor recomendado:** "70" a "100" proporciona una velocidad suave y legible sin ser demasiado rápida o demasiado lenta.
- **Escenario/ejemplo de comerciante:** Si el texto es demasiado rápido, los clientes no pueden leerlo. Si es demasiado lento, podría no llamar la atención. Experimente para encontrar un equilibrio.

#### **Posición del slider (rsps\_position)**

- **Qué hace este ajuste:** Le permite seleccionar el hook de PrestaShop donde se mostrará el slider en su tienda.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en `displayHome`:* El slider aparecerá en la página de inicio de su tienda.
  - *Cuando se establece en `displayHeader`:* El slider aparecerá en la sección del encabezado de todas las páginas.
  - *Cuando se establece en `displayFooter`:* El slider aparecerá en la sección del pie de página de todas las páginas.
  - *Otras opciones (por ejemplo, `displayLeftColumn`, `displayRightColumn`, `displayTop`):* El slider aparecerá en la columna o sección superior respectiva.
- **Valor recomendado:** `displayHeader` o `displayHome` para máxima visibilidad, o `displayFooter` para un enfoque más sutil.
- **Escenario/ejemplo de comerciante:** Si desea que cada visitante vea las ventas recientes inmediatamente, elija `displayHeader`. Si desea que sea parte del contenido de su página de inicio, elija `displayHome`.

#### **Número de productos (rsps\_nb)**

- **Qué hace este ajuste:** Especifica cuántos productos vendidos recientemente deben recuperarse y mostrarse en el slider.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un número más bajo (por ejemplo, "5"):* Solo se mostrarán las 5 ventas más recientes.
  - *Cuando se establece un número más alto (por ejemplo, "20"):* Se incluirán hasta 20 ventas recientes en la lista de desplazamiento.
- **Valor recomendado:** "10" a "15" para asegurar una buena variedad de productos sin hacer la lista excesivamente larga.
- **Escenario/ejemplo de comerciante:** Si su tienda tiene muchas ventas, un número más alto proporciona más prueba social. Si las ventas son menos frecuentes, un número más bajo podría ser suficiente.

#### **Ordenar por (rsps\_order)**

- **Qué hace este ajuste:** Determina los criterios de clasificación para los productos mostrados en el slider.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "date\_add":* Los productos se ordenarán por la fecha en que se agregaron al pedido (los más recientes primero).
  - *Cuando se establece en "product\_name":* Los productos se ordenarán alfabéticamente por nombre.
  - *Cuando se establece en "price":* Los productos se ordenarán por precio.
- **Valor recomendado:** "date\_add" para mostrar realmente los artículos "vendidos recientemente".
- **Escenario/ejemplo de comerciante:** Para reflejar con precisión las compras recientes, ordenar por `date_add` es la opción más lógica.

#### **Diversidad (rsps\_diversity)**

- **Qué hace este ajuste:** Este ajuste controla si el slider debe mostrar productos únicos o permitir que el mismo producto aparezca varias veces si se vendió recientemente.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (por ejemplo, "Sí" o "1"):* Si el mismo producto se vendió varias veces, solo aparecerá una vez en la lista de productos a mostrar, asegurando una mayor variedad de artículos.
  - *Cuando está deshabilitado (por ejemplo, "No" o "0"):* El mismo producto podría aparecer varias veces en el slider si formó parte de varios pedidos recientes.
- **Valor recomendado:** "Sí" (o "1") para mostrar una gama más amplia de su catálogo y evitar que el slider se vuelva repetitivo.
- **Escenario/ejemplo de comerciante:** Si vende un artículo muy popular, deshabilitar la diversidad podría significar que el slider solo muestre ese artículo repetidamente. Habilitarlo asegura que otros productos tengan la oportunidad de ser vistos.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | **Color de fondo** (rsps\_c\_bg) | `#FFFFFF` (Blanco) | Establece el color de fondo del bloque del slider. |
| Configuración del módulo | **Color del borde** (rsps\_c\_border) | `#CCCCCC` (Gris claro) | Establece el color del borde alrededor del bloque del slider. |
| Configuración del módulo | **Color de la fuente** (rsps\_c\_font) | `#333333` (Gris oscuro) | Establece el color del texto de los nombres de los productos. |
| Configuración del módulo | **Relleno del slider** (rsps\_s\_padding) | `10px` | Espaciado interno alrededor del texto dentro del slider. |
| Configuración del módulo | **Tamaño de fuente del slider** (rsps\_s\_font) | `14px` | Tamaño de la fuente para los nombres de los productos. |
| Configuración del módulo | **Borde del slider** (rsps\_s\_border) | `0px` | Borde alrededor del área de texto desplazable en sí. |
| Configuración del módulo | **Dirección del movimiento** (rsps\_m\_dir) | `left` | Dirección de la animación de desplazamiento (izquierda o derecha). |
| Configuración del módulo | **Retraso del movimiento** (rsps\_m\_delay) | `70` | Velocidad de la animación de desplazamiento (menor = más rápido). |
| Configuración del módulo | **Posición del slider** (rsps\_position) | `displayHeader` | Hook de PrestaShop donde se mostrará el slider. |
| Configuración del módulo | **Número de productos** (rsps\_nb) | `10` | Número máximo de productos vendidos recientemente a mostrar. |
| Configuración del módulo | **Ordenar por** (rsps\_order) | `date_add` | Criterios de clasificación para los productos mostrados. |
| Configuración del módulo | **Diversidad** (rsps\_diversity) | `Sí` (1) | Asegura que se muestren productos únicos (evita la repetición). |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He configurado el módulo, pero el slider no aparece en mi tienda.**
**R1:**

-   **Verificar la posición del hook:** Vaya a **Diseño > Posiciones** en su Back Office de PrestaShop. Busque el hook que seleccionó en la configuración de "Posición del slider" del módulo (por ejemplo, `displayHeader`, `displayHome`). Asegúrese de que el módulo "Slider de productos vendidos recientemente" esté listado y habilitado en ese hook. Si no, es posible que deba "Trasplantar un módulo" al hook correcto.
-   **Borrar caché:** PrestaShop a menudo almacena contenido en caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la parte superior derecha.
-   **Módulo habilitado:** Verifique que el módulo esté habilitado en **Módulos > Gestor de módulos**.
-   **Ventas recientes:** Asegúrese de tener ventas recientes en su tienda. El módulo se basa en datos de pedidos existentes.

**P2: El slider se muestra, pero los colores o tamaños de fuente no son los que configuré.**
**R2:**

-   **Borrar caché:** Esta es la razón más común de los problemas de estilo. Borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento**) y la caché de su navegador (Ctrl+F5 o Cmd+R).
-   **Sobrescrituras del tema:** Su tema de PrestaShop podría tener su propio CSS que está sobrescribiendo los estilos del módulo. Es posible que deba inspeccionar el elemento usando las herramientas de desarrollador de su navegador (F12) para ver qué reglas CSS se están aplicando. Si es un conflicto de tema, es posible que deba agregar CSS personalizado a su tema para forzar los estilos del módulo.
-   **Entrada correcta:** Asegúrese de que está utilizando códigos de color CSS válidos (por ejemplo, `#RRGGBB` o `rgba(R,G,B,A)`) y valores de píxeles (por ejemplo, `14px`) en la configuración del módulo.

**P3: El texto se desplaza demasiado rápido/lento, o es difícil de leer.**
**R3:**

-   **Retraso del movimiento:** Ajuste la configuración de "Retraso del movimiento". Un número más alto lo hace más lento, un número más bajo lo hace más rápido. Experimente hasta encontrar una velocidad de lectura cómoda.
-   **Tamaño de fuente y contraste:** Asegúrese de que su "Tamaño de fuente del slider" sea adecuado y que su "Color de fuente" tenga un buen contraste con su "Color de fondo".
-   **Número de productos:** Si tiene demasiados productos y una velocidad muy rápida, podría ser abrumador. Reduzca el "Número de productos" o disminuya el "Retraso del movimiento".

**P4: ¿Puedo traducir el texto "Alguien acaba de comprar..." a otros idiomas?**
**R4:** Sí, los módulos de PrestaShop suelen ser traducibles.

-   Vaya a **Internacional > Traducciones** en su Back Office.
-   Seleccione "Traducciones de módulos instalados" para el "Tipo de traducción".
-   Elija su tema.
-   Seleccione el idioma que desea traducir.
-   Busque el módulo "Slider de productos vendidos recientemente" en la lista y debería poder editar las cadenas traducibles.

**P5: El slider se ve bien en el escritorio, pero está roto o mal formateado en el móvil.**
**R5:**

-   **Borrar caché:** Siempre comience borrando la caché de PrestaShop y del navegador.
-   **Capacidad de respuesta del tema:** Si bien el módulo en sí está diseñado para ser responsivo, pueden ocurrir conflictos con el CSS responsivo específico de su tema.
-   **Verificar relleno/bordes:** Un relleno o bordes excesivos podrían empujar el contenido fuera de la vista en pantallas más pequeñas. Intente reducir temporalmente el "Relleno del slider" o el "Borde del slider" para ver si resuelve el problema.
-   **Inspeccionar en el móvil:** Use las herramientas de desarrollador de su navegador (F12) y cambie a la vista móvil, o pruebe directamente en un dispositivo móvil, para diagnosticar problemas de diseño específicos. Es posible que se necesite CSS personalizado en su tema para ajustarse a los dispositivos móviles si existe un conflicto.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada del módulo "Slider de productos vendidos recientemente" para desarrolladores, webmasters y agencias técnicas.

### 4.1 Descripción general de la arquitectura

El módulo "Slider de productos vendidos recientemente" (`recentlysoldproducts`) sigue una arquitectura de módulo estándar de PrestaShop. Es un módulo de un solo archivo (`recentlysoldproducts.php`) que extiende `Module`, manejando su propia instalación, desinstalación, configuración (`getContent()`) y visualización en el front-office a través de hooks. Aprovecha la clase `Configuration` de PrestaShop para el almacenamiento de configuraciones y Smarty para las plantillas. La funcionalidad del front-office se basa principalmente en JavaScript para la animación de desplazamiento y el estilo.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador de administración de Front-Office o Back-Office dedicado. Toda la configuración se maneja dentro del método `getContent()` del archivo principal del módulo, y la renderización del front-office se gestiona directamente a través de los hooks de PrestaShop.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** contiene ninguna clase personalizada o definiciones de `ObjectModel` en un directorio `classes/`. Consulta directamente la base de datos de PrestaShop para obtener información de pedidos y productos dentro del archivo principal del módulo.

### 4.4 Activos de JavaScript (`views/js/`)

-   **`recentlysoldproducts/jscolor/jscolor.js`**

    -   **Alcance:** Back-office (utilizado en `getContent()` para selectores de color).
    -   **Descripción:** Esta es una biblioteca JavaScript de terceros que proporciona una interfaz de selector de color fácil de usar para los campos de entrada. Está integrada en el formulario de configuración del módulo para permitir a los comerciantes seleccionar fácilmente los colores para el fondo, el borde y la fuente del slider. Normalmente funciona añadiendo una clase (por ejemplo, `jscolor`) a un campo de entrada, que luego lo transforma en un selector de color.
-   **`recentlysoldproducts/js/script.js`**

    -   **Alcance:** Front-office.
    -   **Descripción:** Este archivo probablemente contiene la lógica central para la animación de desplazamiento del slider. Típicamente:
        -   Selecciona el elemento contenedor del slider (por ejemplo, por ID o clase).
        -   Inicializa variables para la dirección del movimiento, la velocidad y el contenido.
        -   Implementa un bucle de animación de desplazamiento continuo, potencialmente usando `setInterval` o `requestAnimationFrame`.
        -   Maneja la clonación de elementos para crear un efecto de bucle infinito.
        -   Se ajusta a la capacidad de respuesta o pausas al pasar el ratón.
-   **`recentlysoldproducts/recentlysoldproducts.js`**

    -   **Alcance:** Front-office.
    -   **Descripción:** Este archivo podría contener JavaScript adicional del front-office específico para la inicialización o interacción del módulo. Podría ser responsable de:
        -   Cargar el contenido del slider dinámicamente (aunque en este módulo, es probable que sea renderizado por Smarty).
        -   Configurar escuchadores de eventos (por ejemplo, para pausar el slider al pasar el ratón).
        -   Asegurarse de que el slider se inicialice correctamente después de que el DOM esté listo.
        -   Potencialmente manejar AJAX si el módulo fuera a buscar datos de forma asíncrona (aunque no está explícitamente indicado por la estructura del módulo).

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`recentlysoldproducts/css.css`**

    -   **Alcance:** Front-office.
    -   **Descripción:** Esta es probablemente la hoja de estilo principal para la visualización del slider en el front-office. Definiría:
        -   Diseño y posicionamiento del contenedor del slider.
        -   Estilos básicos para los elementos de texto desplazables (por ejemplo, `font-size`, `color`, `padding`).
        -   Estilos para el fondo y los bordes basados en la configuración del módulo.
        -   Potencialmente ajustes responsivos para diferentes tamaños de pantalla.
        -   Selectores clave: `.recentlysoldproducts_block`, `.recentlysoldproducts_item`, etc.
-   **`recentlysoldproducts/recentlysoldproducts.css`**

    -   **Alcance:** Front-office.
    -   **Descripción:** Este archivo podría contener reglas de estilo adicionales o específicas, potencialmente para efectos visuales más avanzados o para anular los estilos predeterminados del tema. Dado el nombre, también podría ser un archivo redundante o heredado, o contener estilos más específicos para el mecanismo de desplazamiento en sí, distintos del estilo general del bloque en `css.css`. Los desarrolladores deben verificar las reglas superpuestas y los posibles conflictos.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **`recentlysoldproducts/views/front/rsps.tpl`**
    -   **Alcance:** Front-office (plantilla de hook).
    -   **Descripción:** Este es el archivo de plantilla principal responsable de renderizar la estructura HTML del slider de productos vendidos recientemente.
    -   **Renderizado en hooks:** `rightColumn`, `displayrightColumn`, `home`, `top`, `displayleftColumn`, `footer`, `displayhome`, `displayheader`, `displaytop`, `displayfooter`, `header`, `leftColumn`.
    -   **Contenido:** Recibe datos (por ejemplo, una lista de productos vendidos recientemente, configuraciones del módulo) de los métodos `hookDisplay*` en `recentlysoldproducts.php`. Luego itera a través de la lista de productos para generar el texto desplazable, aplicando estilos o clases en línea basados en la configuración del módulo (colores, tamaños de fuente, relleno, etc.). Contendrá el contenedor HTML principal para el slider y las entradas de productos individuales.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   Este módulo no crea ninguna tabla de base de datos personalizada.
    -   Almacena sus configuraciones en la tabla `ps_configuration` de PrestaShop. Las claves utilizadas son:
        -   `RSPS_C_BG`
        -   `RSPS_C_BORDER`
        -   `RSPS_C_FONT`
        -   `RSPS_S_PADDING`
        -   `RSPS_S_FONT`
        -   `RSPS_S_BORDER`
        -   `RSPS_M_DIR`
        -   `RSPS_M_DELAY`
        -   `RSPS_POSITION`
        -   `RSPS_NB`
        -   `RSPS_ORDER`
        -   `RSPS_DIVERSITY`
    -   Consulta las tablas existentes de PrestaShop, principalmente `ps_orders`, `ps_order_detail`, `ps_product_lang` y `ps_product` para recuperar información de productos vendidos recientemente.
-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento y ubicación de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Registra activos CSS/JS y potencialmente renderiza un elemento oculto para la inicialización de JS. |
| `header` | Alias para `displayHeader` en versiones anteriores de PrestaShop. | Igual que `displayHeader`. |
| `displayHome` | En la página de inicio, generalmente en el área de contenido principal. | Renderiza el bloque del slider en la página de inicio de la tienda. |
| `home` | Alias para `displayHome` en versiones anteriores de PrestaShop. | Igual que `displayHome`. |
| `displayTop` | En la sección superior de la página, a menudo debajo del encabezado. | Renderiza el bloque del slider en el área de contenido superior. |
| `top` | Alias para `displayTop` en versiones anteriores de PrestaShop. | Igual que `displayTop`. |
| `displayLeftColumn` | En la barra lateral izquierda de las páginas aplicables. | Renderiza el bloque del slider en la columna izquierda. |
| `leftColumn` | Alias para `displayLeftColumn` en versiones anteriores de PrestaShop. | Igual que `displayLeftColumn`. |
| `displayRightColumn` | En la barra lateral derecha de las páginas aplicables. | Renderiza el bloque del slider en la columna derecha. |
| `rightColumn` | Alias para `displayRightColumn` en versiones anteriores de PrestaShop. | Igual que `displayRightColumn`. |
| `displayFooter` | En la sección del pie de página de cada página. | Renderiza el bloque del slider en el pie de página. |
| `footer` | Alias para `displayFooter` en versiones anteriores de PrestaShop. | Igual que `displayFooter`. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Slider de productos vendidos recientemente", consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.

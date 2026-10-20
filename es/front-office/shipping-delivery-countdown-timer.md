---
title: "Temporizador de cuenta regresiva para envío - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Temporizador de cuenta regresiva para envío' de MyPresta.eu."
sidebar:
  label: "Temporizador de cuenta regresiva para envío - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Shipping delivery countdown timer en MyPresta.eu](https://mypresta.eu/modules/front-office-features/shipping-delivery-countdown-timer.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/shipping-delivery-countdown-timer/)
>
> ---


# Temporizador de cuenta regresiva para envío

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde controla todos los aspectos del temporizador de cuenta regresiva para envío.

#### Configuración general

- **Activado / Desactivado (Interruptor)**
  - **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar todo el módulo en su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El temporizador de cuenta regresiva aparecerá en su front office según sus otras configuraciones.
    - *Cuando está desactivado:* El temporizador de cuenta regresiva no será visible en ninguna parte de su tienda.
  - **Valor recomendado:** **Activado** (una vez que lo haya configurado).
  - **Escenario / ejemplo de comerciante:** Está configurando el módulo por primera vez y quiere configurarlo completamente antes de ponerlo en marcha. Lo mantendría "Desactivado" hasta que esté listo, luego lo cambiaría a "Activado".

#### Visualización y diseño

- **¿Dónde desea mostrar el temporizador? (Casillas de verificación)**

  - **Qué hace este ajuste:** Esto determina las ubicaciones específicas (hooks) en su tema de PrestaShop donde se mostrará el temporizador de cuenta regresiva.
  - **Efecto de cambiar este ajuste:**
    - *Marcar una casilla (por ejemplo, `displayProductAdditionalInfo`):* El temporizador aparecerá en esa área específica de su tema.
    - *Desmarcar una casilla:* El temporizador se eliminará de esa área específica.
  - **Valor recomendado:** Comience con `displayProductAdditionalInfo` o `displayFooterProduct` para la visibilidad en la página del producto. Puede experimentar con otros como `displayNav1` o `displayReassurance` según su tema y el impacto deseado.
  - **Escenario / ejemplo de comerciante:** Quiere que el temporizador sea muy visible en las páginas de productos. Marcaría `displayProductAdditionalInfo` y `displayFooterProduct`. Si también lo quiere en la cabecera, podría marcar `displayNav1`.
  - **Opciones disponibles:**
    - `displayFooterProduct`
    - `displayReassurance`
    - `displayDeliveryTimer` (Hook personalizado para integración avanzada del tema)
    - `displayProductAdditionalInfo`
    - `displayNav1`
- **¿Qué diseño del módulo desea usar? (Botones de radio)**

  - **Qué hace este ajuste:** Le permite seleccionar un estilo visual prediseñado para su temporizador de cuenta regresiva. Esto incluye esquemas de color y diseño general.
  - **Efecto de cambiar este ajuste:** La apariencia del temporizador de cuenta regresiva en su front office cambiará instantáneamente al diseño seleccionado.
  - **Valor recomendado:** Elija el diseño que mejor se adapte a la marca de su tienda y a los colores de su tema.
  - **Escenario / ejemplo de comerciante:** Su tienda utiliza mucho azul y blanco. Podría seleccionar "Azul 400x48" o "Azul 200x100" para asegurarse de que el temporizador se integre perfectamente con la estética de su sitio.

#### Plazos de envío

- **Hora límite de compra (Selector de hora)**
  - **Qué hace este ajuste:** Esta es la hora límite diaria en la que se debe realizar un pedido para calificar para el envío del día actual.
  - **Efecto de cambiar este ajuste:**
    - *Configurar a las 14:00:* Si un cliente realiza un pedido antes de las 2 PM, el temporizador cuenta regresivamente hasta las 2 PM. Si realiza un pedido después de las 2 PM, el temporizador mostrará la cuenta regresiva hasta la hora límite del siguiente día de envío disponible.
  - **Valor recomendado:** Establezca esto a su hora límite de envío diaria real (por ejemplo, 15:00 para las 3 PM).
  - **Escenario / ejemplo de comerciante:** Su equipo de almacén procesa todos los pedidos recibidos antes de las 4 PM para su envío el mismo día. Establecería esto en `16:00`.

#### Mensajes diarios y disponibilidad

- **Mostrar el domingo / lunes / martes / miércoles / jueves / viernes / sábado (Casillas de verificación)**

  - **Qué hace este ajuste:** Estas casillas de verificación controlan si el temporizador de cuenta regresiva está activo y se muestra en días específicos de la semana.
  - **Efecto de cambiar este ajuste:**
    - *Marcar un día (por ejemplo, "Mostrar el domingo"):* El temporizador estará activo y se mostrará los domingos.
    - *Desmarcar un día:* El temporizador no se mostrará en ese día específico, y el mensaje para ese día no se mostrará.
  - **Valor recomendado:** Marque todos los días en los que realmente realiza envíos. Si no realiza envíos los fines de semana, desmarque sábado y domingo.
  - **Escenario / ejemplo de comerciante:** Su negocio opera de lunes a viernes. Marcaría de lunes a viernes y desmarcaría sábado y domingo.
- **Mensaje (Entrada de texto para cada día: domingo, lunes, martes, miércoles, jueves, viernes, sábado)**

  - **Qué hace este ajuste:** Le permite personalizar el mensaje que se muestra junto al temporizador de cuenta regresiva para cada día de la semana. Puede usar marcadores de posición para contenido dinámico.
  - **Efecto de cambiar este ajuste:** El texto que se muestra al cliente cambiará según su entrada para ese día específico.
  - **Valor recomendado:** Elabore mensajes claros y concisos. Use marcadores de posición como `{time}` para el tiempo restante y `{date}` para la fecha de entrega estimada.
  - **Escenario / ejemplo de comerciante:**
    - *Mensaje del lunes:* "¡Pida en las próximas {time} para recibir el martes!"
    - *Mensaje del sábado (si no hay envío):* "Los pedidos realizados el sábado se enviarán el lunes."

#### Exclusiones/Inclusiones de productos y categorías

- **Mostrar solo para productos en stock (Interruptor)**

  - **Qué hace este ajuste:** Controla si el temporizador de cuenta regresiva se muestra solo para productos que actualmente están en stock.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El temporizador solo aparecerá en las páginas de productos donde el producto tenga stock disponible.
    - *Cuando está desactivado:* El temporizador aparecerá independientemente del estado del stock (aunque podría ser confuso para artículos agotados).
  - **Valor recomendado:** **Activado**. Tiene poco sentido mostrar una cuenta regresiva de envío para un artículo que no se puede enviar de inmediato.
  - **Escenario / ejemplo de comerciante:** Quiere evitar prometer envío rápido para artículos que no tiene. Habilitar esto asegura que el temporizador solo se muestre para productos disponibles.
- **Excluir módulo de productos seleccionados / Visibilidad del módulo para productos seleccionados (Botones de radio)**

  - **Qué hace este ajuste:** Esta es una configuración crucial para definir si las siguientes selecciones de productos/categorías/fabricantes son para *excluir* el módulo o *incluirlo* (haciéndolo visible solo para esos elementos seleccionados).
  - **Efecto de cambiar este ajuste:**
    - *Excluir módulo de productos seleccionados:* El temporizador se mostrará en todas partes *excepto* para los elementos que seleccione a continuación.
    - *Visibilidad del módulo para productos seleccionados:* El temporizador *solo* se mostrará para los elementos que seleccione a continuación, y en ningún otro lugar.
  - **Valor recomendado:** Depende de su estrategia. Si tiene algunos productos específicos que no pueden usar el temporizador, elija "Excluir". Si solo quiere el temporizador en unos pocos productos seleccionados, elija "Visibilidad del módulo".
  - **Escenario / ejemplo de comerciante:**
    - *Excluir:* Vende principalmente artículos pequeños con envío rápido, pero también algunas piezas de mobiliario grandes que tardan más. Elegiría "Excluir" y luego seleccionaría los productos de mobiliario.
    - *Visibilidad:* Está realizando una promoción especial en una categoría específica de productos y solo quiere que el temporizador aparezca allí. Elegiría "Visibilidad del módulo" y seleccionaría esa categoría.
- **Exclusiones/Inclusiones de productos (Buscar y seleccionar)**

  - **Qué hace este ajuste:** Le permite buscar y seleccionar productos específicos para excluir el temporizador o hacer que el temporizador sea visible solo para ellos (según la configuración "Excluir módulo de productos seleccionados" anterior).
  - **Efecto de cambiar este ajuste:** Añade o elimina productos específicos de la lista de exclusión/inclusión.
  - **Valor recomendado:** Utilice esto para un control preciso sobre productos individuales.
  - **Escenario / ejemplo de comerciante:** Tiene un nuevo producto que está en pre-pedido y no se enviará en semanas. Lo añadiría a la lista de exclusión para evitar que se muestre la cuenta regresiva.
- **Exclusiones/Inclusiones de categorías (Buscar y seleccionar)**

  - **Qué hace este ajuste:** Similar a las exclusiones de productos, pero se aplica a categorías enteras.
  - **Efecto de cambiar este ajuste:** Añade o elimina categorías enteras de la lista de exclusión/inclusión.
  - **Valor recomendado:** Útil para aplicar reglas a grandes grupos de productos.
  - **Escenario / ejemplo de comerciante:** Todos los productos de su categoría "Hecho a medida" tienen largos plazos de entrega. Añadiría esta categoría a la lista de exclusión.
- **Exclusiones/Inclusiones de fabricantes (Buscar y seleccionar)**

  - **Qué hace este ajuste:** Similar a las exclusiones de productos/categorías, pero se aplica a productos de fabricantes específicos.
  - **Efecto de cambiar este ajuste:** Añade o elimina fabricantes de la lista de exclusión/inclusión.
  - **Valor recomendado:** Útil si ciertas marcas tienen diferentes políticas de envío.
  - **Escenario / ejemplo de comerciante:** Uno de sus proveedores es conocido por envíos más lentos. Añadiría su fabricante a la lista de exclusión.

#### Otros ajustes

- **mypresta\_updates, update\_, updatev\_ (Configuración interna)**
  - **Qué hace este ajuste:** Son configuraciones internas utilizadas por los módulos de MyPresta.eu para comprobaciones de actualizaciones y gestión de versiones. No están destinadas a la interacción directa del comerciante.
  - **Efecto de cambiar este ajuste:** Cambiarlos podría interferir con la capacidad del módulo para buscar actualizaciones.
  - **Valor recomendado:** Déjelos como están.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Activado | Activado | Interruptor maestro para la funcionalidad del módulo. |
| Configuración del módulo | Hora límite de compra | Su hora límite de envío diaria | Define la hora diaria en que se debe realizar un pedido para el envío del día actual. |
| Configuración del módulo | ¿Dónde desea mostrar el temporizador? | `displayProductAdditionalInfo`, `displayFooterProduct` | Selecciona las ubicaciones del tema para el temporizador. |
| Configuración del módulo | ¿Qué diseño del módulo desea usar? | Coincide con su tema | Estilo visual del temporizador de cuenta regresiva. |
| Configuración del módulo | Mostrar el domingo/lunes/…/sábado | Marcar todos los días de envío | Controla en qué días el temporizador está activo. |
| Configuración del módulo | Mensaje (para cada día) | "¡Pida en las próximas {time} para recibir antes de {date}!" | Texto personalizable que se muestra con el temporizador. |
| Configuración del módulo | Mostrar solo para productos en stock | Activado | El temporizador solo aparece para productos con stock disponible. |
| Configuración del módulo | Excluir módulo de productos seleccionados / Visibilidad del módulo para productos seleccionados | Depende de la estrategia | Define si las selecciones son para exclusión o inclusión. |
| Configuración del módulo | Exclusiones/Inclusiones de productos | Vacío | Seleccione productos específicos para incluir/excluir. |
| Configuración del módulo | Exclusiones/Inclusiones de categorías | Vacío | Seleccione categorías específicas para incluir/excluir. |
| Configuración del módulo | Exclusiones/Inclusiones de fabricantes | Vacío | Seleccione fabricantes específicos para incluir/excluir. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: El temporizador no aparece en mi tienda o aparece en el lugar equivocado.**
R1:

-   **Verifique el estado del módulo:** Primero, asegúrese de que el módulo esté "Activado" en la página de configuración.
-   **Verifique la selección de hooks:** Verifique que haya seleccionado las casillas de verificación correctas en "¿Dónde desea mostrar el temporizador?". Si su tema está muy personalizado, es posible que algunos hooks estándar no se rendericen, o que necesite usar un hook diferente.
-   **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, PrestaShop almacena en caché las posiciones de módulos antiguas.
-   **Compatibilidad del tema:** Si su tema es muy personalizado, es posible que no implemente los hooks estándar de PrestaShop de la manera habitual. Es posible que deba consultar a su desarrollador de temas o a un webmaster para insertar manualmente el hook `displayDeliveryTimer` en los archivos `.tpl` de su tema.

**P2: El mensaje de cuenta regresiva es incorrecto o la hora límite parece errónea.**
R2:

-   **Verifique la "Hora límite de compra":** Vuelva a verificar que la "Hora límite de compra" esté configurada correctamente a su hora límite de envío diaria.
-   **Verifique los mensajes diarios:** Asegúrese de que el "Mensaje" para el día actual de la semana esté configurado correctamente y tenga sentido.
-   **Zona horaria del servidor:** Asegúrese de que la zona horaria del servidor de su tienda PrestaShop esté configurada correctamente. Si la hora del servidor es incorrecta, la cuenta regresiva será inexacta. Puede verificar esto en **Parámetros avanzados > Información de configuración** o con su proveedor de alojamiento.

**P3: El temporizador se muestra para productos agotados.**
R3:

-   **Configuración "Mostrar solo para productos en stock":** Asegúrese de que el interruptor "Mostrar solo para productos en stock" esté configurado en **Activado** en la configuración del módulo. Si está desactivado, el temporizador aparecerá independientemente del estado del stock.

**P4: Quiero cambiar los colores o las fuentes del temporizador más allá de los diseños preestablecidos.**
R4:

-   El módulo proporciona varios diseños predefinidos. Para una personalización más profunda (por ejemplo, fuentes específicas, códigos de color exactos no disponibles en los diseños), necesitará un webmaster o desarrollador. Pueden anular los estilos CSS del módulo añadiendo CSS personalizado a la hoja de estilos de su tema. Consulte la Sección 7.5 para obtener detalles sobre el archivo CSS.

**P5: El temporizador no se traduce a otros idiomas.**
R5:

-   Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop.
-   Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Temporizador de cuenta regresiva para envío" en el menú desplegable del módulo.
-   Luego podrá traducir todos los mensajes diarios y otras cadenas del módulo a los idiomas deseados.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo `Shipping delivery countdown timer` (`deliverycountdown`) es un módulo estándar de PrestaShop que sigue un patrón similar a MVC dentro del alcance del módulo. Principalmente extiende `Module` y aprovecha el sistema de hooks de PrestaShop para inyectar su contenido y funcionalidad en el front office. La configuración se gestiona a través del método `getContent()`, almacenando los ajustes en `ps_configuration`. La visualización en el front office se basa en plantillas Smarty y un archivo JavaScript dedicado para la lógica de la cuenta regresiva.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores personalizados de front office o back office. Toda la configuración se gestiona dentro del método `getContent()` del archivo principal del módulo. La renderización del front office se logra directamente a través de hooks y plantillas asociadas.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada ni `ObjectModel` en el directorio `classes/`. Todos los datos se almacenan directamente en `ps_configuration` utilizando claves de configuración.

### 4.4 Activos JavaScript (`views/js/`)

-   **`deliverycountdown/views/js/deliverycountdown.js`**
    -   **Alcance:** Front office.
    -   **Responsabilidad:** Este es el archivo JavaScript principal responsable de la lógica de la cuenta regresiva.
    -   **Detalles:**
        -   Probablemente inicializa un temporizador de cuenta regresiva en elementos identificados por clases CSS o IDs específicos.
        -   Calcula el tiempo restante hasta la "Hora límite de compra" para el día actual o el siguiente día de envío disponible.
        -   Actualiza dinámicamente el tiempo mostrado (horas, minutos, segundos) en la plantilla del front office.
        -   Gestiona la transición de mensajes cuando se alcanza la hora límite (por ejemplo, cambiando de "Pida en X tiempo" a "Los pedidos realizados ahora se enviarán mañana").
        -   Puede usar `setInterval` o `setTimeout` para actualizaciones en tiempo real.
        -   Probablemente lee los valores de configuración (como la hora límite, los mensajes diarios y los días habilitados) pasados desde la plantilla Smarty o JavaScript en línea.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo incluye un archivo CSS base y varios archivos CSS específicos del tema para diferentes diseños visuales.

-   **`deliverycountdown/views/css/deliverycountdown.css`**

    -   **Alcance:** Front office.
    -   **Responsabilidad:** Contiene el estilo estructural fundamental y predeterminado para el temporizador de cuenta regresiva. Esto incluye el diseño básico, los tamaños de fuente y los elementos comunes compartidos en todos los diseños.
    -   **Selectores clave:** Los desarrolladores pueden inspeccionar la salida HTML del temporizador para identificar clases como `.deliverycountdown-container`, `.deliverycountdown-message`, `.deliverycountdown-timer`, etc., para anular los estilos en la hoja de estilos de su tema `custom.css` o `theme.css`.
-   **`deliverycountdown/views/css/deliverycountdown-{color}-{size}.css`** (por ejemplo, `deliverycountdown-black-200x100.css`, `deliverycountdown-blue-400x48.css`)

    -   **Alcance:** Front office.
    -   **Responsabilidad:** Estos archivos proporcionan los esquemas de color específicos, las imágenes de fondo (si las hay) y los ajustes de tamaño para las diferentes opciones de diseño seleccionadas en el back office. Normalmente anulan o extienden los estilos definidos en `deliverycountdown.css`.
    -   **Selectores clave:** Estos archivos se dirigirán a los mismos selectores principales, pero aplicarán `background-color`, `color`, `width`, `height`, `border`, etc., específicos para lograr el estilo visual elegido.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   **`deliverycountdown/views/hook/displayFooterProduct.tpl`**
        -   **Hook:** `displayFooterProduct` (y potencialmente otros como `displayProductAdditionalInfo`, `displayReassurance`, `displayNav1`, `displayDeliveryTimer` si está configurado).
        -   **Propósito:** Esta es la plantilla principal responsable de renderizar la estructura HTML del temporizador de cuenta regresiva y su mensaje asociado en el front office.
        -   **Contenido:**
            -   Contendrá los elementos `div` principales para el contenedor del temporizador.
            -   Mostrará el mensaje dinámico (por ejemplo, "Pida en los próximos...") y los dígitos de la cuenta regresiva.
            -   Probablemente pasa las variables de configuración necesarias (como la hora límite, los mensajes diarios, los días habilitados, el estado actual del stock del producto, las reglas de exclusión/inclusión) al script `deliverycountdown.js`, ya sea a través de atributos de datos o etiquetas `<script>` en línea.
            -   Incluye el archivo de diseño CSS seleccionado y el script `deliverycountdown.js`.
-   **Plantillas de administración (`views/templates/admin/`)**:

    -   **`deliverycountdown/views/admin/datepicker.tpl`**
        -   **Propósito:** Probablemente una plantilla reutilizable para renderizar un campo de entrada de selector de fecha en la configuración del back office del módulo. (Aunque no se usa explícitamente para fechas en la configuración actual, podría ser un componente de biblioteca).
    -   **`deliverycountdown/views/admin/selectedExcludedProducts.tpl`**
        -   **Propósito:** Renderiza la lista de productos que han sido seleccionados para exclusión o inclusión en la configuración del módulo. Esto forma parte de la interfaz de selección de productos/categorías/fabricantes.
    -   **`deliverycountdown/views/admin/selectedProducts.tpl`**
        -   **Propósito:** Similar a `selectedExcludedProducts.tpl`, pero potencialmente para un contexto de selección diferente (por ejemplo, si hubiera listas separadas de inclusión y exclusión).
    -   **`deliverycountdown/views/admin/timepicker.tpl`**
        -   **Propósito:** Renderiza el campo de entrada del selector de hora utilizado para establecer la "Hora límite de compra" en la configuración del back office.
-   **Plantillas de biblioteca (`deliverycountdown/lib/searchTool/views/scripts.tpl`)**:

    -   **`deliverycountdown/lib/searchTool/views/scripts.tpl`**
        -   **Propósito:** Probablemente contiene lógica JavaScript o Smarty relacionada con la herramienta de búsqueda y selección de productos/categorías/fabricantes utilizada en la configuración del módulo. Este script facilita la búsqueda basada en AJAX y la visualización de los elementos seleccionados.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   Este módulo no crea tablas SQL personalizadas. Todos los ajustes de configuración se almacenan en la tabla estándar `ps_configuration` de PrestaShop.
    -   **Registros de configuración clave (ejemplos):**
        -   `DC_LAYOUT`: Almacena el diseño seleccionado (por ejemplo, 'black-200x100').
        -   `DC_SUNDAY_MSG`, `DC_MONDAY_MSG`, etc.: Almacena el mensaje personalizado para cada día.
        -   `DC_TIME`: Almacena la "Hora límite de compra" (por ejemplo, '16:00').
        -   `DC_EXCL`: Booleano para la regla de exclusión (0 o 1).
        -   `DC_INSTOCK`: Booleano para "Mostrar solo para productos en stock".
        -   `dc_exclusions_products`, `dc_exclusions_cat`, `DC_EXCL_MANUF`: Listas JSON o separadas por comas de IDs para entidades excluidas/incluidas.
        -   `DC_SUNDAY`, `DC_MONDAY`, etc.: Booleanos para habilitar/deshabilitar el temporizador en días específicos.
        -   `DC_HOOK_displayFooterProduct`, `DC_HOOK_displayReassurance`, etc.: Booleanos que indican qué hooks están habilitados para su visualización.
-   **Tabla de hooks registrados**:

| Nombre del Hook | Alcance | Momento de ejecución | Propósito técnico |
| --- | --- | --- | --- |
| `displayHeader` | Front office | En la sección `<head>` de cada página. | Se utiliza para cargar los activos CSS y JS del módulo globalmente, o para la visualización general del temporizador en todo el sitio. |
| `displayNav1` | Front office | Normalmente en la barra de navegación superior. | Muestra el temporizador en el área de navegación principal. |
| `displayNav2` | Front office | A menudo en una barra de navegación secundaria o enlaces de utilidad. | Muestra el temporizador en un área de navegación secundaria. |
| `displayTop` | Front office | En la sección de la cabecera principal, debajo de `displayNav`. | Muestra el temporizador en la cabecera principal. |
| `displayProductAdditionalInfo` | Front office | En la página del producto, a menudo cerca del botón "Añadir al carrito". | Ubicación estratégica para la urgencia específica del producto. |
| `displayFooterProduct` | Front office | En la página del producto, normalmente debajo de la descripción o los detalles del producto. | Otra ubicación específica del producto para la urgencia. |
| `displayReassurance` | Front office | En un bloque de confianza (si el tema lo admite), a menudo debajo de la información del producto. | Integra el temporizador con otros elementos que generan confianza. |
| `displayDeliveryTimer` | Front office | Hook personalizado. | Permite a los desarrolladores de temas colocar el temporizador con precisión en cualquier lugar del tema. |
| `actionAdminControllerSetMedia` | Back office | Cuando un controlador de administración carga sus activos multimedia. | Se utiliza para cargar CSS/JS específicos del módulo para la página de configuración del back office (por ejemplo, para la herramienta de búsqueda, el selector de hora). |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Temporizador de cuenta regresiva para envío", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.

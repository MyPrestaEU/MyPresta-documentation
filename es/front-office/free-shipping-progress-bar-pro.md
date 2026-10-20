---
title: "Barra de Progreso de Envío Gratuito Pro - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Barra de Progreso de Envío Gratuito Pro de MyPresta.eu."
sidebar:
  label: "Barra de Progreso de Envío Gratuito Pro - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Free Shipping Progress Bar Pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-shipping-progress-bar-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/free-shipping-progress-bar-pro/)
>
> ---


# Barra de Progreso de Envío Gratuito Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias y generalmente están habilitadas por defecto en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es el área de configuración principal donde establecerás todas las reglas, apariencia y comportamiento de tu Barra de Progreso de Envío Gratuito. La página está diseñada para ser intuitiva, guiándote a través de varias secciones.

#### Ajustes Generales

-   **Qué hace este ajuste:** Controla la activación general y el comportamiento básico de la barra de progreso.
-   **Efecto de cambiar este ajuste:**
    -   *Habilitar/Deshabilitar Módulo:* Activa o desactiva toda la funcionalidad de la barra de progreso para tu tienda.
    -   *Posición de Visualización:* Determina dónde aparece la barra de progreso en tu front office (por ejemplo, Cabecera, Pie de página, Página de producto, Página de carrito).
    -   *Barra Fija (Sticky Bar):* Hace que la barra se "pegue" a la parte superior o inferior de la pantalla a medida que el usuario se desplaza, manteniéndola visible.
-   **Valor recomendado:**
    -   *Habilitar Módulo:* SÍ (para activar la función).
    -   *Posición de Visualización:* Cabecera (a menudo la más efectiva para la visibilidad).
    -   *Barra Fija:* SÍ (para un impacto máximo).
-   **Escenario / ejemplo de comerciante:** Quieres que la barra de progreso esté siempre visible en la parte superior de tu tienda para recordar constantemente a los clientes sobre el envío gratuito. Habilitarías el módulo, establecerías la posición de visualización en "Cabecera" y habilitarías "Barra Fija".

#### Umbrales de Envío Gratuito

-   **Qué hace este ajuste:** Define la cantidad que los clientes deben gastar para calificar para el envío gratuito. Este es el núcleo de la funcionalidad del módulo. Puedes establecer un umbral predeterminado y luego anularlo con reglas específicas para países o grupos de clientes.
-   **Efecto de cambiar este ajuste:**
    -   *Umbral Predeterminado:* Establece la cantidad base para todos los clientes no cubiertos por reglas específicas.
    -   *Umbrales Específicos por País:* Te permite establecer diferentes cantidades de envío gratuito para clientes de países particulares (por ejemplo, más alto para envíos internacionales).
    -   *Umbrales Específicos por Grupo de Clientes:* Adapta los umbrales para diferentes grupos de clientes (por ejemplo, más bajo para clientes VIP, más alto para mayoristas).
-   **Valor recomendado:** Comienza con un umbral predeterminado que tenga sentido para tu valor medio de pedido y costes de envío. Luego, añade reglas específicas según sea necesario.
-   **Escenario / ejemplo de comerciante:** Tu envío gratuito predeterminado es de 100 €. Sin embargo, para clientes en Canadá, quieres que sea de 150 € debido a los mayores costes de envío. Establecerías el valor predeterminado en 100 € y luego añadirías una regla de país para Canadá en 150 €. Para tu grupo de clientes "Mayoristas", podrías establecerlo en 500 €.

#### Diseñador Visual

-   **Qué hace este ajuste:** Proporciona una interfaz fácil de usar para personalizar la apariencia de tu barra de progreso sin necesidad de codificación. Puedes cambiar colores, fuentes, estilos de barra y más.
-   **Efecto de cambiar este ajuste:** Impacta directamente la apariencia visual de la barra de progreso en tu front office.
    -   *Colores:* Ajusta los colores de fondo, texto y relleno de la barra de progreso para que coincidan con tu marca.
    -   *Fuentes y Tamaños:* Personaliza los estilos de texto para los mensajes.
    -   *Estilo de Barra:* Elige entre diferentes estilos visuales para la propia barra de progreso (por ejemplo, redondeada, plana).
    -   *Animaciones:* Añade animaciones sutiles para una experiencia más atractiva.
-   **Valor recomendado:** Experimenta para encontrar un diseño que sea visualmente atractivo, claramente visible y consistente con la marca de tu tienda.
-   **Escenario / ejemplo de comerciante:** Tu tienda utiliza un tono específico de azul y una fuente limpia y moderna. Usarías el diseñador visual para establecer el fondo de la barra de progreso en ese azul, el texto en blanco y elegir una fuente sans-serif para que coincida con tu tema.

#### Mensajes Dinámicos

-   **Qué hace este ajuste:** Te permite crear mensajes personalizados que aparecen en la barra de progreso, cambiando según el progreso del cliente hacia el envío gratuito. Puedes usar marcadores de posición para insertar valores dinámicos como la cantidad restante.
-   **Efecto de cambiar este ajuste:**
    -   *Mensajes para "Aún no calificado":* Se muestra cuando el cliente no ha alcanzado el umbral.
    -   *Mensajes para "Calificado":* Se muestra una vez que el cliente ha alcanzado o superado el umbral.
    -   *Marcadores de posición:* Usar `[amount_left]`, `[total_cart]`, `[free_shipping_threshold]`, `[currency_symbol]` insertará dinámicamente estos valores en tus mensajes.
-   **Valor recomendado:** Mantén los mensajes claros, concisos y alentadores. Usa marcadores de posición para hacerlos dinámicos y personales.
-   **Escenario / ejemplo de comerciante:**
    -   *No calificado:* "¡Gasta [amount\_left] más para obtener Envío GRATUITO!"
    -   *Calificado:* "¡Felicidades! ¡Tu pedido califica para Envío GRATUITO!"
        Esto comunica claramente el objetivo y celebra el logro.

#### Pruebas A/B y Análisis

-   **Qué hace este ajuste:** Te permite ejecutar pruebas A/B en diferentes configuraciones de la barra de progreso (por ejemplo, diferentes mensajes, colores o umbrales) y rastrear su rendimiento.
-   **Efecto de cambiar este ajuste:**
    -   *Habilita el Modo de Prueba A/B:* Te permite crear variaciones de tu barra de progreso.
    -   *Rastrea Conversiones:* Registra cómo las diferentes variaciones impactan tus tasas de conversión y el valor medio del pedido.
-   **Valor recomendado:** Habilita esta función una vez que tu configuración básica sea estable. Úsala para optimizar continuamente la efectividad de tu barra de progreso.
-   **Escenario / ejemplo de comerciante:** Quieres probar si "¡Gasta X € más para Envío GRATUITO!" funciona mejor que "¡Desbloquea el Envío GRATUITO con solo X € más!". Configurarías dos variaciones y dejarías que el módulo rastree cuál conduce a más ventas.

#### Ajustes Avanzados

-   **Qué hace este ajuste:** Contiene opciones para aspectos más técnicos, como el almacenamiento en caché, la compatibilidad con temas específicos o CSS/JS personalizado.
-   **Efecto de cambiar este ajuste:** Puede afectar el rendimiento, la integración del tema o permitir personalizaciones muy específicas.
    -   *Ajustes de Caché:* Mejora la velocidad de carga al almacenar en caché el contenido de la barra.
    -   *CSS/JS Personalizado:* Permite a los desarrolladores añadir su propio estilo o scripts.
-   **Valor recomendado:** Generalmente, déjalos en su valor predeterminado a menos que tengas una necesidad específica o te lo aconseje un desarrollador.
-   **Escenario / ejemplo de comerciante:** Tu tema personalizado tiene una estructura de cabecera única y la barra de progreso no se alinea perfectamente. Un desarrollador podría usar el campo "CSS Personalizado" para añadir reglas de estilo específicas para corregir la alineación.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Ajustes Generales** | Habilitar Módulo | SÍ | Activa/desactiva toda la función de la barra de progreso. |
| | Posición de Visualización | Cabecera | Dónde aparece la barra (Cabecera, Pie de página, Producto, Carrito, Columnas). |
| | Barra Fija (Sticky Bar) | SÍ | Hace que la barra se pegue a la parte superior/inferior de la pantalla. |
| **Umbrales de Envío Gratuito** | Umbral Predeterminado | Cantidad de envío gratuito de tu tienda | Cantidad base para el envío gratuito. |
| | Reglas por País | Según sea necesario | Anula el valor predeterminado para países específicos. |
| | Reglas por Grupo de Clientes | Según sea necesario | Anula el valor predeterminado para grupos de clientes específicos. |
| **Diseñador Visual** | Color de Fondo de la Barra | Depende del tema | Cambia el color de fondo de la barra. |
| | Color de Relleno del Progreso | Depende del tema | Cambia el color de la sección de progreso rellena. |
| | Color del Texto | Depende del tema | Cambia el color de los mensajes. |
| | Familia / Tamaño de Fuente | Depende del tema | Personaliza la apariencia del texto. |
| | Estilo de Barra | Predeterminado | Diseño visual de la propia barra de progreso. |
| **Mensajes Dinámicos** | Mensaje - No Calificado | "¡Gasta [amount\_left] más para Envío GRATUITO!" | Mensaje que se muestra cuando no se cumple el objetivo. |
| | Mensaje - Calificado | "¡Felicidades! ¡Tu pedido califica para Envío GRATUITO!" | Mensaje que se muestra cuando se cumple el objetivo. |
| **Pruebas A/B y Análisis** | Habilitar Pruebas A/B | NO (inicialmente) | Permite ejecutar pruebas en diferentes configuraciones de barra. |
| | Rastrear Conversiones | SÍ (al hacer pruebas A/B) | Registra el rendimiento de diferentes versiones de la barra. |
| **Ajustes Avanzados** | Habilitar Caché | SÍ | Mejora la velocidad de carga de la barra. |
| | CSS Personalizado | Dejar vacío | Para anulaciones de estilo avanzadas por parte de desarrolladores. |
| | JS Personalizado | Dejar vacío | Para adiciones de scripts avanzadas por parte de desarrolladores. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: La barra de progreso no aparece en mi tienda o no se actualiza.**
**R1:**

-   **Verificar el Estado del Módulo:** Primero, asegúrate de que el módulo esté habilitado en tu Back Office de PrestaShop en **Módulos > Gestor de módulos**.
-   **Verificar la Posición de Visualización:** Ve a la configuración del módulo y verifica el ajuste "Posición de Visualización". Asegúrate de que esté configurado en un `hook` visible (por ejemplo, Cabecera, Pie de página). Si has elegido un `hook` de columna, asegúrate de que tu tema realmente muestre esa columna.
-   **Borrar Caché:** PrestaShop a menudo almacena contenido en caché. Ve a **Parámetros Avanzados > Rendimiento** y haz clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Además, borra la caché de tu navegador.
-   **Compatibilidad con el Tema:** Algunos temas altamente personalizados pueden requerir ajustes menores. Si el problema persiste después de borrar la caché, contacta con el soporte de MyPresta.eu con detalles sobre tu tema.

**P2: La barra de progreso se ve extraña o no coincide con el diseño de mi tema.**
**R2:**

-   **Usar el Diseñador Visual:** El módulo incluye una sección de "Diseñador Visual" en su configuración. Úsala para ajustar colores, fuentes y estilos para que coincidan mejor con tu tema.
-   **CSS Personalizado:** Si el diseñador visual no es suficiente, tu webmaster o un desarrollador puede usar el campo "CSS Personalizado" en los ajustes avanzados del módulo para añadir reglas de estilo específicas que anulen las predeterminadas.
-   **Caché del Tema:** Después de realizar cambios de diseño, siempre borra la caché de PrestaShop (**Parámetros Avanzados > Rendimiento**) y la caché de tu navegador.

**P3: La cantidad de envío gratuito es incorrecta o no cambia para ciertos clientes.**
**R3:**

-   **Verificar las Reglas de Umbral:** Ve a la sección "Umbrales de Envío Gratuito" en la configuración del módulo.
    -   Verifica que el "Umbral Predeterminado" sea correcto.
    -   Comprueba si alguna "Regla Específica por País" o "Regla Específica por Grupo de Clientes" está anulando el valor predeterminado para los clientes afectados. Asegúrate de que las reglas estén configuradas correctamente para los países/grupos relevantes.
-   **Moneda:** Asegúrate de que tu moneda predeterminada y la moneda utilizada para el umbral coincidan.
-   **Cálculo del Carrito:** El módulo se basa en el total del carrito de PrestaShop. Asegúrate de que tus productos tengan precios correctos y que las reglas de impuestos se apliquen como se espera.

**P4: ¿Cómo traduzco los mensajes a diferentes idiomas para mis clientes internacionales?**
**R4:**

-   El módulo es compatible con el sistema de traducción nativo de PrestaShop.
-   Ve a **Internacional > Traducciones** en tu Back Office de PrestaShop.
-   Selecciona "Traducciones de módulos instalados", elige tu tema y luego selecciona el módulo "Barra de Progreso de Envío Gratuito Pro".
-   Luego podrás traducir todos los mensajes dinámicos y otros textos mostrados por el módulo a los idiomas deseados. Recuerda guardar tus cambios.

**P5: La barra de progreso no se muestra en dispositivos móviles o no es adaptable.**
**R5:**

-   El módulo está diseñado para ser totalmente adaptable.
-   **Borrar Caché:** Como siempre, borra la caché de PrestaShop (**Parámetros Avanzados > Rendimiento**) y la caché de tu navegador móvil.
-   **Verificar Posición de Visualización:** Asegúrate de que la posición de visualización elegida (por ejemplo, Cabecera) sea una que tu tema renderice de forma destacada en dispositivos móviles. Algunos temas pueden ocultar ciertos elementos en pantallas más pequeñas.
-   **Conflictos de Tema:** Muy raramente, un tema móvil altamente personalizado podría tener CSS en conflicto. Si el problema persiste, consulta con el soporte de MyPresta.eu o con tu webmaster.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo Barra de Progreso de Envío Gratuito Pro, destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Resumen de la Arquitectura

El módulo `Free Shipping Progress Bar Pro` (`smartfreeshippingpro`) sigue la arquitectura estándar de módulos de PrestaShop, aprovechando principalmente los `hooks` para la visualización en el front-office y un `ModuleFrontController` dedicado para las interacciones AJAX. La configuración se gestiona a través del método `getContent()` de la clase principal del módulo, que renderiza una plantilla Smarty para la interfaz del back-office. Utiliza la clase `Configuration` de PrestaShop para almacenar la configuración y se basa en los servicios centrales de PrestaShop para la información del carrito y la moneda. El módulo enfatiza un enfoque de configuración visual con JS dedicado para la interfaz de administración.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `smartfreeshippingpro/controllers/front/index.php`
        -   **Nombre de la Clase:** `SmartFreeShippingProIndexModuleFrontController` (probablemente, basado en la convención de nombres de archivo)
        -   **Clase Padre:** `ModuleFrontController`
        -   **Responsabilidad:** Este controlador probablemente sirve como base o punto de entrada para las interacciones del front-office, aunque sus métodos específicos podrían ser mínimos si `refresh.php` maneja el AJAX principal. Podría ser responsable de la configuración inicial de datos o de la lógica del front-office no AJAX.
    -   `smartfreeshippingpro/controllers/front/refresh.php`
        -   **Nombre de la Clase:** `SmartFreeShippingProRefreshModuleFrontController`
        -   **Clase Padre:** `ModuleFrontController`
        -   **Responsabilidad:** Este es el punto final AJAX crítico. Responde a las solicitudes (por ejemplo, desde `front.js`) para actualizar la barra de progreso de envío gratuito. Obtiene el total actual del carrito, calcula la cantidad restante para el envío gratuito basándose en los umbrales configurados (reglas predeterminadas, por país, por grupo) y devuelve los datos de progreso y mensajes actualizados, típicamente en formato JSON. Este controlador es responsable de las actualizaciones en tiempo real de la barra.
-   **Controladores de Administración de Back-Office**:

    -   No hay archivos `AdminController` dedicados presentes. Toda la configuración del back-office se maneja dentro del método `getContent()` del archivo principal del módulo (`index.php`).

### 4.3 Clases y Modelos Principales (`classes/`)

No se enumeran explícitamente clases personalizadas que extiendan `ObjectModel` u otras clases principales de PrestaShop en el inventario proporcionado. El módulo probablemente se basa en las clases `Cart`, `Context`, `Configuration`, `Currency` y `Country` integradas de PrestaShop para su lógica.

### 4.4 Activos JavaScript (`views/js/`)

-   `smartfreeshippingpro/views/js/admin-config.js`
    -   **Alcance:** Back-office.
    -   **Descripción:** Probablemente maneja las interacciones generales del formulario de configuración, guardando ajustes y potencialmente la validación del formulario para la página de configuración principal del módulo.
-   `smartfreeshippingpro/views/js/admin-placeholders.js`
    -   **Alcance:** Back-office.
    -   **Descripción:** Gestiona la inserción dinámica de marcadores de posición (por ejemplo, `[amount_left]`, `[total_cart]`) en los campos de entrada de mensajes dentro de la configuración de administración, facilitando a los comerciantes la creación de mensajes dinámicos.
-   `smartfreeshippingpro/views/js/admin-threshold-picker.js`
    -   **Alcance:** Back-office.
    -   **Descripción:** Maneja la lógica para añadir, editar y eliminar umbrales de envío gratuito específicos por país y por grupo de clientes. Esto implicaría elementos de formulario dinámicos para seleccionar países/grupos e introducir cantidades.
-   `smartfreeshippingpro/views/js/admin-visual-designer.js`
    -   **Alcance:** Back-office.
    -   **Descripción:** Impulsa la interfaz de personalización visual. Probablemente utiliza JavaScript para actualizar dinámicamente una vista previa de la barra de progreso a medida que el administrador cambia colores, fuentes y estilos, proporcionando retroalimentación visual inmediata.
-   `smartfreeshippingpro/views/js/admin.js`
    -   **Alcance:** Back-office.
    -   **Descripción:** Un script de administración de propósito general que podría inicializar otros archivos JS específicos de administración, manejar eventos globales de administración o proporcionar funciones de utilidad para la interfaz del back-office.
-   `smartfreeshippingpro/views/js/front.js`
    -   **Alcance:** Front-office.
    -   **Descripción:** Este es el script principal del front-end.
        -   **Escuchadores de Eventos:** Se enlaza a `prestashop.on('updateCart', ...)` o eventos similares para detectar cambios en el carrito de compras (añadir, eliminar, actualizar cantidad).
        -   **Llamadas AJAX:** Activa solicitudes AJAX al controlador frontal `refresh.php` para obtener datos actualizados de la barra de progreso.
        -   **Manipulación del DOM:** Actualiza el ancho de la barra de progreso, los mensajes de texto y, potencialmente, su visibilidad basándose en la respuesta AJAX.
        -   **Animaciones:** Puede incluir lógica para transiciones suaves o animaciones de la barra de progreso.
        -   **Lógica de Barra Fija:** Si la función de barra fija está habilitada, este script manejaría el posicionamiento CSS (`position: fixed`) y potencialmente los escuchadores de eventos de desplazamiento para gestionar su visibilidad.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `smartfreeshippingpro/views/css/admin-config.css`
    -   **Alcance:** Estilo del formulario de administración del back-office.
    -   **Descripción:** Estilos para el diseño general y los elementos de la página de configuración principal del módulo.
-   `smartfreeshippingpro/views/css/admin-threshold-picker.css`
    -   **Alcance:** Estilo del formulario de administración del back-office.
    -   **Descripción:** Estilos específicos para las interfaces de selección de umbrales por país y por grupo de clientes.
-   `smartfreeshippingpro/views/css/admin-visual-designer.css`
    -   **Alcance:** Estilo del formulario de administración del back-office.
    -   **Descripción:** Estilos para la interfaz del diseñador visual, incluyendo selectores de color, elementos de vista previa y diseño.
-   `smartfreeshippingpro/views/css/admin.css`
    -   **Alcance:** Estilo del formulario de administración del back-office.
    -   **Descripción:** Estilos generales de administración, que potencialmente incluyen elementos comunes utilizados en diferentes secciones de administración del módulo.
-   `smartfreeshippingpro/views/css/front.css`
    -   **Alcance:** Estilo del cliente del front-office.
    -   **Descripción:**
        -   Componentes principales de la interfaz de usuario: Estiliza el contenedor de la barra de progreso, el relleno del progreso y los mensajes de texto.
        -   Selectores de clase CSS clave: Probablemente incluye clases como `.smartfreeshippingpro-bar`, `.smartfreeshippingpro-progress`, `.smartfreeshippingpro-message`, `.smartfreeshippingpro-sticky`. Los desarrolladores pueden anularlos en el `custom.css` de su tema o añadiendo CSS personalizado en los ajustes avanzados del módulo.
        -   Reglas de diseño adaptable para varios tamaños de pantalla.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `smartfreeshippingpro/views/templates/admin/configure.tpl`
        -   **Descripción:** La plantilla principal para la página de configuración del módulo en el Back Office. Renderiza todo el formulario, incluyendo ajustes generales, enlaces a otras subplantillas para secciones específicas (como el diseñador visual, el selector de umbrales).
    -   `smartfreeshippingpro/views/templates/admin/country-priority.tpl`
        -   **Descripción:** Probablemente una subplantilla utilizada dentro de `configure.tpl` para gestionar la prioridad de las reglas específicas por país si pudieran aplicarse varias reglas (por ejemplo, un cliente está en un país con una regla específica, pero también forma parte de un grupo con otra regla).
    -   `smartfreeshippingpro/views/templates/admin/country-rules-picker.tpl`
        -   **Descripción:** Una subplantilla para la interfaz donde los administradores definen y gestionan los umbrales de envío gratuito basados en los países de los clientes.
    -   `smartfreeshippingpro/views/templates/admin/group-rules-picker.tpl`
        -   **Descripción:** Una subplantilla para la interfaz donde los administradores definen y gestionan los umbrales de envío gratuito basados en los grupos de clientes.
    -   `smartfreeshippingpro/views/templates/admin/visual-designer.tpl`
        -   **Descripción:** Una subplantilla para la interfaz del diseñador visual, que contiene la estructura HTML para la barra de vista previa y los campos de entrada (selectores de color, deslizadores, campos de texto) para la personalización.
-   **Plantillas de `hook` (`views/templates/hook/`)**:

    -   `smartfreeshippingpro/views/templates/hook/progress.tpl`
        -   **Descripción:** Esta es la plantilla principal del front-office. Contiene la estructura HTML para la propia barra de progreso de envío gratuito (por ejemplo, un `div` para la barra, un `div` para el relleno del progreso y un `span` para el mensaje dinámico).
        -   **Renderizado en `hooks`:** Esta plantilla se renderiza en varios `hooks` del front-office como `displayHeader`, `displayFooter`, `displayProductButtons`, `displayShoppingCart`, `displayLeftColumn`, `displayRightColumn`, dependiendo de la configuración del comerciante.
        -   **Salida de bloque visual:** Muestra la barra de progreso completa y estilizada con su mensaje dinámico.

### 4.7 Esquema de Base de Datos y Mapa de `Hooks`

-   **Tablas de Base de Datos**:

    -   El módulo no parece crear tablas SQL personalizadas según el inventario.
    -   Los registros de configuración se almacenan en la tabla `ps_configuration` de PrestaShop. Las claves seguirían típicamente un patrón como `SMARTFREESHIPPINGPRO_ENABLED`, `SMARTFREESHIPPINGPRO_THRESHOLD_DEFAULT`, `SMARTFREESHIPPINGPRO_COLOR_BAR`, `SMARTFREESHIPPINGPRO_MESSAGE_NOT_QUALIFIED`, etc.
    -   Las reglas específicas por país y grupo podrían almacenarse como arrays serializados dentro de una única entrada de `ps_configuration` o, potencialmente, en una tabla personalizada simple si la estructura es compleja, aunque el inventario sugiere que `ObjectModel` no se utiliza.
-   **Tabla de `Hooks` Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza en la sección `<head>` o en la parte superior del `<body>`. | Inyecta activos CSS/JS y/o el HTML de la barra de progreso (especialmente para barras fijas). |
| `displayFooter` | Se renderiza en la parte inferior del `<body>` antes de la etiqueta de cierre. | Inyecta activos CSS/JS y/o el HTML de la barra de progreso. |
| `displayLeftColumn` | Renderiza contenido en la barra lateral izquierda de la tienda. | Muestra la barra de progreso en la columna izquierda. |
| `displayRightColumn` | Renderiza contenido en la barra lateral derecha de la tienda. | Muestra la barra de progreso en la columna derecha. |
| `displayProductButtons` | Se renderiza cerca del botón "Añadir al carrito" en las páginas de productos. | Muestra la barra de progreso directamente en las páginas de productos. |
| `displayShoppingCart` | Se renderiza en la página de resumen del carrito de compras. | Muestra la barra de progreso en la página del carrito para fomentar más compras. |
| `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador frontal establece sus medios (CSS/JS). | Inyecta archivos CSS y JavaScript específicos del front-office. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración establece sus medios (CSS/JS). | Inyecta archivos CSS y JavaScript específicos del back-office para la página de configuración. |
| `actionCartSave` | Se ejecuta después de guardar un carrito (por ejemplo, se añade/elimina un artículo). | Activa el JS del front-office para actualizar la barra de progreso a través de AJAX. |
| `actionObjectCartUpdateAfter` | Se ejecuta después de que se ha actualizado un objeto de carrito. | Similar a `actionCartSave`, se utiliza para activar actualizaciones. |
| `actionObjectOrderAddAfter` | Se ejecuta después de que se ha añadido un nuevo pedido. | Potencialmente utilizado para análisis de pruebas A/B para rastrear conversiones. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para tu módulo Barra de Progreso de Envío Gratuito Pro, consulta tu cuenta de cliente en MyPresta.eu. Nuestro equipo se dedica a garantizar que tu módulo funcione sin problemas y de manera efectiva.

-   **Acceder a Actualizaciones:** Inicia sesión en tu cuenta de MyPresta.eu y navega a tu historial de pedidos y sección de descargas para obtener la versión más reciente del módulo.
-   **Soporte Técnico:** Si encuentras algún problema, tienes preguntas o necesitas ayuda con la configuración, abre un ticket de soporte a través de tu cuenta de cliente de MyPresta.eu. Nuestro equipo de expertos estará encantado de ayudarte.

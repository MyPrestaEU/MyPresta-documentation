---
title: "Tooltip Pro - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Tooltip Pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "Tooltip Pro - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Tooltip Pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/tooltip-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/tooltip-pro/)
>
> ---


# Tooltip Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Tooltip Pro)

Esta es la pantalla de configuración principal para el módulo Tooltip Pro, donde controla su comportamiento y apariencia general.

- **Ubicación del Menú:** Back Office > Módulos > Gestor de módulos > Buscar "Tooltip Pro" > Hacer clic en "Configurar"

#### Ajustes y Opciones:

1.  **Habilitar Tooltips:**

    - **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar toda la funcionalidad de tooltip en su front office.
    - **Efecto de cambiar este ajuste:**
      - *Cuando está habilitado (SÍ):* Los tooltips estarán activos en su tienda según sus otras configuraciones.
      - *Cuando está deshabilitado (NO):* No aparecerán tooltips en su tienda, independientemente de las entradas de tooltip individuales que haya creado.
    - **Valor recomendado:** SÍ (una vez que haya configurado sus tooltips).
    - **Escenario / ejemplo para el comerciante:** Si está realizando mantenimiento o desea deshabilitar temporalmente todos los tooltips sin eliminarlos, establezca esto en NO.
2.  **Resaltar Palabras Clave del Tooltip:**

    - **Qué hace este ajuste:** Determina si el texto que activa un tooltip debe resaltarse visualmente en su sitio web.
    - **Efecto de cambiar este ajuste:**
      - *Cuando está habilitado (SÍ):* Las palabras clave que ha definido para los tooltips tendrán un estilo visual aplicado (por ejemplo, un subrayado punteado, negrita o un color específico, dependiendo del CSS de su tema o del estilo predeterminado del módulo). Esto ayuda a los clientes a identificar elementos interactivos.
      - *Cuando está deshabilitado (NO):* Las palabras clave aparecerán como texto normal, pero al pasar el cursor sobre ellas seguirá activando el tooltip. Esto puede hacer que los tooltips sean menos descubribles.
    - **Valor recomendado:** SÍ.
    - **Escenario / ejemplo para el comerciante:** Habilitar esto deja claro a sus clientes qué palabras son interactivas, animándolos a descubrir la información útil. Si prefiere un diseño muy minimalista y espera que los usuarios descubran los tooltips de forma natural, podría deshabilitarlo.
3.  **Posición del Tooltip:**

    - **Qué hace este ajuste:** Controla dónde aparece la ventana emergente del tooltip en relación con el texto de la palabra clave.
    - **Efecto de cambiar este ajuste:**
      - *Opciones (por ejemplo, Arriba, Abajo, Izquierda, Derecha, Auto):* Elegir "Arriba" hará que el tooltip aparezca encima del texto, "Abajo" debajo, etc. "Auto" intenta colocar inteligentemente el tooltip para evitar que se salga de la pantalla.
    - **Valor recomendado:** Auto.
    - **Escenario / ejemplo para el comerciante:** "Auto" es generalmente la mejor opción, ya que se adapta a diferentes tamaños de pantalla y diseños de contenido. Si encuentra que los tooltips oscurecen constantemente contenido importante en un área específica, podría experimentar con una ubicación fija como "Abajo".
4.  **Animación del Tooltip:**

    - **Qué hace este ajuste:** Selecciona el efecto de animación cuando un tooltip aparece y desaparece.
    - **Efecto de cambiar este ajuste:**
      - *Opciones (por ejemplo, Desvanecer, Crecer, Balancear, Deslizar, Caer):* Cada opción proporciona una transición visual diferente. "Desvanecer" es una disolución simple, "Crecer" se expande, etc.
    - **Valor recomendado:** Desvanecer o Crecer.
    - **Escenario / ejemplo para el comerciante:** Una animación sutil como "Desvanecer" o "Crecer" añade un toque pulido sin ser una distracción. Evite animaciones excesivamente complejas que puedan ralentizar la experiencia del usuario o sentirse fuera de lugar con su marca.
5.  **Tema del Tooltip:**

    - **Qué hace este ajuste:** Le permite elegir un tema visual predefinido para sus tooltips. Esto afecta los colores, bordes y el estilo general.
    - **Efecto de cambiar este ajuste:**
      - *Opciones (por ejemplo, Predeterminado, Claro, Oscuro, Con Borde, Punk):* Cada tema aplica un conjunto diferente de estilos CSS.
    - **Valor recomendado:** Predeterminado o Claro.
    - **Escenario / ejemplo para el comerciante:** Elija un tema que mejor se adapte al diseño general y la marca de su tienda. "Claro" o "Predeterminado" suelen ser buenos puntos de partida. Si tiene un sitio web con tema oscuro, "Oscuro" podría ser más apropiado.
6.  **Ancho Máximo del Tooltip (píxeles):**

    - **Qué hace este ajuste:** Establece el ancho máximo para la caja emergente del tooltip en píxeles.
    - **Efecto de cambiar este ajuste:**
      - *Introducir un valor (por ejemplo, 300):* El tooltip no excederá este ancho, ajustando el texto si es necesario.
      - *Dejar vacío o 0:* El tooltip se ajustará automáticamente para adaptarse a su contenido, lo que a veces puede llevar a tooltips muy anchos.
    - **Valor recomendado:** 250-350 píxeles.
    - **Escenario / ejemplo para el comerciante:** Establecer un ancho máximo razonable asegura que los tooltips no se vuelvan demasiado anchos y se extiendan por la pantalla, especialmente en dispositivos más pequeños o en diseños de columna estrecha.
7.  **Retraso Antes de Mostrar (milisegundos):**

    - **Qué hace este ajuste:** El tiempo (en milisegundos) que un usuario necesita pasar el cursor sobre una palabra clave antes de que aparezca el tooltip.
    - **Efecto de cambiar este ajuste:**
      - *Valor más alto (por ejemplo, 500ms):* Los tooltips aparecen después de un retraso más largo, evitando que aparezcan demasiado rápido si un usuario solo está moviendo el ratón por la página.
      - *Valor más bajo (por ejemplo, 0ms):* Los tooltips aparecen instantáneamente.
    - **Valor recomendado:** 200-300.
    - **Escenario / ejemplo para el comerciante:** Un ligero retraso (por ejemplo, 200ms) proporciona una experiencia de usuario más fluida, ya que evita que los tooltips accidentales aparezcan y desaparezcan rápidamente.
8.  **Retraso Antes de Ocultar (milisegundos):**

    - **Qué hace este ajuste:** El tiempo (en milisegundos) que el tooltip permanece visible después de que el usuario aleja el ratón de la palabra clave.
    - **Efecto de cambiar este ajuste:**
      - *Valor más alto (por ejemplo, 200ms):* El tooltip permanece visible por un corto período, permitiendo a los usuarios mover ligeramente el ratón sin que el tooltip desaparezca inmediatamente.
      - *Valor más bajo (por ejemplo, 0ms):* El tooltip desaparece instantáneamente cuando el ratón abandona la palabra clave.
    - **Valor recomendado:** 100-200.
    - **Escenario / ejemplo para el comerciante:** Un pequeño retraso aquí puede ser útil si un usuario accidentalmente mueve el ratón fuera de la palabra clave pero quiere seguir leyendo el tooltip.
9.  **Tipos de Página Permitidos para Tooltips:**

    - **Qué hace este ajuste:** Especifica en qué tipos de páginas deben estar activos los tooltips.
    - **Efecto de cambiar este ajuste:**
      - *Casillas de verificación (por ejemplo, Páginas de Producto, Páginas de Categoría, Páginas CMS, Todas las Páginas):* Seleccione los tipos de página específicos donde desea que funcionen sus tooltips.
      - *Seleccionar "Todas las Páginas":* Los tooltips estarán activos en todas partes de su tienda.
    - **Valor recomendado:** Seleccione solo los tipos de página donde realmente necesite tooltips para evitar un procesamiento innecesario en otras páginas.
    - **Escenario / ejemplo para el comerciante:** Si utiliza principalmente tooltips para especificaciones de productos, solo marcaría "Páginas de Producto". Si tiene muchos términos técnicos en todo su sitio, "Todas las Páginas" podría ser apropiado.

### 2.2 Pantalla de Administración Dedicada: Lista de Tooltips (Back Office > Tooltip Pro > Tooltips)

Esta pantalla es donde gestiona todos los tooltips individuales que desea crear y mostrar en su tienda. Actúa como un centro para añadir, editar y eliminar entradas de tooltips.

- **Nombre de la Pantalla y Ubicación del Menú:** Back Office > Tooltip Pro > Tooltips
- **Acciones y Ajustes Disponibles:**
  - **Tabla de Lista de Tooltips:** Muestra una lista de todos sus tooltips creados, típicamente mostrando la palabra clave, el contenido y su estado (habilitado/deshabilitado).
  - **Botón Añadir Nuevo Tooltip:** Haga clic aquí para crear una nueva entrada de tooltip.
  - **Acciones de Editar/Eliminar:** Cada tooltip en la lista tendrá botones de acción (por ejemplo, un icono de lápiz para "Editar", un icono de papelera para "Eliminar") para gestionar entradas individuales.
  - **Acciones Masivas:** A menudo, hay opciones para habilitar, deshabilitar o eliminar múltiples tooltips seleccionados a la vez.

#### Al Añadir/Editar un Tooltip:

1.  **Palabra Clave:**

    - **Qué hace este ajuste:** Esta es la palabra o frase exacta que, cuando se encuentra en su sitio web, activará el tooltip.
    - **Efecto de cambiar este ajuste:** El módulo buscará este texto específico en sus páginas habilitadas. La sensibilidad a mayúsculas y minúsculas podría aplicarse dependiendo de la lógica interna del módulo (asuma que es sensible a mayúsculas y minúsculas para obtener los mejores resultados).
    - **Valor recomendado:** Sea preciso. Utilice la ortografía y las mayúsculas exactas tal como aparecen en su sitio.
    - **Escenario / ejemplo para el comerciante:** Si desea explicar "Algodón Orgánico", introduzca "Algodón Orgánico". Si introduce "algodón orgánico", podría no activarse en "Algodón Orgánico".
2.  **Contenido del Tooltip:**

    - **Qué hace este ajuste:** Esta es la información que se mostrará dentro de la ventana emergente del tooltip. Suele ser un editor de texto enriquecido (WYSIWYG) que permite varios tipos de contenido.
    - **Efecto de cambiar este ajuste:** Lo que introduzca aquí se mostrará al cliente cuando pase el cursor sobre la palabra clave.
    - **Valor recomendado:** Manténgalo conciso e informativo. Utilice imágenes, videos o enlaces con moderación para evitar abrumar al usuario.
    - **Escenario / ejemplo para el comerciante:** Para "Algodón Orgánico", podría añadir: "El algodón orgánico se cultiva sin productos químicos nocivos, pesticidas u OGM, lo que lo hace mejor para el medio ambiente y su piel. [Enlace a la publicación del blog sobre sostenibilidad]".
3.  **Activo:**

    - **Qué hace este ajuste:** Controla si esta entrada de tooltip específica está activa o inactiva.
    - **Efecto de cambiar este ajuste:**
      - *Cuando está habilitado (SÍ):* Este tooltip individual aparecerá en su tienda.
      - *Cuando está deshabilitado (NO):* Este tooltip no aparecerá, incluso si el módulo principal está habilitado.
    - **Valor recomendado:** SÍ (para los tooltips que desea mostrar).
    - **Escenario / ejemplo para el comerciante:** Podría deshabilitar un tooltip temporalmente si la información está desactualizada o si una característica del producto que describe ya no está disponible, sin eliminar la entrada completa.

- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Comience identificando preguntas comunes o términos confusos en sus páginas de productos, páginas de categorías o páginas CMS importantes.
  2. Vaya a **Back Office > Tooltip Pro > Tooltips**.
  3. Haga clic en "Añadir Nuevo Tooltip".
  4. Introduzca la **Palabra Clave** exacta que desea explicar.
  5. Elabore un **Contenido del Tooltip** claro, conciso y útil.
  6. Asegúrese de que **Activo** esté configurado en SÍ.
  7. Guarde sus cambios.
  8. Pruebe el tooltip en su front office para asegurarse de que aparece correctamente y proporciona la información deseada.
  9. Revise regularmente sus tooltips para asegurarse de que la información siga siendo precisa y relevante.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Habilitar Tooltips | SÍ | Interruptor maestro para toda la funcionalidad de tooltip. |
| | Resaltar Palabras Clave del Tooltip | SÍ | Marca visualmente las palabras clave en el front-office. |
| | Posición del Tooltip | Auto | Posición de la ventana emergente del tooltip en relación con la palabra clave. |
| | Animación del Tooltip | Desvanecer / Crecer | Efecto visual cuando el tooltip aparece/desaparece. |
| | Tema del Tooltip | Predeterminado / Claro | Estilo (colores, bordes) de la caja del tooltip. |
| | Ancho Máximo del Tooltip (píxeles) | 250-350 | Evita que los tooltips se vuelvan demasiado anchos. |
| | Retraso Antes de Mostrar (ms) | 200-300 | Tiempo antes de que aparezca el tooltip al pasar el cursor. |
| | Retraso Antes de Ocultar (ms) | 100-200 | Tiempo antes de que el tooltip desaparezca después de pasar el cursor. |
| | Tipos de Página Permitidos | Seleccionar según sea necesario | Restringe los tooltips a tipos de página específicos (por ejemplo, Producto, Categoría). |
| **Lista de Tooltips (Añadir/Editar)** | Palabra Clave | Texto exacto | La palabra/frase específica que activa el tooltip. |
| | Contenido del Tooltip | Conciso, informativo | La información que se muestra dentro del tooltip. |
| | Activo | SÍ | Habilita/deshabilita una entrada de tooltip individual. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Mis tooltips no aparecen en el front office, aunque los he creado.**
R:

1.  **Verifique el Interruptor Maestro:** Vaya a **Módulos > Gestor de módulos > Configurar Tooltip Pro**. Asegúrese de que "Habilitar Tooltips" esté configurado en SÍ.
2.  **Verifique el Estado del Tooltip Individual:** Vaya a **Tooltip Pro > Tooltips**. Asegúrese de que el tooltip específico que espera ver tenga "Activo" configurado en SÍ.
3.  **Verifique el Tipo de Página:** Verifique que la configuración "Tipos de Página Permitidos para Tooltips" incluya el tipo de página que está viendo actualmente (por ejemplo, si está en una página de producto, "Páginas de Producto" debe estar marcada).
4.  **Coincidencia de Palabras Clave:** Asegúrese de que la "Palabra Clave" que introdujo para el tooltip coincida exactamente con el texto de su front office, incluyendo mayúsculas, minúsculas y espacios.
5.  **Borrar Caché:** A veces, la caché de PrestaShop puede impedir que aparezca contenido nuevo. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché".

**P: El contenido del tooltip se ve extraño o no se muestra correctamente (por ejemplo, imágenes rotas, formato extraño).**
R:

1.  **Errores HTML:** Si ha utilizado el editor de texto enriquecido, asegúrese de no haber introducido ninguna etiqueta HTML rota. Cambie a la vista de código fuente en el editor para buscar etiquetas sin cerrar o atributos no válidos.
2.  **Rutas de Imagen:** Si las imágenes no se muestran, verifique que la URL de la imagen en el contenido de su tooltip sea correcta y accesible. Utilice URLs absolutas (que comiencen con `http://` o `https://`) para las imágenes alojadas en su servidor.
3.  **Conflictos de CSS:** El CSS de su tema podría estar anulando el estilo del módulo. Esto es más un problema de desarrollador, pero puede intentar cambiar el "Tema del Tooltip" en la configuración del módulo para ver si un tema diferente lo resuelve.

**P: Los tooltips aparecen en páginas donde no los quiero.**
R:

1.  **Revise "Tipos de Página Permitidos":** Vaya a **Módulos > Gestor de módulos > Configurar Tooltip Pro**. Revise cuidadosamente los "Tipos de Página Permitidos para Tooltips" y desmarque cualquier tipo de página donde no desee que aparezcan los tooltips.
2.  **Especificidad de la Palabra Clave:** Si una palabra clave es muy genérica (por ejemplo, "producto"), podría aparecer en muchas páginas. Considere hacer sus palabras clave más específicas o restringirlas a ciertos tipos de página.

**P: ¿Cómo traduzco mis tooltips a otros idiomas?**
R:

1.  **Editar Tooltip:** Vaya a **Tooltip Pro > Tooltips** y haga clic en "Editar" en el tooltip que desea traducir.
2.  **Selector de Idioma:** Dentro del editor de texto enriquecido "Contenido del Tooltip", debería ver un selector de idioma (normalmente un icono de bandera o un menú desplegable). Seleccione el idioma deseado e introduzca el contenido traducido para ese idioma. Repita para todos los idiomas.
3.  **Traducción de Palabras Clave:** La "Palabra Clave" en sí misma generalmente no es traducida por el módulo, ya que busca el texto exacto en la página. Si sus palabras clave cambian por idioma (por ejemplo, "Guía de Tallas" vs. "Size Guide"), necesitaría crear entradas de tooltip separadas para la palabra clave de cada idioma.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Visión General de la Arquitectura

El módulo Tooltip Pro sigue una arquitectura de módulo estándar de PrestaShop, aprovechando los principios MVC. Consiste principalmente en:

- Una clase de módulo principal (`index.php`) para la instalación, desinstalación y configuración.
- Controladores de administración dedicados (`AdminTooltipsListController`) para gestionar entidades de tooltip en el Back Office.
- Controladores frontales (`ajax.php`) para manejar solicitudes de contenido dinámico si es necesario (aunque la renderización principal del tooltip es del lado del cliente).
- JavaScript del lado del cliente (utilizando la biblioteca Tooltipster) para detectar palabras clave y mostrar tooltips dinámicamente.
- Tabla de base de datos personalizada (`ps_tooltips`) para almacenar definiciones de tooltips.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

- `controllers/front/ajax.php`
  - **Nombre de la clase y clase padre:** `TooltipsAjaxModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador está diseñado para manejar solicitudes AJAX desde el front-office. Si bien el contenido principal del tooltip a menudo se renderiza directamente en el HTML, este controlador podría usarse para la carga dinámica de contenido, la obtención de datos del tooltip bajo demanda u otras características interactivas. Responde a rutas específicas definidas por el módulo.
- `controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `TooltipsIndexModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador podría servir como un recurso alternativo o un marcador de posición. En muchos módulos simples, `index.php` en el directorio del controlador frontal no se utiliza directamente para renderizar una página, pero podría estar presente para la completitud arquitectónica o para manejar el enrutamiento predeterminado del módulo si ningún otro controlador frontal específico coincide. Para Tooltip Pro, la interacción principal del front-office es a través de JavaScript y hooks.

#### Controladores de Administración del Back-Office

- `controllers/admin/AdminTooltipsList.php`
  - **Nombre de la clase y clase padre:** `AdminTooltipsListController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Este controlador gestiona la lista de "Tooltips" en el Back Office de PrestaShop. Es responsable de mostrar la cuadrícula de tooltips existentes, manejar las operaciones de añadir/editar/eliminar para objetos `Tooltip` y renderizar los formularios asociados. Interactúa directamente con el `ObjectModel` `Tooltip`.
- `controllers/admin/index.php`
  - **Nombre de la clase y clase padre:** `TooltipsAdminIndexModuleFrontController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Similar al `index.php` del front-office, este podría ser un marcador de posición o un punto de entrada predeterminado para la sección de administración del módulo. La gestión principal se realiza mediante `AdminTooltipsList.php`.

### 4.3 Clases y Modelos Principales (`classes/`)

El dossier del módulo no indica un directorio `classes/` específico, lo que implica que el `ObjectModel` principal `Tooltip` y la lógica relacionada podrían definirse directamente dentro del archivo principal `tooltips/index.php` o generarse dinámicamente.
Asumiendo una estructura de módulo estándar de PrestaShop, normalmente habría una clase `Tooltip.php`.

- **`Tooltip` (hipotético, probablemente en `index.php` o un `classes/Tooltip.php` dedicado si está presente):**
  - **Tabla de base de datos:** `ps_tooltips` (o `_PREFIX_tooltips`)
  - **Extiende `ObjectModel`:** Sí.
  - **Campos `$definition`:**
    - `id_tooltip`: Clave primaria (INT)
    - `keyword`: La cadena de texto a resaltar (VARCHAR)
    - `content`: El contenido HTML del tooltip (HTML, TEXT)
    - `active`: Booleano para el estado activo/inactivo (TINYINT)
    - `date_add`: Fecha de creación (DATETIME)
    - `date_upd`: Fecha de última actualización (DATETIME)
    - `id_shop`: ID de la tienda para multi-tienda (INT)
    - `id_lang`: ID de idioma para contenido multi-idioma (INT)
  - **Métodos públicos clave:** Métodos estándar de `ObjectModel` (`add()`, `update()`, `delete()`, `getFields()`). Los métodos personalizados podrían incluir `getTooltipsByShopAndLang()` o `getKeywordsForPageType()`.

### 4.4 Activos JavaScript (`views/js/`)

El módulo aprovecha la biblioteca `Tooltipster` para su funcionalidad de tooltip.

- `tooltips/lib/tooltipster/js/plugins/tooltipster/SVG/tooltipster-SVG.js`
  - **Alcance:** Front-office.
  - **Descripción:** Un plugin para la biblioteca Tooltipster específicamente para manejar elementos SVG. Si sus tooltips necesitan interactuar o colocarse en gráficos SVG, este plugin proporciona la funcionalidad necesaria.
- `tooltips/lib/tooltipster/js/tooltipster.bundle.js`
  - **Alcance:** Front-office.
  - **Descripción:** La versión completa y empaquetada de la biblioteca Tooltipster, incluyendo su núcleo y potencialmente otros plugins comunes. Esto proporciona la funcionalidad principal para crear y gestionar tooltips.
- `tooltips/lib/tooltipster/js/tooltipster.core.js`
  - **Alcance:** Front-office.
  - **Descripción:** La funcionalidad principal de la biblioteca Tooltipster. Este archivo contiene la lógica esencial para la creación, posicionamiento, eventos y estilo de los tooltips.
- `tooltips/views/js/tooltips.js`
  - **Alcance:** Front-office.
  - **Descripción:** Este es el JavaScript personalizado del módulo.
    - **Escuchadores de eventos:** Probablemente se vincula al evento `ready` del documento (`$(document).ready()` o similar) para inicializar los tooltips.
    - **Manipulación del DOM:** Escanea el contenido de la página en busca de palabras clave definidas, las envuelve en un elemento HTML específico (por ejemplo, `<span class="tooltip-keyword">`) y luego inicializa la biblioteca Tooltipster en estos elementos.
    - **Inicialización de Tooltipster:** Configura Tooltipster con los ajustes del Back Office del módulo (posición, animación, tema, retrasos, ancho máximo).
    - **Llamadas AJAX:** Potencialmente realiza llamadas AJAX a `controllers/front/ajax.php` para obtener contenido del tooltip dinámicamente, aunque la descripción del módulo sugiere que el contenido a menudo se pre-renderiza.
    - **Interacción móvil:** Maneja eventos de toque para dispositivos móviles para activar los tooltips.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `tooltips/lib/tooltipster/css/tooltipster.bundle.css`
  - **Alcance:** Estilo del cliente del front-office.
  - **Descripción:** La hoja de estilo principal para la biblioteca Tooltipster, que contiene estilos predeterminados para la caja del tooltip, las flechas y varios temas.
- `tooltips/lib/tooltipster/css/tooltipster.core.css`
  - **Alcance:** Estilo del cliente del front-office.
  - **Descripción:** CSS principal para la biblioteca Tooltipster, que define propiedades visuales esenciales para los tooltips.
- `tooltips/views/css/tooltips-admin.css`
  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Descripción:** Contiene estilos específicos para las páginas de configuración del módulo y el controlador `AdminTooltipsList` en el Back Office de PrestaShop, asegurando una interfaz de administración consistente y fácil de usar.
- `tooltips/views/css/tooltips.css`
  - **Alcance:** Estilo del cliente del front-office.
  - **Descripción:** Este es el CSS personalizado del front-office del módulo.
    - **Componentes principales de la interfaz de usuario:** Estiliza las palabras clave resaltadas (por ejemplo, `span.tooltip-keyword`).
    - **Selectores de clase CSS clave:** Los desarrolladores pueden anular los estilos para `.tooltip-keyword` o clases de tema específicas de Tooltipster (por ejemplo, `.tooltipster-base`, `.tooltipster-light`) en el `custom.css` de su tema o creando un archivo de anulación.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- `tooltips/views/tooltips.tpl`
  - **Alcance:** Plantilla de hook del front-office.
  - **Descripción:** Esta plantilla probablemente está enganchada a `displayHeader` o `displayFooter` para generar las variables JavaScript necesarias y potencialmente el script de inicialización para el archivo `tooltips.js`. Podría pasar configuraciones del Back Office (por ejemplo, `tooltip_placement`, `tooltip_animation`, `tooltip_theme`) como variables Smarty al JavaScript. No renderiza directamente el contenido del tooltip, ya que eso lo maneja dinámicamente JavaScript.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de la Base de Datos**:

  - `ps_tooltips`: Almacena las definiciones de cada tooltip.
    - `id_tooltip` (PK, INT)
    - `keyword` (VARCHAR)
    - `content` (TEXT, HTML permitido)
    - `active` (TINYINT(1))
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
    - `id_shop` (INT)
    - `id_lang` (INT)
  - `ps_configuration`: Almacena la configuración de todo el módulo (por ejemplo, `TOOLTIPS_PRO_ENABLED`, `TOOLTIPS_PRO_HIGHLIGHT`, `TOOLTIPS_PRO_PLACEMENT`, etc.).
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyecta archivos CSS y JavaScript (biblioteca Tooltipster, `tooltips.js` y estilos específicos del módulo) en la página. También genera variables de configuración para JS. |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página del Back Office. | Inyecta CSS específico de administración (`tooltips-admin.css`) y potencialmente JS para las páginas de configuración y lista del módulo. |
| `actionFrontControllerSetMedia` | Después de que se han establecido los medios para un controlador frontal. | Permite que el módulo añada condicionalmente su CSS/JS basándose en el contexto de la página actual (por ejemplo, solo en páginas de producto si está configurado). |
| `moduleRoutes` | Durante la inicialización del enrutador. | Registra rutas personalizadas del front-office para `ajax.php` si se utiliza la carga dinámica de contenido. |
| `actionObjectTooltipAddAfter` | Después de que se añade un objeto `Tooltip`. | Puede usarse para borrar la caché o registrar. |
| `actionObjectTooltipUpdateAfter` | Después de que se actualiza un objeto `Tooltip`. | Puede usarse para borrar la caché o registrar. |
| `actionObjectTooltipDeleteAfter` | Después de que se elimina un objeto `Tooltip`. | Puede usarse para borrar la caché o registrar. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para su módulo Tooltip Pro, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar que su módulo funcione perfectamente y le ayude a mejorar su tienda PrestaShop.

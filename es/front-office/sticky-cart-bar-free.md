---
title: "Sticky Cart Bar FREE - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Sticky Cart Bar FREE de PrestaShop por MyPresta.eu."
sidebar:
  label: "Sticky Cart Bar FREE - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Sticky Cart Bar FREE en MyPresta.eu](https://mypresta.eu/modules/front-office-features/sticky-cart-bar-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/sticky-cart-bar-free/)
>
> ---


# Sticky Cart Bar FREE

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Sticky Cart Bar FREE)

Esta es la pantalla de configuración principal donde controlas cómo se comporta y aparece la barra de carrito pegajosa en tus páginas de producto.

#### **Habilitar Barra de Carrito Pegajosa**

- **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar toda la funcionalidad de la barra de carrito pegajosa para tu tienda.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* La barra de carrito pegajosa aparecerá en las páginas de producto según tus otras configuraciones cuando los clientes se desplacen más allá del botón principal "Añadir al carrito".
  - *Cuando está deshabilitado (NO):* La barra de carrito pegajosa no aparecerá en ninguna página de producto, desactivando efectivamente el módulo.
- **Valor recomendado:** SÍ (para utilizar los beneficios del módulo).
- **Escenario / ejemplo de comerciante:** Si estás probando el módulo o quieres deshabilitarlo temporalmente sin desinstalarlo, configúralo en NO. Para el funcionamiento en vivo, debe ser SÍ.

#### **Posición de la Barra de Carrito Pegajosa**

- **Qué hace este ajuste:** Determina dónde se "pegará" la barra pegajosa en la pantalla del cliente, ya sea en la parte superior o inferior.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "Superior":* La barra pegajosa aparecerá en la parte superior de la ventana del navegador, debajo del encabezado.
  - *Cuando se establece en "Inferior":* La barra pegajosa aparecerá en la parte inferior de la ventana del navegador, encima del pie de página.
- **Valor recomendado:** "Inferior" (a menudo menos intrusivo, ya que no cubre la navegación principal ni el logotipo). Sin embargo, "Superior" puede ser más prominente. Prueba ambos para ver cuál funciona mejor para tu tema y audiencia.
- **Escenario / ejemplo de comerciante:** Si tu tienda tiene un encabezado muy ocupado o un menú fijo en la parte superior, colocar la barra pegajosa en la "Inferior" podría evitar el desorden visual. Si deseas la máxima visibilidad para el botón "Añadir al carrito", "Superior" podría ser preferible.

#### **Mostrar en Dispositivos Móviles**

- **Qué hace este ajuste:** Controla si la barra de carrito pegajosa se muestra a los clientes que navegan por tu tienda en smartphones u otros dispositivos móviles.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* La barra de carrito pegajosa estará activa y visible en las páginas de producto móviles.
  - *Cuando está deshabilitado (NO):* La barra de carrito pegajosa no aparecerá en dispositivos móviles, solo en escritorio/tablet.
- **Valor recomendado:** SÍ (Los usuarios móviles se desplazan mucho, y esta característica es muy beneficiosa para ellos).
- **Escenario / ejemplo de comerciante:** Dado el espacio limitado en pantalla en los móviles, mantener el botón "Añadir al carrito" visible es aún más crítico. Solo deshabilítalo si encuentras conflictos de diseño específicos con tu tema móvil.

#### **Mostrar en Dispositivos de Escritorio**

- **Qué hace este ajuste:** Controla si la barra de carrito pegajosa se muestra a los clientes que navegan por tu tienda en ordenadores de escritorio o pantallas de tablet más grandes.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* La barra de carrito pegajosa estará activa y visible en las páginas de producto de escritorio.
  - *Cuando está deshabilitado (NO):* La barra de carrito pegajosa no aparecerá en dispositivos de escritorio, solo en móvil (si está habilitado).
- **Valor recomendado:** SÍ (Incluso en escritorio, las páginas de producto largas se benefician de esta característica).
- **Escenario / ejemplo de comerciante:** La mayoría de las tiendas querrán esto habilitado para todos los tipos de dispositivos para maximizar el potencial de conversión.

#### **Ocultar Botón Original "Añadir al Carrito"**

- **Qué hace este ajuste:** Esta opción te permite ocultar el botón original "Añadir al carrito" en la página del producto una vez que aparece la barra pegajosa.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Cuando la barra pegajosa esté visible, el botón original "Añadir al carrito" en la página del producto se ocultará. Esto puede reducir la redundancia visual.
  - *Cuando está deshabilitado (NO):* Tanto el botón "Añadir al carrito" de la barra pegajosa como el botón original "Añadir al carrito" serán visibles simultáneamente (cuando el original esté a la vista).
- **Valor recomendado:** NO (Generalmente, es más seguro mantener el botón original visible si está en el viewport, ya que algunos clientes podrían preferirlo. Ocultarlo podría causar confusión si la barra pegajosa desaparece rápidamente).
- **Escenario / ejemplo de comerciante:** Si encuentras que los botones duales "Añadir al carrito" son visualmente distractores o confusos cuando la barra pegajosa está activa, podrías habilitar esto. De lo contrario, déjalo deshabilitado.

#### **Compatibilidad con el Tema**

- **Qué hace este ajuste:** Este ajuste ayuda al módulo a adaptar su estilo y comportamiento a diferentes temas de PrestaShop, específicamente Classic y Hummingbird (el tema predeterminado para PrestaShop 8+).
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "Classic":* El módulo cargará CSS y JavaScript optimizados para el tema Classic de PrestaShop y los temas basados en él.
  - *Cuando se establece en "Hummingbird":* El módulo cargará CSS y JavaScript optimizados para el tema Hummingbird de PrestaShop (PrestaShop 8.x y 9.x por defecto) y los temas basados en él.
- **Valor recomendado:** Selecciona el tema que tu tienda esté utilizando actualmente. Si estás en PrestaShop 8.x o 9.x, es probable que sea "Hummingbird". Si estás en PrestaShop 1.7.x y usas el tema predeterminado, es "Classic". Si usas un tema personalizado, prueba ambos para ver cuál se integra mejor.
- **Escenario / ejemplo de comerciante:** Si tu tienda está en PrestaShop 8.1 y seleccionas "Classic", la barra pegajosa podría no verse o funcionar correctamente. Siempre haz que coincida con tu tema activo.

#### **Avance de la Versión Pro**

- **Qué hace este ajuste:** Esta sección es un área promocional para el módulo "Sticky Cart Bar PRO", que ofrece características avanzadas no disponibles en la versión FREE. No afecta la funcionalidad del módulo FREE.
- **Efecto de cambiar este ajuste:** No tiene un efecto directo en el comportamiento del módulo FREE. Proporciona información sobre la actualización.
- **Valor recomendado:** N/A (Solo informativo).
- **Escenario / ejemplo de comerciante:** Si encuentras beneficioso el módulo FREE y necesitas más control sobre la segmentación, el diseño o las exclusiones de productos específicos, puedes revisar las características de la versión PRO aquí.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Habilitar Barra de Carrito Pegajosa | SÍ | Interruptor maestro para el módulo. SÍ activa la barra pegajosa. |
| Configuración del Módulo | Posición de la Barra de Carrito Pegajosa | Inferior | Determina si la barra se adhiere a la parte superior o inferior de la pantalla. |
| Configuración del Módulo | Mostrar en Dispositivos Móviles | SÍ | Controla la visibilidad en smartphones/tablets. SÍ es recomendado. |
| Configuración del Módulo | Mostrar en Dispositivos de Escritorio | SÍ | Controla la visibilidad en ordenadores de escritorio. SÍ es recomendado. |
| Configuración del Módulo | Ocultar Botón Original "Añadir al Carrito" | NO | Oculta el botón original cuando la barra pegajosa está activa. NO es generalmente más seguro. |
| Configuración del Módulo | Compatibilidad con el Tema | Hummingbird (para PS 8/9) | Asegura el estilo y la funcionalidad correctos para tu tema activo. Haz que coincida con tu tema. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: La barra de carrito pegajosa no aparece en mis páginas de producto.**
R:

-   **Verifica "Habilitar Barra de Carrito Pegajosa"**: Asegúrate de que esta configuración esté en SÍ en la configuración del módulo.
-   **Verifica "Compatibilidad con el Tema"**: Asegúrate de haber seleccionado el tema correcto (Classic o Hummingbird) que coincida con el tema activo de tu tienda. Una selección incorrecta puede impedir que la barra se cargue.
-   **Borrar Caché**: Ve a **Parámetros Avanzados > Rendimiento** en el back office de tu PrestaShop y haz clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los archivos de caché antiguos impiden que aparezcan los nuevos cambios del módulo.
-   **Desplázate Más Allá del Botón Original**: Recuerda, la barra solo aparece cuando te desplazas más allá del botón original "Añadir al carrito". Asegúrate de desplazarte lo suficiente hacia abajo en la página.
-   **Verifica la Configuración del Dispositivo**: Asegúrate de que "Mostrar en Dispositivos Móviles" y/o "Mostrar en Dispositivos de Escritorio" estén habilitados para el dispositivo en el que estás realizando la prueba.

**P2: La barra de carrito pegajosa se ve extraña o desalineada con mi tema personalizado.**
R:

-   **Compatibilidad con el Tema**: Vuelve a verificar que hayas seleccionado la opción correcta de "Compatibilidad con el Tema" en la configuración del módulo. Si tienes un tema altamente personalizado, podría comportarse de manera diferente. Intenta cambiar entre "Classic" y "Hummingbird" para ver si uno funciona mejor.
-   **CSS Personalizado (Se Necesita Desarrollador)**: Si el problema persiste, tu tema personalizado podría tener estilos CSS en conflicto. Un desarrollador web puede inspeccionar la página usando las herramientas de desarrollador del navegador y escribir unas pocas líneas de CSS personalizado para ajustar la apariencia de la barra pegajosa. Esto generalmente implica anular los estilos existentes en el archivo `custom.css` de tu tema.

**P3: El botón "Añadir al carrito" en la barra pegajosa no funciona.**
R:

-   **Borrar Caché**: Al igual que con los problemas de visualización, borrar la caché de tu PrestaShop (**Parámetros Avanzados > Rendimiento**) puede resolver problemas relacionados con JavaScript.
-   **Compatibilidad con el Tema**: Asegúrate de que el tema correcto esté seleccionado. El JavaScript podría no inicializarse correctamente si se elige el tema incorrecto.
-   **Errores de la Consola del Navegador (Se Necesita Desarrollador)**: Pide a tu desarrollador web que revise la consola JavaScript del navegador en busca de errores. Los conflictos con otros módulos o el JavaScript del tema a veces pueden impedir que el botón funcione.

**P4: ¿Puedo personalizar los colores o el contenido de la barra pegajosa?**
R:

-   La versión FREE del módulo ofrece opciones de estilo limitadas (principalmente adaptándose a tu tema). Para una personalización avanzada como cambiar colores, fuentes, añadir texto personalizado o un control más granular sobre la información que se muestra, normalmente necesitarías actualizar al módulo **Sticky Cart Bar PRO**.
-   Para pequeños ajustes visuales en la versión FREE, un desarrollador web puede usar CSS personalizado para anular los estilos predeterminados.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Visión General de la Arquitectura

El módulo Sticky Cart Bar FREE sigue una arquitectura estándar de módulo de PrestaShop, aprovechando principalmente la clase `Module` para la instalación, desinstalación y configuración. Se integra con el front-office a través de hooks, inyectando dinámicamente una barra pegajosa basada en el comportamiento de desplazamiento del usuario. El módulo utiliza una combinación de plantillas Smarty para la estructura, CSS para el estilo y JavaScript para la funcionalidad pegajosa y la interacción con el botón principal "Añadir al carrito". La compatibilidad con diferentes temas de PrestaShop (Classic vs. Hummingbird) se maneja cargando activos específicos del tema.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores de administración de Front-Office o Back-Office personalizados. Toda la configuración se maneja a través del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Principales (`classes/`)

-   `stickycartbarfree/classes/index.php`:
    -   Este es típicamente un archivo vacío utilizado para evitar la lista de directorios, una práctica de seguridad común en los módulos de PrestaShop. No contiene código funcional.
-   `stickycartbarfree/classes/ScbfCompatibility.php`:
    -   **Nombre de la Clase**: `ScbfCompatibility`
    -   **Clase Padre**: Ninguna (clase de utilidad independiente)
    -   **Responsabilidad**: Esta clase probablemente contiene métodos estáticos de ayuda para manejar las diferencias de compatibilidad entre varias versiones o temas de PrestaShop. Podría abstraer las diferencias en cómo se recuperan los datos del producto o cómo se registran los activos, asegurando que el módulo funcione en todos los entornos compatibles. No interactúa directamente con una tabla de base de datos específica, pero podría consultar `ps_configuration` para obtener información del tema.
    -   **Métodos Públicos Clave**: Probablemente métodos estáticos para verificar el contexto del tema, la versión de PrestaShop o recuperar valores de configuración de una manera compatible.

### 4.4 Activos JavaScript (`views/js/`)

-   `stickycartbarfree/views/js/front.js`:
    -   **Ámbito**: Front-office.
    -   **Descripción**: Este es el archivo JavaScript principal responsable del comportamiento pegajoso de la barra de carrito.
    -   **Funcionalidad**:
        -   **Escuchadores de Eventos**: Se enlaza al evento `scroll` en la ventana para detectar cuándo el usuario se desplaza.
        -   **Manipulación del DOM**:
            -   Calcula la posición del botón original "Añadir al carrito" (`#add_to_cart` o un selector similar).
            -   Monitorea la posición de desplazamiento en relación con el botón original.
            -   Añade/elimina una clase CSS (por ejemplo, `is-visible`) al contenedor de la barra de carrito pegajosa (`#sticky-cart-bar`) para mostrarla u ocultarla.
            -   Potencialmente oculta el botón original "Añadir al carrito" si la configuración del módulo correspondiente está habilitada.
        -   **Interacción**: Maneja los clics en el botón "Añadir al carrito" dentro de la barra pegajosa, probablemente imitando el comportamiento del botón original (por ejemplo, enviando el formulario del producto, realizando una llamada AJAX para añadir al carrito).
        -   **Responsividad**: Puede incluir lógica para reevaluar posiciones en eventos `resize`.
        -   **Eventos de PrestaShop**: Probablemente utiliza `prestashop.on('updateProduct', ...)` o eventos similares para actualizar el contenido de la barra pegajosa (precio, cantidad, atributos) cuando se cambian las opciones del producto en la página.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `stickycartbarfree/views/css/admin-config.css`:
    -   **Ámbito**: Estilo del formulario de administración del Back-office.
    -   **Descripción**: Contiene estilos específicamente para la página de configuración del módulo en el back office de PrestaShop, asegurando una interfaz de administración consistente y fácil de usar.
    -   **Componentes principales de la interfaz de usuario**: Estilos para elementos de formulario, etiquetas, botones y potencialmente elementos de diseño específicos dentro de la salida de `getContent()`.
-   `stickycartbarfree/views/css/admin-pro-teaser.css`:
    -   **Ámbito**: Estilo del formulario de administración del Back-office.
    -   **Descripción**: Estilos para el contenido promocional relacionado con la versión PRO del módulo que se muestra en la página de configuración.
    -   **Componentes principales de la interfaz de usuario**: Estilos para cuadros de avance, botones de actualización, listas de características e imágenes de vista previa para la versión PRO.
-   `stickycartbarfree/views/css/front-classic.css`:
    -   **Ámbito**: Estilo del cliente del Front-office (tema Classic).
    -   **Descripción**: Proporciona ajustes de estilo específicos para la barra de carrito pegajosa cuando se selecciona la opción de compatibilidad con el tema "Classic". Esto asegura que la barra se integre visualmente con el diseño del tema Classic.
    -   **Selectores de clase CSS clave**: Dirige elementos dentro de `sticky-cart-bar` para que coincidan con las fuentes, colores, espaciado y estilos de botón del tema Classic.
-   `stickycartbarfree/views/css/front-hummingbird.css`:
    -   **Ámbito**: Estilo del cliente del Front-office (tema Hummingbird).
    -   **Descripción**: Proporciona ajustes de estilo específicos para la barra de carrito pegajosa cuando se selecciona la opción de compatibilidad con el tema "Hummingbird". Esto asegura que la barra se integre visualmente con el tema predeterminado de PrestaShop 8.x/9.x.
    -   **Selectores de clase CSS clave**: Dirige elementos dentro de `sticky-cart-bar` para que coincidan con las fuentes, colores, espaciado y estilos de botón del tema Hummingbird.
-   `stickycartbarfree/views/css/front.css`:
    -   **Ámbito**: Estilo del cliente del Front-office (general).
    -   **Descripción**: Contiene los estilos base y comunes para la barra de carrito pegajosa que se aplican independientemente de la compatibilidad del tema seleccionado. Esto incluye el posicionamiento central, la visibilidad y la capacidad de respuesta.
    -   **Selectores de clase CSS clave**: Define propiedades de `#sticky-cart-bar` como `position: fixed`, `z-index`, `width`, `padding`, `background-color` y consultas de medios responsivas.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   `stickycartbarfree/views/templates/hook/sticky-cart-bar-classic.tpl`: Se renderiza cuando se selecciona la compatibilidad con el tema "Classic". Contiene la estructura principal para la barra pegajosa, adaptada a las expectativas de HTML y CSS del tema Classic.
    -   `stickycartbarfree/views/templates/hook/sticky-cart-bar-hummingbird.tpl`: Se renderiza cuando se selecciona la compatibilidad con el tema "Hummingbird". Contiene la estructura principal para la barra pegajosa, adaptada a las expectativas de HTML y CSS del tema Hummingbird.
    -   `stickycartbarfree/views/templates/hook/sticky-cart-bar-inner.tpl`: Esta plantilla probablemente contiene el contenido principal de la barra pegajosa (nombre del producto, precio, entrada de cantidad, botón de añadir al carrito). Probablemente está incluida por `sticky-cart-bar-classic.tpl` y `sticky-cart-bar-hummingbird.tpl` para evitar la duplicación de código.
    -   `stickycartbarfree/views/templates/hook/sticky-cart-bar.tpl`: Esta podría ser una plantilla envolvente o un fallback, o podría ser el punto de entrada principal que incluye condicionalmente `sticky-cart-bar-classic.tpl` o `sticky-cart-bar-hummingbird.tpl` según la configuración.
    -   **Propósito**: Estas plantillas suelen estar enganchadas a `displayFooter` o `displayBeforeBodyClosingTag` para asegurar que el HTML de la barra pegajosa esté presente en las páginas de productos. Generan la estructura HTML para la barra pegajosa, poblada con datos de productos pasados desde el módulo.
-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `stickycartbarfree/views/templates/admin/configure.tpl`: Esta es la plantilla principal para la página de configuración del módulo en el Back Office. Renderiza todas las configuraciones, campos de entrada y opciones definidas en el método `getContent()` del módulo.
    -   `stickycartbarfree/views/templates/admin/pro-teaser-intro.tpl`: Renderiza la parte introductoria del avance de la versión PRO en la página de configuración.
    -   `stickycartbarfree/views/templates/admin/pro-teaser-preview.tpl`: Renderiza una vista previa o representación visual de las características de la versión PRO.
    -   `stickycartbarfree/views/templates/admin/pro-teaser.tpl`: La plantilla principal para la sección de avance de la versión PRO, que probablemente incluye las plantillas de introducción y vista previa.
    -   **Propósito**: Estas plantillas proporcionan la interfaz de usuario para las configuraciones del módulo y el contenido promocional dentro del Back Office de PrestaShop.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   Este módulo no crea ninguna tabla SQL personalizada.
    -   Las configuraciones se almacenan en la tabla estándar `ps_configuration` de PrestaShop, con claves típicamente prefijadas por `SCBF_` (por ejemplo, `SCBF_ENABLE`, `SCBF_POSITION`).
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para registrar activos CSS y JavaScript (`front.js`, `front.css`, CSS específico del tema) para el front-office. |
| `displayFooter` | Antes de la etiqueta de cierre `</body>` en cada página. | Se utiliza para inyectar la estructura HTML principal de la barra de carrito pegajosa (`sticky-cart-bar.tpl` o sus variantes) en la página. |
| `actionFrontControllerSetMedia` | Después de que los medios (CSS/JS) hayan sido establecidos por el controlador frontal. | Hook alternativo para registrar activos, asegurando que se carguen correctamente. |
| `actionProductUpdate` | Después de que un producto se actualiza en el back office. | (Probablemente no se usa en la versión FREE, pero es común para módulos que necesitan borrar la caché o reindexar datos de productos). |
| `actionCartUpdateQuantity` | Cuando se actualiza la cantidad de un producto en el carrito. | (Probablemente no se usa en la versión FREE, pero podría usarse para actualizar el selector de cantidad de la barra pegajosa si fuera más interactivo). |
| `actionAjaxDieProduct` | Cuando una solicitud AJAX relacionada con datos de productos falla. | (Podría usarse para depuración o interacciones AJAX específicas). |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y para explorar las características avanzadas disponibles en la versión PRO del módulo, visita tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta relacionada con el módulo Sticky Cart Bar FREE.

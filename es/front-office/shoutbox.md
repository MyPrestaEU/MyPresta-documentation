---
title: "Shoutbox - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Shoutbox de PrestaShop por MyPresta.eu."
sidebar:
  label: "Shoutbox - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Shoutbox en MyPresta.eu](https://mypresta.eu/modules/front-office-features/shoutbox.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/shoutbox/)
>
> ---


# Shoutbox

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo Shoutbox, accesible directamente después de la instalación o navegando a **Módulos > Gestor de módulos**, buscando "Shoutbox" y haciendo clic en "Configurar".

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo para el comerciante |
| --- | --- | --- | --- | --- |
| **Habilitar Shoutbox** | Este es el interruptor maestro para activar o desactivar toda la función Shoutbox en su tienda. | *Cuando está habilitado:* El Shoutbox aparecerá en su front office en las ubicaciones de hook elegidas. Los clientes pueden verlo e interactuar con él.   *Cuando está deshabilitado:* El Shoutbox estará completamente oculto de su tienda, y no se mostrarán ni aceptarán mensajes. | **SÍ** | Desea activar la función de chat comunitario en su tienda. Si necesita ocultarlo temporalmente para mantenimiento o revisión de contenido, lo establecería en NO. |
| **Título del Shoutbox** | Esto establece el texto del encabezado que aparece en la parte superior del widget Shoutbox en el front office de su tienda. | *Cuando se establece en "Chat Comunitario":* Sus clientes verán "Chat Comunitario" como el título del cuadro.   *Cuando se establece en "Pregúntanos lo que quieras":* El título cambia a "Pregúntanos lo que quieras". | **Chat Comunitario** | Desea etiquetar claramente el cuadro de chat para sus clientes. Podría cambiarlo a "Discusiones de Productos" si lo coloca en las páginas de productos. |
| **Número de Mensajes a Mostrar** | Esto controla cuántos de los mensajes más recientes se muestran en el Shoutbox en un momento dado. Los mensajes más antiguos se ocultarán. | *Cuando se establece en 10:* Solo los últimos 10 mensajes serán visibles en el cuadro de chat.   *Cuando se establece en 20:* Se mostrarán los últimos 20 mensajes. | **10** | Para mantener el chat conciso y evitar que se vuelva demasiado largo, mostrar los 10-15 mensajes más recientes suele ser lo mejor. Si tiene una comunidad muy activa, podría aumentarlo. |
| **Intervalo de Actualización (segundos)** | Esto determina con qué frecuencia el Shoutbox busca y carga automáticamente nuevos mensajes sin que el cliente tenga que actualizar la página. | *Cuando se establece en 5:* Los nuevos mensajes aparecerán cada 5 segundos.   *Cuando se establece en 15:* Los nuevos mensajes aparecerán cada 15 segundos. | **10** | Un intervalo más corto (por ejemplo, 5 segundos) hace que el chat se sienta más en tiempo real, pero utiliza más recursos del servidor. Un intervalo más largo (por ejemplo, 15-20 segundos) reduce la carga del servidor, pero los mensajes aparecen menos instantáneamente. 10 segundos es un buen equilibrio. |
| **Permitir Publicaciones a Invitados** | Esta opción controla si los visitantes que no han iniciado sesión en una cuenta de cliente pueden publicar mensajes en el Shoutbox. | *Cuando está habilitado:* Cualquiera que visite su tienda puede publicar mensajes, incluso si no se ha registrado o iniciado sesión. Normalmente publicarán como "Invitado".   *Cuando está deshabilitado:* Solo los clientes registrados y con sesión iniciada pueden publicar mensajes. Los invitados verán el chat pero no podrán contribuir. | **NO** | Si desea fomentar el registro y evitar el spam anónimo, deshabilite esto. Si desea la máxima interacción y no le importan las publicaciones anónimas, habilítelo. |
| **Mostrar Shoutbox En** | Esta configuración crucial determina dónde aparecerá el widget Shoutbox en el front office de su tienda. Puede seleccionar una o más ubicaciones. | *Cuando se selecciona "Columna Izquierda":* El Shoutbox aparecerá en la barra lateral izquierda de su tienda.   *Cuando se selecciona "Pie de página":* El Shoutbox aparecerá en la parte inferior de las páginas de su tienda. | **Columna Izquierda** (o una ubicación que se adapte a su tema) | Desea que el Shoutbox sea fácilmente visible pero que no interfiera con el contenido principal de su producto. Colocarlo en una columna o en el pie de página suele ser una buena opción. |
| **Moderación Requerida** | Si está habilitado, los nuevos mensajes no aparecerán en el Shoutbox hasta que un administrador los apruebe manualmente en el Back Office. | *Cuando está habilitado:* Todos los mensajes nuevos entran en una cola pendiente. Debe aprobar cada mensaje antes de que sea visible para otros clientes.   *Cuando está deshabilitado:* Los mensajes aparecen instantáneamente después de ser publicados. | **NO** (a menos que anticipe spam) | Si le preocupa el spam, el contenido inapropiado o desea mantener un control estricto sobre la conversación, habilite la moderación. Para un chat más fluido y en tiempo real, deshabilítelo. |
| **Borrar Todos los Mensajes** | Este es un botón (no un interruptor) que, al hacer clic, eliminará permanentemente todos los mensajes existentes del Shoutbox. | *Al hacer clic:* Todos los mensajes históricos en el Shoutbox se eliminan de su base de datos y ya no se mostrarán. Esta acción es irreversible. | **N/A** (Usar con precaución) | Podría usar esto si el chat ha acumulado demasiados mensajes antiguos, o si desea iniciar una nueva conversación para una nueva promoción o evento. |

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Habilitar Shoutbox | SÍ | Activa/desactiva toda la función Shoutbox. |
| Configuración del Módulo | Título del Shoutbox | Chat Comunitario | Establece el título visible del widget Shoutbox. |
| Configuración del Módulo | Número de Mensajes a Mostrar | 10 | Controla cuántos mensajes recientes se muestran. |
| Configuración del Módulo | Intervalo de Actualización (segundos) | 10 | Con qué frecuencia se actualiza el chat con nuevos mensajes. |
| Configuración del Módulo | Permitir Publicaciones a Invitados | NO | Determina si los usuarios no registrados pueden publicar mensajes. |
| Configuración del Módulo | Mostrar Shoutbox En | Columna Izquierda | Selecciona la(s) ubicación(es) del front-office para el Shoutbox. |
| Configuración del Módulo | Moderación Requerida | NO | Requiere aprobación del administrador para que los mensajes aparezcan. |
| Configuración del Módulo | Borrar Todos los Mensajes | N/A | Elimina permanentemente todos los mensajes del Shoutbox. |

## 3. Solución de Problemas para el Comerciante y Preguntas Frecuentes (FAQ)

**P1: El Shoutbox no aparece en mi tienda, aunque lo he habilitado.**
**R1:**

- **Verifique la selección del Hook:** Vaya a la configuración del módulo y asegúrese de haber seleccionado al menos una ubicación en "Mostrar Shoutbox En" (por ejemplo, Columna Izquierda, Pie de página).
- **Borrar caché:** La caché de PrestaShop a veces puede impedir que aparezcan nuevos módulos. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
- **Compatibilidad con el tema:** Algunos temas altamente personalizados pueden no renderizar correctamente los hooks de módulo estándar. Si borrar la caché no funciona, intente cambiar temporalmente al tema predeterminado de PrestaShop para ver si aparece el Shoutbox. Si lo hace, es probable que su tema necesite un pequeño ajuste (contacte con el desarrollador de su tema o un webmaster).

**P2: Los mensajes nuevos no aparecen en tiempo real; tengo que actualizar la página.**
**R2:**

- **Verifique el intervalo de actualización:** En la configuración del módulo, asegúrese de que "Intervalo de Actualización (segundos)" esté configurado en un número razonable (por ejemplo, 5-15 segundos) y no en 0 o un número muy alto.
- **Conflictos de JavaScript:** Otro módulo o el JavaScript de su tema podría estar causando un conflicto. Revise la consola de desarrollador de su navegador (tecla F12, luego mire la pestaña "Consola") en busca de errores de JavaScript. Si aparecen errores, intente deshabilitar otros módulos instalados recientemente uno por uno para identificar al culpable.

**P3: Estoy recibiendo muchos mensajes de spam en el Shoutbox.**
**R3:**

- **Habilitar moderación:** Vaya a la configuración del módulo y establezca "Moderación Requerida" en SÍ. Esto pondrá todos los mensajes nuevos en estado pendiente, permitiéndole aprobarlos antes de que se publiquen.
- **Deshabilitar publicaciones de invitados:** Si el spam proviene de usuarios anónimos, establezca "Permitir Publicaciones a Invitados" en NO. Esto requerirá que los usuarios inicien sesión en una cuenta de cliente para publicar, lo que a menudo reduce el spam.

**P4: ¿Cómo traduzco el título del Shoutbox u otros textos a diferentes idiomas?**
**R4:**

- Navegue a **Internacional > Traducciones** en su Back Office de PrestaShop.
- Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione su idioma.
- Busque el módulo "Shoutbox" en la lista y podrá editar las cadenas traducibles, incluido el título del Shoutbox.

**P5: El Shoutbox se ve un poco mal o no coincide con el estilo de mi tema.**
**A5:**

- El módulo utiliza estilos básicos. Para una apariencia personalizada, necesitará un webmaster o desarrollador para agregar reglas CSS personalizadas a la hoja de estilos de su tema. Pueden apuntar a los elementos del Shoutbox y ajustar colores, fuentes, bordes, etc., para que coincidan perfectamente con su marca.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo Shoutbox, destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Visión General de la Arquitectura

El módulo Shoutbox sigue una estructura clásica de módulo de PrestaShop, aprovechando los controladores frontales para las interacciones AJAX y el archivo principal del módulo (`index.php`) para la configuración y el registro de hooks. Es un módulo ligero, centrado principalmente en mostrar y enviar mensajes a través de AJAX sin modelos de objetos complejos o tablas de base de datos dedicadas más allá de `ps_configuration` para la configuración. La funcionalidad principal se basa en la interacción directa con la base de datos para el almacenamiento y la recuperación de mensajes.

### 4.2 Controladores (`controllers/`)

El módulo utiliza controladores frontales para manejar las solicitudes AJAX para cargar e insertar mensajes, asegurando una experiencia de usuario dinámica sin recargas completas de la página.

- **Controladores del Front-Office**:

  - `controllers/front/ajaxload.php`
    - **Nombre de la Clase**: `ShoutboxAjaxloadModuleFrontController` (extiende `ModuleFrontController`)
    - **Responsabilidad**: Este controlador maneja la solicitud AJAX para cargar mensajes existentes. Típicamente, obtiene un número especificado de los mensajes más recientes de la base de datos y los devuelve, probablemente como JSON o HTML sin formato, para ser mostrados en el widget Shoutbox. Este es el punto final para el mecanismo de auto-actualización.
  - `controllers/front/index.php`
    - **Nombre de la Clase**: `ShoutboxIndexModuleFrontController` (extiende `ModuleFrontController`)
    - **Responsabilidad**: Este controlador podría servir como un respaldo o un punto de acceso directo al Shoutbox si tuviera una página dedicada. Dada la naturaleza del módulo, es más probable que sea un marcador de posición o que maneje la lógica de renderizado inicial si el Shoutbox se incrusta directamente en lugar de a través de un hook. En la mayoría de los casos, el Shoutbox se renderiza a través de `shoutbox.tpl` en un hook.
  - `controllers/front/insert.php`
    - **Nombre de la Clase**: `ShoutboxInsertModuleFrontController` (extiende `ModuleFrontController`)
    - **Responsabilidad**: Este controlador maneja la solicitud AJAX para enviar nuevos mensajes. Recibe el contenido del mensaje (y potencialmente el ID/nombre del usuario) del front-end, realiza cualquier validación necesaria (por ejemplo, publicación de invitados, moderación), almacena el mensaje en la base de datos y devuelve una respuesta de éxito/fracaso.
- **Controladores de Administración del Back-Office**:

  - Ninguno. Toda la configuración se maneja dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

El módulo no define ninguna clase personalizada o `ObjectModel` en el directorio `classes/`. El almacenamiento y la recuperación de mensajes se manejan directamente dentro de los archivos PHP del módulo, probablemente utilizando `Db::getInstance()` para las consultas SQL. Esto implica que los mensajes se almacenan en una tabla personalizada creada durante la instalación o directamente en `ps_configuration` si los mensajes son muy pocos y simples (aunque una tabla dedicada es más probable para los mensajes de chat).

### 4.4 Activos JavaScript (`views/js/`)

El módulo se basa en JavaScript para su funcionalidad AJAX y actualizaciones dinámicas.

- `js/advajax.js`
  - **Alcance**: Front-office.
  - **Detalles**: Este archivo probablemente contiene una utilidad AJAX genérica o funciones envoltorio utilizadas por el módulo. Podría proporcionar compatibilidad entre navegadores para solicitudes AJAX o simplificar el proceso de envío y recepción de datos desde los controladores frontales. Podría ser una implementación personalizada o una biblioteca ligera.
- `js/script.js`
  - **Alcance**: Front-office.
  - **Detalles**: Este es el archivo JavaScript principal para la lógica del front-end del Shoutbox.
    - **Escuchadores de Eventos**: Se enlaza a los eventos de envío de formularios para publicar nuevos mensajes, y potencialmente a los eventos de clic para acciones como borrar mensajes (si se exponen al front-end).
    - **Llamadas AJAX**: Inicia solicitudes AJAX a `ajaxload.php` para actualizar mensajes en el intervalo especificado y a `insert.php` para enviar nuevos mensajes.
    - **Manipulación del DOM**: Actualiza la visualización del Shoutbox con nuevos mensajes, se desplaza hasta la parte inferior del chat y maneja el borrado del campo de entrada.
    - **Temporizadores**: Configura `setInterval` para la carga periódica de mensajes basada en la configuración de "Intervalo de Actualización".

### 4.5 Hojas de Estilo CSS (`views/css/`)

El módulo no lista explícitamente ningún archivo CSS personalizado en el directorio `views/css/`. Esto sugiere que:

1. El módulo se basa en estilos en línea o estilos básicos predeterminados del navegador.
2. Podría estar diseñado para heredar el estilo directamente del tema activo de PrestaShop, requiriendo un CSS personalizado mínimo.
3. Cualquier estilo está incrustado directamente dentro del archivo `shoutbox.tpl` o el PHP del módulo principal.
   Los desarrolladores que deseen estilizar el Shoutbox deberán inspeccionar el HTML generado y agregar reglas CSS personalizadas a la hoja de estilos de su tema, apuntando a los ID y clases específicos utilizados por los elementos del Shoutbox.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de Hook (`views/templates/hook/`)**:
  - `shoutbox/shoutbox.tpl`
    - **Hook(s) Renderizado(s)**: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (o un hook similar de página de producto). El hook real depende de la configuración del comerciante en el Back Office.
    - **Salida de Bloque Visual**: Esta plantilla renderiza la estructura HTML completa del widget Shoutbox. Esto incluye:
      - El contenedor principal para el cuadro de chat.
      - El título (por ejemplo, "Chat Comunitario").
      - El área donde se muestran los mensajes (un div desplazable).
      - El campo de entrada para escribir nuevos mensajes.
      - El botón "Enviar".
      - Renderizado condicional para las capacidades de publicación de invitados.
      - También incluirá el JavaScript necesario y, potencialmente, CSS en línea.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo no declara explícitamente un `ObjectModel` personalizado o un archivo SQL. El almacenamiento de mensajes probablemente se maneja directamente a través de `Db::getInstance()` en el archivo principal del módulo o en los controladores frontales. Un patrón común para dichos módulos es crear una tabla como `ps_shoutbox_messages` con campos como `id_shoutbox_message`, `id_customer`, `customer_name`, `message_content`, `date_add`, `ip_address`, `approved`.
  - **Registros de Configuración**: La configuración del módulo (por ejemplo, `SHOUTBOX_ENABLED`, `SHOUTBOX_TITLE`, `SHOUTBOX_NUM_MESSAGES`, `SHOUTBOX_REFRESH_INTERVAL`, `SHOUTBOX_ALLOW_GUEST`, `SHOUTBOX_MODERATION`, `SHOUTBOX_HOOK`) se almacena en la tabla `ps_configuration`.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Renderiza contenido en la sección `<head>` del HTML o en la parte superior del `<body>`. | Se utiliza para inyectar archivos CSS, JavaScript o el propio widget Shoutbox si está configurado para mostrarse en la cabecera. |
| `displayLeftColumn` | Renderiza contenido en la barra lateral izquierda de la tienda. | Hook común para mostrar el widget Shoutbox como un elemento de la barra lateral. |
| `displayRightColumn` | Renderiza contenido en la barra lateral derecha de la tienda. | Hook común para mostrar el widget Shoutbox como un elemento de la barra lateral. |
| `displayFooter` | Renderiza contenido en la sección del pie de página de la tienda. | Se utiliza para mostrar el widget Shoutbox en la parte inferior de la página. |
| `displayProductButtons` (o un hook similar de página de producto) | Renderiza contenido en la página del producto, a menudo cerca del botón de añadir al carrito o la descripción del producto. | Se utiliza para mostrar el widget Shoutbox específicamente en las páginas de productos para discusiones relacionadas con el producto. |
| `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador frontal establece sus medios (CSS/JS). | Se utiliza para registrar JavaScript específico del módulo (`advajax.js`, `script.js`) y cualquier posible archivo CSS que se cargará en el front office. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo Shoutbox, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte dedicado está listo para ayudarle con cualquier problema o pregunta que pueda tener.

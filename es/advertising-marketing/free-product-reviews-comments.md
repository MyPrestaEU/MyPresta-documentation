---
title: "Reseñas (comentarios) de productos gratuitas - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Reseñas (comentarios) de productos gratuitas' de MyPresta.eu."
sidebar:
  label: "Reseñas (comentarios) de productos gratuitas"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Free product reviews (comments) en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/free-product-reviews-comments.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/free-product-reviews-comments/)
>
> ---


# Reseñas (comentarios) de productos gratuitas

## 1. Requisitos y compatibilidad
Este módulo está diseñado para una amplia compatibilidad con las versiones modernas de PrestaShop y los entornos de alojamiento estándar.

-   **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilidad con PHP**: PHP 7.1 - 8.5
-   **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en cualquier entorno de alojamiento moderno compatible con PrestaShop. No se necesitan configuraciones de servidor inusuales o especializadas.

## 2. Recorrido completo por la configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Después de la instalación, al hacer clic en "Configurar" accederá a la pantalla de configuración principal del módulo "Reseñas (comentarios) de productos gratuitas". Aquí es donde controla cómo se comportan y aparecen las reseñas en su tienda.

#### Ajustes generales

-   **Activar reseñas:**
    *   **Qué hace este ajuste:** Este es el interruptor maestro para todo el sistema de reseñas.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está activado:* La sección de reseñas aparecerá en las páginas de productos, y los clientes podrán leer y enviar reseñas.
        *   *Cuando está desactivado:* La sección de reseñas se ocultará de las páginas de productos, y no se podrán enviar ni ver nuevas reseñas.
    *   **Valor recomendado:** SÍ
    *   **Escenario/ejemplo de comerciante:** Active esto para empezar a recopilar y mostrar los comentarios de los clientes inmediatamente después de la instalación.

-   **Las reseñas deben ser aprobadas por un empleado:**
    *   **Qué hace este ajuste:** Determina si las reseñas se publican automáticamente o requieren la aprobación manual de un administrador de la tienda.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está activado:* Todas las reseñas enviadas entrarán en un estado "pendiente" y no serán visibles en el front office hasta que un administrador las apruebe manualmente en la sección de gestión de reseñas del módulo. Esto le permite filtrar el spam, el contenido inapropiado o las reseñas que no cumplen sus directrices.
        *   *Cuando está desactivado:* Las reseñas se publican instantáneamente tras su envío, sin ninguna intervención humana.
    *   **Valor recomendado:** SÍ (especialmente para tiendas nuevas o para mantener el control de calidad)
    *   **Escenario/ejemplo de comerciante:** Si desea asegurarse de que todas las reseñas sean apropiadas y constructivas antes de que se publiquen, active esto. Esto es crucial para mantener la imagen de su marca y evitar el spam.

-   **Permitir reseñas de invitados:**
    *   **Qué hace este ajuste:** Controla si los visitantes no registrados (invitados) pueden enviar reseñas.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está activado:* Cualquier visitante de la página de su producto puede enviar una reseña, incluso si no tiene una cuenta o no ha iniciado sesión. Normalmente se les pedirá un nombre y una dirección de correo electrónico.
        *   *Cuando está desactivado:* Solo los clientes que han iniciado sesión en su cuenta de PrestaShop pueden enviar reseñas.
    *   **Valor recomendado:** SÍ (para fomentar más reseñas) o NO (para asegurar que las reseñas provengan de clientes reales).
    *   **Escenario/ejemplo de comerciante:** Si desea maximizar el número de reseñas, incluso de navegadores ocasionales, active las reseñas de invitados. Si prefiere recopilar reseñas solo de clientes verificados que le han comprado, desactive esto.

-   **Tiempo mínimo entre 2 reseñas del mismo usuario (en segundos):**
    *   **Qué hace este ajuste:** Establece un período de enfriamiento para evitar que un mismo usuario envíe varias reseñas en rápida sucesión para el mismo producto.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando se establece un valor (por ejemplo, 3600 para 1 hora):* Un usuario debe esperar al menos esta cantidad de segundos después de enviar una reseña antes de poder enviar otra reseña para el mismo producto.
        *   *Cuando se establece en 0:* No hay límite de tiempo, y los usuarios pueden enviar reseñas con la frecuencia que deseen.
    *   **Valor recomendado:** 3600 (1 hora) u 86400 (24 horas) para evitar el spam.
    *   **Escenario/ejemplo de comerciante:** Para evitar que un solo cliente inunde un producto con múltiples reseñas, establezca esto en una duración razonable como 3600 segundos (1 hora).

-   **Mostrar reseñas en la página del producto:**
    *   **Qué hace este ajuste:** Determina si la lista de reseñas y el formulario de envío se muestran directamente en la página del producto.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está activado:* La sección de reseñas será visible en la página del producto, permitiendo a los clientes leer y escribir reseñas.
        *   *Cuando está desactivado:* La sección de reseñas se ocultará de la página del producto. Esto podría usarse si prefiere enlazar a una página de reseñas separada o gestionar las reseñas de otra manera.
    *   **Valor recomendado:** SÍ
    *   **Escenario/ejemplo de comerciante:** Para que las reseñas sean fácilmente accesibles para los compradores que navegan por sus productos, mantenga esto activado.

-   **Número de reseñas por página:**
    *   **Qué hace este ajuste:** Controla cuántas reseñas se muestran en una sola página dentro de la lista de reseñas antes de aplicar la paginación.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando se establece un valor (por ejemplo, 5):* Solo se mostrarán 5 reseñas a la vez, con botones "Siguiente" y "Anterior" o números de página para navegar por el resto.
        *   *Cuando se establece un número muy alto:* Todas las reseñas podrían cargarse en una página, lo que puede afectar la velocidad de carga de la página si hay muchas reseñas.
    *   **Valor recomendado:** 5-10
    *   **Escenario/ejemplo de comerciante:** Si un producto tiene muchas reseñas, establecer esto en 5 o 10 mantendrá la página del producto ordenada y se cargará rápidamente, al tiempo que permitirá a los clientes navegar por todos los comentarios.

#### Gestión de criterios de reseña

Esta sección le permite definir criterios específicos (por ejemplo, "Calidad", "Precio", "Características") que los clientes pueden valorar además de la valoración general del producto.

-   **Añadir nuevo criterio:**
    *   **Qué hace:** Le permite crear un nuevo aspecto específico de un producto que los clientes pueden valorar (por ejemplo, "Relación calidad-precio", "Facilidad de uso", "Durabilidad").
    *   **Efecto de cambiar este ajuste:** Cuando añade un criterio, aparecerá como una opción de valoración adicional en el formulario de envío de reseñas en la página del producto. Los clientes podrán dar una valoración por estrellas para cada criterio que defina.
    *   **Valor recomendado:** Añada criterios relevantes para sus productos.
    *   **Escenario/ejemplo de comerciante:** Para una tienda de electrónica, podría añadir criterios como "Rendimiento", "Duración de la batería" y "Diseño". Para una tienda de ropa, "Ajuste", "Calidad del material" y "Estilo".

-   **Lista de criterios existentes:**
    *   **Qué hace:** Muestra una tabla de todos los criterios que ha añadido previamente, junto con opciones para editarlos o eliminarlos.
    *   **Efecto de cambiar este ajuste:** Puede modificar el nombre de un criterio (por ejemplo, cambiar "Calidad" a "Calidad del producto") o eliminar un criterio si ya no es relevante. La eliminación de un criterio lo eliminará de futuros envíos de reseñas, pero las reseñas existentes que utilizaron ese criterio aún podrían mostrar sus valoraciones para él (dependiendo de la implementación del módulo).
    *   **Valor recomendado:** Mantenga su lista de criterios actualizada y relevante.
    *   **Escenario/ejemplo de comerciante:** Si introduce una nueva línea de productos con características únicas, podría añadir un nuevo criterio. Si un criterio se vuelve redundante, puede eliminarlo.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
|---|---|---|---|
| Configuración del módulo | Activar reseñas | SÍ | Interruptor maestro para el sistema de reseñas. |
| Configuración del módulo | Las reseñas deben ser aprobadas por un empleado | SÍ | Controla la aprobación manual de reseñas para evitar spam/contenido inapropiado. |
| Configuración del módulo | Permitir reseñas de invitados | SÍ | Permite a los usuarios no registrados enviar reseñas. |
| Configuración del módulo | Tiempo mínimo entre 2 reseñas del mismo usuario (en segundos) | 3600 (1 hora) | Evita el envío masivo de reseñas por parte de un solo usuario. |
| Configuración del módulo | Mostrar reseñas en la página del producto | SÍ | Muestra u oculta la sección de reseñas en las páginas de productos. |
| Configuración del módulo | Número de reseñas por página | 5-10 | Controla la paginación de la lista de reseñas en las páginas de productos. |
| Configuración del módulo | Añadir nuevo criterio | N/A | Crea aspectos de valoración específicos (por ejemplo, "Calidad", "Precio"). |
| Configuración del módulo | Lista de criterios existentes | N/A | Gestiona (edita/elimina) los criterios de reseña personalizados. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis reseñas no aparecen en la página del producto después de enviarlas.**
R: Compruebe si "Las reseñas deben ser aprobadas por un empleado" está activado en la configuración del módulo. Si es así, debe aprobarlas manualmente en la interfaz de administración del módulo (normalmente se encuentra en la página de configuración del módulo, donde verá una lista de reseñas). Una vez aprobadas, aparecerán en el front office.

**P2: La sección de reseñas se ve extraña o no se ajusta al diseño de mi tema.**
R: Esto suele ser un conflicto de CSS con su tema personalizado de PrestaShop.
    *   **Borrar caché:** Primero, intente borrar la caché de PrestaShop en **Parámetros avanzados > Rendimiento**.
    *   **Sobreescrituras del tema:** Su tema podría tener su propio estilo para los elementos de reseña o podría carecer de un estilo específico para este módulo. Es posible que necesite un webmaster para inspeccionar el CSS y aplicar estilos personalizados para que se integre sin problemas. El módulo proporciona sus propios archivos CSS (`myprestacomments.css`, etc.), pero los estilos de su tema podrían anularlos.

**P3: Los clientes se quejan de que no pueden enviar reseñas, o el formulario no aparece.**
R:
    *   **Compruebe "Activar reseñas":** Asegúrese de que el interruptor principal en la configuración del módulo esté configurado en SÍ.
    *   **Compruebe "Mostrar reseñas en la página del producto":** Asegúrese de que esto también esté activado.
    *   **Reseñas de invitados:** Si los usuarios no registrados no pueden enviar, compruebe "Permitir reseñas de invitados". Si está desactivado, solo los clientes registrados pueden enviar.
    *   **Tiempo mínimo entre reseñas:** Si un usuario específico no puede enviar, es posible que esté alcanzando el límite de "Tiempo mínimo entre 2 reseñas".

**P4: ¿Cómo traduzco el texto del módulo a otros idiomas?**
R: Puede traducir el texto del módulo directamente dentro de PrestaShop:
    1.  Vaya a **Internacional > Traducciones**.
    2.  Seleccione "Traducciones de módulos instalados" para el "Tipo de traducción".
    3.  Elija su tema.
    4.  Seleccione el idioma que desea traducir.
    5.  Busque "Reseñas (comentarios) de productos gratuitas" en la lista de módulos y haga clic en "Modificar". A continuación, podrá editar todas las cadenas traducibles.

**P5: Quiero eliminar una reseña que es inapropiada o spam.**
R: Navegue a la página de configuración del módulo en el Back Office. Debería ver una lista de todas las reseñas enviadas. Desde allí, normalmente puede "Eliminar" o "Desaprobar" reseñas. Si tiene "Las reseñas deben ser aprobadas por un empleado" activado, simplemente puede optar por no aprobarla.

## 4. Guía para desarrolladores y webmasters (arquitectura técnica y mapa de código)
Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura
El módulo "Reseñas (comentarios) de productos gratuitas" (`myprestacomments`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando `ModuleFrontController` para las interacciones del front office y `Module` para su configuración principal y gestión de hooks. Utiliza una tabla de base de datos personalizada para almacenar los datos de las reseñas y se basa en plantillas Smarty para renderizar tanto las pantallas de reseñas del front office como los formularios de configuración del back office. El módulo se integra con el sistema de hooks de PrestaShop para inyectar su contenido en las páginas de productos.

### 4.2 Controladores (`controllers/`)

-   **Controladores del Front Office**:
    *   `controllers/front/default.php`
        *   **Nombre de la clase y clase padre**: `MyPrestaCommentsDefaultModuleFrontController` que extiende `ModuleFrontController`
        *   **Responsabilidad**: Este controlador probablemente maneja la visualización inicial de las reseñas en la página del producto o sirve como respaldo para acciones generales relacionadas con las reseñas. Normalmente, obtendría las reseñas de un producto dado y las pasaría a la plantilla Smarty.
    *   `controllers/front/feedback.php`
        *   **Nombre de la clase y clase padre**: `MyPrestaCommentsFeedbackModuleFrontController` que extiende `ModuleFrontController`
        *   **Responsabilidad**: Este controlador está dedicado a manejar el envío de nuevas reseñas. Procesa las solicitudes POST del formulario de reseña, valida la entrada (valoración, comentario, criterios), verifica los permisos de reseña de invitados y los límites de tiempo, y luego guarda la reseña en la base de datos. También gestiona el estado de aprobación según la configuración del módulo.
    *   `controllers/front/index.php`
        *   **Nombre de la clase y clase padre**: `MyPrestaCommentsIndexModuleFrontController` que extiende `ModuleFrontController`
        *   **Responsabilidad**: Este controlador podría servir como un punto de entrada general o manejar solicitudes AJAX relacionadas con las reseñas, como cargar más reseñas a través de la paginación o manejar la funcionalidad de "reportar abuso".

-   **Controladores de administración del Back Office**:
    *   No se enumeran controladores de administración personalizados dedicados (`controllers/admin/`). Esto sugiere que la administración de reseñas (listado, aprobación, eliminación) se maneja directamente dentro del método `getContent()` del archivo principal del módulo (`index.php`) o a través de un `AdminController` estándar que el módulo extiende o con el que se integra. La presencia de las plantillas `list_action_approve.tpl` y `list_action_noabuse.tpl` indica fuertemente que la gestión de reseñas está integrada en una vista de lista estándar de PrestaShop, probablemente dentro de la propia página de configuración del módulo.

### 4.3 Clases y modelos principales (`classes/`)
No se enumeran clases personalizadas en el directorio `classes/`. Esto implica que el módulo podría estar utilizando un enfoque más directo para la interacción con la base de datos dentro de su archivo principal de módulo o controladores, o podría estar aprovechando los `ObjectModel`s existentes de PrestaShop si corresponde (aunque es poco probable para datos de reseñas personalizados). Es probable que la estructura de datos de las reseñas se gestione directamente dentro de `install.sql` y el `index.php` del módulo.

### 4.4 Activos JavaScript (`views/js/`)

-   `js/jquery.rating.pack.js`
    *   **Alcance**: Front Office
    *   **Descripción**: Un plugin de jQuery para crear widgets interactivos de valoración por estrellas. Maneja la visualización visual de las estrellas y captura la selección de valoración del usuario en el formulario de envío de reseñas.
-   `js/jquery.textareaCounter.plugin.js`
    *   **Alcance**: Front Office
    *   **Descripción**: Un plugin de jQuery para contar caracteres o palabras en un área de texto, a menudo utilizado para proporcionar retroalimentación en tiempo real a los usuarios sobre la longitud de su reseña.
-   `js/moderate.js`
    *   **Alcance**: Back Office
    *   **Descripción**: Este script probablemente maneja las acciones AJAX para moderar reseñas en el Back Office. Sería responsable de aprobar, desaprobar o eliminar reseñas sin una recarga completa de la página, interactuando con el `getContent()` del módulo o un controlador de administración oculto.
-   `js/myprestacomments.js`
    *   **Alcance**: Front Office
    *   **Descripción**: El JavaScript personalizado principal para el módulo. Orquesta la funcionalidad de reseñas del front office, incluyendo:
        *   Inicialización de `jquery.rating.pack.js` para las valoraciones por estrellas.
        *   Manejo del envío del formulario de reseña (potencialmente a través de AJAX).
        *   Visualización de mensajes de éxito o error.
        *   Gestión de la paginación o la funcionalidad de "cargar más" para las reseñas.
        *   Potencialmente, manejo de clics de "reportar abuso".
-   `js/productCriterion.js`
    *   **Alcance**: Back Office
    *   **Descripción**: Este script se utiliza en el Back Office para gestionar los criterios de reseña. Probablemente maneja la adición, edición y eliminación dinámica de campos de criterios en la página de configuración del módulo, posiblemente utilizando AJAX para actualizar la base de datos.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `myprestacomments.css`
    *   **Alcance**: Front Office y Back Office
    *   **Descripción**: La hoja de estilo principal del módulo, que contiene estilos generales para la sección de reseñas, las valoraciones por estrellas, los formularios de reseñas y, potencialmente, algunos estilos básicos del panel de administración.
    *   **Selectores clave**: `.myprestacomments_block`, `.myprestacomments_review_list`, `.myprestacomments_form`, `.star_content`, `.comment_item`, `.review_rating`.
-   `myprestacomments16.css`
    *   **Alcance**: Front Office y Back Office
    *   **Descripción**: Probablemente una hoja de estilo de compatibilidad para PrestaShop 1.6.x, que contiene anulaciones o ajustes específicos para la estructura de tema predeterminada de esa versión.
-   `myprestacomments24.css`
    *   **Alcance**: Front Office y Back Office
    *   **Descripción**: Probablemente una hoja de estilo de compatibilidad para PrestaShop 1.7.x u 8.x, que contiene anulaciones o ajustes específicos para la estructura de tema predeterminada de esas versiones (por ejemplo, tema Classic).
-   `myprestacomments32.css`
    *   **Alcance**: Front Office y Back Office
    *   **Descripción**: Probablemente una hoja de estilo de compatibilidad para PrestaShop 9.x, que contiene anulaciones o ajustes específicos para la estructura de tema predeterminada más reciente.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    *   `myprestacomments/mypresta_myprestacomments.tpl`
        *   **Hook**: Probablemente `displayProductButtons` o `displayProductExtraContent` (o hooks similares de la página de producto).
        *   **Salida**: Esta es la plantilla principal para mostrar el resumen de reseñas (valoración media, número de reseñas) y el botón/enlace "Escribir una reseña" en la página del producto. A menudo actúa como un envoltorio para la lista completa de reseñas y el formulario.
    *   `myprestacomments/mypresta_myprestacomments_reviews_list.tpl`
        *   **Hook**: Renderizado dentro de `mypresta_myprestacomments.tpl` o enganchado directamente si el módulo utiliza una pestaña separada.
        *   **Salida**: Muestra la lista real de reseñas individuales de clientes, incluyendo sus valoraciones, títulos, comentarios e información del revisor. También manejará la paginación.

-   **Plantillas de administración (`views/templates/admin/`)**:
    *   `myprestacomments/views/templates/admin/advert.tpl`
        *   **Salida**: Probablemente muestra un anuncio o mensaje promocional de MyPresta.eu dentro de la página de configuración del módulo.
    *   `myprestacomments/views/templates/admin/list_action_approve.tpl`
        *   **Salida**: Un fragmento de plantilla para un botón o enlace de acción "Aprobar", utilizado dentro de una lista de reseñas pendientes en el Back Office.
    *   `myprestacomments/views/templates/admin/list_action_noabuse.tpl`
        *   **Salida**: Un fragmento de plantilla para un botón o enlace de acción "Marcar como no abusivo", utilizado dentro de una lista de reseñas reportadas en el Back Office.
    *   `myprestacomments/views/templates/admin/_configure/helpers/form/form.tpl`
        *   **Salida**: Esta es una anulación de plantilla de ayuda estándar de PrestaShop, utilizada para renderizar el formulario de configuración del módulo (ajustes generales, gestión de criterios) en el Back Office. Define el diseño y los campos de entrada para el método `getContent()`.
    *   `myprestacomments/views/templates/admin/_configure/helpers/list/list_content.tpl`
        *   **Salida**: Otra anulación de plantilla de ayuda estándar de PrestaShop, utilizada para renderizar la lista de reseñas (o criterios) en el Back Office, incluyendo columnas para los detalles de la reseña, el estado y los botones de acción (aprobar, eliminar).

-   **Plantillas del Front Office (`views/templates/front/`)**:
    *   `myprestacomments/views/templates/front/feedback.tpl`
        *   **Salida**: La plantilla para el formulario de envío de reseñas. Esto incluye la entrada de valoración por estrellas, los campos de texto para el título y el comentario, y potencialmente campos para las valoraciones de criterios personalizados. Se renderiza cuando un cliente hace clic en "Escribir una reseña".

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:
    *   `myprestacomments/install.sql`: Este archivo contiene las sentencias SQL ejecutadas durante la instalación del módulo. Definirá al menos una tabla personalizada:
        *   `ps_myprestacomments_reviews`: Almacena los datos reales de la reseña (ID de producto, ID de cliente, valoración, título, comentario, fecha, estado de aprobación, estado de abuso).
        *   `ps_myprestacomments_criteria`: Almacena los criterios de reseña personalizados definidos por el comerciante (por ejemplo, "Calidad", "Precio").
        *   `ps_myprestacomments_review_criterion`: Una tabla de enlace si las reseñas pueden valorar múltiples criterios.

-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
|---|---|---|
| `displayHeader` | En la sección `<head>` de cada página. | Para incluir los archivos CSS y JS del módulo globalmente o condicionalmente. |
| `displayProductExtraContent` | En la página del producto, normalmente debajo de la descripción principal del producto o en una pestaña. | Para mostrar el resumen de reseñas, la lista de reseñas y el formulario "Escribir una reseña". |
| `displayProductButtons` | En la página del producto, cerca del botón Añadir al carrito. | Para mostrar un enlace o botón rápido a la sección de reseñas. |
| `displayFooter` | En el pie de página de cada página. | Menos común, pero podría usarse para un enlace general a reseñas o contenido específico del módulo. |
| `displayLeftColumn` / `displayRightColumn` | En la barra lateral izquierda o derecha. | Podría usarse para mostrar un bloque de reseñas recientes o un resumen de reseñas. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Potencialmente utilizado para enviar un correo electrónico al cliente solicitando una reseña de los productos comprados. |
| `actionProductUpdate` | Después de que un producto se actualiza en el Back Office. | Para borrar la caché relacionada con las reseñas de productos si es necesario. |
| `actionObjectProductAddAfter` / `actionObjectProductUpdateAfter` | Después de que un producto se añade o se actualiza. | Para garantizar la integridad de los datos de las reseñas o la invalidación de la caché. |

## 5. Soporte oficial y actualizaciones
Para actualizaciones oficiales, soporte técnico y cualquier otra asistencia con el módulo "Reseñas (comentarios) de productos gratuitas", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con problemas relacionados con el módulo y garantizar que su tienda funcione sin problemas.
"""

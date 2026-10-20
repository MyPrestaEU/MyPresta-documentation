---
title: "Block Search Pro - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Block Search Pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "Block Search Pro - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Block Search Pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/block-search-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/block-search-pro/)
>
> ---


# Block Search Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Por lo general, no se necesitan configuraciones de servidor especiales más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Block Search Pro)

Esta es la pantalla de configuración principal donde controla cómo se comporta y aparece el módulo Block Search Pro en su tienda.

#### 2.1.1 Ajustes Generales

**1. Habilitar búsqueda AJAX**

-   **Qué hace este ajuste:** Controla si los resultados de búsqueda aparecen instantáneamente a medida que el cliente escribe (AJAX) o si tienen que presionar Enter/hacer clic en el botón de búsqueda para ver los resultados.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* A medida que los clientes escriben en la barra de búsqueda, aparecerá una lista desplegable de productos coincidentes en tiempo real debajo del campo de búsqueda. Esto proporciona retroalimentación inmediata y acelera el proceso de búsqueda.
    -   *Cuando está deshabilitado (NO):* Los clientes deben escribir su consulta de búsqueda completa y luego presionar Enter o hacer clic en el botón de búsqueda para ser redirigidos a la página de resultados de búsqueda.
-   **Valor recomendado:** SÍ. Esto mejora significativamente la experiencia del usuario al ofrecer gratificación instantánea y reducir los pasos para encontrar un producto.
-   **Escenario / ejemplo de comerciante:** Un cliente escribe "vestido" e inmediatamente ve aparecer sugerencias como "Vestido de Fiesta Rojo", "Vestido Maxi de Verano" y "Vestido de Cóctel Negro", lo que le permite hacer clic directamente en una página de producto sin esperar.

**2. Búsqueda instantánea**

-   **Qué hace este ajuste:** Similar a la búsqueda AJAX, esto se refiere específicamente a la visualización "instantánea" de los resultados de búsqueda en la propia página de resultados de búsqueda, actualizándose a medida que el usuario refina su consulta. (Nota: En muchas versiones modernas de PrestaShop, la "búsqueda AJAX" a menudo abarca el menú desplegable instantáneo, mientras que la "búsqueda instantánea" podría referirse al comportamiento en la página de resultados de búsqueda real).
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Si un cliente está en la página de resultados de búsqueda y modifica su consulta de búsqueda en la barra de búsqueda, los resultados de esa página se actualizarán instantáneamente sin una recarga completa de la página.
    -   *Cuando está deshabilitado (NO):* El cliente tendría que enviar la consulta de búsqueda modificada nuevamente para que la página de resultados se actualice.
-   **Valor recomendado:** SÍ. Esto proporciona una experiencia de búsqueda más dinámica y responsiva.
-   **Escenario / ejemplo de comerciante:** Un cliente busca "zapatos", llega a la página de resultados de búsqueda y luego escribe "rojo" en la barra de búsqueda de esa página. Con la búsqueda instantánea, los resultados se filtran inmediatamente para mostrar solo zapatos rojos.

**3. Permitir enviar búsqueda con entrada de palabra clave de búsqueda vacía**

-   **Qué hace este ajuste:** Determina si un cliente puede hacer clic en el botón de búsqueda o presionar Enter sin escribir ninguna palabra clave.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Si un cliente hace clic en buscar con una entrada vacía, será llevado a la página general de resultados de búsqueda, que podría mostrar todos los productos o un mensaje predeterminado según su tema. Esto a veces se puede usar para navegar por todos los productos.
    -   *Cuando está deshabilitado (NO):* El botón de búsqueda estará inactivo o mostrará un mensaje de error si el campo de entrada está vacío, lo que obliga al cliente a escribir una palabra clave antes de buscar.
-   **Valor recomendado:** NO. Generalmente, es mejor guiar a los clientes para que introduzcan una consulta para evitar confusiones o páginas de resultados de búsqueda vacías.
-   **Escenario / ejemplo de comerciante:** Si un cliente hace clic accidentalmente en buscar sin escribir, deshabilitar esto evita que aterrice en una página vacía potencialmente confusa.

**4. Longitud mínima de palabra (en caracteres)**

-   **Qué hace este ajuste:** Establece el número mínimo de caracteres que un cliente debe escribir antes de que la función de búsqueda (incluida la búsqueda AJAX/instantánea) comience a buscar resultados.
-   **Efecto de cambiar este ajuste:**
    -   *Establecido en 3:* Los clientes deben escribir al menos tres caracteres (por ejemplo, "roj") antes de que aparezcan sugerencias de búsqueda o se pueda enviar una búsqueda.
    -   *Establecido en 1:* Incluso un solo carácter (por ejemplo, "a") activará la búsqueda.
-   **Valor recomendado:** 3. Esto equilibra la capacidad de respuesta con la relevancia. Demasiado bajo (por ejemplo, 1-2 caracteres) puede generar demasiadas sugerencias irrelevantes, mientras que demasiado alto podría frustrar a los usuarios.
-   **Escenario / ejemplo de comerciante:** Si se establece en 3, escribir "za" no mostrará resultados, pero escribir "zap" comenzará a mostrar sugerencias para "zapatos", "zapatillas", etc.

#### 2.1.2 Opciones de Filtrado de Búsqueda

**5. Seleccionar categorías**

-   **Qué hace este ajuste:** Le permite restringir la búsqueda solo a categorías de productos específicas. El módulo solo devolverá resultados de las categorías que seleccione aquí.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se seleccionan categorías específicas:* La búsqueda solo buscará productos dentro de esas categorías elegidas. Los productos en categorías no seleccionadas no aparecerán en los resultados de búsqueda, incluso si coinciden con la palabra clave.
    -   *Cuando no se seleccionan categorías:* La búsqueda por defecto buscará en todas las categorías de su tienda.
-   **Valor recomendado:** Seleccione categorías si desea guiar a los clientes a tipos de productos específicos, o déjelo vacío si desea una búsqueda amplia.
-   **Escenario / ejemplo de comerciante:** Si vende ropa y electrónica, pero solo desea que la barra de búsqueda en la cabecera encuentre ropa, seleccionaría solo sus categorías de ropa aquí.

**6. Buscar en subcategorías**

-   **Qué hace este ajuste:** Esta opción funciona junto con "Seleccionar categorías". Determina si la búsqueda también debe incluir productos dentro de las subcategorías de las categorías padre seleccionadas.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Si selecciona "Electrónica" como categoría, la búsqueda también buscará dentro de "Portátiles", "Smartphones" y cualquier otra subcategoría de "Electrónica".
    -   *Cuando está deshabilitado (NO):* La búsqueda solo buscará productos asignados directamente a las categorías padre seleccionadas, ignorando sus subcategorías.
-   **Valor recomendado:** SÍ. La mayoría de los comerciantes desean que las búsquedas sean completas dentro de un árbol de categorías elegido.
-   **Escenario / ejemplo de comerciante:** Si selecciona "Ropa" y habilita "Buscar en subcategorías", una búsqueda de "camisa" encontrará camisas en "Camisetas de Hombre", "Blusas de Mujer", etc.

**7. Fabricantes**

-   **Qué hace este ajuste:** Le permite restringir la búsqueda solo a productos de fabricantes específicos.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se seleccionan fabricantes específicos:* La búsqueda solo devolverá productos fabricados por los fabricantes elegidos. Los productos de fabricantes no seleccionados no aparecerán.
    -   *Cuando no se seleccionan fabricantes:* La búsqueda por defecto buscará en todos los fabricantes de su tienda.
-   **Valor recomendado:** Seleccione fabricantes si desea ofrecer una búsqueda específica de marca, o déjelo vacío para una búsqueda general.
-   **Escenario / ejemplo de comerciante:** Si tiene un bloque de búsqueda dedicado a "Marcas Premium", podría seleccionar solo fabricantes de alta gama aquí.

#### 2.1.3 Ajustes de Visualización

**8. Tamaño del bloque de búsqueda**

-   **Qué hace este ajuste:** Controla el ancho visual del campo de entrada de búsqueda en píxeles.
-   **Efecto de cambiar este ajuste:**
    -   *Establecido en 280px:* La barra de búsqueda tendrá 280 píxeles de ancho.
    -   *Establecido en 100% (o déjelo vacío para detección automática):* La barra de búsqueda se adaptará al espacio disponible, a menudo llenando su contenedor.
-   **Valor recomendado:** Déjelo vacío para detección automática o configúrelo en un porcentaje (por ejemplo, 100%) para garantizar la capacidad de respuesta. Si necesita un ancho fijo por razones de diseño, especifique un valor en píxeles.
-   **Escenario / ejemplo de comerciante:** Si su tema tiene una cabecera muy estrecha, es posible que deba ajustar esto para asegurarse de que la barra de búsqueda encaje sin romper el diseño. Para la mayoría de los temas modernos, es mejor dejar que el tema maneje el ancho.

#### 2.1.4 Otros Ajustes

**9. Ajustes de Actualización en Vivo de MyPresta.eu (mypresta\_updates, update\_, updatev\_)**

-   **Qué hace este ajuste:** Estos son ajustes internos relacionados con el sistema de actualización de módulos de MyPresta.eu. Permiten que el módulo verifique y le notifique sobre nuevas versiones.
-   **Efecto de cambiar este ajuste:** Estos no son configurables por el usuario directamente a través de la interfaz, sino que son gestionados por el propio módulo. Asegurarse de que su tienda tenga acceso a Internet saliente permite que estas comprobaciones funcionen.
-   **Valor recomendado:** Estos son internos y no deben cambiarse manualmente.
-   **Escenario / ejemplo de comerciante:** Recibirá una notificación en su back office de PrestaShop si hay una nueva versión de Block Search Pro disponible, lo que garantiza que pueda mantener su módulo actualizado con las últimas características y correcciones de seguridad.

**10. PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**

-   **Qué hace este ajuste:** Estas son variables de configuración estándar de PrestaShop relacionadas con el idioma predeterminado de su tienda y si los empleados pueden cambiar el idioma de los formularios en el back office. El módulo las utiliza para asegurarse de que se muestre correctamente en el idioma activo del back office.
-   **Efecto de cambiar este ajuste:** Estos son ajustes globales de PrestaShop y no están directamente controlados por Block Search Pro. El módulo simplemente los lee para adaptar su visualización.
-   **Valor recomendado:** Gestionado por su configuración general de PrestaShop.
-   **Escenario / ejemplo de comerciante:** Si su back office está configurado en francés, las etiquetas de configuración del módulo aparecerán en francés (si hay traducciones disponibles).

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Habilitar búsqueda AJAX | SÍ | Muestra sugerencias de productos instantáneas a medida que el cliente escribe. |
| Configuración del Módulo | Búsqueda instantánea | SÍ | Actualiza la página de resultados de búsqueda instantáneamente al cambiar la consulta. |
| Configuración del Módulo | Permitir enviar búsqueda con entrada de palabra clave de búsqueda vacía | NO | Evita buscar con un campo de entrada vacío. |
| Configuración del Módulo | Longitud mínima de palabra (en caracteres) | 3 | Caracteres mínimos requeridos para activar la búsqueda. |
| Configuración del Módulo | Seleccionar categorías | Dejar vacío (busca en todas) | Restringe la búsqueda a las categorías elegidas. |
| Configuración del Módulo | Buscar en subcategorías | SÍ | Incluye subcategorías cuando se seleccionan categorías padre. |
| Configuración del Módulo | Fabricantes | Dejar vacío (busca en todos) | Restringe la búsqueda a los fabricantes elegidos. |
| Configuración del Módulo | Tamaño del bloque de búsqueda | Dejar vacío (detección automática) | Ancho visual del campo de entrada de búsqueda. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Mis resultados de búsqueda no muestran productos que sé que existen. ¿Qué pasa?**
R1: Verifique sus configuraciones de "Seleccionar categorías" y "Fabricantes" en la configuración del módulo. Si ha restringido la búsqueda a ciertas categorías o fabricantes, los productos fuera de esas selecciones no aparecerán. Además, asegúrese de que sus productos estén activos y visibles en las categorías seleccionadas.

**P2: La búsqueda instantánea (AJAX) no funciona, o las sugerencias desplegables no aparecen.**
R2:
\* **Habilitar búsqueda AJAX:** Asegúrese de que "Habilitar búsqueda AJAX" esté configurado en SÍ en la configuración del módulo.
\* **Longitud mínima de palabra:** Verifique "Longitud mínima de palabra". Si está configurado demasiado alto, las sugerencias no aparecerán hasta que se escriban suficientes caracteres.
\* **Borrar caché:** Vaya a **Parámetros Avanzados > Rendimiento** y borre la caché de su PrestaShop (caché de Smarty, caché del sistema de archivos).
\* **Conflictos de tema:** A veces, los temas personalizados u otros módulos pueden entrar en conflicto con la funcionalidad AJAX. Deshabilite temporalmente otros módulos o cambie al tema predeterminado de PrestaShop para diagnosticar.
\* **Errores de JavaScript:** Abra la consola de desarrollador de su navegador (F12) y busque cualquier error de JavaScript. Si ve errores, póngase en contacto con el soporte de MyPresta.eu.

**P3: El bloque de búsqueda se ve extraño o no encaja con mi tema.**
R3:
\* **Tamaño del bloque de búsqueda:** Ajuste la configuración de "Tamaño del bloque de búsqueda" en la configuración del módulo. Intente dejarlo vacío para la detección automática o configurarlo en un porcentaje (por ejemplo, 100%).
\* **Conflictos de CSS:** El CSS de su tema podría estar anulando los estilos del módulo. Esto generalmente requiere que un webmaster inspeccione el CSS.
\* **Ubicación del hook:** Asegúrese de que el módulo esté enganchado en una posición adecuada (por ejemplo, `displayTop`) que tenga suficiente espacio en su tema. Puede gestionar las posiciones de los módulos en **Diseño > Posiciones**.

**P4: ¿Cómo traduzco el texto del bloque de búsqueda (por ejemplo, "Buscar en nuestro catálogo")?**
R4:
\* Vaya a **Internacional > Traducciones** en su back office de PrestaShop.
\* Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione su idioma.
\* Busque el módulo "Block Search Pro" en la lista y podrá editar las cadenas de texto allí.

**P5: Quiero colocar el bloque de búsqueda en una ubicación diferente de mi sitio.**
R5:
\* Navegue a **Diseño > Posiciones** (o **Módulos > Posiciones** en versiones anteriores de PS).
\* Busque el módulo "Block Search Pro" en la lista de módulos.
\* Puede "trasplantar" (enganchar) el módulo a diferentes hooks disponibles como `displayHeader`, `displayTop`, `displayLeftColumn`, `displayRightColumn` o `displayNav`. Arrastre y suelte para cambiar el orden dentro de un hook.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica detallada del módulo Block Search Pro para desarrolladores y webmasters.

### 4.1 Resumen de la Arquitectura

El módulo Block Search Pro extiende la funcionalidad de búsqueda principal de PrestaShop anulando la clase `Search`, lo que le permite inyectar lógica de filtrado personalizada (categorías, fabricantes) en la consulta de búsqueda. Aprovecha los patrones MVC estándar de PrestaShop para su visualización en el front-office (hooks, plantillas) y la configuración en el back-office (método `getContent()` en el archivo principal del módulo). La funcionalidad AJAX se maneja a través de un archivo JavaScript dedicado que interactúa con el mecanismo de búsqueda principal de PrestaShop.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce controladores de administración de Front-Office o Back-Office personalizados. Su funcionalidad de front-office se maneja principalmente mediante la clase `Search` anulada y su visualización a través de los hooks del módulo. La configuración del back-office se gestiona directamente dentro del método `getContent()` del archivo del módulo `blocksearchpro.php`.

### 4.3 Clases y Modelos Principales (`classes/`)

-   **`blocksearchpro/override/classes/index.php`**:

    -   Este es un archivo `index.php` vacío estándar, típicamente colocado en directorios para evitar la lista de directorios. No tiene ningún impacto funcional en la lógica del módulo.
-   **`blocksearchpro/override/classes/Search.php`**:

    -   **Nombre de la clase**: `Search` (anula la clase `Search` principal)
    -   **Clase padre**: `SearchCore`
    -   **Responsabilidad**: Este es el archivo más crítico. Anula la clase `Search` predeterminada de PrestaShop, modificando específicamente el método `find()` (o métodos similares relacionados con la búsqueda) para incorporar la lógica de filtrado personalizada del módulo.
        -   Lee los valores de configuración (`bsp_cat_exc`, `bsp_subcat`, `bsp_cat`, `bsp_man`) de `ps_configuration`.
        -   Modifica la consulta SQL utilizada para la búsqueda de productos para incluir cláusulas `WHERE` que filtran por categorías y/o fabricantes seleccionados.
        -   Asegura que la búsqueda respete la configuración "Buscar en subcategorías" cuando se aplican filtros de categoría.
        -   Esta anulación es lo que permite que el módulo inyecte sus capacidades de filtrado directamente en el mecanismo de búsqueda principal de PrestaShop.

### 4.4 Recursos JavaScript (`views/js/`)

-   **`blocksearchpro/blocksearchpro.js`**:
    -   **Alcance**: Front-office.
    -   **Responsabilidad**: Este script mejora la experiencia del usuario para el bloque de búsqueda.
        -   Probablemente vincula escuchadores de eventos al campo de entrada de búsqueda (por ejemplo, `keyup`, `focus`, `blur`).
        -   Maneja las solicitudes AJAX para sugerencias de búsqueda instantánea, enviando el valor de entrada actual al punto final AJAX de búsqueda principal de PrestaShop.
        -   Procesa la respuesta JSON de la llamada AJAX y rellena dinámicamente la lista desplegable de sugerencias de productos debajo de la barra de búsqueda.
        -   Gestiona la visualización y ocultación de la lista de sugerencias, la navegación con el teclado dentro de las sugerencias y los eventos de clic en las sugerencias para redirigir a las páginas de productos.
        -   También puede manejar la lógica de "Permitir enviar búsqueda con entrada de palabra clave de búsqueda vacía" en el lado del cliente.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   **`blocksearchpro/blocksearchpro.css`**:
    -   **Alcance**: Estilo del cliente en el front-office.
    -   **Componentes de la interfaz de usuario principales y contenedores que estiliza**:
        -   El propio campo de entrada de búsqueda (`#search_query_top`, `.search_query`).
        -   El botón de búsqueda (`#search_button`, `.button-search`).
        -   El contenedor para las sugerencias de búsqueda AJAX (`.ac_results`, `.block_search_pro_results`).
        -   Elementos de sugerencia individuales dentro del menú desplegable.
        -   Garantiza la capacidad de respuesta para varios tamaños de pantalla.
    -   **Selectores de clase CSS clave que los desarrolladores pueden anular**:
        -   `.block_search_pro` (contenedor principal)
        -   `.search_query` (campo de entrada)
        -   `.button-search` (botón de envío)
        -   `.ac_results` (contenedor de resultados AJAX)
        -   `.ac_odd`, `.ac_even`, `.ac_over` (estilo para elementos de sugerencia y estados de hover)
        -   Los desarrolladores pueden anular estos estilos en el `custom.css` de su tema o creando un tema hijo.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   **`blocksearchpro/blocksearchpro-top.tpl`**:
        -   **Hook**: `displayTop`, `displayNav` (y potencialmente `displayHeader` dependiendo del tema).
        -   **Propósito**: Renderiza el campo de entrada de búsqueda y el botón, típicamente para la barra de búsqueda de la cabecera principal. Incluye la estructura HTML necesaria para el formulario de búsqueda y el contenedor para los resultados AJAX.
    -   **`blocksearchpro/blocksearchpro.tpl`**:
        -   **Hook**: `displayLeftColumn`, `displayRightColumn`.
        -   **Propósito**: Renderiza un bloque de búsqueda para las columnas laterales. Esta plantilla podría tener un diseño o estilo ligeramente diferente en comparación con la barra de búsqueda superior, optimizado para espacios de columna más estrechos. También incluye el formulario de búsqueda y el contenedor de resultados AJAX.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

-   **Tablas de la Base de Datos**:

    -   Este módulo no crea tablas SQL personalizadas.
    -   Almacena sus configuraciones en la tabla estándar `ps_configuration` de PrestaShop.
    -   Claves de configuración utilizadas: `mypresta_updates`, `update_`, `updatev_`, `PS_SEARCH_AJAX`, `bsp_cat_exc`, `PS_INSTANT_SEARCH`, `bsp_empty`, `PS_SEARCH_MINWORDLEN`, `bsp_subcat`, `bsp_cat`, `bsp_man`, `bsp_size`.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyecta recursos CSS (`blocksearchpro.css`) y JavaScript (`blocksearchpro.js`) para la funcionalidad del front-office. |
| `displayTop` | Típicamente en el área de la cabecera principal de la tienda. | Renderiza el bloque de búsqueda usando `blocksearchpro-top.tpl`. |
| `displayNav` | A menudo en la barra de navegación superior (encima de `displayTop`). | Renderiza el bloque de búsqueda usando `blocksearchpro-top.tpl`. |
| `displayLeftColumn` | En la barra lateral izquierda de las páginas que la tienen. | Renderiza el bloque de búsqueda usando `blocksearchpro.tpl`. |
| `displayRightColumn` | En la barra lateral derecha de las páginas que la tienen. | Renderiza el bloque de búsqueda usando `blocksearchpro.tpl`. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | (No utilizado directamente por este módulo para su funcionalidad de búsqueda principal, pero un hook común para otros módulos. No hay ninguna acción específica aquí para Block Search Pro). |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y asistencia adicional con el módulo Block Search Pro, visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está listo para ayudarle con cualquier problema o pregunta que pueda tener.

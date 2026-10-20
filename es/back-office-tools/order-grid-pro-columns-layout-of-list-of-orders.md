---
title: "Order Grid Pro - columnas y diseño de la lista de pedidos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Order Grid Pro - columnas y diseño de la lista de pedidos' de MyPresta.eu."
sidebar:
  label: "Order Grid Pro - columnas y diseño de la lista de pedidos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Order Grid Pro - columns & layout of list of orders en MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-grid-pro-columns-layout-of-list-of-orders.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/order-grid-pro-columns-layout-of-list-of-orders/)
>
> ---


# Order Grid Pro - columnas y diseño de la lista de pedidos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.7.x, 1.7.8.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página principal de configuración de Order Grid Pro. Esta página es donde define qué columnas aparecen en su lista de pedidos y su disposición.

La configuración se divide típicamente en varias pestañas o secciones, lo que le permite gestionar diferentes aspectos de la cuadrícula de pedidos.

**Configuración General / Visibilidad y Orden de Columnas:**
Este es el núcleo del módulo. Normalmente verá una lista de todas las columnas disponibles, tanto las columnas predeterminadas de PrestaShop como las nuevas añadidas por Order Grid Pro.

-   **Qué hace esta configuración:** Esta sección le permite elegir qué columnas son visibles en su lista de pedidos del Back Office y organizar su orden de visualización. Normalmente verá dos listas: "Columnas Disponibles" y "Columnas Activas" (o similar).
-   **Efecto de cambiar esta configuración:**
    -   *Mover una columna de "Disponibles" a "Activas":* La columna aparecerá en su lista de pedidos del Back Office.
    -   *Mover una columna de "Activas" a "Disponibles":* La columna se ocultará de su lista de pedidos del Back Office.
    -   *Arrastrar y soltar columnas dentro de "Columnas Activas":* Cambia el orden de visualización de izquierda a derecha de las columnas en su lista de pedidos.
-   **Valor recomendado:** Esto depende completamente de las necesidades de su equipo. Empiece por habilitar las columnas que consulta con frecuencia y ocultar las que nunca utiliza. Organícelas en un flujo lógico para sus tareas diarias.
-   **Escenario / ejemplo de comerciante:**
    -   **Gerente de Almacén:** Podría habilitar "Miniatura del Producto", "Peso del Producto", "Número de Seguimiento" y "Transportista" y colocarlas de forma destacada a la izquierda para un procesamiento rápido del envío. Podría ocultar "Correo Electrónico del Cliente" o "Método de Pago" si no son relevantes para su función.
    -   **Agente de Servicio al Cliente:** Priorizaría "Teléfono del Cliente", "Correo Electrónico del Cliente", "Fragmento del Hilo de Servicio al Cliente" y "Mensaje del Pedido" para abordar rápidamente las consultas sin abrir cada pedido.
    -   **Departamento de Finanzas:** Podría centrarse en "Método de Pago", "ISO de Moneda", "Total Pagado" y "Reglas del Carrito" para verificar transacciones y descuentos.

**Opciones de Columna Específicas (Ejemplos de nuevas columnas que puede habilitar):**

-   **Teléfono del Cliente:**
    -   **Qué hace esta configuración:** Muestra el número de teléfono del cliente directamente en la lista de pedidos.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Aparecen los números de teléfono, lo que facilita llamar a los clientes sin navegar a los detalles de su pedido.
        -   *Cuando está deshabilitado:* Los números de teléfono están ocultos.
    -   **Valor recomendado:** SÍ, si su equipo de servicio al cliente o de envío necesita contactar con frecuencia a los clientes.
    -   **Escenario / ejemplo de comerciante:** Un agente de servicio al cliente puede llamar rápidamente a un cliente sobre un problema de entrega directamente desde la lista de pedidos.
-   **Número de Seguimiento:**
    -   **Qué hace esta configuración:** Muestra el número de seguimiento asociado con el pedido.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Los números de seguimiento son visibles, lo que permite copiar y pegar rápidamente para actualizaciones de seguimiento.
        -   *Cuando está deshabilitado:* Los números de seguimiento están ocultos.
    -   **Valor recomendado:** SÍ, esencial para los equipos de almacén y servicio al cliente.
    -   **Escenario / ejemplo de comerciante:** El personal del almacén puede verificar rápidamente si se ha añadido un número de seguimiento antes del envío, o el servicio al cliente puede proporcionárselo a un cliente.
-   **Miniatura del Producto de Primera Línea:**
    -   **Qué hace esta configuración:** Muestra una pequeña imagen del primer producto del pedido.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Aparece una señal visual del contenido del pedido, lo que ayuda a una identificación rápida.
        -   *Cuando está deshabilitado:* No se muestra ninguna imagen del producto.
    -   **Valor recomendado:** SÍ, muy útil para la confirmación visual, especialmente para la preparación de pedidos en el almacén.
    -   **Escenario / ejemplo de comerciante:** El personal del almacén puede confirmar visualmente el tipo de producto en un pedido sin abrirlo, acelerando la preparación.
-   **Peso del Pedido:**
    -   **Qué hace esta configuración:** Muestra el peso total del pedido.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Se muestra el peso del pedido, útil para cálculos de envío o selección de transportista.
        -   *Cuando está deshabilitado:* El peso del pedido está oculto.
    -   **Valor recomendado:** SÍ, si trabaja con productos físicos y el peso es un factor en el envío.
    -   **Escenario / ejemplo de comerciante:** Los gerentes de envío pueden evaluar rápidamente los tamaños y pesos de los paquetes para envíos a granel.
-   **Fragmento del Hilo de Servicio al Cliente:**
    -   **Qué hace esta configuración:** Muestra un breve fragmento del último mensaje de servicio al cliente relacionado con el pedido.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Proporciona contexto inmediato sobre las comunicaciones recientes con el cliente.
        -   *Cuando está deshabilitado:* No se muestra ningún fragmento.
    -   **Valor recomendado:** SÍ, invaluable para los equipos de servicio al cliente.
    -   **Escenario / ejemplo de comerciante:** Un agente de servicio al cliente puede ver si un cliente ha preguntado recientemente sobre un pedido sin abrir el hilo completo.
-   **ISO de Moneda:**
    -   **Qué hace esta configuración:** Muestra el código ISO de la moneda utilizada para el pedido (por ejemplo, EUR, USD).
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Útil para tiendas internacionales para identificar rápidamente la moneda.
        -   *Cuando está deshabilitado:* El ISO de la moneda está oculto.
    -   **Valor recomendado:** SÍ, si opera una tienda multi-moneda.
    -   **Escenario / ejemplo de comerciante:** El personal de finanzas puede ordenar o filtrar rápidamente los pedidos por moneda para la conciliación.
-   **Reglas de Carrito (Descuentos) Aplicadas:**
    -   **Qué hace esta configuración:** Indica si se aplicaron reglas de carrito (descuentos) al pedido.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Proporciona una visión general rápida de los pedidos con descuento.
        -   *Cuando está deshabilitado:* La información sobre los descuentos aplicados está oculta.
    -   **Valor recomendado:** SÍ, para finanzas, marketing o servicio al cliente para comprender los precios.
    -   **Escenario / ejemplo de comerciante:** Marketing puede identificar rápidamente los pedidos que utilizaron un código de promoción específico.

**Guardar Cambios:**
Recuerde siempre hacer clic en el botón "Guardar" o "Actualizar" después de realizar cualquier cambio en sus selecciones de columnas o en su orden. El módulo guarda el orden de las columnas como JSON, asegurando que su diseño personalizado persista.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 AdminMyordergridproAjaxController (Back Office > Módulos > Configurar > Order Grid Pro)

Este controlador maneja principalmente las interacciones dinámicas en la página de configuración del módulo. No tiene un elemento de menú separado en la navegación de PrestaShop.

-   **Nombre de la pantalla y ubicación del menú:** Este controlador se activa cuando está en la página "Módulos > Gestor de Módulos > Order Grid Pro > Configurar". Procesa las solicitudes AJAX realizadas por el JavaScript en esa página.
-   **Acciones y configuraciones disponibles:** Gestiona el guardado y la carga de sus configuraciones de cuadrícula personalizadas (qué columnas son visibles y su orden). Cuando arrastra y suelta columnas o alterna su visibilidad en la página de configuración del módulo, este controlador recibe los datos y los guarda.
-   **Efecto de los cambios:** Cualquier cambio que realice en el diseño de las columnas en la página de configuración del módulo se envía a este controlador, que luego actualiza las preferencias almacenadas para su cuadrícula de pedidos. Esto asegura que cuando navegue a "Pedidos > Pedidos", se aplique su diseño personalizado.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Usted interactúa con este controlador indirectamente simplemente configurando el módulo en su página principal. No hay una "vista de gestión" directa para los comerciantes aquí; es el procesador de backend para sus opciones de configuración.

#### 2.2.2 index.php (myordergridpro/controllers/admin/index.php)

Este archivo es un marcador de posición estándar o punto de entrada para los controladores de administración dentro de un módulo, asegurando que se impida el acceso directo al directorio y que se respeten los mecanismos de seguridad de PrestaShop. No representa una pantalla distinta y configurable para el comerciante.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de Configuración del Módulo** | **Visibilidad y Orden de Columnas** | Varía según el rol | Selecciona qué columnas aparecen en la lista de pedidos del Back Office y su orden de visualización. Impacta directamente en la eficiencia del equipo. |
| | *Teléfono del Cliente* | SÍ | Muestra el número de teléfono del cliente para un contacto rápido. |
| | *Número de Seguimiento* | SÍ | Muestra el número de seguimiento del pedido para envío/soporte. |
| | *Miniatura del Producto de Primera Línea* | SÍ | Señal visual del primer producto del pedido. |
| | *Peso del Pedido* | SÍ (para productos físicos) | Muestra el peso total del pedido para el envío. |
| | *Fragmento del Hilo de Servicio al Cliente* | SÍ | Proporciona contexto sobre las comunicaciones recientes con el cliente. |
| | *ISO de Moneda* | SÍ (para multi-moneda) | Muestra el código de moneda para tiendas internacionales. |
| | *Reglas de Carrito Aplicadas* | SÍ | Indica si se utilizaron descuentos en el pedido. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: He configurado las columnas, pero no veo los cambios en la página de Pedidos.**
R:

1.  **Borrar Caché de PrestaShop:** Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. A veces, PrestaShop almacena en caché las configuraciones del módulo.
2.  **Caché del Navegador:** Intente borrar la caché de su navegador o abrir el Back Office en una ventana de incógnito/privada para asegurarse de que no está viendo una versión antigua en caché de la página.
3.  **Guardar Configuración:** Verifique que hizo clic en el botón "Guardar" o "Actualizar" en la página de configuración del módulo después de realizar sus cambios.

**P: Algunas columnas que habilité están vacías o muestran "N/A". ¿Por qué?**
R: Esto generalmente significa que los datos para esa columna específica no están disponibles para ese pedido en particular. Por ejemplo:

-   "Número de Seguimiento" estará vacío si no se ha añadido ningún número de seguimiento al pedido.
-   "Fragmento del Hilo de Servicio al Cliente" estará vacío si no hay mensajes de servicio al cliente para ese pedido.
-   "Peso del Pedido" podría estar vacío si los pesos de los productos no están definidos o si el pedido contiene solo productos virtuales.
    Este es un comportamiento normal e indica datos faltantes en lugar de un error del módulo.

**P: El arrastrar y soltar para reordenar columnas no funciona.**
R:

1.  **Conflicto de JavaScript:** Otro módulo o su tema podría tener un conflicto de JavaScript. Intente deshabilitar otros módulos instalados recientemente uno por uno para identificar al culpable.
2.  **Problema del Navegador:** Pruebe en un navegador diferente (Chrome, Firefox, Edge) para descartar un problema específico del navegador.
3.  **Borrar Caché:** Borre tanto la caché de PrestaShop como la del navegador como se describió anteriormente.

**P: ¿Este módulo ralentizará mi Back Office?**
R: El módulo está diseñado para usar los hooks oficiales de la cuadrícula de PrestaShop y evitar anulaciones del núcleo, lo que ayuda a mantener el rendimiento y la compatibilidad. Si bien agregar muchas columnas nuevas requiere que PrestaShop obtenga más datos, el impacto es generalmente mínimo. Si nota ralentizaciones significativas, considere reducir el número de columnas personalizadas altamente complejas que ha habilitado.

**P: ¿Es este módulo compatible con mi tema personalizado?**
R: Sí, este módulo funciona dentro del Back Office de PrestaShop, que utiliza su propio tema predeterminado (New Classic o similar). No afecta su tema de front office, por lo que no debería haber problemas de compatibilidad con temas de front office personalizados.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Order Grid Pro" extiende la funcionalidad de la lista de pedidos del Back Office de PrestaShop, apuntando específicamente al sistema de cuadrícula de Symfony introducido en PrestaShop 1.7.7+. Se adhiere a las mejores prácticas de desarrollo de módulos de PrestaShop utilizando hooks oficiales (`actionGet` y `actionSet` para definiciones de cuadrícula) en lugar de anulaciones directas del núcleo. Esto garantiza la compatibilidad y estabilidad de las actualizaciones. El módulo principalmente inyecta nuevas definiciones de columna y proveedores de datos en la cuadrícula de pedidos existente, y almacena las preferencias del usuario para la visibilidad y el orden de las columnas utilizando la configuración estándar de PrestaShop. Las llamadas AJAX manejan las actualizaciones dinámicas de estas preferencias.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front Office**: Ninguno. Este módulo es puramente de Back Office.
-   **Controladores de Administración del Back Office**:

    -   `controllers/admin/AdminMyordergridproAjaxController.php`
        -   **Nombre de la clase y clase padre**: `AdminMyordergridproAjaxController` extiende `ModuleAdminController`.
        -   **Responsabilidad**: Este controlador es responsable de manejar las solicitudes AJAX de la página de configuración del módulo. Procesa las solicitudes para guardar y cargar la configuración personalizada de la cuadrícula de pedidos (visibilidad y orden de las columnas). Típicamente recibe datos JSON que representan el diseño de cuadrícula deseado y los almacena en `Configuration::updateValue()`.
        -   **Rutas**: Responde a las llamadas AJAX realizadas a `index.php?controller=AdminMyordergridproAjax&token=...&ajax=1`.
    -   `controllers/admin/index.php`
        -   **Nombre de la clase y clase padre**: No es una clase, sino un archivo de seguridad.
        -   **Responsabilidad**: Este es un archivo `index.php` vacío estándar colocado en los directorios de controladores para evitar la lista de directorios y el acceso directo, mejorando la seguridad. Típicamente contiene `<?php header('Expires: Mon, 26 Jul 1997 05:00:00 GMT'); header('Last-Modified: '.gmdate('D, d M Y H:i:s').' GMT'); header('Cache-Control: no-store, no-cache, must-revalidate'); header('Cache-Control: post-check=0, pre-check=0', false); header('Pragma: no-cache'); header('Location: ../'); exit;`.

### 4.3 Clases y Modelos del Núcleo (`classes/`)

El módulo no parece definir clases `ObjectModel` personalizadas ni tablas de base de datos. Principalmente funciona extendiendo las definiciones de cuadrícula existentes de PrestaShop y almacenando datos de configuración en `ps_configuration`.

### 4.4 Activos JavaScript (`views/js/`)

-   `views/js/grid_pro.js`
    -   **Alcance**: Back office (página de lista de pedidos).
    -   **Descripción**: Este script probablemente contiene la lógica central para manipular la cuadrícula de Symfony de PrestaShop en la página "Pedidos > Pedidos". Sería responsable de:
        -   Leer la configuración de columnas guardada de `Configuration::get()`.
        -   Añadir/eliminar columnas dinámicamente a la cuadrícula basándose en la configuración.
        -   Aplicar el orden personalizado de las columnas.
        -   Potencialmente manejar actualizaciones en vivo o lógica de renderizado de columnas específica.
        -   Vincularse a los eventos de la cuadrícula de PrestaShop (por ejemplo, `prestashop.on('grid.loaded', ...)`).
-   `views/js/order_grid_admin.js`
    -   **Alcance**: Back office (página de configuración del módulo).
    -   **Descripción**: Este script se utiliza principalmente en la página de configuración del módulo (`getContent()`). Maneja la interfaz de usuario para seleccionar y ordenar columnas. Esto incluye:
        -   Implementar la funcionalidad de arrastrar y soltar para reordenar columnas.
        -   Gestionar las listas de "Columnas Disponibles" y "Columnas Activas".
        -   Vincular oyentes de eventos a interruptores/casillas de verificación para la visibilidad de las columnas.
        -   Realizar llamadas AJAX a `AdminMyordergridproAjaxController.php` para guardar la configuración actualizada.
-   `views/js/order_list_live_status.js`
    -   **Alcance**: Back office (página de lista de pedidos).
    -   **Descripción**: Este script probablemente proporciona funcionalidad para actualizaciones en vivo o elementos interactivos directamente dentro de la lista de pedidos. Esto podría incluir:
        -   Actualizaciones de estado basadas en AJAX para pedidos sin recargar la página.
        -   Tooltips o popovers para información adicional en columnas específicas.
        -   Potencialmente mejorar los desplegables de cambio de estado predeterminados o añadir acciones rápidas personalizadas.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `views/css/order_grid_admin.css`
    -   **Alcance**: Back office (página de configuración del módulo y potencialmente página de lista de pedidos).
    -   **Descripción**: Esta hoja de estilo proporciona el estilo visual para la interfaz de configuración del módulo, asegurando que los elementos de arrastrar y soltar y las listas de columnas se presenten claramente. También puede incluir pequeños ajustes de estilo para las nuevas columnas introducidas en la lista de pedidos real para asegurar una alineación y legibilidad adecuadas dentro del tema del Back Office de PrestaShop.
    -   **Selectores de clase CSS clave**: Probablemente apunta a IDs o clases específicas dentro de la plantilla `getContent()` del módulo, y potencialmente a nuevas clases de columna inyectadas en la cuadrícula.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

La información del módulo indica que no se encontraron archivos `.tpl` explícitos en `views/templates/`. Esto sugiere que la interfaz de configuración del módulo probablemente se renderiza directamente dentro del método `getContent()` del archivo principal del módulo (`index.php`) utilizando PHP para generar el HTML, o inyecta contenido dinámicamente en las plantillas de cuadrícula existentes de PrestaShop a través de hooks.

Si hubiera plantillas presentes, típicamente serían:

-   **Plantillas de hook (`views/templates/hook/`)**: Para renderizar nuevo contenido de columna dentro de las celdas de la cuadrícula.
-   **Plantillas de administración (`views/templates/admin/`)**: Para el formulario de configuración del módulo.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:
    -   El módulo no crea tablas SQL personalizadas.
    -   La configuración (por ejemplo, la cadena JSON que representa el orden y la visibilidad de las columnas) se almacena en la tabla `ps_configuration` utilizando claves como `MYORDERGRIDPRO_CONFIG` o similar.
-   **Tabla de Hooks Registrados**:
    El módulo se basa principalmente en los hooks de la cuadrícula de Symfony de PrestaShop para su funcionalidad.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionGet` y `actionSet` (para definiciones de cuadrícula) | Cuando la cuadrícula de pedidos se está definiendo y renderizando en el Back Office. | Estos son los hooks principales utilizados para inyectar nuevas definiciones de columna y proveedores de datos en la cuadrícula de pedidos existente de PrestaShop. `actionGet` permite al módulo recuperar la definición de cuadrícula actual, y `actionSet` le permite modificar o añadir nuevas columnas antes de que se renderice la cuadrícula. |
| `displayBackOfficeHeader` | Ejecutado en la sección `<head>` de cada página del Back Office. | Se utiliza para incluir activos CSS y JavaScript (`order_grid_admin.css`, `grid_pro.js`, `order_grid_admin.js`, `order_list_live_status.js`) específicamente para el Back Office, asegurando que se carguen cuando sea necesario. |
| `displayAdminOrderListToolbar` (o similar) | Renderiza contenido en el área de la barra de herramientas de la lista de pedidos. | Potencialmente utilizado para añadir botones de acción rápida o filtros relacionados con la funcionalidad del módulo. |
| `actionAdminOrdersListingFieldsModifier` (o similar) | Modifica los campos/columnas disponibles en la consulta de listado de pedidos. | Permite al módulo añadir nuevos campos a la consulta SQL que obtiene los datos del pedido, permitiendo la visualización de datos de columnas personalizadas. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para "Order Grid Pro - columnas y diseño de la lista de pedidos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo se dedica a garantizar que su módulo funcione perfectamente y le ayude a maximizar la eficiencia de su tienda PrestaShop.
"""

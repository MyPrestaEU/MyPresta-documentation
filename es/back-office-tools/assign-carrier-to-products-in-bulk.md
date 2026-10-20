---
title: "Asignar transportista a productos en masa - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Asignar transportista a productos en masa' de MyPresta.eu."
sidebar:
  label: "Asignar transportista a productos en masa - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Assign carrier to products in bulk en MyPresta.eu](https://mypresta.eu/modules/administration-tools/assign-carrier-to-products-in-bulk.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/assign-carrier-to-products-in-bulk/)
>
> ---


# Asignar transportista a productos en masa

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones de servidor inusuales.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Asignar transportista a productos en masa)

Esta es la interfaz principal donde definirá sus tareas de asignación masiva de transportistas. La página está diseñada para ser intuitiva, guiándole a través del proceso de selección de transportistas y luego especificando qué productos deben ser afectados.

**Opciones de configuración principales:**

1.  **Seleccionar transportistas:**

    -   **Qué hace este ajuste:** Esta sección muestra una lista de todos los transportistas activos configurados en su tienda PrestaShop (que se encuentran en **Transporte > Transportistas**). Puede seleccionar uno o más transportistas que desee asignar a sus productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se selecciona uno o más transportistas:* Los transportistas elegidos se asignarán a los productos que especifique en los siguientes pasos. Esto significa que estos transportistas se convertirán en opciones de envío disponibles para esos productos durante el proceso de pago.
        -   *Cuando no se selecciona ningún transportista:* El módulo no realizará ninguna asignación. Debe seleccionar al menos un transportista para continuar.
    -   **Valor recomendado:** Seleccione todos los transportistas que deben estar disponibles para los productos objetivo.
    -   **Escenario / ejemplo de comerciante:** Si desea que "UPS Ground" y "FedEx Express" estén disponibles para una nueva línea de productos electrónicos, seleccionaría ambos de esta lista.
2.  **Seleccionar productos a los que asignar transportistas:**

    -   **Qué hace este ajuste:** Esta sección crucial le permite definir el alcance de los productos que recibirán las asignaciones de transportistas seleccionadas. Tiene tres opciones potentes:
        -   **Por categorías:** Asignar transportistas a todos los productos dentro de categorías específicas.
        -   **Por fabricantes:** Asignar transportistas a todos los productos de fabricantes específicos.
        -   **Por productos específicos:** Asignar transportistas a productos individuales que seleccione.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se selecciona "Por categorías":* Aparecerá una lista de las categorías de su tienda. Seleccionar categorías aquí significa que a todos los productos que pertenecen a estas categorías se les asignarán los transportistas elegidos.
        -   *Cuando se selecciona "Por fabricantes":* Aparecerá una lista de los fabricantes de su tienda. Seleccionar fabricantes aquí significa que a todos los productos asociados con estos fabricantes se les asignarán los transportistas elegidos.
        -   *Cuando se selecciona "Por productos específicos":* Aparecerá un campo de entrada con una función de autocompletado. Puede escribir nombres de productos y el sistema sugerirá productos. Puede añadir varios productos específicos a la lista.
    -   **Valor recomendado:** Elija el método que mejor agrupe sus productos objetivo. Para cambios amplios, las categorías o los fabricantes son eficientes. Para ajustes precisos, los productos específicos son los mejores.
    -   **Escenario / ejemplo de comerciante:**
        -   *Categorías:* Lanza una nueva categoría "Artículos frágiles". Seleccionaría esta categoría y asignaría un "Transportista de mercancías frágiles" especializado a todos los productos dentro de ella.
        -   *Fabricantes:* Llega una nueva marca de ropa. Selecciona el fabricante y asigna su "Transportista de ropa" estándar a todos sus productos.
        -   *Productos específicos:* Tiene tres productos únicos y de gran tamaño que requieren un "Transportista de carga". Buscaría y añadiría estos tres productos individualmente.
3.  **Botones de acción:**

    -   **Botón "Asignar transportistas":**
        -   **Qué hace este botón:** Inicia el proceso de asignación masiva. Después de hacer clic, el módulo procesará sus selecciones y actualizará las asociaciones de transportistas para todos los productos especificados.
        -   **Efecto de hacer clic en este botón:** Los transportistas seleccionados se vincularán a los productos elegidos. Normalmente se mostrará un mensaje de éxito o error.
        -   **Acción recomendada:** Haga clic solo después de revisar cuidadosamente sus selecciones de transportistas y productos.
        -   **Escenario / ejemplo de comerciante:** Después de configurar sus transportistas y grupos de productos, hacer clic en este botón ejecuta los cambios en su tienda.
    -   **Botón "Borrar todas las asignaciones" (o similar):**
        -   **Qué hace este botón:** Esta opción (si está presente) normalmente eliminaría *todas* las asignaciones de transportistas para los productos seleccionados, o potencialmente para todos los productos de la tienda, dependiendo de la implementación exacta del módulo.
        -   **Efecto de hacer clic en este botón:** Los productos volverían a no tener transportistas específicos asignados, o solo transportistas predeterminados, lo que podría afectar la disponibilidad de envío.
        -   **Acción recomendada:** Úselo con extrema precaución y solo si comprende completamente las implicaciones. Esta es una acción poderosa que puede interrumpir sus opciones de envío.
        -   **Escenario / ejemplo de comerciante:** Está revisando completamente su estrategia de envío y necesita restablecer todos los enlaces producto-transportista antes de reasignarlos.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### 2.2.1 AdminMassCarrierCronController (Back Office > Parámetros avanzados > Cron de transportista masivo)

Esta pantalla proporciona la gestión de trabajos cron relacionados con el módulo, lo que le permite programar y automatizar tareas de asignación de transportistas.

-   **Nombre de la pantalla y ubicación del menú:** Normalmente encontrará un nuevo elemento de menú en **Parámetros avanzados** (o una sección similar, según la versión de PrestaShop) llamado algo como "Cron de transportista masivo" o "Programador de asignación de transportistas".
-   **Acciones y configuraciones disponibles:** Esta pantalla probablemente mostrará una cuadrícula (lista) de tareas programadas. Para cada tarea, es posible que vea:
    -   **ID de tarea:** Identificador único.
    -   **Descripción:** Una breve explicación de lo que hace la tarea (por ejemplo, "Asignar UPS a la Categoría X").
    -   **Frecuencia:** Con qué frecuencia se ejecuta la tarea (por ejemplo, diaria, semanal, una vez).
    -   **Última ejecución:** Marca de tiempo de la última ejecución.
    -   **Estado:** Si la tarea está activa, pendiente o completada.
    -   **Acciones:** Botones para "Añadir nueva tarea", "Editar", "Eliminar" o "Ejecutar ahora".
-   **Efecto de los cambios:**
    -   *Añadir una nueva tarea:* Le permite definir una nueva operación de asignación masiva de transportistas para que se ejecute automáticamente en un intervalo especificado. Esto es útil para actualizaciones recurrentes (por ejemplo, nuevas importaciones de productos).
    -   *Editar una tarea:* Modifica los parámetros (transportistas, productos, frecuencia) de una asignación programada existente.
    -   *Eliminar una tarea:* Elimina una asignación programada, impidiendo que se ejecute en el futuro.
    -   *Ejecutar una tarea ahora:* Ejecuta una tarea programada inmediatamente, fuera de su horario regular.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    -   Utilice esta pantalla para automatizar las asignaciones rutinarias de transportistas, especialmente si importa regularmente nuevos productos a categorías específicas o de ciertos fabricantes que siempre utilizan los mismos transportistas.
    -   Para asignaciones puntuales e inmediatas, utilice la página principal de configuración del módulo (4.1).
    -   Verifique regularmente "Última ejecución" y "Estado" para asegurarse de que sus tareas automatizadas se estén ejecutando correctamente.

#### 2.2.2 index.php (masscarrier/controllers/admin/index.php)

Este archivo suele servir como marcador de posición o redireccionamiento dentro del directorio de controladores de administración del módulo y, por lo general, no representa una pantalla distinta y configurable para el comerciante. En el desarrollo de módulos de PrestaShop, los archivos `index.php` dentro de subdirectorios a menudo evitan la lista de directorios o manejan el enrutamiento básico, en lugar de proporcionar una interfaz de usuario. Por lo tanto, no hay configuraciones o acciones específicas orientadas al comerciante asociadas con este archivo.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de configuración del módulo** | Seleccionar transportistas | Seleccionar todos los relevantes | Elija qué transportistas se asignarán a los productos. |
|  | Seleccionar productos: Por categorías | Seleccionar categorías relevantes | Asignar transportistas a todos los productos dentro de las categorías elegidas. |
|  | Seleccionar productos: Por fabricantes | Seleccionar fabricantes relevantes | Asignar transportistas a todos los productos de los fabricantes elegidos. |
|  | Seleccionar productos: Por productos específicos | Buscar y añadir productos | Asignar transportistas a productos seleccionados individualmente. |
|  | Botón Asignar transportistas | Hacer clic después de la selección | Ejecuta la asignación masiva de transportistas. |
|  | Botón Borrar todas las asignaciones | Usar con precaución | Elimina las asignaciones de transportistas para los productos seleccionados (si está presente). |
| **AdminMassCarrierCronController** | Añadir/Editar/Eliminar tarea | Según las necesidades de automatización | Programar y gestionar asignaciones masivas de transportistas automatizadas. |
|  | Acción Ejecutar ahora | Según sea necesario para la ejecución inmediata | Activar manualmente una tarea programada. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Asigné transportistas, pero no aparecen para los clientes en el proceso de pago.**
R:

1.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). PrestaShop a menudo almacena en caché la disponibilidad del transportista.
2.  **Configuración del transportista:** Verifique que los transportistas estén activos, tengan zonas de envío válidas y estén configurados para manejar el rango de peso/precio del producto. Vaya a **Transporte > Transportistas** y edite el transportista para revisar su configuración.
3.  **Dimensiones/Peso del producto:** Asegúrese de que las dimensiones y el peso del producto estén correctamente introducidos y se encuentren dentro de los rangos definidos por el transportista.
4.  **Ejecución del módulo:** Vuelva a ejecutar el proceso de asignación en el módulo, asegurándose de haber seleccionado los transportistas y grupos de productos correctos.

**P: El módulo parece estar atascado o tarda mucho tiempo en procesarse.**
R:

1.  **Recursos del servidor:** Si tiene un catálogo muy grande (decenas de miles de productos) y está asignando a "todos los productos", el proceso puede consumir muchos recursos. Asegúrese de que su alojamiento tenga suficiente memoria PHP y límites de tiempo de ejecución.
2.  **Trabajo Cron:** Para operaciones extremadamente grandes, considere usar el "AdminMassCarrierCronController" para programar la tarea como un trabajo cron en segundo plano, lo cual es más robusto para procesos de larga duración.
3.  **Dividir tareas:** En lugar de asignar a *todos* los productos a la vez, intente dividirlo por categorías principales o fabricantes.

**P: ¿Puedo eliminar un transportista de productos en masa usando este módulo?**
R: La función principal de este módulo es *asignar* transportistas. Aunque no tiene una función directa de "eliminar transportista de productos seleccionados", puede lograrlo de manera efectiva mediante:

1.  **Reasignación:** Si desea reemplazar el Transportista A por el Transportista B para un grupo de productos, simplemente seleccione el Transportista B y el grupo de productos, luego ejecute la asignación. Esto añadirá el Transportista B. Luego, tendría que eliminar manualmente el Transportista A de esos productos si desea que desaparezca por completo, o usar una herramienta separada si está disponible.
2.  **Eliminación manual:** Para productos específicos, aún puede ir a la página de edición del producto (**Catálogo > Productos > Editar producto > pestaña Envío**) y desmarcar el transportista manualmente.

**P: Mi tema personalizado no muestra los elementos del módulo correctamente (si alguno era visible).**
R: Este módulo no tiene elementos visuales en el front-office, por lo que es poco probable que haya problemas de compatibilidad con el tema desde una perspectiva de visualización. Si encuentra problemas con las pantallas de configuración del *back-office*:

1.  **Versión de PrestaShop:** Asegúrese de haber descargado la versión correcta del módulo para su instalación de PrestaShop.
2.  **Caché del navegador:** Borre la caché de su navegador.
3.  **Sobreescrituras del tema:** Si su tema del back-office está muy personalizado, podría interferir. Intente cambiar temporalmente al tema predeterminado del back-office de PrestaShop para ver si el problema persiste.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura

El módulo "Asignar transportista a productos en masa" (`masscarrier`) sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, centrándose principalmente en tareas administrativas. Aprovecha la clase `Module` de PrestaShop para su funcionalidad principal y extiende `AdminController` para sus pantallas de gestión dedicadas en el back-office. El módulo interactúa directamente con los datos principales de productos y transportistas de PrestaShop, modificando la tabla `ps_product_carrier` para establecer asociaciones. También incluye un controlador frontal para la ejecución de trabajos cron, lo que permite operaciones masivas programadas.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nombre de la clase y clase padre**: `MassCarrierCronjobModuleFrontController` extiende `ModuleFrontController`.
        -   **Responsabilidad**: Este controlador está diseñado para ser llamado externamente, típicamente por un trabajo cron del lado del servidor. Ejecuta las tareas de asignación de transportistas programadas definidas en el back-office. No renderiza ninguna salida visual al navegador, sino que realiza el procesamiento en segundo plano. Maneja la lógica para recuperar tareas pendientes de la tabla `masscarriercron` y aplicar los cambios de transportista a los productos.
-   **Controladores de administración del Back-Office**:

    -   `controllers/admin/AdminMassCarrierCron.php`
        -   **Nombre de la pestaña y entidad gestionada**: Este controlador gestiona la entidad `masscarriercron`, que representa tareas programadas de asignación masiva de transportistas. Crea una nueva pestaña en el back office de PrestaShop (probablemente en "Parámetros avanzados" o un menú personalizado "Transportista masivo").
        -   **Responsabilidad**: Proporciona una interfaz `AdminController` estándar de PrestaShop para listar, añadir, editar y eliminar tareas cron programadas. Maneja el envío de formularios para crear/actualizar tareas, validar la entrada e interactuar con la tabla de la base de datos `masscarriercron`.
    -   `controllers/admin/index.php`
        -   **Responsabilidad**: Este es un archivo `index.php` vacío estándar que a menudo se coloca en los directorios de módulos de PrestaShop para evitar la lista de directorios cuando se accede directamente a través de un navegador web. No contiene ninguna lógica funcional ni gestiona ninguna entidad.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto implica que la lógica central para la asignación de transportistas y la gestión de trabajos cron probablemente se maneja directamente dentro del archivo principal `masscarrier.php` y los controladores respectivos, posiblemente utilizando directamente los `ObjectModel` de `Product` y `Carrier` de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

-   `masscarrier/lib/searchTool/views/js/autocomplete.js`
    -   **Alcance**: Back-office.
    -   **Responsabilidad**: Este script probablemente proporciona la funcionalidad de autocompletado para seleccionar productos específicos en la página de configuración principal del módulo. Escucha la entrada del usuario en un campo de búsqueda de productos designado, envía solicitudes AJAX a un controlador del back-office (o al método `getContent()` del módulo principal) para obtener sugerencias de productos y las muestra en una lista desplegable. Maneja los eventos de selección para añadir los productos elegidos a una lista para la asignación masiva.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `masscarrier/lib/searchTool/views/css/autocomplete.css`
    -   **Alcance**: Estilo del formulario de administración del back-office.
    -   **Responsabilidad**: Proporciona estilo para la entrada de búsqueda de autocompletado y su lista de sugerencias, asegurando que se integre visualmente con el tema del back-office de PrestaShop. Define estilos para el campo de entrada, el contenedor desplegable y los elementos de sugerencia individuales. Los desarrolladores pueden anular estas clases en sus temas personalizados del back-office si es necesario.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   No se enumeran plantillas de hook específicas, lo que sugiere que la configuración principal del módulo se maneja a través de `getContent()` y controladores de administración dedicados.
-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `masscarrier/lib/searchTool/views/scripts.tpl`
        -   **Propósito**: Esta plantilla probablemente incluye el JavaScript necesario para la herramienta de búsqueda de autocompletado (por ejemplo, `autocomplete.js`) y potencialmente configuraciones de JavaScript en línea o enlaces CSS. Probablemente se incluye en el formulario de configuración principal del módulo o en un formulario de controlador de administración.
    -   `masscarrier/masscarrier.tpl`
        -   **Propósito**: Esta es la plantilla de configuración principal del módulo, renderizada por el método `getContent()` de `masscarrier.php`. Contiene la estructura HTML para seleccionar transportistas, elegir grupos de productos (categorías, fabricantes, productos específicos) y el botón "Asignar transportistas". Probablemente incluye `scripts.tpl` para la funcionalidad de autocompletado.
    -   `masscarrier/views/button-subcategories.tpl`
        -   **Propósito**: Esta plantilla probablemente renderiza un botón o una sección relacionada con la gestión de subcategorías, posiblemente para expandir/contraer árboles de categorías en la interfaz de selección de productos, o para acciones específicas relacionadas con la selección de subcategorías.
-   **Plantillas de Front-office (`views/templates/front/`)**:

    -   No se enumeran plantillas de front-office, lo que es consistente con la naturaleza administrativa del módulo en el back-office.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   `ps_masscarriercron`: Esta tabla personalizada almacena los detalles de las tareas programadas de asignación masiva de transportistas. Normalmente contendría campos como:
        -   `id_masscarriercron`: Clave primaria.
        -   `carriers`: Un array serializado o una cadena de IDs de transportistas separados por comas.
        -   `product_selection_type`: (por ejemplo, 'category', 'manufacturer', 'product').
        -   `product_selection_ids`: Un array serializado o una cadena de IDs de categoría/fabricante/producto separados por comas.
        -   `frequency`: (por ejemplo, 'daily', 'weekly', 'once').
        -   `last_run`: DATETIME de la última ejecución.
        -   `active`: BOOLEAN que indica si la tarea está habilitada.
    -   El módulo interactúa principalmente con las tablas principales de PrestaShop:
        -   `ps_product_carrier`: Esta es la tabla crucial que almacena la relación de muchos a muchos entre productos y transportistas. El módulo inserta/actualiza registros en esta tabla.
        -   `ps_product`: Para recuperar información del producto.
        -   `ps_category_product`: Para vincular productos a categorías.
        -   `ps_product_supplier` / `ps_manufacturer`: Para vincular productos a fabricantes.
        -   `ps_carrier`: Para recuperar información del transportista.
-   **Tabla de Hooks registrados**:
    La descripción del módulo menciona "Hooks de Front-Office: Cabecera, Columnas, Producto o Pie de página", pero basándose en el inventario de código y el propósito del módulo, es muy poco probable que registre hooks de front-office para la salida visual. Estos podrían ser marcadores de posición genéricos o referirse a hooks internos utilizados para la inicialización del módulo o el procesamiento de datos.

    El módulo utilizaría principalmente hooks internos de PrestaShop para su funcionalidad:

    | Nombre del Hook | Momento de ejecución | Propósito técnico |
    | --- | --- | --- |
    | `actionModuleInstall` | Durante la instalación del módulo | Crea la tabla `ps_masscarriercron`, registra las pestañas de administración. |
    | `actionModuleUninstall` | Durante la desinstalación del módulo | Elimina la tabla `ps_masscarriercron`, anula el registro de las pestañas de administración. |
    | `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración | Inyecta activos JS/CSS para formularios del back-office (por ejemplo, autocomplete.js, autocomplete.css). |
    | `displayBackOfficeHeader` | Se renderiza en la cabecera del back-office | Puede incluir JS/CSS global del back-office o configuración. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Asignar transportista a productos en masa", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu proporciona soporte directo y garantiza que tenga acceso a las versiones más compatibles y ricas en funciones del módulo para su tienda PrestaShop.

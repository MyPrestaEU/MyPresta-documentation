---
title: "GPSR Free - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo GPSR Free de PrestaShop por MyPresta.eu."
sidebar:
  label: "GPSR Free"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo GPSR Free en MyPresta.eu](https://mypresta.eu/modules/administration-tools/gpsr-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/gpsr-free/)
>
> ---


# GPSR Free

## 1. Requisitos y Compatibilidad
-   **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilidad PHP**: PHP 7.1 - 8.5
-   **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento compatibles con PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > GPSR Free)

Esta es la pantalla de configuración principal para el módulo GPSR Free, accesible inmediatamente después de la instalación o haciendo clic en "Configurar" desde el Gestor de Módulos.

-   **Qué hace este ajuste:** Este interruptor controla si el bloque de información del GPSR se muestra en sus páginas de producto en el front office.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (Sí):* El bloque de información del GPSR, que contiene los detalles del fabricante, la persona responsable y las advertencias, aparecerá en las páginas de producto donde haya mapeado la información relevante.
    -   *Cuando está deshabilitado (No):* El bloque de información del GPSR se ocultará de todas las páginas de producto, independientemente de cualquier mapeo que haya configurado.
-   **Valor recomendado:** **Sí**. Para cumplir con el GPSR y mostrar la información, esto debe estar habilitado.
-   **Escenario / ejemplo del comerciante:** Si está configurando activamente sus datos del GPSR y desea que sean visibles para los clientes, habilite esto. Si todavía está en proceso de configurar datos o desea ocultar temporalmente el bloque (por ejemplo, durante un rediseño del sitio), puede deshabilitarlo.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

El módulo GPSR Free añade varios elementos de menú nuevos bajo una sección principal "GPSR Free" en su Back Office de PrestaShop. Estas pantallas le permiten gestionar las diversas piezas de información requeridas para el cumplimiento del GPSR.

#### 2.2.1 Panel de Control GPSR Free (Back Office > GPSR Free > Panel de Control)
Esta pantalla sirve como punto de entrada principal para la administración dedicada del módulo. Típicamente proporciona una visión general o enlaces rápidos a las otras secciones de gestión.

-   **Acciones y Ajustes Disponibles:** Esta vista suele presentar una interfaz tipo panel de control, que potencialmente muestra estadísticas o enlaces rápidos para gestionar Fabricantes, Entidades, Advertencias y Mapas de Productos.
-   **Efecto de los cambios:** Esta pantalla en sí no tiene ajustes directos que cambien el comportamiento del front office, pero es su centro de navegación para toda la gestión de datos del GPSR.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Comience aquí para obtener una visión general, luego navegue a las secciones específicas (Fabricantes, Entidades, Advertencias, Mapa de Productos) para añadir o modificar datos.

#### 2.2.2 Fabricantes (Back Office > GPSR Free > Fabricantes)
Esta pantalla le permite definir y gestionar los fabricantes de sus productos.

-   **Acciones y Ajustes Disponibles:**
    -   **Tabla de Listado:** Muestra todos los fabricantes que ha añadido, con columnas para el nombre, la dirección y acciones como "Editar" o "Eliminar".
    -   **Botón "Añadir Nuevo Fabricante":** Al hacer clic en este botón, se abre un formulario para crear una nueva entrada de fabricante.
    -   **Campos del Formulario (para añadir/editar un fabricante):**
        -   **Nombre:** El nombre oficial del fabricante.
        -   **Dirección:** La dirección postal completa del fabricante.
        -   **¿Es Fabricante de la UE?:** Un interruptor para indicar si este fabricante tiene su sede dentro de la Unión Europea. Esto es crucial para determinar si se debe asignar una "Persona Responsable en la UE".
-   **Efecto de los cambios:** Añadir o editar fabricantes aquí crea o actualiza la lista central de fabricantes que luego puede asociar con sus productos. Esta información se mostrará en las páginas de producto si está mapeada.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Antes de mapear productos, asegúrese de que todos los fabricantes de sus productos estén listados aquí con detalles precisos. Si una nueva línea de productos proviene de un nuevo fabricante, añádalo aquí primero.

#### 2.2.3 Personas Responsables en la UE (Back Office > GPSR Free > Personas Responsables en la UE)
Esta pantalla es para gestionar las "Personas Responsables en la UE" (también denominadas "Entidades" en la nomenclatura interna del módulo) que están designadas para productos fabricados fuera de la UE.

-   **Acciones y Ajustes Disponibles:**
    -   **Tabla de Listado:** Muestra todas las Personas Responsables en la UE definidas, con su nombre, dirección y acciones.
    -   **Botón "Añadir Nueva Persona Responsable en la UE":** Abre un formulario para añadir una nueva persona responsable.
    -   **Campos del Formulario (para añadir/editar una Persona Responsable en la UE):**
        -   **Nombre:** El nombre de la persona o entidad responsable en la UE (por ejemplo, importador, representante autorizado).
        -   **Dirección:** La dirección postal completa de la persona responsable en la UE dentro de la UE.
-   **Efecto de los cambios:** Esto crea o actualiza la lista de Personas Responsables en la UE que pueden vincularse a fabricantes no comunitarios o directamente a productos. Esta información se muestra en las páginas de producto cuando es aplicable.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Si importa productos de fuera de la UE, asegúrese de tener los detalles correctos de la Persona Responsable en la UE introducidos aquí.

#### 2.2.4 Advertencias (Back Office > GPSR Free > Advertencias)
Esta pantalla le permite crear y gestionar advertencias o descargos de responsabilidad de seguridad personalizados.

-   **Acciones y Ajustes Disponibles:**
    -   **Tabla de Listado:** Muestra todas las advertencias creadas, con su texto y acciones.
    -   **Botón "Añadir Nueva Advertencia":** Abre un formulario para crear una nueva advertencia.
    -   **Campos del Formulario (para añadir/editar una advertencia):**
        -   **Texto de Advertencia:** El texto real de la advertencia o instrucción de seguridad. Este campo suele ser multilingüe, lo que le permite proporcionar traducciones para cada idioma habilitado en su tienda (controlado por `PS_LANG_DEFAULT`).
-   **Efecto de los cambios:** Añadir o editar advertencias aquí crea o actualiza el conjunto de advertencias que puede asociar con los productos. Las advertencias seleccionadas aparecerán en la página del producto.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Cree advertencias genéricas que se apliquen a varios productos (por ejemplo, "Mantener fuera del alcance de los niños", "Leer las instrucciones antes de usar"). Luego puede seleccionarlas fácilmente para productos individuales.

#### 2.2.5 Mapa de Productos (Back Office > GPSR Free > Mapa de Productos)
Esta es la pantalla más crítica donde vincula sus productos con los fabricantes, las personas responsables en la UE y las advertencias que ha definido.

-   **Acciones y Ajustes Disponibles:**
    -   **Tabla de Listado:** Muestra los mapeos de productos existentes, típicamente mostrando el nombre del producto, el fabricante asociado, la persona responsable en la UE y las advertencias.
    -   **Botón "Añadir Nuevo Mapa de Productos":** Abre un formulario para crear un nuevo mapeo.
    -   **Campos del Formulario (para añadir/editar un mapa de productos):**
        -   **Búsqueda de Producto:** Un campo para buscar y seleccionar el producto específico que desea mapear.
        -   **Fabricante:** Una lista desplegable para seleccionar uno de los fabricantes que definió en la sección "Fabricantes".
        -   **Persona Responsable en la UE:** Una lista desplegable para seleccionar una de las Personas Responsables en la UE que definió. Este campo podría ser obligatorio o aparecer solo si el fabricante seleccionado *no* es un fabricante de la UE.
        -   **Advertencias:** Una casilla de selección múltiple o lista de verificación para elegir una o más advertencias de la sección "Advertencias" para asociar con este producto.
-   **Efecto de los cambios:** Cuando guarda un mapa de productos, el fabricante seleccionado, la persona responsable en la UE (si corresponde) y las advertencias se mostrarán en la página de producto del front office para ese producto específico, siempre que la configuración "Habilitar bloque GPSR" esté activa.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Después de configurar sus fabricantes, personas responsables en la UE y advertencias, revise su catálogo de productos y mapee cada producto relevante aquí. Aquí es donde la información del GPSR se une para su visualización.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Configuración del Módulo | Habilitar bloque GPSR | Sí | Controla la visibilidad del bloque de información del GPSR en las páginas de producto. |
| Fabricantes | Nombre | N/A | Nombre oficial del fabricante del producto. |
| Fabricantes | Dirección | N/A | Dirección postal completa del fabricante. |
| Fabricantes | ¿Es Fabricante de la UE? | Sí | Indica si el fabricante tiene su sede en la UE, afectando la necesidad de una Persona Responsable en la UE. |
| Personas Responsables en la UE | Nombre | N/A | Nombre de la Persona/Entidad Responsable en la UE designada. |
| Personas Responsables en la UE | Dirección | N/A | Dirección postal completa de la Persona Responsable en la UE dentro de la UE. |
| Advertencias | Texto de Advertencia | N/A | El texto real de la advertencia o instrucción de seguridad (multilingüe). |
| Mapa de Productos | Producto | N/A | Selecciona el producto al que se mapeará la información del GPSR. |
| Mapa de Productos | Fabricante | N/A | Asocia un fabricante definido con el producto seleccionado. |
| Mapa de Productos | Persona Responsable en la UE | N/A | Asocia una Persona Responsable en la UE definida con el producto seleccionado (si el fabricante no es de la UE). |
| Mapa de Productos | Advertencias | N/A | Selecciona una o más advertencias definidas para mostrar para el producto. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: He configurado todo, pero el bloque GPSR no aparece en mis páginas de producto.**
R:
1.  **Verifique "Habilitar bloque GPSR":** Vaya a **Módulos > Gestor de Módulos > GPSR Free > Configurar** y asegúrese de que la configuración "Habilitar bloque GPSR" esté establecida en "Sí".
2.  **Borrar Caché:** Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, la caché de PrestaShop impide que el nuevo contenido aparezca inmediatamente.
3.  **Mapeo de Productos:** Vuelva a verificar que el producto específico que está viendo haya sido mapeado en **GPSR Free > Mapa de Productos** con un fabricante y al menos una advertencia/entidad.
4.  **Compatibilidad del Tema:** Si bien el módulo intenta ser compatible con la mayoría de los temas, los temas muy personalizados podrían requerir ajustes menores. Si el bloque falta por completo después de verificar lo anterior, póngase en contacto con el soporte de MyPresta.eu.

**P: El texto de advertencia o los detalles del fabricante no se muestran en el idioma correcto.**
R:
1.  **Verifique las Traducciones:** Al editar una advertencia o un fabricante, asegúrese de haber proporcionado traducciones para todos los idiomas activos en su tienda. Busque las pestañas de idioma junto a los campos de entrada.
2.  **Idioma Predeterminado:** El módulo utiliza el idioma predeterminado de PrestaShop (`PS_LANG_DEFAULT`) si falta una traducción específica. Asegúrese de que su idioma predeterminado esté configurado correctamente en **Internacional > Localización**.

**P: ¿Cómo elimino los datos de ejemplo instalados con el módulo?**
R: Puede ir a cada pantalla de gestión respectiva (**GPSR Free > Fabricantes**, **GPSR Free > Personas Responsables en la UE**, **GPSR Free > Advertencias**, **GPSR Free > Mapa de Productos**) y usar la acción "Eliminar" para cada entrada de ejemplo.

**P: ¿Puedo personalizar la apariencia del bloque GPSR?**
R: Sí, el módulo incluye un archivo `front.css`. Para cambios básicos de estilo (colores, fuentes, espaciado), a menudo puede anular estos estilos en el archivo CSS personalizado de su tema sin modificar el módulo directamente. Para cambios de diseño más avanzados, es posible que deba ajustar la plantilla `product-footer.tpl`. (Consulte la Sección 7 para obtener detalles del desarrollador).

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura
El módulo GPSR Free sigue el patrón MVC (Modelo-Vista-Controlador) de PrestaShop. Utiliza Controladores de Administración personalizados para gestionar los datos relacionados con el GPSR (Fabricantes, Entidades, Advertencias, Mapas de Productos) y aprovecha el `ObjectModel` de PrestaShop para la persistencia de datos. La visualización en el front office se maneja a través de una plantilla de hook. El módulo utiliza un patrón de repositorio (`GpsrFreeRepository`) para las interacciones con la base de datos, promoviendo un código más limpio y la separación de preocupaciones.

### 4.2 Controladores (`controllers/`)

El módulo utiliza principalmente Controladores de Administración del Back Office para la gestión de datos. No hay controladores dedicados al front office, ya que la visualización en el front office se maneja directamente a través de hooks.

-   **Controladores de Administración del Back Office**:
    -   `controllers/admin/AdminGpsrFreeController.php`
        -   **Nombre de la Clase:** `AdminGpsrFreeController` (extiende `ModuleAdminController`)
        -   **Nombre de la Pestaña:** GPSR Free (entrada principal del panel de control)
        -   **Responsabilidad:** Sirve como punto de entrada principal para la administración del módulo, probablemente mostrando un panel de control o enlaces a otras pantallas de gestión específicas. No gestiona una entidad específica, sino que orquesta el acceso a otros controladores.
    -   `controllers/admin/AdminGpsrFreeEntitiesController.php`
        -   **Nombre de la Clase:** `AdminGpsrFreeEntitiesController` (extiende `ModuleAdminController`)
        -   **Nombre de la Pestaña:** Personas Responsables en la UE
        -   **Entidad Gestionada:** `GpsrFreeEntity` (se mapea a la tabla `ps_gpsrfree_entity`)
        -   **Responsabilidad:** Gestiona la creación, edición, listado y eliminación de Personas Responsables en la UE (entidades). Proporciona una vista de lista y formulario estándar de PrestaShop para estos datos.
    -   `controllers/admin/AdminGpsrFreeManufacturersController.php`
        -   **Nombre de la Clase:** `AdminGpsrFreeManufacturersController` (extiende `ModuleAdminController`)
        -   **Nombre de la Pestaña:** Fabricantes
        -   **Entidad Gestionada:** `GpsrFreeManufacturer` (se mapea a la tabla `ps_gpsrfree_manufacturer`)
        -   **Responsabilidad:** Gestiona la creación, edición, listado y eliminación de fabricantes de productos. Incluye lógica para `is_eu_manufacturer`.
    -   `controllers/admin/AdminGpsrFreeMapController.php`
        -   **Nombre de la Clase:** `AdminGpsrFreeMapController` (extiende `ModuleAdminController`)
        -   **Nombre de la Pestaña:** Mapa de Productos
        -   **Entidad Gestionada:** `GpsrFreeProductMap` (se mapea a la tabla `ps_gpsrfree_product_map`)
        -   **Responsabilidad:** Gestiona el mapeo entre productos, fabricantes, personas responsables en la UE y advertencias. Este controlador maneja las complejas relaciones entre los diferentes tipos de datos del GPSR.
    -   `controllers/admin/AdminGpsrFreeWarningsController.php`
        -   **Nombre de la Clase:** `AdminGpsrFreeWarningsController` (extiende `ModuleAdminController`)
        -   **Nombre de la Pestaña:** Advertencias
        -   **Entidad Gestionada:** `GpsrFreeWarning` (se mapea a la tabla `ps_gpsrfree_warning`)
        -   **Responsabilidad:** Gestiona la creación, edición, listado y eliminación de advertencias de seguridad. Admite campos multilingües.
    -   `controllers/admin/GpsrFreeAdminController.php`
        -   **Nombre de la Clase:** `GpsrFreeAdminController` (extiende `ModuleAdminController`)
        -   **Nombre de la Pestaña:** (Probablemente un controlador base o abstracto para otros controladores de administración, o un punto de entrada más antiguo/redundante)
        -   **Responsabilidad:** Dado su nombre genérico, podría servir como una clase base para otros controladores de administración en el módulo, proporcionando métodos o propiedades comunes, o podría ser un punto de entrada heredado.
    -   `controllers/admin/index.php`
        -   **Nombre de la Clase:** N/A
        -   **Responsabilidad:** Archivo de seguridad estándar de PrestaShop para evitar la lista directa de directorios.

### 4.3 Clases y Modelos Principales (`classes/`)

-   `classes/GpsrFreeAdminUi.php`
    -   **Nombre de la Clase:** `GpsrFreeAdminUi`
    -   **Responsabilidad:** Probablemente una clase auxiliar para generar o gestionar elementos de la interfaz de usuario dentro del Back Office, como campos de formulario, configuraciones de lista o componentes comunes de la interfaz de administración. Ayuda a estandarizar el aspecto de las pantallas de administración del módulo.
-   `classes/GpsrFreeEntity.php`
    -   **Nombre de la Clase:** `GpsrFreeEntity` (extiende `ObjectModel`)
    -   **Tabla de Base de Datos:** `ps_gpsrfree_entity`
    -   **Campos `$definition`:** Define campos como `name`, `address`.
    -   **Métodos públicos clave:** Métodos `ObjectModel` estándar para operaciones CRUD. Representa una Persona Responsable en la UE.
-   `classes/GpsrFreeManufacturer.php`
    -   **Nombre de la Clase:** `GpsrFreeManufacturer` (extiende `ObjectModel`)
    -   **Tabla de Base de Datos:** `ps_gpsrfree_manufacturer`
    -   **Campos `$definition`:** Define campos como `name`, `address`, `is_eu_manufacturer`.
    -   **Métodos públicos clave:** Métodos `ObjectModel` estándar para operaciones CRUD. Representa un fabricante de productos.
-   `classes/GpsrFreeProductMap.php`
    -   **Nombre de la Clase:** `GpsrFreeProductMap` (extiende `ObjectModel`)
    -   **Tabla de Base de Datos:** `ps_gpsrfree_product_map`
    -   **Campos `$definition`:** Define campos como `id_product`, `id_manufacturer`, `id_entity`, `id_warning`. Esta tabla probablemente almacena las relaciones de muchos a muchos o los mapeos directos.
    -   **Métodos públicos clave:** Métodos `ObjectModel` estándar para operaciones CRUD. Gestiona los enlaces entre productos y datos del GPSR.
-   `classes/GpsrFreeRepository.php`
    -   **Nombre de la Clase:** `GpsrFreeRepository`
    -   **Responsabilidad:** Implementa el patrón de repositorio. Esta clase es responsable de todas las interacciones directas con la base de datos, abstrayéndolas de los controladores y modelos. Contiene métodos para obtener, insertar, actualizar y eliminar datos relacionados con el GPSR, a menudo utilizando la clase `Db` de PrestaShop. Contendría métodos como `getMappedProductData($id_product)`.
-   `classes/GpsrFreeWarning.php`
    -   **Nombre de la Clase:** `GpsrFreeWarning` (extiende `ObjectModel`)
    -   **Tabla de Base de Datos:** `ps_gpsrfree_warning`
    -   **Campos `$definition`:** Define campos como `text` (multilingüe).
    -   **Métodos públicos clave:** Métodos `ObjectModel` estándar para operaciones CRUD. Representa una advertencia de seguridad.
-   `classes/index.php`
    -   **Nombre de la Clase:** N/A
    -   **Responsabilidad:** Archivo de seguridad estándar de PrestaShop para evitar la lista directa de directorios.

### 4.4 Activos JavaScript (`views/js/`)
El inventario proporcionado indica que no se incluyen archivos JavaScript personalizados en el módulo. Esto sugiere que el módulo se basa principalmente en las funcionalidades JavaScript integradas de PrestaShop para sus formularios de administración y, potencialmente, en interacciones mínimas del front office, o que cualquier comportamiento dinámico se maneja en el lado del servidor.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `views/css/admin.css`
    -   **Alcance:** Estilo de los formularios de administración del Back Office.
    -   **Componentes principales de la interfaz de usuario y contenedores que estiliza:** Probablemente proporciona un estilo específico para las páginas de administración personalizadas del módulo, como tablas de lista, elementos de formulario o widgets del panel de control, para garantizar una apariencia consistente dentro del Back Office de PrestaShop.
    -   **Selectores de clase CSS clave que los desarrolladores pueden anular:** Cualquier clase personalizada utilizada en las plantillas de administración del módulo (por ejemplo, `.gpsrfree-admin-panel`, `.gpsrfree-table`).
-   `views/css/front.css`
    -   **Alcance:** Estilo del cliente del Front Office.
    -   **Componentes principales de la interfaz de usuario y contenedores que estiliza:** Estiliza el bloque de información del GPSR que se muestra en las páginas de producto. Esto incluiría el estilo del contenedor del bloque, los encabezados, los detalles del fabricante, los detalles de la persona responsable en la UE y las listas de advertencias.
    -   **Selectores de clase CSS clave que los desarrolladores pueden anular:** Clases como `.gpsrfree-block`, `.gpsrfree-manufacturer`, `.gpsrfree-entity`, `.gpsrfree-warnings`, etc. Los desarrolladores pueden dirigirse a estas clases en el archivo `custom.css` o `theme.css` de su tema para que coincidan con la marca de la tienda.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de Hook (`views/templates/hook/`)**:
    -   `views/templates/hook/product-footer.tpl`
        -   **Hook:** `displayFooterProduct` (y potencialmente `displayProductButtons` o similar, aunque `displayFooterProduct` está explícitamente listado).
        -   **Salida del Bloque Visual:** Esta plantilla es responsable de renderizar todo el bloque de información del GPSR en la página del producto. Contendrá la lógica para mostrar los detalles del fabricante, los detalles de la persona responsable en la UE (si corresponde) y una lista de advertencias asociadas, basándose en los datos recuperados del `GpsrFreeRepository` para el producto actual.
-   **Plantillas de Administración (`views/templates/admin/`)**:
    -   `views/templates/admin/configure.tpl`
        -   **Hook:** Renderizado por el método `getContent()` del archivo principal del módulo `gpsrfree.php`.
        -   **Salida del Bloque Visual:** Esta plantilla renderiza el formulario de configuración principal del módulo en el Back Office, específicamente el interruptor "Habilitar bloque GPSR". También podría contener enlaces o texto introductorio para navegar a los controladores de administración dedicados.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:
    -   `ps_gpsrfree_entity`: Almacena información sobre las Personas Responsables en la UE (id, nombre, dirección).
    -   `ps_gpsrfree_manufacturer`: Almacena información sobre los fabricantes de productos (id, nombre, dirección, is_eu_manufacturer).
    -   `ps_gpsrfree_product_map`: Almacena las relaciones de mapeo entre productos, fabricantes, personas responsables en la UE y advertencias (id_product, id_manufacturer, id_entity, id_warning). Esta tabla probablemente maneja relaciones de muchos a muchos almacenando múltiples entradas para un solo producto si tiene múltiples advertencias.
    -   `ps_gpsrfree_warning`: Almacena el texto de las advertencias de seguridad (id, texto - multilingüe).
    -   `ps_configuration`: Los ajustes del módulo como `GPSRFREE_ENABLED` se almacenan aquí.

-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
|---|---|---|
| `displayHeader` | En la sección `<head>` de cada página del front office. | Potencialmente utilizado para cargar CSS del front office (`front.css`) o JavaScript (si hubiera alguno) globalmente. |
| `displayFooterProduct` | En la parte inferior de la página del producto, típicamente debajo del contenido principal del producto. | Hook principal para renderizar el bloque de información del GPSR (`product-footer.tpl`) en la página del producto. |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página del Back Office. | Utilizado para cargar CSS del Back Office (`admin.css`) o JavaScript para las pantallas de administración del módulo. |
| `displayAdminProductsExtra` | (Implícito, a menudo utilizado para añadir pestañas/secciones a la página de edición de productos) | Aunque no está explícitamente listado como registrado, los módulos a menudo usan este o hooks similares para integrarse con la página de edición de productos si el mapeo se realizó directamente allí. Dado `AdminGpsrFreeMapController`, es probable que sea una pantalla separada. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | (No está explícitamente listado como registrado, pero es común para módulos que interactúan con pedidos. Si está presente, sería para el procesamiento de datos del GPSR relacionados con el pedido, lo cual no está indicado por la descripción del módulo). |

*Nota: El dossier del módulo listaba `DisplayHeader`, `DisplayFooterProduct`, `displayHeader`, `DisplayBackOfficeHeader`, `displayFooterProduct`, `displayBackOfficeHeader`. Estas son duplicados debido a la sensibilidad a mayúsculas y minúsculas, pero funcionalmente se refieren a los mismos hooks.*

## 5. Soporte Oficial y Actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo GPSR Free, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.

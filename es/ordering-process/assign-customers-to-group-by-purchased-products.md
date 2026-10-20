---
title: "Asignar clientes a grupo por productos comprados - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Asignar clientes a grupo por productos comprados' de MyPresta.eu."
sidebar:
  label: "Asignar clientes a grupo por productos comprados - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Assign customers to group by purchased products en MyPresta.eu](https://mypresta.eu/modules/ordering-process/assign-customers-to-group-by-purchased-products.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/assign-customers-to-group-by-purchased-products/)
>
> ---


# Asignar clientes a grupo por productos comprados

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde gestiona los ajustes centrales del módulo.

-   **Qué hace este ajuste:** Esta sección suele contener ajustes generales para el módulo, como habilitar/deshabilitar su funcionalidad principal.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado:* El módulo supervisará activamente las compras de los clientes y aplicará sus reglas de asignación de grupo definidas.
    -   *Cuando está deshabilitado:* El módulo dejará de procesar nuevos pedidos para asignaciones de grupo. Las asignaciones existentes permanecerán, pero no se realizarán nuevas automáticamente.
-   **Valor recomendado:** **SÍ** (Habilitado) para permitir que el módulo funcione.
-   **Escenario / ejemplo de comerciante:** Si está configurando el módulo por primera vez, querrá habilitarlo inmediatamente después de la configuración. Si necesita detener temporalmente las asignaciones automáticas (por ejemplo, durante una migración importante de la tienda), puede deshabilitarlo aquí.

### 2.2 Pantalla de administración dedicada: Asociaciones de grupos de productos

Esta es el área de gestión principal donde define las reglas para asignar clientes a grupos basándose en sus compras.

**Nombre de la pantalla y ubicación del menú:**
Puede acceder a esta pantalla navegando a **Módulos > Gestor de módulos**, buscando "Asignar clientes a grupo por productos comprados" y haciendo clic en "Configurar". Dentro de la configuración del módulo, encontrará una sección o pestaña dedicada a "Asociaciones de grupos de productos" o similar.

**Acciones y ajustes disponibles:**
En esta pantalla, normalmente encontrará una lista de reglas de asignación existentes. Tendrá opciones para:

-   **Añadir nueva regla:** Crear una nueva condición para la asignación de grupo.
-   **Editar regla:** Modificar una regla existente.
-   **Eliminar regla:** Eliminar una regla.

Al añadir o editar una regla, configurará lo siguiente:

1.  **Seleccionar grupo de clientes:**

    -   **Qué hace este ajuste:** Este es el grupo objetivo al que se asignarán los clientes si cumplen las condiciones de la regla.
    -   **Efecto de cambiar este ajuste:** Cuando la compra de un cliente activa esta regla, se moverá (o se añadirá) al grupo de clientes seleccionado.
    -   **Valor recomendado:** Elija el grupo de clientes específico que desea segmentar (por ejemplo, "Clientes Mayoristas", "Compradores VIP", "Entusiastas de la Electrónica").
    -   **Escenario / ejemplo de comerciante:** Desea crear una regla para asignar clientes a su grupo de "Compradores VIP".
2.  **Seleccionar productos / categorías:**

    -   **Qué hace este ajuste:** Aquí define *qué* productos o categorías de productos, cuando se compran, activarán la asignación de grupo. Normalmente puede seleccionar varios productos o categorías. El módulo probablemente incluye una herramienta de búsqueda para encontrar productos fácilmente.
    -   **Efecto de cambiar este ajuste:** Solo las compras que contengan los productos especificados o de las categorías especificadas activarán esta regla.
    -   **Valor recomendado:** Sea preciso. Utilice la herramienta de búsqueda para seleccionar todos los productos o categorías relevantes.
    -   **Escenario / ejemplo de comerciante:** Para el grupo de "Compradores VIP", podría seleccionar productos de alto valor como "Reloj de Lujo X" y "Collar de Diamantes Y". Para "Entusiastas de la Electrónica", podría seleccionar toda la categoría "Electrónica".
3.  **Cantidad mínima (Opcional):**

    -   **Qué hace este ajuste:** Si se especifica, el cliente debe comprar al menos esta cantidad de los productos/categorías seleccionados en un solo pedido para ser asignado al grupo.
    -   **Efecto de cambiar este ajuste:** Si un cliente compra menos de la cantidad mínima, la regla no se aplicará, incluso si compró los productos especificados.
    -   **Valor recomendado:** Deje vacío para cualquier cantidad, o establezca un valor como "1" para al menos un artículo, o "5" para compradores al por mayor.
    -   **Escenario / ejemplo de comerciante:** Para ser un "Cliente Mayorista", deben comprar al menos 10 unidades de cualquier producto de la categoría "Artículos a Granel".
4.  **Estado del pedido para activar la asignación:**

    -   **Qué hace este ajuste:** Esto determina en qué estado del pedido debe ocurrir la asignación del grupo de clientes. Por ejemplo, es posible que solo desee asignar grupos una vez que un pedido esté "Pago aceptado" o "Entregado".
    -   **Efecto de cambiar este ajuste:** El módulo solo procesará la asignación de grupo cuando un pedido alcance el estado seleccionado. Si un pedido nunca alcanza ese estado (por ejemplo, "Cancelado"), la asignación no se realizará.
    -   **Valor recomendado:** "Pago aceptado" o "Entregado" son generalmente opciones seguras para asegurar que la compra esté confirmada.
    -   **Escenario / ejemplo de comerciante:** Desea asegurarse de que los clientes hayan pagado realmente antes de que se añadan a un grupo especial, por lo que selecciona "Pago aceptado".
5.  **Asignar a grupo (Añadir o Reemplazar):**

    -   **Qué hace este ajuste:** Esta opción crucial determina cómo se gestiona la pertenencia del cliente al grupo.
        -   **Añadir a grupo:** El cliente se añadirá al grupo seleccionado *además* de cualquier grupo en el que ya esté.
        -   **Reemplazar grupo actual:** El grupo *principal* del cliente se cambiará al grupo seleccionado, eliminándolo potencialmente de su grupo principal anterior.
    -   **Efecto de cambiar este ajuste:**
        -   *Añadir a grupo:* Los clientes pueden pertenecer a varios grupos, lo que permite una segmentación flexible.
        -   *Reemplazar grupo actual:* Los clientes solo pertenecerán a un grupo principal, simplificando la gestión pero potencialmente perdiendo otras afiliaciones de grupo.
    -   **Valor recomendado:** "Añadir a grupo" ofrece más flexibilidad para la mayoría de los escenarios. Utilice "Reemplazar grupo actual" con cuidado, especialmente si otros módulos dependen de asignaciones de grupo primarias.
    -   **Escenario / ejemplo de comerciante:**
        -   *Añadir a grupo:* Un cliente que compra un producto específico se añade a "Compradores VIP" pero permanece en "Clientes Generales".
        -   *Reemplazar grupo actual:* Un cliente que compra un producto específico se mueve de "Clientes Generales" a "Clientes Mayoristas", convirtiéndose en su nuevo grupo principal.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1.  **Planifique sus segmentos de clientes:** Antes de crear reglas, decida qué grupos de clientes desea tener y qué criterios los definen.
2.  **Cree sus grupos de clientes:** Vaya a **Clientes > Grupos** en su Back Office de PrestaShop y cree los nuevos grupos que necesite (por ejemplo, "Mayoristas", "VIP", "Compradores del Producto X").
3.  **Defina reglas:** Para cada grupo de clientes, cree una nueva regla de asociación en la configuración del módulo.
4.  **Pruebe a fondo:** Realice una compra de prueba con una cuenta de cliente de prueba para asegurarse de que la asignación de grupo se realiza como se espera.
5.  **Revise regularmente:** Verifique periódicamente sus reglas y asignaciones de grupos de clientes para asegurarse de que sigan siendo relevantes para sus objetivos comerciales.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de configuración del módulo** | Módulo Habilitado/Deshabilitado | Habilitado | Controla si el módulo procesa activamente los pedidos para asignaciones de grupo. |
| **Asociaciones de grupos de productos** | Grupo de clientes objetivo | N/A (Definido por el usuario) | El grupo al que se asignarán los clientes. |
| | Productos / Categorías | N/A (Definido por el usuario) | Los productos o categorías específicos cuya compra activa la asignación. |
| | Cantidad mínima | Vacío (Cualquier cantidad) | Número mínimo de artículos de los productos/categorías de la regla requeridos en un pedido. |
| | Estado del pedido para activar | Pago aceptado / Entregado | El estado del pedido en el que se procesa la asignación de grupo. |
| | Tipo de asignación | Añadir a grupo | Determina si el cliente se añade al grupo o si se reemplaza su grupo principal. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis clientes no se asignan a grupos después de comprar. ¿Qué pasa?**
R:

1.  **Verifique el estado del módulo:** Asegúrese de que el módulo esté habilitado en **Módulos > Gestor de módulos** y en su página de configuración principal.
2.  **Verifique el estado del pedido:** Verifique la configuración "Estado del pedido para activar la asignación" de su regla. ¿Ha alcanzado realmente el pedido del cliente ese estado específico (por ejemplo, "Pago aceptado", "Entregado")? Los pedidos en estado "Pendiente" o "Cancelado" no activarán la asignación si su regla especifica un estado posterior.
3.  **Revise las condiciones de la regla:** Vuelva a verificar los productos/categorías seleccionados en su regla. ¿Son exactamente lo que compró el cliente? ¿Se cumple la "Cantidad mínima"?
4.  **Borrar caché:** A veces, la caché de PrestaShop puede causar problemas. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché".
5.  **Verifique si hay conflictos:** Deshabilite temporalmente otros módulos que modifiquen grupos de clientes o el procesamiento de pedidos para ver si hay un conflicto.

**P: ¿Puede un cliente estar en varios grupos?**
R: Sí, si utiliza la opción "Añadir a grupo" al crear sus reglas. Esto permite a los clientes acumular membresías de grupo basadas en varios comportamientos de compra. Si utiliza "Reemplazar grupo actual", solo estarán en un grupo principal.

**P: ¿Qué sucede si un cliente compra productos que activan varias reglas?**
R: El módulo procesará todas las reglas aplicables. Si las reglas usan "Añadir a grupo", el cliente se añadirá a todos los grupos relevantes. Si las reglas usan "Reemplazar grupo actual", la última regla procesada (basada en la lógica interna del módulo o el orden de creación de la regla) podría determinar el grupo principal final, pero es una buena práctica evitar reglas de "Reemplazar" conflictivas.

**P: He cambiado una regla, pero los pedidos antiguos no se actualizan. ¿Por qué?**
R: El módulo normalmente procesa las asignaciones de grupo cuando un pedido *cambia* al estado especificado. No aplica reglas retroactivamente a pedidos ya completados y procesados. Si necesita reevaluar clientes anteriores, es posible que deba asignarlos manualmente o considerar un script personalizado (para desarrolladores) para volver a ejecutar la lógica.

**P: ¿Cómo traduzco el texto del módulo?**
R: Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop. Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Asignar clientes a grupo por productos comprados" de la lista de módulos. Luego podrá traducir todas las cadenas visibles.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura

El módulo "Asignar clientes a grupo por productos comprados" (`pgroup`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente el patrón MVC para sus componentes de Back Office. Se integra con la funcionalidad principal de PrestaShop a través de hooks, específicamente reaccionando a los cambios de estado de los pedidos para activar su lógica de asignación de grupos de clientes. El módulo no introduce ningún controlador de front-office, ya que su funcionalidad es completamente impulsada por el backend. Utiliza un `AdminController` personalizado para gestionar las reglas de asociación de productos a grupos y se basa en el `ObjectModel` de PrestaShop para la persistencia de datos.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. Toda la lógica se maneja en el Back Office o a través de hooks.
-   **Controladores de administración de Back-Office**:

    -   `pgroup/controllers/admin/AdminProductGroupsAssociationsController.php`
        -   **Nombre de la clase:** `AdminProductGroupsAssociationsController` (extiende `ModuleAdminController`)
        -   **Responsabilidad:** Este es el controlador principal para gestionar las reglas de asociación de productos a grupos de clientes. Maneja la visualización de la lista de reglas (usando `HelperList`) y la creación/edición de reglas individuales (usando `HelperForm`). Interactúa con el `ObjectModel` `PgAssign` para persistir y recuperar los datos de asociación. Este controlador es responsable de renderizar la cuadrícula de asociaciones y el formulario para añadirlas/editarlas.
    -   `pgroup/controllers/admin/index.php`
        -   **Nombre de la clase:** No es una clase, típicamente un archivo vacío o una simple redirección para evitar el acceso directo al directorio. En PrestaShop, los archivos `index.php` dentro de los directorios de controladores suelen servir como marcadores de posición de seguridad.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto sugiere que el modelo de datos principal para las asignaciones de grupos de productos probablemente se define directamente dentro del archivo principal del módulo (`pgroup/index.php`) como un `ObjectModel` o se maneja a través de consultas directas a la base de datos.

-   **Modelo probable (dentro de `pgroup/index.php`):**
    -   **Nombre de la clase:** `PgAssign` (o similar, extendiendo `ObjectModel`)
    -   **Tabla de la base de datos:** `ps_pgassign` (o similar, basado en el `AdminProductGroupsAssociationsController` que gestiona la entidad `pgassign`).
    -   **Campos de `$definition`:** Normalmente incluiría campos como:
        -   `id_pgassign` (Clave primaria)
        -   `id_group` (ID del grupo de clientes objetivo)
        -   `id_product` (ID del producto, si la regla es específica del producto)
        -   `id_category` (ID de la categoría, si la regla es específica de la categoría)
        -   `min_quantity` (Cantidad mínima requerida)
        -   `id_order_state` (Estado del pedido para activar la asignación)
        -   `assignment_type` (por ejemplo, 'add' o 'replace')
    -   **Métodos públicos clave:**
        -   `add()`: Para guardar una nueva regla de asociación.
        -   `update()`: Para modificar una regla de asociación existente.
        -   `delete()`: Para eliminar una regla de asociación.
        -   `getAssociationsByProduct($id_product)`: Para recuperar reglas basadas en un producto.
        -   `getAssociationsByCategory($id_category)`: Para recuperar reglas basadas en una categoría.

### 4.4 Activos JavaScript (`views/js/`)

-   `pgroup/lib/searchTool/views/js/autocomplete.js`
    -   **Alcance:** Back-office (probablemente utilizado en el formulario `AdminProductGroupsAssociationsController`).
    -   **Funcionalidad:** Implementa una función de búsqueda de autocompletado, probablemente para seleccionar productos o categorías al crear/editar una regla de asignación. Escucha la entrada del usuario en un campo de texto específico, envía solicitudes AJAX a un endpoint de backend (probablemente un controlador AJAX de administración dedicado o el método `ajaxProcess` del módulo principal) para obtener productos/categorías coincidentes y muestra sugerencias. Luego maneja la selección de un elemento, rellenando campos de entrada ocultos con IDs.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `pgroup/css.css`
    -   **Alcance:** Back-office (estilo general del módulo).
    -   **Funcionalidad:** Contiene reglas de estilo generales para la página de configuración del módulo y potencialmente la interfaz `AdminProductGroupsAssociationsController`. Esto podría incluir estilos para elementos de formulario, botones o ajustes de diseño específicos del módulo.
-   `pgroup/lib/searchTool/views/css/autocomplete.css`
    -   **Alcance:** Back-office (estilo específico de autocompletado).
    -   **Funcionalidad:** Proporciona estilo para el campo de entrada de búsqueda de autocompletado, la lista desplegable de sugerencias y los elementos resaltados dentro de la lista. Los desarrolladores pueden anular estas clases para que coincidan con los temas personalizados del Back Office.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**: Ninguna explícitamente listada, lo que indica que el impacto del front-office del módulo es indirecto y no a través de la inyección directa de contenido a través de hooks.
-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `pgroup/lib/searchTool/views/scripts.tpl`
        -   **Alcance:** Back-office.
        -   **Funcionalidad:** Probablemente incluye scripts de inicialización de JavaScript para la funcionalidad de autocompletado. Esta plantilla se incluiría en el formulario de `AdminProductGroupsAssociationsController` para renderizar el JS necesario para la herramienta de búsqueda de productos/categorías.
    -   `pgroup/views/templates/admin/orderstates.tpl`
        -   **Alcance:** Back-office.
        -   **Funcionalidad:** Esta plantilla probablemente renderiza un menú desplegable o una lista de estados de pedido de PrestaShop, lo que permite al comerciante seleccionar qué estado debe activar la asignación del grupo de clientes. Sería parte del `HelperForm` utilizado en `AdminProductGroupsAssociationsController`.
    -   `pgroup/views/templates/admin/script.tpl`
        -   **Alcance:** Back-office.
        -   **Funcionalidad:** Podría contener JavaScript adicional o lógica Smarty específica de la página de configuración del módulo o los formularios de `AdminProductGroupsAssociationsController`, como la visualización condicional de campos o llamadas AJAX.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   `ps_pgassign`: Esta tabla es creada por el módulo durante la instalación. Almacena las reglas de asociación de productos a grupos.
        -   `id_pgassign` (INT, CLAVE PRIMARIA, AUTO_INCREMENT)
        -   `id_group` (INT, clave externa a `ps_group`)
        -   `id_product` (INT, clave externa a `ps_product`, anulable si la regla se basa en la categoría)
        -   `id_category` (INT, clave externa a `ps_category`, anulable si la regla se basa en el producto)
        -   `min_quantity` (INT, predeterminado 1)
        -   `id_order_state` (INT, clave externa a `ps_order_state`)
        -   `assignment_type` (VARCHAR, por ejemplo, 'add', 'replace')
    -   Registros de configuración en `ps_configuration`: El módulo podría almacenar su configuración principal `PS_PGROUP_ENABLED` (o similar) aquí.
-   **Tabla de Hooks Registrados**:
    La funcionalidad principal del módulo se basa en hooks que se activan cuando cambia el estado de un pedido.

    | Nombre del Hook | Momento de Ejecución | Propósito Técnico |
    | --- | --- | --- |
    | `actionOrderStatusPostUpdate` | Se ejecuta inmediatamente después de que se haya actualizado el estado de un pedido. | Este es el hook más probable utilizado por el módulo para verificar si un pedido ha alcanzado el estado configurado y luego aplicar las reglas de asignación de grupo basadas en los productos de ese pedido. |
    | `actionObjectOrderUpdateAfter` | Se ejecuta después de que se haya actualizado un objeto de Pedido. | También podría usarse, de manera similar a `actionOrderStatusPostUpdate`, para reaccionar a los cambios de pedido. |
    | `displayHeader` | Renderiza contenido en la sección `<head>` de las páginas del front-office. | No se utiliza directamente para la funcionalidad principal, pero podría usarse para cargar JS/CSS global si el módulo tuviera componentes de front-office (lo que no parece tener). |
    | `displayRightColumn` / `displayLeftColumn` | Renderiza contenido en las columnas laterales de las páginas del front-office. | No se utiliza directamente para la funcionalidad principal. |
    | `displayProductAdditionalInfo` / `displayProductButtons` | Renderiza contenido en la página del producto. | No se utiliza directamente para la funcionalidad principal. |
    | `displayFooter` | Renderiza contenido en el pie de página de las páginas del front-office. | No se utiliza directamente para la funcionalidad principal. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Asignar clientes a grupo por productos comprados", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.

---
title: "Cantidad máxima de producto - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Cantidad máxima de producto' de MyPresta.eu."
sidebar:
  label: "Cantidad máxima de producto"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Maximum product quantity en MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-product-quantity.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/maximum-product-quantity/)
>
> ---


# Cantidad máxima de producto

## 1. Requisitos y compatibilidad
-   **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilidad con PHP**: PHP 5.6 - 8.5
-   **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se requieren configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Cantidad máxima de producto)

La página de configuración principal del módulo es donde se definen los ajustes globales y se gestionan los límites de cantidad específicos del producto.

#### **Configuración general**

-   **Qué hace esta configuración:** Estos son los ajustes principales que habilitan o deshabilitan la funcionalidad del módulo y definen cómo se comporta globalmente.
-   **Efecto de cambiar esta configuración:**
    -   *Habilitar/Deshabilitar módulo:* Activa o desactiva todo el sistema de limitación de cantidad.
    -   *Cantidad máxima global:* Establece una cantidad máxima predeterminada para todos los productos si no se define un límite específico.
-   **Valor recomendado:** Comience habilitando el módulo y estableciendo un máximo global razonable si desea aplicar una regla general.
-   **Escenario / ejemplo de comerciante:** Si desea asegurarse de que ningún cliente pueda comprar más de 100 unidades de *cualquier* producto, establezca el máximo global en 100.

#### **Límites de cantidad específicos del producto**

Esta sección suele ser una tabla o una lista donde puede buscar productos y definir límites específicos para ellos.

-   **Qué hace esta configuración:** Le permite anular la configuración global para productos individuales. Puede especificar:
    -   **Cantidad máxima por pedido:** El número más alto de unidades de este producto que un cliente puede añadir a un solo carrito.
    -   **Cantidad máxima por cliente (total):** El número más alto de unidades de este producto que un cliente específico puede comprar *en todos sus pedidos*.
    -   **Límites específicos del grupo de clientes:** Aplique diferentes límites según el grupo de clientes (por ejemplo, "Invitados", "Clientes", "Mayoristas").
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se establecen límites:* El módulo aplicará estos límites específicos para el producto elegido, anulando cualquier configuración global.
    -   *Cuando se eliminan los límites:* El producto volverá a usar la configuración de cantidad máxima global.
-   **Valor recomendado:** Establezca límites específicos para productos de alta demanda, bajo stock o estratégicamente importantes.
-   **Escenario / ejemplo de comerciante:**
    -   Tiene un producto de edición limitada. Establece "Cantidad máxima por pedido" en 1 y "Cantidad máxima por cliente (total)" en 1 para asegurar una unidad por cliente.
    -   Para un artículo a granel, podría establecer "Cantidad máxima por pedido" en 50 para "Clientes" pero 500 para "Mayoristas".

#### **Configuración de seguimiento del historial de pedidos**

-   **Qué hace esta configuración:** Controla si el módulo consulta los pedidos anteriores de un cliente para aplicar los límites de "cantidad máxima por cliente (total)". A menudo puede especificar qué estados de pedido cuentan para el límite (por ejemplo, solo pedidos "Entregados" o "Pago aceptado").
-   **Efecto de cambiar esta configuración:**
    -   *Cuando está habilitado:* El módulo consultará el historial de pedidos del cliente para calcular sus compras totales de un producto.
    -   *Cuando está deshabilitado:* Solo se verificará la cantidad del carrito actual con el límite de "cantidad máxima por pedido". Los límites de "cantidad máxima por cliente (total)" se ignorarán efectivamente.
-   **Valor recomendado:** Habilite esto si desea aplicar límites verdaderos por cliente a lo largo del tiempo. Seleccione los estados de pedido relevantes (por ejemplo, "Pago aceptado", "Entregado") para realizar un seguimiento preciso de las compras.
-   **Escenario / ejemplo de comerciante:** Está ejecutando una promoción en la que cada cliente solo puede comprar un máximo de 3 unidades de un producto específico *en total*. Habilita el seguimiento del historial de pedidos y selecciona los estados "Pago aceptado" y "Entregado". Si un cliente ya ha comprado 2, solo puede añadir 1 más a su carrito.

#### **Personalización del mensaje de error**

-   **Qué hace esta configuración:** Le permite personalizar el mensaje que se muestra a los clientes cuando exceden un límite de cantidad.
-   **Efecto de cambiar esta configuración:** El mensaje de error genérico predeterminado se reemplazará con su texto personalizado, que puede ser más informativo o de marca.
-   **Valor recomendado:** Proporcione un mensaje claro, educado y útil. Puede usar marcadores de posición (si el módulo los admite) como `{max_quantity}` para mostrar el límite real.
-   **Escenario / ejemplo de comerciante:** En lugar de "La cantidad excede el máximo", podría establecerlo en: "Lo sentimos, solo puede comprar un máximo de {max_quantity} unidades de este artículo. ¡Esto nos ayuda a garantizar un acceso justo para todos nuestros clientes!"

#### **Exportación e importación CSV / JSON (si está disponible)**

-   **Qué hace esta configuración:** Proporciona herramientas para exportar sus límites de cantidad actuales a un archivo CSV o JSON, e importar nuevos límites desde dichos archivos. Esto es útil para la edición masiva o la migración de configuraciones.
-   **Efecto de cambiar esta configuración:**
    -   *Exportar:* Crea un archivo con todos sus límites de cantidad de producto definidos.
    -   *Importar:* Sobrescribe o añade nuevos límites de cantidad basados en los datos del archivo subido.
-   **Valor recomendado:** Utilice esto para actualizaciones a gran escala o configuración inicial si tiene muchos productos con límites específicos. Siempre haga una copia de seguridad de su configuración actual antes de importar.
-   **Escenario / ejemplo de comerciante:** Está lanzando un nuevo catálogo con 500 productos, cada uno de los cuales necesita una cantidad máxima única. En lugar de introducir cada uno manualmente, prepara un archivo CSV y lo importa.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Configuración del módulo | Habilitar/Deshabilitar módulo | Habilitado | Activa/desactiva todas las funciones de limitación de cantidad. |
| Configuración del módulo | Cantidad máxima global por pedido | Varía / 100 | Establece una cantidad máxima predeterminada para productos sin límites específicos. |
| Configuración del módulo | Cantidad máxima específica del producto por pedido | Varía / Personalizado | Anula el límite global para productos individuales en un solo carrito. |
| Configuración del módulo | Cantidad máxima específica del producto por cliente (Total) | Varía / Personalizado | Limita las compras totales de un producto por un cliente en todos los pedidos. |
| Configuración del módulo | Límites específicos del grupo de clientes | Varía / Personalizado | Aplica diferentes límites según los grupos de clientes (por ejemplo, Mayoristas). |
| Configuración del módulo | Rastrear historial de pedidos | Habilitado | Verifica pedidos anteriores para aplicar "Cantidad máxima por cliente (Total)". |
| Configuración del módulo | Estados de pedido para seguimiento | Pago aceptado, Entregado | Define qué estados de pedido cuentan para las compras totales del cliente. |
| Configuración del módulo | Mensaje de error personalizado | "La cantidad excede el límite" | Personaliza el mensaje que se muestra a los clientes cuando se alcanza un límite. |
| Configuración del módulo | Exportar/Importar CSV/JSON | N/A | Permite la gestión masiva de límites de cantidad mediante carga/descarga de archivos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He establecido límites, pero los clientes aún pueden añadir más de lo permitido. ¿Qué está mal?**
R1:
*   **¿Módulo habilitado?** Primero, verifique que el módulo esté habilitado en la configuración principal.
*   **Producto específico vs. Global:** Asegúrese de haber establecido los límites correctamente para el *producto específico* en cuestión, o que los límites globales estén activos si no existen límites específicos del producto.
*   **Grupo de clientes:** Verifique que el grupo de clientes al que pertenece el cliente tenga los límites correctos aplicados.
*   **Caché:** Borre la caché de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché). A veces, todavía se están sirviendo configuraciones antiguas.
*   **Conflictos de tema:** En raras ocasiones, un tema altamente personalizado podría interferir con la forma en que se manejan las entradas de cantidad. Pruebe con el tema predeterminado de PrestaShop para descartar esto.

**P2: La "cantidad máxima por cliente (total)" no funciona, incluso con el seguimiento del historial de pedidos habilitado.**
R2:
*   **Estados de pedido:** Vaya a la configuración del módulo y verifique qué "Estados de pedido para seguimiento" están seleccionados. Si los pedidos anteriores de un cliente están en un estado no seleccionado (por ejemplo, "Pendiente" en lugar de "Entregado"), no contarán para el límite. Asegúrese de que los estados relevantes estén marcados.
*   **Inicio de sesión del cliente:** Asegúrese de que el cliente haya iniciado sesión. El módulo solo puede rastrear compras anteriores para clientes identificados, no para invitados.

**P3: ¿Cómo traduzco los mensajes de error a otros idiomas?**
R3:
*   Navegue a **Internacional > Traducciones** en su Back Office de PrestaShop.
*   Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione su idioma.
*   Busque el módulo "Cantidad máxima de producto" en la lista. Debería poder editar los mensajes de error personalizados que haya establecido para cada idioma.

**P4: El módulo parece ralentizar mis páginas de productos o el carrito.**
R4:
*   Aunque el módulo está optimizado, si tiene un número extremadamente grande de productos con límites complejos y específicos de grupo y un seguimiento extenso del historial de pedidos, podría añadir una ligera sobrecarga.
*   **Rendimiento > CCC:** Asegúrese de que sus configuraciones CCC (Combinar, Comprimir, Almacenar en caché) para CSS y JavaScript estén habilitadas en **Parámetros avanzados > Rendimiento**.
*   **Recursos del servidor:** Verifique el límite de memoria PHP y el tiempo de ejecución de su servidor. Si son demasiado bajos, puede afectar el rendimiento.
*   **Optimización de la base de datos:** Asegúrese de que su base de datos de PrestaShop se optimice regularmente.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Cantidad máxima de producto".

### 4.1 Descripción general de la arquitectura
El módulo `Maximum product quantity` (nombre interno `mqc`) es un módulo estándar de PrestaShop diseñado para extender el proceso de pedido principal. Opera principalmente conectándose a varios puntos del front-office (página de producto, carrito, pago) para validar las cantidades de productos con los límites configurados. La configuración se gestiona a través de un único método `getContent()` en el archivo principal del módulo, utilizando la clase `Configuration` de PrestaShop para almacenar la configuración. Utiliza JavaScript para la validación front-end y la retroalimentación del usuario, y plantillas Smarty para mostrar mensajes y formularios de configuración.

### 4.2 Controladores (`controllers/`)
Este módulo no contiene controladores dedicados de front-office o back-office. Toda la lógica del front-office se maneja a través de hooks y JavaScript, mientras que la configuración del back-office se gestiona directamente dentro del método `getContent()` del archivo del módulo `index.php`.

### 4.3 Clases y modelos principales (`classes/`)
El módulo no define clases `ObjectModel` personalizadas. Todos los datos se almacenan directamente en la tabla `ps_configuration` utilizando claves de configuración estándar de PrestaShop. La lógica principal reside en el archivo `mqc/index.php`.

### 4.4 Activos JavaScript (`views/js/`)

-   **`mqc/views/js/mqc-17500.js`**:
    *   **Alcance:** Front-office (específico para PrestaShop 1.7.5.0+).
    *   **Responsabilidad:** Contiene lógica JavaScript adaptada para las versiones más recientes de PrestaShop 1.7.x y 8.x. Probablemente se conecta a `prestashop.on('updateProduct', ...)` o eventos similares para revalidar cantidades cuando los atributos del producto cambian o cuando se modifica la entrada de cantidad en la página del producto. También podría manejar llamadas AJAX al `index.php` del módulo para obtener validación de cantidad en tiempo real.
    *   **Interacción:** Se vincula a los campos de entrada de cantidad, botones de añadir al carrito y, potencialmente, selectores de atributos de producto para proporcionar retroalimentación inmediata al usuario si se excede un límite de cantidad.

-   **`mqc/views/js/mqc-front.js`**:
    *   **Alcance:** Front-office (general, potencialmente para versiones anteriores de PrestaShop o lógica común).
    *   **Responsabilidad:** Contiene lógica JavaScript general del front-office para la validación de cantidad. Esto podría incluir:
        *   Detectores de eventos para cambios en la entrada de cantidad en la página del producto o el carrito.
        *   Llamadas AJAX al servidor para verificar los límites de cantidad.
        *   Mostrar mensajes de error al usuario.
        *   Potencialmente deshabilitar o limitar los campos de entrada de cantidad.
    *   **Interacción:** Similar a `mqc-17500.js` pero podría usar enlaces de eventos basados en jQuery más antiguos o eventos de PrestaShop menos específicos.

-   **`mqc/views/js/mqc.js`**:
    *   **Alcance:** Back-office.
    *   **Responsabilidad:** Maneja JavaScript para la página de configuración del módulo en el Back Office de PrestaShop. Esto podría incluir:
        *   Elementos de formulario dinámicos (por ejemplo, añadir/eliminar filas de límite específicas del producto).
        *   Búsqueda AJAX de productos al establecer límites individuales.
        *   Validación de campos de entrada en el formulario de configuración.
        *   Lógica para las funcionalidades de importación/exportación CSV/JSON.
    *   **Interacción:** Se vincula a los elementos del formulario en la página de configuración del módulo, potencialmente realizando solicitudes AJAX al método `getContent()` del módulo para la recuperación o envío de datos.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`mqc/views/css/mqc.css`**:
    *   **Alcance:** Tanto Front-office (para mensajes de error) como Back-office (para el estilo de la página de configuración).
    *   **Componentes y contenedores principales de la interfaz de usuario que estiliza:**
        *   Contenedores de mensajes de error (por ejemplo, `div.alert.alert-danger` o clases personalizadas para mensajes específicos del módulo).
        *   Campos de entrada y etiquetas en la página de configuración del back-office.
        *   Potencialmente estilo para elementos dinámicos añadidos por `mqc.js` (por ejemplo, resultados de búsqueda de productos, filas de tabla para límites).
    *   **Selectores de clase CSS clave que los desarrolladores pueden anular:** Busque clases como `.mqc-error-message`, `.mqc-limit-table`, `.mqc-product-search-results` dentro de las plantillas del módulo y el HTML generado. Los desarrolladores pueden anularlas en el `custom.css` de su tema o creando un tema hijo.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty tanto para la visualización del front-office como para la configuración del back-office.

-   **Plantillas de hook (`views/templates/hook/`)**:
    *   **`product-details.tpl`**:
        *   **Hook:** Probablemente `displayProductExtraContent` o `displayProductButtons` (dependiendo de la versión de PrestaShop y la implementación específica).
        *   **Salida:** Podría mostrar un pequeño mensaje informativo sobre los límites de cantidad en la página del producto, o renderizar un campo de entrada de cantidad personalizado si el módulo reemplaza el predeterminado.
    *   **`productActions.tpl`**:
        *   **Hook:** `displayProductActions` (en la página del producto).
        *   **Salida:** Potencialmente utilizado para inyectar variables JavaScript o entradas ocultas relacionadas con los límites de cantidad cerca del botón de añadir al carrito, o para mostrar un mensaje de error si se excede un límite de cantidad antes de añadir al carrito.
    *   **`shoppingCart.tpl`**:
        *   **Hook:** `displayShoppingCartFooter` o `displayShoppingCart` (en la página del carrito).
        *   **Salida:** Se utiliza para mostrar mensajes de error directamente dentro del carrito de compras si las cantidades exceden los límites, impidiendo el pago.

-   **Plantillas de administración (`views/templates/admin/`)**: Estas plantillas se renderizan dentro del método `getContent()` de `mqc/index.php` para construir la interfaz de configuración del módulo.
    *   **`admintab.tpl`**: Probablemente un envoltorio o un encabezado/pie de página común para la página de configuración de administración.
    *   **`button-subcategories-purchases.tpl`**: Podría ser un botón o sección relacionada con la gestión de compras por subcategorías, posiblemente para informes avanzados o configuración de límites.
    *   **`button-subcategories.tpl`**: Similar al anterior, pero para subcategorías en general.
    *   **`csv.tpl`**: Plantilla para la funcionalidad de exportación CSV, que potencialmente contiene elementos de formulario para seleccionar opciones de exportación.
    *   **`csv_file.tpl`**: Plantilla para la funcionalidad de importación CSV, generalmente un formulario de carga.
    *   **`json.tpl`**: Plantilla para exportación/importación JSON, similar a `csv.tpl` y `csv_file.tpl`.
    *   **`main.tpl`**: La plantilla principal para la página de configuración del módulo, que contiene la estructura principal del formulario, la configuración general y, potencialmente, una tabla para límites específicos del producto.
    *   **`message.tpl`, `message2.tpl`, `message3.tpl`, `message4.tpl`, `message5.tpl`**: Plantillas de mensajes genéricos utilizadas para mostrar mensajes de éxito, error o informativos dentro de la configuración del back-office.
    *   **`orderstates.tpl`**: Plantilla para seleccionar qué estados de pedido cuentan para el límite de "cantidad máxima por cliente (total)".

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    *   El módulo no crea tablas SQL personalizadas.
    *   Todas las configuraciones se almacenan en la tabla `ps_configuration`. Las claves de configuración suelen seguir un patrón como `MQC_GLOBAL_MAX_QTY`, `MQC_PRODUCT_LIMITS_[id_product]`, `MQC_TRACK_HISTORY_STATUSES`, etc. Los límites específicos del producto pueden almacenarse como arrays serializados o cadenas JSON en una única clave de configuración, o claves individuales por producto/grupo.
    *   El seguimiento del historial de pedidos se basa en la consulta de las tablas existentes de PrestaShop: `ps_orders`, `ps_order_detail` y `ps_order_state`.

-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
|---|---|---|
| `displayHeader` | En la sección `<head>` de cada página. | Registra activos CSS y JavaScript (`mqc.css`, `mqc-front.js`, `mqc-17500.js`) para la funcionalidad del front-office. |
| `displayProductButtons` | Cerca del botón "Añadir al carrito" en la página del producto. | Inyecta lógica de validación de cantidad o muestra mensajes relacionados con límites específicos del producto. |
| `displayProductExtraContent` | Debajo de la descripción del producto, encima de los productos relacionados. | Se puede utilizar para mostrar mensajes informativos sobre los límites de cantidad. |
| `displayShoppingCart` | Dentro del resumen del carrito de compras. | Valida las cantidades en el carrito y muestra mensajes de error si se exceden los límites. |
| `displayShoppingCartFooter` | En la parte inferior de la página del carrito de compras. | Similar a `displayShoppingCart`, para la validación final antes del pago. |
| `actionValidateOrder` | Después de que un pedido ha sido validado y guardado. | Potencialmente utilizado para el procesamiento o registro posterior al pedido, aunque la validación principal es previa al pago. |
| `actionCartSave` | Después de que un carrito se guarda o actualiza (por ejemplo, cambio de cantidad). | Crucial para la validación de cantidad en tiempo real cuando un cliente modifica cantidades en el carrito o añade nuevos productos. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su salida. | Registra activos del front-office, similar a `displayHeader` pero más específico del contexto del controlador. |
| `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice su salida. | Registra activos del back-office (`mqc.js`, `mqc.css`) para la página de configuración del módulo. |

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Cantidad máxima de producto", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.

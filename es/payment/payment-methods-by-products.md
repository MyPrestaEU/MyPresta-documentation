---
title: "Métodos de pago por productos - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Métodos de pago por productos de MyPresta.eu."
sidebar:
  label: "Métodos de pago por productos - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Payment methods by products en MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/payment-methods-by-products/)
>
> ---


# Métodos de pago por productos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser requeridas por PrestaShop y son suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada grupo de ajustes por pantalla)

Este módulo tiene dos áreas de configuración principales: la página de configuración inicial del módulo y una pantalla de gestión dedicada para crear asociaciones producto-pago.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Métodos de pago por productos)

Al hacer clic en "Configurar" después de la instalación, accederá a la página de configuración principal del módulo. Esta página suele contener ajustes generales para el módulo.

**Actualmente, no se han detectado ajustes específicos en esta página de configuración principal más allá de la información estándar del módulo. La funcionalidad principal se gestiona a través de la pantalla dedicada "Asociaciones de pago - producto".**

Si futuras versiones introducen ajustes aquí, aparecerían como interruptores, campos de entrada o desplegables. Por ahora, puede proceder directamente a la pantalla de gestión dedicada.

### 2.2 Pantalla de administración dedicada: Asociaciones de pago - producto (Back Office > Módulos > Métodos de pago por productos > Asociaciones de pago - producto)

Este es el centro neurálgico para gestionar sus restricciones de pago por producto. Encontrará esta pantalla navegando a **Módulos > Gestor de módulos**, buscando "Métodos de pago por productos", haciendo clic en "Configurar" y luego buscando una pestaña o enlace llamado "Asociaciones de pago - producto" (o similar, dependiendo de la navegación del módulo).

**Nombre de la pantalla y ubicación del menú:**

- **Ruta del menú:** Back Office > Módulos > Gestor de módulos > Métodos de pago por productos > Configurar > **Asociaciones de pago - producto** (o una pestaña/enlace similar en la página de configuración).
- Esta pantalla le permite ver, añadir, editar y eliminar asociaciones entre productos y métodos de pago.

**Acciones y ajustes disponibles:**

#### 2.2.1 Vista de lista "Asociaciones de pago - producto"

Esta vista presenta una tabla de todas las restricciones de pago por producto existentes que ha configurado.

| Nombre de la columna | Propósito e impacto |
| --- | --- |
| **ID** | Un identificador único para cada asociación. |
| **Producto** | El nombre del producto involucrado en la restricción. |
| **Pago** | El nombre del método de pago que está restringido o permitido para este producto. |
| **País** | (Si aplica) El país para el que se aplica esta restricción. Si se deja vacío, se aplica globalmente. |
| **Acciones** | Iconos para **Editar** (icono de lápiz) o **Eliminar** (icono de papelera) una asociación existente. |

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

- **Revisar reglas existentes:** Revise regularmente esta lista para asegurarse de que sus restricciones estén actualizadas con su catálogo de productos y necesidades comerciales.
- **Identificar conflictos:** Busque cualquier regla superpuesta o conflictiva, especialmente si tiene muchos productos y métodos de pago.
- **Usar búsqueda/filtro:** Si la lista crece mucho, use cualquier opción de búsqueda o filtro disponible para encontrar rápidamente restricciones de productos o pagos específicos.

#### 2.2.2 Añadir o editar una "Asociación de pago - producto"

Para añadir una nueva restricción, normalmente encontrará un botón "Añadir nuevo" en la vista de lista. Al editar, haga clic en el icono de lápiz junto a una entrada existente. Esto abrirá un formulario con los siguientes campos:

| Campo del formulario | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo de comerciante |
| --- | --- | --- | --- | --- |
| **ID Producto** | Este campo le permite seleccionar el producto específico que desea asociar con restricciones de pago. | Cuando selecciona un producto, el módulo aplicará las restricciones de pago elegidas cada vez que este producto esté en el carrito de un cliente. | Seleccione el producto exacto de su catálogo. Utilice la función de búsqueda si tiene muchos productos. | Vende "Ebook Digital: Guía de Marketing". Quiere asegurarse de que solo se pague a través de PayPal o Tarjeta de Crédito, no contra reembolso. Selecciona este producto aquí. |
| **Métodos de pago** | Esta es una lista de todos los métodos de pago activos en su tienda PrestaShop. Selecciona qué métodos de pago están **permitidos** para el producto elegido. | - *Cuando selecciona uno o más métodos de pago:* Solo estos métodos seleccionados estarán disponibles en la caja si el producto asociado está en el carrito. Todos los demás métodos de pago se ocultarán.   - *Cuando no selecciona NINGÚN método de pago:* Esto significa efectivamente que el producto no se puede comprar, o heredará reglas de otros productos en el carrito. Generalmente no se recomienda dejarlo vacío a menos que tenga un caso de uso muy específico. | Seleccione todos los métodos de pago que sean aceptables para el producto elegido. | Para "Ebook Digital: Guía de Marketing", marca "PayPal" y "Tarjeta de Crédito". Si un cliente compra este ebook, solo estas dos opciones aparecerán en la caja. |
| **País** | (Opcional) Este campo le permite especificar un país para el que se aplica esta restricción particular de pago por producto. | - *Cuando se selecciona un país:* La restricción (producto + pagos permitidos) solo se aplicará si la dirección de envío del cliente está en el país seleccionado.   - *Cuando se deja vacío:* La restricción se aplica globalmente, independientemente del país del cliente. | Deje vacío para aplicación global, o seleccione un país específico si la restricción está limitada geográficamente. | Vende "Escultura de Cristal Frágil" que solo se puede pagar mediante "Transferencia Bancaria" en Francia debido a los requisitos del seguro de envío. Selecciona la escultura, "Transferencia Bancaria" y "Francia". Para clientes fuera de Francia, otros métodos de pago podrían seguir estando disponibles para este producto (si no se aplican otras reglas globales). |
| **Guardar** | Este botón guarda su asociación de pago por producto nueva o actualizada. | Los cambios se aplican inmediatamente al proceso de pago de su tienda. | Siempre haga clic en "Guardar" después de realizar cualquier cambio. | Después de configurar las reglas para su "Ebook Digital", hace clic en "Guardar" para activarlas. |

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | (No se detectaron ajustes específicos) | N/A | Información general del módulo. |
| Asociaciones de pago - producto (Lista) | ID | N/A | Identificador único para la asociación. |
| Asociaciones de pago - producto (Lista) | Producto | N/A | Nombre del producto en la asociación. |
| Asociaciones de pago - producto (Lista) | Pago | N/A | Nombre del método de pago en la asociación. |
| Asociaciones de pago - producto (Lista) | País | N/A | País para el que se aplica la restricción (si la hay). |
| Asociaciones de pago - producto (Formulario Añadir/Editar) | ID Producto | Seleccione un producto | Especifica el producto para el que se restringirán los métodos de pago. |
| Asociaciones de pago - producto (Formulario Añadir/Editar) | Métodos de pago | Seleccione todos los métodos aceptables | Define qué métodos de pago están **permitidos** para el producto seleccionado. |
| Asociaciones de pago - producto (Formulario Añadir/Editar) | País | Dejar vacío para global, o seleccionar específico | Limita la restricción a un país específico. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He configurado una restricción, pero todos los métodos de pago siguen apareciendo en la caja. ¿Qué está mal?**
R:

1. **Caché:** Siempre borre la caché de PrestaShop después de realizar cambios. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
2. **Producto en el carrito:** Asegúrese de que el producto específico que ha restringido esté realmente en el carrito de compras del cliente al realizar la prueba. El módulo solo aplica las reglas si el producto está presente.
3. **Método de pago habilitado:** Verifique que los métodos de pago que *espera* ver estén realmente habilitados en **Módulos > Pago > Métodos de pago**. Este módulo filtra los métodos *habilitados*, no los habilita por sí mismo.
4. **Reglas en conflicto:** Si tiene varios productos en el carrito, y cada uno tiene restricciones, el módulo solo mostrará los métodos de pago que estén permitidos por *todos* los productos restringidos. Si no hay un método permitido común, podría parecer que no se muestran métodos. Revise sus asociaciones cuidadosamente.

**P: He configurado una restricción, ¡y ahora NO se muestran métodos de pago en la caja!**
R: Esto suele ocurrir si:

1. **No hay métodos comunes:** Tiene varios productos restringidos en el carrito, y no hay métodos de pago que estén permitidos por *todos* ellos. Por ejemplo, el Producto A permite PayPal, el Producto B permite Tarjeta de Crédito. Si ambos están en el carrito, ninguno se mostrará. Debe asegurarse de que haya al menos un método permitido común.
2. **Lista de permitidos vacía:** Creó una asociación para un producto pero no seleccionó *ningún* método de pago como permitido. El módulo ocultará entonces todos los métodos para ese producto. Edite la asociación y seleccione los métodos de pago apropiados.

**P: ¿Este módulo afecta a los métodos de pago para productos que NO están en ninguna asociación?**
R: No. Si un producto no forma parte de ninguna "Asociación de pago - producto", no impone ninguna restricción. El módulo solo actúa sobre los productos para los que ha definido reglas explícitamente. Si un carrito contiene solo productos sin restricciones, se mostrarán todos los métodos de pago estándar habilitados de su tienda.

**P: ¿Cómo interactúa este módulo con otros módulos de restricción de pago (por ejemplo, por grupo de clientes, por importe total)?**
R: Este módulo suele funcionar anulando la clase principal `PaymentOptionsFinder` de PrestaShop (como se ve en la carpeta `override`). Esto significa que tiene prioridad o se integra a un nivel fundamental. Generalmente, se aplicará la regla más restrictiva. Si otro módulo restringe un método de pago, y este módulo lo permite para un producto, el método de pago probablemente seguirá estando restringido por el otro módulo. Es crucial realizar pruebas exhaustivas si utiliza varios módulos de restricción.

**P: ¿Puedo restringir los métodos de pago por país sin restringir por producto?**
R: La función principal de este módulo es la restricción basada en productos. Aunque tiene un campo "País", se aplica *a la asociación producto-pago*. Si necesita restricciones de pago puramente basadas en el país (independientemente del producto), es posible que necesite un módulo separado diseñado para eso, o verificar si sus pasarelas de pago ofrecen restricciones por país directamente.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión técnica profunda en el módulo "Métodos de pago por productos" para desarrolladores y webmasters.

### 4.1 Resumen de la arquitectura

El módulo extiende principalmente el mecanismo de descubrimiento de opciones de pago principal de PrestaShop. Aprovecha una `override` para modificar la clase `PaymentOptionsFinder`, que es responsable de determinar los métodos de pago disponibles durante el proceso de compra. Esto permite que el módulo inyecte su lógica de filtrado basada en productos directamente en el proceso de recuperación de opciones de pago, asegurando una integración perfecta con el flujo de compra de PrestaShop.
El módulo sigue un patrón MVC estándar de PrestaShop para su gestión en el Back Office, utilizando un AdminController para gestionar la entidad `pobp` (Asociación Producto-Pago).

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**: Ninguno. La funcionalidad del front-office del módulo se gestiona mediante una anulación de una clase principal, no un controlador frontal dedicado.
- **Controladores de administración del Back-Office**:

  - `pobp/controllers/admin/AdminPobpController.php`
    - **Nombre de la clase y clase padre**: `AdminPobpController` extiende `ModuleAdminController`.
    - **Nombre de la pestaña**: Este controlador gestiona la entidad "Asociaciones de pago - producto". Es probable que esté registrado como una subpestaña bajo la configuración principal del módulo.
    - **Responsabilidad**: Este es el controlador principal CRUD (Crear, Leer, Actualizar, Eliminar) para las asociaciones producto-pago. Maneja:
      - Mostrar la lista de asociaciones existentes (ID, Producto, Pago, País).
      - Proporcionar el formulario para añadir nuevas asociaciones o editar las existentes.
      - Procesar los envíos de formularios para guardar asociaciones nuevas o actualizadas en la base de datos.
      - Manejar la eliminación de asociaciones.
      - Los campos del formulario "ID Producto", "Métodos de pago" y "País" se gestionan aquí.
  - `pobp/controllers/admin/index.php`
    - Este archivo suele ser un marcador de posición vacío o contiene medidas de seguridad básicas (por ejemplo, `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;`). No representa una vista de controlador funcional en sí mismo, sino que asegura que el acceso directo al directorio `controllers/admin` sea redirigido.

### 4.3 Clases y modelos principales (`classes/`)

- `pobp/override/classes/checkout/PaymentOptionsFinder.php`
  - **Propósito**: Este es un archivo de anulación crítico. Modifica la clase principal de PrestaShop responsable de encontrar y devolver las opciones de pago disponibles durante el proceso de compra.
  - **Nombre de la clase y clase padre**: `PaymentOptionsFinder` (anula la clase original `PaymentOptionsFinder`).
  - **Lógica clave**: El método `getPaymentOptions()` anulado (o un método similar) contendrá la lógica principal del módulo.
    - Recupera los productos actualmente en el carrito del cliente.
    - Para cada producto, comprueba si hay alguna "Asociación de pago - producto" definida en la base de datos del módulo.
    - Luego filtra las opciones de pago inicialmente disponibles (devueltas por el método `getPaymentOptions()` padre) basándose en estas asociaciones.
    - La lógica de filtrado garantiza que solo se devuelvan los métodos de pago explícitamente permitidos para *todos* los productos restringidos en el carrito. Si un producto no tiene asociación, no restringe nada. Si varios productos tienen asociaciones, se utiliza la intersección de los métodos de pago permitidos.
  - **Interacción con la base de datos**: Esta clase consultará la tabla de base de datos personalizada del módulo (probablemente `ps_pobp` o similar) para obtener las asociaciones producto-pago.

### 4.4 Activos JavaScript (`views/js/`)

No se detectaron archivos JavaScript específicos en el inventario proporcionado. Cualquier comportamiento dinámico en el Back Office (como la búsqueda de productos en el formulario de asociación) es probable que sea manejado por el JS principal de PrestaShop o un script en línea mínimo.

### 4.5 Hojas de estilo CSS (`views/css/`)

No se detectaron archivos CSS específicos en el inventario proporcionado. El estilo para los formularios y listas del Back Office probablemente se hereda del tema de administración predeterminado de PrestaShop.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**: Ninguna explícitamente listada, ya que el módulo opera a través de una anulación en lugar de una renderización directa de hook en el front office.
- **Plantillas de administración (`views/templates/admin/`)**:
  - `pobp/lib/searchTool/views/scripts.tpl`
    - **Propósito**: Esta plantilla probablemente contiene lógica JavaScript o Smarty relacionada con una herramienta de búsqueda utilizada dentro del Back Office, posiblemente para buscar productos al crear o editar una asociación. Podría incluir llamadas AJAX o filtrado dinámico para la selección de productos.
- **Plantillas del front-office (`views/templates/front/`)**: Ninguna.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo creará al menos una tabla personalizada durante su método `install()` (definido en `pobp/index.php`).
  - **`ps_pobp` (o nombre similar, por ejemplo, `ps_payment_by_product_association`)**:
    - Esta tabla almacena las asociaciones reales de producto-pago.
    - Columnas esperadas:
      - `id_pobp` (Clave primaria, INT)
      - `id_product` (INT, clave externa a `ps_product`)
      - `id_payment_module` (INT, clave externa a `ps_module` o `ps_payment_module` si existe tal tabla, o simplemente almacena el nombre/ID del módulo)
      - `id_country` (INT, clave externa a `ps_country`, anulable para reglas globales)
      - Otras columnas potenciales para configuraciones o marcas de tiempo.
  - Los valores de configuración (si los hubiera en `getContent()`) se almacenarían en `ps_configuration`.
- **Tabla de Hooks registrados**:
  La funcionalidad principal del módulo se basa en el mecanismo `override` en lugar de la ejecución directa de hooks para su filtrado primario. Sin embargo, para su integración en el Back Office y potencialmente para futuras características, podría registrar hooks estándar.

  | Nombre del Hook | Momento de ejecución | Propósito técnico |
  | --- | --- | --- |
  | `displayAdminProductsExtra` | En la página de edición de productos en el Back Office. | Podría usarse para mostrar un enlace rápido o un resumen de las restricciones de pago para el producto actual. (No detectado explícitamente, pero un punto de integración común). |
  | `actionPaymentOptionsModifier` | Durante el proceso de recuperación de opciones de pago. | Este hook está diseñado específicamente para que los módulos modifiquen la lista de opciones de pago. La anulación de `PaymentOptionsFinder` logra efectivamente un resultado similar a un nivel inferior. |
  | `actionModuleInstall` | Cuando se instala el módulo. | Para crear tablas de base de datos y registrar los hooks necesarios. |
  | `actionModuleUninstall` | Cuando se desinstala el módulo. | Para limpiar las tablas de la base de datos y anular el registro de los hooks. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y para asegurarse de tener la última versión compatible del módulo "Métodos de pago por productos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.

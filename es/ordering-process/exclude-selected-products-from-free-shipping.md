---
title: "Excluir productos seleccionados del envío gratuito - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Excluir productos seleccionados del envío gratuito' de MyPresta.eu."
sidebar:
  label: "Excluir productos seleccionados del envío gratuito - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Exclude selected products from free shipping en MyPresta.eu](https://mypresta.eu/modules/ordering-process/exclude-selected-products-from-free-shipping.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/exclude-selected-products-from-free-shipping/)
>
> ---


# Excluir productos seleccionados del envío gratuito

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla principal donde definirá las reglas principales para excluir productos del envío gratuito.

#### 2.1.1 Configuración general

- **Eliminar código de cupón con envío gratuito**

  - **Qué hace esta configuración:** Esta opción determina si un cupón de envío gratuito (una `CartRule` que otorga envío gratuito) debe ser eliminado o invalidado del carrito del cliente si hay un producto excluido presente.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado (SÍ):* Si un cliente aplica un cupón de envío gratuito y luego añade un producto que usted ha marcado para exclusión, el módulo intentará eliminar ese cupón de su carrito. Esto asegura que, incluso con un cupón, no se otorgue envío gratuito para artículos excluidos.
    - *Cuando está deshabilitado (NO):* Los cupones de envío gratuito permanecerán activos incluso si hay un producto excluido en el carrito. Esto significa que un cliente aún podría obtener envío gratuito a través de un cupón, anulando la exclusión basada en productos del módulo.
  - **Valor recomendado:** **SÍ**. Esto proporciona el control más consistente sobre sus costos de envío, evitando el envío gratuito incluso cuando se utiliza un cupón.
  - **Escenario / ejemplo de comerciante:** Usted vende muebles grandes que siempre incurren en un costo de envío. También ofrece un cupón "ENVIO GRATIS" para pedidos superiores a 100 €. Si un cliente añade un sofá (un producto excluido) y utiliza el cupón "ENVIO GRATIS", habilitar esta configuración eliminará el cupón, asegurando que pague el envío del sofá.
- **Excluir productos agotados**

  - **Qué hace esta configuración:** Esta opción le permite excluir automáticamente los productos que actualmente están agotados de calificar para envío gratuito.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado (SÍ):* Si un producto está agotado y en el carrito del cliente, y usted también lo ha marcado para exclusión, el módulo aplicará sus reglas. Esto es generalmente menos relevante ya que los productos agotados a menudo no se pueden pedir de todos modos, pero asegura la consistencia.
    - *Cuando está deshabilitado (NO):* El módulo no considerará el estado del stock al aplicar sus reglas de exclusión.
  - **Valor recomendado:** **NO**. Esta configuración a menudo es redundante ya que los productos agotados generalmente no se pueden añadir al carrito ni pedir. Manténgala deshabilitada a menos que tenga una razón específica para usarla (por ejemplo, permitir pedidos pendientes donde el envío gratuito aún debe ser bloqueado).
  - **Escenario / ejemplo de comerciante:** Usted permite pedidos pendientes para ciertos artículos. Si un artículo está en pedido pendiente (agotado) y también es un artículo grande y pesado que nunca envía gratis, habilitar esta configuración asegura que, incluso en pedido pendiente, contribuya a deshabilitar el envío gratuito.

#### 2.1.2 Reglas de exclusión de envío gratuito

- **Deshabilitar envío gratuito para productos seleccionados**

  - **Qué hace esta configuración:** Esta es la funcionalidad principal. Le permite especificar productos individuales que, cuando están en el carrito, deshabilitarán el envío gratuito.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado (SÍ):* El módulo buscará los productos específicos que haya añadido a la lista de exclusión. Si alguno de estos productos está en el carrito del cliente, el envío gratuito se deshabilitará.
    - *Cuando está deshabilitado (NO):* Ningún producto individual deshabilitará el envío gratuito, independientemente de lo que haya en la lista de exclusión.
  - **Valor recomendado:** **SÍ**. Habilite esto para usar la característica principal del módulo.
  - **Escenario / ejemplo de comerciante:** Usted vende joyas finas (pequeñas, ligeras, generalmente con envío gratuito) y también grandes vitrinas (pesadas, caras de enviar). Habilitaría esto y añadiría las vitrinas a la lista de exclusión.
- **Deshabilitar envío gratuito para categorías seleccionadas**

  - **Qué hace esta configuración:** Similar a los productos, esta opción le permite seleccionar categorías de productos enteras. Si *cualquier* producto de una categoría seleccionada está en el carrito del cliente, el envío gratuito se deshabilitará.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado (SÍ):* El módulo verificará si algún producto en el carrito pertenece a una de las categorías que ha seleccionado para exclusión. Si es así, el envío gratuito se deshabilita.
    - *Cuando está deshabilitado (NO):* Ninguna categoría deshabilitará el envío gratuito.
  - **Valor recomendado:** **SÍ** si tiene grupos enteros de productos que nunca deberían calificar para envío gratuito.
  - **Escenario / ejemplo de comerciante:** Usted vende tanto libros como grandes impresiones de arte. Todas las impresiones de arte requieren embalaje y envío especiales. Habilitaría esto y seleccionaría la categoría "Impresiones de arte". Cualquier impresión de arte en el carrito deshabilitará el envío gratuito.

#### 2.1.3 Interfaz de selección de productos y categorías

Debajo de estas configuraciones, encontrará dos secciones:

- **Productos a excluir del envío gratuito:** Una barra de búsqueda y una lista de productos actualmente excluidos.
  - **Cómo usar:** Comience a escribir el nombre de un producto en la barra de búsqueda. A medida que escribe, aparecerá una lista de productos coincidentes. Haga clic en un producto para añadirlo a la lista de exclusión. Para eliminar un producto, haga clic en la "X" junto a su nombre en la lista.
- **Categorías a excluir del envío gratuito:** Una vista de árbol de las categorías de su tienda con casillas de verificación.
  - **Cómo usar:** Marque la casilla junto a cualquier categoría que desee excluir. Todos los productos dentro de esa categoría (y sus subcategorías, dependiendo del comportamiento de las categorías de su versión de PrestaShop) deshabilitarán el envío gratuito si están presentes en el carrito.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración principal del módulo | Eliminar código de cupón con envío gratuito | SÍ | Asegura que los cupones de envío gratuito se eliminen si hay productos excluidos en el carrito. |
| Configuración principal del módulo | Excluir productos agotados | NO | Generalmente no es necesario, ya que los artículos agotados a menudo no se pueden pedir. |
| Configuración principal del módulo | Deshabilitar envío gratuito para productos seleccionados | SÍ | Activa la exclusión de envío gratuito específica del producto. |
| Configuración principal del módulo | Deshabilitar envío gratuito para categorías seleccionadas | SÍ | Activa la exclusión de envío gratuito específica de la categoría. |
| Configuración principal del módulo | Productos a excluir del envío gratuito | (Vacío) | Añada productos específicos aquí usando la herramienta de búsqueda. |
| Configuración principal del módulo | Categorías a excluir del envío gratuito | (Ninguna seleccionada) | Seleccione categorías de la vista de árbol. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: He configurado el módulo, pero el envío gratuito sigue apareciendo para un producto excluido. ¿Qué está mal?**
R:

1. **Verifique su configuración:** Vuelva a verificar que "Deshabilitar envío gratuito para productos seleccionados" (o categorías) esté habilitado y que el producto/categoría específico se haya añadido correctamente a la lista de exclusión.
2. **Borrar caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. A veces, PrestaShop almacena en caché los cálculos de envío.
3. **Pruebe con un nuevo carrito:** Asegúrese de estar probando con un carrito nuevo, ya que la caché del navegador o los datos de la sesión podrían interferir. Intente en una ventana de incógnito.
4. **Conflicto de cupón:** Si está utilizando un cupón de envío gratuito, asegúrese de que "Eliminar código de cupón con envío gratuito" esté habilitado.

**P: ¿Este módulo afecta mis tarifas de envío estándar?**
R: No, este módulo solo afecta la *disponibilidad* de la opción "Envío gratuito" (ya sea a través de reglas de carrito o transportistas de envío gratuito específicos). No modifica sus tarifas de envío estándar ni otras configuraciones de transportistas. Si el envío gratuito está deshabilitado, los clientes simplemente verán y pagarán sus opciones de envío regulares.

**P: ¿Puedo excluir productos según el peso o las dimensiones en lugar de productos/categorías específicos?**
R: Este módulo se dirige específicamente a productos y categorías. Las reglas de envío integradas de PrestaShop le permiten definir umbrales de envío gratuito basados en el peso total del carrito o el precio. Este módulo añade una capa de *excepción* sobre esas reglas. Si necesita reglas más complejas basadas puramente en peso/dimensiones para *todos* los productos, es posible que necesite un módulo de envío más avanzado o configuraciones de transportistas personalizadas.

**P: ¿Qué sucede si un cliente tiene un producto excluido y un producto no excluido en su carrito?**
R: Si *cualquier* producto en el carrito está en su lista de exclusión (ya sea directamente o a través de su categoría), el envío gratuito se deshabilitará para todo el carrito, incluso si otros productos en el carrito normalmente calificarían. La lógica del módulo es "si hay algún producto excluido presente, entonces no hay envío gratuito".

**P: Estoy usando un tema personalizado y la herramienta de búsqueda de productos no funciona correctamente.**
R: Los temas personalizados a veces pueden interferir con JavaScript.

1. **Verifique si hay errores de JavaScript:** Abra la consola de desarrollador de su navegador (generalmente F12) y busque cualquier error en la pestaña "Consola" cuando intente usar la herramienta de búsqueda.
2. **Compatibilidad del tema:** Asegúrese de que su tema sea totalmente compatible con su versión de PrestaShop.
3. **Póngase en contacto con el soporte:** Si ve errores o el problema persiste, proporcione capturas de pantalla y registros de la consola al soporte de MyPresta.eu.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Excluir productos seleccionados del envío gratuito" opera principalmente anulando las clases principales de PrestaShop relacionadas con la gestión del carrito y las reglas del carrito. Esto le permite interceptar la lógica de cálculo del envío gratuito y aplicar sus reglas de exclusión antes de que se presenten las opciones de envío finales al cliente. Aprovecha el sistema de anulación de PrestaShop para las clases `CartController`, `Cart` y `CartRule`. El módulo también incluye un controlador de administración dedicado para buscar y gestionar productos/categorías excluidos.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `exfreeshipping/override/controllers/front/CartController.php`
    - **Nombre de la clase y clase padre**: `CartController` (anula `CartControllerCore`)
    - **Responsabilidad**: Esta anulación es crucial para interceptar acciones relacionadas con el carrito, particularmente cuando se añaden o eliminan productos, o cuando se realizan cálculos de envío. Asegura que la lógica del módulo se aplique cada vez que el estado del carrito cambia, afectando la elegibilidad para el envío gratuito.
- **Controladores de administración de Back-Office**:

  - `exfreeshipping/controllers/admin/AdminExfreeshippingSearchController.php`
    - **Nombre de la pestaña y entidad gestionada**: Este controlador gestiona la funcionalidad de búsqueda AJAX de productos dentro de la configuración del módulo. No gestiona un `ObjectModel` específico directamente, pero proporciona datos para la lista de exclusión de productos.
    - **Propósito**: Responde a las solicitudes AJAX de la página de configuración del módulo para buscar productos por nombre, permitiendo al administrador seleccionar fácilmente los productos a excluir.
  - `exfreeshipping/controllers/admin/index.php`
    - **Propósito**: Este es un archivo `index.php` vacío estándar que a menudo se incluye en los directorios para evitar la lista de directorios en los servidores web. No contiene ninguna lógica de controlador funcional.

### 4.3 Clases y modelos principales (`classes/`)

- `exfreeshipping/override/classes/Cart.php`

  - **Nombre de la clase y clase padre**: `Cart` (anula `CartCore`)
  - **Tabla de la base de datos**: `ps_cart`
  - **Responsabilidad**: Esta anulación es central para la funcionalidad del módulo. Probablemente modifica métodos relacionados con el cálculo del costo de envío o la elegibilidad para el envío gratuito dentro del objeto `Cart`. Contendrá la lógica para verificar si algún producto en el carrito (o su categoría) está en la lista de exclusión y, si es así, para deshabilitar la bandera de envío gratuito para ese carrito.
  - **Métodos clave (probablemente modificados/extendidos)**: `getProducts()`, `getPackageList()`, `getWsShippingCost()`, `getShippingCost()`, o métodos similares que determinan la elegibilidad del envío.
- `exfreeshipping/override/classes/CartRule.php`

  - **Nombre de la clase y clase padre**: `CartRule` (anula `CartRuleCore`)
  - **Tabla de la base de datos**: `ps_cart_rule`
  - **Responsabilidad**: Esta anulación es responsable de gestionar la configuración "Eliminar código de cupón con envío gratuito". Modifica los métodos relacionados con la aplicación o validación de reglas de carrito para eliminar los cupones de envío gratuito si hay un producto excluido presente en el carrito.
  - **Métodos clave (probablemente modificados/extendidos)**: `checkValidity()`, `addCartRule()`, `removeCartRule()` o métodos similares que interactúan con las reglas del carrito y su validez.
- `exfreeshipping/override/classes/index.php`

  - **Propósito**: Similar al `index.php` de administración, este es un archivo vacío para evitar la lista de directorios.

### 4.4 Activos JavaScript (`views/js/`)

- `exfreeshipping/lib/searchTool/views/js/autocomplete.js`
  - **Alcance**: Back-office (página de configuración del módulo).
  - **Funcionalidad**: Este script impulsa la interfaz de búsqueda y selección de productos en la página de configuración del módulo.
  - **Detalles**:
    - Inicializa un campo de entrada de autocompletado para buscar productos.
    - Vincula oyentes de eventos (por ejemplo, `keyup`, `change`, `click`) al campo de entrada de búsqueda y a la lista de resultados.
    - Envía solicitudes AJAX a `AdminExfreeshippingSearchController` para obtener sugerencias de productos basadas en la entrada del usuario.
    - Gestiona la visualización de los resultados de búsqueda y permite a los administradores seleccionar productos, añadiéndolos a un campo de entrada oculto o a una lista visible de productos excluidos.
    - Gestiona la eliminación de productos seleccionados de la lista de exclusión.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `exfreeshipping/lib/searchTool/views/css/autocomplete.css`
  - **Alcance**: Back-office (página de configuración del módulo).
  - **Estilo**: Proporciona estilo para el campo de entrada de autocompletado de búsqueda de productos, la lista desplegable de resultados de búsqueda y la visualización de productos excluidos seleccionados en la página de configuración del módulo.
  - **Selectores clave**: Probablemente incluye estilos para `.autocomplete-input`, `.autocomplete-results`, `.selected-product-tag`, etc. Los desarrolladores pueden anularlos en sus temas de administración personalizados si es necesario.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - `exfreeshipping/lib/searchTool/views/scripts.tpl`
    - **Propósito**: Esta plantilla probablemente se incluye en el método `getContent()` del módulo para renderizar la estructura HTML necesaria para la herramienta de búsqueda de productos, incluido el campo de entrada de búsqueda y el área donde se muestran los productos seleccionados. También es probable que incluya la etiqueta `<script>` para cargar `autocomplete.js`.
  - `exfreeshipping/views/tpl/selectedProducts.tpl`
    - **Propósito**: Esta plantilla se utiliza para renderizar la lista de productos que se han seleccionado para la exclusión del envío gratuito. Se actualiza dinámicamente mediante JavaScript cuando se añaden o eliminan productos.

### 4.7 Esquema de la base de datos y mapa de ganchos

- **Tablas de la base de datos**:

  - El módulo no crea tablas SQL personalizadas.
  - La configuración se almacena en la tabla `ps_configuration` utilizando claves como `exfreeshipping_oos`, `exfreeshipping_vcode`, `exfreeshipping_visibility_rule`, `exfreeshipping_visibility_products`, `exfreeshipping_visibility_cat`.
  - Las listas de productos y categorías excluidos se almacenan como arrays serializados o cadenas separadas por comas dentro de `ps_configuration` bajo `exfreeshipping_visibility_products` y `exfreeshipping_visibility_cat` respectivamente.
- **Tabla de ganchos registrados**:
  El módulo utiliza principalmente anulaciones en lugar de llamadas directas a ganchos para su lógica central. Sin embargo, podría registrar algunos ganchos estándar para la inicialización o propósitos de visualización específicos.

| Nombre del Gancho | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador frontal está configurando sus medios (CSS/JS). | Potencialmente utilizado para cargar cualquier CSS/JS específico del front-office, aunque el impacto principal del módulo es la lógica de backend. |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Podría usarse para la configuración inicial o la carga de scripts/estilos muy ligeros si es necesario, pero no directamente para la lógica central. |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página del back-office. | Se utiliza para cargar `autocomplete.js` y `autocomplete.css` para la página de configuración del módulo. |
| `actionCartSave` | Después de que un carrito se guarda o actualiza. | Aquí es donde se activaría o reevaluaría la lógica central del módulo para verificar productos excluidos y deshabilitar el envío gratuito. |
| `actionValidateOrder` | Cuando se valida un pedido. | Asegura que las reglas de envío gratuito se apliquen correctamente en la etapa final del pago. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte técnico para el módulo "Excluir productos seleccionados del envío gratuito", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con la funcionalidad y compatibilidad del módulo.

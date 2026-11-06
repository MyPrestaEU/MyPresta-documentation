---
title: "Cart Conditions - documentación y manual de usuario"
sidebar:
  label: "Cart Conditions - documentación y manual de usuario"
description: "Manual de configuración y de resolución de problemas para tiendas que ya usan Cart Conditions."
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Cart conditions pro en MyPresta.eu](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/cart-conditions-pro/)
>
> ---


## 1. Requisitos

Cart Conditions funciona dentro de la tienda. No necesita otro módulo ni una cuenta en un servicio externo.

- PrestaShop 1.7, 8 y 9. Este manual se comprobó en PrestaShop 9.2.0.
- La versión de PHP que exige esa versión de PrestaShop. El módulo no pide una extensión PHP adicional.
- No hace falta ningún otro módulo.
- Las reglas leen el carrito actual. El tamaño del catálogo no cambia la comprobación.

## 2. Instalación

1. Abra **Módulos** y después **Module Manager**.
2. Suba el zip e instale el módulo. La instalación lo activa.
3. Abra **Catálogo**. Aparecen cinco entradas, en este orden. Los nombres siguen en inglés en cualquier idioma del back office:

- **Cart Conditions**
- **Cart Value Conditions**
- **Cart Quantity Conditions**
- **Cart Associations Conditions**
- **Cart value by country conditions**

La instalación no vacía la caché de la tienda.

La desinstalación quita esas cinco entradas y desengancha el módulo. Deja las reglas guardadas, la lista de exclusiones, el ajuste de disponibilidad y el ajuste de avisos. Si lo instala de nuevo, el menú vuelve y las reglas antiguas siguen ahí.

## 3. Configuración y trabajo diario

El cliente llena el carrito. En la página del carrito la tienda lista cada regla rota en un aviso rojo. Si el cliente sigue hacia el pago, la tienda lo devuelve al carrito hasta que cada regla activa se cumple. Un cliente de **Exclude customers from conditions** se salta todas las reglas y puede comprar.

Prepare la tienda en este orden:

1. Abra **Configure** y decida a quién y qué productos ignoran las reglas.
2. Decida si se pueden mezclar fechas de disponibilidad futuras.
3. Abra cada lista en **Catálogo**, pulse **Add new**, rellene el formulario, ponga **Active** en **On** y pulse **Save**.
4. Haga un pedido de prueba con un cliente normal y con un cliente excluido.

Un formulario nuevo se abre con **Active** en **Off**. **Save** guarda la fila y el carrito la ignora hasta que ponga **On**. La página de configuración responde **Saved**. Las listas usan la confirmación habitual del back office después de **Save**.

La nota azul de **Configure** dice: "Management of this module is located under Price Rules menu." Los cinco enlaces de esa nota, y las entradas de **Catálogo**, abren las listas. Este módulo no añade una entrada en Price Rules.

Las pantallas de este manual son el back office en inglés. Los botones y los campos se nombran como aparecen ahí.

![Enlaces de la configuración](https://mypresta.eu/docs/images/docs/cartcon-configure-links.webp)

### 3.1 Página de configuración

Abra **Módulos**, **Module Manager**, busque **Cart Conditions** y pulse **Configure**.

#### Excluir clientes y productos

![Formulario de exclusiones](https://mypresta.eu/docs/images/docs/cartcon-configure-exclude.webp)

Busque un cliente, pulse el resultado y esa persona entra en la lista de exclusión. Quite a una persona de la misma lista antes de guardar. Los clientes excluidos se saltan cada regla del carrito, también la comprobación de disponibilidad.

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Exclude customers from conditions** | vacío | Los clientes de esta lista compran sin ninguna regla de carrito. **Save** guarda la lista. |
| **Exclude products from conditions** | **Do not exclude products** | **Exclude selected products** hace que las reglas ignoren los productos y las categorías elegidos. **Do not exclude products** cuenta todos los productos. |
| **Categories** | ninguna marcada | Las categorías marcadas se omiten cuando el interruptor de arriba es **Exclude selected products**. |
| **Save** | - | Guarda clientes, interruptor, productos y categorías. La página muestra **Saved**. |

La búsqueda de productos y el árbol de categorías están en el mismo formulario. Elija un producto como elige un cliente: busque y pulse el resultado.

#### Condiciones globales

![Comparación de disponibilidad](https://mypresta.eu/docs/images/docs/cartcon-configure-availability.webp)

La comprobación mira solo productos sin stock cuya **Availability date** sigue en el futuro. Los productos con stock, con fecha vacía o pasada, y los productos excluidos quedan fuera. Una sola fecha futura en el carrito no bloquea. Dos o más valores distintos sí.

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Block order of products with Various availabiltiy date** | **Off** | **On** bloquea el carrito cuando esas fechas futuras no coinciden con la comparación de abajo. **Off** omite la comprobación. PrestaShop ya puede permitir un pedido de un producto que estará disponible más tarde. Este interruptor decide si fechas distintas pueden ir en un mismo carrito. |
| **How to compare availability dates** | **Exact date** | **Exact date** bloquea cuando las fechas futuras no son el mismo día. **Same calendar month** permite días distintos del mismo mes y año, y bloquea cuando cambia el mes o el año. El 5 de noviembre de 2026 y el 20 de noviembre de 2026 pasan. El 2 de diciembre de 2026 no. El 5 de noviembre de 2027 no. |
| **Save** | - | Guarda el interruptor y la comparación. La página muestra **Saved**. Este botón no crea una regla del Catálogo. |

Texto del carrito para **Exact date**: "Availability dates of products in your cart are different. You cant place an order." Para **Same calendar month**: "Availability months of products in your cart are different. You cant place an order."

#### Actualizaciones MyPresta

![Comprobación de actualizaciones](https://mypresta.eu/docs/images/docs/cartcon-configure-updates.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Check updates** / **Check now** | - | Pregunta a MyPresta si existe un archivo más nuevo. **Module is up to date!** significa que este archivo está al día. **New version available!** significa que hay un archivo más nuevo publicado. El botón no lo instala. |
| **Updates notifications** | **Disable** | **Enable** muestra un aviso en el back office cuando se publica una versión más nueva. **Disable** permanece en silencio. **Save** guarda la elección. |
| **Module page** | enlace | Abre la página del módulo, donde está la lista de cambios. |
| **Save** | - | Guarda la elección de avisos. |

### 3.2 Cart Conditions

Abra **Catálogo** y después **Cart Conditions**. Estas reglas valen para cada cliente que no está excluido. Esta lista no tiene campo de grupo de clientes.

![Lista Cart Conditions](https://mypresta.eu/docs/images/docs/cartcon-conditions-list.webp)

Columnas: **ID**, **Cart condition**, **Target type**, **Target item** y **Active**. Una tienda vacía muestra **No records found**. Los filtros están encima de las columnas. Acciones de fila: editar, borrar y el icono **Active**. Acción masiva: borrar. **Add new** abre el formulario.

![Nueva regla Cart Conditions](https://mypresta.eu/docs/images/docs/cartcon-conditions-form.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Condition** | **Must have** | **Must have** exige el objetivo. **Can't have** lo bloquea. |
| **Target type** | **Category** | **Category** usa un id de categoría. **Product** usa un id de producto. **More than defined number of products** usa un número de piezas de todo el carrito. |
| **Target item** | vacío | Id de categoría, id de producto o número de piezas. La ayuda del campo pide un id o un número de productos. |
| **Active** | **Off** | **On** hace que el carrito compruebe la fila. **Off** guarda la fila y la omite. |
| **Save** | - | Guarda la regla. |

Lo que ve el cliente:

- **Must have** y **Category**: "To place an order you must order product from category: ...".
- **Can't have** y **Category**: "Your cart contains product from forbidden category: .... To continue order please remove it from cart."
- **Must have** y **Product**: "To place an order you must order product: ...".
- **Can't have** y **Product**: "Your cart contains forbidden product: .... To continue order please remove it from cart."
- **Must have** y un número de piezas: "Your cart contains less products than required (...). To continue order please increase quantity of products in your cart".
- **Can't have** y un número de piezas: "Your cart contains more products than allowed (...). To continue order please decrease quantity of products in your cart".

El número de piezas es la suma de cantidades del carrito, después de quitar los productos excluidos. **Must have** exige que el carrito llegue a ese número. **Can't have** bloquea un carrito por encima de ese número.

### 3.3 Cart Value Conditions

Abra **Catálogo** y después **Cart Value Conditions**. Cada fila es un grupo de clientes, una categoría y un importe mínimo.

![Lista de valores](https://mypresta.eu/docs/images/docs/cartcon-value-list.webp)

Columnas: **ID**, **Customer group**, **Cart condition**, **Target**, **Value** y **Active**. Lista vacía: **No records found**. Acciones de fila: editar, borrar, icono **Active**. Acción masiva: borrar. **Add new** abre el formulario.

![Nueva regla de valor](https://mypresta.eu/docs/images/docs/cartcon-value-form.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Customer Group** | primer grupo de la tienda (Visitor en una tienda por defecto) | Solo se comprueba a los compradores de ese grupo. Un cliente conectado se comprueba en cada grupo al que pertenece. |
| **Condition** | **Must order from selected category** | Es la única opción. La regla actúa cuando el carrito ya contiene esa categoría. |
| **Target item** | vacío | Id de categoría. |
| **Value** | vacío | Total mínimo con impuestos de los productos de esa categoría. Escríbalo en la moneda por defecto de la tienda. El signo de moneda del formulario es la moneda de la tienda. |
| **Active** | **Off** | **On** aplica la fila. **Off** la guarda sin usarla. |
| **Save** | - | Guarda la regla. |

Si la categoría no está en el carrito, la regla calla. Si está y el total con impuestos queda por debajo de **Value**, el carrito muestra: "To place an order you must order for: ... from category: ...".

### 3.4 Cart Quantity Conditions

Abra **Catálogo** y después **Cart Quantity Conditions**.

![Lista de cantidades](https://mypresta.eu/docs/images/docs/cartcon-quantity-list.webp)

Columnas: **ID**, **Customer group**, **Cart condition**, **Target**, **Quantity** y **Active**. Lista vacía: **No records found**. Acciones de fila: editar, borrar, icono **Active**. Acción masiva: borrar.

![Nueva regla de cantidad](https://mypresta.eu/docs/images/docs/cartcon-quantity-form.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Customer Group** | primer grupo de la tienda | Solo se comprueba ese grupo. |
| **Condition** | **Must order at least X products from selected category** | Elija el límite. La lista completa está abajo. |
| **Target country** | primer país de la tienda | Solo se usa en las dos reglas "from Y category". En cualquier otra condición la página oculta esta lista. |
| **Target item** | vacío | Id de categoría, de producto, de fabricante o valor de atributo, según **Condition**. La ayuda pide el id del objetivo. En las condiciones de todo el carrito la página pone la palabra Cart y bloquea el campo. |
| **Quantity** | vacío | El número X de la condición elegida. |
| **Accept only multiplied qty** | **Off** | **On** acepta solo múltiplos de **Quantity**, por ejemplo 6, 12, 18, 24 cuando **Quantity** es 6. **Off** acepta cualquier cantidad que cumpla la regla. |
| **Active** | **Off** | **On** aplica la fila. |
| **Save** | - | Guarda la regla. |

Opciones de **Condition**, en el orden del formulario:

- **Must order at least X products from selected category**
- **Can't more than X products from selected category**
- **Must order at least X products from selected manufacturer**
- **Can't more than X products from selected manufacturer**
- **Must order at least X quantity of selected product**
- **Can't order more than X quantity of selected product**
- **Must order at least X quantity of each product**
- **Can't order more than X quantity of each product**
- **Can't order more than X products with the same attribute value**
- **Cart must have at least X products**
- **Cart can't have more than X products**
- **Cart must have at least X different products**
- **Cart can't have more than X different products**
- **Cart of user from selected country must have more than X products**
- **Cart of user from selected country can't have more than X products**
- **Cart of user from selected country must have more than X products from Y category**
- **Cart of user from selected country can't have more than X products from Y category**

En las dos últimas, ponga **Target country** y el id de categoría en **Target item**. En las dos reglas de país que no mencionan categoría, la página oculta **Target country**, así que ahí no elige un país. Use **Cart value by country conditions** cuando el límite es un importe. Use las dos últimas reglas de cantidad cuando el límite es un número de piezas de una categoría.

**Search for attribute value** aparece solo en **Can't order more than X products with the same attribute value**. Busque, pulse un valor y ese valor pasa a **Target item**.

El texto del carrito sigue la elección. Las reglas de categoría y fabricante dicen "at least" o "can't order more than" y nombran la categoría o el fabricante. Una regla de producto cita la cantidad actual. Una regla de todo el carrito dice "you must order more than" o "you can't order more than" y cita la cantidad actual. Con **Accept only multiplied qty** en **On**, el carrito añade: "We accept only multiplied quantity...".

En la ficha del producto el tema puede mostrar "You must order at least: ... quantity of this product" para **Must order at least X quantity of selected product**, cuando ese producto es el objetivo y el visitante coincide con el grupo. Es un aviso. El bloqueo ocurre en el carrito.

### 3.5 Cart Associations Conditions

Abra **Catálogo** y después **Cart Associations Conditions**. Una fila une un elemento con otro para un grupo de clientes. La regla empieza solo cuando el primer elemento ya está en el carrito.

![Lista de asociaciones](https://mypresta.eu/docs/images/docs/cartcon-associations-list.webp)

Columnas: **ID**, **Customer group**, **Cart condition**, **Target item (1)**, **Associated item (2)** y **Active**. Lista vacía: **No records found**. Acciones de fila: editar, borrar, icono **Active**. Acción masiva: borrar.

![Nueva asociación](https://mypresta.eu/docs/images/docs/cartcon-associations-form.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Active** | **Off** | **On** aplica la fila. |
| **Type of condition** | **Associations between product and product** | **Associations between product and category** o **Associations between category and category** cambia el sentido de los dos ids. |
| **For what customer group** | primer grupo de la tienda | Solo se comprueba ese grupo. |
| **Target item (1)** | vacío | Id de producto o de categoría. La regla actúa cuando el cliente mete ese objeto en el carrito. |
| **Condition** | **If customer will add to cart Target item (1) then it must order Associated item (2)** | Las opciones están abajo. |
| **Associated item (2)** | vacío | El id de producto o de categoría exigido o prohibido. |
| **Save** | - | Guarda la pareja. |

Opciones de **Condition**:

- **If customer will add to cart Target item (1) then it must order Associated item (2)**. Texto: "If your cart has a product: ... you must order also product: ..." o el equivalente de categoría.
- **If customer will add to cart Target item (1) then cart must have at least one different product**. Solo se muestra en producto y producto. La comprobación del carrito no muestra un mensaje para esta opción. Use otra opción cuando el carrito deba bloquear.
- **If customer will add to cart Target item (1) then it will be forbidden to order Associated item (2)**. Texto: "If your cart has a product: ... you can't place an order for: ...".
- **If customer will add to cart Target item (1) then it will be forbidden to add any other product to cart**. La página oculta **Associated item (2)**. Texto: "If your cart has a product: ... you can't place an order for any other product."
- **If customer will add to cart Target item (1) then it will be forbidden to add products from categories other than Target item (1)**. Solo en categoría y categoría. La página oculta **Associated item (2)**.

El formulario también contiene **Include subcategories of Target item (1)** e **Include subcategories of Associated item (2)**. La página oculta ambos interruptores en todos los tipos. La regla usa los ids que usted escribe.

### 3.6 Cart value by country conditions

Abra **Catálogo** y después **Cart value by country conditions**. La regla usa el país de la dirección de entrega.

![Lista de importes por país](https://mypresta.eu/docs/images/docs/cartcon-country-list.webp)

Columnas: **ID**, **Customer group**, **Condition**, **Country**, **Value** y **Active**. Lista vacía: **No records found**. Acciones de fila: editar, borrar, icono **Active**. Acción masiva: borrar.

![Nuevo importe por país](https://mypresta.eu/docs/images/docs/cartcon-country-form.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Customer Group** | primer grupo de la tienda | Solo se comprueba ese grupo. |
| **Target country** | primer país de la tienda | La regla actúa cuando la dirección de entrega es de ese país. La lista es la de países de la tienda. |
| **Condition** | **Cart must be worth at least ...** | **Cart can't be worth more than ...** es el máximo. |
| **Condition tax** | **Tax included** | **Tax excluded** compara el total sin impuestos. El mensaje del carrito repite la etiqueta de impuesto elegida. |
| **Cart value type** | **Products + shipping** | **Products** deja el envío fuera del total comparado. |
| **Value** | vacío | El importe, en la moneda por defecto de la tienda. |
| **Active** | **Off** | **On** aplica la fila. |
| **Save** | - | Guarda la regla. |

Por debajo del mínimo el carrito muestra: "To place an order from country: ... your cart must be worth at least ..., while you cart is worth ...". Por encima del máximo: "To place an order from country: ... your cart can't be worth more than ..., while you cart is worth ...".

## 4. Tienda

El cliente no abre una página aparte. El módulo habla en la ficha del producto y en el carrito.

En la ficha, y solo con una regla activa **Must order at least X quantity of selected product** dirigida a ese producto, el tema puede mostrar: "You must order at least: ... quantity of this product". El tema tiene que imprimir el área de acciones del producto. Este manual no incluye una foto de la tienda, porque esa línea no se confirmó en el tema de prueba.

En el carrito, cada regla rota es una línea de un aviso rojo. Los nombres de productos y categorías exigidos o prohibidos son enlaces. Si el cliente abre el pago con una regla rota, la tienda lo devuelve al carrito y muestra el mismo aviso.

Un cliente de la lista de exclusión no ve estos mensajes y no es devuelto.

No hay una dirección de la tienda que copiar. No hay un formulario para que el cliente acepte o rechace una regla.

## 5. Problemas

**Faltan las cinco entradas en Catálogo.** El módulo no está instalado o se desinstaló. Instálelo de nuevo en **Module Manager**. Las reglas antiguas vuelven con él.

**La nota azul dice Price Rules y en Price Rules no hay Cart Conditions.** Use los cinco enlaces de la nota, o **Catálogo**. El padre del menú es Catálogo.

**Una regla guardada no hace nada.** **Active** está en **Off**, el cliente está en la lista de exclusión o no está en el grupo elegido. Un visitante sin sesión se comprueba como el grupo Visitor. Abra la fila, ponga **Active** en **On** y pruebe con un cliente de ese grupo.

**Una regla de valor calla.** La categoría no está en el carrito. Añada un producto de esa categoría. El total comparado incluye impuestos.

**Dos reglas de cantidad por país ignoran el país.** **Target country** está oculto salvo que **Condition** sea una de las dos líneas "from Y category". Elija una de esas, o use **Cart value by country conditions** para un límite de dinero.

**Same calendar month sigue bloqueando noviembre y noviembre.** Los años son distintos. El 5 de noviembre de 2026 y el 5 de noviembre de 2027 son valores distintos. El producto además tiene que estar sin stock y con una **Availability date** futura. Los productos con stock no se comparan.

**Check now no muestra nada, o el aviso no aparece.** El servidor de la tienda no puede abrir la dirección remota de MyPresta. **Check now** solo informa de una versión. No descarga ni instala el archivo. Abra **Module page** y tome el archivo nuevo allí.

**Falta el aviso del carrito y el pago igual vuelve al carrito.** El tema no imprime el bloque del carrito. La vuelta al carrito sigue funcionando. Sobrescriba la plantilla del carrito en el tema, o confirme que el tema imprime el hook del carrito.

**La desinstalación quitó el menú y una instalación posterior muestra las reglas antiguas.** Así funciona la desinstalación. Borre las filas de las listas antes de desinstalar si después quiere el módulo vacío.

## 6. Para el desarrollador

### 6.1 Visión general

Clase principal `cartcon`, versión 2.1.9, nombre de lista **Cart Conditions**, autor MyPresta.eu, pestaña `advertising_marketing`. `cartconPrestashopNewCompatibility` extiende `cartcon` para el formato de precios y no es la instancia del módulo. `psversion()` mapea una versión mayor 8 o superior a la rama 1.7 en algunas decisiones de marcado del back office. No hay sustitución de `enable()` ni de `disable()`.

`getRestrictions()` lee las filas activas de la tienda actual, omite los clientes de `CARTCON_CUSTOMERS` y llena `errors_cartcon`. `hookDisplayShoppingCart` imprime esa lista. `hookDisplayPaymentTop` redirige al carrito con `cartcon=show` cuando la lista no está vacía. `hookDisplayProductActions` imprime una cantidad mínima solo para `cartcon_quantity.c_type = 2` de ese id de producto.

### 6.2 Archivos

- `cartcon.php` - instalación, formularios, comprobaciones, hooks.
- `lib/prestashop9compatibility.php` - `cartconPrestashopNewCompatibility`.
- `controllers/admin/AdminCartConditionController.php` - must-have y can't-have.
- `controllers/admin/AdminCartValueConditionController.php` - importe mínimo de categoría.
- `controllers/admin/AdminCartQuantityConditionController.php` - reglas de cantidad.
- `controllers/admin/AdminCartAssociationsConditionController.php` - parejas.
- `controllers/admin/AdminCartCountryConditionController.php` - importes por país.
- `models/CartCondition.php`, `CartValueCondition.php`, `CartQuantityCondition.php`, `CartAssociationsCondition.php`, `CartCountryCondition.php` - modelos.
- `views/templates/front/displayShoppingCart.tpl` - aviso rojo.
- `views/templates/front/productActions.tpl` - mínimo en la ficha.
- `views/templates/admin/script.tpl` - comportamiento del formulario de cantidad.
- `views/templates/admin/search-attribute-value.tpl` - búsqueda de atributo, visible en el tipo de cantidad 7.
- `lib/searchTool/searchTool.php` - `initTool()` solo inyecta scripts. No pinta un panel.

### 6.3 Controladores

Los cinco controladores de admin extienden `ModuleAdminController`. `createMenu()` inserta una pestaña por idioma con el nombre en inglés, padre `AdminCatalog` (`Sell > Catalog` en PrestaShop 9). Clases: `AdminCartCondition`, `AdminCartValueCondition`, `AdminCartQuantityCondition`, `AdminCartAssociationsCondition`, `AdminCartCountryCondition`. No hay controlador de front. La única bandera de front que lee el módulo es `cartcon=show`, añadida por la redirección del pago.

`script.tpl` desactiva **Target item** y pone el valor `Cart` en los tipos de cantidad 4, 5, 8, 9, 15 y 16. El select de país se muestra para los tipos 8 y 9 y el bloque siguiente lo oculta salvo que el tipo sea 10 u 11. El resultado visible es un campo de país solo para los tipos 10 y 11. El tipo 7 muestra `.searchAttributeValue`.

El script de asociaciones oculta `.subcatt` y `.subcata` en todos los tipos. El id de condición 4 solo está activo en categoría-categoría (tipo 3). El id 5 solo se muestra en producto-producto (tipo 1). Los ids 3, 4 y 5 ocultan **Associated item (2)**. `getRestrictions()` compara `c_value` de asociación 1, 2, 3 y 4. No compara `c_value` 5.

### 6.4 Hooks

- `displayHeader` - CSS y JS de front, y la llamada ajax `getCartConditions`.
- `displayShoppingCart` - lista de avisos.
- `displayProductActions` - aviso de cantidad mínima.
- `displayPaymentTop` - vuelta al carrito cuando hay algún error.
- `actionAdminControllerSetMedia` - recursos del admin.

El módulo no registra hooks propios.

### 6.5 Sustituciones

Ninguna. No hay sustitución de clase ni de controlador.

### 6.6 Base de datos

Tablas con prefijo. `inconsistency()` / `maybeUpdateDatabase()` añaden columnas que faltan en `installdb()` y desde el botón de actualizaciones. No se ejecutan en cada carga de la configuración. La desinstalación no borra las tablas.

| Tabla | Contenido |
|---|---|
| `cartcon` | `id_cartcon`, `c_type`, `c_value`, `c_option`, `active` por defecto 1, `id_shop` añadido después. Sin grupo de clientes. |
| `cartcon_value` | `id_cartcon_value`, `c_type`, `c_target`, `c_value`, `active`, `c_only_if_in_cart` por defecto 0, `c_group`, `id_shop`. `c_only_if_in_cart` no está en el formulario. |
| `cartcon_quantity` | `id_cartcon_quantity`, `c_type`, `c_target`, `c_value`, `active`, `c_only_if_in_cart` por defecto 0, `c_group`, `id_shop`, `multiply` por defecto 0, `c_country` por defecto 0. |
| `cartcon_ass` | `id_cartcon_ass`, `c_type`, `c_target1`, `c_target2`, `c_value`, `active`, `c_group`, `id_shop`, `subcatt` por defecto 0, `subcata` por defecto 0. El emparejado de categorías lee `subcatt` y `subcata` cuando valen 1. El formulario oculta ambos interruptores. |
| `cartcon_country` | `id_cartcon_country`, `c_type`, `c_target`, `c_value`, `active`, `c_group`, `id_shop`, `c_tax` por defecto 1, `c_cartValueType` por defecto 1. |

Las pantallas nuevas de HelperForm envían **Active** como 0 porque el radio Off está marcado. El valor por defecto 1 de la columna solo vale cuando la columna se omite.

### 6.7 Claves y traducciones

| Clave | Si falta |
|---|---|
| `CARTCON_CUSTOMERS` | vacío. Ids de cliente separados por comas. Esos clientes salen de `getRestrictions()` de inmediato. |
| `ccon_visibility_rule` | `0` significa no excluir. `1` omite productos y categorías seleccionados. |
| `ccon_visibility_products` | lista vacía de ids de producto. |
| `ccon_visibility_cat` | lista vacía de ids de categoría. |
| `CARTCON_FUTURE` | no definido, se trata como apagado. `1` ejecuta la comparación de fechas. |
| `CARTCON_FUTURE_MODE` | si falta se convierte en `0` (**Exact date**). `1` agrupa con `date('Y-m')`. Los productos comparados necesitan `stock_quantity <= 0` y `available_date` estrictamente en el futuro. Más de una clave distinta bloquea el pedido. |
| `mypresta_updates` | `0` desactiva el aviso automático. `1` lo activa. |
| `update_cartcon` | marca de tiempo de la última comprobación. |
| `updatev_cartcon` | cadena de versión de la última comprobación. |

La comprobación usa `allow_url_fopen` y `file_get_contents` contra `dev.mypresta.eu`. Las traducciones de la tienda están en `translations/{iso}.php`. Las etiquetas del menú se escriben en inglés para cada idioma dentro de `createMenu()` y no pasan por un archivo de traducción. Las descripciones de campo viven en las llamadas `l()` de los controladores y en las cadenas `desc` de HelperForm en `cartcon.php`. `getCustomerGroups()` mapea un carrito con `id_customer` 0 al id de grupo 1. La rama de invitado solo corre cuando `id_customer` no está definido.

### 6.8 Ampliación

Sobrescriba desde el tema `views/templates/front/displayShoppingCart.tpl` y `views/templates/front/productActions.tpl`. Si el tema nunca llama a `displayShoppingCart` ni a `displayProductActions`, no hay nada que sobrescribir y el cliente no verá el aviso. La redirección del pago sigue en marcha.

## 7. Ayuda

Página del módulo: [Cart Conditions Pro](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html).

Para escribir sobre este módulo, entre en la cuenta de cliente de mypresta.eu, abra el contacto y elija **Support for paid modules**. El formulario indica que el acceso es obligatorio para los módulos de pago. Después de entrar, elija este módulo en el historial de compras.

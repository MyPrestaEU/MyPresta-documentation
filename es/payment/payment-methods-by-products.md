---
title: "Métodos de pago por producto - documentación y manual del vendedor"
description: "Use este manual para fijar los métodos de pago por producto, combinarlos en el carrito y corregir una caja que sigue mostrando el método equivocado."
sidebar:
  label: "Métodos de pago por producto - documentación y manual del vendedor"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Payment methods by products en MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/payment-methods-by-products/)
>
> ---


## 1. Requisitos

Compruebe estos puntos antes de instalar.

- Use PrestaShop 1.7.0.0 o posterior, incluidos PrestaShop 8 y 9. El módulo acepta versiones de tienda hasta 9.99.99.
- Mantenga la versión de PHP que exige esa versión de PrestaShop. El instalador no comprueba PHP aparte.
- Active la extensión PHP cURL si la comprobación de actualizaciones debe contactar con MyPresta.eu. Si falta cURL, la comprobación intenta abrir la dirección con el ajuste del servidor que permite lecturas remotas. Las reglas de pago no necesitan cURL.
- No hace falta ningún otro módulo de PrestaShop. La lista de métodos sale de los módulos de pago ya instalados. Si no hay ninguno, las casillas están vacías.
- Instale y active al menos un módulo de pago si quiere que un método aparezca en la caja.
- El módulo no pide una cuenta externa.

Los textos del módulo en el back office están en inglés. Solo se entrega el polaco. Los nombres de esta guía son las denominaciones en español de esas etiquetas inglesas.

## 2. Instalación

1. Abra **Módulos** y luego **Gestor de módulos**.
2. Pulse **Subir un módulo** y suba el archivo ZIP.
3. Pulse **Instalar** en **Payment options by products**.

La instalación hace lo siguiente:

- Añade **Payment - Product associations** en **Mejorar**, luego **Pago**. Si falta ese menú, la entrada queda bajo **Mejorar**.
- Crea la tabla. Una fila es un producto, un módulo de pago, una tienda y un país.
- Registra el filtro de la caja y la pestaña de la ficha de producto.
- Copia la sobrescritura de la caja. PrestaShop debe permitir sobrescrituras. Si están apagadas, la pestaña del producto y el filtro de la caja siguen funcionando. El aviso amarillo de la configuración lo dice.
- No vacía la caché de la tienda. Vacíela en **Parámetros avanzados**, **Rendimiento**, solo si queda una pantalla antigua.
- No crea ninguna regla. La caja no cambia hasta que guarde una regla.

**Configurar** en el **Gestor de módulos** abre los ajustes. La entrada **Payment - Product associations** abre la lista de reglas.

Desinstalación:

- Quita la entrada **Payment - Product associations**.
- Quita la sobrescritura de la caja y los hooks registrados.
- Quita la versión guardada que usa la actualización.
- No borra las reglas de producto. Una instalación posterior vuelve a leer esas filas.
- No apaga los avisos de actualización compartidos con otros módulos de MyPresta.
- Deja la carpeta del módulo hasta que la borre en el **Gestor de módulos** o en el servidor.

Desactivar el módulo en el **Gestor de módulos** detiene el filtro de la caja. Las reglas siguen en la base de datos.

## 3. Configuración y trabajo en el back office

Una regla es una lista de métodos de pago para un producto, en la tienda que está editando, para un país de entrega o para todos los países.

Siga este orden:

1. Abra **Configurar** y elija cómo se combinan varios productos restringidos en un mismo carrito. Pulse **Save**. Este paso es opcional. Hasta que guarde, la tienda conserva cada método permitido por al menos un producto restringido.
2. Abra un producto y la pestaña **Payment methods**, o **Mejorar**, **Pago**, **Payment - Product associations**, y añada una fila.
3. Marque los métodos que deben seguir disponibles cuando ese producto está en el carrito. Elija **All countries** o un país. Guarde.
4. En la caja, la tienda lee la dirección de entrega y oculta los métodos que las reglas no permiten.

Un producto sin regla guardada no quita métodos de pago. **Free order** permanece cuando es el único método de un carrito a cero.

No hay un estado de pedido. El resultado es la lista de pago en la página de caja.

Las capturas de este capítulo muestran el back office en inglés. El pie usa el nombre de este manual.

### 3.1 Configuración del módulo

Abra **Módulos**, **Gestor de módulos**, **Payment options by products**, **Configurar**.

Arriba hay dos notas. El primer enlace abre **Payment - Product associations**. La segunda indica la pestaña **Payment methods** del producto. Ninguna guarda una regla.

Si las sobrescrituras están apagadas, el aviso amarillo dice: «Overrides are disabled. Checkout filtering still runs through the payment options hook.» Déjelas apagadas si solo usa PrestaShop 8 o 9. Actívelas en **Parámetros avanzados**, **Rendimiento**, solo si también necesita la sobrescritura antigua de la caja.

El panel **Settings** explica la regla de país y el modo de combinación. El texto encima del desplegable no guarda nada por sí solo.

![Settings](https://mypresta.eu/docs/images/docs/pobp-configure-settings.webp)

**Configurar**, panel **Settings**. El texto azul explica los países. La lista es **How to get available payment methods?**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **How to get available payment methods?** | **Show all payment methods from products**, hasta que guarde otra opción | **Show the same payment methods available for all products in cart** conserva un método solo si cada producto restringido del carrito lo permite. **Show all payment methods from products** lo conserva si al menos un producto restringido lo permite. Un producto sin regla no quita métodos. |
| **Save** | — | Guarda solo esa elección. No edita una regla de producto. La página se recarga con el valor elegido. |

### 3.2 Payment - Product associations

Abra **Mejorar**, **Pago**, **Payment - Product associations**. La nota superior repite que la misma regla está en el producto, en la pestaña **Payment methods**.

La lista muestra una línea por producto en la tienda actual.

![Payment - Product associations](https://mypresta.eu/docs/images/docs/pobp-associations-list.webp)

**Payment - Product associations** sin filas. Las columnas son **ID**, **Product**, **Payment** y **Country**. El signo más es **Add new**.

| Columna | Qué se ve |
|---|---|
| **ID** | El número de fila. No es el número de producto. |
| **Product** | Número y nombre del producto. |
| **Payment** | Cada método guardado para ese producto, uno debajo de otro. |
| **Country** | **All countries**, o el país de entrega guardado. El texto de la columna dice que un país elegido se aplica solo si la dirección de entrega está en ese país, y que **All countries** se aplica a cualquier dirección. |

**Add new** abre un formulario vacío. **Edit** abre el formulario de ese producto. **Delete** borra esa única fila de la base, no cada método listado en **Payment**. **Delete selected** hace lo mismo con las líneas marcadas. Este formulario rechaza una selección vacía. Borre las filas que queden, o quite la regla en la pestaña del producto, donde una selección vacía sí está permitida.

La búsqueda y los filtros de la lista son los filtros habituales del back office para estas columnas.

### 3.3 Formulario de asociación

En **Add new** o **Edit**:

![Formulario de asociación](https://mypresta.eu/docs/images/docs/pobp-associations-form.webp)

**Add new**, rellenado para esta imagen y sin guardar. **ID Product** es 1. En el formulario están **Payment methods** y **Country** (**All countries**).

| Campo | Al inicio | Qué hace |
|---|---|---|
| **ID Product** | Vacío en una fila nueva. Relleno al editar. | Escriba el número de producto o use **Search**. La ayuda dice que busque por nombre, ID o referencia. **Save** sin producto muestra «Product is required.» y no escribe una regla. |
| **Payment methods** | Sin marcar en una fila nueva. Al editar, están marcados los métodos ya guardados. | Marque los métodos que siguen en la caja cuando el carrito contiene este producto y el país de entrega coincide con el país de abajo. La etiqueta muestra el nombre del módulo de pago. |
| **Country** | **All countries** | Si elige un país, los métodos marcados se aplican solo cuando la dirección de entrega del cliente está en ese país. **All countries** los aplica a cualquier dirección. |
| **Save** | — | Sustituye todos los métodos guardados de este producto en la tienda actual por las marcas y el país de este formulario. Si no hay ninguno marcado, la página muestra «There was a problem with form. No payment method selected» y las filas anteriores se quedan. |

Un producto tiene un país. Guardar de nuevo sustituye los métodos anteriores de ese producto en esta tienda. Las reglas de otra tienda no cambian. Cambie el contexto de tienda antes de editar allí.

### 3.4 Ficha de producto

Abra **Catálogo**, **Productos**, edite el producto y abra la pestaña **Payment methods**.

![Payment methods en el producto](https://mypresta.eu/docs/images/docs/pobp-product-tab.webp)

Producto Hummingbird printed t-shirt, pestaña **Payment methods**. Ahí están **Country** y **Available payment methods**. Las marcas están solo en la imagen. El producto no se guardó.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Country** | **All countries** si el producto no tiene regla. Si no, el país ya guardado. | Si elige un país, los métodos marcados se aplican solo cuando la dirección de entrega está en ese país. **All countries** los aplica a cualquier dirección. |
| **Available payment methods** | Sin marcar si no hay regla. Si no, están marcados los métodos ya guardados. | Los métodos marcados siguen en la caja cuando el carrito contiene este producto y el país de entrega coincide con el país de arriba. No marcar ninguno quita la restricción de este producto. |

Pulse **Save** en el producto. PrestaShop confirma el guardado del producto. La regla de pago se guarda con ese mismo guardado, para la tienda que está editando. Una selección vacía borra la regla de este producto en esta tienda. El formulario de asociaciones, en cambio, no guarda si no hay nada marcado.

Los mismos datos aparecen en **Payment - Product associations**.

### 3.5 Actualizaciones de MyPresta

En **Configurar**, debajo de los ajustes, **MyPresta Updates** comprueba si hay un archivo más nuevo. No lo instala.

![MyPresta Updates](https://mypresta.eu/docs/images/docs/pobp-updates.webp)

**MyPresta Updates**, debajo de los ajustes en **Configurar**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Check updates** | — | **Check now** pregunta a MyPresta.eu si existe un archivo más nuevo. La línea sobre el botón muestra que hay una versión nueva o que el módulo está al día. No descarga ni instala el archivo. |
| **Updates notifications** | Activadas, hasta que guarde **Disable** | **Enable** muestra un aviso en el back office cuando se publica una versión más nueva. **Disable** detiene esa comprobación automática. **Save** guarda la elección y muestra «Update settings saved.» |
| **Module page** | — | Abre la página del módulo en MyPresta.eu, donde está el registro de cambios. No guarda ningún ajuste. |
| **Save** | — | Guarda solo **Updates notifications**. |

## 4. Frente de la tienda

El módulo no añade un bloque, una página ni un mensaje en el producto, el carrito o la cuenta del cliente. En esas páginas el tema no tiene nada que cambiar.

El cliente ve el efecto en el paso de pago de la caja. Los métodos que las reglas no permiten no están en la lista. Los métodos sin regla, y **Free order** cuando es la única opción, se quedan.

El país es el de la dirección de entrega. Antes de que exista una dirección, solo se aplican las reglas en **All countries**. Una regla de un país espera a que la dirección esté en ese país.

## 5. Problemas

**La lista de pago no cambió.** El producto no tiene regla, o ningún producto del carrito la tiene. Abra el producto, **Payment methods**, marque los métodos y guarde el producto. Un producto sin marcas no limita la caja.

**Un método desapareció solo para un país.** El país de la regla no es **All countries** y la dirección de entrega está en ese país. Ponga **All countries** si la regla debe valer para cualquier dirección.

**Un método sigue ofreciéndose.** Otro producto del carrito lo permite y **How to get available payment methods?** está en **Show all payment methods from products**. Cámbielo a **Show the same payment methods available for all products in cart** si cada producto restringido debe permitir el método. Un producto sin regla no lo bloquea.

**En la configuración se lee «Overrides are disabled…» y no sabe si el filtro funciona.** En PrestaShop 8 y 9 el filtro sigue. El texto amarillo dice que filtra el hook de la caja. Active las sobrescrituras solo si también depende del archivo antiguo.

**Save en Payment - Product associations muestra «Product is required.»** El campo de producto está vacío. Busque el producto o escriba su número y pulse **Save** otra vez.

**Save muestra «There was a problem with form. No payment method selected».** No hay ningún método marcado. Marque al menos uno. La regla anterior no se sustituyó. Para quitar una regla por completo, use la pestaña **Payment methods** del producto y guarde sin marcas.

**Delete en la lista quitó solo un método.** **Delete** borra la fila de esa línea, mientras **Payment** lista todos los métodos. Abra **Edit** y **Save** para reescribir el conjunto, o borre hasta que el producto desaparezca de la lista.

**Free order es el único método y la regla no lo incluye.** Un carrito a cero conserva **Free order**. El módulo no quita ese único método.

**La regla de una tienda no está en otra.** Las reglas se guardan por tienda. Cambie de tienda en la cabecera multitienda y guarde la regla allí.

## 6. Para el desarrollador

### 6.1 Visión general

Clase principal `pobp`, versión `1.4.0`, nombre **Payment options by products**, autor MyPresta.eu, pestaña `administration`. Compatibilidad de `1.7.0.0` a `9.99.99`.

Una fila de `ps_pobp` es un módulo de pago permitido para un producto, una tienda y un país (`id_country` `0` significa todos los países). La caja lee los productos del carrito y la dirección de entrega en `pobp::filterPaymentOptions()`. El hook `actionPresentPaymentOptions` quita las claves que el filtro descartó. La sobrescritura `PaymentOptionsFinder::find()` devuelve el mismo filtro si el módulo está activo. `pobp_innerjoin` verdadero significa la intersección de los productos restringidos. Cualquier otro valor, incluido un clave ausente, significa la unión. Los productos sin filas coincidentes se ignoran. La clave `free_order` nunca se quita. Una lista que solo contiene `free_order` se devuelve igual.

### 6.2 Archivos

| Archivo | Función |
|---|---|
| `pobp.php` | Instalación, formulario de ajustes, filtro de caja, pestaña de producto. |
| `lib/updatesChecker.php` | Clase `pobpUpdate`. Comprobación de actualización y formulario MyPresta Updates. |
| `lib/searchTool/searchTool.php` | Búsqueda de producto en el formulario de asociación. |
| `models/pob.php` | ObjectModel `pob` y `replaceForProduct()`. |
| `controllers/admin/AdminPobpController.php` | Lista y formulario de asociaciones. |
| `override/classes/checkout/PaymentOptionsFinder.php` | `find()` llama a `filterPaymentOptions()`. |
| `upgrade/upgrade-1.4.0.php` | Llama a `ensureModuleComplements()` y guarda `POBP_VERSION`. |
| `translations/pl.php` | Textos en polaco. |

No hay controlador ni plantilla de frente.

### 6.3 Controladores

`AdminPobpController` extiende `ModuleAdminController`. Clase de pestaña `AdminPobp`, padre `AdminParentPayment`, o `IMPROVE` si falta ese padre. Icono `credit_card`. Nombre visible **Payment - Product associations**.

La lista agrupa con una subconsulta de `MIN(id_pobp)` por producto y tienda. `processAdd()` y `processUpdate()` llaman a `pob::replaceForProduct()`. Un conjunto vacío de métodos o un producto ausente devuelve false y no sustituye filas. Los textos usan `$this->module->l(..., 'AdminPobpController')`.

La configuración del módulo es `getContent()` de `pobp`, no un controlador aparte.

### 6.4 Hooks

Registrados en `registerHooks()`:

| Hook | Función |
|---|---|
| `actionPresentPaymentOptions` | Quita los módulos de pago descartados por el filtro. El array se modifica en el sitio. |
| `actionProductFormBuilderModifier` | Añade la pestaña `pobp` (país y pagos) al formulario de producto. |
| `actionAfterUpdateProductFormHandler` | Escribe `form_data['pobp']` del producto guardado. |
| `actionAfterCreateProductFormHandler` | La misma escritura después de crear un producto. |

No hay `enable()` ni `disable()` propios. Desactivar el módulo quita los hooks. La sobrescritura sigue cargándose y devuelve la lista padre cuando `Module::isEnabled('pobp')` es falso.

La primera carga del back office tras subir archivos llama a `ensureModuleComplements()` si `POBP_VERSION` difiere de la versión del archivo.

### 6.5 Sobrescrituras

`override/classes/checkout/PaymentOptionsFinder.php` sustituye solo `find()`. No sobrescribe `present()` ni `findFree()`.

### 6.6 Base de datos

| Tabla | Contenido |
|---|---|
| `ps_pobp` | `id_pobp`, `id_product`, `id_payment` (id del módulo), `id_shop`, `id_country`. `inconsistency()` añade `id_country` si falta la columna. `0` significa todos los países. |

La desinstalación no borra `ps_pobp`. La instalación usa `CREATE TABLE IF NOT EXISTS`, así que una instalación nueva conserva las filas antiguas.

### 6.7 Claves y traducciones

| Clave | Si falta |
|---|---|
| `pobp_innerjoin` | Se trata como apagada. La caja usa la unión de los productos restringidos. |
| `POBP_VERSION` | La siguiente petición del back office ejecuta `ensureModuleComplements()` y luego guarda la versión del archivo. |
| `mypresta_updates` | Se trata como encendida. `0` detiene la comprobación automática. La clave es compartida con otros módulos de MyPresta. |
| `update_pobp` | Marca de tiempo de la última comprobación. |
| `updatev_pobp` | Cadena de versión devuelta por el servidor de actualizaciones. |

Los textos de la tienda pasan por `$this->l()`. El panel de actualizaciones usa la fuente `updatesChecker`. El controlador de asociaciones usa `AdminPobpController`. El polaco está en `translations/pl.php`. Añada otro idioma como `translations/{iso}.php` con la misma forma de clave.

`key.php` en la carpeta del módulo puede fijar `$this->mkey`. Si falta el archivo, la comprobación envía `nlc`.

### 6.8 Ampliación

El frente no renderiza una plantilla del módulo, así que el tema no tiene nada que sobrescribir. Para cambiar la lista de la caja, siga con el hook de opciones de pago o con la sobrescritura de `PaymentOptionsFinder`. Para cambiar la pestaña del producto, amplíe `hookActionProductFormBuilderModifier` y conserve las claves del formulario `pobp`; si no, el hook de guardado ignora los datos.

## 7. Ayuda

Página del módulo: [https://mypresta.eu/modules/payment-process/payment-methods-by-products.html](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)

Para escribir sobre este módulo, inicie sesión en su cuenta de cliente en mypresta.eu, abra el formulario de contacto y elija el tema **Support for paid modules**. El formulario indica que el inicio de sesión es obligatorio para ese tema. Después de entrar, elija este módulo en el historial de compras.

---
title: MyFAQ Free - documentación y manual de usuario
sidebar:
  label: MyFAQ Free - documentación y manual de usuario
description: Manual de configuración y resolución de problemas para tiendas que ya tienen MyFAQ Free.
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Free Product FAQ en MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-product-faq.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/free-product-faq/)
>
> ---


## 1. Requisitos

MyFAQ Free funciona dentro de PrestaShop. No necesita otro módulo.

- PrestaShop 1.7.0.0 hasta PrestaShop 9.
- La versión de PHP que exige esa versión de PrestaShop. El módulo no comprueba la versión de PHP por su cuenta.
- No hace falta ninguna extensión de PHP adicional. La comprobación de actualizaciones usa cURL cuando el servidor lo tiene. Si falta cURL, la comprobación lee la dirección solo cuando el servidor permite lecturas remotas.
- No hace falta otro módulo. La página de producto del tema tiene que imprimir el pie del producto o las pestañas extra del producto para que el cliente vea las preguntas.
- Para escribir y mostrar las tres preguntas no hace falta una cuenta en un servicio externo. La donación de PayPal en la página de configuración es voluntaria. La comprobación de actualizaciones solo necesita que la tienda llegue a MyPresta.eu.

Cada producto guarda tres preguntas. No hay importación, así que un catálogo grande no arranca un lote ni sube la memoria que pide el módulo.

## 2. Instalación

1. En el back office abra **Módulos** y después **Gestor de módulos**.
2. Suba el zip y pulse **Instalar**.
3. Abra **Configurar** en **MyFAQ Free**. La página se abre en **Unlock Pro**. La barra también tiene **Settings** y **Updates**.
4. MyFAQ Free no añade una entrada al menú izquierdo. Las preguntas se escriben en cada producto.

La instalación no vacía la caché de PrestaShop. Si después de una actualización la página de producto sigue con el diseño anterior, vacíe la caché en **Parámetros avanzados**, **Rendimiento**.

Para apagarlo use el interruptor del **Gestor de módulos**. La página de producto deja de imprimir las preguntas y la edición del producto deja de mostrar el bloque FAQ. Las preguntas y la colocación se quedan. Vuelva a encender el módulo y se usan como antes. El módulo no tiene un botón propio de activar o desactivar.

Para quitarlo pulse **Desinstalar** y confirme. La desinstalación borra las preguntas, la colocación, el título de la pestaña y el encabezado. Desaparece la página oculta que guarda las preguntas. Los archivos del módulo siguen en el servidor hasta que borre el módulo. Una instalación nueva empieza con preguntas vacías, **Product footer**, el título de pestaña FAQ y un encabezado vacío. Las preguntas antiguas no vuelven. El interruptor de avisos de actualización es común a otros módulos de MyPresta y se queda como lo dejó.

## 3. Configuración y trabajo diario

Las pantallas de este manual están en inglés. A partir de aquí uso los nombres de este manual y cito el texto tal como se ve en el back office.

Las preguntas se escriben en el producto, no en la página del módulo. Abra **Catálogo**, **Productos** y edite el producto. En una tienda con varias tiendas, la página del producto pide que elija una tienda en la cabecera multitienda. Abra la pestaña **Modules** y en **Module to configure** elija **MyFAQ Free**. Escriba hasta tres preguntas, marque **Show on the product page** y pulse **Save these questions**. Un hueco con la pregunta vacía se queda fuera de la página de producto.

En la página del módulo solo elige dónde se imprime ese bloque y cómo se llama. **Product footer** imprime el acordeón bajo el producto. **Product tab** añade una pestaña de producto y deja el pie vacío. Un producto sin pregunta no muestra nada en ninguno de los dos sitios.

El cliente abre el producto, pulsa una pregunta y lee la respuesta. No hay un formulario para que el cliente envíe una pregunta nueva. El recorrido termina cuando la página de producto muestra el acordeón, o cuando el producto no tiene nada que mostrar.

Abra **Módulos**, **Gestor de módulos**, **MyFAQ Free**, **Configurar**. Encima de la barra la página dice **I am developing this module for free - if you want** y ofrece **send me a donation**. Debajo hay una franja de otros módulos. La nota bajo la barra dice que las preguntas se ponen en cada producto.

### 3.1 Unlock Pro

![Unlock Pro](https://mypresta.eu/docs/images/docs/myfaqfree-configure-unlock.webp)

La pantalla es la sección **Unlock Pro**, con la línea de donación encima de la barra.

**Unlock Pro** no guarda un ajuste y no escribe preguntas. La línea bajo la barra es **MyFAQ without the three-question limit**. Dice que MyFAQ conserva cada pregunta que ya escribió y añade el catálogo, el redactor con IA y la API, y que las preguntas de un producto se quedan en el módulo gratuito hasta que las mueva.

El recuadro **The full FAQ for the catalogue** enumera lo que añade el módulo de pago y termina en **See MyFAQ**. Ese botón abre la página del módulo de pago en una pestaña nueva. Esta pestaña no guarda nada del módulo gratuito.

### 3.2 Settings

![Settings](https://mypresta.eu/docs/images/docs/myfaqfree-configure-settings.webp)

La pantalla es la sección **Settings**. La imagen muestra una tienda que ya guardó **Product tab** y un encabezado. Una instalación nueva usa los valores de la tabla.

La línea bajo la barra es **Where the three questions are shown**. Dice que el módulo gratuito escribe la FAQ en cada producto, tres preguntas como máximo, y que aquí solo elige el pie del producto o una pestaña de producto, y los nombres de ese bloque.

El título del formulario es **Placement**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Show the FAQ** | Product footer | **Product footer** imprime el acordeón bajo el producto. **Product tab** añade una pestaña de producto y deja el pie vacío. Un producto sin pregunta no muestra nada en ninguno de los dos sitios. |
| **Tab title** | FAQ en cada idioma | Nombre de la pestaña de producto cuando **Show the FAQ** es **Product tab**. Rellene cada idioma con el botón de idioma. Un idioma vacío muestra FAQ. |
| **Heading** | vacío | Título encima de las preguntas, en el pie y en la pestaña. Rellene cada idioma con el botón de idioma. Vacío muestra solo las preguntas. |

Pulse **Save**. La página muestra **Settings saved.**

El botón de idioma muestra los idiomas de esta tienda. En la tienda de la imagen son inglés, francés y polaco.

### 3.3 Updates

![Updates](https://mypresta.eu/docs/images/docs/myfaqfree-configure-updates.webp)

La pantalla es la sección **Updates**.

La línea bajo la barra es **Newer versions of MyFAQ Free**. Dice que la comprobación informa de una versión y que instalar el paquete sigue siendo una descarga manual.

El título del formulario es **MyPresta Updates**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Check updates** | **Check now** | Comprueba a mano si hay una versión nueva de este módulo en los servidores de MyPresta.eu. El botón no descarga ni instala el paquete. Después de la comprobación, junto al botón aparece **New version available!** o **Module is up to date!** |
| **Updates notifications** | Enable | Activado comprueba MyPresta.eu de forma automática y muestra un aviso de versiones nuevas de este complemento. **Disable** detiene esa comprobación automática. El interruptor es común: otros módulos de MyPresta de esta tienda usan el mismo interruptor. La comprobación automática corre más o menos cada tres días mientras se usa el back office. |
| **Module page** | un enlace llamado **MyFAQ Free** | Enlace directo a la página oficial del complemento, donde se leen los cambios del módulo (changelog). El enlace abre [https://mypresta.eu/](https://mypresta.eu/). |

Pulse **Save**. La página muestra **Update settings saved.**

Cuando se ha informado de una versión más nueva y los avisos están activos, el back office muestra **New version available, check http://MyPresta.eu for more informations** y el enlace **More details in changelog**. Ese enlace abre la misma dirección que **Module page**.

### 3.4 Preguntas en el producto

![FAQ en el producto](https://mypresta.eu/docs/images/docs/myfaqfree-product-block.webp)

La pantalla es el bloque **MyFAQ Free** del producto, en la pestaña **Modules**. La imagen es un producto que ya tiene tres preguntas. Un producto nuevo empieza con los campos vacíos. EN, FR y PL son los idiomas de esta tienda.

Abra **Catálogo**, **Productos**, edite el producto, abra **Modules** y en **Module to configure** elija **MyFAQ Free**.

En un producto que todavía no se ha guardado, el bloque dice **Save the product first** y **The three FAQ slots appear after the product has an id.** Guarde el producto y vuelva a este bloque.

El recuadro **Three questions on this product** repite la nota del módulo de pago y termina en **See MyFAQ**. No guarda las preguntas gratuitas.

Debajo, **FAQ for this product** dice: tres preguntas, una pregunta vacía se queda fuera de la página, y **Save these questions** le deja en este producto. Los botones de idioma cambian la pregunta y la respuesta. Aparecen cuando la tienda tiene más de un idioma.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Question 1**, **Question 2**, **Question 3** | tres huecos vacíos, **Show on the product page** marcado | Los tres huecos de este producto en esta tienda. El cliente los ve en este orden. |
| **Show on the product page** | marcado | Marcado muestra el hueco cuando la pregunta está rellena. Quítelo para conservar el texto y ocultar el hueco. |
| **Question** | vacío | La línea que pulsa el cliente. El campo admite 512 caracteres. Una pregunta vacía se queda fuera de la página. Escriba la pregunta en cada idioma en el que vende. Un idioma con la pregunta vacía no se muestra en ese idioma. |
| **Answer** | vacío | El texto bajo la pregunta. Un salto de línea en el campo pasa a ser una línea nueva en la página de producto. El texto que escribe se muestra como texto. |
| **Save these questions** | un botón | Guarda los tres huecos y se queda en este producto. Mientras guarda, la línea bajo el botón dice **Saving the three questions…** Tras un guardado correcto dice **The three FAQ slots are saved. A slot with an empty question stays off the product page.** |

Fuera del producto no hay una lista de preguntas ni una acción masiva. Borrar el producto borra sus tres preguntas. Las preguntas escritas en una tienda no se muestran en otra hasta que las escriba allí.

## 4. Tienda

![Preguntas en la página de producto](https://mypresta.eu/docs/images/docs/myfaqfree-front-tab.webp)

La pantalla de la tienda está en inglés.

El cliente ve el bloque solo en una página de producto, y solo cuando ese producto tiene al menos una pregunta rellena, con **Show on the product page** marcado y escrita en el idioma del cliente.

Con **Show the FAQ** en **Product footer**, el acordeón queda bajo el producto. Con **Product tab**, el mismo acordeón va dentro de una pestaña de producto y el pie queda vacío. El nombre de la pestaña es **Tab title**. Un título de pestaña vacío se muestra como FAQ. La imagen es la pestaña de esta tienda: la pestaña se llama FAQ y el encabezado es **Questions before you buy**.

El encabezado, cuando lo ha rellenado, se imprime encima de las preguntas. La primera pregunta está abierta al cargar la página. El cliente pulsa una pregunta para abrir o cerrar su respuesta. Un cliente sin JavaScript ve todas las respuestas. Bajo la lista, la línea **Powered by MyFAQ for PrestaShop** enlaza al módulo de pago.

No hay una página aparte, ni una dirección que copiar, ni un formulario para el cliente. Un producto sin nada que mostrar no imprime el bloque.

## 5. Problemas

**El producto no muestra preguntas.** La pregunta de ese idioma está vacía, **Show on the product page** está desmarcado, el módulo está apagado o el tema no imprime el sitio que eligió. Abra el producto, revise el hueco y en **Settings** confirme **Show the FAQ**. **Product footer** necesita que el tema imprima el pie del producto. **Product tab** necesita que el tema imprima las pestañas extra del producto. Un producto sin una pregunta rellena no muestra nada en ninguno de los dos sitios.

**El bloque de un producto nuevo dice Save the product first.** El producto todavía no tiene id. Guarde el producto, ábralo otra vez y aparecen los tres huecos. Si pulsa **Save these questions** antes, la línea dice **Save the product first, then add the FAQ.**

**Save these questions termina con The FAQ could not be saved.** Pulse **Save these questions** otra vez. Si sigue fallando, confirme que el módulo está instalado y que el perfil del empleado puede editar productos.

**La línea dice The FAQ could not reach the shop.** El navegador no llegó al back office. Revise la conexión y pulse **Save these questions** otra vez. Mientras dura la petición, la línea dice **Saving the three questions…**

**La pregunta en la tienda es más corta que la que escribió.** El campo de la pregunta se detiene en 512 caracteres.

**La respuesta muestra las etiquetas que escribió.** La respuesta es texto plano. El salto de línea se conserva. Las etiquetas se ven como caracteres.

**El pie queda vacío después de elegir Product tab.** Así funciona el ajuste. **Product tab** deja el pie vacío y pone el acordeón en la pestaña de producto. Elija **Product footer** en **Settings** y pulse **Save** cuando quiera el acordeón bajo el producto.

**Otra tienda no muestra las preguntas.** Los tres huecos pertenecen a la tienda que editó. Cambie la cabecera multitienda a esa tienda, abra el producto y escriba allí las preguntas.

**La página de producto del back office pide elegir una tienda.** La edición del producto trabaja en una tienda cada vez. Elija la tienda en la cabecera multitienda y después abra **Modules**.

**Check now dice Module is up to date! y usted esperaba una versión más nueva.** La comprobación no leyó una versión de MyPresta.eu, o este paquete es el que informó el servidor. Confirme que la tienda llega a MyPresta.eu y pulse **Check now** otra vez. El botón nunca instala el paquete.

**Un aviso dice New version available, check http://MyPresta.eu for more informations.** Los avisos están activos y se informó de una versión más nueva. Abra **Updates**, lea **Module page** e instale el paquete usted mismo cuando lo quiera. **Disable** en **Updates notifications** detiene el aviso. Ese interruptor es común a otros módulos de MyPresta.

**La franja de donación se queda vacía.** El resto de la página de configuración sigue funcionando. Escriba las preguntas en el producto y ponga la colocación en **Settings**.

## 6. Para el desarrollador

### 6.1 Resumen

Clase principal `myfaqfree`, versión `1.0.0`, nombre en la lista **MyFAQ Free**, autor mypresta.eu, pestaña `front_office_features`. La compatibilidad está declarada de `1.7.0.0` a `9.99.99`.

La colocación se lee de `MYFAQFREE_DISPLAY` (`footer` mientras el valor no sea `tab`). El título de la pestaña y el encabezado se leen por idioma de `MYFAQFREE_TAB_TITLE` y `MYFAQFREE_HEADING`. La página de producto carga como máximo tres huecos activos de la tienda y el idioma actuales con `MyfaqfreeRepository::frontItems()` y pinta `views/templates/hook/product.tpl`. El primer elemento recibe `is-open` en la plantilla. La respuesta se escapa y pasa por `nl2br`.

### 6.2 Archivos

- `myfaqfree.php` — instalación, configuración, panel del producto, pintado del front.
- `lib/MyfaqfreeRepository.php` — tres huecos, tablas, guardado y borrado.
- `lib/updatesChecker.php` — clase `myfaqfreeUpdate`, comprobación de actualizaciones.
- `lib/prestashop9compatibility.php` — directorios de plantillas de HelperForm y `curl_close` en PHP anterior a 8.
- `controllers/admin/AdminMyfaqfreeController.php` — guardado ajax. El controlador es una pestaña oculta.
- `views/templates/admin/configure.tpl` — Unlock Pro, Settings, Updates.
- `views/templates/admin/_pro.tpl` — recuadro del módulo de pago.
- `views/templates/admin/product.tpl` — tres huecos en el producto.
- `views/templates/hook/product.tpl` — acordeón. Variables: `mff_heading`, `mff_items` (`id`, `question`, `answer`), `mff_pro_url`.
- `views/js/admin.js` — cambio de idioma y guardado en el producto.
- `views/js/front.js` — abrir y cerrar una pregunta.
- `views/css/admin.css`, `views/css/front.css`.
- `translations/en.php` — presente y vacío. Los textos en inglés son los textos fuente.

### 6.3 Controladores

`AdminMyfaqfree` extiende `ModuleAdminController`. La pestaña se crea con `id_parent = -1`, así que no está en el menú izquierdo. El nombre de clase de la pestaña es `AdminMyfaqfree` y la etiqueta es MyFAQ Free. `ajaxProcessSave` reenvía a `myfaqfree::ajaxProcessSave()`. El bloque del producto envía `id_product`, `mff_on_{position}`, `mff_q_{position}_{id_lang}` y `mff_a_{position}_{id_lang}` a `AdminMyfaqfree` con `ajax=1` y `action=Save`.

No hay controlador de front. El acordeón se pinta desde los hooks.

`getContent()` es la página de configuración. `mff_tab` acepta `unlock`, `settings` y `updates`. Cualquier otro valor abre `unlock`.

### 6.4 Hooks

Registrados en `install()`:

| Hook | Función |
|---|---|
| `displayHeader` | CSS y JS solo en la página de producto. |
| `displayFooterProduct` | Acordeón cuando la colocación es el pie. |
| `displayProductFooter` | El mismo acordeón. Una marca estática lo imprime una vez por petición. |
| `displayProductExtraContent` | Una pestaña de producto cuando la colocación es la pestaña. Si no, un array vacío. |
| `displayAdminProductsExtra` | Los tres huecos en la edición del producto. |
| `actionAdminControllerSetMedia` | CSS y JS de administración en la página de producto y en la configuración del módulo. |
| `actionProductDelete` | Borra los huecos de ese producto. |

La clase no define `enable()` ni `disable()`. Apagar el módulo en el Gestor de módulos usa el interruptor del núcleo. La clase no registra un hook propio.

`ensureHiddenTab()` y `grantHiddenTabAccess()` se ejecutan desde el constructor cuando el objeto es `myfaqfree`, desde `getContent()` y desde el hook del producto. El acceso concede `view`, `add`, `edit` y `delete` al perfil 1 y al perfil del empleado actual.

### 6.5 Sobrescrituras

El módulo no sobrescribe una clase ni un controlador.

### 6.6 Base de datos

| Tabla | Contenido |
|---|---|
| `ps_myfaqfree_item` | `id_item`, `id_product`, `id_shop`, `position` (1–3), `active`, `date_upd`. Clave única de producto, tienda y posición. |
| `ps_myfaqfree_item_lang` | `id_item`, `id_lang`, `question` (varchar 512), `answer` (text). |

`uninstall()` borra las dos tablas cuando `parent::uninstall()` devuelve true. Si `parent::uninstall()` devuelve false, las tablas se quedan. La pestaña y las tres claves de configuración se borran antes de ese return. Borrar un producto borra sus filas en las dos tablas. Un hueco cuya pregunta está vacía en todos los idiomas se borra al guardar. Un idioma con la pregunta vacía no se inserta.

Las tablas se crean en la instalación. Abrir la página de configuración no añade una columna.

### 6.7 Claves y traducciones

| Clave | Si falta o en la instalación |
|---|---|
| `MYFAQFREE_DISPLAY` | La instalación escribe `footer`. Cualquier valor distinto de `tab` se trata como pie. |
| `MYFAQFREE_TAB_TITLE` | La instalación escribe `FAQ` para cada idioma. Un idioma vacío vuelve al texto fuente FAQ al pintar. |
| `MYFAQFREE_HEADING` | La instalación escribe una cadena vacía para cada idioma. Un encabezado vacío no se imprime. |
| `mypresta_updates` | Este módulo no lo crea. Si falta, se trata como activado. **Disable** escribe `0`. La desinstalación no lo borra. |
| `update_myfaqfree` | Tiempo Unix de la última comprobación. La desinstalación no lo borra. |
| `updatev_myfaqfree` | Cadena de versión devuelta por la comprobación. La desinstalación no la borra. |

La dirección de la comprobación es `https://dev.mypresta.eu/update/get.php`. El intervalo es 259200 segundos. Se usa cURL cuando existe `curl_init`, con un tiempo de 3 segundos. Si no, `file_get_contents` cuando `allow_url_fopen` está activo. El cuerpo de la respuesta se limpia de etiquetas y se guarda como versión disponible.

Los textos del back office pasan por `$this->l()`. El formulario de actualización usa la fuente `updatesChecker`. Añada un idioma con `translations/{iso}.php`. Textos que no pasan por `$this->l()`: **Saving the three questions…**, **The FAQ could not reach the shop.** y los recursos de JavaScript **The FAQ could not be saved.** y **Saved.** en `views/js/admin.js`. El crédito de la tienda **Powered by MyFAQ for PrestaShop** está fijo en `product.tpl`.

Las descripciones de los campos son las cadenas `desc` de `renderSettingsForm()` y de `renderUpdateForm()`.

### 6.8 Ampliación

Sobrescriba `views/templates/hook/product.tpl` desde el tema en `themes/{theme}/modules/myfaqfree/views/templates/hook/product.tpl`. Igual con `views/css/front.css` y `views/js/front.js`. La plantilla no se pinta cuando el producto no tiene un hueco visible, así que una sobrescritura del tema no tiene nada que imprimir en ese caso.

## 7. Ayuda

Página del módulo: [https://mypresta.eu/](https://mypresta.eu/)

Para preguntar por este módulo, inicie sesión en la cuenta de cliente de [mypresta.eu](https://mypresta.eu), abra el contacto y elija el tema **Support for paid modules**. El formulario dice que para ese tema hace falta iniciar sesión. Después de iniciar sesión, elija este módulo en el historial de compras. Este módulo es gratuito: si no está en ese historial, escriba **MyFAQ Free** en el mensaje.

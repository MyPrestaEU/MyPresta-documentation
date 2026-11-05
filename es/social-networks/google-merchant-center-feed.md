---
title: "Google Merchant Center Feed - manual del vendedor"
sidebar:
  label: "Google Merchant Center Feed - manual del vendedor"
description: "Cómo configurar el archivo de productos para Google Merchant Center y qué hacer cuando ese archivo falla."
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Google merchant center feed en MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/google-merchant-center-feed/)
>
> ---


## 1. Requisitos

El módulo funciona en PrestaShop 1.6, 1.7, 8 y 9, y en PHP de 5.6 a 8.5.

El servidor necesita cURL y JSON. No necesita otro módulo.

Con decenas de miles de productos, abrir la dirección del archivo tarda más y pide más memoria.

La cuenta de Google Merchant Center la crea usted.

## 2. Instalación

1. Suba el módulo en **Módulos**, **Gestor de módulos**, y actívelo.
2. Después de la instalación, **Catálogo** tiene la entrada **Google Merchant Feed**.
3. El módulo no vacía la caché al instalarse.

Desinstalar quita solo la entrada de Catálogo. La lista de archivos, los emparejamientos de categorías, los archivos guardados en el servidor y el ajuste del árbol de categorías siguen. Vuelven al instalar el módulo otra vez.

## 3. Configuración

Las capturas salen de un back office en inglés. Abajo van los nombres en español, cuando el panel en español los muestra.

### 3.1 Página de ajustes del módulo

Entre en **Módulos**, **Gestor de módulos**, **Google Merchant Center Feed**, **Configurar**. El título es **Ajustes del módulo**. Hay un campo.

![Ajustes del módulo](https://mypresta.eu/docs/images/docs/gmfeed-settings.webp)

| Campo | Al empezar | Qué hace |
|---|---|---|
| **Mostrar árbol de categorías** | **No** | **Sí** muestra las categorías padre al emparejar categorías de Google. No elige qué productos entran en el archivo. |

Pulse **Save**. Verá **Ajustes guardados correctamente**.

### 3.2 Panel de control

Entre en **Catálogo**, **Google Merchant Feed**. El título es **Feeds de Google Merchant Center**. La pestaña es **Panel de control**.

![Panel de control](https://mypresta.eu/docs/images/docs/gmfeed-dashboard.webp)

El panel muestra cuántos archivos hay guardados, cuántas veces alguien abrió una dirección hoy, cuántas veces en los últimos 7 días y cuántos archivos hay en el servidor. El gráfico y la lista de ejecuciones recientes están vacíos hasta que alguien abre una dirección. Abajo está la lista de archivos preparados para guardarse en el servidor.

### 3.3 Lista de archivos

La pestaña es **Feeds**.

![Feeds](https://mypresta.eu/docs/images/docs/gmfeed-feeds.webp)

Si la lista está vacía, verá que todavía no hay feeds y el botón **Crear nuevo feed**.

Cuando hay archivos, la fila muestra estado, nombre, tienda, última ejecución y la dirección. **Crear nuevo feed** está encima de la lista.

- El interruptor enciende y apaga el archivo. La dirección se queda.
- Un archivo en vivo tiene una dirección. Google la lee y la lista se genera en cada apertura.
- Guardar en el servidor tiene dos direcciones. La de generación construye la lista y guarda el archivo. En Google pegue la dirección del archivo, no la de generación. Si el archivo aún no existe, abra primero la dirección de generación.
- **Edit** abre el formulario. Una copia añade una marca de copia al nombre. **Delete** pide confirmación y quita la fila. El archivo en disco se queda.

### 3.4 Actualizaciones

La pestaña es **Actualizaciones**.

![Actualizaciones](https://mypresta.eu/docs/images/docs/gmfeed-updates.webp)

- **MyPresta Updates**
- **Check Now** pregunta una vez si hay una versión más nueva.
- Avisos automáticos: **Enabled** o **Disabled**. **Enabled** lo comprueba más o menos cada tres días y puede mostrar un aviso en el back office.
- **Product Page** abre la página del módulo.
- **Save** guarda estos ajustes.

### 3.5 Formulario del archivo

Pulse **Crear nuevo feed** o **Edit**. Abajo están **Save feed** y **Save & download**.

La imagen muestra la parte alta del formulario.

![Formulario del archivo](https://mypresta.eu/docs/images/docs/gmfeed-form.webp)

Un nombre vacío al guardar pasa a ser **Feed sin título**.

| Campo | Al empezar | Qué hace |
|---|---|---|
| **Feed name** | vacío, obligatorio | El nombre en la lista. |
| **Active** | **Yes** | **No** conserva la dirección. Al abrirla dice que el archivo está apagado. |
| **Shop** | la tienda actual | El campo solo aparece con varias tiendas. La dirección vale en la tienda elegida. |

### 3.6 Opciones del catálogo

| Campo | Al empezar | Qué hace |
|---|---|---|
| **Remember settings** | **Yes** | El siguiente archivo nuevo empieza con las mismas elecciones. El que acaba de guardar conserva las suyas. |

### 3.7 Qué exportar

Aquí decide qué archivo leerá Google y si la lista se genera al abrir la dirección o se guarda en el servidor.

![Qué exportar](https://mypresta.eu/docs/images/docs/gmfeed-form-export.webp)

Deje **CSV** salvo que Google deba recibir XML. **Products** es una fila por producto. La otra opción es una fila por variante. Solo entonces aparece **Combination title**. **Save to file** en **No** muestra la lista al momento. **Yes** la guarda también en el servidor. La dirección copiada de la lista ya trae la clave. Sin ella verá **Access denied**.

| Campo | Al empezar | Qué hace |
|---|---|---|
| Tipo de archivo | **CSV** | **CSV** o **XML**. |
| Qué exportar | **Products** | **Products**: una fila por producto. La otra opción: una fila por variante. |
| **Save to file** | **No** | **No**: la dirección muestra la lista al momento. **Yes**: la lista también se guarda en el servidor. Para guardar, la dirección tiene que llevar la clave de esta página. Sin la clave verá **Access denied**. Con la sesión abierta en el back office, usted guarda el archivo sin pegar la clave. |
| **File name** | vacío | Quedan letras, cifras, guion y guion bajo. Un nombre vacío se rellena con el tipo de exportación. |
| Cómo identificar el producto | id de producto | Id de producto, id de variante, o ambos. Es la columna ID del archivo. |

### 3.8 Talla, sexo, color y edad

Google pide estas columnas en ropa y productos parecidos. Empiezan apagadas. Encienda un grupo solo si la tienda tiene ese dato. El resto de campos aparece al poner el grupo en **Yes**.

![Talla, sexo, color y edad](https://mypresta.eu/docs/images/docs/gmfeed-form-attributes.webp)

| Grupo | Campos |
|---|---|
| Talla | exportar o no, atributo de talla, valor por defecto |
| Sexo | exportar o no, origen, característica, atributo, por defecto: male, female, unisex |
| Color | exportar o no, origen, atributo, característica, valor por defecto |
| Edad | exportar o no, origen, característica, atributo, por defecto: newborn, infant, toddler, kids, adult |

### 3.9 Ajustes del archivo

Aquí está el contenido de la fila: identificadores, envío, descripciones, nombres, stock, fotos y precios. Deje los valores iniciales si Google debe recibir un catálogo normal.

![Identificadores y envío](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-a.webp)

![Envío, descripciones y nombre](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-b.webp)

![Formato, idioma y stock](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-c.webp)

![Fotos y precios](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-d.webp)

La moneda y el país empiezan como la moneda y el país de la tienda. La captura muestra los del taller de prueba.

| Campo | Al empezar | Qué hace |
|---|---|---|
| Id de grupo | **No** | Columna que une las variantes de un producto. |
| Identificador único | UPC | UPC, EAN-13, referencia, MPN, ISBN o vacío. Vacío dice que el identificador no existe. |
| Campo identifier_exists | **No** | Columna de si el identificador existe. |
| Campo adult | no incluir | No incluirlo, incluirlo como true o incluirlo como false. |
| Precio de envío | no incluir | Calculado por artículo o escrito a mano. |
| Coste de envío adicional del producto | **No** | Suma el recargo de envío de la ficha del producto. |
| Importe de envío manual | 0 | El importe cuando el envío es manual. |
| Zona para calcular el envío | la primera zona | La zona de la que sale el precio de envío. |
| Peso | **No** | Columna de peso. |
| Tipo de producto | **No** | Su propia ruta de categorías en el archivo. |
| Añadir el id de categoría al tipo | **No** | El número de categoría junto al nombre. |
| Descripción corta | descripción corta | Descripción corta o descripción larga. |
| Quitar HTML de las descripciones | **No** | **Yes** quita las etiquetas. |
| Nombre del producto | nombre del producto | O el meta título. |
| Título de la variante | solo el nombre | El nombre, el nombre más el valor de la variante, o el nombre más «etiqueta: valor». |
| Formato del nombre | sin cambios | Primera letra, cada palabra o todo en minúsculas. |
| Caracteres a quitar del nombre | vacío | Los caracteres que escriba desaparecen del nombre. |
| Idioma | idioma de la tienda | Nombres y descripciones del archivo. |
| Separador | barra vertical | El carácter entre columnas CSV. |
| Comillas alrededor del texto | **No** | **Yes** envuelve los campos en comillas. |
| Información de stock | el stock real | Todos con stock, todos sin stock, todos en reserva, o la reserva como «con stock». |
| Fecha de disponibilidad | vacío | La fecha para productos en reserva que no tienen una propia. |
| Cantidad | **No** | **Yes** pone la cantidad. |
| Marca si no hay | Default | El texto de marca cuando el producto no tiene fabricante. |
| Tamaño de la foto | tamaños de la tienda | Qué tamaño de foto poner en la dirección. |
| Foto del producto si la variante no tiene | **No** | Para variantes sin foto propia. |
| Cuántas fotos | solo la principal | O todas las fotos. |
| Moneda | moneda de la tienda | Precios del archivo. |
| Impuesto en el precio | con impuesto | Con impuesto o sin impuesto. |
| Precios específicos | **Yes** | Cuando la moneda del archivo no es la moneda con la que mira la tienda. |
| Grupo de precios | grupo de visitantes | Precios para ese grupo de clientes. |
| Precio unitario | **No** | Una columna extra de precio por unidad. |
| País de los precios | país de la tienda | El país para el impuesto y los descuentos. |

### 3.10 Productos elegidos

Deje **All** si deben entrar todos los fabricantes, proveedores y categorías. Una sola elección recorta el catálogo. No sustituye las exclusiones de abajo.

![Fabricante, proveedor y categoría](https://mypresta.eu/docs/images/docs/gmfeed-form-products.webp)

| Campo | Al empezar | Qué hace |
|---|---|---|
| Fabricante | **All** | Un fabricante o todos. |
| Proveedor | **All** | Un proveedor o todos. |
| Categoría | **All** | Una categoría o todas. |

### 3.11 Exclusiones

Aquí salen los productos que pasaron el filtro del punto 3.10. Al empezar casi no se excluye nada.

![Exclusiones](https://mypresta.eu/docs/images/docs/gmfeed-form-exclude.webp)

| Campo | Al empezar | Qué hace |
|---|---|---|
| Categorías a omitir | vacío | Escriba un nombre. Los productos de esa categoría salen. |
| Productos sin foto | **No** | **Yes** omite los productos sin foto. |
| Disponibilidad | todos los productos | O solo los activados en la tienda. |
| Stock | todos los productos | O solo los que tienen stock. |
| Omitir por referencia | apagado | Activa un filtro por el inicio de la referencia. También vale para variantes. |
| Inicio de la referencia | vacío | Texto a partir del cual la referencia sale. |
| Omitir más baratos que | apagado | Un umbral de precio en la moneda de la tienda. |
| Importe del umbral | vacío | Los productos por debajo de este importe salen. |
| Productos concretos | vacío | Un buscador de productos a omitir. |

### 3.12 Límite

Deje 0 si todo el catálogo debe ir en un archivo. Al lado se ve cuántos productos hay en la tienda. Con un hosting justo, ponga un límite y un número de parte. El formulario pone el ejemplo: 3000 productos y un límite de 1000 dan las partes 1, 2 y 3.

![Límite y código de tienda](https://mypresta.eu/docs/images/docs/gmfeed-form-limit.webp)

| Campo | Al empezar | Qué hace |
|---|---|---|
| Límite de productos | 0 | 0 o vacío significa sin límite. Al lado se ve el número de productos de la tienda. |
| Parte del archivo | 0 | El número de parte cuando parte un catálogo en varios archivos. Con 3000 productos y un límite de 1000 hace las partes 1, 2 y 3. |

### 3.13 Código de tienda física

| Campo | Al empezar | Qué hace |
|---|---|---|
| Incluir el código de tienda | **No** | Una columna para el código de la tienda física. |
| Código de tienda | vacío | El mismo código que en Google Business. Importan mayúsculas y minúsculas. |

### 3.14 Categorías de Google

Abajo hay una fila por idioma de la tienda. **Pair categories** abre el emparejamiento. **Synchronize** trae la lista de Google de ese idioma. Si falta la lista, el botón sale en rojo. En la captura en-us ya tiene el archivo y fr todavía no.

![Categorías de Google](https://mypresta.eu/docs/images/docs/gmfeed-form-categories.webp)

**Mostrar árbol de categorías** del punto 3.1 solo cambia el dibujo de esta lista. Abajo están otra vez **Save & download** y **Save feed**.

**Mostrar árbol de categorías** del punto 3.1 solo cambia el dibujo de esta lista. No cambia qué productos entran en el archivo.

## 4. Tienda

El cliente no ve nada en la tienda. No hay bloque en la ficha, en el carrito ni en el pie. No hay captura de la tienda.

Hay una dirección que abre Google o el navegador. Cópiela de la lista. No la arme usted.

Una apertura en vivo devuelve CSV o XML. Al guardar en el servidor, la dirección de generación escribe el archivo, y la dirección para Google es la del archivo.

Añadir parámetros propios no cambia nada. El módulo usa los ajustes guardados en ese archivo.

Guardar el formulario no envía productos a Google. La lista se genera al abrir la dirección.

| Qué ve al abrirla | Qué hacer |
|---|---|
| feed does not exists | El número no vale o el archivo se borró. Copie la dirección de la lista. |
| Feed is disabled | Encienda **Active**. |
| Feed is not available in this store | El archivo es de otra tienda. |
| Access denied | El guardado en el servidor está encendido y la dirección no trae la clave. Copie la dirección de la lista. |
| Invalid export path | Acorte el nombre del archivo. |
| Unable to save export file | Revise el espacio y el permiso de escritura en la carpeta del módulo. |

## 5. Problemas

**Google sigue mostrando los productos de ayer.** El módulo no envía nada a Google. Abra la dirección y compruebe la lista. Después descárguela a mano en Merchant Center.

**En el archivo casi no hay productos.** Mire si quedaron solo productos activos, solo con stock, un fabricante, un proveedor, una categoría, exclusiones, un límite o un número de parte.

**El árbol de categorías está encendido y el archivo tiene los mismos productos.** El árbol solo muestra las categorías padre al emparejar.

**Desinstalé el módulo y la lista desapareció.** Instálelo otra vez. Los datos siguen. Solo desapareció la entrada de Catálogo.

**Un catálogo grande se corta a la mitad.** Ponga un límite y un número de parte. Haga varios archivos.

## 6. Para el desarrollador

### 6.1 Visión general

`gmfeed` 2.4.3. La clase `gmfeed` extiende `Module`. El nombre en la lista de módulos es el texto fijo `Google Merchant Center Feed`. Autor MyPresta.eu. Pestaña `administration`.

El formulario guarda una fila `gms`. El campo `conf` es una cadena de consulta. La dirección pública lee esa fila, construye CSV o XML y termina la respuesta. Guardar en archivo lo escribe en `/modules/gmfeed/`.

### 6.2 Archivos

- `gmfeed.php`: install, uninstall, la página de ajustes, la clave de escritura y la limpieza del nombre, la extensión y el tipo.
- `controllers/admin/AdminExportProductsFeedGoogle.php`: panel, lista, formulario, guardado.
- `controllers/front/feed.php`: generación. `initContent()` llama a `generateFeed()` y `die()`.
- `model/gms.php`: la fila del archivo y la dirección. Clase `gms`.
- `model/google.php`: pares de categorías. Clase `pixelgoogle`.
- `lib/updateChecker.php`: clase `gmfeedUpdate`.
- `lib/searchTool/searchTool.php`: sugerencias de categorías y productos.
- `views/templates/admin/`: `layout.tpl`, `dashboard.tpl`, `feeds.tpl`, `form-chrome.tpl`.
- `google/en-us.txt`: la taxonomía. Primera línea `# Google_Product_Taxonomy_Version: 2015-02-19`.
- `.htaccess` en la carpeta del módulo bloquea la ejecución de PHP.

### 6.3 Controladores

Admin: `AdminExportProductsFeedGoogle`, padre `AdminCatalog`. Vistas en `gmfeed_view`: `dashboard`, `feeds`, `form`, `updates`.

Front: `gmfeedfeedModuleFrontController`. Dirección `module/gmfeed/feed?feed=` y el número.

La clave de escritura es HMAC-SHA256 de `gmfeed.write.` más el id de tienda, secreto `_COOKIE_KEY_`. Un empleado conectado escribe sin la clave. Los parámetros `export_` y `gmfeed_` que llegan se descartan y se sustituyen por los guardados. Quedan la clave y `debug_feed`.

Un archivo apagado responde HTTP 503 y `Feed is disabled`. Un `conf` vacío o demasiado corto termina en `feed does not exists`. Otro `id_shop` termina en `Feed is not available in this store`.

### 6.4 Hooks

Hay un hook: `actionAdminControllerSetMedia`. Carga fancybox y autocomplete solo en `AdminExportProductsFeedGoogle`. El módulo no publica hooks propios. No hay `enable()` ni `disable()`.

### 6.5 Sobrescrituras

Este módulo no sobrescribe clases ni controladores de PrestaShop.

### 6.6 Base de datos

| Tabla | Contenido |
|---|---|
| `pixelgoogle` | Un par de categorías: `id_google`, `id_category`, `id_lang`, `value`. |
| `gms` | Un archivo: `name`, `id_shop`, `conf`, `active`. `CREATE` no pone clave primaria. |
| `gms_log` | Una apertura de la dirección: hora, número, estado, guardado de archivo, nombre, formato, origen. |

`ensureSchema` en la página de catálogo añade `active` e `id_shop`, crea `gms_log` si falta y rellena `id_shop` 0 con la tienda por defecto. La desinstalación no borra las tablas.

### 6.7 Claves y traducciones

`pf_tree`: si falta la clave, está apagado. El resto del formulario vive en `gms.conf`. **Remember settings** enviado como 1 copia los campos a `gm_{campo}`, sin la clave de escritura, el enlace corto, activo, la tienda y el id del archivo. Con un archivo abierto, un campo ausente usa el valor inicial del formulario, no la copia `gm_`. Una clave antigua `notepad_products` se copia a `gmfeed_products` si falta la nueva.

Actualizaciones: `mypresta_updates`, `update_gmfeed` (172800 segundos entre comprobaciones), `updatev_gmfeed`. Si falta `mkey`, se envía `nokey`.

Un idioma nuevo es un archivo `translations/{iso}.php`. Los textos de `$this->l()` salen de la fuente inglesa. El nombre en la lista de módulos no pasa por `$this->l()`. En `translations/de.php` los textos de la página de ajustes están en checo.

El tipo de exportación guardado como `product` se trata como `products` al generar. Las extensiones permitidas son `csv`, `xml` y `txt`. El formulario muestra CSV y XML.

### 6.8 Ampliar

El tema no tiene nada que sobrescribir en la tienda, porque el front no pinta una plantilla. Otro orden de columnas exige cambiar el código del módulo. Una taxonomía en otro idioma se añade como `google/{codigo}.txt`.

## 7. Soporte

Página del módulo: [Google Merchant Center Feed](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html).

Para escribir sobre este módulo, inicie sesión en su cuenta de cliente en [mypresta.eu](https://mypresta.eu/), vaya al [contacto](https://mypresta.eu/contact.html) y elija el asunto **Support for paid modules**. El formulario indica que el inicio de sesión es obligatorio. Después de entrar, elija este módulo en el historial de compras.

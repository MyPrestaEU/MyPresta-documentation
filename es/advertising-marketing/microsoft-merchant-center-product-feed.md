---
title: "Microsoft Merchant Center Product Feed - documentación y manual de usuario"
description: "Manual para usuarios que ya tienen el módulo y necesitan configurar feeds de Microsoft Merchant Center o resolver problemas de generación y catálogo."
sidebar:
  label: "Microsoft Merchant Center Product Feed - documentación y manual de usuario"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Microsoft Merchant Center Product Feed en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-product-feed.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/microsoft-merchant-center-product-feed/)
>
> ---


## 1. Requisitos

Antes de instalar el módulo, compruebe que la tienda y el alojamiento cumplen estos requisitos:

- PrestaShop 1.7, 8 o 9.
- PHP de la versión 7.1 a la 8.5.
- Extensiones PHP: cURL, JSON, hash y SimpleXML cuando genere feeds XML.
- Una cuenta activa de Microsoft Merchant Center donde pueda crear un catálogo e indicar la dirección de su feed.
- No se necesita ningún otro módulo de PrestaShop.

Un catálogo grande necesita suficiente tiempo de ejecución y memoria PHP para recopilar productos, calcular precios y envíos y crear la salida. Si un feed completo supera los límites de su alojamiento, use **Limit number of products in feed** junto con **Part of feed** para dividirlo en feeds más pequeños.

## 2. Instalación

1. Abra **Modules → Module Manager**.
2. Haga clic en **Upload a module** y cargue el archivo ZIP del módulo.
3. Instale **Microsoft Merchant Center Feed**.
4. Abra **Catalog → Microsoft Merchant Feed**. Este es el espacio de trabajo para crear feeds, copiar direcciones del catálogo, supervisar ejecuciones y emparejar categorías.
5. Si se repiten nombres de categorías en distintas ramas del catálogo, abra **Modules → Module Manager**, busque el módulo, haga clic en **Configure** y active **Show categories tree**.

La instalación no vacía la caché de PrestaShop.

Para eliminar el módulo, desinstálelo en **Module Manager**. La desinstalación quita **Microsoft Merchant Feed** del menú **Catalog**, pero conserva feeds guardados, historial de generación, emparejamientos de categorías, ajustes recordados del formulario, archivos de catálogo generados y datos de taxonomía descargados. Por tanto, una reinstalación puede reutilizar los datos conservados.

## 3. Configuración y flujo de trabajo del back office

Siga este proceso para publicar un catálogo:

1. Abra **Catalog → Microsoft Merchant Feed** y seleccione **Create new feed**.
2. Introduzca un **Feed name**, deje **Active** en **Yes**, seleccione las opciones de salida y producto, empareje **Microsoft Categories** y haga clic en **Save feed**.
3. Elija un método de publicación:
   - Para un feed en directo, deje **Save to file** en **No**. Copie la **Live catalog URL**. Microsoft solicita esta dirección y el módulo regenera el feed en cada solicitud.
   - Para un archivo estático, establezca **Save to file** en **Yes**. Llame a la **Generate / cron URL** secreta manualmente o desde un programador. Tras la primera generación correcta, copie la **Catalog file URL**. Facilite a Microsoft Merchant Center la dirección del archivo de catálogo, nunca la dirección de generación.
4. Cree o abra el catálogo correspondiente en Microsoft Merchant Center y pegue la dirección en directo o del archivo como fuente del feed.
5. Vuelva a **Dashboard** para confirmar que se registran las ejecuciones y que hay un archivo guardado disponible si usa el modo de archivo.
6. Abra la sección **Microsoft Categories** del feed, sincronice la taxonomía para el idioma del feed y use **Pair categories** para conectar las categorías de la tienda con las de Microsoft Shopping.
7. Para pausar la publicación sin cambiar la dirección, desactive el feed en **Feeds**. **Active** en **No** detiene la generación; al volver a activarlo se reanuda el mismo feed en la misma dirección.

Las capturas de este manual proceden de un back office en inglés.

### 3.1 Ajustes del módulo

Abra **Modules → Module Manager**, busque **Microsoft Merchant Center Feed** y haga clic en **Configure**.

![Ajustes del módulo con Show categories tree](https://mypresta.eu/docs/images/docs/mmcfeed-module-settings.webp)

| Campo | Valor inicial | Función |
|---|---|---|
| **Show categories tree** | No | El espacio de trabajo está en **Catalog → Microsoft Merchant Feed**. Allí puede emparejar categorías de la tienda con categorías de Microsoft Shopping. Establezca este campo en **Yes** para mostrar la ruta principal de cada categoría en la ventana de emparejamiento. Las rutas permiten distinguir categorías con el mismo nombre. Haga clic en **Save**; la página confirma **Settings saved properly**. |

### 3.2 Lista de feeds

Abra **Catalog → Microsoft Merchant Feed** y seleccione **Feeds**.

![Lista de feeds](https://mypresta.eu/docs/images/docs/mmcfeed-feeds.webp)

Si no existe ningún feed, la página muestra **You have no feeds yet** y **Create your first feed**. En caso contrario, use estas columnas:

| Columna | Qué muestra |
|---|---|
| **Status** | **On** u **Off**. Use el interruptor para pausar o reanudar el feed sin eliminarlo ni cambiar su dirección. |
| **Feed** | Nombre del feed y distintivos de formato, exportación de productos o variantes, idioma y modo **Live** o **File**. |
| **Shop** | Tienda a la que pertenece el feed. En multitienda, un feed ajeno a la tienda actual aparece como **Not available in this store**. |
| **Last run** | Número de elementos generados y hora de la última ejecución. Antes de la primera llamada muestra **Never** y **No cron call yet**. |
| **Catalog URL** | En modo directo, la dirección **Live catalog**. En modo de archivo, la dirección secreta **Generate / cron** y la dirección pública **Catalog file**. Copie cada dirección con el botón contiguo. |
| **Actions** | Comandos disponibles para el feed. |

Utilice las acciones así:

- **Edit** abre todas las opciones guardadas.
- **Duplicate** crea una copia y la abre para revisarla. Cambie nombre, nombre de archivo, tienda, filtros u otros ajustes antes de guardar cuando la copia deba ser independiente.
- **Generate** llama al generador en modo de archivo.
- **Open file** abre el archivo guardado en modo de archivo.
- **Open** genera y abre un feed en directo.
- **Delete** elimina definitivamente el registro tras la confirmación.

Después de una operación, la página puede mostrar:

- **Feed saved. Its catalog URL is ready to use.**
- **Feed removed.**
- **Feed duplicated. Review the copy and save if you need a different filename or URL.**

### 3.3 Dashboard

Seleccione **Dashboard** para supervisar la actividad.

![Dashboard](https://mypresta.eu/docs/images/docs/mmcfeed-dashboard.webp)

El resumen muestra **Saved feeds**, ejecuciones correctas en **Cron runs today**, productos generados hoy, **Runs last 7 days**, duración media de generación y número de **Saved files** preparados. **Catalog generation activity** representa los últimos 14 días. **Recent runs** enumera feed, hora, cantidad de elementos, duración, formato y si se escribió un archivo.

La tabla **Generated files** muestra cada feed en modo de archivo con tienda, nombre, tamaño, estado y última actualización. **Waiting for first cron** significa que el feed está guardado, pero la dirección de generación aún no ha producido su archivo. **On disk** significa que el archivo está disponible en su dirección de catálogo.

### 3.4 Pestaña Updates

Seleccione **Updates** para comparar el módulo instalado con las actualizaciones de MyPresta.

![Pestaña Updates](https://mypresta.eu/docs/images/docs/mmcfeed-updates.webp)

| Campo | Valor inicial | Función |
|---|---|---|
| **Manual Check** | Sin resultado hasta comprobar | Haga clic en **Check Now** tras instalar o cuando espere una versión nueva. El módulo contacta una vez con el servicio, compara versiones e informa inmediatamente de **Module is up to date!** o **New version available!**. |
| **Automatic Notifications** | Preferencia compartida actual de MyPresta | Use **Enabled** para comprobar en el back office aproximadamente cada tres días y avisar a los empleados si existe una versión más reciente. Use **Disabled** si realiza comprobaciones manuales. Haga clic en **Save**. |
| **Product Page** | Enlace disponible | Abra la página oficial del módulo para consultar información y recursos de soporte. No requiere configuración. |

### 3.5 Crear/editar un feed

Seleccione **Create new feed** o haga clic en **Edit** junto a un feed. Los campos aparecen en el siguiente orden de pantalla. Las opciones dependientes de la tienda proceden de los idiomas, monedas, países, grupos, tipos de imagen, características, atributos, categorías, fabricantes, proveedores, zonas y tiendas configurados en PrestaShop.

Haga clic en **Save feed** para guardar y volver a la lista. Haga clic en **Save & download** para guardar y descargar de inmediato un CSV o XML recién generado. Al editar, la página muestra también la **Live catalog URL** correspondiente o la **Generate / cron URL** y la **Catalog file URL**.

![Crear o editar un feed: nombre, estado, formato, tipo y modo de archivo](https://mypresta.eu/docs/images/docs/mmcfeed-form-top.webp)

**Identidad y salida del feed**

| Campo | Valor inicial | Función |
|---|---|---|
| **Feed name** | Vacío | Introduzca un nombre obligatorio y reconocible para la lista. Si una entrega vacía llega al guardado, se almacena como **Untitled feed**. |
| **Active** | Yes | Déjelo activado para permitir la generación. Use **No** para pausar el feed conservando dirección y ajustes. |
| **Shop** | Tienda actual; solo en multitienda | Asigne el feed a una tienda. Su dirección solo funciona para esa tienda. |
| **Remember settings** | Yes | Guarda las opciones como valores iniciales del próximo feed. Use **No** si estas opciones no deben convertirse en valores recordados. |
| **Type of file module will generate** | CSV | Elija **CSV** para un feed de texto o **XML** para uno Atom. Para TSV, elija **CSV** y establezca **Delimiter** en `Tab`; TSV es una salida CSV con tabulador. |
| **What you want to export?** | Products | Elija **Products** para una fila por producto o **All products variants** para exportar combinaciones por separado. |
| **Save to file** | No | **No** hace que el feed sea directo y lo devuelve al llamar a su dirección. **Yes** hace que la dirección de generación escriba un archivo estático; programe esa dirección secreta y entregue a Microsoft la dirección independiente del archivo. |
| **File name** | Vacío | Con **Save to file** activado, introduzca el nombre base del archivo. Si queda vacío, el módulo usa el tipo de exportación. Use letras, números, guiones o guiones bajos. |
| **How to identify product?** | `id_product` | Elija `id_product`, `id_combination` o `id_product-id_attribute`. Este valor será el ID único. Use una opción compatible con combinaciones si exporta variantes por separado. |

**Talla, género, color y grupo de edad**

![Campos de talla, género, color y edad](https://mypresta.eu/docs/images/docs/mmcfeed-form-attributes.webp)

| Campo | Valor inicial | Función |
|---|---|---|
| **Export size** | No | Use **Yes** para incluir `size`. |
| **Size attribute** | None | Seleccione el grupo de atributos que contiene la talla. Mantenga Ctrl al hacer clic para elegir varios. Los productos sin valor usan **Default size value**. |
| **Default size value** | Vacío | Indique la talla alternativa cuando no haya valor en el grupo seleccionado. |
| **Export gender** | No | Use **Yes** para incluir `gender`. |
| **Export gender value from** | Ninguna fuente | Elija **Attribute** o **Feature** como fuente y complete el campo correspondiente. |
| **Gender feature** | Ninguna característica | Si la fuente es **Feature**, seleccione la característica que almacena el género. |
| **Gender attribute** | Ningún atributo | Si la fuente es **Attribute**, seleccione el grupo que almacena el género. |
| **Default gender value** | Vacío | Elija **Male**, **Female** o **Unisex** como alternativa si no hay valor. |
| **Export color** | No | Use **Yes** para incluir `color`. |
| **Export color value from** | Ninguna fuente | Elija **Attribute** o **Feature** como fuente del color. |
| **Color attribute** | Ningún atributo | Si la fuente es **Attribute**, seleccione el grupo que almacena el color. |
| **Color feature** | Ninguna característica | Si la fuente es **Feature**, seleccione la característica que almacena el color. |
| **Default color value** | Vacío | Introduzca el valor alternativo. Use nombres de colores en inglés, que son los que Microsoft acepta en este campo. |
| **Export age_group** | No | Use **Yes** para incluir `age_group`. |
| **Export age group value from** | Ninguna fuente | Elija **Attribute** o **Feature** como fuente del grupo de edad. |
| **age group feature** | Ninguna característica | Si la fuente es **Feature**, seleccione la característica del grupo de edad. |
| **age group attribute** | Ningún atributo | Si la fuente es **Attribute**, seleccione el grupo correspondiente. |
| **Default age group value** | Sin alternativa | Elija **adult**, **kids**, **toddler**, **infant** o el valor mostrado **newbord**. Use los valores admitidos por Microsoft en producción. |

**Campos, envío, texto, existencias, imágenes y precios**

![Ajustes con identificadores, envío, descripciones, idioma y delimitador](https://mypresta.eu/docs/images/docs/mmcfeed-form-feed-settings.webp)

| Campo | Valor inicial | Función |
|---|---|---|
| **Include item_group_id** | No | Use **Yes** para agrupar variantes que difieren por talla, color, patrón, edad o género, de modo que Microsoft las trate como variantes de un producto. |
| **Unique product identifier** | Product UPC barcode | Elija el campo para GTIN o identificadores: **Product UPC barcode**, **Product ean13 / JAN barcode**, **Product reference number**, **Product MPN code**, **Product ISBN code** o **Make this field empty, identifier_exists field will have value false then**. Proporcione identificadores del fabricante siempre que existan. |
| **Include identifier_exists field** | No | Use **Yes** para añadir `identifier_exists`, que indica si el artículo tiene identificador único. |
| **Include adult field** | Do not include | Elija **Include as true**, **Include as false** o **- do not include -**. El formulario muestra además la etiqueta no relacionada **Lowercase all letters, example: product name**; no la use aquí. |
| **Include shipping price** | Do not include | Elija **Do not include**, **Include (shipping price calculated for each item separately)** o **Set shipping price manually**. El cálculo automático es específico de cada producto; el manual aplica un importe. |
| **Include product's additional shipping cost** | No | Use **Yes** para sumar el coste adicional propio del producto. |
| **Manual shipping value** | 0 | En modo manual, introduzca el importe aplicado a cada artículo. |
| **Automatic shipping price zone select** | Zona inicial de la tienda | En modo automático, elija la zona de destino. El cálculo individual consume más recursos que un importe fijo. |
| **Include weight** | No | Use **Yes** para incluir el peso en la unidad de la tienda. |
| **Product type** | No | Use **Yes** para incluir la estructura de categorías como `product_type`. |
| **Product type - include category ID** | No | Con **Product type** activo, use **Yes** para añadir el ID y distinguir categorías homónimas. |
| **Short description** | Short description | Elija **Short description** o **Long description** como origen de la descripción. |
| **Remove html from descriptions** | Yes | Microsoft exige texto sin formato. Las etiquetas y saltos problemáticos se eliminan incluso con **No**; mantenga **Yes** como recordatorio del resultado. |
| **Product name** | Product name | Elija **Product name** o **Meta title** como origen del título. |
| **Format name** | Do not format name | Déjelo igual, ponga en mayúscula la primera letra o cada palabra, o pase todo a minúsculas. Úselo si Microsoft rechaza títulos completamente en mayúsculas. |
| **Remove selected characters from product name** | Vacío | Escriba cada carácter que desee eliminar; `x=,` elimina `x`, `=` y `,`. Deje el campo realmente vacío para no eliminar nada. |
| **Language** | Idioma predeterminado | Elija el idioma de títulos, descripciones y demás datos traducidos. |
| **Delimiter** | `|` | Establezca el separador CSV. Introduzca `Tab` para TSV, recomendado por Microsoft. También puede usar barra vertical o coma. No afecta a XML. |
| **Wrap strings in double quotes** | Yes | Manténgalo activo para que separadores o caracteres especiales no rompan las filas CSV. |
| **Information about stock** | Include real stock information | Use disponibilidad real o fuerce **in-stock**, **out-of-stock** o **backorder**. La última opción informa como disponibles los productos con pedidos pendientes habilitados. |
| **Availability date** | Vacío | Introduzca una fecha alternativa para productos pendientes sin fecha individual. Microsoft la exige. |
| **Include quantity info** | No | Use **Yes** para incluir la cantidad del producto o combinación. |
| **Default manufacturer value** | `Default` | Introduzca la marca alternativa para productos sin fabricante. |
| **Image size for product pictures** | Tipo inicial dependiente de la tienda | Elija el tipo de imagen de PrestaShop usado en las direcciones. |
| **Use default product picture if combination will not have associated photo** | No | Use **Yes** para utilizar la imagen principal si una combinación no tiene foto. |
| **How many pictures you want to export?** | Export cover only | Elija **Export cover only** o **Export all pictures**. La segunda opción añade enlaces adicionales. |
| **Currency** | Moneda predeterminada | Elija la moneda exportada y hágala coincidir con el mercado del catálogo. |
| **Price tax included or excluded** | Price Tax Included | Elija si los precios normales y rebajados incluyen impuestos. |
| **Include specific prices** | Yes | Manténgalo activo si los precios específicos de PrestaShop deben reflejarse. |
| **Export prices for selected group** | Grupo de clientes no identificados | Elija el grupo cuyo contexto de precio usará el módulo. |
| **Export also unit price** | No | Use **Yes** para incluir información de precio unitario disponible en feeds de variantes. |
| **Export prices for selected country** | País predeterminado | Elija el contexto nacional para impuestos y descuentos. |

**Selección, exclusiones, límites, inventario local y categorías**

![Filtros, límites, código de tienda y Microsoft Categories](https://mypresta.eu/docs/images/docs/mmcfeed-form-filters.webp)

| Campo | Valor inicial | Función |
|---|---|---|
| **Product Manufacturer** | All | Exporte todos los fabricantes o solo el seleccionado. |
| **Product Supplier** | All | Exporte todos los proveedores o solo el seleccionado. |
| **Product Category** | All | Exporte todas las categorías o limite a una. |
| **Exclude categories** | Vacío | Busque categorías y añádalas. Se omiten los productos asignados a una categoría excluida. |
| **Exclude products without pictures** | No | Use **Yes** para omitir productos sin imagen utilizable. |
| **Products's availability** | Export all products | Elija **Export only active products** para omitir desactivados. |
| **Products's stock** | Export all products | Elija **Export only in-stock products** para omitir productos sin existencias. |
| **Exclude products with specific reference** | No | Use **Yes** para filtrar por prefijo de referencia. |
| **Exclude product where reference starts with:** | Vacío | Introduzca el prefijo. Se aplica a productos y combinaciones. |
| **Exclude products worth less than defined value** | No | Use **Yes** para omitir productos bajo un mínimo en la moneda predeterminada. |
| **Value of products (worth less) to exclude** | Vacío | Introduzca el mínimo utilizado por el filtro anterior. |
| **Exclude products** | Lista vacía | Escriba un nombre y seleccione el producto. **Add all search results** añade todos los resultados; quite elementos con su botón. |
| **Limit number of products in feed** | 0 | Indique el máximo. Vacío o `0` elimina el límite. Úselo si el catálogo supera el tiempo o la memoria disponibles. |
| **Part of feed** | 0 | Use `0` si no divide el feed. Para 3.000 productos con límite 1.000, cree feeds equivalentes con partes 1, 2 y 3. |
| **Include store code to feed** | No | Use **Yes** para un feed de inventario local que identifique una tienda física. Use el mismo identificador de su cuenta Microsoft. |
| **Store code** | Vacío | Introduzca el identificador alfanumérico exacto, respetando mayúsculas. |
| **Microsoft Categories** | Taxonomía quizá no sincronizada | Compruebe cada idioma. Haga clic en **Synchronize** o elija una fuente en **Synchronize specific**. Después use **Pair categories**, busque la categoría Microsoft adecuada y guarde. El icono de repetición aplica un valor a todos los campos; el de papelera elimina el emparejamiento. |

## 4. Tienda y direcciones del feed

El módulo no añade bloques, botones, contenido de producto, formularios, páginas de cuenta ni otra interfaz a la tienda. Los clientes no interactúan con él.

Los servicios externos usan la dirección copiada de **Feeds**:

- **Live catalog URL** regenera y devuelve el catálogo en cada solicitud; no guarda archivo.
- **Generate / cron URL** contiene el secreto para escribir un archivo. Llámela desde un programador o con **Generate**. No se la entregue a Microsoft.
- **Catalog file URL** apunta al archivo estático. Úsela como fuente cuando **Save to file** está activo.

| Qué ve | Qué debe hacer |
|---|---|
| **Feed is disabled** | Abra **Feeds** y active **On**, o establezca **Active** en **Yes**. |
| **feed does not exists** | Copie de nuevo la dirección desde **Feeds**. El feed se eliminó, la dirección está incompleta o la configuración no es válida. |
| **Feed is not available in this store** | Cambie a la tienda asignada, edite **Shop** y copie su dirección. |
| **Access denied** | Use la **Generate / cron URL** completa. No quite ni modifique su parte secreta. |

## 5. Problemas y soluciones

### 5.1 El feed indica que está desactivado

**Síntoma:** La dirección muestra **Feed is disabled**.

**Causa:** El interruptor está apagado o **Active** está en **No**.

**Acción:** Abra **Catalog → Microsoft Merchant Feed → Feeds** y póngalo en **On**. La dirección existente sigue siendo válida.

### 5.2 El feed no existe

**Síntoma:** Aparece **feed does not exists**.

**Causa:** La dirección corresponde a un feed eliminado, está incompleta o la configuración no es utilizable.

**Acción:** Copie de nuevo la dirección en **Feeds**. Si no existe, créelo y guárdelo.

### 5.3 El feed pertenece a otra tienda

**Síntoma:** Aparece **Not available in this store** o **Feed is not available in this store**.

**Causa:** Está asignado a otra tienda del entorno multitienda.

**Acción:** Cambie a la tienda asignada o edite **Shop**, guarde y copie la nueva dirección.

### 5.4 La generación de archivo indica acceso denegado

**Síntoma:** El generador muestra **Access denied** y no actualiza el archivo.

**Causa:** Falta la autorización secreta incluida por el módulo.

**Acción:** Copie otra vez **Generate / cron URL** y úsela sin cambios en el programador. Manténgala privada.

### 5.5 Microsoft recibe la respuesta del generador

**Síntoma:** La recuperación programada falla o genera en cada solicitud aunque **Save to file** está activo.

**Causa:** Se pegó la **Generate / cron URL** en Microsoft Merchant Center.

**Acción:** Use esa dirección solo en su programador. Ejecútela, confirme **On disk** en **Dashboard** y pegue **Catalog file URL** en Microsoft.

### 5.6 El feed está vacío o faltan productos

**Síntoma:** La generación funciona, pero devuelve menos elementos de los esperados.

**Causa:** Los filtros de fabricante, proveedor, categoría, exclusiones, imagen, estado, existencias, referencia, valor mínimo, límite o parte eliminan productos.

**Acción:** Revise todos los campos de selección y exclusión. Elija temporalmente **All**, desactive exclusiones, vacíe listas y ponga límite y parte en `0`. Genere de nuevo y reintroduzca filtros uno a uno.

### 5.7 Faltan categorías de Microsoft

**Síntoma:** No hay valores útiles o **Pair categories** no puede buscar.

**Causa:** La taxonomía del idioma no está sincronizada o faltan emparejamientos.

**Acción:** En **Microsoft Categories**, pulse **Synchronize**. Si no está disponible, use **Synchronize specific**. Cuando el archivo esté disponible, pulse **Pair categories** y complete las asignaciones.

### 5.8 Un catálogo grande agota tiempo o memoria

**Síntoma:** La generación se detiene, tarda demasiado o no actualiza el archivo.

**Causa:** El alojamiento no puede procesar catálogo, precios, imágenes y envío automático en una ejecución.

**Acción:** Defina **Limit number of products in feed** y cree feeds con valores consecutivos de **Part of feed**. Si procede, use un importe manual de envío y programe las partes por separado.

### 5.9 Microsoft informa de problemas de calidad

**Síntoma:** Microsoft Merchant Center advierte sobre identificadores, descripciones, precios, disponibilidad, imágenes, variantes, edad, género, colores o envío.

**Causa:** Las fuentes están vacías, usan valores no admitidos o no coinciden con el mercado.

**Acción:** Haga coincidir **Language**, **Currency**, país e impuestos con el catálogo Microsoft. Proporcione GTIN, marca alternativa, texto sin HTML, disponibilidad actual, imágenes y categorías. Para ropa, revise **size**, **gender**, **color**, **age_group** e **item_group_id**. Regenere y revise los diagnósticos.

## 6. Referencia para desarrolladores

### 6.1 Descripción general del módulo

| Elemento | Valor |
|---|---|
| Nombre técnico | `mmcfeed` |
| Versión | `1.1.0` |
| Nombre mostrado | `Microsoft Merchant Center Feed` |
| Autor | `MyPresta.eu` |
| Pestaña del módulo | `administration` |
| Pestaña del back office | `AdminExportProductsFeedMicrosoft`, instalada bajo `AdminCatalog` |
| Endpoint frontal | `controllers/front/feed.php` |

`mmcfeed` amplía `Module`. El ObjectModel `mmc` guarda las definiciones como nombre, tienda, indicador activo y configuración serializada como cadena de consulta. Las descargas inmediatas y las llamadas al controlador frontal crean CSV o XML con datos de PrestaShop. El modo de archivo escribe un nombre saneado en el directorio del módulo; el directo transmite la respuesta.

### 6.2 Archivos y clases importantes

| Archivo | Responsabilidad |
|---|---|
| `mmcfeed.php` | Metadatos, instalación, desinstalación, formulario global, saneamiento, rutas seguras y validación HMAC. |
| `controllers/admin/AdminExportProductsFeedMicrosoft.php` | Dashboard, lista, formulario, duplicado, borrado, taxonomía, emparejamiento, exportación inmediata y valores recordados. |
| `controllers/front/feed.php` | Carga el feed, valida estado y tienda, aplica opciones, transmite o escribe archivo. |
| `model/mmc.php` | ObjectModel `mmc`, migración, URL, lista, registros, estadísticas y metadatos de archivos. |
| `model/categorymap.php` | Define el ObjectModel `pixelgoogle` para categorías. |
| `model/google.php` | Duplica la clase `pixelgoogle` de `model/categorymap.php`; cargar ambas causa redeclaración. |
| `lib/updateChecker.php` | `mmcfeedUpdate`, comprobaciones, preferencia y formulario Updates. |
| `lib/searchTool/searchTool.php` | Autocompletado de productos y categorías. |
| `views/templates/admin/layout.tpl` | Cabecera, navegación, avisos y recursos. |
| `views/templates/admin/feeds.tpl` | Tarjetas, URL, estados y acciones. |
| `views/templates/admin/dashboard.tpl` | KPI, gráfico, ejecuciones y archivos. |
| `views/templates/admin/form-chrome.tpl` | Cabecera del formulario y URL. |
| `views/category_taxonomy.tpl` | Estado, sincronización y emparejamiento. |
| `views/categories-fancybox.tpl` | Diálogo de categorías y rutas. |
| `views/exclude-products.tpl` | Autocompletado y lista de exclusión. |
| `views/js/admin-app.js` y `views/css/admin-app.css` | Interacciones y estilos del back office. |

### 6.3 Controladores y flujo de solicitudes

`AdminExportProductsFeedMicrosoftController` amplía `ModuleAdminController`. `mmcfeed_view` selecciona `dashboard`, `feeds`, `updates` o `form`. Gestiona:

- `saveonly` para guardar y volver a la lista.
- `submitExport` para guardar y descargar.
- `updatemmc` con `id_mmc` para editar.
- `duplicatemmc` y `deletemmc`.
- AJAX `toggleFeedActive`.
- AJAX de taxonomía, asignación, autocompletado y guardado o borrado de asociaciones.

`mmcfeedfeedModuleFrontController` amplía `ModuleFrontController`. Acepta el ID guardado, carga solo parámetros almacenados, rechaza feeds inexistentes, desactivados o de otra tienda y genera. En modo de archivo exige `mmcfeed_write_key`. Descarta parámetros entrantes de depuración y exportación para impedir que se reemplace la configuración.

Hay archivos `index.php` de marcador, pero no otro controlador frontal funcional.

### 6.4 Hooks y ciclo de vida

El único hook registrado es `actionAdminControllerSetMedia`. Para `AdminExportProductsFeedMicrosoft` activa Fancybox y autocompletado de jQuery. No produce salida frontal.

El módulo no define métodos `enable()` o `disable()` propios ni hooks proporcionados por el módulo.

`install()` llama al instalador superior, registra el hook, crea la pestaña y las tablas y completa el esquema. No vacía la caché. `uninstall()` elimina la pestaña y llama a `parent::uninstall()`; no borra tablas, configuración, feeds, archivos ni taxonomías.

### 6.5 Overrides

El módulo no instala overrides de clases ni controladores de PrestaShop.

### 6.6 Base de datos

El prefijo real es el configurado por la tienda.

| Tabla | Contenido |
|---|---|
| `pixelgoogle` | Asignaciones: clave `id_pixelgoogle`, legado `id_google`, `id_category`, `id_lang` y `value`. |
| `mmc` | Feeds: `id_mmc`, `name`, `id_shop`, `conf` serializada y `active`. Las comprobaciones añaden columnas y asignan feeds heredados a la tienda predeterminada. |
| `mmc_log` | Historial: ID, fecha, duración, elementos, estado, modo, nombre, formato y fuente. Se eliminan entradas de más de 90 días al registrar una ejecución. |

La desinstalación conserva las tres tablas, feeds, asignaciones e historial.

### 6.7 Claves de configuración y valores predeterminados

| Clave | Valor o comportamiento |
|---|---|
| `mmc_pf_tree` | Si falta se comporta como `0`; controla rutas principales. |
| `mypresta_updates` | Preferencia compartida; si falta, la comprobación periódica está desactivada. |
| `update_mmcfeed` | Marca temporal de la última comprobación. |
| `updatev_mmcfeed` | Última versión devuelta. |

Con **Remember settings**, los valores se guardan con prefijo `mmc_`:

| Claves | Valores alternativos |
|---|---|
| `mmc_export_igid`, `mmc_export_active`, `mmc_export_instock`, `mmc_export_product_type`, `mmc_export_product_type_id`, `mmc_export_product_weight`, `mmc_export_shipping_info`, `mmc_export_unit_price`, `mmc_export_save_file`, `mmc_export_nophoto_exclude`, `mmc_export_adult`, `mmc_export_color`, `mmc_export_gender`, `mmc_export_age_group`, `mmc_export_size`, `mmc_export_storecode`, `mmc_export_mainpicture`, `mmc_export_inventory`, `mmc_export_ie` | `0` o false. |
| `mmc_export_additional_sc`, `mmc_export_exworthless` | False. |
| `mmc_remember_settings`, `mmc_export_specific`, `mmc_export_enclosure`, `mmc_export_removehtml` | `1` o true. |
| `mmc_export_file_format` | `csv`. |
| `mmc_export_type` | Alternativa heredada `product`, normalizada a `products`. |
| `mmc_export_identification` | `id_product`. |
| `mmc_export_gtin` | `upc`. |
| `mmc_export_product_name` | `name`. |
| `mmc_export_product_name_format`, `mmc_export_instock_info`, `mmc_export_what_pictures` | `0`. |
| `mmc_export_short_description_what` | `short`. |
| `mmc_export_delimiter` | `|`. |
| `mmc_export_tax` | `price_tin`. |
| `mmc_export_manufacturers_default` | `Default`. |
| `mmc_export_language`, `mmc_export_currency`, `mmc_export_country_prices`, `mmc_export_group_prices` | Valores predeterminados de la tienda. |
| `mmc_export_category`, `mmc_export_manufacturers`, `mmc_export_suppliers` | Alternativa heredada `all`; selector **All**. |
| `mmc_export_shipping_info_price`, `mmc_limit_limit`, `mmc_limit_page` | `0`. |
| `mmc_export_shipping_id_zone` | `1`. |
| `mmc_export_filename`, `mmc_export_remove_char_product_name`, `mmc_export_exclude`, `mmc_export_exclude_categories`, `mmc_export_color_type`, `mmc_export_color_default`, `mmc_export_gender_default`, `mmc_export_size_default`, `mmc_export_availability_date`, `mmc_export_exreference`, `mmc_export_exreference_value`, `mmc_export_sc`, `mmc_export_exworthless_value` | Cadena vacía. |
| `mmc_export_color_attribute`, `mmc_export_color_feature`, `mmc_export_gender_type`, `mmc_export_gender_feature`, `mmc_export_gender_attribute`, `mmc_export_age_group_type`, `mmc_export_age_group_feature`, `mmc_export_age_group_attribute`, `mmc_export_age_group_default` | `0`. |
| `mmc_export_size_attribute` | ID separados por comas; vacío. |
| `mmc_mmcfeed_products` | ID excluidos separados por comas; vacío. |

El formulario también lee `delete_images` como `mmc_delete_images`, aunque no tiene campo visible. La desinstalación no borra estas claves.

### 6.8 Archivos generados, taxonomía, seguridad y extensiones

Los feeds se escriben como `modules/mmcfeed/{sanitized-name}.{csv|xml|txt}`. Los nombres se reducen a letras, dígitos, guiones y guiones bajos; las rutas seguras impiden salir del directorio. Las taxonomías se guardan en `modules/mmcfeed/google/{language-code}.txt`. No se eliminan al desinstalar.

El token es `hash_hmac('sha256', 'mmcfeed.write.' . $idShop, _COOKIE_KEY_)`. Un empleado del back office puede escribir directamente; una llamada externa debe presentar el token y se compara con `hash_equals`. El controlador descarta parámetros `export_*`, `mmcfeed_*`, `mmc_*`, `pf_*`, límites, depuración y exclusiones no fiables antes de aplicar la configuración.

CSV usa `fputcsv`, delimitador normalizado y comillas dobles. El texto decodifica entidades, normaliza espacios, elimina saltos, tabuladores y HTML. XML usa `SimpleXMLElement`. Las actualizaciones usan cURL o acceso a archivos mediante URL.

Las traducciones usan `translations/{iso}.php`. La mayoría de cadenas pasa por llamadas de traducción; algunas etiquetas, como **All**, **Price Tax Included** y **Price Tax Excluded**, están en inglés. Las descripciones están en los arrays HelperForm del controlador y las del actualizador en `lib/updateChecker.php`.

No hay plantilla frontal que el tema pueda sobrescribir. Las plantillas Smarty del back office solo se cambian modificando o ampliando el módulo. Para personalizar con seguridad, use un fork mantenido o una integración independiente; no se expone un hook formal.

## 7. Ayuda

Página del producto: [Microsoft Merchant Center Product Feed](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-feed.html)

Para obtener soporte, inicie sesión en su cuenta de mypresta.eu, abra la página de contacto y seleccione **Support for paid modules**. Debe iniciar sesión; después elija el módulo en su historial de compras y describa el feed, la tienda y el mensaje exacto.

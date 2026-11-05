---
title: "Combinations Tab Pro - documentación y manual de usuario"
description: "Configure la matriz de combinaciones, los ajustes diarios de la ficha de producto y solucione problemas habituales del escaparate si ya dispone de Combinations Tab Pro."
sidebar:
  label: "Combinations Tab Pro - documentación y manual de usuario"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product page combinations table en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-page-combinations-table/)
>
> ---


Las capturas de este manual proceden de un back office en inglés. Utilice los mismos nombres de pestañas y campos que aparecen abajo aunque el idioma del empleado sea otro.

## 1. Requisitos

Combinations Tab Pro muestra una lista de combinaciones o una matriz 2D en la ficha de producto para que los clientes puedan filtrar, ordenar, indicar cantidades y añadir variantes al carrito.

- PrestaShop: 1.7, 8 y 9
- PHP: una versión compatible con su tienda PrestaShop
- Extensiones PHP que usa el módulo: JSON
- Otros módulos: ninguno obligatorio. Opcionalmente, **Product combination features** desbloquea las columnas de descripción de combinación y características de combinación cuando ese módulo está instalado en la tienda
- Fuera de la tienda: nada. Las comprobaciones de actualización contactan con MyPresta cuando las notificaciones están activadas
- Catálogos grandes: muchas combinaciones por producto ralentizan la página si deja todas las columnas y los extras de lista y de rejilla activos; use filtros, paginación o un preset adecuado a su catálogo

## 2. Instalación

1. Suba el ZIP del módulo en **Modules** → **Module Manager**, luego instale y active **Combinations Tab Pro**.
2. Abra la configuración desde la lista de módulos con **Configure**. No hay una entrada de menú separada en el back office para el uso diario; todos los ajustes están en esa página de configuración.
3. La instalación no vacía por sí sola la caché de PrestaShop. Vacíe la caché Smarty / del tema en **Advanced Parameters** → **Performance** si la tabla no aparece tras instalar.

**Tras desinstalar:** el módulo se elimina del Module Manager. Se eliminan las tablas de base de datos de lista de deseos, alertas de reposición y perfiles de override por entidad. Los valores de configuración permanecen en la base de datos de la tienda, de modo que una reinstalación posterior puede recuperar los interruptores anteriores hasta que los cambie de nuevo. Los overrides de plantillas del módulo en el tema (si añadió alguno) no se eliminan al desinstalar.

## 3. Configuración y trabajo en el back office

Abra **Modules** → **Module Manager** → **Combinations Tab Pro** → **Configure**. La página usa pestañas superiores: **Overview**, **Display**, **Cart**, **B2B**, **Visibility**, **Exclusions**, **Integrations**, **Overrides**, **Updates**. La búsqueda de productos en **Visibility**, **Exclusions** y **Overrides** se ejecuta en segundo plano (AJAX); no hay un menú Orders separado para este módulo.

### 3.1 Proceso completo

1. El comerciante configura la ubicación, el modo de vista, columnas o celdas de rejilla, reglas de carrito, herramientas B2B opcionales, visibilidad, exclusiones, integraciones y overrides.
2. El cliente abre un producto que tiene combinaciones y que cumple las reglas de visibilidad.
3. El escaparate muestra una lista (una fila por combinación) o una rejilla 2D (matriz cuando el producto tiene dos grupos de atributos y el modo de vista lo permite), en el pie del producto o bajo una pestaña **Product variants**.
4. El cliente puede usar filtros de atributos, ordenar cabeceras de lista, indicar cantidades y añadir una o varias líneas al carrito (incluido el añadido masivo).
5. Herramientas opcionales: corazón de lista de deseos, aviso de reposición, pegado de cantidades CSV, hoja de exportación, rellenar último pedido.
6. El checkout continúa como un pedido PrestaShop normal. El módulo no usa estados de tipo presupuesto; el éxito es una tabla visible, cantidades rellenadas y un carrito con las combinaciones seleccionadas.

### 3.2 Overview & presets

![Overview and presets — English back office](https://mypresta.eu/docs/images/docs/combinationstab-overview.webp)

**Overview & presets** es la pestaña de inicio. Las configuraciones listas activan o desactivan muchos interruptores a la vez. Use **Preview** para ver los valores previstos y luego **Apply**. Confirmación: *Preset applied. Review Display & Columns and Cart & prices if you want to fine-tune.* Después abra **Display** y **Cart** para ajustar los detalles.

Presets principales por nombre:

| Preset | Tag | What it prepares |
|---|---|---|
| **Fashion** | B2C | Fotos, filtros, muestras de color, lista de deseos, tarjetas móviles para ropa con muchas tallas y colores |
| **B2B Wholesale** | B2B | Matriz orientada a SKU, añadido masivo al carrito, importación CSV, exportación, descuentos por volumen |
| **Minimal** | Simple | Solo nombre de combinación, precio y añadir al carrito |
| **Replace buy block** | UX | Oculta el bloque de compra predeterminado de PrestaShop para que los clientes pidan desde la tabla |
| **2D size × color** | Grid | Fuerza la rejilla 2D con contenido rico en celdas cuando los productos tienen Color + Size |
| **Detailed list** | List | Lista completa con imágenes, SKU, EAN, stock, ordenación, paginación |
| **Electronics** | B2C | Referencia, EAN, precio unitario, fechas de disponibilidad para electrodomésticos y gadgets |
| **Beauty & cosmetics** | B2C | Caja de color + texto, fotos, lista de deseos y reposición para tonos y kits |
| **Catalog only** | Display | Combinaciones sin pedido; los precios pueden permanecer para clientes conectados |
| **Logged-in pricing** | B2B | Precios y añadir al carrito solo para clientes conectados |
| **Mobile first** | UX | Lista con tarjetas móviles, cantidad +/- , añadido masivo fijo |
| **Restock & alerts** | Conversion | Filas agotadas con fechas y alertas de reposición |
| **Luxury / lookbook** | B2C | Fotos grandes, zoom, stock exacto oculto, resaltado de ahorro |
| **Food & packaging** | Retail | Precio unitario, peso, cantidad mínima, descuentos por volumen |
| **Quick order sheet** | B2B | Rejilla + añadido masivo + CSV/exportación/reordenar sin imágenes |

### 3.3 Display — Placement

![Display settings — English back office](https://mypresta.eu/docs/images/docs/combinationstab-display.webp)

Subpestaña **Placement**. Ubicación a nivel de página y marco alrededor de la tabla (lista y rejilla 2D). Al guardar se muestra *Display settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **Position on the product page** | Product footer (below product content) | Elige dónde ven los clientes la tabla de combinaciones. Use **Product footer** debajo del producto, o **Product tabs section** para una pestaña como **Product variants**. Elija el lugar que encaje con su tema: una elección incorrecta puede ocultar la tabla o colocarla demasiado abajo. |
| **Tab style (legacy themes)** | Classic tabs (PS 1.5 style) | Solo importa si usa la posición Product tabs en temas antiguos. Deje el valor predeterminado salvo que su tema aún use pestañas estilo PrestaShop 1.5. Cambia cómo se inyecta el título de la pestaña; los temas modernos 1.7/8/9 suelen ignorarlo. Opciones: Classic tabs (PS 1.5 style) o Accordion bars (PS 1.6 style). |
| **Custom HTML above the table** | Empty | Contenido libre (nota de envío, enlace a guía de tallas, etc.) encima de la matriz. Opcional por idioma. Visible encima de la lista y de la rejilla 2D. |
| **Hide default PrestaShop buy block** | No | Oculta los desplegables clásicos de atributos y el añadir al carrito en la ficha. Ponga **Yes** cuando la tabla deba ser la única forma de comprar. Página más limpia; asegúrese de que la tabla permite añadir al carrito. |
| **Hide default buy block only when table has combinations** | No | Mantiene el bloque de compra normal en productos simples; lo oculta cuando se muestra la matriz. **Yes** suele ser lo más seguro para que los productos simples sigan funcionando. |
| **Also hide default buy block based on product restrictions** | No | Emparejamiento avanzado con reglas de Visibility. Deje **No** salvo que use listas complejas de mostrar/ocultar productos. Puede ocultar el bloque nativo en productos seleccionados incluso sin la tabla. |

### 3.4 Display — View mode

| Field | At the start | What it does |
|---|---|---|
| **View mode** | List (classic table — one row per combination) | Elige tabla lista o matriz 2D. **List** = siempre filas; **2D grid** = forzar matriz cuando sea posible; **Auto** = matriz con 2 grupos de atributos, lista en caso contrario. Tiendas fashion/B2B con Color+Size encajan con Grid/Auto; productos con un atributo permanecen en lista. |
| **Click combination to open that variant** | Off | Al hacer clic en una fila/celda se abre la URL del producto de esa combinación. Ponga **Yes** si quiere navegar variantes desde la tabla. Útil con fotos; desactívelo si los clics solo deben cambiar la cantidad. |

### 3.5 Display — Filters

Estas reglas se aplican tanto a la tabla lista como a la rejilla 2D.

| Field | At the start | What it does |
|---|---|---|
| **Attribute filters above the table / grid** | Off | Muestra chips clicables (por ejemplo Red, XL) para filtrar filas/columnas. Ponga **Yes** en productos con muchas combinaciones. Los clientes acotan la lista y la matriz sin desplazarse sin fin. |
| **Hide out-of-stock combinations** | Off | Quita las combinaciones agotadas de la lista y de la rejilla 2D. Ponga **Yes** para vender solo variantes disponibles. Tabla/matriz más corta; los clientes no ven tallas faltantes. |
| **Hide combinations with price = 0** | Off | Oculta variantes gratis/a precio cero de la lista y la rejilla. Ponga **Yes** si cero significa «no a la venta». Las matrices pueden parecer incompletas si algunas celdas son 0 a propósito. |
| **Show only combinations that have a picture** | Off | Oculta combinaciones sin imagen en lista y rejilla. Ponga **Yes** para lookbooks; **No** si cada SKU debe ser pedible. Los catálogos incompletos se ven mejor, pero algunas variantes desaparecen. |
| **Multistore: disabled attribute values** | Hide the whole combination | Cuando un valor de atributo está desactivado para la tienda actual. Solo multitienda: ocultar combinación, mostrar como «-» o ignorar. Se aplica antes de construir lista y rejilla; tiendas de una sola sede pueden dejar el valor predeterminado. |

### 3.6 Display — Stock format

Cómo se muestran las cantidades de stock en lista y rejilla cuando el stock está visible. La visibilidad de columna/celda está en List columns o Grid cells.

| Field | At the start | What it does |
|---|---|---|
| **Show negative stock as zero** | Off | Muestra 0 en lugar de números negativos. Ponga **Yes** si el stock puede bajar de cero. Números de stock más claros en lista y rejilla. |
| **Hide exact stock above a threshold** | Off | Muestra por ejemplo «20+» en lugar del número real. Ponga **Yes** y el umbral. Oculta grandes cifras de almacén a la competencia en lista y rejilla. |
| **Stock threshold (show as X+)** | Empty | Cuando ocultar stock exacto es **Yes**, las cantidades por encima se muestran como «N+». Ejemplo: 20 hace que el stock 45 aparezca como «20+». |

### 3.7 Display — Grid axes, images, cells

Una rejilla 2D es una matriz estilo talla×color. Funciona cuando el producto tiene exactamente dos grupos de atributos y View mode es **Grid** o **Auto**. Un emparejamiento de ejes incorrecto (el mismo grupo dos veces) rompe la rejilla y vuelve a la lista.

**Grid axes**

| Field | At the start | What it does |
|---|---|---|
| **Grid rows = attribute group** | -- automatic -- | Qué atributo pasa a ser el lado izquierdo de la matriz (por ejemplo Color). Elija un grupo o deje Automatic (primer grupo de atributos por posición). Un par incorrecto rompe la rejilla y vuelve a la lista. |
| **Grid columns = attribute group** | -- automatic -- | Qué atributo pasa a ser la parte superior de la matriz (por ejemplo Size). Elija un grupo distinto al de filas, o Automatic. Cada celda es una combinación donde el cliente escribe la cantidad. |

**Grid images** (solo rejilla 2D)

| Field | At the start | What it does |
|---|---|---|
| **Show image in cells** | Off | Miniatura dentro de cada celda de la matriz. Ponga **Yes** para matrices fashion color×talla. Celdas más densas; usa la imagen de la combinación o la portada de respaldo de abajo. |
| **Use product cover when combination has no image** | Yes | Muestra la foto principal del producto como respaldo en las celdas. Ponga **Yes** para no mostrar nunca una imagen en blanco en la matriz. Solo afecta a la rejilla 2D, no a la lista. |
| **Grid thumbnail image type** | Empty (shop image types) | Tamaño de imagen PrestaShop usado en las celdas. Elija un tipo pequeño (por ejemplo cart / small_default). Solo rejilla 2D; la lista usa List images → Thumbnail type. |

**Grid cells** — arrastre **Cell block order** (arriba→abajo) y luego Save. Solo aparecen los bloques activados. Wishlist/BIS siguen necesitando **Integrations**; añadir al carrito necesita el interruptor maestro en **Cart**.

| Field | At the start | What it does |
|---|---|---|
| **Cell block order** | Default block order | Orden de los bloques dentro de cada celda de la matriz. Arrastre y luego Save. Solo aparecen los bloques activados abajo. Imagen on/off y tamaño en Grid images. |
| **Grid: show reference (SKU)** | Off | SKU bajo el contenido de la celda. Ponga **Yes** en B2B para que los compradores identifiquen SKU sin abrir el producto. |
| **Grid: show price** | Off | Precio en la celda (las reglas de impuestos/descuentos siguen Cart). Ponga **Yes** en casi todas las tiendas para comparar variantes por precio en la matriz. |
| **Grid: show unit price** | Off | Precio unitario en la celda. Ponga **Yes** si usa precios unitarios. Línea compacta bajo el precio principal. |
| **Grid: show stock quantity** | Off | Número de stock disponible en la celda. Ponga **Yes** para transparencia; revela inventario por talla/color. |
| **Grid: show availability** | Off | Etiqueta In stock / Out of stock en la celda. Ponga **Yes** cuando se ocultan los números de stock. Estado claro sin la cantidad exacta. |
| **Grid: show minimal quantity** | Off | Cantidad mínima de pedido en la celda. Ponga **Yes** para packs B2B; reduce cantidades incorrectas en el carrito. |
| **Grid: show savings badge** | Off | % ahorrado frente a la combinación más cara. Ponga **Yes** para conversión; destaca tallas/colores más baratos. |
| **Grid: quantity input** | Off | Campo de cantidad en cada celda (funciona con Bulk Add to cart). Ponga **Yes** para pedidos en matriz y que los clientes rellenen cantidades por talla. |
| **Grid: Add to cart button (when bulk ATC is off)** | Off | Botón de añadir por celda cuando Bulk add to cart está desactivado. Ponga **Yes** para añadidos de un clic sin bulk. Se ignora mientras bulk ATC esté activo. |
| **Grid: wishlist heart** | Off | Botón corazón en la celda. Active primero Wishlist en Integrations. Los clientes guardan talla/color desde la matriz. |
| **Grid: back-in-stock alert** | Off | Botón de aviso en celdas agotadas. Active primero Back in stock en Integrations. Captura demanda de tallas faltantes. |

### 3.8 Display — List layout, images, columns

Estos ajustes afectan solo a la lista clásica (una fila por combinación), no a las celdas de la rejilla 2D.

**List layout & sorting**

| Field | At the start | What it does |
|---|---|---|
| **Column order (list only)** | Default column order | Define el orden de izquierda a derecha de las columnas en la vista lista. Arrastre elementos y luego Save. Los clientes ven las columnas en este orden (solo aparecen las activadas). |
| **Mobile card layout (list)** | Yes | En móviles, convierte filas anchas de tabla en tarjetas apiladas. Ponga **Yes** para mejor UX móvil. Cada combinación parece una tarjeta pequeña; el escritorio sigue siendo tabla normal. |
| **Hide table header (list)** | Off | Quita la fila superior con nombres de columna. Suele dejarse **No**. Aspecto más limpio pero más difícil de entender las columnas. |
| **Paginate long tables (list)** | Off | Divide muchas combinaciones en páginas. Ponga **Yes** si un producto tiene docenas de variantes. Sensación de página más rápida; configure Rows per page abajo. |
| **Rows per page** | 10 when pagination is used without a custom value | Cuántas combinaciones por página con paginación activa. Ejemplo: 10 o 20. Número menor = páginas más cortas, más clics. |
| **Allow sorting by column headers** | Yes | Cabeceras clicables para ordenar la lista. Ponga **Yes** en listas largas. Los clientes ordenan por precio, referencia, etc. (solo vista lista). |
| **Default sort by price** | Off | La ordenación inicial usa el precio. Opcional. Más barato/caro primero según la dirección. |
| **Default sort by attribute** | Off | Ordenación inicial por un grupo de atributos elegido. Configure el ID de atributo y la dirección abajo. Ejemplo: tallas S→XL. |
| **Attribute sort uses** | Attribute value position | Ordenar por posición de atributo (orden del catálogo) o por nombre A→Z. La posición suele ser mejor para tallas. Cambia el orden de filas por defecto cuando la ordenación por atributo está activa. |
| **Attribute group ID to sort by** | Empty | ID numérico del grupo de atributos usado para la ordenación por defecto. En Catalog → Attributes, abra el grupo y lea el ID en la URL. ID incorrecto = orden inesperado. |
| **Sort direction** | Ascending | Orden por defecto ascendente o descendente. Ascending para S→XL; Descending para precio alto→bajo al ordenar por precio. Controla las primeras filas que ven los clientes. |

**List images**

| Field | At the start | What it does |
|---|---|---|
| **Show image column** | Yes | Añade una miniatura por cada combinación. Ponga **Yes** cuando las variantes tengan fotos distintas para reconocerlas antes. |
| **Show image column only if at least one combination has a photo** | Off | Oculta la columna de imagen vacía cuando ninguna combinación tiene foto. Ponga **Yes** para evitar una columna vacía inútil. La tabla permanece limpia en productos sin imágenes de combinación. |
| **Use product cover when combination has no image** | Off | Muestra la foto principal del producto como respaldo en la lista. Ponga **Yes** para no mostrar nunca una celda de imagen en blanco. Solo afecta a la vista lista, no a la rejilla 2D. |
| **Click image to zoom** | Off | Abre una imagen más grande en lightbox. Ponga **Yes** para productos visuales; configure el tamaño de zoom abajo. Los clientes inspeccionan detalles sin salir de la página. |
| **Thumbnail image type** | Empty (shop image types) | Tamaño de imagen PrestaShop en la columna de lista. Elija un tipo pequeño (por ejemplo cart / small_default). Solo lista; la rejilla usa Grid images → Thumbnail type. |
| **Zoom image type** | Empty (shop image types) | Tamaño de imagen abierto en el lightbox cuando el zoom está activo. Elija un tipo grande (por ejemplo large_default). Vista previa de zoom más nítida en lista. |

**List columns** — visibilidad para la lista clásica. La descripción / características de combinación necesitan el módulo opcional Combination features; en caso contrario esos controles permanecen bloqueados con un enlace a la tienda.

| Field | At the start | What it does |
|---|---|---|
| **How attributes are shown** | All attributes in one column | Una columna combinada «Combination name» frente a columnas separadas por atributo (Color, Size…). Las columnas separadas se escanean y ordenan mejor. El diseño de la vista lista cambia de inmediato. |
| **Include attribute label in the name** | Off | Muestra «Color: Red, Size: L» en lugar de «Red, L». Ponga **Yes** para claridad; solo aplica al método de una sola columna. Nombres más largos pero más claros. |
| **Color attribute display** | Text only | Cómo se ven los valores de color (muestra, texto o ambos). Caja de color para moda; Text si los colores tienen nombres especiales. Solo afecta a atributos de tipo «color». |
| **Show combination / attribute columns** | Yes | Interruptor maestro de las columnas de nombre de atributo. Casi siempre **Yes**. **No** oculta cómo difieren las variantes: solo para diseños muy especiales. |
| **Show combination description** | Off (locked without Combination features) | Muestra la descripción personalizada asignada a la combinación por Combination features. Ponga **Yes** cuando las variantes tengan texto propio. Columna de lista extra; las celdas vacías muestran «-». |
| **Show combination features** | Off (locked without Combination features) | Muestra los valores de característica asignados a la combinación por Combination features. Ponga **Yes** cuando las variantes tengan su propia ficha. Columna de lista extra con nombre de característica + valores. |
| **Show reference (SKU)** | Yes | Muestra la referencia de la combinación. Ponga **Yes** en B2B / mayorista para pedir más rápido por SKU. |
| **Show EAN** | No | Muestra el código de barras EAN-13. Ponga **Yes** si el personal/clientes escanean códigos. Columna extra; desactívela en moda B2C si no se usa. |
| **Show MPN** | No | Columna de número de pieza del fabricante. Ponga **Yes** cuando rellene MPN en el catálogo. Las celdas vacías muestran «-» si el MPN está en blanco. |
| **Show weight** | Off | Peso del producto + impacto de la combinación. Ponga **Yes** en bienes sensibles al envío para estimar portes. |
| **Show stock quantity** | Yes | Stock disponible por combinación. Ponga **Yes** para transparencia; combínelo con Stock format para «10+». Genera confianza; revela inventario. |
| **Show total product stock in header** | No | Añade la suma de stock junto a la cabecera Quantity. Resumen opcional rápido de la disponibilidad total. |
| **Show availability text** | Yes | «In stock» / «Out of stock» (o las etiquetas de su tienda). Ponga **Yes** para claridad y que el cliente vea el estado sin leer el número. |
| **Show availability date when out of stock** | Yes | Imprime la fecha de disponibilidad de la combinación bajo el estado agotado. Ponga **Yes** si rellena fechas de disponibilidad. Fija expectativas de reposición. |
| **Show minimal quantity** | Off | Muestra la cantidad mínima de pedido de la combinación. Ponga **Yes** para packs B2B; reduce errores al añadir al carrito. |
| **Show price** | Yes | Columna de precio por combinación (solo lista). Ponga **Yes** en casi todas las tiendas. Los clientes comparan variantes por precio. La rejilla usa Grid cells → show price. |
| **Show unit price** | Off | Columna de precio unitario (solo lista). Ponga **Yes** si usa precios unitarios. Valores vacíos/raros si la unidad no está definida en el producto. |
| **Show savings column** | No | Cuánto más barata es una combinación frente a la más cara (solo lista). Ponga **Yes** para psicología de upsell. Columna extra con % e importe ahorrado. La rejilla usa Grid cells → savings badge. |
| **Show volume (quantity) discounts column** | Off | Lista tramos de descuento por cantidad por combinación (solo lista). Ponga **Yes** para mayorista. Tabla más ancha; ideal para B2B. |
| **Hide volume discount rows that do not apply** | Off | Limpia listas de descuento vacías en la columna de lista. Ponga **Yes** para reducir ruido y dejar solo tramos significativos. |

### 3.9 Cart — Prices

![Cart settings — English back office](https://mypresta.eu/docs/images/docs/combinationstab-cart.webp)

Subpestaña **Prices**. Reglas globales de visualización de precios para lista y rejilla 2D. Al guardar se muestra *Cart & price settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **Show prices only to logged-in customers** | No | Los invitados ven un aviso de inicio de sesión en lugar de precios. Ponga **Yes** para precios B2B ocultos. Los invitados deben iniciar sesión para ver importes en lista y rejilla. |
| **Tax display** | Tax included | Impuestos incluidos, excluidos o seguir el ajuste del grupo de clientes. Ajuste a la política de precios de su tienda. Una elección incorrecta confunde a compradores B2B frente a B2C. |
| **Show “tax incl./excl.” label next to price** | Off | Texto pequeño tras el precio. Ponga **Yes** para claridad legal en la UE. Celdas un poco más cargadas. |
| **Show discount % badge on reduced prices** | Off | Muestra -X% cuando existe una reducción de precio específica. Ponga **Yes** para destacar ofertas. Llama la atención sobre combinaciones rebajadas en lista y rejilla. |
| **Highlight the cheapest combination** | Yes | Marca la fila/celda de precio más bajo. Ponga **Yes** para guiar compras impulsivas. Resaltado verde del mejor precio en lista y rejilla. |

### 3.10 Cart — Add to cart

| Field | At the start | What it does |
|---|---|---|
| **Show add to cart controls** | Yes | Campo de cantidad y/o botón por combinación. Ponga **Yes** para vender desde la tabla. **No** = matriz solo de visualización. |
| **Add to cart only for logged-in customers** | Off | Los invitados no pueden añadir desde la tabla. Ponga **Yes** para B2B. Los invitados ven un mensaje en lugar de botones. |
| **Show quantity input** | Yes | Casilla de cantidad editable. **Yes** siempre recomendado. **No** oculta la cantidad (más difícil comprar varias unidades). |
| **Qty box also in the table header (fill all rows)** | Off | Una cantidad en cabecera se copia a todas las filas. Comodidad opcional. Acelera el relleno masivo; úselo con cuidado. |
| **Plus / minus buttons** | No | Pulsadores +/- junto a la cantidad. Ponga **Yes** para dispositivos táctiles. Cambios de cantidad más fáciles. |
| **Block qty higher than stock** | Off | Impide pedir más de lo disponible (cuando no se permiten pedidos sin stock). Ponga **Yes** para evitar sobreventa. El botón + se detiene en el stock. |
| **AJAX add to cart** | Yes | Añade sin recargar toda la página. Ponga **Yes** en temas modernos. UX más fluida; desactívelo solo si hay conflicto con el tema. |
| **Bulk add to cart (one button for many rows)** | Off | El cliente rellena varios campos de cantidad y un **Add to cart** envía todos. Ponga **Yes** para B2B/moda. Los botones por fila pueden ocultarse; aparece una barra fija en móvil. |
| **Show live total price of selected quantities** | Off | Calcula la suma de las líneas seleccionadas (respeta descuentos por cantidad cuando es posible). Ponga **Yes** con añadido masivo. Los clientes ven el valor del carrito antes de pulsar Add. |
| **Tip: how many units until next quantity discount** | Yes | Bajo la barra masiva, indica al cliente «add X more to unlock the next discount». Ponga **Yes** si usa descuentos por cantidad. Fomenta carritos mayores. |
| **Use Font Awesome cart icon** | Off | Icono FA en lugar del icono Material. Ponga **Yes** solo si su tema carga Font Awesome. Sin FA = icono roto. |

### 3.11 B2B Tools and Groups

![B2B tools — English back office](https://mypresta.eu/docs/images/docs/combinationstab-b2b.webp)

**Tools** — ayudas mayoristas. Los interruptores globales son valores por defecto; use **Groups** para permitir o denegar por grupo de clientes PrestaShop. Al guardar se muestra *B2B settings saved.*

| Field | At the start | What it does |
|---|---|---|
| **CSV quantity import on product page** | No | Los compradores pegan líneas como SKU;5 (o EAN;qty) para rellenar cantidades. Ponga **Yes** para mayorista; luego permítalo por grupo si hace falta. Gran ahorro de tiempo en recompras. |
| **Export order sheet (CSV / XLSX / PDF)** | No | Descarga las combinaciones con las cantidades tecleadas. Ponga **Yes** para compradores que envían hojas a contabilidad. Los botones aparecen junto al añadido masivo. |
| **Fill last order button** | No | Restaura cantidades del último añadido masivo / exportación de este producto. Ponga **Yes** para pedidos mayoristas repetidos. Un clic rellena la matriz. |

**Groups** — para cada grupo de clientes configure **Show table**, **Add to cart**, **CSV import**, **Export**, **Reorder** (Yes/No). Valores por defecto sin regla propia: show table Yes, add to cart Yes, CSV/export/reorder siguen los interruptores globales de Tools (off tras la instalación). Si **Show table** es No para el grupo del visitante, la matriz no aparece. Si **Add to cart** es No, el visitante no puede añadir desde la tabla aunque los interruptores globales de Cart estén activos.

### 3.12 Visibility

![Visibility — English back office](https://mypresta.eu/docs/images/docs/combinationstab-visibility.webp)

Controle en qué productos los clientes ven la tabla de combinaciones. Busque productos con el selector en pantalla (búsqueda AJAX). Confirmación: *Successfully updated*.

| Field | At the start | What it does |
|---|---|---|
| **Visibility rule** | Show on all products | Decide si la tabla aparece en todos los productos, solo en seleccionados o en todas partes excepto los seleccionados. Elija una regla y luego marque categorías / añada productos en el selector de abajo. «All products» es lo más simple; use Include/Exclude cuando solo parte del catálogo necesite la matriz. |
| **Selected categories & products** | None | La lista de categorías y productos usada por la regla anterior. Marque categorías y/o busque productos y pulse Add. Solo se usa cuando la regla es Include o Exclude; se ignora con «all products». |
| **Hide table when product has too few attribute groups** | Off | Oculta la tabla en productos con pocos grupos de atributos (por ejemplo solo Color, sin Size). Ponga **Yes** y el número abajo. Ejemplo: umbral 1 oculta productos con 1 o menos grupos de atributos: útil si solo quiere la matriz para productos Color+Size. |
| **Hide when attribute groups ≤** | Empty | Umbral del interruptor anterior. Introduzca 1 para ocultar productos de un solo atributo; 0 prácticamente nunca oculta por esta regla. Se compara con el número de grupos de atributos del producto. |

### 3.13 Exclusions

Oculte de forma permanente combinaciones elegidas de la tabla (todos los productos). Busque un producto, elija combinaciones con **Select** y luego **Save**. Confirmación: *Settings saved*. Esas variantes siguen en PrestaShop pero nunca aparecen en la matriz: útil para tallas obsoletas o SKU internos. La búsqueda de producto y combinación usa la misma búsqueda AJAX de productos que Visibility.

| Field | At the start | What it does |
|---|---|---|
| **Search for product** | Empty | Encuentre el producto cuyas combinaciones desea excluir. |
| **Combination** | None selected | Marque las combinaciones a ocultar de la matriz del escaparate y luego Save. |

### 3.14 Integrations

![Integrations — English back office](https://mypresta.eu/docs/images/docs/combinationstab-integrations.webp)

Al guardar se muestra *Integrations saved.* El formulario indica Advanced Stock Management cuando se detecta; sin ASM, deje el interruptor de almacén en Off.

| Field | At the start | What it does |
|---|---|---|
| **Combination wishlist** | No | El botón corazón guarda una variante en una lista de deseos ligera (cuenta o cookie). Ponga **Yes** si los clientes marcan tallas. El enlace aparece en My Account; no es una suite completa de lista de deseos. |
| **Back-in-stock email alerts** | No | Las filas agotadas obtienen un botón de aviso; cuando vuelve el stock, el módulo envía un correo al cliente. Ponga **Yes** y asegúrese de que su tienda puede enviar correos. Recupera demanda de tallas faltantes. |
| **Warehouse stock column** | No | Lista cantidades por almacén cuando Advanced Stock está activo. Ponga **Yes** solo con ASM. Sin ASM la columna queda vacía: déjela Off. |

### 3.15 Overrides

![Overrides — English back office](https://mypresta.eu/docs/images/docs/combinationstab-overrides.webp)

Los perfiles se cascaden **Product → deepest Category → Manufacturer → Global**. Solo los campos sobrescritos cambian la capa inferior. Filtre la lista con **All / Products / Categories / Manufacturers**. Cree con **Product override**, **Category override** o **Manufacturer override**.

En la pantalla de edición: busque y seleccione una entidad, active solo los campos que desea sobrescribir, deje sin marcar los que deben heredar. Use **Copy all from global** para sembrar valores y luego **Save override**. Éxito: *Override profile saved.* Al eliminar se pregunta *Delete this override profile?* Éxito: *Override profile deleted.*

Motivos típicos para usar overrides: una marca siempre necesita modo rejilla; una categoría oculta precios a invitados; un producto necesita columnas SKU extra sin cambiar toda la tienda.

### 3.16 Updates

**Check now** pregunta a MyPresta si existe una versión más reciente. Mensajes: *New version available!* o *Module is up to date!*

| Field | At the start | What it does |
|---|---|---|
| **Check updates** | — | Ejecuta una comprobación inmediata y muestra si existe una versión nueva. |
| **Updates notifications** | Select / as previously saved | Active esta opción si desea comprobar automáticamente en MyPresta.eu las actualizaciones del módulo. Esta opción mostrará notificaciones sobre nuevas versiones de este addon. |
| **Module page** | Link on screen | Enlace directo a la página oficial del addon donde puede leer los cambios del módulo (changelog). Use Support (capítulo 7) para solicitudes de ayuda. |

## 4. Front office

- **Placement:** pie del producto bajo el contenido, o una pestaña **Product variants** en el área de pestañas del producto, según Display → Placement.
- **List vs 2D grid:** la lista es una fila por combinación. La rejilla es una matriz cuando el producto tiene exactamente dos grupos de atributos y View mode es Grid o Auto; en caso contrario el escaparate vuelve a la lista.
- **Filters:** chips de atributos encima de la tabla/rejilla cuando están activados.
- **Sorting / pagination / mobile cards:** solo lista, cuando esas opciones de Display están activas.
- **Add to cart:** controles por fila y/o **Add to cart** masivo con total en vivo opcional y tip «units until next discount».
- **Toolbar:** cuando está activada — **Fill last order**, **Export** (CSV / XLSX / PDF), área de texto **Import quantities** con líneas como `REF001;5`, luego **Apply**.
- **Wishlist:** corazón en filas/celdas cuando Integrations + interruptores de columna/celda lo permiten. Los clientes conectados obtienen **My combination wishlist** en la página de cuenta.
- **Back in stock:** control de aviso en líneas agotadas; correo cuando vuelve el stock (el correo de la tienda debe funcionar).
- **Guest prices:** con «prices only for logged-in», los invitados ven un aviso de inicio de sesión en lugar de importes; con «ATC only for logged-in», los invitados no pueden añadir desde la tabla.

No se requiere aquí una captura separada del escaparate; el diseño del tema decide el marco exacto alrededor del bloque del módulo.

## 5. Problemas habituales

### 5.1 La tabla no es visible en la ficha de producto

Compruebe que el módulo está activado, que el producto tiene combinaciones, que la regla **Visibility** incluye el producto, que el grupo de clientes tiene **Show table** en Yes y que la posición encaja con su tema (pie frente a pestañas). Vacíe la caché. Confirme que Exclusions no ha ocultado todas las combinaciones.

### 5.2 Posición incorrecta o pestaña vacía

Cambie **Position on the product page**. En temas modernos, ignore Tab style. Si usa pestañas, abra el producto y busque **Product variants**.

### 5.3 Esperaba rejilla 2D pero ve una lista

La rejilla necesita exactamente dos grupos de atributos y View mode Grid o Auto. Un atributo, o tres o más, fuerza la lista. El mismo grupo de atributos en ambos ejes también vuelve a la lista: configure grupos distintos de filas y columnas.

### 5.4 El bloque de compra predeterminado falta o sigue visible

Revise **Hide default PrestaShop buy block** y **Hide default buy block only when table has combinations**. Si el bloque nativo está oculto pero la tabla no tiene añadir al carrito, los clientes no pueden comprar: active Cart → **Show add to cart controls**.

### 5.5 El añadido masivo no hace nada o recarga mal

Active **AJAX add to cart** en temas modernos. Confirme que **Bulk add to cart** es Yes y que las cantidades están rellenadas. La regla de grupo **Add to cart** debe ser Yes para ese grupo de clientes.

### 5.6 Las reglas de grupo bloquean el añadir al carrito u ocultan la tabla

En **B2B** → **Groups**, ponga **Show table** y **Add to cart** en Yes para el grupo del visitante (Guest, Customer o su grupo mayorista).

### 5.7 Precios ocultos para invitados

Esperado cuando **Show prices only to logged-in customers** es Yes. Póngalo en Off para precios públicos, o pida a los invitados que inicien sesión.

### 5.8 Falta la lista de deseos o la reposición

Actívelas en **Integrations** y luego active los interruptores de columna de lista o celda de rejilla correspondientes. Para BIS, confirme que PrestaShop puede enviar correo y que el stock se actualiza al reponer.

### 5.9 Columnas de descripción / características de combinación bloqueadas

Instale y active el módulo opcional **Product combination features**. Hasta entonces esas columnas permanecen bloqueadas en Display y Overrides.

### 5.10 Faltan CSV / exportación / rellenar último pedido

Active las herramientas en **B2B** → **Tools** y ponga Yes para ese grupo de clientes en **Groups**.

## 6. Guía para desarrolladores

### 6.1 Resumen

- Nombre técnico: `combinationstab`
- Versión: 3.0.5
- Nombre mostrado: Combinations Tab Pro
- Autor: mypresta.eu
- Pestaña del módulo: `smart_shopping`
- Clase principal: `Combinationstab`
- UI BO: `CtpAdminBo` (`lib/CtpAdminBo.php`)
- Resolución de ajustes: `CtpSettingsResolver` (Product → Category → Manufacturer → Global)
- Opcional: `CtpCombfeat` — el archivo puede estar ausente; `class_exists('CtpCombfeat')` controla descripción/características de combinación. Sin la clase, esas opciones permanecen bloqueadas.

Flujo: Configuration / ajustes de entidad → los hooks FO renderizan plantillas de lista o rejilla → los controladores front gestionan ayudas AJAX de carrito, lista de deseos, BIS, CSV, exportación, reordenar, calculadora de precios.

### 6.2 Archivos importantes

| Path | Role |
|---|---|
| `combinationstab.php` | Clase del módulo, install/uninstall, hooks, formularios de visibility/exclusions |
| `lib/CtpAdminBo.php` | Pestañas de la página Configure y campos HelperForm |
| `lib/CtpColumnRegistry.php` | Columnas de lista, presets, JSON de orden |
| `lib/CtpGridRegistry.php` | Bloques de celdas de rejilla y JSON de orden |
| `lib/CtpGrid2d.php` | Construcción de matriz 2D / `shouldUseGrid` |
| `lib/CtpCombinationsData.php` | Filas de combinación para FO |
| `lib/CtpGroupRules.php` | Por grupo show/atc/csv/export/reorder |
| `lib/CtpWishlist.php` / `CtpBackInStock.php` / `CtpExport.php` / `CtpReorder.php` | Ayudantes de funciones |
| `lib/CtpSettingsResolver.php` | Tabla de override y cascada |
| `views/templates/admin/tabs.tpl` | Marco de pestañas BO |
| `views/templates/hook/productfooter.tpl` / `productfooter_grid.tpl` | Lista / rejilla FO |
| `views/templates/hook/_toolbar.tpl` | Barra bulk / export / CSV |
| `controllers/front/*.php` | Endpoints front |
| `controllers/admin/AdminCombinationstabSearchController.php` | Búsqueda AJAX de productos para selectores BO |

### 6.3 Controladores

**Admin:** `AdminCombinationstabSearchController` — búsqueda AJAX de producto/combinación usada por Visibility, Exclusions, Overrides. No es una página de menú para comerciantes.

**Front:**

| Controller | Purpose |
|---|---|
| `Wishlist` | Alternar / listar lista de deseos (JSON + página de cuenta) |
| `BackInStock` | Suscribirse a alertas OOS (JSON) |
| `CsvImport` | Aplicar cantidades SKU/EAN pegadas (JSON) |
| `Export` | Descargar hoja CSV/XLSX/PDF |
| `Reorder` | Guardar / restaurar últimas cantidades (JSON) |
| `PriceCalculator` | Total seleccionado en vivo / tip de volumen (cuerpo JSON, sin curl) |

### 6.4 Hooks (registrados en la instalación)

`displayHeader`, `displayProductFooter`, `displayFooterProduct`, `displayProductTab`, `displayProductExtraContent`, `displayProductTabContent`, `CombinationsTable`, `ActionAdminControllerSetMedia`, `displayCustomerAccount`, `actionUpdateQuantity`.

Sin `enable()` / `disable()` personalizados más allá de los valores predeterminados de PrestaShop. Uninstall elimina las tablas de funciones y luego `parent::uninstall()`.

### 6.5 Overrides

El módulo no incluye overrides de clase/controlador bajo `override/`. Los overrides de plantillas `.tpl` del módulo en el tema son opcionales y del lado del comerciante.

### 6.6 Base de datos

Uninstall elimina estas tablas; las claves de Configuration se conservan.

| Table | Content |
|---|---|
| `ctp_wishlist` | `id_ctp_wishlist`, customer/guest, product, combination, shop, `date_add` |
| `ctp_backinstock` | Suscripciones por correo, product/combination, shop, lang, `notified`, dates |
| `ctp_entity_settings` | `entity_type`, `id_entity`, JSON `settings`, `date_upd` |

### 6.7 Claves de configuración y valores por defecto (instalación)

Valores por defecto seleccionados escritos en la instalación: `ctp_position` = `productFooter`, `ctp_where` = `1`, `ctp_view_mode` = `list`, `ctp_image`/`ctp_price`/`ctp_reference`/`ctp_cname`/`ctp_atc`/`ctp_atcq`/`ctp_ajax`/`ctp_sort`/`ctp_quantity`/`ctp_availability`/`ctp_availability_d` = `1`, `ctp_ean`/`ctp_mpn` = `0`, `ctp_wishlist`/`ctp_bis`/`ctp_export`/`ctp_csv_import`/`ctp_reorder` = `0`, `ctp_group_rules` = `{}`, `ctp_column_order` = JSON de `CtpColumnRegistry::defaultKeys()`, más claves relacionadas de impuestos/ocultar/rejilla como en `install()`. El orden de columnas/celdas también usa JSON (`ctp_column_order`, `ctp_grid_cell_order`). Traducciones: `translations/{iso}.php`. Los textos `desc` de campos viven principalmente en `CtpAdminBo`.

### 6.8 Extensión

Anule las plantillas FO desde el tema bajo `modules/combinationstab/...` sin editar el paquete del módulo. El tema debe seguir llamando a los hooks de producto registrados para la salida. La integración opcional Combination features requiere `lib/CtpCombfeat.php` presente y `CtpCombfeat::isAvailable()` true.

## 7. Soporte

Página del producto: https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html

Para obtener ayuda: inicie sesión en su cuenta de cliente en mypresta.eu, abra Contact y elija **Support for paid modules**. El formulario requiere inicio de sesión para módulos de pago; tras iniciar sesión, elija este módulo en su historial de compras.

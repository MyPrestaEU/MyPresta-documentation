---
title: "Exportar catálogo para anuncios dinámicos de Facebook Pixel - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Exportar catálogo para anuncios dinámicos de Facebook Pixel' de MyPresta.eu."
sidebar:
  label: "Exportar catálogo para anuncios dinámicos de Facebook Pixel - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Export catalog for facebook pixel dynamic ads en MyPresta.eu](https://mypresta.eu/modules/social-networks/export-catalog-for-facebook-pixel-dynamic-ads.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/export-catalog-for-facebook-pixel-dynamic-ads/)
>
> ---


# Exportar catálogo para anuncios dinámicos de Facebook Pixel

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Asegúrese de que su servidor tenga suficiente memoria y tiempo de ejecución para generar grandes feeds de productos si tiene muchos productos.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

La configuración del módulo se gestiona principalmente a través de una pantalla de administración dedicada, que le permite definir cómo se exporta su catálogo de productos.

### 2.1 Pantalla de configuración principal del módulo (Back Office > Módulos > Gestor de módulos > Configurar)

Esta pantalla proporciona los ajustes principales para el módulo, permitiéndole generar y gestionar sus feeds de productos.

**Ubicación del menú:** Back Office > Módulos > Gestor de módulos > Busque "Exportar catálogo para anuncios dinámicos de Facebook Pixel" > Haga clic en "Configurar".

#### Configuración general y generación de feed

Esta sección es donde define los parámetros principales para su feed de productos.

- **Seleccionar idioma para la exportación:**

  - **Qué hace este ajuste:** Determina qué nombres de productos, descripciones y otros campos de texto del idioma se incluirán en el feed exportado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en inglés:* Su feed contendrá detalles del producto en inglés.
    - *Cuando se establece en francés:* Su feed contendrá detalles del producto en francés.
  - **Valor recomendado:** El idioma principal de su público objetivo para los anuncios de Facebook. Si ejecuta anuncios en varios idiomas, deberá generar feeds separados para cada idioma.
  - **Escenario/ejemplo de comerciante:** Si se dirige principalmente a clientes en EE. UU., seleccionaría "Inglés". Si también se dirige a clientes en Francia, generaría un feed separado con "Francés" seleccionado.
- **Seleccionar moneda para la exportación:**

  - **Qué hace este ajuste:** Determina qué precios de moneda se incluirán en el feed exportado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en USD:* Todos los precios de los productos en el feed estarán en dólares estadounidenses.
    - *Cuando se establece en EUR:* Todos los precios de los productos en el feed estarán en euros.
  - **Valor recomendado:** La moneda principal de su público objetivo para los anuncios de Facebook. Al igual que el idioma, si se dirige a varias monedas, necesitará feeds separados.
  - **Escenario/ejemplo de comerciante:** Si su tienda vende tanto en USD como en CAD, y desea ejecutar anuncios de Facebook para sus clientes canadienses, seleccionaría "Dólar canadiense" para ese feed específico.
- **Exportar solo productos activos:**

  - **Qué hace este ajuste:** Controla si solo los productos actualmente habilitados y visibles en su tienda se incluyen en el feed.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Solo se exportarán los productos que estén activos en su tienda PrestaShop. Esto evita mostrar anuncios de artículos agotados o descontinuados.
    - *Cuando está deshabilitado (NO):* Todos los productos, incluidos los inactivos, podrían exportarse. Esto generalmente no se recomienda para campañas publicitarias en vivo.
  - **Valor recomendado:** **SÍ**. Esto asegura que sus anuncios sean siempre relevantes y se vinculen a productos disponibles.
  - **Escenario/ejemplo de comerciante:** Tiene productos de temporada que actualmente están inactivos. Habilitar esto asegura que no aparezcan en sus anuncios de Facebook hasta que los reactive.
- **Exportar solo productos en stock:**

  - **Qué hace este ajuste:** Determina si solo los productos con stock disponible se incluyen en el feed.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Solo se exportarán los productos que estén actualmente en stock.
    - *Cuando está deshabilitado (NO):* Los productos que están agotados podrían exportarse, lo que podría llevar a una mala experiencia del cliente si hacen clic en un anuncio de un artículo no disponible.
  - **Valor recomendado:** **SÍ**. Esto evita que los clientes hagan clic en anuncios de productos que no pueden comprar, lo que reduce la frustración y el gasto publicitario desperdiciado.
  - **Escenario/ejemplo de comerciante:** Un artículo popular acaba de agotarse. Con esto habilitado, se eliminará automáticamente de su feed de Facebook hasta que se reponga.
- **Exportar combinaciones de productos (variaciones):**

  - **Qué hace este ajuste:** Controla si las combinaciones de productos individuales (por ejemplo, una camiseta en diferentes tallas y colores) se exportan como elementos separados en el feed.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Cada combinación (por ejemplo, "Camiseta Roja - Pequeña", "Camiseta Roja - Mediana") aparecerá como un elemento único en el feed, con su propia imagen, precio y enlace. Esto es crucial para que los anuncios dinámicos muestren la variante exacta que vio un cliente.
    - *Cuando está deshabilitado (NO):* Solo se exportará el producto principal, sin combinaciones individuales. Esto limita la granularidad de sus anuncios dinámicos.
  - **Valor recomendado:** **SÍ**. Esto es muy recomendable para la mayoría de las tiendas, especialmente aquellas que venden ropa, productos electrónicos o cualquier producto con variaciones, para garantizar la experiencia publicitaria más precisa y personalizada.
  - **Escenario/ejemplo de comerciante:** Un cliente ve un "Vestido Azul - Grande" en su sitio. Si se exportan las combinaciones, Facebook puede mostrarle un anuncio específicamente para ese "Vestido Azul - Grande".
- **Identificación del producto (campo ID):**

  - **Qué hace este ajuste:** Especifica qué campo de ID de PrestaShop debe usarse como identificador único para los productos en el feed de Facebook (campo `id`).
  - **Efecto de cambiar este ajuste:**
    - *ID de producto:* Utiliza el `id_product` estándar de PrestaShop.
    - *EAN13:* Utiliza el código de barras EAN13.
    - *UPC:* Utiliza el código de barras UPC.
    - *Referencia:* Utiliza el código de referencia interno del producto.
  - **Valor recomendado:** **ID de producto** es generalmente la opción más segura y confiable, ya que siempre es única e interna de PrestaShop. Si utiliza consistentemente EAN13/UPC para todos los productos y combinaciones, esos también pueden funcionar.
  - **Escenario/ejemplo de comerciante:** Tiene una integración personalizada que depende de `id_product` para el seguimiento. Usar "ID de producto" aquí garantiza la coherencia.
- **Campo de categoría de producto:**

  - **Qué hace este ajuste:** Determina qué información de categoría se envía a Facebook.
  - **Efecto de cambiar este ajuste:**
    - *Categoría predeterminada de PrestaShop:* Utiliza el nombre de la categoría principal del producto.
    - *Categoría de producto de Google:* Utiliza la Categoría de producto de Google (si está asignada). Esto a menudo es preferido por Facebook para una mejor coincidencia.
  - **Valor recomendado:** **Categoría de producto de Google** si las tiene asignadas. De lo contrario, "Categoría predeterminada de PrestaShop".
  - **Escenario/ejemplo de comerciante:** Vende "Camisetas" en PrestaShop, pero la Categoría de producto de Google es "Ropa y accesorios > Ropa > Camisas y tops > Camisetas". Usar la categoría de Google proporciona datos más específicos a Facebook.
- **Campo de marca de producto:**

  - **Qué hace este ajuste:** Selecciona qué campo de los datos de su producto debe usarse para el atributo `brand` en el feed de Facebook.
  - **Efecto de cambiar este ajuste:**
    - *Nombre del fabricante:* Utiliza el fabricante asignado al producto en PrestaShop.
    - *Nombre del proveedor:* Utiliza el proveedor asignado al producto.
  - **Valor recomendado:** **Nombre del fabricante**. Este es el campo más común y lógico para "marca".
  - **Escenario/ejemplo de comerciante:** Vende zapatos Nike. Seleccionar "Nombre del fabricante" completará correctamente "Nike" como la marca en su feed.
- **Campo de tipo de producto:**

  - **Qué hace este ajuste:** Especifica qué información debe usarse para el campo `product_type` en el feed de Facebook.
  - **Efecto de cambiar este ajuste:**
    - *Categoría predeterminada de PrestaShop:* Utiliza el nombre de la categoría principal del producto.
    - *Categoría de producto de Google:* Utiliza la Categoría de producto de Google (si está asignada).
  - **Valor recomendado:** **Categoría de producto de Google** si está disponible, de lo contrario "Categoría predeterminada de PrestaShop". Esto ayuda a Facebook a comprender el tipo de producto.
  - **Escenario/ejemplo de comerciante:** Para un producto en "Electrónica > Smartphones", la Categoría de producto de Google podría ser "Electrónica > Comunicaciones > Telefonía > Teléfonos móviles".
- **Campo de imagen de producto:**

  - **Qué hace este ajuste:** Determina qué URL de imagen se utiliza para el `image_link` en el feed.
  - **Efecto de cambiar este ajuste:**
    - *Imagen de producto predeterminada:* Utiliza la imagen principal asociada al producto.
    - *Imagen de combinación (si está disponible):* Si se exportan combinaciones, esto utilizará la imagen específica asignada a esa combinación, de lo contrario, la imagen de producto predeterminada.
  - **Valor recomendado:** **Imagen de combinación (si está disponible)**. Esto asegura que si un cliente ve una camisa roja, el anuncio muestre una camisa roja, no solo la imagen genérica del producto.
  - **Escenario/ejemplo de comerciante:** Tiene un producto con múltiples combinaciones de colores, cada una con su propia imagen. Este ajuste asegura que la imagen de color correcta se muestre en el anuncio.
- **Campo de descripción del producto:**

  - **Qué hace este ajuste:** Selecciona qué campo de descripción de PrestaShop (`description` o `short_description`) se utiliza para el atributo `description` en el feed de Facebook.
  - **Efecto de cambiar este ajuste:**
    - *Descripción:* Exporta la descripción completa y detallada del producto.
    - *Descripción corta:* Exporta el breve resumen del producto.
  - **Valor recomendado:** **Descripción**. Facebook generalmente prefiere una descripción más detallada para un mejor contexto del anuncio.
  - **Escenario/ejemplo de comerciante:** Desea proporcionar la mayor cantidad de información posible en sus anuncios. Usar la descripción completa asegura esto.
- **Campo de descripción corta del producto:**

  - **Qué hace este ajuste:** Selecciona qué campo de descripción de PrestaShop (`description` o `short_description`) se utiliza para el atributo `short_description` en el feed de Facebook.
  - **Efecto de cambiar este ajuste:**
    - *Descripción:* Exporta la descripción completa y detallada del producto.
    - *Descripción corta:* Exporta el breve resumen del producto.
  - **Valor recomendado:** **Descripción corta**. Esto es útil si el feed de Facebook requiere tanto una descripción larga como una corta, o si prefiere un resumen conciso para ciertos formatos de anuncios.
  - **Escenario/ejemplo de comerciante:** Desea un resumen conciso para el campo `short_description` en su feed.
- **Delimitador CSV:**

  - **Qué hace este ajuste:** Especifica el carácter utilizado para separar los valores en el archivo CSV generado (por ejemplo, coma, punto y coma).
  - **Efecto de cambiar este ajuste:**
    - *Coma (,):* Formato CSV estándar.
    - *Punto y coma (;):* Común en algunas configuraciones regionales europeas.
  - **Valor recomendado:** **Coma (,)**. Este es el delimitador más ampliamente aceptado para archivos CSV, incluido por Facebook.
  - **Escenario/ejemplo de comerciante:** Si la herramienta de importación de Facebook especifica un delimitador de punto y coma, lo cambiaría aquí. De lo contrario, mantenga la coma.
- **Eliminar imágenes del feed:**

  - **Qué hace este ajuste:** Si está habilitado, el módulo eliminará los enlaces de imagen del feed generado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Las columnas `image_link` y `additional_image_link` en el feed estarán vacías. Esto generalmente NO se recomienda, ya que las imágenes son cruciales para los anuncios dinámicos.
    - *Cuando está deshabilitado (NO):* Los enlaces de imagen se incluirán en el feed.
  - **Valor recomendado:** **NO**. Las imágenes son fundamentales para los anuncios visuales.
  - **Escenario/ejemplo de comerciante:** Este ajuste rara vez es útil a menos que tenga una configuración muy específica y avanzada donde las imágenes se manejan completamente por separado.

#### Excluir productos

Esta sección le permite evitar que productos específicos se incluyan en su feed de Facebook.

- **Excluir productos por ID:**
  - **Qué hace este ajuste:** Le permite ingresar una lista de ID de productos separadas por comas que no desea que aparezcan en su catálogo de productos de Facebook.
  - **Efecto de cambiar este ajuste:**
    - *Productos listados aquí:* Se omitirán completamente del feed generado.
  - **Valor recomendado:** Déjelo vacío a menos que tenga productos específicos que nunca desee anunciar (por ejemplo, productos de prueba internos, servicios no aptos para anuncios dinámicos).
  - **Escenario/ejemplo de comerciante:** Vende tanto productos físicos como servicios digitales. Podría excluir los productos de servicios digitales del feed, ya que no se ajustan al formato de anuncio dinámico.

#### Botón Generar feed

- **Qué hace este botón:** Inicia el proceso de generación del archivo CSV del catálogo de productos basándose en todos los ajustes que ha configurado anteriormente.
- **Efecto de hacer clic en este botón:** El módulo procesará sus productos y creará un archivo CSV descargable. Dependiendo del número de productos, esto podría llevar algún tiempo.
- **Acción recomendada:** Haga clic en este botón después de haber revisado y guardado todos sus ajustes deseados.
- **Escenario/ejemplo de comerciante:** Después de realizar cambios en las descripciones de sus productos o agregar nuevos productos, haría clic aquí para generar un feed actualizado para Facebook.

#### Botón Descargar feed

- **Qué hace este botón:** Le permite descargar el archivo CSV del catálogo de productos generado más recientemente a su computadora.
- **Efecto de hacer clic en este botón:** Su navegador descargará el archivo `facebook_products.csv`.
- **Acción recomendada:** Descargue el archivo después de la generación y luego súbalo a su Administrador comercial de Facebook.
- **Escenario/ejemplo de comerciante:** Una vez que se genera el feed, lo descarga y luego navega a su Administrador comercial de Facebook > Catálogos > Fuentes de datos para subir el CSV.

### 2.2 Pantalla de administración dedicada: AdminExportProductsFeedController

Esta es la pantalla de administración principal donde gestiona la generación real del feed de productos y revisa los datos que se exportarán.

**Ubicación del menú:** Back Office > Módulos > Gestor de módulos > Configurar "Exportar catálogo para anuncios dinámicos de Facebook Pixel" > (Esta pantalla es la interfaz de configuración principal en sí misma, a menudo se accede directamente después de hacer clic en "Configurar").

Esta pantalla presenta una interfaz tipo cuadrícula o un formulario con varias opciones para controlar la salida de su feed de productos. Los campos que se enumeran a continuación representan los puntos de datos que se pueden incluir en su catálogo de productos de Facebook.

- **ID:** El identificador único del producto (basado en su configuración de "Identificación del producto").
- **item_group_id:** Se utiliza para combinaciones de productos para agruparlos bajo un único producto padre.
- **Título:** El nombre del producto.
- **Descripción corta:** El breve resumen del producto.
- **Descripción:** La descripción completa del producto.
- **Anulación:** (Probablemente una configuración interna del módulo, no exportada directamente a Facebook).
- **Disponibilidad:** Indica si el producto está en stock (`in stock`, `out of stock`).
- **Inventario:** La cantidad de stock actual.
- **Condición:** La condición del producto (por ejemplo, `new`, `used`, `refurbished`).
- **Enlace de imagen:** La URL de la imagen principal del producto.
- **Additional_image_link:** URLs de imágenes de productos adicionales.
- **Precio:** El precio actual del producto.
- **sale_price:** El precio de venta del producto (si corresponde).
- **Marca:** La marca del producto (fabricante).
- **Enlace:** La URL directa a la página del producto en su tienda.
- **Categoría de producto de Google:** La Categoría de producto de Google asignada al producto.
- **product_type:** El tipo de producto (por ejemplo, nombre de la categoría).
- **gender:** Para ropa, el género objetivo (por ejemplo, `male`, `female`, `unisex`).
- **size:** Para ropa, la talla del producto.
- **age_group:** Para ropa, el grupo de edad objetivo (por ejemplo, `newborn`, `infant`, `toddler`, `kids`, `adult`).

**Acciones y configuraciones disponibles:**
En esta pantalla, encontrará las diversas opciones de configuración detalladas en la sección 4.1. La "Tabla / Entidad administrada" aquí se refiere a la tabla virtual de datos de productos que el módulo construye antes de exportar. No hay una tabla de base de datos directa administrada por este controlador específico, sino que procesa y prepara datos de sus tablas de productos existentes de PrestaShop.

**Efecto de los cambios:**
Cualquier cambio realizado en la configuración de esta pantalla (por ejemplo, seleccionar un idioma diferente, habilitar/deshabilitar la exportación de combinaciones) alterará directamente el contenido y el formato del archivo CSV generado cuando haga clic en el botón "Generar feed".

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1. Periódicamente (por ejemplo, diaria o semanalmente, dependiendo de la frecuencia con la que cambie su catálogo de productos) visite esta página de configuración.
2. Asegúrese de que la configuración de idioma, moneda y stock/productos activos sea correcta.
3. Haga clic en "Generar feed" para crear un CSV actualizado.
4. Descargue el CSV generado.
5. Suba este nuevo CSV a su Administrador comercial de Facebook para actualizar su catálogo de productos. Facebook también ofrece opciones para programar extracciones automáticas desde una URL, que se pueden configurar una vez que tenga una URL de feed estable (a menudo proporcionada por el módulo o la configuración de su servidor).

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | Seleccionar idioma para la exportación | Su idioma principal | Determina el idioma de los nombres/descripciones de los productos en el feed. |
| | Seleccionar moneda para la exportación | Su moneda principal | Determina la moneda de los precios en el feed. |
| | Exportar solo productos activos | SÍ | Incluye solo productos activos, evitando anuncios de artículos no disponibles. |
| | Exportar solo productos en stock | SÍ | Incluye solo productos en stock, evitando anuncios de artículos agotados. |
| | Exportar combinaciones de productos | SÍ | Exporta cada variación de producto (talla, color) como un artículo único para anuncios granulares. |
| | Identificación del producto (campo ID) | ID de producto | Define el identificador único para los productos en el feed. |
| | Campo de categoría de producto | Categoría de producto de Google (si está disponible) | Especifica los datos de categoría para Facebook. |
| | Campo de marca de producto | Nombre del fabricante | Especifica los datos de marca para Facebook. |
| | Campo de tipo de producto | Categoría de producto de Google (si está disponible) | Especifica los datos de tipo de producto para Facebook. |
| | Campo de imagen de producto | Imagen de combinación (si está disponible) | Asegura la imagen correcta para las variaciones de producto. |
| | Campo de descripción del producto | Descripción | Utiliza la descripción completa del producto para el feed. |
| | Campo de descripción corta del producto | Descripción corta | Utiliza la descripción corta del producto para el feed. |
| | Delimitador CSV | Coma (,) | Carácter que separa los valores en el archivo CSV. |
| | Eliminar imágenes del feed | NO | Incluye enlaces de imagen en el feed (esencial para los anuncios). |
| | Excluir productos por ID | Vacío | Lista de ID de productos separadas por comas para excluir del feed. |
| | Botón Generar feed | Hacer clic después de finalizar la configuración | Crea el archivo CSV del catálogo de productos. |
| | Botón Descargar feed | Hacer clic después de la generación | Descarga el archivo CSV a su computadora. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mi archivo de feed generado está vacío o contiene muy pocos productos.**
R:

- **Verifique "Exportar solo productos activos" y "Exportar solo productos en stock":** Asegúrese de que no sean demasiado restrictivos si espera muchos productos.
- **Verifique el idioma y la moneda seleccionados:** Asegúrese de que existan productos para el idioma seleccionado y que tengan precios en la moneda seleccionada.
- **Verifique la visibilidad del producto:** ¿Sus productos son realmente visibles en el contexto de la tienda seleccionado (si tiene multi-tienda habilitada)?
- **Borrar caché de Smarty:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché". A veces, los datos antiguos pueden interferir.

**P: Facebook está rechazando mi feed o mostrando errores.**
R:

- **Verifique el delimitador CSV:** Asegúrese de que coincida con lo que Facebook espera (generalmente una coma).
- **Revise los mensajes de error de Facebook:** El Administrador comercial de Facebook proporciona informes de errores detallados. Preste mucha atención a los campos que están causando problemas (por ejemplo, enlaces de imagen faltantes, precios no válidos).
- **Verifique los enlaces de imagen:** Asegúrese de que las imágenes de sus productos sean de acceso público y que las URL sean correctas. Si tiene SSL (HTTPS), asegúrese de que los enlaces de imagen también sean HTTPS.
- **Busque caracteres especiales:** A veces, los caracteres inusuales en los nombres o descripciones de los productos pueden causar problemas de análisis.
- **Asegure ID únicos:** La configuración de "Identificación del producto" es crucial. Cada elemento en el feed (especialmente las combinaciones) necesita un `id` único.

**P: Las imágenes de mis productos no se muestran en el feed de Facebook.**
R:

- **Verifique la configuración "Eliminar imágenes del feed":** Asegúrese de que esté configurada en **NO**.
- **Verifique las URL de las imágenes:** Abra algunos enlaces de imágenes del CSV generado en su navegador. ¿Cargan correctamente? ¿Son accesibles desde fuera de su red?
- **Imágenes de combinación:** Si está utilizando imágenes de combinación, asegúrese de que estén asignadas correctamente a sus combinaciones de productos en PrestaShop.

**P: ¿Con qué frecuencia debo generar y subir un nuevo feed?**
R:

- Depende de la frecuencia con la que cambie su catálogo de productos.
- **Diario:** Recomendado para la mayoría de las tiendas, especialmente si tiene cambios frecuentes de stock, actualizaciones de precios o nuevas adiciones de productos.
- **Semanal:** Aceptable para tiendas con un catálogo muy estable.
- **Extracción automatizada:** La mejor práctica es configurar Facebook para que extraiga automáticamente el feed de una URL. Este módulo genera el feed bajo demanda, por lo que es posible que necesite un trabajo cron para activar la generación y hacer que el archivo esté disponible en una URL consistente para que Facebook lo extraiga.

**P: El módulo no aparece en mi lista de módulos o no puedo configurarlo.**
R:

- **Volver a subir:** Intente volver a subir el archivo ZIP del módulo a través del Gestor de módulos.
- **Verificar permisos:** Asegúrese de que la carpeta del módulo (`/modules/pixelfeed/`) y su contenido tengan los permisos de archivo correctos (generalmente 755 para carpetas, 644 para archivos).
- **Registros de errores:** Verifique su modo de depuración de PrestaShop y los registros de errores del servidor para detectar cualquier error de PHP durante la instalación o configuración.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada del módulo "Exportar catálogo para anuncios dinámicos de Facebook Pixel" para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura

El módulo sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, centrándose principalmente en la funcionalidad administrativa para generar un feed de productos. Aprovecha las clases principales `Product` y `Combination` de PrestaShop para extraer datos, luego formatea estos datos en un archivo CSV compatible con la especificación del catálogo de anuncios dinámicos de Facebook. El archivo principal del módulo (`index.php`) actúa como punto de entrada para la configuración, mientras que los controladores de administración dedicados manejan la lógica compleja de extracción de datos y generación de feeds. Los controladores frontales están presentes, probablemente para servir el feed generado o para solicitudes AJAX específicas.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `controllers/front/feed.php`
  - **Nombre de la clase:** `PixelfeedFeedModuleFrontController` (o similar, extendiendo `ModuleFrontController`)
  - **Responsabilidad:** Este controlador es probablemente responsable de servir el archivo de feed CSV generado a través de una URL pública. Manejaría las solicitudes a una ruta específica (por ejemplo, `tutienda.com/module/pixelfeed/feed`) y generaría el contenido CSV directamente. Esto es crucial para las extracciones programadas de Facebook.
- `controllers/front/index.php`
  - **Nombre de la clase:** `PixelfeedIndexModuleFrontController` (o similar, extendiendo `ModuleFrontController`)
  - **Responsabilidad:** Esto podría ser un marcador de posición o un controlador para una acción de front-office muy específica y no relacionada con el feed, aunque la función principal del módulo es la generación de feeds en el back-office. Potencialmente podría manejar solicitudes AJAX relacionadas con el estado del feed u otras interacciones menores.

#### Controladores de administración de Back-Office

- `controllers/admin/AdminExportProductsFeed.php`
  - **Nombre de la clase:** `AdminExportProductsFeedController` (extendiendo `ModuleAdminController`)
  - **Nombre de la pestaña:** Este controlador es el corazón de la interfaz administrativa del módulo. Es la pantalla de configuración principal donde los comerciantes interactúan con los ajustes y activan la generación del feed.
  - **Entidad administrada:** No gestiona directamente una única entidad `ObjectModel`, sino que orquesta la recuperación y el procesamiento de datos de `Product` y `Combination` del núcleo de PrestaShop.
  - **Funcionalidad clave:**
    - Maneja la visualización del formulario de configuración (`renderForm`).
    - Procesa los envíos de formularios (`postProcess`) para guardar la configuración del módulo (por ejemplo, idioma, moneda, opciones de exportación).
    - Activa la lógica de extracción de datos y generación de CSV.
    - Gestiona la exclusión de productos.
    - Los campos del formulario y las columnas enumeradas en el dossier del módulo (`ID`, `item_group_id`, `Title`, etc.) representan la *estructura de salida* del feed, no necesariamente campos de entrada directos en el formulario de administración, aunque muchos ajustes influyen en estas columnas de salida.
    - Claves de configuración asociadas: `pf_tree`, `PS_LANG_DEFAULT`, `PS_CURRENCY_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `pf_pixelfeed_products`, `pf_remember_settings`, `pf_export_not_group_combinations`, `pf_export_active`, `pf_export_instock`, `pf_export_identification`, `pf_export_category`, `pf_export_manufacturers_default`, `pf_export_type`, `pf_export_img`, `pf_export_manufacturers`, `pf_export_description_what`, `pf_export_short_description_what`, `pf_export_suppliers`, `pf_export_delimiter`, `pf_delete_images`. Estas son las claves de `Configuration` utilizadas para almacenar la configuración del módulo.
- `controllers/admin/index.php`
  - **Nombre de la clase:** `PixelfeedAdminIndexController` (o similar, extendiendo `ModuleAdminController`)
  - **Nombre de la pestaña:** Este podría ser un controlador de administración secundario, potencialmente para un panel de control o una vista de administración más simple, o podría ser un archivo heredado. Dado que `AdminExportProductsFeedController` maneja la lógica principal, este `index.php` podría ser una redirección o una página de aterrizaje muy básica dentro de la sección de administración.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo indica que no hay clases personalizadas en el directorio `classes/`. Esto implica que la lógica central para la extracción de datos y la generación del feed probablemente está contenida dentro del archivo principal del módulo (`pixelfeed/index.php`) y el `AdminExportProductsFeedController`. Utiliza directamente las clases principales de PrestaShop `Product`, `Combination`, `Category`, `Manufacturer`, `Image` y `Tools`.

### 4.4 Activos de JavaScript (`views/js/`)

- `pixelfeed/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office.
  - **Funcionalidad:** Probablemente proporciona funcionalidad de autocompletado para los campos de entrada dentro de la configuración de administración, como el campo "Excluir productos por ID". Se vincularía a los elementos de entrada, realizaría llamadas AJAX para buscar productos y mostraría sugerencias.
- `pixelfeed/views/js/admin-app.js`
  - **Alcance:** Back-office.
  - **Funcionalidad:** Este es el archivo JavaScript principal para la interfaz de administración del módulo. Manejaría:
    - Validación y envío de formularios.
    - Solicitudes AJAX para generar el feed (a `AdminExportProductsFeedController`).
    - Visualización de indicadores de carga o mensajes de éxito/error.
    - Potencialmente actualizaciones dinámicas de la interfaz de usuario basadas en las opciones seleccionadas.
    - Interacciones con Fancybox (si se usa para la selección de categorías o similar).

### 4.5 Hojas de estilo CSS (`views/css/`)

- `pixelfeed/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Estilo de administración del back-office.
  - **Funcionalidad:** Estiliza el menú desplegable de autocompletado y los campos de entrada, asegurando una apariencia consistente dentro del back-office de PrestaShop.
- `pixelfeed/views/admin-theme.css`
  - **Alcance:** Estilo de administración del back-office.
  - **Funcionalidad:** Proporciona un estilo general para la página de configuración del módulo, asegurando que se integre bien con el tema del back-office de PrestaShop. Esto podría incluir el diseño, los estilos de los botones y el estilo de los elementos del formulario.
- `pixelfeed/views/css/admin-app.css`
  - **Alcance:** Estilo de administración del back-office.
  - **Funcionalidad:** Estilo específico para los elementos de la interfaz de usuario personalizados del módulo, como el progreso de generación del feed, las alertas o cualquier widget personalizado en la página de configuración.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza principalmente plantillas Smarty para su interfaz de Back Office.

#### Plantillas de administración (`views/templates/admin/`)

- `pixelfeed/views/templates/admin/dashboard.tpl`
  - **Propósito:** Podría ser una descripción general tipo panel de control para el módulo, que potencialmente muestre el estado del feed, la fecha de la última generación o enlaces rápidos.
- `pixelfeed/views/templates/admin/feeds.tpl`
  - **Propósito:** Probablemente la plantilla principal para mostrar las opciones y los resultados de la generación del feed, posiblemente incluyendo una lista de feeds generados o un registro.
- `pixelfeed/views/templates/admin/form-chrome.tpl`
  - **Propósito:** Un envoltorio genérico o una plantilla estructural para formularios dentro de la interfaz de administración, asegurando un diseño y estilo consistentes.
- `pixelfeed/views/templates/admin/layout.tpl`
  - **Propósito:** La plantilla de diseño general para las páginas de administración del módulo, que define la estructura general, el encabezado y el pie de página.

#### Otras plantillas (`views/`)

- `pixelfeed/lib/searchTool/views/scripts.tpl`
  - **Propósito:** Incluye JavaScript para la herramienta de búsqueda, probablemente renderizado al final del cuerpo HTML o dentro de una sección específica.
- `pixelfeed/views/categories-fancybox.tpl`
  - **Propósito:** Plantilla para un modal de Fancybox, posiblemente utilizado para seleccionar categorías para incluir/excluir del feed, o para mostrar árboles de categorías.
- `pixelfeed/views/exclude-products.tpl`
  - **Propósito:** Plantilla para la sección donde los productos pueden excluirse por ID, potencialmente incluyendo el campo de entrada de autocompletado.
- `pixelfeed/views/google_lang_links.tpl`
  - **Propósito:** Podría estar relacionado con la visualización de enlaces o información específicos del idioma, posiblemente para las categorías de productos de Google.
- `pixelfeed/views/returnAlert.tpl`
  - **Propósito:** Una plantilla para mostrar mensajes de éxito, error o advertencia al usuario en la interfaz de administración.
- `pixelfeed/views/script-fancybox.tpl`
  - **Propósito:** Incluye JavaScript para la integración de Fancybox, a menudo para ventanas emergentes modales.
- `pixelfeed/views/script.tpl`
  - **Propósito:** Inclusiones generales de JavaScript para las páginas de administración del módulo, potencialmente para variables globales o inicializaciones.

### 4.7 Esquema de la base de datos y mapa de ganchos

#### Tablas de la base de datos

El dossier del módulo indica que no hay archivos SQL personalizados, lo que sugiere que no crea sus propias tablas de base de datos dedicadas. Todas las configuraciones se almacenan en la tabla `ps_configuration` de PrestaShop utilizando claves con el prefijo `pf_` (por ejemplo, `pf_export_active`, `pf_export_delimiter`).

#### Tabla de ganchos registrados

La función principal del módulo es la exportación de datos, no la visualización en el front-office. Los ganchos de front-office enumerados (Header, Columns, Product, Footer) probablemente *no* se utilizan para la salida visual directa de este módulo. En su lugar, podrían registrarse para:

- **`displayHeader`**: Para incluir los activos JavaScript o CSS necesarios para el controlador de feed del front-office del módulo (si sirve el feed directamente).
- **Ganchos `action*`**: El módulo probablemente utiliza ganchos `action` (por ejemplo, `actionProductUpdate`, `actionProductAdd`) internamente para borrar cachés o activar avisos de regeneración en el back-office cuando cambian los datos del producto, aunque estos no se enumeran explícitamente en el dossier. La lógica central del módulo para generar el feed se activa normalmente de forma manual o mediante un trabajo cron, no directamente por un gancho del front-office.

| Nombre del gancho | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de las páginas del front-office. | Potencialmente para cargar JS/CSS para el servicio de feed del front-office, o para integraciones muy específicas y no visuales. |
| `displayRightColumn` / `displayLeftColumn` | En las columnas laterales de las páginas del front-office. | Es poco probable que se utilice para la función principal de este módulo; posiblemente para un bloque de depuración o una característica muy específica no central para la generación del feed. |
| `displayProductAdditionalInfo` / `displayProductButtons` (Página del producto) | En las páginas de productos. | Es poco probable que se utilice para la función principal de este módulo. |
| `displayFooter` | En el pie de página de las páginas del front-office. | Es poco probable que se utilice para la función principal de este módulo. |
| (Implícito) `actionProductUpdate` / `actionProductAdd` / `actionProductDelete` | Después de que los datos del producto cambian en el BO. | Para invalidar los datos del feed en caché o solicitar al administrador la regeneración del feed. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Exportar catálogo para anuncios dinámicos de Facebook Pixel", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.

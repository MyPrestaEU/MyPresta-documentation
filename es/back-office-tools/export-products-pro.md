---
title: "Export Products Pro - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Export Products Pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "Export Products Pro - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Export Products Pro en MyPresta.eu](https://mypresta.eu/modules/administration-tools/export-products-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/export-products-pro/)
>
> ---


# Export Products Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para el funcionamiento general de PrestaShop, pero este módulo no tiene requisitos exóticos específicos más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Export Products Pro)

Esta es la pantalla de configuración principal donde define el comportamiento general y los ajustes para sus exportaciones de productos.

#### Ajustes Generales

-   **Formato de exportación**:

    -   **Qué hace este ajuste:** Determina el formato de archivo para sus datos exportados.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en CSV:* El módulo generará un archivo de Valores Separados por Comas, que es ampliamente compatible con software de hoja de cálculo como Excel, Google Sheets o LibreOffice Calc. Este es el formato más común y versátil.
        -   *Cuando se establece en XML:* El módulo generará un archivo de Lenguaje de Marcado Extensible, a menudo utilizado para un intercambio de datos más estructurado entre sistemas o para feeds de productos específicos (por ejemplo, Google Shopping).
    -   **Valor recomendado:** CSV para uso general y análisis de hojas de cálculo. XML si tiene un sistema específico que lo requiere.
    -   **Escenario / ejemplo del comerciante:** Si desea abrir los datos en Excel para analizar precios, elija CSV. Si está creando un feed para una aplicación de terceros que especifica XML, elija XML.
-   **Delimitador**:

    -   **Qué hace este ajuste:** Este carácter separa las diferentes columnas (campos) en su archivo CSV.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en coma (,):* Cada dato en una fila estará separado por una coma. Esto es estándar para muchos sistemas.
        -   *Cuando se establece en punto y coma (;):* Cada dato estará separado por un punto y coma. Esto es común en algunas regiones europeas o cuando las comas pueden aparecer dentro de sus datos de producto (por ejemplo, en descripciones), causando problemas de análisis.
    -   **Valor recomendado:** Coma (`,`) para la mayoría de los casos. Si su software de hoja de cálculo tiene dificultades para abrir el CSV correctamente, pruebe con punto y coma (`;`).
    -   **Escenario / ejemplo del comerciante:** Si abre su CSV en Excel y todos los datos aparecen en una columna, intente cambiar el delimitador a punto y coma y vuelva a exportar.
-   **Exportar solo productos activos**:

    -   **Qué hace este ajuste:** Controla si solo los productos actualmente visibles y comprables en su tienda se incluyen en la exportación.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* Solo se exportarán los productos con su "Estado" establecido en "En línea" o "Activo" en su back office de PrestaShop. Esto es útil para el inventario actual.
        -   *Cuando está deshabilitado (No):* Se exportarán todos los productos, incluidos los marcados como inactivos o deshabilitados. Esto es útil para una copia de seguridad completa del catálogo o una auditoría.
    -   **Valor recomendado:** Sí, para la mayoría de las exportaciones operativas.
    -   **Escenario / ejemplo del comerciante:** Si está generando un feed de productos para Google Shopping, solo desea productos activos, así que habilite esto. Si está haciendo una copia de seguridad completa de los datos, deshabilítelo.
-   **Exportar solo productos en stock**:

    -   **Qué hace este ajuste:** Filtra la exportación para incluir solo los productos que actualmente tienen una cantidad mayor que cero.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* Solo se exportarán los productos que actualmente están en stock.
        -   *Cuando está deshabilitado (No):* Se exportarán los productos independientemente de su nivel de stock (en stock o sin stock).
    -   **Valor recomendado:** Sí, si está creando un feed para ventas o disponibilidad actual.
    -   **Escenario / ejemplo del comerciante:** Si está enviando una lista de productos disponibles a un dropshipper, habilite esto. Si necesita ver todos los productos, incluidos los que necesita reordenar, deshabilítelo.
-   **Exportar imágenes de productos**:

    -   **Qué hace este ajuste:** Determina si las URL de las imágenes de sus productos se incluyen en la exportación.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* El archivo CSV/XML contendrá columnas con las URL de las imágenes de sus productos.
        -   *Cuando está deshabilitado (No):* Las URL de las imágenes se omitirán, lo que resultará en un tamaño de archivo más pequeño si las imágenes no son necesarias.
    -   **Valor recomendado:** Sí, si necesita imágenes para marketplaces o catálogos externos.
    -   **Escenario / ejemplo del comerciante:** Si está actualizando un catálogo de productos en otra plataforma que requiere URL de imágenes, habilite esto.
-   **Exportar descripción corta del producto**:

    -   **Qué hace este ajuste:** Incluye la descripción corta (resumen) de sus productos en la exportación.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* La descripción corta de cada producto se incluirá como una columna.
        -   *Cuando está deshabilitado (No):* La descripción corta se omitirá.
    -   **Valor recomendado:** Sí, ya que las descripciones cortas se utilizan a menudo para listados de productos y resultados de búsqueda.
    -   **Escenario / ejemplo del comerciante:** Si está creando un feed de productos para un sitio de comparación que muestra descripciones cortas, habilite esto.
-   **Exportar descripción del producto**:

    -   **Qué hace este ajuste:** Incluye la descripción completa y detallada de sus productos en la exportación.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* La descripción completa del producto se incluirá como una columna.
        -   *Cuando está deshabilitado (No):* La descripción completa se omitirá.
    -   **Valor recomendado:** Sí, para una exportación de datos completa.
    -   **Escenario / ejemplo del comerciante:** Si está migrando su tienda a una nueva plataforma y necesita todo el contenido del producto, habilite esto.
-   **Recordar ajustes**:

    -   **Qué hace este ajuste:** Si está habilitado, el módulo guardará sus últimos ajustes de exportación utilizados (filtros, campos seleccionados) para su próxima exportación.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* El módulo rellenará previamente el formulario de exportación con sus elecciones anteriores, ahorrando tiempo para exportaciones repetitivas.
        -   *Cuando está deshabilitado (No):* El formulario de exportación siempre se restablecerá a la configuración predeterminada cada vez que lo visite.
    -   **Valor recomendado:** Sí, si realiza exportaciones similares con frecuencia.
    -   **Escenario / ejemplo del comerciante:** Si exporta regularmente una lista de productos activos y en stock con campos específicos, habilitar esto hará que su flujo de trabajo sea más rápido.

#### Opciones de Filtro

-   **Exportar productos de la categoría**:

    -   **Qué hace este ajuste:** Le permite seleccionar categorías de productos específicas para incluir en su exportación.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan categorías específicas:* Solo se exportarán los productos que pertenezcan a esas categorías.
        -   *Cuando no se seleccionan categorías (o se seleccionan todas):* Todos los productos, independientemente de la categoría, se considerarán para la exportación (sujeto a otros filtros).
    -   **Valor recomendado:** Seleccione categorías específicas si necesita una exportación dirigida; de lo contrario, déjelo sin seleccionar para un catálogo completo.
    -   **Escenario / ejemplo del comerciante:** Si solo desea exportar productos de su categoría "Electrónica", selecciónela aquí.
-   **Exportar solo categorías padre**:

    -   **Qué hace este ajuste:** Si ha seleccionado categorías, esta opción refina aún más si los productos de las subcategorías también se incluyen.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* Solo se exportarán los productos asignados directamente a las categorías padre seleccionadas. Los productos en sus subcategorías se excluirán.
        -   *Cuando está deshabilitado (No):* Se exportarán los productos de las categorías padre seleccionadas Y todas sus subcategorías.
    -   **Valor recomendado:** No, para la mayoría de los casos, ya que normalmente también desea productos de subcategorías. Habilítelo solo si tiene una razón específica para excluir productos de subcategorías.
    -   **Escenario / ejemplo del comerciante:** Si tiene "Ropa" como categoría padre y "Camisetas" como subcategoría, habilitar esto exportaría productos directamente en "Ropa" pero no los de "Camisetas".
-   **Exportar productos del fabricante**:

    -   **Qué hace este ajuste:** Le permite filtrar productos por su fabricante asignado.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan fabricantes específicos:* Solo se exportarán los productos de esos fabricantes.
        -   *Cuando no se seleccionan fabricantes (o se seleccionan todos):* Se considerarán los productos de todos los fabricantes.
    -   **Valor recomendado:** Seleccione fabricantes específicos para exportaciones dirigidas.
    -   **Escenario / ejemplo del comerciante:** Si necesita enviar una lista de productos a una marca específica para su revisión, seleccione su fabricante aquí.
-   **Exportar productos del proveedor**:

    -   **Qué hace este ajuste:** Le permite filtrar productos por su proveedor asignado.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan proveedores específicos:* Solo se exportarán los productos de esos proveedores.
        -   *Cuando no se seleccionan proveedores (o se seleccionan todos):* Se considerarán los productos de todos los proveedores.
    -   **Valor recomendado:** Seleccione proveedores específicos para exportaciones dirigidas.
    -   **Escenario / ejemplo del comerciante:** Si necesita proporcionar una lista de productos que tiene en stock de un proveedor en particular, selecciónelos aquí.

### 2.2 Pantalla de Administración Dedicada: Panel de Export Products Pro (Back Office > Catálogo > Export Products Pro)

Esta es la interfaz principal para iniciar y gestionar sus exportaciones de productos.

-   **Nombre de la pantalla y ubicación del menú:** **Catálogo > Export Products Pro**
-   **Acciones y ajustes disponibles:**
    -   **Botón Exportar:** Este es el botón de acción principal. Al hacer clic en él, se iniciará el proceso de exportación según la configuración que haya establecido en esta página.
    -   **Selección de Campos:** Debajo de la configuración general, encontrará una lista completa de todos los campos de producto y combinación disponibles. Puede marcar o desmarcar individualmente qué campos desea incluir en su exportación.
        -   **Campos de Producto:** Incluye detalles estándar del producto como ID, nombre, referencia, EAN13, UPC, precio, cantidad, peso, descripciones, etc.
        -   **Campos de Combinación:** Si sus productos tienen combinaciones (por ejemplo, tamaño, color), verá campos específicos para combinaciones como "ID de Combinación", "Atributo (Nombre:Tipo:Posición)", "Valor (Valor:Posición)", "Impacto en el precio", "Impacto en el peso", "Predeterminado (0 = No, 1 = Sí)", "Fecha de disponibilidad de la combinación".
    -   **Efecto de los cambios:**
        -   **Seleccionar/Deseleccionar campos:** Solo los campos marcados aparecerán como columnas en su archivo CSV/XML exportado. Esto le permite crear exportaciones altamente personalizadas, incluyendo solo los datos que necesita y omitiendo información innecesaria.
    -   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
        1.  Navegue a **Catálogo > Export Products Pro**.
        2.  Revise los "Ajustes Generales" y las "Opciones de Filtro" en la parte superior de la página. Ajústelos según si necesita productos activos, productos en stock, categorías específicas, fabricantes o proveedores.
        3.  Seleccione cuidadosamente los "Campos de Producto" y "Campos de Combinación" que desea incluir en su exportación. Si no está seguro, a menudo es más seguro seleccionar más campos inicialmente y luego eliminar las columnas no deseadas en su software de hoja de cálculo.
        4.  Haga clic en el botón "Exportar". El módulo generará y le pedirá que descargue el archivo CSV o XML.
        5.  Abra el archivo descargado en su software de hoja de cálculo preferido (por ejemplo, Excel, Google Sheets) para verificar los datos y el formato.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Formato de exportación | CSV | Determina el tipo de archivo de salida (CSV o XML). |
| | Delimitador | Coma (`,`) | Carácter que separa los campos en CSV. Cambiar si ocurren problemas de análisis. |
| | Exportar solo productos activos | Sí | Incluye solo productos activos. |
| | Exportar solo productos en stock | Sí | Incluye solo productos con cantidad > 0. |
| | Exportar imágenes de productos | Sí | Incluye URL de imágenes en la exportación. |
| | Exportar descripción corta del producto | Sí | Incluye la descripción corta del producto. |
| | Exportar descripción del producto | Sí | Incluye la descripción completa del producto. |
| | Recordar ajustes | Sí | Guarda sus últimas opciones de exportación para mayor comodidad. |
| | Exportar productos de la categoría | (Ninguno seleccionado) | Filtra la exportación por categorías seleccionadas. |
| | Exportar solo categorías padre | No | Si se seleccionan categorías, incluye/excluye productos de subcategorías. |
| | Exportar productos del fabricante | (Ninguno seleccionado) | Filtra la exportación por fabricantes seleccionados. |
| | Exportar productos del proveedor | (Ninguno seleccionado) | Filtra la exportación por proveedores seleccionados. |
| **Panel de Export Products Pro** | **Selección de Campos** | Varía según la necesidad | Elija atributos específicos de producto/combinación para incluir como columnas en el archivo de exportación. |
| | Botón Exportar | N/A | Inicia la exportación de productos según todos los ajustes configurados. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mi archivo CSV exportado se ve ilegible o todos los datos están en una columna cuando lo abro en Excel.**
**R1:** Esto suele ser un problema de delimitador o de codificación de caracteres.

-   **Solución 1 (Delimitador):** Vuelva a la configuración del módulo, cambie el ajuste "Delimitador" de coma (`,`) a punto y coma (`;`), y vuelva a exportar. Intente abrir el nuevo archivo.
-   **Solución 2 (Codificación):** Al abrir el CSV en Excel, use la opción "Datos > Desde Texto/CSV". En el asistente de importación, asegúrese de seleccionar el "Origen del archivo" o "Codificación" correcto (normalmente `UTF-8`) y especifique el delimitador correcto.

**P2: Faltan algunos productos en mi exportación, pero sé que existen en mi tienda.**
**R2:** Verifique la configuración de sus filtros en la configuración del módulo:

-   **Solución:** Asegúrese de que "Exportar solo productos activos" y "Exportar solo productos en stock" estén configurados correctamente para sus necesidades. Si ha seleccionado categorías, fabricantes o proveedores específicos, verifique que los productos que faltan se encuentren dentro de esos filtros. Si desea todo, asegúrese de que no haya filtros seleccionados.

**P3: El proceso de exportación tarda mucho tiempo o se agota el tiempo de espera para catálogos grandes.**
**R3:** Exportar miles de productos puede consumir muchos recursos.

-   **Solución 1:** Intente exportar lotes más pequeños utilizando los filtros "Exportar productos de la categoría", "fabricante" o "proveedor".
-   **Solución 2:** Si tiene acceso a la configuración de su servidor, es posible que deba aumentar temporalmente `memory_limit` y `max_execution_time` de PHP en su archivo `php.ini`. Póngase en contacto con su proveedor de alojamiento para obtener ayuda con esto.
-   **Solución 3:** Deseleccione los campos innecesarios para reducir la cantidad de datos procesados.

**P4: ¿Cómo traduzco los encabezados de las columnas en el archivo exportado?**
**R4:** Los encabezados de las columnas en el archivo exportado generalmente se basan en los nombres de campo internos o las etiquetas predeterminadas de PrestaShop, y no son directamente traducibles a través de la interfaz del módulo.

-   **Solución:** La forma más sencilla es abrir el archivo CSV exportado en un programa de hoja de cálculo (como Excel o Google Sheets) y cambiar manualmente el nombre de los encabezados de las columnas a su idioma o terminología deseada. Guarde el archivo con los nuevos encabezados.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo Export Products Pro, destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Visión General de la Arquitectura

El módulo `Export Products Pro` sigue el patrón MVC estándar de PrestaShop, centrándose principalmente en la funcionalidad de back-office. Aprovecha los Controladores de Administración para su interfaz de usuario y clases personalizadas para el manejo de datos y la generación de feeds. La lógica central del módulo reside en su archivo principal `exportproducts.php` y el `AdminExportProductsController` que gestiona el proceso de exportación y la configuración. Utiliza `ObjectModel` para sus datos personalizados, si los hubiera, aunque en este caso, interactúa principalmente con los datos de productos centrales de PrestaShop.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

-   `controllers/front/feed.php`
    -   **Nombre de la clase y clase padre:** `ExportProductsFeedModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este controlador es probablemente responsable de generar un feed de productos (por ejemplo, XML o CSV) al que se puede acceder directamente a través de una URL. Manejaría la lógica para consultar productos basándose en parámetros específicos y mostrarlos en el formato elegido. Esto podría usarse para la generación automatizada de feeds para servicios externos.
-   `controllers/front/index.php`
    -   **Nombre de la clase y clase padre:** `ExportProductsIndexModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este controlador podría servir como un punto de entrada predeterminado o un respaldo para las solicitudes de front-office relacionadas con el módulo. Dada la función principal del módulo, podría redirigir o mostrar un mensaje simple, o podría ser un marcador de posición para futuras características de front-office.

#### Controladores de Administración de Back-Office

-   `controllers/admin/AdminExportProducts.php`
    -   **Nombre de la pestaña y entidad gestionada:** Este controlador gestiona el panel principal de "Export Products Pro" en el Back Office de PrestaShop, accesible a través de **Catálogo > Export Products Pro**. No gestiona una única entidad `ObjectModel` en el sentido tradicional, sino que orquesta el proceso de exportación de productos.
    -   **Responsabilidad:**
        -   Muestra el formulario de configuración para los ajustes de exportación (filtros, formato, delimitador, etc.).
        -   Maneja la solicitud POST cuando se hace clic en el botón "Exportar".
        -   Procesa los campos de producto y combinación seleccionados.
        -   Consulta la base de datos de PrestaShop para obtener datos de productos y combinaciones basándose en los filtros aplicados.
        -   Genera el contenido del archivo CSV o XML.
        -   Inicia la descarga del archivo al navegador del usuario.
        -   Gestiona la funcionalidad `ep_remember_settings` para persistir las elecciones del usuario.
-   `controllers/admin/index.php`
    -   **Responsabilidad:** Este es típicamente un archivo vacío o un archivo que contiene una simple declaración `die('No direct script access');`, que sirve como medida de seguridad para evitar el acceso directo al directorio `controllers/admin`. No contiene lógica de controlador activa.

### 4.3 Clases Principales y Modelos (`classes/`)

-   `classes/ExportProductsFeed.php`
    -   **Con qué tabla de base de datos interactúa:** Esta clase probablemente interactúa con varias tablas centrales de PrestaShop como `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_manufacturer`, `ps_supplier`, `ps_image`, `ps_product_attribute`, `ps_product_attribute_combination`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`, etc.
    -   **Si extiende `ObjectModel` y definición de los campos `$definition`:** Es poco probable que extienda `ObjectModel` directamente, ya que su función principal es *consultar* y *procesar* los datos de productos existentes en lugar de gestionar una nueva entidad de base de datos. Contendría métodos para obtener datos de productos con varias uniones (categorías, fabricantes, proveedores, imágenes, descripciones).
    -   **Métodos públicos clave y lógica de negocio encapsulada:**
        -   Métodos para recuperar datos de productos con varias uniones (categorías, fabricantes, proveedores, imágenes, descripciones).
        -   Métodos para manejar combinaciones de productos y sus atributos específicos.
        -   Lógica para aplicar filtros (activo, en stock, categoría, fabricante, proveedor).
        -   Métodos para formatear datos en estructuras CSV o XML.
        -   Potencialmente métodos para manejar grandes conjuntos de datos para evitar el agotamiento de la memoria.
-   `classes/index.php`
    -   **Responsabilidad:** Similar a `controllers/admin/index.php`, este es un archivo de seguridad para evitar la lista directa de directorios o la ejecución de archivos dentro del directorio `classes/`.

### 4.4 Activos JavaScript (`views/js/`)

El inventario de módulos proporcionado no indica archivos JavaScript personalizados (`[]`). Esto sugiere que el front-end del módulo (configuración del Back Office) se basa completamente en las bibliotecas JavaScript nativas de PrestaShop (por ejemplo, jQuery, JS central de PrestaShop) para el manejo de formularios, o su interfaz es lo suficientemente simple como para no requerir interacciones complejas del lado del cliente más allá de los envíos de formularios estándar.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El inventario de módulos proporcionado no indica archivos CSS personalizados (`[]`). Esto implica que la interfaz del Back Office del módulo utiliza el estilo predeterminado del back-office de PrestaShop, lo que garantiza una apariencia consistente sin introducir estilos personalizados.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **`exportproducts/script.tpl`**
    -   **Alcance:** Probablemente una plantilla genérica utilizada para incrustar pequeños fragmentos de JavaScript o variables de configuración directamente en el HTML, posiblemente enganchada a `displayHeader` o `displayBackOfficeHeader` si necesita ejecutarse en páginas específicas. Dado que no hay archivos JS, esto podría contener JS en línea para la validación de formularios o el comportamiento dinámico.
-   **`exportproducts/views/templates/admin/dashboard.tpl`**
    -   **Alcance:** Plantilla de administración.
    -   **Propósito:** Esta es la plantilla principal para el `AdminExportProductsController`. Renderiza todo el formulario de configuración de exportación, incluyendo los ajustes generales, las opciones de filtro y la extensa lista de campos de producto y combinación que el comerciante puede seleccionar para la exportación. También contiene el botón "Exportar".
-   **`exportproducts/views/templates/admin/form_header.tpl`**
    -   **Alcance:** Plantilla de administración.
    -   **Propósito:** Esta plantilla probablemente renderiza una sección de encabezado común para los formularios de configuración de administración, que podría incluir el título del módulo, la descripción y quizás algún texto introductorio o enlaces. Está diseñada para incluirse en la parte superior de otras plantillas de administración (como `dashboard.tpl`) para mayor coherencia.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El módulo no parece crear sus propias tablas de base de datos personalizadas.
    -   Almacena sus ajustes de configuración (por ejemplo, `ep_export_format`, `ep_export_active`, `ep_remember_settings`, `ep_export_categories_onlycats`, etc.) en la tabla estándar `ps_configuration` de PrestaShop. Estas claves tienen el prefijo `ep_` para "Export Products".
    -   Principalmente lee datos de las tablas centrales de PrestaShop: `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_manufacturer`, `ps_supplier`, `ps_image`, `ps_product_attribute`, `ps_product_attribute_combination`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`, etc.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayModuleRoutes` | Durante la generación de rutas para módulos. | Permite al módulo registrar URL amigables personalizadas para sus controladores de front-office (por ejemplo, `/feed` para `feed.php`). |
| `moduleRoutes` | Durante la generación de rutas para módulos. | Similar a `displayModuleRoutes`, utilizado para definir patrones de URL personalizados y asociarlos con controladores de módulos. |
| `displayBackOfficeHeader` | Renderiza contenido en la sección `<head>` del Back Office. | Potencialmente utilizado para incluir `script.tpl` para JS o CSS en línea, o para añadir metaetiquetas o variables JS específicas necesarias para la interfaz de administración. |
| `actionAdminControllerSetMedia` | Antes de que un Controlador de Administración renderice su página. | Se utiliza para registrar archivos CSS y JavaScript para el Back Office, asegurando que se carguen solo cuando sea necesario. (Aunque no se enumeran archivos JS/CSS, este hook sería el lugar estándar si estuvieran presentes). |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo **Export Products Pro**, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar el buen funcionamiento y la mejora continua de nuestros módulos.

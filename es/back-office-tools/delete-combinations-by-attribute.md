---
title: "Eliminar combinaciones por atributo - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Eliminar combinaciones por atributo' de MyPresta.eu."
sidebar:
  label: "Eliminar combinaciones por atributo - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Delete combinations by attribute en MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-combinations-by-attribute.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/delete-combinations-by-attribute/)
>
> ---


# Eliminar combinaciones por atributo

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No hay requisitos de alojamiento especiales más allá de una configuración estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo "Eliminar combinaciones por atributo". Aquí encontrará todas las herramientas para seleccionar y eliminar combinaciones.

#### **Sección superior: Actualizaciones e información del módulo**

Esta sección suele mostrar información sobre las actualizaciones y versiones del módulo de MyPresta.eu.

-   **Qué hace este ajuste:** Proporciona información sobre las actualizaciones disponibles para el módulo, asegurando que está ejecutando la última versión para correcciones de errores y nuevas características.
-   **Efecto de cambiar este ajuste:** Estos son campos informativos y no tienen ajustes directos que pueda cambiar. Simplemente muestran datos.
-   **Valor recomendado:** Mantenga su módulo actualizado a la última versión.
-   **Escenario / ejemplo de comerciante:** Ve una notificación de que hay una nueva versión `1.3.1` disponible. Entonces la descargaría de MyPresta.eu y actualizaría el módulo.

#### **Opciones de configuración principales**

1.  **Valor del atributo**

    -   **Qué hace este ajuste:** Este es el filtro principal. Le permite seleccionar un valor de atributo específico (por ejemplo, "Rojo", "Pequeño", "Algodón") que desea eliminar. El módulo buscará todas las combinaciones de productos que incluyan este valor de atributo seleccionado.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se selecciona un valor:* El módulo identificará todas las combinaciones en su tienda que utilizan este valor de atributo específico.
        -   *Cuando no se selecciona ningún valor:* No puede continuar con el proceso de eliminación ya que el módulo no sabe qué combinaciones eliminar.
    -   **Valor recomendado:** Seleccione el valor de atributo exacto para el que desea eliminar combinaciones.
    -   **Escenario / ejemplo de comerciante:** Ha descontinuado todos los productos de color "Naranja". Seleccionaría "Naranja" de este desplegable para eliminar todas las combinaciones con "Naranja" como uno de sus atributos.
2.  **Cantidad**

    -   **Qué hace este ajuste:** Esto le permite filtrar combinaciones en función de su cantidad de stock actual. Puede optar por eliminar combinaciones solo si su cantidad es inferior, igual o superior a un número especificado.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando "Qué hacer" se establece en "menos de" y "Cantidad" es 5:* Solo las combinaciones con una cantidad de stock de 4 o menos se considerarán para su eliminación.
        -   *Cuando "Qué hacer" se establece en "igual a" y "Cantidad" es 0:* Solo las combinaciones con exactamente 0 stock se considerarán.
    -   **Valor recomendado:** A menudo se usa con "igual a" y "0" para limpiar combinaciones agotadas.
    -   **Escenario / ejemplo de comerciante:** Desea eliminar todas las combinaciones de productos "Naranja" que actualmente están agotadas. Seleccionaría "Naranja" en "Valor del atributo", luego establecería "Qué hacer" en "igual a" y "Cantidad" en "0".
3.  **Qué hacer (con Cantidad)**

    -   **Qué hace este ajuste:** Este desplegable funciona junto con el campo "Cantidad" para definir la condición para el filtrado de stock. Las opciones suelen incluir "menos de", "igual a", "mayor que".
    -   **Efecto de cambiar este ajuste:** Modifica la lógica de comparación para el filtro "Cantidad".
    -   **Valor recomendado:** "igual a" es común para apuntar a artículos agotados.
    -   **Escenario / ejemplo de comerciante:** Para eliminar combinaciones que tienen muy poco stock, podría elegir "menos de" y establecer "Cantidad" en "3".
4.  **Lista de códigos de referencia**

    -   **Qué hace este ajuste:** Este campo le permite especificar una lista de códigos de referencia de productos (SKU) para incluir o excluir del proceso de eliminación. Esto es útil si solo desea afectar a un subconjunto de productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando "Campo de código" es "Referencia" y "Qué hacer" es "incluir":* Solo las combinaciones que pertenecen a productos con estos códigos de referencia específicos se verán afectadas.
        -   *Cuando "Campo de código" es "Referencia" y "Qué hacer" es "excluir":* Las combinaciones que pertenecen a productos con estos códigos de referencia específicos se omitirán.
    -   **Valor recomendado:** Utilice esto para reducir el alcance de la eliminación a productos específicos. Introduzca un código por línea.
    -   **Escenario / ejemplo de comerciante:** Solo desea eliminar combinaciones "Naranja" de productos con códigos de referencia `PROD-A`, `PROD-B` y `PROD-C`. Introduciría estos códigos, seleccionaría "Referencia" para "Campo de código" e "incluir" para "Qué hacer".
5.  **Campo de código**

    -   **Qué hace este ajuste:** Define a qué campo de identificador de producto se refiere la "Lista de códigos". Las opciones suelen ser "Referencia" (SKU) o "EAN13" (Código de barras).
    -   **Efecto de cambiar este ajuste:** Cambia cómo el módulo interpreta los códigos introducidos en "Lista de códigos".
    -   **Valor recomendado:** "Referencia" para SKUs internos, "EAN13" para códigos de barras.
    -   **Escenario / ejemplo de comerciante:** Si su lista contiene códigos de barras EAN13, seleccione "EAN13" aquí.
6.  **Lista de códigos (Qué hacer)**

    -   **Qué hace este ajuste:** Determina si la "Lista de códigos de referencia" (o códigos EAN) debe ser *incluida* en el proceso de eliminación (solo eliminar de estos productos) o *excluida* (eliminar de todos los productos EXCEPTO estos).
    -   **Efecto de cambiar este ajuste:** Controla el alcance de los productos afectados por la eliminación.
    -   **Valor recomendado:** "incluir" para eliminaciones específicas, "excluir" para eliminaciones amplias con excepciones.
    -   **Escenario / ejemplo de comerciante:** Desea eliminar combinaciones "Naranja" de todos los productos *excepto* su `BESTSELLER-01` más vendido. Introduciría `BESTSELLER-01` en la "Lista de códigos" y seleccionaría "excluir" aquí.
7.  **Producto**

    -   **Qué hace este ajuste:** Esto le permite seleccionar un producto específico por su nombre. Si se selecciona, la eliminación *solo* se aplicará a las combinaciones de este único producto, anulando cualquier otro filtro a nivel de producto.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se selecciona un producto:* El módulo solo procesará las combinaciones que pertenecen a este producto específico.
        -   *Cuando se deja vacío:* El módulo aplicará los criterios de eliminación a todos los productos de su tienda (sujeto a otros filtros como "Lista de códigos de referencia").
    -   **Valor recomendado:** Utilice esto para eliminaciones altamente específicas en un solo producto.
    -   **Escenario / ejemplo de comerciante:** Solo desea eliminar combinaciones "Naranja" de su producto "Vestido de verano". Seleccionaría "Vestido de verano" aquí.

#### **Botón de acción**

-   **Botón "Eliminar combinaciones seleccionadas"**
    -   **Qué hace este botón:** Este es el botón de acción que, al hacer clic, ejecuta el proceso de eliminación basado en todos los criterios que ha establecido anteriormente.
    -   **Efecto de hacer clic en este botón:** **¡Esta acción es irreversible!** Todas las combinaciones de productos que coincidan con su "Valor de atributo" seleccionado, los filtros de "Cantidad" y los filtros de "Producto" o "Referencia/EAN" se eliminarán permanentemente de su base de datos. Esto incluye su stock asociado, imágenes y precios específicos.
    -   **Valor recomendado:** **SIEMPRE realice una copia de seguridad completa de la base de datos antes de hacer clic en este botón.** Revise cuidadosamente todos sus ajustes.
    -   **Escenario / ejemplo de comerciante:** Después de seleccionar cuidadosamente "Color: Naranja", establecer "Cantidad: igual a 0" y confirmar su copia de seguridad, hace clic en este botón para eliminar todas las combinaciones naranjas agotadas.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | **Valor del atributo** | *Seleccionar valor específico* | Filtro principal: Elimina combinaciones que contienen este valor de atributo. |
| Configuración del módulo | **Cantidad** | *0 o número deseado* | Filtra combinaciones según su cantidad de stock. |
| Configuración del módulo | **Qué hacer (con Cantidad)** | *igual a* | Define la lógica de comparación para el filtro "Cantidad" (menos de, igual a, mayor que). |
| Configuración del módulo | **Lista de códigos de referencia** | *Vacío o códigos específicos* | Lista de códigos de referencia de producto (SKU) o EAN para incluir/excluir. Uno por línea. |
| Configuración del módulo | **Campo de código** | *Referencia* | Especifica si la "Lista de códigos" se refiere a "Referencia" o "EAN13". |
| Configuración del módulo | **Lista de códigos (Qué hacer)** | *incluir* | Determina si los códigos listados se incluyen o excluyen de la eliminación. |
| Configuración del módulo | **Producto** | *Vacío o nombre de producto específico* | Dirige la eliminación a un solo producto, anulando otros filtros de producto. |
| Configuración del módulo | **Eliminar combinaciones seleccionadas** | **¡Haga clic con precaución!** | Ejecuta la eliminación irreversible de combinaciones según todos los criterios. **¡Primero haga una copia de seguridad!** |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Hice clic en "Eliminar" pero no pasó nada, o no se eliminaron todas las combinaciones.**
R:

-   **Verifique sus filtros:** Vuelva a verificar todos sus ajustes: "Valor del atributo", condiciones de "Cantidad", "Lista de códigos" (incluir/excluir) y selección de "Producto". Incluso una pequeña discrepancia puede evitar que las combinaciones sean eliminadas.
-   **Borrar caché:** A veces, la caché de PrestaShop puede causar problemas de visualización. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché".
-   **Conflictos de módulos:** Otro módulo podría estar interfiriendo. Intente deshabilitar otros módulos uno por uno (especialmente los relacionados con la gestión de productos o combinaciones) para ver si el problema se resuelve.

**P: Eliminé accidentalmente combinaciones que no quería. ¿Puedo recuperarlas?**
R: **No, no directamente a través del módulo.** Por eso una copia de seguridad es fundamental. Si tiene una copia de seguridad reciente de la base de datos, puede restaurar su tienda al estado en que se encontraba antes de la eliminación. Si no tiene una copia de seguridad, tendrá que recrear manualmente las combinaciones.

**P: El valor del atributo que quiero eliminar no aparece en el desplegable.**
R:

-   **Verifique si existe:** Asegúrese de que el valor del atributo realmente existe en su catálogo de PrestaShop y está asignado a al menos un producto. Vaya a **Catálogo > Atributos y características** para verificar.
-   **Idioma:** Asegúrese de que está viendo el Back Office en el idioma correcto si el nombre del valor del atributo depende del idioma.

**P: ¿Puedo eliminar combinaciones basándome en características en lugar de atributos?**
R: No, este módulo está diseñado específicamente para funcionar con **atributos y valores de atributo**. Las características son un concepto diferente en PrestaShop y no son compatibles con este módulo para su eliminación.

**P: ¿La eliminación de combinaciones también eliminará las imágenes o precios específicos asociados?**
R: Sí, cuando se elimina una combinación, todos los datos directamente vinculados a esa combinación específica (como su imagen única, reglas de precios específicas para esa combinación y su cantidad de stock) también se eliminarán. La imagen principal del producto y los precios específicos generales del producto permanecerán.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura

El módulo `delcombs` es un módulo de PrestaShop sencillo centrado principalmente en la funcionalidad del Back Office. Se adhiere a la estructura del módulo de PrestaShop, utilizando la clase `Module` para la instalación, desinstalación y configuración. Su lógica central reside dentro del método `getContent()` del archivo principal del módulo, donde maneja el envío de formularios, la validación de datos y la ejecución de operaciones de base de datos para eliminar combinaciones de productos. No introduce controladores de front-office personalizados ni ObjectModels complejos, sino que se basa en consultas directas a la base de datos y en las clases `Product` y `Combination` del núcleo de PrestaShop para la manipulación de datos.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. Toda la funcionalidad está confinada al Back Office.
-   **Controladores de administración de Back-Office**: Ninguno. La lógica de configuración y procesamiento del módulo se maneja dentro del método `getContent()` de la clase principal del módulo, que se renderiza como parte de la página de configuración estándar del módulo.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define ninguna clase personalizada en el directorio `classes/`. Interactúa directamente con las clases `Product` y `Combination` del núcleo de PrestaShop y realiza consultas directas a la base de datos para una mayor eficiencia en las operaciones de eliminación masiva.

### 4.4 Activos de JavaScript (`views/js/`)

-   `delcombs/views/js/delcombs-admin.js`
    -   **Alcance:** Back-office (página de configuración del módulo).
    -   **Propósito:** Este script probablemente maneja el comportamiento dinámico en el formulario de configuración del módulo. Esto podría incluir:
        -   Llamadas AJAX para buscar productos o atributos (por ejemplo, para el campo de selección de "Producto").
        -   Visualización condicional de campos de formulario basados en las selecciones del usuario (por ejemplo, mostrar/ocultar filtros de cantidad).
        -   Validación de entrada antes del envío del formulario.
        -   Cuadros de diálogo de confirmación antes de ejecutar la acción de eliminación.
        -   Interacciones con la `searchTool` (probablemente un componente de búsqueda personalizado para productos/atributos).

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `delcombs/views/css/delcombs-admin.css`
    -   **Alcance:** Back-office (página de configuración del módulo).
    -   **Propósito:** Proporciona estilos para los elementos del formulario de configuración del módulo, asegurando una interfaz consistente y fácil de usar dentro del Back Office de PrestaShop.
    -   **Selectores de clase CSS clave:** Probablemente apunta a IDs o clases específicas dentro de la salida `getContent()` del módulo, como grupos de formularios, campos de entrada y potencialmente el componente `searchTool`. Los desarrolladores pueden anular estos estilos en sus temas de administración personalizados o agregando CSS de mayor especificidad.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   `delcombs/lib/searchTool/views/scripts.tpl`
    -   **Alcance:** Back-office.
    -   **Propósito:** Esta plantilla probablemente contiene código JavaScript o variables Smarty necesarias para un componente de herramienta de búsqueda genérico utilizado dentro del módulo. Podría inicializar campos de búsqueda, definir puntos finales AJAX para consultas de búsqueda o configurar el manejo de datos del lado del cliente para los resultados de búsqueda. Probablemente está incluida por la plantilla de configuración principal.
-   `delcombs/views/templates/admin/tabs.tpl`
    -   **Alcance:** Back-office (página de configuración del módulo).
    -   **Propósito:** Esta es la plantilla principal de Smarty renderizada por el método `getContent()` del módulo `delcombs`. Estructura todo el formulario de configuración, incluyendo:
        -   Los diversos campos de entrada (desplegables para atributos, áreas de texto para códigos, entradas de cantidad).
        -   El botón "Eliminar combinaciones seleccionadas".
        -   Cualquier mensaje o advertencia informativa.
        -   Probablemente incluye `scripts.tpl` para la funcionalidad de búsqueda.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   El módulo no crea ninguna tabla de base de datos personalizada.
    -   Opera directamente en las tablas principales de PrestaShop, principalmente:
        -   `ps_product_attribute` (tabla principal de combinaciones)
        -   `ps_product_attribute_combination` (vincula combinaciones a valores de atributo)
        -   `ps_product_attribute_shop` (datos de combinación específicos de la tienda)
        -   `ps_stock_available` (stock para combinaciones)
        -   `ps_specific_price` (precios específicos para combinaciones)
        -   `ps_image` (imágenes vinculadas a combinaciones)
        -   `ps_product` (para filtrar por ID de producto, referencia, EAN)
        -   `ps_attribute_lang`, `ps_attribute_group_lang` (para mostrar nombres de atributos en los desplegables)
    -   Los ajustes de configuración se almacenan en `ps_configuration` con claves como `delcombs_attribute`, `delcombs_product`, `delcombs_qty_wtd`, `delcombs_qty`, `delcombs_ref_codes`, `delcombs_ref_type`, `delcombs_ean_codes`, `delcombs_ean_type`, `delcombs_ean_field`, `delcombs_product_mode`.
-   **Tabla de Hooks registrados**:
    El módulo no registra ningún hook de visualización de front-office o back-office. Su funcionalidad está completamente autocontenida dentro de su página de configuración.
    Podría usar hooks de acción internamente (por ejemplo, `actionProductUpdate` o `actionAttributeCombinationSave`) para borrar la caché o reaccionar a los cambios, pero estos no se enumeran explícitamente como hooks registrados para la interacción externa del módulo.
    La lógica central del módulo se activa mediante el envío del formulario dentro de su método `getContent()`, no por un hook estándar de PrestaShop.

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y descargar las últimas versiones del módulo "Eliminar combinaciones por atributo", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.

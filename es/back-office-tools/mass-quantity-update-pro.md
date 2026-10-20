---
title: "Actualización masiva de cantidad pro - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Actualización masiva de cantidad pro' de MyPresta.eu."
sidebar:
  label: "Actualización masiva de cantidad pro - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Mass quantity update pro en MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-quantity-update-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/mass-quantity-update-pro/)
>
> ---


# Actualización masiva de cantidad pro

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

El módulo "Actualización masiva de cantidad pro" proporciona una única e intuitiva pantalla de configuración en el back office de PrestaShop donde se definen los productos a actualizar y los cambios de cantidad a aplicar.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Para acceder a la configuración del módulo, navegue a **Módulos > Gestor de módulos**, busque "Actualización masiva de cantidad pro" y haga clic en el botón "Configurar".

La página de configuración se divide en dos secciones principales: **Productos objetivo** y **¿Qué hacer?**.

#### 2.1.1 Productos objetivo

Esta sección le permite definir *qué* productos o combinaciones de productos se verán afectados por la actualización de cantidad. Puede seleccionar productos basándose en varios criterios.

-   **Qué hace este ajuste:** Esta sección define el alcance de su actualización de cantidad. Usted elige el grupo específico de productos que tendrán sus cantidades modificadas.
-   **Efecto de cambiar este ajuste:** Solo los productos que coincidan con los criterios seleccionados serán considerados para la actualización de cantidad. Si no se selecciona ningún criterio, no se apuntará a ningún producto.
-   **Valor recomendado:** Seleccione uno o más criterios que definan con precisión los productos que desea modificar.

**Criterios disponibles:**

1.  **Productos de categorías:**

    -   **Qué hace este ajuste:** Le permite seleccionar una o más categorías de productos específicas. Todos los productos (y sus combinaciones) que pertenezcan a estas categorías serán objetivo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está seleccionado:* Se incluirán los productos dentro de las categorías elegidas.
        -   *Cuando no está seleccionado:* Los productos no se filtran por categoría.
    -   **Valor recomendado:** Seleccione esto si necesita actualizar el stock de una línea de productos o departamento completo.
    -   **Escenario / ejemplo de comerciante:** Ha recibido un nuevo envío para todos los productos de su categoría "Colección de Verano". Puede seleccionar esta categoría para actualizar su stock.
2.  **Productos por marca:**

    -   **Qué hace este ajuste:** Le permite seleccionar una o más marcas de productos (fabricantes) específicas. Todos los productos (y sus combinaciones) asociados con estas marcas serán objetivo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está seleccionado:* Se incluirán los productos de las marcas elegidas.
        -   *Cuando no está seleccionado:* Los productos no se filtran por marca.
    -   **Valor recomendado:** Seleccione esto si necesita actualizar el stock de productos de un proveedor o marca en particular.
    -   **Escenario / ejemplo de comerciante:** Su proveedor "Fashionista Inc." ha entregado nuevo stock. Selecciona "Fashionista Inc." para actualizar todos sus productos.
3.  **Productos por características:**

    -   **Qué hace este ajuste:** Le permite seleccionar productos basándose en sus características asignadas (por ejemplo, "Color: Rojo", "Material: Algodón"). Puede elegir una característica y luego valores específicos para esa característica.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está seleccionado:* Solo se incluirán los productos que posean la característica y el valor especificados.
        -   *Cuando no está seleccionado:* Los productos no se filtran por características.
    -   **Valor recomendado:** Útil para actualizaciones muy específicas basadas en las características del producto.
    -   **Escenario / ejemplo de comerciante:** Desea actualizar el stock de todas las camisetas de "Algodón Orgánico". Selecciona "Material" como característica y "Algodón Orgánico" como valor.
4.  **Productos por atributos:**

    -   **Qué hace este ajuste:** Le permite seleccionar productos basándose en sus atributos (por ejemplo, "Talla: M", "Color: Azul"). Esto es particularmente útil para combinaciones de productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está seleccionado:* Solo se incluirán las combinaciones de productos con el atributo y el valor especificados.
        -   *Cuando no está seleccionado:* Los productos no se filtran por atributos.
    -   **Valor recomendado:** Esencial para gestionar el stock de variaciones de productos específicas.
    -   **Escenario / ejemplo de comerciante:** Ha recibido una nueva entrega de camisetas "Talla L". Selecciona "Talla" como atributo y "L" como valor para actualizar solo esas combinaciones.
5.  **Productos por asociaciones de reglas de impuestos:**

    -   **Qué hace este ajuste:** Le permite seleccionar productos basándose en el grupo de reglas de impuestos aplicado a ellos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está seleccionado:* Solo se incluirán los productos asociados con el grupo de reglas de impuestos elegido.
        -   *Cuando no está seleccionado:* Los productos no se filtran por regla de impuestos.
    -   **Valor recomendado:** Útil para tiendas con estructuras fiscales complejas o cuando las actualizaciones de stock están vinculadas a inventarios relacionados con impuestos.
    -   **Escenario / ejemplo de comerciante:** Necesita ajustar el stock de todos los productos sujetos a una regla de impuestos específica de "Derechos de importación".
6.  **Productos específicos:**

    -   **Qué hace este ajuste:** Proporciona un cuadro de búsqueda con autocompletado para seleccionar manualmente productos individuales por nombre.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se añaden productos:* Solo los productos seleccionados explícitamente (y sus combinaciones) serán objetivo.
        -   *Cuando está vacío:* No se apuntan productos específicos de esta manera.
    -   **Valor recomendado:** Utilice esto para actualizaciones muy precisas en un pequeño conjunto de productos seleccionados manualmente.
    -   **Escenario / ejemplo de comerciante:** Necesita actualizar el stock de "Producto A", "Producto B" y "Producto C" que no están relacionados por categoría o marca.

#### 2.1.2 ¿Qué hacer?

Esta sección define *cómo* se cambiarán las cantidades de los productos objetivo.

-   **Qué hace este ajuste:** Esta sección especifica el tipo de modificación de cantidad (aumentar, disminuir o establecer un valor fijo) y la cantidad del cambio.
-   **Efecto de cambiar este ajuste:** La operación seleccionada se aplicará a las cantidades de todos los productos definidos en la sección "Productos objetivo".
-   **Valor recomendado:** Elija la operación que refleje con precisión su ajuste de inventario.

**Operaciones disponibles:**

1.  **Aumentar cantidad en:**

    -   **Qué hace este ajuste:** Añade un número especificado a la cantidad actual de cada producto/combinación objetivo.
    -   **Efecto de cambiar este ajuste:** El nivel de stock de cada artículo objetivo aumentará en la cantidad introducida.
    -   **Valor recomendado:** Utilice cuando llegue nuevo stock. Introduzca un número entero positivo (por ejemplo, `10`).
    -   **Escenario / ejemplo de comerciante:** Ha recibido 50 unidades de un producto. Selecciona "Aumentar cantidad en" e introduce `50`.
2.  **Disminuir cantidad en:**

    -   **Qué hace este ajuste:** Resta un número especificado de la cantidad actual de cada producto/combinación objetivo.
    -   **Efecto de cambiar este ajuste:** El nivel de stock de cada artículo objetivo disminuirá en la cantidad introducida.
    -   **Valor recomendado:** Utilice cuando el stock necesite ser reducido debido a daños, devoluciones o uso interno. Introduzca un número entero positivo (por ejemplo, `5`).
    -   **Escenario / ejemplo de comerciante:** 5 artículos fueron dañados en el almacén. Selecciona "Disminuir cantidad en" e introduce `5`.
3.  **Establecer cantidad en:**

    -   **Qué hace este ajuste:** Cambia la cantidad actual de cada producto/combinación objetivo a un número fijo específico.
    -   **Efecto de cambiar este ajuste:** El nivel de stock de cada artículo objetivo se convertirá exactamente en la cantidad introducida, independientemente de su cantidad anterior.
    -   **Valor recomendado:** Utilice cuando necesite sincronizar el stock con un sistema externo o corregir un recuento de stock absoluto. Introduzca un número entero no negativo (por ejemplo, `100`).
    -   **Escenario / ejemplo de comerciante:** Después de un recuento de inventario completo, sabe que tiene exactamente 100 unidades de un producto. Selecciona "Establecer cantidad en" e introduce `100`.

**Nota importante:** Después de definir tanto "Productos objetivo" como "¿Qué hacer?", debe hacer clic en el botón **"Actualizar cantidades"** para aplicar los cambios. No hay un botón de "deshacer", así que siempre revise sus selecciones antes de confirmar.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | **Productos objetivo** | | Define qué productos/combinaciones se verán afectados. |
| | Productos de categorías | Seleccionar según sea necesario | Apunta a todos los productos dentro de las categorías elegidas. |
| | Productos por marca | Seleccionar según sea necesario | Apunta a todos los productos de las marcas elegidas. |
| | Productos por características | Seleccionar según sea necesario | Apunta a productos con características/valores específicos. |
| | Productos por atributos | Seleccionar según sea necesario | Apunta a combinaciones de productos con atributos/valores específicos. |
| | Productos por asociaciones de reglas de impuestos | Seleccionar según sea necesario | Apunta a productos asociados con las reglas de impuestos elegidas. |
| | Productos específicos | Seleccionar según sea necesario | Apunta a productos seleccionados individualmente. |
| | **¿Qué hacer?** | | Define cómo se cambiarán las cantidades. |
| | Aumentar cantidad en | Introducir entero positivo | Añade la cantidad especificada al stock actual. |
| | Disminuir cantidad en | Introducir entero positivo | Resta la cantidad especificada del stock actual. |
| | Establecer cantidad en | Introducir entero no negativo | Establece el stock en una cantidad exacta y especificada. |
| | **Botón Actualizar cantidades** | Hacer clic para aplicar | Ejecuta los cambios de cantidad definidos. |

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Actualicé las cantidades, pero mi tienda sigue mostrando los números antiguos. ¿Qué pasa?**
**R1:** Esto suele ser un problema de caché. PrestaShop utiliza la caché para acelerar su tienda.

-   **Solución:** Vaya a **Parámetros avanzados > Rendimiento** en su back office de PrestaShop. Haga clic en "Borrar caché" (o "Borrar caché de Smarty" / "Borrar caché" según su versión de PrestaShop). Esto debería forzar a su tienda a mostrar las cantidades actualizadas.

**P2: Cometí un error y actualicé productos/cantidades incorrectos. ¿Puedo deshacerlo?**
**R2:** El módulo no tiene un botón de "deshacer". Por eso es crucial revisar sus selecciones antes de hacer clic en "Actualizar cantidades".

-   **Solución:** Si tiene una copia de seguridad reciente de su base de datos, puede restaurarla (aunque esto podría revertir otros cambios recientes). De lo contrario, deberá corregir manualmente las cantidades de los productos afectados, o usar el módulo nuevamente con la configuración correcta para reajustarlas. Por ejemplo, si accidentalmente aumentó en 10, puede disminuir en 10.

**P3: El módulo no encuentra productos cuando escribo en el cuadro de búsqueda de "Productos específicos".**
**R3:** Asegúrese de estar escribiendo el nombre completo o parcial de un producto existente en su tienda. La función de autocompletado depende de JavaScript.

-   **Solución:**
    1.  Revise la consola de su navegador en busca de errores de JavaScript (tecla F12, luego pestaña "Consola").
    2.  Intente borrar la caché de su navegador.
    3.  Asegúrese de que su tienda PrestaShop esté ejecutándose en una versión de PHP compatible (consulte la sección 3).
    4.  Si el problema persiste, póngase en contacto con el soporte de MyPresta.eu.

**Q4: ¿Puedo actualizar cantidades para productos que tienen combinaciones (atributos)?**
**R4:** ¡Sí, absolutamente! El módulo está diseñado para manejar combinaciones de productos. Cuando selecciona productos por categoría, marca, característica o producto específico, aplicará el cambio de cantidad a todas las combinaciones asociadas de esos productos. Si utiliza "Productos por atributos", incluso puede apuntar a combinaciones específicas directamente.

**Q5: El módulo parece lento al actualizar un número muy grande de productos.**
**R5:** Actualizar miles de productos puede consumir muchos recursos.

-   **Solución:**
    1.  Asegúrese de que su servidor cumpla con las especificaciones recomendadas de PrestaShop.
    2.  Aumente los límites de tiempo de ejecución de PHP (`max_execution_time`) y los límites de memoria (`memory_limit`) en su archivo `php.ini` (consulte a su proveedor de alojamiento o webmaster).
    3.  Si es posible, divida las actualizaciones muy grandes en lotes más pequeños (por ejemplo, actualice una categoría a la vez en lugar de todas las categorías).

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Actualización masiva de cantidad pro".

### 4.1 Descripción general de la arquitectura

El módulo `MassQtyPro` sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para su funcionalidad principal y el método `getContent()` para su única interfaz de configuración de back-office. Integra una herramienta de búsqueda personalizada para la selección de productos, utilizando AJAX para la funcionalidad de autocompletado. El módulo interactúa directamente con las clases `Product` y `StockAvailable` de PrestaShop para realizar actualizaciones de cantidad.

### 4.2 Controladores (`controllers/`)

El módulo no utiliza controladores personalizados de front-office o back-office. Toda la lógica de configuración y procesamiento para el back-office se maneja dentro del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define ninguna clase `ObjectModel` personalizada ni clases dedicadas dentro de un directorio `classes/`. Toda la lógica principal reside dentro del archivo principal `massqtypro.php`.

### 4.4 Activos de JavaScript (`views/js/`)

-   **`massqtypro/lib/searchTool/views/js/autocomplete.js`**
    -   **Alcance:** Back-office (utilizado en la página de configuración del módulo).
    -   **Descripción:** Este script probablemente implementa o integra una funcionalidad genérica de autocompletado. Escucha la entrada del usuario en los campos de texto (específicamente para la búsqueda de productos) y envía solicitudes AJAX para obtener nombres de productos coincidentes. Luego muestra estas sugerencias en una lista desplegable, permitiendo al usuario seleccionar productos. Gestiona la visualización y selección de los resultados de autocompletado.
-   **`massqtypro/views/js/jquery.autocomplete.js`**
    -   **Alcance:** Back-office (utilizado en la página de configuración del módulo).
    -   **Descripción:** Este parece ser un plugin de jQuery para la funcionalidad de autocompletado. Proporciona el marco principal para el cuadro de búsqueda de productos en la página de configuración del módulo. Maneja las llamadas AJAX al servidor (probablemente al método `getContent()` o a un hook específico que proporciona datos de productos), procesa la respuesta JSON y renderiza las sugerencias. También gestiona la selección de un elemento de la lista y la población del campo de entrada o un campo oculto con el ID del producto seleccionado.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`massqtypro/lib/searchTool/views/css/autocomplete.css`**
    -   **Alcance:** Back-office (estilo para la página de configuración del módulo).
    -   **Descripción:** Esta hoja de estilo proporciona la presentación visual para el cuadro de búsqueda de autocompletado y su lista de sugerencias. Define estilos para el campo de entrada, el contenedor desplegable, los elementos de sugerencia individuales y, potencialmente, los estados de `:hover`/`:active` para una mejor interacción del usuario. Los desarrolladores pueden anular estos estilos en su tema de administración personalizado o añadiendo reglas CSS específicas para apuntar a los elementos del módulo.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty para renderizar su formulario de configuración de back-office.

-   **`massqtypro/lib/searchTool/views/scripts.tpl`**
    -   **Alcance:** Back-office (incluido en la página de configuración del módulo).
    -   **Descripción:** Esta plantilla probablemente incluye los archivos JavaScript y CSS necesarios para la herramienta de búsqueda de autocompletado. También podría contener JavaScript en línea para inicializar el plugin de autocompletado en campos de entrada específicos, pasando opciones de configuración y definiendo funciones de callback para cuando se selecciona un producto.
-   **`massqtypro/views/templates/admin/target_products.tpl`**
    -   **Alcance:** Back-office (parte del formulario de configuración del módulo).
    -   **Descripción:** Esta plantilla renderiza la sección "Productos objetivo" de la página de configuración del módulo. Contiene el HTML para todos los criterios de selección de productos: desplegables de categorías, desplegables de marcas, selectores de características/atributos, selectores de reglas de impuestos y el campo de entrada de autocompletado de productos específicos. Utiliza ayudantes de formulario estándar de PrestaShop y potencialmente HTML personalizado para los elementos de selección dinámica.
-   **`massqtypro/views/templates/admin/wtd.tpl`**
    -   **Alcance:** Back-office (parte del formulario de configuración del módulo).
    -   **Descripción:** Esta plantilla renderiza la sección "¿Qué hacer?" de la página de configuración del módulo. Contiene el HTML para las operaciones de actualización de cantidad: botones de radio para "Aumentar", "Disminuir" o "Establecer en", y el campo de entrada correspondiente para el valor de la cantidad. También incluye el botón de envío "Actualizar cantidades".
-   **`massqtypro/views/templates/hook/form.tpl`**
    -   **Alcance:** Back-office (formulario de configuración principal).
    -   **Descripción:** Esta es la plantilla principal para la página de configuración del módulo. Probablemente envuelve las plantillas `target_products.tpl` y `wtd.tpl`, combinándolas en el formulario de configuración completo. También manejaría el envío general del formulario y mostraría cualquier mensaje de éxito o error.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**: El módulo no crea ninguna tabla de base de datos personalizada. Interactúa principalmente con las tablas existentes de PrestaShop, en particular `ps_product`, `ps_product_attribute`, `ps_stock_available`, `ps_category_product`, `ps_manufacturer`, `ps_feature_product`, `ps_product_attribute_combination` y `ps_tax_rule_group_product`. Los ajustes de configuración se almacenan en `ps_configuration`.
-   **Tabla de Hooks registrados**:
    La funcionalidad principal del módulo se ejecuta a través de su método `getContent()` en el back-office. No se registra explícitamente en hooks de front-office para fines de visualización. Sin embargo, el módulo podría usar internamente hooks para acciones administrativas o recuperación de datos.

    | Nombre del Hook | Momento de ejecución | Propósito técnico |
    | --- | --- | --- |
    | `displayBackOfficeHeader` | Se renderiza en la sección `<head>` del Back Office. | Potencialmente utilizado para cargar CSS/JS específicos del módulo para la página de configuración, aunque a menudo se maneja directamente en `getContent()`. |
    | `actionProductUpdate` | Después de que se actualiza un producto. | Podría usarse para el registro interno o para activar acciones relacionadas, aunque no se indica explícitamente en las características. |
    | `actionUpdateQuantity` | Después de que se actualiza la cantidad de un producto. | Podría usarse para el registro interno o para activar acciones relacionadas, aunque no se indica explícitamente en las características. |

    La lógica central del módulo para las actualizaciones de cantidad manipula directamente las entradas de `StockAvailable`, lo que internamente activa los mecanismos de actualización de stock de PrestaShop.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte técnico oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con el módulo "Actualización masiva de cantidad pro".

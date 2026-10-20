---
title: "Buscar y reemplazar texto en campos de producto - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Buscar y reemplazar texto en campos de producto' de MyPresta.eu."
sidebar:
  label: "Buscar y reemplazar texto en campos de producto"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Search and replace text in product fields en MyPresta.eu](https://mypresta.eu/modules/administration-tools/search-and-replace-text-in-product-fields.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/search-and-replace-text-in-product-fields/)
>
> ---


# Buscar y reemplazar texto en campos de producto

## 1. Requisitos y compatibilidad
-   **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilidad con PHP**: PHP 7.1 - 8.5
-   **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones especiales del servidor más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

El módulo "Buscar y reemplazar texto en campos de producto" no tiene una página de configuración tradicional con ajustes como interruptores o campos de entrada. En su lugar, se integra directamente en la lista de productos de PrestaShop, proporcionando una nueva acción para realizar operaciones de búsqueda y reemplazo.

### 2.1 Acceso a la herramienta de búsqueda y reemplazo

La funcionalidad del módulo se accede directamente desde su lista de productos de PrestaShop:

1.  **Navegue a la lista de productos:**
    -   En su Back Office de PrestaShop, vaya a **Catálogo > Productos**.
2.  **Seleccione productos:**
    -   Puede seleccionar uno o más productos específicos marcando las casillas junto a ellos, o puede optar por aplicar la búsqueda y reemplazo a *todos* los productos actualmente mostrados en la lista (por ejemplo, si ha filtrado la lista).
3.  **Acceda al menú de acciones masivas:**
    -   Después de seleccionar productos, aparecerá un menú desplegable de "Acciones masivas" (normalmente en la parte superior o inferior de la lista de productos).
4.  **Seleccione "Buscar y reemplazar texto en campos de producto":**
    -   Haga clic en el menú desplegable "Acciones masivas" y seleccione la opción etiquetada **"Buscar y reemplazar texto en campos de producto"**.

### 2.2 La interfaz de búsqueda y reemplazo

Una vez que seleccione la acción "Buscar y reemplazar texto en campos de producto", aparecerá una ventana modal o una interfaz dedicada. Aquí es donde define su operación de búsqueda y reemplazo.

**Campos disponibles para buscar y reemplazar:**
El módulo le permite apuntar a varios campos de texto asociados con sus productos. Estos suelen incluir:
-   **Nombre del producto:** El título principal de su producto.
-   **Descripción corta:** El breve resumen que a menudo se muestra cerca de la imagen del producto.
-   **Descripción:** La descripción completa y detallada del producto.
-   **Meta título:** El título que se muestra en las pestañas del navegador y en los resultados de los motores de búsqueda.
-   **Meta descripción:** El breve resumen que se muestra debajo del título en los resultados de los motores de búsqueda.
-   **URL amigable:** La parte de la dirección web del producto optimizada para SEO.
-   **Etiquetas:** Palabras clave asociadas con el producto.
-   **Características:** Valores de características de producto personalizadas (por ejemplo, "Color: Rojo" - podría reemplazar "Rojo" por "Carmesí").
-   **Valores de atributo:** Valores para atributos de producto (por ejemplo, "Talla: S" - podría reemplazar "S" por "Pequeña").
-   **Campos de personalización:** Campos de texto que los clientes pueden rellenar para la personalización del producto.

**Configuraciones clave dentro de la interfaz:**

-   **Buscar:**
    -   **Qué hace esta configuración:** Esta es la frase de texto exacta que desea encontrar dentro de los campos de producto seleccionados.
    -   **Efecto de cambiar esta configuración:** El módulo buscará esta cadena precisa de caracteres. Es sensible a mayúsculas y minúsculas por defecto, a menos que se proporcione una opción "Insensible a mayúsculas y minúsculas" (verifique la interfaz para esto).
    -   **Valor recomendado:** Ingrese el texto exacto que desea encontrar.
    -   **Escenario / ejemplo de comerciante:** Si desea cambiar "nombre de marca antiguo" a "nombre de marca nuevo", ingresaría "nombre de marca antiguo" aquí.

-   **Reemplazar con:**
    -   **Qué hace esta configuración:** Esta es la nueva frase de texto que reemplazará cada instancia del texto "Buscar" encontrado.
    -   **Efecto de cambiar esta configuración:** Todas las ocurrencias del texto "Buscar" se actualizarán a este nuevo texto. Si se deja vacío, el texto "Buscar" se eliminará.
    -   **Valor recomendado:** Ingrese el nuevo texto que desea usar.
    -   **Escenario / ejemplo de comerciante:** Siguiendo el ejemplo anterior, ingresaría "nombre de marca nuevo" aquí.

-   **Seleccionar campos para buscar:**
    -   **Qué hace esta configuración:** Esta es una lista de casillas de verificación o un menú desplegable de selección múltiple donde elige qué campos de texto de producto específicos (por ejemplo, "Descripción", "Descripción corta", "Meta título") debe procesar el módulo.
    -   **Efecto de cambiar esta configuración:** Solo los campos seleccionados serán escaneados y modificados. Los campos no seleccionados permanecerán intactos.
    -   **Valor recomendado:** Seleccione solo los campos relevantes para su tarea actual para evitar cambios no deseados.
    -   **Escenario / ejemplo de comerciante:** Si solo desea actualizar la descripción principal del producto, marque solo "Descripción". Si está actualizando un nombre de marca en todas partes, podría marcar "Nombre del producto", "Descripción corta", "Descripción", "Meta título" y "Meta descripción".

-   **Aplicar a productos seleccionados / Aplicar a todos los productos filtrados:**
    -   **Qué hace esta configuración:** Esto confirma si la operación se aplica solo a los productos que marcó manualmente en la lista, o a todos los productos actualmente visibles en la lista de productos (que podría ser un subconjunto filtrado).
    -   **Efecto de cambiar esta configuración:** Determina el alcance de la operación. Tenga mucho cuidado con "todos los productos filtrados" para asegurarse de que sus filtros se apliquen correctamente.
    -   **Valor recomendado:** Siempre verifique dos veces su selección de productos antes de continuar.
    -   **Escenario / ejemplo de comerciante:** Si filtró la lista de productos para mostrar solo productos de una categoría específica, y luego elige "Aplicar a todos los productos filtrados", los cambios solo afectarán a los productos de esa categoría.

-   **Sensible a mayúsculas y minúsculas / Insensible a mayúsculas y minúsculas (si está disponible):**
    -   **Qué hace esta configuración:** Determina si la búsqueda debe distinguir entre letras mayúsculas y minúsculas.
    -   **Efecto de cambiar esta configuración:**
        -   *Sensible a mayúsculas y minúsculas:* "Apple" no coincidirá con "apple".
        -   *Insensible a mayúsculas y minúsculas:* "Apple" coincidirá con "apple", "APPLE", "Apple", etc.
    -   **Valor recomendado:** Use insensible a mayúsculas y minúsculas para reemplazos amplios (por ejemplo, corregir un error tipográfico común que podría aparecer en diferentes casos). Use sensible a mayúsculas y minúsculas para reemplazos precisos donde el uso de mayúsculas importa.
    -   **Escenario / ejemplo de comerciante:** Si desea reemplazar "ProductoX" por "Producto Y", pero algunas descripciones podrían tener "productoX", usar insensible a mayúsculas y minúsculas capturará ambos.

-   **Vista previa / Ejecución de prueba (si está disponible):**
    -   **Qué hace esta configuración:** Algunas herramientas avanzadas de búsqueda y reemplazo ofrecen un modo de "vista previa" o "ejecución de prueba" que le muestra qué cambios *se harían* sin guardarlos realmente.
    -   **Efecto de cambiar esta configuración:** Le permite revisar el impacto de su operación antes de confirmarla, evitando la pérdida accidental de datos.
    -   **Valor recomendado:** Siempre use una vista previa si está disponible, especialmente para operaciones a gran escala.
    -   **Escenario / ejemplo de comerciante:** Antes de reemplazar "antiguo" por "nuevo" en 1000 productos, una vista previa le mostraría exactamente qué productos y campos se verían afectados.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Lista de productos (Acciones masivas) | Buscar | Definido por el usuario | La cadena de texto exacta a encontrar. Sensible a mayúsculas y minúsculas a menos que se especifique. |
| Lista de productos (Acciones masivas) | Reemplazar con | Definido por el usuario | La cadena de texto para reemplazar el texto 'Buscar'. Vacío elimina el texto. |
| Lista de productos (Acciones masivas) | Seleccionar campos para buscar | Definido por el usuario | Casillas de verificación para seleccionar qué campos de producto (descripción, nombre, meta, etc.) modificar. |
| Lista de productos (Acciones masivas) | Aplicar a productos seleccionados / todos los productos filtrados | Definido por el usuario | Define el alcance de la operación: solo productos marcados o todos los productos actualmente filtrados. |
| Lista de productos (Acciones masivas) | Sensible a mayúsculas y minúsculas / Insensible a mayúsculas y minúsculas | (Ver interfaz del módulo) | Determina si la búsqueda distingue entre letras mayúsculas y minúsculas. |
| Lista de productos (Acciones masivas) | Vista previa / Ejecución de prueba | (Si está disponible, usar siempre) | Muestra los posibles cambios antes de aplicarlos, evitando errores. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: Ejecuté la búsqueda y reemplazo, pero no veo los cambios en mi sitio web.**
R: PrestaShop utiliza el almacenamiento en caché para acelerar su tienda. Después de realizar cambios en el back office, a menudo necesita borrar la caché para que aparezcan en el front office.
    -   Vaya a **Parámetros avanzados > Rendimiento**.
    -   Haga clic en "Borrar caché" en la esquina superior derecha.
    -   Si utiliza un módulo de caché de terceros o CDN, borre también sus cachés.

**P: El módulo no aparece en el menú "Acciones masivas" en la lista de productos.**
R:
    1.  **Verifique la instalación:** Asegúrese de que el módulo esté correctamente instalado y habilitado en **Módulos > Gestor de módulos**.
    2.  **Permisos:** Verifique que su cuenta de usuario tenga los permisos necesarios para gestionar módulos y productos.
    3.  **Conflictos de módulos:** En raras ocasiones, otro módulo que modifique en gran medida la lista de productos o las acciones masivas podría entrar en conflicto. Intente deshabilitar temporalmente otros módulos instalados recientemente para ver si el problema se resuelve.

**P: Accidentalmente reemplacé el texto incorrecto o cometí un error. ¿Cómo puedo deshacerlo?**
R: Desafortunadamente, el módulo realiza una actualización directa de la base de datos y no hay un botón de "deshacer" incorporado. Por eso las copias de seguridad son cruciales.
    -   **Restaurar desde la copia de seguridad:** La forma más segura de revertir es restaurar su base de datos desde una copia de seguridad realizada *antes* de ejecutar la operación.
    -   **Ejecutar una operación inversa:** Si solo cambió una frase simple, podría ejecutar otra operación de búsqueda y reemplazo para revertirla (por ejemplo, buscar "texto nuevo" y reemplazar con "texto antiguo"). Esto es arriesgado y solo funciona para reemplazos simples y directos.

**P: ¿Puedo usar este módulo para tiendas multi-idioma?**
R: Sí, el módulo opera en campos de producto, que a menudo son compatibles con varios idiomas en PrestaShop. Cuando selecciona campos como "Descripción" o "Nombre del producto", el módulo normalmente aplicará la búsqueda y reemplazo a todos los idiomas activos para esos campos. La interfaz debería permitirle especificar qué idiomas desea seleccionar si esa opción está disponible.

**P: La operación de búsqueda y reemplazo es muy lenta o se agota el tiempo de espera para un gran número de productos.**
R:
    1.  **Recursos del servidor:** Las operaciones grandes en miles de productos pueden consumir muchos recursos. Asegúrese de que su servidor tenga límites de memoria PHP y tiempo de ejecución adecuados. Es posible que deba aumentar `memory_limit` y `max_execution_time` en su `php.ini` (consulte a su proveedor de alojamiento o webmaster).
    2.  **Procesar en lotes:** Si es posible, filtre su lista de productos y ejecute la operación en lotes más pequeños de productos (por ejemplo, por categoría, marca o rango de ID) en lugar de intentar procesar todo su catálogo a la vez.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una visión técnica general para desarrolladores y webmasters que buscan comprender, depurar o extender el módulo "Buscar y reemplazar texto en campos de producto".

### 4.1 Visión general de la arquitectura
El módulo `snrp` es un módulo de PrestaShop sencillo centrado principalmente en extender la funcionalidad de la lista de productos del Back Office. Aprovecha el sistema de hooks de PrestaShop para inyectar una nueva acción masiva en el controlador `AdminProducts`. La lógica central reside dentro del archivo principal del módulo, manejando la visualización del formulario de búsqueda/reemplazo y la ejecución de las actualizaciones de la base de datos. No utiliza clases `ObjectModel` personalizadas ni controladores de administración dedicados, sino que extiende las vistas de administración existentes de PrestaShop.

### 4.2 Controladores (`controllers/`)
Este módulo no introduce ningún controlador personalizado de Front-Office o Back-Office. Su funcionalidad se integra en el controlador `AdminProducts` existente a través de hooks.

### 4.3 Clases y modelos principales (`classes/`)
Este módulo no define ninguna clase personalizada en un directorio `classes/`. Toda la lógica central está contenida dentro del archivo principal del módulo `snrp/index.php`. El módulo interactúa directamente con los `ObjectModel` de `Product` y `ProductLang` de PrestaShop, y potencialmente con los datos de `FeatureValue`, `AttributeGroup` y `Tag`, realizando actualizaciones SQL basadas en la entrada del usuario.

### 4.4 Activos JavaScript (`views/js/`)

-   **`snrp/views/js/snrp.js`**
    *   **Alcance:** Back-office (específicamente, la página de lista de `AdminProducts`).
    *   **Responsabilidad:** Este script es responsable del comportamiento del lado del cliente de la herramienta de búsqueda y reemplazo.
        *   Probablemente vincula un detector de eventos a la opción "Buscar y reemplazar texto en campos de producto" dentro del menú desplegable "Acciones masivas".
        *   Cuando se selecciona, activa la visualización de la ventana modal o el formulario donde el usuario ingresa el término de búsqueda, el término de reemplazo y selecciona los campos de destino.
        *   Maneja la solicitud AJAX al método `getContent()` del módulo (o un endpoint AJAX dedicado si se implementara dentro de `index.php`) para enviar los parámetros de búsqueda y reemplazo.
        *   Gestiona la retroalimentación de la interfaz de usuario durante y después de la operación (por ejemplo, spinners de carga, mensajes de éxito/error).
        *   Podría incluir lógica de validación para los campos de entrada antes del envío.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`snrp/views/css/snrp.css`**
    *   **Alcance:** Back-office (específicamente, la página de lista de `AdminProducts`).
    *   **Responsabilidad:** Esta hoja de estilo proporciona el estilo visual para la interfaz de búsqueda y reemplazo.
        *   Define la apariencia de la ventana modal (tamaño, posicionamiento, superposición de fondo).
        *   Estiliza los campos de entrada, botones, casillas de verificación y cualquier otro elemento de la interfaz de usuario dentro del formulario de búsqueda y reemplazo.
        *   Asegura que la interfaz se integre visualmente con el tema del Back Office de PrestaShop.
    *   **Selectores de clase CSS clave que los desarrolladores pueden anular:** Los desarrolladores pueden inspeccionar el HTML generado del modal para identificar nombres de clase específicos (por ejemplo, `.snrp-modal`, `.snrp-form-group`, `.snrp-button`) para personalizar su apariencia en sus temas de administración personalizados o a través de `override/css/admin.css`.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)
La descripción del módulo indica que no hay archivos `.tpl` en `views/templates/`. Esto sugiere que el formulario de configuración del módulo y la interfaz modal de búsqueda/reemplazo probablemente se renderizan directamente dentro del método `getContent()` de `snrp/index.php` utilizando HTML y PHP sin procesar, o generando dinámicamente los elementos del formulario a través de JavaScript.

Si se utiliza un modal, es posible que la estructura HTML se inyecte directamente en el DOM por `snrp.js` o se renderice como parte de la respuesta de `getContent()`.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    *   Este módulo no crea ninguna tabla de base de datos personalizada.
    *   Modifica directamente las tablas existentes de PrestaShop, principalmente:
        *   `ps_product_lang`: Para nombres de productos, descripciones cortas, descripciones, meta títulos, meta descripciones y URLs amigables (campos específicos del idioma).
        *   `ps_tag`: Para etiquetas de productos.
        *   Potencialmente `ps_feature_product` y `ps_product_attribute_lang` si se seleccionan valores de características y valores de atributos.
    *   La configuración (si estuviera presente) se almacenaría típicamente en `ps_configuration`.

-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| :-------- | :--------------- | :---------------- |
| `displayBackOfficeHeader` | Se renderiza en la sección `<head>` del Back Office. | Se utiliza para incluir `snrp.js` y `snrp.css` en las páginas de administración relevantes (por ejemplo, `AdminProducts`). |
| `displayAdminProductsExtra` | Renderiza contenido adicional en la página de lista de `AdminProducts`. | Este hook probablemente se utiliza para inyectar la estructura HTML para la opción "Buscar y reemplazar texto en campos de producto" en el menú desplegable "Acciones masivas" o para añadir un botón que active el modal. |
| `actionProductUpdate` / `actionObjectProductUpdateAfter` | Se ejecuta después de que se actualiza un producto. | Aunque no se indica explícitamente, el módulo podría engancharse a estos para realizar acciones adicionales o registrar después de una operación exitosa de búsqueda y reemplazo, aunque las actualizaciones SQL directas son más probables por razones de rendimiento. |
| `actionAdminProductsListingResultsModifier` | Modifica los resultados de la lista de productos. | Menos probable para este módulo, pero podría usarse para añadir una columna o modificar los datos mostrados antes de que se active la acción de búsqueda/reemplazo. |

La funcionalidad central de realizar la lógica de búsqueda y reemplazo se manejará dentro del método `getContent()` del módulo (o un método AJAX dedicado dentro de `index.php`) cuando se envíe el formulario, procesando los ID de producto y los campos seleccionados.

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Buscar y reemplazar texto en campos de producto", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.

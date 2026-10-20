---
title: "Cambio masivo de tipo de producto - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Cambio masivo de tipo de producto' de MyPresta.eu."
sidebar:
  label: "Cambio masivo de tipo de producto - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Mass change product type en MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-change-product-type.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/mass-change-product-type/)
>
> ---


# Cambio masivo de tipo de producto

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y normalmente están habilitadas por defecto en la mayoría de los entornos de alojamiento.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

El módulo "Cambio masivo de tipo de producto" proporciona una única e intuitiva pantalla de configuración dentro de su Back Office de PrestaShop. Esta pantalla le guía a través de la selección de productos y luego aplica el cambio de tipo de producto deseado.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Para acceder a la configuración del módulo, navegue a **Módulos > Gestor de módulos**, busque "Cambio masivo de tipo de producto" y haga clic en **"Configurar"**.

La página de configuración se divide en dos secciones principales: **1. Seleccionar productos** y **2. Qué hacer con los productos seleccionados**.

#### Sección 1: Seleccionar productos

Esta sección le permite definir qué productos se verán afectados por el cambio masivo. Puede seleccionar productos basándose en varios criterios.

##### 1.1 Seleccionar productos por categoría

- **Qué hace este ajuste:** Le permite seleccionar todos los productos que pertenecen a una o más categorías específicas.
- **Efecto de cambiar este ajuste:**
  - *Cuando se seleccionan categorías:* Solo los productos dentro de las categorías elegidas se considerarán para el cambio de tipo.
  - *Cuando no se seleccionan categorías:* Este criterio no se utilizará para filtrar productos.
- **Valor recomendado:** Seleccione las categorías relevantes para su operación de cambio masivo.
- **Escenario / ejemplo del comerciante:** Desea convertir todos los productos de su categoría "Descargas digitales" de productos estándar a productos virtuales. Seleccionaría la categoría "Descargas digitales" aquí.

##### 1.2 Seleccionar productos por marca

- **Qué hace este ajuste:** Le permite seleccionar todos los productos asociados con una o más marcas (fabricantes) específicas.
- **Efecto de cambiar este ajuste:**
  - *Cuando se seleccionan marcas:* Solo los productos de las marcas elegidas se considerarán para el cambio de tipo.
  - *Cuando no se seleccionan marcas:* Este criterio no se utilizará para filtrar productos.
- **Valor recomendado:** Seleccione las marcas relevantes para su operación de cambio masivo.
- **Escenario / ejemplo del comerciante:** Ha decidido vender todos los productos de "Marca X" como paquetes. Seleccionaría "Marca X" aquí.

##### 1.3 Seleccionar productos por característica

- **Qué hace este ajuste:** Le permite seleccionar productos que tienen una característica específica y, opcionalmente, un valor específico para esa característica.
- **Efecto de cambiar este ajuste:**
  - *Cuando se selecciona una característica (y opcionalmente un valor):* Solo se considerarán los productos que coincidan con este criterio de característica.
  - *Cuando no se selecciona ninguna característica:* Este criterio no se utilizará para filtrar productos.
- **Valor recomendado:** Elija la característica y el valor que identifiquen con precisión los productos que desea modificar.
- **Escenario / ejemplo del comerciante:** Desea cambiar todos los productos con la característica "Material" establecida en "Digital" a productos virtuales. Seleccionaría "Material" y luego "Digital" aquí.

##### 1.4 Seleccionar productos por atributo

- **Qué hace este ajuste:** Le permite seleccionar productos que tienen un atributo específico y, opcionalmente, un valor específico para ese atributo. Esto es útil para productos con combinaciones.
- **Efecto de cambiar este ajuste:**
  - *Cuando se selecciona un atributo (y opcionalmente un valor):* Solo se considerarán los productos que coincidan con este criterio de atributo.
  - *Cuando no se selecciona ningún atributo:* Este criterio no se utilizará para filtrar productos.
- **Valor recomendado:** Elija el atributo y el valor que identifiquen con precisión los productos que desea modificar.
- **Escenario / ejemplo del comerciante:** Desea convertir todos los productos que tienen el atributo "Tamaño" establecido en "Descargable" a productos virtuales. Seleccionaría "Tamaño" y luego "Descargable" aquí.

##### 1.5 Seleccionar productos por frase de búsqueda

- **Qué hace este ajuste:** Le permite seleccionar productos cuyos nombres contienen una frase específica. Esto utiliza una herramienta de búsqueda para encontrar productos.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce una frase de búsqueda:* Los productos cuyos nombres coincidan con la frase se añadirán a la selección.
  - *Cuando no se introduce ninguna frase de búsqueda:* Este criterio no se utilizará para filtrar productos.
- **Valor recomendado:** Introduzca una frase clara y concisa para identificar sus productos objetivo.
- **Escenario / ejemplo del comerciante:** Desea cambiar todos los productos con "eBook" en su nombre a productos virtuales. Escribiría "eBook" en el cuadro de búsqueda.

##### 1.6 Lista de productos seleccionados

- **Qué hace este ajuste:** Después de aplicar cualquiera de los filtros anteriores, esta área mostrará una lista de productos que coinciden con sus criterios. Puede eliminar manualmente productos de esta lista si no desea que se vean afectados.
- **Efecto de cambiar este ajuste:**
  - *Eliminar un producto:* Ese producto específico se excluirá del cambio de tipo masivo.
  - *Dejar productos en la lista:* Se incluirán en el cambio de tipo masivo.
- **Valor recomendado:** Revise siempre esta lista cuidadosamente para asegurarse de que solo se seleccionen los productos deseados.
- **Escenario / ejemplo del comerciante:** Buscó "eBook" pero apareció un libro físico titulado "Manual del Lector de eBook". Eliminaría este producto específico de la lista.

#### Sección 2: Qué hacer con los productos seleccionados

Una vez que haya seleccionado sus productos objetivo, esta sección le permite elegir el nuevo tipo de producto que desea aplicar.

##### 2.1 Cambiar tipo de producto a:

- **Qué hace este ajuste:** Este menú desplegable le permite seleccionar el nuevo tipo de producto para todos los productos identificados en la Sección 1.
- **Opciones:**
  - **Producto estándar:** Un producto físico regular.
  - **Paquete de productos:** Un conjunto de otros productos.
  - **Producto con combinaciones:** Un producto con variaciones (por ejemplo, tamaño, color).
  - **Producto virtual:** Un producto no físico (por ejemplo, servicio, descarga).
- **Efecto de cambiar este ajuste:**
  - *Seleccionar una opción:* Todos los productos seleccionados se convertirán a este nuevo tipo.
- **Valor recomendado:** Elija el tipo de producto que refleje con precisión la nueva naturaleza de sus productos seleccionados.
- **Escenario / ejemplo del comerciante:** Ha seleccionado todos los productos "eBook". Elegiría "Producto virtual" aquí.

##### 2.2 Botón Aplicar cambios

- **Qué hace este ajuste:** Este botón ejecuta la operación de cambio masivo.
- **Efecto de cambiar este ajuste:**
  - *Al hacer clic en el botón:* El módulo procesará todos los productos de la "Lista de productos seleccionados" y cambiará su tipo de producto al elegido en "Cambiar tipo de producto a:". Normalmente aparecerá un mensaje de confirmación.
- **Valor recomendado:** Haga clic en esto solo después de estar absolutamente seguro de su selección de productos y del nuevo tipo deseado.
- **Escenario / ejemplo del comerciante:** Después de revisar sus eBooks seleccionados y confirmar "Producto virtual" como el nuevo tipo, hace clic en "Aplicar cambios" para convertirlos todos.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | **Seleccionar productos por categoría** | Seleccionar categorías relevantes | Filtra productos por sus categorías asignadas. |
| Configuración del módulo | **Seleccionar productos por marca** | Seleccionar marcas relevantes | Filtra productos por su fabricante/marca. |
| Configuración del módulo | **Seleccionar productos por característica** | Seleccionar característica y valor | Filtra productos por características específicas y sus valores. |
| Configuración del módulo | **Seleccionar productos por atributo** | Seleccionar atributo y valor | Filtra productos por atributos específicos y sus valores (para combinaciones). |
| Configuración del módulo | **Seleccionar productos por frase de búsqueda** | Introducir término de búsqueda | Filtra productos por palabras clave en su nombre. |
| Configuración del módulo | **Lista de productos seleccionados** | Revisar cuidadosamente | Muestra los productos seleccionados; permite la eliminación manual antes de procesar. |
| Configuración del módulo | **Cambiar tipo de producto a:** | Elegir el tipo deseado | Establece el nuevo tipo de producto (Estándar, Paquete, Combinaciones, Virtual) para todos los productos seleccionados. |
| Configuración del módulo | **Botón Aplicar cambios** | Hacer clic para ejecutar | Inicia el cambio masivo de tipo de producto para todos los productos seleccionados. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Cambié los tipos de producto, pero no veo los cambios en el front office de mi tienda.**
R: Después de realizar cambios en el Back Office, siempre borre la caché de PrestaShop. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. Es posible que también deba borrar la caché de su navegador (Ctrl+F5 o Cmd+R).

**P: Algunos productos no se cambiaron, aunque estaban en mi selección.**
R:

1.  **Vuelva a verificar la "Lista de productos seleccionados":** ¿Los eliminó accidentalmente de la lista antes de aplicar los cambios?
2.  **Verifique los criterios:** Vuelva a verificar sus criterios de selección (categoría, marca, característica, atributo, frase de búsqueda). ¿Los productos realmente coinciden con todos los filtros seleccionados?
3.  **Estado del producto:** Asegúrese de que los productos estén activos y no deshabilitados.
4.  **Errores:** Verifique si apareció algún mensaje de error durante el proceso de "Aplicar cambios".

**P: ¿Puedo revertir los cambios realizados por este módulo?**
R: Este módulo realiza actualizaciones directas de la base de datos. No hay un botón de "deshacer" dentro del módulo. Por eso es **crucial una copia de seguridad de la base de datos antes de usarlo**. Si necesita revertir, normalmente restauraría su base de datos desde una copia de seguridad tomada *antes* de usar el módulo. Alternativamente, tendría que usar el módulo nuevamente para cambiar los tipos de producto a su estado original, o editarlos manualmente.

**P: ¿Este módulo afectará el SEO o las URL de mi producto?**
R: Cambiar el tipo de un producto en sí mismo no altera directamente su URL amigable para SEO. Sin embargo, si el cambio de tipo conduce a otras modificaciones (por ejemplo, eliminación de combinaciones, cambio de estructura del producto), siempre es una buena idea verificar las páginas de sus productos y potencialmente regenerar las URL (sección SEO y URL en PrestaShop) si nota algún problema, aunque esto es raro para un simple cambio de tipo.

**P: El módulo no muestra ningún producto cuando uso la frase de búsqueda.**
R:

1.  **Verifique si hay errores tipográficos:** Asegúrese de que su frase de búsqueda esté escrita correctamente.
2.  **Sensibilidad a mayúsculas y minúsculas:** Los nombres de los productos pueden ser sensibles a mayúsculas y minúsculas dependiendo de la configuración de su base de datos, intente con diferentes mayúsculas y minúsculas.
3.  **Idioma:** Asegúrese de que está buscando en el idioma correcto si su tienda es multilingüe.
4.  **Conflicto de módulos:** Deshabilite temporalmente otros módulos relacionados con la búsqueda para verificar si hay conflictos.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una visión técnica general para desarrolladores y webmasters que mantienen o extienden una tienda PrestaShop utilizando el módulo "Cambio masivo de tipo de producto".

### 4.1 Visión general de la arquitectura

El módulo "Cambio masivo de tipo de producto" (`massptype`) es un módulo estándar de PrestaShop que opera principalmente dentro del Back Office. Aprovecha la clase `Module` de PrestaShop y utiliza AJAX para el filtrado de productos y el proceso de actualización masiva. La lógica central reside en el archivo principal del módulo, que maneja la configuración, la selección de productos y la actualización masiva de los tipos de producto. Integra una herramienta de búsqueda personalizada para la selección de productos.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores dedicados de front-office o back-office en los directorios `controllers/admin` o `controllers/front`. Toda la lógica se maneja dentro del archivo principal del módulo `massptype.php` y su método `getContent()`, que actúa como el punto de entrada de configuración principal. Las solicitudes AJAX se envían a través del archivo `ajax_products_list.php` del módulo principal.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define clases `ObjectModel` personalizadas. Interactúa directamente con los métodos `Product` y `Product::updateProductFlags()` del núcleo de PrestaShop para modificar los tipos de producto.

### 4.4 Activos JavaScript (`views/js/`)

- `massptype/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office (utilizado dentro de la página de configuración del módulo).
  - **Propósito:** Proporciona la lógica central para la funcionalidad de autocompletado de la búsqueda de productos. Probablemente maneja el envío de solicitudes AJAX al punto final `ajax_products_list.php` del módulo para obtener sugerencias de productos basadas en la entrada del usuario.
- `massptype/views/js/jquery.autocomplete.js`
  - **Alcance:** Back-office (utilizado dentro de la página de configuración del módulo).
  - **Propósito:** Parece ser un plugin de jQuery para la funcionalidad de autocompletado, probablemente una dependencia o una implementación personalizada utilizada por la herramienta de búsqueda. Maneja el aspecto de la interfaz de usuario de mostrar sugerencias y la interacción del usuario.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `massptype/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back-office (estilos de elementos dentro de la página de configuración del módulo).
  - **Propósito:** Estiliza el menú desplegable de autocompletado, los campos de entrada y, potencialmente, la lista de productos seleccionados dentro de la interfaz de la herramienta de búsqueda del módulo. Los desarrolladores pueden anular estos estilos en su tema personalizado del Back Office o añadiendo reglas CSS más específicas.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - `massptype/views/templates/hook/form.tpl`
    - **Hook:** No está directamente enganchado en el sentido tradicional, sino que es renderizado por `getContent()` del archivo principal del módulo.
    - **Propósito:** Esta es la plantilla principal para el formulario de configuración del módulo en el Back Office. Contiene la estructura HTML para seleccionar productos por varios criterios y elegir el nuevo tipo de producto.
- **Plantillas de administración (`views/templates/admin/`)**:
  - `massptype/views/templates/admin/target_products.tpl`
    - **Propósito:** Esta plantilla se utiliza probablemente para renderizar la lista de productos seleccionados después de que se hayan aplicado los criterios de filtrado. Se actualiza dinámicamente a través de AJAX para mostrar qué productos se verán afectados.
  - `massptype/views/templates/admin/wtd.tpl` (Qué hacer)
    - **Propósito:** Esta plantilla probablemente renderiza la sección donde el usuario selecciona el nuevo tipo de producto (Estándar, Paquete, Combinaciones, Virtual) y el botón "Aplicar cambios".
- **Otras plantillas**:
  - `massptype/lib/searchTool/views/scripts.tpl`
    - **Propósito:** Esta plantilla probablemente incluye código JavaScript o inicializa la funcionalidad de autocompletado de JavaScript para la herramienta de búsqueda de productos. Podría incluirse dentro de `form.tpl`.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: El módulo no crea tablas de base de datos personalizadas. Modifica las tablas principales existentes de PrestaShop, específicamente `ps_product` (y potencialmente `ps_product_shop`) actualizando los campos `cache_is_pack`, `cache_has_attachments`, `is_virtual` y `cache_default_attribute`, que determinan el tipo de producto. La configuración se almacena en `ps_configuration` utilizando claves estándar (por ejemplo, `_PS_MASS_PTYPE_...`).
- **Tabla de hooks registrados**:
  El módulo no registra ningún hook de visualización tradicional de front-office o back-office. Su funcionalidad está completamente contenida dentro de su método `getContent()` y las llamadas AJAX.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionModuleInstall` | Durante la instalación del módulo | Configura la configuración inicial. |
| `actionModuleUninstall` | Durante la desinstalación del módulo | Limpia la configuración. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Cambio masivo de tipo de producto", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad del módulo.

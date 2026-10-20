---
title: "Búsqueda de productos AJAX en el Back Office - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Búsqueda de productos AJAX en el Back Office' de MyPresta.eu."
sidebar:
  label: "Búsqueda de productos AJAX en el Back Office - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Back office ajax product search en MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-ajax-product-search.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/back-office-ajax-product-search/)
>
> ---


# Búsqueda de productos AJAX en el Back Office

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y normalmente están disponibles en cualquier entorno de alojamiento moderno.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Este módulo está diseñado para ser altamente eficiente y en gran medida "configúrelo y olvídese". Se integra perfectamente en su back office sin requerir configuraciones complejas.

Cuando haga clic en "Configurar" después de la instalación, normalmente encontrará una interfaz sencilla, a menudo sin ajustes específicos que ajustar. La funcionalidad principal del módulo (búsqueda de productos AJAX con autocompletado) se habilita por defecto tras la instalación.

-   **Qué hace esta pantalla:** Esta es el área de configuración principal del módulo. Sin embargo, para "Búsqueda de productos AJAX en el Back Office", su función principal es confirmar que el módulo está instalado y activo.
-   **Efecto de cambiar la configuración:** Dado que no hay configuraciones específicas configurables por el usuario expuestas en esta pantalla, el módulo operará con su comportamiento predeterminado y optimizado.
-   **Valor recomendado:** Normalmente no se requieren acciones específicas aquí. El módulo está diseñado para funcionar de forma inmediata.
-   **Escenario / ejemplo del comerciante:** Después de la instalación, simplemente navegue a cualquier página del back office. Debería notar que cuando comienza a escribir en un campo de búsqueda de productos, las sugerencias aparecen instantáneamente, y al hacer clic en ellas, se le lleva directamente a la página de edición del producto.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | (Sin ajustes específicos) | N/A | El módulo mejora automáticamente la búsqueda de productos del back office con la funcionalidad de autocompletado AJAX tras la instalación. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He instalado el módulo, pero la barra de búsqueda no parece funcionar de manera diferente.**
R:

1.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. A veces, la caché de PrestaShop necesita ser borrada para que los nuevos activos del módulo (como JavaScript y CSS) se carguen correctamente.
2.  **Caché del navegador:** Intente borrar la caché de su navegador o probar en una ventana de incógnito/privada.
3.  **Estado del módulo:** Asegúrese de que el módulo esté habilitado en **Módulos > Gestor de módulos**.
4.  **Compatibilidad del tema:** Aunque es raro para los módulos del back office, un tema de administración muy personalizado podría interferir. Si el problema persiste, póngase en contacto con el soporte de MyPresta.eu.

**P: ¿Este módulo ralentizará mi back office?**
R: No, todo lo contrario. Al usar AJAX, el módulo realiza búsquedas en segundo plano sin recargas completas de la página, lo que es inherentemente más rápido y eficiente que los métodos de búsqueda tradicionales. Está diseñado para mejorar el rendimiento, no para obstaculizarlo.

**P: ¿Este módulo afecta la búsqueda de mi front office para los clientes?**
R: No, este módulo es estrictamente para el back office de PrestaShop. No tiene ningún impacto en su tienda orientada al cliente ni en su funcionalidad de búsqueda.

**P: ¿Puedo configurar el número de resultados de búsqueda que se muestran?**
R: Este módulo está diseñado para la simplicidad y la funcionalidad lista para usar. Normalmente no ofrece opciones configurables para el número de resultados. El comportamiento predeterminado suele estar optimizado para una buena experiencia de usuario.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo `Back office ajax product search` (boproductfinder) es un módulo ligero de PrestaShop centrado principalmente en mejorar la experiencia del usuario dentro del back office. Logra su funcionalidad inyectando activos personalizados de JavaScript y CSS en la cabecera del back office, aprovechando el sistema de hooks de PrestaShop. La lógica central reside en JavaScript del lado del cliente, que intercepta la entrada del usuario en campos de búsqueda específicos y realiza solicitudes AJAX a los puntos finales de búsqueda de productos incorporados de PrestaShop, luego muestra los resultados utilizando una interfaz de usuario de autocompletado. No introduce nuevas tablas de base de datos ni lógica compleja del lado del servidor más allá de lo que PrestaShop ya proporciona para la búsqueda de productos.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front office o back office. Se basa en los controladores existentes de PrestaShop para manejar las consultas de búsqueda de productos (por ejemplo, los métodos AJAX de `AdminProductsController`).

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase PHP personalizada o definiciones de `ObjectModel`. Su funcionalidad es principalmente del lado del cliente.

### 4.4 Activos JavaScript (`views/js/`)

-   **`boproductfinder/views/autocomplete.js`**
    -   **Alcance**: Back-office.
    -   **Descripción**: Este script probablemente implementa o integra una biblioteca genérica de autocompletado. Proporciona la funcionalidad principal para mostrar sugerencias a medida que el usuario escribe en un campo de entrada de texto. Maneja la representación de la interfaz de usuario de la lista de sugerencias, la navegación con el teclado dentro de la lista y la selección de elementos. Es un componente fundamental para la búsqueda interactiva del módulo.
-   **`boproductfinder/views/boproductfinder.js`**
    -   **Alcance**: Back-office.
    -   **Descripción**: Este es el script principal del módulo.
    -   **Detectores de eventos**: Probablemente se vincula a eventos `keyup` o `input` en campos de entrada de búsqueda de productos específicos dentro del back office de PrestaShop (por ejemplo, `input[name="product_search"]` o selectores similares).
    -   **Llamadas AJAX**: Cuando un usuario escribe, este script activa solicitudes AJAX a la API interna de búsqueda de productos de PrestaShop (por ejemplo, `admin-ajax.php` o una acción AJAX de un controlador de administración específico para la búsqueda de productos). Envía la consulta de búsqueda y, potencialmente, otros parámetros (por ejemplo, `id_lang`).
    -   **Manipulación del DOM**: Recibe la respuesta JSON del servidor (que contiene ID de productos, nombres y, potencialmente, enlaces) y utiliza `autocomplete.js` (o lógica similar) para mostrar estos resultados en una lista desplegable debajo del campo de búsqueda.
    -   **Navegación**: Cuando se hace clic o se selecciona una sugerencia de producto, este script construye la URL a la página de edición del producto (por ejemplo, `admin/index.php?controller=AdminProducts&id_product=X&updateproduct&token=Y`) y redirige el navegador a esa página.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`boproductfinder/views/autocomplete.css`**
    -   **Alcance**: Estilo del formulario de administración del back office.
    -   **Descripción**: Esta hoja de estilo proporciona el estilo visual para la lista de sugerencias de autocompletado.
    -   **Componentes y contenedores principales de la interfaz de usuario que estiliza**:
        -   El contenedor desplegable para los resultados de búsqueda.
        -   Elementos de lista individuales dentro de las sugerencias.
        -   Resaltado para la sugerencia actualmente sobre la que se pasa el ratón o seleccionada.
        -   Potencialmente indicadores de carga o mensajes de "sin resultados".
    -   **Selectores de clase CSS clave que los desarrolladores pueden anular**: Los desarrolladores pueden inspeccionar el HTML generado en busca de clases como `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected` para personalizar la apariencia en su tema de administración.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

Este módulo no contiene ningún archivo de plantilla Smarty (`.tpl`) personalizado. Su funcionalidad se inyecta directamente a través de activos JavaScript y CSS cargados a través de hooks.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Se basa en las tablas existentes de PrestaShop `ps_product`, `ps_product_lang` y tablas relacionadas para los datos del producto. La configuración se almacena en `ps_configuration` si hubiera alguna configuración presente, pero para este módulo, suele ser mínima o inexistente.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Se ejecuta en la sección `<head>` de cada página del back office. | Se utiliza para incluir los archivos CSS y JavaScript del módulo (`autocomplete.css`, `autocomplete.js`, `boproductfinder.js`) para garantizar que se carguen en todas las páginas de administración donde pueda ser necesaria la funcionalidad de búsqueda. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración está configurando sus activos multimedia. | Un hook alternativo o complementario a `displayBackOfficeHeader` para agregar archivos CSS y JS, asegurando la compatibilidad entre diferentes versiones de PrestaShop y temas del back office. Asegura que los activos del módulo se registren y carguen correctamente. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Búsqueda de productos AJAX en el Back Office", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad o compatibilidad del módulo.

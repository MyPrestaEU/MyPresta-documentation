---
title: "Combinations List Free - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Combinations List Free para PrestaShop de MyPresta.eu."
sidebar:
  label: "Combinations List Free - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Combinations List Free en MyPresta.eu](https://mypresta.eu/modules/front-office-features/combinations-list-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/combinations-list-free/)
>
> ---


# Combinations List Free

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una instalación de PrestaShop, pero este módulo no tiene requisitos exóticos específicos más allá de un entorno PrestaShop estándar.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haz clic en "Configurar" junto al módulo "Combinations List Free" en tu Gestor de Módulos. Esto te llevará a la pantalla de configuración principal.

#### Ajustes Generales

-   **Qué hace este ajuste:** Esta sección controla el comportamiento general y la apariencia de la lista de combinaciones en tus páginas de producto.

    -   **Mostrar lista de combinaciones en la página del producto:**

        -   **Qué hace este ajuste:** Este es el interruptor principal para habilitar o deshabilitar la funcionalidad del módulo.
        -   **Efecto de cambiar este ajuste:**
            -   *Cuando está habilitado (SÍ):* El módulo intentará mostrar la lista de combinaciones en las páginas de producto según tus otros ajustes.
            -   *Cuando está deshabilitado (NO):* El módulo estará inactivo y tus páginas de producto volverán a los selectores de combinación predeterminados de PrestaShop (desplegables).
        -   **Valor recomendado:** SÍ (para usar el módulo).
        -   **Escenario / ejemplo del comerciante:** Si estás probando el módulo o deseas deshabilitarlo temporalmente sin desinstalarlo, configúralo en NO.
    -   **Hook para mostrar la lista de combinaciones:**

        -   **Qué hace este ajuste:** Determina dónde aparecerá la lista de combinaciones en la página del producto. Esto es crucial para integrar visualmente la lista con tu tema.
        -   **Efecto de cambiar este ajuste:**
            -   *Cuando se establece en `displayProductButtons` (o un hook similar relacionado con el producto):* La lista aparecerá típicamente cerca del botón "Añadir al carrito" o del precio del producto, a menudo debajo de los detalles principales del producto.
            -   *Cuando se establece en `displayProductExtraContent` (o un hook similar relacionado con pestañas):* La lista aparecerá dentro de una pestaña de producto nueva o existente, manteniendo más limpia el área de descripción principal del producto.
            -   *Cuando se establece en `displayFooterProduct` (o un hook de pie de página similar):* La lista aparecerá en la parte inferior de la página del producto.
        -   **Valor recomendado:** Experimenta con diferentes hooks para encontrar la mejor integración visual con tu tema específico. `displayProductButtons` o `displayProductExtraContent` son opciones comunes.
        -   **Escenario / ejemplo del comerciante:** Si tu página de producto ya es larga, colocar la lista en una pestaña `displayProductExtraContent` puede hacer que la página esté menos desordenada. Si deseas que la lista sea visible de inmediato, un hook como `displayProductButtons` es mejor.
    -   **Mostrar imagen de combinación:**

        -   **Qué hace este ajuste:** Controla si se muestra una pequeña imagen específica para cada combinación en la lista.
        -   **Efecto de cambiar este ajuste:**
            -   *Cuando está habilitado (SÍ):* Si has subido imágenes específicas para cada combinación de producto, aparecerán junto a su combinación respectiva en la lista.
            -   *Cuando está deshabilitado (NO):* Solo se mostrará el nombre, la referencia y el precio de la combinación, sin imagen.
        -   **Valor recomendado:** SÍ, si tienes imágenes únicas para las combinaciones. Esto ayuda significativamente a los clientes a visualizar el producto exacto que están seleccionando.
        -   **Escenario / ejemplo del comerciante:** Para la ropa, mostrar una imagen de una camiseta roja para la combinación "Roja - Grande" es mucho más claro que solo texto.
    -   **Mostrar referencia de combinación:**

        -   **Qué hace este ajuste:** Determina si se muestra el número de referencia interno para cada combinación.
        -   **Efecto de cambiar este ajuste:**
            -   *Cuando está habilitado (SÍ):* La referencia de la combinación (por ejemplo, SKU) será visible en la lista.
            -   *Cuando está deshabilitado (NO):* El número de referencia estará oculto.
        -   **Valor recomendado:** SÍ, especialmente para tiendas B2B o productos donde los clientes a menudo piden por referencia.
        -   **Escenario / ejemplo del comerciante:** Un cliente que vuelve a pedir una pieza específica podría conocerla por su número de referencia, lo que facilita su búsqueda.
    -   **Mostrar campo de entrada de cantidad de combinación:**

        -   **Qué hace este ajuste:** Permite a los clientes especificar la cantidad para cada combinación directamente dentro de la lista, en lugar de añadir solo uno a la vez.
        -   **Efecto de cambiar este ajuste:**
            -   *Cuando está habilitado (SÍ):* Aparecerá un campo de entrada de cantidad (por ejemplo, un cuadro numérico) junto a cada combinación, permitiendo a los clientes introducir la cantidad deseada antes de hacer clic en "Añadir al carrito".
            -   *Cuando está deshabilitado (NO):* El botón "Añadir al carrito" normalmente añadirá una unidad de la combinación al carrito.
        -   **Valor recomendado:** SÍ, para la mayoría de las tiendas, ya que mejora la eficiencia para los clientes que compran varias unidades de la misma combinación.
        -   **Escenario / ejemplo del comerciante:** Un cliente que compra 5 unidades de "Azul - Mediano" y 3 unidades de "Verde - Grande" puede hacerlo rápidamente desde la lista.
    -   **Mostrar precio de combinación:**

        -   **Qué hace este ajuste:** Controla si el precio de cada combinación individual se muestra en la lista.
        -   **Efecto de cambiar este ajuste:**
            -   *Cuando está habilitado (SÍ):* Se mostrará el precio de cada combinación específica.
            -   *Cuando está deshabilitado (NO):* El precio estará oculto y los clientes solo verán el precio principal del producto o necesitarán inferirlo.
        -   **Valor recomendado:** SÍ. La transparencia en los precios es crucial para la confianza del cliente y la toma de decisiones.
        -   **Escenario / ejemplo del comerciante:** Si diferentes tamaños o colores tienen precios diferentes, mostrar el precio exacto de cada combinación es esencial.
    -   **Mostrar disponibilidad de combinación:**

        -   **Qué hace este ajuste:** Muestra el estado del stock (por ejemplo, "En stock", "Agotado", "¡Últimas unidades!") para cada combinación.
        -   **Efecto de cambiar este ajuste:**
            -   *Cuando está habilitado (SÍ):* Los clientes verán el estado de disponibilidad de cada combinación, ayudándoles a tomar decisiones de compra informadas.
            -   *Cuando está deshabilitado (NO):* El estado del stock no se mostrará en la lista.
        -   **Valor recomendado:** SÍ. Esto evita que los clientes añadan artículos agotados a su carrito, reduciendo la frustración y los carritos abandonados.
        -   **Escenario / ejemplo del comerciante:** Un cliente puede ver inmediatamente que la camiseta "Roja - Grande" está agotada y elegir "Azul - Grande" en su lugar.
    -   **Mostrar descripción de combinación:**

        -   **Qué hace este ajuste:** Si tienes descripciones específicas para cada combinación, este ajuste controla su visualización.
        -   **Efecto de cambiar este ajuste:**
            -   *Cuando está habilitado (SÍ):* Cualquier descripción única asociada a una combinación se mostrará en la lista.
            -   *Cuando está deshabilitado (NO):* Las descripciones específicas de la combinación estarán ocultas.
        -   **Valor recomendado:** SÍ, si tus combinaciones tienen descripciones distintas que añaden valor a la decisión del cliente.
        -   **Escenario / ejemplo del comerciante:** Para un producto personalizable, una descripción de combinación podría detallar los materiales específicos utilizados para esa variante.
    -   **Texto del botón Añadir al carrito:**

        -   **Qué hace este ajuste:** Te permite personalizar el texto que se muestra en el botón "Añadir al carrito" para cada combinación.
        -   **Efecto de cambiar este ajuste:**
            -   *Cuando se cambia:* El texto del botón se actualizará a tu frase personalizada.
            -   *Cuando se deja vacío:* Se utilizará el texto predeterminado "Añadir al carrito" (o el predeterminado de tu tema).
        -   **Valor recomendado:** "Añadir al carrito" o "Comprar ahora" para mayor claridad. Mantenlo conciso.
        -   **Escenario / ejemplo del comerciante:** Podrías cambiarlo a "Seleccionar y Comprar" si quieres enfatizar la selección antes de la compra.
    -   **Mostrar combinaciones como tabla:**

        -   **Qué hace este ajuste:** Cambia la presentación visual de las combinaciones de una lista simple a una tabla HTML estructurada.
        -   **Efecto de cambiar este ajuste:**
            -   *Cuando está habilitado (SÍ):* Las combinaciones se presentarán en formato de tabla con columnas para imagen, nombre, referencia, precio, cantidad y añadir al carrito. Esto suele ser más compacto y organizado para muchas combinaciones.
            -   *Cuando está deshabilitado (NO):* Las combinaciones se mostrarán como una lista menos estructurada, típicamente una combinación por línea.
        -   **Valor recomendado:** SÍ, para la mayoría de los casos, ya que una tabla proporciona una mejor legibilidad y alineación, especialmente con muchas opciones.
        -   **Escenario / ejemplo del comerciante:** Si tienes más de 20 combinaciones, una tabla facilita mucho el escaneo y la comparación.
    -   **Mostrar combinaciones como pestaña:**

        -   **Qué hace este ajuste:** Este ajuste es probablemente un legado o un detalle de implementación específico. Dada la configuración de `Hook para mostrar la lista de combinaciones`, esto podría ser redundante o referirse a una plantilla específica.
        -   **Efecto de cambiar este ajuste:**
            -   *Cuando está habilitado (SÍ):* Podría forzar la lista de combinaciones a una estructura similar a una pestaña, potencialmente anulando el hook elegido si ese hook no crea una pestaña de forma natural.
            -   *Cuando está deshabilitado (NO):* La visualización seguirá el hook elegido más directamente.
        -   **Valor recomendado:** Generalmente NO, a menos que desees específicamente una pestaña y tu hook elegido no la proporcione. Confía en el ajuste "Hook para mostrar la lista de combinaciones" para la ubicación.
        -   **Escenario / ejemplo del comerciante:** Si tu tema no crea automáticamente pestañas para `displayProductExtraContent`, habilitar esto podría forzar una apariencia similar a una pestaña.

#### 2.1.1 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Mostrar lista de combinaciones en la página del producto | SÍ | Interruptor principal para habilitar/deshabilitar la visualización del módulo en el front-office. |
| Configuración del Módulo | Hook para mostrar la lista de combinaciones | `displayProductButtons` o `displayProductExtraContent` | Determina la posición exacta de la lista en la página del producto. |
| Configuración del Módulo | Mostrar imagen de combinación | SÍ (si existen imágenes) | Muestra imágenes únicas para cada combinación. |
| Configuración del Módulo | Mostrar referencia de combinación | SÍ | Muestra el número de SKU/referencia para cada combinación. |
| Configuración del Módulo | Mostrar campo de entrada de cantidad de combinación | SÍ | Permite a los clientes introducir cantidades para cada combinación. |
| Configuración del Módulo | Mostrar precio de combinación | SÍ | Muestra el precio específico para cada combinación. |
| Configuración del Módulo | Mostrar disponibilidad de combinación | SÍ | Muestra el estado del stock (por ejemplo, "En stock") para cada combinación. |
| Configuración del Módulo | Mostrar descripción de combinación | SÍ (si existen descripciones) | Muestra descripciones únicas para cada combinación. |
| Configuración del Módulo | Texto del botón Añadir al carrito | "Añadir al carrito" | Personaliza el texto de los botones 'Añadir al carrito'. |
| Configuración del Módulo | Mostrar combinaciones como tabla | SÍ | Presenta las combinaciones en un formato de tabla estructurado para una mejor legibilidad. |
| Configuración del Módulo | Mostrar combinaciones como pestaña | NO | (Probablemente legado/específico) Controla la visualización similar a una pestaña; prefiere la configuración del hook. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: La lista de combinaciones no aparece en la página de mi producto.**
**R1:**

-   Primero, verifica si "Mostrar lista de combinaciones en la página del producto" está configurado en SÍ en la configuración del módulo.
-   A continuación, verifica la configuración de "Hook para mostrar la lista de combinaciones". Algunos temas pueden no renderizar todos los hooks estándar de PrestaShop de la misma manera. Intenta cambiar a un hook diferente (por ejemplo, `displayProductButtons`, `displayProductExtraContent`, `displayFooterProduct`) para ver si aparece.
-   Asegúrate de que el producto que estás viendo realmente tiene combinaciones definidas.
-   Borra la caché de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché).

**P2: Las imágenes de mis combinaciones no aparecen en la lista.**
**R2:**

-   Asegúrate de que "Mostrar imagen de combinación" esté habilitado en la configuración del módulo.
-   Fundamentalmente, debes haber subido imágenes específicas para cada combinación en el editor de productos de PrestaShop (Producto > Pestaña Combinaciones > Editar cada combinación > Añadir imagen). Si no se asigna una imagen específica a una combinación, no aparecerá.

**P3: La lista se ve desordenada o no se ajusta al diseño de mi tema.**
**R3:**

-   Intenta habilitar "Mostrar combinaciones como tabla" si aún no lo está. Esto a menudo proporciona un diseño más estructurado y visualmente atractivo.
-   El módulo utiliza su propio CSS. El CSS de tu tema podría estar anulándolo o entrando en conflicto con él. Es posible que necesites un desarrollador web para ajustar el CSS del módulo (`mycombtabfree.css`) o añadir CSS personalizado a tu tema para darle el estilo que desees.
-   Experimenta con diferentes hooks. Algunos hooks pueden tener un mejor estilo predeterminado de tu tema.

**P4: ¿Puedo traducir el texto del botón "Añadir al carrito" a otros idiomas?**
**R4:** Sí. Ve a **Internacional > Traducciones** en el Back Office de PrestaShop. Selecciona "Traducciones de módulos instalados", elige tu tema y luego selecciona "Combinations List Free" del desplegable de módulos. Luego podrás traducir el texto del botón y cualquier otra frase específica del módulo.

**P5: ¿Por qué algunas combinaciones muestran "Agotado" a pesar de que tengo stock?**
**A5:**

-   Verifica la configuración de stock de tu producto en el editor de productos de PrestaShop. Asegúrate de que la combinación específica tenga cantidad disponible.
-   Verifica la configuración global de gestión de stock (Parámetros de la tienda > Configuración de productos > Stock de productos).
-   Borra la caché de PrestaShop después de realizar cualquier ajuste de stock.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Descripción General de la Arquitectura

El módulo "Combinations List Free" (`mycombtabfree`) es un módulo estándar de PrestaShop diseñado para mejorar la página de producto del front-office. Opera principalmente enganchándose a varios puntos de visualización en la página del producto para inyectar su estructura HTML personalizada para las combinaciones de productos. El módulo sigue un patrón básico similar a MVC dentro del marco del módulo de PrestaShop, utilizando una clase de módulo principal para la configuración y el registro de hooks, y plantillas Smarty para renderizar la salida del front-office. Aprovecha las funcionalidades principales existentes de PrestaShop para recuperar datos de productos y combinaciones.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la configuración se maneja a través del método `getContent()` de la clase principal del módulo, y la renderización del front-office se realiza directamente a través de hooks.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no contiene ninguna clase personalizada o definiciones de `ObjectModel` en el directorio `classes/`. Se basa completamente en las clases principales `Product` y `Combination` de PrestaShop para recuperar y mostrar datos.

### 4.4 Activos JavaScript (`views/js/`)

-   **`mycombtabfree/js/atc.js`**
    -   **Alcance:** Front-office.
    -   **Propósito:** Este script es responsable de manejar la funcionalidad "Añadir al carrito" para las combinaciones mostradas por el módulo. Probablemente intercepta los eventos de clic en los botones "Añadir al carrito" personalizados generados por el módulo.
    -   **Funcionalidad:**
        -   Vincula oyentes de eventos a los botones "Añadir al carrito" dentro de la lista/tabla de combinaciones.
        -   Cuando se hace clic en un botón, recopila el `id_product`, `id_product_attribute` (ID de combinación) y, potencialmente, la cantidad del campo de entrada asociado.
        -   Luego realiza una solicitud AJAX al controlador principal `cart` de PrestaShop (o un endpoint similar) para añadir la combinación seleccionada al carrito.
        -   También podría actualizar el bloque del carrito, mostrar notificaciones (éxito/error) o manejar otros comentarios de la interfaz de usuario después de la llamada AJAX.
        -   Probablemente utiliza jQuery o los eventos nativos `prestashop.on` de PrestaShop para actualizaciones dinámicas.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   **`mycombtabfree/css/admin.css`**

    -   **Alcance:** Estilo del formulario de administración del Back-office.
    -   **Propósito:** Contiene estilos específicamente para la página de configuración del módulo en el Back Office de PrestaShop. Esto podría incluir estilos para elementos de formulario, alertas o ajustes de diseño para hacer que la interfaz de configuración sea fácil de usar.
    -   **Selectores clave:** Probablemente apunta a elementos dentro de la salida `getContent()` del módulo, como `.panel`, `.form-group`, `.alert`, etc., para garantizar una interfaz de usuario de administración consistente.
-   **`mycombtabfree/css/mycombtabfree.css`**

    -   **Alcance:** Estilo del cliente del Front-office.
    -   **Propósito:** Proporciona el estilo visual principal para la lista/tabla de combinaciones que se muestra en la página del producto. Esto incluye diseño, tipografía, colores y adaptabilidad.
    -   **Selectores clave:**
        -   `.mycombtabfree-container`: Contenedor principal para la lista de combinaciones.
        -   `.mycombtabfree-table`: Estilos para el elemento `<table>` cuando "Mostrar combinaciones como tabla" está habilitado.
        -   `.mycombtabfree-row`, `.mycombtabfree-cell`: Estilos para filas y celdas de la tabla.
        -   `.mycombtabfree-image`, `.mycombtabfree-name`, `.mycombtabfree-reference`, `.mycombtabfree-price`, `.mycombtabfree-qty`, `.mycombtabfree-atc`: Estilos específicos para cada pieza de datos de combinación.
        -   Consultas de medios para ajustes adaptables en pantallas más pequeñas.
    -   **Anulación del desarrollador:** Los desarrolladores pueden anular estos estilos en los archivos CSS de su tema personalizado utilizando selectores más específicos o modificando este archivo directamente (aunque esto último no se recomienda para facilitar las actualizaciones).

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **`mycombtabfree/views/templates/admin/configure.tpl`**

    -   **Alcance:** Panel de configuración de administración.
    -   **Propósito:** Renderiza el formulario HTML para la configuración del módulo en el Back Office de PrestaShop. Esta plantilla es cargada por el método `getContent()` de la clase principal del módulo.
    -   **Contenido:** Contiene campos de formulario (casillas de verificación, entradas de texto, desplegables de selección) correspondientes a los ajustes descritos en la Sección 4.1.
-   **`mycombtabfree/views/templates/admin/pro-upsell.tpl`**

    -   **Alcance:** Panel de configuración de administración.
    -   **Propósito:** Muestra contenido promocional o un banner de venta adicional para una versión "Pro" del módulo dentro de la configuración del Back Office. Esta es una práctica común para los módulos gratuitos.
-   **`mycombtabfree/views/templates/hook/pro-banner.tpl`**

    -   **Alcance:** Hook del Front-office.
    -   **Propósito:** Renderiza un banner promocional para la versión "Pro" del módulo, probablemente mostrado en un hook del front-office menos intrusivo (por ejemplo, `displayFooter` o `displayLeftColumn`).
-   **`mycombtabfree/views/templates/hook/tab.tpl`**

    -   **Alcance:** Hook del Front-office.
    -   **Propósito:** Esta plantilla se utiliza probablemente cuando el ajuste "Mostrar combinaciones como pestaña" está habilitado, o cuando el módulo está enganchado a una posición que crea naturalmente una pestaña (por ejemplo, `displayProductExtraContent`). Contendría la estructura para una pestaña de producto, dentro de la cual se renderizaría la lista/tabla de combinaciones real.
-   **`mycombtabfree/views/templates/hook/table.tpl`**

    -   **Alcance:** Hook del Front-office.
    -   **Propósito:** Esta es la plantilla principal responsable de renderizar la lista o tabla real de combinaciones de productos en el front-office. Itera a través de las combinaciones disponibles para un producto dado y muestra cada una según la configuración del módulo (por ejemplo, mostrando imagen, referencia, precio, entrada de cantidad, botón de añadir al carrito).
    -   **Lógica:** Contiene bucles Smarty (`{foreach}`) para iterar sobre el array `$combinations`, declaraciones condicionales (`{if}`) para mostrar elementos basados en la configuración del módulo, y variables como `$combination.id_product_attribute`, `$combination.name`, `$combination.price`, etc.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de la Base de Datos**:

    -   Este módulo no crea ninguna tabla SQL personalizada.
    -   Almacena su configuración en la tabla `ps_configuration` de PrestaShop. Las claves de configuración suelen seguir un patrón como `MYCOMBTABFREE_SETTING_NAME`.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para registrar activos CSS (`mycombtabfree.css`) y JavaScript (`atc.js`) para el front-office. |
| `displayProductButtons` | Cerca del botón "Añadir al carrito" en la página del producto. | Un hook común para mostrar la lista de combinaciones directamente debajo de los detalles del producto. |
| `displayProductExtraContent` | Dentro del área de pestañas del producto en la página del producto. | Permite que la lista de combinaciones aparezca en su propia pestaña dedicada. |
| `displayFooterProduct` | En la parte inferior del contenido de la página del producto. | Otra posible ubicación para la lista de combinaciones, a menudo menos prominente. |
| `actionFrontControllerSetMedia` | Antes de que el controlador frontal renderice su salida. | Se utiliza para añadir archivos CSS y JS específicos del módulo a la página. |
| `moduleRoutes` | Durante la inicialización de la reescritura de URL. | (No utilizado explícitamente por este módulo, pero un hook común para módulos con URL personalizadas). |

## 5. Soporte Oficial y Actualizaciones

Para obtener actualizaciones oficiales, correcciones de errores y soporte técnico dedicado para el módulo "Combinations List Free", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Asegúrate de descargar la última versión compatible con tu instalación de PrestaShop desde tu historial de pedidos.

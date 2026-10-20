---
title: "Bloque de categorías con contador - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Bloque de categorías con contador' de MyPresta.eu."
sidebar:
  label: "Bloque de categorías con contador - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Block categories with counter en MyPresta.eu](https://mypresta.eu/modules/front-office-features/block-categories-with-counter.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/block-categories-with-counter/)
>
> ---


# Bloque de categorías con contador

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se necesitan configuraciones de servidor especiales más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

El módulo "Bloque de categorías con contador" ofrece una configuración sencilla, centrada principalmente en habilitar o deshabilitar su funcionalidad principal.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" para el módulo "Bloque de categorías con contador", accederá a su pantalla de configuración principal.

#### **Mostrar contador de productos**

-   **Qué hace este ajuste:** Este es el interruptor principal que controla si el recuento de productos se muestra junto a cada nombre de categoría en el bloque.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* El módulo buscará y mostrará el número de productos activos para cada categoría en el bloque de categorías, como "Electrónica (125)". Esta es la característica principal del módulo.
    -   *Cuando está deshabilitado (NO):* El módulo se comportará como un bloque de categorías estándar, mostrando solo los nombres de las categorías sin ningún recuento de productos. El módulo seguirá mostrando el árbol de categorías, pero la característica única del contador estará inactiva.
-   **Valor recomendado:** **SÍ**. Para utilizar el principal beneficio del módulo, debe habilitar este ajuste.
-   **Escenario/ejemplo para el comerciante:** Si desea que sus clientes vean rápidamente qué categorías son populares o están bien surtidas, habilítelo. Si prefiere una lista de categorías minimalista sin números, puede deshabilitarlo, aunque esto anularía el propósito de instalar este módulo específico.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración principal | Mostrar contador de productos | SÍ | Controla si el recuento de productos se muestra junto a los nombres de las categorías. Habilitarlo activa la función principal del módulo. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: Los recuentos de productos no aparecen o parecen incorrectos.**
R:

1.  **Verifique la configuración del módulo:** Vaya a **Módulos > Gestor de módulos**, busque "Bloque de categorías con contador", haga clic en "Configurar" y asegúrese de que "Mostrar contador de productos" esté configurado en **SÍ**.
2.  **Borre la caché de PrestaShop:** Navegue a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, el contenido antiguo en caché impide que los cambios aparezcan inmediatamente.
3.  **Estado del producto:** Asegúrese de que los productos que espera que se cuenten estén "activos" y "disponibles para pedido" en la configuración de su producto. El módulo solo cuenta los productos activos y visibles.
4.  **Asociación de categorías:** Verifique que los productos estén correctamente asociados con sus respectivas categorías.

**P: El bloque de categorías se ve extraño o no se ajusta a mi tema.**
R: El módulo hereda el estilo de su tema activo de PrestaShop.

1.  **Compatibilidad del tema:** Aunque el módulo es compatible con las versiones de PrestaShop, los diseños de temas específicos a veces pueden causar pequeñas desalineaciones visuales.
2.  **CSS personalizado:** Si tiene un tema personalizado o necesidades de estilo específicas, es posible que deba agregar reglas CSS personalizadas al archivo `custom.css` de su tema (o equivalente) para ajustar la apariencia del bloque de categorías y el contador. Un desarrollador web puede ayudarle con esto.

**P: ¿Puedo cambiar la posición del bloque de categorías?**
R: Sí, esta es una característica estándar de PrestaShop.

1.  Vaya a **Diseño > Posiciones** (o **Diseño > Tema y logotipo > Posiciones** en versiones anteriores).
2.  Busque el `hook` donde se muestra actualmente el módulo "Bloque de categorías con contador" (por ejemplo, `displayLeftColumn`, `displayRightColumn`).
3.  Puede arrastrar y soltar el módulo para reordenar su posición dentro de ese `hook`, o usar el botón "Trasplantar un módulo" para moverlo a un `hook` completamente diferente.

**P: ¿Este módulo ralentiza mi tienda?**
R: El módulo está diseñado para ser eficiente. Consulta la base de datos para los recuentos de productos, lo cual es una operación estándar. Para tiendas muy grandes con decenas de miles de productos y categorías, podría haber un impacto mínimo, pero para la mayoría de las tiendas, debería ser insignificante. Asegúrese de que su servidor cumpla con las especificaciones recomendadas de PrestaShop para un rendimiento óptimo.

**P: ¿Cómo traduzco el módulo si mi tienda es multilingüe?**
R: Este módulo muestra principalmente nombres de categorías y números, que ya son manejados por el sistema de traducción central de PrestaShop para las categorías. Si el módulo en sí tuviera alguna cadena de texto específica (por ejemplo, un título para el bloque), las traduciría a través de **Internacional > Traducciones > Traducciones de módulos**. Sin embargo, para este módulo específico, la mayor parte del contenido es dinámico de sus categorías.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Bloque de categorías con contador", destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Resumen de la arquitectura

El módulo "Bloque de categorías con contador" es un módulo ligero de PrestaShop de un solo archivo (`block-categories-with-counter.php`). Extiende la clase `Module` principal y utiliza principalmente el sistema de `hooks` de PrestaShop para integrar su funcionalidad. Su lógica central gira en torno a anular o extender el comportamiento predeterminado del bloque de categorías para inyectar recuentos de productos. Aprovecha los ObjectModels `Category` y `Product` de PrestaShop para recuperar datos.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la configuración se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** introduce ninguna clase u ObjectModels personalizados en el directorio `classes/`. Utiliza directamente los ObjectModels `Category` y `Product` principales de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo **no** incluye ningún archivo JavaScript personalizado. Su funcionalidad se renderiza puramente en el lado del servidor.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo **no** incluye ningún archivo CSS personalizado. Se basa completamente en el estilo proporcionado por el tema activo de PrestaShop para el bloque de categorías predeterminado.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

Este módulo **no** contiene archivos de plantilla personalizados en `views/templates/`. Probablemente anula o modifica la salida de la plantilla del módulo `blockcategories` predeterminado o renderiza directamente su contenido dentro de los métodos `hook`. Dada su simplicidad, es muy probable que utilice el método `display` para renderizar contenido directamente, o podría estar diseñado para reemplazar la salida del módulo `blockcategories` predeterminado al engancharse en las mismas posiciones y proporcionar su propio HTML.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**: Este módulo **no** crea ninguna tabla de base de datos personalizada. Almacena su configuración (específicamente, el ajuste `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT`) en la tabla estándar `ps_configuration`.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `install()` | Durante la instalación del módulo. | Registra el módulo en varios hooks de visualización (`displayCategories` en PrestaShop 1.6, `displayLeftColumn`, `displayRightColumn`, `displayHome`, `displayFooter`, `displayHeader`). Establece el valor de configuración predeterminado para `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT` en `true`. |
| `uninstall()` | Durante la desinstalación del módulo. | Elimina el valor de configuración `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT`. Anula el registro del módulo de todos los hooks registrados. |
| `getContent()` | Cuando se accede a la página de configuración del módulo en el Back Office. | Maneja el formulario de configuración del Back Office. Procesa los envíos del formulario (guardando el ajuste `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT`). Muestra el formulario de configuración al comerciante. |
| `hookDisplayLeftColumn($params)` / `hookDisplayRightColumn($params)` / etc. | Cuando PrestaShop renderiza la columna izquierda/derecha/etc. en el Front Office. | Estas funciones son responsables de renderizar el bloque de categorías en las respectivas posiciones del front-office. Recuperan el árbol de categorías utilizando `Category::getNestedCategories()`. Si `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT` está habilitado, iteran a través de las categorías y obtienen el recuento de productos para cada una utilizando `Category::getProducts($id_category, null, null, null, null, null, true)`. Los datos (árbol de categorías con recuentos) se pasan luego a una plantilla Smarty para su renderizado. |

### 4.8 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:
    -   `ps_configuration`: Almacena la configuración principal del módulo:
        -   `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT`: Booleano (0 o 1) que indica si se deben mostrar los recuentos de productos.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Propósito técnico |
| --- | --- |
| `displayLeftColumn` | Renderiza el bloque de categorías en la columna izquierda. |
| `displayRightColumn` | Renderiza el bloque de categorías en la columna derecha. |
| `displayHome` | Renderiza el bloque de categorías en la página de inicio. |
| `displayFooter` | Renderiza el bloque de categorías en el pie de página. |
| `displayHeader` | Renderiza el bloque de categorías en el encabezado. |

El módulo genera dinámicamente el HTML para el árbol de categorías y los recuentos de productos dentro de estos métodos de `hook`, típicamente usando una función recursiva para construir la estructura de lista anidada.

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, soporte oficial y descargar nuevas versiones del módulo "Bloque de categorías con contador", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.

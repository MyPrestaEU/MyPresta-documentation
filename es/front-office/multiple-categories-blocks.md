---
title: "Bloques de Múltiples Categorías - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Bloques de Múltiples Categorías de MyPresta.eu."
sidebar:
  label: "Bloques de Múltiples Categorías - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Multiple Categories Blocks en MyPresta.eu](https://mypresta.eu/modules/front-office-features/multiple-categories-blocks.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/multiple-categories-blocks/)
>
> ---


# Bloques de Múltiples Categorías

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Bloques de Múltiples Categorías)

Esta es la pantalla de configuración principal donde crearás y gestionarás todos tus bloques de categorías personalizados.

Al entrar en la página de configuración, verás una lista de los bloques de categorías existentes (si los hay) y opciones para añadir nuevos.

#### **Añadir / Editar un Bloque de Categorías**

Cuando hagas clic en "Añadir nuevo bloque" o edites uno existente, se te presentarán los siguientes ajustes:

-   **Nombre del Bloque:**

    -   **Qué hace este ajuste:** Es un nombre interno para tu referencia en el Back Office. Te ayuda a identificar diferentes bloques.
    -   **Efecto de cambiar este ajuste:** Solo afecta cómo ves el bloque en el panel de administración. No es visible para los clientes.
    -   **Valor recomendado:** Un nombre descriptivo (por ejemplo, "Categorías de Electrónica de la Página de Inicio", "Ropa de la Columna Izquierda").
    -   **Escenario / ejemplo de comerciante:** Si tienes un bloque para "Moda Masculina" en la columna izquierda, nómbralo "Columna Izquierda - Moda Masculina".
-   **Mostrar Título del Bloque:**

    -   **Qué hace este ajuste:** Determina si se muestra un título (por ejemplo, "Categorías") encima de la lista de categorías en el front office.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* Aparecerá un título encima del bloque de categorías. Puedes definir este título en el campo "Título del Bloque".
        -   *Cuando está deshabilitado (No):* No se mostrará ningún título, solo la lista de categorías.
    -   **Valor recomendado:** "Sí" para la mayoría de los bloques, ya que proporciona contexto al cliente.
    -   **Escenario / ejemplo de comerciante:** Si quieres que tu bloque simplemente se integre en el diseño sin un título explícito, configúralo en "No".
-   **Título del Bloque:** (Aparece solo si "Mostrar Título del Bloque" es Sí)

    -   **Qué hace este ajuste:** El texto real que se mostrará como título del bloque en el front office. Es multilingüe.
    -   **Efecto de cambiar este ajuste:** Cambia el título visible para los clientes.
    -   **Valor recomendado:** Un título claro y conciso (por ejemplo, "Comprar por Categoría", "Nuestros Productos", "Departamentos").
    -   **Escenario / ejemplo de comerciante:** Para un bloque que muestra solo categorías de "Electrónica", podrías establecer el título en "Electrónica".
-   **Hook para mostrar el bloque:**

    -   **Qué hace este ajuste:** Selecciona dónde aparecerá este bloque de categorías en tu tienda. Los hooks son puntos de visualización específicos en tu tema de PrestaShop.
    -   **Efecto de cambiar este ajuste:** Determina la ubicación física del bloque en tu sitio web.
    -   **Valor recomendado:** Depende de tu diseño. Las opciones comunes son `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayHome`.
    -   **Escenario / ejemplo de comerciante:** Para mostrar un bloque en la barra lateral izquierda, selecciona `displayLeftColumn`. Para mostrarlo en el pie de página, selecciona `displayFooter`.
-   **Categoría Raíz:**

    -   **Qué hace este ajuste:** Este es el punto de partida (el "padre") para las categorías mostradas en este bloque específico. Solo se mostrarán esta categoría y sus subcategorías.
    -   **Efecto de cambiar este ajuste:**
        -   *Seleccionar "Inicio":* El bloque mostrará todas las categorías comenzando desde la parte superior de tu árbol de categorías.
        -   *Seleccionar una categoría específica (por ejemplo, "Electrónica"):* El bloque solo mostrará "Electrónica" y todas sus subcategorías.
    -   **Valor recomendado:** Elige la categoría de nivel más alto que defina el alcance de este bloque.
    -   **Escenario / ejemplo de comerciante:** Si quieres un bloque específicamente para "Ropa", selecciona tu categoría "Ropa" aquí.
-   **Profundidad Máxima:**

    -   **Qué hace este ajuste:** Controla cuántos niveles de subcategorías se muestran dentro de este bloque, comenzando desde la Categoría Raíz.
    -   **Efecto de cambiar este ajuste:**
        -   *Configurar en 1:* Solo se mostrará la Categoría Raíz (si "Mostrar Categoría Raíz" es Sí).
        -   *Configurar en 2:* Se mostrarán la Categoría Raíz y sus subcategorías inmediatas.
        -   *Configurar en 0 (o vacío):* Se mostrarán todas las subcategorías, independientemente de la profundidad.
    -   **Valor recomendado:** 2 o 3 para la mayoría de los bloques de columna para mantenerlos manejables. 0 para los bloques de pie de página si quieres un mapa del sitio completo.
    -   **Escenario / ejemplo de comerciante:** Si tu categoría "Electrónica" tiene subcategorías como "Cámaras" y "Portátiles", y "Cámaras" tiene "DSLR" y "Sin espejo", configurar la profundidad en 2 mostraría "Electrónica > Cámaras, Portátiles". Configurar en 3 mostraría "Electrónica > Cámaras > DSLR, Sin espejo, Portátiles".
-   **Dinámico (abrir árbol de categorías actual):**

    -   **Qué hace este ajuste:** Cuando un cliente navega a una página de categoría, esta opción determina si el bloque de categorías se expande automáticamente para mostrar la categoría actual y sus subcategorías.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* Si un cliente está en la página de "DSLR", el bloque de categorías expandirá automáticamente "Electrónica > Cámaras > DSLR" para mostrar la ruta.
        -   *Cuando está deshabilitado (No):* El bloque de categorías permanecerá en su estado predeterminado contraído, independientemente de la página actual.
    -   **Valor recomendado:** "Sí" para una mejor experiencia de usuario, ya que ayuda a los clientes a comprender su ubicación actual en el árbol de categorías.
    -   **Escenario / ejemplo de comerciante:** Esto es particularmente útil en las columnas laterales para mantener la navegación relevante al contexto de navegación actual del usuario.
-   **Mostrar Categoría Raíz:**

    -   **Qué hace este ajuste:** Controla si la "Categoría Raíz" en sí (la que seleccionaste anteriormente) se muestra como el elemento superior en el bloque.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* La Categoría Raíz será el primer elemento clicable en el bloque.
        -   *Cuando está deshabilitado (No):* El bloque comenzará a mostrarse desde las subcategorías inmediatas de la Categoría Raíz.
    -   **Valor recomendado:** "Sí" si la Categoría Raíz es una categoría amplia como "Comprar por Departamento". "No" si la Categoría Raíz es solo una agrupación lógica y quieres empezar directamente con sus subcategorías (por ejemplo, un bloque de "Marcas" donde "Marcas" en sí no es una categoría de producto).
    -   **Escenario / ejemplo de comerciante:** Si tu Categoría Raíz es "Ropa de Hombre" y quieres que sea el enlace superior, configúralo en "Sí". Si quieres que el bloque comience directamente con "Camisas", "Pantalones", etc., configúralo en "No".
-   **Mostrar Número de Productos:**

    -   **Qué hace este ajuste:** Muestra el recuento de productos disponibles dentro de cada categoría junto a su nombre en el bloque.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* Las categorías aparecerán como "Nombre de la Categoría (X)".
        -   *Cuando está deshabilitado (No):* Solo se mostrará el nombre de la categoría.
    -   **Valor recomendado:** "Sí" puede ser útil para que los clientes evalúen el tamaño de una categoría, pero "No" puede llevar a un aspecto más limpio. Prueba ambos para ver qué se adapta a tu diseño.
    -   **Escenario / ejemplo de comerciante:** Si quieres mostrar "Camisetas (125)" junto al nombre de la categoría, habilita esta opción.
-   **Mostrar Categorías sin productos:**

    -   **Qué hace este ajuste:** Determina si las categorías que actualmente no tienen productos asignados se siguen mostrando en el bloque.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* Las categorías vacías seguirán apareciendo.
        -   *Cuando está deshabilitado (No):* Las categorías vacías se ocultarán del bloque.
    -   **Valor recomendado:** "No" para evitar callejones sin salida para los clientes y mantener tu navegación limpia. Solo habilita "Sí" si tienes una razón específica para mostrar categorías próximas.
    -   **Escenario / ejemplo de comerciante:** Si estás desarrollando una nueva línea de productos y has creado categorías pero aún no has añadido productos, podrías habilitar temporalmente "Sí" para pruebas internas, pero generalmente "No" para tiendas en vivo.
-   **Ordenar por:**

    -   **Qué hace este ajuste:** Define el orden de clasificación de las categorías dentro del bloque.
    -   **Efecto de cambiar este ajuste:** Cambia la secuencia en la que se listan las categorías.
    -   **Valor recomendado:** "Posición" (orden predeterminado de PrestaShop) o "Nombre" (alfabético).
    -   **Escenario / ejemplo de comerciante:** Si quieres que tus categorías aparezcan alfabéticamente, selecciona "Nombre". Si prefieres ordenarlas manualmente en la sección de Categorías de PrestaShop, selecciona "Posición".
-   **Orden de Clasificación:**

    -   **Qué hace este ajuste:** Especifica el orden ascendente o descendente para el ajuste "Ordenar por".
    -   **Efecto de cambiar este ajuste:**
        -   *ASC:* Ascendente (A-Z, 1-9).
        -   *DESC:* Descendente (Z-A, 9-1).
    -   **Valor recomendado:** "ASC" para la mayoría de los casos.
    -   **Escenario / ejemplo de comerciante:** Si ordenaste por "Nombre" y quieres A-Z, selecciona "ASC".

#### **Gestión de Bloques Existentes**

Después de crear bloques, verás una lista con opciones para:

-   **Editar:** Modificar los ajustes de un bloque existente.
-   **Eliminar:** Eliminar un bloque de tu tienda.
-   **Alternar Estado (Habilitar/Deshabilitar):** Activar o desactivar rápidamente un bloque sin eliminar su configuración.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | **Nombre del Bloque** | Descriptivo | Identificador interno para el bloque. |
| | **Mostrar Título del Bloque** | Sí | Muestra/oculta el título del bloque a los clientes. |
| | **Título del Bloque** | "Categorías" (ejemplo) | El título visible para el bloque (multilingüe). |
| | **Hook para mostrar el bloque** | `displayLeftColumn` | Determina dónde aparece el bloque en tu tema. |
| | **Categoría Raíz** | Inicio | Establece el punto de partida para las categorías en este bloque. |
| | **Profundidad Máxima** | 0 (Todas) | Limita el número de niveles de subcategorías mostrados. |
| | **Dinámico (abrir árbol de categorías actual)** | Sí | Expande automáticamente el árbol a la categoría actual. |
| | **Mostrar Categoría Raíz** | Sí | Muestra/oculta la Categoría Raíz seleccionada. |
| | **Mostrar Número de Productos** | No | Muestra/oculta el recuento de productos junto a los nombres de las categorías. |
| | **Mostrar Categorías sin productos** | No | Muestra/oculta las categorías que no tienen productos. |
| | **Ordenar por** | Posición | Ordena las categorías por posición o nombre. |
| | **Orden de Clasificación** | ASC | Ordena las categorías en orden ascendente o descendente. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mi nuevo bloque de categorías no aparece en el front office.**
R1:

-   **Verifica el Hook:** Asegúrate de haber seleccionado el "Hook para mostrar el bloque" correcto en la configuración del módulo.
-   **Posición del Módulo:** Ve a **Diseño > Posiciones** (o **Módulos > Posiciones** en versiones anteriores). Busca `Multiple Categories Blocks` y asegúrate de que esté enganchado a la posición que seleccionaste y que no esté deshabilitado. Es posible que necesites mover su posición hacia arriba o hacia abajo si otros módulos se están superponiendo.
-   **Estado del Módulo:** En la configuración del módulo, asegúrate de que el bloque esté "Habilitado" (marca de verificación verde).
-   **Caché:** Borra la caché de tu PrestaShop (**Parámetros Avanzados > Rendimiento > Borrar caché**).

**P2: Las categorías de mi bloque no se expanden o no se muestran correctamente.**
R2:

-   **Categoría Raíz y Profundidad Máxima:** Vuelve a verificar la configuración de tu "Categoría Raíz" y "Profundidad Máxima". Si la Profundidad Máxima es demasiado baja, las subcategorías no aparecerán. Si la Categoría Raíz es incorrecta, verás el árbol equivocado.
-   **Opción Dinámica:** Si esperas que el árbol se expanda automáticamente al navegar, asegúrate de que "Dinámico (abrir árbol de categorías actual)" esté configurado en "Sí".
-   **Categorías sin productos:** Si faltan categorías, verifica "Mostrar Categorías sin productos". Si está en "No", las categorías sin productos se ocultarán.

**P3: El estilo del bloque de categorías no coincide con mi tema.**
R3:

-   El módulo intenta heredar los estilos de tu tema activo de PrestaShop. Sin embargo, los temas personalizados pueden requerir pequeños ajustes de CSS.
-   A menudo puedes anular el CSS predeterminado del módulo añadiendo reglas al archivo `custom.css` o `theme.css` de tu tema. (Consulta la Sección 7.5 para obtener detalles de desarrollador sobre el CSS del módulo).
-   Para PrestaShop 1.7/8/9, asegúrate de que estás utilizando el archivo `multicatblock-prestashop17.css` si tu tema lo requiere (esto lo gestiona automáticamente el módulo).

**P4: ¿Cómo traduzco el título del bloque a otros idiomas?**
R4:

-   Al editar un bloque, el campo "Título del Bloque" tendrá banderas de idioma junto a él. Haz clic en cada bandera para introducir el título para ese idioma específico.
-   Guarda tus cambios después de introducir todas las traducciones.

**P5: ¿Por qué faltan algunas categorías del bloque, aunque tienen productos?**
R5:

-   **Alcance de la Categoría Raíz:** Asegúrate de que las categorías que faltan sean realmente descendientes (subcategorías) de la "Categoría Raíz" que seleccionaste para ese bloque específico. Si están fuera de esa rama, no aparecerán.
-   **Estado de la Categoría:** Verifica en **Catálogo > Categorías** que las categorías que faltan estén "Habilitadas" y "Mostradas" (visibles).
-   **Asociación de Productos:** Vuelve a verificar que los productos estén correctamente asociados con las categorías en cuestión.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo Bloques de Múltiples Categorías (`multicatblocks`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para su funcionalidad central y configuración. Se integra en el front-office a través de varios hooks de visualización y utiliza plantillas Smarty para la renderización. El módulo almacena su configuración en la tabla `ps_configuration`, lo que permite definir múltiples bloques de categorías distintos. Utiliza una lógica de renderización de árbol personalizada para construir la navegación de categorías.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores dedicados para el front-office o el back-office. Toda la lógica de configuración y renderización del front-office se maneja dentro del archivo principal del módulo `index.php` y sus plantillas y hooks asociados.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no define clases `ObjectModel` personalizadas. Toda la manipulación de datos para las categorías se basa en la clase `Category` nativa de PrestaShop.

La lógica principal reside en `multicatblocks/index.php`:

-   **Clase `Multicatblocks`:** Extiende `Module`.
    -   **`__construct()`:** Inicializa los detalles del módulo, configura las pestañas y registra los hooks.
    -   **`install()`:** Registra los hooks necesarios (`displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayHome`, `displayProductButtons` - aunque este último podría ser para uso heredado/interno ya que no está expuesto en la configuración), crea entradas de configuración predeterminadas.
    -   **`uninstall()`:** Limpia las entradas de configuración.
    -   **`getContent()`:** Maneja el envío y la visualización del formulario de configuración del Back Office. Gestiona la creación, edición y eliminación de bloques de categorías, almacenando sus ajustes en `Configuration::updateValue()`.
    -   **`hookDisplayHeader()`:** Inyecta activos CSS y JavaScript en la sección `<head>` del front office.
    -   **`hookDisplayLeftColumn()`, `hookDisplayRightColumn()`, `hookDisplayFooter()`, `hookDisplayHome()`, `hookDisplayProductButtons()`:** Estos métodos son responsables de recuperar los bloques configurados para sus respectivos hooks, obtener datos de categorías, preparar variables Smarty y renderizar la plantilla `multicatblock.tpl` o `multicatblock-footer.tpl`.
    -   **`getCategoryTree()`:** Un método interno crucial que recupera y estructura recursivamente los datos de las categorías basándose en la configuración del bloque (categoría raíz, profundidad máxima, recuento de productos, etc.).

### 4.4 Activos JavaScript (`views/js/`)

-   **`multicatblocks/js/script.js`**:

    -   **Alcance:** Front-office.
    -   **Propósito:** Maneja el comportamiento interactivo principal del árbol de categorías, como expandir/contraer subcategorías. Probablemente enlaza eventos de clic a enlaces de categorías o iconos de expandir/contraer.
    -   **Detalles:** Este script es responsable del comportamiento "dinámico", asegurando que cuando se hace clic en una categoría, sus subcategorías se revelen u oculten, y potencialmente resaltando la ruta de la categoría activa.
-   **`multicatblocks/js/tree.js`**:

    -   **Alcance:** Front-office.
    -   **Propósito:** Probablemente una dependencia o una versión anterior de la funcionalidad del árbol, o maneja específicamente el estado inicial y la renderización de la estructura del árbol.
    -   **Detalles:** Podría contener lógica para inicializar el árbol, manejar llamadas AJAX para datos de categorías (si aplica, aunque el módulo parece renderizar el árbol completo al cargar la página), o gestionar el estado del árbol.
-   **`multicatblocks/lib/searchTool/views/js/autocomplete.js`**:

    -   **Alcance:** Back-office (configuración de administración).
    -   **Propósito:** Proporciona una funcionalidad de autocompletado para seleccionar categorías en el formulario de configuración del módulo, específicamente para el ajuste "Categoría Raíz".
    -   **Detalles:** Se enlaza a un campo de entrada, realiza solicitudes AJAX a un controlador de administración de PrestaShop (probablemente `AdminCategories` o uno personalizado si está presente, aunque no se lista ninguno) para buscar categorías y muestra sugerencias.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   **`multicatblocks/css.css`**:

    -   **Alcance:** Front-office.
    -   **Propósito:** Estilo general para los bloques de categorías.
    -   **Detalles:** Contiene reglas básicas para elementos de lista, enlaces y potencialmente iconos de expandir/contraer. Los selectores clave pueden incluir `.multicatblock`, `.multicatblock_list`, `.multicatblock_item`.
-   **`multicatblocks/lib/searchTool/views/css/autocomplete.css`**:

    -   **Alcance:** Back-office (configuración de administración).
    -   **Propósito:** Estilos para la entrada de búsqueda de autocompletado y su menú desplegable de sugerencias.
    -   **Detalles:** Asegura que la herramienta de búsqueda de categorías en el panel de administración sea visualmente consistente y fácil de usar.
-   **`multicatblocks/multicatblock-prestashop17.css`**:

    -   **Alcance:** Front-office.
    -   **Propósito:** Anulaciones específicas o estilos adicionales adaptados para temas de PrestaShop 1.7.x, 8.x y 9.x (por ejemplo, el tema Classic).
    -   **Detalles:** Aborda posibles inconsistencias de diseño o estilo que puedan surgir entre versiones anteriores de PrestaShop y las nuevas estructuras de temas. Esto se carga condicionalmente según la versión de PS.
-   **`multicatblocks/multicatblock.css`**:

    -   **Alcance:** Front-office.
    -   **Propósito:** Estilo principal para los bloques de categorías, probablemente para versiones anteriores de PrestaShop (1.5.x, 1.6.x) o como respaldo.
    -   **Detalles:** Similar a `css.css`, pero podría contener reglas más específicas para estructuras de temas antiguas.
-   **`multicatblocks/views/css/mcb-admin.css`**:

    -   **Alcance:** Back-office (configuración de administración).
    -   **Propósito:** Estilo para la página de configuración del módulo en el Back Office de PrestaShop.
    -   **Detalles:** Asegura que el formulario de configuración del módulo, la lista de bloques y otros elementos de la interfaz de usuario de administración estén bien presentados y sean consistentes con el tema de administración de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de Hook (`views/templates/hook/` - aunque los archivos están directamente en `multicatblocks/`):**

    -   **`multicatblocks/multicatblock.tpl`**:
        -   **Enganchado en:** `displayLeftColumn`, `displayRightColumn`, `displayHome`, `displayProductButtons`.
        -   **Salidas:** La estructura principal del bloque de categorías, incluyendo el título (si está habilitado) y el árbol de categorías recursivo generado por `category-tree-branch.tpl`.
    -   **`multicatblocks/multicatblock-footer.tpl`**:
        -   **Enganchado en:** `displayFooter`.
        -   **Salidas:** Una variación del bloque de categorías específicamente para el pie de página, potencialmente con diferentes estilos o elementos estructurales. También utiliza `category-tree-branch-footer.tpl`.
    -   **`multicatblocks/category-tree-branch.tpl`**:
        -   **Enganchado en:** Incluido por `multicatblock.tpl`.
        -   **Salidas:** Renderiza recursivamente una única rama del árbol de categorías. Itera a través de subcategorías, maneja límites de profundidad y muestra recuentos de productos.
    -   **`multicatblocks/category-tree-branch-footer.tpl`**:
        -   **Enganchado en:** Incluido por `multicatblock-footer.tpl`.
        -   **Salidas:** Similar a `category-tree-branch.tpl` pero adaptado para la estructura del bloque de pie de página.
-   **Plantillas de Administración (`views/templates/admin/` - aunque `shell.tpl` está en `multicatblocks/views/templates/admin/`):**

    -   **`multicatblocks/views/templates/admin/shell.tpl`**:
        -   **Propósito:** La plantilla principal para la página de configuración del módulo en el Back Office.
        -   **Salidas:** El formulario para añadir/editar bloques, la lista de bloques existentes y potencialmente incluye otros elementos específicos de administración.
-   **Plantillas de Biblioteca:**

    -   **`multicatblocks/lib/searchTool/views/scripts.tpl`**:
        -   **Propósito:** Probablemente incluye JavaScript necesario para la herramienta de búsqueda de autocompletado utilizada en la configuración de administración.
        -   **Salidas:** Etiquetas `<script>` o JavaScript en línea para la funcionalidad de autocompletado.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El módulo no crea tablas SQL personalizadas.
    -   Toda la configuración para cada bloque de categorías se almacena en la tabla `ps_configuration`. Los ajustes de cada bloque se serializan y se almacenan bajo una clave de configuración única (por ejemplo, `MULTICATBLOCKS_BLOCKS`).
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Inyecta los archivos CSS y JavaScript del módulo. |
| `displayLeftColumn` | En la barra lateral izquierda del front office. | Renderiza un bloque de categorías configurado en la columna izquierda. |
| `displayRightColumn` | En la barra lateral derecha del front office. | Renderiza un bloque de categorías configurado en la columna derecha. |
| `displayFooter` | En la sección del pie de página del front office. | Renderiza un bloque de categorías configurado en el pie de página. |
| `displayHome` | En la página de inicio (si el tema soporta el hook `displayHome`). | Renderiza un bloque de categorías configurado en la página de inicio. |
| `displayProductButtons` | En la página del producto, cerca del botón de añadir al carrito. | Renderiza un bloque de categorías configurado en las páginas de productos (menos común para este módulo, pero disponible). |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Bloques de Múltiples Categorías", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema técnico o pregunta que puedas tener.

---
title: "Menú desplegable vertical de categorías - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Menú desplegable vertical de categorías' de MyPresta.eu."
sidebar:
  label: "Menú desplegable vertical de categorías - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Vertical dropdown categories menu en MyPresta.eu](https://mypresta.eu/modules/front-office-features/vertical-dropdown-categories-menu.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/vertical-dropdown-categories-menu/)
>
> ---


# Menú desplegable vertical de categorías

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Menú desplegable vertical de categorías" en el Gestor de módulos. Esto le llevará a su pantalla de configuración principal.

La página de configuración del módulo proporciona ajustes estándar para controlar su comportamiento y apariencia.

-   **Qué hace este ajuste:** Esta sección suele contener ajustes generales para el módulo, como habilitarlo/deshabilitarlo, elegir dónde aparece o las opciones básicas de visualización. Aunque no se detallan ajustes específicos en el dossier, las opciones comunes para un módulo de este tipo incluyen:

    -   **Habilitar/Deshabilitar Módulo**: Un simple interruptor para activar o desactivar el módulo sin desinstalarlo.
    -   **Mostrar Categoría Raíz**: Elija si desea mostrar la categoría principal "Inicio" o "Raíz" en el menú.
    -   **Profundidad Máxima**: Limite cuántos niveles de subcategorías se muestran en el desplegable.
    -   **Selección de Hook**: Elija a qué hooks de visualización debe adjuntarse el módulo (por ejemplo, `displayLeftColumn`, `displayRightColumn`).
    -   **Configuración de Caché**: Opciones para habilitar o deshabilitar el almacenamiento en caché de la salida del módulo para mejorar el rendimiento.
-   **Efecto de cambiar este ajuste:**

    -   *Cuando está habilitado:* El módulo estará activo y mostrará el menú de categorías vertical en su front office de acuerdo con otros ajustes.
    -   *Cuando está deshabilitado:* El módulo no aparecerá en su tienda, pero su configuración se guardará.
    -   *Elegir un hook (por ejemplo, `displayLeftColumn`):* El bloque del menú vertical aparecerá en la columna izquierda de su tienda.
    -   *Limitar la profundidad:* Solo se mostrarán las categorías hasta el nivel especificado, simplificando el menú para los clientes.
-   **Valor recomendado:**

    -   **Habilitar Módulo**: SÍ
    -   **Mostrar Categoría Raíz**: NO (normalmente, para empezar directamente con sus categorías de productos principales)
    -   **Profundidad Máxima**: 3 (un buen equilibrio para la mayoría de las tiendas, evitando menús excesivamente complejos)
    -   **Selección de Hook**: `displayLeftColumn` o `displayRightColumn` (dependiendo de la preferencia de diseño de su tema).
-   **Escenario/ejemplo de comerciante:**

    -   *Escenario 1 (Simplificación de la navegación):* Tiene una estructura de categorías muy profunda (por ejemplo, 5-6 niveles). Podría establecer "Profundidad Máxima" en 3 para asegurarse de que los clientes no se sientan abrumados por demasiadas opciones, guiándolos primero a través de las opciones de nivel superior.
    -   *Escenario 2 (Optimización del rendimiento):* Si su tienda experimenta mucho tráfico, habilitar el almacenamiento en caché para la salida del módulo puede acelerar significativamente los tiempos de carga de la página, ya que el menú no necesita ser reconstruido para cada visitante.
    -   *Escenario 3 (Ajuste de diseño):* Su tema se ve mejor con la navegación en el lado derecho. Seleccionaría `displayRightColumn` en la configuración del hook para mover el bloque del menú en consecuencia.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Habilitar/Deshabilitar Módulo | Habilitado | Controla si el módulo está activo en su tienda. |
| Página de configuración del módulo | Mostrar Categoría Raíz | No | Determina si se muestra la categoría "Inicio" de nivel superior. |
| Página de configuración del módulo | Profundidad Máxima | 3 | Limita el número de niveles de subcategorías mostrados. |
| Página de configuración del módulo | Selección de Hook | `displayLeftColumn` | Especifica dónde aparece el bloque del menú (por ejemplo, columna izquierda o derecha). |
| Página de configuración del módulo | Caché | Habilitado | Mejora el rendimiento almacenando el HTML del menú generado. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: El menú no aparece en mi tienda después de la instalación.**
**R1:**

1.  **Verificar el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que el módulo "Menú desplegable vertical de categorías" esté instalado y habilitado.
2.  **Verificar la asignación del hook:** En la configuración del módulo, asegúrese de que esté asignado a un hook activo (por ejemplo, `displayLeftColumn`, `displayRightColumn`). Algunos temas pueden no mostrar todos los hooks por defecto, o es posible que deba ajustar la configuración de diseño de su tema.
3.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty"). A veces, el contenido antiguo en caché impide que aparezcan nuevos módulos.
4.  **Compatibilidad del tema:** Si está utilizando un tema altamente personalizado, podría anular la renderización predeterminada de los hooks de PrestaShop. Póngase en contacto con el desarrollador de su tema o con un experto en PrestaShop.

**P2: El efecto desplegable no funciona o se ve roto.**
**R2:**

1.  **Conflictos de tema:** Otro módulo o el JavaScript/CSS personalizado de su tema podría estar en conflicto con el estilo o la funcionalidad del módulo.
2.  **Borrar caché:** Siempre intente borrar la caché de su PrestaShop (**Parámetros avanzados > Rendimiento**) y la caché de su navegador.
3.  **Inspeccionar con herramientas del navegador:** Utilice las herramientas de desarrollador de su navegador (F12) para buscar errores de JavaScript en la consola o conflictos de CSS. Busque mensajes de error en rojo.
4.  **Reinstalación del módulo:** Intente desinstalar y reinstalar el módulo (después de hacer una copia de seguridad de su configuración si es posible).

**P3: ¿Cómo cambio los colores o las fuentes del menú?**
**R3:** El módulo viene con su propio archivo `blockcategories.css` para el estilo.

1.  **Personalización básica:** Para cambios menores, a menudo puede anular estos estilos en el archivo CSS personalizado de su tema (por ejemplo, `themes/yourtheme/assets/css/custom.css`). Esta es la forma más segura de realizar cambios sin modificar los archivos centrales del módulo.
2.  **Personalización avanzada:** Para cambios más extensos, es posible que deba editar directamente el archivo `blockcategories.css` dentro del directorio `views/css/` del módulo. **Sin embargo, tenga en cuenta que estos cambios se perderán con las actualizaciones del módulo.** Siempre es mejor usar las anulaciones del tema.
3.  **Personalizador de temas de PrestaShop:** Algunos temas ofrecen un "Personalizador de temas" o "Configurador en vivo" que permite cambios básicos de estilo sin tocar el código. Verifique si su tema tiene esta característica.

**P4: Mis categorías no aparecen en el menú.**
**R4:**

1.  **Estado de la categoría:** Asegúrese de que sus categorías estén activas y visibles en su Back Office de PrestaShop (**Catálogo > Categorías**).
2.  **Configuración de la categoría raíz:** Verifique la configuración del módulo para ver si "Mostrar categoría raíz" está habilitado o deshabilitado. Si está deshabilitado y sus categorías son hijos directos de la raíz, es posible que no aparezcan.
3.  **Permisos:** Asegúrese de que las categorías tengan los permisos de grupo adecuados si está utilizando grupos de clientes.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Menú desplegable vertical de categorías" (`verticalblockcategories`) es un módulo estándar de PrestaShop diseñado para mostrar un bloque de navegación de categorías dinámico. Principalmente, aprovecha el sistema de hooks de PrestaShop para renderizar su contenido en varias ubicaciones del front-office. La lógica del módulo está contenida en su archivo PHP principal, que maneja la instalación, desinstalación, registro de hooks y configuración. La presentación visual se gestiona a través de plantillas Smarty y un archivo CSS dedicado. No introduce controladores personalizados ni ObjectModels complejos, centrándose en la renderización eficiente de los datos de categorías existentes.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la lógica se maneja dentro del archivo principal del módulo (`index.php`) y se renderiza a través de hooks.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase u ObjectModels personalizados en un directorio `classes/`. Utiliza directamente las clases `Category` y `Tools` del núcleo de PrestaShop para obtener y procesar los datos de las categorías.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo no contiene ningún archivo JavaScript personalizado. El efecto desplegable se logra típicamente puramente a través de CSS, o se basa en bibliotecas jQuery/JavaScript existentes ya cargadas por PrestaShop o el tema.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`verticalblockcategories/blockcategories.css`**
    -   **Alcance**: Estilo del front-office para el cliente.
    -   **Componentes y contenedores principales de la interfaz de usuario que estiliza**: Esta hoja de estilo es responsable del diseño visual, la apariencia y la animación desplegable del menú de categorías vertical. Se dirige a elementos dentro de la estructura HTML generada por el módulo, como `div#categories_block_left`, `ul.tree`, `li.last`, `a.selected` y `ul.tree li ul`.
    -   **Selectores de clase CSS clave que los desarrolladores pueden anular en su tema**:
        -   `#categories_block_left` (o ID/clase similar para el contenedor del bloque principal)
        -   `.block_content`
        -   `ul.tree` (para la lista principal de categorías)
        -   `ul.tree li` (para elementos de categoría individuales)
        -   `ul.tree li a` (para enlaces de categoría)
        -   `ul.tree li ul` (para desplegables de subcategorías)
        -   `ul.tree li ul li` (para elementos de subcategoría individuales)
        -   `.selected` (para la categoría actualmente activa)
        -   Clases relacionadas con efectos hover y transiciones para el desplegable.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   **`verticalblockcategories/blockcategories.tpl`**: Este es el archivo de plantilla principal renderizado por el módulo cuando se engancha. Típicamente contiene la estructura general del bloque de categorías, incluyendo el título y la lista desordenada principal (`<ul>`) que contendrá el árbol de categorías. Es probable que incluya `category-tree-branch.tpl` recursivamente para construir el menú completo.
        -   **Enganchado en**: `displayLeftColumn`, `displayRightColumn`, `displayHeader`, `displayFooter`, `displayProductExtraContent` (u otros hooks de columna/contenido).
        -   **Salidas**: El bloque HTML principal para el menú de categorías vertical.
    -   **`verticalblockcategories/category-tree-branch.tpl`**: Esta plantilla está diseñada para la renderización recursiva de ramas de categorías individuales (categorías y sus subcategorías). Maneja la visualización de un solo elemento de categoría y, si esa categoría tiene hijos, se llama a sí misma recursivamente para renderizar esos hijos como una lista anidada, creando la estructura de árbol.
        -   **Incluido por**: `blockcategories.tpl` (y potencialmente por sí mismo).
        -   **Salidas**: Un elemento `<li>` para una categoría, que potencialmente contiene un `<ul>` anidado para sus subcategorías.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Se basa completamente en las tablas principales de PrestaShop `ps_category`, `ps_category_lang` y `ps_category_product` para los datos de las categorías. La configuración se almacena en `ps_configuration` utilizando claves con el prefijo `VERTICALBLOCKCATEGORIES_`.
-   **Tabla de hooks registrados**:

    | Nombre del Hook | Momento de Ejecución | Propósito Técnico |
    | --- | --- | --- |
    | `displayHeader` | En la sección `<head>` del HTML. | Potencialmente utilizado para cargar activos CSS/JS, aunque para este módulo, el CSS se registra típicamente a través de `install()` o el propio `hookDisplayHeader`. |
    | `displayLeftColumn` | Renderiza contenido en la columna izquierda de la tienda. | Hook principal para mostrar el bloque del menú de categorías vertical. |
    | `displayRightColumn` | Renderiza contenido en la columna derecha de la tienda. | Hook alternativo para mostrar el bloque del menú de categorías vertical. |
    | `displayHome` | Renderiza contenido en la página de inicio. | Puede usarse para mostrar el menú en la página de inicio, aunque es menos común para un menú vertical. |
    | `displayFooter` | Renderiza contenido en la sección del pie de página. | Menos común para un menú de navegación principal, pero posible para enlaces suplementarios. |
    | `displayProductExtraContent` | Renderiza contenido en la página del producto, típicamente debajo de la información principal del producto. | Podría usarse para mostrar categorías relacionadas para la navegación del producto. |
    | `actionObjectCategoryAddAfter` | Después de añadir una categoría. | Potencialmente utilizado para borrar la caché del módulo si la estructura de categorías cambia. |
    | `actionObjectCategoryUpdateAfter` | Después de actualizar una categoría. | Potencialmente utilizado para borrar la caché del módulo si la estructura de categorías cambia. |
    | `actionObjectCategoryDeleteAfter` | Después de eliminar una categoría. | Potencialmente utilizado para borrar la caché del módulo si la estructura de categorías cambia. |
    | `actionShopDataDuplication` | Cuando se duplica una tienda (en contexto multitienda). | Asegura que la configuración del módulo se copie a la nueva tienda. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Menú desplegable vertical de categorías", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta relacionada con la funcionalidad del módulo.

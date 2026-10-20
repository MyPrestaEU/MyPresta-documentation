---
title: "Fabricante (marca) en la lista de productos del back office - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Fabricante (marca) en la lista de productos del back office' de MyPresta.eu."
sidebar:
  label: "Fabricante (marca) en la lista de productos del back office - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Manufacturer (brand) on products list in back office en MyPresta.eu](https://mypresta.eu/modules/administration-tools/manufacturer-brand-on-products-list-in-back-office.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/manufacturer-brand-on-products-list-in-back-office/)
>
> ---


# Fabricante (marca) en la lista de productos del back office

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.0.0 - 1.7.7.x, 1.7.8.x, 8.x (lista estándar), 8.x (lista de productos experimental), 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página de configuración principal del módulo. Esta página gestiona principalmente las notificaciones de actualización y el mantenimiento general del módulo.

-   **Qué hace este ajuste:** Esta sección suele gestionar cómo el módulo busca actualizaciones y muestra notificaciones.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está activado:* El módulo comprobará periódicamente MyPresta.eu en busca de nuevas versiones y le informará si hay una actualización disponible. Esto le ayuda a mantener su módulo actualizado con las últimas funciones y correcciones de errores.
    -   *Cuando está desactivado:* El módulo no buscará actualizaciones automáticamente y no recibirá notificaciones sobre nuevas versiones. Tendría que comprobar manualmente su cuenta de MyPresta.eu para ver si hay actualizaciones.
-   **Valor recomendado:** **Activado (Sí)**. Mantenerlo activado garantiza que siempre esté al tanto de las actualizaciones disponibles, lo cual es crucial para la seguridad y la compatibilidad con futuras versiones de PrestaShop.
-   **Escenario/ejemplo de comerciante:** Desea recibir notificaciones cuando se lance una nueva versión del módulo que admita las últimas funciones de PrestaShop 8.x. Activar este ajuste garantiza que reciba esa notificación directamente en su back office.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

Este módulo no introduce nuevos elementos de menú separados ni pantallas de administración dedicadas para gestionar su funcionalidad principal. En cambio, sus cambios se integran directamente en la página existente de **Catálogo > Productos**.

**Nombre de la pantalla y ubicación del menú:**

-   **Catálogo > Productos** (La página estándar de listado de productos de PrestaShop)

**Acciones y configuraciones disponibles:**
Al navegar a **Catálogo > Productos**, notará inmediatamente los cambios introducidos por el módulo:

-   **Nueva columna: Fabricante/Marca:** Aparecerá una nueva columna en su lista de productos que muestra el nombre del fabricante asociado a cada producto.
-   **Logotipo del fabricante (Opcional):** Dependiendo de la lógica interna del módulo, también podría mostrar el logotipo del fabricante junto al nombre, si está disponible y configurado.
-   **Filtrar por fabricante:** Encima de la lista de productos, encontrará una nueva opción de filtro, normalmente un menú desplegable, que le permite seleccionar un fabricante específico. Una vez seleccionado, la lista de productos se actualizará instantáneamente para mostrar solo los productos de esa marca.

**Efecto de los cambios:**

-   **Añadir la columna de Fabricante:** Proporciona una señal visual inmediata de la marca de cada producto, eliminando la necesidad de abrir las páginas de productos individualmente para comprobar esta información.
-   **Filtrar por Fabricante:** Acelera drásticamente las tareas en las que necesita trabajar con productos de una marca específica. Por ejemplo, si un fabricante anuncia un aumento de precio, puede filtrar rápidamente todos sus productos y actualizar los precios. O si necesita comprobar los niveles de stock de los artículos de una marca en particular.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1.  **Identificación rápida de la marca:** Al navegar por su lista de productos, utilice la nueva columna "Fabricante" para identificar rápidamente las marcas.
2.  **Gestión dirigida:** Si necesita realizar una acción en todos los productos de una marca específica (por ejemplo, actualizar descripciones, ajustar precios, comprobar inventario), utilice el nuevo menú desplegable "Filtrar por fabricante" en la parte superior de la lista de productos. Seleccione la marca deseada y su lista se refinará instantáneamente.
3.  **Acciones masivas:** Combine el filtro de fabricante con las acciones masivas estándar de PrestaShop (por ejemplo, seleccionar varios productos y aplicar un cambio) para una gestión altamente eficiente y específica de la marca.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Notificaciones de actualización | Activado | Le notifica las nuevas versiones del módulo para seguridad y funciones. |
| Catálogo > Lista de productos | Columna de Fabricante | N/A (Siempre activado) | Muestra la marca del producto directamente en la lista de productos para una identificación rápida. |
| Catálogo > Lista de productos | Filtrar por Fabricante | N/A (Siempre activado) | Permite filtrar la lista de productos por una marca específica, agilizando las tareas de gestión específicas de la marca. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He instalado el módulo, pero no veo la columna del fabricante ni el filtro en mi lista de productos.**
R:

1.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, PrestaShop necesita una actualización de caché para mostrar nuevos elementos.
2.  **Módulo activado:** Verifique que el módulo esté realmente activado en **Módulos > Gestor de módulos**.
3.  **Compatibilidad de la versión de PrestaShop:** Asegúrese de haber descargado la versión correcta del módulo para su instalación específica de PrestaShop. Si está en PrestaShop 8.x, asegúrese de no haber instalado accidentalmente una versión 1.7.x, por ejemplo.
4.  **Sobreescrituras de tema:** Aunque el módulo está diseñado sin sobreescrituras, un tema muy personalizado u otro módulo podrían entrar en conflicto. Si el problema persiste, intente desactivar otros módulos uno por uno para identificar un conflicto.

**P: El nombre del fabricante aparece, pero el logotipo no.**
R: El módulo se centra principalmente en mostrar el nombre del fabricante. Si admite logotipos, asegúrese de que:

1.  **Logotipo del fabricante subido:** Ha subido un logotipo para ese fabricante en **Catálogo > Fabricantes** en su back office de PrestaShop.
2.  **Configuración del módulo:** Podría haber una configuración interna (aunque no expuesta en la configuración básica de este módulo) que controle la visualización del logotipo. Si no, significa que el módulo está diseñado para mostrar solo el nombre.

**P: ¿Puedo cambiar la posición de la columna del fabricante en la lista de productos?**
R: Este módulo se integra directamente en el sistema de cuadrícula de productos de PrestaShop. La posición exacta de la columna está determinada por la configuración principal de la lista de productos de PrestaShop. Si bien este módulo añade la columna, normalmente no ofrece opciones para arrastrar y soltar las posiciones de las columnas. Es posible que necesite un módulo de personalización de cuadrícula más avanzado o un desarrollo personalizado para reordenar las columnas.

**P: ¿Este módulo ralentiza mi back office?**
R: No, el módulo está diseñado para ser ligero y eficiente. Aprovecha el sistema de hooks nativo de PrestaShop para añadir los datos del fabricante sin un procesamiento pesado. No debería experimentar ninguna ralentización notable.

**P: ¿Funcionará este módulo con la nueva página de producto experimental en PrestaShop 8.x?**
R: Sí, la descripción del módulo establece explícitamente la compatibilidad con la "lista de productos experimental de 8.x", lo que significa que está diseñado para funcionar tanto con la interfaz de listado de productos estándar como con la más nueva y experimental en PrestaShop 8.x.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo `Fabricante (marca) en la lista de productos del back office` (nombre interno `dpmypresta`) está diseñado para mejorar la página de listado de productos del Back Office de PrestaShop añadiendo información del fabricante. Se adhiere a un enfoque sin sobreescrituras, basándose en gran medida en el sistema de hooks de PrestaShop, particularmente los hooks `actionProductGrid*` introducidos en PrestaShop 1.7.x para modificar la cuadrícula del catálogo de productos. Esto lo hace robusto frente a las actualizaciones del núcleo de PrestaShop. El módulo inyecta principalmente nuevas columnas y capacidades de filtrado en los datos de la cuadrícula de productos existentes y en el proceso de renderizado.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores de front-office. Incluye dos archivos de controlador de administración, pero `AdminDpMyPrestaController.php` parece ser un marcador de posición o un remanente, e `index.php` es un archivo vacío estándar para evitar la lista de directorios. La lógica central del módulo para la configuración se maneja dentro del método `getContent()` de `dpmypresta.php`, y las modificaciones de la cuadrícula de productos se manejan a través de hooks.

-   **Controladores de Front-Office**: Ninguno. Toda la funcionalidad es específica del back-office.
-   **Controladores de administración de Back-Office**:
    -   `controllers/admin/AdminDpMyPrestaController.php`
        -   Nombre de la clase: `AdminDpMyPrestaController` (extiende `ModuleAdminController`)
        -   Responsabilidad: Este controlador está presente pero parece ser un marcador de posición. Su método `__construct` configura el contexto básico del módulo. No define ninguna acción específica ni renderiza ninguna vista única más allá de lo que pueda heredar de `ModuleAdminController`. No está directamente vinculado a la funcionalidad principal de añadir datos del fabricante a la lista de productos, que se basa en hooks.
    -   `controllers/admin/index.php`
        -   Archivo `index.php` vacío estándar por seguridad para evitar la lista de directorios.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define ninguna clase personalizada ni `ObjectModel`s en el directorio `classes/`. Sus operaciones se integran directamente en las estructuras de datos y mecanismos de cuadrícula existentes de PrestaShop a través de hooks.

### 4.4 Activos de JavaScript (`views/js/`)

El módulo no incluye ningún archivo JavaScript personalizado. Todas las interacciones y la lógica de visualización para la columna del fabricante y el filtro son manejadas por los componentes de cuadrícula nativos de PrestaShop y la lógica PHP del módulo.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo no incluye ningún archivo CSS personalizado. El estilo para la columna del fabricante y el filtro añadidos se hereda del tema del back office de PrestaShop.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

El módulo aprovecha el nuevo sistema de plantillas Twig utilizado en PrestaShop 1.7+ para las cuadrículas del back-office.

-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`
        -   Esta plantilla Twig probablemente extiende o modifica la plantilla principal de la lista de productos de PrestaShop. Es responsable de renderizar la página general del catálogo de productos, incluida la cuadrícula. El módulo inyecta la columna del fabricante y el filtro en esta estructura.
    -   `views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`
        -   Esta plantilla Twig renderiza específicamente la tabla de productos dentro de la página del catálogo. El módulo modifica esta plantilla para añadir los datos del fabricante a cada fila de producto.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**: El módulo no crea ninguna tabla de base de datos personalizada. Se basa en las tablas existentes de PrestaShop, principalmente `ps_product`, `ps_manufacturer` y `ps_configuration` para sus configuraciones.

    -   Los valores de configuración (`mypresta_updates`, `update_`, `updatev_`) se almacenan en la tabla `ps_configuration`.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionProductGridDataModifier` | Después de que se obtienen los datos del producto para la cuadrícula. | Modifica el array de datos sin procesar para cada producto, inyectando el ID y el nombre del fabricante. |
| `actionAdminProductsListingFieldsModifier` | Antes de que se definan los campos de la cuadrícula de productos. | Añade la definición de la columna 'Fabricante' a la cuadrícula de productos. |
| `actionProductGridDefinitionModifier` | Modifica la definición de la propia cuadrícula de productos. | Potencialmente añade el filtro de fabricante a la colección de filtros de la cuadrícula. |
| `actionAdminProductsListingResultsModifier` | Después de que se preparan los resultados del listado de productos. | Modifica aún más los resultados, asegurando que los datos del fabricante estén correctamente formateados para su visualización. |
| `actionProductGridQueryBuilderModifier` | Modifica el Doctrine Query Builder para la cuadrícula de productos. | Une la tabla `ps_manufacturer` a la consulta de productos y añade condiciones para filtrar por fabricante. |
| `displayBackOfficeHeader` | Renderiza contenido en la sección `<head>` del Back Office. | Se utiliza para cargar activos específicos del módulo (aunque no hay ninguno presente en este módulo) o para comprobaciones de actualización. |
| `displayAdminProductsExtra` | Renderiza contenido extra en la página del producto (no se utiliza directamente para la modificación de la lista). | No está directamente relacionado con la funcionalidad principal de este módulo, pero es un hook común para extensiones de la página de producto de administración. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y asistencia adicional con el módulo "Fabricante (marca) en la lista de productos del back office", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está listo para ayudarle con cualquier pregunta o problema que pueda encontrar.

---
title: "Atributos de la lista de productos (combinaciones) - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Atributos de la lista de productos (combinaciones)' de MyPresta.eu."
sidebar:
  label: "Atributos de la lista de productos (combinaciones)"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product list attributes (combinations) en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-list-attributes-combinations.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-list-attributes-combinations/)
>
> ---


# Atributos de la lista de productos (combinaciones)

## 1. Requisitos y compatibilidad

-   **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilidad con PHP**: PHP 5.6 - 8.5
-   **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento web modernos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Después de la instalación, al hacer clic en "Configurar" accederá a la página de configuración principal del módulo "Atributos de la lista de productos (combinaciones)". Aquí es donde controla cómo se muestran las combinaciones en sus listas de productos.

#### Ajustes generales

-   **Mostrar combinaciones en la lista de productos:**
    -   **Qué hace este ajuste:** Este es el interruptor maestro del módulo. Controla si las combinaciones de productos se muestran en las páginas de listado de productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* El módulo inyectará la interfaz de selección de combinaciones en las plantillas de su lista de productos, permitiendo a los clientes elegir variantes directamente.
        -   *Cuando está desactivado (NO):* El módulo estará inactivo en el front office, y las listas de productos se comportarán como PrestaShop estándar, requiriendo que los clientes visiten la página del producto para seleccionar combinaciones.
    -   **Valor recomendado:** SÍ (para utilizar la funcionalidad principal del módulo).
    -   **Escenario / ejemplo del comerciante:** Si desea ofrecer una experiencia de compra más rápida, active esto. Si prefiere que los clientes siempre lleguen a la página del producto para obtener más detalles, desactívelo.

-   **Mostrar botón "Añadir al carrito":**
    -   **Qué hace este ajuste:** Determina si se muestra un botón "Añadir al carrito" junto a los selectores de combinación en la lista de productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* Aparecerá un botón "Añadir al carrito" junto a las opciones de combinación. Una vez que un cliente selecciona una combinación, puede hacer clic en este botón para añadirla a su carrito.
        -   *Cuando está desactivado (NO):* Los selectores de combinación seguirán siendo visibles, pero los clientes deberán hacer clic en la imagen o el nombre del producto para ir a la página del producto y añadirlo al carrito. Esto podría ser útil si desea mostrar opciones pero aún así fomentar las visitas a la página del producto.
    -   **Valor recomendado:** SÍ (para máxima comodidad y conversión).
    -   **Escenario / ejemplo del comerciante:** Para una experiencia de compra rápida, active esto. Si sus productos requieren una lectura o personalización extensas antes de la compra, podría desactivarlo para guiar a los clientes a la página del producto.

-   **Mostrar campo de cantidad:**
    -   **Qué hace este ajuste:** Controla si se muestra un campo de entrada de cantidad junto al botón "Añadir al carrito" en la lista de productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* Los clientes pueden especificar la cantidad de una combinación elegida que desean añadir a su carrito directamente desde la lista de productos.
        -   *Cuando está desactivado (NO):* El botón "Añadir al carrito" añadirá una sola unidad de la combinación seleccionada. Los clientes tendrían que ajustar las cantidades en el carrito o en la página del producto.
    -   **Valor recomendado:** SÍ (para la mayoría de las tiendas, ya que ofrece más flexibilidad).
    -   **Escenario / ejemplo del comerciante:** Si los clientes suelen comprar varias unidades del mismo artículo (por ejemplo, calcetines, papelería), active esto. Si sus productos se compran normalmente de uno en uno, podría desactivarlo para una apariencia más limpia.

-   **Mostrar referencia del producto:**
    -   **Qué hace este ajuste:** Muestra u oculta el número de referencia del producto (SKU) junto a las opciones de combinación.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* La referencia del producto será visible, lo que puede ser útil para los clientes que rastrean artículos específicos o para clientes B2B.
        -   *Cuando está desactivado (NO):* La referencia no se mostrará, lo que lleva a una interfaz más limpia y menos desordenada.
    -   **Valor recomendado:** NO (a menos que su público objetivo se beneficie específicamente de ver las referencias).
    -   **Escenario / ejemplo del comerciante:** Para tiendas B2B o productos técnicos donde los clientes a menudo piden por SKU, active esto. Para el comercio minorista general, normalmente no es necesario.

-   **Mostrar EAN13/JAN del producto:**
    -   **Qué hace este ajuste:** Muestra u oculta el número de código de barras EAN13 o JAN del producto.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* El EAN13/JAN será visible, lo que puede ser útil para los clientes que necesitan hacer referencias cruzadas de productos utilizando estos identificadores.
        -   *Cuando está desactivado (NO):* El EAN13/JAN no se mostrará.
    -   **Valor recomendado:** NO (similar a la referencia, solo active si hay una necesidad específica del cliente).
    -   **Escenario / ejemplo del comerciante:** Rara vez es necesario para la visualización en el front-office, pero podría ser útil para nichos específicos o B2B.

-   **Mostrar UPC del producto:**
    -   **Qué hace este ajuste:** Muestra u oculta el número de código de barras UPC del producto.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* El UPC será visible.
        -   *Cuando está desactivado (NO):* El UPC no se mostrará.
    -   **Valor recomendado:** NO (similar a EAN13/JAN).
    -   **Escenario / ejemplo del comerciante:** Similar a EAN13/JAN, normalmente no es un requisito del front-office para la mayoría de los minoristas.

-   **Mostrar peso del producto:**
    -   **Qué hace este ajuste:** Muestra u oculta el peso del producto junto a las opciones de combinación.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* El peso del producto será visible, lo que puede ser importante para los clientes preocupados por los costos de envío o la manipulación.
        -   *Cuando está desactivado (NO):* El peso no se mostrará.
    -   **Valor recomendado:** NO (a menos que el peso sea un factor crítico para sus productos).
    -   **Escenario / ejemplo del comerciante:** Para productos donde el peso es un factor de compra significativo (por ejemplo, productos a granel, piezas de maquinaria pesada), active esto.

-   **Mostrar precio del producto:**
    -   **Qué hace este ajuste:** Controla si el precio de la combinación seleccionada se actualiza dinámicamente y se muestra en la lista de productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* A medida que un cliente selecciona diferentes combinaciones, el precio mostrado se actualizará para reflejar el precio de la combinación específica (incluyendo cualquier impacto de precio de atributo).
        -   *Cuando está desactivado (NO):* El precio que se muestra en la lista de productos seguirá siendo el precio base del producto, y los clientes podrían tener que inferir el precio de la combinación o ir a la página del producto.
    -   **Valor recomendado:** SÍ (crucial para la transparencia y la compra informada).
    -   **Escenario / ejemplo del comerciante:** Active siempre esto para una fijación de precios clara. Si está desactivado, los clientes podrían confundirse con los cambios de precio al finalizar la compra.

-   **Mostrar disponibilidad del producto:**
    -   **Qué hace este ajuste:** Muestra u oculta el estado de disponibilidad de stock para la combinación seleccionada (por ejemplo, "En stock", "Agotado", "¡Últimas unidades!").
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* Los clientes verán el estado del stock, lo que les ayudará a tomar decisiones de compra y evitará la frustración de intentar pedir artículos agotados.
        -   *Cuando está desactivado (NO):* El estado del stock no se mostrará, lo que podría llevar a los clientes a intentar añadir artículos agotados a su carrito.
    -   **Valor recomendado:** SÍ (muy recomendado para gestionar las expectativas del cliente).
    -   **Escenario / ejemplo del comerciante:** Esencial para cualquier tienda para evitar pedidos de artículos no disponibles. Active siempre.

-   **Mostrar descripción del producto:**
    -   **Qué hace este ajuste:** Muestra u oculta una breve descripción del producto debajo de las combinaciones.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* Aparecerá una breve descripción del producto, ofreciendo más contexto sin requerir un clic a la página del producto.
        -   *Cuando está desactivado (NO):* La descripción no se mostrará, manteniendo la lista de productos concisa.
    -   **Valor recomendado:** NO (las listas de productos suelen ser para una navegación rápida; las descripciones detalladas pertenecen a la página del producto).
    -   **Escenario / ejemplo del comerciante:** Si tiene descripciones muy cortas e impactantes que ayudan a tomar decisiones rápidas, podría activar esto. De lo contrario, manténgalo desactivado para evitar el desorden.

-   **Mostrar descripción corta del producto:**
    -   **Qué hace este ajuste:** Similar a "Mostrar descripción del producto", pero específicamente para el campo de descripción corta.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* La descripción corta del producto será visible.
        -   *Cuando está desactivado (NO):* La descripción corta no se mostrará.
    -   **Valor recomendado:** NO (por las mismas razones que la descripción completa).
    -   **Escenario / ejemplo del comerciante:** Úselo con moderación, solo si sus descripciones cortas son extremadamente concisas y cruciales para la compra en vista de lista.

-   **Mostrar imágenes del producto:**
    -   **Qué hace este ajuste:** Determina si la imagen del producto se actualiza dinámicamente cuando un cliente selecciona una combinación diferente (por ejemplo, seleccionar una camisa "azul" muestra la imagen de la camisa azul).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* La imagen principal del producto en la lista cambiará para reflejar la imagen asociada con la combinación seleccionada. Esto proporciona una rica retroalimentación visual.
        -   *Cuando está desactivado (NO):* La imagen del producto permanecerá estática, mostrando la imagen predeterminada del producto independientemente de la combinación seleccionada.
    -   **Valor recomendado:** SÍ (muy recomendado para la confirmación visual y una mejor experiencia de usuario).
    -   **Escenario / ejemplo del comerciante:** Crucial para ropa, electrónica o cualquier producto donde la representación visual de la variante sea importante.

-   **Mostrar atributos del producto como:**
    -   **Qué hace este ajuste:** Este es un ajuste crucial que define cómo se presentan las opciones de combinación (por ejemplo, tamaño, color) al cliente.
    -   **Efecto de cambiar este ajuste:**
        -   *Lista desplegable:* Los atributos aparecerán como elementos `<select>` desplegables HTML estándar. Esto es compacto y adecuado para muchas opciones.
        -   *Botones de radio:* Los atributos aparecerán como botones de radio. Bueno para un pequeño número de opciones distintas.
        -   *Selector de color:* Si sus atributos están definidos como tipo "color" en PrestaShop, esto los mostrará como muestras de color en las que se puede hacer clic.
    -   **Valor recomendado:**
        -   *Selector de color* para atributos de color.
        -   *Lista desplegable* para atributos con muchas opciones (por ejemplo, tallas S-XXL).
        -   *Botones de radio* para atributos con pocas opciones distintas (por ejemplo, "Sí/No", "Con/Sin").
    -   **Escenario / ejemplo del comerciante:** Para una tienda de ropa, probablemente usaría "Selector de color" para los colores y "Lista desplegable" para las tallas. Para un producto simple con dos opciones como "Envuelto para regalo: Sí/No", los botones de radio podrían ser lo mejor.

-   **Mostrar atributos del producto para:**
    -   **Qué hace este ajuste:** Le permite especificar qué atributos de producto deben tener sus combinaciones mostradas en la lista de productos. Puede seleccionar grupos de atributos específicos (por ejemplo, "Talla", "Color", "Material").
    -   **Efecto de cambiar este ajuste:**
        -   *Grupos de atributos seleccionados:* Solo se mostrarán las combinaciones que involucren los grupos de atributos elegidos. Por ejemplo, si selecciona "Color" y "Talla", los clientes verán opciones para colores y tallas.
        -   *Sin selección:* Si no se selecciona nada, el módulo podría mostrar por defecto todos los atributos o ninguno, dependiendo de la lógica interna del módulo. Es mejor seleccionar explícitamente.
    -   **Valor recomendado:** Seleccione todos los grupos de atributos relevantes que definen sus combinaciones de productos.
    -   **Escenario / ejemplo del comerciante:** Si vende camisetas en diferentes colores y tallas, seleccione "Color" y "Talla". Si también tiene un atributo "Material" pero no desea mostrarlo en la lista, déjelo sin seleccionar.

-   **Hook para mostrar el módulo:**
    -   **Qué hace este ajuste:** Determina dónde se inyectarán los selectores de combinación en sus páginas de listado de productos.
    -   **Efecto de cambiar este ajuste:**
        -   `displayProductListFunctionalButtons`: Este hook suele estar ubicado cerca del botón "Añadir al carrito" u otros elementos funcionales en los elementos de la lista de productos.
        -   `displayProductListReviews`: A menudo cerca de las estrellas de las reseñas o los recuentos de reseñas.
        -   `displayProductListPrice`: Generalmente cerca del precio del producto.
        -   `displayProductListExtraContent`: Un hook general para contenido extra, a menudo en la parte inferior de la tarjeta del producto.
        -   `displayProductListFooter`: En la parte inferior de la tarjeta del producto.
    -   **Valor recomendado:** `displayProductListFunctionalButtons` o `displayProductListExtraContent` son opciones comunes, pero esto depende en gran medida del diseño de su tema. Es posible que deba experimentar para encontrar la mejor ubicación visual.
    -   **Escenario / ejemplo del comerciante:** Si su tema tiene un área limpia debajo del nombre y el precio del producto, `displayProductListFunctionalButtons` podría encajar bien. Si desea que las opciones aparezcan de forma más destacada, `displayProductListExtraContent` podría ser mejor.

-   **Excluir productos del módulo:**
    -   **Qué hace este ajuste:** Le permite especificar productos individuales por su ID que *no* deben mostrar combinaciones en la lista de productos, incluso si el módulo está generalmente activado.
    -   **Efecto de cambiar este ajuste:**
        -   *Introduciendo IDs de producto (separados por comas):* Los productos especificados volverán al comportamiento estándar de PrestaShop en las listas de productos, requiriendo un clic a la página del producto para la selección de combinaciones.
        -   *Dejando vacío:* Todos los productos con combinaciones las mostrarán en la lista.
    -   **Valor recomendado:** Dejar vacío a menos que tenga productos específicos que requieran una visita completa a la página del producto.
    -   **Escenario / ejemplo del comerciante:** Es posible que tenga algunos productos complejos con muchos atributos, o productos que requieren un configurador detallado, donde prefiere que los clientes lleguen primero a la página del producto.

-   **Excluir categorías del módulo:**
    -   **Qué hace este ajuste:** Le permite especificar categorías por su ID que *no* deben mostrar combinaciones en sus listas de productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Introduciendo IDs de categoría (separados por comas):* Los productos dentro de estas categorías no mostrarán combinaciones en sus respectivas páginas de listado.
        -   *Dejando vacío:* Todas las categorías mostrarán combinaciones de productos.
    -   **Valor recomendado:** Dejar vacío a menos que tenga categorías específicas donde esta característica no sea deseada.
    -   **Escenario / ejemplo del comerciante:** Si tiene una categoría de "Liquidación" donde todos los productos son de una sola variante y desea mantener la visualización muy mínima, podría excluirla.

#### 2.1.1 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Configuración del módulo | Mostrar combinaciones en la lista de productos | SÍ | Interruptor maestro para activar/desactivar la visualización de combinaciones en las listas de productos. |
| Configuración del módulo | Mostrar botón "Añadir al carrito" | SÍ | Muestra un botón "Añadir al carrito" junto a las combinaciones para compra directa. |
| Configuración del módulo | Mostrar campo de cantidad | SÍ | Permite a los clientes seleccionar la cantidad directamente en la lista de productos. |
| Configuración del módulo | Mostrar referencia del producto | NO | Muestra/oculta el SKU del producto. |
| Configuración del módulo | Mostrar EAN13/JAN del producto | NO | Muestra/oculta el EAN13/JAN del producto. |
| Configuración del módulo | Mostrar UPC del producto | NO | Muestra/oculta el UPC del producto. |
| Configuración del módulo | Mostrar peso del producto | NO | Muestra/oculta el peso del producto. |
| Configuración del módulo | Mostrar precio del producto | SÍ | Actualiza dinámicamente el precio según la combinación seleccionada. |
| Configuración del módulo | Mostrar disponibilidad del producto | SÍ | Muestra el estado del stock para la combinación seleccionada. |
| Configuración del módulo | Mostrar descripción del producto | NO | Muestra/oculta la descripción completa del producto. |
| Configuración del módulo | Mostrar descripción corta del producto | NO | Muestra/oculta la descripción corta del producto. |
| Configuración del módulo | Mostrar imágenes del producto | SÍ | Actualiza dinámicamente la imagen del producto según la combinación seleccionada. |
| Configuración del módulo | Mostrar atributos del producto como | Desplegable, Radio, Selector de color | Define la presentación visual de las opciones de atributo. |
| Configuración del módulo | Mostrar atributos del producto para | Seleccionar grupos relevantes | Especifica qué grupos de atributos mostrar. |
| Configuración del módulo | Hook para mostrar el módulo | `displayProductListFunctionalButtons` | Determina la ubicación visual del módulo en las tarjetas de producto. |
| Configuración del módulo | Excluir productos del módulo | Dejar vacío | IDs de producto separados por comas para excluir de la función. |
| Configuración del módulo | Excluir categorías del módulo | Dejar vacío | IDs de categoría separados por comas para excluir de la función. |

### 2.2 Pantallas de administración dedicadas y vistas de controlador

Este módulo utiliza controladores de administración personalizados para la gestión interna, pero el comerciante no suele acceder a ellos directamente para la configuración diaria. Son principalmente para operaciones internas del módulo o depuración avanzada.

#### 2.2.1 AdminPlaSearchController (Back Office > Módulos > Atributos de la lista de productos (combinaciones) > Configuración de búsqueda)
-   **Nombre de la pantalla y ubicación del menú:** Este controlador probablemente se utiliza para la configuración de búsqueda interna o la gestión de datos relacionados con la forma en que se indexan o recuperan las combinaciones. Puede que no tenga un elemento de menú directo y visible para el comerciante, o podría ser una pestaña interna dentro de la configuración principal del módulo.
-   **Acciones y configuraciones disponibles:** Esta pantalla normalmente presentaría una vista de cuadrícula o lista de datos (por ejemplo, productos indexados, mapeos de atributos) y podría ofrecer acciones como "Reconstruir índice", "Borrar caché" o "Editar configuración de búsqueda".
-   **Efecto de los cambios:** Los cambios aquí afectarían el rendimiento o la precisión de la visualización de combinaciones, especialmente en catálogos grandes. Una configuración incorrecta podría hacer que las combinaciones no aparezcan o se carguen lentamente.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Los comerciantes generalmente no necesitan interactuar con esta pantalla a menos que lo aconseje el soporte o para una resolución de problemas avanzada. La página de configuración principal del módulo maneja todos los ajustes orientados al usuario.

#### 2.2.2 index.php (pla/controllers/admin/index.php)
-   **Nombre de la pantalla y ubicación del menú:** Este archivo `index.php` dentro del directorio del controlador `admin` es una práctica común de PrestaShop para evitar la lista de directorios. Normalmente no representa una pantalla orientada al usuario, sino que garantiza la seguridad y el enrutamiento adecuado para otros controladores de administración dentro del módulo.
-   **Acciones y configuraciones disponibles:** No hay acciones o configuraciones directas orientadas al comerciante.
-   **Efecto de los cambios:** No hay un efecto directo en la visualización o los datos de la tienda, ya que es un archivo estructural.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** No se requiere interacción.

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Las combinaciones no aparecen en mi lista de productos. ¿Qué debo hacer?**
R:
1.  **Verificar el estado del módulo:** Vaya a **Módulos > Gestor de módulos**, busque "Atributos de la lista de productos (combinaciones)" y asegúrese de que esté instalado y activado.
2.  **Verificar la configuración del módulo:** Vaya a la página de configuración del módulo. Asegúrese de que "Mostrar combinaciones en la lista de productos" esté configurado en SÍ.
3.  **Verificar los grupos de atributos:** Asegúrese de haber seleccionado los grupos correctos en "Mostrar atributos del producto para" (por ejemplo, "Talla", "Color").
4.  **Verificar exclusiones:** Verifique que el producto o la categoría que está probando no esté listado en "Excluir productos del módulo" o "Excluir categorías del módulo".
5.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los archivos de caché antiguos impiden que aparezca el nuevo contenido del módulo.
6.  **Compatibilidad del tema:** Su tema podría estar muy personalizado y no utilizar los hooks estándar de PrestaShop. Intente cambiar la configuración "Hook para mostrar el módulo" a un hook diferente (por ejemplo, `displayProductListExtraContent`) y borre la caché. Si los problemas persisten, póngase en contacto con su webmaster o con el soporte de MyPresta.eu.

**P: El botón "Añadir al carrito" o el campo de cantidad no se muestran.**
R:
1.  **Verificar la configuración del módulo:** Asegúrese de que "Mostrar botón 'Añadir al carrito'" y "Mostrar campo de cantidad" estén ambos configurados en SÍ en la configuración del módulo.
2.  **Borrar caché:** Siempre borre la caché de su PrestaShop después de realizar cambios en la configuración.

**P: La imagen del producto no cambia cuando selecciono una combinación diferente.**
R:
1.  **Verificar la configuración del módulo:** Asegúrese de que "Mostrar imágenes del producto" esté configurado en SÍ.
2.  **Imágenes del producto:** Verifique que sus combinaciones de productos realmente tengan imágenes asociadas. En la página de back office de su producto, vaya a la pestaña "Combinaciones" y asegúrese de que cada combinación tenga imágenes vinculadas a ella.
3.  **Borrar caché:** Borre la caché de su PrestaShop.

**P: El estilo (colores, alineación) de las combinaciones se ve mal en mi tienda.**
R:
Esto suele ser un conflicto de CSS con su tema.
1.  **Borrar caché:** A veces, borrar la caché ayuda.
2.  **Personalización del tema:** Su tema podría tener reglas de estilo específicas que anulan o entran en conflicto con el CSS predeterminado del módulo. Esto requiere que un webmaster o desarrollador inspeccione el CSS y realice ajustes en la hoja de estilos de su tema. El módulo proporciona sus propios archivos CSS, pero los temas siempre pueden anularlos.

**P: ¿Este módulo funciona con tiendas multi-idioma?**
R: Sí, el módulo está diseñado para ser compatible con las funciones multi-idioma de PrestaShop. Los nombres y valores de los atributos se mostrarán en el idioma seleccionado en el front-office, siempre que estén correctamente traducidos en el back office de su PrestaShop (Catálogo > Atributos y características).

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada del módulo "Atributos de la lista de productos (combinaciones)" para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura
El módulo sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, extendiendo principalmente `Module` para su funcionalidad principal y `ModuleFrontController` para las interacciones AJAX. Aprovecha el sistema de hooks de PrestaShop para inyectar su contenido en las plantillas de listado de productos. La lógica principal del módulo reside en `index.php` (el archivo principal del módulo), que maneja la instalación, desinstalación y el método `getContent()` para la configuración del back-office. La visualización en el front-office se gestiona a través de plantillas Smarty renderizadas mediante hooks, con interacciones dinámicas impulsadas por JavaScript y AJAX.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office
-   `controllers/front/ajax.php`
    *   **Nombre de la clase y clase padre:** `PlaAjaxModuleFrontController` extiende `ModuleFrontController`.
    *   **Responsabilidad:** Este controlador maneja todas las solicitudes AJAX desde el front office. Cuando un cliente interactúa con los selectores de combinación (por ejemplo, cambia una talla o un color), este controlador es responsable de recibir la solicitud, procesarla (por ejemplo, obtener precios actualizados, stock, imágenes para la combinación seleccionada) y devolver una respuesta JSON para actualizar el front-end dinámicamente sin una recarga completa de la página. Es crucial para la experiencia interactiva del módulo.
-   `controllers/front/index.php`
    *   **Nombre de la clase y clase padre:** `PlaIndexModuleFrontController` extiende `ModuleFrontController`.
    *   **Responsabilidad:** Este es un controlador frontal de marcador de posición, a menudo utilizado para evitar la lista de directorios o como un respaldo para rutas específicas del módulo. En el contexto de este módulo, puede que no tenga un enrutamiento directo y activo, pero sirve como una práctica estándar de PrestaShop. La interacción principal del front-office es a través de `ajax.php`.

#### Controladores de administración del Back-Office
-   `controllers/admin/AdminPlaSearchController.php`
    *   **Nombre de la clase y clase padre:** `AdminPlaSearchController` extiende `ModuleAdminController`.
    *   **Nombre de la pestaña y entidad gestionada:** Este controlador probablemente gestiona mecanismos internos de búsqueda o indexación para combinaciones de productos. Puede que no tenga una entrada de menú directa, pero podría ser accedido internamente por el módulo para tareas como reconstruir un índice de búsqueda para combinaciones. Normalmente gestionaría una entidad virtual relacionada con los datos de búsqueda en lugar de un `ObjectModel` directo.
-   `controllers/admin/index.php`
    *   **Nombre de la clase y clase padre:** No es una clase de controlador directa, sino un archivo `index.php` estándar.
    *   **Nombre de la pestaña y entidad gestionada:** Este archivo es una medida de seguridad para evitar la lista de directorios de la carpeta `admin`. No representa una pantalla de administración funcional en sí mismo.

### 4.3 Clases y modelos principales (`classes/`)
El dossier del módulo no indica clases o modelos personalizados en el directorio `classes/`. Esto sugiere que el módulo opera principalmente extendiendo las funcionalidades principales existentes de PrestaShop (como `Product`, `Combination`) y utiliza consultas directas a la base de datos o la clase `Db` de PrestaShop para la interacción de datos, en lugar de definir sus propias entidades `ObjectModel`. Toda la lógica principal probablemente está encapsulada dentro del archivo principal del módulo (`pla/index.php`) y sus controladores.

### 4.4 Activos JavaScript (`views/js/`)
-   `pla/lib/searchTool/views/js/autocomplete.js`
    *   **Alcance:** Potencialmente tanto Front-office (para funcionalidad de búsqueda en vivo si está integrada) como Back-office (para campos de búsqueda de administración). Dado el enfoque del módulo, es más probable que sea para la configuración de búsqueda del back-office relacionada con `AdminPlaSearchController`.
    *   **Detalles:** Maneja la funcionalidad de autocompletado, probablemente para buscar productos o atributos dentro de la configuración de administración del módulo o una función de búsqueda personalizada. Se vincularía a los campos de entrada, escucharía los eventos `keyup` y realizaría llamadas AJAX para obtener sugerencias.
-   `pla/views/templates/js/pla.js`
    *   **Alcance:** Front-office.
    *   **Detalles:** Este es el archivo JavaScript principal para la funcionalidad del front-office.
        *   **Escuchadores de eventos:** Vincula eventos `change` a los selectores de combinación (desplegables, botones de radio, selectores de color) en los elementos de la lista de productos.
        *   **Manipulación del DOM:** Actualiza los precios de los productos, el estado del stock, las imágenes de los productos y los estados del botón "Añadir al carrito" en función de las combinaciones seleccionadas.
        *   **Llamadas AJAX:** Realiza solicitudes AJAX a `controllers/front/ajax.php` para recuperar datos de combinación actualizados (precio, stock, URL de imagen, etc.) cuando cambia una selección.
        *   **Inicialización del módulo:** Probablemente contiene código para inicializar los selectores de combinación al cargar la página y volver a inicializarlos después de las actualizaciones AJAX (por ejemplo, desplazamiento infinito, filtrado de categorías).

### 4.5 Hojas de estilo CSS (`views/css/`)
-   `pla/css.css`
    *   **Alcance:** Probablemente Front-office.
    *   **Detalles:** Estilo general para los elementos de visualización de combinaciones en las listas de productos. Contiene estilos base para desplegables, botones de radio, campos de cantidad y botones "Añadir al carrito" tal como los renderiza el módulo.
-   `pla/lib/searchTool/views/css/autocomplete.css`
    *   **Alcance:** Potencialmente tanto Front-office como Back-office.
    *   **Detalles:** Estilos para la lista de sugerencias de autocompletado y los campos de entrada, probablemente utilizados en conjunto con `autocomplete.js`.
-   `pla/views/templates/css/pla-classic.css`
    *   **Alcance:** Front-office.
    *   **Detalles:** Estilo específico adaptado para temas antiguos de PrestaShop (por ejemplo, tema Classic o estructuras similares). Podría contener anulaciones más explícitas o estilos de respaldo.
-   `pla/views/templates/css/pla.css`
    *   **Alcance:** Front-office.
    *   **Detalles:** Estilo principal para los elementos del front-office del módulo, potencialmente para versiones más nuevas de PrestaShop o un enfoque más genérico. Contiene estilos para los contenedores de combinaciones, las opciones de atributos y los elementos dinámicos.
    *   **Selectores de clase CSS clave:** Los desarrolladores pueden esperar que estén presentes clases como `.pla-combinations-wrapper`, `.pla-attribute-group`, `.pla-attribute-option`, `.pla-add-to-cart-btn`, `.pla-quantity-input`, `.pla-price-display`, `.pla-availability-status` y pueden anularlas en el `custom.css` o `theme.css` de su tema.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)
-   `pla/views/templates/hook/pla.tpl`
    *   **Hook:** Principalmente destinado a hooks como `displayProductListFunctionalButtons`, `displayProductListExtraContent`, etc.
    *   **Salida:** Esta es la plantilla principal responsable de renderizar los selectores de combinación, el botón "Añadir al carrito", el campo de cantidad, el precio y la disponibilidad en cada elemento del producto en la lista de productos. Itera a través de los grupos y valores de atributos disponibles, generando el HTML apropiado (desplegables, botones de radio, muestras de color) según la configuración del módulo.

#### Plantillas de administración (`views/templates/admin/`)
-   `pla/views/templates/admin/admin.tpl`
    *   **Propósito:** Esta plantilla se utiliza para la página de configuración principal del módulo en el back office de PrestaShop (accesible a través de `getContent()` en `pla/index.php`). Contiene los formularios para todos los ajustes descritos en la Sección 4.1.
-   `pla/views/templates/admin/selectedCa.tpl`
    *   **Propósito:** Probablemente una plantilla parcial utilizada dentro de un formulario o cuadrícula de administración para mostrar categorías seleccionadas (por ejemplo, para la configuración "Excluir categorías del módulo"). Renderizaría una lista de categorías seleccionadas, posiblemente con opciones para eliminarlas.
-   `pla/views/templates/admin/selectedProducts.tpl`
    *   **Propósito:** Similar a `selectedCa.tpl`, pero para productos seleccionados (por ejemplo, para la configuración "Excluir productos del módulo"). Mostraría una lista de productos seleccionados.

#### Plantillas JavaScript (`views/templates/js/`)
-   `pla/views/templates/js/pla_admin.tpl`
    *   **Alcance:** Back-office.
    *   **Salida:** Esta plantilla probablemente contiene código JavaScript específicamente para el panel de administración. Podría incluir scripts para manejar elementos de formulario dinámicos, llamadas AJAX dentro del administrador o inicializar componentes en la página de configuración del módulo.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos
El dossier del módulo no indica archivos SQL personalizados. Esto implica que el módulo almacena principalmente sus configuraciones en la tabla `ps_configuration` de PrestaShop.
-   **`ps_configuration`**: Almacena la configuración del módulo (por ejemplo, `PLA_DISPLAY_COMBINATIONS`, `PLA_DISPLAY_ADD_TO_CART`, `PLA_EXCLUDE_PRODUCTS`, `PLA_HOOK_NAME`, etc.). Estas claves suelen tener el prefijo `PLA_` o `MYPRESTA_PLA_`.

#### Tabla de hooks registrados
El módulo registra y utiliza varios hooks de PrestaShop para integrar su funcionalidad.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
|---|---|---|
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Para incluir los archivos CSS y JavaScript necesarios para la funcionalidad del front-office del módulo. |
| `displayProductListFunctionalButtons` | Dentro de cada elemento de producto en las páginas de listado de productos, normalmente cerca de los botones de acción. | Un hook común para inyectar los selectores de combinación y el botón "Añadir al carrito". |
| `displayProductListReviews` | Dentro de cada elemento de producto en las páginas de listado de productos, a menudo cerca de los elementos de reseña. | Hook alternativo para mostrar las opciones de combinación. |
| `displayProductListPrice` | Dentro de cada elemento de producto en las páginas de listado de productos, cerca del precio del producto. | Hook alternativo para mostrar las opciones de combinación. |
| `displayProductListExtraContent` | Un hook de propósito general dentro de cada elemento de producto para contenido adicional. | Hook flexible para inyectar los selectores de combinación, a menudo en la parte inferior de la tarjeta del producto. |
| `displayProductListFooter` | En la parte inferior de cada elemento de producto en las páginas de listado de productos. | Otro hook alternativo para mostrar las opciones de combinación. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su contenido, permitiendo que los módulos añadan activos. | Para cargar condicionalmente activos JS/CSS específicos solo cuando el módulo los necesita en las páginas relevantes. |
| `actionProductUpdate` | Después de que un producto se actualiza en el back office. | Potencialmente utilizado para borrar cachés específicas del módulo o reindexar datos de combinación de productos si el módulo tiene un mecanismo de indexación interno. |
| `actionAttributeGroupUpdate` / `actionAttributeUpdate` | Después de que se actualizan los grupos de atributos o los atributos. | Similar a `actionProductUpdate`, para borrar la caché o reindexar. |

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo se dedica a brindar asistencia y garantizar el buen funcionamiento de su módulo.

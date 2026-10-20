---
title: "Tabla de combinaciones de la página de producto - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Tabla de combinaciones de la página de producto' de MyPresta.eu."
sidebar:
  label: "Tabla de combinaciones de la página de producto - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product page combinations table en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-page-combinations-table/)
>
> ---


# Tabla de combinaciones de la página de producto

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde controla cómo aparece y se comporta la tabla de combinaciones en sus páginas de producto.

#### Configuración general

-   **Activar función de filtros**

    -   **Qué hace esta configuración:** Habilita o deshabilita un sistema de filtrado encima de la tabla de combinaciones, permitiendo a los clientes reducir rápidamente las opciones basándose en valores de atributos específicos (por ejemplo, "Mostrar solo camisetas rojas").
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Aparecerá una barra de filtros encima de la tabla, facilitando a los clientes encontrar combinaciones específicas en listas grandes.
        -   *Cuando está deshabilitado:* No se mostrará ninguna barra de filtros, y todas las combinaciones se mostrarán sin opciones de filtrado.
    -   **Valor recomendado:** SÍ (si tiene muchas combinaciones por producto, o si los clientes a menudo buscan atributos específicos).
    -   **Escenario / ejemplo de comerciante:** Una tienda de ropa con docenas de tallas y colores para una sola camiseta. Los filtros ayudan a los clientes a encontrar rápidamente camisetas "Grandes Azules".
-   **Resaltar mejor precio**

    -   **Qué hace esta configuración:** Enfatiza visualmente la combinación con el precio más bajo en la tabla, atrayendo la atención del cliente a la opción más asequible.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* La fila correspondiente a la combinación más barata se resaltará (por ejemplo, con un color de fondo diferente).
        -   *Cuando está deshabilitado:* No habrá un resaltado especial para el precio más bajo.
    -   **Valor recomendado:** SÍ (puede fomentar las compras al destacar el valor).
    -   **Escenario / ejemplo de comerciante:** Un producto con varios paquetes o configuraciones donde una combinación ofrece una oferta significativamente mejor.
-   **Mostrar columna de ahorro**

    -   **Qué hace esta configuración:** Añade una columna extra a la tabla que muestra la cantidad o el porcentaje que un cliente ahorra al comprar una combinación específica, especialmente útil con descuentos por cantidad o precios especiales.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Aparecerá una columna "Ahorro", mostrando el descuento para cada combinación si corresponde.
        -   *Cuando está deshabilitado:* Esta columna no se mostrará.
    -   **Valor recomendado:** SÍ (si ofrece descuentos con frecuencia o tiene precios basados en la cantidad).
    -   **Escenario / ejemplo de comerciante:** Vender un producto con un precio base, pero ciertas combinaciones (por ejemplo, una combinación de "paquete") tienen un precio reducido, y desea mostrar el ahorro.
-   **Consejo de umbral de descuento por cantidad**

    -   **Qué hace esta configuración:** Muestra una pequeña información o mensaje que indica la cantidad requerida para desbloquear un descuento específico, animando a los clientes a comprar más.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Cuando un cliente pasa el ratón por encima o interactúa con una entrada de cantidad, puede aparecer un consejo que diga "¡Compre 5 para un 10% de descuento!".
        -   *Cuando está deshabilitado:* No se mostrarán tales consejos.
    -   **Valor recomendado:** SÍ (si utiliza la función de descuentos por cantidad de PrestaShop).
    -   **Escenario / ejemplo de comerciante:** Una tienda que vende material de oficina donde comprar 10 bolígrafos obtiene un 5% de descuento, y este consejo se lo recuerda al cliente.
-   **Diseño de tarjeta móvil**

    -   **Qué hace esta configuración:** Determina cómo se muestra la tabla de combinaciones en dispositivos móviles. En lugar de una tabla ancha, puede cambiar a un diseño de "tarjeta" más fácil de usar.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* En smartphones, cada combinación se presentará como una tarjeta separada, apilada verticalmente, lo que facilita la lectura y la interacción.
        -   *Cuando está deshabilitado:* El módulo intentará mostrar la tabla completa, lo que podría requerir desplazamiento horizontal en el móvil, lo que podría dificultar la usabilidad.
    -   **Valor recomendado:** SÍ (crucial para la capacidad de respuesta móvil y una buena experiencia de usuario).
    -   **Escenario / ejemplo de comerciante:** Un cliente que navega por su tienda en su teléfono. El diseño de tarjeta garantiza que pueda ver y seleccionar combinaciones fácilmente sin hacer zoom ni desplazarse excesivamente.
-   **Orden de las columnas**

    -   **Qué hace esta configuración:** Le permite personalizar la secuencia de columnas (por ejemplo, Imagen, Referencia, Precio, Cantidad) en la tabla de combinaciones.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando se cambia:* Las columnas se reorganizarán en la tabla del front-office según el orden especificado.
    -   **Valor recomendado:** Organice las columnas en un orden intuitivo que tenga sentido para sus productos (por ejemplo, Imagen, Atributos, Precio, Cantidad, Añadir al carrito).
    -   **Escenario / ejemplo de comerciante:** Para una tienda de moda, es posible que desee "Imagen" primero, luego "Color", luego "Talla", luego "Precio". Para la electrónica, "Referencia" podría ser más importante.
-   **Hacer clic y cambiar combinación**

    -   **Qué hace esta configuración:** Controla si al hacer clic en una fila de combinación en la tabla se actualiza automáticamente la imagen principal del producto, el precio y otros detalles de la página del producto para reflejar esa combinación específica.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Al hacer clic en una fila, la visualización principal del producto se actualizará dinámicamente, dando al cliente una confirmación visual de su selección.
        -   *Cuando está deshabilitado:* La visualización principal del producto no cambiará al hacer clic en una fila; solo la entrada de cantidad y el botón Añadir al carrito de esa fila estarán activos.
    -   **Valor recomendado:** SÍ (mejora la experiencia del usuario al proporcionar retroalimentación visual).
    -   **Escenario / ejemplo de comerciante:** Un cliente hace clic en una combinación "Roja, Grande", y la imagen principal del producto cambia inmediatamente a la versión roja del producto.

#### Configuración de imagen

-   **Mostrar imagen**

    -   **Qué hace esta configuración:** Determina si se debe mostrar una imagen en miniatura para cada combinación en la tabla.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Aparecerá una columna de imagen, mostrando la imagen específica asociada a cada combinación (si está disponible).
        -   *Cuando está deshabilitado:* No se mostrará ninguna columna de imagen.
    -   **Valor recomendado:** SÍ (los elementos visuales son potentes para la selección de productos).
    -   **Escenario / ejemplo de comerciante:** Una tienda de ropa donde cada variación de color tiene una imagen distinta.
-   **Mostrar columna de imagen si hay al menos una combinación con imagen**

    -   **Qué hace esta configuración:** Controla la visibilidad de la columna de imagen en función de si alguna combinación tiene realmente una imagen específica asignada.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Si al menos una combinación tiene una imagen, la columna de imagen aparecerá para todas las combinaciones (mostrando la imagen predeterminada del producto para aquellas sin imágenes de combinación específicas).
        -   *Cuando está deshabilitado:* La columna de imagen solo aparecerá si *todas* las combinaciones tienen imágenes específicas, o podría no aparecer en absoluto si también usa "Usar imagen de producto predeterminada" con cuidado.
    -   **Valor recomendado:** SÍ (evita una columna de imagen vacía si solo unas pocas combinaciones tienen imágenes).
    -   **Escenario / ejemplo de comerciante:** Tiene 20 combinaciones, pero solo 5 tienen imágenes únicas. Esto asegura que la columna de imagen siga apareciendo, utilizando la imagen principal del producto para las otras 15.
-   **Usar imagen de producto predeterminada**

    -   **Qué hace esta configuración:** Si una combinación específica no tiene su propia imagen, esta configuración determina si se debe usar la imagen principal del producto como alternativa.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Las combinaciones sin imágenes específicas mostrarán la imagen principal del producto.
        -   *Cuando está deshabilitado:* Las combinaciones sin imágenes específicas mostrarán un marcador de posición o ninguna imagen.
    -   **Valor recomendado:** SÍ (asegura que todas las combinaciones tengan una representación visual).
    -   **Escenario / ejemplo de comerciante:** Un producto con muchas variaciones de tamaño pero solo una imagen por color. Esto asegura que todos los tamaños de un color específico muestren la imagen de color correcta.
-   **Habilitar zoom Fancybox**

    -   **Qué hace esta configuración:** Permite a los clientes hacer clic en las imágenes de combinación de la tabla para ver una versión más grande y ampliada en una ventana emergente (Fancybox).
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Al hacer clic en una imagen de combinación, se abrirá en una ventana emergente de Fancybox.
        -   *Cuando está deshabilitado:* Las imágenes no serán clicables para hacer zoom.
    -   **Valor recomendado:** SÍ (mejora la experiencia de visualización de imágenes).
    -   **Escenario / ejemplo de comerciante:** Un cliente quiere ver la textura o el detalle de una variación de color específica más de cerca.
-   **Tipo de imagen a mostrar**

    -   **Qué hace esta configuración:** Selecciona el tamaño/tipo de imagen (por ejemplo, `small_default`, `medium_default`) que se mostrará como miniaturas en la tabla de combinaciones.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando se cambia:* El tamaño de las imágenes en la tabla se actualizará al tipo de imagen seleccionado.
    -   **Valor recomendado:** `small_default` o `medium_default` (elija uno que se ajuste bien a su diseño de tabla sin ser demasiado grande o demasiado pequeño).
    -   **Escenario / ejemplo de comerciante:** Desea que las imágenes de la tabla sean ligeramente más grandes que el pequeño `small_default` pero no tan grandes como `large_default`.
-   **Tipo de imagen utilizada para ampliar la miniatura**

    -   **Qué hace esta configuración:** Selecciona el tamaño/tipo de imagen que se utilizará cuando se active la función de zoom Fancybox.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando se cambia:* La imagen mostrada en la ventana emergente de Fancybox será del tamaño seleccionado.
    -   **Valor recomendado:** `large_default` o `thickbox_default` (elija el tipo de imagen más grande y de mayor calidad para hacer zoom).
    -   **Escenario / ejemplo de comerciante:** Un cliente hace zoom en una imagen y espera ver una versión de alta resolución.

#### Configuración de visualización de atributos

-   **Método de visualización de atributos**

    -   **Qué hace esta configuración:** Controla cómo se muestran los nombres de los atributos (por ejemplo, "Talla", "Color") en el encabezado de la tabla.
    -   **Efecto de cambiar esta configuración:**
        -   *Opciones (por ejemplo, "Nombre completo", "Nombre corto", "ID"):* Cambia cómo aparecen los encabezados de los atributos.
    -   **Valor recomendado:** "Nombre completo" (más descriptivo para los clientes).
    -   **Escenario / ejemplo de comerciante:** Desea que "Talla" aparezca como "Talla" y no como "S" o "ID: 1".
-   **Asociaciones de atributos con la tienda (multitienda)**

    -   **Qué hace esta configuración:** En un entorno multitienda, esto le permite especificar qué grupos de atributos son relevantes para qué tiendas, evitando que aparezcan atributos irrelevantes.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está configurado:* Solo los atributos asociados con el contexto de la tienda actual se mostrarán en la tabla.
    -   **Valor recomendado:** Configure con cuidado si tiene una multitienda con diferentes catálogos de productos.
    -   **Escenario / ejemplo de comerciante:** La Tienda A vende ropa (Talla, Color), la Tienda B vende electrónica (Almacenamiento, RAM). Esto evita que "Almacenamiento" aparezca en la tabla de combinaciones de la Tienda A.
-   **Incluir etiqueta al nombre del atributo**

    -   **Qué hace esta configuración:** Añade el nombre del grupo de atributos como prefijo al valor del atributo (por ejemplo, "Talla: S", "Color: Rojo").
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Los valores de los atributos serán más descriptivos.
        -   *Cuando está deshabilitado:* Solo se mostrará el valor del atributo (por ejemplo, "S", "Rojo").
    -   **Valor recomendado:** SÍ (mejora la claridad, especialmente si los valores de los atributos no son autoexplicativos).
    -   **Escenario / ejemplo de comerciante:** Un producto tiene un valor de atributo "Estándar". ¿Es una talla estándar, un color estándar o un acabado estándar? "Acabado: Estándar" lo aclara.
-   **Atributo de color**

    -   **Qué hace esta configuración:** Le permite especificar qué grupo de atributos representa el "color" en su tienda. Esto es importante para que el módulo muestre correctamente las muestras de color o la lógica específica del color.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está seleccionado:* El módulo tratará los valores de este grupo de atributos como colores, mostrándolos potencialmente como muestras de color en lugar de texto.
    -   **Valor recomendado:** Seleccione su grupo de atributos "Color" principal.
    -   **Escenario / ejemplo de comerciante:** Tiene un grupo de atributos llamado "Color" con valores como "Rojo", "Azul", "Verde". Seleccionar este grupo asegura que se muestren como muestras de color reales.

#### Opciones de visualización

-   **Ocultar encabezado de tabla**

    -   **Qué hace esta configuración:** Elimina la fila de encabezado de la tabla de combinaciones (por ejemplo, "Imagen | Talla | Color | Precio | Cantidad").
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* La tabla comenzará directamente con las filas de combinación, sin títulos de columna.
        -   *Cuando está deshabilitado:* La fila de encabezado estará visible.
    -   **Valor recomendado:** NO (los encabezados suelen ser importantes para la claridad, a menos que su tabla sea muy simple y autoexplicativa).
    -   **Escenario / ejemplo de comerciante:** Para un producto muy simple con un solo atributo (por ejemplo, "Tamaño del paquete"), podría ocultar el encabezado si el contenido de la columna es obvio.
-   **Ocultar combinaciones agotadas**

    -   **Qué hace esta configuración:** Evita que las combinaciones que actualmente están agotadas se muestren en la tabla.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Solo las combinaciones en stock serán visibles, reduciendo el desorden y evitando la frustración del cliente.
        -   *Cuando está deshabilitado:* Las combinaciones agotadas seguirán mostrándose, a menudo con una etiqueta de "Agotado" o el botón "Añadir al carrito" deshabilitado.
    -   **Valor recomendado:** SÍ (generalmente mejor para la experiencia del usuario, a menos que desee mostrar todas las opciones para pedidos anticipados o notificaciones de reposición).
    -   **Escenario / ejemplo de comerciante:** Un modelo de zapato popular ha agotado la talla 10. Ocultarlo evita que los clientes intenten seleccionarlo.
-   **Ocultar combinaciones con precio = 0**

    -   **Qué hace esta configuración:** Excluye las combinaciones que tienen un precio de cero de la tabla.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Las combinaciones con precio cero no aparecerán.
        -   *Cuando está deshabilitado:* Las combinaciones con precio cero se listarán.
    -   **Valor recomendado:** SÍ (a menos que ofrezca intencionalmente combinaciones gratuitas, lo cual es raro).
    -   **Escenario / ejemplo de comerciante:** A veces, debido a una mala configuración, una combinación puede terminar con un precio cero. Ocultarlas evita confusiones.
-   **Mostrar solo combinaciones con imágenes**

    -   **Qué hace esta configuración:** Filtra la tabla para mostrar solo las combinaciones que tienen una imagen específica asignada.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Solo se listarán las combinaciones con imágenes únicas.
        -   *Cuando está deshabilitado:* Se mostrarán todas las combinaciones, independientemente de si tienen una imagen específica.
    -   **Valor recomendado:** NO (suele ser mejor mostrar todas las combinaciones, utilizando imágenes predeterminadas si es necesario, a menos que la diferenciación visual sea primordial).
    -   **Escenario / ejemplo de comerciante:** Si solo desea mostrar combinaciones que tienen diferencias visuales distintas y no ha subido imágenes para todas ellas.
-   **Mostrar precio**

    -   **Qué hace esta configuración:** Controla si el precio de cada combinación se muestra en la tabla.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Una columna "Precio" será visible.
        -   *Cuando está deshabilitado:* La columna de precio estará oculta.
    -   **Valor recomendado:** SÍ (el precio es un factor crítico para los clientes).
    -   **Escenario / ejemplo de comerciante:** Un cliente quiere comparar precios entre diferentes tamaños o materiales de un producto.
-   **Mostrar precio unitario**

    -   **Qué hace esta configuración:** Muestra el precio unitario (por ejemplo, precio por kg, por litro) para cada combinación, si corresponde.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Aparecerá una columna adicional de "Precio unitario".
        -   *Cuando está deshabilitado:* Esta columna no se mostrará.
    -   **Valor recomendado:** SÍ (si sus productos se venden por peso/volumen y el precio unitario es relevante).
    -   **Escenario / ejemplo de comerciante:** Vender granos de café en diferentes tamaños de bolsa, y los clientes quieren comparar el precio por 100g.
-   **Mostrar precio solo para clientes registrados**

    -   **Qué hace esta configuración:** Oculta los precios de las combinaciones a los visitantes que no han iniciado sesión en sus cuentas de cliente.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Los invitados no verán los precios; es posible que vean un mensaje que les pida que inicien sesión.
        -   *Cuando está deshabilitado:* Los precios son visibles para todos.
    -   **Valor recomendado:** NO (a menos que tenga una tienda B2B o estrategias de precios específicas que requieran inicio de sesión).
    -   **Escenario / ejemplo de comerciante:** Una tienda mayorista donde los precios se negocian o son específicos para cuentas comerciales registradas.
-   **Mostrar etiqueta de impuestos**

    -   **Qué hace esta configuración:** Muestra una etiqueta que indica si los precios mostrados incluyen o excluyen impuestos (por ejemplo, "Impuestos incl.", "Impuestos excl.").
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* El estado de los impuestos se indicará claramente junto a los precios.
        -   *Cuando está deshabilitado:* No se mostrará ninguna etiqueta de impuestos.
    -   **Valor recomendado:** SÍ (mejora la transparencia y cumple con los requisitos legales en muchas regiones).
    -   **Escenario / ejemplo de comerciante:** Los clientes en Europa esperan ver precios "Impuestos incl.", mientras que los clientes B2B pueden preferir "Impuestos excl.".

#### Otras claves de configuración (Avanzadas/Internas)

Estos ajustes suelen ser gestionados internamente por el módulo o son ajustados con menos frecuencia por los comerciantes.

-   `mypresta_updates`, `update_`, `updatev_`: Claves internas para actualizaciones del módulo y seguimiento de versiones.
-   `ctp_position`: Controla la posición del hook donde se muestra la tabla.
-   `ctp_lasttab`: Relacionado con la visualización de la tabla en una pestaña de producto.
-   `ctp_reference`, `ctp_ean`, `ctp_mpn`: Controlan la visualización de las columnas Referencia, EAN13/JAN y MPN.
-   `ctp_cname`: Controla la visualización del nombre de la combinación.
-   `ctp_atc`, `ctp_atcq`: Controlan el botón "Añadir al carrito" y la entrada de cantidad.
-   `ctp_ajax`: Determina si se usa AJAX para añadir al carrito.
-   `ctp_sort`: Opciones de ordenación para las combinaciones dentro de la tabla.
-   `ctp_quantity`, `ctp_quantity_sum`: Visualización de la cantidad en stock y la suma de cantidades.
-   `ctp_availability`, `ctp_availability_d`: Visualización del estado de disponibilidad y la fecha.
-   `ctp_imagetype`, `ctp_imagetype_zoom`, `ctp_grid_imagetype`, `ctp_grid_defimg`: Configuración del tipo de imagen (cubierto anteriormente).
-   `ctp_attributes_method`: Método de visualización de atributos (cubierto anteriormente).
-   `ctp_prices_tax`: Configuración de visualización de impuestos (cubierto anteriormente).
-   `ctp_color_method`: Cómo se muestran los atributos de color (por ejemplo, muestras).
-   `ctp_hide_default`, `ctp_hide_r`: Ocultar combinación predeterminada, ocultar combinaciones con precio cero (cubierto anteriormente).
-   `ctp_where`, `ctp_tabtype`: Ubicación de la tabla (hook, tipo de pestaña).
-   `ctp_quantity_pm`: Botones de más/menos para la entrada de cantidad.
-   `ctp_view_mode`: Modo de vista general de la tabla (tabla, cuadrícula, etc.).
-   `ctp_grid_row_attr`, `ctp_grid_col_attr`: Configuración para el diseño de cuadrícula (qué atributos forman filas/columnas).

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### AdminCombinationstabSearchController (Back Office > Módulos > Tabla de combinaciones de la página de producto > Buscar)

Este controlador proporciona una interfaz dedicada dentro del back office de PrestaShop, probablemente para gestionar o buscar combinaciones, potencialmente en varios productos, o para una configuración avanzada relacionada con la visualización de combinaciones.

-   **Nombre de la pantalla y ubicación del menú:** Normalmente encontrará un nuevo elemento de menú en **Módulos > Tabla de combinaciones de la página de producto** (o similar, según la versión de PrestaShop) etiquetado como "Buscar" o "Búsqueda de combinaciones".
-   **Acciones y configuraciones disponibles:** Esta pantalla probablemente presenta una cuadrícula o vista de gestión de combinaciones de productos. Podría permitirle:
    -   Buscar combinaciones específicas por atributos, referencia, EAN o nombre de producto.
    -   Ver detalles de combinaciones, como stock, precio y producto asociado.
    -   Potencialmente realizar acciones masivas como actualizar el stock o el precio de múltiples combinaciones (aunque esto a menudo se maneja en la página de producto principal de PrestaShop).
    -   Esta pantalla es principalmente para *gestionar* y *ver* datos de combinaciones de forma estructurada, separada de la página de edición del producto principal.
-   **Efecto de los cambios:** Cualquier cambio realizado aquí (si la edición está habilitada) actualizaría directamente los datos de la combinación en su base de datos de PrestaShop, afectando los precios, el stock y la disponibilidad en el front office.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esta pantalla para auditar rápidamente los datos de las combinaciones, encontrar combinaciones específicas o verificar los niveles de stock sin navegar a las páginas de productos individuales. Es una herramienta potente para tiendas con un gran catálogo de productos y combinaciones.

#### index.php (combinationstab/controllers/admin/index.php)

Este archivo suele servir como marcador de posición o como redireccionador para el controlador de administración principal del módulo. Podría simplemente cargar el `AdminCombinationstabSearchController` o presentar una página de aterrizaje básica para la sección de administración del módulo. Por lo general, no tiene configuraciones directas, pero actúa como un punto de entrada.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | Activar función de filtros | SÍ | Habilita filtros de atributos para la tabla de combinaciones. |
| | Resaltar mejor precio | SÍ | Resalta visualmente la combinación de menor precio. |
| | Mostrar columna de ahorro | SÍ | Muestra la cantidad/porcentaje de descuento en una columna dedicada. |
| | Consejo de umbral de descuento por cantidad | SÍ | Muestra consejos para descuentos basados en la cantidad. |
| | Diseño de tarjeta móvil | SÍ | Optimiza la visualización de la tabla para dispositivos móviles. |
| | Orden de las columnas | Personalizable | Define la secuencia de columnas en la tabla. |
| | Hacer clic y cambiar combinación | SÍ | Actualiza la imagen/detalles principales del producto al hacer clic en la fila. |
| | Mostrar imagen | SÍ | Muestra imágenes de combinación en la tabla. |
| | Mostrar columna de imagen si hay al menos una combinación con imagen | SÍ | Asegura que la columna de imagen aparezca si alguna combinación tiene una imagen. |
| | Usar imagen de producto predeterminada | SÍ | Vuelve a la imagen principal del producto si la combinación no tiene una imagen específica. |
| | Habilitar zoom Fancybox | SÍ | Permite el zoom de las imágenes de combinación. |
| | Tipo de imagen a mostrar | `medium_default` | Establece el tamaño de la miniatura en la tabla. |
| | Tipo de imagen utilizada para ampliar la miniatura | `large_default` | Establece el tamaño de la imagen de zoom. |
| | Método de visualización de atributos | Nombre completo | Cómo se etiquetan los encabezados de los atributos (por ejemplo, "Talla"). |
| | Asociaciones de atributos con la tienda (multitienda) | Configurar según sea necesario | Filtra atributos por tienda en multitienda. |
| | Incluir etiqueta al nombre del atributo | SÍ | Añade el nombre del grupo de atributos al valor (por ejemplo, "Talla: S"). |
| | Atributo de color | Seleccione su atributo de Color | Identifica el atributo de color para una visualización especial. |
| | Ocultar encabezado de tabla | NO | Mantiene los títulos de las columnas visibles para mayor claridad. |
| | Ocultar combinaciones agotadas | SÍ | Elimina las combinaciones no disponibles de la tabla. |
| | Ocultar combinaciones con precio = 0 | SÍ | Elimina las combinaciones con precio cero. |
| | Mostrar solo combinaciones con imágenes | NO | Muestra todas las combinaciones, utilizando imágenes predeterminadas si es necesario. |
| | Mostrar precio | SÍ | Muestra el precio de cada combinación. |
| | Mostrar precio unitario | SÍ (si aplica) | Muestra el precio por unidad (por ejemplo, por kg). |
| | Mostrar precio solo para clientes registrados | NO | Hace que los precios sean visibles para todos los visitantes. |
| | Mostrar etiqueta de impuestos | SÍ | Indica si los precios incluyen/excluyen impuestos. |
| **AdminCombinationstabSearchController** | Vista de cuadrícula / gestión | N/A | Buscar, ver y potencialmente gestionar combinaciones en todos los productos. |

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: La tabla de combinaciones no aparece en la página de mi producto.**
R1:

-   **Verificar la posición del módulo:** Vaya a **Diseño > Posiciones** (o **Módulos > Posiciones** en versiones anteriores de PrestaShop) en su Back Office. Busque el módulo "Tabla de combinaciones de la página de producto". Asegúrese de que esté enganchado a un hook de visualización relevante como `displayProductFooter`, `displayProductExtraContent` o `displayProductTabContent`. Si no lo está, haga clic en "Trasplantar un módulo" y añádalo al hook deseado.
-   **Configuración del módulo:** Vuelva a verificar la página de configuración del módulo para asegurarse de que esté habilitado y no esté oculto por otras configuraciones (por ejemplo, "Ocultar combinaciones con precio = 0" podría ocultar todas si todas son cero).
-   **El producto tiene combinaciones:** Asegúrese de que el producto que está viendo realmente tenga combinaciones definidas en la configuración de su producto.
-   **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché". A veces, el contenido antiguo en caché impide la visualización de nuevos módulos.

**P2: Las imágenes de mis combinaciones no aparecen o tienen el tamaño incorrecto.**
R2:

-   **Configuración de imagen:** Revise las configuraciones "Tipo de imagen a mostrar" y "Tipo de imagen utilizada para ampliar la miniatura" en la configuración del módulo. Asegúrese de haber seleccionado tipos de imagen apropiados que existan en su tema de PrestaShop.
-   **Imágenes de combinación subidas:** Verifique que realmente haya subido imágenes específicas para sus combinaciones de productos en la pestaña "Combinaciones" del producto en el Back Office. Si no, el módulo recurrirá a la imagen principal del producto (si "Usar imagen de producto predeterminada" está habilitado).
-   **Regenerar miniaturas:** Si cambió los tipos de imagen o subió nuevas imágenes, vaya a **Diseño > Configuración de imágenes** (o **Preferencias > Imágenes**) y haga clic en "Regenerar miniaturas" para los tipos de imagen relevantes (por ejemplo, `medium_default`, `large_default`).

**P3: La tabla se ve extraña o desalineada en mi tema personalizado.**
R3:

-   **Conflictos de CSS:** Los temas personalizados a veces tienen estilos CSS conflictivos. Este módulo intenta ser compatible, pero podrían ser necesarios pequeños ajustes.
-   **Contactar con soporte:** Si se siente cómodo con CSS, puede inspeccionar los elementos utilizando las herramientas de desarrollo de su navegador e intentar anular los estilos conflictivos. De lo contrario, póngase en contacto con el soporte de MyPresta.eu con los detalles de su tema y una captura de pantalla; a menudo pueden proporcionar una solución rápida.
-   **Actualizaciones del módulo:** Asegúrese de que está ejecutando la última versión del módulo, ya que las mejoras de compatibilidad a menudo se incluyen en las actualizaciones.

**P4: Los precios no se muestran correctamente o están ocultos.**
R4:

-   **Configuración de visualización de precios:** Verifique "Mostrar precio" y "Mostrar precio solo para clientes registrados" en la configuración del módulo. Si esta última está habilitada, asegúrese de haber iniciado sesión como cliente para ver los precios.
-   **Precios del núcleo de PrestaShop:** Verifique que los precios de sus combinaciones estén configurados correctamente en la pestaña "Combinaciones" del producto.
-   **Configuración de impuestos:** Verifique "Mostrar etiqueta de impuestos" y su configuración general de impuestos de PrestaShop (**Internacional > Impuestos**) para asegurarse de que los precios se calculen y muestren como se espera (impuestos incl./excl.).

**P5: ¿Cómo cambio el orden de los atributos en la tabla?**
R5:

-   La configuración "Orden de las columnas" del módulo le permite reorganizar las columnas. Para el orden de los atributos en sí (por ejemplo, "Talla" antes de "Color"), esto se gestiona normalmente en el núcleo de PrestaShop: **Catálogo > Atributos y características > Atributos** y **Grupos de atributos**. El orden que establezca allí suele influir en cómo aparecen en la tabla del módulo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Tabla de combinaciones de la página de producto" (`combinationstab`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando en gran medida los hooks para la visualización en el front-office y los controladores de administración personalizados para la configuración avanzada y la gestión de datos. Se integra profundamente con los datos principales de productos y combinaciones de PrestaShop, renderizando dinámicamente tablas o cuadrículas HTML utilizando plantillas Smarty. Se utiliza AJAX para funciones como "Añadir al carrito" y el cambio de combinaciones para una experiencia de usuario fluida. El módulo no introduce clases `ObjectModel` personalizadas, sino que trabaja directamente con los objetos `Product` y `Combination` existentes.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

Estos controladores manejan solicitudes AJAX específicas o funcionalidades dedicadas del front-office.

-   `controllers/front/BackInStock.php`
    -   **Nombre de la clase y clase padre:** `CombinationstabBackInStockModuleFrontController` extiende `ModuleFrontController`.
    -   **Responsabilidad:** Probablemente maneja solicitudes AJAX relacionadas con notificaciones de "reposición de stock" para combinaciones específicas. Esto podría implicar el envío de un formulario para registrarse para recibir notificaciones cuando una combinación agotada esté disponible.
-   `controllers/front/CsvImport.php`
    -   **Nombre de la clase y clase padre:** `CombinationstabCsvImportModuleFrontController` extiende `ModuleFrontController`.
    -   **Responsabilidad:** Sugiere funcionalidad para importar datos de combinación a través de CSV desde el front-office, posiblemente para grupos de usuarios específicos o escenarios B2B. Esto implicaría analizar archivos CSV y actualizar las combinaciones de productos.
-   `controllers/front/Export.php`
    -   **Nombre de la clase y clase padre:** `CombinationstabExportModuleFrontController` extiende `ModuleFrontController`.
    -   **Responsabilidad:** Proporciona funcionalidad para exportar datos de combinación, potencialmente para productos específicos o conjuntos filtrados, probablemente en formato CSV o similar. Útil para B2B o análisis de datos.
-   `controllers/front/index.php`
    -   **Nombre de la clase y clase padre:** `CombinationstabIndexModuleFrontController` extiende `ModuleFrontController`.
    -   **Responsabilidad:** A menudo un marcador de posición o un despachador predeterminado. Podría manejar solicitudes AJAX generales relacionadas con la tabla de combinaciones que no encajan en controladores más específicos, o simplemente redirigir.
-   `controllers/front/PriceCalculator.php`
    -   **Nombre de la clase y clase padre:** `CombinationstabPriceCalculatorModuleFrontController` extiende `ModuleFrontController`.
    -   **Responsabilidad:** Maneja solicitudes AJAX para calcular y devolver dinámicamente los precios de las combinaciones, especialmente relevante para descuentos por cantidad o reglas de precios complejas, asegurando actualizaciones de precios en tiempo real sin recargas de página.
-   `controllers/front/Reorder.php`
    -   **Nombre de la clase y clase padre:** `CombinationstabReorderModuleFrontController` extiende `ModuleFrontController`.
    -   **Responsabilidad:** Probablemente facilita la reordenación de combinaciones compradas anteriormente, potencialmente desde la página de la cuenta de un cliente o una lista dedicada de "reordenación".
-   `controllers/front/Wishlist.php`
    -   **Nombre de la clase y clase padre:** `CombinationstabWishlistModuleFrontController` extiende `ModuleFrontController`.
    -   **Responsabilidad:** Gestiona las interacciones AJAX con una función de lista de deseos integrada en la tabla de combinaciones, permitiendo a los clientes añadir combinaciones específicas a su lista de deseos.

#### Controladores de administración de Back-Office

Estos controladores proporcionan la interfaz administrativa para el módulo.

-   `controllers/admin/AdminCombinationstabSearchController.php`
    -   **Nombre de la pestaña y entidad gestionada:** "Búsqueda de combinaciones" (o similar, accesible a través del menú del módulo). Gestiona las combinaciones de `Product`.
    -   **Responsabilidad:** Implementa una interfaz de búsqueda y gestión para las combinaciones de productos. Este controlador probablemente utiliza un `HelperList` o `HelperForm` para mostrar una cuadrícula filtrable y ordenable de combinaciones, permitiendo a los administradores encontrar y potencialmente editar rápidamente los datos de las combinaciones (por ejemplo, stock, precio, referencia) sin navegar a las páginas de productos individuales. También podría manejar acciones masivas.
-   `controllers/admin/index.php`
    -   **Nombre de la pestaña y entidad gestionada:** N/A (punto de entrada).
    -   **Responsabilidad:** Un patrón común para los directorios de controladores de administración. Este archivo suele servir como punto de entrada predeterminado o como redireccionador al `AdminCombinationstabSearchController` principal. Por lo general, no contiene lógica directa, pero asegura que el elemento del menú de administración apunte a un controlador válido.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo indica que no hay clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo extiende principalmente las funcionalidades y objetos principales existentes de PrestaShop (`Product`, `Combination`, `Attribute`, `AttributeGroup`) en lugar de introducir nuevos modelos de datos. Toda la lógica de negocio probablemente está encapsulada dentro del archivo principal `combinationstab.php` y sus controladores.

### 4.4 Activos JavaScript (`views/js/`)

El módulo utiliza una variedad de archivos JavaScript para proporcionar funcionalidad dinámica en el front-office y el back-office.

-   `combinationstab/js/admin.js`
    -   **Alcance:** Back-office.
    -   **Detalles:** Maneja la lógica JavaScript para las páginas de administración del módulo, incluidas las interacciones de formularios, las llamadas AJAX para las actualizaciones de configuración y, potencialmente, los elementos dinámicos dentro de la interfaz `AdminCombinationstabSearchController`.
-   `combinationstab/js/atc.js`
    -   **Alcance:** Front-office.
    -   **Detalles:** Gestiona la funcionalidad "Añadir al carrito" para la tabla de combinaciones. Vincula eventos de clic a los botones "Añadir al carrito", maneja las entradas de cantidad y envía solicitudes AJAX al controlador del carrito de PrestaShop para añadir las combinaciones seleccionadas (potencialmente varias a la vez) sin recargar la página.
-   `combinationstab/js/combinationstab-switch.js`
    -   **Alcance:** Front-office.
    -   **Detalles:** Implementa la función "Hacer clic y cambiar combinación". Escucha los clics en las filas de combinación de la tabla y actualiza dinámicamente la imagen principal del producto, el precio y otros detalles del producto en la página para reflejar la combinación seleccionada.
-   `combinationstab/js/combinationstab.js`
    -   **Alcance:** Front-office.
    -   **Detalles:** El archivo JavaScript principal del front-office para la tabla de combinaciones. Inicializa la tabla, maneja las interacciones generales, potencialmente gestiona la visualización del stock, la disponibilidad y las actualizaciones de precios basadas en la entrada o selección del usuario.
-   `combinationstab/js/ctp-extras.js`
    -   **Alcance:** Front-office.
    -   **Detalles:** Contiene funcionalidades JavaScript adicionales, no centrales, para la tabla de combinaciones, como la visualización de información sobre herramientas, pequeñas mejoras de la interfaz de usuario o interacciones específicas no cubiertas por los scripts principales.
-   `combinationstab/js/ctp-filters.js`
    -   **Alcance:** Front-office.
    -   **Detalles:** Implementa la lógica de filtrado para la tabla de combinaciones. Escucha los cambios en los menús desplegables o campos de entrada de filtros, oculta/muestra dinámicamente las filas de la tabla basándose en los valores de los atributos seleccionados y actualiza las combinaciones visibles.
-   `combinationstab/js/ctp-mobile.js`
    -   **Alcance:** Front-office.
    -   **Detalles:** Maneja el comportamiento responsivo de la tabla de combinaciones, implementando específicamente la función "Diseño de tarjeta móvil". Detecta el tamaño de la pantalla y transforma la tabla en un diseño basado en tarjetas para una mejor usabilidad móvil.
-   `combinationstab/js/ctp-wishlist-toast.js`
    -   **Alcance:** Front-office.
    -   **Detalles:** Proporciona retroalimentación visual (por ejemplo, una notificación toast) cuando se añade una combinación a una lista de deseos, mejorando la experiencia del usuario.
-   `combinationstab/lib/searchTool/views/js/autocomplete.js`
    -   **Alcance:** Back-office (probablemente).
    -   **Detalles:** Proporciona funcionalidad de autocompletado, probablemente para campos de búsqueda de productos o combinaciones dentro de las interfaces de administración del módulo (por ejemplo, `AdminCombinationstabSearchController`).
-   `combinationstab/views/js/wishlist.js`
    -   **Alcance:** Front-office.
    -   **Detalles:** JavaScript dedicado para la integración de la lista de deseos, que maneja las llamadas AJAX para añadir/eliminar elementos de la lista de deseos directamente desde la tabla de combinaciones.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo incluye varios archivos CSS tanto para el estilo del front-office como para la administración del back-office.

-   `combinationstab/css/admin.css`
    -   **Alcance:** Estilo del formulario de administración del Back-office.
    -   **Detalles:** Estiliza la página de configuración del módulo y cualquier interfaz de administración personalizada (como `AdminCombinationstabSearchController`), asegurando una apariencia consistente dentro del back office de PrestaShop.
-   `combinationstab/css/combinationstab.css`
    -   **Alcance:** Estilo del cliente del Front-office.
    -   **Detalles:** Contiene el estilo principal para la tabla de combinaciones, incluido el diseño de la tabla, el relleno de las celdas, la alineación del texto y la capacidad de respuesta básica.
-   `combinationstab/css.css`
    -   **Alcance:** Estilo del cliente del Front-office.
    -   **Detalles:** Potencialmente una hoja de estilo más antigua o complementaria para el front-office, o anulaciones específicas.
-   `combinationstab/lib/searchTool/views/css/autocomplete.css`
    -   **Alcance:** Back-office (probablemente).
    -   **Detalles:** Estilos para los campos de búsqueda de autocompletado utilizados en el panel de administración.
-   `combinationstab/views/css/ctp-admin.css`
    -   **Alcance:** Estilo del formulario de administración del Back-office.
    -   **Detalles:** Estilo de administración adicional o específico, potencialmente para nuevas funciones o anulaciones de `admin.css`.
-   `combinationstab/views/css/wishlist.css`
    -   **Alcance:** Estilo del cliente del Front-office.
    -   **Detalles:** Estilos para el botón de la lista de deseos y cualquier elemento asociado dentro de la tabla de combinaciones.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty para renderizar todas sus vistas de front-office y back-office.

#### Plantillas de hook (`views/templates/hook/`)

Estas plantillas están diseñadas para ser renderizadas cuando se ejecutan hooks específicos de PrestaShop.

-   `views/templates/hook/columns/cells.tpl`
    -   **Hook:** Probablemente renderizado dentro de la plantilla principal de la tabla de combinaciones.
    -   **Salida:** Define la estructura y el contenido de las celdas de datos individuales dentro de las filas de la tabla (por ejemplo, mostrando valores de atributos, precio, entrada de cantidad).
-   `views/templates/hook/columns/headers.tpl`
    -   **Hook:** Probablemente renderizado dentro de la plantilla principal de la tabla de combinaciones.
    -   **Salida:** Define las celdas de encabezado para la tabla de combinaciones, mostrando títulos de columna como "Imagen", "Talla", "Precio".
-   `views/templates/hook/columns/_wishlist_btn.tpl`
    -   **Hook:** Integrado en las filas de combinación.
    -   **Salida:** Renderiza el botón o icono "Añadir a la lista de deseos" para cada combinación en la tabla.
-   `views/templates/hook/customer_account.tpl`
    -   **Hook:** `displayCustomerAccount`
    -   **Salida:** Añade un enlace o bloque a la página de la cuenta del cliente, potencialmente para acceder a listas de reordenación, datos exportados o gestión de la lista de deseos.
-   `views/templates/hook/grid/_axis_label.tpl`
    -   **Hook:** Utilizado internamente cuando `ctp_view_mode` se establece en un diseño de cuadrícula.
    -   **Salida:** Renderiza etiquetas para los ejes (filas/columnas) de una visualización de combinación de estilo cuadrícula.
-   `views/templates/hook/grid/_cell.tpl`
    -   **Hook:** Utilizado internamente cuando `ctp_view_mode` se establece en un diseño de cuadrícula.
    -   **Salida:** Renderiza celdas individuales dentro de una visualización de combinación de estilo cuadrícula, que contiene detalles de la combinación.
-   `views/templates/hook/productfooter.tpl`
    -   **Hook:** `displayProductFooter`
    -   **Salida:** La plantilla principal para renderizar la tabla de combinaciones cuando se coloca debajo del contenido principal del producto. Esta es a menudo la ubicación predeterminada o más común.
-   `views/templates/hook/productfooter_grid.tpl`
    -   **Hook:** `displayProductFooter` (condicional al modo de vista).
    -   **Salida:** Una plantilla alternativa para `displayProductFooter` específicamente para renderizar las combinaciones en un diseño de cuadrícula en lugar de una tabla tradicional.
-   `views/templates/hook/quickViewScripts.tpl`
    -   **Hook:** Potencialmente `displayHeader` o `actionFrontControllerSetMedia` (para modales de vista rápida).
    -   **Salida:** Incluye el JavaScript necesario o inicializa la funcionalidad del módulo específicamente para los modales de vista rápida del producto, asegurando que la tabla de combinaciones funcione dentro de estas ventanas emergentes.
-   `views/templates/hook/tab.tpl`
    -   **Hook:** `displayProductTabContent` (o similar para pestañas de producto).
    -   **Salida:** Renderiza la tabla de combinaciones dentro de una pestaña de producto dedicada en la página del producto.
-   `views/templates/hook/volume_discounts.tpl`
    -   **Hook:** Integrado en las filas de combinación o como una información sobre herramientas.
    -   **Salida:** Muestra información sobre descuentos por cantidad para combinaciones específicas.
-   `views/templates/hook/_filters.tpl`
    -   **Hook:** Renderizado encima de la tabla de combinaciones.
    -   **Salida:** Renderiza la interfaz de filtrado de atributos para la tabla de combinaciones.
-   `views/templates/hook/_toolbar.tpl`
    -   **Hook:** Renderizado encima de la tabla de combinaciones.
    -   **Salida:** Renderiza una barra de herramientas, que potencialmente contiene filtros, búsqueda u otros elementos interactivos para la tabla de combinaciones.

#### Plantillas de administración (`views/templates/admin/`)

Estas plantillas se utilizan para las pantallas de configuración y gestión del back-office del módulo.

-   `views/templates/admin/b2b.tpl`
    -   **Salida:** Plantilla para configuraciones o funciones específicas de B2B dentro del panel de administración.
-   `views/templates/admin/b2b_groups.tpl`
    -   **Salida:** Plantilla para gestionar grupos de clientes B2B o sus configuraciones específicas de precios/visibilidad.
-   `views/templates/admin/column_editor.tpl`
    -   **Salida:** Proporciona una interfaz para que los administradores personalicen el orden y la visibilidad de las columnas en la tabla de combinaciones del front-office.
-   `views/templates/admin/getCombinations.tpl`
    -   **Salida:** Utilizado por `AdminCombinationstabSearchController` para mostrar una lista o cuadrícula de combinaciones.
-   `views/templates/admin/getProducts.tpl`
    -   **Salida:** Utilizado por `AdminCombinationstabSearchController` u otras herramientas de administración para mostrar una lista de productos.
-   `views/templates/admin/grid_block_editor.tpl`
    -   **Salida:** Interfaz para configurar la visualización de combinaciones de estilo cuadrícula, definiendo potencialmente qué atributos forman filas y columnas.
-   `views/templates/admin/menu.tpl`
    -   **Salida:** Renderiza los elementos del submenú del módulo dentro del back office de PrestaShop.
-   `views/templates/admin/overrides_entity.tpl`
    -   **Salida:** Plantilla para gestionar anulaciones específicas de entidades (por ejemplo, configuraciones específicas de productos para la tabla).
-   `views/templates/admin/overrides_fields.tpl`
    -   **Salida:** Plantilla para gestionar anulaciones específicas de campos.
-   `views/templates/admin/overrides_list.tpl`
    -   **Salida:** Plantilla para listar y gestionar varias anulaciones configuradas para el módulo.
-   `views/templates/admin/presets.tpl`
    -   **Salida:** Interfaz para guardar y cargar preajustes de configuración para la tabla de combinaciones.
-   `views/templates/admin/selectedProducts.tpl`
    -   **Salida:** Muestra una lista de productos que han sido seleccionados para configuraciones o anulaciones específicas del módulo.
-   `views/templates/admin/subtabs.tpl`
    -   **Salida:** Renderiza las pestañas de subnavegación dentro de la interfaz de configuración del módulo.
-   `views/templates/admin/tabs.tpl`
    -   **Salida:** Renderiza las pestañas de navegación principales para la configuración del módulo.
-   `views/templates/admin/tabstype.tpl`
    -   **Salida:** Opciones de configuración relacionadas con cómo se muestra la tabla de combinaciones dentro de las pestañas del producto.

#### Plantillas de Front-office (`views/templates/front/`)

-   `views/templates/front/wishlist.tpl`
    -   **Salida:** Renderiza la interfaz de la lista de deseos del front-office, potencialmente una página dedicada o un modal, mostrando los elementos añadidos a la lista de deseos a través de la tabla de combinaciones.

#### Otras plantillas

-   `combinationstab/lib/searchTool/views/scripts.tpl`
    -   **Salida:** Incluye fragmentos de JavaScript o inicializa scripts para la funcionalidad de la herramienta de búsqueda.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

El dossier del módulo indica que no hay archivos SQL personalizados. Esto implica que el módulo utiliza principalmente la tabla `ps_configuration` de PrestaShop para almacenar su configuración y se basa en tablas principales existentes como `ps_product_attribute`, `ps_product_attribute_combination`, `ps_product_attribute_shop`, `ps_stock_available`, etc., para los datos de combinación.

-   **`ps_configuration`**: Almacena todas las configuraciones del módulo (por ejemplo, `CTP_POSITION`, `CTP_IMAGE`, `CTP_PRICE_LOGGED`, `CTP_MOBILE_CARD_LAYOUT`).

#### Tabla de Hooks registrados

El módulo se registra en varios hooks de PrestaShop para inyectar su contenido y funcionalidad.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `ActionAdminControllerSetMedia` | Cuando se inicializa un controlador de administración y se establecen los medios (JS/CSS). | Inyecta JS/CSS específicos del módulo en el Back Office. |
| `displayRightColumn` | Renderiza contenido en la columna derecha del front office. | Muestra la tabla de combinaciones en la columna derecha (menos común para tablas). |
| `displayProductFooter` | Renderiza contenido debajo de la información principal del producto en la página del producto. | Hook principal para mostrar la tabla de combinaciones debajo del producto. |
| `displayHeader` | Renderiza contenido en la sección `<head>` del front office. | Inyecta JS/CSS específicos del módulo, metaetiquetas u otros elementos de la cabecera para la funcionalidad del front office. |
| `displayProductExtraContent` | Renderiza bloques de contenido adicionales en la página del producto. | Proporciona flexibilidad para colocar la tabla de combinaciones en un bloque de contenido personalizado. |
| `displayRightColumnProduct` | Renderiza contenido en la columna derecha específicamente en la página del producto. | Similar a `displayRightColumn` pero dirigido a páginas de producto. |
| `displayCustomerAccount` | Renderiza contenido en la página de la cuenta del cliente. | Añade enlaces o información relacionada con reordenación, listas de deseos o exportaciones. |
| `actionUpdateQuantity` | Después de que se actualiza la cantidad (stock) de un producto. | Potencialmente activa actualizaciones en la visualización de la tabla de combinaciones (por ejemplo, estado "agotado"). |
| `displayProductListFunctionalButtons` | Renderiza botones en listados de productos (por ejemplo, páginas de categoría). | Podría añadir botones de vista rápida o comparación relacionados con las combinaciones. |
| `displayExtraLeft` | Renderiza contenido en una columna izquierda extra (si el tema lo admite). | Otra opción de ubicación para la tabla de combinaciones. |
| `CombinationsTable` | **Hook personalizado** | Un hook personalizado definido por el propio módulo, que permite que otros módulos o temas se integren o anulen su salida de tabla. |
| `displayLeftColumnProduct` | Renderiza contenido en la columna izquierda específicamente en la página del producto. | Similar a `displayRightColumnProduct` pero para la columna izquierda. |
| `displayProductTabContent` | Renderiza contenido dentro de una pestaña de producto. | Muestra la tabla de combinaciones en una pestaña de producto dedicada. |
| `displayCombinationsTable` | **Hook personalizado** | Otro hook personalizado, probablemente para la renderización principal de la tabla de combinaciones, que ofrece una alternativa a `displayProductFooter`. |
| `displayProductActions` | Renderiza contenido cerca del botón "Añadir al carrito" en la página del producto. | Podría usarse para un selector de combinación compacto o botones de adición rápida. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, soporte técnico y cualquier pregunta relacionada con el módulo "Tabla de combinaciones de la página de producto", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está listo para ayudarle.

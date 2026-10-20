---
title: "Mostrar etiquetas en la página de producto - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Mostrar etiquetas en la página de producto' de MyPresta.eu."
sidebar:
  label: "Mostrar etiquetas en la página de producto - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Show tags on product page en MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-tags-on-product-page.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/show-tags-on-product-page/)
>
> ---


# Mostrar etiquetas en la página de producto

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL) que se encuentran típicamente en cualquier entorno de alojamiento PrestaShop moderno.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Este módulo presenta una página de configuración sencilla, que le permite habilitar o deshabilitar rápidamente su funcionalidad y elegir dónde aparecerán las etiquetas en sus páginas de producto.

**Acceso:** Navegue a **Módulos > Gestor de módulos**, busque "Mostrar etiquetas en la página de producto" y haga clic en "Configurar".

#### **Habilitar / Deshabilitar Módulo**

- **Qué hace esta configuración:** Este es el interruptor principal para la funcionalidad del módulo.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado:* El módulo comenzará a mostrar las etiquetas de producto en las páginas de producto de su front office según el hook elegido.
  - *Cuando está deshabilitado:* El módulo dejará de mostrar las etiquetas de producto. Todas las demás configuraciones se guardarán pero estarán inactivas.
- **Valor recomendado:** SÍ
- **Escenario / ejemplo de comerciante:** Desea probar el módulo o ocultar temporalmente las etiquetas durante un rediseño del sitio. Lo deshabilitaría y luego lo volvería a habilitar cuando esté listo.

#### **Seleccionar Hook para Mostrar Etiquetas**

- **Qué hace esta configuración:** Esta configuración crucial determina *dónde* en la página de su producto se mostrarán las etiquetas. PrestaShop utiliza "hooks" como puntos específicos en el código de la página donde los módulos pueden insertar su contenido.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en `displayProductButtons` (PrestaShop 1.7+):* Las etiquetas aparecerán típicamente cerca del botón "Añadir al carrito" u otros botones de acción del producto. Esta suele ser una ubicación prominente y efectiva.
  - *Cuando se establece en `displayProductExtraContent` (PrestaShop 1.7+):* Las etiquetas aparecerán en una sección dedicada para contenido extra del producto, a menudo debajo de la información principal del producto o dentro de una pestaña.
  - *Cuando se establece en `displayFooterProduct` (PrestaShop 1.7+):* Las etiquetas aparecerán en la parte inferior de la página del producto, a menudo encima del pie de página de todo el sitio web.
  - *Cuando se establece en `displayLeftColumnProduct` (PrestaShop 1.7+):* Las etiquetas aparecerán en la columna izquierda específicamente en la página del producto.
  - *Cuando se establece en `displayRightColumnProduct` (PrestaShop 1.7+):* Las etiquetas aparecerán en la columna derecha específicamente en la página del producto.
  - *Otros hooks (por ejemplo, `displayProductTab`, `displayProductTabContent`, `displayFooter`):* La ubicación exacta dependerá de la implementación de estos hooks en su tema. `displayFooter` colocaría las etiquetas en el pie de página general del sitio web, lo que generalmente no es específico del producto.
- **Valor recomendado:** `displayProductButtons` o `displayProductExtraContent` son generalmente los más efectivos para la visibilidad y el contexto. Experimente para ver qué se ve mejor con su tema.
- **Escenario / ejemplo de comerciante:** Desea que las etiquetas sean muy visibles para fomentar el descubrimiento inmediato de productos similares, por lo que elige `displayProductButtons`. Si prefiere que sean menos intrusivas y parte de información suplementaria, `displayProductExtraContent` podría ser mejor.

#### **Título para el Bloque de Etiquetas**

- **Qué hace esta configuración:** Esto le permite establecer un título personalizado que aparecerá encima de la lista de etiquetas en la página del producto.
- **Efecto de cambiar esta configuración:**
  - *Cuando se introduce un título (por ejemplo, "Etiquetas de producto", "Palabras clave relacionadas"):* Este título se mostrará encima de la lista de etiquetas, proporcionando un encabezado claro para sus clientes.
  - *Cuando se deja vacío:* No se mostrará ningún título, y solo aparecerá la lista de etiquetas.
- **Valor recomendado:** "Etiquetas de producto" o "Palabras clave"
- **Escenario / ejemplo de comerciante:** Desea etiquetar claramente la sección para que los clientes entiendan su propósito. Establecer el título en "Etiquetas relacionadas" ayuda a guiar su interacción.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar Módulo | SÍ | Activa/desactiva la funcionalidad de visualización de etiquetas del módulo. |
| Configuración del módulo | Seleccionar Hook para Mostrar Etiquetas | `displayProductButtons` o `displayProductExtraContent` | Determina la posición exacta de las etiquetas en la página del producto. |
| Configuración del módulo | Título para el Bloque de Etiquetas | "Etiquetas de producto" | Establece un encabezado para las etiquetas mostradas, mejorando la claridad para los clientes. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He instalado y configurado el módulo, pero las etiquetas no aparecen en las páginas de mis productos. ¿Qué ocurre?**
**R1:**

- **Verificar el estado del módulo:** Asegúrese de que el módulo esté "Habilitado" en su configuración.
- **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). PrestaShop a menudo almacena contenido en caché, y la nueva salida del módulo podría no aparecer hasta que se borre la caché.
- **Verificar etiquetas de producto:** Asegúrese de que el producto específico que está viendo tenga etiquetas asignadas. Edite el producto en el Back Office y verifique la pestaña "SEO" o "Etiquetas".
- **Compatibilidad del tema:** Algunos temas altamente personalizados podrían anular los hooks estándar de PrestaShop o tener diseños únicos. Intente cambiar temporalmente al tema predeterminado de PrestaShop (por ejemplo, Classic) para ver si aparecen las etiquetas. Si lo hacen, su tema personalizado podría requerir un pequeño ajuste (ver P3).
- **Selección de hook:** Verifique que haya seleccionado un hook apropiado en la configuración del módulo. Algunos hooks podrían no ser renderizados por su tema en una ubicación visible.

**P2: Las etiquetas se muestran, pero se ven simples o no coinciden con el estilo de mi tema.**
**R2:**

- El módulo proporciona un estilo básico. Si desea que coincidan perfectamente con su tema, deberá añadir CSS personalizado.
- **Cómo hacerlo:**
  1. Inspeccione las etiquetas en la página de su producto utilizando las herramientas de desarrollo de su navegador (clic derecho, luego "Inspeccionar").
  2. Identifique las clases CSS utilizadas por las etiquetas (por ejemplo, `ptags_block`, `ptags_item`).
  3. Añada reglas CSS personalizadas al archivo `custom.css` de su tema (si tiene uno) o directamente al archivo `ptags.css` del módulo (aunque modificar los archivos del módulo directamente no es recomendable ya que las actualizaciones los sobrescribirán).
  - **Ejemplo CSS:**

    ```
    .ptags_block { margin-top: 20px; padding: 15px; border: 1px solid #eee; background-color: #f9f9f9;}.ptags_block h3 { font-size: 18px; color: #333; margin-bottom: 10px;}.ptags_item { display: inline-block; margin-right: 8px; margin-bottom: 8px;}.ptags_item a { background-color: #007bff; color: white; padding: 5px 10px; border-radius: 3px; text-decoration: none; font-size: 14px;}.ptags_item a:hover { background-color: #0056b3;}
    ```

**P3: Las etiquetas aparecen, pero están en una posición incómoda, o las quiero en un lugar muy específico que no aparece en las opciones de hook.**
**R3:**

- El módulo se basa en los hooks estándar de PrestaShop. Si necesita una ubicación muy específica y no estándar, generalmente requiere la modificación del tema.
- **Solución:** Usted o su desarrollador web tendrían que insertar manualmente la función de visualización del módulo en la plantilla de la página de producto de su tema (`product.tpl` o `product-details.tpl` en la carpeta de su tema).
  - Encuentre la ubicación exacta en el archivo `.tpl` de su tema donde desea que aparezcan las etiquetas.
  - Inserte el siguiente código Smarty: `{hook h='displayProductTags' product=$product}` (Nota: `displayProductTags` es un nombre de hook personalizado que registraría en el módulo, o puede usar `displayProductButtons` si eso es lo que configuró).
  - Alternativamente, puede llamar al módulo directamente: `{Module::getInstanceByName('ptags')->hookDisplayProductTags(['product' => $product])}`. Esto es más directo pero menos flexible que usar un hook.
- **Importante:** Esto requiere conocimientos básicos de desarrollo de temas de PrestaShop.

**P4: ¿Este módulo ralentizará mi tienda?**
**R4:**

- No, este módulo es muy ligero. Realiza una consulta simple a la base de datos para obtener las etiquetas asociadas con el producto actual. Esta operación está altamente optimizada por el núcleo de PrestaShop y no afectará notablemente los tiempos de carga de su página.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Mostrar etiquetas en la página de producto" (`ptags`) es un módulo de PrestaShop sencillo diseñado para extender la funcionalidad del front-office. Sigue una arquitectura de módulo de PrestaShop clásica, aprovechando principalmente la clase `Module` y sus métodos `install()`, `uninstall()` y `hook`. No introduce controladores, modelos ni JavaScript complejos personalizados. Su función principal es obtener las etiquetas de los productos y renderizarlas a través de una plantilla Smarty en un hook del front-office elegido.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador personalizado de Front-Office o Back-Office. Toda la lógica está encapsulada dentro de la clase principal del módulo (`ptags/index.php`) y se ejecuta a través del sistema de hooks de PrestaShop.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** introduce ninguna clase personalizada o definiciones de `ObjectModel`. Utiliza directamente las clases principales de PrestaShop `Tag` y `Product` para recuperar los datos necesarios.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo **no** contiene ningún archivo JavaScript personalizado. Su funcionalidad es puramente de renderizado HTML del lado del servidor.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **Ruta del archivo**: `ptags/views/css/ptags.css`
- **Alcance**: Estilo del front-office para el cliente.
- **Principales componentes de la interfaz de usuario y contenedores que estiliza**: Esta hoja de estilo proporciona un estilo básico para el bloque que contiene las etiquetas de producto y los enlaces de etiquetas individuales.
- **Selectores de clase CSS clave que los desarrolladores pueden anular en su tema**:
  - `.ptags_block`: Estiliza el bloque contenedor principal de las etiquetas.
  - `.ptags_block h3`: Estiliza el título del bloque de etiquetas.
  - `.ptags_item`: Estiliza cada elemento de etiqueta individual (por ejemplo, `display: inline-block`, márgenes).
  - `.ptags_item a`: Estiliza los enlaces de etiquetas clicables (por ejemplo, fondo, color, relleno, radio de borde).

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - **Ruta del archivo**: `ptags/views/front/ptags.tpl`
  - **Renderizado en hook**: Esta plantilla es renderizada por los métodos `hook` del módulo (por ejemplo, `hookDisplayProductButtons`, `hookDisplayProductExtraContent`, etc., dependiendo de la configuración).
  - **Salida del bloque visual**: Esta plantilla es responsable de generar la estructura HTML para el bloque de etiquetas, incluyendo el título opcional y la lista de enlaces de etiquetas clicables. Itera a través de la variable `$tags` (un array de objetos de etiqueta) pasada desde el método hook del módulo.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Se basa en las tablas existentes de PrestaShop, principalmente `ps_tag`, `ps_product_tag` y `ps_lang` para los datos de las etiquetas.

  - La configuración se almacena en `ps_configuration` con claves como `PTAGS_ENABLED`, `PTAGS_HOOK`, `PTAGS_TITLE`.
- **Tabla de Hooks Registrados**:

  | Nombre del Hook | Momento de Ejecución | Propósito Técnico |
  | --- | --- | --- |
  | `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para cargar la hoja de estilo CSS del módulo (`ptags.css`). |
  | `displayProductButtons` | En la página del producto, típicamente cerca del botón "Añadir al carrito". | Muestra el bloque de etiquetas del producto. (PrestaShop 1.7+) |
  | `displayProductExtraContent` | En la página del producto, en una sección dedicada para contenido extra. | Muestra el bloque de etiquetas del producto. (PrestaShop 1.7+) |
  | `displayFooterProduct` | En la parte inferior del contenido de la página del producto. | Muestra el bloque de etiquetas del producto. (PrestaShop 1.7+) |
  | `displayLeftColumnProduct` | En la columna izquierda específicamente en la página del producto. | Muestra el bloque de etiquetas del producto. (PrestaShop 1.7+) |
  | `displayRightColumnProduct` | En la columna derecha específicamente en la página del producto. | Muestra el bloque de etiquetas del producto. (PrestaShop 1.7+) |
  | `displayProductTab` | Añade una nueva pestaña a la página del producto. | (Si está configurado) Muestra las etiquetas del producto dentro de una pestaña. |
  | `displayProductTabContent` | Contenido para una pestaña de la página del producto. | (Si está configurado) Muestra las etiquetas del producto como contenido para una pestaña. |
  | `displayFooter` | En el pie de página general del sitio web. | (Si está configurado) Muestra el bloque de etiquetas del producto en el pie de página global. |
  | `displayLeftColumn` | En la columna izquierda de las páginas (no específica del producto). | (Si está configurado) Muestra el bloque de etiquetas del producto en la columna izquierda global. |
  | `displayRightColumn` | En la columna derecha de las páginas (no específica del producto). | (Si está configurado) Muestra el bloque de etiquetas del producto en la columna derecha global. |

  El módulo se registra dinámicamente en el hook seleccionado en su configuración. El archivo `index.php` contiene los métodos `hook[NombreDelHook]` que obtienen el ID del producto, recuperan las etiquetas asociadas y las pasan a `ptags.tpl` para su renderizado.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Mostrar etiquetas en la página de producto", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.

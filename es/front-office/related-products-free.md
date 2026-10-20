---
title: "Productos Relacionados Gratis - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Productos Relacionados Gratis de MyPresta.eu."
sidebar:
  label: "Productos Relacionados Gratis - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Related Products Free en MyPresta.eu](https://mypresta.eu/modules/front-office-features/related-products-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/related-products-free/)
>
> ---


# Productos Relacionados Gratis

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento compatibles con PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Productos Relacionados Gratis)

Esta es la pantalla principal y única de configuración para el módulo "Productos Relacionados Gratis". Aquí definirás cómo se comporta el bloque de productos relacionados y qué productos muestra.

#### **Mostrar productos relacionados de la categoría**

- **Qué hace este ajuste:** Esta configuración crucial determina *qué* productos se mostrarán como "relacionados". En lugar de seleccionar productos manualmente para cada artículo, este módulo simplifica las cosas permitiéndote seleccionar una categoría específica. Todos los productos que pertenecen a esta categoría elegida se mostrarán como productos relacionados en *cada* página de producto de tu tienda.
- **Efecto de cambiar este ajuste:**
  - *Cuando se selecciona una categoría (por ejemplo, "Accesorios"):* En cada página de producto de tu tienda, aparecerá un bloque que muestra productos que pertenecen a la categoría "Accesorios".
  - *Cuando se selecciona "Ninguno" o ninguna categoría:* El módulo no mostrará ningún producto relacionado, ya que no sabe qué productos mostrar.
- **Valor recomendado:** Elige una categoría que contenga artículos generales, complementarios o más vendidos que puedan ser relevantes para una amplia gama de tus productos principales. Por ejemplo, si vendes ropa, "Accesorios" o "Artículos en Oferta" podrían ser buenas opciones.
- **Escenario / ejemplo de comerciante:** Vendes varios tipos de productos electrónicos. Creas una categoría llamada "Accesorios Imprescindibles para Gadgets" y añades artículos como cargadores universales, protectores de pantalla y auriculares. Al seleccionar esta categoría aquí, cada página de producto (por ejemplo, para un smartphone, un portátil o una tableta) mostrará estos "Accesorios Imprescindibles para Gadgets" como productos relacionados, fomentando las ventas cruzadas.

#### **Número de productos a mostrar**

- **Qué hace este ajuste:** Esto controla cuántos productos relacionados se mostrarán en el bloque de tus páginas de producto.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en '4':* El módulo mostrará cuatro productos de la categoría elegida.
  - *Cuando se establece en '8':* El módulo mostrará ocho productos.
- **Valor recomendado:** 4 o 5. Demasiados productos pueden abrumar al cliente o hacer que la página se vea desordenada, especialmente en dispositivos móviles. Una selección más pequeña y curada suele ser más efectiva.
- **Escenario / ejemplo de comerciante:** Quieres mostrar una selección concisa de artículos relacionados sin hacer que la página del producto sea demasiado larga. Establecer esto en '4' asegura un diseño limpio al tiempo que ofrece buenas oportunidades de venta cruzada.

#### **Mostrar productos solo de la categoría seleccionada**

- **Qué hace este ajuste:** Esta configuración determina si los productos relacionados mostrados son *solo* de la categoría que seleccionaste anteriormente, o si también puede incluir productos de la *propia categoría del producto actual*.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Solo se mostrarán los productos de la categoría elegida en "Mostrar productos relacionados de la categoría".
  - *Cuando está deshabilitado (NO):* El módulo mostrará productos de la categoría seleccionada *y* potencialmente productos de la categoría del producto que el cliente está viendo actualmente. Esto puede llevar a sugerencias más relevantes si la categoría del producto actual también contiene buenos artículos de venta cruzada.
- **Valor recomendado:** "SÍ" si tu categoría de "productos relacionados" elegida es muy general (como "Accesorios"). "NO" si quieres mezclar artículos relacionados más específicos de la categoría del producto actual. Prueba ambos para ver qué funciona mejor para tu tienda.
- **Escenario / ejemplo de comerciante:** Has seleccionado "Accesorios" como tu categoría relacionada. Si lo configuras en "SÍ", solo se mostrarán accesorios. Si lo configuras en "NO", y un cliente está viendo una "Camiseta" (que está en la categoría "Tops"), el módulo podría mostrar tanto "Accesorios" como otros "Tops" como relacionados.

#### **Hook para mostrar productos relacionados**

- **Qué hace este ajuste:** Aquí es donde decides *dónde* en la página del producto aparecerá el bloque de productos relacionados. PrestaShop utiliza "hooks" como puntos específicos en el código de la página donde los módulos pueden insertar su contenido.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en `displayFooterProduct` (Recomendado):* El bloque de productos relacionados aparecerá en la parte inferior de la sección de información del producto, generalmente encima del pie de página de toda la página. Esta es una ubicación común y efectiva.
  - *Cuando se establece en `displayProductExtraContent` (PrestaShop 1.7+):* El bloque podría aparecer dentro de una pestaña o una sección específica del área de contenido principal de la página del producto, dependiendo de tu tema.
  - *Otros hooks (por ejemplo, `displayLeftColumnProduct`, `displayRightColumnProduct`):* El bloque aparecerá en la barra lateral izquierda o derecha de la página del producto, si tu tema soporta barras laterales en las páginas de producto.
- **Valor recomendado:** `displayFooterProduct`. Este hook es ampliamente compatible con los temas y proporciona una ubicación clara y discreta para los artículos relacionados. Experimenta con otros si tienes un diseño específico en mente.
- **Escenario / ejemplo de comerciante:** Quieres que los productos relacionados sean visibles pero que no interfieran con la descripción principal del producto y el botón "Añadir al carrito". Elegir `displayFooterProduct` lo coloca de forma ordenada debajo del contenido principal, permitiendo a los clientes desplazarse hacia abajo y descubrir más.

#### **Mostrar productos en carrusel**

- **Qué hace este ajuste:** Esto determina si los productos relacionados se muestran en una cuadrícula estática (todos visibles a la vez) o en un carrusel dinámico y desplazable (donde los clientes pueden hacer clic en flechas o deslizar para ver más).
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Los productos relacionados aparecerán en formato de carrusel, lo que te permite mostrar más productos en un espacio compacto.
  - *Cuando está deshabilitado (NO):* Los productos se mostrarán en una cuadrícula estática, mostrando todos los productos seleccionados a la vez (hasta el límite de "Número de productos a mostrar").
- **Valor recomendado:** "SÍ" si quieres ahorrar espacio o mostrar más productos de los que caben cómodamente en una sola fila. "NO" si prefieres que todos los productos sean inmediatamente visibles sin interacción.
- **Escenario / ejemplo de comerciante:** Quieres mostrar 8 productos relacionados, pero mostrarlos todos en una cuadrícula hace que la página sea demasiado larga. Habilitar el carrusel te permite mostrar 8 productos ocupando solo el espacio de 4, con los clientes desplazándose para ver el resto.

#### **Mostrar productos en orden aleatorio**

- **Qué hace este ajuste:** Esto controla el orden en que se muestran los productos relacionados de la categoría elegida.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Cada vez que un cliente visita una página de producto, los productos relacionados aparecerán en un orden diferente y aleatorio.
  - *Cuando está deshabilitado (NO):* Los productos aparecerán en un orden consistente, generalmente basado en su ID o posición dentro de la categoría seleccionada.
- **Valor recomendado:** "SÍ". Aleatorizar el orden asegura que todos los productos de la categoría elegida tengan la oportunidad de ser vistos con el tiempo, evitando que los mismos pocos productos estén siempre en la parte superior.
- **Escenario / ejemplo de comerciante:** Tienes 20 productos en tu categoría "Accesorios", pero solo muestras 5. Si el orden es siempre el mismo, solo se verán los primeros 5. Al habilitar el orden aleatorio, aparecerán diferentes accesorios cada vez, aumentando la exposición para todos ellos.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Mostrar productos relacionados de la categoría | Seleccionar una categoría relevante | Define la categoría de origen para los productos relacionados. |
| Configuración del Módulo | Número de productos a mostrar | 4-5 | Controla cuántos productos relacionados se muestran. |
| Configuración del Módulo | Mostrar productos solo de la categoría seleccionada | SÍ / NO (Probar ambos) | Determina si solo se muestran los productos de la categoría seleccionada, o si la categoría del producto actual también puede contribuir. |
| Configuración del Módulo | Hook para mostrar productos relacionados | `displayFooterProduct` | Especifica la ubicación del bloque de productos relacionados en la página del producto. |
| Configuración del Módulo | Mostrar productos en carrusel | SÍ | Muestra productos relacionados en un carrusel desplazable para una visualización compacta. |
| Configuración del Módulo | Mostrar productos en orden aleatorio | SÍ | Aleatoriza el orden de los productos relacionados mostrados para una exposición variada. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: He configurado el módulo, pero no veo ningún producto relacionado en mis páginas de producto.**
R:

1. **Verificar Selección de Categoría:** Asegúrate de haber seleccionado una categoría válida en la configuración "Mostrar productos relacionados de la categoría" y de que esta categoría realmente contenga productos.
2. **Verificar Estado del Producto:** Asegúrate de que los productos dentro de tu categoría seleccionada estén activos, en stock y visibles en tu tienda.
3. **Borrar Caché:** Ve a **Parámetros Avanzados > Rendimiento** en tu Back Office de PrestaShop y haz clic en "Borrar caché" (o "Borrar caché de Smarty"). A veces, PrestaShop necesita una actualización de caché para mostrar el nuevo contenido del módulo.
4. **Compatibilidad con el Tema:** Si bien el módulo utiliza hooks estándar de PrestaShop, algunos temas altamente personalizados pueden tener anulaciones específicas. Intenta cambiar temporalmente al tema predeterminado de PrestaShop para ver si aparece el bloque. Si lo hace, tu tema podría requerir pequeños ajustes.

**P: El bloque de productos relacionados se ve extraño o sin estilo en mi sitio.**
R: Esto suele ser un conflicto de CSS (estilo) con tu tema.

1. **Borrar Caché:** Siempre comienza borrando la caché de PrestaShop.
2. **Anulaciones del Tema:** Tu tema podría tener su propio estilo para listas de productos o carruseles que entran en conflicto. Es posible que necesites un desarrollador web para inspeccionar el CSS y aplicar estilos personalizados para que se ajuste al diseño de tu tema. El módulo proporciona un estilo básico, pero los estilos de tu tema a menudo tienen prioridad.

**P: ¿Puedo tener diferentes productos relacionados para diferentes productos principales?**
R: El módulo "Productos Relacionados Gratis" está diseñado para la simplicidad, mostrando productos de una *única categoría elegida* en todas las páginas de producto. Para asignaciones de productos relacionados más avanzadas y específicas de cada producto, necesitarías un módulo más completo (de pago).

**P: El carrusel no funciona o no se muestra correctamente.**
R:

1. **Verificar Conflictos de JavaScript:** Otro módulo o tu tema podría tener JavaScript en conflicto que impide que el carrusel se inicialice. Revisa la consola de desarrollador de tu navegador en busca de errores de JavaScript.
2. **Borrar Caché:** De nuevo, borra la caché de PrestaShop.
3. **Deshabilitar y Volver a Habilitar:** Intenta deshabilitar la configuración "Mostrar productos en carrusel", guardar, luego volver a habilitarla y guardar de nuevo.

**P: ¿Cómo traduzco el título del módulo (por ejemplo, "Productos Relacionados") a otros idiomas?**
R:

1. Ve a **Internacional > Traducciones** en tu Back Office de PrestaShop.
2. Selecciona "Traducciones de módulos instalados" para el "Tipo de traducción".
3. Elige tu tema (o "Core" si tu tema no está en la lista).
4. Selecciona el idioma que deseas traducir.
5. Busca el módulo "relatedfree" en la lista y traduce las cadenas relevantes.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una visión técnica para desarrolladores y webmasters que trabajan con el módulo "Productos Relacionados Gratis".

### 4.1 Visión General de la Arquitectura

El módulo "Productos Relacionados Gratis" es un módulo de PrestaShop sencillo que sigue un patrón básico similar a MVC dentro del alcance del módulo. Utiliza principalmente el método `getContent()` de la clase `Module` para su configuración en el Back Office y registra un único hook (`displayFooterProduct` por defecto, pero configurable) para inyectar su plantilla de front-office. No introduce controladores personalizados, ObjectModels o activos complejos de JavaScript/CSS más allá de su funcionalidad principal.

### 4.2 Controladores (`controllers/`)

- Este módulo **no** contiene ningún controlador personalizado de Front-Office o Back-Office. Toda la configuración se maneja dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

- Este módulo **no** contiene ninguna clase personalizada u ObjectModels en el directorio `classes/`. Toda la lógica está encapsulada dentro de la clase principal `RelatedFree` (definida en `index.php`).

### 4.4 Activos de JavaScript (`views/js/`)

- Este módulo **no** contiene ningún archivo JavaScript personalizado. Si la opción de carrusel está habilitada, se basa en las bibliotecas JavaScript principales de PrestaShop (por ejemplo, Owl Carousel si está disponible en el tema, o una implementación personalizada simple dentro del TPL si no).

### 4.5 Hojas de Estilo CSS (`views/css/`)

- Este módulo **no** contiene ningún archivo CSS personalizado. Se espera que el estilo sea manejado por el tema o se base en estilos/estructura básicos en línea que los temas suelen estilizar. Los desarrolladores deben aplicar CSS personalizado para que coincida con la estética de su tema.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:

  - `views/templates/admin/tabs.tpl`: Esta plantilla se utiliza para renderizar el formulario de configuración del módulo en el Back Office. Define la estructura de los ajustes, incluidos los campos de entrada para la selección de categoría, el número de productos, la selección de hook y los interruptores para el carrusel y el orden aleatorio. Es renderizada por `getContent()` en `index.php`.
- **Plantillas de hook (`views/templates/hook/`)**:

  - `views/templates/hook/productFooter.tpl`: Esta es la plantilla principal del front-office. Se renderiza cuando el módulo está enganchado (por ejemplo, `displayFooterProduct`). Esta plantilla contiene la estructura HTML para el bloque de productos relacionados, incluido el título, e itera a través de la variable `$products` (pasada desde el módulo) para mostrar la imagen, el nombre y el precio de cada producto relacionado. También contiene la lógica para renderizar un carrusel si la opción de configuración correspondiente está habilitada.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:
  El módulo no crea ninguna tabla de base de datos personalizada. Todas las configuraciones se almacenan en la tabla `ps_configuration` utilizando claves de configuración estándar de PrestaShop.

  - `PS_RELATEDFREE_CATEGORY`: Almacena el ID de la categoría seleccionada para productos relacionados.
  - `PS_RELATEDFREE_NUMBER`: Almacena el número de productos a mostrar.
  - `PS_RELATEDFREE_ONLY_SELECTED`: Almacena un booleano (0/1) para mostrar solo productos de la categoría seleccionada.
  - `PS_RELATEDFREE_HOOK`: Almacena el nombre del hook donde se muestra el módulo.
  - `PS_RELATEDFREE_CAROUSEL`: Almacena un booleano (0/1) para habilitar el carrusel.
  - `PS_RELATEDFREE_RANDOM`: Almacena un booleano (0/1) para mostrar productos en orden aleatorio.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para registrar activos (aunque este módulo no lo usa para activos). |
| `displayLeftColumn` | En la barra lateral izquierda de las páginas que tienen una. | Ubicación alternativa para el bloque de productos relacionados. |
| `displayRightColumn` | En la barra lateral derecha de las páginas que tienen una. | Ubicación alternativa para el bloque de productos relacionados. |
| `displayFooter` | En la parte inferior de cada página, antes de la etiqueta de cierre `</body>`. | Ubicación alternativa para el bloque de productos relacionados. |
| `displayProductExtraContent` | Dentro del área de contenido principal del producto, a menudo en pestañas (PrestaShop 1.7+). | Ubicación alternativa para el bloque de productos relacionados. |
| `displayFooterProduct` | En la parte inferior de la sección de información del producto en las páginas de producto. | **Hook principal utilizado por el módulo** para mostrar productos relacionados. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Productos Relacionados Gratis", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto a la funcionalidad del módulo.

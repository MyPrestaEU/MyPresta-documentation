---
title: "Comentarios de Facebook - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Comentarios de Facebook de MyPresta.eu."
sidebar:
  label: "Comentarios de Facebook - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook Comments en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-comments.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-comments/)
>
> ---


# Comentarios de Facebook

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y cualquier módulo que interactúe con APIs externas como Facebook.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" para acceder a la configuración del módulo. Aquí es donde controlará cómo aparece y funciona el cuadro de Comentarios de Facebook en sus páginas de productos.

#### 2.1.1 ID de la aplicación de Facebook

- **Qué hace esta configuración:** Este es un identificador único para su aplicación de Facebook. Aunque el módulo puede funcionar sin él, proporcionar un ID de aplicación le da acceso a las herramientas de moderación e información de Facebook para los comentarios en su sitio.
- **Efecto de cambiar esta configuración:**
  - *Cuando se proporciona:* Obtiene acceso al panel de moderación de comentarios de Facebook (developers.facebook.com/tools/comments) donde puede revisar, aprobar o eliminar comentarios. También ayuda a Facebook a atribuir los comentarios a su sitio específico.
  - *Cuando se deja vacío:* Los comentarios seguirán apareciendo, pero no tendrá las capacidades de moderación avanzadas a través de las herramientas para desarrolladores de Facebook. Dependerá del filtro de spam predeterminado de Facebook.
- **Valor recomendado:** Es muy recomendable crear una aplicación de Facebook e introducir su ID de aplicación aquí para un mejor control y moderación.
- **Escenario/ejemplo del comerciante:** Desea asegurarse de que todos los comentarios sean apropiados y relevantes. Al configurar un ID de aplicación de Facebook, puede moderar fácilmente los comentarios directamente desde el panel de control para desarrolladores de Facebook, eliminando spam o contenido inapropiado.

#### 2.1.2 Número de comentarios

- **Qué hace esta configuración:** Esto controla cuántos comentarios se muestran inicialmente en el cuadro de Comentarios de Facebook antes de que los usuarios necesiten hacer clic en "Ver más comentarios" o "Cargar más" para ver los más antiguos.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en un número bajo (por ejemplo, 5):* La sección de comentarios será más compacta, lo que requerirá que los usuarios hagan clic para ver más. Esto puede ser bueno para páginas con espacio limitado o si desea mantener la carga inicial de la página más ligera.
  - *Cuando se establece en un número más alto (por ejemplo, 20):* Más comentarios serán visibles inmediatamente, proporcionando más prueba social de un vistazo. Sin embargo, podría hacer que la página del producto sea más larga.
- **Valor recomendado:** 5-10 comentarios es un buen punto de partida para equilibrar la visibilidad y la longitud de la página. Ajuste según el diseño de su página de producto y el volumen típico de comentarios.
- **Escenario/ejemplo del comerciante:** Para productos populares con muchos comentarios, podría establecer esto en 5 para mantener la página ordenada. Para productos más nuevos, establecerlo en 10 podría fomentar más interacción al mostrar más comentarios existentes.

#### 2.1.3 Ancho del cuadro de comentarios

- **Qué hace esta configuración:** Esto determina el ancho del cuadro de Comentarios de Facebook en píxeles.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en un valor de píxel específico (por ejemplo, 600px):* El cuadro de comentarios mantendrá ese ancho fijo, lo que podría crear espacio vacío o desbordarse si el área de contenido de su tema es más estrecha o más ancha.
  - *Cuando se deja vacío o se establece en 100% (si es compatible con el módulo):* El cuadro de comentarios intentará ajustarse automáticamente al ancho disponible de su contenedor padre, haciéndolo responsivo.
- **Valor recomendado:** Dejar vacío para detección automática o establecer en 100% si el módulo lo admite, para asegurar la responsividad. Si necesita un ancho fijo, asegúrese de que se ajuste al área de contenido de su tema.
- **Escenario/ejemplo del comerciante:** La columna de contenido principal de su página de producto tiene 700px de ancho. Podría establecer el ancho en 700px para llenar perfectamente ese espacio. Si desea que se adapte a dispositivos móviles, dejarlo vacío suele ser lo mejor.

#### 2.1.4 Idioma del cuadro de comentarios

- **Qué hace esta configuración:** Esto le permite especificar el idioma para la interfaz del plugin de Comentarios de Facebook (por ejemplo, "Escribir un comentario...", "Ver más comentarios").
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en un código de idioma específico (por ejemplo, "en_US" para inglés, "fr_FR" para francés):* El texto del plugin de Facebook se mostrará en ese idioma, independientemente del idioma del navegador del usuario o del idioma activo de su tienda PrestaShop.
  - *Cuando se deja vacío:* Facebook normalmente intentará detectar el idioma preferido del usuario o el idioma de su tienda PrestaShop.
- **Valor recomendado:** Generalmente es mejor dejar esto vacío para que Facebook pueda detectar automáticamente el idioma del usuario, o establecerlo en el idioma principal de su tienda si desea coherencia.
- **Escenario/ejemplo del comerciante:** Si su tienda se dirige principalmente a clientes en Alemania, podría establecer esto en "de_DE" para asegurarse de que todo el texto del plugin de Facebook esté en alemán, incluso si el navegador de un usuario está configurado en inglés.

#### 2.1.5 Posición del cuadro de comentarios

- **Qué hace esta configuración:** Esto determina dónde se mostrará el cuadro de Comentarios de Facebook en la página del producto. Puede elegir entre varios hooks de PrestaShop.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en `displayProductButtons` (o similar):* El cuadro de comentarios podría aparecer cerca del botón "Añadir al carrito" u otras acciones del producto.
  - *Cuando se establece en `displayFooterProduct` (o similar):* El cuadro de comentarios aparecerá más abajo en la página del producto, a menudo debajo de los detalles principales del producto, lo cual es una ubicación común y generalmente preferida.
  - *Cuando se establece en `displayRightColumn` o `displayLeftColumn` (si está disponible):* El cuadro de comentarios aparecería en una de las columnas laterales de su tienda, lo cual es menos común para los comentarios y podría no ser ideal visualmente.
- **Valor recomendado:** `displayFooterProduct` o un hook similar que coloque la sección de comentarios debajo de la información principal del producto suele ser la ubicación más natural y efectiva.
- **Escenario/ejemplo del comerciante:** Desea que los comentarios sean visibles pero que no distraigan del objetivo principal de añadir el producto al carrito. Colocarlo en `displayFooterProduct` asegura que los clientes vean todos los detalles del producto primero, y luego puedan interactuar con los comentarios.

#### 2.1.6 Habilitar comentarios de Facebook

- **Qué hace esta configuración:** Este es un simple interruptor de ENCENDIDO/APAGADO para activar o desactivar toda la funcionalidad de Comentarios de Facebook.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado (SÍ):* El cuadro de Comentarios de Facebook aparecerá en sus páginas de productos según sus otras configuraciones.
  - *Cuando está deshabilitado (NO):* El cuadro de Comentarios de Facebook estará completamente oculto de sus páginas de productos, y el módulo no cargará ningún script relacionado con Facebook.
- **Valor recomendado:** SÍ, si desea utilizar la función.
- **Escenario/ejemplo del comerciante:** Ha terminado de configurar el módulo y desea activarlo en su tienda. Lo cambia a SÍ. Más tarde, si decide deshabilitar temporalmente los comentarios por mantenimiento, puede cambiarlo a NO.

#### 2.1.7 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | ID de la aplicación de Facebook | (Vacío) / Recomendado: Su ID de aplicación | Habilita las herramientas de moderación de Facebook para los comentarios. |
| Configuración del módulo | Número de comentarios | 5-10 | Establece cuántos comentarios son visibles inicialmente. Afecta la longitud de la página. |
| Configuración del módulo | Ancho del cuadro de comentarios | (Vacío) / Detección automática (Responsivo) | Define el ancho de la sección de comentarios. Vacío para responsividad. |
| Configuración del módulo | Idioma del cuadro de comentarios | (Vacío) / Detección automática | Establece el idioma de la interfaz del plugin de Facebook. Vacío para el idioma del usuario/tienda. |
| Configuración del módulo | Posición del cuadro de comentarios | `displayFooterProduct` | Determina dónde aparece el cuadro de comentarios en la página del producto. |
| Configuración del módulo | Habilitar comentarios de Facebook | SÍ | Activa o desactiva toda la función de Comentarios de Facebook. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: El cuadro de Comentarios de Facebook no aparece en mis páginas de productos. ¿Qué debo hacer?**
R:

1. **Verifique "Habilitar comentarios de Facebook":** Asegúrese de que esta configuración en la configuración del módulo esté establecida en SÍ.
2. **Verifique la posición:** Asegúrese de que la configuración "Posición del cuadro de comentarios" esté establecida en un hook que realmente esté presente y sea renderizado por su tema en las páginas de productos (por ejemplo, `displayFooterProduct`). Algunos temas personalizados podrían no usar todos los hooks estándar.
3. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty"). A veces, el contenido antiguo en caché impide que aparezcan nuevos módulos.
4. **Compatibilidad del tema:** Si está utilizando un tema muy personalizado, podría anular las plantillas estándar de la página del producto o eliminar los hooks necesarios. Póngase en contacto con el desarrollador de su tema o con un experto en PrestaShop para obtener ayuda.
5. **Problemas del navegador:** Intente borrar la caché y las cookies de su navegador, o pruebe en una ventana de incógnito.

**P: ¿Cómo modero los comentarios?**
R: Si ha configurado un ID de aplicación de Facebook y lo ha introducido en la configuración del módulo, puede moderar los comentarios directamente a través de las herramientas para desarrolladores de Facebook. Vaya a [developers.facebook.com/tools/comments](https://developers.facebook.com/tools/comments). Deberá iniciar sesión con la cuenta de Facebook asociada a su ID de aplicación.

**P: ¿Puedo cambiar el estilo (colores, fuentes) del cuadro de Comentarios de Facebook?**
R: El estilo del plugin de Comentarios de Facebook está en gran medida controlado por Facebook mismo para mantener una experiencia de marca consistente. Tiene un control muy limitado sobre su apariencia interna. Puede controlar el ancho y su ubicación, pero no su CSS interno.

**P: ¿Los Comentarios de Facebook ralentizarán mi sitio web?**
R: El plugin de Comentarios de Facebook carga scripts externos de Facebook. Aunque Facebook los optimiza, cualquier script externo puede añadir un ligero retraso a la carga de la página. El módulo está diseñado para cargar estos scripts de manera eficiente. Puede usar herramientas como Google PageSpeed Insights para monitorear el rendimiento de su sitio.

**P: ¿Necesito una página de empresa de Facebook para que este módulo funcione?**
R: No, no necesita estrictamente una página de empresa de Facebook. Sin embargo, si desea utilizar las herramientas de moderación avanzadas, necesitará una cuenta de desarrollador de Facebook y crear una aplicación básica de Facebook, que es una entidad separada de una página de empresa.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo Comentarios de Facebook (`facebook-comments`) es un módulo de PrestaShop sencillo diseñado principalmente para inyectar el HTML y el SDK de JavaScript del plugin social de Comentarios de Facebook en las páginas de productos del front-office. Sigue una estructura de módulo estándar de PrestaShop, aprovechando los hooks para la inyección de contenido y la clase `Configuration` para el almacenamiento de la configuración. No introduce controladores personalizados, modelos o interacciones AJAX complejas.

### 4.2 Controladores (`controllers/`)

- Este módulo **no** contiene ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la configuración se gestiona a través del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

- Este módulo **no** contiene ninguna clase personalizada o definiciones de `ObjectModel`. Toda la lógica está encapsulada dentro del archivo principal `facebook-comments.php`.

### 4.4 Activos de JavaScript (`views/js/`)

- Este módulo **no** contiene ningún archivo JavaScript personalizado. El SDK de JavaScript de Facebook se carga directamente desde el CDN de Facebook mediante la plantilla del módulo.

### 4.5 Hojas de estilo CSS (`views/css/`)

- Este módulo **no** contiene ningún archivo CSS personalizado. El estilo del plugin de Comentarios de Facebook es gestionado por las propias hojas de estilo de Facebook.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

Este módulo utiliza principalmente un único archivo de plantilla para renderizar el cuadro de Comentarios de Facebook.

- **Plantillas de hook (`views/templates/hook/`)**:
  - `facebook-comments.tpl`: Este es el archivo de plantilla principal.
    - **Propósito:** Renderiza el elemento `div` que el SDK de JavaScript de Facebook transforma en el cuadro de comentarios. También incluye el código de inicialización del SDK de JavaScript necesario.
    - **Variables:**
      - `{$facebook_app_id}`: El ID de la aplicación de Facebook de la configuración del módulo.
      - `{$facebook_comments_number}`: El número de comentarios a mostrar.
      - `{$facebook_comments_width}`: El ancho del cuadro de comentarios.
      - `{$facebook_comments_lang}`: El código de idioma para el plugin.
      - `{$product_link}`: La URL de la página del producto actual, utilizada por Facebook para identificar el hilo de comentarios.
    - **Hooks:** Esta plantilla se renderiza a través del hook especificado en la configuración del módulo (por ejemplo, `displayFooterProduct`).

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: Este módulo **no** crea ninguna tabla de base de datos personalizada. Todas las configuraciones se almacenan en la tabla `ps_configuration` utilizando los métodos estándar de PrestaShop `Configuration::get()` y `Configuration::updateValue()`.

  - Las claves de configuración suelen incluir:
    - `FACEBOOK_COMMENTS_APP_ID`
    - `FACEBOOK_COMMENTS_NUMBER`
    - `FACEBOOK_COMMENTS_WIDTH`
    - `FACEBOOK_COMMENTS_LANG`
    - `FACEBOOK_COMMENTS_POSITION`
    - `FACEBOOK_COMMENTS_ENABLED`
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para incluir el SDK de JavaScript de Facebook una vez por página, asegurando que esté disponible antes de que se renderice el cuadro de comentarios. |
| `displayProductButtons` | Cerca del botón "Añadir al carrito" en las páginas de productos. | Hook opcional para renderizar el cuadro de comentarios, si lo configura el comerciante. |
| `displayFooterProduct` | En la parte inferior del contenido de la página del producto. | Hook común y recomendado para renderizar el cuadro de comentarios, si lo configura el comerciante. |
| `displayLeftColumn` | En la barra lateral izquierda de las páginas. | Hook opcional para renderizar el cuadro de comentarios, si lo configura el comerciante. (Menos común para comentarios). |
| `displayRightColumn` | En la barra lateral derecha de las páginas. | Hook opcional para renderizar el cuadro de comentarios, si lo configura el comerciante. (Menos común para comentarios). |
| `displayFooter` | En la sección del pie de página de la tienda. | Hook opcional para renderizar el cuadro de comentarios, si lo configura el comerciante. (Menos común para comentarios específicos del producto). |

El módulo se registra dinámicamente en el hook elegido por el comerciante en la configuración. El hook `displayHeader` siempre se utiliza para cargar el SDK de Facebook.

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo Comentarios de Facebook, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con la funcionalidad del módulo.

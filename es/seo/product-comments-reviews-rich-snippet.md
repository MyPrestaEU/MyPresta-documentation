---
title: "Comentarios de productos - Fragmento enriquecido de reseñas - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Comentarios de productos - Fragmento enriquecido de reseñas' de MyPresta.eu."
sidebar:
  label: "Comentarios de productos - Fragmento enriquecido de reseñas - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product Comments - Reviews rich snippet en MyPresta.eu](https://mypresta.eu/modules/seo/product-comments-reviews-rich-snippet.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/seo/product-comments-reviews-rich-snippet/)
>
> ---


# Comentarios de productos - Fragmento enriquecido de reseñas

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).
- **Dependencia**: Este módulo extiende la funcionalidad del **módulo gratuito de Comentarios de productos de PrestaShop**. Debe tener el módulo oficial de Comentarios de productos de PrestaShop instalado y activo para que este módulo funcione correctamente.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Este módulo tiene una página de configuración sencilla, centrada principalmente en habilitar o deshabilitar su funcionalidad principal y seleccionar dónde se deben inyectar los datos del fragmento enriquecido.

**Para acceder:** Vaya a **Módulos > Gestor de módulos**, busque "Comentarios de productos - Fragmento enriquecido de reseñas" y haga clic en "Configurar".

#### **Habilitar / Deshabilitar fragmentos enriquecidos**

- **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar la funcionalidad principal del módulo. Cuando está habilitado, el módulo comenzará a añadir los datos estructurados necesarios a sus páginas de productos.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* El módulo inyectará el código de fragmento enriquecido en sus páginas de productos, permitiendo a Google mostrar calificaciones de estrellas y recuentos de reseñas en los resultados de búsqueda.
  - *Cuando está deshabilitado:* El módulo dejará de inyectar el código de fragmento enriquecido. Sus listados de productos en los resultados de búsqueda de Google volverán al texto estándar, sin estrellas ni recuentos de reseñas.
- **Valor recomendado:** **SÍ** (Habilitado). El propósito principal de este módulo es mostrar fragmentos enriquecidos, por lo que casi siempre debe estar habilitado.
- **Escenario / ejemplo de comerciante:** Si está probando el módulo o desea ocultar temporalmente los datos de las reseñas de los resultados de búsqueda (por ejemplo, durante una revisión importante del sitio), podría deshabilitarlo. De lo contrario, manténgalo habilitado para maximizar la visibilidad.

#### **Mostrar fragmentos enriquecidos en el hook**

- **Qué hace este ajuste:** Esta opción le permite elegir *dónde* en su página de producto el módulo debe inyectar los datos estructurados. Aunque los datos son invisibles para el cliente, su ubicación a veces puede afectar la compatibilidad con temas u otros módulos.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en 'Header':* Los datos del fragmento enriquecido se colocarán dentro de la sección `<head>` del HTML de su página de producto. Esta es generalmente la ubicación más común y recomendada para los datos estructurados.
  - *Cuando se establece en 'Product':* Los datos del fragmento enriquecido se colocarán dentro del área de contenido principal del producto.
  - *Cuando se establece en 'Columns':* Los datos del fragmento enriquecido se colocarán dentro de una de las columnas laterales de su tienda (izquierda o derecha, según el diseño de su tema).
  - *Cuando se establece en 'Footer':* Los datos del fragmento enriquecido se colocarán dentro de la sección `<footer>` del HTML de su página de producto.
- **Valor recomendado:** **Header**. Esta es la ubicación más estándar y robusta para los datos estructurados, ya que es procesada temprano por los rastreadores de los motores de búsqueda y es menos probable que entre en conflicto con elementos visuales u otros scripts en su página.
- **Escenario / ejemplo de comerciante:** Si experimenta problemas inesperados con el diseño de su página de producto u otros módulos después de habilitar los fragmentos enriquecidos, podría intentar cambiar este hook a 'Product' o 'Footer' como paso de solución de problemas. Sin embargo, 'Header' suele ser la opción más segura.

#### **Mostrar fragmentos enriquecidos cortos (solo estrellas)**

- **Qué hace este ajuste:** Esta opción le permite elegir entre mostrar el fragmento enriquecido completo (estrellas + recuento de reseñas) o una versión "corta" que solo muestra las estrellas, sin el número de reseñas.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* Google solo mostrará la calificación de estrellas (por ejemplo, "★★★★★ 4.5") en los resultados de búsqueda, omitiendo la parte "(X reseñas)".
  - *Cuando está deshabilitado:* Google mostrará tanto la calificación de estrellas como el número de reseñas (por ejemplo, "★★★★★ 4.5 (12 reseñas)").
- **Valor recomendado:** **NO** (Deshabilitado). Mostrar tanto las estrellas como el recuento de reseñas proporciona información más completa y a menudo genera más confianza, especialmente si tiene un gran número de reseñas.
- **Escenario / ejemplo de comerciante:** Si tiene muy pocas reseñas en muchos productos y siente que mostrar "1 reseña" podría parecer menos impresionante que solo las estrellas, podría habilitar esta opción. Sin embargo, para la mayoría de las tiendas con un número saludable de reseñas, mostrar el recuento es beneficioso.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar / Deshabilitar fragmentos enriquecidos | SÍ (Habilitado) | Activa/desactiva la inyección de código de fragmento enriquecido para los resultados de búsqueda de Google. |
| Configuración del módulo | Mostrar fragmentos enriquecidos en el hook | Header | Determina dónde se coloca el código de fragmento enriquecido invisible en la página del producto. 'Header' es generalmente lo mejor para la compatibilidad. |
| Configuración del módulo | Mostrar fragmentos enriquecidos cortos (solo estrellas) | NO (Deshabilitado) | Controla si solo se muestran las estrellas o las estrellas + el recuento de reseñas en los resultados de búsqueda de Google. Se recomienda mostrar ambos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He instalado el módulo, pero no veo estrellas en los resultados de búsqueda de Google. ¿Qué pasa?**
R: Varios factores podrían estar en juego:
1. **Tiempo de rastreo de Google:** Google tarda en volver a rastrear su sitio web y actualizar su índice. Esto puede variar desde unos pocos días hasta unas pocas semanas, especialmente para páginas nuevas o cambios significativos.
2. **Caché:** Borre la caché de su PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché) después de la configuración.
3. **Google Search Console:** Revise su Google Search Console en "Fragmentos de reseñas" en "Mejoras". Si hay errores, Google podría no mostrar los fragmentos.
4. **Sin reseñas:** Asegúrese de que el producto realmente tenga reseñas aprobadas en su tienda. Google no mostrará estrellas si no hay reseñas.
5. **Módulo de Comentarios de productos:** Verifique que el módulo oficial de Comentarios de productos de PrestaShop esté instalado y activo. Este módulo depende de él.
6. **Discreción de Google:** Aunque el módulo proporciona los datos, Google decide en última instancia si mostrar los fragmentos enriquecidos. Puede optar por no mostrarlos si considera que el contenido es irrelevante o de baja calidad.

**P: Mi página de producto se ve rota después de instalar el módulo.**
R: Esto es muy poco probable ya que el módulo solo inyecta datos estructurados invisibles. Sin embargo, si sucede:
1. **Deshabilite el módulo:** Vaya al Gestor de módulos y deshabilite "Comentarios de productos - Fragmento enriquecido de reseñas". Si la página vuelve a la normalidad, entonces el módulo podría ser la causa.
2. **Cambie la configuración "Mostrar fragmentos enriquecidos en el hook":** Intente cambiar el hook de 'Header' a 'Product' o 'Footer'. A veces, pueden ocurrir conflictos de tema con ubicaciones de hook específicas.
3. **Borrar caché:** Siempre borre la caché de su PrestaShop después de realizar cambios.

**P: ¿Este módulo afecta la velocidad de carga de mi sitio web?**
R: No, el impacto en la velocidad de carga es insignificante. El módulo solo añade un pequeño bloque de texto (datos estructurados) al HTML de su página, que es muy ligero y procesado rápidamente por los navegadores y los motores de búsqueda.

**P: ¿Puedo personalizar la apariencia de las estrellas en los resultados de búsqueda de Google?**
R: No, la apariencia de las estrellas y el recuento de reseñas en los resultados de búsqueda de Google está completamente controlada por la interfaz de Google. Este módulo proporciona los datos; Google los renderiza. No puede cambiar el color, el tamaño o el estilo de las estrellas en los resultados de búsqueda.

**P: ¿Funcionará este módulo con temas personalizados?**
R: Sí, este módulo está diseñado para funcionar independientemente del estilo visual de su tema. Inyecta datos estructurados en el HTML, lo cual es una práctica estándar. Siempre que su tema personalizado implemente correctamente el sistema de hooks de PrestaShop, el módulo debería funcionar sin problemas.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la arquitectura técnica del módulo "Comentarios de productos - Fragmento enriquecido de reseñas", destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Resumen de la arquitectura

El módulo `prrs` (Product Reviews Rich Snippet) es un módulo ligero de PrestaShop diseñado para inyectar datos estructurados `AggregateRating` de Schema.org en las páginas de productos. Aprovecha los datos existentes del módulo oficial `productcomments`. El módulo opera principalmente enganchándose a un punto de visualización (configurable por el comerciante) y renderizando una plantilla Smarty que contiene los datos estructurados JSON-LD. Sigue una estructura de módulo estándar de PrestaShop, con una clase de módulo principal y algunos activos de soporte.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador personalizado de Front-Office o Back-Office. Toda la lógica se maneja dentro del archivo principal del módulo `index.php` y sus plantillas asociadas.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada ni extiende `ObjectModel`. Se basa principalmente en las funcionalidades principales existentes de PrestaShop y en los datos del módulo `productcomments`.

### 4.4 Activos de JavaScript (`views/js/`)

- **`prrs/lib/searchTool/views/js/autocomplete.js`**
  - **Alcance:** Back-office (probablemente para una herramienta de búsqueda interna, aunque no utilizada directamente por la funcionalidad de fragmento enriquecido del módulo principal).
  - **Responsabilidad:** Este script parece ser parte de una utilidad genérica de autocompletado. Probablemente maneja solicitudes AJAX para sugerencias de búsqueda, actualiza campos de entrada y gestiona la visualización de los resultados de búsqueda en un menú desplegable. Dada la función principal del módulo, esto podría ser un remanente o una dependencia de una biblioteca compartida. No está directamente involucrado en la generación del fragmento enriquecido.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`prrs/lib/searchTool/views/css/autocomplete.css`**
  - **Alcance:** Back-office.
  - **Responsabilidad:** Proporciona estilos para la herramienta de búsqueda de autocompletado mencionada anteriormente. Esto incluiría estilos para la entrada de búsqueda, sugerencias desplegables, resultados resaltados, etc. No es relevante para la visualización del front-office.
- **`prrs/views/css/prrs.css`**
  - **Alcance:** Front-office.
  - **Responsabilidad:** Esta hoja de estilo es probablemente mínima o vacía, ya que la función principal del módulo es inyectar datos estructurados invisibles. Si contiene algún estilo, sería para elementos muy sutiles y no intrusivos, o potencialmente para una visualización de respaldo si los datos estructurados en sí tuvieran un componente visible (lo cual típicamente no ocurre con los fragmentos enriquecidos). Los desarrolladores deben revisar este archivo en busca de cualquier salida visual inesperada.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`prrs/lib/searchTool/views/scripts.tpl`**
  - **Alcance:** Back-office.
  - **Propósito:** Esta plantilla probablemente incluye el JavaScript para la herramienta de búsqueda de autocompletado (`autocomplete.js`) y potencialmente otros scripts relacionados o configuraciones de scripts en línea. Se renderizaría en un contexto de administración.
- **`prrs/views/templates/prrs-json.tpl`**
  - **Alcance:** Front-office (página de producto).
  - **Propósito:** Esta es la plantilla principal responsable de generar los datos estructurados JSON-LD para el fragmento enriquecido `AggregateRating`. Recupera dinámicamente la calificación promedio del producto y el recuento de reseñas del módulo `productcomments` y los formatea de acuerdo con las especificaciones de Schema.org. Esta plantilla se renderiza cuando la opción "Mostrar fragmentos enriquecidos cortos" está deshabilitada.
  - **Puntos de datos clave:** `product.id_product`, `product.name`, `product.link_rewrite`, `product.link`, `product.cover.bySize.home_default.url`, `average_grade`, `nb_comments`.
- **`prrs/views/templates/prrs.tpl`**
  - **Alcance:** Front-office (página de producto).
  - **Propósito:** Esta plantilla es probablemente un envoltorio o una alternativa a `prrs-json.tpl`, potencialmente utilizada para versiones anteriores de PrestaShop o integraciones de hooks específicos. También genera los datos del fragmento enriquecido. Es importante verificar qué plantilla se utiliza activamente según la lógica `getContent()` del módulo y el registro del hook.
- **`prrs/views/templates/shortprrs.tpl`**
  - **Alcance:** Front-office (página de producto).
  - **Propósito:** Esta plantilla genera un fragmento de datos estructurados JSON-LD simplificado, que típicamente solo incluye la calificación promedio de estrellas sin el recuento explícito de reseñas. Se renderiza cuando la opción "Mostrar fragmentos enriquecidos cortos" está habilitada.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo no crea ninguna tabla de base de datos personalizada.
  - Se basa en la tabla `ps_configuration` para almacenar sus configuraciones (por ejemplo, `PRRS_ENABLED`, `PRRS_HOOK`, `PRRS_SHORT`).
  - Recupera los datos de las reseñas de las tablas creadas por el módulo oficial `productcomments` (por ejemplo, `ps_product_comment`, `ps_product_comment_criterion`).
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento / Contexto de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza dentro de la sección `<head>` de la página. | Inyecta datos estructurados JSON-LD para fragmentos enriquecidos al principio de la carga de la página. Configurable a través de la configuración del módulo. |
| `displayProductAdditionalInfo` | Se renderiza dentro de la página del producto, típicamente debajo de los detalles principales del producto. | Hook alternativo para inyectar datos estructurados JSON-LD. Configurable a través de la configuración del módulo. |
| `displayLeftColumn` / `displayRightColumn` | Se renderiza dentro de las respectivas columnas laterales. | Menos común, pero disponible como hook alternativo para inyectar datos estructurados JSON-LD. Configurable a través de la configuración del módulo. |
| `displayFooter` | Se renderiza dentro de la sección `<footer>` de la página. | Hook alternativo para inyectar datos estructurados JSON-LD, típicamente al final de la página. Configurable a través de la configuración del módulo. |
| `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador frontal establece sus activos multimedia. | Se utiliza para registrar archivos CSS y JavaScript para el front office. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración establece sus activos multimedia. | Se utiliza para registrar archivos CSS y JavaScript para el back office (por ejemplo, `autocomplete.js`, `autocomplete.css`). |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con el módulo "Comentarios de productos - Fragmento enriquecido de reseñas".

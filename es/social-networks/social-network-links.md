---
title: "Enlaces a Redes Sociales - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Enlaces a Redes Sociales de PrestaShop por MyPresta.eu."
sidebar:
  label: "Enlaces a Redes Sociales - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Social Network Links en MyPresta.eu](https://mypresta.eu/modules/social-networks/social-network-links.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/social-network-links/)
>
> ---


# Enlaces a Redes Sociales

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y generalmente vienen preinstaladas en la mayoría de los entornos de alojamiento web.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Enlaces a Redes Sociales)

Esta es la pantalla de configuración principal y única para el módulo "Enlaces a Redes Sociales". Aquí definirás qué redes sociales mostrar y dónde aparecerán en tu tienda.

**Acceso:** Navega a **Módulos > Gestor de Módulos**, busca "Enlaces a Redes Sociales" y haz clic en "Configurar".

#### **Configuración General**

- **URL de Facebook:**

  - **Qué hace este ajuste:** Aquí es donde introduces la dirección web completa (URL) de tu página de Facebook.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está lleno:* Aparecerá un icono de Facebook en el bloque del módulo, enlazando directamente a la URL que proporcionaste.
    - *Cuando está vacío:* No se mostrará ningún icono de Facebook.
  - **Valor recomendado:** La URL de tu página oficial de Facebook (por ejemplo, `https://www.facebook.com/nombredetutienda`).
  - **Escenario / ejemplo de comerciante:** Si tu página de Facebook es `https://www.facebook.com/MiTiendaGenial`, introduce esa URL aquí. Los clientes que hagan clic en el icono de Facebook serán llevados a tu página.
- **URL de Twitter:**

  - **Qué hace este ajuste:** Introduce la dirección web completa (URL) de tu perfil de Twitter.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está lleno:* Aparecerá un icono de Twitter, enlazando a tu perfil de Twitter.
    - *Cuando está vacío:* No se mostrará ningún icono de Twitter.
  - **Valor recomendado:** La URL de tu perfil oficial de Twitter (por ejemplo, `https://twitter.com/nombredetutienda`).
  - **Escenario / ejemplo de comerciante:** Si tu nombre de usuario de Twitter es `@MiTiendaGenial`, tu URL podría ser `https://twitter.com/MiTiendaGenial`.
- **URL de YouTube:**

  - **Qué hace este ajuste:** Introduce la dirección web completa (URL) de tu canal de YouTube.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está lleno:* Aparecerá un icono de YouTube, enlazando a tu canal.
    - *Cuando está vacío:* No se mostrará ningún icono de YouTube.
  - **Valor recomendado:** La URL de tu canal oficial de YouTube (por ejemplo, `https://www.youtube.com/channel/id_de_tu_canal`).
  - **Escenario / ejemplo de comerciante:** Si tienes videos de reseñas de productos o tutoriales en YouTube, enlaza tu canal aquí.
- **URL de Google+:**

  - **Qué hace este ajuste:** Introduce la dirección web completa (URL) de tu perfil o página de Google+.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está lleno:* Aparecerá un icono de Google+, enlazando a tu perfil.
    - *Cuando está vacío:* No se mostrará ningún icono de Google+.
  - **Valor recomendado:** La URL de tu perfil/página oficial de Google+ (por ejemplo, `https://plus.google.com/+NombreDeTuTienda`).
  - **Escenario / ejemplo de comerciante:** Aunque Google+ está en gran parte obsoleto, si aún mantienes una presencia o tienes contenido heredado, puedes enlazarlo aquí. De lo contrario, déjalo vacío.
- **URL de RSS:**

  - **Qué hace este ajuste:** Introduce la dirección web completa (URL) de tu feed RSS. Esto se usa típicamente para blogs o secciones de noticias para permitir a los usuarios suscribirse a las actualizaciones.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está lleno:* Aparecerá un icono de RSS, enlazando a tu feed.
    - *Cuando está vacío:* No se mostrará ningún icono de RSS.
  - **Valor recomendado:** Si tu tienda tiene un blog o una sección de noticias con un feed RSS, introduce su URL (por ejemplo, `https://tutienda.com/blog/feed`). De lo contrario, déjalo vacío.
  - **Escenario / ejemplo de comerciante:** Si publicas regularmente entradas de blog sobre tus productos o industria, proporcionar un feed RSS permite a los clientes expertos en tecnología obtener actualizaciones directamente.

#### **Configuración de Visualización**

- **Mostrar en la Cabecera:**

  - **Qué hace este ajuste:** Controla si el bloque de enlaces a redes sociales aparece en la sección de la cabecera de tu tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* El bloque de enlaces sociales será visible en la parte superior de tu sitio web.
    - *Cuando está deshabilitado (No):* El bloque no aparecerá en la cabecera.
  - **Valor recomendado:** **Sí**, si quieres una alta visibilidad para tus enlaces sociales.
  - **Escenario / ejemplo de comerciante:** Habilita esto si quieres que los clientes vean inmediatamente tu presencia social al aterrizar en tu sitio.
- **Mostrar en la Columna Izquierda:**

  - **Qué hace este ajuste:** Controla si el bloque de enlaces a redes sociales aparece en la barra lateral izquierda de tu tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* El bloque de enlaces sociales será visible en la columna izquierda (si tu tema tiene una).
    - *Cuando está deshabilitado (No):* El bloque no aparecerá en la columna izquierda.
  - **Valor recomendado:** **No**, a menos que tengas una razón específica para colocarlo allí y tu tema admita una columna izquierda. A menudo, se prefiere la columna derecha o el pie de página.
  - **Escenario / ejemplo de comerciante:** Si tu tema tiene una columna izquierda prominente y quieres mantener los enlaces visibles mientras los clientes navegan por las categorías, habilita esto.
- **Mostrar en la Columna Derecha:**

  - **Qué hace este ajuste:** Controla si el bloque de enlaces a redes sociales aparece en la barra lateral derecha de tu tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* El bloque de enlaces sociales será visible en la columna derecha (si tu tema tiene una).
    - *Cuando está deshabilitado (No):* El bloque no aparecerá en la columna derecha.
  - **Valor recomendado:** **Sí**, si quieres mostrar los enlaces en una barra lateral.
  - **Escenario / ejemplo de comerciante:** Una buena opción para mantener los enlaces sociales visibles sin saturar demasiado la cabecera o el pie de página.
- **Mostrar en el Pie de Página:**

  - **Qué hace este ajuste:** Controla si el bloque de enlaces a redes sociales aparece en la sección del pie de página de tu tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* El bloque de enlaces sociales será visible en la parte inferior de tu sitio web.
    - *Cuando está deshabilitado (No):* El bloque no aparecerá en el pie de página.
  - **Valor recomendado:** **Sí**, ya que el pie de página es un lugar estándar y esperado para los enlaces de redes sociales.
  - **Escenario / ejemplo de comerciante:** Habilita esto para proporcionar una ubicación consistente para los enlaces sociales que los clientes suelen buscar en la parte inferior de una página.
- **Mostrar en la Página de Producto:**

  - **Qué hace este ajuste:** Controla si el bloque de enlaces a redes sociales aparece en las páginas de productos individuales.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* El bloque de enlaces sociales será visible en cada página de detalles del producto.
    - *Cuando está deshabilitado (No):* El bloque no aparecerá en las páginas de productos.
  - **Valor recomendado:** **Sí**, si quieres fomentar el intercambio social o el seguimiento directamente desde las páginas de productos.
  - **Escenario / ejemplo de comerciante:** Si quieres que los clientes encuentren fácilmente tus redes sociales mientras consideran una compra, habilita esto.

#### 2.1.1 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | URL de Facebook | Vacío / URL de tu Página de Facebook | Enlace a tu perfil de Facebook. Vacío = sin icono. |
| Configuración del Módulo | URL de Twitter | Vacío / URL de tu Perfil de Twitter | Enlace a tu perfil de Twitter. Vacío = sin icono. |
| Configuración del Módulo | URL de YouTube | Vacío / URL de tu Canal de YouTube | Enlace a tu canal de YouTube. Vacío = sin icono. |
| Configuración del Módulo | URL de Google+ | Vacío / URL de tu Perfil de Google+ | Enlace a tu perfil de Google+. Vacío = sin icono. |
| Configuración del Módulo | URL de RSS | Vacío / URL de tu Feed RSS | Enlace a tu feed RSS. Vacío = sin icono. |
| Configuración del Módulo | Mostrar en la Cabecera | No / Sí | Mostrar enlaces sociales en la cabecera de la tienda. |
| Configuración del Módulo | Mostrar en la Columna Izquierda | No / No | Mostrar enlaces sociales en la barra lateral izquierda. |
| Configuración del Módulo | Mostrar en la Columna Derecha | No / Sí | Mostrar enlaces sociales en la barra lateral derecha. |
| Configuración del Módulo | Mostrar en el Pie de Página | No / Sí | Mostrar enlaces sociales en el pie de página de la tienda. |
| Configuración del Módulo | Mostrar en la Página de Producto | No / Sí | Mostrar enlaces sociales en las páginas de productos individuales. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

- **P: Mis iconos sociales no aparecen después de la configuración.**

  - **R:** Primero, verifica que hayas introducido las URL completas de tus redes sociales en la configuración del módulo. Además, asegúrate de haber seleccionado al menos una opción "Mostrar en..." (por ejemplo, "Mostrar en el Pie de Página" en Sí). Finalmente, borra la caché de PrestaShop en **Parámetros Avanzados > Rendimiento** (haz clic en el botón "Borrar caché"). A veces, la caché del tema también puede impedir que los cambios aparezcan inmediatamente.
- **P: Los iconos se muestran, pero se ven desalineados o no coinciden con mi tema.**

  - **R:** El módulo proporciona un estilo básico. Si tu tema tiene reglas CSS muy específicas, podrían anular o entrar en conflicto con los estilos del módulo.
    - **Solución 1 (Básica):** Intenta borrar la caché de tu navegador (Ctrl+F5 o Cmd+R).
    - **Solución 2 (Avanzada):** Esto generalmente requiere que un webmaster o desarrollador inspeccione el CSS de tu tema y potencialmente añada reglas CSS personalizadas al archivo `custom.css` de tu tema para ajustar la apariencia. El archivo CSS del módulo (`socialnetworklinks.css`) puede ser una referencia.
- **P: ¿Puedo añadir otras redes sociales no listadas (por ejemplo, Instagram, Pinterest)?**

  - **R:** La versión actual del módulo es compatible con Facebook, Twitter, YouTube, Google+ y RSS. Para añadir otras redes, se requeriría un desarrollo personalizado para modificar el código del módulo y añadir nuevos iconos y campos de entrada. Alternativamente, busca un módulo de redes sociales más completo si necesitas una gama más amplia de plataformas.
- **P: Los enlaces se abren en la misma pestaña, pero quiero que se abran en una nueva pestaña.**

  - **R:** Por defecto, el módulo está diseñado para abrir enlaces en una nueva pestaña (`target="_blank"`). Si esto no sucede, podría deberse a un conflicto con el JavaScript de tu tema o un navegador antiguo. Asegúrate de que tu PrestaShop y tu navegador estén actualizados. Si el problema persiste, un desarrollador necesitaría inspeccionar el HTML generado.
- **P: He habilitado "Mostrar en la Columna Izquierda/Derecha", pero no aparece nada.**

  - **R:** Muchos temas modernos de PrestaShop están diseñados sin columnas izquierda o derecha tradicionales en todas las páginas, especialmente en las páginas de productos o la página de inicio. Si tu tema no renderiza estas columnas, el módulo no tendrá un lugar donde mostrar su bloque. Consulta la documentación de tu tema o personaliza su diseño para habilitar las columnas donde quieras que aparezca el módulo. El pie de página y la cabecera son generalmente ubicaciones de visualización más fiables en todos los temas.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo "Enlaces a Redes Sociales" es un módulo de PrestaShop sencillo que sigue un patrón similar a MVC básico dentro del alcance del módulo. Utiliza principalmente la clase `Module` para su funcionalidad principal, configuración y registro de hooks. Almacena sus ajustes directamente en la tabla `ps_configuration` de PrestaShop. La visualización en el front-office del módulo se gestiona a través de una única plantilla Smarty renderizada mediante varios hooks de visualización.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador de Front-Office o Back-Office Admin personalizado. Toda la configuración se gestiona directamente dentro del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo **no** contiene ninguna clase personalizada o definiciones de `ObjectModel`. Toda la lógica está encapsulada dentro de la clase principal `SocialNetworkLinks`.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo **no** contiene ningún archivo JavaScript personalizado. La funcionalidad para abrir enlaces en nuevas pestañas se maneja directamente en el HTML de la plantilla usando `target="_blank"`.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- **`socialnetworklinks/css/socialnetworklinks.css`**
  - **Alcance:** Estilo para el cliente en el front-office.
  - **Componentes e interfaces de usuario principales que estiliza:** Esta hoja de estilo proporciona la apariencia visual básica para los iconos de redes sociales, incluyendo su tamaño, espaciado y, potencialmente, efectos de hover. Se dirige al bloque contenedor principal y a los elementos individuales de los enlaces sociales.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular en su tema:**
    - `.socialnetworklinks_block`: El contenedor principal para el bloque de enlaces sociales.
    - `.socialnetworklinks_block ul`: La lista desordenada que contiene los iconos sociales.
    - `.socialnetworklinks_block li`: Elementos de lista individuales para cada icono social.
    - `.socialnetworklinks_block li a`: La etiqueta de anclaje para cada enlace social.
    - `.socialnetworklinks_block li a i`: El elemento de icono (por ejemplo, Font Awesome o similar, dependiendo del tema).
    - Clases específicas para cada red social (por ejemplo, `.facebook`, `.twitter`, etc.) pueden estar presentes o pueden añadirse para un estilo personalizado por red.

### 4.6 Estructura de la Plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - **`socialnetworklinks/views/front/column.tpl`**:
    - **Hook(s) renderizado(s) en:** `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (o un hook similar de página de producto dependiendo de la versión de PrestaShop y el tema).
    - **Salida del bloque visual:** Esta plantilla renderiza la estructura HTML para el bloque de enlaces a redes sociales. Itera a través de las URL de redes sociales configuradas y muestra un icono (típicamente usando una biblioteca de iconos de fuente como Font Awesome, que generalmente es proporcionada por el tema o el núcleo de PrestaShop) para cada enlace activo. Cada icono está envuelto en una etiqueta `<a>` con `target="_blank"` para abrir el enlace en una nueva pestaña.
    - **Variables disponibles:**
      - `$facebook_url`: La URL de Facebook configurada.
      - `$twitter_url`: La URL de Twitter configurada.
      - `$youtube_url`: La URL de YouTube configurada.
      - `$google_url`: La URL de Google+ configurada.
      - `$rss_url`: La URL de RSS configurada.
      - `$module_dir`: El directorio base del módulo, útil para enlazar a los activos del módulo (aunque no se usa mucho en esta plantilla específica).

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:
  El módulo no crea ninguna tabla de base de datos personalizada. Todos los ajustes de configuración se almacenan en la tabla `ps_configuration` utilizando claves con el prefijo `SOCIALNETWORKLINKS_`.

  - `PS_SOCIALNETWORKLINKS_FACEBOOK_URL`
  - `PS_SOCIALNETWORKLINKS_TWITTER_URL`
  - `PS_SOCIALNETWORKLINKS_YOUTUBE_URL`
  - `PS_SOCIALNETWORKLINKS_GOOGLE_URL`
  - `PS_SOCIALNETWORKLINKS_RSS_URL`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_HEADER`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_LEFT_COLUMN`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_RIGHT_COLUMN`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_FOOTER`
  - `PS_SOCIALNETWORKLINKS_DISPLAY_PRODUCT_PAGE`
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Renderiza contenido dentro de la sección `<head>` o en la parte superior del `<body>`. | Se utiliza para mostrar el bloque de enlaces sociales en la cabecera de la tienda. |
| `displayLeftColumn` | Renderiza contenido en la barra lateral izquierda. | Se utiliza para mostrar el bloque de enlaces sociales en la columna izquierda. |
| `displayRightColumn` | Renderiza contenido en la barra lateral derecha. | Se utiliza para mostrar el bloque de enlaces sociales en la columna derecha. |
| `displayFooter` | Renderiza contenido en el pie de página de la tienda. | Se utiliza para mostrar el bloque de enlaces sociales en el pie de página. |
| `displayProductButtons` (o hook similar de página de producto) | Renderiza contenido en la página del producto, a menudo cerca del botón "Añadir al carrito" o la descripción del producto. | Se utiliza para mostrar el bloque de enlaces sociales en las páginas de productos individuales. |
| `moduleRoutes` | (Gestionado implícitamente por PrestaShop para la configuración del módulo) | No se utiliza directamente para la visualización en el front-office, pero forma parte del ciclo de vida del módulo. |
| `actionAdminControllerSetMedia` | (Gestionado implícitamente por PrestaShop para la configuración del módulo) | Se utiliza para cargar CSS/JS en el back office para la página de configuración del módulo. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Enlaces a Redes Sociales", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto a la funcionalidad y compatibilidad del módulo.

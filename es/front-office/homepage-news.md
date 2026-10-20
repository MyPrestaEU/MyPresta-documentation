---
title: "Noticias de la página de inicio - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Noticias de la página de inicio' de MyPresta.eu."
sidebar:
  label: "Noticias de la página de inicio - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Homepage news en MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-news.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/homepage-news/)
>
> ---


# Noticias de la página de inicio

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop en sí y son suficientes para este módulo.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Noticias de la página de inicio", donde controla cómo se muestran sus artículos de noticias en la página de inicio.

#### **Seleccionar categoría de páginas CMS**

- **Qué hace este ajuste:** Este desplegable le permite elegir qué categoría CMS específica se utilizará como fuente para las noticias de su página de inicio. Solo las páginas CMS que pertenezcan a esta categoría seleccionada serán consideradas para su visualización por el módulo.
- **Efecto de cambiar este ajuste:**
  - *Cuando se selecciona una categoría:* El módulo buscará y mostrará artículos de noticias solo de las páginas CMS dentro de esa categoría.
  - *Cuando no se selecciona ninguna categoría (o una inapropiada):* El módulo podría no mostrar ninguna noticia, o podría mostrar páginas que no pretendía que fueran artículos de noticias.
- **Valor recomendado:** Seleccione la categoría CMS que haya creado o designado específicamente para sus artículos de noticias (por ejemplo, "Noticias", "Blog", "Actualizaciones").
- **Escenario / ejemplo de comerciante:** Ha creado una categoría CMS llamada "Noticias de la empresa" y ha añadido varias páginas CMS a ella, como "Lanzamiento de nuevo producto", "Anuncio de rebajas de verano" y "Horario de apertura en vacaciones". Al seleccionar "Noticias de la empresa" aquí, solo estas páginas aparecerán como noticias en su página de inicio.

#### **Mostrar contenido completo de la última página CMS**

- **Qué hace este ajuste:** Este interruptor determina si el último artículo de noticias (página CMS) de su categoría seleccionada se mostrará con su contenido completo directamente en la página de inicio.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El contenido completo del artículo de noticias más reciente será visible en su página de inicio, proporcionando información inmediata sin necesidad de hacer clic.
  - *Cuando está deshabilitado (NO):* Solo se mostrará el título, la miniatura y una breve descripción (si está configurada) del último artículo de noticias, de forma similar a otras miniaturas. Los clientes deberán hacer clic para leer el contenido completo.
- **Valor recomendado:** "SÍ" si desea destacar sus noticias más importantes de inmediato; "NO" si prefiere una sección de noticias más compacta donde todos los artículos requieren un clic.
- **Escenario / ejemplo de comerciante:** Tiene un anuncio importante, como la apertura de una nueva tienda. Habilitar esto asegura que los clientes vean los detalles completos de inmediato. Si prefiere una página de inicio más limpia, podría deshabilitarlo y mostrar solo extractos.

#### **Mostrar miniaturas de páginas CMS**

- **Qué hace este ajuste:** Este interruptor controla si se muestran versiones más pequeñas y resumidas (miniaturas) de sus artículos de noticias en la página de inicio. Estas miniaturas suelen incluir un título, una pequeña imagen y una breve descripción.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El módulo mostrará una serie de bloques de noticias en miniatura, cada uno representando una página CMS reciente de su categoría seleccionada.
  - *Cuando está deshabilitado (NO):* No se mostrarán miniaturas. Si "Mostrar contenido completo de la última página CMS" también está deshabilitado, no aparecerá ninguna noticia.
- **Valor recomendado:** "SÍ" para proporcionar una visión general de varios artículos de noticias y fomentar la exploración.
- **Escenario / ejemplo de comerciante:** Desea mostrar los últimos 3-5 artículos de noticias para que los clientes puedan echar un vistazo rápido a las actualizaciones recientes. Habilitar las miniaturas logra esto.

#### **Número de miniaturas a mostrar**

- **Qué hace este ajuste:** Si "Mostrar miniaturas de páginas CMS" está habilitado, este campo de entrada determina cuántas de las miniaturas de artículos de noticias más recientes se mostrarán en su página de inicio.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un número mayor (por ejemplo, 5):* Se verán más miniaturas de artículos de noticias, proporcionando una visión general más amplia.
  - *Cuando se establece un número menor (por ejemplo, 2):* Se mostrarán menos miniaturas, haciendo la sección de noticias más concisa.
- **Valor recomendado:** De 3 a 5, dependiendo del diseño de su página de inicio y de cuánto espacio desee dedicar a las noticias.
- **Escenario / ejemplo de comerciante:** Tiene muchas noticias pero quiere mantener su página de inicio limpia. Establecer esto en "3" asegura que solo se destaquen los tres artículos más recientes.

#### **Número de caracteres utilizados en la descripción para miniaturas**

- **Qué hace este ajuste:** Este campo de entrada controla la longitud de la descripción corta (extracto) que se muestra dentro de cada miniatura de noticia.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un número mayor (por ejemplo, 200):* Las descripciones en las miniaturas serán más largas, proporcionando más contexto.
  - *Cuando se establece un número menor (por ejemplo, 50):* Las descripciones serán más cortas, haciendo las miniaturas más compactas.
- **Valor recomendado:** De 100 a 150 caracteres, suficiente para dar un buen resumen sin abrumar la miniatura.
- **Escenario / ejemplo de comerciante:** Quiere dar a los clientes la información justa en la miniatura para despertar su interés. Establecer esto en "120" asegura un fragmento conciso pero informativo.

#### **Estilo de las miniaturas**

- **Qué hace este ajuste:** Esta opción (probablemente un desplegable o botones de radio) le permite elegir el diseño visual o el estilo de cómo se presentan las miniaturas de noticias en su página de inicio. Los estilos disponibles pueden incluir opciones como una cuadrícula, una lista o un carrusel.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "Cuadrícula":* Las miniaturas pueden aparecer en filas y columnas, adecuadas para mostrar varios elementos de forma compacta.
  - *Cuando se establece en "Lista":* Las miniaturas pueden aparecer una debajo de la otra, bueno para descripciones más detalladas.
  - *Cuando se establece en "Carrusel":* Las miniaturas pueden deslizarse horizontalmente, ahorrando espacio y permitiendo a los usuarios navegar por más elementos.
- **Valor recomendado:** Experimente con los estilos disponibles para ver cuál se adapta mejor al diseño de su tema y a la estética deseada para su página de inicio.
- **Escenario / ejemplo de comerciante:** Su página de inicio tiene un espacio horizontal limitado. Elegir un estilo "Carrusel" le permite mostrar muchos elementos de noticias sin alargar demasiado la página. Si tiene mucho espacio, una "Cuadrícula" podría verse más atractiva.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Seleccionar categoría de páginas CMS | Su categoría CMS "Noticias" designada | Define qué páginas CMS se utilizan como fuente de noticias. |
| Configuración del módulo | Mostrar contenido completo de la última página CMS | SÍ | Muestra el contenido completo del artículo más reciente directamente en la página de inicio. |
| Configuración del módulo | Mostrar miniaturas de páginas CMS | SÍ | Habilita la visualización de bloques de noticias resumidos. |
| Configuración del módulo | Número de miniaturas a mostrar | 3-5 | Controla cuántas miniaturas de noticias recientes se muestran. |
| Configuración del módulo | Número de caracteres utilizados en la descripción para miniaturas | 100-150 | Establece la longitud del extracto de texto en las miniaturas. |
| Configuración del módulo | Estilo de las miniaturas | Varía (por ejemplo, Cuadrícula, Lista, Carrusel) | Determina el diseño visual de las miniaturas de noticias. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: Mi sección de noticias no aparece en la página de inicio. ¿Qué debo verificar?**
R:

1.  **Módulo habilitado:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Noticias de la página de inicio" esté instalado y habilitado.
2.  **Categoría CMS seleccionada:** En la configuración del módulo, verifique que haya seleccionado una categoría CMS válida en "Seleccionar categoría de páginas CMS".
3.  **Existen páginas CMS:** Asegúrese de que haya páginas CMS reales publicadas dentro de la categoría seleccionada.
4.  **Configuración de visibilidad:** Verifique si "Mostrar miniaturas de páginas CMS" y/o "Mostrar contenido completo de la última página CMS" están habilitados en la configuración del módulo. Si ambos están deshabilitados, no se mostrará nada.
5.  **Caché:** Borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**).

**P: Las imágenes de mis miniaturas de noticias no aparecen.**
R: El módulo normalmente intenta extraer la primera imagen del contenido de su página CMS.

1.  **Imagen en la página CMS:** Asegúrese de que el contenido de su página CMS realmente incluya una imagen.
2.  **Ruta de la imagen:** Verifique que la ruta de la imagen en su página CMS sea correcta y que el archivo de imagen exista en su servidor.
3.  **Compatibilidad del tema:** Algunos temas personalizados pueden interferir con la representación de imágenes. Si todo lo demás falla, consulte a su desarrollador de temas o al soporte de MyPresta.eu.

**P: ¿Cómo traduzco los títulos y descripciones de las noticias?**
R: Los títulos y el contenido de las noticias provienen directamente de sus páginas CMS.

1.  **Traducciones de páginas CMS:** Vaya a **Diseño > Páginas** (o **CMS** en versiones anteriores), edite su página CMS de noticias.
2.  **Editar en todos los idiomas:** Para cada idioma que admita, asegúrese de haber proporcionado el título y el contenido traducidos para esa página CMS específica. El módulo mostrará automáticamente el idioma correcto según el idioma de la tienda seleccionado por el cliente.

**P: La sección de noticias se ve extraña o desalineada en mi página de inicio.**
R: Esto suele ser un conflicto de CSS con el tema de su tienda.

1.  **Borrar caché:** Siempre comience borrando la caché de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**).
2.  **Configuración del módulo:** Verifique si cambiar la configuración de "Estilo de las miniaturas" ayuda.
3.  **Personalización del tema:** El CSS de su tema podría estar anulando los estilos del módulo. Es posible que deba consultar a un desarrollador web para agregar CSS personalizado a su tema para ajustar la apariencia. El soporte de MyPresta.eu puede ofrecer orientación, pero no puede proporcionar desarrollo de temas personalizados.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura

El módulo "Noticias de la página de inicio" (`hnews`) es un módulo de PrestaShop sencillo diseñado principalmente para mostrar contenido de páginas CMS existentes en la página de inicio del front-office. Aprovecha la clase `Module` de PrestaShop y los hooks estándar. La lógica del módulo reside principalmente en su archivo PHP principal, `hnews.php`, que maneja la configuración, el registro de hooks y la recuperación de datos. No introduce controladores personalizados ni ObjectModels complejos, sino que se basa en las clases nativas `CMSCategory` y `CMS` de PrestaShop para los datos.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. La lógica de visualización del front-office del módulo se maneja completamente mediante su método `hookDisplayHome` dentro de `hnews.php` y se renderiza a través de una plantilla Smarty.
-   **Controladores de administración de Back-Office**: Ninguno. Toda la configuración se gestiona a través del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

-   Este módulo no introduce clases ni ObjectModels personalizados. Consulta directamente la base de datos o utiliza las clases `CMSCategory` y `CMS` del núcleo de PrestaShop para recuperar datos.

### 4.4 Activos de JavaScript (`views/js/`)

-   No se incluyen archivos JavaScript personalizados en este módulo.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `hnews/views/admin/css/hnews.css`:
    -   **Alcance:** Estilo del formulario de administración del back-office.
    -   **Componentes principales de la interfaz de usuario:** Probablemente contiene estilos específicos para la página de configuración del módulo, asegurando un diseño consistente y legible dentro del back office de PrestaShop.
    -   **Selectores de clase CSS clave:** Puede incluir estilos para elementos de formulario, etiquetas y contenedores específicos utilizados en `getContent()`.
-   `hnews/views/css/hnews.css`:
    -   **Alcance:** Estilo del cliente del front-office.
    -   **Componentes principales de la interfaz de usuario:** Estiliza la sección de noticias que se muestra en la página de inicio, incluido el artículo de noticias principal (si se muestra el contenido completo) y las miniaturas de noticias individuales.
    -   **Selectores de clase CSS clave:** Contendrá selectores para el contenedor principal de noticias, bloques de miniaturas individuales, títulos, descripciones e imágenes. Los desarrolladores pueden anular estas clases en el `custom.css` o `theme.css` de su tema para que coincidan con el diseño de la tienda.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `hnews/views/hnews.tpl`: Esta es la plantilla principal del front-office.
        -   **Hook:** Renderizado en `displayHome`.
        -   **Bloque visual:** Muestra toda la sección de noticias en la página de inicio, incluido el contenido completo del último artículo de noticias (si está habilitado) y la lista de miniaturas de noticias. Itera a través de los artículos de noticias pasados desde la lógica PHP del módulo.
-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `hnews/views/admin/elements.tpl`:
        -   **Hook:** No enganchado directamente, pero incluido/renderizado por el método `getContent()` en `hnews.php`.
        -   **Bloque visual:** Renderiza los elementos del formulario de configuración para el módulo en el back office de PrestaShop. Esto suele incluir el desplegable para categorías CMS, interruptores para opciones de visualización y campos de entrada para recuentos y límites de caracteres.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    -   El módulo no crea ninguna tabla SQL personalizada.
    -   Almacena su configuración en la tabla `ps_configuration` utilizando claves como `HNEWS_ID_CMSCAT`, `HNEWS_NB_MIN`, `HNEWS_LATEST`, `HNEWS_SIZE_MIN`, `HNEWS_CHR_MIN`, `HNEWS_MINIATURES`.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHome` | Renderiza contenido en el área principal de la página de inicio. | Muestra la sección de noticias con las últimas páginas CMS. |
| `displayHeader` | Ejecutado en la sección `<head>` de la página del front-office. | Potencialmente utilizado para cargar activos CSS o JS del front-office (aunque no hay JS presente, se carga CSS). |
| `actionAdminControllerSetMedia` | Ejecutado cuando un controlador de administración establece sus medios (CSS/JS). | Utilizado para cargar CSS del back-office para la página de configuración del módulo. |
| `header` | Similar a `displayHeader`, a menudo utilizado para la carga de activos. | Potencialmente utilizado para cargar activos CSS o JS del front-office. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Noticias de la página de inicio", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier consulta o problema relacionado con el módulo.

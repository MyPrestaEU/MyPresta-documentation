---
title: "Free My AI Act - Cumplimiento de la Ley de Inteligencia Artificial - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Free My AI Act - Artificial Intelligence Act compliance de MyPresta.eu."
sidebar:
  label: "Free My AI Act - Cumplimiento de la Ley de Inteligencia Artificial"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Free My AI Act - Artificial Intelligence Act compliance en MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-my-ai-act-artificial-intelligence-act-compliance.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/free-my-ai-act-artificial-intelligence-act-compliance/)
>
> ---


# Free My AI Act - Cumplimiento de la Ley de Inteligencia Artificial

## 1. Requisitos y Compatibilidad
-   **Versiones de PrestaShop Compatibles**: PrestaShop 9.x
-   **Compatibilidad con PHP**: PHP 7.4 - 8.5
-   **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una instalación de PrestaShop y son suficientes para este módulo.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)
Para acceder a la configuración del módulo, navegue a **Módulos > Gestor de módulos**, busque "Free My AI Act" y haga clic en el botón "Configurar".

Esta pantalla proporciona todos los ajustes esenciales para controlar cómo se divulga el contenido de IA en su tienda.

#### **Configuración General**

-   **Activar Cumplimiento de la Ley de IA:**
    -   **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar las funciones del módulo en toda su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Todas las funciones de divulgación de IA configuradas (insignias, banners, avisos) se activarán en su front office.
        -   *Cuando está desactivado:* Todas las funciones de divulgación de IA se ocultarán y el módulo no mostrará ninguna información relacionada con la IA a los clientes.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo del comerciante:** Ha completado su configuración y está listo para implementar el cumplimiento de la Ley de IA. Active este ajuste. Si necesita desactivar temporalmente todas las divulgaciones por mantenimiento, cámbielo a NO.

#### **Opciones de Divulgación de Contenido de IA**

-   **Mostrar Insignia de IA en Imágenes de Productos:**
    -   **Qué hace este ajuste:** Controla si aparece una pequeña insignia (por ejemplo, "Generado por IA" o un icono) directamente en las imágenes de los productos en los listados de categorías y en la página del producto.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Se superpondrá un indicador visual en las imágenes de los productos que haya marcado como generados por IA.
        -   *Cuando está desactivado:* No aparecerá ninguna insignia en las imágenes de los productos, incluso si están marcadas como generadas por IA.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo del comerciante:** Utiliza IA para generar o mejorar muchas de las fotos de sus productos. Al activar esto, proporciona una divulgación visual inmediata a los clientes mientras navegan.

-   **Mostrar Aviso de Información Adicional en la Página del Producto:**
    -   **Qué hace este ajuste:** Determina si se muestra un aviso de texto dedicado en las páginas de productos individuales para informar a los clientes sobre el contenido generado por IA (texto o imágenes) para ese producto específico.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Aparecerá un bloque de texto personalizable en las páginas de productos, normalmente debajo de la descripción o en una nueva pestaña, detallando el uso de IA para el contenido de ese producto.
        -   *Cuando está desactivado:* No se mostrará ningún aviso específico de divulgación de IA en las páginas de productos.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo del comerciante:** Desea proporcionar una explicación más detallada sobre el contenido de IA para cada producto. Este aviso le permite elaborar más allá de una simple insignia.

-   **Mostrar Banner de Política de IA en Toda la Tienda:**
    -   **Qué hace este ajuste:** Activa un banner que aparece de forma consistente en toda su tienda (por ejemplo, en la parte superior o inferior de cada página) para informar a los visitantes sobre su política general de contenido de IA.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Un banner personalizable será visible en todas las páginas, a menudo con un enlace a una página de política de IA más completa.
        -   *Cuando está desactivado:* No se mostrará ningún banner en toda la tienda.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo del comerciante:** Desea hacer una declaración general sobre el uso de IA en su tienda y dirigir a los clientes a una página de política dedicada para una transparencia total.

-   **Enlace a la Página de Política de IA (URL):**
    -   **Qué hace este ajuste:** Le permite especificar la URL de una página CMS o un enlace externo donde los clientes pueden encontrar su política detallada de contenido de IA. Este enlace se incluirá normalmente en el banner de toda la tienda o en los avisos de información adicional.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce una URL:* El banner y los avisos incluirán un enlace clicable a esta página.
        -   *Cuando se deja vacío:* No se proporcionará ningún enlace, o el banner/aviso podría no aparecer si depende de este enlace.
    -   **Valor recomendado:** `[La URL de su página CMS, por ejemplo, /content/10-ai-policy]`
    -   **Escenario / ejemplo del comerciante:** Ha creado una página CMS dedicada que explica su uso de IA, sus prácticas de datos y su compromiso con la transparencia. Introduzca su URL aquí para que los clientes puedan acceder a ella fácilmente.

#### **Personalización de Contenido**

-   **Texto de la Insignia de IA (por ejemplo, "IA"):**
    -   **Qué hace este ajuste:** Define el texto corto que aparece en la insignia de IA superpuesta en las imágenes de los productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se cambia:* El texto de la insignia se actualizará en consecuencia.
    -   **Valor recomendado:** IA
    -   **Escenario / ejemplo del comerciante:** Prefiere una etiqueta más corta como "IA" en lugar de "Generado por IA" para mantener la insignia concisa.

-   **Color de la Insignia de IA:**
    -   **Qué hace este ajuste:** Establece el color de fondo de la insignia de IA.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se cambia:* El color de fondo de la insignia se actualizará, permitiéndole que coincida con la marca de su tienda.
    -   **Valor recomendado:** #FF0000 (Rojo) o un color que contraste bien con las imágenes de sus productos.
    -   **Escenario / ejemplo del comerciante:** Su marca utiliza una paleta de colores específica. Puede establecer el color de la insignia en un tono contrastante que siga siendo visualmente atractivo.

-   **Color del Texto de la Insignia de IA:**
    -   **Qué hace este ajuste:** Establece el color del texto dentro de la insignia de IA.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se cambia:* El color del texto de la insignia se actualizará.
    -   **Valor recomendado:** #FFFFFF (Blanco) o un color que contraste bien con el fondo de insignia elegido.
    -   **Escenario / ejemplo del comerciante:** Si el fondo de su insignia es oscuro, querrá texto blanco o de color claro para facilitar la lectura.

-   **Texto del Aviso de Información Adicional:**
    -   **Qué hace este ajuste:** Le permite personalizar el texto completo que se muestra en el "Aviso de Información Adicional" en las páginas de productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se cambia:* El contenido del aviso en las páginas de productos reflejará su texto personalizado.
    -   **Valor recomendado:** "Tenga en cuenta: Partes de la descripción de este producto y/o imágenes pueden haber sido generadas o mejoradas utilizando Inteligencia Artificial para proporcionarle información completa."
    -   **Escenario / ejemplo del comerciante:** Desea indicar claramente que tanto el texto como las imágenes pueden ser generados por IA y explicar por qué (por ejemplo, para obtener información completa).

-   **Texto del Banner en Toda la Tienda:**
    -   **Qué hace este ajuste:** Personaliza el mensaje que se muestra en el banner de política de IA en toda la tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se cambia:* El texto del banner en todas las páginas se actualizará.
    -   **Valor recomendado:** "Nuestra tienda utiliza IA para mejorar el contenido. Obtenga más información sobre nuestra política de IA."
    -   **Escenario / ejemplo del comerciante:** Desea un mensaje conciso en el banner que anime a los clientes a hacer clic en el enlace para obtener más detalles.

#### **Marcado de IA Específico del Producto**

Este módulo también se integra directamente en su página de edición de productos. Cuando edite un producto en el Back Office (**Catálogo > Productos > Editar Producto**), encontrará una nueva pestaña o sección relacionada con "Cumplimiento de la Ley de IA".

-   **Marcar Contenido del Producto como Generado por IA:**
    -   **Qué hace este ajuste:** Una casilla de verificación o un interruptor en la página de edición del producto que le permite marcar individualmente el contenido de texto de un producto específico (descripción, descripción corta, características) como generado por IA.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado para un producto:* El "Aviso de Información Adicional" (si está activado en la configuración del módulo) aparecerá en la página de ese producto, y se activarán otras divulgaciones de IA basadas en texto.
        -   *Cuando está desactivado para un producto:* No aparecerán divulgaciones de IA basadas en texto para ese producto específico.
    -   **Valor recomendado:** Activar para cualquier producto en el que se haya utilizado IA para el texto.
    -   **Escenario / ejemplo del comerciante:** Utilizó un asistente de escritura de IA para crear la descripción larga de un nuevo producto. Actuaría este ajuste para ese producto específico.

-   **Marcar Imágenes del Producto como Generadas por IA:**
    -   **Qué hace este ajuste:** Una casilla de verificación o un interruptor en la página de edición del producto que le permite marcar individualmente las imágenes de un producto específico como generadas o mejoradas por IA.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado para un producto:* La "Insignia de IA" (si está activada en la configuración del módulo) aparecerá en las imágenes de ese producto, y también se activará el "Aviso de Información Adicional".
        -   *Cuando está desactivado para un producto:* No aparecerá ninguna insignia de IA en las imágenes de ese producto específico.
    -   **Valor recomendado:** Activar para cualquier producto en el que se haya utilizado IA para las imágenes.
    -   **Escenario / ejemplo del comerciante:** Utilizó un generador o mejorador de imágenes de IA para la imagen principal del producto. Actuaría este ajuste para ese producto específico.

#### 2.1.1 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Configuración del Módulo | Activar Cumplimiento de la Ley de IA | SÍ | Interruptor principal para todas las funciones del módulo. |
| Configuración del Módulo | Mostrar Insignia de IA en Imágenes de Productos | SÍ | Muestra la insignia "IA" en las imágenes de productos marcadas con IA. |
| Configuración del Módulo | Mostrar Aviso de Información Adicional en la Página del Producto | SÍ | Muestra un aviso de texto en las páginas de productos marcadas con IA. |
| Configuración del Módulo | Mostrar Banner de Política de IA en Toda la Tienda | SÍ | Muestra un banner en todas las páginas para la política general. |
| Configuración del Módulo | Enlace a la Página de Política de IA (URL) | `/content/10-ai-policy` | URL de su página de política de IA detallada. |
| Configuración del Módulo | Texto de la Insignia de IA | IA | Texto que se muestra en la insignia de la imagen del producto. |
| Configuración del Módulo | Color de la Insignia de IA | `#FF0000` (Rojo) | Color de fondo de la insignia de IA. |
| Configuración del Módulo | Color del Texto de la Insignia de IA | `#FFFFFF` (Blanco) | Color del texto de la insignia de IA. |
| Configuración del Módulo | Texto del Aviso de Información Adicional | Personalizable | Texto completo para el aviso de la página del producto. |
| Configuración del Módulo | Texto del Banner en Toda la Tienda | Personalizable | Texto completo para el banner en toda la tienda. |
| Página de Edición del Producto | Marcar Contenido del Producto como Generado por IA | N/A (por producto) | Marca el contenido de texto del producto como generado por IA. |
| Página de Edición del Producto | Marcar Imágenes del Producto como Generadas por IA | N/A (por producto) | Marca las imágenes del producto como generadas por IA. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: He habilitado el módulo y configurado los ajustes, pero no veo ninguna insignia o banner de IA en mi tienda.**
**R1:**
1.  **Verifique "Activar Cumplimiento de la Ley de IA":** Asegúrese de que el interruptor principal en la configuración del módulo esté configurado en SÍ.
2.  **Borrar Caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Es posible que también deba borrar la caché de su navegador (Ctrl+F5 o Cmd+R).
3.  **Verifique la Configuración Individual del Producto:** Para las insignias y los avisos de la página del producto, asegúrese de haber marcado individualmente los productos específicos como que tienen contenido/imágenes generados por IA en sus respectivas páginas de edición de productos.
4.  **Compatibilidad del Tema:** Si bien el módulo está diseñado para PrestaShop 9.x, los temas personalizados a veces pueden interferir. Si los problemas persisten, cambie temporalmente al tema predeterminado de PrestaShop para descartar un conflicto de tema.

**P2: La insignia o el banner de IA se ve extraño o está mal colocado en mi tema personalizado.**
**R2:** Esto suele ser un conflicto de CSS con su tema.
1.  **Inspeccionar Elemento:** Utilice las herramientas de desarrollador de su navegador (F12) para inspeccionar la insignia/banner de IA. Busque reglas CSS en conflicto.
2.  **CSS Personalizado:** Es posible que deba agregar CSS personalizado a la hoja de estilo de su tema (o a través de un módulo CSS personalizado) para ajustar el posicionamiento o el estilo. Las clases CSS del módulo suelen estar bien definidas (por ejemplo, `.myaiactfree-badge`, `.myaiactfree-banner`).
3.  **Contactar Soporte:** Si no se siente cómodo con CSS, póngase en contacto con el soporte de MyPresta.eu o con su desarrollador web para obtener ayuda.

**P3: ¿Cómo traduzco el texto de la insignia de IA, el texto del banner o el aviso de información adicional a otros idiomas?**
**R3:**
1.  Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop.
2.  Seleccione "Traducciones de módulos instalados" para el "Tipo de traducción".
3.  Elija su tema y el idioma al que desea traducir.
4.  Busque el módulo "Free My AI Act" en la lista. Podrá traducir los campos de texto que configuró (Texto de la Insignia de IA, Texto del Aviso de Información Adicional, Texto del Banner en Toda la Tienda) directamente allí.
5.  Guarde sus cambios.

**P4: ¿Cuál es la diferencia entre este módulo "Gratuito" y "My AI Act Pro"?**
**A4:** El módulo "Free My AI Act" proporciona funciones esenciales de divulgación para el cumplimiento básico. "My AI Act Pro" (un módulo de pago separado) ofrece funcionalidades avanzadas como la integración de AI Studio, acceso a la API para el marcado automatizado, registros de auditoría y capacidades avanzadas de marca de agua para imágenes. La versión gratuita es un excelente punto de partida, y puede actualizar a Pro si sus necesidades se vuelven más complejas.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica para desarrolladores y webmasters que buscan comprender, extender o solucionar problemas del módulo "Free My AI Act".

### 4.1 Descripción General de la Arquitectura
El módulo `myaiactfree` sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente los hooks para la visualización en el front-office y `getContent()` para la configuración en el back-office. Se integra directamente en la interfaz de edición de productos enganchándose a `displayAdminProductsExtra` para proporcionar opciones de marcado de IA específicas del producto. La configuración se almacena en `ps_configuration`, y la representación del front-office se logra a través de plantillas Smarty y un archivo JavaScript dedicado para interacciones dinámicas.

### 4.2 Controladores (`controllers/`)
Este módulo no contiene ningún controlador dedicado de front-office o back-office. Toda la lógica del front-office se maneja a través de hooks dentro del archivo principal del módulo, y la configuración del back-office se gestiona mediante el método `getContent()`.

### 4.3 Clases y Modelos Principales (`classes/`)
Este módulo no define ninguna clase personalizada o instancias de `ObjectModel`. Todos los datos se gestionan directamente a través de `Configuration` para la configuración global y las propiedades de `Product` para las banderas específicas del producto.

### 4.4 Activos JavaScript (`views/js/`)

-   **`myaiactfree/views/js/front.js`**
    *   **Alcance:** Front-office.
    *   **Responsabilidad:** Este script es probablemente responsable de cualquier comportamiento dinámico del front-office relacionado con los elementos de divulgación de IA. Esto podría incluir:
        *   Inicializar la visualización de la insignia de IA en las imágenes de los productos después de que el DOM esté listo.
        *   Manejar los eventos de clic en el banner de la política de IA (si es descartable o tiene elementos interactivos).
        *   Asegurar el posicionamiento y la capacidad de respuesta adecuados de la insignia o el banner de IA, especialmente si las imágenes se cargan dinámicamente o se redimensionan.
        *   Potencialmente agregar tooltips o popovers al pasar el ratón sobre las insignias de IA.
        *   Vincularse a eventos `prestashop.on` para actualizaciones de contenido dinámico (por ejemplo, `updateProduct` en la página del producto).

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   **`myaiactfree/views/css/admin.css`**
    *   **Alcance:** Estilo del formulario de administración del back-office.
    *   **Responsabilidad:** Proporciona estilo para la página de configuración del módulo (`configure.tpl`) y potencialmente la pestaña/sección personalizada agregada a la página de edición del producto (`product_tab.tpl`). Esto garantiza una apariencia consistente y fácil de usar dentro del Back Office de PrestaShop.
    *   **Selectores de clase CSS clave:** Probablemente apunta a elementos dentro del formulario de configuración del módulo, como campos de entrada específicos, etiquetas o bloques de información.

-   **`myaiactfree/views/css/front.css`**
    *   **Alcance:** Estilo del cliente del front-office.
    *   **Responsabilidad:** Define la apariencia visual de todos los elementos de divulgación de IA visibles para los clientes. Esto incluye:
        *   Estilo para la insignia de IA (por ejemplo, `.myaiactfree-badge`, `.myaiactfree-badge-text`, `.myaiactfree-badge-icon`), incluyendo su posición, color de fondo, color de texto, relleno y radio de borde.
        *   Estilo para el aviso de información adicional en las páginas de productos (por ejemplo, `.myaiactfree-additional-info`).
        *   Estilo para el banner de política de IA en toda la tienda (por ejemplo, `.myaiactfree-banner`, `.myaiactfree-banner-text`, `.myaiactfree-banner-link`).
    *   **Selectores de clase CSS clave:** Los desarrolladores pueden anular estas clases en el CSS personalizado de su tema para que coincidan con el diseño de su marca.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    *   **`myaiactfree/views/templates/hook/additional_info.tpl`**:
        *   **Hook:** Probablemente se renderiza en `displayProductExtraContent` o hooks similares de la página del producto.
        *   **Salida:** Muestra el texto personalizable del "Aviso de Información Adicional" en la página del producto cuando un producto está marcado como generado por IA.
    *   **`myaiactfree/views/templates/hook/ai_badge.tpl`**:
        *   **Hook:** Probablemente se renderiza en `displayProductListReviews` (para listados de productos) o `displayProductAdditionalInfo` (para la imagen de la página del producto).
        *   **Salida:** Genera la estructura HTML para la insignia de IA que se superpone a las imágenes de los productos, incluyendo el texto y el estilo personalizables.
    *   **`myaiactfree/views/templates/hook/banner.tpl`**:
        *   **Hook:** Probablemente se renderiza en `displayHeader`, `displayTop`, `displayWrapperTop` o `displayFooter`.
        *   **Salida:** Renderiza el banner de política de IA en toda la tienda, incluyendo el texto personalizable y un enlace a la página de política de IA.

-   **Plantillas de administración (`views/templates/admin/`)**:
    *   **`myaiactfree/views/templates/admin/configure.tpl`**:
        *   **Propósito:** Esta es la plantilla principal para la página de configuración del módulo a la que se accede a través de `getContent()`. Renderiza todos los ajustes globales (activar/desactivar, texto de la insignia, texto del banner, etc.) como se describe en la sección 4.1.
    *   **`myaiactfree/views/templates/admin/configure_intro.tpl`**:
        *   **Propósito:** Probablemente muestra un mensaje introductorio o una explicación en la parte superior de la página de configuración del módulo, quizás explicando la Ley de IA o el propósito del módulo.
    *   **`myaiactfree/views/templates/admin/product_tab.tpl`**:
        *   **Hook:** Renderizado a través de `displayAdminProductsExtra`.
        *   **Propósito:** Esta plantilla proporciona la interfaz dentro de la página de edición del producto (Back Office > Catálogo > Productos > Editar Producto) donde los comerciantes pueden marcar individualmente el contenido y las imágenes de un producto como generados por IA. Contiene las casillas de verificación o los interruptores para las banderas de IA específicas del producto.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:
    *   Este módulo no crea tablas SQL personalizadas.
    *   La configuración se almacena en la tabla `ps_configuration` utilizando claves típicamente prefijadas con `MYAIACTFREE_`. Ejemplos:
        *   `MYAIACTFREE_ENABLED`
        *   `MYAIACTFREE_SHOW_BADGE`
        *   `MYAIACTFREE_BADGE_TEXT`
        *   `MYAIACTFREE_BADGE_COLOR`
        *   `MYAIACTFREE_BADGE_TEXT_COLOR`
        *   `MYAIACTFREE_SHOW_ADDITIONAL_INFO`
        *   `MYAIACTFREE_ADDITIONAL_INFO_TEXT`
        *   `MYAIACTFREE_SHOW_BANNER`
        *   `MYAIACTFREE_BANNER_TEXT`
        *   `MYAIACTFREE_POLICY_URL`
    *   Las banderas de IA específicas del producto (para contenido e imágenes) probablemente se almacenan como propiedades del objeto `Product` o en un campo personalizado asociado con la entidad `Product`, posiblemente a través de `Configuration::updateValue` con un sufijo de ID de producto o modificando directamente los datos del objeto `Product`.

-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
|---|---|---|
| `displayHeader` | En la sección `<head>` de cada página. | Inyectar activos CSS/JS (`front.css`, `front.js`) y potencialmente el banner de toda la tienda (`banner.tpl`). |
| `displayTop` / `displayWrapperTop` | A menudo en la parte superior del contenido de la página. | Hook alternativo para el banner de toda la tienda (`banner.tpl`). |
| `displayFooter` | En la parte inferior de cada página. | Hook alternativo para el banner de toda la tienda (`banner.tpl`). |
| `displayProductListReviews` | En las páginas de listado de productos, cerca de las imágenes de los productos. | Renderizar la insignia de IA (`ai_badge.tpl`) en las miniaturas de los productos. |
| `displayProductAdditionalInfo` | En la página del producto, cerca del bloque de imagen/precio del producto. | Renderizar la insignia de IA (`ai_badge.tpl`) en la imagen principal del producto. |
| `displayProductExtraContent` | En la página del producto, normalmente debajo de la descripción o en una nueva pestaña. | Renderizar el aviso de información adicional (`additional_info.tpl`). |
| `displayAdminProductsExtra` | En la página de edición del producto en el Back Office. | Inyectar la pestaña/sección personalizada para el marcado de IA específico del producto (`product_tab.tpl`). |
| `actionProductUpdate` | Después de que se actualiza un producto en el Back Office. | Guardar las banderas de IA específicas del producto (contenido/imagen) en la base de datos. |
| `actionProductAdd` | Después de que se agrega un nuevo producto en el Back Office. | Inicializar las banderas de IA específicas del producto para nuevos productos. |

## 5. Soporte Oficial y Actualizaciones
Para obtener actualizaciones oficiales, soporte técnico y acceder a las últimas versiones del módulo "Free My AI Act - Artificial Intelligence Act compliance", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad o compatibilidad del módulo.

---
title: "Free hreflang & canonical urls - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Free hreflang & canonical urls de MyPresta.eu."
sidebar:
  label: "Free hreflang & canonical urls - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Free hreflang & canonical urls en MyPresta.eu](https://mypresta.eu/modules/seo/free-hreflang-canonical-urls.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/seo/free-hreflang-canonical-urls/)
>
> ---


# Free hreflang & canonical urls

## 1. Requisitos y compatibilidad

-   **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilidad con PHP**: PHP 7.1 - 8.5
-   **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y normalmente están preinstaladas en la mayoría de los entornos de alojamiento. No se requieren configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de instalar el módulo, navegue a **Módulos > Gestor de módulos**, busque "Free hreflang & canonical urls" y haga clic en "Configurar". Se le presentará la pantalla de configuración principal del módulo.

#### **Opciones de configuración:**

-   **Activar etiquetas hreflang:**

    -   **Qué hace este ajuste:** Este interruptor maestro controla si el módulo generará y añadirá etiquetas `hreflang` al encabezado HTML de su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* El módulo generará e insertará activamente etiquetas `hreflang` para todas las versiones de idioma disponibles de sus páginas (páginas de producto, páginas de categoría, páginas CMS, etc.). Esto es crucial para el SEO internacional.
        -   *Cuando está desactivado (NO):* Este módulo no añadirá etiquetas `hreflang`. Si tiene una tienda multilingüe, los motores de búsqueda podrían tratar sus diferentes versiones de idioma como contenido duplicado, lo que podría perjudicar su posicionamiento internacional.
    -   **Valor recomendado:** **SÍ**. Active siempre esto si su tienda admite varios idiomas o se dirige a diferentes regiones.
    -   **Escenario / ejemplo de comerciante:** Si vende productos tanto en inglés como en español, al activar esto se asegura de que un cliente de habla hispana que busque en Google vea la versión en español de su página de producto, y un cliente de habla inglesa vea la versión en inglés.
-   **Activar URLs canónicas:**

    -   **Qué hace este ajuste:** Este interruptor maestro controla si el módulo generará y añadirá etiquetas de URL `canonical` al encabezado HTML de su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* El módulo generará e insertará activamente etiquetas `canonical` para todas las páginas, apuntando a la versión preferida de cada página. Esto ayuda a consolidar las señales SEO y previene problemas de contenido duplicado.
        -   *Cuando está desactivado (NO):* Este módulo no añadirá etiquetas `canonical`. Su tienda podría sufrir problemas de contenido duplicado si el mismo contenido es accesible a través de múltiples URLs (por ejemplo, con o sin barras finales, con diferentes parámetros o a través de diferentes rutas de categoría).
    -   **Valor recomendado:** **SÍ**. Las etiquetas canónicas son fundamentales para un buen SEO en casi cualquier sitio web.
    -   **Escenario / ejemplo de comerciante:** Una página de producto podría ser accesible a través de `sutienda.com/nombre-del-producto` y también `sutienda.com/categoria/nombre-del-producto`. Al activar las URLs canónicas, se le dice a Google que `sutienda.com/nombre-del-producto` es la versión principal, asegurando que todo el crédito SEO vaya a esa única URL.
-   **Usar x-default hreflang:**

    -   **Qué hace este ajuste:** El atributo `x-default` hreflang especifica una página predeterminada que debe mostrarse a los usuarios cuando ningún otro idioma/región coincide con la configuración de su navegador o ubicación.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* El módulo añadirá una etiqueta `x-default` hreflang, que normalmente apunta al idioma predeterminado de su tienda o a una versión internacional genérica. Esto es útil para los usuarios cuyo idioma o región no está explícitamente dirigido por sus otras etiquetas hreflang.
        -   *Cuando está desactivado (NO):* No se añadirá ninguna etiqueta `x-default` hreflang. A los usuarios cuyo idioma/región no coincida con ningún hreflang específico se les podría mostrar una página menos relevante, o los motores de búsqueda podrían tener que adivinar qué página mostrar.
    -   **Valor recomendado:** **SÍ**. Generalmente es una buena práctica incluir un `x-default` para un SEO internacional completo, especialmente si tiene una audiencia global.
    -   **Escenario / ejemplo de comerciante:** Si tiene versiones en inglés (EE. UU.), inglés (Reino Unido) y francés, pero un usuario de Alemania busca en inglés, el `x-default` puede dirigirlos a su página general en inglés (EE. UU.), asegurando que sigan obteniendo contenido relevante.
-   **Usar solo código de idioma (por ejemplo, "es" en lugar de "es-es"):**

    -   **Qué hace este ajuste:** Esto controla el formato de los códigos de idioma utilizados en sus etiquetas `hreflang`.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* El módulo utilizará solo el código de idioma ISO de dos letras (por ejemplo, `en`, `fr`, `de`). Esto es más simple y adecuado si se dirige a un idioma a nivel global en lugar de a regiones específicas.
        -   *Cuando está desactivado (NO):* El módulo utilizará tanto el código de idioma como el de región (por ejemplo, `en-US`, `en-GB`, `fr-CA`). Esto es más preciso y se recomienda si tiene contenido o precios diferentes para países específicos dentro del mismo idioma.
    -   **Valor recomendado:**
        -   **NO** si tiene una segmentación regional específica (por ejemplo, contenido en inglés diferente para EE. UU. frente a Reino Unido).
        -   **SÍ** si sus diferentes versiones de idioma son genéricas y no específicas de un país (por ejemplo, una versión "inglés" para todos los hablantes de inglés).
    -   **Escenario / ejemplo de comerciante:** Si vende en inglés y tiene una versión en inglés para todos los países, elija SÍ. Si tiene contenido/precios en inglés separados para EE. UU. y el Reino Unido, elija NO para usar `en-US` y `en-GB`.

#### **Guardar sus ajustes:**

Después de realizar sus selecciones, haga clic en el botón **"Guardar"** en la parte inferior de la página de configuración para aplicar sus cambios.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Activar etiquetas hreflang | SÍ | Activa las etiquetas hreflang para SEO internacional. |
| Configuración del módulo | Activar URLs canónicas | SÍ | Activa las etiquetas canónicas para evitar contenido duplicado. |
| Configuración del módulo | Usar x-default hreflang | SÍ | Proporciona una página de respaldo para usuarios con idioma/región no coincidentes. |
| Configuración del módulo | Usar solo código de idioma (por ejemplo, "es" en lugar de "es-es") | NO (depende de la estrategia) | Determina si hreflang usa solo el idioma (`es`) o el idioma-región (`es-ES`). |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He activado el módulo, pero no veo ningún cambio visual en mi sitio web. ¿Está funcionando?**
R1: Sí, ¡está funcionando como se espera! Este módulo opera completamente en segundo plano. Añade código especial (etiquetas hreflang y canónicas) a la sección `<head>` del HTML de su sitio web, que es visible para los motores de búsqueda pero no para sus clientes. Para verificar que funciona, puede hacer clic derecho en cualquier página de su tienda, seleccionar "Ver código fuente de la página" (o similar) y buscar "hreflang" o "canonical". Debería ver las etiquetas allí.

**P2: Después de activar el módulo, mi posicionamiento en las búsquedas no ha mejorado inmediatamente. ¿Qué debo esperar?**
R2: Los cambios de SEO, especialmente los relacionados con el rastreo y la indexación, tardan en reflejarse en los resultados de los motores de búsqueda. Google y otros motores de búsqueda necesitan volver a rastrear su sitio, procesar las nuevas etiquetas y actualizar su índice. Este proceso puede tardar desde unos pocos días hasta varias semanas o incluso meses. Continúe monitoreando su Google Search Console para cualquier cambio en la indexación o en los informes de segmentación internacional.

**P3: Mi tema personalizado tiene algunas estructuras de URL únicas. ¿Seguirá funcionando correctamente este módulo?**
R3: El módulo está diseñado para integrarse con los mecanismos de generación de URL principales de PrestaShop. En la mayoría de los casos, debería funcionar sin problemas con temas personalizados. Sin embargo, si su tema modifica en gran medida el enrutamiento de URL estándar o la representación de páginas de PrestaShop, existe una pequeña posibilidad de conflicto. Si sospecha un problema, primero borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**). Si los problemas persisten, póngase en contacto con el soporte de MyPresta.eu con los detalles de su tema y cualquier página específica donde vea problemas.

**P4: Tengo una tienda multilingüe, pero algunas páginas no tienen traducciones para todos los idiomas. ¿Cómo maneja esto el módulo?**
R4: El módulo normalmente genera etiquetas `hreflang` solo para los idiomas que realmente tienen contenido disponible para una página determinada. Si un producto o categoría no está traducido a un idioma específico, el módulo no debería generar una etiqueta `hreflang` para esa traducción inexistente. Asegúrese de que sus traducciones de PrestaShop se gestionen correctamente en el Back Office.

**P5: Estoy viendo varias etiquetas canónicas o etiquetas hreflang incorrectas. ¿Qué podría estar mal?**
R5: Esto suele indicar un conflicto con otro módulo SEO o con su tema que también podría estar intentando añadir etiquetas canónicas o hreflang.
1.  **Compruebe otros módulos SEO:** Desactive cualquier otro módulo SEO uno por uno para identificar el que está en conflicto.
2.  **Compruebe su tema:** Algunos temas pueden tener etiquetas canónicas codificadas.
3.  **Borrar caché:** Siempre borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**) después de realizar cualquier cambio en el módulo.
Si el problema persiste, póngase en contacto con el soporte de MyPresta.eu para obtener ayuda.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura

El módulo "Free hreflang & canonical urls" (`myhreflang`) es un módulo ligero de PrestaShop diseñado principalmente para inyectar metaetiquetas `hreflang` y `canonical` en la sección `<head>` de las páginas del front-office. Se adhiere a la arquitectura estándar de módulos de PrestaShop, utilizando hooks para integrar su funcionalidad sin modificar los archivos principales. La lógica del módulo reside principalmente en su archivo PHP principal, `index.php`, que maneja la configuración, instalación, desinstalación y la lógica central para la generación de etiquetas. Aprovecha las clases `Context` y `Link` de PrestaShop para determinar la página actual, los idiomas disponibles y generar URLs correctas.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la lógica se maneja dentro del archivo principal del módulo y sus métodos enganchados.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** define ninguna clase personalizada o `ObjectModel` en un directorio `classes/`. Toda la lógica principal está autocontenida dentro de la clase `myhreflang` en `index.php`.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo **no** incluye ningún archivo JavaScript personalizado. Su funcionalidad es puramente la generación de etiquetas HTML del lado del servidor.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo **no** incluye ningún archivo CSS personalizado. Su funcionalidad es puramente la generación de etiquetas HTML del lado del servidor y no tiene impacto visual.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza una única plantilla Smarty para renderizar las etiquetas `hreflang` y `canonical`.

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `myhreflang/views/templates/hook/hreflang.tpl`: Esta plantilla es responsable de generar las etiquetas reales `<link rel="alternate" hreflang="..." href="..." />` y `<link rel="canonical" href="..." />`.
        -   **Renderizado en el hook**: `displayHeader`
        -   **Propósito**: Recibe un array de `hreflang_links` y un `canonical_link` del método `hookDisplayHeader` del módulo. Luego itera a través de estos para generar las etiquetas HTML `<link>` necesarias.
        -   **Variables disponibles**:
            -   `$hreflang_links`: Un array de arrays asociativos, cada uno conteniendo `lang_code` (por ejemplo, 'en', 'en-US', 'x-default') y `url`.
            -   `$canonical_link`: Una cadena que contiene la URL canónica para la página actual.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    Este módulo **no** crea ninguna tabla SQL personalizada. Almacena sus configuraciones directamente en la tabla `ps_configuration` utilizando los métodos estándar `Configuration::get()` y `Configuration::updateValue()` de PrestaShop.

    -   Claves de configuración almacenadas en `ps_configuration`:
        -   `MYHREFLANG_HREFLANG_ENABLED` (booleano)
        -   `MYHREFLANG_CANONICAL_ENABLED` (booleano)
        -   `MYHREFLANG_XDEFAULT_ENABLED` (booleano)
        -   `MYHREFLANG_LANG_CODE_ONLY` (booleano)
-   **Tabla de Hooks registrados**:

    | Nombre del Hook | Momento de ejecución | Propósito técnico |
    | --- | --- | --- |
    | `displayHeader` | Se ejecuta en la sección `<head>` de cada página del front-office. | Este es el hook principal utilizado por el módulo. Llama al método `hookDisplayHeader()` para generar e inyectar las etiquetas `<link>` `hreflang` y `canonical` en el `<head>` HTML de la página. |

## 5. Soporte oficial y actualizaciones

Para soporte oficial, actualizaciones del módulo y cualquier otra asistencia con el módulo "Free hreflang & canonical urls", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier pregunta o problema técnico que pueda encontrar.

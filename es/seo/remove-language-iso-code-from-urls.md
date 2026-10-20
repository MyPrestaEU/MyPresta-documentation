---
title: "Eliminar el código ISO del idioma de las URLs - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Eliminar el código ISO del idioma de las URLs' de MyPresta.eu."
sidebar:
  label: "Eliminar el código ISO del idioma de las URLs - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Remove language ISO code from urls en MyPresta.eu](https://mypresta.eu/modules/seo/remove-language-iso-code-from-urls.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/seo/remove-language-iso-code-from-urls/)
>
> ---


# Eliminar el código ISO del idioma de las URLs

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor más allá de lo que PrestaShop requiere.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo "Eliminar el código ISO del idioma de las URLs" para acceder a sus ajustes.

La página de configuración de este módulo es intencionadamente simple, ya que su función principal es sencilla.

**Nombre de la pantalla:** Configuración de Eliminar el código ISO del idioma de las URLs
**Ubicación del menú:** Back Office > Módulos > Gestor de módulos > Eliminar el código ISO del idioma de las URLs > Configurar

En esta pantalla, normalmente encontrará un único ajuste crucial:

- **Nombre del ajuste:** Habilitar / Deshabilitar módulo
  - **Qué hace este ajuste:** Este es el interruptor maestro para la funcionalidad del módulo. Controla si el módulo elimina activamente el código ISO del idioma de las URLs de su idioma predeterminado o no.
  - **Efecto de cambiar este ajuste:**
    - **Cuando está habilitado (SÍ):** El módulo se activará. Para el idioma predeterminado de su tienda, el código ISO del idioma (por ejemplo, `/es/` si el español es el predeterminado) se eliminará de todas las URLs generadas. Las URLs para otros idiomas permanecerán sin cambios.
    - **Cuando está deshabilitado (NO):** El módulo estará inactivo. Todas las URLs, incluidas las de su idioma predeterminado, seguirán mostrando el código ISO del idioma (por ejemplo, `/es/`, `/fr/`).
  - **Valor recomendado:** **SÍ**. El propósito principal de instalar este módulo es utilizar su funcionalidad, por lo que habilitarlo es la recomendación estándar.
  - **Escenario / ejemplo de comerciante:**
    - Acaba de instalar el módulo y quiere que sus URLs en español (predeterminado) se vean como `www.sutienda.com/mi-producto`. Debería establecer esto en **SÍ**.
    - Si más tarde decide que prefiere que el código ISO del idioma esté presente en todas las URLs por alguna razón (por ejemplo, un cambio específico en la estrategia de SEO), podría establecer esto en **NO** para revertir el comportamiento sin desinstalar el módulo.

**Nota importante después de la configuración:**
Después de habilitar o deshabilitar el módulo, se recomienda encarecidamente:

1. **Borrar la caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la parte superior derecha.
2. **Regenerar su archivo `.htaccess`:** Vaya a **Parámetros de la tienda > Tráfico y SEO**, desplácese hasta la sección "Configurar URLs" y haga clic en "Guardar" (incluso si no cambia nada). Esto asegura que las reglas de reescritura de URL se actualicen correctamente.
3. **Pruebe sus URLs:** Navegue por su tienda en su idioma predeterminado y verifique que el código ISO del idioma se haya eliminado de las URLs. Además, pruebe otros idiomas para asegurarse de que sus URLs sigan conteniendo el código ISO.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar / Deshabilitar módulo | SÍ | Controla si el módulo elimina el código ISO del idioma de las URLs del idioma predeterminado. **SÍ** para URLs más limpias, **NO** para mantener los códigos ISO para todos los idiomas. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He habilitado el módulo, pero el código ISO del idioma sigue apareciendo en las URLs de mi idioma predeterminado. ¿Qué debo hacer?**
R: Esto suele ser un problema de caché o de que el archivo `.htaccess` no se ha regenerado.
1. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché".
2. Vaya a **Parámetros de la tienda > Tráfico y SEO**, desplácese hasta "Configurar URLs" y haga clic en "Guardar".
3. Revise también la caché de su navegador, o intente navegar en una ventana de incógnito/privada.

**P: ¿Este módulo afectará las URLs de mis idiomas no predeterminados?**
R: No, el módulo está diseñado específicamente para eliminar el código ISO del idioma solo para su idioma *predeterminado*. Todas las demás versiones de idioma seguirán mostrando sus respectivos códigos ISO (por ejemplo, `/fr/`, `/de/`).

**P: ¿Este módulo romperá mi SEO existente o creará errores 404 para URLs antiguas?**
R: El módulo funciona anulando la generación y el envío de URLs principales de PrestaShop. Debería manejar las redirecciones internamente. Sin embargo, para una máxima seguridad, especialmente en tiendas establecidas, siempre es una buena idea:
1. **Hacer una copia de seguridad de su base de datos y archivos** antes de la instalación.
2. **Probar a fondo** en un entorno de staging primero.
3. Después de habilitarlo, monitoree los registros de acceso de su servidor y Google Search Console para detectar cualquier error 404. Si encuentra alguno, es posible que deba agregar manualmente redirecciones 301 para URLs antiguas específicas a sus nuevas versiones más limpias en su archivo `.htaccess`, aunque esto rara vez es necesario con este módulo.

**P: Mi tema personalizado tiene algunos problemas después de instalar el módulo. ¿Qué podría estar mal?**
R: Este módulo afecta principalmente la generación y el enrutamiento de URLs, no la visualización. Es poco probable que cause directamente problemas de tema. Sin embargo, si su tema tiene estructuras de URL muy específicas y codificadas o se basa en JavaScript que analiza URLs de una manera inusual, existe una probabilidad muy pequeña de conflicto.
\* Primero, borre la caché de Smarty (**Parámetros avanzados > Rendimiento**).
\* Si el problema persiste, deshabilite temporalmente el módulo para ver si el problema desaparece. Si lo hace, póngase en contacto con el soporte de MyPresta.eu con los detalles del problema.

**P: ¿Este módulo es compatible con todos los idiomas instalados en PrestaShop?**
R: Sí, es compatible con todos los idiomas. Identifica su idioma *predeterminado* y elimina su código ISO, mientras deja intactos los códigos ISO para todos los demás idiomas instalados.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la implementación técnica del módulo "Eliminar el código ISO del idioma de las URLs", destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Visión general de la arquitectura

El módulo "Eliminar el código ISO del idioma de las URLs" logra su funcionalidad anulando las clases principales de PrestaShop responsables de la generación de URLs (`Link`) y el envío de URLs (`Dispatcher`). Esto le permite interceptar y modificar cómo PrestaShop construye e interpreta las URLs, específicamente apuntando a la eliminación del código ISO del idioma para el idioma predeterminado. Aprovecha el sistema de anulación de PrestaShop para inyectar su lógica personalizada sin modificar directamente los archivos principales.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front-office o back-office. Su lógica se implementa principalmente a través de anulaciones de clases.

### 4.3 Clases y modelos principales (`classes/`)

La funcionalidad principal del módulo reside en sus anulaciones de clases. Estos archivos se colocan en `removeiso/override/classes/` para asegurar que el sistema de anulación de PrestaShop los detecte.

- **`removeiso/override/classes/Dispatcher.php`**
  - **Nombre de la clase:** `Dispatcher` (anula la clase `Dispatcher` principal de PrestaShop)
  - **Clase padre:** `DispatcherCore`
  - **Responsabilidad:** Esta anulación es crucial para cómo PrestaShop *interpreta* las URLs entrantes. Modifica el método `dispatch()` (o un método relacionado) para enrutar correctamente las solicitudes que ya no contienen el código ISO del idioma predeterminado. Cuando llega una URL como `www.sutienda.com/mi-producto`, este `Dispatcher` anulado asegura que PrestaShop entienda que pertenece al idioma predeterminado, incluso sin el segmento `/es/`. También es probable que maneje la lógica para asegurar que si el ISO del idioma predeterminado *está* presente (por ejemplo, `www.sutienda.com/es/mi-producto`), se redirija a la URL más limpia.
- **`removeiso/override/classes/Link.php`**
  - **Nombre de la clase:** `Link` (anula la clase `Link` principal de PrestaShop)
  - **Clase padre:** `LinkCore`
  - **Responsabilidad:** Esta anulación es responsable de cómo PrestaShop *genera* las URLs salientes. Modifica métodos como `getLanguageLink()`, `getProductLink()`, `getCategoryLink()`, etc., para evitar la inclusión del código ISO del idioma cuando el idioma de destino es el idioma predeterminado de la tienda. Esto asegura que todos los enlaces generados por PrestaShop (por ejemplo, en plantillas, módulos) para el idioma predeterminado sean limpios.
- **`removeiso/override/classes/Tools.php`**
  - **Nombre de la clase:** `Tools` (anula la clase `Tools` principal de PrestaShop)
  - **Clase padre:** `ToolsCore`
  - **Responsabilidad:** La clase `Tools` contiene muchas funciones de utilidad. Esta anulación podría usarse para modificar cómo se manejan ciertos parámetros globales o cadenas relacionadas con URLs, posiblemente en conjunto con las anulaciones de `Dispatcher` y `Link` para asegurar la consistencia en varias tareas de manipulación de URLs. Podría, por ejemplo, afectar cómo se interpreta `$_SERVER['REQUEST_URI']` o cómo se comporta `Tools::redirect()` en escenarios específicos relacionados con códigos de idioma.
- **`removeiso/override/classes/index.php`**
  - **Nombre de la clase:** N/A (archivo vacío)
  - **Clase padre:** N/A
  - **Responsabilidad:** Esta es una práctica de seguridad estándar en los módulos de PrestaShop para evitar la lista de directorios si se accede directamente al archivo `index.php`. No contiene código ejecutable.

### 4.4 Activos de JavaScript (`views/js/`)

- **`removeiso/views/js/removeiso.js`**
  - **Alcance:** Back-office (probablemente cargado en la página de configuración del módulo).
  - **Responsabilidad:** Dada la función del módulo, este archivo JS es probablemente mínimo. Podría contener:
    - Simples escuchadores de eventos para el formulario de configuración (por ejemplo, un clic en el botón "Guardar").
    - Llamadas AJAX para guardar la configuración si el formulario utiliza el envío asíncrono.
    - Mejoras básicas de la interfaz de usuario o validación para el único interruptor "Habilitar/Deshabilitar".
    - No parece tener ninguna responsabilidad de front-office o lógica compleja del lado del cliente relacionada con la manipulación de URLs, ya que eso se maneja en el lado del servidor mediante las anulaciones de PHP.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo no incluye ningún archivo CSS personalizado. Esto indica que su interfaz de configuración se basa en el estilo predeterminado del Back Office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`removeiso/views/templates/admin/removeiso.tpl`**
  - **Alcance:** Plantilla de administración para la página de configuración del módulo.
  - **Responsabilidad:** Esta plantilla renderiza el formulario de configuración del módulo en el Back Office de PrestaShop. Contendrá la estructura HTML para el interruptor "Habilitar / Deshabilitar módulo" y los elementos de formulario estándar de PrestaShop (por ejemplo, botón `submit`, mensajes `alert`). Normalmente es renderizado por el método `getContent()` de la clase principal del módulo.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:
  - Este módulo no crea ninguna tabla de base de datos personalizada.
  - Sus ajustes de configuración (por ejemplo, el estado "Habilitar/Deshabilitar") se almacenan en la tabla `ps_configuration`, utilizando claves típicamente prefijadas con `REMOVEISO_` o similar (por ejemplo, `PS_REMOVEISO_ENABLED`).
- **Tabla de hooks registrados**:
  Este módulo no se registra explícitamente en muchos hooks estándar de PrestaShop para su funcionalidad principal, ya que su mecanismo principal es la anulación de clases. El método `install()` del módulo podría registrarse en `actionModuleInstall` o `actionModuleUninstall` para la limpieza, pero su comportamiento en tiempo de ejecución es impulsado por las clases anuladas.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Renderiza contenido en la sección `<head>` de las páginas del front-office. | Aunque no se utiliza directamente para su lógica de URL principal, un módulo podría engancharse aquí para cargar JS/CSS o realizar comprobaciones iniciales. (No utilizado directamente por este módulo para su función principal). |
| `displayRightColumn` / `displayLeftColumn` | Renderiza contenido en las columnas laterales. | (No utilizado directamente por este módulo). |
| `displayProduct` | Renderiza contenido en la página del producto. | (No utilizado directamente por este módulo). |
| `displayFooter` | Renderiza contenido en la sección del pie de página. | (No utilizado directamente por este módulo). |
| `actionDispatcherBefore` | Antes de que el despachador procese la solicitud. | La clase `Dispatcher` anulada maneja esto implícitamente, pero un módulo también podría usar este hook para la lógica previa al envío. |
| `actionDispatcherAfter` | Después de que el despachador haya procesado la solicitud. | (No utilizado directamente por este módulo). |
| `actionModuleInstall` | Se ejecuta cuando se instala el módulo. | Para realizar tareas de configuración como registrar anulaciones, añadir configuración a `ps_configuration`. |
| `actionModuleUninstall` | Se ejecuta cuando se desinstala el módulo. | Para realizar tareas de limpieza como eliminar anulaciones, borrar la configuración de `ps_configuration`. |

El núcleo del funcionamiento de este módulo son sus anulaciones de clases, que son cargadas automáticamente por el sistema de autocarga de PrestaShop cuando el módulo está habilitado, en lugar de depender de registros de hooks explícitos para su manipulación principal de URLs.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Eliminar el código ISO del idioma de las URLs", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema técnico o pregunta que pueda tener con respecto a la funcionalidad del módulo.
"""

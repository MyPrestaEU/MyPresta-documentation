---
title: "Directiva Ómnibus - Addon Gratuito - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Directiva Ómnibus - Addon Gratuito' de MyPresta.eu."
sidebar:
  label: "Directiva Ómnibus - Addon Gratuito - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Omnibus Directive - Free Addon en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/omnibus-directive-free-addon.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/omnibus-directive-free-addon/)
>
> ---


# Directiva Ómnibus - Addon Gratuito

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5 (El módulo está diseñado para ser compatible con una amplia gama de versiones de PHP, hasta las últimas versiones estables soportadas por PrestaShop 9.x)
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son típicamente requeridas por PrestaShop y son suficientes para este módulo. No se necesitan configuraciones especiales del servidor.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Para acceder a la configuración del módulo, navegue a **Módulos > Gestor de módulos**, busque "Directiva Ómnibus - Addon Gratuito" y haga clic en el botón "Configurar".

#### Ajustes Generales

- **Habilitar Cumplimiento de la Directiva Ómnibus:**

  - **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar la funcionalidad central del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* El módulo comenzará a rastrear los precios de los productos y mostrará el precio más bajo de los últimos 30 días en las páginas de producto cuando haya un descuento activo.
    - *Cuando está deshabilitado (NO):* El módulo dejará de rastrear precios y no mostrará ninguna información relacionada con la Directiva Ómnibus en su tienda.
  - **Valor recomendado:** SÍ (a menos que no venda a clientes de la UE o lo esté deshabilitando temporalmente por mantenimiento).
  - **Escenario / ejemplo de comerciante:** Acaba de instalar el módulo y quiere asegurarse de que su tienda cumpla con la normativa. Lo establecería en SÍ. Si está probando un nuevo tema y quiere ocultar temporalmente la visualización, podría establecerlo en NO.
- **Texto a Mostrar del Precio Más Bajo:**

  - **Qué hace este ajuste:** Le permite personalizar el texto que aparece antes del precio más bajo de los últimos 30 días.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se cambia:* El texto mostrado a los clientes reflejará su mensaje personalizado.
    - *Cuando se deja por defecto:* Se utilizará el texto por defecto (por ejemplo, "Precio más bajo en los últimos 30 días:").
  - **Valor recomendado:** "Precio más bajo en los últimos 30 días:" o similar, asegurando claridad para sus clientes.
  - **Escenario / ejemplo de comerciante:** Es posible que desee utilizar una frase ligeramente diferente como "Nuestro precio más bajo recientemente fue:" para que coincida con el tono de su marca.
- **Mostrar en la Página del Producto (Selección de Hook):**

  - **Qué hace este ajuste:** Este ajuste crucial determina *dónde* en la página de su producto se mostrará la información del precio más bajo de los últimos 30 días. El módulo proporciona opciones predefinidas para estructuras de temas comunes (Classic, Hummingbird) y una opción de hook personalizado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se selecciona "Perfil de Tema Classic":* El módulo intentará inyectar el historial de precios en una ubicación adecuada dentro de la estructura estándar del tema Classic (por ejemplo, `displayProductPriceBlock` o `displayProductButtons`).
    - *Cuando se selecciona "Perfil de Tema Hummingbird":* El módulo intentará inyectar el historial de precios en una ubicación adecuada dentro de la estructura estándar del tema Hummingbird.
    - *Cuando se selecciona "Hook Personalizado":* Deberá especificar manualmente un hook de PrestaShop donde el módulo debe mostrar su contenido. Esto requiere algunos conocimientos técnicos o la modificación del tema.
  - **Valor recomendado:** Comience con "Perfil de Tema Classic" o "Perfil de Tema Hummingbird" según su tema activo. Si la visualización no es satisfactoria, consulte a un webmaster para la integración de "Hook Personalizado".
  - **Escenario / ejemplo de comerciante:** Si su tienda utiliza el tema Classic predeterminado de PrestaShop, elija "Perfil de Tema Classic". Si ha actualizado a PrestaShop 8.x y utiliza el tema Hummingbird, seleccione "Perfil de Tema Hummingbird". Si tiene un tema altamente personalizado, es posible que deba usar "Hook Personalizado" y pedirle a su desarrollador que agregue `{hook h='displayMyCustomOmnibusHook'}` a la plantilla de su página de producto.
- **Nombre del Hook Personalizado (si se seleccionó "Hook Personalizado" arriba):**

  - **Qué hace este ajuste:** Si eligió "Hook Personalizado" en el ajuste anterior, este campo le permite especificar el nombre exacto del hook donde el módulo debe renderizar su contenido.
  - **Efecto de cambiar este ajuste:** El módulo solo mostrará su contenido si un hook con este nombre exacto está presente en la plantilla de la página de producto de su tema.
  - **Valor recomendado:** Déjelo vacío a menos que haya seleccionado "Hook Personalizado" arriba y conozca el nombre exacto del hook. Ejemplo: `displayProductExtraContent`.
  - **Escenario / ejemplo de comerciante:** Su webmaster ha modificado la plantilla de su página de producto (`product.tpl`) para incluir `{hook h='displayMyCustomOmnibusHook'}`. Entonces, introduciría `displayMyCustomOmnibusHook` en este campo.

#### Gestión de Datos

- **Borrar Datos de la Directiva Ómnibus:**
  - **Qué hace este ajuste:** Este botón le permite eliminar todos los datos de historial de precios registrados previamente por el módulo.
  - **Efecto de cambiar este ajuste:** Al hacer clic en este botón, se eliminarán permanentemente todos los registros de precios históricos. El módulo comenzará a recopilar datos de nuevo desde el momento en que los productos sean vistos o actualizados.
  - **Valor recomendado:** Úselo con precaución. Solo borre los datos si necesita restablecer el historial de precios, por ejemplo, después de una revisión importante del catálogo de productos o si sospecha que hay corrupción de datos.
  - **Escenario / ejemplo de comerciante:** Ha importado un conjunto completamente nuevo de productos con diferentes estrategias de precios y desea asegurarse de que los datos de la Directiva Ómnibus comiencen de nuevo sin precios heredados. Haría clic en este botón.

#### 2.1.1 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Habilitar Cumplimiento de la Directiva Ómnibus | SÍ | Activa/desactiva el seguimiento y la visualización de precios para el cumplimiento de la UE. |
| Configuración del Módulo | Texto a Mostrar del Precio Más Bajo | "Precio más bajo en los últimos 30 días:" | Personaliza el texto que se muestra antes del precio histórico. |
| Configuración del Módulo | Mostrar en la Página del Producto (Selección de Hook) | Perfil Classic/Hummingbird (según el tema) | Determina dónde aparece el historial de precios en la página del producto. |
| Configuración del Módulo | Nombre del Hook Personalizado | (Vacío) | Especifica un hook personalizado para la visualización si se selecciona "Hook Personalizado". |
| Configuración del Módulo | Borrar Datos de la Directiva Ómnibus | (Botón) | Elimina todo el historial de precios almacenado, forzando un nuevo comienzo. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: La información del precio más bajo no aparece en las páginas de mis productos.**
R:

1. **Verifique "Habilitar Cumplimiento de la Directiva Ómnibus":** Asegúrese de que esté configurado en SÍ en la configuración del módulo.
2. **Verifique "Mostrar en la Página del Producto (Selección de Hook)":** Intente cambiar entre "Perfil de Tema Classic" y "Perfil de Tema Hummingbird" si no está seguro de cuál coincide mejor con su tema.
3. **Borrar Caché:** Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los cambios de tema o las actualizaciones de módulos requieren una actualización de la caché.
4. **Verifique los Descuentos:** La información solo aparece cuando un producto está realmente descontado. Asegúrese de que el producto que está probando tenga un precio específico activo o una regla de precio de catálogo aplicada.
5. **Tema Personalizado:** Si está utilizando un tema muy personalizado, es posible que el módulo no pueda inyectar el contenido automáticamente. Probablemente necesitará usar la opción "Hook Personalizado" y hacer que su webmaster lo integre en el archivo `product.tpl` de su tema.

**P: El precio más bajo mostrado parece incorrecto o demasiado alto/bajo.**
R:

1. **Tiempo de Recopilación de Datos:** El módulo necesita tiempo para recopilar datos. Si acaba de instalarlo, solo comenzará a rastrear los precios a partir de ese momento. Tardará 30 días en tener un historial completo de 30 días.
2. **Borrar Datos de la Directiva Ómnibus:** Si sospecha que se están utilizando datos antiguos e incorrectos, puede hacer clic en el botón "Borrar Datos de la Directiva Ómnibus" en la configuración del módulo. Tenga en cuenta que esto eliminará todo el historial y el módulo comenzará a recopilar datos desde cero.
3. **Combinaciones de Productos/Monedas:** Asegúrese de que está viendo la combinación y moneda correctas. El módulo rastrea los precios por combinación y moneda.

**P: ¿Este módulo ralentizará mi tienda?**
R: El módulo está diseñado para ser ligero. El seguimiento de precios ocurre en segundo plano o durante las vistas de productos, y la visualización en el front office es una salida de texto simple. Cualquier impacto en el rendimiento debería ser insignificante.

**P: ¿Cómo maneja este módulo las tiendas multilingües?**
R: El ajuste "Texto a Mostrar del Precio Más Bajo" es traducible. Puede ir a **Internacional > Traducciones**, seleccionar "Traducciones de módulos instalados", elegir su tema y luego seleccionar el módulo "Directiva Ómnibus - Addon Gratuito" para traducir el texto a todos sus idiomas activos.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo "Directiva Ómnibus - Addon Gratuito" sigue una arquitectura de módulo estándar de PrestaShop. Su funcionalidad principal reside dentro del archivo principal `index.php`, que actúa como punto de entrada del módulo y maneja la instalación, desinstalación, configuración y registro de hooks. El historial de precios se gestiona observando los cambios de precio de los productos y almacenándolos, probablemente en una tabla personalizada o en `ps_configuration` (aunque el dossier indica que no hay SQL personalizado, lo que implica `ps_configuration` o generación dinámica de datos). La visualización en el front-office se logra mediante la conexión a puntos de visualización estándar de PrestaShop, con lógica específica para los temas Classic y Hummingbird.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno definido explícitamente en el dossier. La lógica del front-office probablemente se maneja directamente dentro de los métodos de hook del archivo principal del módulo.
- **Controladores de Administración del Back-Office**: Ninguno definido explícitamente en el dossier. Toda la configuración del back-office se maneja a través del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

- Ninguno definido explícitamente en el dossier. La lógica del módulo, incluido el seguimiento y almacenamiento de precios, probablemente está encapsulada dentro de la clase `Omnifree` en `index.php`.
  - **Clase `Omnifree` (en `omnifree/index.php`)**:
    - Extiende `Module`.
    - Maneja la instalación (`install()`) y desinstalación (`uninstall()`) del módulo.
    - Registra los hooks necesarios (por ejemplo, `displayHeader`, `displayProductPriceBlock`, `displayProductButtons`, `displayFooter`, `actionProductUpdate`, `actionProductSave`).
    - Gestiona la configuración a través de `getContent()`.
    - Contiene métodos para el seguimiento y la recuperación de precios, probablemente interactuando con `ps_configuration` para almacenar precios históricos o calculándolos dinámicamente basándose en el historial de pedidos.
    - Implementa métodos de hook (`hookDisplayHeader`, `hookDisplayProductPriceBlock`, `hookDisplayProductButtons`, `hookDisplayFooter`, etc.) para inyectar contenido en el front office.
    - Implementa hooks de acción (`hookActionProductUpdate`, `hookActionProductSave`) para registrar cambios de precio.

### 4.4 Activos JavaScript (`views/js/`)

- **`omnifree/views/js/admin-config.js`**:
  - **Alcance:** Back-office.
  - **Propósito:** Este script probablemente maneja el comportamiento dinámico de la página de configuración del módulo. Esto podría incluir:
    - Mostrar/ocultar el campo de entrada "Nombre del Hook Personalizado" según el valor del desplegable "Mostrar en la Página del Producto (Selección de Hook)".
    - Llamadas AJAX para el botón "Borrar Datos de la Directiva Ómnibus" para realizar la limpieza de datos sin una recarga completa de la página.
    - Validación de entrada u otros elementos interactivos en el formulario de configuración.
  - **Detectores de eventos:** Probablemente escucha eventos `change` en los desplegables y eventos `click` en los botones dentro del formulario de configuración del módulo.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- **`omnifree/views/css/admin-config.css`**:
  - **Alcance:** Estilo del formulario de administración del back-office.
  - **Propósito:** Proporciona estilos específicos para los elementos dentro de la página de configuración del módulo en el back office de PrestaShop, asegurando una interfaz de administración consistente y fácil de usar.
  - **Selectores de clase CSS clave:** Probablemente apunta a IDs o clases específicas dentro de la plantilla `configure.tpl`.
- **`omnifree/views/css/omnibus-classic.css`**:
  - **Alcance:** Estilo del cliente del front-office (específicamente para el tema Classic).
  - **Propósito:** Contiene reglas CSS para asegurar que la información del precio más bajo mostrada tenga el estilo y la posición correctos dentro del tema Classic de PrestaShop, evitando conflictos y manteniendo la armonía visual.
  - **Selectores de clase CSS clave:** Apunta a elementos como `.product-prices`, `.product-information` o clases personalizadas añadidas por el módulo para la visualización del historial de precios.
- **`omnifree/views/css/omnibus-hummingbird.css`**:
  - **Alcance:** Estilo del cliente del front-office (específicamente para el tema Hummingbird).
  - **Propósito:** Proporciona ajustes de estilo y posicionamiento específicos para la información del precio más bajo cuando el tema Hummingbird (predeterminado de PrestaShop 8.x) está activo.
  - **Selectores de clase CSS clave:** Apunta a elementos específicos de la estructura de la página de producto del tema Hummingbird.
- **`omnifree/views/css/omnibus.css`**:
  - **Alcance:** Estilo del cliente del front-office (general).
  - **Propósito:** Contiene reglas CSS generales, agnósticas al tema, para la visualización del precio más bajo. Esto podría incluir estilos básicos de fuente, color o margen que se aplican independientemente del perfil de tema específico elegido.
  - **Selectores de clase CSS clave:** Clases genéricas utilizadas en `omnibus.tpl`.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de Hook (`views/templates/hook/`)**:
  - **`omnifree/views/templates/hook/omnibus.tpl`**:
    - **Propósito:** Esta es la plantilla principal del front-office responsable de renderizar la información del precio más bajo de los últimos 30 días. Será renderizada por los métodos de hook del módulo (por ejemplo, `hookDisplayProductPriceBlock`, `hookDisplayProductButtons` o un hook personalizado).
    - **Variables:** Probablemente espera variables como `$lowest_price_30_days`, `$currency_symbol`, `$display_text` y potencialmente `$product_id` o `$id_product_attribute`.
    - **Salida:** Un pequeño fragmento HTML que contiene el texto configurado y el precio más bajo formateado.
- **Plantillas de Administración (`views/templates/admin/`)**:
  - **`omnifree/views/templates/admin/configure.tpl`**:
    - **Propósito:** Esta plantilla renderiza el formulario de configuración principal para el módulo en el back office de PrestaShop. Incluye todos los ajustes descritos en la Sección 4.1.
    - **Variables:** Recibe valores de configuración de `getContent()` para prellenar los campos del formulario.
    - **Estructura:** Utiliza la estructura de formulario de ayuda de PrestaShop (por ejemplo, `AdminForm`) para crear los campos de entrada, interruptores y botones.
  - **`omnifree/views/templates/admin/pro-teaser.tpl`**:
    - **Propósito:** Esta plantilla probablemente muestra contenido promocional o un "teaser" para una versión "Pro" o de pago del módulo Directiva Ómnibus de MyPresta.eu. Podría destacar características adicionales disponibles en la versión premium.
    - **Ubicación:** Probablemente incluida dentro de `configure.tpl` o mostrada como un bloque separado en la página de configuración.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:
  - El dossier indica que no hay archivos SQL personalizados. Esto sugiere que los datos del historial de precios son:
    1. Almacenados directamente en `ps_configuration` como arrays serializados (menos eficiente para grandes conjuntos de datos).
    2. Calculados dinámicamente basándose en las tablas `ps_order_detail` y `ps_product_attribute_combination` (más complejo, pero evita tablas personalizadas).
    3. Una tabla personalizada se crea programáticamente dentro de `install()` sin un archivo SQL separado. Dada la naturaleza de "Addon Gratuito", la opción 1 o 2 es más probable por simplicidad.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Alcance | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | En cada carga de página en la sección `<head>`. | Para cargar los activos CSS/JS del módulo (por ejemplo, `omnibus.css`, `omnibus-classic.css`, `omnibus-hummingbird.css`). |
| `displayProductPriceBlock` | Front-Office | En las páginas de producto, típicamente cerca del precio. | Uno de los hooks principales para mostrar la información del precio más bajo en el tema Classic. |
| `displayProductButtons` | Front-Office | En las páginas de producto, típicamente cerca del botón de añadir al carrito. | Otro hook potencial para mostrar la información del precio más bajo en el tema Classic. |
| `displayFooter` | Front-Office | En la parte inferior de cada página. | Menos probable para la visualización de precios, pero podría usarse para mensajes generales de cumplimiento o si se coloca un hook personalizado aquí. |
| `actionProductUpdate` | Back-Office | Cuando un producto se actualiza/guarda en el back office. | Para activar el mecanismo de seguimiento de precios y registrar el precio actual del producto para el historial. |
| `actionProductSave` | Back-Office | Cuando un producto se guarda (nuevo o existente) en el back office. | Similar a `actionProductUpdate`, asegura que los cambios de precio sean capturados. |
| `actionFrontControllerSetMedia` | Front-Office | Antes de que un controlador frontal renderice su salida. | Para cargar condicionalmente CSS/JS específico según la página o el tema actual. |
| (Nombre del Hook Personalizado) | Front-Office | Donde el comerciante coloca `{hook h='CustomHookName'}` en su plantilla. | Permite una colocación flexible de la visualización del precio más bajo para temas altamente personalizados. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Directiva Ómnibus - Addon Gratuito", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.

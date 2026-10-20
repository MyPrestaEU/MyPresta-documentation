---
title: "Barra de progreso de envío gratuito - Manual del comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Barra de progreso de envío gratuito' de MyPresta.eu."
sidebar:
  label: "Barra de progreso de envío gratuito - Manual del comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Free Shipping Progress Bar for free en MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-shipping-progress-bar-for-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/free-shipping-progress-bar-for-free/)
>
> ---


# Barra de progreso de envío gratuito

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Barra de progreso de envío gratuito". Puede acceder a ella navegando a **Módulos > Gestor de módulos** y haciendo clic en "Configurar" junto al nombre del módulo.

#### Ajustes generales

- **Activar barra de progreso de envío gratuito:**

  - **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar toda la funcionalidad de la barra de progreso para su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado (SÍ):* La barra de progreso aparecerá en las posiciones seleccionadas en su front office, y todos los demás ajustes del módulo surtirán efecto.
    - *Cuando está desactivado (NO):* La barra de progreso estará completamente oculta de su tienda, independientemente de otros ajustes.
  - **Valor recomendado:** SÍ (para utilizar las características del módulo).
  - **Escenario / ejemplo del comerciante:** Si está ejecutando temporalmente una promoción diferente o realizando mantenimiento, podría desactivarlo. De lo contrario, manténgalo activado para fomentar las ventas.
- **Umbral de envío gratuito:**

  - **Qué hace este ajuste:** Esto define la cantidad exacta (en la moneda predeterminada de su tienda) que un cliente necesita gastar para calificar para el envío gratuito.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en una cantidad específica (por ejemplo, 50.00):* La barra de progreso calculará la cantidad restante en función de este umbral.
    - *Cuando se cambia:* El objetivo de envío gratuito se actualiza instantáneamente para todos los clientes.
  - **Valor recomendado:** Establezca esto en el umbral de envío gratuito real de su tienda. Si ofrece envío gratuito a partir de 50 €, configúrelo en 50.00.
  - **Escenario / ejemplo del comerciante:** Si su transportista ofrece envío gratuito para pedidos superiores a 75 €, lo establecería en 75.00.
- **Gancho de visualización:**

  - **Qué hace este ajuste:** Esto determina dónde se mostrará la barra de progreso de envío gratuito en su sitio web. Puede elegir entre varias ubicaciones comunes.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 'displayHeader':* La barra aparecerá en la sección superior de su sitio web, generalmente encima o debajo de su logotipo/menú.
    - *Cuando se establece en 'displayLeftColumn' o 'displayRightColumn':* La barra aparecerá en la columna lateral respectiva de su tienda.
    - *Cuando se establece en 'displayFooter':* La barra aparecerá en la parte inferior de su sitio web.
    - *Cuando se establece en 'displayProductButtons' (o un gancho similar de página de producto):* La barra aparecerá en las páginas de productos, a menudo cerca del botón de añadir al carrito.
  - **Valor recomendado:** 'displayHeader' o 'displayProductButtons' suelen ser los más efectivos para la visibilidad y para fomentar la acción inmediata.
  - **Escenario / ejemplo del comerciante:** Para asegurar la máxima visibilidad, podría elegir `displayHeader`. Si desea fomentar la adición de más artículos directamente desde la página del producto, `displayProductButtons` es una buena opción.
- **Color de la barra de progreso:**

  - **Qué hace este ajuste:** Le permite personalizar el color de la propia barra de progreso. Esto le ayuda a que coincida con la marca de su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en un color específico (por ejemplo, #4CAF50 para verde):* La barra se mostrará en ese color.
  - **Valor recomendado:** Un color que contraste bien con su fondo pero que complemente la paleta de colores de su marca.
  - **Escenario / ejemplo del comerciante:** Si su marca utiliza mucho azul, podría elegir un tono de azul o un naranja complementario para que la barra destaque.
- **Color de fondo:**

  - **Qué hace este ajuste:** Le permite personalizar el color de fondo del contenedor de la barra de progreso.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en un color específico (por ejemplo, #F0F0F0 para gris claro):* El fondo detrás del progreso se mostrará en ese color.
  - **Valor recomendado:** Un color sutil que proporcione un buen contraste con el color de la barra de progreso, a menudo un gris claro o blanco.
  - **Escenario / ejemplo del comerciante:** Para que la barra de progreso destaque, podría usar un color de fondo claro como blanco o un gris muy claro.
- **Color del texto:**

  - **Qué hace este ajuste:** Le permite personalizar el color del texto que se muestra dentro o alrededor de la barra de progreso (por ejemplo, "¡Le quedan X para el envío gratuito!").
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en un color específico (por ejemplo, #333333 para gris oscuro):* El texto se mostrará en ese color.
  - **Valor recomendado:** Un color que sea fácilmente legible tanto en la barra de progreso como en su fondo.
  - **Escenario / ejemplo del comerciante:** Si su barra de progreso es verde y su fondo es gris claro, un color de texto gris oscuro o negro aseguraría la legibilidad.

#### Avance de la edición Pro

Esta sección suele contener información y enlaces para actualizar a la versión "Pro" del módulo, que ofrece funciones más avanzadas. Estos no son ajustes de configuración para el módulo gratuito, sino contenido promocional.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Activar barra de progreso de envío gratuito | SÍ | Interruptor maestro para la funcionalidad del módulo. |
| Configuración del módulo | Umbral de envío gratuito | Cantidad de envío gratuito de su tienda | Define la cantidad objetivo para el envío gratuito. |
| Configuración del módulo | Gancho de visualización | displayHeader / displayProductButtons | Determina dónde aparece la barra en su tienda. |
| Configuración del módulo | Color de la barra de progreso | Personalizable (por ejemplo, #4CAF50) | Establece el color de la parte rellena de la barra de progreso. |
| Configuración del módulo | Color de fondo | Personalizable (por ejemplo, #F0F0F0) | Establece el color de fondo del contenedor de la barra de progreso. |
| Configuración del módulo | Color del texto | Personalizable (por ejemplo, #333333) | Establece el color del texto que se muestra con la barra. |

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: La barra de progreso no aparece en mi tienda. ¿Qué debo hacer?**
R1:

- **Verificar el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Barra de progreso de envío gratuito" esté instalado y activado.
- **Verificar la configuración:** Navegue a la página de configuración del módulo. Asegúrese de que "Activar barra de progreso de envío gratuito" esté configurado en SÍ. Además, verifique que la configuración de "Gancho de visualización" esté correctamente elegida y que su tema realmente renderice ese gancho (algunos temas personalizados podrían no hacerlo).
- **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty"). A veces, la caché antigua impide que aparezca el nuevo contenido del módulo.
- **Compatibilidad del tema:** Aunque el módulo está diseñado para temas estándar de PrestaShop (Classic, Hummingbird), los temas altamente personalizados podrían requerir pequeños ajustes. Si los pasos anteriores no funcionan, póngase en contacto con el soporte de MyPresta.eu.

**P2: La barra de progreso se muestra, pero no se actualiza cuando añado artículos al carrito.**
R2:

- **Verificar JavaScript:** Asegúrese de que no haya errores de JavaScript en su sitio que puedan estar impidiendo la ejecución del script del módulo. Puede verificar la consola de desarrollador de su navegador (generalmente F12) en busca de errores.
- **Carrito AJAX:** El módulo se basa en la funcionalidad de carrito AJAX de PrestaShop. Asegúrese de que el mecanismo de actualización del carrito de su tema sea estándar y no esté anulando las llamadas AJAX principales de PrestaShop de una manera que impida que el módulo detecte cambios.
- **Conflictos de módulos:** Desactive temporalmente otros módulos que modifiquen el comportamiento del carrito o muestren elementos en los mismos ganchos para verificar si hay conflictos.

**P3: ¿Cómo cambio el texto que se muestra en la barra de progreso (por ejemplo, "¡Le quedan X para el envío gratuito!")?**
R3: La versión gratuita del módulo suele utilizar texto predefinido. Para personalizar este texto, normalmente necesitaría editar el archivo de plantilla del módulo (`progress.tpl`). Sin embargo, esto requiere conocimientos básicos de las plantillas Smarty. Para una forma más fácil de personalizar el texto, la versión Pro del módulo a menudo incluye campos de texto dedicados en el back office.

**P4: La barra de progreso se ve extraña o no coincide con el estilo de mi tema.**
R4:

- **Colores de configuración del módulo:** Primero, use los ajustes "Color de la barra de progreso", "Color de fondo" y "Color del texto" en la configuración del módulo para intentar que coincida con su tema.
- **Conflictos de CSS:** El CSS de su tema podría estar anulando los estilos predeterminados del módulo. Un webmaster puede inspeccionar el elemento usando las herramientas de desarrollador del navegador para identificar las reglas CSS en conflicto y añadir CSS personalizado a su tema para anularlas. Los archivos CSS del módulo (`front.css`) pueden ser un buen punto de partida para identificar los selectores a los que apuntar.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Barra de progreso de envío gratuito" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para la instalación, desinstalación y configuración. Utiliza controladores frontales para interacciones AJAX para actualizar dinámicamente la barra de progreso sin recargas completas de la página. El módulo se integra con el sistema de ganchos de PrestaShop para mostrar su contenido en varias ubicaciones del front-office y utiliza plantillas Smarty para renderizar su interfaz de usuario. La configuración se almacena en la tabla `ps_configuration`.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `controllers/front/index.php`
    - **Nombre de la clase y clase padre:** `SmartFreeShippingFreeIndexModuleFrontController` extiende `ModuleFrontController`.
    - **Responsabilidad:** Este controlador probablemente sirve como base o punto de entrada para las interacciones del front-office, aunque sus métodos específicos podrían ser mínimos si `refresh.php` maneja el AJAX principal. Podría usarse para la carga inicial de datos o para configurar el contexto.
  - `controllers/front/refresh.php`
    - **Nombre de la clase y clase padre:** `SmartFreeShippingFreeRefreshModuleFrontController` extiende `ModuleFrontController`.
    - **Responsabilidad:** Este es el controlador AJAX principal. Responde a las solicitudes (probablemente POST o GET) del JavaScript del front-office para obtener el total actual del carrito, calcular la cantidad restante para el envío gratuito y devolver el HTML o los datos actualizados de la barra de progreso. Maneja la conversión de moneda y asegura que la barra de progreso refleje los cambios del carrito en tiempo real.
- **Controladores de administración de Back-Office**:

  - Ninguno. Toda la configuración se maneja dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

- Ninguno. El módulo no define clases `ObjectModel` personalizadas ni clases de lógica de negocio complejas más allá de lo que se contiene en el archivo principal del módulo (`index.php`) y los controladores frontales.

### 4.4 Activos JavaScript (`views/js/`)

- `views/js/front.js`
  - **Alcance:** Front-office.
  - **Detalles:** Este script es responsable del comportamiento dinámico de la barra de progreso.
    - Probablemente vincula oyentes de eventos a los eventos de actualización del carrito (por ejemplo, `prestashop.on('updateCart', ...)` o eventos personalizados activados por el carrito AJAX del tema).
    - Cuando se detecta una actualización del carrito, realiza una llamada AJAX al controlador frontal `refresh.php` para obtener el estado actualizado de la barra de progreso.
    - Luego actualiza el DOM para reflejar el nuevo progreso (por ejemplo, el ancho de la barra de progreso, el texto de la cantidad restante).
    - Puede incluir lógica para la representación inicial al cargar la página y para manejar diferentes ganchos de visualización.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `views/css/admin-config.css`

  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Detalles:** Contiene estilos específicamente para la página de configuración del módulo en el back office de PrestaShop, asegurando un diseño limpio y fácil de usar para los ajustes.
  - **Selectores de clase CSS clave:** Probablemente apunta a elementos dentro del formulario de configuración del módulo, como `.panel`, `.form-group`, `.control-label`, etc., específicos de la estructura HTML del módulo.
- `views/css/admin-pro-teaser.css`

  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Detalles:** Estilos para el contenido promocional relacionado con la versión "Pro" del módulo, asegurando que se vea atractivo y distinto dentro de la página de configuración.
  - **Selectores de clase CSS clave:** Apunta a elementos como `.pro-teaser-block`, `.pro-feature-list`, etc.
- `views/css/front.css`

  - **Alcance:** Estilo del cliente del Front-office.
  - **Detalles:** Contiene el CSS principal para la propia barra de progreso de envío gratuito, incluyendo su diseño, colores, animaciones y capacidad de respuesta.
  - **Selectores de clase CSS clave:** Apunta a elementos como `#smartfreeshippingfree-progress-bar-container`, `.progress-bar-fill`, `.progress-bar-text`, etc. Los desarrolladores pueden anular estas clases en el `custom.css` o `theme.css` de su tema para que coincidan con su diseño específico.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:

  - `views/templates/admin/configure.tpl`
    - **Propósito:** Esta es la plantilla Smarty principal para la página de configuración del módulo en el Back Office. Renderiza los campos del formulario, los interruptores y los elementos de entrada para todos los ajustes del módulo. Probablemente incluye `get-pro-hero.tpl` y `get-pro.tpl` para contenido promocional.
  - `views/templates/admin/get-pro-hero.tpl`
    - **Propósito:** Renderiza una sección "hero" prominente que promociona la versión Pro del módulo, a menudo en la parte superior de la página de configuración.
  - `views/templates/admin/get-pro.tpl`
    - **Propósito:** Renderiza una sección detallada que describe las características y beneficios de actualizar a la versión Pro, que normalmente incluye una llamada a la acción.
- **Plantillas de gancho (`views/templates/hook/`)**:

  - `views/templates/hook/progress.tpl`
    - **Propósito:** Esta es la plantilla principal del front-office. Renderiza la estructura HTML de la barra de progreso de envío gratuito, incluyendo el contenedor, la sección de progreso rellena y el texto dinámico (por ejemplo, "¡Le quedan X para el envío gratuito!"). Esta plantilla es renderizada por el método `displayHook` del archivo principal del módulo.
- **Plantillas de Front-office (`views/templates/front/`)**:

  - Ninguno. La visualización del front-office se gestiona a través de `hook/progress.tpl`.

### 4.7 Esquema de la base de datos y mapa de ganchos

- **Tablas de la base de datos**:

  - El módulo no crea tablas SQL personalizadas. Todos los ajustes de configuración se almacenan en la tabla estándar `ps_configuration` de PrestaShop, utilizando claves con el prefijo `SMARTFREESHIPPINGFREE_` (por ejemplo, `SMARTFREESHIPPINGFREE_ENABLED`, `SMARTFREESHIPPINGFREE_THRESHOLD`).
- **Tabla de ganchos registrados**:

| Nombre del gancho | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página, o en la parte superior del `<body>`. | Se utiliza para inyectar activos CSS/JS y potencialmente renderizar la barra de progreso en la cabecera. |
| `displayLeftColumn` | En la columna izquierda del tema. | Posición alternativa para mostrar la barra de progreso. |
| `displayRightColumn` | En la columna derecha del tema. | Posición alternativa para mostrar la barra de progreso. |
| `displayFooter` | En la sección del pie de página del tema. | Posición alternativa, menos intrusiva, para mostrar la barra de progreso. |
| `displayProductButtons` (o similar) | En la página del producto, a menudo cerca del botón de añadir al carrito. | Ubicación específica para fomentar la adición de artículos directamente desde las páginas de productos. |
| `actionCartSave` | Después de guardar un carrito (por ejemplo, artículo añadido/eliminado). | Gancho interno (no para visualización) utilizado por el módulo para activar actualizaciones AJAX para la barra de progreso. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su salida, para añadir CSS/JS. | Se utiliza para registrar `front.js` y `front.css` para las páginas del front-office. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Barra de progreso de envío gratuito", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta que pueda tener.

---
title: "Free PopUp - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Free PopUp para PrestaShop de MyPresta.eu."
sidebar:
  label: "Free PopUp - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Free PopUp en MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-popup.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/free-popup/)
>
> ---


# Free PopUp

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo Free PopUp. Aquí encontrarás todos los ajustes para controlar el contenido y el comportamiento de tu popup.

#### **1. Habilitar / Deshabilitar Popup**

- **Qué hace este ajuste:** Este es el interruptor principal para tu popup.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El popup aparecerá en tu front office según tus otros ajustes.
  - *Cuando está deshabilitado (NO):* El popup no aparecerá en tu front office, independientemente de otros ajustes.
- **Valor recomendado:** SÍ (cuando quieras que el popup esté activo), NO (cuando quieras ocultarlo temporalmente).
- **Escenario / ejemplo de comerciante:** Habilítalo cuando tengas una nueva promoción en curso. Desactívalo durante el mantenimiento o si quieres ejecutar una campaña diferente temporalmente.

#### **2. Contenido del Popup**

- **Qué hace este ajuste:** Aquí es donde introduces el mensaje, la oferta o la información real que quieres mostrar dentro del popup. Utiliza un editor de texto enriquecido (TinyMCE), lo que te permite formatear texto, añadir imágenes, enlaces y más.
- **Efecto de cambiar este ajuste:** Lo que escribas y formatees aquí se mostrará directamente a tus clientes en la ventana del popup.
- **Valor recomendado:** Tu mensaje promocional específico, texto de bienvenida o anuncio importante.
- **Escenario / ejemplo de comerciante:** "¡Bienvenido a nuestra tienda! ¡Usa el código BIENVENIDO10 para un 10% de descuento en tu primer pedido!" o "¡Envío gratis en todos los pedidos superiores a 50€ esta semana!" También puedes añadir una imagen de un nuevo producto o un logotipo de marca.

#### **3. Caducidad de la Cookie (Días)**

- **Qué hace este ajuste:** Esto determina cuánto tiempo permanece oculto el popup después de que un cliente lo cierra. Establece una cookie en el navegador del cliente.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en 0:* El popup aparecerá en *cada* carga de página, incluso si el cliente acaba de cerrarlo. Esto generalmente no se recomienda, ya que puede ser molesto.
  - *Cuando se establece en un número positivo (por ejemplo, 7):* El popup aparecerá en la primera visita. Una vez cerrado, no volverá a aparecer durante los próximos 7 días para ese cliente específico en ese navegador específico.
- **Valor recomendado:** 7 (para promociones semanales), 30 (para mensajes de bienvenida mensuales) o 1 (si quieres que reaparezca diariamente).
- **Escenario / ejemplo de comerciante:** Si tienes un mensaje de bienvenida general, establecerlo en 30 días es bueno. Si estás ejecutando una venta semanal, 7 días asegura que los clientes vean la nueva oferta la próxima semana.

#### **4. Modo de Prueba**

- **Qué hace este ajuste:** Esto te permite probar la apariencia y el contenido de tu popup sin esperar a que expire la cookie.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El popup aparecerá en cada actualización de página, incluso si acabas de cerrarlo. Esto anula el ajuste de "Caducidad de la Cookie" para fines de prueba.
  - *Cuando está deshabilitado (NO):* El popup se comportará normalmente, respetando el ajuste de "Caducidad de la Cookie".
- **Valor recomendado:** SÍ (mientras estás configurando y ajustando el popup), NO (una vez que estés satisfecho con la configuración y quieras que funcione normalmente para los clientes).
- **Escenario / ejemplo de comerciante:** Acabas de actualizar el contenido de tu popup y quieres ver cómo se ve en el front office inmediatamente. Habilita el Modo de Prueba, actualiza la página de tu tienda y el popup aparecerá. Una vez que estés satisfecho, desactiva el Modo de Prueba.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | Habilitar / Deshabilitar Popup | SÍ | Interruptor principal para mostrar u ocultar el popup en tu tienda. |
| Página de Configuración del Módulo | Contenido del Popup | Tu mensaje | El texto, imágenes y enlaces reales que se muestran dentro del popup. |
| Página de Configuración del Módulo | Caducidad de la Cookie (Días) | 7 | Cuántos días permanece oculto el popup después de que un cliente lo cierra. |
| Página de Configuración del Módulo | Modo de Prueba | NO | Fuerza la aparición del popup en cada actualización para fines de prueba. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mi popup no aparece en el front office, incluso después de habilitarlo.**

- **R:** Primero, verifica si "Habilitar / Deshabilitar Popup" está configurado en SÍ. Si lo está, intenta habilitar el "Modo de Prueba" para ver si aparece. Si aún no se muestra, borra la caché de tu navegador y la caché de Smarty de PrestaShop (Ve a **Parámetros Avanzados > Rendimiento**, luego haz clic en "Borrar caché" en la esquina superior derecha). Además, asegúrate de haber guardado tu configuración después de realizar cambios.

**P2: El popup apareció una vez, pero ahora no vuelve a mostrarse.**

- **R:** Este es un comportamiento normal debido a la configuración de "Caducidad de la Cookie". El módulo establece una cookie en tu navegador para evitar que el popup reaparezca durante el número de días especificado. Para forzar su aparición para pruebas, habilita el "Modo de Prueba" en la configuración del módulo. Para verlo como un nuevo visitante, borra las cookies de tu navegador para el dominio de tu tienda o usa una ventana de navegación de incógnito/privada.

**P3: ¿Cómo puedo hacer que el popup se vea diferente (cambiar colores, fuentes, etc.)?**

- **R:** El módulo proporciona un modal blanco básico con una superposición del 70%. Para un estilo avanzado, necesitarías CSS personalizado. Esto generalmente lo maneja un desarrollador web. Puedes añadir CSS personalizado al archivo `custom.css` de tu tema o editar directamente el `front.css` del módulo (aunque esto último no se recomienda ya que las actualizaciones lo sobrescribirían).

**P4: ¿Puedo tener diferentes popups para diferentes páginas o grupos de clientes?**

- **R:** El módulo Free PopUp está diseñado para una única campaña a nivel de toda la tienda. Muestra el mismo contenido a todos los visitantes. Para popups más avanzados y dirigidos, necesitarías un módulo de popup con más funciones (y probablemente de pago).

**P5: Mis imágenes o enlaces en el contenido del popup no funcionan correctamente.**

- **R:** Asegúrate de usar URLs completas y absolutas para imágenes y enlaces (por ejemplo, `https://tutienda.com/img/tuimagen.jpg` en lugar de `/img/tuimagen.jpg`). El editor TinyMCE debería manejar esto automáticamente, pero a veces surgen problemas si copias y pegas contenido de fuentes externas. Vuelve a verificar el código fuente HTML si te sientes cómodo con ello.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo Free PopUp es un módulo de PrestaShop sencillo que sigue un patrón MVC básico. Utiliza principalmente la clase `Module` para su funcionalidad principal, gestión de configuración y registro de hooks. La visualización en el front-office se gestiona mediante una única plantilla renderizada a través de un hook, y su comportamiento es controlado por un archivo JavaScript simple. El estilo se maneja mediante archivos CSS dedicados tanto para el administrador como para el front-office.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores personalizados de front-office o back-office. Toda la configuración se maneja dentro del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no define ninguna clase personalizada o instancias de `ObjectModel`. Todos los datos de configuración se almacenan directamente en la tabla `ps_configuration` de PrestaShop utilizando los métodos estándar `Configuration::get()` y `Configuration::updateValue()`.

### 4.4 Activos JavaScript (`views/js/`)

-   **`myfreepopup/js/front.js`**
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Este script es responsable del comportamiento del popup en el lado del cliente.
    -   **Detalles:**
        -   Verifica la presencia de una cookie específica (`myfreepopup_closed`).
        -   Si no se encuentra la cookie (lo que significa que el usuario no ha cerrado el popup recientemente o es su primera visita), muestra el popup manipulando propiedades CSS (por ejemplo, `display: block`).
        -   Adjunta un detector de eventos al botón de cierre dentro del popup.
        -   Cuando se hace clic en el botón de cierre, oculta el popup y establece la cookie `myfreepopup_closed` con una caducidad basada en la configuración del módulo.
        -   También maneja la lógica del "Modo de Prueba", asegurando que la verificación de la cookie se omita cuando el modo de prueba está activo.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   **`myfreepopup/css/admin.css`**
    -   **Alcance:** Estilo del formulario de administración del back-office.
    -   **Detalles:** Contiene reglas de estilo básicas para la página de configuración del módulo en el back office de PrestaShop, asegurando una apariencia consistente dentro del panel de administración.
-   **`myfreepopup/css/front.css`**
    -   **Alcance:** Estilo del cliente del front-office.
    -   **Detalles:** Define la apariencia visual del popup en sí. Esto incluye:
        -   Estilo para la superposición modal (por ejemplo, `position: fixed`, `background-color`, `opacity`, `z-index`).
        -   Estilo para el cuadro de contenido principal del popup (por ejemplo, `background-color: #fff`, `border`, `box-shadow`, `max-width`, `padding`, `text-align`, `position: fixed`, `top`, `left`, `transform` para centrar).
        -   Estilo para el botón de cierre (por ejemplo, `position: absolute`, `font-size`, `cursor: pointer`).
        -   Ajustes responsivos para diferentes tamaños de pantalla utilizando media queries.
    -   **Selectores de clase CSS clave para anular:** `.myfreepopup_overlay`, `.myfreepopup_content`, `.myfreepopup_close`.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **`myfreepopup/views/admin_banner.tpl`**
    -   **Alcance:** Plantilla de administración.
    -   **Propósito:** Muestra un banner promocional o un mensaje de información dentro de la página de configuración del módulo en el back office.
-   **`myfreepopup/views/admin_locks.tpl`**
    -   **Alcance:** Plantilla de administración.
    -   **Propósito:** Probablemente se utiliza para mostrar información relacionada con la licencia del módulo o características adicionales, a menudo con un icono de candado.
-   **`myfreepopup/views/front.tpl`**
    -   **Alcance:** Plantilla de hook del front-office.
    -   **Propósito:** Esta es la plantilla principal responsable de renderizar la estructura HTML del popup en el front office.
    -   **Renderizado en el hook:** `displayHeader` (o un hook global similar donde se pueden cargar JS/CSS).
    -   **Contenido:** Contiene el HTML para la superposición, el cuadro de contenido del popup, el botón de cierre, e inserta dinámicamente la variable `{$popup_content}` (que proviene del editor TinyMCE en el back office). También incluye los archivos JavaScript y CSS necesarios.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   Este módulo no crea tablas SQL personalizadas.
    -   Almacena sus configuraciones en la tabla estándar `ps_configuration` utilizando claves como `MYFREEPOPUP_ENABLED`, `MYFREEPOPUP_CONTENT`, `MYFREEPOPUP_COOKIE_DAYS`, `MYFREEPOPUP_TEST_MODE`.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página del front-office. | Se utiliza para incluir los archivos CSS y JavaScript del módulo, y para renderizar la estructura HTML inicial del popup (`front.tpl`) que luego es controlada por JavaScript. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicia sesión en tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta relacionada con el módulo Free PopUp.
"""

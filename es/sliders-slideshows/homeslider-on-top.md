---
title: "Homeslider en la parte superior - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Homeslider en la parte superior de PrestaShop de MyPresta.eu."
sidebar:
  label: "Homeslider en la parte superior - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Homeslider on top en MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/homeslider-on-top.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/sliders-slideshows/homeslider-on-top/)
>
> ---


# Homeslider en la parte superior

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una instalación de PrestaShop y serán compatibles con este módulo.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

Este módulo está diseñado para ser extremadamente simple, actuando principalmente como un "puente" para permitir que el *slider de imágenes predeterminado de PrestaShop* se muestre en una nueva ubicación. Por lo tanto, su propia pantalla de configuración es mínima. Las imágenes, enlaces y configuraciones reales del slider (como velocidad, pausa al pasar el ratón, etc.) se gestionan a través del módulo estándar "Slider de imágenes" de PrestaShop.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de instalar "Homeslider en la parte superior", navegue a **Módulos > Gestor de módulos**, busque "Homeslider en la parte superior" y haga clic en "Configurar".

Normalmente encontrará una interfaz de configuración muy simple, centrada principalmente en habilitar o deshabilitar la funcionalidad principal del módulo.

- **Qué hace este ajuste:** Este ajuste controla si el módulo "Homeslider en la parte superior" está activo e intentando mostrar su slider de imágenes en la posición superior designada.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* El módulo registrará sus hooks e intentará renderizar el slider de imágenes predeterminado de PrestaShop en la parte superior de su tienda.
  - *Cuando está deshabilitado:* El módulo dejará de funcionar y el slider de imágenes no aparecerá en la posición superior (volverá a su ubicación predeterminada si el módulo estándar de Slider de imágenes sigue activo y enganchado en otro lugar).
- **Valor recomendado:** **SÍ** (Habilitado) si desea que su slider aparezca en la parte superior.
- **Escenario/ejemplo de comerciante:** Acaba de lanzar una nueva colección y desea destacarla de manera prominente con un gran banner en la parte superior de su sitio. Habilitaría este módulo. Si más tarde decide que prefiere el slider en una ubicación diferente (por ejemplo, debajo del encabezado), podría deshabilitar este módulo y volver a enganchar el módulo estándar de Slider de imágenes en otro lugar.

**Nota importante:** Este módulo *no* gestiona las imágenes ni la configuración del slider en sí. Para añadir, editar o eliminar diapositivas, o para cambiar el comportamiento del slider (como la velocidad de transición, la reproducción automática, etc.), debe ir a la configuración del módulo **"Slider de imágenes"** (a menudo se encuentra en **Módulos > Gestor de módulos**, busque "Slider de imágenes" o `ps_imageslider`).

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Módulo Habilitado/Deshabilitado | Habilitado | Controla si el módulo muestra activamente el slider de imágenes en la parte superior de la tienda. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mi slider no aparece en absoluto, incluso después de habilitar el módulo.**
R:

1. **Verifique el módulo "Slider de imágenes":** Asegúrese de que el *módulo predeterminado de PrestaShop "Slider de imágenes"* (a menudo llamado `ps_imageslider`) esté instalado, habilitado y tenga diapositivas configuradas. Este módulo "Homeslider en la parte superior" solo cambia la *posición* de ese slider existente.
2. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, PrestaShop necesita una actualización de caché para reconocer las nuevas ubicaciones de los módulos.
3. **Compatibilidad del tema:** Aunque está diseñado para una amplia compatibilidad, algunos temas muy personalizados pueden anular los comportamientos predeterminados de los hooks. Si los problemas persisten, póngase en contacto con el desarrollador de su tema o con el soporte de MyPresta.eu.

**P: El slider se muestra, pero se ve extraño o desalineado.**
R:

1. **Verifique la configuración del "Slider de imágenes":** Asegúrese de que las imágenes que ha subido al *módulo predeterminado de PrestaShop "Slider de imágenes"* tengan dimensiones consistentes y alta calidad.
2. **Estilo del tema:** El CSS de su tema podría estar en conflicto. Este módulo se encarga principalmente de la ubicación. Si el estilo es incorrecto, es probable que sea un problema de CSS de su tema que interactúa con los estilos predeterminados del slider. Es posible que necesite un desarrollador web para inspeccionar el CSS.

**P: ¿Cómo cambio las imágenes o la velocidad del slider?**
R: Este módulo solo controla la *ubicación*. Para gestionar el contenido real (imágenes, enlaces, descripciones) y el comportamiento (velocidad, reproducción automática, pausa al pasar el ratón) del slider, debe ir a la configuración del módulo **"Slider de imágenes"** (el módulo estándar de PrestaShop, que normalmente se encuentra buscando "Slider de imágenes" en **Módulos > Gestor de módulos**).

**P: ¿Puedo tener dos sliders, uno en la parte superior y otro en la posición predeterminada?**
R: Este módulo mueve específicamente el *slider de imágenes predeterminado* de PrestaShop a la parte superior. Si desea un segundo slider independiente, necesitaría un módulo diferente diseñado para ese propósito.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica para desarrolladores y webmasters que buscan comprender, personalizar o solucionar problemas del módulo "Homeslider en la parte superior".

### 4.1 Descripción general de la arquitectura

El módulo "Homeslider en la parte superior" es un módulo ligero de PrestaShop diseñado principalmente para alterar la ubicación de visualización del módulo principal `ps_imageslider`. Lo logra desregistrando `ps_imageslider` de sus hooks predeterminados (como `displayHome`) y volviéndolo a registrar en un hook más prominente, típicamente `displayHeader`. No introduce nuevas tablas de base de datos, clases complejas o extensos activos de front-office, lo que lo convierte en un "gestor de hooks" simple pero efectivo para la funcionalidad de slider existente.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de Front-Office o Back-Office. Toda la configuración se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase o modelo personalizado. Opera interactuando con las funciones de gestión de módulos principales de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado. El JavaScript para la funcionalidad del slider es proporcionado por el propio módulo `ps_imageslider`.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. El estilo del slider es proporcionado por el módulo `ps_imageslider` y/o el tema activo de PrestaShop.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

Este módulo no incluye ningún archivo de plantilla Smarty personalizado. Se basa en las plantillas proporcionadas por el módulo `ps_imageslider`.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Su configuración se almacena en `ps_configuration` utilizando claves de configuración estándar de PrestaShop.
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `install()` | Durante la instalación del módulo | Registra el módulo en `displayHeader` y potencialmente desregistra `ps_imageslider` de `displayHome` u otros hooks predeterminados. |
| `uninstall()` | Durante la desinstalación del módulo | Desregistra el módulo de `displayHeader` y potencialmente vuelve a registrar `ps_imageslider` en sus hooks predeterminados. |
| `displayHeader` | Renderiza contenido dentro de la sección `<head>` o en la parte superior del `<body>` | Este es el hook principal donde el módulo intenta renderizar el contenido de `ps_imageslider`. |
| `hookDisplayHeader` | Cuando se llama a `displayHeader` | El método del módulo que se ejecuta cuando se llama a `displayHeader`. Típicamente llama a `Module::hookDisplayHome()` del módulo `ps_imageslider` para renderizar su contenido. |

La lógica central reside en el archivo `homeslider-on-top.php`, específicamente dentro de los métodos `install()`, `uninstall()` y `hookDisplayHeader()`. El método `hookDisplayHeader()` es crucial ya que es responsable de obtener y renderizar el contenido del módulo `ps_imageslider` cuando este módulo está activo.

**Lógica clave dentro de `homeslider-on-top.php`:**

- **`__construct()`**: Configura la información básica del módulo.
- **`install()`**:
  - Llama a `parent::install()`.
  - Registra el módulo en `displayHeader`.
  - De manera crucial, a menudo intenta desregistrar el módulo `ps_imageslider` de `displayHome` para evitar la visualización duplicada, y luego registra `ps_imageslider` en `displayHeader` si aún no está allí, o asegura que su contenido se renderice a través del `hookDisplayHeader` de este módulo.
- **`uninstall()`**:
  - Llama a `parent::uninstall()`.
  - Desregistra el módulo de `displayHeader`.
  - Vuelve a registrar `ps_imageslider` en `displayHome` para restaurar el comportamiento predeterminado.
- **`getContent()`**: Maneja el formulario de configuración del back-office del módulo (que suele ser muy simple, a menudo solo un interruptor de habilitar/deshabilitar).
- **`hookDisplayHeader()`**:
  - Este método se ejecuta cuando PrestaShop llama al hook `displayHeader`.
  - Típicamente verifica si el módulo `ps_imageslider` está instalado y habilitado.
  - Si es así, llama directamente al método `hookDisplayHome()` del módulo `ps_imageslider` para recuperar su contenido renderizado y devolverlo, "moviendo" efectivamente la salida del slider a la posición `displayHeader`.

Los desarrolladores que deseen personalizar este módulo se centrarían principalmente en el método `hookDisplayHeader()` si quisieran alterar cómo se recupera o envuelve el contenido de `ps_imageslider`, o en los métodos `install()`/`uninstall()` si necesitaran cambiar los hooks específicos involucrados.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Homeslider en la parte superior", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.

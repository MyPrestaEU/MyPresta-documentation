---
title: "Efecto de carga al cambiar atributos - precargador - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Efecto de carga al cambiar atributos - precargador' de MyPresta.eu."
sidebar:
  label: "Efecto de carga al cambiar atributos - precargador - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Loading effect on attribute change - preloader en MyPresta.eu](https://mypresta.eu/modules/front-office-features/loading-effect-on-attribute-change-preloader.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/loading-effect-on-attribute-change-preloader/)
>
> ---


# Efecto de carga al cambiar atributos - precargador

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo para acceder a sus ajustes. Este módulo tiene una página de configuración sencilla.

#### **Habilitar / Deshabilitar Precargador**

-   **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar el efecto de carga en toda su tienda.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* La animación de carga aparecerá en las páginas de producto cada vez que un cliente cambie los atributos del producto.
    -   *Cuando está deshabilitado (NO):* La animación de carga no aparecerá, y sus páginas de producto se comportarán como lo hacían antes de instalar el módulo (es decir, sin retroalimentación visual durante los cambios de atributos).
-   **Valor recomendado:** SÍ
-   **Escenario / ejemplo de comerciante:** Acaba de instalar el módulo y desea activarlo. Establezca esto en SÍ. Si necesita deshabilitarlo temporalmente para pruebas o durante una actualización importante del tema, puede cambiarlo a NO.

#### **Tipo de Precargador**

-   **Qué hace este ajuste:** Esta opción le permite elegir el estilo o tipo de animación de carga que se mostrará. El módulo generalmente viene con una selección de animaciones de spinner predefinidas.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en "Spinner 1":* Se mostrará un tipo específico de spinner animado (por ejemplo, un círculo giratorio simple).
    -   *Cuando se establece en "Spinner 2":* Se mostrará un spinner animado diferente (por ejemplo, un punto pulsante, una barra que se desvanece).
    -   *Cuando se establece en "Imagen personalizada":* Si está disponible, esta opción le permitiría subir su propio GIF o imagen para usar como precargador. (Según la descripción del módulo, esto podría ser una mejora futura o una opción más avanzada no mencionada directamente, pero es una característica común para los ajustes de "tipo de precargador").
-   **Valor recomendado:** Experimente con las opciones disponibles para ver cuál se adapta mejor al diseño y la marca de su tienda. Un spinner simple y limpio suele ser lo mejor.
-   **Escenario / ejemplo de comerciante:** Su tienda tiene un diseño minimalista, por lo que podría elegir "Spinner 1" si es una animación limpia y discreta. Si su marca es más juguetona, podría elegir un "Spinner 2" más dinámico o incluso subir un GIF personalizado de su marca si la opción está disponible.

#### **Color del Precargador**

-   **Qué hace este ajuste:** Esto le permite definir el color de la animación de carga. Esto es crucial para que el precargador coincida con el esquema de color de su tienda.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en `#007bff` (azul):* El spinner aparecerá en color azul.
    -   *Cuando se establece en `#ff0000` (rojo):* El spinner aparecerá en color rojo.
-   **Valor recomendado:** Un color que complemente los colores primarios o de acento de su tienda. A menudo, un gris neutro, blanco o el color de acción principal de su marca funciona bien.
-   **Escenario / ejemplo de comerciante:** Los botones principales de llamada a la acción de su tienda son verdes. Establecer el color del precargador en verde hará que se sienta como una parte integrada del diseño de su tienda, en lugar de un elemento genérico.

#### **Tamaño del Precargador (en píxeles)**

-   **Qué hace este ajuste:** Esto controla las dimensiones físicas (ancho y alto) de la animación de carga.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en `32px`:* El spinner será pequeño y sutil.
    -   *Cuando se establece en `64px`:* El spinner será más grande y prominente.
-   **Valor recomendado:** Comience con un tamaño moderado como `40px` o `48px`. Pruebe en escritorio y móvil para asegurarse de que sea visible pero no excesivamente intrusivo.
-   **Escenario / ejemplo de comerciante:** En una página de producto con imágenes grandes, un spinner de `32px` podría perderse. Aumentarlo a `48px` o `56px` lo haría más notorio sin ser una distracción. Por el contrario, si las imágenes de su producto son pequeñas, un spinner más pequeño podría ser más apropiado.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar / Deshabilitar Precargador | SÍ | Activa o desactiva la animación de carga en los cambios de atributos del producto. |
| Configuración del módulo | Tipo de Precargador | (Elegir según preferencia) | Selecciona el estilo visual del indicador de carga. |
| Configuración del módulo | Color del Precargador | (Coincidir con su marca) | Establece el color de la animación de carga para integrarse con el diseño de su tienda. |
| Configuración del módulo | Tamaño del Precargador (en píxeles) | 40px - 56px | Ajusta el tamaño físico del indicador para visibilidad y estética. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: He habilitado el módulo, pero no veo ningún efecto de carga en mi página de producto.**
R:

1.  **Borrar caché:** La razón más común. Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
2.  **Posición del módulo:** Asegúrese de que el módulo esté enganchado correctamente. Aunque el módulo lo maneja automáticamente, a veces los conflictos de tema pueden impedirlo. El módulo generalmente inyecta su CSS/JS en el hook `displayHeader`.
3.  **Sobreescrituras de tema:** Si está utilizando un tema muy personalizado, podría estar sobrescribiendo el comportamiento JavaScript predeterminado de PrestaShop para los cambios de atributos, impidiendo que el módulo detecte el evento. Póngase en contacto con el desarrollador de su tema o con un experto en PrestaShop.
4.  **Caché del navegador:** Intente borrar la caché de su navegador o probar en una ventana de incógnito/privada.

**P: El precargador aparece, pero se ve fuera de lugar o no coincide con el diseño de mi tienda.**
R:

1.  **Ajustar color y tamaño:** Vaya a la página de configuración del módulo y experimente con los ajustes "Color del Precargador" y "Tamaño del Precargador". Intente que coincida con los colores primarios o de acento de su marca.
2.  **Cambiar tipo de precargador:** Si está disponible, pruebe diferentes opciones de "Tipo de Precargador" para encontrar una que se adapte mejor visualmente a su tema.
3.  **CSS personalizado:** Para una personalización avanzada, un webmaster puede usar CSS personalizado para ajustar su apariencia (consulte la Guía del desarrollador).

**P: El precargador aparece, pero permanece en la pantalla demasiado tiempo, incluso después de que los atributos del producto se hayan actualizado.**
R: Esto generalmente indica un conflicto de JavaScript o un problema con el mecanismo de actualización de atributos de su tema. El módulo se basa en eventos estándar de PrestaShop para saber cuándo ocultar el precargador.

1.  **Verifique si hay errores de JavaScript:** Abra la consola de desarrollador de su navegador (F12) y busque cualquier mensaje de error en rojo en la pestaña "Consola" al cambiar atributos.
2.  **Conflictos de módulos:** Deshabilite temporalmente otros módulos de front-office que modifiquen el comportamiento de la página del producto (por ejemplo, módulos de vista rápida, módulos de atributos personalizados) para ver si alguno está causando un conflicto.
3.  **Compatibilidad del tema:** Asegúrese de que su tema sea totalmente compatible con su versión de PrestaShop y no tenga JavaScript obsoleto.

**P: ¿Este módulo ralentiza mi sitio web?**
R: No, el módulo en sí es muy ligero. Agrega una pequeña cantidad de CSS y JavaScript a su página. Su propósito es *gestionar visualmente* la percepción del tiempo de carga, no causarlo. Si su página es lenta, el problema reside en otro lugar (por ejemplo, imágenes grandes, servidor no optimizado, otros módulos pesados).

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Efecto de carga al cambiar atributos - precargador" (`ppreloader`) es un módulo ligero, centrado en el front-office, diseñado para mejorar la experiencia del usuario durante las actualizaciones de atributos de productos impulsadas por AJAX. Principalmente aprovecha el hook `displayHeader` de PrestaShop para inyectar su CSS y JavaScript, que luego escucha cambios o eventos DOM específicos en la página del producto para activar y ocultar la animación de carga. No introduce nuevas tablas de base de datos ni lógica de backend compleja, centrándose únicamente en la presentación del front-end.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la configuración se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase personalizada o definición de `ObjectModel`. Opera completamente a través de su archivo de módulo principal y activos de front-end.

### 4.4 Activos JavaScript (`views/js/`)

-   **`ppreloader/views/js/ppreloader.js`**
    -   **Alcance:** Front-office (Página de Producto).
    -   **Responsabilidad:** Este script es el núcleo de la funcionalidad del módulo.
        -   Espera a que el DOM esté listo.
        -   Escucha los cambios en los selectores de atributos del producto (por ejemplo, `select[name="group[X]"]`, botones de radio, selectores de color, etc., dependiendo de la estructura del tema).
        -   También es probable que escuche eventos AJAX relacionados con las actualizaciones de combinaciones de productos (por ejemplo, el evento `updateProduct` o las llamadas `ajaxComplete` dirigidas a URL específicas).
        -   Cuando se detecta un cambio de atributo y se inicia una llamada AJAX, inserta dinámicamente la estructura HTML del precargador (definida en `header.tpl` o generada sobre la marcha) en un contenedor relevante en la página del producto (por ejemplo, `$('#product_images')` o `$('#product-details')`).
        -   Aplica el `Tipo de Precargador`, `Color del Precargador` y `Tamaño del Precargador` elegidos de la configuración del módulo.
        -   Una vez que la llamada AJAX se completa y la información del producto se actualiza, elimina el HTML del precargador del DOM.
        -   Asegura la capacidad de respuesta móvil del precargador.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`ppreloader/views/css/ppreloader.css`**
    -   **Alcance:** Estilo del cliente del front-office.
    -   **Responsabilidad:** Esta hoja de estilo define la apariencia visual y la animación del precargador de carga.
        -   Incluye estilos para la superposición que podría cubrir el área del producto durante la carga.
        -   Define el CSS para varios tipos de precargador (spinners, puntos, etc.), incluidos sus fotogramas clave de animación.
        -   Asegura que el precargador esté centrado y posicionado correctamente dentro de su contenedor.
        -   Maneja la capacidad de respuesta básica para diferentes tamaños de pantalla.
    -   **Selectores de clase CSS clave que los desarrolladores pueden sobrescribir:**
        -   `.ppreloader-overlay`: El contenedor principal de la superposición.
        -   `.ppreloader-spinner`: El contenedor para la animación real del spinner.
        -   Clases específicas para diferentes tipos de spinner (por ejemplo, `.ppreloader-spinner-type1`, `.ppreloader-spinner-type2`).
        -   Reglas `@keyframes` para las animaciones.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **`ppreloader/views/header.tpl`**
    -   **Alcance:** Front-office.
    -   **Hook:** `displayHeader`
    -   **Responsabilidad:** Esta plantilla es principalmente responsable de incluir los archivos CSS y JavaScript del módulo en la sección `<head>` de las páginas del front-office.
        -   Utiliza `{$css_dir}ppreloader.css` para enlazar la hoja de estilo.
        -   Utiliza `{$js_dir}ppreloader.js` para enlazar el archivo JavaScript.
        -   También es probable que contenga JavaScript en línea para pasar la configuración del módulo (estado habilitado, tipo, color, tamaño) del Back Office al script `ppreloader.js`, haciéndolos disponibles para uso dinámico. Esto es crucial para que el JS sepa cómo renderizar el precargador.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**: Este módulo no crea ninguna tabla SQL personalizada. Todos los ajustes de configuración se almacenan en la tabla `ps_configuration` utilizando claves de configuración estándar de PrestaShop (por ejemplo, `PPRELOADER_ENABLED`, `PPRELOADER_TYPE`, `PPRELOADER_COLOR`, `PPRELOADER_SIZE`).
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página del front-office. | Inyecta los archivos CSS (`ppreloader.css`) y JavaScript (`ppreloader.js`) del módulo, además de pasar variables de configuración al JS. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y descargar las últimas versiones del módulo "Efecto de carga al cambiar atributos - precargador", inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.
"""

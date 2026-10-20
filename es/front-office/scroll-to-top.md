---
title: "Volver arriba - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Volver arriba de PrestaShop por MyPresta.eu."
sidebar:
  label: "Volver arriba - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Scroll to top en MyPresta.eu](https://mypresta.eu/modules/front-office-features/scroll-to-top.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/scroll-to-top/)
>
> ---


# Volver arriba

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de instalar el módulo, navegue a **Módulos > Gestor de módulos** y haga clic en "Configurar" junto a "Volver arriba". Esta página le permite personalizar la apariencia y el posicionamiento del botón de volver arriba.

#### **Posicionamiento visual**

- **Qué hace este ajuste:** Es una representación visual de dónde aparecerá el botón en su tienda. No es un ajuste directo, sino una ayuda visual que cambia según sus ajustes de "Posición X" y "Posición Y".
- **Efecto de cambiar este ajuste:** A medida que ajuste "Posición X" y "Posición Y", la vista previa del botón en esta página de configuración se moverá, ayudándole a visualizar su ubicación final en su front office.
- **Valor recomendado:** Es dinámico.
- **Escenario / ejemplo de comerciante:** Si desea que el botón esté más cerca de la parte inferior derecha, verá cómo la vista previa se mueve allí a medida que ajusta los valores X e Y.

#### **Esquema de color**

- **Qué hace este ajuste:** Controla el color de fondo del botón de volver arriba.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un color específico (por ejemplo, #007bff para azul):* El botón se mostrará con ese color de fondo en su front office.
  - *Cuando se establece un color diferente:* El fondo del botón cambiará en consecuencia.
- **Valor recomendado:** Elija un color que complemente la marca de su tienda y sea claramente visible sobre el fondo de su sitio web, pero que no sea demasiado distractor.
- **Escenario / ejemplo de comerciante:** Si los colores de su marca son azul y blanco, podría establecerlo en un tono de azul para que coincida con su tema.

#### **Opacidad**

- **Qué hace este ajuste:** Determina cuán transparente u opaco es el botón de volver arriba. Una opacidad más baja lo hace más transparente, permitiendo que se vea el contenido de fondo.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un valor alto (por ejemplo, 1.0 o 100%):* El botón será completamente opaco, sin transparencia.
  - *Cuando se establece un valor más bajo (por ejemplo, 0.7 o 70%):* El botón será semitransparente, mezclándose sutilmente con el fondo de su tienda.
- **Valor recomendado:** Un valor entre 0.8 y 1.0 (80%-100%) suele ser bueno. Demasiado bajo, y podría ser difícil de ver; demasiado alto, y podría parecer demasiado prominente.
- **Escenario / ejemplo de comerciante:** Si desea que el botón esté presente pero no sea demasiado dominante, establecer la opacidad en 0.8 podría ser una buena opción.

#### **Posición X (desde la derecha)**

- **Qué hace este ajuste:** Controla la posición horizontal del botón, específicamente su distancia desde el borde derecho de la ventana del navegador.
- **Efecto de cambiar este ajuste:**
  - *Aumentar el valor (por ejemplo, de 20px a 50px):* Mueve el botón más a la izquierda, lejos del borde derecho.
  - *Disminuir el valor (por ejemplo, de 50px a 20px):* Mueve el botón más cerca del borde derecho.
- **Valor recomendado:** Comience con un valor como `20px` o `30px` para mantenerlo cómodamente alejado del borde sin que esté demasiado dentro del área de contenido.
- **Escenario / ejemplo de comerciante:** Si tiene un widget de chat u otro elemento fijo en el lado derecho de su tienda, podría aumentar este valor a `60px` para evitar que el botón de volver arriba se superponga.

#### **Posición Y (desde abajo)**

- **Qué hace este ajuste:** Controla la posición vertical del botón, específicamente su distancia desde el borde inferior de la ventana del navegador.
- **Efecto de cambiar este ajuste:**
  - *Aumentar el valor (por ejemplo, de 20px a 50px):* Mueve el botón más hacia arriba, lejos del borde inferior.
  - *Disminuir el valor (por ejemplo, de 50px a 20px):* Mueve el botón más cerca del borde inferior.
- **Valor recomendado:** Comience con un valor como `20px` o `30px` para mantenerlo cómodamente alejado del borde inferior, por encima del pie de página.
- **Escenario / ejemplo de comerciante:** Si su tienda tiene un pie de página fijo o una barra de consentimiento de cookies en la parte inferior, podría aumentar este valor a `70px` para asegurarse de que el botón de volver arriba siempre sea visible por encima de esos elementos.

#### **Tabla de referencia rápida de configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Posicionamiento visual | Dinámico | Ayuda visual para la ubicación del botón basada en los ajustes X/Y. |
| Configuración del módulo | Esquema de color | Varía (ej. #007bff) | Establece el color de fondo del botón de volver arriba. |
| Configuración del módulo | Opacidad | 0.8 - 1.0 | Controla la transparencia del botón (0.0 = totalmente transparente, 1.0 = totalmente opaco). |
| Configuración del módulo | Posición X (desde la derecha) | 20px - 30px | Define la distancia horizontal del botón desde el borde derecho de la pantalla. |
| Configuración del módulo | Posición Y (desde abajo) | 20px - 30px | Define la distancia vertical del botón desde el borde inferior de la pantalla. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: El botón de volver arriba no aparece en mi tienda. ¿Qué debo hacer?**
R:

1.  **Verificar el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que el módulo "Volver arriba" esté instalado y habilitado.
2.  **Borrar caché:** PrestaShop utiliza caché. Vaya a **Parámetros avanzados > Rendimiento**, desplácese hasta "Borrar caché" y haga clic en "Borrar caché". Luego, actualice su front office.
3.  **Desplazarse hacia abajo:** Recuerde, el botón solo aparece cuando se desplaza hacia abajo en la página. Asegúrese de haberse desplazado lo suficiente para que sea visible.
4.  **Verificar posiciones:** Asegúrese de que "Posición X" y "Posición Y" no estén configuradas con valores extremadamente altos que puedan empujar el botón fuera de la pantalla. Intente configurarlos en `20px` cada uno como prueba.
5.  **Compatibilidad del tema:** Aunque es raro, algunos temas altamente personalizados pueden tener conflictos de CSS. Si los pasos anteriores no funcionan, cambie temporalmente al tema predeterminado de PrestaShop (Classic) para ver si aparece el botón. Si lo hace, es posible que el desarrollador de su tema necesite ayudar.

**P: El botón es visible pero no se desplaza hacia arriba al hacer clic.**
R:

1.  **Verificar JavaScript:** Esto generalmente indica un conflicto o error de JavaScript. Abra la consola de desarrollador de su navegador (generalmente F12, luego vaya a la pestaña "Consola") y busque cualquier mensaje de error en rojo.
2.  **Orden de los módulos:** Asegúrese de que ningún otro módulo esté interfiriendo con la funcionalidad principal de JavaScript.
3.  **Reinstalar:** Intente desinstalar y reinstalar el módulo. Esto a veces puede resolver archivos corruptos.

**P: ¿Cómo puedo cambiar el icono del botón (por ejemplo, de una flecha a otra cosa)?**
R: El módulo utiliza un icono de flecha estándar. Cambiar esto requiere una modificación directa de los archivos CSS o de plantilla del módulo, lo que se considera una personalización de desarrollador. No es una opción disponible en la configuración del módulo.

**P: El botón se ve bien en el escritorio, pero es demasiado grande/pequeño/mal colocado en el móvil.**
R:

1.  **Ajustar X e Y:** Utilice los ajustes de "Posición X" y "Posición Y" para ajustar su ubicación específicamente para dispositivos móviles. Es posible que necesite valores diferentes para evitar conflictos con elementos de la interfaz de usuario específicos para móviles.
2.  **Capacidad de respuesta del tema:** El CSS del módulo está diseñado para ser receptivo, pero la capacidad de respuesta general de su tema puede influir en cómo aparece. Pruebe en dispositivos reales o utilice las herramientas de desarrollador de su navegador para simular diferentes tamaños de pantalla.
3.  **CSS personalizado (tarea del desarrollador):** Para cambios avanzados de tamaño o estilo específicos para dispositivos móviles, un webmaster necesitaría agregar reglas CSS personalizadas a su tema, dirigidas al botón solo en pantallas más pequeñas.

**P: ¿Este módulo ralentizará mi sitio web?**
R: No, el módulo "Volver arriba" es muy ligero. Añade un mínimo de CSS y JavaScript, que se cargan de manera eficiente. Cualquier impacto en el rendimiento sería insignificante.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores, webmasters y agencias que buscan comprender, depurar o extender el módulo "Volver arriba".

### 4.1 Descripción general de la arquitectura

El módulo "Volver arriba" es un módulo de PrestaShop sencillo centrado principalmente en la mejora de la interfaz de usuario del front-office. Sigue una estructura clásica de módulo de PrestaShop, aprovechando los hooks para inyectar sus activos HTML, CSS y JavaScript en el front office. No introduce controladores personalizados ni modelos de datos complejos, sino que se basa en el sistema de configuración de PrestaShop para sus ajustes. La funcionalidad principal se gestiona en el lado del cliente a través de JavaScript.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. La funcionalidad de front-office del módulo se gestiona completamente inyectando activos y una plantilla a través de hooks.
-   **Controladores de Administración de Back-Office**: Ninguno. Toda la configuración se gestiona a través del método `getContent()` del módulo principal.

### 4.3 Clases y modelos principales (`classes/`)

-   No hay clases personalizadas ni definiciones de `ObjectModel` presentes en este módulo. Toda la lógica reside dentro del archivo principal `scrolltop.php`.

### 4.4 Activos JavaScript (`views/js/`)

-   **`scrolltop/scrolltop.js`**
    *   **Alcance:** Front-office.
    *   **Responsabilidad:** Este script maneja la lógica principal del lado del cliente para el botón de volver arriba.
    *   **Detalles:**
        *   Espera a que el DOM esté completamente cargado (`$(document).ready()`).
        *   Adjunta un oyente de eventos al evento `$(window).scroll()`.
        *   Dentro del manejador de eventos de desplazamiento, verifica `$(this).scrollTop()`. Si la posición de desplazamiento es mayor que un cierto umbral (por ejemplo, 100px), muestra el botón de volver arriba; de lo contrario, lo oculta.
        *   Adjunta un oyente de eventos de clic al elemento del botón de volver arriba.
        *   Cuando se hace clic, utiliza `$('html, body').animate({scrollTop: 0}, 'slow');` para animar suavemente el desplazamiento de la página de vuelta a la parte superior.
        *   Evita el comportamiento de enlace predeterminado (`return false;`).
    *   **Dependencias:** jQuery (que suele estar disponible en el front office de PrestaShop).

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`scrolltop/scrolltop.css`**
    *   **Alcance:** Estilo del cliente del front-office.
    *   **Responsabilidad:** Define la apariencia visual y el posicionamiento fijo del botón de volver arriba.
    *   **Detalles:**
        *   Dirige el elemento `#scroll-to-top`.
        *   Utiliza `position: fixed;` para mantener el botón en una posición estática en relación con la ventana gráfica.
        *   Aplica las propiedades `bottom` y `right`, establecidas dinámicamente por la configuración del módulo, para controlar su ubicación exacta.
        *   Define `z-index` para asegurar que el botón aparezca por encima de otros contenidos.
        *   Establece `display: none;` inicialmente, ya que JavaScript controla su visibilidad.
        *   Estilos para `background-color`, `border-radius`, `padding`, `width`, `height`, `line-height`, `text-align`, `color` (para el icono de flecha), `font-size` y `cursor`.
        *   Incluye una propiedad `transition` para cambios visuales suaves (por ejemplo, al pasar el ratón o al aparecer/desaparecer).
        *   Puede incluir ajustes responsivos utilizando consultas de medios para optimizar la apariencia en diferentes tamaños de pantalla.
    *   **Selectores de clase CSS clave que los desarrolladores pueden anular:** `#scroll-to-top`, `#scroll-to-top i` (para el icono).

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    *   **`scrolltop/footer.tpl`**
        *   **Hook:** `displayFooter` (o `displayHeader` para la carga de activos).
        *   **Propósito:** Esta plantilla renderiza la estructura HTML para el botón de volver arriba.
        *   **Contenido:** Típicamente contiene una etiqueta `<a>` o `<div>` con un ID como `#scroll-to-top`, y una etiqueta `<i>` (a menudo usando Font Awesome o una fuente de iconos similar) para el icono de flecha.
        *   También incluye atributos de estilo en línea o atributos de datos para pasar los valores configurados de `color`, `opacity`, `position X` y `position Y` desde la configuración del módulo al CSS o JavaScript del front-end para un estilo dinámico.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    *   Este módulo no crea ninguna tabla SQL personalizada.
    *   Los ajustes de configuración (`st_color`, `st_x`, `st_y`, `st_o`, `mypresta_updates`, `update_`, `updatev_`) se almacenan en la tabla `ps_configuration` de PrestaShop.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Se utiliza para registrar y cargar los activos CSS (`scrolltop.css`) y JavaScript (`scrolltop.js`) del módulo. |
| `displayFooter` | Al final de la sección `<body>` de cada página del front-office, justo antes de la etiqueta de cierre `</body>`. | Se utiliza para renderizar la estructura HTML del botón de volver arriba (`footer.tpl`). Esto asegura que el HTML del botón esté presente en el DOM para que JavaScript lo manipule. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y las últimas versiones del módulo "Volver arriba", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con la funcionalidad y compatibilidad del módulo.

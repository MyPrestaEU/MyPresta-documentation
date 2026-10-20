---
title: "Desplazarse hacia abajo - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Desplazarse hacia abajo' de MyPresta.eu."
sidebar:
  label: "Desplazarse hacia abajo - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Scroll to bottom en MyPresta.eu](https://mypresta.eu/modules/front-office-features/scroll-to-bottom.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/scroll-to-bottom/)
>
> ---


# Desplazarse hacia abajo

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo "Desplazarse hacia abajo". Puede acceder a ella navegando a **Módulos > Gestor de módulos** y buscando "Desplazarse hacia abajo", luego haciendo clic en el botón "Configurar".

#### Ajustes y opciones

-   **Color del botón (st\_color)**

    -   **Qué hace este ajuste:** Le permite definir el color del botón "Desplazarse hacia abajo". Puede usar nombres de colores HTML estándar (como `red`, `blue`, `green`) o códigos de color hexadecimales (como `#FF0000` para rojo, `#0000FF` para azul).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece un color específico (por ejemplo, `#007bff`):* El botón se mostrará en ese color exacto en su front office.
        -   *Cuando se deja vacío o es inválido:* El botón probablemente volverá a un color predeterminado definido por el CSS del módulo, que podría no coincidir con su marca.
    -   **Valor recomendado:** Elija un color que complemente el diseño de su tienda y sea claramente visible contra su fondo, pero no demasiado distractor. Use el color primario o secundario de su marca.
    -   **Escenario / ejemplo de comerciante:** Si su marca usa mucho azul oscuro, establecer esto en `#000080` (azul marino) haría que el botón se integre bien sin dejar de ser funcional.
-   **Posición X del botón (st\_x)**

    -   **Qué hace este ajuste:** Controla la posición horizontal del botón en la pantalla. Determina qué tan lejos del borde derecho de la ventana del navegador aparecerá el botón. El valor suele estar en píxeles.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece un valor más bajo (por ejemplo, `20`):* El botón estará más cerca del borde derecho de la pantalla.
        -   *Cuando se establece un valor más alto (por ejemplo, `80`):* El botón estará más lejos del borde derecho, moviéndose hacia el centro de la pantalla.
    -   **Valor recomendado:** `20` o `30` píxeles es una ubicación común y discreta. Esto lo mantiene fuera del área de contenido principal pero aún fácilmente accesible.
    -   **Escenario / ejemplo de comerciante:** Si tiene otros elementos fijos en el lado derecho de su pantalla (como un widget de chat), es posible que deba aumentar este valor a `50px` para evitar que el botón "Desplazarse hacia abajo" se superponga.
-   **Posición Y del botón (st\_y)**

    -   **Qué hace este ajuste:** Controla la posición vertical del botón en la pantalla. Determina qué tan lejos del borde superior de la ventana del navegador aparecerá el botón. El valor suele estar en píxeles.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece un valor más bajo (por ejemplo, `20`):* El botón estará más cerca del borde superior de la pantalla.
        -   *Cuando se establece un valor más alto (por ejemplo, `80`):* El botón estará más abajo del borde superior.
    -   **Valor recomendado:** `20` o `30` píxeles es un buen punto de partida. Esto lo coloca en la esquina superior derecha sin estar demasiado alto o demasiado bajo.
    -   **Escenario / ejemplo de comerciante:** Si el encabezado de su tienda es muy alto o tiene un botón "Desplazarse hacia arriba" también en la parte superior derecha, podría ajustar esto a `60px` o `70px` para asegurar que ambos botones tengan suficiente espacio y no se superpongan.
-   **Opacidad del botón (st\_o)**

    -   **Qué hace este ajuste:** Controla la transparencia del botón. Los valores de opacidad van de `0` (completamente transparente/invisible) a `1` (completamente opaco/sólido). Puede usar valores decimales como `0.5` para una transparencia del 50%.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en `1`:* El botón será completamente visible y sólido.
        -   *Cuando se establece en `0.5`:* El botón será semitransparente, permitiendo que se vea el contenido de fondo.
        -   *Cuando se establece en `0`:* El botón será invisible (aunque seguirá siendo clicable si sabe dónde está).
    -   **Valor recomendado:** `0.8` o `0.9` suele ser un buen equilibrio. Hace que el botón sea ligeramente menos intrusivo sin dejar de ser claramente visible. `1` también es perfectamente aceptable si desea que destaque más.
    -   **Escenario / ejemplo de comerciante:** Si encuentra el botón demasiado prominente o distractor, reducir su opacidad a `0.7` puede hacer que se integre más sutilmente en el diseño de su tienda sin perder su funcionalidad.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Color del botón (st\_color) | `#007bff` (ejemplo) | Establece el color del botón. Afecta la visibilidad y la coherencia de la marca. |
| Configuración del módulo | Posición X del botón (st\_x) | `20` | Distancia horizontal desde el borde derecho. Evita la superposición con otros elementos. |
| Configuración del módulo | Posición Y del botón (st\_y) | `20` | Distancia vertical desde el borde superior. Posiciona el botón claramente. |
| Configuración del módulo | Opacidad del botón (st\_o) | `0.8` | Transparencia del botón. Controla cuán intrusivo o sutil aparece. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

-   **P: El botón no aparece en mi tienda.**
    -   **R:** Primero, asegúrese de que el módulo esté instalado y habilitado en **Módulos > Gestor de módulos**. Luego, revise la página de configuración del módulo para asegurarse de que todos los ajustes estén guardados. Si aún no aparece, intente borrar la caché de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**). A veces, los temas personalizados también pueden interferir; cambie temporalmente al tema predeterminado de PrestaShop para descartar esto.
-   **P: El botón aparece, pero está en el lugar equivocado o se ve extraño.**
    -   **R:** Vaya a la página de configuración del módulo. Ajuste los valores de "Posición X" y "Posición Y" para mover el botón horizontal y verticalmente. Experimente con diferentes valores hasta que esté en una ubicación satisfactoria. Para problemas de apariencia, revise los ajustes de "Color" y "Opacidad". Si aún se ve mal, el CSS de su tema podría estar anulando los estilos del módulo.
-   **P: La animación de desplazamiento no es suave o no funciona.**
    -   **R:** Este módulo utiliza JavaScript para el efecto de desplazamiento suave. Asegúrese de que no haya errores de JavaScript en su sitio (puede verificar la consola de desarrollador de su navegador en busca de errores). Los conflictos con otros módulos o el JavaScript del tema personalizado a veces pueden impedir que la animación funcione correctamente. Borrar la caché es un buen primer paso.
-   **P: ¿Puedo cambiar el icono del botón?**
    -   **R:** La versión actual del módulo no ofrece una configuración directa para cambiar el icono desde el back office. Esto requeriría CSS personalizado o modificaciones de plantilla (consulte la Guía del desarrollador para obtener más detalles técnicos).
-   **P: ¿Este módulo afecta el rendimiento o el SEO de mi tienda?**
    -   **R:** Este módulo es muy ligero, añadiendo un mínimo de CSS y JavaScript. Debería tener un impacto insignificante en la velocidad de carga de su tienda o en el SEO. La funcionalidad es puramente para la experiencia del usuario y no altera el contenido de una manera que afecte la indexación de los motores de búsqueda.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Desplazarse hacia abajo" es una característica sencilla del front-office implementada como un módulo estándar de PrestaShop. Principalmente aprovecha el sistema de hooks de PrestaShop para inyectar su CSS, JavaScript y la estructura HTML del botón en el front office. La configuración se maneja a través del método `getContent()` en el archivo principal del módulo, almacenando los ajustes en `ps_configuration`. No hay controladores personalizados, ObjectModels ni interacciones complejas con la base de datos.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. La funcionalidad de front-office del módulo se inyecta directamente a través de hooks.
-   **Controladores de Administración de Back-Office**: Ninguno. La configuración se maneja dentro del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

-   Ninguno. El módulo no define ninguna clase o ObjectModels personalizados. Toda la lógica está contenida dentro de `scrollbottom.php`.

### 4.4 Activos de JavaScript (`views/js/`)

-   `scrollbottom/scrollbottom.js`
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Este script es responsable de la funcionalidad principal del botón "Desplazarse hacia abajo".
        -   Probablemente escucha que el DOM esté listo.
        -   Adjunta un oyente de eventos de clic al elemento del botón "Desplazarse hacia abajo".
        -   Cuando se hace clic, utiliza el método `window.scrollTo()` o `element.scrollIntoView()` de JavaScript, a menudo con `behavior: 'smooth'`, para animar el desplazamiento hasta la parte inferior de la página (específicamente, la altura máxima de desplazamiento del elemento `body` o `html`).
        -   También podría manejar la visibilidad del botón, haciéndolo aparecer o desaparecer según la posición de desplazamiento del usuario (por ejemplo, solo mostrar cuando el usuario se ha desplazado una cierta cantidad).

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `scrollbottom/scrollbottom.css`
    -   **Alcance:** Estilo del cliente del front-office.
    -   **Componentes e contenedores principales de la interfaz de usuario que estiliza:** Esta hoja de estilo define la apariencia visual y el posicionamiento del botón "Desplazarse hacia abajo".
        -   Probablemente apuntará a un ID o clase específica para el botón (por ejemplo, `#scrollbottom_button`).
        -   Define propiedades como `position: fixed`, `right`, `top`, `z-index`, `background-color`, `color`, `padding`, `border-radius`, `cursor`, y potencialmente `display: none` inicialmente, con JavaScript controlando su visibilidad.
        -   También puede incluir estilos para el icono de flecha dentro del botón (por ejemplo, usando un icono de fuente o una imagen de fondo).
    -   **Selectores de clase CSS clave que los desarrolladores pueden anular en su tema:** Los desarrolladores pueden inspeccionar el HTML generado para encontrar el ID/clase exactos del botón (por ejemplo, `#scrollbottom_button`) y anular sus estilos en el archivo `custom.css` de su tema o un archivo equivalente para lograr un aspecto personalizado.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   `scrollbottom/adv.tpl`: Esta plantilla se utiliza probablemente para mostrar un anuncio o contenido promocional relacionado con MyPresta.eu, a menudo inyectado en un hook como `displayAdminHome` o similar, pero no directamente relacionado con la funcionalidad del botón del front-office.
    -   `scrollbottom/footer.tpl`: Esta es la plantilla principal para el botón del front-office.
        -   **Enganchado en:** `displayFooter` o `footer` (dependiendo de la versión de PrestaShop y el tema).
        -   **Salidas:** La estructura HTML para el botón "Desplazarse hacia abajo", incluyendo su ID/clase, el icono de flecha y potencialmente estilos en línea o atributos de datos derivados de la configuración del módulo (color, posición, opacidad).
-   **Plantillas de administración (`views/templates/admin/`)**: Ninguna.
-   **Plantillas de Front-office (`views/templates/front/`)**: Ninguna.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:

    -   El módulo no crea ninguna tabla SQL personalizada.
    -   Los ajustes de configuración se almacenan en la tabla `ps_configuration` utilizando claves como `ST_COLOR`, `ST_X`, `ST_Y`, `ST_O`.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` del front office. | Se utiliza para registrar e incluir los archivos CSS (`scrollbottom.css`) y JavaScript (`scrollbottom.js`) del módulo, asegurando que se carguen antes del contenido de la página. |
| `header` | Alias para `displayHeader` en algunos contextos. | Igual que `displayHeader`. |
| `displayFooter` | Al final de la sección `<body>`, antes de la etiqueta de cierre `</body>`. | Se utiliza para renderizar la plantilla `footer.tpl`, que contiene la estructura HTML para el botón "Desplazarse hacia abajo". |
| `footer` | Alias para `displayFooter` en algunos contextos. | Igual que `displayFooter`. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y acceder a las últimas versiones del módulo "Desplazarse hacia abajo", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.

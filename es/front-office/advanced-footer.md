---
title: "Pie de página avanzado - Manual del comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Pie de página avanzado' de MyPresta.eu."
sidebar:
  label: "Pie de página avanzado - Manual del comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Advanced Footer en MyPresta.eu](https://mypresta.eu/modules/front-office-features/advanced-footer.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/advanced-footer/)
>
> ---


# Pie de página avanzado

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No hay requisitos de servidor inusuales.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla principal donde definirá el aspecto de su pie de página avanzado.

- **Ubicación del menú:** Back Office > Módulos > Gestor de módulos > Busque "Pie de página avanzado" > Haga clic en "Configurar".

#### **Ajustes y opciones:**

1.  **Ancho del pie de página (`advf_f_width`)**

    - **Qué hace este ajuste:** Controla el ancho total del área de su pie de página personalizado. Puede establecerlo en un valor de píxeles fijo o en un porcentaje.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en un valor de píxeles fijo (por ejemplo, `1200px`):* El pie de página siempre tendrá ese ancho exacto, centrado en la página. En pantallas muy anchas, puede haber espacio vacío a los lados. En pantallas más estrechas, podría introducir barras de desplazamiento horizontales si el valor es demasiado grande.
      - *Cuando se establece en un porcentaje (por ejemplo, `100%`):* El pie de página se estirará para llenar el ancho disponible de la pantalla, adaptándose dinámicamente. Esto generalmente se recomienda para diseños responsivos.
    - **Valor recomendado:** `100%` para un pie de página de ancho completo y responsivo, o `1200px` si el área de contenido principal de su tienda tiene un ancho fijo y desea que el pie de página coincida.
    - **Escenario / ejemplo de comerciante:** Si el área de contenido principal de su tienda tiene 1200px de ancho, establecer el ancho del pie de página en `1200px` hará que se alinee perfectamente, creando un diseño cohesivo. Si desea que el pie de página siempre abarque toda la ventana del navegador, `100%` es la opción.
2.  **Altura del pie de página (`advf_f_height`)**

    - **Qué hace este ajuste:** Define la altura mínima del área de su pie de página. Si su contenido es más alto que esto, el pie de página se expandirá automáticamente.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en un valor de píxeles específico (por ejemplo, `280px`):* El pie de página siempre tendrá al menos esta altura. Esto puede ser útil para mantener una presencia visual consistente incluso si algunas páginas tienen menos contenido en el pie de página.
      - *Cuando se deja vacío o se establece en `auto` (si está disponible):* La altura del pie de página estará determinada únicamente por su contenido.
    - **Valor recomendado:** `280px` o `300px` es un buen punto de partida para darle a su pie de página una presencia sustancial. Puede ajustarlo según la cantidad de contenido que planee colocar dentro.
    - **Escenario / ejemplo de comerciante:** Desea que su pie de página ocupe siempre un espacio notable en la parte inferior de la página, incluso si solo tiene unos pocos enlaces. Establecer una altura mínima asegura que no se vea demasiado delgado.
3.  **Color de fondo del pie de página (`advf_f_bg`)**

    - **Qué hace este ajuste:** Le permite elegir un color de fondo sólido para toda el área de su pie de página.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en un color (por ejemplo, `#333333` para gris oscuro):* El fondo del pie de página mostrará este color.
      - *Cuando se deja vacío:* El pie de página podría heredar un fondo de su tema o ser transparente.
    - **Valor recomendado:** Un color que complemente la marca de su tienda. Los colores más oscuros (como gris oscuro o negro) son comunes para los pies de página, pero un color más claro también puede funcionar según su diseño.
    - **Escenario / ejemplo de comerciante:** Su marca utiliza un tono específico de azul. Puede establecer el fondo del pie de página en este azul para reforzar la identidad de su marca.
4.  **Color del texto del pie de página (`advf_f_color`)**

    - **Qué hace este ajuste:** Establece el color predeterminado para todo el texto dentro de su pie de página, incluidos los enlaces.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en un color (por ejemplo, `#ffffff` para blanco):* Todo el texto del pie de página aparecerá en este color.
      - *Cuando se deja vacío:* El color del texto podría heredar de la configuración predeterminada de su tema, lo que podría no ser legible contra el fondo del pie de página elegido.
    - **Valor recomendado:** Un color que proporcione un buen contraste con el `Color de fondo del pie de página` elegido. Si su fondo es oscuro, elija un color de texto claro (por ejemplo, blanco, gris claro). Si su fondo es claro, elija un color de texto oscuro.
    - **Escenario / ejemplo de comerciante:** Tiene un fondo de pie de página gris oscuro. Establecer el color del texto en blanco (`#ffffff`) asegura que todos sus enlaces e información sean fácilmente legibles.
5.  **Color de los enlaces del pie de página al pasar el ratón (`advf_f_color_hover`)**

    - **Qué hace este ajuste:** Define el color al que cambiarán los enlaces de su pie de página cuando un cliente pase el ratón sobre ellos.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en un color (por ejemplo, `#cccccc` para gris claro):* Los enlaces cambiarán visualmente a este color al pasar el ratón, proporcionando retroalimentación al usuario de que el elemento es interactivo.
      - *Cuando se deja vacío:* Los enlaces podrían no tener un efecto de desplazamiento, o podrían heredar un color de desplazamiento predeterminado de su tema, que podría no coincidir con el diseño de su pie de página.
    - **Valor recomendado:** Un tono ligeramente diferente de su `Color del texto del pie de página` o un color de acento de la paleta de su marca. Debe ser perceptible pero no discordante.
    - **Escenario / ejemplo de comerciante:** Los enlaces de su pie de página son blancos. Establecer el color de desplazamiento en un azul claro (`#ADD8E6`) proporciona una interacción sutil y de marca cuando los clientes mueven el ratón sobre ellos.
6.  **URL de la imagen de fondo del pie de página (`advf_f_bg_url`)**

    - **Qué hace este ajuste:** Le permite usar una imagen como fondo para su pie de página en lugar de o además de un color sólido. Debe proporcionar la URL completa de la imagen.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se proporciona una URL válida:* La imagen aparecerá como fondo del pie de página. El `Color de fondo del pie de página` se mostrará si la imagen es transparente o si la imagen no cubre todo el pie de página.
      - *Cuando se deja vacío:* No se utilizará ninguna imagen de fondo.
    - **Valor recomendado:** Dejar vacío a menos que tenga una imagen de fondo específica y optimizada. Si se usa, asegúrese de que la imagen sea ligera y relevante.
    - **Escenario / ejemplo de comerciante:** Tiene una imagen de textura sutil que desea usar como fondo para su pie de página para agregar profundidad visual. Subiría esta imagen a su servidor y pegaría su URL aquí.
7.  **Posición de la imagen de fondo del pie de página (`advf_f_bg_pos`)**

    - **Qué hace este ajuste:** Controla cómo se posiciona una imagen de fondo (si está configurada) dentro del área del pie de página. Los valores comunes incluyen `center center`, `top left`, `bottom right`, etc.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en `center center`:* La imagen se centrará horizontal y verticalmente.
      - *Cuando se establece en `top left`:* La imagen comenzará desde la esquina superior izquierda.
    - **Valor recomendado:** `center center` para la mayoría de las imágenes, o `top left` si su imagen es un patrón destinado a comenzar desde la esquina.
    - **Escenario / ejemplo de comerciante:** Su imagen de fondo es un pequeño logotipo que desea que aparezca una vez en el centro del pie de página. Lo establecería en `center center`.
8.  **Repetición de la imagen de fondo del pie de página (`advf_f_bg_repeat`)**

    - **Qué hace este ajuste:** Determina si una imagen de fondo (si está configurada) debe repetirse y cómo para llenar el área del pie de página.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en `repeat`:* La imagen se repetirá horizontal y verticalmente.
      - *Cuando se establece en `no-repeat`:* La imagen aparecerá solo una vez.
      - *Cuando se establece en `repeat-x`:* La imagen se repetirá solo horizontalmente.
      - *Cuando se establece en `repeat-y`:* La imagen se repetirá solo verticalmente.
    - **Valor recomendado:** `no-repeat` para imágenes individuales (como un logotipo), o `repeat` si su imagen es un patrón pequeño diseñado para repetirse.
    - **Escenario / ejemplo de comerciante:** Tiene una imagen de patrón diminuta y sin costuras. Establecer esto en `repeat` hará que cubra toda el área del pie de página con ese patrón. Si es un elemento decorativo único, `no-repeat` es mejor.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Ancho del pie de página (`advf_f_width`) | `100%` | Establece el ancho total del pie de página. `100%` para ancho completo responsivo, `1200px` para ancho fijo. |
| Configuración del módulo | Altura del pie de página (`advf_f_height`) | `280px` | Define la altura mínima del pie de página. Asegura una presencia visual consistente. |
| Configuración del módulo | Color de fondo del pie de página (`advf_f_bg`) | (Color de su marca) | Establece el color de fondo sólido para el pie de página. Crucial para la marca y el contraste. |
| Configuración del módulo | Color del texto del pie de página (`advf_f_color`) | (Color contrastante) | Establece el color de texto predeterminado en el pie de página. Asegura la legibilidad contra el fondo. |
| Configuración del módulo | Color de los enlaces del pie de página al pasar el ratón (`advf_f_color_hover`) | (Acento sutil) | Define el color de los enlaces al pasar el ratón. Mejora la retroalimentación de la interacción del usuario. |
| Configuración del módulo | URL de la imagen de fondo del pie de página (`advf_f_bg_url`) | Dejar vacío | URL de una imagen para usar como fondo del pie de página. Agrega textura visual o marca. |
| Configuración del módulo | Posición de la imagen de fondo del pie de página (`advf_f_bg_pos`) | `center center` | Cómo se posiciona la imagen de fondo. `center center` para la mayoría de las imágenes individuales. |
| Configuración del módulo | Repetición de la imagen de fondo del pie de página (`advf_f_bg_repeat`) | `no-repeat` | Cómo se repite la imagen de fondo. `no-repeat` para imágenes individuales, `repeat` para patrones. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis cambios en el pie de página no aparecen en el front office.**
**R1:** Esto suele ser un problema de caché.
\* Vaya a **Parámetros avanzados > Rendimiento** en el Back Office de su PrestaShop.
\* Haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
\* Si utiliza un módulo de caché de terceros o caché a nivel de servidor (como Varnish), borre también esas cachés.
\* Además, intente borrar la caché de su navegador (Ctrl+F5 o Cmd+Shift+R).

**P2: El pie de página se ve diferente en dispositivos móviles que en el escritorio.**
**R2:** Esto es esperado y generalmente algo bueno. Los temas modernos de PrestaShop son responsivos, lo que significa que adaptan el diseño a diferentes tamaños de pantalla. La configuración del módulo (como `Ancho del pie de página: 100%`) está diseñada para funcionar con esto. Si elementos específicos se ven rotos, podría ser un conflicto con el CSS de su tema.
\* **Solución de problemas:** Revise el CSS específico para móviles de su tema. Si ha agregado contenido HTML personalizado al pie de página, asegúrese de que ese contenido también sea responsivo. Es posible que necesite un webmaster para inspeccionar el CSS.

**P3: ¿Cómo agrego contenido real (enlaces, texto, imágenes) a este pie de página avanzado?**
**R3:** Este módulo proporciona principalmente el *marco de estilo* (fondo, colores, dimensiones) para su pie de página. El *contenido* del pie de página se gestiona típicamente mediante los hooks del pie de página de su tema de PrestaShop (como `displayFooter`) o mediante otros módulos diseñados para bloques de contenido (por ejemplo, un módulo de bloque HTML personalizado, o el módulo de Lista de enlaces integrado de PrestaShop).
\* **Solución:** Después de configurar el estilo del Pie de página avanzado, deberá usar las opciones de su tema u otros módulos de contenido para poblar el hook `displayFooter` con los enlaces, texto e imágenes deseados. El módulo Pie de página avanzado aplicará entonces su estilo a ese contenido.

**P4: Los colores que configuré no parecen aplicarse a todos los elementos de mi pie de página.**
**R4:** Esto puede suceder si su tema tiene reglas CSS muy específicas que anulan los estilos del módulo.
\* **Solución de problemas:** El módulo aplica un estilo general al pie de página. Si su tema tiene reglas más específicas (por ejemplo, para `ul li a` dentro del pie de página), esas podrían tener prioridad. Es posible que deba consultar a un webmaster para agregar CSS personalizado a su tema para anular elementos específicos, o ajustar la configuración de su tema si tiene una sección dedicada a la personalización del pie de página.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo Pie de página avanzado es un módulo estándar de PrestaShop centrado principalmente en el estilo del front office. Aprovecha el sistema de configuración de PrestaShop (`Configuration::updateValue`) para almacenar sus ajustes y se engancha a `displayFooter` para inyectar su CSS y JavaScript personalizados. No introduce nuevas tablas de base de datos ni ObjectModels complejos, lo que lo hace ligero y centrado en su tarea principal: la personalización del pie de página. El módulo utiliza un método `getContent()` para su configuración de back office, renderizando un formulario estándar de PrestaShop.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front Office**: Ninguno. El módulo se engancha directamente a `displayFooter` y `footer` para renderizar su contenido y aplicar estilos.
- **Controladores de administración de Back Office**: Ninguno. Toda la configuración se maneja dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

- No se definen clases personalizadas ni ObjectModels en el directorio `classes/`. Toda la lógica está contenida dentro del archivo principal del módulo `advfooter.php`.

### 4.4 Activos de JavaScript (`views/js/`)

- `advfooter/js/advajax.js`:
  - **Alcance:** Back office.
  - **Responsabilidad:** Probablemente maneja las solicitudes AJAX relacionadas con el guardado de la configuración del módulo sin una recarga completa de la página, o proporciona retroalimentación dinámica dentro del formulario de configuración.
- `advfooter/js/foscript.js`:
  - **Alcance:** Front office.
  - **Responsabilidad:** Este script contendría cualquier lógica del lado del cliente o comportamiento dinámico específico del pie de página avanzado en el lado del cliente. Esto podría incluir ajustes responsivos, efectos de desplazamiento específicos no manejados por CSS, o interacciones con contenido incrustado.
- `advfooter/js/jscolor/jscolor.js`:
  - **Alcance:** Back office.
  - **Responsabilidad:** Esta es una biblioteca JavaScript de terceros para proporcionar un widget de selección de color en el Back Office. Se utiliza para permitir a los comerciantes seleccionar visualmente colores para el fondo, el texto y los efectos de desplazamiento.
- `advfooter/js/script.js`:
  - **Alcance:** Back office.
  - **Responsabilidad:** Script de propósito general para la página de configuración del Back Office del módulo. Podría inicializar el selector `jscolor`, manejar la validación del formulario u otras mejoras de la interfaz de usuario para la interfaz de administración.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `advfooter/css/fancybox.css`:
  - **Alcance:** Front office (potencialmente, si el módulo utiliza Fancybox para cualquier contenido o imagen incrustada).
  - **Responsabilidad:** Proporciona estilo para la biblioteca lightbox Fancybox, que se usa comúnmente para mostrar imágenes, videos u otro contenido en una superposición modal. Su presencia sugiere que el módulo podría admitir dicha funcionalidad, o se incluye como una utilidad general.
  - **Selectores de clase CSS clave:** `.fancybox-overlay`, `.fancybox-wrap`, `.fancybox-inner`, etc. Los desarrolladores pueden anularlos para personalizar la apariencia del lightbox.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:

  - `advfooter/footer.tpl`:
    - **Hook:** `displayFooter` (y potencialmente `footer` para temas más antiguos).
    - **Salida:** Esta plantilla es responsable de renderizar la estructura principal del pie de página avanzado. Probablemente contendrá un elemento HTML `div` o `footer` con estilos en línea dinámicos o atributos de clase poblados por la configuración del módulo (por ejemplo, `width`, `height`, `background-color`, `background-image`, `color`). Actúa como el contenedor para cualquier contenido que otros módulos o el tema coloquen en el hook `displayFooter`.
- **Plantillas de administración (`views/templates/admin/`)**: Ninguna. El formulario de configuración probablemente se renderiza directamente dentro de `getContent()` usando `HelperForm` de PrestaShop o similar.
- **Plantillas de Front Office (`views/templates/front/`)**: Ninguna.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo no crea ninguna tabla SQL personalizada.
  - La configuración se almacena en la tabla `ps_configuration` utilizando las claves: `ADVF_F_WIDTH`, `ADVF_F_HEIGHT`, `ADVF_F_BG`, `ADVF_F_COLOR`, `ADVF_F_COLOR_HOVER`, `ADVF_F_BG_URL`, `ADVF_F_BG_POS`, `ADVF_F_BG_REPEAT`.
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página. | Se utiliza para registrar activos CSS y JavaScript (`foscript.js`, `fancybox.css`) para el front office, y potencialmente inyectar estilos en línea basados en la configuración del módulo. |
| `displayBackOfficeHeader` | Se ejecuta en la sección `<head>` de cada página del Back Office. | Se utiliza para registrar activos CSS y JavaScript (`advajax.js`, `jscolor.js`, `script.js`) para la página de configuración del módulo. |
| `displayFooter` | Se ejecuta en la parte inferior de la página, típicamente antes de la etiqueta de cierre `</body>`. | Renderiza la plantilla `footer.tpl`, que aplica el estilo personalizado y actúa como contenedor para el contenido del pie de página. |
| `footer` | (PrestaShop 1.6 y anteriores, o para compatibilidad con temas específicos) | Similar a `displayFooter`, se utiliza para renderizar el contenido del pie de página. El módulo probablemente se registra en ambos para una compatibilidad más amplia. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Allí encontrará sus módulos comprados y acceso directo a los recursos de soporte.

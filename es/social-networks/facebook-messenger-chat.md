---
title: "Chat de Facebook Messenger - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Chat de Facebook Messenger de MyPresta.eu."
sidebar:
  label: "Chat de Facebook Messenger - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook Messenger chat en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-messenger-chat.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-messenger-chat/)
>
> ---


# Chat de Facebook Messenger

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y normalmente están disponibles en todos los entornos de alojamiento modernos. No se necesitan extensiones especiales para este módulo más allá de los requisitos estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal de su módulo de chat de Facebook Messenger. Aquí encontrará todas las opciones para personalizar cómo aparece y funciona el chat en su tienda.

- **Qué hace este ajuste:** Este es un ajuste general para que los módulos de MyPresta.eu comprueben si hay actualizaciones.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (Activado):* El módulo comprobará periódicamente MyPresta.eu en busca de nuevas versiones.
  - *Cuando está deshabilitado (Desactivado):* El módulo no comprobará si hay actualizaciones.
- **Valor recomendado:** **Activado** (Siempre es bueno mantenerse actualizado para la seguridad y las nuevas funciones).
- **Escenario / ejemplo del comerciante:** Mantener esto activado garantiza que se le notifique cuando haya una nueva versión con correcciones de errores o nuevas funciones, lo que ayuda a que su tienda se mantenga actualizada y segura.

---

- **Qué hace este ajuste:** Esta opción le permite elegir entre dos tipos de integración de chat de Facebook: un chat simple de página de Facebook o el chat más avanzado de Facebook Messenger.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "Chat de página de Facebook":* Aparecerá un widget de chat más simple, principalmente para enviar mensajes a su página de Facebook.
  - *Cuando se establece en "Chat de Facebook Messenger":* Aparecerá el widget de chat de Facebook Messenger con todas las funciones, ofreciendo una experiencia de conversación más rica, incluidos mensajes de bienvenida y potencialmente funciones más avanzadas de Facebook.
- **Valor recomendado:** **Chat de Facebook Messenger** (Ofrece una mejor experiencia de usuario y más funciones).
- **Escenario / ejemplo del comerciante:** Si desea la experiencia completa e interactiva de Messenger con mensajes de bienvenida, elija "Chat de Facebook Messenger". Si prefiere un remitente de mensajes muy básico y ligero, "Chat de página de Facebook" podría ser suficiente.

---

- **Qué hace este ajuste:** Este ajuste ayuda a mejorar las puntuaciones de rendimiento de su tienda en herramientas como Google PageSpeed Insights al evitar que el chat de Facebook se cargue inmediatamente, lo que a veces puede bloquear la representación de su página.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (Activado):* El script de chat de Facebook se cargará con un ligero retraso o de forma no bloqueante, lo que puede mejorar sus puntuaciones de Google PageSpeed.
  - *Cuando está deshabilitado (Desactivado):* El script de chat de Facebook se cargará normalmente, lo que podría afectar ligeramente las métricas de rendimiento de carga de la página.
- **Valor recomendado:** **Activado** (Recomendado para un mejor SEO y experiencia de usuario).
- **Escenario / ejemplo del comerciante:** Si le preocupan las métricas de rendimiento de su tienda y desea asegurarse de que el chat no las afecte negativamente, habilite esta opción.

---

- **Qué hace este ajuste:** Esto controla si el SDK (Kit de desarrollo de software) de la aplicación de Facebook se incluye en su sitio web. El SDK es necesario para la funcionalidad completa del chat de Facebook Messenger, especialmente para funciones como la identificación de usuarios que han iniciado sesión.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (Activado):* Se cargará el SDK de Facebook, lo que habilitará todas las funciones de chat de Messenger.
  - *Cuando está deshabilitado (Desactivado):* Algunas funciones avanzadas de Messenger, particularmente las relacionadas con la identificación de usuarios y los saludos personalizados, podrían no funcionar correctamente.
- **Valor recomendado:** **Activado** (Requerido para la funcionalidad completa del chat de Messenger).
- **Escenario / ejemplo del comerciante:** Si desea que el chat reconozca si un cliente ha iniciado sesión en Facebook y muestre un saludo personalizado, debe habilitar esta opción.

---

- **Qué hace este ajuste:** Este es su identificador único para su aplicación de Facebook. Debe crear una aplicación de Facebook en el sitio web de desarrolladores de Facebook para obtener este ID. Vincula su sitio web a su página de Facebook para funciones avanzadas de Messenger.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce correctamente:* Habilita la funcionalidad completa del chat de Facebook Messenger, incluidos los saludos personalizados y una identificación de usuario potencialmente más precisa.
  - *Cuando es incorrecto o está vacío:* El chat de Messenger podría no funcionar correctamente o no funcionar en absoluto.
- **Valor recomendado:** Su **ID de aplicación de Facebook** real. (Dejar vacío si "Incluir SDK de aplicación de Facebook" está desactivado).
- **Escenario / ejemplo del comerciante:** Para usar las funciones avanzadas de chat de Messenger, deberá ir a [developers.facebook.com](https://developers.facebook.com/), crear una aplicación, vincularla a su página de Facebook y luego copiar el ID de la aplicación aquí.

---

- **Qué hace este ajuste:** Esto le permite especificar el idioma para la interfaz de chat de Facebook Messenger.
- **Efecto de cambiar este ajuste:**
  - *Cuando se selecciona un código de idioma:* El widget de chat mostrará texto (como "Envíanos un mensaje") en el idioma elegido.
  - *Cuando se deja vacío o es incorrecto:* El chat podría usar el inglés por defecto o el idioma del navegador.
- **Valor recomendado:** Seleccione el idioma principal de su tienda, por ejemplo, `es_ES` para español (España), `en_US` para inglés (Estados Unidos), `fr_FR` para francés (Francia).
- **Escenario / ejemplo del comerciante:** Si su tienda atiende principalmente a clientes en Alemania, configurar esto en `de_DE` garantizará que la interfaz de chat esté en alemán, lo que la hará más fácil de usar para sus clientes locales.

---

- **Qué hace este ajuste:** Esta es la URL de su página de fans de Facebook. Esto es crucial ya que le dice al widget de chat dónde enviar los mensajes.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce correctamente:* Los mensajes enviados a través del widget de chat irán directamente a la bandeja de entrada de su página de Facebook.
  - *Cuando es incorrecto o está vacío:* El widget de chat no podrá conectarse a su página y los mensajes no se entregarán.
- **Valor recomendado:** La URL completa de su página de fans de Facebook, por ejemplo, `https://www.facebook.com/MyPresta.eu`.
- **Escenario / ejemplo del comerciante:** Si su página de Facebook es `https://www.facebook.com/MiTiendaImpresionante/`, introduciría esa URL aquí para que los clientes puedan comunicarse con usted.

---

- **Qué hace este ajuste:** Este es el mensaje inicial que se muestra a los clientes que ya han iniciado sesión en Facebook cuando abren el chat.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece:* Los clientes que han iniciado sesión verán este saludo personalizado, lo que hará que la interacción sea más acogedora.
  - *Cuando está vacío:* Se podría usar un saludo predeterminado de Facebook, o no aparecerá ningún saludo.
- **Valor recomendado:** Un saludo amable y conciso, por ejemplo, "Hola [Nombre del cliente], ¿cómo podemos ayudarte hoy?".
- **Escenario / ejemplo del comerciante:** Podría establecer esto en "¡Bienvenido de nuevo! ¿Cómo podemos ayudarte con tus compras hoy?" para que los clientes que regresan se sientan valorados.

---

- **Qué hace este ajuste:** Este es el mensaje inicial que se muestra a los clientes que NO han iniciado sesión en Facebook cuando abren el chat.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece:* Los clientes no registrados verán este saludo, animándolos a iniciar una conversación.
  - *Cuando está vacío:* Se podría usar un saludo predeterminado de Facebook, o no aparecerá ningún saludo.
- **Valor recomendado:** Un mensaje claro y atractivo, por ejemplo, "¡Hola! Estamos aquí para ayudarte. ¡Pregúntanos lo que quieras!".
- **Escenario / ejemplo del comerciante:** Para los nuevos visitantes, podría usar "¡Hola! ¿Tienes alguna pregunta sobre nuestros productos? ¡Chatea con nosotros!".

---

- **Qué hace este ajuste:** Este es el ID numérico de su página de Facebook. Puede encontrarlo en la sección "Información" de su página de Facebook o utilizando una herramienta de búsqueda de ID de página de Facebook. Es esencial para vincular el widget de chat a su página específica.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce correctamente:* El widget de chat identificará y se conectará correctamente a su página de Facebook.
  - *Cuando es incorrecto o está vacío:* El widget de chat no funcionará, ya que no sabrá a qué página conectarse.
- **Valor recomendado:** Su **ID de página de Facebook** real.
- **Escenario / ejemplo del comerciante:** Si el ID de su página de Facebook es `123456789012345`, introduciría ese número aquí. Esto es distinto del ID de la aplicación.

---

- **Qué hace este ajuste:** Esto controla la posición del widget de chat en su sitio web.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "Izquierda":* El icono/panel de chat aparecerá en el lado inferior izquierdo de su pantalla.
  - *Cuando se establece en "Derecha":* El icono/panel de chat aparecerá en el lado inferior derecho de su pantalla.
- **Valor recomendado:** **Derecha** (Esta es una posición común y a menudo menos intrusiva, ya que muchos sitios web tienen navegación u otros elementos a la izquierda).
- **Escenario / ejemplo del comerciante:** Si la navegación principal de su sitio web o un banner crucial está a la izquierda, elegiría "Derecha" para evitar oscurecerlo.

---

- **Qué hace este ajuste:** Este es el texto que aparece como título de la ventana de chat o del panel deslizante antes de que comience una conversación.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece:* Los clientes verán este título, indicando claramente para qué sirve el chat.
  - *Cuando está vacío:* Se podría usar un título predeterminado, o no aparecerá ningún título, lo que puede ser confuso.
- **Valor recomendado:** Un título claro y atractivo, por ejemplo, "¡Chatea con nosotros!", "Soporte al cliente" o "¿Preguntas?".
- **Escenario / ejemplo del comerciante:** Establecer esto en "¿Necesitas ayuda?" deja claro a los clientes que pueden obtener asistencia a través del chat.

---

- **Qué hace este ajuste:** Esto le permite personalizar el color del texto dentro del widget de chat de Facebook.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce un código de color:* El texto del widget de chat se mostrará en el color elegido.
  - *Cuando está vacío:* Se utilizará el color de texto predeterminado de Facebook Messenger.
- **Valor recomendado:** Elija un color que contraste bien con el color de fondo y que coincida con su marca. Utilice un código de color hexadecimal (por ejemplo, `#FFFFFF` para blanco, `#000000` para negro).
- **Escenario / ejemplo del comerciante:** Si los colores de su marca son azul oscuro y blanco, podría establecer el color de la fuente en `#FFFFFF` (blanco) si el color de fondo es azul oscuro.

---

- **Qué hace este ajuste:** Esto le permite personalizar el color de fondo del widget de chat de Facebook.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce un código de color:* El fondo del widget de chat se mostrará en el color elegido.
  - *Cuando está vacío:* Se utilizará el color de fondo predeterminado de Facebook Messenger.
- **Valor recomendado:** Elija un color que complemente el diseño de su tienda. Utilice un código de color hexadecimal (por ejemplo, `#F0F2F5` para gris claro, `#3B5998` para azul Facebook).
- **Escenario / ejemplo del comerciante:** Para integrar el chat sin problemas con el diseño de su tienda, podría establecer el color de fondo en un gris sutil o un color de su paleta de marca.

---

- **Qué hace este ajuste:** Esto le permite personalizar el color de acento principal del chat de Facebook Messenger, como el botón de enviar o los elementos activos.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce un código de color:* Los elementos interactivos clave del widget de chat se mostrarán en el color elegido.
  - *Cuando está vacío:* Se utilizará el color de acento predeterminado de Facebook Messenger (normalmente azul Facebook).
- **Valor recomendado:** Elija un color que se alinee con el color de acento principal o secundario de su marca. Utilice un código de color hexadecimal (por ejemplo, `#1877F2` para azul Facebook, o el color de llamada a la acción de su marca).
- **Escenario / ejemplo del comerciante:** Si los botones de llamada a la acción de su tienda son verdes, establecer esto en un verde similar (`#28A745`) hará que el widget de chat se sienta más integrado con su sitio.

---

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Actualizaciones de MyPresta.eu | Activado | Habilita las comprobaciones de actualización del módulo para seguridad y funciones. |
| Configuración del módulo | Tipo de chat | Chat de Facebook Messenger | Selecciona entre el chat básico de la página de Facebook y la experiencia completa de Messenger. |
| Configuración del módulo | Deshabilitar chat para Google Insights | Activado | Mejora las puntuaciones de PageSpeed al retrasar la carga del script de chat. |
| Configuración del módulo | Incluir SDK de aplicación de Facebook | Activado | Habilita funciones avanzadas de Messenger como saludos personalizados. |
| Configuración del módulo | Su ID de APP | Su ID de aplicación de Facebook | Vincula su sitio web a su aplicación de Facebook para la funcionalidad completa de Messenger. |
| Configuración del módulo | Códigos de idioma de la APP de Facebook | `es_ES` (o el idioma de su tienda) | Establece el idioma para la interfaz de chat. |
| Configuración del módulo | URL de la página de fans de Facebook (receptor de mensajes) | URL de su página de Facebook | Dirige los mensajes de los clientes a la bandeja de entrada de su página de Facebook. |
| Configuración del módulo | Mensaje de bienvenida para usuarios registrados | "Hola [Nombre del cliente], ¿cómo podemos ayudarte hoy?" | Saludo personalizado para usuarios de Facebook que han iniciado sesión. |
| Configuración del módulo | Mensaje de bienvenida para usuarios no registrados | "¡Hola! Estamos aquí para ayudarte. ¡Pregúntanos lo que quieras!" | Mensaje de invitación para usuarios que no han iniciado sesión en Facebook. |
| Configuración del módulo | Su ID de página de Facebook | Su ID de página de Facebook | Identifica su página de Facebook específica para la conexión del chat. |
| Configuración del módulo | ¿Dónde mostrar? | Derecha | Posiciona el widget de chat en el lado izquierdo o derecho de la pantalla. |
| Configuración del módulo | Título del panel deslizante | "¡Chatea con nosotros!" | Texto que se muestra como título de la ventana de chat. |
| Configuración del módulo | Color de fuente del chat de Facebook | `#000000` (negro) o el color de su marca | Personaliza el color del texto dentro del widget de chat. |
| Configuración del módulo | Color de fondo del chat de Facebook | `#F0F2F5` (gris claro) o el color de su marca | Personaliza el color de fondo del widget de chat. |
| Configuración del módulo | Color de Facebook Messenger | `#1877F2` (azul Facebook) o el color de su marca | Personaliza el color de acento de los elementos interactivos del chat. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: El widget de chat no aparece en mi tienda. ¿Qué debo hacer?**
R:

1. **Verifique el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que el módulo "Chat de Facebook Messenger" esté instalado y habilitado.
2. **Verifique la configuración:** Revise todos los ajustes en la página de configuración del módulo, especialmente "Su ID de APP", "URL de la página de fans de Facebook" y "Su ID de página de Facebook". Incluso un solo carácter incorrecto puede impedir que funcione.
3. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los archivos antiguos en caché impiden que se muestren los nuevos módulos.
4. **Compatibilidad del tema:** Si está utilizando un tema muy personalizado, podría haber un conflicto. Cambie temporalmente al tema predeterminado de PrestaShop para ver si aparece el chat. Si lo hace, su tema podría requerir un pequeño ajuste.

**P: Mis mensajes de bienvenida no aparecen, o el chat no reconoce a los usuarios que han iniciado sesión.**
R:

1. **Habilitar SDK:** Asegúrese de que "Incluir SDK de aplicación de Facebook" esté configurado en **Activado**.
2. **Proporcionar ID de APP:** Asegúrese de que "Su ID de APP" esté introducido correctamente. Debe crear una aplicación de Facebook y vincularla a su página para obtener esto.
3. **Inicio de sesión en Facebook:** El cliente debe haber iniciado sesión en Facebook en su navegador para que el saludo personalizado funcione.

**P: El widget de chat se ve fuera de lugar o no coincide con el diseño de mi tienda.**
R:

1. **Utilice la configuración de color:** Vaya a la configuración del módulo y ajuste "Color de fuente del chat de Facebook", "Color de fondo del chat de Facebook" y "Color de Facebook Messenger" para que coincidan con la paleta de su marca.
2. **Posicionamiento:** Experimente con el ajuste "¿Dónde mostrar?" (Izquierda/Derecha) para encontrar la posición menos intrusiva para su sitio.

**P: ¿Cómo encuentro mi ID de página de Facebook y mi ID de aplicación?**
R:

- **ID de página de Facebook:** Vaya a su página de Facebook, haga clic en "Información" en el menú de la izquierda. Desplácese hacia abajo y debería ver "ID de página".
- **ID de aplicación de Facebook:** Debe crear una cuenta de desarrollador de Facebook y luego crear una nueva aplicación. Una vez creada, el ID de la aplicación será visible en el panel de control de su aplicación. Asegúrese de vincular esta aplicación a su página de Facebook.

**P: ¿Este módulo ralentizará mi sitio web?**
R: El SDK de Facebook a veces puede afectar los tiempos de carga de la página. Sin embargo, el módulo incluye una opción "Deshabilitar chat para Google Insights". Habilitar esto puede ayudar a mitigar los impactos en el rendimiento al cargar el script de forma no bloqueante, mejorando sus puntuaciones de PageSpeed.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura

El módulo `Facebook Messenger chat` (`fbchat`) es un módulo estándar de PrestaShop que sigue un patrón similar a MVC dentro del alcance del módulo. Principalmente aprovecha el sistema de hooks de PrestaShop para inyectar JavaScript y HTML en el front-office. La configuración se gestiona a través del método `getContent()` en la clase principal del módulo, almacenando los ajustes en `ps_configuration`. El módulo se integra directamente con el SDK de la plataforma de Facebook Messenger, basándose en recursos externos de Facebook para su funcionalidad principal.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la lógica se maneja dentro del archivo principal del módulo (`fbchat.php`) y se inyecta a través de hooks.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** define ninguna clase personalizada o instancias de `ObjectModel` en el directorio `classes/`. Todo el manejo de datos se realiza directamente a través de la clase `Configuration` para la configuración.

### 4.4 Activos de JavaScript (`views/js/`)

- **`fbchat/jscolor/jscolor.js`**

  - **Alcance:** Back-office (página de configuración de administración).
  - **Propósito:** Esta es una biblioteca JavaScript de terceros para un selector de color. Se utiliza en la página de configuración del módulo para proporcionar una interfaz fácil de usar para seleccionar colores para el widget de chat (por ejemplo, color de fuente, color de fondo).
  - **Interacción:** Adjunta la funcionalidad del selector de color a campos de entrada específicos en el formulario de administración.
- **`fbchat/js/fbchat.js`**

  - **Alcance:** Front-office.
  - **Propósito:** Este JavaScript personalizado maneja la carga dinámica y la inicialización del widget de chat de Facebook Messenger. Contiene lógica para cargar condicionalmente el SDK de Facebook y el chat de Messenger según la configuración del módulo y las posibles banderas de optimización del rendimiento.
  - **Interacción:**
    - Comprueba la configuración `fbchat_hack` para determinar si la carga retrasada para Google Insights está habilitada.
    - Crea y adjunta dinámicamente el script del SDK de Facebook (`sdk.js`) al `<body>` si `fbchat_appsdk` está habilitado.
    - Inicializa el plugin `FB.CustomerChat` con parámetros obtenidos de la configuración del módulo (por ejemplo, `page_id`, `app_id`, `theme_color`, `logged_in_greeting`, `logged_out_greeting`, `locale`).
    - Maneja el posicionamiento del widget de chat según `fbchat_side`.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`fbchat/css.css`**

  - **Alcance:** Back-office (página de configuración de administración).
  - **Propósito:** Contiene estilos específicos para el formulario de configuración del módulo en el Back Office de PrestaShop. Esto podría incluir estilos para campos de entrada, botones o elementos de diseño personalizados dentro de la salida de `getContent()`.
  - **Selectores clave:** Probablemente apunta a elementos dentro del formulario de configuración del módulo.
- **`fbchat/css/fbchat_left.css`**

  - **Alcance:** Front-office.
  - **Propósito:** Proporciona ajustes de estilo para el widget de chat de Facebook Messenger cuando su posición se establece en el lado "Izquierdo" de la pantalla. Esto podría incluir propiedades CSS `right` o `left` para controlar su posición fija.
  - **Selectores clave:** Apunta al contenedor principal del chat o a su envoltorio para garantizar una alineación correcta a la izquierda.
- **`fbchat/css/fbchat_right.css`**

  - **Alcance:** Front-office.
  - **Propósito:** Proporciona ajustes de estilo para el widget de chat de Facebook Messenger cuando su posición se establece en el lado "Derecho" de la pantalla. Esto podría incluir propiedades CSS `right` o `left` para controlar su posición fija.
  - **Selectores clave:** Apunta al contenedor principal del chat o a su envoltorio para garantizar una alineación correcta a la derecha.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`fbchat/admin-script.tpl`**

  - **Alcance:** Back-office (página de configuración de administración).
  - **Propósito:** Esta plantilla probablemente se utiliza para inyectar código JavaScript (por ejemplo, para la inicialización del selector de color de `jscolor.js`) o estilos específicos en la página de configuración del módulo. Se renderiza dentro del método `getContent()`.
  - **Variables:** Puede recibir variables de configuración para establecer dinámicamente los valores iniciales del selector de color.
- **`fbchat/fbchat.tpl`**

  - **Alcance:** Front-office.
  - **Propósito:** Esta es la plantilla principal del front-office responsable de renderizar la estructura HTML necesaria y la inicialización de JavaScript para el widget de chat de Facebook Messenger. Normalmente se engancha a `displayFooter` o `displayHeader`.
  - **Variables:** Recibe todas las variables de configuración necesarias de los métodos `hookDisplayFooter` o `hookDisplayHeader` del módulo, como `fbchat_fanid`, `fbchat_appid`, `fbchat_theme`, `fbchat_bg`, `fbchat_color`, `fbchat_langarray`, `fbchat_hello_logged`, `fbchat_hello_unlogged`, `fbchat_hack`, `fbchat_appsdk`, `fbchat_type`, `fbchat_side`.
  - **Salida:** Genera el elemento `<div class="fb-customerchat">` y la etiqueta `<script>` para la inicialización del SDK de Facebook.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:

  - Este módulo no crea ninguna tabla SQL personalizada.
  - Todos los ajustes de configuración se almacenan en la tabla `ps_configuration` utilizando claves como `mypresta_updates`, `fbchat_theme`, `fbchat_bg`, `fbchat_color`, `fbchat_fanpage`, `fbchat_positions`, `fbchat_hack`, `fbchat_appsdk`, `fbchat_type`, `fbchat_fanid`, `fbchat_appid`, `fbchat_title`, `fbchat_langarray`, `fbchat_hello_logged`, `fbchat_hello_unlogged`, `fbchat_side`.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página del front-office. | Se utiliza para incluir archivos CSS (`fbchat_left.css`, `fbchat_right.css`) y potencialmente algo de JavaScript inicial si es necesario al principio de la carga de la página. |
| `displayFooter` | Se ejecuta justo antes de la etiqueta de cierre `</body>` de cada página del front-office. | Este es el hook principal para renderizar la plantilla `fbchat.tpl`, que incluye el HTML del chat de Facebook Messenger e inicializa el script `fbchat.js`. Colocarlo aquí asegura que el contenido principal de la página se cargue primero, mejorando el rendimiento percibido. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y las últimas versiones del módulo "Chat de Facebook Messenger", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad o integración del módulo.

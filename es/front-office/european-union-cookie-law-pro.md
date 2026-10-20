---
title: "Ley de Cookies de la Unión Europea Pro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Ley de Cookies de la Unión Europea Pro de MyPresta.eu."
sidebar:
  label: "Ley de Cookies de la Unión Europea Pro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo European Union Cookie Law Pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/european-union-cookie-law-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/european-union-cookie-law-pro/)
>
> ---


# Ley de Cookies de la Unión Europea Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Ley de Cookies de la Unión Europea Pro)

Esta es la pantalla de configuración principal donde definirá la apariencia, el contenido y el comportamiento de su aviso de cookies. El módulo ofrece una función de vista previa en vivo, lo que le permite ver sus cambios en tiempo real dentro del back office antes de guardar.

#### **Configuración General**

- **Habilitar Módulo de Ley de Cookies:**

  - **Qué hace esta configuración:** Este es el interruptor principal para activar o desactivar el aviso de cookies en toda su tienda.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado (SÍ):* El aviso de cookies se mostrará a los visitantes según sus otras configuraciones.
    - *Cuando está deshabilitado (NO):* El aviso de cookies no aparecerá en su tienda y este módulo no recopilará ningún consentimiento de cookies.
  - **Valor recomendado:** SÍ (para garantizar el cumplimiento legal).
  - **Escenario / ejemplo del comerciante:** Lo deshabilitaría temporalmente durante el mantenimiento o si está probando una solución de cookies diferente.
- **Tiempo de Expiración de la Cookie (en días):**

  - **Qué hace esta configuración:** Determina cuánto tiempo se recuerda el consentimiento de cookies de un usuario en su tienda. Después de este período, se le solicitará nuevamente el consentimiento al usuario.
  - **Efecto de cambiar esta configuración:**
    - *Cuando se establece en 365:* El consentimiento de un usuario será válido por un año.
    - *Cuando se establece en 30:* El consentimiento será válido por un mes.
  - **Valor recomendado:** 365 (un año) es un período común y razonable para la mayoría de las regulaciones. Consulte las leyes locales para conocer los requisitos específicos.
  - **Escenario / ejemplo del comerciante:** Si sus regulaciones locales requieren volver a solicitar el consentimiento cada 6 meses, lo establecería en 180.
- **Mostrar en Dispositivos Móviles:**

  - **Qué hace esta configuración:** Controla si el aviso de cookies se muestra a los usuarios que navegan en teléfonos inteligentes y tabletas.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado (SÍ):* El aviso de cookies aparecerá en dispositivos móviles, adaptando su diseño para pantallas más pequeñas.
    - *Cuando está deshabilitado (NO):* Los usuarios móviles no verán el aviso de cookies.
  - **Valor recomendado:** SÍ (para un cumplimiento total en todos los dispositivos).
  - **Escenario / ejemplo del comerciante:** Siempre debe habilitar esto, ya que los usuarios móviles están sujetos a las mismas leyes de privacidad.
- **Mostrar solo a Visitantes de Países de la UE:**

  - **Qué hace esta configuración:** Si está habilitado, el aviso de cookies solo se mostrará a los visitantes cuya dirección IP indique que están navegando desde un estado miembro de la UE.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado (SÍ):* Los visitantes no pertenecientes a la UE no verán el banner.
    - *Cuando está deshabilitado (NO):* Todos los visitantes, independientemente de su ubicación, verán el banner.
  - **Valor recomendado:** Depende de su público objetivo y asesoramiento legal. Si solo atiende a clientes de la UE, SÍ podría ser apropiado. Si atiende a una audiencia global y quiere estar seguro, NO es mejor.
  - **Escenario / ejemplo del comerciante:** Una tienda australiana que atiende principalmente a clientes australianos podría habilitar esto para evitar mostrar el banner a su audiencia principal, mientras sigue cumpliendo con los pocos visitantes de la UE. Una tienda global podría deshabilitarlo para ser universalmente compatible.

#### **Contenido y Enlaces**

- **Mensaje de Ley de Cookies:**

  - **Qué hace esta configuración:** Este es el texto principal que se muestra dentro del aviso de cookies, informando a los usuarios sobre el uso de cookies. Puede usar un editor de texto enriquecido para formatearlo.
  - **Efecto de cambiar esta configuración:** El texto que ingrese aquí será el mensaje principal que leerán sus clientes.
  - **Valor recomendado:** Un mensaje claro y conciso como "Este sitio web utiliza cookies para garantizar que obtenga la mejor experiencia en nuestro sitio web. [Más información]"
  - **Escenario / ejemplo del comerciante:** Podría incluir información sobre los tipos de cookies utilizadas (por ejemplo, "Utilizamos cookies para análisis y para mejorar su experiencia de compra").
- **Texto del Botón "Aceptar":**

  - **Qué hace esta configuración:** Define el texto que se muestra en el botón que los usuarios hacen clic para aceptar las cookies.
  - **Efecto de cambiar esta configuración:** Cambia la etiqueta del botón de aceptación.
  - **Valor recomendado:** "Aceptar", "Entendido", "OK", "Lo entiendo".
  - **Escenario / ejemplo del comerciante:** Podría usar "Aceptar y Continuar" para animar a los usuarios a continuar.
- **Texto del Botón "Más Información":**

  - **Qué hace esta configuración:** Define el texto que se muestra en el botón que los usuarios hacen clic para obtener más información sobre su política de cookies.
  - **Efecto de cambiar esta configuración:** Cambia la etiqueta del botón de información.
  - **Valor recomendado:** "Más información", "Info", "Política de Privacidad".
  - **Escenario / ejemplo del comerciante:** Podría usar "Configuración de Cookies" si tiene un sistema detallado de gestión de preferencias.
- **Enlace a la Página de Política de Privacidad:**

  - **Qué hace esta configuración:** Especifica la URL donde los usuarios pueden encontrar su política de privacidad o de cookies completa. Este enlace se adjuntará al botón "Más Información" o a una parte específica de su mensaje.
  - **Efecto de cambiar esta configuración:** Cuando los usuarios hagan clic en el botón "Más Información", serán redirigidos a esta URL.
  - **Valor recomendado:** La URL completa de su página CMS (por ejemplo, `https://tutienda.com/content/3-terminos-y-condiciones`).
  - **Escenario / ejemplo del comerciante:** Crea una página CMS dedicada en PrestaShop (Diseño > Páginas) para su "Política de Cookies" y la enlaza aquí.

#### **Opciones de Visualización y Estilo**

- **Posición del Aviso de Cookies:**

  - **Qué hace esta configuración:** Determina dónde aparece el aviso de cookies en su sitio web.
  - **Efecto de cambiar esta configuración:**
    - *Barra Superior:* El banner aparece en la parte superior de la ventana del navegador.
    - *Barra Inferior:* El banner aparece en la parte inferior de la ventana del navegador.
    - *Modal Central:* Una ventana emergente en el medio de la pantalla.
    - *Caja Flotante (Superior Izquierda, Superior Derecha, Inferior Izquierda, Inferior Derecha):* Una caja más pequeña y fija en una de las esquinas.
  - **Valor recomendado:** La Barra Inferior o la Caja Flotante son generalmente menos intrusivas. El Modal Central es muy visible pero puede ser disruptivo.
  - **Escenario / ejemplo del comerciante:** Una tienda de moda podría preferir una "Barra Inferior" sutil para mantener el enfoque en los productos, mientras que un negocio basado en servicios podría usar un "Modal Central" para una máxima visibilidad.
- **Color de Fondo:**

  - **Qué hace esta configuración:** Establece el color de fondo principal del banner de aviso de cookies.
  - **Efecto de cambiar esta configuración:** Cambia el fondo visual del aviso.
  - **Valor recomendado:** Un color que contraste bien con su texto y coincida con su marca.
  - **Escenario / ejemplo del comerciante:** Use el color principal de su marca o un gris neutro.
- **Color del Texto:**

  - **Qué hace esta configuración:** Establece el color del texto del mensaje principal dentro del aviso.
  - **Efecto de cambiar esta configuración:** Cambia el color del texto del mensaje.
  - **Valor recomendado:** Un color que proporcione buena legibilidad contra el fondo elegido.
  - **Escenario / ejemplo del comerciante:** Texto blanco sobre un fondo oscuro, o texto gris oscuro sobre un fondo claro.
- **Color del Enlace:**

  - **Qué hace esta configuración:** Establece el color para cualquier enlace dentro de su mensaje de cookies (por ejemplo, el enlace "Más información" si forma parte del mensaje).
  - **Efecto de cambiar esta configuración:** Cambia el color del texto en el que se puede hacer clic dentro del mensaje.
  - **Valor recomendado:** El color de acento de su marca o un azul estándar para los enlaces.
  - **Escenario / ejemplo del comerciante:** Use un color brillante para que el enlace "Más información" se destaque.
- **Color de Fondo del Botón:**

  - **Qué hace esta configuración:** Establece el color de fondo para los botones "Aceptar" y "Más Información".
  - **Efecto de cambiar esta configuración:** Cambia el fondo visual de los botones.
  - **Valor recomendado:** Un color que haga que los botones sean claramente visibles y clicables.
  - **Escenario / ejemplo del comerciante:** Use el color de llamada a la acción de su marca.
- **Color del Texto del Botón:**

  - **Qué hace esta configuración:** Establece el color del texto en los botones "Aceptar" y "Más Información".
  - **Efecto de cambiar esta configuración:** Cambia el color de las etiquetas de los botones.
  - **Valor recomendado:** Un color que proporcione un buen contraste con el fondo del botón.
  - **Escenario / ejemplo del comerciante:** Texto blanco sobre un botón de color, o texto negro sobre un botón claro.
- **Color de Fondo del Botón al Pasar el Ratón:**

  - **Qué hace esta configuración:** Establece el color de fondo de los botones cuando un usuario pasa el ratón sobre ellos.
  - **Efecto de cambiar esta configuración:** Proporciona retroalimentación visual al usuario de que el botón es interactivo.
  - **Valor recomendado:** Un tono ligeramente más oscuro o más claro del color de fondo normal del botón.
  - **Escenario / ejemplo del comerciante:** Un cambio sutil de color para indicar interactividad.
- **Color del Texto del Botón al Pasar el Ratón:**

  - **Qué hace esta configuración:** Establece el color del texto de los botones cuando un usuario pasa el ratón sobre ellos.
  - **Efecto de cambiar esta configuración:** Proporciona retroalimentación visual.
  - **Valor recomendado:** A menudo el mismo que el color de texto normal del botón, o un color contrastante si el fondo cambia significativamente.
  - **Escenario / ejemplo del comerciante:** Si el fondo de su botón se vuelve oscuro al pasar el ratón, podría cambiar el texto a blanco.
- **Radio del Borde (px):**

  - **Qué hace esta configuración:** Controla la redondez de las esquinas del aviso de cookies y sus botones. Un valor de 0 significa esquinas afiladas, valores más altos significan esquinas más redondeadas.
  - **Efecto de cambiar esta configuración:**
    - *0px:* Esquinas afiladas y cuadradas.
    - *5px:* Esquinas ligeramente redondeadas.
    - *20px:* Esquinas muy redondeadas, con forma de píldora.
  - **Valor recomendado:** 0-5px para un aspecto moderno y limpio; más alto para una sensación más suave y amigable.
  - **Escenario / ejemplo del comerciante:** Haga que coincida con el `border-radius` utilizado en su tema para mayor coherencia.
- **Efecto Cristal:**

  - **Qué hace esta configuración:** Aplica un efecto translúcido, similar al cristal esmerilado, al fondo del aviso de cookies.
  - **Efecto de cambiar esta configuración:** Hace que el fondo sea ligeramente transparente y borroso, permitiendo que el contenido detrás se vea sutilmente.
  - **Valor recomendado:** Pruébelo y vea si se adapta a su diseño. Puede añadir una sensación premium.
  - **Escenario / ejemplo del comerciante:** Úselo si su tema tiene una estética moderna y minimalista.
- **Fondo Degradado:**

  - **Qué hace esta configuración:** Le permite usar una transición suave entre dos colores para el fondo del aviso de cookies en lugar de un solo color sólido.
  - **Efecto de cambiar esta configuración:** Crea una mezcla de colores visualmente atractiva. Normalmente tendrá opciones para un color de inicio y un color de fin.
  - **Valor recomendado:** Use colores que se complementen entre sí y con su marca.
  - **Escenario / ejemplo del comerciante:** Una tienda de tecnología podría usar un degradado de azul a púrpura para un aspecto moderno.
- **Color de Fondo de la Superposición (para Modal Central):**

  - **Qué hace esta configuración:** Cuando se utiliza la posición "Modal Central", esto establece el color de la capa semitransparente que cubre el resto de la página detrás del modal.
  - **Efecto de cambiar esta configuración:** Controla el enfoque visual en el modal. Una superposición más oscura y opaca hace que el modal se destaque más.
  - **Valor recomendado:** Un negro semitransparente (`rgba(0,0,0,0.7)`) o un tono oscuro que coincida con su tema.
  - **Escenario / ejemplo del comerciante:** Use una superposición oscura y ligeramente transparente para asegurarse de que el modal de cookies sea el enfoque principal cuando aparezca.
- **CSS Personalizado:**

  - **Qué hace esta configuración:** Proporciona un área de texto donde puede agregar sus propias reglas CSS personalizadas para estilizar aún más el aviso de cookies, anulando los estilos predeterminados del módulo.
  - **Efecto de cambiar esta configuración:** Permite una personalización avanzada más allá de las opciones proporcionadas.
  - **Valor recomendado:** Déjelo vacío a menos que tenga requisitos de diseño específicos y conocimientos de CSS.
  - **Escenario / ejemplo del comerciante:** Podría usar esto para cambiar el tamaño de fuente del mensaje, agregar una sombra o ajustar el relleno si las opciones integradas no son suficientes.

#### **Preajustes y Vista Previa en Vivo**

- **Cargar Preajuste:**

  - **Qué hace esta configuración:** Le permite aplicar rápidamente un conjunto predefinido de opciones de estilo (colores, posiciones, efectos) de una biblioteca de diseños listos para usar.
  - **Efecto de cambiar esta configuración:** Transforma instantáneamente la apariencia de su aviso de cookies para que coincida con el preajuste elegido. Todas las configuraciones de estilo individuales se actualizarán.
  - **Valor recomendado:** Explore los preajustes para encontrar uno que se adapte a su marca y luego ajústelo.
  - **Escenario / ejemplo del comerciante:** Está buscando un banner oscuro y minimalista. Selecciona un preajuste de "Tema Oscuro" y luego simplemente ajusta los tonos exactos de negro y gris.
- **Vista Previa en Vivo:**

  - **Qué hace esta configuración:** Esta sección de la página de configuración muestra una vista previa en tiempo real de su aviso de cookies a medida que ajusta la configuración.
  - **Efecto de cambiar esta configuración:** Le muestra exactamente cómo se verá su banner en el front office, sin necesidad de guardar y actualizar su tienda.
  - **Valor recomendado:** Siempre use la vista previa en vivo para verificar sus elecciones de diseño antes de guardar.
  - **Escenario / ejemplo del comerciante:** Está experimentando con diferentes colores de botones; la vista previa en vivo le muestra inmediatamente qué combinación se ve mejor.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Habilitar Módulo de Ley de Cookies | SÍ | Interruptor maestro para el aviso de cookies. |
| | Tiempo de Expiración de la Cookie (días) | 365 | Cuánto tiempo se recuerda el consentimiento. |
| | Mostrar en Dispositivos Móviles | SÍ | Mostrar banner en teléfonos/tabletas. |
| | Mostrar solo a Visitantes de la UE | NO (para cumplimiento global) | Dirigirse a visitantes de la UE o a todos los visitantes. |
| | Mensaje de Ley de Cookies | Personalizable | Texto principal del aviso de cookies. |
| | Texto del Botón "Aceptar" | "Aceptar" | Etiqueta para el botón de consentimiento. |
| | Texto del Botón "Más Información" | "Más información" | Etiqueta para el botón de información. |
| | Enlace a la Página de Política de Privacidad | Su URL de Política | URL para la política de cookies detallada. |
| | Posición del Aviso de Cookies | Barra Inferior / Caja Flotante | Dónde aparece el banner (Barra Superior/Inferior, Modal Central, Caja Flotante). |
| | Color de Fondo | Personalizable | Color de fondo principal del aviso. |
| | Color del Texto | Personalizable | Color del texto del mensaje. |
| | Color del Enlace | Personalizable | Color de los enlaces dentro del mensaje. |
| | Color de Fondo del Botón | Personalizable | Color de fondo de los botones de acción. |
| | Color del Texto del Botón | Personalizable | Color del texto en los botones de acción. |
| | Color de Fondo del Botón al Pasar el Ratón | Personalizable | Color de fondo al pasar el ratón por el botón. |
| | Color del Texto del Botón al Pasar el Ratón | Personalizable | Color del texto al pasar el ratón por el botón. |
| | Radio del Borde (px) | 0-5 | Redondez de las esquinas. |
| | Efecto Cristal | NO | Agrega un efecto translúcido y esmerilado. |
| | Fondo Degradado | NO | Utiliza un degradado de color para el fondo. |
| | Color de Fondo de la Superposición | Oscuro semitransparente | Color de la superposición de fondo para el Modal Central. |
| | CSS Personalizado | Vacío | Para anulaciones de estilo avanzadas. |
| | Cargar Preajuste | Elegir uno | Aplicar opciones de estilo predefinidas. |
| | Vista Previa en Vivo | N/A | Retroalimentación visual en tiempo real de la configuración. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: He configurado el módulo, pero el banner de cookies no aparece en mi tienda.**
R:

1. **Verifique "Habilitar Módulo de Ley de Cookies":** Asegúrese de que esté configurado en SÍ en la configuración del módulo.
2. **Borrar Caché:** Vaya a **Parámetros Avanzados > Rendimiento** en el back office de su PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Es posible que también deba borrar la caché del navegador (Ctrl+F5 o Cmd+R).
3. **Verifique la Configuración del País de la UE:** Si "Mostrar solo a Visitantes de Países de la UE" está habilitado, asegúrese de que está probando desde una dirección IP de la UE. Intente deshabilitar esta configuración temporalmente para realizar pruebas.
4. **Compatibilidad del Tema:** Aunque el módulo está diseñado para ser compatible, algunos temas altamente personalizados pueden tener conflictos. Revise la consola de desarrollador de su navegador (F12) en busca de errores de JavaScript.

**P: El banner se ve diferente en mi tienda que en la vista previa en vivo.**
R:

1. **Borrar Caché:** Siempre borre la caché de su PrestaShop (**Parámetros Avanzados > Rendimiento**) después de realizar cambios. La caché de su navegador también podría estar mostrando una versión anterior.
2. **Conflictos de CSS Personalizado:** Si ha agregado "CSS Personalizado" o su tema tiene estilos conflictivos, podrían anular la configuración del módulo. Elimine temporalmente su CSS personalizado para ver si eso resuelve el problema.
3. **Anulaciones del Tema:** Su tema podría tener reglas CSS específicas que son más específicas que las del módulo. Un desarrollador puede ayudar a identificar y resolver estas.

**P: ¿Cómo traduzco el mensaje de cookies y los textos de los botones a otros idiomas?**
R:

1. Vaya a **Internacional > Traducciones** en el back office de su PrestaShop.
2. Seleccione "Traducciones de módulos instalados" como Tipo de traducción.
3. Elija su tema.
4. Seleccione el idioma que desea traducir.
5. Busque el módulo "Ley de Cookies de la Unión Europea Pro" en la lista. Podrá traducir el "Mensaje de Ley de Cookies", el "Texto del Botón Aceptar" y el "Texto del Botón Más Información" allí.

**P: El banner de cookies está cubriendo una parte importante de mi sitio web (por ejemplo, un widget de chat, un elemento del menú).**
R:

1. **Ajustar Posición:** Experimente con la configuración "Posición del Aviso de Cookies". Si una barra inferior cubre un widget de chat, pruebe una barra superior o una caja flotante en una esquina diferente.
2. **CSS Personalizado (Avanzado):** Si ninguna posición funciona, un desarrollador puede usar el campo "CSS Personalizado" para ajustar la propiedad `z-index` del banner de cookies o del elemento en conflicto para asegurar que el elemento correcto esté encima.

**P: ¿Este módulo maneja diferentes categorías de cookies (por ejemplo, esenciales, analíticas, de marketing)?**
R: Este módulo se enfoca principalmente en mostrar un aviso general de consentimiento de cookies y recopilar un único consentimiento de "aceptar" o "rechazar" (al no aceptar). Para una gestión más avanzada y granular de categorías de cookies (donde los usuarios pueden seleccionar qué tipos de cookies permiten), normalmente necesitaría una solución más compleja o integrarse con una Plataforma de Gestión de Consentimiento (CMP) dedicada. Este módulo está diseñado para un cumplimiento sencillo.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica para desarrolladores y webmasters que buscan comprender, personalizar o depurar el módulo "Ley de Cookies de la Unión Europea Pro".

### 4.1 Descripción General de la Arquitectura

El módulo `uecookiepro` sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para su funcionalidad principal y `getContent()` para la configuración del back-office. Inyecta su contenido de front-office directamente en un hook elegido, renderizando dinámicamente el banner de cookies basado en la configuración. El estilo se gestiona a través de estilos en línea y, potencialmente, CSS personalizado, con JavaScript manejando la interacción del usuario y el almacenamiento del consentimiento.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador de front-office o back-office personalizado. Toda la configuración se maneja dentro del método `getContent()` del archivo principal del módulo, y la visualización del front-office se gestiona a través de hooks.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no define ninguna clase personalizada o instancias de `ObjectModel`. Toda la configuración se almacena directamente en la tabla `ps_configuration` utilizando claves de configuración estándar de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

El módulo incluye varios archivos JavaScript, principalmente para mejoras en la configuración del back-office y la interacción del front-office.

- `uecookiepro/jscolor/jscolor.js`:
  - **Alcance:** Back-office.
  - **Responsabilidad:** Proporciona la funcionalidad del selector de color utilizada en el formulario de configuración del módulo, permitiendo a los comerciantes seleccionar visualmente los colores para el banner.
- `uecookiepro/tinymce-original.js`:
  - **Alcance:** Back-office.
  - **Responsabilidad:** La biblioteca principal del editor de texto enriquecido TinyMCE. Esto se utiliza para el campo "Mensaje de Ley de Cookies", lo que permite a los comerciantes formatear su mensaje con HTML.
- `uecookiepro/tinymce16.inc.js`:
  - **Alcance:** Back-office.
  - **Responsabilidad:** Un archivo de inclusión que probablemente contiene configuraciones y ajustes de inicialización específicos de TinyMCE adaptados para entornos PrestaShop 1.6.x, asegurando que el editor funcione correctamente dentro de la configuración del módulo.
- `uecookiepro/views/js/patterns.js`:
  - **Alcance:** Back-office.
  - **Responsabilidad:** Probablemente contiene patrones o configuraciones predefinidas para los preajustes de estilo del módulo, utilizados para cargar rápidamente diferentes temas visuales para el banner de cookies.
- `uecookiepro/views/js/presets-community.js`:
  - **Alcance:** Back-office.
  - **Responsabilidad:** Contiene preajustes adicionales aportados por la comunidad o extendidos para el estilo visual del banner de cookies, ofreciendo más opciones de diseño listas para usar.
- `uecookiepro/views/js/scripts.js`:
  - **Alcance:** Front-office y Back-office.
  - **Responsabilidad:** Este es el archivo JavaScript personalizado principal para el módulo.
    - **Front-office:** Maneja la lógica de visualización del banner de cookies, escucha los clics del botón "Aceptar", establece la cookie de consentimiento y oculta el banner. También gestiona la visibilidad según el `Cookie Expiration Time`.
    - **Back-office:** Probablemente contiene lógica para la funcionalidad de vista previa en vivo, actualizando dinámicamente el banner de vista previa a medida que se cambian las configuraciones en el formulario de configuración. También podría manejar interacciones con la función "Cargar Preajuste".

### 4.5 Hojas de Estilo CSS (`views/css/`)

El módulo no enumera explícitamente ningún archivo `.css` en el inventario proporcionado. Esto sugiere que el estilo se maneja principalmente a través de:

1. **Estilos en línea:** Generados dinámicamente por el módulo en función de la configuración (colores, posiciones, etc.).
2. **CSS interno de `jscolor.js`:** Para la interfaz de usuario del selector de color.
3. **CSS interno de `tinymce`:** Para la interfaz de usuario del editor de texto enriquecido.
4. **Campo de CSS personalizado:** Permitiendo a los comerciantes inyectar sus propios estilos.
   Los desarrolladores que deseen anular estilos deben inspeccionar el HTML renderizado del banner de cookies y apuntar a sus elementos con reglas CSS más específicas en la hoja de estilo de su tema o a través del campo CSS personalizado del módulo.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de Hook (`views/templates/hook/`)**:
  - `uecookiepro/top.tpl`:
    - **Hook:** Esta plantilla está diseñada para ser renderizada en varios hooks de front-office como `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, o incluso directamente dentro de `product.tpl` o `index.tpl` del tema, dependiendo de la "Posición del Aviso de Cookies" elegida y de cómo se implementen los métodos `hookDisplay*` del módulo.
    - **Salida:** Genera la estructura HTML para el banner de consentimiento de cookies, incluyendo el texto del mensaje, el botón "Aceptar" y el enlace "Más Información". El estilo dinámico (colores, posición, efectos) se inyecta en esta plantilla, ya sea como estilos en línea o mediante manipulación de JavaScript.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:
  El módulo no crea ninguna tabla SQL personalizada. Todas las configuraciones se almacenan en la tabla estándar `ps_configuration` de PrestaShop. Las claves de configuración suelen seguir el patrón `UECOOKIEPRO_SETTING_NAME`.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza en la sección `<head>` de cada página. | Potencialmente utilizado para cargar activos CSS/JS o para inyectar el banner en la parte superior de la página. |
| `displayFooter` | Se renderiza en la parte inferior de cada página, antes de la etiqueta de cierre `</body>`. | Hook común para inyectar el banner de cookies (posición de barra inferior) o su JavaScript asociado. |
| `displayLeftColumn` | Se renderiza en la barra lateral izquierda (si está habilitada por el tema). | Menos común para banners de cookies, pero podría usarse para una caja flotante en la columna izquierda. |
| `displayRightColumn` | Se renderiza en la barra lateral derecha (si está habilitada por el tema). | Menos común para banners de cookies, pero podría usarse para una caja flotante en la columna derecha. |
| `displayProductAdditionalInfo` (o hook similar de página de producto) | Se renderiza en la página del producto, a menudo debajo de la descripción o detalles del producto. | Podría usarse para colocar una caja flotante específicamente en las páginas de productos. |
| `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador de front-office establece sus medios (CSS/JS). | Ideal para cargar condicionalmente CSS y JavaScript específicos del módulo solo cuando sea necesario, mejorando el rendimiento. |

El módulo elige dinámicamente qué hook usar según la configuración de "Posición del Aviso de Cookies". Por ejemplo, si se selecciona "Barra Inferior", es probable que use `displayFooter`. Si se selecciona "Barra Superior", podría usar `displayHeader`. Las posiciones "Caja Flotante" o "Modal Central" suelen gestionarse inyectando el HTML en un hook general como `displayFooter` y luego usando CSS (`position: fixed;`) y JavaScript para controlar su ubicación y visibilidad exactas.

## 5. Soporte Oficial y Actualizaciones

Para soporte oficial, actualizaciones del módulo y cualquier asistencia adicional, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a brindar soporte oportuno y garantizar que su módulo funcione de manera óptima.
"""

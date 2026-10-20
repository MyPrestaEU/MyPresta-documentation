---
title: "Widget para unirse a grupo de Facebook - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Widget para unirse a grupo de Facebook' de MyPresta.eu."
sidebar:
  label: "Widget para unirse a grupo de Facebook - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook join to group widget en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-join-to-group-widget.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-join-to-group-widget/)
>
> ---


# Widget para unirse a grupo de Facebook

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla principal donde configurará todas las opciones para su widget de unirse a grupo de Facebook.

- **Nombre de la pantalla y ubicación del menú:** Back Office > Módulos > Gestor de módulos > "Widget para unirse a grupo de Facebook" > Configurar

#### Ajustes y opciones:

1.  **URL del grupo** (Clave de configuración: `fbg_href`)

    - **Qué hace este ajuste:** Esta es la configuración más crucial. Define el enlace directo a su Grupo de Facebook. Cuando los clientes hagan clic en el botón "Unirse al grupo", serán llevados a esta URL.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece una URL de Grupo de Facebook válida:* El botón "Unirse al grupo" redirigirá correctamente a los usuarios a su grupo especificado.
      - *Cuando se deja vacío o se establece una URL no válida:* El botón podría no funcionar, o podría llevar a una página de error, frustrando a sus clientes.
    - **Valor recomendado:** Siempre proporcione la URL completa y correcta de su Grupo de Facebook (por ejemplo, `https://www.facebook.com/groups/nombre_de_su_grupo/`).
    - **Escenario/ejemplo de comerciante:** Desea que los clientes se unan a su grupo "Comunidad de Mi Tienda Impresionante". Pegaría `https://www.facebook.com/groups/comunidad_de_mi_tienda_impresionante/` aquí.
2.  **Ancho de la caja** (Clave de configuración: `fbg_width`)

    - **Qué hace este ajuste:** Controla el ancho del cuadro del widget para unirse a grupo de Facebook en su tienda. Puede especificarlo en píxeles.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece un valor de píxel específico (por ejemplo, `280`):* El cuadro intentará renderizarse con ese ancho exacto.
      - *Cuando se deja vacío o se establece en `0`:* El módulo intentará ajustar automáticamente su ancho según el espacio disponible en el hook en el que se muestra, o usará un valor predeterminado.
    - **Valor recomendado:** Comience con `280` o `300` píxeles. Pruebe en diferentes dispositivos. Si desea que ocupe el espacio disponible en una columna, podría dejarlo vacío, pero tenga en cuenta que podría estirarse demasiado en algunos hooks.
    - **Escenario/ejemplo de comerciante:** Desea que el widget encaje perfectamente en su columna izquierda, que tiene 250px de ancho. Lo establecería en `250`.
3.  **¿Dónde desea mostrar la caja?** (Clave de configuración: `fbg_hook`)

    - **Qué hace este ajuste:** Este desplegable le permite seleccionar la ubicación específica (hook de PrestaShop) donde aparecerá el widget en su tienda.
    - **Efecto de cambiar este ajuste:**
      - *Seleccionando `DisplayFooter`:* El widget aparecerá en la parte inferior de cada página.
      - *Seleccionando `DisplayHome`:* El widget aparecerá solo en su página de inicio.
      - *Seleccionando `DisplayRightColumn`:* El widget aparecerá en la barra lateral derecha en las páginas que la tengan.
      - *Seleccionando cualquier otro hook:* El widget aparecerá en esa ubicación específica.
    - **Valor recomendado:** Esto depende completamente de su tema y estrategia de marketing. `DisplayRightColumn` o `DisplayLeftColumn` son comunes para widgets laterales. `DisplayFooter` es bueno para una ubicación menos intrusiva. `DisplayHome` es excelente para una alta visibilidad.
    - **Escenario/ejemplo de comerciante:** Desea que el widget sea visible en la mayoría de las páginas pero que no interfiera con su contenido principal. Elige `DisplayRightColumn`.
4.  **Cabecera** (Clave de configuración: `fbg_header`)

    - **Qué hace este ajuste:** Este es el texto del título principal que se muestra en la parte superior de su widget para unirse a grupo de Facebook.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en "Únete a nuestra comunidad":* Este texto se mostrará prominentemente.
      - *Cuando se deja vacío:* No se mostrará texto de cabecera, lo que hará que el widget sea menos claro para los clientes.
    - **Valor recomendado:** Un título claro y atractivo como "Únete a nuestro grupo de Facebook", "Nuestra comunidad" o "Conéctate con nosotros".
    - **Escenario/ejemplo de comerciante:** Desea indicar claramente a los clientes de qué trata el cuadro. Lo establece en "¡Únete a nuestro grupo exclusivo de Facebook!".
5.  **Descripción** (Clave de configuración: `fbg_desc`)

    - **Qué hace este ajuste:** Proporciona un texto explicativo breve debajo de la cabecera, dando a los clientes más contexto sobre su Grupo de Facebook.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en "¡Obtén ofertas y actualizaciones exclusivas!":* Este mensaje aparecerá debajo de la cabecera.
      - *Cuando se deja vacío:* El widget solo mostrará la cabecera y el botón, perdiendo potencialmente una oportunidad para atraer a los usuarios.
    - **Valor recomendado:** Una frase o dos breves y convincentes que expliquen los beneficios de unirse (por ejemplo, "¡Sé el primero en enterarte de nuevos productos y ofertas especiales!").
    - **Escenario/ejemplo de comerciante:** Desea fomentar las inscripciones destacando los beneficios. Lo establece en "¡Accede a descuentos exclusivos para miembros, adelantos y conéctate con otros entusiastas!".
6.  **Texto del botón** (Clave de configuración: `fbg_btn_text`)

    - **Qué hace este ajuste:** Este es el texto que se muestra en el botón que los clientes hacen clic para unirse a su grupo.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en "Unirse al grupo":* Este texto aparecerá en el botón.
      - *Cuando se deja vacío:* El botón podría aparecer en blanco o usar un valor predeterminado, lo cual es menos efectivo.
    - **Valor recomendado:** Una llamada a la acción clara como "Unirse al grupo", "Unirse ahora" o "Conectar en Facebook".
    - **Escenario/ejemplo de comerciante:** Desea una llamada a la acción directa. Lo establece en "Unirse a nuestro grupo".
7.  **Color del texto** (Clave de configuración: `fbg_text_color`)

    - **Qué hace este ajuste:** Le permite establecer el color del texto de la cabecera y la descripción dentro del widget.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en `#000000` (negro):* El texto aparecerá en negro.
      - *Cuando se establece en `#FFFFFF` (blanco):* El texto aparecerá en blanco.
    - **Valor recomendado:** Elija un color que contraste bien con el color de fondo elegido y que coincida con la paleta de colores de su marca. Use un código hexadecimal (por ejemplo, `#333333`).
    - **Escenario/ejemplo de comerciante:** Su widget tiene un fondo oscuro. Establece el color del texto en `#FFFFFF` para facilitar la lectura.
8.  **Estilo del borde** (Clave de configuración: `fbg_border_style`)

    - **Qué hace este ajuste:** Define el estilo visual del borde alrededor del cuadro del widget.
    - **Efecto de cambiar este ajuste:**
      - *`solid`:* Una línea única y continua.
      - *`dashed`:* Una serie de líneas cortas.
      - *`dotted`:* Una serie de puntos.
      - *`none`:* No se mostrará ningún borde.
    - **Valor recomendado:** `solid` o `none` son los más comunes. `solid` proporciona un límite claro.
    - **Escenario/ejemplo de comerciante:** Desea un contorno sutil para el cuadro. Elige `solid`.
9.  **Color del borde** (Clave de configuración: `fbg_border_color`)

    - **Qué hace este ajuste:** Establece el color del borde alrededor del cuadro del widget.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en `#CCCCCC` (gris claro):* El borde será gris claro.
      - *Cuando se establece en `#FF0000` (rojo):* El borde será rojo.
    - **Valor recomendado:** Un color que complemente el diseño de su tienda, a menudo un gris sutil o un color de acento de la marca. Use un código hexadecimal.
    - **Escenario/ejemplo de comerciante:** Su marca utiliza un tono específico de azul. Establece el color del borde en `#007bff`.
10. **Tamaño del borde** (Clave de configuración: `fbg_border_size`)

    - **Qué hace este ajuste:** Determina el grosor del borde en píxeles.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en `1`:* Aparecerá un borde delgado.
      - *Cuando se establece en `5`:* Aparecerá un borde más grueso y prominente.
    - **Valor recomendado:** `1` o `2` píxeles para un borde sutil.
    - **Escenario/ejemplo de comerciante:** Desea un borde muy delgado. Establece el tamaño en `1`.
11. **Radio del borde** (Clave de configuración: `fbg_border_radius`)

    - **Qué hace este ajuste:** Controla la redondez de las esquinas del cuadro del widget. Un valor más alto crea esquinas más redondeadas.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en `0`:* El cuadro tendrá esquinas afiladas y cuadradas.
      - *Cuando se establece en `10`:* Las esquinas estarán notablemente redondeadas.
    - **Valor recomendado:** `0` para esquinas afiladas, `3` a `5` para ligeramente redondeadas, o `10+` para muy redondeadas, dependiendo de la estética de su tema.
    - **Escenario/ejemplo de comerciante:** Su tema utiliza elementos ligeramente redondeados. Establece el radio del borde en `5`.
12. **Color de fondo** (Clave de configuración: `fbg_bg_color`)

    - **Qué hace este ajuste:** Establece el color de fondo principal del cuadro del widget.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en `#F0F2F5` (gris claro, similar al fondo de Facebook):* El fondo del cuadro será gris claro.
      - *Cuando se establece en `#FFFFFF` (blanco):* El fondo del cuadro será blanco.
    - **Valor recomendado:** Un color que haga que el texto sea legible y se ajuste al diseño de su tienda. Use un código hexadecimal.
    - **Escenario/ejemplo de comerciante:** Desea que el widget se destaque ligeramente de un fondo de página blanco. Establece el color de fondo en `#F8F8F8`.
13. **Gradiente de fondo** (Clave de configuración: `fbg_bg_gradient`)

    - **Qué hace este ajuste:** Le permite añadir un gradiente CSS al fondo del cuadro del widget, creando una transición suave entre dos o más colores. Esto anula el "Color de fondo" único si se utiliza.
    - **Efecto de cambiar este ajuste:**
      - *Cuando se establece en `linear-gradient(to right, #FFD700, #FFA500)`:* El fondo hará una transición de dorado a naranja.
      - *Cuando se deja vacío:* Se utilizará la configuración de "Color de fondo" en su lugar.
    - **Valor recomendado:** Use una cadena de gradiente CSS si desea un fondo más dinámico. Si no está seguro, déjelo vacío y use un solo "Color de fondo".
    - **Escenario/ejemplo de comerciante:** Desea un aspecto sutil y moderno. Utiliza un gradiente como `linear-gradient(to bottom, #e0eafc, #cfdef3)`.

#### Ajustes ocultos/internos (para referencia del desarrollador, no configurables directamente por el comerciante):

- `mypresta_updates`, `update_`, `updatev_`: Claves internas para actualizaciones y comprobaciones de versión del módulo.
- `fbg_app`, `fbg_appid`: Estas claves sugieren un potencial para la integración de la aplicación de Facebook, pero no están expuestas en la configuración actual.
- `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Configuraciones centrales de PrestaShop relacionadas con el manejo de idiomas en el back office.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | **URL del grupo** | URL de su Grupo de Facebook | Enlace directo a su Grupo de Facebook para el botón "Unirse al grupo". **¡CRÍTICO!** |
| Configuración del módulo | **Ancho de la caja** | `280` o `300`px | Establece el ancho del cuadro del widget. Dejar vacío para ajuste automático. |
| Configuración del módulo | **¿Dónde desea mostrar la caja?** | `DisplayRightColumn` o `DisplayFooter` | Selecciona el hook de PrestaShop donde aparece el widget. |
| Configuración del módulo | **Cabecera** | "Únete a nuestro grupo de Facebook" | Texto del título principal para el widget. |
| Configuración del módulo | **Descripción** | "¡Obtén ofertas y actualizaciones exclusivas!" | Texto explicativo breve debajo de la cabecera. |
| Configuración del módulo | **Texto del botón** | "Unirse al grupo" | Texto que se muestra en el botón de acción. |
| Configuración del módulo | **Color del texto** | `#333333` (gris oscuro) | Color del texto de la cabecera y la descripción. Usar código hexadecimal. |
| Configuración del módulo | **Estilo del borde** | `solid` o `none` | Estilo visual del borde del cuadro (sólido, discontinuo, punteado, ninguno). |
| Configuración del módulo | **Color del borde** | `#CCCCCC` (gris claro) | Color del borde del cuadro. Usar código hexadecimal. |
| Configuración del módulo | **Tamaño del borde** | `1` o `2`px | Grosor del borde del cuadro. |
| Configuración del módulo | **Radio del borde** | `0` o `5`px | Redondez de las esquinas del cuadro. |
| Configuración del módulo | **Color de fondo** | `#F0F2F5` (gris claro) | Color de fondo principal del cuadro del widget. Usar código hexadecimal. |
| Configuración del módulo | **Gradiente de fondo** | Dejar vacío | Gradiente CSS para el fondo. Anula el `Color de fondo` si se establece. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

1.  **El widget no aparece en mi tienda.**

    - **Comprobación 1:** Vaya a **Módulos > Gestor de módulos**, busque "Widget para unirse a grupo de Facebook" y asegúrese de que esté instalado y habilitado.
    - **Comprobación 2:** En la configuración del módulo, verifique que haya seleccionado un "Dónde desea mostrar la caja?" (hook). Asegúrese de que el hook seleccionado realmente exista y esté activo en su tema actual. Algunos temas pueden no usar todos los hooks estándar de PrestaShop.
    - **Comprobación 3:** Borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**). A veces, los cambios no aparecen hasta que se actualiza la caché.
    - **Comprobación 4:** Si tiene un tema personalizado, podría anular las visualizaciones de hooks estándar. Póngase en contacto con el desarrollador de su tema o con un webmaster.
2.  **El botón "Unirse al grupo" no funciona o lleva a un error.**

    - **Comprobación:** Vaya a la configuración del módulo y vuelva a introducir cuidadosamente su "URL del grupo". Asegúrese de que sea la URL completa y correcta de su Grupo de Facebook (por ejemplo, `https://www.facebook.com/groups/nombre_de_su_grupo/`). Pruebe la URL directamente en su navegador para confirmar que funciona.
3.  **El widget se ve extraño o no se ajusta al diseño de mi tema.**

    - **Comprobación 1:** Ajuste la configuración de "Ancho de la caja". Si es demasiado ancho para una columna, podría romper el diseño. Pruebe con un valor de píxel más pequeño.
    - **Comprobación 2:** Utilice los ajustes de "Color del texto", "Estilo del borde", "Color del borde", "Tamaño del borde", "Radio del borde", "Color de fondo" y "Gradiente de fondo" para que coincidan con los colores y estilos de su tema.
    - **Comprobación 3:** Borre la caché de su PrestaShop después de realizar cambios de estilo.
    - **Comprobación 4:** Si el problema persiste, podría ser un conflicto de CSS con su tema. Un webmaster puede inspeccionar el CSS de su sitio para identificar y resolver conflictos.
4.  **¿Puedo mostrar el widget en varias ubicaciones?**

    - La versión actual del módulo le permite seleccionar solo un hook del desplegable. Si necesita mostrarlo en varios lugares, necesitaría duplicar el módulo (lo que requiere la intervención de un desarrollador) o usar una solución personalizada.
5.  **Mi texto no aparece en el idioma correcto.**

    - Los campos "Cabecera", "Descripción" y "Texto del botón" suelen ser traducibles si su instalación de PrestaShop admite varios idiomas para las configuraciones del módulo. Asegúrese de que está editando la configuración del módulo en el contexto de idioma correcto en el Back Office (verifique el desplegable de idioma en la parte superior derecha de su panel de administración).

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Widget para unirse a grupo de Facebook" es un módulo de PrestaShop sencillo que sigue un patrón básico similar a MVC inherente a la estructura de módulos de PrestaShop. Utiliza principalmente la clase `Module` para su funcionalidad principal, gestión de configuración y registro de hooks. Toda la configuración se maneja a través del método `getContent()` en el archivo principal del módulo, almacenando los ajustes en `ps_configuration`. La visualización en el front-office se gestiona a través de plantillas Smarty renderizadas a través de hooks registrados. No hay controladores personalizados ni ObjectModels.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. Toda la renderización del front-office se maneja directamente a través de métodos `hook` dentro del archivo principal del módulo `fbgroup.php`, que luego renderizan plantillas Smarty.
-   **Controladores de Administración de Back-Office**: Ninguno. Toda la administración se maneja a través del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

-   **`fbgroup/fbgroup.php` (Clase principal del módulo)**
    -   **Nombre de la clase:** `Fbgroup`
    -   **Clase padre:** `Module`
    -   **Responsabilidad:**
        -   Instalación (`install()`) y desinstalación (`uninstall()`) del módulo.
        -   Registro de todos los hooks especificados (`registerHook()`).
        -   Gestión de la configuración del módulo a través del método `getContent()`, que maneja el envío del formulario y actualiza la tabla `ps_configuration`.
        -   Implementación de varios métodos `hook` (por ejemplo, `hookDisplayHeader`, `hookDisplayFooter`, `hookDisplayHome`, etc.) para renderizar el widget en el front office.
        -   Recuperación de valores de configuración de `ps_configuration` para la renderización de plantillas.
        -   Método `_clearCache()` para borrar la caché específica del módulo.
        -   Método `_displayForm()` para renderizar el formulario de configuración en el back office.

### 4.4 Activos JavaScript (`views/js/`)

-   No se incluyen archivos JavaScript personalizados en este módulo. Toda la funcionalidad se maneja en el lado del servidor o mediante HTML/CSS estándar.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   No se incluyen archivos CSS personalizados en este módulo. Todo el estilo se aplica en línea dentro de la plantilla `displayHeader.tpl` o directamente a través del método `hookDisplayHeader`, utilizando los valores de configuración. Esto significa que los desarrolladores que deseen anular estilos deberán apuntar directamente al HTML generado o usar el hook `displayHeader` para inyectar su propio CSS.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   `fbgroup/views/displayHeader.tpl`:
        -   **Hook:** Principalmente destinado a `displayHeader` (aunque el método `hookDisplayHeader` del módulo se utiliza para inyectar CSS, no para renderizar el widget en sí). Esta plantilla NO se utiliza para la visualización principal del widget. Es probable que sea un remanente o se utilice para la inyección de meta/CSS.
        -   **Propósito:** Si se utilizara, generaría HTML dentro de la sección `<head>`. En el contexto de este módulo, el método `hookDisplayHeader` se utiliza para *inyectar estilos CSS* dinámicamente basados en la configuración, en lugar de renderizar una plantilla visible.
    -   `fbgroup/views/displayWidget.tpl`:
        -   **Hook:** Esta es la plantilla principal utilizada para renderizar el widget para unirse a grupo de Facebook en todos los hooks seleccionados del front-office (por ejemplo, `displayFooter`, `displayHome`, `displayRightColumn`, etc.).
        -   **Propósito:** Genera la estructura HTML para el widget, incluyendo la cabecera, la descripción y el botón "Unirse al grupo". Recibe variables como `fbg_href`, `fbg_header`, `fbg_desc`, `fbg_btn_text` y estilos CSS dinámicos de los métodos hook del módulo.
-   **Plantillas de administración (`views/templates/admin/`)**: Ninguna. El formulario de configuración se construye programáticamente dentro de `getContent()` utilizando `HelperForm` de PrestaShop.
-   **Plantillas de front-office (`views/templates/front/`)**: Ninguna.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   El módulo no crea ninguna tabla de base de datos personalizada.
    -   Todos los ajustes de configuración se almacenan en la tabla `ps_configuration` (o prefijo `_configuration`, según su configuración) utilizando las claves de configuración enumeradas en la sección 4.1 (por ejemplo, `FBG_HREF`, `FBG_WIDTH`, `FBG_HEADER`, etc.).
-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Utilizado por el módulo para inyectar estilos CSS dinámicos para el widget basados en la configuración. |
| `displayFooter` | En la parte inferior de cada página, antes de `</body>`. | Renderiza la plantilla `displayWidget.tpl`, mostrando el widget de Facebook. |
| `displayHome` | En la página de inicio, generalmente en el área de contenido principal. | Renderiza la plantilla `displayWidget.tpl`, mostrando el widget de Facebook. |
| `displayNav1` | En la barra de navegación, a menudo arriba a la izquierda. | Renderiza la plantilla `displayWidget.tpl`, mostrando el widget de Facebook. |
| `displayNav2` | En la barra de navegación, a menudo arriba a la derecha. | Renderiza la plantilla `displayWidget.tpl`, mostrando el widget de Facebook. |
| `displayNav` | Hook de navegación genérico, dependiente del tema. | Renderiza la plantilla `displayWidget.tpl`, mostrando el widget de Facebook. |
| `displayFbgroup` | Hook personalizado, requiere integración con el tema. | Renderiza la plantilla `displayWidget.tpl`, mostrando el widget de Facebook. |
| `displayTop` | En la sección de la cabecera, a menudo encima del logotipo. | Renderiza la plantilla `displayWidget.tpl`, mostrando el widget de Facebook. |
| `displayTopColumn` | En el área de contenido principal de la cabecera. | Renderiza la plantilla `displayWidget.tpl`, mostrando el widget de Facebook. |
| `displayLeftColumn` | En la barra lateral izquierda de las páginas que la tienen. | Renderiza la plantilla `displayWidget.tpl`, mostrando el widget de Facebook. |
| `displayRightColumn` | En la barra lateral derecha de las páginas que la tienen. | Renderiza la plantilla `displayWidget.tpl`, mostrando el widget de Facebook. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Widget para unirse a grupo de Facebook", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.

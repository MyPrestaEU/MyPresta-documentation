---
title: "PopUp Login Pro - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo PopUp Login Pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "PopUp Login Pro - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo PopUp Login Pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/popup-login-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/popup-login-pro/)
>
> ---


# PopUp Login Pro

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x, 1.4.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una tienda PrestaShop y este módulo no tiene requisitos inusuales más allá de eso.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > PopUp Login Pro)

Esta es la pantalla de configuración principal del módulo PopUp Login Pro. Aquí puede personalizar cómo aparece y se comporta la ventana emergente en su tienda.

#### Configuración general

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo de comerciante |
| --- | --- | --- | --- | --- |
| **Habilitar PopUp Login** | Este interruptor controla si la funcionalidad de inicio de sesión emergente está activa en su tienda. | *Cuando está habilitado:* El módulo interceptará los clics en los enlaces de inicio de sesión y mostrará la ventana emergente. *Cuando está deshabilitado:* Su tienda volverá a las redirecciones de página de inicio de sesión predeterminadas de PrestaShop. | SÍ | Desea utilizar la función de inicio de sesión emergente. |
| **Tipo de formulario PopUp** | Esta opción le permite seleccionar entre varios estilos visuales prediseñados para su formulario de inicio de sesión emergente. | *Cuando se establece en Opción A:* La ventana emergente se mostrará con el diseño de la Opción A. *Cuando se establece en Opción B:* La ventana emergente se mostrará con el diseño de la Opción B. Cada opción ofrece un aspecto y una sensación distintos. | Elija el que mejor se adapte al diseño de su tienda. | Desea un formulario de inicio de sesión minimalista (Opción 1) o uno más visualmente atractivo con una imagen (Opción 3). |
| **Ancho del PopUp (píxeles)** | Define el ancho de la ventana emergente en píxeles. | *Cuando se establece en 400px:* La ventana emergente tendrá 400 píxeles de ancho. *Cuando se establece en 600px:* La ventana emergente tendrá 600 píxeles de ancho. Un ancho menor podría verse mejor en dispositivos móviles, mientras que uno mayor puede acomodar más contenido o un diseño específico. | 400-500px (ajustar según el tipo de formulario seleccionado) | El tipo de formulario elegido se ve apretado a 400px, por lo que lo aumenta a 500px para una mejor legibilidad. |
| **Altura del PopUp (píxeles)** | Define la altura de la ventana emergente en píxeles. | *Cuando se establece en 300px:* La ventana emergente tendrá 300 píxeles de alto. *Cuando se establece en 500px:* La ventana emergente tendrá 500 píxeles de alto. Asegúrese de que sea lo suficientemente alta como para mostrar todos los campos del formulario sin necesidad de desplazarse. | 300-450px (ajustar según el tipo de formulario seleccionado) | El tipo de formulario elegido tiene muchos campos, y a 300px, los clientes tienen que desplazarse. Lo aumenta a 450px para mostrar todo. |
| **Color de fondo del PopUp** | Establece el color de fondo de la ventana emergente. Normalmente puede usar un selector de color o introducir un código de color hexadecimal (por ejemplo, #FFFFFF para blanco). | *Cuando se establece en #FFFFFF:* El fondo de la ventana emergente será blanco. *Cuando se establece en #F0F0F0:* El fondo de la ventana emergente será gris claro. Esto ayuda a que la ventana emergente coincida con el esquema de color de su tienda. | #FFFFFF (Blanco) o un color que complemente su tema. | Su tienda utiliza un tema oscuro, por lo que establece el fondo en un gris oscuro (#333333) para mayor coherencia. |
| **Color del borde del PopUp** | Establece el color del borde alrededor de la ventana emergente. | *Cuando se establece en #CCCCCC:* El borde de la ventana emergente será gris claro. *Cuando se establece en transparente:* No se mostrará ningún borde visible. | #CCCCCC (Gris claro) o transparente | Desea un borde sutil para definir la ventana emergente, por lo que elige un gris claro. |
| **Radio del borde del PopUp (píxeles)** | Controla la redondez de las esquinas de la ventana emergente. Un valor de 0 significa esquinas afiladas, valores más altos crean esquinas más redondeadas. | *Cuando se establece en 0:* La ventana emergente tendrá esquinas afiladas y cuadradas. *Cuando se establece en 10:* La ventana emergente tendrá esquinas ligeramente redondeadas. | 5-10px | Prefiere un aspecto más suave y moderno, por lo que establece el radio del borde en 8px. |
| **Color de fondo de la superposición** | Establece el color del fondo atenuado que aparece detrás de la ventana emergente. Esto ayuda a centrar la atención en la ventana emergente. | *Cuando se establece en #000000:* La superposición será negra. *Cuando se establece en #FFFFFF:* La superposición será blanca. | #000000 (Negro) | Desea una superposición oscura y transparente para separar claramente la ventana emergente del contenido principal. |
| **Opacidad de la superposición (0-1)** | Controla la transparencia del fondo de la superposición. 0 es totalmente transparente, 1 es totalmente opaco. | *Cuando se establece en 0.5:* La superposición será 50% transparente. *Cuando se establece en 0.8:* La superposición será 80% opaca. | 0.7-0.8 | Desea que el contenido de fondo sea ligeramente visible pero claramente atenuado, por lo que lo establece en 0.7. |
| **Color del botón de cerrar** | Establece el color del botón 'X' (cerrar) de la ventana emergente. | *Cuando se establece en #000000:* El botón de cerrar será negro. *Cuando se establece en #FF0000:* El botón de cerrar será rojo. | #000000 (Negro) | Su tienda utiliza un color de acento rojo, por lo que hace que el botón de cerrar sea rojo para mayor coherencia. |
| **Color de fondo del botón de cerrar** | Establece el color de fondo del botón 'X' (cerrar). | *Cuando se establece en #FFFFFF:* El fondo del botón de cerrar será blanco. *Cuando se establece en transparente:* No se aplicará ningún color de fondo. | transparente | Desea que el botón de cerrar se integre en la ventana emergente, por lo que establece su fondo en transparente. |
| **Habilitar Google reCAPTCHA** | Activa Google reCAPTCHA para los formularios de inicio de sesión y registro dentro de la ventana emergente, ayudando a prevenir el spam y los registros de bots. | *Cuando está habilitado:* reCAPTCHA aparecerá en los formularios, requiriendo que los usuarios verifiquen que no son robots. *Cuando está deshabilitado:* No habrá reCAPTCHA presente. | SÍ (si tiene claves reCAPTCHA) | Está experimentando muchos registros de spam, por lo que habilita reCAPTCHA para filtrarlos. |
| **Clave del sitio reCAPTCHA** | Su clave pública del sitio reCAPTCHA, obtenida de Google. Requerida si reCAPTCHA está habilitado. | *Cuando se introduce correctamente:* reCAPTCHA funcionará. *Cuando es incorrecta o está vacía:* reCAPTCHA no funcionará, lo que podría bloquear a usuarios legítimos o no evitar bots. | Su clave real del sitio Google reCAPTCHA | Ha registrado su sitio con Google reCAPTCHA y pega la clave del sitio proporcionada aquí. |
| **Clave secreta reCAPTCHA** | Su clave secreta privada de reCAPTCHA, obtenida de Google. Requerida si reCAPTCHA está habilitado. | *Cuando se introduce correctamente:* reCAPTCHA funcionará. *Cuando es incorrecta o está vacía:* reCAPTCHA no funcionará. | Su clave secreta real de Google reCAPTCHA | Ha registrado su sitio con Google reCAPTCHA y pega la clave secreta proporcionada aquí. |

#### 2.1.1 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar PopUp Login | SÍ | Activa/desactiva la función de inicio de sesión emergente. |
| Configuración del módulo | Tipo de formulario PopUp | (Elegir según el diseño) | Selecciona el estilo visual del formulario de inicio de sesión. |
| Configuración del módulo | Ancho del PopUp (píxeles) | 400-500px | Controla el ancho de la ventana emergente. |
| Configuración del módulo | Altura del PopUp (píxeles) | 300-450px | Controla la altura de la ventana emergente. |
| Configuración del módulo | Color de fondo del PopUp | #FFFFFF | Establece el color de fondo de la ventana emergente. |
| Configuración del módulo | Color del borde del PopUp | #CCCCCC o transparente | Establece el color del borde de la ventana emergente. |
| Configuración del módulo | Radio del borde del PopUp (píxeles) | 5-10px | Controla la redondez de las esquinas de la ventana emergente. |
| Configuración del módulo | Color de fondo de la superposición | #000000 | Establece el color del fondo atenuado detrás de la ventana emergente. |
| Configuración del módulo | Opacidad de la superposición (0-1) | 0.7-0.8 | Controla la transparencia del fondo de la superposición. |
| Configuración del módulo | Color del botón de cerrar | #000000 | Establece el color del botón de cerrar de la ventana emergente. |
| Configuración del módulo | Color de fondo del botón de cerrar | transparente | Establece el color de fondo del botón de cerrar. |
| Configuración del módulo | Habilitar Google reCAPTCHA | SÍ (si hay claves disponibles) | Activa reCAPTCHA para la protección contra bots. |
| Configuración del módulo | Clave del sitio reCAPTCHA | Su clave real | Clave pública para la verificación de reCAPTCHA. |
| Configuración del módulo | Clave secreta reCAPTCHA | Su clave real | Clave privada para la verificación de reCAPTCHA. |

## 3. Solución de problemas para el comerciante y preguntas frecuentes (FAQ)

**P1: La ventana emergente no aparece cuando hago clic en "Iniciar sesión". ¿Qué debo hacer?**
R:

1.  **Verificar el estado del módulo:** Asegúrese de que la opción "Habilitar PopUp Login" esté configurada en SÍ en la configuración del módulo.
2.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los archivos de caché antiguos impiden que se cargue la nueva funcionalidad del módulo.
3.  **Compatibilidad del tema:** Algunos temas altamente personalizados pueden usar formas no estándar de manejar los enlaces de inicio de sesión. Verifique si su tema tiene configuraciones o anulaciones específicas para el inicio de sesión. Si los problemas persisten, póngase en contacto con el soporte de MyPresta.eu.

**P2: La ventana emergente se ve extraña o no coincide con el estilo de mi tema.**
R:

1.  **Ajustar la configuración de estilo:** Vaya a la configuración del módulo y experimente con "Color de fondo del PopUp", "Color del borde del PopUp", "Radio del borde del PopUp", "Color de fondo de la superposición" y "Opacidad de la superposición".
2.  **Tipo de formulario:** Pruebe diferentes opciones de "Tipo de formulario PopUp" para ver si otro diseño se integra mejor con su tema.
3.  **CSS personalizado:** Si la configuración básica no es suficiente, su webmaster podría necesitar añadir CSS personalizado a su tema para anular los estilos predeterminados del módulo (consulte la Sección 7.5 para obtener detalles sobre el archivo CSS).

**P3: reCAPTCHA no funciona en los formularios de la ventana emergente.**
R:

1.  **Habilitar reCAPTCHA:** Asegúrese de que "Habilitar Google reCAPTCHA" esté configurado en SÍ.
2.  **Verificar claves:** Vuelva a verificar que sus "Clave del sitio reCAPTCHA" y "Clave secreta reCAPTCHA" estén correctamente introducidas en la configuración del módulo. Estas distinguen entre mayúsculas y minúsculas.
3.  **Configuración de Google reCAPTCHA:** Asegúrese de que su dominio esté correctamente registrado en su cuenta de Google reCAPTCHA.
4.  **Borrar caché:** Siempre borre la caché de PrestaShop después de realizar cambios en la configuración de reCAPTCHA.

**P4: La ventana emergente es demasiado grande/pequeña en mi teléfono móvil.**
R:

1.  **Ajustar ancho/alto:** Modifique "Ancho del PopUp (píxeles)" y "Altura del PopUp (píxeles)" en la configuración del módulo. Aunque estos son valores en píxeles, el módulo está diseñado para ser responsivo, por lo que ajustarlos influirá en su escalado en diferentes dispositivos.
2.  **Probar la capacidad de respuesta:** Utilice las herramientas de desarrollo de su navegador (F12) para simular diferentes dispositivos móviles y ajustar las dimensiones.

**P5: ¿Cómo traduzco el texto dentro de la ventana emergente?**
R:

1.  **Traducir módulo:** En su Back Office de PrestaShop, vaya a **Internacional > Traducciones**.
2.  **Seleccionar opciones:**
    - Tipo de traducción: "Traducciones de módulos instalados"
    - Seleccione su tema: Su tema actual
    - Seleccione su idioma: El idioma que desea traducir
3.  **Buscar módulo:** Busque "PopUp Login Pro" (o `popuplogin`).
4.  **Traducir campos:** Encontrará todas las cadenas traducibles utilizadas por el módulo. Introduzca sus traducciones y guarde.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura

El módulo PopUp Login Pro sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente los controladores frontales para las solicitudes AJAX y los hooks para la integración en el tema. Utiliza JavaScript para interceptar los clics en los enlaces de inicio de sesión estándar y mostrar la ventana emergente, cargando contenido dinámicamente a través de AJAX. La configuración se gestiona a través del método `getContent()` de la clase principal del módulo, almacenando la configuración en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:
    -   `controllers/front/index.php`
        -   **Nombre de la clase**: `PopUpLoginIndexModuleFrontController`
        -   **Clase padre**: `ModuleFrontController`
        -   **Responsabilidad**: Este controlador probablemente sirve como un punto de entrada general o maneja la configuración inicial para las interacciones del front-office, aunque sus métodos específicos definirían su rol exacto. Podría ser responsable de renderizar la estructura inicial de la ventana emergente o de manejar llamadas AJAX no relacionadas con el inicio de sesión.
    -   `controllers/front/loginbox.php`
        -   **Nombre de la clase**: `PopUpLoginLoginBoxModuleFrontController`
        -   **Clase padre**: `ModuleFrontController`
        -   **Responsabilidad**: Este es el controlador principal para manejar la lógica del formulario de inicio de sesión y registro. Responde a las solicitudes AJAX para mostrar el contenido del formulario de inicio de sesión/registro, procesar los intentos de inicio de sesión, manejar nuevos registros y gestionar las solicitudes de "olvidé mi contraseña". Probablemente devuelve fragmentos HTML o respuestas JSON al JavaScript para su inserción dinámica en la ventana emergente.

### 4.3 Clases y modelos principales (`classes/`)

Según el inventario proporcionado, no hay clases personalizadas ni definiciones de `ObjectModel` dentro del directorio `classes/`. El módulo probablemente aprovecha las clases principales existentes de PrestaShop para la gestión de clientes (`Customer`, `Context`, `Tools`) y el almacenamiento de configuración estándar.

### 4.4 Activos JavaScript (`views/js/`)

-   `popuplogin/popuplogin.js`
    -   **Alcance**: Front-office.
    -   **Detalles**: Este es el archivo JavaScript principal para la funcionalidad de front-end del módulo.
        -   **Escuchadores de eventos**: Vincula escuchadores de eventos a varios elementos, de manera más crítica a los enlaces estándar de inicio de sesión/cuenta (por ejemplo, `a[href*="controller=authentication"]`, `a[href*="my-account"]`). Intercepta los eventos de clic en estos enlaces.
        -   **Llamadas AJAX**: Cuando se hace clic en un enlace de inicio de sesión, evita la navegación predeterminada e inicia una solicitud AJAX a `popuplogin/controllers/front/loginbox.php` (o similar) para obtener el HTML del formulario de inicio de sesión/registro.
        -   **Manipulación del DOM**: Crea e inserta dinámicamente la superposición de la ventana emergente y el contenido del formulario de inicio de sesión en el DOM. Maneja la visualización/ocultación de la ventana emergente, la gestión de la superposición y, potencialmente, el cambio entre las vistas de inicio de sesión y registro dentro de la ventana emergente.
        -   **Envío de formularios**: Probablemente intercepta los envíos de formularios dentro de la ventana emergente (inicio de sesión, registro, olvidé mi contraseña) y los envía a través de AJAX al controlador `loginbox.php`, procesando las respuestas (por ejemplo, mostrando mensajes de éxito, mensajes de error o redirigiendo al iniciar sesión correctamente).
        -   **UI/UX**: Gestiona los efectos visuales de la ventana emergente (por ejemplo, fundido de entrada/salida, centrado).
        -   **Integración de reCAPTCHA**: Si reCAPTCHA está habilitado, este script es responsable de renderizar el widget reCAPTCHA e incluir su token en los envíos de formularios AJAX.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `popuplogin/css.css`
    -   **Alcance**: Estilo del cliente del front-office.
    -   **Detalles**: Este archivo probablemente contiene estilos generales y fundamentales para el contenedor de la ventana emergente, la superposición y, potencialmente, elementos de formulario comunes. Podría incluir estilos de reinicio o reglas de diseño básicas.
    -   **Selectores clave**: `.popuplogin-overlay`, `.popuplogin-popup`, `.popuplogin-close-btn`.
-   `popuplogin/popuplogin.css`
    -   **Alcance**: Estilo del cliente del front-office.
    -   **Detalles**: Este archivo probablemente contiene el estilo más específico y detallado para los diversos tipos de formularios de ventana emergente, incluidos los campos de entrada, los botones, los mensajes de error y los ajustes responsivos. Definirá las diferencias visuales entre las opciones de "Tipo de formulario PopUp".
    -   **Selectores clave**: `.popuplogin-form-type-1`, `.popuplogin-form-type-2`, `.popuplogin-input`, `.popuplogin-button`, `.popuplogin-error-message`.
    -   **Anulación del desarrollador**: Los desarrolladores pueden anular estos estilos en el `custom.css` de su tema o creando un tema hijo para modificar la apariencia sin editar directamente los archivos del módulo.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `popuplogin/dashboardZoneOne.tpl`
        -   **Hook**: Probablemente `displayDashboardZoneOne` (o un hook de panel similar).
        -   **Propósito**: Esta plantilla es probablemente para mostrar un pequeño bloque de información o estadísticas rápidas relacionadas con el módulo PopUp Login Pro en el panel de control del Back Office de PrestaShop. Es una plantilla orientada al administrador.
    -   `popuplogin/displayPopUpLogin.tpl`
        -   **Hook**: Esta plantilla es probablemente renderizada por el controlador frontal `loginbox.php` y contiene la estructura HTML real para el formulario de inicio de sesión/registro que aparece dentro de la ventana emergente. No está directamente enganchada a un hook `display` en el tema, sino que se carga dinámicamente.
        -   **Propósito**: Renderiza los formularios de inicio de sesión, registro y recuperación de contraseña, incluidos los campos de entrada, los botones y, potencialmente, los marcadores de posición de reCAPTCHA.
    -   `popuplogin/header.tpl`
        -   **Hook**: Probablemente `displayHeader`.
        -   **Propósito**: Esta plantilla es responsable de incluir los archivos CSS y JavaScript del módulo (`popuplogin.js`, `css.css`, `popuplogin.css`) en la sección `<head>` de las páginas del front-office, asegurando que se carguen antes de que se active la funcionalidad del módulo.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:
    -   El módulo no crea tablas SQL personalizadas.
    -   La configuración se almacena en la tabla `ps_configuration` utilizando claves típicamente prefijadas con `POPUPLOGIN_` (por ejemplo, `POPUPLOGIN_ENABLED`, `POPUPLOGIN_FORM_TYPE`, `POPUPLOGIN_WIDTH`, `POPUPLOGIN_RECAPTCHA_SITE_KEY`).
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Inyecta los archivos CSS y JavaScript del módulo para la funcionalidad de front-end. |
| `displayDashboardZoneOne` | En el panel de control del Back Office de PrestaShop. | Muestra un bloque de información o widget para el módulo en el panel de administración. |
| (Hooks implícitos) | Activado por la intercepción de JavaScript de los enlaces de inicio de sesión estándar. | El JavaScript del módulo intercepta los clics en elementos que normalmente conducirían a los controladores `authentication` o `my-account`, y luego utiliza AJAX para cargar dinámicamente contenido de sus propios controladores frontales. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo PopUp Login Pro, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar que su módulo funcione perfectamente y se integre sin problemas con su tienda PrestaShop.

---
title: "Preguntar sobre el producto gratis - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Preguntar sobre el producto gratis' de MyPresta.eu."
sidebar:
  label: "Preguntar sobre el producto gratis - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Ask about product free en MyPresta.eu](https://mypresta.eu/modules/front-office-features/ask-about-product-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/ask-about-product-free/)
>
> ---


# Preguntar sobre el producto gratis

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Preguntar sobre el producto gratis", donde usted controla su comportamiento y apariencia.

- **Ubicación del menú:** Back Office > Módulos > Gestor de módulos > "Preguntar sobre el producto gratis" > Configurar

#### Ajustes y opciones:

1.  **Mostrar resumen del producto dentro de la ventana emergente**

    -   **Qué hace este ajuste:** Controla si se muestra un pequeño resumen del producto (como su nombre e imagen) dentro del formulario emergente "Preguntar sobre el producto".
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* El formulario emergente incluirá una breve descripción del producto sobre el que el cliente está preguntando. Esto ayuda al cliente a confirmar que está preguntando sobre el artículo correcto y le proporciona contexto cuando recibe el correo electrónico.
        -   *Cuando está deshabilitado (No):* El formulario emergente solo contendrá los campos para el nombre del cliente, el correo electrónico y la pregunta, sin ningún resumen específico del producto.
    -   **Valor recomendado:** **Sí**.
    -   **Escenario / ejemplo del comerciante:** Habilitar esto ayuda a evitar confusiones. Un cliente podría tener varias pestañas abiertas y olvidar sobre qué producto está preguntando. El resumen lo confirma para ellos y para usted.
2.  **Habilitado**

    -   **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar toda la función "Preguntar sobre el producto" en su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* El botón "Preguntar sobre el producto" aparecerá en las páginas de producto y el formulario emergente será funcional.
        -   *Cuando está deshabilitado (No):* El botón "Preguntar sobre el producto" se ocultará de las páginas de producto y los clientes no podrán usar esta función.
    -   **Valor recomendado:** **Sí** (para usar el módulo).
    -   **Escenario / ejemplo del comerciante:** Podría deshabilitarlo temporalmente si está realizando mantenimiento o si prefiere manejar todas las consultas a través de un canal diferente durante un período.
3.  **Cumple con el RGPD**

    -   **Qué hace este ajuste:** Activa una casilla de verificación en el formulario "Preguntar sobre el producto", requiriendo que los clientes acepten explícitamente su política de privacidad antes de enviar su pregunta. Esto ayuda a su tienda a cumplir con el RGPD y otras regulaciones de protección de datos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* Aparecerá una casilla de verificación obligatoria en el formulario, típicamente indicando algo como "Acepto la política de privacidad". El cliente debe marcar esta casilla para enviar su pregunta.
        -   *Cuando está deshabilitado (No):* La casilla de verificación de la política de privacidad no se mostrará y los clientes podrán enviar sus preguntas sin consentimiento explícito.
    -   **Valor recomendado:** **Sí**.
    -   **Escenario / ejemplo del comerciante:** Si su tienda opera en regiones con leyes estrictas de protección de datos (como la UE), habilitar esto es crucial para el cumplimiento legal.
4.  **Página de política de privacidad**

    -   **Qué hace este ajuste:** Si "Cumple con el RGPD" está habilitado, este ajuste le permite seleccionar qué página CMS (Sistema de Gestión de Contenidos) de su tienda se vinculará como su política de privacidad.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se selecciona una página:* El texto "Acepto la política de privacidad" en el formulario emergente incluirá un enlace clicable a la página CMS elegida, permitiendo a los clientes revisar fácilmente su política.
        -   *Cuando no se selecciona ninguna página (o "Cumple con el RGPD" es No):* No se proporcionará ningún enlace, o la función RGPD no estará activa.
    -   **Valor recomendado:** Seleccione la página oficial de política de privacidad de su tienda.
    -   **Escenario / ejemplo del comerciante:** Debe tener una página CMS dedicada que describa sus prácticas de manejo de datos. Este ajuste asegura que los clientes puedan acceder a ella fácilmente.
5.  **Título del correo electrónico**

    -   **Qué hace este ajuste:** Define la línea de asunto para el correo electrónico que recibe cuando un cliente envía una pregunta a través del formulario.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece un título específico (por ejemplo, "Nueva pregunta de producto"):* Todos los correos electrónicos entrantes de este módulo usarán esta línea de asunto, lo que los hace fáciles de identificar en su bandeja de entrada.
        -   *Cuando se deja por defecto:* El módulo usará su línea de asunto predeterminada, que podría ser menos descriptiva.
    -   **Valor recomendado:** Algo claro y descriptivo, como "Nueva pregunta de producto de [Nombre de su tienda]".
    -   **Escenario / ejemplo del comerciante:** Una línea de asunto clara le ayuda a priorizar y responder rápidamente a las consultas de los clientes, especialmente si recibe muchos correos electrónicos diariamente.
6.  **Destinatario del correo electrónico del formulario**

    -   **Qué hace este ajuste:** Especifica la(s) dirección(es) de correo electrónico a la(s) que se enviarán las preguntas de los clientes enviadas a través del formulario "Preguntar sobre el producto".
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce una o más direcciones de correo electrónico (separadas por comas):* El módulo enviará todas las consultas de los clientes a estas direcciones especificadas.
        -   *Cuando se deja vacío:* El módulo podría usar por defecto el correo electrónico de contacto principal de la tienda, o la función podría no funcionar correctamente.
    -   **Valor recomendado:** Su dirección de correo electrónico de atención al cliente (por ejemplo, `soporte@sutienda.com`) o un correo electrónico dedicado para consultas de productos. Puede añadir varios correos electrónicos separados por comas si varios miembros del equipo necesitan recibirlos.
    -   **Escenario / ejemplo del comerciante:** Dirigir estos correos electrónicos al equipo correcto asegura respuestas rápidas, mejorando la satisfacción del cliente.
7.  **Protección ReCaptcha (v2)**

    -   **Qué hace este ajuste:** Integra Google reCAPTCHA v2 (la casilla de verificación "No soy un robot") en el formulario "Preguntar sobre el producto" para proteger contra el spam y los envíos automatizados.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (Sí):* La casilla de verificación reCAPTCHA aparecerá en el formulario, requiriendo que los clientes pasen el desafío antes de enviar.
        -   *Cuando está deshabilitado (No):* El formulario no tendrá protección reCAPTCHA, lo que lo hace potencialmente vulnerable a los bots de spam.
    -   **Valor recomendado:** **Sí**.
    -   **Escenario / ejemplo del comerciante:** Si está recibiendo muchas consultas de spam a través del formulario, habilitar reCAPTCHA es esencial para filtrar los mensajes ilegítimos.
8.  **Clave del sitio reCaptcha**

    -   **Qué hace este ajuste:** Esta es la clave pública proporcionada por Google reCAPTCHA que permite a su sitio web mostrar el widget reCAPTCHA. Obtiene esta clave cuando registra su sitio con Google reCAPTCHA.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce correctamente:* El widget reCAPTCHA se mostrará y funcionará correctamente en su formulario.
        -   *Cuando es incorrecta o está vacía:* reCAPTCHA no funcionará y podría ver un mensaje de error o el formulario no se enviará.
    -   **Valor recomendado:** La clave del sitio obtenida de su cuenta de Google reCAPTCHA.
    -   **Escenario / ejemplo del comerciante:** Necesita registrar su dominio con Google reCAPTCHA (v2) para obtener tanto una clave del sitio como una clave secreta.
9.  **Clave secreta reCaptcha**

    -   **Qué hace este ajuste:** Esta es la clave privada proporcionada por Google reCAPTCHA que permite a su servidor verificar la respuesta de reCAPTCHA. Se utiliza para la validación del lado del servidor.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce correctamente:* Su servidor puede verificar con éxito si un cliente ha pasado el desafío reCAPTCHA.
        -   *Cuando es incorrecta o está vacía:* Incluso si el widget reCAPTCHA se muestra, el envío del formulario fallará la validación y la pregunta no se enviará.
    -   **Valor recomendado:** La clave secreta obtenida de su cuenta de Google reCAPTCHA.
    -   **Escenario / ejemplo del comerciante:** Esta clave es crucial para el aspecto de seguridad de reCAPTCHA, asegurando que solo se procesen los envíos legítimos.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Mostrar resumen del producto dentro de la ventana emergente | Sí | Muestra los detalles del producto en la ventana emergente para mayor claridad. |
| Configuración del módulo | Habilitado | Sí | Activa/desactiva la función "Preguntar sobre el producto". |
| Configuración del módulo | Cumple con el RGPD | Sí | Añade una casilla de verificación de acuerdo de política de privacidad al formulario. |
| Configuración del módulo | Página de política de privacidad | Seleccione su página CMS de Política de privacidad | Enlaza a la política de privacidad de su tienda para el RGPD. |
| Configuración del módulo | Título del correo electrónico | "Nueva pregunta de producto de [Nombre de su tienda]" | Establece la línea de asunto para los correos electrónicos de preguntas entrantes. |
| Configuración del módulo | Destinatario del correo electrónico del formulario | Su correo electrónico de atención al cliente (por ejemplo, `soporte@sutienda.com`) | Especifica dónde se envían las preguntas de los clientes. |
| Configuración del módulo | Protección ReCaptcha (v2) | Sí | Habilita Google reCAPTCHA para evitar el spam. |
| Configuración del módulo | Clave del sitio reCaptcha | Su clave del sitio de Google reCAPTCHA | Clave pública para mostrar el widget reCAPTCHA. |
| Configuración del módulo | Clave secreta reCaptcha | Su clave secreta de Google reCAPTCHA | Clave privada para la validación de reCAPTCHA del lado del servidor. |

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### AdminAapfreeQuestionController (Back Office > Preguntar sobre el producto > Preguntas)

Esta pantalla de administración dedicada le permite ver y gestionar todas las preguntas enviadas a través del formulario "Preguntar sobre el producto".

-   **Nombre de la pantalla y ubicación del menú:** Back Office > **Preguntar sobre el producto** (nuevo elemento de menú) > **Preguntas**
-   **Acciones y ajustes disponibles:**
    -   **Tabla de listado:** Esta pantalla muestra una tabla de todas las preguntas enviadas. Cada fila típicamente muestra:
        -   **ID:** Identificador único de la pregunta.
        -   **Nombre del cliente:** El nombre proporcionado por el cliente.
        -   **Correo electrónico del cliente:** La dirección de correo electrónico proporcionada por el cliente.
        -   **Nombre del producto:** El nombre del producto sobre el que se hace la pregunta.
        -   **Pregunta:** Un fragmento o el texto completo de la pregunta del cliente.
        -   **Fecha de adición:** Cuándo se envió la pregunta.
        -   **Estado:** (por ejemplo, Nuevo, Respondido, Pendiente) - *Nota: El dossier del módulo no indica explícitamente un campo de estado, pero es una característica común para tales listas. Si no está presente, simplemente listará todas las preguntas.*
    -   **Ver detalles:** Normalmente puede hacer clic en una pregunta de la lista para ver sus detalles completos, incluido el texto completo de la pregunta y, potencialmente, el enlace del producto.
    -   **Eliminar:** Opciones para eliminar preguntas individuales o, potencialmente, eliminar varias preguntas seleccionadas.
-   **Efecto de los cambios:**
    -   **Ver preguntas:** Le permite revisar todas las consultas de los clientes en una ubicación centralizada dentro de su back office de PrestaShop, incluso si también las recibe por correo electrónico.
    -   **Eliminar preguntas:** Elimina el registro de la pregunta de su base de datos. Esto es útil para limpiar consultas antiguas o irrelevantes.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Revise regularmente esta lista de "Preguntas" (o su bandeja de entrada de correo electrónico, según lo configurado) en busca de nuevas consultas.
    2.  Priorice y responda a las preguntas rápidamente para mantener un buen servicio al cliente.
    3.  Después de responder, puede eliminar la pregunta de esta lista para mantenerla ordenada, o si el módulo lo admite, marcarla como "Respondida".

#### index.php (aapfree/controllers/admin/index.php)

Este archivo es típicamente un marcador de posición o un redireccionador dentro del directorio `controllers/admin` y no representa una pantalla distinta y configurable para el comerciante. Es una práctica estándar de PrestaShop tener un `index.php` en subdirectorios para evitar la lista de directorios, o podría contener una lógica de enrutamiento básica. No gestiona una tabla o entidad específica para la interacción directa del comerciante.

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: El botón "Preguntar sobre el producto" no aparece en las páginas de mis productos.**

-   **R:** Primero, verifique si el módulo está "Habilitado" en sus ajustes de configuración (Back Office > Módulos > Gestor de módulos > Preguntar sobre el producto gratis > Configurar). Si lo está, intente borrar la caché de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché). A veces, los conflictos de tema o las estructuras de tema personalizadas específicas pueden impedir que aparezca el botón. Si sigue sin aparecer, póngase en contacto con su webmaster o con el soporte de MyPresta.eu.

**P2: No recibo ningún correo electrónico cuando los clientes envían preguntas.**

-   **R:**
    1.  Verifique el ajuste "Destinatario del correo electrónico del formulario" en la configuración del módulo. Asegúrese de que la(s) dirección(es) de correo electrónico sean correctas y estén separadas por comas si hay varias.
    2.  Revise su carpeta de spam/correo no deseado en la bandeja de entrada del correo electrónico del destinatario.
    3.  Asegúrese de que la configuración de correo electrónico de su tienda esté correctamente configurada en PrestaShop (Parámetros avanzados > Correo electrónico). Pruebe a enviar un correo electrónico general desde PrestaShop para confirmar que su servidor de correo funciona.
    4.  Si ReCAPTCHA está habilitado, asegúrese de que tanto la "Clave del sitio reCaptcha" como la "Clave secreta reCaptcha" estén correctamente introducidas. Las claves incorrectas impedirán los envíos.

**P3: El reCAPTCHA no funciona o veo un mensaje de error.**

-   **R:** Esto generalmente significa que sus claves de reCAPTCHA son incorrectas o no están configuradas correctamente con Google.
    1.  Vaya a la consola de administración de Google reCAPTCHA y asegúrese de que su dominio esté correctamente registrado para reCAPTCHA v2.
    2.  Copie la "Clave del sitio" y la "Clave secreta" exactamente como las proporciona Google y péguelas en los campos de configuración del módulo.
    3.  Borre la caché de PrestaShop después de realizar cambios.

**P4: ¿Cómo cambio el texto del botón "Preguntar sobre el producto" o del formulario emergente?**

-   **R:** Puede traducir las cadenas de texto del módulo directamente dentro de PrestaShop. Vaya a **Internacional > Traducciones**, seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Preguntar sobre el producto gratis". Encontrará todas las cadenas traducibles allí, incluidas las etiquetas de los botones, las etiquetas de los campos del formulario y los mensajes de confirmación.

**P5: La ventana emergente se ve extraña o no se muestra correctamente en mi teléfono móvil.**

-   **R:** Aunque el módulo está diseñado para ser adaptable, los temas personalizados a veces pueden anular o entrar en conflicto con su estilo.
    1.  Borre la caché de su navegador y la caché de PrestaShop.
    2.  Si el problema persiste, es probable que sea un conflicto de CSS con su tema. Su webmaster o un desarrollador necesitaría inspeccionar la página utilizando las herramientas de desarrollo del navegador para identificar y resolver el conflicto de CSS.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Preguntar sobre el producto gratis" sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, centrándose principalmente en la interacción del front-office y la administración de preguntas enviadas en el back-office. Aprovecha el sistema de hooks de PrestaShop para la integración en las páginas de productos y utiliza controladores frontales dedicados para las solicitudes AJAX y el envío de formularios. El componente del back-office proporciona una interfaz de gestión de listas simple para las preguntas.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `controllers/front/index.php`
        -   **Nombre de la clase y clase padre:** `AapfreeIndexModuleFrontController` que extiende `ModuleFrontController`.
        -   **Responsabilidad:** Este controlador probablemente maneja la lógica de visualización inicial para el componente de front-office del módulo, posiblemente renderizando el botón o preparando datos para la ventana emergente. También podría servir como un controlador general para las rutas de front-office específicas del módulo.
    -   `controllers/front/question.php`
        -   **Nombre de la clase y clase padre:** `AapfreeQuestionModuleFrontController` que extiende `ModuleFrontController`.
        -   **Responsabilidad:** Este es el controlador principal para manejar el envío del formulario "Preguntar sobre el producto". Recibe datos POST del formulario emergente, valida las entradas (incluido reCAPTCHA si está habilitado), procesa la pregunta, envía el correo electrónico a los destinatarios configurados y almacena la pregunta en la base de datos. Devuelve respuestas JSON para las solicitudes AJAX (por ejemplo, mensajes de éxito/error).
-   **Controladores de administración de Back-Office**:

    -   `controllers/admin/AdminAapfreeQuestion.php`
        -   **Nombre de la clase y clase padre:** `AdminAapfreeQuestionController` que extiende `ModuleAdminController`.
        -   **Nombre de la pestaña y entidad gestionada:** Este controlador crea y gestiona la pestaña "Preguntas" bajo el menú "Preguntar sobre el producto" en el Back Office de PrestaShop. Es responsable de mostrar una lista (cuadrícula) de todas las preguntas enviadas, permitiendo a los administradores ver detalles y eliminar entradas. Interactúa con el `ObjectModel` `AapfreeQuestion` (si existe, de lo contrario directamente con la base de datos).
    -   `controllers/admin/index.php`
        -   **Nombre de la clase y clase padre:** No es un controlador funcional en el sentido tradicional.
        -   **Nombre de la pestaña y entidad gestionada:** Este archivo es una medida de seguridad estándar de PrestaShop para evitar la lista de directorios. Típicamente contiene un simple `header('Location: ../../index.php?controller=AdminHome');` o un redireccionamiento similar, o simplemente `<?php exit;`. No gestiona ninguna entidad específica ni proporciona una pantalla configurable.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo podría manejar las interacciones con la base de datos directamente dentro de sus controladores o el archivo principal del módulo, o podría usar un `ObjectModel` genérico para `aapfreequestion` si está definido implícitamente.

-   **Modelo implícito (probable):** Dado que `AdminAapfreeQuestionController` gestiona una tabla, existe un modelo `AapfreeQuestion` implícito, incluso si no está explícitamente en `classes/`. Este modelo se mapearía a la tabla de la base de datos `_aapfree_question`.
    -   **Tabla de la base de datos:** `ps_aapfree_question` (o similar, según el prefijo del módulo).
    -   **Extiende `ObjectModel`:** Sí, implícitamente.
    -   **Campos `$definition` (esperados):** `id_aapfree_question`, `id_product`, `customer_name`, `customer_email`, `question_text`, `date_add`.

### 4.4 Activos JavaScript (`views/js/`)

-   `aapfree/views/aapfree.js`
    -   **Alcance:** Front-office.
    -   **Escuchadores de eventos:**
        -   Vincula eventos de clic al botón "Preguntar sobre el producto" (`.aapfree-button`).
        -   Vincula eventos de envío al formulario "Preguntar sobre el producto" dentro de la ventana emergente (`#aapfree-form`).
        -   Maneja eventos relacionados con el widget reCAPTCHA (si está habilitado).
    -   **Manipulación del DOM:**
        -   Abre y cierra la ventana emergente modal (`#aapfree-modal`).
        -   Rellena los datos de resumen del producto en la ventana emergente.
        -   Muestra mensajes de éxito o error al usuario después del envío del formulario.
        -   Gestiona los estados de los campos del formulario (por ejemplo, deshabilitar el botón de envío durante AJAX).
    -   **Llamadas AJAX:**
        -   Envía datos del formulario a `AapfreeQuestionModuleFrontController` (por ejemplo, `index.php?fc=module&module=aapfree&controller=question`).
        -   Procesa las respuestas JSON del servidor.
    -   **Llamadas a SDK externos:** Inicializa y renderiza el widget de Google reCAPTCHA v2 si `aapfree_recaptcha` está habilitado, utilizando la `aapfree_recaptcha_sitekey`.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `aapfree/views/aapfree.css`
    -   **Alcance:** Estilo del cliente de Front-office.
    -   **Principales componentes de la interfaz de usuario y contenedores que estiliza:**
        -   El botón "Preguntar sobre el producto" (`.aapfree-button`).
        -   El contenedor de la ventana emergente modal (`#aapfree-modal`).
        -   Los elementos del formulario dentro de la ventana emergente (campos de entrada, áreas de texto, etiquetas, casillas de verificación).
        -   Visualización de mensajes de éxito y error.
        -   Ajustes responsivos para diferentes tamaños de pantalla.
    -   **Selectores de clase CSS clave que los desarrolladores pueden anular:** `.aapfree-button`, `.aapfree-modal`, `.aapfree-modal-content`, `.aapfree-form-group`, `.aapfree-product-summary`, `.aapfree-success-message`, `.aapfree-error-message`. Los desarrolladores pueden anular estos estilos en el `custom.css` de su tema o utilizando las funciones de personalización de temas de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `aapfree/views/aapfree-extra.tpl`
        -   **Hook:** `displayProductAdditionalInfo` (o un hook similar de página de producto como `displayProductButtons`, `displayProductActions`).
        -   **Salida de bloque visual:** Esta plantilla es responsable de renderizar el botón "Preguntar sobre el producto" en la página del producto. También contiene la estructura HTML para el formulario emergente modal, que inicialmente está oculto y se muestra mediante JavaScript. Incluye marcadores de posición para el resumen del producto, los campos del formulario, la casilla de verificación del RGPD y reCAPTCHA.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:

    -   `ps_aapfree_question`:
        -   `id_aapfree_question` (INT, CLAVE PRIMARIA, AUTO\_INCREMENT)
        -   `id_product` (INT, Clave externa a `ps_product`)
        -   `customer_name` (VARCHAR)
        -   `customer_email` (VARCHAR)
        -   `question_text` (TEXT)
        -   `date_add` (DATETIME)
        -   (Potencialmente otros campos como `ip_address`, `status`, `id_customer` si se implementan)
    -   **Registros de configuración (en `ps_configuration`):**
        -   `AAPFREE_TITLE`: Línea de asunto del correo electrónico.
        -   `AAPFREE_GDPR`: Estado de cumplimiento del RGPD (0/1).
        -   `AAPFREE_GDPRCMS`: ID de la página CMS para la política de privacidad.
        -   `AAPFREE_SUMMARY`: Estado de visualización del resumen del producto (0/1).
        -   `AAPFREE_RECAPTCHA`: Estado de protección reCAPTCHA (0/1).
        -   `AAPFREE_RECAPTCHA_SITEKEY`: Clave del sitio de Google reCAPTCHA.
        -   `AAPFREE_RECAPTCHA_SECRETKEY`: Clave secreta de Google reCAPTCHA.
        -   `AAPFREE_EMAILSLIST`: Lista de correos electrónicos de destinatarios separados por comas.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayProductAdditionalInfo` | En las páginas de productos, típicamente debajo de la descripción o el precio del producto. | Renderiza el botón "Preguntar sobre el producto" y la estructura modal emergente oculta. |
| `actionAdminControllerSetMedia` | Cuando un controlador de administración carga sus activos (CSS/JS). | Inyecta CSS (`aapfree.css`) y JavaScript (`aapfree.js`) específicos del módulo en el Back Office para `AdminAapfreeQuestionController`. |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Potencialmente utilizado para cargar variables JavaScript globales, CSS o el script de la API de Google reCAPTCHA si reCAPTCHA está habilitado. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Preguntar sobre el producto gratis", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo se dedica a garantizar el buen funcionamiento y la mejora continua de su módulo.

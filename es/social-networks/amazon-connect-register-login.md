---
title: "Conexión con Amazon (registro + inicio de sesión) - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Conexión con Amazon (registro + inicio de sesión)' de MyPresta.eu."
sidebar:
  label: "Conexión con Amazon (registro + inicio de sesión) - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Amazon connect (register + login) en MyPresta.eu](https://mypresta.eu/modules/social-networks/amazon-connect-register-login.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/amazon-connect-register-login/)
>
> ---


# Conexión con Amazon (registro + inicio de sesión)

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una comunicación segura con la API.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo de inicio de sesión de Amazon, donde vinculará su tienda PrestaShop a su cuenta de desarrollador de Amazon.

-   **aml\_ClientID (ID de Cliente de Amazon)**
    -   **Qué hace esta configuración:** Este es un identificador único proporcionado por Amazon cuando registra su aplicación (su tienda PrestaShop) con su servicio "Iniciar sesión con Amazon". Le indica a Amazon qué aplicación está solicitando la autenticación del usuario.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando se introduce correctamente:* Su botón "Iniciar sesión con Amazon" funcionará correctamente, permitiendo a los clientes autenticarse a través de su cuenta de Amazon.
        -   *Cuando es incorrecto o está vacío:* El botón "Iniciar sesión con Amazon" no funcionará, o los clientes encontrarán un error al intentar usarlo.
    -   **Valor recomendado:** El ID de Cliente obtenido de su Consola de Desarrollador de Amazon. Este campo no puede dejarse vacío para que el módulo funcione.
    -   **Escenario / ejemplo de comerciante:** Ha registrado su tienda PrestaShop como una aplicación en la Consola de Desarrollador de Amazon. Amazon le proporciona un "ID de Cliente" (por ejemplo, `amzn1.oauth-client.xxxxxxxxxxxxxxxxxxxxxxxxxxxx`). Debe copiar y pegar este ID exacto en este campo.
-   **aml\_ClientSecret (Secreto de Cliente de Amazon)**
    -   **Qué hace esta configuración:** Esta es una clave confidencial también proporcionada por Amazon, utilizada junto con el ID de Cliente para autenticar su aplicación de forma segura con los servidores de Amazon. Asegura que solo su aplicación legítima pueda solicitar datos de usuario.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando se introduce correctamente:* Su módulo puede comunicarse de forma segura con la API de Amazon para verificar las identidades de los usuarios.
        -   *Cuando es incorrecto o está vacío:* El proceso de autenticación fallará, ya que su tienda no puede identificarse de forma segura ante Amazon.
    -   **Valor recomendado:** El Secreto de Cliente obtenido de su Consola de Desarrollador de Amazon. Este campo no puede dejarse vacío para que el módulo funcione.
    -   **Escenario / ejemplo de comerciante:** Junto con el ID de Cliente, Amazon también le proporciona un "Secreto de Cliente" (por ejemplo, `yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy`). Este secreto debe mantenerse confidencial e introducirse con precisión aquí.
-   **aml\_RedirectURI (URI de Redirección de Amazon)**
    -   **Qué hace esta configuración:** Esta es la URL de su tienda PrestaShop a la que Amazon redirigirá el navegador del usuario *después* de que haya iniciado sesión o autorizado su aplicación en el sitio de Amazon. Es crucial para el flujo seguro del proceso de autenticación.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando se configura correctamente en ambos extremos (módulo y Consola de Desarrollador de Amazon):* Los usuarios son devueltos sin problemas a su tienda después de iniciar sesión en Amazon.
        -   *Cuando es incorrecto:* Los usuarios encontrarán un error después de iniciar sesión con Amazon, o no serán redirigidos de vuelta a su tienda correctamente. Esta URI también debe registrarse en la configuración de su Consola de Desarrollador de Amazon para su aplicación.
    -   **Valor recomendado:** Esto debería ser generado automáticamente por el módulo o ser una URL específica como `https://tutienda.com/module/amlogin/ajax_amlogin` (verifique la ruta exacta proporcionada por el módulo o la documentación de Amazon). Asegúrese de que coincida con la URI que registró en su Consola de Desarrollador de Amazon.
    -   **Escenario / ejemplo de comerciante:** Al configurar su aplicación en la Consola de Desarrollador de Amazon, se le pedirá "URLs de Retorno Permitidas". Debe introducir la URL exacta que este módulo utiliza para la redirección (por ejemplo, `https://www.tutienda.com/module/amlogin/ajax_amlogin`).
-   **Mostrar botón de inicio de sesión de Amazon en la cabecera**
    -   **Qué hace esta configuración:** Controla si el botón "Iniciar sesión con Amazon" aparece en la sección de cabecera de su tienda.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* El botón será visible en la cabecera, ofreciendo acceso inmediato al inicio de sesión de Amazon.
        -   *Cuando está deshabilitado:* El botón no aparecerá en la cabecera.
    -   **Valor recomendado:** SÍ, para máxima visibilidad y facilidad de acceso.
    -   **Escenario / ejemplo de comerciante:** Desea que los clientes vean la opción de inicio de sesión de Amazon tan pronto como lleguen a su sitio, por lo que habilita esto.
-   **Mostrar botón de inicio de sesión de Amazon en la columna izquierda**
    -   **Qué hace esta configuración:** Controla si el botón "Iniciar sesión con Amazon" aparece en la columna lateral izquierda de su tienda.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* El botón será visible en la columna izquierda, a menudo junto con otros bloques de navegación o de cuenta.
        -   *Cuando está deshabilitado:* El botón no aparecerá en la columna izquierda.
    -   **Valor recomendado:** SÍ, si su tema utiliza una columna izquierda y desea visibilidad persistente.
    -   **Escenario / ejemplo de comerciante:** Su tienda tiene una columna izquierda prominente y desea ofrecer la opción de inicio de sesión de Amazon allí mientras los clientes navegan por las categorías.
-   **Mostrar botón de inicio de sesión de Amazon en la columna derecha**
    -   **Qué hace esta configuración:** Controla si el botón "Iniciar sesión con Amazon" aparece en la columna lateral derecha de su tienda.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* El botón será visible en la columna derecha.
        -   *Cuando está deshabilitado:* El botón no aparecerá en la columna derecha.
    -   **Valor recomendado:** SÍ, si su tema utiliza una columna derecha y desea visibilidad persistente.
    -   **Escenario / ejemplo de comerciante:** Similar a la columna izquierda, si su tema utiliza una columna derecha, podría colocar el botón allí para mayor visibilidad.
-   **Mostrar botón de inicio de sesión de Amazon en la página de producto**
    -   **Qué hace esta configuración:** Controla si el botón "Iniciar sesión con Amazon" aparece en las páginas de detalles de productos individuales.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* El botón se mostrará en las páginas de productos, potencialmente cerca del botón "Añadir al carrito" o la descripción del producto.
        -   *Cuando está deshabilitado:* El botón no aparecerá en las páginas de productos.
    -   **Valor recomendado:** SÍ, ya que puede fomentar el inicio de sesión o el registro inmediato antes de añadir al carrito.
    -   **Escenario / ejemplo de comerciante:** Un cliente está viendo un producto y decide comprarlo. Ver el botón de inicio de sesión de Amazon le permite iniciar sesión o crear una cuenta rápidamente antes de proceder al pago.
-   **Mostrar botón de inicio de sesión de Amazon en el pie de página**
    -   **Qué hace esta configuración:** Controla si el botón "Iniciar sesión con Amazon" aparece en la sección de pie de página de su tienda.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* El botón será visible en el pie de página, proporcionando un punto de inicio de sesión alternativo.
        -   *Cuando está deshabilitado:* El botón no aparecerá en el pie de página.
    -   **Valor recomendado:** NO, a menos que tenga una razón de diseño específica. Otras ubicaciones ofrecen mejor visibilidad.
    -   **Escenario / ejemplo de comerciante:** Desea ofrecer la opción de inicio de sesión de Amazon, pero prefiere que no sea demasiado prominente, por lo que la coloca en el pie de página.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | `aml_ClientID` | Su ID de Cliente de Amazon | Identificador único para su aplicación con Amazon. **Requerido para la funcionalidad.** |
| Página de Configuración del Módulo | `aml_ClientSecret` | Su Secreto de Cliente de Amazon | Clave confidencial para una autenticación segura con Amazon. **Requerido para la funcionalidad.** |
| Página de Configuración del Módulo | `aml_RedirectURI` | URL autogenerada / Específica | URL a la que Amazon redirige a los usuarios después de iniciar sesión. **Debe coincidir con la Consola de Desarrollador de Amazon.** |
| Página de Configuración del Módulo | Mostrar en la Cabecera | SÍ | Muestra el botón en la cabecera de la tienda. |
| Página de Configuración del Módulo | Mostrar en la Columna Izquierda | SÍ | Muestra el botón en la barra lateral izquierda. |
| Página de Configuración del Módulo | Mostrar en la Columna Derecha | SÍ | Muestra el botón en la barra lateral derecha. |
| Página de Configuración del Módulo | Mostrar en la Página de Producto | SÍ | Muestra el botón en las páginas de productos individuales. |
| Página de Configuración del Módulo | Mostrar en el Pie de Página | NO | Muestra el botón en el pie de página de la tienda. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: El botón de inicio de sesión de Amazon aparece, pero no sucede nada cuando hago clic en él, o recibo un error.**
R: Esto generalmente indica un problema con su `aml_ClientID`, `aml_ClientSecret` o `aml_RedirectURI`.
-   **Verificación 1:** Vuelva a comprobar que ha copiado el ID de Cliente y el Secreto de Cliente exactamente desde su Consola de Desarrollador de Amazon a la configuración del módulo. Incluso un solo error de carácter causará un fallo.
-   **Verificación 2:** Verifique que la `aml_RedirectURI` en la configuración del módulo coincida exactamente con una de las "URLs de Retorno Permitidas" que ha registrado en su Consola de Desarrollador de Amazon para su aplicación. Preste atención a `http` vs `https` y a las barras finales.
-   **Verificación 3:** Borre la caché de su PrestaShop (Parámetros Avanzados > Rendimiento > Borrar caché) y la caché de su navegador.

**P: Mis clientes son redirigidos a Amazon, pero luego reciben un error o no son enviados de vuelta a mi tienda.**
R: Esto es casi con certeza una discrepancia de `aml_RedirectURI`. Vaya a su Consola de Desarrollador de Amazon, encuentre su aplicación y asegúrese de que la lista de "URLs de Retorno Permitidas" contenga la URL *exacta* que su módulo de PrestaShop está configurado para usar. Debe ser una coincidencia exacta, incluyendo `http/https` y cualquier subdirectorio.

**P: El botón de inicio de sesión de Amazon no aparece en las ubicaciones que he habilitado.**
R:
-   **Verificación 1:** Asegúrese de que el módulo esté habilitado y configurado correctamente en el Back Office.
-   **Verificación 2:** Borre la caché de su PrestaShop (Parámetros Avanzados > Rendimiento > Borrar caché). A veces, los cambios de plantilla no se reflejan inmediatamente.
-   **Verificación 3:** Su tema podría estar anulando los hooks estándar de PrestaShop. Si el botón aún no aparece, es posible que necesite un desarrollador web para insertar manualmente la llamada al hook del módulo en los archivos `.tpl` de su tema (consulte la Sección 7.6 para las plantillas relevantes).

**P: ¿Este módulo funciona con tiendas multi-idioma?**
R: Sí, el módulo debería heredar las capacidades multi-idioma de PrestaShop para cualquier texto que muestre. El proceso de inicio de sesión de Amazon en sí es gestionado por Amazon y normalmente se adaptará a la configuración de idioma de la cuenta de Amazon del usuario.

**P: ¿Puedo personalizar la apariencia del botón de inicio de sesión de Amazon?**
R: El módulo utiliza los activos estándar del botón de inicio de sesión de Amazon. Aunque no puede cambiar el diseño central del botón de Amazon (según las directrices de marca de Amazon), puede usar CSS personalizado (consulte la Sección 7.5) para ajustar su ubicación, márgenes o el contenedor que lo rodea para que se adapte mejor a su tema.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo "Conexión con Amazon (registro + inicio de sesión)" integra el servicio Login with Amazon (LWA) de Amazon en PrestaShop. Opera principalmente como un módulo estándar de PrestaShop, aprovechando los hooks para mostrar el botón de inicio de sesión en varias ubicaciones del front-office. La lógica central para manejar el flujo OAuth 2.0 de Amazon (redirigir a Amazon, recibir el código de autorización, intercambiarlo por un token de acceso y obtener datos del perfil de usuario) está encapsulada dentro del archivo principal del módulo y su controlador AJAX asociado. Los datos de usuario recibidos de Amazon se utilizan luego para iniciar sesión a un cliente de PrestaShop existente o crear uno nuevo.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores frontales o de administración dedicados en el directorio `controllers/`. Todas las solicitudes AJAX del front-office y la configuración principal del módulo son manejadas por el archivo principal del módulo (`amlogin/ajax_amlogin.php`) que actúa como un pseudo-controlador para las acciones AJAX.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no contiene ninguna clase o modelo personalizado en un directorio `classes/` dedicado. La lógica central reside dentro del archivo principal del módulo `amlogin/ajax_amlogin.php`.

### 4.4 Activos JavaScript (`views/js/`)

-   `amlogin/js/amlogin.js`
    -   **Alcance:** Front-office.
    -   **Descripción:** Este script es responsable de inicializar el SDK de inicio de sesión de Amazon, manejar los eventos de clic en el botón de inicio de sesión de Amazon y gestionar el flujo OAuth 2.0. Probablemente utiliza el método `amazon.Login.authorize` para iniciar el proceso de inicio de sesión y maneja la devolución de llamada de Amazon. Luego realizará una llamada AJAX al backend del módulo para procesar los datos del usuario de Amazon e iniciar sesión al cliente en PrestaShop. También puede actualizar la interfaz de usuario (por ejemplo, mostrar el estado de inicio de sesión) después de una autenticación exitosa.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `amlogin/css.css`
    -   **Alcance:** Front-office.
    -   **Descripción:** Estilo general para el botón de inicio de sesión de Amazon y cualquier elemento de la interfaz de usuario asociado. Esto podría contener ajustes básicos de diseño, relleno o margen.
-   `amlogin/css/amlogin.css`
    -   **Alcance:** Front-office.
    -   **Descripción:** Estilo específico para el botón de inicio de sesión de Amazon, que potencialmente incluye ajustes responsivos o anulaciones específicas del tema para PrestaShop 1.6.
-   `amlogin/css/amlogin17.css`
    -   **Alcance:** Front-office.
    -   **Descripción:** Estilo específico adaptado para temas de PrestaShop 1.7, abordando posibles diferencias en las estructuras de temas predeterminadas o marcos CSS (por ejemplo, Bootstrap 4 vs. Bootstrap 3). Los desarrolladores pueden anular estos estilos en el `custom.css` de su tema o creando un tema hijo.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El módulo utiliza un conjunto completo de plantillas Smarty para renderizar el botón de inicio de sesión de Amazon a través de varios hooks de PrestaShop.

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `amlogin/ajax-amlogin.tpl`: Probablemente utilizado para respuestas AJAX o contenido dinámico relacionado con el proceso de inicio de sesión de Amazon.
    -   `amlogin/amlogin.tpl`: Una plantilla genérica para el botón de inicio de sesión de Amazon, a menudo incluida por otras plantillas de hook.
    -   `amlogin/createAccountForm.tpl`: Renderiza el botón de inicio de sesión de Amazon dentro del formulario estándar de creación de cuenta de PrestaShop.
    -   `amlogin/createAccountTop.tpl`: Renderiza el botón de inicio de sesión de Amazon en la parte superior de la página de creación de cuenta.
    -   `amlogin/dashboardZoneOne.tpl`: Renderiza el botón de inicio de sesión de Amazon en la primera zona del panel de control del cliente (por ejemplo, `displayCustomerAccount`).
    -   `amlogin/displayCustomerLoginFormAfter.tpl`: Renderiza el botón de inicio de sesión de Amazon después del formulario de inicio de sesión estándar del cliente.
    -   `amlogin/displayNav.tpl`: Renderiza el botón de inicio de sesión de Amazon en la barra de navegación (por ejemplo, hook `displayNav`).
    -   `amlogin/displayPopUpLogin.tpl`: Renderiza el botón de inicio de sesión de Amazon dentro de un modal de inicio de sesión emergente (si lo implementa el tema o el módulo).
    -   `amlogin/footer.tpl`: Renderiza el botón de inicio de sesión de Amazon en el pie de página de la tienda (hook `displayFooter`).
    -   `amlogin/header.tpl`: Renderiza el botón de inicio de sesión de Amazon en la cabecera de la tienda (hook `displayHeader`).
    -   `amlogin/home.tpl`: Renderiza el botón de inicio de sesión de Amazon en la página de inicio (hook `displayHome`).
    -   `amlogin/leftcolumn.tpl`: Renderiza el botón de inicio de sesión de Amazon en la barra lateral izquierda (hook `displayLeftColumn`).
    -   `amlogin/rightcolumn.tpl`: Renderiza el botón de inicio de sesión de Amazon en la barra lateral derecha (hook `displayRightColumn`).
    -   `amlogin/shoppingCart.tpl`: Renderiza el botón de inicio de sesión de Amazon dentro del resumen del carrito de compras.
    -   `amlogin/shoppingCartExtra.tpl`: Renderiza el botón de inicio de sesión de Amazon en una sección extra del carrito de compras.
    -   `amlogin/top.tpl`: Renderiza el botón de inicio de sesión de Amazon en la sección superior de la página (por ejemplo, hook `displayTop`).
    -   `amlogin/topColumn.tpl`: Renderiza el botón de inicio de sesión de Amazon en el área de la columna superior (hook `displayTopColumn`).

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**: Este módulo no parece crear tablas SQL personalizadas. La configuración (ID de Cliente, Secreto de Cliente, etc.) se almacena en la tabla `ps_configuration` utilizando claves como `AML_CLIENT_ID`, `AML_CLIENT_SECRET`, `AML_REDIRECT_URI` y `AML_DISPLAY_HEADER`, etc.
-   **Tabla de Hooks Registrados**:

    | Nombre del Hook | Momento de Ejecución | Propósito Técnico |
    | --- | --- | --- |
    | `displayHeader` | En la sección `<head>` de la página. | Inyecta CSS, JS y potencialmente el botón de inicio de sesión de Amazon. |
    | `displayNav` | En la barra de navegación superior. | Muestra el botón de inicio de sesión de Amazon en la navegación. |
    | `displayLeftColumn` | En la barra lateral izquierda. | Muestra el botón de inicio de sesión de Amazon en la columna izquierda. |
    | `displayRightColumn` | En la barra lateral derecha. | Muestra el botón de inicio de sesión de Amazon en la columna derecha. |
    | `displayProductButtons` (o similar) | En la página de producto, cerca de los botones de acción. | Muestra el botón de inicio de sesión de Amazon en las páginas de productos. |
    | `displayFooter` | En el pie de página de la tienda. | Muestra el botón de inicio de sesión de Amazon en el pie de página. |
    | `displayCustomerAccount` | En el panel de control de la cuenta del cliente. | Muestra el botón de inicio de sesión de Amazon en el área de la cuenta del cliente. |
    | `displayCustomerLoginFormAfter` | Después del formulario de inicio de sesión estándar. | Integra el botón de inicio de sesión de Amazon en la página de inicio de sesión. |
    | `displayBeforeBodyClosingTag` | Antes de la etiqueta `</body>`. | Puede inyectar JavaScript para el SDK de Amazon o ventanas emergentes. |
    | `displayShoppingCart` | En la página de resumen del carrito de compras. | Muestra el botón de inicio de sesión de Amazon en el carrito. |
    | `displayShoppingCartExtra` | Área de contenido extra en el carrito de compras. | Muestra el botón de inicio de sesión de Amazon en un área adicional del carrito. |
    | `displayTop` | Parte superior de la página, encima de la cabecera. | Muestra el botón de inicio de sesión de Amazon en la sección superior. |
    | `displayTopColumn` | En el área principal de la columna superior. | Muestra el botón de inicio de sesión de Amazon en la columna superior. |
    | `displayHome` | En la página de inicio de la tienda. | Muestra el botón de inicio de sesión de Amazon en la página de inicio. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para su módulo "Conexión con Amazon (registro + inicio de sesión)", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar que su módulo funcione perfectamente y se integre sin problemas con su tienda PrestaShop.

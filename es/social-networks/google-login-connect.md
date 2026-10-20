---
title: "Google Login Connect - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Google Login Connect de MyPresta.eu."
sidebar:
  label: "Google Login Connect"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Google Login Connect en MyPresta.eu](https://mypresta.eu/modules/social-networks/google-login-connect.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/google-login-connect/)
>
> ---


# Google Login Connect

## 1. Requisitos y Compatibilidad

-   **Versiones de PrestaShop Soportadas**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilidad PHP**: PHP 5.6 - 8.5
-   **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una comunicación segura con la API de Google.

## 2. Recorrido Completo de Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Google Login Connect)

Esta es la pantalla de configuración principal donde configurará sus credenciales de la API de Google y decidirá dónde aparece el botón "Iniciar sesión con Google" en su tienda.

#### **Credenciales de la API de Google**

Antes de configurar el módulo, debe crear un Proyecto de la API de Google y obtener su ID de Cliente. Esto es crucial para que el módulo se comunique de forma segura con Google.

**Cómo obtener su ID de Cliente de Google:**
1.  Vaya a la [Consola de Google Cloud](https://console.cloud.google.com/).
2.  Cree un nuevo proyecto o seleccione uno existente.
3.  Navegue a **APIs y Servicios > Credenciales**.
4.  Haga clic en **"Crear credenciales"** y elija **"ID de cliente de OAuth"**.
5.  Seleccione **"Aplicación web"** como tipo de aplicación.
6.  En **"Orígenes de JavaScript autorizados"**, añada la URL de su tienda (por ejemplo, `https://www.sutienda.com`).
7.  En **"URI de redirección autorizados"**, añada la URL de su tienda seguida de la ruta de devolución de llamada del módulo (por ejemplo, `https://www.sutienda.com/module/glogin/index`).
8.  Después de la creación, Google le proporcionará un **ID de Cliente**. Copie este valor.

-   **ID de Cliente de Google (ggl_appid)**
    -   **Qué hace este ajuste:** Este es el identificador único de su aplicación (su tienda PrestaShop) que Google utiliza para reconocer sus solicitudes de inicio de sesión. Es esencial para que la funcionalidad "Iniciar sesión con Google" funcione.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce correctamente:* Sus botones de inicio de sesión de Google funcionarán, permitiendo a los clientes autenticarse a través de Google.
        -   *Cuando es incorrecto o está vacío:* Los botones de inicio de sesión de Google no funcionarán, o los clientes encontrarán errores al intentar iniciar sesión con Google.
    -   **Valor recomendado:** El ID de Cliente obtenido de su Consola de Google Cloud.
    -   **Escenario / ejemplo del comerciante:** Acaba de crear su proyecto de la API de Google y recibió `1234567890-abcdefg.apps.googleusercontent.com`. Debe pegar esta cadena exacta aquí.

#### **Configuración de la Cuenta del Cliente**

-   **Grupo de Clientes para Usuarios de Google (glogin_groupid)**
    -   **Qué hace este ajuste:** Determina a qué grupo de clientes se asignarán automáticamente los nuevos usuarios que se registren a través de Google.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Cliente" (predeterminado):* Los nuevos usuarios de Google serán clientes estándar.
        -   *Cuando se establece en "Visitante" u otro grupo personalizado:* Los nuevos usuarios de Google serán asignados a ese grupo específico, lo que podría afectar su acceso a descuentos, precios especiales o contenido.
    -   **Valor recomendado:** "Cliente" (o su grupo de clientes predeterminado).
    -   **Escenario / ejemplo del comerciante:** Desea que todos los nuevos registros de Google formen parte de su grupo de "Clientes Mayoristas" para concederles automáticamente precios B2B. Seleccionaría "Clientes Mayoristas" del menú desplegable.

-   **Enviar Correo Electrónico de Bienvenida a Nuevos Usuarios de Google (glogin_semail)**
    -   **Qué hace este ajuste:** Controla si PrestaShop envía un correo electrónico de bienvenida estándar a los clientes que se registran utilizando su cuenta de Google.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (SÍ):* Los nuevos usuarios de Google recibirán el correo electrónico de bienvenida estándar de PrestaShop, confirmando la creación de su cuenta.
        -   *Cuando está deshabilitado (NO):* Los nuevos usuarios de Google no recibirán un correo electrónico de bienvenida.
    -   **Valor recomendado:** SÍ (para confirmar la creación de la cuenta y dar una buena primera impresión).
    -   **Escenario / ejemplo del comerciante:** Desea asegurarse de que los nuevos clientes se sientan bienvenidos y tengan los detalles de su cuenta confirmados, por lo que habilita esta opción.

#### **Opciones de Visualización**

-   **Estilo del Botón de Inicio de Sesión de Google (glogin_button_style)**
    -   **Qué hace este ajuste:** Le permite elegir el estilo visual del botón "Iniciar sesión con Google". Las opciones suelen incluir diferentes tamaños, formas o esquemas de color proporcionados por Google.
    -   **Efecto de cambiar este ajuste:** Cambia la apariencia de todos los botones de inicio de sesión de Google en su tienda.
    -   **Valor recomendado:** Elija el estilo que mejor se adapte al diseño de su tienda.
    -   **Escenario / ejemplo del comerciante:** Su tema utiliza botones grandes y redondeados. Seleccionaría un estilo de botón que coincida con esta estética para mayor coherencia.

-   **Mostrar Botón de Inicio de Sesión de Google en Ventana Emergente (ggl_popuplogin)**
    -   **Qué hace este ajuste:** Si está habilitado, cuando un cliente haga clic en un enlace de inicio de sesión, aparecerá una ventana emergente con la opción de inicio de sesión de Google, en lugar de redirigirlos a una página de inicio de sesión completa.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (SÍ):* Proporciona una experiencia de inicio de sesión más rápida y menos disruptiva a través de una ventana emergente modal.
        -   *Cuando está deshabilitado (NO):* Los clientes serán redirigidos a la página de inicio de sesión estándar.
    -   **Valor recomendado:** SÍ (para una experiencia de usuario moderna y fluida).
    -   **Escenario / ejemplo del comerciante:** Desea mantener a los clientes en la página actual tanto como sea posible, por lo que habilita el inicio de sesión emergente.

#### **Ubicación del Botón (Selección de Hook)**

Estos ajustes controlan dónde aparece el botón "Iniciar sesión con Google" en su tienda. Puede habilitar o deshabilitar el botón para varios hooks de visualización de PrestaShop.

-   **Mostrar en la Cabecera (ggl_top)**
    -   **Qué hace este ajuste:** Controla la visibilidad del botón de inicio de sesión de Google en la sección de cabecera de su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Habilitado:* El botón aparece en la cabecera (por ejemplo, cerca de "Mi Cuenta" o "Iniciar Sesión").
        -   *Deshabilitado:* El botón está oculto de la cabecera.
    -   **Valor recomendado:** SÍ (para un fácil acceso desde cualquier página).

-   **Mostrar en la Barra de Navegación (ggl_displayNav, ggl_displayNav1, ggl_displayNav2)**
    -   **Qué hacen estos ajustes:** Controlan la visibilidad del botón de inicio de sesión de Google en diferentes posiciones de la barra de navegación, dependiendo de su versión de PrestaShop y tema. `displayNav` es común para temas antiguos, mientras que `displayNav1` y `displayNav2` se utilizan a menudo en PrestaShop 1.7+ para la navegación en la parte superior de la página.
    -   **Efecto de cambiar este ajuste:**
        -   *Habilitado:* El botón aparece en la barra de navegación seleccionada.
        -   *Deshabilitado:* El botón está oculto de esa barra de navegación.
    -   **Valor recomendado:** Habilite uno o dos que mejor se adapten a su tema, evitando la redundancia.

-   **Mostrar en el Carrito de Compras (ggl_shoppingCart, ggl_shoppingCartExtra)**
    -   **Qué hacen estos ajustes:** Controlan la visibilidad del botón de inicio de sesión de Google en la página del carrito de compras. `ggl_shoppingCart` es típicamente para el contenido principal del carrito, mientras que `ggl_shoppingCartExtra` podría ser para bloques o resúmenes adicionales.
    -   **Efecto de cambiar este ajuste:**
        -   *Habilitado:* El botón aparece en la página del carrito de compras, permitiendo un inicio de sesión rápido antes de la compra.
        -   *Deshabilitado:* El botón está oculto de la página del carrito de compras.
    -   **Valor recomendado:** SÍ (para fomentar el inicio de sesión rápido y reducir el abandono).

-   **Mostrar en la Columna Izquierda (ggl_leftcolumn)**
    -   **Qué hace este ajuste:** Controla la visibilidad del botón de inicio de sesión de Google en la barra lateral izquierda de su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Habilitado:* El botón aparece en la columna izquierda.
        -   *Deshabilitado:* El botón está oculto de la columna izquierda.
    -   **Valor recomendado:** SÍ (si su tema utiliza una columna izquierda y desea una ubicación destacada).

-   **Mostrar en la Columna Derecha (ggl_rightoclumn)**
    -   **Qué hace este ajuste:** Controla la visibilidad del botón de inicio de sesión de Google en la barra lateral derecha de su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Habilitado:* El botón aparece en la columna derecha.
        -   *Deshabilitado:* El botón está oculto de la columna derecha.
    -   **Valor recomendado:** SÍ (si su tema utiliza una columna derecha y desea una ubicación destacada).

-   **Mostrar en la Página de Inicio (ggl_home)**
    -   **Qué hace este ajuste:** Controla la visibilidad del botón de inicio de sesión de Google en la página de inicio de su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Habilitado:* El botón aparece en la página de inicio.
        -   *Deshabilitado:* El botón está oculto de la página de inicio.
    -   **Valor recomendado:** SÍ (para máxima visibilidad y acceso rápido para nuevos visitantes).

-   **Mostrar Después del Formulario de Inicio de Sesión del Cliente (ggl_displayCustomerLoginFormAfter)**
    -   **Qué hace este ajuste:** Controla la visibilidad del botón de inicio de sesión de Google directamente después del formulario de inicio de sesión estándar del cliente de PrestaShop (por ejemplo, en la página `/my-account`).
    -   **Efecto de cambiar este ajuste:**
        -   *Habilitado:* El botón aparece debajo del formulario de inicio de sesión tradicional.
        -   *Deshabilitado:* El botón está oculto de esta posición.
    -   **Valor recomendado:** SÍ (esta es una ubicación principal para los botones de inicio de sesión social).

-   **Mostrar en el Formulario de Creación de Cuenta (ggl_createAccountForm, ggl_createAccountTop)**
    -   **Qué hacen estos ajustes:** Controlan la visibilidad del botón de inicio de sesión de Google en la página de creación de cuenta del cliente. `ggl_createAccountForm` lo coloca típicamente dentro o cerca del formulario, mientras que `ggl_createAccountTop` lo coloca en la parte superior de la página de creación de cuenta.
    -   **Efecto de cambiar este ajuste:**
        -   *Habilitado:* El botón aparece en la página de creación de cuenta, ofreciendo una alternativa de registro rápido.
        -   *Deshabilitado:* El botón está oculto de esta página.
    -   **Valor recomendado:** SÍ (para simplificar el registro de nuevos clientes).

-   **Mostrar en la Columna Superior (ggl_topColumn)**
    -   **Qué hace este ajuste:** Controla la visibilidad del botón de inicio de sesión de Google en el hook `displayTopColumn`, a menudo utilizado para banners o contenido justo debajo de la cabecera.
    -   **Efecto de cambiar este ajuste:**
        -   *Habilitado:* El botón aparece en la columna superior.
        -   *Deshabilitado:* El botón está oculto de la columna superior.
    -   **Valor recomendado:** Considere según el diseño de su tema; a menudo menos crítico que otras posiciones.

-   **Mostrar Información Personal Superior (ggl_displayPersonalInformationTop)**
    -   **Qué hace este ajuste:** Controla la visibilidad del botón de inicio de sesión de Google en la página "Mi Información Personal", generalmente cuando un cliente ya ha iniciado sesión. Esto podría ser menos común para un botón de inicio de sesión, pero podría usarse para vincular cuentas.
    -   **Efecto de cambiar este ajuste:**
        -   *Habilitado:* El botón aparece en la página de información personal.
        -   *Deshabilitado:* El botón está oculto de esta página.
    -   **Valor recomendado:** NO (típicamente no es un punto de inicio de sesión principal).

#### **Otros Ajustes (Internos/Legados)**

-   **mypresta_updates, update_, updatev_**: Estos son ajustes internos utilizados por MyPresta.eu para comprobaciones de actualización de módulos y gestión de versiones. No debe modificarlos.
-   **PS_CUSTOMER_GROUP, PS_CUSTOMER_CREATION_EMAIL, PS_CART_FOLLOWING**: Estas son variables de configuración estándar de PrestaShop a las que el módulo podría hacer referencia, pero que normalmente no permite la modificación directa a través de su interfaz. Reflejan la configuración principal de su tienda.
-   **glogin_identity**: Este es probablemente un identificador interno utilizado por el módulo. No lo modifique.
-   **ggl_**: Cualquier otro ajuste que comience con `ggl_` y no esté explícitamente listado anteriormente son probablemente indicadores internos u opciones heredadas. Es mejor dejarlos en sus valores predeterminados a menos que el soporte le indique lo contrario.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Configuración del Módulo | ID de Cliente de Google | Su ID de Cliente de Google | Esencial para la funcionalidad de inicio de sesión de Google. |
| Configuración del Módulo | Grupo de Clientes para Usuarios de Google | Cliente | Asigna nuevos usuarios de Google a un grupo de clientes específico. |
| Configuración del Módulo | Enviar Correo Electrónico de Bienvenida a Nuevos Usuarios de Google | SÍ | Envía un correo electrónico de bienvenida a los nuevos registros de Google. |
| Configuración del Módulo | Estilo del Botón de Inicio de Sesión de Google | (Elija el que mejor se adapte) | Cambia la apariencia visual del botón. |
| Configuración del Módulo | Mostrar Botón de Inicio de Sesión de Google en Ventana Emergente | SÍ | Habilita el inicio de sesión emergente para una UX más fluida. |
| Configuración del Módulo | Mostrar en la Cabecera (ggl_top) | SÍ | Muestra el botón en la cabecera de la tienda. |
| Configuración del Módulo | Mostrar en la Barra de Navegación (ggl_displayNav, ggl_displayNav1, ggl_displayNav2) | SÍ (según sea necesario) | Muestra el botón en varias barras de navegación. |
| Configuración del Módulo | Mostrar en el Carrito de Compras (ggl_shoppingCart, ggl_shoppingCartExtra) | SÍ | Muestra el botón en la página del carrito de compras. |
| Configuración del Módulo | Mostrar en la Columna Izquierda (ggl_leftcolumn) | SÍ (si aplica) | Muestra el botón en la barra lateral izquierda. |
| Configuración del Módulo | Mostrar en la Columna Derecha (ggl_rightoclumn) | SÍ (si aplica) | Muestra el botón en la barra lateral derecha. |
| Configuración del Módulo | Mostrar en la Página de Inicio (ggl_home) | SÍ | Muestra el botón en la página de inicio de la tienda. |
| Configuración del Módulo | Mostrar Después del Formulario de Inicio de Sesión del Cliente (ggl_displayCustomerLoginFormAfter) | SÍ | Muestra el botón debajo del formulario de inicio de sesión estándar. |
| Configuración del Módulo | Mostrar en el Formulario de Creación de Cuenta (ggl_createAccountForm, ggl_createAccountTop) | SÍ | Muestra el botón en la página de creación de cuenta. |
| Configuración del Módulo | Mostrar en la Columna Superior (ggl_topColumn) | NO (o según sea necesario) | Muestra el botón en el hook de la columna superior. |
| Configuración del Módulo | Mostrar Información Personal Superior (ggl_displayPersonalInformationTop) | NO | Muestra el botón en la página de información personal (menos común). |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: El botón de inicio de sesión de Google aparece, pero no pasa nada cuando hago clic en él, o recibo un error.**
R: Esto es casi siempre un problema con su ID de Cliente de Google o los URI de Redirección Autorizados en su Consola de Google Cloud.
    *   **Verifique el ID de Cliente:** Vuelva a verificar que el `ID de Cliente de Google` introducido en la configuración del módulo sea exactamente el que Google proporcionó, sin espacios adicionales.
    *   **Verifique los URI de Redirección Autorizados:** En su Consola de Google Cloud, asegúrese de haber añadido `https://www.sutienda.com/module/glogin/index` (reemplace `sutienda.com` con su dominio real) a la lista de "URI de redirección autorizados". Debe ser una coincidencia exacta, incluyendo `https://` si su tienda utiliza SSL.
    *   **Verifique los Orígenes de JavaScript Autorizados:** También asegúrese de que la URL principal de su tienda (por ejemplo, `https://www.sutienda.com`) esté listada en "Orígenes de JavaScript autorizados".

**P: Los nuevos clientes se están registrando con Google, pero no reciben un correo electrónico de bienvenida.**
R: Verifique la configuración "Enviar Correo Electrónico de Bienvenida a Nuevos Usuarios de Google" en la configuración del módulo. Asegúrese de que esté configurado en "SÍ". Además, verifique que la configuración general de correo electrónico de su tienda PrestaShop esté configurada correctamente y que otros correos electrónicos transaccionales (como las confirmaciones de pedido) se estén enviando con éxito.

**P: El botón de inicio de sesión de Google no aparece en una ubicación específica (por ejemplo, la cabecera) a pesar de que lo habilité.**
R:
    *   **Borrar Caché:** Primero, borre la caché de su PrestaShop (**Parámetros Avanzados > Rendimiento > Borrar Caché**).
    *   **Posición del Módulo:** Vaya a **Diseño > Posiciones** (o **Módulos > Posiciones** en versiones anteriores). Busque el módulo `glogin`. Asegúrese de que esté enganchado a `displayHeader`, `displayNav` u otros hooks relevantes que haya habilitado. A veces, los temas pueden anular los comportamientos predeterminados de los hooks.
    *   **Conflictos de Tema:** Su tema podría tener plantillas personalizadas que no llaman explícitamente a todos los hooks estándar de PrestaShop. Si el botón no aparece después de borrar la caché y verificar las posiciones del módulo, es posible que necesite que un webmaster inspeccione los archivos `.tpl` de su tema.

**P: ¿Pueden los clientes vincular una cuenta de PrestaShop existente a su cuenta de Google?**
R: Este módulo facilita principalmente los nuevos registros e inicios de sesión. Si un cliente inicia sesión con Google y ya existe una cuenta con ese correo electrónico en su tienda PrestaShop, el módulo normalmente los iniciará en su cuenta existente. No suele ofrecer una función separada de "vincular cuenta existente" después del inicio de sesión, pero coincide inteligentemente por correo electrónico.

**P: Quiero cambiar el texto o la apariencia del botón más allá de las opciones del módulo.**
R: El módulo proporciona estilos de botón estándar de Google. Para una personalización avanzada (por ejemplo, cambiar el texto, añadir iconos personalizados), necesitaría CSS personalizado y potencialmente modificaciones de JavaScript, que deberían ser manejadas por un desarrollador web.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo Google Login Connect.

### 4.1 Descripción General de la Arquitectura
El módulo `Google Login Connect` sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente los controladores frontales para el manejo de la devolución de llamada de OAuth 2.0 y varios hooks de visualización para la inyección de botones. Se basa en la clase `Configuration` de PrestaShop para el almacenamiento de la configuración y en `ObjectModel` de `Customer` para la gestión de usuarios. El módulo se integra con la API de JavaScript de Google para la autenticación del lado del cliente, que luego envía el token a un controlador frontal del módulo para la verificación del lado del servidor y la creación de la sesión del usuario.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:
    *   `glogin/controllers/front/index.php`
        *   **Nombre de la clase y clase padre**: `GloginIndexModuleFrontController` extiende `ModuleFrontController`
        *   **Responsabilidad**: Este es el punto final de devolución de llamada principal para el flujo de OAuth 2.0 de Google. Después de que un usuario se autentica con Google, Google redirige a este controlador. Recibe el token de ID de Google, lo verifica, extrae la información del usuario (correo electrónico, nombre) y luego inicia sesión en un cliente de PrestaShop existente o crea uno nuevo. Maneja la gestión de sesiones y redirige al usuario de vuelta a la tienda.
    *   `glogin/controllers/front/loginloader.php`
        *   **Nombre de la clase y clase padre**: `GloginLoginloaderModuleFrontController` extiende `ModuleFrontController`
        *   **Responsabilidad**: Este controlador probablemente sirve una pequeña pieza de JavaScript o inicializa el cliente de la API de Google en las páginas donde se muestra el botón de inicio de sesión. Podría usarse para cargar dinámicamente la Biblioteca de la Plataforma de Google (`platform.js`) o para proporcionar variables de configuración (como el `ggl_appid`) al JavaScript del front-end.

-   **Controladores de Administración de Back-Office**:
    *   Ninguno. Toda la configuración se maneja a través del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Principales (`classes/`)
-   No se definen clases `ObjectModel` personalizadas dentro del directorio `classes/`. El módulo interactúa directamente con la clase `Customer` `ObjectModel` y `Configuration` de PrestaShop.
-   El archivo principal del módulo `glogin/glogin.php` actúa como la clase principal, extendiendo `Module` y conteniendo toda la lógica de instalación, desinstalación y configuración.

### 4.4 Activos JavaScript (`views/js/`)

-   `glogin/views/js/glogin.js`
    *   **Alcance**: Front-office.
    *   **Responsabilidad**: Este script es responsable de inicializar la biblioteca cliente de Google Sign-In. Probablemente incluye:
        *   Cargar la Biblioteca de la Plataforma de Google (`https://apis.google.com/js/platform.js`).
        *   Renderizar el botón "Iniciar sesión con Google" usando `gapi.signin2.render()`.
        *   Manejar la función de devolución de llamada `onSignIn`, que se activa después de un inicio de sesión exitoso de Google. Esta devolución de llamada extrae el token de ID y lo envía a través de AJAX al controlador frontal del módulo (`index.php`) para su procesamiento en el servidor.
        *   Potencialmente gestiona la funcionalidad de inicio de sesión emergente (`ggl_popuplogin`), mostrando dinámicamente el botón de Google dentro de un modal.
        *   Escuchadores de eventos para clics en los botones de inicio de sesión de Google.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `glogin/css.css`
    *   **Alcance**: Front-office.
    *   **Responsabilidad**: Estilo general para los botones de inicio de sesión de Google y potencialmente cualquier contenedor personalizado o ventanas emergentes introducidas por el módulo. Puede contener ajustes básicos de diseño.
-   `glogin/views/css/glogin.css`
    *   **Alcance**: Front-office.
    *   **Responsabilidad**: Similar a `css.css`, probablemente contiene el estilo principal para los botones de inicio de sesión de Google, asegurando que estén correctamente alineados y dimensionados dentro de varios temas de PrestaShop.
-   `glogin/views/css/glogin17-new.css`
    *   **Alcance**: Front-office.
    *   **Responsabilidad**: Reglas CSS específicas adaptadas para temas de PrestaShop 1.7+, abordando posibles diferencias de diseño o anulaciones de estilo requeridas para versiones más nuevas. Esto podría incluir ajustes de Flexbox o Grid.
-   `glogin/views/css/glogin17.css`
    *   **Alcance**: Front-office.
    *   **Responsabilidad**: Otra hoja de estilo específicamente para PrestaShop 1.7.x, que potencialmente contiene estilos adicionales o alternativos en comparación con `glogin17-new.css`, dependiendo de la estructura exacta del tema.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El módulo utiliza numerosas plantillas para inyectar el botón de inicio de sesión de Google en varios hooks de PrestaShop. La mayoría de estas plantillas contendrán una llamada a la lógica de renderizado del botón de Google Sign-In (por ejemplo, `<div class="g-signin2" data-onsuccess="onSignIn"></div>`) y potencialmente algo de HTML circundante para el estilo.

-   **Plantillas de Hook (`views/templates/hook/`)**:
    *   `glogin/views/templates/createAccountForm.tpl`: Renderiza el botón de Google dentro del formulario de creación de cuenta del cliente.
    *   `glogin/views/templates/createAccountTop.tpl`: Renderiza el botón de Google en la parte superior de la página de creación de cuenta.
    *   `glogin/views/templates/dashboardZoneOne.tpl`: Renderiza el botón de Google en el hook `dashboardZoneOne` (menos común para el inicio de sesión, posiblemente para la integración del panel de administración o un tema específico).
    *   `glogin/views/templates/displayCustomerLoginFormAfter.tpl`: Renderiza el botón de Google directamente después del formulario de inicio de sesión estándar del cliente.
    *   `glogin/views/templates/displayNav.tpl`: Renderiza el botón de Google en el hook `displayNav` (a menudo navegación superior).
    *   `glogin/views/templates/displayNav1.tpl`: Renderiza el botón de Google en el hook `displayNav1` (navegación de PrestaShop 1.7+).
    *   `glogin/views/templates/displayNav2.tpl`: Renderiza el botón de Google en el hook `displayNav2` (navegación de PrestaShop 1.7+).
    *   `glogin/views/templates/displayPopUpLogin.tpl`: Contiene la estructura HTML para el modal de inicio de sesión emergente, incluyendo el botón de Google.
    *   `glogin/views/templates/footer.tpl`: Renderiza el botón de Google en el hook `displayFooter`.
    *   `glogin/views/templates/glogin.tpl`: Una plantilla genérica, posiblemente utilizada como respaldo o para la lógica de renderizado interno.
    *   `glogin/views/templates/header.tpl`: Renderiza el botón de Google en el hook `displayHeader`.
    *   `glogin/views/templates/home.tpl`: Renderiza el botón de Google en el hook `displayHome`.
    *   `glogin/views/templates/leftcolumn.tpl`: Renderiza el botón de Google en el hook `displayLeftColumn`.
    *   `glogin/views/templates/rightcolumn.tpl`: Renderiza el botón de Google en el hook `displayRightColumn`.
    *   `glogin/views/templates/shoppingCart.tpl`: Renderiza el botón de Google en el hook `displayShoppingCart`.
    *   `glogin/views/templates/shoppingCartExtra.tpl`: Renderiza el botón de Google en el hook `displayShoppingCartExtra`.
    *   `glogin/views/templates/top.tpl`: Renderiza el botón de Google en el hook `displayTop`.
    *   `glogin/views/templates/topColumn.tpl`: Renderiza el botón de Google en el hook `displayTopColumn`.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:
    *   El módulo no crea ninguna tabla SQL personalizada.
    *   Los ajustes de configuración se almacenan en la tabla `ps_configuration` utilizando claves como `GLOGIN_GROUPID`, `GLOGIN_SEMAIL`, `GGL_APPID`, `GGL_POPUP_LOGIN`, `GGL_BUTTON_STYLE` y varias banderas `GGL_DISPLAY[HOOK_NAME]`.

-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
|---|---|---|
| `displayHeader` | En la sección `<head>` o al principio del `<body>` | Inyectar CSS, JS y potencialmente el botón de Google en la cabecera. |
| `displayFooter` | Al final del `<body>` | Inyectar el botón de Google en el pie de página. |
| `displayHome` | En el área de contenido de la página de inicio | Inyectar el botón de Google en la página de inicio. |
| `displayShoppingCart` | En la página del carrito de compras | Inyectar el botón de Google en la página del carrito. |
| `displayRightColumn` | En la barra lateral derecha | Inyectar el botón de Google en la columna derecha. |
| `displayCustomerLoginFormAfter` | Después del formulario de inicio de sesión estándar del cliente | Inyectar el botón de Google para un inicio de sesión alternativo. |
| `displayNav` | En la barra de navegación principal (temas antiguos) | Inyectar el botón de Google en la navegación. |
| `displayCreateAccountTop` | En la parte superior de la página de creación de cuenta | Inyectar el botón de Google para un registro rápido. |
| `displayTop` | En la sección superior de la página (a menudo encima de la cabecera) | Inyectar el botón de Google en la sección superior. |
| `displayNav2` | En una barra de navegación secundaria (PS 1.7+) | Inyectar el botón de Google en la navegación. |
| `displayShoppingCartExtra` | Área de contenido adicional en la página del carrito de compras | Inyectar el botón de Google en la página del carrito. |
| `displayTopColumn` | En el área de contenido debajo de la cabecera (a menudo para banners) | Inyectar el botón de Google en la columna superior. |
| `displayNav1` | En una barra de navegación principal (PS 1.7+) | Inyectar el botón de Google en la navegación. |
| `dashboardZoneOne` | En la primera zona del panel de administración | Potencialmente para información del lado del administrador o un botón específico. |
| `displayLeftColumn` | En la barra lateral izquierda | Inyectar el botón de Google en la columna izquierda. |

## 5. Soporte Oficial y Actualizaciones
Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Asegúrese de estar ejecutando la última versión compatible del módulo para su tienda PrestaShop.

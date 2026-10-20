---
title: "Conexión de inicio de sesión de PayPal - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Conexión de inicio de sesión de PayPal' de MyPresta.eu."
sidebar:
  label: "Conexión de inicio de sesión de PayPal - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo PayPal login connect en MyPresta.eu](https://mypresta.eu/modules/social-networks/paypal-login-connect.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/paypal-login-connect/)
>
> ---


# Conexión de inicio de sesión de PayPal

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo de configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Conexión de inicio de sesión de PayPal" para acceder a sus ajustes.

#### **Credenciales de la API de PayPal**

Estos ajustes conectan su tienda a su cuenta de desarrollador de PayPal, permitiendo que el módulo autentique a los usuarios de forma segura.

- **Qué hace este ajuste:** Estos campos requieren su ID de cliente y Secreto de cliente únicos obtenidos de su cuenta de desarrollador de PayPal. Estas credenciales son vitales para que su tienda se comunique con el servicio de inicio de sesión de PayPal.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce correctamente:* El botón "Iniciar sesión con PayPal" funcionará, permitiendo a los clientes iniciar sesión.
  - *Cuando es incorrecto o está vacío:* El módulo no podrá conectarse a PayPal y la función de inicio de sesión fallará o no aparecerá.
- **Valor recomendado:** Introduzca el ID de cliente y el Secreto de cliente exactos proporcionados por PayPal.
- **Escenario/ejemplo de comerciante:** Ha creado una cuenta de desarrollador de PayPal y ha configurado una aplicación "Iniciar sesión con PayPal". PayPal le proporciona un ID de cliente (una larga cadena de caracteres) y un Secreto de cliente (otra cadena larga y segura). Los copia y pega en los campos respectivos aquí.

#### **Habilitar inicio de sesión de PayPal**

Este es el interruptor principal para la funcionalidad del módulo.

- **Qué hace este ajuste:** Controla si la función "Iniciar sesión con PayPal" está activa y visible en su tienda.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Los botones de inicio de sesión de PayPal aparecerán en las ubicaciones seleccionadas y la funcionalidad estará activa.
  - *Cuando está deshabilitado (NO):* Los botones de inicio de sesión de PayPal estarán ocultos y los clientes no podrán usar esta función.
- **Valor recomendado:** SÍ
- **Escenario/ejemplo de comerciante:** Ha terminado de configurar el módulo y quiere activarlo para sus clientes. Lo establece en SÍ. Si necesita deshabilitarlo temporalmente para mantenimiento, puede establecerlo en NO.

#### **Mostrar botón en**

Esta sección le permite elegir dónde aparecerá el botón "Iniciar sesión con PayPal" en su tienda.

- **Qué hace este ajuste:** Determina las ubicaciones específicas (hooks) donde se renderizará el botón de inicio de sesión de PayPal en su front office.
- **Efecto de cambiar este ajuste:**
  - *Cuando se marca una ubicación:* El botón de inicio de sesión de PayPal aparecerá en esa área específica de su tienda.
  - *Cuando se desmarca una ubicación:* El botón no se mostrará en esa área.
- **Valor recomendado:** Seleccione las ubicaciones más relevantes para el inicio de sesión/registro del cliente, como `displayNav` (navegación superior), `displayCustomerLoginFormAfter` (después del formulario de inicio de sesión estándar) y `createAccountForm` (en la página de registro).
- **Escenario/ejemplo de comerciante:** Quiere que el botón sea fácilmente accesible en el encabezado y en la página principal de inicio de sesión. Marcaría `displayNav` y `displayCustomerLoginFormAfter`. Si su tema tiene un inicio de sesión emergente personalizado, también podría marcar `displayPopUpLogin`.

#### **Estilo del botón**

Personalice la apariencia visual del botón de inicio de sesión de PayPal.

- **Qué hace este ajuste:** Le permite seleccionar entre diferentes estilos predefinidos para el botón "Iniciar sesión con PayPal" para que coincida con el diseño de su tienda o las directrices de marca de PayPal.
- **Efecto de cambiar este ajuste:** Cambia el aspecto visual (por ejemplo, color, tamaño, texto) de los botones de inicio de sesión de PayPal en toda su tienda.
- **Valor recomendado:** Elija un estilo que mejor se integre con el diseño de su tienda sin dejar de ser claramente identificable como un botón de PayPal.
- **Escenario/ejemplo de comerciante:** Su tienda utiliza un tema oscuro, por lo que podría elegir un botón de PayPal blanco con texto oscuro para un mejor contraste. O podría preferir el botón azul estándar de PayPal para una máxima identificación de marca.

#### **URL de redirección después del inicio de sesión**

Especifique a dónde se envía a los clientes después de iniciar sesión correctamente con PayPal.

- **Qué hace este ajuste:** Define la página a la que se redirige a un cliente inmediatamente después de que se autentica correctamente con PayPal y regresa a su tienda.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "Mi cuenta":* Los clientes aterrizan en el panel de control de su cuenta personal.
  - *Cuando se establece en "Página de inicio":* Los clientes son llevados de vuelta a la página principal de su tienda.
  - *Cuando se establece en "Página anterior":* Los clientes regresan a la página en la que estaban antes de iniciar el inicio de sesión.
- **Valor recomendado:** "Página anterior" o "Mi cuenta" para una experiencia fluida. "Página anterior" a menudo se prefiere durante el proceso de pago.
- **Escenario/ejemplo de comerciante:** Un cliente está en una página de producto y hace clic en "Iniciar sesión con PayPal". Si se selecciona "Página anterior", regresará a esa página de producto. Si estaba en el proceso de pago, regresaría al paso de pago.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | ID de cliente de PayPal | (Vacío) / Su ID de cliente de PayPal | Identificador único para su aplicación de PayPal. **Requerido para que el módulo funcione.** |
| Configuración del módulo | Secreto de cliente de PayPal | (Vacío) / Su Secreto de cliente de PayPal | Clave secreta para su aplicación de PayPal. **Requerido para que el módulo funcione.** |
| Configuración del módulo | Habilitar inicio de sesión de PayPal | SÍ | Interruptor principal para activar/desactivar la función de inicio de sesión de PayPal. |
| Configuración del módulo | Mostrar botón en: displayNav | SÍ | Muestra el botón en la barra de navegación principal. |
| Configuración del módulo | Mostrar botón en: displayCustomerLoginFormAfter | SÍ | Muestra el botón después del formulario de inicio de sesión estándar. |
| Configuración del módulo | Mostrar botón en: createAccountForm | SÍ | Muestra el botón en la página de registro de clientes. |
| Configuración del módulo | Mostrar botón en: displayFooter | NO | Muestra el botón en el pie de página de la tienda. |
| Configuración del módulo | Mostrar botón en: displayHome | NO | Muestra el botón en la página de inicio. |
| Configuración del módulo | Mostrar botón en: displayLeftColumn | NO | Muestra el botón en la columna izquierda. |
| Configuración del módulo | Mostrar botón en: displayNav1 | NO | Muestra el botón en un hook de navegación alternativo (dependiente del tema). |
| Configuración del módulo | Mostrar botón en: displayNav2 | NO | Muestra el botón en otro hook de navegación alternativo (dependiente del tema). |
| Configuración del módulo | Mostrar botón en: displayPopUpLogin | SÍ | Muestra el botón en formularios de inicio de sesión emergentes (si su tema los usa). |
| Configuración del módulo | Mostrar botón en: displayRightColumn | NO | Muestra el botón en la columna derecha. |
| Configuración del módulo | Mostrar botón en: displayTop | NO | Muestra el botón en la sección superior de la página (dependiente del tema). |
| Configuración del módulo | Mostrar botón en: header | NO | Muestra el botón en la sección `<head>` de HTML (menos común para botones visibles). |
| Configuración del módulo | Mostrar botón en: shoppingCart | NO | Muestra el botón dentro del resumen del carrito de compras. |
| Configuración del módulo | Mostrar botón en: shoppingCartExtra | NO | Muestra el botón en una sección extra del carrito de compras (dependiente del tema). |
| Configuración del módulo | Estilo del botón | (Estilo predeterminado de PayPal) | Apariencia visual del botón de inicio de sesión de PayPal. |
| Configuración del módulo | URL de redirección después del inicio de sesión | Página anterior | Página de destino después de un inicio de sesión exitoso con PayPal. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: El botón de inicio de sesión de PayPal no aparece en mi tienda.**
R:

1. **Verifique "Habilitar inicio de sesión de PayPal":** Asegúrese de que esta configuración esté establecida en SÍ en la configuración del módulo.
2. **Verifique la configuración de "Mostrar botón en":** Asegúrese de haber seleccionado al menos un hook (por ejemplo, `displayNav`, `displayCustomerLoginFormAfter`) donde desea que aparezca el botón.
3. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y borre la caché de PrestaShop (caché de Smarty, caché del sistema de archivos). Es posible que también deba borrar la caché de su navegador.
4. **Compatibilidad con el tema:** Algunos temas altamente personalizados pueden requerir pequeños ajustes. Si el botón aún no aparece, póngase en contacto con el soporte de MyPresta.eu.

**P: Cuando hago clic en el botón de PayPal, no sucede nada o recibo un error.**
R:

1. **Verifique las credenciales de la API:** Vuelva a verificar su ID de cliente de PayPal y su Secreto de cliente en la configuración del módulo. Incluso un solo carácter incorrecto impedirá la conexión.
2. **Configuración de la aplicación de PayPal:** Asegúrese de que su aplicación "Iniciar sesión con PayPal" en su cuenta de desarrollador de PayPal esté configurada correctamente, especialmente la "URL de retorno" o "URI de redirección" que debe apuntar a la página de autenticación de su tienda (por ejemplo, `https://tutienda.com/authentication?paypal_login=1`).
3. **Compatibilidad con PHP:** Verifique que la versión de PHP de su servidor esté dentro del rango admitido (PHP 5.6 - 8.5).

**P: Mis clientes son redirigidos a la página incorrecta después de iniciar sesión.**
R:

1. **Verifique "URL de redirección después del inicio de sesión":** Revise esta configuración en la configuración del módulo. Seleccione la opción deseada (por ejemplo, "Mi cuenta", "Página anterior").
2. **Borrar caché:** Después de cambiar esta configuración, borre la caché de PrestaShop y del navegador.

**P: ¿Puedo cambiar el texto del botón de inicio de sesión de PayPal?**
R: El módulo suele utilizar la marca estándar de PayPal para el texto y el estilo del botón. La modificación directa del texto no suele ser una opción dentro de la propia configuración del módulo, ya que está diseñado para cumplir con las directrices de PayPal. Si necesita texto personalizado, requeriría anulaciones a nivel de tema o personalización del módulo (consulte la Guía del desarrollador).

**P: ¿Funciona este módulo con tiendas multiidioma?**
R: Sí, el módulo está diseñado para ser compatible con las funciones multiidioma de PrestaShop. La interfaz de inicio de sesión de PayPal en sí es gestionada por PayPal, que normalmente se adapta al idioma del navegador del usuario. Cualquier texto específico del módulo (si está presente) se puede traducir a través de **Internacional > Traducciones** en el back office de PrestaShop.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura

El módulo "Conexión de inicio de sesión de PayPal" (`plogin`) es un módulo estándar de PrestaShop implementado principalmente dentro de su archivo `index.php` principal, que actúa como punto de entrada del módulo y controlador de configuración. Aprovecha el sistema de hooks de PrestaShop para inyectar el botón "Iniciar sesión con PayPal" en varias ubicaciones del front-office. El módulo maneja el flujo OAuth 2.0 con PayPal para la autenticación de usuarios, creando una cuenta de cliente si no existe y registrando al usuario. No introduce tablas de base de datos personalizadas ni estructuras `ObjectModel` complejas, basándose en las clases nativas `Customer` y `Configuration` de PrestaShop.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores dedicados de front-office o back-office en el directorio `controllers/`. Toda la lógica del front-office relacionada con la devolución de llamada de PayPal se maneja directamente dentro del archivo `index.php` (la clase principal del módulo) a través de parámetros `$_GET`, y la configuración del back-office se gestiona a través del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no contiene clases o modelos personalizados en un directorio `classes/`. Toda la lógica central, incluida la interacción con la API y el manejo de clientes, está encapsulada dentro de la clase principal `plogin` definida en `index.php`.

### 4.4 Activos de JavaScript (`views/js/`)

- **`plogin/js/plogin.js`**
  - **Alcance:** Front-office.
  - **Propósito:** Este script probablemente maneja la interacción del lado del cliente para el botón de inicio de sesión de PayPal. Esto podría incluir:
    - Abrir la ventana de autenticación de PayPal como una ventana emergente.
    - Manejar la redirección después de la autenticación de PayPal.
    - Potencialmente gestionar solicitudes AJAX para el estado de inicio de sesión o la representación dinámica de botones.
    - Vincular eventos de clic a los botones de inicio de sesión de PayPal.
    - Asegurar la funcionalidad del botón en diferentes navegadores y dispositivos.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`plogin/css.css`**

  - **Alcance:** Front-office.
  - **Propósito:** Esta hoja de estilo probablemente contiene estilos generales para el botón de inicio de sesión de PayPal y cualquier elemento asociado. Podría definir el diseño básico, el relleno, los márgenes y los estilos de fuente.
  - **Selectores clave:** Los desarrolladores pueden inspeccionar este archivo en busca de nombres de clase (por ejemplo, `.paypal-login-button`, `.plogin-container`) para anular estilos en el `custom.css` o `theme.css` de su tema.
- **`plogin/css/plogin.css`**

  - **Alcance:** Front-office.
  - **Propósito:** Similar a `css.css`, este archivo proporciona estilos adicionales o más específicos para el botón de inicio de sesión de PayPal, incluyendo potencialmente diferentes estilos de botón basados en la configuración, efectos de desplazamiento o ajustes responsivos.
  - **Selectores clave:** Busque clases de botones específicas (por ejemplo, `.plogin-btn-blue`, `.plogin-btn-white`) para apuntar y personalizar.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza un conjunto completo de plantillas Smarty para inyectar el botón de inicio de sesión de PayPal en varios hooks de PrestaShop.

- **Plantillas de hook (`views/templates/hook/`)**:
  - `plogin/createAccountForm.tpl`: Renderiza el botón de PayPal en el formulario de registro de clientes.
  - `plogin/displayCustomerLoginFormAfter.tpl`: Renderiza el botón de PayPal después del formulario de inicio de sesión estándar del cliente.
  - `plogin/displayFooter.tpl`: Renderiza el botón de PayPal en el pie de página de la tienda.
  - `plogin/displayHome.tpl`: Renderiza el botón de PayPal en la página de inicio.
  - `plogin/displayleftColumn.tpl`: Renderiza el botón de PayPal en la columna izquierda.
  - `plogin/displayNav.tpl`: Renderiza el botón de PayPal en la barra de navegación principal (hook común para enlaces superiores).
  - `plogin/displayNav1.tpl`: Renderiza el botón de PayPal en un hook de navegación alternativo (dependiente del tema).
  - `plogin/displayNav2.tpl`: Renderiza el botón de PayPal en otro hook de navegación alternativo (dependiente del tema).
  - `plogin/displayPopUpLogin.tpl`: Renderiza el botón de PayPal dentro de un formulario de inicio de sesión emergente (si lo usa el tema).
  - `plogin/displayrightColumn.tpl`: Renderiza el botón de PayPal en la columna derecha.
  - `plogin/displayTop.tpl`: Renderiza el botón de PayPal en la sección superior de la página (dependiente del tema).
  - `plogin/header.tpl`: Esta plantilla probablemente se usa para incluir activos CSS/JS en la sección `<head>` cuando se usa el hook `displayHeader`, en lugar de mostrar un botón visible.
  - `plogin/shoppingCart.tpl`: Renderiza el botón de PayPal dentro del resumen del carrito de compras.
  - `plogin/shoppingCartExtra.tpl`: Renderiza el botón de PayPal en una sección extra del carrito de compras (dependiente del tema).
  - `plogin/top.tpl`: Similar a `displayTop`, para la sección superior de la página.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo no crea tablas SQL personalizadas.
  - La configuración (ID de cliente, Secreto de cliente, estado habilitado, hooks seleccionados, URL de redirección, estilo del botón) se almacena en la tabla `ps_configuration` de PrestaShop, normalmente con claves prefijadas por `PLOGIN_` (por ejemplo, `PLOGIN_CLIENT_ID`, `PLOGIN_ENABLED`).
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución / Ubicación | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Para incluir activos CSS y JavaScript globalmente para el módulo. |
| `displayNav` | En la barra de navegación principal, generalmente en la parte superior de la página. | Muestra el botón de inicio de sesión de PayPal en un área de navegación destacada. |
| `displayNav1` | Hook de navegación alternativo (dependiente del tema). | Proporciona flexibilidad para temas con múltiples áreas de navegación. |
| `displayNav2` | Otro hook de navegación alternativo (dependiente del tema). | Proporciona flexibilidad para temas con múltiples áreas de navegación. |
| `displayTop` | En la sección superior de la página, encima del contenido principal. | Muestra el botón de inicio de sesión de PayPal en la barra superior. |
| `displayLeftColumn` | En la barra lateral izquierda de las páginas que la tienen. | Muestra el botón de inicio de sesión de PayPal en la columna izquierda. |
| `displayRightColumn` | En la barra lateral derecha de las páginas que la tienen. | Muestra el botón de inicio de sesión de PayPal en la columna derecha. |
| `displayFooter` | En la sección del pie de página de la tienda. | Muestra el botón de inicio de sesión de PayPal en el pie de página. |
| `displayHome` | En la página de inicio de la tienda. | Muestra el botón de inicio de sesión de PayPal en la página de aterrizaje principal. |
| `displayCustomerLoginFormAfter` | Después del formulario de inicio de sesión estándar en la página de autenticación. | Proporciona la opción de inicio de sesión de PayPal como alternativa al correo electrónico/contraseña. |
| `createAccountForm` | En la página de registro de clientes. | Ofrece PayPal como un método de registro rápido. |
| `displayPopUpLogin` | Dentro de un modal de inicio de sesión emergente (si lo implementa el tema). | Se integra con los pop-ups de inicio de sesión de temas modernos. |
| `shoppingCart` | Dentro del bloque de resumen del carrito de compras. | Ofrece inicio de sesión/registro durante la fase de revisión del carrito. |
| `shoppingCartExtra` | En una sección extra del carrito de compras (dependiente del tema). | Proporciona flexibilidad de ubicación adicional dentro del carrito. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Conexión de inicio de sesión de PayPal", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema técnico o pregunta relacionada con la funcionalidad del módulo.

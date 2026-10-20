---
title: "Recuperación de contraseña simple - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Recuperación de contraseña simple' de MyPresta.eu."
sidebar:
  label: "Recuperación de contraseña simple - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Simple password recovery en MyPresta.eu](https://mypresta.eu/modules/front-office-features/simple-password-recovery.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/simple-password-recovery/)
>
> ---


# Recuperación de contraseña simple

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones de servidor inusuales.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

El módulo "Recuperación de contraseña simple" está diseñado para ser en gran medida plug-and-play, reemplazando el flujo de recuperación de contraseña predeterminado de PrestaShop con una configuración mínima requerida.

Cuando navegue a **Módulos > Gestor de módulos** y haga clic en "Configurar" junto a "Recuperación de contraseña simple", normalmente encontrará una interfaz de configuración sencilla.

**Qué hace este ajuste:** Esta pantalla le permite habilitar o deshabilitar la funcionalidad principal del módulo y, potencialmente, ajustar configuraciones de comportamiento menores. El propósito principal es activar el proceso simplificado de recuperación de contraseña.

**Efecto de cambiar este ajuste:**

- **Cuando está habilitado:** El módulo toma el control del mecanismo de recuperación de contraseña predeterminado de PrestaShop. Cuando un cliente solicita un restablecimiento de contraseña, recibirá un correo electrónico con un enlace único y seguro que lo dirigirá a una página dedicada para establecer su nueva contraseña. Esto simplifica significativamente la experiencia del usuario.
- **Cuando está deshabilitado:** La funcionalidad del módulo se desactiva. Su tienda PrestaShop volverá a su proceso de recuperación de contraseña estándar predeterminado, que puede implicar más pasos o diferentes métodos de verificación para el cliente.

**Valor recomendado:** **Habilitado (SÍ)**. El beneficio principal de este módulo es simplificar el proceso de recuperación de contraseña. Mantenerlo habilitado asegura que sus clientes se beneficien de esta experiencia mejorada.

**Escenario / ejemplo de comerciante:**
Ha notado que los clientes contactan con frecuencia al soporte porque tienen dificultades con la recuperación de contraseña predeterminada. Al habilitar este módulo, proporciona un enlace directo de un solo clic en el correo electrónico, lo que les permite establecer instantáneamente una nueva contraseña. Esto reduce la confusión y los devuelve a las compras más rápido.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Estado del módulo (Habilitar/Deshabilitar) | Habilitado | Activa o desactiva el proceso simplificado de recuperación de contraseña. Cuando está habilitado, los clientes reciben un enlace directo para establecer una nueva contraseña. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis clientes no reciben los correos electrónicos de restablecimiento de contraseña.**
R:

- **Verifique las carpetas de spam:** Aconseje a los clientes que revisen sus carpetas de spam o correo no deseado.
- **Configuración de correo electrónico:** Verifique la configuración de correo electrónico de PrestaShop en **Parámetros avanzados > E-mail**. Asegúrese de que su configuración SMTP sea correcta o de que la función PHP `mail()` esté funcionando.
- **Conflictos de módulos:** Deshabilite temporalmente otros módulos que puedan interferir con el envío de correo electrónico o la gestión de cuentas de clientes para descartar conflictos.
- **Registros del servidor:** Revise los registros de correo de su servidor en busca de errores relacionados con los correos electrónicos salientes.

**P: El enlace de restablecimiento de contraseña lleva a los clientes a una página en blanco o a un error.**
R:

- **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y borre la caché de Smarty, la caché del navegador y la caché del módulo.
- **Reescritura de URL:** Asegúrese de que la reescritura de URL esté habilitada en PrestaShop (**Parámetros de la tienda > SEO y URLs**) y de que su archivo `.htaccess` esté configurado correctamente.
- **Integridad del módulo:** Vuelva a subir los archivos del módulo a través de FTP para asegurarse de que no haya archivos dañados o faltantes.
- **Compatibilidad del tema:** Aunque es raro, un tema altamente personalizado podría tener conflictos de JavaScript. Revise la consola de desarrollador de su navegador en busca de errores de JavaScript.

**P: ¿Puedo personalizar la apariencia de la nueva página de contraseña?**
R: Sí, el módulo utiliza la plantilla estándar de PrestaShop. La apariencia está controlada principalmente por el CSS de su tema activo de PrestaShop y el propio CSS del módulo (`spreset/views/css/spreset.css`). Los desarrolladores pueden anular estos estilos en el CSS personalizado de su tema o modificando los archivos de plantilla del módulo (`views/templates/front/password-change-form.tpl`, `views/templates/front/simple-reset-page.tpl`, `views/templates/front/simple-reset.tpl`).

**P: ¿Este módulo funciona con tiendas multiidioma?**
R: Sí, como la mayoría de los módulos de PrestaShop, las cadenas de texto son traducibles. Puede traducir las frases del módulo a través de **Internacional > Traducciones** en su Back Office, seleccionando "Traducciones de módulos instalados" y luego buscando "Recuperación de contraseña simple".

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Recuperación de contraseña simple".

### 4.1 Descripción general de la arquitectura

El módulo "Recuperación de contraseña simple" anula el mecanismo de recuperación de contraseña predeterminado de PrestaShop al introducir controladores frontales personalizados para manejar la generación de tokens, el envío de correos electrónicos y el proceso de establecimiento de nuevas contraseñas. Aprovecha el patrón MVC de PrestaShop, con controladores dedicados para las diferentes etapas de la recuperación. El archivo principal del módulo (`index.php`) gestiona la instalación, desinstalación y el formulario de configuración principal.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `controllers/front/changepass.php`
    - **Nombre de la clase**: `SpresetChangepassModuleFrontController` (extiende `ModuleFrontController`)
    - **Responsabilidad**: Este controlador es responsable de mostrar el formulario donde un cliente puede establecer su nueva contraseña después de hacer clic en el enlace de restablecimiento seguro. Valida el token proporcionado en la URL y maneja el envío de la nueva contraseña.
  - `controllers/front/index.php`
    - **Nombre de la clase**: `SpresetIndexModuleFrontController` (extiende `ModuleFrontController`)
    - **Responsabilidad**: Este controlador probablemente sirve como un recurso alternativo o un punto de entrada general para la funcionalidad de front-office del módulo, potencialmente redirigiendo o manejando solicitudes iniciales relacionadas con el proceso de restablecimiento de contraseña. En muchos casos, podría ser un marcador de posición o usarse para un enrutamiento específico.
  - `controllers/front/simplereset.php`
    - **Nombre de la clase**: `SpresetSimpleresetModuleFrontController` (extiende `ModuleFrontController`)
    - **Responsabilidad**: Este controlador es el núcleo del proceso de restablecimiento simplificado. Recibe la solicitud inicial de restablecimiento de contraseña (por ejemplo, del formulario estándar de PrestaShop "Olvidé mi contraseña"), genera el token seguro, envía el correo electrónico con el enlace de restablecimiento único y maneja la validación inicial de la dirección de correo electrónico del cliente.
- **Controladores de administración de Back-Office**: Ninguno. La configuración del módulo se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no parece definir clases personalizadas que extiendan `ObjectModel` u otras clases principales de PrestaShop dentro de un directorio `classes/` dedicado. Su lógica está principalmente encapsulada dentro del archivo principal del módulo y sus controladores frontales.

### 4.4 Activos JavaScript (`views/js/`)

- `views/js/spreset.js`
  - **Alcance**: Front-office.
  - **Detalles**: Este script probablemente maneja la validación del lado del cliente para el formulario de nueva contraseña (por ejemplo, verificar si las contraseñas coinciden, requisitos de longitud mínima) y potencialmente envíos AJAX para el cambio de contraseña. También podría incluir mejoras de la interfaz de usuario o interacciones específicas de la página de restablecimiento de contraseña. Los desarrolladores deben inspeccionar este archivo en busca de detectores de eventos específicos (por ejemplo, `submit` en el formulario de contraseña) y cualquier función personalizada.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `views/css/spreset.css`
  - **Alcance**: Estilo del cliente de Front-office.
  - **Detalles**: Esta hoja de estilo proporciona un estilo específico para los componentes de front-office del módulo, principalmente el formulario de entrada de nueva contraseña y las páginas asociadas. Asegura que la interfaz de recuperación de contraseña tenga una apariencia presentable y se integre razonablemente bien con varios temas. Los desarrolladores pueden inspeccionar este archivo para identificar selectores de clase CSS clave (por ejemplo, `.spreset-form`, `.spreset-input`, `.spreset-button`) que se pueden anular en el archivo CSS personalizado de su tema para que coincidan con la marca de la tienda.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de Front-office (`views/templates/front/`)**:

  - `views/templates/front/password-change-form.tpl`
    - **Propósito**: Esta plantilla probablemente renderiza el formulario real donde el cliente introduce y confirma su nueva contraseña. Contendría campos de entrada para "Nueva contraseña" y "Confirmar nueva contraseña", junto con un botón de envío.
  - `views/templates/front/simple-reset-page.tpl`
    - **Propósito**: Esta plantilla podría servir como el contenedor principal o el diseño para el proceso de restablecimiento de contraseña simplificado, potencialmente incluyendo mensajes, instrucciones e incrustando otras plantillas parciales como `password-change-form.tpl`.
  - `views/templates/front/simple-reset.tpl`
    - **Propósito**: Similar a `simple-reset-page.tpl`, esta plantilla forma parte de la visualización de front-office para el flujo de restablecimiento de contraseña. Podría usarse para el formulario inicial de "introduzca su correo electrónico" o para mostrar mensajes de éxito/error relacionados con la solicitud de restablecimiento.
- **Plantillas específicas del módulo (`views/templates/`)**:

  - `views/templates/spreset.tpl`
    - **Propósito**: Esta plantilla probablemente se utiliza para la configuración principal del módulo en el Back Office (si `getContent()` renderiza una plantilla) o para un hook de visualización genérico si el módulo tiene una salida simple para un hook. Dada la naturaleza del módulo, es más probable que sea para la configuración del Back Office.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: El módulo no parece crear tablas SQL personalizadas. Probablemente utiliza tablas existentes de PrestaShop (por ejemplo, `ps_customer` para datos de clientes, `ps_configuration` para la configuración del módulo) y genera tokens temporales sin almacenamiento persistente en una tabla dedicada. Los tokens suelen almacenarse en la sesión o pasarse a través de parámetros de URL con una caducidad corta.
- **Tabla de hooks registrados**:
  El módulo no enumera explícitamente los hooks registrados en la información proporcionada, pero basándose en su funcionalidad, interactuaría implícitamente con el flujo de recuperación de contraseña estándar de PrestaShop, que a menudo se activa mediante los hooks `displayCustomerAccountForm` o `actionAuthenticationBefore`, o anulando los controladores principales de PrestaShop.
  El archivo principal del módulo (`index.php`) registraría sus controladores frontales para manejar rutas específicas, "enganchándose" efectivamente al sistema de enrutamiento de URL en lugar de los hooks tradicionales `display` o `action` para la salida visual.

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Recuperación de contraseña simple", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar el rendimiento y la compatibilidad óptimos de nuestros módulos con las últimas versiones de PrestaShop.

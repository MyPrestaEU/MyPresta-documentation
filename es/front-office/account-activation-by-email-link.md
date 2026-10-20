---
title: "Activación de cuenta por enlace de correo electrónico - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Activación de cuenta por enlace de correo electrónico' de MyPresta.eu."
sidebar:
  label: "Activación de cuenta por enlace de correo electrónico - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Account activation by email link en MyPresta.eu](https://mypresta.eu/modules/front-office-features/account-activation-by-email-link.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/account-activation-by-email-link/)
>
> ---


# Activación de cuenta por enlace de correo electrónico

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Activación de cuenta por enlace de correo electrónico". Puede acceder a ella navegando a **Módulos > Gestor de módulos** y haciendo clic en "Configurar" junto al nombre del módulo.

#### **Configuración general**

- **Enviar correo electrónico con enlace de activación de cuenta al administrador:**

  - **Qué hace este ajuste:** Controla si también se envía una notificación por correo electrónico al administrador de la tienda (usted) cada vez que un nuevo cliente se registra y necesita activar su cuenta.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado ("Sí"):* Recibirá una notificación por correo electrónico a la dirección de correo electrónico de contacto principal de su tienda (normalmente `PS_SHOP_EMAIL`) cada vez que un nuevo cliente se registre y esté esperando la activación. Esto puede ser útil para monitorear nuevos registros.
    - *Cuando está deshabilitado ("No"):* No se enviará ninguna notificación por correo electrónico al administrador al registrarse un nuevo cliente.
  - **Valor recomendado:** "No" para la mayoría de las tiendas para evitar el desorden de correos electrónicos, a menos que necesite monitorear específicamente cada nuevo registro.
  - **Escenario / ejemplo de comerciante:** Si tiene una tienda pequeña y de nicho y desea dar la bienvenida o revisar personalmente a cada nuevo cliente, habilitar esto puede mantenerlo informado. Para tiendas más grandes, suele ser innecesario.
- **Título del correo electrónico al administrador:**

  - **Qué hace este ajuste:** Define la línea de asunto del correo electrónico enviado al administrador cuando se registra una nueva cuenta (si "Enviar correo electrónico con enlace de activación de cuenta al administrador" está habilitado).
  - **Efecto de cambiar este ajuste:** Cambia la línea de asunto del correo electrónico de notificación al administrador.
  - **Valor recomendado:** "Nuevo registro de cliente pendiente de activación - {shop\_name}" (o similar, usando `{shop_name}` para el nombre de su tienda).
  - **Escenario / ejemplo de comerciante:** Es posible que desee incluir el nombre de su tienda en el título para una fácil identificación en su bandeja de entrada, por ejemplo, "Nuevo cliente en Mi Tienda Impresionante - Activación pendiente".
- **Iniciar sesión automáticamente al cliente después de la activación:**

  - **Qué hace este ajuste:** Determina si un cliente inicia sesión automáticamente en su cuenta inmediatamente después de hacer clic en el enlace de activación de su correo electrónico.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado ("Sí"):* Después de hacer clic en el enlace de activación, el cliente inicia sesión sin problemas en su cuenta recién activada y normalmente es redirigido a su panel de cuenta o a la página de inicio. Esto proporciona una experiencia de usuario más fluida.
    - *Cuando está deshabilitado ("No"):* Después de hacer clic en el enlace de activación, la cuenta del cliente se activa, pero *no* inicia sesión automáticamente. Será redirigido a la página de inicio de sesión y se le pedirá que introduzca sus credenciales manualmente.
  - **Valor recomendado:** "Sí" para una mejor experiencia del cliente, reduciendo la fricción.
  - **Escenario / ejemplo de comerciante:** Habilitar esto hace que el proceso de activación se sienta más completo y fácil de usar, ya que el cliente no tiene que dar un paso adicional después de verificar su correo electrónico.
- **Activar cuenta en página específica:**

  - **Qué hace este ajuste:** Le permite definir una página específica en su tienda a la que el cliente será redirigido *después* de que su cuenta se active con éxito.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado ("Sí"):* El módulo utilizará la URL especificada en el campo "Enlace de página de activación específica" para la redirección después de la activación.
    - *Cuando está deshabilitado ("No"):* El cliente será redirigido a la página predeterminada (normalmente la página de inicio o la página de su cuenta de cliente) después de la activación.
  - **Valor recomendado:** "No" por defecto, a menos que tenga una estrategia de marketing o de incorporación específica.
  - **Escenario / ejemplo de comerciante:** Es posible que desee redirigir a los nuevos clientes a una página de "Bienvenida" con ofertas especiales, una guía de su tienda o una categoría de producto específica para fomentar su primera compra.
- **Enlace de página de activación específica:**

  - **Qué hace este ajuste:** Este campo aparece solo si "Activar cuenta en página específica" está habilitado. Es donde introduce la URL completa de la página a la que desea redirigir a los clientes después de la activación.
  - **Efecto de cambiar este ajuste:** Define la URL de destino exacta para la redirección posterior a la activación.
  - **Valor recomendado:** Dejar vacío si "Activar cuenta en página específica" está en "No". Si está habilitado, proporcione una URL completa y válida (por ejemplo, `https://sutenda.com/content/1-entrega`).
  - **Escenario / ejemplo de comerciante:** Si tiene una página de "Bienvenida al nuevo cliente" en `https://sutenda.com/bienvenida-nuevos-clientes`, introduciría esa URL aquí.

#### **Configuración del contenido del correo electrónico**

- **Título del correo electrónico al cliente:**
  - **Qué hace este ajuste:** Define la línea de asunto del correo electrónico de activación enviado al cliente.
  - **Efecto de cambiar este ajuste:** Cambia la línea de asunto que los clientes ven en su bandeja de entrada para el correo electrónico de activación.
  - **Valor recomendado:** "Active su cuenta en {shop\_name}" o "Por favor, verifique su correo electrónico para {shop\_name}" (usando `{shop_name}` para el nombre de su tienda).
  - **Escenario / ejemplo de comerciante:** Una línea de asunto clara y concisa ayuda a los clientes a identificar el correo electrónico y los anima a abrirlo, reduciendo la posibilidad de que se marque como spam.

#### **Otros ajustes (Internos / Técnicos)**

- **mypresta\_updates, update\_, updatev\_:** Estos son ajustes internos utilizados por los módulos de MyPresta.eu para comprobaciones de actualizaciones y gestión de versiones. Generalmente, **no** debe modificarlos.
- **PS\_SHOP\_EMAIL, PS\_SHOP\_NAME, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG, PS\_CART\_FOLLOWING:** Estos son valores de configuración estándar de PrestaShop que el módulo puede leer o mostrar para el contexto, pero no son directamente configurables dentro del propio módulo. Reflejan su configuración general de PrestaShop.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Enviar correo electrónico con enlace de activación de cuenta al administrador | No | Controla la notificación al administrador para nuevos registros. |
| Configuración del módulo | Título del correo electrónico al administrador | "Nuevo registro de cliente pendiente de activación - {shop\_name}" | Línea de asunto para el correo electrónico de notificación al administrador. |
| Configuración del módulo | Iniciar sesión automáticamente al cliente después de la activación | Sí | Inicia sesión automáticamente al cliente después de una activación exitosa. |
| Configuración del módulo | Activar cuenta en página específica | No | Habilita la redirección a una página personalizada después de la activación. |
| Configuración del módulo | Enlace de página de activación específica | (Vacío si está deshabilitado) | URL para la redirección posterior a la activación (si está habilitado). |
| Configuración del módulo | Título del correo electrónico al cliente | "Active su cuenta en {shop\_name}" | Línea de asunto para el correo electrónico de activación del cliente. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: Mis clientes no reciben el correo electrónico de activación. ¿Qué debo hacer?**

- **R:**
  1. **Verifique las carpetas de spam/correo no deseado:** Aconseje a los clientes que revisen sus carpetas de spam o correo no deseado.
  2. **Verifique la configuración de correo electrónico de la tienda:** Vaya a **Parámetros de la tienda > Contacto > Tiendas** (o **Parámetros avanzados > Correo electrónico** en versiones anteriores) en su Back Office de PrestaShop. Asegúrese de que la configuración de correo electrónico de su tienda sea correcta y de que los correos electrónicos se envíen correctamente (pruebe enviando un correo electrónico de prueba).
  3. **Funcionalidad de correo del servidor:** Póngase en contacto con su proveedor de alojamiento para asegurarse de que la función de correo de su servidor (PHP `mail()` o SMTP) funciona correctamente y no está siendo bloqueada.
  4. **Configuración del módulo:** Vuelva a verificar el "Título del correo electrónico al cliente" en la configuración del módulo. Un título muy genérico o de aspecto sospechoso podría activar los filtros de spam.
  5. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los problemas de caché pueden impedir el envío de correos electrónicos.

**P2: Un cliente activó su cuenta pero aún no puede iniciar sesión.**

- **A:**
  1. **Verificar el estado del cliente:** En su Back Office de PrestaShop, vaya a **Clientes > Clientes**. Busque la cuenta del cliente y verifique que su estado "Habilitado" esté configurado en "Sí". Si no, habilítelo manualmente.
  2. **Restablecer contraseña:** Sugiera al cliente que pruebe el enlace "Olvidé mi contraseña" en su página de inicio de sesión. Esto puede resolver problemas si están recordando mal su contraseña.
  3. **Caché/cookies del navegador:** Pida al cliente que borre la caché y las cookies de su navegador, o que intente iniciar sesión desde un navegador diferente o una ventana de incógnito.
  4. **Conflicto de módulos:** Deshabilite temporalmente otros módulos que interactúen con las cuentas de clientes o los procesos de inicio de sesión para descartar conflictos.

**P3: ¿Cómo puedo activar manualmente la cuenta de un cliente si no puede recibir el correo electrónico?**

- **A:** Puede activar manualmente la cuenta de un cliente desde el Back Office de PrestaShop:
  1. Vaya a **Clientes > Clientes**.
  2. Busque el nombre del cliente en la lista y haga clic en "Editar" (el icono del lápiz).
  3. En la página de detalles del cliente, localice el interruptor "Habilitado" y configúrelo en "Sí".
  4. Haga clic en "Guardar". El cliente ahora podrá iniciar sesión.

**P4: El enlace de activación redirige a la página incorrecta o muestra un error.**

- **A:**
  1. **Verificación del "Enlace de página de activación específica":** Si tiene "Activar cuenta en página específica" habilitado, verifique que la URL introducida en "Enlace de página de activación específica" sea absolutamente correcta y accesible. Un error tipográfico o una URL no válida causará problemas de redirección.
  2. **URLs amigables:** Asegúrese de que sus URLs amigables estén habilitadas y funcionando correctamente (**Parámetros de la tienda > Tráfico y SEO**).
  3. **Borrar caché:** Borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento**).
  4. **Verifique .htaccess:** Si ha realizado algún cambio manual en su archivo `.htaccess`, reviértalos o asegúrese de que no estén interfiriendo con la reescritura de URL.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Activación de cuenta por enlace de correo electrónico" (`acactiv`) es un módulo estándar de PrestaShop diseñado principalmente para interceptar el proceso de registro de clientes. Aprovecha el sistema de hooks de PrestaShop para modificar el comportamiento predeterminado, específicamente `actionCustomerAccountAdd` para marcar las nuevas cuentas como inactivas y enviar correos electrónicos de activación, y `displayHeader` para inyectar el JavaScript necesario. El módulo no introduce nuevas tablas de base de datos ni estructuras `ObjectModel` complejas, sino que se basa en la modificación de las propiedades existentes del objeto `Customer` y en el uso de `ps_configuration` para sus ajustes.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores dedicados de front-office o back-office. Toda la lógica se maneja dentro del archivo principal del módulo (`acactiv.php`) y sus hooks registrados. El propio enlace de activación apunta al despacho principal del módulo, que luego maneja la lógica de activación.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase o modelo personalizado en el directorio `classes/`. Interactúa directamente con la clase `Customer` y la clase `Configuration` del núcleo de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

- **`acactiv/views/acactiv-compat.js`**

  - **Alcance:** Front-office.
  - **Propósito:** Este script probablemente contiene correcciones de compatibilidad o polyfills para versiones o navegadores más antiguos de PrestaShop, asegurando que la funcionalidad de front-end del módulo funcione en una gama más amplia de entornos. Podría abordar diferencias en las versiones de jQuery o los métodos de manipulación del DOM.
  - **Detectores de eventos/Manipulación del DOM:** Los detalles requerirían una revisión del código, pero típicamente implica asegurar que los elementos estén presentes o ajustar comportamientos basados en la versión de PrestaShop.
- **`acactiv/views/acactiv.js`**

  - **Alcance:** Front-office.
  - **Propósito:** Este es el archivo JavaScript principal para las interacciones del front-office. Es responsable de mostrar mensajes al usuario después del registro (por ejemplo, "Verifique su correo electrónico para el enlace de activación") y potencialmente de manejar aspectos del lado del cliente del proceso de activación.
  - **Detectores de eventos/Manipulación del DOM:**
    - Puede escuchar los envíos de formularios en la página de registro para mostrar mensajes personalizados.
    - Podría manipular el DOM para mostrar/ocultar elementos, mostrar notificaciones emergentes o redirigir al usuario después de ciertas acciones.
    - Podría usar `prestashop.on('updatedProduct', function(event) { ... });` o detectores de eventos similares de PrestaShop si necesita reaccionar a las actualizaciones de contenido dinámico, aunque es menos probable para la función principal de este módulo.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`acactiv/views/acactiv.css`**
  - **Alcance:** Estilo del cliente del front-office.
  - **Propósito:** Proporciona un estilo básico para cualquier mensaje o elemento personalizado introducido por el módulo en el front office. Esto podría incluir el estilo para el mensaje de "cuenta pendiente de activación" o la confirmación de "cuenta activada".
  - **Selectores de clase CSS clave:** Los desarrolladores deben inspeccionar el HTML de salida del módulo para identificar clases específicas (por ejemplo, `.acactiv-message`, `.acactiv-success`, `.acactiv-error`) que se pueden sobrescribir en el `custom.css` o `theme.css` de su tema para que coincidan con la marca de la tienda.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:

  - **`acactiv/views/checkout_notice.tpl`**
    - **Hook:** No se indica explícitamente como plantilla de hook, pero su nombre sugiere que podría renderizarse en un contexto relacionado con el checkout o la creación de cuentas, posiblemente a través de `displayCustomerAccountForm` o similar, para mostrar un aviso sobre la activación.
    - **Salida:** Probablemente muestra un mensaje informativo al cliente después del registro, instruyéndole a revisar su correo electrónico para el enlace de activación.
  - **`acactiv/views/displayHeader.tpl`**
    - **Hook:** `displayHeader`
    - **Salida:** Esta plantilla se utiliza típicamente para incluir archivos CSS y JavaScript en la sección `<head>` de las páginas del front-office. Contendrá etiquetas `<link>` para `acactiv.css` y etiquetas `<script>` para `acactiv-compat.js` y `acactiv.js`, asegurando que estos activos se carguen en las páginas relevantes.
- **Plantillas de administración (`views/templates/admin/`)**: Ninguna identificada. La configuración se maneja directamente en `getContent()` dentro de `acactiv.php`.
- **Plantillas de front-office (`views/templates/front/`)**: Ninguna identificada como páginas independientes dedicadas.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo no crea tablas SQL personalizadas.
  - Modifica la columna `active` de la tabla `ps_customer` (estableciéndola en `0` para nuevos registros hasta que se activen).
  - La configuración se almacena en la tabla `ps_configuration` con claves como `ACACTIV_SENDTOME`, `ACACTIV_SPECURLFEATURE`, `ACACTIV_SPECURL`, `ACACTIV_AUTOLOGIN`, `ACACTIV_ATITLE`, `ACACTIV_CTITLE`.
- **Tabla de hooks registrados**:
"""

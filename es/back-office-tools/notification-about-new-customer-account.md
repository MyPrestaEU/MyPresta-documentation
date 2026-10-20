---
title: "Notificación sobre nueva cuenta de cliente - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Notificación sobre nueva cuenta de cliente' de MyPresta.eu."
sidebar:
  label: "Notificación sobre nueva cuenta de cliente - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Notification about new customer account en MyPresta.eu](https://mypresta.eu/modules/administration-tools/notification-about-new-customer-account.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/notification-about-new-customer-account/)
>
> ---


# Notificación sobre nueva cuenta de cliente

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y generalmente están habilitadas por defecto en la mayoría de los entornos de alojamiento.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Notificación sobre nueva cuenta de cliente". Se le presentará la pantalla de configuración principal.

#### **1. Enviar notificación al propietario de la tienda sobre una nueva cuenta de cliente**

-   **Qué hace este ajuste:** Este interruptor controla si usted, el propietario de la tienda, recibe una notificación por correo electrónico cuando un nuevo cliente se registra en su tienda.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Cada vez que un cliente crea una cuenta con éxito en el front office de su tienda, se enviará un correo electrónico a la(s) dirección(es) de correo electrónico especificada(s) en el campo "Dirección(es) de correo electrónico para notificaciones" a continuación.
    -   *Cuando está deshabilitado (NO):* No recibirá ninguna notificación por correo electrónico sobre nuevos registros de clientes.
-   **Valor recomendado:** SÍ.
-   **Escenario / ejemplo de comerciante:** Desea estar inmediatamente al tanto de los nuevos registros de clientes para realizar un seguimiento del crecimiento o identificar posibles clientes potenciales para una campaña de bienvenida. Habilitar esto garantiza que obtenga esa información crucial.

#### **2. Dirección(es) de correo electrónico para notificaciones**

-   **Qué hace este ajuste:** Este campo especifica la(s) dirección(es) de correo electrónico a la(s) que se enviarán las notificaciones de registro de nuevos clientes.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en una o más direcciones de correo electrónico:* Las notificaciones se entregarán a estas direcciones. Si introduce varias direcciones, sepárelas con una coma (por ejemplo, `admin@sutienda.com, soporte@sutienda.com`).
    -   *Cuando se deja vacío:* Incluso si "Enviar notificación al propietario de la tienda" está habilitado, no se enviarán correos electrónicos porque no hay destinatario.
-   **Valor recomendado:** Su dirección de correo electrónico principal de administración de la tienda, o un correo electrónico de equipo dedicado (por ejemplo, `info@sutienda.com`).
-   **Escenario / ejemplo de comerciante:** Desea que tanto usted como su equipo de atención al cliente reciban alertas de nuevos registros. Introduciría `sunombre@sutienda.com, soporte@sutienda.com` aquí.

#### **3. Enviar notificación al cliente si el administrador crea una nueva cuenta**

-   **Qué hace este ajuste:** Este interruptor determina si se envía automáticamente un correo electrónico de bienvenida a un cliente si su cuenta es creada manualmente por un administrador en el Back Office de PrestaShop (por ejemplo, a través de Clientes > Añadir nuevo cliente).
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Cuando usted u otro administrador crea una nueva cuenta de cliente en el Back Office, el cliente recién creado recibirá automáticamente un correo electrónico de bienvenida. Este correo electrónico suele incluir sus datos de inicio de sesión o una confirmación de la creación de su cuenta.
    -   *Cuando está deshabilitado (NO):* Los clientes cuyas cuentas se crean manualmente en el Back Office no recibirán ningún correo electrónico de bienvenida automático del módulo. Tendría que informarles manualmente si lo desea.
-   **Valor recomendado:** SÍ.
-   **Escenario / ejemplo de comerciante:** Con frecuencia crea cuentas para clientes B2B o para clientes que realizan pedidos por teléfono. Habilitar esto garantiza que reciban un correo electrónico de bienvenida inmediato y profesional sin que usted tenga que redactar y enviar uno manualmente cada vez.

#### **4. Botón Guardar**

-   **Qué hace:** Después de realizar cualquier cambio en los ajustes anteriores, debe hacer clic en este botón para aplicar y guardar su nueva configuración.
-   **Efecto de hacer clic:** Sus cambios se guardan en la base de datos y el módulo comenzará a funcionar de acuerdo con los nuevos ajustes inmediatamente.
-   **Acción recomendada:** Siempre haga clic en "Guardar" después de modificar cualquier ajuste.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Enviar notificación al propietario de la tienda sobre una nueva cuenta de cliente | SÍ | Controla si el propietario de la tienda recibe un correo electrónico al registrarse un nuevo cliente. |
| Configuración del módulo | Dirección(es) de correo electrónico para notificaciones | Correo electrónico principal de su tienda | Especifica el/los destinatario(s) de las notificaciones del propietario (separados por comas). |
| Configuración del módulo | Enviar notificación al cliente si el administrador crea una nueva cuenta | SÍ | Controla si el cliente recibe un correo electrónico de bienvenida cuando el administrador crea su cuenta. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: No recibo notificaciones de nuevos clientes, pero el módulo está habilitado. ¿Qué debo verificar?**
R1:

-   **Verifique las direcciones de correo electrónico:** Vuelva a verificar el campo "Dirección(es) de correo electrónico para notificaciones" en la configuración del módulo. Asegúrese de que esté ingresado correctamente y que no haya errores tipográficos. Si hay varias, asegúrese de que estén separadas por comas.
-   **Carpeta de spam:** Revise la carpeta de spam o correo no deseado de su correo electrónico. Las notificaciones podrían estar filtradas allí.
-   **Configuración de correo electrónico de PrestaShop:** Verifique que la configuración principal de correo electrónico de su PrestaShop (Parámetros avanzados > Correo electrónico) esté configurada correctamente y envíe correos electrónicos con éxito. Puede enviar un correo electrónico de prueba desde allí.
-   **Problemas de correo electrónico del alojamiento:** Póngase en contacto con su proveedor de alojamiento para asegurarse de que no haya restricciones de envío de correo electrónico del lado del servidor o problemas con su servidor de correo.

**P2: Mis clientes no reciben correos electrónicos de bienvenida cuando creo sus cuentas en el Back Office.**
R2:

-   **Configuración del módulo:** Asegúrese de que "Enviar notificación al cliente si el administrador crea una nueva cuenta" esté configurado en SÍ en la configuración del módulo.
-   **Correo electrónico del cliente:** Verifique que la dirección de correo electrónico ingresada para el cliente en el Back Office sea correcta y válida.
-   **Carpeta de spam del cliente:** Aconseje al cliente que revise su carpeta de spam o correo no deseado.
-   **Configuración de correo electrónico de PrestaShop:** Como se indicó anteriormente, asegúrese de que la configuración general de correo electrónico de su tienda funcione correctamente.

**P3: ¿Puedo personalizar el contenido de los correos electrónicos de notificación?**
R3: Este módulo, en su versión actual, envía correos electrónicos estándar del sistema PrestaShop. La personalización del contenido normalmente requeriría la modificación directa de las plantillas de correo electrónico de PrestaShop (que se encuentran en el directorio `mails/` para su idioma) o el código central del módulo, lo cual no se recomienda para los comerciantes. Para una personalización avanzada, consulte a un desarrollador.

**P4: ¿Este módulo ralentizará mi tienda?**
R4: No. Este módulo realiza una operación muy ligera (enviar un correo electrónico) solo cuando se crea una nueva cuenta de cliente. No añade ninguna sobrecarga a la carga de páginas ni al rendimiento general de la tienda.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Notificación sobre nueva cuenta de cliente".

### 4.1 Descripción general de la arquitectura

El módulo `registernotification` es un módulo estándar de PrestaShop que sigue el patrón similar a MVC. Principalmente aprovecha el sistema de hooks de PrestaShop para interceptar eventos relacionados con el registro de clientes y luego utiliza la clase `Mail` de PrestaShop para enviar notificaciones. Almacena su configuración directamente en la tabla `ps_configuration`.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza ningún controlador personalizado de front-office o back-office. Toda la lógica está encapsulada dentro de la clase principal del módulo y su método `getContent()` para la configuración.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada o instancias de `ObjectModel`. Toda la lógica central reside dentro de la clase principal `registernotification`.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

Este módulo no incluye ningún archivo de plantilla Smarty personalizado. Se basa en las plantillas de correo electrónico predeterminadas de PrestaShop para las notificaciones a los clientes.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    El módulo no crea ninguna tabla de base de datos personalizada. Todos sus ajustes de configuración se almacenan en la tabla `ps_configuration` utilizando claves con el prefijo `REGISTERNOTIFICATION_`.

    -   Entradas de `PS_CONFIGURATION`:
        -   `REGISTERNOTIFICATION_SEND_OWNER`: Almacena el valor booleano (0 o 1) para enviar notificaciones al propietario de la tienda.
        -   `REGISTERNOTIFICATION_EMAIL_ADDRESSES`: Almacena la cadena de direcciones de correo electrónico separadas por comas para las notificaciones del propietario.
        -   `REGISTERNOTIFICATION_SEND_CUSTOMER_ADMIN`: Almacena el valor booleano (0 o 1) para enviar notificaciones a los clientes cuando son creados por un administrador.
-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Se ejecuta inmediatamente después de que una nueva cuenta de cliente se añade con éxito a la base de datos. | Este hook se utiliza para activar la notificación por correo electrónico al propietario de la tienda cuando un cliente se registra a través del front office. También activa el correo electrónico de bienvenida al cliente si su cuenta fue creada por un administrador en el back office. |
| `displayBackOfficeHeader` | Se ejecuta cuando se renderiza el encabezado del Back Office. | Típicamente utilizado para añadir CSS/JS o mostrar alertas en el Back Office. Aunque se enumera como un hook potencial, su uso principal en este módulo sería para mostrar un mensaje de éxito/error después de guardar la configuración, o potencialmente para añadir activos específicos del módulo (aunque no hay ninguno presente). |

### 4.8 Estructura de archivos del módulo (`registernotification/`)

-   `index.php`: El archivo principal del módulo. Este archivo contiene la clase `registernotification`, que extiende `Module`. Maneja:
    -   `__construct()`: Inicialización del módulo, configuración del nombre, pestaña, versión, autor, etc.
    -   `install()`: Registra los hooks necesarios (`actionCustomerAccountAdd`, `displayBackOfficeHeader`) y establece los valores de configuración predeterminados en `ps_configuration`.
    -   `uninstall()`: Anula el registro de los hooks y elimina los valores de configuración.
    -   `getContent()`: Renderiza el formulario de configuración del módulo en el Back Office, maneja el envío del formulario y actualiza `ps_configuration`.
    -   `hookActionCustomerAccountAdd($params)`: La lógica central para enviar correos electrónicos. Verifica la configuración del módulo y utiliza `Mail::Send()` para enviar correos electrónicos al propietario y/o al nuevo cliente según el contexto de la creación de la cuenta.
    -   `hookDisplayBackOfficeHeader()`: Potencialmente utilizado para mostrar mensajes de confirmación después de guardar la configuración.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Notificación sobre nueva cuenta de cliente", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.

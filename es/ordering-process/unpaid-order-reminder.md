---
title: "Recordatorio de pedidos impagados - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Recordatorio de pedidos impagados' de MyPresta.eu."
sidebar:
  label: "Recordatorio de pedidos impagados - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Unpaid order reminder en MyPresta.eu](https://mypresta.eu/modules/ordering-process/unpaid-order-reminder.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/unpaid-order-reminder/)
>
> ---


# Recordatorio de pedidos impagados

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Asegúrese de que la funcionalidad de cron job de su servidor esté habilitada y configurada correctamente para que los recordatorios automáticos del módulo funcionen.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

El módulo "Recordatorio de pedidos impagados" ofrece varias pantallas de configuración para gestionar sus ajustes de recordatorio, ver el historial y manejar a los clientes dados de baja.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Recordatorio de pedidos impagados)

Esta es la pantalla de configuración principal donde se establece el comportamiento central del módulo.

-   **Qué hace este ajuste:** Esta sección le permite habilitar o deshabilitar el módulo, configurar el cron job y gestionar los ajustes generales para sus correos electrónicos de recordatorio.
-   **Efecto de cambiar este ajuste:** Controla la funcionalidad general y la automatización del sistema de recordatorios.

#### Ajustes generales

-   **Habilitar módulo:**

    -   **Qué hace este ajuste:** Activa o desactiva todo el módulo "Recordatorio de pedidos impagados".
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* El módulo comenzará a enviar recordatorios según sus reglas definidas y el cron job.
        -   *Cuando está deshabilitado:* No se enviarán recordatorios y el módulo estará inactivo.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo de comerciante:** Habilítelo después de haber configurado sus reglas de recordatorio para comenzar a recuperar pedidos impagados. Desactívelo si necesita detener temporalmente todos los recordatorios para mantenimiento o una campaña específica.
-   **URL del Cron Job:**

    -   **Qué hace este ajuste:** Muestra la URL única que el cron job de su servidor necesita ejecutar periódicamente. Esta URL activa el módulo para que busque pedidos impagados y envíe recordatorios.
    -   **Efecto de cambiar este ajuste:** Esta URL es crucial para la automatización del módulo. Sin que sea llamada por un cron job, no se enviarán recordatorios automáticamente.
    -   **Valor recomendado:** Copie esta URL y configúrela en el gestor de cron jobs de su panel de control de alojamiento.
    -   **Escenario / ejemplo de comerciante:** Normalmente lo configurará una vez durante la configuración inicial. Por ejemplo, podría configurar su servidor para llamar a esta URL cada hora para asegurar recordatorios oportunos.
-   **Enlace para darse de baja en el correo electrónico:**

    -   **Qué hace este ajuste:** Determina si se incluye un enlace para darse de baja en los correos electrónicos de recordatorio.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Los clientes pueden hacer clic en un enlace en el correo electrónico para optar por no recibir futuros recordatorios de pedidos impagados.
        -   *Cuando está deshabilitado:* Los clientes no pueden darse de baja fácilmente, lo que podría generar frustración o hacer que sus correos electrónicos se marquen como spam.
    -   **Valor recomendado:** SÍ (Altamente recomendado para el cumplimiento y la satisfacción del cliente).
    -   **Escenario / ejemplo de comerciante:** Incluya siempre esto para dar control a los clientes y mantener una buena reputación como remitente.
-   **Estados de pedido para recordar:**

    -   **Qué hace este ajuste:** Le permite seleccionar qué estados de pedido específicos deben activar un recordatorio. Típicamente, estos son estados que indican que un pedido está pendiente de pago (por ejemplo, "Esperando pago por transferencia bancaria", "Esperando pago por cheque").
    -   **Efecto de cambiar este ajuste:** Solo los pedidos con los estados seleccionados serán considerados para recordatorios.
    -   **Valor recomendado:** Seleccione todos los estados que representen un pedido pendiente de pago.
    -   **Escenario / ejemplo de comerciante:** Si utiliza "Esperando pago por transferencia bancaria" y "Esperando pago por cheque", seleccione ambos. Si tiene un estado personalizado como "Pago pendiente de pasarela", inclúyalo también.
-   **Estados de pedido para detener recordatorios:**

    -   **Qué hace este ajuste:** Define qué estados de pedido, si se alcanzan, deben detener cualquier recordatorio adicional para ese pedido específico. Esto generalmente incluye estados como "Pago aceptado", "Enviado" o "Cancelado".
    -   **Efecto de cambiar este ajuste:** Una vez que un pedido alcanza uno de estos estados, el módulo ya no enviará recordatorios para él, evitando correos electrónicos innecesarios o confusos.
    -   **Valor recomendado:** Seleccione todos los estados que indiquen que el pago ha sido recibido, el pedido ha sido procesado o el pedido ya no es válido (por ejemplo, "Pago aceptado", "Cancelado", "Reembolsado").
    -   **Escenario / ejemplo de comerciante:** Si un cliente paga un pedido, no querrá que reciba otro recordatorio. Seleccionar "Pago aceptado" aquí asegura esto.

#### Reglas de recordatorio

Esta sección es donde define los correos electrónicos de recordatorio reales. Puede crear múltiples reglas, cada una con diferente tiempo y contenido de correo electrónico.

-   **Añadir nueva regla de recordatorio:**
    -   **Qué hace este ajuste:** Le permite crear un nuevo conjunto de parámetros de recordatorio.
    -   **Efecto de cambiar este ajuste:** Abre un formulario para definir un nuevo correo electrónico de recordatorio.
    -   **Valor recomendado:** Cree al menos una regla.
    -   **Escenario / ejemplo de comerciante:** Es posible que desee enviar un primer recordatorio después de 24 horas y un segundo, más urgente, después de 72 horas.

Al añadir/editar una regla, configurará:

-   **Días después de la creación del pedido:**

    -   **Qué hace este ajuste:** Especifica cuántos días después de que se realizó el pedido se debe enviar este correo electrónico de recordatorio en particular.
    -   **Efecto de cambiar este ajuste:** Controla el momento del recordatorio.
    -   **Valor recomendado:** Comience con 1 o 2 días para el primer recordatorio.
    -   **Escenario / ejemplo de comerciante:** Establezca "1" para un primer recordatorio 24 horas después del pedido. Establezca "3" para un segundo recordatorio 3 días después del pedido.
-   **Asunto del correo electrónico:**

    -   **Qué hace este ajuste:** La línea de asunto del correo electrónico de recordatorio.
    -   **Efecto de cambiar este ajuste:** Esto es lo que los clientes ven en su bandeja de entrada. Un asunto claro y conciso aumenta las tasas de apertura.
    -   **Valor recomendado:** Algo como "Recordatorio: Su pedido impagado en [Nombre de la tienda]" o "Acción requerida: Complete su pedido #[ID de pedido]".
    -   **Escenario / ejemplo de comerciante:** "¡No olvide su pedido de MyPresta.eu!"
-   **Contenido del correo electrónico:**

    -   **Qué hace este ajuste:** El cuerpo principal del correo electrónico de recordatorio. Puede usar variables (como `{customer_name}`, `{order_id}`, `{shop_name}`) para personalizar el mensaje.
    -   **Efecto de cambiar este ajuste:** Este es el mensaje central para su cliente. Un tono amigable y útil es lo mejor.
    -   **Valor recomendado:** Incluya un saludo, mencione el pedido impagado, proporcione instrucciones sobre cómo pagar o dónde encontrar los detalles de pago, y ofrezca ayuda.
    -   **Escenario / ejemplo de comerciante:** "Estimado/a {customer\_name}, Este es un amable recordatorio sobre su reciente pedido #{order\_id} en {shop\_name}. Parece que el pago de este pedido aún está pendiente. Por favor, complete su pago lo antes posible para asegurar que su pedido sea procesado. Puede ver los detalles de su pedido aquí: [Enlace al historial de pedidos]. Si tiene alguna pregunta, contáctenos."
-   **Activo:**

    -   **Qué hace este ajuste:** Habilita o deshabilita esta regla de recordatorio específica.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Este recordatorio se enviará según su programación.
        -   *Cuando está deshabilitado:* Este recordatorio no se enviará, incluso si el módulo está activo.
    -   **Valor recomendado:** SÍ para reglas activas.
    -   **Escenario / ejemplo de comerciante:** Podría deshabilitar una regla si está probando contenido nuevo o desea pausar temporalmente un recordatorio específico.

### 2.2 Gestión de recordatorios de pedidos (Back Office > Módulos > Recordatorio de pedidos impagados > Recordatorios de pedidos)

Esta pantalla dedicada, accesible a través del menú del módulo en el Back Office, le permite ver y gestionar los pedidos que actualmente son elegibles para recordatorios.

-   **Nombre de la pantalla y ubicación del menú:** **Recordatorios de pedidos** (bajo el elemento de menú "Recordatorio de pedidos impagados").
-   **Acciones y ajustes disponibles:** Esta pantalla muestra una lista de pedidos que actualmente coinciden con sus criterios de "Estados de pedido para recordar".
    -   **Vista de cuadrícula / gestión:** Verá una tabla con columnas como ID de pedido, Nombre del cliente, Fecha del pedido, Estado actual y, potencialmente, la fecha del próximo recordatorio.
    -   **Acciones:** Podría tener acciones para enviar manualmente un recordatorio para un pedido específico, o para excluir un pedido de futuros recordatorios.
-   **Efecto de los cambios:**
    -   **Envío manual de un recordatorio:** Envía inmediatamente el siguiente correo electrónico de recordatorio programado para ese pedido.
    -   **Excluir un pedido:** Evita que el módulo envíe más recordatorios para ese pedido específico, incluso si su estado aún coincide con los criterios de recordatorio.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise periódicamente esta lista para obtener una visión general de los pedidos impagados pendientes. Utilice la opción de envío manual si un cliente llama y desea enviarle inmediatamente los detalles de pago de nuevo. Excluya pedidos si ha llegado a un acuerdo especial con un cliente o si un pedido es problemático.

### 2.3 Historial de recordatorios de pedidos (Back Office > Módulos > Recordatorio de pedidos impagados > Historial)

Esta pantalla proporciona un registro de todos los correos electrónicos de recordatorio que han sido enviados por el módulo.

-   **Nombre de la pantalla y ubicación del menú:** **Historial** (bajo el elemento de menú "Recordatorio de pedidos impagados").
-   **Acciones y ajustes disponibles:** Esta pantalla muestra una tabla con detalles sobre cada recordatorio enviado:
    -   Las columnas suelen incluir: ID de pedido, Nombre del cliente, Dirección de correo electrónico, Regla de recordatorio (qué regla lo activó), Fecha de envío y, potencialmente, el asunto del correo electrónico.
-   **Efecto de los cambios:** Este es un registro de solo lectura. No se realizan cambios directos aquí, pero proporciona información valiosa.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esta pantalla para verificar que los recordatorios se están enviando correctamente. Si un cliente afirma que no recibió un recordatorio, puede consultar este historial para confirmar si fue enviado.

### 2.4 Clientes dados de baja (Back Office > Módulos > Recordatorio de pedidos impagados > Clientes dados de baja)

Esta pantalla enumera a los clientes que han optado por no recibir recordatorios de pedidos impagados.

-   **Nombre de la pantalla y ubicación del menú:** **Clientes dados de baja** (bajo el elemento de menú "Recordatorio de pedidos impagados").
-   **Acciones y ajustes disponibles:** Esta pantalla muestra una tabla con:
    -   Las columnas suelen incluir: ID de cliente, Nombre del cliente, Dirección de correo electrónico y Fecha de baja.
    -   **Acciones:** Podría tener una opción para eliminar manualmente a un cliente de esta lista, re-suscribiéndolo efectivamente a los recordatorios (use con precaución y solo si lo solicita el cliente).
-   **Efecto de los cambios:**
    -   **Eliminar de la lista:** El cliente volverá a ser elegible para recibir recordatorios si el estado de su pedido coincide.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Supervise esta lista para comprender las preferencias del cliente. Solo vuelva a suscribir a un cliente si lo solicita explícitamente.

### 2.5 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | Habilitar módulo | SÍ | Activa/desactiva la funcionalidad del módulo. |
| | URL del Cron Job | Copiar y configurar | Esencial para el envío automático de recordatorios. |
| | Enlace para darse de baja en el correo electrónico | SÍ | Permite a los clientes darse de baja, mejora la reputación del remitente. |
| | Estados de pedido para recordar | Esperando transferencia bancaria, Esperando cheque, etc. | Define qué estados de pedido activan los recordatorios. |
| | Estados de pedido para detener recordatorios | Pago aceptado, Cancelado, etc. | Evita recordatorios para pedidos pagados o inválidos. |
| | **Reglas de recordatorio** | | |
| | Días después de la creación del pedido | 1, 3, 7 (ejemplo) | Establece el momento para cada correo electrónico de recordatorio. |
| | Asunto del correo electrónico | "Recordatorio: Su pedido impagado..." | Línea de asunto del correo electrónico de recordatorio. |
| | Contenido del correo electrónico | Mensaje personalizado con variables | Cuerpo del correo electrónico de recordatorio. |
| | Activo (para cada regla) | SÍ | Habilita/deshabilita reglas de recordatorio individuales. |
| **Recordatorios de pedidos** | (Lista de pedidos elegibles) | N/A | Resumen de pedidos pendientes de pago. |
| | Enviar recordatorio manual | N/A | Envía inmediatamente el siguiente recordatorio para el pedido seleccionado. |
| | Excluir pedido | N/A | Evita futuros recordatorios para el pedido seleccionado. |
| **Historial** | (Registro de recordatorios enviados) | N/A | Registro de auditoría de todos los correos electrónicos de recordatorio enviados. |
| **Clientes dados de baja** | (Lista de clientes dados de baja) | N/A | Muestra los clientes que optaron por no recibir recordatorios. |
| | Eliminar de la lista de baja | N/A | Vuelve a suscribir al cliente a los recordatorios (usar con precaución). |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis recordatorios no se envían. ¿Qué debo verificar primero?**
**R1:**

-   **Módulo habilitado:** Vaya a **Módulos > Gestor de módulos > Recordatorio de pedidos impagados** y asegúrese de que la configuración "Habilitar módulo" esté en SÍ.
-   **Cron Job:** El problema más común. *Debe* configurar el cron job en su servidor de alojamiento. Copie la "URL del Cron Job" de la página de configuración del módulo y agréguela al gestor de cron jobs de su panel de control de alojamiento. Asegúrese de que esté configurado para ejecutarse con frecuencia (por ejemplo, cada hora). Si no está seguro de cómo hacerlo, póngase en contacto con su proveedor de alojamiento.
-   **Estados de pedido:** Verifique "Estados de pedido para recordar" y "Estados de pedido para detener recordatorios" en la configuración del módulo. Asegúrese de que los pedidos para los que espera recordatorios tengan un estado seleccionado en la lista "para recordar" y no hayan alcanzado un estado en la lista "para detener".
-   **Reglas de recordatorio activas:** Asegúrese de que las reglas de recordatorio individuales que ha creado estén marcadas como "Activas".

**P2: Los clientes reciben demasiados recordatorios, o recordatorios después de haber pagado. ¿Cómo lo soluciono?**
**R2:**

-   **"Estados de pedido para detener recordatorios":** Esto es crucial. Asegúrese de que todos los estados que indican un pedido pagado o completado (por ejemplo, "Pago aceptado", "Enviado", "Cancelado", "Reembolsado") estén seleccionados en esta configuración. Esto le indica al módulo que deje de enviar recordatorios una vez que el pedido alcanza uno de estos estados.
-   **Tiempo de la regla de recordatorio:** Revise los "Días después de la creación del pedido" para cada regla de recordatorio. Asegúrese de que estén espaciados adecuadamente y no se superpongan de manera que envíen demasiados correos electrónicos demasiado rápido.

**P3: ¿Puedo personalizar las plantillas de correo electrónico?**
**R3:** Sí, el módulo le permite personalizar el asunto y el contenido del correo electrónico directamente dentro de la configuración de la regla de recordatorio. Puede usar variables específicas (como `{customer_name}`, `{order_id}`, `{shop_name}`) para personalizar el mensaje. Para una personalización visual más avanzada, un desarrollador necesitaría modificar los archivos de plantilla de correo electrónico subyacentes (ubicados en `mails/` dentro de su instalación de PrestaShop, utilizando la estructura de plantilla del módulo como guía).

**P4: El enlace para darse de baja no funciona, o los clientes siguen recibiendo correos electrónicos después de darse de baja.**
**R4:**

-   **Enlace para darse de baja habilitado:** Asegúrese de que "Enlace para darse de baja en el correo electrónico" esté configurado en SÍ en la configuración principal del módulo.
-   **Verificar la lista de "Clientes dados de baja":** Vaya a **Módulos > Recordatorio de pedidos impagados > Clientes dados de baja**. Verifique que la dirección de correo electrónico del cliente aparezca en esta lista. Si no es así, es posible que no se hayan dado de baja correctamente.
-   **Caché:** Borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**) después de realizar cualquier cambio de configuración.

**P5: ¿Qué sucede si un cliente tiene varios pedidos impagados?**
**R5:** El módulo tratará cada pedido impagado individualmente. Si un cliente tiene dos pedidos impagados separados, recibirá recordatorios para cada pedido de acuerdo con sus reglas definidas, siempre que esos pedidos cumplan los criterios.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Recordatorio de pedidos impagados", destinada a desarrolladores y webmasters.

### 4.1 Resumen de la arquitectura

El módulo "Recordatorio de pedidos impagados" (`oreminders`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando los principios MVC. Se centra principalmente en la administración del back-office para la configuración y un cron job del front-office para el procesamiento automatizado. Extiende `Module` para su funcionalidad principal y utiliza clases `AdminController` personalizadas para gestionar recordatorios, historial y clientes dados de baja. La creación de plantillas de correo electrónico se gestiona a través de un gestor personalizado, y la configuración se almacena en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

-   `controllers/front/CronJob.php`
    -   **Nombre de la clase y clase padre:** `OremindersCronJobModuleFrontController` extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este controlador está diseñado para ser llamado por un cron job del lado del servidor. Es el punto de entrada para la lógica automatizada del módulo. Cuando se ejecuta, itera a través de los pedidos impagados, verifica las reglas de recordatorio definidas y envía correos electrónicos de recordatorio. Normalmente devuelve un mensaje simple de éxito/fallo o una salida de registro.
-   `controllers/front/index.php`
    -   **Nombre de la clase y clase padre:** `OremindersIndexModuleFrontController` extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este es probablemente un marcador de posición o un controlador de respaldo. En muchos módulos, `index.php` en `controllers/front` sirve como un punto de entrada predeterminado o simple si no se solicita ninguna acción específica. Podría manejar la visualización básica del módulo o la redirección si el módulo tuviera una presencia en el front-office. Dada la naturaleza del módulo, su interacción principal en el front-office es a través de `CronJob.php`.

#### Controladores de administración del Back-Office

-   `controllers/admin/AdminOrderReminders.php`
    -   **Nombre de la clase y clase padre:** `AdminOrderRemindersController` extiende `ModuleAdminController`.
    -   **Nombre de la pestaña y entidad gestionada:** Gestiona la lista de "Recordatorios de pedidos". Este controlador es responsable de mostrar una lista de pedidos que actualmente son elegibles para recordatorios según la configuración del módulo. Proporciona acciones para enviar recordatorios manualmente o excluir pedidos específicos.
-   `controllers/admin/AdminOrderRemindersHistory.php`
    -   **Nombre de la clase y clase padre:** `AdminOrderRemindersHistoryController` extiende `ModuleAdminController`.
    -   **Nombre de la pestaña y entidad gestionada:** Gestiona el registro de "Historial". Este controlador muestra una lista de solo lectura de todos los correos electrónicos de recordatorio que han sido enviados con éxito por el módulo, incluyendo detalles como el ID del pedido, el cliente y la fecha de envío.
-   `controllers/admin/AdminOrderRemindersUnsub.php`
    -   **Nombre de la clase y clase padre:** `AdminOrderRemindersUnsubController` extiende `ModuleAdminController`.
    -   **Nombre de la pestaña y entidad gestionada:** Gestiona la lista de "Clientes dados de baja". Este controlador muestra a los clientes que han optado por no recibir recordatorios y permite su re-suscripción (si es necesario).
-   `controllers/admin/index.php`
    -   **Nombre de la clase y clase padre:** `AdminOremindersIndexController` extiende `ModuleAdminController`.
    -   **Nombre de la pestaña y entidad gestionada:** Similar al `index.php` del front-office, este podría servir como un controlador de administración predeterminado o de respaldo. Potencialmente podría manejar la configuración principal del módulo si `getContent()` en el archivo principal del módulo redirige a él, o si se utiliza para una acción de administración específica y simple.

### 4.3 Clases y modelos principales (`classes/`)

El inventario proporcionado no indica clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo podría estar utilizando `ObjectModel` directamente dentro de su archivo principal del módulo o controladores de administración, o está gestionando datos a través de consultas directas a la base de datos o extendiendo modelos principales existentes de PrestaShop (por ejemplo, `Order`, `Customer`).

Si se almacenan datos personalizados, es probable que se gestionen a través de `ps_configuration` para la configuración y, potencialmente, tablas de base de datos personalizadas creadas durante la instalación (aunque no se enumeraron archivos SQL, por lo que la creación de tablas estaría en línea en `install()`).

### 4.4 Activos de JavaScript (`views/js/`)

-   `oreminders/lib/emailTemplatesManager/js/emailTemplatesManager.js`
    -   **Alcance:** Back-office.
    -   **Detalles:** Este script probablemente proporciona funcionalidad dinámica para la interfaz de gestión de plantillas de correo electrónico dentro de la configuración del módulo. Esto podría incluir:
        -   Añadir/eliminar reglas de recordatorio dinámicamente.
        -   Manejar solicitudes AJAX para guardar/cargar plantillas de correo electrónico.
        -   Implementar un editor de texto enriquecido (por ejemplo, integración de TinyMCE) para el contenido del correo electrónico.
        -   Gestionar la inserción de variables en las plantillas de correo electrónico.
        -   Validación del lado del cliente para los campos del formulario relacionados con las reglas de correo electrónico.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `oreminders/lib/emailTemplatesManager/css/emailTemplatesManager.css`
    -   **Alcance:** Estilo del formulario de administración del Back-office.
    -   **Detalles:** Esta hoja de estilo proporciona un estilo específico para la interfaz del gestor de plantillas de correo electrónico en la configuración del Back Office del módulo. Definiría estilos para:
        -   Diseño de los formularios de reglas de recordatorio.
        -   Estilo de los campos de entrada, botones y áreas de texto dentro del editor de plantillas.
        -   Asegurar una apariencia y sensación consistentes con el tema del Back Office de PrestaShop.
    -   **Selectores de clase CSS clave que los desarrolladores pueden anular:** Busque clases específicas con el prefijo `oreminders-` o `email-templates-manager-` dentro de las plantillas de administración del módulo para identificar elementos personalizables.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de gancho (`views/templates/hook/`)

-   `oreminders/views/templates/hook/form.tpl`
    -   **Gancho:** Potencialmente `displayAdminModuleConfigure` o similar, si se usa para un pequeño formulario dentro de un contexto de gancho. Más probablemente, es una plantilla de formulario genérica utilizada internamente.
    -   **Salida:** Renderiza una estructura de formulario genérica.
-   `oreminders/views/templates/hook/header.tpl`
    -   **Gancho:** `displayHeader` (Front-office).
    -   **Salida:** Se utiliza para incluir archivos CSS o JavaScript necesarios en la sección `<head>` del front-office, si el módulo tuviera algún componente de front-end (por ejemplo, para la página de darse de baja).
-   `oreminders/views/templates/hook/identity.tpl`
    -   **Gancho:** No está claro por el nombre, pero `displayCustomerAccount` o similar para mostrar información específica del cliente, o quizás relacionado con el proceso de darse de baja.
    -   **Salida:** Podría renderizar un mensaje o un formulario relacionado con la identidad o las preferencias del cliente.

#### Plantillas de administración (`views/templates/admin/`)

-   `oreminders/lib/emailTemplatesManager/views/buttonManager.tpl`
    -   **Contexto:** Utilizado dentro del gestor de plantillas de correo electrónico.
    -   **Salida:** Renderiza botones para gestionar plantillas de correo electrónico (por ejemplo, "Añadir nueva regla", "Guardar", "Eliminar").
-   `oreminders/lib/emailTemplatesManager/views/createTemplateForm.tpl`
    -   **Contexto:** Utilizado dentro del gestor de plantillas de correo electrónico.
    -   **Salida:** Renderiza el formulario para crear una nueva plantilla/regla de correo electrónico de recordatorio.
-   `oreminders/lib/emailTemplatesManager/views/editTemplateForm.tpl`
    -   **Contexto:** Utilizado dentro del gestor de plantillas de correo electrónico.
    -   **Salida:** Renderiza el formulario para editar una plantilla/regla de correo electrónico de recordatorio existente.
-   `oreminders/lib/emailTemplatesManager/views/mainForm.tpl`
    -   **Contexto:** Utilizado dentro del gestor de plantillas de correo electrónico.
    -   **Salida:** La plantilla principal de envoltura para la interfaz de gestión de plantillas de correo electrónico, probablemente combinando `buttonManager`, `createTemplateForm` y `editTemplateForm`.
-   `oreminders/lib/emailTemplatesManager/views/selectInput.tpl`
    -   **Contexto:** Utilizado dentro del gestor de plantillas de correo electrónico.
    -   **Salida:** Una plantilla reutilizable para renderizar una entrada de lista desplegable `<select>`, probablemente para elegir estados de pedido u otras opciones.
-   `oreminders/views/templates/admin/order_reminders/helpers/form/form.tpl`
    -   **Contexto:** Utilizado por `AdminOrderRemindersController` para sus vistas de formulario (por ejemplo, si hay un formulario de añadir/editar para una entrada de recordatorio de pedido, aunque es principalmente un controlador de lista).
    -   **Salida:** Renderiza un formulario de administración estándar de PrestaShop.
-   `oreminders/views/templates/admin/order_reminders/helpers/list/list_action_email.tpl`
    -   **Contexto:** Utilizado por `AdminOrderRemindersController` en su vista de lista.
    -   **Salida:** Renderiza un botón de acción o enlace específico dentro de la lista de recordatorios de pedidos, probablemente para "Enviar correo electrónico" o "Ver correo electrónico".
-   `oreminders/views/templates/admin/script.tpl`
    -   **Contexto:** Back Office de administración.
    -   **Salida:** Probablemente incluye código JavaScript en línea o variables de configuración necesarias para la interfaz del Back Office, posiblemente para llamadas AJAX o elementos de UI dinámicos.

### 4.7 Esquema de la base de datos y mapa de ganchos

#### Tablas de la base de datos

La descripción del módulo y el inventario de archivos no enumeran explícitamente archivos SQL para la creación de tablas personalizadas. Sin embargo, basándose en los controladores de administración, el módulo probablemente interactúa con lo siguiente (ya sean tablas personalizadas o `ps_configuration` para la configuración):

-   `ps_configuration`: Almacena todas las configuraciones del módulo (por ejemplo, `OREMINDERS_ENABLED`, `OREMINDERS_CRON_URL`, `OREMINDERS_UNSUB_LINK`, `OREMINDERS_STATUSES_REMIND`, `OREMINDERS_STATUSES_STOP`, y datos serializados para reglas de recordatorio individuales).
-   `ps_or` (o similar, gestionado por `AdminOrderRemindersController`): Probablemente una tabla personalizada para almacenar información sobre los pedidos que se están recordando actualmente, o para marcar pedidos como excluidos.
-   `ps_or_history` (o similar, gestionado por `AdminOrderRemindersHistoryController`): Una tabla personalizada para registrar cada correo electrónico de recordatorio enviado, incluyendo `id_order`, `id_customer`, `email`, `id_reminder_rule`, `date_sent`.
-   `ps_or_ounsub` (o similar, gestionado por `AdminOrderRemindersUnsubController`): Una tabla personalizada para almacenar los ID de cliente o las direcciones de correo electrónico de aquellos que se han dado de baja de los recordatorios.

#### Tabla de ganchos registrados

| Nombre del gancho | Alcance | Momento de ejecución | Propósito técnico |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | En la sección `<head>` de todas las páginas del front-office. | Para incluir CSS/JS específicos del módulo para componentes del front-office (por ejemplo, página de darse de baja). |
| `displayAdminModuleConfigure` | Back-Office | Al ver la página de configuración principal del módulo. | Para renderizar el formulario de configuración principal del módulo (método `getContent()`). |
| `actionValidateOrder` | Back-Office | Después de que un pedido ha sido validado con éxito. | Potencialmente utilizado para inicializar el seguimiento de recordatorios para nuevos pedidos, aunque el cron job es el disparador principal. |
| `actionOrderStatusUpdate` | Back-Office | Cuando se cambia el estado de un pedido. | Para verificar si el nuevo estado de un pedido debe detener los recordatorios (por ejemplo, si pasa a ser "Pago aceptado"). |
| `actionCronJob` | Back-Office (a través del controlador frontal) | Ejecutado por el cron job del servidor. | El gancho principal que activa la lógica del módulo para encontrar pedidos impagados y enviar recordatorios. |
| (Ganchos implícitos para pestañas de administración) | Back-Office | Al renderizar el menú del Back Office. | Para añadir los elementos de menú personalizados del módulo (Recordatorios de pedidos, Historial, Clientes dados de baja). |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Recordatorio de pedidos impagados", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y configuración del módulo.

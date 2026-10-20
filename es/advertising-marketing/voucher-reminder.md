---
title: "Recordatorio de Vales - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Recordatorio de Vales' de MyPresta.eu."
sidebar:
  label: "Recordatorio de Vales - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Voucher Reminder en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-reminder.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/voucher-reminder/)
>
> ---


# Recordatorio de Vales

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. El acceso para configurar una tarea cron en tu servidor es esencial para el funcionamiento automático del módulo.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, la primera pantalla que verás es la página de configuración principal del módulo Recordatorio de Vales. Esta página es crucial para configurar la funcionalidad principal.

**URL de la Tarea Cron:**

- **Qué hace este ajuste:** Muestra una URL única que la tarea cron de tu servidor necesita llamar periódicamente. Esta URL activa el módulo para que compruebe los vales próximos a caducar y envíe recordatorios.
- **Efecto de cambiar este ajuste:** No puedes cambiar esta URL directamente. Es generada por el módulo. Si la tarea cron no está configurada correctamente en tu servidor para llamar a esta URL, el módulo no enviará ningún recordatorio automáticamente.
- **Valor recomendado:** Copia esta URL exactamente y úsala para configurar una tarea cron en tu servidor de alojamiento.
- **Escenario / ejemplo de comerciante:** Has creado varias reglas de recordatorio, pero no se envían correos electrónicos. Lo primero que debes verificar es si has configurado correctamente la tarea cron en tu servidor usando esta URL.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 Gestión de Recordatorios de Vales (Back Office > Módulos > Recordatorio de Vales > Recordatorios de Vales)

Aquí es donde defines y gestionas las reglas de recordatorio reales. Cada regla especifica cuándo se debe enviar un recordatorio y qué plantilla de correo electrónico debe usar.

- **Nombre de la Pantalla y Ubicación del Menú:** **Recordatorios de Vales** (en **Módulos > Recordatorio de Vales** en el menú principal de PrestaShop).
- **Acciones y Ajustes Disponibles:**
  - **Lista de Recordatorios:** Verás una tabla que enumera todas tus reglas de recordatorio definidas.
  - **Añadir Nuevo Recordatorio:** Haz clic en el botón "Añadir nuevo" para crear una nueva regla de recordatorio.
    - **Recordar (horas antes de la caducidad):**
      - **Qué hace este ajuste:** Este es el ajuste más crítico para una regla de recordatorio. Determina cuántas horas *antes* de la fecha de caducidad de un vale se debe enviar el correo electrónico de recordatorio.
      - **Efecto de cambiar este ajuste:**
        - *Establecido en 24:* Se enviará un correo electrónico de recordatorio exactamente 24 horas antes de que caduque el vale.
        - *Establecido en 72:* Se enviará un correo electrónico de recordatorio 3 días (72 horas) antes de la caducidad.
      - **Valor recomendado:** Esto depende de tu estrategia. Los valores comunes son 24, 48, 72 horas, o incluso 168 horas (1 semana).
      - **Escenario / ejemplo de comerciante:** Quieres dar a los clientes un último empujón un día antes de que caduque su vale. Establecerías esto en `24`. Si quieres darles un aviso de una semana, lo establecerías en `168`.
    - **Título:**
      - **Qué hace este ajuste:** Un nombre descriptivo para tu regla de recordatorio, visible solo en el Back Office. Esto te ayuda a identificar diferentes reglas de recordatorio.
      - **Efecto de cambiar este ajuste:** Cambia la etiqueta de esta regla en tu panel de administración. No tiene impacto en el front office.
      - **Valor recomendado:** Algo claro y descriptivo, por ejemplo, "24 Horas Antes de la Caducidad", "Semana Antes de que Caduca el Vale".
      - **Escenario / ejemplo de comerciante:** Tienes varios recordatorios. Nombrarlos "Recordatorio de 1 día" y "Recordatorio de 3 días" facilita la gestión.
    - **Título del correo electrónico:**
      - **Qué hace este ajuste:** Esta es la línea de asunto del correo electrónico que recibirán tus clientes.
      - **Efecto de cambiar este ajuste:** Cambia directamente la línea de asunto de los correos electrónicos de recordatorio.
      - **Valor recomendado:** Algo atractivo y claro, por ejemplo, "¡Tu [Código de Vale] está a punto de caducar!", "¡No te pierdas tu descuento!".
      - **Escenario / ejemplo de comerciante:** Quieres que el correo electrónico destaque en la bandeja de entrada del cliente. Un asunto como "Última Oportunidad: ¡Tu Descuento Caduca Pronto!" es más efectivo que uno genérico.
    - **Archivo de plantilla de correo electrónico:**
      - **Qué hace este ajuste:** Especifica qué archivo de plantilla de correo electrónico (por ejemplo, `voucher_reminder.html` y `voucher_reminder.txt`) debe usar el módulo para este recordatorio específico. Esto te permite tener diferentes diseños de correo electrónico para diferentes momentos de recordatorio.
      - **Efecto de cambiar este ajuste:** Determina el contenido y el diseño del correo electrónico enviado. Si creas una plantilla personalizada, seleccionarías su nombre aquí.
      - **Valor recomendado:** Usa la plantilla predeterminada a menos que tengas necesidades de diseño específicas. Si creas plantillas personalizadas, asegúrate de que estén correctamente ubicadas en el directorio `mails` de tu tema.
      - **Escenario / ejemplo de comerciante:** Quieres un correo electrónico de recordatorio suave con una semana de antelación, y un correo electrónico más urgente de "última oportunidad" con 24 horas de antelación. Crearías dos plantillas de correo electrónico diferentes y las asignarías a sus respectivas reglas de recordatorio.
    - **Enviar recordatorio:**
      - **Qué hace este ajuste:** Un simple interruptor ON/OFF para habilitar o deshabilitar esta regla de recordatorio específica.
      - **Efecto de cambiar este ajuste:**
        - *Habilitado (Sí):* El módulo enviará correos electrónicos según esta regla.
        - *Deshabilitado (No):* Esta regla será ignorada y no se enviarán correos electrónicos para ella.
      - **Valor recomendado:** "Sí" una vez que hayas configurado la regla y estés listo para usarla.
      - **Escenario / ejemplo de comerciante:** Estás probando una nueva regla de recordatorio y quieres asegurarte de que sea perfecta antes de activarla para todos los clientes. La mantendrías deshabilitada durante las pruebas.
  - **Botón Guardar:** Aplica todos los cambios realizados en la regla de recordatorio.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Comienza creando una o dos reglas de recordatorio (por ejemplo, 72 horas y 24 horas antes de la caducidad).
  2. Usa títulos claros y asuntos de correo electrónico atractivos.
  3. Monitorea el "Historial de Recordatorios de Vales" para ver si los correos electrónicos se envían como se espera.
  4. Considera crear plantillas de correo electrónico personalizadas para diferentes momentos de recordatorio para adaptar tu mensaje.

#### 2.2.2 Historial de Recordatorios de Vales (Back Office > Módulos > Recordatorio de Vales > Historial)

Esta pantalla proporciona un registro de todos los correos electrónicos de recordatorio que han sido enviados con éxito por el módulo.

- **Nombre de la Pantalla y Ubicación del Menú:** **Historial** (en **Módulos > Recordatorio de Vales** en el menú principal de PrestaShop).
- **Acciones y Ajustes Disponibles:**
  - **Lista de Recordatorios Enviados:** Una tabla que muestra:
    - **ID:** Identificador único para la entrada del historial.
    - **Fecha de entrega del correo electrónico:** Cuándo se envió el correo electrónico.
    - **Recordatorio:** Qué regla de recordatorio (por título) activó este correo electrónico.
    - **Cliente:** El cliente que recibió el recordatorio.
    - **Vale:** El código de vale específico sobre el que se recordó.
- **Efecto de los cambios:** Este es un registro de solo lectura. No puedes realizar cambios aquí, pero es invaluable para verificar el funcionamiento del módulo.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revisa regularmente este historial para asegurarte de que los recordatorios se envían como se espera. Si notas lagunas o un comportamiento inesperado, este registro es tu primer punto de referencia para la resolución de problemas.

#### 2.2.3 Bajas (Back Office > Módulos > Recordatorio de Vales > Bajas)

Esta pantalla enumera los clientes que han optado por no recibir recordatorios de vales.

- **Nombre de la Pantalla y Ubicación del Menú:** **Bajas** (en **Módulos > Recordatorio de Vales** en el menú principal de PrestaShop).
- **Acciones y Ajustes Disponibles:**
  - **Lista de Clientes Dados de Baja:** Una tabla que muestra:
    - **ID:** Identificador único para la entrada de baja.
    - **Correo electrónico:** La dirección de correo electrónico del cliente que se dio de baja.
    - **IP:** La dirección IP desde la que se produjo la baja.
    - **Fecha de baja:** Cuándo se dio de baja el cliente.
  - **Añadir Nueva Baja:** Puedes añadir manualmente una dirección de correo electrónico a la lista de bajas.
    - **Correo electrónico del cliente:** Introduce la dirección de correo electrónico que deseas dar de baja.
    - **IP:** (Opcional) La dirección IP asociada con la baja.
    - **Fecha:** (Opcional) La fecha de baja.
    - **Botón Guardar:** Añade el cliente a la lista de bajas.
- **Efecto de los cambios:** Los clientes que aparecen aquí ya no recibirán correos electrónicos de recordatorio de vales de tu tienda, incluso si tienen vales próximos a caducar. Añadir manualmente un correo electrónico asegura que se les dé de baja.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Si bien los clientes pueden darse de baja ellos mismos, esta pantalla te permite añadir manualmente clientes si se ponen en contacto contigo directamente solicitando ser eliminados de las listas de recordatorios. También es un buen lugar para monitorear las tendencias de baja.

#### 2.2.4 index.php (vreminders/controllers/admin/index.php)

Este archivo es típicamente un marcador de posición o una redirección dentro de la estructura de administración de PrestaShop y no representa una pantalla directa y configurable para el comerciante. Su propósito suele ser asegurar que el acceso directo al directorio esté restringido o para redirigir a la configuración principal del módulo.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | URL de la Tarea Cron | (URL Generada) | Esencial para configurar la automatización del lado del servidor para enviar recordatorios. |
| **Recordatorios de Vales** | Recordar (horas antes de la caducidad) | Varía (ej., 24, 72) | Define el momento del correo electrónico de recordatorio en relación con la caducidad del vale. |
| | Título | Descriptivo (ej., "Recordatorio de 1 Día") | Etiqueta interna para identificar las reglas de recordatorio en el Back Office. |
| | Título del correo electrónico | Línea de asunto atractiva | La línea de asunto del correo electrónico que reciben los clientes. |
| | Archivo de plantilla de correo electrónico | `voucher_reminder` | Especifica la plantilla de correo electrónico utilizada para este recordatorio. |
| | Enviar recordatorio | Sí | Activa o desactiva una regla de recordatorio específica. |
| **Historial de Recordatorios de Vales** | (Todos los campos) | N/A (Solo lectura) | Registro de todos los correos electrónicos de recordatorio enviados para verificación y resolución de problemas. |
| **Bajas** | Correo electrónico del cliente | N/A | Añade manualmente correos electrónicos de clientes para evitar que reciban recordatorios. |
| | IP | N/A | (Opcional) Dirección IP asociada con la baja. |
| | Fecha | N/A | (Opcional) Fecha de baja. |

## 3. Resolución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Mis recordatorios no se envían. ¿Qué debo verificar primero?**
R: La razón más común es una tarea cron configurada incorrectamente.

1. Ve a **Módulos > Recordatorio de Vales > Configurar**.
2. Copia la "URL de la Tarea Cron" exactamente.
3. Inicia sesión en el panel de control de tu alojamiento (cPanel, Plesk, etc.) y navega a la sección "Tareas Cron".
4. Crea una nueva tarea cron que llame a esta URL cada 5-15 minutos. El comando suele ser algo como `wget -q -O /dev/null "TU_URL_DE_TAREA_CRON_AQUI"` o `curl -s "TU_URL_DE_TAREA_CRON_AQUI" > /dev/null`.
5. Además, asegúrate de que las reglas de recordatorio individuales estén habilitadas ("Enviar recordatorio" esté configurado en "Sí") en **Módulos > Recordatorio de Vales > Recordatorios de Vales**.

**P: Los clientes se quejan de que no reciben recordatorios, pero el historial muestra que se enviaron.**
R: Esto suele indicar problemas de entrega de correo electrónico.

1. **Revisa las Carpetas de Spam:** Aconseja a los clientes que revisen sus carpetas de spam o correo no deseado.
2. **Configuración del Servidor de Correo Electrónico:** Asegúrate de que la configuración de correo electrónico de tu tienda PrestaShop (en **Parámetros Avanzados > E-mail**) esté configurada correctamente y de que tu servidor no esté en una lista negra. Usar un servidor SMTP (como SendGrid, Mailgun, etc.) suele ser más fiable que la función `mail()` de PHP.
3. **Problemas con la Plantilla de Correo Electrónico:** Asegúrate de que tus plantillas de correo electrónico sean HTML/texto válidos y no contengan enlaces o imágenes rotos que puedan activar los filtros de spam.

**P: ¿Puedo personalizar las plantillas de correo electrónico?**
R: ¡Sí!

1. El módulo utiliza plantillas de correo electrónico estándar de PrestaShop. Puedes encontrar los archivos de plantilla predeterminados en `modules/vreminders/mails/en/` (o en la carpeta de tu idioma).
2. **Mejor Práctica:** Copia estos archivos al directorio `mails/en/` de tu tema activo (por ejemplo, `themes/yourtheme/mails/en/`). De esta manera, tus personalizaciones no se sobrescribirán cuando se actualice el módulo.
3. Edita los archivos `.html` y `.txt` para que coincidan con tu marca y mensaje. Puedes usar las variables Smarty disponibles en las plantillas de correo electrónico de PrestaShop.
4. Si creas archivos de plantilla completamente nuevos (por ejemplo, `my_custom_reminder.html`), deberás seleccionar `my_custom_reminder` en el ajuste "Archivo de plantilla de correo electrónico" para tu regla de recordatorio.

**P: ¿Cómo pruebo los recordatorios sin enviarlos a clientes reales?**
R:

1. Crea una cuenta de cliente de prueba en tu tienda.
2. Crea manualmente un código de vale para este cliente de prueba con una fecha de caducidad unas horas o días en el futuro.
3. Configura una regla de recordatorio con un "Recordar (horas antes de la caducidad)" corto (por ejemplo, 1 hora).
4. En lugar de esperar la tarea cron, puedes activar manualmente la URL cron en tu navegador (aunque esto no se recomienda para producción).
5. Revisa el "Historial de Recordatorios de Vales" y la bandeja de entrada del correo electrónico del cliente de prueba.
6. Una vez satisfecho, elimina el vale de prueba y la regla de recordatorio, y configura tus reglas de producción.

**P: ¿Qué sucede si un cliente usa su vale después de que se envía un recordatorio pero antes de que caduque?**
R: El módulo está diseñado para enviar recordatorios solo para vales *no utilizados*. Si un cliente usa su vale, ya no se considerará "activo" y "no utilizado", por lo que no se enviarán más recordatorios para ese vale específico.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Recordatorio de Vales" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando los principios MVC. Su funcionalidad principal gira en torno a una tarea cron que verifica periódicamente los vales próximos a caducar y envía correos electrónicos según las reglas configuradas. Utiliza `ObjectModel` de PrestaShop para gestionar sus entidades personalizadas (recordatorios, historial, bajas) y mecanismos de correo electrónico estándar para la comunicación. La lógica principal del módulo reside en `cronjob.php` (que actúa como la clase principal del módulo) y controladores de administración dedicados para las operaciones CRUD en sus datos personalizados.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `controllers/front/CronJob.php`
    - **Nombre de la clase y clase padre**: `VremindersCronJobModuleFrontController` extiende `ModuleFrontController`.
    - **Responsabilidad**: Este controlador es el punto de entrada para la tarea cron del módulo. Cuando se accede a la URL cron (generada en la configuración del módulo), se ejecuta este controlador. Contiene la lógica para obtener los vales próximos a caducar, verificar las reglas de recordatorio configuradas y enviar correos electrónicos. Normalmente no renderiza ninguna salida visual, sino que realiza el procesamiento en segundo plano.
  - `controllers/front/index.php`
    - **Nombre de la clase y clase padre**: No es una clase, típicamente un archivo vacío o un simple `die('No direct script access allowed')` para evitar la lista de directorios o el acceso directo.
- **Controladores de Administración (Back-Office)**:

  - `controllers/admin/AdminVoucherReminders.php`
    - **Nombre de la pestaña y entidad gestionada**: Gestiona la lista y los formularios de "Recordatorios de Vales" en el Back Office. Maneja las operaciones CRUD para la entidad `VoucherReminder` (que se asigna a la tabla `ps_vr`).
  - `controllers/admin/AdminVoucherRemindersHistory.php`
    - **Nombre de la pestaña y entidad gestionada**: Gestiona la lista de "Historial de Recordatorios de Vales" en el Back Office. Muestra un registro de solo lectura de los recordatorios enviados, asignándose a la entidad `VoucherReminderHistory` (que se asigna a la tabla `ps_vr_history`).
  - `controllers/admin/AdminVRemindersUnsub.php`
    - **Nombre de la pestaña y entidad gestionada**: Gestiona la lista y los formularios de "Bajas" en el Back Office. Maneja las operaciones CRUD para la entidad `VoucherReminderUnsub` (que se asigna a la tabla `ps_vr_vunsub`).
  - `controllers/admin/index.php`
    - **Nombre de la clase y clase padre**: No es una clase, típicamente un archivo vacío o un simple `die('No direct script access allowed')` para evitar la lista de directorios o el acceso directo.

### 4.3 Clases y Modelos Principales (`classes/`)

El dossier del módulo no indica un directorio `classes/` explícito. Esto implica que las clases `ObjectModel` principales probablemente se definen directamente dentro del archivo principal del módulo (`cronjob.php`) o dentro de los archivos de controlador de administración respectivos. Basándose en la estructura típica de los módulos de PrestaShop y las entidades identificadas, se espera que las siguientes clases `ObjectModel` estén presentes, probablemente definidas dentro de `cronjob.php` o `AdminVoucherReminders.php`, `AdminVoucherRemindersHistory.php`, `AdminVRemindersUnsub.php`:

- **`VoucherReminder` (o similar)**

  - **Tabla de base de datos**: `ps_vr` (o `_vreminders_vr`)
  - **Extiende `ObjectModel`**: Sí.
  - **Campos de `$definition`**: Los campos esperados incluyen `id_vr`, `remind_hours`, `title`, `email_title`, `email_template`, `active`.
  - **Métodos públicos clave**: Métodos para añadir, actualizar, eliminar reglas de recordatorio y, potencialmente, métodos para obtener reglas activas.
- **`VoucherReminderHistory` (o similar)**

  - **Tabla de base de datos**: `ps_vr_history` (o `_vreminders_vr_history`)
  - **Extiende `ObjectModel`**: Sí.
  - **Campos de `$definition`**: Los campos esperados incluyen `id_vr_history`, `id_vr`, `id_customer`, `id_cart_rule`, `date_add`.
  - **Métodos públicos clave**: Métodos para registrar los recordatorios enviados.
- **`VoucherReminderUnsub` (o similar)**

  - **Tabla de base de datos**: `ps_vr_vunsub` (o `_vreminders_vr_vunsub`)
  - **Extiende `ObjectModel`**: Sí.
  - **Campos de `$definition`**: Los campos esperados incluyen `id_vunsub`, `email`, `ip`, `date_add`.
  - **Métodos públicos clave**: Métodos para gestionar las bajas, incluyendo añadir y verificar correos electrónicos dados de baja.

### 4.4 Activos JavaScript (`views/js/`)

El dossier del módulo no indica archivos JavaScript. Esto sugiere que el módulo se basa completamente en las funcionalidades JavaScript principales de PrestaShop para sus formularios y listas del Back Office, o que cualquier JS mínimo está incrustado directamente en las plantillas.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El dossier del módulo no indica archivos CSS. Esto sugiere que el módulo se basa completamente en el CSS principal del Back Office de PrestaShop para sus interfaces de administración, y cualquier estilo de front-office (para correos electrónicos) se maneja dentro de las propias plantillas de correo electrónico.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:

  - `vreminders/views/templates/admin/order_reminders/helpers/form/form.tpl`
    - **Propósito**: Esta plantilla es probablemente utilizada por `AdminVoucherRemindersController` para renderizar el formulario de añadir/editar reglas de recordatorio de vales individuales. Contendría los campos de entrada para "Recordar (horas antes de la caducidad)", "Título", "Título del correo electrónico", "Archivo de plantilla de correo electrónico" y "Enviar recordatorio".
- **Plantillas de hook (`views/templates/hook/`)**:

  - `vreminders/views/templates/hook/form.tpl`
    - **Propósito**: Esta plantilla podría ser una plantilla de formulario genérica o una específica para un hook que muestra un formulario. Dada la naturaleza del módulo, es menos probable que sea un formulario visible en el front-office y más probable que sea un componente interno o un hook heredado. Sin más contexto, su ubicación exacta en el front-office no está clara, pero podría ser para un formulario de baja o similar.
  - `vreminders/views/templates/hook/header.tpl`
    - **Propósito**: Esta plantilla se renderiza en el hook `displayHeader`. Se utiliza típicamente para incluir archivos CSS o JavaScript, metaetiquetas u otros elementos que deben cargarse en la sección `<head>` del documento HTML. Para este módulo, podría usarse para incluir cualquier JS necesario para la tarea cron o para configurar metaetiquetas específicas, aunque el dossier no indica archivos JS/CSS. También podría ser un marcador de posición.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - `ps_vr` (o `_vreminders_vr`): Almacena la configuración de cada regla de recordatorio de vale.
    - `id_vr` (PK, INT)
    - `remind_hours` (INT)
    - `title` (VARCHAR)
    - `email_title` (VARCHAR)
    - `email_template` (VARCHAR)
    - `active` (TINYINT)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_vr_history` (o `_vreminders_vr_history`): Registra cada correo electrónico de recordatorio enviado.
    - `id_vr_history` (PK, INT)
    - `id_vr` (FK a `ps_vr.id_vr`, INT)
    - `id_customer` (FK a `ps_customer.id_customer`, INT)
    - `id_cart_rule` (FK a `ps_cart_rule.id_cart_rule`, INT)
    - `date_add` (DATETIME)
  - `ps_vr_vunsub` (o `_vreminders_vr_vunsub`): Almacena las direcciones de correo electrónico de los clientes que se han dado de baja de los recordatorios.
    - `id_vunsub` (PK, INT)
    - `email` (VARCHAR)
    - `ip` (VARCHAR)
    - `date_add` (DATETIME)
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Para incluir cualquier activo necesario (JS/CSS) o metaetiquetas para el módulo. |
| `actionModuleInstall` | Durante la instalación del módulo. | Para crear tablas de base de datos y configuración predeterminada. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Para eliminar tablas de base de datos y configuración. |
| `displayAdminProductsExtra` (o similar) | Potencialmente en las páginas de productos en el BO. | Si el módulo tuviera configuraciones de recordatorio específicas del producto, pero no indicado por el dossier. |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página del back-office. | Para incluir JS/CSS específico de administración o contexto para la configuración del módulo. |
| `moduleRoutes` | Durante la inicialización de la reescritura de URL. | Para definir URLs amigables personalizadas para los controladores frontales (por ejemplo, URL de la tarea cron, URL de baja). |

La lógica principal del módulo para enviar recordatorios se activa mediante el controlador frontal `CronJob.php`, que se llama a través de una tarea cron del lado del servidor, no directamente por un hook de PrestaShop.

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y asistencia adicional con tu módulo "Recordatorio de Vales", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a proporcionar un soporte integral y a garantizar que tu módulo funcione sin problemas.

---
title: "Recordatorio de puntos de fidelidad - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Recordatorio de puntos de fidelidad' de MyPresta.eu."
sidebar:
  label: "Recordatorio de puntos de fidelidad - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Loyalty points reminder en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-reminder.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/loyalty-points-reminder/)
>
> ---


# Recordatorio de puntos de fidelidad

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. El módulo se basa en las funciones de correo nativas de PrestaShop y en las capacidades de las tareas cron.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Recordatorio de puntos de fidelidad)

Esta es la pantalla de configuración principal y única para el módulo "Recordatorio de puntos de fidelidad". Aquí definirá cómo y cuándo se envían los correos electrónicos de recordatorio.

#### **Habilitar / Deshabilitar Módulo**

- **Qué hace este ajuste:** Este es el interruptor maestro para el módulo.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* El módulo buscará activamente los puntos de fidelidad a punto de caducar y enviará correos electrónicos de recordatorio según sus otras configuraciones.
  - *Cuando está deshabilitado:* El módulo no enviará ningún correo electrónico de recordatorio, independientemente de otras configuraciones.
- **Valor recomendado:** SÍ (una vez que haya configurado los otros ajustes).
- **Escenario / ejemplo del comerciante:** Acaba de instalar el módulo y quiere empezar a recordar a los clientes. Lo habilitaría después de configurar los días antes de la caducidad.

#### **Días antes de la caducidad para enviar recordatorio**

- **Qué hace este ajuste:** Esto determina cuántos días *antes* de que los puntos de fidelidad de un cliente caduquen se enviará el correo electrónico de recordatorio.
- **Efecto de cambiar este ajuste:**
  - *Si se establece en 7:* Los clientes recibirán un correo electrónico 7 días antes de que sus puntos caduquen.
  - *Si se establece en 30:* Los clientes recibirán un correo electrónico 30 días antes de que sus puntos caduquen.
- **Valor recomendado:** 7-14 días. Esto da a los clientes tiempo suficiente para reaccionar sin ser demasiado anticipado como para que lo olviden.
- **Escenario / ejemplo del comerciante:** Quiere dar a los clientes una semana para usar sus puntos. Lo establecería en "7". Si quiere darles más margen, quizás "14".

#### **URL de la tarea Cron**

- **Qué hace este ajuste:** Muestra una URL única que debe configurar como una tarea cron en su servidor. Una tarea cron es una tarea programada que le dice a su servidor que ejecute un script específico a intervalos regulares (por ejemplo, una vez al día). Así es como el módulo comprueba automáticamente los puntos a punto de caducar y envía correos electrónicos sin que usted tenga que hacer nada manualmente.
- **Efecto de cambiar este ajuste:** No puede cambiar este ajuste directamente. Es una URL generada.
  - *Si la tarea cron está configurada correctamente:* El módulo se ejecutará automáticamente, enviando correos electrónicos según lo configurado.
  - *Si la tarea cron NO está configurada:* El módulo nunca enviará ningún correo electrónico de recordatorio, incluso si está habilitado.
- **Valor recomendado:** Copie esta URL y configúrela como una tarea cron diaria en su servidor de alojamiento.
- **Escenario / ejemplo del comerciante:** Después de configurar el ajuste "Días antes de la caducidad", copiaría esta URL y la pegaría en el programador de tareas cron de su panel de control de alojamiento (por ejemplo, cPanel, Plesk o acceso directo al servidor). Normalmente lo configuraría para que se ejecute una vez cada 24 horas.

#### **Dirección de correo electrónico de prueba**

- **Qué hace este ajuste:** Le permite enviar un correo electrónico de recordatorio de prueba a una dirección específica para asegurarse de que el módulo funciona correctamente y el contenido del correo electrónico se ve bien.
- **Efecto de cambiar este ajuste:**
  - *Introducir un correo electrónico y hacer clic en "Enviar correo electrónico de prueba":* Se enviará un correo electrónico a la dirección especificada, simulando un recordatorio de puntos de fidelidad. Este correo electrónico contendrá datos de marcador de posición, ya que es una prueba.
- **Valor recomendado:** Utilice su propia dirección de correo electrónico o la de un colega para realizar pruebas.
- **Escenario / ejemplo del comerciante:** Antes de salir en vivo, quiere ver cómo se ve el correo electrónico de recordatorio. Introduciría su dirección de correo electrónico aquí y haría clic en el botón de prueba.

### 2.2 Tabla de referencia rápida de la configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | **Habilitar / Deshabilitar Módulo** | SÍ | Interruptor maestro para activar o desactivar los correos electrónicos de recordatorio. |
| Configuración del módulo | **Días antes de la caducidad para enviar recordatorio** | 7-14 días | Define cuántos días antes de que caduquen los puntos se envía el correo electrónico. |
| Configuración del módulo | **URL de la tarea Cron** | Copiar y configurar diariamente | Esencial para el envío automatizado de correos electrónicos; debe configurarse en su servidor. |
| Configuración del módulo | **Dirección de correo electrónico de prueba** | Su correo electrónico para pruebas | Envía un correo electrónico de recordatorio de muestra para verificar el contenido y la entrega. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis clientes no reciben correos electrónicos de recordatorio. ¿Qué debo comprobar?**
R:

1.  **¿Está habilitado el módulo?** Vaya a la configuración del módulo y asegúrese de que "Habilitar / Deshabilitar Módulo" esté configurado en SÍ.
2.  **¿Está configurada correctamente la tarea cron?** Este es el problema más común. El módulo se basa en una tarea cron para ejecutarse automáticamente. Copie la "URL de la tarea Cron" de la configuración del módulo y asegúrese de que esté configurada correctamente en su servidor de alojamiento para que se ejecute diariamente.
3.  **Compruebe la configuración de correo electrónico de PrestaShop:** Vaya a **Parámetros avanzados > Correo electrónico** en su Back Office. Envíe un correo electrónico de prueba desde allí para asegurarse de que el sistema de correo electrónico de su tienda funciona.
4.  **Compruebe las carpetas de spam:** Pida a los clientes que revisen sus carpetas de spam o correo no deseado.
5.  **Borrar la caché de Smarty:** A veces, los cambios de plantilla o las actualizaciones de módulos requieren borrar la caché. Vaya a **Parámetros avanzados > Rendimiento**, desplácese hasta "Borrar caché" y haga clic en "Borrar caché".

**P: El correo electrónico de prueba funciona, pero los clientes siguen sin recibir recordatorios.**
R: Esto sugiere fuertemente que la tarea cron es el problema. El correo electrónico de prueba utiliza el envío de correo inmediato de PrestaShop, mientras que los recordatorios reales dependen de que la tarea cron ejecute el proceso en segundo plano del módulo. Vuelva a verificar la configuración de su tarea cron con su proveedor de alojamiento.

**P: ¿Puedo personalizar el contenido del correo electrónico de recordatorio?**
R: El módulo utiliza las plantillas de correo electrónico estándar de PrestaShop. Normalmente, encontrará los archivos de plantilla de correo electrónico en el directorio `mails/` de su tema (por ejemplo, `themes/yourtheme/mails/en/loyalty_points_reminder.html` y `loyalty_points_reminder.txt`). Si estos no existen, el módulo utilizará las plantillas de correo predeterminadas de PrestaShop. Puede anularlas en su tema para personalizar el texto y la apariencia.

**P: ¿Qué sucede si un cliente no tiene puntos de fidelidad?**
R: El módulo está diseñado para enviar correos electrónicos solo a los clientes que realmente tienen puntos de fidelidad que están cerca de su fecha de caducidad. Si un cliente no tiene puntos, o sus puntos no caducan pronto, no recibirá un correo electrónico.

**P: ¿Funciona este módulo con módulos de puntos de fidelidad personalizados?**
R: Este módulo está diseñado para funcionar con el sistema nativo de puntos de fidelidad de PrestaShop. Si utiliza un módulo de fidelidad de terceros, es posible que no se integre directamente a menos que ese módulo extienda o utilice específicamente las funcionalidades de fidelidad principales de PrestaShop de una manera compatible.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Recordatorio de puntos de fidelidad".

### 4.1 Descripción general de la arquitectura

El módulo "Recordatorio de puntos de fidelidad" (`lpreminder`) es un módulo estándar de PrestaShop que sigue un patrón similar a MVC. Su funcionalidad principal gira en torno a una tarea programada (tarea cron) que activa un controlador frontal para procesar los puntos de fidelidad a punto de caducar y enviar correos electrónicos. Aprovecha las clases nativas `LoyaltyModule` y `Mail` de PrestaShop.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

Estos controladores están diseñados para ser accedidos a través de una URL específica, principalmente para la ejecución de tareas cron.

- **`controllers/front/cronjob.php`**
  - **Nombre de la clase y clase padre:** `LpreminderCronjobModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este es el punto final crítico para la tarea cron. Cuando se accede, ejecuta la lógica del módulo para identificar a los clientes con puntos de fidelidad a punto de caducar y envía correos electrónicos de recordatorio. Idealmente, debería estar protegido (por ejemplo, por un token o restricción de IP) si el módulo no lo ha implementado ya para evitar el acceso no autorizado. No renderiza ninguna salida visual, sino que realiza un procesamiento en segundo plano.
- **`controllers/front/index.php`**
  - **Nombre de la clase y clase padre:** `LpreminderIndexModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador podría servir como un punto de entrada predeterminado o un marcador de posición. En muchos módulos, si no se define una acción específica, `index.php` podría manejarla. Dada la función principal del módulo, `cronjob.php` es el controlador frontal operativo principal. Este `index.php` podría ser un respaldo o usarse para futuras extensiones.

#### Controladores de administración del Back-Office

El módulo no utiliza ningún controlador de administración personalizado. Toda la configuración se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define ninguna clase personalizada o `ObjectModel` en el directorio `classes/`. Interactúa directamente con las clases principales de PrestaShop, en particular:

- `LoyaltyModule`: Para recuperar los puntos de fidelidad del cliente y sus fechas de caducidad.
- `Customer`: Para obtener los detalles del cliente para el envío de correos electrónicos.
- `Mail`: Para enviar los correos electrónicos de recordatorio.
- `Configuration`: Para almacenar y recuperar la configuración del módulo.

### 4.4 Activos de JavaScript (`views/js/`)

El módulo no incluye ningún archivo JavaScript personalizado. Toda la funcionalidad se maneja en el lado del servidor.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo no incluye ningún archivo CSS personalizado. La página de configuración utiliza el estilo predeterminado del Back Office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo no incluye ningún archivo de plantilla Smarty personalizado en su directorio `views/templates/`.

- **Plantillas de correo electrónico:** El módulo se basa en el sistema de plantillas de correo electrónico predeterminado de PrestaShop. El contenido del correo electrónico para el recordatorio se genera utilizando una plantilla llamada `loyalty_points_reminder`. Los desarrolladores pueden personalizar este correo electrónico creando o anulando los siguientes archivos en el directorio `mails/` de su tema activo:
  - `themes/yourtheme/mails/en/loyalty_points_reminder.html` (para contenido de correo electrónico HTML)
  - `themes/yourtheme/mails/en/loyalty_points_reminder.txt` (para contenido de correo electrónico de texto plano)
  - Reemplace `en` con el código de idioma apropiado.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: El módulo no crea ninguna tabla de base de datos personalizada. Almacena sus configuraciones (por ejemplo, `PS_LPREMINDER_DAYS_BEFORE_EXPIRY`, `PS_LPREMINDER_ENABLED`) en la tabla `ps_configuration`. Consulta las tablas existentes de PrestaShop como `ps_loyalty_history` y `ps_customer`.
- **Tabla de Hooks registrados**:
  El módulo utiliza principalmente el hook `actionFrontControllerSetMedia` para una posible inclusión futura de JS/CSS (aunque actualmente no hay ninguno) y se basa implícitamente en el mecanismo de la tarea cron para su funcionalidad principal, que no es un hook tradicional de PrestaShop sino un disparador externo a un controlador frontal.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Renderiza contenido en la sección `<head>` de las páginas del front-office. | No se utiliza directamente para la lógica central del módulo, pero podría usarse para JS/CSS si fuera necesario. |
| `displayRightColumn` | Renderiza contenido en la columna derecha de las páginas del front-office. | No se utiliza directamente para la lógica central del módulo. |
| `displayLeftColumn` | Renderiza contenido en la columna izquierda de las páginas del front-office. | No se utiliza directamente para la lógica central del módulo. |
| `displayFooter` | Renderiza contenido en el pie de página de las páginas del front-office. | No se utiliza directamente para la lógica central del módulo. |
| `displayProductExtraContent` | Renderiza contenido en la página del producto. | No se utiliza directamente para la lógica central del módulo. |
| `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador frontal está configurando sus medios (JS/CSS). | Permite al módulo registrar sus propios activos JS/CSS si es necesario. |
| *(Disparador de tarea Cron)* | Tarea programada externa del lado del servidor (por ejemplo, diaria). | Activa el controlador frontal `cronjob.php` para procesar los puntos de fidelidad a punto de caducar y enviar correos electrónicos. Este es el disparador operativo principal del módulo. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Recordatorio de puntos de fidelidad", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta relacionada con la funcionalidad del módulo.

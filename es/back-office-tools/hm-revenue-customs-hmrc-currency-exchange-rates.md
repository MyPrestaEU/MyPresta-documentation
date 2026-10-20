---
title: "HM Revenue & Customs (HMRC) - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop HM Revenue & Customs (HMRC) - tipos de cambio de divisas de MyPresta.eu."
sidebar:
  label: "HM Revenue & Customs (HMRC) - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo HM Revenue & Customs (HMRC) - currency exchange rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/hm-revenue-customs-hmrc-currency-exchange-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/hm-revenue-customs-hmrc-currency-exchange-rates/)
>
> ---


# HM Revenue & Customs (HMRC) - tipos de cambio de divisas

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para obtener datos externos, las cuales son estándar en la mayoría de los entornos de alojamiento.

## 2. Recorrido completo por la configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la pantalla de configuración principal del módulo de tipos de cambio de HMRC. Aquí es donde configurará cómo el módulo obtiene y aplica los tipos de cambio oficiales.

La página de configuración le presentará la siguiente información y ajustes clave:

#### **URL del Cron Job**

- **Qué hace este ajuste:** Esta es una dirección web especial (URL) que, al ser visitada, activa el módulo para obtener los últimos tipos de cambio de HMRC y actualizarlos en su tienda PrestaShop. Está diseñada para ser ejecutada automáticamente por un "cron job" en su servidor.
- **Efecto de cambiar este ajuste:** No puede cambiar esta URL directamente. Es generada por el módulo.
- **Valor recomendado:** Copie esta URL exactamente como aparece.
- **Escenario / ejemplo de comerciante:** Necesitará esta URL para configurar una tarea automatizada (cron job) en el servidor de su alojamiento web. Esta tarea visitará la URL a una hora programada (por ejemplo, una vez al día o una vez al mes) para asegurarse de que sus tasas estén siempre actualizadas sin que tenga que hacer clic manualmente en nada.

#### **Comando del Cron Job (para servidores Linux/Unix)**

- **Qué hace este ajuste:** Esta es una instrucción de línea de comandos que logra el mismo resultado que visitar la URL del Cron Job, pero está específicamente formateada para su uso directo en el programador de cron jobs de un servidor (a menudo se encuentra en su panel de control de alojamiento como cPanel o Plesk). Utiliza `wget` o `curl` para solicitar la URL de forma silenciosa.
- **Efecto de cambiar este ajuste:** No puede cambiar este comando directamente. Es generado por el módulo.
- **Valor recomendado:** Copie este comando exactamente como aparece.
- **Escenario / ejemplo de comerciante:** Si su proveedor de alojamiento utiliza servidores Linux/Unix (la mayoría lo hacen), utilizará este comando para configurar su cron job automatizado. Esto es generalmente más fiable que depender de servicios de cron basados en la web.

#### **Estado de la última actualización**

- **Qué hace este ajuste:** Esta sección muestra información sobre cuándo el módulo obtuvo y actualizó con éxito las tasas de HMRC por última vez. Mostrará la fecha y hora de la última actualización.
- **Efecto de cambiar este ajuste:** Esto es solo una visualización informativa; no puede cambiarlo.
- **Valor recomendado:** Monitoree esto para asegurarse de que su cron job se está ejecutando correctamente y las tasas se están actualizando regularmente.
- **Escenario / ejemplo de comerciante:** Si configura su cron job para que se ejecute diariamente, debería ver que el "Estado de la última actualización" cambia diariamente, confirmando que el módulo está funcionando como se esperaba. Si no se actualiza, indica un problema con la configuración de su cron job.

#### **Botón "Actualizar ahora"**

- **Qué hace este ajuste:** Este botón le permite activar manualmente el proceso de actualización de tasas inmediatamente, directamente desde la página de configuración del módulo.
- **Efecto de cambiar este ajuste:** Al hacer clic en este botón, se obtendrán instantáneamente las últimas tasas de HMRC y se aplicarán a las monedas de su tienda.
- **Valor recomendado:** Utilice este botón para las pruebas iniciales después de la instalación, o si necesita forzar una actualización inmediata fuera de su cron job programado.
- **Escenario / ejemplo de comerciante:** Después de instalar el módulo, haga clic en "Actualizar ahora" para ver si obtiene las tasas correctamente y para poblar su tienda con las últimas tasas de HMRC antes de que se ejecute su primer cron job programado.

#### **Nota importante sobre los Cron Jobs:**

La funcionalidad principal de este módulo se basa en la configuración de un **cron job** en su servidor web. Un cron job es un programador de tareas basado en el tiempo en sistemas operativos tipo Unix. Permite a los usuarios programar tareas (comandos o scripts) para que se ejecuten periódicamente en momentos, fechas o intervalos fijos.

**Cómo configurar un cron job (pasos generales):**

1. **Acceda a su Panel de Control de Alojamiento:** Inicie sesión en su cPanel, Plesk u otro panel de control de alojamiento.
2. **Busque "Cron Jobs" o "Tareas Programadas":** Busque una sección que generalmente se llama "Cron Jobs", "Tareas Programadas" o "Automatización".
3. **Añada un nuevo Cron Job:**
   - **Frecuencia:** Establezca la frecuencia. Para las tasas de HMRC, mensual suele ser suficiente (por ejemplo, "Una vez al mes" el día 1 del mes). Algunos comerciantes prefieren diariamente para mayor seguridad, pero las tasas de HMRC son mensuales.
   - **Comando:** Pegue el "Comando del Cron Job" proporcionado por el módulo en el campo de comando.
   - **Correo electrónico:** Normalmente puede especificar una dirección de correo electrónico para recibir la salida del cron job. Esto es útil para solucionar problemas si la tarea falla.
4. **Guardar:** Guarde el cron job.

Si no está seguro de cómo configurar un cron job, póngase en contacto con el equipo de soporte de su proveedor de alojamiento y proporcióneles el "Comando del Cron Job" de la página de configuración del módulo, pidiéndoles que lo configuren para que se ejecute mensualmente (o diariamente, según su preferencia).

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | URL del Cron Job | N/A (Copiar y usar) | URL para activar la actualización de tasas; para servicios de cron basados en la web. |
| Configuración del módulo | Comando del Cron Job | N/A (Copiar y usar) | Instrucción de línea de comandos para cron jobs basados en servidor (por ejemplo, cPanel). |
| Configuración del módulo | Estado de la última actualización | N/A (Informativo) | Muestra la fecha/hora de la última actualización exitosa de tasas. |
| Configuración del módulo | Botón "Actualizar ahora" | Clic para actualización manual | Obtiene y aplica inmediatamente las últimas tasas de HMRC. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis tipos de cambio no se están actualizando. ¿Qué debo hacer?**
R: La razón más común para esto es una configuración incorrecta del cron job.
1. **Verifique la configuración de su cron job:** Inicie sesión en el panel de control de su alojamiento (cPanel, Plesk, etc.) y verifique que el cron job esté configurado correctamente utilizando el "Comando del Cron Job" proporcionado por el módulo. Asegúrese de que la frecuencia esté configurada como desee (por ejemplo, mensual o diaria).
2. **Pruebe manualmente:** Vaya a la página de configuración del módulo en el back office de su PrestaShop y haga clic en el botón "Actualizar ahora". Si esto funciona, el problema es definitivamente con la configuración de su cron job. Si no funciona, podría haber un problema del lado del servidor que impida que el módulo obtenga datos (por ejemplo, firewall, problemas de cURL).
3. **Contacte a su host:** Si no está seguro acerca de los cron jobs, proporcione a su soporte de alojamiento el "Comando del Cron Job" y pídales que lo configuren por usted.

**P: ¿Este módulo afecta los precios que ven los clientes en mi sitio web?**
R: Sí, indirectamente. El módulo actualiza los tipos de cambio subyacentes en PrestaShop. Si su tienda permite a los clientes cambiar entre monedas, los precios mostrados en esas monedas extranjeras reflejarán los tipos actualizados. Sin embargo, el propósito principal del módulo es para la contabilidad *interna* y el cumplimiento fiscal, no necesariamente para estrategias de precios dinámicas en el front-end.

**P: ¿Qué sucede si HMRC cambia su método de publicación de tipos de cambio?**
R: MyPresta.eu monitorea regularmente los cambios en servicios externos como HMRC. Si HMRC altera su fuente de datos o formato, lanzaremos una actualización del módulo para garantizar la compatibilidad continua. Mantenga siempre sus módulos actualizados a sus últimas versiones.

**P: ¿Puedo usar este módulo si mi moneda base no es GBP?**
R: Si bien el módulo obtiene las tasas de HMRC, su beneficio principal es para el cumplimiento del IVA del Reino Unido, lo que generalmente asume GBP como la moneda de informe. Si su moneda base no es GBP, el módulo seguirá actualizando los tipos de cambio para otras monedas en relación con su moneda base, pero deberá comprender cómo esto interactúa con sus obligaciones específicas de declaración de impuestos. Para el IVA del Reino Unido, generalmente se recomienda tener GBP como su moneda predeterminada.

**P: Veo un mensaje de error al intentar actualizar las tasas manualmente.**
R: Esto podría indicar varias cosas:
1. **Conectividad del servidor:** Su servidor podría no poder conectarse al sitio web de HMRC para obtener los datos. Esto podría deberse a un firewall, un problema de red o una interrupción temporal del servidor de HMRC.
2. **Extensiones PHP:** Asegúrese de que las extensiones PHP estándar como `cURL` y `JSON` estén habilitadas en su servidor.
3. **Permisos del módulo:** Verifique que los archivos del módulo tengan los permisos de lectura/escritura correctos.
Si el problema persiste, póngase en contacto con el soporte de MyPresta.eu con el mensaje de error exacto.

## 4. Guía para desarrolladores y webmasters (arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica para desarrolladores y webmasters responsables de mantener o extender la tienda PrestaShop.

### 4.1 Resumen de la arquitectura

El módulo `hmrcrates` es un módulo de PrestaShop sencillo diseñado para obtener y actualizar los tipos de cambio de divisas del sitio web de HMRC. Aprovecha la arquitectura de módulos de PrestaShop, utilizando principalmente la clase `Module` para la instalación/desinstalación y `ModuleFrontController` para manejar las solicitudes de cron job. La lógica central reside en el archivo principal del módulo, `cronjob.php`, que también actúa como el punto de entrada principal para la configuración y la ejecución del cron. No utiliza `ObjectModel` ya que manipula directamente los objetos `Currency` existentes.

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**:

  - `controllers/front/cronjob.php`
    - **Nombre de la clase y clase padre**: `HmrcratesCronjobModuleFrontController` que extiende `ModuleFrontController`.
    - **Responsabilidad**: Este controlador es el punto final público para el cron job. Cuando se accede a través de su URL (por ejemplo, `sutenda.com/module/hmrcrates/cronjob`), activa el método `processUpdateRates()` en el módulo principal `hmrcrates`. Está diseñado para ser llamado por servicios de cron externos o cron jobs del lado del servidor. Emite un mensaje simple de éxito o error.
  - `controllers/front/index.php`
    - **Nombre de la clase y clase padre**: `HmrcratesIndexModuleFrontController` que extiende `ModuleFrontController`.
    - **Responsabilidad**: Este es un controlador de marcador de posición, típicamente utilizado para proporcionar un punto de entrada predeterminado para un módulo si no se solicita ninguna acción específica. En el contexto de este módulo, probablemente no tiene ningún propósito funcional directo más allá de proporcionar una ruta predeterminada si `cronjob.php` no se llama explícitamente. Podría redirigir o simplemente mostrar una página en blanco.
- **Controladores de administración del Back-Office**:

  - Este módulo no utiliza archivos `AdminController` dedicados. Toda la configuración del back-office se gestiona directamente dentro del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada dentro del directorio `classes/`. La lógica central para obtener y actualizar las tasas está encapsulada dentro del archivo principal del módulo, `hmrcrates/cronjob.php`. Interactúa directamente con la clase `Currency` incorporada de PrestaShop para actualizar los tipos de cambio.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. La configuración del back-office se basa en el estilo predeterminado del back-office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - `views/templates/admin/admin.tpl`
    - **Propósito**: Esta plantilla es renderizada por el método `getContent()` de la clase principal del módulo (`hmrcrates/cronjob.php`) para mostrar el formulario de configuración del módulo en el back office de PrestaShop.
    - **Contenido**: Típicamente incluye la estructura HTML para mostrar la URL del Cron Job, el Comando del Cron Job, el Estado de la última actualización y el botón "Actualizar ahora". Utiliza los ayudantes de formulario y el estilo estándar de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo no crea ninguna tabla SQL personalizada.
  - Almacena sus ajustes de configuración (por ejemplo, `HMRCRATES_LAST_UPDATE`) en la tabla estándar `ps_configuration` de PrestaShop.
  - Actualiza la columna `exchange_rate` en la tabla `ps_currency` para las monedas relevantes.
- **Tabla de Hooks registrados**:
  Este módulo no registra explícitamente ningún hook de visualización del front-office (como `displayHeader`, `displayRightColumn`, `displayFooter`) ya que su funcionalidad está puramente orientada al backend. Su "hook" principal es el hook `action` activado por el `ModuleFrontController` para el cron job.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionModuleInstall` | Durante la instalación del módulo | Crea entradas de configuración, configura datos iniciales. |
| `actionModuleUninstall` | Durante la desinstalación del módulo | Limpia las entradas de configuración. |
| (Implícito) `actionFrontControllerSetMedia` | Cuando se carga un controlador frontal | No utilizado explícitamente por este módulo, pero estándar para que los módulos carguen activos. |
| (Implícito) `actionDispatcher` | Cuando se despacha un controlador frontal | El `ModuleFrontController` `HmrcratesCronjobModuleFrontController` se despacha cuando se accede a la URL del cron, lo que activa la lógica de actualización de tasas. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y para descargar las últimas versiones del módulo "HM Revenue & Customs (HMRC) - tipos de cambio de divisas", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad o configuración del módulo.

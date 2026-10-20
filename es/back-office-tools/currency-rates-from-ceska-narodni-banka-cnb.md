---
title: "Tasas de cambio del Česká národní banka (CNB) - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Tasas de cambio del Česká národní banka (CNB)' de MyPresta.eu."
sidebar:
  label: "Tasas de cambio del Česká národní banka (CNB) - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Currency rates from Česká národní banka (CNB) en MyPresta.eu](https://mypresta.eu/modules/administration-tools/currency-rates-from-ceska-narodni-banka-cnb.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/currency-rates-from-ceska-narodni-banka-cnb/)
>
> ---


# Tasas de cambio del Česká národní banka (CNB)

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para obtener datos externos, las cuales están casi universalmente disponibles en entornos de alojamiento modernos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo para acceder a sus ajustes. Esta es la pantalla de configuración principal y única para el módulo.

#### **Ajustes y opciones**

**1. `mypresta_updates` (Actualizaciones de MyPresta.eu)**

- **Qué hace este ajuste:** Este es un ajuste estándar que se encuentra en muchos módulos de MyPresta.eu. Controla si el módulo busca actualizaciones de MyPresta.eu y muestra notificaciones en el back office de PrestaShop.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El módulo buscará periódicamente nuevas versiones disponibles en MyPresta.eu. Si se encuentra una actualización, es posible que vea una notificación en el panel de administración de PrestaShop, lo que le indicará que descargue e instale la versión más reciente. Esto le ayuda a mantenerse actualizado con correcciones de errores y nuevas funciones.
  - *Cuando está deshabilitado (NO):* El módulo no buscará actualizaciones. No recibirá ninguna notificación sobre nuevas versiones, lo que significa que tendría que revisar manualmente su cuenta de MyPresta.eu para ver si hay actualizaciones.
- **Valor recomendado:** **SÍ**. Siempre se recomienda mantener los módulos actualizados por seguridad, compatibilidad y nuevas funciones.
- **Escenario / ejemplo de comerciante:** Desea asegurarse de que su módulo siempre esté ejecutando la última versión más estable sin tener que verificar constantemente de forma manual. Habilitar esto le avisará cuando haya una actualización disponible.

**2. `update_` (Frecuencia de actualización)**

- **Qué hace este ajuste:** Este ajuste determina con qué frecuencia el módulo intenta obtener y actualizar las tasas de cambio de moneda del feed del CNB.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un intervalo más corto (por ejemplo, "Cada hora"):* Sus tasas de cambio se actualizarán con mayor frecuencia, asegurando que sus precios estén muy actualizados, lo cual es beneficioso en mercados volátiles. Sin embargo, podría aumentar ligeramente la carga del servidor (aunque típicamente insignificante para este tipo de operación).
  - *Cuando se establece un intervalo más largo (por ejemplo, "Una vez al día"):* Las tasas se actualizan con menos frecuencia. Esto suele ser suficiente ya que el CNB normalmente proporciona tasas diarias. Reduce la carga del servidor.
- **Valor recomendado:** **Una vez al día**. El CNB suele publicar tasas diarias, por lo que actualizar con más frecuencia de una vez al día suele ser innecesario y no proporciona datos más recientes.
- **Escenario / ejemplo de comerciante:** Dirige una tienda internacional donde las fluctuaciones del tipo de cambio pueden afectar sus márgenes de beneficio. Establecer esto en "Una vez al día" garantiza que siempre tenga las últimas tasas oficiales sin sobrecargar su servidor.

**3. `updatev_` (Método de actualización)**

- **Qué hace este ajuste:** Este ajuste define cómo el módulo activa el proceso de actualización de las tasas de cambio.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "Tarea programada (Cron Job)":* El módulo espera que configure una tarea programada (cron job) en el servidor que llamará periódicamente a una URL específica proporcionada por el módulo. Este es el método más fiable y recomendado, ya que garantiza que las actualizaciones se realicen exactamente cuando están programadas, incluso si nadie visita su tienda.
  - *Cuando se establece en "Al cargar la página":* El módulo intentará actualizar las tasas cuando un cliente o administrador visite cualquier página de su tienda. Esto es menos fiable, ya que las actualizaciones solo ocurren cuando hay tráfico en su sitio, y si su sitio tiene poco tráfico, las actualizaciones podrían retrasarse. También puede ralentizar ligeramente la primera carga de la página para un visitante si una actualización está pendiente.
- **Valor recomendado:** **Tarea programada (Cron Job)**. Este es el método más robusto y eficiente para tareas programadas. El módulo le proporcionará la URL exacta para usar en su tarea programada.
- **Escenario / ejemplo de comerciante:** Desea garantizar que las tasas de cambio se actualicen cada mañana a las 3 AM, independientemente del tráfico del sitio web. Configurar esto en "Tarea programada (Cron Job)" y configurar el cron de su servidor logrará esto de manera fiable.

**4. `currency_` (Monedas a actualizar)**

- **Qué hace este ajuste:** Esto le permite seleccionar qué monedas específicas en su tienda PrestaShop deben tener sus tasas de cambio actualizadas por el feed del CNB.
- **Efecto de cambiar este ajuste:**
  - *Cuando se seleccionan monedas específicas:* Solo las monedas elegidas tendrán sus tasas de cambio actualizadas por el módulo. Otras monedas (si tiene alguna) conservarán sus tasas establecidas manualmente o el mecanismo de actualización predeterminado de PrestaShop (si está activo). Esto le da un control granular.
  - *Cuando no se selecciona ninguna moneda (o se seleccionan todas):* El módulo intentará actualizar todas las monedas activas en su tienda que estén presentes en el feed del CNB.
- **Valor recomendado:** Seleccione **todas las monedas que utilice activamente para transacciones y que sean compatibles con el feed del CNB**. Típicamente, esto incluye EUR, USD, GBP y otras monedas importantes.
- **Escenario / ejemplo de comerciante:** Su tienda acepta pagos en EUR, USD y CZK. Desea que las tasas de EUR y USD sean actualizadas por el CNB, pero CZK es su moneda predeterminada y no necesita actualizaciones externas. Seleccionaría EUR y USD de esta lista.

#### **URL de la tarea programada (Cron Job) (Se muestra después de guardar la configuración)**

- **Qué hace esto:** Después de configurar y guardar los ajustes del módulo, especialmente si elige "Tarea programada (Cron Job)" como método de actualización, el módulo mostrará una URL única. Esta URL es la que la tarea programada de su servidor necesita llamar para activar el proceso de actualización.
- **Efecto de usar esta URL:** Cuando se accede a esta URL (ya sea por la tarea programada de su servidor o manualmente en un navegador), el módulo ejecuta su lógica para obtener las últimas tasas de cambio del CNB y las actualiza en la base de datos de su PrestaShop.
- **Acción recomendada:** Copie esta URL y configúrela como una tarea programada en su servidor de alojamiento. Consulte la documentación o el soporte de su proveedor de alojamiento para saber cómo configurar una tarea programada. Una tarea programada típica podría ser `wget -q -O /dev/null "SU_URL_CRON_AQUÍ"`.
- **Escenario / ejemplo de comerciante:** Ha configurado la frecuencia de actualización en "Una vez al día" y el método en "Tarea programada (Cron Job)". El módulo muestra `https://sutenda.com/module/cnbrates/cronjob?token=SU_TOKEN_ÚNICO`. Entonces configuraría el cron de su servidor para ejecutar `wget -q -O /dev/null "https://sutenda.com/module/cnbrates/cronjob?token=SU_TOKEN_ÚNICO"` una vez cada 24 horas.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Actualizaciones de MyPresta.eu | SÍ | Controla las notificaciones de actualización de MyPresta.eu. |
| Configuración del módulo | Frecuencia de actualización | Una vez al día | Con qué frecuencia el módulo obtiene nuevas tasas del CNB. |
| Configuración del módulo | Método de actualización | Tarea programada (Cron Job) | Cómo se activa el proceso de actualización (tarea programada vs. carga de página). |
| Configuración del módulo | Monedas a actualizar | Seleccionar todas las relevantes | Especifica qué monedas de su tienda son actualizadas por el CNB. |
| Configuración del módulo | URL de la tarea programada (Cron Job) | (Se muestra después de guardar) | La URL a usar para las tareas programadas del servidor para activar las actualizaciones. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis tasas de cambio no se actualizan. ¿Qué debo verificar primero?**
R: La razón más común es un problema con la tarea programada (cron job).

1. Vaya a **Módulos > Gestor de módulos > Configurar** para el módulo de Tasas CNB.
2. Verifique la configuración de "Método de actualización". Si es "Tarea programada (Cron Job)", asegúrese de haber configurado correctamente la tarea programada en su servidor de alojamiento utilizando la URL proporcionada. Póngase en contacto con el soporte de su proveedor de alojamiento si no está seguro de cómo hacerlo.
3. Si se selecciona "Al cargar la página", asegúrese de que su tienda reciba tráfico regular. Si no, cambie a "Tarea programada (Cron Job)" para actualizaciones más fiables.
4. Además, verifique que las monedas que espera que se actualicen estén seleccionadas en la lista "Monedas a actualizar".

**P: ¿Funciona este módulo si la moneda predeterminada de mi tienda no es CZK?**
R: ¡Sí, absolutamente! El módulo está diseñado para funcionar incluso si su moneda predeterminada no es CZK. Obtiene las tasas del CNB, que proporciona tasas de cambio para varias monedas frente al CZK. Luego, el módulo convierte inteligentemente estas tasas para actualizar las monedas no predeterminadas de su tienda en relación con su moneda predeterminada real.

**P: ¿Con qué frecuencia actualiza el CNB sus tasas?**
R: El Česká národní banka (CNB) suele publicar sus tasas de cambio oficiales una vez al día, normalmente en días hábiles. Por lo tanto, configurar la "Frecuencia de actualización" de su módulo en "Una vez al día" suele ser suficiente para capturar los últimos datos disponibles.

**P: He actualizado el módulo, pero no veo ningún cambio. ¿Qué puedo hacer?**
R: A veces, el sistema de caché de PrestaShop puede impedir la visualización inmediata de los cambios.

1. Vaya a **Parámetros avanzados > Rendimiento** en el back office de su PrestaShop.
2. Haga clic en "Borrar caché" (o "Borrar caché de Smarty" si está disponible).
3. Actualice su navegador (Ctrl+F5 o Cmd+R) para asegurarse de que no está viendo una versión en caché de la página.

**P: ¿Puedo activar una actualización manualmente?**
R: Sí, si su "Método de actualización" está configurado en "Tarea programada (Cron Job)", puede visitar manualmente la URL de la tarea programada (mostrada en la configuración del módulo) en su navegador web. Esto activará una actualización inmediata. Sin embargo, esto es solo para pruebas/solución de problemas; para actualizaciones regulares, confíe en la tarea programada automatizada.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Tasas de cambio del Česká národní banka (CNB)" es un módulo ligero de PrestaShop diseñado para una única tarea específica: obtener y actualizar las tasas de cambio de moneda. Principalmente, aprovecha un controlador de front-office para exponer un punto final de tarea programada (cron job), lo que permite actualizaciones programadas y automatizadas. El módulo no introduce nuevas tablas de base de datos ni estructuras `ObjectModel` complejas, sino que se basa en la clase `Currency` existente de PrestaShop y en `Configuration` para sus ajustes. Sigue una estructura básica de módulo de PrestaShop, integrándose con los métodos `install()` y `uninstall()` para la configuración y limpieza.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `controllers/front/cronjob.php`
    - **Nombre de la clase y clase padre**: `CnbratesCronjobModuleFrontController` extiende `ModuleFrontController`.
    - **Responsabilidad**: Este controlador es el núcleo de la automatización del módulo. Responde a las solicitudes a la URL de la tarea programada (por ejemplo, `sutenda.com/module/cnbrates/cronjob?token=...`). Su método `initContent()` (o método de ciclo de vida similar) contiene la lógica para:
      1. Validar el parámetro `token` contra la configuración almacenada para evitar accesos no autorizados.
      2. Obtener las últimas tasas de cambio del feed XML del CNB (típicamente `https://www.cnb.cz/cs/financni_trhy/devizovy_trh/kurzy_devizoveho_trhu/denni_kurz.xml`).
      3. Analizar los datos XML.
      4. Iterar a través de las monedas configuradas en PrestaShop.
      5. Para cada moneda seleccionada, calcular su nueva tasa de cambio basándose en los datos del CNB (que suele ser relativa a CZK) y la moneda predeterminada de la tienda.
      6. Actualizar el campo `exchange_rate` para el objeto `Currency` respectivo en la tabla `ps_currency`.
      7. Imprimir un mensaje simple de éxito o error, principalmente para el registro de la tarea programada.
  - `controllers/front/index.php`
    - **Nombre de la clase y clase padre**: `CnbratesIndexModuleFrontController` extiende `ModuleFrontController`.
    - **Responsabilidad**: Este es un controlador de marcador de posición o de reserva. En muchos módulos, un controlador de front-office `index.php` sirve como punto de entrada predeterminado si no se solicita ninguna acción específica. Para este módulo, su función principal es probablemente redirigir a la página de inicio o mostrar un mensaje simple, ya que la funcionalidad principal es manejada por `cronjob.php`. No contiene una lógica de negocio significativa para las actualizaciones de moneda.
- **Controladores de administración de Back-Office**: Ninguno. La configuración del módulo se maneja completamente dentro de `cnbrates.php` a través de `getContent()`.

### 4.3 Clases y modelos principales (`classes/`)

No hay clases personalizadas ni definiciones de `ObjectModel` dentro del directorio `classes/` para este módulo. El módulo interactúa directamente con la clase `Currency` y la clase `Configuration` de PrestaShop para la gestión de datos.

### 4.4 Activos JavaScript (`views/js/`)

No hay archivos JavaScript personalizados en este módulo. Toda la funcionalidad es PHP del lado del servidor.

### 4.5 Hojas de estilo CSS (`views/css/`)

No hay archivos CSS personalizados en este módulo. El módulo no introduce ningún elemento visual de front-office ni estilos complejos de back-office más allá de los elementos de formulario estándar de PrestaShop.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de gancho (`views/templates/hook/`)**: Ninguna. El módulo no muestra contenido a través de ganchos.
- **Plantillas de administración (`views/templates/admin/`)**:
  - `views/admin.tpl`
    - **Propósito**: Esta plantilla es renderizada por el método `getContent()` en `cnbrates.php` para mostrar el formulario de configuración del módulo en el back office de PrestaShop.
    - **Contenido**: Contiene la estructura HTML para los ajustes descritos en la Sección 4.1, incluidos los campos de entrada para la frecuencia de actualización, el método de actualización, la selección de moneda y la visualización de la URL de la tarea programada. Utiliza los ayudantes de formulario y el estilo estándar de PrestaShop.
- **Plantillas de front-office (`views/templates/front/`)**: Ninguna.

### 4.7 Esquema de la base de datos y mapa de ganchos

- **Tablas de la base de datos**:

  - El módulo **no** crea ninguna tabla SQL personalizada.
  - Almacena sus ajustes de configuración en la tabla `ps_configuration` de PrestaShop. Las claves de configuración principales incluyen:
    - `CNBRATES_UPDATE_FREQUENCY`
    - `CNBRATES_UPDATE_METHOD`
    - `CNBRATES_CURRENCIES` (probablemente una lista de IDs de moneda separada por comas)
    - `CNBRATES_CRON_TOKEN` (un token único para la seguridad de la tarea programada)
    - `MYPRESTA_UPDATES_CNBRATES` (para las comprobaciones de actualización de MyPresta.eu)
  - Actualiza la columna `exchange_rate` en la tabla `ps_currency` para las monedas seleccionadas.
- **Tabla de ganchos registrados**:
  El módulo registra los siguientes ganchos, principalmente para su propia gestión del ciclo de vida y potencialmente para comprobaciones de actualización, en lugar de mostrar contenido:

| Nombre del gancho | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En cada carga de página en el front office (antes de la salida HTML). | A menudo se utiliza para la inclusión de JS/CSS, o en este caso, potencialmente para el método de actualización "Al cargar la página" si está configurado, o para las comprobaciones de actualización de MyPresta.eu. |
| `displayRightColumn` | Renderiza contenido en la columna derecha del front office. | No utilizado para la visualización de contenido por este módulo, posiblemente un registro de gancho heredado o para comprobaciones internas. |
| `displayLeftColumn` | Renderiza contenido en la columna izquierda del front office. | No utilizado para la visualización de contenido por este módulo, posiblemente un registro de gancho heredado o para comprobaciones internas. |
| `displayFooter` | Renderiza contenido en el pie de página del front office. | No utilizado para la visualización de contenido por este módulo, posiblemente un registro de gancho heredado o para comprobaciones internas. |
| `displayBackOfficeHeader` | En cada carga de página en el back office. | Se utiliza para incluir CSS/JS específicos del módulo para la página de configuración, o para mostrar notificaciones de actualización de MyPresta.eu. |
| `actionAdminCurrenciesControllerSaveAfter` | Después de guardar una moneda en el back office. | Podría usarse para reevaluar la configuración de la moneda o activar una actualización si el estado de una moneda cambia. |
| `actionAdminCurrenciesControllerDeleteAfter` | Después de eliminar una moneda en el back office. | Podría usarse para eliminar la moneda eliminada de la lista de actualización del módulo. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y las últimas versiones del módulo "Tasas de cambio del Česká národní banka (CNB)", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad o integración del módulo.

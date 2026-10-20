---
title: "BdE Tipos de Cambio y Moneda (Banco de España) - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop BdE Tipos de Cambio y Moneda (Banco de España) de MyPresta.eu."
sidebar:
  label: "BdE Tipos de Cambio y Moneda (Banco de España) - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo BdE Exchange Rates & Currency (Bank of Spain) en MyPresta.eu](https://mypresta.eu/modules/administration-tools/bde-exchange-rates-currency-bank-of-spain.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/bde-exchange-rates-currency-bank-of-spain/)
>
> ---


# BdE Tipos de Cambio y Moneda (Banco de España)

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar como cURL (para obtener datos externos), JSON (para procesar datos) y OpenSSL (para conexiones seguras) suelen ser necesarias y son estándar en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederás a la página principal de configuración del módulo "BdE Tipos de Cambio y Moneda (Banco de España)". Aquí es donde controlas cómo el módulo obtiene y aplica los tipos de cambio.

#### **Actualizaciones en Vivo de MyPresta.eu**

- **Qué hace esta configuración:** Esta sección te permite gestionar la conexión del módulo a MyPresta.eu para actualizaciones automáticas y soporte.
- **Efecto de cambiar esta configuración:**
  - *Introducir tu ID de pedido y correo electrónico de MyPresta.eu:* Permite que el módulo compruebe si hay nuevas versiones y reciba actualizaciones directamente de MyPresta.eu. Esto asegura que siempre tengas las últimas características y correcciones de errores.
  - *Dejarlo vacío:* El módulo no podrá comprobar si hay actualizaciones automáticas. Tendrías que descargar e instalar manualmente las nuevas versiones desde tu cuenta MyPresta.eu.
- **Valor recomendado:** Introduce siempre tu ID de pedido de MyPresta.eu y la dirección de correo electrónico asociada a tu compra. Esto es crucial para recibir actualizaciones y soporte a tiempo.
- **Escenario / ejemplo de comerciante:** Compraste el módulo usando `tu.email@ejemplo.com` y tu ID de pedido era `MP12345`. Introducir estos detalles aquí significa que se te notificará directamente en el back office de tu PrestaShop cuando se lance una nueva versión del módulo, y podrás actualizar con un solo clic.

#### **URL del CRON Job**

- **Qué hace esta configuración:** Muestra una URL única que puedes usar para configurar un "CRON job" en tu servidor. Un CRON job es una tarea programada que ejecuta automáticamente un comando o URL específico a intervalos regulares (por ejemplo, una vez al día).
- **Efecto de cambiar esta configuración:**
  - *Configurar un CRON job con esta URL:* El módulo obtendrá automáticamente los últimos tipos de cambio del Banco de España con la frecuencia que definas (por ejemplo, diariamente). Esto asegura que tus tipos de cambio estén siempre actualizados sin ninguna intervención manual.
  - *No configurar un CRON job:* Los tipos de cambio no se actualizarán automáticamente. Tendrías que visitar manualmente esta URL en tu navegador cada vez que quieras actualizar los tipos, lo cual es muy poco práctico y anula el propósito de la automatización.
- **Valor recomendado:** Copia esta URL y configura un CRON job diario en tu servidor de alojamiento. La mayoría de los paneles de control de alojamiento (como cPanel, Plesk) tienen una sección de "Cron Jobs" donde puedes añadir fácilmente esta URL para que se ejecute una vez cada 24 horas.
- **Escenario / ejemplo de comerciante:** Quieres que tus tipos de cambio de Euro se actualicen cada mañana a las 3:00 AM. Copias la URL del CRON proporcionada, vas a tu panel de control de alojamiento, creas un nuevo CRON job, pegas la URL y lo configuras para que se ejecute diariamente a las 3:00 AM. A partir de entonces, tus tipos se actualizarán automáticamente.

#### **Ajuste de Margen (%)**

- **Qué hace esta configuración:** Te permite añadir un pequeño porcentaje de margen a los tipos de cambio obtenidos. Esto puede ser útil para cubrir posibles tarifas de transacción, costos de conversión de moneda o simplemente para darte un pequeño margen.
- **Efecto de cambiar esta configuración:**
  - *Establecer un porcentaje positivo (por ejemplo, 2%):* El módulo aumentará el tipo de cambio oficial en ese porcentaje. Por ejemplo, si el tipo oficial es 1 EUR = 1.10 USD, y estableces un margen del 2%, el módulo usará 1 EUR = 1.122 USD (1.10 * 1.02). Esto significa que los productos con precio en EUR aparecerán ligeramente más caros cuando se conviertan a USD.
  - *Establecer 0% (predeterminado):* El módulo utilizará los tipos de cambio oficiales exactos sin ningún ajuste.
- **Valor recomendado:** 0% a menos que tengas razones comerciales específicas (como cubrir tarifas bancarias) para añadir un margen. La transparencia suele ser lo mejor para la confianza del cliente.
- **Escenario / ejemplo de comerciante:** Tu pasarela de pago cobra una tarifa del 1.5% por las conversiones de moneda internacional. Para compensar esto, podrías establecer el Ajuste de Margen en 1.5%. Esto asegura que tus precios convertidos tengan en cuenta ligeramente este costo.

#### **Actualizar Tipos de Cambio**

- **Qué hace esta configuración:** Este es un botón de activación manual para obtener y actualizar inmediatamente todos los tipos de cambio del Banco de España.
- **Efecto de cambiar esta configuración:**
  - *Hacer clic en el botón:* El módulo se conectará instantáneamente al Banco de España, recuperará los últimos tipos y los actualizará en tu tienda PrestaShop. Esto es útil para realizar pruebas o para una actualización inmediata fuera del horario de tu CRON job.
- **Valor recomendado:** Utiliza este botón para pruebas de configuración inicial o si necesitas una actualización inmediata. Para actualizaciones regulares, confía en el CRON job.
- **Escenario / ejemplo de comerciante:** Acabas de instalar el módulo y quieres verificar que funciona correctamente y que está obteniendo los últimos tipos. Haces clic en este botón para ver el efecto inmediato.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | ID de Pedido MyPresta.eu | Tu ID de Pedido | Habilita las actualizaciones automáticas del módulo y el soporte. |
| Configuración del Módulo | Correo Electrónico MyPresta.eu | Tu Correo Electrónico | Habilita las actualizaciones automáticas del módulo y el soporte. |
| Configuración del Módulo | URL del CRON Job | (URL Única) | Configura un CRON job diario con esta URL para actualizaciones automáticas de tipos. |
| Configuración del Módulo | Ajuste de Margen (%) | 0% | Añade un porcentaje de amortiguación a los tipos de cambio (por ejemplo, para tarifas). |
| Configuración del Módulo | Actualizar Tipos de Cambio | Haz clic para activar | Obtiene y actualiza manualmente los tipos de cambio inmediatamente. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Mis tipos de cambio no se actualizan automáticamente.**
R:

1.  **Verifica la configuración de tu CRON job:** Vuelve a comprobar que has configurado correctamente el CRON job en tu servidor de alojamiento utilizando la URL exacta proporcionada en la configuración del módulo. Asegúrate de que esté programado para ejecutarse al menos una vez al día.
2.  **Verifica la ejecución del CRON job:** Algunos paneles de alojamiento proporcionan registros de la ejecución del CRON job. Revisa estos registros para ver si el CRON job se está ejecutando realmente y si hay algún error.
3.  **Conectividad del servidor:** Asegúrate de que tu servidor tenga acceso saliente a sitios web externos (específicamente la API del Banco de España). A veces, los cortafuegos pueden bloquear esto. Ponte en contacto con tu proveedor de alojamiento si sospechas que este es el problema.
4.  **Configuración del módulo:** Asegúrate de que tus datos de MyPresta.eu estén introducidos correctamente para posibles problemas de actualización.

**P: Los precios en EUR parecen ligeramente incorrectos, incluso después de una actualización.**
R:

1.  **Verifica el Ajuste de Margen:** Revisa la configuración de "Ajuste de Margen (%)" en la configuración del módulo. Si está configurado con un valor superior a 0, tus precios se ajustarán en ese porcentaje. Configúralo en 0% si quieres tipos oficiales exactos.
2.  **Redondeo de PrestaShop:** PrestaShop tiene sus propias reglas de redondeo para los precios. Asegúrate de que la configuración de tu moneda en **Internacional > Monedas** esté configurada con la precisión decimal deseada.
3.  **Caché:** Borra la caché de tu PrestaShop (Parámetros Avanzados > Rendimiento) y la caché de tu navegador.

**P: ¿Qué sucede en días festivos bancarios o fines de semana cuando el Banco de España no publica nuevos tipos?**
R: El módulo está diseñado para manejar esto de forma inteligente. Si no hay nuevos tipos disponibles para un día determinado, seguirá utilizando los últimos tipos obtenidos con éxito. Una vez que se publiquen nuevos tipos, el módulo los actualizará en su próxima ejecución programada.

**P: ¿Puedo usar este módulo con otros módulos de moneda?**
R: Este módulo se centra específicamente en obtener y aplicar los tipos oficiales del Banco de España. Generalmente funciona bien junto con las funciones nativas de PrestaShop para múltiples monedas. Sin embargo, si tienes otros módulos que *también* intentan obtener o anular los tipos de cambio de diferentes fuentes, podría haber conflictos. Es mejor usar una fuente principal para las actualizaciones de tipos de cambio para evitar inconsistencias.

**P: Veo una sección "Actualizaciones de MyPresta.eu". ¿Para qué sirve?**
R: Esta sección te permite introducir tu ID de pedido y correo electrónico de MyPresta.eu. Esto permite que el módulo compruebe si hay nuevas versiones y reciba actualizaciones directamente de MyPresta.eu, asegurando que siempre tengas las últimas características y correcciones de errores. Es muy recomendable rellenar esta sección.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo `BdE Exchange Rates & Currency` es un módulo ligero de PrestaShop diseñado principalmente para integrarse con la API oficial de tipos de cambio del Banco de España. Sigue una estructura de módulo estándar de PrestaShop, aprovechando la clase `Module` para la instalación y configuración, y `ModuleFrontController` para manejar las solicitudes de CRON job. Su funcionalidad principal gira en torno a la obtención de datos externos, su análisis y la actualización de los tipos de cambio nativos de `Currency` de PrestaShop.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

-   **`controllers/front/cronjob.php`**
    -   **Nombre de la clase y clase padre:** `BderatesCronjobModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este controlador es el punto de entrada para la tarea CRON programada. Cuando se accede a él, inicia el proceso de obtención de los últimos tipos de cambio del Banco de España. Maneja la solicitud de la API, analiza la respuesta y actualiza los tipos de cambio para las monedas configuradas en PrestaShop. Está diseñado para ser llamado externamente por un programador CRON del lado del servidor y normalmente devuelve un mensaje simple de éxito/fallo.
-   **`controllers/front/index.php`**
    -   **Nombre de la clase y clase padre:** `BderatesIndexModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este es un controlador de marcador de posición, a menudo incluido en los módulos pero no utilizado activamente en la funcionalidad principal de este módulo específico. Podría estar presente para fines de enrutamiento o como un punto de entrada predeterminado, pero la lógica principal para las actualizaciones de tipos está dentro de `cronjob.php`.

#### Controladores de Administración de Back-Office

Este módulo no implementa ningún controlador de administración de Back-Office personalizado. Toda la configuración se gestiona a través del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no define ninguna clase personalizada o `ObjectModel` en el directorio `classes/`. Interactúa directamente con la clase `Currency` principal de PrestaShop para actualizar los tipos de cambio.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de Estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de administración (`views/templates/admin/`)

-   **`views/templates/admin/admin.tpl`**
    -   **Propósito:** Esta plantilla se utiliza para renderizar el formulario de configuración del módulo en el Back Office de PrestaShop. Muestra los campos de entrada para las actualizaciones de MyPresta.eu, la URL del CRON job, el ajuste de margen y el botón de actualización manual.
    -   **Contexto:** Renderizado por el método `getContent()` del archivo principal del módulo `bderates.php`.
    -   **Elementos clave:** Elementos de formulario para las configuraciones `mypresta_updates`, `update_`, `updatev_`, `currency_`.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

Este módulo no crea ninguna tabla SQL personalizada. Almacena sus configuraciones directamente en la tabla `ps_configuration` de PrestaShop utilizando claves como:

-   `BDERATES_MYPRESTA_ID`
-   `BDERATES_MYPRESTA_EMAIL`
-   `BDERATES_MARGIN`
-   `BDERATES_LAST_UPDATE`

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | No utilizado activamente para la salida visual por este módulo, pero a menudo registrado por módulos para configuración general o carga de activos. |
| `displayRightColumn` | En la columna derecha de las páginas del front-office. | No utilizado activamente para la salida visual por este módulo. |
| `displayLeftColumn` | En la columna izquierda de las páginas del front-office. | No utilizado activamente para la salida visual por este módulo. |
| `displayFooter` | En la sección del pie de página de cada página del front-office. | No utilizado activamente para la salida visual por este módulo. |
| `displayProductAdditionalInfo` | En la página del producto, debajo de la información principal del producto. | No utilizado activamente para la salida visual por este módulo. |
| `actionUpdateCurrency` | Se activa después de que se actualiza el tipo de cambio de una moneda. | Este módulo *activa* este hook cuando actualiza los tipos de cambio, permitiendo que otros módulos reaccionen al cambio. |
| `actionCronJob` | Un hook personalizado a menudo utilizado por los módulos para registrar sus tareas CRON. | El controlador `cronjob.php` del módulo es el mecanismo principal para las actualizaciones programadas, pero este hook podría registrarse para compatibilidad o expansión futura. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y las últimas versiones del módulo "BdE Tipos de Cambio y Moneda (Banco de España)", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto a la funcionalidad e integración del módulo.

---
title: "Tasas de cambio de Banca Nationala a Romaniei - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Tasas de cambio de Banca Nationala a Romaniei' de MyPresta.eu."
sidebar:
  label: "Tasas de cambio de Banca Nationala a Romaniei - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Currency rates from Banca Nationala a Romaniei en MyPresta.eu](https://mypresta.eu/modules/administration-tools/currency-rates-from-banca-nationala-a-romaniei.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/currency-rates-from-banca-nationala-a-romaniei/)
>
> ---


# Tasas de cambio de Banca Nationala a Romaniei

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para obtener feeds de datos externos, las cuales son estándar en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo para acceder a sus ajustes.

#### **Ajustes y Opciones**

1.  **Buscar actualizaciones del módulo**

    -   **Qué hace este ajuste:** Este interruptor controla si el módulo verifica periódicamente MyPresta.eu en busca de nuevas versiones o actualizaciones importantes.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (SÍ):* El módulo se conectará ocasionalmente a MyPresta.eu para ver si hay una versión más reciente disponible. Si se encuentra una actualización, podría aparecer una notificación en el back office de PrestaShop, pidiéndole que la descargue e instale.
        -   *Cuando está deshabilitado (NO):* El módulo no buscará actualizaciones automáticamente. Tendrá que revisar manualmente su cuenta de MyPresta.eu para ver si hay nuevas versiones.
    -   **Valor recomendado:** **SÍ**. Siempre se recomienda mantener sus módulos actualizados para beneficiarse de nuevas características, correcciones de errores y mejoras de seguridad.
    -   **Escenario / ejemplo de comerciante:** Desea asegurarse de que su módulo de tasas de cambio siempre esté ejecutando la última versión más estable sin tener que verificar constantemente de forma manual. Habilitar esto le avisará cuando una actualización esté lista.
2.  **Actualizar tasas de cambio**

    -   **Qué hace este ajuste:** Esta es la función principal del módulo. Al hacer clic en este botón, el módulo obtendrá inmediatamente las últimas tasas de cambio de la Banca Naţională a României (BNR) y las aplicará a las monedas configuradas en su tienda PrestaShop.
    -   **Efecto de cambiar este ajuste:** Al hacer clic en este botón, se activa una actualización inmediata de todas las tasas de cambio en su tienda basándose en el feed del BNR. Este es un disparador manual para el proceso de actualización.
    -   **Valor recomendado:** Este es un botón de acción, no un ajuste. Haga clic en él siempre que necesite una actualización inmediata, o después de configurar sus monedas.
    -   **Escenario / ejemplo de comerciante:** Es el comienzo del día de operaciones y desea asegurarse de que todos sus precios reflejen las últimas tasas de cambio antes de que los clientes comiencen a realizar pedidos. Haría clic en este botón.
3.  **URL del Cronjob**

    -   **Qué hace este ajuste:** Este campo muestra una URL única que puede usar para automatizar las actualizaciones de las tasas de cambio. Esta URL está diseñada para ser llamada por un "cron job" en su servidor web, que es una tarea programada que se ejecuta automáticamente a intervalos específicos (por ejemplo, una vez al día, cada hora).
    -   **Efecto de cambiar este ajuste:** Este es un campo de solo visualización. Copiar y configurar esta URL en el programador de cron jobs de su panel de alojamiento asegurará que sus tasas de cambio se actualicen automáticamente sin que tenga que hacer clic manualmente en el botón "Actualizar tasas de cambio".
    -   **Valor recomendado:** Copie esta URL y configure un cron job en su servidor para que se ejecute al menos una vez al día, o con mayor frecuencia si su negocio lo requiere.
    -   **Escenario / ejemplo de comerciante:** Desea que sus tasas de cambio se actualicen automáticamente cada mañana a las 6 AM, incluso cuando no esté en su ordenador. Copiaría esta URL y configuraría un cron job en su servidor de alojamiento para que la ejecute diariamente a las 6 AM.
4.  **Moneda a actualizar**

    -   **Qué hace este ajuste:** Esta lista desplegable le permite seleccionar qué monedas específicas en su tienda PrestaShop deben ser actualizadas por el feed del BNR. El feed del BNR proporciona principalmente tasas contra el RON. El módulo luego las convertirá a la moneda predeterminada de su tienda y luego a otras monedas seleccionadas.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se selecciona una moneda específica:* Solo la tasa de cambio de esa moneda será actualizada por el módulo.
        -   *Cuando se selecciona "Todas las monedas":* El módulo intentará actualizar todas las monedas activas en su tienda PrestaShop utilizando el feed del BNR.
    -   **Valor recomendado:** **Todas las monedas**, a menos que tenga una razón específica para actualizar solo una. Esto asegura que todos sus precios internacionales sean consistentes.
    -   **Escenario / ejemplo de comerciante:** Su tienda acepta EUR, USD y GBP. Desea que todas estas monedas se actualicen diariamente basándose en la conversión del feed del BNR a RON y luego a la moneda predeterminada de su tienda. Seleccionaría "Todas las monedas". Si solo quisiera actualizar EUR por alguna razón, seleccionaría "EUR".

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Buscar actualizaciones del módulo | SÍ | Habilita las comprobaciones automáticas de nuevas versiones del módulo. |
| Configuración del Módulo | Actualizar tasas de cambio | N/A (Botón de Acción) | Activa manualmente una actualización inmediata de todas las tasas de cambio seleccionadas desde el BNR. |
| Configuración del Módulo | URL del Cronjob | N/A (Solo Visualización) | Proporciona la URL para configurar una tarea programada automatizada para las actualizaciones de tasas de cambio. |
| Configuración del Módulo | Moneda a actualizar | Todas las monedas | Determina qué monedas de su tienda recibirán actualizaciones automáticas de tasas desde el BNR. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Mis tasas de cambio no se están actualizando. ¿Qué debo verificar primero?**
R1:

1.  **Actualización Manual:** Vaya a la página de configuración del módulo y haga clic en el botón "Actualizar tasas de cambio". Si esto funciona, el problema probablemente esté en la configuración de su cron job.
2.  **Cron Job:** Verifique que su cron job esté configurado correctamente en su servidor de alojamiento utilizando la "URL del Cronjob" exacta proporcionada por el módulo. Asegúrese de que esté configurado para ejecutarse con la frecuencia deseada.
3.  **Configuración del Módulo:** Verifique que "Todas las monedas" o las monedas específicas que desea actualizar estén seleccionadas en el menú desplegable "Moneda a actualizar".
4.  **Monedas de PrestaShop:** Asegúrese de que las monedas que espera que se actualicen estén activas en su tienda PrestaShop (Internacional > Monedas).
5.  **Conectividad del Servidor:** Asegúrese de que su servidor pueda acceder a sitios web externos (específicamente el feed del BNR). A veces, las reglas del firewall o los problemas de red pueden impedirlo.

**P2: El módulo dice que se actualizó, pero los precios en mi front office no parecen correctos.**
R2:

1.  **Borrar Caché:** PrestaShop utiliza caché. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Esto asegura que su tienda muestre los datos más recientes.
2.  **Caché del Navegador:** Borre la caché y las cookies de su navegador, o intente ver su tienda en una ventana de incógnito/privada para descartar problemas de caché local.
3.  **Selección de Moneda:** Asegúrese de que está viendo los precios en la moneda correcta en el front office.

**P3: ¿Puedo actualizar las tasas con más frecuencia que una vez al día?**
R3: Sí, puede. Al configurar su cron job, puede configurarlo para que se ejecute cada hora, cada pocas horas o en cualquier intervalo compatible con el programador de cron de su proveedor de alojamiento. Solo tenga en cuenta la posible carga del servidor si lo configura para que se ejecute con mucha frecuencia (por ejemplo, cada minuto), aunque para las actualizaciones de moneda, esto rara vez es un problema.

**P4: ¿Qué sucede si el feed del BNR no está disponible temporalmente?**
R4: Si el feed del BNR no está disponible, es probable que el módulo no pueda obtener nuevas tasas. No eliminará ni restablecerá sus tasas existentes; simplemente permanecerán sin cambios hasta que el feed vuelva a estar disponible y se produzca una actualización exitosa. Es posible que vea un mensaje de error en los registros de cron job de su servidor si la actualización falla.

**P5: La moneda predeterminada de mi tienda no es RON. ¿Seguirá funcionando este módulo?**
R5: Sí, absolutamente. El módulo está diseñado para funcionar independientemente de la moneda predeterminada de su tienda. Obtiene las tasas del BNR (que suelen ser contra el RON) y luego las convierte inteligentemente a la moneda predeterminada de su tienda, y posteriormente a cualquier otra moneda activa que haya habilitado para la actualización.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters.

### 4.1 Resumen de la Arquitectura

El módulo "Tasas de cambio de Banca Nationala a Romaniei" es un módulo de PrestaShop sencillo centrado principalmente en una única tarea: obtener y actualizar las tasas de cambio de moneda. Sigue una estructura básica de módulo de PrestaShop, aprovechando la clase `Module` para la instalación y configuración, y `ModuleFrontController` para su funcionalidad de cron job. No introduce clases `ObjectModel` personalizadas ni tablas de base de datos, sino que se basa en la clase `Currency` y la tabla `Configuration` del núcleo de PrestaShop para la configuración. La lógica central implica analizar un feed XML del BNR y actualizar las tasas de cambio existentes.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

Estos controladores están diseñados para ser accedidos externamente, principalmente para la automatización de cron jobs.

-   `controllers/front/cronjob.php`
    -   **Nombre de la clase y clase padre:** `BnrratesCronjobModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este es el punto final dedicado para el cron job de actualización automática de moneda. Cuando se accede, activa la lógica central del módulo para obtener las últimas tasas de cambio del BNR y actualizarlas en la base de datos de PrestaShop. Normalmente devuelve un mensaje simple de éxito o error, adecuado para el registro de cron jobs. No renderiza ninguna salida visual para un navegador.
-   `controllers/front/index.php`
    -   **Nombre de la clase y clase padre:** `BnrratesIndexModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este controlador probablemente sirve como un respaldo o un punto de entrada predeterminado, aunque su función principal podría ser mínima dado el controlador `cronjob.php` explícito. En muchos módulos, un controlador de front `index.php` podría redirigir o mostrar un mensaje simple si se accede directamente sin parámetros específicos. Para este módulo, su uso práctico es probablemente limitado, con `cronjob.php` manejando la interacción principal del front-office.

#### Controladores de Administración de Back-Office

El módulo no implementa ninguna clase `AdminController` personalizada. Toda la configuración del back-office se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

El módulo no introduce ninguna clase personalizada o definiciones de `ObjectModel` en el directorio `classes/`. Interactúa directamente con la clase `Currency` y la clase `Configuration` del núcleo de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

El módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El módulo no incluye ningún archivo CSS personalizado.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `bnrrates/views/admin.tpl`
        -   **Propósito:** Esta plantilla es responsable de renderizar el formulario de configuración del módulo en el Back Office de PrestaShop. Muestra los ajustes como "Buscar actualizaciones del módulo", el botón "Actualizar tasas de cambio", la "URL del Cronjob" y el menú desplegable "Moneda a actualizar".
        -   **Variables:** Normalmente recibiría variables del método `getContent()` del archivo principal del módulo, como los valores actuales de los ajustes de configuración y la URL del cron job generada.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El módulo no crea ninguna tabla SQL personalizada.
    -   Almacena sus ajustes de configuración en la tabla `ps_configuration` de PrestaShop. Las claves de configuración relevantes son:
        -   `BNRRATES_MYPRESTA_UPDATES`: Almacena el valor booleano para verificar las actualizaciones del módulo.
        -   `BNRRATES_CURRENCY_TO_UPDATE`: Almacena el ID de la moneda a actualizar, o un valor especial (por ejemplo, `0` o `all`) para todas las monedas.
        -   `BNRRATES_LAST_UPDATE_TIME`: (Probablemente) Almacena una marca de tiempo de la última actualización exitosa.
        -   `BNRRATES_CRON_TOKEN`: Almacena un token único utilizado en la URL del cron job por seguridad.
-   **Tabla de Hooks Registrados**:
    El módulo utiliza principalmente los hooks `action` para su funcionalidad principal y potencialmente los hooks `display` para notificaciones o contenido específico (aunque no se enumeran explícitamente hooks de visualización de front-office específicos en la información proporcionada, la descripción del módulo menciona "Encabezado, Columnas, Producto o Pie de página" como áreas potenciales, lo que implicaría `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons`, `displayFooter`, etc. Sin embargo, dado el propósito del módulo, estos probablemente serían para mostrar una notificación o estado, no para la funcionalidad principal).

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionModuleInstall` | Durante la instalación del módulo | Registra la configuración del módulo, crea los ajustes predeterminados. |
| `actionModuleUninstall` | Durante la desinstalación del módulo | Limpia la configuración del módulo de `ps_configuration`. |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración | Potencialmente registra CSS/JS para la página de configuración de administración (aunque no hay ninguno presente en este módulo). |
| `displayBackOfficeHeader` | En el encabezado del Back Office | Potencialmente muestra notificaciones de actualización u otro contenido específico de administración. |
| `displayHeader` | En la sección `<head>` del front office | No se utiliza directamente para la funcionalidad principal, pero podría usarse para metaetiquetas o JS/CSS si fuera necesario. |
| `displayLeftColumn` | En la columna izquierda del front office | No se utiliza directamente para la funcionalidad principal, pero podría usarse para mostrar un bloque de moneda. |
| `displayRightColumn` | En la columna derecha del front office | No se utiliza directamente para la funcionalidad principal, pero podría usarse para mostrar un bloque de moneda. |
| `displayProductButtons` | En la página del producto, cerca de añadir al carrito | No se utiliza directamente para la funcionalidad principal, pero podría usarse para información relacionada con la moneda. |
| `displayFooter` | En el pie de página del front office | No se utiliza directamente para la funcionalidad principal, pero podría usarse para información relacionada con la moneda. |

La lógica principal de actualización de moneda se activa al acceder al controlador de front `cronjob.php`, que no es un hook estándar de PrestaShop sino un punto final externo.

## 5. Soporte Oficial y Actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y descargar las últimas versiones del módulo "Tasas de cambio de Banca Nationala a Romaniei", inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y configuración del módulo.

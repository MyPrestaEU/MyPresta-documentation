---
title: "Banco Central de Turquía (TCMB) - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Banco Central de Turquía (TCMB) - tipos de cambio de divisas' de MyPresta.eu."
sidebar:
  label: "Banco Central de Turquía (TCMB) - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Central Bank of Turkey (TCMB) - currency exchange rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/central-bank-of-turkey-tcmb-currency-exchange-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/central-bank-of-turkey-tcmb-currency-exchange-rates/)
>
> ---


# Banco Central de Turquía (TCMB) - tipos de cambio de divisas

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Generalmente se requieren extensiones PHP estándar (cURL, JSON, OpenSSL) para obtener datos externos. Su entorno de alojamiento debe permitir conexiones salientes al sitio web del TCMB.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo para acceder a sus ajustes.

#### Ajustes generales

-   **Habilitar módulo**

    -   **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar la funcionalidad del módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* El módulo comenzará a obtener tipos de cambio y a actualizar los precios de las divisas de su tienda según sus otros ajustes.
        -   *Cuando está deshabilitado:* El módulo cesará todas las operaciones. Los tipos de cambio no se actualizarán automáticamente y sus precios permanecerán estáticos hasta que se cambien manualmente o se vuelva a habilitar el módulo.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo de comerciante:** Si está configurando el módulo por primera vez, habilítelo para comenzar a usar sus funciones. Si necesita detener temporalmente las actualizaciones automáticas (por ejemplo, para mantenimiento), puede deshabilitarlo.
-   **URL CRON**

    -   **Qué hace este ajuste:** Este campo muestra una URL única que, al ser accedida, activa el módulo para obtener los últimos tipos de cambio del TCMB y actualizar los precios de las divisas de su tienda.
    -   **Efecto de cambiar este ajuste:** Este es un campo de solo lectura. Copiar y establecer esta URL en el programador de tareas CRON de su panel de alojamiento automatizará las actualizaciones de tipos.
    -   **Valor recomendado:** Copie esta URL.
    -   **Escenario / ejemplo de comerciante:** Copiará esta URL y la pegará en el panel de control de su alojamiento (por ejemplo, cPanel, Plesk o una interfaz de tareas CRON personalizada) para programar actualizaciones automáticas. Por ejemplo, podría configurarlo para que se ejecute una vez cada 24 horas para garantizar la precisión diaria de los precios.
-   **Margen (%)**

    -   **Qué hace este ajuste:** Le permite agregar un margen porcentual sobre los tipos de cambio oficiales obtenidos del TCMB. Esto se puede usar para cubrir tarifas de transacción, costos de conversión de divisas o simplemente para ajustar su estrategia de precios.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en 0:* Su tienda utilizará los tipos de cambio oficiales exactos proporcionados por el TCMB.
        -   *Cuando se establece en un valor positivo (por ejemplo, 2):* El módulo aumentará el tipo de cambio calculado en ese porcentaje. Por ejemplo, si el tipo oficial es 1 USD = 30 TRY, y usted establece un margen del 2%, el módulo utilizará 1 USD = 30.6 TRY para las conversiones. Esto significa que los productos con precio en USD aparecerán ligeramente más caros en TRY, o viceversa, dependiendo de su divisa base.
    -   **Valor recomendado:** 0 (si desea tipos oficiales exactos) o un pequeño porcentaje positivo (por ejemplo, 1-3%) para cubrir costos.
    -   **Escenario / ejemplo de comerciante:** Si su pasarela de pago cobra una tarifa del 1.5% por las conversiones de divisas, podría establecer un "Margen (%)" del 1.5 para absorber este costo y mantener sus márgenes de beneficio.
-   **Última actualización**

    -   **Qué hace este ajuste:** Este campo de solo lectura muestra la fecha y hora en que el módulo obtuvo y aplicó con éxito las últimas actualizaciones de tipos de cambio.
    -   **Efecto de cambiar este ajuste:** Este campo se actualiza automáticamente después de cada ejecución exitosa de la tarea CRON o actualización manual. Le ayuda a verificar que el módulo funciona correctamente y cuándo se actualizaron los tipos por última vez.
    -   **Valor recomendado:** Monitoree este valor para asegurar actualizaciones regulares.
    -   **Escenario / ejemplo de comerciante:** Después de configurar su tarea CRON, puede verificar este campo para confirmar que las actualizaciones automatizadas se están ejecutando como se esperaba. Si la fecha es antigua, indica un problema con la configuración de su tarea CRON.

#### Actualización manual

-   Botón **Actualizar ahora**
    -   **Qué hace este ajuste:** Este botón le permite activar manualmente el proceso de actualización de tipos de cambio de inmediato, sin esperar la tarea CRON.
    -   **Efecto de cambiar este ajuste:** Al hacer clic en este botón, se obtendrán instantáneamente los últimos tipos del TCMB y se actualizarán los precios de las divisas de su tienda. Esto es útil para pruebas o para actualizaciones urgentes.
    -   **Valor recomendado:** Haga clic cuando necesite una actualización inmediata o para realizar pruebas.
    -   **Escenario / ejemplo de comerciante:** Acaba de lanzar un nuevo producto y quiere asegurarse de que su precio se base en los últimos tipos de cambio antes de que los clientes comiencen a realizar pedidos. Puede hacer clic en "Actualizar ahora" para actualizar todos los tipos al instante.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar módulo | SÍ | Activa/desactiva la funcionalidad principal del módulo. |
| Configuración del módulo | URL CRON | Copiar esta URL | URL para configurar actualizaciones automáticas de tipos de cambio a través de la tarea CRON de su alojamiento. |
| Configuración del módulo | Margen (%) | 0-3% | Agrega un margen porcentual sobre los tipos de cambio oficiales del TCMB para flexibilidad de precios. |
| Configuración del módulo | Última actualización | Monitorear | Muestra la fecha/hora de la última actualización exitosa de tipos de cambio. |
| Configuración del módulo | Botón Actualizar ahora | Hacer clic según sea necesario | Activa manualmente una actualización inmediata de tipos de cambio. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis precios no se actualizan, incluso después de haber configurado el módulo.**
R1: Primero, verifique si la configuración "Habilitar módulo" está en SÍ. Segundo, verifique la configuración de su tarea CRON en su panel de alojamiento. Asegúrese de que la URL CRON sea correcta y que la tarea esté programada para ejecutarse. También puede intentar hacer clic en el botón "Actualizar ahora" en la configuración del módulo para ver si una actualización manual funciona. Si lo hace, el problema probablemente esté en su tarea CRON.

**P2: El campo "Última actualización" muestra una fecha antigua, pero mi tarea CRON está configurada.**
R2: Esto generalmente significa que su tarea CRON no se está ejecutando correctamente o que el módulo está encontrando un error al intentar obtener datos.
-   **Verifique los registros de la tarea CRON:** Muchos proveedores de alojamiento ofrecen registros para las ejecuciones de tareas CRON. Busque cualquier error allí.
-   **Acceso al servidor:** Asegúrese de que su servidor tenga acceso a Internet saliente a `www.tcmb.gov.tr` (el sitio web del Banco Central de Turquía). Los firewalls o las restricciones de red pueden bloquear esto.
-   **Versión de PHP:** Confirme que su versión de PHP está dentro del rango compatible (PHP 5.6 - 8.5).
-   **Reinstalación del módulo:** Como último recurso, intente desinstalar y reinstalar el módulo (después de hacer una copia de seguridad de su tienda) para asegurarse de que todos los archivos estén correctamente en su lugar.

**P3: ¿Puedo actualizar los tipos con más frecuencia que una vez al día?**
R3: Sí, puede configurar su tarea CRON para que se ejecute con más frecuencia (por ejemplo, cada 6 horas, cada hora). Sin embargo, considere el impacto en los recursos de su servidor y la frecuencia real de los cambios de tipos del TCMB. Las actualizaciones diarias suelen ser suficientes para la mayoría de las tiendas de comercio electrónico, ya que los tipos oficiales suelen cambiar una vez al día hábil.

**P4: Tengo varias divisas. ¿Este módulo las actualizará todas?**
R4: Sí, el módulo obtiene los tipos de cambio oficiales de la Lira Turca (TRY) frente a otras divisas principales. Luego utiliza estos tipos para recalcular y actualizar los precios de todas las divisas activas en su tienda PrestaShop basándose en su divisa base y los tipos TRY obtenidos.

**P5: ¿Qué sucede si el sitio web del TCMB está caído o inaccesible?**
R5: Si el módulo no puede conectarse al sitio web del TCMB, normalmente no podrá actualizar los tipos. Sus tipos de cambio existentes permanecerán sin cambios hasta que se pueda establecer una conexión y actualización exitosas. El campo "Última actualización" no cambiará, lo que indica un problema.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo `tcmbrates` está diseñado como un módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para su funcionalidad principal. Su propósito principal es obtener datos externos (tipos de cambio del TCMB) y actualizar los tipos de cambio internos de PrestaShop. Utiliza un controlador frontal para la ejecución de tareas CRON, lo que permite que se active externamente sin interacción directa con el Back Office. La configuración se gestiona a través del método `getContent()` en el archivo principal del módulo, mostrando un formulario simple para los ajustes y un activador de actualización manual.

### 4.2 Controladores (`controllers/`)

El módulo incluye controladores frontales para manejar solicitudes externas, específicamente para la tarea CRON.

-   **Controladores de Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nombre de la clase y clase padre:** `TcmbratesCronjobModuleFrontController` que extiende `ModuleFrontController`.
        -   **Responsabilidad:** Este controlador está diseñado para ser llamado por un programador de tareas CRON externo. Cuando se accede a él, activa la lógica central del módulo para obtener los últimos tipos de cambio del Banco Central de Turquía y actualizar los tipos de cambio en la base de datos de PrestaShop. Normalmente, genera un mensaje de éxito o fracaso.
    -   `controllers/front/index.php`
        -   **Nombre de la clase y clase padre:** `TcmbratesIndexModuleFrontController` que extiende `ModuleFrontController`.
        -   **Responsabilidad:** Este es un marcador de posición o controlador frontal predeterminado, a menudo incluido en los módulos pero no siempre utilizado activamente para funcionalidades específicas. En el contexto de este módulo, probablemente sirve como un recurso alternativo o un punto de entrada simple si no se solicita ningún otro controlador frontal específico. Su función principal suele ser redirigir o mostrar un mensaje genérico.
-   **Controladores de administración de Back-Office**: Ninguno. Toda la administración se gestiona a través del método `getContent()` del módulo.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define clases personalizadas que extiendan `ObjectModel`. Su lógica principal reside dentro del archivo principal del módulo (`cronjob.php`).

### 4.4 Activos de JavaScript (`views/js/`)

No se incluyen archivos JavaScript personalizados en este módulo.

### 4.5 Hojas de estilo CSS (`views/css/`)

No se incluyen archivos CSS personalizados en este módulo.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

El módulo utiliza una única plantilla Smarty para su interfaz de configuración del Back Office.

-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `views/admin.tpl`
        -   **Propósito:** Esta plantilla es renderizada por el método `getContent()` del archivo principal del módulo (`cronjob.php`). Muestra el formulario de configuración del módulo en el Back Office de PrestaShop, incluyendo campos para habilitar el módulo, establecer el margen, mostrar la URL CRON y proporcionar un botón de actualización manual.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**: El módulo no crea ninguna tabla SQL personalizada. Almacena sus ajustes de configuración (por ejemplo, `PS_TCMBRATES_ENABLED`, `PS_TCMBRATES_MARGIN`, `PS_TCMBRATES_LAST_UPDATE`) en la tabla estándar `ps_configuration`. Interactúa directamente con la tabla `ps_currency` de PrestaShop para actualizar los tipos de cambio.
-   **Tabla de Hooks registrados**: El módulo no se registra explícitamente en hooks de visualización estándar como `displayHeader` o `displayFooter` para contenido de front-office. Su interacción principal con el sistema PrestaShop es a través de su lógica interna activada por la tarea CRON o la actualización manual, que luego modifica los datos de divisas existentes.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `install()` | Instalación del módulo | Crea entradas de configuración en `ps_configuration`. |
| `uninstall()` | Desinstalación del módulo | Elimina entradas de configuración de `ps_configuration`. |
| (No hay hooks de visualización explícitos en el front-office) | N/A | El módulo opera en segundo plano para actualizar datos, no para mostrar contenido. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Banco Central de Turquía (TCMB) - tipos de cambio de divisas", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.

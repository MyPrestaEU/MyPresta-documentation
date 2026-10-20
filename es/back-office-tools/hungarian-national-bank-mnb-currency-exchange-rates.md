---
title: "Banco Nacional de Hungría (MNB) - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Banco Nacional de Hungría (MNB) - tipos de cambio de divisas' de MyPresta.eu."
sidebar:
  label: "Banco Nacional de Hungría (MNB) - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Hungarian National Bank (MNB) - currency exchange rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/hungarian-national-bank-mnb-currency-exchange-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/hungarian-national-bank-mnb-currency-exchange-rates/)
>
> ---


# Banco Nacional de Hungría (MNB) - tipos de cambio de divisas

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para la comunicación con API externas, lo cual es común para los módulos de tipo de cambio. Asegúrese de que su entorno de alojamiento las admita.

## 2. Recorrido completo por la configuración (Cada grupo de ajustes por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la pantalla de configuración principal del módulo. Aquí es donde se configura cómo el módulo obtiene y aplica los tipos de cambio.

#### **Ajustes y opciones**

La página de configuración del módulo "Banco Nacional de Hungría (MNB) - tipos de cambio de divisas" normalmente presentará un formulario con varias opciones para controlar su comportamiento. Aunque los nombres específicos de los campos pueden variar ligeramente, la funcionalidad principal gira en torno a la habilitación del proceso de actualización y, potencialmente, su programación.

1. **Habilitar actualizaciones de tipo de cambio del MNB**

   - **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar las actualizaciones automáticas de tipos de cambio del Banco Nacional de Hungría.
   - **Efecto de cambiar este ajuste:**
     - *Cuando está habilitado (SÍ):* El módulo obtendrá periódicamente los últimos tipos de cambio del MNB y los aplicará a las monedas configuradas en su tienda. Esto garantiza que sus precios estén siempre actualizados.
     - *Cuando está deshabilitado (NO):* El módulo dejará de obtener y aplicar los tipos de cambio del MNB. Los tipos de cambio de su tienda permanecerán como se establecieron por última vez (ya sea manualmente o por el módulo antes de ser deshabilitado).
   - **Valor recomendado:** SÍ
   - **Escenario / ejemplo de comerciante:** Si desea que su tienda refleje automáticamente los últimos tipos de cambio del MNB para HUF, EUR, USD, etc., debe habilitar este ajuste. Si prefiere gestionar las tarifas manualmente o utilizar un sistema diferente, lo deshabilitaría.
2. **URL de Cron Job (para actualizaciones automáticas)**

   - **Qué hace este ajuste:** Este campo muestra una URL única que puede utilizar para configurar un "cron job" en su servidor web. Un cron job es una tarea programada que le indica a su servidor que visite esta URL a intervalos regulares, lo que activa el módulo para actualizar automáticamente los tipos de cambio.
   - **Efecto de cambiar este ajuste:** Este no es un ajuste que se cambie directamente, sino una URL que se copia.
     - *Cuando el cron job está configurado:* Su servidor llamará periódicamente a esta URL, y el módulo ejecutará su proceso de actualización en segundo plano sin que usted tenga que hacer nada.
     - *Cuando el cron job NO está configurado:* Tendría que visitar manualmente esta URL en su navegador (o hacer clic en un botón "Ejecutar actualización ahora" si está disponible) para activar una actualización. Esto no se recomienda para un uso regular.
   - **Valor recomendado:** Copie esta URL y configure un cron job en su panel de alojamiento (por ejemplo, cPanel, Plesk o línea de comandos del servidor) para que se ejecute al menos una vez al día, o con mayor frecuencia si su negocio lo requiere.
   - **Escenario / ejemplo de comerciante:** Desea que sus tipos de cambio se actualicen todas las mañanas a las 3 AM. Copiaría esta URL, iría a la sección "Cron Jobs" de su panel de control de alojamiento y crearía un nuevo cron job que ejecute `wget -O /dev/null -q "SU_URL_DE_CRON_JOB_AQUÍ"` (o un comando similar) diariamente a las 3 AM.
3. **Hora de la última actualización** (Visualización informativa)

   - **Qué hace este ajuste:** Este es un campo de solo visualización que le muestra cuándo se actualizaron con éxito los tipos de cambio por última vez por el módulo.
   - **Efecto de cambiar este ajuste:** Este no es un ajuste configurable. Simplemente proporciona información sobre la actividad del módulo.
   - **Valor recomendado:** N/A (informativo)
   - **Escenario / ejemplo de comerciante:** Puede verificar rápidamente esta marca de tiempo para confirmar que su cron job se está ejecutando correctamente y que los tipos de cambio se están actualizando como se esperaba. Si la hora es antigua, indica un problema con la configuración de su cron job.

#### **Tabla de referencia rápida de configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar actualizaciones de tipo de cambio del MNB | SÍ | Activa/desactiva la obtención y aplicación automática de los tipos de cambio del MNB. |
| Configuración del módulo | URL de Cron Job | N/A (Copiar y configurar) | URL para configurar una tarea programada (cron job) para actualizaciones automáticas de tipos de cambio. |
| Configuración del módulo | Hora de la última actualización | N/A (Informativo) | Muestra la marca de tiempo de la última actualización exitosa del tipo de cambio. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis tipos de cambio no se están actualizando. ¿Qué debo hacer?**
R1:

1. **Verifique "Habilitar actualizaciones de tipo de cambio del MNB":** Asegúrese de que este ajuste esté configurado en SÍ en la configuración del módulo.
2. **Verifique la configuración del Cron Job:** La razón más común para las no actualizaciones es un cron job configurado incorrectamente.
   - Asegúrese de haber copiado la "URL de Cron Job" exacta del módulo.
   - Verifique su panel de control de alojamiento (cPanel, Plesk, etc.) para la configuración del cron job.
   - Confirme que el comando es correcto (por ejemplo, `wget -O /dev/null -q "SU_URL_DE_CRON_JOB"`).
   - Verifique la programación (por ejemplo, `* * * * *` para cada minuto, `0 3 * * *` para las 3 AM diarias).
   - Busque cualquier registro de errores relacionado con el cron job en su panel de alojamiento.
3. **Verifique "Hora de la última actualización":** Si esta marca de tiempo es antigua, confirma que el cron job no se está ejecutando.
4. **Conectividad del servidor:** Asegúrese de que su servidor pueda realizar conexiones salientes a sitios web externos (como la API del MNB). A veces, los firewalls o la configuración de seguridad pueden bloquear esto. Póngase en contacto con su proveedor de alojamiento si sospecha esto.

**P2: He habilitado el módulo, pero algunas monedas no se están actualizando.**
R2:

1. **Activación de la moneda:** Vaya a **Internacional > Divisas** en su Back Office de PrestaShop. Asegúrese de que las monedas que espera que se actualicen estén habilitadas (activas). El módulo solo actualiza las monedas activas.
2. **Soporte del MNB:** El MNB proporciona tipos de cambio para monedas específicas. Si una moneda no es compatible con el MNB, el módulo no puede actualizarla. Es posible que deba establecer manualmente los tipos de cambio para dichas monedas o utilizar otro módulo para ellas.

**P3: Mi tema personalizado no muestra los precios correctamente después de la actualización.**
R3: Este módulo actualiza principalmente los *datos* (tipos de cambio) en la base de datos de su PrestaShop. No afecta directamente cómo su tema *muestra* los precios. Si ve problemas de visualización:

1. **Borrar caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty").
2. **Personalización del tema:** Si su tema tiene una lógica de visualización de precios muy personalizada, podría estar interfiriendo. Consulte la documentación de su tema o póngase en contacto con el desarrollador de su tema.
3. **Caché del navegador:** Pida a sus clientes que borren la caché de su navegador o que prueben con un navegador diferente para descartar problemas de caché del lado del cliente.

**P4: ¿Puedo anular manualmente un tipo de cambio después de que el módulo lo actualice?**
R4: Sí, puede. Después de que el módulo se ejecuta, los tipos de cambio se almacenan en la base de datos de PrestaShop. Puede ir a **Internacional > Divisas**, editar una moneda específica y ajustar manualmente su tipo de cambio. Sin embargo, tenga en cuenta que la próxima vez que se ejecute el cron job, el módulo sobrescribirá sus cambios manuales con los últimos datos del MNB. Si necesita un control manual permanente sobre una moneda específica, podría considerar deshabilitar las actualizaciones del módulo para esa moneda (si el módulo ofrece una configuración tan granular, lo cual es raro) o deshabilitar el módulo por completo y gestionar todas las tarifas manualmente.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Banco Nacional de Hungría (MNB) - tipos de cambio de divisas" sigue una arquitectura de módulo estándar de PrestaShop, centrándose principalmente en el procesamiento en segundo plano. Aprovecha la clase `Module` de PrestaShop para la instalación y configuración, y `ModuleFrontController` para manejar la ejecución del cron job. La lógica central implica realizar una solicitud HTTP a la API oficial de tipos de cambio del MNB (probablemente un feed XML), analizar la respuesta y luego actualizar la tabla `ps_currency` en la base de datos de PrestaShop.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `mnbrates/controllers/front/cronjob.php`
    - **Nombre de la clase y clase padre**: `MnbratesCronjobModuleFrontController` que extiende `ModuleFrontController`
    - **Responsabilidad**: Este controlador es el punto de entrada para el cron job programado. Cuando se accede a su URL (por ejemplo, `sutienda.com/module/mnbrates/cronjob`), activa la lógica central del módulo para obtener y actualizar los tipos de cambio. Normalmente maneja la solicitud HTTP, llama al método de actualización del módulo principal y devuelve un mensaje simple de éxito/fracaso o ninguna salida (para una ejecución silenciosa del cron).
  - `mnbrates/controllers/front/index.php`
    - **Nombre de la clase y clase padre**: `MnbratesIndexModuleFrontController` que extiende `ModuleFrontController`
    - **Responsabilidad**: Este es un controlador de marcador de posición estándar que a menudo se incluye en los módulos. En muchos casos, simplemente podría redirigir a la página de inicio o servir como un respaldo. Para este módulo específico, su propósito principal es probablemente evitar la lista de directorios si alguien intenta acceder a `/module/mnbrates/` directamente, o podría ser un archivo vestigial. Es poco probable que contenga lógica de negocio central para las actualizaciones de tipos de cambio.
- **Controladores de administración de Back-Office**:

  - No se identifican controladores de administración dedicados (`controllers/admin/`). Esto significa que toda la configuración del back-office se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

No se identifican clases o modelos personalizados en el directorio `classes/`. Esto sugiere que el módulo probablemente realiza sus operaciones directamente dentro del archivo principal del módulo `cronjob.php`, utilizando potencialmente el `ObjectModel` `Currency` principal de PrestaShop para actualizar los tipos de cambio.

### 4.4 Activos de JavaScript (`views/js/`)

No se identifican archivos JavaScript. Esto confirma la naturaleza centrada en el backend del módulo, sin componentes interactivos de front-office o formularios complejos de back-office que requieran JS dinámico.

### 4.5 Hojas de estilo CSS (`views/css/`)

No se identifican archivos CSS. Esto indica que el módulo no introduce ningún estilo personalizado para el front-office o el back-office. La configuración del back-office heredará los estilos del tema de administración predeterminado de PrestaShop.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - `mnbrates/views/admin.tpl`
    - **Propósito**: Esta plantilla es renderizada por el método `getContent()` del archivo principal del módulo (`mnbrates/cronjob.php`). Define la estructura y el contenido de la página de configuración del módulo en el Back Office de PrestaShop. Contendrá los elementos del formulario para habilitar/deshabilitar las actualizaciones, mostrar la URL del cron job y mostrar la marca de tiempo de la última actualización.
- **Plantillas de hook (`views/templates/hook/`)**: Ninguna identificada.
- **Plantillas de front-office (`views/templates/front/`)**: Ninguna identificada.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:

  - El módulo no crea tablas SQL personalizadas. Interactúa con la tabla principal `ps_currency` de PrestaShop para actualizar el campo `conversion_rate` de cada moneda.
  - Los ajustes de configuración (como `PS_MNBRATES_ENABLED`, `PS_MNBRATES_LAST_UPDATE`) se almacenan en la tabla `ps_configuration`.
- **Tabla de Hooks registrados**:
  Es probable que el módulo registre hooks durante su método `install()`. Dada su funcionalidad, el hook más crucial es para el cron job, que es manejado por un controlador frontal. Otros hooks podrían ser para fines informativos o para garantizar la compatibilidad.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza en la sección `<head>` de todas las páginas del front-office. | Poco probable que se use para la lógica central, posiblemente para agregar una metaetiqueta o un JS/CSS muy simple (aunque no se identificó ninguno). |
| `displayRightColumn` | Se renderiza en la columna derecha de las páginas donde está disponible. | Poco probable que se use para la lógica central, posiblemente para un pequeño bloque informativo si el módulo tuviera un componente de front-office. |
| `displayLeftColumn` | Se renderiza en la columna izquierda de las páginas donde está disponible. | Similar a `displayRightColumn`. |
| `displayFooter` | Se renderiza en el pie de página de todas las páginas del front-office. | Similar a `displayHeader`, pero en la parte inferior. |
| `displayProductExtraContent` | Renderiza contenido adicional en la página del producto. | Poco probable para este módulo. |
| `actionModuleInstall` | Se ejecuta cuando se instala un módulo. | Registra los hooks necesarios y establece los valores de configuración predeterminados. |
| `actionModuleUninstall` | Se ejecuta cuando se desinstala un módulo. | Limpia los valores de configuración y anula el registro de los hooks. |
| `actionModuleUpdate` | Se ejecuta cuando se actualiza un módulo. | Maneja los cambios de esquema o las migraciones de configuración entre versiones. |
| (Implícito) `frontController` dispatch | Cuando se accede a `mnbrates/controllers/front/cronjob.php`. | Activa la lógica principal de actualización del tipo de cambio. Este es el "hook" principal para el cron job. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Banco Nacional de Hungría (MNB) - tipos de cambio de divisas", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo se dedica a garantizar que su módulo funcione de manera óptima y que su tienda se beneficie de las características y la compatibilidad más actuales.

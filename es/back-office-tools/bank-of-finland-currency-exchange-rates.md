---
title: "Banco de Finlandia - tipos de cambio de divisas - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Banco de Finlandia - tipos de cambio de divisas' de MyPresta.eu."
sidebar:
  label: "Banco de Finlandia - tipos de cambio de divisas - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Bank of Finland - currency exchange rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-finland-currency-exchange-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/bank-of-finland-currency-exchange-rates/)
>
> ---


# Banco de Finlandia - tipos de cambio de divisas

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para obtener datos externos. Su entorno de alojamiento también debe admitir tareas CRON para actualizaciones automatizadas.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" para acceder a la configuración del módulo. Aquí es donde definirá cómo se actualizan y aplican los tipos de cambio.

#### **1. URL CRON**

- **Qué hace esta configuración:** Esta es una dirección web (URL) única que, al ser visitada, activa el módulo para obtener los últimos tipos de cambio del Banco de Finlandia y actualizarlos en su tienda PrestaShop.
- **Efecto de cambiar esta configuración:** No puede cambiar esta URL directamente. Es generada por el módulo. Esta URL es crucial para configurar una tarea automatizada (tarea CRON) en su servidor web.
- **Valor recomendado:** Copie esta URL exactamente como aparece.
- **Escenario / ejemplo de comerciante:** Proporcionará esta URL a su proveedor de alojamiento o la utilizará en su panel de control de alojamiento (por ejemplo, cPanel, Plesk) para configurar una tarea CRON. Esto asegura que sus tipos de cambio se actualicen automáticamente, por ejemplo, una vez al día, sin que tenga que hacer clic manualmente en nada.

#### **2. Instrucciones de configuración de la tarea CRON**

- **Qué hace esta configuración:** Esta sección proporciona instrucciones sobre cómo configurar la tarea CRON utilizando la URL proporcionada anteriormente. Una tarea CRON es un programador de tareas basado en tiempo en sistemas operativos tipo Unix. Le permite programar comandos o scripts para que se ejecuten automáticamente a intervalos especificados.
- **Efecto de cambiar esta configuración:** Esta es una sección informativa; no cambia nada aquí. Seguir estas instrucciones correctamente asegura que sus tipos de cambio se actualicen automáticamente.
- **Valor recomendado:** Lea y siga estas instrucciones cuidadosamente.
- **Escenario / ejemplo de comerciante:** El panel de control de su proveedor de alojamiento (como cPanel) tendrá una sección "Tareas Cron" o "Tareas Programadas". Normalmente, añadirá una nueva tarea cron, especificará la frecuencia (por ejemplo, una vez al día a las 3 AM) y pegará la URL CRON en el campo de comando, a menudo precedida por `wget -q -O /dev/null`.

#### **3. Margen (%)**

- **Qué hace esta configuración:** Esto le permite añadir un margen porcentual a los tipos de cambio obtenidos. Por ejemplo, si el tipo oficial es 1 EUR = 1.10 USD, y usted establece un margen del 2%, el módulo utilizará 1 EUR = 1.078 USD (1.10 \* 0.98) o 1 EUR = 1.122 USD (1.10 \* 1.02) dependiendo de cómo el módulo aplique el margen (generalmente para proteger contra fluctuaciones, por lo que podría aumentar ligeramente el precio en moneda extranjera).
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en 0:* Los tipos de cambio se actualizarán exactamente como los proporciona el Banco de Finlandia.
  - *Cuando se establece en un valor positivo (por ejemplo, 2):* El módulo ajustará el tipo de cambio en este porcentaje. Esto puede ayudar a cubrir tarifas de transacción, costos de conversión de moneda o simplemente proporcionar un pequeño colchón contra movimientos desfavorables del tipo, asegurando que sus márgenes de beneficio se mantengan.
- **Valor recomendado:** Empiece con 0. Si experimenta problemas de rentabilidad debido a fluctuaciones monetarias o tarifas de conversión, considere un pequeño margen como 1-3%.
- **Escenario / ejemplo de comerciante:** Si vende un producto por 100 EUR y el tipo de cambio es 1 EUR = 1.10 USD, el producto sería 110 USD. Si establece un margen del 2%, el módulo podría calcular el tipo como 1 EUR = 1.078 USD, haciendo que el producto cueste 107.80 USD. Esto le da un pequeño colchón.

#### **4. Última actualización**

- **Qué hace esta configuración:** Muestra la fecha y hora en que los tipos de cambio fueron actualizados por última vez con éxito por el módulo.
- **Efecto de cambiar esta configuración:** Este es un campo informativo y no se puede cambiar directamente. Sirve como verificación de que su tarea CRON está funcionando correctamente y el módulo está actualizando activamente los tipos.
- **Valor recomendado:** Esto debería mostrar una fecha y hora recientes, idealmente dentro de las últimas 24 horas si su tarea CRON se ejecuta diariamente.
- **Escenario / ejemplo de comerciante:** Si configura su tarea CRON para que se ejecute diariamente a las 3 AM, debería ver que la marca de tiempo "Última actualización" cambia para reflejar las 3 AM del día actual (o poco después) cada mañana. Si no se actualiza, indica un problema con la configuración de su tarea CRON.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | URL CRON | Copiar exactamente | URL única para activar las actualizaciones de tipos a través de una tarea CRON. |
| Configuración del Módulo | Instrucciones de configuración de la tarea CRON | Leer cuidadosamente | Guía para configurar actualizaciones automatizadas en su servidor. |
| Configuración del Módulo | Margen (%) | 0 (o 1-3% si es necesario) | Añade un porcentaje de amortiguación a los tipos de cambio para proteger los márgenes de beneficio. |
| Configuración del Módulo | Última actualización | N/A (informativo) | Muestra la marca de tiempo de la última actualización exitosa del tipo. |

## 3. Resolución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Mis tipos de cambio no se están actualizando. ¿Qué debo hacer?**
R1: Esto casi siempre está relacionado con la configuración de la tarea CRON.
1.  **Verifique la marca de tiempo "Última actualización":** Vaya a la página de configuración del módulo. Si esta fecha es antigua, su tarea CRON no se está ejecutando.
2.  **Verifique la configuración de la tarea CRON:** Inicie sesión en su panel de control de alojamiento (por ejemplo, cPanel, Plesk). Navegue a la sección "Tareas Cron" o "Tareas Programadas".
    \* Asegúrese de que la URL CRON que copió del módulo sea exactamente la que está en el comando de su tarea CRON.
    \* Asegúrese de que el comando esté formateado correctamente (por ejemplo, `wget -q -O /dev/null "SU_URL_CRON_AQUI"`).
    \* Confirme que la frecuencia esté configurada como desea (por ejemplo, diariamente).
    \* Verifique la dirección de correo electrónico asociada con la tarea CRON (si la hay) para ver si hay mensajes de error.
3.  **Ejecute manualmente la URL CRON:** Copie la URL CRON de la configuración del módulo y péguela directamente en la barra de direcciones de su navegador web. Esto debería activar una actualización. Si funciona, el problema es definitivamente con la configuración de la tarea CRON de su servidor. Si no funciona, podría haber un problema del lado del servidor que impida que el módulo obtenga datos (por ejemplo, firewall, cURL no habilitado).

**P2: Mis precios en monedas extranjeras parecen ligeramente incorrectos, incluso después de las actualizaciones.**
R2: Verifique la configuración "Margen (%)" en la configuración del módulo. Si tiene un margen establecido (por ejemplo, 2%), el módulo ajustará intencionalmente el tipo de cambio en ese porcentaje. Si desea tipos oficiales exactos, establezca el margen en 0. Además, asegúrese de que su moneda base en PrestaShop (Localización > Monedas) esté configurada correctamente en EUR si principalmente trabaja con tipos del Banco de Finlandia.

**P3: ¿Este módulo funciona con todas las monedas?**
R3: El módulo obtiene datos de referencia oficiales del Banco de Finlandia, que principalmente proporciona tipos frente al Euro. Sin embargo, calcula inteligentemente tipos cruzados para monedas que no son el euro. Esto significa que si el Banco de Finlandia proporciona EUR a USD y EUR a GBP, el módulo puede derivar el tipo de USD a GBP. Siempre que el Banco de Finlandia proporcione un tipo para una moneda frente al Euro, el módulo debería poder actualizarla.

**P4: ¿Necesito borrar mi caché de Smarty después de las actualizaciones?**
R4: No, normalmente no. Este módulo actualiza los valores de la base de datos (tipos de cambio). La caché de Smarty de PrestaShop afecta principalmente la compilación de plantillas y el contenido estático. Los cambios en los tipos de cambio son dinámicos y deberían reflejarse inmediatamente en los precios de su tienda sin necesidad de borrar la caché.

**P5: Mi tema personalizado no muestra los precios actualizados correctamente.**
R5: El módulo actualiza los tipos de cambio subyacentes en la base de datos de PrestaShop. El selector de moneda de su tema y la lógica de visualización de precios deberían recoger automáticamente estos tipos actualizados. Si no es así, es probable que sea un problema específico del tema en lugar de un problema del módulo.
1.  **Verifique los tipos internos de PrestaShop:** Vaya a **Localización > Monedas** en su Back Office. Verifique la columna "Tipo de cambio" para sus monedas que no son EUR. Si estos tipos se actualizan correctamente, el módulo está funcionando.
2.  **Contacte a su desarrollador de temas:** Si los tipos son correctos en el Back Office pero no en el front-end, su tema podría tener una caché personalizada o una forma específica de manejar la visualización de la moneda que necesita la atención del desarrollador del tema.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Visión General de la Arquitectura

El módulo "Banco de Finlandia - tipos de cambio de divisas" (`sprates`) es un módulo ligero de PrestaShop diseñado para una única tarea crítica: automatizar las actualizaciones de los tipos de cambio de divisas. Utiliza un controlador de front-office para exponer un punto final invocable por CRON, que, al ser accedido, obtiene datos XML del Banco de Finlandia, los analiza y actualiza la tabla `ps_currency`. El módulo sigue un patrón MVC estándar de PrestaShop para su configuración y el disparador de front-end.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `sprates/controllers/front/cronjob.php`
  - **Nombre de la clase y clase padre:** `SpratesCronjobModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este es el controlador principal para el proceso de actualización automatizado. Responde a las solicitudes realizadas a la URL CRON. Tras su ejecución, realiza lo siguiente:
    1. Obtiene datos XML del feed oficial de tipos de cambio del Banco de Finlandia.
    2. Analiza el XML para extraer los tipos de cambio basados en EUR.
    3. Calcula los tipos cruzados para monedas que no son EUR si es necesario.
    4. Aplica el margen configurado.
    5. Actualiza la columna `exchange_rate` en la tabla `ps_currency` para todas las monedas activas en PrestaShop.
    6. Actualiza la marca de tiempo `last_update` en la configuración del módulo.
    7. Muestra un mensaje simple de éxito o error (a menudo suprimido por `wget -q -O /dev/null`).
- `sprates/controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `SpratesIndexModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este es un controlador de marcador de posición, típicamente utilizado para evitar la lista de directorios o proporcionar una acción predeterminada si no se utiliza el despacho principal del módulo. En el contexto de este módulo, probablemente sirve como un respaldo o una práctica estándar de PrestaShop para módulos con controladores de front-end, pero la lógica principal reside en `cronjob.php`.

#### Controladores de Administración de Back-Office

Este módulo no utiliza ningún controlador de administración personalizado dedicado. Toda la configuración se maneja a través del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no define ninguna clase o modelo personalizado dentro del directorio `classes/`. Interactúa directamente con las clases principales de PrestaShop `Currency` y `Configuration` para gestionar los tipos de cambio y la configuración del módulo.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de Estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - `sprates/views/admin.tpl`
    - **Propósito:** Esta plantilla renderiza el formulario de configuración del módulo en el Back Office de PrestaShop. Muestra la URL CRON, las instrucciones de configuración, el campo de entrada del margen y la marca de tiempo de la última actualización. Utiliza elementos de formulario de ayuda estándar de PrestaShop.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

El módulo no crea ninguna tabla de base de datos personalizada. Interactúa con las tablas existentes de PrestaShop:

- `ps_currency`: Actualiza la columna `exchange_rate` para las monedas activas.
- `ps_configuration`: Almacena configuraciones específicas del módulo, como `SP_RATES_MARGIN` (para el porcentaje de margen) y `SP_RATES_LAST_UPDATE` (para la marca de tiempo de la última actualización).

#### Tabla de Hooks Registrados

Este módulo no registra ningún hook de visualización tradicional (por ejemplo, `displayHeader`, `displayFooter`) ya que no tiene componentes visuales en el front-office. Su mecanismo principal de "hook" es la tarea CRON, que activa su controlador de front-end.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionModuleInstall` | Durante la instalación del módulo | Establece los valores de configuración predeterminados. |
| `actionModuleUninstall` | Durante la desinstalación del módulo | Limpia los valores de configuración. |
| (Tarea CRON a través del Controlador Frontal) | Programado por el servidor (por ejemplo, diariamente) | Obtiene, calcula y actualiza los tipos de cambio de divisas. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Banco de Finlandia - tipos de cambio de divisas", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta que pueda tener.

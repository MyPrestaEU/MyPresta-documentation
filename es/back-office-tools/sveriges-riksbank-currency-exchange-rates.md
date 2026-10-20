---
title: "Sveriges Riksbank - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Sveriges Riksbank - tipos de cambio de divisas' de MyPresta.eu."
sidebar:
  label: "Sveriges Riksbank - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Sveriges Riksbank - currency exchange rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/sveriges-riksbank-currency-exchange-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/sveriges-riksbank-currency-exchange-rates/)
>
> ---


# Sveriges Riksbank - tipos de cambio de divisas

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para las llamadas a API externas, que son estándar en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" para acceder a la página de configuración principal del módulo. Aquí es donde configurará cómo el módulo obtiene y aplica los tipos de cambio.

#### **Configuración General**

- **Habilitar Módulo:**

  - **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar la funcionalidad del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El módulo estará activo, y su tarea cron y la lógica de actualización de tasas funcionarán de acuerdo con sus otras configuraciones.
    - *Cuando está deshabilitado:* El módulo estará inactivo y no se producirán actualizaciones automáticas de tasas. Sus tipos de cambio permanecerán como se establecieron por última vez (ya sea manualmente o por una actualización anterior del módulo).
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo del comerciante:** Si solo está configurando o solucionando problemas, podría deshabilitarlo temporalmente. Para un funcionamiento normal, siempre debe estar habilitado.
- **URL de la Tarea Cron:**

  - **Qué hace este ajuste:** Muestra una URL única que debe configurar como una "tarea cron" en el servidor de su alojamiento web. Una tarea cron es una tarea programada que le indica a su servidor que visite esta URL a intervalos regulares (por ejemplo, una vez al día). Cuando se visita la URL, el módulo obtiene y actualiza automáticamente los tipos de cambio.
  - **Efecto de cambiar este ajuste:** No puede cambiar esta URL directamente. Es generada por el módulo. El efecto proviene de *usar* esta URL en su panel de alojamiento.
    - *Cuando se configura correctamente como una tarea cron:* Sus tipos de cambio se actualizarán automáticamente con la frecuencia especificada (por ejemplo, diariamente).
    - *Cuando no se configura como una tarea cron:* Las tasas no se actualizarán automáticamente. Tendría que visitar manualmente esta URL en su navegador para activar una actualización, lo que anula el propósito de la automatización.
  - **Valor recomendado:** Copie esta URL y configúrela como una tarea cron diaria en su servidor.
  - **Escenario / ejemplo del comerciante:** Normalmente, lo configuraría para que se ejecute una vez cada 24 horas para asegurarse de que sus tasas estén siempre actualizadas. Consulte la documentación o el soporte de su proveedor de alojamiento para saber cómo configurar una tarea cron (a menudo se encuentra en cPanel o Plesk en "Tareas Cron" o "Tareas Programadas").

#### **Configuración específica de la moneda**

Debajo de la configuración general, verá una lista de todas las monedas activas en su tienda PrestaShop. Para cada moneda, puede configurar ajustes específicos:

- **Nombre de la moneda (por ejemplo, Euro, Dólar estadounidense):**

  - **Qué hace este ajuste:** Identifica la moneda que está configurando.
  - **Efecto de cambiar este ajuste:** Esto es solo una etiqueta; no puede cambiar el nombre de la moneda aquí.
- **Recargo / Descuento (%):**

  - **Qué hace este ajuste:** Le permite aplicar un ajuste porcentual al tipo de cambio obtenido de Sveriges Riksbank.
    - Un **valor positivo (recargo)** aumenta el tipo de cambio, lo que significa que obtiene más de la moneda extranjera por su moneda base. Esto es útil para cubrir tarifas de transacción o aumentar su margen de beneficio.
    - Un **valor negativo (descuento)** disminuye el tipo de cambio, lo que significa que obtiene menos de la moneda extranjera. Esto podría usarse con fines promocionales o si desea ofrecer una tasa ligeramente mejor a los clientes.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 0:* El tipo de cambio será exactamente el que proporciona Sveriges Riksbank.
    - *Cuando se establece en 2 (recargo):* Si la tasa del Riksbank es 1 EUR = 10 SEK, con un recargo del 2%, su tienda utilizará 1 EUR = 10.20 SEK. Esto significa que cuando un cliente paga en EUR, usted recibe efectivamente más SEK.
    - *Cuando se establece en -1 (descuento):* Si la tasa del Riksbank es 1 EUR = 10 SEK, con un descuento del 1%, su tienda utilizará 1 EUR = 9.90 SEK. Esto significa que cuando un cliente paga en EUR, obtiene una tasa ligeramente mejor.
  - **Valor recomendado:** Depende de su estrategia comercial. Una práctica común es agregar un pequeño recargo (por ejemplo, 1-3%) para cubrir las tarifas de la pasarela de pago y los costos de conversión de moneda.
  - **Escenario / ejemplo del comerciante:** Si su procesador de pagos cobra una tarifa del 1.5% por convertir EUR a SEK, podría establecer un recargo del 2% para EUR para asegurarse de cubrir esa tarifa y retener una pequeña ganancia.

#### **Botón Guardar**

- **Qué hace este botón:** Guarda todos los cambios que ha realizado en la página de configuración.
- **Efecto de hacer clic en este botón:** Se aplicarán sus nuevas configuraciones (habilitar/deshabilitar, porcentajes de recargo/descuento). La próxima vez que se ejecute la tarea cron, o que active manualmente una actualización, se utilizarán estas nuevas configuraciones.
- **Acción recomendada:** Siempre haga clic en "Guardar" después de realizar cualquier cambio.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Habilitar Módulo | SÍ | Activa/desactiva las actualizaciones automáticas de tasas del módulo. |
| Configuración del Módulo | URL de la Tarea Cron | (URL generada) | URL que se configurará como una tarea programada en su servidor para actualizaciones automáticas. |
| Configuración del Módulo | Recargo / Descuento (%) (por moneda) | 0 | Ajusta el tipo de cambio obtenido en un porcentaje para cubrir tarifas o gestionar ganancias. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis tipos de cambio no se actualizan automáticamente. ¿Qué debo verificar?**
R1:

- **¿Está habilitado el módulo?** Vaya a Módulos > Gestor de módulos > Sveriges Riksbank - tipos de cambio de divisas y asegúrese de que "Habilitar Módulo" esté configurado en SÍ.
- **¿Está configurada correctamente la tarea cron?** Vuelva a verificar su panel de control de alojamiento (cPanel, Plesk, etc.) para asegurarse de que la URL de la tarea cron proporcionada en la configuración del módulo esté correctamente ingresada y programada para ejecutarse. Asegúrese de que el comando sea correcto (por ejemplo, `wget -q -O /dev/null "SU_URL_CRON"` o `curl -s "SU_URL_CRON"`).
- **¿Hay algún error al visitar manualmente la URL de la tarea cron?** Intente pegar la URL de la tarea cron en su navegador. Si ve un mensaje de error, podría indicar un problema del servidor o un problema con la conexión del módulo a Sveriges Riksbank.
- **Conectividad del servidor:** Asegúrese de que su servidor pueda realizar conexiones salientes a sitios web externos (la API de Sveriges Riksbank). A veces, los firewalls pueden bloquear esto. Póngase en contacto con su proveedor de alojamiento si sospecha esto.

**P2: He actualizado los porcentajes de recargo, pero los precios en mi tienda no han cambiado.**
R2:

- **¿Ha guardado la configuración?** Siempre haga clic en el botón "Guardar" después de realizar cambios en la página de configuración del módulo.
- **¿Se ha ejecutado la tarea cron desde que guardó?** Los cambios solo surtirán efecto después de que el módulo realice su próximo ciclo de actualización. Puede esperar a su tarea cron programada o activar manualmente una actualización visitando la URL de la tarea cron en su navegador.
- **Borrar la caché de PrestaShop:** A veces, la caché de PrestaShop puede retener datos antiguos. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la parte superior derecha.

**P3: Los tipos de cambio parecen incorrectos o no son los que espero de Sveriges Riksbank.**
R3:

- **Verifique su configuración de Recargo/Descuento:** Asegúrese de no haber establecido accidentalmente un porcentaje de recargo o descuento alto que esté distorsionando las tasas.
- **Verifique las tasas oficiales de Sveriges Riksbank:** Compare las tasas en su tienda (después de una actualización) con las tasas oficiales publicadas en el sitio web de Sveriges Riksbank para ver si hay una discrepancia.
- **Moneda base del módulo:** El módulo obtiene las tasas en relación con SEK. Asegúrese de que la moneda predeterminada de su PrestaShop esté configurada correctamente si espera una base diferente.

**P4: ¿Funcionará este módulo con mi tema personalizado?**
R4: Sí, este módulo opera completamente en segundo plano y no agrega ningún elemento visual ni modifica ninguna plantilla en el front office. Por lo tanto, es totalmente compatible con cualquier tema de PrestaShop, personalizado o predeterminado. Su función es puramente basada en datos (actualización de tipos de cambio).

**P5: ¿Cómo agrego una nueva moneda a mi tienda para que este módulo pueda gestionarla?**
R5:

1. Vaya a **Internacional > Monedas** en su Back Office de PrestaShop.
2. Haga clic en "Añadir nueva moneda" (o el icono de más).
3. Rellene los detalles de la nueva moneda (código ISO, símbolo, tipo de cambio en relación con su moneda predeterminada).
4. Una vez agregada y habilitada, la nueva moneda aparecerá en la página de configuración del módulo "Sveriges Riksbank - tipos de cambio de divisas", lo que le permitirá establecer su recargo/descuento.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Sveriges Riksbank - tipos de cambio de divisas".

### 4.1 Resumen de la arquitectura

El módulo sigue una arquitectura de módulo estándar de PrestaShop, centrándose principalmente en la configuración del back-office y la ejecución de tareas cron en el front-office. Aprovecha el sistema de configuración de PrestaShop para el almacenamiento de ajustes y `ModuleFrontController` para manejar la solicitud de la tarea cron. La lógica central reside en el archivo principal del módulo, que gestiona la instalación, desinstalación y el método `getContent()` para el formulario de configuración. La función principal del módulo es obtener datos externos (tipos de cambio de divisas) y actualizar los datos del objeto `Currency` de PrestaShop.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

Estos controladores están diseñados para ser accesibles públicamente, principalmente para la funcionalidad de la tarea cron.

- **`srrates/controllers/front/cronjob.php`**

  - **Nombre de la clase y clase padre:** `SrratesCronjobModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este es el controlador crucial para las actualizaciones automáticas de divisas. Cuando se accede a esta URL (normalmente mediante una tarea cron del lado del servidor), activa la lógica del módulo para obtener los últimos tipos de cambio de Sveriges Riksbank y actualizarlos en la base de datos de PrestaShop. No renderiza ninguna salida visual, pero normalmente devuelve un mensaje simple de éxito o error. Está diseñado para ser ligero y eficiente para tareas programadas.
- **`srrates/controllers/front/index.php`**

  - **Nombre de la clase y clase padre:** `SrratesIndexModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador probablemente sirve como un respaldo o un punto de entrada predeterminado para el enrutamiento del front-office del módulo. En muchos módulos, `index.php` en un directorio de controlador frontal se utiliza para manejar la ruta base del módulo si no se solicita ninguna acción específica. Podría redirigir o simplemente mostrar una página en blanco si no se utiliza explícitamente para una función. Para este módulo, su función principal es probablemente mínima, ya que `cronjob.php` maneja la lógica principal del front-office.

#### Controladores de administración de Back-Office

El módulo no utiliza ningún controlador de administración personalizado. Toda la configuración se gestiona a través del método `getContent()` en el archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define ninguna clase personalizada ni `ObjectModel` en el directorio `classes/`. Interactúa directamente con la clase principal `Currency` y la clase `Configuration` de PrestaShop para gestionar la configuración y actualizar las tasas.

### 4.4 Activos de JavaScript (`views/js/`)

El módulo no incluye ningún archivo JavaScript personalizado. Todas las interacciones en la página de configuración se manejan mediante elementos de formulario estándar de PrestaShop y, potencialmente, jQuery si se usa directamente dentro del método `getContent()`.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo no incluye ningún archivo CSS personalizado. El estilo de la página de configuración se basa completamente en los estilos predeterminados del tema del Back Office de PrestaShop.

### 4.6 Estructura de plantilla Smarty (`views/templates/`)

- **`srrates/views/admin.tpl`**
  - **Alcance:** Plantilla de administración.
  - **Propósito:** Esta plantilla se utiliza para renderizar el formulario de configuración del módulo dentro del Back Office de PrestaShop. Muestra el interruptor "Habilitar Módulo", la "URL de la Tarea Cron" y la lista dinámica de monedas con sus respectivos campos de entrada "Recargo / Descuento (%)". Es responsable del diseño visual de la salida de `getContent()`.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:
  El módulo no crea ninguna tabla SQL personalizada. Almacena sus ajustes de configuración (como `PS_SRRATES_ENABLED` y los recargos de moneda individuales) directamente en la tabla `ps_configuration` de PrestaShop.

  - `ps_configuration`: Almacena la configuración del módulo. Las claves suelen seguir un patrón como `PS_SRRATES_ENABLED` para el interruptor principal, y potencialmente `PS_SRRATES_MARKUP_EUR` para los recargos específicos de la moneda.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | No utilizado explícitamente por este módulo para la salida, pero `install()` podría registrarlo como práctica estándar. |
| `displayRightColumn` | En la columna derecha de las páginas del front-office. | No utilizado explícitamente por este módulo para la salida. |
| `displayLeftColumn` | En la columna izquierda de las páginas del front-office. | No utilizado explícitamente por este módulo para la salida. |
| `displayFooter` | En la sección del pie de página de cada página del front-office. | No utilizado explícitamente por este módulo para la salida. |
| `displayProductExtraContent` | En la página del producto, debajo del contenido principal. | No utilizado explícitamente por este módulo para la salida. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | No utilizado explícitamente por este módulo, ya que su función es la actualización de tasas, no el procesamiento de pedidos. |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración, antes de renderizar. | Potencialmente utilizado para cargar CSS/JS para la página de configuración del módulo, aunque no hay activos personalizados presentes. |
| `actionModuleInstall` | Durante la instalación del módulo. | Se utiliza para realizar la configuración inicial, crear entradas de configuración y registrar hooks. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Se utiliza para limpiar las entradas de configuración y anular el registro de hooks. |

La funcionalidad principal del módulo (actualización de tasas) se activa mediante el controlador frontal `cronjob.php`, no directamente por un hook de PrestaShop, aunque el módulo en sí se instala y gestiona mediante hooks de módulo estándar.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Sveriges Riksbank - tipos de cambio de divisas", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Puede descargar las versiones más recientes desde su historial de pedidos y acceder a los recursos de soporte allí.

---
title: "Tipo de cambio y tasas del NBU - Manual del comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Tipo de cambio y tasas del NBU' de MyPresta.eu."
sidebar:
  label: "Tipo de cambio y tasas del NBU"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo NBU Currency Exchange & Rates (National Bank of Ukraine) en MyPresta.eu](https://mypresta.eu/modules/administration-tools/nbu-currency-exchange-rates-national-bank-of-ukraine.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/nbu-currency-exchange-rates-national-bank-of-ukraine/)
>
> ---


# Tipo de cambio y tasas del NBU

## 1. Requisitos y compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL) para obtener datos de APIs externas. La mayoría de los entornos de alojamiento modernos cumplen estos requisitos por defecto.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Después de la instalación, haga clic en "Configurar" para acceder a la configuración del módulo. Aquí es donde definirá cómo se aplican los tipos del NBU a su tienda.

**Nombre de la pantalla:** Configuración del tipo de cambio y tasas del NBU

**Ajustes y opciones:**

1.  **URL de la tarea CRON:**
    -   **Qué hace este ajuste:** Muestra la URL única que el programador CRON de su servidor necesita llamar periódicamente. Cuando se accede a esta URL, el módulo obtiene automáticamente los últimos tipos de cambio del NBU y los actualiza en su tienda PrestaShop.
    -   **Efecto de cambiar este ajuste:** No puede cambiar esta URL directamente. Es generada por el módulo. Si no configura una tarea CRON para llamar a esta URL, los tipos de cambio no se actualizarán automáticamente, y tendrá que activar las actualizaciones manualmente (si existe tal opción, lo cual no ocurre para la función principal de este módulo).
    -   **Valor recomendado:** Copie esta URL y configúrela en el programador de tareas CRON de su panel de control de alojamiento.
    -   **Escenario / ejemplo del comerciante:** Copia `https://yourstore.com/module/nburates/cronjob?token=YOUR_SECURE_TOKEN` y la añade a sus tareas CRON de cPanel o Plesk para que se ejecute una vez al día (por ejemplo, a las 3 AM). Esto garantiza que sus precios en UAH estén siempre actualizados antes de que sus clientes empiecen a comprar.

2.  **Frecuencia de la tarea CRON:**
    -   **Qué hace este ajuste:** Es una recomendación sobre la frecuencia con la que debe ejecutar la tarea CRON. El NBU suele actualizar los tipos una vez al día.
    -   **Efecto de cambiar este ajuste:** Esto es puramente informativo. Cambiar la frecuencia real de su tarea CRON (en su panel de alojamiento) afectará la frecuencia con la que se actualizan los tipos. Ejecutarla con demasiada frecuencia (por ejemplo, cada minuto) es innecesario y puede consumir recursos del servidor sin beneficio, ya que los tipos del NBU no cambian tan a menudo. Ejecutarla con muy poca frecuencia (por ejemplo, una vez a la semana) significa que sus tipos podrían estar desactualizados.
    -   **Valor recomendado:** Una vez al día.
    -   **Escenario / ejemplo del comerciante:** Configura la tarea CRON de su servidor para que se ejecute `0 3 * * *` (todos los días a las 3 AM) para que coincida con las actualizaciones diarias del NBU.

3.  **Moneda a actualizar (UAH):**
    -   **Qué hace este ajuste:** Este campo le permite especificar el ID de la moneda Hryvnia ucraniana (UAH) en su tienda PrestaShop. El módulo necesita saber qué moneda debe actualizar.
    -   **Efecto de cambiar este ajuste:** Si el ID es incorrecto o se deja vacío, el módulo no podrá encontrar y actualizar la moneda UAH, y sus precios no reflejarán los tipos del NBU.
    -   **Valor recomendado:** El ID de su moneda UAH. Puede encontrarlo navegando a **Internacional > Monedas** en su Back Office de PrestaShop, editando la moneda UAH y mirando la URL (por ejemplo, `id_currency=3` significa que el ID es 3).
    -   **Escenario / ejemplo del comerciante:** Su moneda UAH tiene un ID de `3`. Introduce `3` en este campo. Ahora, cuando se ejecuta la tarea CRON, el módulo sabe que debe actualizar el tipo de cambio para la moneda con ID `3`.

4.  **Margen (%):**
    -   **Qué hace este ajuste:** Esto le permite añadir un margen porcentual (recargo o descuento) a los tipos de cambio del NBU obtenidos. Un valor positivo aumenta el tipo (haciendo que los precios en UAH sean más altos), y un valor negativo lo disminuye (haciendo que los precios en UAH sean más bajos).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en 0:* El módulo utiliza el tipo exacto del NBU.
        -   *Cuando se establece en 2:* El tipo de cambio de UAH será un 2% más alto que el tipo oficial del NBU. Por ejemplo, si el NBU dice 1 EUR = 40 UAH, con un margen del 2%, su tienda utilizará 1 EUR = 40.8 UAH. Esto puede ayudar a cubrir las tarifas de transacción o proporcionar un ligero margen de beneficio.
        -   *Cuando se establece en -1:* El tipo de cambio de UAH será un 1% más bajo que el tipo oficial del NBU. Esto podría usarse para precios promocionales o para ofrecer un pequeño descuento.
    -   **Valor recomendado:** Depende de su estrategia comercial. `0` para tipos exactos del NBU, o un pequeño porcentaje positivo (por ejemplo, `1` o `2`) para cubrir costes.
    -   **Escenario / ejemplo del comerciante:** Desea compensar ligeramente las tarifas de la pasarela de pago para las transacciones en UAH. Establece el margen en `1.5`. Ahora, todos los precios en UAH se calcularán utilizando el tipo del NBU más un 1.5% adicional.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
|---|---|---|---|
| Configuración del módulo | URL de la tarea CRON | N/A (Generado) | La URL para activar las actualizaciones diarias de tipos. Debe configurarse en el CRON del alojamiento. |
| Configuración del módulo | Frecuencia de la tarea CRON | Una vez al día | Recomendación informativa para la programación de la tarea CRON. |
| Configuración del módulo | Moneda a actualizar (UAH) | ID de la moneda UAH | Especifica qué moneda en PrestaShop debe actualizarse con los tipos del NBU. Crítico para el funcionamiento del módulo. |
| Configuración del módulo | Margen (%) | 0 | Añade un recargo/descuento porcentual al tipo del NBU para flexibilidad de precios. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis precios en UAH no se actualizan. ¿Qué debo hacer?**
R1:
*   **Verifique la tarea CRON:** La razón más común es una tarea CRON configurada incorrectamente o faltante. Verifique que la URL de la tarea CRON de la configuración del módulo esté correctamente añadida a su panel de alojamiento y esté programada para ejecutarse.
*   **Verifique el ID de la moneda UAH:** Asegúrese de que el ajuste "Moneda a actualizar (UAH)" en la configuración del módulo coincida con el ID exacto de su moneda UAH en PrestaShop (**Internacional > Monedas**).
*   **Verifique la disponibilidad del NBU:** Ocasionalmente, la API del NBU podría no estar disponible temporalmente. Espere unas horas y vuelva a verificar. El módulo está diseñado para usar el último tipo conocido si la API está caída.
*   **Registros del servidor:** Verifique los registros de la tarea CRON de su servidor (si están disponibles) en busca de errores cuando se llama a la URL de CRON.

**P2: El módulo está instalado, pero no veo ningún cambio visual en mi tienda.**
R2: Este módulo funciona en segundo plano para actualizar los tipos de cambio. No añade nuevos bloques o elementos visuales a su tienda. Su efecto se ve en el cálculo preciso de los precios de los productos cuando UAH es la moneda seleccionada.

**P3: ¿Puedo actualizar manualmente los tipos si la tarea CRON falla?**
R3: El mecanismo principal del módulo es la tarea CRON. Si bien puede actualizar manualmente los tipos de cambio en PrestaShop (**Internacional > Monedas**), hacerlo anularía los tipos del NBU. La mejor práctica es asegurarse de que su tarea CRON funcione correctamente. Si necesita una actualización inmediata, puede activar manualmente la URL de CRON una vez visitándola en su navegador (aunque esta no es la solución a largo plazo prevista).

**P4: ¿Qué sucede en los días festivos bancarios cuando el NBU no publica nuevos tipos?**
R4: El módulo está diseñado para manejar esto de forma inteligente. Si el NBU no publica nuevos tipos en un día determinado (por ejemplo, fines de semana o días festivos), el módulo normalmente conservará el último tipo obtenido con éxito. Esto garantiza que sus precios en UAH permanezcan estables y consistentes.

**P5: ¿Cómo borro la caché de Smarty si hago cambios y no los veo?**
R5: Si bien los cambios de este módulo se basan principalmente en datos (tipos de cambio) y menos en plantillas visuales, borrar la caché a veces puede ayudar. Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop. Establezca "Compilación de plantillas" en "Recompilar las plantillas si los archivos han sido actualizados" o "Forzar compilación" y haga clic en "Borrar caché". Recuerde volver a "Nunca recompilar los archivos de plantilla" para el rendimiento en producción después de la solución de problemas.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)
Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura
El módulo `NBU Currency Exchange & Rates` es un módulo ligero de PrestaShop diseñado para integrar tipos de cambio de moneda externos de la API del Banco Nacional de Ucrania (NBU). Sigue un patrón simple similar a MVC dentro de la estructura del módulo de PrestaShop. La lógica central reside en el archivo principal del módulo (`cronjob.php`), que maneja la configuración, la instalación y la ejecución principal de la tarea CRON. Utiliza la clase `Configuration` de PrestaShop para almacenar la configuración y el ObjectModel `Currency` para actualizar los tipos. La funcionalidad principal del módulo se expone a través de un controlador frontal, diseñado específicamente para ser llamado por una tarea CRON del lado del servidor.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:
    *   `nburates/controllers/front/cronjob.php`
        *   **Nombre de la clase:** `NburatesCronjobModuleFrontController` (extiende `ModuleFrontController`)
        *   **Responsabilidad:** Este es el punto final crítico para la tarea CRON. Cuando se accede a él, realiza las siguientes acciones:
            1.  Valida un token seguro (`token`) pasado en la URL para evitar accesos no autorizados.
            2.  Recupera la configuración del módulo (ID de la moneda UAH, margen).
            3.  Obtiene los últimos tipos de cambio del NBU de la API oficial del NBU (probablemente `https://bank.gov.ua/NBUStatService/v1/statdirectory/exchangenew?json`).
            4.  Analiza la respuesta JSON para extraer los tipos de cambio relevantes.
            5.  Aplica el margen configurado a los tipos obtenidos.
            6.  Actualiza el tipo de cambio para la moneda UAH especificada en la tabla `ps_currency` utilizando el ObjectModel `Currency` de PrestaShop.
            7.  Maneja las condiciones de error (por ejemplo, API inaccesible, respuesta no válida) registrando o recurriendo a tipos anteriores.
            8.  Genera un mensaje simple de éxito o error, adecuado para el registro de tareas CRON.
    *   `nburates/controllers/front/index.php`
        *   **Nombre de la clase:** `NburatesIndexModuleFrontController` (extiende `ModuleFrontController`)
        *   **Responsabilidad:** Este es un controlador frontal `index.php` estándar vacío, a menudo incluido en los módulos para evitar la lista de directorios o para servir como marcador de posición. Normalmente no contiene lógica específica para la función principal de este módulo.

-   **Controladores de administración de Back-Office**:
    *   Ninguno. Toda la configuración se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)
-   Ninguno. El módulo interactúa directamente con el ObjectModel `Currency` y la clase `Configuration` de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)
-   Ninguno. El módulo no utiliza ningún JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)
-   Ninguno. El módulo no utiliza ningún CSS personalizado. La página de configuración de administración se basa en el estilo predeterminado del Back Office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de administración (`views/templates/admin/`)**:
    *   `nburates/views/admin.tpl`
        *   **Propósito:** Esta plantilla renderiza el formulario de configuración del módulo en el Back Office de PrestaShop.
        *   **Contenido:** Muestra la URL de la tarea CRON, la recomendación de frecuencia de CRON, los campos de entrada para el ID de la moneda UAH y el porcentaje de margen. Normalmente utiliza los ayudantes de formulario y el estilo estándar de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    *   El módulo no crea ninguna tabla de base de datos personalizada.
    *   Interactúa con la tabla `ps_configuration` para almacenar su configuración (por ejemplo, `NBU_RATES_UAH_CURRENCY_ID`, `NBU_RATES_MARGIN`, `NBU_RATES_SECURE_TOKEN`).
    *   Actualiza la tabla `ps_currency`, específicamente la columna `conversion_rate` para la moneda UAH.

-   **Tabla de hooks registrados**:
    El módulo no registra ningún hook de visualización tradicional (`displayHeader`, `displayFooter`, etc.) que renderice contenido en el front office. Su "hook" principal es la `acción` que realiza cuando su controlador frontal es llamado por la tarea CRON.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
|---|---|---|
| `actionModuleInstall` | Durante la instalación del módulo | Crea entradas de configuración, genera token seguro. |
| `actionModuleUninstall` | Durante la desinstalación del módulo | Limpia las entradas de configuración. |
| (Implícito) `ModuleFrontController::initContent()` para `NburatesCronjobModuleFrontController` | Cuando se accede a la URL de CRON | Obtiene los tipos del NBU, aplica el margen, actualiza el tipo de cambio de la moneda UAH. |

## 5. Soporte oficial y actualizaciones
Para actualizaciones oficiales, correcciones de errores y soporte para desarrolladores del módulo "Tipo de cambio y tasas del NBU", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a proporcionar asistencia oportuna y a garantizar la compatibilidad del módulo con las últimas versiones de PrestaShop.

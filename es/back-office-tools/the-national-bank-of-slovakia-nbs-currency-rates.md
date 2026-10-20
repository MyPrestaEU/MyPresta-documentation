---
title: "El Banco Nacional de Eslovaquia (NBS) - tasas de cambio - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop El Banco Nacional de Eslovaquia (NBS) - tasas de cambio de MyPresta.eu."
sidebar:
  label: "El Banco Nacional de Eslovaquia (NBS) - tasas de cambio - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo The National Bank of Slovakia (NBS) - currency rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/the-national-bank-of-slovakia-nbs-currency-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/the-national-bank-of-slovakia-nbs-currency-rates/)
>
> ---


# El Banco Nacional de Eslovaquia (NBS) - tasas de cambio

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para obtener datos externos, las cuales están casi universalmente disponibles en los entornos de alojamiento modernos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo para acceder a sus ajustes.

#### **1. Habilitar / Deshabilitar Módulo**

- **Qué hace este ajuste:** Este es un interruptor estándar de PrestaShop para activar o desactivar la funcionalidad principal del módulo.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* El módulo comenzará a obtener y actualizar las tasas de cambio según su configuración.
  - *Cuando está deshabilitado:* El módulo detendrá todas las operaciones, y sus tasas de cambio ya no serán actualizadas automáticamente por los datos del NBS.
- **Valor recomendado:** **SÍ** (para habilitar la funcionalidad del módulo).
- **Escenario / ejemplo de comerciante:** Si desea detener temporalmente las actualizaciones automáticas (por ejemplo, durante el mantenimiento o si cambia a la gestión manual de tasas), puede deshabilitarlo. De lo contrario, manténgalo habilitado para actualizaciones continuas.

#### **2. URL CRON para actualizaciones automáticas**

- **Qué hace este ajuste:** Muestra una URL única que debe configurar como una "tarea cron" en su servidor de alojamiento web. Una tarea cron es una tarea programada que le indica a su servidor que visite esta URL a intervalos regulares, lo que activa el módulo para obtener y actualizar automáticamente las últimas tasas de cambio del NBS.
- **Efecto de cambiar este ajuste:**
  - *Cuando se configura correctamente como una tarea cron:* Sus tasas de cambio se actualizarán automáticamente sin ninguna intervención manual.
  - *Cuando no se configura como una tarea cron:* El módulo no actualizará las tasas automáticamente. Tendría que visitar manualmente esta URL en su navegador para activar una actualización (lo que anula el propósito de la automatización).
- **Valor recomendado:** Esta es una URL generada. Debe **copiar esta URL** y pegarla en el programador de tareas cron de su panel de control de alojamiento.
- **Escenario / ejemplo de comerciante:** Desea que sus tasas de cambio se actualicen todos los días a las 3 AM. Copiaría esta URL, iría a su panel de alojamiento (por ejemplo, cPanel, Plesk, o pediría ayuda a su host) y crearía una tarea cron que ejecute esta URL diariamente a las 3 AM.

#### **3. Añadir margen porcentual a las tasas de cambio**

- **Qué hace este ajuste:** Le permite añadir un valor porcentual además de las tasas de cambio oficiales obtenidas del NBS. Este margen se aplica a todas las monedas actualizadas por el módulo.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en 0 (o se deja vacío):* Sus tasas de cambio serán exactamente las proporcionadas por el NBS.
  - *Cuando se establece en un valor positivo (por ejemplo, 2):* El módulo aumentará la tasa de cambio del NBS en ese porcentaje (por ejemplo, si la tasa es 1 EUR = 1.10 USD, con un margen del 2%, se convierte en 1 EUR = 1.122 USD). Esto hace que sus productos sean ligeramente más caros cuando se pagan en la moneda no base.
- **Valor recomendado:** **0** (si desea tasas exactas del NBS) o un pequeño porcentaje positivo (por ejemplo, **1-3%**) para cubrir tarifas de transacción o volatilidad del mercado.
- **Escenario / ejemplo de comerciante:** Desea tener en cuenta posibles tarifas bancarias al convertir pagos o simplemente desea un pequeño margen en sus ventas internacionales. Establecer esto en "2" agregará un margen del 2% a todas las tasas de cambio actualizadas.

#### **4. Actualizar solo las monedas seleccionadas**

- **Qué hace este ajuste:** Esta opción le permite elegir monedas específicas en su tienda PrestaShop que deben ser actualizadas por el módulo NBS. Si tiene muchas monedas pero solo desea que NBS gestione algunas, esto es útil.
- **Efecto de cambiar este ajuste:**
  - *Cuando no está marcado:* El módulo intentará actualizar todas las monedas activas en su tienda PrestaShop que tengan una tasa correspondiente disponible del NBS.
  - *Cuando está marcado y se seleccionan monedas específicas:* Solo las monedas elegidas tendrán sus tasas de cambio actualizadas por el módulo. Otras monedas conservarán sus tasas existentes (manuales o de otras fuentes).
- **Valor recomendado:** **Marque esta casilla** y seleccione solo las monedas que gestiona activamente con los datos del NBS. Esto evita cambios no deseados en otras monedas.
- **Escenario / ejemplo de comerciante:** Su moneda base es EUR, y también vende en USD y CZK. Desea que el NBS actualice las tasas de USD y CZK, pero gestiona manualmente las tasas de GBP. Marcaría esta casilla y seleccionaría solo USD y CZK de la lista.

#### **5. Lista de monedas a actualizar**

- **Qué hace este ajuste:** Esta es una lista de selección múltiple que aparece solo si "Actualizar solo las monedas seleccionadas" está marcado. Muestra todas las monedas activas en su tienda PrestaShop, lo que le permite elegir cuáles debe actualizar el módulo.
- **Efecto de cambiar este ajuste:**
  - *Seleccionar monedas:* Estas monedas tendrán sus tasas de cambio actualizadas automáticamente por el módulo NBS.
  - *Deseleccionar monedas:* Estas monedas serán ignoradas por el módulo NBS y sus tasas no se cambiarán.
- **Valor recomendado:** Seleccione todas las monedas para las que desea utilizar las tasas del NBS.
- **Escenario / ejemplo de comerciante:** Siguiendo el ejemplo anterior, haría clic en "USD" y "CZK" en esta lista para asegurarse de que solo esas se actualicen.

#### **6. Botón Guardar**

- **Qué hace este ajuste:** Aplica todos los cambios que ha realizado en la página de configuración.
- **Efecto de cambiar este ajuste:** La configuración de su módulo se guardará y surtirá efecto inmediatamente (para futuras ejecuciones de tareas cron o actualizaciones manuales).
- **Valor recomendado:** Siempre haga clic en **"Guardar"** después de realizar cualquier cambio.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar / Deshabilitar Módulo | SÍ | Activa/desactiva la funcionalidad del módulo. |
| Configuración del módulo | URL CRON para actualizaciones automáticas | URL generada | Copiar y configurar como tarea cron para actualizaciones automáticas de tasas. |
| Configuración del módulo | Añadir margen porcentual a las tasas de cambio | 0 (o 1-3%) | Añade un margen porcentual a las tasas del NBS para la estrategia de precios. |
| Configuración del módulo | Actualizar solo las monedas seleccionadas | Marcar y seleccionar | Restringe las actualizaciones del NBS a monedas específicas elegidas. |
| Configuración del módulo | Lista de monedas a actualizar | Seleccionar las deseadas | Elija qué monedas activas reciben actualizaciones de tasas del NBS. |
| Configuración del módulo | Botón Guardar | Hacer clic después de los cambios | Guarda todos los ajustes de configuración del módulo. |

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis tasas de cambio no se actualizan automáticamente. ¿Qué debo hacer?**
R:

1. **Verificar el estado del módulo:** Asegúrese de que el módulo esté habilitado en **Módulos > Gestor de módulos**.
2. **Verificar la tarea cron:** El problema más común es una tarea cron configurada incorrectamente.
   - Vuelva a la página de configuración del módulo y copie la "URL CRON" de nuevo.
   - Inicie sesión en su panel de control de alojamiento (cPanel, Plesk, etc.) y navegue a la sección "Tareas Cron" o "Tareas Programadas".
   - Verifique que la URL sea exactamente la proporcionada por el módulo y que la programación (por ejemplo, diaria, horaria) sea correcta.
   - Asegúrese de que el comando utilice `wget` o `curl` para ejecutar la URL (por ejemplo, `wget -O /dev/null "SU_URL_CRON_AQUÍ"`).
   - Si no está seguro, póngase en contacto con el soporte de su proveedor de alojamiento con la URL CRON y pídales que la configuren por usted.
3. **Verificar los registros del servidor:** Su proveedor de alojamiento podría tener registros de la ejecución de la tarea cron que pueden indicar si hay un error.

**P2: El módulo está habilitado, pero algunas monedas no se actualizan.**
R:

1. **Verificar "Actualizar solo las monedas seleccionadas":** Vaya a la configuración del módulo. Si "Actualizar solo las monedas seleccionadas" está marcado, asegúrese de que las monedas específicas que espera que se actualicen estén seleccionadas en la "Lista de monedas a actualizar".
2. **Disponibilidad de datos del NBS:** Es posible que el Banco Nacional de Eslovaquia no proporcione tasas para todas las monedas. El módulo solo puede actualizar las monedas para las que el NBS publica datos. Consulte el sitio web oficial del NBS para conocer los pares de divisas disponibles.
3. **Estado de la moneda en PrestaShop:** Asegúrese de que las monedas en cuestión estén activas en su tienda PrestaShop (**Internacional > Monedas**). Las monedas inactivas no se pueden actualizar.

**P3: ¿Con qué frecuencia debo ejecutar la tarea cron?**
R: Para la mayoría de las tiendas, ejecutar la tarea cron una vez al día es suficiente para mantener las tasas actualizadas. Si su negocio requiere tasas en tiempo real debido a transacciones internacionales de alto volumen o mercados volátiles, podría configurarla para que se ejecute con mayor frecuencia (por ejemplo, cada 6 o 12 horas), pero diariamente suele ser adecuado.

**P4: Agregué un margen, pero los precios no parecen reflejarlo.**
R:

1. **Guardar configuración:** Asegúrese de haber hecho clic en el botón "Guardar" después de establecer el margen.
2. **Activar actualización:** El margen solo se aplicará cuando se actualicen las tasas de cambio. Esto sucederá con la próxima ejecución de su tarea cron, o puede activar una actualización manualmente visitando la URL CRON en su navegador.
3. **Borrar caché:** A veces, la caché de PrestaShop podría contener valores antiguos. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).

**P5: ¿Este módulo afectará mi moneda base?**
R: No, el módulo actualiza las tasas de cambio *en relación* con su moneda base. El valor de su moneda base en sí mismo permanece constante. Por ejemplo, si su moneda base es EUR, el módulo actualizará cuántos USD o CZK equivalen a 1 EUR.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "El Banco Nacional de Eslovaquia (NBS) - tasas de cambio" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente una clase de módulo principal (`cronjob.php`) para la configuración y la gestión de hooks, y un controlador frontal (`cronjob.php`) para manejar la ejecución de la tarea cron. Interactúa con la gestión de monedas central de PrestaShop para actualizar las tasas. La función principal del módulo es obtener datos externos (tasas del NBS) e integrarlos en el modelo de objeto `Currency` de PrestaShop.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `controllers/front/cronjob.php`
    - **Nombre de la clase y clase padre:** `NbsratesCronjobModuleFrontController` que extiende `ModuleFrontController`.
    - **Responsabilidad:** Este controlador está diseñado específicamente para ser llamado por una tarea cron. Cuando se accede a él, inicia el proceso de obtención de las últimas tasas de cambio del Banco Nacional de Eslovaquia y las actualiza en la base de datos de PrestaShop. No renderiza ninguna salida visual al navegador, sino que realiza un procesamiento en segundo plano. Maneja la lógica para aplicar el margen porcentual configurado y actualizar solo las monedas seleccionadas.
  - `controllers/front/index.php`
    - **Nombre de la clase y clase padre:** Este suele ser un archivo vacío o un marcador de posición, a menudo utilizado para evitar la lista de directorios o para asegurar un punto de entrada válido para versiones antiguas de PrestaShop. No contiene lógica específica del módulo para las tasas del NBS.
- **Controladores de administración de Back-Office**: Ninguno. Toda la administración se maneja a través del método `getContent()` del módulo principal.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define clases `ObjectModel` personalizadas. Interactúa directamente con la clase `Currency` principal de PrestaShop para actualizar las tasas de cambio.

### 4.4 Activos de JavaScript (`views/js/`)

Ninguno. El módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Ninguno. El módulo no incluye ningún archivo CSS personalizado.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - `views/templates/admin/admin.tpl`
    - **Propósito:** Esta plantilla se renderiza cuando se accede a la página de configuración del módulo en el Back Office de PrestaShop. Muestra los campos de entrada para habilitar/deshabilitar el módulo, la URL CRON, el porcentaje de margen y las opciones de selección de moneda. Utiliza ayudantes y elementos de formulario estándar de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:
  El módulo no crea tablas SQL personalizadas. Almacena sus ajustes de configuración en la tabla `ps_configuration` de PrestaShop.

  - `PS_NBS_RATES_ENABLED`: Almacena el estado habilitado/deshabilitado del módulo.
  - `PS_NBS_RATES_MARGIN`: Almacena el margen porcentual a aplicar.
  - `PS_NBS_RATES_SELECTED_CURRENCIES`: Almacena un array serializado de IDs de moneda si "Actualizar solo las monedas seleccionadas" está activo.
  - `PS_NBS_RATES_CRON_TOKEN`: Almacena un token único para la URL cron por seguridad.
- **Tabla de Hooks Registrados**:
  El módulo utiliza principalmente el hook `actionFrontControllerSetMedia` (implícitamente, si fuera a cargar activos, aunque no lo hace) y se basa en sus métodos `install()` y `uninstall()` para la configuración y limpieza. Su funcionalidad principal se activa por el controlador frontal `cronjob.php` en lugar de un hook tradicional de PrestaShop.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `install()` | Durante la instalación del módulo | Configura los valores predeterminados en `ps_configuration` y registra el módulo. |
| `uninstall()` | Durante la desinstalación del módulo | Limpia los valores de configuración de `ps_configuration`. |
| (Tarea Cron) | Solicitud HTTP externa a `controllers/front/cronjob.php` | Obtiene las tasas del NBS, aplica el margen y actualiza la tabla `ps_currency`. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial del módulo "El Banco Nacional de Eslovaquia (NBS) - tasas de cambio", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y configuración del módulo.
"""

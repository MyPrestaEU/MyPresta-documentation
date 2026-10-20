---
title: "CBR Currency Exchange & Rates (Banco de Rusia) - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop CBR Currency Exchange & Rates (Banco de Rusia) de MyPresta.eu."
sidebar:
  label: "CBR Currency Exchange & Rates (Banco de Rusia) - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo CBR Currency Exchange & Rates (Bank of Russia) en MyPresta.eu](https://mypresta.eu/modules/administration-tools/cbr-currency-exchange-rates-bank-of-russia.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/cbr-currency-exchange-rates-bank-of-russia/)
>
> ---


# CBR Currency Exchange & Rates (Banco de Rusia)

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para la comunicación con API externas, que son comunes en la mayoría de los entornos de alojamiento web.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de instalar el módulo, haga clic en "Configurar" para acceder a sus ajustes. Esta es la pantalla principal donde gestionará todos los aspectos del módulo CBR Currency Exchange & Rates.

#### **Configuración general**

- **Habilitar actualizaciones automáticas:**

  - **Qué hace este ajuste:** Este interruptor controla si el módulo buscará y aplicará automáticamente nuevos tipos de cambio del Banco Central de Rusia.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* El módulo obtendrá periódicamente los últimos tipos de cambio del sitio web del CBR. Esto es crucial para mantener sus precios en RUB precisos sin intervención manual. Deberá configurar un trabajo CRON (explicado a continuación) para que esto funcione.
    - *Cuando está deshabilitado (NO):* El módulo no actualizará las tasas automáticamente. Tendría que actualizar las tasas manualmente si esta opción está desactivada, lo que anula el propósito del módulo.
  - **Valor recomendado:** SÍ
  - **Escenario/ejemplo de comerciante:** Desea que sus precios en RUB siempre reflejen el tipo de cambio oficial actual sin tener que iniciar sesión diariamente y actualizarlos. Habilitar esto asegura que su tienda esté siempre actualizada.
- **Frecuencia de actualización (en horas):**

  - **Qué hace este ajuste:** Define con qué frecuencia el módulo debe intentar obtener nuevos tipos de cambio del CBR.
  - **Efecto de cambiar este ajuste:**
    - *Establecer un número más bajo (por ejemplo, 1 hora):* Las tasas se verificarán y actualizarán con mayor frecuencia. Esto es ideal si su negocio requiere conversiones muy precisas y casi en tiempo real.
    - *Establecer un número más alto (por ejemplo, 24 horas):* Las tasas se verificarán con menos frecuencia. Esto podría ser adecuado si sus precios no fluctúan drásticamente o si prefiere reducir la carga del servidor por llamadas externas frecuentes.
  - **Valor recomendado:** 24 (Las actualizaciones diarias suelen ser suficientes, ya que las tasas del CBR cambian una vez al día).
  - **Escenario/ejemplo de comerciante:** Desea asegurarse de que sus precios en RUB se actualicen diariamente, por lo que lo establece en 24 horas. Si vende artículos de alto valor con márgenes ajustados, podría establecerlo en 12 horas para capturar cambios a mitad del día si el CBR los publica (aunque normalmente es una vez al día).
- **Margen sobre el tipo de cambio (%):**

  - **Qué hace este ajuste:** Le permite agregar un margen porcentual sobre el tipo de cambio oficial del CBR. Esto se puede utilizar para cubrir tarifas de transacción, costos de conversión de moneda o para ajustar ligeramente su estrategia de precios.
  - **Efecto de cambiar este ajuste:**
    - *Establecer un valor positivo (por ejemplo, 2):* El módulo aumentará el tipo de cambio calculado en un 2%. Esto significa que por cada unidad de su moneda base, obtendrá un poco más de RUB, lo que aumentará efectivamente sus precios en RUB.
    - *Establecer 0 o dejar en blanco:* El módulo utilizará el tipo de cambio oficial exacto del CBR sin ningún ajuste.
    - *Establecer un valor negativo (por ejemplo, -1):* El módulo disminuirá el tipo de cambio calculado en un 1%. Esto significa que obtendrá un poco menos de RUB por cada unidad de su moneda base, lo que disminuirá efectivamente sus precios en RUB.
  - **Valor recomendado:** 0 (A menos que tenga razones comerciales específicas para agregar un margen).
  - **Escenario/ejemplo de comerciante:** Su pasarela de pago cobra una tarifa del 1.5% por convertir RUB a su moneda base. Puede establecer un margen del 1.5% aquí para compensar ese costo y mantener sus márgenes de beneficio.
- **URL del trabajo CRON:**

  - **Qué hace este ajuste:** Muestra la URL única que necesita configurar como un trabajo CRON en su servidor de alojamiento. Cuando se accede a esta URL, activa el módulo para obtener y actualizar los tipos de cambio.
  - **Efecto de cambiar este ajuste:** Este no es un ajuste que cambie, sino una URL que *usa*.
    - *Cuando se configura correctamente como un trabajo CRON:* El módulo se ejecutará automáticamente en segundo plano con la frecuencia especificada (según el ajuste "Frecuencia de actualización") para actualizar las tasas.
    - *Si no se configura como un trabajo CRON:* Las actualizaciones automáticas no se producirán, incluso si "Habilitar actualizaciones automáticas" está configurado en SÍ.
  - **Valor recomendado:** Copie esta URL y configúrela como un trabajo CRON en su servidor.
  - **Escenario/ejemplo de comerciante:** Después de configurar el módulo, copia esta URL y la agrega al programador de trabajos CRON de su panel de control de alojamiento para que se ejecute diariamente a las 3 AM, asegurando que las tasas se actualicen antes de que comience su día hábil.

#### **Configuración de moneda**

- **Moneda a actualizar:**
  - **Qué hace este ajuste:** Este menú desplegable le permite seleccionar qué moneda específica en su tienda PrestaShop debe actualizarse con las tasas del CBR. Listará todas las monedas que haya habilitado en su Back Office de PrestaShop.
  - **Efecto de cambiar este ajuste:**
    - *Seleccionar "Rublo Ruso (RUB)":* El módulo se dirigirá específicamente y actualizará el tipo de cambio del Rublo Ruso frente a la moneda base de su tienda utilizando los datos del CBR.
    - *Seleccionar cualquier otra moneda:* Este módulo está diseñado específicamente para las tasas del CBR, que son para el Rublo Ruso. Seleccionar otra moneda podría provocar un comportamiento inesperado o ninguna actualización para esa moneda.
  - **Valor recomendado:** Rublo Ruso (RUB)
  - **Escenario/ejemplo de comerciante:** La moneda base de su tienda es EUR, y desea asegurarse de que cuando los clientes seleccionen RUB, la conversión de EUR a RUB sea precisa según el CBR. Selecciona "Rublo Ruso (RUB)" aquí.

#### **Botón Guardar**

- **Guardar:**
  - **Qué hace:** Aplica todos los cambios que ha realizado en la página de configuración.
  - **Efecto de hacer clic:** Sus ajustes se almacenarán en la base de datos y el módulo funcionará de acuerdo con los nuevos parámetros.
  - **Acción recomendada:** Siempre haga clic en "Guardar" después de realizar cualquier cambio.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar actualizaciones automáticas | SÍ | Controla la obtención automática de las tasas del CBR. SÍ para actualizaciones sin intervención. |
| Configuración del módulo | Frecuencia de actualización (en horas) | 24 | Con qué frecuencia el trabajo CRON debe activar las actualizaciones de tasas. 24 para diario. |
| Configuración del módulo | Margen sobre el tipo de cambio (%) | 0 | Agrega un porcentaje a la tasa oficial. Úselo para tarifas o estrategia de precios. |
| Configuración del módulo | URL del trabajo CRON | (URL única) | URL que se configurará en su servidor para actualizaciones automatizadas. |
| Configuración del módulo | Moneda a actualizar | Rublo Ruso (RUB) | Especifica qué moneda de PrestaShop se actualizará con las tasas del CBR. Debe ser RUB. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: Mis precios en RUB no se actualizan automáticamente. ¿Qué debo verificar?**
R1:

-   **¿Está "Habilitar actualizaciones automáticas" configurado en SÍ?** Verifique la configuración del módulo.
-   **¿Ha configurado el trabajo CRON en su servidor de alojamiento?** Esta es la razón más común. Copie la "URL del trabajo CRON" de la configuración del módulo y agréguela al programador CRON de su panel de alojamiento. Asegúrese de que esté configurado para ejecutarse al menos con la misma frecuencia que su configuración de "Frecuencia de actualización".
-   **¿Está "Moneda a actualizar" configurado en "Rublo Ruso (RUB)"?** El módulo está diseñado para RUB.
-   **Verifique los registros del trabajo CRON de su servidor (si están disponibles):** Su proveedor de alojamiento podría ofrecer registros que muestren si el trabajo CRON se está ejecutando y si encontró algún error.
-   **Borre la caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" para asegurarse de que su tienda esté mostrando los datos más recientes.

**P2: El tipo de cambio parece incorrecto o no ha cambiado en un tiempo.**
R2:

-   **Verifique la tasa oficial del CBR:** Consulte el sitio web oficial del Banco Central de Rusia para conocer el tipo de cambio de hoy y confirmar cuál debería ser.
-   **Verifique su "Frecuencia de actualización":** Si está configurado en 24 horas, solo se actualizará una vez al día.
-   **Días festivos bancarios:** El CBR no actualiza las tasas en días festivos bancarios. El módulo utiliza inteligentemente la última tasa disponible. Si hay un período de vacaciones largo, la tasa podría permanecer estática durante varios días.
-   **Problemas con el trabajo CRON:** Consulte la P1 para solucionar problemas con los trabajos CRON.

**P3: ¿Puedo usar este módulo para otras monedas además de RUB?**
R3: No, este módulo está diseñado específicamente para integrarse con los datos de tipo de cambio del Banco Central de Rusia, que son principalmente para el Rublo Ruso. Solo actualizará con precisión la moneda RUB en su tienda.

**P4: He cambiado mi tema y ahora los precios se ven extraños en RUB.**
R4: Este módulo solo maneja el *valor* de la conversión de moneda. La *visualización* de los precios (fuentes, colores, diseño) es manejada por su tema de PrestaShop. Si los precios se ven extraños después de un cambio de tema, es probable que sea un problema de CSS o de plantilla con su nuevo tema, no del módulo en sí. Es posible que deba ajustar el estilo de su tema.

**P5: ¿Cómo actualizo manualmente las tasas si es necesario?**
R5: Si bien el módulo está diseñado para actualizaciones automáticas, puede forzar una actualización visitando manualmente la URL del trabajo CRON en su navegador web. Esto activará el proceso de actualización una vez. Recuerde borrar la caché de PrestaShop después.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo CBR Currency Exchange & Rates.

### 4.1 Descripción general de la arquitectura

El módulo `cbrrates` sigue una arquitectura de módulo PrestaShop estándar, utilizando principalmente la clase `Module` para su funcionalidad principal y configuración. Aprovecha los controladores frontales para la ejecución de trabajos CRON y un método `getContent()` simple para la configuración del back-office. El módulo obtiene datos XML de la API del CBR, los analiza y actualiza los tipos de cambio de `Currency` de PrestaShop.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nombre de clase y clase padre**: `CbrratesCronjobModuleFrontController` que extiende `ModuleFrontController`.
        -   **Responsabilidad**: Este controlador está diseñado para ser llamado por un trabajo CRON externo. Cuando se accede a él, inicia el proceso de actualización del tipo de cambio. Verifica los valores de configuración `update_` y `updatev_` para determinar si una actualización es necesaria según la frecuencia configurada. Luego llama a la lógica principal del módulo para obtener y aplicar las últimas tasas del CBR. Emite un mensaje simple de éxito o error.
    -   `controllers/front/index.php`
        -   **Nombre de clase y clase padre**: `CbrratesIndexModuleFrontController` que extiende `ModuleFrontController`.
        -   **Responsabilidad**: Este es un controlador frontal de marcador de posición o predeterminado. En muchos módulos, si no se define una acción específica, `index.php` podría servir como un recurso alternativo o simplemente redirigir. Para `cbrrates`, su función principal es probablemente mínima, ya que la interacción principal del front-office es a través de `cronjob.php`. Podría estar presente para asegurar que exista una ruta de front-office válida para el módulo, incluso si no se usa activamente para la visualización.
-   **Controladores de administración de Back-Office**:

    -   No hay controladores de administración dedicados presentes en este módulo. Toda la configuración del back-office se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

No hay clases personalizadas ni definiciones de `ObjectModel` presentes en el directorio `classes/` para este módulo. Toda la lógica principal reside dentro del archivo principal `cbrrates.php`.

### 4.4 Activos de JavaScript (`views/js/`)

No hay archivos JavaScript personalizados presentes en el módulo.

### 4.5 Hojas de estilo CSS (`views/css/`)

No hay archivos CSS personalizados presentes en el módulo.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `cbrrates/views/admin.tpl`
        -   **Propósito**: Esta plantilla es renderizada por el método `getContent()` en `cbrrates.php` para mostrar el formulario de configuración del módulo en el Back Office de PrestaShop.
        -   **Contenido**: Típicamente contiene la estructura HTML para los campos de entrada, interruptores y botones para configuraciones como `mypresta_updates`, `update_`, `updatev_`, `currency_` y la visualización de la URL del trabajo CRON. Utiliza ayudantes de formulario y estilos estándar de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   El módulo no crea ninguna tabla SQL personalizada.
    -   Almacena sus configuraciones en la tabla `ps_configuration` (o `_configuration` según el prefijo).
        -   `PS_CBRRATES_UPDATE_ENABLED`: Booleano (0/1) para "Habilitar actualizaciones automáticas".
        -   `PS_CBRRATES_UPDATE_FREQUENCY`: Entero para "Frecuencia de actualización (en horas)".
        -   `PS_CBRRATES_MARGIN`: Flotante para "Margen sobre el tipo de cambio (%)".
        -   `PS_CBRRATES_CURRENCY_ID`: Entero, ID de la moneda de PrestaShop a actualizar (por ejemplo, ID para RUB).
        -   `PS_CBRRATES_LAST_UPDATE`: Marca de tiempo de la última actualización exitosa.
        -   `PS_CBRRATES_CRON_TOKEN`: Una cadena única utilizada en la URL del trabajo CRON por seguridad.
-   **Tabla de Hooks registrados**:
    El módulo no registra explícitamente hooks para la visualización del front-office (por ejemplo, `displayHeader`, `displayFooter`). Su interacción principal con el núcleo de PrestaShop es a través del hook `actionUpdateCurrency` (implícitamente, al actualizar los tipos de cambio) y su propio mecanismo CRON interno.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionUpdateCurrency` | Se activa cuando se actualiza una moneda (implícitamente por este módulo) | No está registrado explícitamente por el módulo, pero la función principal del módulo es actualizar los tipos de cambio, lo que podría activar este hook principal de PrestaShop. |
| (CRON interno) | A través de `controllers/front/cronjob.php` | Activa la obtención y actualización de los tipos de cambio del CBR según la frecuencia configurada. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "CBR Currency Exchange & Rates (Banco de Rusia)", consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.

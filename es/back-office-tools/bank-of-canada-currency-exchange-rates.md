---
title: "Banco de Canadá - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Banco de Canadá - tipos de cambio de divisas' de MyPresta.eu."
sidebar:
  label: "Banco de Canadá - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Bank of Canada - currency exchange rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-canada-currency-exchange-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/bank-of-canada-currency-exchange-rates/)
>
> ---


# Banco de Canadá - tipos de cambio de divisas

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para obtener datos externos, las cuales están casi universalmente disponibles en los entornos de alojamiento modernos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" para acceder a la configuración del módulo. Esta es la pantalla principal donde gestionará cómo se actualizan los tipos de cambio.

#### **1. Actualizar tipos de cambio manualmente**

- **Qué hace esta configuración:** Este es un botón que, al hacer clic, activa inmediatamente el módulo para obtener los últimos tipos de cambio del Banco de Canadá y actualizarlos en su tienda.
- **Efecto de cambiar esta configuración:**
  - *Al hacer clic:* El módulo se conecta al Banco de Canadá, recupera las tasas más actuales, calcula las tasas cruzadas y las aplica a las monedas de su tienda. Normalmente aparecerá un mensaje de confirmación.
- **Valor recomendado:** Utilice este botón para actualizaciones inmediatas o para probar el módulo después de la configuración inicial. Para actualizaciones continuas, se recomienda la tarea CRON (explicada a continuación).
- **Escenario / ejemplo de comerciante:** Acaba de lanzar un nuevo producto y quiere asegurarse de que todos los precios internacionales estén absolutamente actualizados antes de una gran campaña de marketing. Haga clic en este botón para forzar una actualización inmediata.

#### **2. URL de la tarea CRON**

- **Qué hace esta configuración:** Este campo muestra una URL única que, al ser accedida, activa el módulo para actualizar automáticamente los tipos de cambio. Esta URL está diseñada para ser utilizada con una "tarea CRON" en su servidor web.
- **Efecto de cambiar esta configuración:**
  - *Cuando se accede a la URL (mediante una tarea CRON):* El módulo realiza el mismo proceso de actualización de tasas que al hacer clic en el botón de actualización manual, pero lo hace automáticamente a intervalos programados.
- **Valor recomendado:** Copie esta URL y configúrela como una tarea CRON en su servidor de alojamiento.
- **Escenario / ejemplo de comerciante:** Desea que sus tipos de cambio se actualicen todos los días a las 3 AM. Copia esta URL y configura su panel de alojamiento (cPanel, Plesk, etc.) para visitar esta URL diariamente a las 3 AM. Esto asegura que sus tasas estén siempre frescas sin que usted tenga que mover un dedo.

#### **3. Margen del tipo de cambio (%)**

- **Qué hace esta configuración:** Esto le permite añadir un margen porcentual a los tipos de cambio obtenidos del Banco de Canadá. Por ejemplo, si la tasa del BOC es 1.20 y usted establece un margen del 2%, su tienda utilizará una tasa de 1.224 (1.20 * 1.02).
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece un valor positivo (por ejemplo, 2):* Todos los precios convertidos en su tienda serán ligeramente más altos, reflejando el margen añadido. Esto puede ayudar a cubrir las tarifas de transacción, los costos de conversión de moneda o simplemente aumentar su margen de beneficio en las ventas internacionales.
  - *Cuando se establece en 0 (o se deja vacío):* El módulo utilizará los tipos de cambio exactos proporcionados por el Banco de Canadá sin ningún recargo adicional.
- **Valor recomendado:** Comience con 0% y ajuste según sus necesidades comerciales, las tarifas de la pasarela de pago y los márgenes de beneficio deseados. Una práctica común es del 1-3% para cubrir posibles costos.
- **Escenario / ejemplo de comerciante:** Su pasarela de pago cobra una tarifa del 1.5% por las conversiones de moneda internacional. Usted establece el "Margen del tipo de cambio" en 1.5% para asegurarse de que este costo esté cubierto en el precio de sus productos, en lugar de erosionar su beneficio.

#### **4. Última actualización**

- **Qué hace esta configuración:** Este campo muestra la fecha y hora de la última actualización exitosa del tipo de cambio realizada por el módulo.
- **Efecto de cambiar esta configuración:** Este es un campo de solo lectura y no se puede cambiar. Sirve como un indicador informativo.
- **Valor recomendado:** Supervise este campo para asegurarse de que su tarea CRON se esté ejecutando correctamente y que las tasas se estén actualizando regularmente.
- **Escenario / ejemplo de comerciante:** Nota que sus precios internacionales parecen desactualizados. Comprueba "Última actualización" y ve que no se ha actualizado en una semana, lo que indica un posible problema con la configuración de su tarea CRON.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Actualizar tipos de cambio manualmente (Botón) | Hacer clic para actualizar | Fuerza una actualización inmediata de todos los tipos de cambio de divisas del BOC. |
| Configuración del módulo | URL de la tarea CRON | Copiar y configurar en el servidor | Proporciona una URL para actualizaciones automáticas y programadas a través del servicio CRON de su alojamiento. |
| Configuración del módulo | Margen del tipo de cambio (%) | 0% | Añade un recargo porcentual a los tipos de cambio obtenidos, afectando a todos los precios convertidos. |
| Configuración del módulo | Última actualización | Solo lectura | Muestra la marca de tiempo de la última actualización exitosa del tipo de cambio. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis tipos de cambio no se actualizan automáticamente. ¿Qué debo hacer?**
R1: Esto casi siempre es un problema de la tarea CRON.
- **Compruebe su panel de alojamiento:** Inicie sesión en su cuenta de alojamiento (cPanel, Plesk, etc.) y verifique que la tarea CRON esté configurada correctamente con la URL exacta proporcionada por el módulo. Asegúrese de que la frecuencia sea correcta (por ejemplo, diaria).
- **Verifique el comando CRON:** El comando suele ser algo como `wget -O /dev/null "SU_URL_CRON_AQUI"` o `curl "SU_URL_CRON_AQUI"`. Asegúrese de que no haya errores tipográficos.
- **Compruebe "Última actualización" en el módulo:** Si esta fecha es antigua, confirma que la tarea CRON no se está ejecutando.
- **Ejecute manualmente la URL de la tarea CRON:** Copie la URL de la tarea CRON de la configuración del módulo y péguela en su navegador. Si se actualiza, entonces la URL en sí está bien, y el problema es puramente con la configuración de la tarea CRON de su alojamiento.

**P2: Los precios en otras monedas parecen demasiado altos/bajos en comparación con la moneda predeterminada.**
R2:
- **Compruebe su "Margen del tipo de cambio (%)":** Si está configurado demasiado alto, los precios se inflarán. Si es negativo (aunque no se recomienda), los precios serían más bajos.
- **Verifique su moneda predeterminada:** Asegúrese de que la moneda predeterminada de su tienda PrestaShop (Localización > Monedas) esté configurada correctamente a su moneda operativa principal (por ejemplo, CAD si está obteniendo datos del Banco de Canadá). El módulo calcula las tasas en relación con su moneda predeterminada.
- **Borre la caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los precios antiguos pueden estar en caché.

**P3: El módulo dice que "Última actualización" fue exitosa, pero no veo cambios en el front office.**
R3:
- **Borre la caché de PrestaShop:** Esta es la razón más común. Siempre borre su caché después de cualquier actualización de datos significativa en PrestaShop.
- **Compruebe la caché del navegador:** Intente borrar la caché de su navegador o ver su tienda en una ventana de incógnito/privada para descartar problemas de caché local.
- **Verifique la selección de moneda:** Asegúrese de que realmente está viendo la tienda en la moneda no predeterminada donde espera ver los precios convertidos.

**P4: ¿Este módulo funciona con temas personalizados?**
R4: Sí, este módulo funciona en segundo plano actualizando los tipos de cambio de divisas principales de PrestaShop. No interactúa directamente con los elementos visuales de su tema, por lo que debería ser compatible con cualquier tema personalizado. El selector de moneda del tema simplemente mostrará los precios basándose en las tasas que proporciona el módulo.

**P5: ¿Puedo usar este módulo si mi moneda predeterminada no es CAD?**
R5: Sí, puede. El módulo obtiene las tasas base del Banco de Canadá (por ejemplo, USD a CAD, EUR a CAD). Luego calcula inteligentemente las tasas cruzadas en relación con *la moneda predeterminada de su tienda*. Así, si su moneda predeterminada es EUR y el BOC proporciona USD/CAD, el módulo calculará EUR/USD, EUR/CAD, etc., basándose en los datos disponibles.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Banco de Canadá - tipos de cambio de divisas" (`bocrates`) está diseñado como una solución ligera y automatizada para la sincronización de tipos de cambio. Principalmente aprovecha el `ObjectModel` `Currency` principal de PrestaShop para actualizar los tipos de cambio. El módulo utiliza un controlador frontal para la ejecución de tareas CRON, asegurando que las actualizaciones de tasas ocurran fuera del contexto estándar del Back Office, lo cual es ideal para tareas programadas. Se adhiere a la arquitectura del módulo de PrestaShop, utilizando los métodos `install()` y `uninstall()` para la configuración y limpieza, y `getContent()` para la configuración del Back Office.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `controllers/front/cronjob.php`
    - **Nombre de clase y clase padre**: `BocratesCronjobModuleFrontController` que extiende `ModuleFrontController`.
    - **Responsabilidad**: Este controlador es el punto de entrada para la tarea CRON automatizada. Cuando se accede a través de su URL única (proporcionada en la configuración del módulo), activa el método `processUpdateExchangeRates()` dentro de la clase principal del módulo. Está diseñado para ser llamado externamente por un programador CRON del lado del servidor, no directamente por un usuario. Normalmente, genera un mensaje simple de éxito o error.
  - `controllers/front/index.php`
    - **Nombre de clase y clase padre**: `BocratesIndexModuleFrontController` que extiende `ModuleFrontController`.
    - **Responsabilidad**: Este es un controlador frontal de marcador de posición o predeterminado. En muchos módulos, si no se define una acción específica, se podría usar `index.php`. Para este módulo, su función principal es probablemente servir como un respaldo o para asegurar que el enrutamiento del front-office del módulo esté correctamente establecido, incluso si no realiza una acción específica orientada al usuario. El `cronjob.php` es el controlador frontal activo para la funcionalidad.
- **Controladores de administración del Back-Office**:

  - Ninguno. Toda la configuración del Back Office se maneja directamente dentro del método `getContent()` del archivo principal del módulo `bocrates.php`.

### 4.3 Clases y modelos principales (`classes/`)

- Ninguno. El módulo interactúa directamente con el `ObjectModel` `Currency` y la clase `Configuration` de PrestaShop para el almacenamiento y manipulación de datos.

### 4.4 Activos JavaScript (`views/js/`)

- Ninguno. El módulo no utiliza JavaScript personalizado para su funcionalidad.

### 4.5 Hojas de estilo CSS (`views/css/`)

- Ninguno. El módulo no utiliza CSS personalizado para su funcionalidad.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - `bocrates/views/admin.tpl`
    - **Propósito**: Esta plantilla es renderizada por el método `getContent()` del archivo principal del módulo `bocrates.php`. Muestra el formulario de configuración del módulo en el Back Office de PrestaShop. Esto incluye el botón de actualización manual, la URL de la tarea CRON, la entrada del margen del tipo de cambio y la marca de tiempo de la última actualización.

### 4.7 Esquema de la base de datos y mapa de ganchos

- **Tablas de la base de datos**:

  - El módulo no crea tablas SQL personalizadas.
  - Almacena su configuración en la tabla `ps_configuration` utilizando claves como:
    - `BOCRATES_MARGIN`: Almacena el margen porcentual para los tipos de cambio.
    - `BOCRATES_LAST_UPDATE`: Almacena la marca de tiempo de la última actualización exitosa.
    - `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Relacionadas con el mecanismo de actualización de MyPresta.eu.
- **Tabla de ganchos registrados**:
  El módulo opera principalmente en segundo plano y no registra ganchos para la visualización en el front-office. Su funcionalidad principal se activa mediante el controlador frontal `cronjob`.

  | Nombre del gancho | Momento de ejecución | Propósito técnico |
  | --- | --- | --- |
  | `actionModuleInstall` | Durante la instalación del módulo | Establece los valores de configuración predeterminados y registra los ganchos necesarios (si los hay). |
  | `actionModuleUninstall` | Durante la desinstalación del módulo | Limpia los valores de configuración. |
  | `displayBackOfficeHeader` | Se renderiza en el encabezado del Back Office | Potencialmente utilizado para incluir activos o mostrar avisos en el panel de administración (aunque no se enumeran activos específicos). |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte técnico dedicado para el módulo "Banco de Canadá - tipos de cambio de divisas", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.
"""

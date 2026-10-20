---
title: "Actualización de tasas de cambio NBP - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Actualización de tasas de cambio NBP' de MyPresta.eu."
sidebar:
  label: "Actualización de tasas de cambio NBP - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo NBP currency rates update en MyPresta.eu](https://mypresta.eu/modules/administration-tools/nbp-currency-rates-update.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/nbp-currency-rates-update/)
>
> ---


# Actualización de tasas de cambio NBP

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar como cURL, JSON y OpenSSL suelen ser necesarias y son estándar en la mayoría de los entornos de alojamiento web modernos. Su alojamiento también debe admitir la configuración de cron jobs.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Actualización de tasas de cambio NBP". Se le presentará la pantalla de configuración principal.

#### **URL del Cron Job**

- **Qué hace este ajuste:** Muestra una URL única que utilizará para configurar una tarea automatizada (un "cron job") en su servidor web. Cuando se accede a esta URL, el módulo se conectará a los servidores del NBP, obtendrá las últimas tasas de cambio y las actualizará en su tienda PrestaShop.
- **Efecto de cambiar este ajuste:** No puede cambiar esta URL directamente. Es generada por el módulo.
- **Valor recomendado:** Copie esta URL exactamente como aparece.
- **Escenario / ejemplo de comerciante:** Tomará esta URL y la pegará en la sección "Cron Jobs" de su panel de control de alojamiento (por ejemplo, cPanel, Plesk o una configuración de cron de servidor personalizada). Esto le indica a su servidor que visite esta URL a intervalos específicos (por ejemplo, todos los días a las 3 AM), lo que activa automáticamente el proceso de actualización de la moneda.

#### **Frecuencia del Cron Job**

- **Qué hace este ajuste:** Este no es un ajuste que cambie *dentro* de PrestaShop, sino una recomendación sobre la frecuencia con la que debe configurar el cron job de su servidor para llamar a la URL.
- **Efecto de cambiar este ajuste:** Este texto simplemente le aconseja. La frecuencia real la controla la configuración del cron job de su servidor.
- **Valor recomendado:** "Una vez al día" suele ser suficiente para la mayoría de las tiendas, ya que las tasas del NBP suelen actualizarse diariamente.
- **Escenario / ejemplo de comerciante:** Si configura el cron job de su servidor para que se ejecute diariamente, las tasas de cambio de su tienda se actualizarán una vez cada 24 horas, asegurando que estén siempre al día con los datos del NBP. Ejecutarlo con más frecuencia (por ejemplo, cada hora) suele ser innecesario y podría sobrecargar su servidor o la API del NBP.

#### **Nota Importante sobre los Cron Jobs**

- **Qué hace este ajuste:** Esta sección proporciona instrucciones cruciales sobre cómo configurar el cron job en su servidor. Explica que debe acceder a su panel de control de alojamiento (como cPanel o Plesk) y agregar un nuevo cron job.
- **Efecto de cambiar este ajuste:** Este es un texto informativo. Debe seguir estas instrucciones fuera de PrestaShop.
- **Valor recomendado:** Lea esto atentamente y siga los pasos proporcionados por su proveedor de alojamiento para configurar los cron jobs.
- **Escenario / ejemplo de comerciante:** Su proveedor de alojamiento tendrá una sección, generalmente llamada "Cron Jobs" o "Tareas Programadas", donde puede agregar un nuevo comando. Normalmente elegirá una frecuencia (por ejemplo, "Una vez al día") y luego pegará la "URL del Cron Job" en el campo de comando, a menudo precedido por `wget -q -O /dev/null`. Si no está seguro, póngase en contacto con el soporte de su proveedor de alojamiento.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | URL del Cron Job | (URL Única) | La URL para activar las actualizaciones automáticas de moneda a través de un cron job del servidor. Cópiela para la configuración de su servidor. |
| Configuración del Módulo | Frecuencia del Cron Job | Una vez al día | Recomendación sobre la frecuencia con la que debe ejecutar el cron job en su servidor para mantener las tasas actualizadas. |
| Configuración del Módulo | Instrucciones para la Configuración del Cron Job | N/A | Guía sobre cómo configurar el cron job en su servidor de alojamiento web. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Mis tasas de cambio no se actualizan, incluso después de configurar el cron job. ¿Qué debo hacer?**
R:

1. **Verifique la URL del Cron Job:** Asegúrese de haber copiado la URL exactamente de la página de configuración del módulo y de haberla pegado correctamente en la configuración del cron job de su panel de control de alojamiento.
2. **Verifique la Ejecución del Cron Job:** Revise los registros de cron job de su proveedor de alojamiento (si están disponibles) para ver si el cron job se está ejecutando realmente a la hora programada. A veces, el comando podría ser incorrecto o la ruta a `wget` podría necesitar un ajuste.
3. **Pruebe Manualmente:** Intente visitar la "URL del Cron Job" directamente en su navegador web. Esto debería activar una actualización inmediata. Si las tasas se actualizan después de una visita manual, el problema está en la configuración del cron job de su servidor, no en el módulo en sí.
4. **Verifique las Monedas de PrestaShop:** Asegúrese de que las monedas que desea actualizar estén habilitadas en PrestaShop (**Internacional > Monedas**) y que tengan un código ISO válido que el NBP pueda reconocer (por ejemplo, USD, EUR, GBP).
5. **Borre la Caché:** A veces, la caché de PrestaShop puede impedirle ver los cambios inmediatos. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché".

**P: ¿Este módulo actualiza todas las monedas de mi tienda?**
R: Actualiza las monedas para las que el NBP proporciona tasas de cambio, en relación con PLN. El módulo es lo suficientemente inteligente como para convertir estas tasas a la moneda predeterminada de su tienda. Por ejemplo, si su moneda predeterminada es EUR y el NBP proporciona USD/PLN y EUR/PLN, el módulo puede calcular USD/EUR. Si el NBP no proporciona una tasa para una moneda específica, la tasa de esa moneda no será actualizada por este módulo.

**P: ¿Puedo configurar la frecuencia de actualización para que sea más de una vez al día?**
R: Si bien puede configurar el cron job de su servidor para que se ejecute con más frecuencia (por ejemplo, cada hora), las tasas de cambio del NBP suelen actualizarse una vez al día. Ejecutar el cron job con más frecuencia de la diaria suele ser innecesario y no proporcionará datos más recientes, pero tampoco causará ningún daño.

**P: Recibo un mensaje de error cuando intento configurar el módulo o cuando se ejecuta el cron job.**
R:

1. **Verifique la Versión de PHP:** Asegúrese de que su versión de PHP esté dentro del rango compatible (PHP 5.6 - 8.5).
2. **Conectividad del Servidor:** El módulo necesita conectarse al sitio web del NBP para obtener las tasas. Asegúrese de que su servidor tenga acceso a Internet saliente y no esté bloqueado por un firewall para acceder a URL externas.
3. **Modo Depuración de PrestaShop:** Habilite el modo de depuración de PrestaShop (**Parámetros Avanzados > Rendimiento > Modo depuración**) para ver mensajes de error más detallados, lo que puede ayudar a identificar el problema. Recuerde deshabilitarlo después de la solución de problemas.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Visión General de la Arquitectura

El módulo `Actualización de tasas de cambio NBP` es un módulo ligero de PrestaShop diseñado principalmente para realizar una única tarea crítica: obtener y actualizar las tasas de cambio del Banco Nacional de Polonia (NBP) a través de un cron job programado. Sigue una estructura de módulo estándar de PrestaShop, aprovechando `ModuleFrontController` para su punto final de cron y la clase principal del módulo para la configuración e instalación. La lógica central reside en el archivo `cronjob.php`, que actúa como la clase principal del módulo y el punto de entrada para la ejecución del cron.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `nbprates/controllers/front/cronjob.php`
    - **Nombre de clase y clase padre**: `NbpratesCronjobModuleFrontController` extiende `ModuleFrontController`
    - **Responsabilidad**: Este controlador sirve como punto final público para el cron job. Cuando se accede a través de la URL única generada por el módulo, activa la lógica de actualización de la moneda. No renderiza ninguna salida visual, sino que ejecuta el proceso de obtención y actualización de tasas. Está diseñado para ser llamado por `wget` o `curl` desde un programador de cron de un servidor.
  - `nbprates/controllers/front/index.php`
    - **Nombre de clase y clase padre**: `NbpratesIndexModuleFrontController` extiende `ModuleFrontController`
    - **Responsabilidad**: Este es un controlador de marcador de posición, a menudo incluido en módulos para evitar la lista de directorios si `index.php` no está presente en el directorio `controllers/front`. Normalmente no hace nada más que redirigir a la página de inicio o mostrar un error "404 No Encontrado". No contiene ninguna lógica de negocio específica para este módulo.
- **Controladores de Administración de Back-Office**:

  - Ninguno. Toda la configuración se maneja directamente dentro del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Principales (`classes/`)

- Ninguno. La lógica del módulo está contenida principalmente en el archivo principal del módulo (`nbprates/cronjob.php`).

### 4.4 Activos JavaScript (`views/js/`)

- Ninguno. El módulo no utiliza ningún JavaScript personalizado.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- Ninguno. El módulo no utiliza ningún CSS personalizado.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - `nbprates/views/admin.tpl`
    - **Propósito**: Esta plantilla es renderizada por el método `getContent()` de la clase principal del módulo (`NbpratesCronjob`) para mostrar el formulario de configuración del módulo en el Back Office de PrestaShop.
    - **Contenido**: Normalmente muestra la "URL del Cron Job" e instrucciones para configurar el cron job. Es una visualización estática de información en lugar de un formulario interactivo con campos de entrada.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo no crea ninguna tabla SQL personalizada.
  - Almacena su configuración (específicamente el token de cron generado) en la tabla `ps_configuration`. La clave para el token de cron sería típicamente `NBP_CRON_TOKEN`.
  - Actualiza las tasas de cambio de moneda existentes en la tabla `ps_currency` (específicamente la columna `conversion_rate`).
- **Tabla de Hooks Registrados**:
  El módulo no se registra explícitamente en ningún hook de visualización estándar de PrestaShop (como `displayHeader`, `displayFooter`, etc.) para la renderización del front-office. Su "hook" principal es el punto final de `ModuleFrontController` que es llamado externamente por el cron job del servidor.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `install()` | Durante la instalación del módulo | Crea el token de cron único y lo almacena en `ps_configuration`. |
| `uninstall()` | Durante la desinstalación del módulo | Elimina el token de cron de `ps_configuration`. |
| `actionFrontControllerSetMedia` | No registrado explícitamente, pero `ModuleFrontController` maneja implícitamente la carga de activos si hubiera alguno presente. | N/A (este módulo no carga ningún activo). |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Actualización de tasas de cambio NBP", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo con su tienda PrestaShop.

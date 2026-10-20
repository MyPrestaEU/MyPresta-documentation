---
title: "Banco Nacional Suizo - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Banco Nacional Suizo - tipos de cambio de divisas' de MyPresta.eu."
sidebar:
  label: "Banco Nacional Suizo - tipos de cambio de divisas"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Swiss National Bank - currency exchange rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/swiss-national-bank-currency-exchange-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/swiss-national-bank-currency-exchange-rates/)
>
> ---


# Banco Nacional Suizo - tipos de cambio de divisas

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para obtener datos externos. Su entorno de alojamiento también debe admitir tareas CRON para actualizaciones automatizadas.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" para acceder a la página de configuración principal del módulo. Aquí es donde definirá cómo el módulo obtiene y aplica los tipos de cambio.

#### **1. URL CRON**

-   **Qué hace esta configuración:** Muestra la URL única que necesita configurar como una tarea CRON en su servidor web. Cuando se accede a esta URL, el módulo obtendrá automáticamente los últimos tipos de cambio del Banco Nacional Suizo y los actualizará en su tienda PrestaShop.
-   **Efecto de cambiar esta configuración:** No puede cambiar esta URL directamente. Es generada por el módulo.
    -   *Cuando se configura correctamente como una tarea CRON:* Sus tipos de cambio se actualizarán automáticamente con la frecuencia que defina (por ejemplo, diariamente, cada hora).
    -   *Cuando NO se configura como una tarea CRON:* Sus tipos de cambio no se actualizarán automáticamente, y tendrá que activar la actualización manualmente visitando esta URL en su navegador, lo que anula el propósito de la automatización.
-   **Valor recomendado:** Copie esta URL y configúrela como una tarea CRON en su servidor de alojamiento.
-   **Escenario / ejemplo de comerciante:** Desea que sus tipos de cambio se actualicen cada mañana a las 3 AM. Copia esta URL y la añade al programador de tareas CRON de su panel de control de alojamiento, configurado para ejecutarse diariamente a las 3 AM.

#### **2. Margen del Tipo de Cambio (%)**

-   **Qué hace esta configuración:** Le permite añadir un margen porcentual a los tipos de cambio obtenidos del Banco Nacional Suizo. Este margen se aplica además de la tasa base.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se establece en 0 (predeterminado):* Los tipos de cambio se actualizarán exactamente como los proporciona el SNB.
    -   *Cuando se establece en un valor positivo (por ejemplo, 2):* El tipo de cambio se incrementará en ese porcentaje. Por ejemplo, si la tasa del SNB es 1 EUR = 1.10 CHF, y usted establece un margen del 2%, su tienda utilizará 1 EUR = 1.122 CHF (1.10 \* 1.02). Esto significa que los productos con precio en CHF aparecerán ligeramente más caros cuando se conviertan a EUR.
-   **Valor recomendado:** Comience con 0. Solo aumente si necesita tener en cuenta las tarifas de la pasarela de pago, los costos de conversión de moneda o para construir un pequeño margen de beneficio en su estrategia de precios internacionales.
-   **Escenario / ejemplo de comerciante:** Su procesador de pagos cobra una tarifa del 1.5% por las conversiones de moneda internacionales. Para cubrir este costo, establece el "Margen del Tipo de Cambio" en 1.5%. Esto asegura que sus márgenes de beneficio no se vean afectados por las tarifas de conversión.

#### **3. Botón Guardar**

-   **Qué hace esta configuración:** Este botón guarda cualquier cambio que haya realizado en la configuración de "Margen del Tipo de Cambio".
-   **Efecto de cambiar esta configuración:** Al hacer clic en "Guardar" se aplica su configuración de margen. La URL CRON es estática y no requiere guardado.
-   **Valor recomendado:** Siempre haga clic en "Guardar" después de ajustar el margen.
-   **Escenario / ejemplo de comerciante:** Ha decidido añadir un margen del 1%. Después de escribir "1" en el campo de margen, hace clic en "Guardar" para asegurarse de que esta configuración se aplique para futuras actualizaciones de tarifas.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Página de Configuración del Módulo | URL CRON | Generada por el módulo | URL para configurar la tarea CRON para actualizaciones automáticas de tipos de cambio. |
| Página de Configuración del Módulo | Margen del Tipo de Cambio (%) | 0 | Añade un margen porcentual a los tipos de cambio obtenidos del SNB. |
| Página de Configuración del Módulo | Botón Guardar | N/A | Guarda los cambios realizados en el "Margen del Tipo de Cambio". |

## 3. Resumen del Módulo

El módulo "Banco Nacional Suizo - tipos de cambio de divisas" es un módulo de PrestaShop que actualiza automáticamente los tipos de cambio de divisas en su tienda obteniendo datos del Banco Nacional Suizo (SNB). Utiliza el franco suizo (CHF) como moneda base para los cálculos y le permite añadir un margen personalizado a los tipos. Las actualizaciones están totalmente automatizadas a través de una tarea CRON.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo sigue una arquitectura de módulo PrestaShop minimalista. Su función principal es obtener periódicamente los tipos de cambio de una API externa (Banco Nacional Suizo) y actualizar la tabla `currency` en la base de datos de PrestaShop. La lógica central reside en el archivo principal del módulo (`snbrates/cronjob.php`) y se activa mediante un controlador frontal, diseñado para ser llamado por una tarea CRON. Utiliza la clase `Configuration` de PrestaShop para almacenar la configuración y el ObjectModel `Currency` para actualizar los tipos.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Estos controladores están diseñados para ser accedidos externamente, principalmente por tareas CRON.

    -   `controllers/front/cronjob.php`

        -   **Nombre de la clase y clase padre:** `SnbratesCronjobModuleFrontController` extiende `ModuleFrontController`.
        -   **Responsabilidad:** Este es el punto de entrada principal para la actualización automática de tipos. Cuando se accede a la URL de este controlador (por ejemplo, `sutienda.com/module/snbrates/cronjob`), ejecuta la lógica para:
            1.  Obtener los últimos tipos de cambio del endpoint de la API del SNB configurado.
            2.  Aplicar el margen configurado (si lo hay).
            3.  Actualizar la `conversion_rate` para cada moneda activa en la base de datos de PrestaShop, utilizando CHF como base.
            4.  No renderiza ninguna salida visual al navegador, típicamente devuelve un simple mensaje de éxito/fallo o redirige.
    -   `controllers/front/index.php`

        -   **Nombre de la clase y clase padre:** `SnbratesIndexModuleFrontController` extiende `ModuleFrontController`.
        -   **Responsabilidad:** Este es un controlador de marcador de posición, a menudo incluido en módulos pero no utilizado directamente para la funcionalidad principal de este módulo específico. Podría usarse para redirecciones simples o para evitar la lista de directorios si se accede directamente, pero no contiene lógica de negocio específica para las actualizaciones de tipos.
-   **Controladores de Administración de Back-Office**: Ninguno. La configuración del módulo se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

El módulo no introduce ninguna clase o ObjectModel personalizado en el directorio `classes/`. Aprovecha directamente el ObjectModel `Currency` principal de PrestaShop para gestionar los datos de la moneda y `Configuration` para la configuración del módulo.

### 4.4 Activos JavaScript (`views/js/`)

Ninguno. El módulo no utiliza ningún JavaScript personalizado.

### 4.5 Hojas de Estilo CSS (`views/css/`)

Ninguno. El módulo no utiliza ningún CSS personalizado.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `views/admin.tpl`
        -   **Propósito:** Esta plantilla es renderizada por el método `getContent()` del archivo principal del módulo (`snbrates/cronjob.php`) para mostrar el formulario de configuración del módulo en el Back Office de PrestaShop.
        -   **Contenido:** Típicamente incluye los campos del formulario para la "URL CRON" (solo visualización) y el "Margen del Tipo de Cambio (%)" (campo de entrada), junto con el botón "Guardar". Utiliza funciones de ayuda estándar de PrestaShop para la renderización de formularios.

### 4.7 Esquema de la Base de Datos y Mapa de Ganchos

-   **Tablas de la Base de Datos**:

    -   El módulo no crea ninguna tabla de base de datos personalizada.
    -   Interactúa con la tabla `ps_currency` principal de PrestaShop, actualizando específicamente la columna `conversion_rate` para las monedas activas.
    -   Almacena su configuración (por ejemplo, `SNBRATES_MARGIN`) en la tabla `ps_configuration`.
-   **Tabla de Ganchos Registrados**:
    El módulo no registra explícitamente ningún gancho de visualización de front-office (como `displayHeader`, `displayRightColumn`, `displayFooter`, `displayProductButtons`, etc.) ya que su función principal es el procesamiento de datos en segundo plano. Los "Ganchos de Front-Office: Cabecera, Columnas, Producto o Pie de página" mencionados en el aviso podrían referirse a una capacidad general o a un malentendido, ya que la función principal del módulo no implica la renderización de contenido en estas áreas.

    El módulo utiliza implícitamente lo siguiente:

    | Nombre del Gancho | Momento de Ejecución | Propósito Técnico |
    |---|---|---|
    | `actionModuleInstall` | Durante la instalación del módulo | Establece los valores de configuración predeterminados. |
    | `actionModuleUninstall` | Durante la desinstalación del módulo | Limpia los valores de configuración. |
    | (Interno) `ModuleFrontController` dispatch | Cuando se accede a la URL CRON | Activa la lógica de actualización de tipos. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y para asegurarse de que está ejecutando la última versión compatible del módulo "Banco Nacional Suizo - tipos de cambio de divisas", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.

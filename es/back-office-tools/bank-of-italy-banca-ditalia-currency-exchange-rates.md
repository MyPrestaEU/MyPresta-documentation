---
title: "Banco de Italia (Banca d'Italia) - tipos de cambio - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Banco de Italia (Banca d'Italia) - tipos de cambio' de MyPresta.eu."
sidebar:
  label: "Banco de Italia (Banca d'Italia) - tipos de cambio - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Bank of Italy (Banca dItalia) - currency exchange rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-italy-banca-ditalia-currency-exchange-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/bank-of-italy-banca-ditalia-currency-exchange-rates/)
>
> ---


# Banco de Italia (Banca d'Italia) - tipos de cambio

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para la comunicación con API externas, las cuales están casi universalmente disponibles en los entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en el botón "Configurar" junto al nombre del módulo en el Gestor de Módulos. Esto le llevará a la pantalla de configuración principal del módulo "Banco de Italia (Banca d'Italia) - tipos de cambio".

#### Configuración General

- **Qué hace esta configuración:** Esta sección le permite controlar cómo el módulo actualiza sus tipos de cambio de moneda y gestionar su funcionalidad principal.
- **Efecto de cambiar esta configuración:** Estos ajustes impactan directamente la precisión y frecuencia de los tipos de cambio de su tienda.

#### Ajustes y Opciones Específicas:

1.  **Botón "Actualizar tipos de cambio"**

    - **Qué hace esta configuración:** Este es un disparador manual para obtener inmediatamente los últimos tipos de cambio del Banco de Italia y aplicarlos a las monedas de su tienda.
    - **Efecto de cambiar esta configuración:**
      - *Al hacer clic:* El módulo se conectará a la fuente de datos del Banco de Italia, recuperará los tipos de referencia del Euro más recientes y actualizará todas las monedas activas en su tienda PrestaShop (excepto su moneda predeterminada, que suele ser EUR). Esto es útil para pruebas o para una actualización inmediata fuera de sus tareas programadas (cron jobs).
    - **Valor recomendado:** Haga clic en este botón después de la configuración inicial para asegurarse de que sus tipos de cambio estén actualizados. Úselo manualmente siempre que necesite una actualización inmediata.
    - **Escenario / ejemplo de comerciante:** Acaba de agregar una nueva moneda a su tienda, o ha habido una fluctuación significativa del mercado, y desea asegurarse de que sus precios se actualicen instantáneamente antes de una venta importante.
2.  **Campo "URL CRON para actualizaciones automáticas"**

    - **Qué hace esta configuración:** Este campo muestra una URL única que puede usar con el servicio de "cron job" de su proveedor de alojamiento. Un cron job es una tarea programada que se ejecuta automáticamente a intervalos específicos (por ejemplo, una vez al día, cada hora).
    - **Efecto de cambiar esta configuración:**
      - *Cuando se configura con su proveedor de alojamiento:* Los tipos de cambio de su tienda se actualizarán automáticamente con la frecuencia que defina en la configuración de su cron job, sin necesidad de hacer clic manualmente en ningún botón. Esto asegura que sus tipos de cambio estén siempre actualizados.
      - *Cuando no está configurado:* Deberá hacer clic manualmente en el botón "Actualizar tipos de cambio" para actualizar sus tipos de cambio.
    - **Valor recomendado:** Copie esta URL y configure un cron job en su servidor para que se ejecute al menos una vez cada 24 horas. Una actualización diaria suele ser suficiente para la mayoría de las tiendas de comercio electrónico.
    - **Escenario / ejemplo de comerciante:** Desea que los tipos de cambio de su tienda se actualicen todas las mañanas a las 3 AM, asegurando que todos los precios estén actualizados para el inicio del día hábil, sin tener que recordarlo.
3.  **Campo "Añadir margen a los tipos de cambio (%)"**

    - **Qué hace esta configuración:** Esto le permite añadir un margen porcentual a los tipos de cambio obtenidos. Por ejemplo, si el tipo oficial es 1 EUR = 1.10 USD, y usted establece un margen del 2%, el módulo usará 1 EUR = 1.078 USD (1.10 \* 0.98) o 1 EUR = 1.122 USD (1.10 \* 1.02) dependiendo de la dirección de la conversión. Esto ayuda a cubrir posibles tarifas de transacción, costos de conversión de moneda o simplemente para darle un pequeño margen.
    - **Efecto de cambiar esta configuración:**
      - *Cuando se establece un valor positivo (por ejemplo, 2):* El módulo ajustará los tipos de cambio obtenidos por ese porcentaje. Esto normalmente significa que obtendrá un poco más de moneda local por sus productos basados en euros, o un poco menos de euros por productos en moneda local, lo que ayuda a proteger sus márgenes de beneficio.
      - *Cuando se establece en 0 (o vacío):* El módulo utilizará los tipos de cambio exactos proporcionados por el Banco de Italia sin ningún ajuste.
    - **Valor recomendado:** Empiece con 0. Si experimenta problemas de rentabilidad debido a las fluctuaciones monetarias o las tarifas de transacción, considere añadir un pequeño margen (por ejemplo, 1-3%).
    - **Escenario / ejemplo de comerciante:** Su pasarela de pago cobra una tarifa del 1.5% por transacciones internacionales. Al establecer un margen del 2%, puede absorber este costo y asegurarse de que su rentabilidad no se vea erosionada por las conversiones de moneda.
4.  **Interruptor "Buscar actualizaciones del módulo"**

    - **Qué hace esta configuración:** Este interruptor controla si el módulo busca periódicamente en MyPresta.eu versiones más recientes del módulo.
    - **Efecto de cambiar esta configuración:**
      - *Cuando está habilitado (SÍ):* El módulo se conectará ocasionalmente a MyPresta.eu para ver si hay una versión más reciente disponible. Si se encuentra una actualización, verá una notificación en su back office de PrestaShop, lo que le indicará que descargue e instale la última versión. Esto le ayuda a mantenerse al día con las correcciones de errores, las nuevas funciones y las actualizaciones de compatibilidad.
      - *Cuando está deshabilitado (NO):* El módulo no buscará actualizaciones y no se le notificará de nuevas versiones. Tendría que verificar manualmente su cuenta de MyPresta.eu para buscar actualizaciones.
    - **Valor recomendado:** **SÍ**. Mantener sus módulos actualizados es crucial para la seguridad, el rendimiento y la compatibilidad con futuras versiones de PrestaShop.
    - **Escenario / ejemplo de comerciante:** Desea ser informado automáticamente cuando se lanza una nueva versión del módulo, para poder beneficiarse de las últimas mejoras y asegurarse de que su tienda permanezca segura y funcional.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | Botón "Actualizar tipos de cambio" | Clic después de la configuración / manualmente según sea necesario | Obtiene y aplica inmediatamente los últimos tipos de cambio del Banco de Italia. |
| Página de Configuración del Módulo | "URL CRON para actualizaciones automáticas" | Copiar y configurar en el alojamiento | Automatiza las actualizaciones diarias/horarias de los tipos de cambio, asegurando una precisión constante. |
| Página de Configuración del Módulo | "Añadir margen a los tipos de cambio (%)" | 0 (o 1-3% si es necesario) | Añade un margen porcentual a los tipos de cambio para cubrir tarifas o proteger los márgenes de beneficio. |
| Página de Configuración del Módulo | "Buscar actualizaciones del módulo" | SÍ | Le notifica las nuevas versiones del módulo para correcciones de errores, funciones y compatibilidad. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Mis tipos de cambio no se actualizan automáticamente. ¿Qué debo hacer?**
R1: Esto casi siempre está relacionado con la configuración del cron job.
- **Verifique su alojamiento:** Inicie sesión en el panel de control de su alojamiento (cPanel, Plesk, etc.) y verifique que el cron job para la URL del módulo esté configurado correctamente y se ejecute en los intervalos especificados. Asegúrese de que la URL copiada de la configuración del módulo sea exacta.
- **Pruebe la URL manualmente:** Copie la "URL CRON para actualizaciones automáticas" de la configuración del módulo y péguela directamente en su navegador web. Si se ejecuta correctamente, debería ver un mensaje simple de "OK" o similar. Si ve un error, podría haber un problema del lado del servidor o un problema con la propia URL.
- **Verifique el estado del módulo:** Asegúrese de que el módulo esté habilitado en su back office de PrestaShop.

**P2: Hice clic en "Actualizar tipos de cambio" pero mis precios en otras monedas no cambiaron.**
R2:
- **Borrar caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** en su back office de PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). PrestaShop a menudo almacena en caché las conversiones de moneda.
- **Verificar monedas activas:** Asegúrese de que las monedas que espera que se actualicen estén realmente habilitadas en **Internacional > Monedas**. El módulo solo actualiza las monedas activas.
- **Verificar moneda predeterminada:** El módulo actualiza *otras* monedas en relación con su moneda predeterminada (generalmente EUR). Si su moneda predeterminada no es EUR, el módulo seguirá obteniendo los tipos de EUR y convertirá a partir de ahí. Asegúrese de que su moneda predeterminada esté configurada correctamente.

**P3: ¿Puedo establecer diferentes márgenes para diferentes monedas?**
R3: No, la configuración "Añadir margen a los tipos de cambio (%)" aplica un único margen porcentual uniforme a *todos* los tipos de cambio obtenidos por el módulo. Si necesita márgenes muy específicos por moneda, necesitaría una solución de desarrollo personalizada o un módulo de gestión de moneda más avanzado.

**P4: El módulo dice que obtiene los tipos de cambio de Banca d'Italia. ¿Es esto fiable?**
R4: Sí, Banca d'Italia (Banco de Italia) es un banco central dentro del Sistema Europeo de Bancos Centrales (SEBC) y proporciona tipos de referencia oficiales del Euro. Estos tipos son altamente fiables y ampliamente utilizados para transacciones financieras en toda Europa.

**P5: Después de actualizar el módulo, mi tienda se ve un poco mal o veo errores.**
R5:
- **Borrar caché:** Siempre borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento**) después de cualquier actualización del módulo.
- **Caché del navegador:** Borre la caché y las cookies de su navegador web, o intente acceder a su tienda en modo incógnito/privado.
- **Revertir (si es necesario):** Si el problema persiste, es posible que deba deshabilitar o desinstalar temporalmente el módulo y revertir a una copia de seguridad anterior de su tienda. Luego, póngase en contacto con el soporte de MyPresta.eu con los detalles del problema.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Visión General de la Arquitectura

El módulo "Banco de Italia (Banca d'Italia) - tipos de cambio" (`birates`) es un módulo ligero de PrestaShop diseñado para automatizar las actualizaciones de los tipos de cambio. Sigue un patrón MVC estándar de PrestaShop cuando es aplicable, centrándose principalmente en una única interfaz de configuración y un controlador frontal para la ejecución de tareas cron. Aprovecha el `ObjectModel` `Currency` de PrestaShop para actualizar los tipos de cambio. La lógica central reside en el archivo principal del módulo, que maneja la instalación, desinstalación, configuración y el proceso de obtención de tipos de cambio.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nombre de clase y clase padre**: `BiratesCronjobModuleFrontController` extiende `ModuleFrontController`.
        -   **Responsabilidad**: Este controlador está diseñado para ser llamado por una tarea cron externa. Su método `initContent()` (o lógica similar dentro de `postProcess()`) activa el método `updateRates()` del módulo principal `birates`. No renderiza ningún contenido visual al usuario; su propósito es puramente ejecutar la lógica de actualización de tipos de cambio en segundo plano. Normalmente, emite un mensaje de éxito simple o un estado.
    -   `controllers/front/index.php`
        -   **Nombre de clase y clase padre**: `BiratesIndexModuleFrontController` extiende `ModuleFrontController`.
        -   **Responsabilidad**: Este es un controlador frontal de marcador de posición o de reserva. En muchos módulos, los controladores `index.php` se utilizan para definir una ruta predeterminada o manejar casos en los que no se proporciona una acción específica. Para este módulo, probablemente sirve como un punto de entrada básico, pero la funcionalidad principal para las actualizaciones de tipos de cambio es manejada por `cronjob.php`. Podría redirigir o simplemente mostrar una página mínima.
-   **Controladores de Administración de Back-Office**:

    -   No hay controladores de administración dedicados presentes en este módulo. Toda la configuración del back-office se maneja directamente dentro del método `getContent()` del archivo principal del módulo `birates.php`.

### 4.3 Clases y Modelos Principales (`classes/`)

No hay clases personalizadas ni definiciones de `ObjectModel` presentes en el directorio `classes/`. El módulo interactúa directamente con el `ObjectModel` `Currency` principal de PrestaShop para actualizar los tipos de cambio de moneda existentes.

### 4.4 Activos JavaScript (`views/js/`)

No hay archivos JavaScript personalizados presentes en el módulo.

### 4.5 Hojas de Estilo CSS (`views/css/`)

No hay archivos CSS personalizados presentes en el módulo.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `birates/views/admin.tpl`
        -   **Propósito**: Esta plantilla es renderizada por el método `getContent()` del archivo principal del módulo `birates.php`. Muestra todo el formulario de configuración del módulo en el back office de PrestaShop.
        -   **Contenido**: Incluye el botón "Actualizar tipos de cambio", el campo de URL CRON, la entrada "Añadir margen a los tipos de cambio (%)" y el interruptor "Buscar actualizaciones del módulo". Utiliza los ayudantes de formulario y el estilo estándar de PrestaShop.
-   **Plantillas de gancho (`views/templates/hook/`)**: Ninguna.
-   **Plantillas de front-office (`views/templates/front/`)**: Ninguna.

### 4.7 Esquema de Base de Datos y Mapa de Ganchos

-   **Tablas de Base de Datos**:

    -   El módulo no crea ninguna tabla SQL personalizada.
    -   Almacena sus configuraciones (por ejemplo, `mypresta_updates`, `update_`, `updatev_`, `currency_`) en la tabla `ps_configuration` (o `_configuration` dependiendo de su prefijo de tabla). Estas claves suelen estar prefijadas con el nombre del módulo o un identificador único.
-   **Tabla de Ganchos Registrados**:

| Nombre del Gancho | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | No se utiliza directamente para la salida visual, pero podría usarse para cargar activos (aunque no hay ninguno presente). |
| `displayRightColumn` | En la columna derecha de las páginas del front-office. | No se utiliza para la salida visual. |
| `displayLeftColumn` | En la columna izquierda de las páginas del front-office. | No se utiliza para la salida visual. |
| `displayFooter` | En la parte inferior de cada página del front-office. | No se utiliza para la salida visual. |
| `displayProductExtraContent` | En la página del producto, normalmente debajo de la información principal del producto. | No se utiliza para la salida visual. |
| `actionUpdateCurrency` | Después de que se ha actualizado una moneda. | El módulo *activa* las actualizaciones de moneda, pero no se engancha explícitamente a esto para su propia lógica. |
| `actionModuleInstall` | Durante la instalación del módulo. | Se utiliza para establecer valores de configuración predeterminados y registrar ganchos. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Se utiliza para limpiar los valores de configuración y anular el registro de los ganchos. |

*Nota: La función principal del módulo (actualizar tipos de cambio) se inicia mediante su controlador frontal `cronjob.php`, que se llama externamente, en lugar de a través de un gancho estándar de PrestaShop.*

## 5. Soporte Oficial y Actualizaciones

Para soporte oficial, actualizaciones y para descargar la última versión del módulo "Banco de Italia (Banca d'Italia) - tipos de cambio", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y configuración del módulo.

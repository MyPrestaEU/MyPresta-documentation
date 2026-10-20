---
title: "Banco de Israel - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Banco de Israel - tipos de cambio de divisas' de MyPresta.eu."
sidebar:
  label: "Banco de Israel - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Bank of Israel - currency exchange rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-israel-currency-exchange-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/bank-of-israel-currency-exchange-rates/)
>
> ---


# Banco de Israel - tipos de cambio de divisas

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para obtener datos externos. Su entorno de alojamiento también debe ser compatible con los trabajos CRON para las actualizaciones automatizadas.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" para acceder a la configuración del módulo. Esta es la pantalla principal donde configurará cómo el módulo obtiene y aplica los tipos de cambio.

#### **Actualizaciones de MyPresta.eu**

-   **Qué hace este ajuste:** Esta sección proporciona información sobre las actualizaciones de MyPresta.eu, incluyendo la versión actual del módulo y las actualizaciones disponibles. Le ayuda a mantener su módulo actualizado.
-   **Efecto de cambiar este ajuste:**
    *   *Cuando hay una actualización disponible:* Verá una notificación y un enlace para descargar la última versión desde su cuenta MyPresta.eu.
    *   *Cuando no hay una actualización disponible:* La sección simplemente mostrará su versión actual.
-   **Valor recomendado:** Mantenga siempre sus módulos actualizados para beneficiarse de nuevas características, correcciones de errores y mejoras de seguridad.
-   **Escenario / ejemplo de comerciante:** Revise regularmente esta sección para asegurarse de que su módulo está actualizado, especialmente después de las principales actualizaciones de la versión de PrestaShop.

#### **Intervalo de actualización**

-   **Qué hace este ajuste:** Esto determina con qué frecuencia el módulo intenta obtener y actualizar los tipos de cambio del Banco de Israel.
-   **Efecto de cambiar este ajuste:**
    *   *Establecer un intervalo más corto (por ejemplo, 1 hora):* Los tipos de cambio se actualizarán con mayor frecuencia, asegurando que sus precios estén siempre muy cerca del tiempo real. Esto es bueno para monedas altamente volátiles o ventas internacionales de gran volumen.
    *   *Establecer un intervalo más largo (por ejemplo, 24 horas):* Los tipos de cambio se actualizarán con menos frecuencia. Esto podría ser adecuado si las fluctuaciones monetarias no son una preocupación importante para su negocio o si prefiere llamadas externas menos frecuentes.
-   **Valor recomendado:** "24 horas" para la mayoría de las tiendas. Si tiene un alto volumen de ventas con clientes internacionales y tipos de cambio que cambian con frecuencia, considere "12 horas" o "6 horas".
-   **Escenario / ejemplo de comerciante:** Si vende productos electrónicos de alto valor a clientes internacionales, podría elegir "6 horas" para asegurarse de que sus precios reflejen las últimas condiciones del mercado. Para una boutique local con ventas internacionales ocasionales, "24 horas" es suficiente.

#### **Margen de actualización (%)**

-   **Qué hace este ajuste:** Esto le permite añadir un margen porcentual a los tipos de cambio obtenidos del Banco de Israel. Este margen se aplica además del tipo oficial.
-   **Efecto de cambiar este ajuste:**
    *   *Establecer un margen positivo (por ejemplo, 2%):* Sus precios convertidos en otras monedas serán ligeramente superiores al tipo de cambio oficial directo, lo que le ayudará a cubrir posibles tarifas de transacción, costos de conversión de moneda o simplemente a aumentar su margen de beneficio.
    *   *Establecer un margen cero (0%):* Sus precios reflejarán el tipo de cambio oficial exacto sin ningún recargo adicional.
-   **Valor recomendado:** "0" si desea tipos oficiales exactos. Un pequeño valor positivo (por ejemplo, "1" o "2") a menudo se recomienda para cubrir posibles tarifas bancarias o proporcionar un colchón contra fluctuaciones menores.
-   **Escenario / ejemplo de comerciante:** Si su pasarela de pago cobra una tarifa del 1.5% por transacciones internacionales, establecer un margen del "1.5" o "2" por ciento puede ayudarle a absorber ese costo sin afectar el precio base de su producto en su moneda predeterminada.

#### **Monedas a actualizar**

-   **Qué hace este ajuste:** Esta es una lista de todas las monedas actualmente activas en su tienda PrestaShop. Puede seleccionar cuáles de estas monedas deben tener sus tipos de cambio actualizados automáticamente por este módulo.
-   **Efecto de cambiar este ajuste:**
    *   *Seleccionar una moneda (casilla marcada):* El módulo obtendrá el tipo de cambio para esta moneda (en relación con ILS) del Banco de Israel y lo actualizará en su tienda.
    *   *Deseleccionar una moneda (casilla desmarcada):* El módulo ignorará esta moneda, y su tipo de cambio *no* se actualizará automáticamente. Tendría que actualizarlo manualmente si fuera necesario.
-   **Valor recomendado:** Seleccione todas las monedas que utiliza activamente para ventas internacionales y que desea mantener actualizadas. Asegúrese de que su moneda predeterminada (por ejemplo, ILS) esté configurada correctamente en PrestaShop.
-   **Escenario / ejemplo de comerciante:** Si vende a clientes en EE. UU., Europa y el Reino Unido, marcaría las casillas de USD, EUR y GBP. Si solo vende localmente en ILS y ocasionalmente a EE. UU., podría marcar solo USD.

#### **URL del trabajo CRON**

-   **Qué hace este ajuste:** Esto muestra la URL única que debe configurarse como un trabajo CRON en su servidor web. Un trabajo CRON es una tarea programada que le indica a su servidor que visite esta URL a intervalos regulares, lo que activa el módulo para obtener y actualizar los tipos de cambio automáticamente.
-   **Efecto de cambiar este ajuste:** Esto no es un ajuste que usted cambie, sino una URL que usted *usa*.
    *   *Cuando el trabajo CRON está configurado correctamente:* El módulo se ejecutará automáticamente en su "Intervalo de actualización" especificado, manteniendo sus tipos de cambio actualizados sin ninguna intervención manual.
    *   *Cuando el trabajo CRON NO está configurado:* Los tipos de cambio *no* se actualizarán automáticamente. Tendría que visitar manualmente esta URL en su navegador (lo cual no se recomienda para uso regular) o actualizar manualmente los tipos en PrestaShop.
-   **Valor recomendado:** Copie esta URL y configúrela como un trabajo CRON en su panel de alojamiento (por ejemplo, cPanel, Plesk o a través de SSH). La frecuencia del trabajo CRON debe coincidir o ser ligeramente más frecuente que la configuración de su "Intervalo de actualización". Por ejemplo, si su intervalo de actualización es de 24 horas, configure el trabajo CRON para que se ejecute una vez cada 24 horas.
-   **Escenario / ejemplo de comerciante:** Después de configurar todos los demás ajustes, copie esta URL y péguela en el programador de trabajos CRON de su proveedor de alojamiento. Configúrelo para que se ejecute diariamente en un momento de bajo tráfico (por ejemplo, a las 3 AM).

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Actualizaciones de MyPresta.eu | N/A | Muestra la versión del módulo y la disponibilidad de actualizaciones. |
| Configuración del Módulo | Intervalo de actualización | 24 horas | Con qué frecuencia se obtienen los tipos de cambio (por ejemplo, 6, 12, 24 horas). |
| Configuración del Módulo | Margen de actualización (%) | 0-2% | Añade un recargo porcentual a los tipos de cambio obtenidos. |
| Configuración del Módulo | Monedas a actualizar | Todas las monedas activas | Selecciona qué monedas se actualizarán automáticamente. |
| Configuración del Módulo | URL del trabajo CRON | N/A | URL para configurar en su servidor para actualizaciones automatizadas. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Mis tipos de cambio no se actualizan automáticamente. ¿Qué debo hacer?**
R:

1.  **Verifique el trabajo CRON:** La razón más común es un trabajo CRON configurado incorrectamente o faltante. Vuelva a verificar la URL del trabajo CRON proporcionada en la configuración del módulo y asegúrese de que esté configurada correctamente en su servidor de alojamiento para que se ejecute con la frecuencia deseada.
2.  **Configuración del módulo:** Verifique que el "Intervalo de actualización" esté configurado y que las "Monedas a actualizar" deseadas estén marcadas en la configuración del módulo.
3.  **Acceso al servidor:** Asegúrese de que su servidor pueda realizar solicitudes externas a la API del Banco de Israel. A veces, los cortafuegos o la configuración de seguridad pueden bloquear esto. Póngase en contacto con su proveedor de alojamiento si sospecha esto.
4.  **Caché de PrestaShop:** Borre la caché de su PrestaShop (Parámetros Avanzados > Rendimiento > Borrar caché) después de realizar cualquier cambio en la configuración del módulo.

**P: ¿Puedo anular manualmente un tipo de cambio después de que el módulo lo actualice?**
R: Sí, puede hacerlo. Después de que el módulo se ejecute, los tipos se almacenan en la configuración de moneda estándar de PrestaShop (Internacional > Monedas). Puede editar manualmente el tipo de cambio de una moneda específica allí. Sin embargo, tenga en cuenta que la próxima vez que se ejecute el trabajo CRON, sobrescribirá su cambio manual con el último tipo del Banco de Israel (más su margen).

**P: ¿Qué sucede si la API del Banco de Israel no está disponible temporalmente?**
R: Si el módulo no puede obtener datos, normalmente conservará los últimos tipos de cambio actualizados con éxito. No eliminará ni restablecerá sus tipos a cero. Simplemente lo intentará de nuevo durante la próxima ejecución programada del trabajo CRON.

**P: Mis precios parecen ligeramente incorrectos después de la actualización. ¿Por qué?**
R:

1.  **Margen de actualización:** Verifique la configuración de "Margen de actualización (%)" en la configuración del módulo. Si tiene un margen positivo establecido, sus precios serán ligeramente superiores al tipo oficial directo.
2.  **Redondeo:** La configuración de moneda de PrestaShop también tiene una opción de "Decimales". Asegúrese de que esté configurada apropiadamente para sus monedas para evitar problemas de redondeo inesperados.
3.  **Moneda base:** Asegúrese de que su moneda predeterminada en PrestaShop (Internacional > Monedas) esté configurada correctamente como el Shekel israelí (ILS) si esa es su moneda base para estas actualizaciones.

**P: ¿Cómo configuro un trabajo CRON?**
R: Este proceso varía según el proveedor de alojamiento. Generalmente, iniciará sesión en su panel de control de alojamiento (por ejemplo, cPanel, Plesk). Busque una sección llamada "Trabajos Cron", "Tareas Programadas" o "Tareas Automatizadas". Deberá agregar un nuevo trabajo CRON, especificar la frecuencia (por ejemplo, una vez al día) y pegar la "URL del trabajo CRON" proporcionada por el módulo. Si no está seguro, póngase en contacto con el soporte de su proveedor de alojamiento, proporcionándoles la URL y la frecuencia deseada.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo "Banco de Israel - tipos de cambio de divisas" (`boirates`) sigue una arquitectura de módulo estándar de PrestaShop. Aprovecha una clase de módulo principal (`boirates.php`) para la instalación, desinstalación y manejo de la configuración. Las actualizaciones de los tipos de cambio se activan principalmente a través de un controlador frontal (`cronjob.php`) diseñado para ser llamado por un trabajo CRON del lado del servidor. El módulo obtiene datos XML de la API oficial del Banco de Israel, los analiza y actualiza la tabla `ps_currency` de PrestaShop.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nombre de la clase**: `BoiratesCronjobModuleFrontController` (extiende `ModuleFrontController`)
        -   **Responsabilidad**: Este controlador está diseñado para ser invocado por un trabajo CRON externo. Contiene la lógica central para obtener los tipos de cambio de la API del Banco de Israel, analizar la respuesta XML, aplicar el margen configurado y actualizar la tabla `ps_currency` en PrestaShop. No renderiza ningún contenido de front-office, sino que realiza el procesamiento de datos en segundo plano. Es crucial para la funcionalidad automatizada del módulo.
    -   `controllers/front/index.php`
        -   **Nombre de la clase**: `BoiratesIndexModuleFrontController` (extiende `ModuleFrontController`)
        -   **Responsabilidad**: Este es un marcador de posición o controlador frontal predeterminado. En muchos módulos, si no se enruta una acción específica, se podría llamar a `index.php`. Para este módulo, su función principal es probablemente evitar la lista de directorios o proporcionar una respuesta predeterminada mínima si se accede directamente sin parámetros específicos. La lógica central reside en `cronjob.php`.
-   **Controladores de Administración de Back-Office**:

    -   Ninguno. Toda la configuración se maneja directamente dentro del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Principales (`classes/`)

-   Ninguno. La lógica del módulo está encapsulada principalmente dentro del archivo principal `boirates.php` y el `BoiratesCronjobModuleFrontController`. La interacción de datos es directa con la clase `Currency` de PrestaShop y la tabla `ps_configuration`.

### 4.4 Activos JavaScript (`views/js/`)

-   Ninguno. El módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   Ninguno. El módulo no incluye ningún archivo CSS personalizado.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `views/templates/admin/admin.tpl`
        -   **Propósito**: Esta plantilla es renderizada por el método `getContent()` del archivo del módulo `boirates.php`. Define la estructura y el diseño de la página de configuración del módulo en el Back Office de PrestaShop. Incluye los elementos del formulario para los ajustes `mypresta_updates`, `update_`, `updatev_` y `currency_`, así como la visualización de la URL del trabajo CRON.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de la Base de Datos**:

    -   El módulo no crea ninguna tabla SQL personalizada.
    -   Interactúa con la tabla estándar `ps_configuration` de PrestaShop para almacenar su configuración (por ejemplo, `BOIRATES_UPDATE_INTERVAL`, `BOIRATES_UPDATE_MARGIN`, `BOIRATES_CURRENCIES_TO_UPDATE`).
    -   Actualiza la columna `exchange_rate` en la tabla `ps_currency` para las monedas seleccionadas.
-   **Tabla de Hooks Registrados**:
    El módulo no registra explícitamente ningún hook de visualización de front-office (como `displayHeader`, `displayRightColumn`, `displayProductButtons`, `displayFooter`) en su método `install()` para renderizar contenido. Su función principal es el procesamiento de datos en segundo plano.
    Probablemente utiliza hooks internos de PrestaShop para su funcionalidad principal, como:

    | Nombre del Hook | Momento de Ejecución | Propósito Técnico |
    | --- | --- | --- |
    | `actionModuleInstall` | Durante la instalación del módulo | Establece los valores de configuración predeterminados y registra los elementos necesarios. |
    | `actionModuleUninstall` | Durante la desinstalación del módulo | Limpia los valores de configuración. |
    | `displayBackOfficeHeader` | Renderiza contenido en la cabecera del Back Office | Potencialmente utilizado para añadir CSS/JS o notificaciones, aunque no se detecta explícitamente en el inventario. |

## 5. Soporte Oficial y Actualizaciones

Para soporte oficial, actualizaciones y para descargar las últimas versiones del módulo "Banco de Israel - tipos de cambio de divisas", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con la funcionalidad y compatibilidad del módulo.

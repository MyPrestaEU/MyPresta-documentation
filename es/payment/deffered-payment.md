---
title: "Pago aplazado - Manual del comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Pago aplazado de MyPresta.eu."
sidebar:
  label: "Pago aplazado - Manual del comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Deffered Payment en MyPresta.eu](https://mypresta.eu/modules/payment-process/deffered-payment.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/deffered-payment/)
>
> ---


# Pago aplazado

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop en sí y generalmente suficientes para este módulo. No se necesitan extensiones inusuales.

## 2. Recorrido completo por la configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Pago aplazado)

Esta es la pantalla de configuración principal donde se define el comportamiento central del módulo Pago aplazado.

- **Ubicación del menú:** Back Office > Módulos > Gestor de módulos > Buscar "Pago aplazado" > Hacer clic en "Configurar"

#### Ajustes generales

| Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- |
| **Activar Pago aplazado** | SÍ | **Qué hace este ajuste:** Este es el interruptor maestro del módulo.   **Efecto de cambiar este ajuste:**   *Cuando está activado:* La opción de Pago aplazado estará disponible en la caja para los clientes elegibles.   *Cuando está desactivado:* La opción de Pago aplazado estará oculta para todos los clientes, independientemente de otros ajustes.   **Valor recomendado:** SÍ (para usar el módulo).   **Escenario del comerciante:** Actívelo cuando esté listo para ofrecer este método de pago. |
| **Grupos de clientes permitidos** | (Seleccionar grupos relevantes) | **Qué hace este ajuste:** Determina qué grupos de clientes pueden ver y usar la opción de Pago aplazado.   **Efecto de cambiar este ajuste:**   *Cuando se selecciona:* Solo los clientes que pertenecen a los grupos elegidos verán Pago aplazado en la caja.   *Cuando no se selecciona:* Los clientes de los grupos no seleccionados no verán esta opción.   **Valor recomendado:** Seleccionar grupos específicos (por ejemplo, "Mayoristas", "Clientes VIP"). Evite "Todos los clientes" a menos que tenga la intención de ofrecer el pago aplazado a todo el mundo.   **Escenario del comerciante:** Tiene un grupo de "Clientes B2B". Seleccione solo este grupo para que solo sus clientes comerciales puedan usar el pago aplazado. |
| **Días de vencimiento del pago** | 30 | **Qué hace este ajuste:** Define el número de días después de realizar un pedido en que vence el pago.   **Efecto de cambiar este ajuste:** Este valor se utilizará para calcular la fecha de vencimiento del pago que se muestra al cliente y para el seguimiento interno.   **Valor recomendado:** 30 (común para términos netos de 30 días), 7, 14, 60, etc., según su política comercial.   **Escenario del comerciante:** Establezca 30 para los términos de pago "Neto 30". |
| **Total mínimo del pedido para Pago aplazado** | 0.00 | **Qué hace este ajuste:** Establece un valor mínimo de pedido (en su moneda predeterminada) que un pedido debe cumplir para calificar para el pago aplazado.   **Efecto de cambiar este ajuste:**   *Si el total del pedido es inferior a este valor:* El Pago aplazado no estará disponible, incluso para grupos de clientes elegibles.   *Si el total del pedido es superior o igual a este valor:* El Pago aplazado estará disponible (si se cumplen otras condiciones).   **Valor recomendado:** 0.00 (sin mínimo) o un valor específico (por ejemplo, 100.00 para B2B).   **Escenario del comerciante:** Solo desea ofrecer el pago aplazado para pedidos grandes, por lo que lo establece en 500.00. |
| **Estado del pedido para Pago aplazado** | Pendiente de pago aplazado | **Qué hace este ajuste:** Especifica el estado inicial del pedido que se asignará a los pedidos realizados utilizando el método de Pago aplazado.   **Efecto de cambiar este ajuste:** Este estado será visible en su lista de pedidos del Back Office y para el cliente en su historial de pedidos. Le ayuda a identificar rápidamente los pedidos pendientes de pago.   **Valor recomendado:** Cree un estado específico como "Pendiente de pago aplazado" o "Pago vencido" en **Estados de pedido** (Back Office > Parámetros de la tienda > Configuración de pedidos > Estados) y selecciónelo aquí.   **Escenario del comerciante:** Desea un estado claro para diferenciar estos pedidos de "Pendiente de transferencia bancaria" o "Pago aceptado". |
| **URL de Cron Job** | (URL mostrada) | **Qué hace este ajuste:** Esta URL se utiliza para activar tareas automatizadas relacionadas con los pagos aplazados (por ejemplo, verificar fechas de vencimiento, enviar recordatorios, si tales características están implementadas o extendidas).   **Efecto de cambiar este ajuste:** Este es un campo de solo lectura. Debe configurar un cron job en su servidor para visitar esta URL regularmente (por ejemplo, una vez al día).   **Valor recomendado:** Copie esta URL y agréguela al programador de cron jobs de su servidor.   **Escenario del comerciante:** Desea automatizar cualquier proceso en segundo plano que el módulo pueda tener, como actualizar estados de pedidos o enviar notificaciones. |

#### Productos objetivo (elegibilidad de productos específicos)

Esta sección le permite restringir el pago aplazado a productos o categorías específicas.

| Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- |
| **Aplicar solo a productos específicos** | NO | **Qué hace este ajuste:** Determina si la opción de pago aplazado se limita a pedidos que contienen solo productos específicos.   **Efecto de cambiar este ajuste:**   *Cuando está activado:* La opción "Pago aplazado" solo aparecerá en la caja si *todos* los productos del carrito están en su lista aprobada.   *Cuando está desactivado:* El módulo se aplicará en función de los grupos de clientes y el total mínimo del pedido, independientemente de los productos específicos.   **Valor recomendado:** NO (para uso general) o SÍ (para escenarios muy específicos).   **Escenario del comerciante:** Solo ofrece pago aplazado para sus productos de "Servicios Premium" de alto valor. Habilita esto y añade esos productos a continuación. |
| **Productos permitidos para pago aplazado** | (Vacío) | **Qué hace este ajuste:** Si "Aplicar solo a productos específicos" está activado, este campo le permite buscar y añadir productos específicos.   **Efecto de cambiar este ajuste:** Solo los pedidos que contengan estos productos (y ningún otro) serán elegibles para el pago aplazado.   **Valor recomendado:** Añada productos relevantes si "Aplicar solo a productos específicos" es SÍ.   **Escenario del comerciante:** Añade "Producto A" y "Producto B". Si el carrito de un cliente contiene "Producto A" y "Producto C", el pago aplazado no estará disponible. Si solo contiene "Producto A", sí lo estará. |

### 2.2 Pantallas de administración dedicadas y vistas de controlador

El módulo añade varias secciones nuevas a su menú del Back Office de PrestaShop para gestionar los pagos aplazados.

#### 2.2.1 Usuarios de pago aplazado (Back Office > Pago aplazado > Usuarios de pago aplazado)

Esta pantalla le permite gestionar los permisos de clientes individuales para el pago aplazado, anulando o complementando la configuración de los grupos de clientes.

- **Nombre de la pantalla y ubicación del menú:** Back Office > Pago aplazado > Usuarios de pago aplazado
- **Acciones y ajustes disponibles:**
  - **Tabla de listado:** Muestra una lista de clientes a los que se les ha concedido o denegado específicamente el acceso al pago aplazado.
  - **Añadir nuevo / Editar usuario:**
    - **Búsqueda de clientes:** Encuentre un cliente específico por nombre o correo electrónico.
    - **Activar pago aplazado:** Interruptor SÍ/NO para conceder o revocar el acceso al pago aplazado para este cliente individual.
    - **Días de vencimiento del pago (anulación):** Opcionalmente, establezca un número personalizado de días de vencimiento del pago para este cliente específico, anulando la configuración global.
    - **Límite de crédito:** Establezca un importe máximo pendiente (en su moneda predeterminada, basado en `PS_CURRENCY_DEFAULT`) que este cliente puede tener en pedidos de pago aplazado.
  - **Efecto de los cambios:**
    - Añadir un cliente y activar el pago aplazado le concede acceso, incluso si su grupo no está seleccionado en la configuración principal del módulo.
    - Desactivar para un cliente revoca su acceso, incluso si su grupo está seleccionado.
    - Los días de vencimiento personalizados y los límites de crédito se aplican solo a ese cliente específico.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Utilice esta sección para conceder condiciones de pago aplazado especiales a clientes VIP individuales o para bloquear a clientes problemáticos.
  2. Revise regularmente los límites de crédito para los usuarios de pago aplazado de alto volumen.

#### 2.2.2 Registro de actividad de pago aplazado (Back Office > Pago aplazado > Registro de actividad)

Esta pantalla proporciona un registro histórico de acciones y eventos relacionados con los pagos aplazados.

- **Nombre de la pantalla y ubicación del menú:** Back Office > Pago aplazado > Registro de actividad
- **Acciones y ajustes disponibles:**
  - **Tabla de listado:** Muestra un registro de eventos, que podría incluir:
    - Cuándo se realizó un pedido de pago aplazado.
    - Cuándo se marcó un pago como recibido.
    - Cambios en la configuración de usuarios de pago aplazado.
    - Ejecuciones de cron job.
  - **Columnas:** Normalmente incluye Fecha/Hora, Tipo de evento, Pedido/Cliente relacionado, Descripción.
- **Efecto de los cambios:** Este es un registro de solo lectura. No puede cambiar directamente las entradas aquí, pero proporciona información valiosa para la auditoría y la resolución de problemas.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Revise periódicamente el registro para supervisar la actividad de pago aplazado y asegurarse de que todo funciona sin problemas.
  2. Utilícelo para investigar cualquier problema reportado por los clientes con respecto a sus pedidos de pago aplazado.

#### 2.2.3 Panel de control (Back Office > Pago aplazado > Panel de control)

Esta pantalla (probablemente representada por `defpay/controllers/admin/index.php`) normalmente proporcionaría una visión general o un resumen de las actividades de pago aplazado.

- **Nombre de la pantalla y ubicación del menú:** Back Office > Pago aplazado > Panel de control (o elemento de menú principal "Pago aplazado")
- **Acciones y ajustes disponibles:**
  - **Vista de cuadrícula / Gestión:** Esta pantalla probablemente presenta estadísticas clave, pagos pendientes, pagos vencidos o un resumen rápido de los pedidos de pago aplazado. Podría ofrecer filtros o capacidades de búsqueda.
- **Efecto de los cambios:** Este es principalmente un panel de información. Cualquier acción realizada (por ejemplo, marcar un pedido como pagado) normalmente redirigiría a la página de pedido específica o a otra pantalla de gestión.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Utilice esto como su vista general principal para identificar rápidamente los pedidos que requieren atención (por ejemplo, fechas de vencimiento próximas, pagos vencidos).
  2. Supervise el estado general de su sistema de pago aplazado.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
|---|---|---|
| **Configuración del módulo** | Activar Pago aplazado | SÍ | Interruptor maestro para el método de pago. |
| | Grupos de clientes permitidos | (Seleccionar grupos relevantes) | Restringe el acceso a segmentos de clientes específicos. |
| | Días de vencimiento del pago | 30 | Establece el plazo de pago predeterminado en días. |
| | Total mínimo del pedido para Pago aplazado | 0.00 | Valor mínimo del carrito para la elegibilidad del pago aplazado. |
| | Estado del pedido para Pago aplazado | Pendiente de pago aplazado | Estado inicial para los pedidos realizados con este método. |
| | URL de Cron Job | (URL mostrada) | URL para tareas de automatización del lado del servidor. |
| | Aplicar solo a productos específicos | NO | Limita el pago aplazado a productos específicos. |
| | Productos permitidos para pago aplazado | (Vacío) | Lista de productos elegibles si "Aplicar solo a productos específicos" es SÍ. |
| **Usuarios de pago aplazado** | Búsqueda de clientes | N/A | Buscar y gestionar el acceso de clientes individuales. |
| | Activar Pago aplazado (por usuario) | SÍ/NO | Anulación individual para el acceso al pago aplazado. |
| | Días de vencimiento del pago (anulación) | (Vacío para global) | Condiciones de pago personalizadas para un cliente específico. |
| | Límite de crédito | (Vacío para sin límite) | Importe máximo pendiente para un cliente específico. |
| **Registro de actividad** | N/A | N/A | Registro de solo lectura de eventos de pago aplazado. |
| **Panel de control** | N/A | N/A | Resumen de pedidos y estadísticas de pago aplazado. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: ¿Por qué no aparece el Pago aplazado para mis clientes en la caja?**
R:

1.  **¿Está el módulo activado?** Compruebe "Activar Pago aplazado" en la configuración del módulo.
2.  **¿Son correctos los grupos de clientes?** Asegúrese de que el cliente ha iniciado sesión y pertenece a uno de los "Grupos de clientes permitidos" seleccionados en la configuración del módulo.
3.  **Total mínimo del pedido:** ¿El total del carrito supera el "Total mínimo del pedido para Pago aplazado"?
4.  **Productos específicos:** Si "Aplicar solo a productos específicos" está activado, ¿el carrito *solo* contiene productos de su lista aprobada?
5.  **Configuración de usuario individual:** Compruebe "Usuarios de pago aplazado" para ver si el cliente ha sido deshabilitado individualmente o tiene anulaciones específicas.
6.  **Caché:** Borre la caché de su PrestaShop (Parámetros avanzados > Rendimiento) y la caché de su navegador.

**P: ¿Cómo cambio el estado del pedido una vez que se recibe un pago aplazado?**
R: Deberá actualizar manualmente el estado del pedido en el Back Office de PrestaShop. Vaya a **Pedidos > Pedidos**, busque el pedido relevante y cambie su estado de "Pendiente de pago aplazado" (o lo que haya configurado) a "Pago aceptado" o "Entregado" según corresponda.

**P: ¿Puedo establecer diferentes días de vencimiento de pago para diferentes clientes?**
R: ¡Sí! Utilice la pantalla "Usuarios de pago aplazado". Puede buscar un cliente específico y establecer un "Días de vencimiento del pago (anulación)" personalizado para él, que tendrá prioridad sobre la configuración global.

**P: ¿Para qué sirve la URL de Cron Job y necesito configurarla?**
R: La URL de Cron Job es para tareas automatizadas que el módulo podría realizar en segundo plano (por ejemplo, verificar pagos vencidos, enviar notificaciones, si están implementadas). Si bien el módulo podría funcionar sin ella para el procesamiento básico de pagos, se recomienda encarecidamente configurarla en su servidor para garantizar que todas las funciones automatizadas funcionen correctamente. Su proveedor de alojamiento web o un desarrollador pueden ayudarle a configurar un cron job para visitar esta URL diariamente.

**P: El módulo está instalado, pero no veo el elemento de menú "Pago aplazado" en el Back Office.**
R:

1.  **Permisos:** Compruebe los permisos de su empleado (Parámetros avanzados > Equipo > Empleados > Editar su perfil > pestaña Permisos). Asegúrese de tener acceso al módulo "Pago aplazado" y a sus controladores de administración asociados.
2.  **Caché:** Borre la caché de su PrestaShop (Parámetros avanzados > Rendimiento).

## 4. Guía para desarrolladores y webmasters (arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo Pago aplazado para desarrolladores y webmasters.

### 4.1 Resumen de la arquitectura

El módulo Pago aplazado sigue el patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop. Se integra como un módulo de pago, extendiendo `PaymentModule` y proporcionando controladores de administración personalizados para gestionar usuarios y registros de pago aplazado. Aprovecha el sistema de configuración de PrestaShop para los ajustes y los hooks para la visualización en el front office y la integración de pedidos en el back office. El módulo introduce tablas de base de datos personalizadas (`defpay_log`, `defpayuser`) para almacenar datos específicos de pago aplazado.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front Office

- `defpay/controllers/front/cron.php`
  - **Nombre de la clase:** `DefPayCronModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Gestiona la ejecución de las tareas del cron job. Este controlador se accede a través de la `URL de Cron Job` proporcionada en la configuración del módulo. Está diseñado para ser llamado periódicamente por un programador de cron del servidor para realizar operaciones en segundo plano como verificar las fechas de vencimiento de los pagos, actualizar los estados de los pedidos o activar notificaciones.
- `defpay/controllers/front/index.php`
  - **Nombre de la clase:** `DefPayIndexModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Un controlador frontal de marcador de posición o predeterminado. A menudo se utiliza para el enrutamiento básico del módulo o si el módulo necesita un punto de entrada frontal predeterminado que no se corresponda directamente con una acción específica. En este módulo, podría no tener una función directa orientada al usuario.
- `defpay/controllers/front/statement.php`
  - **Nombre de la clase:** `DefPayStatementModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Probablemente gestiona la visualización o generación de extractos de pago aplazado para los clientes. Podría ser una página en el área de la cuenta del cliente que muestre los pagos pendientes o un enlace para descargar una factura.
- `defpay/controllers/front/validation.php`
  - **Nombre de la clase:** `DefPayValidationModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** El controlador principal de validación de pagos. Cuando un cliente selecciona "Pago aplazado" en la caja y confirma el pedido, este controlador procesa el pedido, establece el estado de pedido apropiado y redirige al cliente a la página de confirmación del pedido.

#### Controladores de administración del Back Office

- `defpay/controllers/admin/AdminDefPayActivityLog.php`
  - **Nombre de la clase:** `AdminDefPayActivityLogController` (extiende `ModuleAdminController`)
  - **Nombre de la pestaña:** `Registro de actividad de pago aplazado`
  - **Entidad gestionada:** `defpay_log` (tabla de base de datos personalizada)
  - **Responsabilidad:** Proporciona una interfaz de gestión de listas para la tabla `defpay_log`. Muestra un registro histórico de eventos relacionados con los pagos aplazados, como la realización de pedidos, los cambios de estado o las acciones del cron job.
- `defpay/controllers/admin/AdminDefPayUsers.php`
  - **Nombre de la clase:** `AdminDefPayUsersController` (extiende `ModuleAdminController`)
  - **Nombre de la pestaña:** `Usuarios de pago aplazado`
  - **Entidad gestionada:** `defpayuser` (tabla de base de datos personalizada)
  - **Responsabilidad:** Gestiona la configuración individual de los clientes para el pago aplazado. Permite a los administradores activar/desactivar el pago aplazado para clientes específicos, establecer días de vencimiento personalizados y definir límites de crédito. Interactúa con la tabla `ps_currency` (a través de `PS_CURRENCY_DEFAULT`) para la moneda del límite de crédito.
- `defpay/controllers/admin/index.php`
  - **Nombre de la clase:** `AdminDefPayDashboardController` (probablemente, extiende `ModuleAdminController`)
  - **Nombre de la pestaña:** `Panel de control de pago aplazado` (o elemento de menú principal)
  - **Entidad gestionada:** No hay una única entidad directa; agrega datos.
  - **Responsabilidad:** Sirve como el panel de control principal o la visión general del módulo Pago aplazado en el Back Office. Probablemente muestra estadísticas clave, resúmenes de pagos pendientes/vencidos y enlaces rápidos a otras secciones de gestión.

### 4.3 Clases y modelos principales (`classes/`)

La información del módulo proporcionada no indica clases personalizadas en el directorio `classes/`. Esto sugiere que la lógica central del módulo, incluidas las definiciones de `ObjectModel` para `defpay_log` y `defpayuser`, podría estar directamente incrustada en el archivo principal `defpay/cronjob.php` o dentro de los propios controladores de administración. Este es un enfoque menos común pero a veces utilizado para módulos más simples.

Si `defpay_log` y `defpayuser` son de hecho tablas personalizadas, sus definiciones de `ObjectModel` (por ejemplo, las clases `DefPayLog` y `DefPayUser`) se encontrarían típicamente en `classes/`. Si no, es probable que estén definidas en línea o gestionadas directamente a través de llamadas a la clase `Db`.

### 4.4 Activos JavaScript (`views/js/`)

- `defpay/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Alcance:** Back office.
  - **Descripción:** Probablemente proporciona funcionalidad para gestionar plantillas de correo electrónico dentro de la configuración del módulo o pantallas de administración específicas. Esto podría incluir campos de formulario dinámicos, previsualización de plantillas o guardar contenido de plantillas.
- `defpay/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back office (por ejemplo, `AdminDefPayUsers` para búsqueda de clientes, o configuración del módulo para búsqueda de productos).
  - **Descripción:** Implementa una función de autocompletado para entradas de búsqueda, como encontrar clientes o productos. Escucha la entrada del usuario, realiza llamadas AJAX para obtener sugerencias y las muestra en un menú desplegable.
- `defpay/tools/browser-demo-simulator.js`
  - **Alcance:** Potencialmente ambos, pero más probable para desarrollo/pruebas.
  - **Descripción:** Un script de utilidad, posiblemente para simular el comportamiento del navegador o las interacciones del módulo con fines de prueba. No se utiliza normalmente en un entorno de producción.
- `defpay/views/js/adminDefPayActivityPreview.js`
  - **Alcance:** Back office (`AdminDefPayActivityLog`).
  - **Descripción:** Proporciona funciones interactivas para el registro de actividad, como expandir entradas de registro, filtrar o previsualizar detalles de una actividad.
- `defpay/views/js/adminDefPayCollections.js`
  - **Alcance:** Back office (probablemente relacionado con la gestión de cobros de pagos aplazados).
  - **Descripción:** Implementa la lógica JavaScript para una interfaz de gestión de "cobros", que podría implicar marcar pagos como recibidos, enviar recordatorios o gestionar cuentas vencidas.
- `defpay/views/js/adminDefPayDashboard.js`
  - **Alcance:** Back office (Panel de control).
  - **Descripción:** Impulsa los elementos interactivos del panel de control de pago aplazado, como gráficos dinámicos, filtrado de datos o actualizaciones AJAX para estadísticas.
- `defpay/views/js/adminDefPayPortfolio.js`
  - **Alcance:** Back office.
  - **Descripción:** Probablemente relacionado con la gestión de una "cartera" de cuentas u órdenes de pago aplazado, posiblemente ofreciendo filtrado avanzado, informes o acciones masivas.
- `defpay/views/js/defpay_target_products.js`
  - **Alcance:** Back office (Configuración del módulo).
  - **Descripción:** Proporciona la funcionalidad JavaScript para la sección "Productos objetivo" en la configuración del módulo, lo que permite la búsqueda, selección y eliminación de productos para la elegibilidad de pago aplazado.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `defpay/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Alcance:** Back office.
  - **Descripción:** Estilos para la interfaz de gestión de plantillas de correo electrónico, asegurando una apariencia consistente dentro del panel de administración de PrestaShop.
- `defpay/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back office.
  - **Descripción:** Estilos para las sugerencias de búsqueda de autocompletado, asegurando que sean visualmente distintas y fáciles de usar.
- `defpay/views/css/admin_defpay.css`
  - **Alcance:** Back office.
  - **Descripción:** Estilo general para las pantallas de administración personalizadas del módulo (Panel de control, Usuarios, Registro de actividad), asegurando un diseño cohesivo dentro del Back Office de PrestaShop.
- `defpay/views/css/defpay.css`
  - **Alcance:** Front office.
  - **Descripción:** Estilo general para los componentes del front office del módulo, como la visualización de la opción de pago en la página de pago o las secciones de la cuenta del cliente.
- `defpay/views/css/statement-document.css`
  - **Alcance:** Front office (para impresión/PDF).
  - **Descripción:** Estilos específicos para la versión imprimible o PDF de un extracto de pago aplazado, optimizados para el diseño del documento.
- `defpay/views/css/statement.css`
  - **Alcance:** Front office.
  - **Descripción:** Estilos para la visualización en pantalla de los extractos de pago aplazado en el área de la cuenta del cliente.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

- `defpay/views/templates/hook/confirmation.tpl`
  - **Hook:** `displayOrderConfirmation` (o similar).
  - **Salida:** Contenido mostrado en la página de confirmación del pedido después de que se realiza un pedido de pago aplazado, informando al cliente sobre las condiciones de pago.
- `defpay/views/templates/hook/displayAdminOrder16.tpl`
  - **Hook:** `displayAdminOrder` (PrestaShop 1.6).
  - **Salida:** Añade un bloque de información o acciones relacionadas con el pago aplazado en la página de detalles del pedido en el Back Office de PrestaShop 1.6.
- `defpay/views/templates/hook/displayAdminOrder17.tpl`
  - **Hook:** `displayAdminOrder` (PrestaShop 1.7+).
  - **Salida:** Similar a `displayAdminOrder16.tpl`, pero adaptado para la página de detalles del pedido del Back Office de PrestaShop 1.7+, mostrando el estado del pago aplazado, la fecha de vencimiento y posiblemente acciones de cobro de pagos.
- `defpay/views/templates/hook/displayCustomerAccount.tpl`
  - **Hook:** `displayCustomerAccount` o `displayMyAccountBlock`.
  - **Salida:** Añade un enlace o bloque a la página "Mi cuenta" del cliente, que podría enlazar con su extracto o historial de pagos aplazados.
- `defpay/views/templates/hook/displayOrderDetail.tpl`
  - **Hook:** `displayOrderDetail` (front office).
  - **Salida:** Muestra información específica del pago aplazado (por ejemplo, fecha de vencimiento, estado del pago) dentro de la página de detalles del pedido del front office del cliente.
- `defpay/views/templates/hook/payment.tpl`
  - **Hook:** `displayPayment` (o `paymentOptions` para PS 1.7+).
  - **Salida:** Renderiza la opción "Pago aplazado" en la página de selección de pago de la caja.

#### Plantillas de administración (`views/templates/admin/`)

- `defpay/views/templates/admin/cron_setup.tpl`
  - **Propósito:** Probablemente se utiliza dentro de la página de configuración principal del módulo (`getContent()`) para mostrar la URL de Cron Job e instrucciones.
- `defpay/views/templates/admin/defpay_target_products.tpl`
  - **Propósito:** Renderiza la interfaz para seleccionar productos específicos elegibles para el pago aplazado dentro de la configuración del módulo.

#### Plantillas del Front Office (`views/templates/front/`)

- `defpay/views/templates/front/statement_preview.tpl`
  - **Propósito:** Muestra una vista previa de un extracto de pago aplazado al cliente en el front office.
- `defpay/views/templates/front/validation.tpl`
  - **Propósito:** La plantilla renderizada por el controlador frontal `validation.php`, típicamente un mensaje de confirmación o un resumen después de que un pedido de pago aplazado se ha realizado con éxito.

#### Plantillas PDF (`views/templates/pdf/`)

- `defpay/views/templates/pdf/statement.tpl`
  - **Propósito:** Plantilla utilizada para generar una versión PDF de un extracto o factura de pago aplazado.

#### Plantillas de biblioteca (`defpay/lib/emailTemplatesManager/views/` y `defpay/lib/searchTool/views/`)

Estas plantillas forman parte de bibliotecas incrustadas dentro del módulo:

- `defpay/lib/emailTemplatesManager/views/buttonManager.tpl`
- `defpay/lib/emailTemplatesManager/views/createTemplateForm.tpl`
- `defpay/lib/emailTemplatesManager/views/editTemplateForm.tpl`
- `defpay/lib/emailTemplatesManager/views/mainForm.tpl`
- `defpay/lib/emailTemplatesManager/views/selectInput.tpl`
  - **Propósito:** Estas plantillas se utilizan para renderizar los diversos componentes de la interfaz de gestión de plantillas de correo electrónico en el Back Office.
- `defpay/lib/searchTool/views/scripts.tpl`
  - **Propósito:** Probablemente incluye la inicialización o configuración de JavaScript para la herramienta de búsqueda de autocompletado.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

- `ps_defpay_log` (o `defpay_log`):
  - Almacena entradas del registro de actividad relacionadas con los pagos aplazados.
  - Los campos probablemente incluyen: `id_defpay_log`, `id_order`, `id_customer`, `event_type`, `description`, `date_add`.
- `ps_defpayuser` (o `defpayuser`):
  - Almacena la configuración individual de pago aplazado para los clientes.
  - Los campos probablemente incluyen: `id_defpayuser`, `id_customer`, `deferred_payment_enabled` (booleano), `payment_due_days_override` (entero), `credit_limit` (decimal), `date_add`, `date_upd`.
- `ps_configuration`:
  - La configuración del módulo se almacena aquí con claves como `DEFPAY_ENABLED`, `DEFPAY_GROUPS`, `DEFPAY_DUE_DAYS`, `DEFPAY_MIN_TOTAL`, `DEFPAY_ORDER_STATUS`, `DEFPAY_CRON_URL`, `DEFPAY_TARGET_PRODUCTS_ENABLED`, `DEFPAY_TARGET_PRODUCTS_LIST`.

#### Tabla de hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayPayment` (PS 1.6) | En el paso de selección de pago de la caja. | Renderiza la opción "Pago aplazado". |
| `paymentOptions` (PS 1.7+) | En el paso de selección de pago de la caja. | Renderiza la opción "Pago aplazado" (hook moderno). |
| `displayOrderConfirmation` | Después de que un pedido se ha realizado con éxito. | Muestra los detalles del pago aplazado en la página de confirmación. |
| `displayCustomerAccount` / `displayMyAccountBlock` | En la página "Mi cuenta" del cliente. | Añade un enlace a los extractos o historial de pagos aplazados. |
| `displayOrderDetail` | En la página de detalles del pedido del front office del cliente. | Muestra información específica del pago aplazado para un pedido. |
| `displayAdminOrder` (PS 1.6) | En la página de detalles del pedido en el Back Office (PS 1.6). | Inyecta el estado del pago aplazado y las herramientas de gestión. |
| `displayAdminOrder` (PS 1.7+) | En la página de detalles del pedido en el Back Office (PS 1.7+). | Inyecta el estado del pago aplazado y las herramientas de gestión. |
| `actionValidateOrder` | Después de que un pedido se ha validado con éxito. | Se utiliza para realizar acciones como establecer el estado inicial del pedido de pago aplazado, registrar el evento o crear una entrada `defpayuser` si es necesario. |
| `actionOrderStatusUpdate` | Cuando se cambia el estado de un pedido. | Se puede utilizar para activar acciones basadas en cambios de estado (por ejemplo, pago recibido, vencido). |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su salida. | Se utiliza para encolar activos CSS y JS del front office. |
| `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice su salida. | Se utiliza para encolar activos CSS y JS del back office. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Allí encontrará sus módulos comprados y acceso a nuestros canales de soporte.

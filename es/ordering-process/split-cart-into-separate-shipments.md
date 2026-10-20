---
title: "Dividir carrito en envíos separados - Manual de comerciante y guía de configuración"
description: ""
sidebar:
  label: "Dividir carrito en envíos separados - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Split cart into separate shipments en MyPresta.eu](https://mypresta.eu/modules/ordering-process/split-cart-into-separate-shipments.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/split-cart-into-separate-shipments/)
>
> ---


# Dividir carrito en envíos separados

## 1. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

El módulo "Dividir carrito en envíos separados" introduce varias pantallas y opciones nuevas y potentes en su Back Office de PrestaShop.

### 1.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Dividir carrito en envíos separados)

Esta es la página de configuración principal a la que accede inmediatamente después de la instalación o haciendo clic en "Configurar" desde el Gestor de módulos. Contiene ajustes generales para el comportamiento del módulo.

- **Activar módulo:**

  - **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar la funcionalidad del módulo en toda su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El módulo dividirá activamente los carritos según sus reglas durante el pago.
    - *Cuando está desactivado:* La lógica de división del módulo se omitirá y PrestaShop volverá a su comportamiento predeterminado de envío único.
  - **Valor recomendado:** SÍ (una vez que haya configurado sus reglas).
  - **Escenario/ejemplo de comerciante:** Podría desactivarlo temporalmente si está realizando mantenimiento o solucionando problemas en otras partes de su proceso de pago.
- **Modo depuración:**

  - **Qué hace este ajuste:** Activa un modo especial que puede mostrar información técnica o registros adicionales para ayudar a identificar problemas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Puede mostrar mensajes de error o pasos de procesamiento detallados en el Front Office (visibles para los clientes) o en la consola de desarrollador de su navegador. Esto es útil para los desarrolladores.
    - *Cuando está desactivado:* El módulo funciona silenciosamente, sin mostrar información de depuración.
  - **Valor recomendado:** NO (desactivar siempre en una tienda de producción en vivo).
  - **Escenario/ejemplo de comerciante:** Si está trabajando con un desarrollador para entender por qué un carrito específico no se divide como se esperaba, podrían pedirle que lo active temporalmente.
- **Mostrar resumen de división en la página de confirmación de pedido:**

  - **Qué hace este ajuste:** Controla si los clientes ven un resumen de cómo se dividió su pedido en diferentes envíos en la página final de confirmación de pedido.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes verán un desglose claro de qué artículos fueron a qué grupo de envío y el transportista elegido para cada uno, confirmando sus selecciones.
    - *Cuando está desactivado:* La página de confirmación de pedido mostrará un resumen estándar sin la información detallada de la división.
  - **Valor recomendado:** SÍ.
  - **Escenario/ejemplo de comerciante:** Habilitar esto mejora la transparencia y asegura a los clientes que sus opciones de envío específicas para cada paquete se aplicaron correctamente.
- **Permitir al cliente elegir puntos de recogida (si corresponde):**

  - **Qué hace este ajuste:** Si tiene transportistas que ofrecen entrega en puntos de recogida (por ejemplo, Mondial Relay, Colissimo Point Relais), este ajuste permite a los clientes seleccionar una ubicación de recogida específica para cada grupo de envío relevante.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Para los transportistas configurados con puntos de recogida, los clientes verán una opción para elegir una ubicación de recogida durante el pago para el envío correspondiente.
    - *Cuando está desactivado:* Los clientes solo podrán seleccionar entrega a domicilio u otras opciones de envío estándar, incluso si los transportistas admiten puntos de recogida.
  - **Valor recomendado:** SÍ (si utiliza transportistas con puntos de recogida).
  - **Escenario/ejemplo de comerciante:** Si ofrece Mondial Relay, habilitar esto permite a los clientes recibir un artículo pesado en un punto de recogida conveniente cerca de su casa o trabajo, mejorando su experiencia.

### 1.2 Pantallas de administración dedicadas: Reglas de envío (Back Office > Envío > Reglas de división de envío)

Esta pantalla es donde define la lógica de cómo los artículos de su carrito deben agruparse en envíos separados. Es el núcleo de la funcionalidad del módulo.

- **Nombre de la pantalla y ubicación del menú:** **Reglas de división de envío** (se encuentra en **Envío** en el menú de su Back Office de PrestaShop).
- **Acciones y ajustes disponibles:**
  - **Tabla de listado de reglas:** Muestra todas sus reglas de agrupación definidas. Cada regla tiene un nombre, estado (activo/inactivo), prioridad y un resumen de sus condiciones y acciones.
  - **Botón "Añadir nueva regla":** Al hacer clic en este botón, puede crear una nueva regla.
  - **Acciones de edición/eliminación:** Para cada regla de la lista, puede editar sus detalles o eliminarla.
  - **Alternar activar/desactivar:** Active o desactive rápidamente una regla sin eliminarla.
  - **Reordenación por arrastrar y soltar:** Las reglas se procesan en orden de su prioridad. Puede arrastrar y soltar reglas para cambiar su orden de ejecución. Las reglas de mayor prioridad se procesan primero.
- **Efecto de los cambios:**
  - **Añadir/Editar reglas:** Impacta directamente cómo se dividen los carritos durante el pago. Una regla bien definida puede asegurar que productos específicos siempre se envíen por separado o juntos.
  - **Activar/Desactivar reglas:** Controla si se aplica la lógica de una regla.
  - **Cambiar prioridad:** Determina qué regla tiene prioridad si varias reglas podrían aplicarse al mismo producto. Las reglas con mayor prioridad (que aparecen más arriba en la lista) se evalúan primero.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. **Identificar necesidades de agrupación:** Piense en sus productos. ¿Tiene artículos de gran tamaño, artículos frágiles, artículos de diferentes almacenes o artículos que requieren un manejo especial?
  2. **Crear reglas:** Para cada necesidad de agrupación, cree una nueva regla.
     - **Condiciones:** Defina *cuándo* se aplica la regla. Esto podría basarse en:
       - **Producto:** Productos específicos, categorías, fabricantes, proveedores o características del producto.
       - **Carrito:** Valor total del carrito, número de artículos, grupos de clientes específicos.
       - **Envío:** Transportistas o zonas específicas.
     - **Acciones:** Defina *qué* hace la regla. Esto podría ser:
       - **Forzar envío separado:** Siempre coloque los artículos coincidentes en su propio grupo de envío.
       - **Forzar mismo envío:** Asegúrese de que los artículos coincidentes siempre permanezcan juntos en un solo envío.
       - **Excluir del procesamiento de reglas:** Evite que otras reglas afecten a estos artículos.
  3. **Establecer prioridad:** Organice sus reglas de las más específicas (por ejemplo, "Cristalería frágil siempre se envía sola") a las más generales (por ejemplo, "Todos los artículos de gran tamaño se envían por separado").
  4. **Probar a fondo:** Utilice una cuenta de cliente de prueba para añadir varias combinaciones de productos al carrito y verifique que la división funciona como se espera durante el pago.

### 1.3 Pantallas de administración dedicadas: Divisiones de envío (Back Office > Envío > Divisiones de envío)

Esta pantalla proporciona una visión general de cómo se han dividido los pedidos por el módulo después de haber sido realizados. Es una herramienta de informes y gestión.

- **Nombre de la pantalla y ubicación del menú:** **Divisiones de envío** (se encuentra en **Envío** en el menú de su Back Office de PrestaShop).
- **Acciones y ajustes disponibles:**
  - **Tabla de listado de divisiones:** Muestra una lista de todos los pedidos que han sido divididos por el módulo.
  - **Referencia del pedido:** Enlaza directamente al pedido original de PrestaShop.
  - **Detalles del grupo de envío:** Proporciona información sobre cada grupo de envío individual dentro de un pedido, incluidos los productos que contiene, el transportista elegido y su estado.
  - **Ver detalles de la división:** Le permite profundizar en una división específica para ver información más granular.
- **Efecto de los cambios:** Esta pantalla es principalmente para visualización y auditoría. No cambia directamente cómo se dividen los carritos futuros aquí. Cualquier cambio que realice (por ejemplo, actualizar un transportista para una división específica) se realizaría normalmente dentro de la vista principal del pedido de PrestaShop, y este módulo reflejaría esos cambios.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  - **Monitorizar pedidos divididos:** Revise regularmente esta pantalla para comprender cómo funcionan sus reglas en la práctica.
  - **Solucionar problemas:** Si un cliente tiene una pregunta sobre su envío, esta pantalla puede ayudarle a ver rápidamente cómo se procesó su pedido en diferentes envíos.
  - **Integración con la gestión de pedidos:** Si bien el módulo crea pedidos estándar de PrestaShop, esta pantalla ofrece una vista consolidada de la lógica de división aplicada a cada pedido.

### 1.4 Pantallas de administración dedicadas: Panel de control (Back Office > Envío > Panel de control de división de envío)

Esta pantalla proporciona una visión general rápida y estadísticas relacionadas con la actividad del módulo.

- **Nombre de la pantalla y ubicación del menú:** **Panel de control de división de envío** (se encuentra en **Envío** en el menú de su Back Office de PrestaShop).
- **Acciones y ajustes disponibles:**
  - **Franja de KPI:** Indicadores clave de rendimiento (KPI) como el total de pedidos divididos, el promedio de envíos por pedido o los ingresos totales de envío de pedidos divididos.
  - **Gráficos y diagramas:** Representaciones visuales de tendencias, como el número de pedidos divididos a lo largo del tiempo, las reglas de división más comunes utilizadas o los transportistas populares para envíos divididos.
  - **Divisiones recientes:** Una lista rápida de los pedidos divididos más recientemente.
- **Efecto de los cambios:** Este es un panel de informes. No se realizan cambios directos en el comportamiento del módulo aquí. Le ayuda a comprender el impacto y el uso del módulo.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  - **Monitorización del rendimiento:** Utilice este panel para evaluar la eficacia de sus reglas de división e identificar cualquier patrón o anomalía.
  - **Planificación estratégica:** Los datos pueden informar decisiones sobre estrategias de envío, asociaciones con transportistas o ajustes del catálogo de productos.

### 1.5 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | Activar módulo | SÍ | Interruptor maestro para la funcionalidad del módulo. |
|  | Modo depuración | NO | Muestra información técnica (solo para desarrolladores). |
|  | Mostrar resumen de división en la página de confirmación de pedido | SÍ | Muestra a los clientes cómo se dividió su pedido. |
|  | Permitir al cliente elegir puntos de recogida | SÍ (si corresponde) | Habilita la selección de puntos de recogida para los transportistas relevantes. |
| **Reglas de división de envío** | Añadir/Editar regla (Condiciones) | N/A | Define *cuándo* se aplica una regla (por ejemplo, por producto, categoría, valor del carrito). |
|  | Añadir/Editar regla (Acciones) | N/A | Define *qué* hace la regla (por ejemplo, forzar envío separado, forzar mismo envío). |
|  | Prioridad de la regla | N/A | Determina el orden en que se procesan las reglas (mayor = primero). |
|  | Activar/Desactivar regla | N/A | Activa o desactiva una regla de agrupación específica. |
| **Divisiones de envío** | Ver pedidos divididos | N/A | Proporciona una lista y detalles de todos los pedidos procesados por el módulo. |
| **Panel de control de división de envío** | KPI, gráficos, divisiones recientes | N/A | Ofrece una visión general de la actividad y el rendimiento del módulo. |

## 2. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

- **P: Mi carrito no se divide, o se divide incorrectamente. ¿Qué debo hacer?**

  - **R:** Primero, verifique si el módulo está activado en su configuración principal. Luego, vaya a **Envío > Reglas de división de envío** y revise sus reglas. Asegúrese de que estén activas y que sus condiciones coincidan correctamente con los productos de su carrito de prueba. Preste mucha atención a la prioridad de las reglas: una regla más general podría estar anulando una más específica. Si tiene el "Modo depuración" activado en la configuración principal del módulo, busque cualquier mensaje durante el pago. Finalmente, borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**).
- **P: ¿Por qué algunos transportistas no aparecen para un grupo de envío específico?**

  - **R:** El módulo respeta las restricciones estándar de transportistas de PrestaShop. Verifique lo siguiente:
    1. **Zonas del transportista:** Asegúrese de que el transportista esté habilitado para la zona de envío del cliente.
    2. **Rangos de peso/precio del transportista:** Verifique que el peso/precio total del *grupo de envío individual* (no de todo el carrito) se encuentre dentro de los rangos definidos por el transportista.
    3. **Asociaciones de transportistas:** Asegúrese de que el transportista esté asociado con los productos de ese grupo de envío (si ha configurado restricciones de transportista específicas para el producto).
    4. **Compatibilidad del módulo:** Algunos módulos de envío de terceros pueden tener su propia lógica que entra en conflicto; verifique si hay incompatibilidades conocidas o póngase en contacto con el soporte.
- **P: ¿Cómo afecta este módulo a mis costos de envío existentes y a las reglas de envío gratuito?**

  - **R:** El módulo agrega los costos de envío. Si un carrito se divide en dos envíos y cada envío tiene un costo de 10 $, el cliente verá un costo total de envío de 20 $. Para el envío gratuito, sus reglas de envío gratuito existentes (por ejemplo, "envío gratuito a partir de X $") se aplicarán a *cada grupo de envío individual* si el módulo lo permite, o al *total general del carrito* dependiendo de cómo estén configuradas sus reglas y cómo se integre el módulo. Es posible que deba ajustar sus reglas de envío gratuito para tener en cuenta los envíos divididos.
- **P: ¿Puedo traducir los textos del módulo a otros idiomas?**

  - **R:** Sí, como la mayoría de los módulos de PrestaShop, puede traducir sus textos del Front Office y del Back Office. Vaya a **Internacional > Traducciones**, seleccione "Traducciones de módulos instalados", elija su tema, seleccione "Dividir carrito en envíos separados" y luego elija el idioma al que desea traducir.
- **P: Después de la instalación, veo una página en blanco o un error. ¿Qué pasa?**

  - **R:** Esto a menudo indica un error de PHP.
    1. **Verifique los registros de errores de PHP:** Su panel de control de alojamiento web generalmente proporciona acceso a los registros de errores de PHP. Busque entradas recientes relacionadas con PrestaShop.
    2. **Habilite el modo de depuración de PrestaShop:** Vaya a `config/defines.inc.php` en su instalación de PrestaShop, busque `define('_PS_MODE_DEV_', false);` y cambie `false` a `true`. Esto mostrará el error en la pantalla.
    3. **Compatibilidad del módulo:** Asegúrese de haber descargado la versión correcta del módulo para su versión de PrestaShop (por ejemplo, PS 8.x, 1.7.x).
    4. **Póngase en contacto con el soporte:** Si no puede resolverlo, proporcione el mensaje de error al soporte de MyPresta.eu.

## 3. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 3.1 Resumen de la arquitectura

El módulo "Dividir carrito en envíos separados" (`multishipsplit`) está construido siguiendo el patrón MVC (Modelo-Vista-Controlador) de PrestaShop, con un uso significativo de hooks y overrides para integrarse profundamente en el proceso de pago. Introduce un robusto motor basado en reglas para la división del carrito, permitiendo condiciones y acciones complejas. La lógica central gira en torno a la división del objeto `Cart` en múltiples entidades `MultishipShipmentGroup`, cada una representando un paquete distinto con su propia selección de transportista. Aprovecha `ObjectModel` para gestionar reglas y datos divididos, y emplea una serie de clases de servicio para manejar la intrincada lógica de evaluación de condiciones, construcción de acciones y presentación de pago. Se utilizan overrides para modificar el comportamiento central de `Cart` y `PaymentModule` para admitir múltiples envíos.

### 3.2 Controladores (`controllers/`)

#### Controladores de Front Office

- `multishipsplit/controllers/front/groups.php`
  - **Nombre de la clase:** `MultishipsplitGroupsModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Maneja las solicitudes AJAX relacionadas con los grupos de envío durante el pago. Esto podría incluir la actualización de las selecciones de transportista para un grupo específico, el recálculo de los costos de envío o la obtención de opciones de puntos de recogida. Procesa los datos `POST` y devuelve respuestas JSON a la página de pago.
- `multishipsplit/controllers/front/index.php`
  - **Nombre de la clase:** `MultishipsplitIndexModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Un controlador de marcador de posición o punto de entrada. Podría usarse para acciones o redirecciones generales del Front Office relacionadas con el módulo, aunque su función principal podría ser mínima si la mayoría de las interacciones son impulsadas por AJAX a través de `groups.php`.
- `multishipsplit/controllers/front/pickup.php`
  - **Nombre de la clase:** `MultishipsplitPickupModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Gestiona las interacciones AJAX específicamente para la selección de puntos de recogida. Probablemente maneja las solicitudes para mostrar los puntos de recogida disponibles para un transportista y una dirección determinados, y para guardar el punto de recogida seleccionado en el carrito o la sesión.

#### Controladores de administración del Back Office

- `multishipsplit/controllers/admin/AdminMultishipRules.php`
  - **Nombre de la clase:** `AdminMultishipRulesController` (extiende `ModuleAdminController`)
  - **Nombre de la pestaña:** "Reglas de división de envío"
  - **Entidad gestionada:** `MultishipGroupingRule` (se asigna a la tabla `mss_grouping_rule`)
  - **Responsabilidad:** Proporciona la interfaz CRUD (Crear, Leer, Actualizar, Eliminar) para gestionar las reglas de agrupación de envíos. Maneja la visualización de la lista de reglas, el formulario para añadir/editar reglas (incluidos los constructores de condiciones y acciones) y el guardado/eliminación de datos de reglas.
- `multishipsplit/controllers/admin/AdminMultishipSplits.php`
  - **Nombre de la clase:** `AdminMultishipSplitsController` (extiende `ModuleAdminController`)
  - **Nombre de la pestaña:** "Divisiones de envío"
  - **Entidad gestionada:** `MultishipSplitGroup` (se asigna a la tabla `mss_split_group`)
  - **Responsabilidad:** Muestra una lista de todos los pedidos que han sido procesados y divididos por el módulo. Proporciona una vista de solo lectura de los grupos divididos dentro de cada pedido, enlazando de nuevo al pedido original de PrestaShop.
- `multishipsplit/controllers/admin/index.php`
  - **Nombre de la clase:** `MultishipsplitIndexModuleAdminController` (extiende `ModuleAdminController`)
  - **Nombre de la pestaña:** "Panel de control de división de envío"
  - **Entidad gestionada:** N/A (vista de panel de control)
  - **Responsabilidad:** Sirve como controlador del panel de control, mostrando KPI, gráficos y pedidos divididos recientes. Agrega datos de las tablas del módulo para proporcionar una visión general de su actividad.

### 3.3 Clases y modelos principales (`classes/`)

- `multishipsplit/classes/MultishipActionBuilder.php`
  - **Responsabilidad:** Una clase de servicio responsable de construir e interpretar las acciones definidas dentro de una `MultishipGroupingRule`. Traduce la configuración de acción de la regla en lógica ejecutable.
- `multishipsplit/classes/MultishipCartSlicer.php`
  - **Responsabilidad:** La clase central para la lógica de división del carrito. Toma un objeto `Cart` y, utilizando las `MultishipGroupingRule`s definidas, divide los productos del carrito en una matriz de objetos `MultishipShipmentGroup`.
- `multishipsplit/classes/MultishipCheckoutPresenter.php`
  - **Responsabilidad:** Prepara los datos para la página de pago del Front Office. Toma los `MultishipShipmentGroup`s y los formatea para su visualización, incluidos los transportistas disponibles, los costos y las opciones de puntos de recogida, para ser renderizados por las plantillas Smarty.
- `multishipsplit/classes/MultishipCompatibility.php`
  - **Responsabilidad:** Maneja las capas de compatibilidad para diferentes versiones de PrestaShop o posibles conflictos con otros módulos. Asegura que el módulo funcione correctamente en varios entornos.
- `multishipsplit/classes/MultishipConditionBuilder.php`
  - **Responsabilidad:** Similar a `MultishipActionBuilder`, pero para las condiciones de las reglas. Construye e interpreta las condiciones que determinan cuándo debe aplicarse una `MultishipGroupingRule`.
- `multishipsplit/classes/MultishipConditionEvaluator.php`
  - **Responsabilidad:** Evalúa un conjunto de condiciones contra un contexto dado (por ejemplo, un producto, un carrito, un cliente) para determinar si una regla debe activarse.
- `multishipsplit/classes/MultishipConditionTree.php`
  - **Responsabilidad:** Gestiona la estructura jerárquica de las condiciones (por ejemplo, grupos AND/OR) dentro de una regla, permitiendo expresiones lógicas complejas.
- `multishipsplit/classes/MultishipConfirmationPresenter.php`
  - **Responsabilidad:** Prepara los datos para mostrar el resumen de la división en la página de confirmación del pedido.
- `multishipsplit/classes/MultishipDashboardPresenter.php`
  - **Responsabilidad:** Recopila y formatea datos para el panel de control del Back Office, incluidos los KPI y los datos de los gráficos.
- `multishipsplit/classes/MultishipGroupingEngine.php`
  - **Responsabilidad:** Orquesta todo el proceso de agrupación basado en reglas. Obtiene las reglas activas, las aplica secuencialmente (según la prioridad) al carrito y gestiona la creación de `MultishipShipmentGroup`s.
- `multishipsplit/classes/MultishipGroupingRule.php`
  - **Extiende:** `ObjectModel`
  - **Tabla de base de datos:** `mss_grouping_rule`
  - **Campos `$definition`:** Almacena la configuración de cada regla de división, incluido su nombre, prioridad, estado activo y condiciones y acciones serializadas.
  - **Métodos públicos clave:** Métodos para guardar, cargar y gestionar datos de reglas.
- `multishipsplit/classes/MultishipOrderLink.php`
  - **Extiende:** `ObjectModel`
  - **Tabla de base de datos:** `mss_order_link`
  - **Campos `$definition`:** Vincula un `Order` de PrestaShop a sus `MultishipSplitGroup`s correspondientes, lo que permite al módulo rastrear cómo se dividió un pedido.
  - **Métodos públicos clave:** Métodos para crear y recuperar estos enlaces.
- `multishipsplit/classes/MultishipPaymentBridge.php`
  - **Responsabilidad:** Facilita el proceso de pago cuando un carrito se divide. Asegura que el monto total adeudado para todos los grupos de envío se pase correctamente al módulo de pago y que la confirmación de pago actualice correctamente el estado de todos los pedidos asociados.
- `multishipsplit/classes/MultishipPayPlugRefundAdapter.php`
  - **Responsabilidad:** Proporciona una integración específica para reembolsar pedidos divididos cuando se utiliza el módulo de pago PayPlug. Esto sugiere que el módulo podría tener adaptadores similares para otras pasarelas de pago.
- `multishipsplit/classes/MultishipPickupFactory.php`
  - **Responsabilidad:** Una clase de fábrica para crear instancias de `MultishipPickupAdapterInterface` basada en el transportista o módulo en uso (por ejemplo, para Mondial Relay, Colissimo).
- `multishipsplit/classes/MultishipRefundLog.php`
  - **Extiende:** `ObjectModel`
  - **Tabla de base de datos:** `mss_refund_log`
  - **Campos `$definition`:** Registra las acciones de reembolso relacionadas con los pedidos divididos, especialmente importante cuando se trata de reembolsos parciales o reembolsos en múltiples pedidos vinculados.
- `multishipsplit/classes/MultishipRuleContext.php`
  - **Responsabilidad:** Encapsula el contexto (por ejemplo, carrito actual, cliente, producto que se está evaluando) para la evaluación de reglas, lo que facilita el paso de datos relevantes a los evaluadores de condiciones.
- `multishipsplit/classes/MultishipShipmentGroup.php`
  - **Responsabilidad:** Representa un único envío lógico dentro de un carrito dividido. Contiene una colección de `MultishipShipmentProduct`s, el transportista seleccionado y los costos asociados.
- `multishipsplit/classes/MultishipShipmentProduct.php`
  - **Responsabilidad:** Representa un artículo de producto dentro de un `MultishipShipmentGroup`, incluida su cantidad y atributos específicos relevantes para ese envío.
- `multishipsplit/classes/MultishipShippingCostAggregator.php`
  - **Responsabilidad:** Calcula el costo total de envío sumando los costos de todos los `MultishipShipmentGroup`s individuales.
- `multishipsplit/classes/MultishipSplitGroup.php`
  - **Extiende:** `ObjectModel`
  - **Tabla de base de datos:** `mss_split_group`
  - **Campos `$definition`:** Almacena detalles sobre un grupo de envío específico que se creó como parte de un pedido dividido. Esto se utiliza para el seguimiento y la elaboración de informes en el Back Office.
- `multishipsplit/classes/MultishipSplitOrchestrator.php`
  - **Responsabilidad:** El orquestador de alto nivel para todo el proceso de división, desde la división inicial del carrito hasta la creación del pedido y el manejo del pago.
- `multishipsplit/classes/Pickup/MultishipColissimoPickupAdapter.php`
  - **Implementa:** `MultishipPickupAdapterInterface`
  - **Responsabilidad:** Proporciona lógica específica para la integración con los puntos de recogida de Colissimo.
- `multishipsplit/classes/Pickup/MultishipMondialRelayPickupAdapter.php`
  - **Implementa:** `MultishipPickupAdapterInterface`
  - **Responsabilidad:** Proporciona lógica específica para la integración con los puntos de recogida de Mondial Relay.
- `multishipsplit/classes/Pickup/MultishipPickupAdapterInterface.php`
  - **Responsabilidad:** Define el contrato para todos los adaptadores de integración de puntos de recogida, asegurando una interfaz consistente para diferentes transportistas.
- `multishipsplit/override/classes/Cart.php`
  - **Responsabilidad:** Sobrescribe los métodos principales de `Cart` para interceptar y modificar cómo se añaden, eliminan productos y cómo se calculan los costos de envío, lo que permite que la lógica de división del módulo surta efecto. Esta es una sobrescritura crítica.
- `multishipsplit/override/classes/PaymentModule.php`
  - **Responsabilidad:** Sobrescribe los métodos principales de `PaymentModule` para manejar el proceso de pago de múltiples pedidos generados a partir de un único carrito dividido. Asegura que un solo pago cubra todos los subpedidos y que sus estados se actualicen correctamente.

### 3.4 Activos JavaScript (`views/js/`)

- `multishipsplit/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back Office.
  - **Detalles:** Proporciona funcionalidad de autocompletado para las entradas de búsqueda, probablemente utilizada en el constructor de reglas para seleccionar productos, categorías u otras entidades.
- `multishipsplit/lib/searchTool/views/views/js/autocomplete.js`
  - **Alcance:** Back Office.
  - **Detalles:** Probablemente una ruta duplicada o alternativa para el script de autocompletado, posiblemente para compatibilidad o contextos de vista específicos.
- `multishipsplit/views/js/adminActionBuilder.js`
  - **Alcance:** Back Office (AdminMultishipRulesController).
  - **Detalles:** Gestiona la interfaz dinámica para construir acciones de reglas (por ejemplo, "Forzar envío separado"). Maneja la adición/eliminación de tipos de acción y sus parámetros asociados.
- `multishipsplit/views/js/adminConditionBuilder.js`
  - **Alcance:** Back Office (AdminMultishipRulesController).
  - **Detalles:** Gestiona la interfaz dinámica para construir condiciones de reglas. Permite a los administradores añadir múltiples condiciones, agruparlas con lógica AND/OR y seleccionar varios criterios (producto, categoría, etc.).
- `multishipsplit/views/js/adminMultishipSearchTool.js`
  - **Alcance:** Back Office.
  - **Detalles:** Integra la herramienta de búsqueda de autocompletado en los formularios de administración del módulo, particularmente para seleccionar productos, categorías u otras entidades específicas al definir reglas.
- `multishipsplit/views/js/admin_dashboard.js`
  - **Alcance:** Back Office (AdminMultishipIndexController).
  - **Detalles:** Maneja elementos dinámicos y carga de datos para el panel de control, incluyendo potencialmente la representación de gráficos (por ejemplo, usando Chart.js) y actualizaciones de KPI.
- `multishipsplit/views/js/admin_rules.js`
  - **Alcance:** Back Office (AdminMultishipRulesController).
  - **Detalles:** JavaScript general para la página de gestión de reglas, incluida la reordenación de reglas por arrastrar y soltar, los interruptores de activar/desactivar y el manejo del envío de formularios.
- `multishipsplit/views/js/checkout.js`
  - **Alcance:** Front Office (página de pago).
  - **Detalles:** Este es un script crítico para la experiencia del Front Office. Vincula los oyentes de eventos a los cambios de selección de transportista para cada grupo de envío, envía solicitudes AJAX a `groups.php` o `pickup.php` para actualizar los costos de envío o obtener puntos de recogida, y actualiza dinámicamente el resumen total del pedido en la página de pago. Probablemente utiliza `prestashop.on` para eventos personalizados.

### 3.5 Hojas de estilo CSS (`views/css/`)

- `multishipsplit/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back Office.
  - **Detalles:** Estilos para los desplegables de autocompletado y los campos de entrada de búsqueda utilizados en los formularios de administración.
- `multishipsplit/lib/searchTool/views/views/css/autocomplete.css`
  - **Alcance:** Back Office.
  - **Detalles:** Probablemente una ruta duplicada o alternativa para los estilos de autocompletado.
- `multishipsplit/views/css/admin_condition_builder.css`
  - **Alcance:** Back Office (AdminMultishipRulesController).
  - **Detalles:** Estiliza la interfaz dinámica para construir condiciones dentro del formulario de creación/edición de reglas, asegurando un diseño claro y organizado.
- `multishipsplit/views/css/admin_dashboard.css`
  - **Alcance:** Back Office (AdminMultishipIndexController).
  - **Detalles:** Estilos para el diseño del panel de control, KPI, gráficos y tabla de divisiones recientes.
- `multishipsplit/views/css/admin_order.css`
  - **Alcance:** Back Office (página de vista de pedido).
  - **Detalles:** Estilos para el widget o la información personalizada que se muestra dentro de la vista de pedido estándar de PrestaShop, mostrando cómo se dividió el pedido.
- `multishipsplit/views/css/admin_rules.css`
  - **Alcance:** Back Office (AdminMultishipRulesController).
  - **Detalles:** Estilos generales para la tabla de listado de reglas, las acciones de reglas (activar/desactivar) y el diseño general de la página de gestión de reglas.
- `multishipsplit/views/css/checkout.css`
  - **Alcance:** Front Office (página de pago).
  - **Detalles:** Estiliza la presentación de los grupos de envío divididos en la página de pago, incluyendo cómo se muestran los transportistas para cada grupo, el resumen de costos y, potencialmente, las interfaces de selección de puntos de recogida. Los desarrolladores pueden sobrescribir estas clases en el `custom.css` de su tema o modificando las plantillas del módulo.

### 3.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

- `multishipsplit/views/templates/hook/checkout_groups.tpl`
  - **Hook:** Probablemente `displayCarrierList` o un hook personalizado inyectado en el paso de envío del pago.
  - **Salidas:** El bloque visual principal en la página de pago que muestra los productos agrupados y permite a los clientes seleccionar un transportista para cada grupo de envío individual. Aquí es donde ocurre la interacción principal del Front Office.
- `multishipsplit/views/templates/hook/order_confirmation_split.tpl`
  - **Hook:** `displayOrderConfirmation` o un hook similar en la página de confirmación del pedido.
  - **Salidas:** El resumen de cómo se dividió el pedido, mostrando qué artículos estaban en cada envío y el transportista elegido, según lo configurado por el ajuste "Mostrar resumen de división en la página de confirmación de pedido".
- `multishipsplit/views/templates/hook/payment_top.tpl`
  - **Hook:** `displayPaymentTop`
  - **Salidas:** Potencialmente muestra una advertencia o mensaje informativo al cliente con respecto al pedido dividido antes de que proceda al pago, asegurando que comprenda que el costo total incluye múltiples tarifas de envío.

#### Plantillas de administración (`views/templates/admin/`)

- `multishipsplit/lib/searchTool/views/scripts.tpl`
  - **Salidas:** Bloque de script Smarty para la herramienta de búsqueda, que probablemente incluye JavaScript y CSS.
- `multishipsplit/lib/searchTool/views/views/scripts.tpl`
  - **Salidas:** Ruta duplicada o alternativa para los scripts de la herramienta de búsqueda.
- `multishipsplit/views/templates/admin/actionBuilder.tpl`
  - **Salidas:** La estructura HTML para la interfaz dinámica del constructor de acciones dentro del formulario de creación/edición de reglas.
- `multishipsplit/views/templates/admin/dashboard_chart.tpl`
  - **Salidas:** Plantilla para renderizar un gráfico específico en el panel de control, probablemente utilizando una biblioteca de gráficos JavaScript.
- `multishipsplit/views/templates/admin/dashboard_kpi_strip.tpl`
  - **Salidas:** Plantilla para la franja de indicadores clave de rendimiento (KPI) en la parte superior del panel de control.
- `multishipsplit/views/templates/admin/dashboard_recent_splits.tpl`
  - **Salidas:** Plantilla para mostrar una lista de pedidos divididos recientemente en el panel de control.
- `multishipsplit/views/templates/admin/dashboard_stats.tpl`
  - **Salidas:** Bloque de estadísticas generales en el panel de control.
- `multishipsplit/views/templates/admin/menu.tpl`
  - **Salidas:** Define los elementos de menú personalizados del módulo en la navegación del Back Office de PrestaShop (por ejemplo, en "Envío").
- `multishipsplit/views/templates/admin/order_split_widget.tpl`
  - **Salidas:** Un widget o bloque personalizado que se muestra dentro de la página de detalles del pedido estándar de PrestaShop en el Back Office, proporcionando un resumen de cómo se dividió ese pedido específico.
- `multishipsplit/views/templates/admin/policyConditionBuilder.tpl`
  - **Salidas:** La estructura HTML para la interfaz dinámica del constructor de condiciones dentro del formulario de creación/edición de reglas.
- `multishipsplit/views/templates/admin/split_view.tpl`
  - **Salidas:** Una vista detallada para un pedido dividido específico, a la que se puede acceder desde la lista "Divisiones de envío".

### 3.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

- `ps_mss_grouping_rule`: Almacena las definiciones de todas las reglas de agrupación de envíos creadas por el administrador.
  - `id_mss_grouping_rule` (PK)
  - `name` (VARCHAR)
  - `priority` (INT)
  - `active` (TINYINT)
  - `conditions` (TEXT - array/JSON serializado de condiciones)
  - `actions` (TEXT - array/JSON serializado de acciones)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_mss_split_group`: Almacena los detalles de cada grupo de envío individual creado para un pedido dividido.
  - `id_mss_split_group` (PK)
  - `id_order` (FK a `ps_orders`)
  - `id_cart` (FK a `ps_cart`)
  - `id_carrier` (FK a `ps_carrier`)
  - `shipping_cost_tax_excl` (DECIMAL)
  - `shipping_cost_tax_incl` (DECIMAL)
  - `products` (TEXT - array serializado de productos en este grupo)
  - `pickup_point_data` (TEXT - datos serializados para el punto de recogida, si se selecciona)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_mss_order_link`: Vincula un único `id_order` de PrestaShop (el pedido "padre") a múltiples `id_order`s (los pedidos "hijo" creados para cada envío dividido).
  - `id_mss_order_link` (PK)
  - `id_parent_order` (FK a `ps_orders`)
  - `id_child_order` (FK a `ps_orders`)
  - `id_mss_split_group` (FK a `ps_mss_split_group`)
  - `date_add` (DATETIME)
- `ps_mss_refund_log`: Registra los eventos de reembolso relacionados con los pedidos divididos.
  - `id_mss_refund_log` (PK)
  - `id_order` (FK a `ps_orders`)
  - `id_order_slip` (FK a `ps_order_slip`)
  - `amount` (DECIMAL)
  - `reason` (TEXT)
  - `date_add` (DATETIME)
- `ps_configuration`: La configuración del módulo se almacena aquí con claves como `MULTISHIPSPLIT_ENABLED`, `MULTISHIPSPLIT_DEBUG_MODE`, etc.

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de todas las páginas del Front Office. | Inyección de activos CSS y JS para la funcionalidad del Front Office (por ejemplo, `checkout.js`, `checkout.css`). |
| `displayBackOfficeHeader` | En la sección `<head>` de todas las páginas del Back Office. | Inyección de activos CSS y JS para los controladores de administración (por ejemplo, `admin_rules.js`, `admin_condition_builder.css`). |
| `displayAdminProductsExtra` | En la página de edición de productos en el Back Office. | Potencialmente añade una pestaña o sección para configurar reglas de división específicas del producto o sobrescrituras. |
| `actionCartSave` | Después de que un carrito se guarda o actualiza. | Intercepta las modificaciones del carrito para activar la lógica de división y recalcular los grupos de envío. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Procesa el carrito dividido en múltiples pedidos de PrestaShop, los vincula y almacena los datos del grupo dividido. |
| `actionOrderSlipAdd` | Cuando se añade una nota de crédito (reembolso). | Maneja la lógica de reembolso para pedidos divididos, potencialmente registrando reembolsos parciales en pedidos vinculados. |
| `displayCarrierList` | En el paso de envío del pago, donde se muestran las opciones de transportista. | Reemplaza o aumenta la lista de transportistas estándar con la interfaz de selección de envío agrupado (`checkout_groups.tpl`). |
| `displayOrderConfirmation` | En la página final de confirmación del pedido. | Muestra el resumen del pedido dividido al cliente (`order_confirmation_split.tpl`). |
| `displayPaymentTop` | Antes de la selección del método de pago en la página de pago. | Puede mostrar mensajes o resúmenes importantes relacionados con los costos de envío divididos (`payment_top.tpl`). |
| `displayAdminOrder` | En la página de detalles del pedido en el Back Office. | Inyecta el `order_split_widget.tpl` para mostrar cómo se dividió el pedido específico. |
| `actionObjectCartUpdateAfter` | Después de que un objeto Cart ha sido actualizado. | Similar a `actionCartSave`, asegura que la lógica de división se reevalúe. |
| `actionObjectOrderAddAfter` | Después de que se ha añadido un nuevo objeto Order. | Se utiliza para finalizar la vinculación de pedidos padre/hijo y los datos del grupo dividido. |
| `actionObjectOrderUpdateAfter` | Después de que un objeto Order ha sido actualizado. | Potencialmente actualiza los estados del grupo dividido o los datos relacionados si se modifica un pedido. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su contenido. | Asegura que se carguen los JS/CSS necesarios para las páginas del Front Office. |
| `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice su contenido. | Asegura que se carguen los JS/CSS necesarios para las páginas del Back Office. |
| `displayAdminStatsModules` | En la página Módulos > Estadísticas. | Potencialmente añade estadísticas específicas del módulo al panel de control de PrestaShop. |
| `displayDashboardTop` | En la parte superior del panel de control de PrestaShop. | Puede mostrar un resumen rápido o una alerta del módulo. |
| `displayDashboardZoneOne` | En la primera zona del panel de control de PrestaShop. | Puede mostrar un widget específico del módulo en el panel de control. |
| `displayDashboardZoneTwo` | En la segunda zona del panel de control de PrestaShop. | Puede mostrar un widget específico del módulo en el panel de control. |

## 4. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en MyPresta.eu.

- **Actualizaciones del módulo:** Inicie sesión en [Historial de pedidos y descargas de MyPresta.eu](https://mypresta.eu/my-account/orders/) para descargar la versión más reciente del módulo "Dividir carrito en envíos separados".
- **Soporte técnico:** Si encuentra algún problema o tiene preguntas que no están cubiertas en esta guía, abra un ticket de soporte a través de su cuenta de cliente de MyPresta.eu. Nuestro equipo está listo para ayudarle.

## 5. ## Galería

![Panel de control en la página de configuración del módulo que muestra las estadísticas del módulo](https://mypresta.eu/docs/images/docs/02-shipping-multi-carrier-order-split_1791740311.webp)
"""

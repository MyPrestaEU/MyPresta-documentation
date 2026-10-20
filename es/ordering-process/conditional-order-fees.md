---
title: "Conditional Order Fees - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Conditional Order Fees para PrestaShop de MyPresta.eu."
sidebar:
  label: "Conditional Order Fees - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Conditional Order Fees en MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-fees.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/conditional-order-fees/)
>
> ---


# Conditional Order Fees

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL) típicamente disponibles en la mayoría de los entornos de alojamiento compatibles con PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Conditional Order Fees)

Esta es la pantalla de configuración principal donde habilitas o deshabilitas el módulo y configuras el "producto" fundamental que representa tus tarifas.

- **Ubicación del Menú:** Back Office > Módulos > Gestor de Módulos > Conditional Order Fees > Configurar

#### Ajustes Generales

- **Habilitar Módulo:**

  - **Qué hace este ajuste:** Este es el interruptor maestro para todo el módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El módulo evaluará activamente tus políticas de tarifas definidas y aplicará tarifas a los carritos que cumplan las condiciones.
    - *Cuando está deshabilitado:* Este módulo no aplicará ninguna tarifa, independientemente de la configuración de tus políticas.
  - **Valor recomendado:** SÍ (una vez que hayas configurado tus políticas).
  - **Escenario / ejemplo de comerciante:** Has terminado de configurar todas tus políticas de tarifas y estás listo para salir en vivo. Habilita esto para empezar a cobrar tarifas. Si necesitas detener temporalmente todas las tarifas por mantenimiento o una promoción, desactívalo.
- **ID de Producto de Tarifa:**

  - **Qué hace este ajuste:** Esta configuración crucial vincula tus tarifas a un producto específico y oculto en tu catálogo. PrestaShop necesita un "producto" para representar cualquier artículo añadido al carrito, incluso si es un servicio o una tarifa. Este módulo crea un producto especial no visible para este propósito durante la instalación.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un ID de Producto válido:* El módulo utilizará este producto para representar la tarifa en el carrito, el proceso de pago y los detalles del pedido. El nombre del producto será reemplazado por la etiqueta personalizada de la tarifa, y su precio será anulado por la tarifa calculada.
    - *Cuando se establece un ID de Producto inválido o inexistente:* El módulo no podrá añadir tarifas al carrito, ya que no tendrá un producto "marcador de posición" válido para usar.
  - **Valor recomendado:** Utiliza el ID del producto especial "Conditional Order Fee" creado por el módulo durante la instalación. Puedes encontrar este ID buscando "Conditional Order Fee" en tu lista de Productos (aunque generalmente está oculto en el front office). El módulo a menudo lo rellenará automáticamente.
  - **Escenario / ejemplo de comerciante:** El módulo crea automáticamente un producto llamado "Conditional Order Fee" (o similar) y establece su ID aquí. Generalmente no debes cambiar esto a menos que intencionalmente quieras usar un producto diferente como marcador de posición de la tarifa (lo cual no se recomienda para la mayoría de los usuarios).

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

El módulo proporciona secciones dedicadas en tu Back Office de PrestaShop para gestionar tus políticas de tarifas y revisar su aplicación.

#### 2.2.1 Panel de Control de Tarifas de Pedido Condicionales (Back Office > Conditional Order Fees > Dashboard)

Esta pantalla proporciona una visión general de la actividad de tu módulo, incluyendo un resumen de las tarifas aplicadas y acceso rápido a la gestión de políticas.

- **Nombre de la Pantalla y Ubicación del Menú:** **Conditional Order Fees > Dashboard** (se encuentra bajo el elemento de menú principal "Conditional Order Fees" en la barra lateral izquierda).
- **Acciones y Ajustes Disponibles:**
  - **Estadísticas de Resumen:** Consulta métricas clave como el total de tarifas recaudadas, el número de pedidos con tarifas y la tarifa promedio por pedido. Esto te ayuda a comprender el impacto de tus políticas de tarifas.
  - **Tarifas Recientes Aplicadas:** Una lista rápida de los pedidos más recientes donde se aplicó una tarifa condicional, incluyendo el ID del pedido, el cliente y el importe de la tarifa.
  - **Enlaces Rápidos:** Enlaces directos a "Gestionar Políticas" y "Ver Registro de Auditoría".
- **Efecto de los cambios:** Esta pantalla es principalmente para monitoreo y navegación. No se realizan cambios directos aquí, pero refleja el impacto de tus políticas de tarifas.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Consulta este panel periódicamente para monitorear el rendimiento de tus políticas de tarifas y asegurarte de que funcionan como se espera.

#### 2.2.2 Gestionar Políticas de Tarifas (Back Office > Conditional Order Fees > Policies)

Aquí es donde defines, editas y gestionas todas tus reglas de tarifas condicionales. Cada "política" es un conjunto de condiciones que, cuando se cumplen, aplicarán una tarifa específica.

- **Nombre de la Pantalla y Ubicación del Menú:** **Conditional Order Fees > Policies** (se encuentra bajo el elemento de menú principal "Conditional Order Fees" en la barra lateral izquierda).
- **Acciones y Ajustes Disponibles:**
  - **Lista de Políticas:** Una tabla que muestra todas tus políticas de tarifas existentes, incluyendo su nombre, estado (habilitado/deshabilitado), prioridad y el importe/tipo de tarifa.
  - **Añadir Nueva Política:** Haz clic en el botón "Añadir nueva política" para crear una nueva regla de tarifa.
    - **Nombre de la Política:** Un nombre descriptivo para tu referencia interna (por ejemplo, "Tarifa de Manipulación de Pedido Pequeño", "Recargo por Embalaje Frágil").
    - **Estado:** Habilita o deshabilita la política.
    - **Prioridad:** Si varias políticas pudieran aplicarse al mismo carrito, la que tenga la prioridad más alta (número más bajo) se evaluará primero. Si "Detener el procesamiento de reglas adicionales" está habilitado, solo se aplicará la regla coincidente de mayor prioridad.
    - **Tipo de Tarifa:**
      - **Cantidad Fija:** Un valor monetario específico (por ejemplo, 5,00 €).
      - **Porcentaje del Total del Carrito:** Un porcentaje del subtotal del carrito (por ejemplo, 2%).
      - **Porcentaje de Productos en el Carrito:** Un porcentaje del precio total de los productos en el carrito (excluyendo envío/impuestos).
    - **Valor de la Tarifa:** El importe o porcentaje real basado en el tipo de tarifa seleccionado.
    - **Etiqueta de la Tarifa (Multi-idioma):** El texto que los clientes verán en su carrito y resumen de pedido (por ejemplo, "Tarifa de Manipulación", "Cargo por Servicio"). Esto se puede traducir para diferentes idiomas.
    - **Constructor de Condiciones:** Este es el núcleo de la política. Puedes construir reglas complejas usando grupos "Y" / "O", combinando condiciones como:
      - Valor del carrito (total, subtotal, cantidad)
      - Grupo de clientes
      - País, estado o zona
      - Transportista
      - Productos específicos en el carrito (por ID, categoría, fabricante, proveedor)
      - Método de pago
      - Y más…
    - **Detener el procesamiento de reglas adicionales:** Si está habilitado, una vez que esta política se aplica, ninguna otra política de menor prioridad será evaluada para el mismo carrito.
  - **Editar/Eliminar Políticas:** Modifica políticas existentes o elimínalas.
  - **Duplicar Política:** Crea rápidamente una nueva política basada en una existente, ahorrando tiempo al crear reglas similares.
- **Efecto de los cambios:** Añadir, editar o eliminar políticas impacta directamente qué tarifas se aplican a los carritos de los clientes y bajo qué circunstancias. Las políticas configuradas incorrectamente pueden llevar a cargos inesperados o a la pérdida de ingresos.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Comienza definiendo tus escenarios de tarifas más comunes.
  2. Utiliza el botón "Añadir nueva política" para crear cada regla.
  3. Construye cuidadosamente tus condiciones utilizando el constructor. Prueba a fondo utilizando el simulador (si está disponible, consulta el registro de auditoría) para asegurarte de que funcionan como se espera.
  4. Establece prioridades adecuadas, especialmente si tienes condiciones superpuestas.
  5. Revisa y actualiza regularmente las políticas a medida que cambien tus necesidades comerciales o promociones.

#### 2.2.3 Registro de Auditoría (Back Office > Conditional Order Fees > Audit Log)

El registro de auditoría proporciona un historial detallado de cada instancia en la que el módulo evaluó un carrito y aplicó (o no aplicó) una tarifa. Esto es invaluable para la resolución de problemas y para comprender por qué se cobraron o no ciertas tarifas.

- **Nombre de la Pantalla y Ubicación del Menú:** **Conditional Order Fees > Audit Log** (se encuentra bajo el elemento de menú principal "Conditional Order Fees" en la barra lateral izquierda).
- **Acciones y Ajustes Disponibles:**
  - **Entradas del Registro:** Una tabla que muestra cada evento de evaluación, incluyendo:
    - Fecha y hora
    - Cliente (si ha iniciado sesión)
    - ID del carrito
    - Política Aplicada (si la hay)
    - Importe de la Tarifa (si se aplicó)
    - Estado (por ejemplo, "Tarifa Aplicada", "No se Aplicó Tarifa", "Política No Cumplida")
  - **Vista Detallada:** Haz clic en una entrada del registro para ver un desglose completo de cómo se evaluaron las condiciones para ese carrito específico, mostrando qué condiciones pasaron y cuáles fallaron. Esto es como un "simulador" para eventos pasados.
  - **Filtrado y Búsqueda:** Filtra las entradas del registro por fecha, cliente, ID del carrito o política para encontrar rápidamente eventos específicos.
- **Efecto de los cambios:** Esta pantalla es para revisión y depuración. No se realizan cambios directos aquí, pero proporciona información crítica sobre el comportamiento del módulo.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Si un cliente informa de una tarifa inesperada o la ausencia de una tarifa esperada, utiliza el registro de auditoría para investigar.
  2. Filtra por el nombre del cliente o el ID del carrito para ver exactamente qué políticas se evaluaron y por qué.
  3. Utiliza la vista detallada para identificar qué condición específica hizo que una política pasara o fallara.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Habilitar Módulo | SÍ | Interruptor maestro para activar/desactivar toda la funcionalidad del módulo. |
|  | ID de Producto de Tarifa | ID autogenerado | Vincula las tarifas a un producto oculto para el sistema de carrito de PrestaShop. No cambiar a menos que se indique. |
| **Políticas** | Nombre de la Política | N/A | Etiqueta interna para tu regla de tarifa. |
|  | Estado | Habilitado | Activa/desactiva una política de tarifa individual. |
|  | Prioridad | 1 (número más bajo = prioridad más alta) | Determina el orden de evaluación si se pueden aplicar varias políticas. |
|  | Tipo de Tarifa | Cantidad Fija | Elige cómo se calcula la tarifa (fija, % del carrito, % de productos). |
|  | Valor de la Tarifa | 0.00 | El importe o porcentaje de la tarifa. |
|  | Etiqueta de la Tarifa | "Tarifa de Manipulación" (ejemplo) | Texto visible para el cliente para la tarifa en el carrito/pedido. |
|  | Constructor de Condiciones | N/A | Define los criterios específicos (carrito, cliente, producto, etc.) para que se aplique la tarifa. |
|  | Detener el procesamiento de reglas adicionales | No | Si está habilitado, evita que se apliquen políticas de menor prioridad una vez que esta coincide. |
| **Registro de Auditoría** | (Todas las entradas) | N/A | Proporciona un historial detallado de las evaluaciones de tarifas para la resolución de problemas y el monitoreo. |

## 3. Resolución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: He configurado una política, pero la tarifa no aparece en el carrito.**
R1:

- **Verificar Estado del Módulo:** Asegúrate de que la configuración "Habilitar Módulo" en la página de configuración principal esté establecida en SÍ.
- **Verificar Estado de la Política:** Asegúrate de que la política específica que esperas que se aplique esté "Habilitada" en la lista de Políticas.
- **Revisar Condiciones:** Vuelve a verificar las condiciones de tu política. ¿Se cumplen realmente todas con el carrito actual? Utiliza el Registro de Auditoría (Conditional Order Fees > Audit Log) para ver cómo se evaluaron tus condiciones para un carrito de prueba.
- **ID de Producto de Tarifa:** Verifica que el "ID de Producto de Tarifa" en la página de configuración principal sea correcto y apunte al producto especial creado por el módulo.
- **Caché:** Borra la caché de tu PrestaShop (Parámetros Avanzados > Rendimiento) y la caché de tu navegador.

**P2: La tarifa aparece, pero la etiqueta o el importe son incorrectos.**
R2:

- **Configuración de la Política:** Ve a la política específica en "Conditional Order Fees > Políticas" y verifica la configuración de "Valor de la Tarifa" y "Etiqueta de la Tarifa". Asegúrate de que la etiqueta esté traducida correctamente para el idioma que estás probando.
- **Múltiples Políticas:** Si varias políticas pudieran aplicarse potencialmente, verifica su "Prioridad" y la configuración "Detener el procesamiento de reglas adicionales". Una política de mayor prioridad podría estar aplicándose en lugar de la que esperas.

**P3: ¿Puedo traducir la etiqueta de la tarifa para diferentes idiomas?**
R3: ¡Sí! Al editar una política, el campo "Etiqueta de la Tarifa" normalmente tendrá un selector de idioma (un icono de bandera). Haz clic en él para introducir traducciones para cada idioma instalado en tu tienda.

**P4: ¿Qué sucede si elimino el "Producto de Tarifa" que utiliza el módulo?**
R4: Si eliminas el producto especificado en la configuración "ID de Producto de Tarifa", el módulo ya no podrá añadir tarifas al carrito. Es crucial no eliminar este producto. Si se elimina accidentalmente, es posible que debas reinstalar el módulo (lo que lo recreará) o crear manualmente un nuevo producto oculto y actualizar la configuración "ID de Producto de Tarifa".

**P5: El módulo parece estar ralentizando mi proceso de pago.**
R5: Aunque el módulo está optimizado para el rendimiento, las políticas complejas con muchas condiciones, especialmente aquellas que implican extensas comprobaciones de productos, pueden añadir una ligera sobrecarga.

- **Simplificar Condiciones:** Revisa tus políticas. ¿Se pueden simplificar o combinar algunas condiciones?
- **Priorizar:** Utiliza la configuración de "Prioridad" y "Detener el procesamiento de reglas adicionales" de manera efectiva para minimizar el número de políticas que necesitan una evaluación completa para un carrito dado.
- **Recursos del Servidor:** Asegúrate de que tu entorno de alojamiento cumpla con las especificaciones recomendadas de PrestaShop.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo Conditional Order Fees está construido siguiendo el patrón MVC de PrestaShop, aprovechando en gran medida `ObjectModel` para la persistencia de datos y una sólida arquitectura basada en eventos a través de los hooks de PrestaShop. Introduce un sofisticado motor de evaluación de condiciones, que permite una lógica `AND`/`OR` compleja y anidada para determinar la aplicabilidad de las tarifas. El módulo se integra perfectamente en el flujo de procesamiento del carrito y del pedido añadiendo dinámicamente un "producto virtual" al carrito cuando se cumplen las condiciones. Las interfaces de administración se construyen utilizando los componentes `AdminController` y `HelperList`/`HelperForm` de PrestaShop, con JavaScript personalizado para el constructor de condiciones y el simulador.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `conorderfee/controllers/front/index.php`
  - **Nombre de la Clase:** `ConorderfeeIndexModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Este controlador probablemente sirve como un fallback o un punto de entrada simple, pero la lógica central para aplicar tarifas se maneja principalmente a través de hooks, no de rutas directas del controlador frontal. Podría usarse para información básica del módulo o redirección si se accede directamente.

#### Controladores de Administración de Back-Office

- `conorderfee/controllers/admin/AdminconorderfeeAuditLog.php`
  - **Nombre de la Clase:** `AdminconorderfeeAuditLogController` (extiende `ModuleAdminController`)
  - **Nombre de la Pestaña:** Conditional Order Fees > Audit Log
  - **Entidad Gestionada:** `ConorderfeeLog` (ORM para la tabla `ps_conorderfee_log`).
  - **Responsabilidad:** Gestiona la visualización y el filtrado del registro de auditoría de tarifas. Utiliza `HelperList` para renderizar la tabla de entradas del registro y proporciona vistas detalladas para entradas de registro individuales, mostrando el proceso de evaluación de condiciones.
- `conorderfee/controllers/admin/AdminconorderfeePolicies.php`
  - **Nombre de la Clase:** `AdminconorderfeePoliciesController` (extiende `ModuleAdminController`)
  - **Nombre de la Pestaña:** Conditional Order Fees > Policies
  - **Entidad Gestionada:** `ConorderfeePolicy` (ORM para la tabla `ps_conorderfee_policy`).
  - **Responsabilidad:** Gestiona la creación, edición, duplicación y eliminación de políticas de tarifas. Utiliza `HelperList` para la visión general de las políticas y `HelperForm` para el formulario de creación/edición de políticas, que incluye la compleja interfaz del constructor de condiciones.
- `conorderfee/controllers/admin/index.php`
  - **Nombre de la Clase:** `ConorderfeeIndexModuleAdminController` (extiende `ModuleAdminController`)
  - **Nombre de la Pestaña:** Conditional Order Fees > Dashboard
  - **Entidad Gestionada:** N/A (vista de panel de control)
  - **Responsabilidad:** Sirve como el panel de control principal para el módulo en el back office, mostrando estadísticas y enlaces rápidos. Es el controlador predeterminado que se carga al hacer clic en el elemento de menú principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

- `conorderfee/classes/ConorderfeeAdmin.php`
  - **Responsabilidad:** Clase de utilidad para funcionalidades específicas de administración, que potencialmente maneja el registro de menús, la gestión de pestañas y ayudantes generales relacionados con la administración.
- `conorderfee/classes/ConorderfeeAuditLog.php`
  - **Tabla de Base de Datos:** `ps_conorderfee_log`
  - **Extiende ObjectModel:** Sí.
  - **Campos `$definition`:** `id_conorderfee_log`, `id_cart`, `id_order`, `id_customer`, `id_conorderfee_policy`, `fee_amount`, `fee_label`, `conditions_snapshot`, `evaluation_result`, `date_add`.
  - **Métodos públicos clave:** Métodos para guardar entradas de registro, recuperar datos de registro y potencialmente formatear detalles de registro para su visualización.
- `conorderfee/classes/ConorderfeeCartState.php`
  - **Responsabilidad:** Una clase de ayuda para encapsular el estado actual del carrito y el contexto relacionado (cliente, dirección, transportista, etc.) para la evaluación de condiciones. Proporciona métodos para recuperar varias propiedades del carrito necesarias para las condiciones.
- `conorderfee/classes/ConorderfeeCompatibility.php`
  - **Responsabilidad:** Maneja las capas de compatibilidad para diferentes versiones de PrestaShop (por ejemplo, 1.7 vs. 8.x vs. 9.x) para asegurar que el módulo funcione correctamente en las versiones compatibles.
- `conorderfee/classes/ConorderfeeCondition.php`
  - **Tabla de Base de Datos:** `ps_conorderfee_condition`
  - **Extiende ObjectModel:** Sí.
  - **Campos `$definition`:** `id_conorderfee_condition`, `id_conorderfee_condition_group`, `type`, `operator`, `value`, `is_inverted`.
  - **Métodos públicos clave:** Representa una única condición dentro de una política (por ejemplo, "Total del Carrito > 100"). Métodos para guardar, cargar y potencialmente validar datos de condiciones.
- `conorderfee/classes/ConorderfeeConditionEvaluator.php`
  - **Responsabilidad:** El motor de lógica central para evaluar un `ConorderfeeConditionTree` contra un `ConorderfeeCartState`. Procesa recursivamente grupos de condiciones y condiciones individuales para determinar si una política se aplica.
- `conorderfee/classes/ConorderfeeConditionGroup.php`
  - **Tabla de Base de Datos:** `ps_conorderfee_condition_group`
  - **Extiende ObjectModel:** Sí.
  - **Campos `$definition`:** `id_conorderfee_condition_group`, `id_conorderfee_policy`, `id_parent_group`, `operator` (`AND`/`OR`).
  - **Métodos públicos clave:** Representa un grupo de condiciones (por ejemplo, "Condición A Y (Condición B O Condición C)"). Gestiona sus condiciones hijas y subgrupos.
- `conorderfee/classes/ConorderfeeConditionTree.php`
  - **Responsabilidad:** Representa la estructura jerárquica de las condiciones para una política (grupo raíz, subgrupos, condiciones individuales). Utilizado por el `ConorderfeeConditionEvaluator`.
- `conorderfee/classes/ConorderfeeContext.php`
  - **Responsabilidad:** Un envoltorio alrededor del objeto `Context` de PrestaShop, que potencialmente añade datos de contexto específicos del módulo o simplifica el acceso a elementos de contexto comunes.
- `conorderfee/classes/ConorderfeeDashboard.php`
  - **Responsabilidad:** Proporciona datos y lógica para la vista del panel de control del módulo, obteniendo estadísticas y entradas de registro recientes.
- `conorderfee/classes/ConorderfeeEngine.php`
  - **Responsabilidad:** El orquestador central para la lógica de front-office del módulo. Se engancha a varios eventos de PrestaShop, recupera políticas activas, utiliza el `ConorderfeeConditionEvaluator` para verificar las condiciones y añade el producto de tarifa al carrito si es aplicable.
- `conorderfee/classes/ConorderfeeFeeProduct.php`
  - **Responsabilidad:** Gestiona el "producto de tarifa" especial que representa el cargo condicional en el carrito. Maneja su creación durante la instalación y asegura que esté configurado correctamente como un producto virtual no visible.
- `conorderfee/classes/ConorderfeeListRenderer.php`
  - **Responsabilidad:** Una clase de ayuda para renderizar listas en el back office, que potencialmente extiende `HelperList` o proporciona lógica de renderizado de columnas personalizada.
- `conorderfee/classes/ConorderfeeLog.php`
  - **Tabla de Base de Datos:** `ps_conorderfee_log` (igual que `ConorderfeeAuditLog`, probablemente un alias o clase base)
  - **Extiende ObjectModel:** Sí.
  - **Campos `$definition`:** Igual que `ConorderfeeAuditLog`.
  - **Métodos públicos clave:** Métodos para registrar eventos, almacenar resultados de evaluación y recuperar datos de registro.
- `conorderfee/classes/ConorderfeePolicy.php`
  - **Tabla de Base de Datos:** `ps_conorderfee_policy`
  - **Extiende ObjectModel:** Sí.
  - **Campos `$definition`:** `id_conorderfee_policy`, `name`, `active`, `priority`, `fee_type`, `fee_value`, `fee_label`, `stop_further_rules`, `date_add`, `date_upd`.
  - **Métodos públicos clave:** Representa una política de tarifas completa. Métodos para guardar, cargar y gestionar sus `ConorderfeeConditionGroup`s asociados.
- `conorderfee/classes/ConorderfeePolicyDuplicator.php`
  - **Responsabilidad:** Maneja la lógica para duplicar una política de tarifas existente, incluyendo todas sus condiciones y grupos asociados, para agilizar la creación de políticas.
- `conorderfee/classes/ConorderfeePreset.php`
  - **Responsabilidad:** Gestiona los tipos de condiciones y operadores predefinidos para el constructor de condiciones (por ejemplo, "Total del Carrito", "Grupo de Clientes", "es mayor que", "es uno de").
- `conorderfee/classes/ConorderfeeRule.php`
  - **Responsabilidad:** Probablemente una clase abstracta o base para definir reglas, o un tipo específico de regla dentro del constructor de condiciones.
- `conorderfee/classes/ConorderfeeTreeRepository.php`
  - **Responsabilidad:** Gestiona la persistencia y recuperación de la estructura del árbol de condiciones (políticas, grupos, condiciones) de la base de datos.
- `conorderfee/classes/index.php`
  - **Responsabilidad:** Archivo vacío, típicamente utilizado para evitar la lista de directorios.

### 4.4 Activos JavaScript (`views/js/`)

- `conorderfee/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office.
  - **Descripción:** Proporciona funcionalidad de autocompletado para campos de búsqueda, probablemente utilizado para seleccionar productos, categorías, clientes, etc., dentro del constructor de condiciones.
- `conorderfee/lib/searchTool/views/views/js/autocomplete.js`
  - **Alcance:** Back-office.
  - **Descripción:** Duplicado del anterior, probablemente un error de ruta o archivo heredado.
- `conorderfee/views/js/adminConditionBuilder.js`
  - **Alcance:** Back-office (`AdminconorderfeePoliciesController`).
  - **Descripción:** El JavaScript central para la interfaz interactiva del constructor de condiciones. Maneja la adición/eliminación de condiciones y grupos, la gestión de la lógica `AND`/`OR`, la carga dinámica de tipos de condiciones y operadores, y la actualización de la interfaz de usuario basada en la entrada del usuario.
- `conorderfee/views/js/adminConorderfeeDashboard.js`
  - **Alcance:** Back-office (`AdminconorderfeeDashboardController`).
  - **Descripción:** JavaScript para el panel de control, que potencialmente maneja actualizaciones AJAX para estadísticas, renderizado de gráficos o elementos interactivos en el panel de control.
- `conorderfee/views/js/adminConorderfeeSearchTool.js`
  - **Alcance:** Back-office.
  - **Descripción:** Integra la herramienta de búsqueda de autocompletado (de `lib/searchTool`) en varios formularios de administración, particularmente para seleccionar entidades en condiciones.
- `conorderfee/views/js/adminConorderfeeSimulator.js`
  - **Alcance:** Back-office (probablemente en la página de edición de políticas o en el registro de auditoría).
  - **Descripción:** Proporciona una herramienta de evaluación de condiciones en tiempo real o simulada en el back office, permitiendo a los administradores probar políticas contra escenarios de carrito hipotéticos sin realizar un pedido real.
- `conorderfee/views/js/adminPolicyRules.js`
  - **Alcance:** Back-office (`AdminconorderfeePoliciesController`).
  - **Descripción:** Maneja las interacciones generales de JavaScript en la lista de políticas y las páginas de edición, como habilitar/deshabilitar políticas, manejar la duplicación y gestionar el formulario general de políticas.
- `conorderfee/views/js/checkout.js`
  - **Alcance:** Front-office.
  - **Descripción:** Este script probablemente monitorea los cambios en el carrito durante el proceso de pago (por ejemplo, actualizaciones de cantidad, selección de transportista) y activa llamadas AJAX para reevaluar las tarifas, asegurando que el total del carrito sea siempre preciso. También podría actualizar la visualización de la línea de artículo de la tarifa.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `conorderfee/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back-office (Administración).
  - **Descripción:** Estilos para los campos de entrada de búsqueda de autocompletado y sus sugerencias desplegables.
- `conorderfee/lib/searchTool/views/views/css/autocomplete.css`
  - **Alcance:** Back-office (Administración).
  - **Descripción:** Duplicado del anterior, probablemente un error de ruta o archivo heredado.
- `conorderfee/views/css/admin_conorderfee.css`
  - **Alcance:** Back-office (Administración).
  - **Descripción:** Estilo general para las interfaces de back-office del módulo, incluyendo el panel de control, la lista de políticas, el registro de auditoría y, especialmente, el complejo constructor de condiciones, asegurando un diseño consistente y fácil de usar.
- `conorderfee/views/css/front.css`
  - **Alcance:** Front-office (Cliente).
  - **Descripción:** Estilo mínimo para cómo aparece la línea de artículo de la tarifa en el resumen del carrito y las páginas de pago, asegurando que se integre visualmente con el tema de la tienda.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)

- `conorderfee/views/templates/hook/admin_order.tpl`
  - **Hook:** `displayAdminOrder`
  - **Salida:** Muestra información sobre las tarifas condicionales aplicadas dentro de la vista de pedidos del Back Office de PrestaShop, permitiendo a los administradores ver qué políticas se aplicaron a un pedido específico.

#### Plantillas de Administración (`views/templates/admin/`)

- `conorderfee/lib/searchTool/views/scripts.tpl`
  - **Salida:** Incluye el JavaScript y CSS necesarios para la herramienta de búsqueda en el back office.
- `conorderfee/lib/searchTool/views/views/scripts.tpl`
  - **Salida:** Duplicado del anterior, probablemente un error de ruta o archivo heredado.
- `conorderfee/views/templates/admin/auditPreview.tpl`
  - **Salida:** Renderiza la vista detallada de una entrada individual del registro de auditoría, mostrando el proceso completo de evaluación de condiciones.
- `conorderfee/views/templates/admin/dashboard.tpl`
  - **Salida:** La vista principal del panel de control para el módulo, mostrando estadísticas y enlaces rápidos.
- `conorderfee/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Salida:** Plantilla personalizada para el botón de acción "duplicar" en las vistas de `HelperList`, específicamente para políticas.
- `conorderfee/views/templates/admin/policiesPreview.tpl`
  - **Salida:** Renderiza una vista previa o resumen de una política, potencialmente utilizada dentro del registro de auditoría o un simulador.
- `conorderfee/views/templates/admin/policyConditionBuilder.tpl`
  - **Salida:** La compleja estructura HTML para la interfaz interactiva del constructor de condiciones utilizada al crear o editar una política.
- `conorderfee/views/templates/admin/policyRuleCard.tpl`
  - **Salida:** Renderiza una única regla o condición dentro del constructor de condiciones, típicamente una tarjeta o bloque visual.
- `conorderfee/views/templates/admin/policyRulesTable.tpl`
  - **Salida:** Renderiza la tabla de políticas en la vista de lista `AdminconorderfeePolicies`.
- `conorderfee/views/templates/admin/scopeSelector.tpl`
  - **Salida:** Una plantilla para seleccionar el alcance de una condición (por ejemplo, "Carrito", "Producto", "Cliente"), utilizada dentro del constructor de condiciones.

#### Plantillas de Front-office (`views/templates/front/`)

- `conorderfee/controllers/front/index.php` (No se lista un archivo .tpl específico, probablemente maneja la salida directamente o redirige)

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

- `ps_conorderfee_policy`: Almacena las definiciones principales de la política de tarifas (nombre, estado activo, tipo de tarifa, valor, etiqueta, prioridad).
- `ps_conorderfee_condition_group`: Almacena la estructura jerárquica de los grupos de condiciones (lógica AND/OR) dentro de cada política.
- `ps_conorderfee_condition`: Almacena condiciones individuales (tipo, operador, valor) vinculadas a grupos de condiciones.
- `ps_conorderfee_log`: Almacena un registro de auditoría de cada vez que se evaluó una tarifa, incluyendo detalles del carrito, política aplicada, importe de la tarifa y una instantánea del resultado de la evaluación.
- `ps_configuration`: Almacena valores de configuración específicos del módulo como `CONORDERFEE_ENABLED` y `CONORDERFEE_FEE_PRODUCT_ID`.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | No listado explícitamente en la información del módulo, pero a menudo utilizado para cargar CSS/JS del front-office. |
| `displayBeforeCarrier` | Antes de la selección del transportista en la página de pago. | Potencialmente utilizado para reevaluar tarifas si la selección del transportista impacta las condiciones. |
| `actionObjectProductInCartDeleteBefore` | Antes de que se elimine un producto del carrito. | Reevaluar tarifas para ajustar si el producto eliminado era parte de una condición. |
| `actionPresentCart` | Cuando los datos del carrito se presentan al front office. | **CRÍTICO:** Hook principal para inyectar la línea de artículo de la tarifa en el resumen del carrito. |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración, antes de su contenido. | Carga CSS y JavaScript del back-office para las interfaces de administración del módulo. |
| `actionPresentProductListing` | Cuando se presentan listados de productos. | No directamente relacionado con las tarifas, pero podría usarse para indicadores de tarifas específicos de productos. |
| `actionValidateOrderBefore` | Justo antes de que se valide un pedido. | Verificación final y aplicación de tarifas para asegurar que el total del pedido sea correcto. |
| `actionGetProductPropertiesAfter` | Después de que se recuperan las propiedades del producto. | Potencialmente utilizado para identificar productos específicos que activan tarifas. |
| `displayAdminOrder` | En la página de detalles del pedido del Back Office. | Muestra información sobre las tarifas aplicadas para un pedido específico. |
| `actionFrontControllerInitAfter` | Después de que se inicializa un controlador frontal. | Inicialización general del front-office, potencialmente configurando el contexto para la evaluación de tarifas. |
| `actionPresentProduct` | Cuando se presenta un solo producto. | Similar a `actionPresentProductListing`. |
| `actionPresentCartProduct` | Cuando se presenta un producto en el carrito. | Permite la modificación de los datos del producto del carrito, potencialmente para la visualización relacionada con tarifas. |
| `actionProductPriceCalculation` | Durante el cálculo del precio del producto. | Asegura que el precio del producto de tarifa sea correctamente anulado por la tarifa calculada. |
| `actionFrontControllerSetVariables` | Antes de que se asignen las variables Smarty en un controlador frontal. | Pasa datos relacionados con tarifas a las plantillas del front-office. |
| `actionCartSave` | Después de que se guarda un carrito (por ejemplo, cambio de cantidad, adición/eliminación de producto). | **CRÍTICO:** Activa la lógica principal de evaluación de tarifas cada vez que cambia el contenido del carrito. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Registra la aplicación final de la tarifa y la asocia con el nuevo ID de pedido. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, correcciones de errores y soporte técnico dedicado, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Asegúrate de descargar siempre la última versión compatible con tu instalación de PrestaShop.

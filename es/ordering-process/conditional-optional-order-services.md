---
title: "Servicios Opcionales Condicionales para Pedidos - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Servicios Opcionales Condicionales para Pedidos' de MyPresta.eu."
sidebar:
  label: "Servicios Opcionales Condicionales para Pedidos - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Conditional Optional Order Services en MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-optional-order-services.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/conditional-optional-order-services/)
>
> ---


# Servicios Opcionales Condicionales para Pedidos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

El módulo "Servicios Opcionales Condicionales para Pedidos" ofrece un potente conjunto de herramientas para gestionar tus servicios opcionales. Interactuarás principalmente con el módulo a través de sus entradas de menú dedicadas en tu Back Office de PrestaShop.

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla inicial que ves después de instalar el módulo o hacer clic en "Configurar" desde el Gestor de Módulos. Proporciona una forma rápida de habilitar o deshabilitar la funcionalidad principal del módulo.

- **Nombre del Ajuste:** Habilitar Servicios Opcionales Condicionales para Pedidos
- **Qué hace este ajuste:** Este es el interruptor maestro para todo el módulo. Cuando está habilitado, la lógica del módulo se ejecutará y tus servicios definidos se ofrecerán a los clientes según tus políticas. Cuando está deshabilitado, no se ofrecerán servicios y el módulo estará efectivamente inactivo en tu front-office.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* El módulo comenzará a evaluar tus políticas de servicio y a mostrar los servicios relevantes a los clientes en el front-office (por ejemplo, la página de pago).
  - *Cuando está deshabilitado:* Todos los servicios condicionales se ocultarán a los clientes y la lógica del módulo no se ejecutará.
- **Valor recomendado:** **SÍ** (Habilitado) una vez que hayas configurado tus políticas.
- **Escenario / ejemplo de comerciante:** Acabas de instalar el módulo y estás listo para empezar a definir tus servicios. Habilitarías este ajuste para que tus servicios sean visibles para los clientes una vez que estén configurados. Si necesitas dejar de ofrecer temporalmente todos los servicios (por ejemplo, durante el mantenimiento o un período de vacaciones), puedes deshabilitarlo rápidamente aquí sin eliminar tus políticas.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

Después de la configuración inicial, encontrarás nuevas entradas de menú en **Vender > Servicios de Pedido** (o una ubicación similar, dependiendo de tu versión y tema de PrestaShop).

#### 2.2.1 Políticas (Back Office > Vender > Servicios de Pedido > Políticas)

Aquí es donde defines y gestionas todos tus servicios opcionales condicionales para pedidos. Cada "Política" representa un servicio específico que deseas ofrecer, junto con las reglas que determinan cuándo y a quién se ofrece.

- **Nombre de la Pantalla y Ubicación del Menú:** Políticas (En **Vender > Servicios de Pedido** en el menú principal de PrestaShop).
- **Acciones y Ajustes Disponibles:**

  - **Lista de Políticas:** Una tabla que muestra todas tus políticas creadas, su nombre, estado (activo/inactivo) y otra información clave.
  - **Añadir Nueva Política:** Haz clic en este botón para crear un nuevo servicio opcional.
  - **Editar Política:** Haz clic en el icono "Editar" junto a una política existente para modificar sus detalles, condiciones y reglas.
  - **Duplicar Política:** ¡Una característica muy útil! Haz clic en el icono "Duplicar" para crear una copia exacta de una política existente. Esto ahorra tiempo si necesitas crear servicios similares.
  - **Eliminar Política:** Elimina una política permanentemente.
  - **Acciones Masivas:** Selecciona varias políticas y realiza acciones como "Habilitar", "Deshabilitar" o "Eliminar" simultáneamente.
- **Al añadir/editar una Política, configurarás:**

  - **Información General:**
    - **Nombre:** Un nombre interno claro para tu política (por ejemplo, "Servicio de Envoltura de Regalo", "Seguro de Envío Exprés").
    - **Estado:** Habilita o deshabilita esta política específica. Una política inactiva nunca se mostrará a los clientes.
    - **Descripción:** El texto que verán los clientes explicando el servicio. Sé conciso y destaca los beneficios.
    - **Precio:** El costo de este servicio opcional. Se añadirá al carrito del cliente si se selecciona.
    - **Regla de Impuestos:** Selecciona la regla de impuestos aplicable para este servicio (por ejemplo, "Tasa Estándar", "Tasa Reducida").
    - **Imagen/Icono:** Sube una imagen o icono para representar visualmente el servicio a los clientes. Esto lo hace más atractivo y fácil de identificar.
  - **Condiciones:** Este es el núcleo del poder del módulo. Aquí construyes reglas usando un constructor de condiciones visual para determinar *cuándo* se debe ofrecer este servicio.
    - Puedes combinar múltiples condiciones usando la lógica "Y" o "O".
    - **Ejemplos de condiciones:**
      - **Valor del Carrito:** Ofrecer servicio solo si el total del carrito está por encima/debajo de una cierta cantidad.
      - **Producto en el Carrito:** Ofrecer servicio solo si productos específicos o productos de ciertas categorías/fabricantes están en el carrito.
      - **Grupo de Clientes:** Ofrecer servicio solo a grupos de clientes específicos (por ejemplo, "Mayoristas", "Clientes VIP").
      - **Transportista:** Ofrecer servicio solo si se selecciona un transportista específico.
      - **Rango de Fechas:** Ofrecer servicio solo durante un período promocional específico.
      - **País/Zona:** Ofrecer servicio solo a clientes de ciertos países o zonas de envío.
  - **Configuración de Visualización:** Controla cómo aparece el servicio en el front-office.
    - **Posición:** Si se ofrecen varios servicios, puedes establecer su orden de visualización.
    - **Visibilidad:** Dónde exactamente en el proceso de pago aparece el servicio.
- **Efecto de los cambios:**

  - Añadir una nueva política hace que un nuevo servicio opcional esté disponible para su visualización a los clientes, sujeto a sus condiciones.
  - Editar una política cambia su nombre, precio, descripción, imagen o las condiciones bajo las cuales se ofrece. Estos cambios se reflejan inmediatamente en el front-office.
  - Habilitar/deshabilitar una política controla su visibilidad para los clientes.
  - Eliminar una política la elimina por completo y ya no se ofrecerá.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

  1. Comienza definiendo tus servicios más comunes (por ejemplo, envoltura de regalo, seguro).
  2. Utiliza el constructor de condiciones para hacer que estos servicios sean altamente relevantes. Por ejemplo, la envoltura de regalo solo podría ofrecerse para productos físicos, no para descargas digitales.
  3. Revisa regularmente tus políticas, especialmente antes de promociones o ventas estacionales, para asegurarte de que estén activas y configuradas correctamente.
  4. Utiliza la función "Duplicar" para crear rápidamente variaciones de servicios existentes (por ejemplo, "Envoltura de Regalo Premium" vs. "Envoltura de Regalo Estándar").

#### 2.2.2 Registro de Auditoría (Back Office > Vender > Servicios de Pedido > Registro de Auditoría)

Esta pantalla proporciona un historial detallado de todas las acciones relacionadas con las políticas y servicios del módulo. Es una herramienta invaluable para rastrear cambios y solucionar problemas.

- **Nombre de la Pantalla y Ubicación del Menú:** Registro de Auditoría (En **Vender > Servicios de Pedido** en el menú principal de PrestaShop).
- **Acciones y Ajustes Disponibles:**
  - **Lista de Registros:** Una tabla que muestra una lista cronológica de eventos.
  - **Las columnas suelen incluir:**
    - **Fecha:** Cuándo ocurrió el evento.
    - **Empleado:** Qué usuario del Back Office realizó la acción.
    - **Acción:** Qué acción se realizó (por ejemplo, "Política Añadida", "Política Editada", "Política Eliminada", "Módulo Habilitado/Deshabilitado").
    - **Detalles:** Información específica sobre el cambio (por ejemplo, qué política se vio afectada, qué valores se cambiaron).
  - **Filtrado/Búsqueda:** Herramientas para filtrar el registro por fecha, empleado o tipo de acción para encontrar eventos específicos.
- **Efecto de los cambios:** Esta pantalla es solo para visualización; no puedes realizar cambios directos aquí. Sirve como un registro de todas las modificaciones realizadas en la configuración y las políticas del módulo.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  - Utiliza el registro de auditoría para rastrear quién realizó cambios en tus políticas de servicio, especialmente en entornos multiusuario.
  - Si un servicio no aparece como se esperaba, verifica el registro de auditoría para ver si una política fue deshabilitada o modificada accidentalmente.
  - Monitorea cualquier comportamiento inesperado del módulo registrado en los logs.

#### 2.2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Habilitar Servicios Opcionales Condicionales para Pedidos | SÍ (después de la configuración) | Interruptor maestro para la funcionalidad de front-office del módulo. |
| **Políticas (Lista)** | Añadir Nueva Política | N/A | Crea un nuevo servicio opcional con sus propias reglas y precios. |
| **Políticas (Lista)** | Editar Política | N/A | Modifica los detalles, condiciones o visualización de un servicio existente. |
| **Políticas (Lista)** | Duplicar Política | N/A | Crea rápidamente una copia de una política existente para ahorrar tiempo. |
| **Políticas (Lista)** | Eliminar Política | N/A | Elimina permanentemente un servicio opcional. |
| **Políticas (Formulario de Edición)** | Nombre | Nombre Descriptivo | Identificador interno del servicio. |
| **Políticas (Formulario de Edición)** | Estado | Habilitado | Controla si este servicio específico está activo y visible para los clientes. |
| **Políticas (Formulario de Edición)** | Descripción | Explicación clara | Texto que se muestra a los clientes sobre el servicio. |
| **Políticas (Formulario de Edición)** | Precio | 0.00 (establecer valor) | Costo añadido al carrito si se selecciona el servicio. |
| **Políticas (Formulario de Edición)** | Regla de Impuestos | Regla de Impuestos Predeterminada | Impuesto aplicable al servicio. |
| **Políticas (Formulario de Edición)** | Imagen/Icono | Imagen subida | Representación visual del servicio para los clientes. |
| **Políticas (Formulario de Edición)** | Condiciones (Constructor) | Reglas personalizadas | Define *cuándo* y *a quién* se ofrece el servicio (por ejemplo, valor del carrito, producto en el carrito, grupo de clientes). |
| **Políticas (Formulario de Edición)** | Posición | Auto (establecer valor) | Orden de visualización si se ofrecen varios servicios. |
| **Registro de Auditoría** | (Todas las entradas) | N/A | Proporciona un registro histórico de todos los cambios realizados en la configuración y las políticas del módulo. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mis servicios opcionales no aparecen en la página de pago. ¿Qué debo verificar?**
R1:

1.  **¿Módulo Habilitado?** Ve a **Módulos > Gestor de Módulos**, busca "Servicios Opcionales Condicionales para Pedidos" y asegúrate de que esté habilitado.
2.  **¿Estado de la Política?** Ve a **Vender > Servicios de Pedido > Políticas**. Asegúrate de que la política específica que esperas ver esté "Activa".
3.  **¿Se Cumplen las Condiciones de la Política?** Esta es la razón más común. Revisa cuidadosamente las condiciones que has establecido para la política. ¿Tu carrito de prueba actual cumple *todas* las condiciones "Y" y *alguna* de las condiciones "O"? Por ejemplo, si estableces "Total del Carrito > $50" y tu carrito es de $45, el servicio no se mostrará.
4.  **¿Caché?** Borra la caché de PrestaShop en **Parámetros Avanzados > Rendimiento**. A veces, los datos antiguos en caché pueden impedir que aparezcan las nuevas configuraciones del módulo.
5.  **¿Compatibilidad del Tema?** Aunque el módulo está diseñado para una amplia compatibilidad, los temas muy personalizados podrían requerir ajustes menores. Revisa la consola de desarrollador de tu navegador en busca de errores de JavaScript.

**P2: El precio de mi servicio no se añade correctamente al total del carrito.**
R2:

1.  **¿Precio de la Política Establecido?** Vuelve a verificar el campo "Precio" en la configuración de tu política.
2.  **¿Regla de Impuestos Aplicada?** Asegúrate de que la "Regla de Impuestos" correcta esté seleccionada para el servicio. El precio final incluye impuestos basados en esta regla.
3.  **¿Moneda?** Verifica que el precio esté establecido en la moneda predeterminada de tu tienda o que la configuración de varias monedas sea manejada correctamente por PrestaShop.

**P3: ¿Cómo traduzco los nombres y descripciones de los servicios a otros idiomas?**
R3:

1.  Ve a **Internacional > Traducciones** en tu Back Office de PrestaShop.
2.  Selecciona "Traducciones de módulos instalados", elige tu tema y luego selecciona tu idioma.
3.  Busca el módulo "Servicios Opcionales Condicionales para Pedidos". Deberías poder traducir los nombres y descripciones de tus políticas directamente dentro de los formularios de configuración del módulo, ya que suelen almacenarse como campos traducibles. Si no, aparecerán aquí.

**P4: ¿Puedo cambiar el orden en que aparecen los servicios en la página de pago?**
R4: Sí, dentro de la configuración de cada política, debería haber un ajuste de "Posición". Puedes establecer un valor numérico (por ejemplo, 10, 20, 30) para controlar el orden de visualización. Los números más bajos aparecen primero.

**P5: El módulo está causando un problema visual o un conflicto con otro módulo.**
A5:

1.  **Aísla el problema:** Deshabilita temporalmente otros módulos instalados o actualizados recientemente para ver si el conflicto desaparece.
2.  **Busca errores:** Usa la consola de desarrollador de tu navegador (F12) para buscar errores de JavaScript o CSS.
3.  **Contacta con Soporte:** Si no puedes resolverlo, proporciona al soporte de MyPresta.eu detalles sobre el problema, tu versión de PrestaShop y cualquier otro módulo que sospeches que podría estar en conflicto.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Servicios Opcionales Condicionales para Pedidos", destinada a desarrolladores y webmasters.

### 4.1 Resumen de la Arquitectura

El módulo sigue un patrón MVC (Modelo-Vista-Controlador) robusto, típico de los módulos de PrestaShop. Se basa en gran medida en el sistema de hooks de PrestaShop para inyectar su funcionalidad en varios puntos del front-office (pago, página de producto) y del back-office (vista de pedidos de administración, configuración del módulo).
Los componentes arquitectónicos clave incluyen:

- **Políticas (`conorderservicesPolicy`):** La entidad central que representa un servicio opcional, extendiendo `ObjectModel`.
- **Condiciones (`conorderservicesCondition`, `conorderservicesConditionGroup`, `conorderservicesConditionTree`):** Un sistema sofisticado para construir reglas complejas que determinan la elegibilidad del servicio.
- **Motor (`conorderservicesEngine`):** La clase central responsable de evaluar las condiciones y determinar qué servicios presentar al cliente.
- **Registro de Auditoría (`conorderservicesAuditLog`):** Registra todas las acciones significativas dentro del módulo para su trazabilidad.
- **Capa de Compatibilidad (`conorderservicesCompatibility`):** Maneja las diferencias entre PrestaShop 1.7, 8 y 9.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `conorderservices/controllers/front/ajax.php`
  - **Nombre de la Clase:** `ConorderservicesAjaxModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Maneja las solicitudes AJAX desde el front-office, principalmente para actualizar dinámicamente las selecciones de servicios o recalcular los totales del carrito cuando un cliente añade/elimina un servicio. Probablemente envía al `conorderservicesEngine` para realizar cálculos y devuelve respuestas JSON.
- `conorderservices/controllers/front/index.php`
  - **Nombre de la Clase:** `ConorderservicesIndexModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Un controlador de marcador de posición o de reserva. A menudo se utiliza para el acceso directo al módulo si es necesario, aunque la mayoría de la interacción del front-office es a través de hooks o AJAX.

#### Controladores de Administración de Back-Office

- `conorderservices/controllers/admin/AdminconorderservicesAuditLog.php`
  - **Nombre de la Clase:** `AdminconorderservicesAuditLogController` (extiende `ModuleAdminController`)
  - **Nombre de la Pestaña:** Registro de Auditoría (en "Vender > Servicios de Pedido")
  - **Entidad Gestionada:** `conorderservicesAuditLog`
  - **Responsabilidad:** Gestiona la visualización y el filtrado de las entradas del registro de auditoría. Utiliza `HelperList` de PrestaShop para renderizar la tabla de registro.
- `conorderservices/controllers/admin/AdminconorderservicesPolicies.php`
  - **Nombre de la Clase:** `AdminconorderservicesPoliciesController` (extiende `ModuleAdminController`)
  - **Nombre de la Pestaña:** Políticas (en "Vender > Servicios de Pedido")
  - **Entidad Gestionada:** `conorderservicesPolicy`
  - **Responsabilidad:** El controlador principal para gestionar las políticas de servicios opcionales. Maneja la lista, adición, edición, duplicación y eliminación de objetos `conorderservicesPolicy`. Utiliza `HelperList` para la lista de políticas y `HelperForm` para los formularios de añadir/editar políticas, incluyendo el complejo constructor de condiciones.
- `conorderservices/controllers/admin/index.php`
  - **Nombre de la Clase:** `AdminconorderservicesIndexController` (extiende `ModuleAdminController`)
  - **Nombre de la Pestaña:** (Probablemente el punto de entrada principal de "Servicios de Pedido")
  - **Entidad Gestionada:** Ninguna directamente, a menudo redirige a `AdminconorderservicesPolicies` o muestra un panel de control.
  - **Responsabilidad:** Sirve como el punto de entrada principal para la sección de administración del módulo, mostrando potencialmente un panel de control o redirigigiendo a la lista de políticas.

### 4.3 Clases y Modelos Principales (`classes/`)

- `conorderservices/classes/conorderservicesAdmin.php`
  - **Propósito:** Clase de utilidad para funciones específicas de administración, que potencialmente maneja permisos, generación de menús o tareas administrativas comunes.
- `conorderservices/classes/conorderservicesAuditLog.php`
  - **Extiende:** `ObjectModel`
  - **Tabla de Base de Datos:** `ps_conorderservices_log`
  - **Campos `$definition`:** `id_conorderservices_log`, `id_employee`, `action`, `details`, `date_add`
  - **Propósito:** Representa una entrada en el registro de auditoría del módulo. Proporciona métodos para añadir nuevas entradas de registro.
- `conorderservices/classes/conorderservicesCartState.php`
  - **Propósito:** Gestiona y persiste el estado de los servicios opcionales seleccionados dentro del carrito del cliente. Probablemente interactúa con `Context::getContext()->cart` y almacena las selecciones de servicios.
- `conorderservices/classes/conorderservicesCompatibility.php`
  - **Propósito:** Proporciona una capa de abstracción para funciones o comportamientos específicos de la versión de PrestaShop, asegurando que el módulo funcione en 1.7, 8 y 9.
- `conorderservices/classes/conorderservicesCondition.php`
  - **Extiende:** `ObjectModel` (probablemente, o una clase base para condiciones)
  - **Tabla de Base de Datos:** `ps_conorderservices_condition`
  - **Campos `$definition`:** `id_conorderservices_condition`, `id_conorderservices_condition_group`, `type`, `operator`, `value`
  - **Propósito:** Representa una única condición dentro de un grupo de condiciones (por ejemplo, "Total del Carrito" "es mayor que" "100").
- `conorderservices/classes/conorderservicesConditionEvaluator.php`
  - **Propósito:** El motor lógico para evaluar un conjunto de condiciones contra el carrito actual, el cliente y el contexto del producto. Determina si se cumplen las condiciones de una política.
- `conorderservices/classes/conorderservicesConditionGroup.php`
  - **Extiende:** `ObjectModel` (probablemente)
  - **Tabla de Base de Datos:** `ps_conorderservices_condition_group`
  - **Campos `$definition`:** `id_conorderservices_condition_group`, `id_conorderservices_policy`, `logic_operator` (AND/OR)
  - **Propósito:** Agrupa múltiples objetos `conorderservicesCondition`, definiendo la relación lógica entre ellos (AND/OR).
- `conorderservices/classes/conorderservicesConditionTree.php`
  - **Propósito:** Gestiona la estructura jerárquica de grupos de condiciones y condiciones individuales, permitiendo la construcción de reglas complejas.
- `conorderservices/classes/conorderservicesContext.php`
  - **Propósito:** Un envoltorio o extensión de la clase `Context` de PrestaShop, que proporciona datos de contexto específicos del módulo (por ejemplo, carrito actual, cliente, idioma) para la evaluación de condiciones.
- `conorderservices/classes/conorderservicesDashboard.php`
  - **Propósito:** Proporciona datos y lógica para la vista del panel de control del módulo (si la hay), mostrando potencialmente análisis o estadísticas rápidas.
- `conorderservices/classes/conorderservicesEngine.php`
  - **Propósito:** La unidad de procesamiento central del módulo. Recupera las políticas activas, las pasa al `ConditionEvaluator` y determina qué servicios son elegibles para el carrito actual. También maneja la adición/eliminación de productos de servicio del carrito.
- `conorderservices/classes/conorderservicesListRenderer.php`
  - **Propósito:** Clase auxiliar para renderizar listas en el Back Office, que potencialmente extiende `HelperList` o proporciona lógica de renderizado personalizada.
- `conorderservices/classes/conorderservicesLog.php`
  - **Propósito:** Alias o implementación específica para el registro, posiblemente distinta de `conorderservicesAuditLog` para diferentes tipos de registro.
- `conorderservices/classes/conorderservicesPolicy.php`
  - **Extiende:** `ObjectModel`
  - **Tabla de Base de Datos:** `ps_conorderservices_policy`
  - **Campos `$definition`:** `id_conorderservices_policy`, `name`, `description`, `price`, `id_tax_rule`, `image`, `active`, `position`, `date_add`, `date_upd` (y campos `_lang` para `name`, `description` traducibles).
  - **Propósito:** El modelo central para un servicio opcional. Almacena toda la configuración de un servicio, incluidos sus detalles, precio, imagen y grupos de condiciones asociados.
- `conorderservices/classes/conorderservicesPolicyDuplicator.php`
  - **Propósito:** Maneja la lógica para duplicar una política completa, incluidas sus condiciones y datos asociados.
- `conorderservices/classes/conorderservicesPreset.php`
  - **Propósito:** Probablemente proporciona conjuntos predefinidos de condiciones o políticas que el comerciante puede cargar rápidamente.
- `conorderservices/classes/conorderservicesRule.php`
  - **Propósito:** Un término más genérico para una condición o un conjunto de condiciones. Podría ser una clase base abstracta o un tipo específico de regla.
- `conorderservices/classes/ConorderservicesRuleImage.php`
  - **Propósito:** Gestiona las imágenes/iconos asociados con políticas o reglas.
- `conorderservices/classes/ConorderservicesServiceProduct.php`
  - **Extiende:** `Product` (o un envoltorio alrededor de él)
  - **Propósito:** Representa el "producto virtual" que se añade al carrito cuando un cliente selecciona un servicio opcional. Asegura que el servicio se comporte como un producto normal para el procesamiento del carrito y del pedido.
- `conorderservices/classes/conorderservicesTreeRepository.php`
  - **Propósito:** Gestiona el almacenamiento y la recuperación de la estructura del árbol de condiciones.
- `conorderservices/classes/index.php`
  - **Propósito:** Archivo vacío estándar para evitar la lista de directorios.
- `conorderservices/classes/load.php`
  - **Propósito:** Archivo de autocarga o un archivo que incluye otras definiciones de clases.

### 4.4 Activos JavaScript (`views/js/`)

- `conorderservices/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office (para selección de productos/categorías en el constructor de condiciones)
  - **Detalles:** Proporciona funcionalidad de autocompletado para campos de entrada, probablemente utilizada al seleccionar productos, categorías o fabricantes dentro del constructor de condiciones.
- `conorderservices/lib/searchTool/views/views/js/autocomplete.js`
  - **Alcance:** Back-office (redundante o específico para una vista diferente de la herramienta de búsqueda)
  - **Detalles:** Similar al anterior, probablemente una duplicación o versión específica del script de autocompletado.
- `conorderservices/views/js/adminConditionBuilder.js`
  - **Alcance:** Back-office (`AdminconorderservicesPoliciesController`)
  - **Detalles:** JS principal para el constructor de condiciones visual. Maneja la adición/eliminación de condiciones y grupos de condiciones, la gestión de operadores lógicos (AND/OR) y la actualización de la interfaz de usuario según la entrada del usuario.
- `conorderservices/views/js/adminconorderservicesDashboard.js`
  - **Alcance:** Back-office (`AdminconorderservicesIndexController` o vista de Panel de Control)
  - **Detalles:** Scripts para elementos interactivos en el panel de control del módulo, como gráficos, estadísticas o enlaces rápidos.
- `conorderservices/views/js/adminconorderservicesSearchTool.js`
  - **Alcance:** Back-office (`AdminconorderservicesPoliciesController`)
  - **Detalles:** Integra la herramienta de búsqueda (autocompletado) con el constructor de condiciones, permitiendo a los administradores encontrar y seleccionar fácilmente entidades (productos, categorías, etc.) para las condiciones.
- `conorderservices/views/js/adminconorderservicesSimulator.js`
  - **Alcance:** Back-office (`AdminconorderservicesPoliciesController` - probablemente una pestaña o modal dedicado)
  - **Detalles:** Proporciona funcionalidad para un simulador de políticas, permitiendo a los administradores probar condiciones con datos de carrito simulados para ver qué servicios se ofrecerían.
- `conorderservices/views/js/adminPolicyRuleImage.js`
  - **Alcance:** Back-office (`AdminconorderservicesPoliciesController`)
  - **Detalles:** Maneja la carga de imágenes y la funcionalidad de vista previa para iconos/imágenes de políticas.
- `conorderservices/views/js/adminPolicyRules.js`
  - **Alcance:** Back-office (`AdminconorderservicesPoliciesController`)
  - **Detalles:** Scripts generales para gestionar las reglas de las políticas, que potencialmente incluyen la reordenación por arrastrar y soltar u otras interacciones de la interfaz de usuario en la página de edición de políticas.
- `conorderservices/views/js/adminSettingsOfferDisplay.js`
  - **Alcance:** Back-office (Configuración Principal del Módulo o Edición de Políticas)
  - **Detalles:** Scripts relacionados con la configuración de cómo y dónde se muestran los servicios opcionales en el front-office.
- `conorderservices/views/js/checkout.js`
  - **Alcance:** Front-office (Página de Pago)
  - **Detalles:** Este es el script crítico del front-office. Escucha las interacciones del usuario (por ejemplo, marcar/desmarcar un servicio), envía solicitudes AJAX a `ajax.php` para actualizar el carrito y actualiza dinámicamente el resumen y el total del carrito en la página de pago. Probablemente se vincula a eventos `prestashop.on` para actualizaciones del carrito.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `conorderservices/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back-office
  - **Detalles:** Estilos para los desplegables de autocompletado y los campos de entrada utilizados en la herramienta de búsqueda de administración.
- `conorderservices/lib/searchTool/views/views/css/autocomplete.css`
  - **Alcance:** Back-office (redundante o específico para una vista diferente de la herramienta de búsqueda)
  - **Detalles:** Similar al anterior, probablemente una duplicación o versión específica de los estilos de autocompletado.
- `conorderservices/views/css/admin_conorderservices.css`
  - **Alcance:** Back-office
  - **Detalles:** Estilo general para las páginas de administración del módulo, incluida la lista de políticas, el constructor de condiciones y el registro de auditoría. Contiene estilos para elementos de formulario, tablas y componentes de interfaz de usuario personalizados.
- `conorderservices/views/css/front.css`
  - **Alcance:** Front-office
  - **Detalles:** Estilos para cómo se muestran los servicios opcionales en la página de pago. Incluye estilos para el bloque de servicios, filas de servicios individuales, casillas de verificación, precios e iconos. Los desarrolladores pueden anular estas clases en el `custom.css` o `theme.css` de su tema.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)

- `conorderservices/views/templates/hook/admin_order.tpl`
  - **Hook:** `displayAdminOrder`
  - **Salida:** Muestra información sobre los servicios opcionales seleccionados dentro de la vista de pedidos del Back Office de PrestaShop. Esto permite a los administradores ver qué servicios se compraron con un pedido.
- `conorderservices/views/templates/hook/checkout_services.tpl`
  - **Hook:** `displayShoppingCart`, `displayShoppingCartFooter` (o hooks de pago similares)
  - **Salida:** La plantilla principal para renderizar la lista de servicios opcionales disponibles en la página de pago del front-office. Itera a través de las políticas elegibles y las muestra.
- `conorderservices/views/templates/hook/partials/checkout_offer_row.tpl`
  - **Hook:** Incluido por `checkout_services.tpl`
  - **Salida:** Renderiza una sola fila o tarjeta para un servicio opcional dentro de la lista de pago, incluyendo su nombre, descripción, precio y entrada de selección (por ejemplo, casilla de verificación).

#### Plantillas de Administración (`views/templates/admin/`)

- `conorderservices/views/templates/admin/auditPreview.tpl`
  - **Propósito:** Renderiza una vista detallada o previa de una entrada del registro de auditoría.
- `conorderservices/views/templates/admin/dashboard.tpl`
  - **Propósito:** La plantilla principal para el panel de control del módulo en el Back Office, que potencialmente muestra análisis o información resumida.
- `conorderservices/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Propósito:** Plantilla personalizada para el botón de acción "Duplicar" en las vistas de `HelperList` (específicamente para políticas).
- `conorderservices/views/templates/admin/policiesPreview.tpl`
  - **Propósito:** Renderiza una vista previa de una política, potencialmente utilizada en un simulador o vista rápida.
- `conorderservices/views/templates/admin/policyConditionBuilder.tpl`
  - **Propósito:** La plantilla para la interfaz del constructor de condiciones visual dentro del formulario de edición de políticas. Esta es una plantilla compleja que añade/elimina dinámicamente grupos de condiciones y condiciones individuales.
- `conorderservices/views/templates/admin/policyRuleCard.tpl`
  - **Propósito:** Renderiza una sola regla o grupo de condiciones como una tarjeta dentro del constructor de condiciones, haciéndolo visualmente distinto.
- `conorderservices/views/templates/admin/policyRulesTable.tpl`
  - **Propósito:** Renderiza una estructura similar a una tabla para mostrar reglas, posiblemente una alternativa o un componente dentro del constructor de condiciones.
- `conorderservices/views/templates/admin/scopeSelector.tpl`
  - **Propósito:** Plantilla para seleccionar el alcance de una condición (por ejemplo, producto, categoría, cliente).

#### Plantillas de Biblioteca (`conorderservices/lib/searchTool/views/`)

- `conorderservices/lib/searchTool/views/helpers.tpl`
  - **Propósito:** Plantillas auxiliares para la herramienta de búsqueda, posiblemente para renderizar resultados de búsqueda o campos de entrada.
- `conorderservices/lib/searchTool/views/scripts.tpl`
  - **Propósito:** Incluye JavaScript para la herramienta de búsqueda.
- `conorderservices/lib/searchTool/views/views/scripts.tpl`
  - **Propósito:** Versión duplicada o específica de los scripts de la herramienta de búsqueda.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

- `ps_conorderservices_policy`
  - Almacena la información principal de la política: `id_conorderservices_policy`, `name`, `description`, `price`, `id_tax_rule`, `image`, `active`, `position`, `date_add`, `date_upd`.
  - También incluye campos específicos del idioma para `name` y `description` (por ejemplo, `ps_conorderservices_policy_lang`).
- `ps_conorderservices_condition_group`
  - Almacena grupos de condiciones: `id_conorderservices_condition_group`, `id_conorderservices_policy`, `logic_operator` (AND/OR).
- `ps_conorderservices_condition`
  - Almacena condiciones individuales: `id_conorderservices_condition`, `id_conorderservices_condition_group`, `type`, `operator`, `value`.
- `ps_conorderservices_log`
  - Almacena entradas del registro de auditoría: `id_conorderservices_log`, `id_employee`, `action`, `details`, `date_add`.
- `ps_conorderservices_cart_state` (probable)
  - Almacena qué servicios están seleccionados para un carrito dado: `id_cart`, `id_conorderservices_policy`, `date_add`.
- `ps_configuration`
  - `CONORDERSERVICES_ENABLED`: Almacena el estado maestro de habilitación/deshabilitación del módulo.
  - `PS_CURRENCY_DEFAULT`: Se utiliza para mostrar precios en la administración.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `ActionObjectProductInCartDeleteBefore` | Antes de que se elimine un producto del carrito. | Asegura que si se elimina un producto requerido para un servicio, el servicio también se elimine o se reevalúe. |
| `actionPresentCart` | Cuando se presentan los datos del carrito (por ejemplo, en la página de pago). | Inyecta la lista de servicios opcionales elegibles en los datos de presentación del carrito. |
| `ActionAdminControllerSetMedia` | Cuando se carga un controlador de administración y se establecen sus medios (JS/CSS). | Inyecta JS y CSS específicos del módulo para las páginas del Back Office (políticas, registro de auditoría, constructor de condiciones). |
| `ActionPresentProductListing` | Cuando se presentan los datos del producto en una lista (por ejemplo, página de categoría). | Potencialmente utilizado para mostrar indicadores de disponibilidad de servicio en las listas de productos. |
| `ActionValidateOrderBefore` | Antes de que se valide un pedido. | Realiza comprobaciones finales sobre los servicios seleccionados, asegura que sigan siendo válidos y los añade como detalles del pedido. |
| `ActionGetProductPropertiesAfter` | Después de recuperar las propiedades del producto. | Potencialmente modifica las propiedades del producto si un servicio las afecta (por ejemplo, añadiendo un producto virtual para el servicio). |
| `DisplayAdminOrder` | En la página de detalles del pedido del Back Office. | Muestra los servicios opcionales seleccionados asociados con el pedido. |
| `ActionFrontControllerInitAfter` | Después de que se inicializa un controlador de front-office. | Inicializa el contexto o la lógica del front-office específicos del módulo. |
| `ActionPresentProduct` | Cuando se presentan los datos de un solo producto (por ejemplo, página de producto). | Potencialmente utilizado para mostrar indicadores de disponibilidad de servicio en las páginas de productos. |
| `ActionPresentCartProduct` | Cuando se presenta un producto en el carrito. | Modifica la presentación de los productos del carrito si los servicios están asociados a ellos. |
| `ActionProductPriceCalculation` | Durante el cálculo del precio del producto. | Asegura que los precios de los servicios se tengan en cuenta correctamente en el total. |
| `DisplayShoppingCart` | En la página del carrito de compras. | Muestra el bloque de servicios opcionales. |
| `DisplayShoppingCartFooter` | En el pie de página del carrito de compras. | Ubicación alternativa o adicional para el bloque de servicios opcionales. |
| `ActionCartSave` | Después de guardar un carrito. | Persiste el estado de los servicios opcionales seleccionados en el carrito. |
| `ActionValidateOrder` | Después de que se ha validado un pedido. | Finaliza el pedido con los servicios seleccionados, potencialmente actualizando el inventario o activando acciones de seguimiento. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Servicios Opcionales Condicionales para Pedidos", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta relacionada con la funcionalidad y compatibilidad del módulo.

---
title: "Descuentos Condicionales en Pedidos - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Descuentos Condicionales en Pedidos para PrestaShop de MyPresta.eu."
sidebar:
  label: "Descuentos Condicionales en Pedidos - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Conditional Order Discounts en MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-discounts.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/conditional-order-discounts/)
>
> ---


# Descuentos Condicionales en Pedidos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página principal de configuración del módulo.

- **Habilitar Descuentos Condicionales en Pedidos:**
  - **Qué hace este ajuste:** Este es el interruptor maestro para todo el módulo. Cuando está habilitado, la lógica del módulo para aplicar descuentos condicionales estará activa en su tienda. Cuando está deshabilitado, no se aplicarán descuentos condicionales, independientemente de las políticas que haya creado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El módulo comenzará a evaluar sus políticas de descuento definidas y a aplicar descuentos o regalos gratuitos a los carritos de los clientes a medida que califiquen.
    - *Cuando está deshabilitado:* Todas las políticas de descuento condicional creadas con este módulo serán ignoradas y no se aplicarán descuentos.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Acaba de terminar de configurar su primera política de "Compre 2, Llévate 1 Gratis" y quiere que se active. Habilitaría este ajuste. Si necesita pausar temporalmente todos los descuentos condicionales para una venta en toda la tienda gestionada por otros medios, lo deshabilitaría.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

El módulo Descuentos Condicionales en Pedidos añade un nuevo elemento de menú principal a su Back Office de PrestaShop, generalmente bajo **Catálogo** o **Marketing**, llamado **"Descuentos Condicionales"**. Este menú contiene varios subelementos para gestionar sus políticas y revisar los registros.

#### 2.2.1 Descuentos Condicionales > Políticas (AdminConorderdisPoliciesController)

Aquí es donde define y gestiona todas sus políticas de descuento condicional.

- **Nombre de la Pantalla y Ubicación del Menú:** Back Office > Descuentos Condicionales > Políticas
- **Acciones y Ajustes Disponibles:**

  - **Lista de Políticas:** Verá una tabla que enumera todas sus políticas de descuento existentes. Cada política mostrará su nombre, estado (activo/inactivo) y otros detalles clave.
  - **Añadir Nueva Política:** Haga clic en el botón "Añadir nueva política" para crear una nueva regla de descuento condicional.
  - **Editar Política:** Haga clic en el icono "Editar" junto a una política existente para modificar sus condiciones, promociones o ajustes.
  - **Duplicar Política:** ¡Esta es una característica muy útil! Haga clic en el icono "Duplicar" para crear una copia exacta de una política existente. Esto ahorra mucho tiempo si necesita crear promociones similares.
  - **Habilitar/Deshabilitar Política:** Puede activar o desactivar rápidamente políticas individuales directamente desde la lista.
  - **Eliminar Política:** Elimine una política de su tienda.
  - **Formulario de Configuración de Política (al añadir/editar):**
    - **Nombre de la Política:** Un nombre descriptivo para su referencia interna (por ejemplo, "Camisetas BOGO", "Gaste 100€, Obtenga 10% de Descuento").
    - **Estado (Activo/Inactivo):** Controla si esta política específica está actualmente activa en su tienda.
    - **Constructor de Condiciones:** Este es el núcleo del módulo. Utilizará una interfaz visual para definir *cuándo* se aplica el descuento. Ejemplos:
      - "El total del carrito es mayor que 100€"
      - "El cliente está en el grupo 'Mayoristas'"
      - "El producto 'X' está en el carrito con una cantidad >= 2"
      - "Cualquier producto de la categoría 'Rebajas de Verano' está en el carrito"
      - Puede combinar múltiples condiciones con lógica "Y" u "O".
    - **Constructor de Promociones:** Esto define *qué* descuento o regalo recibe el cliente si se cumplen las condiciones. Ejemplos:
      - "Aplicar 10% de descuento a todo el pedido"
      - "Regalar el artículo más barato de la categoría 'Accesorios'"
      - "Añadir el producto 'Caja de Regalo' al carrito gratis"
      - "Aplicar 50% de descuento a la segunda unidad del producto 'Y'"
    - **Selector de Alcance:** Defina a qué tiendas (para configuraciones multitienda), grupos de clientes o monedas se aplica esta política.
    - **Prioridad:** Si varias políticas pudieran aplicarse a un solo carrito, esto determina cuál tiene precedencia. Los números más bajos significan mayor prioridad.
    - **Fechas de Validez:** Establezca una fecha de inicio y fin para la promoción.
    - **Simulador de Carrito:** Una potente herramienta dentro del editor de políticas que le permite añadir productos a un carrito simulado y ver instantáneamente si su política se aplica y qué descuento se otorga. ¡Esto es crucial para las pruebas!
- **Efecto de los cambios:**

  - Añadir una nueva política hace que una nueva promoción esté disponible (si está activa) en su tienda.
  - Editar una política cambia las condiciones o promociones de una oferta existente.
  - Habilitar/deshabilitar políticas controla directamente su visibilidad y aplicación en el front office.
  - Duplicar políticas permite la creación rápida de promociones similares sin empezar de cero.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

  1. **Planifique su promoción:** Decida la oferta (por ejemplo, "Compre 3, llévese 1 gratis en todos los calcetines").
  2. **Cree una nueva política:** Vaya a "Políticas" y haga clic en "Añadir nueva política".
  3. **Defina las condiciones:** Utilice el constructor visual para especificar qué productos, categorías, cantidades o valores de carrito activan el descuento.
  4. **Defina las promociones:** Especifique el tipo de descuento (porcentaje, cantidad fija, regalo gratuito) y a qué se aplica.
  5. **Pruebe a fondo con el Simulador de Carrito:** Antes de guardar, utilice el simulador para añadir varios productos y cantidades para asegurarse de que el descuento se aplica exactamente como se desea.
  6. **Establezca las fechas de validez y la prioridad:** Asegúrese de que la promoción se ejecute solo cuando usted quiera y que interactúe correctamente con otras promociones.
  7. **Active la política:** Una vez probada y lista, establezca su estado en "Activa".
  8. **Supervise con el Registro de Auditoría:** Revise el Registro de Auditoría (consulte la siguiente sección) para confirmar que las políticas se están aplicando correctamente en los carritos en vivo.

#### 2.2.2 Descuentos Condicionales > Registro de Auditoría (AdminConorderdisAuditLogController)

Esta pantalla proporciona un historial detallado de cómo se han aplicado (o intentado aplicar) sus políticas de descuento condicional a los carritos de los clientes.

- **Nombre de la Pantalla y Ubicación del Menú:** Back Office > Descuentos Condicionales > Registro de Auditoría
- **Acciones y Ajustes Disponibles:**
  - **Lista de Registros:** Una tabla que muestra las entradas para cada vez que se evaluó una política. Cada entrada suele incluir:
    - **Fecha/Hora:** Cuándo ocurrió el evento.
    - **Cliente:** Qué cliente (si ha iniciado sesión) estuvo involucrado.
    - **ID del Carrito:** El ID del carrito de compras.
    - **Nombre de la Política:** Qué política se evaluó.
    - **Resultado:** Si se cumplieron las condiciones de la política y si se aplicó un descuento.
    - **Detalles:** Información más específica sobre las condiciones cumplidas, el descuento aplicado o por qué no se aplicó.
  - **Filtrado y Búsqueda:** Puede filtrar el registro por fecha, cliente, política o resultado para encontrar rápidamente eventos específicos.
- **Efecto de los cambios:** Esta es una pantalla de solo lectura. No realiza cambios aquí, sino que observa el comportamiento del módulo.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  - **Resolución de problemas:** Si un cliente informa de un problema con un descuento que no se aplica, o si sospecha que una política no funciona como se esperaba, consulte el registro de auditoría. Puede ver exactamente lo que sucedió cuando se evaluó su carrito.
  - **Supervisión:** Revise regularmente el registro para asegurarse de que sus promociones se están activando correctamente e identificar cualquier comportamiento inesperado.
  - **Comprensión de las interacciones de las políticas:** Si tiene varias políticas, el registro puede ayudarle a comprender qué políticas se están considerando y cuál se aplica finalmente en función de las prioridades.

#### 2.2.3 Descuentos Condicionales > Panel de Control (AdminConorderdisDashboardController)

Esta pantalla proporciona una visión general y, potencialmente, acceso rápido a las funcionalidades clave del módulo.

- **Nombre de la Pantalla y Ubicación del Menú:** Back Office > Descuentos Condicionales > Panel de Control
- **Acciones y Ajustes Disponibles:** Este panel de control suele proporcionar:
  - **Estadísticas de Resumen:** Recuentos rápidos de políticas activas, políticas totales o entradas recientes del registro de auditoría.
  - **Enlaces Rápidos:** Atajos para "Añadir Nueva Política", "Ver Políticas" o "Ver Registro de Auditoría".
  - **Acceso al Simulador:** Un enlace prominente o una herramienta incrustada para el Simulador de Carrito para probar rápidamente las políticas.
  - **Estado del Módulo:** Indicación de si el módulo está habilitado o deshabilitado.
- **Efecto de los cambios:** Esta es principalmente una pantalla informativa y de navegación. Los cambios se realizan a través de las secciones vinculadas "Políticas" o "Registro de Auditoría".
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esto como punto de partida para gestionar sus promociones, obtener una visión general rápida de sus campañas activas y acceder al simulador para realizar pruebas.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Habilitar Descuentos Condicionales en Pedidos | SÍ | Interruptor maestro para activar/desactivar todas las funcionalidades del módulo. |
| Políticas (Añadir/Editar) | Nombre de la Política | Nombre Descriptivo | Etiqueta interna para su promoción. |
| Políticas (Añadir/Editar) | Estado | Activo | Controla si una política específica está activa en la tienda. |
| Políticas (Añadir/Editar) | Constructor de Condiciones | Varía | Define los criterios de elegibilidad para el descuento (por ejemplo, total del carrito, productos en el carrito). |
| Políticas (Añadir/Editar) | Constructor de Promociones | Varía | Define el descuento o regalo gratuito aplicado (por ejemplo, % de descuento, producto gratuito). |
| Políticas (Añadir/Editar) | Selector de Alcance | Todas las Tiendas/Grupos/Monedas | Limita la aplicación de la política a contextos específicos. |
| Políticas (Añadir/Editar) | Prioridad | Número más bajo = mayor prioridad | Determina qué política se aplica si varias son elegibles. |
| Políticas (Añadir/Editar) | Fechas de Validez | Sin fecha de finalización | Establece el período activo para la promoción. |
| Políticas (Añadir/Editar) | Simulador de Carrito | N/A | Herramienta para probar la aplicación de la política antes de guardar. |
| Políticas (Lista) | Acción Duplicar Política | N/A | Crea una copia de una política existente, ahorrando tiempo de configuración. |
| Registro de Auditoría | Entradas del Registro | N/A | Registra cada evaluación de política, mostrando éxito/fracaso y detalles. |
| Panel de Control | Enlaces Rápidos / Resumen | N/A | Proporciona una visión general y atajos a las características clave del módulo. |

## 3. Resolución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Mi descuento no se aplica, aunque he configurado una política.**
R1:

- **¿Está habilitado el módulo?** Vaya a **Módulos > Gestor de Módulos > Descuentos Condicionales en Pedidos** y asegúrese de que el interruptor principal esté ENCENDIDO.
- **¿Está activa la política específica?** Vaya a **Descuentos Condicionales > Políticas** y compruebe la columna "Estado" de su política.
- **¿Se cumplen las condiciones?** Utilice el **Simulador de Carrito** dentro del editor de políticas. Añada productos al carrito simulado exactamente como lo haría un cliente. ¿El simulador muestra que se aplica el descuento? Si no es así, revise sus condiciones cuidadosamente.
- **Compruebe las fechas de validez:** ¿Está la política dentro de su rango de fechas activo?
- **Compruebe la prioridad:** Si varias políticas pudieran aplicarse, asegúrese de que la que espera que se aplique tenga la prioridad correcta (número más bajo = mayor prioridad).
- **Borre la caché de PrestaShop:** Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché". A veces, los datos en caché pueden impedir que las nuevas reglas surtan efecto inmediatamente.

**P2: El descuento se aplica, pero no es la cantidad o el producto correcto.**
R2:

- **Revise su Constructor de Promociones:** Vuelva a verificar el tipo de descuento (porcentaje, cantidad fija), el valor y a qué se aplica (pedido completo, productos específicos, artículo más barato, etc.).
- **Vuelva a comprobar las condiciones:** A veces, una condición sutil puede llevar a un resultado inesperado. Por ejemplo, si tiene "cualquier producto de la categoría X" pero el cliente tiene productos de otras categorías que también cumplen una regla de "artículo más barato".
- **Utilice el Simulador de Carrito de forma extensiva:** Esta es su mejor herramienta para verificar reglas complejas. Pruebe casos extremos.
- **Registro de Auditoría:** Vaya a **Descuentos Condicionales > Registro de Auditoría** para ver los detalles exactos de cómo el módulo evaluó el carrito y qué descuento intentó aplicar. Esto puede revelar discrepancias.

**P3: Mi tema personalizado no muestra claramente los mensajes de descuento o los regalos gratuitos.**
R3:

- El módulo se integra con las reglas de carrito nativas de PrestaShop, por lo que el descuento en sí debería aparecer en el resumen del carrito. Sin embargo, si desea que aparezcan mensajes personalizados como "¡Ha calificado para un regalo gratuito!" o "¡Compre 2, Llévate 1 Gratis!" dinámicamente en las páginas de productos o en el carrito, esto generalmente requiere modificaciones personalizadas del tema.
- **Consulte a un desarrollador:** Su webmaster o un desarrollador de PrestaShop puede ayudarle a integrar mensajes dinámicos en los archivos `product.tpl`, `cart.tpl` o `checkout.tpl` de su tema, potencialmente utilizando los hooks del módulo (consulte la Guía del Desarrollador).

**P4: ¿Puedo usar este módulo con otros módulos de descuento o reglas de carrito nativas?**
R4:

- Sí, este módulo funciona creando y gestionando reglas de carrito nativas de PrestaShop en segundo plano. Esto significa que generalmente es compatible con otros módulos que también dependen del sistema de descuentos central de PrestaShop.
- **La prioridad es clave:** Tenga en cuenta la configuración de prioridad para sus políticas de Descuentos Condicionales en Pedidos y cualquier otra regla de carrito nativa que haya creado manualmente. PrestaShop aplica los descuentos en función de su prioridad. Pruebe a fondo con el Simulador de Carrito y revise el Registro de Auditoría si tiene muchas promociones superpuestas.

**P5: ¿Cómo gestiono las traducciones multilingües para los nombres o descripciones de las políticas?**
R5:

- Los nombres de las políticas y cualquier texto personalizado que introduzca para las condiciones o promociones se gestionan normalmente directamente en la pantalla de edición de políticas. La interfaz de traducción estándar de PrestaShop (en **Internacional > Traducciones**) puede no aplicarse directamente al contenido dinámico generado por el constructor de políticas del módulo.
- Si el módulo proporciona campos específicos para diferentes idiomas dentro del editor de políticas, utilícelos. De lo contrario, asegúrese de que los nombres de sus políticas sean claros y concisos, o considere añadir bloques de información estáticos en su tema para diferentes idiomas para explicar las promociones.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la arquitectura técnica del módulo Descuentos Condicionales en Pedidos, detallando su estructura de archivos, clases, controladores y puntos de integración para desarrolladores y webmasters.

### 4.1 Resumen de la Arquitectura

El módulo Descuentos Condicionales en Pedidos está construido siguiendo el patrón MVC (Modelo-Vista-Controlador) de PrestaShop. Aprovecha en gran medida el sistema nativo `CartRule` de PrestaShop, actuando eficazmente como un constructor y gestor de reglas avanzado para estos objetos centrales. Introduce varias clases `ObjectModel` personalizadas para gestionar políticas, condiciones, promociones y un registro de auditoría. El módulo utiliza un motor robusto para evaluar condiciones complejas contra el estado del carrito de un cliente y luego materializa los objetos `CartRule` apropiados. También incluye un sofisticado constructor de condiciones y un simulador en el Back Office para facilitar su uso.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

- `conorderdis/controllers/front/index.php`
  - **Nombre de la Clase:** `ConorderdisIndexModuleFrontController` (o similar, dependiendo de la versión de PrestaShop y la estructura del módulo, a menudo `ModuleFrontController`).
  - **Responsabilidad:** Este archivo suele servir como marcador de posición o punto de entrada predeterminado para las interacciones del módulo en el front-office. En el contexto de este módulo, los controladores directos del front-office son menos críticos ya que la mayor parte de la lógica se maneja a través de hooks que interactúan con el proceso de carrito y pedido. Podría manejar solicitudes AJAX relacionadas con actualizaciones del carrito o interacciones específicas del front-end si se implementan, pero la lógica central de descuento se ejecuta a través de hooks.

#### Controladores de Administración del Back-Office

- `conorderdis/controllers/admin/AdminconorderdisAuditLog.php`
  - **Nombre de la Pestaña:** Descuentos Condicionales > Registro de Auditoría
  - **Entidad Gestionada:** `ConorderdisAuditLog` (se mapea a la tabla `ps_conorderdis_log`).
  - **Responsabilidad:** Gestiona la visualización y el filtrado de las entradas del registro de auditoría. Extiende `AdminController` y utiliza `HelperList` para renderizar la tabla de registro, permitiendo a los administradores revisar cómo se aplicaron o evaluaron las políticas contra los carritos de los clientes.
- `conorderdis/controllers/admin/AdminconorderdisPolicies.php`
  - **Nombre de la Pestaña:** Descuentos Condicionales > Políticas
  - **Entidad Gestionada:** `ConorderdisPolicy` (se mapea a la tabla `ps_conorderdis_policy`).
  - **Responsabilidad:** Este es el controlador principal para gestionar las políticas de descuento. Extiende `AdminController` y proporciona funcionalidad CRUD (Crear, Leer, Actualizar, Eliminar) para las políticas. Integra los constructores visuales de condiciones y promociones, el selector de productos y el simulador de carrito. Utiliza `HelperList` para la descripción general de las políticas y `HelperForm` para los formularios de añadir/editar políticas.
- `conorderdis/controllers/admin/index.php`
  - **Responsabilidad:** Esta es una práctica estándar de PrestaShop para evitar la lista de directorios. Normalmente contiene una simple declaración `die('No direct script access allowed');`. No gestiona ninguna entidad específica ni proporciona funcionalidad más allá de la seguridad.

### 4.3 Clases y Modelos Centrales (`classes/`)

- `conorderdis/classes/ConorderdisAdmin.php`
  - **Responsabilidad:** Probablemente contiene métodos de ayuda o utilidades específicamente para la administración del Back Office, como la renderización de elementos de formulario específicos, el manejo de solicitudes AJAX de formularios de administración o la gestión de configuraciones específicas del módulo.
- `conorderdis/classes/ConorderdisAuditLog.php`
  - **Extiende:** `ObjectModel`
  - **Tabla de Base de Datos:** `ps_conorderdis_log`
  - **Campos `$definition`:** Almacena detalles sobre las evaluaciones de políticas, incluyendo `id_cart`, `id_customer`, `id_policy`, `result`, `details`, `date_add`.
  - **Responsabilidad:** Representa una entrada en el registro de auditoría. Proporciona métodos para registrar eventos de aplicación de políticas, éxitos y fallos.
- `conorderdis/classes/ConorderdisCartRuleManager.php`
  - **Responsabilidad:** Gestiona la creación, actualización y eliminación de objetos `CartRule` nativos de PrestaShop basados en las definiciones de `ConorderdisPolicy` del módulo. Esta clase es crucial para traducir las reglas complejas del módulo en descuentos estándar de PrestaShop.
- `conorderdis/classes/ConorderdisCartState.php`
  - **Responsabilidad:** Encapsula el estado actual del carrito de un cliente, proporcionando una capa de abstracción para que el motor de descuentos evalúe las condiciones. Podría incluir métodos para recuperar el total del carrito, las cantidades de productos, el grupo de clientes, etc.
- `conorderdis/classes/ConorderdisCompatibility.php`
  - **Responsabilidad:** Maneja las capas de compatibilidad para diferentes versiones de PrestaShop (por ejemplo, 1.7.x, 8.x, 9.x) o versiones específicas de PHP. Asegura que el módulo funcione correctamente en todo el rango de entornos compatibles al proporcionar polyfills o implementaciones alternativas para funciones/métodos obsoletos.
- `conorderdis/classes/ConorderdisConditionTree.php`
  - **Responsabilidad:** Gestiona la compleja estructura lógica de las condiciones (por ejemplo, grupos "Y", "O", condiciones anidadas). Probablemente analiza los datos de las condiciones de la base de datos y proporciona métodos para evaluar si un `ConorderdisCartState` dado cumple las condiciones definidas.
- `conorderdis/classes/ConorderdisContext.php`
  - **Responsabilidad:** Un envoltorio alrededor del objeto `Context` global de PrestaShop, que potencialmente añade datos de contexto específicos del módulo o simplifica el acceso a propiedades de contexto comunes.
- `conorderdis/classes/ConorderdisDashboard.php`
  - **Responsabilidad:** Proporciona datos y lógica para la vista del panel de control del Back Office, resumiendo estadísticas clave y proporcionando enlaces rápidos.
- `conorderdis/classes/ConorderdisEngine.php`
  - **Responsabilidad:** El motor de lógica central del módulo. Esta clase orquesta la evaluación de políticas. Toma un `ConorderdisCartState`, itera a través de los objetos `ConorderdisPolicy` activos, evalúa su `ConorderdisConditionTree` y, si se cumplen las condiciones, instruye a `ConorderdisPromoMaterializer` para que aplique el descuento.
- `conorderdis/classes/ConorderdisFreeGift.php`
  - **Responsabilidad:** Maneja específicamente la lógica para añadir productos de regalo gratuitos al carrito cuando una promoción lo dicta. Interactúa con el objeto `Cart` para asegurar que el producto se añada correctamente y se marque como gratuito.
- `conorderdis/classes/ConorderdisListRenderer.php`
  - **Responsabilidad:** Una clase de ayuda para renderizar listas en el Back Office, que potencialmente extiende `HelperList` o proporciona lógica de renderización personalizada para columnas o acciones específicas (por ejemplo, la acción de duplicar).
- `conorderdis/classes/ConorderdisLog.php`
  - **Extiende:** `ObjectModel` (probablemente un alias o una versión anterior de `ConorderdisAuditLog`).
  - **Tabla de Base de Datos:** `ps_conorderdis_log`
  - **Responsabilidad:** Similar a `ConorderdisAuditLog`, maneja el registro de eventos del módulo.
- `conorderdis/classes/ConorderdisPolicy.php`
  - **Extiende:** `ObjectModel`
  - **Tabla de Base de Datos:** `ps_conorderdis_policy`
  - **Campos `$definition`:** Almacena todos los datos relacionados con la política, incluyendo `name`, `active`, `conditions_data` (JSON/array serializado), `promotions_data` (JSON/array serializado), `priority`, `date_from`, `date_to`, `id_shop`, `id_customer_group`, `id_currency`.
  - **Responsabilidad:** Representa una única política de descuento condicional. Proporciona métodos para guardar, cargar y gestionar datos de políticas, incluyendo sus condiciones y promociones.
- `conorderdis/classes/ConorderdisPolicyDuplicator.php`
  - **Responsabilidad:** Maneja la lógica para duplicar objetos `ConorderdisPolicy`, asegurando que todos los datos asociados (condiciones, promociones) se copien correctamente.
- `conorderdis/classes/ConorderdisProductPicker.php`
  - **Responsabilidad:** Proporciona funcionalidad para seleccionar productos, categorías o fabricantes dentro del constructor de políticas del Back Office, probablemente a través de una herramienta de búsqueda basada en AJAX.
- `conorderdis/classes/ConorderdisPromoMaterializer.php`
  - **Responsabilidad:** Toma la salida del `ConorderdisEngine` (es decir, "esta promoción debe aplicarse") y la traduce en cambios reales en el carrito de PrestaShop, principalmente creando o modificando objetos `CartRule` a través de `ConorderdisCartRuleManager`.
- `conorderdis/classes/ConorderdisPromotionCalculator.php`
  - **Responsabilidad:** Calcula la cantidad exacta de descuento o identifica el producto gratuito basándose en las reglas de promoción definidas y el estado actual del carrito.
- `conorderdis/classes/ConorderdisPromotionType.php`
  - **Responsabilidad:** Define y gestiona diferentes tipos de promociones (por ejemplo, descuento porcentual, cantidad fija, regalo gratuito, artículo más barato gratis). Probablemente contiene lógica específica para cada tipo de promoción.
- `conorderdis/classes/ConorderdisRule.php`
  - **Responsabilidad:** Una clase genérica que representa una única regla o condición dentro del `ConorderdisConditionTree`.
- `conorderdis/classes/ConorderdisSchema.php`
  - **Responsabilidad:** Gestiona el esquema de la base de datos del módulo, incluyendo la instalación y desinstalación de tablas personalizadas (`ps_conorderdis_policy`, `ps_conorderdis_log`).
- `conorderdis/classes/ConorderdisUnitPool.php`
  - **Responsabilidad:** Probablemente se utiliza en escenarios complejos de "Compre N, Llévate M" o "artículo más barato gratis" para gestionar y rastrear unidades de producto individuales dentro del carrito para el cálculo de descuentos.
- `conorderdis/classes/index.php`
  - **Responsabilidad:** Práctica estándar de PrestaShop para evitar la lista de directorios.

### 4.4 Activos JavaScript (`views/js/`)

- `conorderdis/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office (utilizado en formularios de administración).
  - **Detalles:** Proporciona funcionalidad de autocompletado para campos de entrada, probablemente utilizada en el constructor de políticas para seleccionar productos, categorías o fabricantes. Se vincula a los campos de entrada, realiza llamadas AJAX a un controlador de búsqueda y muestra sugerencias.
- `conorderdis/views/js/adminConditionBuilder.js`
  - **Alcance:** Back-office (controlador AdminConorderdisPolicies).
  - **Detalles:** Impulsa la interfaz visual del constructor de condiciones. Maneja la adición/eliminación de condiciones, la agrupación de condiciones (Y/O), la selección de tipos de condiciones y la actualización dinámica de la interfaz de usuario basada en la entrada del usuario. Gestiona la estructura de datos que representa el árbol de condiciones.
- `conorderdis/views/js/adminConorderdisDashboard.js`
  - **Alcance:** Back-office (controlador AdminConorderdisDashboard).
  - **Detalles:** Proporciona elementos interactivos o contenido dinámico para el panel de control del módulo, como la obtención de estadísticas de resumen a través de AJAX o el manejo de clics en enlaces rápidos.
- `conorderdis/views/js/adminConorderdisSearchTool.js`
  - **Alcance:** Back-office (controlador AdminConorderdisPolicies).
  - **Detalles:** Una herramienta de búsqueda más general, potencialmente utilizada para la selección de productos/categorías dentro del constructor de políticas, similar a `autocomplete.js` pero posiblemente con opciones de filtrado o visualización más avanzadas.
- `conorderdis/views/js/adminConorderdisSimulator.js`
  - **Alcance:** Back-office (controlador AdminConorderdisPolicies).
  - **Detalles:** Implementa el simulador de carrito interactivo. Se vincula a los campos de entrada para añadir productos simulados, realiza llamadas AJAX a un punto final de simulación (probablemente en `AdminConorderdisPolicies`) y actualiza la interfaz de usuario con el estado del carrito simulado y los descuentos aplicados.
- `conorderdis/views/js/adminPolicyRules.js`
  - **Alcance:** Back-office (controlador AdminConorderdisPolicies).
  - **Detalles:** Gestiona la interacción y la lógica general para el formulario de creación/edición de políticas, coordinando entre el constructor de condiciones, el constructor de promociones y el simulador.
- `conorderdis/views/js/adminPromotionBuilder.js`
  - **Alcance:** Back-office (controlador AdminConorderdisPolicies).
  - **Detalles:** Impulsa la interfaz visual del constructor de promociones. Maneja la adición/eliminación de promociones, la selección de tipos de promoción (por ejemplo, porcentaje, regalo gratuito) y la actualización dinámica de la interfaz de usuario basada en el tipo de promoción elegido.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `conorderdis/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back-office (formularios de administración).
  - **Detalles:** Estiliza los desplegables de autocompletado y los resultados de búsqueda proporcionados por el script `autocomplete.js`.
- `conorderdis/views/css/admin_conorderdis.css`
  - **Alcance:** Back-office (formularios y páginas de administración).
  - **Detalles:** Contiene estilos generales para las interfaces del Back Office del módulo, incluyendo la lista de políticas, el editor de políticas (constructores de condiciones y promociones), el panel de control y el registro de auditoría. Define diseños, colores y componentes de interfaz de usuario específicos para una apariencia y sensación consistentes dentro del administrador de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)

- `conorderdis/views/templates/hook/admin_order.tpl`
  - **Hook:** `displayAdminOrder`
  - **Salida:** Esta plantilla se renderiza en el Back Office al ver un pedido. Probablemente muestra información relacionada con cualquier descuento condicional aplicado a ese pedido específico, potencialmente vinculando al registro de auditoría o mostrando qué políticas estaban activas.

#### Plantillas de Administración (`views/templates/admin/`)

- `conorderdis/lib/searchTool/views/scripts.tpl`
  - **Salida:** Contiene la inicialización o configuración de JavaScript para la herramienta de búsqueda, a menudo incluida en formularios de administración donde se utiliza la herramienta de búsqueda.
- `conorderdis/views/templates/admin/auditPreview.tpl`
  - **Salida:** Renderiza una vista previa o una vista detallada de una entrada del registro de auditoría, posiblemente dentro de un modal o una sección específica de la página `AdminconorderdisAuditLog`.
- `conorderdis/views/templates/admin/dashboard.tpl`
  - **Salida:** La plantilla principal para el controlador `AdminConorderdisDashboard`, que muestra estadísticas de resumen, enlaces rápidos y potencialmente el simulador incrustado.
- `conorderdis/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Salida:** Una plantilla personalizada para renderizar el icono y el enlace de la acción "Duplicar" dentro de una tabla `HelperList`, específicamente para políticas.
- `conorderdis/views/templates/admin/policiesPreview.tpl`
  - **Salida:** Renderiza una vista previa o una vista detallada de una política, posiblemente dentro de un modal o una sección específica de la página `AdminconorderdisPolicies`.
- `conorderdis/views/templates/admin/policyConditionBuilder.tpl`
  - **Salida:** La plantilla Smarty para la interfaz visual del constructor de condiciones dentro del editor de políticas. Define la estructura para añadir, agrupar y configurar condiciones.
- `conorderdis/views/templates/admin/policyRuleCard.tpl`
  - **Salida:** Una plantilla reutilizable para mostrar una única regla o condición dentro del constructor de condiciones, a menudo utilizada para la renderización dinámica a través de JavaScript.
- `conorderdis/views/templates/admin/policyRulesTable.tpl`
  - **Salida:** Renderiza la tabla o lista de reglas/condiciones dentro del editor de políticas.
- `conorderdis/views/templates/admin/scopeSelector.tpl`
  - **Salida:** Renderiza la interfaz para seleccionar tiendas, grupos de clientes y monedas para una política.

#### Plantillas del Front-office (`views/templates/front/`)

- `conorderdis/controllers/front/index.php` (No se enumeran archivos `.tpl` específicos para el front-office, lo que implica una renderización directa mínima en el front-end, confiando en hooks para inyectar contenido o modificar elementos existentes).

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

- `ps_conorderdis_policy`: Almacena la definición de cada política de descuento condicional.
  - `id_conorderdis_policy` (Clave Primaria)
  - `name` (Nombre de la política)
  - `active` (Booleano, 1 para activo, 0 para inactivo)
  - `conditions_data` (TEXTO, array de condiciones codificado en JSON)
  - `promotions_data` (TEXTO, array de promociones codificado en JSON)
  - `priority` (INT, número más bajo = mayor prioridad)
  - `date_from` (DATETIME)
  - `date_to` (DATETIME)
  - `id_shop` (INT, para el alcance multitienda)
  - `id_customer_group` (INT, para el alcance del grupo de clientes)
  - `id_currency` (INT, para el alcance de la moneda)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_conorderdis_log`: Almacena las entradas del registro de auditoría para las evaluaciones de políticas.
  - `id_conorderdis_log` (Clave Primaria)
  - `id_cart` (INT)
  - `id_customer` (INT)
  - `id_policy` (INT, clave externa a `ps_conorderdis_policy`)
  - `result` (VARCHAR, por ejemplo, 'applied', 'not\_met', 'error')
  - `details` (TEXTO, detalles de la evaluación codificados en JSON)
  - `date_add` (DATETIME)
- `ps_configuration`: El módulo almacena su configuración principal `CONORDERDIS_ENABLED` aquí.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Se utiliza para incluir el CSS/JS del front-office del módulo, si lo hay, o para inyectar metaetiquetas. |
| `actionFrontControllerInitAfter` | Después de que el controlador del front-office se haya inicializado. | Punto temprano para modificar el contexto, registrar servicios o prepararse para la evaluación de reglas de carrito. |
| `actionCartSave` | Después de que se haya guardado un carrito (por ejemplo, producto añadido/eliminado). | Hook principal para reevaluar las políticas de descuento condicional basadas en el contenido actualizado del carrito. |
| `actionValidateCartRule` | Antes de que se valide/aplique una regla de carrito. | Permite que el módulo intervenga o modifique el comportamiento de la regla de carrito nativa, aunque es menos probable para este módulo que crea las suyas propias. |
| `actionValidateOrderBefore` | Antes de que se valide un pedido. | Verificación final de descuentos condicionales antes de la creación del pedido, asegurando que todas las reglas se apliquen correctamente. |
| `actionValidateOrder` | Después de que un pedido se haya validado correctamente. | Se utiliza para finalizar cualquier acción específica del módulo después del pedido, como registrar la aplicación final del descuento o borrar datos temporales. |
| `actionObjectProductInCartDeleteBefore` | Antes de que se elimine un producto del carrito. | Permite que el módulo reaccione a la eliminación del producto, potencialmente ajustando descuentos o regalos gratuitos. |
| `actionObjectProductInCartDeleteAfter` | Después de que se haya eliminado un producto del carrito. | Similar a `DeleteBefore`, pero para la lógica posterior a la eliminación, potencialmente activando una reevaluación de las reglas del carrito. |
| `actionAdminControllerSetMedia` | Cuando un controlador de administración está configurando sus medios (CSS/JS). | Se utiliza para incluir los archivos CSS y JavaScript del Back Office del módulo para sus páginas de configuración y controladores personalizados. |
| `displayAdminOrder` | En la página de detalles del pedido del Back Office. | Se utiliza para mostrar información específica del módulo relacionada con los descuentos condicionales aplicados al pedido visualizado (por ejemplo, a través de `admin_order.tpl`). |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Allí encontrará sus módulos comprados y acceso a nuestros canales de soporte.

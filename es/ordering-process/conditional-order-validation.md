---
title: "Validación Condicional de Pedidos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Validación Condicional de Pedidos' de MyPresta.eu."
sidebar:
  label: "Validación Condicional de Pedidos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Conditional Order Validation en MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-order-validation.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/conditional-order-validation/)
>
> ---


# Validación Condicional de Pedidos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo de Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Validación Condicional de Pedidos)

Este es el punto de entrada principal para la configuración global del módulo.

- **Ubicación del Menú:** Back Office > Módulos > Gestor de Módulos > Validación Condicional de Pedidos > Configurar

#### 2.1.1 Configuración General

| Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- |
| **Habilitar Validación Condicional de Pedidos** | SÍ | **Qué hace este ajuste:** Este es el interruptor maestro para todo el módulo. Si está deshabilitado, ninguna de sus políticas definidas estará activa, y los clientes podrán realizar el pago sin ninguna restricción de este módulo. **Efecto de cambiar este ajuste:** *Cuando está habilitado:* El módulo comenzará a evaluar todas las políticas activas que haya creado. Si un carrito viola una política, el cliente verá advertencias o será bloqueado del pago según la configuración de su política. *Cuando está deshabilitado:* El módulo se vuelve inactivo. No se verifican políticas y no se muestran mensajes. **Valor recomendado:** SÍ (una vez que haya configurado sus políticas). **Escenario del comerciante:** Habilite esto después de haber configurado sus primeras políticas y las haya probado usando el simulador. |
| **Mostrar Mensajes de Validación En** | Carrito y Pago | **Qué hace este ajuste:** Controla dónde se muestran los mensajes de advertencia o bloqueo del módulo al cliente. **Efecto de cambiar este ajuste:** *Cuando se establece en "Carrito y Pago":* Los mensajes aparecerán tanto en la página del carrito de compras como durante los diversos pasos del proceso de pago. Esto proporciona la máxima visibilidad y retroalimentación temprana al cliente. *Cuando se establece en "Solo Carrito":* Los mensajes solo aparecerán en la página del carrito de compras. Los clientes podrían avanzar más en el pago antes de ser bloqueados si ignoran la advertencia del carrito. *Cuando se establece en "Solo Pago":* Los mensajes solo aparecerán durante el proceso de pago. Los clientes no verán advertencias en la página del carrito, lo que podría generar frustración más adelante en el proceso. **Valor recomendado:** Carrito y Pago. **Escenario del comerciante:** Para una mejor experiencia del cliente, muestre los mensajes temprano y con frecuencia (Carrito y Pago) para que los clientes puedan arreglar su carrito antes de invertir tiempo en el proceso de pago. |
| **Permitir Pago con Advertencias** | NO | **Qué hace este ajuste:** Determina si los clientes pueden proceder al pago incluso si su carrito activa una política de "advertencia" (a diferencia de una política de "bloqueo"). **Efecto de cambiar este ajuste:** *Cuando está habilitado (SÍ):* Si una política está configurada como "Advertencia", el cliente verá el mensaje de advertencia pero aún podrá hacer clic en el botón "Proceder al pago" o "Realizar pedido". Esto es útil para recomendaciones suaves o problemas no críticos. *Cuando está deshabilitado (NO):* Si una política está configurada como "Advertencia", el cliente verá el mensaje de advertencia, y el botón "Proceder al pago" o "Realizar pedido" se deshabilitará hasta que se resuelva la condición de advertencia. Esto hace que las "advertencias" se comporten como "bloqueos" en la etapa de pago. **Valor recomendado:** NO (a menos que tenga advertencias "suaves" muy específicas). **Escenario del comerciante:** Si tiene una política como "Los clientes que compran más de $100 obtienen envío gratuito", y desea *sugerir* que añadan más a su carrito pero no *forzarlos*, podría habilitar esto. Sin embargo, para la mayoría de las reglas de negocio, querrá deshabilitarlo para asegurar el cumplimiento. |

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

El módulo introduce dos nuevas y potentes secciones en el menú de su Back Office de PrestaShop: "Políticas" y "Registro de Auditoría".

#### 2.2.1 Políticas (Back Office > Validación Condicional de Pedidos > Políticas)

Aquí es donde define, gestiona y activa sus reglas de validación condicional de pedidos. Cada "política" es un conjunto de condiciones que, si se cumplen, bloquearán o advertirán al cliente.

- **Ubicación del Menú:** Back Office > Validación Condicional de Pedidos > Políticas
- **Acciones y Ajustes Disponibles:**

  - **Lista de Políticas:** Una tabla que muestra todas sus políticas creadas, indicando su nombre, estado (habilitado/deshabilitado), tipo (bloqueo/advertencia) y prioridad.
  - **Añadir Nueva Política:** Haga clic en este botón para crear una nueva política de validación.
  - **Editar Política:** Modifique el nombre, las condiciones, los mensajes y el estado de una política existente.
  - **Duplicar Política:** Cree rápidamente una copia de una política existente para usarla como punto de partida para una nueva. Esto ahorra tiempo al crear reglas similares.
  - **Habilitar/Deshabilitar Política:** Active o desactive el estado de una política sin eliminarla.
  - **Eliminar Política:** Elimine una política permanentemente.
  - **Simulador:** Una herramienta crucial (a menudo se encuentra en la pantalla de creación/edición de políticas o como una pestaña dedicada) que le permite probar sus políticas con un carrito simulado antes de que se activen. Esto ayuda a prevenir el bloqueo involuntario de pedidos legítimos.
- **Formulario de Creación/Edición de Políticas:**

  - **Nombre de la Política:** Un nombre descriptivo para su política (por ejemplo, "Valor Mínimo de Pedido para Mayoristas", "Restricción de Edad para Alcohol").
  - **Estado:** Habilite o Deshabilite la política.
  - **Tipo de Política:**
    - **Bloqueo:** Si se cumplen las condiciones, se *impide* al cliente realizar el pago.
    - **Advertencia:** Si se cumplen las condiciones, el cliente ve un mensaje de advertencia pero *puede o no* poder continuar, dependiendo de la configuración global de "Permitir Pago con Advertencias".
  - **Prioridad:** Si varias políticas están activas y se activan, esto determina el orden en que se muestran los mensajes o qué política tiene precedencia (número más bajo = mayor prioridad).
  - **Constructor de Condiciones:** Este es el núcleo de la política. Construirá un árbol de condiciones utilizando lógica "Y" / "O".
    - **Tipos de Condición:** Normalmente puede elegir entre una amplia gama de condiciones:
      - **Nivel de Carrito:** Valor total del carrito, cantidad total de artículos, número de productos únicos.
      - **Nivel de Producto:** IDs de producto específicos, categorías, fabricantes, proveedores, atributos de producto, cantidad mínima/máxima de un producto específico.
      - **Nivel de Cliente:** Grupo de clientes, ID de cliente específico, país del cliente.
      - **Nivel de Envío:** Transportista seleccionado, zona de envío.
    - **Operadores:** (por ejemplo, "es igual a", "es mayor que", "contiene", "no es").
    - **Valores:** El punto de datos específico con el que comparar (por ejemplo, "100" para un valor mínimo, "Electrónica" para una categoría).
  - **Mensaje al Cliente:** El mensaje que se muestra al cliente en el front office cuando se activa esta política. Hágalo claro, útil y accionable (por ejemplo, "Su carrito debe contener al menos 5 unidades del producto X para continuar.").
  - **Mensaje de Administración (Opcional):** Una nota interna para usted u otros administradores.
- **Efecto de los cambios:**

  - Añadir/modificar una política impacta directamente la experiencia de pago del front-office para los clientes.
  - Habilitar una política activa sus reglas. Deshabilitarla las desactiva sin eliminarlas.
  - El simulador le permite probar cambios sin afectar a los clientes en vivo.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

  1. Identifique una regla de negocio que desee aplicar (por ejemplo, "Los clientes mayoristas deben pedir un mínimo de $500").
  2. Vaya a "Políticas" y haga clic en "Añadir Nueva Política".
  3. Dele un nombre claro, configúrela como "Bloqueo" y defina las condiciones (por ejemplo, "Grupo de Clientes ES Mayorista" Y "Total del Carrito ES MAYOR O IGUAL A 500").
  4. Escriba un mensaje útil para el cliente (por ejemplo, "Los pedidos al por mayor requieren un total mínimo de $500. Por favor, añada más artículos a su carrito.").
  5. Utilice el "Simulador" para probar varios escenarios (por ejemplo, un cliente mayorista con un carrito de $400, un cliente minorista con un carrito de $400, un cliente mayorista con un carrito de $600).
  6. Una vez satisfecho, habilite la política.

#### 2.2.2 Registro de Auditoría (Back Office > Validación Condicional de Pedidos > Registro de Auditoría)

El Registro de Auditoría proporciona un historial de cuándo se activaron las políticas, por quién y cuál fue el resultado. Esto es invaluable para la resolución de problemas y la comprensión del comportamiento del cliente.

- **Ubicación del Menú:** Back Office > Validación Condicional de Pedidos > Registro de Auditoría
- **Acciones y Ajustes Disponibles:**

  - **Lista de Registros:** Una tabla que muestra las entradas cada vez que se evaluó y activó una política.
  - **Columnas:**
    - **Fecha/Hora:** Cuándo ocurrió el evento.
    - **Cliente:** El cliente que activó la política (si ha iniciado sesión).
    - **ID del Carrito:** El ID del carrito de compras involucrado.
    - **Nombre de la Política:** El nombre de la política que se activó.
    - **Tipo de Política:** Si fue una política de "Bloqueo" o "Advertencia".
    - **Mensaje:** El mensaje mostrado al cliente.
    - **Estado:** Si el pedido fue finalmente validado, bloqueado o advertido.
  - **Filtrado/Búsqueda:** El filtrado estándar de listas de PrestaShop le permite buscar por cliente, política, rango de fechas, etc.
  - **Ver Detalles del Carrito:** A menudo, puede hacer clic en un ID de carrito para inspeccionar el contenido del carrito en el momento en que se activó la política.
- **Efecto de los cambios:** Esta pantalla es solo para visualización y auditoría; no puede realizar cambios aquí. Es un registro de eventos.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

  - Si un cliente informa un problema con el pago, consulte el Registro de Auditoría para ver si se activó alguna política para su carrito. Esto puede identificar rápidamente si una política está mal configurada o si el cliente simplemente no cumplió con los requisitos.
  - Revise periódicamente el registro para comprender qué políticas se activan con mayor frecuencia y si se necesitan ajustes.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| **Configuración del Módulo** | Habilitar Validación Condicional de Pedidos | SÍ | Interruptor maestro para la funcionalidad del módulo. |
| **Configuración del Módulo** | Mostrar Mensajes de Validación En | Carrito y Pago | Dónde aparecen los mensajes al cliente (carrito, pago o ambos). |
| **Configuración del Módulo** | Permitir Pago con Advertencias | NO | Determina si las políticas de "advertencia" bloquean el pago o simplemente informan. |
| **Políticas (Admin)** | Nombre de la Política | N/A | Identificador descriptivo para su regla. |
| **Políticas (Admin)** | Estado | Habilitado | Activa o desactiva una política específica. |
| **Políticas (Admin)** | Tipo de Política | Bloqueo / Advertencia | Define si la política impide el pago o solo muestra un mensaje. |
| **Políticas (Admin)** | Prioridad | N/A | Orden de evaluación/visualización para múltiples políticas activadas. |
| **Políticas (Admin)** | Constructor de Condiciones | N/A | Define las reglas lógicas para cuando se activa la política. |
| **Políticas (Admin)** | Mensaje al Cliente | N/A | El mensaje que se muestra al cliente cuando se activa la política. |
| **Políticas (Admin)** | Mensaje de Administración | N/A | Notas internas para los administradores. |
| **Registro de Auditoría (Admin)** | (Todas las Columnas) | N/A | Registra todas las instancias de políticas activadas para su revisión. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Mis políticas no funcionan, o los clientes siguen realizando el pago cuando no deberían.**
R:

1.  **¿Está habilitado el módulo?** Verifique "Habilitar Validación Condicional de Pedidos" en la configuración principal del módulo.
2.  **¿Están habilitadas las políticas específicas?** Vaya a "Políticas" y asegúrese de que la columna "Estado" de sus políticas esté configurada en "Habilitado".
3.  **Verifique el Tipo de Política:** ¿Está configurada como "Bloqueo" o "Advertencia"? Si es "Advertencia", verifique la configuración global "Permitir Pago con Advertencias". Si está habilitada, los clientes pueden omitir las advertencias.
4.  **Borrar Caché:** A veces, la caché de PrestaShop puede impedir que los cambios surtan efecto de inmediato. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché".
5.  **Simulador:** Utilice el "Simulador" incorporado en la pantalla de creación/edición de políticas para probar sus condiciones con varios escenarios de carrito. Esta es la forma más efectiva de depurar.
6.  **Registro de Auditoría:** Verifique el "Registro de Auditoría" para ver si sus políticas se están activando en absoluto y cuál fue el resultado.

**P: Los mensajes de advertencia/bloqueo no se ven bien en mi tema.**
R: El módulo utiliza el estilo estándar de PrestaShop siempre que sea posible, pero los temas personalizados pueden anular o requerir ajustes CSS específicos.

1.  **CSS Básico:** El CSS del módulo está diseñado para ser genérico. Si su tema tiene un estilo muy específico, es posible que necesite que un webmaster añada CSS personalizado al archivo `custom.css` de su tema para que coincida con su marca.
2.  **Sobreescrituras de Plantillas:** Los usuarios avanzados pueden sobrescribir los archivos de plantilla del módulo (por ejemplo, `views/templates/hook/validation_banner.tpl`) en su tema para personalizar completamente la estructura HTML y la apariencia.

**P: ¿Puedo traducir los mensajes a diferentes idiomas?**
R: Sí, todos los mensajes orientados al cliente que defina en sus políticas son traducibles.

1.  Vaya a **Internacional > Traducciones** en su Back Office.
2.  Seleccione "Traducciones de módulos instalados", elija su tema y seleccione el idioma.
3.  Busque el módulo "Validación Condicional de Pedidos" y traduzca los mensajes de la política allí.

**P: He creado una política, pero está bloqueando *todos* los pedidos, incluso los válidos.**
R: Esto generalmente significa que sus condiciones son demasiado amplias o están configuradas incorrectamente.

1.  **Revise las Condiciones:** Vuelva a leer cuidadosamente cada condición de su política. Asegúrese de que los operadores (por ejemplo, "ES", "NO ES", "MAYOR QUE") y los valores sean correctos.
2.  **Lógica AND/OR:** Preste mucha atención a si está utilizando "Y" u "O" entre los grupos de condiciones. "Y" significa que *todas* las condiciones deben ser verdaderas; "O" significa que *cualquiera* de las condiciones debe ser verdadera. Un error común es usar "O" cuando se pretende "Y", o viceversa.
3.  **Use el Simulador:** Esto es crítico. Simule varios carritos "buenos" y "malos" para ver exactamente por qué se activa la política.

**P: ¿Cómo manejo las configuraciones de múltiples tiendas?**
R: El módulo está diseñado para ser compatible con múltiples tiendas. Al crear o editar políticas, debería ver una opción para seleccionar a qué tiendas se aplica la política. Asegúrese de que sus políticas estén asignadas a los contextos de tienda correctos.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo de Validación Condicional de Pedidos para desarrolladores y webmasters.

### 4.1 Resumen de la Arquitectura

El módulo de Validación Condicional de Pedidos sigue un patrón MVC (Modelo-Vista-Controlador) robusto dentro del framework de PrestaShop. Aprovecha en gran medida `ObjectModel` para la persistencia de datos (políticas, registros de auditoría), controladores de administración personalizados para gestionar estas entidades y un sofisticado motor de evaluación de condiciones para procesar reglas en tiempo real. El módulo se integra profundamente en los hooks de validación de pedidos y presentación del carrito, asegurando que las políticas se apliquen en etapas críticas del recorrido del cliente. Un aspecto clave es el `ConordervalidEngine` que orquesta la evaluación de los objetos `ConordervalidPolicy`, cada uno de los cuales contiene un `ConordervalidConditionTree`.

### 4.2 Controladores (`controllers/`)

#### 4.2.1 Controladores de Front-Office

- `conordervalid/controllers/front/index.php`
  - **Nombre de la Clase:** `ConordervalidIndexModuleFrontController` (probablemente extiende `ModuleFrontController`)
  - **Responsabilidad:** Este controlador podría servir como un punto de entrada general o manejar solicitudes AJAX específicas del front-office relacionadas con la validación del carrito o la visualización de mensajes. Dado su nombre, podría ser un fallback o un controlador de visualización simple.
- `conordervalid/controllers/front/validate.php`
  - **Nombre de la Clase:** `ConordervalidValidateModuleFrontController` (probablemente extiende `ModuleFrontController`)
  - **Responsabilidad:** Este controlador es crucial para la validación del carrito en tiempo real. Probablemente maneja solicitudes AJAX desde las páginas del carrito o de pago para verificar si el estado actual del carrito viola alguna política activa. Devolvería respuestas JSON indicando si el carrito es válido, cualquier mensaje de advertencia o razones de bloqueo. Aquí es donde se invocaría el `ConordervalidEngine`.

#### 4.2.2 Controladores de Administración (Back-Office)

- `conordervalid/controllers/admin/AdminconordervalidAuditLog.php`
  - **Nombre de la Clase:** `AdminconordervalidAuditLogController` (extiende `ModuleAdminController`)
  - **Nombre de la Pestaña:** Registro de Auditoría (bajo el menú de Validación Condicional de Pedidos)
  - **Entidad Gestionada:** `ConordervalidAuditLog` (mapeado a la tabla `ps_conordervalid_log`)
  - **Responsabilidad:** Gestiona la visualización y el filtrado de las entradas del registro de auditoría. Utiliza `HelperList` para renderizar la cuadrícula, permitiendo a los administradores ver registros históricos de activaciones de políticas.
- `conordervalid/controllers/admin/AdminconordervalidPolicies.php`
  - **Nombre de la Clase:** `AdminconordervalidPoliciesController` (extiende `ModuleAdminController`)
  - **Nombre de la Pestaña:** Políticas (bajo el menú de Validación Condicional de Pedidos)
  - **Entidad Gestionada:** `ConordervalidPolicy` (mapeado a la tabla `ps_conordervalid_policy`)
  - **Responsabilidad:** Este es el controlador principal para gestionar las políticas de validación. Maneja las operaciones CRUD para las políticas, incluida la compleja interfaz del constructor de condiciones. Utiliza `HelperList` para la descripción general de las políticas y `HelperForm` para la creación/edición de políticas, integrando la lógica de `ConordervalidConditionTree` y `ConordervalidConditionBuilder`.
- `conordervalid/controllers/admin/index.php`
  - **Nombre de la Clase:** (Probablemente una simple redirección o marcador de posición)
  - **Responsabilidad:** A menudo, `index.php` en un directorio de controlador es una medida de seguridad para evitar la lista directa de directorios o una simple redirección a la configuración principal del módulo o al panel de control.

### 4.3 Clases y Modelos Principales (`classes/`)

- `conordervalid/classes/ConordervalidAdmin.php`
  - **Responsabilidad:** Probablemente contiene métodos de ayuda o utilidades específicamente para la interfaz de administración, como el registro de menús, la gestión de pestañas o la lógica común de renderizado de formularios.
- `conordervalid/classes/ConordervalidAuditLog.php`
  - **Extiende:** `ObjectModel`
  - **Tabla de Base de Datos:** `ps_conordervalid_log`
  - **Campos `$definition`:** `id_conordervalid_log`, `id_cart`, `id_customer`, `id_policy`, `policy_name`, `policy_type`, `message`, `date_add`.
  - **Responsabilidad:** Representa una única entrada en el registro de auditoría, almacenando detalles sobre una política activada.
- `conordervalid/classes/ConordervalidCartState.php`
  - **Responsabilidad:** Una clase de utilidad para encapsular el estado actual del carrito de un cliente (productos, cantidades, total, información del cliente, transportista seleccionado, etc.). Este objeto se pasa al `ConordervalidConditionEvaluator`.
- `conordervalid/classes/ConordervalidCompatibility.php`
  - **Responsabilidad:** Maneja las capas de compatibilidad para diferentes versiones de PrestaShop (por ejemplo, diferencias en los nombres de los hooks, estructuras de clases o llamadas a la API entre PS 1.7, 8.x y 9.x).
- `conordervalid/classes/ConordervalidCondition.php`
  - **Extiende:** (Probablemente una clase base o `ObjectModel` si las condiciones se almacenan individualmente)
  - **Responsabilidad:** Representa una única condición dentro de una política (por ejemplo, "Total del Carrito > 100"). Define el tipo de condición, el operador y el valor.
- `conordervalid/classes/ConordervalidConditionEvaluator.php`
  - **Responsabilidad:** La lógica central para evaluar un `ConordervalidCondition` o `ConordervalidConditionGroup` contra un objeto `ConordervalidCartState`. Contiene métodos para comparar diferentes tipos de datos y aplicar operadores.
- `conordervalid/classes/ConordervalidConditionGroup.php`
  - **Extiende:** (Probablemente una clase base)
  - **Responsabilidad:** Representa una agrupación lógica de condiciones (por ejemplo, "Condición A Y (Condición B O Condición C)"). Gestiona la lógica `AND`/`OR`.
- `conordervalid/classes/ConordervalidConditionTree.php`
  - **Extiende:** (Probablemente una clase base o `ObjectModel`)
  - **Responsabilidad:** Representa toda la estructura jerárquica de condiciones para una política. Es una estructura de datos tipo árbol compuesta por objetos `ConordervalidConditionGroup` y `ConordervalidCondition`.
- `conordervalid/classes/ConordervalidContext.php`
  - **Responsabilidad:** Un envoltorio o extensión de la clase `Context` de PrestaShop, que potencialmente añade datos de contexto específicos del módulo o métodos de ayuda.
- `conordervalid/classes/ConordervalidDashboard.php`
  - **Responsabilidad:** Probablemente proporciona datos y lógica para un posible panel de control del módulo en el Back Office, resumiendo el rendimiento de las políticas o las estadísticas del registro de auditoría.
- `conordervalid/classes/ConordervalidEngine.php`
  - **Responsabilidad:** El orquestador central. Obtiene los objetos `ConordervalidPolicy` activos, los itera y utiliza `ConordervalidConditionEvaluator` para verificar si un carrito dado viola alguna política. Determina el resultado final (bloqueado, advertido, válido) y recopila mensajes.
- `conordervalid/classes/ConordervalidListRenderer.php`
  - **Responsabilidad:** Una clase de utilidad para renderizar listas o tablas en el Back Office, personalizando potencialmente el comportamiento de `HelperList` o proporcionando un formato de columna específico.
- `conordervalid/classes/ConordervalidLog.php`
  - **Extiende:** `ObjectModel` (probablemente un alias o una versión anterior de `ConordervalidAuditLog`)
  - **Tabla de Base de Datos:** `ps_conordervalid_log`
  - **Campos `$definition`:** Similar a `ConordervalidAuditLog`.
  - **Responsabilidad:** Almacena entradas del registro de auditoría.
- `conordervalid/classes/ConordervalidPolicy.php`
  - **Extiende:** `ObjectModel`
  - **Tabla de Base de Datos:** `ps_conordervalid_policy`
  - **Campos `$definition`:** `id_conordervalid_policy`, `name`, `active`, `type` (bloqueo/advertencia), `priority`, `conditions_json` (almacena el `ConordervalidConditionTree` como JSON), `customer_message`, `admin_message`, `date_add`, `date_upd`.
  - **Responsabilidad:** Representa una única política de validación, incluyendo sus condiciones, mensajes y configuraciones.
- `conordervalid/classes/ConordervalidPolicyDuplicator.php`
  - **Responsabilidad:** Maneja la lógica para duplicar objetos `ConordervalidPolicy`, asegurando que todas las condiciones y configuraciones asociadas se copien correctamente.
- `conordervalid/classes/ConordervalidPreset.php`
  - **Responsabilidad:** Probablemente define conjuntos predefinidos de condiciones o plantillas de políticas que los administradores pueden cargar rápidamente.
- `conordervalid/classes/ConordervalidRule.php`
  - **Extiende:** (Probablemente una clase base o `ObjectModel`)
  - **Responsabilidad:** Podría ser un alias para `ConordervalidCondition` o una abstracción de nivel superior para una sola regla dentro de una política.
- `conordervalid/classes/ConordervalidTreeRepository.php`
  - **Responsabilidad:** Gestiona el almacenamiento y la recuperación de objetos `ConordervalidConditionTree`, probablemente serializándolos/deserializándolos hacia/desde el campo `conditions_json` en `ConordervalidPolicy`.
- `conordervalid/classes/index.php`
  - **Responsabilidad:** Medida de seguridad estándar para evitar la lista de directorios.

### 4.4 Activos JavaScript (`views/js/`)

- `conordervalid/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office (formularios de administración)
  - **Responsabilidad:** Proporciona funcionalidad de autocompletado para campos de entrada en la administración, probablemente utilizada al seleccionar productos, categorías, clientes, etc., dentro del constructor de condiciones.
- `conordervalid/lib/searchTool/views/views/js/autocomplete.js`
  - **Alcance:** Back-office (formularios de administración)
  - **Responsabilidad:** Duplicado del anterior, probablemente un error en el empaquetado o una ruta heredada.
- `conordervalid/views/js/adminConditionBuilder.js`
  - **Alcance:** Back-office (`AdminconordervalidPoliciesController`)
  - **Responsabilidad:** Impulsa la interfaz interactiva de construcción de condiciones en el formulario de creación/edición de políticas. Maneja la adición/eliminación de condiciones, la gestión de la lógica AND/OR y la actualización de la estructura JSON subyacente del árbol de condiciones.
- `conordervalid/views/js/adminConordervalidDashboard.js`
  - **Alcance:** Back-office (Panel de administración, si está implementado)
  - **Responsabilidad:** Proporciona funcionalidad dinámica para un posible panel de control del módulo, como la representación de gráficos, el filtrado de datos o las actualizaciones AJAX.
- `conordervalid/views/js/adminConordervalidSearchTool.js`
  - **Alcance:** Back-office (formularios de administración)
  - **Responsabilidad:** Integra la herramienta de búsqueda (por ejemplo, para productos, categorías) en varios formularios de administración, probablemente utilizada por el constructor de condiciones.
- `conordervalid/views/js/adminConordervalidSimulator.js`
  - **Alcance:** Back-office (`AdminconordervalidPoliciesController`)
  - **Responsabilidad:** Maneja la lógica para el simulador de políticas. Captura datos de carrito simulados, los envía a través de AJAX a un controlador frontal (por ejemplo, `validate.php`) y muestra los resultados de la validación.
- `conordervalid/views/js/adminPolicyRules.js`
  - **Alcance:** Back-office (`AdminconordervalidPoliciesController`)
  - **Responsabilidad:** Contiene lógica JS específica para gestionar la visualización e interacción de las reglas de política dentro de la interfaz de administración, potencialmente relacionada con el reordenamiento de arrastrar y soltar o ediciones rápidas.
- `conordervalid/views/js/validation.js`
  - **Alcance:** Front-office (páginas de Carrito, Pago)
  - **Responsabilidad:** Este es el JS principal del front-office. Escucha los cambios del carrito (por ejemplo, actualización de cantidad, eliminación de producto), activa llamadas AJAX al controlador frontal `validate.php` y luego actualiza dinámicamente la interfaz de usuario para mostrar mensajes de advertencia/bloqueo o habilitar/deshabilitar botones de pago según la respuesta. Probablemente utiliza `prestashop.on` para la vinculación de eventos.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `conordervalid/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back-office (formularios de administración)
  - **Componentes principales de la interfaz de usuario:** Estilos para los desplegables de autocompletado y los campos de entrada utilizados en la herramienta de búsqueda de administración.
  - **Selectores clave:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`.
- `conordervalid/lib/searchTool/views/views/css/autocomplete.css`
  - **Alcance:** Back-office (formularios de administración)
  - **Componentes principales de la interfaz de usuario:** Duplicado del anterior.
  - **Selectores clave:** Igual que el anterior.
- `conordervalid/views/css/admin_conordervalid.css`
  - **Alcance:** Back-office (formularios y listas de administración)
  - **Componentes principales de la interfaz de usuario:** Estilos para la lista de políticas, el formulario de creación/edición de políticas, el constructor de condiciones y el registro de auditoría.
  - **Selectores clave:** `.conordervalid-policy-card`, `.conordervalid-condition-group`, `.conordervalid-condition-row`, `.conordervalid-simulator-results`.
- `conordervalid/views/css/front.css`
  - **Alcance:** Front-office (páginas de Carrito, Pago)
  - **Componentes principales de la interfaz de usuario:** Estilos para los banners y mensajes de advertencia/bloqueo mostrados a los clientes.
  - **Selectores clave:** `.conordervalid-validation-banner`, `.conordervalid-warning`, `.conordervalid-blocking`, `.conordervalid-message-list`.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### 4.6.1 Plantillas de Hook (`views/templates/hook/`)

- `conordervalid/views/templates/hook/admin_order.tpl`
  - **Hook:** `DisplayAdminOrder`
  - **Salidas:** Un bloque dentro de la vista de pedidos del Back Office, que potencialmente muestra qué políticas se activaron para un pedido o carrito específico.
- `conordervalid/views/templates/hook/validation_banner.tpl`
  - **Hook:** `DisplayPaymentTop`, `DisplayShoppingCartFooter`, `DisplayCheckoutSummaryTop`
  - **Salidas:** La estructura HTML para los mensajes de advertencia/bloqueo del front-office mostrados al cliente. Esta plantilla recibe variables como `$validation_messages`, `$is_blocked`, etc.

#### 4.6.2 Plantillas de Administración (`views/templates/admin/`)

- `conordervalid/lib/searchTool/views/scripts.tpl`
  - **Salidas:** Plantilla Smarty para incluir activos JS/CSS relacionados con la herramienta de búsqueda en la administración.
- `conordervalid/lib/searchTool/views/views/scripts.tpl`
  - **Salidas:** Duplicado del anterior.
- `conordervalid/views/templates/admin/auditPreview.tpl`
  - **Salidas:** Una plantilla parcial para mostrar una vista previa o resumen de las entradas del registro de auditoría, posiblemente utilizada dentro de un panel de control o una vista específica.
- `conordervalid/views/templates/admin/dashboard.tpl`
  - **Salidas:** La plantilla principal para un posible panel de control del módulo en el Back Office, mostrando estadísticas, registros recientes o resúmenes de políticas.
- `conordervalid/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Salidas:** Botón de acción personalizado para duplicar políticas dentro de la vista `HelperList` para `AdminconordervalidPoliciesController`.
- `conordervalid/views/templates/admin/policiesPreview.tpl`
  - **Salidas:** Una plantilla parcial para mostrar una vista previa o resumen de políticas, similar a `auditPreview.tpl`.
- `conordervalid/views/templates/admin/policyConditionBuilder.tpl`
  - **Salidas:** La compleja estructura HTML para la interfaz interactiva del constructor de condiciones utilizada al crear o editar una política. Esta plantilla funciona en estrecha colaboración con `adminConditionBuilder.js`.
- `conordervalid/views/templates/admin/policyRuleCard.tpl`
  - **Salidas:** Una plantilla más pequeña y reutilizable para mostrar una sola regla o condición dentro del constructor de condiciones.
- `conordervalid/views/templates/admin/policyRulesTable.tpl`
  - **Salidas:** Una estructura tipo tabla para mostrar una lista de reglas, posiblemente utilizada en la descripción general de la política o el simulador.
- `conordervalid/views/templates/admin/scopeSelector.tpl`
  - **Salidas:** Plantilla para seleccionar el alcance de una política (por ejemplo, tiendas específicas en un entorno multi-tienda).

#### 4.6.3 Plantillas de Front-office (`views/templates/front/`)

- (No se identificaron plantillas de front-office independientes dedicadas, ya que la visualización del front-office se maneja a través de plantillas de hook como `validation_banner.tpl`.)

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### 4.7.1 Tablas de Base de Datos

- `ps_conordervalid_policy`
  - **Propósito:** Almacena la definición de cada política de validación.
  - **Campos Clave:** `id_conordervalid_policy` (PK), `name`, `active` (booleano), `type` (enum: 'blocking', 'warning'), `priority`, `conditions_json` (TEXT, almacena `ConordervalidConditionTree` serializado), `customer_message` (TEXT), `admin_message` (TEXT), `date_add`, `date_upd`.
- `ps_conordervalid_log`
  - **Propósito:** Almacena entradas de la pista de auditoría para políticas activadas.
  - **Campos Clave:** `id_conordervalid_log` (PK), `id_cart`, `id_customer`, `id_policy`, `policy_name`, `policy_type`, `message`, `date_add`.
- `ps_configuration`
  - **Propósito:** Almacena la configuración global del módulo.
  - **Campos Clave:** `CONORDERVALID_DISPLAY_SURFACES` (por ejemplo, 'cart,checkout'), `CONORDERVALID_ENABLED` (booleano), `CONORDERVALID_ALLOW_WARN_CHECKOUT` (booleano).

#### 4.7.2 Tabla de Hooks Registrados

| Nombre del Hook | Momento y Contexto de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `DisplayHeader` | Se renderiza en la sección `<head>` de todas las páginas del front-office. | Inyecta activos CSS (`front.css`) y JS (`validation.js`) del front-office. |
| `ActionFrontControllerInitAfter` | Después de que un controlador frontal ha sido inicializado. | Potencialmente utilizado para inicializar el contexto del módulo, cargar políticas o realizar verificaciones de validación tempranas. |
| `ActionObjectProductInCartDeleteBefore` | Antes de que un producto sea eliminado del carrito. | Podría usarse para registrar el estado del carrito antes de un cambio, o para evitar la eliminación si viola una política. |
| `ActionObjectProductInCartDeleteAfter` | Después de que un producto ha sido eliminado del carrito. | Reevalúa las políticas del carrito después de la eliminación de un producto, activa la actualización AJAX. |
| `ActionCartSave` | Después de que un carrito ha sido guardado (por ejemplo, actualización de cantidad, adición/eliminación de producto). | Activa la reevaluación de todas las políticas activas contra el carrito actualizado. |
| `actionPresentCart` | Cuando el carrito se está preparando para su visualización (por ejemplo, en la página del carrito). | Inyecta mensajes de validación en la plantilla de la página del carrito. |
| `DisplayShoppingCartFooter` | En la parte inferior de la página del carrito de compras. | Renderiza el `validation_banner.tpl` con cualquier mensaje de advertencia/bloqueo. |
| `DisplayPaymentTop` | En la parte superior de la sección de selección de pago durante el pago. | Renderiza el `validation_banner.tpl` con cualquier mensaje de advertencia/bloqueo, potencialmente deshabilitando las opciones de pago. |
| `DisplayCheckoutSummaryTop` | En la parte superior de la página de resumen de pago (antes de la confirmación final del pedido). | Renderiza el `validation_banner.tpl` con cualquier mensaje de advertencia/bloqueo, potencialmente deshabilitando el botón de confirmación del pedido. |
| `ActionFilterPaymentOptions` | Filtra las opciones de pago disponibles durante el pago. | Puede usarse para ocultar o deshabilitar métodos de pago si se viola una política (por ejemplo, "COD no permitido para pedidos superiores a $X"). |
| `ActionValidateOrderBefore` | Justo antes de que un pedido sea validado oficialmente. | La verificación crítica final para bloquear un pedido si se viola alguna política de bloqueo. Registra el intento. |
| `ActionValidateOrder` | Después de que un pedido ha sido validado y creado con éxito. | Registra la validación exitosa del pedido, potencialmente registra qué políticas *no* fueron violadas. |
| `DisplayAdminOrder` | Renderiza un bloque dentro de la página de detalles del pedido del Back Office. | Muestra información sobre las políticas que se activaron (o pasaron) para el pedido específico, utilizando `admin_order.tpl`. |
| `ActionAdminControllerSetMedia` | Cuando un controlador de administración está configurando sus medios (JS/CSS). | Inyecta JS (`adminConditionBuilder.js`, `adminConordervalidSimulator.js`) y CSS (`admin_conordervalid.css`) específicos del Back Office para la gestión de políticas. |
| `DisplayReassurance` | A menudo utilizado para mostrar elementos de confianza (por ejemplo, iconos de pago seguro). | Podría usarse potencialmente para mostrar una pequeña advertencia o estado persistente si un carrito no es válido. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo de Validación Condicional de Pedidos, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y configuración del módulo.

---
title: "Reglas de Métodos de Pago Condicionales - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Reglas de Métodos de Pago Condicionales' de MyPresta.eu."
sidebar:
  label: "Reglas de Métodos de Pago Condicionales - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Conditional Payment Method Rules en MyPresta.eu](https://mypresta.eu/modules/payment-process/conditional-payment-method-rules.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/conditional-payment-method-rules/)
>
> ---


# Reglas de Métodos de Pago Condicionales

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo de Configuración (Cada Ajuste Agrupado por Pantalla)

La configuración del módulo se gestiona principalmente a través de pantallas de administración dedicadas, lo que te permite crear y gestionar tus políticas de métodos de pago.

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Este es el punto de entrada principal para el módulo. Después de la instalación, al hacer clic en "Configurar" te llevará a un panel de control o a una página de configuración general.

#### Configuración General y Panel de Control

Esta pantalla proporciona una visión general del estado de tu módulo y acceso rápido a las funciones clave.

-   **Qué hace esta pantalla:** Muestra un resumen de tus políticas activas, entradas recientes del registro de auditoría y enlaces rápidos para gestionar políticas o ver el registro de auditoría. Es tu centro neurálgico para monitorear la actividad del módulo.
-   **Efecto de cambiar la configuración:** Esta pantalla proporciona principalmente información y navegación. Cualquier cambio que realices aquí (por ejemplo, habilitar/deshabilitar una política) impactará directamente en cómo se muestran los métodos de pago en el proceso de compra.
-   **Valor recomendado:** Mantén un ojo en el panel de control para detectar cualquier conflicto de políticas o comportamiento inesperado.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

El módulo introduce varios elementos de menú nuevos bajo la sección "Pago" en tu Back Office de PrestaShop.

#### 2.2.1 Políticas de Métodos de Pago (Back Office > Pago > Reglas de Métodos de Pago > Políticas)

Aquí es donde defines y gestionas todas tus reglas para mostrar u ocultar métodos de pago.

-   **Nombre de la Pantalla y Ubicación del Menú:** **Pago > Reglas de Métodos de Pago > Políticas**
-   **Acciones y Configuraciones Disponibles:**

    -   **Lista de Políticas:** Una tabla que muestra todas tus políticas creadas, su estado (habilitado/deshabilitado) y los métodos de pago a los que afectan.
    -   **Añadir Nueva Política:** Haz clic en este botón para crear una nueva regla.
    -   **Editar/Eliminar Política:** Gestiona políticas individuales desde la lista.
    -   **Duplicar Política:** Crea rápidamente una copia de una política existente para modificarla.
    -   **Habilitar/Deshabilitar Política:** Alterna el estado activo de una política sin eliminarla.
    -   **Importar/Exportar Políticas (JSON):** Haz una copia de seguridad de tus políticas o transfiérelas entre tiendas.
-   **Crear/Editar una Política:**
    Cuando añades o editas una política, configurarás varios aspectos clave:

    1.  **Nombre de la Política:**

        -   **Qué hace esta configuración:** Un nombre descriptivo para tu política (por ejemplo, "Ocultar Pago Contra Reembolso para pedidos internacionales").
        -   **Efecto de cambiar esta configuración:** Te ayuda a identificar la política en la lista.
        -   **Valor recomendado:** Hazlo claro y conciso.
        -   **Escenario del comerciante:** Nombrar una política "Envío Gratuito Solo con PayPal" te indica inmediatamente su propósito.
    2.  **Estado (Habilitado/Deshabilitado):**

        -   **Qué hace esta configuración:** Controla si la política está activa y se aplica en el proceso de compra.
        -   **Efecto de cambiar esta configuración:**
            -   *Cuando está habilitada:* Las reglas dentro de esta política se evaluarán y afectarán la visibilidad del método de pago.
            -   *Cuando está deshabilitada:* La política se ignora y sus reglas no tienen efecto.
        -   **Valor recomendado:** Habilita las políticas solo cuando estés seguro de que están configuradas correctamente.
        -   **Escenario del comerciante:** Podrías deshabilitar una política temporalmente durante una promoción o si estás solucionando un problema.
    3.  **Métodos de Pago Afectados:**

        -   **Qué hace esta configuración:** Selecciona qué métodos de pago específicos controlará esta política.
        -   **Efecto de cambiar esta configuración:** Solo los métodos de pago seleccionados estarán sujetos a las reglas de esta política.
        -   **Valor recomendado:** Selecciona todos los métodos de pago relevantes para esta política.
        -   **Escenario del comerciante:** Si quieres ocultar "Pago Contra Reembolso" y "Transferencia Bancaria" bajo ciertas condiciones, seleccionarías ambos aquí.
    4.  **Tipo de Política (Mostrar/Ocultar):**

        -   **Qué hace esta configuración:** Determina si las condiciones de la política *mostrarán* los métodos de pago seleccionados u *ocultarán* los métodos de pago seleccionados.
        -   **Efecto de cambiar esta configuración:**
            -   *Cuando se establece en "Mostrar":* Los métodos de pago seleccionados *solo* serán visibles si se cumplen TODAS las condiciones de esta política. Si las condiciones no se cumplen, se ocultan.
            -   *Cuando se establece en "Ocultar":* Los métodos de pago seleccionados se ocultarán si se cumplen TODAS las condiciones de esta política. Si las condiciones no se cumplen, son visibles.
        -   **Valor recomendado:** Elige según tu objetivo principal. "Ocultar" suele ser más fácil para restricciones específicas, mientras que "Mostrar" es bueno para ofertas exclusivas.
        -   **Escenario del comerciante:**
            -   *Ocultar:* "Ocultar Pago Contra Reembolso si el total del carrito supera los 500 €."
            -   *Mostrar:* "Mostrar 'Plan de Cuotas' SOLO si el grupo de clientes es 'VIP' Y el total del carrito supera los 1000 €."
    5.  **Constructor de Condiciones:**

        -   **Qué hace esta configuración:** Este es el núcleo de tu política. Construyes reglas complejas usando lógica "Y" y "O" basada en varios criterios.
        -   **Efecto de cambiar esta configuración:** Las condiciones que defines aquí determinan *cuándo* se activa la acción "Mostrar" u "Ocultar" de la política.
        -   **Condiciones Disponibles (Ejemplos):**
            -   **Total del Carrito:** Basado en el valor total del carrito del cliente.
            -   **Grupo de Clientes:** Basado en el grupo al que pertenece el cliente (por ejemplo, Invitado, Cliente, VIP, Mayorista).
            -   **País:** Basado en el país de envío o facturación del cliente.
            -   **Transportista:** Basado en el transportista de envío seleccionado.
            -   **Productos en el Carrito:** Basado en productos, categorías, fabricantes o proveedores específicos en el carrito.
            -   **Moneda:** Basado en la moneda utilizada para el pedido.
            -   **Peso:** Basado en el peso total del carrito.
            -   **Fecha/Hora:** Basado en fechas u horas específicas (por ejemplo, para promociones).
            -   **Tienda:** Para configuraciones multi-tienda.
        -   **Valor recomendado:** Empieza con condiciones simples y prueba a fondo. Usa "Y" para requisitos más estrictos y "O" para una aplicabilidad más amplia.
        -   **Escenario del comerciante:**
            -   "Ocultar PayPal si (País ES 'EE. UU.' Y Total del Carrito ES MENOR QUE 10 €) O (Grupo de Clientes ES 'Mayorista')."
            -   "Mostrar Transferencia Bancaria si (Grupo de Clientes ES 'B2B') Y (Total del Carrito ES MAYOR QUE 1000 €)."
    6.  **Mensaje de No Disponibilidad:**

        -   **Qué hace esta configuración:** Un mensaje personalizado que se muestra al cliente si un método de pago es ocultado por esta política.
        -   **Efecto de cambiar esta configuración:** Proporciona una comunicación clara al cliente sobre por qué una opción de pago no está disponible, evitando confusiones.
        -   **Valor recomendado:** Mantenlo educado e informativo (por ejemplo, "El pago contra reembolso no está disponible para pedidos superiores a 500 €. Por favor, elija otro método de pago.").
        -   **Escenario del comerciante:** "Este método de pago solo está disponible para clientes VIP." o "Por favor, seleccione un método de envío diferente para usar esta opción de pago."
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

    1.  **Identifica una necesidad:** "Quiero dejar de ofrecer Pago Contra Reembolso para pedidos superiores a 200 €."
    2.  **Crea una nueva política:** Nómbrala "Límite Pago Contra Reembolso 200 €".
    3.  **Selecciona "Ocultar"** como tipo de política.
    4.  **Selecciona "Pago Contra Reembolso"** como método de pago afectado.
    5.  **Añade una condición:** "Total del Carrito ES MAYOR QUE 200 €".
    6.  **Añade un mensaje de no disponibilidad:** "El pago contra reembolso no está disponible para pedidos que superen los 200 €. Por favor, elija otro método de pago."
    7.  **Habilita y Guarda.**
    8.  **Prueba usando el Simulador** (ver siguiente sección).

#### 2.2.2 Registro de Auditoría (Back Office > Pago > Reglas de Métodos de Pago > Registro de Auditoría)

Esta pantalla proporciona un historial detallado de cómo se han aplicado tus reglas de pago.

-   **Nombre de la Pantalla y Ubicación del Menú:** **Pago > Reglas de Métodos de Pago > Registro de Auditoría**
-   **Acciones y Configuraciones Disponibles:**
    -   **Lista de Registros:** Una tabla que muestra cada instancia en la que la visibilidad de un método de pago fue afectada por una política.
    -   **Detalles:** Consulta información específica sobre cada entrada del registro, incluyendo el cliente, detalles del carrito, políticas evaluadas y el resultado final (qué métodos de pago se mostraron/ocultaron).
    -   **Filtrado:** Filtra las entradas del registro por fecha, cliente, política o método de pago para encontrar rápidamente eventos específicos.
-   **Efecto de los cambios:** Esta pantalla es para visualización y auditoría. No puedes realizar cambios aquí, pero es invaluable para entender por qué ciertos métodos de pago se mostraron o no a un cliente.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revisa regularmente el registro de auditoría si recibes consultas de clientes sobre métodos de pago faltantes o si sospechas que una política no está funcionando como se esperaba. Es tu herramienta de depuración.

#### 2.2.3 Simulador (Back Office > Pago > Reglas de Métodos de Pago > Simulador)

El simulador es una herramienta poderosa para probar tus políticas sin realizar un pedido real.

-   **Nombre de la Pantalla y Ubicación del Menú:** **Pago > Reglas de Métodos de Pago > Simulador**
-   **Acciones y Configuraciones Disponibles:**
    -   **Campos de Entrada:** Introduce varios criterios como grupo de clientes, país, transportista, total del carrito e incluso añade productos específicos a un carrito simulado.
    -   **Botón Simular:** Haz clic para ver qué métodos de pago estarían disponibles basándose en los criterios introducidos y las políticas activas.
    -   **Visualización de Resultados:** Muestra una lista de métodos de pago disponibles y no disponibles, junto con las razones (qué políticas hicieron que se ocultaran/mostraran).
-   **Efecto de los cambios:** Esta pantalla te permite experimentar con diferentes escenarios y ver inmediatamente el impacto de tus políticas. No afecta a tu tienda en vivo.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** *Siempre* usa el simulador después de crear o modificar una política. Prueba casos extremos y escenarios comunes para asegurarte de que tus reglas funcionan exactamente como se pretende antes de que se activen.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Políticas (Añadir/Editar)** | Nombre de la Política | Nombre Descriptivo | Identificación interna de la regla. |
| | Estado | Habilitado | Activa/desactiva la política. |
| | Métodos de Pago Afectados | Seleccionar métodos relevantes | Especifica qué pasarelas de pago controla esta política. |
| | Tipo de Política | Ocultar | Determina si las condiciones *ocultan* o *muestran* los métodos seleccionados. |
| | Constructor de Condiciones | Varía según la regla | Define los criterios (por ejemplo, total del carrito, grupo de clientes) para que la política se aplique. |
| | Mensaje de No Disponibilidad | Texto claro e informativo | Mensaje que se muestra a los clientes cuando un método de pago está oculto. |
| **Registro de Auditoría** | Entradas del Registro | N/A | Proporciona un registro histórico de las evaluaciones de políticas. |
| | Filtros | N/A | Ayuda a buscar y analizar eventos de registro específicos. |
| **Simulador** | Entradas de Simulación | N/A | Permite probar políticas con varios escenarios de cliente/carrito. |
| | Resultados de Simulación | N/A | Muestra qué métodos de pago estarían disponibles/no disponibles para el escenario simulado. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Un método de pago no aparece, pero no tengo ninguna política configurada para ocultarlo. ¿Qué pasa?**
R: Primero, revisa el **Registro de Auditoría** del módulo para ver si hay entradas relacionadas con ese método de pago y cliente. El registro te dirá si una política *lo ocultó*. Si no, el problema podría estar fuera de este módulo:
\* ¿Está el método de pago habilitado en **Pago > Métodos de Pago**?
\* ¿Hay alguna restricción establecida directamente en el módulo de pago (por ejemplo, restricciones de país, moneda, grupo dentro de la propia configuración del módulo de pago)?
\* Borra la caché de tu PrestaShop (**Parámetros Avanzados > Rendimiento**).

**P: Mis políticas no parecen funcionar. ¿Qué debo hacer?**
R:
1.  **Verifica el Estado de la Política:** Asegúrate de que la política esté "Habilitada" en la pantalla de **Políticas**.
2.  **Usa el Simulador:** Ve a **Pago > Reglas de Métodos de Pago > Simulador** e introduce las condiciones exactas que estás probando. Mira lo que predice el simulador. Esta es la forma más rápida de depurar tus condiciones.
3.  **Revisa las Condiciones:** Vuelve a verificar tu lógica "Y" y "O". Una sola condición incorrecta puede evitar que toda la política se active.
4.  **Verifica los Métodos de Pago Afectados:** Asegúrate de que el método de pago que esperas que se vea afectado esté realmente seleccionado en la política.
5.  **Borra la Caché:** Siempre borra la caché de tu PrestaShop (**Parámetros Avanzados > Rendimiento**) después de realizar cambios significativos en la configuración del módulo o las políticas.

**P: ¿Cómo gestiono múltiples políticas que afectan al mismo método de pago?**
R: El módulo evalúa todas las políticas activas.
\* Si varias políticas de "Ocultar" se aplican al mismo método de pago, y *cualquiera* de ellas se activa, el método de pago se ocultará.
\* Si varias políticas de "Mostrar" se aplican al mismo método de pago, y *cualquiera* de ellas se activa, el método de pago se mostrará.
\* **Resolución de Conflictos:** Si una política dice "Mostrar" y otra dice "Ocultar" para el mismo método de pago bajo las mismas condiciones, el módulo tiene una estrategia de fusión definida (típicamente, "Ocultar" tiene precedencia para garantizar la seguridad y evitar la disponibilidad no intencionada). Usa el **Simulador** y el **Registro de Auditoría** para comprender el resultado exacto de las políticas en conflicto.

**P: ¿Puedo traducir el "Mensaje de No Disponibilidad" para diferentes idiomas?**
R: Sí, al editar una política, el campo "Mensaje de No Disponibilidad" normalmente tendrá un selector de idioma (un icono de bandera) junto a él. Haz clic en la bandera para introducir traducciones para cada idioma habilitado en tu tienda.

**P: Mi tema personalizado no muestra los mensajes de no disponibilidad correctamente. ¿Qué puedo hacer?**
R: Esto suele indicar un conflicto de CSS o una anulación de plantilla faltante en tu tema.
\* **Verifica `front.css`:** El módulo incluye su propio `front.css` para el estilo básico. Tu tema podría estar anulándolo.
\* **Inspeccionar Elemento:** Usa las herramientas de desarrollador de tu navegador (F12) para inspeccionar el área donde debería aparecer el mensaje. Busca reglas CSS que puedan estar ocultándolo o posicionándolo incorrectamente.
\* **Contacta al Desarrollador del Tema:** Si no te sientes cómodo con CSS, contacta al desarrollador de tu tema o a un experto en PrestaShop para obtener ayuda. Ellos pueden ayudarte a integrar el estilo del módulo con tu tema.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo de Reglas de Métodos de Pago Condicionales sigue un diseño robusto y orientado a objetos dentro del framework MVC de PrestaShop. Utiliza en gran medida `ObjectModel` para gestionar políticas y registros de auditoría, una estructura `ConditionTree` dedicada para la evaluación de reglas complejas y un `PaymethodrulesEngine` para aplicar estas reglas en la etapa de pago. El módulo inyecta su lógica principalmente a través de hooks, específicamente `actionPaymentOptionsModifier` (o similar para versiones anteriores de PS) para manipular la lista de métodos de pago disponibles. Los controladores de administración proporcionan una rica interfaz de usuario para la gestión de políticas, simulación y auditoría.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

-   `controllers/front/index.php`
    -   **Nombre de la Clase:** `PaymethodrulesIndexModuleFrontController` (o similar, típicamente extendiendo `ModuleFrontController`)
    -   **Responsabilidad:** Este controlador podría servir como un fallback o un simple punto de entrada, pero la lógica central para la modificación de métodos de pago generalmente se maneja a través de hooks. Podría usarse para solicitudes AJAX específicas relacionadas con la evaluación de reglas en el front-office si fuera necesario, aunque la evaluación principal ocurre durante la renderización de las opciones de pago.
-   `controllers/front/simulate.php`
    -   **Nombre de la Clase:** `PaymethodrulesSimulateModuleFrontController` (o similar, extendiendo `ModuleFrontController`)
    -   **Responsabilidad:** Aunque el simulador principal está en el BO, un controlador de front podría existir para una simulación simplificada en el front-end o para exponer los resultados de la simulación a través de AJAX con fines de depuración.

#### Controladores de Administración (Back-Office)

-   `controllers/admin/AdminPaymethodrulesAuditLog.php`
    -   **Nombre de la Clase:** `AdminPaymethodrulesAuditLogController` (extiende `ModuleAdminController`)
    -   **Nombre de la Pestaña:** Reglas de Métodos de Pago -> Registro de Auditoría
    -   **Entidad Gestionada:** `PaymethodrulesAuditLog` (mapeada a la tabla `ps_paymethodrules_log`)
    -   **Responsabilidad:** Gestiona la visualización y el filtrado de las entradas del registro de auditoría. Utiliza `HelperList` para renderizar la vista de cuadrícula y proporciona acciones para ver los detalles del registro.
-   `controllers/admin/AdminPaymethodrulesPolicies.php`
    -   **Nombre de la Clase:** `AdminPaymethodrulesPoliciesController` (extiende `ModuleAdminController`)
    -   **Nombre de la Pestaña:** Reglas de Métodos de Pago -> Políticas
    -   **Entidad Gestionada:** `PaymethodrulesPolicy` (mapeada a la tabla `ps_paymethodrules_policy`)
    -   **Responsabilidad:** Este es el controlador central para gestionar las políticas de pago. Maneja:
        -   Listado de políticas usando `HelperList`.
        -   Añadir/editar políticas usando `HelperForm` con renderizado de campos complejos para el constructor de condiciones.
        -   Habilitar/deshabilitar, duplicar y eliminar políticas.
        -   Manejo de importación/exportación de políticas en JSON.
-   `controllers/admin/index.php`
    -   **Nombre de la Clase:** `AdminPaymethodrulesDashboardController` (o similar, extiende `ModuleAdminController`)
    -   **Nombre de la Pestaña:** Reglas de Métodos de Pago -> Panel de Control (o enlace principal de configuración del módulo)
    -   **Entidad Gestionada:** N/A (vista de panel de control)
    -   **Responsabilidad:** Proporciona el punto de entrada principal y la vista de panel de control para el módulo en el Back Office. Agrega información de otros controladores (por ejemplo, recuentos de políticas, entradas de registro recientes) y proporciona navegación. Típicamente utiliza plantillas Smarty para renderizar los widgets del panel de control.

### 4.3 Clases y Modelos Principales (`classes/`)

-   `classes/index.php`: Archivo vacío estándar para evitar la lista de directorios.
-   `classes/PaymethodrulesAdmin.php`: Probablemente una clase auxiliar para funciones comunes relacionadas con la administración, como el registro de menús, la gestión de pestañas o la lógica de renderizado de formularios compartida.
-   `classes/PaymethodrulesAuditLog.php`
    -   **Extiende:** `ObjectModel`
    -   **Tabla de Base de Datos:** `ps_paymethodrules_log`
    -   **Campos `$definition`:** `id_paymethodrules_log`, `id_cart`, `id_customer`, `id_shop`, `context_data` (JSON), `policies_applied` (JSON), `payment_methods_before` (JSON), `payment_methods_after` (JSON), `date_add`.
    -   **Métodos Públicos Clave:** Métodos para registrar eventos, recuperar entradas de registro y posiblemente limpiar registros antiguos.
-   `classes/PaymethodrulesCompatibility.php`: Maneja capas de compatibilidad para diferentes versiones de PrestaShop (por ejemplo, diferencias en nombres de hooks, estructuras de objetos o funciones `Tools`).
-   `classes/PaymethodrulesCondition.php`
    -   **Extiende:** `ObjectModel` (o una clase base para condiciones)
    -   **Tabla de Base de Datos:** `ps_paymethodrules_condition` (si las condiciones se almacenan individualmente)
    -   **Campos `$definition`:** `id_paymethodrules_condition`, `id_paymethodrules_policy`, `type`, `operator`, `value`, `id_parent_group`.
    -   **Métodos Públicos Clave:** Métodos para definir tipos de condición, operadores y valores. Parte de la estructura del árbol de condiciones.
-   `classes/PaymethodrulesConditionEvaluator.php`: Contiene la lógica central para evaluar una única `PaymethodrulesCondition` contra un contexto dado (carrito, cliente, etc.).
-   `classes/PaymethodrulesConditionGroup.php`
    -   **Extiende:** `ObjectModel` (o una clase base para grupos de condiciones)
    -   **Tabla de Base de Datos:** `ps_paymethodrules_condition_group` (si los grupos se almacenan individualmente)
    -   **Campos `$definition`:** `id_paymethodrules_condition_group`, `id_paymethodrules_policy`, `operator` (`AND`/`OR`), `id_parent_group`.
    -   **Métodos Públicos Clave:** Gestiona una colección de condiciones o grupos de condiciones anidados, aplicando la lógica `AND`/`OR`.
-   `classes/PaymethodrulesConditionTree.php`: Representa toda la estructura jerárquica de condiciones y grupos de condiciones para una política. Proporciona métodos para construir, recorrer y evaluar el árbol.
-   `classes/PaymethodrulesContext.php`: Una clase de utilidad que encapsula todos los datos relevantes necesarios para la evaluación de reglas (carrito actual, cliente, dirección, transportista, moneda, etc.). Actúa como proveedor de datos para el `PaymethodrulesEngine`.
-   `classes/PaymethodrulesDashboard.php`: Clase auxiliar para obtener datos y preparar estadísticas/resúmenes para la vista del panel de control del módulo.
-   `classes/PaymethodrulesEngine.php`: La clase central responsable de orquestar la evaluación de reglas.
    -   **Métodos Públicos Clave:** `evaluatePolicies(PaymethodrulesContext $context, array $payment_options)`: Toma el contexto actual y una lista de opciones de pago disponibles, aplica todas las políticas activas y devuelve la lista modificada. Utiliza `PaymethodrulesConditionTree` y `PaymethodrulesConditionEvaluator`.
-   `classes/PaymethodrulesListRenderer.php`: Un ayudante especializado para renderizar listas en el Back Office, que potencialmente extiende `HelperList` o proporciona renderizado de columnas personalizado.
-   `classes/PaymethodrulesLog.php`: Alias o implementación específica para `PaymethodrulesAuditLog`.
-   `classes/PaymethodrulesPolicy.php`
    -   **Extiende:** `ObjectModel`
    -   **Tabla de Base de Datos:** `ps_paymethodrules_policy`
    -   **Campos `$definition`:** `id_paymethodrules_policy`, `name`, `active`, `policy_type` (`show`/`hide`), `payment_methods` (array JSON de nombres de módulos), `unavailable_message` (multilingüe), `conditions_tree` (representación JSON del árbol de condiciones), `date_add`, `date_upd`.
    -   **Métodos Públicos Clave:** Métodos para guardar/cargar datos de políticas, recuperar condiciones asociadas y proporcionar lógica específica de políticas.
-   `classes/PaymethodrulesPolicyDuplicator.php`: Clase de utilidad específicamente para duplicar objetos `PaymethodrulesPolicy`, asegurando que todas las condiciones y grupos asociados también se copien correctamente.
-   `classes/PaymethodrulesPreset.php`: Probablemente maneja conjuntos predefinidos de condiciones o políticas que el comerciante puede cargar rápidamente.
-   `classes/PaymethodrulesRule.php`: Podría ser un nombre más antiguo o alternativo para `PaymethodrulesCondition` o `PaymethodrulesPolicy`, o una clase base para componentes de reglas.
-   `classes/PaymethodrulesTreeRepository.php`: Gestiona la persistencia y recuperación de la estructura `PaymethodrulesConditionTree`, probablemente convirtiéndola a/desde JSON para su almacenamiento en el objeto `PaymethodrulesPolicy`.

### 4.4 Activos JavaScript (`views/js/`)

-   `paymethodrules/lib/searchTool/views/js/autocomplete.js`: Funcionalidad genérica de autocompletado, probablemente utilizada para seleccionar productos, categorías u otras entidades dentro del constructor de condiciones.
-   `paymethodrules/lib/searchTool/views/views/js/autocomplete.js`: Versión duplicada o específica del script de autocompletado.
-   `paymethodrules/views/js/adminConditionBuilder.js`:
    -   **Alcance:** Back-office (pantalla de creación/edición de políticas).
    -   **Funcionalidad:** Maneja la creación, modificación y eliminación dinámica de condiciones y grupos de condiciones dentro del formulario de política. Gestiona la lógica "Y"/"O", añade nuevas filas de condición, maneja los cambios de tipo de condición (por ejemplo, mostrando diferentes campos de entrada para "Total del Carrito" vs. "Producto").
-   `paymethodrules/views/js/adminPaymethodrulesDashboard.js`:
    -   **Alcance:** Back-office (pantalla del panel de control).
    -   **Funcionalidad:** Podría manejar llamadas AJAX para widgets del panel de control, actualizar datos o proporcionar elementos interactivos en el panel de control.
-   `paymethodrules/views/js/adminPaymethodrulesSearchTool.js`:
    -   **Alcance:** Back-office (constructor de condiciones).
    -   **Funcionalidad:** Integra la biblioteca `autocomplete.js` para buscar y seleccionar entidades (productos, categorías, clientes, transportistas) al construir condiciones.
-   `paymethodrules/views/js/adminPaymethodrulesSimulator.js`:
    -   **Alcance:** Back-office (pantalla del simulador).
    -   **Funcionalidad:** Captura la entrada del usuario para los criterios de simulación, envía solicitudes AJAX al controlador del simulador y actualiza dinámicamente la visualización con la disponibilidad simulada del método de pago.
-   `paymethodrules/views/js/adminPolicyRules.js`:
    -   **Alcance:** Back-office (lista de políticas y pantallas de edición).
    -   **Funcionalidad:** JS general para la gestión de políticas, como el manejo de los interruptores de habilitar/deshabilitar, acciones de duplicación y potencialmente la lógica de envío de formularios para los detalles de la política.
-   `paymethodrules/views/js/checkout.js`:
    -   **Alcance:** Front-office (página de pago).
    -   **Funcionalidad:** Esto es crucial. Escucha los cambios en el proceso de pago (por ejemplo, selección del método de envío, cambio de dirección, actualización del carrito) y podría activar llamadas AJAX para reevaluar la disponibilidad del método de pago o actualizar dinámicamente la visualización de los mensajes de no disponibilidad. Asegura que las opciones de pago estén siempre actualizadas.
-   `paymethodrules/views/js/unavailableUi.js`:
    -   **Alcance:** Front-office (página de pago).
    -   **Funcionalidad:** Gestiona la visualización y el estilo del "mensaje de no disponibilidad" para los métodos de pago ocultos. Podría inyectar dinámicamente el mensaje, aplicar clases CSS o manejar animaciones.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `paymethodrules/lib/searchTool/views/css/autocomplete.css`: Estilos para la herramienta de búsqueda de autocompletado en el Back Office.
-   `paymethodrules/lib/searchTool/views/views/css/autocomplete.css`: Versión duplicada o específica del CSS de autocompletado.
-   `paymethodrules/views/css/admin_paymethodrules.css`:
    -   **Alcance:** Back-office (todas las pantallas de administración del módulo).
    -   **Funcionalidad:** Proporciona estilos para la lista de políticas, el constructor de condiciones, el panel de control, el simulador y el registro de auditoría. Incluye estilos para elementos de formulario, tablas y componentes de UI personalizados específicos del módulo.
    -   **Selectores de clase CSS clave:** `.paymethodrules-policy-card`, `.condition-group`, `.condition-row`, `.paymethodrules-dashboard-widget`.
-   `paymethodrules/views/css/front.css`:
    -   **Alcance:** Front-office (página de pago).
    -   **Funcionalidad:** Proporciona estilos básicos para los mensajes de métodos de pago no disponibles o cualquier indicación visual relacionada con las opciones de pago ocultas en la página de pago.
    -   **Selectores de clase CSS clave:** `.paymethodrules-unavailable-message`, `.paymethodrules-hidden-payment`.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)

-   `paymethodrules/views/templates/hook/payment_top.tpl`:
    -   **Hook:** `displayPaymentTop` (o similar, dependiendo de la versión de PS)
    -   **Bloque Visual:** Esta plantilla podría usarse para mostrar un mensaje general o información relacionada con las reglas de pago en la parte superior de la sección de selección de pago. Sin embargo, la interacción principal suele ser la modificación directa del array de opciones de pago. También podría usarse para inyectar los scripts `checkout.js` y `unavailableUi.js`.

#### Plantillas de Administración (`views/templates/admin/`)

-   `paymethodrules/lib/searchTool/views/scripts.tpl`: Incluye JS/CSS para la herramienta de búsqueda en el administrador.
-   `paymethodrules/lib/searchTool/views/views/scripts.tpl`: Versión duplicada o específica de los scripts de la herramienta de búsqueda.
-   `paymethodrules/views/templates/admin/auditPreview.tpl`: Renderiza la vista detallada de una única entrada del registro de auditoría, mostrando el contexto, las políticas aplicadas y los cambios en los métodos de pago.
-   `paymethodrules/views/templates/admin/dashboard.tpl`: Renderiza el panel de control principal del módulo, incluyendo widgets para el resumen de políticas, registros recientes y enlaces rápidos.
-   `paymethodrules/views/templates/admin/helpers/list/list_action_duplicate.tpl`: Plantilla personalizada para el botón de acción "duplicar" en el `HelperList` para políticas.
-   `paymethodrules/views/templates/admin/policiesPreview.tpl`: Podría usarse para una vista previa rápida de las reglas de una política sin entrar en el formulario de edición completo, o para mostrar detalles de la política en el registro de auditoría.
-   `paymethodrules/views/templates/admin/policyConditionBuilder.tpl`: La plantilla principal para renderizar la interfaz dinámica del constructor de condiciones dentro del formulario de añadir/editar política. Incluye parciales para condiciones y grupos individuales.
-   `paymethodrules/views/templates/admin/policyRuleCard.tpl`: Renderiza una única política como una tarjeta o una fila en una lista, potencialmente utilizada en el panel de control o en una vista de política simplificada.
-   `paymethodrules/views/templates/admin/policyRulesTable.tpl`: Renderiza la tabla principal de políticas en la pantalla `AdminPaymethodrulesPolicies`.
-   `paymethodrules/views/templates/admin/scopeSelector.tpl`: Una plantilla reutilizable para seleccionar el alcance (por ejemplo, tienda, idioma) dentro de los formularios de administración.

#### Plantillas de Front-office (`views/templates/front/`)

-   No se enumeran plantillas de página de front-office dedicadas, lo que indica que el módulo se integra principalmente en las plantillas de pago existentes modificando datos, en lugar de renderizar páginas completamente nuevas.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

-   `ps_paymethodrules_policy`: Almacena las definiciones principales de las políticas, incluyendo nombre, estado, métodos de pago afectados, tipo de política, mensajes de no disponibilidad (multilingües) y la representación JSON del árbol de condiciones.
-   `ps_paymethodrules_log`: Almacena las entradas del registro de auditoría, incluyendo `id_cart`, `id_customer`, `context_data`, `policies_applied`, `payment_methods_before`, `payment_methods_after` y `date_add`.
-   (Potencialmente) `ps_paymethodrules_condition` y `ps_paymethodrules_condition_group` si el árbol de condiciones se almacena de forma normalizada en lugar de completamente como JSON dentro de `ps_paymethodrules_policy`. El archivo `install.sql` lo confirmará.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionPaymentOptionsModifier` | Durante el proceso de pago, antes de que se muestren los métodos de pago. | **Hook principal:** El `PaymethodrulesEngine` del módulo se invoca aquí para filtrar y modificar el array de opciones de pago disponibles basándose en las políticas activas y el contexto actual del carrito. |
| `displayBackOfficeHeader` | En cada carga de página del Back Office. | Inyecta CSS y JS específicos del módulo para los controladores de administración (por ejemplo, `admin_paymethodrules.css`, `adminConditionBuilder.js`). |
| `displayHeader` | En cada carga de página del front-office. | Inyecta CSS y JS específicos del módulo para el front-office (por ejemplo, `front.css`, `checkout.js`, `unavailableUi.js`), particularmente en la página de pago. |
| `moduleRoutes` | Durante la compilación de rutas de PrestaShop. | Registra rutas personalizadas de front-office y back-office para los controladores del módulo (por ejemplo, `/module/paymethodrules/simulate`). |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración. | Inyecta CSS y JS específicos del módulo para el controlador de administración actual, asegurando que los activos se carguen solo cuando sea necesario. |
| `actionObject*AddAfter` / `actionObject*UpdateAfter` | Después de que se añade o actualiza un objeto (por ejemplo, `Cart`, `Customer`). | Potencialmente utilizado para borrar cachés internas o activar una reevaluación si el módulo mantiene datos en caché. |
| `displayAdminProductsExtra` (o similar) | En la página de edición de productos en el BO. | Podría usarse para añadir condiciones específicas del producto directamente en la página del producto, aunque no se menciona explícitamente en la lista de archivos. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Reglas de Métodos de Pago Condicionales", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.
"""

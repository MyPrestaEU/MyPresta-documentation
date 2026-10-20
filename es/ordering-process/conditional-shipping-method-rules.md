---
title: "Reglas de Métodos de Envío Condicionales - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Reglas de Métodos de Envío Condicionales de MyPresta.eu."
sidebar:
  label: "Reglas de Métodos de Envío Condicionales"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Conditional Shipping Method Rules en MyPresta.eu](https://mypresta.eu/modules/ordering-process/conditional-shipping-method-rules.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/conditional-shipping-method-rules/)
>
> ---


# Reglas de Métodos de Envío Condicionales

## 1. Requisitos y Compatibilidad

-   **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilidad PHP**: PHP 7.1 - 8.5
-   **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento modernos de PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)
Puedes acceder a esta pantalla navegando a **Módulos > Gestor de Módulos**, buscando "Reglas de Métodos de Envío Condicionales" y haciendo clic en "Configurar".

Esta página proporciona ajustes generales para el comportamiento del módulo.

-   **Activar Módulo:**
    -   **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar toda la funcionalidad del módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Todas tus reglas de envío definidas estarán activas e influirán en los métodos de envío mostrados en el proceso de compra.
        -   *Cuando está desactivado:* El módulo estará inactivo y se aplicará la selección de método de envío predeterminada de PrestaShop, ignorando todas tus reglas personalizadas.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo de comerciante:** Podrías desactivarlo temporalmente durante el mantenimiento o si necesitas volver rápidamente al comportamiento de envío predeterminado. Para un funcionamiento normal, mantenlo activado.

-   **Estrategia de Fusión para Múltiples Reglas:**
    -   **Qué hace este ajuste:** Determina cómo el módulo combina los resultados de múltiples reglas activas cuando se aplican al mismo método de envío.
    -   **Efecto de cambiar este ajuste:**
        -   *Opción A (Priorizar "MOSTRAR"):* Si *alguna* regla activa dice "MOSTRAR" un transportista, se mostrará, incluso si otras reglas dicen "OCULTARLO". Esta es una estrategia más permisiva.
        -   *Opción B (Priorizar "OCULTAR"):* Si *alguna* regla activa dice "OCULTAR" un transportista, se ocultará, incluso si otras reglas dicen "MOSTRARLO". Esta es una estrategia más restrictiva.
        -   *Opción C (Estrategia de Fusión Personalizada 1):* [Explicación detallada de la lógica específica, por ejemplo, "Solo mostrar si TODAS las reglas aplicables dicen MOSTRAR"]
        -   *Opción D (Estrategia de Fusión Personalizada 2):* [Explicación detallada de la lógica específica]
        -   *Opción E (Estrategia de Fusión Personalizada 3):* [Explicación detallada de la lógica específica]
    -   **Valor recomendado:** Priorizar "OCULTAR" (por seguridad, asegurando que no se muestren transportistas no deseados). Sin embargo, esto depende en gran medida de tu configuración de reglas específica.
    -   **Escenario / ejemplo de comerciante:** Si tienes una regla para "MOSTRAR" envío gratuito para pedidos superiores a 100 €, pero otra regla para "OCULTAR" envío gratuito para un producto específico, la estrategia de fusión determina qué regla prevalece. "Priorizar OCULTAR" ocultaría el envío gratuito para ese producto, incluso si el pedido supera los 100 €.

-   **Mostrar Mensajes de Método de Envío No Disponible:**
    -   **Qué hace este ajuste:** Controla si los clientes ven una explicación cuando un método de envío está oculto por una regla.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Si un transportista está oculto, se mostrará un mensaje (que tú defines por regla) al cliente, explicando por qué no está disponible.
        -   *Cuando está desactivado:* Los transportistas ocultos simplemente desaparecerán de la lista sin ninguna explicación.
    -   **Valor recomendado:** SÍ (Mejora la experiencia del cliente y reduce la confusión).
    -   **Escenario / ejemplo de comerciante:** Si el "Envío Exprés" está oculto porque el carrito del cliente contiene un "Artículo Frágil" que no se puede enviar por exprés, al activar esto se mostrará un mensaje como "El envío exprés no está disponible para artículos frágiles".

-   **Retención del Registro de Auditoría (Días):**
    -   **Qué hace este ajuste:** Define cuánto tiempo el módulo mantiene registros de las evaluaciones de reglas y sus resultados en el registro de auditoría.
    -   **Efecto de cambiar este ajuste:**
        -   *Establecer un número (por ejemplo, 30):* El módulo eliminará automáticamente las entradas de registro más antiguas que este número de días.
        -   *Establecer en 0 o vacío:* El módulo mantendrá todas las entradas de registro indefinidamente (puede llevar a una base de datos grande con el tiempo).
    -   **Valor recomendado:** 30-90 días (suficiente para la resolución de problemas sin un crecimiento excesivo de la base de datos).
    -   **Escenario / ejemplo de comerciante:** Si un cliente se queja de no ver un método de envío específico, puedes consultar el registro de auditoría para ver las evaluaciones recientes. Mantener los registros durante 30 días te permite investigar problemas recientes sin almacenar años de datos.

-   **Activar Simulador de Pago:**
    -   **Qué hace este ajuste:** Activa una herramienta en el back office que te permite probar tus reglas de envío simulando diferentes escenarios de clientes y carritos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* La pestaña "Simulador de Pago" aparecerá en la configuración del módulo, proporcionando un potente entorno de prueba.
        -   *Cuando está desactivado:* El simulador no estará disponible.
    -   **Valor recomendado:** SÍ (Esencial para probar reglas complejas antes de la implementación).
    -   **Escenario / ejemplo de comerciante:** Antes de lanzar una nueva promoción de envío, puedes usar el simulador para asegurarte de que tus reglas muestren/oculten correctamente el envío promocional para varios valores de carrito, grupos de clientes y direcciones.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 Políticas de Envío (Back Office > Módulos > Reglas de Métodos de Envío Condicionales > Políticas de Envío)
Esta es la pantalla principal donde defines y gestionas todas tus reglas de envío.

-   **Nombre de la Pantalla y Ubicación del Menú:** **Reglas de Métodos de Envío Condicionales > Políticas de Envío** (se encuentra en la sección "Módulos" del menú de tu back office de PrestaShop).
-   **Acciones y Ajustes Disponibles:**
    -   **Lista de Políticas:** Una tabla que muestra todas tus políticas de envío creadas. Cada política tiene un nombre, estado (activada/desactivada) y acciones.
    -   **Añadir Nueva Política:** Un botón para crear una nueva política de envío.
    -   **Editar Política:** Haz clic en una política existente para modificar sus reglas, condiciones y ajustes.
    -   **Duplicar Política:** Crea rápidamente una copia de una política existente, útil para hacer pequeñas variaciones.
    -   **Activar/Desactivar Política:** Alterna el estado activo de una política sin eliminarla.
    -   **Eliminar Política:** Elimina una política permanentemente.
    -   **Formulario de Configuración de Política (al añadir/editar):**
        -   **Nombre de la Política:** Un nombre descriptivo para tu conjunto de reglas (por ejemplo, "Envío Gratuito a partir de 100 €", "Restricciones de Envío Exprés").
        -   **Estado:** Activa o desactiva esta política específica.
        -   **Prioridad:** Si se aplican varias políticas, esto determina el orden en que se evalúan. Los números más bajos significan mayor prioridad.
        -   **Transportistas Objetivo:** Selecciona qué transportistas de envío específicos afectará esta política.
        -   **Acción (MOSTRAR/OCULTAR):** Elige si esta política *mostrará* los transportistas seleccionados si se cumplen las condiciones, u *ocultará* los mismos.
        -   **Mensaje de No Disponible:** Si elegiste "OCULTAR" y "Mostrar Mensajes de Método de Envío No Disponible" está activado en la configuración principal, este es el mensaje que verán los clientes (multilingüe).
        -   **Constructor de Condiciones:** Aquí es donde defines la parte "SI" de tu regla. Puedes añadir múltiples grupos de condiciones (lógica Y/O) basados en:
            -   Total del carrito, peso, cantidad
            -   Productos o categorías específicas en el carrito
            -   Grupo de clientes, país, estado, código postal
            -   Fecha y hora
            -   Y muchos más criterios.
-   **Efecto de los cambios:**
    -   Añadir, editar o eliminar políticas impacta directamente en qué métodos de envío se presentan a los clientes en el proceso de compra, según las condiciones definidas.
    -   Cambiar el estado de una política (activar/desactivar) activa o desactiva inmediatamente su efecto en el front office.
    -   Ajustar la prioridad puede resolver conflictos si varias políticas se aplican al mismo transportista.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  **Planifica tu regla:** Antes de crear, define claramente lo que quieres lograr (por ejemplo, "Si el total del carrito > 50 € Y el cliente está en España, ENTONCES MOSTRAR 'Envío Estándar'").
    2.  **Crea una nueva política:** Dale un nombre claro.
    3.  **Selecciona Transportistas Objetivo:** Elige los transportistas que afectará esta política.
    4.  **Establece la Acción:** Decide si la política debe MOSTRAR u OCULTAR estos transportistas.
    5.  **Construye las Condiciones:** Usa el constructor de condiciones intuitivo para configurar tus declaraciones "SI". Usa "Añadir Grupo de Condiciones" para la lógica O y "Añadir Condición" dentro de un grupo para la lógica Y.
    6.  **Prueba con el Simulador:** Fundamentalmente, usa el "Simulador de Pago" (ver la siguiente sección) para verificar que tus reglas funcionan como se espera para varios escenarios.
    7.  **Activa:** Una vez probado, activa la política.

#### 2.2.2 Registro de Auditoría (Back Office > Módulos > Reglas de Métodos de Envío Condicionales > Registro de Auditoría)
Esta pantalla proporciona un registro histórico de cómo se han evaluado tus reglas de envío.

-   **Nombre de la Pantalla y Ubicación del Menú:** **Reglas de Métodos de Envío Condicionales > Registro de Auditoría** (se encuentra en la sección "Módulos" del menú de tu back office de PrestaShop).
-   **Acciones y Ajustes Disponibles:**
    -   **Tabla de Registro:** Una lista detallada de cada vez que el módulo evaluó las reglas de envío para el carrito de un cliente.
    -   **Columnas:** Incluye información como:
        -   Fecha y Hora de la evaluación
        -   ID de Cliente (si ha iniciado sesión)
        -   ID de Carrito
        -   Políticas Aplicadas: Qué políticas se consideraron.
        -   Resultado: Qué transportistas se mostraron/ocultaron y por qué.
        -   Instantánea del Pedido: Un enlace para ver el estado exacto del carrito en el momento de la evaluación.
    -   **Filtrado y Ordenación:** Funciones estándar de lista de PrestaShop para filtrar por fecha, cliente o ID de carrito.
-   **Efecto de los cambios:** Esta es una pantalla de solo lectura para monitoreo y resolución de problemas. No puedes realizar cambios directos aquí, pero los datos te ayudan a comprender cómo funcionan tus reglas.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    -   Usa este registro para diagnosticar problemas reportados por los clientes (por ejemplo, "No vi el envío gratuito"). Puedes encontrar su ID de carrito o ID de cliente y ver exactamente qué reglas se aplicaron y cuál fue el resultado.
    -   Revisa periódicamente el registro para asegurarte de que las reglas se están ejecutando como se espera, especialmente después de realizar cambios en las políticas.

#### 2.2.3 Simulador de Pago (Back Office > Módulos > Reglas de Métodos de Envío Condicionales > Simulador de Pago)
Esta potente herramienta te permite probar tus reglas de envío sin realizar un pedido real.

-   **Nombre de la Pantalla y Ubicación del Menú:** **Reglas de Métodos de Envío Condicionales > Simulador de Pago** (se encuentra en la sección "Módulos" del menú de tu back office de PrestaShop, solo visible si "Activar Simulador de Pago" está activo en la configuración principal).
-   **Acciones y Ajustes Disponibles:**
    -   **Selección de Cliente:** Elige un cliente existente de tu tienda o simula un invitado.
    -   **Selección de Dirección:** Selecciona una dirección específica para el cliente elegido o introduce manualmente los detalles de la dirección.
    -   **Contenido del Carrito:** Añade productos, cantidades y combinaciones específicas para simular el carrito de un cliente.
    -   **Botón Simular:** Haz clic para ejecutar la simulación.
    -   **Visualización de Resultados:** Muestra qué métodos de envío estarían disponibles (y cuáles estarían ocultos con sus mensajes) para el escenario simulado. También detalla qué políticas se aplicaron y por qué.
-   **Efecto de los cambios:** Esta pantalla no cambia ningún dato de la tienda en vivo. Es puramente un entorno de prueba.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    -   **Antes de activar nuevas políticas:** Pruébalas siempre a fondo aquí.
    -   **Resolución de problemas:** Recrea un problema reportado por un cliente simulando su carrito y dirección exactos para ver por qué se mostró o no un transportista.
    -   **Escenarios complejos:** Prueba casos límite, como valores mínimos/máximos de pedido, combinaciones de productos específicas o diferentes grupos de clientes.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| **Configuración del Módulo** | Activar Módulo | SÍ | Interruptor principal para la funcionalidad del módulo. |
| | Estrategia de Fusión para Múltiples Reglas | Priorizar "OCULTAR" | Cómo se resuelven las reglas en conflicto (MOSTRAR vs. OCULTAR). |
| | Mostrar Mensajes de Método de Envío No Disponible | SÍ | Muestra explicaciones para los transportistas ocultos a los clientes. |
| | Retención del Registro de Auditoría (Días) | 30-90 | Cuánto tiempo se mantienen los registros de evaluación de reglas. |
| | Activar Simulador de Pago | SÍ | Activa la herramienta de prueba en el back office. |
| **Políticas de Envío** | Nombre de la Política | Nombre Descriptivo | Identifica el conjunto de reglas. |
| | Estado | Activado | Activa/desactiva esta política específica. |
| | Prioridad | Número más bajo = mayor prioridad | Determina el orden de evaluación para políticas en conflicto. |
| | Transportistas Objetivo | Transportistas Específicos | Qué métodos de envío afecta esta política. |
| | Acción (MOSTRAR/OCULTAR) | MOSTRAR/OCULTAR | Si mostrar u ocultar los transportistas objetivo si se cumplen las condiciones. |
| | Mensaje de No Disponible | Texto Personalizado (multilingüe) | Mensaje mostrado cuando el transportista está oculto (si está activado). |
| | Constructor de Condiciones | Varía | Define los criterios "SI" para que se aplique la política. |
| **Registro de Auditoría** | (Todas las columnas) | N/A (Solo lectura) | Proporciona registros históricos de evaluaciones de reglas para la resolución de problemas. |
| **Simulador de Pago** | (Todos los campos) | N/A (Herramienta de prueba) | Permite simular escenarios de cliente/carrito para probar reglas. |

## 3. Resolución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mis reglas no funcionan, o estoy viendo opciones de envío inesperadas. ¿Qué debo hacer?**
R1:
1.  **Verifica el Estado del Módulo:** Asegúrate de que la configuración "Activar Módulo" en la página de configuración principal esté establecida en SÍ.
2.  **Verifica el Estado de la Política:** Ve a "Políticas de Envío" y verifica que las políticas específicas que esperas que estén activas estén habilitadas.
3.  **Borra la Caché:** Ve a **Parámetros Avanzados > Rendimiento** y haz clic en "Borrar caché". A veces, PrestaShop almacena en caché configuraciones antiguas.
4.  **Usa el Simulador de Pago:** ¡Este es tu mejor amigo! Recrea el escenario exacto (cliente, dirección, contenido del carrito) en el simulador. Te mostrará exactamente qué reglas se aplicaron y por qué, ayudándote a identificar el problema.
5.  **Revisa el Registro de Auditoría:** Si un cliente informó un problema, verifica el "Registro de Auditoría" para su ID de carrito/cliente para ver cómo se evaluaron las reglas para su pedido específico.
6.  **Estrategia de Fusión:** Revisa tu configuración de "Estrategia de Fusión para Múltiples Reglas". Si tienes reglas de MOSTRAR y OCULTAR en conflicto, esta configuración determina el resultado.

**P2: ¿Por qué no aparece mi "Mensaje de No Disponible" personalizado?**
R2:
1.  **Activa la Visualización de Mensajes:** En la página de configuración principal del módulo, asegúrate de que "Mostrar Mensajes de Método de Envío No Disponible" esté establecido en SÍ.
2.  **Acción de la Política:** Verifica que la "Acción" de la política esté establecida en "OCULTAR" para el transportista objetivo. Los mensajes solo se muestran cuando un transportista está oculto.
3.  **Contenido del Mensaje:** Asegúrate de haber introducido realmente un mensaje en el campo "Mensaje de No Disponible" para la política específica, y de que esté traducido para los idiomas relevantes.

**P3: El módulo está ralentizando mi proceso de pago. ¿Es esto normal?**
R3: El módulo está altamente optimizado, pero las reglas muy complejas (por ejemplo, cientos de condiciones, muchas políticas) pueden añadir una ligera sobrecarga.
1.  **Simplifica las Reglas:** Revisa tus políticas. ¿Se pueden combinar o simplificar algunas?
2.  **Prioriza:** Asegúrate de que tus reglas más frecuentemente activadas tengan una prioridad más alta (número más bajo) para que se evalúen primero.
3.  **Tamaño de la Base de Datos:** Verifica tu configuración de "Retención del Registro de Auditoría". Si está configurado para mantener los registros indefinidamente, una tabla de registro muy grande puede afectar el rendimiento. Establécelo en un número razonable de días (por ejemplo, 30-90).

**P4: ¿Cómo me aseguro de que mi tema personalizado muestre las opciones de envío correctamente?**
R4: El módulo se integra con el proceso de pago estándar de PrestaShop.
1.  **Hooks Estándar:** El módulo utiliza hooks estándar de PrestaShop. Si tu tema personaliza en gran medida el proceso de pago, asegúrate de que siga llamando correctamente a `displayCarrierList` o hooks similares donde se renderizan las opciones de envío.
2.  **Conflictos de CSS:** Si la visualización parece incorrecta (por ejemplo, los mensajes están desalineados), podría haber un conflicto de CSS con tu tema. Usa las herramientas de desarrollo de tu navegador (F12) para inspeccionar los elementos e identificar las reglas CSS en conflicto. Es posible que necesites añadir CSS personalizado a tu tema para anular los estilos del módulo o del tema.
3.  **Contacta con Soporte:** Si estás utilizando un tema altamente personalizado y encuentras problemas de visualización persistentes, proporciona los detalles al soporte de MyPresta.eu.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura
El módulo "Reglas de Métodos de Envío Condicionales" (`shipmethodrules`) está construido siguiendo el patrón MVC (Modelo-Vista-Controlador) de PrestaShop, aprovechando en gran medida `ObjectModel` para la persistencia de datos y un motor de políticas personalizado para la evaluación de reglas. Introduce varios controladores de administración personalizados para gestionar políticas, ver registros de auditoría y simular escenarios de pago. La lógica central gira en torno a los objetos `ShipmethodrulesPolicy`, que encapsulan las entidades `ShipmethodrulesConditionGroup` y `ShipmethodrulesCondition`, lo que permite una lógica compleja anidada de AND/OR. El `ShipmethodrulesEngine` es responsable de evaluar estas políticas contra un `ShipmethodrulesContext` dado (que representa el carrito, cliente y dirección actuales) y determinar la visibilidad de los transportistas de envío.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office
-   `controllers/front/index.php`:
    -   Nombre de la clase: `ShipmethodrulesIndexModuleFrontController`
    -   Clase padre: `ModuleFrontController`
    -   Responsabilidad: Probablemente un marcador de posición o controlador base. En muchos módulos, esto podría manejar la configuración inicial o la redirección si se necesita una página de front-office dedicada. Para este módulo, la lógica principal del front-office se integra a través de hooks en el proceso de pago.
-   `controllers/front/simulate.php`:
    -   Nombre de la clase: `ShipmethodrulesSimulateModuleFrontController`
    -   Clase padre: `ModuleFrontController`
    -   Responsabilidad: Maneja las solicitudes AJAX relacionadas con el simulador de pago. Recibe datos simulados de carrito, cliente y dirección, luego usa el `ShipmethodrulesEngine` para evaluar políticas y devuelve la visibilidad del transportista resultante.
-   `controllers/front/visibility.php`:
    -   Nombre de la clase: `ShipmethodrulesVisibilityModuleFrontController`
    -   Clase padre: `ModuleFrontController`
    -   Responsabilidad: Este controlador es crucial para las actualizaciones en tiempo real en la página de pago. Responde a las solicitudes AJAX (por ejemplo, cuando un cliente cambia la dirección o el contenido del carrito) para reevaluar las reglas de envío y devolver la lista actualizada de transportistas disponibles y sus mensajes asociados.

#### Controladores de Administración (Back-Office)
-   `controllers/admin/AdminShipmethodrulesAuditLog.php`:
    -   Nombre de la clase: `AdminShipmethodrulesAuditLogController`
    -   Clase padre: `ModuleAdminController`
    -   Nombre de la pestaña: "Registro de Auditoría"
    -   Entidad gestionada: `ShipmethodrulesLog`
    -   Responsabilidad: Gestiona la visualización y el filtrado de la tabla `ps_shipmethodrules_log`. Proporciona una vista de cuadrícula de todas las evaluaciones de reglas, incluidos los detalles sobre el carrito, el cliente, las políticas aplicadas y el resultado final (qué transportistas se mostraron/ocultaron).
-   `controllers/admin/AdminShipmethodrulesPolicies.php`:
    -   Nombre de la clase: `AdminShipmethodrulesPoliciesController`
    -   Clase padre: `ModuleAdminController`
    -   Nombre de la pestaña: "Políticas de Envío"
    -   Entidad gestionada: `ShipmethodrulesPolicy`
    -   Responsabilidad: Este es el controlador principal para gestionar las políticas de envío. Maneja la lista, adición, edición, duplicación, activación/desactivación y eliminación de objetos `ShipmethodrulesPolicy`. También orquesta la interfaz del constructor de condiciones.
-   `controllers/admin/index.php`:
    -   Nombre de la clase: `ShipmethodrulesAdminController` (o similar, si es un controlador base para la sección de administración del módulo)
    -   Clase padre: `ModuleAdminController`
    -   Responsabilidad: A menudo actúa como un despachador o un controlador predeterminado para la entrada del menú principal de administración del módulo, redirigiendo a la configuración principal o a la lista de políticas.

### 4.3 Clases y Modelos Principales (`classes/`)

-   `classes/ShipmethodrulesAdmin.php`: Probablemente una clase de ayuda para funcionalidades comunes relacionadas con la administración o estadísticas del panel.
-   `classes/ShipmethodrulesAuditLog.php`: Extiende `ObjectModel`. Se mapea a la tabla `ps_shipmethodrules_log`. Almacena los detalles de cada evento de evaluación de reglas para fines de auditoría.
    -   Campos `$definition`: `id_cart`, `id_customer`, `id_address_delivery`, `policies_applied`, `carriers_visibility`, `timestamp`.
-   `classes/ShipmethodrulesCompatibility.php`: Proporciona métodos para manejar las diferencias entre PrestaShop 1.7, 8 y 9, asegurando la compatibilidad entre versiones para las funcionalidades principales (por ejemplo, registro de hooks, acceso a la configuración).
-   `classes/ShipmethodrulesCondition.php`: Extiende `ObjectModel`. Representa una única condición dentro de un grupo de condiciones (por ejemplo, "Total del Carrito > 100 €").
    -   Campos `$definition`: `id_shipmethodrules_condition_group`, `type`, `operator`, `value`, `id_product`, `id_category`, etc.
-   `classes/ShipmethodrulesConditionEvaluator.php`: Contiene la lógica para evaluar una única `ShipmethodrulesCondition` contra el `ShipmethodrulesContext` actual.
-   `classes/ShipmethodrulesConditionGroup.php`: Extiende `ObjectModel`. Representa un grupo de condiciones vinculadas por un operador AND. Múltiples grupos pueden vincularse por un operador OR dentro de una política.
    -   Campos `$definition`: `id_shipmethodrules_policy`, `logic_operator` (implícitamente AND para condiciones internas, OR para grupos).
-   `classes/ShipmethodrulesConditionTree.php`: Gestiona la estructura jerárquica de condiciones y grupos de condiciones para una política, facilitando su almacenamiento y recuperación.
-   `classes/ShipmethodrulesContext.php`: Un objeto que encapsula todos los datos relevantes para la evaluación de reglas: `Cart`, `Customer`, `Address`, `Currency`, `Language` actuales, etc. Esto proporciona una interfaz consistente para el `ShipmethodrulesEngine`.
-   `classes/ShipmethodrulesDashboard.php`: Clase de ayuda para generar estadísticas o resúmenes del panel relacionados con la actividad del módulo.
-   `classes/ShipmethodrulesEngine.php`: La clase central para la evaluación de reglas. Toma un `ShipmethodrulesContext` y una lista de objetos `ShipmethodrulesPolicy`, aplica la estrategia de fusión configurada y devuelve el estado de visibilidad final para cada transportista.
-   `classes/ShipmethodrulesListRenderer.php`: Renderizador personalizado para listas de administración, que potencialmente añade acciones específicas (como duplicar) o formato de columna personalizado.
-   `classes/ShipmethodrulesLog.php`: Alias o implementación específica para `ShipmethodrulesAuditLog`.
-   `classes/ShipmethodrulesOrderSnapshot.php`: Captura y almacena una instantánea del estado de un pedido (carrito, cliente, dirección) en el momento de la evaluación de la regla, útil para la depuración.
-   `classes/ShipmethodrulesPolicy.php`: Extiende `ObjectModel`. El modelo principal para una regla de envío. Contiene el nombre de la política, el estado, la prioridad, los transportistas objetivo, la acción (MOSTRAR/OCULTAR), el mensaje de no disponible y una colección de objetos `ShipmethodrulesConditionGroup`.
    -   Campos `$definition`: `name`, `active`, `priority`, `action`, `unavailable_message`, `target_carriers`.
-   `classes/ShipmethodrulesPolicyDuplicator.php`: Maneja la lógica para duplicar una `ShipmethodrulesPolicy`, incluidos todos sus grupos de condiciones y condiciones asociados.
-   `classes/ShipmethodrulesPreset.php`: Probablemente gestiona conjuntos predefinidos de condiciones o políticas que se pueden aplicar rápidamente.
-   `classes/ShipmethodrulesRule.php`: Una representación más genérica de una regla, posiblemente una clase base abstracta o una iteración anterior de `ShipmethodrulesPolicy`.
-   `classes/ShipmethodrulesTreeRepository.php`: Gestiona la persistencia y recuperación de la estructura del árbol de condiciones.

### 4.4 Activos JavaScript (`views/js/`)

-   `shipmethodrules/lib/searchTool/views/js/autocomplete.js`: Funcionalidad genérica de autocompletado, probablemente utilizada para buscar productos, categorías o clientes en el constructor de condiciones.
-   `shipmethodrules/lib/searchTool/views/views/js/autocomplete.js`: Instancia duplicada o específica del script de autocompletado.
-   `shipmethodrules/views/js/adminConditionBuilder.js`: Maneja la creación, modificación y eliminación dinámica de condiciones y grupos de condiciones dentro de la interfaz de edición de políticas. Gestiona la compleja interfaz de usuario para construir reglas.
-   `shipmethodrules/views/js/adminPolicyRules.js`: JS específico para el controlador `AdminShipmethodrulesPolicies`, que gestiona la lista de políticas, acciones masivas y potencialmente interacciones con el constructor de condiciones.
-   `shipmethodrules/views/js/adminShipmethodrulesDashboard.js`: Scripts para cualquier widget o estadística del panel que se muestre en la sección de administración del módulo.
-   `shipmethodrules/views/js/adminShipmethodrulesSearchTool.js`: Integra la herramienta de búsqueda (autocompletado) específicamente para los formularios de administración del módulo.
-   `shipmethodrules/views/js/adminShipmethodrulesSimulator.js`: Impulsa la interfaz del "Simulador de Pago", manejando la entrada del usuario para cliente, dirección y carrito, y realizando llamadas AJAX a `controllers/front/simulate.php`.
-   `shipmethodrules/views/js/checkout.js`: Script de front-office inyectado en el proceso de pago. Escucha los cambios en el carrito o la dirección de entrega, luego realiza llamadas AJAX a `controllers/front/visibility.php` para actualizar dinámicamente los métodos de envío mostrados.
-   `shipmethodrules/views/js/unavailableUi.js`: Maneja la visualización y el estilo de los mensajes de método de envío no disponible en la página de pago del front office.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `shipmethodrules/lib/searchTool/views/css/autocomplete.css`: Estilos para la herramienta de búsqueda de autocompletado.
-   `shipmethodrules/lib/searchTool/views/views/css/autocomplete.css`: Instancia duplicada o específica de estilos de autocompletado.
-   `shipmethodrules/views/css/admin_order_snapshot.css`: Estilos para mostrar los detalles de la instantánea del pedido en el registro de auditoría o el simulador.
-   `shipmethodrules/views/css/admin_shipmethodrules.css`: Estilo general para las interfaces de back-office del módulo, incluidas las listas de políticas, el constructor de condiciones y el simulador.
-   `shipmethodrules/views/css/front.css`: Estilos de front-office para mostrar mensajes de método de envío no disponible o resaltar opciones de envío específicas en la página de pago.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)
-   `shipmethodrules/views/templates/hook/carrier_guard.tpl`: Renderiza una entrada oculta o un script para "proteger" contra selecciones de transportistas no válidas, asegurando que solo se puedan enviar los transportistas permitidos.
-   `shipmethodrules/views/templates/hook/carrier_list.tpl`: Anula o extiende la plantilla de lista de transportistas predeterminada en el proceso de pago para aplicar reglas de visibilidad y mostrar mensajes de no disponible. Aquí es donde se renderiza la lista filtrada de transportistas.

#### Plantillas de Administración (`views/templates/admin/`)
-   `shipmethodrules/views/templates/admin/auditPreview.tpl`: Plantilla para mostrar una vista previa detallada de una entrada del registro de auditoría.
-   `shipmethodrules/views/templates/admin/dashboard.tpl`: Plantilla para la configuración principal o la vista del panel del módulo.
-   `shipmethodrules/views/templates/admin/helpers/list/list_action_duplicate.tpl`: Plantilla personalizada para el botón de acción "duplicar" en las listas de administración (por ejemplo, para políticas).
-   `shipmethodrules/views/templates/admin/policiesPreview.tpl`: Plantilla para mostrar una vista previa de una política de envío.
-   `shipmethodrules/views/templates/admin/policyConditionBuilder.tpl`: La compleja plantilla que renderiza la interfaz de usuario para construir condiciones (listas desplegables, campos de entrada, lógica AND/OR).
-   `shipmethodrules/views/templates/admin/policyRuleCard.tpl`: Renderiza una única regla o política como una tarjeta en una vista de lista.
-   `shipmethodrules/views/templates/admin/policyRulesTable.tpl`: Renderiza la tabla de políticas de envío.
-   `shipmethodrules/views/templates/admin/scopeSelector.tpl`: Plantilla para seleccionar el alcance de una condición (por ejemplo, "Total del Carrito", "Grupo de Clientes").

#### Otras plantillas
-   `shipmethodrules/lib/searchTool/views/scripts.tpl`: Incluye JavaScript para la herramienta de búsqueda.
-   `shipmethodrules/lib/searchTool/views/views/scripts.tpl`: Instancia duplicada o específica de scripts de herramientas de búsqueda.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos
-   `ps_shipmethodrules_policy`: Almacena las definiciones principales de la política de envío (nombre, estado activo, prioridad, acción, mensaje de no disponible, transportistas objetivo).
-   `ps_shipmethodrules_condition_group`: Almacena grupos de condiciones asociados con una política.
-   `ps_shipmethodrules_condition`: Almacena condiciones individuales (tipo, operador, valor, entidades asociadas como IDs de producto/categoría).
-   `ps_shipmethodrules_log`: Almacena entradas del registro de auditoría de evaluaciones de reglas (ID de carrito, ID de cliente, marca de tiempo, políticas aplicadas, visibilidad de transportistas).
-   `ps_shipmethodrules_order_snapshot`: Almacena instantáneas detalladas de los datos del carrito/pedido para las entradas del registro de auditoría.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
|---|---|---|
| `displayHeader` | En la sección `<head>` de todas las páginas del front-office. | Inyecta los archivos CSS y JS necesarios para la funcionalidad del front-office (por ejemplo, `checkout.js`, `front.css`). |
| `displayCarrierList` | En la página de pago, donde se enumeran los métodos de envío. | El hook principal para filtrar y renderizar los métodos de envío disponibles según las políticas definidas. |
| `actionCarrierProcess` | Después de que se ha seleccionado un transportista, pero antes de que se valide el pedido. | Actúa como una "protección" para revalidar el transportista seleccionado contra las reglas, evitando el envío de una elección no válida. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Potencialmente registra el método de envío final elegido y las reglas aplicadas en el registro de auditoría. |
| `actionAdminControllerSetMedia` | En el back office, cuando se carga un controlador de administración. | Inyecta CSS y JS para las interfaces de administración del módulo (constructor de políticas, simulador, registro de auditoría). |
| `actionObjectCarrierAddAfter` | Después de que se añade un nuevo transportista. | Potencialmente actualiza datos internos del módulo o cachés relacionados con los transportistas. |
| `actionObjectCarrierUpdateAfter` | Después de que se actualiza un transportista. | Potencialmente actualiza datos internos del módulo o cachés relacionados con los transportistas. |
| `actionObjectCarrierDeleteAfter` | Después de que se elimina un transportista. | Limpia cualquier referencia al transportista eliminado en las políticas. |
| `displayBackOfficeHeader` | En el encabezado de todas las páginas del back-office. | Inyecta CSS/JS de administración global o scripts específicos para las páginas de administración del módulo. |

## 5. Soporte Oficial y Actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Reglas de Métodos de Envío Condicionales", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.

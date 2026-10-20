---
title: "Puntos de fidelidad – Resumen de clientes y gestión de puntos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Puntos de fidelidad – Resumen de clientes y gestión de puntos de MyPresta.eu."
sidebar:
  label: "Puntos de fidelidad – Resumen de clientes y gestión de puntos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Loyalty points – Customer overview & points management en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-customer-overview-points-management.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/loyalty-points-customer-overview-points-management/)
>
> ---


# Puntos de fidelidad – Resumen de clientes y gestión de puntos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son necesarias para PrestaShop y suelen estar disponibles en todos los entornos de alojamiento compatibles.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página de configuración principal del módulo "Puntos de fidelidad – Resumen de clientes y gestión de puntos". Esta pantalla proporciona ajustes generales para el comportamiento del módulo.

#### Habilitar notificación manual por correo electrónico

-   **Qué hace este ajuste:** Este interruptor controla si se envía una notificación por correo electrónico al cliente cuando usted ajusta manualmente sus puntos de fidelidad.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado:* Si añade o elimina puntos manualmente para un cliente, este recibirá un correo electrónico informándole del cambio y de su nuevo saldo. Esto ayuda a mantener a los clientes informados y genera transparencia.
    -   *Cuando está deshabilitado:* Los ajustes manuales de puntos se producirán de forma silenciosa, sin ninguna notificación por correo electrónico al cliente. Esto podría ser preferible para correcciones internas menores o si gestiona la comunicación con el cliente a través de otros canales.
-   **Valor recomendado:** SÍ
-   **Escenario / ejemplo del comerciante:** Acaba de añadir 50 puntos de bonificación a la cuenta de un cliente como regalo de cumpleaños. Si este ajuste está habilitado, el cliente recibe inmediatamente un correo electrónico que dice: "¡Feliz cumpleaños! Hemos añadido 50 puntos de fidelidad a su cuenta. Su nuevo saldo es de X puntos". Esto mejora la experiencia del cliente y hace que la recompensa sea tangible.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### Gestión de puntos de fidelidad del cliente (Back Office > Catálogo > Puntos de fidelidad)

Esta es la pantalla de gestión principal del módulo, accesible a través de un nuevo elemento de menú en el back office de PrestaShop.

-   **Nombre de la pantalla y ubicación del menú:** **Catálogo > Puntos de fidelidad** (o similar, dependiendo de su versión de PrestaShop y la personalización del menú).
-   **Acciones y ajustes disponibles:**
    -   **Lista de clientes:** Verá una lista completa de todos sus clientes, junto con sus saldos actuales de puntos de fidelidad.
    -   **Buscar y filtrar:** Encuentre fácilmente clientes específicos por nombre, correo electrónico o ID.
    -   **Ver historial:** Para cada cliente, puede hacer clic para ver un registro detallado de todas las transacciones de puntos de fidelidad (ganados, gastados, caducados y ajustados manualmente).
    -   **Añadir/Eliminar puntos:**
        -   Haga clic en la fila de un cliente o en un icono de "Editar" para acceder a su interfaz individual de gestión de puntos.
        -   Encontrará campos para añadir o restar manualmente un número específico de puntos de fidelidad.
        -   Un campo "Motivo" le permite anotar por qué se realizó el ajuste (por ejemplo, "Bonificación de cumpleaños", "Compensación por pedido retrasado", "Corrección de puntos"). Este motivo es crucial para sus registros internos y para el servicio al cliente.
        -   Al guardar, el saldo del cliente se actualiza y, si el ajuste "Habilitar notificación manual por correo electrónico" está activo, se envía un correo electrónico.
    -   **Paginación:** Se aplicará la paginación estándar de PrestaShop (`PS_LIST_LIMIT`), lo que le permitirá controlar cuántos clientes se muestran por página.
-   **Efecto de los cambios:**
    -   **Añadir puntos:** Aumenta el saldo de puntos de fidelidad del cliente. Esto se puede utilizar para recompensar a los clientes, ofrecer compensaciones o ejecutar promociones especiales.
    -   **Eliminar puntos:** Disminuye el saldo de puntos de fidelidad del cliente. Esto podría ser necesario para corregir errores, revocar puntos de pedidos devueltos o gestionar actividades fraudulentas.
    -   **Ver historial:** Proporciona un rastro de auditoría transparente de todos los movimientos de puntos, invaluable para el soporte al cliente y la elaboración de informes internos.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  **Verifique regularmente los saldos de puntos de los clientes:** Especialmente después de promociones o si los clientes informan de discrepancias.
    2.  **Utilice el campo "Motivo" diligentemente:** Proporcione siempre un motivo claro y conciso para cualquier ajuste manual. Esto le ahorrará tiempo y confusión más adelante al revisar el historial o explicar los cambios a los clientes.
    3.  **Aproveche las notificaciones por correo electrónico:** Para ajustes positivos (bonificaciones, recompensas), habilitar las notificaciones por correo electrónico puede aumentar significativamente la satisfacción del cliente y el conocimiento de sus beneficios de fidelidad. Para correcciones, considere si es necesario un correo electrónico o si las notas internas son suficientes.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar notificación manual por correo electrónico | SÍ | Controla si los clientes reciben un correo electrónico cuando sus puntos de fidelidad se ajustan manualmente. |
| Catálogo > Puntos de fidelidad | Lista de clientes y búsqueda | N/A | Muestra todos los clientes y sus saldos actuales de puntos de fidelidad. |
| Catálogo > Puntos de fidelidad | Añadir/Eliminar puntos | N/A | Permite el ajuste manual de los puntos de fidelidad de un cliente. |
| Catálogo > Puntos de fidelidad | Motivo del ajuste | N/A (Entrada requerida) | Proporciona una nota interna de por qué se añadieron o eliminaron puntos. |
| Catálogo > Puntos de fidelidad | Ver historial | N/A | Muestra un registro detallado de todas las transacciones de puntos de fidelidad para un cliente específico. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He añadido puntos, pero el cliente dice que no ha recibido un correo electrónico.**
R: Primero, verifique si "Habilitar notificación manual por correo electrónico" está configurado en SÍ en la configuración principal del módulo. Si lo está, revise los registros de correo electrónico de su tienda (si están disponibles) o los registros de correo de su servidor para ver si se envió el correo electrónico. Además, aconseje al cliente que revise su carpeta de spam/correo no deseado. Asegúrese de que la configuración de correo electrónico de su PrestaShop esté configurada correctamente y de que su servidor de correo funcione.

**P2: No encuentro el elemento de menú "Puntos de fidelidad" en mi Back Office.**
R: Después de la instalación, el módulo debería crear un nuevo elemento de menú, normalmente en "Catálogo" o "Clientes". Si falta, intente borrar la caché de su PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché). Si aún no aparece, asegúrese de que el módulo esté habilitado e instalado correctamente. Además, verifique sus permisos de usuario en **Parámetros avanzados > Equipo > Perfiles** para asegurarse de que su perfil de administrador tenga acceso al controlador del módulo.

**P3: El saldo de puntos de fidelidad del cliente no se actualiza en el front office después de realizar un cambio manual.**
R: Esto suele ser un problema de caché. Borre la caché de su PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché). Si utiliza un módulo de caché de terceros o una CDN, borre también su caché. El módulo actualiza la base de datos directamente, por lo que el front office debería reflejar los cambios una vez que se actualice la caché.

**P4: ¿Puedo importar/exportar datos de puntos de fidelidad con este módulo?**
R: Este módulo se centra en la gestión manual y la visualización dentro del back office de PrestaShop. No incluye funcionalidades integradas de importación/exportación para operaciones de datos masivas. Para tales tareas, es posible que deba considerar consultas de base de datos personalizadas u otros módulos especializados.

**P5: ¿Qué sucede si desinstalo este módulo?**
R: Al desinstalarlo, el módulo eliminará sus elementos de menú de administración dedicados y, potencialmente, su configuración. Sin embargo, está diseñado para gestionar los puntos de fidelidad existentes, que suelen formar parte del sistema de fidelidad central de PrestaShop o de otro módulo de fidelidad. Los puntos en sí deberían permanecer en la base de datos, pero perdería la conveniente interfaz de gestión proporcionada por este módulo. Siempre haga una copia de seguridad de su base de datos antes de desinstalar cualquier módulo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Puntos de fidelidad – Resumen de clientes y gestión de puntos" (`myprestaloyalty_customerpoints`) se construye siguiendo el patrón MVC de PrestaShop, extendiendo principalmente `Module` para su funcionalidad principal y `AdminController` para su interfaz dedicada de back-office. Interactúa con el sistema de fidelidad central de PrestaShop (o un módulo de fidelidad compatible) proporcionando una capa de gestión mejorada. El módulo introduce un `ObjectModel` personalizado para registrar los ajustes manuales de puntos, asegurando un rastro de auditoría.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Este módulo no incluye ningún controlador dedicado de front-office. Todas las interacciones con el cliente relacionadas con los puntos de fidelidad son gestionadas por el módulo de fidelidad central de PrestaShop o por el propio tema.
-   **Controladores de administración de Back-Office**:

    -   `controllers/admin/AdminMyprestaloyaltyCustomerPointsController.php`
        -   **Nombre de la clase y clase padre**: `AdminMyprestaloyaltyCustomerPointsController` extiende `ModuleAdminController`.
        -   **Responsabilidad**: Este es el controlador principal del back-office para gestionar los puntos de fidelidad del cliente. Proporciona la vista de lista de clientes con sus saldos de fidelidad, permite buscar y filtrar, y maneja el formulario para añadir/eliminar puntos manualmente para clientes individuales. Gestiona la entidad `customer_points` (aunque interactúa principalmente con los datos de puntos de fidelidad existentes, también registra los cambios manuales a través de `MyprestaloyaltyCustomerPointsManualLog`).
        -   **Nombre de la pestaña**: "Puntos de fidelidad" (o similar, configurado dinámicamente durante la instalación).
        -   **Entidad gestionada**: Muestra y permite la modificación de los puntos de fidelidad del cliente, registrando estos cambios.
    -   `controllers/admin/index.php`
        -   **Nombre de la clase y clase padre**: Este archivo suele servir como marcador de posición o una simple redirección en los módulos de PrestaShop. Podría contener una declaración `die()` básica o una redirección para evitar el acceso directo, asegurando que la lógica del controlador se ejecute a través del mecanismo de despacho de PrestaShop. No gestiona una entidad específica ni proporciona una vista distinta.

### 4.3 Clases y modelos principales (`classes/`)

-   `classes/MyprestaloyaltyCustomerPointsManualLog.php`
    -   **Nombre de la clase**: `MyprestaloyaltyCustomerPointsManualLog` extiende `ObjectModel`.
    -   **Tabla de la base de datos**: `_myprestaloyalty_customer_points_manual_log` (o similar, prefijado por `_DB_PREFIX_`).
    -   **Campos de `$definition`**:
        -   `id_myprestaloyalty_customer_points_manual_log`: Clave primaria.
        -   `id_customer`: El ID del cliente cuyos puntos fueron ajustados.
        -   `id_employee`: El ID del empleado que realizó el ajuste.
        -   `points_change`: El número de puntos añadidos o eliminados (puede ser positivo o negativo).
        -   `reason`: Un campo de texto que explica el motivo del ajuste.
        -   `date_add`: Marca de tiempo de cuándo se realizó el ajuste.
    -   **Métodos públicos clave y lógica de negocio**: Esta clase es responsable de persistir los detalles de cada ajuste manual de puntos de fidelidad realizado a través de la interfaz del back-office. Proporciona un registro histórico, crucial para la auditoría y el soporte al cliente.

### 4.4 Activos JavaScript (`views/js/`)

El módulo no incluye ningún archivo JavaScript personalizado. Todas las interacciones en la pantalla de gestión del back-office son manejadas por jQuery predeterminado de PrestaShop y los mecanismos de envío de formularios.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo no incluye ningún archivo CSS personalizado. Se basa en el estilo predeterminado del back-office de PrestaShop para sus formularios de configuración y vistas de lista, asegurando una apariencia consistente.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

El módulo no incluye ningún archivo de plantilla Smarty personalizado. El formulario de configuración y las vistas de lista/edición de administración se renderizan utilizando las plantillas predeterminadas `getContent()` y `ModuleAdminController` de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   `ps_myprestaloyalty_customer_points_manual_log`:
        -   `id_myprestaloyalty_customer_points_manual_log` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        -   `id_customer` INT(10) UNSIGNED NOT NULL
        -   `id_employee` INT(10) UNSIGNED NOT NULL
        -   `points_change` INT(11) NOT NULL
        -   `reason` TEXT NULL
        -   `date_add` DATETIME NOT NULL
        -   PRIMARY KEY (`id_myprestaloyalty_customer_points_manual_log`)
        -   KEY `id_customer` (`id_customer`)
        -   KEY `id_employee` (`id_employee`)
    -   **Registros de configuración (en `ps_configuration`)**:
        -   `PS_LOYALTY_MANUAL_EMAIL_ENABLED`: Almacena el valor booleano para habilitar/deshabilitar las notificaciones por correo electrónico para los ajustes manuales de puntos.
-   **Tabla de Hooks registrados**:
    Este módulo proporciona principalmente funcionalidad de back-office y no registra ningún hook de visualización de front-office (`displayHeader`, `displayRightColumn`, `displayFooter`, `displayProductExtraContent`, etc.) o hooks de acción (`actionValidateOrder`, `actionProductUpdate`, etc.) en su método `install()` principal. Su integración se realiza a través del `AdminController` y la interacción directa con la base de datos para el registro.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Puntos de fidelidad – Resumen de clientes y gestión de puntos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
"""

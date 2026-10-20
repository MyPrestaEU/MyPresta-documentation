---
title: "Botón de Devolución Gratuito - Retiro de la UE - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Botón de Devolución Gratuito - Retiro de la UE' de MyPresta.eu."
sidebar:
  label: "Botón de Devolución Gratuito - Retiro de la UE"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Return Button Free - EU Withdrawal en MyPresta.eu](https://mypresta.eu/modules/front-office-features/return-button-free-eu-withdrawal.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/return-button-free-eu-withdrawal/)
>
> ---


# Botón de Devolución Gratuito - Retiro de la UE

## 1. Requisitos y Compatibilidad
-   **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilidad con PHP**: PHP 7.1 - 8.5
-   **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)
Esta es la pantalla de configuración principal del módulo, donde controla su comportamiento general y apariencia.

#### Pestaña de Ajustes Generales

-   **Activar Módulo:**
    -   **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar la funcionalidad del módulo en su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El botón de desistimiento y la funcionalidad estarán activos y visibles para los clientes según sus otras configuraciones.
        -   *Cuando está desactivado:* Las características del módulo estarán completamente ocultas del front office, y los clientes no podrán enviar solicitudes de desistimiento a través de él.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo del comerciante:** Lo activaría cuando esté listo para ofrecer la opción de desistimiento a sus clientes. Podría desactivarlo temporalmente durante el mantenimiento o si necesita realizar cambios significativos en su política de devoluciones.

-   **Mostrar Botón de Desistimiento En:**
    -   **Qué hace este ajuste:** Determina dónde aparece el botón principal de "Solicitud de Desistimiento" en el front office de su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cabecera:* El botón aparece en la sección superior de su sitio web, a menudo visible globalmente.
        -   *Columna Izquierda:* El botón aparece en la barra lateral izquierda (si su tema tiene una).
        -   *Columna Derecha:* El botón aparece en la barra lateral derecha (si su tema tiene una).
        -   *Página de Producto:* El botón aparece en las páginas de productos individuales.
        -   *Pie de Página:* El botón aparece en la sección inferior de su sitio web.
    -   **Valor recomendado:** Pie de página (a menudo una buena ubicación discreta para enlaces legales) o Cabecera (para máxima visibilidad). Elija según el diseño de su tema y su preferencia de prominencia.
    -   **Escenario / ejemplo del comerciante:** Si desea que los clientes encuentren fácilmente la opción, colocarla en la Cabecera o el Pie de página es común. Si prefiere que sea menos prominente pero aún accesible, una columna podría ser adecuada.

-   **Permitir Solicitudes de Desistimiento de Invitados:**
    -   **Qué hace este ajuste:** Controla si los clientes que compraron sin crear una cuenta aún pueden enviar una solicitud de desistimiento.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Los invitados podrán acceder al formulario de desistimiento proporcionando su referencia de pedido y dirección de correo electrónico.
        -   *Cuando está desactivado:* Solo los clientes registrados que hayan iniciado sesión en sus cuentas podrán enviar solicitudes de desistimiento.
    -   **Valor recomendado:** SÍ (Altamente recomendado para el cumplimiento de la UE, ya que el derecho de desistimiento se aplica a todos los consumidores, no solo a los registrados).
    -   **Escenario / ejemplo del comerciante:** Habilitar esto asegura que cumpla con los derechos del consumidor para todos los clientes, independientemente de su método de pago, y evita frustrar a los invitados que no pueden encontrar una manera de desistir.

-   **Estados de Pedido para la Elegibilidad del Desistimiento:**
    -   **Qué hace este ajuste:** Define qué estados de pedido hacen que un pedido sea elegible para una solicitud de desistimiento. Por ejemplo, solo podría permitir desistimientos para pedidos que hayan sido "Entregados" o "Enviados".
    -   **Efecto de cambiar este ajuste:** Los clientes solo verán la opción de desistimiento para los pedidos que coincidan con uno de los estados seleccionados en su historial de pedidos o al introducir una referencia de pedido de invitado.
    -   **Valor recomendado:** Seleccione estados como "Pago aceptado", "Preparación en curso", "Enviado", "Entregado". Evite estados como "Cancelado" o "Reembolsado", ya que los desistimientos no son aplicables allí.
    -   **Escenario / ejemplo del comerciante:** Desea permitir desistimientos para pedidos que ya están procesados o entregados, pero no para pedidos que aún están pendientes de pago o que ya han sido cancelados.

-   **Estados de Pedido para la Confirmación del Desistimiento:**
    -   **Qué hace este ajuste:** Especifica qué estado de pedido debe aplicarse automáticamente a un pedido una vez que el cliente ha enviado con éxito una solicitud de desistimiento. Esto le ayuda a identificar rápidamente los pedidos con solicitudes de desistimiento pendientes.
    -   **Efecto de cambiar este ajuste:** Cuando un cliente envía un desistimiento, el estado del pedido cambiará al que seleccione aquí.
    -   **Valor recomendado:** Cree un nuevo estado de pedido distinto como "Desistimiento Solicitado" o "Retiro de la UE Pendiente" en la configuración de estados de pedido de su PrestaShop (en Parámetros de la tienda > Ajustes de pedidos > Estados) y selecciónelo aquí.
    -   **Escenario / ejemplo del comerciante:** Establecer un estado específico como "Desistimiento Solicitado" permite a su equipo de atención al cliente filtrar y gestionar fácilmente los pedidos que requieren atención para un proceso de desistimiento.

-   **Estados de Pedido para la Finalización del Desistimiento:**
    -   **Qué hace este ajuste:** Especifica qué estado de pedido debe aplicarse automáticamente a un pedido una vez que usted, el comerciante, ha procesado y completado el desistimiento (por ejemplo, ha emitido un reembolso).
    -   **Efecto de cambiar este ajuste:** Después de marcar una solicitud de desistimiento como completada en la interfaz de administración del módulo, el estado del pedido asociado se actualizará a este estado elegido.
    -   **Valor recomendado:** Seleccione un estado existente como "Reembolsado" o cree uno nuevo como "Retiro de la UE Completado".
    -   **Escenario / ejemplo del comerciante:** Una vez que haya procesado el reembolso y cerrado el caso de desistimiento, actualizar el estado del pedido a "Reembolsado" proporciona un registro claro tanto para usted como para el cliente.

-   **Activar Estadísticas:**
    -   **Qué hace este ajuste:** Controla si el módulo recopila estadísticas anónimas sobre su uso. Estos datos ayudan al desarrollador del módulo a mejorarlo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El módulo enviará datos de uso anónimos.
        -   *Cuando está desactivado:* No se enviarán datos de uso.
    -   **Valor recomendado:** SÍ (Ayuda a mejorar el módulo para todos).
    -   **Escenario / ejemplo del comerciante:** Lo activa para contribuir al desarrollo del módulo, o lo desactiva si tiene políticas estrictas de privacidad de datos que impiden cualquier transmisión de datos externa.

#### Pestaña de Información Legal

-   **Período de Desistimiento (Días):**
    -   **Qué hace este ajuste:** Define el número de días naturales que un cliente tiene para ejercer su derecho de desistimiento, a partir del día en que recibe la mercancía.
    -   **Efecto de cambiar este ajuste:** El módulo mostrará este período a los clientes y lo utilizará internamente para cualquier cálculo de fechas o comprobaciones de elegibilidad.
    -   **Valor recomendado:** 14 (Este es el requisito legal mínimo en la UE, pero puede ofrecer un período más largo si lo desea).
    -   **Escenario / ejemplo del comerciante:** Lo establece en 14 días para cumplir con la ley de la UE. Si ofrece una política de devoluciones más generosa, podría establecerlo en 30 días.

-   **Texto del Formulario de Desistimiento:**
    -   **Qué hace este ajuste:** Le permite personalizar el texto introductorio que se muestra en la parte superior del formulario de solicitud de desistimiento. Este es un campo multi-idioma.
    -   **Efecto de cambiar este ajuste:** El texto que introduzca aparecerá a los clientes cuando accedan al formulario de desistimiento.
    -   **Valor recomendado:** Proporcione instrucciones claras y concisas o una breve explicación del proceso de desistimiento.
    -   **Escenario / ejemplo del comerciante:** Podría añadir un mensaje como: "Por favor, rellene este formulario para ejercer su derecho de desistimiento. Tiene 14 días desde la recepción de su pedido para enviar esta solicitud."

-   **Texto del Correo Electrónico de Confirmación:**
    -   **Qué hace este ajuste:** Le permite personalizar el texto incluido en el correo electrónico de confirmación enviado a los clientes después de que envíen una solicitud de desistimiento. Este es un campo multi-idioma.
    -   **Efecto de cambiar este ajuste:** El texto que introduzca formará parte del correo electrónico que reciban los clientes, sirviendo como prueba en soporte duradero de su solicitud.
    -   **Valor recomendado:** Incluya información importante como los siguientes pasos, dónde enviar la mercancía y cualquier instrucción específica de devolución.
    -   **Escenario / ejemplo del comerciante:** Podría escribir: "Gracias por su solicitud de desistimiento. Su solicitud ha sido recibida y se procesará en breve. Por favor, devuelva la mercancía a [Su Dirección de Devolución] en un plazo de 14 días. Para más detalles, consulte nuestra política de devoluciones."

-   **Enlace a la Política de Desistimiento:**
    -   **Qué hace este ajuste:** Le permite proporcionar un enlace a la página detallada de política de desistimiento o devolución de su tienda.
    -   **Efecto de cambiar este ajuste:** Se mostrará un enlace en el formulario de desistimiento, dirigiendo a los clientes a su política completa.
    -   **Valor recomendado:** Proporcione la URL de su página CMS dedicada a devoluciones/desistimientos.
    -   **Escenario / ejemplo del comerciante:** Tiene una página CMS titulada "Política de Devoluciones y Reembolsos" en `su_tienda.com/content/devoluciones-reembolsos`. Introduciría esta URL aquí.

#### 2.1.1 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| **Pestaña de Ajustes Generales** | Activar Módulo | SÍ | Activa/desactiva la funcionalidad del módulo. |
| | Mostrar Botón de Desistimiento En | Pie de página / Cabecera | Establece la ubicación del botón principal de desistimiento. |
| | Permitir Solicitudes de Desistimiento de Invitados | SÍ | Habilita el desistimiento para clientes no registrados. |
| | Estados de Pedido para la Elegibilidad del Desistimiento | Pago aceptado, Enviado, Entregado | Define qué estados de pedido permiten solicitudes de desistimiento. |
| | Estados de Pedido para la Confirmación del Desistimiento | "Desistimiento Solicitado" (Personalizado) | Estado aplicado al pedido tras la presentación del cliente. |
| | Estados de Pedido para la Finalización del Desistimiento | "Reembolsado" (Existente) / "Retiro de la UE Completado" (Personalizado) | Estado aplicado al pedido tras la finalización por parte del comerciante. |
| | Activar Estadísticas | SÍ | Permite la recopilación anónima de datos de uso para mejorar el módulo. |
| **Pestaña de Información Legal** | Período de Desistimiento (Días) | 14 | Establece el período legal para el desistimiento. |
| | Texto del Formulario de Desistimiento | Personalizable | Texto introductorio en el formulario de desistimiento. |
| | Texto del Correo Electrónico de Confirmación | Personalizable | Texto incluido en el correo electrónico de confirmación del desistimiento. |
| | Enlace a la Política de Desistimiento | URL de su página CMS | Enlace a su política detallada de devoluciones/desistimientos. |

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### Solicitudes de Desistimiento (Back Office > Módulos > Botón de Devolución Gratuito > Solicitudes de Desistimiento)
Esta pantalla de administración dedicada es donde gestiona todas las solicitudes de desistimiento entrantes de sus clientes.

-   **Nombre de la Pantalla y Ubicación del Menú:** **Solicitudes de Desistimiento** (se encuentra en el menú principal "Módulos", luego en el submenú "Botón de Devolución Gratuito").
-   **Acciones y Ajustes Disponibles:**
    -   **Tabla de Listado:** Muestra una lista completa de todas las solicitudes de desistimiento.
        -   **ID:** Identificador único para cada solicitud.
        -   **Enviado:** Fecha y hora en que se envió la solicitud.
        -   **Pedido:** La referencia del pedido de PrestaShop asociado.
        -   **Nombre, Apellido, Correo electrónico:** Detalles de contacto del cliente.
        -   **Alcance:** Indica si es un desistimiento de pedido completo (esta versión gratuita solo admite el desistimiento de pedido completo).
        -   **Tipo:** El tipo de desistimiento (por ejemplo, "Retiro de la UE").
        -   **Estado:** El estado actual de la solicitud de desistimiento (por ejemplo, "Pendiente", "Procesado", "Cancelado").
    -   **Ver Detalles:** Haga clic en cualquier solicitud de la lista para abrir una vista detallada.
        -   Esta vista proporciona toda la información enviada por el cliente, incluidos los detalles del pedido, los productos y cualquier nota adicional.
        -   Puede añadir notas internas, cambiar el estado del desistimiento (por ejemplo, de "Pendiente" a "Procesado" o "Cancelado") y realizar un seguimiento del historial de cambios.
        -   El ajuste "Estados de Pedido para la Finalización del Desistimiento" (de la configuración principal) se aplicará al pedido asociado cuando marque un desistimiento como completado aquí.
    -   **Filtrado y Búsqueda:** Puede filtrar la lista por estado, nombre del cliente, ID de pedido, etc., para encontrar rápidamente solicitudes específicas.
-   **Efecto de los cambios:**
    -   **Cambio de Estado:** La actualización del estado de una solicitud de desistimiento (por ejemplo, a "Procesado" o "Completado") actualizará el registro en el módulo y, si está configurado, el estado del pedido de PrestaShop asociado. Esto le ayuda a seguir el progreso y comunicarse con los clientes.
    -   **Añadir Notas:** Las notas internas son para referencia de su equipo y no son visibles para el cliente. Ayudan a documentar la comunicación y las acciones tomadas para cada desistimiento.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Revise regularmente la pantalla "Solicitudes de Desistimiento" en busca de nuevas solicitudes "Pendientes".
    2.  Haga clic en una solicitud para ver sus detalles.
    3.  Revise la información del cliente y el pedido asociado.
    4.  Comuníquese con el cliente según sea necesario (por ejemplo, proporcione instrucciones de envío de devolución).
    5.  Una vez que la mercancía sea recibida e inspeccionada, procese el reembolso en la gestión de pedidos de PrestaShop.
    6.  Actualice el estado de la solicitud de desistimiento en el módulo a "Procesado" o "Completado". Esto también actualizará el estado del pedido principal si configuró "Estados de Pedido para la Finalización del Desistimiento".
    7.  Añada cualquier nota interna relevante sobre el reembolso, los números de seguimiento o la comunicación.

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

-   **P: El botón de desistimiento no aparece en mi tienda.**
    -   **R:** Primero, compruebe si el módulo está "Activado" en su configuración. Luego, verifique que haya seleccionado una ubicación para "Mostrar Botón de Desistimiento En" (por ejemplo, Pie de página, Cabecera). Si su tema está muy personalizado, es posible que no se esté enganchando correctamente. Intente seleccionar una ubicación de visualización diferente. Además, asegúrese de que su caché de Smarty esté borrada (Parámetros avanzados > Rendimiento > Borrar caché).
-   **P: Los clientes están enviando solicitudes de desistimiento, pero el estado del pedido no cambia.**
    -   **R:** Vaya a la configuración del módulo y compruebe el ajuste "Estados de Pedido para la Confirmación del Desistimiento". Asegúrese de haber seleccionado un estado de pedido apropiado allí. Si creó un nuevo estado, asegúrese de que esté configurado correctamente en PrestaShop (Parámetros de la tienda > Ajustes de pedidos > Estados).
-   **P: ¿Pueden los clientes desistir de productos individuales de un pedido con este módulo?**
    -   **R:** No, el módulo gratuito "Botón de Devolución Gratuito - Retiro de la UE" está diseñado únicamente para el **desistimiento de pedido completo**, según la Directiva de la UE. Si necesita gestionar devoluciones parciales de productos individuales, necesitaría un módulo de gestión de devoluciones más avanzado.
-   **P: El módulo está instalado, pero el texto del formulario o del correo electrónico está en el idioma incorrecto o parece genérico.**
    -   **R:** Los ajustes "Texto del Formulario de Desistimiento" y "Texto del Correo Electrónico de Confirmación" son campos multi-idioma. Asegúrese de haber introducido el texto deseado para cada idioma habilitado en su tienda. Puede cambiar entre idiomas utilizando el icono de la bandera junto al área de texto en la configuración del módulo.
-   **P: He actualizado el módulo y ahora algo no funciona bien. ¿Qué debo hacer?**
    -   **R:** Después de cualquier actualización del módulo, es una buena práctica borrar la caché de PrestaShop. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché". Si el problema persiste, compruebe la configuración del módulo para asegurarse de que sigue siendo la que espera.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Botón de Devolución Gratuito - Retiro de la UE", destinada a desarrolladores y webmasters.

### 4.1 Visión General de la Arquitectura
El módulo sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop. Aprovecha `ModuleFrontController` para las interacciones del front-office y `AdminController` para la gestión del back-office. Se utiliza `ObjectModel` para el almacenamiento de datos persistentes relacionados con las solicitudes de desistimiento. Los servicios clave y las clases de ayuda encapsulan la lógica de negocio y garantizan la compatibilidad entre las versiones de PrestaShop. El módulo se integra con varios hooks de PrestaShop para mostrar su funcionalidad.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office
Estos controladores gestionan las interacciones orientadas al cliente relacionadas con las solicitudes de desistimiento.

-   `rbfree/controllers/front/confirm.php`
    *   Nombre de la clase: `RbfConfirmModuleFrontController` (extiende `RbfModuleFrontController`)
    *   Responsabilidad: Muestra el paso de confirmación final del formulario de desistimiento, permitiendo al cliente revisar y enviar su solicitud. Gestiona el envío POST para crear una nueva entrada `RbfWithdrawal`.
-   `rbfree/controllers/front/form.php`
    *   Nombre de la clase: `RbfFormModuleFrontController` (extiende `RbfModuleFrontController`)
    *   Responsabilidad: Renderiza el formulario inicial de solicitud de desistimiento. Gestiona la validación de entrada para la referencia del pedido, el correo electrónico y los detalles del cliente.
-   `rbfree/controllers/front/print.php`
    *   Nombre de la clase: `RbfPrintModuleFrontController` (extiende `RbfModuleFrontController`)
    *   Responsabilidad: Proporciona una versión imprimible del formulario de solicitud de desistimiento, normalmente después del envío, para los registros del cliente.
-   `rbfree/controllers/front/RbfModuleFrontController.php`
    *   Nombre de la clase: `RbfModuleFrontController` (extiende `ModuleFrontController`)
    *   Responsabilidad: Clase base para todos los controladores del front-office del módulo, proporcionando utilidades comunes, comprobaciones de seguridad y asignaciones de variables Smarty.
-   `rbfree/controllers/front/status.php`
    *   Nombre de la clase: `RbfStatusModuleFrontController` (extiende `RbfModuleFrontController`)
    *   Responsabilidad: Muestra el estado actual de una solicitud de desistimiento específica al cliente.
-   `rbfree/controllers/front/track.php`
    *   Nombre de la clase: `RbfTrackModuleFrontController` (extiende `RbfModuleFrontController`)
    *   Responsabilidad: Permite a los clientes (incluidos los invitados) seguir su solicitud de desistimiento introduciendo una referencia de pedido y un correo electrónico.

#### Controladores de Administración del Back-Office
Estos controladores gestionan la interfaz de administración para las solicitudes de desistimiento.

-   `rbfree/controllers/admin/AdminRbfWithdrawalController.php`
    *   Nombre de la clase: `AdminRbfWithdrawalController` (extiende `ModuleAdminController`)
    *   Nombre de la pestaña: "Solicitudes de Desistimiento" (en "Módulos > Botón de Devolución Gratuito")
    *   Entidad gestionada: `RbfWithdrawal`
    *   Responsabilidad: Proporciona la interfaz CRUD (Crear, Leer, Actualizar, Eliminar) para gestionar las solicitudes de desistimiento. Muestra una lista de solicitudes, permite ver información detallada, actualizar el estado y añadir notas. Gestiona los envíos de formularios para cambios de estado y notas.

### 4.3 Clases y Modelos Principales (`classes/`)

-   `rbfree/classes/RbfCompatibility.php`
    *   Nombre de la clase: `RbfCompatibility`
    *   Responsabilidad: Proporciona métodos de ayuda para garantizar la compatibilidad entre diferentes versiones de PrestaShop (por ejemplo, gestionando las diferencias en los métodos `Context` o `Tools`).
-   `rbfree/classes/RbfSecurity.php`
    *   Nombre de la clase: `RbfSecurity`
    *   Responsabilidad: Contiene métodos de ayuda relacionados con la seguridad, como la generación y validación de tokens, para proteger los formularios contra ataques CSRF.
-   `rbfree/classes/RbfSelfHeal.php`
    *   Nombre de la clase: `RbfSelfHeal`
    *   Responsabilidad: Implementa la lógica para la auto-reparación o comprobaciones de diagnóstico, asegurando la integridad del módulo y la coherencia de los datos.
-   `rbfree/classes/RbfStatsService.php`
    *   Nombre de la clase: `RbfStatsService`
    *   Responsabilidad: Gestiona la recopilación y el envío de estadísticas de uso anónimas si el comerciante lo ha habilitado.
-   `rbfree/classes/RbfWithdrawal.php`
    *   Nombre de la clase: `RbfWithdrawal` (extiende `ObjectModel`)
    *   Tabla de base de datos: `ps_rbf_withdrawal`
    *   Campos `$definition`: Define la estructura de una solicitud de desistimiento, incluyendo `id_order`, `id_customer`, `firstname`, `lastname`, `email`, `status`, `date_add`, `date_upd`, etc.
    *   Métodos públicos clave: `add()`, `update()`, `delete()`, métodos para recuperar detalles de desistimiento, gestionar transiciones de estado.
-   `rbfree/classes/RbfWithdrawalAttachment.php`
    *   Nombre de la clase: `RbfWithdrawalAttachment` (extiende `ObjectModel`)
    *   Tabla de base de datos: `ps_rbf_withdrawal_attachment`
    *   Campos `$definition`: Almacena información sobre los archivos adjuntos a una solicitud de desistimiento (si la versión Pro lo admite).
    *   Métodos públicos clave: Métodos para gestionar adjuntos.
-   `rbfree/classes/RbfWithdrawalHistory.php`
    *   Nombre de la clase: `RbfWithdrawalHistory` (extiende `ObjectModel`)
    *   Tabla de base de datos: `ps_rbf_withdrawal_history`
    *   Campos `$definition`: Registra los cambios en el estado de una solicitud de desistimiento u otros atributos clave.
    *   Métodos públicos clave: `add()`, métodos para recuperar el historial.
-   `rbfree/classes/RbfWithdrawalNote.php`
    *   Nombre de la clase: `RbfWithdrawalNote` (extiende `ObjectModel`)
    *   Tabla de base de datos: `ps_rbf_withdrawal_note`
    *   Campos `$definition`: Almacena notas internas añadidas por los administradores a una solicitud de desistimiento.
    *   Métodos públicos clave: `add()`, métodos para recuperar notas.
-   `rbfree/classes/RbfWithdrawalProduct.php`
    *   Nombre de la clase: `RbfWithdrawalProduct` (extiende `ObjectModel`)
    *   Tabla de base de datos: `ps_rbf_withdrawal_product`
    *   Campos `$definition`: Almacena los detalles de los productos incluidos en una solicitud de desistimiento.
    *   Métodos públicos clave: Métodos para gestionar productos asociados.
-   `rbfree/classes/RbfWithdrawalService.php`
    *   Nombre de la clase: `RbfWithdrawalService`
    *   Responsabilidad: Encapsula la lógica de negocio principal para gestionar las solicitudes de desistimiento, como crear nuevas solicitudes, actualizar estados de pedidos, enviar correos electrónicos y validar la elegibilidad.

### 4.4 Activos JavaScript (`views/js/`)

-   `rbfree/views/js/admin-order-state-picker.js`
    *   Ámbito: Back-office
    *   Detalles: Gestiona la selección interactiva de estados de pedido en la configuración del módulo, probablemente para los ajustes "Estados de Pedido para la Elegibilidad/Confirmación/Finalización del Desistimiento".
-   `rbfree/views/js/front.js`
    *   Ámbito: Front-office
    *   Detalles: Contiene JavaScript general del front-office para el módulo. Esto podría incluir validación de formularios, envíos AJAX para formularios de desistimiento, carga dinámica de contenido o interacciones con el botón de desistimiento.
-   `rbfree/views/js/order-history.js`
    *   Ámbito: Front-office (Cuenta de Cliente > Historial de Pedidos)
    *   Detalles: Gestiona específicamente la integración del enlace/botón de desistimiento dentro de la página de historial de pedidos del cliente, potencialmente añadiendo escuchadores de eventos para mostrar/ocultar opciones dinámicamente según el estado del pedido.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `rbfree/views/css/admin-config.css`
    *   Ámbito: Back-office (Configuración del Módulo)
    *   Detalles: Estilos para la página de configuración principal del módulo (`configure.tpl`), asegurando una apariencia consistente dentro del administrador de PrestaShop.
-   `rbfree/views/css/admin-dashboard.css`
    *   Ámbito: Back-office (Panel de control de AdminRbfWithdrawalController)
    *   Detalles: Estilos para la vista del panel de control que lista todas las solicitudes de desistimiento, incluyendo diseños de tabla, indicadores de estado y diseño general.
-   `rbfree/views/css/admin-order-state-picker.css`
    *   Ámbito: Back-office
    *   Detalles: Estilos para la interfaz de selección de estado de pedido utilizada en la configuración del módulo.
-   `rbfree/views/css/admin-pro-teaser.css`
    *   Ámbito: Back-office
    *   Detalles: Estilos para los elementos de avance de la versión "Pro" dentro de la interfaz de administración del módulo gratuito.
-   `rbfree/views/css/admin-searchtool.css`
    *   Ámbito: Back-office
    *   Detalles: Estilos para las herramientas de búsqueda y filtrado dentro de la lista de desistimientos del administrador.
-   `rbfree/views/css/admin-withdrawal-view.css`
    *   Ámbito: Back-office (vista de AdminRbfWithdrawalController)
    *   Detalles: Estilos para la vista detallada de una única solicitud de desistimiento en el administrador, incluyendo notas, historial y listas de productos.
-   `rbfree/views/css/front-classic.css`
    *   Ámbito: Front-office (tema Classic)
    *   Detalles: Ajustes de estilo específicos para el tema Classic de PrestaShop, asegurando la coherencia visual con el diseño del tema.
-   `rbfree/views/css/front-hummingbird.css`
    *   Ámbito: Front-office (tema Hummingbird)
    *   Detalles: Ajustes de estilo específicos para el tema Hummingbird de PrestaShop, asegurando la coherencia visual con el diseño del tema.
-   `rbfree/views/css/front.css`
    *   Ámbito: Front-office
    *   Detalles: Estilo general del front-office para los formularios de desistimiento, botones y páginas de estado, aplicado en todos los temas.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)
-   `rbfree/views/templates/hook/account-link-classic.tpl`
    *   Hook: `displayCustomerAccount` (o similar)
    *   Salidas: Un enlace en el panel de control de la cuenta del cliente para el tema Classic.
-   `rbfree/views/templates/hook/account-link-hummingbird.tpl`
    *   Hook: `displayCustomerAccount` (o similar)
    *   Salidas: Un enlace en el panel de control de la cuenta del cliente para el tema Hummingbird.
-   `rbfree/views/templates/hook/button-classic.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (o similar)
    *   Salidas: El botón principal de desistimiento para el tema Classic.
-   `rbfree/views/templates/hook/button-hummingbird.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (o similar)
    *   Salidas: El botón principal de desistimiento para el tema Hummingbird.
-   `rbfree/views/templates/hook/button.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (o similar)
    *   Salidas: Botón genérico principal de desistimiento, utilizado como reserva o para elementos comunes.
-   `rbfree/views/templates/hook/order-detail-classic.tpl`
    *   Hook: `displayOrderDetail` (o similar)
    *   Salidas: Un enlace/botón de desistimiento dentro de la página de detalles del pedido para el tema Classic.
-   `rbfree/views/templates/hook/order-detail-hummingbird.tpl`
    *   Hook: `displayOrderDetail` (o similar)
    *   Salidas: Un enlace/botón de desistimiento dentro de la página de detalles del pedido para el tema Hummingbird.
-   `rbfree/views/templates/hook/order-detail.tpl`
    *   Hook: `displayOrderDetail` (o similar)
    *   Salidas: Enlace/botón genérico de desistimiento dentro de la página de detalles del pedido.
-   `rbfree/views/templates/hook/order-withdrawal-notice.tpl`
    *   Hook: `displayAdminOrder` (o similar)
    *   Salidas: Un aviso o resumen del estado de desistimiento en la página de vista de pedidos del Back Office.

#### Plantillas de Administración (`views/templates/admin/`)
-   `rbfree/views/templates/admin/configure.tpl`
    *   Utilizado por: `getContent()` en `rbfree/index.php`
    *   Salidas: El formulario de configuración principal del módulo en el Back Office.
-   `rbfree/views/templates/admin/dashboard.tpl`
    *   Utilizado por: `AdminRbfWithdrawalController`
    *   Salidas: La vista del panel de control que lista todas las solicitudes de desistimiento.
-   `rbfree/views/templates/admin/order-state-picker.tpl`
    *   Utilizado por: Configuración del módulo
    *   Salidas: El widget interactivo de selección de estado de pedido.
-   `rbfree/views/templates/admin/order-withdrawal-notice.tpl`
    *   Utilizado por: Hook `displayAdminOrder`
    *   Salidas: Un aviso sobre el estado de desistimiento en la página de vista de pedidos del Back Office.
-   `rbfree/views/templates/admin/pro-teaser-dashboard-intro.tpl`
    *   Utilizado por: `AdminRbfWithdrawalController`
    *   Salidas: Avance introductorio de la versión Pro en el panel de control.
-   `rbfree/views/templates/admin/pro-teaser-dashboard.tpl`
    *   Utilizado por: `AdminRbfWithdrawalController`
    *   Salidas: Avance general de la versión Pro en el panel de control.
-   `rbfree/views/templates/admin/pro-teaser-exclusions.tpl`
    *   Utilizado por: Configuración del módulo
    *   Salidas: Avance de las características de la versión Pro relacionadas con las exclusiones.
-   `rbfree/views/templates/admin/pro-teaser-order-states.tpl`
    *   Utilizado por: Configuración del módulo
    *   Salidas: Avance de las características de la versión Pro relacionadas con los estados de pedido.
-   `rbfree/views/templates/admin/pro-teaser-withdrawal-scope.tpl`
    *   Utilizado por: Configuración del módulo
    *   Salidas: Avance de las características de la versión Pro relacionadas con el alcance del desistimiento.
-   `rbfree/views/templates/admin/pro-teaser.tpl`
    *   Utilizado por: Varias secciones de administración
    *   Salidas: Avance genérico de la versión Pro.
-   `rbfree/views/templates/admin/updates.tpl`
    *   Utilizado por: Configuración del módulo
    *   Salidas: Muestra información sobre las actualizaciones del módulo.
-   `rbfree/views/templates/admin/view.tpl`
    *   Utilizado por: `AdminRbfWithdrawalController`
    *   Salidas: La página de vista detallada de una única solicitud de desistimiento en el Back Office.

#### Plantillas del Front-office (`views/templates/front/`)
-   `rbfree/views/templates/front/confirm_step.tpl`
    *   Utilizado por: `RbfConfirmModuleFrontController`
    *   Salidas: El segundo paso del formulario de desistimiento, para confirmación.
-   `rbfree/views/templates/front/error.tpl`
    *   Utilizado por: Varios controladores frontales
    *   Salidas: Una página de mensaje de error genérico.
-   `rbfree/views/templates/front/form.tpl`
    *   Utilizado por: `RbfFormModuleFrontController`
    *   Salidas: El formulario inicial de solicitud de desistimiento.
-   `rbfree/views/templates/front/print.tpl`
    *   Utilizado por: `RbfPrintModuleFrontController`
    *   Salidas: La versión imprimible del formulario de desistimiento.
-   `rbfree/views/templates/front/status.tpl`
    *   Utilizado por: `RbfStatusModuleFrontController`
    *   Salidas: La página que muestra el estado de una solicitud de desistimiento específica.
-   `rbfree/views/templates/front/success.tpl`
    *   Utilizado por: `RbfConfirmModuleFrontController`
    *   Salidas: Un mensaje de éxito después de que se envía una solicitud de desistimiento.
-   `rbfree/views/templates/front/track.tpl`
    *   Utilizado por: `RbfTrackModuleFrontController`
    *   Salidas: El formulario para que los clientes sigan su solicitud de desistimiento.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos
-   `ps_rbf_withdrawal`: Almacena los detalles principales de la solicitud de desistimiento (id, id_order, id_customer, status, dates, customer info).
-   `ps_rbf_withdrawal_attachment`: Almacena los detalles de cualquier adjunto a una solicitud de desistimiento.
-   `ps_rbf_withdrawal_history`: Almacena un registro de los cambios de estado y otras actualizaciones para cada solicitud de desistimiento.
-   `ps_rbf_withdrawal_note`: Almacena notas internas añadidas por los administradores a una solicitud de desistimiento.
-   `ps_rbf_withdrawal_product`: Almacena los detalles de los productos incluidos en una solicitud de desistimiento.
-   `ps_configuration`: La configuración del módulo se almacena aquí con claves como `RBFREE_ENABLED`, `RBFREE_BUTTON_HOOK`, `RBFREE_ALLOW_GUEST`, etc.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
|---|---|---|
| `displayHeader` | En la sección `<head>` de cada página. | Inyectar CSS/JS, o renderizar el botón de desistimiento si está configurado. |
| `displayLeftColumn` | En la barra lateral izquierda de las páginas aplicables. | Renderizar el botón de desistimiento si está configurado. |
| `displayRightColumn` | En la barra lateral derecha de las páginas aplicables. | Renderizar el botón de desistimiento si está configurado. |
| `displayFooter` | En la sección del pie de página de cada página. | Renderizar el botón de desistimiento si está configurado. |
| `displayProductButtons` | En la página del producto, cerca del botón de añadir al carrito. | Renderizar el botón de desistimiento si está configurado. |
| `displayCustomerAccount` | En el panel de control "Mi Cuenta" del cliente. | Añadir un enlace al formulario de desistimiento. |
| `displayOrderDetail` | En la página de detalles del pedido del cliente. | Añadir un enlace/botón para iniciar el desistimiento de ese pedido específico. |
| `displayAdminOrder` | En la página de vista de pedidos del Back Office. | Mostrar un aviso o resumen de cualquier solicitud de desistimiento asociada. |
| `actionOrderStatusUpdate` | Cuando se cambia el estado de un pedido. | Potencialmente activar acciones como actualizar el estado de desistimiento o enviar notificaciones. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su plantilla. | Encolar archivos CSS y JavaScript del front-office. |
| `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice su plantilla. | Encolar archivos CSS y JavaScript del back-office. |
| `actionModuleInstall` | Durante la instalación del módulo. | Crear tablas de base de datos, establecer la configuración predeterminada. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Eliminar tablas de base de datos, eliminar la configuración. |

## 5. Soporte Oficial y Actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Botón de Devolución Gratuito - Retiro de la UE", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta que pueda tener con respecto a la funcionalidad del módulo.

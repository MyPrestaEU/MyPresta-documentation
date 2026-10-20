---
title: "Botón de Devolución UE – Formulario de Desistimiento Online - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Botón de Devolución UE – Formulario de Desistimiento Online de MyPresta.eu."
sidebar:
  label: "Botón de Devolución UE – Formulario de Desistimiento Online - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo EU Return Button – Online Withdrawal Form en MyPresta.eu](https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/eu-return-button-online-withdrawal-form/)
>
> ---


# Botón de Devolución UE – Formulario de Desistimiento Online

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde controla el comportamiento general y la apariencia del botón y el formulario de devolución.

#### Pestaña de Ajustes Generales

- **Activar Módulo:**

  - **Qué hace este ajuste:** Este es el interruptor maestro para todo el módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El botón de devolución y el formulario de desistimiento online se activan y son visibles para los clientes según sus otras configuraciones.
    - *Cuando está desactivado:* El módulo está completamente desactivado. El botón no aparecerá y los formularios no serán accesibles.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Solo lo desactivaría si desea dejar de ofrecer devoluciones online temporalmente, quizás durante el mantenimiento o un cambio de política.
- **Mostrar Botón de Devolución En:**

  - **Qué hace este ajuste:** Determina dónde aparecerá el botón principal de "Devolución" o "Desistimiento" en el front office de su tienda. Puede seleccionar varias ubicaciones.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está seleccionado (por ejemplo, Cabecera):* Aparecerá un botón en la ubicación elegida, proporcionando un enlace directo al formulario de devolución.
    - *Cuando no está seleccionado:* El botón no aparecerá en esa ubicación específica.
  - **Valor recomendado:** Cabecera y/o Pie de página para un fácil acceso, y Página de Producto para informar a los clientes de antemano.
  - **Escenario / ejemplo de comerciante:** Si desea que los clientes encuentren fácilmente la opción de devolución desde cualquier página, active "Cabecera" y "Pie de página". Si desea enfatizar su política de devolución en las páginas de productos, active "Página de Producto".
- **Texto del Botón:**

  - **Qué hace este ajuste:** Le permite personalizar el texto que se muestra en el botón de devolución.
  - **Efecto de cambiar este ajuste:** El texto del botón cambiará al valor especificado.
  - **Valor recomendado:** "Solicitud de Devolución", "Formulario de Desistimiento Online" o "Iniciar una Devolución".
  - **Escenario / ejemplo de comerciante:** Podría cambiarlo de "Devolución" a "Formulario de Desistimiento" para alinearse con la terminología legal específica de su región.
- **Estado Mínimo del Pedido para Desistimiento:**

  - **Qué hace este ajuste:** Define el estado más temprano del pedido en el que un cliente puede iniciar una solicitud de devolución para un pedido. Los pedidos con un estado inferior a este no serán elegibles.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "Pago aceptado":* Los clientes solo pueden solicitar una devolución una vez que su pago ha sido procesado con éxito.
    - *Cuando se establece en "Enviado":* Los clientes solo pueden solicitar una devolución después de que su pedido haya sido marcado como enviado.
  - **Valor recomendado:** "Pago aceptado" o "Enviado", dependiendo de su política.
  - **Escenario / ejemplo de comerciante:** Si solo acepta devoluciones de artículos que realmente han sido pagados y procesados, establezca esto en "Pago aceptado". Si solo acepta devoluciones de artículos que ya han salido de su almacén, establézcalo en "Enviado".
- **Días Máximos para Desistimiento:**

  - **Qué hace este ajuste:** Establece el número máximo de días después de que se realiza un pedido (o se envía, según su política) durante los cuales un cliente puede enviar una solicitud de devolución.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 14:* Los clientes tienen 14 días desde la fecha del pedido para solicitar una devolución. Después de 14 días, la opción ya no estará disponible para ese pedido.
    - *Cuando se establece en 30:* Los clientes tienen 30 días.
  - **Valor recomendado:** 14 (para el cumplimiento estándar de la UE) o 30 (si ofrece un período de devolución extendido).
  - **Escenario / ejemplo de comerciante:** Para cumplir con el derecho de desistimiento estándar de 14 días de la UE, establezca esto en 14. Si ofrece una política más generosa, puede extenderlo a 30 o más.
- **Permitir Desistimientos de Invitados:**

  - **Qué hace este ajuste:** Determina si los clientes que compraron como invitados (sin crear una cuenta) pueden usar el formulario de desistimiento online.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes invitados pueden acceder al formulario proporcionando su referencia de pedido y dirección de correo electrónico.
    - *Cuando está desactivado:* Solo los clientes registrados que han iniciado sesión pueden iniciar una devolución.
  - **Valor recomendado:** SÍ (para la máxima comodidad del cliente y el cumplimiento de la UE).
  - **Escenario / ejemplo de comerciante:** Habilitar esto asegura que todos los clientes, independientemente de su método de pago, puedan iniciar fácilmente una devolución, lo cual es crucial para el cumplimiento y la satisfacción del cliente.
- **Permitir Archivos Adjuntos:**

  - **Qué hace este ajuste:** Permite a los clientes subir archivos (por ejemplo, fotos de productos dañados, prueba de compra) al enviar su solicitud de devolución.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Aparecerá un campo de carga en el formulario.
    - *Cuando está desactivado:* Los clientes no pueden subir archivos.
  - **Valor recomendado:** SÍ (especialmente para productos donde se pueda necesitar prueba visual de daños o defectos).
  - **Escenario / ejemplo de comerciante:** Si vende artículos frágiles, permitir archivos adjuntos ayuda a los clientes a proporcionar rápidamente pruebas de daños, acelerando el proceso de resolución.
- **Tamaño Máximo de Archivo Adjunto (MB):**

  - **Qué hace este ajuste:** Establece el tamaño máximo de archivo para cada archivo adjunto que un cliente puede subir.
  - **Efecto de cambiar este ajuste:** Los archivos más grandes que este límite serán rechazados por el formulario.
  - **Valor recomendado:** 2-5 MB.
  - **Escenario / ejemplo de comerciante:** Establecer un límite razonable evita que los clientes suban archivos excesivamente grandes que podrían ralentizar su servidor o sistema de correo electrónico.
- **Extensiones de Archivo Adjunto Permitidas (separadas por comas):**

  - **Qué hace este ajuste:** Especifica qué tipos de archivo (por ejemplo, jpg, png, pdf) se permite a los clientes subir.
  - **Efecto de cambiar este ajuste:** Solo se aceptarán archivos con estas extensiones.
  - **Valor recomendado:** jpg, jpeg, png, gif, pdf.
  - **Escenario / ejemplo de comerciante:** Limitar a formatos de imagen y documento comunes asegura que reciba archivos utilizables y previene cargas maliciosas.
- **Requerir Mensaje de Estado:**

  - **Qué hace este ajuste:** Cuando cambia el estado de una solicitud de devolución en el back office, este ajuste determina si se le exige añadir un mensaje al cliente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Un campo de entrada para un mensaje será obligatorio al actualizar un estado de devolución.
    - *Cuando está desactivado:* Puede cambiar los estados sin añadir un mensaje.
  - **Valor recomendado:** SÍ (para una comunicación clara y registros de auditoría).
  - **Escenario / ejemplo de comerciante:** Habilitar esto asegura que su equipo siempre proporcione una razón o actualización al cliente al cambiar el estado, mejorando la transparencia.

#### Pestaña de Estados del Pedido

Esta pestaña le permite definir los diversos estados para las solicitudes de devolución y cómo interactúan con los estados de pedido existentes de PrestaShop.

- **Nuevo Estado de Desistimiento:**

  - **Qué hace este ajuste:** Selecciona el estado de pedido de PrestaShop que se asignará a una nueva solicitud de devolución cuando sea enviada por primera vez por un cliente.
  - **Efecto de cambiar este ajuste:** Todas las nuevas solicitudes de devolución se marcarán automáticamente con este estado en su back office.
  - **Valor recomendado:** Cree un nuevo estado de pedido personalizado como "Devolución Solicitada" o "Desistimiento Pendiente" para una identificación clara.
  - **Escenario / ejemplo de comerciante:** Al crear un estado específico de "Devolución Solicitada", su equipo de atención al cliente puede filtrar e identificar fácilmente las nuevas solicitudes de devolución que necesitan su atención.
- **Estado de Desistimiento Aceptado:**

  - **Qué hace este ajuste:** Selecciona el estado de pedido de PrestaShop que se asignará cuando usted, como comerciante, acepte la solicitud de devolución de un cliente.
  - **Efecto de cambiar este ajuste:** Cuando marque una devolución como "Aceptada" en el módulo, su estado cambiará a este estado de pedido seleccionado.
  - **Valor recomendado:** Cree un nuevo estado de pedido personalizado como "Devolución Aceptada" o "Desistimiento Aprobado".
  - **Escenario / ejemplo de comerciante:** Una vez que haya revisado una solicitud y la haya aprobado, cambiar su estado a "Devolución Aceptada" puede activar un correo electrónico al cliente con más instrucciones.
- **Estado de Desistimiento Rechazado:**

  - **Qué hace este ajuste:** Selecciona el estado de pedido de PrestaShop que se asignará cuando rechace la solicitud de devolución de un cliente.
  - **Efecto de cambiar este ajuste:** Cuando marque una devolución como "Rechazada" en el módulo, su estado cambiará a este estado de pedido seleccionado.
  - **Valor recomendado:** Cree un nuevo estado de pedido personalizado como "Devolución Rechazada" o "Desistimiento Denegado".
  - **Escenario / ejemplo de comerciante:** Si una solicitud de devolución no cumple con su política (por ejemplo, ha pasado el plazo de devolución), cambiaría su estado a "Devolución Rechazada" e idealmente enviaría un mensaje explicando el motivo.
- **Estado de Desistimiento Cerrado:**

  - **Qué hace este ajuste:** Selecciona el estado de pedido de PrestaShop que se asignará cuando una solicitud de devolución se complete o resuelva (por ejemplo, reembolso emitido, reemplazo enviado).
  - **Efecto de cambiar este ajuste:** Cuando marque una devolución como "Cerrada" en el módulo, su estado cambiará a este estado de pedido seleccionado.
  - **Valor recomendado:** Cree un nuevo estado de pedido personalizado como "Devolución Completada" o "Desistimiento Cerrado".
  - **Escenario / ejemplo de comerciante:** Después de que se haya procesado un reembolso, marcar la devolución como "Devolución Completada" proporciona un rastro de auditoría claro y la elimina de su cola de devoluciones activas.
- **Estados de Pedido a Excluir del Desistimiento:**

  - **Qué hace este ajuste:** Le permite seleccionar estados de pedido específicos de PrestaShop para los cuales los clientes *no pueden* iniciar una solicitud de devolución, incluso si cumplen otros criterios.
  - **Efecto de cambiar este ajuste:** Los pedidos con cualquiera de los estados seleccionados no mostrarán la opción de devolución al cliente.
  - **Valor recomendado:** "Cancelado", "Reembolsado", "Error" o cualquier otro estado que signifique que un pedido ya no es elegible para una nueva solicitud de devolución.
  - **Escenario / ejemplo de comerciante:** Si un pedido ya ha sido "Reembolsado", no querría que un cliente pudiera enviar otra solicitud de devolución para él.

### 2.2 Pantallas de Administración Dedicadas y Vistas del Controlador

#### Solicitudes de Desistimiento (Back Office > Pedidos > Solicitudes de Desistimiento)

Este es el centro neurálgico para gestionar todas las solicitudes de devolución y desistimiento enviadas por sus clientes.

- **Nombre de la Pantalla y Ubicación del Menú:** Puede encontrar esta pantalla navegando a **Pedidos > Solicitudes de Desistimiento** en el menú de su back office de PrestaShop.
- **Acciones y Ajustes Disponibles:**
  - **Tabla de Listado:** Muestra una lista completa de todas las solicitudes de devolución, incluyendo:
    - **ID:** Identificador único de la solicitud.
    - **Nombre del Cliente:** El cliente que envió la solicitud.
    - **Referencia del Pedido:** El pedido de PrestaShop asociado.
    - **Fecha:** Cuando se envió la solicitud.
    - **Estado:** El estado actual de la solicitud (por ejemplo, "Devolución Solicitada", "Devolución Aceptada").
    - **Acciones:** Botones para "Ver" los detalles de la solicitud, cambiar su estado o realizar otras tareas de gestión.
  - **Filtrado y Búsqueda:** Puede filtrar la lista por estado, cliente, referencia de pedido y rango de fechas para encontrar rápidamente solicitudes específicas.
  - **Acciones Masivas:** Le permite seleccionar varias solicitudes y realizar acciones como cambiar su estado simultáneamente.
  - **Ver Detalles:** Al hacer clic en "Ver" para una solicitud específica, se abre una página detallada donde puede:
    - Ver toda la información proporcionada por el cliente (motivo, comentarios, archivos adjuntos).
    - Revisar los productos incluidos en la solicitud de devolución.
    - Ver un historial de cambios de estado y notas internas.
    - Añadir notas privadas para la comunicación interna del equipo.
    - Cambiar el estado de la solicitud (por ejemplo, de "Devolución Solicitada" a "Devolución Aceptada").
    - Enviar mensajes al cliente (si "Requerir Mensaje de Estado" está activado).
    - Descargar archivos adjuntos.
    - Imprimir el formulario de desistimiento.
- **Efecto de los cambios:**
  - **Cambiar Estado:** Actualiza el estado de la solicitud de devolución, lo que puede activar notificaciones por correo electrónico al cliente y actualizar la visualización en su cuenta de cliente.
  - **Añadir Notas:** Registra la comunicación interna o las decisiones relacionadas con la solicitud, visible solo para los usuarios del back office.
  - **Enviar Mensajes:** Se comunica directamente con el cliente con respecto a su solicitud de devolución.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Revise regularmente la lista de "Solicitudes de Desistimiento" en busca de nuevas solicitudes (estado "Devolución Solicitada").
  2. Revise cada nueva solicitud, verificando los detalles del pedido, los comentarios del cliente y cualquier archivo adjunto.
  3. Decida si acepta o rechaza la solicitud basándose en la política de devoluciones de su tienda.
  4. Cambie el estado en consecuencia (por ejemplo, a "Devolución Aceptada" o "Devolución Rechazada"). Si "Requerir Mensaje de Estado" está activado, proporcione un mensaje claro al cliente.
  5. Siga los siguientes pasos (por ejemplo, emitir un reembolso, organizar el envío de devolución) y actualice el estado a "Devolución Completada" una vez resuelto.
  6. Utilice notas internas para la comunicación del equipo o para registrar acciones específicas tomadas.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de Configuración del Módulo** | Activar Módulo | SÍ | Activa/desactiva todo el módulo. |
|  | Mostrar Botón de Devolución En | Cabecera, Pie de página, Página de Producto | Controla dónde aparece el botón de devolución en el front office. |
|  | Texto del Botón | "Solicitud de Devolución" | Personaliza el texto del botón de devolución. |
|  | Estado Mínimo del Pedido para Desistimiento | "Pago aceptado" | Establece el estado de pedido más temprano para la elegibilidad de devolución. |
|  | Días Máximos para Desistimiento | 14 | Define el plazo de devolución en días desde la fecha del pedido. |
|  | Permitir Desistimientos de Invitados | SÍ | Permite a los clientes no registrados usar el formulario. |
|  | Permitir Archivos Adjuntos | SÍ | Habilita/deshabilita la carga de archivos en el formulario. |
|  | Tamaño Máximo de Archivo Adjunto (MB) | 2-5 MB | Establece el tamaño máximo para los archivos subidos. |
|  | Extensiones de Archivo Adjunto Permitidas | jpg, jpeg, png, gif, pdf | Especifica los tipos de archivo permitidos para las cargas. |
|  | Requerir Mensaje de Estado | SÍ | Hace que un mensaje sea obligatorio al cambiar el estado de devolución. |
| **Pestaña de Estados del Pedido** | Nuevo Estado de Desistimiento | "Devolución Solicitada" (personalizado) | Estado para las solicitudes recién enviadas. |
|  | Estado de Desistimiento Aceptado | "Devolución Aceptada" (personalizado) | Estado cuando el comerciante aprueba una solicitud. |
|  | Estado de Desistimiento Rechazado | "Devolución Rechazada" (personalizado) | Estado cuando el comerciante rechaza una solicitud. |
|  | Estado de Desistimiento Cerrado | "Devolución Completada" (personalizado) | Estado cuando una solicitud está completamente resuelta. |
|  | Estados de Pedido a Excluir del Desistimiento | "Cancelado", "Reembolsado" | Evita devoluciones para pedidos con estos estados. |
| **Solicitudes de Desistimiento (Admin)** | Ver/Editar Solicitud | N/A | Gestionar solicitudes de devolución individuales, cambiar estado, añadir notas. |
|  | Filtrar/Buscar | N/A | Localizar solicitudes específicas por varios criterios. |
|  | Acciones Masivas | N/A | Realizar acciones en varias solicitudes seleccionadas. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: El botón de devolución no aparece en mi tienda. ¿Qué debo hacer?**
R1:

- **Verificar el Estado del Módulo:** Vaya a **Módulos > Gestor de Módulos**, busque "Botón de Devolución UE – Formulario de Desistimiento Online" y asegúrese de que esté "Activado".
- **Verificar Ubicaciones de Visualización:** En la configuración del módulo, en la pestaña "Ajustes Generales", verifique que haya seleccionado al menos una ubicación en "Mostrar Botón de Devolución En" (por ejemplo, Cabecera, Pie de página).
- **Borrar Caché:** Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, el contenido antiguo en caché impide que aparezcan nuevos elementos del módulo.
- **Compatibilidad del Tema:** Aunque el módulo está diseñado para una amplia compatibilidad, los temas personalizados pueden requerir ajustes menores. Si el botón aún no aparece, póngase en contacto con el soporte de MyPresta.eu con detalles sobre su tema.

**P2: Los clientes informan que no pueden enviar una devolución para un pedido específico, aunque esté dentro del período de devolución.**
R2:

- **Verificar el Estado Mínimo del Pedido:** En la configuración del módulo, en "Ajustes Generales", revise "Estado Mínimo del Pedido para Desistimiento". Asegúrese de que el pedido del cliente haya alcanzado este estado. Por ejemplo, si está configurado en "Enviado" y el pedido aún está en "Pago aceptado", no verán la opción.
- **Verificar Estados de Pedido Excluidos:** En la configuración del módulo, en la pestaña "Estados del Pedido", verifique "Estados de Pedido a Excluir del Desistimiento". Si el pedido del cliente tiene uno de estos estados (por ejemplo, "Cancelado", "Reembolsado"), no podrá iniciar una nueva devolución.
- **Días Máximos para Desistimiento:** Vuelva a verificar el ajuste "Días Máximos para Desistimiento". El plazo de devolución podría haber expirado para ese pedido específico.

**P3: Cambié un ajuste, pero no se refleja en el front office.**
R3:

- **Borrar Caché:** Esta es la razón más común. Siempre borre la caché de su PrestaShop después de realizar cambios de configuración en cualquier módulo. Navegue a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché". Si utiliza un módulo de caché de terceros o CDN, borre también sus cachés.
- **Caché del Navegador:** Pida a sus clientes (o a usted mismo) que borren la caché de su navegador o intenten ver la página en una ventana de incógnito/privada para descartar problemas de caché del lado del navegador.

**P4: ¿Cómo traduzco el texto del módulo a otros idiomas?**
R4:

- Vaya a **Internacional > Traducciones** en su back office de PrestaShop.
- Seleccione "Traducciones de módulos instalados".
- Elija su tema, el idioma al que desea traducir y luego seleccione "Botón de Devolución UE – Formulario de Desistimiento Online" de la lista de módulos.
- A continuación, verá una lista de todas las cadenas traducibles dentro del módulo, incluyendo el texto del botón, las etiquetas del formulario y los mensajes. Introduzca sus traducciones y guarde.

**P5: Quiero personalizar la apariencia del formulario de devolución para que coincida con mi tema.**
R5:

- El módulo incluye archivos CSS (`front-classic.css`, `front-hummingbird.css`, `front.css`) diseñados para temas comunes de PrestaShop.
- Para un estilo avanzado, necesitará un desarrollador web. Pueden inspeccionar la estructura HTML del módulo y anular sus reglas CSS en el archivo `custom.css` de su tema o creando una nueva hoja de estilos que se cargue después del CSS del módulo. Evite editar directamente los archivos CSS del módulo, ya que sus cambios se perderán durante las actualizaciones.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo "Botón de Devolución UE – Formulario de Desistimiento Online" (`rbpro`) sigue la arquitectura MVC (Modelo-Vista-Controlador) estándar de PrestaShop. Utiliza `ModuleFrontController` para las interacciones con el cliente y `AdminController` para la gestión del back office. La lógica de negocio central está encapsulada en clases de servicio y ObjectModel dedicadas, lo que garantiza la integridad de los datos y la separación de preocupaciones. El módulo se integra con el sistema de hooks de PrestaShop para la inyección dinámica de contenido y utiliza Smarty para la creación de plantillas. También incluye capas de compatibilidad para diferentes versiones de PrestaShop y una clase de seguridad para la validación de entradas.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

Estos controladores gestionan las interacciones del cliente relacionadas con el formulario de devolución y el seguimiento del estado.

- `rbpro/controllers/front/confirm.php`

  - **Nombre de la Clase:** `RbpConfirmModuleFrontController` (extiende `RbpModuleFrontController`)
  - **Responsabilidad:** Muestra el paso final de confirmación del formulario de desistimiento. Procesa los datos del formulario enviado, crea la entrada `RbpWithdrawal` y redirige a la página de éxito o error. Maneja la validación de datos antes de guardar.
- `rbpro/controllers/front/form.php`

  - **Nombre de la Clase:** `RbpFormModuleFrontController` (extiende `RbpModuleFrontController`)
  - **Responsabilidad:** Renderiza el formulario principal de desistimiento online. Maneja la visualización inicial de pedidos/productos elegibles, procesa las selecciones del usuario y prepara los datos para el paso de confirmación. Gestiona el acceso de invitados a través de la referencia del pedido y el correo electrónico.
- `rbpro/controllers/front/print.php`

  - **Nombre de la Clase:** `RbpPrintModuleFrontController` (extiende `RbpModuleFrontController`)
  - **Responsabilidad:** Proporciona una versión imprimible del formulario de desistimiento o los detalles de la solicitud. Normalmente utilizado por los clientes para incluirlo con su paquete devuelto.
- `rbpro/controllers/front/RbpModuleFrontController.php`

  - **Nombre de la Clase:** `RbpModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Esta es una clase base para todos los controladores del front office dentro del módulo `rbpro`. Proporciona funcionalidades comunes como la configuración de migas de pan, la gestión de activos específicos del módulo y, potencialmente, comprobaciones de seguridad compartidas o inicialización de datos.
- `rbpro/controllers/front/status.php`

  - **Nombre de la Clase:** `RbpStatusModuleFrontController` (extiende `RbpModuleFrontController`)
  - **Responsabilidad:** Muestra el estado actual y el historial de una solicitud de devolución específica al cliente. Accesible a través de un enlace de seguimiento único o desde la cuenta del cliente.
- `rbpro/controllers/front/track.php`

  - **Nombre de la Clase:** `RbpTrackModuleFrontController` (extiende `RbpModuleFrontController`)
  - **Responsabilidad:** Proporciona una interfaz simple para que los clientes (especialmente los invitados) introduzcan una referencia de pedido y un correo electrónico para rastrear el estado de su solicitud de desistimiento.

#### Controladores de Administración del Back-Office

- `rbpro/controllers/admin/AdminRbpWithdrawalController.php`
  - **Nombre de la Clase:** `AdminRbpWithdrawalController` (extiende `ModuleAdminController`)
  - **Nombre de la Pestaña:** "Solicitudes de Desistimiento" (bajo "Pedidos")
  - **Entidad Gestionada:** `RbpWithdrawal`
  - **Responsabilidad:** Gestiona el listado, visualización, edición y actualización de estado de todas las solicitudes de desistimiento de clientes en el back office de PrestaShop. Implementa `renderList()` para la tabla de resumen y `renderForm()` para la vista detallada de una única solicitud. Maneja acciones como cambiar el estado, añadir notas y gestionar archivos adjuntos.

### 4.3 Clases y Modelos Principales (`classes/`)

- `rbpro/classes/index.php`

  - **Responsabilidad:** Archivo `index.php` vacío estándar para evitar el listado de directorios.
- `rbpro/classes/RbpCompatibility.php`

  - **Responsabilidad:** Proporciona métodos estáticos para manejar problemas de compatibilidad entre diferentes versiones de PrestaShop (por ejemplo, lógica específica de `_PS_VERSION_`, reemplazos de funciones obsoletas). Asegura que el módulo funcione correctamente desde PS 1.6 hasta 9.x.
- `rbpro/classes/RbpSecurity.php`

  - **Responsabilidad:** Contiene métodos estáticos para tareas relacionadas con la seguridad, como la validación de entradas, la sanitización y, potencialmente, la generación/verificación de tokens CSRF para formularios específicos del módulo.
- `rbpro/classes/RbpStatsService.php`

  - **Responsabilidad:** Una clase de servicio responsable de recopilar y, potencialmente, procesar estadísticas relacionadas con las solicitudes de desistimiento (por ejemplo, número de solicitudes, tiempo medio de procesamiento).
- `rbpro/classes/RbpWithdrawal.php`

  - **Extiende:** `ObjectModel`
  - **Tabla de Base de Datos:** `rbp_withdrawal`
  - **Campos `$definition`:** Define la estructura de una solicitud de desistimiento, incluyendo campos como `id_customer`, `id_order`, `id_order_state`, `reference`, `email`, `date_add`, `date_upd`, `status`, `reason`, `message`, etc.
  - **Métodos Públicos Clave:** Métodos para operaciones CRUD en solicitudes de desistimiento, recuperación de productos asociados, historial y notas.
- `rbpro/classes/RbpWithdrawalAttachment.php`

  - **Extiende:** `ObjectModel`
  - **Tabla de Base de Datos:** `rbp_withdrawal_attachment`
  - **Campos `$definition`:** Define la estructura para los archivos adjuntos vinculados a una solicitud de desistimiento, incluyendo `id_rbp_withdrawal`, `filename`, `original_filename`, `mime_type`, `date_add`.
  - **Métodos Públicos Clave:** Métodos para gestionar archivos adjuntos (subir, recuperar, eliminar).
- `rbpro/classes/RbpWithdrawalHistory.php`

  - **Extiende:** `ObjectModel`
  - **Tabla de Base de Datos:** `rbp_withdrawal_history`
  - **Campos `$definition`:** Define el historial de cambios de estado para una solicitud de desistimiento, incluyendo `id_rbp_withdrawal`, `id_order_state`, `id_employee`, `message`, `date_add`.
  - **Métodos Públicos Clave:** Métodos para registrar y recuperar cambios de estado y mensajes asociados.
- `rbpro/classes/RbpWithdrawalNote.php`

  - **Extiende:** `ObjectModel`
  - **Tabla de Base de Datos:** `rbp_withdrawal_note`
  - **Campos `$definition`:** Define las notas internas añadidas por los empleados a una solicitud de desistimiento, incluyendo `id_rbp_withdrawal`, `id_employee`, `note`, `date_add`.
  - **Métodos Públicos Clave:** Métodos para añadir y recuperar notas internas.
- `rbpro/classes/RbpWithdrawalProduct.php`

  - **Extiende:** `ObjectModel`
  - **Tabla de Base de Datos:** `rbp_withdrawal_product`
  - **Campos `$definition`:** Define los productos específicos incluidos en una solicitud de desistimiento, vinculando a `id_rbp_withdrawal`, `id_order_detail`, `id_product`, `id_product_attribute`, `quantity`, `reason`.
  - **Métodos Públicos Clave:** Métodos para gestionar la lista de productos dentro de una solicitud de devolución.
- `rbpro/classes/RbpWithdrawalService.php`

  - **Responsabilidad:** Una clase de capa de servicio que orquesta la lógica de negocio compleja que involucra múltiples ObjectModels relacionados con `RbpWithdrawal`. Ejemplos incluyen la creación de una nueva solicitud de desistimiento (que involucra `RbpWithdrawal`, `RbpWithdrawalProduct`, `RbpWithdrawalHistory`), la actualización de su estado, el envío de notificaciones por correo electrónico y la gestión de archivos adjuntos.

### 4.4 Activos JavaScript (`views/js/`)

- `rbpro/lib/searchTool/views/js/autocomplete.js`

  - **Alcance:** Back-office (probablemente para buscar pedidos/clientes en formularios de administración).
  - **Detalles:** Implementa la funcionalidad de autocompletado para campos de entrada, típicamente para buscar clientes u pedidos al crear/editar solicitudes de desistimiento manualmente en el back office. Se vincula a eventos `keyup` y realiza llamadas AJAX para obtener sugerencias.
- `rbpro/views/js/admin-order-state-picker.js`

  - **Alcance:** Back-office (configuración del módulo y AdminRbpWithdrawalController).
  - **Detalles:** Mejora los desplegables de selección de estado de pedido en la configuración del módulo y, potencialmente, en la vista detallada de desistimiento. Puede añadir señales visuales o capacidades de filtrado.
- `rbpro/views/js/front.js`

  - **Alcance:** Front-office (formularios de desistimiento y páginas de estado).
  - **Detalles:** Maneja las interacciones del lado del cliente en el formulario de desistimiento, como:
    - Selección dinámica de productos basada en el pedido.
    - Validación de campos del formulario antes del envío.
    - Llamadas AJAX para el envío del formulario o la carga de datos.
    - Visualización de mensajes o gestión de cargas de archivos.
- `rbpro/views/js/order-history.js`

  - **Alcance:** Front-office (cuenta de cliente > historial de pedidos).
  - **Detalles:** Integra el botón o enlace "Solicitar Devolución" en la página de historial de pedidos del cliente. Puede usar AJAX para verificar la elegibilidad del pedido o mostrar/ocultar dinámicamente el botón.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `rbpro/lib/searchTool/views/css/autocomplete.css`

  - **Alcance:** Back-office.
  - **Detalles:** Estilos para los desplegables de autocompletado y los campos de entrada de búsqueda utilizados en el panel de administración.
- `rbpro/views/css/admin-config.css`

  - **Alcance:** Back-office (página de configuración del módulo).
  - **Detalles:** Estilos para el formulario de configuración principal del módulo, incluyendo pestañas, campos de entrada y diseño general.
- `rbpro/views/css/admin-dashboard.css`

  - **Alcance:** Back-office (potencialmente para un panel de control o vista de estadísticas del módulo).
  - **Detalles:** Estilos para cualquier elemento de panel de control personalizado o visualización estadística dentro de la interfaz de administración del módulo.
- `rbpro/views/css/admin-order-state-picker.css`

  - **Alcance:** Back-office.
  - **Detalles:** Estilos específicos para los elementos mejorados de selección de estado de pedido en el administrador.
- `rbpro/views/css/admin-searchtool.css`

  - **Alcance:** Back-office.
  - **Detalles:** Estilos generales para las herramientas de búsqueda y los componentes de filtrado dentro de la interfaz de administración.
- `rbpro/views/css/admin-withdrawal-view.css`

  - **Alcance:** Back-office (vista detallada de AdminRbpWithdrawalController).
  - **Detalles:** Estilos para la vista detallada de una única solicitud de desistimiento, incluyendo secciones para información del cliente, productos, historial y notas.
- `rbpro/views/css/front-classic.css`

  - **Alcance:** Front-office (para compatibilidad con el tema Classic).
  - **Detalles:** Ajustes de estilo específicos para el formulario de desistimiento y los botones para integrarse perfectamente con el tema Classic de PrestaShop.
- `rbpro/views/css/front-hummingbird.css`

  - **Alcance:** Front-office (para compatibilidad con el tema Hummingbird).
  - **Detalles:** Ajustes de estilo específicos para el formulario de desistimiento y los botones para integrarse perfectamente con el tema Hummingbird de PrestaShop.
- `rbpro/views/css/front.css`

  - **Alcance:** Front-office (estilo general).
  - **Detalles:** CSS principal para el formulario de desistimiento del front office, botones y páginas de estado, proporcionando un estilo base que puede ser anulado por hojas de estilo específicas del tema.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

Estas plantillas se renderizan cuando el módulo se engancha en puntos de visualización específicos.

- `rbpro/views/templates/hook/account-link-classic.tpl`

  - **Hook:** `displayCustomerAccount` (o similar)
  - **Salidas:** Un enlace en la sección "Mi cuenta" del cliente para el tema Classic, que lleva al formulario de desistimiento o a la página de seguimiento.
- `rbpro/views/templates/hook/account-link-hummingbird.tpl`

  - **Hook:** `displayCustomerAccount` (o similar)
  - **Salidas:** Un enlace en la sección "Mi cuenta" del cliente para el tema Hummingbird.
- `rbpro/views/templates/hook/button-classic.tpl`

  - **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (o similar)
  - **Salidas:** El botón principal de "Devolución" o "Desistimiento", con estilo para el tema Classic.
- `rbpro/views/templates/hook/button-hummingbird.tpl`

  - **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (o similar)
  - **Salidas:** El botón principal de "Devolución" o "Desistimiento", con estilo para el tema Hummingbird.
- `rbpro/views/templates/hook/button.tpl`

  - **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (o similar)
  - **Salidas:** Un botón genérico de "Devolución" o "Desistimiento", utilizado como respaldo o base para botones específicos del tema.
- `rbpro/views/templates/hook/order-detail-classic.tpl`

  - **Hook:** `displayOrderDetail` (o similar)
  - **Salidas:** Una opción o botón en la página de detalles de pedido individual del cliente para el tema Classic, que le permite iniciar una devolución para ese pedido específico.
- `rbpro/views/templates/hook/order-detail-hummingbird.tpl`

  - **Hook:** `displayOrderDetail` (o similar)
  - **Salidas:** Una opción o botón en la página de detalles de pedido individual del cliente para el tema Hummingbird.
- `rbpro/views/templates/hook/order-detail.tpl`

  - **Hook:** `displayOrderDetail` (o similar)
  - **Salidas:** Una opción o botón genérico en la página de detalles de pedido individual del cliente.
- `rbpro/views/templates/hook/order-withdrawal-notice.tpl`

  - **Hook:** `displayAdminOrder` (o similar)
  - **Salidas:** Un aviso o resumen de las solicitudes de desistimiento relacionadas con un pedido específico, que se muestra dentro de la vista de pedidos de administración de PrestaShop.

#### Plantillas de administración (`views/templates/admin/`)

Estas plantillas se utilizan para la interfaz de back office del módulo.

- `rbpro/lib/searchTool/views/scripts.tpl`

  - **Salidas:** Inclusiones de JavaScript y CSS para la biblioteca de herramientas de búsqueda, típicamente incluidas en formularios de administración que usan autocompletado.
- `rbpro/views/templates/admin/configure.tpl`

  - **Salidas:** El formulario de configuración principal del módulo, renderizado por `getContent()` en `index.php`. Contiene todos los ajustes descritos en la sección 4.1.
- `rbpro/views/templates/admin/dashboard.tpl`

  - **Salidas:** Un panel de control o vista de resumen para el módulo, que potencialmente muestra estadísticas o solicitudes de desistimiento recientes.
- `rbpro/views/templates/admin/order-state-picker.tpl`

  - **Salidas:** Una plantilla personalizada para seleccionar estados de pedido, utilizada en la configuración del módulo o en la vista de desistimiento de administración.
- `rbpro/views/templates/admin/order-withdrawal-notice.tpl`

  - **Salidas:** Un pequeño widget o aviso que se muestra dentro de la página de detalles del pedido de PrestaShop en el back office, indicando si hay una solicitud de desistimiento activa para ese pedido.
- `rbpro/views/templates/admin/updates.tpl`

  - **Salidas:** Una plantilla para mostrar notificaciones de actualización del módulo o registros de cambios dentro de la interfaz de administración.
- `rbpro/views/templates/admin/view.tpl`

  - **Salidas:** La plantilla de vista detallada para una única solicitud de desistimiento, renderizada por `AdminRbpWithdrawalController::renderForm()`. Muestra todos los detalles de la solicitud, productos, historial, notas y opciones de cambio de estado.

#### Plantillas del front-office (`views/templates/front/`)

Estas son plantillas de página independientes para el proceso de desistimiento orientado al cliente.

- `rbpro/views/templates/front/confirm_step.tpl`

  - **Salidas:** El paso de confirmación del formulario de desistimiento, que resume las selecciones del cliente antes del envío final.
- `rbpro/views/templates/front/error.tpl`

  - **Salidas:** Una página de error genérica que se muestra si algo sale mal durante el proceso de desistimiento (por ejemplo, pedido no válido, problema técnico).
- `rbpro/views/templates/front/form.tpl`

  - **Salidas:** El formulario principal de solicitud de desistimiento online, que permite a los clientes seleccionar pedidos, productos y proporcionar detalles.
- `rbpro/views/templates/front/print.tpl`

  - **Salidas:** Una versión imprimible de la solicitud de desistimiento, típicamente un diseño simplificado sin navegación.
- `rbpro/views/templates/front/status.tpl`

  - **Salidas:** La página que muestra el estado actual y el historial de una solicitud de desistimiento específica.
- `rbpro/views/templates/front/success.tpl`

  - **Salidas:** Una página de mensaje de éxito que se muestra después de que una solicitud de desistimiento ha sido enviada con éxito.
- `rbpro/views/templates/front/track.tpl`

  - **Salidas:** El formulario donde los clientes pueden introducir su referencia de pedido y correo electrónico para rastrear una solicitud de desistimiento.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

El módulo crea y gestiona varias tablas personalizadas:

- `ps_rbp_withdrawal`: Almacena los detalles principales de la solicitud de desistimiento (cliente, pedido, estado, motivo, etc.).
- `ps_rbp_withdrawal_attachment`: Almacena detalles sobre los archivos subidos por los clientes para una solicitud de desistimiento.
- `ps_rbp_withdrawal_history`: Registra todos los cambios de estado y los mensajes asociados para cada solicitud de desistimiento.
- `ps_rbp_withdrawal_note`: Almacena notas internas añadidas por los empleados a una solicitud de desistimiento.
- `ps_rbp_withdrawal_product`: Vincula productos específicos de un pedido a una solicitud de desistimiento, incluyendo cantidad y motivo.

Los registros de configuración se almacenan en `ps_configuration` con claves típicamente prefijadas con `RBP_` (por ejemplo, `RBP_ALLOW_GUEST_WITHDRAWAL`, `RBP_MIN_ORDER_STATUS`).

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyectar CSS/JS, mostrar botón de devolución (si está configurado). |
| `displayFooter` | En el pie de página de cada página. | Mostrar botón de devolución (si está configurado). |
| `displayLeftColumn` | En la columna izquierda de las páginas. | Mostrar botón de devolución (si está configurado). |
| `displayRightColumn` | En la columna derecha de las páginas. | Mostrar botón de devolución (si está configurado). |
| `displayProductButtons` | En la página del producto, cerca del botón de añadir al carrito. | Mostrar botón de devolución (si está configurado). |
| `displayCustomerAccount` | En la página "Mi cuenta" del cliente. | Añadir un enlace al formulario de desistimiento/seguimiento. |
| `displayOrderDetail` | En la página de detalles de pedido individual del cliente. | Añadir una opción para solicitar una devolución para ese pedido. |
| `displayAdminOrder` | En el back office de PrestaShop, en la página de detalles del pedido. | Mostrar un aviso o resumen de las solicitudes de desistimiento relacionadas. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Potencialmente registrar detalles del pedido para futuras comprobaciones de elegibilidad de desistimiento. |
| `actionOrderStatusUpdate` | Después de que el estado de un pedido ha sido cambiado. | Comprobar si el estado del pedido afecta la elegibilidad de desistimiento o activar notificaciones. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su contenido. | Cargar activos CSS y JavaScript específicos del front office. |
| `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice su contenido. | Cargar activos CSS y JavaScript específicos del back office. |
| `actionModuleInstall` | Durante la instalación del módulo. | Crear tablas de base de datos, establecer valores de configuración predeterminados. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Eliminar tablas de base de datos, limpiar valores de configuración. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y cualquier pregunta relacionada con el módulo "Botón de Devolución UE – Formulario de Desistimiento Online", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte y desarrolladores están disponibles para ayudarle con cualquier problema o consulta.

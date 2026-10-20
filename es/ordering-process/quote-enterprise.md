---
title: "Quote Enterprise - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Quote Enterprise para PrestaShop de MyPresta.eu."
sidebar:
  label: "Quote Enterprise - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Quote Enterprise en MyPresta.eu](https://mypresta.eu/modules/ordering-process/quote-enterprise.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/quote-enterprise/)
>
> ---


# Quote Enterprise

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL). Asegúrate de que tu servidor cumpla con los requisitos mínimos de PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Quote Enterprise)

Esta es la pantalla de configuración principal donde defines el comportamiento central y la apariencia del módulo Quote Enterprise.

#### Pestaña de Configuración General

- **Habilitar Quote Enterprise:**

  - **Qué hace este ajuste:** Este es el interruptor maestro para todo el módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El sistema de cotizaciones se activa en tu tienda y los clientes pueden empezar a solicitar cotizaciones.
    - *Cuando está deshabilitado:* Toda la funcionalidad de cotizaciones se oculta del front office y no se pueden solicitar nuevas cotizaciones. Las cotizaciones existentes en el back office siguen siendo accesibles para su gestión.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo del comerciante:** Habilítalo cuando estés listo para ofrecer servicios de cotización. Desactívalo temporalmente durante el mantenimiento o si decides dejar de ofrecer cotizaciones.
- **Permitir Solicitudes de Cotización desde el Carrito:**

  - **Qué hace este ajuste:** Determina si los clientes pueden convertir todo su carrito de compras en una solicitud de cotización.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Un botón o enlace "Solicitar una Cotización" aparecerá en el resumen del carrito de compras, permitiendo a los clientes enviar todos los artículos de su carrito para una cotización.
    - *Cuando está deshabilitado:* Los clientes solo pueden solicitar cotizaciones desde páginas de productos individuales o a través del botón flotante (si está habilitado), no directamente desde su carrito.
  - **Valor recomendado:** SÍ (para la mayoría de los escenarios B2B y de pedidos al por mayor)
  - **Escenario / ejemplo del comerciante:** Si principalmente tratas con pedidos grandes de varios artículos donde el precio a menudo se negocia, habilita esto. Si tus cotizaciones suelen ser para productos únicos y personalizados, podrías deshabilitarlo.
- **Permitir Solicitudes de Cotización desde la Página de Producto:**

  - **Qué hace este ajuste:** Controla si aparece un botón "Solicitar una Cotización" en las páginas de productos individuales.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes pueden añadir un producto específico a una solicitud de cotización directamente desde su página, en lugar de añadirlo al carrito.
    - *Cuando está deshabilitado:* La opción de solicitud de cotización se elimina de las páginas de productos.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo del comerciante:** Esencial para productos personalizados, artículos de alto valor o cuando deseas ofrecer una alternativa a la compra directa para cualquier producto.
- **Mostrar Botón Flotante de Cotización:**

  - **Qué hace este ajuste:** Añade un botón flotante persistente al front office de tu tienda, permitiendo a los clientes iniciar una solicitud de cotización desde casi cualquier página.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un pequeño botón clicable (a menudo en una esquina de la pantalla), abriendo el formulario de solicitud de cotización o una lista de cotizaciones existentes.
    - *Cuando está deshabilitado:* El botón flotante no será visible.
  - **Valor recomendado:** SÍ (para alta visibilidad y facilidad de acceso)
  - **Escenario / ejemplo del comerciante:** Utiliza esto para hacer que la opción de cotización sea altamente visible en toda tu tienda, fomentando más solicitudes.
- **Valor Mínimo del Pedido para la Solicitud de Cotización:**

  - **Qué hace este ajuste:** Establece un valor total mínimo (en tu moneda predeterminada) que una solicitud de cotización debe cumplir para ser enviada.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un valor (por ejemplo, 100):* Los clientes no pueden enviar una solicitud de cotización si el valor total de los artículos en su solicitud es inferior a esta cantidad. Se mostrará un mensaje de error.
    - *Cuando se establece en 0 o se deja vacío:* No se aplica ningún valor mínimo.
  - **Valor recomendado:** 0 (o un valor que filtre solicitudes triviales)
  - **Escenario / ejemplo del comerciante:** Si solo deseas procesar cotizaciones para pedidos significativos, establece un valor mínimo (por ejemplo, $500) para reducir la carga administrativa de las solicitudes pequeñas.
- **Validez Predeterminada de la Cotización (Días):**

  - **Qué hace este ajuste:** Define cuántos días será válida una cotización recién creada, por defecto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un número (por ejemplo, 30):* Todas las nuevas cotizaciones creadas por tu equipo tendrán automáticamente una fecha de vencimiento 30 días después de su creación.
    - *Cuando se establece en 0 o se deja vacío:* Las cotizaciones no tendrán un período de validez predeterminado, y tu equipo deberá establecerlo manualmente o gestionarlas sin vencimiento.
  - **Valor recomendado:** 30 (o un período típico para tu industria)
  - **Escenario / ejemplo del comerciante:** Establecer una validez de 30 días anima a los clientes a actuar dentro de un plazo razonable y te protege de las fluctuaciones de precios.

#### Pestaña de Plantillas de Correo Electrónico

Esta sección te permite personalizar las notificaciones por correo electrónico enviadas por el módulo.

- **Gestor de Plantillas de Correo Electrónico:**
  - **Qué hace este ajuste:** Proporciona una interfaz visual para editar el contenido de varias plantillas de correo electrónico relacionadas con las cotizaciones (por ejemplo, nueva solicitud de cotización, cotización actualizada, cotización aceptada).
  - **Efecto de cambiar este ajuste:**
    - *Cuando editas una plantilla:* El correo electrónico correspondiente enviado a los clientes o a tu equipo reflejará tus cambios, incluyendo texto, marca y diseño.
  - **Valor recomendado:** Personaliza para que coincida con la voz de tu marca y proporciona instrucciones claras.
  - **Escenario / ejemplo del comerciante:** Cambia el correo electrónico de "Nueva Solicitud de Cotización" para incluir instrucciones específicas para tu equipo de ventas o añade un saludo personalizado para los clientes.

#### Pestaña de Configuración Avanzada

- **Habilitar REST API:**

  - **Qué hace este ajuste:** Activa una interfaz programática (API) para el módulo, permitiendo que sistemas externos o aplicaciones personalizadas interactúen con tus cotizaciones.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El módulo expone puntos finales que pueden ser utilizados por los desarrolladores para crear, leer, actualizar y eliminar cotizaciones programáticamente.
    - *Cuando está deshabilitado:* La API está inactiva y no se puede acceder a ella.
  - **Valor recomendado:** NO (a menos que tengas necesidades de integración específicas)
  - **Escenario / ejemplo del comerciante:** Si te integras con un CRM, ERP o una aplicación móvil personalizada, habilitar la API permite que estos sistemas creen o actualicen automáticamente cotizaciones en PrestaShop. Requiere experiencia de desarrollador.
- **Gestión de Claves API:**

  - **Qué hace este ajuste:** Te permite generar y gestionar claves API, que son necesarias para autenticar las solicitudes a la REST API del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando creas una clave:* Obtienes un identificador único que las aplicaciones externas deben usar para acceder a la API.
    - *Cuando revocas una clave:* Cualquier aplicación que use esa clave perderá el acceso a la API.
  - **Valor recomendado:** Genera claves solo cuando sea necesario para integraciones específicas.
  - **Escenario / ejemplo del comerciante:** Crea una nueva clave API para que tu sistema CRM envíe nuevos clientes potenciales como solicitudes de cotización a PrestaShop.
- **URL de Tarea Cron para Vencimiento y Resumen:**

  - **Qué hace este ajuste:** Proporciona una URL que, al ser accedida, activa tareas en segundo plano como la comprobación de vencimientos de cotizaciones y el envío de resúmenes diarios a tu equipo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se configura en tu servidor:* El módulo realizará automáticamente estas tareas a intervalos regulares (por ejemplo, diariamente), asegurando que las cotizaciones se marquen como vencidas y tu equipo reciba resúmenes oportunos.
    - *Cuando no se configura:* Las comprobaciones de vencimiento y los correos electrónicos de resumen no se automatizarán.
  - **Valor recomendado:** Configura esta URL como una tarea cron diaria en tu servidor de alojamiento.
  - **Escenario / ejemplo del comerciante:** Configura una tarea cron para ejecutar esta URL una vez al día para asegurar que los clientes sean notificados de las cotizaciones que vencen y tu equipo de ventas reciba un resumen diario de las nuevas solicitudes.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 Gestión de Cotizaciones (Back Office > Quote Enterprise > Cotizaciones)

Este es el centro neurálgico para que tu equipo de ventas gestione todas las solicitudes de cotización.

- **Nombre de la Pantalla y Ubicación del Menú:** **Quote Enterprise > Cotizaciones**
- **Acciones y Configuraciones Disponibles:**
  - **Tabla de Lista de Cotizaciones:** Muestra todas las cotizaciones enviadas con información clave como el nombre del cliente, el estado, el valor total y la fecha de creación.
  - **Filtrado y Búsqueda:** Herramientas para encontrar cotizaciones específicas por cliente, estado, rango de fechas, etc.
  - **Ver/Editar Cotización:** Haz clic en cualquier cotización para abrir una vista detallada donde puedes:
    - **Ajustar Productos y Cantidades:** Modifica los artículos, cantidades y precios dentro de la cotización.
    - **Añadir/Eliminar Productos:** Busca y añade nuevos productos a la cotización o elimina los existentes.
    - **Aplicar Descuentos:** Ofrece descuentos específicos sobre el total de la cotización o artículos individuales.
    - **Establecer Validez:** Define la fecha de vencimiento de la cotización.
    - **Añadir Notas/Mensajes:** Comunícate con el cliente directamente a través de la interfaz de cotización.
    - **Cambiar Estado:** Actualiza el estado de la cotización (por ejemplo, Pendiente, Enviada, Aceptada, Rechazada, Vencida).
    - **Generar PDF:** Crea una factura proforma profesional en PDF para el cliente.
    - **Convertir a Pedido:** Con un solo clic, convierte una cotización aceptada en un pedido estándar de PrestaShop, listo para el pago.
    - **Enviar Correo Electrónico:** Envía detalles de cotización actualizados o mensajes al cliente.
  - **Acciones Masivas:** Selecciona varias cotizaciones para realizar acciones como cambiar el estado, eliminar o exportar.
- **Efecto de los cambios:**
  - Modificar una cotización actualiza sus detalles en la base de datos y puede activar notificaciones por correo electrónico al cliente.
  - Convertir a pedido crea un nuevo pedido en el sistema de gestión de pedidos estándar de PrestaShop, pre-rellenado con los artículos y precios cotizados.
  - Cambiar el estado actualiza la vista del cliente en su cuenta y puede activar plantillas de correo electrónico específicas.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Revisa regularmente la lista de "Cotizaciones" en busca de nuevas solicitudes "Pendientes".
  2. Abre cada nueva solicitud, revisa los artículos, ajusta precios/cantidades si es necesario y añade cualquier nota interna.
  3. Establece un período de validez y genera una proforma en PDF.
  4. Cambia el estado a "Enviada" y envía la cotización por correo electrónico al cliente.
  5. Haz un seguimiento de las cotizaciones "Enviadas". Si se aceptan, conviértelas en pedido. Si se rechazan o vencen, actualiza el estado en consecuencia.

#### 2.2.2 Registro de Auditoría (Back Office > Quote Enterprise > Registro de Auditoría)

Esta pantalla proporciona un historial detallado de todas las acciones realizadas en las cotizaciones.

- **Nombre de la Pantalla y Ubicación del Menú:** **Quote Enterprise > Registro de Auditoría**
- **Acciones y Configuraciones Disponibles:**
  - **Tabla de Lista de Registros:** Muestra una lista cronológica de eventos relacionados con las cotizaciones, incluyendo quién realizó la acción, qué acción se tomó (por ejemplo, "Cotización Creada", "Precio Cambiado", "Estado Actualizado") y cuándo ocurrió.
  - **Filtrado:** Filtra el registro por fecha, usuario o tipo de acción para encontrar eventos específicos.
- **Efecto de los cambios:** Este es un registro de solo lectura; no puedes realizar cambios aquí. Sirve como un registro histórico.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  - Utiliza el registro de auditoría para rastrear cambios, solucionar problemas o revisar la actividad del equipo en las cotizaciones. Es invaluable para la rendición de cuentas y para comprender el ciclo de vida de cada cotización.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Habilitar Quote Enterprise | SÍ | Interruptor maestro para la funcionalidad del módulo. |
|  | Permitir Solicitudes de Cotización desde el Carrito | SÍ | Añade el botón de cotización a la página del carrito. |
|  | Permitir Solicitudes de Cotización desde la Página de Producto | SÍ | Añade el botón de cotización a las páginas de productos. |
|  | Mostrar Botón Flotante de Cotización | SÍ | Muestra un botón de cotización persistente en el front office. |
|  | Valor Mínimo del Pedido para la Solicitud de Cotización | 0 | Establece un valor mínimo para el envío de cotizaciones. |
|  | Validez Predeterminada de la Cotización (Días) | 30 | Establece el vencimiento predeterminado para las nuevas cotizaciones. |
|  | Gestor de Plantillas de Correo Electrónico | Personalizar | Edita el contenido del correo electrónico para varios eventos de cotización. |
|  | Habilitar REST API | NO | Activa la API para integraciones externas (solo desarrolladores). |
|  | Gestión de Claves API | N/A | Gestiona las claves API para un acceso seguro a la API (solo desarrolladores). |
|  | URL de Tarea Cron para Vencimiento y Resumen | Configurar | Automatiza las comprobaciones de vencimiento de cotizaciones y los resúmenes del equipo. |
| **Gestión de Cotizaciones** | Lista de Cotizaciones | N/A | Ver, filtrar y gestionar todas las cotizaciones. |
|  | Ver/Editar Cotización | N/A | Ajustar artículos, precios, estado, generar PDF, convertir a pedido. |
|  | Acciones Masivas | N/A | Aplicar acciones a múltiples cotizaciones seleccionadas. |
| **Registro de Auditoría** | Lista de Registros | N/A | Revisar acciones históricas en todas las cotizaciones. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Mis botones "Solicitar una Cotización" no aparecen en el front office.**
R:

1. **Verifica el Estado del Módulo:** Asegúrate de que "Habilitar Quote Enterprise" esté configurado en SÍ en la configuración del módulo.
2. **Verifica la Configuración Específica:** Verifica que "Permitir Solicitudes de Cotización desde el Carrito" y "Permitir Solicitudes de Cotización desde la Página de Producto" estén habilitados según sea necesario.
3. **Borra la Caché:** Ve a **Parámetros Avanzados > Rendimiento** y borra la caché de PrestaShop (caché de Smarty, caché del sistema de archivos). A veces, los cambios no aparecen hasta que se actualiza la caché.
4. **Compatibilidad del Tema:** Si estás utilizando un tema personalizado, podría haber un problema de compatibilidad. Contacta con el soporte de MyPresta.eu con los detalles de tu tema.

**P: Los clientes no reciben correos electrónicos de notificación de cotización.**
R:

1. **Verifica las Plantillas de Correo Electrónico:** En la configuración del módulo, ve a la pestaña "Plantillas de Correo Electrónico" y asegúrate de que las plantillas estén correctamente configuradas y guardadas.
2. **Configuración de Correo Electrónico de PrestaShop:** Verifica tu configuración general de correo electrónico de PrestaShop (SMTP, correo PHP) en **Parámetros Avanzados > E-mail**. Envía un correo electrónico de prueba desde allí para confirmar que el sistema de correo de tu tienda funciona.
3. **Carpetas de Spam:** Aconseja a los clientes que revisen sus carpetas de spam o correo no deseado.
4. **Tarea Cron (para resúmenes/recordatorios):** Si se trata de recordatorios de vencimiento o resúmenes diarios, asegúrate de que la URL de la tarea cron esté correctamente configurada en tu servidor para ejecutarse regularmente.

**P: ¿Puedo personalizar la apariencia del formulario de solicitud de cotización o los botones?**
R: Sí, el módulo utiliza la plantilla estándar de PrestaShop. Para cambios básicos de estilo (colores, fuentes), a menudo puedes sobrescribir el CSS del módulo en el archivo CSS personalizado de tu tema. Para cambios de diseño más complejos, necesitarías sobrescribir los archivos TPL del módulo en tu tema. Esto generalmente requiere un desarrollador web.

**P: ¿Cómo convierto una cotización aceptada en un pedido regular?**
R: En el Back Office de PrestaShop, navega a **Quote Enterprise > Cotizaciones**. Abre la cotización específica que deseas convertir. Dentro de la vista detallada de la cotización, habrá un botón (por ejemplo, "Convertir a Pedido" o "Crear Pedido"). Al hacer clic en él, se generará un nuevo pedido en tu lista de pedidos estándar de PrestaShop, pre-rellenado con los artículos y precios cotizados.

**P: ¿Qué sucede si una cotización vence?**
R: Si la tarea cron está configurada, el módulo marcará automáticamente las cotizaciones vencidas como "Vencidas". Los clientes ya no podrán aceptar o convertir una cotización vencida en un pedido. Tu equipo de ventas aún puede ver las cotizaciones vencidas y potencialmente reactivar o crear una nueva cotización si es necesario.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo Quote Enterprise sigue una sólida arquitectura MVC (Modelo-Vista-Controlador) de PrestaShop, aprovechando en gran medida `ObjectModel` para la persistencia de datos. Se integra perfectamente con el sistema de hooks de PrestaShop para la visualización en el front-office y las acciones en el back-office. El módulo incluye controladores de administración dedicados para gestionar cotizaciones y registros de auditoría, controladores frontales para la interacción del cliente (solicitud, lista, vista, API) y un conjunto completo de clases de ayuda para la lógica de negocio, generación de PDF, manejo de correo electrónico y más. También se proporciona una REST API para la integración de sistemas externos.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

- `controllers/front/api.php`
  - Nombre de la clase: `QuoteenterpriseApiModuleFrontController` (extiende `ModuleFrontController`)
  - Responsabilidad: Maneja las solicitudes de API desde el front-office, probablemente para integraciones específicas orientadas al cliente o carga de contenido dinámico.
- `controllers/front/cron.php`
  - Nombre de la clase: `QuoteenterpriseCronModuleFrontController` (extiende `ModuleFrontController`)
  - Responsabilidad: Sirve como punto final para la tarea cron, activando tareas en segundo plano como la comprobación de vencimientos de cotizaciones y el envío de correos electrónicos de resumen.
- `controllers/front/index.php`
  - Nombre de la clase: `QuoteenterpriseIndexModuleFrontController` (extiende `ModuleFrontController`)
  - Responsabilidad: Probablemente un controlador de reserva o base, o maneja una ruta predeterminada para la sección del front-office del módulo.
- `controllers/front/list.php`
  - Nombre de la clase: `QuoteenterpriseListModuleFrontController` (extiende `ModuleFrontController`)
  - Responsabilidad: Muestra una lista de cotizaciones para el cliente que ha iniciado sesión en su área de cuenta.
- `controllers/front/pdf.php`
  - Nombre de la clase: `QuoteenterprisePdfModuleFrontController` (extiende `ModuleFrontController`)
  - Responsabilidad: Genera y sirve versiones PDF de las cotizaciones para que los clientes las descarguen.
- `controllers/front/quoteList.php`
  - Nombre de la clase: `QuoteenterpriseQuoteListModuleFrontController` (extiende `ModuleFrontController`)
  - Responsabilidad: Similar a `list.php`, potencialmente una vista alternativa o específica para listados de cotizaciones, posiblemente para carga AJAX.
- `controllers/front/request.php`
  - Nombre de la clase: `QuoteenterpriseRequestModuleFrontController` (extiende `ModuleFrontController`)
  - Responsabilidad: Maneja la visualización y el envío del formulario de solicitud de cotización desde las páginas de productos, el carrito o el botón flotante. Procesa los datos del formulario y crea nuevas entradas de cotización.
- `controllers/front/view.php`
  - Nombre de la clase: `QuoteenterpriseViewModuleFrontController` (extiende `ModuleFrontController`)
  - Responsabilidad: Muestra la vista detallada de una sola cotización para el cliente, mostrando artículos, precios, estado y mensajes.

#### Controladores de Administración del Back-Office

- `controllers/admin/AdminQuoteEnterpriseAuditLog.php`
  - Nombre de la clase: `AdminQuoteEnterpriseAuditLogController` (extiende `ModuleAdminController`)
  - Nombre de la pestaña: Quote Enterprise > Registro de Auditoría
  - Entidad gestionada: `quote_audit_log` (probablemente un `ObjectModel` personalizado para entradas de auditoría)
  - Responsabilidad: Proporciona una vista de cuadrícula para que los administradores revisen todas las acciones y cambios históricos relacionados con las cotizaciones.
- `controllers/admin/AdminQuoteEnterpriseQuotes.php`
  - Nombre de la clase: `AdminQuoteEnterpriseQuotesController` (extiende `ModuleAdminController`)
  - Nombre de la pestaña: Quote Enterprise > Cotizaciones
  - Entidad gestionada: `quote` (probablemente un `ObjectModel` personalizado para cotizaciones)
  - Responsabilidad: La interfaz principal para gestionar cotizaciones, incluyendo listar, ver, editar, convertir a pedido y enviar comunicaciones.
- `controllers/admin/index.php`
  - Nombre de la clase: `QuoteenterpriseAdminIndexModuleFrontController` (extiende `ModuleAdminController`)
  - Responsabilidad: Probablemente un marcador de posición o controlador de administración base, que potencialmente redirige a la lista principal de cotizaciones o al panel de control.

### 4.3 Clases y Modelos Principales (`classes/`)

- `classes/index.php`: Archivo vacío, práctica común para evitar la lista de directorios.
- `classes/QuoteAdmin.php`: Contiene la lógica para tareas específicas de administración, potencialmente relacionadas con la configuración del módulo o utilidades generales de administración.
- `classes/QuoteAdminAjax.php`: Maneja las solicitudes AJAX originadas desde el back-office, como la búsqueda dinámica de productos para añadir a una cotización.
- `classes/QuoteAdminQuoteForm.php`: Gestiona la compleja lógica del formulario para editar y crear cotizaciones en el back-office.
- `classes/QuoteApi.php`: Clase principal para la REST API del módulo, que maneja la autenticación, el enrutamiento y la serialización de datos.
- `classes/QuoteApiDocumentation.php`: Proporciona métodos para generar o mostrar documentación para los puntos finales de la API del módulo.
- `classes/QuoteBulkActions.php`: Implementa la lógica para realizar acciones en múltiples cotizaciones seleccionadas en la lista de administración (por ejemplo, cambio de estado masivo).
- `classes/QuoteConverter.php`: Maneja la lógica crucial de convertir una cotización aceptada en un pedido estándar de PrestaShop.
- `classes/QuoteDashboard.php`: Proporciona datos y lógica para la vista del panel de control del módulo en el back-office (si está presente), resumiendo la actividad de las cotizaciones.
- `classes/QuoteDuplicator.php`: Lógica para duplicar cotizaciones existentes.
- `classes/QuoteenterpriseModuleFrontController.php`: Clase base para los controladores del front-office, que proporciona métodos y propiedades comunes.
- `classes/QuoteExpiry.php`: Gestiona la lógica para comprobar la validez de las cotizaciones, marcarlas como vencidas y enviar notificaciones relacionadas.
- `classes/QuoteExporter.php`: Maneja la exportación de datos de cotizaciones (por ejemplo, CSV, Excel).
- `classes/QuoteFeeProduct.php`: Probablemente un `ObjectModel` o un ayudante para gestionar productos de "tarifa" especiales que se pueden añadir a las cotizaciones (por ejemplo, para servicios, cargos personalizados).
- `classes/QuoteListHelper.php`: Proporciona métodos de utilidad para mostrar y filtrar listas de cotizaciones tanto en el front como en el back office.
- `classes/QuoteMailer.php`: Clase centralizada para enviar varias notificaciones por correo electrónico relacionadas con las cotizaciones.
- `classes/QuoteNotifyDigest.php`: Lógica para compilar y enviar resúmenes diarios o periódicos de la actividad de las cotizaciones a los administradores.
- `classes/QuotePdf.php`: Maneja la generación de facturas proforma en PDF para las cotizaciones.
- `classes/QuoteProductHelper.php`: Métodos de utilidad para interactuar con los productos de PrestaShop en el contexto de una cotización.
- `classes/QuoteQtyHelper.php`: Ayuda con la gestión y validación de cantidades dentro de las cotizaciones.
- `classes/QuoteQuotesManager.php`: Lógica de negocio principal para gestionar cotizaciones, incluyendo creación, actualizaciones y cambios de estado.
- `classes/QuoteReference.php`: Gestiona la generación y unicidad de los números de referencia de las cotizaciones.
- `classes/QuoteRequestHelper.php`: Ayuda con el procesamiento y la validación de las solicitudes de cotización enviadas por los clientes.
- `classes/QuoteSchema.php`: Define el esquema de la base de datos para las tablas personalizadas utilizadas por el módulo (por ejemplo, `ps_quote`, `ps_quote_product`, `ps_quote_audit_log`).
- `classes/QuoteSettingDescTrait.php`: Un trait de PHP probablemente utilizado para proporcionar descripciones o metadatos comunes para la configuración del módulo.
- `classes/QuoteTaxHelper.php`: Maneja los cálculos de impuestos específicos de las cotizaciones.
- `classes/QuoteThemeCompat.php`: Contiene la lógica para garantizar la compatibilidad con varios temas de PrestaShop, potencialmente detectando características del tema o proporcionando sobrescrituras.
- `classes/QuoteTimeline.php`: Gestiona y muestra la línea de tiempo de eventos para una cotización específica (similar al historial de pedidos).
- `classes/QuoteValidityHelper.php`: Métodos de utilidad para calcular y validar las fechas de vencimiento de las cotizaciones.
- `classes/QuoteVisibility.php`: Controla la visibilidad de los elementos relacionados con las cotizaciones en el front office (por ejemplo, quién puede solicitar una cotización, dónde aparecen los botones).

### 4.4 Activos JavaScript (`views/js/`)

- `lib/emailTemplatesManager/js/emailTemplatesManager.js`: Lógica de front-end para el editor de plantillas de correo electrónico en el back-office.
- `lib/searchTool/views/js/autocomplete.js`: Proporciona funcionalidad de autocompletado para buscar productos o clientes en el editor de cotizaciones del back-office.
- `views/js/admin-audience-picker.js`: Maneja la lógica para seleccionar grupos de clientes o clientes específicos para la visibilidad o segmentación de cotizaciones en la administración.
- `views/js/adminQuoteApi.js`: JavaScript para la pantalla de configuración de la API de administración, que potencialmente maneja la generación de claves o la visualización de la documentación de la API.
- `views/js/adminQuoteDashboard.js`: Scripts para elementos interactivos o visualización de datos en el panel de control de administración.
- `views/js/adminQuoteDetail.js`: Maneja las interacciones dinámicas dentro de la vista detallada de la cotización en el back-office (por ejemplo, añadir productos, aplicar descuentos, cambios de estado).
- `views/js/adminQuoteEditor.js`: JavaScript principal para el formulario de creación/edición de cotizaciones del back-office, incluyendo la selección de productos, actualizaciones de cantidad y ajustes de precios.
- `views/js/adminQuoteSelector.js`: Se utiliza para seleccionar cotizaciones, posiblemente en un modal o contexto vinculado.
- `views/js/adminQuotesList.js`: Scripts para la lista de cotizaciones de administración, incluyendo filtrado, clasificación y acciones masivas.
- `views/js/front.js`: JavaScript general del front-office para el módulo, que maneja clics de botones, ventanas emergentes modales para solicitudes de cotización, envíos de formularios y actualizaciones dinámicas.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `lib/emailTemplatesManager/css/emailTemplatesManager.css`: Estilo para el editor de plantillas de correo electrónico en el back-office.
- `lib/searchTool/views/css/autocomplete.css`: Estilos para los resultados de búsqueda de autocompletado (por ejemplo, búsqueda de productos).
- `views/css/admin-audience-picker.css`: Estilo para la interfaz de selección de clientes/audiencia en la administración.
- `views/css/admin_quoteenterprise.css`: Hoja de estilo principal para las interfaces del back-office del módulo (lista de cotizaciones, detalles, registro de auditoría).
- `views/css/front-hummingbird.css`: Ajustes de estilo específicos del front-office para el tema predeterminado "Hummingbird" de PrestaShop.
- `views/css/front.css`: Estilo general del front-office para botones de cotización, formularios y vistas de cuenta de cliente. Los desarrolladores pueden sobrescribir clases como `.quoteenterprise-button`, `.quoteenterprise-form`, `.quoteenterprise-list` en su tema.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)

- `hook/adminOrderQuote.tpl`: Renderiza un bloque relacionado con la cotización dentro de la página de detalles del pedido estándar de PrestaShop en la administración.
- `hook/cartQuoteButton.tpl`: Muestra el botón o enlace "Solicitar una Cotización" en la página del carrito de compras.
- `hook/customerAccount-hummingbird.tpl`: Renderiza el enlace de la lista de cotizaciones en el área de la cuenta del cliente para el tema Hummingbird.
- `hook/customerAccount.tpl`: Renderiza el enlace de la lista de cotizaciones en el área de la cuenta del cliente para temas clásicos.
- `hook/productListQuote.tpl`: Muestra un botón o opción de cotización en las páginas de lista de productos (categoría, resultados de búsqueda).
- `hook/quoteFloatButton.tpl`: Renderiza el botón de cotización flotante persistente en el front office.
- `hook/quoteListModal.tpl`: Plantilla para una ventana modal que muestra una lista de cotizaciones.
- `hook/quoteRequestButton.tpl`: Muestra el botón "Solicitar una Cotización" en las páginas de productos individuales.
- `hook/quoteRequestModal.tpl`: Plantilla para la ventana modal que abre el formulario de solicitud de cotización.

#### Plantillas de Administración (`views/templates/admin/`)

- `admin/api.tpl`: Renderiza la configuración de la API y la interfaz de gestión de claves.
- `admin/audience-picker.tpl`: Plantilla para la herramienta de selección de clientes/grupos en la administración.
- `admin/audit.tpl`: Muestra la tabla del registro de auditoría en el back-office.
- `admin/dashboard.tpl`: Renderiza la vista general del panel de control del módulo en el back-office.
- `admin/notifications.tpl`: Muestra las notificaciones de administración relacionadas con las cotizaciones.
- `admin/quoteDetail.tpl`: La plantilla completa para ver y editar una sola cotización en el back-office.
- `admin/quotes.tpl`: Renderiza la tabla principal de la lista de cotizaciones en el back-office.
- `admin/quotesOverview.tpl`: Una sección de resumen o vista general para las cotizaciones, posiblemente en el panel de control.
- `admin/scopeSelector.tpl`: Plantilla para seleccionar el ámbito (por ejemplo, tienda, idioma) en la administración.
- `admin/visibilityConfigurator.tpl`: Plantilla para configurar las reglas de visibilidad de las cotizaciones.
- `admin/_api_documentation_modal.tpl`: Renderiza una ventana modal con documentación de la API para desarrolladores.
- `admin/_bulk_options.tpl`: Plantilla para los desplegables de acciones masivas en las listas de administración.

#### Plantillas del Front-Office (`views/templates/front/`)

- `front/list.tpl`: Muestra la lista de cotizaciones del cliente en su cuenta.
- `front/request.tpl`: La plantilla principal para el formulario de solicitud de cotización del cliente.
- `front/view.tpl`: Muestra la vista detallada de una sola cotización para el cliente.
- `front/_requestComplianceFields.tpl`: Plantilla parcial para campos adicionales relacionados con el cumplimiento en el formulario de solicitud de cotización.
- `front/_requestLinesTable.tpl`: Plantilla parcial para mostrar las líneas de productos dentro de un formulario de solicitud de cotización.

#### Plantillas PDF (`views/templates/pdf/`)

- `pdf/quote.tpl`: Plantilla utilizada para generar el contenido de la factura proforma en PDF.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

#### Tablas de la Base de Datos

El módulo crea tablas personalizadas, típicamente con el prefijo `ps_` (o tu prefijo personalizado). Las tablas clave incluyen:

- `ps_quote`: Almacena los detalles principales de la cotización (ID de cliente, estado, total, validez, referencia, etc.).
- `ps_quote_product`: Almacena los productos individuales y sus cantidades/precios asociados a cada cotización.
- `ps_quote_audit_log`: Registra todos los cambios y acciones realizadas en las cotizaciones para fines de auditoría.
- `ps_quote_api_key`: Almacena las claves API para integraciones externas.
- `ps_configuration`: La configuración del módulo se almacena aquí con claves como `QUOTEENTERPRISE_ENABLE`, `QUOTEENTERPRISE_MIN_VALUE`, etc.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyección de activos CSS/JS, metaetiquetas o inicialización global del módulo. |
| `displayRightColumn` | En la columna derecha de tu tienda (si está habilitada por el tema). | Mostrar el botón de cotización flotante o un bloque estático de solicitud de cotización. |
| `displayLeftColumn` | En la columna izquierda de tu tienda (si está habilitada por el tema). | Mostrar el botón de cotización flotante o un bloque estático de solicitud de cotización. |
| `displayFooter` | En la sección del pie de página de cada página. | Mostrar el botón de cotización flotante o un bloque estático de solicitud de cotización. |
| `displayProductButtons` | En la página del producto, cerca del botón "Añadir al carrito". | Mostrar el botón "Solicitar una Cotización" en las páginas de productos. |
| `displayShoppingCartFooter` | En el resumen del carrito de compras, debajo de la lista de productos. | Mostrar el botón "Solicitar una Cotización" para convertir el carrito en cotización. |
| `displayCustomerAccount` | En la página "Mi cuenta" del cliente. | Añadir un enlace a la lista de cotizaciones del cliente. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Potencialmente utilizado para vincular una cotización al pedido resultante o actualizar el estado de la cotización. |
| `actionAdminControllerSetMedia` | Cuando un controlador de administración carga sus activos. | Inyección de CSS/JS específicos del módulo para las páginas del back-office. |
| `displayAdminOrder` | En la página de detalles del pedido de administración de PrestaShop. | Mostrar un bloque con información de la cotización si el pedido se originó a partir de una cotización. |
| `actionObjectProductUpdateAfter` | Después de que se actualiza un producto. | Potencialmente para actualizar los precios de las cotizaciones si los precios de los productos cambian (característica avanzada). |
| `actionObjectProductDeleteAfter` | Después de que se elimina un producto. | Para manejar productos eliminados de las cotizaciones. |
| `actionObjectCustomerDeleteAfter` | Después de que se elimina un cliente. | Para manejar cotizaciones asociadas a un cliente eliminado. |
| `displayBackOfficeHeader` | En el `<head>` de cada página del back-office. | Inyección general de activos del back-office o configuración global del módulo de administración. |
| `displayBackOfficeTop` | En la parte superior del área de contenido del back-office. | Mostrar alertas específicas del módulo o widgets del panel de control. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicia sesión en tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto al módulo Quote Enterprise.

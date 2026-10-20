---
title: "Delete Orders Pro - Manual de Usuario y Guía de Configuración para Comerciantes"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Delete Orders Pro de MyPresta.eu."
sidebar:
  label: "Delete Orders Pro - Manual de Usuario y Guía de Configuración para Comerciantes"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Delete Orders Pro en MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-orders-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/delete-orders-pro/)
>
> ---


# Delete Orders Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones de servidor especiales más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página de configuración principal del módulo "Delete Orders Pro". Esta pantalla gestiona principalmente la configuración general del módulo y las comprobaciones de actualización.

-   **Qué hace este ajuste:** Esta sección suele incluir la configuración estándar de los módulos de MyPresta.eu relacionada con las notificaciones de actualización y el seguimiento interno.
-   **Efecto de cambiar este ajuste:**
    -   `mypresta_updates`, `update_`, `updatev_`: Estos ajustes controlan si el módulo busca actualizaciones de MyPresta.eu y muestra notificaciones en su back office. Habilitarlos le mantiene informado sobre nuevas versiones y características. Deshabilitarlos detendrá estas notificaciones.
    -   `DELETEORDERS_LAST_TAB`: Este es un ajuste interno que rastrea la última pestaña o vista en la que estuvo dentro de la interfaz de administración dedicada del módulo. Ayuda al módulo a recordar su última posición para mayor comodidad.
-   **Valor recomendado:**
    -   Para los ajustes relacionados con las actualizaciones: **SÍ** (o Habilitado). Siempre se recomienda mantener las comprobaciones de actualización habilitadas para asegurarse de que está ejecutando la última versión del módulo, la más segura y con más funciones.
    -   `DELETEORDERS_LAST_TAB`: Deje este ajuste tal cual; el módulo lo gestiona automáticamente.
-   **Escenario / ejemplo de comerciante:** Mantener las comprobaciones de actualización habilitadas significa que se le notificará directamente en su back office de PrestaShop cuando se lance una nueva versión de "Delete Orders Pro", lo que le permitirá actualizar fácilmente y beneficiarse de mejoras o correcciones de errores.

### 2.2 Pantallas de Administración Dedicadas y Vistas del Controlador

#### 2.2.1 Pestaña Eliminar Pedidos (Back Office > Pedidos > Delete Orders Pro)

Esta es la interfaz principal donde gestionará y eliminará pedidos.

-   **Nombre de la Pantalla y Ubicación del Menú:** Puede acceder a esta pantalla navegando a **Pedidos > Delete Orders Pro** en el menú de su back office de PrestaShop.
-   **Acciones y Ajustes Disponibles:** Esta pantalla presenta una vista de cuadrícula o lista de sus pedidos, similar a la lista estándar de Pedidos de PrestaShop, pero con funcionalidad adicional específicamente para la eliminación.
    -   **Opciones de Filtrado:** Probablemente encontrará filtros para reducir los pedidos que desea eliminar (por ejemplo, por estado del pedido, rango de fechas, cliente, etc.). Esto es crucial para apuntar de forma segura a tipos específicos de pedidos.
    -   **Casillas de Verificación de Selección:** Cada pedido de la lista tendrá una casilla de verificación, lo que le permitirá seleccionar pedidos individuales para su eliminación.
    -   **Acciones Masivas:** Debería haber una opción para seleccionar varios pedidos (por ejemplo, "Seleccionar todo" o "Seleccionar pedidos con estado X") y luego realizar una eliminación masiva.
    -   **Botón Eliminar:** Un botón prominente (por ejemplo, "Eliminar Pedidos Seleccionados" o "Eliminar Pedidos") iniciará el proceso de eliminación.
-   **Efecto de los cambios:**
    -   Cuando selecciona pedidos y hace clic en el botón de eliminar, el módulo eliminará permanentemente esos pedidos y todos los datos asociados (detalles del pedido, productos pedidos, mensajes del cliente relacionados con el pedido, facturas, etc.) de su base de datos de PrestaShop.
    -   Esta acción es irreversible.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  **Revise regularmente sus pedidos:** Identifique qué estados de pedido representan comúnmente pedidos "no deseados" (por ejemplo, "Cancelado", "Error de pago", "En espera" si no se cumplen, o estados personalizados para pedidos de prueba).
    2.  **Acceda a "Delete Orders Pro":** Vaya a **Pedidos > Delete Orders Pro**.
    3.  **Filtre pedidos:** Utilice los filtros disponibles para mostrar solo los pedidos que desea eliminar (por ejemplo, filtre por estado "Cancelado" y un rango de fechas anterior a 3 meses).
    4.  **Seleccione cuidadosamente los pedidos:** Vuelva a verificar los pedidos que ha filtrado y selecciónelos usando las casillas de verificación.
    5.  **Inicie la eliminación:** Haga clic en el botón "Eliminar Pedidos Seleccionados". Confirme la acción cuando se le solicite.
    6.  **Realice copias de seguridad:** Antes de cualquier eliminación importante, asegúrese siempre de tener una copia de seguridad reciente de la base de datos.

#### 2.2.2 Controlador Index (deleteorderspro/controllers/admin/index.php)

Este archivo suele servir como controlador de enrutamiento o de reserva dentro de la sección de administración del módulo. En el contexto de "Delete Orders Pro", es probable que garantice que si un usuario navega a la ruta de administración base del módulo sin especificar una acción o subcontrolador particular, sea redirigido a la interfaz principal `deleteorderstab`.

-   **Nombre de la Pantalla y Ubicación del Menú:** No es una pantalla directa, sino parte de la navegación interna del módulo.
-   **Acciones y Ajustes Disponibles:** No hay ajustes configurables directamente por el usuario. Su propósito es gestionar el enrutamiento interno.
-   **Efecto de los cambios:** No hay impacto directo para el comerciante. Garantiza una experiencia de navegación fluida dentro de la sección de administración del módulo.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** No se necesita un flujo de trabajo específico; esto opera en segundo plano.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | `mypresta_updates` | SÍ | Habilita/deshabilita las notificaciones de actualización de MyPresta.eu. |
| | `update_` | SÍ | Indicador interno para el estado de la actualización. |
| | `updatev_` | SÍ | Indicador interno para la versión de la actualización. |
| | `DELETEORDERS_LAST_TAB` | (Gestionado automáticamente) | Rastrea la última pestaña visitada en la interfaz de administración del módulo. |
| **Pestaña Eliminar Pedidos** | Filtros (Estado, Fecha, etc.) | Varía | Reduce la lista de pedidos a eliminar. |
| | Casillas de Verificación de Selección de Pedidos | N/A | Permite la selección de pedidos individuales para su eliminación. |
| | Acción Masiva: Eliminar Seleccionados | N/A | Elimina permanentemente los pedidos seleccionados y los datos asociados. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Eliminé pedidos, pero el rendimiento de mi tienda no parece mucho más rápido. ¿Por qué?**
R: Si bien la eliminación de pedidos reduce el tamaño de la base de datos, el rendimiento está influenciado por muchos factores (alojamiento, otros módulos, optimización del tema, tamaños de imagen). La eliminación de pedidos es un paso en la optimización general. Asegúrese de haber borrado también la caché de PrestaShop (**Parámetros avanzados > Rendimiento**) después de la eliminación.

**P: ¿Puedo recuperar pedidos después de haberlos eliminado?**
R: No. Una vez que los pedidos se eliminan con este módulo, se eliminan permanentemente de su base de datos. Por eso es crucial hacer siempre una copia de seguridad de su base de datos antes de realizar cualquier eliminación importante y revisar cuidadosamente sus selecciones.

**P: ¿La eliminación de pedidos afectará las cuentas de mis clientes o el stock de productos?**
R: La eliminación de un pedido elimina el registro del pedido en sí y sus detalles asociados (como los productos específicos pedidos dentro de esa transacción, facturas, mensajes). NO elimina la cuenta del cliente asociada con el pedido, ni suele revertir los niveles de stock (ya que el stock generalmente se ajusta en el momento de la creación del pedido o el cambio de estado, no la eliminación). Verifique siempre el comportamiento del módulo en un entorno de prueba si tiene preocupaciones específicas sobre el stock.

**P: El módulo no aparece en el menú de mi Back Office.**
R:

1.  **Verifique la instalación:** Vaya a **Módulos > Gestor de módulos** y busque "Delete Orders Pro". Asegúrese de que esté listado como "Instalado" y "Habilitado".
2.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché". A veces, los cambios en el menú requieren una actualización de la caché.
3.  **Permisos:** Verifique sus permisos de usuario en **Administración > Permisos** para asegurarse de que su perfil tenga acceso a la sección "Pedidos" y a cualquier permiso específico del módulo.

**P: Recibo un error al intentar eliminar pedidos.**
R:

1.  **Verifique el Modo Depuración de PrestaShop:** Habilite el modo depuración (**Parámetros avanzados > Rendimiento > Modo depuración**) para ver si aparece un mensaje de error más detallado.
2.  **Registros de Errores del Servidor:** Verifique los registros de errores de PHP de su servidor (a menudo se encuentran en su panel de control de alojamiento) para ver si hay mensajes relacionados.
3.  **Contactar con Soporte:** Si no puede resolver el problema, recopile los mensajes de error y póngase en contacto con el soporte de MyPresta.eu para obtener ayuda.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una visión técnica para desarrolladores y webmasters que trabajan con el módulo "Delete Orders Pro".

### 4.1 Resumen de la Arquitectura

El módulo "Delete Orders Pro" sigue la arquitectura estándar de módulos de PrestaShop, aprovechando principalmente los Controladores de Administración del Back-Office para su funcionalidad. Se integra en el sistema de menús de PrestaShop y utiliza el `AdminController` central de PrestaShop para renderizar listas y manejar envíos de formularios. El módulo interactúa directamente con la base de datos para realizar operaciones de eliminación en tablas relacionadas con pedidos. No introduce clases `ObjectModel` personalizadas, sino que opera sobre entidades de pedidos existentes de PrestaShop.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. Este módulo no tiene presencia en el front-office.
-   **Controladores de Administración del Back-Office**:

    -   `deleteorderspro/controllers/admin/deleteorderstab.php`

        -   **Nombre de la Clase**: `AdminDeleteOrdersProController` (o similar, típicamente derivado del nombre del archivo y el contexto del módulo) que extiende `ModuleAdminController`.
        -   **Responsabilidad**: Este es el controlador administrativo principal del módulo. Es responsable de:
            -   Mostrar la lista de pedidos en formato de cuadrícula.
            -   Manejar el filtrado, la clasificación y la paginación de pedidos.
            -   Procesar la eliminación de pedidos seleccionados.
            -   Interactuar con los `Order` y `ObjectModel` relacionados de PrestaShop para realizar eliminaciones de la base de datos.
            -   Renderizar la plantilla para la lista de pedidos y la interfaz de eliminación.
        -   **Pestaña de PrestaShop**: Este controlador está registrado como una nueva pestaña en el menú "Pedidos" del back office de PrestaShop.
    -   `deleteorderspro/controllers/admin/index.php`

        -   **Nombre de la Clase**: No es una clase de controlador típica; a menudo un simple archivo de redirección o de arranque.
        -   **Responsabilidad**: Este archivo suele servir como un punto de entrada o de reserva. En muchos módulos, si un usuario navega a la ruta base `admin/nombre_del_modulo`, este `index.php` podría redirigirlos al controlador principal (por ejemplo, `deleteorderstab`) para asegurar que se cargue la interfaz correcta. Evita el acceso directo al directorio y asegura un enrutamiento adecuado.

### 4.3 Clases y Modelos Centrales (`classes/`)

El módulo no parece introducir ninguna clase o `ObjectModel` personalizada en su directorio `classes/` según el inventario proporcionado. Es probable que opere directamente sobre los `Order` y `ObjectModel` relacionados de PrestaShop (por ejemplo, `OrderHistory`, `OrderDetail`, `ProductSale`, `Cart`, etc.) para asegurar una eliminación completa de todos los datos asociados.

### 4.4 Activos JavaScript (`views/js/`)

No se identificaron archivos JavaScript en el archivo del módulo. El módulo probablemente se basa en el JavaScript estándar del back office de PrestaShop para el envío de formularios y las interacciones de la cuadrícula, o su funcionalidad es completamente del lado del servidor.

### 4.5 Hojas de Estilo CSS (`views/css/`)

No se identificaron archivos CSS en el archivo del módulo. El módulo probablemente hereda el estilo directamente del tema del back office de PrestaShop, asegurando una apariencia consistente sin estilos personalizados.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

No se identificaron archivos `.tpl` en el archivo del módulo. Esto sugiere que el módulo podría estar utilizando las plantillas predeterminadas `list.tpl` y `form.tpl` proporcionadas por `AdminController` para renderizar su cuadrícula y configuración, o genera su HTML directamente dentro del controlador.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:
    El módulo no crea tablas de base de datos personalizadas. Opera sobre tablas existentes de PrestaShop relacionadas con pedidos, incluyendo, entre otras:

    -   `ps_orders`
    -   `ps_order_detail`
    -   `ps_order_history`
    -   `ps_order_invoice`
    -   `ps_order_payment`
    -   `ps_order_return`
    -   `ps_order_slip`
    -   `ps_cart` (y `ps_cart_product` relacionado)
    -   `ps_message` (para mensajes de clientes relacionados con pedidos)
    -   `ps_product_sale` (actualiza el recuento de ventas)
    -   `ps_customer_thread` (para hilos de atención al cliente relacionados con pedidos)
    -   `ps_configuration` (para almacenar la configuración del módulo como `mypresta_updates`, `DELETEORDERS_LAST_TAB`).
-   **Tabla de Hooks Registrados**:
    Basado en el propósito del módulo como herramienta de administración del back office, utiliza principalmente hooks para la instalación, desinstalación y, potencialmente, para añadir elementos de menú. No parece utilizar hooks de visualización del front office.

    | Nombre del Hook | Momento de Ejecución | Propósito Técnico |
    | --- | --- | --- |
    | `install()` | Durante la instalación del módulo | Crea la nueva pestaña "Delete Orders Pro" en el menú del back office de PrestaShop. Almacena los valores de configuración iniciales en `ps_configuration`. |
    | `uninstall()` | Durante la desinstalación del módulo | Elimina la pestaña "Delete Orders Pro" del menú del back office. Elimina los valores de configuración de `ps_configuration`. |
    | `displayBackOfficeHeader` | Renderiza contenido en la sección `<head>` del Back Office | Potencialmente utilizado para incluir cualquier JS/CSS necesario para el controlador de administración, aunque no se identificó ninguno en el inventario. |
    | `actionAdminControllerSetMedia` | Permite añadir JS/CSS a controladores de administración específicos | Utilizado por `AdminDeleteOrdersProController` para añadir cualquier activo específico requerido para su interfaz. |

## 5. Soporte Oficial y Actualizaciones

Para soporte oficial, actualizaciones y para descargar la última versión del módulo "Delete Orders Pro", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta que pueda tener con respecto a la funcionalidad del módulo.
"""

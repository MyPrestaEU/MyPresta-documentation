---
title: "Limitar el número de pedidos permitidos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Limitar el número de pedidos permitidos' de MyPresta.eu."
sidebar:
  label: "Limitar el número de pedidos permitidos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Limit number of allowed orders en MyPresta.eu](https://mypresta.eu/modules/ordering-process/limit-number-of-allowed-orders.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/limit-number-of-allowed-orders/)
>
> ---


# Limitar el número de pedidos permitidos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo, donde define los límites globales para sus clientes.

- **Qué hace este ajuste:** Este es el ajuste central del módulo. Define el número máximo de pedidos que *cualquier* cliente puede realizar en su tienda antes de que se le impida realizar más.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en un número específico (por ejemplo, 3):* Cualquier cliente que haya realizado 3 pedidos con éxito ya no podrá realizar un 4º pedido. Verá un mensaje que le impedirá completar el proceso de compra.
  - *Cuando se establece en 0 o se deja vacío:* El módulo se deshabilitará efectivamente para los límites globales, lo que significa que los clientes pueden realizar un número ilimitado de pedidos (a menos que se establezcan límites de cliente específicos, consulte la sección 4.2).
- **Valor recomendado:** Comience con un valor que se alinee con su objetivo comercial (por ejemplo, 1 para una promoción estricta de "uno por cliente", 5 para un límite general). Si solo desea limitar a clientes específicos, puede dejar esto vacío y usar la pantalla de gestión de clientes dedicada.
- **Escenario / ejemplo de comerciante:** Está realizando una venta flash de un producto muy solicitado y desea asegurarse de que cada cliente tenga solo una oportunidad de comprar. Establecería este valor en `1`.

### 2.2 Pantalla de administración dedicada: Límites de pedidos de clientes (Back Office > Módulos > Limitar el número de pedidos permitidos > Límites de pedidos de clientes)

Esta pantalla le permite gestionar límites de pedidos individuales para clientes específicos, anulando el límite global establecido en la sección 4.1.

- **Nombre de la pantalla y ubicación del menú:** Puede acceder a esta pantalla navegando a **Módulos > Gestor de módulos**, buscando "Limitar el número de pedidos permitidos", haciendo clic en "Configurar" y luego buscando una pestaña o enlace etiquetado como "Límites de pedidos de clientes" o similar. Alternativamente, podría aparecer directamente en su menú principal de PrestaShop bajo una nueva entrada creada por el módulo (por ejemplo, **Clientes > Límites de pedidos de clientes**).
- **Acciones y ajustes disponibles:**

  - **Búsqueda/Selección de clientes:** Normalmente encontrará una barra de búsqueda o un menú desplegable para seleccionar un cliente existente de su tienda.
  - **Establecer límite individual:** Una vez seleccionado un cliente, puede introducir un número específico de pedidos permitidos para *ese cliente en particular*.
  - **Ver/Editar límites existentes:** Una tabla o lista mostrará todos los clientes para los que ha establecido límites personalizados, junto con su límite actual y posiblemente su recuento de pedidos actual. Puede editar o eliminar estas entradas.
  - **Visualización de moneda:** El módulo podría mostrar información de moneda (por ejemplo, `PS_CURRENCY_DEFAULT`) en el contexto de los pedidos de los clientes, aunque los límites en sí son recuentos numéricos de pedidos, no valores monetarios.
- **Efecto de los cambios:**

  - *Agregar un nuevo límite de cliente:* El cliente seleccionado ahora estará restringido por el número específico de pedidos que le haya establecido, anulando el límite global (si está establecido).
  - *Editar un límite de cliente existente:* El recuento de pedidos permitidos del cliente se actualizará inmediatamente.
  - *Eliminar un límite de cliente:* El cliente volverá a regirse por el límite de pedidos global (si está establecido), o no tendrá límite si no hay un límite global activo.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

  1. **Identificar necesidades específicas:** Determine si ciertos clientes VIP, clientes problemáticos o clientes que participan en programas especiales requieren límites de pedidos únicos.
  2. **Buscar y agregar:** Utilice la funcionalidad de búsqueda para encontrar al cliente.
  3. **Aplicar límite:** Introduzca el número máximo de pedidos deseado para ese cliente.
  4. **Monitorear:** Revise periódicamente la lista de clientes con límites personalizados para asegurarse de que la configuración sigue siendo apropiada.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | **Número máximo de pedidos permitidos (Global)** | 0 (Ilimitado) / Su necesidad comercial | Establece un número máximo de pedidos en toda la tienda para *todos* los clientes. Impide el proceso de compra si se excede. |
| Límites de pedidos de clientes | **Búsqueda y selección de clientes** | N/A | Permite encontrar y seleccionar clientes específicos para aplicar límites individuales. |
| Límites de pedidos de clientes | **Límite de pedidos de cliente individual** | N/A | Anula el límite global para un cliente específico. Impide el proceso de compra para ese cliente si se excede su límite individual. |

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis clientes aún pueden realizar pedidos ilimitados, incluso después de establecer un límite global. ¿Qué pasa?**
R:

1. **Verifique la configuración:** Vuelva a verificar que ha guardado la configuración de "Número máximo de pedidos permitidos (Global)" en la página principal de configuración del módulo.
2. **Borrar caché:** PrestaShop utiliza caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Esto asegura que sus nuevas configuraciones se apliquen inmediatamente.
3. **Estado del módulo:** Asegúrese de que el módulo esté habilitado en **Módulos > Gestor de módulos**.
4. **Anulaciones de clientes específicos:** Verifique la pantalla "Límites de pedidos de clientes". Si un cliente específico tiene un límite individual establecido en `0` o un número muy alto, anulará el límite global para ellos.

**P: ¿Puedo establecer un límite para un cliente basado en el *valor* de sus pedidos, no solo en el recuento?**
R: Este módulo limita específicamente el *número* de pedidos. Actualmente no admite la limitación basada en el valor monetario. Para límites basados en el valor, necesitaría un tipo diferente de módulo o desarrollo personalizado.

**P: ¿Qué sucede cuando un cliente alcanza su límite? ¿Qué ve?**
R: Cuando un cliente intenta realizar un pedido que excedería su límite, el módulo impedirá que el pedido se finalice. Normalmente, se mostrará un mensaje claro en la página de pago o en el carrito de compras, informándoles que han alcanzado su número máximo de pedidos permitidos y no pueden continuar. La redacción exacta podría depender de su versión y tema de PrestaShop.

**P: ¿Este módulo afecta a pedidos anteriores?**
R: No, este módulo solo afecta a pedidos *futuros*. Cuenta los pedidos exitosos existentes para determinar si un nuevo intento de pedido excedería el límite, pero no modifica ni cancela ningún pedido realizado anteriormente.

**P: Quiero levantar temporalmente un límite para un cliente específico. ¿Cómo lo hago?**
R: Vaya a la pantalla "Límites de pedidos de clientes". Busque al cliente, edite su límite individual y establézcalo en `0` (para ilimitado) o un número muy alto. Recuerde guardar sus cambios. Siempre puede volver a aplicar un límite más estricto más tarde.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Limitar el número de pedidos permitidos" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando los hooks para la integración y un AdminController para gestionar los límites de clientes específicos. Opera principalmente verificando el historial de pedidos del cliente con los límites configurados durante el proceso de validación del pedido. El módulo se basa en el sistema de configuración de PrestaShop para la configuración global y una tabla de base de datos personalizada para los límites de clientes individuales.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Este módulo no utiliza controladores de front-office dedicados. Su lógica para verificar los límites se integra directamente en el proceso de pedido de PrestaShop a través de hooks.
- **Controladores de Back-Office Admin**:
  - `controllers/admin/AdminLimitOrdersUserController.php`
    - **Nombre de la clase**: `AdminLimitOrdersUserController` (extiende `ModuleAdminController`)
    - **Responsabilidad**: Este controlador gestiona los límites de pedidos personalizados para clientes individuales. Proporciona una interfaz estándar de PrestaShop de `list` y `form` para agregar, editar y eliminar límites de pedidos específicos del cliente. Interactúa con el ObjectModel `LimitOrdersUser` (aunque no se identificó ningún archivo `classes/` explícito, está implícito por el nombre y la función del controlador). Es probable que utilice `PS_CURRENCY_DEFAULT` para mostrar el contexto de la moneda, aunque los límites en sí son numéricos.
    - **Nombre de la pestaña**: Probablemente "Límites de pedidos de clientes" o similar, accesible desde la página de configuración del módulo o una entrada de menú dedicada.
  - `controllers/admin/index.php`
    - **Nombre de la clase**: (No es una clase, normalmente un archivo vacío o una redirección por seguridad)
    - **Responsabilidad**: Este archivo suele ser un marcador de posición o una medida de seguridad para evitar la lista directa de directorios. No contiene lógica de controlador activa.

### 4.3 Clases y modelos principales (`classes/`)

Según la información proporcionada, no se identificaron clases personalizadas explícitas en el directorio `classes/`. Sin embargo, `AdminLimitOrdersUserController` implica fuertemente la existencia de una clase `ObjectModel`, probablemente llamada `LimitOrdersUser`, que se asignaría a una tabla de base de datos personalizada (por ejemplo, `ps_limitorders_user`). Este `ObjectModel` definiría campos como `id_customer` y `max_orders`.

### 4.4 Activos JavaScript (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`
  - **Alcance**: Probablemente Back-office.
  - **Propósito**: Proporciona funcionalidad de autocompletado, probablemente para buscar y seleccionar clientes dentro del formulario `AdminLimitOrdersUserController` al establecer límites individuales. Se vincularía a los campos de entrada, enviaría solicitudes AJAX a un controlador de backend (posiblemente el propio `AdminLimitOrdersUserController` o un endpoint AJAX dedicado) y mostraría sugerencias.
- `views/js/limitorders.js`
  - **Alcance**: Potencialmente tanto Front-office (para mostrar mensajes) como Back-office (para la funcionalidad general del módulo).
  - **Propósito**: Este archivo contendría la lógica JavaScript central del módulo. En el Back-office, podría manejar validaciones de formularios o elementos dinámicos de la interfaz de usuario en las páginas de configuración. En el Front-office, si se necesitan mensajes o interacciones dinámicas cuando un cliente alcanza su límite (por ejemplo, una ventana emergente modal, actualización dinámica del carrito), este script lo gestionaría.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`
  - **Alcance**: Estilo de administración del Back-office.
  - **Propósito**: Estiliza el menú desplegable de autocompletado y los campos de entrada utilizados en el panel de administración, asegurando una experiencia de búsqueda consistente y fácil de usar para los clientes.
- `views/css/limitorders.css`
  - **Alcance**: Tanto Front-office como Back-office.
  - **Propósito**: Contiene el estilo general para cualquier elemento visible introducido por el módulo. En el Back-office, estilizaría los formularios y tablas de configuración. En el Front-office, estilizaría los mensajes mostrados a los clientes cuando alcanzan su límite de pedidos, asegurando que se integren bien con el tema de la tienda.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - Este módulo no lista explícitamente plantillas en el directorio `hook/`, pero su funcionalidad implica que se engancharía a `displayShoppingCart` o `displayShoppingCartFooter` para mostrar mensajes.
- **Plantillas de administración (`views/templates/admin/`)**:
  - Las plantillas para `AdminLimitOrdersUserController` (por ejemplo, `list.tpl`, `form.tpl`) residirían aquí, definiendo la estructura de la interfaz de gestión de límites de clientes.
- **Plantillas de Front-office (`views/templates/front/`)**:
  - `views/templates/front/displayShoppingCart.tpl`
    - **Propósito**: Esta plantilla probablemente se renderiza cuando el módulo se engancha a `displayShoppingCart`. Contendría la lógica para mostrar un mensaje al cliente *dentro de su carrito de compras* si ha alcanzado su límite de pedidos, impidiéndole continuar con el proceso de compra.
  - `views/templates/front/displayShoppingCartEmpty.tpl`
    - **Propósito**: Esta plantilla podría usarse en un escenario específico donde el módulo necesita mostrar un mensaje relacionado con los límites de pedidos incluso cuando el carrito está vacío, o como una visualización de mensaje de respaldo/alternativa. Su caso de uso exacto dependería de la lógica interna del módulo para diferentes estados.
- `lib/searchTool/views/scripts.tpl`
  - **Propósito**: Esta plantilla probablemente incluye los archivos JavaScript y CSS necesarios para los componentes `autocomplete.js` y `autocomplete.css`, asegurando que se carguen correctamente en el Back-office.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:
  - `ps_configuration`: Almacena el número máximo global de pedidos permitidos (por ejemplo, `LIMITORDERS_MAX_ORDERS`).
  - `ps_limitorders_user`: (Tabla personalizada implícita) Almacena los límites de pedidos de clientes individuales.
    - `id_limitorders_user` (Clave primaria)
    - `id_customer` (Clave externa a `ps_customer`)
    - `max_orders` (INT, el número máximo de pedidos permitidos para este cliente específico)
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza en la sección `<head>` de todas las páginas del front-office. | Potencialmente para cargar activos CSS/JS del front-office o para verificaciones tempranas. |
| `displayRightColumn` / `displayLeftColumn` | Se renderiza en la columna derecha/izquierda de las páginas del front-office. | Podría usarse para mostrar un mensaje sutil sobre los límites de pedidos, aunque es menos probable para este módulo. |
| `displayProductButtons` / `displayProductExtraContent` | Se renderiza en la página del producto. | Podría usarse para mostrar un mensaje si un cliente ha alcanzado su límite y no puede añadir al carrito. |
| `displayShoppingCart` | Se renderiza dentro del resumen del carrito de compras. | **CRÍTICO:** Probablemente se usa para mostrar mensajes al cliente si ha alcanzado su límite de pedidos, impidiendo el proceso de compra. |
| `displayShoppingCartFooter` | Se renderiza debajo del resumen del carrito de compras. | Similar a `displayShoppingCart`, para mostrar mensajes o advertencias. |
| `displayFooter` | Se renderiza en el pie de página de todas las páginas del front-office. | Menos probable para la funcionalidad principal, posiblemente para información general del módulo o scripts. |
| `actionValidateOrder` | Se ejecuta *después* de que un pedido ha sido validado y guardado con éxito en la base de datos. | **CRÍTICO:** Este hook es esencial para que el módulo incremente el recuento de pedidos de un cliente y potencialmente actualice su estado si ha alcanzado su límite. |
| `actionBeforeCartUpdateQuantity` | Se ejecuta antes de que se actualice la cantidad de un producto en el carrito. | Podría usarse para realizar una verificación preliminar de los límites antes de permitir que se agregue/actualice un artículo. |
| `actionFrontControllerSetMedia` | Permite añadir CSS/JS a las páginas del front-office. | Se utiliza para cargar `limitorders.js` y `limitorders.css` en las páginas relevantes del front-office. |
| `actionAdminControllerSetMedia` | Permite añadir CSS/JS a las páginas del back-office. | Se utiliza para cargar CSS/JS específicos de administración para la configuración y las pantallas de `AdminLimitOrdersUserController`. |
| `displayBackOfficeHeader` | Se renderiza en la sección `<head>` de todas las páginas del back-office. | Para cargar CSS/JS específicos de administración o mostrar avisos de administración. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Limitar el número de pedidos permitidos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar que su módulo funcione perfectamente y le ayude a alcanzar sus objetivos de comercio electrónico.

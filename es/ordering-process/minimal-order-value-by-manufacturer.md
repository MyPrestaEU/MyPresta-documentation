---
title: "Valor mínimo de pedido por fabricante - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Valor mínimo de pedido por fabricante' de MyPresta.eu."
sidebar:
  label: "Valor mínimo de pedido por fabricante - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Minimal order value by manufacturer en MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-manufacturer.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/minimal-order-value-by-manufacturer/)
>
> ---


# Valor mínimo de pedido por fabricante

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo, accesible directamente después de la instalación o haciendo clic en "Configurar" junto al módulo en el Gestor de módulos.

- **Qué hace esta pantalla:** Esta página le permite habilitar/deshabilitar el módulo y gestionar los ajustes principales que controlan su comportamiento.

#### Ajustes y Opciones

- **Habilitar / Deshabilitar Módulo:**

  - **Qué hace este ajuste:** Este es un interruptor global para activar o desactivar la funcionalidad completa del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El módulo comprobará activamente los valores mínimos de pedido por fabricante en los carritos de los clientes y aplicará restricciones si no se cumplen las condiciones.
    - *Cuando está deshabilitado:* El módulo dejará de funcionar. No se realizarán comprobaciones de valor mínimo de pedido, y los clientes podrán pedir cualquier cantidad de cualquier fabricante.
  - **Valor recomendado:** **SÍ** (para activar la función principal del módulo).
  - **Escenario / ejemplo de comerciante:** Si está probando el módulo o desea deshabilitar temporalmente todas las reglas de pedido mínimo sin eliminarlas, puede desactivarlo.
- **Mostrar mensaje en la página del carrito de compras:**

  - **Qué hace este ajuste:** Controla si se muestra un mensaje de advertencia al cliente en la página del carrito de compras si no se cumple el valor mínimo de pedido de un fabricante.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes verán un mensaje claro e informativo en la página de su carrito, indicando qué mínimo de fabricante no se cumple y cuánto más necesitan añadir.
    - *Cuando está deshabilitado:* No aparecerá ningún mensaje en la página del carrito. La restricción seguirá aplicándose, pero el cliente podría descubrirla más tarde durante el pago, lo que podría generar frustración.
  - **Valor recomendado:** **SÍ**.
  - **Escenario / ejemplo de comerciante:** Habilitar esto proporciona una mejor experiencia de usuario, guiando a los clientes a resolver el problema temprano en lugar de sorprenderlos en el pago.
- **Mostrar mensaje en la página de pago:**

  - **Qué hace este ajuste:** Controla si se muestra un mensaje de advertencia al cliente en la página de pago si no se cumple el valor mínimo de pedido de un fabricante.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes verán un mensaje en la página de pago, impidiéndoles completar el pedido hasta que se cumpla el mínimo.
    - *Cuando está deshabilitado:* El proceso de pago podría simplemente detenerse sin una explicación clara, o el módulo podría impedir el avance sin un mensaje específico, lo que puede confundir a los clientes.
  - **Valor recomendado:** **SÍ**.
  - **Escenario / ejemplo de comerciante:** Esto es crucial para evitar pedidos que no cumplan sus criterios y para comunicar claramente la razón al cliente.
- **Mensaje a mostrar (para las páginas del carrito de compras y de pago):**

  - **Qué hace este ajuste:** Le permite personalizar el texto del mensaje de advertencia que se muestra a los clientes cuando no se cumple un valor mínimo de pedido. Puede usar marcadores de posición como `{manufacturer_name}` y `{missing_amount}`.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se cambia:* El mensaje personalizado aparecerá en el front office.
    - *Cuando se deja por defecto:* Se utilizará un mensaje estándar.
  - **Valor recomendado:** Personalizar para que sea claro y útil. Ejemplo: "Para completar su pedido, necesita añadir {missing\_amount} más de productos de {manufacturer\_name}."
  - **Escenario / ejemplo de comerciante:** Es posible que desee que el mensaje sea más amigable, incluya una llamada a la acción o se alinee con el tono de voz de su marca.

### 2.2 Pantallas de administración dedicadas: Reglas de valor mínimo de pedido por fabricante (Back Office > Catálogo > Valor mínimo de pedido por fabricante)

Esta pantalla es donde define y gestiona las reglas reales de valor mínimo de pedido para cada fabricante.

- **Nombre de la pantalla y ubicación del menú:** "Valor mínimo de pedido por fabricante" en el menú **Catálogo**.
- **Qué hace esta pantalla:** Esta es un área de gestión dedicada para añadir, editar y eliminar reglas para los valores mínimos de pedido por fabricante. Presenta una lista de todas las reglas configuradas actualmente.

#### Acciones y Ajustes Disponibles

- **Lista de Reglas:**

  - **Qué hace:** Muestra una tabla de todas las reglas de valor mínimo de pedido existentes. Cada fila suele mostrar el nombre del fabricante, el valor mínimo establecido y las opciones para editar o eliminar la regla.
  - **Efecto de los cambios:** Esta tabla proporciona una visión general de todas las reglas activas.
  - **Flujo de trabajo recomendado:** Revise regularmente esta lista para asegurarse de que sus reglas estén actualizadas con sus necesidades comerciales.
- **Botón "Añadir nueva regla":**

  - **Qué hace:** Al hacer clic en este botón, se accede a un formulario donde puede crear una nueva regla de valor mínimo de pedido.
  - **Efecto de los cambios:** Abre un nuevo formulario.
  - **Flujo de trabajo recomendado:** Utilícelo cuando necesite establecer un nuevo mínimo para un fabricante que aún no está en la lista.
- **Botón "Editar" (para cada regla):**

  - **Qué hace:** Le permite modificar la configuración de una regla existente.
  - **Efecto de los cambios:** Abre el formulario de la regla con los datos precargados, lo que le permite cambiar el fabricante o el valor mínimo.
  - **Flujo de trabajo recomendado:** Utilícelo para ajustar los mínimos en función de nuevos acuerdos con proveedores o estrategias de ventas.
- **Botón "Eliminar" (para cada regla):**

  - **Qué hace:** Elimina una regla específica de valor mínimo de pedido.
  - **Efecto de los cambios:** La regla se elimina inmediatamente y el fabricante asociado ya no tendrá un requisito de valor mínimo de pedido.
  - **Flujo de trabajo recomendado:** Utilícelo cuando un fabricante ya no requiera un pedido mínimo, o si va a descatalogar una marca.

#### Formulario Añadir/Editar Regla

Al añadir una nueva regla o editar una existente, normalmente verá los siguientes campos:

- **Fabricante:**

  - **Qué hace este ajuste:** Este campo le permite seleccionar el fabricante específico al que se aplicará esta regla de valor mínimo de pedido. Normalmente cuenta con una búsqueda autocompletar para ayudarle a encontrar fabricantes fácilmente.
  - **Efecto de cambiar este ajuste:** Vincula la regla a un fabricante en particular.
  - **Valor recomendado:** Seleccione el fabricante exacto al que desea aplicar la regla.
  - **Escenario / ejemplo de comerciante:** Podría seleccionar "Apple" para establecer un mínimo para todos los productos de Apple, o "Samsung" para los productos de Samsung.
- **Valor mínimo de pedido:**

  - **Qué hace este ajuste:** Aquí es donde introduce el valor numérico (en la moneda predeterminada de su tienda, por ejemplo, USD, EUR) que representa la cantidad total mínima requerida para los productos del fabricante seleccionado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un valor (por ejemplo, 50.00):* Los clientes deben tener al menos 50.00 en productos del fabricante seleccionado en su carrito para continuar.
    - *Cuando se establece en 0 o se deja vacío:* Esto deshabilita efectivamente el mínimo para ese fabricante (aunque es mejor eliminar la regla si no se necesita un mínimo).
  - **Valor recomendado:** Un valor numérico positivo que refleje sus requisitos comerciales.
  - **Escenario / ejemplo de comerciante:** Si su proveedor de "MarcaX" le exige que pida al menos 100 $ de sus productos, usted establecería esto en "100.00" para "MarcaX".

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar / Deshabilitar Módulo | SÍ | Interruptor global para la funcionalidad del módulo. |
| Configuración del módulo | Mostrar mensaje en la página del carrito de compras | SÍ | Muestra advertencia en el carrito si no se cumple el mínimo. |
| Configuración del módulo | Mostrar mensaje en la página de pago | SÍ | Muestra advertencia en el pago si no se cumple el mínimo. |
| Configuración del módulo | Mensaje a mostrar | Personalizable | Personaliza el texto del mensaje de advertencia. |
| AdminMobmController | Fabricante (Añadir/Editar Regla) | Seleccionar de la lista | Vincula la regla a un fabricante específico. |
| AdminMobmController | Valor mínimo de pedido (Añadir/Editar Regla) | Valor numérico | Establece el valor total mínimo para los productos del fabricante seleccionado. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: He establecido un mínimo, pero no funciona en el front office. ¿Qué debo comprobar?**
R1:

- **¿Está habilitado el módulo?** Vaya a `Módulos > Gestor de módulos` y asegúrese de que "Valor mínimo de pedido por fabricante" esté activo.
- **¿Está habilitada la regla específica?** Compruebe en `Catálogo > Valor mínimo de pedido por fabricante` que la regla para el fabricante en cuestión esté configurada correctamente con un valor positivo.
- **Borrar caché:** Vaya a `Parámetros avanzados > Rendimiento` y haga clic en "Borrar caché" (para todas las cachés). A veces, la caché de PrestaShop puede impedir que los cambios aparezcan inmediatamente.
- **Comprobar conflictos:** Deshabilite temporalmente otros módulos que modifiquen el carrito o el proceso de pago para ver si hay un conflicto.

**P2: El mensaje en la página del carrito/pago no aparece.**
R2:

- **Compruebe la configuración del módulo:** Vaya a `Módulos > Gestor de módulos > Configurar` para "Valor mínimo de pedido por fabricante". Asegúrese de que "Mostrar mensaje en la página del carrito de compras" y "Mostrar mensaje en la página de pago" estén ambos configurados en **SÍ**.
- **¿Realmente no se cumple el mínimo?** Vuelva a comprobar que los productos del carrito del fabricante específico realmente están por debajo del mínimo establecido.

**P3: ¿Puedo establecer mínimos diferentes para diferentes grupos de clientes?**
R3: Este módulo, en su forma estándar, aplica un único valor mínimo por fabricante a todos los clientes. Si necesita mínimos específicos para grupos de clientes, esto requeriría un desarrollo personalizado o un módulo diferente.

**P4: ¿Cómo maneja el módulo las tiendas multidivisa?**
R4: El módulo utiliza la moneda predeterminada de su tienda (tal como se define en `Localización > Monedas` y `Localización > Localización`) para el "Valor mínimo de pedido" que usted establece. Convertirá automáticamente el total del carrito del cliente a la moneda predeterminada para la comparación, asegurando la coherencia.

**P5: El módulo parece ralentizar mi sitio. ¿Qué puedo hacer?**
R5:

- **Borrar caché:** Asegúrese de que todas las cachés se borren regularmente (`Parámetros avanzados > Rendimiento`).
- **Recursos del servidor:** Compruebe los recursos de su entorno de alojamiento (CPU, RAM). Si su tienda tiene un número muy grande de fabricantes o productos, asegúrese de que su servidor pueda manejar la carga.
- **Actualizaciones del módulo:** Utilice siempre la última versión del módulo de MyPresta.eu, ya que las actualizaciones a menudo incluyen mejoras de rendimiento.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Valor mínimo de pedido por fabricante" para desarrolladores y webmasters.

### 4.1 Visión general de la arquitectura

El módulo sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop. Principalmente extiende `Module` para su funcionalidad y configuración principales, utiliza `AdminController` para la gestión de reglas en el back-office y `ModuleFrontController` para las interacciones AJAX en el front-office relacionadas con la validación del carrito. No parece utilizar clases `ObjectModel` personalizadas, sino que se basa en `Configuration` para la configuración general y la interacción directa con la base de datos (o potencialmente una estructura de array simple) para las reglas específicas del fabricante. Los hooks se utilizan ampliamente para integrarse en el flujo del carrito y del pago.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `controllers/front/ajax.php`
  - **Nombre de la clase:** `MobmAjaxModuleFrontController` (probablemente, basado en la convención de nombres de archivos) que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador es probablemente responsable de manejar las solicitudes AJAX desde el front-office, particularmente aquellas relacionadas con las actualizaciones del carrito o la progresión del pago. Recibiría los datos del carrito, realizaría las comprobaciones del valor mínimo de pedido y devolvería una respuesta JSON indicando si se cumplen las condiciones y qué mensajes deben mostrarse. Esto es crucial para las actualizaciones dinámicas sin recargas completas de la página.
- `controllers/front/index.php`
  - **Nombre de la clase:** `MobmIndexModuleFrontController` (probablemente) que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este archivo podría ser un marcador de posición o usarse para una página simple del front-office si el módulo tuviera una. Dado el propósito del módulo, es menos probable que renderice una página completa y más probable que sea un respaldo o parte de una cadena de redirección si `ajax.php` es el punto de interacción principal.

#### Controladores de administración del Back-Office

- `controllers/admin/AdminMobm.php`
  - **Nombre de la clase:** `AdminMobmController` que extiende `ModuleAdminController`.
  - **Nombre de la pestaña:** "Valor mínimo de pedido por fabricante" (en Catálogo).
  - **Entidad gestionada:** Gestiona la entidad `mobm`, que representa las reglas individuales de valor mínimo de pedido para los fabricantes.
  - **Responsabilidad:** Este es el controlador principal para gestionar la lista de reglas de pedido mínimo del fabricante. Maneja:
    - Mostrar la lista de reglas existentes (usando `renderList()`).
    - Añadir nuevas reglas (usando `renderForm()` para el formulario de añadir).
    - Editar reglas existentes (usando `renderForm()` para el formulario de editar).
    - Eliminar reglas.
    - Validación de formularios y guardado de datos.
    - Probablemente interactúa con la tabla `ps_configuration` o una tabla personalizada para almacenar el ID del fabricante y su valor mínimo asociado.
- `controllers/admin/index.php`
  - **Nombre de la clase:** `AdminMobmIndexModuleAdminController` (probablemente) que extiende `ModuleAdminController`.
  - **Responsabilidad:** Similar al `index.php` del front-office, esto podría ser un marcador de posición o un punto de entrada predeterminado. En PrestaShop, los archivos `index.php` en los directorios de controladores a menudo sirven como medidas de seguridad básicas (por ejemplo, `die('Acceso Denegado');`) o enrutamiento simple si no se manejan explícitamente por un controlador más específico.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo indica que no hay clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo:

1. Almacena sus reglas de fabricante directamente en la tabla `ps_configuration` (por ejemplo, como un array serializado).
2. Utiliza consultas directas a la base de datos dentro del archivo principal del módulo o del controlador de administración para gestionar una tabla personalizada.
3. Gestiona los datos como un array simple dentro del contexto del módulo sin un `ObjectModel` formal.

Dado que `AdminMobmController` gestiona una entidad `mobm`, es muy probable que se cree una tabla personalizada (por ejemplo, `ps_mobm`) durante la instalación, y `AdminMobmController` maneje implícitamente las operaciones CRUD para esta tabla sin una clase `ObjectModel` dedicada en `classes/`. La `$definition` para esta entidad se definiría entonces directamente dentro de `AdminMobmController` o el archivo principal del módulo.

### 4.4 Activos JavaScript (`views/js/`)

- `mobm/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office (probablemente para el formulario `AdminMobmController`).
  - **Responsabilidad:** Proporciona funcionalidad de autocompletado para seleccionar fabricantes en el formulario "Añadir/Editar Regla". Escucha la entrada del usuario en un campo de texto, envía solicitudes AJAX a un controlador del back-office (por ejemplo, `AdminManufacturers` o un método `AdminMobm` personalizado) para obtener nombres de fabricantes coincidentes y muestra sugerencias.
- `mobm/views/js/mobm.js`
  - **Alcance:** Front-office.
  - **Responsabilidad:** Este es el JavaScript principal del front-office para el módulo. Probablemente:
    - Se vincula a eventos en la página del carrito de compras (por ejemplo, cambios de cantidad, eliminación de productos).
    - Se vincula a eventos en la página de pago (por ejemplo, clics en el botón "Proceder al pago").
    - Envía solicitudes AJAX a `controllers/front/ajax.php` para validar el carrito contra los mínimos del fabricante.
    - Recibe respuestas JSON y actualiza dinámicamente la interfaz de usuario con mensajes de advertencia o impide la progresión si no se cumplen los mínimos.
    - Podría manejar ventanas emergentes modales o señales visuales para el cliente.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `mobm/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Estiliza el menú desplegable de autocompletado y el campo de entrada utilizados para la selección del fabricante en el formulario de administración.
  - **Selectores de clase CSS clave:** Probablemente apunta a clases como `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`, etc.
- `mobm/views/css/mobm.css`
  - **Alcance:** Front-office.
  - **Responsabilidad:** Estiliza los mensajes de advertencia que se muestran en las páginas del carrito de compras y de pago. Asegura que estos mensajes sean visualmente distintos y se integren bien con el tema.
  - **Selectores de clase CSS clave:** Probablemente apunta a clases personalizadas añadidas por el módulo a los contenedores de mensajes de advertencia, por ejemplo, `.mobm-warning-message`, `.mobm-error-block`.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- `mobm/lib/searchTool/views/scripts.tpl`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Esta plantilla probablemente incluye el JavaScript necesario para la funcionalidad de autocompletado (de `autocomplete.js`) y potencialmente algún script o configuración en línea para ello. Se renderizaría dentro del método `renderForm()` de `AdminMobmController`.
- `mobm/views/templates/front/displayShoppingCart.tpl`
  - **Alcance:** Front-office.
  - **Hook:** Esta plantilla está diseñada para ser renderizada en un hook que muestra contenido en la página del carrito de compras, como `displayShoppingCartFooter` o `displayBeforeShoppingCartBlock`.
  - **Responsabilidad:** Muestra el mensaje de advertencia al cliente si no se cumple el valor mínimo de pedido de un fabricante. Contendrá la lógica para mostrar el mensaje solo cuando `{$mobm_warning_message}` (o una variable similar pasada desde el módulo) no esté vacío.

### 4.7 Esquema de la base de datos y mapa de Hooks

#### Tablas de la base de datos

- **`ps_configuration`**: Almacena la configuración general del módulo (por ejemplo, `PS_MOVB_ENABLED`, `PS_MOVB_CART_MSG_ENABLED`, `PS_MOVB_CHECKOUT_MSG_ENABLED`, `PS_MOVB_CUSTOM_MESSAGE`).
- **`ps_mobm` (Probablemente tabla personalizada)**: Esta tabla es muy probable dada la gestión de una entidad `mobm` por parte de `AdminMobmController`.
  - **Columnas (Hipotéticas):**
    - `id_mobm` (Clave primaria, INT)
    - `id_manufacturer` (INT, Clave foránea a `ps_manufacturer`)
    - `min_value` (DECIMAL(20,6), almacena el importe mínimo del pedido)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de todas las páginas del front-office. | Para incluir los activos CSS (`mobm.css`) y JavaScript (`mobm.js`) del front-office. |
| `actionCartSave` | Después de guardar un carrito (por ejemplo, cambio de cantidad, producto añadido/eliminado). | Para realizar la validación en tiempo real de los mínimos del fabricante y potencialmente almacenar el estado de la validación. |
| `actionValidateOrder` | Antes de que un pedido sea validado oficialmente. | Para evitar la validación del pedido si no se cumplen los mínimos del fabricante. |
| `displayShoppingCartFooter` (o similar) | En la parte inferior de la página del carrito de compras. | Para mostrar el mensaje de advertencia (`displayShoppingCart.tpl`) si no se cumplen los mínimos. |
| `displayPaymentTop` (o hook de pago similar) | En la parte superior del paso de selección de pago en el proceso de pago. | Para mostrar el mensaje de advertencia e impedir la progresión si no se cumplen los mínimos. |
| `displayAdminProductsExtra` (o similar) | En la página de edición de productos en el back office. | Potencialmente para mostrar información sobre el valor mínimo del fabricante directamente en las páginas de productos (menos probable pero posible). |
| `displayBackOfficeHeader` | En la sección `<head>` de todas las páginas del back-office. | Para incluir los activos CSS (`autocomplete.css`) y JavaScript (`autocomplete.js`) del back-office para el formulario `AdminMobmController`. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y para asegurarse de que está ejecutando la última versión y la más compatible del módulo "Valor mínimo de pedido por fabricante", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.

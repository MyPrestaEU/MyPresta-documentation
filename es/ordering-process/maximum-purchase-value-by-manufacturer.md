---
title: "Valor máximo de compra por fabricante - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Valor máximo de compra por fabricante' de MyPresta.eu."
sidebar:
  label: "Valor máximo de compra por fabricante - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Maximum purchase value by manufacturer en MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-manufacturer.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/maximum-purchase-value-by-manufacturer/)
>
> ---


# Valor máximo de compra por fabricante

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde puede habilitar o deshabilitar el módulo y acceder al área de gestión dedicada para configurar los límites del fabricante.

- **Qué hace esta configuración:** Esta sección suele contener un simple interruptor para habilitar o deshabilitar la funcionalidad principal del módulo. También proporciona un enlace directo a la pantalla dedicada donde se definen los valores máximos de compra reales para los fabricantes.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado:* El módulo verificará activamente los carritos de los clientes con los límites de fabricante definidos y evitará pedidos si se exceden los límites.
  - *Cuando está deshabilitado:* El módulo dejará de funcionar y no se aplicarán límites de compra por fabricante.
- **Valor recomendado:** "SÍ" (Habilitado) si tiene la intención de utilizar las funciones del módulo.
- **Escenario / ejemplo de comerciante:** Acaba de instalar el módulo y desea comenzar a establecer límites. Lo habilitaría aquí y luego pasaría a la sección "Gestionar límites de fabricante".

### 2.2 Pantalla de Administración Dedicada: Límites de Fabricante (Back Office > Módulos > Valor máximo de compra por fabricante > Configurar > Botón "Gestionar límites de fabricante" o una entrada de menú dedicada)

Esta pantalla es donde usted define y gestiona los valores máximos de compra reales para cada fabricante. Típicamente, presentará una lista de sus fabricantes y le permitirá añadir, editar o eliminar reglas.

**Nombre de la pantalla y ubicación del menú:**
Accederá a esta pantalla haciendo clic en el botón "Configurar" junto al módulo en el Gestor de Módulos, y luego probablemente haciendo clic en un botón prominente como "Gestionar límites de fabricante" o "Añadir nueva regla". Alternativamente, el módulo podría crear un nuevo elemento de menú bajo "Catálogo" o "Parámetros de la tienda" para acceder directamente a `AdminMaobm`.

**Acciones y configuraciones disponibles:**

1. **Tabla de listado de reglas existentes:**

   - Verá una tabla que enumera todos los límites de fabricante que ya ha configurado.
   - Las columnas suelen incluir: Nombre del fabricante, Valor máximo y acciones como "Editar" o "Eliminar".
   - **Efecto de los cambios:** Esta tabla proporciona una visión general de sus reglas activas. Eliminar una regla eliminará el límite de compra para ese fabricante específico.
   - **Flujo de trabajo recomendado:** Revise regularmente esta tabla para asegurarse de que sus límites estén actualizados con sus necesidades comerciales.
2. **Formulario para añadir / editar regla:**

   - Cuando haga clic en "Añadir nuevo" o "Editar" una regla existente, normalmente verá un formulario con los siguientes campos:
     - **Fabricante:** Una lista desplegable o un cuadro de búsqueda para seleccionar el fabricante al que desea aplicar el límite.
       - **Qué hace esta configuración:** Especifica a qué fabricante se aplica esta regla.
       - **Efecto de cambiar esta configuración:** La regla solo se aplicará a los productos asociados con el fabricante seleccionado.
       - **Valor recomendado:** Seleccione el fabricante específico que desea limitar.
       - **Escenario / ejemplo de comerciante:** Desea establecer un límite para los productos de "Acme Corp.", por lo que selecciona "Acme Corp." de la lista.
     - **Valor máximo de compra:** Un campo de entrada donde introduce el valor total máximo (en la moneda predeterminada de su tienda) que un cliente puede comprar del fabricante seleccionado en un solo pedido.
       - **Qué hace esta configuración:** Define el límite monetario para los productos del fabricante elegido.
       - **Efecto de cambiar esta configuración:** Si el valor total de los productos de este fabricante en el carrito de un cliente excede este número, se le impedirá realizar el pedido.
       - **Valor recomendado:** Un valor numérico que representa el total máximo permitido, por ejemplo, "500.00" para 500 unidades de su moneda predeterminada.
       - **Escenario / ejemplo de comerciante:** Desea limitar los productos de "Acme Corp." a un máximo de 500 € por pedido. Introduciría "500" aquí.
     - **Botón Guardar:** Para aplicar sus cambios.
       - **Efecto de los cambios:** Guarda la nueva regla o actualiza una existente en la base de datos, haciéndola activa inmediatamente.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

- **Configuración inicial:** Revise su lista de fabricantes e identifique aquellos para los que necesita establecer límites de compra. Añada una nueva regla para cada uno.
- **Monitoreo:** Esté atento a sus ventas e inventario. Si nota que los productos de un fabricante se compran en cantidades excesivas, o si los acuerdos con los proveedores cambian, vuelva a esta pantalla para ajustar o añadir nuevos límites.
- **Actualizaciones:** Cuando se añadan nuevos fabricantes a su tienda, considere si requieren una regla de límite de compra.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | Estado del Módulo (Habilitar/Deshabilitar) | Habilitado | Activa o desactiva la funcionalidad del módulo. |
| `AdminMaobmController` (Límites de Fabricante) | Fabricante | Seleccionar de la lista | Especifica el fabricante al que se aplica el límite. |
| `AdminMaobmController` (Límites de Fabricante) | Valor Máximo de Compra | Su límite monetario deseado (ej., 500.00) | Establece el valor total máximo para los productos del fabricante seleccionado en un solo pedido. Excederlo bloquea el proceso de pago. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Un cliente está intentando finalizar la compra, pero ve un mensaje sobre haber excedido un límite de fabricante. ¿Qué debo hacer?**
R: Esto significa que el módulo está funcionando según lo previsto. El cliente tiene demasiados artículos de un fabricante específico en su carrito, y el valor total de esos artículos excede el límite que usted estableció. Puede:
1. Aconsejar al cliente que reduzca la cantidad de artículos de ese fabricante.
2. Deshabilitar o ajustar temporalmente el límite para ese fabricante en la configuración del módulo si considera que el pedido es aceptable (pero tenga precaución con esto).

**P: He establecido un límite, pero parece que no funciona. Los clientes aún pueden pedir más del máximo.**
R:
1. **Verifique el estado del módulo:** Asegúrese de que el módulo esté habilitado en **Módulos > Gestor de módulos** y en su página de configuración principal.
2. **Verifique la regla:** Revise la regla que creó en la pantalla "Gestionar límites de fabricante". ¿Está seleccionado el fabricante correcto? ¿Está configurado correctamente el "Valor máximo de compra"?
3. **Borrar caché:** A veces, la caché de PrestaShop puede impedir que los cambios surtan efecto inmediatamente. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché".
4. **Fabricante del producto:** Asegúrese de que los productos en cuestión estén asignados correctamente al fabricante para el que estableció el límite. Verifique la configuración del producto en su catálogo.

**P: ¿Puedo establecer límites diferentes para diferentes grupos de clientes?**
R: Este módulo, en su forma estándar, aplica un único límite por fabricante a todos los clientes. Si necesita límites específicos para grupos de clientes, esto requeriría un desarrollo personalizado.

**P: El mensaje de advertencia no es claro o no coincide con el idioma/tema de mi tienda.**
R:
1. **Traducciones:** Vaya a **Internacional > Traducciones**, seleccione "Traducciones de módulos instalados", su tema y el módulo "Valor máximo de compra por fabricante". Puede personalizar el texto del mensaje de advertencia allí.
2. **Estilo del tema:** El módulo utiliza el estilo estándar de PrestaShop para sus mensajes. Si se ve fuera de lugar, su tema podría tener CSS personalizado que necesite ajuste. Un webmaster puede inspeccionar el archivo `maobm.css` y el CSS de su tema para que sea visualmente consistente.

**P: ¿Qué sucede si un producto no tiene un fabricante asignado?**
R: Los productos sin un fabricante asignado no estarán sujetos a ningún límite establecido por este módulo, ya que las reglas son específicas del fabricante.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Valor máximo de compra por fabricante" (`maobm`) sigue una arquitectura de módulo estándar de PrestaShop. Utiliza principalmente una clase `Module` para la instalación y configuración básica, un `AdminController` para gestionar los límites del fabricante y `FrontController`s para manejar las solicitudes AJAX e integrarse con el proceso del carrito del front-office. El módulo aprovecha el sistema de hooks de PrestaShop para inyectar su lógica en el flujo del carrito y del proceso de pago, evitando pedidos si se exceden los límites. Almacena su configuración en `ps_configuration` y gestiona los límites específicos del fabricante a través de una tabla de base de datos dedicada (aunque no se lista explícitamente un `ObjectModel`, implica una interacción directa con la base de datos o un `AdminController` simple que gestiona la configuración).

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**:

  - `controllers/front/ajax.php`
    - **Nombre de la clase**: `MaobmAjaxModuleFrontController` (implícito, extiende `ModuleFrontController`)
    - **Responsabilidad**: Este controlador probablemente maneja las solicitudes AJAX desde el front-office, como cuando un cliente actualiza su carrito. Reevaluaría los límites del fabricante y devolvería una respuesta (por ejemplo, un mensaje de advertencia o un estado que indique si el pedido puede continuar). Podría estar enganchado a `actionCartSave` o eventos similares para proporcionar retroalimentación en tiempo real.
  - `controllers/front/index.php`
    - **Nombre de la clase**: `MaobmIndexModuleFrontController` (implícito, extiende `ModuleFrontController`)
    - **Responsabilidad**: Este controlador podría servir como un respaldo o un punto de entrada simple, aunque su función principal podría ser mínima si `ajax.php` maneja la mayoría de las interacciones del front-end. Potencialmente podría mostrar un mensaje genérico o redirigir si se accede directamente.
- **Controladores de Administración del Back-Office**:

  - `controllers/admin/AdminMaobm.php`
    - **Nombre de la clase**: `AdminMaobmController` (extiende `ModuleAdminController`)
    - **Nombre de la pestaña**: Probablemente una pestaña personalizada creada por el módulo, o accesible a través de la página de configuración del módulo.
    - **Entidad gestionada**: Gestiona las reglas específicas de límite de fabricante. Proporciona la interfaz para listar, añadir, editar y eliminar estas reglas. Este controlador interactuaría directamente con la base de datos para almacenar y recuperar los IDs de fabricante y sus valores máximos asociados. Típicamente usaría `HelperList` para la tabla de resumen y `HelperForm` para el formulario de añadir/editar.
  - `controllers/admin/index.php`
    - **Nombre de la clase**: `AdminMaobmIndexController` (implícito, extiende `ModuleAdminController`)
    - **Responsabilidad**: Similar al `index.php` del front-office, esto podría ser un marcador de posición o una simple redirección. En PrestaShop, los archivos `index.php` en los directorios de controladores a menudo sirven como medidas de seguridad para evitar la lista directa de directorios.

### 4.3 Clases y Modelos Principales (`classes/`)

El inventario proporcionado indica que no hay clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo:

1. Manipula directamente las tablas de la base de datos (por ejemplo, `ps_maobm_limits`) utilizando `Db::getInstance()` en sus controladores o en el archivo principal del módulo.
2. Almacena toda la configuración en `ps_configuration` utilizando `Configuration::updateValue()`, con el `AdminMaobmController` gestionando estas entradas de configuración.
   Dada la característica de "número ilimitado de reglas", la interacción directa con la base de datos para una tabla personalizada es más probable que `ps_configuration` para almacenar múltiples límites de fabricante.

### 4.4 Activos JavaScript (`views/js/`)

- `views/js/maobm.js`
  - **Alcance**: Probablemente Front-office.
  - **Detalles**: Este script sería responsable de las interacciones del lado del cliente relacionadas con la funcionalidad del módulo. Podría:
    - Vincular escuchadores de eventos a las acciones de actualización del carrito (por ejemplo, cambios de cantidad, eliminación de productos).
    - Realizar llamadas AJAX a `controllers/front/ajax.php` para reevaluar los límites del fabricante en tiempo real sin una recarga completa de la página.
    - Mostrar mensajes de advertencia o deshabilitar el botón de pago si se exceden los límites, basándose en la respuesta AJAX.
    - Potencialmente integrarse con los eventos `prestashop.on` de PrestaShop para una mejor compatibilidad.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `views/css/maobm.css`
  - **Alcance**: Principalmente Front-office, posiblemente algunos estilos de Back-office para elementos personalizados.
  - **Detalles**: Esta hoja de estilo contendría las reglas CSS necesarias para dar estilo a los mensajes de advertencia mostrados al cliente en el carrito o en el proceso de pago. Podría definir clases para:
    - `#maobm-warning-message` o contenedores similares para el texto de error.
    - Estilo para botones de pago deshabilitados.
    - Asegurar la capacidad de respuesta en diferentes tamaños de pantalla.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular**: Busque clases como `.maobm-alert`, `.maobm-error-message` o IDs específicos utilizados para el contenedor de advertencia.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:

  - `views/templates/front/displayShoppingCart.tpl`
    - **Hook**: Esta plantilla probablemente se renderiza en un hook que aparece en la página del carrito de compras, como `displayShoppingCartFooter` o `displayShoppingCart`.
    - **Salida**: Sería responsable de mostrar el mensaje de advertencia al cliente si excede el límite de compra de un fabricante. Recibiría variables del módulo que indican si se excede un límite y el mensaje relevante a mostrar.
- **Plantillas de administración (`views/templates/admin/`)**: (No listadas explícitamente, pero implícitas por `AdminMaobmController`)

  - El `AdminMaobmController` normalmente usaría las plantillas `HelperList` y `HelperForm` de PrestaShop para su interfaz, pero podría tener archivos `.tpl` personalizados para partes específicas de su configuración o para mostrar una lista de reglas. Estos se encontrarían generalmente en `views/templates/admin/maobm/` o similar.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de la Base de Datos**:

  - `ps_maobm_limits` (Implícito): Una tabla personalizada para almacenar los límites del fabricante.
    - `id_maobm_limit` (Clave Primaria, AUTO_INCREMENT)
    - `id_manufacturer` (Clave Foránea a `ps_manufacturer.id_manufacturer`)
    - `max_value` (Decimal o Flotante, almacenando el valor máximo de compra permitido)
    - `date_add`, `date_upd` (Marcas de tiempo estándar de PrestaShop)
  - `ps_configuration`: El módulo podría almacenar configuraciones generales (como el estado de habilitado/deshabilitado del módulo) aquí.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza en la sección `<head>` de todas las páginas del front-office. | Para incluir los activos `maobm.css` y `maobm.js`. |
| `displayShoppingCart` o `displayShoppingCartFooter` | Renderiza contenido en la página del carrito de compras. | Para mostrar el mensaje de advertencia (`displayShoppingCart.tpl`) si se exceden los límites. |
| `actionCartSave` | Se ejecuta después de que un carrito se guarda o actualiza. | Para reevaluar los límites del fabricante y potencialmente actualizar el estado del carrito o mostrar mensajes. |
| `actionValidateOrder` | Se ejecuta antes de que un pedido sea validado oficialmente. | **CRÍTICO**: Para realizar una verificación final de los límites del fabricante y evitar la validación del pedido si se exceden los límites. Aquí residiría la lógica de bloqueo del pedido. |
| `displayAdminProductsExtra` (o similar) | Podría usarse para mostrar información del límite del fabricante directamente en la página de edición del producto en el BO. | (Opcional) Para proporcionar acceso rápido a la información del límite para el fabricante del producto. |
| `displayBackOfficeHeader` | Se renderiza en la sección `<head>` de todas las páginas del back-office. | Para incluir CSS/JS específicos del back-office para `AdminMaobmController`. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Valor máximo de compra por fabricante", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y configuración del módulo.

---
title: "Iniciar sesión como cliente - Manual del comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Iniciar sesión como cliente' de MyPresta.eu."
sidebar:
  label: "Iniciar sesión como cliente - Manual del comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Log in as customer en MyPresta.eu](https://mypresta.eu/modules/administration-tools/log-in-as-customer.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/log-in-as-customer/)
>
> ---


# Iniciar sesión como cliente

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

El módulo "Iniciar sesión como cliente" tiene una configuración muy sencilla. Después de la instalación, cuando haga clic en "Configurar", accederá a una pantalla simple.

**Nombre de la pantalla y ubicación del menú:** Back Office > Módulos > Gestor de módulos > Iniciar sesión como cliente > Configurar

En esta pantalla, normalmente encontrará una simple confirmación de que el módulo está instalado y listo. La funcionalidad principal de este módulo está integrada directamente en su lista de clientes, en lugar de requerir configuraciones extensas en una página de configuración dedicada.

- **Qué hace esta pantalla:** Esta página confirma la instalación del módulo y proporciona cualquier información básica o enlaces rápidos. Para "Iniciar sesión como cliente", su propósito principal es confirmar que el módulo está activo y listo para usar.
- **Efecto de cambiar la configuración:** No hay configuraciones complejas que cambiar aquí. La funcionalidad del módulo se activa al instalarlo.
- **Valor recomendado:** No hay valores específicos que establecer. Solo asegúrese de que el módulo esté instalado y habilitado.
- **Escenario / ejemplo del comerciante:** Después de la instalación, verá un mensaje que confirma que el módulo está activo. Luego puede proceder directamente a la sección Clientes de su Back Office para usar sus funciones.

### 2.2 Uso de la función "Iniciar sesión como cliente"

La funcionalidad principal de este módulo se accede directamente desde su lista de clientes de PrestaShop.

**Nombre de la pantalla y ubicación del menú:** Back Office > Clientes > Clientes

1. **Navegue a Clientes:** En su Back Office de PrestaShop, vaya al menú **Clientes** y luego haga clic en **Clientes**.
2. **Localice al cliente:** Encuentre al cliente con el que desea iniciar sesión en la lista de clientes. Puede usar las opciones de búsqueda y filtro para localizarlos rápidamente.
3. **Haga clic en el botón "Iniciar sesión como cliente":** Para cada cliente en la lista, ahora verá un botón adicional (a menudo un icono como una persona o una llave, o un botón de texto) en la columna "Acciones". Este botón es añadido por el módulo "Iniciar sesión como cliente".
   - **Qué hace este botón:** Cuando hace clic en este botón, el módulo realiza un proceso de inicio de sesión seguro. Cierra su sesión de administrador (temporalmente) y luego inicia sesión como el cliente seleccionado.
   - **Efecto de hacer clic en este botón:** Será redirigido inmediatamente al front office de su tienda. Verá la tienda exactamente como la ve ese cliente, incluyendo su carrito activo, historial de pedidos, direcciones y cualquier contenido o precio personalizado.
   - **Escenario / ejemplo del comerciante:** Un cliente informa un problema al agregar un producto específico a su carrito. Usted navega a "Clientes", encuentra su nombre, hace clic en "Iniciar sesión como cliente" y es llevado instantáneamente al front office como ellos. Luego puede intentar agregar el producto usted mismo, solucionar el problema o verificar el contenido de su carrito.
4. **Cerrar sesión como cliente:** Para volver a su sesión de administrador del Back Office, simplemente cierre sesión desde el front office (como si fuera un cliente normal). Esto finalizará la sesión del cliente, y luego podrá volver a iniciar sesión en su Back Office.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | (Sin configuraciones directas) | N/A | Confirma la instalación y la preparación del módulo. |
| Lista de clientes (Back Office) | Botón "Iniciar sesión como cliente" | N/A | Permite el inicio de sesión instantáneo en el front office como un cliente seleccionado para solucionar problemas y realizar pruebas. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He instalado el módulo, pero no veo el botón "Iniciar sesión como cliente" en la lista de clientes.**
R:

1. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
2. **Estado del módulo:** Asegúrese de que el módulo esté habilitado. Vaya a **Módulos > Gestor de módulos**, busque "Iniciar sesión como cliente" y verifique que esté activo.
3. **Compatibilidad del tema:** Aunque es raro, algunos temas muy personalizados pueden interferir con la visualización de nuevos botones. Si el problema persiste, póngase en contacto con el soporte de MyPresta.eu.
4. **Versión de PrestaShop:** Asegúrese de haber descargado la versión correcta del módulo para su instalación de PrestaShop.

**P: Cuando hago clic en el botón, soy redirigido al front office, pero no he iniciado sesión como cliente.**
R:

1. **Cookies del navegador:** Asegúrese de que su navegador acepte cookies. Intente borrar la caché y las cookies de su navegador, luego inténtelo de nuevo.
2. **Configuración de la sesión:** Verifique el archivo `config/defines.inc.php` de su PrestaShop para las configuraciones `_PS_COOKIE_DOMAIN_` y `_PS_COOKIE_PATH_`. Asegúrese de que estén configuradas correctamente para su dominio.
3. **Configuración del servidor:** Verifique que las configuraciones de sesión PHP de su servidor sean estándar y no demasiado restrictivas.

**P: ¿Puedo iniciar sesión como cliente y luego realizar acciones como hacer un pedido por ellos?**
R: Sí, puede. Sin embargo, tenga extrema precaución. Siempre obtenga el permiso explícito del cliente antes de realizar cualquier acción en su nombre, especialmente realizar pedidos o modificar datos personales. Generalmente, es una buena práctica usar esta función para ver y solucionar problemas, no para realizar cambios sin consentimiento.

**P: ¿Es seguro usar este módulo? ¿Almacena las contraseñas de los clientes?**
R: El módulo no almacena ni accede a las contraseñas de los clientes. Utiliza la gestión de sesiones interna de PrestaShop para simular un inicio de sesión de cliente, de manera similar a cómo funciona la funcionalidad "Olvidé mi contraseña" de PrestaShop al generar una sesión segura temporal. Está diseñado para ser seguro.

**P: ¿Qué sucede si inicio sesión como cliente y luego cierro mi navegador sin cerrar sesión?**
R: La sesión del cliente eventualmente caducará según la configuración de tiempo de espera de la sesión de su PrestaShop. Para volver a su panel de administración, simplemente navegue a la URL de su Back Office e inicie sesión nuevamente como administrador.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Iniciar sesión como cliente" (`lac`) es un módulo ligero de PrestaShop centrado principalmente en extender la funcionalidad de la lista de clientes del Back Office. Aprovecha las clases principales `Customer` y `Context` de PrestaShop para gestionar las sesiones de usuario y la redirección. El módulo inyecta JavaScript en el Back Office para agregar el botón "Iniciar sesión como cliente" y utiliza un controlador frontal dedicado para manejar el proceso de inicio de sesión seguro y la redirección al front office. Sigue una arquitectura de módulo estándar de PrestaShop, integrándose sin problemas sin tablas de base de datos personalizadas ni modelos de objetos complejos.

### 4.2 Controladores (`controllers/`)

- **Controladores del Front Office**:

  - `lac/controllers/front/index.php`
    - **Nombre de la clase**: `LacIndexModuleFrontController` (probablemente, según la convención de nombres de archivo)
    - **Clase padre**: `ModuleFrontController`
    - **Responsabilidad**: Este controlador probablemente sirve como punto de aterrizaje o de respaldo. Dado el controlador `login.php`, `index.php` podría ser menos crítico o manejar la configuración inicial/redirección si `login.php` es el controlador de acción principal. También podría ser un marcador de posición.
  - `lac/controllers/front/login.php`
    - **Nombre de la clase**: `LacLoginModuleFrontController` (probablemente)
    - **Clase padre**: `ModuleFrontController`
    - **Responsabilidad**: Este es el controlador principal para la funcionalidad "Iniciar sesión como cliente".
      - Recibe el ID del cliente a través de un parámetro GET o POST desde el Back Office.
      - Realiza los pasos necesarios para cerrar la sesión del administrador actual.
      - Luego inicia sesión de forma segura con el cliente especificado manipulando los objetos `Context` y `Customer` (por ejemplo, `Context::getContext()->customer = new Customer($id_customer); Context::getContext()->cookie->id_customer = $id_customer;`).
      - Luego redirige el navegador a la página de inicio del front office o a una página específica relacionada con el cliente (`my-account`, `history`, etc.).
- **Controladores de administración del Back Office**:

  - Ninguno. El módulo se integra directamente en la vista del controlador `AdminCustomers` existente a través de hooks y JavaScript.

### 4.3 Clases y modelos principales (`classes/`)

- Ninguno. Este módulo no introduce clases `ObjectModel` personalizadas ni tablas de base de datos. Opera directamente sobre los objetos nativos `Customer` y `Context` de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

Estos archivos JavaScript son responsables de inyectar el botón "Iniciar sesión como cliente" en la lista de clientes del Back Office y de manejar el evento de clic para iniciar el proceso de inicio de sesión. Los diferentes nombres de archivo sugieren ajustes de compatibilidad para varias versiones de PrestaShop.

- `lac/views/js/16customers.js`
  - **Alcance**: Back office (lista `AdminCustomers` de PrestaShop 1.6.x).
  - **Funcionalidad**: Este script se dirige a la tabla de la lista de clientes en PrestaShop 1.6.x. Probablemente utiliza selectores de jQuery para encontrar la columna "Acciones" de cada fila de cliente y agrega un nuevo botón o enlace. El controlador de clic para este botón construirá una URL que apunte al controlador frontal del módulo (`lac/controllers/front/login.php`) con el ID del cliente y redirigirá el navegador.
- `lac/views/js/176orders.js`
  - **Alcance**: Back office (vista de pedidos de PrestaShop 1.7.6.x).
  - **Funcionalidad**: Este script podría estar destinado a agregar un botón "Iniciar sesión como cliente" directamente desde la vista de pedidos en 1.7.6.x, permitiendo un acceso rápido al cliente asociado con un pedido específico. Extraería el ID del cliente de la página de detalles del pedido y lo usaría para la redirección de inicio de sesión.
- `lac/views/js/177orders.js`
  - **Alcance**: Back office (vista de pedidos de PrestaShop 1.7.7.x+).
  - **Funcionalidad**: Similar a `176orders.js`, pero adaptado para posibles cambios de DOM o diferentes estructuras de tabla en PrestaShop 1.7.7.x y versiones posteriores de la vista de pedidos.
- `lac/views/js/17carts.js`
  - **Alcance**: Back office (vista de carrito de PrestaShop 1.7.x).
  - **Funcionalidad**: Este script probablemente agrega el botón "Iniciar sesión como cliente" a la página de detalles del carrito del Back Office, permitiendo a un administrador iniciar sesión como el cliente asociado con un carrito específico.
- `lac/views/js/17customersview.js`
  - **Alcance**: Back office (lista `AdminCustomers` de PrestaShop 1.7.x, 8.x, 9.x).
  - **Funcionalidad**: Este es el script principal para inyectar el botón en la lista de clientes para las versiones modernas de PrestaShop. Se dirigirá a la lista `AdminCustomers`, identificará el ID del cliente para cada fila y agregará el botón de acción "Iniciar sesión como cliente". Utiliza la delegación de eventos para manejar los clics en estos botones agregados dinámicamente, construyendo la URL apropiada para el controlador `lac/controllers/front/login.php`.

### 4.5 Hojas de estilo CSS (`views/css/`)

- Ninguno. El módulo no incluye archivos CSS personalizados. Probablemente se basa en el estilo predeterminado de PrestaShop para los botones o utiliza estilos en línea si es necesario, o el botón es estilizado por el propio tema del Back Office.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- Ninguno. El módulo no utiliza plantillas Smarty personalizadas. Su integración en el Back Office es puramente a través de la inyección de JavaScript, y el inicio de sesión en el front office se maneja mediante una redirección directa desde el controlador.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:
  - El módulo no crea ninguna tabla de base de datos personalizada. Almacena su configuración (si la hay, aunque no se identificó explícitamente ninguna más allá del estado básico del módulo) en la tabla estándar `ps_configuration`.
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Se ejecuta en la sección `<head>` de cada página del Back Office. | Se utiliza para incluir los archivos JavaScript necesarios (`16customers.js`, `17customersview.js`, etc.) en el Back Office, específicamente cuando el controlador `AdminCustomers` está activo. Esto asegura que el botón "Iniciar sesión como cliente" se agregue a la lista de clientes. |
| `displayAdminCustomers` | Se ejecuta en la página del controlador `AdminCustomers`. | Este hook está diseñado específicamente para que los módulos agreguen contenido o acciones a la lista de clientes. El módulo podría usar este hook para renderizar una pequeña plantilla o inyectar directamente JavaScript para agregar el botón. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador del Back Office está configurando sus medios (JS/CSS). | Un hook más robusto para agregar JS/CSS condicionalmente según el controlador activo. El módulo lo usaría para cargar sus archivos JS específicos solo cuando esté en las páginas `AdminCustomers` o `AdminOrders`. |
| `displayAdminOrder` | Se ejecuta en la página del controlador `AdminOrders`. | Si el módulo agrega un botón "Iniciar sesión como cliente" a la vista de pedidos (como sugieren `176orders.js`, `177orders.js`), este hook se usaría para inyectar el JavaScript o el HTML del botón necesario. |
| `displayAdminCarts` | Se ejecuta en la página del controlador `AdminCarts`. | Si el módulo agrega un botón "Iniciar sesión como cliente" a la vista del carrito (como sugiere `17carts.js`), este hook se usaría. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial del módulo "Iniciar sesión como cliente", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta que pueda tener.

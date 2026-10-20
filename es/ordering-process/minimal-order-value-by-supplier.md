---
title: "Valor mínimo de pedido por proveedor - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Valor mínimo de pedido por proveedor' de MyPresta.eu."
sidebar:
  label: "Valor mínimo de pedido por proveedor - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Minimal order value by supplier en MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-supplier.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/minimal-order-value-by-supplier/)
>
> ---


# Valor mínimo de pedido por proveedor

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página principal de configuración del módulo. Aquí es donde puede habilitar o deshabilitar el módulo y acceder a la pantalla de gestión principal para sus mínimos de proveedor.

- **Qué hace este ajuste:** Esta pantalla sirve como centro neurálgico del módulo. Le permite habilitar o deshabilitar toda la funcionalidad del módulo y proporciona un enlace directo para gestionar sus valores mínimos de pedido por proveedor.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* El módulo verificará activamente los carritos de los clientes con respecto a sus valores mínimos de pedido por proveedor definidos y bloqueará el pago si no se cumplen los requisitos.
  - *Cuando está deshabilitado:* El módulo dejará de funcionar. No se realizarán comprobaciones de valor mínimo de pedido y los clientes podrán pagar independientemente de los totales de pedido por proveedor.
- **Valor recomendado:** "SÍ" (Habilitado) si tiene la intención de utilizar las funciones del módulo.
- **Escenario / ejemplo de comerciante:** Si está configurando el módulo por primera vez, lo habilitará aquí. Si necesita suspender temporalmente las reglas (por ejemplo, durante una promoción en toda la tienda donde desea permitir todos los pedidos), puede deshabilitarlo aquí.

En esta pantalla, también encontrará un botón o enlace para **"Gestionar Valores Mínimos de Pedido por Proveedor"**. Al hacer clic en él, accederá a la pantalla de administración dedicada donde definirá las reglas reales.

### 2.2 Pantallas de Administración Dedicadas y Vistas del Controlador

#### AdminMobsController (Back Office > Módulos > Valor mínimo de pedido por proveedor > Gestionar Valores Mínimos de Pedido)

Esta es la pantalla principal donde define y gestiona los valores mínimos de pedido para cada uno de sus proveedores.

- **Nombre de la Pantalla y Ubicación del Menú:** Accede a esta pantalla navegando a **Módulos > Gestor de Módulos**, buscando "Valor mínimo de pedido por proveedor", haciendo clic en "Configurar" y luego haciendo clic en el botón/enlace "Gestionar Valores Mínimos de Pedido por Proveedor".
- **Acciones y Ajustes Disponibles:**
  - **Tabla de Listado:** Esta pantalla muestra una tabla de todos los valores mínimos de pedido configurados actualmente. Cada fila suele mostrar:
    - **Nombre del Proveedor:** El nombre del proveedor al que se aplica la regla.
    - **Valor Mínimo de Pedido:** El monto monetario que los productos de este proveedor deben alcanzar en el carrito.
    - **Acciones:** Generalmente botones "Editar" y "Eliminar" para modificar o eliminar una regla existente.
  - **Botón Añadir Nueva Regla:** Un botón (por ejemplo, "Añadir Nuevo Valor Mínimo de Pedido") para crear una nueva regla.
  - **Formulario Añadir/Editar:** Al añadir una nueva regla o editar una existente, normalmente verá un formulario con los siguientes campos:
    - **Selección de Proveedor:** Un menú desplegable o campo de búsqueda para seleccionar uno de sus proveedores existentes.
    - **Valor Mínimo:** Un campo de entrada donde introduce el monto numérico mínimo de pedido requerido para los productos del proveedor seleccionado. Este valor estará en la moneda predeterminada de su tienda (por ejemplo, EUR, USD).
    - **Botón Guardar:** Para aplicar sus cambios.
- **Efecto de los cambios:**
  - *Añadir una regla:* Una vez guardada, el nuevo valor mínimo de pedido para el proveedor seleccionado se activa inmediatamente. Los clientes deberán cumplir este valor para los productos de ese proveedor.
  - *Editar una regla:* Modificar el valor mínimo o cambiar el proveedor para una regla existente actualiza el requisito activo.
  - *Eliminar una regla:* Elimina el requisito de valor mínimo de pedido para ese proveedor específico. Los clientes ya no estarán restringidos por una compra mínima de ese proveedor.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. **Identificar Proveedores:** Determine qué proveedores requieren valores mínimos de pedido según sus necesidades comerciales (por ejemplo, altos costos de envío, acuerdos de dropshipping).
  2. **Añadir Reglas:** Para cada proveedor identificado, haga clic en "Añadir Nuevo Valor Mínimo de Pedido", seleccione el proveedor, introduzca el monto mínimo y guarde.
  3. **Monitorear y Ajustar:** Revise regularmente sus acuerdos con los proveedores y los datos de ventas. Si un proveedor cambia sus términos, o si observa una tendencia de pedidos pequeños no rentables, vuelva a esta pantalla para ajustar o añadir nuevas reglas.
  4. **Probar:** Después de añadir o modificar reglas, siempre pruebe la funcionalidad añadiendo productos de los proveedores afectados a su carrito en el front office e intentando pagar.

#### index.php (mobs/controllers/admin/index.php)

Este archivo suele servir como un marcador de posición o un redirigidor dentro del directorio de controladores de administración y no presenta una pantalla de configuración directa al comerciante. Su función principal suele ser asegurar que el acceso directo al directorio se maneje con elegancia, a menudo redirigiendo a la configuración principal del módulo o a una página de error. Los comerciantes no interactuarán directamente con este archivo.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de Configuración del Módulo** | Habilitar/Deshabilitar Módulo | Habilitado | Controla si la funcionalidad del módulo (comprobaciones de valor mínimo de pedido) está activa o inactiva. |
| **AdminMobsController** | Añadir Nueva Regla (Proveedor) | N/A | Selecciona un proveedor al que aplicar una regla de valor mínimo de pedido. |
| **AdminMobsController** | Añadir Nueva Regla (Valor Mínimo) | N/A | Establece el umbral monetario para los productos del proveedor seleccionado. |
| **AdminMobsController** | Editar Regla (Proveedor) | N/A | Modifica el proveedor asociado a una regla existente. |
| **AdminMobsController** | Editar Regla (Valor Mínimo) | N/A | Cambia el umbral monetario para una regla de proveedor existente. |
| **AdminMobsController** | Eliminar Regla | N/A | Elimina un requisito de valor mínimo de pedido para un proveedor específico. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: He establecido un valor mínimo, pero no funciona en el carrito. ¿Qué debo revisar?**
R1:

1.  **¿Está el módulo habilitado?** Vaya a **Módulos > Gestor de Módulos**, busque "Valor mínimo de pedido por proveedor" y asegúrese de que esté habilitado.
2.  **¿Está la regla configurada correctamente?** Vaya a la pantalla "Gestionar Valores Mínimos de Pedido por Proveedor" y verifique que el proveedor esté seleccionado correctamente y que el valor mínimo se haya introducido como un número (sin símbolos de moneda).
3.  **¿Están los productos asignados correctamente al proveedor?** Verifique los productos en el carrito del cliente para asegurarse de que realmente estén asociados con el proveedor para el que ha establecido la regla.
4.  **Borrar Caché:** A veces, la caché de PrestaShop puede impedir que los cambios aparezcan inmediatamente. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché".

**P2: El mensaje de notificación aparece, pero no está en el idioma de mi tienda.**
R2: Los mensajes de front-office del módulo son traducibles.

1.  Vaya a **Internacional > Traducciones**.
2.  Seleccione "Traducciones de módulos instalados", elija su tema, seleccione su idioma y haga clic en "Modificar".
3.  Busque el módulo "mobs" (Valor mínimo de pedido por proveedor) y traduzca las cadenas relevantes. Guarde sus cambios.

**P3: El módulo está bloqueando el pago, pero quiero permitir una excepción para un cliente o pedido específico.**
R3: El módulo aplica las reglas globalmente. Para hacer una excepción, necesitaría deshabilitar temporalmente la regla del proveedor específico en la configuración del módulo (**Módulos > Valor mínimo de pedido por proveedor > Gestionar Valores Mínimos de Pedido**) o deshabilitar todo el módulo si hay varias reglas activas. Recuerde volver a habilitarlo después. No hay una función de "anulación" incorporada por cliente o pedido.

**P4: El módulo está activo, pero el estilo del mensaje de notificación no coincide con mi tema.**
R4: El módulo viene con un estilo básico. Si choca con su tema personalizado, su webmaster o desarrollador puede anular el CSS del módulo. El archivo CSS del módulo es `mobs/views/css/mobs.css`. Pueden añadir estilos personalizados al archivo `custom.css` o `theme.css` de su tema, apuntando a los elementos de notificación del módulo para que coincidan con la marca de su tienda.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Valor mínimo de pedido por proveedor" (`mobs`) sigue una arquitectura estándar de módulo de PrestaShop, aprovechando los principios MVC. Consiste principalmente en una clase de módulo principal, un controlador de administración dedicado para gestionar reglas y un controlador frontal para interacciones AJAX y mostrar notificaciones. No utiliza clases `ObjectModel` personalizadas, sino que almacena la configuración directamente en `ps_configuration` y gestiona los mínimos específicos del proveedor a través de `AdminMobsController`, que probablemente interactúa con una tabla personalizada o extiende un `AdminController` genérico para gestionar datos. La interacción con el front-office se maneja a través de una plantilla dedicada para el carrito de compras y un controlador AJAX para comprobaciones dinámicas.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `controllers/front/ajax.php`
    - **Nombre de la clase y clase padre**: `MobsAjaxModuleFrontController` extiende `ModuleFrontController`.
    - **Responsabilidad**: Este controlador es responsable de manejar las solicitudes AJAX desde el front-office, típicamente iniciadas desde la página del carrito de compras. Probablemente realiza comprobaciones en tiempo real del contenido del carrito con respecto a los valores mínimos de pedido por proveedor configurados. Devuelve respuestas JSON que indican si se cumplen los mínimos y proporciona mensajes relevantes si no. Esto permite actualizaciones dinámicas de la visualización del carrito sin recargas completas de la página.
  - `controllers/front/index.php`
    - **Nombre de la clase y clase padre**: `MobsIndexModuleFrontController` extiende `ModuleFrontController`.
    - **Responsabilidad**: Este controlador podría servir como un punto de entrada predeterminado para la parte de front-office del módulo, aunque su función principal suele ser redirigir o servir una página básica si el módulo no tiene una página de front-office dedicada. Dada la funcionalidad del módulo, es más probable que el controlador `ajax.php` maneje la lógica principal del front-office, y `index.php` sea una página de respaldo o mínima.
- **Controladores de Administración (Back-Office)**:

  - `controllers/admin/AdminMobs.php`
    - **Nombre de la clase y clase padre**: `AdminMobsController` extiende `ModuleAdminController`.
    - **Nombre de la pestaña y entidad gestionada**: Este controlador gestiona las reglas de "Valores Mínimos de Pedido por Proveedor". Proporciona la interfaz para listar, añadir, editar y eliminar estas reglas. Probablemente interactúa con una tabla de base de datos personalizada (por ejemplo, `ps_mobs_rules`) para almacenar el ID del proveedor y el valor mínimo asociado. La vista de cuadrícula y los campos del formulario se renderizan utilizando las clases `HelperList` y `HelperForm` de PrestaShop.
  - `controllers/admin/index.php`
    - **Nombre de la clase y clase padre**: Sin clase específica, típicamente un archivo PHP simple.
    - **Responsabilidad**: Este archivo suele ser un marcador de posición o una medida de seguridad para evitar la lista directa de directorios. A menudo contiene un simple `header('Location: ../../../index.php?controller=AdminHome');` o una redirección similar al panel de control del back office de PrestaShop, asegurando que el acceso directo a `tutienda.com/modules/mobs/controllers/admin/` no exponga información sensible ni cause errores. No presenta una pantalla orientada al usuario.

### 4.3 Clases Principales y Modelos (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo:

1.  Almacena su configuración directamente en `ps_configuration` para ajustes simples.
2.  Gestiona sus datos (mínimos de proveedor) directamente dentro de `AdminMobsController` utilizando métodos de consulta de base de datos estándar de PrestaShop, interactuando potencialmente con una tabla personalizada creada durante la instalación, sin un `ObjectModel` dedicado.

Si se utiliza una tabla personalizada, su estructura se definiría en el método `install()` del archivo principal del módulo (`mobs/index.php`).

### 4.4 Activos JavaScript (`views/js/`)

- `views/js/mobs.js`
  - **Alcance**: Front-office.
  - **Descripción**: Este archivo JavaScript es responsable de las interacciones del lado del cliente relacionadas con las comprobaciones de valor mínimo de pedido. Probablemente:
    - Vincula escuchadores de eventos a cambios de cantidad en el carrito, eliminaciones de productos o al botón "Proceder al pago".
    - Envía solicitudes AJAX a `controllers/front/ajax.php` para validar el carrito con respecto a los mínimos del proveedor.
    - Recibe respuestas JSON del controlador AJAX.
    - Actualiza dinámicamente la visualización del carrito de compras, mostrando mensajes de notificación si no se cumplen los mínimos.
    - Deshabilita o habilita el botón "Proceder al pago" según los resultados de la validación.
    - Puede incluir lógica para mostrar ventanas emergentes modales o mensajes de error en línea.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `views/css/mobs.css`
  - **Alcance**: Estilo del cliente en el front-office.
  - **Descripción**: Esta hoja de estilo proporciona la presentación visual para los elementos del front-office del módulo, principalmente los mensajes de notificación que se muestran en el carrito de compras.
  - **Principales componentes de la interfaz de usuario y contenedores que estiliza**: Probablemente apuntará a clases CSS específicas añadidas por el módulo a la plantilla del carrito de compras, como `div.mobs-notification`, `p.mobs-error-message`, o elementos similares que muestran las advertencias sobre valores mínimos de pedido no cumplidos.
  - **Selectores de clases CSS clave que los desarrolladores pueden anular**: Los desarrolladores pueden inspeccionar la salida HTML de las notificaciones del módulo para identificar los nombres de clase exactos (por ejemplo, `.mobs-alert`, `.mobs-supplier-name`, `.mobs-required-value`) y anularlos en el `custom.css` de su tema para que coincidan con la marca de la tienda.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:

  - No se enumeran plantillas de hook específicas en el inventario, lo que sugiere que la salida del front-office del módulo se inyecta principalmente en una plantilla existente como `displayShoppingCart.tpl` o mediante una renderización directa de la plantilla dentro de un controlador.
- **Plantillas de administración (`views/templates/admin/`)**:

  - El dossier del módulo no enumera plantillas de administración específicas. El `AdminMobsController` probablemente utiliza las plantillas predeterminadas `HelperList` y `HelperForm` de PrestaShop para sus vistas de cuadrícula y formulario, que forman parte del framework principal de PrestaShop.
- **Plantillas de front-office (`views/templates/front/`)**:

  - `views/templates/front/displayShoppingCart.tpl`
    - **Descripción**: Esta plantilla está diseñada específicamente para ser incluida o renderizada dentro de la página del carrito de compras. Contiene la estructura HTML para mostrar las notificaciones de valor mínimo de pedido al cliente. Probablemente iterará a través de cualquier mínimo de proveedor no cumplido y mostrará un mensaje para cada uno, posiblemente incluyendo el nombre del proveedor y el monto restante necesario. Esta plantilla se actualiza dinámicamente mediante el script `mobs.js` basándose en las respuestas AJAX.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El dossier del módulo no enumera explícitamente clases personalizadas o archivos SQL, pero para que el `AdminMobsController` gestione los "Valores Mínimos de Pedido por Proveedor", debe almacenar estos datos. Es muy probable que el módulo cree una tabla personalizada durante su método `install()` en `mobs/index.php`.
  - **Nombre de Tabla Probable**: `ps_mobs_rules` (o similar, por ejemplo, `ps_minimal_order_by_supplier`).
  - **Estructura de Tabla Probable**:
    - `id_mobs_rule` (CLAVE PRIMARIA, INT)
    - `id_supplier` (INT, CLAVE FORÁNEA a `ps_supplier.id_supplier`)
    - `min_value` (DECIMAL(20,6))
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - **Registros de Configuración**: El estado principal de habilitación/deshabilitación del módulo probablemente se almacena en `ps_configuration` con una clave como `MOBS_ENABLED`.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Para incluir archivos CSS (`mobs.css`) y JavaScript (`mobs.js`) para la funcionalidad del front-office. |
| `displayShoppingCartFooter` | En la parte inferior de la página del carrito de compras. | Para mostrar la plantilla `displayShoppingCart.tpl`, que contiene los mensajes de notificación para los valores mínimos de pedido no cumplidos. |
| `actionCartSave` | Después de guardar un carrito (por ejemplo, cambio de cantidad, añadir/eliminar producto). | Para activar la lógica que verifica los valores mínimos de pedido y potencialmente actualiza el estado del carrito o las variables de sesión. |
| `actionValidateOrder` | Antes de que un pedido sea validado oficialmente. | Para realizar una comprobación final de los valores mínimos de pedido y evitar la validación del pedido si no se cumplen los requisitos. |
| `displayBeforeCarrier` | Antes del paso de selección de transportista en el proceso de pago. | Para mostrar advertencias o bloquear el progreso si no se cumplen los mínimos en una etapa anterior del proceso de pago. |
| `displayPaymentTop` | En la parte superior de la página de selección de pago. | Para mostrar advertencias o bloquear el progreso si no se cumplen los mínimos antes del pago. |

*Nota: El dossier del módulo menciona "Header, Columns, Product, or Footer" como hooks de front-office. Si bien `displayHeader` es seguro, el módulo probablemente utiliza `displayShoppingCartFooter` o un hook similar específico del carrito para su salida principal, y `actionCartSave`/`actionValidateOrder` para su lógica central. `displayRightColumn` o `displayLeftColumn` podrían usarse para bloques estáticos opcionales, pero son menos probables para la funcionalidad principal.*

## 5. Soporte Oficial y Actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y acceder a las últimas versiones del módulo "Valor mínimo de pedido por proveedor", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y configuración del módulo.

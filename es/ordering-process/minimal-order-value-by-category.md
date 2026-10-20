---
title: "Valor mínimo de pedido por categoría - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Valor mínimo de pedido por categoría' de MyPresta.eu."
sidebar:
  label: "Valor mínimo de pedido por categoría - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Minimal order value by category en MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-category.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/minimal-order-value-by-category/)
>
> ---


# Valor mínimo de pedido por categoría

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y generalmente están disponibles por defecto en la mayoría de los entornos de alojamiento.

## 2. Recorrido Completo de Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla principal de configuración del módulo, a la que se accede inmediatamente después de la instalación o haciendo clic en "Configurar" desde el Gestor de Módulos.

- **Qué hace este ajuste:** Esta pantalla sirve principalmente como punto de entrada. Si bien la lógica central del módulo se gestiona a través de una pantalla de administración dedicada, esta página de configuración inicial asegura que el módulo esté correctamente instalado y proporciona un enlace o redirección a la interfaz de gestión principal.
- **Efecto de cambiar este ajuste:** Típicamente, esta pantalla no tiene interruptores directos o campos de entrada para el comerciante. Su propósito principal es confirmar el estado del módulo y guiarte al siguiente paso.
- **Valor recomendado:** No hay valores directos que establecer aquí. Solo asegúrate de que el módulo esté habilitado.
- **Escenario / ejemplo de comerciante:** Después de instalar, aterrizarás aquí. Podrías ver un mensaje confirmando la instalación y un botón o enlace para "Gestionar Valores Mínimos de Pedido" o similar, que te llevará a la pantalla `AdminMobcController` dedicada.

### 2.2 Pantalla de Administración Dedicada: Gestión de Valor Mínimo de Pedido por Categoría (Back Office > Módulos > Valor mínimo de pedido por categoría)

Esta es la interfaz de gestión central donde defines y controlas todos tus valores mínimos de pedido específicos por categoría. Normalmente encontrarás un nuevo elemento de menú bajo "Módulos" o "Catálogo" (dependiendo de tu versión de PrestaShop y del hook del módulo) llamado "Valor mínimo de pedido por categoría" o similar.

**Nombre de la Pantalla y Ubicación del Menú:**
Encontrarás esta pantalla navegando a **Módulos > Valor mínimo de pedido por categoría** en el menú de tu Back Office de PrestaShop.

**Acciones y Ajustes Disponibles:**
Esta pantalla presenta una lista (cuadrícula) de todas tus reglas de valor mínimo de pedido actualmente definidas. Para cada regla, típicamente verás:

- **Nombre de la Categoría:** El nombre de la categoría de PrestaShop a la que se aplica la regla.
- **Valor Mínimo:** El monto mínimo de pedido requerido para los productos dentro de esa categoría.
- **Moneda:** La moneda en la que se establece el valor mínimo (generalmente la moneda predeterminada de tu tienda, por ejemplo, USD, EUR).
- **Acciones:** Botones para "Editar" o "Eliminar" una regla existente.

También encontrarás un botón, generalmente en la parte superior derecha, para **"Añadir Nueva Regla"** o **"Añadir Nuevo Valor Mínimo de Pedido"**. Al hacer clic en esto, se abrirá un formulario donde puedes:

1. **Seleccionar Categoría:**

   - **Qué hace este ajuste:** Te permite elegir a qué categoría de PrestaShop existente se aplicará esta regla de valor mínimo de pedido.
   - **Efecto de cambiar este ajuste:** Seleccionar una categoría vincula la regla a todos los productos dentro de esa categoría (y sus subcategorías, dependiendo de la lógica del módulo).
   - **Valor recomendado:** Selecciona la categoría específica a la que deseas aplicar el valor mínimo de pedido.
   - **Escenario / ejemplo de comerciante:** Quieres establecer un mínimo para tu categoría "Venta al por mayor". Seleccionarías "Venta al por mayor" del menú desplegable.
2. **Valor Mínimo de Pedido:**

   - **Qué hace este ajuste:** Define la cantidad monetaria que los clientes deben gastar en productos *dentro de la categoría seleccionada* antes de que puedan proceder con su pedido.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se establece un valor (por ejemplo, 50.00):* Los clientes deben tener al menos 50.00 unidades de tu moneda predeterminada en productos de la categoría seleccionada en su carrito. Si no, serán bloqueados en el pago con un mensaje.
     - *Cuando se deja vacío o se establece en 0:* Esta regla se deshabilitaría efectivamente para la categoría, permitiendo cualquier valor. Sin embargo, es mejor eliminar la regla si no la necesitas.
   - **Valor recomendado:** Un valor numérico positivo que refleje tu mínimo deseado (por ejemplo, `25.00`, `100.00`).
   - **Escenario / ejemplo de comerciante:** Para tu categoría "Venta al por mayor", lo estableces en `100.00`. Un cliente con 90 € en productos al por mayor no puede pagar hasta que añada otros 10 €.
3. **Botón Guardar:**

   - **Qué hace:** Aplica los cambios o crea la nueva regla.
   - **Efecto:** La nueva regla estará activa inmediatamente, y el sistema comenzará a aplicar el valor mínimo de pedido para la categoría seleccionada.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1. **Revisa las reglas existentes:** Verifica periódicamente tu lista de reglas para asegurarte de que sigan siendo relevantes para tu estrategia comercial.
2. **Añade nuevas reglas:** Si introduces nuevas categorías de productos que requieren mínimos específicos (por ejemplo, una nueva línea B2B), añade una regla para ellas.
3. **Edita las reglas existentes:** Ajusta los valores mínimos en función de los cambios de precios de los productos, las condiciones del mercado o las estrategias promocionales.
4. **Elimina las reglas obsoletas:** Elimina las reglas para categorías que ya no requieren un mínimo o que han sido descontinuadas.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | (Sin ajustes directos) | N/A | Punto de entrada al módulo; confirma la instalación y dirige a la pantalla de gestión. |
| Gestión de Valor Mínimo de Pedido por Categoría | Añadir Nueva Regla / Editar Regla > Seleccionar Categoría | N/A | Vincula un valor mínimo de pedido a una categoría de producto específica de PrestaShop. |
| Gestión de Valor Mínimo de Pedido por Categoría | Añadir Nueva Regla / Editar Regla > Valor Mínimo de Pedido | Tu mínimo deseado (por ejemplo, `50.00`) | Establece la cantidad monetaria requerida para los productos dentro de la categoría elegida. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: He establecido un valor mínimo, pero no funciona. Los clientes aún pueden pagar con menos.**
R:

- **Verifica el Estado del Módulo:** Asegúrate de que el módulo esté habilitado en **Módulos > Gestor de Módulos**.
- **Verifica la Configuración de la Regla:** Ve a **Módulos > Valor mínimo de pedido por categoría** y confirma que la regla para la categoría específica esté activa, tenga un valor mayor que cero y esté correctamente asignada a la categoría deseada.
- **Borra la Caché:** A veces, la caché de PrestaShop puede impedir que los cambios aparezcan inmediatamente. Ve a **Parámetros Avanzados > Rendimiento** y haz clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
- **Asignación de Categoría de Producto:** Vuelve a verificar que los productos en cuestión estén realmente asignados a la categoría para la que estableciste el mínimo.

**P2: El mensaje que se muestra a los clientes no es claro o no coincide con el idioma de mi tienda.**
R:

- **Traducciones del Módulo:** El módulo debería ser compatible con el sistema de traducción de PrestaShop. Ve a **Internacional > Traducciones**, selecciona "Traducciones de módulos instalados", elige tu tema y luego selecciona "Valor mínimo de pedido por categoría". Luego puedes personalizar los mensajes de advertencia para que sean más específicos o traducirlos a otros idiomas.
- **Estilo de Tema Personalizado:** Si el mensaje aparece pero se ve fuera de lugar, el CSS de tu tema podría estar anulando los estilos del módulo. Un webmaster puede ayudarte a ajustar el archivo `mobc.css` o añadir CSS personalizado a tu tema para asegurar una visualización adecuada.

**P3: ¿Puedo establecer mínimos diferentes para diferentes grupos de clientes (por ejemplo, minoristas vs. mayoristas)?**
R: La versión actual del módulo "Valor mínimo de pedido por categoría" se centra en mínimos a nivel de categoría, no en mínimos específicos de grupos de clientes. Si necesitas esta funcionalidad avanzada, es posible que debas usar categorías separadas para diferentes grupos de clientes (por ejemplo, "Productos al por mayor" vs. "Productos al por menor") y aplicar reglas a esas categorías distintas.

**P4: ¿Qué sucede si un producto está en varias categorías, y solo una tiene un mínimo?**
R: El módulo calcula el valor total de los productos dentro de *cada* categoría que tiene una regla de mínimo. Si un producto está en la Categoría A (sin mínimo) y la Categoría B (mínimo 50 €), su valor contribuirá al total de la Categoría B si se añade al carrito. El cliente debe cumplir el mínimo para la Categoría B basándose en la suma de todos los productos en su carrito que pertenecen a la Categoría B.

**P5: Eliminé una categoría, pero la regla para ella sigue apareciendo en la configuración del módulo.**
R: Si eliminas una categoría directamente desde el menú Catálogo de PrestaShop, la regla del módulo asociada a esa categoría podría quedar huérfana. Debes ir manualmente a **Módulos > Valor mínimo de pedido por categoría** y eliminar la regla correspondiente de la lista para mantener tu configuración limpia.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Visión General de la Arquitectura

El módulo "Valor mínimo de pedido por categoría" (`mobc`) sigue un patrón MVC estándar de PrestaShop. Principalmente extiende `Module` para su funcionalidad central y `AdminController` para su interfaz de gestión en el back-office. Las interacciones del front-office se manejan a través de `ModuleFrontController` para solicitudes AJAX y renderizado de plantillas. El módulo no utiliza clases `ObjectModel` personalizadas, sino que se basa en las entidades `Category` y `Product` del núcleo de PrestaShop para la recuperación de datos. La configuración se almacena en `ps_configuration` y en una tabla de base de datos personalizada para las asignaciones de categoría-valor.

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**:

  - `controllers/front/ajax.php`
    - **Nombre de la Clase:** `MobcAjaxModuleFrontController` (extiende `ModuleFrontController`)
    - **Responsabilidad:** Maneja las solicitudes AJAX desde el front-office, principalmente para verificar el contenido del carrito contra los valores mínimos de pedido definidos por categoría. Probablemente recibe datos del carrito y devuelve una respuesta JSON indicando si se cumplen los mínimos y, si no, qué categorías son deficientes y por cuánto. Esto es crucial para la validación en tiempo real en la página del carrito sin recargas completas de la página.
  - `controllers/front/index.php`
    - **Nombre de la Clase:** `MobcIndexModuleFrontController` (extiende `ModuleFrontController`)
    - **Responsabilidad:** Este controlador podría servir como un respaldo o un punto de entrada simple, pero dada la funcionalidad del módulo, su papel principal es probablemente mínimo, posiblemente redirigiendo o sirviendo una página básica si se accede directamente. La lógica central del front-office se espera en `ajax.php`.
- **Controladores de Administración del Back-Office**:

  - `controllers/admin/AdminMobc.php`
    - **Nombre de la Clase:** `AdminMobcController` (extiende `ModuleAdminController`)
    - **Nombre de la Pestaña:** Valor mínimo de pedido por categoría (o similar, típicamente bajo "Módulos" o "Catálogo").
    - **Entidad Gestionada:** Gestiona la entidad `mobc` personalizada, que representa las asignaciones de categoría-valor mínimo.
    - **Responsabilidad:** Proporciona la interfaz CRUD (Crear, Leer, Actualizar, Eliminar) para gestionar las reglas de valor mínimo de pedido. Se encarga de listar las reglas existentes en una cuadrícula, mostrar formularios para añadir/editar reglas (seleccionar categorías, introducir valores mínimos) y procesar los envíos de formularios. Interactúa con la tabla de la base de datos del módulo para las entradas `mobc`.
  - `controllers/admin/index.php`
    - **Nombre de la Clase:** `AdminMobcIndexController` (extiende `ModuleAdminController`)
    - **Responsabilidad:** Similar al `index.php` del front-office, este podría ser un marcador de posición o un simple redireccionador. La lógica principal de administración reside en `AdminMobc.php`.

### 4.3 Clases Principales y Modelos (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto sugiere que el manejo de datos del módulo para las asignaciones de categoría-valor se realiza directamente dentro de `AdminMobcController` o `index.php` (archivo principal del módulo) utilizando `Db::getInstance()` o extendiendo un `ObjectModel` genérico dentro del propio archivo principal del módulo sin crear un archivo de clase dedicado.

Dado que `AdminMobcController` gestiona una entidad "mobc", es muy probable que `AdminMobcController` defina sus `$this->object` y `$this->fields_list` directamente, o que haya una definición implícita de `ObjectModel` dentro del archivo `mobc.php` principal que el controlador aprovecha.

### 4.4 Activos JavaScript (`views/js/`)

- `mobc/views/js/mobc.js`
  - **Alcance:** Front-office.
  - **Responsabilidad:** Este script es crucial para la validación en tiempo real del carrito. Probablemente:
    - Vincula oyentes de eventos a cambios de cantidad del carrito, eliminaciones de productos o cargas de página en la página del carrito de compras.
    - Activa llamadas AJAX a `controllers/front/ajax.php` para enviar los datos actuales del carrito.
    - Recibe la respuesta JSON del controlador AJAX.
    - Actualiza dinámicamente el DOM en la página del carrito para mostrar mensajes de advertencia si no se cumplen los mínimos.
    - Deshabilita/habilita el botón de pago basándose en el resultado de la validación.
    - Puede incluir lógica para mostrar mensajes emergentes o resaltar categorías problemáticas.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `mobc/views/css/mobc.css`
  - **Alcance:** Estilo del cliente del front-office.
  - **Componentes y contenedores principales de la interfaz de usuario que estiliza:** Esta hoja de estilos es responsable de la presentación visual de los mensajes de advertencia que se muestran en la página del carrito de compras. Definirá estilos para:
    - Contenedores que contienen los mensajes de advertencia (por ejemplo, `div.mobc-warning-message`).
    - Elementos de texto dentro de las advertencias (por ejemplo, `span.mobc-category-name`, `span.mobc-remaining-amount`).
    - Potencialmente, estilos para el botón de pago deshabilitado u otras señales visuales.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular en su tema:** Los desarrolladores pueden inspeccionar el HTML generado en la página del carrito para identificar los nombres de clase específicos (por ejemplo, `.mobc-alert`, `.mobc-error-list`, `.mobc-checkout-blocked`) y anularlos en el `custom.css` o `theme.css` de su tema para que coincidan con la marca de la tienda.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - `mobc/views/templates/front/displayShoppingCart.tpl`
    - **Hook:** Esta plantilla probablemente se renderiza en un hook en la página del carrito de compras, como `displayShoppingCartFooter` o `displayShoppingCartExtraContent`.
    - **Salida del Bloque Visual:** Genera la estructura HTML para los mensajes de advertencia que informan a los clientes sobre los valores mínimos de pedido no cumplidos para las categorías. Esta plantilla contendrá marcadores de posición para los nombres de las categorías, las cantidades requeridas y la cantidad restante necesaria, que son rellenados por el JavaScript y el controlador AJAX.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - `ps_mobc_category_value` (o similar, basado en la entidad de `AdminMobcController`): Esta tabla personalizada almacena la asignación entre los ID de categoría y sus respectivos valores mínimos de pedido.
    - `id_mobc_category_value` (Clave Primaria, INT)
    - `id_category` (INT, Clave Foránea a `ps_category.id_category`)
    - `min_value` (DECIMAL, almacena el monto monetario mínimo)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_configuration`: Tabla de configuración estándar de PrestaShop. El módulo podría almacenar sus configuraciones generales (si las hay, aunque no se detectaron explícitamente) aquí, prefijadas con `MOBC_`.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Para incluir `mobc.css` y `mobc.js` para la funcionalidad del front-office. |
| `displayShoppingCart` | En la página del carrito de compras, típicamente antes o después del resumen del carrito. | Para renderizar `displayShoppingCart.tpl` para mostrar mensajes de advertencia. |
| `actionCartSave` | Después de guardar un carrito (por ejemplo, producto añadido/eliminado, cantidad cambiada). | Para activar la lógica del módulo para reevaluar los mínimos de categoría y potencialmente actualizar el estado del carrito o las variables de sesión. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su salida, permitiendo a los módulos añadir JS/CSS. | Para registrar archivos JavaScript y CSS específicos del módulo para el front-office. |
| `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice su salida. | Para registrar archivos JavaScript y CSS específicos del módulo para el back-office (por ejemplo, para `AdminMobcController`). |
| `displayAdminProductsExtra` (o similar) | En la página de edición de productos en el back-office. | Potencialmente para mostrar información sobre los mínimos de categoría relacionados con el producto actual, aunque no confirmado explícitamente por el dossier. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial del módulo "Valor mínimo de pedido por categoría", consulta tu cuenta de cliente en MyPresta.eu. Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta relacionada con la funcionalidad y configuración del módulo.

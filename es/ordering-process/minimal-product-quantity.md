---
title: "Cantidad mínima de producto - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Cantidad mínima de producto' de MyPresta.eu."
sidebar:
  label: "Cantidad mínima de producto - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Minimal product quantity en MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-product-quantity.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/minimal-product-quantity/)
>
> ---


# Cantidad mínima de producto

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página de configuración principal del módulo "Cantidad mínima de producto". Aquí es donde se definen las reglas principales para las cantidades mínimas.

La página de configuración está diseñada para ser intuitiva, permitiéndole establecer cantidades mínimas para productos individuales y grupos de clientes específicos.

**Cómo establecer una cantidad mínima para un producto:**

1. **Buscar un producto:**

   - Verá una barra de búsqueda o una lista de productos. Empiece a escribir el nombre del producto que desea configurar. A medida que escribe, el módulo sugerirá productos coincidentes.
   - *Qué hace este ajuste:* Le permite localizar rápidamente el producto específico al que desea aplicar una regla de cantidad mínima.
   - *Efecto de cambiar este ajuste:* N/A (función de búsqueda).
   - *Valor recomendado:* Escriba el nombre exacto del producto para mayor precisión.
   - *Escenario de comerciante:* Desea establecer un mínimo para "Granos de café orgánico (1kg)". Escriba "Café orgánico".
2. **Seleccionar el producto:**

   - Haga clic en el producto deseado de los resultados de búsqueda. Esto lo añadirá a una lista de productos configurados a continuación.
   - *Qué hace este ajuste:* Confirma a qué producto está aplicando la regla.
   - *Efecto de cambiar este ajuste:* El producto aparece en la lista de configuración, listo para los ajustes de cantidad y grupo.
   - *Valor recomendado:* Seleccione el producto correcto.
   - *Escenario de comerciante:* Después de escribir "Café orgánico", hace clic en "Granos de café orgánico (1kg)".
3. **Establecer cantidad mínima:**

   - Junto al producto seleccionado, habrá un campo de entrada (por ejemplo, "Cantidad mínima"). Introduzca el número más bajo de unidades que un cliente debe comprar para este producto específico.
   - *Qué hace este ajuste:* Define el número mínimo absoluto de unidades para este producto.
   - *Efecto de cambiar este ajuste:*
     - *Cuando se establece en 5:* Los clientes deben añadir al menos 5 unidades de este producto a su carrito. Si intentan añadir 1, 2, 3 o 4, recibirán un mensaje de error.
     - *Cuando se establece en 1 (o comportamiento predeterminado de PrestaShop):* No se aplica una cantidad mínima especial más allá de la predeterminada de PrestaShop.
   - *Valor recomendado:* Un número mayor que 1, que refleje sus necesidades comerciales (por ejemplo, 6, 12, 24).
   - *Escenario de comerciante:* Vende granos de café al por mayor. Establece la "Cantidad mínima" en 5.
4. **Seleccionar grupo de clientes (Opcional):**

   - Probablemente verá un menú desplegable o una lista de grupos de clientes (por ejemplo, "Invitado", "Cliente", "Mayorista"). Puede seleccionar uno o más grupos a los que se aplica esta cantidad mínima.
   - *Qué hace este ajuste:* Le permite aplicar diferentes reglas de cantidad mínima según el grupo de clientes. Si no se selecciona ningún grupo, la regla se aplica a todos los clientes.
   - *Efecto de cambiar este ajuste:*
     - *Cuando se selecciona "Mayorista":* Solo los clientes que pertenecen al grupo "Mayorista" estarán sujetos a esta cantidad mínima. Otros grupos pueden tener un mínimo diferente (o ningún mínimo).
     - *Cuando no se selecciona ningún grupo específico (o se implica "Todos los clientes"):* La cantidad mínima se aplica a todos los clientes, independientemente de su grupo.
   - *Valor recomendado:* Seleccione grupos específicos si tiene diferentes estrategias de precios o ventas para ellos. De lo contrario, déjelo para "Todos los clientes".
   - *Escenario de comerciante:* Desea que los mayoristas compren al menos 10 unidades, pero los clientes habituales solo necesitan comprar 5. Crearía dos reglas separadas para el mismo producto, una para el grupo "Mayorista" con cantidad 10, y otra para el grupo "Cliente" con cantidad 5.
5. **Guardar cambios:**

   - Después de configurar los productos y sus cantidades/grupos mínimos, recuerde hacer clic en el botón "Guardar" o "Actualizar" para aplicar sus ajustes.
   - *Qué hace este ajuste:* Persiste sus cambios de configuración en la base de datos.
   - *Efecto de cambiar este ajuste:* Las nuevas reglas de cantidad mínima se activan en su front office inmediatamente.
   - *Valor recomendado:* Guarde siempre después de realizar cambios.
   - *Escenario de comerciante:* Ha configurado todos sus mínimos; ahora hace clic en "Guardar" para activarlos.

**Configuración general del módulo (si está presente):**

Aunque la función principal son los mínimos por producto, algunos módulos pueden incluir configuraciones generales:

- **Habilitar/Deshabilitar módulo:**

  - *Qué hace este ajuste:* Activa o desactiva la funcionalidad de todo el módulo.
  - *Efecto de cambiar este ajuste:*
    - *Cuando está habilitado:* Se aplican las reglas de cantidad mínima.
    - *Cuando está deshabilitado:* Todas las reglas de cantidad mínima se ignoran y los clientes pueden añadir cualquier cantidad.
  - *Valor recomendado:* SÍ (habilitado) una vez configurado.
  - *Escenario de comerciante:* Está probando el módulo y desea deshabilitarlo temporalmente sin perder su configuración.
- **Tipo de mensaje de error a mostrar (por ejemplo, Ventana emergente, En línea):**

  - *Qué hace este ajuste:* Controla cómo se notifica al cliente cuando intenta añadir menos de la cantidad mínima.
  - *Efecto de cambiar este ajuste:*
    - *Cuando se establece en Ventana emergente:* Aparece una ventana modal, interrumpiendo el flujo del usuario, indicando claramente el problema.
    - *Cuando se establece en En línea:* Aparece un mensaje directamente en la página del producto o en el carrito, sin una ventana emergente.
  - *Valor recomendado:* La ventana emergente suele ser más efectiva para errores críticos como las cantidades mínimas, ya que exige atención.
  - *Escenario de comerciante:* Desea asegurarse de que los clientes no pasen por alto el requisito de cantidad mínima, por lo que elige una ventana emergente.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Búsqueda de productos | N/A | Localiza productos para aplicar reglas de cantidad mínima. |
| Página de configuración del módulo | Cantidad mínima (por producto) | Varía (por ejemplo, 5, 10) | Establece el número más bajo de unidades que un cliente debe comprar para ese producto. |
| Página de configuración del módulo | Grupo de clientes (por producto) | Todos los clientes | Aplica la regla de cantidad mínima a grupos de clientes específicos o a todos los clientes. |
| Página de configuración del módulo | Botón Guardar | N/A | Aplica todas las reglas de cantidad mínima configuradas a la tienda. |
| Página de configuración del módulo | Habilitar/Deshabilitar módulo | Habilitado | Activa o desactiva la funcionalidad del módulo globalmente. |
| Página de configuración del módulo | Tipo de mensaje de error | Ventana emergente | Define cómo se muestran los errores de cantidad mínima a los clientes. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He establecido una cantidad mínima, pero no funciona en mi tienda. ¿Qué pasa?**
R:

1.  **¿Está habilitado el módulo?** Vuelva a comprobar la página de configuración principal para asegurarse de que el módulo "Cantidad mínima de producto" está activo.
2.  **¿Ha guardado sus cambios?** Haga siempre clic en el botón "Guardar" o "Actualizar" después de realizar cualquier cambio de configuración.
3.  **Borre la caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, PrestaShop almacena en caché configuraciones antiguas.
4.  **Compruebe si hay conflictos de tema:** Si tiene un tema muy personalizado, podría interferir con la forma en que el módulo muestra los mensajes o interactúa con el botón "Añadir al carrito". Cambie temporalmente al tema predeterminado de PrestaShop (Classic o Hummingbird) para ver si el problema persiste. Si se resuelve, su tema necesita ajustes.
5.  **Grupo de clientes:** Asegúrese de que el cliente con el que está probando pertenece al grupo para el que se establece la cantidad mínima. Si no se especifica ningún grupo, debería aplicarse a todos.

**P2: La notificación emergente se ve extraña o no coincide con el diseño de mi tienda.**
R: El módulo utiliza su propio CSS para la ventana emergente. Si su tema tiene reglas de estilo muy específicas, podrían anular o entrar en conflicto.

1.  **Compruebe la configuración del módulo:** Vea si el módulo ofrece opciones para personalizar la apariencia de la ventana emergente o elegir un método de visualización diferente (por ejemplo, mensaje en línea en lugar de ventana emergente).
2.  **CSS personalizado:** Para desarrolladores o webmasters, se puede añadir CSS personalizado al archivo `custom.css` de su tema para anular los estilos predeterminados del módulo. (Consulte la Sección 7.5 para obtener detalles del archivo CSS).

**P3: ¿Puedo establecer una cantidad mínima para combinaciones de productos (atributos)?**
R: El módulo normalmente aplica cantidades mínimas a nivel de producto. Si necesita mínimos específicos para combinaciones (por ejemplo, "Camiseta roja, Talla S" frente a "Camiseta azul, Talla L"), es posible que deba verificar si el módulo admite explícitamente esto en su configuración. Si no es así, establecería el mínimo para el producto principal, que se aplica a cualquier combinación de ese producto.

**P4: ¿Cómo traduzco los mensajes del módulo a otros idiomas?**
R:

1.  Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop.
2.  Seleccione "Traducciones de módulos instalados".
3.  Elija su tema, el idioma que desea traducir y luego seleccione "Cantidad mínima de producto" de la lista de módulos.
4.  Encontrará todas las cadenas traducibles utilizadas por el módulo (por ejemplo, "Debe añadir al menos X unidades de este producto"). Tradúzcalas y guarde.

**P5: ¿Qué sucede si un cliente tiene un producto en su carrito al que posteriormente se le aplica una cantidad mínima?**
R: Cuando el cliente visite su carrito o intente pagar la próxima vez, el módulo detectará la discrepancia. Se le mostrará el mensaje de error y se le impedirá continuar hasta que ajuste la cantidad para cumplir con el nuevo mínimo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Cantidad mínima de producto" (`minqc`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente los hooks para inyectar su lógica y activos de front-end. Opera interceptando los cambios de cantidad y las adiciones al carrito, validando contra los mínimos configurados y mostrando comentarios al usuario. La lógica central del módulo reside en su archivo `index.php` principal, que gestiona la instalación, desinstalación, configuración y registro de hooks. La interacción del front-end se gestiona a través de un conjunto de archivos JavaScript adaptados para diferentes versiones y contextos de PrestaShop (página de producto, carrito, vista rápida).

### 4.2 Controladores (`controllers/`)

Este módulo no parece utilizar controladores de administración de Front-Office o Back-Office personalizados. Su configuración se gestiona directamente dentro del método `getContent()` de la clase principal del módulo, y las interacciones del front-office se gestionan a través de JavaScript y llamadas AJAX a funcionalidades principales de PrestaShop o al propio `ajax.php` del módulo (si está presente, aunque no se enumera explícitamente como un controlador dedicado, es un patrón común para que los módulos gestionen las solicitudes AJAX a través de su archivo principal o un script simple).

### 4.3 Clases y modelos principales (`classes/`)

Según el inventario proporcionado, este módulo no define clases `ObjectModel` personalizadas ni otras clases PHP complejas en un directorio `classes/` dedicado. Es probable que su lógica esté encapsulada dentro del archivo `minqc/index.php` principal, interactuando directamente con `Configuration` para la configuración y potencialmente `Db` para el almacenamiento de datos personalizados si los mínimos específicos del producto se almacenan fuera de `ps_configuration`.

### 4.4 Activos JavaScript (`views/js/`)

El módulo utiliza ampliamente JavaScript para proporcionar una experiencia de usuario dinámica y aplicar reglas de cantidad en tiempo real.

- `minqc/views/js/minqc.js`:

  - **Alcance:** Probablemente un archivo JS central, potencialmente cargado globalmente o en varias páginas.
  - **Responsabilidad:** Contiene funciones de utilidad generales, enlace de eventos para elementos comunes y, potencialmente, la lógica principal para verificar las cantidades mínimas antes de añadir al carrito o actualizar el carrito. Podría gestionar la visualización de la notificación emergente.
  - **Interacciones:** Se enlaza a eventos `click` en los botones "Añadir al carrito", eventos `change` en los campos de entrada de cantidad y, potencialmente, eventos `prestashop.on` para actualizaciones del carrito AJAX.
- `minqc/views/js/minqc-17500.js`:

  - **Alcance:** Front-office, específicamente para PrestaShop 1.7.5.0 y versiones más recientes (o rangos de versiones similares).
  - **Responsabilidad:** Contiene lógica JavaScript específica de la versión para adaptarse a los cambios en la estructura del front-office de PrestaShop, el comportamiento del carrito AJAX o los elementos de la página del producto introducidos en estas versiones.
  - **Interacciones:** Anula o extiende `minqc.js` para estructuras DOM y manejo de eventos específicos de PrestaShop 1.7+.
- `minqc/views/js/minqc-admin-product.js`:

  - **Alcance:** Back-office, específicamente en la página de edición de productos (`AdminProducts`).
  - **Responsabilidad:** Si el módulo permite establecer cantidades mínimas directamente en la página de edición de productos, este script gestionaría la interfaz de usuario para ello (por ejemplo, añadir campos de entrada, guardar valores a través de AJAX).
  - **Interacciones:** Se enlaza a eventos en elementos del formulario de producto, realiza llamadas AJAX para guardar mínimos específicos del producto.
- `minqc/views/js/minqc-cart.js`:

  - **Alcance:** Front-office, específicamente en la página del carrito de la compra.
  - **Responsabilidad:** Supervisa los cambios de cantidad dentro del carrito, valida contra los mínimos e impide el pago si se infringen las reglas. Muestra mensajes de error o ventanas emergentes en la página del carrito.
  - **Interacciones:** Se enlaza a cambios en la entrada de cantidad, clics en el botón "Proceder al pago" y, potencialmente, eventos `prestashop.on` relacionados con las actualizaciones del carrito.
- `minqc/views/js/minqc-front.js`:

  - **Alcance:** Uso general del front-office.
  - **Responsabilidad:** Podría ser un script de front-end más genérico, que potencialmente gestione la visualización de información de cantidad mínima en listados de productos u otras páginas no específicas de productos/carrito.
  - **Interacciones:** Manipulación del DOM para mostrar mensajes, potencialmente llamadas AJAX para validación.
- `minqc/views/js/minqc-no-autoadd.js`:

  - **Alcance:** Front-office.
  - **Responsabilidad:** Sugiere un comportamiento específico relacionado con la prevención de la adición automática de productos al carrito si no se cumplen los mínimos, o la gestión de escenarios en los que un producto podría añadirse automáticamente pero luego falla la validación.
  - **Interacciones:** Modifica el comportamiento predeterminado de "Añadir al carrito" para garantizar que la validación se produzca *antes* de que se añada el artículo.
- `minqc/views/js/minqc-product-classic.js`:

  - **Alcance:** Front-office, específicamente para temas basados en el tema Classic de PrestaShop (PrestaShop 1.7+).
  - **Responsabilidad:** Adapta la aplicación y visualización de la cantidad mínima a la estructura DOM y los eventos JavaScript específicos de la página de producto del tema Classic.
  - **Interacciones:** Se enlaza al botón "Añadir al carrito" y a los elementos de entrada de cantidad en la página de producto del tema Classic.
- `minqc/views/js/minqc-product-hummingbird.js`:

  - **Alcance:** Front-office, específicamente para temas basados en el tema Hummingbird de PrestaShop (PrestaShop 8+).
  - **Responsabilidad:** Adapta la aplicación y visualización de la cantidad mínima a la estructura DOM y los eventos JavaScript específicos de la página de producto del tema Hummingbird.
  - **Interacciones:** Se enlaza al botón "Añadir al carrito" y a los elementos de entrada de cantidad en la página de producto del tema Hummingbird.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `minqc/views/css/minqc.css`:
  - **Alcance:** Front-office y potencialmente Back-office para elementos de interfaz de usuario específicos del módulo.
  - **Componentes principales de la interfaz de usuario:** Estilos para la notificación emergente (fondo modal, cuadro de contenido, botón de cierre, texto del mensaje), mensajes de error en línea y, potencialmente, indicadores visuales en las páginas de productos.
  - **Selectores de clase CSS clave:** Los desarrolladores pueden inspeccionar el HTML de salida del módulo para identificar clases específicas (por ejemplo, `.minqc-popup`, `.minqc-error-message`, `.minqc-quantity-input-error`) y anularlas en el archivo `custom.css` o `theme.css` de su tema para que coincidan con la marca de su tienda.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**: No se enumeran explícitamente, pero es común que los módulos usen `displayHeader` para JS/CSS, o `displayProductActions` para mensajes de la página del producto.
- **Plantillas de administración (`views/templates/admin/`)**:

  - `minqc/views/templates/admin/admin.tpl`: Probablemente la plantilla de configuración principal del módulo, renderizada por el método `getContent()`. Contendría la búsqueda de productos, la lista de productos configurados y la configuración general.
  - `minqc/views/templates/admin/admintab.tpl`: Podría ser una subplantilla para una pestaña o sección específica dentro de la configuración de administración, o una plantilla heredada.
  - `minqc/views/templates/admin/_configure/helpers/list/list_content.tpl`: Esto sugiere que el módulo utiliza `HelperList` de PrestaShop para mostrar la lista de productos con cantidades mínimas configuradas en el back office. Esta plantilla definiría cómo se renderiza cada fila de esa lista.
- **Plantillas Ajax (`views/templates/ajax/`)**:

  - `minqc/views/templates/ajax/minqcErrors.tpl`: Esta plantilla se utiliza probablemente para renderizar el contenido HTML de la ventana emergente de error o los mensajes en línea que se muestran al cliente cuando no se cumple una cantidad mínima. Se cargaría a través de AJAX.
- **Plantillas de Front-office (`views/templates/front/`)**:

  - `minqc/views/templates/front/beforeShoppingCart.tpl`: Esta plantilla probablemente se engancha en una posición antes del contenido principal del carrito de la compra, potencialmente para mostrar una advertencia o resumen relacionado con las cantidades mínimas si el carrito no es válido.
  - `minqc/views/templates/front/product-details.tpl`: Esta plantilla se utilizaría para inyectar información o advertencias de cantidad mínima directamente en la página de detalles del producto, a menudo cerca del selector de cantidad o del botón "Añadir al carrito".
  - `minqc/views/templates/front/productActions.tpl`: Similar a `product-details.tpl`, esta plantilla se engancharía en el hook `displayProductActions` (o similar) para mostrar mensajes o modificar el comportamiento del botón "Añadir al carrito" en función de las reglas de cantidad mínima.
  - `minqc/views/templates/front/qv.tpl`: Esta plantilla es específicamente para la funcionalidad de "Vista rápida", inyectando información o advertencias de cantidad mínima en el modal de vista rápida.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:

  - Es probable que el módulo almacene su configuración para las cantidades mínimas específicas del producto y las asociaciones de grupos de clientes en la tabla `ps_configuration` para configuraciones globales simples.
  - Para los mínimos específicos del producto y del grupo, es muy probable que el módulo cree su propia tabla de base de datos personalizada (por ejemplo, `ps_minqc_product_quantity`) para almacenar los valores `id_product`, `id_customer_group` y `min_quantity`. Esta tabla se crearía durante el método `install()` y se eliminaría durante `uninstall()`.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Inyecta los archivos CSS (`minqc.css`) y JavaScript (`minqc.js`, `minqc-front.js`, JS específicos de la versión como `minqc-17500.js`, `minqc-product-classic.js`, `minqc-product-hummingbird.js`, `minqc-cart.js`, `minqc-no-autoadd.js`) del módulo para la funcionalidad del front-end. |
| `displayProductActions` | En la página del producto, normalmente cerca del botón "Añadir al carrito". | Inyecta `productActions.tpl` para mostrar los requisitos o advertencias de cantidad mínima directamente en la página del producto. |
| `displayProductExtraContent` (o similar) | En la página del producto, para bloques de contenido adicionales. | Podría usarse para mostrar `product-details.tpl` u otra información. |
| `displayShoppingCartFooter` (o similar) | En la parte inferior del resumen del carrito de la compra. | Inyecta `beforeShoppingCart.tpl` o similar para mostrar advertencias si los artículos del carrito no cumplen los mínimos, impidiendo el pago. |
| `actionCartSave` | Después de guardar o actualizar un carrito. | Activa la lógica PHP del módulo para volver a validar todas las cantidades en el carrito contra los mínimos configurados. |
| `actionValidateOrder` | Antes de que se valide oficialmente un pedido. | Verificación final para garantizar que todas las cantidades de productos en el carrito cumplen sus mínimos antes de realizar el pedido. |
| `actionProductUpdate` / `actionProductAdd` | Cuando se actualiza o añade un producto en el Back Office. | Potencialmente utilizado para actualizar o borrar datos de cantidad mínima en caché para ese producto. |
| `displayAdminProductsExtra` | En la página de edición de productos en el Back Office. | Inyecta elementos de la interfaz de usuario (por ejemplo, a través de `admintab.tpl` o `admin.tpl`) para permitir establecer cantidades mínimas específicas del producto directamente desde el formulario del producto, utilizando `minqc-admin-product.js`. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con el módulo "Cantidad mínima de producto".

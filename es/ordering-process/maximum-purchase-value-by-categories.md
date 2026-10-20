---
title: "Valor máximo de compra por categorías - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Valor máximo de compra por categorías' de MyPresta.eu."
sidebar:
  label: "Valor máximo de compra por categorías - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Maximum purchase value by categories en MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-categories.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/maximum-purchase-value-by-categories/)
>
> ---


# Valor máximo de compra por categorías

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No hay requisitos de alojamiento especiales más allá de una configuración estándar de PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo, donde gestionas los ajustes generales y accedes a las reglas para los valores máximos de compra.

- **Qué hace este ajuste:** Esta página proporciona información general sobre el módulo y a menudo incluye un enlace o botón para gestionar las reglas reales.
- **Efecto de cambiar este ajuste:** Aunque esta pantalla específica podría no tener "ajustes" directos para cambiar, sirve como punto de entrada a la funcionalidad del módulo.
- **Valor recomendado:** N/A (Esta es una pantalla informativa).
- **Escenario / ejemplo de comerciante:** Después de la instalación, aterrizarás aquí. Luego harás clic en un botón o enlace (por ejemplo, "Gestionar Reglas" o "Configurar Valores Máximos") para proceder a la pantalla dedicada donde defines los límites de tus categorías.

### 2.2 Pantalla de Administración Dedicada: Reglas de Valor Máximo de Compra (Back Office > Módulos > Valor máximo de compra por categorías > Configurar)

Este es el núcleo del módulo donde defines y gestionas tus reglas de valor máximo de compra para diferentes categorías. Normalmente encontrarás esta pantalla haciendo clic en "Configurar" después de instalar el módulo, o navegando a **Módulos > Gestor de Módulos**, buscando el módulo y haciendo clic en "Configurar".

**Nombre de la Pantalla y Ubicación del Menú:**
Accederás a esta pantalla navegando a **Módulos > Gestor de Módulos**, buscando "Valor máximo de compra por categorías" y haciendo clic en el botón "Configurar". Esto te llevará a una interfaz de administración dedicada para gestionar tus reglas.

**Acciones y Ajustes Disponibles:**
En esta pantalla, verás una lista (cuadrícula) de todas tus reglas de valor máximo de compra actualmente definidas. Para cada regla, normalmente verás:

- **Nombre de la Categoría:** El nombre de la categoría de producto a la que se aplica la regla.
- **Valor Máximo:** El valor total más alto (en tu moneda predeterminada) permitido para productos de esta categoría en un solo pedido.
- **Acciones:** Botones para "Editar" una regla existente o "Eliminarla".

También encontrarás:

- **Botón "Añadir Nueva Regla":** Un botón prominente para crear una nueva regla de valor máximo de compra.

**Al añadir o editar una regla, normalmente encontrarás los siguientes campos:**

1. **Seleccionar Categoría:**

   - **Qué hace este ajuste:** Te permite elegir a qué categoría de producto específica se aplicará esta regla de valor máximo de compra. Normalmente verás un desplegable o un selector de árbol de categorías.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se selecciona una categoría:* La regla se aplicará a todos los productos dentro de esa categoría (y a menudo a sus subcategorías, dependiendo de la lógica del módulo).
     - *Cuando no se selecciona ninguna categoría (o si la cambias):* La regla será inválida o se aplicará a una categoría diferente.
   - **Valor recomendado:** Selecciona la categoría específica que deseas limitar.
   - **Escenario / ejemplo de comerciante:** Quieres limitar las compras de productos de "Electrónica". Seleccionarías "Electrónica" de la lista.
2. **Valor Máximo de Compra:**

   - **Qué hace este ajuste:** Este es el valor numérico (en la moneda predeterminada de tu tienda) que representa el total más alto permitido para productos de la categoría seleccionada en el carrito de un cliente.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se establece un valor específico (por ejemplo, 500):* Los clientes no podrán tener más de 500 unidades del valor de la moneda predeterminada de tu tienda en productos de la categoría seleccionada en su carrito.
     - *Cuando se establece en 0 o se deja vacío (si está permitido):* Esto podría deshabilitar la regla para la categoría o considerarse una entrada inválida.
   - **Valor recomendado:** Un valor numérico positivo que represente tu límite deseado (por ejemplo, `250.00`).
   - **Escenario / ejemplo de comerciante:** Quieres limitar las "Impresiones de Arte de Edición Limitada" a un máximo de $250 por pedido. Introducirías `250` aquí. El módulo calculará automáticamente los valores equivalentes para otras monedas si tu tienda las soporta.

**Efecto de los cambios:**

- **Añadir una nueva regla:** Aplica inmediatamente el valor máximo de compra para la categoría seleccionada en toda tu tienda. Se impedirá a los clientes exceder este límite.
- **Editar una regla:** Actualiza el valor máximo para una categoría existente. El nuevo límite entra en vigor inmediatamente.
- **Eliminar una regla:** Elimina la restricción para esa categoría. Los clientes ya no estarán limitados en sus compras de esa categoría.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1. Revisa periódicamente tus categorías de productos e identifica aquellas que podrían beneficiarse de un límite de valor de compra (por ejemplo, nuevos productos de alta demanda, artículos con existencias limitadas o productos con acuerdos de distribución específicos).
2. Navega a la pantalla de configuración "Valor máximo de compra por categorías".
3. Utiliza el botón "Añadir Nueva Regla" para crear nuevos límites.
4. Monitoriza los comentarios de los clientes o los patrones de pedidos para ajustar los límites existentes según sea necesario utilizando la acción "Editar".
5. Si una línea de productos o categoría ya no requiere un límite, utiliza la acción "Eliminar" para eliminar la regla.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| AdminMaobcController (Gestión de Reglas) | **Seleccionar Categoría** | Nombre de Categoría Específico | Define a qué categoría de producto se aplica el valor máximo. |
| AdminMaobcController (Gestión de Reglas) | **Valor Máximo de Compra** | Valor numérico (por ejemplo, `250.00`) | Establece el valor total más alto permitido para productos de la categoría seleccionada en un solo pedido (en la moneda predeterminada). Convierte automáticamente para otras monedas. |

## 3. Resolución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: He establecido un límite, pero los clientes aún pueden excederlo. ¿Qué está mal?**
R1:

- **Verifica la Asignación de Categorías:** Asegúrate de que los productos en cuestión estén correctamente asignados a la categoría para la cual estableciste el límite.
- **Módulo Habilitado:** Verifica que el módulo "Valor máximo de compra por categorías" esté habilitado en **Módulos > Gestor de Módulos**.
- **Regla Activa:** Ve a la configuración del módulo y confirma que la regla para la categoría específica esté presente y tenga un valor máximo válido.
- **Borrar Caché:** A veces, la caché de PrestaShop puede impedir que los cambios surtan efecto inmediatamente. Ve a **Parámetros Avanzados > Rendimiento** y haz clic en "Borrar caché".

**P2: El módulo muestra la moneda incorrecta o no convierte correctamente.**
R2: El módulo utiliza automáticamente la moneda predeterminada de tu tienda para el valor que introduces y luego lo convierte para otras monedas.

- **Moneda Predeterminada:** Asegúrate de que tu moneda predeterminada esté configurada correctamente en **Internacional > Monedas**. El valor que introduces en la configuración del módulo siempre debe estar en esta moneda predeterminada.
- **Tasas de Cambio:** Verifica tus tasas de cambio en **Internacional > Monedas** para asegurarte de que estén actualizadas y sean precisas para las monedas que soportas.

**P3: ¿Puedo establecer límites diferentes para diferentes grupos de clientes?**
R3: Este módulo específico establece un límite global por categoría, aplicable a todos los clientes. Si necesitas límites diferentes para grupos de clientes específicos (por ejemplo, mayoristas vs. minoristas), necesitarías un módulo más avanzado o un desarrollo personalizado.

**P4: ¿Cómo traduzco los mensajes de error que se muestran a los clientes?**
R4: Los mensajes del front-office del módulo suelen ser traducibles a través del sistema de traducción de PrestaShop:

1. Ve a **Internacional > Traducciones**.
2. Selecciona "Traducciones de módulos instalados".
3. Elige tu tema, el idioma y luego selecciona "Valor máximo de compra por categorías" de la lista de módulos.
4. Luego podrás encontrar y editar las cadenas de texto mostradas por el módulo a tus clientes.

**P5: El módulo parece estar en conflicto con otro módulo en mi carrito/proceso de pago.**
R5: Los conflictos de módulos pueden ocurrir a veces.

- **Aísla el Problema:** Deshabilita temporalmente otros módulos que interactúen con el carrito o la página del producto uno por uno para ver si el conflicto se resuelve.
- **Compatibilidad del Tema:** Si estás utilizando un tema personalizado, podría tener anulaciones específicas que interfieran. Comprueba si el problema persiste con el tema predeterminado de PrestaShop.
- **Contacta con Soporte:** Si no puedes identificar el conflicto, reúne los detalles (qué módulos, qué error exacto) y contacta con el soporte de MyPresta.eu para obtener ayuda.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Valor máximo de compra por categorías" (`maobc`) sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop. Utiliza principalmente un Controlador de Administración para gestionar la configuración y las reglas, y un Controlador Frontal para interceptar las solicitudes AJAX relacionadas con las actualizaciones del carrito. La lógica central reside dentro de la clase principal del módulo, que se engancha a varios eventos de PrestaShop para aplicar los límites de valor basados en categorías. Almacena su configuración en la tabla `ps_configuration` y gestiona sus reglas a través de una tabla personalizada y un Controlador de Administración.

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**:

  - `controllers/front/ajax.php`
    - **Nombre de la Clase**: `MaobcAjaxModuleFrontController` (extiende `ModuleFrontController`)
    - **Responsabilidad**: Este controlador es responsable de manejar las solicitudes AJAX desde el front-office, principalmente aquellas relacionadas con la adición de productos al carrito o la actualización de las cantidades del carrito. Intercepta estas solicitudes para realizar una validación en tiempo real contra las reglas de valor máximo de compra definidas antes de que PrestaShop procese la actualización del carrito. Devuelve respuestas JSON que indican éxito o fracaso con mensajes apropiados.
  - `controllers/front/index.php`
    - **Nombre de la Clase**: `MaobcIndexModuleFrontController` (extiende `ModuleFrontController`)
    - **Responsabilidad**: Este controlador podría servir como un recurso alternativo o un punto de entrada simple, pero dada la funcionalidad del módulo, `ajax.php` es el punto de interacción principal del front-office. Podría renderizar una página simple o redirigir si se accede directamente.
- **Controladores de Administración del Back-Office**:

  - `controllers/admin/AdminMaobc.php`
    - **Nombre de la Clase**: `AdminMaobcController` (extiende `ModuleAdminController`)
    - **Nombre de la Pestaña**: "Valor máximo de compra por categorías" (o similar, accesible a través del botón "Configurar" del módulo).
    - **Entidad Gestionada**: Este controlador gestiona la entidad `maobc` personalizada, que representa las reglas individuales para los valores máximos de compra por categoría. Maneja las operaciones CRUD (Crear, Leer, Actualizar, Eliminar) para estas reglas.
    - **Responsabilidad**: Muestra una lista (cuadrícula) de todas las reglas configuradas, permite a los administradores añadir nuevas reglas, editar las existentes (seleccionando una categoría y estableciendo un valor máximo) y eliminar reglas. Interactúa con el almacenamiento de datos interno del módulo (probablemente una tabla de base de datos personalizada o entradas de `ps_configuration`).
  - `controllers/admin/index.php`
    - **Nombre de la Clase**: `AdminMaobcIndexController` (extiende `ModuleAdminController`)
    - **Responsabilidad**: Similar al `index.php` del front-office, este podría ser un punto de entrada simple o un recurso alternativo. El `AdminMaobcController` es el controlador principal para gestionar las reglas del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto sugiere que la lógica central y el manejo de datos del módulo probablemente estén integrados directamente en el archivo principal del módulo (`maobc/index.php`) o gestionados a través de la clase `Configuration` estándar de PrestaShop para la configuración y, potencialmente, una tabla de base de datos personalizada gestionada directamente por el `AdminMaobcController` sin un `ObjectModel` dedicado.

### 4.4 Activos JavaScript (`views/js/`)

- `views/js/maobc.js`
  - **Alcance**: Front-office.
  - **Detalles**: Este script es probablemente responsable de las interacciones del lado del cliente relacionadas con las actualizaciones del carrito. Podría:
    - Anular o extender las funciones predeterminadas del carrito AJAX de PrestaShop (por ejemplo, clics en el botón `añadir al carrito`).
    - Interceptar las respuestas AJAX de `controllers/front/ajax.php` para mostrar mensajes de error personalizados al usuario si se excede un valor máximo.
    - Potencialmente actualizar la interfaz de usuario (por ejemplo, deshabilitar botones, mostrar alertas) basándose en los resultados de la validación.
    - Probablemente utilizará `jQuery` o eventos `prestashop.on` para vincular su lógica.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `views/css/maobc.css`
  - **Alcance**: Front-office.
  - **Detalles**: Esta hoja de estilo proporciona un estilo personalizado para los elementos del front-office del módulo, principalmente los mensajes de notificación que se muestran a los clientes cuando se excede un valor máximo de compra.
  - **Selectores de Clases CSS Clave**: Los desarrolladores deben inspeccionar este archivo en busca de clases como `.maobc-error-message`, `.maobc-alert` o similares, que pueden anularse en el `custom.css` o `theme.css` de su tema para que coincidan con la marca de la tienda.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de gancho (`views/templates/hook/`)**:

  - El dossier del módulo no lista explícitamente plantillas en `views/templates/hook/`. Esto sugiere que cualquier mensaje o contenido dinámico podría inyectarse directamente a través de JavaScript o renderizarse mediante el archivo principal del módulo utilizando métodos `display()`.
- **Plantillas de administración (`views/templates/admin/`)**:

  - El dossier del módulo no lista explícitamente plantillas en `views/templates/admin/`. El `AdminMaobcController` probablemente utiliza formularios de ayuda estándar de PrestaShop (`HelperList`, `HelperForm`) para su cuadrícula y formularios de configuración, que generan su HTML dinámicamente.
- **Plantillas del front-office (`views/templates/front/`)**:

  - `views/templates/front/displayShoppingCart.tpl`
    - **Propósito**: Esta plantilla se utiliza probablemente para mostrar el mensaje de error personalizado en la página del carrito de compras si se excede el valor máximo de compra para una categoría. Contendría la estructura HTML para la alerta o notificación que informa al cliente sobre el límite. Probablemente está enganchada a un `displayShoppingCartFooter` o un gancho similar.

### 4.7 Esquema de Base de Datos y Mapa de Ganchos

- **Tablas de Base de Datos**:

  - El módulo probablemente crea una tabla de base de datos personalizada (por ejemplo, `ps_maobc_rules`) para almacenar el ID de la categoría y el valor máximo de compra asociado para cada regla.
  - Los valores de configuración (por ejemplo, estado de habilitación del módulo, ajustes generales) se almacenan en la tabla `ps_configuration`, típicamente con claves prefijadas `MAOBC_`.
- **Tabla de Ganchos Registrados**:

| Nombre del Gancho | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza en la sección `<head>` de todas las páginas del front-office. | Potencialmente utilizado para cargar los activos `maobc.js` y `maobc.css`, o para inyectar variables JavaScript. |
| `displayRightColumn` / `displayLeftColumn` | Renderiza contenido en las columnas laterales. | Menos probable para este módulo, pero podría usarse para mostrar un mensaje estático sobre los límites de compra. |
| `displayProductAdditionalInfo` / `displayProductButtons` | Se renderiza en la página del producto. | Podría usarse para mostrar un mensaje de advertencia en la página del producto si el artículo pertenece a una categoría restringida. |
| `displayShoppingCartFooter` / `displayShoppingCart` | Se renderiza en la página del carrito de compras. | Se utiliza para mostrar la plantilla `displayShoppingCart.tpl` con mensajes de error si se exceden los límites. |
| `actionCartSave` | Se ejecuta después de guardar un carrito (por ejemplo, producto añadido/eliminado, cantidad cambiada). | Crucial para la validación del lado del servidor del contenido del carrito contra los límites de categoría. Aquí es donde la lógica central evita estados de carrito no válidos. |
| `actionAjaxDieCartController` | Se ejecuta antes de una respuesta AJAX del CartController. | Permite que el módulo intercepte y modifique las respuestas AJAX, inyectando mensajes de error personalizados si se exceden los límites durante las actualizaciones del carrito AJAX. |
| `actionFrontControllerSetMedia` | Se ejecuta antes de que un controlador frontal renderice su salida. | Se utiliza para registrar archivos CSS y JavaScript del front-office. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y para descargar las últimas versiones del módulo "Valor máximo de compra por categorías", inicia sesión en tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto a la funcionalidad o integración del módulo.
"""

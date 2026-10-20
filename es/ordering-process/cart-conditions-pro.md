---
title: "Cart conditions pro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Cart conditions pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "Cart conditions pro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Cart conditions pro en MyPresta.eu](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/cart-conditions-pro/)
>
> ---


# Cart conditions pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y son suficientes para este módulo.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Cart conditions pro)

Esta es la pantalla de configuración principal del módulo, donde se establecen los comportamientos globales y se accede a las áreas específicas de gestión de condiciones.

- **Qué hace esta configuración:** Controla el comportamiento general del módulo y proporciona enlaces rápidos para gestionar sus condiciones.
- **Efecto de cambiar esta configuración:** Determina qué tan ampliamente se aplican las condiciones y cómo se manejan ciertos casos excepcionales.

#### Ajustes Generales

1. **Excluir clientes de las condiciones**

   - **Qué hace esta configuración:** Le permite especificar ciertos grupos de clientes o clientes individuales que estarán exentos de cualquier condición de carrito que configure.
   - **Efecto de cambiar esta configuración:**
     - *Cuando está habilitado (y se seleccionan clientes/grupos):* Los clientes/grupos seleccionados siempre podrán proceder al pago, independientemente de si su carrito cumple las condiciones.
     - *Cuando está deshabilitado (o no se seleccionan clientes/grupos):* Todos los clientes estarán sujetos a las condiciones del carrito.
   - **Valor recomendado:** "Desactivado" por defecto, a menos que tenga clientes B2B específicos o VIPs a los que quiera eximir.
   - **Escenario / ejemplo de comerciante:** Tiene un grupo de clientes mayoristas que siempre recibe un trato especial y no debe estar restringido por valores mínimos de pedido.
2. **Excluir productos de las condiciones**

   - **Qué hace esta configuración:** Le permite especificar ciertos productos que no contarán ni se verán afectados por ninguna condición del carrito. Esto es útil para regalos, muestras o artículos promocionales específicos.
   - **Efecto de cambiar esta configuración:**
     - *Cuando está habilitado (y se seleccionan productos):* Los productos seleccionados se ignorarán al evaluar las condiciones del carrito. Por ejemplo, si tiene una condición de "mínimo 3 artículos", y un cliente tiene 2 artículos regulares + 1 artículo excluido, la condición podría seguir fallando.
     - *Cuando está deshabilitado (o no se seleccionan productos):* Todos los productos del carrito se considerarán al evaluar las condiciones.
   - **Valor recomendado:** "Desactivado" por defecto. Habilítelo solo si tiene productos específicos que deben estar exentos de las condiciones.
   - **Escenario / ejemplo de comerciante:** Ofrece un producto de muestra gratuito con cada pedido. No quiere que esta muestra cuente para una condición de cantidad mínima de producto.
3. **Bloquear pedido de productos con Varias fechas de disponibilidad**

   - **Qué hace esta configuración:** Esta opción aborda específicamente los productos que tienen diferentes fechas de disponibilidad (por ejemplo, artículos en pre-pedido con fechas de lanzamiento escalonadas). Si está habilitada, evita que los clientes pidan una mezcla de productos disponibles de inmediato y productos disponibles en el futuro en el mismo carrito.
   - **Efecto de cambiar esta configuración:**
     - *Cuando está "Activado":* Si el carrito de un cliente contiene productos con diferentes fechas de disponibilidad, se le impedirá el pago. Tendría que realizar pedidos separados para los artículos con diferente disponibilidad.
     - *Cuando está "Desactivado":* Los clientes pueden pedir productos con varias fechas de disponibilidad en un solo carrito.
   - **Valor recomendado:** "Desactivado" a menos que tenga razones logísticas específicas para separar los pedidos según la disponibilidad.
   - **Escenario / ejemplo de comerciante:** Vende tanto artículos en stock como artículos en pre-pedido. Para simplificar el envío y evitar retener pedidos, desea que los clientes realicen pedidos separados para los artículos en pre-pedido.

#### Enlaces de Gestión de Condiciones

Debajo de la configuración general, encontrará enlaces para gestionar diferentes tipos de condiciones. Estos enlaces le llevarán a pantallas de administración dedicadas.

- **Gestionar Condiciones (General):** Aquí es donde se definen condiciones amplias basadas en asociaciones de productos, categorías u otras reglas generales.
- **Gestionar Condiciones por País:** Defina condiciones que se apliquen solo a clientes de países específicos.
- **Gestionar Condiciones por Cantidad:** Establezca cantidades mínimas o máximas de productos/categorías requeridas en el carrito.
- **Gestionar Condiciones por Valor:** Establezca valores totales mínimos o máximos del carrito requeridos.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 AdminCartConditionController (Back Office > Módulos > Cart conditions pro > Gestionar Condiciones)

Esta pantalla le permite definir condiciones generales, a menudo basadas en asociaciones de productos o categorías.

- **Nombre de la pantalla y ubicación del menú:** "Gestionar Condiciones" (accesible desde la página de configuración principal del módulo).
- **Acciones y configuraciones disponibles:**
  - **Tabla de listado:** Muestra todas las condiciones generales existentes con sus nombres, productos/categorías asociados y estado.
  - **Botón Añadir nueva condición:** Le permite crear una nueva condición.
    - **Nombre de la condición:** Un nombre descriptivo para su referencia interna.
    - **Productos/Categorías:** Seleccione productos específicos o categorías enteras que deben estar presentes (o no presentes) en el carrito.
    - **Grupos de clientes:** Aplique esta condición solo a grupos de clientes específicos.
    - **Cantidad mínima/máxima:** Defina un rango para el número de productos/categorías seleccionados.
    - **Valor mínimo/máximo:** Defina un rango para el valor total de los productos/categorías seleccionados.
    - **Mensaje:** El mensaje que se muestra al cliente si no se cumple la condición.
    - **Activo:** Habilita o deshabilita la condición.
  - **Botones Editar/Eliminar:** Modificar o eliminar condiciones existentes.
- **Efecto de los cambios:**
  - Añadir una nueva condición aplica inmediatamente esa regla a los carritos de los clientes.
  - Modificar una condición actualiza sus criterios y mensaje.
  - Eliminar una condición elimina la restricción.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise regularmente sus condiciones, especialmente después de añadir nuevos productos, categorías o ejecutar promociones, para asegurarse de que se alinean con su estrategia de ventas actual.

#### 2.2.2 AdminCartAssociationsConditionController (Back Office > Módulos > Cart conditions pro > Gestionar Condiciones > (Condición Específica) > Asociaciones)

Esta pantalla se accede típicamente al editar una condición general y le permite especificar qué productos o categorías están *asociados* con esa condición.

- **Nombre de la pantalla y ubicación del menú:** Se accede editando una condición desde "Gestionar Condiciones".
- **Acciones y configuraciones disponibles:**
  - **Buscar y seleccionar productos/categorías:** Herramientas para encontrar y añadir productos específicos o categorías enteras que forman parte de esta condición.
  - **Lista de productos/categorías seleccionados:** Muestra todos los artículos actualmente asociados con la condición.
  - **Botón Eliminar:** Eliminar un artículo de la asociación.
- **Efecto de los cambios:** Impacta directamente qué productos o categorías son evaluados por la condición principal. Por ejemplo, si una condición establece "El carrito debe contener al menos 2 artículos de la categoría 'Electrónica'", esta pantalla es donde se define qué productos pertenecen a esa categoría "Electrónica" para esta condición específica.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Al crear o actualizar una condición, asegúrese de que todos los productos y categorías relevantes estén correctamente asociados.

#### 2.2.3 AdminCartCountryConditionController (Back Office > Módulos > Cart conditions pro > Gestionar Condiciones por País)

Esta pantalla le permite definir condiciones específicas para el país de envío del cliente.

- **Nombre de la pantalla y ubicación del menú:** "Gestionar Condiciones por País" (accesible desde la página de configuración principal del módulo).
- **Acciones y configuraciones disponibles:**
  - **Tabla de listado:** Muestra las condiciones existentes específicas por país.
  - **Botón Añadir nueva condición:**
    - **País:** Seleccione el país de destino.
    - **Cantidad mínima/máxima:** Para todos los productos del carrito, o productos/categorías específicos.
    - **Valor mínimo/máximo:** Para el valor total del carrito.
    - **Mensaje:** El mensaje que se muestra si no se cumple la condición.
    - **Activo:** Habilitar o deshabilitar.
- **Efecto de los cambios:** Aplica reglas de carrito específicas solo a los clientes cuya dirección de envío se encuentra en el país seleccionado.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Útil para tiendas internacionales con diferentes costos de envío, regulaciones aduaneras o estrategias de mercado por país.

#### 2.2.4 AdminCartQuantityConditionController (Back Office > Módulos > Cart conditions pro > Gestionar Condiciones por Cantidad)

Esta pantalla se centra en las condiciones relacionadas con el número total de artículos en el carrito, o la cantidad de artículos/categorías específicos.

- **Nombre de la pantalla y ubicación del menú:** "Gestionar Condiciones por Cantidad" (accesible desde la página de configuración principal del módulo).
- **Acciones y configuraciones disponibles:**
  - **Tabla de listado:** Muestra todas las condiciones basadas en cantidad.
  - **Botón Añadir nueva condición:**
    - **Nombre de la condición:**
    - **Cantidad total mínima/máxima:** Para todo el carrito.
    - **Cantidad mínima/máxima de productos/categorías específicos:** Seleccione artículos y establezca reglas de cantidad para ellos.
    - **Grupos de clientes:** Aplicar a grupos específicos.
    - **Mensaje:**
    - **Activo:**
- **Efecto de los cambios:** Aplica reglas basadas en el recuento de artículos en el carrito, lo que puede usarse para fomentar compras al por mayor o gestionar el inventario.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esto para promociones de "compre X y obtenga Y", cantidad mínima de pedido (MOQ) para ventas al por mayor, o para asegurar que los clientes cumplan un cierto umbral para el envío gratuito.

#### 2.2.5 AdminCartValueConditionController (Back Office > Módulos > Cart conditions pro > Gestionar Condiciones por Valor)

Esta pantalla es para establecer condiciones basadas en el valor monetario total del carrito del cliente.

- **Nombre de la pantalla y ubicación del menú:** "Gestionar Condiciones por Valor" (accesible desde la página de configuración principal del módulo).
- **Acciones y configuraciones disponibles:**
  - **Tabla de listado:** Muestra las condiciones existentes basadas en valor.
  - **Botón Añadir nueva condición:**
    - **Nombre de la condición:**
    - **Valor total mínimo/máximo del carrito:** Establezca un rango para el valor total del carrito.
    - **Grupos de clientes:**
    - **Mensaje:**
    - **Activo:**
- **Efecto de los cambios:** Aplica reglas basadas en el valor monetario del carrito, impactando directamente el valor promedio del pedido.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Ideal para establecer un valor mínimo de pedido para el envío gratuito, o un valor mínimo de pedido general para asegurar la rentabilidad.

#### 2.2.6 index.php (cartcon/controllers/admin/index.php)

Este archivo es una práctica estándar de PrestaShop para evitar la lista de directorios y no representa una pantalla configurable. Simplemente contiene `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;` para redirigir si alguien intenta acceder al directorio directamente.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Excluir clientes de las condiciones | Desactivado | Exime a clientes/grupos específicos de todas las condiciones. |
|  | Excluir productos de las condiciones | Desactivado | Exime a productos específicos de todas las condiciones. |
|  | Bloquear pedido de productos con Varias fechas de disponibilidad | Desactivado | Evita pedidos mixtos de artículos en stock y en pre-pedido. |
| **Gestionar Condiciones** | Nombre de la condición | Definido por el usuario | Etiqueta interna para la condición. |
|  | Productos/Categorías | Definido por el usuario | Selecciona artículos/categorías requeridos o restringidos. |
|  | Grupos de clientes | Todos | Aplica la condición a segmentos de clientes específicos. |
|  | Cantidad Mín/Máx | Definido por el usuario | Establece el rango de cantidad para los artículos/categorías seleccionados. |
|  | Valor Mín/Máx | Definido por el usuario | Establece el rango de valor para los artículos/categorías seleccionados. |
|  | Mensaje | Definido por el usuario | Mensaje para el cliente cuando no se cumple la condición. |
|  | Activo | Sí | Habilita/deshabilita la condición. |
| **Gestionar Condiciones por País** | País | Definido por el usuario | Dirige condiciones a países específicos. |
|  | Cantidad Mín/Máx | Definido por el usuario | Rango de cantidad para carritos del país seleccionado. |
|  | Valor Mín/Máx | Definido por el usuario | Rango de valor para carritos del país seleccionado. |
|  | Mensaje | Definido por el usuario | Mensaje para el cliente en caso de fallo específico del país. |
|  | Activo | Sí | Habilita/deshabilita la condición por país. |
| **Gestionar Condiciones por Cantidad** | Nombre de la condición | Definido por el usuario | Etiqueta interna para la condición por cantidad. |
|  | Cantidad Total Mín/Máx | Definido por el usuario | Rango de cantidad para todo el carrito. |
|  | Cantidad Mín/Máx de Productos/Categorías Específicos | Definido por el usuario | Rango de cantidad para artículos/categorías seleccionados. |
|  | Grupos de clientes | Todos | Aplica a segmentos de clientes específicos. |
|  | Mensaje | Definido por el usuario | Mensaje para el cliente en caso de fallo por cantidad. |
|  | Activo | Sí | Habilita/deshabilita la condición por cantidad. |
| **Gestionar Condiciones por Valor** | Nombre de la condición | Definido por el usuario | Etiqueta interna para la condición por valor. |
|  | Valor Total Mín/Máx del Carrito | Definido por el usuario | Rango de valor para todo el carrito. |
|  | Grupos de clientes | Todos | Aplica a segmentos de clientes específicos. |
|  | Mensaje | Definido por el usuario | Mensaje para el cliente en caso de fallo por valor. |
|  | Activo | Sí | Habilita/deshabilita la condición por valor. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Mis condiciones están configuradas, pero no parecen funcionar en el front office. ¿Qué está mal?**
**R1:**

- **Verificar el estado de la condición:** Asegúrese de que el interruptor "Activo" para cada condición que haya configurado esté en "Sí".
- **Borrar caché:** PrestaShop a menudo almacena contenido en caché. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
- **Posición del módulo:** Verifique que el módulo esté enganchado correctamente. Los hooks `displayShoppingCart` y `displayPaymentTop` son cruciales. Si su tema tiene hooks personalizados, es posible que necesite ayuda de un desarrollador.
- **Grupos de clientes:** Vuelva a verificar si las condiciones se aplican a los grupos de clientes correctos y si su cliente de prueba pertenece a ese grupo.
- **IDs de producto/categoría:** Al seleccionar productos o categorías, asegúrese de haber elegido los correctos. A veces, nombres similares pueden causar confusión.

**P2: El mensaje que se muestra a los clientes no es claro o no se ve bien con mi tema.**
**R2:**

- **Editar mensaje:** Vaya a la condición específica (por ejemplo, Gestionar Condiciones por Valor, luego edite la condición) y actualice el campo "Mensaje" con un texto más claro y útil.
- **Estilo del tema:** La apariencia visual (fuente, color, tamaño) del mensaje está controlada por el CSS de su tema de PrestaShop. Si necesita cambiar el estilo, deberá consultar a un diseñador web o desarrollador para añadir reglas CSS personalizadas a su tema. Los archivos CSS del módulo (`cartcon.css`) proporcionan el estilo base.

**P3: ¿Puedo establecer diferentes condiciones para diferentes idiomas/países?**
**R3:**

- **Condiciones específicas por país:** Sí, utilice la pantalla "Gestionar Condiciones por País" para establecer reglas que se apliquen solo a clientes de países específicos.
- **Mensajes multilingües:** Al editar una condición, el campo "Mensaje" suele tener un selector de idioma (un icono de bandera). Haga clic en él para proporcionar traducciones de su mensaje en todos los idiomas activos de su tienda.

**Q4: Quiero excluir un producto específico de TODAS las condiciones. ¿Cómo lo hago?**
**R4:**

- En la página de configuración principal del módulo (Back Office > Módulos > Configurar > Cart conditions pro), utilice la configuración "Excluir productos de las condiciones". Puede buscar y seleccionar los productos específicos que desea eximir.

**Q5: El módulo está bloqueando el pago, pero no puedo encontrar qué condición lo está causando.**
**R5:**

- **Revisar todas las condiciones:** Revise "Gestionar Condiciones", "Gestionar Condiciones por País", "Gestionar Condiciones por Cantidad" y "Gestionar Condiciones por Valor" una por una. Verifique el estado "Activo" de cada una y revise sus criterios.
- **Probar sistemáticamente:** Si tiene muchas condiciones, intente deshabilitarlas una por una (o en grupos) y pruebe el carrito hasta que identifique la culpable. Luego, vuelva a habilitarlas y ajuste la condición problemática.
- **Verificar grupo de clientes:** Asegúrese de que su cliente de prueba no forma parte de un grupo de clientes excluido.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo "Cart conditions pro" sigue el patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, extendiendo principalmente `Module` para su configuración principal y `AdminController` para interfaces de gestión dedicadas. Aprovecha el sistema de hooks de PrestaShop para inyectar lógica y mostrar mensajes en puntos críticos del front-office (carrito, pago) y utiliza `ObjectModel` implícitamente para gestionar sus diversas entidades de condición. El módulo se basa en tablas de base de datos personalizadas para almacenar sus complejas reglas de condición.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

El módulo no parece tener controladores frontales dedicados en el inventario proporcionado. La lógica y la visualización del front-office probablemente se manejan directamente a través del archivo principal del módulo `cartcon.php` mediante callbacks de hooks.

#### Controladores de Administración de Back-Office

Todos los controladores de administración extienden `ModuleAdminController` (o `AdminController` en versiones anteriores de PrestaShop) y son responsables de gestionar los diversos tipos de condiciones.

- `cartcon/controllers/admin/AdminCartAssociationsConditionController.php`

  - **Nombre de la clase:** `AdminCartAssociationsConditionController`
  - **Clase padre:** `ModuleAdminController`
  - **Responsabilidad:** Gestiona las asociaciones (productos, categorías) vinculadas a una condición de carrito general específica. Este controlador proporciona la interfaz para buscar y seleccionar productos/categorías que forman parte de los criterios de una condición. Interactúa con la tabla `cartcon_ass`.
- `cartcon/controllers/admin/AdminCartConditionController.php`

  - **Nombre de la clase:** `AdminCartConditionController`
  - **Clase padre:** `ModuleAdminController`
  - **Responsabilidad:** Gestiona las condiciones principales y generales del carrito. Esta es la interfaz principal para crear, editar y eliminar condiciones basadas en la presencia, cantidad o valor de productos/categorías. Interactúa con la tabla `cartcon`.
- `cartcon/controllers/admin/AdminCartCountryConditionController.php`

  - **Nombre de la clase:** `AdminCartCountryConditionController`
  - **Clase padre:** `ModuleAdminController`
  - **Responsabilidad:** Gestiona las condiciones del carrito específicamente vinculadas a los países de los clientes. Permite definir reglas que solo se aplican cuando el país de envío del cliente coincide con un país especificado. Interactúa con la tabla `cartcon_country`.
- `cartcon/controllers/admin/AdminCartQuantityConditionController.php`

  - **Nombre de la clase:** `AdminCartQuantityConditionController`
  - **Clase padre:** `ModuleAdminController`
  - **Responsabilidad:** Gestiona las condiciones basadas en la cantidad total de artículos en el carrito o la cantidad de productos/categorías específicos. Interactúa con la tabla `cartcon_quantity`.
- `cartcon/controllers/admin/AdminCartValueConditionController.php`

  - **Nombre de la clase:** `AdminCartValueConditionController`
  - **Clase padre:** `ModuleAdminController`
  - **Responsabilidad:** Gestiona las condiciones basadas en el valor monetario total del carrito. Interactúa con la tabla `cartcon_value`.
- `cartcon/controllers/admin/index.php`

  - **Responsabilidad:** Archivo de seguridad estándar de PrestaShop para evitar la lista de directorios. Redirige al directorio padre.

### 4.3 Clases y Modelos Principales (`classes/`)

El inventario proporcionado no enumera archivos explícitos en un directorio `classes/`. Esto sugiere que la lógica central del módulo y las definiciones de `ObjectModel` (si las hay) están incrustadas en el archivo principal `cartcon.php` o dentro de los propios archivos del controlador de administración, lo cual es un patrón común para módulos más simples o versiones anteriores de PrestaShop. Si se utilizan `ObjectModel`s, sus arrays `$definition` se encontrarían dentro de la clase del controlador respectivo o del módulo principal.

### 4.4 Activos JavaScript (`views/js/`)

- `cartcon/lib/searchTool/views/js/autocomplete.js`

  - **Alcance:** Back-office.
  - **Responsabilidad:** Proporciona funcionalidad de autocompletado para buscar productos, categorías o clientes dentro de los formularios de administración (por ejemplo, al configurar exclusiones o asociaciones de condiciones). Probablemente se enlaza a campos de entrada, envía solicitudes AJAX a un endpoint de búsqueda y muestra sugerencias.
- `cartcon/views/js/cartcon.js`

  - **Alcance:** Front-office y potencialmente Back-office.
  - **Responsabilidad:**
    - **Front-office:** Maneja la visualización dinámica de los mensajes de condición del carrito, deshabilitando/habilitando el botón "Proceder al pago" basándose en las respuestas AJAX del servidor sobre la validez del carrito. Podría escuchar las actualizaciones del carrito (`prestashop.on('updateCart', ...)` o eventos similares) para reevaluar las condiciones.
    - **Back-office:** Podría contener lógica para la validación de formularios, visibilidad dinámica de campos u otras mejoras de la interfaz de usuario específicas de las páginas de configuración del módulo.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `cartcon/lib/searchTool/views/css/autocomplete.css`

  - **Alcance:** Back-office.
  - **Responsabilidad:** Estiliza los desplegables de sugerencias de autocompletado y los campos de entrada de búsqueda utilizados en los formularios de administración, asegurando una experiencia de búsqueda consistente y fácil de usar.
- `cartcon/views/css/cartcon.css`

  - **Alcance:** Front-office y Back-office.
  - **Responsabilidad:**
    - **Front-office:** Estiliza los mensajes de notificación mostrados en la página del carrito, la página de pago o la página del producto cuando no se cumplen las condiciones. Define la apariencia de los cuadros de advertencia, el texto y, potencialmente, el estado deshabilitado del botón de pago.
    - **Back-office:** Proporciona estilo para los formularios de configuración del módulo y las tablas de lista, asegurando que se integren bien con el tema del back office de PrestaShop.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:** Busque clases como `.cartcon-alert`, `.cartcon-message`, `.cartcon-disabled-button` o similares dentro de este archivo para apuntar y personalizar la salida del front-office del módulo.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

La lógica de visualización del front-office del módulo probablemente está incrustada directamente en los métodos de hook del archivo principal `cartcon.php`, que luego renderizan estas plantillas.

- `cartcon/views/templates/front/displayShoppingCart.tpl`

  - **Renderizado en el hook:** `displayShoppingCart`
  - **Propósito:** Muestra los mensajes de condición del carrito y potencialmente deshabilita el botón de pago en la página principal del carrito de compras si no se cumplen las condiciones. Recibe variables del método `hookDisplayShoppingCart` del módulo, indicando la validez del carrito y el mensaje a mostrar.
- `cartcon/views/templates/front/displayShoppingCartEmpty.tpl`

  - **Renderizado en el hook:** Potencialmente `displayShoppingCart` o un hook relacionado cuando el carrito está vacío.
  - **Propósito:** Proporciona una plantilla específica para mostrar mensajes o contenido alternativo cuando el carrito de compras está vacío, potencialmente relacionado con los requisitos de pedido mínimo.
- `cartcon/views/templates/front/productActions.tpl`

  - **Renderizado en el hook:** `displayProductActions` (típicamente cerca del botón "Añadir al carrito" en la página del producto).
  - **Propósito:** Puede usarse para mostrar pistas o advertencias sutiles en la propia página del producto si añadir el producto violaría una condición del carrito o si el producto requiere que se compren otros artículos con él.

#### Plantillas de administración (`views/templates/admin/`)

- `cartcon/lib/searchTool/views/scripts.tpl`

  - **Propósito:** Probablemente incluye dependencias de JavaScript o inicializa los scripts de autocompletado para los formularios de administración.
- `cartcon/views/templates/admin/AdminCartAssociationsCondition.tpl`

  - **Propósito:** La plantilla principal para `AdminCartAssociationsConditionController`, que muestra la interfaz para gestionar las asociaciones de productos/categorías para una condición. Esto incluiría campos de búsqueda, listas de elementos seleccionados y botones de guardar.
- `cartcon/views/templates/admin/adminSearchCustomer.tpl`

  - **Propósito:** Plantilla para la interfaz de búsqueda de clientes, utilizada al excluir clientes de las condiciones.
- `cartcon/views/templates/admin/script.tpl`

  - **Propósito:** Plantilla de script de administración general, que potencialmente incluye JavaScript específico del módulo o variables de configuración para el back office.
- `cartcon/views/templates/admin/search-attribute-value-result.tpl`

  - **Propósito:** Plantilla para mostrar los resultados de una búsqueda de atributo/valor dentro del panel de administración, probablemente utilizada en conjunto con búsquedas de productos.
- `cartcon/views/templates/admin/search-attribute-value.tpl`

  - **Propósito:** Plantilla para el campo de entrada de búsqueda y los elementos de la interfaz de usuario asociados para buscar atributos/valores de productos en la administración.
- `cartcon/views/templates/admin/selectedProducts.tpl`

  - **Propósito:** Plantilla para mostrar la lista de productos que han sido seleccionados y asociados con una condición particular en los formularios de administración.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

#### Tablas de la Base de Datos

El módulo crea tablas personalizadas para almacenar sus diversas condiciones y asociaciones. Estas tablas suelen tener el prefijo `ps_cartcon_` o `cartcon_`.

- `ps_cartcon`: Almacena las condiciones generales del carrito (nombre, mensaje, estado activo, etc.).
- `ps_cartcon_ass`: Almacena las asociaciones entre condiciones y productos/categorías específicos.
- `ps_cartcon_country`: Almacena las condiciones específicas por país.
- `ps_cartcon_quantity`: Almacena las condiciones basadas en la cantidad.
- `ps_cartcon_value`: Almacena las condiciones basadas en el valor.
- `ps_configuration`: La configuración del módulo como `CARTCON_CUSTOMERS`, `ccon_visibility_rule`, `CARTCON_FUTURE`, etc., se almacena aquí.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para cargar los activos CSS y JavaScript del módulo tanto para el front-office como para el back-office. |
| `displayPaymentTop` | En la parte superior de la página de selección de pago durante el proceso de compra. | Crítico para reevaluar las condiciones del carrito justo antes del pago y bloquear si es necesario. |
| `displayShoppingCart` | En la página principal del carrito de compras. | Hook principal para mostrar mensajes de condición y deshabilitar el botón de pago. |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración y se están configurando sus medios (JS/CSS). | Se utiliza para cargar activos JS/CSS específicos para las páginas de configuración del back-office del módulo. |
| `displayProductActions` | Típicamente cerca del botón "Añadir al carrito" en la página del producto. | Puede utilizarse para mostrar pistas o advertencias de condiciones específicas del producto. |
| `actionCartSave` | Después de guardar un carrito (por ejemplo, producto añadido/eliminado, cantidad cambiada). | (Implícito/Probable) El módulo probablemente usaría un `actionCartSave` o un hook similar para activar la reevaluación de las condiciones del carrito en el lado del servidor, lo que luego informa al JS del front-office. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Cart conditions pro", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar que el módulo funcione de manera óptima con su tienda PrestaShop.

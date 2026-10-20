---
title: "Descuento de carrito basado en el valor del carrito - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Descuento de carrito basado en el valor del carrito' de MyPresta.eu."
sidebar:
  label: "Descuento de carrito basado en el valor del carrito - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Cart discount based on cart value en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cart-discount-based-on-cart-value.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/cart-discount-based-on-cart-value/)
>
> ---


# Descuento de carrito basado en el valor del carrito

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento compatibles con PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla principal donde controla el comportamiento general y la configuración de su programa de descuentos de carrito.

- **Activar programa**

  - **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar todo el programa de descuentos de carrito.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* El módulo comprobará activamente los valores del carrito y aplicará descuentos según sus reglas definidas.
    - *Cuando está deshabilitado (NO):* No se aplicarán descuentos de carrito y no aparecerán mensajes relacionados en la página del carrito, independientemente de otras configuraciones.
  - **Valor recomendado:** SÍ (una vez que haya configurado sus reglas de descuento).
  - **Escenario / ejemplo de comerciante:** Podría deshabilitarlo temporalmente durante una venta especial donde se aplican otras reglas de descuento, o si necesita realizar mantenimiento.
- **Desactivar programa de descuentos de carrito para grupos de clientes seleccionados**

  - **Qué hace este ajuste:** Le permite evitar que grupos de clientes específicos (por ejemplo, mayoristas, VIP o invitados) reciban estos descuentos basados en el valor del carrito.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está seleccionado:* Los clientes que pertenecen a los grupos elegidos no recibirán ningún descuento de este módulo, incluso si el valor de su carrito cumple los criterios.
    - *Cuando no está seleccionado:* Todos los grupos de clientes son elegibles para los descuentos.
  - **Valor recomendado:** Depende de su estrategia comercial. Si tiene precios especiales para ciertos grupos, podría excluirlos.
  - **Escenario / ejemplo de comerciante:** Tiene un grupo de clientes "Mayoristas" que ya recibe precios especiales. Seleccionaría este grupo aquí para evitar la acumulación de descuentos.
- **Tipo de precio**

  - **Qué hace este ajuste:** Determina si el valor del carrito para el cálculo del descuento debe incluir o excluir impuestos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "Precio con impuestos":* El descuento se calcula en función del valor total del carrito *incluyendo* IVA/impuestos.
    - *Cuando se establece en "Precio sin impuestos":* El descuento se calcula en función del valor total del carrito *excluyendo* IVA/impuestos.
  - **Valor recomendado:** "Precio con impuestos" para la mayoría de las tiendas B2C, "Precio sin impuestos" para tiendas B2B o si su precio principal es sin impuestos.
  - **Escenario / ejemplo de comerciante:** Si sus clientes están acostumbrados a ver los precios con impuestos, calcular el descuento en función del "Precio con impuestos" les resultará más natural y transparente.
- **Excluir productos con descuento**

  - **Qué hace este ajuste:** Controla si los productos que ya están en oferta o tienen un precio específico (por ejemplo, de una regla de catálogo) deben contar para el valor del carrito para el cálculo del descuento.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Los productos ya descontados se ignorarán al calcular el valor total del carrito para el descuento escalonado.
    - *Cuando está deshabilitado (NO):* Todos los productos del carrito, independientemente de si ya están descontados, contribuirán al valor del carrito para el descuento escalonado.
  - **Valor recomendado:** SÍ, para evitar "doble descuento" y proteger sus márgenes.
  - **Escenario / ejemplo de comerciante:** Está realizando una venta del 20% de descuento en camisetas específicas. Si un cliente compra una camiseta y otros artículos, y este ajuste es SÍ, el valor de la camiseta no les ayudará a alcanzar el siguiente nivel de descuento del carrito.
- **Excluir productos del fabricante**

  - **Qué hace este ajuste:** Le permite especificar ciertos fabricantes cuyos productos no deben contribuir al valor del carrito al calcular el descuento escalonado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está seleccionado:* Los productos de los fabricantes elegidos se ignorarán al calcular el valor total del carrito para el descuento escalonado.
    - *Cuando no está seleccionado:* Todos los productos, independientemente del fabricante, contribuyen al valor del carrito.
  - **Valor recomendado:** Déjelo vacío a menos que tenga acuerdos específicos o productos de bajo margen de ciertos fabricantes.
  - **Escenario / ejemplo de comerciante:** Vende productos de una marca premium que tiene reglas de precios estrictas y no puede incluirse en descuentos generales. Seleccionaría ese fabricante aquí.
- **Excluir productos con descuento del valor del descuento**

  - **Qué hace este ajuste:** Determina si el *valor* de los productos que ya están descontados debe excluirse del *importe* del descuento de carrito aplicado. Esta es una distinción sutil pero importante de "Excluir productos con descuento".
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Si se aplica un descuento de carrito del 5%, y algunos productos del carrito ya están descontados, el 5% solo se aplicará a los artículos no descontados.
    - *Cuando está deshabilitado (NO):* El descuento de carrito del 5% se aplicará al valor *total* del carrito, incluso si algunos artículos ya están descontados.
  - **Valor recomendado:** SÍ, para proteger los márgenes y evitar descuentos excesivos en artículos ya rebajados.
  - **Escenario / ejemplo de comerciante:** Un cliente tiene un carrito de 100 €, con un artículo de 20 € ya con un 10% de descuento. Si se aplica un descuento de carrito del 5% y este ajuste es SÍ, el 5% solo se aplicará a los 80 € de artículos no descontados.
- **Excluir carrito con código de cupón**

  - **Qué hace este ajuste:** Evita que los descuentos basados en el valor del carrito del módulo se apliquen si un cliente ya ha introducido un código de cupón (vale) separado en su carrito.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Si un cliente utiliza un código de cupón, el descuento automático del carrito del módulo no se aplicará, evitando descuentos acumulados.
    - *Cuando está deshabilitado (NO):* El descuento del módulo se aplicará incluso si hay un código de cupón presente, lo que podría acumular descuentos.
  - **Valor recomendado:** SÍ, para evitar descuentos excesivos y mantener el control sobre sus promociones.
  - **Escenario / ejemplo de comerciante:** Está ejecutando una campaña de correo electrónico especial con un cupón único del 10% de descuento. Quiere que los clientes elijan entre ese cupón o el descuento de carrito escalonado, no ambos.
- **Mostrar información del programa de descuentos en la página del carrito**

  - **Qué hace este ajuste:** Controla si los mensajes sobre el programa de descuentos de carrito (por ejemplo, "¡Gaste X más para un Y% de descuento!") se muestran en la página del carrito de compras.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Aparecerán mensajes informativos en la página del carrito, guiando a los clientes hacia un mayor gasto.
    - *Cuando está deshabilitado (NO):* No se mostrarán mensajes relacionados con los descuentos de este módulo en la página del carrito. El descuento seguirá aplicándose si está activo, pero sin los mensajes promocionales.
  - **Valor recomendado:** SÍ, ya que esta es una característica clave para fomentar un AOV más alto.
  - **Escenario / ejemplo de comerciante:** Quiere animar activamente a los clientes a alcanzar el siguiente nivel de descuento. Habilitar esto les mostrará exactamente cuánto más necesitan gastar.
- **Contenidos personalizados adicionales**

  - **Qué hace este ajuste:** Le permite añadir texto, HTML o incluso imágenes personalizadas que se mostrarán junto con la información del programa de descuentos en la página del carrito. Este contenido se puede traducir a diferentes idiomas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce contenido:* Su mensaje personalizado aparecerá en la página del carrito, mejorando el mensaje promocional.
    - *Cuando se deja vacío:* No se mostrará ningún contenido personalizado adicional.
  - **Valor recomendado:** Utilícelo para añadir una llamada a la acción convincente o explicar los beneficios del programa de descuentos.
  - **Escenario / ejemplo de comerciante:** Podría añadir "¡No se pierda los ahorros! ¡Cuanto más compre, más ahorrará!" o un enlace a sus términos y condiciones para descuentos.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 AdminCdisListController (Back Office > Módulos > Descuento de carrito basado en el valor del carrito > botón "Configurar", luego navegue a la pestaña "Descuentos" o similar)

Esta pantalla es donde define y gestiona sus reglas de descuento reales. Normalmente se accede a ella después de hacer clic en "Configurar" en el módulo y luego navegar a una pestaña o enlace específico para "Descuentos" o "Reglas".

- **Nombre de la pantalla y ubicación del menú:** A esta pantalla se suele acceder a través de una pestaña o enlace dedicado dentro de la página de configuración principal del módulo, a menudo etiquetado como "Descuentos", "Reglas" o "Gestionar descuentos".
- **Acciones y configuraciones disponibles:**
  - **Vista de cuadrícula / gestión:** Verá una tabla que enumera todas sus reglas de descuento definidas. Cada fila representa una regla con columnas como:
    - **Valor mínimo del carrito:** El umbral que debe alcanzar el carrito.
    - **Tipo de descuento:** Si es un porcentaje o una cantidad fija.
    - **Valor del descuento:** El porcentaje (por ejemplo, 5) o la cantidad fija (por ejemplo, 10.00).
    - **Activo:** Si la regla está actualmente habilitada.
    - **Acciones:** Botones para "Editar" o "Eliminar" reglas individuales.
  - **Botón Añadir nueva regla:** Un botón (por ejemplo, "Añadir nueva regla de descuento") para crear una nueva condición de descuento. Al hacer clic, se abrirá un formulario para definir una nueva regla.
  - **Formulario de edición de reglas:** Al añadir o editar una regla, normalmente encontrará campos para:
    - **Valor mínimo del carrito:** (por ejemplo, 500) - El valor total mínimo del carrito para que se aplique este descuento.
    - **Tipo de descuento:** (por ejemplo, Porcentaje, Cantidad fija) - Elija cómo se calcula el descuento.
    - **Valor del descuento:** (por ejemplo, 5 para 5%, o 10.00 para 10 €) - El descuento real a aplicar.
    - **Activo:** (Interruptor Sí/No) - Para habilitar o deshabilitar esta regla específica sin eliminarla.
    - **Prioridad:** (por ejemplo, 1, 2, 3) - Si se pudieran aplicar varias reglas (por ejemplo, el valor del carrito es de 1000 €, y tiene reglas para 500 € y 1000 €), la prioridad determina cuál tiene precedencia. Los números más bajos suelen significar mayor prioridad.
- **Efecto de los cambios:**
  - **Añadir una regla:** Una nueva condición de descuento se activa en su tienda, aplicándose automáticamente a los carritos de los clientes que cumplen los criterios.
  - **Editar una regla:** Modifica una condición de descuento existente, cambiando su umbral, valor o estado activo.
  - **Eliminar una regla:** Elimina permanentemente una condición de descuento, y ya no se aplicará a los carritos.
  - **Activar/Desactivar:** Alterna la disponibilidad de una regla de descuento específica sin eliminar su configuración.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Comience planificando sus niveles de descuento (por ejemplo, 250 € para 2%, 500 € para 5%, 1000 € para 10%).
  2. Haga clic en "Añadir nueva regla de descuento" para cada nivel.
  3. Introduzca el "Valor mínimo del carrito", seleccione "Tipo de descuento" (normalmente Porcentaje) e introduzca el "Valor del descuento".
  4. Asegúrese de que "Activo" esté configurado en SÍ.
  5. Establezca prioridades si tiene rangos superpuestos (por ejemplo, una regla para >500 € y otra para >1000 €, asegúrese de que la regla de 1000 € tenga mayor prioridad si desea que se aplique en lugar de la regla de 500 € cuando el carrito supere los 1000 €). El módulo normalmente lo gestiona aplicando el descuento de mayor valor para el nivel más alto alcanzado.
  6. Revise regularmente sus reglas de descuento, especialmente antes de grandes ventas o períodos promocionales, para asegurarse de que se alinean con su estrategia de marketing actual.

#### 2.2.2 index.php (cartdiscount/controllers/admin/index.php)

Este archivo es un marcador de posición y normalmente contiene solo una declaración de seguridad `die()` para evitar el acceso directo al directorio. No representa una pantalla configurable o una vista de gestión de entidades para el comerciante.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de Configuración del Módulo** | Activar programa | SÍ | Interruptor maestro para todo el programa de descuentos. |
|  | Desactivar programa de descuentos de carrito para grupos de clientes seleccionados | (Ninguno seleccionado) | Excluye a los grupos de clientes elegidos de recibir descuentos. |
|  | Tipo de precio | Precio con impuestos | Determina si el valor del carrito incluye o excluye impuestos para el cálculo. |
|  | Excluir productos con descuento | SÍ | Evita que los productos ya descontados contribuyan al umbral del valor del carrito. |
|  | Excluir productos del fabricante | (Ninguno seleccionado) | Ignora los productos de los fabricantes seleccionados para el cálculo del valor del carrito. |
|  | Excluir productos con descuento del valor del descuento | SÍ | Asegura que el descuento del carrito solo se aplique a los artículos no descontados del carrito. |
|  | Excluir carrito con código de cupón | SÍ | Evita los descuentos del módulo si se utiliza un código de cupón separado. |
|  | Mostrar información del programa de descuentos en la página del carrito | SÍ | Muestra mensajes promocionales en la página del carrito. |
|  | Contenidos personalizados adicionales | (Vacío) | Añade texto/HTML personalizado a la información de descuento de la página del carrito. |
| **AdminCdisListController (Lista de Descuentos)** | Valor mínimo del carrito | (Definido por el comerciante) | El umbral total del carrito para activar un descuento. |
|  | Tipo de descuento | Porcentaje | Cómo se calcula el descuento (porcentaje o cantidad fija). |
|  | Valor del descuento | (Definido por el comerciante) | La cantidad real del descuento (por ejemplo, 5 para 5%, 10.00 para 10 €). |
|  | Activo | SÍ | Habilita o deshabilita una regla de descuento específica. |
|  | Prioridad | (Automático/Definido por el comerciante) | Determina qué regla se aplica si se cumplen varios umbrales. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Mis descuentos no se aplican, aunque he configurado las reglas. ¿Qué pasa?**
R:

1.  **Compruebe "Activar programa":** Asegúrese de que el interruptor principal en la página de configuración del módulo esté configurado en SÍ.
2.  **Compruebe el estado "Activo" de la regla individual:** Asegúrese de que cada regla de descuento que ha creado en el `AdminCdisListController` también esté configurada en SÍ.
3.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). PrestaShop a menudo almacena en caché la configuración del módulo.
4.  **Comprobar grupos de clientes:** Verifique que el grupo de clientes con el que está probando no esté excluido en "Desactivar programa de descuentos de carrito para grupos de clientes seleccionados".
5.  **Umbral de valor del carrito:** Vuelva a comprobar que el valor de su carrito realmente cumple el "Valor mínimo del carrito" para que se active el descuento.

**P: El descuento se aplica, pero el mensaje en la página del carrito no aparece.**
R:

1.  **Compruebe "Mostrar información del programa de descuentos en la página del carrito":** Asegúrese de que esta configuración esté habilitada (SÍ) en la página de configuración principal del módulo.
2.  **Compatibilidad del tema:** Su tema personalizado podría estar anulando la visualización estándar del carrito. Compruebe si el hook `displayShoppingCartFooter` está correctamente implementado en el archivo `shopping-cart.tpl` de su tema o equivalente. Si no, un desarrollador podría necesitar añadir el hook manualmente.
3.  **Borrar caché:** Siempre borre la caché de PrestaShop después de realizar cambios de configuración.

**P: El valor del descuento parece incorrecto, o no se aplica a todos los artículos.**
R:

1.  **"Tipo de precio":** Verifique si ha seleccionado "Precio con impuestos" o "Precio sin impuestos" para el cálculo.
2.  **"Excluir productos con descuento":** Si está habilitado, los productos ya en oferta no contribuirán al umbral.
3.  **"Excluir productos con descuento del valor del descuento":** Si está habilitado, el descuento porcentual solo se aplicará a los artículos no descontados del carrito. Revise estas configuraciones para asegurarse de que coinciden con el comportamiento deseado.
4.  **"Excluir carrito con código de cupón":** Si un cliente ha aplicado un cupón separado, y esta configuración es SÍ, el descuento del módulo no se aplicará.

**P: ¿Cómo traduzco el contenido personalizado que he añadido?**
R:

1.  Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop.
2.  Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione el idioma que desea traducir.
3.  Busque el módulo "Descuento de carrito basado en el valor del carrito". Debería ver campos para traducir los "Contenidos personalizados adicionales" para cada idioma.

**P: Veo un error después de actualizar PrestaShop u otro módulo.**
R:

1.  **Compruebe la versión del módulo:** Asegúrese de que está utilizando la última versión del módulo "Descuento de carrito basado en el valor del carrito" compatible con su versión de PrestaShop. Descargue el ZIP correcto de MyPresta.eu.
2.  **Compatibilidad con PHP:** Verifique que la versión de PHP de su servidor esté dentro del rango compatible con el módulo (PHP 5.6 - 8.5).
3.  **Deshabilitar anulaciones (para desarrolladores):** Si sospecha un conflicto, deshabilite temporalmente las anulaciones en **Parámetros avanzados > Rendimiento** (establezca "Deshabilitar módulos no PrestaShop" en SÍ, luego borre la caché). Si el problema se resuelve, es probable que sea un conflicto de anulación. Vuelva a habilitar y consulte a un desarrollador.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Descuento de carrito basado en el valor del carrito" extiende las funcionalidades principales de `Cart` y `CartRule` de PrestaShop a través de anulaciones para aplicar descuentos dinámicamente. Aprovecha un controlador de administración dedicado (`AdminCdisListController`) para gestionar las reglas de descuento almacenadas en una tabla de base de datos personalizada. La integración con el front-office se logra principalmente a través de hooks para mostrar mensajes informativos y asegurar la aplicación del descuento durante los procesos de carrito y pago.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno definido explícitamente en el directorio `controllers/front/` del módulo. La lógica de front-office para la aplicación de descuentos se maneja a través de anulaciones y hooks.
- **Controladores de Administración (Back-Office)**:

  - `cartdiscount/controllers/admin/AdminCdisList.php`
    - **Nombre de la Clase y Clase Padre:** `AdminCdisListController` extiende `ModuleAdminController`.
    - **Nombre de la Pestaña y Entidad Gestionada:** Gestiona la lista y los formularios para las entidades `Cdis` (Descuento de Carrito). Este controlador proporciona la interfaz para crear, editar y eliminar las reglas de descuento escalonadas. Define la vista de lista (`renderList()`) y la vista de formulario (`renderForm()`) para las reglas de descuento.
  - `cartdiscount/controllers/admin/index.php`
    - **Nombre de la Clase y Clase Padre:** N/A (archivo de seguridad).
    - **Responsabilidad:** Contiene una declaración `die('No direct script access allowed');` para evitar el acceso directo al directorio, una práctica de seguridad estándar de PrestaShop.

### 4.3 Clases y Modelos Principales (`classes/`)

El módulo se basa en gran medida en anulaciones para inyectar su lógica en las clases principales de PrestaShop.

- `cartdiscount/override/classes/Cart.php`
  - **Clase Original:** `Cart`
  - **Responsabilidad:** Esta anulación es crucial. Extiende la clase `Cart` para modificar cómo se calculan los totales del carrito, específicamente para aplicar los descuentos dinámicos basados en las reglas del módulo. Probablemente intercepta métodos como `getProducts()`, `getProductsTotal()` o `getPackageShippingCost()` para ajustar los precios antes de que se finalicen. También contiene lógica para determinar si se debe aplicar un descuento en función del valor actual del carrito y las reglas configuradas.
- `cartdiscount/override/classes/CartRule.php`
  - **Clase Original:** `CartRule`
  - **Responsabilidad:** Esta anulación probablemente extiende la clase `CartRule` para permitir que el módulo cree y gestione sus propios objetos `CartRule` internos dinámicamente. Cuando el módulo aplica un descuento, a menudo se hace creando una `CartRule` temporal o específica que refleja el descuento calculado, que luego se aplica al carrito. Esta anulación garantiza la compatibilidad y el manejo adecuado de estas reglas generadas dinámicamente.
- `cartdiscount/override/classes/index.php`
  - **Responsabilidad:** Archivo de seguridad, `die('No direct script access allowed');`.
- `cartdiscount/override/classes/order/index.php`
  - **Responsabilidad:** Archivo de seguridad, `die('No direct script access allowed');`.
- `cartdiscount/override/classes/order/Order.php`
  - **Clase Original:** `Order`
  - **Responsabilidad:** Esta anulación asegura que los descuentos aplicados por el módulo se transfieran y almacenen correctamente cuando se realiza un pedido. Podría modificar métodos relacionados con la creación de pedidos o el cálculo total para reflejar las reglas de carrito aplicadas.

### 4.4 Activos JavaScript (`views/js/`)

- `cartdiscount/views/admin/js/cdis.js`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Este script probablemente maneja las interacciones del lado del cliente para el `AdminCdisListController`. Esto podría incluir:
    - Llamadas AJAX para guardar/actualizar reglas de descuento.
    - Validación de formularios para el formulario "Añadir/Editar Regla de Descuento".
    - Actualizaciones dinámicas de la interfaz de usuario o interacciones dentro de la cuadrícula de gestión de reglas de descuento.
    - Potencialmente, el manejo de "Excluir productos del fabricante" u otros campos de selección dinámica.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `cartdiscount/views/admin/css/cdis.css`
  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Responsabilidad:** Proporciona un estilo específico para la interfaz de `AdminCdisListController`, asegurando que los formularios y listas de gestión de reglas de descuento estén bien presentados y sean consistentes con la interfaz de usuario del back-office de PrestaShop.
  - **Selectores de clase CSS clave:** Los desarrolladores pueden inspeccionar el HTML generado por `AdminCdisListController` para encontrar clases específicas (por ejemplo, `.cdis-form`, `.cdis-list-table`) para anular si se necesita un estilo de administración personalizado.
- `cartdiscount/views/css/cartdiscount.css`
  - **Alcance:** Estilo del cliente del Front-office.
  - **Responsabilidad:** Estiliza los mensajes informativos que se muestran en la página del carrito (por ejemplo, "¡Gaste X más para un Y% de descuento!").
  - **Selectores de clase CSS clave:** Probablemente apunta a elementos dentro de la plantilla `myDiscount.tpl` (por ejemplo, `.cartdiscount-info`, `.cartdiscount-message`, `.cartdiscount-progress`). Los desarrolladores pueden anular estas clases en el `custom.css` de su tema o equivalente para que coincidan con la marca de la tienda.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - `cartdiscount/views/templates/hook/myDiscount.tpl`
    - **Hook:** `displayShoppingCartFooter` (y potencialmente otros como `displayHeader` para la inclusión de JS/CSS).
    - **Bloque Visual:** Esta plantilla es responsable de renderizar los mensajes dinámicos en la página del carrito de compras. Muestra información sobre el valor actual del carrito, el descuento aplicado y cuánto más necesita gastar el cliente para alcanzar el siguiente nivel de descuento. También renderiza los "Contenidos personalizados adicionales" si están configurados.
- **Plantillas de administración (`views/templates/admin/`)**:
  - El `AdminCdisListController` utilizará plantillas de administración estándar de PrestaShop para renderizar sus vistas de lista y formulario, que normalmente se encuentran en `_partials` o `helpers/list/list_header.tpl`, `helpers/form/form.tpl`, etc., que forman parte del núcleo de PrestaShop. El módulo en sí mismo podría no tener archivos `.tpl` personalizados en `views/templates/admin/`, sino que se basa en el controlador para pasar datos a los ayudantes del núcleo.
- **Plantillas de front-office (`views/templates/front/`)**: Ninguna definida explícitamente.
- `cartdiscount/lib/searchTool/views/scripts.tpl`
  - **Alcance:** Probablemente se utiliza para incluir activos JavaScript o CSS para un componente de herramienta de búsqueda dentro de la configuración del módulo o una característica específica. Su uso exacto dependería de la implementación de la herramienta de búsqueda (por ejemplo, para seleccionar fabricantes a excluir).

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de la Base de Datos**:

  - `ps_cdis`: Esta tabla personalizada almacena las reglas de descuento reales definidas por el comerciante (valor mínimo del carrito, tipo de descuento, valor del descuento, estado activo, prioridad).
  - `ps_configuration`: La configuración del módulo como `CDIS_ACTIVE`, `CDIS_PRICETYPE`, `CDIS_GROUPSNOT`, `CDIS_EXMANUFACTURER`, `CDIS_SHOWINFO_CART`, `CDIS_EXSPECIFIC`, `CDIS_ORDERCOUPON`, `cdis_contents` (para contenido personalizado) y `mypresta_updates` se almacenan aquí.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Se utiliza para incluir el CSS (`cartdiscount.css`) y potencialmente JavaScript del front-office del módulo, asegurando que los estilos y scripts se carguen para la página del carrito. |
| `ActionAdminControllerSetMedia` | Cuando se inicializa un controlador de administración y se están configurando sus medios (JS/CSS). | Se utiliza para incluir el CSS (`cdis.css`) y JavaScript (`cdis.js`) del back-office del módulo para el `AdminCdisListController`, asegurando el estilo y la funcionalidad adecuados de la interfaz de administración. |
| `displayShoppingCartFooter` | En la parte inferior de la página de resumen del carrito de compras. | Renderiza la plantilla `myDiscount.tpl`, mostrando mensajes informativos sobre el programa de descuentos, los ahorros actuales y los próximos niveles de descuento al cliente. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Descuento de carrito basado en el valor del carrito", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.

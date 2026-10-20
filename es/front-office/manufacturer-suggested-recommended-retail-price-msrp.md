---
title: "Precio de venta sugerido/recomendado por el fabricante (MSRP) - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Precio de venta sugerido/recomendado por el fabricante (MSRP)' de MyPresta.eu."
sidebar:
  label: "Precio de venta sugerido/recomendado por el fabricante (MSRP) - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Manufacturer suggested / recommended retail price (MSRP) en MyPresta.eu](https://mypresta.eu/modules/front-office-features/manufacturer-suggested-recommended-retail-price-msrp.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/manufacturer-suggested-recommended-retail-price-msrp/)
>
> ---


# Precio de venta sugerido/recomendado por el fabricante (MSRP)

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo MSRP, accesible después de la instalación haciendo clic en el botón "Configurar". Aquí definirá cómo se muestran y gestionan los MSRP en su tienda.

#### **Habilitar la visualización del MSRP**

- **Qué hace esta configuración:** Este es el interruptor maestro para activar o desactivar la función MSRP para toda su tienda.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado (SÍ):* El módulo comenzará a mostrar la información del MSRP en sus páginas de producto y listados de productos, siempre que haya introducido los MSRP para sus productos.
  - *Cuando está deshabilitado (NO):* La función MSRP estará completamente inactiva y no se mostrará ninguna información del MSRP a los clientes, incluso si ha introducido valores.
- **Valor recomendado:** SÍ (para utilizar las funciones del módulo).
- **Escenario/ejemplo del comerciante:** Si está configurando el módulo por primera vez, habilítelo para ver los cambios. Si necesita ocultar temporalmente los MSRP para una promoción o mantenimiento, puede deshabilitarlo aquí.

#### **Mostrar MSRP en la página del producto**

- **Qué hace esta configuración:** Controla si el MSRP se muestra en las páginas de detalles de productos individuales.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado (SÍ):* El MSRP, su precio y la información de "Usted ahorra" aparecerán en la página del producto.
  - *Cuando está deshabilitado (NO):* El MSRP no se mostrará en la página del producto, incluso si está habilitado globalmente.
- **Valor recomendado:** SÍ (Esta es una ubicación principal para que los clientes vean el valor).
- **Escenario/ejemplo del comerciante:** Podría deshabilitar esto si prefiere resaltar los ahorros solo en las páginas de categorías, o si el diseño de su página de producto ya está muy saturado.

#### **Mostrar MSRP en la lista de productos**

- **Qué hace esta configuración:** Controla si el MSRP se muestra en las páginas que muestran varios productos, como páginas de categorías, resultados de búsqueda o bloques de productos destacados.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado (SÍ):* El MSRP, su precio y la información de "Usted ahorra" aparecerán para cada producto en los listados de productos.
  - *Cuando está deshabilitado (NO):* El MSRP no se mostrará en las páginas de listado de productos.
- **Valor recomendado:** SÍ (Ideal para comparaciones rápidas y para resaltar el valor mientras se navega).
- **Escenario/ejemplo del comerciante:** Habilitar esto ayuda a los clientes a identificar rápidamente buenas ofertas mientras navegan por las categorías, lo que potencialmente aumenta las tasas de clics a las páginas de productos.

#### **Mostrar precio con impuestos incluidos**

- **Qué hace esta configuración:** Determina si el MSRP mostrado debe incluir impuestos o mostrarse como exento de impuestos.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado (SÍ):* El MSRP se mostrará con los impuestos aplicables ya añadidos, reflejando el precio final que pagaría un cliente.
  - *Cuando está deshabilitado (NO):* El MSRP se mostrará sin impuestos.
- **Valor recomendado:** SÍ (Generalmente, los clientes prefieren ver los precios finales, especialmente en contextos B2C).
- **Escenario/ejemplo del comerciante:** Si su tienda atiende principalmente a clientes B2C, mostrar los precios con impuestos incluidos es más claro. Para tiendas B2B, podría preferirse el precio sin impuestos.

#### **Mostrar precio sin impuestos**

- **Qué hace esta configuración:** Determina si el MSRP mostrado debe excluir impuestos o mostrarse con impuestos incluidos.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado (SÍ):* El MSRP se mostrará sin impuestos.
  - *Cuando está deshabilitado (NO):* El MSRP se mostrará con los impuestos aplicables ya añadidos.
- **Valor recomendado:** NO (A menos que se dirija específicamente a clientes B2B u opere en una región donde los precios sin impuestos son estándar para la visualización inicial).
- **Escenario/ejemplo del comerciante:** Si habilita "Mostrar precio con impuestos incluidos", normalmente deshabilitaría este para evitar confusiones. Solo habilite ambos si desea mostrar ambos valores uno al lado del otro (lo que podría ser confuso para los clientes).

#### **Mostrar información de "Usted ahorra"**

- **Qué hace esta configuración:** Controla si el módulo calcula y muestra la diferencia monetaria entre el MSRP y el precio de venta de su tienda.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado (SÍ):* El módulo mostrará un mensaje como "Usted ahorra $X.XX" o "Usted ahorra X%" junto al MSRP y su precio.
  - *Cuando está deshabilitado (NO):* Solo se mostrarán el MSRP y su precio, sin el cálculo explícito de los ahorros.
- **Valor recomendado:** SÍ (Este es un beneficio clave del uso del módulo, que motiva fuertemente las compras).
- **Escenario/ejemplo del comerciante:** Esta función resalta directamente la propuesta de valor. Si sus precios son consistentemente más bajos que el MSRP, habilitar esto aumentará significativamente el valor percibido.

#### **Campo MSRP para productos**

- **Qué hace esta configuración:** Esta configuración define dónde introducirá el MSRP para cada producto en su Back Office de PrestaShop.
- **Efecto de cambiar esta configuración:**
  - *Cuando se selecciona:* El módulo utilizará el campo de producto elegido para recuperar el valor del MSRP. Deberá introducir manualmente el MSRP para cada producto en el campo especificado.
- **Valor recomendado:** El módulo suele crear un campo personalizado o sugiere utilizar uno existente. Siga las instrucciones del módulo para identificar el campo correcto.
- **Escenario/ejemplo del comerciante:** Después de instalar el módulo, vaya a **Catálogo > Productos**, edite un producto y encontrará un nuevo campo de entrada (o uno existente reutilizado) donde puede escribir el MSRP para ese producto específico.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar visualización de MSRP | SÍ | Interruptor maestro para activar/desactivar la función MSRP en toda la tienda. |
| Configuración del módulo | Mostrar MSRP en la página del producto | SÍ | Mostrar MSRP en las páginas de detalles de productos individuales. |
| Configuración del módulo | Mostrar MSRP en la lista de productos | SÍ | Mostrar MSRP en las páginas de categorías/resultados de búsqueda. |
| Configuración del módulo | Mostrar precio con impuestos incluidos | SÍ | Mostrar MSRP con impuestos incluidos (compatible con B2C). |
| Configuración del módulo | Mostrar precio sin impuestos | NO | Mostrar MSRP sin impuestos (compatible con B2B, evitar conflicto con 'Impuestos incluidos'). |
| Configuración del módulo | Mostrar información de "Usted ahorra" | SÍ | Mostrar los ahorros calculados (MSRP - Su precio). |
| Configuración del módulo | Campo MSRP para productos | (Específico del módulo) | Define qué campo de producto en el BO almacena el valor del MSRP. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He habilitado el módulo y he introducido los MSRP, pero no aparece nada en mi tienda. ¿Qué pasa?**
R1:

- **Verificar habilitación global:** Asegúrese de que "Habilitar visualización de MSRP" esté configurado en SÍ en la configuración del módulo.
- **Verificar configuraciones de visualización específicas:** Verifique que "Mostrar MSRP en la página del producto" y "Mostrar MSRP en la lista de productos" también estén configurados en SÍ para las áreas donde espera verlo.
- **Borrar caché:** PrestaShop utiliza caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
- **MSRP específico del producto:** Verifique que realmente haya introducido un valor de MSRP para los productos específicos que está probando.
- **Compatibilidad del tema:** A veces, los temas altamente personalizados pueden requerir pequeños ajustes para mostrar nuevos elementos. Si después de borrar la caché aún no aparece, póngase en contacto con el soporte de MyPresta.eu.

**P2: La cantidad de "Usted ahorra" parece incorrecta o no aparece.**
R2:

- **Habilitar "Usted ahorra":** Asegúrese de que "Mostrar información de 'Usted ahorra'" esté habilitado en la configuración del módulo.
- **MSRP vs. Su precio:** El cálculo de "Usted ahorra" depende tanto del MSRP como del precio de venta de su producto. Asegúrese de que ambos valores estén configurados correctamente para el producto. Si su precio de venta es mayor o igual que el MSRP, no se mostrarán ahorros.
- **Configuración de impuestos:** El cálculo podría verse afectado por si está mostrando precios con impuestos incluidos o excluidos. Asegúrese de que su configuración de impuestos sea consistente.

**P3: ¿Cómo introduzco el MSRP para cada producto?**
R3: Después de instalar el módulo, navegue a **Catálogo > Productos** en su Back Office de PrestaShop. Edite un producto existente o cree uno nuevo. Dentro de la interfaz de edición del producto, debería encontrar un nuevo campo específicamente para "MSRP" (o un campo existente reutilizado, según lo definido en la configuración del módulo). Introduzca el precio de venta sugerido por el fabricante allí y guarde el producto.

**P4: El texto del MSRP no coincide con el diseño/fuente de mi tienda. ¿Cómo puedo cambiarlo?**
R4: El módulo utiliza su propio CSS para el estilo. Para ajustes menores (como el tamaño de la fuente, el color), a menudo puede anular estos estilos en el archivo CSS personalizado de su tema (por ejemplo, `themes/yourtheme/assets/css/custom.css` o `themes/yourtheme/css/custom.css`). Para cambios más extensos, es posible que necesite un desarrollador web para inspeccionar el CSS del módulo y aplicar anulaciones más específicas.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Precio de venta sugerido/recomendado por el fabricante (MSRP)" es un módulo estándar de PrestaShop diseñado para extender las funcionalidades de visualización de productos en el front-office. Opera principalmente enganchándose a los puntos de visualización existentes de PrestaShop (como páginas de productos y listados de productos) para inyectar información de MSRP. Aprovecha el sistema de configuración de PrestaShop para sus ajustes y las plantillas Smarty para renderizar la salida del front-office. La lógica central del módulo reside en su archivo PHP principal, que maneja la instalación, desinstalación, configuración y registro de hooks.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores de administración de Front-Office o Back-Office personalizados. Toda la configuración se maneja a través del método `getContent()` en el archivo principal del módulo, y la visualización del front-office se gestiona a través de hooks y la renderización de plantillas.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada o instancias de `ObjectModel` en el directorio `classes/`. Interactúa directamente con los datos de productos y la configuración existentes de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)

- **`msrp/views/admin/js/msrp.js`**

  - **Alcance:** Back-office.
  - **Propósito:** Este script probablemente maneja cualquier comportamiento dinámico o validación dentro del formulario de configuración del módulo en el Back Office de PrestaShop. Esto podría incluir mostrar/ocultar campos basados en otras selecciones, llamadas AJAX para guardar configuraciones o validación del lado del cliente.
  - **Detalles:** Vincula oyentes de eventos a los elementos del formulario de configuración, realiza el manejo del envío del formulario y, potencialmente, actualiza la interfaz de usuario según la entrada del usuario.
- **`msrp/views/js/msrp.js`**

  - **Alcance:** Front-office.
  - **Propósito:** Este script es responsable de cualquier interacción del lado del cliente o actualizaciones dinámicas relacionadas con la visualización del MSRP en el front-office. Esto podría implicar actualizar la cantidad de "Usted ahorra" dinámicamente si los atributos del producto cambian (por ejemplo, seleccionar un tamaño/color diferente que afecte el precio) o manejar la lógica de visualización.
  - **Detalles:** Se vincula a eventos `prestashop.on` (por ejemplo, `updatedProduct` para cambios de precio en la página del producto), manipula elementos DOM para actualizar la visualización del MSRP o los ahorros, y garantiza la capacidad de respuesta.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`msrp/views/admin/css/msrp.css`**

  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Propósito:** Proporciona un estilo específico para la página de configuración del módulo dentro del Back Office de PrestaShop, asegurando una interfaz consistente y fácil de usar.
  - **Selectores clave:** Dirige elementos dentro de la salida `getContent()` del módulo, como campos de formulario, etiquetas y secciones.
- **`msrp/views/css/msrp.css`**

  - **Alcance:** Estilo del cliente del Front-office.
  - **Propósito:** Estiliza el MSRP mostrado, su precio y la información de "Usted ahorra" en las páginas de productos y listados de productos. Esto asegura que la información sea claramente visible y se integre bien con el diseño general de la tienda.
  - **Selectores clave:** Dirige elementos `div` o `span` específicos generados por las plantillas Smarty del módulo (por ejemplo, `.msrp-price`, `.msrp-you-save`, `.msrp-old-price`). Los desarrolladores pueden anular estas clases en el `custom.css` de su tema para que coincidan con su marca.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`msrp/views/admin/msrp.tpl`**

  - **Alcance:** Plantillas de administración.
  - **Propósito:** Esta plantilla renderiza el formulario de configuración del módulo en el Back Office de PrestaShop. Contiene la estructura HTML para todos los ajustes descritos en la Sección 4.1.
  - **Detalles:** Utiliza los componentes de formulario de ayuda de PrestaShop (por ejemplo, `helperForm`) para crear campos de entrada, interruptores y botones para la configuración del módulo.
- **`msrp/views/templates/msrp-product-list.tpl`**

  - **Alcance:** Plantillas de hook (por ejemplo, `displayProductPriceBlock` o similar para listados de productos).
  - **Propósito:** Esta plantilla es responsable de mostrar la información del MSRP en las páginas de listado de productos (categorías, resultados de búsqueda, etc.). Normalmente recibe datos de productos y configuraciones del módulo para renderizar el MSRP, el precio actual y el mensaje de "Usted ahorra".
  - **Detalles:** Contiene lógica para verificar si el MSRP está disponible, si se debe mostrar "Usted ahorra" y formatea los precios de acuerdo con la configuración de impuestos.
- **`msrp/views/templates/msrp-product-page.tpl`**

  - **Alcance:** Plantillas de hook (por ejemplo, `displayProductPriceBlock` o `displayProductButtons` en las páginas de productos).
  - **Propósito:** Esta plantilla renderiza la información del MSRP en las páginas de detalles de productos individuales. Está diseñada para integrarse sin problemas cerca del bloque de precio principal del producto.
  - **Detalles:** Similar a `msrp-product-list.tpl`, maneja la visualización condicional del MSRP, el precio actual y los ahorros, aplicando reglas de impuestos y formato.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo no crea tablas SQL personalizadas.
  - La configuración se almacena en la tabla `ps_configuration`, típicamente con claves prefijadas por `MSRP_` (por ejemplo, `MSRP_ENABLE`, `MSRP_DISPLAY_PRODUCT_PAGE`).
  - Los valores de MSRP para los productos se almacenan en un campo de producto existente, según lo configurado en el módulo (por ejemplo, `ps_product_lang.description_short` o un campo de producto personalizado si lo crea el módulo).
- **Tabla de Hooks registrados**:
  El módulo registra hooks para inyectar su contenido en el front office y gestionar su ciclo de vida.

  | Nombre del Hook | Momento de ejecución | Propósito técnico |
  | --- | --- | --- |
  | `install()` | Durante la instalación del módulo | Crea entradas de configuración, registra hooks, potencialmente añade campos de producto. |
  | `uninstall()` | Durante la desinstalación del módulo | Limpia entradas de configuración, desregistra hooks, elimina campos de producto. |
  | `displayHeader` | En la sección `<head>` de cada página | Inyecta los archivos CSS y JS del módulo para la visualización en el front-office. |
  | `displayProductPriceBlock` | Dentro del bloque de precio del producto en páginas de productos y listados | Hook principal para renderizar el MSRP, el precio actual y la información de "Usted ahorra". Este hook se llama varias veces con diferentes parámetros (por ejemplo, `type='after_price'`). |
  | `actionProductUpdate` | Después de que un producto se actualiza en el Back Office | Potencialmente utilizado para asegurar que los datos del MSRP se guarden o procesen correctamente. |
  | `actionProductSave` | Después de que un producto se guarda en el Back Office | Similar a `actionProductUpdate`, asegura la integridad de los datos del MSRP. |
  | `actionProductDelete` | Después de que un producto se elimina | Limpia cualquier dato de MSRP asociado si se almacena por separado. |
  | `displayAdminProductsExtra` | En la página de edición de productos en el Back Office | Añade el campo de entrada del MSRP al formulario del producto. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y cualquier otra asistencia con el módulo "Precio de venta sugerido/recomendado por el fabricante (MSRP)", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte y desarrolladores están listos para ayudarle a maximizar el potencial de este módulo para su tienda PrestaShop.

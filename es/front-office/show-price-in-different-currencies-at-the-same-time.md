---
title: "Mostrar precio en diferentes monedas al mismo tiempo - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Mostrar precio en diferentes monedas al mismo tiempo' de MyPresta.eu."
sidebar:
  label: "Mostrar precio en diferentes monedas al mismo tiempo - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Show price in different currencies at the same time en MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-price-in-different-currencies-at-the-same-time.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/show-price-in-different-currencies-at-the-same-time/)
>
> ---


# Mostrar precio en diferentes monedas al mismo tiempo

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una instalación de PrestaShop y son suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Mostrar precio en diferentes monedas al mismo tiempo". Puede acceder a ella navegando a **Módulos > Gestor de módulos** y haciendo clic en "Configurar" junto al nombre del módulo.

La página de configuración presentará una serie de opciones para controlar cómo y dónde se muestran los precios en varias monedas.

#### Configuración general

- **Activar la visualización de precios en varias monedas:**

  - **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar la funcionalidad principal del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El módulo comenzará a mostrar los precios en varias monedas según sus otras configuraciones.
    - *Cuando está desactivado:* El módulo dejará de funcionar y solo se mostrará el precio en la moneda principal.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Si está configurando el módulo por primera vez o realizando mantenimiento, podría desactivarlo temporalmente. Para un funcionamiento normal, siempre debe estar activado.
- **Seleccionar monedas a mostrar:**

  - **Qué hace este ajuste:** Esto le permite elegir qué monedas adicionales, además de la principal, desea mostrar los precios. Normalmente verá una lista de todas las monedas activas en su tienda PrestaShop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está seleccionado:* Los precios se mostrarán en las monedas elegidas.
    - *Cuando no está seleccionado:* Los precios no se mostrarán en esa moneda específica.
  - **Valor recomendado:** Seleccione todas las monedas relevantes para sus mercados internacionales objetivo.
  - **Escenario / ejemplo de comerciante:** Si vende a clientes de la Eurozona, EE. UU. y Reino Unido, seleccionaría EUR, USD y GBP.
- **Mostrar en las páginas de listado de productos (categorías, resultados de búsqueda, etc.):**

  - **Qué hace este ajuste:** Controla si los precios en varias monedas aparecen en las páginas que listan varios productos (por ejemplo, páginas de categorías, resultados de búsqueda, páginas de fabricantes).
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los precios en varias monedas serán visibles debajo del precio principal en las tarjetas de producto.
    - *Cuando está desactivado:* Los precios en varias monedas solo aparecerán en la página de detalles del producto individual.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** La activación de esta opción proporciona una claridad de precios inmediata mientras los clientes navegan, ayudándoles a comparar rápidamente los productos en su moneda preferida.
- **Mostrar en la página de detalles del producto:**

  - **Qué hace este ajuste:** Controla si los precios en varias monedas aparecen en la página de producto individual.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los precios en varias monedas serán visibles cerca del precio principal en la página del producto.
    - *Cuando está desactivado:* Los precios en varias monedas no se mostrarán en la página del producto.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Esto es crucial para los clientes que toman una decisión final, especialmente al considerar combinaciones de productos o descuentos por cantidad, ya que el módulo garantiza que estos precios dinámicos también se conviertan.
- **Formato de visualización de precios:**

  - **Qué hace este ajuste:** Define cómo se formatean los precios de las monedas adicionales (por ejemplo, con o sin símbolo de moneda, número de decimales). Esto suele aprovechar el formato de moneda nativo de PrestaShop.
  - **Efecto de cambiar este ajuste:** Cambia la presentación visual de los precios convertidos.
  - **Valor recomendado:** Utilice un formato que sea claro y consistente con los estándares internacionales para cada moneda (por ejemplo, "$100.00 USD" o "€100,00").
  - **Escenario / ejemplo de comerciante:** Podría optar por mostrar "USD 100.00" en lugar de "$100.00" para evitar confusiones con otras monedas denominadas en dólares.
- **Posición de los precios adicionales:**

  - **Qué hace este ajuste:** Determina dónde se colocan los precios de las monedas adicionales en relación con el precio principal del producto. Las opciones pueden incluir "Debajo del precio principal", "Junto al precio principal" o "En un bloque separado".
  - **Efecto de cambiar este ajuste:** Altera el diseño visual de los precios en sus páginas de productos.
  - **Valor recomendado:** "Debajo del precio principal" suele ser el más claro y menos intrusivo.
  - **Escenario / ejemplo de comerciante:** Si el diseño de su página de producto es muy compacto, colocar los precios debajo podría ser mejor que al lado, para evitar aglomeraciones.
- **Actualizar precios con combinaciones/descuentos por cantidad:**

  - **Qué hace este ajuste:** Asegura que cuando un cliente selecciona una combinación de producto diferente (por ejemplo, un tamaño más grande con un precio diferente) o cambia la cantidad (activando un descuento por cantidad), los precios en varias monedas mostrados se actualizan dinámicamente para reflejar el nuevo total.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El módulo utilizará JavaScript para recalcular y mostrar los precios convertidos correctos en tiempo real.
    - *Cuando está desactivado:* Los precios adicionales podrían no actualizarse, lo que llevaría a información incorrecta para el cliente.
  - **Valor recomendado:** SÍ (Crucial para la precisión y la confianza del cliente).
  - **Escenario / ejemplo de comerciante:** Un cliente selecciona una camiseta "Grande" (que cuesta más) o añade 10 artículos (activando un descuento por volumen). Este ajuste garantiza que vea el precio convertido correcto para la camiseta grande o el precio con descuento por volumen en las monedas elegidas.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Activar la visualización de precios en varias monedas | SÍ | Activa/desactiva la funcionalidad principal del módulo. |
| Configuración del módulo | Seleccionar monedas a mostrar | Seleccionar monedas relevantes | Determina qué monedas adicionales se muestran. |
| Configuración del módulo | Mostrar en las páginas de listado de productos | SÍ | Muestra precios en varias monedas en páginas de categoría, búsqueda, etc. |
| Configuración del módulo | Mostrar en la página de detalles del producto | SÍ | Muestra precios en varias monedas en páginas de productos individuales. |
| Configuración del módulo | Formato de visualización de precios | Varía (usar valores predeterminados de PrestaShop) | Controla el formato visual de los precios convertidos. |
| Configuración del módulo | Posición de los precios adicionales | Debajo del precio principal | Establece el diseño de los precios adicionales en relación con el precio principal. |
| Configuración del módulo | Actualizar precios con combinaciones/descuentos por cantidad | SÍ | Asegura actualizaciones dinámicas de precios para combinaciones y descuentos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Los precios en varias monedas no aparecen en mi tienda.**
**R1:**

- **Comprobar el estado del módulo:** Primero, asegúrese de que la opción "Activar la visualización de precios en varias monedas" esté configurada en SÍ en la configuración del módulo.
- **Monedas seleccionadas:** Verifique que haya seleccionado las monedas específicas que desea mostrar en la configuración del módulo.
- **Caché:** Borre la caché de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché) y la caché de su navegador. A veces, el contenido antiguo en caché impide la visualización de nuevos módulos.
- **Compatibilidad del tema:** Si está utilizando un tema altamente personalizado, podría haber un conflicto. Póngase en contacto con el soporte de MyPresta.eu con los detalles de su tema.

**P2: Los precios en otras monedas son incorrectos o no se actualizan.**
**R2:**

- **Tipos de cambio:** Asegúrese de que los tipos de cambio de PrestaShop estén actualizados. Vaya a **Internacional > Monedas** en su Back Office y compruebe los tipos de cambio de cada moneda. Normalmente puede actualizarlos automáticamente o manualmente.
- **Configuración de actualización dinámica:** Asegúrese de que "Actualizar precios con combinaciones/descuentos por cantidad" esté activado en la configuración del módulo si espera que los precios cambien con las opciones del producto.
- **Caché:** Borre todas las cachés (PrestaShop y navegador) después de actualizar los tipos de cambio.

**P3: Los precios en varias monedas se ven extraños o no tienen el estilo correcto en mi tema.**
**R3:**

- **Configuración del módulo:** Compruebe los ajustes "Formato de visualización de precios" y "Posición de los precios adicionales" en el módulo.
- **CSS del tema:** El CSS de su tema personalizado podría estar anulando el estilo predeterminado del módulo. Esto suele requerir que un webmaster o desarrollador inspeccione el CSS. A menudo puede añadir CSS personalizado a su tema para ajustar la apariencia.
- **Póngase en contacto con el soporte:** Si no puede resolver los problemas de estilo, proporcione capturas de pantalla y la URL de su tienda al soporte de MyPresta.eu para obtener ayuda.

**P4: ¿Este módulo ralentizará mi tienda?**
**R4:** El módulo está diseñado para ser ligero. Principalmente obtiene los tipos de cambio existentes y realiza cálculos simples. Las actualizaciones dinámicas para las combinaciones utilizan JavaScript, que se ejecuta en el lado del cliente. En la mayoría de los casos, cualquier impacto en el rendimiento debería ser insignificante. Asegúrese de que su servidor cumpla con los requisitos mínimos de PrestaShop para un rendimiento óptimo.

**Q5: ¿Cómo traduzco el texto del módulo (por ejemplo, "Precio en USD")?**
**A5:** Puede traducir cualquier cadena de texto añadida por el módulo a través de la interfaz de traducción de PrestaShop:

- Navegue a **Internacional > Traducciones**.
- Seleccione "Traducciones de módulos instalados".
- Elija su tema, su idioma y luego seleccione el módulo "Mostrar precio en diferentes monedas al mismo tiempo".
- A continuación, puede editar las traducciones de cualquier frase que introduzca el módulo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la arquitectura técnica del módulo "Mostrar precio en diferentes monedas al mismo tiempo", destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Visión general de la arquitectura

El módulo `multiprice` (nombre interno `ajax_multiprice`) es un módulo estándar de PrestaShop centrado principalmente en la visualización en el front-office. Aprovecha el sistema de hooks de PrestaShop para inyectar información de precios en varias monedas en los listados de productos y en las páginas de detalles del producto. La lógica central reside en el archivo principal del módulo, que gestiona la configuración y el registro de hooks. Se utiliza JavaScript del lado del cliente para las actualizaciones dinámicas de los precios cuando cambian las combinaciones o cantidades de productos, lo que garantiza la precisión en tiempo real sin recargas completas de la página. No introduce tablas de base de datos personalizadas ni ObjectModels complejos, sino que se basa en los mecanismos de precios de productos y monedas existentes de PrestaShop.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores de administración de Front-Office o Back-Office personalizados. Toda la configuración se gestiona a través del método `getContent()` en el archivo principal del módulo, y las interacciones del front-office se gestionan a través de hooks y JavaScript del lado del cliente.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define ninguna clase u ObjectModels personalizados en el directorio `classes/`. Su lógica está encapsulada dentro del archivo principal del módulo `ajax_multiprice.php`.

### 4.4 Activos de JavaScript (`views/js/`)

- **`multiprice/lib/searchTool/views/js/autocomplete.js`**

  - **Ámbito:** Potencialmente Front-office (si se utiliza para una función de búsqueda dentro del módulo, aunque no está directamente relacionado con la visualización principal de precios múltiples).
  - **Responsabilidad:** Este archivo parece ser parte de una biblioteca genérica de herramientas de búsqueda de autocompletado incluida con el módulo. Normalmente manejaría las solicitudes AJAX para sugerencias de búsqueda, se vincularía a los campos de entrada y mostraría los resultados. Su relevancia directa para la visualización de precios en varias monedas es probablemente mínima, a menos que el módulo integre una función de búsqueda que también muestre precios.
  - **Detalles:** Se vincula a los campos de entrada, escucha los eventos `keyup`, realiza llamadas AJAX a un endpoint de backend (no definido en los controladores de este módulo, probablemente un controlador de búsqueda genérico de PrestaShop o un controlador de una herramienta de búsqueda incluida) y manipula el DOM para mostrar una lista desplegable de sugerencias.
- **`multiprice/views/js/multiprice.js`**

  - **Ámbito:** Front-office.
  - **Responsabilidad:** Este es el archivo JavaScript principal para la visualización de precios en varias monedas. Es responsable de actualizar dinámicamente los precios mostrados cuando los atributos del producto (combinaciones) o las cantidades cambian en la página del producto.
  - **Detalles:**
    - Escucha los eventos `change` en los selectores de combinación de productos (por ejemplo, elementos `select` para atributos, botones de radio).
    - Escucha los eventos `change` o `blur` en el campo de entrada de cantidad.
    - Se conecta al evento nativo de PrestaShop `prestashop.on('updatedProduct', ...)` (para PS 1.7+), que se activa cuando los datos del producto (incluido el precio) se actualizan después de la selección de la combinación.
    - Recupera el nuevo precio base de los datos del producto actualizados.
    - Realiza cálculos del lado del cliente para convertir el nuevo precio base a las monedas adicionales configuradas, utilizando tipos de cambio potencialmente pasados desde el backend o almacenados en una variable JS global.
    - Actualiza los elementos del DOM (`<span>`, `<div>`) donde se muestran los precios de las monedas adicionales.
    - Asegura el formato adecuado de los precios convertidos (símbolo de moneda, decimales).

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`multiprice/lib/searchTool/views/css/autocomplete.css`**

  - **Ámbito:** Front-office.
  - **Responsabilidad:** Estiliza el menú desplegable de resultados de búsqueda de autocompletado, incluidas las sugerencias, el resaltado y el diseño general.
  - **Selectores de clase CSS clave:** Probablemente apunta a clases como `.autocomplete-results`, `.autocomplete-item`, `.highlighted`. Los desarrolladores pueden anularlos en el `custom.css` o `theme.css` de su tema.
- **`multiprice/views/css/multiprice.css`**

  - **Ámbito:** Estilo del cliente del Front-office.
  - **Responsabilidad:** Proporciona el estilo predeterminado para los bloques de visualización de precios en varias monedas. Esto incluye tamaños de fuente, colores, márgenes y, potencialmente, el diseño (por ejemplo, apilar los precios verticalmente).
  - **Selectores de clase CSS clave:** Apuntará a clases específicas añadidas por las plantillas del módulo (por ejemplo, `.multiprice-container`, `.multiprice-currency-item`, `.multiprice-price`). Los desarrolladores pueden anular estos selectores en el CSS de su tema para que coincidan con el diseño de su tienda.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **`multiprice/lib/searchTool/views/scripts.tpl`**

  - **Ámbito:** Front-office.
  - **Propósito:** Esta plantilla probablemente incluye el JavaScript y el CSS para la funcionalidad `autocomplete.js`. Se engancharía a `displayHeader` o `displayFooter` para asegurar que se carguen los activos necesarios.
- **`multiprice/views/templates/multiprice-custom.tpl`**

  - **Ámbito:** Front-office (plantilla de hook).
  - **Propósito:** Esta plantilla es probablemente una plantilla de reserva o alternativa para mostrar los precios en varias monedas, posiblemente para hooks específicos o ubicaciones personalizadas. Contendría la estructura HTML para renderizar el precio principal y luego iteraría a través de las monedas adicionales para mostrar sus precios convertidos.
- **`multiprice/views/templates/multiprice.tpl`**

  - **Ámbito:** Front-office (plantilla de hook).
  - **Propósito:** Esta es la plantilla principal responsable de renderizar el bloque de precios en varias monedas. Se inyecta en los elementos de la lista de productos y en la página de detalles del producto a través de los hooks de PrestaShop. Recibe una matriz de monedas y sus precios convertidos y los formatea de acuerdo con la configuración del módulo.
  - **Variables:** Espera variables como `$product_price`, `$additional_currencies` (una matriz de objetos de moneda con precios convertidos), `$currency_format`, etc.
- **`multiprice/views/templates/selectedProducts.tpl`**

  - **Ámbito:** Front-office.
  - **Propósito:** El nombre de esta plantilla sugiere que podría usarse en un contexto donde se muestra una lista de productos seleccionados, potencialmente en un resumen del carrito, una página de comparación o un widget de selección de productos personalizado. Iteraría sobre una colección de productos y mostraría sus precios, potencialmente con la función de varias monedas.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo no crea ninguna tabla SQL personalizada.
  - Almacena sus ajustes de configuración (por ejemplo, estado activado, monedas seleccionadas, opciones de visualización) en la tabla `ps_configuration`, utilizando claves con el prefijo `MULTIPRICE_` o similar.
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Para incluir `multiprice.js` y `multiprice.css` (y potencialmente activos de `autocomplete`) en las páginas del front-office. |
| `displayProductPriceBlock` (tipo `after_price`) | Después del bloque de precio principal en las páginas de productos. | Para inyectar el contenido de `multiprice.tpl` o `multiprice-custom.tpl` que muestra precios de monedas adicionales en la página de detalles del producto. |
| `displayProductListReviews` (o similar para la lista de productos) | Dentro de los elementos de la lista de productos (por ejemplo, páginas de categorías). | Para inyectar el contenido de `multiprice.tpl` o `multiprice-custom.tpl` que muestra precios de monedas adicionales debajo del precio principal en las páginas de listado de productos. El hook exacto puede variar según la versión de PrestaShop y la estructura del tema (por ejemplo, `displayProductPriceBlock` también se puede usar aquí, o un hook personalizado proporcionado por el tema). |
| `actionProductUpdate` (o similar) | Después de que un producto se actualiza en el back office. | (Menos probable para este módulo) Podría usarse para borrar la caché relacionada con los precios de los productos, aunque no es estrictamente necesario para su función principal. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su contenido. | Para registrar archivos JavaScript y CSS para el front office, asegurando que se carguen correctamente. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y cualquier consulta relacionada con el módulo "Mostrar precio en diferentes monedas al mismo tiempo", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con la instalación, configuración y cualquier problema que pueda encontrar.

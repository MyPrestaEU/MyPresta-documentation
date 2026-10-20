---
title: "Acceso a productos por país - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Acceso a productos por país' de MyPresta.eu."
sidebar:
  label: "Acceso a productos por país - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Access to products by country en MyPresta.eu](https://mypresta.eu/modules/ordering-process/access-to-products-by-country.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/access-to-products-by-country/)
>
> ---


# Acceso a productos por país

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo "Acceso a productos por país". Aquí encontrará todos los ajustes para definir cómo se restringe el acceso a los productos.

#### Ajustes generales

- **Activado / Desactivado (Estado del módulo)**

  - **Qué hace este ajuste:** Este es el interruptor principal del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está Activado:* El módulo filtrará activamente los productos basándose en las restricciones por país.
    - *Cuando está Desactivado:* El módulo estará inactivo y todos los productos serán visibles para todos los clientes, independientemente de su país.
  - **Valor recomendado:** **Activado** una vez que haya configurado sus reglas.
  - **Escenario / ejemplo de comerciante:** Está configurando el módulo por primera vez; manténgalo desactivado hasta que haya definido todas sus reglas, luego actívelo para ponerlo en marcha.
- **¿Qué desea hacer? (Tipo de restricción)**

  - **Qué hace este ajuste:** Define la lógica central de sus restricciones por país: ¿desea *bloquear* productos en países seleccionados o *permitir* productos *solo* en países seleccionados?
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "Bloquear acceso a productos en países seleccionados":* Los productos que configure se ocultarán a los clientes de los países que especifique. Serán visibles en cualquier otro lugar.
    - *Cuando se establece en "Permitir acceso a productos SÓLO en países seleccionados":* Los productos que configure *solo* serán visibles para los clientes de los países que especifique. Se ocultarán en cualquier otro lugar.
  - **Valor recomendado:** Elija según su caso de uso principal. Si tiene algunos países donde un producto está restringido, elija "Bloquear". Si un producto es exclusivo de unos pocos países, elija "Permitir SÓLO".
  - **Escenario / ejemplo de comerciante:**
    - *Bloquear:* Vende una marca específica que no se puede enviar a Canadá. Seleccionaría "Bloquear acceso" y luego elegiría Canadá para ese producto.
    - *Permitir SÓLO:* Tiene un producto de edición especial solo disponible para la venta en EE. UU. y México. Seleccionaría "Permitir acceso SÓLO" y luego elegiría EE. UU. y México para ese producto.
- **Seleccionar países**

  - **Qué hace este ajuste:** Aquí es donde selecciona los países específicos que se verán afectados por la regla "¿Qué desea hacer?".
  - **Efecto de cambiar este ajuste:** Los países seleccionados serán bloqueados para ver el producto o serán los únicos a los que se les permitirá verlo, dependiendo del ajuste "¿Qué desea hacer?".
  - **Valor recomendado:** Seleccione todos los países relevantes según sus restricciones de productos.
  - **Escenario / ejemplo de comerciante:** Si está bloqueando las ventas a Canadá y Australia, seleccionaría tanto Canadá como Australia de la lista.
- **Seleccionar categorías**

  - **Qué hace este ajuste:** Le permite aplicar las reglas de restricción por país a categorías de productos enteras en lugar de a productos individuales.
  - **Efecto de cambiar este ajuste:** Todos los productos dentro de las categorías seleccionadas heredarán las reglas de restricción por país definidas anteriormente.
  - **Valor recomendado:** Utilice esto para restricciones amplias. Déjelo vacío si desea gestionar las restricciones producto por producto.
  - **Escenario / ejemplo de comerciante:** Todos los productos de su categoría "Electrónica" no se pueden vender en Brasil. Seleccionaría la categoría "Electrónica" aquí.
- **Seleccionar fabricante**

  - **Qué hace este ajuste:** Le permite aplicar las reglas de restricción por país a todos los productos de fabricantes específicos.
  - **Efecto de cambiar este ajuste:** Todos los productos de los fabricantes seleccionados heredarán las reglas de restricción por país.
  - **Valor recomendado:** Utilice esto para restricciones a nivel de marca. Déjelo vacío si desea gestionar las restricciones producto por producto o categoría por categoría.
  - **Escenario / ejemplo de comerciante:** Tiene un acuerdo de distribución que le impide vender productos de "Marca X" en Europa. Seleccionaría "Marca X" aquí.

#### Exclusiones de clientes y grupos

- **Excluir grupos de clientes**

  - **Qué hace este ajuste:** Le permite eximir a ciertos grupos de clientes de las restricciones por país. Por ejemplo, podría tener un grupo B2B especial al que se le permite comprar productos restringidos.
  - **Efecto de cambiar este ajuste:** Los clientes que pertenezcan a los grupos seleccionados *no* estarán sujetos a las restricciones por país definidas por este módulo. Verán todos los productos.
  - **Valor recomendado:** Seleccione los grupos que necesitan acceso especial, como "Clientes mayoristas" o "Empleados". Déjelo vacío si todos los clientes deben estar sujetos a restricciones.
  - **Escenario / ejemplo de comerciante:** Tiene un grupo de "Clientes VIP" a quienes se les permite comprar productos que de otro modo están restringidos en su país. Seleccionaría el grupo "Clientes VIP" aquí.
- **Excluir clientes**

  - **Qué hace este ajuste:** Le permite eximir a clientes individuales específicos de las restricciones por país.
  - **Efecto de cambiar este ajuste:** Los clientes individuales seleccionados *no* estarán sujetos a las restricciones por país. Verán todos los productos.
  - **Valor recomendado:** Utilice esto para excepciones específicas. Déjelo vacío si no es necesario.
  - **Escenario / ejemplo de comerciante:** Un cliente específico es un socio a largo plazo y necesita acceso a todos los productos independientemente de su ubicación. Seleccionaría su cuenta de cliente aquí.

#### Ajustes de geolocalización y simulación

- **Establecer prioridad de los métodos de identificación de origen**

  - **Qué hace este ajuste:** Determina el orden en que el módulo intenta identificar el país del cliente. Esto es crucial para la precisión.
  - **Efecto de cambiar este ajuste:** El módulo intentará primero el método en la parte superior de la lista. Si falla o no está disponible, pasará al siguiente.
  - **Valor recomendado:**
    1. **Dirección de entrega (si está disponible):** Es la más precisa para la intención de compra real.
    2. **Geolocalización:** Buena para la navegación inicial.
    3. **País de la cuenta del cliente:** Si ha iniciado sesión.
  - **Escenario / ejemplo de comerciante:** Un cliente está navegando desde EE. UU. (geolocalización), pero tiene la intención de enviar a Canadá. Si se prioriza la "Dirección de entrega", el módulo utilizará Canadá para las restricciones una vez que la introduzca en el carrito.
- **Usar dirección de entrega**

  - **Qué hace este ajuste:** Cuando está activado, el módulo considerará el país de la dirección de entrega seleccionada por el cliente en el carrito de compras como su "origen" para aplicar las restricciones.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está Activado:* Si un cliente añade un producto restringido a su carrito y luego selecciona una dirección de entrega en un país bloqueado, el módulo impedirá el proceso de compra o eliminará el producto.
    - *Cuando está Desactivado:* El módulo se basará únicamente en la geolocalización por IP o en el país registrado del cliente, lo que podría no coincidir con su destino de envío previsto.
  - **Valor recomendado:** **SÍ**. Esto proporciona la aplicación de restricciones más precisa y práctica durante el proceso de compra.
  - **Escenario / ejemplo de comerciante:** Un cliente de Alemania (donde un producto está permitido) lo añade a su carrito, pero luego selecciona una dirección de envío en Austria (donde el producto está bloqueado). Con este ajuste activado, el módulo impedirá el pedido.
- **Simular visita**

  - **Qué hace este ajuste:** Le permite probar sus restricciones por país simulando una visita desde un país específico sin cambiar realmente su dirección IP.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está Activado:* El módulo tratará su sesión actual como si estuviera navegando desde el país especificado en "Simular IP".
    - *Cuando está Desactivado:* El módulo utiliza su dirección IP real para la geolocalización.
  - **Valor recomendado:** **Desactivado** para tiendas en vivo. **Activado** solo para pruebas.
  - **Escenario / ejemplo de comerciante:** Desea verificar si un producto está correctamente oculto para los clientes en Francia. Activa "Simular visita", introduce una dirección IP francesa (o selecciona Francia si está disponible) y luego navega por su tienda.
- **Simular IP**

  - **Qué hace este ajuste:** Cuando "Simular visita" está activado, este campo le permite introducir una dirección IP del país que desea simular, o seleccionar un país de una lista desplegable.
  - **Efecto de cambiar este ajuste:** El módulo utilizará esta IP/país para todas las comprobaciones de restricciones durante su sesión simulada.
  - **Valor recomendado:** Introduzca una dirección IP válida o seleccione un país para fines de prueba.
  - **Escenario / ejemplo de comerciante:** Para simular una visita desde Alemania, podría introducir `88.130.179.0` (una IP alemana) o simplemente seleccionar "Alemania" de la lista.

#### Ajustes de lista blanca

- **Activar lista blanca**

  - **Qué hace este ajuste:** Este ajuste aprovecha la función de lista blanca de geolocalización integrada de PrestaShop. Si la geolocalización de PrestaShop está activa, esta lista blanca le permite definir direcciones IP o rangos de IP específicos que *siempre* deben tener acceso a su tienda, independientemente de su país detectado. Esto es útil para las IP de su propia oficina o socios de confianza.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está Activado:* El módulo respetará la lista blanca de geolocalización de PrestaShop. Las IP de esta lista omitirán cualquier restricción por país.
    - *Cuando está Desactivado:* La lista blanca no se tendrá en cuenta.
  - **Valor recomendado:** **SÍ** si utiliza la geolocalización de PrestaShop y tiene IP que desea incluir en la lista blanca.
  - **Escenario / ejemplo de comerciante:** Su oficina está en un país donde ciertos productos están restringidos, pero necesita acceder a ellos para fines administrativos. Añadiría la dirección IP de su oficina a la lista blanca de geolocalización de PrestaShop y activaría este ajuste.
- **Lista blanca**

  - **Qué hace este ajuste:** Aquí es donde gestiona las direcciones IP o rangos de IP específicos que están en la lista blanca. Esto corresponde directamente al ajuste `PS_GEOLOCATION_WHITELIST` de PrestaShop.
  - **Efecto de cambiar este ajuste:** Cualquier dirección IP o rango introducido aquí omitirá todas las restricciones basadas en geolocalización.
  - **Valor recomendado:** Añada las direcciones IP de su propia oficina, las IP de su servidor de desarrollo o cualquier otra IP de confianza que siempre deba tener acceso completo.
  - **Escenario / ejemplo de comerciante:** Añade `192.168.1.1/24` (la red de su oficina) para asegurarse de que todos los empleados puedan acceder a todos los productos.

#### Ajustes de actualización (Internos)

- **mypresta\_updates, update\_, updatev\_**
  - **Qué hacen estos ajustes:** Estos son ajustes internos utilizados por los módulos de MyPresta.eu para gestionar actualizaciones y comprobaciones de versión. No están destinados a la interacción directa del comerciante.
  - **Efecto de cambiar este ajuste:** Modificarlos podría interferir con las notificaciones de actualización del módulo.
  - **Valor recomendado:** Deje estos ajustes tal como están.
  - **Escenario / ejemplo de comerciante:** No hay escenario de comerciante; estos son para la gestión interna del módulo.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | **Activado / Desactivado** | Activado | Interruptor principal para la funcionalidad del módulo. |
| Configuración del módulo | **¿Qué desea hacer?** | Bloquear acceso | Define si las reglas bloquean el acceso o permiten el acceso SÓLO. |
| Configuración del módulo | **Seleccionar países** | (Ninguno) | Países afectados por la regla de restricción. |
| Configuración del módulo | **Seleccionar categorías** | (Ninguno) | Categorías cuyos productos se ven afectados por la regla. |
| Configuración del módulo | **Seleccionar fabricante** | (Ninguno) | Fabricantes cuyos productos se ven afectados por la regla. |
| Configuración del módulo | **Excluir grupos de clientes** | (Ninguno) | Grupos de clientes exentos de restricciones. |
| Configuración del módulo | **Excluir clientes** | (Ninguno) | Clientes individuales exentos de restricciones. |
| Configuración del módulo | **Establecer prioridad de los métodos de identificación de origen** | Dirección de entrega, Geolocalización, País de la cuenta del cliente | Orden de los métodos para determinar el país del cliente. |
| Configuración del módulo | **Usar dirección de entrega** | SÍ | Considera la dirección de entrega para la aplicación de restricciones. |
| Configuración del módulo | **Simular visita** | Desactivado | Activa/desactiva la simulación de IP para pruebas. |
| Configuración del módulo | **Simular IP** | (Vacío) | Dirección IP/país a simular para pruebas. |
| Configuración del módulo | **Activar lista blanca** | SÍ | Activa/desactiva la lista blanca de geolocalización de PrestaShop. |
| Configuración del módulo | **Lista blanca** | (Vacío) | Lista de direcciones IP/rangos para omitir restricciones. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Los productos siguen siendo visibles en un país bloqueado, ¿qué debo hacer?**
R1: Primero, verifique la configuración de su módulo:
\* ¿Está el módulo "Activado"?
\* ¿Está "Qué desea hacer?" configurado correctamente (por ejemplo, "Bloquear acceso" si desea ocultarlos)?
\* ¿Están seleccionados los "Seleccionar países" correctos?
\* ¿Están "Seleccionar categorías" o "Seleccionar fabricante" aplicados correctamente a los productos en cuestión?
\* Si está probando, asegúrese de que "Simular visita" esté activado y "Simular IP" esté configurado en el país correcto.
\* Finalmente, borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**) y la caché de su navegador.

**P2: Mi propia dirección IP parece estar bloqueada, aunque estoy en un país permitido.**
R2: Esto puede ocurrir si su IP se identifica erróneamente de alguna manera o si ha cometido un error en su configuración.
\* Verifique el ajuste "Lista blanca" y asegúrese de que la dirección IP de su oficina o personal esté añadida allí si desea omitir todas las restricciones.
\* Verifique su dirección IP pública real (puede usar sitios web como "cuál es mi IP").
\* Asegúrese de que "Activar lista blanca" esté activado si está utilizando la lista blanca de geolocalización integrada de PrestaShop.

**P3: ¿Cómo determina el módulo el país de un cliente?**
R3: El módulo utiliza un sistema de prioridad:
1.  **Dirección de entrega:** Si "Usar dirección de entrega" está activado y el cliente ha introducido una dirección de envío en el carrito, esta se prioriza.
2.  **Geolocalización:** Utiliza la dirección IP del cliente para determinar su ubicación geográfica.
3.  **País de la cuenta del cliente:** Si el cliente ha iniciado sesión, utiliza el país registrado en su cuenta.
Puede ajustar la prioridad de estos métodos en la configuración del módulo.

**P4: Tengo un tema personalizado, ¿funcionará este módulo?**
R4: Sí, el módulo está diseñado para funcionar con temas estándar de PrestaShop. Principalmente filtra productos a nivel de datos antes de que sean renderizados por el tema. Sin embargo, si su tema personalizado tiene una lógica de listado de productos muy inusual o anula los hooks de visualización de productos principales de PrestaShop, podrían ser necesarios pequeños ajustes. Si encuentra problemas, póngase en contacto con el soporte de MyPresta.eu.

**P5: ¿Puedo restringir el acceso a productos específicos, no solo a categorías o fabricantes?**
R5: Sí, el módulo funciona filtrando productos. Si bien la pantalla de configuración principal le permite seleccionar categorías y fabricantes, la lógica central del módulo se aplica a productos individuales. Puede dejar "Seleccionar categorías" y "Seleccionar fabricante" vacíos y gestionar las restricciones directamente en las páginas de productos individuales (si el módulo añade una pestaña allí, lo cual es común para este tipo de módulos). *Según la información proporcionada, el módulo funciona configurando reglas que se aplican a los productos basándose en las categorías/fabricantes seleccionados en la configuración principal. No se menciona explícitamente una pestaña de configuración a nivel de producto, pero la descripción implica "cada producto individualmente". Si no hay una pestaña de producto, la selección de categoría/fabricante es la forma principal de dirigir los productos.*

## 4. Guía para desarrolladores y webmasters (arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Acceso a productos por país" (`atpbc`) está construido como un módulo estándar de PrestaShop, aprovechando el patrón MVC cuando es apropiado. Su función principal es interceptar las consultas de productos y filtrar los resultados basándose en las restricciones por país configuradas y la ubicación identificada del cliente. Se integra con el núcleo de PrestaShop enganchándose en varios puntos de visualización y acción, particularmente aquellos relacionados con la obtención y visualización de productos. La geolocalización es un componente clave, que determina el origen del cliente, que luego se cruza con las reglas del módulo.

### 4.2 Controladores (`controllers/`)

El módulo no parece tener controladores personalizados de front-office o back-office en su directorio `controllers/` según el inventario proporcionado. Toda la configuración se gestiona dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no parece tener clases personalizadas o definiciones de `ObjectModel` en un directorio `classes/`. La lógica central y el manejo de datos probablemente están encapsulados dentro del archivo principal `atpbc.php`, utilizando `Configuration` para la configuración y consultas directas a la base de datos o las clases `Product` y `Category` de PrestaShop para la manipulación de datos.

### 4.4 Activos de JavaScript (`views/js/`)

- **`atpbc/lib/searchTool/views/js/autocomplete.js`**
  - **Alcance:** Back-office.
  - **Propósito:** Este script probablemente proporciona funcionalidad de autocompletado para campos de entrada dentro de la configuración del módulo, como la selección de clientes, categorías o fabricantes. Mejora la experiencia del usuario sugiriendo opciones a medida que el administrador escribe, reduciendo errores y acelerando la configuración.
  - **Funcionalidad:** Vincula escuchadores de eventos a campos de entrada específicos (por ejemplo, `keyup`, `focus`), envía solicitudes AJAX a un endpoint del back-office (probablemente manejado por el archivo principal del módulo o un controlador de administración central de PrestaShop) para obtener sugerencias y muestra estas sugerencias en una lista desplegable. Maneja la selección y el llenado del campo de entrada.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`atpbc/lib/searchTool/views/css/autocomplete.css`**
  - **Alcance:** Estilo del formulario de administración del back-office.
  - **Propósito:** Proporciona estilo para el desplegable de sugerencias de autocompletado y, potencialmente, para los propios campos de entrada, asegurando una apariencia consistente y fácil de usar dentro del back office de PrestaShop.
  - **Selectores clave:** Probablemente apunta a clases como `.autocomplete-suggestions`, `.autocomplete-suggestion-item`, `.autocomplete-input` para controlar el diseño, los colores, las fuentes y los estados de hover. Los desarrolladores pueden anularlos en su tema de administración personalizado o añadiendo CSS de mayor especificidad.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`atpbc/lib/searchTool/views/scripts.tpl`**

  - **Alcance:** Back-office.
  - **Propósito:** Esta plantilla se utiliza probablemente para incluir el script `autocomplete.js` y, potencialmente, otras configuraciones relacionadas con JavaScript o scripts en línea para la funcionalidad de `searchTool`. También podría definir variables pasadas a JavaScript.
  - **Renderizado en:** Probablemente enganchado en `actionAdminControllerSetMedia` o incluido directamente en la plantilla de configuración principal.
- **`atpbc/views/templates/admin/AdminTab.tpl`**

  - **Alcance:** Back-office.
  - **Propósito:** Esta plantilla es probablemente una plantilla genérica para una pestaña de administración personalizada o una sección dentro de la configuración del módulo. Podría contener la estructura para mostrar listas, formularios u otro contenido administrativo.
  - **Renderizado en:** Podría ser incluido por `configuration.tpl` o utilizado si el módulo tuviera un controlador de administración dedicado.
- **`atpbc/views/templates/admin/button-subcategories.tpl`**

  - **Alcance:** Back-office.
  - **Propósito:** Esta plantilla probablemente renderiza un botón o elemento de interfaz de usuario específicamente para gestionar subcategorías dentro de la configuración del módulo, posiblemente para el ajuste "Seleccionar categorías" para expandir/contraer árboles de categorías.
  - **Renderizado en:** Dentro de `configuration.tpl` al mostrar las opciones de selección de categoría.
- **`atpbc/views/templates/admin/configuration.tpl`**

  - **Alcance:** Back-office.
  - **Propósito:** Esta es la plantilla principal de Smarty para la página de configuración del módulo, renderizada por el método `getContent()` en `atpbc.php`. Contiene todos los formularios HTML, campos de entrada, interruptores y listas de selección para los ajustes del módulo.
  - **Renderizado en:** Al acceder a la página de configuración del módulo en el Back Office de PrestaShop.
- **`atpbc/views/templates/hook/displayHeader.tpl`**

  - **Alcance:** Front-office.
  - **Propósito:** Esta plantilla está enganchada en `displayHeader`. Se utiliza típicamente para incluir CSS, JavaScript o metaetiquetas del front-office que necesitan cargarse temprano en la página. Para este módulo, podría incluir lógica para detectar el país del cliente o configurar variables del lado del cliente para su uso posterior.
  - **Renderizado en:** La sección `<head>` de cada página del front-office.
- **`atpbc/views/templates/hook/displayHeaderNoAccess.tpl`**

  - **Alcance:** Front-office.
  - **Propósito:** Esta plantilla es probablemente una alternativa o una visualización específica para cuando se detecta que un cliente no tiene "acceso" a un producto o página en particular. Podría contener un script de redirección, un mensaje o un estilo específico para ocultar contenido.
  - **Renderizado en:** Potencialmente dentro de `displayHeader` u otro hook, condicional a las restricciones de acceso.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo utiliza principalmente la tabla `ps_configuration` de PrestaShop para almacenar sus ajustes (por ejemplo, `atpbc_EXCLUDE_GROUP`, `atpbc_EXCLUDE_CUSTOMER`, `atpbc_COUNTRY`, `atpbc_WTD`, `atpbc_MANUFACT`, `atpbc_CATEGORIES`, `atpbc_PRIORITY`, `atpbc_SIMULATE_ON`, `atpbc_SIMULATE_IP`, `atpbc_DELIVERY`, `atpbc_WHITELIST_ON`).
  - No parece crear tablas SQL personalizadas según el inventario proporcionado.
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Antes de que se renderice el contenido de un controlador de administración, después de que se establezcan los medios. | Para incluir JS/CSS del back-office (por ejemplo, `autocomplete.js`, `autocomplete.css`) para la página de configuración del módulo. |
| `actionDispatcherAfter` | Después de que el despachador haya procesado una solicitud. | Potencialmente utilizado para realizar redirecciones o modificar la respuesta basándose en las reglas de acceso después de que se haya identificado una página. |
| `displayFilterProductSearch` | Durante el filtrado de búsqueda de productos. | Para modificar los resultados de la búsqueda de productos, eliminando los productos restringidos según el país. |
| `actionProductUpdate` | Después de que un producto se actualiza en el Back Office. | Para potencialmente borrar la caché relacionada con la disponibilidad del producto o reevaluar las reglas para el producto actualizado. |
| `displayAdminProductsExtra` | En la página de edición de productos en el Back Office. | Para añadir campos adicionales o una pestaña para reglas de acceso específicas del producto (aunque no se indica explícitamente, este es un uso común para este hook). |
| `actionCartSave` | Después de que un carrito se guarda o actualiza. | Para verificar si los productos en el carrito están permitidos para el país identificado del cliente (especialmente si "Usar dirección de entrega" está activado). |
| `FilterProductSearch` | Durante el filtrado de búsqueda de productos (similar a `displayFilterProductSearch`, a menudo para manipular la consulta directamente). | Para modificar la consulta de la base de datos para las búsquedas de productos, asegurando que los productos restringidos no se recuperen. |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Para incluir JavaScript/CSS del front-office (por ejemplo, `displayHeader.tpl`, `displayHeaderNoAccess.tpl`) o realizar una detección temprana del país. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte profesional, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar que su módulo funcione de manera óptima y proporcione la mejor experiencia posible para su tienda.

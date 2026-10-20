---
title: "Ocultar productos por país - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Ocultar productos por país' de MyPresta.eu."
sidebar:
  label: "Ocultar productos por país - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Hide products by country en MyPresta.eu](https://mypresta.eu/modules/front-office-features/hide-products-by-country.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/hide-products-by-country/)
>
> ---


# Ocultar productos por país

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Puede acceder a la configuración del módulo navegando a **Módulos > Gestor de módulos** y buscando "Ocultar productos por país", luego haciendo clic en "Configurar".

#### Ajustes generales

- **Activado / Desactivado (Interruptor)**

  - **Qué hace este ajuste:** Este es el interruptor maestro para todo el módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El módulo filtra activamente los productos según sus ajustes.
    - *Cuando está desactivado:* El módulo deja de filtrar productos y todos los productos serán visibles para todos los clientes, independientemente del país.
  - **Valor recomendado:** **Activado** una vez que haya configurado sus reglas.
  - **Escenario / ejemplo de comerciante:** Está configurando el módulo por primera vez y quiere probarlo antes de ponerlo en marcha, por lo que lo mantiene desactivado. Una vez listo, lo activa.
- **¿Qué desea hacer? (Desplegable)**

  - **Qué hace este ajuste:** Define la lógica central de sus reglas de ocultación de productos.
  - **Efecto de cambiar este ajuste:**
    - *Ocultar productos para los países seleccionados:* Los productos elegidos en las secciones "Seleccionar categorías" y "Seleccionar fabricante" se ocultarán a los clientes de la lista "Seleccionar países". Este es el caso de uso más común.
    - *Mostrar productos solo para los países seleccionados:* Los productos elegidos SOLO serán visibles para los clientes de la lista "Seleccionar países". Para todos los demás países, estos productos se ocultarán.
  - **Valor recomendado:** Normalmente **Ocultar productos para los países seleccionados**.
  - **Escenario / ejemplo de comerciante:**
    - *Ocultar productos:* Vende una marca específica que no se puede vender en Alemania. Selecciona "Ocultar productos para los países seleccionados", elige la marca y selecciona Alemania.
    - *Mostrar productos solo:* Tiene una colección especial de productos exclusivamente para el mercado estadounidense. Selecciona "Mostrar productos solo para los países seleccionados", elige la colección y selecciona Estados Unidos.
- **Seleccionar países (Lista de selección múltiple)**

  - **Qué hace este ajuste:** Le permite elegir los países específicos a los que se aplicará su regla "¿Qué desea hacer?".
  - **Efecto de cambiar este ajuste:** Solo los clientes identificados como de estos países seleccionados se verán afectados por las reglas de visibilidad del producto que establezca.
  - **Valor recomendado:** Seleccione todos los países relevantes para sus reglas.
  - **Escenario / ejemplo de comerciante:** Si está ocultando productos para clientes en Francia y España, seleccionaría "Francia" y "España" de esta lista.
- **Seleccionar categorías (Árbol de categorías)**

  - **Qué hace este ajuste:** Le permite elegir categorías de productos específicas cuyos productos estarán sujetos a la regla de ocultación/visualización.
  - **Efecto de cambiar este ajuste:** Todos los productos dentro de las categorías seleccionadas (y sus subcategorías, si elige incluirlas) se verán afectados por la regla "¿Qué desea hacer?".
  - **Valor recomendado:** Seleccione las categorías que contienen los productos que desea controlar.
  - **Escenario / ejemplo de comerciante:** Desea ocultar todos los productos de su categoría "Electrónica" para los clientes de Canadá. Seleccionaría "Electrónica" aquí.
- **Seleccionar fabricante (Lista de selección múltiple)**

  - **Qué hace este ajuste:** Le permite elegir fabricantes específicos cuyos productos estarán sujetos a la regla de ocultación/visualización.
  - **Efecto de cambiar este ajuste:** Todos los productos de los fabricantes seleccionados se verán afectados por la regla "¿Qué desea hacer?".
  - **Valor recomendado:** Seleccione los fabricantes cuyos productos desea controlar.
  - **Escenario / ejemplo de comerciante:** Tiene un acuerdo de distribución que le impide vender productos de "Marca X" en Australia. Seleccionaría "Marca X" aquí.
- **Excluir grupos de clientes (Lista de selección múltiple)**

  - **Qué hace este ajuste:** Le permite eximir a ciertos grupos de clientes de las reglas de ocultación de productos del módulo.
  - **Efecto de cambiar este ajuste:** Los clientes que pertenecen a los grupos seleccionados siempre verán todos los productos, independientemente de su país o de la configuración del módulo. Esto es útil para socios B2B o VIP.
  - **Valor recomendado:** Déjelo vacío a menos que tenga grupos de clientes específicos que necesiten omitir las reglas.
  - **Escenario / ejemplo de comerciante:** Tiene un grupo de clientes "Mayoristas" que siempre deben ver su catálogo completo, incluso si algunos productos están restringidos para clientes habituales en su país. Seleccionaría "Mayoristas" aquí.
- **Excluir clientes (Entrada de búsqueda)**

  - **Qué hace este ajuste:** Le permite eximir a clientes individuales de las reglas de ocultación de productos del módulo.
  - **Efecto de cambiar este ajuste:** Los clientes específicos que seleccione siempre verán todos los productos, independientemente de su país o de la configuración del módulo.
  - **Valor recomendado:** Déjelo vacío a menos que tenga clientes individuales específicos que necesiten omitir las reglas.
  - **Escenario / ejemplo de comerciante:** Un gerente de cuenta clave específico necesita ver todos los productos para un cliente, incluso si está navegando desde un país restringido. Buscaría y seleccionaría a ese cliente aquí.

#### Ajustes de geolocalización y simulación

- **Establecer prioridad de los métodos de identificación de origen (Lista de arrastrar y soltar)**

  - **Qué hace este ajuste:** Determina el orden en que el módulo intenta identificar el país de un cliente. Esto es crucial porque diferentes métodos a veces pueden dar resultados diferentes.
  - **Efecto de cambiar este ajuste:** El módulo intentará los métodos de arriba a abajo. Se utilizará la primera identificación exitosa.
    - *Dirección de entrega:* Utiliza el país de la dirección de entrega seleccionada por el cliente (requiere que el cliente haya iniciado sesión y tenga una dirección).
    - *Dirección IP (Geolocalización):* Utiliza la dirección IP del cliente para determinar su país (más común para invitados).
    - *Idioma del navegador:* Infiere el país de la configuración de idioma del navegador del cliente (menos fiable para una identificación precisa del país).
  - **Valor recomendado:**
    1. Dirección de entrega (si la dirección del cliente que ha iniciado sesión es la más importante)
    2. Dirección IP (para una precisión general para todos los visitantes)
    3. Idioma del navegador (como respaldo, menos preciso)
  - **Escenario / ejemplo de comerciante:** Desea priorizar la dirección de entrega real del cliente si ha iniciado sesión, ya que esta es la más precisa para el envío. Para los invitados, desea confiar en la geolocalización por IP. Arrastraría "Dirección de entrega" a la parte superior, luego "Dirección IP".
- **Usar dirección de entrega (Interruptor)**

  - **Qué hace este ajuste:** Controla si el módulo considera el país de la dirección de entrega elegida por el cliente para el filtrado de productos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Si un cliente ha iniciado sesión y tiene una dirección de entrega seleccionada, el módulo utilizará el país de esa dirección para determinar la visibilidad del producto.
    - *Cuando está desactivado:* El módulo ignorará la dirección de entrega y se basará en otros métodos (como la dirección IP) incluso para los clientes que han iniciado sesión.
  - **Valor recomendado:** **Activado** para clientes que han iniciado sesión, ya que la dirección de entrega suele ser el indicador más preciso de dónde debe ir el producto.
  - **Escenario / ejemplo de comerciante:** Un cliente de EE. UU. está navegando desde Canadá. Si "Usar dirección de entrega" está activado y tiene una dirección de entrega de EE. UU. seleccionada, verá los productos disponibles en EE. UU. Si está desactivado, podría ver los productos disponibles en Canadá (según su IP).
- **Activar lista blanca (Interruptor)**

  - **Qué hace este ajuste:** Este ajuste funciona en conjunto con la función de geolocalización incorporada de PrestaShop (que se encuentra en **Parámetros de la tienda > General > Geolocalización**). Si la geolocalización de PrestaShop está activada, este módulo puede usar su lista blanca.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Si la geolocalización nativa de PrestaShop está activa y configurada con una lista blanca (países permitidos para navegar), este módulo respetará esa lista blanca. Los visitantes de países *no* incluidos en la lista blanca de PrestaShop podrían ser bloqueados o redirigidos antes de que este módulo aplique sus reglas.
    - *Cuando está desactivado:* Este módulo ignorará la lista blanca de geolocalización de PrestaShop y aplicará sus reglas basándose en su propia identificación de país.
  - **Valor recomendado:** **Desactivado** a menos que esté utilizando y gestionando activamente la lista blanca de geolocalización nativa de PrestaShop.
  - **Escenario / ejemplo de comerciante:** Ha configurado la geolocalización de PrestaShop para permitir solo visitantes de países de la UE. Si activa "Activar lista blanca" aquí, los visitantes de fuera de la UE serán gestionados por el sistema central de PrestaShop, y este módulo aplicará sus reglas específicas de productos a los visitantes de la UE permitidos.
- **Simular visita (Interruptor)**

  - **Qué hace este ajuste:** Esta es una potente herramienta de prueba que le permite simular que está navegando desde un país diferente sin cambiar realmente su ubicación ni usar una VPN.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El campo "Simular IP" se activa, lo que le permite introducir una dirección IP. El módulo tratará su sesión de navegación actual como si estuviera visitando desde el país asociado a esa IP.
    - *Cuando está desactivado:* El módulo identifica su país normalmente.
  - **Valor recomendado:** **Desactivado** para tiendas en vivo. Solo actívelo temporalmente para realizar pruebas.
  - **Escenario / ejemplo de comerciante:** Desea verificar que los productos están correctamente ocultos para los clientes en Alemania. Activa "Simular visita", introduce una dirección IP alemana (por ejemplo, 85.214.132.112) y luego navega por su tienda para ver si los productos correctos están ocultos.
- **Simular IP (Entrada de texto)**

  - **Qué hace este ajuste:** Cuando "Simular visita" está activado, introduce una dirección IP aquí para simular un visitante del país de esa IP.
  - **Efecto de cambiar este ajuste:** Su sesión de navegación actual se comportará como si estuviera ubicado en el país asociado a la dirección IP introducida, lo que le permite probar las reglas de visibilidad del producto.
  - **Valor recomendado:** Déjelo vacío a menos que "Simular visita" esté activado para realizar pruebas.
  - **Escenario / ejemplo de comerciante:** Después de activar "Simular visita", introduce "192.168.1.1" (una IP local común, pero usaría una IP pública real para un país) para probar. Para una IP alemana, podría usar "85.214.132.112".

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | **Activado** | Activado | Interruptor maestro para la funcionalidad del módulo. |
| Configuración del módulo | **¿Qué desea hacer?** | Ocultar productos para los países seleccionados | Define si los productos se ocultan para los países seleccionados o solo se muestran a ellos. |
| Configuración del módulo | **Seleccionar países** | (Vacío) / Seleccionar relevantes | Países afectados por la regla de visibilidad del producto. |
| Configuración del módulo | **Seleccionar categorías** | (Vacío) / Seleccionar relevantes | Categorías cuyos productos se ven afectados. |
| Configuración del módulo | **Seleccionar fabricante** | (Vacío) / Seleccionar relevantes | Fabricantes cuyos productos se ven afectados. |
| Configuración del módulo | **Excluir grupos de clientes** | (Vacío) | Grupos de clientes exentos de las reglas de ocultación. |
| Configuración del módulo | **Excluir clientes** | (Vacío) | Clientes individuales exentos de las reglas de ocultación. |
| Configuración del módulo | **Establecer prioridad de los métodos de identificación de origen** | Dirección de entrega, Dirección IP, Idioma del navegador | Orden de los métodos para identificar el país del cliente. |
| Configuración del módulo | **Usar dirección de entrega** | Activado | Usar el país de la dirección de entrega del cliente para el filtrado. |
| Configuración del módulo | **Activar lista blanca** | Desactivado | Respetar la lista blanca de geolocalización nativa de PrestaShop. |
| Configuración del módulo | **Simular visita** | Desactivado | Activar para probar la visibilidad del producto desde una IP específica. |
| Configuración del módulo | **Simular IP** | (Vacío) | Dirección IP a simular cuando "Simular visita" está activado. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He configurado el módulo, pero los productos siguen visibles/ocultos incorrectamente. ¿Qué debo verificar primero?**
R:

1. **Módulo activado:** Verifique que el interruptor principal "Activado" en la página de configuración del módulo esté ENCENDIDO.
2. **Caché:** Borre la caché de su PrestaShop (Vaya a **Parámetros avanzados > Rendimiento**, luego haga clic en "Borrar caché" en la esquina superior derecha). La caché del navegador también puede interferir a veces, así que intente una actualización forzada (Ctrl+F5 o Cmd+Shift+R) o una ventana de navegación de incógnito/privada.
3. **Simulación:** Si está probando, asegúrese de que "Simular visita" esté activado y "Simular IP" esté configurado correctamente. Si no está simulando, asegúrese de que "Simular visita" esté desactivado.
4. **Lógica de la regla:** Revise su configuración "¿Qué desea hacer?" ("Ocultar productos para los países seleccionados" vs. "Mostrar productos solo para los países seleccionados") y asegúrese de que coincida con su intención.
5. **Selección de país/categoría/fabricante:** Asegúrese de haber seleccionado correctamente los países, categorías y fabricantes que deben verse afectados.

**P: ¿Cómo identifica el módulo el país de un cliente?**
R: El módulo utiliza un sistema de prioridad que usted configura:

1. **Dirección de entrega:** Si el cliente ha iniciado sesión y tiene una dirección de entrega, esta es la más precisa.
2. **Dirección IP (Geolocalización):** Para invitados o si no se utiliza una dirección de entrega, utiliza la dirección IP del visitante para determinar su país.
3. **Idioma del navegador:** Como respaldo, puede inferir el país de la configuración de idioma del navegador, aunque esto es menos preciso. Puede ajustar la prioridad en la configuración del módulo.

**P: ¿Afectará este módulo a mi SEO? ¿Google seguirá indexando mis productos ocultos?**
R: El módulo oculta productos de la visualización del front-office para países específicos. Generalmente, los rastreadores de motores de búsqueda (como Googlebot) a menudo rastrean desde direcciones IP específicas (por ejemplo, IP con sede en EE. UU.). Si sus productos están ocultos para EE. UU., es posible que Google no los vea. Si están ocultos para otros países pero visibles para EE. UU., Google aún podría indexarlos. Para preocupaciones críticas de SEO, considere usar la función nativa de PrestaShop "Desactivar producto" o reglas específicas de robots.txt si no desea absolutamente que un producto se indexe en ningún lugar. Este módulo es principalmente para la experiencia del usuario final y el cumplimiento, no para el control de SEO.

**P: ¿Puedo ocultar productos para clientes o grupos de clientes específicos, independientemente de su país?**
R: ¡Sí! El módulo incluye las configuraciones "Excluir grupos de clientes" y "Excluir clientes". Estas le permiten especificar grupos o clientes individuales que *siempre* verán todos los productos, omitiendo efectivamente las reglas de ocultación basadas en el país. Esto es útil para VIP, socios B2B o personal interno.

**P: ¿Qué sucede si un cliente de un país restringido intenta acceder a un producto oculto a través de un enlace directo?**
R: El módulo está diseñado para evitar el acceso. Normalmente, serán redirigidos a la página de inicio o a un error de "página no encontrada", asegurándose de que no puedan ver ni añadir el producto restringido a su carrito.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Ocultar productos por país" (`hbc`) opera principalmente anulando clases centrales de PrestaShop y utilizando hooks para interceptar y modificar las consultas de productos antes de que se muestren al cliente. Aprovecha el `ObjectModel` de PrestaShop para el almacenamiento de la configuración y se basa en la geolocalización por IP o los datos de la dirección del cliente para determinar el país del visitante. La lógica del módulo se inyecta en el proceso de filtrado de productos, asegurando que los productos restringidos se eliminen de los listados, los resultados de búsqueda y los intentos de acceso directo.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador de administración de Front-Office o Back-Office dedicado. Su configuración se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos centrales (`classes/`)

El módulo implementa anulaciones para modificar el comportamiento central de PrestaShop.

- **`hbc/override/classes/index.php`**: Archivo `index.php` vacío estándar para evitar la lista de directorios.
- **`hbc/override/classes/shop/index.php`**: Archivo `index.php` vacío estándar para evitar la lista de directorios.
- **`hbc/override/classes/shop/Shop.php`**:
  - **Nombre de la clase**: `Shop` (anula la clase `Shop` central de PrestaShop)
  - **Clase padre**: `ShopCore`
  - **Responsabilidad**: Esta anulación es crítica. Probablemente modifica cómo se determina el contexto del producto o el contexto de la tienda, inyectando potencialmente lógica de filtrado específica del país a un nivel muy fundamental del sistema de múltiples tiendas y recuperación de productos de PrestaShop. Esto asegura que las reglas de visibilidad del producto se apliquen de manera consistente en varias partes de la tienda. Los desarrolladores deben tener en cuenta que anular `Shop.php` puede tener efectos de gran alcance y puede entrar en conflicto con otros módulos que también anulan esta clase central.

### 4.4 Activos de JavaScript (`views/js/`)

- **`hbc/lib/searchTool/views/js/autocomplete.js`**:
  - **Alcance**: Back-office (probablemente utilizado en el formulario de configuración del módulo).
  - **Propósito**: Este script proporciona funcionalidad de autocompletado, específicamente para el campo de entrada "Excluir clientes" en la configuración del módulo. Probablemente realiza llamadas AJAX a un punto final de administración de PrestaShop para buscar clientes a medida que el administrador escribe, mejorando la usabilidad para seleccionar clientes individuales.
  - **Funcionalidad clave**:
    - Inicializa un widget de autocompletado en un campo de entrada específico (por ejemplo, `#hbc_exclude_customer`).
    - Envía solicitudes AJAX (por ejemplo, a `admin-ajax.php` o un controlador de administración dedicado) con la consulta escrita.
    - Analiza las respuestas JSON que contienen datos del cliente (ID, nombre, correo electrónico).
    - Muestra sugerencias en una lista desplegable.
    - Maneja la selección de un cliente, rellenando una entrada oculta con el ID del cliente y mostrando el nombre.
    - Gestiona la eliminación de clientes seleccionados de la lista.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`hbc/lib/searchTool/views/css/autocomplete.css`**:
  - **Alcance**: Back-office (estiliza el widget de autocompletado).
  - **Propósito**: Proporciona estilo para la herramienta de búsqueda de autocompletado de clientes utilizada en la configuración del módulo. Esto incluye el estilo para el campo de entrada, la lista desplegable de sugerencias y, potencialmente, la visualización de los clientes seleccionados.
  - **Selectores clave**: Probablemente apunta a clases e IDs asociados con el widget de autocompletado, como `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item` y elementos para mostrar etiquetas/tokens seleccionados.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`hbc/lib/searchTool/views/scripts.tpl`**:

  - **Alcance**: Back-office.
  - **Propósito**: Esta plantilla probablemente incluye los archivos JavaScript y CSS necesarios para la herramienta de búsqueda de autocompletado (`autocomplete.js` y `autocomplete.css`) y potencialmente inicializa la lógica de JavaScript. Probablemente se incluye en la plantilla de configuración principal.
- **`hbc/views/templates/admin/AdminTab.tpl`**:

  - **Alcance**: Back-office.
  - **Propósito**: Esta plantilla es probablemente un envoltorio genérico o un componente utilizado dentro de la página de configuración del módulo. Podría definir la estructura para una interfaz con pestañas o una sección específica dentro de la configuración del módulo.
- **`hbc/views/templates/admin/button-subcategories.tpl`**:

  - **Alcance**: Back-office.
  - **Propósito**: Esta plantilla probablemente renderiza un botón o un elemento de interfaz de usuario relacionado con la selección de categorías, específicamente para incluir/excluir subcategorías al seleccionar categorías principales en el formulario de configuración.
- **`hbc/views/templates/admin/configuration.tpl`**:

  - **Alcance**: Back-office.
  - **Propósito**: Esta es la plantilla principal de Smarty para la página de configuración del módulo. Renderiza todos los ajustes, campos de entrada, interruptores y listas descritos en la Sección 4.1. Utiliza los componentes del formulario de ayuda de PrestaShop y probablemente incluye `scripts.tpl` para la funcionalidad de autocompletado.
- **`hbc/views/templates/hook/displayHeader.tpl`**:

  - **Alcance**: Front-office.
  - **Hook**: `displayHeader`
  - **Propósito**: Esta plantilla se renderiza en la sección `<head>` de cada página del front-office. Podría usarse para:
    - Inyectar JavaScript en línea para la detección de países del lado del cliente (menos probable dado el filtrado del lado del servidor).
    - Establecer variables de JavaScript basadas en la configuración del módulo (por ejemplo, modo de simulación).
    - Incluir archivos CSS o JS adicionales que sean necesarios globalmente para la funcionalidad del front-office del módulo (aunque el filtrado central es del lado del servidor).
    - Potencialmente manejar redirecciones o verificaciones iniciales basadas en la geolocalización antes de que la página se cargue por completo.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:

  - El módulo utiliza principalmente la tabla `ps_configuration` de PrestaShop para almacenar su configuración.
  - Las claves de configuración incluyen: `HBC_EXCLUDE_GROUP`, `HBC_EXCLUDE_CUSTOMER`, `HBC_SIMULATE_ON`, `HBC_SIMULATE_IP`, `HBC_DELIVERY`, `HBC_WHITELIST_ON`, `HBC_COUNTRY`, `HBC_WTD`, `HBC_MANUFACT`, `HBC_CATEGORIES`, `HBC_PRIORITY`.
  - Este módulo no crea tablas SQL personalizadas.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Alcance | Momento de ejecución | Propósito técnico |
| --- | --- | --- | --- |
| `displayHeader` | Front-office | En la sección `<head>` de cada página. | Potencialmente para inyectar scripts del lado del cliente, metaetiquetas o comprobaciones iniciales. |
| `actionAdminControllerSetMedia` | Back-office | Cuando un controlador de administración establece sus activos multimedia. | Se utiliza para cargar CSS/JS para la página de configuración del módulo (por ejemplo, `autocomplete.js`, `autocomplete.css`). |
| `actionDispatcherAfter` | Front-office | Después de que el despachador haya procesado la solicitud. | Podría usarse para realizar redirecciones o comprobaciones finales después de que se haya identificado una página pero antes de la renderización. |
| `displayFilterProductSearch` | Front-office | Durante el filtrado de búsqueda de productos. | **CRÍTICO**: Este hook se utiliza para inyectar la lógica del módulo en la consulta de búsqueda de productos, asegurando que los productos ocultos se excluyan de los resultados de búsqueda. |
| `actionProductUpdate` | Back-office | Después de que un producto se actualiza en el Back Office. | Podría usarse para borrar la caché relacionada con la visibilidad del producto o reevaluar las reglas para el producto actualizado. |
| `displayAdminProductsExtra` | Back-office | En la página de edición de productos en el Back Office. | Podría usarse para mostrar información o configuraciones adicionales relacionadas con la ocultación de productos para el producto específico que se está editando (aunque no se identifica explícitamente en la configuración). |
| `actionCartSave` | Front-office | Cuando se guarda el carrito (por ejemplo, se añade/elimina un producto). | Podría usarse para evitar añadir productos ocultos al carrito o para eliminarlos si el país del cliente cambia. |
| `FilterProductSearch` | Front-office | Durante el filtrado de búsqueda de productos (similar a `displayFilterProductSearch`). | **CRÍTICO**: Otro hook para modificar las consultas de búsqueda de productos, asegurando un filtrado completo en diferentes contextos de búsqueda. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Ocultar productos por país", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.

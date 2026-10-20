---
title: "Generador de Referencias de Pedido Personalizadas Pro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Generador de Referencias de Pedido Personalizadas Pro de MyPresta.eu."
sidebar:
  label: "Generador de Referencias de Pedido Personalizadas Pro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Custom Order Reference Generator Pro en MyPresta.eu](https://mypresta.eu/modules/administration-tools/custom-order-reference-generator-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/custom-order-reference-generator-pro/)
>
> ---


# Generador de Referencias de Pedido Personalizadas Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo de Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Generador de Referencias de Pedido Personalizadas Pro)

Esta es la pantalla de configuración principal donde define sus patrones y reglas de referencia de pedido personalizados. La página suele estar organizada en varias pestañas o secciones para mayor claridad.

#### **Pestaña de Configuración General**

Esta pestaña controla el comportamiento fundamental del módulo.

- **Habilitar Generación de Referencias de Pedido Personalizadas:**

  - **Qué hace esta configuración:** Este es el interruptor maestro del módulo. Cuando está habilitado, el módulo se encargará de la generación de referencias de pedido. Cuando está deshabilitado, PrestaShop volverá a su método predeterminado de generación de referencias de pedido.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado:* Todos los pedidos nuevos recibirán una referencia generada por este módulo de acuerdo con sus reglas definidas.
    - *Cuando está deshabilitado:* Todos los pedidos nuevos utilizarán el formato de referencia predeterminado de PrestaShop. Los pedidos existentes conservarán sus referencias.
  - **Valor recomendado:** SÍ (para activar la funcionalidad del módulo).
  - **Escenario / ejemplo del comerciante:** Si desea comenzar a usar referencias personalizadas, habilítelo. Si necesita volver temporalmente a la configuración predeterminada de PrestaShop para solucionar problemas, desactívelo.
- **Patrón de Referencia Predeterminado:**

  - **Qué hace esta configuración:** Esto define la estructura básica para sus referencias de pedido personalizadas. Puede combinar texto estático con "códigos cortos" dinámicos que extraen información del pedido, el cliente o la fecha.
  - **Efecto de cambiar esta configuración:** Esto dicta directamente el formato de sus referencias de pedido cuando no se aplica ninguna regla específica.
  - **Valor recomendado:** Comience con algo simple como `MITIENDA-{DATE:YMD}-{ID_ORDER}` o `PED-{RAND:6}`.
  - **Escenario / ejemplo del comerciante:**
    - `MITIENDA-{DATE:YMD}-{ID_ORDER}`: Genera referencias como `MITIENDA-20231027-12345`. Esto es ideal para identificar fácilmente los pedidos de su tienda y ver la fecha en que se realizaron, junto con un ID de pedido secuencial.
    - `PED-{RAND:6}`: Genera referencias como `PED-A1B2C3`. Esto proporciona una referencia corta, aleatoria y única.
    - `{CUSTOMER_LASTNAME}-{ID_ORDER}`: Genera referencias como `SMITH-12345`. Útil para B2B o servicio personalizado.
  - **Códigos Cortos Disponibles:**
    - `{ID_ORDER}`: El ID único del pedido (secuencial).
    - `{ID_CUSTOMER}`: El ID único del cliente.
    - `{DATE:format}`: Fecha y hora actuales. `format` utiliza la sintaxis de la función `date()` de PHP (por ejemplo, `YMD` para 20231027, `His` para 143059).
    - `{RAND:length}`: Una cadena aleatoria de caracteres alfanuméricos, `length` especifica cuántos caracteres (por ejemplo, `RAND:6`).
    - `{CUSTOMER_FIRSTNAME}`: Nombre del cliente.
    - `{CUSTOMER_LASTNAME}`: Apellido del cliente.
    - `{CUSTOMER_EMAIL}`: Dirección de correo electrónico del cliente.
    - `{PAYMENT_METHOD}`: El método de pago utilizado para el pedido.
    - `{DELIVERY_COUNTRY_ISO}`: Código ISO del país de entrega (por ejemplo, US, FR).
    - `{DELIVERY_CITY}`: Ciudad de la dirección de entrega.
    - `{CART_TOTAL}`: Valor total del carrito.
    - `{PRODUCT_SKU}`: SKU del primer producto en el carrito (usar con precaución, puede ser largo).
    - `{PRODUCT_NAME}`: Nombre del primer producto en el carrito (usar con precaución).
    - `{SHOP_NAME}`: Nombre de su tienda PrestaShop.
- **Valor Inicial del Contador Secuencial:**

  - **Qué hace esta configuración:** Si su patrón de referencia incluye `{ID_ORDER}` o un elemento secuencial similar, esto define el número inicial para esa secuencia.
  - **Efecto de cambiar esta configuración:** Los pedidos nuevos comenzarán su numeración secuencial a partir de este valor. Esto es útil si está migrando de otro sistema o desea reiniciar la numeración.
  - **Valor recomendado:** 1 (para un nuevo comienzo) o un número más alto si necesita continuar una secuencia.
  - **Escenario / ejemplo del comerciante:** Si anteriormente tenía 1000 pedidos y desea que sus nuevas referencias personalizadas comiencen desde 1001, establezca este valor en 1001.
- **Límite de Longitud de Referencia:**

  - **Qué hace esta configuración:** PrestaShop tiene un límite predeterminado para la longitud de la referencia del pedido. Esto le permite definir una longitud máxima para sus referencias generadas. Si una referencia excede esto, se truncará.
  - **Efecto de cambiar esta configuración:** Asegura que sus referencias se ajusten a las restricciones de la base de datos y se muestren correctamente en todas las áreas de PrestaShop.
  - **Valor recomendado:** 9 (el valor predeterminado de PrestaShop suele ser 9, pero puede aumentarlo si su tema/base de datos lo admite, hasta 32 caracteres es generalmente seguro).
  - **Escenario / ejemplo del comerciante:** Si su patrón `MITIENDA-{DATE:YMD}-{ID_ORDER}` da como resultado `MITIENDA-20231027-12345` (21 caracteres), y establece el límite en 9, podría convertirse en `MITIENDA-2`. Tenga en cuenta el truncamiento.
- **Referencia de Vista Previa:**

  - **Qué hace esta configuración:** Este es un campo de utilidad que le permite probar su `Patrón de Referencia Predeterminado` con un ID de pedido ficticio para ver cómo se vería la referencia generada.
  - **Efecto de cambiar esta configuración:** No tiene un efecto directo en su tienda, es puramente una herramienta de prueba.
  - **Valor recomendado:** Úselo con frecuencia al diseñar sus patrones.
  - **Escenario / ejemplo del comerciante:** Ingrese `12345` como un ID de pedido ficticio y haga clic en "Generar Vista Previa" para ver cómo se vería `MITIENDA-{DATE:YMD}-{ID_ORDER}`.

#### **Pestaña de Reglas**

Esta pestaña es donde define condiciones específicas bajo las cuales se deben aplicar diferentes patrones de referencia de pedido, anulando el patrón predeterminado. Las reglas se procesan de arriba a abajo, y se aplica la primera regla que coincide.

- **Añadir Nueva Regla / Editar Regla:**

  - **Qué hace esto:** Le permite crear una nueva regla o modificar una existente. Cada regla consta de:
    - **Nombre de la Regla:** Un nombre descriptivo para su referencia interna (por ejemplo, "Pedidos de Alto Valor", "Clientes Franceses").
    - **Patrón de la Regla:** El patrón de referencia personalizado a usar si esta regla coincide (los mismos códigos cortos que el patrón predeterminado).
    - **Condiciones:** Uno o más criterios que deben cumplirse para que esta regla se aplique.
  - **Efecto de cambiar esta configuración:** Añade o modifica un patrón de referencia condicional.
  - **Valor recomendado:** Cree reglas para sus segmentos de negocio más importantes.
  - **Escenario / ejemplo del comerciante:**
    - **Regla 1: Pedidos de Alto Valor**
      - **Patrón:** `VIP-{ID_ORDER}-{DATE:YMD}`
      - **Condición:** `Total del Carrito` es `mayor que` `500`
      - **Efecto:** Cualquier pedido superior a 500 € obtendrá una referencia como `VIP-12345-20231027`.
    - **Regla 2: Clientes Franceses**
      - **Patrón:** `FR-{ID_ORDER}`
      - **Condición:** `País de Entrega` es `Francia`
      - **Efecto:** Los pedidos con envío a Francia obtendrán `FR-12345`.
    - **Regla 3: Pedidos de Productos Específicos**
      - **Patrón:** `PROD-XYZ-{ID_ORDER}`
      - **Condición:** `Producto en el Carrito` es `Nombre del Producto XYZ`
      - **Efecto:** Los pedidos que contengan "Nombre del Producto XYZ" obtendrán `PROD-XYZ-12345`.
- **Condiciones de la Regla (para cada regla):**

  - **Qué hace esto:** Define los criterios para que una regla esté activa. Puede combinar múltiples condiciones usando la lógica "Y".
  - **Condiciones Disponibles:**
    - **Total del Carrito:** Basado en el valor total del pedido.
    - **Grupo de Clientes:** Basado en el grupo al que pertenece el cliente (por ejemplo, Visitantes, Clientes, Invitados o grupos personalizados).
    - **País de Entrega:** Basado en el país de la dirección de envío.
    - **Método de Pago:** Basado en el módulo de pago utilizado (por ejemplo, Transferencia Bancaria, PayPal).
    - **Producto en el Carrito:** Basado en si un producto específico (por ID o nombre) está presente en el pedido.
    - **Transportista:** Basado en el transportista elegido.
  - **Efecto de cambiar esta configuración:** Determina cuándo se utiliza un patrón de referencia personalizado específico.
  - **Valor recomendado:** Utilice condiciones que segmenten claramente sus pedidos.
  - **Escenario / ejemplo del comerciante:** Una regla para "Clientes Mayoristas" podría usar `Grupo de Clientes es Mayorista`. Una regla para "Envío Exprés" podría usar `Transportista es DHL Express`.

#### **Pestaña de Configuración Avanzada**

Esta pestaña contiene configuraciones para aspectos más técnicos y de mantenimiento.

- **Copia de Seguridad / Restauración JSON:**

  - **Qué hace esto:** Le permite exportar la configuración de su módulo (patrones, reglas) a un archivo JSON o importar una configuración guardada previamente.
  - **Efecto de cambiar esta configuración:**
    - *Copia de seguridad:* Crea un archivo descargable de su configuración.
    - *Restaurar:* Sobrescribe la configuración actual con la del archivo JSON cargado.
  - **Valor recomendado:** Siempre haga una copia de seguridad de su configuración antes de realizar cambios importantes o actualizar su tienda PrestaShop.
  - **Escenario / ejemplo del comerciante:** Antes de actualizar PrestaShop o mover su tienda a un nuevo servidor, descargue una copia de seguridad de sus reglas de referencia personalizadas. Si comete un error con una regla, puede restaurar fácilmente una versión anterior.
- **Restablecer Configuración del Módulo:**

  - **Qué hace esto:** Elimina todos los patrones y reglas personalizados, revirtiendo el módulo a su estado predeterminado, recién instalado.
  - **Efecto de cambiar esta configuración:** Se perderán todos sus patrones y reglas de referencia personalizados.
  - **Valor recomendado:** Úselo con extrema precaución, solo si desea comenzar completamente de nuevo.
  - **Escenario / ejemplo del comerciante:** Si sus reglas se han vuelto demasiado complejas o están causando problemas, y desea comenzar desde cero, puede usar esto. ¡Siempre haga una copia de seguridad primero!

#### **Tabla de Referencia Rápida de Configuración**

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración General** | Habilitar Generación de Referencias de Pedido Personalizadas | SÍ | Activa/desactiva la lógica de referencia personalizada del módulo. |
|  | Patrón de Referencia Predeterminado | `PED-{RAND:6}` (ejemplo) | Define el formato de referencia de respaldo cuando no coinciden reglas. |
|  | Valor Inicial del Contador Secuencial | 1 | Establece el número inicial para `{ID_ORDER}` en nuevas referencias. |
|  | Límite de Longitud de Referencia | 9 (o más si es seguro) | Limita la longitud máxima de las referencias generadas para evitar problemas. |
|  | Referencia de Vista Previa | (N/A) | Herramienta para probar su patrón con un ID de pedido ficticio. |
| **Pestaña de Reglas** | Añadir/Editar Regla | N/A | Crea patrones de referencia condicionales basados en criterios. |
|  | Nombre de la Regla | Descriptivo (ej., "Pedidos de Alto Valor") | Etiqueta interna para la regla. |
|  | Patrón de la Regla | Personalizado (ej., `VIP-{ID_ORDER}`) | El formato de referencia para esta regla específica. |
|  | Condiciones de la Regla | Varía (ej., `Total del Carrito > 500`) | Criterios que deben cumplirse para que la regla se aplique. |
| **Configuración Avanzada** | Copia de Seguridad / Restauración JSON | N/A | Exporta/importa la configuración del módulo por seguridad o migración. |
|  | Restablecer Configuración del Módulo | N/A | Elimina todas las configuraciones y reglas del módulo. Usar con extrema precaución. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mis referencias personalizadas no aparecen, o sigo viendo las referencias predeterminadas de PrestaShop.**
R1: Primero, asegúrese de que el módulo esté **habilitado** en la pestaña "Configuración General". Además, verifique si ha vaciado la caché de PrestaShop (Parámetros Avanzados > Rendimiento > Vaciar Caché). Si tiene reglas específicas, asegúrese de que se cumplan sus condiciones y de que las reglas estén ordenadas correctamente (se aplica la primera regla que coincide).

**P2: Mis referencias personalizadas son demasiado largas o se están cortando.**
R2: Verifique el "Límite de Longitud de Referencia" en la pestaña "Configuración General". PrestaShop tiene un límite predeterminado (a menudo 9 caracteres) para las referencias de pedido en su base de datos. Si su patrón personalizado genera referencias más largas, es posible que deba aumentar este límite. Tenga precaución, ya que aumentarlo demasiado podría causar problemas de visualización en algunos temas o versiones antiguas de PrestaShop. Generalmente es seguro llegar hasta 32 caracteres. Si necesita más, consulte a un desarrollador.

**P3: Cometí un error con mis reglas y ahora mis referencias son incorrectas. ¿Cómo lo soluciono?**
R3: Si tiene una copia de seguridad JSON reciente (de la pestaña "Configuración Avanzada"), puede restaurarla. De lo contrario, deberá editar o eliminar manualmente las reglas problemáticas. Si desea comenzar completamente de nuevo, use la opción "Restablecer Configuración del Módulo", pero tenga en cuenta que esto eliminará *todos* sus patrones y reglas personalizados.

**P4: ¿Puedo usar este módulo con varias tiendas (configuración multitienda)?**
R4: Sí, el módulo está diseñado para ser compatible con la función multitienda de PrestaShop. Puede configurar diferentes patrones y reglas de referencia para cada tienda desde la página de configuración del módulo, seleccionando el contexto de tienda específico en el back office de PrestaShop.

**P5: ¿Qué sucede con los pedidos existentes cuando cambio el patrón de referencia?**
R5: Cambiar el patrón de referencia o las reglas solo afecta a los *nuevos* pedidos realizados después del cambio. Los pedidos existentes conservarán sus referencias de pedido originales. El módulo no modifica retroactivamente los datos de pedidos anteriores.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Generador de Referencias de Pedido Personalizadas Pro" extiende principalmente la clase `Order` central de PrestaShop a través de una anulación para interceptar y modificar el proceso de generación de referencias de pedido. Sigue un enfoque basado en eventos donde el módulo se engancha al ciclo de vida de creación de pedidos. La configuración se gestiona a través de un método `getContent()` estándar en el archivo principal del módulo, almacenando la configuración en `ps_configuration` y las reglas personalizadas en sus propias tablas de base de datos (aunque no se enumeran archivos SQL específicos, esto implica la creación dinámica de tablas o el almacenamiento de la configuración). El módulo utiliza un `RulesEngine` para evaluar las condiciones y un `ReferenceGenerator` para construir la referencia final basándose en patrones y códigos cortos definidos.

### 4.2 Controladores (`controllers/`)

Este módulo no parece utilizar controladores personalizados de front-office o back-office. Toda la configuración se maneja dentro del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Centrales (`classes/`)

- `refchangepro/classes/PayloadFactory.php`

  - **Nombre de la Clase:** `PayloadFactory`
  - **Clase Padre:** Ninguna (probablemente una clase de utilidad)
  - **Responsabilidad:** Responsable de crear una carga útil de datos (contexto) que el `RulesEngine` y el `ReferenceGenerator` puedan usar. Esta carga útil contendría información sobre el pedido actual que se está procesando (por ejemplo, total del carrito, ID del cliente, país de entrega, productos). Actúa como una capa de abstracción para recopilar todos los datos necesarios para la evaluación de reglas y la generación de referencias.
- `refchangepro/classes/ReferenceContext.php`

  - **Nombre de la Clase:** `ReferenceContext`
  - **Clase Padre:** Ninguna (probablemente un objeto de transferencia de datos o un objeto de valor)
  - **Responsabilidad:** Una clase simple para contener y gestionar los datos contextuales (por ejemplo, ID de pedido, detalles del cliente, detalles del carrito) que se pasan durante el proceso de generación de referencias. Asegura la coherencia del acceso a los datos para el generador y el motor de reglas.
- `refchangepro/classes/ReferenceGenerator.php`

  - **Nombre de la Clase:** `ReferenceGenerator`
  - **Clase Padre:** Ninguna (probablemente una clase de servicio)
  - **Responsabilidad:** La lógica central para construir la cadena de referencia de pedido final. Toma un patrón (por ejemplo, `MITIENDA-{DATE:YMD}-{ID_ORDER}`) y un objeto `ReferenceContext`, luego reemplaza los códigos cortos con valores reales. Maneja el formato de fecha, la generación de cadenas aleatorias y la inserción de ID secuenciales.
- `refchangepro/classes/RulesEngine.php`

  - **Nombre de la Clase:** `RulesEngine`
  - **Clase Padre:** Ninguna (probablemente una clase de servicio)
  - **Responsabilidad:** Evalúa las reglas definidas contra el contexto del pedido actual. Itera a través de las reglas configuradas, verifica si se cumplen las condiciones (por ejemplo, total del carrito, grupo de clientes, país) y devuelve el patrón de la primera regla que coincide. Si ninguna regla coincide, indica que se debe usar el patrón predeterminado.
- `refchangepro/classes/Runtime.php`

  - **Nombre de la Clase:** `Runtime`
  - **Clase Padre:** Ninguna (probablemente una clase de utilidad o auxiliar)
  - **Responsabilidad:** Podría manejar configuraciones en tiempo de ejecución, almacenamiento en caché u otros aspectos operativos del módulo. Podría ser responsable de cargar reglas desde la configuración, gestionar el contador secuencial o proporcionar métodos de utilidad utilizados en todo el módulo.
- `refchangepro/override/classes/order/Order.php`

  - **Ruta exacta del archivo:** `refchangepro/override/classes/order/Order.php`
  - **Nombre de la Clase:** `Order`
  - **Clase Padre:** `OrderCore` (clase Order central de PrestaShop)
  - **Responsabilidad:** Esta es la anulación crítica. Intercepta el método `generateReference()` (o un método similar responsable de establecer la referencia del pedido) dentro de la clase `Order` central de PrestaShop. Dentro de este método anulado, llama al `RulesEngine` del módulo para determinar el patrón correcto y luego al `ReferenceGenerator` para crear la referencia personalizada, finalmente estableciéndola para el objeto de pedido. Esto asegura que cada nuevo pedido creado utilice la lógica del módulo.

### 4.4 Activos JavaScript (`views/js/`)

- `refchangepro/lib/searchTool/views/js/autocomplete.js`

  - **Alcance:** Probablemente Back-office.
  - **Descripción:** Proporciona funcionalidad de autocompletado, posiblemente para seleccionar productos, clientes u otras entidades al definir reglas. Se vincularía a los campos de entrada, realizaría solicitudes AJAX a un controlador de administración de PrestaShop (o al método `getContent` del módulo) y mostraría sugerencias.
- `refchangepro/views/js/admin-tabs.js`

  - **Alcance:** Back-office.
  - **Descripción:** Gestiona la interfaz con pestañas dentro de la página de configuración del módulo. Vincula eventos de clic a los encabezados de las pestañas, muestra/oculta el contenido de las pestañas correspondientes y podría manejar cambios de hash de URL para enlaces directos a pestañas.
- `refchangepro/views/js/rules-builder.js`

  - **Alcance:** Back-office.
  - **Descripción:** Este es el JavaScript central para la pestaña "Reglas". Maneja la adición, edición y eliminación dinámica de condiciones de reglas. Vincula eventos a los botones "Añadir Condición", gestiona los desplegables para los tipos de condición (por ejemplo, "Total del Carrito", "Grupo de Clientes") y renderiza dinámicamente los campos de entrada según el tipo de condición seleccionado (por ejemplo, entrada numérica para el total del carrito, cuadro de selección para grupos de clientes). Probablemente serializa los datos de la regla en un campo de entrada oculto para su envío.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `refchangepro/lib/searchTool/views/css/autocomplete.css`

  - **Alcance:** Estilo de administración del Back-office.
  - **Descripción:** Estiliza las listas de sugerencias de autocompletado y los campos de entrada, asegurando que sean visualmente consistentes y fáciles de usar dentro del back office de PrestaShop.
- `refchangepro/views/css/admin.css`

  - **Alcance:** Estilo de administración del Back-office.
  - **Descripción:** Proporciona estilo general para la página de configuración del módulo, incluyendo el diseño, la tipografía, los estilos de botones y la presentación visual general para integrarse sin problemas con el tema del back office de PrestaShop.
- `refchangepro/views/css/rules-builder.css`

  - **Alcance:** Estilo de administración del Back-office.
  - **Descripción:** Estilos específicos para la interfaz del constructor de reglas, incluyendo el diseño de bloques de reglas individuales, filas de condiciones y cualquier elemento de arrastrar y soltar o reordenar.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- `refchangepro/lib/searchTool/views/scripts.tpl`
  - **Alcance:** Administración del Back-office.
  - **Descripción:** Esta plantilla probablemente incluye el JavaScript y, potencialmente, el CSS necesarios para la herramienta de búsqueda de autocompletado. Se incluiría en la plantilla de configuración principal del módulo para cargar la funcionalidad de autocompletado.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - La descripción del módulo menciona que "Las reglas inteligentes aplican diferentes patrones por valor de carrito, país, producto o grupo de clientes". Esto implica fuertemente la creación de tablas de base de datos personalizadas para almacenar estas reglas y sus condiciones asociadas.
  - Tablas esperadas (los nombres son ilustrativos, los nombres reales se prefijarían con `ps_` y el nombre del módulo):
    - `ps_refchangepro_rules`: Almacena las definiciones de reglas principales (ID, nombre, patrón, estado activo).
    - `ps_refchangepro_conditions`: Almacena las condiciones individuales para cada regla (ID de regla, tipo de condición, operador, valor).
  - La configuración (como `PS_REFCHANGEPRO_ENABLED`, `PS_REFCHANGEPRO_DEFAULT_PATTERN`, `PS_REFCHANGEPRO_COUNTER_START`) se almacena en la tabla `ps_configuration` de PrestaShop.
  - El contador secuencial para `{ID_ORDER}` podría almacenarse en `ps_configuration` o en una tabla dedicada para un bloqueo más robusto.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionOrderAdd` / `actionObjectOrderAddAfter` | Después de que se crea un nuevo objeto de pedido en la base de datos. | La anulación del módulo de `Order::generateReference()` es el mecanismo principal. Sin embargo, si el módulo necesita realizar acciones adicionales *después* de que el pedido se haya guardado completamente con su nueva referencia, se usarían estos hooks. Por ejemplo, para registrar la referencia generada o actualizar un contador personalizado. |
| `displayBackOfficeHeader` | En la sección `<head>` del Back Office. | Se utiliza para cargar CSS (`admin.css`, `rules-builder.css`, `autocomplete.css`) y JavaScript (`admin-tabs.js`, `rules-builder.js`, `autocomplete.js`) específicos del módulo para la página de configuración. |
| `displayAdminProductsExtra` / `displayAdminCustomers` (Hipotético) | En las páginas de edición de productos o clientes en el Back Office. | Si el módulo ofreciera configuraciones de referencia específicas por producto o cliente, se engancharía aquí para mostrar esas opciones. (No se indica explícitamente, pero es común para las versiones "Pro"). |
| `displayModuleConfigure` (Interno) | Cuando se carga la página de configuración del módulo. | El método `getContent()` del archivo principal del módulo se engancha implícitamente aquí para renderizar el formulario de configuración. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico e información adicional sobre el módulo "Generador de Referencias de Pedido Personalizadas Pro", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier pregunta o problema.

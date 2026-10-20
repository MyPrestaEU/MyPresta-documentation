---
title: "Experiencia del Cliente - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Experiencia del Cliente de PrestaShop por MyPresta.eu."
sidebar:
  label: "Experiencia del Cliente - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Customers Expertise en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/customers-expertise.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/customers-expertise/)
>
> ---


# Experiencia del Cliente

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y normalmente están presentes en cualquier entorno de alojamiento moderno. No hay requisitos de alojamiento especiales más allá de una configuración estándar de PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Experiencia del Cliente)

Esta es la pantalla de configuración principal donde define sus logros, sus criterios y las recompensas. La configuración del módulo se gestiona a través de una interfaz dedicada que le permite añadir, editar y eliminar logros.

**Nombre de la Pantalla y Ubicación del Menú:**
Puede acceder a esta pantalla navegando a **Módulos > Gestor de Módulos**, buscando "Experiencia del Cliente" y haciendo clic en el botón "Configurar".

**Acciones y Ajustes Disponibles:**
La página de configuración presentará una lista de sus logros actualmente definidos. Normalmente encontrará opciones para:

- **Añadir Nuevo Logro:** Un botón o enlace para crear un nuevo logro.
- **Editar Logro Existente:** Un icono (por ejemplo, lápiz) junto a cada logro en la lista para modificar sus ajustes.
- **Eliminar Logro:** Un icono (por ejemplo, papelera) junto a cada logro para eliminarlo.

Al añadir o editar un logro, normalmente encontrará los siguientes ajustes:

#### **Detalles del Logro**

- **Nombre del Logro:**

  - **Qué hace este ajuste:** Este es el título del logro que verán sus clientes (por ejemplo, "Comprador por Primera Vez", "Maestro de Reseñas", "Comprador VIP").
  - **Efecto de cambiar este ajuste:** Este nombre se muestra en la sección "Mis Logros" del cliente. Un nombre claro y atractivo fomenta la interacción.
  - **Valor recomendado:** Algo descriptivo y motivador.
  - **Escenario / ejemplo del comerciante:** "Héroe del Primer Pedido" para la primera compra de un cliente.
- **Descripción del Logro:**

  - **Qué hace este ajuste:** Una breve explicación de qué trata el logro y cómo obtenerlo. Esto ayuda a los clientes a entender el objetivo.
  - **Efecto de cambiar este ajuste:** Esta descripción aparece junto al nombre. Una buena descripción aclara los criterios del logro.
  - **Valor recomendado:** Conciso y alentador.
  - **Escenario / ejemplo del comerciante:** "¡Realiza tu primera compra en nuestra tienda para ganar esta insignia!"
- **Imagen/Icono del Logro:**

  - **Qué hace este ajuste:** Le permite subir una representación visual (insignia, icono) para el logro.
  - **Efecto de cambiar este ajuste:** Esta imagen se muestra junto al nombre del logro, haciéndolo visualmente atractivo y reconocible.
  - **Valor recomendado:** Una imagen única y de alta calidad que refleje el tema del logro.
  - **Escenario / ejemplo del comerciante:** Un icono de "estrella" para un logro de "Mejor Reseñador".
- **Activo / Habilitado:**

  - **Qué hace este ajuste:** Un interruptor para habilitar o deshabilitar el logro.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El logro está activo, los clientes pueden obtenerlo y aparecerá en su lista de logros.
    - *Cuando está deshabilitado:* El logro está oculto, los clientes no pueden obtenerlo y no aparecerá en el front office. Útil para logros estacionales o aquellos que aún está preparando.
  - **Valor recomendado:** SÍ para logros activos.
  - **Escenario / ejemplo del comerciante:** Deshabilitar un logro de "Comprador de Navidad" después de la temporada navideña.

#### **Criterios del Logro (Cómo Obtenerlo)**

Esta es la parte central del módulo, donde define las condiciones que un cliente debe cumplir. El módulo probablemente ofrece varios tipos de criterios. Ejemplos comunes incluyen:

- **Número de Pedidos:**

  - **Qué hace este ajuste:** El cliente debe realizar un número específico de pedidos.
  - **Efecto de cambiar este ajuste:** Determina cuántos pedidos exitosos se requieren.
  - **Valor recomendado:** Comience con números bajos para los logros iniciales (por ejemplo, 1, 3) y aumente para niveles superiores.
  - **Escenario / ejemplo del comerciante:** Establecer en "1" para "Comprador por Primera Vez", "5" para "Cliente Leal".
- **Cantidad Total Gastada:**

  - **Qué hace este ajuste:** El gasto acumulado del cliente en todos los pedidos debe alcanzar una cierta cantidad.
  - **Efecto de cambiar este ajuste:** Define el umbral monetario.
  - **Valor recomendado:** Adapte a su valor promedio de pedido y segmentos de clientes.
  - **Escenario / ejemplo del comerciante:** Establecer en "€100" para "Gastador Bronce", "€500" para "Gastador Plata".
- **Número de Productos Comprados:**

  - **Qué hace este ajuste:** El cliente debe comprar una cantidad total específica de productos (en todos los pedidos).
  - **Efecto de cambiar este ajuste:** Establece el umbral de cantidad.
  - **Valor recomendado:** Útil para fomentar compras al por mayor o probar diferentes productos.
  - **Escenario / ejemplo del comerciante:** Establecer en "10" para "Coleccionista de Productos".
- **Número de Reseñas de Productos:**

  - **Qué hace este ajuste:** El cliente debe enviar un cierto número de reseñas de productos aprobadas.
  - **Efecto de cambiar este ajuste:** Fomenta el contenido generado por el usuario y la prueba social.
  - **Valor recomendado:** Establecer en "1" para "Primer Reseñador", "5" para "Maestro de Reseñas".
  - **Escenario / ejemplo del comerciante:** Recompense a los clientes por contribuir con comentarios valiosos.
- **Compra de Producto/Categoría Específica:**

  - **Qué hace este ajuste:** El cliente debe comprar un producto de una categoría específica o un producto específico.
  - **Efecto de cambiar este ajuste:** Promueve artículos o categorías específicas.
  - **Valor recomendado:** Utilizar para lanzamientos de nuevos productos o inventario de baja rotación.
  - **Escenario / ejemplo del comerciante:** "Compró un artículo de nueva colección" por comprar en una categoría de "Novedades".

#### **Recompensa del Logro (Vale de Descuento)**

- **Tipo de Vale:**

  - **Qué hace este ajuste:** Define el tipo de código de descuento que recibe el cliente (por ejemplo, porcentaje, cantidad fija, envío gratuito).
  - **Efecto de cambiar este ajuste:** Determina la naturaleza de la recompensa.
  - **Valor recomendado:** Los descuentos porcentuales suelen ser populares, pero las cantidades fijas pueden ser buenas para compras más pequeñas.
  - **Escenario / ejemplo del comerciante:** "Descuento porcentual" para un 10% de descuento en el próximo pedido.
- **Valor del Vale:**

  - **Qué hace este ajuste:** El valor real del descuento (por ejemplo, "10" para 10%, "€5" para una cantidad fija).
  - **Efecto de cambiar este ajuste:** Impacta directamente el incentivo para el cliente.
  - **Valor recomendado:** Equilibre la generosidad con sus márgenes de beneficio.
  - **Escenario / ejemplo del comerciante:** "15" para un 15% de descuento.
- **Período de Validez del Vale (Días):**

  - **Qué hace este ajuste:** Cuántos días es válido el vale generado desde el momento en que el cliente lo reclama.
  - **Efecto de cambiar este ajuste:** Crea urgencia para que el cliente use el vale.
  - **Valor recomendado:** 7-30 días es común. Demasiado corto puede frustrar, demasiado largo reduce la urgencia.
  - **Escenario / ejemplo del comerciante:** Establecer en "14" días para fomentar una compra repetida rápida.
- **Importe Mínimo del Pedido para el Vale:**

  - **Qué hace este ajuste:** Si el vale requiere un valor mínimo de compra para ser utilizado.
  - **Efecto de cambiar este ajuste:** Ayuda a proteger sus márgenes y anima a los clientes a gastar más.
  - **Valor recomendado:** Establezca un mínimo razonable que fomente una venta adicional sin ser prohibitivo.
  - **Escenario / ejemplo del comerciante:** "€30" de pedido mínimo para un descuento de €5.
- **Prefijo del Vale:**

  - **Qué hace este ajuste:** Un prefijo personalizado para los códigos de descuento generados (por ejemplo, "LOGRO-", "INSIGNIA-").
  - **Efecto de cambiar este ajuste:** Le ayuda a identificar la fuente de los códigos de descuento en sus informes de ventas de PrestaShop.
  - **Valor recomendado:** Un prefijo corto y memorable.
  - **Escenario / ejemplo del comerciante:** "EXPERTO-" para saber que el vale proviene del módulo Experiencia del Cliente.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1. **Planifique sus logros:** Antes de crear, decida qué comportamientos desea recompensar y cuántos niveles de logros desea.
2. **Empiece de forma sencilla:** Comience con 2-3 logros básicos (por ejemplo, primer pedido, gasto total, número de reseñas) para probar.
3. **Cree cada logro:** Siga el proceso de "Añadir Nuevo Logro", definiendo cuidadosamente los criterios y las recompensas.
4. **Supervise la interacción del cliente:** Revise sus ventas y cuentas de clientes para ver cómo interactúan los clientes con los logros.
5. **Ajuste y expanda:** Basándose en el rendimiento, refine los logros existentes o introduzca otros nuevos y más complejos.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de Configuración del Módulo** | Nombre del Logro | Descriptivo | Título mostrado al cliente. |
|  | Descripción del Logro | Informativo | Explica cómo obtener el logro. |
|  | Imagen/Icono del Logro | Imagen única | Representación visual de la insignia. |
|  | Activo / Habilitado | SÍ | Alterna la visibilidad y elegibilidad del logro. |
|  | **Criterios: Número de Pedidos** | 1, 3, 5 | El cliente debe realizar X pedidos. |
|  | **Criterios: Cantidad Total Gastada** | €50, €100, €500 | El gasto total del cliente debe alcanzar X. |
|  | **Criterios: Número de Productos Comprados** | 5, 10, 20 | El cliente debe comprar X productos en total. |
|  | **Criterios: Número de Reseñas de Productos** | 1, 3, 5 | El cliente debe enviar X reseñas aprobadas. |
|  | **Criterios: Compra de Producto/Categoría Específica** | (Seleccionar producto/categoría) | El cliente debe comprar de un producto/categoría específica. |
|  | **Recompensa: Tipo de Vale** | Porcentaje | Tipo de descuento (%, fijo, envío gratuito). |
|  | **Recompensa: Valor del Vale** | 10 (para %) | La cantidad del descuento. |
|  | **Recompensa: Período de Validez del Vale (Días)** | 14-30 | Cuánto tiempo es válido el vale después de reclamarlo. |
|  | **Recompensa: Importe Mínimo del Pedido para el Vale** | (Opcional) | Valor mínimo del carrito requerido para usar el vale. |
|  | **Recompensa: Prefijo del Vale** | EXPERTO- | Prefijo personalizado para los códigos de descuento generados. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Mis clientes no ven la sección de logros en su cuenta.**
R: Primero, asegúrese de que el módulo "Experiencia del Cliente" esté instalado y habilitado en su Back Office. Verifique la configuración del módulo para asegurarse de que tiene al menos un logro creado y configurado como "Activo". Además, verifique que el archivo `customer-account.tpl` de su tema (o equivalente) esté correctamente enganchado para mostrar el enlace del módulo. Si tiene un tema personalizado, es posible que necesite un webmaster para asegurarse de que el hook se renderice.

**P: Los clientes están obteniendo logros pero no reciben códigos de descuento.**
R: Vaya a la configuración del módulo y edite el logro específico. Verifique que un "Tipo de Vale" y un "Valor del Vale" estén correctamente definidos para la recompensa. Asegúrese de que no haya errores tipográficos o configuraciones incorrectas en los parámetros del vale. Además, verifique sus "Reglas del Carrito" de PrestaShop (o "Descuentos" en versiones anteriores) para ver si los vales generados aparecen allí.

**P: Las imágenes de los logros no se muestran correctamente.**
R: Esto generalmente indica un problema con la carga de la imagen o los permisos de archivo. Asegúrese de que el archivo de imagen que subió sea un formato web estándar (JPG, PNG, GIF) y no demasiado grande. Verifique los permisos de archivo de su servidor para el directorio de imágenes del módulo (por ejemplo, `modules/customersexpertise/img/`) para asegurarse de que PrestaShop pueda escribir y leer archivos allí. Borrar la caché de PrestaShop (Parámetros Avanzados > Rendimiento) también puede ayudar.

**P: ¿Puedo traducir los nombres y descripciones de los logros a varios idiomas?**
R: Sí, como la mayoría de los módulos de PrestaShop, los campos de texto para los nombres y descripciones de los logros deben admitir la entrada en varios idiomas. Al editar un logro, busque las banderas de idioma junto a los campos de entrada, lo que le permite proporcionar traducciones para cada idioma instalado en su tienda.

**P: ¿Qué sucede si un cliente obtiene un logro pero luego lo desactivo?**
R: Si un logro se desactiva, los nuevos clientes ya no podrán obtenerlo y, por lo general, se ocultará del front office. Los clientes que ya lo hayan obtenido generalmente conservarán su estado de logro y cualquier vale asociado que hayan reclamado antes de que el logro fuera deshabilitado. Sin embargo, no podrán volver a reclamar vales si el logro se vuelve a habilitar y ya tienen uno.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo Experiencia del Cliente.

### 4.1 Descripción General de la Arquitectura

El módulo Experiencia del Cliente sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente los controladores frontales para las interacciones con el cliente y la clase principal del módulo para la configuración y la gestión de hooks. Integra la lógica de gamificación al rastrear las acciones del cliente (pedidos, reseñas) y generar dinámicamente objetos `CartRule` (vale) de PrestaShop como recompensas. La lógica central del módulo reside en su archivo PHP principal y en los controladores frontales dedicados, con plantillas Smarty que manejan la capa de presentación.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

Estos controladores manejan la lógica y la visualización orientadas al cliente para los logros y las características relacionadas.

- `controllers/front/achievements.php`

  - **Nombre de la clase y clase padre:** `CustomersExpertiseAchievementsModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este es el controlador principal para mostrar los logros de un cliente. Recupera todos los logros definidos, verifica la elegibilidad del cliente actual y el estado de obtención de cada uno, y prepara los datos para la plantilla `achievements.tpl`. Probablemente maneja la lógica para reclamar vales una vez que se obtiene un logro.
  - **Rutas:** Normalmente se accede a través de una URL como `sutenda.com/module/customersexpertise/achievements`.
- `controllers/front/affiliationlink.php`

  - **Nombre de la clase y clase padre:** `CustomersExpertiseAffiliationlinkModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Aunque la descripción del módulo no menciona explícitamente la afiliación, este controlador sugiere una característica potencial para que los clientes generen y administren enlaces de afiliación, posiblemente como una recompensa de logro o una característica independiente. Manejaría la visualización y generación de dichos enlaces.
  - **Rutas:** Probablemente `sutenda.com/module/customersexpertise/affiliationlink`.
- `controllers/front/index.php`

  - **Nombre de la clase y clase padre:** `CustomersExpertiseIndexModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** A menudo sirve como controlador frontal predeterminado o de respaldo. Podría redirigir al controlador `achievements` o mostrar una página de inicio general para el módulo si no se solicita ninguna acción específica.
  - **Rutas:** `sutenda.com/module/customersexpertise/index` o `sutenda.com/module/customersexpertise`.
- `controllers/front/voucher.php`

  - **Nombre de la clase y clase padre:** `CustomersExpertiseVoucherModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador es probablemente responsable del proceso real de generar y asignar un vale de descuento a un cliente una vez que reclama un logro obtenido. Interactuaría con el objeto `CartRule` de PrestaShop para crear el vale y potencialmente actualizar el estado de logro del cliente.
  - **Rutas:** Podría ser un endpoint AJAX o una URL directa para reclamar vales, por ejemplo, `sutenda.com/module/customersexpertise/voucher`.

#### Controladores de Administración del Back-Office

El módulo no parece tener controladores de administración personalizados dedicados. La configuración se maneja a través del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

El inventario proporcionado no indica clases personalizadas dentro del directorio `classes/`. Esto sugiere que la lógica central del módulo, las definiciones de logros y el seguimiento del cliente probablemente se gestionan directamente dentro del archivo principal del módulo (`ajax_customersexpertise.php`) y potencialmente aprovechando las clases `ObjectModel` existentes de PrestaShop como `Customer`, `Order`, `Product` y `CartRule`.

El módulo gestionaría internamente los datos de los logros, posiblemente mediante:

- Almacenamiento de las definiciones de logros (nombre, descripción, criterios, recompensa) en la tabla `ps_configuration` como arrays serializados o JSON.
- Almacenamiento del estado de logro del cliente (obtenido, vale reclamado) en una tabla personalizada creada durante la instalación o también dentro de los campos meta de `ps_configuration` o `ps_customer`.

### 4.4 Activos JavaScript (`views/js/`)

- `customersexpertise/lib/voucherengine/script.js`
  - **Ámbito:** Probablemente Front-office.
  - **Detalles:** Este script es probablemente responsable de mejorar la experiencia del usuario en la página de logros del cliente. Podría manejar:
    - Solicitudes AJAX para reclamar vales (por ejemplo, cuando un cliente hace clic en un botón "Reclamar Vale").
    - Actualizaciones dinámicas de la página después de que se reclama un vale (por ejemplo, mostrando el código del vale, marcando el logro como reclamado).
    - Validación del lado del cliente o elementos interactivos relacionados con las características de gamificación.
    - Potencialmente, podría interactuar con el controlador frontal `voucher.php`.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `customersexpertise/css/customersexpertise.css`

  - **Ámbito:** Estilo del cliente del Front-office.
  - **Detalles:** Esta es la hoja de estilo principal para los componentes del front-office del módulo. Define la apariencia visual de la lista de logros, las tarjetas de logros individuales, la visualización de vales y cualquier otro elemento de la interfaz de usuario presentado al cliente.
  - **Selectores de clase CSS clave:** Los desarrolladores pueden esperar clases como `.customersexpertise-achievements`, `.achievement-item`, `.achievement-badge`, `.voucher-code`, etc., que se pueden anular en el `custom.css` o `theme.css` de un tema personalizado para que coincidan con la marca de la tienda.
- `customersexpertise/lib/voucherengine/ps16.css`

  - **Ámbito:** Estilo del cliente del Front-office, específicamente para la compatibilidad con PrestaShop 1.6.
  - **Detalles:** Esta hoja de estilo probablemente contiene anulaciones específicas o estilos adicionales para garantizar que la visualización del front-office del módulo sea correcta y visualmente consistente con los temas de PrestaShop 1.6. Podría abordar diferencias de diseño o estilos de elementos específicos que cambiaron entre las versiones de PrestaShop. Para versiones más nuevas de PrestaShop (1.7, 8.x, 9.x), este archivo podría cargarse condicionalmente o sus estilos podrían ser menos relevantes, dependiendo más de `customersexpertise.css`.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas del Front-office (`views/templates/front/`)**:

  - `customersexpertise/views/templates/front/achievements.tpl`
    - **Propósito:** Esta es la plantilla principal para mostrar la página de logros del cliente. Itera a través de los datos de logros pasados desde el controlador `achievements.php`, mostrando insignias obtenidas, criterios para las no obtenidas y opciones para reclamar vales.
  - `customersexpertise/views/templates/front/affiliation-link.tpl`
    - **Propósito:** Si el controlador `affiliationlink.php` está activo, esta plantilla renderizaría la interfaz para que los clientes vean o generen sus enlaces de afiliación.
  - `customersexpertise/views/templates/front/voucher.tpl`
    - **Propósito:** Esta plantilla podría usarse para mostrar un solo código de vale o un mensaje de confirmación después de que se haya reclamado un vale, potencialmente como parte de una respuesta AJAX o una página dedicada.
- **Plantillas de Hook (`views/templates/hook/`)**:

  - `customersexpertise/views/templates/hook/customer-account.tpl`
    - **Hook:** `displayCustomerAccount` (o similar, dependiendo de la versión de PrestaShop).
    - **Propósito:** Esta plantilla renderiza el enlace o bloque que aparece en el panel de "Mi Cuenta" del cliente, dirigiéndolos a la página "Mis Logros". Es crucial para la detectabilidad de las características del módulo por parte del cliente.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:
  La descripción del módulo y el inventario de archivos no enumeran explícitamente archivos SQL personalizados para la creación de tablas. Esto sugiere que el módulo podría almacenar sus datos de una de las siguientes maneras:

  - **`ps_configuration`**: Las definiciones de logros (criterios, recompensas) podrían almacenarse como arrays serializados o cadenas JSON en la tabla `ps_configuration`, utilizando claves de configuración únicas (por ejemplo, `CUSTOMERS_EXPERTISE_ACHIEVEMENTS`).
  - **Tablas existentes de PrestaShop**: El estado de logro del cliente (qué logros ha obtenido, qué vales ha reclamado) podría almacenarse en un campo personalizado añadido a las tablas `ps_customer` o `ps_customer_group`, o en una tabla personalizada creada dinámicamente por el método `install()` del módulo sin un archivo `.sql` dedicado.
  - **`ps_cart_rule`**: El módulo interactúa directamente con el sistema `CartRule` (vale de descuento) de PrestaShop para generar recompensas.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de todas las páginas del front-office. | Para incluir activos CSS y JavaScript globalmente, o para añadir metaetiquetas. |
| `displayLeftColumn` / `displayRightColumn` | En la columna izquierda/derecha de las páginas del front-office. | Para mostrar un pequeño bloque promocional o un enlace a la página de logros. |
| `displayProductButtons` / `displayProductExtraContent` (o hooks similares de la página de producto) | En la página del producto. | Potencialmente para rastrear vistas/compras de productos para criterios de logros, o para insinuar la gamificación. |
| `displayFooter` | En el pie de página de todas las páginas del front-office. | Para mostrar un enlace a la página de logros o una promoción general de gamificación. |
| `displayCustomerAccount` | En el panel de "Mi Cuenta" del cliente. | **CRÍTICO:** Para añadir el enlace "Mis Logros" para los clientes. |
| `actionValidateOrder` | Después de que el pedido de un cliente ha sido validado con éxito. | **CRÍTICO:** Para verificar si el pedido cumple con algún criterio de logro (por ejemplo, primer pedido, gasto total, compra de producto) y otorgar logros. |
| `actionObjectProductAddAfter` / `actionObjectProductUpdateAfter` | Después de que se añade o actualiza un producto. | Menos probable, pero podría usarse para actualizar los criterios de logros si se relacionan con atributos del producto. |
| `actionObjectCustomerAddAfter` | Después de que un nuevo cliente se registra. | Para inicializar el seguimiento de logros para nuevos clientes. |
| `actionObjectReviewAddAfter` (o similar para módulos de reseñas) | Después de que un cliente envía una reseña de producto. | **CRÍTICO:** Para verificar si la reseña cumple con algún criterio de logro (por ejemplo, número de reseñas). |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo Experiencia del Cliente, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar que el módulo funcione de manera óptima con su tienda PrestaShop.
"""

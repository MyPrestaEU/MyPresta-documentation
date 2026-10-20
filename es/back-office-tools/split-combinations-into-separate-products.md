---
title: "Dividir combinaciones en productos separados - Manual del Comerciante y Guía de Configuración"
description: ""
sidebar:
  label: "Dividir combinaciones en productos separados - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Split combinations into separate products en MyPresta.eu](https://mypresta.eu/modules/administration-tools/split-combinations-into-separate-products.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/split-combinations-into-separate-products/)
>
> ---


# Dividir combinaciones en productos separados

## 1. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 1.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo, a la que se accede haciendo clic en "Configurar" después de la instalación.

#### Ajustes generales

-   **Activar módulo:**

    -   **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar la funcionalidad del módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Las características del módulo, incluida la capacidad de dividir productos y su lógica de visualización, se activan.
        -   *Cuando está desactivado:* La funcionalidad del módulo se desactiva por completo. No se dividirán combinaciones, y cualquier producto dividido existente volverá a su estado original o se gestionará como productos regulares, dependiendo de la lógica interna del módulo.
    -   **Valor recomendado:** SÍ (una vez que esté listo para usar el módulo).
    -   **Escenario / ejemplo del comerciante:** Está configurando el módulo por primera vez y quiere probarlo. Lo activa para ver sus efectos. Si necesita desactivarlo temporalmente para mantenimiento, puede apagarlo.
-   **Modo de división:**

    -   **Qué hace este ajuste:** Determina cómo el módulo maneja las combinaciones de productos. Puede elegir entre crear nuevos productos reales para cada combinación o simplemente cambiar cómo se muestran en las páginas de listado.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Crear productos separados para cada combinación":* El módulo creará físicamente nuevas entradas de producto en su base de datos para cada combinación. Cada nuevo producto tendrá su propio ID, URL, stock, precio, etc. Esta es la opción más potente para SEO y control granular.
        -   *Cuando se establece en "Mostrar un recuadro por combinación en las listas de categorías, marcas, proveedores, búsqueda y los más vendidos (división virtual)":* El módulo *no* creará nuevos productos. En su lugar, modificará cómo se muestran los productos existentes con combinaciones en las páginas de listado, haciendo que *parezca* que cada combinación es un producto separado. El catálogo de productos real permanece sin cambios. Esto tiene menos impacto para el SEO, pero puede mejorar la experiencia de navegación.
    -   **Valor recomendado:** "Crear productos separados para cada combinación" para un máximo SEO y control, o "Mostrar un recuadro por combinación..." para una mejora de visualización más simple.
    -   **Escenario / ejemplo del comerciante:** Quiere que cada color y talla de su camiseta tenga su propia página de producto y se posicione en Google. Elige "Crear productos separados". Si solo quiere que sus páginas de categoría se vean más limpias mostrando cada variación sin crear nuevos productos, elige "Mostrar un recuadro por combinación".
-   **Solo dividir productos activos:**

    -   **Qué hace este ajuste:** Controla si el módulo debe procesar solo los productos que están actualmente habilitados en su tienda, o todos los productos independientemente de su estado activo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Solo los productos que están actualmente configurados como "activos" en su catálogo de PrestaShop tendrán sus combinaciones divididas. Los productos inactivos serán ignorados.
        -   *Cuando está desactivado:* El módulo intentará dividir combinaciones para todos los productos, incluidos aquellos que están actualmente inactivos.
    -   **Valor recomendado:** SÍ (para evitar crear productos innecesarios para artículos que no está vendiendo).
    -   **Escenario / ejemplo del comerciante:** Tiene muchos productos antiguos e inactivos en su catálogo. Solo quiere dividir combinaciones para su inventario actual y activo para mantener su tienda organizada. Activa este ajuste.
-   **Acción del producto de origen después de la división:**

    -   **Qué hace este ajuste:** Define qué sucede con el producto original (el que tiene combinaciones) después de que sus combinaciones se hayan dividido en nuevos productos individuales.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Desactivar producto de origen":* El producto original se marcará como inactivo en su catálogo. Ya no será visible en el front office.
        -   *Cuando se establece en "Mantener producto de origen activo":* El producto original permanecerá activo y visible en su tienda. Es posible que deba ajustar manualmente su visualización o contenido para evitar confusiones con los nuevos productos divididos.
        -   *Cuando se establece en "Eliminar producto de origen":* El producto original se eliminará permanentemente de su catálogo. ¡Úselo con extrema precaución!
    -   **Valor recomendado:** "Desactivar producto de origen" o "Mantener producto de origen activo" (dependiendo de su estrategia). "Eliminar producto de origen" generalmente no se recomienda a menos que esté absolutamente seguro.
    -   **Escenario / ejemplo del comerciante:** Ha dividido un producto "Camiseta" en "Camiseta - Roja - S", "Camiseta - Azul - M", etc. Quiere que los clientes solo vean las variaciones individuales, por lo que elige "Desactivar producto de origen" para la "Camiseta" original.
-   **Copiar imágenes del producto:**

    -   **Qué hace este ajuste:** Determina si las imágenes asociadas con el producto original y sus combinaciones deben copiarse a los productos divididos recién creados.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Las imágenes del producto original y su combinación específica se duplicarán y asignarán al nuevo producto dividido. Esto asegura que cada nuevo producto tenga imágenes relevantes.
        -   *Cuando está desactivado:* Se crearán nuevos productos divididos sin ninguna imagen. Luego, tendría que subir manualmente las imágenes para cada nuevo producto, lo cual es muy lento.
    -   **Valor recomendado:** SÍ.
    -   **Escenario / ejemplo del comerciante:** Tiene una combinación de "Camiseta Roja" con una imagen específica. Cuando la divide en "Camiseta - Roja - Pequeña", quiere que esa imagen de camiseta roja se asigne automáticamente al nuevo producto.
-   **Combinaciones mínimas para dividir:**

    -   **Qué hace este ajuste:** Establece un umbral para el número de combinaciones que debe tener un producto antes de que el módulo considere dividirlo. Los productos con menos combinaciones que este valor serán ignorados.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en un valor (por ejemplo, 2):* Solo se procesarán los productos que tengan 2 o más combinaciones. Los productos con solo 1 combinación (o sin combinaciones) se omitirán.
        -   *Cuando se establece en 0 o 1:* Todos los productos con al menos una combinación se considerarán para la división.
    -   **Valor recomendado:** 2 (para evitar dividir productos simples que podrían no beneficiarse de ello).
    -   **Escenario / ejemplo del comerciante:** Tiene algunos productos con una sola combinación (por ejemplo, una camiseta de "Talla Única"). No quiere dividirlos, pero sí quiere dividir productos con múltiples colores y tallas. Lo establece en 2.

#### Ajustes del constructor de nombres

Estos ajustes controlan cómo se generan los nombres de los nuevos productos divididos.

-   **Plantilla del constructor de nombres:**

    -   **Qué hace este ajuste:** Le permite definir una plantilla personalizada para generar los nombres de los nuevos productos divididos. Puede usar marcadores de posición para el nombre del producto, los nombres de los grupos de atributos y los nombres de los atributos.
    -   **Efecto de cambiar este ajuste:** El módulo utilizará esta plantilla para construir el campo `name` para cada nuevo producto.
    -   **Valor recomendado:** `[product_name] - [attribute_group_name]: [attribute_name]` (o similar, dependiendo del estilo de su marca).
    -   **Escenario / ejemplo del comerciante:** Su producto original es "Vestido de Fiesta". Tiene combinaciones como "Color: Rojo" y "Talla: Pequeña". Si su plantilla es `[product_name] - [attribute_name]`, el nuevo nombre del producto sería "Vestido de Fiesta - Rojo".
-   **Plantilla del constructor de URL:**

    -   **Qué hace este ajuste:** Similar al constructor de nombres, esto le permite definir una plantilla personalizada para generar las URL amigables (slugs) de los nuevos productos divididos.
    -   **Efecto de cambiar este ajuste:** El módulo utilizará esta plantilla para construir el campo `link_rewrite` para cada nuevo producto.
    -   **Valor recomendado:** `[product_name]-[attribute_name]` (o similar, asegurándose de que sea amigable para SEO y único).
    -   **Escenario / ejemplo del comerciante:** Usando el ejemplo de "Vestido de Fiesta", si su plantilla de URL es `[product_name]-[attribute_name]`, la nueva URL podría ser `/vestido-de-fiesta-rojo`.
-   **Separador para múltiples atributos:**

    -   **Qué hace este ajuste:** Especifica el carácter o la cadena utilizada para separar múltiples nombres de atributos cuando se combinan en el nombre o la URL del producto.
    -   **Efecto de cambiar este ajuste:** Este carácter se insertará entre los nombres de los atributos si un producto tiene combinaciones de múltiples grupos de atributos (por ejemplo, Color y Talla).
    -   **Valor recomendado:** `-` (guion) para URL, `,` (coma espacio) para nombres.
    -   **Escenario / ejemplo del comerciante:** Si un producto es "Camiseta - Roja - Pequeña", el guion es el separador. Puede cambiarlo a una barra `/` si lo prefiere.

#### Ajustes avanzados

-   **Redirigir URLs antiguas:**

    -   **Qué hace este ajuste:** Si está activado, el módulo creará redirecciones 301 desde la URL del producto original (y potencialmente URLs específicas de combinación) a la URL del nuevo producto dividido. Esto es crucial para el SEO.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Los motores de búsqueda y los usuarios que accedan a URLs antiguas serán redirigidos automáticamente a la página del nuevo producto correcto, preservando el valor SEO y evitando enlaces rotos.
        -   *Cuando está desactivado:* Las URLs antiguas llevarán a errores 404 "Página no encontrada", lo que perjudicará su SEO y la experiencia del usuario.
    -   **Valor recomendado:** SÍ.
    -   **Escenario / ejemplo del comerciante:** Ha dividido "Camiseta" en "Camiseta - Roja - Pequeña". Si un cliente o motor de búsqueda intenta acceder a la antigua página de "Camiseta", será enviado automáticamente a la página del nuevo producto dividido más relevante.
-   **Borrar caché después de la división:**

    -   **Qué hace este ajuste:** Borra automáticamente la caché de PrestaShop después de realizar una operación de división.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Asegura que los cambios realizados por el módulo (nuevos productos, redirecciones) sean inmediatamente visibles en el front office sin necesidad de borrar la caché manualmente.
        -   *Cuando está desactivado:* Es posible que deba borrar la caché manualmente (Parámetros avanzados > Rendimiento) para que aparezcan los cambios.
    -   **Valor recomendado:** SÍ.
    -   **Escenario / ejemplo del comerciante:** Acaba de dividir un gran número de productos. Activar esto asegura que sus clientes vean los nuevos listados de productos de inmediato sin que usted tenga que borrar la caché manualmente.

### 1.2 Pantallas de administración dedicadas y vistas de controlador

#### AdminMySplitProductsController (Back Office > Módulos > Dividir combinaciones en productos separados > Gestionar divisiones)

Esta pantalla proporciona la interfaz para iniciar, gestionar y revertir operaciones de división de productos.

-   **Nombre de la pantalla y ubicación del menú:** "Gestionar divisiones" (accesible desde la página de configuración principal del módulo o potencialmente un nuevo elemento de menú en "Catálogo" o "Módulos").
-   **Acciones y configuraciones disponibles:**
    -   **Búsqueda y selección de productos:** Una barra de búsqueda y una función de autocompletado para encontrar productos específicos que desea dividir.
    -   **Botón "Dividir producto":** Inicia el proceso de división para el producto seleccionado.
    -   **Botón "Revertir":** Le permite deshacer una operación de división anterior para un producto específico, restaurando el producto original y eliminando los productos divididos.
    -   **Tabla de historial:** Una lista de todos los productos que se han dividido, mostrando:
        -   Nombre del producto original
        -   Fecha de división
        -   Número de combinaciones divididas
        -   Estado (por ejemplo, "Completado", "Revertido")
        -   Botones de acción (por ejemplo, "Revertir", "Ver productos divididos")
-   **Efecto de los cambios:**
    -   **Dividir un producto:** Crea nuevas entradas de producto en su catálogo basadas en las combinaciones del producto seleccionado y la configuración del módulo (nombres, URLs, imágenes, etc.). El estado del producto original podría cambiar (por ejemplo, deshabilitado).
    -   **Revertir una división:** Elimina los productos creados durante la división y restaura el producto original a su estado anterior a la división (por ejemplo, lo vuelve a habilitar, restaura sus combinaciones). Esta es una potente función de deshacer.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Use la barra de búsqueda para encontrar el producto que desea dividir.
    2.  Revise los nombres y URLs propuestos (si hay una vista previa disponible).
    3.  Haga clic en "Dividir producto".
    4.  Supervise la tabla de historial para ver el estado.
    5.  Si comete un error o cambia de opinión, use la función "Revertir" de la tabla de historial.

#### index.php (mysplitproducts/controllers/admin/index.php)

Este archivo probablemente sirve como marcador de posición o base para los controladores de administración del módulo, asegurando las mejores prácticas de seguridad de PrestaShop al evitar la lista directa de directorios. No representa una pantalla distinta orientada al usuario, sino que forma parte de la estructura interna del módulo.

### 1.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de configuración del módulo** | Activar módulo | SÍ | Interruptor maestro para la funcionalidad del módulo. |
| | Modo de división | "Crear productos separados" | Cómo se manejan las combinaciones (nuevos productos vs. visualización virtual). |
| | Solo dividir productos activos | SÍ | Procesar solo productos activos. |
| | Acción del producto de origen después de la división | "Desactivar producto de origen" | Qué sucede con el producto original. |
| | Copiar imágenes del producto | SÍ | Duplicar imágenes a nuevos productos divididos. |
| | Combinaciones mínimas para dividir | 2 | Umbral para la división de productos. |
| | Plantilla del constructor de nombres | `[product_name] - [attribute_group_name]: [attribute_name]` | Define los nombres de los nuevos productos. |
| | Plantilla del constructor de URL | `[product_name]-[attribute_name]` | Define las URL amigables de los nuevos productos. |
| | Separador para múltiples atributos | `-` (para URL), `,` (para nombre) | Carácter para separar múltiples atributos. |
| | Redirigir URLs antiguas | SÍ | Crea redirecciones 301 para SEO. |
| | Borrar caché después de la división | SÍ | Borra automáticamente la caché de PrestaShop. |
| **Gestionar divisiones (AdminMySplitProductsController)** | Búsqueda y división de productos | N/A | Encontrar e iniciar la división de productos. |
| | Revertir división | N/A | Deshacer una operación de división anterior. |
| | Tabla de historial | N/A | Ver y gestionar operaciones de división pasadas. |

## 2. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Después de dividir productos, no veo los nuevos productos en mis categorías o resultados de búsqueda.**

-   **R:** La razón más común es el almacenamiento en caché.
    -   **Solución:** Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop. Haga clic en "Borrar caché" (o "Borrar caché de Smarty" y "Borrar caché" para todas las cachés). Si la configuración del módulo "Borrar caché después de la división" está activada, esto debería ocurrir automáticamente, pero a veces es necesario un borrado manual. Además, asegúrese de que los nuevos productos estén configurados como "activos" y asociados a categorías.

**P2: Mis URLs de productos antiguos ahora muestran "Página no encontrada" (errores 404).**

-   **R:** Esto generalmente significa que la función de redirección no está activa o no funciona correctamente.
    -   **Solución:** Vaya a la página de configuración del módulo y asegúrese de que "Redirigir URLs antiguas" esté configurado en SÍ. Si ya está activado, borre la caché de su PrestaShop (Parámetros avanzados > Rendimiento). Si el problema persiste, revise el archivo `.htaccess` de su servidor en busca de reglas de reescritura en conflicto, o póngase en contacto con el soporte.

**P3: Los nombres o URLs de mis nuevos productos divididos se ven extraños o no son lo que esperaba.**

-   **R:** Esto está controlado por los ajustes "Plantilla del constructor de nombres" y "Plantilla del constructor de URL".
    -   **Solución:** Vaya a la página de configuración del módulo y revise estas plantillas. Asegúrese de que está utilizando los marcadores de posición correctos (`[product_name]`, `[attribute_name]`, `[attribute_group_name]`) y que los separadores son apropiados. Puede probar diferentes plantillas en un solo producto primero. Recuerde borrar la caché después de realizar cambios en las plantillas.

**P4: Algunos productos con combinaciones no se dividieron, aunque inicié el proceso.**

-   **R:** Verifique el ajuste "Combinaciones mínimas para dividir" en la configuración del módulo.
    -   **Solución:** Si un producto tiene menos combinaciones que este umbral, se omitirá. Ajuste este ajuste si desea dividir productos con menos variaciones. Además, asegúrese de que "Solo dividir productos activos" no esté impidiendo que se procesen productos inactivos si esa es su intención.

**P5: ¿Qué sucede con los carritos de los clientes si divido un producto que ya han añadido?**

-   **R:** El módulo está diseñado para manejar esto con elegancia. Los carritos abiertos existentes que contienen una combinación de un producto que se ha dividido se actualizarán típicamente para reflejar el nuevo ID de producto distinto. Esto significa que el carrito del cliente seguirá conteniendo el artículo correcto, ahora vinculado a su nueva entrada de producto individual. Sin embargo, siempre es mejor realizar las divisiones durante períodos de bajo tráfico o probar a fondo.

## 3. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 3.1 Resumen de la arquitectura

El módulo "Dividir combinaciones en productos separados" (`mysplitproducts`) está construido siguiendo el patrón MVC (Modelo-Vista-Controlador) de PrestaShop. Aprovecha en gran medida `ObjectModel` para la persistencia de datos, `AdminController` personalizado para su interfaz de Back Office y un conjunto de clases de servicio dedicadas para encapsular la lógica compleja de división de productos, nombramiento y redirección. El módulo extiende la funcionalidad principal de PrestaShop creando y gestionando dinámicamente entidades de productos, manejando reescrituras de URL e integrándose con el gestor de módulos. Se basa en un robusto sistema de registro interno y un patrón de búsqueda para una recuperación eficiente de datos.

### 3.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno definido explícitamente en el inventario proporcionado. La lógica de visualización del front-office para divisiones virtuales o redirecciones probablemente se maneja a través de hooks dentro del archivo principal `mysplitproducts.php` o mediante overrides.
-   **Controladores de administración de Back-Office**:

    -   `controllers/admin/AdminMySplitProductsController.php`
        -   **Nombre de la clase y clase padre:** `AdminMySplitProductsController` extiende `ModuleAdminController`.
        -   **Nombre de la pestaña y entidad gestionada:** Este controlador gestiona la funcionalidad principal de dividir y revertir productos. Presenta una vista de cuadrícula/gestión para los productos que se han procesado y permite a los administradores iniciar nuevas divisiones o revertir las existentes. Interactúa con las clases `MspSplitEngine`, `MspLogger` y `MspRedirector`.
        -   **Responsabilidad:** Maneja la visualización de la interfaz "Gestionar divisiones", procesa las solicitudes AJAX para la búsqueda de productos, inicia el proceso de división de productos y gestiona las operaciones de reversión. Es el centro neurálgico para las tareas administrativas del módulo.
    -   `controllers/admin/index.php`
        -   **Nombre de la clase y clase padre:** N/A (no es un archivo de clase).
        -   **Responsabilidad:** Este es un archivo `index.php` vacío estándar colocado en subdirectorios para evitar la lista de directorios, mejorando la seguridad. No contiene ninguna lógica funcional para el módulo.

### 3.3 Clases y modelos principales (`classes/`)

-   `classes/index.php`
    -   **Responsabilidad:** `index.php` vacío estándar por seguridad, evitando la lista de directorios.
-   `classes/MspAliasStore.php`
    -   **Con qué tabla de base de datos interactúa:** Probablemente `ps_mysplitproducts_alias` (tabla personalizada) o `ps_configuration` para almacenar alias/redirecciones.
    -   **Si extiende ObjectModel:** Poco probable que extienda directamente `ObjectModel`, pero gestiona datos relacionados con los alias.
    -   **Métodos públicos clave y lógica de negocio encapsulada:** Gestiona el mapeo entre los ID de producto/combinación originales y sus ID de producto dividido recién creados. Crucial para la funcionalidad de redirección y reversión.
-   `classes/MspCatalog.php`
    -   **Con qué tabla de base de datos interactúa:** `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_image`, `ps_image_shop`, `ps_stock_available`, etc. (tablas de productos principales de PrestaShop).
    -   **Si extiende ObjectModel:** No, probablemente una clase de servicio.
    -   **Métodos públicos clave y lógica de negocio encapsulada:** Proporciona métodos para consultar y manipular datos de productos principales de PrestaShop. Utilizado por `MspSplitEngine` para recuperar detalles de productos, combinaciones y actualizar estados de productos.
-   `classes/MspCombinationSearchProvider.php`
    -   **Con qué tabla de base de datos interactúa:** `ps_product`, `ps_product_lang`, `ps_product_attribute`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`.
    -   **Si extiende ObjectModel:** No, probablemente una clase de servicio.
    -   **Métodos públicos clave y lógica de negocio encapsulada:** Proporciona funcionalidad para buscar productos y sus combinaciones, a menudo utilizado para la función de autocompletado en el controlador de administración.
-   `classes/MspFinder.php`
    -   **Con qué tabla de base de datos interactúa:** Varias tablas de PrestaShop, dependiendo del contexto de búsqueda.
    -   **Si extiende ObjectModel:** No, probablemente una clase de utilidad/servicio.
    -   **Métodos públicos clave y lógica de negocio encapsulada:** Una clase de recuperación de datos de propósito general, que abstrae consultas de base de datos comunes para productos, atributos y otras entidades necesarias para el módulo.
-   `classes/MspLogger.php`
    -   **Con qué tabla de base de datos interactúa:** Probablemente `ps_mysplitproducts_log` (tabla personalizada).
    -   **Si extiende ObjectModel:** Sí, o gestiona una tabla personalizada directamente.
    -   **Métodos públicos clave y lógica de negocio encapsulada:** Registra todas las operaciones de división y reversión, incluidas las marcas de tiempo, los productos afectados y el estado. Esencial para la tabla de historial en `AdminMySplitProductsController` y para la depuración.
-   `classes/MspNameBuilder.php`
    -   **Con qué tabla de base de datos interactúa:** N/A (lógica pura).
    -   **Si extiende ObjectModel:** No, una clase de utilidad.
    -   **Métodos públicos clave y lógica de negocio encapsulada:** Implementa la lógica para generar nuevos nombres de productos y URLs amigables basándose en las plantillas configuradas (`MSP_NAME_BUILDER_TEMPLATE`, `MSP_URL_BUILDER_TEMPLATE`) y los datos de atributos.
-   `classes/MspProductCloner.php`
    -   **Con qué tabla de base de datos interactúa:** `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_image`, `ps_image_shop`, `ps_stock_available`, etc.
    -   **Si extiende ObjectModel:** No, una clase de servicio.
    -   **Métodos públicos clave y lógica de negocio encapsulada:** La clase principal responsable de duplicar un producto y sus datos asociados (imágenes, stock, categorías, características, etc.) para crear un nuevo producto distinto para una combinación específica. Maneja el complejo proceso de copiar datos entre múltiples tablas de PrestaShop.
-   `classes/MspRedirector.php`
    -   **Con qué tabla de base de datos interactúa:** `ps_mysplitproducts_redirect` (tabla personalizada) o `ps_url_rewrite` (PrestaShop core).
    -   **Si extiende ObjectModel:** No, una clase de servicio.
    -   **Métodos públicos clave y lógica de negocio encapsulada:** Gestiona la creación y eliminación de redirecciones 301 de las URLs de productos/combinaciones originales a las URLs de los nuevos productos divididos. Se integra con el sistema de reescritura de URLs de PrestaShop o implementa su propia lógica de redirección.
-   `classes/MspSplitEngine.php`
    -   **Con qué tabla de base de datos interactúa:** Orquesta las interacciones con `MspCatalog`, `MspProductCloner`, `MspNameBuilder`, `MspRedirector`, `MspLogger`.
    -   **Si extiende ObjectModel:** No, la clase de servicio orquestadora principal.
    -   **Métodos públicos clave y lógica de negocio encapsulada:** La clase central que coordina todo el proceso de división. Toma un ID de producto, recupera sus combinaciones, utiliza `MspNameBuilder` para generar nuevos detalles, `MspProductCloner` para crear nuevos productos, `MspRedirector` para URLs y `MspLogger` para registrar la operación. También maneja la lógica de reversión.

### 3.4 Activos JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    -   **Alcance:** Back-office.
    -   **Qué escuchadores de eventos vincula:** Eventos de entrada en campos de búsqueda.
    -   **Qué manipulación del DOM, ventanas emergentes modales, animación o llamadas a SDK de terceros externos ejecuta:** Proporciona una funcionalidad de autocompletado para los campos de búsqueda de productos en la interfaz de administración, probablemente utilizando llamadas AJAX a `AdminMySplitProductsController` para obtener sugerencias de productos.
-   `views/js/admin.js`
    -   **Alcance:** Back-office.
    -   **Qué escuchadores de eventos vincula:** Eventos de clic en botones (por ejemplo, "Dividir producto", "Revertir"), envíos de formularios.
    -   **Qué manipulación del DOM, ventanas emergentes modales, animación o llamadas a SDK de terceros externos ejecuta:** Maneja los elementos interactivos del panel de control de `AdminMySplitProductsController`, incluida la iniciación de acciones de división/reversión, la actualización de la tabla de historial y la visualización de indicadores de carga o mensajes de éxito/error.
-   `views/js/configure.js`
    -   **Alcance:** Back-office.
    -   **Qué escuchadores de eventos vincula:** Eventos de cambio en campos de configuración, envíos de formularios.
    -   **Qué manipulación del DOM, ventanas emergentes modales, animación o llamadas a SDK de terceros externos ejecuta:** Gestiona el formulario de configuración principal del módulo. Puede incluir lógica para mostrar/ocultar campos según otras selecciones (por ejemplo, modo de división), validación de formularios y guardado AJAX de la configuración.
-   `views/js/listing.js`
    -   **Alcance:** Front-office (para el modo de división virtual).
    -   **Qué escuchadores de eventos vincula:** Potencialmente eventos `prestashop.on` para actualizaciones de listas de productos, DOM ready.
    -   **Qué manipulación del DOM, ventanas emergentes modales, animación o llamadas a SDK de terceros externos ejecuta:** Si el modo de "división virtual" está activo, este script modificaría dinámicamente los listados de productos en categorías, búsquedas y otras páginas para mostrar recuadros de combinación individuales. Esto podría implicar clonar elementos de productos existentes, actualizar su contenido (nombre, imagen, precio) y volver a renderizar partes de la cuadrícula de productos.

### 3.5 Hojas de estilo CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`
    -   **Alcance:** Estilo de formulario de administración del Back-office.
    -   **Principales componentes y contenedores de la interfaz de usuario que estiliza:** Estilos para el menú desplegable de autocompletado, campos de entrada de búsqueda y listas de sugerencias dentro del panel de administración.
    -   **Selectores de clase CSS clave que los desarrolladores pueden anular en su tema:** `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`.
-   `views/css/admin.css`
    -   **Alcance:** Estilo de formulario de administración del Back-office.
    -   **Principales componentes y contenedores de la interfaz de usuario que estiliza:** Estilo general para las páginas de configuración del módulo y el panel de control "Gestionar divisiones", incluidas tablas, botones, elementos de formulario e indicadores de estado.
    -   **Selectores de clase CSS clave que los desarrolladores pueden anular en su tema:** `.mysplitproducts-config`, `.mysplitproducts-dashboard`, `.mysplitproducts-table`, `.mysplitproducts-status-success`, `.mysplitproducts-status-error`.

### 3.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**: Ninguna listada explícitamente, pero el módulo podría usar hooks para la visualización en el front-office en modo de división virtual (por ejemplo, `displayProductList`, `displayProductExtraContent`) que serían manejados por el archivo principal `mysplitproducts.php`.
-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `views/templates/admin/configure_shell.tpl`
        -   **Propósito:** Esta plantilla probablemente sirve como el envoltorio o shell principal para la página de configuración del módulo, incluyendo los ajustes generales y posiblemente pestañas o secciones para otros ajustes. Proporciona el diseño general para `getContent()`.
    -   `views/templates/admin/dashboard.tpl`
        -   **Propósito:** Esta plantilla renderiza el panel de control "Gestionar divisiones", incluyendo el campo de búsqueda de productos, el botón "Dividir producto" y la tabla de historial de operaciones de división. Es la vista para `AdminMySplitProductsController`.
-   **Plantillas de front-office (`views/templates/front/`)**: Ninguna listada explícitamente. La renderización del front-office para divisiones virtuales probablemente implicaría modificar las plantillas de temas existentes a través de hooks u overrides, o inyectar contenido dinámicamente a través de JavaScript (`listing.js`).

### 3.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:

    -   `ps_mysplitproducts_log`: Almacena un historial de todas las operaciones de división y reversión, incluyendo `id_product_original`, `id_product_split`, `action` (dividir/revertir), `date_add`, `status`.
    -   `ps_mysplitproducts_redirect`: Almacena mapeos de redirección 301 de URLs antiguas a URLs de nuevos productos divididos, incluyendo `old_url`, `new_url`, `id_product_original`, `id_product_split`.
    -   `ps_mysplitproducts_alias`: Almacena mapeos entre los ID de producto/combinación originales y los nuevos ID de producto dividido, crucial para búsquedas internas y reversiones.
    -   Registros de configuración almacenados en `ps_configuration`:
        -   `MSP_MODE`: (int) 0 para virtual, 1 para división real.
        -   `MSP_ACTIVE_ONLY`: (bool) Solo dividir productos activos.
        -   `MSP_SOURCE_ACTION`: (int) Acción para el producto de origen (desactivar, mantener activo, eliminar).
        -   `MSP_IMAGE_COPY`: (bool) Copiar imágenes a nuevos productos.
        -   `MSP_MIN_COMBINATIONS`: (int) Combinaciones mínimas para la división.
        -   `MSP_NAME_BUILDER_TEMPLATE`: (string) Plantilla para nuevos nombres de productos.
        -   `MSP_URL_BUILDER_TEMPLATE`: (string) Plantilla para nuevas URLs de productos.
        -   `MSP_SEPARATOR_MULTIPLE_ATTRIBUTES`: (string) Separador para múltiples atributos.
        -   `MSP_REDIRECT_OLD_URLS`: (bool) Habilitar redirecciones 301.
        -   `MSP_CLEAR_CACHE_AFTER_SPLIT`: (bool) Borrar caché automáticamente.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Potencialmente inyecta CSS/JS para la división virtual del front-office, o metaetiquetas para SEO. |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página del Back Office. | Inyecta CSS/JS para las páginas de administración del módulo (`admin.css`, `admin.js`, `autocomplete.css`, `autocomplete.js`). |
| `actionProductUpdate` | Después de que se actualiza un producto. | Potencialmente activa la reevaluación para la división o actualizaciones relacionadas con productos divididos. |
| `actionProductDelete` | Después de que se elimina un producto. | Maneja la limpieza de productos divididos o redirecciones si se elimina el producto original. |
| `actionProductSave` | Antes o después de guardar un producto. | Intercepta los guardados de productos para gestionar productos divididos o datos relacionados. |
| `actionObjectProductAddAfter` | Después de añadir un nuevo producto. | Potencialmente activa la división para productos recién añadidos si está configurado. |
| `actionObjectProductUpdateAfter` | Después de que se actualiza un producto. | Actualiza productos divididos o redirecciones relacionadas. |
| `actionObjectProductDeleteAfter` | Después de que se elimina un producto. | Limpia los productos divididos y las redirecciones asociadas. |
| `displayProductList` | Cuando se renderiza una lista de productos (categoría, búsqueda, etc.). | **Crucial para el modo de división virtual.** Modifica la lista de productos para mostrar recuadros de combinación individuales. |
| `displayProductExtraContent` | En la página del producto, debajo del contenido principal. | Podría usarse para mostrar enlaces a otras combinaciones o un mensaje sobre productos divididos. |
| `displayAdminProductsExtra` | En la página de edición de productos en el Back Office. | Añade una pestaña o sección personalizada a la página de edición de productos para gestionar las divisiones relacionadas con ese producto específico. |
| `actionAdminProductsListingResultsModifier` | Modifica los resultados del listado de productos en el Back Office. | Ajusta la lista de productos para mostrar/ocultar productos originales o resaltar productos divididos. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su plantilla. | Registra JavaScript (`listing.js`) y CSS del front-office para el modo de división virtual. |
| `moduleRoutes` | Durante la inicialización del enrutamiento de URL. | Registra rutas personalizadas para productos divididos o redirecciones. |

## 4. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte completo, consulte su cuenta de cliente en MyPresta.eu.

-   **Actualizaciones del módulo:** Inicie sesión en su cuenta en [MyPresta.eu Order History & Downloads](https://mypresta.eu/my-account/orders/) para descargar la versión más reciente de "Dividir combinaciones en productos separados".
-   **Soporte técnico:** Si encuentra algún problema o tiene preguntas que no están cubiertas en esta guía, abra un ticket de soporte a través de su cuenta de cliente de MyPresta.eu. Nuestro equipo de expertos está listo para ayudarle.
"""

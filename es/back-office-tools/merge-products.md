---
title: "Fusionar Productos - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Fusionar Productos' de MyPresta.eu."
sidebar:
  label: "Fusionar Productos - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Merge Products en MyPresta.eu](https://mypresta.eu/modules/administration-tools/merge-products.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/merge-products/)
>
> ---


# Fusionar Productos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

El módulo Fusionar Productos ofrece una pantalla de administración dedicada para gestionar el proceso de fusión, accesible desde su back office de PrestaShop.

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Cuando haga clic por primera vez en "Configurar" después de la instalación, será llevado a una página similar a un panel de control. Esta página sirve principalmente como punto de entrada a la herramienta principal de fusión.

- **Qué hace esta pantalla:** Esta página de configuración inicial proporciona una breve descripción y un enlace directo a la herramienta principal "Fusionar Productos". No contiene ajustes específicos en sí misma, sino que le guía a donde se realiza la fusión real.
- **Efecto de cambiar este ajuste:** No hay ajustes directos que cambiar en esta pantalla inicial.
- **Valor recomendado:** N/A
- **Escenario / ejemplo de comerciante:** Este es su punto de partida. Desde aquí, hará clic en un botón o enlace para acceder a la funcionalidad principal del módulo.

### 2.2 Pantalla de Administración Dedicada: Herramienta Fusionar Productos (Back Office > Catálogo > Fusionar Productos)

Esta es la interfaz principal donde realizará todas las operaciones de fusión de productos. Puede encontrarla navegando a **Catálogo > Fusionar Productos** en el menú de su back office de PrestaShop.

Esta pantalla se divide en varias secciones para guiarle a través del proceso de fusión:

#### Paso 1: Seleccionar Producto Maestro

- **Qué hace esta sección:** Aquí, define el producto "maestro". Este es el producto en el que se fusionarán todos los demás productos "fuente" seleccionados, convirtiéndose en sus combinaciones.
- **Campo de entrada: "Buscar un producto"**
  - **Qué hace este ajuste:** Le permite buscar un producto existente en su catálogo para designarlo como el producto maestro. Puede buscar por nombre de producto, ID, EAN o referencia.
  - **Efecto de cambiar este ajuste:** A medida que escribe, aparecerá una lista de autocompletado. Seleccionar un producto rellena el área "Producto Maestro" con sus detalles. Este producto será la base para las nuevas combinaciones.
  - **Valor recomendado:** Elija el producto que mejor represente el listado consolidado. Por ejemplo, si fusiona "Camiseta Roja S", "Camiseta Roja M", "Camiseta Roja L" en uno, podría elegir "Camiseta Roja S" como maestro, y los demás se convertirán en sus combinaciones.
  - **Escenario / ejemplo de comerciante:** Tiene "iPhone 13 (Nuevo)" y "iPhone 13 (Reacondicionado)" como productos separados. Buscaría y seleccionaría "iPhone 13 (Nuevo)" como su producto maestro.

#### Paso 2: Seleccionar Productos Fuente

- **Qué hace esta sección:** Aquí, selecciona los productos que se convertirán en combinaciones y se añadirán al producto maestro.
- **Campo de entrada: "Buscar productos para fusionar"**
  - **Qué hace este ajuste:** Similar a la búsqueda de productos maestros, este campo le permite encontrar y seleccionar múltiples productos que se convertirán en combinaciones.
  - **Efecto de cambiar este ajuste:** Cada producto seleccionado se añade a una lista a continuación. Estos son los productos cuyos datos (precio, stock, atributos) se transferirán al producto maestro como nuevas combinaciones.
  - **Valor recomendado:** Seleccione todos los productos que son variaciones de su producto maestro elegido y que deben consolidarse.
  - **Escenario / ejemplo de comerciante:** Siguiendo el ejemplo del iPhone, buscaría y seleccionaría "iPhone 13 (Reacondicionado)" aquí. Si también tuviera "iPhone 13 (Usado - Grado A)", también lo seleccionaría.

#### Paso 3: Configurar Opciones de Fusión

Esta sección contiene ajustes críticos que controlan cómo se realiza la operación de fusión.

- **Opción: Modo de Fusión**

  - **Qué hace este ajuste:** Determina cómo se manejan los atributos de los productos fuente al crear combinaciones.
  - **Efecto de cambiar este ajuste:**
    - *Añadir un nuevo grupo de atributos:* El módulo creará un nuevo grupo de atributos (por ejemplo, "Condición") y un atributo para cada producto fuente (por ejemplo, "Nuevo", "Reacondicionado", "Usado"). Esto es ideal cuando los productos fuente difieren por una característica no cubierta por atributos existentes.
    - *Usar un grupo de atributos existente:* Si sus productos fuente ya comparten un grupo de atributos común (por ejemplo, "Talla" o "Color") y desea fusionarlos basándose en eso, puede seleccionarlo. Esto es menos común para fusionar productos completamente separados, pero útil para consolidar variaciones dentro de una estructura de atributos existente.
  - **Valor recomendado:** **"Añadir un nuevo grupo de atributos"** generalmente se recomienda para fusionar productos distintos, ya que proporciona una forma clara de diferenciar las nuevas combinaciones.
  - **Escenario / ejemplo de comerciante:** Está fusionando "Producto X - Nuevo" y "Producto X - Usado". Seleccionar "Añadir un nuevo grupo de atributos" creará un grupo de atributos "Condición" con atributos "Nuevo" y "Usado" para las combinaciones.
- **Campo de entrada: Nombre del Nuevo Grupo de Atributos (solo visible si se selecciona "Añadir un nuevo grupo de atributos")**

  - **Qué hace este ajuste:** Especifica el nombre para el nuevo grupo de atributos que se creará para diferenciar las combinaciones fusionadas.
  - **Efecto de cambiar este ajuste:** Este nombre aparecerá en su página de producto (por ejemplo, "Condición", "Grado", "Versión").
  - **Valor recomendado:** Un nombre descriptivo como "Condición", "Estado", "Tipo" o "Grado".
  - **Escenario / ejemplo de comerciante:** Si fusiona productos "Nuevos" y "Usados", podría introducir "Condición".
- **Opción: Regla del Producto Maestro**

  - **Qué hace este ajuste:** Define cómo se trata el propio producto maestro durante la fusión.
  - **Efecto de cambiar este ajuste:**
    - *Mantener como producto maestro:* El producto maestro permanece como el producto predeterminado, y los productos fuente se convierten en sus combinaciones. Sus combinaciones existentes (si las hay) se conservan.
    - *Convertir a combinación:* El propio producto maestro también se convierte en una combinación bajo su propio listado. Esto es útil si desea que todas las variaciones, incluido el maestro original, sean seleccionables a través del nuevo grupo de atributos.
  - **Valor recomendado:** **"Mantener como producto maestro"** suele ser suficiente. Elija "Convertir a combinación" si desea que el estado original del producto maestro sea explícitamente seleccionable como una combinación.
  - **Escenario / ejemplo de comerciante:** Si "iPhone 13 (Nuevo)" es su maestro, y fusiona "iPhone 13 (Reacondicionado)" en él, "Mantener como producto maestro" significa que "iPhone 13 (Nuevo)" es el predeterminado. Si elige "Convertir a combinación", entonces "Nuevo" se convertiría en una opción seleccionable junto con "Reacondicionado".
- **Opción: Acción del Producto Fuente**

  - **Qué hace este ajuste:** Determina qué sucede con los productos fuente originales después de que se hayan fusionado en el producto maestro como combinaciones.
  - **Efecto de cambiar este ajuste:**
    - *Desactivar:* Las páginas de producto fuente originales se deshabilitarán, haciéndolas inaccesibles para los clientes. Esta es generalmente la opción más segura.
    - *Eliminar:* Las páginas de producto fuente originales se eliminarán permanentemente de su catálogo. Use con precaución, ya que esta acción es irreversible.
    - *No hacer nada:* Las páginas de producto fuente originales permanecen activas. Esto generalmente no se recomienda, ya que puede llevar a contenido duplicado y confusión.
  - **Valor recomendado:** **"Desactivar"** es la opción más segura y común. Si está seguro de su fusión y redirecciones, "Eliminar" puede limpiar su catálogo, pero asegúrese de tener copias de seguridad.
  - **Escenario / ejemplo de comerciante:** Después de fusionar "iPhone 13 (Reacondicionado)" en "iPhone 13 (Nuevo)", normalmente elegiría "Desactivar" para evitar que los clientes encuentren la antigua página de producto "Reacondicionado".
- **Opción: Crear Redirecciones 301**

  - **Qué hace este ajuste:** Si está habilitado, el módulo creará redirecciones permanentes (301) desde las antiguas URLs de los productos fuente a la nueva URL del producto maestro.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* Cualquier cliente o motor de búsqueda que intente acceder a una URL de producto fuente antigua será enviado automáticamente a la página del producto maestro. Esto es crucial para el SEO, preservando la equidad de los enlaces y evitando enlaces rotos.
    - *Deshabilitado:* Las URLs de productos fuente antiguas llevarán a un error de "página no encontrada" si el producto fuente está desactivado o eliminado.
  - **Valor recomendado:** **SÍ (Habilitado)**. Esto es altamente recomendado para SEO y experiencia de usuario.
  - **Escenario / ejemplo de comerciante:** Un cliente marcó la antigua página de "iPhone 13 (Reacondicionado)". Con las redirecciones habilitadas, aterrizará automáticamente en la página maestra de "iPhone 13".
- **Opción: Tamaño del Lote**

  - **Qué hace este ajuste:** Controla cuántos productos se procesan en un solo lote durante la operación de fusión. Este es un ajuste técnico para evitar tiempos de espera del servidor para fusiones grandes.
  - **Efecto de cambiar este ajuste:** Un número más bajo reduce la carga del servidor pero hace que el proceso tarde más. Un número más alto lo acelera pero podría causar problemas en alojamientos menos potentes.
  - **Valor recomendado:** Dejar en el valor predeterminado a menos que experimente tiempos de espera. Si lo hace, intente reducirlo.
  - **Escenario / ejemplo de comerciante:** Si está fusionando cientos de productos y el proceso falla, reducir el tamaño del lote podría ayudar.
- **Opción: Solo Productos Activos**

  - **Qué hace este ajuste:** Si está habilitado, solo los productos fuente activos se considerarán para la fusión.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* Evita que los productos inactivos se fusionen, lo que puede simplificar el proceso y evitar crear combinaciones para productos que no tiene intención de vender.
    - *Deshabilitado:* Todos los productos, activos o inactivos, pueden fusionarse.
  - **Valor recomendado:** **SÍ (Habilitado)**, a menos que necesite específicamente fusionar productos inactivos.
  - **Escenario / ejemplo de comerciante:** Solo desea fusionar productos que actualmente son visibles y comprables en su tienda.
- **Opción: Excluir Packs**

  - **Qué hace este ajuste:** Si está habilitado, los productos configurados como "packs" (paquetes de otros productos) se excluirán de la selección de productos fuente.
  - **Efecto de cambiar este ajuste:** Evita la fusión accidental de packs de productos, que tienen relaciones complejas y podrían no comportarse como se espera al convertirlos en combinaciones.
  - **Valor recomendado:** **SÍ (Habilitado)**. La fusión de packs puede llevar a un comportamiento inesperado.
  - **Escenario / ejemplo de comerciante:** Tiene un pack "Kit de Inicio". No desea que este se fusione como una combinación en otro producto.
- **Opción: Excluir Productos Virtuales**

  - **Qué hace este ajuste:** Si está habilitado, los productos virtuales (por ejemplo, archivos descargables, servicios) se excluirán de la selección de productos fuente.
  - **Efecto de cambiar este ajuste:** Evita la fusión accidental de productos virtuales, que normalmente no tienen atributos físicos o stock y podrían no ser adecuados para la conversión a combinación.
  - **Valor recomendado:** **SÍ (Habilitado)**. Los productos virtuales no suelen ser buenos candidatos para fusionarse en combinaciones de productos físicos.
  - **Escenario / ejemplo de comerciante:** Vende un libro electrónico descargable. No desea que este se fusione como una combinación en un producto de libro físico.
- **Opción: Tamaño Mínimo del Grupo**

  - **Qué hace este ajuste:** Establece un número mínimo de productos fuente requeridos para formar un nuevo grupo de atributos.
  - **Efecto de cambiar este ajuste:** Esto es una salvaguarda. Si selecciona "Añadir un nuevo grupo de atributos" pero solo fusiona un producto fuente, este ajuste puede evitar la creación de un grupo de atributos innecesario con una sola opción.
  - **Valor recomendado:** Dejar en el valor predeterminado (normalmente 2).
  - **Escenario / ejemplo de comerciante:** Si selecciona accidentalmente solo un producto fuente, esto puede evitar que el módulo cree un grupo de atributos con una sola opción, lo cual es redundante.
- **Opción: Grupo de Atributos a Usar (solo visible si se selecciona "Usar un grupo de atributos existente")**

  - **Qué hace este ajuste:** Le permite seleccionar un grupo de atributos existente de su tienda para categorizar las nuevas combinaciones.
  - **Efecto de cambiar este ajuste:** El módulo intentará mapear los productos fuente a atributos dentro de este grupo elegido. Esto requiere una planificación cuidadosa para asegurar que sus productos fuente encajen lógicamente en la estructura de atributos existente.
  - **Valor recomendado:** Solo usar si tiene un escenario muy específico donde los productos fuente ya son variaciones de un atributo existente. De lo contrario, "Añadir un nuevo grupo de atributos" es más seguro.
  - **Escenario / ejemplo de comerciante:** Tiene productos "Camisa - Azul" y "Camisa - Roja" como productos separados, y desea fusionarlos en un producto maestro "Camisa", utilizando el grupo de atributos "Color" existente.

#### Paso 4: Revisar y Fusionar

- **Botón: "Fusionar Productos"**
  - **Qué hace este botón:** Inicia el proceso de fusión real basado en sus selecciones y configuraciones.
  - **Efecto de hacer clic:** El módulo procesará los productos fuente seleccionados, los convertirá en combinaciones, los asignará al producto maestro, actualizará el stock y los precios, y realizará redirecciones/desactivaciones según lo configurado. Se mostrará una barra de progreso o un mensaje de éxito.
  - **Acción recomendada:** Revise cuidadosamente todas sus selecciones antes de hacer clic. Asegúrese de tener una copia de seguridad de su tienda.
  - **Escenario / ejemplo de comerciante:** Después de seleccionar "iPhone 13 (Nuevo)" como maestro, "iPhone 13 (Reacondicionado)" como fuente, establecer "Condición" como el nuevo grupo de atributos y habilitar las redirecciones 301, hace clic en "Fusionar Productos" para ejecutar la consolidación.

#### Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Herramienta Fusionar Productos** | **Búsqueda de Producto Maestro** | N/A | Selecciona el producto principal al que se fusionarán otros. |
|  | **Búsqueda de Productos Fuente** | N/A | Selecciona productos para ser convertidos en combinaciones bajo el maestro. |
|  | **Modo de Fusión** | Añadir un nuevo grupo de atributos | Determina si se crea un nuevo grupo de atributos o se usa uno existente para las combinaciones. |
|  | **Nombre del Nuevo Grupo de Atributos** | Nombre descriptivo (ej., "Condición") | Nombre para el grupo de atributos creado para diferenciar las combinaciones fusionadas. |
|  | **Regla del Producto Maestro** | Mantener como producto maestro | Define si el propio producto maestro se convierte en una combinación o permanece como predeterminado. |
|  | **Acción del Producto Fuente** | Desactivar | Qué sucede con las páginas de producto fuente originales después de la fusión (Desactivar, Eliminar, No hacer nada). |
|  | **Crear Redirecciones 301** | SÍ | Crea redirecciones permanentes desde las URLs de los productos fuente antiguos a la nueva URL del maestro. Crucial para el SEO. |
|  | **Tamaño del Lote** | Predeterminado (ej., 10) | Número de productos procesados por lote. Ajustar para el rendimiento del servidor. |
|  | **Solo Productos Activos** | SÍ | Limita la selección de productos fuente solo a productos activos. |
|  | **Excluir Packs** | SÍ | Evita que los packs de productos sean seleccionados como productos fuente. |
|  | **Excluir Productos Virtuales** | SÍ | Evita que los productos virtuales sean seleccionados como productos fuente. |
|  | **Tamaño Mínimo del Grupo** | Predeterminado (ej., 2) | Número mínimo de productos fuente para crear un nuevo grupo de atributos. |
|  | **Grupo de Atributos a Usar** | N/A (solo si el modo es "Usar existente...") | Selecciona un grupo de atributos existente para el mapeo de combinaciones. |
|  | **Botón Fusionar Productos** | Hacer clic después de revisar | Ejecuta la operación de fusión. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Después de fusionar, no veo las nuevas combinaciones en mi página de producto.**
R1: Primero, borre la caché de su PrestaShop. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. Si el problema persiste, revise el producto maestro en su Back Office para asegurarse de que las combinaciones se crearon correctamente y están activas. Además, verifique que el grupo de atributos creado por el módulo esté habilitado y asociado con el producto maestro.

**P2: Las URLs de mis productos antiguos muestran errores de "Página no encontrada".**
R2: Esto generalmente significa que las redirecciones 301 no se crearon o no están funcionando.
1. Vuelva a la herramienta "Fusionar Productos" (**Catálogo > Fusionar Productos**).
2. Verifique si la opción "Crear Redirecciones 301" estaba habilitada durante la fusión. Si no, deberá configurar las redirecciones manualmente o volver a fusionar (después de restaurar una copia de seguridad si eliminó los productos fuente).
3. Asegúrese de que el archivo `.htaccess` de su servidor esté configurado correctamente para manejar las URLs amigables y las redirecciones de PrestaShop. A veces, las configuraciones del servidor pueden interferir.

**P3: El módulo parece quedarse atascado o agota el tiempo de espera durante el proceso de fusión.**
R3: Esto puede ocurrir con un gran número de productos o en servidores con recursos limitados.
1. Intente reducir el ajuste **"Tamaño del Lote"** en la sección "Configurar Opciones de Fusión" del módulo. Un tamaño de lote más pequeño (por ejemplo, 5 o 10) procesará menos productos a la vez, reduciendo la carga del servidor.
2. Verifique la configuración `max_execution_time` y `memory_limit` de PHP de su servidor. Es posible que deba aumentar temporalmente estos valores (contacte a su proveedor de alojamiento si no está seguro).

**P4: ¿Puedo deshacer una operación de fusión?**
R4: El módulo no tiene un botón de "deshacer". Por eso, **las copias de seguridad son absolutamente críticas**. Si necesita revertir, debe restaurar su tienda desde una copia de seguridad realizada *antes* de la fusión. Si solo desactivó los productos fuente y no los eliminó, podría reactivarlos manualmente y eliminar las combinaciones recién creadas del producto maestro, pero este es un proceso manual complejo.

**P5: ¿Qué pasa si mi tema personalizado no muestra correctamente el nuevo grupo de atributos?**
R5: El módulo crea grupos de atributos y combinaciones estándar de PrestaShop. Si su tema no los muestra correctamente, es probable que sea un problema de CSS o de plantilla Smarty dentro de su tema.
1. Verifique si los temas predeterminados de PrestaShop (por ejemplo, Classic) muestran las combinaciones correctamente. Si lo hacen, el problema es con su tema personalizado.
2. Es posible que deba consultar con un desarrollador web para ajustar el archivo `product.tpl` de su tema o el CSS asociado para renderizar correctamente los nuevos selectores de atributos.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Visión General de la Arquitectura

El módulo `Merge Products` sigue un patrón MVC estándar de PrestaShop para sus componentes de Back Office. Aprovecha el `ObjectModel` de PrestaShop para la manipulación de datos (aunque interactúa principalmente con los objetos `Product` y `Combination` directamente en lugar de modelos personalizados específicos del módulo). La lógica central para encontrar, construir y fusionar productos y sus combinaciones está encapsulada en clases de servicio dedicadas. El módulo utiliza un controlador de administración personalizado para su interfaz principal, proporcionando una cuadrícula y un formulario fáciles de usar para el proceso de fusión. También implementa un mecanismo de registro para rastrear las operaciones de fusión.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno. El módulo es puramente una herramienta de administración de Back-Office.
- **Controladores de Administración de Back-Office**:

  - `controllers/admin/AdminMyMergeProductsController.php`

    - **Nombre de la Clase**: `AdminMyMergeProductsController`
    - **Clase Padre**: `ModuleAdminController`
    - **Responsabilidad**: Este es el controlador principal para la interfaz administrativa del módulo. Maneja la visualización de la herramienta de fusión, incluyendo la búsqueda de productos (autocompletado), las opciones de configuración y el inicio del proceso de fusión. Orquesta las llamadas a las clases de servicio principales (`MmpFinder`, `MmpMergeEngine`, `MmpLogger`, `MmpRedirector`) para realizar la fusión real. Gestiona el envío del formulario y muestra comentarios al usuario.
    - **Nombre de la Pestaña**: "Fusionar Productos" (bajo el menú Catálogo)
    - **Entidad Gestionada**: Productos y sus combinaciones, atributos.
  - `controllers/admin/index.php`

    - **Nombre de la Clase**: N/A (archivo vacío)
    - **Clase Padre**: N/A
    - **Responsabilidad**: Este es un archivo `index.php` vacío estándar, a menudo colocado en directorios para evitar la lista de directorios en los servidores web. No tiene un papel funcional en la lógica del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

- `classes/index.php`

  - **Responsabilidad**: Archivo `index.php` vacío estándar para evitar la lista de directorios.
- `classes/MmpCombinationBuilder.php`

  - **Nombre de la Clase**: `MmpCombinationBuilder`
  - **Clase Padre**: Ninguna (clase de servicio independiente)
  - **Responsabilidad**: Esta clase es responsable de la intrincada lógica de crear nuevas combinaciones de productos basadas en los productos fuente. Maneja:
    - Mapeo de datos de productos fuente (precio, cantidad, EAN, referencia) a nuevas combinaciones.
    - Creación de nuevos atributos y grupos de atributos si `MMP_MERGE_MODE` está configurado en "Añadir un nuevo grupo de atributos".
    - Asignación de atributos existentes a nuevas combinaciones.
    - Manejo de imágenes para combinaciones.
    - Asegurar que las reglas de stock y precio se apliquen correctamente a las nuevas combinaciones.
- `classes/MmpFinder.php`

  - **Nombre de la Clase**: `MmpFinder`
  - **Clase Padre**: Ninguna (clase de servicio independiente)
  - **Responsabilidad**: Proporciona métodos para buscar y recuperar productos basados en varios criterios (ID, nombre, EAN, referencia). Esta clase es utilizada por `AdminMyMergeProductsController` para la funcionalidad de búsqueda de autocompletado tanto para productos maestros como para productos fuente. También filtra productos basándose en la configuración del módulo (por ejemplo, `MMP_ACTIVE_ONLY`, `MMP_EXCLUDE_PACKS`, `MMP_EXCLUDE_VIRTUAL`).
- `classes/MmpLogger.php`

  - **Nombre de la Clase**: `MmpLogger`
  - **Clase Padre**: Ninguna (clase de servicio independiente)
  - **Responsabilidad**: Maneja el registro de las operaciones de fusión. Registra los detalles de cada fusión, incluyendo el producto maestro, los productos fuente y la configuración utilizada. Esto es crucial para la depuración y auditoría. Probablemente almacena los registros en una tabla de base de datos personalizada o en un archivo.
- `classes/MmpMergeEngine.php`

  - **Nombre de la Clase**: `MmpMergeEngine`
  - **Clase Padre**: Ninguna (clase de servicio independiente)
  - **Responsabilidad**: Este es el orquestador central del proceso de fusión. Toma el producto maestro y los productos fuente, junto con la configuración, y coordina las acciones:
    - Llama a `MmpCombinationBuilder` para crear combinaciones.
    - Actualiza el producto maestro.
    - Maneja la `MMP_SOURCE_ACTION` (desactivar o eliminar productos fuente).
    - Gestiona el procesamiento por lotes (`MMP_BATCH_SIZE`).
    - Interactúa con `MmpRedirector` para las redirecciones 301.
    - Utiliza `MmpLogger` para registrar la operación.
- `classes/MmpRedirector.php`

  - **Nombre de la Clase**: `MmpRedirector`
  - **Clase Padre**: Ninguna (clase de servicio independiente)
  - **Responsabilidad**: Gestiona la creación de redirecciones 301. Cuando `MMP_REDIRECT` está habilitado, esta clase crea entradas en la tabla `ps_product_redirect` de PrestaShop (o un mecanismo similar) para redirigir las URLs de los productos fuente antiguos a la nueva URL del producto maestro.

### 4.4 Activos JavaScript (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`

  - **Ámbito**: Back-office.
  - **Responsabilidad**: Proporciona la lógica JavaScript para los campos de búsqueda de autocompletado de productos utilizados en `AdminMyMergeProductsController`. Probablemente utiliza AJAX para consultar `MmpFinder` en busca de sugerencias de productos a medida que el usuario escribe, mostrando los resultados en un menú desplegable. Maneja la selección y el llenado de los campos de producto respectivos.
- `views/js/admin.js`

  - **Ámbito**: Back-office.
  - **Responsabilidad**: Contiene funcionalidades JavaScript generales para la interfaz de administración del módulo. Esto podría incluir:
    - Visualización condicional de campos de configuración (por ejemplo, `New Attribute Group Name` solo visible si se selecciona "Añadir un nuevo grupo de atributos").
    - Validación de formularios.
    - Llamadas AJAX para iniciar el proceso de fusión y mostrar el progreso.
    - Escuchadores de eventos para botones y cambios de formulario.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`

  - **Ámbito**: Estilo de administración de Back-office.
  - **Responsabilidad**: Estiliza el menú desplegable de autocompletado y los campos de entrada de búsqueda, asegurando que sean visualmente consistentes y fáciles de usar dentro del Back Office de PrestaShop.
- `views/css/admin.css`

  - **Ámbito**: Estilo de administración de Back-office.
  - **Responsabilidad**: Proporciona un estilo específico para la interfaz de `AdminMyMergeProductsController`, incluyendo el diseño de las secciones, el estilo de las listas de productos y mejoras visuales generales para la página de configuración del módulo.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- `lib/searchTool/views/scripts.tpl`

  - **Ámbito**: Back-office.
  - **Responsabilidad**: Esta plantilla probablemente incluye el JavaScript y CSS necesarios para la herramienta de búsqueda de autocompletado, asegurando que se cargue en las páginas de administración relevantes. Podría contener etiquetas `script` y `link`.
- `views/templates/admin/configure_shell.tpl`

  - **Ámbito**: Administración de Back-office.
  - **Responsabilidad**: Esta plantilla sirve como envoltorio o shell para el contenido principal de configuración del módulo. Podría incluir elementos comunes de encabezado/pie de página, navegación o estructura de diseño general para las páginas de administración del módulo. Probablemente incluye `dashboard.tpl`.
- `views/templates/admin/dashboard.tpl`

  - **Ámbito**: Administración de Back-office.
  - **Responsabilidad**: Esta es la plantilla principal para la vista `AdminMyMergeProductsController`. Renderiza toda la interfaz de la herramienta de fusión, incluyendo:
    - El área de selección del producto maestro.
    - El área de selección de productos fuente.
    - El formulario de opciones de configuración de fusión (con todos los ajustes como `MMP_MERGE_MODE`, `MMP_REDIRECT`, etc.).
    - El botón "Fusionar Productos".
    - Cualquier mensaje de estado o indicadores de progreso durante la fusión.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo interactúa principalmente con las tablas principales existentes de PrestaShop:
    - `ps_product`: Para recuperar información del producto y actualizar el estado del producto (activo/inactivo).
    - `ps_product_attribute`: Para crear y gestionar combinaciones de productos.
    - `ps_product_attribute_shop`: Para datos de combinación específicos de la tienda.
    - `ps_product_attribute_combination`: Vincula combinaciones a atributos.
    - `ps_attribute_group`, `ps_attribute_group_lang`, `ps_attribute_group_shop`: Para crear nuevos grupos de atributos.
    - `ps_attribute`, `ps_attribute_lang`, `ps_attribute_shop`: Para crear nuevos atributos.
    - `ps_stock_available`: Para actualizar las cantidades de stock de las combinaciones.
    - `ps_product_lang`: Para nombres y descripciones de productos.
    - `ps_product_shop`: Para datos de productos específicos de la tienda.
    - `ps_url_rewrite`: Para gestionar URLs amigables.
    - `ps_configuration`: Almacena la configuración del módulo (por ejemplo, `MMP_MERGE_MODE`, `MMP_MASTER_RULE`, `MMP_SOURCE_ACTION`, `MMP_REDIRECT`, `MMP_BATCH_SIZE`, `MMP_ACTIVE_ONLY`, `MMP_EXCLUDE_PACKS`, `MMP_EXCLUDE_VIRTUAL`, `MMP_MIN_GROUP`, `MMP_ATTRIBUTE_GROUP`, `MMP_ATTRIBUTE_GROUP_NAME`).
  - El módulo podría crear una tabla personalizada para registrar las operaciones de fusión (por ejemplo, `ps_mmp_log` o similar), aunque esto no se detalla explícitamente en el inventario proporcionado. Si existe, almacenaría registros de cada evento de fusión.
  - Para las redirecciones 301, probablemente utiliza la tabla `ps_product_redirect` de PrestaShop (o un mecanismo similar si el módulo implementa su propio manejador de redirecciones).
- **Tabla de Hooks Registrados**:
  El módulo no registra explícitamente ningún hook de front-office (como `displayHeader`, `displayProductButtons`, etc.) ya que es una herramienta de back-office. Su interacción principal con el sistema de hooks de PrestaShop sería para:

  - `actionAdminControllerSetMedia`: Para cargar sus archivos CSS y JS específicos en el Back Office.
  - `actionProductUpdate` / `actionProductAdd` / `actionProductDelete`: Aunque no se enumeran explícitamente, la lógica interna del módulo para modificar productos podría activar estos hooks principales de PrestaShop, a los que otros módulos podrían escuchar.
  - `actionObjectProductAddAfter`, `actionObjectProductUpdateAfter`, `actionObjectProductDeleteAfter`: Hooks de ObjectModel que se activarían cuando el módulo crea, actualiza o elimina objetos `Product` o `ProductAttribute`.

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Fusionar Productos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta que pueda tener con respecto a la funcionalidad del módulo.

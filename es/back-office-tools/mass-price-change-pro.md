---
title: "Cambio masivo de precios pro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Cambio masivo de precios pro' de MyPresta.eu."
sidebar:
  label: "Cambio masivo de precios pro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Mass price change pro en MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-price-change-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/mass-price-change-pro/)
>
> ---


# Cambio masivo de precios pro

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.0.0 - 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para el funcionamiento general de PrestaShop y son suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

El módulo "Cambio masivo de precios pro" proporciona una interfaz completa dentro del Back Office de PrestaShop para definir y ejecutar sus cambios de precios. Todos los ajustes se acceden a través de la página de configuración principal del módulo.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Gestor de módulos > Cambio masivo de precios pro > Configurar)

Al entrar en la página de configuración del módulo, encontrará una serie de pestañas o secciones diseñadas para guiarle a través del proceso de definición de su operación de cambio de precios.

#### **Pestañas / Secciones principales:**

La configuración del módulo suele estar organizada en varias secciones clave, a menudo presentadas como pestañas o bloques distintos en la página principal. Aunque las etiquetas exactas pueden variar ligeramente entre versiones, la funcionalidad principal sigue siendo consistente:

1.  **Qué hacer (WTD):** Defina el tipo de cambio de precio.
2.  **Productos objetivo:** Seleccione qué productos se verán afectados.
3.  **Restricciones:** Añada condiciones adicionales para la segmentación.
4.  **Reglas:** Defina reglas de precios específicas.
5.  **Vista previa:** Vea el impacto antes de aplicar.
6.  **Historial:** Revise operaciones pasadas.
7.  **Programador:** Programe futuros cambios de precios.
8.  **Importar/Exportar CSV:** Gestione precios a través de CSV.
9.  **Configuración de Cron:** Configure tareas automatizadas.

Repasemos cada sección en detalle:

#### **4.1.1 Qué hacer (WTD)**

Esta sección es donde define la acción principal de su cambio de precio.

-   **Qué hace este ajuste:** Determina cómo se modificarán los precios de los productos. Puede elegir entre aumentar, disminuir o establecer un nuevo precio, y si esto se aplica al precio base, al precio específico o al impacto en las combinaciones.
-   **Efecto de cambiar este ajuste:**
    -   *Aumentar en porcentaje:* Añade un porcentaje del precio actual al producto.
    -   *Disminuir en porcentaje:* Resta un porcentaje del precio actual al producto.
    -   *Aumentar en cantidad fija:* Añade un valor monetario específico al precio del producto.
    -   *Disminuir en cantidad fija:* Resta un valor monetario específico al precio del producto.
    -   *Establecer nuevo precio en:* Sobrescribe el precio actual con un nuevo valor especificado.
    -   *Aplicar al precio base:* Modifica el precio principal del producto.
    -   *Aplicar al precio específico:* Modifica los precios establecidos a través de las reglas de "Precios específicos" (por ejemplo, para grupos, países o cantidad).
    -   *Aplicar al impacto en combinaciones:* Modifica el ajuste de precio para las combinaciones de productos (atributos).
-   **Valor recomendado:** Depende completamente de su objetivo comercial. Comience con un objetivo claro (por ejemplo, "aumentar todos los precios en un 5%") antes de seleccionar.
-   **Escenario / ejemplo de comerciante:**
    -   *Escenario 1 (Inflación):* "Necesito aumentar todos los precios de mis productos en un 3% debido al aumento de los costos de los proveedores." -> Seleccione "Aumentar en porcentaje", introduzca "3" y elija "Aplicar al precio base".
    -   *Escenario 2 (Venta de liquidación):* "Quiero reducir el precio de todos los productos de la categoría 'Colección de Verano' en 5 $." -> Seleccione "Disminuir en cantidad fija", introduzca "5" y elija "Aplicar al precio base".

#### **4.1.2 Productos objetivo**

Aquí es donde selecciona con precisión *qué* productos se verán afectados por el cambio de precio.

-   **Qué hace este ajuste:** Le permite filtrar productos basándose en varios criterios como categorías, fabricantes, proveedores, ID de producto específicos o incluso productos sin precio específico.
-   **Efecto de cambiar este ajuste:**
    -   *Seleccionar categorías:* Solo se considerarán los productos dentro de las categorías elegidas.
    -   *Seleccionar fabricantes/proveedores:* Solo se verán afectados los productos de estas marcas/fuentes.
    -   *Introducir ID de producto:* Solo se dirigirán los productos exactos que liste.
    -   *Filtrar por "Productos sin precio específico":* Útil para asegurarse de no anular accidentalmente las reglas de precios específicos existentes.
-   **Valor recomendado:** Sea lo más específico posible para evitar cambios no deseados. Utilice varios filtros si es necesario.
-   **Escenario / ejemplo de comerciante:**
    -   *Escenario 1 (Actualización de marca):* "Mi proveedor principal, 'Fashionista Co.', ha aumentado sus precios. Necesito actualizar todos los productos de este fabricante." -> Seleccione "Fabricante", luego elija "Fashionista Co.".
    -   *Escenario 2 (Stock estacional):* "Quiero poner en oferta todos los productos de la categoría 'Ropa de Invierno'." -> Seleccione "Categoría", luego elija "Ropa de Invierno".

#### **4.1.3 Restricciones**

Esta sección le permite añadir condiciones aún más específicas a la segmentación de sus productos.

-   **Qué hace este ajuste:** Proporciona opciones de filtrado avanzadas, como segmentar productos dentro de un cierto rango de precios, productos con características o atributos específicos, o productos que actualmente están en stock.
-   **Efecto de cambiar este ajuste:**
    -   *Rango de precios:* Solo se incluirán los productos cuyo precio actual se encuentre dentro del mínimo y máximo especificados.
    -   *Características/Atributos:* Diríjase a productos que tengan una característica particular (por ejemplo, "Color: Rojo") o atributo (por ejemplo, "Talla: XL").
    -   *Solo en stock:* Asegura que solo los productos actualmente disponibles para la compra se vean afectados.
-   **Valor recomendado:** Utilícelos para refinar aún más su lista de objetivos, especialmente para promociones complejas o ajustes basados en el inventario.
-   **Escenario / ejemplo de comerciante:**
    -   *Escenario 1 (Venta de productos premium):* "Quiero ofrecer un descuento en artículos de alto valor. Reducir los precios en un 10% para todos los productos de más de 100 $ en la categoría 'Electrónica'." -> En "Productos objetivo", seleccione "Electrónica". En "Restricciones", establezca "Rango de precios" de "100 $" a "Máx.".
    -   *Escenario 2 (Liquidación de stock específico):* "Necesito liquidar todas las camisas de color 'Azul' que están actualmente en stock." -> En "Productos objetivo", seleccione "Camisas". En "Restricciones", seleccione "Atributo: Color > Azul" y "Solo en stock".

#### **4.1.4 Reglas**

Esta sección le permite definir una lógica de precios más compleja, que potencialmente anula o añade a la acción general de "Qué hacer".

-   **Qué hace este ajuste:** Le permite crear ajustes de precios condicionales. Por ejemplo, "Si un producto está en la Categoría A, aumente su precio en un 5%, pero si está en la Categoría B, disminúyalo en un 10%."
-   **Efecto de cambiar este ajuste:** Permite estrategias de precios altamente matizadas donde diferentes grupos de productos reciben diferentes ajustes dentro de una sola operación.
-   **Valor recomendado:** Utilice esto cuando un cambio de precio único y uniforme no sea suficiente para todos los productos objetivo.
-   **Escenario / ejemplo de comerciante:**
    -   *Escenario (Descuento escalonado):* "Para los productos de la categoría 'Accesorios', si su precio está entre 10 $ y 50 $, disminuya en un 5%. Si su precio supera los 50 $, disminuya en un 10%." -> Aquí configuraría varias reglas, cada una con su propio rango de precios y ajuste.

#### **4.1.5 Vista previa**

Antes de confirmar cualquier cambio, esta sección crucial le permite revisar las modificaciones propuestas.

-   **Qué hace este ajuste:** Muestra una lista de productos que se verán afectados, mostrando su precio actual y cuál será su nuevo precio después de la operación.
-   **Efecto de cambiar este ajuste:** Esta es una sección de solo lectura. Proporciona una red de seguridad, permitiéndole detectar cualquier error en su segmentación o reglas antes de que se apliquen a su tienda en vivo.
-   **Valor recomendado:** **SIEMPRE** revise la vista previa cuidadosamente antes de proceder con el cambio de precio real.
-   **Escenario / ejemplo de comerciante:**
    -   *Escenario (Verificación doble):* "He configurado un descuento del 10% para todos los 'Vestidos de Verano'. La vista previa muestra un vestido que sé que no debería tener descuento. Puedo volver a 'Productos objetivo' o 'Restricciones' para refinar mi selección."

#### **4.1.6 Historial**

Esta sección mantiene un registro de todas las operaciones de cambio de precios pasadas.

-   **Qué hace este ajuste:** Muestra un registro de quién realizó qué cambio de precio, cuándo se hizo y qué tipo de operación fue.
-   **Efecto de cambiar este ajuste:** Este es un registro de solo lectura. Es invaluable para auditar, solucionar problemas y comprender decisiones de precios pasadas.
-   **Valor recomendado:** Revise el historial regularmente, especialmente si varias personas administran la tienda, para asegurarse de que todos los cambios sean intencionales y estén registrados.
-   **Escenario / ejemplo de comerciante:**
    -   *Escenario (Auditoría):* "Un cliente informó un precio incorrecto. Puedo consultar el historial para ver si un cambio masivo de precios reciente pudo haberlo causado y quién inició el cambio."

#### **4.1.7 Programador**

Planifique que sus cambios de precios se ejecuten automáticamente en una fecha y hora futuras.

-   **Qué hace este ajuste:** Le permite definir una operación de cambio de precios y configurarla para que se ejecute automáticamente en una fecha y hora especificadas. También puede configurarla para revertir los precios después de un cierto período, perfecto para ventas temporales.
-   **Efecto de cambiar este ajuste:**
    -   *Ejecución programada:* El cambio de precio se aplicará sin intervención manual en el momento elegido.
    -   *Revertir precios:* Los productos volverán a sus precios originales (o a un precio diferente especificado) después de que finalice el período de venta.
-   **Valor recomendado:** Esencial para gestionar promociones, ventas estacionales o cualquier cambio de precio que deba activarse fuera del horario comercial.
-   **Escenario / ejemplo de comerciante:**
    -   *Escenario (Venta de Black Friday):* "Quiero aplicar un descuento del 20% a todos los productos a las 00:00 del Black Friday y revertir a los precios originales a las 23:59 del Cyber Monday." -> Configure la operación de descuento, prográmela para el Black Friday y añada una programación de reversión para el Cyber Monday.

#### **4.1.8 Importar/Exportar CSV**

Gestione los precios de sus productos utilizando archivos CSV para un control avanzado o manipulación de datos externos.

-   **Qué hace este ajuste:**
    -   *Exportar:* Le permite exportar una lista de productos (basada en sus criterios de segmentación) con sus precios actuales a un archivo CSV.
    -   *Importar:* Le permite cargar un archivo CSV que contiene ID de producto y nuevos precios, aplicando estos cambios a su tienda.
-   **Efecto de cambiar este ajuste:**
    -   *Exportar:* Proporciona una hoja de cálculo de sus productos objetivo y sus precios, que se puede editar externamente.
    -   *Importar:* Sobrescribe o actualiza los precios de los productos listados en el CSV, ofreciendo una forma potente de gestionar listas de precios grandes y complejas.
-   **Valor recomendado:** Utilice la exportación para un análisis detallado o cuando necesite realizar ajustes de precios muy específicos y no formulados que sean más fáciles de gestionar en una hoja de cálculo. Utilice la importación cuando tenga una lista predefinida de nuevos precios de un proveedor o un sistema externo.
-   **Escenario / ejemplo de comerciante:**
    -   *Escenario (Lista de precios del proveedor):* "Mi proveedor me envió una nueva lista de precios para 500 productos. En lugar de actualizar cada uno manualmente, puedo exportar mi lista de productos actual, compararla con la del proveedor, ajustar los precios en el CSV y luego importarla de nuevo."

#### **4.1.9 Configuración de Cron**

Configure la tarea cron del módulo para tareas automatizadas, especialmente para cambios de precios programados.

-   **Qué hace este ajuste:** Proporciona el comando o la URL necesarios para configurar una tarea cron en su servidor. Esta tarea cron es esencial para que la función "Programador" funcione, ya que verifica y ejecuta periódicamente los cambios de precios programados.
-   **Efecto de cambiar este ajuste:**
    -   *Configuración correcta de Cron:* Asegura que sus cambios de precios programados se ejecuten automáticamente en los momentos especificados. Sin una tarea cron configurada correctamente, las tareas programadas no se ejecutarán.
-   **Valor recomendado:** Siga las instrucciones proporcionadas por el módulo para configurar la tarea cron en su servidor de alojamiento. Normalmente, esto implica añadir una línea al crontab de su servidor. El módulo suele proporcionar el comando exacto.
-   **Escenario / ejemplo de comerciante:**
    -   *Escenario (Ventas automatizadas):* "He programado una venta flash para la próxima semana. Para asegurarme de que comience exactamente a tiempo, necesito asegurarme de que la tarea cron esté configurada correctamente y se ejecute cada 5-15 minutos." -> Copie el comando cron proporcionado y añádalo al gestor de cron de su servidor.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Qué hacer** | Tipo de operación (Aumentar/Disminuir/Establecer) | N/A (depende del objetivo) | Define cómo se cambian los precios (por ejemplo, +5%, -10 $, establecer en 25 $). |
| | Valor (Porcentaje/Fijo) | N/A (depende del objetivo) | La cantidad o el porcentaje del ajuste de precio. |
| | Aplicar a (Base/Específico/Combinaciones) | Precio base | Determina qué tipo de precio se ve afectado. |
| **Productos objetivo** | Categorías | Seleccionar específicas | Filtra productos por categoría. |
| | Fabricantes | Seleccionar específicos | Filtra productos por marca. |
| | Proveedores | Seleccionar específicos | Filtra productos por proveedor. |
| | ID de producto | Introducir lista | Dirige productos específicos por ID. |
| | Productos sin precio específico | Sí/No | Excluye productos con precios específicos existentes. |
| **Restricciones** | Rango de precios (Mín/Máx) | N/A (opcional) | Filtra productos dentro de un rango de precios. |
| | Características / Atributos | Seleccionar específicos | Filtra productos por sus características o atributos. |
| | Solo en stock | Sí/No | Solo afecta a los productos actualmente en stock. |
| **Reglas** | Añadir regla | N/A (opcional) | Define ajustes de precios condicionales basados en criterios. |
| **Vista previa** | (Tabla de solo lectura) | N/A | Muestra los precios actuales frente a los nuevos para los productos afectados. **¡Siempre revise!** |
| **Historial** | (Registro de solo lectura) | N/A | Registra todas las operaciones de cambio de precios pasadas. |
| **Programador** | Programar operación | N/A (opcional) | Establece una fecha/hora futura para que los cambios de precios se ejecuten automáticamente. |
| | Revertir precios | N/A (opcional) | Programa una reversión de precios después de un período establecido. |
| **Importar/Exportar CSV** | Exportar productos | N/A (opcional) | Descarga datos de productos objetivo para edición externa. |
| | Importar precios | N/A (opcional) | Carga un CSV para aplicar nuevos precios a los productos. |
| **Configuración de Cron** | Comando Cron | Copiar del módulo | Esencial para tareas programadas automatizadas. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis precios no cambiaron después de aplicar la operación. ¿Qué salió mal?**
R1:

-   **Verifique la pestaña Historial:** Verifique que la operación se haya registrado y completado con éxito.
-   **Borrar caché:** PrestaShop utiliza caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché". Su navegador también podría estar almacenando datos antiguos en caché, así que intente borrar la caché de su navegador o ver la tienda en modo incógnito.
-   **Verifique la segmentación:** Revise la configuración de "Productos objetivo" y "Restricciones". ¿Excluyó accidentalmente los productos que pretendía cambiar?
-   **Precios específicos:** Si intentaba cambiar los precios base pero los productos tienen precios específicos, los precios específicos podrían estar anulándolos. Verifique si su operación se configuró para afectar "Precios específicos" o "Precio base".

**P2: Mi cambio de precio programado no se ejecutó a la hora especificada.**
R2:

-   **Tarea Cron:** La razón más común para esto es una tarea cron configurada incorrectamente o que no se está ejecutando. Vaya a la pestaña **Configuración de Cron** en la configuración del módulo. Asegúrese de que el comando cron proporcionado se haya añadido correctamente al crontab de su servidor y se esté ejecutando con la frecuencia recomendada (por ejemplo, cada 5-15 minutos). Si no está seguro de cómo hacerlo, póngase en contacto con su proveedor de alojamiento o con un webmaster.
-   **Módulo habilitado:** Asegúrese de que el módulo "Cambio masivo de precios pro" todavía esté habilitado en su Gestor de módulos.

**P3: Accidentalmente cambié los precios incorrectos. ¿Puedo revertir los cambios?**
R3:

-   **Pestaña Historial:** La pestaña "Historial" del módulo a menudo proporciona una opción para revertir una operación anterior. Busque un botón "Revertir" o "Deshacer" junto a la operación específica que desea revertir.
-   **Copia de seguridad de la base de datos:** Si una opción de reversión no está disponible o no funciona como se esperaba, esto resalta la importancia de tener una copia de seguridad reciente de la base de datos. Tendría que restaurar su base de datos a un punto anterior al cambio de precio erróneo. **¡Siempre haga una copia de seguridad antes de operaciones importantes!**

**P4: El módulo no se muestra correctamente o está causando errores después de la instalación.**
R4:

-   **Versión de PrestaShop:** Asegúrese de haber descargado e instalado la versión correcta del módulo para su instalación específica de PrestaShop (por ejemplo, PrestaShop 8.x, 1.7.x).
-   **Compatibilidad con PHP:** Verifique que la versión de PHP de su servidor esté dentro del rango compatible del módulo (PHP 5.6 - 8.5).
-   **Conflictos de tema:** A veces, los temas personalizados pueden interferir. Cambie temporalmente al tema predeterminado de PrestaShop para ver si el problema se resuelve. Si lo hace, su tema podría requerir ajustes.
-   **Registros de errores:** Verifique su modo de depuración de PrestaShop (si está habilitado) o los registros de errores de PHP de su servidor para ver mensajes de error específicos. Estos pueden proporcionar pistas para los desarrolladores.

**P5: ¿Cómo traduzco el texto del módulo a otros idiomas?**
R5:

-   En su Back Office de PrestaShop, navegue a **Internacional > Traducciones**.
-   Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Cambio masivo de precios pro" en el menú desplegable del módulo.
-   Luego puede traducir todas las cadenas del módulo a los idiomas deseados.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Cambio masivo de precios pro".

### 4.1 Descripción general de la arquitectura

El módulo "Cambio masivo de precios pro" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para su funcionalidad principal y `ModuleFrontController` para tareas específicas del front-office como la ejecución de cron. El módulo depende en gran medida de su `index.php` (archivo principal del módulo) para la configuración y el procesamiento del back-office, utilizando plantillas Smarty para renderizar varias secciones de configuración. Integra JavaScript personalizado para elementos de interfaz de usuario mejorados como la segmentación de productos y el autocompletado, y CSS para el estilo. Si bien no define explícitamente clases `ObjectModel` en el inventario proporcionado, es probable que interactúe directamente con las tablas principales `Product`, `SpecificPrice` y `Configuration` de PrestaShop.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

-   `controllers/front/cron.php`
    -   **Nombre de la clase:** `MassPriceProCronModuleFrontController` (probablemente, según la convención de nombres de archivos)
    -   **Clase padre:** `ModuleFrontController`
    -   **Responsabilidad:** Este controlador está diseñado para ser llamado por una tarea cron del lado del servidor. Su función principal es ejecutar operaciones de cambio de precios programadas definidas dentro de la configuración del back-office del módulo. Procesa tareas como aplicar descuentos programados, revertir precios o ejecutar otros ajustes de precios automatizados. Normalmente devuelve un mensaje simple de éxito/fracaso o registra su actividad.
-   `controllers/front/index.php`
    -   **Nombre de la clase:** `MassPriceProIndexModuleFrontController` (probablemente)
    -   **Clase padre:** `ModuleFrontController`
    -   **Responsabilidad:** Este controlador podría servir como un punto de entrada general para acciones del módulo de front-office que no encajan en una categoría específica, o podría ser un marcador de posición. Dada la naturaleza del módulo, es menos probable que tenga una funcionalidad directa orientada al cliente y más probable que maneje solicitudes AJAX en segundo plano o recuperación de datos específicos si es necesario para scripts de front-end.

#### Controladores de administración de Back-Office

El módulo no parece utilizar archivos `AdminController` dedicados según el inventario proporcionado. Toda la configuración y el procesamiento del back-office probablemente se manejan directamente dentro del método `getContent()` del archivo principal `masspricepro/index.php`.

### 4.3 Clases y modelos principales (`classes/`)

Según el inventario proporcionado, no hay clases personalizadas ni definiciones de `ObjectModel` dentro de un directorio `classes/`. Esto sugiere que el módulo interactúa directamente con las clases `ObjectModel` principales de PrestaShop `Product`, `SpecificPrice`, `Category`, `Manufacturer`, `Supplier`, `Configuration` y potencialmente otras relacionadas, así como con sus tablas de base de datos asociadas. La lógica de cambio de precios probablemente está encapsulada dentro de los métodos de la clase principal `MassPricePro` (en `index.php`).

### 4.4 Activos de JavaScript (`views/js/`)

-   `masspricepro/lib/searchTool/views/js/autocomplete.js`
    -   **Alcance:** Probablemente tanto Front-office (si se usa para la búsqueda de productos) como Back-office (para la segmentación de productos).
    -   **Detalles:** Proporciona funcionalidad genérica de autocompletado. Escucha la entrada del usuario en los campos de texto, envía solicitudes AJAX a un punto final de backend (posiblemente `controllers/front/index.php` o un controlador AJAX dedicado en el archivo principal del módulo) y muestra sugerencias en una lista desplegable.
-   `masspricepro/views/js/jquery.autocomplete.js`
    -   **Alcance:** Probablemente Back-office.
    -   **Detalles:** Un complemento de autocompletado basado en jQuery. Esta podría ser una implementación específica o una dependencia para las interfaces de selección de productos del módulo en el back office, como cuando se segmentan productos por nombre o ID. Maneja la representación de la interfaz de usuario de las sugerencias y los eventos de selección.
-   `masspricepro/views/js/mpp_pro.js`
    -   **Alcance:** Back-office.
    -   **Detalles:** Este es probablemente el archivo JavaScript principal para la configuración del back-office del módulo. Contendría:
        -   Detectores de eventos para envíos de formularios, cambios de pestaña, clics de botones (por ejemplo, "Aplicar cambios", "Vista previa", "Añadir regla").
        -   Llamadas AJAX al método `getContent()` o a un controlador frontal para el procesamiento de datos (por ejemplo, generar vistas previas, guardar configuraciones, ejecutar cambios de precios).
        -   Manipulación del DOM para mostrar/ocultar secciones dinámicamente, actualizar tablas de vista previa o gestionar entradas de reglas.
        -   Lógica de validación para campos de formulario.
-   `masspricepro/views/js/mpp_target_products.js`
    -   **Alcance:** Back-office.
    -   **Detalles:** Maneja específicamente la lógica para la sección "Productos objetivo" del módulo. Esto incluiría:
        -   Gestión de la selección de categorías, fabricantes, proveedores (por ejemplo, utilizando menús desplegables de selección múltiple o vistas de árbol).
        -   Manejo de la entrada para ID de producto, potencialmente con validación.
        -   Interacción con los scripts de autocompletado para permitir a los administradores buscar y seleccionar productos.
        -   Actualización dinámica de la lista de productos objetivo seleccionados.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `masspricepro/lib/searchTool/views/css/autocomplete.css`
    -   **Alcance:** Tanto Front-office como Back-office.
    -   **Detalles:** Proporciona estilo para los menús desplegables de sugerencias de autocompletado y los campos de entrada, asegurando que sean visualmente consistentes y fáciles de usar.
-   `masspricepro/views/css/mpp_admin.css`
    -   **Alcance:** Estilo del formulario de administración del Back-office.
    -   **Detalles:** Esta es la hoja de estilo principal para la interfaz de configuración del módulo en el Back Office de PrestaShop. Estiliza:
        -   El diseño de las pestañas/secciones de configuración.
        -   Elementos del formulario (entradas, botones, selecciones, casillas de verificación).
        -   Tablas (por ejemplo, para historial, vista previa).
        -   Cualquier componente de interfaz de usuario personalizado específico del módulo.
        -   Selectores de clase CSS clave que los desarrolladores pueden anular: `.mpp-container`, `.mpp-tab-content`, `.mpp-form-group`, `.mpp-table`, etc.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

#### Plantillas de administración (`views/templates/admin/`)

Estas plantillas se renderizan dentro del método `getContent()` del archivo principal del módulo para construir la interfaz de configuración del back-office.

-   `constraints.tpl`: Renderiza la sección para definir restricciones adicionales (por ejemplo, rango de precios, características, atributos).
-   `cron_setup.tpl`: Muestra instrucciones y el comando para configurar la tarea cron del servidor.
-   `csv.tpl`: Renderiza la interfaz para la funcionalidad de importación CSV.
-   `csv_export_target.tpl`: Renderiza la interfaz para la funcionalidad de exportación CSV, específicamente para productos objetivo.
-   `history.tpl`: Muestra la tabla y los detalles de las operaciones de cambio de precios pasadas.
-   `mpp_operation_block.tpl`: Probablemente un bloque reutilizable para definir una única operación de cambio de precios (aumentar/disminuir/establecer).
-   `mpp_target_block.tpl`: Probablemente un bloque reutilizable para definir criterios de segmentación de productos.
-   `mpp_target_products_full.tpl`: Renderiza la interfaz completa para seleccionar productos objetivo, posiblemente incluyendo campos de autocompletado y listas de productos seleccionados.
-   `preview.tpl`: Muestra la tabla con los precios actuales y los nuevos precios propuestos antes de la ejecución.
-   `rules.tpl`: Renderiza la interfaz para definir reglas de precios condicionales.
-   `scheduler.tpl`: Muestra el formulario para programar futuros cambios de precios y reversiones.
-   `target_products.tpl`: Una plantilla más concisa o alternativa para la segmentación de productos, potencialmente utilizada dentro de otras secciones.
-   `wtd.tpl`: Renderiza la sección "Qué hacer", donde se selecciona el tipo principal de ajuste de precio.

#### Plantillas de gancho (`views/templates/hook/`)

-   `form.tpl`: Esta plantilla probablemente se utiliza para renderizar el formulario de configuración principal o una parte específica del mismo cuando el módulo se engancha a un gancho de visualización genérico (aunque el módulo utiliza principalmente `getContent()` para su configuración principal). Dado el propósito del módulo, es poco probable que muestre algo directamente en el front office a través de ganchos como `displayHeader` o `displayFooter`, sino que utiliza estos ganchos para cargar activos o procesamiento interno.

### 4.7 Esquema de la base de datos y mapa de ganchos

#### Tablas de la base de datos

El módulo no crea tablas SQL personalizadas según el inventario proporcionado. Se basa principalmente en las tablas principales de PrestaShop:

-   `ps_product`: Para precios base de productos.
-   `ps_product_shop`: Para precios de productos específicos de la tienda.
-   `ps_specific_price`: Para reglas de precios específicos.
-   `ps_product_attribute`, `ps_product_attribute_shop`: Para precios e impactos de combinaciones.
-   `ps_category_product`, `ps_manufacturer`, `ps_supplier`: Para la segmentación de productos.
-   `ps_configuration`: Para almacenar la configuración y los valores de configuración del módulo (por ejemplo, `MPP_LAST_OPERATION_DATE`, `MPP_CRON_TOKEN`, `MPP_SCHEDULED_TASKS`).

#### Tabla de ganchos registrados

El módulo probablemente registra ganchos para integrarse con el ciclo de vida de PrestaShop y mostrar activos.

| Nombre del gancho | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Para cargar CSS específico del módulo (`mpp_admin.css` si es necesario por alguna razón, aunque poco probable para el front-office) y JavaScript (`autocomplete.js`, `jquery.autocomplete.js` si se usa para la búsqueda en el front-end). |
| `actionModuleInstall` | Durante la instalación del módulo. | Para realizar la configuración inicial, crear entradas de configuración y registrar otros ganchos. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Para limpiar entradas de configuración y anular el registro de ganchos. |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración. | Para cargar CSS específico del Back-office (`mpp_admin.css`) y JavaScript (`mpp_pro.js`, `mpp_target_products.js`, `autocomplete.js`) para la página de configuración del módulo. |
| `actionScheduler` (o gancho personalizado similar) | Activado por la tarea cron del módulo. | Para ejecutar cambios de precios programados y operaciones de reversión. Este es un gancho interno personalizado o un método llamado por el controlador `cron.php`. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Cambio masivo de precios pro", consulte su cuenta de cliente en MyPresta.eu. Puede descargar las versiones más recientes desde su historial de pedidos y acceder a los recursos de soporte directamente a través de la plataforma.

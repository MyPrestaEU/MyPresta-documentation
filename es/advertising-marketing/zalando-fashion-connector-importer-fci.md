---
title: "Importador de Zalando Fashion Connector (FCI) - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Importador de Zalando Fashion Connector (FCI) de MyPresta.eu."
sidebar:
  label: "Importador de Zalando Fashion Connector (FCI) - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Zalando Fashion Connector Importer (FCI) en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/zalando-fashion-connector-importer-fci.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/zalando-fashion-connector-importer-fci/)
>
> ---


# Importador de Zalando Fashion Connector (FCI)

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para la mayoría de los módulos de PrestaShop y generalmente están disponibles en cualquier entorno de alojamiento moderno.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Importador de Zalando Fashion Connector (FCI))

Esta es la pantalla de configuración principal donde establece los parámetros básicos para su feed de Zalando.

-   **Qué hace este ajuste:** Esta sección le permite definir la información central que se incluirá en su feed de productos de Zalando.
-   **Efecto de cambiar este ajuste:** Los valores que establezca aquí influirán directamente en los datos que Zalando recibe sobre sus productos, afectando cómo se muestran y gestionan en su plataforma.

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo del comerciante |
| --- | --- | --- | --- | --- |
| **Tienda** | Especifica el nombre de su tienda tal como debe aparecer en Zalando. Esto ayuda a Zalando a identificar su punto de venta específico. | *Cuando se establece:* El nombre de su tienda especificado se incluirá en el feed de productos. *Cuando se deja vacío:* Zalando podría usar un identificador predeterminado o rechazar el feed si el nombre de la tienda es obligatorio. | El nombre real de su tienda (por ejemplo, "Mi Boutique de Moda") | Si tiene varias tiendas físicas o marcas, esto ayuda a Zalando a diferenciar su inventario. |
| **EAN (Número de Artículo Europeo)** | Determina si el EAN (código de barras) de sus productos debe incluirse en el feed. Los EAN son cruciales para la identificación del producto. | *Cuando está habilitado:* Los EAN serán parte del feed, permitiendo a Zalando hacer coincidir sus productos con precisión. *Cuando está deshabilitado:* Los productos podrían no ser identificados correctamente o podrían ser rechazados por Zalando si el EAN es un campo obligatorio. | SÍ | Esencial para la mayoría de los listados de productos, especialmente en moda, para asegurar una identificación única. |
| **Precio** | Controla si el precio de venta del producto se incluye en el feed. | *Cuando está habilitado:* El precio de venta actual de su tienda PrestaShop se enviará a Zalando. *Cuando está deshabilitado:* Zalando no recibirá actualizaciones de precios, lo que podría llevar a precios desactualizados en su plataforma. | SÍ | Crucial para asegurar que los clientes vean el precio correcto en Zalando. |
| **Precio de Venta al Público** | Determina si se incluye el precio de venta al público original (a menudo el precio "tachado" para descuentos). | *Cuando está habilitado:* El precio original se enviará, permitiendo a Zalando mostrar ahorros o promociones. *Cuando está deshabilitado:* Solo se enviará el precio de venta actual, ocultando potencialmente la información de descuento. | SÍ (si usa precios de venta al público para promociones) | Si realiza ventas, incluir el precio de venta al público ayuda a destacar el descuento a los clientes en Zalando. |
| **Cantidad** | Especifica si la cantidad de stock actual de sus productos se incluye en el feed. | *Cuando está habilitado:* Sus niveles de stock de productos se actualizarán en Zalando, evitando la sobreventa. *Cuando está deshabilitado:* Zalando no recibirá actualizaciones de stock, lo que provocará posibles discrepancias y la insatisfacción del cliente si un artículo está agotado. | SÍ | Absolutamente crítico para evitar vender productos que ya no tiene disponibles. |
| **Nombre del Producto** | Controla si el nombre del producto se incluye en el feed. | *Cuando está habilitado:* El nombre del producto de su tienda PrestaShop se enviará a Zalando. *Cuando está deshabilitado:* Los productos podrían listarse sin nombres o ser rechazados si este es un campo obligatorio. | SÍ | Esencial para que los clientes identifiquen y busquen sus productos en Zalando. |
| **ID de Cliente (zf\_client)** | Su identificador de cliente único proporcionado por Zalando para el acceso a la API. | *Cuando se introduce correctamente:* Permite que el módulo se autentique con los sistemas de Zalando. *Cuando es incorrecto o está vacío:* La generación y las actualizaciones del feed fallarán. | El ID proporcionado por Zalando | Debe obtenerlo de su gestor de cuentas de Zalando Connected Retail. |
| **Clave API (zf\_api)** | Su clave API única proporcionada por Zalando para una comunicación segura. | *Cuando se introduce correctamente:* Habilita la transferencia segura de datos entre su tienda y Zalando. *Cuando es incorrecto o está vacío:* La generación y las actualizaciones del feed fallarán debido a problemas de autenticación. | La clave proporcionada por Zalando | Esta es una credencial de seguridad; manténgala confidencial y obténgala de Zalando. |

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 Configuración de Exportación de Productos (Back Office > Zalando FCI > Exportar Productos)

Esta pantalla, accesible a través del menú del back office de PrestaShop, es donde define los parámetros detallados para generar su feed de productos para Zalando. Permite ajustar qué datos se incluyen y cómo se formatean.

-   **Nombre de la Pantalla y Ubicación del Menú:** **Zalando FCI > Exportar Productos** (Esto aparecerá como un nuevo elemento de menú en la navegación de su Back Office de PrestaShop).
-   **Acciones y Ajustes Disponibles:** Esta pantalla presenta un formulario con numerosas opciones para personalizar la exportación de sus productos. Encontrará campos para seleccionar tiendas, monedas, atributos de productos y opciones de filtrado.
-   **Efecto de los cambios:** Los cambios aquí impactan directamente el contenido y la estructura del archivo de feed de productos generado. Una configuración incorrecta puede llevar a que Zalando rechace su feed o muestre información incorrecta del producto.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Inicialmente, configure todos los ajustes cuidadosamente de acuerdo con las especificaciones de Zalando y las necesidades de su tienda.
    2.  Genere un feed de prueba y valídelo con Zalando (si es posible) para asegurarse de que todos los datos sean correctos.
    3.  Una vez configurado, utilizará principalmente esta pantalla para generar el feed manualmente cuando sea necesario, o configurará un trabajo cron (una tarea programada) para automatizar la generación del feed basándose en estos ajustes.

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo del comerciante |
| --- | --- | --- | --- | --- |
| **Recordar Ajustes (zf\_remember\_settings)** | Si está habilitado, el módulo recordará sus últimas configuraciones de exportación elegidas para mayor comodidad. | *Cuando está habilitado:* Sus selecciones en esta página persistirán para futuras exportaciones. *Cuando está deshabilitado:* Los ajustes volverán a los valores predeterminados cada vez que visite la página. | SÍ | Ahorra tiempo si genera feeds con frecuencia con los mismos parámetros. |
| **Formato de Archivo de Exportación (zf\_export\_file\_format)** | Selecciona el formato de salida para el archivo de feed de productos (por ejemplo, CSV, XML). | *Cuando se establece:* El archivo generado estará en el formato elegido. *Cuando es incorrecto:* Zalando podría no ser capaz de procesar el archivo. | Verifique los requisitos de Zalando (generalmente CSV o XML) | Zalando especificará el formato requerido para su sistema de importación. |
| **Tipo de Exportación (zf\_export\_type)** | Define qué tipo de productos exportar (por ejemplo, todos los productos, solo activos, solo categorías específicas). | *Cuando se establece:* Solo se incluirán los productos que coincidan con los criterios. *Cuando es incorrecto:* Podría exportar demasiados o muy pocos productos. | Todos los productos activos, o según la incorporación de Zalando | Si solo desea listar un subconjunto de su catálogo en Zalando. |
| **Tienda (zf\_export\_store)** | Le permite seleccionar de qué tienda PrestaShop (en una configuración multi-tienda) exportar productos. | *Cuando se selecciona:* Se exportarán productos de esa tienda específica. *Cuando es incorrecto:* Podrían incluirse productos de la tienda equivocada. | Su tienda principal, o la tienda relevante para Zalando | Para comerciantes que operan varias tiendas distintas desde una instalación de PrestaShop. |
| **Delimitador (zf\_export\_delimiter)** | Especifica el carácter utilizado para separar los campos de datos en el archivo de exportación (por ejemplo, coma, punto y coma). | *Cuando se establece:* Se utilizará el delimitador elegido. *Cuando es incorrecto:* El archivo será ilegible para Zalando. | Verifique los requisitos de Zalando (a menudo coma o punto y coma) | Crucial para archivos CSV para asegurar que los datos se analicen correctamente. |
| **Moneda (zf\_export\_currency)** | Selecciona la moneda para los precios de los productos en el archivo de exportación. | *Cuando se selecciona:* Los precios se convertirán o se mostrarán en esta moneda. *Cuando es incorrecto:* Zalando podría mostrar precios incorrectos o rechazar el feed. | La moneda requerida por Zalando (por ejemplo, EUR) | Si su tienda opera en varias monedas, asegúrese de exportar en la que Zalando espera. |
| **Formato del Nombre del Producto (zf\_export\_product\_name\_format)** | Define cómo se formatean los nombres de los productos (por ejemplo, incluir fabricante, atributos). | *Cuando se establece:* Los nombres de los productos seguirán este formato. *Cuando es incorrecto:* Los nombres podrían ser poco claros o no cumplir con las directrices de Zalando. | Según las recomendaciones de Zalando para mayor claridad | Para asegurar que los nombres de los productos sean informativos y consistentes en Zalando. |
| **Incluir Impuestos (zf\_export\_tax)** | Determina si los precios de los productos en el feed deben incluir impuestos. | *Cuando está habilitado:* Los precios incluirán impuestos. *Cuando está deshabilitado:* Los precios no incluirán impuestos. | Verifique los requisitos de Zalando para la visualización de precios | Importante para el cumplimiento fiscal y la visualización correcta de precios en Zalando. |
| **Exportar Precios por País (zf\_export\_country\_prices)** | Si está habilitado, se incluirán los precios específicos de diferentes países (si están configurados en PrestaShop). | *Cuando está habilitado:* Se exportarán los precios específicos de cada país. *Cuando está deshabilitado:* Solo se exportarán los precios predeterminados. | SÍ (si tiene precios específicos por país) | Para vendedores internacionales con estrategias de precios variadas por región. |
| **País Predeterminado (PS\_COUNTRY\_DEFAULT)** | El país predeterminado para su tienda PrestaShop, utilizado como respaldo para algunos ajustes. | *Cuando se establece:* Proporciona un país base para los cálculos de precios e impuestos. | El país principal de su tienda | Asegura un comportamiento predeterminado consistente para la configuración internacional. |
| **Exportar Solo Productos Activos (zf\_export\_active)** | Si está habilitado, solo se exportarán los productos actualmente marcados como "activos" en PrestaShop. | *Cuando está habilitado:* Solo se envían los productos disponibles. *Cuando está deshabilitado:* Podrían incluirse productos inactivos, lo que provocaría errores en Zalando. | SÍ | Evita listar productos que no desea vender o que ya no están disponibles. |
| **Exportar Fabricantes (zf\_export\_manufacturers)** | Si está habilitado, la información del fabricante se incluirá en el feed. | *Cuando está habilitado:* Se envían los datos del fabricante. *Cuando está deshabilitado:* Se omiten los datos del fabricante. | SÍ | Útil para que los clientes filtren por marca en Zalando. |
| **Exportar Proveedores (zf\_export\_suppliers)** | Si está habilitado, la información del proveedor se incluirá en el feed. | *Cuando está habilitado:* Se envían los datos del proveedor. *Cuando está deshabilitado:* Se omiten los datos del proveedor. | NO (a menos que lo requiera Zalando) | Menos común para feeds orientados al cliente, más para seguimiento interno. |
| **Exportar Categoría (zf\_export\_category)** | Si está habilitado, se incluirá la información de la categoría del producto. | *Cuando está habilitado:* Se envían los datos de la categoría. *Cuando está deshabilitado:* Se omiten los datos de la categoría. | SÍ | Ayuda a Zalando a categorizar sus productos correctamente y facilita la navegación del cliente. |
| **Exportar Solo Productos en Stock (zf\_export\_instock)** | Si está habilitado, solo se exportarán los productos con stock disponible. | *Cuando está habilitado:* Solo se envían los productos que puede cumplir. *Cuando está deshabilitado:* Podrían incluirse productos agotados, lo que provocaría problemas de sobreventa. | SÍ | Crucial para evitar la decepción del cliente debido a artículos no disponibles. |
| **Excluir Precio Máximo (zf\_export\_exclude\_price\_max)** | Si está habilitado, los productos por encima de un cierto umbral de precio se excluirán del feed. | *Cuando está habilitado:* Los productos que excedan el precio máximo no se exportarán. *Cuando está deshabilitado:* Todos los productos, independientemente del precio, se exportan. | NO (a menos que tenga artículos específicos de alto valor para excluir) | Útil si Zalando tiene límites de precios o si solo desea vender ciertos rangos de precios en su plataforma. |
| **Valor de Exclusión de Precio Máximo (zf\_export\_exclude\_price\_price\_max\_v)** | El valor de precio máximo para el ajuste "Excluir Precio Máximo". | *Cuando se establece:* Define el límite superior de precio para los productos exportados. | Dejar vacío si no se excluye por precio máximo | Si solo desea vender artículos por debajo de 500 € en Zalando, establezca esto en 500. |

#### 2.2.2 Pantalla de Índice de Administración (Back Office > Zalando FCI > Índice)

Esta pantalla probablemente sirve como página de inicio o una vista de gestión simple para el módulo, mostrando potencialmente información o proporcionando enlaces rápidos.

-   **Nombre de la Pantalla y Ubicación del Menú:** **Zalando FCI > Índice** (Esto aparecerá como un nuevo elemento de menú en la navegación de su Back Office de PrestaShop, a menudo el primer elemento debajo del menú principal del módulo).
-   **Acciones y Ajustes Disponibles:** Esta pantalla suele mostrar una cuadrícula o un panel informativo simple. Podría mostrar la fecha de la última exportación, un enlace para generar el feed o el estado general del módulo. Generalmente no es una pantalla para una configuración detallada, sino más bien para una visión general o acciones rápidas.
-   **Efecto de los cambios:** Normalmente no hay "ajustes" directos para cambiar en esta pantalla. Su propósito es más informativo o de navegación.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esto como un punto de entrada rápido al módulo, para verificar el estado de su última exportación o para navegar a la pantalla "Exportar Productos" para una configuración detallada y la generación del feed.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Tienda | El Nombre de Su Tienda | Identifica su tienda en Zalando. |
| **Configuración del Módulo** | EAN | SÍ | Esencial para la identificación del producto. |
| **Configuración del Módulo** | Precio | SÍ | Asegura precios correctos en Zalando. |
| **Configuración del Módulo** | Precio de Venta al Público | SÍ (si se usa) | Muestra el precio original para promociones. |
| **Configuración del Módulo** | Cantidad | SÍ | Crítico para niveles de stock precisos, evita la sobreventa. |
| **Configuración del Módulo** | Nombre del Producto | SÍ | Esencial para la identificación y búsqueda de productos. |
| **Configuración del Módulo** | ID de Cliente (zf\_client) | Proporcionado por Zalando | Autentica con la API de Zalando. |
| **Configuración del Módulo** | Clave API (zf\_api) | Proporcionado por Zalando | Asegura la comunicación con la API de Zalando. |
| **Exportar Productos** | Recordar Ajustes | SÍ | Ahorra tiempo al preservar las opciones de exportación. |
| **Exportar Productos** | Formato de Archivo de Exportación | Verifique los requisitos de Zalando | Define el tipo de archivo de salida. |
| **Exportar Productos** | Tipo de Exportación | Todos los productos activos | Controla qué productos se incluyen. |
| **Exportar Productos** | Tienda | Su tienda principal | Selecciona productos de una tienda específica (multi-tienda). |
| **Exportar Productos** | Delimitador | Verifique los requisitos de Zalando | Separa campos en archivos CSV. |
| **Exportar Productos** | Moneda | Requerida por Zalando (por ejemplo, EUR) | Establece la moneda para los precios exportados. |
| **Exportar Productos** | Formato del Nombre del Producto | Según las recomendaciones de Zalando | Formatea los nombres de los productos para mayor claridad. |
| **Exportar Productos** | Incluir Impuestos | Verifique los requisitos de Zalando | Determina si los precios incluyen impuestos. |
| **Exportar Productos** | Exportar Precios por País | SÍ (si aplica) | Incluye precios específicos por país. |
| **Exportar Productos** | País Predeterminado | El país principal de su tienda | Respaldo para ajustes relacionados con el país. |
| **Exportar Productos** | Exportar Solo Productos Activos | SÍ | Evita listar productos inactivos. |
| **Exportar Productos** | Exportar Fabricantes | SÍ | Incluye información de la marca. |
| **Exportar Productos** | Exportar Proveedores | NO (a menos que sea requerido) | Incluye información del proveedor. |
| **Exportar Productos** | Exportar Categoría | SÍ | Ayuda a Zalando a categorizar productos. |
| **Exportar Productos** | Exportar Solo Productos en Stock | SÍ | Evita listar artículos agotados. |
| **Exportar Productos** | Excluir Precio Máximo | NO (a menos que sea necesario) | Excluye productos por encima de un precio establecido. |
| **Exportar Productos** | Valor de Exclusión de Precio Máximo | Dejar vacío si no se excluye | Establece el precio máximo para la exclusión. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mis productos no aparecen en Zalando, o el feed está siendo rechazado. ¿Qué debo verificar primero?**
R1:

-   **Verificar la Configuración del Módulo:** Vaya a **Módulos > Gestor de Módulos > Importador de Zalando Fashion Connector (FCI) > Configurar**. Asegúrese de que su "ID de Cliente" y "Clave API" estén correctamente ingresados según lo proporcionado por Zalando.
-   **Verificar la Configuración de Exportación:** Navegue a **Zalando FCI > Exportar Productos**. Verifique que el "Formato de Archivo de Exportación" y el "Delimitador" coincidan exactamente con los requisitos de Zalando. Además, asegúrese de que "Exportar Solo Productos Activos" y "Exportar Solo Productos en Stock" estén habilitados si solo desea enviar artículos disponibles.
-   **Validar Datos del Producto:** Asegúrese de que sus productos en PrestaShop tengan EAN, nombres, precios y cantidades de stock válidos. Los datos faltantes o inválidos son una razón común para los rechazos.
-   **Borrar Caché:** A veces, los datos antiguos pueden persistir. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).

**P2: Los precios o niveles de stock en Zalando no se actualizan correctamente.**
R2:

-   **Verificar la Frecuencia de Exportación:** ¿Con qué frecuencia está generando el feed? Si lo hace manualmente, debe hacerlo regularmente. Si ha configurado un trabajo cron, asegúrese de que se esté ejecutando con la frecuencia deseada (por ejemplo, cada hora).
-   **Configuración del Módulo:** Verifique que "Precio" y "Cantidad" estén habilitados en la pantalla de configuración principal del módulo.
-   **Tiempo de Procesamiento de Zalando:** Recuerde que incluso después de generar y enviar el feed, los sistemas de Zalando necesitan tiempo para procesar y actualizar los datos. Esto a veces puede llevar desde unos minutos hasta varias horas, dependiendo de su carga.

**P3: Tengo un tema personalizado y la interfaz de administración del módulo se ve un poco extraña.**
R3:

-   La interfaz de administración del módulo utiliza el estilo estándar de PrestaShop, pero pueden ocurrir pequeñas inconsistencias visuales con temas de back-office altamente personalizados. Esto generalmente no afecta la funcionalidad.
-   Si es un problema significativo, póngase en contacto con el soporte de MyPresta.eu. Para pequeños ajustes, un desarrollador web a menudo puede modificar el archivo `zalandofci/views/admin-theme.css` o agregar CSS personalizado a su back office de PrestaShop.

**P4: ¿Cómo configuro un trabajo cron para automatizar la generación del feed?**
R4:

-   Los pasos exactos dependen de su proveedor de alojamiento. Normalmente, encontrará una sección de "Trabajos Cron" o "Tareas Programadas" en el panel de control de su alojamiento (por ejemplo, cPanel, Plesk).
-   Necesitará la URL que activa la generación del feed. Esta URL generalmente se proporciona en la página de configuración "Exportar Productos" del módulo después de guardar sus ajustes, o se puede construir utilizando la ruta del controlador frontal (por ejemplo, `sutienda.com/module/zalandofci/feed`).
-   Configure el trabajo cron para ejecutar esta URL en el intervalo deseado (por ejemplo, `wget -q -O /dev/null "http://sutienda.com/module/zalandofci/feed"`). Si no está seguro, consulte la documentación o el soporte de su proveedor de alojamiento.

**P5: El módulo está instalado, pero no veo "Zalando FCI" en el menú de mi Back Office.**
A5:

-   **Borrar Caché de PrestaShop:** Vaya a **Parámetros Avanzados > Rendimiento** y borre la caché. A veces, el menú no se actualiza inmediatamente después de la instalación del módulo.
-   **Verificar el Estado del Módulo:** Vaya a **Módulos > Gestor de Módulos** y busque "Importador de Zalando Fashion Connector (FCI)". Asegúrese de que esté listado como "Instalado" y "Habilitado".
-   **Permisos:** En casos raros, los permisos de los empleados pueden restringir la visibilidad del menú. Verifique **Administración > Permisos** para su perfil de empleado.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo Importador de Zalando Fashion Connector (FCI) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando los principios MVC cuando corresponde. Se centra principalmente en la exportación de datos, utilizando una combinación de controladores frontales y de administración. La lógica central reside en el archivo principal del módulo y en los controladores de administración para la configuración y la generación del feed. No parece utilizar clases `ObjectModel` personalizadas, sino que consulta directamente la base de datos de PrestaShop para obtener datos de productos. La función principal del módulo es generar un feed de datos, que normalmente es consumido por un sistema externo (Zalando) a través de una tarea programada (trabajo cron) que accede a un controlador frontal.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

Estos controladores son accesibles desde la URL del front-office y se utilizan típicamente para generar el feed de productos, a menudo activados por un trabajo cron.

-   `controllers/front/feed.php`
    -   **Nombre de la clase y clase padre**: `ZalandofciFeedModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad**: Este es el punto final principal para generar el feed de productos. Responde a las solicitudes (típicamente de trabajos cron) y genera dinámicamente los datos del producto basándose en la configuración del módulo. Probablemente obtiene información del producto (EAN, precio, cantidad, nombre) y la formatea en la salida especificada (por ejemplo, CSV, XML) para Zalando. Este controlador no renderiza una página visual, sino que produce datos sin procesar.
-   `controllers/front/index.php`
    -   **Nombre de la clase y clase padre**: `ZalandofciIndexModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad**: Este controlador probablemente sirve como un respaldo o un punto de entrada simple, potencialmente redirigiendo o mostrando un mensaje mínimo. En muchos módulos, un controlador frontal `index.php` está presente para evitar la lista de directorios o proporcionar una acción predeterminada si no se solicita ninguna acción específica.

#### Controladores de Administración del Back-Office

Estos controladores gestionan la configuración del módulo y los ajustes de exportación de productos dentro del Back Office de PrestaShop.

-   `controllers/admin/AdminExportProductsFci.php`
    -   **Nombre de la pestaña y entidad gestionada**: "Exportar Productos" bajo el menú "Zalando FCI". Este controlador gestiona la configuración detallada de la exportación de productos.
    -   **Responsabilidad**: Este controlador maneja la visualización y el envío del formulario de exportación de productos. Recupera la configuración (por ejemplo, `zf_export_file_format`, `zf_export_type`, `zf_export_currency`, `zf_export_tax`, `zf_export_active`, etc.) de `ps_configuration`, procesa la entrada del usuario y activa la lógica real de recuperación y formato de datos del producto para la generación del feed. Probablemente utiliza métodos de `AdminController` para la renderización del formulario (`renderForm`) y el guardado (`postProcess`).
-   `controllers/admin/index.php`
    -   **Nombre de la pestaña y entidad gestionada**: "Índice" bajo el menú "Zalando FCI".
    -   **Responsabilidad**: Similar a su contraparte del front-office, este controlador de administración probablemente sirve como una página de inicio o una descripción general simple. Podría mostrar información general del módulo, enlaces rápidos a otras páginas de administración o un mensaje de estado. No suele estar involucrado en la gestión compleja de datos, sino más bien en la navegación y la visualización de información.

### 4.3 Clases y Modelos Principales (`classes/`)

El dossier del módulo indica que no hay clases o modelos personalizados en el directorio `classes/`. Esto sugiere que el módulo interactúa directamente con las clases `ObjectModel` principales de PrestaShop `Product` y `ProductSupplier` (o similares) y la clase `Configuration` para la configuración. La recuperación de datos probablemente se maneja directamente dentro de los controladores o el archivo principal del módulo utilizando `Db::getInstance()->executeS()` u objetos `DbQuery`.

### 4.4 Activos JavaScript (`views/js/`)

El dossier del módulo indica que no hay archivos JavaScript personalizados. Esto implica que la configuración y funcionalidad del módulo se basan principalmente en el lado del servidor, con interacciones dinámicas mínimas o nulas en el front-end del Back Office o Front Office que requieran JS personalizado.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `zalandofci/views/admin-theme.css`
    -   **Alcance**: Estilo del formulario de administración del back-office.
    -   **Principales componentes y contenedores de la interfaz de usuario que estiliza**: Esta hoja de estilo es responsable de la presentación visual de los formularios de configuración del módulo y, potencialmente, de cualquier cuadrícula o panel informativo personalizado dentro del Back Office de PrestaShop. Asegura que la interfaz del módulo se integre visualmente con el tema de administración de PrestaShop.
    -   **Selectores de clase CSS clave que los desarrolladores pueden anular**: Los desarrolladores pueden inspeccionar las páginas de administración del módulo para identificar clases específicas (por ejemplo, `.zalandofci-form`, `.zalandofci-panel`, `.zalandofci-alert`) y anularlas en su tema de administración personalizado o agregando CSS a través de un hook `displayBackOfficeHeader`.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   El dossier del módulo no enumera explícitamente plantillas dentro de un subdirectorio `hook/`, pero registra hooks como `displayHeader`, `displayRightColumn`, `displayProduct`, `displayFooter`. Si se pretendiera alguna salida visual para estos hooks, las plantillas residirían típicamente aquí. Dado el propósito del módulo (feed de datos de backend), es probable que estos hooks se utilicen para fines técnicos (por ejemplo, agregar JS/CSS, o no se utilicen en absoluto para la salida visual).
-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `zalandofci/views/how-it-works.tpl`
        -   **Propósito**: Esta plantilla probablemente proporciona contenido informativo dentro del Back Office, posiblemente en la página de configuración principal o en la pantalla "Índice", explicando cómo funciona el módulo o proporcionando instrucciones de configuración.
    -   `zalandofci/views/returnAlert.tpl`
        -   **Propósito**: Esta plantilla probablemente se utiliza para mostrar mensajes de éxito o error (alertas) dentro del Back Office después de una acción (por ejemplo, guardar la configuración, generar un feed).
    -   `zalandofci/views/script.tpl`
        -   **Propósito**: Esta plantilla podría contener código JavaScript en línea o usarse para incluir archivos JS externos condicionalmente dentro del Back Office. Podría usarse para el comportamiento dinámico del formulario o para activar acciones específicas.
-   **Plantillas del front-office (`views/templates/front/`)**:
    -   El dossier del módulo no enumera ninguna plantilla específica del front-office, lo que refuerza la idea de que el módulo no tiene una presencia visual directa en el lado de la tienda orientado al cliente.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

-   **Tablas de la Base de Datos**:

    -   El módulo no parece crear tablas SQL personalizadas durante la instalación (método `install()`).
    -   Todas las configuraciones específicas del módulo (por ejemplo, `zf_client`, `zf_api`, `zf_export_file_format`, `zf_remember_settings`, etc.) se almacenan en la tabla estándar `ps_configuration` de PrestaShop. Estas claves tienen el prefijo `zf_` o `PS_` (para las configuraciones principales de PrestaShop utilizadas por el módulo).
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza en la sección `<head>` de todas las páginas del front-office. | Potencialmente utilizado para incluir CSS o JS específicos del módulo, aunque no se lista JS/CSS personalizado para el front-office. También podría usarse para metaetiquetas u otros elementos no visuales. |
| `displayRightColumn` | Se renderiza en la columna derecha de las páginas que tienen una. | Poco probable que se use para salida visual dado el propósito del módulo. Podría ser un hook heredado o usarse para una inyección de datos muy específica y no visual. |
| `displayProduct` | Se renderiza en la página del producto. | Poco probable que se use para salida visual. Podría usarse para agregar atributos de datos ocultos a los elementos del producto para scripts externos, aunque no se lista JS personalizado. |
| `displayFooter` | Se renderiza en la sección del pie de página de todas las páginas del front-office. | Similar a `displayHeader`, podría usarse para incluir JS/CSS u otros elementos no visuales al final de la carga de la página. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración está configurando sus medios (JS/CSS). | Utilizado por `AdminExportProductsFci` para cargar `zalandofci/views/admin-theme.css` para sus formularios de configuración. |

## 5. Soporte Oficial y Actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y descargar las últimas versiones del módulo Importador de Zalando Fashion Connector (FCI), visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.

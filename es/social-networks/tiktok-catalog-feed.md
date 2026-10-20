---
title: "TikTok Catalog Feed - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo TikTok Catalog Feed para PrestaShop de MyPresta.eu."
sidebar:
  label: "TikTok Catalog Feed - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo TikTok Catalog Feed en MyPresta.eu](https://mypresta.eu/modules/social-networks/tiktok-catalog-feed.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/tiktok-catalog-feed/)
>
> ---


# TikTok Catalog Feed

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Asegúrese de que su servidor pueda manejar la generación de archivos XML/CSV potencialmente grandes si tiene un catálogo muy extenso.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

El módulo TikTok Catalog Feed proporciona una sección dedicada en su Back Office de PrestaShop para gestionar sus feeds de productos.

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta pantalla de configuración inicial le permite establecer los parámetros básicos para su feed de TikTok.

- **Activar Módulo:**

  - **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar la funcionalidad del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El módulo estará activo, permitiéndole generar y gestionar feeds de productos de TikTok.
    - *Cuando está desactivado:* El módulo dejará de funcionar y no se podrán generar ni acceder a feeds.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Lo activaría cuando esté listo para comenzar a usar TikTok Ads. Podría desactivarlo temporalmente si necesita realizar mantenimiento o detener sus campañas publicitarias de TikTok.
- **Tipo de Generación de Feed:**

  - **Qué hace este ajuste:** Determina si el módulo genera un archivo CSV (valores separados por comas) o XML (lenguaje de marcado extensible) para su feed de productos. TikTok generalmente admite ambos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en CSV:* La URL del feed generado proporcionará un archivo CSV.
    - *Cuando se establece en XML:* La URL del feed generado proporcionará un archivo XML.
  - **Valor recomendado:** XML (a menudo preferido por su naturaleza estructurada, pero CSV funciona igual de bien para TikTok).
  - **Escenario / ejemplo de comerciante:** Si la documentación de TikTok o su agencia de publicidad recomienda un formato específico, elija ese. De lo contrario, cualquiera de los dos funciona.
- **Idioma Predeterminado para el Feed:**

  - **Qué hace este ajuste:** Selecciona el idioma principal para los datos del producto en su feed. Esto es crucial para dirigirse a mercados específicos en TikTok.
  - **Efecto de cambiar este ajuste:** Los títulos de los productos, descripciones y otros campos dependientes del idioma en el feed se extraerán de su tienda PrestaShop en el idioma elegido.
  - **Valor recomendado:** El idioma de su audiencia objetivo principal en TikTok (por ejemplo, inglés para un mercado estadounidense, francés para un mercado francés).
  - **Escenario / ejemplo de comerciante:** Si se dirige a clientes en Alemania, seleccionaría "Alemán" aquí para asegurarse de que la información de su producto se muestre correctamente en su idioma en TikTok.
- **Moneda Predeterminada para el Feed:**

  - **Qué hace este ajuste:** Selecciona la moneda utilizada para todos los precios de los productos en su feed. Esto debe coincidir con la moneda de su mercado objetivo.
  - **Efecto de cambiar este ajuste:** Todos los precios en el feed se convertirán o se mostrarán en la moneda seleccionada.
  - **Valor recomendado:** La moneda de su audiencia objetivo principal en TikTok (por ejemplo, USD para un mercado estadounidense, EUR para un mercado europeo).
  - **Escenario / ejemplo de comerciante:** Si sus anuncios de TikTok se dirigen a clientes en el Reino Unido, seleccionaría "GBP" para asegurarse de que los precios se muestren en libras esterlinas.
- **País Predeterminado para el Envío:**

  - **Qué hace este ajuste:** Establece el país predeterminado utilizado para calcular los costos de envío y la disponibilidad en el feed. Esto es importante para que TikTok entienda dónde se pueden enviar sus productos.
  - **Efecto de cambiar este ajuste:** La información de envío en el feed se basará en las reglas de envío del país seleccionado configuradas en su tienda PrestaShop.
  - **Valor recomendado:** Su país de destino de envío principal.
  - **Escenario / ejemplo de comerciante:** Si la mayoría de sus ventas son dentro de Francia, seleccionaría "Francia" aquí.
- **Incluir Productos Agotados:**

  - **Qué hace este ajuste:** Determina si los productos actualmente marcados como "agotados" en su tienda PrestaShop deben incluirse en el feed de TikTok.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los productos agotados aparecerán en el feed, típicamente con un estado de "no disponible".
    - *Cuando está desactivado:* Los productos agotados se excluirán por completo del feed.
  - **Valor recomendado:** NO (a menos que tenga una estrategia específica para pedidos anticipados o notificaciones de reposición de stock).
  - **Escenario / ejemplo de comerciante:** Generalmente, desea mostrar solo productos disponibles en sus anuncios para evitar la frustración del cliente. Si tiene un largo tiempo de entrega para productos personalizados, podría incluirlos pero marcarlos como "pedido anticipado".
- **Excluir Categorías Específicas:**

  - **Qué hace este ajuste:** Le permite seleccionar categorías de productos específicas de su tienda PrestaShop que NO desea que aparezcan en el feed de TikTok.
  - **Efecto de cambiar este ajuste:** Los productos que pertenecen a las categorías seleccionadas se omitirán del feed generado.
  - **Valor recomendado:** Depende de su tienda.
  - **Escenario / ejemplo de comerciante:** Podría excluir categorías como "Tarjetas de Regalo" o "Servicios" si no son productos físicos adecuados para los Anuncios de Catálogo de TikTok. O, si tiene una categoría solo para B2B, la excluiría de los anuncios dirigidos al consumidor.
- **Excluir Productos Específicos:**

  - **Qué hace este ajuste:** Proporciona una forma de seleccionar manualmente productos individuales que deben excluirse del feed de TikTok, independientemente de su categoría.
  - **Efecto de cambiar este ajuste:** Los productos seleccionados no se incluirán en el feed.
  - **Valor recomendado:** Depende de su tienda.
  - **Escenario / ejemplo de comerciante:** Podría excluir un producto que forma parte de una venta flash por tiempo limitado que no desea anunciar en TikTok, o un producto que tiene restricciones legales para la publicidad en ciertas regiones.
- **Usar Descripción Corta del Producto:**

  - **Qué hace este ajuste:** Determina si se utiliza la descripción corta o la descripción completa de sus productos en el feed de TikTok.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Se utilizará la descripción del producto más corta y concisa.
    - *Cuando está desactivado:* Se utilizará la descripción completa y más larga del producto.
  - **Valor recomendado:** SÍ (las descripciones cortas suelen ser mejores para los anuncios, ya que los usuarios tienen una capacidad de atención limitada).
  - **Escenario / ejemplo de comerciante:** Los anuncios de TikTok se benefician de la información concisa. Usar la descripción corta asegura que el texto de su anuncio sea impactante y directo.
- **Exportar Características del Producto como Atributos:**

  - **Qué hace este ajuste:** Si está activado, las características de sus productos de PrestaShop (como "Material", "Color", "Tamaño") se exportarán como atributos adicionales en el feed de TikTok, proporcionando información más detallada del producto.
  - **Efecto de cambiar este ajuste:** Habrá información más detallada del producto disponible para TikTok para una mejor segmentación y visualización de anuncios.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Si vende ropa, exportar "Color" y "Tamaño" como atributos permite a TikTok mostrar anuncios más específicos (por ejemplo, "Vestido Rojo, Talla M").
- **Exportar Combinaciones de Productos (Variantes):**

  - **Qué hace este ajuste:** Crucial para tiendas con productos que tienen variaciones (por ejemplo, una camiseta disponible en diferentes tallas y colores). Este ajuste asegura que cada combinación única se exporte como un elemento separado en el feed.
  - **Efecto de cambiar este ajuste:** Cada variante de producto tendrá su propia entrada en el feed, con su precio, stock e imagen específicos, lo que permite a TikTok mostrar la variante exacta anunciada.
  - **Valor recomendado:** SÍ (casi siempre, a menos que solo venda productos simples sin variaciones).
  - **Escenario / ejemplo de comerciante:** Si vende un zapato disponible en tallas 7, 8 y 9, habilitar esto asegura que TikTok vea tres productos distintos, cada uno con su propio SKU y disponibilidad.
- **Exportar Atributo de Talla:**

  - **Qué hace este ajuste:** Específicamente para productos con combinaciones, este ajuste asegura que el atributo "talla" de cada combinación se incluya explícitamente en el feed, lo cual es importante para la ropa y el calzado.
  - **Efecto de cambiar este ajuste:** La talla de cada variante de producto se listará claramente en el feed.
  - **Valor recomendado:** SÍ (especialmente para moda, calzado o cualquier producto dependiente de la talla).
  - **Escenario / ejemplo de comerciante:** Para una tienda de ropa, esto asegura que una "Camiseta Azul Grande" sea correctamente identificada por TikTok, no solo una "Camiseta Azul".
- **Exportar Fecha de Disponibilidad:**

  - **Qué hace este ajuste:** Incluye la fecha de "disponible para pedido" para los productos, lo cual es útil para artículos de pedido anticipado o productos con fechas de lanzamiento futuras.
  - **Efecto de cambiar este ajuste:** TikTok recibirá información sobre cuándo estará disponible un producto.
  - **Valor recomendado:** SÍ (si utiliza esta función en PrestaShop).
  - **Escenario / ejemplo de comerciante:** Si va a lanzar un nuevo producto el próximo mes, esto permite a TikTok mostrar anuncios de "pedido anticipado" con la fecha de disponibilidad correcta.
- **Mapeo de Categorías de Productos de Google:**

  - **Qué hace este ajuste:** TikTok a menudo aprovecha la extensa taxonomía de productos de Google. Esta sección le permite mapear sus categorías de PrestaShop a las Categorías de Productos de Google más relevantes. Esto mejora la relevancia y la segmentación de los anuncios.
  - **Efecto de cambiar este ajuste:** Sus productos se categorizarán correctamente según la taxonomía de Google en el feed, que TikTok utiliza para una mejor comprensión y segmentación.
  - **Valor recomendado:** Mapee tantas categorías como sea posible.
  - **Escenario / ejemplo de comerciante:** Si tiene una categoría de PrestaShop "Vestidos de Verano", la mapearía a una Categoría de Productos de Google como "Ropa y Accesorios > Ropa > Vestidos".
- **Generar URL del Feed:**

  - **Qué hace este ajuste:** Después de configurar todos los ajustes, este botón genera la URL única para su feed de productos de TikTok. Esta URL es la que proporcionará al Administrador de Anuncios de TikTok.
  - **Efecto de cambiar este ajuste:** Al hacer clic, se mostrará la URL. El feed en esta URL reflejará todos los ajustes elegidos.
  - **Valor recomendado:** Haga clic después de que todos los demás ajustes estén finalizados.
  - **Escenario / ejemplo de comerciante:** Una vez que haya configurado todo, haga clic, copie la URL y péguela en su Administrador de Anuncios de TikTok al configurar su Catálogo.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

El módulo proporciona una sección dedicada en su Back Office de PrestaShop para gestionar y generar sus feeds de productos de TikTok.

**Nombre de la Pantalla y Ubicación del Menú:**
Puede acceder a esta sección a través del menú principal de PrestaShop: **Catálogo > Feed de TikTok**.

Esta sección típicamente presenta un panel de control o una lista de feeds generados, lo que le permite gestionar diferentes configuraciones de feed si el módulo admite múltiples feeds (por ejemplo, para diferentes idiomas o monedas).

#### 2.2.1 Panel de Control del Feed de TikTok (Back Office > Catálogo > Feed de TikTok)

Este es el punto de entrada principal para gestionar sus feeds de TikTok.

- **Acciones y Ajustes Disponibles:**

  - **Lista de Feeds:** Verá una tabla o lista de todos sus feeds de TikTok configurados. Cada entrada típicamente mostrará:
    - **Nombre del Feed:** Un nombre descriptivo para su feed (por ejemplo, "Feed en Inglés de EE. UU.", "Feed en Francés de la UE").
    - **Idioma:** El idioma de los productos en este feed.
    - **Moneda:** La moneda de los precios en este feed.
    - **Última Generación:** La marca de tiempo de la última actualización del feed.
    - **URL del Feed:** El enlace directo al archivo de feed generado (CSV o XML).
    - **Acciones:** Botones para "Editar", "Generar Ahora" o "Eliminar" el feed.
  - **Botón "Añadir Nuevo Feed":** Le permite crear una nueva configuración de feed, potencialmente para un idioma, moneda o conjunto de exclusiones de productos diferente.
  - **Botón "Generar Todos los Feeds":** Una opción conveniente para actualizar todos sus feeds configurados a la vez.
- **Efecto de los cambios:**

  - **Añadir un Nuevo Feed:** Crea una nueva instancia de configuración, lo que le permite definir un conjunto separado de reglas (idioma, moneda, exclusiones) para un feed de TikTok distinto. Esto es útil para tiendas multi-país o multi-idioma.
  - **Editar un Feed:** Le lleva a un formulario de configuración (similar a la configuración principal del módulo, pero específico para esta instancia de feed) donde puede ajustar sus ajustes.
  - **Generar un Feed:** Activa el módulo para procesar su catálogo de productos basándose en los ajustes del feed y crear/actualizar el archivo del feed en su URL única. Esto es crucial para asegurar que TikTok siempre tenga la información más actualizada del producto.
  - **Eliminar un Feed:** Elimina la configuración del feed y su archivo generado asociado.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

  1. **Configuración Inicial:** Cree al menos un feed para su mercado objetivo principal (por ejemplo, inglés, USD).
  2. **Configuración Multi-Mercado:** Si se dirige a varios países o idiomas, cree un feed separado para cada uno, configurando los ajustes de idioma, moneda y país de manera apropiada.
  3. **Generación Regular:** TikTok típicamente extrae feeds en un horario (por ejemplo, diariamente). Puede hacer clic manualmente en "Generar Ahora" si ha realizado cambios significativos en los productos (nuevos productos, actualizaciones de precios, cambios de stock) y desea que TikTok los refleje inmediatamente. De lo contrario, el módulo a menudo tiene un mecanismo de generación automática o configuración de tarea cron (consulte la sección de Desarrolladores).
  4. **Monitorear la Salud del Feed:** Revise regularmente su Administrador de Anuncios de TikTok en busca de errores o advertencias del feed. Si surgen problemas, revise los ajustes de su módulo y regenere el feed.

#### 2.2.2 Formulario de Configuración del Feed (Accedido a través de "Añadir Nuevo Feed" o "Editar" un feed)

Esta pantalla es donde define los parámetros específicos para un feed de productos de TikTok individual. Refleja muchos de los ajustes que se encuentran en la página de configuración principal del módulo, pero los aplica a una única instancia de feed.

- **Campos y Columnas del Formulario:**

  - **Nombre del Feed:** Un nombre único y descriptivo para este feed específico (por ejemplo, "Catálogo en Inglés de EE. UU.", "Catálogo en Alemán de DE").
  - **Idioma:** Seleccione el idioma para este feed.
  - **Moneda:** Seleccione la moneda para este feed.
  - **País:** Seleccione el país predeterminado para el envío para este feed.
  - **Incluir Productos Agotados:** (Igual que arriba, pero específico para este feed).
  - **Excluir Categorías Específicas:** (Igual que arriba, pero específico para este feed).
  - **Excluir Productos Específicos:** (Igual que arriba, pero específico para este feed).
  - **Usar Descripción Corta del Producto:** (Igual que arriba, pero específico para este feed).
  - **Exportar Características del Producto como Atributos:** (Igual que arriba, pero específico para este feed).
  - **Exportar Combinaciones de Productos (Variantes):** (Igual que arriba, pero específico para este feed).
  - **Exportar Atributo de Talla:** (Igual que arriba, pero específico para este feed).
  - **Exportar Fecha de Disponibilidad:** (Igual que arriba, pero específico para este feed).
  - **Mapeo de Categorías de Productos de Google:** (Igual que arriba, pero específico para este feed).
- **Efecto de los cambios:** Guardar los cambios en este formulario actualiza la configuración para el feed específico que está editando. Luego deberá "Generar Ahora" para ese feed para aplicar los cambios al archivo de feed real.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de Configuración del Módulo** | Activar Módulo | SÍ | Activa/desactiva la funcionalidad del módulo. |
|  | Tipo de Generación de Feed | XML | Elija el formato CSV o XML para el feed. |
|  | Idioma Predeterminado para el Feed | Idioma Principal de la Tienda | Establece el idioma para los datos del producto. |
|  | Moneda Predeterminada para el Feed | Moneda Principal de la Tienda | Establece la moneda para los precios de los productos. |
|  | País Predeterminado para el Envío | País de Envío Principal | Establece el país predeterminado para la información de envío. |
|  | Incluir Productos Agotados | NO | Excluye los artículos agotados del feed. |
|  | Excluir Categorías Específicas | (Ninguno) | Omite productos de categorías seleccionadas. |
|  | Excluir Productos Específicos | (Ninguno) | Omite productos específicos del feed. |
|  | Usar Descripción Corta del Producto | SÍ | Utiliza descripciones cortas para mayor concisión. |
|  | Exportar Características del Producto como Atributos | SÍ | Incluye las características del producto como atributos. |
|  | Exportar Combinaciones de Productos (Variantes) | SÍ | Exporta cada variante de producto como un elemento separado. |
|  | Exportar Atributo de Talla | SÍ | Incluye el atributo de talla para las variantes. |
|  | Exportar Fecha de Disponibilidad | SÍ | Incluye la fecha de disponibilidad del producto. |
|  | Mapeo de Categorías de Productos de Google | Mapear todos los relevantes | Mapea las categorías de PrestaShop a la taxonomía de Google para TikTok. |
|  | Generar URL del Feed | Clic después de la configuración | Crea/actualiza la URL única para el feed. |
| **Panel de Control del Feed de TikTok** | Añadir Nuevo Feed | N/A | Crea una nueva configuración de feed separada. |
|  | Editar Feed | N/A | Modifica los ajustes de un feed existente. |
|  | Generar Ahora (para un feed específico) | N/A | Actualiza manualmente un único archivo de feed. |
|  | Generar Todos los Feeds | N/A | Actualiza manualmente todos los archivos de feed configurados. |
|  | Eliminar Feed | N/A | Elimina una configuración de feed y su archivo. |
| **Formulario de Configuración del Feed** | Nombre del Feed | Nombre Descriptivo | Identifica el feed específico. |
|  | (Todos los demás ajustes) | (Como arriba) | Configura los parámetros para esta instancia de feed individual. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mis anuncios de TikTok muestran precios desactualizados o productos agotados. ¿Qué debo hacer?**
**R1:** Esto generalmente significa que su feed de TikTok no se está actualizando con la suficiente frecuencia.
1. Vaya a **Catálogo > Feed de TikTok** en su Back Office de PrestaShop.
2. Busque el feed relevante y haga clic en el botón "Generar Ahora".
3. Asegúrese de tener una tarea cron configurada para actualizar automáticamente sus feeds diariamente (recomendado). Consulte con su webmaster o proveedor de alojamiento para confirmar que la tarea cron se está ejecutando correctamente.
4. Verifique su configuración de "Incluir Productos Agotados" en la configuración del feed. Si está habilitada y no desea artículos agotados, desactívela.

**P2: Algunos de mis productos faltan en el feed de TikTok.**
**R2:** Verifique los siguientes ajustes para el feed específico:
1. **"Excluir Categorías Específicas":** Asegúrese de que las categorías de los productos que faltan no estén seleccionadas aquí.
2. **"Excluir Productos Específicos":** Asegúrese de que los productos individuales no estén excluidos manualmente.
3. **"Incluir Productos Agotados":** Si los productos están agotados y este ajuste está deshabilitado, no aparecerán.
4. **Visibilidad del Producto:** Asegúrese de que los productos estén activos y visibles en su tienda PrestaShop.

**P3: Las descripciones de mis productos parecen demasiado largas o demasiado cortas en el feed de TikTok.**
**R3:** Vaya a la configuración del feed y ajuste el ajuste "Usar Descripción Corta del Producto":
- Si las descripciones son demasiado largas, habilite este ajuste para usar la descripción más corta.
- Si las descripciones son demasiado cortas y desea más detalles, deshabilite este ajuste para usar la descripción completa.

**P4: ¿Cómo mapeo mis categorías a las Categorías de Productos de Google de manera efectiva?**
**R4:**
1. Acceda a la sección "Mapeo de Categorías de Productos de Google" dentro de la configuración de su feed.
2. Para cada una de sus categorías de PrestaShop, busque la Categoría de Productos de Google más relevante. Sea lo más específico posible.
3. Si no puede encontrar una coincidencia exacta, elija la categoría más amplia y cercana.
4. Este mapeo ayuda a TikTok a comprender mejor sus productos para la segmentación.

**P5: He realizado cambios, pero la URL del feed sigue mostrando datos antiguos. ¿Qué está mal?**
**R5:** Después de realizar cualquier cambio en la configuración del módulo o en la configuración de un feed específico, **debe** regenerar el feed. Vaya a **Catálogo > Feed de TikTok**, busque el feed que modificó y haga clic en "Generar Ahora". Si cambió la configuración global, es posible que deba regenerar todos los feeds.

**P6: Mi tema personalizado está causando problemas de visualización en el Back Office para el módulo.**
**R6:** Si bien los componentes del front-office del módulo son invisibles, su interfaz del Back Office podría entrar en conflicto con temas de administración muy personalizados.
1. **Borrar Caché de Smarty:** Vaya a **Parámetros Avanzados > Rendimiento** en su Back Office de PrestaShop. Haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Esto a menudo resuelve pequeños problemas de visualización.
2. **Buscar Errores de JavaScript:** Abra la consola del desarrollador de su navegador (F12) en el Back Office. Busque cualquier error de JavaScript. Si encuentra errores, póngase en contacto con el soporte de MyPresta.eu con los detalles del error.
3. **Cambio Temporal de Tema:** Si es posible, cambie temporalmente su tema del Back Office al tema predeterminado de PrestaShop para ver si el problema persiste. Si se resuelve, el conflicto es con su tema de administración personalizado.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo TikTok Catalog Feed, destinada a desarrolladores y webmasters.

### 4.1 Resumen de la Arquitectura

El módulo TikTok Catalog Feed sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, centrado principalmente en la administración del Back Office y la entrega de datos del front-office. Aprovecha la clase `Module` de PrestaShop para la instalación/desinstalación y configuración, y `AdminController` para gestionar la configuración del feed. La lógica central gira en torno a la generación dinámica de datos de productos en un formato estructurado CSV o XML, accesible a través de un `ModuleFrontController` dedicado. No introduce clases `ObjectModel` personalizadas, sino que consulta directamente los datos de productos y categorías principales de PrestaShop.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

Estos controladores son responsables de servir el feed de productos real a TikTok.

- `controllers/front/feed.php`
  - **Nombre de la clase y clase padre:** `TiktokfeedFeedModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este es el punto final principal para que TikTok extraiga el catálogo de productos. Genera dinámicamente el feed de productos (CSV o XML) basándose en los parámetros de configuración (idioma, moneda, exclusiones) asociados con un ID de feed específico. Maneja la recuperación de datos, el formato y la salida como una descarga de archivo o una transmisión directa. Está diseñado para ser sin estado, procesando la solicitud y devolviendo el feed.
- `controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `TiktokfeedIndexModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador es típicamente un marcador de posición o un respaldo. En muchos módulos, `index.php` en el directorio del controlador frontal podría manejar el enrutamiento predeterminado o simplemente redirigir. Para este módulo, `feed.php` es el controlador frontal crítico. Este `index.php` podría no tener una lógica específica o podría usarse para una página frontal general del módulo si se implementara (lo cual no es el caso para un módulo de feed).

#### Controladores de Administración del Back-Office

Estos controladores gestionan la configuración del módulo y los ajustes de generación del feed dentro del Back Office de PrestaShop.

- `controllers/admin/AdminExportProductsFeedTiktok.php`
  - **Nombre de la clase y clase padre:** `AdminExportProductsFeedTiktokController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Este controlador es responsable de la sección principal "Feed de TikTok" en **Catálogo > Feed de TikTok**. Gestiona la creación, edición y eliminación de configuraciones de feed individuales. Muestra una lista de feeds configurados y proporciona formularios para sus ajustes detallados.
  - **Funcionalidades clave:**
    - `renderList()`: Muestra la tabla de feeds existentes.
    - `renderForm()`: Renderiza el formulario para añadir/editar un feed, incluyendo campos para idioma, moneda, exclusiones de categoría/producto, mapeo de categorías de Google, etc.
    - Maneja el guardado y la actualización de las configuraciones del feed (`postProcess()`).
    - Activa el proceso de generación del feed para feeds específicos.
- `controllers/admin/index.php`
  - **Nombre de la clase y clase padre:** `AdminTiktokfeedIndexController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Este controlador probablemente sirve como el punto de entrada principal para la sección de administración del módulo, potencialmente redirigiendo a `AdminExportProductsFeedTiktokController` o proporcionando un panel de control de alto nivel. Dada la estructura del módulo, `AdminExportProductsFeedTiktokController` es donde reside la lógica principal de gestión del feed. Este `index.php` podría ser para una visión general del módulo o una simple redirección.

### 4.3 Clases Principales y Modelos (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo se basa principalmente en las clases `ObjectModel` principales de PrestaShop `Product`, `Category`, `Language`, `Currency`, `Carrier` y `Configuration` para el almacenamiento y la recuperación de datos. La lógica de generación del feed probablemente está encapsulada dentro del archivo principal del módulo (`tiktokfeed/index.php`) y el `AdminExportProductsFeedTiktokController`.

### 4.4 Activos de JavaScript (`views/js/`)

- `tiktokfeed/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office.
  - **Propósito:** Proporciona funcionalidad de autocompletado, probablemente utilizada para seleccionar productos o categorías a excluir, o para el mapeo de categorías de Google. Vincula detectores de eventos a campos de entrada, realiza solicitudes AJAX para sugerencias de búsqueda y actualiza el DOM con los resultados.
- `tiktokfeed/views/js/admin-app.js`
  - **Alcance:** Back-office.
  - **Propósito:** Este es el archivo JavaScript principal para la interfaz del Back Office del módulo. Maneja varios elementos interactivos en los formularios de configuración del feed y el panel de control. Esto podría incluir:
    - Validación de formularios.
    - Actualizaciones dinámicas basadas en las opciones seleccionadas (por ejemplo, mostrar/ocultar campos).
    - Llamadas AJAX para guardar configuraciones o activar la generación del feed.
    - Interacciones con modales fancybox (por ejemplo, para la selección de categorías/productos).

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `tiktokfeed/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Estilo de administración del Back-office.
  - **Propósito:** Estiliza los desplegables de autocompletado y los campos de entrada utilizados por el script `autocomplete.js`, asegurando una experiencia de búsqueda consistente y fácil de usar dentro de los formularios de administración.
- `tiktokfeed/views/admin-theme.css`
  - **Alcance:** Estilo de administración del Back-office.
  - **Propósito:** Proporciona ajustes de estilo generales para la interfaz del Back Office del módulo para integrarse sin problemas con el tema de administración de PrestaShop. Esto podría incluir ajustes de diseño, estilo de botones o formato de tablas.
- `tiktokfeed/views/css/admin-app.css`
  - **Alcance:** Estilo de administración del Back-office.
  - **Propósito:** Contiene estilos específicos para los componentes personalizados del módulo, formularios y elementos del panel de control dentro del Back Office de PrestaShop. Esto podría incluir estilos para la tabla de listado de feeds, paneles de configuración y modales fancybox.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de gancho (`views/templates/hook/`)

El dossier del módulo no lista explícitamente plantillas en un subdirectorio `hook/`, lo que implica que el módulo no renderiza contenido directamente en los ganchos del front-office. Su función principal es la generación de datos, no la visualización en el front-end.

#### Plantillas de administración (`views/templates/admin/`)

Estas plantillas se utilizan para renderizar la interfaz del Back Office del módulo.

- `tiktokfeed/views/templates/admin/dashboard.tpl`
  - **Propósito:** Probablemente la plantilla principal del panel de control para la sección del Feed de TikTok, que potencialmente muestra una visión general de los feeds, el estado y las acciones rápidas.
- `tiktokfeed/views/templates/admin/feeds.tpl`
  - **Propósito:** Renderiza la lista de feeds de TikTok configurados, típicamente una tabla con columnas para el nombre del feed, idioma, moneda, URL y botones de acción (editar, generar, eliminar). Esto probablemente es renderizado por `AdminExportProductsFeedTiktokController::renderList()`.
- `tiktokfeed/views/templates/admin/form-chrome.tpl`
  - **Propósito:** Una plantilla envoltorio o parcial utilizada para proporcionar un estilo y una estructura consistentes para los formularios de configuración del módulo, que potencialmente incluye encabezado, pie de página y elementos de diseño general para el formulario.
- `tiktokfeed/views/templates/admin/layout.tpl`
  - **Propósito:** Una plantilla de diseño base para las páginas de administración del módulo, que define la estructura general, incluyendo encabezado, navegación y áreas de contenido.

#### Otras plantillas relacionadas con la administración

Estas plantillas probablemente se utilizan como parciales o para componentes específicos de la interfaz de usuario dentro de los formularios de administración.

- `tiktokfeed/lib/searchTool/views/scripts.tpl`
  - **Propósito:** Incluye JavaScript para la herramienta de búsqueda, probablemente el script `autocomplete.js` y su inicialización.
- `tiktokfeed/views/categories-fancybox.tpl`
  - **Propósito:** Renderiza el contenido para un modal Fancybox utilizado para seleccionar categorías para exclusión o mapeo.
- `tiktokfeed/views/exclude-products.tpl`
  - **Propósito:** Renderiza la interfaz de usuario para seleccionar y gestionar productos que se excluirán del feed, posiblemente dentro de un Fancybox o una sección dedicada del formulario.
- `tiktokfeed/views/google_lang_links.tpl`
  - **Propósito:** Renderiza enlaces o elementos de la interfaz de usuario relacionados con el mapeo de categorías de productos de Google, potencialmente para diferentes idiomas.
- `tiktokfeed/views/returnAlert.tpl`
  - **Propósito:** Una plantilla genérica para mostrar mensajes/alertas de éxito o error en el Back Office.
- `tiktokfeed/views/script-fancybox.tpl`
  - **Propósito:** Incluye JavaScript para la integración de Fancybox, probablemente para abrir modales para la selección de categorías/productos.
- `tiktokfeed/views/script.tpl`
  - **Propósito:** Una plantilla de script general, posiblemente para la inicialización de JavaScript en todo el módulo o pequeños scripts en línea.

### 4.7 Esquema de la Base de Datos y Mapa de Ganchos

- **Tablas de la Base de Datos**:

  - El módulo no parece crear tablas SQL personalizadas según el dossier.
  - Almacena sus configuraciones (por ejemplo, tipo de feed, idioma/moneda predeterminados, listas de exclusión, mapeos de categorías de Google) en la tabla `ps_configuration` de PrestaShop. Las claves de configuración típicamente seguirían un patrón como `TTF_FEED_TYPE`, `TTF_DEFAULT_LANG`, `TTF_EXCLUDE_CATEGORIES`, etc.
  - Las configuraciones de feed individuales (si se admiten múltiples feeds) podrían almacenarse como arrays serializados en `ps_configuration` o potencialmente en una tabla personalizada si el módulo introdujera una (lo cual no está indicado).
- **Tabla de Ganchos Registrados**:
  La función principal del módulo es la generación de datos, no la visualización en el front-office, por lo que no registra ganchos para mostrar contenido en la tienda (por ejemplo, `displayHeader`, `displayRightColumn`).
  Sin embargo, registrará los siguientes ganchos para su funcionalidad principal:

  | Nombre del Gancho | Momento de Ejecución | Propósito Técnico |
  | --- | --- | --- |
  | `actionModuleInstall` | Durante la instalación del módulo | Crea entradas de configuración, registra pestañas de administración. |
  | `actionModuleUninstall` | Durante la desinstalación del módulo | Limpia entradas de configuración, anula el registro de pestañas de administración. |
  | `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración | Encola JS y CSS específicos del módulo para el Back Office. |
  | `displayBackOfficeHeader` | Renderiza contenido en el encabezado del Back Office | Potencialmente para JS/CSS de administración global o notificaciones. |
  | `actionSchedulerCron` (o similar) | Cuando se ejecuta la tarea cron de PrestaShop | Activa la generación automática del feed si está configurado. |

### Configuración de Tareas Cron para la Generación Automatizada del Feed

Para las actualizaciones automatizadas del feed, deberá configurar una tarea cron en su servidor para llamar a una URL o script específico proporcionado por el módulo. Esta URL típicamente apunta a un controlador frontal que activa la generación del feed.

**Ejemplo de Comando de Tarea Cron (Consulte a su proveedor de alojamiento para la sintaxis exacta):**

Terminal window

```
0 3 \* \* \* wget -q -O /dev/null "https://yourstore.com/module/tiktokfeed/feed?action=generate\_all&token=YOUR\_SECURE\_TOKEN" >/dev/null 2>&1
```

- `0 3 * * *`: Esto programa la tarea para que se ejecute diariamente a las 3:00 AM.
- `wget -q -O /dev/null`: Obtiene la URL silenciosamente y descarta la salida.
- `https://yourstore.com/module/tiktokfeed/feed?action=generate_all&token=YOUR_SECURE_TOKEN`: Esta es la URL que activa la generación del feed. El parámetro `token` es crucial para la seguridad para evitar accesos no autorizados. El módulo debe proporcionar este token en su configuración o documentación.
- `>/dev/null 2>&1`: Redirige toda la salida a null, evitando notificaciones por correo electrónico innecesarias.

**Importante:** La URL y el token exactos serán proporcionados por el módulo después de la configuración. Utilice siempre el token seguro para proteger su punto final de generación de feed.

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial para desarrolladores, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Asegúrese de estar ejecutando la última versión compatible del módulo para su tienda PrestaShop.

---
title: "LLMS.txt Generator Pro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo LLMS.txt Generator Pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "LLMS.txt Generator Pro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo LLMS.txt Generator Pro en MyPresta.eu](https://mypresta.eu/modules/seo/llmstxt-generator-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/seo/llmstxt-generator-pro/)
>
> ---


# LLMS.txt Generator Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL). Su servidor también debe permitir la escritura de archivos en el directorio raíz para que se genere el archivo `llms.txt`.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > LLMS.txt Generator Pro)

Este es el panel de control principal de su módulo LLMS.txt Generator Pro. Aquí, definirá cómo se genera su archivo `llms.txt` y qué contenido incluye.

#### Ajustes Generales

- **Habilitar la Generación de LLMS.txt:**

  - **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar la funcionalidad central del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El módulo generará y servirá el archivo `llms.txt` según sus ajustes. Los rastreadores de IA podrán acceder a él.
    - *Cuando está deshabilitado:* El archivo `llms.txt` no será generado ni servido por el módulo. Los rastreadores de IA no recibirán una guía específica de su tienda.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Acaba de instalar el módulo y quiere empezar a guiar a los bots de IA. Habilite esto. Si necesita detener temporalmente la guía de IA para mantenimiento, puede deshabilitarlo aquí.
- **Tipo de Archivo LLMS.txt:**

  - **Qué hace este ajuste:** Determina si el archivo `llms.txt` se genera como un archivo estático (escrito en su servidor) o se sirve dinámicamente bajo demanda.
  - **Efecto de cambiar este ajuste:**
    - *Estático:* El módulo escribe un archivo `llms.txt` físico en el directorio raíz de su tienda. Esto es generalmente más rápido para los bots de IA, ya que no requiere procesamiento PHP en cada solicitud.
    - *Dinámico:* El archivo `llms.txt` es generado por el código PHP de PrestaShop cada vez que un bot de IA lo solicita. Esto asegura el contenido más actualizado, pero puede ser ligeramente más lento.
  - **Valor recomendado:** Estático (para rendimiento, a menos que tenga cambios de contenido frecuentes y en tiempo real que deban reflejarse instantáneamente).
  - **Escenario / ejemplo de comerciante:** Para la mayoría de las tiendas, estático está bien. Si tiene una tienda con mucho tráfico y precios de productos o existencias que cambian constantemente, dinámico podría ser preferible, pero considere el impacto en el rendimiento.
- **Generar llms-full.txt:**

  - **Qué hace este ajuste:** Controla si también se genera un archivo `llms-full.txt` adicional y más completo. Este archivo suele incluir información más detallada o menos restringida que el `llms.txt` estándar.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Se creará un archivo `llms-full.txt` junto con `llms.txt`, ofreciendo a los rastreadores de IA un conjunto de datos más rico.
    - *Cuando está deshabilitado:* Solo se generará el archivo `llms.txt` estándar.
  - **Valor recomendado:** SÍ (para proporcionar la máxima cantidad de datos a la IA, a menos que tenga razones específicas para restringirlos).
  - **Escenario / ejemplo de comerciante:** Quiere que los modelos de IA tengan acceso a la mayor cantidad de información relevante posible sobre sus productos, incluyendo detalles potencialmente menos críticos pero aún útiles.
- **Incluir Páginas de Producto:**

  - **Qué hace este ajuste:** Determina si las páginas de productos individuales se listan en el archivo `llms.txt`.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Se incluirán las URLs de todas sus páginas de productos activas, haciéndolas descubribles por la IA.
    - *Cuando está deshabilitado:* Las páginas de productos serán excluidas, lo que significa que los bots de IA no serán guiados explícitamente a ellas a través de `llms.txt`.
  - **Valor recomendado:** SÍ (Los productos suelen ser el núcleo de una tienda de comercio electrónico).
  - **Escenario / ejemplo de comerciante:** Quiere que la IA ayude a los clientes a encontrar productos específicos.
- **Incluir Páginas de Categoría:**

  - **Qué hace este ajuste:** Determina si las páginas de categoría (que listan grupos de productos) se listan en el archivo `llms.txt`.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Se incluirán las URLs de todas sus páginas de categoría activas.
    - *Cuando está deshabilitado:* Las páginas de categoría serán excluidas.
  - **Valor recomendado:** SÍ (Las categorías ayudan a la IA a comprender la estructura de su tienda).
  - **Escenario / ejemplo de comerciante:** Quiere que la IA entienda los diferentes tipos de productos que vende y guíe a los clientes a las secciones relevantes.
- **Incluir Páginas CMS:**

  - **Qué hace este ajuste:** Determina si sus páginas del sistema de gestión de contenido (CMS) (por ejemplo, Quiénes Somos, Contacto, Información de Envío, Política de Privacidad) se listan.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Se incluirán las URLs de las páginas CMS activas.
    - *Cuando está deshabilitado:* Las páginas CMS serán excluidas.
  - **Valor recomendado:** SÍ (Importante para que la IA entienda su negocio y políticas).
  - **Escenario / ejemplo de comerciante:** Quiere que la IA pueda responder preguntas sobre las políticas o la historia de su tienda.
- **Incluir Páginas de Fabricantes/Marcas:**

  - **Qué hace este ajuste:** Determina si se listan las páginas dedicadas a fabricantes o marcas específicas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Se incluirán las URLs de las páginas de fabricantes/marcas activas.
    - *Cuando está deshabilitado:* Las páginas de fabricantes/marcas serán excluidas.
  - **Valor recomendado:** SÍ (Si las marcas son importantes para su oferta de productos).
  - **Escenario / ejemplo de comerciante:** Vende productos de marcas conocidas y quiere que la IA lo reconozca.
- **Incluir Páginas de Proveedores:**

  - **Qué hace este ajuste:** Determina si se listan las páginas dedicadas a proveedores específicos. (Menos común para la visibilidad en el front-office, a menudo utilizado para fines internos).
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Se incluirán las URLs de las páginas de proveedores activas.
    - *Cuando está deshabilitado:* Las páginas de proveedores serán excluidas.
  - **Valor recomendado:** NO (A menos que promocione específicamente a los proveedores en su front-office).
  - **Escenario / ejemplo de comerciante:** Tiene un modelo de negocio único en el que los proveedores están a la vista del público y quiere que la IA los indexe.
- **Incluir Página de Nuevos Productos:**

  - **Qué hace este ajuste:** Determina si se incluye la página de listado de "Nuevos Productos".
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Se incluirá la URL de la página de nuevos productos.
    - *Cuando está deshabilitado:* La página de nuevos productos será excluida.
  - **Valor recomendado:** SÍ (Para destacar sus últimas ofertas a la IA).
  - **Escenario / ejemplo de comerciante:** Añade nuevos productos con frecuencia y quiere que la IA los conozca rápidamente.
- **Incluir Página de Mejores Ventas:**

  - **Qué hace este ajuste:** Determina si se incluye la página de listado de "Mejores Ventas" o "Más Vendidos".
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Se incluirá la URL de la página de mejores ventas.
    - *Cuando está deshabilitado:* La página de mejores ventas será excluida.
  - **Valor recomendado:** SÍ (Para promocionar sus artículos más populares).
  - **Escenario / ejemplo de comerciante:** Quiere que la IA recomiende sus artículos más vendidos a los clientes.
- **Incluir Página de Bajada de Precios:**

  - **Qué hace este ajuste:** Determina si se incluye la página de listado de "Bajada de Precios" o "En Oferta".
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Se incluirá la URL de la página de bajada de precios.
    - *Cuando está deshabilitado:* La página de bajada de precios será excluida.
  - **Valor recomendado:** SÍ (Para destacar sus artículos con descuento).
  - **Escenario / ejemplo de comerciante:** Realiza promociones y quiere que la IA informe a los clientes sobre las ofertas actuales.
- **Incluir Página de Contacto:**

  - **Qué hace este ajuste:** Determina si se incluye la página de contacto de su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Se incluirá la URL de la página de contacto.
    - *Cuando está deshabilitado:* La página de contacto será excluida.
  - **Valor recomendado:** SÍ (Esencial para que la IA proporcione información de servicio al cliente).
  - **Escenario / ejemplo de comerciante:** Quiere que la IA pueda decir a los clientes cómo ponerse en contacto con su equipo de soporte.
- **Incluir Página de Mapa del Sitio:**

  - **Qué hace este ajuste:** Determina si se incluye la página principal del mapa del sitio de su tienda (si tiene una).
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Se incluirá la URL de la página del mapa del sitio.
    - *Cuando está deshabilitado:* La página del mapa del sitio será excluida.
  - **Valor recomendado:** SÍ (Puede ayudar a la IA a descubrir más contenido, similar a los mapas del sitio de los motores de búsqueda).
  - **Escenario / ejemplo de comerciante:** Quiere proporcionar a la IA una visión general completa de la estructura de su tienda.
- **Incluir URLs Personalizadas:**

  - **Qué hace este ajuste:** Le permite añadir manualmente URLs específicas que no son generadas automáticamente por PrestaShop pero que aún desea que la IA descubra.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un área de texto donde puede listar una URL por línea. Estas URLs se añadirán a su archivo `llms.txt`.
    - *Cuando está deshabilitado:* No se añadirán URLs personalizadas.
  - **Valor recomendado:** SÍ (Si tiene páginas estáticas importantes o publicaciones de blog fuera de la estructura central de PrestaShop).
  - **Escenario / ejemplo de comerciante:** Tiene un blog separado en un subdominio o páginas de destino específicas que desea que la IA indexe.
- **Excluir URLs Específicas:**

  - **Qué hace este ajuste:** Le permite especificar manualmente URLs que *no* deben incluirse en el archivo `llms.txt`, incluso si de otro modo se generarían.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un área de texto donde puede listar una URL por línea. Estas URLs serán excluidas explícitamente.
    - *Cuando está deshabilitado:* Ninguna URL será excluida explícitamente por este ajuste.
  - **Valor recomendado:** Utilizar según sea necesario para páginas sensibles o irrelevantes.
  - **Escenario / ejemplo de comerciante:** Tiene páginas de prueba internas, promociones desactualizadas o páginas de datos de clientes sensibles a las que no quiere que la IA acceda en absoluto.
- **Excluir Productos por Categoría:**

  - **Qué hace este ajuste:** Proporciona una forma de excluir todos los productos que pertenecen a categorías específicas del archivo `llms.txt`.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá una lista de sus categorías, permitiéndole seleccionar cuáles excluir. Todos los productos dentro de las categorías seleccionadas serán omitidos.
    - *Cuando está deshabilitado:* Todos los productos serán considerados para su inclusión, independientemente de la categoría.
  - **Valor recomendado:** Utilizar según sea necesario.
  - **Escenario / ejemplo de comerciante:** Vende tanto productos públicos como una gama de productos solo para B2B en una categoría específica que no desea que la IA indexe para la búsqueda pública general.
- **Excluir Productos por Fabricante:**

  - **Qué hace este ajuste:** Le permite excluir todos los productos de fabricantes específicos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá una lista de sus fabricantes para su selección. Los productos de los fabricantes seleccionados serán omitidos.
    - *Cuando está deshabilitado:* Todos los productos serán considerados para su inclusión, independientemente del fabricante.
  - **Valor recomendado:** Utilizar según sea necesario.
  - **Escenario / ejemplo de comerciante:** Dejó de vender temporalmente productos de una marca en particular y no quiere que la IA los muestre, incluso si todavía están en su catálogo.
- **Excluir Productos por Proveedor:**

  - **Qué hace este ajuste:** Le permite excluir todos los productos de proveedores específicos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá una lista de sus proveedores para su selección. Los productos de los proveedores seleccionados serán omitidos.
    - *Cuando está deshabilitado:* Todos los productos serán considerados para su inclusión, independientemente del proveedor.
  - **Valor recomendado:** Utilizar según sea necesario.
  - **Escenario / ejemplo de comerciante:** Tiene un proveedor cuyos productos no están destinados a la indexación pública por IA.
- **Excluir Productos por Característica:**

  - **Qué hace este ajuste:** Le permite excluir productos basándose en características de producto específicas (por ejemplo, "Color: Rojo", "Material: Madera").
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Puede seleccionar características y sus valores. Los productos que coincidan con estas características serán omitidos.
    - *Cuando está deshabilitado:* Las características del producto no se utilizarán para la exclusión.
  - **Valor recomendado:** Utilizar según sea necesario.
  - **Escenario / ejemplo de comerciante:** Tiene productos marcados con una característica "Descatalogado" que desea ocultar a la IA.
- **Excluir Productos por Atributo:**

  - **Qué hace este ajuste:** Le permite excluir productos basándose en atributos de producto específicos (por ejemplo, "Talla: XL", "Peso: 1kg").
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Puede seleccionar atributos y sus valores. Los productos que coincidan con estos atributos serán omitidos.
    - *Cuando está deshabilitado:* Los atributos del producto no se utilizarán para la exclusión.
  - **Valor recomendado:** Utilizar según sea necesario.
  - **Escenario / ejemplo de comerciante:** Tiene productos con una combinación de atributos "Sin Stock" que no desea que la IA muestre.
- **Excluir Productos por Rango de Precios:**

  - **Qué hace este ajuste:** Le permite excluir productos que se encuentran dentro de un rango de precios especificado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Puede introducir un precio mínimo y máximo. Los productos con precios dentro de este rango serán omitidos.
    - *Cuando está deshabilitado:* Los precios de los productos no se utilizarán para la exclusión.
  - **Valor recomendado:** Utilizar según sea necesario.
  - **Escenario / ejemplo de comerciante:** Solo quiere que la IA indexe sus productos premium (por ejemplo, excluir productos de menos de 10 $).
- **Excluir Productos por Cantidad de Stock:**

  - **Qué hace este ajuste:** Le permite excluir productos basándose en su cantidad de stock actual.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Puede establecer una cantidad mínima de stock. Los productos con stock por debajo de esta cantidad serán omitidos.
    - *Cuando está deshabilitado:* La cantidad de stock del producto no se utilizará para la exclusión.
  - **Valor recomendado:** SÍ (Excluir productos con 0 stock para evitar que la IA recomiende artículos no disponibles).
  - **Escenario / ejemplo de comerciante:** No quiere que la IA muestre productos que están agotados. Establezca esto para excluir productos con stock <= 0.
- **Excluir Productos por Visibilidad:**

  - **Qué hace este ajuste:** Le permite excluir productos basándose en su configuración de visibilidad de PrestaShop (por ejemplo, "Solo catálogo", "Solo búsqueda", "En todas partes").
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Puede seleccionar qué opciones de visibilidad excluir. Los productos que coincidan con estas serán omitidos.
    - *Cuando está deshabilitado:* La visibilidad del producto no se utilizará para la exclusión.
  - **Valor recomendado:** Utilizar según sea necesario.
  - **Escenario / ejemplo de comerciante:** Tiene productos configurados como "Solo catálogo" (no buscables) que también desea ocultar a la IA.
- **Excluir Productos por Estado:**

  - **Qué hace este ajuste:** Le permite excluir productos basándose en su estado activo/inactivo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Puede optar por excluir productos inactivos.
    - *Cuando está deshabilitado:* Se considerarán tanto los productos activos como los inactivos.
  - **Valor recomendado:** SÍ (Excluir productos inactivos).
  - **Escenario / ejemplo de comerciante:** Quiere que la IA solo muestre productos actualmente disponibles y activos.
- **Excluir Productos por Fecha de Adición:**

  - **Qué hace este ajuste:** Le permite excluir productos basándose en la fecha en que se añadieron a su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Puede establecer un rango de fechas. Los productos añadidos fuera de este rango serán omitidos.
    - *Cuando está deshabilitado:* La fecha de adición del producto no se utilizará para la exclusión.
  - **Valor recomendado:** Utilizar según sea necesario.
  - **Escenario / ejemplo de comerciante:** Solo quiere que la IA indexe productos añadidos en el último año.
- **Excluir Productos por Fecha de Actualización:**

  - **Qué hace este ajuste:** Le permite excluir productos basándose en su última fecha de actualización.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Puede establecer un rango de fechas. Los productos actualizados fuera de este rango serán omitidos.
    - *Cuando está deshabilitado:* La fecha de actualización del producto no se utilizará para la exclusión.
  - **Valor recomendado:** Utilizar según sea necesario.
  - **Escenario / ejemplo de comerciante:** Solo quiere que la IA indexe productos que han sido actualizados o revisados recientemente.
- **Excluir Productos por IDs de Producto Específicos:**

  - **Qué hace este ajuste:** Le permite introducir manualmente una lista de IDs de producto específicos separados por comas para excluir.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los productos con los IDs especificados serán omitidos.
    - *Cuando está deshabilitado:* Ningún producto será excluido por ID.
  - **Valor recomendado:** Utilizar según sea necesario.
  - **Escenario / ejemplo de comerciante:** Tiene algunos productos específicos que son problemáticos o sensibles y nunca deben ser indexados por la IA.

#### Ajustes Avanzados

- **Programación de Regeneración (Cron Job):**

  - **Qué hace este ajuste:** Define la frecuencia con la que el archivo `llms.txt` debe regenerarse automáticamente. Esto es crucial para mantener el archivo actualizado sin intervención manual.
  - **Efecto de cambiar este ajuste:**
    - *Diario / Semanal / Mensual:* El módulo proporcionará una URL de cron job. Cuando se accede a esta URL (por ejemplo, por el servicio cron de su proveedor de alojamiento), el archivo `llms.txt` (y `llms-full.txt`) se reconstruirá.
    - *Manual:* Tendrá que hacer clic en el botón "Generar LLMS.txt" manualmente cada vez que desee actualizar el archivo.
  - **Valor recomendado:** Diario (para la mayoría de las tiendas activas).
  - **Escenario / ejemplo de comerciante:** Añade nuevos productos o actualiza precios regularmente. Establecer una regeneración diaria asegura que los rastreadores de IA siempre obtengan la información más reciente. El módulo mostrará la URL de cron que necesita configurar en su servidor.
- **Soporte Multitienda:**

  - **Qué hace este ajuste:** Si ejecuta una Multitienda de PrestaShop, esta opción le permite generar archivos `llms.txt` separados para cada una de sus tiendas o un solo archivo para todas las tiendas.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado:* El módulo respetará su contexto Multitienda y generará archivos específicos para el contenido de cada tienda.
    - *Deshabilitado:* El módulo podría generar un solo archivo basado en la tienda predeterminada o comportarse de forma inesperada en un entorno Multitienda.
  - **Valor recomendado:** SÍ (si utiliza Multitienda).
  - **Escenario / ejemplo de comerciante:** Tiene diferentes catálogos de productos o idiomas para cada tienda en su configuración Multitienda, y necesita archivos `llms.txt` distintos para cada uno.
- **Tiempo de Vida de la Caché (minutos):**

  - **Qué hace este ajuste:** Determina cuánto tiempo se almacena en caché el archivo `llms.txt` generado antes de que se considere "obsoleto" y necesite regeneración (para el tipo de archivo dinámico).
  - **Efecto de cambiar este ajuste:**
    - *Valor más alto:* Regeneración menos frecuente, potencialmente más rápida para los bots de IA, pero el contenido podría ser ligeramente más antiguo.
    - *Valor más bajo:* Regeneración más frecuente, asegurando un contenido más fresco pero potencialmente una mayor carga del servidor.
  - **Valor recomendado:** 60 (1 hora) para dinámico, o irrelevante para estático.
  - **Escenario / ejemplo de comerciante:** Si utiliza la generación dinámica y sus datos de productos cambian cada hora, establezca esto en 60. Si los cambios son menos frecuentes, puede aumentarlo.
- **Habilitar Análisis y Seguimiento de Bots:**

  - **Qué hace este ajuste:** Activa una función para rastrear cuándo los bots de IA acceden a su archivo `llms.txt`, proporcionando información sobre su actividad.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El módulo registrará los accesos al archivo `llms.txt`, que se pueden ver en el panel del módulo.
    - *Cuando está deshabilitado:* No se recopilarán datos de acceso de bots.
  - **Valor recomendado:** SÍ (Útil para comprender la actividad de los rastreadores de IA).
  - **Escenario / ejemplo de comerciante:** Quiere ver con qué frecuencia los modelos de IA están rastreando su tienda y cuáles son los más activos.
- **Botón Borrar Caché:**

  - **Qué hace este ajuste:** Un botón manual para borrar cualquier archivo `llms.txt` almacenado en caché.
  - **Efecto de cambiar este ajuste:** Elimina inmediatamente cualquier archivo `llms.txt` almacenado, forzando una nueva regeneración en la siguiente solicitud (para dinámico) o cuando se hace clic en el botón "Generar LLMS.txt" (para estático).
  - **Valor recomendado:** Haga clic cuando realice cambios significativos en su configuración o catálogo de productos y quiera asegurarse de que el archivo `llms.txt` se actualice inmediatamente.
  - **Escenario / ejemplo de comerciante:** Acaba de añadir una nueva línea de productos importante y quiere que la IA la descubra de inmediato, así que borra la caché y regenera.
- **Botón Generar LLMS.txt:**

  - **Qué hace este ajuste:** Un botón manual para generar o regenerar inmediatamente el archivo `llms.txt` basándose en su configuración actual.
  - **Efecto de cambiar este ajuste:** El módulo procesa su catálogo y configuración, luego crea o actualiza el archivo `llms.txt`.
  - **Valor recomendado:** Haga clic después de realizar cualquier cambio de configuración o cuando necesite una actualización inmediata, especialmente si utiliza la generación de archivos estáticos.
  - **Escenario / ejemplo de comerciante:** Ha terminado de configurar todas sus reglas de exclusión y quiere crear el archivo `llms.txt` inicial.

#### Anulaciones por Producto (Página de Producto del Administrador)

El módulo también se integra directamente en sus páginas de edición de productos en el Back Office.

- **Excluir este producto de LLMS.txt:**
  - **Qué hace este ajuste:** Una casilla de verificación en las páginas de productos individuales que le permite anular la configuración global y excluir específicamente un solo producto del archivo `llms.txt`.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está marcada:* Este producto específico no se incluirá en el archivo `llms.txt`, independientemente de otras reglas de inclusión global.
    - *Cuando está desmarcada:* La inclusión del producto se determinará por la configuración global.
  - **Valor recomendado:** Utilizar según sea necesario para productos específicos.
  - **Escenario / ejemplo de comerciante:** Tiene un producto temporalmente no disponible, o un artículo muy específico que no desea que la IA promocione ampliamente.

#### Anulaciones por Categoría (Página de Categoría del Administrador)

De manera similar, el módulo se integra en sus páginas de edición de categorías.

- **Excluir esta categoría de LLMS.txt:**
  - **Qué hace este ajuste:** Una casilla de verificación en las páginas de categorías individuales que le permite anular la configuración global y excluir específicamente una categoría completa (y sus productos) del archivo `llms.txt`.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está marcada:* Esta categoría específica y todos los productos dentro de ella no se incluirán en el archivo `llms.txt`.
    - *Cuando está desmarcada:* La inclusión de la categoría se determinará por la configuración global.
  - **Valor recomendado:** Utilizar según sea necesario para categorías específicas.
  - **Escenario / ejemplo de comerciante:** Tiene una categoría de "Liquidación" que cambia con frecuencia y prefiere que la IA no la indexe, o una categoría para uso interno.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### Panel de Control (Back Office > Módulos > LLMS.txt Generator Pro > Panel de Control)

- **Nombre de la Pantalla y Ubicación del Menú:** Esta pantalla es accesible desde la página principal de configuración del módulo, generalmente a través de una pestaña o enlace de "Panel de Control". Proporciona una visión general de la actividad de los bots de IA y el estado del módulo.
- **Acciones y Ajustes Disponibles:**
  - **Análisis de Tráfico de Bots:** Muestra gráficos o tablas que indican qué rastreadores de IA (agentes de usuario) han accedido a su archivo `llms.txt`, con qué frecuencia y cuándo.
  - **Estado de la Última Generación:** Muestra cuándo se generó por última vez el archivo `llms.txt`, su tamaño y el número de URLs incluidas.
  - **Registros de Errores:** Cualquier problema encontrado durante la generación se mostrará aquí.
- **Efecto de los cambios:** Esta pantalla es principalmente para monitoreo e informes. Los cambios aquí suelen estar relacionados con la visualización de datos, no con la alteración del comportamiento de la tienda.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise periódicamente el panel de control para asegurarse de que su archivo `llms.txt` está siendo accedido por los bots de IA como se espera y para monitorear cualquier error. Esto le ayuda a comprender el impacto de su estrategia de visibilidad de IA.

#### Vista Previa (Back Office > Módulos > LLMS.txt Generator Pro > Vista Previa)

- **Nombre de la Pantalla y Ubicación del Menú:** Accesible desde la página principal de configuración del módulo, generalmente a través de una pestaña o enlace de "Vista Previa".
- **Acciones y Ajustes Disponibles:**
  - **Visualización del Contenido de LLMS.txt:** Muestra el contenido real del archivo `llms.txt` que se serviría a los rastreadores de IA, basándose en su configuración actual.
  - **Visualización del Contenido de llms-full.txt:** Si está habilitado, también muestra el contenido del archivo `llms-full.txt`.
- **Efecto de los cambios:** Esta pantalla es para verificación. Le permite revisar el contenido generado antes de que esté en vivo o después de realizar cambios, asegurándose de que cumple con sus requisitos.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Después de realizar cambios significativos en la configuración de su módulo o en el catálogo de productos, utilice la pantalla de vista previa para verificar que las URLs correctas están incluidas y excluidas.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Habilitar la Generación de LLMS.txt | SÍ | Activa/desactiva la función principal del módulo. |
| Configuración del Módulo | Tipo de Archivo LLMS.txt | Estático | Elija estático para rendimiento, dinámico para actualizaciones en tiempo real. |
| Configuración del Módulo | Generar llms-full.txt | SÍ | Proporciona un archivo más completo para la IA. |
| Configuración del Módulo | Incluir Páginas de Producto | SÍ | Hace que las URLs de productos sean descubribles por la IA. |
| Configuración del Módulo | Incluir Páginas de Categoría | SÍ | Hace que las URLs de categorías sean descubribles por la IA. |
| Configuración del Módulo | Incluir Páginas CMS | SÍ | Hace que las páginas informativas sean descubribles por la IA. |
| Configuración del Módulo | Incluir Páginas de Fabricantes/Marcas | SÍ | Hace que las páginas de marcas sean descubribles por la IA. |
| Configuración del Módulo | Incluir Páginas de Proveedores | NO | Generalmente no es necesario para la indexación pública de IA. |
| Configuración del Módulo | Incluir Página de Nuevos Productos | SÍ | Destaca los últimos productos a la IA. |
| Configuración del Módulo | Incluir Página de Mejores Ventas | SÍ | Promueve los artículos más vendidos a la IA. |
| Configuración del Módulo | Incluir Página de Bajada de Precios | SÍ | Destaca los artículos con descuento a la IA. |
| Configuración del Módulo | Incluir Página de Contacto | SÍ | Proporciona información de contacto a la IA. |
| Configuración del Módulo | Incluir Página de Mapa del Sitio | SÍ | Ayuda a la IA a descubrir más contenido. |
| Configuración del Módulo | Incluir URLs Personalizadas | Usar según sea necesario | Añade URLs específicas que no son de PrestaShop. |
| Configuración del Módulo | Excluir URLs Específicas | Usar según sea necesario | Oculta URLs sensibles o irrelevantes. |
| Configuración del Módulo | Excluir Productos por Categoría | Usar según sea necesario | Filtra productos por categoría. |
| Configuración del Módulo | Excluir Productos por Fabricante | Usar según sea necesario | Filtra productos por fabricante. |
| Configuración del Módulo | Excluir Productos por Proveedor | Usar según sea necesario | Filtra productos por proveedor. |
| Configuración del Módulo | Excluir Productos por Característica | Usar según sea necesario | Filtra productos por características específicas. |
| Configuración del Módulo | Excluir Productos por Atributo | Usar según sea necesario | Filtra productos por atributos específicos. |
| Configuración del Módulo | Excluir Productos por Rango de Precios | Usar según sea necesario | Filtra productos dentro de un rango de precios. |
| Configuración del Módulo | Excluir Productos por Cantidad de Stock | SÍ (<=0) | Oculta productos agotados a la IA. |
| Configuración del Módulo | Excluir Productos por Visibilidad | Usar según sea necesario | Filtra productos por visibilidad de PrestaShop. |
| Configuración del Módulo | Excluir Productos por Estado | SÍ (inactivo) | Oculta productos inactivos a la IA. |
| Configuración del Módulo | Excluir Productos por Fecha de Adición | Usar según sea necesario | Filtra productos por fecha de creación. |
| Configuración del Módulo | Excluir Productos por Fecha de Actualización | Usar según sea necesario | Filtra productos por fecha de última actualización. |
| Configuración del Módulo | Excluir Productos por IDs de Producto Específicos | Usar según sea necesario | Excluye productos individuales por ID. |
| Configuración del Módulo | Programación de Regeneración (Cron Job) | Diaria | Automatiza las actualizaciones de `llms.txt`. |
| Configuración del Módulo | Soporte Multitienda | SÍ (si aplica) | Habilita archivos distintos para cada tienda. |
| Configuración del Módulo | Tiempo de Vida de la Caché (minutos) | 60 (para dinámico) | Establece cuánto tiempo se almacena en caché el archivo dinámico. |
| Configuración del Módulo | Habilitar Análisis y Seguimiento de Bots | SÍ | Monitorea la actividad de los rastreadores de IA. |
| Configuración del Módulo | Botón Borrar Caché | Clicar según sea necesario | Fuerza el borrado de la caché para actualizaciones inmediatas. |
| Configuración del Módulo | Botón Generar LLMS.txt | Clicar según sea necesario | Genera manualmente el archivo `llms.txt`. |
| Página de Edición de Producto | Excluir este producto de LLMS.txt | Desmarcado | Anula la configuración global para un solo producto. |
| Página de Edición de Categoría | Excluir esta categoría de LLMS.txt | Desmarcado | Anula la configuración global para una categoría completa. |
| Panel de Control | Análisis de Tráfico de Bots | N/A | Monitorea el acceso de bots de IA. |
| Panel de Control | Estado de la Última Generación | N/A | Muestra el estado del archivo `llms.txt`. |
| Vista Previa | Visualización del Contenido de LLMS.txt | N/A | Muestra el contenido `llms.txt` generado. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Mi archivo `llms.txt` no aparece o no se actualiza.**
R:

1. **Verifique "Habilitar la Generación de LLMS.txt":** Asegúrese de que esté configurado en SÍ en la configuración del módulo.
2. **Verifique el Tipo de Archivo:** Si está configurado en "Estático", asegúrese de que su servidor tenga permisos de escritura en el directorio raíz de PrestaShop. Además, haga clic manualmente en el botón "Generar LLMS.txt".
3. **Tarea Cron:** Si utiliza una tarea cron, verifique que esté configurada correctamente en su alojamiento y que la URL proporcionada por el módulo sea accesible.
4. **Borrar Caché:** Vaya a **Parámetros Avanzados > Rendimiento** en PrestaShop y borre la caché de Smarty. Luego, intente regenerar el archivo `llms.txt`.
5. **Panel del Módulo:** Verifique el panel del módulo en busca de mensajes de error durante la generación.

**P: He realizado cambios, pero el archivo `llms.txt` no los refleja.**
R:

1. **Regenerar Manualmente:** Haga clic en el botón "Generar LLMS.txt" en la configuración del módulo.
2. **Tiempo de la Tarea Cron:** Si depende de una tarea cron, recuerde que solo se ejecuta en intervalos programados. Sus cambios aparecerán después de la próxima ejecución programada.
3. **Caché:** Si está utilizando la generación dinámica, el archivo `llms.txt` podría estar en caché. Haga clic en el botón "Borrar Caché" en el módulo, o borre la caché de PrestaShop en **Parámetros Avanzados > Rendimiento**.

**P: ¿Cómo sé si los bots de IA están utilizando realmente mi archivo `llms.txt`?**
R: Habilite "Análisis y Seguimiento de Bots" en la configuración del módulo. El panel del módulo le mostrará estadísticas sobre qué agentes de usuario de IA han accedido a su archivo `llms.txt` y cuándo.

**P: El archivo `llms.txt` es demasiado grande o incluye demasiadas URLs irrelevantes.**
R:

1. **Revise la Configuración de Inclusión:** Revise las opciones "Incluir..." y desactive cualquier tipo de contenido que no desee que la IA indexe (por ejemplo, Páginas de Proveedores).
2. **Utilice los Filtros de Exclusión:** Haga un uso extensivo de los filtros "Excluir Productos por..." (Categoría, Stock, Precio, etc.) y "Excluir URLs Específicas" para afinar el contenido.
3. **Anulaciones por Producto/Categoría:** Para casos muy específicos, utilice las casillas de verificación de exclusión en las páginas de edición de productos y categorías individuales.

**P: Mi tema personalizado no muestra correctamente las características del módulo (por ejemplo, campos adicionales en la página del producto).**
R: La integración del módulo con las páginas de productos/categorías es estándar. Si encuentra problemas, es probable que sea un conflicto con su tema personalizado u otro módulo que modifique en gran medida los formularios de edición de productos/categorías.

1. **Busque Conflictos:** Deshabilite temporalmente otros módulos que modifiquen las páginas de productos/categorías para ver si el problema se resuelve.
2. **Anulaciones del Tema:** Su tema podría tener anulaciones de plantilla que impidan que los campos adicionales del módulo se rendericen. Póngase en contacto con el desarrollador de su tema o con un experto en PrestaShop para investigar.
3. **Borrar Caché:** Siempre borre la caché de PrestaShop después de realizar cambios en el tema o el módulo.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo LLMS.txt Generator Pro sigue una arquitectura de módulo estándar de PrestaShop, aprovechando los principios MVC. Opera principalmente a través de una clase de módulo principal (`llmstxtpro/index.php`) para la configuración y gestión de hooks, y un conjunto de clases dedicadas (`classes/`) para la lógica de negocio, el manejo de datos y la generación de archivos. Los controladores frontales gestionan el servicio dinámico de `llms.txt` y la ejecución de tareas cron. La configuración se almacena en `ps_configuration` y tablas personalizadas.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

Estos controladores son responsables de servir los archivos `llms.txt` y `llms-full.txt`, y de manejar las solicitudes de tareas cron.

- `controllers/front/aicatalog.php`
  - **Nombre de la clase y clase padre:** `LlmsTxtProAiCatalogModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Probablemente maneja solicitudes específicas de catálogo de IA, potencialmente para formatos de datos más estructurados más allá de `llms.txt`. Podría servir una representación JSON o XML del catálogo para el consumo de IA.
- `controllers/front/cron.php`
  - **Nombre de la clase y clase padre:** `LlmsTxtProCronModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador está diseñado para ser llamado por una tarea cron del lado del servidor. Cuando se accede a él, activa el proceso de regeneración de `llms.txt` (y `llms-full.txt`) basándose en la configuración del módulo. Normalmente devuelve un simple mensaje de éxito/fracaso.
- `controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `LlmsTxtProIndexModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Esto podría ser un marcador de posición o un punto de entrada genérico. Dados los otros controladores específicos, es menos probable que tenga una función directa y única para la generación de `llms.txt` en sí, pero podría usarse para el enrutamiento general del front-office del módulo o para información.
- `controllers/front/llmsfull.php`
  - **Nombre de la clase y clase padre:** `LlmsTxtProLlmsFullModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Cuando el tipo de archivo `llms-full.txt` se establece en dinámico, este controlador sirve el contenido del archivo `llms-full.txt`. Consulta la base de datos y genera la lista completa de URLs y datos asociados.
- `controllers/front/llmstxt.php`
  - **Nombre de la clase y clase padre:** `LlmsTxtProLlmsTxtModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Cuando el tipo de archivo `llms.txt` se establece en dinámico, este controlador sirve el contenido del archivo `llms.txt` estándar. Consulta la base de datos y genera la lista de URLs basándose en la configuración del módulo y las reglas de exclusión.

#### Controladores de Administración del Back-Office

El módulo no parece tener controladores de administración personalizados dedicados (`controllers/admin/`). Toda la configuración se maneja a través del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Principales (`classes/`)

- `classes/index.php`
  - **Responsabilidad:** Típicamente un archivo vacío para evitar la lista de directorios, no una clase funcional.
- `classes/LlmsTxtProAiCatalog.php`
  - **Responsabilidad:** Probablemente contiene la lógica para generar un catálogo de IA más estructurado (por ejemplo, JSON-LD, marcado schema.org) que podría ser servido por `aicatalog.php`. Encapsularía métodos para consultar datos de productos, categorías y CMS con formato específico de IA.
- `classes/LlmsTxtProAnalytics.php`
  - **Responsabilidad:** Maneja el registro y la recuperación de datos de acceso de bots de IA. Interactuaría con una tabla de base de datos personalizada para almacenar el agente de usuario, la marca de tiempo y la información del archivo accedido (`llms.txt` o `llms-full.txt`). Proporciona métodos para informar estos datos al panel de administración.
- `classes/LlmsTxtProConfig.php`
  - **Responsabilidad:** Una clase auxiliar para gestionar la configuración del módulo. Proporcionaría métodos estáticos para obtener y establecer valores de configuración de `Configuration::get()` y `Configuration::updateValue()`, potencialmente con valores predeterminados y conversión de tipos.
- `classes/LlmsTxtProGenerator.php`
  - **Responsabilidad:** Esta es la clase de lógica central para generar el contenido de `llms.txt` y `llms-full.txt`. Contiene métodos para:
    - Obtener productos, categorías, páginas CMS, fabricantes, proveedores, etc.
    - Aplicar todos los filtros de inclusión y exclusión (por categoría, fabricante, precio, stock, URLs personalizadas, etc.).
    - Formatear las URLs según el estándar `llms.txt`.
    - Manejar la escritura de archivos estáticos en el directorio raíz.
    - Potencialmente gestionar el almacenamiento en caché para la generación dinámica.
- `classes/LlmsTxtProLogger.php`
  - **Responsabilidad:** Una clase de utilidad para registrar eventos, advertencias o errores específicos del módulo. Podría escribir en un archivo de registro personalizado o integrarse con el registrador predeterminado de PrestaShop. Útil para depurar problemas de generación.

### 4.4 Activos JavaScript (`views/js/`)

- `llmstxtpro/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Proporciona funcionalidad de autocompletado para campos de entrada en la configuración de administración, probablemente para seleccionar productos, categorías, fabricantes o URLs específicas para exclusión. Se vincula a los campos de entrada y realiza llamadas AJAX para obtener sugerencias.
- `llmstxtpro/views/js/adminLlmsTxtProDashboard.js`
  - **Alcance:** Back-office (pantalla del Panel de Control).
  - **Responsabilidad:** Maneja la visualización dinámica de datos analíticos en el panel de control del módulo. Podría usar AJAX para obtener estadísticas de tráfico de bots de `LlmsTxtProAnalytics` y renderizarlas usando bibliotecas de gráficos o tablas de datos.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `llmstxtpro/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Estiliza los desplegables y sugerencias de autocompletado utilizados en los formularios de configuración de administración.
- `llmstxtpro/views/css/admin-config.css`
  - **Alcance:** Back-office (página de Configuración del Módulo).
  - **Responsabilidad:** Proporciona un estilo específico para el formulario de configuración principal del módulo, asegurando un diseño consistente y fácil de usar dentro del Back Office de PrestaShop.
- `llmstxtpro/views/css/admin-dashboard.css`
  - **Alcance:** Back-office (pantalla del Panel de Control).
  - **Responsabilidad:** Estiliza los elementos del panel de control, incluidos gráficos, tablas e indicadores de estado para el análisis de tráfico de bots y el estado de generación.
- `llmstxtpro/views/css/admin-searchtool.css`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Estilo general para los componentes de la interfaz de usuario relacionados con la búsqueda dentro de la administración, potencialmente compartido con `autocomplete.css` o para otras interfaces de búsqueda/filtro.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**: La descripción del módulo no lista explícitamente plantillas de hook, lo que sugiere que su presencia en el front-office es principalmente a través del propio archivo `llms.txt` generado, no de elementos visuales.
- **Plantillas de administración (`views/templates/admin/`)**:
  - `llmstxtpro/views/templates/admin/category-extra.tpl`
    - **Propósito:** Renderiza la casilla de verificación "Excluir esta categoría de LLMS.txt" y cualquier campo relacionado en la página de edición de categorías de PrestaShop. Esta plantilla probablemente está enganchada a `displayAdminProductsExtra` o similar.
  - `llmstxtpro/views/templates/admin/configure.tpl`
    - **Propósito:** La plantilla principal para la página de configuración del módulo (método `getContent()`). Renderiza todos los ajustes generales, opciones de inclusión/exclusión, ajustes avanzados y botones de acción.
  - `llmstxtpro/views/templates/admin/dashboard.tpl`
    - **Propósito:** Renderiza el panel de análisis del módulo, mostrando el tráfico de bots, el estado de generación y, potencialmente, los registros de errores.
  - `llmstxtpro/views/templates/admin/preview.tpl`
    - **Propósito:** Renderiza el contenido de los archivos `llms.txt` y `llms-full.txt` generados para su revisión dentro del Back Office.
  - `llmstxtpro/views/templates/admin/product-extra.tpl`
    - **Propósito:** Renderiza la casilla de verificación "Excluir este producto de LLMS.txt" y cualquier campo relacionado en la página de edición de productos de PrestaShop. Esta plantilla probablemente está enganchada a `displayAdminProductsExtra` o similar.
- **Plantillas del front-office (`views/templates/front/`)**: Ninguna listada explícitamente, lo que refuerza que la interacción del módulo con el front-office es principalmente máquina a máquina a través del archivo `llms.txt`.
- `llmstxtpro/lib/searchTool/views/scripts.tpl`
  - **Propósito:** Probablemente incluye activos JavaScript y CSS para la herramienta de búsqueda (por ejemplo, autocomplete.js, autocomplete.css) dentro del contexto de administración.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

- **Tablas de la Base de Datos**:
  - `ps_configuration`: Almacena todas las configuraciones del módulo (por ejemplo, `LLMSTXTPRO_ENABLED`, `LLMSTXTPRO_FILE_TYPE`, `LLMSTXTPRO_INCLUDE_PRODUCTS`, `LLMSTXTPRO_EXCLUDE_URLS`, etc.).
  - `ps_llmstxtpro_product_override`: Una tabla personalizada para almacenar la configuración de exclusión por producto. (Probablemente `id_product`, `excluded`).
  - `ps_llmstxtpro_category_override`: Una tabla personalizada para almacenar la configuración de exclusión por categoría. (Probablemente `id_category`, `excluded`).
  - `ps_llmstxtpro_analytics_log`: Una tabla personalizada para almacenar los registros de acceso de bots (por ejemplo, `id_llmstxtpro_analytics_log`, `user_agent`, `access_time`, `file_type`).
  - `ps_llmstxtpro_urls`: Potencialmente una tabla para almacenar en caché las URLs generadas para mejorar el rendimiento, especialmente para la generación de archivos estáticos. (Probablemente `id_url`, `url`, `file_type`, `date_add`).
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Antes de que el controlador de administración renderice su contenido. | Inyecta el CSS/JS del módulo para la configuración de administración, el panel de control y los campos adicionales de productos/categorías. |
| `displayAdminProductsExtra` | En la página de edición de productos. | Renderiza la casilla de verificación "Excluir este producto de LLMS.txt". |
| `displayAdminCategoriesExtra` | En la página de edición de categorías. | Renderiza la casilla de verificación "Excluir esta categoría de LLMS.txt". |
| `actionModuleInstall` | Durante la instalación del módulo. | Crea tablas de base de datos, establece valores de configuración predeterminados. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Elimina tablas de base de datos y valores de configuración. |
| `displayHeader` | En la sección `<head>` de las páginas del front-office. | (Menos probable para este módulo, pero podría usarse para metaetiquetas o enlaces específicos de IA si fuera necesario). |
| `displayRightColumn` | En la columna derecha de las páginas del front-office. | (No directamente relevante para la generación de `llms.txt`). |
| `displayFooter` | En el pie de página de las páginas del front-office. | (No directamente relevante para la generación de `llms.txt`). |
| `actionProductUpdate` | Después de que se actualiza un producto. | Potencialmente activa un borrado de caché o marca para regeneración si se utiliza `llms.txt` dinámico. |
| `actionCategoryUpdate` | Después de que se actualiza una categoría. | Potencialmente activa un borrado de caché o marca para regeneración. |
| `actionObjectProductAddAfter` | Después de que se añade un nuevo producto. | Potencialmente activa un borrado de caché o marca para regeneración. |
| `actionObjectCategoryAddAfter` | Después de que se añade una nueva categoría. | Potencialmente activa un borrado de caché o marca para regeneración. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con el módulo LLMS.txt Generator Pro.

---
title: "Exportar productos a Delcampe Lister - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Exportar productos a Delcampe Lister' de MyPresta.eu."
sidebar:
  label: "Exportar productos a Delcampe Lister - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Export products to Delcampe Lister en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/export-products-to-delcampe-lister.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/export-products-to-delcampe-lister/)
>
> ---


# Exportar productos a Delcampe Lister

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para que PrestaShop funcione correctamente y deberían estar disponibles en la mayoría de los entornos de alojamiento.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Puede acceder a esta pantalla navegando a **Módulos > Gestor de módulos** y haciendo clic en "Configurar" junto a "Exportar productos a Delcampe Lister".

Esta pantalla maneja principalmente la configuración general del módulo, incluidas las comprobaciones de actualización.

-   **MyPresta.eu Live Update Check (Comprobación de actualizaciones en vivo de MyPresta.eu):**
    -   **Qué hace este ajuste:** Esta opción controla si el módulo busca automáticamente nuevas versiones y actualizaciones disponibles en MyPresta.eu.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* El módulo se conectará periódicamente a MyPresta.eu para ver si hay una versión más reciente disponible. Esto le ayuda a mantenerse actualizado con las correcciones de errores y las nuevas funciones.
        -   *Cuando está deshabilitado:* El módulo no buscará actualizaciones automáticamente. Tendría que buscar actualizaciones manualmente en su cuenta de MyPresta.eu.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo de comerciante:** Mantener esto habilitado asegura que siempre esté ejecutando la versión más estable y rica en funciones del módulo sin necesidad de recordar verificar manualmente.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### 2.2.1 Gestión de productos Delcampe (Back Office > Catálogo > Productos Delcampe)

Esta es la pantalla principal de gestión para sus exportaciones de productos Delcampe. Puede acceder a ella navegando a **Catálogo > Productos Delcampe** en el menú de su Back Office de PrestaShop.

Esta pantalla proporciona una vista de cuadrícula de sus productos y le permite gestionar sus configuraciones de exportación para Delcampe. Puede agregar nuevos productos a la lista de exportación, editar los existentes y generar el archivo de exportación.

**Acciones y configuraciones disponibles:**

-   **Tabla de listado de productos:** Esta tabla muestra todos los productos que ya están configurados para la exportación a Delcampe o que están disponibles para ser configurados. Verá columnas como el ID del producto, el nombre y, potencialmente, sus configuraciones específicas de Delcampe.
-   **Añadir nuevo producto / Editar producto:**
    -   Al hacer clic en "Añadir nuevo" o editar un producto existente, se abrirá un formulario donde podrá definir parámetros específicos de listado de Delcampe para ese producto.
    -   **`category_id` (ID de categoría de Delcampe):**
        -   **Qué hace este ajuste:** Este es el ID de categoría específico en Delcampe donde se listará su producto. Delcampe tiene su propia estructura de categorías, que puede diferir de la de PrestaShop.
        -   **Efecto de cambiar este ajuste:** Los ID de categoría incorrectos harán que su producto se liste en la sección incorrecta en Delcampe, o que potencialmente falle la publicación.
        -   **Valor recomendado:** El ID numérico exacto de la categoría de Delcampe de destino.
        -   **Escenario / ejemplo de comerciante:** Si está vendiendo un sello raro, buscaría el ID de categoría de "Sellos" apropiado en Delcampe y lo introduciría aquí.
    -   **`title` (Título del listado de Delcampe):**
        -   **Qué hace este ajuste:** El título que aparecerá para su producto en Delcampe. Esto puede ser diferente del nombre de su producto en PrestaShop.
        -   **Efecto de cambiar este ajuste:** Un título atractivo y rico en palabras clave puede mejorar significativamente la visibilidad en Delcampe.
        -   **Valor recomendado:** Un título descriptivo y conciso optimizado para las búsquedas en Delcampe.
        -   **Escenario / ejemplo de comerciante:** En lugar de "Sello Antiguo", podría usar "Sello Francés Raro de 1920 - Sin Usar - Excelente Condición".
    -   **`description` (Descripción del listado de Delcampe):**
        -   **Qué hace este ajuste:** La descripción detallada del producto que se mostrará en su listado de Delcampe.
        -   **Efecto de cambiar este ajuste:** Una descripción completa con todos los detalles relevantes ayuda a los compradores a tomar decisiones informadas y genera confianza.
        -   **Valor recomendado:** Una descripción completa, que potencialmente incluya contexto histórico, condición y dimensiones.
        -   **Escenario / ejemplo de comerciante:** Copie su descripción de PrestaShop, pero considere agregar detalles o formato específicos de Delcampe.
    -   **`personal_reference` (Su referencia interna):**
        -   **Qué hace este ajuste:** Un campo opcional para su propio número de seguimiento o referencia interna del producto en Delcampe.
        -   **Efecto de cambiar este ajuste:** Le ayuda a relacionar las ventas de Delcampe con su sistema de inventario interno.
        -   **Valor recomendado:** Su referencia de producto o SKU de PrestaShop.
        -   **Escenario / ejemplo de comerciante:** Usar su SKU de PrestaShop aquí le permite identificar rápidamente el producto en su tienda cuando llega un pedido de Delcampe.
    -   **`currency` (Moneda del listado):**
        -   **Qué hace este ajuste:** La moneda en la que se listará el producto en Delcampe.
        -   **Efecto de cambiar este ajuste:** Debe coincidir con una moneda compatible con Delcampe.
        -   **Valor recomendado:** Su moneda de venta principal (por ejemplo, EUR, USD).
        -   **Escenario / ejemplo de comerciante:** Si vende principalmente en euros, establezca esto en EUR.
    -   **`selling_type` (Tipo de venta de Delcampe):**
        -   **Qué hace este ajuste:** Define cómo se vende el producto en Delcampe (por ejemplo, subasta, precio fijo).
        -   **Efecto de cambiar este ajuste:** Determina el proceso de compra para los clientes en Delcampe.
        -   **Valor recomendado:** Elija el tipo que mejor se adapte a su producto y estrategia de ventas (por ejemplo, "Precio Fijo" para artículos estándar, "Subasta" para artículos raros).
        -   **Escenario / ejemplo de comerciante:** Para un coleccionable común, "Precio Fijo" podría ser adecuado. Para un artículo verdaderamente único, una "Subasta" podría generar ofertas más altas.
    -   **`price` (Precio inicial / Precio fijo):**
        -   **Qué hace este ajuste:** El precio inicial para una subasta o el precio fijo para una venta directa.
        -   **Efecto de cambiar este ajuste:** Impacta directamente en el costo para el comprador.
        -   **Valor recomendado:** Su precio de venta deseado.
        -   **Escenario / ejemplo de comerciante:** Para un artículo de precio fijo, este sería su precio de venta al público. Para una subasta, es la oferta mínima.
    -   **`initial_quantity` (Cantidad disponible):**
        -   **Qué hace este ajuste:** El número de unidades de este producto que está poniendo a disposición en Delcampe.
        -   **Efecto de cambiar este ajuste:** Determina cuántos artículos puede comprar un comprador.
        -   **Valor recomendado:** Su nivel de stock actual para el producto.
        -   **Escenario / ejemplo de comerciante:** Si tiene 5 de un sello en particular, establezca esto en 5.
    -   **`minimum_bid_step` (Incremento de la oferta en subasta):**
        -   **Qué hace este ajuste:** Para los listados tipo subasta, esto define la cantidad mínima en la que debe aumentar una oferta.
        -   **Efecto de cambiar este ajuste:** Influye en el comportamiento de las ofertas.
        -   **Valor recomendado:** Un incremento razonable (por ejemplo, 0.50, 1.00).
        -   **Escenario / ejemplo de comerciante:** Si se establece en 1.00, una oferta de 10.00 requeriría que la siguiente oferta fuera de al menos 11.00.
    -   **`renew_duration` (Duración de la renovación automática):**
        -   **Qué hace este ajuste:** Si está habilitado, especifica cuánto tiempo se renovará automáticamente un listado no vendido.
        -   **Efecto de cambiar este ajuste:** Mantiene su producto listado en Delcampe sin intervención manual.
        -   **Valor recomendado:** Una duración que se alinee con su ciclo de ventas (por ejemplo, 7 días, 14 días).
        -   **Escenario / ejemplo de comerciante:** Si un artículo no se vende en 7 días, se volverá a listar automáticamente por otros 7 días.
    -   **`renew_total_count` (Límite de renovación automática):**
        -   **Qué hace este ajuste:** El número máximo de veces que se renovará automáticamente un listado no vendido.
        -   **Efecto de cambiar este ajuste:** Evita la renovación indefinida de artículos impopulares.
        -   **Valor recomendado:** Un límite razonable (por ejemplo, 3, 5).
        -   **Escenario / ejemplo de comerciante:** Si un artículo no se vende después de 3 renovaciones, se eliminará de Delcampe.
    -   **`shipping_model` (Modelo de envío de Delcampe):**
        -   **Qué hace este ajuste:** El método o modelo de envío que utiliza en Delcampe. Esto debe corresponder a sus configuraciones de envío preconfiguradas en Delcampe.
        -   **Efecto de cambiar este ajuste:** Determina cómo se calculan y presentan los costos de envío al comprador.
        -   **Valor recomendado:** El ID o nombre de su modelo de envío preferido de Delcampe.
        -   **Escenario / ejemplo de comerciante:** Si tiene un modelo de "Envío Internacional Estándar" configurado en Delcampe, introduciría su identificador aquí.
    -   **`weight` (Peso del producto):**
        -   **Qué hace este ajuste:** El peso del producto, utilizado para los cálculos de envío en Delcampe.
        -   **Efecto de cambiar este ajuste:** Crucial para una estimación precisa del costo de envío.
        -   **Valor recomendado:** El peso real del producto.
        -   **Escenario / ejemplo de comerciante:** Introduzca "0.1" para un sello ligero.
    -   **`lister_sale_end_time` (Hora de finalización de la venta):**
        -   **Qué hace este ajuste:** La hora específica del día en que finalizará el listado.
        -   **Efecto de cambiar este ajuste:** Le permite programar el final de sus listados.
        -   **Valor recomendado:** Una hora en la que su público objetivo sea más propenso a estar en línea (por ejemplo, 20:00).
        -   **Escenario / ejemplo de comerciante:** Terminar una subasta a las 8 PM un domingo podría atraer más ofertas de última hora.
    -   **`lister_sale_end_day` (Día de finalización de la venta):**
        -   **Qué hace este ajuste:** El día específico de la semana en que finalizará el listado.
        -   **Efecto de cambiar este ajuste:** Le permite programar el final de sus listados.
        -   **Valor recomendado:** Un día en el que su público objetivo sea más propenso a estar en línea (por ejemplo, domingo).
        -   **Escenario / ejemplo de comerciante:** Terminar una subasta un domingo podría atraer más ofertas de última hora.
    -   **`option_last_minute_extension` (Extensión de último minuto):**
        -   **Qué hace este ajuste:** Si está habilitado, extiende la duración de la subasta si se realiza una oferta en los minutos finales.
        -   **Efecto de cambiar este ajuste:** Evita el "sniping" (ofertas de último segundo) y fomenta ofertas más altas.
        -   **Valor recomendado:** SÍ (para subastas).
        -   **Escenario / ejemplo de comerciante:** Una oferta realizada 30 segundos antes de que termine una subasta extenderá la subasta unos minutos, dando a otros la oportunidad de contraofertar.
    -   **`option_anonymous_buyer` (Comprador anónimo):**
        -   **Qué hace este ajuste:** Oculta la identidad del comprador a otros postores en una subasta.
        -   **Efecto de cambiar este ajuste:** Puede aumentar la privacidad de los postores.
        -   **Valor recomendado:** NO (a menos que las preocupaciones específicas de privacidad sean primordiales).
        -   **Escenario / ejemplo de comerciante:** Si desea proteger la privacidad del comprador, habilite esto.
    -   **`option_strong_title` (Título fuerte / Título en negrita):**
        -   **Qué hace este ajuste:** Pone el título de su listado en negrita en Delcampe, aumentando su visibilidad.
        -   **Efecto de cambiar este ajuste:** Su listado se destaca más en los resultados de búsqueda.
        -   **Valor recomendado:** SÍ.
        -   **Escenario / ejemplo de comerciante:** Usar un título en negrita ayuda a que su listado de sellos raros llame la atención de los coleccionistas que buscan muchos artículos similares.
    -   **`option_background_color` (Color de fondo):**
        -   **Qué hace este ajuste:** Establece un color de fondo personalizado para su listado en Delcampe.
        -   **Efecto de cambiar este ajuste:** Puede hacer que su listado sea más atractivo visualmente o que coincida con su marca.
        -   **Valor recomendado:** Dejar vacío o usar un color sutil.
        -   **Escenario / ejemplo de comerciante:** Usar un fondo azul claro podría hacer que su listado destaque sin ser una distracción.
    -   **`option_border_color` (Color del borde):**
        -   **Qué hace este ajuste:** Establece un color de borde personalizado para su listado en Delcampe.
        -   **Efecto de cambiar este ajuste:** Puede hacer que su listado sea más atractivo visualmente o que coincida con su marca.
        -   **Valor recomendado:** Dejar vacío o usar un color sutil.
        -   **Escenario / ejemplo de comerciante:** Un borde delgado y oscuro puede darle a su listado un aspecto más profesional.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1.  **Identifique productos para Delcampe:** Decida cuáles de sus productos de PrestaShop son adecuados para el marketplace de Delcampe.
2.  **Añadir/Editar productos:** Vaya a **Catálogo > Productos Delcampe**. Use el botón "Añadir nuevo" o edite las entradas existentes para configurar los ajustes específicos de Delcampe para cada producto. Preste mucha atención a los ID de categoría de Delcampe, los precios y el tipo de venta.
3.  **Generar exportación:** Una vez que sus productos estén configurados, el módulo le permitirá generar el archivo de exportación. Este archivo contendrá todos los datos necesarios en un formato que Delcampe Lister puede importar.
4.  **Importar a Delcampe Lister:** Descargue el archivo generado e impórtelo a su herramienta Delcampe Lister.
5.  **Monitorear y actualizar:** Esté atento a sus listados de Delcampe y actualice las configuraciones de productos en PrestaShop según sea necesario (por ejemplo, para cambios de precio, actualizaciones de stock).

#### 2.2.2 AdminDelcampeProductsController (delcampeproducts/controllers/admin/AdminDelcampeProducts.php)

Este controlador es responsable de gestionar los listados de productos de Delcampe dentro del back office de PrestaShop. Maneja la visualización de la lista de productos, así como la creación, edición y eliminación de configuraciones individuales de productos de Delcampe.

#### 2.2.3 index.php (delcampeproducts/controllers/admin/index.php)

Este archivo probablemente sirve como un marcador de posición o una simple redirección dentro de la estructura del controlador de administración, asegurando que la sección de administración del módulo se inicialice o enrute correctamente. Normalmente no contiene opciones de configuración directas para el comerciante.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | MyPresta.eu Live Update Check | SÍ | Controla las comprobaciones automáticas de actualizaciones del módulo. |
| Gestión de productos Delcampe | ID de categoría de Delcampe (`category_id`) | (ID específico de Delcampe) | Mapea el producto de PrestaShop a una categoría de Delcampe. |
| Gestión de productos Delcampe | Título del listado de Delcampe (`title`) | (Personalizado) | Título del producto mostrado en Delcampe. |
| Gestión de productos Delcampe | Descripción del listado de Delcampe (`description`) | (Personalizado) | Descripción detallada del producto para Delcampe. |
| Gestión de productos Delcampe | Su referencia interna (`personal_reference`) | (SKU de PrestaShop) | Seguimiento interno de sus productos. |
| Gestión de productos Delcampe | Moneda del listado (`currency`) | (Su moneda principal) | Moneda para el listado de Delcampe. |
| Gestión de productos Delcampe | Tipo de venta de Delcampe (`selling_type`) | (Precio fijo / Subasta) | Cómo se vende el producto en Delcampe. |
| Gestión de productos Delcampe | Precio inicial / Precio fijo (`price`) | (Su precio deseado) | Precio para venta directa o inicio de subasta. |
| Gestión de productos Delcampe | Cantidad disponible (`initial_quantity`) | (Su nivel de stock) | Número de unidades disponibles en Delcampe. |
| Gestión de productos Delcampe | Incremento de la oferta en subasta (`minimum_bid_step`) | (ej., 0.50, 1.00) | Cantidad mínima en que deben aumentar las ofertas. |
| Gestión de productos Delcampe | Duración de la renovación automática (`renew_duration`) | (ej., 7 días) | Cuánto tiempo se renueva un listado no vendido. |
| Gestión de productos Delcampe | Límite de renovación automática (`renew_total_count`) | (ej., 3, 5) | Número máximo de veces que un listado no vendido se renovará automáticamente. |
| Gestión de productos Delcampe | Modelo de envío de Delcampe (`shipping_model`) | (ID/Nombre del modelo de Delcampe) | Método de envío utilizado en Delcampe. |
| Gestión de productos Delcampe | Peso del producto (`weight`) | (Peso real del producto) | Peso del producto para cálculos de envío. |
| Gestión de productos Delcampe | Hora de finalización de la venta (`lister_sale_end_time`) | (ej., 20:00) | Hora específica del día para el final del listado. |
| Gestión de productos Delcampe | Día de finalización de la venta (`lister_sale_end_day`) | (ej., Domingo) | Día específico de la semana para el final del listado. |
| Gestión de productos Delcampe | Extensión de último minuto (`option_last_minute_extension`) | SÍ (para subastas) | Extiende la subasta si se realiza una oferta en los minutos finales. |
| Gestión de productos Delcampe | Comprador anónimo (`option_anonymous_buyer`) | NO | Oculta la identidad del comprador en las subastas. |
| Gestión de productos Delcampe | Título fuerte / Título en negrita (`option_strong_title`) | SÍ | Pone el título del listado en negrita en Delcampe. |
| Gestión de productos Delcampe | Color de fondo (`option_background_color`) | (Dejar vacío o sutil) | Color de fondo personalizado para el listado. |
| Gestión de productos Delcampe | Color del borde (`option_border_color`) | (Dejar vacío o sutil) | Color de borde personalizado para el listado. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: Mis productos no aparecen en Delcampe después de la exportación. ¿Qué debo verificar?**
R:

1.  **¿Completó la importación en Delcampe Lister?** Este módulo solo *exporta* los datos. Aún necesita descargar el archivo generado e *importarlo* a su herramienta Delcampe Lister.
2.  **Verifique los ID de categoría de Delcampe:** Asegúrese de que el `category_id` que ingresó para cada producto sea correcto y exista en Delcampe. Los ID incorrectos pueden causar fallos en la importación.
3.  **Revise los errores de Delcampe Lister:** Cuando importa el archivo a Delcampe Lister, generalmente proporciona comentarios o mensajes de error si algo salió mal. Revise estos mensajes para obtener pistas.
4.  **Estado del producto:** Asegúrese de que los productos estén activos y en stock en su tienda PrestaShop si ha configurado el módulo para exportar solo artículos activos/en stock.

**P: ¿Cómo manejo las actualizaciones de productos (cambios de precio, cambios de stock) en Delcampe?**
R: Deberá reexportar y reimportar los datos de productos actualizados a Delcampe Lister. El módulo genera un nuevo archivo de exportación basado en los datos actuales de sus productos de PrestaShop y las configuraciones específicas de Delcampe que haya configurado. Delcampe Lister generalmente maneja las actualizaciones de los listados existentes cuando importa un archivo con identificadores de producto coincidentes.

**P: El archivo de exportación parece vacío o incompleto.**
R:

1.  **Configuración del producto:** Verifique que realmente haya configurado productos para la exportación a Delcampe en **Catálogo > Productos Delcampe**. Si no hay productos configurados, la exportación estará vacía.
2.  **Configuración del módulo:** Revise cualquier configuración general del módulo (si está presente) que pueda filtrar productos, como "exportar solo productos activos" o "exportar solo productos en stock".
3.  **Caché de PrestaShop:** A veces, borrar la caché de su PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**) puede resolver comportamientos inesperados con la generación de datos.

**P: Mi tema personalizado está causando problemas de visualización en la configuración del back-office del módulo.**
R: La interfaz del back-office de este módulo utiliza componentes estándar de PrestaShop, por lo que generalmente debería ser compatible. Si encuentra problemas de estilo, es probable que sea un conflicto con las anulaciones del back-office de su tema personalizado.

1.  **Verifique las anulaciones:** Si su tema tiene una carpeta `admin` con anulaciones de plantilla, renómbrela temporalmente para ver si el problema se resuelve.
2.  **Contacte al desarrollador del tema:** Si el problema persiste, contacte al desarrollador de su tema para obtener ayuda, ya que es posible que necesiten ajustar su CSS para adaptarse a las interfaces de módulos estándar.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Exportar productos a Delcampe Lister" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente los Controladores de Administración para su interfaz de back-office y la gestión de datos. No depende en gran medida de los componentes del front-office para la interacción directa con el cliente, pero utiliza hooks para integrarse en el ciclo de vida de PrestaShop. La funcionalidad principal gira en torno a la gestión de la configuración de exportación de Delcampe específica del producto y la generación de un feed de datos para la herramienta Delcampe Lister.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `controllers/front/feed.php`
        -   **Nombre de clase y clase padre**: `DelcampeproductsFeedModuleFrontController` que extiende `ModuleFrontController`.
        -   **Responsabilidad**: Este controlador es probablemente responsable de generar el feed de productos de Delcampe real (por ejemplo, XML, CSV) que el comerciante descargaría. Consultaría los productos configurados y formatearía sus datos de acuerdo con las especificaciones de Delcampe. Responde a una ruta específica del front-office, aunque no es directamente visible para el usuario final que navega por la tienda.
    -   `controllers/front/index.php`
        -   **Nombre de clase y clase padre**: `DelcampeproductsIndexModuleFrontController` que extiende `ModuleFrontController`.
        -   **Responsabilidad**: Esto podría servir como un controlador frontal predeterminado o de respaldo, o podría usarse para una simple redirección. En muchos módulos, si `feed.php` maneja la interacción principal del front-office (generando el feed), `index.php` podría ser mínimo o no utilizado.
-   **Controladores de Administración (Back-Office)**:

    -   `controllers/admin/AdminDelcampeProducts.php`
        -   **Nombre de clase y clase padre**: `AdminDelcampeProductsController` que extiende `ModuleAdminController`.
        -   **Nombre de la pestaña y entidad gestionada**: Este controlador gestiona la sección "Productos Delcampe" en el menú "Catálogo" del Back Office de PrestaShop. Es responsable de listar, añadir, editar y eliminar la configuración específica de Delcampe para cada producto. Utiliza `HelperList` y `HelperForm` de PrestaShop para mostrar la cuadrícula de productos y el formulario de configuración detallado.
    -   `controllers/admin/index.php`
        -   **Nombre de clase y clase padre**: No es una clase de controlador completa, típicamente un archivo `index.php` simple para evitar la lista de directorios o para incluir el archivo principal del módulo para el contexto. No define una clase de controlador de administración distinta.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo indica que no hay clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo podría almacenar su configuración de exportación de productos personalizada directamente en la tabla `ps_configuration` o extender las clases `ObjectModel` existentes de PrestaShop (como `Product`) dinámicamente, o usar una interacción de base de datos más directa dentro del controlador. Dados los campos detallados del formulario, es muy probable que la configuración de Delcampe específica del producto se almacene en `ps_configuration` con claves como `dp_export_categories` o directamente dentro de la lógica de `AdminDelcampeProductsController`.

### 4.4 Activos de JavaScript (`views/js/`)

-   `delcampeproducts/lib/js/admin/delcampeproducts.js`
    -   **Alcance**: Back-office.
    -   **Detalles**: Este script se carga en el Back Office de PrestaShop, específicamente para el controlador `AdminDelcampeProducts`. Probablemente maneja:
        -   Comportamiento dinámico del formulario (por ejemplo, mostrar/ocultar campos según `selling_type`).
        -   Llamadas AJAX para guardar configuraciones o generar el archivo de exportación.
        -   Validación o formato de entrada para campos como `category_id`, `price`, `weight`.
        -   Cualquier elemento interactivo dentro de los formularios de configuración de productos o la cuadrícula de listado.
        -   Potencialmente utiliza jQuery para la manipulación del DOM y el manejo de eventos.

### 4.5 Hojas de estilo CSS (`views/css/`)

El dossier del módulo indica que no hay archivos CSS personalizados. Esto implica que el módulo se basa completamente en el estilo predeterminado del Back Office de PrestaShop para sus formularios y listas de configuración, asegurando una apariencia consistente con el resto del panel de administración. Los desarrolladores que deseen estilizar la interfaz de administración del módulo tendrían que apuntar a las clases CSS existentes de PrestaShop o inyectar CSS personalizado a través del hook `actionAdminControllerSetMedia`.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**: Ninguna listada explícitamente, pero los módulos a menudo usan `displayAdminProductsExtra` o similar para las pestañas de la página de productos.
-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `delcampeproducts/script.tpl`
        -   **Alcance**: Back-office.
        -   **Detalles**: Esta plantilla probablemente se usa para generar variables JavaScript o scripts en línea que son necesarios para `delcampeproducts.js`. Podría pasar valores de configuración de PHP a JavaScript, o definir objetos JS globales. A menudo se renderiza a través del hook `actionAdminControllerSetMedia`.
-   **Plantillas de front-office (`views/templates/front/`)**: Ninguna listada explícitamente, lo que se alinea con la naturaleza de exportación en segundo plano del módulo.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   El módulo probablemente almacena su configuración en la tabla `ps_configuration` utilizando claves como `dp_export_categories`, `dp_remember_settings`, `dp_option_homepage_promotion`, `dp_lister_status`, `dp_lister_creation_date`, `dp_lister_sending_date`, `dp_llister_sending_date`, `dp_lister_edit_date`, `dp_export_format`, `dp_export_active`, `dp_export_instock`, `dp_export_identification`, `dp_export_category`, `dp_export_manufacturers_default`.
    -   Para la configuración de Delcampe específica del producto (como `category_id`, `title`, `price`, etc.), dado que no se lista ningún `ObjectModel` personalizado, es probable que se almacenen como datos serializados dentro de `ps_configuration` (menos ideal para la configuración por producto) o, más probablemente, el `AdminDelcampeProductsController` gestiona directamente una tabla de base de datos personalizada (por ejemplo, `ps_delcampe_product_settings`) que no se identificó explícitamente en el dossier, pero sería un enfoque estándar para datos tan detallados por producto. Si no existe una tabla personalizada, podría estar utilizando `Product::addFeature` o `Product::addCustomization` de una manera no estándar, o almacenando datos en `ps_product_lang` o `ps_product_shop` a través de anulaciones. **(Nota del desarrollador: Investigue la base de datos en busca de `ps_delcampe_product_settings` o una tabla similar al instalar.)**
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionProductUpdate` | Después de que un producto se actualiza en el Back Office. | Permite que el módulo reaccione a los cambios del producto (por ejemplo, actualizar sus datos internos de exportación a Delcampe, marcar un producto para reexportación). |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración y se están configurando sus medios (JS/CSS). | Se utiliza para inyectar el JavaScript personalizado del módulo (`delcampeproducts.js`) y potencialmente scripts en línea (`script.tpl`) en las páginas del Back Office, especialmente para el controlador `AdminDelcampeProducts`. |
| `displayAdminProductsExtra` | (Implícito, a menudo utilizado para pestañas de productos) | Si el módulo añade una pestaña a la página de edición de productos para la configuración de Delcampe, se utilizaría este hook. (No listado explícitamente como hook, pero común para dicha funcionalidad). |
| `displayBackOfficeHeader` | En el encabezado de cada página del Back Office. | Puede usarse para JS/CSS global del lado del administrador o para mostrar notificaciones. |
| `moduleRoutes` | Durante la generación de rutas para el módulo. | Se utiliza para definir URLs personalizadas de front-office para controladores como `feed.php`. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte completo para el módulo "Exportar productos a Delcampe Lister", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte dedicado está disponible para ayudarle con cualquier problema técnico o pregunta relacionada con la funcionalidad del módulo.

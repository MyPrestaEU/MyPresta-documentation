---
title: "Sticky Cart Bar PRO - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Sticky Cart Bar PRO para PrestaShop de MyPresta.eu."
sidebar:
  label: "Sticky Cart Bar PRO - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Sticky Cart Bar PRO en MyPresta.eu](https://mypresta.eu/modules/front-office-features/sticky-cart-bar-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/sticky-cart-bar-pro/)
>
> ---


# Sticky Cart Bar PRO

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

El módulo Sticky Cart Bar PRO ofrece un potente conjunto de opciones de configuración, divididas en varias áreas clave para gestionar sus barras adhesivas y pruebas A/B.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Cuando hace clic por primera vez en "Configurar" en el módulo, aterrizará en un panel de control que proporciona una visión general y acceso a las secciones principales. Esta página actúa como un centro central.

La página de configuración principal de Sticky Cart Bar PRO está estructurada con pestañas o secciones para gestionar diferentes aspectos del módulo.

#### Configuración general / Resumen del panel de control

Esta sección suele presentar un resumen de sus barras activas, pruebas A/B y enlaces rápidos a las pantallas de gestión principales.

-   **Qué hace esta sección:** Proporciona una visión general de alto nivel del estado de su módulo y una navegación rápida para crear nuevas barras, gestionar las existentes o configurar pruebas A/B.
-   **Efecto de cambiar esta configuración:** Esta es principalmente una pantalla de navegación e información. Los cambios aquí implican hacer clic en enlaces a otras pantallas de gestión dedicadas.
-   **Valor recomendado:** Revise este panel de control regularmente para supervisar sus barras adhesivas y experimentos.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

El módulo cuenta con controladores de administración dedicados para gestionar sus barras adhesivas y pruebas A/B, ofreciendo una interfaz completa para el diseño, la segmentación y el análisis.

#### 2.2.1 Gestión de barras de carrito adhesivas (Back Office > Módulos > Sticky Cart Bar PRO > **Gestionar barras**)

Esta pantalla es donde crea, edita y gestiona todas sus barras de carrito adhesivas.

-   **Nombre de la pantalla y ubicación del menú:** Lo encontrará en **Módulos > Sticky Cart Bar PRO > Gestionar barras** (o una entrada de menú similar directamente dentro de la configuración del módulo).
-   **Acciones y configuraciones disponibles:**
    -   **Tabla de listado de barras:** Muestra todas sus barras adhesivas creadas con información clave como el nombre, el estado (activo/inactivo) y los experimentos asignados.
        -   *Efecto:* Proporciona una vista organizada de todas sus barras adhesivas.
        -   *Recomendado:* Mantenga los nombres de las barras descriptivos para una fácil identificación.
    -   **Botón Añadir nueva barra:** Inicia el proceso de creación de una nueva barra adhesiva.
        -   *Efecto:* Abre el "Layout Studio" donde diseña su barra.
        -   *Recomendado:* Comience con un objetivo claro en mente para su nueva barra (por ejemplo, "Barra inferior de página de producto - Envío gratuito").
    -   **Botón Editar (para barras existentes):** Le permite modificar una barra adhesiva existente.
        -   *Efecto:* Vuelve a abrir el Layout Studio con la configuración actual de la barra.
        -   *Recomendado:* Revise y actualice regularmente las barras en función del rendimiento o las promociones.
    -   **Botón Duplicar:** Crea una copia exacta de una barra existente.
        -   *Efecto:* Ahorra tiempo al crear barras similares o variaciones para pruebas A/B.
        -   *Recomendado:* Utilícelo para crear rápidamente una nueva barra basada en un diseño exitoso y luego realice pequeños ajustes.
    -   **Alternar estado (Activo/Inactivo):** Un interruptor para habilitar o deshabilitar una barra sin eliminarla.
        -   *Efecto:* Una barra activa aparecerá en su front office según sus reglas de segmentación; una barra inactiva no lo hará.
        -   *Recomendado:* Deshabilite las barras que sean estacionales o que ya no sean relevantes, en lugar de eliminarlas, en caso de que las necesite de nuevo.
    -   **Botón Eliminar:** Elimina permanentemente una barra adhesiva.
        -   *Efecto:* La barra ya no aparecerá en su tienda.
        -   *Recomendado:* Solo elimine las barras que esté seguro de que nunca volverá a usar.
    -   **Layout Studio (al añadir/editar una barra):** Esta es la interfaz de diseño principal.
        -   **Editor de arrastrar y soltar:** Le permite construir visualmente su barra adhesiva añadiendo y organizando elementos.
            -   *Efecto:* Puede personalizar el diseño, el contenido y la apariencia de su barra sin necesidad de codificación.
            -   *Recomendado:* Experimente con diferentes combinaciones de elementos para encontrar lo que mejor funciona para sus productos y audiencia.
        -   **Opciones de elementos:** Cada elemento (por ejemplo, "Botón Añadir al carrito", "Imagen del producto", "Temporizador de cuenta atrás", "Texto personalizado") tiene su propia configuración de estilo, contenido y comportamiento.
            -   *Efecto:* Ajuste el aspecto y la funcionalidad de cada parte de su barra.
            -   *Recomendado:* Preste atención a los colores, fuentes y tamaños para que coincidan con la marca de su tienda.
        -   **Preajustes:** Elija de una biblioteca de diseños de barras adhesivas prediseñados.
            -   *Efecto:* Empiece rápidamente con una barra de aspecto profesional.
            -   *Recomendado:* Utilice los preajustes como punto de partida y luego personalícelos para que se ajusten a sus necesidades específicas.
        -   **Reglas de segmentación:** Defina *dónde* y *a quién* se debe mostrar la barra adhesiva.
            -   *Efecto:* Asegura que su barra se muestre solo a los clientes relevantes en páginas específicas.
            -   *Recomendado:* Segmente categorías de productos, marcas o grupos de clientes específicos para obtener el máximo impacto. Ejemplos:
                -   *Mostrar en:* Todas las páginas de producto, ID de producto específicos, categorías específicas.
                -   *Grupos de clientes:* Solo clientes registrados, nuevos visitantes, grupos de clientes específicos.
                -   *Ubicación geográfica:* Solo clientes de ciertos países.
                -   *Tipo de dispositivo:* Escritorio, móvil o ambos.
        -   **Posición de visualización:** Elija si la barra aparece en la parte superior o inferior de la pantalla.
            -   *Efecto:* Controla la ubicación visual de la barra adhesiva.
            -   *Recomendado:* Las barras inferiores suelen ser menos intrusivas, mientras que las barras superiores pueden ser más prominentes. ¡Pruebe ambas!
        -   **Configuración de visibilidad:** Controle cuándo aparece la barra (por ejemplo, después de desplazarse una cierta distancia, después de un retraso).
            -   *Efecto:* Evita que la barra aparezca demasiado pronto o demasiado tarde, optimizando la experiencia del usuario.
            -   *Recomendado:* Un ligero retraso o umbral de desplazamiento puede hacer que la barra se sienta menos agresiva.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  **Planificar:** Decida el propósito de su nueva barra adhesiva (por ejemplo, promocionar un producto específico, ofrecer envío gratuito, reducir el abandono del carrito).
    2.  **Crear:** Utilice el botón "Añadir nueva barra" y el Layout Studio para diseñar su barra. Comience con un preajuste si no está seguro.
    3.  **Segmentar:** Configure cuidadosamente las reglas de segmentación para asegurarse de que la barra aparezca para la audiencia correcta en las páginas correctas.
    4.  **Activar:** Establezca la barra en "Activa" una vez que esté satisfecho con su diseño y segmentación.
    5.  **Supervisar:** Utilice el panel de análisis (ver la siguiente sección) para seguir su rendimiento.
    6.  **Optimizar:** Basándose en los análisis, edite la barra para mejorar su efectividad.

#### 2.2.2 Gestión de pruebas A/B (Back Office > Módulos > Sticky Cart Bar PRO > **Pruebas A/B**)

Esta pantalla le permite configurar y gestionar pruebas A/B para sus barras adhesivas, comparando diferentes versiones para ver cuál funciona mejor.

-   **Nombre de la pantalla y ubicación del menú:** Lo encontrará en **Módulos > Sticky Cart Bar PRO > Pruebas A/B**.
-   **Acciones y configuraciones disponibles:**
    -   **Tabla de listado de experimentos:** Muestra todas sus pruebas A/B activas y completadas, incluyendo su estado, fechas de inicio/fin y métricas de rendimiento.
        -   *Efecto:* Proporciona una visión general de sus esfuerzos de prueba.
        -   *Recomendado:* Revise regularmente el estado de sus experimentos.
    -   **Botón Añadir nuevo experimento:** Inicia el proceso de creación de una nueva prueba A/B.
        -   *Efecto:* Le guía a través de la selección de una barra de control y una o más barras variantes.
        -   *Recomendado:* Tenga al menos dos barras adhesivas listas (una de control, una variante) antes de iniciar un experimento.
    -   **Configuración del experimento (al añadir/editar):**
        -   **Nombre:** Un nombre descriptivo para su prueba A/B.
            -   *Efecto:* Le ayuda a identificar el experimento más tarde.
            -   *Recomendado:* Utilice nombres como "Barra inferior de página de producto - Prueba de color de botón" o "Barra superior vs. Barra inferior".
        -   **Barra de control:** La barra adhesiva original o predeterminada con la que desea probar.
            -   *Efecto:* Esta es su línea de base para la comparación.
            -   *Recomendado:* Elija su barra de mejor rendimiento actual o un diseño estándar.
        -   **Barras variantes:** Una o más barras adhesivas alternativas que desea probar.
            -   *Efecto:* Estas son las versiones con cambios que cree que podrían mejorar el rendimiento.
            -   *Recomendado:* Concéntrese en probar un cambio importante por variante (por ejemplo, diferente color de botón, diferente mensaje, diferente posición).
        -   **Distribución del tráfico:** Defina qué porcentaje de su audiencia ve cada barra (control vs. variantes).
            -   *Efecto:* Asegura una comparación justa distribuyendo el tráfico de manera uniforme o según se desee.
            -   *Recomendado:* Comience con una distribución uniforme (por ejemplo, 50/50 para dos barras, 33/33/33 para tres).
        -   **Objetivo:** Defina la métrica que desea optimizar (por ejemplo, clics en "Añadir al carrito", tasa de conversión, ingresos).
            -   *Efecto:* El módulo rastreará esta métrica para cada barra.
            -   *Recomendado:* Elija un objetivo claro y medible directamente relacionado con su objetivo comercial.
        -   **Reglas de segmentación:** Similar a la segmentación de barras, pero para el experimento en sí. Asegura que la prueba A/B se ejecute solo para segmentos específicos.
            -   *Efecto:* Le permite ejecutar experimentos segmentados sin afectar a toda su audiencia.
            -   *Recomendado:* Si prueba una barra para una categoría específica, aplique la misma segmentación al experimento.
    -   **Botón Ver análisis:** Accede a datos de rendimiento detallados para un experimento específico.
        -   *Efecto:* Muestra qué barra funcionó mejor según su objetivo definido.
        -   *Recomendado:* Deje que los experimentos se ejecuten el tiempo suficiente para recopilar datos estadísticamente significativos antes de tomar decisiones.
    -   **Botón Detener experimento:** Finaliza una prueba A/B activa.
        -   *Efecto:* El módulo dejará de mostrar las barras variantes y podrá elegir hacer permanente la barra ganadora.
        *Recomendado:* Detenga un experimento una vez que se identifique un ganador claro o si no está produciendo resultados útiles.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  **Hipótesis:** Identifique un área de mejora (por ejemplo, "Creo que un botón rojo 'Añadir al carrito' funcionará mejor que uno verde").
    2.  **Crear variantes:** Duplique su barra adhesiva existente y realice el cambio específico que desea probar (por ejemplo, cambie el color del botón).
    3.  **Configurar experimento:** Vaya a la pantalla de Pruebas A/B, haga clic en "Añadir nuevo experimento" y configure su control, variantes, tráfico y objetivo.
    4.  **Lanzar y supervisar:** Inicie el experimento y revise regularmente el panel de análisis para ver el progreso.
    5.  **Analizar e implementar:** Una vez que el experimento concluya o surja un ganador claro, implemente la barra ganadora como su predeterminada.

#### 2.2.3 Panel de análisis (Back Office > Módulos > Sticky Cart Bar PRO > **Análisis**)

Esta pantalla proporciona métricas de rendimiento detalladas para sus barras adhesivas y pruebas A/B.

-   **Nombre de la pantalla y ubicación del menú:** Lo encontrará en **Módulos > Sticky Cart Bar PRO > Análisis**.
-   **Acciones y configuraciones disponibles:**
    -   **Vista del panel de control:** Muestra gráficos que muestran métricas clave como impresiones, clics, tasas de clics (CTR) y conversiones para sus barras adhesivas.
        -   *Efecto:* Le brinda una representación visual clara de cómo se están desempeñando sus barras.
        -   *Recomendado:* Utilice estos datos para comprender qué barras son efectivas y cuáles necesitan mejorar.
    -   **Opciones de filtro:** Filtre los datos por rango de fechas, barra adhesiva específica o experimento.
        -   *Efecto:* Le permite profundizar en períodos específicos o comparar el rendimiento de barras individuales.
        -   *Recomendado:* Compare el rendimiento antes y después de un cambio importante o promoción.
    -   **Resultados de pruebas A/B:** Para experimentos activos o completados, esta sección mostrará claramente qué variante está funcionando mejor en comparación con el control, a menudo con indicadores de significación estadística.
        -   *Efecto:* Proporciona la evidencia necesaria para tomar decisiones basadas en datos sobre los diseños de su barra adhesiva.
        -   *Recomendado:* No tome decisiones basadas en tamaños de muestra pequeños; espere la significación estadística.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  **Revisión regular:** Revise el panel de análisis semanal o mensualmente para comprender las tendencias generales de rendimiento.
    2.  **Análisis profundo:** Si una barra tiene un rendimiento inferior, utilice los filtros para investigar períodos específicos o compararla con otras barras.
    3.  **Toma de decisiones:** Utilice los resultados de las pruebas A/B para elegir con confianza los diseños ganadores e implementarlos en su tienda.

#### 2.2.4 AdminStickyCartBarAbController (stickycartbarpro/controllers/admin/AdminStickyCartBarAbController.php)

Este controlador gestiona los experimentos de pruebas A/B. Maneja la creación, edición, listado y eliminación de entidades `stickycartbar_experiment`.

#### 2.2.5 AdminStickyCartBarProController (stickycartbarpro/controllers/admin/AdminStickyCartBarProController.php)

Este controlador gestiona las barras de carrito adhesivas individuales. Maneja la creación, edición, listado y eliminación de entidades `stickycartbar_bar`, incluyendo el acceso al Layout Studio para el diseño.

#### 2.2.6 index.php (stickycartbarpro/controllers/admin/index.php)

Este es un archivo de marcador de posición, típicamente utilizado para evitar la lista directa de directorios y no representa una pantalla configurable en sí mismo.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Gestionar barras** | Nombre de la barra | Descriptivo | Identifica la barra en el back office. |
| | Layout Studio | N/A | Editor de arrastrar y soltar para el contenido y estilo de la barra. |
| | Opciones de elementos | Varía | Personaliza elementos individuales (botones, texto, imágenes). |
| | Preajustes | N/A | Plantillas de inicio rápido para el diseño de la barra. |
| | Reglas de segmentación | Todas las páginas de producto | Define dónde y a quién se muestra la barra. |
| | Posición de visualización | Abajo | Controla si la barra está en la parte superior o inferior de la pantalla. |
| | Configuración de visibilidad | Después de desplazarse | Controla cuándo aparece la barra (retraso, desplazamiento). |
| | Estado (Activo/Inactivo) | Inactivo (inicialmente) | Habilita/deshabilita la visualización de la barra en el front office. |
| **Pruebas A/B** | Nombre del experimento | Descriptivo | Identifica la prueba A/B. |
| | Barra de control | Barra existente | La barra de referencia para la comparación. |
| | Barras variantes | Barra(s) nueva(s)/modificada(s) | Las versiones alternativas que se están probando. |
| | Distribución del tráfico | Dividido equitativamente | Cómo se divide la audiencia entre las barras. |
| | Objetivo | Clics en Añadir al carrito | La métrica a optimizar (por ejemplo, clics, conversiones). |
| | Reglas de segmentación | Todas las páginas de producto | Define dónde se ejecuta el experimento. |
| | Estado (Activo/Detenido) | Activo | Controla si el experimento se está ejecutando. |
| **Análisis** | Filtro de rango de fechas | Últimos 30 días | Filtra los datos de rendimiento por tiempo. |
| | Filtro de barra/experimento | Todos | Filtra los datos para barras o pruebas específicas. |
| | Visualización de métricas | Impresiones, Clics, CTR | Muestra datos de rendimiento para barras/experimentos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mi barra adhesiva no aparece en mis páginas de producto. ¿Qué debo comprobar?**
**R1:**

-   **¿Está la barra "Activa"?** Vaya a **Módulos > Sticky Cart Bar PRO > Gestionar barras** y asegúrese de que el interruptor de su barra esté configurado en "Activo".
-   **Compruebe las reglas de segmentación:** Edite su barra y revise las "Reglas de segmentación". Asegúrese de que esté configurada para mostrarse en las páginas correctas (por ejemplo, "Todas las páginas de producto" o categorías/productos específicos) y para los grupos de clientes correctos.
-   **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, la caché de PrestaShop impide que los nuevos cambios del módulo aparezcan inmediatamente.
-   **Posición del módulo:** Asegúrese de que el módulo esté enganchado correctamente. Aunque el módulo suele encargarse de esto, si lo ha desenganchado manualmente, no aparecerá. Compruebe **Diseño > Posiciones** y busque "Sticky Cart Bar PRO" para asegurarse de que esté enganchado a `displayHeader` o `displayFooter` (dependiendo de la posición de su barra).

**P2: La barra adhesiva se ve extraña o no coincide con el diseño de mi tema.**
**R2:**

-   **Estilo del Layout Studio:** Vaya a **Módulos > Sticky Cart Bar PRO > Gestionar barras**, edite su barra y utilice las opciones de estilo del Layout Studio. Puede personalizar colores, fuentes, tamaños, rellenos y más para cada elemento y la propia barra.
-   **Conflictos de tema:** A veces, el CSS de su tema personalizado puede anular el estilo del módulo. Si las opciones básicas de estilo en el Layout Studio no lo solucionan, es posible que necesite que un webmaster inspeccione el CSS (consulte la sección de Desarrolladores).
-   **Compatibilidad del módulo:** Asegúrese de haber descargado la versión correcta del módulo para su versión de PrestaShop.

**P3: ¿Cómo puedo traducir el texto de mi barra adhesiva a otros idiomas?**
**R3:**

-   **Traducciones del módulo:** Para textos estáticos dentro del módulo (como etiquetas de botones si no están personalizadas), vaya a **Internacional > Traducciones**. Seleccione "Traducciones de módulos instalados", elija su tema, seleccione "Sticky Cart Bar PRO" y luego el idioma al que desea traducir.
-   **Elementos de texto personalizados:** Si ha añadido elementos de texto personalizados utilizando el Layout Studio, deberá editar la barra para cada idioma. Al editar la barra, debería ver una opción para cambiar de idioma para las entradas de texto, lo que le permite introducir traducciones directamente dentro del Layout Studio.

**P4: Mi prueba A/B no muestra resultados claros o parece atascada.**
**R4:**

-   **Duración y tráfico:** Las pruebas A/B necesitan suficiente tiempo y tráfico para recopilar datos estadísticamente significativos. Asegúrese de que su experimento se haya ejecutado el tiempo suficiente (al menos unas pocas semanas) y haya recibido suficientes visitantes para sacar conclusiones.
-   **Objetivo claro:** Verifique que su prueba A/B tenga un "Objetivo" claramente definido (por ejemplo, clics en "Añadir al carrito"). Sin un objetivo, el módulo no puede medir el éxito.
-   **Sin cambios importantes en la tienda:** Evite realizar cambios significativos en su tienda (por ejemplo, nuevo tema, promociones importantes) mientras se ejecuta una prueba A/B, ya que esto puede sesgar los resultados.

**P5: ¿Puedo tener varias barras adhesivas activas al mismo tiempo?**
**R5:** Sí, puede crear y activar varias barras adhesivas. Sin embargo, debe configurar cuidadosamente sus **Reglas de segmentación** para evitar conflictos. Por ejemplo, podría tener una barra para "Todas las páginas de producto" en la parte inferior, y otra barra específica para "Productos de la Categoría X" en la parte superior. El módulo priorizará las barras en función de su especificidad y lógica interna, pero es una buena práctica asegurarse de que sus reglas de segmentación no se superpongan de manera que dos barras intenten mostrarse en la misma posición en la misma página.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo Sticky Cart Bar PRO sigue una sólida arquitectura MVC (Modelo-Vista-Controlador) de PrestaShop, aprovechando en gran medida `ObjectModel` para la persistencia de datos y `ModuleFrontController`/`AdminController` para el manejo de solicitudes. Emplea un sistema sofisticado para la construcción de diseños, pruebas A/B y análisis, con clases dedicadas para la configuración, el estilo, la segmentación y la resolución de experimentos. El módulo utiliza un enfoque modular, separando las preocupaciones en clases distintas para una mejor mantenibilidad y extensibilidad. La renderización del front-office se basa principalmente en hooks, con AJAX para interacciones dinámicas.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

-   `controllers/front/ajax.php`
    -   **Nombre de la clase:** `StickyCartBarProAjaxModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Maneja todas las solicitudes AJAX desde la barra adhesiva del front-office. Esto incluye:
        -   Seguimiento de impresiones y clics para análisis.
        -   Actualización dinámica de la información del carrito (por ejemplo, añadir productos, cambiar cantidades).
        -   Resolución de qué variante de barra adhesiva mostrar para las pruebas A/B.
        -   Obtención de datos de productos para selectores de variantes o sugerencias de venta cruzada.
        -   Devuelve respuestas JSON.
-   `controllers/front/index.php`
    -   **Nombre de la clase:** `StickyCartBarProIndexModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Un controlador frontal de marcador de posición. Típicamente, podría usarse para una página de módulo predeterminada, pero en este módulo, la renderización del front-office se maneja principalmente a través de hooks y AJAX. Podría servir como un respaldo o una base para futuras características.

#### Controladores de administración de Back-Office

-   `controllers/admin/AdminStickyCartBarAbController.php`
    -   **Nombre de la clase:** `AdminStickyCartBarAbController` (extiende `AdminController`)
    -   **Nombre de la pestaña:** Pruebas A/B (dentro del menú principal del módulo)
    -   **Entidad gestionada:** `StickyCartBarExperiment` (mapeada a la tabla `ps_stickycartbar_experiment`).
    -   **Responsabilidad:** Gestiona las operaciones CRUD para los experimentos de pruebas A/B. Esto incluye:
        -   Listar todos los experimentos en un `HelperList`.
        -   Proporcionar un `HelperForm` para crear y editar detalles del experimento (nombre, barra de control, barras variantes, distribución del tráfico, objetivo, reglas de segmentación).
        -   Manejar la activación/desactivación del experimento y la visualización de resultados.
-   `controllers/admin/AdminStickyCartBarProController.php`
    -   **Nombre de la clase:** `AdminStickyCartBarProController` (extiende `AdminController`)
    -   **Nombre de la pestaña:** Gestionar barras (dentro del menú principal del módulo)
    -   **Entidad gestionada:** `StickyCartBarLayout` (mapeada a la tabla `ps_stickycartbar_bar`).
    -   **Responsabilidad:** Gestiona las operaciones CRUD para las barras de carrito adhesivas individuales. Este controlador se integra con el "Layout Studio" para el diseño visual.
        -   Listar todas las barras adhesivas en un `HelperList`.
        -   Proporcionar la interfaz para el Layout Studio de arrastrar y soltar, incluyendo la configuración de elementos, el estilo y las reglas de segmentación.
        -   Maneja el guardado y la carga de configuraciones de barras, incluyendo la estructura HTML, CSS y la configuración de JavaScript.
-   `controllers/admin/index.php`
    -   **Nombre de la clase:** N/A (archivo de marcador de posición)
    -   **Responsabilidad:** Evita la lista directa de directorios por seguridad.

### 4.3 Clases y modelos principales (`classes/`)

-   `classes/index.php`: Archivo de marcador de posición para evitar la lista de directorios.
-   `classes/ScbpCompatibility.php`: Maneja las capas de compatibilidad para diferentes versiones de PrestaShop (por ejemplo, diferencias de `Context`, métodos de ayuda específicos).
-   `classes/StickyCartBarAdminUi.php`: Clase de utilidad para generar elementos de UI comunes o manejar lógica de UI específica dentro del panel de administración.
-   `classes/StickyCartBarAnalytics.php`: Gestiona la recopilación, almacenamiento y recuperación de datos analíticos para barras adhesivas y pruebas A/B (impresiones, clics, conversiones).
-   `classes/StickyCartBarConfig.php`: Maneja la configuración específica del módulo almacenada en `ps_configuration` (por ejemplo, habilitar/deshabilitar el módulo global, configuración predeterminada).
-   `classes/StickyCartBarElementStyles.php`: Gestiona las propiedades de estilo y la generación de CSS para elementos individuales dentro de una barra adhesiva.
-   `classes/StickyCartBarExperiment.php`
    -   **Extiende:** `ObjectModel`
    -   **Tabla de base de datos:** `ps_stickycartbar_experiment`
    -   **Campos `$definition`:** `id_stickycartbar_experiment`, `name`, `id_control_bar`, `id_variant_bars` (JSON), `traffic_distribution` (JSON), `goal`, `targeting_rules` (JSON), `active`, `date_add`, `date_upd`.
    -   **Métodos públicos clave:** Operaciones CRUD, métodos para recuperar barras de control/variantes, calcular resultados de experimentos.
-   `classes/StickyCartBarExperimentMatcher.php`: Determina si las reglas de segmentación de un experimento dado coinciden con el contexto actual (cliente, página, dispositivo).
-   `classes/StickyCartBarExperimentResolver.php`: Dada un conjunto de experimentos activos, determina qué barra adhesiva (control o variante) debe mostrarse al visitante actual en función de la distribución del tráfico y las reglas del experimento.
-   `classes/StickyCartBarExperimentRule.php`: Representa una única regla de segmentación dentro de un experimento.
-   `classes/StickyCartBarExperimentVariant.php`: Representa una barra adhesiva variante dentro de una prueba A/B.
-   `classes/StickyCartBarLayout.php`
    -   **Extiende:** `ObjectModel`
    -   **Tabla de base de datos:** `ps_stickycartbar_bar`
    -   **Campos `$definition`:** `id_stickycartbar_bar`, `name`, `content` (JSON para elementos, estilos, configuración), `targeting_rules` (JSON), `position`, `active`, `date_add`, `date_upd`.
    -   **Métodos públicos clave:** Operaciones CRUD, métodos para renderizar la barra, recuperar sus elementos, aplicar estilos.
-   `classes/StickyCartBarLayoutInstances.php`: Gestiona las instancias de diseños de barras adhesivas, potencialmente para el almacenamiento en caché o el acceso en tiempo de ejecución.
-   `classes/StickyCartBarLayoutPreset.php`: Representa un único diseño de barra adhesiva prediseñado.
-   `classes/StickyCartBarLayoutPresets.php`: Gestiona la colección de preajustes de diseño disponibles.
-   `classes/StickyCartBarLayoutPresetsBuiltin.php`: Contiene las definiciones de los preajustes de diseño predeterminados y integrados del módulo.
-   `classes/StickyCartBarListPresenter.php`: Clase de ayuda para formatear y presentar datos en listas de administración (por ejemplo, `HelperList`).
-   `classes/StickyCartBarMatcher.php`: Determina si las reglas de segmentación de una barra adhesiva (para una barra que no es de experimento) coinciden con el contexto actual.
-   `classes/StickyCartBarRule.php`: Representa una única regla de segmentación para una barra adhesiva.
-   `classes/StickyCartBarTargeting.php`: Clase central para evaluar todas las reglas de segmentación (tanto para barras como para experimentos) contra el contexto actual del front-office.

### 4.4 Activos de JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`: Proporciona funcionalidad de autocompletado, probablemente utilizada en la administración para seleccionar productos, categorías o fabricantes para las reglas de segmentación.
-   `views/js/admin-ab-dashboard.js`: Maneja elementos interactivos y visualización de datos en el panel de pruebas A/B en el back office.
-   `views/js/admin-analytics-dashboard.js`: Gestiona gráficos, filtros y visualización de datos en el panel de análisis.
-   `views/js/admin-audience-picker.js`: Impulsa la interfaz interactiva para definir reglas de segmentación de audiencia (por ejemplo, seleccionar grupos de clientes, países).
-   `views/js/admin-element-editor.js`: Proporciona la lógica JavaScript para editar elementos individuales dentro del Layout Studio (por ejemplo, abrir modal para entrada de texto, selectores de color).
-   `views/js/admin-layout-builder.js`: El JavaScript principal para el Layout Studio de arrastrar y soltar, que maneja la colocación, el redimensionamiento y la interacción de los elementos.
-   `views/js/admin-layout-preview.js`: Gestiona la vista previa en tiempo real de la barra adhesiva dentro del Layout Studio.
-   `views/js/admin-layout-studio.js`: Orquesta todos los componentes del Layout Studio, combinando las funcionalidades de constructor, editor y vista previa.
-   `views/js/admin.js`: JavaScript de propósito general para las páginas del back-office del módulo, incluyendo oyentes de eventos globales, envíos de formularios y llamadas AJAX.
-   `views/js/front.js`: El JavaScript principal del front-office para la barra adhesiva.
    -   **Alcance:** Front-office.
    -   **Oyentes de eventos:** Desplazamientos (para detectar cuándo mostrar/ocultar la barra), clics en botones "Añadir al carrito" dentro de la barra, clics en selectores de variantes, envíos de formularios.
    -   **Manipulación del DOM:** Inserta el HTML de la barra adhesiva en el DOM, actualiza las cantidades del carrito, cambia las variantes del producto, muestra/oculta elementos (por ejemplo, temporizadores FOMO).
    -   **Llamadas AJAX:** Se comunica con `controllers/front/ajax.php` para rastrear eventos, actualizar el carrito y obtener contenido dinámico.
    -   **SDKs de terceros:** Ninguno explícitamente listado, pero podría integrarse potencialmente con plataformas de análisis si se configura.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`: Estilos para la herramienta de búsqueda de autocompletado en la administración.
-   `views/css/admin-audience-picker.css`: Estilos para la interfaz de segmentación de audiencia en la administración.
-   `views/css/admin-bars-list.css`: Estilos para la lista de barras adhesivas en la administración.
-   `views/css/admin-config.css`: Estilos generales para la página de configuración principal del módulo.
-   `views/css/admin-dashboard.css`: Estilos para el panel de control principal del módulo y, potencialmente, para las vistas generales de análisis/pruebas A/B.
-   `views/css/admin-element-editor.css`: Estilos para los modales/paneles de edición de elementos dentro del Layout Studio.
-   `views/css/admin-layout-builder.css`: Estilos principales para la interfaz del constructor de diseño de arrastrar y soltar.
-   `views/css/admin-layout-preview.css`: Estilos para el área de vista previa en tiempo real en el Layout Studio.
-   `views/css/admin-layout-studio.css`: Estilos generales para el Layout Studio, combinando todos sus componentes.
-   `views/css/admin-searchtool.css`: Estilos específicos para la herramienta de búsqueda utilizada en la administración.
-   `views/css/front-classic.css`: Estilos específicos del front-office para el tema "Classic" de PrestaShop.
    -   **Componentes principales de la UI:** Anula o añade estilos para asegurar que la barra adhesiva se integre bien con los elementos predeterminados del tema Classic.
    -   **Selectores de clase CSS clave:** `.scbp-bar`, `.scbp-button`, `.scbp-product-info`, etc., potencialmente con anulaciones específicas del tema.
-   `views/css/front-hummingbird.css`: Estilos específicos del front-office para el tema "Hummingbird" de PrestaShop (PrestaShop 8.1+).
    -   **Componentes principales de la UI:** Similar a `front-classic.css` pero adaptado a la estructura y el diseño del tema Hummingbird.
    -   **Selectores de clase CSS clave:** `.scbp-bar`, `.scbp-button`, etc., con ajustes específicos de Hummingbird.
-   `views/css/front.css`: Estilos generales del front-office para la barra adhesiva, aplicados a todos los temas.
    -   **Componentes principales de la UI:** Estilo base para el contenedor de la barra adhesiva, sus elementos (botones, texto, imágenes, temporizadores) y posicionamiento (fijo superior/inferior).
    -   **Selectores de clase CSS clave:** `.scbp-bar`, `.scbp-element`, `.scbp-add-to-cart`, `.scbp-product-name`, `.scbp-price`, `.scbp-quantity-selector`, `.scbp-countdown`, `.scbp-stock-indicator`. Los desarrolladores pueden anular estas clases en el CSS personalizado de su tema.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

-   `sticky-cart-bar-classic.tpl`: Renderiza la barra adhesiva específicamente para el tema Classic. Esta plantilla probablemente incluye una estructura HTML o nombres de clase específicos del tema para asegurar una integración perfecta.
    -   **Hook:** `displayHeader` o `displayFooter` (dependiendo de la posición de la barra y la lógica interna del módulo).
    -   **Salida:** La estructura HTML principal para la barra adhesiva, incluyendo marcadores de posición para contenido dinámico.
-   `sticky-cart-bar-element-inner.tpl`: Renderiza el contenido interno de un solo elemento dentro de la barra adhesiva. Este es un parcial reutilizable.
    -   **Hook:** N/A (incluido por otras plantillas).
    -   **Salida:** HTML para un tipo de elemento específico (por ejemplo, nombre del producto, precio, entrada de cantidad).
-   `sticky-cart-bar-element.tpl`: Renderiza un solo elemento (por ejemplo, botón, imagen, bloque de texto) de la barra adhesiva, envolviendo `sticky-cart-bar-element-inner.tpl` con envoltorios de elementos comunes.
    -   **Hook:** N/A (incluido por otras plantillas).
    -   **Salida:** HTML para un componente de barra adhesiva único y con estilo.
-   `sticky-cart-bar-hummingbird.tpl`: Renderiza la barra adhesiva específicamente para el tema Hummingbird. Similar a `sticky-cart-bar-classic.tpl` pero adaptado para el tema más nuevo.
    -   **Hook:** `displayHeader` o `displayFooter`.
    -   **Salida:** La estructura HTML principal para la barra adhesiva, optimizada para Hummingbird.
-   `sticky-cart-bar-inner.tpl`: Renderiza el contenido interno de toda la barra adhesiva, conteniendo todos los elementos individuales.
    -   **Hook:** N/A (incluido por `sticky-cart-bar.tpl`).
    -   **Salida:** El HTML combinado de todos los elementos configurados para una barra adhesiva.
-   `sticky-cart-bar.tpl`: La plantilla principal responsable de renderizar la barra de carrito adhesiva en el front office. Determina qué plantilla específica del tema (classic/hummingbird) incluir o utiliza una estructura genérica.
    -   **Hook:** `displayHeader` o `displayFooter` (el módulo se registra en estos hooks).
    -   **Salida:** La barra de carrito adhesiva completa y renderizada, incluyendo su contenedor, elementos y atributos de datos necesarios para JavaScript.

#### Plantillas de administración (`views/templates/admin/`)

-   `ab-test-dashboard.tpl`: Renderiza el panel principal para las pruebas A/B, mostrando listas de experimentos y datos de resumen.
-   `ab-tests-tab.tpl`: Renderiza el contenido para la pestaña "Pruebas A/B" dentro de la configuración del módulo.
-   `analytics-dashboard.tpl`: Renderiza el panel de análisis con gráficos y métricas de rendimiento.
-   `audience-picker.tpl`: Renderiza el HTML para la interfaz de selección de segmentación de audiencia (por ejemplo, selectores de país, grupo de clientes).
-   `bars-tab.tpl`: Renderiza el contenido para la pestaña "Gestionar barras", incluyendo la lista de barras adhesivas.
-   `configure.tpl`: La plantilla de configuración principal para el módulo, actuando como el envoltorio para todas las demás plantillas y pestañas de administración.
-   `country-priority-picker.tpl`: Renderiza un componente de UI específico para seleccionar y priorizar países en las reglas de segmentación.

### 4.7 Esquema de la base de datos y mapa de Hooks

#### Tablas de la base de datos

-   `ps_stickycartbar_bar`: Almacena la configuración de cada barra de carrito adhesiva individual.
    -   `id_stickycartbar_bar` (PK, INT)
    -   `name` (VARCHAR)
    -   `content` (TEXT, codificado en JSON: contiene elementos, estilos, posición, configuración de visibilidad)
    -   `targeting_rules` (TEXT, codificado en JSON: condiciones de visualización)
    -   `active` (TINYINT)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_stickycartbar_experiment`: Almacena la configuración de cada experimento de prueba A/B.
    -   `id_stickycartbar_experiment` (PK, INT)
    -   `name` (VARCHAR)
    -   `id_control_bar` (INT, FK a `ps_stickycartbar_bar`)
    -   `id_variant_bars` (TEXT, array codificado en JSON de FKs a `ps_stickycartbar_bar`)
    -   `traffic_distribution` (TEXT, codificado en JSON: porcentaje para cada barra)
    -   `goal` (VARCHAR: por ejemplo, 'add\_to\_cart', 'conversion')
    -   `targeting_rules` (TEXT, codificado en JSON)
    -   `active` (TINYINT)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_stickycartbar_analytics`: Almacena datos analíticos (impresiones, clics, conversiones) para barras y experimentos.
    -   `id_stickycartbar_analytics` (PK, INT)
    -   `id_stickycartbar_bar` (INT, FK)
    -   `id_stickycartbar_experiment` (INT, FK, NULLABLE)
    -   `type` (VARCHAR: 'impression', 'click', 'add\_to\_cart', 'conversion')
    -   `id_customer` (INT, NULLABLE)
    -   `id_guest` (INT, NULLABLE)
    -   `date_add` (DATETIME)
-   **`ps_configuration`**: Almacena la configuración global del módulo (por ejemplo, `STICKYCARTBARPRO_ENABLED`, `STICKYCARTBARPRO_ANALYTICS_ENABLED`).

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyecta archivos CSS y JavaScript para la barra adhesiva, y potencialmente la estructura HTML inicial si la barra se posiciona en la parte superior. |
| `displayFooter` | Antes de la etiqueta de cierre `</body>` en cada página. | Inyecta la estructura HTML para las barras adhesivas posicionadas en la parte inferior, y cualquier inicialización JavaScript necesaria. |
| `actionFrontControllerSetMedia` | Después de que un controlador frontal haya establecido sus activos multimedia. | Permite que el módulo añada condicionalmente su JS/CSS en función del contexto de la página actual (por ejemplo, solo en páginas de producto). |
| `actionProductUpdate` | Después de que un producto se actualice en el back office. | Potencialmente utilizado para borrar la caché relacionada con los datos del producto que podrían mostrarse en las barras adhesivas. |
| `actionObjectProductAddAfter` | Después de que se añade un nuevo producto. | Similar a `actionProductUpdate`. |
| `actionObjectProductUpdateAfter` | Después de que se actualiza un producto existente. | Similar a `actionProductUpdate`. |
| `actionObjectProductDeleteAfter` | Después de que se elimina un producto. | Potencialmente utilizado para limpiar cualquier referencia al producto eliminado en las configuraciones de la barra adhesiva. |
| `actionCartSave` | Después de que un carrito se guarda o actualiza. | Se utiliza para rastrear eventos de "Añadir al carrito" para análisis y objetivos de pruebas A/B. |
| `actionValidateOrder` | Después de que un pedido se valida correctamente. | Se utiliza para rastrear eventos de conversión para análisis y objetivos de pruebas A/B. |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página del back-office. | Inyecta CSS y JavaScript para las interfaces de administración del módulo (Layout Studio, paneles de control). |
| `moduleRoutes` | Durante la inicialización del enrutamiento de URL. | Registra rutas personalizadas del front-office para controladores AJAX si es necesario. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo Sticky Cart Bar PRO, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con la funcionalidad y compatibilidad del módulo.

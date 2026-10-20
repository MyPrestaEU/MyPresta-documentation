---
title: "Redirecciones SEO 301, 302, 303 - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Redirecciones SEO 301, 302, 303 de MyPresta.eu."
sidebar:
  label: "Redirecciones SEO 301, 302, 303 - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Seo Redirects 301, 302, 303 en MyPresta.eu](https://mypresta.eu/modules/seo/seo-redirects-301-302-303.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/seo/seo-redirects-301-302-303/)
>
> ---


# Redirecciones SEO 301, 302, 303

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

El módulo "Redirecciones SEO 301, 302, 303" proporciona un conjunto completo de herramientas, accesibles a través de un menú dedicado en su Back Office de PrestaShop. Después de la instalación, encontrará un nuevo elemento de menú, típicamente bajo **"SEO y SEM"** o **"Parámetros Avanzados"**, llamado **"Redirecciones SEO"** o similar. Este menú contendrá varios subelementos, cada uno de los cuales conducirá a una pantalla de configuración específica.

### 2.1 Página de Configuración Principal del Módulo (Back Office > Módulos > Configurar)

Esta pantalla de configuración inicial (a la que se accede haciendo clic en "Configurar" después de la instalación) proporciona ajustes generales para el módulo.

- **Qué hace este ajuste:** Esta pantalla suele contener la activación básica del módulo y quizás algunos ajustes globales.
- **Efecto de cambiar este ajuste:**
  - *Habilitar el módulo:* Activa la lógica de redirección en toda su tienda.
  - *Deshabilitar el módulo:* Detiene todas las redirecciones gestionadas por este módulo.
- **Valor recomendado:** **Habilitado** para que el módulo funcione.
- **Escenario / ejemplo de comerciante:** Después de la instalación, querrá asegurarse de que el módulo esté activo para que pueda comenzar a gestionar sus redirecciones.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

El módulo organiza sus potentes características en varias secciones distintas, cada una gestionada por un controlador de administración dedicado. Las encontrará bajo el elemento de menú principal "Redirecciones SEO" en su Back Office de PrestaShop.

#### 2.2.1 Panel de Control (AdminSeoRedirectDashboardController)

**Nombre de la Pantalla y Ubicación del Menú:** **Redirecciones SEO > Panel de Control**
Esta pantalla proporciona una visión general del rendimiento y el estado de sus redirecciones. Es su centro central para comprender rápidamente cómo funcionan sus redirecciones.

- **Acciones y Ajustes Disponibles:**
  - **Visión General de Redirecciones:** Muestra estadísticas como el número total de redirecciones activas, redirecciones creadas y quizás el número de veces que se han activado las redirecciones.
  - **Historial/Actividad de Redirecciones:** Puede mostrar intentos de redirección recientes, incluidos errores 404 detectados y URLs redirigidas con éxito.
  - **SEOR\_DASHBOARD\_PERIOD:** Este ajuste probablemente controla el período de tiempo para el cual se muestran las estadísticas del panel de control (por ejemplo, últimos 7 días, últimos 30 días, todo el tiempo).
- **Efecto de los cambios:** Cambiar el período del panel de control actualizará las estadísticas mostradas para reflejar el marco de tiempo seleccionado, ayudándole a analizar tendencias durante diferentes duraciones.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise este panel de control regularmente para monitorear la salud de sus redirecciones, identificar cualquier nuevo error 404 que necesite atención y asegurarse de que sus esfuerzos de SEO estén dando sus frutos.

#### 2.2.2 Lista de Redirecciones (AdminSeoRedirectListController)

**Nombre de la Pantalla y Ubicación del Menú:** **Redirecciones SEO > Lista de Redirecciones**
Este es el núcleo del módulo, donde se crean, editan y gestionan las reglas de redirección individuales.

- **Acciones y Ajustes Disponibles:**
  - **Añadir Nueva Redirección:** Un formulario para crear una nueva regla de redirección.
    - **URL Antigua (URL de Origen):** La URL exacta que ya no es válida o desde la que desea redirigir.
    - **URL Nueva (URL de Destino):** La URL exacta a la que deben ser enviados los visitantes y los motores de búsqueda.
    - **Tipo de Redirección:**
      - **301 Redirección Permanente:** Indica a los motores de búsqueda que la página se ha movido permanentemente. Este es el tipo más común y amigable para el SEO, transmitiendo casi todo el "link juice". Úselo cuando una página ha desaparecido para siempre y ha sido reemplazada por otra.
      - **302 Encontrado / Redirección Temporal:** Indica a los motores de búsqueda que el movimiento es temporal. Úselo si espera que la URL antigua vuelva a estar activa en el futuro (por ejemplo, para productos de temporada, pruebas A/B). Se transmite menos valor SEO.
      - **303 Ver Otro:** Similar a 302, a menudo utilizado después de una solicitud POST para redirigir a una nueva página y evitar el reenvío. Menos común para redirecciones SEO generales.
    - **Estado (Habilitado/Deshabilitado):** Le permite activar o desactivar una regla de redirección específica sin eliminarla.
  - **Editar/Eliminar Redirecciones:** Modificar reglas existentes o eliminarlas.
  - **Buscar/Filtrar:** Encontrar redirecciones específicas por URL antigua o nueva.
  - **Acciones Masivas:** Aplicar acciones (habilitar, deshabilitar, eliminar) a múltiples redirecciones seleccionadas.
- **Efecto de los cambios:**
  - *Añadir una redirección:* Comienza inmediatamente a redirigir el tráfico de la URL antigua a la nueva según el tipo especificado.
  - *Editar una redirección:* Actualiza el comportamiento de la redirección.
  - *Eliminar una redirección:* Elimina la regla, lo que podría provocar errores 404 si la URL antigua sigue siendo accedida.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Siempre que elimine un producto, cambie la URL de una categoría o actualice la dirección de una página, cree inmediatamente una redirección 301 de la URL antigua a la nueva.
  2. Revise regularmente sus registros de errores 404 (por ejemplo, en Google Search Console o en la sección de Auditoría del módulo) y añada redirecciones para los enlaces rotos que se encuentren con frecuencia.

#### 2.2.3 Importar Redirecciones (AdminSeoRedirectImportController)

**Nombre de la Pantalla y Ubicación del Menú:** **Redirecciones SEO > Importar**
Esta pantalla le permite subir un archivo (típicamente CSV) que contiene muchas reglas de redirección, lo que facilita la gestión de un gran número de redirecciones.

- **Acciones y Ajustes Disponibles:**
  - **Subir Archivo CSV:** Seleccione un archivo de su ordenador. El archivo debe contener columnas para "URL Antigua", "URL Nueva" y "Tipo de Redirección".
  - **IV\_COL\_DELIMITER:** Este ajuste define el carácter utilizado para separar las columnas en su archivo CSV (por ejemplo, coma, punto y coma, tabulador).
  - **SEOR\_SAFE\_ROLLOUT:** Este ajuste probablemente controla un "modo seguro" para las importaciones, quizás permitiéndole previsualizar los cambios o habilitar las redirecciones gradualmente para evitar problemas accidentales.
- **Efecto de los cambios:**
  - *Importar un archivo:* Crea múltiples reglas de redirección de forma masiva, ahorrando un esfuerzo manual significativo.
  - *Cambiar el delimitador:* Asegura que el módulo analice correctamente su archivo CSV.
  - *Despliegue Seguro:* Si está habilitado, podría permitir un despliegue por etapas de las redirecciones, dándole tiempo para verificar antes de que se activen.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esta función al migrar una tienda, realizar una reestructuración importante del sitio o limpiar un gran número de errores 404 acumulados. Siempre pruebe un pequeño lote primero si es posible.

#### 2.2.4 Auditoría (AdminSeoRedirectAuditController)

**Nombre de la Pantalla y Ubicación del Menú:** **Redirecciones SEO > Auditoría**
La herramienta de auditoría le ayuda a identificar enlaces rotos (errores 404) en su sitio web, que son candidatos principales para la redirección.

- **Acciones y Ajustes Disponibles:**
  - **Escanear en Busca de Errores 404:** Inicia un escaneo de su sitio web (o una parte específica) para encontrar páginas que devuelven un estado 404.
  - **Lista de Errores 404:** Muestra una tabla de enlaces rotos detectados, a menudo con la página de referencia (donde se encontró el enlace roto) y el número de veces que se accedió a ella.
  - **Opción para Crear Redirección:** Cree directamente una regla de redirección para un error 404 detectado desde esta pantalla.
- **Efecto de los cambios:** Ejecutar una auditoría le ayuda a encontrar y solucionar proactivamente problemas que dañan el SEO y la experiencia del usuario.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Ejecute una auditoría periódicamente (por ejemplo, mensualmente) para detectar nuevos enlaces rotos que puedan aparecer debido a cambios de contenido o enlaces externos. Priorice la corrección de los 404 a los que se accede con frecuencia o que están vinculados desde páginas importantes.

#### 2.2.5 Historial (AdminSeoRedirectHistoryController)

**Nombre de la Pantalla y Ubicación del Menú:** **Redirecciones SEO > Historial**
Esta pantalla registra todos los eventos de redirección, proporcionando un registro claro de cuándo y cómo se utilizan las redirecciones.

- **Acciones y Ajustes Disponibles:**
  - **Tabla de Eventos de Redirección:** Muestra detalles como la URL original solicitada, la nueva URL a la que se redirigió, el tipo de redirección, la fecha/hora y, potencialmente, el agente de usuario o la dirección IP.
  - **Buscar/Filtrar:** Le ayuda a encontrar eventos de redirección específicos.
- **Efecto de los cambios:** Esta es una herramienta de informes y diagnóstico. No cambia el comportamiento de la tienda, pero proporciona información valiosa sobre cómo funcionan sus redirecciones.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice el historial para verificar que las redirecciones específicas funcionan como se espera, solucionar bucles de redirección inesperados o analizar patrones de tráfico a páginas redirigidas.

#### 2.2.6 Ajustes (AdminSeoRedirectSettingsController)

**Nombre de la Pantalla y Ubicación del Menú:** **Redirecciones SEO > Ajustes**
Esta sección contiene opciones de configuración avanzadas que controlan el comportamiento global del módulo.

- **Acciones y Ajustes Disponibles:**
  - **seor\_pos\_exclude:**
    - **Qué hace este ajuste:** Le permite excluir URLs o patrones específicos de ser redirigidos o auditados automáticamente. Esto es útil para páginas que intencionalmente desea que devuelvan un 404 (por ejemplo, páginas de prueba antiguas).
    - **Efecto de cambiar este ajuste:**
      - *Añadir URLs:* El módulo ignorará estas URLs al realizar redirecciones o auditorías.
      - *Eliminar URLs:* Estas URLs estarán sujetas a la lógica de redirección del módulo.
    - **Valor recomendado:** Mantenga esta lista actualizada con cualquier URL que deba ser genuinamente un 404 y no ser redirigida.
    - **Escenario / ejemplo de comerciante:** Podría tener una página de destino temporal que desea eliminar por completo, y no quiere que el módulo intente redirigirla.
  - **seor\_unavorder:**
    - **Qué hace este ajuste:** Probablemente controla cómo el módulo maneja las redirecciones para productos no disponibles o agotados.
    - **Efecto de cambiar este ajuste:**
      - *Habilitado:* El módulo podría redirigir automáticamente las páginas de productos no disponibles a una página de categoría o a una página personalizada de "producto no encontrado".
      - *Deshabilitado:* Las páginas de productos no disponibles devolverán un error 404 estándar.
    - **Valor recomendado:** **Habilitado** para mejorar la experiencia del usuario y el SEO de los productos descatalogados.
    - **Escenario / ejemplo de comerciante:** Cuando un producto se elimina de su catálogo, puede redirigir automáticamente su URL antigua a su categoría principal o a un producto similar, en lugar de mostrar un 404.
  - **seor\_pos\_category, seor\_pins\_category, seor\_pos\_exclude\_cat, seor\_oos\_cat\_include, seor\_emptycat\_exclusions, seor\_pos, seor\_emptycat:**
    - **Qué hacen estos ajustes:** Es probable que se trate de un grupo de ajustes relacionados con la forma en que el módulo maneja las redirecciones para las categorías, especialmente las categorías vacías, los productos agotados dentro de las categorías o las exclusiones de categorías específicas.
      - `seor_pos_category`: Ajuste general para redirecciones de categoría.
      - `seor_pins_category`: Puede relacionarse con categorías "fijadas" o un comportamiento específico de redirección de categoría.
      - `seor_pos_exclude_cat`: Excluye categorías específicas de la lógica de redirección automática.
      - `seor_oos_cat_include`: Incluye productos agotados en la lógica de redirección de categoría.
      - `seor_emptycat_exclusions`: Excluye categorías vacías específicas de ser redirigidas.
      - `seor_pos`: Ajuste general para redirecciones de posición de producto/categoría.
      - `seor_emptycat`: Controla las redirecciones automáticas para categorías vacías.
    - **Efecto de cambiar estos ajustes:** Estos ajustes permiten un control granular sobre cómo se gestionan las URLs de categoría cuando las categorías están vacías, los productos están agotados o las categorías se eliminan. Pueden evitar los 404 para contenido dinámico.
    - **Valor recomendado:** Revíselos según las necesidades específicas de su tienda. Por ejemplo, redirigir automáticamente las categorías vacías a su padre puede ser beneficioso.
    - **Escenario / ejemplo de comerciante:** Si una categoría queda vacía porque todos los productos están agotados, es posible que desee redirigir automáticamente su URL a la categoría principal para evitar un 404.

#### 2.2.7 Herramientas (AdminSeoRedirectToolsController)

**Nombre de la Pantalla y Ubicación del Menú:** **Redirecciones SEO > Herramientas**
Esta sección proporciona funciones de utilidad, que potencialmente incluyen la integración con servicios externos.

- **Acciones y Ajustes Disponibles:**
  - **SEOR\_GSC\_TOKEN, SEOR\_GSC\_SITE:** Estos ajustes sugieren la integración con Google Search Console (GSC).
    - **Qué hacen estos ajustes:** Le permiten conectar su tienda PrestaShop con su cuenta de Google Search Console. Esto podría permitir que el módulo obtenga automáticamente los errores 404 reportados por Google o envíe sitemaps/redirecciones a GSC.
    - **Efecto de cambiar este ajuste:**
      - *Configurar GSC:* Habilita el intercambio de datos entre su tienda y Google Search Console, automatizando potencialmente el descubrimiento de enlaces rotos y mejorando su flujo de trabajo de SEO.
      - *No configurado:* Tendrá que revisar manualmente GSC en busca de 404 y añadir redirecciones.
    - **Valor recomendado:** Configure si utiliza activamente Google Search Console para el SEO de su tienda.
    - **Escenario / ejemplo de comerciante:** En lugar de revisar manualmente Google Search Console en busca de nuevos errores 404, el módulo podría extraerlos directamente, lo que le permitiría crear redirecciones más rápidamente.

#### 2.2.8 Estadísticas (AdminSeoRedirectStatsController)

**Nombre de la Pantalla y Ubicación del Menú:** **Redirecciones SEO > Estadísticas**
Esta pantalla proporciona estadísticas relacionadas con la salud general de su tienda, incluyendo potencialmente el impacto de las redirecciones.

- **Acciones y Ajustes Disponibles:**
  - **PS\_SHOP\_ENABLE:** Esta es una clave de configuración estándar de PrestaShop que indica si su tienda está actualmente habilitada o en modo de mantenimiento. El módulo podría mostrar esto como una verificación rápida de estado.
  - **Métricas de Rendimiento de Redirección:** Puede mostrar datos agregados sobre cuántas redirecciones han ocurrido, qué tipos son más comunes y su impacto general.
- **Efecto de los cambios:** Esta es principalmente una pantalla informativa. Le ayuda a comprender el rendimiento general y el uso del módulo.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise periódicamente estas estadísticas para comprender el volumen de redirecciones y asegurarse de que el módulo contribuye activamente a un sitio saludable.

#### 2.2.9 Controlador API (AdminSeoRedirectApiController)

**Nombre de la Pantalla y Ubicación del Menú:** **Redirecciones SEO > API** (o similar, podría ser una sección técnica)
Esta pantalla es para usuarios avanzados o desarrolladores que desean interactuar con la funcionalidad de redirección del módulo de forma programática.

- **Acciones y Ajustes Disponibles:**
  - **Documentación de la API:** Proporciona información sobre cómo usar la API del módulo para crear, recuperar, actualizar o eliminar redirecciones desde aplicaciones externas o scripts personalizados.
  - **Gestión de Claves API:** Le permite generar y gestionar claves API para un acceso seguro.
- **Efecto de los cambios:** La configuración del acceso a la API permite que los sistemas externos (por ejemplo, un sistema de gestión de inventario personalizado, una herramienta de SEO de terceros) interactúen con sus redirecciones.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esto solo si tiene necesidades de integración específicas y experiencia técnica.

#### 2.2.10 Controlador CLI (AdminSeoRedirectCliController)

**Nombre de la Pantalla y Ubicación del Menú:** **Redirecciones SEO > CLI** (o similar, podría ser una sección técnica)
Esta pantalla proporciona información y herramientas para operaciones de interfaz de línea de comandos (CLI) relacionadas con el módulo.

- **Acciones y Ajustes Disponibles:**
  - **Documentación de Comandos CLI:** Explica cómo ejecutar tareas específicas del módulo desde la línea de comandos de su servidor (por ejemplo, `php bin/console seoredirect:audit`).
  - **Configuración de Tareas Cron:** Proporciona instrucciones para configurar tareas cron para automatizar tareas como auditorías regulares o limpiezas de redirecciones.
- **Efecto de los cambios:** El uso de herramientas CLI permite la automatización de tareas, lo cual es especialmente útil para tiendas grandes u operaciones complejas.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Consulte esta sección si desea automatizar tareas como auditorías diarias de 404 o verificaciones periódicas del estado de las redirecciones utilizando tareas cron del servidor.

#### 2.2.11 Controlador de Búsqueda (AdminSeoredirectSearchController)

**Nombre de la Pantalla y Ubicación del Menú:** **Redirecciones SEO > Búsqueda** (o integrado en otras pantallas)
Este controlador probablemente impulsa las funcionalidades de búsqueda avanzadas dentro de las diversas cuadrículas y listas del módulo, ayudándole a encontrar rápidamente redirecciones específicas, errores 404 o entradas de historial.

- **Acciones y Ajustes Disponibles:**
  - **Filtros de Búsqueda Avanzada:** Proporciona opciones de búsqueda más granulares más allá de la búsqueda de texto simple, posiblemente incluyendo rangos de fechas, tipos de redirección o estado.
- **Efecto de los cambios:** Mejora su capacidad para navegar y gestionar grandes conjuntos de datos dentro del módulo.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esto cuando necesite localizar rápidamente una regla de redirección específica o analizar un subconjunto de sus datos.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Panel de Control** | `SEOR_DASHBOARD_PERIOD` | Últimos 30 días | Controla el período de tiempo para las estadísticas del panel de control. |
| **Lista de Redirecciones** | URL Antigua | N/A | La URL desde la que redirigir. |
|  | URL Nueva | N/A | La URL a la que redirigir. |
|  | Tipo de Redirección | 301 Permanente | Tipo de redirección (301, 302, 303). 301 es el mejor para SEO. |
|  | Estado | Habilitado | Activa/desactiva una regla de redirección específica. |
| **Importar** | `IV_COL_DELIMITER` | Coma (`,`) | Carácter que separa las columnas en el archivo de importación CSV. |
|  | `SEOR_SAFE_ROLLOUT` | No | Habilita un modo seguro para las importaciones (por ejemplo, despliegue por etapas). |
| **Ajustes** | `seor_pos_exclude` | Vacío | Lista de URLs/patrones a excluir de la redirección/auditoría. |
|  | `seor_unavorder` | Sí | Redirige automáticamente los productos no disponibles. |
|  | `seor_pos_category` | Sí | Ajuste general para redirecciones de categoría. |
|  | `seor_pins_category` | No | Comportamiento específico de redirección de categoría. |
|  | `seor_pos_exclude_cat` | Vacío | Excluye categorías específicas de la redirección automática. |
|  | `seor_oos_cat_include` | Sí | Incluye productos agotados en la lógica de redirección de categoría. |
|  | `seor_emptycat_exclusions` | Vacío | Excluye categorías vacías específicas de ser redirigidas. |
|  | `seor_pos` | Sí | Ajuste general para redirecciones de posición de producto/categoría. |
|  | `seor_emptycat` | Sí | Controla las redirecciones automáticas para categorías vacías. |
| **Herramientas** | `SEOR_GSC_TOKEN` | Vacío | Token de la API de Google Search Console para la integración. |
|  | `SEOR_GSC_SITE` | Vacío | La URL de su sitio web registrada en Google Search Console. |
| **Estadísticas** | `PS_SHOP_ENABLE` | Sí | Muestra el estado actual de la tienda (habilitada/mantenimiento). |

## 3. Solución de Problemas para el Comerciante y Preguntas Frecuentes (FAQ)

**P1: He añadido una redirección, pero no funciona. ¿Qué debo hacer?**
R1:

- **Verifique si hay errores tipográficos:** Asegúrese de que la "URL Antigua" y la "URL Nueva" estén escritas exactamente correctamente en la Lista de Redirecciones.
- **Borrar Caché:** PrestaShop utiliza caché. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar la caché". También, borre la caché de su navegador.
- **Estado del Módulo:** Asegúrese de que el módulo "Redirecciones SEO 301, 302, 303" esté habilitado en **Módulos > Gestor de módulos**.
- **Orden de Redirección:** Si tiene varios módulos de redirección o reglas de `.htaccess`, podría haber un conflicto. Este módulo suele tener precedencia, pero revise el archivo `.htaccess` de su servidor en busca de reglas conflictivas.
- **URL Completa vs. URL Relativa:** Asegúrese de que está utilizando el formato correcto para sus URLs (por ejemplo, `/old-page.html` para rutas relativas, o `https://www.yourstore.com/old-page.html` para rutas completas, dependiendo de cómo el módulo las espere).

**P2: ¿Este módulo ralentizará mi tienda?**
R2: El módulo está diseñado para ser eficiente. Las redirecciones ocurren en una etapa muy temprana del proceso de solicitud, minimizando el impacto. Sin embargo, tener decenas de miles de redirecciones podría añadir una pequeña sobrecarga. Auditar y limpiar regularmente las redirecciones innecesarias (por ejemplo, antiguas 302 temporales) puede ayudar a mantener el rendimiento.

**P3: ¿Cómo gestiono las redirecciones para productos que están temporalmente agotados?**
R3:

- Para situaciones temporales, una **Redirección Temporal 302** a una página de categoría relevante o a una página de "notificarme cuando esté disponible" es apropiada. Esto indica a los motores de búsqueda que el producto podría volver.
- Revise la pantalla de **Ajustes** para opciones como `seor_unavorder` o `seor_oos_cat_include`, que podrían ofrecer un manejo automático para productos agotados.

**P4: ¿Puedo usar comodines en mis reglas de redirección (por ejemplo, redirigir todas las páginas en un directorio antiguo)?**
R4: La documentación o interfaz del módulo especificará si admite expresiones regulares o caracteres comodín (como `*`). Si lo hace, puede crear reglas potentes como `/old-category/*` a `/new-category/$1` (donde `$1` captura el resto de la URL). Si no, deberá listar cada redirección individualmente o usar la función de importación. ¡Siempre pruebe las redirecciones con comodines con cuidado!

**P5: Mi tema personalizado no muestra correctamente las características del módulo (por ejemplo, en el modal de auditoría).**
R5: Las interfaces de back-office del módulo son generalmente independientes de su tema de front-office. Si experimenta problemas de visualización en el panel de administración, podría ser un conflicto con otro módulo de administración o una modificación del archivo central de PrestaShop.

- **Borrar Caché de PrestaShop:** Vaya a **Parámetros Avanzados > Rendimiento** y borre la caché.
- **Verificar Consola del Navegador:** Abra las herramientas de desarrollador de su navegador (F12) y busque errores de JavaScript o advertencias de CSS en la pestaña Consola cuando esté en las páginas de configuración del módulo. Esto puede dar pistas sobre conflictos.
- **Contactar Soporte:** Si el problema persiste, proporcione capturas de pantalla y cualquier error de consola al soporte de MyPresta.eu.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Visión General de la Arquitectura

El módulo "Redirecciones SEO 301, 302, 303" está construido siguiendo el patrón MVC (Modelo-Vista-Controlador) de PrestaShop, con un fuerte énfasis en el control administrativo y la gestión de datos. Aprovecha `ModuleAdminController` para su extensa interfaz de back-office, `ObjectModel` para gestionar los datos de redirección, y anula el `FrontController` para interceptar las solicitudes temprano y aplicar la lógica de redirección. El módulo también incluye controladores API y CLI para la gestión programática y automatizada.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

Estos controladores manejan las solicitudes en el lado de la tienda visible para el cliente.

- `seoredirect/controllers/front/api.php`
  - **Nombre de la clase y clase padre:** `SeoredirectApiModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador probablemente sirve como un punto final de API de front-office, potencialmente para que servicios externos consulten el estado de la redirección o para llamadas AJAX internas relacionadas con la lógica de redirección de front-office (aunque la mayoría de las redirecciones se manejan a través de la anulación de `FrontController`). Respondería a rutas específicas definidas por el módulo.
- `seoredirect/controllers/front/cronjob.php`
  - **Nombre de la clase y clase padre:** `SeoredirectCronjobModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Proporciona un punto final accesible desde el front-office para ejecutar tareas cron. Esto permite que las tareas cron del lado del servidor (por ejemplo, comandos `wget` o `curl`) activen funciones del módulo como auditorías, limpieza o sincronización de datos sin requerir autenticación de back-office.
- `seoredirect/controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `SeoredirectIndexModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Un marcador de posición o controlador frontal predeterminado. En muchos módulos, esto podría manejar una ruta predeterminada simple o servir como base para otros controladores frontales. Dada la naturaleza del módulo, su lógica principal de front-office probablemente se encuentra en la anulación de `FrontController`.

#### Controladores de Administración de Back-Office

Estos controladores gestionan la interfaz y los datos del módulo dentro del Back Office de PrestaShop.

- `seoredirect/controllers/admin/AdminSeoRedirectApiController.php`
  - **Nombre de la pestaña y entidad gestionada:** "API" (o similar, bajo el menú Redirecciones SEO). Gestiona las claves API y proporciona documentación de la API.
  - **Responsabilidad:** Maneja la visualización y gestión de credenciales de API y documentación para la interacción programática con el módulo.
- `seoredirect/controllers/admin/AdminSeoRedirectAuditController.php`
  - **Nombre de la pestaña y entidad gestionada:** "Auditoría" (bajo el menú Redirecciones SEO). Gestiona el proceso de auditoría de errores 404.
  - **Responsabilidad:** Proporciona la interfaz para escanear la tienda en busca de errores 404, mostrar los resultados y ofrecer opciones para crear redirecciones a partir de los enlaces rotos detectados.
- `seoredirect/controllers/admin/AdminSeoRedirectCliController.php`
  - **Nombre de la pestaña y entidad gestionada:** "CLI" (o similar, bajo el menú Redirecciones SEO). Proporciona documentación de comandos CLI.
  - **Responsabilidad:** Muestra información e instrucciones para usar las herramientas de interfaz de línea de comandos del módulo, útiles para la automatización y tareas avanzadas.
- `seoredirect/controllers/admin/AdminSeoRedirectDashboardController.php`
  - **Nombre de la pestaña y entidad gestionada:** "Panel de Control" (bajo el menú Redirecciones SEO). Muestra estadísticas y una visión general del módulo.
  - **Responsabilidad:** Presenta métricas clave y una visión general de la actividad de redirección, incluyendo potencialmente gráficos. Gestiona la configuración `SEOR_DASHBOARD_PERIOD`.
- `seoredirect/controllers/admin/AdminSeoRedirectHistoryController.php`
  - **Nombre de la pestaña y entidad gestionada:** "Historial" (bajo el menú Redirecciones SEO). Gestiona los registros `seor_history`.
  - **Responsabilidad:** Muestra un registro de todos los eventos de redirección, incluyendo origen, destino, tipo y marca de tiempo.
- `seoredirect/controllers/admin/AdminSeoRedirectImport.php`
  - **Nombre de la pestaña y entidad gestionada:** "Importar" (bajo el menú Redirecciones SEO). Gestiona la importación masiva de redirecciones.
  - **Responsabilidad:** Proporciona la interfaz para subir archivos CSV para crear múltiples reglas de redirección. Gestiona las configuraciones `IV_COL_DELIMITER` y `SEOR_SAFE_ROLLOUT`.
- `seoredirect/controllers/admin/AdminSeoRedirectListController.php`
  - **Nombre de la pestaña y entidad gestionada:** "Lista de Redirecciones" (bajo el menú Redirecciones SEO). Gestiona los registros `seor` (redirección).
  - **Responsabilidad:** La interfaz principal para añadir, editar, eliminar y listar reglas de redirección individuales 301, 302, 303.
- `seoredirect/controllers/admin/AdminSeoredirectSearchController.php`
  - **Nombre de la pestaña y entidad gestionada:** "Búsqueda" (o integrado). Impulsa la funcionalidad de búsqueda.
  - **Responsabilidad:** Probablemente proporciona capacidades avanzadas de búsqueda y filtrado utilizadas en varias cuadrículas de administración dentro del módulo.
- `seoredirect/controllers/admin/AdminSeoRedirectSettings.php`
  - **Nombre de la pestaña y entidad gestionada:** "Ajustes" (bajo el menú Redirecciones SEO). Gestiona los ajustes de `ps_configuration` relacionados con el módulo.
  - **Responsabilidad:** Proporciona la interfaz para configurar el comportamiento global del módulo, como exclusiones, redirecciones automáticas para productos no disponibles/categorías vacías y otras opciones avanzadas. Gestiona `seor_pos_exclude`, `seor_unavorder`, `seor_pos_category`, `seor_pins_category`, `seor_pos_exclude_cat`, `seor_oos_cat_include`, `seor_emptycat_exclusions`, `seor_pos`, `seor_emptycat`.
- `seoredirect/controllers/admin/AdminSeoRedirectStats.php`
  - **Nombre de la pestaña y entidad gestionada:** "Estadísticas" (bajo el menú Redirecciones SEO). Muestra estadísticas generales de la tienda y del módulo.
  - **Responsabilidad:** Proporciona una visión general del estado de la tienda (`PS_SHOP_ENABLE`) y potencialmente datos agregados de rendimiento de redirección.
- `seoredirect/controllers/admin/AdminSeoRedirectToolsController.php`
  - **Nombre de la pestaña y entidad gestionada:** "Herramientas" (bajo el menú Redirecciones SEO). Proporciona funciones de utilidad.
  - **Responsabilidad:** Contiene herramientas como la integración con Google Search Console (`SEOR_GSC_TOKEN`, `SEOR_GSC_SITE`) y otras características de utilidad.
- `seoredirect/controllers/admin/index.php`
  - **Nombre de la pestaña y entidad gestionada:** No es un controlador directo, típicamente un archivo vacío o una medida de seguridad para evitar la lista de directorios.

### 4.3 Clases y Modelos Principales (`classes/`)

- `seoredirect/override/classes/controller/FrontController.php`
  - **Qué hace:** Esta es una anulación crítica. Extiende la clase `FrontController` central de PrestaShop.
  - **Métodos públicos clave y lógica de negocio:** La anulación probablemente intercepta el método `init()` o `postProcess()` del `FrontController`. Antes de que PrestaShop envíe la solicitud a un controlador de página específico, esta anulación verifica la URL solicitada contra las reglas de redirección almacenadas del módulo. Si se encuentra una coincidencia, emite el encabezado de redirección HTTP 301, 302 o 303 apropiado y termina la solicitud, evitando un 404 y enviando al usuario a la nueva URL. Aquí es donde reside la lógica de redirección principal.
- `seoredirect/override/classes/controller/index.php`
  - **Qué hace:** Archivo de marcador de posición, generalmente por seguridad.
- `seoredirect/override/classes/index.php`
  - **Qué hace:** Archivo de marcador de posición, generalmente por seguridad.

*(Nota: El dossier del módulo no listaba explícitamente clases `ObjectModel` personalizadas como `SeoRedirect` o `SeoRedirectHistory`. Sin embargo, dada la presencia de `AdminSeoRedirectListController` gestionando `seor` y `AdminSeoRedirectHistoryController` gestionando `seor_history`, es muy probable que existan clases `SeoRedirect` y `SeoRedirectHistory` correspondientes (o nombres similares) que extiendan `ObjectModel` dentro del directorio principal del módulo o un subdirectorio `classes/` no listado explícitamente en el inventario. Estas definirían el esquema de la base de datos para las redirecciones y las entradas del historial.)*

### 4.4 Activos JavaScript (`views/js/`)

- `seoredirect/examples/console-mock-dashboard-audit.js`
  - **Alcance:** Probablemente para desarrollo/pruebas, no para producción.
  - **Detalles:** Ejemplo o datos/lógica simulada para las funciones de panel de control y auditoría, posiblemente utilizada para depuración de consola o demostración.
- `seoredirect/views/js/adminSeoRedirectApi.js`
  - **Alcance:** Back-office (AdminSeoRedirectApiController).
  - **Detalles:** Maneja las interacciones del lado del cliente en la pantalla de configuración de la API, como generar claves API, copiar claves al portapapeles o mostrar modales de documentación de la API.
- `seoredirect/views/js/adminSeoRedirectAudit.js`
  - **Alcance:** Back-office (AdminSeoRedirectAuditController).
  - **Detalles:** Gestiona el proceso de auditoría, incluyendo llamadas AJAX para activar escaneos, actualizar indicadores de progreso, mostrar los resultados de la auditoría en una tabla dinámica y manejar acciones como crear redirecciones a partir de los hallazgos de la auditoría. Puede incluir ventanas modales para previsualizar o confirmar redirecciones.
- `seoredirect/views/js/adminSeoRedirectConfig.js`
  - **Alcance:** Back-office (Configuración principal del módulo o AdminSeoRedirectSettingsController).
  - **Detalles:** JavaScript general para los formularios de configuración principal del módulo. Esto podría incluir validación de formularios, visibilidad dinámica de campos basada en otros ajustes o llamadas AJAX para guardar la configuración.
- `seoredirect/views/js/adminSeoRedirectDashboard.js`
  - **Alcance:** Back-office (AdminSeoRedirectDashboardController).
  - **Detalles:** Impulsa los elementos interactivos del panel de control, como cargar datos a través de AJAX, renderizar gráficos (si los hay) y manejar cambios en la selección de período (`SEOR_DASHBOARD_PERIOD`).
- `seoredirect/views/js/adminSeoRedirectImport.js`
  - **Alcance:** Back-office (AdminSeoRedirectImportController).
  - **Detalles:** Gestiona el proceso de importación de CSV, incluyendo la selección de archivos, indicadores de progreso, visualización de resultados/errores de importación y, potencialmente, el manejo de la lógica `SEOR_SAFE_ROLLOUT` en el lado del cliente.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `seoredirect/views/css/seoredirect-admin.css`
  - **Alcance:** Estilo de formularios de administración de back-office.
  - **Detalles:** Contiene estilos específicos para las diversas pantallas de administración del módulo, asegurando una interfaz consistente y fácil de usar dentro del back office de PrestaShop. Esto incluiría el estilo para cuadrículas, formularios, botones, modales y elementos del panel de control.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:** Busque clases con el prefijo `seor-` o `admin-seoredirect-` para elementos específicos del módulo.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de gancho (`views/templates/hook/`)**:

  - La descripción del módulo menciona ganchos de front-office (Encabezado, Columnas, Producto, Pie de página), pero el inventario de archivos no lista plantillas de gancho específicas en `views/templates/hook/`. Esto sugiere que la interacción del front-office se maneja principalmente mediante la anulación de `FrontController` para las redirecciones, en lugar de renderizar contenido visible en los ganchos. Si existen plantillas de gancho, serían para elementos de visualización muy específicos y no relacionados con las redirecciones.
- **Plantillas de administración (`views/templates/admin/`)**:

  - `seoredirect/lib/searchTool/views/scripts.tpl`: Probablemente contiene lógica JavaScript o Smarty para una herramienta de búsqueda genérica utilizada en múltiples pantallas de administración.
  - `seoredirect/views/admin/adminSearch.tpl`: Plantilla para una interfaz de búsqueda genérica en el administrador.
  - `seoredirect/views/admin/adminSearchCategory.tpl`: Plantilla para buscar/seleccionar categorías en el administrador.
  - `seoredirect/views/admin/adminSearchCategoryToMove.tpl`: Plantilla para la búsqueda de movimiento de categorías.
  - `seoredirect/views/admin/adminSearchCategoryToMoveInStock.tpl`: Plantilla para la búsqueda de movimiento de categorías, específicamente para artículos en stock.
  - `seoredirect/views/admin/adminSeoRedirectImport.tpl`: La plantilla principal para la pantalla de importación (AdminSeoRedirectImportController).
  - `seoredirect/views/admin/stats.tpl`: Plantilla para la pantalla de estadísticas (AdminSeoRedirectStatsController).
  - `seoredirect/views/templates/admin/api.tpl`: Plantilla para la pantalla de configuración de la API (AdminSeoRedirectApiController).
  - `seoredirect/views/templates/admin/audit.tpl`: Plantilla para la pantalla de auditoría (AdminSeoRedirectAuditController).
  - `seoredirect/views/templates/admin/cli.tpl`: Plantilla para la pantalla de documentación CLI (AdminSeoRedirectCliController).
  - `seoredirect/views/templates/admin/dashboard.tpl`: Plantilla para el panel de control del módulo (AdminSeoRedirectDashboardController).
  - `seoredirect/views/templates/admin/employee_permissions.tpl`: Plantilla para gestionar los permisos de los empleados relacionados con las pestañas de administración del módulo.
  - `seoredirect/views/templates/admin/import.tpl`: Otra plantilla para la funcionalidad de importación (podría ser un envoltorio o una parte específica del proceso de importación).
  - `seoredirect/views/templates/admin/seo_redirect_settings/helpers/options/options.tpl`: Una plantilla parcial para renderizar opciones dentro de la pantalla de configuración (AdminSeoRedirectSettingsController).
  - `seoredirect/views/templates/admin/tools.tpl`: Plantilla para la pantalla de herramientas (AdminSeoRedirectToolsController).
  - `seoredirect/views/templates/admin/_api_documentation_modal.tpl`: Una plantilla modal para mostrar la documentación de la API.
  - `seoredirect/views/templates/admin/_audit_preview_modal.tpl`: Una plantilla modal para previsualizar los resultados de la auditoría o las creaciones de redirección.
  - `seoredirect/views/templates/admin/_cli_documentation_modal.tpl`: Una plantilla modal para mostrar la documentación CLI.
- **Plantillas de front-office (`views/templates/front/`)**:

  - No se listan plantillas específicas de front-office, lo que refuerza que la operación de front-end del módulo se realiza principalmente a través de la anulación de `FrontController` para la redirección, no a través de contenido visible.

### 4.7 Esquema de Base de Datos y Mapa de Ganchos

- **Tablas de Base de Datos**:

  - `ps_seor`: Almacena las reglas de redirección principales (URL Antigua, URL Nueva, Tipo de Redirección, Estado, etc.). Esta tabla es gestionada por `AdminSeoRedirectListController` y el `ObjectModel` `SeoRedirect` (implícito).
  - `ps_seor_history`: Almacena un registro de todas las redirecciones activadas (Solicitud Original, Redirigido A, Tipo, Marca de Tiempo, etc.). Esta tabla es gestionada por `AdminSeoRedirectHistoryController` y el `ObjectModel` `SeoRedirectHistory` (implícito).
  - `ps_configuration`: Almacena configuraciones globales específicas del módulo como `SEOR_DASHBOARD_PERIOD`, `IV_COL_DELIMITER`, `SEOR_SAFE_ROLLOUT`, `seor_pos_exclude`, `seor_unavorder`, `seor_pos_category`, `seor_pins_category`, `seor_pos_exclude_cat`, `seor_oos_cat_include`, `seor_emptycat_exclusions`, `seor_pos`, `seor_emptycat`, `SEOR_GSC_TOKEN`, `SEOR_GSC_SITE`.
- **Tabla de Ganchos Registrados**:

  | Nombre del Gancho | Momento de Ejecución | Propósito Técnico |
  | --- | --- | --- |
  | `actionFrontControllerSetMedia` | Antes de que el controlador frontal renderice el contenido | Potencialmente carga JS/CSS de front-office si los hay, aunque es poco probable para un módulo de redirección. |
  | `actionDispatcherBefore` | Muy temprano en el ciclo de vida de la solicitud, antes de enviar a un controlador. | **CRÍTICO:** Este es el gancho más probable para que la anulación de `FrontController` intercepte la solicitud y aplique la lógica de redirección. Permite que el módulo redirija antes de que PrestaShop intente encontrar la página original. |
  | `displayAdminProductsExtra` | En la página de edición de productos en el back office. | Podría usarse para mostrar el estado de redirección de un producto o sugerir la creación de una redirección si se cambia la URL del producto. |
  | `displayAdminCategoriesExtra` | En la página de edición de categorías en el back office. | Similar a los productos, podría mostrar el estado de redirección o sugerir redirecciones para cambios de URL de categoría. |
  | `displayHeader` | En la sección `<head>` de cada página de front-office. | Poco probable para la lógica de redirección principal, pero podría usarse para añadir metaetiquetas o canónicas relacionadas con las redirecciones si fuera necesario. |
  | `displayRightColumn` | En la columna derecha de las páginas de front-office. | Poco probable para este módulo. |
  | `displayFooter` | En el pie de página de cada página de front-office. | Poco probable para este módulo. |
  | `actionValidateOrder` | Después de que un pedido se valida con éxito. | Podría usarse para registrar o auditar redirecciones relacionadas con los procesos de pago, aunque menos directo. |
  | `actionModuleInstall` | Durante la instalación del módulo. | Crea tablas de base de datos, registra ganchos, establece valores de configuración predeterminados. |
  | `actionModuleUninstall` | Durante la desinstalación del módulo. | Limpia tablas de base de datos, anula el registro de ganchos, elimina valores de configuración. |
  | `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice el contenido. | Carga JS/CSS de back-office para las páginas de administración del módulo. |
  | `actionAdminSeoRedirectSave` | Gancho personalizado, probablemente activado después de guardar una regla de redirección en el back office. | Permite que otros módulos o código personalizado reaccionen a los cambios de redirección. |
  | `actionAdminSeoRedirectDelete` | Gancho personalizado, probablemente activado después de eliminar una regla de redirección. | Permite que otros módulos o código personalizado reaccionen a las eliminaciones de redirección. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con el módulo "Redirecciones SEO 301, 302, 303".

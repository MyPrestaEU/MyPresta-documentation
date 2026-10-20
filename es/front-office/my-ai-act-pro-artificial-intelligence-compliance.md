---
title: "My AI Act Pro - Cumplimiento de la Ley de IA - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop My AI Act Pro - Cumplimiento de la Ley de IA de MyPresta.eu."
sidebar:
  label: "My AI Act Pro - Cumplimiento de la Ley de IA - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo My AI Act Pro - Artificial Intelligence Compliance en MyPresta.eu](https://mypresta.eu/modules/front-office-features/my-ai-act-pro-artificial-intelligence-compliance.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/my-ai-act-pro-artificial-intelligence-compliance/)
>
> ---


# My AI Act Pro - Cumplimiento de la Ley de IA

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.6.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL). Asegúrese de que su servidor cumpla con los requisitos generales de PrestaShop para un rendimiento óptimo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > My AI Act Pro)

Este es el panel de control principal para su módulo de cumplimiento de la Ley de IA. Aquí habilitará funciones, definirá configuraciones globales y gestionará el comportamiento general de las divulgaciones de IA.

#### Pestaña de Configuración General

- **Habilitar el cumplimiento de la Ley de IA:**

  - **Qué hace esta configuración:** Este es el interruptor maestro para todo el módulo.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado:* Todas las funciones del módulo (insignias, banners, registros, etc.) se activarán en su tienda de acuerdo con sus configuraciones individuales.
    - *Cuando está deshabilitado:* El módulo dejará de mostrar cualquier contenido relacionado con la Ley de IA en su front office, y sus procesos en segundo plano se pausarán.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo del comerciante:** Habilite esto una vez que esté listo para implementar su cumplimiento de la Ley de IA. Si necesita deshabilitar temporalmente todas las divulgaciones por mantenimiento, desactive esto.
- **Mostrar insignia de divulgación de IA en las páginas de productos:**

  - **Qué hace esta configuración:** Controla si la insignia de divulgación de IA aparece en las páginas de productos individuales.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado:* La insignia de IA será visible en las páginas de productos para los productos marcados como generados por IA.
    - *Cuando está deshabilitado:* La insignia no se mostrará en las páginas de productos, incluso si los productos están marcados.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo del comerciante:** Esto es crucial para la transparencia directa del producto. Manténgalo habilitado para informar a los clientes directamente sobre el producto que están viendo.
- **Mostrar insignia de divulgación de IA en los listados de productos:**

  - **Qué hace esta configuración:** Controla si la insignia de divulgación de IA aparece en las páginas de categorías, resultados de búsqueda u otras vistas de listados de productos.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado:* Una insignia de IA más pequeña aparecerá en las miniaturas de los productos en las listas.
    - *Cuando está deshabilitado:* No aparecerá ninguna insignia en los listados de productos.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo del comerciante:** Habilitar esto proporciona transparencia inmediata a medida que los clientes navegan, ayudándoles a identificar el contenido generado por IA antes de hacer clic en una página de producto.
- **Posición de la insignia de divulgación de IA (página de producto):**

  - **Qué hace esta configuración:** Determina dónde se coloca la insignia de IA en la página del producto. Las opciones suelen incluir "Encima de la imagen del producto", "Debajo de la imagen del producto", "Cerca del nombre del producto", "En la descripción del producto", etc.
  - **Efecto de cambiar esta configuración:** La insignia se moverá a la ubicación seleccionada en la página del producto.
  - **Valor recomendado:** Experimente para encontrar el mejor ajuste para su tema, a menudo "Encima de la imagen del producto" o "Cerca del nombre del producto" para mayor visibilidad.
  - **Escenario / ejemplo del comerciante:** Si las imágenes de sus productos son muy grandes, colocar la insignia "Debajo de la imagen del producto" podría ser menos intrusivo. Si desea que sea inmediatamente perceptible, "Encima de la imagen del producto" es mejor.
- **Diseño de la insignia de divulgación de IA:**

  - **Qué hace esta configuración:** Le permite elegir un estilo visual predefinido para la insignia de IA desde el "Estudio de Diseño".
  - **Efecto de cambiar esta configuración:** La apariencia de la insignia de IA (icono, texto, colores, forma) cambiará según el diseño seleccionado.
  - **Valor recomendado:** Seleccione un diseño que coincida con la marca de su tienda y sea claramente visible.
  - **Escenario / ejemplo del comerciante:** Podría crear un diseño personalizado con los colores de su marca y un icono específico para asegurarse de que la insignia se vea profesional y se integre bien.
- **Enlace a la página de política de IA:**

  - **Qué hace esta configuración:** Le permite vincular a una página CMS dedicada o URL externa que explique la política de IA de su tienda.
  - **Efecto de cambiar esta configuración:** El módulo utilizará esta URL al vincular a su política de IA desde insignias, banners u otros elementos de divulgación.
  - **Valor recomendado:** Cree una página CMS detallada (por ejemplo, "Nuestra política de transparencia de IA") y vincúlela aquí.
  - **Escenario / ejemplo del comerciante:** Este enlace es crucial para proporcionar información completa a los clientes que desean obtener más información sobre su uso de la IA.
- **Habilitar banner de divulgación de IA:**

  - **Qué hace esta configuración:** Activa un banner en todo el sitio para informar a los clientes sobre su uso de la IA.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado:* Aparecerá un banner en el hook seleccionado (por ejemplo, encabezado o pie de página).
    - *Cuando está deshabilitado:* No se mostrará ningún banner.
  - **Valor recomendado:** SÍ, especialmente para el lanzamiento inicial o si su tienda utiliza la IA de forma extensiva.
  - **Escenario / ejemplo del comerciante:** Utilice este banner para hacer una declaración general sobre la política de IA de su tienda, quizás vinculando a su página de política dedicada.
- **Posición del banner de divulgación de IA (Hook):**

  - **Qué hace esta configuración:** Selecciona dónde aparecerá el banner (por ejemplo, `displayHeader`, `displayFooter`).
  - **Efecto de cambiar esta configuración:** El banner se renderizará en la ubicación elegida.
  - **Valor recomendado:** `displayHeader` para máxima visibilidad, o `displayFooter` para un enfoque menos intrusivo.
  - **Escenario / ejemplo del comerciante:** Colocarlo en `displayHeader` asegura que cada visitante lo vea inmediatamente al aterrizar en su sitio.
- **Contenido del banner de divulgación de IA:**

  - **Qué hace esta configuración:** Le permite personalizar el texto y el contenido HTML del banner.
  - **Efecto de cambiar esta configuración:** El banner mostrará su mensaje personalizado.
  - **Valor recomendado:** Un mensaje conciso como "Utilizamos IA para mejorar su experiencia de compra. [Más información]" con un enlace a su página de política.
  - **Escenario / ejemplo del comerciante:** Puede usar esto para explicar brevemente su uso de la IA y dirigir a los clientes a su política completa.
- **Habilitar información de respaldo humano:**

  - **Qué hace esta configuración:** Muestra un mensaje que indica supervisión humana u ofrece asistencia humana para el contenido generado por IA.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado:* Aparecerá un mensaje configurable en las páginas relevantes.
    - *Cuando está deshabilitado:* No se mostrará ningún mensaje de respaldo humano.
  - **Valor recomendado:** SÍ, si desea asegurar a los clientes que hay una revisión humana involucrada o proporcionar un punto de contacto.
  - **Escenario / ejemplo del comerciante:** Si las descripciones de sus productos generadas por IA siempre son revisadas por un editor humano, puede usar esto para indicar "Todo el contenido generado por IA es revisado por nuestro equipo. Contáctenos si tiene preguntas".
- **Mensaje de respaldo humano:**

  - **Qué hace esta configuración:** Personaliza el texto para la información de respaldo humano.
  - **Efecto de cambiar esta configuración:** El mensaje se mostrará tal como se ingresó.
  - **Valor recomendado:** Un mensaje claro y tranquilizador.
  - **Escenario / ejemplo del comerciante:** "Nuestras herramientas de IA son supervisadas por expertos humanos. Para cualquier inquietud, comuníquese con nuestro servicio de atención al cliente".
- **Habilitar registro de auditoría:**

  - **Qué hace esta configuración:** Registra todas las acciones y divulgaciones relacionadas con la Ley de IA en un registro para fines de cumplimiento.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado:* Cada vez que se realiza una divulgación de IA o se marca un producto, se guarda una entrada en el registro de auditoría del módulo.
    - *Cuando está deshabilitado:* No se mantendrá ningún registro de auditoría.
  - **Valor recomendado:** SÍ, esto es crucial para demostrar el cumplimiento y la resolución de problemas.
  - **Escenario / ejemplo del comerciante:** Si un organismo regulador solicita pruebas de sus divulgaciones de IA, el registro de auditoría proporciona un registro histórico.

#### Pestaña de API e Integraciones

- **Habilitar API REST:**

  - **Qué hace esta configuración:** Activa un endpoint de API REST para que los sistemas externos interactúen con el módulo (por ejemplo, marcando productos como generados por IA).
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado:* La API se activa, permitiendo la interacción programática.
    - *Cuando está deshabilitado:* La API está inactiva.
  - **Valor recomendado:** NO, a menos que tenga una necesidad técnica específica de integrar con herramientas o sistemas de IA externos.
  - **Escenario / ejemplo del comerciante:** Si utiliza un servicio externo de generación de imágenes de IA, podría usar la API para marcar automáticamente las imágenes como generadas por IA en PrestaShop.
- **Gestión de claves API:**

  - **Qué hace esta configuración:** Le permite generar y gestionar claves API para un acceso seguro a la API REST del módulo.
  - **Efecto de cambiar esta configuración:** Se pueden crear nuevas claves, revocar las existentes, controlando quién puede acceder a la API.
  - **Valor recomendado:** Genere una clave fuerte y única para cada integración.
  - **Escenario / ejemplo del comerciante:** Cree una clave API específica para su generador de imágenes de IA y otra para su escritor de contenido de IA, revocándolas si una integración ya no es necesaria.
- **Habilitar CRON de marca de agua:**

  - **Qué hace esta configuración:** Activa una tarea programada (tarea CRON) para aplicar automáticamente marcas de agua a las imágenes generadas por IA.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado:* La tarea CRON se ejecutará periódicamente, aplicando una marca de agua configurable a las imágenes marcadas.
    - *Cuando está deshabilitado:* No se realizará ninguna marca de agua automática.
  - **Valor recomendado:** NO, a menos que requiera específicamente marcas de agua para imágenes de IA.
  - **Escenario / ejemplo del comerciante:** Si desea un indicador visual directamente en la imagen misma (por ejemplo, un pequeño logotipo de "IA") para todas las imágenes de productos generadas por IA, habilite esto.
- **Imagen/Texto de marca de agua:**

  - **Qué hace esta configuración:** Define la marca de agua a aplicar (por ejemplo, un archivo de imagen o una cadena de texto).
  - **Efecto de cambiar esta configuración:** La tarea CRON utilizará esta marca de agua.
  - **Valor recomendado:** Un indicador sutil y claro si se usa.
  - **Escenario / ejemplo del comerciante:** Suba una imagen pequeña y semitransparente de "Generado por IA" o introduzca "IA" como texto.

#### Pestaña de Shortcodes

- **Lista y uso de shortcodes:**
  - **Qué hace esta configuración:** Proporciona una lista de shortcodes disponibles que se pueden insertar en descripciones de productos, páginas CMS u otras áreas de texto.
  - **Efecto de cambiar esta configuración:** No hay cambios directos, pero el uso de estos shortcodes en su contenido mostrará los elementos de divulgación de IA correspondientes.
  - **Valor recomendado:** Utilice estos shortcodes para incrustar divulgaciones específicas donde la configuración global podría no ser suficiente.
  - **Escenario / ejemplo del comerciante:** Podría tener un producto donde solo un párrafo específico de la descripción fue generado por IA. Puede envolver ese párrafo con un shortcode para mostrar una pequeña insignia junto a él.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### 2.2.1 Ley de IA > Gestión masiva de productos (AdminMyAiActBulkController)

- **Nombre de la pantalla y ubicación del menú:** En su Back Office de PrestaShop, navegue a **Ley de IA > Gestión masiva de productos**.
- **Acciones y configuraciones disponibles:** Esta pantalla proporciona una potente vista de cuadrícula para gestionar el estado de la Ley de IA de varios productos a la vez.
  - **Listado de productos:** Muestra una lista de todos sus productos con columnas para el nombre del producto, ID y, lo que es más importante, su estado de la Ley de IA.
  - **Filtros y búsqueda:** Le permite filtrar productos por varios criterios (por ejemplo, categoría, proveedor, estado de la Ley de IA) para encontrar rápidamente elementos específicos.
  - **Acciones masivas:**
    - **Marcar como generado por IA:** Seleccione varios productos y aplique la bandera de "generado por IA" a ellos simultáneamente.
    - **Desmarcar como generado por IA:** Elimine la bandera de "generado por IA" de los productos seleccionados.
    - **Aplicar etiquetas específicas de la Ley de IA:** Asigne etiquetas o reglas personalizadas (si están configuradas) a varios productos.
- **Efecto de los cambios:**
  - Cuando marca productos como generados por IA, las insignias y divulgaciones del front-office aparecerán para estos productos de acuerdo con la configuración general de su módulo.
  - Desmarcar productos elimina estas divulgaciones.
  - La aplicación de etiquetas permite un control más granular sobre tipos o mensajes de divulgación específicos.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Después de importar nuevos productos o generar contenido con IA, use los filtros para localizar rápidamente estos productos.
  2. Seleccione todos los productos relevantes usando las casillas de verificación.
  3. Use la acción masiva "Marcar como generado por IA" para aplicar la bandera.
  4. Revise periódicamente los productos para asegurarse de que su estado de la Ley de IA sea preciso.

#### 2.2.2 Ley de IA > Registros de auditoría (AdminMyAiActLogsController)

- **Nombre de la pantalla y ubicación del menú:** En su Back Office de PrestaShop, navegue a **Ley de IA > Registros de auditoría**.
- **Acciones y configuraciones disponibles:** Esta pantalla muestra un registro detallado de todos los eventos y divulgaciones relacionados con la Ley de IA, siempre que la configuración "Habilitar registro de auditoría" esté activa.
  - **Entradas de registro:** Cada entrada suele incluir:
    - **Marca de tiempo:** Cuándo ocurrió el evento.
    - **Acción/Evento:** Qué sucedió (por ejemplo, "Producto X marcado como IA", "Insignia de IA mostrada para el Producto Y").
    - **Usuario/Sistema:** Quién inició la acción (por ejemplo, "Usuario administrador Z", "Tarea CRON", "Visitante del Front Office").
    - **ID de producto/Contexto:** Qué producto o entidad se vio afectada.
    - **Detalles:** Cualquier información relevante adicional.
  - **Filtros y búsqueda:** Le permite filtrar las entradas del registro por rango de fechas, tipo de evento o producto para investigar incidentes específicos.
- **Efecto de los cambios:** Esta pantalla es solo para visualización; no puede realizar cambios directamente aquí. Sirve como un registro histórico.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Revise regularmente los registros de auditoría, especialmente después de realizar cambios significativos en la configuración de la Ley de IA o en los datos del producto, para asegurarse de que todo funciona como se espera.
  2. En caso de una auditoría de cumplimiento o una consulta del cliente, use este registro para recuperar eventos de divulgación específicos.

#### 2.2.3 Ley de IA > Estudio de Diseño (AdminMyAiActLayoutsController - *Inferido de plantillas y descripción*)

- **Nombre de la pantalla y ubicación del menú:** En su Back Office de PrestaShop, navegue a **Ley de IA > Estudio de Diseño** (o similar, según la estructura del menú del módulo).
- **Acciones y configuraciones disponibles:** Esta pantalla es donde diseña y gestiona la apariencia visual de sus insignias de divulgación de IA y otros elementos.
  - **Lista de diseños:** Una tabla que muestra todos los diseños de insignias existentes.
  - **Añadir nuevo diseño / Editar diseño:**
    - **Nombre del diseño:** Un nombre descriptivo para su diseño.
    - **Tipo de insignia:** Elija entre solo icono, solo texto o icono + texto.
    - **Selector de iconos:** Seleccione de un catálogo de iconos o suba el suyo propio.
    - **Contenido de texto:** Introduzca el texto a mostrar en la insignia (por ejemplo, "Generado por IA").
    - **Opciones de estilo:**
      - **Colores:** Color de fondo, color de texto, color de icono.
      - **Bordes:** Estilo de borde, ancho, color.
      - **Sombras:** Efectos de sombra.
      - **Degradados:** Opciones de degradado de fondo.
      - **Relleno y márgenes:** Espaciado alrededor de la insignia.
      - **Configuración de fuente:** Tamaño de fuente, peso.
    - **Vista previa:** Una vista previa en vivo de su insignia mientras la diseña.
- **Efecto de los cambios:**
  - La creación de nuevos diseños le brinda más opciones sobre cómo se ven sus divulgaciones de IA.
  - La edición de un diseño existente actualizará inmediatamente la apariencia de todas las insignias que utilizan ese diseño en su tienda.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Comience con un diseño predeterminado y personalícelo para que coincida con la estética de su marca.
  2. Cree diferentes diseños para diferentes tipos de divulgaciones de IA si es necesario (por ejemplo, uno para imágenes de IA, otro para texto de IA).
  3. Pruebe los diseños en varios dispositivos para asegurarse de que sean visibles y se vean bien.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | Habilitar cumplimiento de la Ley de IA | SÍ | Interruptor maestro para todas las funciones del módulo. |
|  | Mostrar insignia de divulgación de IA en páginas de productos | SÍ | Muestra la insignia en las páginas de detalles del producto. |
|  | Mostrar insignia de divulgación de IA en listados de productos | SÍ | Muestra la insignia en las páginas de categoría/búsqueda. |
|  | Posición de la insignia de divulgación de IA (página de producto) | *Depende del tema* | Controla la ubicación de la insignia en las páginas de productos. |
|  | Diseño de la insignia de divulgación de IA | *Personalizable* | Estilo visual de la insignia de IA. |
|  | Enlace a la página de política de IA | *URL de su página CMS* | Enlace a la política de IA de su tienda. |
|  | Habilitar banner de divulgación de IA | SÍ | Activa un banner informativo en todo el sitio. |
|  | Posición del banner de divulgación de IA (Hook) | `displayHeader` | Ubicación del banner (por ejemplo, parte superior/inferior de la página). |
|  | Contenido del banner de divulgación de IA | *Texto/HTML personalizable* | Mensaje mostrado en el banner. |
|  | Habilitar información de respaldo humano | SÍ | Muestra un mensaje sobre la supervisión humana. |
|  | Mensaje de respaldo humano | *Texto personalizable* | Contenido del mensaje de respaldo humano. |
|  | Habilitar registro de auditoría | SÍ | Registra todas las acciones relacionadas con la Ley de IA para el cumplimiento. |
|  | Habilitar API REST | NO | Activa la API para integraciones externas. |
|  | Gestión de claves API | *N/A* | Generar/gestionar claves API para un acceso seguro. |
|  | Habilitar CRON de marca de agua | NO | Marca de agua automáticamente las imágenes generadas por IA. |
|  | Imagen/Texto de marca de agua | *N/A* | Define el contenido de la marca de agua. |
|  | Lista y uso de shortcodes | *N/A* | Proporciona shortcodes para la divulgación granular de contenido. |
| **Ley de IA > Gestión masiva de productos** | Marcar como generado por IA (acción masiva) | N/A | Marca varios productos como generados por IA. |
|  | Desmarcar como generado por IA (acción masiva) | N/A | Elimina la bandera de generado por IA de los productos. |
|  | Aplicar etiquetas específicas de la Ley de IA (acción masiva) | N/A | Asigna etiquetas de divulgación personalizadas a los productos. |
| **Ley de IA > Registros de auditoría** | Ver entradas de registro | N/A | Proporciona un registro histórico de los eventos de la Ley de IA. |
| **Ley de IA > Estudio de Diseño** | Crear/Editar diseños | N/A | Diseñar estilos visuales personalizados para insignias de IA. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He configurado el módulo, pero no veo ninguna insignia o banner de IA en mi tienda. ¿Qué pasa?**
R1:

- **Verifique el interruptor maestro:** Primero, asegúrese de que "Habilitar cumplimiento de la Ley de IA" esté configurado en SÍ en la configuración principal del módulo.
- **Interruptores de funciones individuales:** Verifique que "Mostrar insignia de divulgación de IA en las páginas de productos", "Mostrar insignia de divulgación de IA en los listados de productos" y "Habilitar banner de divulgación de IA" también estén configurados en SÍ si desea que esas funciones estén activas.
- **Estado del producto:** Para que aparezcan las insignias, los productos deben estar explícitamente marcados como "generados por IA". Verifique esto en la página de edición del producto (en una pestaña dedicada) o a través de "Ley de IA > Gestión masiva de productos".
- **Caché:** Borre la caché de su PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché) y la caché de su navegador. A veces, se muestra contenido antiguo.
- **Compatibilidad con el tema:** Si bien el módulo está diseñado para ser compatible, algunos temas altamente personalizados pueden requerir pequeños ajustes. Verifique la consola de desarrollador de su navegador en busca de errores de JavaScript.

**P2: La insignia de IA aparece, pero no se ve bien con el diseño de mi tema. ¿Cómo puedo cambiar su apariencia?**
R2:

- **Estudio de Diseño:** Navegue a **Ley de IA > Estudio de Diseño** en su Back Office. Aquí puede crear y editar diseños de insignias. Tiene amplias opciones de colores, iconos, texto, sombras y degradados.
- **Seleccionar diseño:** Después de crear o editar un diseño, vuelva a la configuración principal del módulo y seleccione el diseño deseado en "Diseño de la insignia de divulgación de IA".
- **Sobreescrituras CSS (Avanzado):** Si el Estudio de Diseño no ofrece suficiente personalización, un webmaster puede usar CSS personalizado en su tema para anular los estilos predeterminados del módulo (consulte la Sección 7.5 para conocer las ubicaciones de los archivos CSS).

**P3: ¿Cómo marco los productos como generados por IA de manera eficiente, especialmente si tengo muchos?**
R3:

- **Gestión masiva de productos:** Vaya a **Ley de IA > Gestión masiva de productos**. Esta pantalla le permite filtrar sus productos y seleccionar varios elementos para marcarlos o desmarcarlos como generados por IA de una sola vez. Este es el método más eficiente para catálogos grandes.
- **Página de producto individual:** Para productos individuales, encontrará una pestaña dedicada (por ejemplo, "Cumplimiento de la Ley de IA") al editar un producto en el Back Office, donde puede alternar su estado de IA.

**P4: Quiero proporcionar una explicación detallada de mi política de IA. ¿Dónde debo ponerla?**
R4:

- **Página CMS dedicada:** Cree una nueva página CMS (Diseño > Páginas) titulada algo como "Nuestra política de transparencia de IA" o "Cómo usamos la IA". Escriba su política completa aquí.
- **Enlace en el módulo:** En la configuración principal del módulo, establezca el "Enlace a la página de política de IA" en la URL de su página CMS recién creada. Este enlace será utilizado por banners e insignias para dirigir a los clientes a su política.

**P5: La tarea CRON para la marca de agua no funciona. ¿Qué debo verificar?**
R5:

- **Habilitar CRON de marca de agua:** Asegúrese de que "Habilitar CRON de marca de agua" esté configurado en SÍ en la configuración del módulo.
- **Configuración de la tarea CRON:** Verifique que la tarea CRON en sí esté configurada correctamente en su servidor. El módulo generalmente proporciona la línea de comando exacta para agregar al administrador de CRON de su panel de alojamiento. Si no está seguro, comuníquese con su proveedor de alojamiento o un webmaster.
- **Permisos:** Asegúrese de que el módulo y las carpetas de imágenes tengan los permisos de escritura correctos.
- **Registros de errores:** Verifique los registros de errores de PHP de su servidor y el modo de depuración de PrestaShop en busca de errores relacionados.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura

El módulo "My AI Act Pro" sigue la arquitectura MVC (Modelo-Vista-Controlador) estándar de PrestaShop. Aprovecha `ObjectModel` para las interacciones con la base de datos, registra varios hooks para la visualización en el front-office e incluye controladores de administración dedicados para la configuración y la gestión de datos. El módulo introduce varias clases personalizadas para encapsular la lógica de negocio específica relacionada con el cumplimiento de la Ley de IA, como el manejo de la API, la gestión del diseño de insignias y el registro de auditorías. También incluye controladores frontales para la ejecución de la API y las tareas CRON, lo que permite integraciones externas y tareas programadas.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

- `controllers/front/api.php`
  - **Nombre de la clase y clase padre:** `MyaiactproApiModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador maneja los endpoints de la API REST del módulo. Procesa las solicitudes entrantes (por ejemplo, para marcar productos como generados por IA, recuperar el estado de IA) y devuelve respuestas JSON. Es responsable de la validación de la clave API y de enviar las solicitudes a los métodos apropiados de la clase `AiActApi`.
- `controllers/front/cron.php`
  - **Nombre de la clase y clase padre:** `MyaiactproCronModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador sirve como endpoint para las tareas CRON del módulo, específicamente para la aplicación de marcas de agua. Cuando se accede a través de una tarea programada, activa el proceso de marca de agua para las imágenes generadas por IA.
- `controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `MyaiactproIndexModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Un controlador frontal de marcador de posición o predeterminado. En muchos módulos, esto podría manejar una ruta predeterminada o una redirección. Para este módulo, podría ser una alternativa o usarse para interacciones front-office específicas y simples no cubiertas por `api.php` o `cron.php`.

#### Controladores de administración del Back-Office

- `controllers/admin/AdminMyAiActBulkController.php`
  - **Nombre de la clase y clase padre:** `AdminMyAiActBulkController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Accesible a través de **Ley de IA > Gestión masiva de productos**. Gestiona la entidad `product` indirectamente al permitir actualizaciones masivas de su estado de la Ley de IA.
  - **Responsabilidad:** Proporciona una interfaz de cuadrícula para listar productos y aplicar acciones masivas relacionadas con el cumplimiento de la Ley de IA (por ejemplo, marcar productos como generados por IA, aplicar etiquetas). Maneja el envío de formularios para actualizaciones masivas.
- `controllers/admin/AdminMyAiActLogsController.php`
  - **Nombre de la clase y clase padre:** `AdminMyAiActLogsController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Accesible a través de **Ley de IA > Registros de auditoría**. Gestiona la entidad `aiact_audit_log`.
  - **Responsabilidad:** Muestra una lista paginada de entradas del registro de auditoría, proporcionando un registro histórico de los eventos relacionados con la Ley de IA. Maneja el filtrado y la visualización de los detalles del registro.
- `controllers/admin/index.php`
  - **Nombre de la clase y clase padre:** `MyaiactproAdminIndexModuleAdminController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Normalmente un controlador de administración predeterminado o introductorio para la entrada del menú principal del módulo.
  - **Responsabilidad:** Puede servir como una redirección a la configuración principal o a un panel de control para el módulo.

### 4.3 Clases y modelos principales (`classes/`)

- `classes/AiActApi.php`
  - **Tabla de base de datos:** No hay interacción directa con la tabla, pero interactúa con `AiActApiKey` y `AiActAuditLog`.
  - **Extiende `ObjectModel`:** No.
  - **Métodos públicos clave:** Maneja el análisis de solicitudes API, la autenticación y envía acciones para actualizar el estado de IA del producto.
- `classes/AiActApiDocumentation.php`
  - **Tabla de base de datos:** Ninguna.
  - **Extiende `ObjectModel`:** No.
  - **Métodos públicos clave:** Genera y proporciona documentación para la API REST del módulo, normalmente para su visualización en el Back Office.
- `classes/AiActApiKey.php`
  - **Tabla de base de datos:** `ps_myaiactpro_api_key`
  - **Extiende `ObjectModel`:** Sí.
  - **Campos `$definition`:** `id_myaiactpro_api_key`, `key_value`, `description`, `active`, `date_add`, `date_upd`.
  - **Métodos públicos clave:** Gestiona la creación, recuperación, validación y eliminación de claves API para un acceso seguro a la API.
- `classes/AiActAuditLog.php`
  - **Tabla de base de datos:** `ps_myaiactpro_audit_log`
  - **Extiende `ObjectModel`:** Sí.
  - **Campos `$definition`:** `id_myaiactpro_audit_log`, `id_employee`, `id_customer`, `id_product`, `action`, `details`, `ip_address`, `date_add`.
  - **Métodos públicos clave:** Registra y recupera entradas del registro de auditoría para acciones de cumplimiento de la Ley de IA.
- `classes/AiActBadgeLayout.php`
  - **Tabla de base de datos:** `ps_myaiactpro_badge_layout`
  - **Extiende `ObjectModel`:** Sí.
  - **Campos `$definition`:** `id_myaiactpro_badge_layout`, `name`, `type`, `icon_class`, `text_content`, `styles_json`, `active`.
  - **Métodos públicos clave:** Gestiona la creación, almacenamiento y recuperación de diseños visuales personalizados para insignias de divulgación de IA.
- `classes/AiActConfigureUi.php`
  - **Tabla de base de datos:** Ninguna.
  - **Extiende `ObjectModel`:** No.
  - **Métodos públicos clave:** Clase auxiliar para construir y renderizar los formularios de configuración del módulo en el Back Office, abstrayendo los elementos de la interfaz de usuario.
- `classes/AiActDisplayResolver.php`
  - **Tabla de base de datos:** Ninguna.
  - **Extiende `ObjectModel`:** No.
  - **Métodos públicos clave:** Determina qué divulgaciones de la Ley de IA (insignias, banners, etc.) deben mostrarse en el front office según la configuración del módulo, el estado del producto y el contexto actual.
- `classes/AiActFlag.php`
  - **Tabla de base de datos:** `ps_myaiactpro_product_flag` (o similar, que vincula productos al estado de IA)
  - **Extiende `ObjectModel`:** Sí (probablemente, o una clase personalizada que gestiona las relaciones de estado producto-IA).
  - **Campos `$definition`:** `id_product`, `is_ai_generated`, `id_myaiactpro_badge_layout`, `date_add`, `date_upd`.
  - **Métodos públicos clave:** Gestiona el estado generado por IA de productos individuales y sus diseños de insignias asociados.
- `classes/AiActIconCatalog.php`
  - **Tabla de base de datos:** Ninguna.
  - **Extiende `ObjectModel`:** No.
  - **Métodos públicos clave:** Proporciona una lista o catálogo de iconos disponibles para usar en diseños de insignias, a menudo integrándose con Font Awesome o bibliotecas de iconos similares.
- `classes/AiActShortcode.php`
  - **Tabla de base de datos:** Ninguna.
  - **Extiende `ObjectModel`:** No.
  - **Métodos públicos clave:** Procesa y renderiza shortcodes personalizados incrustados en el contenido, reemplazándolos con elementos de divulgación de IA.
- `classes/AiActTagRule.php`
  - **Tabla de base de datos:** `ps_myaiactpro_tag_rule` (o similar para etiquetas/reglas personalizadas)
  - **Extiende `ObjectModel`:** Sí.
  - **Campos `$definition`:** `id_myaiactpro_tag_rule`, `name`, `description`, `badge_layout_id`, `active`.
  - **Métodos públicos clave:** Gestiona reglas o etiquetas personalizadas que se pueden aplicar a productos para divulgaciones de IA más específicas más allá de una simple bandera de "generado por IA".
- `classes/index.php`
  - **Tabla de base de datos:** Ninguna.
  - **Extiende `ObjectModel`:** No.
  - **Métodos públicos clave:** Normalmente un archivo vacío para evitar el listado de directorios.

### 4.4 Activos JavaScript (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office (probablemente para la búsqueda de productos en la gestión masiva).
  - **Descripción:** Proporciona funcionalidad de autocompletado para campos de entrada, típicamente utilizada en formularios de administración para buscar productos, categorías u otras entidades.
- `views/js/admin_api.js`
  - **Alcance:** Back-office (pestaña API e Integraciones).
  - **Descripción:** Maneja las interacciones del lado del cliente para la interfaz de gestión de claves API, incluida la generación de nuevas claves, la revocación de claves y la visualización de modales de documentación de la API.
- `views/js/admin_icon_picker.js`
  - **Alcance:** Back-office (Estudio de Diseño).
  - **Descripción:** Gestiona la interfaz de selección de iconos dentro del Estudio de Diseño, permitiendo a los administradores buscar y seleccionar iconos para insignias.
- `views/js/admin_layouts.js`
  - **Alcance:** Back-office (Estudio de Diseño).
  - **Descripción:** Impulsa la interfaz del Estudio de Diseño, manejando las actualizaciones de vista previa en tiempo real, los ajustes de estilo (colores, sombras, degradados) y el envío de formularios para los diseños de insignias.
- `views/js/front.js`
  - **Alcance:** Front-office.
  - **Descripción:** Contiene la lógica del lado del cliente para mostrar e interactuar con los elementos de divulgación de IA en el front office. Esto podría incluir:
    - Inicialización de tooltips o popovers de insignias.
    - Manejo de eventos de clic en insignias para revelar más información o navegar a la página de política de IA.
    - Asegurar la adaptabilidad móvil de los elementos de divulgación.
- `views/js/tinymce_ai_button.js`
  - **Alcance:** Back-office (editor de productos/CMS).
  - **Descripción:** Integra un botón personalizado en el editor TinyMCE (utilizado para descripciones de productos y páginas CMS) para insertar fácilmente shortcodes de la Ley de IA.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back-office.
  - **Descripción:** Estilos para los campos de entrada de búsqueda de autocompletado y sus resultados desplegables, utilizados en formularios de administración.
- `views/css/admin.css`
  - **Alcance:** Estilo de formularios de administración del Back-office.
  - **Descripción:** Contiene reglas de estilo generales para las interfaces del Back Office del módulo, incluida la página de configuración, la gestión masiva, los registros de auditoría y el estudio de diseño. Los desarrolladores pueden anular clases como `.myaiactpro-admin-form`, `.myaiactpro-layout-preview`, etc.
- `views/css/front.css`
  - **Alcance:** Estilo del cliente del Front-office.
  - **Descripción:** Proporciona el estilo predeterminado para las insignias de divulgación de IA, los banners y otros elementos del front-office. Los selectores de clase CSS clave que los desarrolladores pueden anular en su tema incluyen:
    - `.myaiactpro-badge` (para el contenedor principal de la insignia)
    - `.myaiactpro-badge-icon` (para el icono dentro de la insignia)
    - `.myaiactpro-badge-text` (para el texto dentro de la insignia)
    - `.myaiactpro-banner` (para el banner de divulgación en todo el sitio)
    - `.myaiactpro-additional-info` (para bloques de información adicional)
    - `.myaiactpro-human-fallback` (para mensajes de respaldo humano)

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

- `hook/additional_info.tpl`
  - **Hook:** Potencialmente `displayProductExtraContent` o hook personalizado.
  - **Salida:** Renderiza un bloque de información adicional en la página del producto, a menudo utilizado para divulgaciones detalladas de IA o enlaces a políticas.
- `hook/ai_badge.tpl`
  - **Hook:** `displayProductListReviews`, `displayProductButtons`, `displayProductPriceBlock` o hooks personalizados.
  - **Salida:** Renderiza la insignia de divulgación de IA en las páginas o listados de productos, utilizando el diseño seleccionado.
- `hook/banner.tpl`
  - **Hook:** `displayHeader`, `displayFooter`.
  - **Salida:** Renderiza el banner de divulgación de IA en todo el sitio.
- `hook/human_fallback.tpl`
  - **Hook:** Potencialmente `displayProductExtraContent` o hook personalizado.
  - **Salida:** Renderiza el mensaje de respaldo humano en las páginas relevantes.
- `hook/shortcode_badge.tpl`
  - **Hook:** Renderizado dinámicamente por la clase `AiActShortcode`.
  - **Salida:** Renderiza una insignia de IA específica cuando se utiliza un shortcode en el contenido.

#### Plantillas de administración (`views/templates/admin/`)

- `admin/api.tpl`
  - **Propósito:** Renderiza el panel de configuración de API e Integraciones, incluida la gestión de claves API y la documentación.
- `admin/bulk_intro.tpl`
  - **Propósito:** Proporciona un mensaje introductorio o instrucciones para la pantalla de gestión masiva de productos.
- `admin/configure.tpl`
  - **Propósito:** La plantilla de configuración principal para el módulo, renderizada por `getContent()`, que contiene configuraciones generales, alternadores de funciones y enlaces a otras pantallas de administración.
- `admin/configure_shell.tpl`
  - **Propósito:** Una plantilla de envoltura o shell para la página de configuración principal, que proporciona un diseño consistente.
- `admin/cron_box.tpl`
  - **Propósito:** Muestra información relacionada con la configuración de la tarea CRON, incluido el comando CRON.
- `admin/layouts_form.tpl`
  - **Propósito:** Renderiza el formulario para crear o editar un diseño de insignia de IA dentro del Estudio de Diseño.
- `admin/layouts_list.tpl`
  - **Propósito:** Muestra la lista de diseños de insignias de IA existentes en el Estudio de Diseño.
- `admin/mass_settings.tpl`
  - **Propósito:** Renderiza la interfaz para aplicar configuraciones o acciones masivas a los productos, utilizada en el controlador de gestión masiva.
- `admin/overrides_entity.tpl`
  - **Propósito:** Probablemente para gestionar anulaciones o excepciones específicas para las reglas de la Ley de IA por entidad (por ejemplo, por categoría, por fabricante).
- `admin/overrides_fields.tpl`
  - **Propósito:** Renderiza campos de formulario para definir reglas de anulación.
- `admin/overrides_list.tpl`
  - **Propósito:** Muestra una lista de reglas de anulación configuradas.
- `admin/partials/gradient_editor.tpl`
  - **Propósito:** Una plantilla parcial para el selector/editor de color degradado utilizado en el Estudio de Diseño.
- `admin/partials/icon_picker.tpl`
  - **Propósito:** Una plantilla parcial para la interfaz de selección de iconos utilizada en el Estudio de Diseño.
- `admin/partials/shadow_editor.tpl`
  - **Propósito:** Una plantilla parcial para el editor de efectos de sombra utilizado en el Estudio de Diseño.
- `admin/product_tab.tpl`
  - **Propósito:** Renderiza el contenido de la pestaña dedicada "Cumplimiento de la Ley de IA" dentro de la página de edición de productos de PrestaShop.
- `admin/shortcodes.tpl`
  - **Propósito:** Muestra la lista de shortcodes disponibles y sus instrucciones de uso.
- `admin/_api_documentation_modal.tpl`
  - **Propósito:** Renderiza el contenido para una ventana emergente modal que muestra la documentación de la API.

#### Plantillas del Front-office (`views/templates/front/`)

- Ninguna listada explícitamente como plantillas de página independientes, lo que indica que el contenido del front-office se renderiza principalmente a través de hooks.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

- `ps_myaiactpro_api_key`: Almacena las claves API para la API REST del módulo.
  - `id_myaiactpro_api_key` (PK)
  - `key_value` (VARCHAR)
  - `description` (TEXT)
  - `active` (TINYINT)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_myaiactpro_audit_log`: Registra los eventos relacionados con la Ley de IA.
  - `id_myaiactpro_audit_log` (PK)
  - `id_employee` (INT)
  - `id_customer` (INT)
  - `id_product` (INT)
  - `action` (VARCHAR)
  - `details` (TEXT)
  - `ip_address` (VARCHAR)
  - `date_add` (DATETIME)
- `ps_myaiactpro_badge_layout`: Almacena diseños visuales personalizados para insignias de IA.
  - `id_myaiactpro_badge_layout` (PK)
  - `name` (VARCHAR)
  - `type` (VARCHAR)
  - `icon_class` (VARCHAR)
  - `text_content` (VARCHAR)
  - `styles_json` (TEXT)
  - `active` (TINYINT)
- `ps_myaiactpro_product_flag`: Vincula los productos a su estado generado por IA y al diseño de insignia elegido.
  - `id_product` (PK, INT)
  - `is_ai_generated` (TINYINT)
  - `id_myaiactpro_badge_layout` (INT, FK a `ps_myaiactpro_badge_layout`)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_myaiactpro_tag_rule`: Almacena reglas de etiquetas personalizadas de la Ley de IA.
  - `id_myaiactpro_tag_rule` (PK)
  - `name` (VARCHAR)
  - `description` (TEXT)
  - `badge_layout_id` (INT, FK a `ps_myaiactpro_badge_layout`)
  - `active` (TINYINT)
- Registros de configuración en `ps_configuration`: La configuración del módulo se almacena aquí (por ejemplo, `MYAIACTPRO_ENABLED`, `MYAIACTPRO_BADGE_LAYOUT_ID`, `MYAIACTPRO_POLICY_LINK`).

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico | Plantillas renderizadas |
| --- | --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyectar CSS/JS, renderizar banner superior. | `hook/banner.tpl` (si está configurado) |
| `displayFooter` | En la parte inferior de cada página. | Renderizar banner inferior, inyectar JS. | `hook/banner.tpl` (si está configurado) |
| `displayProductAdditionalInfo` | En la página del producto, generalmente debajo de la descripción. | Mostrar información adicional de divulgación de IA. | `hook/additional_info.tpl`, `hook/human_fallback.tpl` |
| `displayProductListReviews` | En los listados de productos, cerca del nombre/imagen del producto. | Mostrar insignia de IA en las miniaturas de los productos. | `hook/ai_badge.tpl` |
| `displayProductButtons` | En la página del producto, cerca del botón añadir al carrito. | Mostrar insignia de IA en la página del producto. | `hook/ai_badge.tpl` |
| `displayAdminProductsExtra` | En la página de edición de productos del Back Office. | Añadir una pestaña dedicada para la configuración de la Ley de IA. | `admin/product_tab.tpl` |
| `actionProductUpdate` | Después de que un producto se actualiza en el Back Office. | Actualizar las banderas/estado de la Ley de IA para el producto. | N/A |
| `actionProductDelete` | Después de que un producto se elimina. | Limpiar los datos asociados de la Ley de IA. | N/A |
| `actionFrontControllerSetMedia` | Antes de que el controlador frontal renderice el contenido. | Registrar CSS/JS del front-office. | N/A |
| `actionAdminControllerSetMedia` | Antes de que el controlador de administración renderice el contenido. | Registrar CSS/JS del back-office. | N/A |
| `actionRegisterShortcode` | En la instalación/actualización del módulo. | Registra shortcodes personalizados para el análisis de contenido. | N/A |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página de administración. | Inyectar CSS/JS de administración. | N/A |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con el módulo "My AI Act Pro - Cumplimiento de la Ley de IA".

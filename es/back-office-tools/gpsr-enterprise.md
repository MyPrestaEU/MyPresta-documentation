---
title: "GPSR Enterprise - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo GPSR Enterprise para PrestaShop de MyPresta.eu."
sidebar:
  label: "GPSR Enterprise"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo GPSR Enterprise en MyPresta.eu](https://mypresta.eu/modules/administration-tools/gpsr-enterprise.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/gpsr-enterprise/)
>
> ---


# GPSR Enterprise

## 1. Requisitos y Compatibilidad

*   **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
*   **Compatibilidad PHP**: PHP 7.1 - 8.5
*   **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL) y suelen estar disponibles en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

El módulo GPSR Enterprise ofrece un conjunto completo de opciones de configuración, distribuidas en su página de configuración principal y varias pantallas de administración dedicadas.

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Gestor de Módulos > GPSR Enterprise > Configurar)

Esta es la pantalla de configuración principal del módulo, donde controla su comportamiento general y la visualización en el front-office.

*   **Módulo activado**
    *   **Qué hace este ajuste:** Este es el interruptor maestro para todo el módulo GPSR Enterprise.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está activado (Sí):* El módulo estará activo, mostrando información GPSR en las páginas de producto, permitiéndole gestionar entidades, advertencias y mapeos, y habilitando la API y las tareas programadas (cron jobs).
        *   *Cuando está desactivado (No):* El módulo estará completamente inactivo. No se mostrará información GPSR en el front office, y las funciones de gestión del backend no estarán disponibles o no funcionarán.
    *   **Valor recomendado:** **Sí** (para utilizar las características del módulo).
    *   **Escenario / ejemplo del comerciante:** Si está configurando el módulo por primera vez, manténgalo desactivado hasta que todas las configuraciones estén completas, luego actívelo para que esté en vivo.

*   **Perfil de tema de la tienda**
    *   **Qué hace este ajuste:** Le permite seleccionar el perfil de estilo visual para el bloque de información GPSR en sus páginas de producto, optimizado para diferentes temas de PrestaShop.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando se establece en 'Classic':* El módulo utilizará un estilo optimizado para el tema Classic predeterminado de PrestaShop (y muchos temas compatibles).
        *   *Cuando se establece en 'Hummingbird':* El módulo utilizará un estilo optimizado para el tema Hummingbird más reciente de PrestaShop (PrestaShop 8.1+).
    *   **Valor recomendado:** Seleccione el perfil que mejor se adapte a su tema actual de PrestaShop. Si no está seguro, pruebe 'Classic' primero.
    *   **Escenario / ejemplo del comerciante:** Si su tienda utiliza PrestaShop 8.1+ con el tema predeterminado, elija 'Hummingbird' para la mejor integración visual. Si está en PrestaShop 1.7 u 8.0 con el tema Classic, elija 'Classic'.

*   **Modo de visualización**
    *   **Qué hace este ajuste:** Controla cómo se presenta el bloque de información GPSR en la página del producto.
    *   **Efecto de cambiar este ajuste:**
        *   *Las opciones varían (por ejemplo, 'Pestaña', 'Acordeón', 'Bloque'):*
            *   **Pestaña:** La información GPSR aparecerá como una nueva pestaña junto a "Descripción", "Detalles del producto", etc.
            *   **Acordeón:** La información se presentará en una sección de acordeón expandible/colapsable.
            *   **Bloque:** La información se mostrará como un bloque estático dentro del flujo de contenido de la página del producto.
    *   **Valor recomendado:** **Pestaña** o **Acordeón** para un diseño de página de producto más limpio, especialmente si tiene mucha información.
    *   **Escenario / ejemplo del comerciante:** Si sus páginas de producto ya son muy largas, usar un modo 'Pestaña' o 'Acordeón' mantiene la página ordenada al mismo tiempo que hace que la información sea accesible.

*   **Estilo visual**
    *   **Qué hace este ajuste:** Define la estética general del bloque de información GPSR.
    *   **Efecto de cambiar este ajuste:**
        *   *Las opciones varían (por ejemplo, 'Predeterminado', 'Minimalista', 'Detallado'):* Esto cambiará la densidad visual, el uso de iconos y la presentación general de la información.
    *   **Valor recomendado:** **Predeterminado** o **Minimalista** para un aspecto limpio. Experimente para ver qué se adapta mejor a su tema.
    *   **Escenario / ejemplo del comerciante:** Si su tema es muy minimalista, elegir un estilo visual 'Minimalista' para el bloque GPSR asegurará una mejor integración.

*   **Mostrar título del bloque**
    *   **Qué hace este ajuste:** Determina si se muestra un título encima del bloque de información GPSR en la página del producto.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está activado (Sí):* El texto especificado en "Texto del título del bloque" aparecerá como un encabezado.
        *   *Cuando está desactivado (No):* No se mostrará ningún título, haciendo que el bloque se integre más fluidamente o dependa del contexto.
    *   **Valor recomendado:** **Sí** para mayor claridad, para que los clientes entiendan inmediatamente qué contiene el bloque.
    *   **Escenario / ejemplo del comerciante:** Habilitar esto con un título como "Información de Seguridad del Producto" deja claro a los clientes lo que están viendo.

*   **Texto del título del bloque**
    *   **Qué hace este ajuste:** Le permite personalizar el título del bloque de información GPSR. Este ajuste solo se aplica si "Mostrar título del bloque" está activado.
    *   **Efecto de cambiar este ajuste:** El texto que introduzca aquí se mostrará como el encabezado del bloque de información GPSR en la página del producto.
    *   **Valor recomendado:** Un título claro y descriptivo como "Seguridad y Cumplimiento del Producto", "Información de Seguridad de la UE" o "Detalles del Pasaporte del Producto".
    *   **Escenario / ejemplo del comerciante:** Puede establecer esto en "Información de Seguridad del Producto de la UE" para comunicar claramente el propósito del bloque a sus clientes europeos.

*   **Ocultar bloque cuando los datos están incompletos**
    *   **Qué hace este ajuste:** Controla si el bloque de información GPSR se muestra en la página del producto si no se han configurado completamente todos los datos requeridos (fabricante, persona responsable en la UE, advertencias, documentos) para ese producto.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está activado (Sí):* Si falta algún dato GPSR para un producto, el bloque completo no se mostrará en el front office. Esto evita mostrar información incompleta o engañosa.
        *   *Cuando está desactivado (No):* El bloque siempre se mostrará, incluso si algunas secciones están vacías. Esto podría mostrar un bloque parcialmente lleno, lo que podría ser confuso.
    *   **Valor recomendado:** **Sí** para mantener una apariencia profesional y evitar mostrar secciones a medio llenar.
    *   **Escenario / ejemplo del comerciante:** Todavía está en proceso de añadir datos GPSR a todos sus productos. Habilitar esto asegura que solo las páginas de productos totalmente conformes muestren el bloque, evitando la confusión del cliente en productos que aún se están actualizando.

*   **Mostrar entidad fabricante**
    *   **Qué hace este ajuste:** Determina si los detalles de la entidad GPSR del fabricante se muestran en el bloque del front-office.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está activado (Sí):* El nombre, la dirección y otros detalles configurados del fabricante serán visibles.
        *   *Cuando está desactivado (No):* La sección del fabricante estará oculta.
    *   **Valor recomendado:** **Sí**, ya que este es un requisito central del GPSR.
    *   **Escenario / ejemplo del comerciante:** Para cumplir plenamente con el GPSR, debe mostrar los detalles del fabricante. Mantenga esto activado.

*   **Mostrar persona responsable en la UE**
    *   **Qué hace este ajuste:** Determina si los detalles de la entidad GPSR de la persona responsable en la UE se muestran en el bloque del front-office.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está activado (Sí):* El nombre, la dirección y otros detalles configurados de la persona responsable en la UE serán visibles.
        *   *Cuando está desactivado (No):* La sección de la persona responsable en la UE estará oculta.
    *   **Valor recomendado:** **Sí**, ya que este es un requisito central del GPSR para productos vendidos en la UE.
    *   **Escenario / ejemplo del comerciante:** Si sus productos requieren una persona responsable en la UE, habilitar esto asegura que sus detalles se muestren.

*   **Mostrar advertencias de seguridad**
    *   **Qué hace este ajuste:** Determina si se muestran las advertencias de seguridad asociadas en el bloque del front-office.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está activado (Sí):* Las advertencias de seguridad configuradas para el producto serán visibles.
        *   *Cuando está desactivado (No):* La sección de advertencias de seguridad estará oculta.
    *   **Valor recomendado:** **Sí** para informar a los clientes de posibles peligros.
    *   **Escenario / ejemplo del comerciante:** Para productos con instrucciones de seguridad específicas (por ejemplo, "Mantener fuera del alcance de los niños"), habilitar esto asegura que estas advertencias se muestren de manera prominente.

*   **Mostrar documentos vinculados**
    *   **Qué hace este ajuste:** Determina si se muestran enlaces a documentos asociados (como manuales, declaraciones) en el bloque del front-office.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está activado (Sí):* Los enlaces a los documentos subidos serán visibles.
        *   *Cuando está desactivado (No):* La sección de documentos vinculados estará oculta.
    *   **Valor recomendado:** **Sí** para proporcionar a los clientes la documentación esencial del producto.
    *   **Escenario / ejemplo del comerciante:** Si necesita proporcionar una "Declaración de Conformidad" o un manual de usuario detallado, habilitar esto permite a los clientes acceder fácilmente a estos archivos.

*   **Mostrar botón de pasaporte de producto**
    *   **Qué hace este ajuste:** Controla la visibilidad del botón "Descargar Pasaporte de Producto" en la página del producto.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está activado (Sí):* Aparecerá un botón que permitirá a los clientes descargar un PDF que contiene toda la información GPSR del producto.
        *   *Cuando está desactivado (No):* El botón no se mostrará.
    *   **Valor recomendado:** **Sí**, ya que el pasaporte de producto es una característica clave del GPSR.
    *   **Escenario / ejemplo del comerciante:** Para ofrecer a los clientes un resumen completo y descargable de toda la información de seguridad y cumplimiento, mantenga esto activado.

*   **Compartir mapeos entre todas las tiendas**
    *   **Qué hace este ajuste:** (Solo visible en una configuración multi-tienda) Determina si los mapeos GPSR (cómo se asignan entidades, advertencias y documentos a productos, categorías o fabricantes) se comparten entre todas sus tiendas PrestaShop.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está activado (Sí):* Todos los mapeos GPSR que cree se aplicarán a todas las tiendas en su entorno multi-tienda. Esto simplifica la gestión si su catálogo de productos y las necesidades de cumplimiento son similares en todas las tiendas.
        *   *Cuando está desactivado (No):* Cada tienda tendrá su propio conjunto independiente de mapeos GPSR, lo que permite configuraciones de cumplimiento específicas para cada tienda.
    *   **Valor recomendado:** **Sí** si sus necesidades de cumplimiento son consistentes en todas las tiendas; de lo contrario, **No**.
    *   **Escenario / ejemplo del comerciante:** Si tiene varias tiendas específicas para cada país pero vende los mismos productos con los mismos requisitos de cumplimiento, habilitar esto ahorra mucho tiempo al gestionar los mapeos una sola vez.

*   **Acción al habilitar compartir**
    *   **Qué hace este ajuste:** (Solo visible en una configuración multi-tienda, aparece cuando "Compartir mapeos entre todas las tiendas" está activado) Define qué sucede con los mapeos existentes específicos de la tienda cuando se cambia a mapeos compartidos.
    *   **Efecto de cambiar este ajuste:**
        *   *Las opciones varían (por ejemplo, 'Fusionar', 'Sobrescribir', 'Mantener tienda actual'):*
            *   **Fusionar:** Intenta combinar los mapeos existentes de todas las tiendas en un único conjunto compartido.
            *   **Sobrescribir:** Reemplaza todos los mapeos existentes específicos de la tienda con los mapeos de la tienda actualmente activa.
            *   **Mantener tienda actual:** Utiliza los mapeos de la tienda actualmente activa como los mapeos compartidos, descartando los demás.
    *   **Valor recomendado:** Elija con cuidado según sus datos. **¡Haga una copia de seguridad de su base de datos** antes de cambiar esto!
    *   **Escenario / ejemplo del comerciante:** Si ha estado gestionando datos GPSR por separado para cada tienda y ahora desea centralizar, deberá decidir si desea combinar todos los datos, o si los datos de una tienda deben convertirse en los maestros.

*   **Acción al deshabilitar compartir**
    *   **Qué hace este ajuste:** (Solo visible en una configuración multi-tienda, aparece cuando "Compartir mapeos entre todas las tiendas" está desactivado) Define qué sucede con los mapeos compartidos cuando se vuelve a los mapeos específicos de la tienda.
    *   **Efecto de cambiar este ajuste:**
        *   *Las opciones varían (por ejemplo, 'Duplicar en todas las tiendas', 'Mantener solo para la tienda actual'):*
            *   **Duplicar en todas las tiendas:** Los mapeos compartidos actuales se copian a cada tienda individual, permitiendo que se editen de forma independiente después.
            *   **Mantener solo para la tienda actual:** Los mapeos compartidos se asignan solo a la tienda actualmente activa, y las otras tiendas comenzarán sin mapeos GPSR.
    *   **Valor recomendado:** Elija con cuidado según sus datos. **¡Haga una copia de seguridad de su base de datos** antes de cambiar esto!
    *   **Escenario / ejemplo del comerciante:** Si decide pasar de mapeos compartidos a la gestión individual de la tienda, debe decidir si los datos compartidos deben copiarse a todas las tiendas como punto de partida, o si solo la tienda actual debe conservarlos.

*   **CSS personalizado**
    *   **Qué hace este ajuste:** Proporciona un área de texto donde puede añadir reglas CSS personalizadas para estilizar aún más el bloque de información GPSR en su tienda.
    *   **Efecto de cambiar este ajuste:** Cualquier código CSS válido introducido aquí se aplicará a los elementos del front-office del módulo GPSR, permitiéndole ajustar colores, fuentes, espaciado, etc., para que coincidan perfectamente con su tema.
    *   **Valor recomendado:** Dejar vacío a menos que tenga necesidades de estilo específicas y se sienta cómodo con CSS.
    *   **Escenario / ejemplo del comerciante:** Su tema utiliza un tono específico de azul para los encabezados. Puede añadir CSS aquí para asegurar que el título del bloque GPSR también utilice ese azul exacto, manteniendo la coherencia visual.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

El módulo GPSR Enterprise añade varios elementos de menú nuevos bajo un menú principal "GPSR Enterprise" en su Back Office de PrestaShop. Estas pantallas son donde gestiona todos los datos detallados de cumplimiento.

#### 2.2.1 Panel de Control de GPSR Enterprise (Back Office > GPSR Enterprise > Panel de Control)

Esta pantalla proporciona una visión general de su estado de cumplimiento GPSR y acceso rápido a las áreas clave de gestión.

*   **Acciones y Ajustes Disponibles:**
    *   **Estadísticas de Resumen:** Puede mostrar recuentos de entidades configuradas, advertencias, productos mapeados, etc.
    *   **Enlaces Rápidos:** Botones o enlaces para saltar directamente a la gestión de Entidades, Advertencias, Mapeos, Documentos, etc.
    *   **Estado de la Tarea Programada (Cron Job):** Información sobre la última ejecución y el resultado de la tarea programada GPSR (para reindexación o sincronización de datos).
    *   **Token de API:** Muestra su token de API único para integraciones externas.
    *   **Token de Cron:** Muestra su token de tarea programada único para una ejecución segura.
*   **Efecto de los cambios:** Esta pantalla es principalmente para monitoreo y navegación. Los cambios aquí (por ejemplo, generar nuevos tokens de API/Cron) impactan directamente la seguridad y funcionalidad de las integraciones externas y las tareas automatizadas.
*   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise este panel periódicamente para monitorear su estado de cumplimiento y asegurarse de que las tareas programadas se ejecuten correctamente.

#### 2.2.2 Entidades (Back Office > GPSR Enterprise > Entidades)

Esta pantalla es donde define y gestiona las "entidades" requeridas por el GPSR, como fabricantes y personas responsables en la UE.

*   **Acciones y Ajustes Disponibles:**
    *   **Lista de Entidades:** Una tabla que muestra todas las entidades configuradas, con columnas para nombre, tipo (Fabricante, Persona Responsable en la UE), dirección, contacto, etc.
    *   **Añadir Nueva Entidad:** Un botón para crear una nueva entidad.
    *   **Editar/Eliminar:** Acciones para cada entidad en la lista.
    *   **Formulario de Entidad:** Al añadir/editar, encontrará campos para:
        *   **Nombre:** El nombre oficial de la entidad.
        *   **Tipo:** Seleccione si es un Fabricante o una Persona Responsable en la UE.
        *   **Dirección:** Dirección postal completa.
        *   **Información de Contacto:** Correo electrónico, teléfono, sitio web.
        *   **Campos Multilingües:** Algunos campos pueden ser traducibles para diferentes idiomas.
*   **Efecto de los cambios:** Crear o actualizar entidades aquí las hace disponibles para su selección al mapear datos GPSR a productos. Los datos de entidad incorrectos o incompletos conducirán al incumplimiento.
*   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Antes de mapear productos, asegúrese de que todos sus fabricantes y personas responsables en la UE estén introducidos con precisión aquí. Actualice los detalles rápidamente si cambian.

#### 2.2.3 Advertencias (Back Office > GPSR Enterprise > Advertencias)

Esta pantalla le permite definir y gestionar varias advertencias de seguridad que se pueden asociar con sus productos.

*   **Acciones y Ajustes Disponibles:**
    *   **Lista de Advertencias:** Una tabla que muestra todas las advertencias creadas, con columnas para título, icono y contenido.
    *   **Añadir Nueva Advertencia:** Un botón para crear una nueva advertencia.
    *   **Editar/Eliminar:** Acciones para cada advertencia en la lista.
    *   **Formulario de Advertencia:** Al añadir/editar, encontrará campos para:
        *   **Título:** Un título corto y descriptivo para la advertencia.
        *   **Icono:** Una opción para seleccionar un icono visual que acompañe la advertencia (por ejemplo, un símbolo de peligro).
        *   **Contenido:** El texto completo de la advertencia de seguridad (multilingüe).
        *   **Gravedad/Tipo:** (Si está disponible) Categorice la advertencia.
*   **Efecto de los cambios:** Las advertencias creadas aquí estarán disponibles para su selección al mapear datos GPSR a productos. Luego aparecerán en la página de producto del front-office.
*   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Cree todas las advertencias de seguridad necesarias aquí primero. Asegúrese de que el contenido sea preciso y legalmente conforme para todos los idiomas que admita.

#### 2.2.4 Documentos (Back Office > GPSR Enterprise > Documentos)

Esta pantalla es para subir y gestionar documentos que deben vincularse a productos, como declaraciones de conformidad, manuales de usuario o fichas de datos de seguridad.

*   **Acciones y Ajustes Disponibles:**
    *   **Lista de Documentos:** Una tabla que muestra los documentos subidos, con columnas para nombre, tipo de archivo y productos asociados.
    *   **Subir Nuevo Documento:** Un botón para subir un nuevo archivo.
    *   **Editar/Eliminar:** Acciones para cada documento.
    *   **Formulario de Documento:** Al subir/editar, encontrará campos para:
        *   **Nombre:** Un nombre descriptivo para el documento (multilingüe).
        *   **Subida de Archivo:** El archivo real (por ejemplo, PDF).
        *   **Tipo:** (Si está disponible) Categorice el documento (por ejemplo, "Manual", "Declaración").
*   **Efecto de los cambios:** Los documentos subidos estarán disponibles para su selección al mapear datos GPSR a productos. Los enlaces a estos documentos aparecerán en la página de producto del front-office.
*   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Suba toda la documentación relevante del producto aquí. Asegúrese de que los documentos estén actualizados y correctamente nombrados para una fácil identificación.

#### 2.2.5 Mapeos (Back Office > GPSR Enterprise > Mapeos)

Este es el núcleo de la automatización del módulo, que le permite definir cómo se asignan los datos GPSR a los productos en función de varios criterios. Es probable que esta sección contenga varias subsecciones para diferentes tipos de mapeo.

*   **Acciones y Ajustes Disponibles:**
    *   **Mapeos Globales:** Aplican datos GPSR a todos los productos por defecto.
    *   **Mapeos por Categoría:** Aplican datos GPSR a todos los productos dentro de una categoría específica.
    *   **Mapeos por Fabricante:** Aplican datos GPSR a todos los productos de un fabricante específico.
    *   **Mapeos por Producto/Combinación:** Aplican datos GPSR a productos individuales o combinaciones de productos específicas (variantes).
    *   **Formularios de Mapeo:** Para cada tipo de mapeo, configurará:
        *   **Entidad Fabricante Asignada:** Seleccione una entidad definida en la sección "Entidades".
        *   **Entidad Persona Responsable en la UE Asignada:** Seleccione una entidad definida en la sección "Entidades".
        *   **Advertencias Asignadas:** Seleccione una o más advertencias definidas en la sección "Advertencias".
        *   **Documentos Asignados:** Seleccione uno o más documentos subidos en la sección "Documentos".
        *   **Reglas de Prioridad/Sobrescritura:** (Si están disponibles) Defina cómo interactúan y se sobrescriben los mapeos de diferentes niveles (global, categoría, fabricante, producto).
*   **Efecto de los cambios:** Los cambios aquí determinan directamente qué información GPSR se muestra en sus páginas de producto. Una estrategia de mapeo bien estructurada reduce significativamente el trabajo manual.
*   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Comience con los Mapeos Globales, luego refine con los Mapeos por Categoría y Fabricante. Utilice los Mapeos por Producto/Combinación solo para excepciones o productos únicos. Revise regularmente sus mapeos, especialmente al añadir nuevos productos o categorías.

#### 2.2.6 Acciones Masivas (Back Office > GPSR Enterprise > Acciones Masivas)

Esta pantalla proporciona herramientas para aplicar datos GPSR a varios productos a la vez, o para realizar operaciones masivas.

*   **Acciones y Ajustes Disponibles:**
    *   **Cuadrícula de Productos:** Una lista de productos filtrable y buscable.
    *   **Asignación Masiva:** Seleccione varios productos y luego asigne una Entidad Fabricante, Persona Responsable en la UE, Advertencias o Documentos a todos los productos seleccionados.
    *   **Eliminación Masiva:** Elimine datos GPSR de los productos seleccionados.
    *   **Importar/Exportar:** (Si está disponible) Herramientas para importar datos GPSR desde un archivo CSV o exportar datos existentes.
*   **Efecto de los cambios:** Las acciones masivas pueden actualizar rápidamente los datos GPSR para un gran número de productos, ahorrando un tiempo significativo. Úselas con precaución, ya que los cambios se aplican de forma generalizada.
*   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esto después de la configuración inicial para aplicar rápidamente datos GPSR comunes a grandes conjuntos de productos. También es útil para actualizar datos en muchos productos si cambia una regulación.

#### 2.2.7 Coincidencia (Back Office > GPSR Enterprise > Coincidencia)

Esta pantalla ayuda a identificar productos a los que podrían faltar datos GPSR o sugiere posibles mapeos.

*   **Tabla / Entidad Gestionada:** `gpsr_match_suggestion`
*   **Acciones y Ajustes Disponibles:**
    *   **Lista de Sugerencias:** Muestra productos o grupos de productos que el módulo identifica como que potencialmente necesitan datos GPSR o tienen datos incompletos.
    *   **Reglas de Coincidencia:** (Si están disponibles) Configure reglas sobre cómo el módulo sugiere coincidencias (por ejemplo, basándose en palabras clave del nombre del producto, atributos existentes).
    *   **Aplicar/Descartar Sugerencias:** Acciones para aplicar los datos GPSR sugeridos o descartar la sugerencia.
*   **Efecto de los cambios:** Aplicar sugerencias actualizará los datos GPSR para los productos identificados. Esto ayuda a garantizar un cumplimiento exhaustivo.
*   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise periódicamente esta pantalla para detectar cualquier producto que pueda haberse escapado de su estrategia de mapeo.

#### 2.2.8 Registro de Auditoría (Back Office > GPSR Enterprise > Registro de Auditoría)

Esta pantalla proporciona un registro histórico de los cambios realizados en los datos GPSR dentro del módulo.

*   **Tabla / Entidad Gestionada:** `gpsr_audit_log`
*   **Acciones y Ajustes Disponibles:**
    *   **Cuadrícula de Registro:** Una tabla que muestra entradas con detalles como:
        *   **Fecha/Hora:** Cuándo ocurrió el cambio.
        *   **Usuario:** Qué administrador realizó el cambio.
        *   **Acción:** Qué acción se realizó (por ejemplo, "Entidad creada", "Producto mapeado", "Advertencia actualizada").
        *   **Detalles:** Detalles específicos del cambio.
*   **Efecto de los cambios:** Esta pantalla es para auditoría y monitoreo. No se realizan cambios directos en los datos GPSR aquí, pero proporciona un registro crucial para la rendición de cuentas y la resolución de problemas.
*   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice este registro para revisar los cambios, especialmente si tiene varios administradores gestionando datos GPSR, o si necesita solucionar por qué ciertos datos aparecen (o no aparecen) en el front office.

#### 2.2.9 Libro de Registro (Back Office > GPSR Enterprise > Libro de Registro)

Esta pantalla probablemente proporciona un registro más detallado y "silencioso" de todos los datos GPSR aplicados a los productos, incluyendo potencialmente versiones históricas o una visión general completa para fines regulatorios.

*   **Acciones y Ajustes Disponibles:**
    *   **Vista Centrada en el Producto:** Una forma de ver todos los datos GPSR asociados con un producto específico, posiblemente incluyendo cómo se derivaron (por ejemplo, de un mapeo de categoría o asignados directamente).
    *   **Opciones de Exportación:** (Si están disponibles) Exporte el libro de registro completo para revisión externa o archivo.
*   **Efecto de los cambios:** Esta pantalla es principalmente para informes y revisión detallada. No cambia directamente los datos del front-office, pero proporciona el registro de cumplimiento subyacente.
*   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esto para verificaciones de cumplimiento en profundidad o al prepararse para auditorías regulatorias.

#### 2.2.10 API (Back Office > GPSR Enterprise > API)

Esta pantalla proporciona información y ajustes relacionados con la API del módulo para integraciones externas.

*   **Acciones y Ajustes Disponibles:**
    *   **Token de API:** Muestra el token único requerido para autenticar las solicitudes de API.
    *   **Generar Nuevo Token:** Un botón para generar un nuevo token de API (útil para la seguridad si un token se ve comprometido).
    *   **Enlace a la Documentación de la API:** Un enlace a la documentación técnica para desarrolladores sobre cómo usar la API.
*   **Efecto de los cambios:** Generar un nuevo token invalidará el anterior, lo que requerirá que cualquier sistema externo que utilice la API se actualice con el nuevo token.
*   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Acceda a esto solo si está integrando el módulo GPSR con sistemas externos (por ejemplo, ERP, PIM). Mantenga su token de API seguro.

#### 2.2.11 Cron (Back Office > GPSR Enterprise > Cron)

Esta pantalla gestiona las tareas programadas del módulo, como la reindexación de datos GPSR o la sincronización de información.

*   **Acciones y Ajustes Disponibles:**
    *   **URL de la Tarea Programada (Cron Job):** La URL para activar la tarea programada externamente (por ejemplo, a través del servicio cron de su proveedor de alojamiento).
    *   **Token de Cron:** El token único para una ejecución segura de la tarea programada.
    *   **Activar/Desactivar Cron:** Un interruptor para activar o desactivar la tarea programada.
    *   **Última Ejecución/Resultado:** Información sobre la última vez que se ejecutó la tarea programada y su resultado.
    *   **Ajustes de Reindexación:** Opciones para la frecuencia y la cantidad de productos a reindexar por ejecución (por ejemplo, `GPSR_CRON_REINDEX_OFFSET`, `GPSR_CRON_REINDEX_LIMIT`).
*   **Efecto de los cambios:** Habilitar la tarea programada asegura que los datos GPSR se procesen y actualicen regularmente en segundo plano, manteniendo su información del front-office actualizada. Una configuración incorrecta de la tarea programada puede llevar a datos desactualizados o problemas de carga del servidor.
*   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Asegúrese de que la tarea programada esté habilitada y configurada correctamente en su servidor de alojamiento para automatizar el procesamiento de datos. Monitoree su estado en el panel de control.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| **Configuración del Módulo** | Módulo activado | Sí | Interruptor maestro para la funcionalidad del módulo. |
| | Perfil de tema de la tienda | Coincide con su tema | Optimiza el estilo visual para temas Classic o Hummingbird. |
| | Modo de visualización | Pestaña / Acordeón | Cómo aparece el bloque GPSR (Pestaña, Acordeón, Bloque). |
| | Estilo visual | Predeterminado / Minimalista | Estética del bloque de información GPSR. |
| | Mostrar título del bloque | Sí | Muestra un título encima del bloque GPSR. |
| | Texto del título del bloque | "Seguridad y Cumplimiento del Producto" | Texto personalizado para el título del bloque. |
| | Ocultar bloque cuando los datos están incompletos | Sí | Evita mostrar información GPSR incompleta. |
| | Mostrar entidad fabricante | Sí | Muestra los detalles del fabricante. |
| | Mostrar persona responsable en la UE | Sí | Muestra los detalles de la persona responsable en la UE. |
| | Mostrar advertencias de seguridad | Sí | Muestra las advertencias de seguridad del producto. |
| | Mostrar documentos vinculados | Sí | Muestra enlaces a documentos del producto. |
| | Mostrar botón de pasaporte de producto | Sí | Muestra el botón para descargar el pasaporte de producto en PDF. |
| | Compartir mapeos entre todas las tiendas | Sí (si es multi-tienda) | Centraliza los mapeos GPSR para multi-tienda. |
| | Acción al habilitar compartir | (Elección cuidadosa) | Define el manejo de datos al habilitar mapeos compartidos. |
| | Acción al deshabilitar compartir | (Elección cuidadosa) | Define el manejo de datos al deshabilitar mapeos compartidos. |
| | CSS personalizado | Vacío | Añade CSS personalizado para el estilo del front-office. |
| **Entidades** | Añadir/Editar Entidad | N/A | Define fabricantes y personas responsables en la UE. |
| **Advertencias** | Añadir/Editar Advertencia | N/A | Crea y gestiona advertencias de seguridad. |
| **Documentos** | Subir/Gestionar Documento | N/A | Sube y vincula documentos relacionados con el producto. |
| **Mapeos** | Mapeos Globales/Categoría/Fabricante/Producto | N/A | Asigna datos GPSR según criterios de producto. |
| **Acciones Masivas** | Asignación/Eliminación Masiva | N/A | Aplica/elimina datos GPSR para múltiples productos. |
| **Coincidencia** | Revisar Sugerencias | N/A | Identifica productos que necesitan datos GPSR. |
| **Registro de Auditoría** | Ver Registro | N/A | Rastrea los cambios realizados en los datos GPSR. |
| **Libro de Registro** | Ver/Exportar Datos | N/A | Registro completo de datos GPSR del producto. |
| **API** | Token de API, Generar Nuevo Token | N/A | Gestiona el acceso a la API para integraciones externas. |
| **Cron** | URL de la Tarea Programada, Activar/Desactivar | Activado | Automatiza el procesamiento de datos GPSR en segundo plano. |

## 3. Resolución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: He configurado todo, pero el bloque GPSR no aparece en mis páginas de producto.**
R:
1.  **Verifique "Módulo activado":** Vaya a **Módulos > Gestor de Módulos > GPSR Enterprise > Configurar** y asegúrese de que "Módulo activado" esté configurado en "Sí".
2.  **Verifique "Ocultar bloque cuando los datos están incompletos":** Si esto está configurado en "Sí", el bloque no se mostrará si falta algún dato requerido (fabricante, persona responsable en la UE, advertencias, documentos) para ese producto específico. Asegúrese de que el producto tenga datos GPSR completos asignados a través de mapeos o ediciones directas del producto.
3.  **Borrar Caché:** Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, el contenido antiguo en caché impide que aparezcan nuevos elementos del módulo.
4.  **Compatibilidad del Tema:** Asegúrese de que la configuración de su "Perfil de tema de la tienda" coincida con su tema (Classic o Hummingbird). Si tiene un tema muy personalizado, podría haber un conflicto de CSS. Intente añadir algo de CSS personalizado para forzar la visibilidad o póngase en contacto con el soporte.

**P: Mi bloque de información GPSR se ve extraño o desalineado en mi sitio web.**
R:
1.  **Perfil del Tema:** Vuelva a verificar la configuración de su "Perfil de tema de la tienda" en la configuración del módulo. Asegúrese de que esté configurado en el perfil correcto para su tema de PrestaShop (Classic o Hummingbird).
2.  **CSS Personalizado:** Si tiene CSS personalizado en su tema o en el campo "CSS personalizado" del módulo, podría estar en conflicto. Intente eliminar temporalmente el CSS personalizado para ver si el problema se resuelve.
3.  **Caché del Navegador:** Borre la caché de su navegador (Ctrl+F5 o Cmd+R) para asegurarse de que está viendo el estilo más reciente.
4.  **Contactar Soporte:** Si el problema persiste, su tema podría tener un estilo único que requiera ajustes específicos. Póngase en contacto con el soporte de MyPresta.eu con capturas de pantalla y el nombre de su tema.

**P: ¿Cómo me aseguro de que mis datos GPSR estén traducidos para clientes internacionales?**
R:
1.  **Campos Multilingües:** Al crear **Entidades** y **Advertencias**, asegúrese de rellenar el contenido para todos los idiomas habilitados en su tienda. Busque las banderas de idioma junto a los campos de entrada.
2.  **Traducciones de PrestaShop:** Para las frases predeterminadas del módulo (como "Descargar Pasaporte de Producto" o el título del bloque), vaya a **Internacional > Traducciones**, seleccione "Traducciones de módulos instalados", elija "GPSR Enterprise" y seleccione su idioma de destino. Traduzca cualquier frase que falte allí.
3.  **Pasaporte de Producto:** El Pasaporte de Producto en PDF generado reflejará el idioma de los datos del producto y las advertencias que haya introducido.

**P: La tarea programada (cron job) no parece estar ejecutándose, o mis datos no se actualizan automáticamente.**
R:
1.  **Cron Habilitado:** En la pantalla **Cron** del módulo (Back Office > GPSR Enterprise > Cron), asegúrese de que la tarea programada esté habilitada.
2.  **Configuración de Cron del Alojamiento:** Verifique que haya configurado correctamente la tarea programada en su servidor de alojamiento utilizando la "URL de la Tarea Programada" y el "Token de Cron" proporcionados. Esto generalmente se hace en el panel de control de su alojamiento (cPanel, Plesk, etc.). La tarea programada debe activarse periódicamente (por ejemplo, cada hora).
3.  **Estado de la Última Ejecución:** Verifique "Última Ejecución" y "Último Resultado" en la pantalla de Cron. Si muestra errores o no se ha ejecutado recientemente, hay un problema con la configuración de cron o un problema del lado del servidor.
4.  **Registros del Servidor:** Revise los registros de errores de PHP de su servidor en busca de mensajes relacionados con la ejecución de la tarea programada.

**P: Cometí un error con una acción masiva y ahora muchos productos tienen datos GPSR incorrectos.**
R:
1.  **Registro de Auditoría:** Revise inmediatamente el **Registro de Auditoría** (Back Office > GPSR Enterprise > Registro de Auditoría) para identificar exactamente qué cambios se realizaron y por quién.
2.  **Revertir Manualmente/Mediante Acciones Masivas:** Dependiendo de la magnitud del error, es posible que deba usar la pantalla de **Acciones Masivas** nuevamente para corregir los datos, o editar manualmente los mapeos de productos individuales si solo unos pocos se vieron afectados.
3.  **Copia de Seguridad de la Base de Datos:** Si el error es grave y generalizado, y tiene una copia de seguridad reciente de la base de datos de *antes* del error, restaurar esa copia de seguridad podría ser la solución más rápida. Por eso las copias de seguridad regulares son cruciales.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo GPSR Enterprise, destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Visión General de la Arquitectura

El módulo GPSR Enterprise se adhiere al patrón MVC (Modelo-Vista-Controlador) de PrestaShop, extendiendo las funcionalidades principales e introduciendo entidades personalizadas. Aprovecha `ObjectModel` para las interacciones con la base de datos, `ModuleFrontController` para la entrega de datos en el front-office (API, cron, generación de pasaportes) y `AdminController` para una gestión integral en el back-office. El módulo se basa en gran medida en los hooks para la integración en las páginas de productos y las interfaces administrativas, asegurando una solución no intrusiva pero potente. El mapeo de datos es jerárquico, lo que permite anulaciones globales, por categoría, por fabricante y específicas del producto.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

*   `controllers/front/api.php`
    *   **Nombre de la Clase:** `GpsrEnterpriseApiModuleFrontController`
    *   **Clase Padre:** `ModuleFrontController`
    *   **Responsabilidad:** Gestiona las solicitudes de API para datos GPSR. Proporciona puntos finales para que los sistemas externos consulten información de seguridad del producto, entidades, advertencias y documentos. Requiere autenticación a través de `GPSR_API_TOKEN`. Devuelve cargas útiles JSON.
*   `controllers/front/cron.php`
    *   **Nombre de la Clase:** `GpsrEnterpriseCronModuleFrontController`
    *   **Clase Padre:** `ModuleFrontController`
    *   **Responsabilidad:** Sirve como punto final para tareas programadas (cron jobs). Activa procesos en segundo plano como la reindexación de datos GPSR, la sincronización de mapeos o la limpieza de datos. Requiere autenticación a través de `GPSR_CRON_TOKEN`.
*   `controllers/front/data.php`
    *   **Nombre de la Clase:** `GpsrEnterpriseDataModuleFrontController`
    *   **Clase Padre:** `ModuleFrontController`
    *   **Responsabilidad:** Proporciona puntos finales AJAX para la obtención dinámica de datos GPSR en la página de producto del front-office. Este controlador probablemente recupera el fabricante específico, la persona responsable en la UE, las advertencias y los documentos para un ID de producto o ID de combinación dado.
*   `controllers/front/index.php`
    *   **Nombre de la Clase:** `GpsrEnterpriseIndexModuleFrontController`
    *   **Clase Padre:** `ModuleFrontController`
    *   **Responsabilidad:** Un controlador frontal de marcador de posición o de reserva. A menudo se utiliza para el enrutamiento básico del módulo o para evitar la lista de directorios.
*   `controllers/front/passport.php`
    *   **Nombre de la Clase:** `GpsrEnterprisePassportModuleFrontController`
    *   **Clase Padre:** `ModuleFrontController`
    *   **Responsabilidad:** Genera y sirve el Pasaporte de Producto en PDF para un producto especificado. Recopila todos los datos GPSR relevantes para el producto y los renderiza en un documento PDF descargable.

#### Controladores de Administración del Back-Office

Todos los controladores de administración extienden `GpsrAdminController` (una clase base personalizada dentro del módulo) que a su vez extiende `ModuleAdminController`.

*   `controllers/admin/AdminGpsrAuditController.php`
    *   **Nombre de la Pestaña:** GPSR Enterprise > Registro de Auditoría
    *   **Entidad Gestionada:** `GpsrAuditLogEntry`
    *   **Responsabilidad:** Gestiona la visualización y el filtrado de la tabla `gpsr_audit_log`, registrando todos los cambios significativos realizados dentro del módulo GPSR.
*   `controllers/admin/AdminGpsrController.php`
    *   **Nombre de la Pestaña:** GPSR Enterprise (punto de entrada principal)
    *   **Responsabilidad:** Probablemente sirve como el panel de control principal o una redirección a la pantalla principal de configuración/panel de control del módulo.
*   `controllers/admin/AdminGpsrDocumentsController.php`
    *   **Nombre de la Pestaña:** GPSR Enterprise > Documentos
    *   **Entidad Gestionada:** `GpsrDocument` (implícito, ya que no se listó una clase específica, pero gestiona documentos)
    *   **Responsabilidad:** Gestiona la carga, listado y administración de documentos relacionados con GPSR (por ejemplo, PDFs).
*   `controllers/admin/AdminGpsrEnterpriseController.php`
    *   **Nombre de la Pestaña:** GPSR Enterprise > Panel de Control (o configuración principal)
    *   **Responsabilidad:** Gestiona la configuración principal del módulo, incluyendo tokens de API/Cron, opciones de visualización global y el uso compartido multi-tienda.
*   `controllers/admin/AdminGpsrEntitiesController.php`
    *   **Nombre de la Pestaña:** GPSR Enterprise > Entidades
    *   **Entidad Gestionada:** `GpsrEntity`
    *   **Responsabilidad:** Gestiona la creación, edición y eliminación de entidades GPSR (fabricantes, personas responsables en la UE).
*   `controllers/admin/AdminGpsrLedgerController.php`
    *   **Nombre de la Pestaña:** GPSR Enterprise > Libro de Registro
    *   **Responsabilidad:** Proporciona una vista completa y una interfaz de gestión para el "libro de registro silencioso" de datos GPSR asociados con productos, incluyendo potencialmente datos históricos.
*   `controllers/admin/AdminGpsrMapBrandsController.php`
    *   **Nombre de la Pestaña:** GPSR Enterprise > Mapeos > Marcas
    *   **Entidad Gestionada:** `Manufacturer` (núcleo de PrestaShop)
    *   **Responsabilidad:** Gestiona los mapeos de datos GPSR basados en los fabricantes de PrestaShop.
*   `controllers/admin/AdminGpsrMapCategoriesController.php`
    *   **Nombre de la Pestaña:** GPSR Enterprise > Mapeos > Categorías
    *   **Entidad Gestionada:** `Category` (núcleo de PrestaShop)
    *   **Responsabilidad:** Gestiona los mapeos de datos GPSR basados en las categorías de PrestaShop.
*   `controllers/admin/AdminGpsrMapCombinationsController.php`
    *   **Nombre de la Pestaña:** GPSR Enterprise > Mapeos > Combinaciones
    *   **Entidad Gestionada:** `ProductCombination` (implícito)
    *   **Responsabilidad:** Gestiona los mapeos de datos GPSR para combinaciones de atributos de producto específicas.
*   `controllers/admin/AdminGpsrMapGlobalController.php`
    *   **Nombre de la Pestaña:** GPSR Enterprise > Mapeos > Global
    *   **Responsabilidad:** Gestiona los mapeos de datos GPSR globales que se aplican como predeterminados en todos los productos.
*   `controllers/admin/AdminGpsrMassController.php`
    *   **Nombre de la Pestaña:** GPSR Enterprise > Acciones Masivas
    *   **Responsabilidad:** Proporciona herramientas para la asignación y eliminación masiva de datos GPSR a múltiples productos.
*   `controllers/admin/AdminGpsrMatcherController.php`
    *   **Nombre de la Pestaña:** GPSR Enterprise > Coincidencia
    *   **Entidad Gestionada:** `GpsrMatchSuggestion`
    *   **Responsabilidad:** Gestiona las sugerencias de productos que podrían necesitar datos GPSR o tener mapeos incompletos.
*   `controllers/admin/AdminGpsrWarningsController.php`
    *   **Nombre de la Pestaña:** GPSR Enterprise > Advertencias
    *   **Entidad Gestionada:** `GpsrWarning`
    *   **Responsabilidad:** Gestiona la creación, edición y eliminación de advertencias de seguridad.
*   `controllers/admin/index.php`
    *   **Responsabilidad:** Archivo `index.php` vacío estándar de PrestaShop para evitar la lista de directorios.

### 4.3 Clases y Modelos Principales (`classes/`)

*   `classes/GpsrAdminController.php`
    *   **Responsabilidad:** Una clase base personalizada para todos los controladores de administración dentro del módulo GPSR. Probablemente proporciona métodos, propiedades y variables de plantilla comunes utilizados en las interfaces del back-office del módulo, asegurando la coherencia y reduciendo la duplicación de código.
*   `classes/GpsrAuditLogEntry.php`
    *   **Extiende:** `ObjectModel`
    *   **Tabla de Base de Datos:** `ps_gpsr_audit_log`
    *   **Campos `$definition`:** `id_gpsr_audit_log`, `id_employee`, `action`, `object_type`, `object_id`, `details`, `date_add`
    *   **Métodos públicos clave:** Métodos para registrar entradas de auditoría, recuperar datos de registro.
    *   **Lógica de Negocio:** Registra cada acción significativa realizada dentro del módulo GPSR para auditoría y cumplimiento.
*   `classes/GpsrCompatibility.php`
    *   **Responsabilidad:** Gestiona las capas de compatibilidad para diferentes versiones de PrestaShop (1.7.x, 8.x, 9.x). Esta clase probablemente contiene métodos estáticos para abstraer las diferencias específicas de la versión en las llamadas a la API, los nombres de los hooks o la representación de plantillas, asegurando que el módulo funcione sin problemas en todas las versiones compatibles.
*   `classes/GpsrEntity.php`
    *   **Extiende:** `ObjectModel`
    *   **Tabla de Base de Datos:** `ps_gpsr_entity` (y `ps_gpsr_entity_lang` para campos multilingües)
    *   **Campos `$definition`:** `id_gpsr_entity`, `type`, `name`, `address`, `contact_email`, `contact_phone`, `contact_website`, `active`, `date_add`, `date_upd` (y campos multilingües como `name_lang`, `address_lang`, etc.)
    *   **Métodos públicos clave:** Métodos para operaciones CRUD en entidades, recuperación de entidades por tipo, asociación de entidades con productos/mapeos.
    *   **Lógica de Negocio:** Gestiona los datos de fabricantes y personas responsables en la UE.
*   `classes/GpsrWarning.php`
    *   **Extiende:** `ObjectModel`
    *   **Tabla de Base de Datos:** `ps_gpsr_warning` (y `ps_gpsr_warning_lang` para campos multilingües)
    *   **Campos `$definition`:** `id_gpsr_warning`, `icon`, `active`, `date_add`, `date_upd` (y campos multilingües como `title`, `content`)
    *   **Métodos públicos clave:** Métodos para operaciones CRUD en advertencias, recuperación de advertencias por ID, asociación de advertencias con productos/mapeos.
    *   **Lógica de Negocio:** Gestiona los datos de las advertencias de seguridad.
*   `classes/index.php`
    *   **Responsabilidad:** Archivo `index.php` vacío estándar de PrestaShop para evitar la lista de directorios.

### 4.4 Activos JavaScript (`views/js/`)

*   `gpsrenterprise/lib/searchTool/views/js/autocomplete.js`
    *   **Alcance:** Probablemente Back-office.
    *   **Responsabilidad:** Proporciona funcionalidad de autocompletado para campos de búsqueda dentro de la interfaz de administración, posiblemente para seleccionar productos, categorías o entidades en las pantallas de mapeo.
*   `gpsrenterprise/views/js/admin-api.js`
    *   **Alcance:** Back-office (AdminGpsrEnterpriseController, pestaña API).
    *   **Responsabilidad:** Gestiona las interacciones AJAX para la pantalla de configuración de la API, como generar nuevos tokens de API o mostrar modales de documentación de la API.
*   `gpsrenterprise/views/js/admin-combination-map.js`
    *   **Alcance:** Back-office (AdminGpsrMapCombinationsController).
    *   **Responsabilidad:** Gestiona la interfaz de usuario y las llamadas AJAX para mapear datos GPSR a combinaciones de productos específicas. Esto probablemente implica la carga dinámica de listas de combinaciones y la gestión de asignaciones.
*   `gpsrenterprise/views/js/admin-combination-picker.js`
    *   **Alcance:** Back-office (Pestaña de página de producto, formularios de mapeo).
    *   **Responsabilidad:** Proporciona un componente de interfaz de usuario para seleccionar combinaciones de productos, a menudo utilizado dentro de formularios de mapeo o la pestaña de edición de productos.
*   `gpsrenterprise/views/js/admin-country-rules.js`
    *   **Alcance:** Back-office (Potencialmente dentro de formularios de entidad o advertencia).
    *   **Responsabilidad:** Gestiona la lógica de la interfaz de usuario para aplicar reglas GPSR basadas en países específicos, si el módulo admite el cumplimiento específico de cada país.
*   `gpsrenterprise/views/js/admin-entity-picker.js`
    *   **Alcance:** Back-office (Formularios de mapeo, pestaña de página de producto).
    *   **Responsabilidad:** Proporciona un componente de interfaz de usuario para seleccionar instancias de `GpsrEntity` (fabricantes, personas responsables en la UE) de un menú desplegable o interfaz de búsqueda.
*   `gpsrenterprise/views/js/admin-icon-picker-data.js`
    *   **Alcance:** Back-office (Formularios de advertencia).
    *   **Responsabilidad:** Contiene datos (por ejemplo, una matriz de nombres/rutas de iconos) utilizados por `admin-icon-picker.js`.
*   `gpsrenterprise/views/js/admin-icon-picker.js`
    *   **Alcance:** Back-office (Formularios de advertencia).
    *   **Responsabilidad:** Implementa un componente de interfaz de usuario para seleccionar visualmente un icono para asociar con una `GpsrWarning`.
*   `gpsrenterprise/views/js/admin-identifier-shortcodes.js`
    *   **Alcance:** Back-office (Áreas de texto en formularios, por ejemplo, para plantillas de pasaporte de producto).
    *   **Responsabilidad:** Proporciona funcionalidad para insertar "códigos cortos" o marcadores de posición predefinidos en campos de texto, que se reemplazarán dinámicamente con datos del producto cuando se rendericen.
*   `gpsrenterprise/views/js/admin-item-picker.js`
    *   **Alcance:** Back-office (Formularios de mapeo generales).
    *   **Responsabilidad:** Un componente de interfaz de usuario genérico para seleccionar varios elementos (productos, categorías, documentos, advertencias) de una lista o búsqueda.
*   `gpsrenterprise/views/js/admin-mass-grid.js`
    *   **Alcance:** Back-office (AdminGpsrMassController).
    *   **Responsabilidad:** Gestiona la cuadrícula de productos interactiva y la funcionalidad de acciones masivas en la pantalla "Acciones Masivas".
*   `gpsrenterprise/views/js/admin-product-tab.js`
    *   **Alcance:** Back-office (Página de edición de producto).
    *   **Responsabilidad:** Inyecta y gestiona la pestaña GPSR personalizada en la página de edición de productos de PrestaShop, permitiendo la asignación directa de datos GPSR a productos individuales.
*   `gpsrenterprise/views/js/adminGpsrDashboard.js`
    *   **Alcance:** Back-office (Panel de control de AdminGpsrController/AdminGpsrEnterpriseController).
    *   **Responsabilidad:** Gestiona elementos dinámicos y actualizaciones AJAX en el panel de control del módulo, como la actualización del estado de cron o la visualización de estadísticas.
*   `gpsrenterprise/views/js/front.js`
    *   **Alcance:** Front-office.
    *   **Responsabilidad:** JavaScript principal para el bloque de información GPSR del front-office. Gestiona la carga dinámica de datos (a través del controlador `data.php`), la funcionalidad de pestañas/acordeón y, potencialmente, las interacciones con el botón del Pasaporte de Producto.
*   `gpsrenterprise/views/js/gpsr-barcode.js`
    *   **Alcance:** Front-office o Back-office (Generación de Pasaporte de Producto).
    *   **Responsabilidad:** Probablemente un script de utilidad para generar o mostrar códigos de barras, potencialmente utilizado dentro del PDF del Pasaporte de Producto o para la identificación del producto.

### 4.5 Hojas de Estilo CSS (`views/css/`)

*   `gpsrenterprise/lib/searchTool/views/css/autocomplete.css`
    *   **Alcance:** Back-office.
    *   **Responsabilidad:** Estilos para los campos de búsqueda de autocompletado utilizados en la interfaz de administración.
*   `gpsrenrterprise/views/css/admin-api.css`
    *   **Alcance:** Back-office (AdminGpsrEnterpriseController, pestaña API).
    *   **Responsabilidad:** Estilos específicos para la configuración de la API y la visualización de la documentación.
*   `gpsrenterprise/views/css/admin-combination-map.css`
    *   **Alcance:** Back-office (AdminGpsrMapCombinationsController).
    *   **Responsabilidad:** Estilos para la interfaz de mapeo de combinaciones.
*   `gpsrenterprise/views/css/admin-combination-picker.css`
    *   **Alcance:** Back-office.
    *   **Responsabilidad:** Estilos para el componente de selección de combinación de productos.
*   `gpsrenterprise/views/css/admin-config.css`
    *   **Alcance:** Back-office (Página de configuración del módulo).
    *   **Responsabilidad:** Estilos generales para el formulario de configuración principal del módulo.
*   `gpsrenterprise/views/css/admin-country-rules.css`
    *   **Alcance:** Back-office.
    *   **Responsabilidad:** Estilos para las interfaces de configuración de reglas específicas de cada país.
*   `gpsrenterprise/views/css/admin-dashboard.css`
    *   **Alcance:** Back-office (Panel de control de AdminGpsrController/AdminGpsrEnterpriseController).
    *   **Responsabilidad:** Estilos para el panel de control administrativo del módulo.
*   `gpsrenterprise/views/css/admin-help.css`
    *   **Alcance:** Back-office.
    *   **Responsabilidad:** Estilos para textos de ayuda, tooltips o secciones de documentación dentro de la administración.
*   `gpsrenterprise/views/css/admin-item-picker.css`
    *   **Alcance:** Back-office.
    *   **Responsabilidad:** Estilos para el componente genérico de selección de elementos.
*   `gpsrenterprise/views/css/admin-list-enhanced.css`
    *   **Alcance:** Back-office.
    *   **Responsabilidad:** Mejoras en el estilo predeterminado de la lista/cuadrícula de PrestaShop para una mejor legibilidad o funcionalidad.
*   `gpsrenterprise/views/css/admin-mass-grid.css`
    *   **Alcance:** Back-office (AdminGpsrMassController).
    *   **Responsabilidad:** Estilos para la cuadrícula de productos de acciones masivas.
*   `gpsrenterprise/views/css/admin-nav.css`
    *   **Alcance:** Back-office.
    *   **Responsabilidad:** Estilos para las pestañas de navegación personalizadas del módulo o los elementos de menú dentro de la administración.
*   `gpsrenterprise/views/css/admin-product-tab.css`
    *   **Alcance:** Back-office (Página de edición de producto).
    *   **Responsabilidad:** Estilos para la pestaña GPSR añadida a la página de edición de productos de PrestaShop.
*   `gpsrenterprise/views/css/front-classic.css`
    *   **Alcance:** Front-office (Tema Classic).
    *   **Responsabilidad:** Estilo específico para el bloque GPSR cuando se selecciona el perfil de tema "Classic".
*   `gpsrenterprise/views/css/front-hummingbird.css`
    *   **Alcance:** Front-office (Tema Hummingbird).
    *   **Responsabilidad:** Estilo específico para el bloque GPSR cuando se selecciona el perfil de tema "Hummingbird".
*   `gpsrenterprise/views/css/front.css`
    *   **Alcance:** Front-office.
    *   **Responsabilidad:** Estilo general y base para el bloque de información GPSR en la tienda, aplicado independientemente del perfil del tema, que luego puede ser anulado por `front-classic.css` o `front-hummingbird.css`.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)

*   `gpsrenterprise/views/templates/hook/product-gpsr-classic.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (dependiendo de la configuración)
    *   **Salida:** El bloque principal de información GPSR para la página de producto del front-office, específicamente estilizado para el perfil de tema Classic.
*   `gpsrenterprise/views/templates/hook/product-gpsr-hummingbird.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (dependiendo de la configuración)
    *   **Salida:** El bloque principal de información GPSR para la página de producto del front-office, específicamente estilizado para el perfil de tema Hummingbird.
*   `gpsrenterprise/views/templates/hook/product-gpsr.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (dependiendo de la configuración)
    *   **Salida:** Una plantilla genérica o base para el bloque de información GPSR, que podría incluir lógica para cargar las plantillas específicas de Classic o Hummingbird según la configuración del módulo.
*   `gpsrenterprise/views/templates/hook/_product-gpsr-attrs.tpl`
    *   **Hook:** Plantilla parcial interna.
    *   **Salida:** Renderiza atributos o detalles específicos dentro del bloque principal de producto GPSR, como advertencias individuales, detalles de la entidad o enlaces a documentos. Esto probablemente está incluido por `product-gpsr.tpl` o sus variantes específicas del tema.

#### Plantillas de Administración (`views/templates/admin/`)

*   `gpsrenterprise/lib/searchTool/views/scripts.tpl`
    *   **Salida:** Contiene JavaScript o lógica Smarty para la funcionalidad de la herramienta de búsqueda, probablemente incluida en varias páginas de administración.
*   `gpsrenterprise/views/templates/admin/api.tpl`
    *   **Salida:** Renderiza el contenido de la pantalla de configuración de la API, incluyendo la visualización del token, el botón de generación y el enlace a la documentación.
*   `gpsrenterprise/views/templates/admin/back-office.tpl`
    *   **Salida:** Una plantilla general del back-office, posiblemente para el panel de control principal del módulo o un envoltorio para otras vistas de administración.
*   `gpsrenterprise/views/templates/admin/combination-list.tpl`
    *   **Salida:** Muestra una lista de combinaciones de productos, utilizada en interfaces de mapeo o selección.
*   `gpsrenterprise/views/templates/admin/combination-picker.tpl`
    *   **Salida:** Renderiza la interfaz de usuario para seleccionar combinaciones de productos.
*   `gpsrenterprise/views/templates/admin/combination-script.tpl`
    *   **Salida:** Contiene JavaScript específico para la gestión de combinaciones, probablemente incluido en páginas que tratan con combinaciones de productos.
*   `gpsrenterprise/views/templates/admin/configure.tpl`
    *   **Salida:** Renderiza el formulario de configuración principal del módulo (accesible a través de Módulos > Configurar).
*   `gpsrenterprise/views/templates/admin/country-rules-panel.tpl`
    *   **Salida:** Renderiza un panel para gestionar las reglas GPSR específicas de cada país.
*   `gpsrenterprise/views/templates/admin/cron.tpl`
    *   **Salida:** Renderiza el contenido de la pantalla de configuración y estado de la tarea programada (Cron job).
*   `gpsrenterprise/views/templates/admin/dashboard.tpl`
    *   **Salida:** Renderiza el panel de control principal del módulo con estadísticas y enlaces rápidos.
*   `gpsrenterprise/views/templates/admin/documents.tpl`
    *   **Salida:** Renderiza la lista y la interfaz de gestión de documentos GPSR.
*   `gpsrenterprise/views/templates/admin/entities-list.tpl`
    *   **Salida:** Muestra la lista de entidades GPSR configuradas.
*   `gpsrenterprise/views/templates/admin/entities.tpl`
    *   **Salida:** Plantilla envoltorio principal para la pantalla de gestión de Entidades.
*   `gpsrenterprise/views/templates/admin/entity-form.tpl`
    *   **Salida:** Renderiza el formulario para añadir o editar una `GpsrEntity`.
*   `gpsrenterprise/views/templates/admin/entity-picker.tpl`
    *   **Salida:** Renderiza la interfaz de usuario para seleccionar una `GpsrEntity`.
*   `gpsrenterprise/views/templates/admin/getCombinations.tpl`
    *   **Salida:** Una plantilla probablemente utilizada para respuestas AJAX para cargar dinámicamente combinaciones de productos.
*   `gpsrenterprise/views/templates/admin/item-picker.tpl`
    *   **Salida:** Renderiza un componente de interfaz de usuario genérico para seleccionar elementos.
*   `gpsrenterprise/views/templates/admin/ledger.tpl`
    *   **Salida:** Renderiza la vista detallada del libro de registro GPSR.
*   `gpsrenterprise/views/templates/admin/map-fields.tpl`
    *   **Salida:** Una plantilla parcial que contiene campos comunes para los mapeos GPSR (por ejemplo, selectores de entidad, selectores de advertencia).
*   `gpsrenterprise/views/templates/admin/map-form-category.tpl`
    *   **Salida:** Renderiza el formulario para crear/editar mapeos GPSR a nivel de categoría.
*   `gpsrenterprise/views/templates/admin/map-form-combination.tpl`
    *   **Salida:** Renderiza el formulario para crear/editar mapeos GPSR a nivel de combinación de producto.
*   `gpsrenterprise/views/templates/admin/map-form-global.tpl`
    *   **Salida:** Renderiza el formulario para crear/editar mapeos GPSR globales.
*   `gpsrenterprise/views/templates/admin/map-form-manufacturer.tpl`
    *   **Salida:** Renderiza el formulario para crear/editar mapeos GPSR a nivel de fabricante.
*   `gpsrenterprise/views/templates/admin/mappings.tpl`
    *   **Salida:** Plantilla envoltorio principal para la sección de Mapeos, probablemente incluyendo navegación para diferentes tipos de mapeo.
*   `gpsrenterprise/views/templates/admin/mass-grid.tpl`
    *   **Salida:** Renderiza la cuadrícula de productos y los controles de acciones masivas para la pantalla "Acciones Masivas".
*   `gpsrenterprise/views/templates/admin/matcher.tpl`
    *   **Salida:** Renderiza la interfaz para el Coincidencia GPSR, mostrando sugerencias.
*   `gpsrenterprise/views/templates/admin/nav-tabs.tpl`
    *   **Salida:** Renderiza las pestañas de navegación para las secciones del back-office del módulo (Panel de Control, Entidades, Advertencias, Mapeos, etc.).
*   `gpsrenterprise/views/templates/admin/product-preview-card.tpl`
    *   **Salida:** Renderiza una pequeña tarjeta de vista previa para un producto, posiblemente utilizada en componentes de selección o cuadrículas de acciones masivas.
*   `gpsrenterprise/views/templates/admin/product-tab.tpl`
    *   **Salida:** Renderiza el contenido de la pestaña GPSR personalizada en la página de edición de productos de PrestaShop.
*   `gpsrenterprise/views/templates/admin/warning-form.tpl`
    *   **Salida:** Renderiza el formulario para añadir o editar una `GpsrWarning`.
*   `gpsrenterprise/views/templates/admin/warnings-list.tpl`
    *   **Salida:** Muestra la lista de advertencias GPSR configuradas.
*   `gpsrenterprise/views/templates/admin/_api_documentation_modal.tpl`
    *   **Salida:** Renderiza el contenido de una ventana modal que muestra la documentación de la API.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

*   `ps_gpsr_audit_log`: Almacena entradas de la pista de auditoría para los cambios realizados dentro del módulo.
    *   `id_gpsr_audit_log` (PK)
    *   `id_employee` (FK a `ps_employee`)
    *   `action` (por ejemplo, 'add', 'edit', 'delete', 'map')
    *   `object_type` (por ejemplo, 'entity', 'warning', 'product_mapping')
    *   `object_id`
    *   `details` (JSON o texto para más información)
    *   `date_add`
*   `ps_gpsr_entity`: Almacena detalles de fabricantes y personas responsables en la UE.
    *   `id_gpsr_entity` (PK)
    *   `type` (por ejemplo, 'manufacturer', 'eu_responsible')
    *   `active`
    *   `date_add`, `date_upd`
*   `ps_gpsr_entity_lang`: Campos multilingües para `ps_gpsr_entity`.
    *   `id_gpsr_entity` (FK)
    *   `id_lang` (FK)
    *   `name`
    *   `address`
    *   `contact_email`
    *   `contact_phone`
    *   `contact_website`
*   `ps_gpsr_warning`: Almacena definiciones de advertencias de seguridad.
    *   `id_gpsr_warning` (PK)
    *   `icon`
    *   `active`
    *   `date_add`, `date_upd`
*   `ps_gpsr_warning_lang`: Campos multilingües para `ps_gpsr_warning`.
    *   `id_gpsr_warning` (FK)
    *   `id_lang` (FK)
    *   `title`
    *   `content`
*   `ps_gpsr_document`: Almacena detalles de los documentos subidos.
    *   `id_gpsr_document` (PK)
    *   `filename`
    *   `mime_type`
    *   `file_size`
    *   `date_add`, `date_upd`
*   `ps_gpsr_document_lang`: Campos multilingües para `ps_gpsr_document` (por ejemplo, `name`).
*   `ps_gpsr_product_mapping`: Asignaciones directas de datos GPSR a nivel de producto.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK, para combinaciones)
    *   `id_gpsr_entity_manufacturer` (FK a `ps_gpsr_entity`)
    *   `id_gpsr_entity_eu_responsible` (FK a `ps_gpsr_entity`)
    *   `date_add`, `date_upd`
*   `ps_gpsr_product_warning`: Tabla de unión para relaciones producto-advertencia.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK)
    *   `id_gpsr_warning` (FK)
*   `ps_gpsr_product_document`: Tabla de unión para relaciones producto-documento.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK)
    *   `id_gpsr_document` (FK)
*   `ps_gpsr_category_mapping`: Asignaciones de datos GPSR a nivel de categoría.
    *   `id_category` (FK)
    *   `id_gpsr_entity_manufacturer`
    *   `id_gpsr_entity_eu_responsible`
*   `ps_gpsr_category_warning`: Tabla de unión para relaciones categoría-advertencia.
*   `ps_gpsr_category_document`: Tabla de unión para relaciones categoría-documento.
*   `ps_gpsr_manufacturer_mapping`: Asignaciones de datos GPSR a nivel de fabricante.
    *   `id_manufacturer` (FK)
    *   `id_gpsr_entity_manufacturer`
    *   `id_gpsr_entity_eu_responsible`
*   `ps_gpsr_manufacturer_warning`: Tabla de unión para relaciones fabricante-advertencia.
*   `ps_gpsr_manufacturer_document`: Tabla de unión para relaciones fabricante-documento.
*   `ps_gpsr_global_mapping`: Almacena datos GPSR globales predeterminados.
*   `ps_gpsr_match_suggestion`: Almacena sugerencias generadas por el coincidencia.
    *   `id_gpsr_match_suggestion` (PK)
    *   `id_product`
    *   `suggestion_type`
    *   `suggested_data` (JSON)
    *   `date_add`
*   `ps_configuration`: La configuración del módulo se almacena aquí con claves como `GPSR_ENABLED`, `GPSR_CUSTOM_CSS`, `GPSR_API_TOKEN`, `GPSR_CRON_TOKEN`, etc.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| :-------- | :--------------- | :---------------- |
| `actionProductSave` | Después de guardar un producto (añadir o actualizar). | Activa la reevaluación de los datos GPSR para el producto, actualiza los mapeos o registra los cambios. |
| `actionAfterUpdateProductFormHandler` | Después de actualizar un formulario de producto en el BO. | Actualiza los datos GPSR mostrados en la pestaña del producto o activa actualizaciones relacionadas. |
| `actionObjectProductDeleteAfter` | Después de eliminar un objeto de producto. | Limpia los datos y mapeos GPSR asociados para el producto eliminado. |
| `actionAfterCreateProductFormHandler` | Después de crear un formulario de producto en el BO. | Inicializa los datos GPSR para un nuevo producto, aplicando potencialmente mapeos predeterminados. |
| `displayAfterProductThumbs` | En la página del producto, después de las imágenes del producto. | Renderiza el bloque de información GPSR del front-office. (La ubicación depende del tema/configuración) |
| `actionObjectProductAddAfter` | Después de añadir un nuevo objeto de producto. | Activa la asignación inicial de datos GPSR para el nuevo producto. |
| `displayProductAdditionalInfo` | En la página del producto, en la sección "Información Adicional". | Renderiza el bloque de información GPSR del front-office, a menudo como una pestaña. |
| `displayAdminProductsExtra` | En la página de edición de productos en el Back Office. | Inyecta la pestaña GPSR personalizada para la gestión de datos específicos del producto. |
| `displayBackOfficeHeader` | En el encabezado de cada página del Back Office. | Carga CSS/JS específicos del módulo para las interfaces de administración, añade elementos de menú. |
| `actionAdminControllerSetMedia` | Cuando un controlador de administración establece sus medios (CSS/JS). | Carga CSS/JS específicos del módulo para las páginas de administración relevantes. |
| `displayProductExtraContent` | En la página del producto, para bloques de contenido extra. | Renderiza el bloque de información GPSR del front-office, ofreciendo una ubicación flexible. |
| `displayFooterProduct` | En la sección del pie de página de la página del producto. | Renderiza el bloque de información GPSR del front-office, a menudo como un bloque debajo del contenido principal. |
| `displayReassurance` | En el bloque de reafirmación del producto (por ejemplo, envío gratuito, pago seguro). | Renderiza el bloque de información GPSR del front-office, potencialmente como una pequeña insignia o enlace tranquilizador. |
| `actionProductAttributeUpdate` | Después de actualizar una combinación de producto (atributo). | Activa la reevaluación de los datos GPSR para la combinación específica. |
| `actionFrontControllerSetMedia` | Cuando un controlador frontal establece sus medios (CSS/JS). | Carga CSS/JS específicos del módulo para las páginas del front-office donde se muestran los datos GPSR. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo GPSR Enterprise, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad o integración del módulo.

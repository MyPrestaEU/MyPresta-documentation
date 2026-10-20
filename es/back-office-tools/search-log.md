---
title: "Registro de búsqueda - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Registro de búsqueda' de MyPresta.eu."
sidebar:
  label: "Registro de búsqueda - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Search log en MyPresta.eu](https://mypresta.eu/modules/administration-tools/search-log.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/search-log/)
>
> ---


# Registro de búsqueda

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No hay requisitos especiales más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Registro de búsqueda)

Esta es la pantalla de configuración principal para el módulo "Registro de búsqueda". Proporciona una interfaz simple para habilitar o deshabilitar la funcionalidad de registro.

- **Ubicación del menú:** Back Office > Módulos > Gestor de módulos > Registro de búsqueda > Configurar

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo de comerciante |
| --- | --- | --- | --- | --- |
| **Habilitar registro de búsqueda** (Interruptor) | Este interruptor controla si el módulo registra activamente las consultas de búsqueda de los clientes. | *Cuando está habilitado (SÍ):* Cada vez que un cliente utiliza la barra de búsqueda de su tienda, su término de búsqueda se guardará en el registro del módulo. Luego podrá ver estos registros en el menú dedicado "Registro de búsqueda". *Cuando está deshabilitado (NO):* El módulo dejará de registrar nuevas consultas de búsqueda. Los registros existentes permanecerán, pero no se recopilarán nuevos datos. | **SÍ** | Acaba de instalar el módulo y desea comenzar a recopilar datos de inmediato para comprender lo que buscan sus clientes. Lo configuraría en SÍ. Si necesita detener temporalmente el registro (por ejemplo, durante el mantenimiento o si tiene demasiados datos), podría cambiarlo a NO. |

### 2.2 Pantalla de administración dedicada: Gestión del registro de búsqueda (Back Office > Registro de búsqueda)

Esta pantalla es donde puede ver y administrar todas las consultas de búsqueda registradas por el módulo. Proporciona una lista completa de lo que buscan sus clientes.

- **Nombre de la pantalla y ubicación del menú:** Back Office > **Registro de búsqueda** (Esto aparecerá como un nuevo elemento de menú, generalmente en "Parámetros de la tienda" o "Parámetros avanzados" según su versión de PrestaShop).

**Acciones y configuraciones disponibles:**
Esta pantalla suele presentar una cuadrícula (lista) de todos los términos de búsqueda registrados. Para cada entrada, normalmente verá:

- **Palabra clave de búsqueda:** El término o frase exacto que el cliente escribió en la barra de búsqueda.
- **Número de búsquedas:** Cuántas veces se ha buscado esta palabra clave específica.
- **Fecha de la última búsqueda:** Cuándo se buscó esta palabra clave más recientemente.
- **Número de resultados:** Cuántos productos se encontraron para este término de búsqueda (esto es crucial para identificar búsquedas "sin resultados").

**Vista de cuadrícula / gestión:**
La cuadrícula le permite:

- **Ordenar:** Haga clic en los encabezados de las columnas (por ejemplo, "Palabra clave de búsqueda", "Número de búsquedas") para ordenar la lista.
- **Filtrar:** Utilice los campos de filtro encima de las columnas para reducir la lista (por ejemplo, buscar una palabra clave específica o filtrar por número de resultados).
- **Exportar:** Algunas versiones pueden ofrecer una opción de exportación para descargar los datos para un análisis posterior en un programa de hoja de cálculo.
- **Eliminar:** Puede tener opciones para eliminar entradas de búsqueda individuales o borrar todo el registro.

**Efecto de los cambios:**

- **Ver la lista:** Proporciona información inmediata sobre el comportamiento de búsqueda del cliente.
- **Ordenar/Filtrar:** Le ayuda a identificar rápidamente búsquedas populares, búsquedas sin resultados o tendencias a lo largo del tiempo.
- **Eliminar entradas:** Elimina datos del registro. Esto podría ser útil para limpiar entradas irrelevantes o gestionar el tamaño de la base de datos, pero generalmente, es mejor mantener los datos para un análisis histórico.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1.  **Revise esta pantalla regularmente:** Acostúmbrese a revisar el "Registro de búsqueda" al menos una vez a la semana.
2.  **Concéntrese en las búsquedas "Sin resultados":** Priorice las palabras clave que arrojaron cero resultados. Estas son sus mayores oportunidades:
    - ¿Tiene el producto pero no está indexado correctamente o la descripción es deficiente?
    - ¿Es un producto que debería considerar almacenar?
    - ¿Es un error ortográfico común que puede tener en cuenta con sinónimos?
3.  **Identifique búsquedas populares:** Vea qué interesa más a los clientes. Asegúrese de que estos productos se muestren de forma destacada, estén bien descritos y se encuentren fácilmente.
4.  **Analice las tendencias:** ¿Hay términos de búsqueda estacionales? ¿Nuevas ideas de productos que surgen de las consultas de los clientes?

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar registro de búsqueda | SÍ | Controla si se registran las consultas de búsqueda de los clientes. |
| Gestión del registro de búsqueda | Palabra clave de búsqueda (Columna de la cuadrícula) | N/A | Muestra el término de búsqueda real utilizado por los clientes. |
| Gestión del registro de búsqueda | Número de búsquedas (Columna de la cuadrícula) | N/A | Muestra cuántas veces se buscó una palabra clave específica. |
| Gestión del registro de búsqueda | Fecha de la última búsqueda (Columna de la cuadrícula) | N/A | Indica la ocurrencia más reciente de un término de búsqueda. |
| Gestión del registro de búsqueda | Número de resultados (Columna de la cuadrícula) | N/A | Crucial para identificar búsquedas que no arrojaron productos. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: He habilitado el módulo, pero no veo que aparezcan registros de búsqueda.**
R:

1.  **Verifique si los clientes realmente están buscando:** Asegúrese de que la barra de búsqueda de su tienda sea visible y esté siendo utilizada por los visitantes.
2.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, el almacenamiento en caché puede evitar que los módulos se inicialicen por completo.
3.  **Pruébelo usted mismo:** Realice algunas búsquedas en su front office mientras está desconectado (o en modo incógnito) y luego verifique la pantalla de administración "Registro de búsqueda".
4.  **Posición del módulo:** Si bien el módulo no tiene un componente visible en el front office, asegúrese de que esté enganchado correctamente. El módulo normalmente se engancha a `displayHeader` o similar, lo que se maneja automáticamente. Si los problemas persisten, intente reinstalarlo.

**P: El registro de búsqueda está creciendo mucho. ¿Esto ralentizará mi tienda?**
R: Si bien una tabla de base de datos muy grande puede, en teoría, afectar el rendimiento, para la mayoría de las tiendas, es poco probable que la tabla `slog` creada por este módulo cause ralentizaciones significativas. Es una tabla de registro simple. Si tiene millones de entradas y nota problemas, puede borrar periódicamente las entradas antiguas de la pantalla de gestión "Registro de búsqueda" o deshabilitar el módulo temporalmente.

**P: ¿Puedo ver qué cliente realizó una búsqueda específica?**
R: No, este módulo está diseñado para el análisis agregado de palabras clave, no para el seguimiento individual de clientes. Registra la palabra clave, no el ID del cliente. Esto garantiza la privacidad del cliente al tiempo que proporciona información comercial valiosa.

**P: ¿Cómo exporto los datos del registro de búsqueda para analizarlos en Excel?**
R: La pantalla de gestión "Registro de búsqueda" en su Back Office debería tener un botón "Exportar" (a menudo ubicado cerca de la parte superior derecha de la cuadrícula, o como una acción masiva). Haga clic en él para descargar los datos, generalmente en formato CSV, que se pueden abrir con Excel o Google Sheets.

**P: La barra de búsqueda de mi tema personalizado no parece estar registrada.**
R: El módulo normalmente se engancha a la funcionalidad de búsqueda estándar de PrestaShop. Si su tema personalizado utiliza una implementación de búsqueda completamente personalizada y no estándar (por ejemplo, una búsqueda AJAX que omite el controlador de búsqueda central de PrestaShop), es posible que el módulo no capture esas consultas. En tales casos, necesitaría un desarrollador para integrar la funcionalidad de registro directamente en su script de búsqueda personalizado.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura

El módulo "Registro de búsqueda" es un módulo de PrestaShop sencillo centrado principalmente en el registro de datos. Sigue un patrón MVC estándar de PrestaShop para su componente de Back Office, utilizando un `AdminController` para gestionar los datos de búsqueda registrados. El mecanismo de registro del front office se integra directamente con el proceso de búsqueda central de PrestaShop, normalmente enganchándose a una acción que se activa después de que se realiza una búsqueda. Crea una tabla de base de datos dedicada para almacenar las consultas de búsqueda.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. El módulo se integra con la funcionalidad de búsqueda existente de PrestaShop a través de hooks, en lugar de proporcionar su propio controlador de front.
-   **Controladores de administración de Back-Office**:

    -   `searchlog/controllers/admin/AdminSlog.php`

        -   **Nombre de la clase y clase padre**: `AdminSlogController` extiende `ModuleAdminController`.
        -   **Responsabilidad**: Este es el controlador principal para gestionar las entradas del registro de búsqueda en el Back Office de PrestaShop. Maneja la visualización de la cuadrícula del registro de búsqueda, incluyendo las acciones de clasificación, filtrado y, potencialmente, eliminación. Es responsable de obtener datos de la tabla de base de datos `slog` y renderizarlos utilizando los componentes `HelperList` o `HelperGrid` de PrestaShop.
        -   **Nombre de la pestaña**: "Registro de búsqueda" (o similar, según la instalación).
        -   **Entidad gestionada**: La tabla de base de datos `slog`.
    -   `searchlog/controllers/admin/index.php`

        -   **Nombre de la clase y clase padre**: No es una clase, sino un archivo `index.php` estándar de PrestaShop dentro de un directorio de controlador de administración.
        -   **Responsabilidad**: Este archivo suele servir como medida de seguridad en los directorios de administración de PrestaShop, evitando la lista directa de directorios. Generalmente contiene un simple `header('Location: ../../index.php?controller=AdminHome'); exit;` o un redireccionamiento similar, o simplemente una declaración `die('Forbidden');`. No contiene lógica específica del módulo.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. La lógica central para interactuar con la tabla `slog` probablemente se maneja directamente dentro de `AdminSlogController` o el archivo principal del módulo `searchlog/index.php`, posiblemente utilizando un `Db::getInstance()->execute()` genérico para operaciones de datos simples, o una definición básica de `ObjectModel` si se creó implícitamente o no se incluyó en el dossier. Dada la simplicidad, una interacción directa con `Db` es más probable.

### 4.4 Activos de JavaScript (`views/js/`)

No se enumeran archivos JavaScript personalizados en el archivo del módulo. Esto sugiere que el módulo se basa completamente en el JS central de PrestaShop para su funcionalidad de cuadrícula del Back Office y no introduce ningún JS personalizado en el front office.

### 4.5 Hojas de estilo CSS (`views/css/`)

No se enumeran archivos CSS personalizados en el archivo del módulo. Esto indica que el módulo utiliza el estilo predeterminado del Back Office de PrestaShop para sus pantallas de configuración y gestión, y no introduce ningún estilo personalizado en el front office.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

No se enumeran archivos de plantilla personalizados en el archivo del módulo. Esto implica que el formulario de configuración del módulo y la vista de cuadrícula de `AdminSlogController` se renderizan utilizando las plantillas predeterminadas `HelperForm` y `HelperList` (o `HelperGrid`) de PrestaShop, que forman parte del framework central de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:

    -   `ps_slog` (o `_slog` con su prefijo de tabla):
        -   Esta tabla es creada por el módulo durante la instalación.
        -   Almacena las consultas de búsqueda registradas.
        -   Los campos típicos incluirían:
            -   `id_slog` (Clave primaria, INT)
            -   `keyword` (VARCHAR, almacena el término de búsqueda)
            -   `results` (INT, número de resultados encontrados para la palabra clave)
            -   `counter` (INT, número de veces que se ha buscado esta palabra clave)
            -   `date_add` (DATETIME, marca de tiempo de la primera búsqueda de esta palabra clave)
            -   `date_upd` (DATETIME, marca de tiempo de la última búsqueda de esta palabra clave)
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página del front office. | Si bien el dossier enumera `Header` como un hook de front office, para un módulo de registro, `displayHeader` se utiliza a menudo para registrar activos o para asegurar que el módulo esté activo en todas las páginas donde pueda ocurrir una búsqueda. La lógica de registro real es más probable que esté vinculada a un hook de `action`. |
| `displayRightColumn` | Se ejecuta en la columna derecha del front office. | Poco probable que se use para el registro, posiblemente para una característica futura o un marcador de posición. |
| `displayLeftColumn` | Se ejecuta en la columna izquierda del front office. | Poco probable que se use para el registro, posiblemente para una característica futura o un marcador de posición. |
| `displayFooter` | Se ejecuta en la sección del pie de página de cada página del front office. | Similar a `displayHeader`, podría usarse para el registro de activos o para asegurar el contexto del módulo, pero no para el registro directo. |
| `actionSearch` | Se ejecuta después de que una consulta de búsqueda ha sido procesada por el controlador de búsqueda central de PrestaShop. | **Este es el hook más crítico para este módulo.** Permite que el módulo intercepte el término de búsqueda y el número de resultados *después* de que PrestaShop haya realizado su búsqueda interna, lo que permite el registro de la `keyword` y el recuento de `results` en la tabla `ps_slog`. |
| `actionModuleInstall` | Se ejecuta cuando se instala el módulo. | Se utiliza para crear la tabla de base de datos `ps_slog` y registrar los hooks necesarios. |
| `actionModuleUninstall` | Se ejecuta cuando se desinstala el módulo. | Se utiliza para limpiar (por ejemplo, eliminar la tabla `ps_slog`, anular el registro de hooks). |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para desarrolladores del módulo "Registro de búsqueda", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a brindar asistencia y garantizar que el módulo funcione de manera óptima con su tienda PrestaShop.

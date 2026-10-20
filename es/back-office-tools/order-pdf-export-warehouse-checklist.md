---
title: "Exportación de PDF de Pedidos y Lista de Verificación de Almacén - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Order PDF Export & Warehouse Checklist' de MyPresta.eu."
sidebar:
  label: "Exportación de PDF de Pedidos y Lista de Verificación de Almacén - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Order PDF Export & Warehouse Checklist en MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-pdf-export-warehouse-checklist.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/order-pdf-export-warehouse-checklist/)
>
> ---


# Exportación de PDF de Pedidos y Lista de Verificación de Almacén

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento compatibles con PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Para acceder a esta pantalla, navegue a **Módulos > Gestor de Módulos**, busque "Order PDF Export & Warehouse Checklist" y haga clic en "Configurar".

#### **Plantilla PDF**

- **Qué hace este ajuste:** Le permite elegir el diseño visual y la maquetación para los documentos PDF generados por el módulo. Puede seleccionar entre una variedad de plantillas prediseñadas.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en 'Clean':* Sus PDFs tendrán un aspecto minimalista y moderno.
  - *Cuando se establece en 'Warehouse Big':* El PDF estará optimizado para uso en almacén, potencialmente con fuentes más grandes y secciones claras para la recogida.
  - *Cuando se establece en 'Retro':* Sus PDFs adoptarán un diseño de inspiración vintage.
- **Valor recomendado:** Comience con 'Clean' o 'Warehouse Big' dependiendo de su caso de uso principal (albarán para el cliente vs. lista de recogida interna). Experimente para encontrar el mejor ajuste para su marca y necesidades operativas.
- **Escenario / ejemplo del comerciante:** Si desea que sus albaranes reflejen una imagen de marca moderna y profesional, podría elegir 'Clean' o 'Elegant Serif'. Si su objetivo principal es proporcionar una lista de recogida altamente legible para el personal del almacén, 'Warehouse Big' podría ser más adecuado.

#### **Habilitar Actualizaciones de MyPresta.eu** (mypresta\_updates)

- **Qué hace este ajuste:** Controla si el módulo puede buscar y notificarle sobre las actualizaciones disponibles de MyPresta.eu.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (Sí):* El módulo buscará periódicamente nuevas versiones, asegurándose de que esté al día con las últimas características, correcciones de errores y mejoras de compatibilidad. Es posible que vea notificaciones en su back office de PrestaShop cuando haya una actualización disponible.
  - *Cuando está deshabilitado (No):* El módulo no buscará actualizaciones. Tendrá que verificar manualmente su cuenta de MyPresta.eu para nuevas versiones.
- **Valor recomendado:** **Sí**. Mantener los módulos actualizados es crucial para la seguridad, el rendimiento y la compatibilidad con las nuevas versiones de PrestaShop.
- **Escenario / ejemplo del comerciante:** Habilitar esto asegura que siempre esté ejecutando la versión más estable y rica en funciones del módulo sin tener que verificar constantemente de forma manual.

#### **Versión de Actualización** (update\_) y **Valor de Versión de Actualización** (updatev\_)

- **Qué hacen estos ajustes:** Son ajustes internos utilizados por el módulo para gestionar su mecanismo de actualización. Almacenan información sobre la última versión disponible o la versión actualmente instalada.
- **Efecto de cambiar este ajuste:** Estos **no deben ser cambiados manualmente** por el comerciante. Alterarlos podría interferir con la capacidad del módulo para buscar y aplicar actualizaciones correctamente.
- **Valor recomendado:** Deje estos ajustes tal como están. Son gestionados automáticamente por el módulo.
- **Escenario / ejemplo del comerciante:** Normalmente no interactuará con estos ajustes. Son parte de la lógica de actualización interna del módulo.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

El módulo añade nuevos elementos de menú bajo **Pedidos** en su Back Office de PrestaShop, permitiéndole gestionar las categorías y elementos de su lista de verificación de almacén.

#### **Nombre de la Pantalla: Categorías de la Lista de Verificación**

- **Ubicación del Menú:** Back Office > Pedidos > **Categorías de la Lista de Verificación**
- **Acciones y Ajustes Disponibles:** Esta pantalla le permite crear, editar y eliminar categorías para su lista de verificación de almacén. Piense en las categorías como agrupaciones lógicas para sus elementos de la lista de verificación (por ejemplo, "Calidad del Embalaje", "Verificación del Producto", "Documentos de Envío").
  - **Añadir una Nueva Categoría:** Haga clic en "Añadir nueva categoría" para definir un nuevo grupo. Normalmente, proporcionará un nombre para la categoría (por ejemplo, "Inspección de Producto").
  - **Editar/Eliminar Categorías:** Puede modificar categorías existentes o eliminarlas si ya no son necesarias.
- **Efecto de los cambios:**
  - *Añadir una categoría:* Crea una nueva sección bajo la cual podrá añadir elementos específicos de la lista de verificación más adelante.
  - *Modificar una categoría:* Cambia el nombre o las propiedades de una categoría existente.
  - *Eliminar una categoría:* Elimina la categoría y cualquier elemento de la lista de verificación asociado del sistema. Esto ya no aparecerá en sus PDFs generados.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Comience definiendo categorías amplias que reflejen su proceso de almacén. Por ejemplo: "Precisión del Pedido", "Integridad del Embalaje", "Documentación".
  2. Asegúrese de que los nombres de las categorías sean claros y descriptivos para su personal.

#### **Nombre de la Pantalla: Elementos de la Lista de Verificación**

- **Ubicación del Menú:** Back Office > Pedidos > **Elementos de la Lista de Verificación**
- **Acciones y Ajustes Disponibles:** Esta pantalla es donde define los elementos reales que aparecerán en su lista de verificación de almacén dentro del PDF. Cada elemento puede asignarse a una categoría que haya creado previamente.
  - **Añadir un Nuevo Elemento:** Haga clic en "Añadir nuevo elemento". Especificará:
    - **Nombre:** El texto del elemento de la lista de verificación (por ejemplo, "¿Todos los artículos presentes y contabilizados?").
    - **Categoría:** Asígnelo a una de las categorías que definió (por ejemplo, "Precisión del Pedido").
    - **Activo:** Si este elemento debe aparecer en la lista de verificación.
  - **Editar/Eliminar Elementos:** Modifique o elimine elementos individuales de la lista de verificación.
- **Efecto de los cambios:**
  - *Añadir un elemento:* El nuevo elemento aparecerá en la lista de verificación del PDF generado bajo su categoría asignada.
  - *Modificar un elemento:* Cambia el texto o la categoría de un elemento existente de la lista de verificación.
  - *Eliminar un elemento:* Elimina el elemento de la lista de verificación en los PDFs.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Una vez configuradas las categorías, rellénelas con elementos de la lista de verificación específicos y accionables.
  2. Ejemplos: "¿La cantidad del producto coincide con el pedido?", "¿Artículos frágiles correctamente amortiguados?", "¿Etiqueta de envío correcta?", "¿Factura incluida?".
  3. Revise y actualice regularmente los elementos de su lista de verificación para reflejar los cambios en sus productos, embalajes o procedimientos de envío.

#### **Nombre de la Pantalla: Lista de Pedidos (con Botón de Exportación)**

- **Ubicación del Menú:** Back Office > Pedidos > **Pedidos**
- **Acciones y Ajustes Disponibles:** Este módulo se integra directamente en su lista de Pedidos estándar de PrestaShop. Encontrará nuevos botones u opciones para generar PDFs para pedidos individuales o, potencialmente, de forma masiva.
  - **Exportación de Pedido Individual:** Al ver un pedido específico en el Back Office, verá un nuevo botón (por ejemplo, "Exportar PDF" o "Imprimir Lista de Recogida") que le permite generar el PDF personalizado para ese pedido.
  - **Exportación de Pedidos Masiva:** (Dependiendo de la versión del módulo y la versión de PrestaShop) Es posible que pueda seleccionar varios pedidos de la lista de pedidos y generar PDFs para todos ellos a la vez.
- **Efecto de los cambios:** Al hacer clic en estos botones, se descargará un documento PDF en su ordenador, formateado según la plantilla elegida e incluyendo su lista de verificación personalizada.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Después de que se realiza y valida un pedido, navegue a la lista de Pedidos.
  2. Abra el pedido específico que necesita cumplir.
  3. Haga clic en el botón "Exportar PDF" para generar la lista de recogida/albarán con la lista de verificación.
  4. Imprima el PDF y entrégueselo a su personal de almacén para su cumplimiento.
  5. El personal utiliza el PDF para recoger artículos, verificar la precisión utilizando la lista de verificación y, potencialmente, recoger firmas antes de embalar.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Plantilla PDF | Clean / Warehouse Big | Selecciona el diseño visual de los documentos PDF generados. |
| **Configuración del Módulo** | Habilitar Actualizaciones de MyPresta.eu | Sí | Permite que el módulo busque y notifique sobre nuevas versiones. |
| **Categorías de la Lista de Verificación** | Añadir/Editar/Eliminar Categoría | N/A | Gestiona las agrupaciones lógicas para los elementos de su lista de verificación de almacén. |
| **Elementos de la Lista de Verificación** | Añadir/Editar/Eliminar Elemento | N/A | Define los elementos específicos que aparecen en su lista de verificación de almacén dentro del PDF. |
| **Lista de Pedidos / Vista de Pedido** | Botón Exportar PDF | N/A | Genera un documento PDF para el/los pedido(s) seleccionado(s) utilizando la plantilla y la lista de verificación configuradas. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: El PDF se ve extraño o tiene problemas de formato. ¿Qué debo hacer?**
R:

1. **Borrar Caché de Smarty:** Vaya a **Parámetros Avanzados > Rendimiento** en su Back Office de PrestaShop. Desplácese hasta "Caché" y haga clic en "Borrar caché". A veces, los archivos de plantilla antiguos pueden causar problemas de visualización.
2. **Probar una Plantilla de PDF Diferente:** En la configuración del módulo, intente seleccionar una "Plantilla PDF" diferente para ver si el problema es específico de un diseño.
3. **Verificar Conflictos de Tema:** Si está utilizando un tema muy personalizado, podría tener CSS o JS que interfiera. Cambie temporalmente al tema predeterminado de PrestaShop (por ejemplo, Classic) y vuelva a probar. Si funciona, su tema podría requerir ajustes.
4. **Contactar con Soporte:** Si los problemas persisten, recopile capturas de pantalla y detalles, luego contacte con el soporte de MyPresta.eu.

**P: Mis elementos personalizados de la lista de verificación no aparecen en el PDF.**
R:

1. **Verificar "Categorías de la Lista de Verificación":** Asegúrese de haber creado categorías en **Pedidos > Categorías de la Lista de Verificación**.
2. **Verificar "Elementos de la Lista de Verificación":** Verifique que haya añadido elementos en **Pedidos > Elementos de la Lista de Verificación** y que estén asignados a una categoría activa. Además, asegúrese de que el interruptor "Activo" para cada elemento esté configurado en "Sí".
3. **Configuración del Módulo:** Asegúrese de que el módulo esté correctamente configurado y guardado.

**P: No veo el botón "Exportar PDF" en mis páginas de pedidos.**
R:

1. **Módulo Instalado y Habilitado:** Verifique que el módulo esté instalado y habilitado en **Módulos > Gestor de Módulos**.
2. **Permisos:** Asegúrese de que su perfil de empleado tenga los permisos necesarios para acceder y usar este módulo. Vaya a **Parámetros Avanzados > Equipo > Perfiles** y verifique los permisos para el perfil asignado a su cuenta de empleado.
3. **Versión de PrestaShop:** Confirme que su versión de PrestaShop sea compatible (1.7.x, 8.x, 9.x).
4. **Borrar Caché:** Borre la caché de su PrestaShop (**Parámetros Avanzados > Rendimiento**).

**P: ¿Puedo personalizar aún más las plantillas de PDF (por ejemplo, añadir mi logotipo, cambiar fuentes)?**
R: Sí, pero esto requiere conocimientos técnicos. El módulo proporciona varias plantillas, pero para una personalización profunda (como añadir su logotipo específico, cambiar fuentes o alterar el diseño más allá de lo que ofrecen los ajustes del módulo), necesitaría:

1. **Identificar el Archivo de Plantilla:** Localice el archivo `.tpl` de la plantilla de PDF elegida dentro del directorio `pdf/en/` del módulo.
2. **Editar la Plantilla:** Esto implica editar el código de la plantilla Smarty y, potencialmente, HTML/CSS. Esta es una tarea para un webmaster o desarrollador.
3. **Considerar una Plantilla Personalizada:** Para cambios significativos, a menudo es mejor crear una nueva plantilla personalizada en lugar de modificar los archivos principales del módulo, para asegurar que sus cambios no sean sobrescritos durante las actualizaciones del módulo.

**P: El módulo no busca actualizaciones.**
R:

1. **Habilitar Verificación de Actualizaciones:** Vaya a la página de configuración del módulo (**Módulos > Gestor de Módulos > Configurar** para "Order PDF Export & Warehouse Checklist") y asegúrese de que "Habilitar Actualizaciones de MyPresta.eu" esté configurado en "Sí".
2. **Conectividad del Servidor:** Asegúrese de que su servidor tenga acceso a Internet saliente para conectarse a los servidores de actualización de MyPresta.eu. Esto podría implicar verificar la configuración del firewall o del proxy con su proveedor de alojamiento.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una visión técnica detallada del módulo "Order PDF Export & Warehouse Checklist" para desarrolladores y webmasters.

### 4.1 Visión General de la Arquitectura

El módulo sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, extendiendo principalmente `Module` para su funcionalidad principal y `AdminController` para sus pantallas de gestión del Back Office. Utiliza `ObjectModel` para gestionar entidades de base de datos personalizadas (categorías y elementos de la lista de verificación). La generación de PDF es manejada por una clase dedicada (`OrderPdfGenerator`) que utiliza plantillas Smarty para renderizar el contenido del PDF, probablemente integrándose con una biblioteca como Dompdf o TCPDF (aunque la biblioteca específica no se menciona explícitamente, la estructura `.tpl` sugiere un motor de renderizado). Los hooks se utilizan para integrar la funcionalidad del módulo en el Back Office de PrestaShop, particularmente para añadir botones de exportación de PDF a las páginas de pedidos.

### 4.2 Controladores (`controllers/`)

#### Controladores de Administración del Back-Office

- `orderexportpdf/controllers/admin/AdminOrderExportChecklistCategoriesController.php`

  - **Nombre de la Clase:** `AdminOrderExportChecklistCategoriesController`
  - **Clase Padre:** `ModuleAdminController`
  - **Responsabilidad:** Gestiona las operaciones CRUD (Crear, Leer, Actualizar, Eliminar) para los objetos `OrderExportChecklistCategory`. Proporciona la interfaz del Back Office para listar, añadir, editar y eliminar categorías de la lista de verificación. Este controlador se mapea al elemento de menú "Categorías de la Lista de Verificación" bajo "Pedidos".
  - **Nombre de la Pestaña:** Checklist Categories
  - **Entidad Gestionada:** `OrderExportChecklistCategory` (mapeada a la tabla `ps_orderexport_checklist_cat`).
- `orderexportpdf/controllers/admin/AdminOrderExportChecklistElementsController.php`

  - **Nombre de la Clase:** `AdminOrderExportChecklistElementsController`
  - **Clase Padre:** `ModuleAdminController`
  - **Responsabilidad:** Gestiona las operaciones CRUD para los objetos `OrderExportChecklistElement`. Proporciona la interfaz del Back Office para listar, añadir, editar y eliminar elementos individuales de la lista de verificación, permitiendo la asignación a categorías. Este controlador se mapea al elemento de menú "Elementos de la Lista de Verificación" bajo "Pedidos".
  - **Nombre de la Pestaña:** Checklist Elements
  - **Entidad Gestionada:** `OrderExportChecklistElement` (mapeada a la tabla `ps_orderexport_checklist_elem`).
- `orderexportpdf/controllers/admin/index.php`

  - **Responsabilidad:** Este es típicamente un archivo vacío o un archivo que contiene una declaración de seguridad `die()` para evitar la lista directa de directorios. No contiene lógica de controlador en sí mismo.

### 4.3 Clases y Modelos Principales (`classes/`)

- `orderexportpdf/classes/index.php`

  - **Responsabilidad:** Archivo de seguridad estándar de PrestaShop, generalmente contiene `<?php exit;` para evitar la lista de directorios.
- `orderexportpdf/classes/OrderExport.php`

  - **Nombre de la Clase:** `OrderExport`
  - **Clase Padre:** `Object` (probablemente, o una clase base personalizada)
  - **Responsabilidad:** Esta clase probablemente contiene métodos de ayuda o lógica central relacionada con el proceso general de exportación de pedidos, posiblemente manejando la recuperación de datos, el formato o la interacción con la clase de generación de PDF. Podría no ser un `ObjectModel` sino una clase de utilidad.
- `orderexportpdf/classes/OrderExportChecklistCategory.php`

  - **Nombre de la Clase:** `OrderExportChecklistCategory`
  - **Clase Padre:** `ObjectModel`
  - **Tabla de Base de Datos:** `ps_orderexport_checklist_cat`
  - **Campos `$definition`:** Define la estructura de una categoría de la lista de verificación, incluyendo campos como `id_orderexport_checklist_cat`, `name` (multilenguaje), `active`, `position`.
  - **Métodos Públicos Clave:** Métodos estándar de `ObjectModel` (`add`, `update`, `delete`, `getFields`, `validateFields`, `validateController`). Puede incluir métodos para recuperar todas las categorías activas o categorías por ID.
- `orderexportpdf/classes/OrderExportChecklistElement.php`

  - **Nombre de la Clase:** `OrderExportChecklistElement`
  - **Clase Padre:** `ObjectModel`
  - **Tabla de Base de Datos:** `ps_orderexport_checklist_elem`
  - **Campos `$definition`:** Define la estructura de un elemento de la lista de verificación, incluyendo campos como `id_orderexport_checklist_elem`, `id_orderexport_checklist_cat` (clave foránea), `name` (multilenguaje), `active`, `position`.
  - **Métodos Públicos Clave:** Métodos estándar de `ObjectModel`. Puede incluir métodos para recuperar elementos por categoría, o todos los elementos activos.
- `orderexportpdf/classes/OrderPdfGenerator.php`

  - **Nombre de la Clase:** `OrderPdfGenerator`
  - **Clase Padre:** Probablemente `Object` o una clase base personalizada.
  - **Responsabilidad:** Esta es la clase principal responsable de generar los documentos PDF. Toma un ID de pedido, la plantilla seleccionada y los datos de la lista de verificación, luego renderiza el contenido en formato PDF. Probablemente utiliza una biblioteca de PDF de terceros (por ejemplo, Dompdf, mPDF) internamente.
  - **Métodos Públicos Clave:** `generatePdf($orderId, $templateName, $checklistData)`, `renderTemplate($templatePath, $data)`, `downloadPdf()`.

### 4.4 Activos JavaScript (`views/js/`)

- `orderexportpdf/lib/pdfTemplatesManager/js/pdfTemplatesManager.js`

  - **Ámbito:** Back-office.
  - **Responsabilidad:** Probablemente maneja la gestión dinámica de plantillas PDF dentro de la interfaz de configuración del módulo. Esto podría incluir llamadas AJAX para guardar la configuración de la plantilla, previsualizar plantillas o cambiar entre diferentes opciones de plantilla.
- `orderexportpdf/views/js/order-list-legacy.js`

  - **Ámbito:** Back-office (para PrestaShop 1.7.x o versiones anteriores que usan JS heredado).
  - **Responsabilidad:** Integra la funcionalidad del botón de exportación de PDF en la vista de lista de pedidos del Back Office de PrestaShop para versiones anteriores de PrestaShop. Vincula eventos de clic a los botones, potencialmente realiza llamadas AJAX para activar la generación de PDF y maneja la descarga del PDF generado.
- `orderexportpdf/views/js/order-list-modern.js`

  - **Ámbito:** Back-office (para PrestaShop 8.x, 9.x o versiones más nuevas que usan JS moderno).
  - **Responsabilidad:** Similar a `order-list-legacy.js`, pero adaptado para interfaces de Back Office de PrestaShop más nuevas y potencialmente utilizando prácticas modernas de JavaScript (por ejemplo, ES6, activos compilados con Webpack). Asegura que el botón de exportación de PDF se muestre y funcione correctamente en la lista de pedidos y en las páginas de vista de pedidos individuales.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `orderexportpdf/lib/pdfTemplatesManager/css/pdfTemplatesManager.css`

  - **Ámbito:** Estilo del formulario de administración del Back-office.
  - **Responsabilidad:** Proporciona estilo para la interfaz de configuración del módulo, específicamente para la sección del gestor de plantillas PDF. Esto podría incluir estilos para botones, desplegables, áreas de vista previa o elementos de formulario relacionados con la selección de plantillas.
- `orderexportpdf/views/css/order-export.css`

  - **Ámbito:** Estilo del formulario de administración del Back-office.
  - **Responsabilidad:** Estilo general para los componentes del Back Office del módulo, como las pantallas de gestión de categorías y elementos de la lista de verificación, o potencialmente estilo para los botones añadidos en las páginas de pedidos.
  - **Selectores de clase CSS clave:** Los desarrolladores pueden inspeccionar el HTML generado en busca de clases como `.orderexportpdf-button`, `.orderexport-checklist-table`, etc., para anular estilos en su tema de administración personalizado.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

- `orderexportpdf/lib/pdfTemplatesManager/views/buttonManager.tpl`

  - **Hook:** Probablemente renderizado en un hook dentro de la configuración del módulo o en una página de pedido de administración para mostrar botones relacionados con la gestión de plantillas (por ejemplo, "Gestionar Plantillas", "Crear Nueva Plantilla").
  - **Salida:** HTML para botones o enlaces para gestionar plantillas PDF.
- `orderexportpdf/lib/pdfTemplatesManager/views/createTemplateForm.tpl`

  - **Hook:** Interno al gestor de plantillas del módulo, mostrado al crear una nueva plantilla PDF.
  - **Salida:** Formulario HTML para definir propiedades de una nueva plantilla PDF.
- `orderexportpdf/lib/pdfTemplatesManager/views/editTemplateForm.tpl`

  - **Hook:** Interno al gestor de plantillas del módulo, mostrado al editar una plantilla PDF existente.
  - **Salida:** Formulario HTML para modificar propiedades de una plantilla PDF existente.
- `orderexportpdf/lib/pdfTemplatesManager/views/mainForm.tpl`

  - **Hook:** El formulario de configuración principal para el módulo (por ejemplo, método `getContent()`).
  - **Salida:** El formulario HTML principal que contiene el desplegable de selección de "Plantilla PDF" y otros ajustes a nivel de módulo.
- `orderexportpdf/lib/pdfTemplatesManager/views/selectInput.tpl`

  - **Hook:** Una plantilla parcial reutilizable, probablemente incluida en `mainForm.tpl` u otros formularios, para renderizar una entrada desplegable (`<select>`) para elegir plantillas.
  - **Salida:** HTML para un elemento `<select>` poblado con las plantillas PDF disponibles.
- `orderexportpdf/pdf/en/*.tpl` (por ejemplo, `blue-line-dompdf.tpl`, `boxed-layout-dompdf.tpl`, `clean-dompdf.tpl`, `warehouse-big-dompdf.tpl`, etc.)

  - **Hook:** Estas **no** son plantillas de hook de PrestaShop. Estas son las **plantillas de diseño de PDF** reales utilizadas por `OrderPdfGenerator` para renderizar el contenido de la lista de recogida/albarán. Se eligen a través de la configuración del módulo.
  - **Salida:** Estructura HTML/CSS que se convertirá en un documento PDF. Estas plantillas contienen marcadores de posición para detalles del pedido, listas de productos, información del cliente y la lista de verificación personalizada.
  - **Nota:** El sufijo `dompdf` sugiere el uso de la biblioteca Dompdf para la conversión de HTML a PDF.
- `orderexportpdf/pdf/fr/kids-play.tpl`

  - **Hook:** Similar a las plantillas `en`, pero una versión específica en francés del diseño de PDF 'kids-play'. Esto indica soporte multilingüe para plantillas PDF.
- `orderexportpdf/pdf/en/order-export.tpl`

  - **Hook:** Esta podría ser una plantilla base genérica o una plantilla de respaldo para la generación de PDF.
  - **Salida:** Una estructura general para el PDF de exportación de pedidos.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

- `ps_orderexport_checklist_cat`: Almacena información sobre las categorías personalizadas de la lista de verificación.

  - `id_orderexport_checklist_cat` (Clave Primaria, INT)
  - `name` (VARCHAR, Multilingüe): El nombre de la categoría de la lista de verificación.
  - `active` (TINYINT): Si la categoría está activa.
  - `position` (INT): Orden de visualización de las categorías.
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_orderexport_checklist_elem`: Almacena información sobre los elementos individuales de la lista de verificación.

  - `id_orderexport_checklist_elem` (Clave Primaria, INT)
  - `id_orderexport_checklist_cat` (Clave Foránea a `ps_orderexport_checklist_cat`, INT): La categoría a la que pertenece este elemento.
  - `name` (VARCHAR, Multilingüe): El texto del elemento de la lista de verificación.
  - `active` (TINYINT): Si el elemento está activo.
  - `position` (INT): Orden de visualización de los elementos dentro de una categoría.
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_configuration`: El módulo almacena sus principales ajustes de configuración aquí.

  - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: (Ajuste central de PrestaShop, no específico del módulo)
  - `MYPRESTA_UPDATES`: (Ajuste del módulo) Almacena el estado de la verificación de actualizaciones (1 para habilitado, 0 para deshabilitado).
  - `UPDATE_`: (Ajuste del módulo) Seguimiento interno de la versión de actualización.
  - `UPDATEV_`: (Ajuste del módulo) Valor interno de la versión de actualización.
  - `ORDEREXPORTPDF_TEMPLATE`: (Ajuste del módulo) Almacena el nombre de la plantilla PDF actualmente seleccionada.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un AdminController carga sus activos. | Inyecta CSS (`order-export.css`, `pdfTemplatesManager.css`) y JavaScript (`order-list-legacy.js`, `order-list-modern.js`, `pdfTemplatesManager.js`) específicos del módulo en el Back Office, particularmente para las páginas de pedidos y la configuración del módulo. |
| `displayAdminOrder` | Se ejecuta en la página de vista de pedido individual en el Back Office. | Renderiza el botón "Exportar PDF" o un widget similar en la página de detalles del pedido, permitiendo la generación de PDF de un solo pedido. |
| `actionGetAdminOrderButtons` | Se ejecuta para permitir que los módulos añadan botones personalizados a la vista de pedido de administración. | Proporciona un mecanismo para inyectar botones personalizados (como "Exportar PDF") en la vista de pedidos de PrestaShop 1.7+, asegurando la compatibilidad con la interfaz de usuario moderna. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y para descargar las últimas versiones del módulo "Order PDF Export & Warehouse Checklist", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad o configuración del módulo.

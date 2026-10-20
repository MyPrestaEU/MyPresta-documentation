---
title: "Omnibus Directive Pro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo PrestaShop Omnibus Directive Pro de MyPresta.eu."
sidebar:
  label: "Omnibus Directive Pro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Omnibus Directive Pro en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/omnibus-directive-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/omnibus-directive-pro/)
>
> ---


# Omnibus Directive Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Omnibus Directive Pro)

Esta es la pantalla de configuración principal donde controlas el comportamiento central y las opciones de visualización del módulo Omnibus Directive Pro.

#### Ajustes Generales

- **Activar Módulo:**

  - **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar la funcionalidad completa del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El módulo comenzará a rastrear precios, mostrará la información del precio más bajo y todas las demás funciones configuradas se activarán.
    - *Cuando está desactivado:* El módulo detendrá todas sus operaciones, incluido el seguimiento de precios y la visualización en el front-office. No se mostrará información del precio más bajo.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Actívalo después de la instalación para empezar a cumplir con la directiva. Desactívalo solo si necesitas pausar temporalmente su funcionalidad por mantenimiento o pruebas específicas.
- **Mostrar Precio Más Bajo en la Página de Producto:**

  - **Qué hace este ajuste:** Controla si la insignia o el texto del "precio más bajo en los últimos 30 días" aparece en las páginas de productos individuales cuando un producto está en oferta.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* La información del precio más bajo será visible para los clientes en cada página de producto donde haya una reducción de precio activa.
    - *Cuando está desactivado:* La información del precio más bajo NO se mostrará en las páginas de producto, incluso si un producto está en oferta.
  - **Valor recomendado:** SÍ (Altamente recomendado para el cumplimiento).
  - **Escenario / ejemplo de comerciante:** Debes activar esto para cumplir con la Directiva Ómnibus. Si lo desactivas, tus páginas de producto no mostrarán la información requerida durante las ventas.
- **Mostrar Precio Más Bajo en Listados de Productos (Categoría, Búsqueda, etc.):**

  - **Qué hace este ajuste:** Determina si la información del precio más bajo se muestra en las tarjetas de producto en las listas (por ejemplo, páginas de categoría, resultados de búsqueda, páginas de fabricante).
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* La insignia del precio más bajo aparecerá en las tarjetas de producto en las vistas de listado, proporcionando transparencia temprana a los clientes.
    - *Cuando está desactivado:* La información del precio más bajo solo aparecerá en la página de producto individual, no en los listados.
  - **Valor recomendado:** SÍ (Recomendado para máxima transparencia y visibilidad del cumplimiento).
  - **Escenario / ejemplo de comerciante:** Habilitar esto ayuda a los clientes a identificar rápidamente las ventas conformes directamente desde las páginas de categoría, lo que podría aumentar las tasas de clics a las páginas de producto.
- **Activar Gráfico de Precios en la Página de Producto:**

  - **Qué hace este ajuste:** Activa un gráfico interactivo en la página de producto que muestra visualmente el historial de precios del producto a lo largo del tiempo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Se incrustará un gráfico en la página de producto, permitiendo a los clientes ver las fluctuaciones de precios pasadas.
    - *Cuando está desactivado:* El gráfico de precios no se mostrará.
  - **Valor recomendado:** SÍ (Mejora la transparencia y la confianza del cliente).
  - **Escenario / ejemplo de comerciante:** Los clientes sensibles al precio o que desean verificar la legitimidad de una venta pueden usar este gráfico. Añade una capa extra de confianza.
- **URL de Cron para Limpieza del Historial de Precios:**

  - **Qué hace este ajuste:** Proporciona una URL única que, al ser accedida, activa el proceso automatizado del módulo para limpiar datos antiguos del historial de precios. Esto mantiene tu base de datos optimizada.
  - **Efecto de cambiar este ajuste:** Este es un campo de solo lectura. Debes configurar una tarea cron en tu servidor para visitar esta URL regularmente.
  - **Valor recomendado:** Copia esta URL y configura una tarea cron.
  - **Escenario / ejemplo de comerciante:** Configura una tarea cron para ejecutar esta URL una vez al día (por ejemplo, a las 3 AM) para asegurar que tu base de datos de historial de precios se mantenga ligera y eficiente, evitando que crezca demasiado con el tiempo.
- **Activar Registro de Auditoría CSV:**

  - **Qué hace este ajuste:** Si está activado, el módulo generará un archivo CSV que contiene un registro detallado de los cambios de precios y los cálculos del precio más bajo, lo que puede ser útil para auditorías y verificación de cumplimiento.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Se generará y actualizará un archivo CSV con información de auditoría.
    - *Cuando está desactivado:* No se creará ni mantendrá ningún registro de auditoría.
  - **Valor recomendado:** NO (A menos que sea específicamente requerido para auditorías internas o fines legales, ya que puede consumir espacio en disco).
  - **Escenario / ejemplo de comerciante:** Si tu equipo legal o auditores requieren un registro verificable de tus actividades de cumplimiento, activa esto. De lo contrario, generalmente no es necesario para el funcionamiento diario.

#### Estudio de Insignias

Esta sección te permite personalizar la apariencia visual de la insignia de "precio más bajo" que se muestra en tu tienda.

- **Tipo de Insignia:**

  - **Qué hace este ajuste:** Elige entre una "Insignia Inteligente" (altamente personalizable con iconos, colores y texto) o una visualización de "Texto Simple".
  - **Efecto de cambiar este ajuste:**
    - *Insignia Inteligente:* Desbloquea más opciones de personalización para una insignia visualmente rica.
    - *Texto Simple:* Muestra solo texto plano sin estilos avanzados.
  - **Valor recomendado:** Insignia Inteligente (Ofrece más control y mejor integración con tu tema).
  - **Escenario / ejemplo de comerciante:** Si quieres una insignia prominente y de marca, elige "Insignia Inteligente". Si prefieres un enfoque minimalista, "Texto Simple" podría ser mejor.
- **Posición de la Insignia (Página de Producto):**

  - **Qué hace este ajuste:** Selecciona dónde aparece la insignia en la página de producto. Las opciones suelen incluir "Cerca del Precio", "Debajo del Precio", "Hook Personalizado", etc.
  - **Efecto de cambiar este ajuste:** Cambia la ubicación visual de la insignia en la página de producto.
  - **Valor recomendado:** Cerca del Precio (La ubicación más común y legalmente clara).
  - **Escenario / ejemplo de comerciante:** Prueba diferentes posiciones para ver cuál se integra mejor con tu tema y es más visible para los clientes sin ser intrusiva.
- **Posición de la Insignia (Listados de Productos):**

  - **Qué hace este ajuste:** Selecciona dónde aparece la insignia en las tarjetas de producto en las páginas de listado. Las opciones suelen incluir "Debajo del Nombre del Producto", "Debajo del Precio", "Hook Personalizado", etc.
  - **Efecto de cambiar este ajuste:** Cambia la ubicación visual de la insignia en las tarjetas de producto.
  - **Valor recomendado:** Debajo del Precio (Claro y consistente con la ubicación en la página de producto).
  - **Escenario / ejemplo de comerciante:** Asegúrate de que la insignia no se superponga con otros elementos en tus tarjetas de producto, especialmente en dispositivos móviles.
- **Texto de la Insignia:**

  - **Qué hace este ajuste:** Personaliza el texto real que se muestra dentro de la insignia. Puedes usar marcadores de posición como `{lowest_price}` para el valor real del precio más bajo.
  - **Efecto de cambiar este ajuste:** Cambia el mensaje que leen los clientes.
  - **Valor recomendado:** "Precio más bajo en los últimos 30 días: {lowest\_price}" (Claro y conforme).
  - **Escenario / ejemplo de comerciante:** Podrías traducir este texto para diferentes idiomas o reformularlo ligeramente para que se ajuste al tono de tu marca, siempre que el significado siga siendo claro y conforme.
- **Color de Fondo de la Insignia:**

  - **Qué hace este ajuste:** Establece el color de fondo de la Insignia Inteligente.
  - **Efecto de cambiar este ajuste:** Cambia el fondo visual de la insignia.
  - **Valor recomendado:** Un color que contraste bien con tu texto y tema, por ejemplo, un gris claro o un color de acento de la marca.
  - **Escenario / ejemplo de comerciante:** Elige un color que haga que la insignia destaque pero que siga siendo profesional y se integre con el diseño de tu tienda.
- **Color del Texto de la Insignia:**

  - **Qué hace este ajuste:** Establece el color del texto dentro de la Insignia Inteligente.
  - **Efecto de cambiar este ajuste:** Cambia el color visual del texto.
  - **Valor recomendado:** Un color que sea altamente legible contra el color de fondo elegido, por ejemplo, negro o gris oscuro.
  - **Escenario / ejemplo de comerciante:** Asegura un alto contraste para la accesibilidad y la legibilidad.
- **Icono de la Insignia:**

  - **Qué hace este ajuste:** Te permite seleccionar un icono para mostrar junto al texto en la Insignia Inteligente.
  - **Efecto de cambiar este ajuste:** Añade un icono visual a la insignia.
  - **Valor recomendado:** Un icono relevante, como una "etiqueta" o un icono de "información".
  - **Escenario / ejemplo de comerciante:** Un icono pequeño y claro puede llamar la atención sobre la insignia y hacer que su propósito sea más intuitivo.

#### Panel de Análisis

Esta sección proporciona información sobre el rendimiento de tu módulo y el estado de cumplimiento.

- **Ver Análisis:**
  - **Qué hace este ajuste:** Este botón abre un panel dedicado dentro de tu Back Office, mostrando estadísticas relacionadas con el seguimiento de precios, productos en oferta y el estado de cumplimiento.
  - **Efecto de cambiar este ajuste:** Al hacer clic en este botón, navegas al panel de análisis.
  - **Valor recomendado:** Revísalo regularmente.
  - **Escenario / ejemplo de comerciante:** Utiliza el panel de análisis para monitorear cuántos productos están mostrando actualmente el precio más bajo, identificar posibles problemas o revisar el estado general de cumplimiento de tu tienda.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Activar Módulo | SÍ | Activa/desactiva todas las funciones del módulo. |
|  | Mostrar Precio Más Bajo en la Página de Producto | SÍ | Muestra el precio más bajo de los últimos 30 días en las páginas de producto durante las ventas. |
|  | Mostrar Precio Más Bajo en Listados de Productos | SÍ | Muestra el precio más bajo de los últimos 30 días en las páginas de categoría/búsqueda durante las ventas. |
|  | Activar Gráfico de Precios en la Página de Producto | SÍ | Muestra un gráfico interactivo del historial de precios en las páginas de producto. |
|  | URL de Cron para Limpieza del Historial de Precios | (Copiar y Configurar) | URL para la limpieza automatizada de la base de datos. Ejecutar diariamente. |
|  | Activar Registro de Auditoría CSV | NO | Crea un registro detallado de los cambios de precios para auditoría. |
| **Estudio de Insignias** | Tipo de Insignia | Insignia Inteligente | Elige entre insignia personalizable o texto simple. |
|  | Posición de la Insignia (Página de Producto) | Cerca del Precio | Establece la ubicación de la insignia en las páginas de producto individuales. |
|  | Posición de la Insignia (Listados de Productos) | Debajo del Precio | Establece la ubicación de la insignia en las tarjetas de producto en los listados. |
|  | Texto de la Insignia | "Precio más bajo en los últimos 30 días: {lowest\_price}" | Texto personalizable para la insignia. |
|  | Color de Fondo de la Insignia | (Depende del tema) | Establece el color de fondo de la Insignia Inteligente. |
|  | Color del Texto de la Insignia | (Depende del tema) | Establece el color del texto de la Insignia Inteligente. |
|  | Icono de la Insignia | (Icono relevante) | Añade un icono visual a la Insignia Inteligente. |
| **Panel de Análisis** | Ver Análisis | (Hacer clic en el botón) | Abre un panel para estadísticas de cumplimiento y seguimiento de precios. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: La insignia del precio más bajo no aparece en mis páginas de producto, aunque la he activado.**
R:

1. **Verifica el Estado del Módulo:** Asegúrate de que la configuración "Activar Módulo" esté en SÍ.
2. **¿Producto en Oferta?** La insignia solo aparece para productos que están actualmente en oferta (tienen un precio específico o un descuento aplicado). Asegúrate de que el producto que estás probando tenga una reducción de precio activa.
3. **Borrar Caché:** Ve a **Parámetros Avanzados > Rendimiento** en tu Back Office de PrestaShop y borra la caché de Smarty, la caché del navegador y cualquier otra caché (por ejemplo, caché CDN) que puedas estar utilizando.
4. **Compatibilidad del Tema:** Aunque el módulo está diseñado para una amplia compatibilidad, los temas muy personalizados podrían requerir ajustes menores. Si el problema persiste, contacta con el soporte de MyPresta.eu.

**P2: El gráfico del historial de precios no muestra datos o parece incompleto.**
R:

1. **Módulo Activado:** Asegúrate de que "Activar Gráfico de Precios en la Página de Producto" esté configurado en SÍ.
2. **Cambios de Precio:** El gráfico solo mostrará datos si el producto ha tenido cambios de precio registrados desde que el módulo fue instalado y activo. Si el precio de un producto nunca ha cambiado, no habrá historial que mostrar.
3. **Tiempo para Recopilar Datos:** El módulo tarda en recopilar el historial de precios. Si acabas de instalarlo, los datos se acumularán a medida que los precios cambien a lo largo de días/semanas.

**P3: ¿Con qué frecuencia debo ejecutar la Tarea Cron de Limpieza del Historial de Precios?**
R: Recomendamos ejecutar la tarea cron una vez cada 24 horas. Esta frecuencia es suficiente para mantener tu base de datos optimizada sin sobrecargar tu servidor.

**P4: El estilo de mi tema personalizado choca con la insignia del módulo. ¿Cómo puedo solucionarlo?**
R: El "Estudio de Insignias" ofrece una amplia personalización de colores, texto e iconos. Intenta ajustar primero estas configuraciones para que coincidan con tu tema. Si sigues teniendo conflictos de estilo, es posible que necesites un webmaster para aplicar anulaciones de CSS personalizadas. Los archivos CSS del módulo están diseñados para ser fácilmente anulados por la hoja de estilos de tu tema.

**P5: ¿Qué sucede si desactivo el módulo? ¿Borra mis datos de historial de precios?**
R: Desactivar el módulo detendrá su visualización en el front-office y sus procesos en segundo plano, pero normalmente no elimina los datos de historial de precios recopilados. Si lo vuelves a activar más tarde, los datos deberían seguir estando disponibles. Sin embargo, para una eliminación completa de datos, tendrías que desinstalar el módulo y elegir eliminar sus datos.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la arquitectura técnica del módulo Omnibus Directive Pro, destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Visión General de la Arquitectura

El módulo Omnibus Directive Pro sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, con un enfoque en los hooks impulsados por eventos para la integración. Principalmente extiende `Module` para su funcionalidad y configuración central, utiliza `ModuleFrontController` para acciones específicas del front-office (como la limpieza cron), y aprovecha las plantillas Smarty para la renderización. El historial de precios se gestiona a través de la interacción directa con la base de datos y los valores de `Configuration`. El módulo integra un "Estudio de Insignias" y un "Panel de Análisis" dentro del Back Office para un mayor control y conocimiento del comerciante.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `omnipro/controllers/front/cleanupcron.php`
  - **Nombre de clase y clase padre:** `OmniproCleanupcronModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador está diseñado para ser accedido a través de una tarea cron. Cuando se invoca, ejecuta la lógica de limpieza interna del módulo para los datos del historial de precios, típicamente eliminando registros antiguos para mantener el rendimiento de la base de datos. No renderiza ninguna salida visual al navegador, generalmente devolviendo un simple mensaje de éxito o error.
- `omnipro/controllers/front/index.php`
  - **Nombre de clase y clase padre:** `OmniproIndexModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador probablemente sirve como un recurso alternativo o un punto de entrada general para acciones del módulo en el front-office que no requieren un enrutamiento específico, o podría ser un marcador de posición. Dada la función principal del módulo, es menos probable que maneje interacciones de usuario complejas directamente, pero podría usarse para una simple recuperación de datos o verificaciones de estado.

#### Controladores de Administración del Back-Office

No se identificaron controladores de administración dedicados (`controllers/admin/`), lo que sugiere que toda la configuración y el análisis del Back Office se manejan directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

No se identificaron clases personalizadas que extendieran `ObjectModel` en el directorio `classes/`. Esto indica que los datos del historial de precios probablemente se almacenan directamente en `ps_configuration` o en una tabla personalizada gestionada por el archivo principal del módulo (`omnipro/index.php`) sin un envoltorio `ObjectModel` dedicado.

### 4.4 Activos JavaScript (`views/js/`)

- `omnipro/views/js/admin-analytics.js`
  - **Alcance:** Back-office.
  - **Descripción:** Este script es responsable de impulsar los elementos interactivos y la visualización de datos dentro del "Panel de Análisis" del módulo en el Back Office. Probablemente maneja solicitudes AJAX para obtener datos analíticos, renderiza gráficos (por ejemplo, usando Chart.js o bibliotecas similares) y actualiza la interfaz de usuario en función de las interacciones del usuario dentro del panel de análisis.
- `omnipro/views/js/admin-badge-studio.js`
  - **Alcance:** Back-office.
  - **Descripción:** Este script proporciona la funcionalidad interactiva para la pantalla de configuración del "Estudio de Insignias". Gestiona las vistas previas en tiempo real de la insignia a medida que el comerciante ajusta colores, texto, iconos y posiciones. Probablemente maneja selectores de color, actualizaciones de campos de entrada y renderización dinámica de una insignia de vista previa.
- `omnipro/views/js/admin-config.js`
  - **Alcance:** Back-office.
  - **Descripción:** Un script de propósito general para la página de configuración principal del módulo. Podría manejar la validación de formularios, la visualización condicional de configuraciones basadas en otras selecciones (por ejemplo, mostrar la personalización de la insignia solo si se selecciona "Insignia Inteligente") y mejoras generales de la interfaz de usuario para el formulario de configuración.
- `omnipro/views/js/front-chart.js`
  - **Alcance:** Front-office.
  - **Descripción:** Este script es responsable de renderizar el gráfico interactivo del historial de precios en la página de producto. Probablemente obtiene datos de precios a través de AJAX (posiblemente desde un controlador frontal dedicado o un hook), inicializa una biblioteca de gráficos (por ejemplo, Chart.js) y muestra visualmente la evolución del precio al cliente.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `omnipro/views/css/admin-analytics.css`
  - **Alcance:** Estilo de administración del Back-office.
  - **Descripción:** Hojas de estilo específicamente para el diseño y la apariencia del "Panel de Análisis" en la configuración del Back Office del módulo.
- `omnipro/views/css/admin-badge-studio.css`
  - **Alcance:** Estilo de administración del Back-office.
  - **Descripción:** Hojas de estilo para la interfaz del "Estudio de Insignias", incluyendo el estilo para los selectores de color, los elementos de vista previa y el diseño de las opciones de personalización.
- `omnipro/views/css/admin-config.css`
  - **Alcance:** Estilo de administración del Back-office.
  - **Descripción:** Estilo general para el formulario de configuración principal del módulo en el Back Office, asegurando una interfaz consistente y fácil de usar.
- `omnipro/views/css/omnibus-classic.css`
  - **Alcance:** Estilo de cliente del Front-office.
  - **Descripción:** Proporciona un estilo predeterminado para la insignia del precio más bajo y, potencialmente, el gráfico de precios, específicamente adaptado para temas "Clásicos" de PrestaShop más antiguos o temas que imitan su estructura.
- `omnipro/views/css/omnibus-hummingbird.css`
  - **Alcance:** Estilo de cliente del Front-office.
  - **Descripción:** Proporciona un estilo predeterminado para la insignia del precio más bajo y, potencialmente, el gráfico de precios, específicamente optimizado para el nuevo tema "Hummingbird" de PrestaShop.
- `omnipro/views/css/omnibus.css`
  - **Alcance:** Estilo de cliente del Front-office.
  - **Descripción:** Estilos centrales del front-office para la insignia del precio más bajo y el gráfico de precios, aplicables a varios temas. Esto probablemente contiene las reglas visuales fundamentales, con `omnibus-classic.css` y `omnibus-hummingbird.css` proporcionando anulaciones o adiciones específicas del tema.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- `omnipro/lib/searchTool/views/scripts.tpl`
  - **Alcance:** No está claro sin contexto, pero `lib` sugiere una biblioteca de terceros o una utilidad interna. `scripts.tpl` a menudo incluye activos JS o CSS.
  - **Descripción:** Esta plantilla probablemente incluye archivos JavaScript o CSS requeridos por una herramienta de búsqueda interna o utilidad utilizada por el módulo, posiblemente para el procesamiento de datos o componentes específicos de la interfaz de usuario dentro del administrador.
- `omnipro/views/templates/admin/analytics-panel.tpl`
  - **Alcance:** Plantilla de administración.
  - **Descripción:** Renderiza la estructura HTML para el "Panel de Análisis" en el Back Office, incluyendo marcadores de posición para gráficos, estadísticas y tablas de datos.
- `omnipro/views/templates/admin/badge-studio.tpl`
  - **Alcance:** Plantilla de administración.
  - **Descripción:** Renderiza el formulario HTML y el área de vista previa para la configuración del "Estudio de Insignias", permitiendo a los comerciantes personalizar la apariencia de la insignia del precio más bajo.
- `omnipro/views/templates/admin/configure.tpl`
  - **Alcance:** Plantilla de administración.
  - **Descripción:** La plantilla de configuración principal para el módulo, renderizada por `getContent()` en `omnipro/index.php`. Incluye todas las configuraciones generales y probablemente incluye `analytics-panel.tpl` y `badge-studio.tpl` o enlaces a ellos.
- `omnipro/views/templates/hook/omnibus-badge.tpl`
  - **Alcance:** Plantilla de hook (Front-office).
  - **Descripción:** Esta plantilla se renderiza en varios hooks del front-office (por ejemplo, `displayProductPriceBlock`, `displayProductListFunctionalButtons`) para generar el HTML de la insignia del precio más bajo en las páginas de producto y los listados. Recibe variables que contienen el precio más bajo y otras opciones de personalización de la insignia.
- `omnipro/views/templates/hook/omnibus.tpl`
  - **Alcance:** Plantilla de hook (Front-office).
  - **Descripción:** Una plantilla de hook más general, potencialmente utilizada para incrustar el gráfico de precios (`front-chart.js`) u otro contenido relacionado con el módulo en la página de producto, o para la inicialización general del módulo en `displayHeader` o `displayFooter`.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo probablemente almacena sus configuraciones principales en `ps_configuration` (por ejemplo, `OMNIPRO_ENABLED`, `OMNIPRO_DISPLAY_PRODUCT_PAGE`).
  - Dada la función de "historial de precios" y la "limpieza cron", es muy probable que el módulo cree al menos una tabla de base de datos personalizada (por ejemplo, `ps_omnipro_price_history`) para almacenar registros de precios de productos a lo largo del tiempo. Esta tabla normalmente contendría los campos `id_product`, `id_product_attribute`, `id_shop`, `id_currency`, `price` y `date_add`.
  - Si el "Registro de Auditoría CSV" está activado, podría almacenar referencias a archivos CSV generados o entradas de registro en una tabla dedicada.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyectar activos CSS/JS para el front-office, inicializar variables JS de todo el módulo. |
| `displayProductPriceBlock` | Cerca del precio del producto en la página de producto. | Renderizar la insignia del precio más bajo (`omnibus-badge.tpl`) en la página de producto. |
| `displayProductListFunctionalButtons` | Dentro de los listados de productos (categoría, búsqueda, etc.). | Renderizar la insignia del precio más bajo (`omnibus-badge.tpl`) en las tarjetas de producto. |
| `displayFooterProduct` | En la parte inferior de la página de producto. | Potencialmente renderizar el gráfico de precios (`omnibus.tpl` con `front-chart.js`). |
| `actionProductUpdate` | Después de que un producto se actualiza en el Back Office. | Activar el registro del historial de precios para el producto actualizado. |
| `actionProductAdd` | Después de que se añade un nuevo producto. | Inicializar el registro del historial de precios para el nuevo producto. |
| `actionProductDelete` | Después de que se elimina un producto. | Limpiar los datos del historial de precios asociados. |
| `actionUpdateQuantity` | Después de que cambia la cantidad del producto. | (Menos probable para el historial de precios, pero posible para lógica relacionada). |
| `actionUpdateSpecificPrice` | Después de que se añade/actualiza un precio específico (descuento). | Crucial para activar el cálculo del precio más bajo y la lógica de visualización. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su salida. | Añadir condicionalmente CSS/JS del front-office según el contexto de la página. |
| `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice su salida. | Añadir condicionalmente CSS/JS del back-office para las páginas de configuración. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo Omnibus Directive Pro, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto a la funcionalidad e integración del módulo.

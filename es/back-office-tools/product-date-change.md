---
title: "Cambio de fecha de producto - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Cambio de fecha de producto' de MyPresta.eu."
sidebar:
  label: "Cambio de fecha de producto - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product date change en MyPresta.eu](https://mypresta.eu/modules/administration-tools/product-date-change.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/product-date-change/)
>
> ---


# Cambio de fecha de producto

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página de configuración principal del módulo "Cambio de fecha de producto". Aquí es donde seleccionará productos y modificará sus fechas.

#### **Selección de producto**

- **Qué hace este ajuste:** Esta sección le permite buscar y seleccionar los productos específicos cuyas fechas desea modificar.
- **Efecto de cambiar este ajuste:**
  - *Búsqueda de un producto:* Escribir en el cuadro de búsqueda filtrará su lista de productos, facilitando la búsqueda del producto exacto que necesita.
  - *Selección de un producto:* Una vez seleccionado un producto, se mostrarán sus fechas de creación y actualización actuales, y podrá introducir nuevas fechas.
- **Valor recomendado:** Utilice la barra de búsqueda para localizar rápidamente productos por nombre o ID.
- **Escenario / ejemplo de comerciante:** Desea cambiar la fecha de "Vestido de verano 2023". Escribe "Vestido de verano" en el cuadro de búsqueda y el módulo muestra los productos coincidentes. Luego hace clic en "Vestido de verano 2023" para seleccionarlo.

#### **Cambiar fecha de creación del producto**

- **Qué hace este ajuste:** Este campo le permite establecer una nueva `date_add` (fecha de creación) para el producto seleccionado. Esta fecha es utilizada a menudo por PrestaShop para determinar si un producto es "nuevo".
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce y guarda una nueva fecha:* La fecha de creación del producto en su base de datos se actualizará. Esto puede hacer que el producto reaparezca en los bloques de "Productos nuevos" o cambie su posición al ordenar por "Fecha de adición".
  - *Cuando se deja sin cambios:* Se conservará la fecha de creación original del producto.
- **Valor recomendado:** Establezca una fecha que refleje cuándo desea que el producto sea considerado "nuevo" o cuándo se añadió realmente a su catálogo. Para volver a destacarlo, una fecha reciente (hoy o ayer) es ideal.
- **Escenario / ejemplo de comerciante:** Su producto "Abrigo de invierno" se añadió el año pasado. Quiere promocionarlo como una "novedad" para la próxima temporada de invierno. Selecciona el producto y luego establece la "Cambiar fecha de creación del producto" a la fecha de hoy. Ahora, aparecerá en su sección de "Productos nuevos".

#### **Cambiar fecha de actualización del producto**

- **Qué hace este ajuste:** Este campo le permite establecer una nueva `date_upd` (fecha de última actualización) para el producto seleccionado. Esta fecha se utiliza para el seguimiento interno y también puede influir en la clasificación de productos.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce y guarda una nueva fecha:* La fecha de última actualización del producto en su base de datos se modificará. Esto puede afectar las opciones de clasificación donde los clientes ordenan por "Fecha de actualización".
  - *Cuando se deja sin cambios:* Se conservará la fecha de actualización original del producto.
- **Valor recomendado:** Establezca una fecha que refleje la última vez que realizó cambios significativos en el producto (por ejemplo, descripción actualizada, precio, imágenes) o si desea llevarlo a la parte superior de las listas de "recientemente actualizados".
- **Escenario / ejemplo de comerciante:** Acaba de actualizar la descripción y ha añadido nuevas imágenes para su producto "Granos de café orgánico". Quiere que este producto aparezca más arriba cuando los clientes ordenen por "recientemente actualizado". Selecciona el producto y establece la "Cambiar fecha de actualización del producto" a la fecha de hoy.

#### **Botón Guardar**

- **Qué hace este ajuste:** Este botón aplica todos los cambios de fecha que ha realizado para el producto seleccionado.
- **Efecto de cambiar este ajuste:** Al hacer clic en "Guardar", se confirmarán las nuevas fechas de creación y/o actualización en su base de datos de PrestaShop. Normalmente verá un mensaje de éxito.
- **Valor recomendado:** Haga siempre clic en "Guardar" después de realizar cualquier modificación de fecha.
- **Escenario / ejemplo de comerciante:** Después de establecer las fechas de creación y actualización para sus "Zapatillas de edición limitada", hace clic en "Guardar" para aplicar estos cambios a su tienda.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Campo de búsqueda de productos | N/A | Encuentre productos por nombre o ID para modificar sus fechas. |
| Página de configuración del módulo | Cambiar fecha de creación del producto | `date_add` actual del producto | Establece una nueva fecha de creación. Afecta la visibilidad de "Productos nuevos" y la clasificación por "Fecha de adición". Recomendado: Una fecha reciente para volver a destacar. |
| Página de configuración del módulo | Cambiar fecha de actualización del producto | `date_upd` actual del producto | Establece una nueva fecha de última actualización. Afecta la clasificación por "Fecha de actualización". Recomendado: Una fecha reciente después de cambios significativos en el producto. |
| Página de configuración del módulo | Botón Guardar | N/A | Aplica todos los cambios de fecha seleccionados al producto en la base de datos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Cambié la fecha, pero el producto no aparece como "nuevo" en mi página de inicio. ¿Qué pasa?**
R1:

- **Borrar caché:** PrestaShop depende en gran medida del almacenamiento en caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Esta es la solución más común.
- **Configuración del módulo:** Verifique la configuración de su módulo de "Productos nuevos" (por ejemplo, "Bloque de productos nuevos" o "Página de productos nuevos"). Asegúrese de que esté configurado para mostrar productos según su fecha de creación y que el número de días para productos "nuevos" esté configurado adecuadamente (por ejemplo, 30 días). Si establece la fecha de creación de un producto para que sea anterior a este umbral, no aparecerá como nuevo.
- **Especificaciones del tema:** Algunos temas pueden tener su propio almacenamiento en caché o lógica personalizada para "productos nuevos". Si borrar la caché no funciona, consulte la documentación o el soporte de su tema.

**P2: ¿Cambiar la fecha del producto afectará mi SEO?**
R2: Directamente, no. Los motores de búsqueda como Google se centran principalmente en el contenido de la página de su producto (descripción, imágenes, reseñas) y los enlaces externos, no en las fechas internas de los productos de PrestaShop. Sin embargo, indirectamente, si cambiar la fecha hace que el producto aparezca como "nuevo" y genera más tráfico interno o ventas, ese mayor compromiso *puede* influir positivamente en el SEO con el tiempo. Se trata más de la experiencia del usuario y la comercialización que de la manipulación directa del SEO.

**P3: ¿Puedo cambiar las fechas de varios productos a la vez (edición masiva)?**
R3: Este módulo está diseñado para cambios de fecha de productos individuales. Si necesita editar fechas de forma masiva para un gran número de productos, normalmente necesitaría una herramienta de importación/exportación más avanzada o un script personalizado. Para unos pocos productos, hacerlo uno por uno con este módulo es eficiente.

**P4: ¿Qué sucede si establezco una fecha futura?**
R4: PrestaShop aceptará una fecha futura. Sin embargo, el efecto práctico podría ser limitado. Un producto configurado con una fecha de creación futura podría no aparecer en las listas de "productos nuevos" hasta que llegue esa fecha. Generalmente se recomienda usar fechas actuales o pasadas.

**P5: Cambié la fecha, pero cuando edito el producto en el Back Office, la fecha antigua sigue ahí.**
R5: Este módulo modifica directamente los campos `date_add` y `date_upd` en la base de datos. Cuando ve un producto en la página de edición de productos estándar de PrestaShop, debería reflejar estos cambios. Si no lo hace, asegúrese de haber hecho clic en "Guardar" en la configuración del módulo, borrado la caché de PrestaShop y recargado la página de edición del producto. Si el problema persiste, podría haber un conflicto con otro módulo o un problema de caché más profundo.

## 4. Guía para desarrolladores y webmasters (arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo `Product date change` (`pdc`) es un módulo de PrestaShop sencillo diseñado para interactuar directamente con el ObjectModel `Product`. Aprovecha el método estándar `getContent()` para su configuración en el Back Office, proporcionando un formulario simple para seleccionar un producto y modificar sus campos `date_add` y `date_upd`. No introduce nuevas tablas de base de datos, controladores complejos o lógica extensa de front-office, lo que lo hace ligero y centrado en su tarea administrativa principal.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador personalizado de front-office o back-office. Toda la lógica está encapsulada dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase o ObjectModel personalizado en el directorio `classes/`. Interactúa directamente con el ObjectModel `Product` principal de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. Se espera que el estilo sea manejado por los estilos predeterminados del Back Office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`pdc/views/pdc.tpl`**:
  - **Alcance**: Configuración de administración del Back Office.
  - **Propósito**: Esta plantilla renderiza el formulario de configuración principal del módulo. Incluye:
    - Un campo de entrada de búsqueda para encontrar productos.
    - Áreas de visualización para la `date_add` y `date_upd` actuales del producto seleccionado.
    - Campos de entrada (probablemente selectores de fecha) para establecer nuevos valores de `date_add` y `date_upd`.
    - Un botón de envío para guardar los cambios.
  - **Uso**: Esta plantilla es renderizada por el método `getContent()` del módulo `pdc`.
  - **Selectores clave**: Los desarrolladores pueden inspeccionar el HTML generado en busca de ID o clases específicas para anular el estilo si es necesario, aunque normalmente no es necesario para un formulario de administración simple.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo no crea ninguna tabla de base de datos personalizada.
  - Modifica directamente las columnas `date_add` y `date_upd` dentro de la tabla `ps_product` existente (y potencialmente `ps_product_shop` si se gestionan fechas específicas del contexto, aunque la descripción del módulo implica la modificación directa del objeto del producto).
  - Los valores de configuración (si los hay, aunque no se enumeran explícitamente más allá de la manipulación directa del producto) se almacenarían en `ps_configuration`.
- **Tabla de hooks registrados**:
  Este módulo no registra ningún hook específico para la visualización en el front-office o acciones en el back-office más allá de los estándar `displayBackOfficeHeader` (para activos, si los hubiera) y `moduleRoutes` (si se necesitaran URL personalizadas, lo cual no es el caso de este módulo). Su interacción principal es a través del método `getContent()`.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Se renderiza en la sección `<head>` de las páginas del Back Office. | (Potencialmente) Para incluir cualquier JS/CSS necesario para la página de configuración del módulo, aunque no hay ninguno presente en este módulo. |
| `actionProductUpdate` | Se ejecuta después de que se actualiza un producto. | La lógica interna del módulo para actualizar las fechas de los productos podría activar este hook, pero el módulo en sí no se registra explícitamente para escucharlo o realizar acciones basadas en él. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Cambio de fecha de producto", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con la funcionalidad y compatibilidad del módulo.

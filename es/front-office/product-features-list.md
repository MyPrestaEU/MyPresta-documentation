---
title: "Lista de características del producto - Manual del comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Lista de características del producto' de MyPresta.eu."
sidebar:
  label: "Lista de características del producto - Manual del comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product features list en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-features-list.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-features-list/)
>
> ---


# Lista de características del producto

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Lista de características del producto)

Esta es la pantalla de configuración principal del módulo, a la que se accede inmediatamente después de la instalación o haciendo clic en "Configurar" desde el Gestor de módulos.

- **Qué hace este ajuste:** Este ajuste controla dónde aparecerá visualmente la lista de características del producto en sus páginas de listado de productos (páginas de categoría, resultados de búsqueda, etc.).
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "displayProductListReviews":* Las características aparecerán cerca de la sección de reseñas del producto en la lista de productos. Este suele ser un buen lugar para agrupar la prueba social con los atributos clave del producto.
  - *Cuando se establece en "displayProductDeliveryTime":* Las características aparecerán cerca de cualquier información de tiempo de entrega mostrada. Esto puede ser útil para productos donde las características están estrechamente ligadas a la logística o la disponibilidad.
  - *Cuando se establece en "displayHeader":* Esta opción es menos común para la visualización visual en las listas de productos y podría colocar las características en el encabezado de la página, que generalmente no es donde querría que aparecieran las características específicas del producto. Es principalmente un hook técnico.
- **Valor recomendado:** "displayProductListReviews" o "displayProductDeliveryTime". Elija el que mejor se integre con el diseño de su tema y donde sienta que las características serán más visibles sin saturar.
- **Escenario / ejemplo de comerciante:** Si su tema muestra prominentemente las calificaciones de estrellas y el número de reseñas, "displayProductListReviews" colocaría las características justo al lado, creando un bloque de información rico. Si sus productos a menudo tienen detalles de entrega específicos (por ejemplo, "Se envía en 24h"), colocar las características con "displayProductDeliveryTime" podría tener sentido.

### 2.2 Pantalla de administración dedicada: Asociación de características (Back Office > Módulos > Lista de características del producto > Configurar > "Gestionar asociaciones de características" o enlace similar)

Esta pantalla es crucial para definir *qué* características aparecen para *qué* productos y categorías. Es donde se asocian características específicas del producto con categorías.

- **Nombre de la pantalla y ubicación del menú:** Después de configurar el módulo principal, normalmente encontrará un enlace o botón en la página de configuración del módulo (o un nuevo elemento de menú en "Catálogo") que lleva a "Gestionar asociaciones de características" o "Lista de características del producto". La ruta exacta puede variar ligeramente según su versión de PrestaShop, pero estará vinculada desde la configuración principal del módulo.
- **Acciones y ajustes disponibles:**
  - **Vista de cuadrícula/gestión:** Verá una tabla que lista sus características de producto existentes (estas son las características estándar que define en **Catálogo > Atributos y características > Características**).
  - **Botón Editar/Asociar:** Para cada característica, habrá un botón "Editar" o "Asociar". Al hacer clic en él, se abrirá un formulario donde podrá:
    - **Seleccionar categorías:** Elija una o más categorías para las que esta característica específica debe mostrarse en las listas de productos. Por ejemplo, si tiene una característica "Material", podría asociarla con las categorías "Camisetas", "Vestidos" y "Chaquetas".
    - **Habilitar/Deshabilitar:** Puede tener una opción para habilitar o deshabilitar la visualización de esta característica en las listas de productos globalmente o por categoría.
- **Efecto de los cambios:**
  - *Cuando asocia una característica con una categoría:* Los productos dentro de esa categoría que poseen esta característica la mostrarán en su entrada de la lista de productos.
  - *Cuando elimina una asociación:* La característica ya no aparecerá para los productos de esa categoría en las listas de productos.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Primero, asegúrese de que todas sus características de producto estén configuradas correctamente en **Catálogo > Atributos y características > Características**.
  2. Navegue a la pantalla "Gestionar asociaciones de características" del módulo "Lista de características del producto".
  3. Revise cada característica relevante.
  4. Para cada característica, seleccione las categorías donde desea que esta característica sea visible en las páginas de listado de productos.
  5. Guarde sus cambios.
  6. Revise periódicamente estas asociaciones, especialmente al añadir nuevos productos, categorías o características, para asegurarse de que sus listas de productos sigan siendo informativas.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Posición de las etiquetas (`fplist_position`) | `displayProductListReviews` | Determina dónde aparecen las características en las páginas de lista de productos (por ejemplo, cerca de las reseñas, cerca del tiempo de entrega). |
| Asociación de características | Nombre de la característica (por ejemplo, "Material") | N/A | Característica estándar de PrestaShop a gestionar. |
| Asociación de características | Categorías asociadas | N/A | Seleccione las categorías donde esta característica debe ser visible en las listas de productos. |
| Asociación de características | Habilitar/Deshabilitar característica | Habilitado | Controla si una característica se muestra activamente para sus categorías asociadas. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He configurado el módulo, pero las características no aparecen en mis páginas de categoría.**
R:

1. **Verifique las asociaciones de características:** Vaya a la pantalla "Gestionar asociaciones de características" y asegúrese de que las características que espera ver estén realmente asociadas con las categorías que está viendo.
2. **Borrar caché:** PrestaShop utiliza caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" si está disponible).
3. **Posición del módulo:** Vuelva a verificar la configuración de "Posición de las etiquetas" en la configuración principal del módulo. Asegúrese de que esté configurado en un hook que su tema realmente renderice en el contexto de la lista de productos (por ejemplo, `displayProductListReviews` o `displayProductDeliveryTime`). Algunos temas personalizados podrían no llamar explícitamente a todos los hooks estándar.
4. **Datos del producto:** Verifique que los productos en cuestión realmente *tengan* valores para las características que está intentando mostrar (por ejemplo, si desea mostrar "Material", asegúrese de que el producto tenga un material asignado).

**P: Las características se muestran, pero se ven desordenadas o no encajan con el diseño de mi tema.**
R:

1. **Conflicto de CSS:** Es probable que se trate de un conflicto de estilo con su tema. El módulo incluye su propio CSS (`fplist/views/css/fplist.css`), pero los estilos de su tema podrían estar anulándolo o causando problemas de diseño.
2. **Tema personalizado:** Si está utilizando un tema altamente personalizado, es posible que necesite un webmaster o desarrollador para ajustar el CSS del módulo o el CSS de su tema para garantizar una integración adecuada.
3. **Posicionamiento:** Intente cambiar la configuración de "Posición de las etiquetas" para ver si un hook diferente se integra mejor visualmente con su tema.

**P: ¿Puedo mostrar diferentes características para diferentes categorías?**
R: ¡Sí, absolutamente! Esta es una de las principales fortalezas del módulo. Utilice la pantalla "Gestionar asociaciones de características" para seleccionar categorías específicas para cada característica. Esto le permite adaptar la información mostrada con precisión al contexto de la lista de productos.

**P: ¿Este módulo afecta a mis páginas de producto?**
R: No, este módulo se dirige específicamente a las páginas de *listado* de productos (categoría, resultados de búsqueda, etc.). No altera la forma en que se muestran las características en las páginas de detalles de productos individuales.

**P: Mi tienda es multiidioma. ¿Se traducen los nombres de las características?**
R: Sí, las características estándar de PrestaShop (que utiliza este módulo) son totalmente traducibles. Asegúrese de haber proporcionado traducciones para los nombres y valores de sus características en **Catálogo > Atributos y características > Características** para todos los idiomas activos en su tienda. El módulo mostrará entonces la traducción correcta en el front office.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Lista de características del producto" (`fplist`) sigue una arquitectura de módulo de PrestaShop estándar, extendiendo principalmente `Module` para su funcionalidad principal y `AdminController` para su interfaz de gestión del Back Office. Aprovecha el sistema de hooks de PrestaShop para inyectar contenido en las páginas de listado de productos y utiliza un `ObjectModel` (implícitamente a través de `AdminFplistAssociationController`) para gestionar la asociación entre características y categorías. La visualización del front-office del módulo se maneja mediante una plantilla Smarty renderizada a través de un hook.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Este módulo no contiene controladores de front-office dedicados. Toda la lógica de visualización del front-office se maneja directamente dentro del archivo principal del módulo (`fplist.php`) a través de hooks registrados.
- **Controladores de administración del Back-Office**:

  - `fplist/controllers/admin/AdminFplistAssociation.php`
    - **Nombre de la clase:** `AdminFplistAssociationController` (extiende `ModuleAdminController`)
    - **Responsabilidad:** Este controlador gestiona la asociación entre las características de PrestaShop y las categorías. Proporciona la interfaz del Back Office (una lista y potencialmente un formulario de edición) para que los administradores seleccionen qué características deben mostrarse en las listas de productos para categorías específicas. Interactúa con el almacenamiento de datos interno del módulo (probablemente la tabla `ps_fplist_association`, aunque no se proporciona un `ObjectModel` explícito en el dossier, el controlador implica su existencia y gestión).
  - `fplist/controllers/admin/index.php`
    - **Nombre de la clase:** N/A (este suele ser un archivo vacío o una redirección para evitar el acceso directo al directorio, no un controlador funcional).
    - **Responsabilidad:** Medida de seguridad estándar de PrestaShop para evitar el listado de directorios.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. El `AdminFplistAssociationController` implica la existencia de un modelo de datos para las asociaciones característica-categoría, que probablemente se maneja directamente dentro del controlador o el archivo principal del módulo utilizando consultas `Db::getInstance()`, en lugar de un `ObjectModel` dedicado. Si hubiera un `ObjectModel`, normalmente se llamaría `FplistAssociation` o similar.

### 4.4 Activos JavaScript (`views/js/`)

El dossier del módulo no indica archivos JavaScript personalizados. Cualquier comportamiento dinámico o interacciones AJAX tendrían que implementarse directamente dentro del PHP o los archivos de plantilla del módulo, o depender del JS principal de PrestaShop.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `fplist/views/css/fplist.css`
  - **Alcance:** Estilo del front-office para el cliente.
  - **Componentes e contenedores principales de la interfaz de usuario que estiliza:** Esta hoja de estilo es responsable de la presentación visual de la lista de características del producto en las páginas de categoría y listado. Define estilos para el contenedor que contiene las características, los elementos de características individuales y, potencialmente, los iconos o etiquetas asociados a ellos.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:** Los desarrolladores deben inspeccionar el HTML renderizado para identificar clases específicas (por ejemplo, `.fplist-container`, `.fplist-item`, `.fplist-feature-name`, `.fplist-feature-value`) para anular en el `custom.css` o `theme.css` de su tema para una integración perfecta.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - `fplist/views/templates/fplist-front.tpl`
    - **Hook:** Esta plantilla se renderiza dentro de los hooks `displayProductListReviews` y `displayProductDeliveryTime` (según la configuración de `fplist_position`).
    - **Salida:** Genera la estructura HTML para la lista de características de un solo producto en una página de listado de productos. Itera a través de las características recuperadas por el módulo para el producto y la categoría actuales, mostrando sus nombres y valores.
  - `fplist/views/templates/fplist.tpl`
    - **Hook:** Esta plantilla se utiliza probablemente para la página de configuración principal del módulo en el Back Office (a través de `getContent()`).
    - **Salida:** Renderiza el formulario para la configuración de "Posición de las etiquetas" y, potencialmente, enlaces al `AdminFplistAssociationController` para gestionar las asociaciones de características.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - `ps_fplist_association` (implícita): Esta tabla no está definida explícitamente en el dossier, pero es necesaria para que el `AdminFplistAssociationController` almacene la relación de muchos a muchos entre las características y categorías de PrestaShop. Normalmente contendría columnas como `id_feature`, `id_category` y, potencialmente, `id_shop`.
  - Registros de configuración en `ps_configuration`:
    - `mypresta_updates`: Almacena información de actualización para los módulos de MyPresta.eu.
    - `update_`: Relacionado con las comprobaciones de actualización del módulo.
    - `updatev_`: Relacionado con las comprobaciones de actualización del módulo.
    - `fplist_position`: Almacena el nombre del hook seleccionado para mostrar las características (por ejemplo, `displayProductListReviews`).
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Configuración estándar de PrestaShop para el idioma del formulario del empleado.
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Se utiliza principalmente para cargar activos CSS/JS o metaetiquetas. El módulo lo utiliza como una posición configurable para las características, aunque es menos común para la visualización visual. |
| `displayProductListReviews` | Dentro del elemento de la lista de productos, normalmente cerca de las reseñas del producto. | Inyecta el HTML de la lista de características en cada entrada de producto en las páginas de categoría/búsqueda. |
| `displayProductDeliveryTime` | Dentro del elemento de la lista de productos, normalmente cerca de la información del tiempo de entrega. | Inyecta el HTML de la lista de características en cada entrada de producto en las páginas de categoría/búsqueda. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | (No utilizado explícitamente por este módulo, pero un hook común para acciones relacionadas con pedidos). |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte profesional, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con el módulo "Lista de características del producto".

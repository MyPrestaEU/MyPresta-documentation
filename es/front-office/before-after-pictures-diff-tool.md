---
title: "Antes y después - herramienta de comparación de imágenes - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Before & after - pictures diff tool' de MyPresta.eu."
sidebar:
  label: "Antes y después - herramienta de comparación de imágenes - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Before & after - pictures diff tool en MyPresta.eu](https://mypresta.eu/modules/front-office-features/before-after-pictures-diff-tool.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/before-after-pictures-diff-tool/)
>
> ---


# Antes y después - herramienta de comparación de imágenes

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones estándar de PHP (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Antes y después - herramienta de comparación de imágenes" para acceder a sus ajustes principales.

#### Ajustes generales

-   **Qué hace este ajuste:** Esta sección controla la activación general y el modo de operación del módulo.
-   **Efecto de cambiar este ajuste:**
    -   *Activado:* El módulo estará activo en toda su tienda. La herramienta de comparación de imágenes "Antes y después" estará disponible en las páginas de productos donde haya configurado imágenes.
    -   *Desactivado:* El módulo estará inactivo. La herramienta de comparación de imágenes "Antes y después" no aparecerá en ninguna página de producto, incluso si ha configurado imágenes para ellas.
    -   *Modo de prueba:* Esta opción se utiliza típicamente para entornos de desarrollo o staging. Cuando está activada, el módulo podría mostrar información de depuración adicional u operar bajo condiciones específicas que no son adecuadas para una tienda de producción en vivo. Generalmente no se recomienda para tiendas en vivo a menos que el soporte lo indique explícitamente.
-   **Valor recomendado:** "Activado" para una tienda en vivo. "Desactivado" si desea ocultar temporalmente la función sin desinstalar el módulo.
-   **Escenario / ejemplo de comerciante:** Si está lanzando una nueva línea de productos que depende en gran medida de las transformaciones visuales (por ejemplo, zapatos pintados a medida), lo configuraría en "Activado" para mostrar el trabajo. Si está realizando mantenimiento o no desea que la función esté activa por un período, lo configuraría en "Desactivado".

#### Ajustes de idioma (Implícito)

Aunque no se enumera explícitamente como un ajuste, el módulo respetará la configuración de idioma predeterminada de su PrestaShop para el Back Office.

-   **`PS_LANG_DEFAULT`**: Este ajuste central de PrestaShop determina el idioma predeterminado de su tienda.
-   **`PS_BO_ALLOW_EMPLOYEE_FORM_LANG`**: Este ajuste central de PrestaShop permite a los empleados elegir su idioma preferido para los formularios.
-   **Efecto de cambiar este ajuste:** Estos ajustes centrales de PrestaShop aseguran que cualquier texto o etiqueta proporcionada por el módulo en el Back Office (por ejemplo, en la página de edición de productos para agregar imágenes de antes/después) se muestre en el idioma correcto para el administrador.
-   **Valor recomendado:** Asegúrese de que su `PS_LANG_DEFAULT` esté configurado en el idioma principal de su tienda. Si tiene un equipo multilingüe, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` debe estar activado.

#### Ajustes de actualización (Implícito)

El módulo también incluye ajustes internos relacionados con las actualizaciones de MyPresta.eu. Estos suelen gestionarse automáticamente.

-   **`mypresta_updates`, `update_`, `updatev_`**: Estas son claves de configuración internas utilizadas por los módulos de MyPresta.eu para verificar y gestionar las actualizaciones. Generalmente no necesita interactuar con ellas.
-   **Efecto de cambiar este ajuste:** Modificarlos directamente podría interferir con la capacidad del módulo para recibir actualizaciones importantes y correcciones de errores.
-   **Valor recomendado:** Déjelos sin tocar.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### Página de edición de productos (Back Office > Catálogo > Productos > Editar producto)

Este módulo se integra directamente en la interfaz estándar de edición de productos de PrestaShop.

-   **Nombre de la pantalla y ubicación del menú:** Para acceder a esto, navegue a **Catálogo > Productos**, luego haga clic en "Editar" en cualquier producto.
-   **Acciones y ajustes disponibles:** Dentro de la página de edición de productos, encontrará una nueva sección o pestaña específicamente para "Antes y después - herramienta de comparación de imágenes". Aquí podrá:
    -   **Subir imagen "Antes":** Seleccione y suba la imagen del estado inicial de su producto.
    -   **Subir imagen "Después":** Seleccione y suba la imagen del estado final de su producto.
    -   **Guardar:** Después de subir, recuerde guardar el producto para aplicar los cambios.
-   **Efecto de los cambios:**
    -   *Agregar imágenes:* Una vez que suba tanto una imagen "Antes" como una "Después" para un producto específico y guarde, el deslizador de comparación interactivo aparecerá automáticamente en la página de front-office de ese producto.
    -   *Eliminar imágenes:* Si elimina una o ambas imágenes, el deslizador de comparación ya no se mostrará para ese producto.
    -   *Actualizar imágenes:* Reemplazar imágenes actualizará el deslizador en el front office.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Al agregar un nuevo producto que se beneficia de una comparación de antes/después, primero cree el producto como de costumbre.
    2.  Navegue a su página de edición.
    3.  Localice la sección "Antes y después".
    4.  Suba sus imágenes "antes" y "después". Asegúrese de que tengan dimensiones similares para el mejor efecto visual.
    5.  Guarde el producto.
    6.  Verifique la página del producto en el front office para confirmar que el deslizador funciona como se espera.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Estado del módulo | Activado | Activa/desactiva la funcionalidad completa del módulo. |
| Página de edición de productos | Subir imagen "Antes" | N/A | Define la imagen del estado inicial para la comparación. |
| Página de edición de productos | Subir imagen "Después" | N/A | Define la imagen del estado final para la comparación. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: El deslizador "Antes y después" no aparece en la página de mi producto.**
R1:

-   **Verificar el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Antes y después - herramienta de comparación de imágenes" esté "Activado".
-   **Verificar las imágenes del producto:** Edite el producto específico (**Catálogo > Productos > Editar**) y verifique que tanto una imagen "Antes" como una "Después" hayan sido subidas y guardadas en la sección del módulo.
-   **Borrar caché:** A veces, la caché de PrestaShop puede evitar que aparezca contenido nuevo. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché".
-   **Compatibilidad del tema:** Aunque el módulo está diseñado para ser compatible, algunos temas altamente personalizados podrían requerir pequeños ajustes de CSS. Si los pasos anteriores no funcionan, póngase en contacto con el soporte de MyPresta.eu.

**P2: Las imágenes se ven distorsionadas o desalineadas en el deslizador.**
R2:

-   **Dimensiones de la imagen:** Para obtener los mejores resultados, asegúrese de que sus imágenes "Antes" y "Después" tengan exactamente las mismas dimensiones (ancho y alto). Si difieren significativamente, el deslizador podría tener dificultades para alinearlas perfectamente.
-   **Calidad de la imagen:** Utilice imágenes de alta calidad. Las imágenes de baja resolución pueden aparecer pixeladas al escalarlas.

**P3: ¿Puedo usar este módulo para productos con múltiples variaciones (combinaciones)?**
R3: El módulo actualmente le permite establecer una imagen "Antes" y una "Después" por producto, no por combinación. Si sus variaciones tienen diferentes estados de antes/después, es posible que deba crear productos separados o usar las imágenes principales del producto para la comparación.

**P4: ¿Cómo traduzco el texto del módulo (si lo hay) a otros idiomas?**
R4: Cualquier etiqueta de texto introducida por el módulo en el Back Office (por ejemplo, "Subir imagen Antes") se puede traducir típicamente a través del sistema de traducción incorporado de PrestaShop. Vaya a **Internacional > Traducciones**, seleccione "Traducciones de módulos instalados", elija su tema y luego busque el módulo "Antes y después - herramienta de comparación de imágenes" para editar sus traducciones.

**P5: El deslizador funciona, pero no se ve del todo bien con el diseño de mi tema.**
R5: Esto a menudo se reduce al estilo CSS. Su tema podría tener estilos conflictivos. Puede intentar inspeccionar el elemento usando las herramientas de desarrollador de su navegador para identificar el CSS conflictivo. Para una personalización más avanzada, es posible que necesite un desarrollador web o ponerse en contacto con el soporte de MyPresta.eu para obtener orientación sobre cómo anular los estilos predeterminados del módulo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Antes y después - herramienta de comparación de imágenes" es un módulo estándar de PrestaShop que sigue un patrón similar a MVC. Principalmente extiende la clase `Module`, se integra con la página de administración de productos a través de hooks e inyecta sus activos y plantillas de front-office en el pie de página del producto. Aprovecha los plugins externos de jQuery (`jquery.event.move.js`, `jquery.twentytwenty.js`) para la funcionalidad del deslizador interactivo.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores dedicados de front-office o back-office. Toda la lógica se maneja dentro de la clase principal del módulo y a través de hooks.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada u `ObjectModel`. Almacena su configuración directamente en `ps_configuration` y las rutas de imagen específicas del producto como atributos del producto o valores de configuración, gestionados a través del hook `displayAdminProductsExtra`.

### 4.4 Activos JavaScript (`views/js/`)

El módulo incluye varios archivos JavaScript, principalmente para el deslizador de comparación de imágenes "TwentyTwenty". Estos se cargan en el front office.

-   **`beforeafter/js/jquery.event.move.js`**
    -   **Alcance:** Front-office.
    -   **Propósito:** Un plugin ligero de jQuery que proporciona manejo de eventos táctiles y de ratón para arrastrar elementos. Es una dependencia para `jquery.twentytwenty.js`.
    -   **Detalles:** Vincula eventos como `move`, `movestart`, `moveend` para habilitar la funcionalidad de arrastre.
-   **`beforeafter/js/jquery.twentytwenty.js`**
    -   **Alcance:** Front-office.
    -   **Propósito:** El plugin principal de jQuery que implementa el deslizador de comparación de imágenes "TwentyTwenty".
    -   **Detalles:** Inicializa el deslizador en elementos especificados, maneja la representación visual de las imágenes de antes/después y gestiona el divisor interactivo basado en `jquery.event.move.js`. Típicamente apunta a un contenedor con dos etiquetas `img` dentro.
-   **`beforeafter/js/twentytwenty.js`**
    -   **Alcance:** Front-office.
    -   **Propósito:** Este archivo probablemente contiene la lógica de inicialización específica del módulo para el plugin `jquery.twentytwenty.js`, aplicándolo a los elementos correctos en la página del producto.
    -   **Detalles:** Contendrá selectores de jQuery para identificar el elemento `div` que envuelve las imágenes de antes/después y llamará al método `.twentytwenty()` en él, potencialmente con opciones de configuración.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo incluye archivos CSS para estilizar el deslizador de comparación de imágenes y sus componentes.

-   **`beforeafter/css/foundation.css`**
    -   **Alcance:** Front-office.
    -   **Propósito:** Este archivo probablemente contiene estilos básicos de reinicio o fundamentales, posiblemente un subconjunto del framework Zurb Foundation, para asegurar una representación consistente de los elementos del deslizador. Podría definir estilos básicos de cuadrícula, tipografía o formularios que utiliza el módulo.
    -   **Selectores clave:** Puede incluir estilos generales de `div`, `img`, `button`, o clases específicas como `.row`, `.column`.
-   **`beforeafter/css/twentytwenty.css`**
    -   **Alcance:** Front-office.
    -   **Propósito:** Contiene el estilo específico requerido para el propio deslizador de comparación de imágenes "TwentyTwenty".
    -   **Selectores clave:** Definirá la apariencia del contenedor del deslizador, el manejador del divisor, la superposición y el posicionamiento de las imágenes "antes" y "después". Ejemplos: `.twentytwenty-container`, `.twentytwenty-overlay`, `.twentytwenty-handle`, `.twentytwenty-before`, `.twentytwenty-after`. Los desarrolladores pueden anular estas clases en el `custom.css` o `theme.css` de su tema para que coincidan con el diseño de su tienda.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `beforeafter/views/templates/front/hook/displayFooter.tpl`
        -   **Hook:** `displayFooter` (o potencialmente `displayFooterProduct` dependiendo de la lógica interna).
        -   **Propósito:** Esta plantilla es responsable de renderizar la estructura HTML real para el deslizador de comparación de imágenes "Antes y después" en el front office. Contendrá los elementos `div` que el JavaScript apuntará para inicializar el plugin `twentytwenty`, incluyendo las etiquetas `img` para las imágenes "antes" y "después". También es probable que incluya la carga necesaria de activos JavaScript y CSS.
    -   `beforeafter/views/templates/front/hook/displayFooterCms.tpl`
        -   **Hook:** Probablemente `displayFooter` o `displayFooterProduct` pero potencialmente con lógica condicional para páginas CMS.
        -   **Propósito:** Esta plantilla podría ser una alternativa o un respaldo para renderizar el deslizador en páginas CMS, aunque la descripción del módulo se centra en las páginas de productos. Su contenido sería similar a `displayFooter.tpl`.
-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `beforeafter/views/templates/admin/displayAdminProductsExtra.tpl`
        -   **Hook:** `displayAdminProductsExtra`
        -   **Propósito:** Esta plantilla renderiza los campos de entrada personalizados y los formularios de carga dentro de la página de edición de productos de PrestaShop en el Back Office. Proporciona la interfaz para que los administradores suban y gestionen las imágenes "Antes" y "Después" para cada producto. Contendrá elementos de formulario (por ejemplo, `input type="file"`) y potencialmente mostrará miniaturas de imágenes ya subidas.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:
    -   El módulo no crea tablas SQL personalizadas.
    -   Almacena sus configuraciones (como `BA_TEST`) en la tabla `ps_configuration`.
    -   Las rutas de imagen "antes" y "después" específicas del producto probablemente se almacenan como valores de configuración o atributos específicos del producto, gestionados a través del hook `displayAdminProductsExtra` y los métodos `install()` y `uninstall()` del módulo.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionProductUpdate` | Después de que un producto se actualiza en el Back Office. | Se utiliza para guardar las rutas de las imágenes "antes" y "después" subidas a través de la página de edición del producto. |
| `displayFooterProduct` | Renderiza contenido en la sección del pie de página de la página del producto. | Se utiliza para mostrar el deslizador de comparación de imágenes "Antes y después" en la página de producto del front-office. |
| `displayAdminProductsExtra` | Renderiza contenido adicional en la página de edición de productos en el Back Office. | Se utiliza para inyectar los campos de formulario personalizados para subir imágenes "antes" y "después" en la interfaz de administración de productos. |
| `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice su vista, permitiendo a los módulos agregar JS/CSS. | Se utiliza para cargar los archivos JavaScript (`jquery.event.move.js`, `jquery.twentytwenty.js`, `twentytwenty.js`) y CSS (`foundation.css`, `twentytwenty.css`) necesarios para el módulo en el Back Office (si es necesario para la página de producto de administración) y potencialmente el front office. |
| `displayHeader` | Renderiza contenido en la sección `<head>` de las páginas del front-office. | Se utiliza para cargar los archivos JavaScript y CSS necesarios para el deslizador "Antes y después" en el front office, asegurando que estén disponibles antes de que el hook `displayFooterProduct` renderice el HTML del deslizador. |

## 5. Soporte oficial y actualizaciones

Para soporte oficial, actualizaciones y cualquier asistencia adicional con el módulo "Antes y después - herramienta de comparación de imágenes", consulte su cuenta de cliente de MyPresta.eu. Puede encontrar las últimas versiones del módulo, documentación y ponerse en contacto con nuestro equipo de soporte directamente a través del sitio web de MyPresta.eu.

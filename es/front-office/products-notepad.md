---
title: "Bloc de Notas de Productos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Bloc de Notas de Productos para PrestaShop de MyPresta.eu."
sidebar:
  label: "Bloc de Notas de Productos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Products Notepad en MyPresta.eu](https://mypresta.eu/modules/front-office-features/products-notepad.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/products-notepad/)
>
> ---


# Bloc de Notas de Productos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para el funcionamiento general de PrestaShop. No se necesitan extensiones adicionales específicas para este módulo.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haz clic en "Configurar" junto al módulo "Bloc de Notas de Productos" en el Gestor de Módulos. Esto te llevará a la pantalla principal de configuración.

#### Ajustes Generales

- **Qué hace este ajuste:** Esta sección controla el comportamiento principal y la visualización del módulo Bloc de Notas de Productos en tu tienda.

  - **Recordar productos en el bloc de notas:**

    - **Qué hace este ajuste:** Determina si los productos que un cliente añade a su bloc de notas se recuerdan en diferentes sesiones de navegación o si el bloc de notas se borra cuando cierran su navegador.
    - **Efecto de cambiar este ajuste:**
      - *Cuando está activado (SÍ):* Los productos añadidos al bloc de notas persistirán incluso si el cliente abandona tu sitio y regresa más tarde (por ejemplo, al día siguiente). Esto utiliza cookies del navegador para almacenar el contenido del bloc de notas.
      - *Cuando está desactivado (NO):* El bloc de notas se borrará cuando el cliente cierre su navegador o borre sus cookies. Cada nueva sesión comenzará con un bloc de notas vacío.
    - **Valor recomendado:** **SÍ**. Esto proporciona una experiencia de cliente mucho mejor, ya que permite a los clientes construir una lista con el tiempo sin perder su progreso.
    - **Escenario / ejemplo del comerciante:** Un cliente añade varios artículos a su bloc de notas el lunes. Si "Recordar productos" es SÍ, pueden regresar el miércoles y encontrar su lista intacta. Si es NO, la lista estaría vacía.
  - **Limitar número de productos en el bloc de notas:**

    - **Qué hace este ajuste:** Te permite establecer un número máximo de productos que un cliente puede guardar en su bloc de notas.
    - **Efecto de cambiar este ajuste:**
      - *Cuando está activado (SÍ):* El bloc de notas solo permitirá un número específico de productos. Una vez alcanzado el límite, los clientes no podrán añadir más productos hasta que eliminen los existentes.
      - *Cuando está desactivado (NO):* Los clientes pueden añadir un número ilimitado de productos a su bloc de notas.
    - **Valor recomendado:** **NO** (a menos que tengas una razón específica para limitarlo, como preocupaciones de rendimiento con listas extremadamente largas). Permitir artículos ilimitados da a los clientes la máxima flexibilidad.
    - **Escenario / ejemplo del comerciante:** Si activas esto y estableces el límite en 10, un cliente que intente añadir un undécimo producto recibirá un mensaje indicando que el bloc de notas está lleno.
  - **Valor límite:** (Solo aparece si "Limitar número de productos en el bloc de notas" está configurado en SÍ)

    - **Qué hace este ajuste:** Especifica el número máximo exacto de productos permitidos en el bloc de notas.
    - **Efecto de cambiar este ajuste:** Establece el límite numérico para el bloc de notas.
    - **Valor recomendado:** Si eliges limitar, un número razonable como **20-50** suele ser suficiente, equilibrando la flexibilidad del cliente con el rendimiento potencial.
    - **Escenario / ejemplo del comerciante:** Si "Limitar número de productos" es SÍ y "Valor límite" es 25, los clientes pueden guardar hasta 25 productos.

#### Ajustes de Visualización

- **Qué hace este ajuste:** Esta sección controla dónde aparece el bloque del Bloc de Notas de Productos en el front office de tu tienda.

  - **Mostrar en la columna izquierda:**

    - **Qué hace este ajuste:** Controla si el bloque de resumen del bloc de notas se muestra en la columna izquierda de tu tienda.
    - **Efecto de cambiar este ajuste:**
      - *Cuando está activado (SÍ):* El bloque del bloc de notas aparecerá en la columna izquierda en las páginas que tienen una columna izquierda (por ejemplo, páginas de categoría, páginas de producto, páginas CMS).
      - *Cuando está desactivado (NO):* El bloque del bloc de notas no se mostrará en la columna izquierda.
    - **Valor recomendado:** **SÍ** (o columna derecha), ya que las columnas son un lugar común para este tipo de bloques de utilidad.
    - **Escenario / ejemplo del comerciante:** Un cliente que navega por una página de categoría verá el resumen de su bloc de notas en la barra lateral izquierda, lo que lo hace fácilmente accesible.
  - **Mostrar en la columna derecha:**

    - **Qué hace este ajuste:** Controla si el bloque de resumen del bloc de notas se muestra en la columna derecha de tu tienda.
    - **Efecto de cambiar este ajuste:**
      - *Cuando está activado (SÍ):* El bloque del bloc de notas aparecerá en la columna derecha en las páginas que tienen una columna derecha.
      - *Cuando está desactivado (NO):* El bloque del bloc de notas no se mostrará en la columna derecha.
    - **Valor recomendado:** **SÍ** (o columna izquierda). Elige una o ambas según el diseño de tu tema y otros módulos que tengas.
    - **Escenario / ejemplo del comerciante:** Si tu tema utiliza la columna derecha para promociones, podrías colocar el bloc de notas allí para mantener la columna izquierda libre para la navegación.
  - **Mostrar en el pie de página:**

    - **Qué hace este ajuste:** Controla si el bloque de resumen del bloc de notas se muestra en la sección del pie de página de tu tienda.
    - **Efecto de cambiar este ajuste:**
      - *Cuando está activado (SÍ):* El bloque del bloc de notas aparecerá en la parte inferior de cada página, típicamente como parte del contenido general del pie de página.
      - *Cuando está desactivado (NO):* El bloque del bloc de notas no se mostrará en el pie de página.
    - **Valor recomendado:** **NO** (a menos que tu tema tenga una sección de pie de página muy prominente para bloques de utilidad). Las columnas son generalmente más visibles para este tipo de característica.
    - **Escenario / ejemplo del comerciante:** Si tu pie de página ya está abarrotado de enlaces e información legal, añadir el bloc de notas allí podría hacerlo menos perceptible.
  - **Mostrar en la cabecera:**

    - **Qué hace este ajuste:** Controla si el bloque de resumen del bloc de notas se muestra en la sección de la cabecera de tu tienda.
    - **Efecto de cambiar este ajuste:**
      - *Cuando está activado (SÍ):* El bloque del bloc de notas aparecerá en la parte superior de cada página, a menudo cerca de los enlaces del carrito o de la cuenta.
      - *Cuando está desactivado (NO):* El bloque del bloc de notas no se mostrará en la cabecera.
    - **Valor recomendado:** **NO** (a menos que tu tema tenga un amplio espacio y un diseño específico para esto). Las cabeceras suelen estar reservadas para la navegación crítica y el carrito.
    - **Escenario / ejemplo del comerciante:** Un icono compacto en la cabecera podría funcionar, pero un bloque completo podría abarrotar la cabecera.
  - **Mostrar en la página de producto:**

    - **Qué hace este ajuste:** Controla si el botón "Añadir al Bloc de Notas" y potencialmente un pequeño resumen del bloc de notas se muestran directamente en las páginas de productos individuales.
    - **Efecto de cambiar este ajuste:**
      - *Cuando está activado (SÍ):* Los clientes verán el botón "Añadir al Bloc de Notas" en cada página de producto, lo que facilita guardar artículos mientras navegan.
      - *Cuando está desactivado (NO):* El botón "Añadir al Bloc de Notas" no aparecerá en las páginas de productos, lo que hace que la función sea menos accesible.
    - **Valor recomendado:** **SÍ**. Esta es una ubicación crucial para que la función sea efectiva.
    - **Escenario / ejemplo del comerciante:** Un cliente que ve un producto puede añadirlo inmediatamente a su bloc de notas para compararlo más tarde con otros productos.

#### Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Recordar productos en el bloc de notas | SÍ | Mantiene los elementos del bloc de notas guardados entre sesiones para una mejor UX. |
| Configuración del Módulo | Limitar número de productos en el bloc de notas | NO | Permite productos ilimitados en el bloc de notas, maximizando la elección del cliente. |
| Configuración del Módulo | Valor límite | (N/A si el límite es NO) | Establece el número máximo de productos si la limitación está activada. |
| Configuración del Módulo | Mostrar en la columna izquierda | SÍ | Muestra el resumen del bloc de notas en la barra lateral izquierda. |
| Configuración del Módulo | Mostrar en la columna derecha | SÍ | Muestra el resumen del bloc de notas en la barra lateral derecha. |
| Configuración del Módulo | Mostrar en el pie de página | NO | Evita saturar el pie de página, menos visible. |
| Configuración del Módulo | Mostrar en la cabecera | NO | Evita saturar la cabecera, menos visible. |
| Configuración del Módulo | Mostrar en la página de producto | SÍ | Esencial para que los clientes añadan fácilmente productos al bloc de notas. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: El bloc de notas no aparece en mi tienda. ¿Qué debo hacer?**
R1: Primero, verifica la configuración del módulo en tu Back Office (**Módulos > Gestor de Módulos > Bloc de Notas de Productos > Configurar**). Asegúrate de que al menos una opción de visualización (por ejemplo, "Mostrar en la columna izquierda" o "Mostrar en la página de producto") esté configurada en SÍ. Si aún no aparece, intenta borrar la caché de PrestaShop (**Parámetros Avanzados > Rendimiento > Borrar caché**). A veces, los conflictos de tema también pueden impedir que los módulos se muestren; cambia temporalmente al tema predeterminado de PrestaShop para descartar esto.

**P2: Los productos no se recuerdan en el bloc de notas después de que un cliente cierra su navegador.**
R2: Ve a la página de configuración del módulo (**Módulos > Gestor de Módulos > Bloc de Notas de Productos > Configurar**) y asegúrate de que la configuración "Recordar productos en el bloc de notas" esté establecida en **SÍ**. Esta opción utiliza cookies del navegador para almacenar el contenido del bloc de notas, así que asegúrate de que los clientes no hayan deshabilitado las cookies en su navegador.

**P3: El botón "Añadir al Bloc de Notas" se ve extraño o no tiene el estilo correcto en mis páginas de productos.**
R3: Esto suele ser un conflicto de CSS con tu tema personalizado. El módulo proporciona su propio estilo básico, pero los estilos de tu tema podrían estar anulándolo. Puedes:
1. Contactar a tu desarrollador de temas para obtener ayuda.
2. Usar el Editor de Temas en Vivo de PrestaShop (si está disponible en tu versión) o las herramientas de desarrollador del navegador (F12) para inspeccionar el botón y aplicar anulaciones de CSS personalizadas en el archivo `custom.css` de tu tema.
3. Ponerte en contacto con el soporte de MyPresta.eu para obtener orientación.

**P4: ¿Pueden los clientes compartir su bloc de notas con otros?**
R4: No, este módulo está diseñado para uso individual del cliente y no incluye funcionalidad para compartir. Es una ayuda personal para la navegación, no una lista de deseos colaborativa.

**P5: ¿Funcionará el bloc de notas con tiendas multi-idioma?**
R5: Sí, el módulo está diseñado para ser compatible con las funciones multi-idioma de PrestaShop. Cualquier texto mostrado por el módulo (como etiquetas de botones o títulos de bloques) se puede traducir a través de la interfaz de traducción de PrestaShop (**Internacional > Traducciones > Traducciones de módulos instalados**).

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo Bloc de Notas de Productos es un módulo estándar de PrestaShop que sigue un patrón similar a MVC. Utiliza principalmente controladores frontales para interacciones AJAX y renderizado, y plantillas Smarty para su visualización en el front-office. Se basa en cookies del navegador para la persistencia si está configurado para recordar productos. La lógica principal del módulo reside en `notepad.php` y sus controladores frontales asociados.

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**:

  - `controllers/front/ajaxload.php`
    - **Nombre de clase y clase padre**: `NotepadAjaxloadModuleFrontController` que extiende `ModuleFrontController`.
    - **Responsabilidad**: Este controlador maneja todas las solicitudes AJAX relacionadas con la funcionalidad del bloc de notas. Es responsable de añadir productos al bloc de notas, eliminarlos y potencialmente actualizar la visualización del bloc de notas. Procesa los datos enviados a través de POST o GET y devuelve respuestas JSON al JavaScript del front-end.
  - `controllers/front/index.php`
    - **Nombre de clase y clase padre**: `NotepadIndexModuleFrontController` que extiende `ModuleFrontController`.
    - **Responsabilidad**: Este controlador probablemente sirve como un recurso alternativo o una página dedicada para el bloc de notas si se implementa una vista de página completa. Dada la naturaleza principal de AJAX del módulo, este podría ser un punto de entrada menos utilizado, posiblemente redirigiendo o renderizando una vista completa del bloc de notas.
- **Controladores de Administración del Back-Office**: Ninguno. Toda la configuración se maneja a través del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Principales (`classes/`)

No se definen clases `ObjectModel` personalizadas en este módulo. Los datos del producto probablemente se almacenan directamente en cookies del navegador o variables de sesión, recuperados y procesados por la clase principal del módulo y los controladores frontales.

### 4.4 Activos JavaScript (`views/js/`)

- `admin.js`
  - **Alcance**: Back-office.
  - **Descripción**: Este script probablemente maneja las interacciones en la página de configuración del módulo en el Back Office de PrestaShop. Podría gestionar la visibilidad de los ajustes (por ejemplo, `notepad_limit_value` basado en `notepad_limit`), envíos de formularios o validación.
- `jscolor.js`
  - **Alcance**: Back-office (probablemente).
  - **Descripción**: Una biblioteca JavaScript de terceros para selectores de color. Si el módulo tuviera opciones de personalización de color para la visualización del bloc de notas, este script proporcionaría la interfaz de usuario para seleccionar colores en el panel de administración. (Según el inventario, está presente pero podría ser un remanente o para uso futuro si actualmente no se exponen configuraciones de color).
- `lib/searchTool/views/js/autocomplete.js`
  - **Alcance**: Front-office (potencialmente Back-office si se usa para la selección de productos).
  - **Descripción**: Este script proporciona funcionalidad de autocompletado, probablemente para buscar productos. Si el bloc de notas tuviera una función para añadir productos buscando, o si es parte de una biblioteca más amplia de "herramientas de búsqueda" incluida con el módulo, esto manejaría las llamadas AJAX y la visualización de sugerencias de búsqueda.
- `notepad.js`
  - **Alcance**: Front-office.
  - **Descripción**: Este es el JavaScript principal del front-office para la funcionalidad del bloc de notas.
    - **Escuchadores de eventos**: Vincula eventos de clic a los botones "Añadir al Bloc de Notas" (por ejemplo, en páginas de productos, listados de productos), enlaces/botones "Eliminar del Bloc de Notas" dentro del bloque del bloc de notas, y potencialmente el encabezado del bloque del bloc de notas para alternar su visibilidad o navegar a una vista completa.
    - **Llamadas AJAX**: Realiza solicitudes asíncronas a `controllers/front/ajaxload.php` para añadir, eliminar o recuperar el contenido del bloc de notas.
    - **Manipulación del DOM**: Actualiza el bloque de visualización del bloc de notas (por ejemplo, recuento de productos, lista de productos), muestra mensajes de éxito/error y renderiza dinámicamente las entradas de productos dentro del bloc de notas.
    - **Gestión de cookies**: Interactúa con las cookies del navegador para almacenar y recuperar los ID de productos del bloc de notas si la opción "Recordar productos" está activada.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `css/admincss.css`
  - **Alcance**: Estilo del formulario de administración del Back-office.
  - **Descripción**: Estilos para la página de configuración del módulo en el Back Office de PrestaShop, asegurando una apariencia consistente con el tema de administración de PrestaShop.
- `css/css.css`
  - **Alcance**: Estilo del cliente del Front-office.
  - **Descripción**: Contiene los estilos principales para el bloque de visualización del bloc de notas, el botón "Añadir al Bloc de Notas" y cualquier elemento asociado en la tienda.
  - **Selectores de clase CSS clave**: Los desarrolladores pueden inspeccionar el HTML generado en busca de clases como `.notepad-block`, `.add-to-notepad`, `.notepad-product-item` para anular estilos en el archivo `custom.css` o `theme.css` de su tema.
- `lib/searchTool/views/css/autocomplete.css`
  - **Alcance**: Front-office (o Back-office si se usa la herramienta de búsqueda allí).
  - **Descripción**: Estilos para el menú desplegable de resultados de búsqueda de autocompletado, si el script `autocomplete.js` se utiliza activamente para una función de búsqueda de productos dentro del módulo.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de gancho (`views/templates/hook/`)**:
  - `extraleft.tpl`
    - **Gancho**: Probablemente `displayLeftColumn` o similar.
    - **Propósito**: Renderiza el bloque principal de resumen del bloc de notas que aparece en la columna izquierda. Esto típicamente muestra un título, el número de artículos y una breve lista o enlace al bloc de notas completo.
  - `notepad.tpl`
    - **Gancho**: Esta podría ser una plantilla general incluida por otras plantillas o directamente enganchada a `displayRightColumn`, `displayFooter` o `displayHeader` según la configuración. Probablemente contiene la estructura central para el bloque del bloc de notas.
- **Plantillas de administración (`views/templates/admin/`)**: Ninguna explícitamente listada, la configuración probablemente se maneja directamente por `notepad.php` renderizando elementos de formulario.
- **Plantillas del Front-office (`views/templates/front/`)**:
  - `views/addToCart.tpl`
    - **Propósito**: Esta plantilla se renderiza en las páginas de productos (y potencialmente en los listados de productos) para mostrar el botón "Añadir al Bloc de Notas". Probablemente está enganchada a `displayProductButtons` o `displayProductActions`.
  - `views/selectedProducts.tpl`
    - **Propósito**: Esta plantilla se utiliza para mostrar la lista detallada de productos dentro del bloc de notas, ya sea en una ventana emergente, una página dedicada o dentro del bloque de columna expandido. Itera sobre los productos guardados en el bloc de notas y muestra su imagen, nombre, precio y una opción de "eliminar".
  - `lib/searchTool/views/scripts.tpl`
    - **Propósito**: Esta plantilla probablemente incluye el JavaScript y CSS necesarios para la biblioteca `searchTool`, como `autocomplete.js` y `autocomplete.css`, si el módulo utiliza una función de búsqueda. Se engancharía a `displayHeader` o `displayFooter` para cargar estos activos.

### 4.7 Esquema de Base de Datos y Mapa de Ganchos

- **Tablas de Base de Datos**: El módulo no parece crear ninguna tabla SQL personalizada. Los ID de productos y los datos relacionados con el bloc de notas se gestionan del lado del cliente, principalmente a través de cookies del navegador o variables de sesión. Los ajustes de configuración se almacenan en `ps_configuration` (por ejemplo, `NOTEPAD_REMEMBER`, `NOTEPAD_LIMIT`, `NOTEPAD_LIMIT_VALUE`).
- **Tabla de Ganchos Registrados**:

| Nombre del Gancho | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Para cargar los activos CSS y JS del módulo (por ejemplo, `notepad.js`, `css.css`) y potencialmente renderizar un resumen compacto del bloc de notas si está configurado. |
| `displayLeftColumn` | En la barra lateral izquierda de las páginas que tienen una. | Para mostrar el bloque principal de resumen del bloc de notas (`extraleft.tpl`). |
| `displayRightColumn` | En la barra lateral derecha de las páginas que tienen una. | Para mostrar el bloque principal de resumen del bloc de notas (`notepad.tpl` o similar). |
| `displayFooter` | En la sección del pie de página de cada página. | Para mostrar el bloque de resumen del bloc de notas si está configurado, o para cargar JS diferido. |
| `displayProductButtons` / `displayProductActions` (o gancho similar de página de producto) | En la página del producto, cerca del botón "Añadir al carrito". | Para renderizar el botón "Añadir al Bloc de Notas" (`views/addToCart.tpl`). |
| `actionFrontControllerSetMedia` | Antes de que el controlador frontal renderice su salida. | Para registrar los archivos CSS y JS del módulo para una carga óptima. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo Bloc de Notas de Productos, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto a la funcionalidad y compatibilidad del módulo.

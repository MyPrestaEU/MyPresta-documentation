---
title: "Características de las combinaciones de productos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Características de las combinaciones de productos' de MyPresta.eu."
sidebar:
  label: "Características de las combinaciones de productos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product combination features en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-combination-features.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-combination-features/)
>
> ---


# Características de las combinaciones de productos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Características de las combinaciones de productos". Puede acceder a ella navegando a **Módulos > Gestor de módulos**, buscando "Características de las combinaciones de productos" y haciendo clic en "Configurar".

#### **Activar características para combinaciones**

- **Qué hace este ajuste:** Este es el interruptor principal para habilitar o deshabilitar la funcionalidad central de asignar características únicas a las combinaciones de productos.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* Verá una nueva sección en sus páginas de edición de productos (en la pestaña "Módulos") donde puede asignar características específicas y sus valores a cada combinación. Cuando los clientes seleccionan una combinación en el front office, la ficha técnica del producto se actualizará dinámicamente para mostrar estas características específicas de la combinación.
  - *Cuando está deshabilitado:* La sección de gestión de características de combinación no aparecerá en las páginas de edición de productos, y el front office volverá a mostrar solo las características del producto principal, independientemente de la combinación seleccionada.
- **Valor recomendado:** **Habilitado** (si desea utilizar la función principal del módulo).
- **Escenario / ejemplo de comerciante:** Si vende camisetas y desea "Material: 100% Algodón" para la camiseta blanca y "Material: 50% Algodón, 50% Poliéster" para la camiseta gris, *debe* habilitar esto.

#### **Clase CSS de la ficha técnica**

- **Qué hace este ajuste:** Le permite especificar una clase CSS o ID de elemento HTML que el módulo debe apuntar al actualizar la sección de características en la página del producto. Esto es crucial para que el módulo identifique correctamente dónde mostrar las características específicas de la combinación en su tema.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece correctamente:* El módulo encontrará el elemento especificado e insertará o actualizará dinámicamente las características de la combinación dentro de él.
  - *Cuando se establece incorrectamente o se deja vacío:* Las características de la combinación podrían no aparecer en el front office, o podrían aparecer en una ubicación inesperada, ya que el módulo no sabrá dónde colocarlas.
- **Valor recomendado:** Esto depende completamente de su tema de PrestaShop. Una clase común es `.product-features` o `.data-sheet`. Es posible que deba inspeccionar el HTML de su página de producto para encontrar el selector correcto. Si no está seguro, consulte a su desarrollador de temas o a un webmaster.
- **Escenario / ejemplo de comerciante:** Su tema muestra las características del producto dentro de un `div` con la clase `product-specifications`. Aquí introduciría `.product-specifications`.

#### **Flujo de trabajo**

- **Qué hace este ajuste:** Controla cómo el módulo maneja las características cuando se selecciona una combinación.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "Añadir":* Las características específicas de la combinación se *añadirán* a las características del producto principal. Así, verá tanto las características generales del producto como las características únicas de la combinación.
  - *Cuando se establece en "Reemplazar":* Las características específicas de la combinación *reemplazarán* las características del producto principal. Solo se mostrarán las características relevantes para la combinación seleccionada.
- **Valor recomendado:** **Reemplazar** para la mayoría de los casos, ya que proporciona la información más precisa. Elija "Añadir" si tiene características generales que se aplican a todas las combinaciones, además de las específicas.
- **Escenario / ejemplo de comerciante:**
  - *Reemplazar:* Para un portátil, es posible que desee que "Procesador: i7", "RAM: 16GB" reemplace completamente a "Procesador: i5", "RAM: 8GB" cuando un cliente selecciona la combinación i7/16GB.
  - *Añadir:* Para una camiseta, es posible que siempre desee que se muestre "Marca: MiMarca" (característica general), pero luego *añadir* "Material: Algodón Orgánico" cuando se elige una combinación específica.

#### **Activar descripciones para combinaciones**

- **Qué hace este ajuste:** Habilita o deshabilita la capacidad de asignar descripciones únicas a cada combinación de producto.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* Aparecerá un nuevo campo en sus páginas de edición de productos (en la pestaña "Módulos") que le permitirá introducir una descripción específica para cada combinación. Cuando los clientes seleccionan una combinación, esta descripción reemplazará dinámicamente la descripción del producto principal.
  - *Cuando está deshabilitado:* El campo de descripción de la combinación no aparecerá, y el front office siempre mostrará la descripción del producto principal.
- **Valor recomendado:** **Habilitado** (si necesita descripciones específicas de la combinación).
- **Escenario / ejemplo de comerciante:** Vende joyas personalizadas. Un producto "Anillo de plata" podría tener una combinación "Grabado: Sí". Podría usar una descripción de combinación para explicar el proceso de grabado y los límites de caracteres, lo cual no es relevante para la combinación "Grabado: No".

#### **Clase CSS / ID de objeto de la descripción**

- **Qué hace este ajuste:** Similar a la "Clase CSS de la ficha técnica", esto le dice al módulo qué elemento HTML en su página de producto contiene la descripción del producto principal que debe ser reemplazada por la descripción específica de la combinación.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece correctamente:* El módulo encontrará el elemento especificado y actualizará dinámicamente su contenido con la descripción de la combinación.
  - *Cuando se establece incorrectamente o se deja vacío:* La descripción de la combinación podría no aparecer, o podría aparecer en un lugar inesperado.
- **Valor recomendado:** Esto depende de su tema. Los selectores comunes son `.product-description`, `#description_short` o `#product-description-short`. Deberá inspeccionar el HTML de su página de producto.
- **Escenario / ejemplo de comerciante:** Su tema utiliza un `div` con el ID `product-description-full` para la descripción principal. Aquí introduciría `#product-description-full`.

#### **Activar meta título para combinaciones**

- **Qué hace este ajuste:** Habilita o deshabilita la capacidad de establecer un meta título único para cada combinación de producto. Este meta título es lo que aparece en la pestaña del navegador y es utilizado por los motores de búsqueda.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* Aparecerá un nuevo campo en sus páginas de edición de productos (en la pestaña "Módulos") que le permitirá introducir un meta título específico para cada combinación. Cuando un cliente selecciona una combinación, el título de la pestaña del navegador se actualizará dinámicamente.
  - *Cuando está deshabilitado:* El campo de meta título de la combinación no aparecerá, y la pestaña del navegador siempre mostrará el meta título del producto principal.
- **Valor recomendado:** **Habilitado** (si desea mejorar el SEO para combinaciones específicas o proporcionar títulos de pestañas de navegador más claros).
- **Escenario / ejemplo de comerciante:** Para un producto "Smartphone", podría tener una combinación "Color: Azul, Almacenamiento: 128GB". Podría establecer su meta título como "Smartphone Azul 128GB - [Nombre de su tienda]" para una mejor visibilidad en los motores de búsqueda.

#### **Modo de título predeterminado**

- **Qué hace este ajuste:** Define cómo se construye el meta título de la combinación si no establece uno explícitamente para una combinación, o si desea combinar el título del producto con los atributos de la combinación.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "Nombre del producto + nombre de la combinación":* El meta título será el nombre del producto principal seguido de los nombres de los atributos de la combinación seleccionada (por ejemplo, "Camiseta - Roja, Grande").
  - *Cuando se establece en "Nombre de la combinación + nombre del producto":* El meta título serán los nombres de los atributos de la combinación seleccionada seguidos del nombre del producto principal (por ejemplo, "Roja, Grande - Camiseta").
  - *Cuando se establece en "Nombre de la combinación":* Solo se utilizarán los nombres de los atributos de la combinación (por ejemplo, "Roja, Grande").
  - *Cuando se establece en "Nombre del producto":* El meta título siempre será el nombre del producto principal, ignorando las combinaciones.
- **Valor recomendado:** **"Nombre del producto + nombre de la combinación"** o **"Nombre de la combinación + nombre del producto"** para un buen equilibrio entre la identidad del producto y la especificidad de la combinación.
- **Escenario / ejemplo de comerciante:** Vende zapatos. Si un cliente selecciona "Talla 10, Color Negro", y se elige "Nombre del producto + nombre de la combinación", el título se convierte en "Zapatillas de correr - Talla 10, Negro".

#### **Separador de título**

- **Qué hace este ajuste:** Le permite definir el carácter o la cadena utilizada para separar las diferentes partes del meta título generado dinámicamente (por ejemplo, entre el nombre del producto y el nombre de la combinación).
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "-":* El título podría verse como "Nombre del producto - Combinación".
  - *Cuando se establece en "|":* El título podría verse como "Nombre del producto | Combinación".
  - *Cuando se deja vacío:* Las partes del título podrían unirse sin un separador claro.
- **Valor recomendado:** **-** (guion) o **|** (barra vertical) son separadores comunes y claros.
- **Escenario / ejemplo de comerciante:** Si su modo de título predeterminado es "Nombre del producto + nombre de la combinación" y el separador se establece en "|", un título podría convertirse en "Mi camiseta increíble | Roja, Grande".

### 2.2 Pantallas de administración dedicadas y vistas de controlador

Este módulo no crea pantallas de administración de nivel superior dedicadas. En su lugar, se integra directamente en la **Página de edición de productos** existente en su Back Office de PrestaShop.

- **Nombre de la pantalla y ubicación del menú:**

  - Navegue a **Catálogo > Productos**.
  - Edite un producto existente o cree uno nuevo.
  - Dentro de la página de edición del producto, haga clic en la pestaña **"Módulos"**.
  - Encontrará una nueva sección titulada **"Características de las combinaciones de productos"** (o similar, dependiendo de la versión/traducciones del módulo).
- **Acciones y configuraciones disponibles:**

  - Dentro de esta sección, verá una lista de todas las combinaciones configuradas para el producto actual.
  - Para cada combinación, tendrá campos para:
    - **Asignar características:** Puede seleccionar características existentes y sus valores, o incluso crear nuevos valores de características, específicamente para esa combinación. El módulo admite múltiples características, lo que significa que una combinación puede tener varios valores para la misma característica (por ejemplo, "Material: Algodón, Material: Spandex").
    - **Introducir descripción de la combinación:** Un editor de texto enriquecido (como el editor de descripción estándar de PrestaShop) estará disponible para introducir una descripción única para esa combinación.
    - **Introducir meta título de la combinación:** Un campo de texto para introducir un meta título único para esa combinación.
  - **Guardar cambios:** Recuerde hacer clic en el botón principal "Guardar" para que el producto aplique todos los cambios específicos de la combinación.
- **Efecto de los cambios:**

  - Cualquier característica, descripción o meta título que establezca aquí se almacenará en la base de datos y se mostrará dinámicamente en la página del producto del front office cuando el cliente seleccione la combinación correspondiente.
  - Si elimina una combinación, sus características, descripciones y meta títulos asociados también se eliminarán.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

  1. Primero, cree su producto y sus combinaciones como de costumbre en PrestaShop (en la pestaña "Combinaciones").
  2. Una vez creadas las combinaciones, vaya a la pestaña **"Módulos"** en la página de edición del producto.
  3. Para cada combinación, asigne cuidadosamente las características relevantes, escriba una descripción específica y establezca un meta título optimizado.
  4. Guarde el producto.
  5. Siempre pruebe en el front office para asegurarse de que las características, descripciones y títulos se actualicen correctamente cuando se seleccionan las combinaciones.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Activar características para combinaciones | Habilitado | Interruptor principal para las características de la combinación. |
| Configuración del módulo | Clase CSS de la ficha técnica | `.product-features` (depende del tema) | Selector CSS para dónde se muestran las características de la combinación. |
| Configuración del módulo | Flujo de trabajo | Reemplazar | Cómo interactúan las características de la combinación con las características del producto principal (añadir o reemplazar). |
| Configuración del módulo | Activar descripciones para combinaciones | Habilitado | Interruptor principal para las descripciones de la combinación. |
| Configuración del módulo | Clase CSS / ID de objeto de la descripción | `#product-description-short` (depende del tema) | Selector CSS para dónde se muestran las descripciones de la combinación. |
| Configuración del módulo | Activar meta título para combinaciones | Habilitado | Interruptor principal para los meta títulos de la combinación. |
| Configuración del módulo | Modo de título predeterminado | Nombre del producto + nombre de la combinación | Cómo se generan los meta títulos si no se establecen explícitamente. |
| Configuración del módulo | Separador de título | `-` | Carácter utilizado para separar partes del meta título. |
| Página de edición de productos > Pestaña Módulos | Asignar características por combinación | N/A | Asignar características y valores únicos a cada combinación. |
| Página de edición de productos > Pestaña Módulos | Descripción de la combinación | N/A | Introducir una descripción de texto enriquecido única para cada combinación. |
| Página de edición de productos > Pestaña Módulos | Meta título de la combinación | N/A | Introducir un meta título único para cada combinación. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis características/descripciones de combinación no aparecen en la página del producto.**
R:

1. **Verifique la configuración del módulo:** Asegúrese de que "Activar características para combinaciones" y/o "Activar descripciones para combinaciones" estén habilitadas en la configuración del módulo.
2. **Verifique los selectores CSS:** Los ajustes "Clase CSS de la ficha técnica" y "Clase CSS / ID de objeto de la descripción" son cruciales. Deben coincidir exactamente con la clase CSS o el ID de los elementos de su tema donde se muestran las características/descripción. Utilice las herramientas de desarrollo de su navegador (F12) para inspeccionar la página de su producto y encontrar los selectores correctos. Si no está seguro, consulte a su desarrollador de temas.
3. **Borre la caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché". A veces, el contenido antiguo en caché impide que aparezca la nueva salida del módulo.
4. **Verifique la configuración del producto:** Asegúrese de haber asignado realmente características/descripciones a las combinaciones específicas en la página de edición del producto en la pestaña "Módulos".

**P: Las características/descripciones de la combinación aparecen, pero se ven sin estilo o fuera de lugar.**
R: Esto suele ser un conflicto de CSS con su tema.

1. **Inspeccione con las herramientas del navegador:** Use F12 para ver qué reglas CSS se están aplicando a la salida del módulo.
2. **Ajuste la clase CSS:** Si la salida del módulo está envuelta en un `div` genérico, es posible que deba ajustar la "Clase CSS de la ficha técnica" o la "Clase CSS / ID de objeto de la descripción" a un contenedor más específico que su tema ya estilice.
3. **CSS personalizado:** Es posible que deba agregar CSS personalizado a la hoja de estilo de su tema (o a través de un módulo CSS personalizado) para estilizar las características/descripciones de la combinación para que coincidan con la apariencia de su tema.

**P: Mis meta títulos de combinación no cambian en la pestaña del navegador.**
R:

1. **Habilite la configuración:** Asegúrese de que "Activar meta título para combinaciones" esté habilitado en la configuración del módulo.
2. **Establezca los títulos:** Asegúrese de haber introducido meta títulos específicos para sus combinaciones en la página de edición del producto.
3. **Comportamiento del navegador:** Algunos navegadores pueden no actualizar inmediatamente el título de la pestaña para las pestañas ya abiertas. Intente abrir la página del producto en una nueva pestaña o borre la caché de su navegador.
4. **Implicaciones SEO:** Si bien el módulo actualiza el título del lado del cliente, para que los motores de búsqueda capten estos títulos específicos de la combinación, deben poder rastrear e indexar el contenido generado dinámicamente. Asegúrese de que su sitio sea rastreable y considere si estos títulos dinámicos son realmente beneficiosos para su estrategia SEO en comparación con los títulos de productos estáticos.

**P: ¿Puedo usar este módulo con tiendas multilingües?**
R: Sí, el módulo es totalmente compatible con varios idiomas. Cuando edite las características, descripciones o meta títulos de la combinación en la página del producto, verá el selector de idioma estándar de PrestaShop, lo que le permitirá introducir contenido para cada idioma.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Características de las combinaciones de productos" (`combfeat`) extiende la gestión de productos principales de PrestaShop inyectando campos y lógica personalizados en la página de edición de productos del Back Office y actualizando dinámicamente el contenido del Front Office en función de las combinaciones de productos seleccionadas. Aprovecha el sistema de hooks de PrestaShop para integrarse sin problemas sin modificar los archivos principales. El módulo opera principalmente a través de JavaScript en el front-end para actualizaciones dinámicas y PHP en el back-end para la configuración y gestión de datos. No introduce nuevas tablas de base de datos, sino que almacena sus datos en las estructuras existentes de PrestaShop (probablemente `ps_product_attribute_feature` para características y `ps_product_attribute_lang` para descripciones/títulos, o `ps_configuration` para la configuración del módulo).

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores de administración de Front-Office o Back-Office dedicados. Su lógica para mostrar y guardar datos de combinación se integra directamente en el archivo principal del módulo `combfeat.php` y a través de JavaScript.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define clases personalizadas en el directorio `classes/`. Su lógica central está contenida dentro del archivo principal `combfeat.php`, interactuando directamente con los `ObjectModel` de `Product` y `Combination` (ProductAttribute) de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

- **`combfeat/views/js/acplt.js`**

  - **Alcance:** Probablemente Back-office (página de producto de administración).
  - **Responsabilidad:** Este script parece ser una biblioteca de autocompletado personalizada o un componente utilizado para seleccionar características y sus valores para las combinaciones. Manejaría las solicitudes AJAX para obtener las características y valores disponibles, y gestionaría la interfaz de usuario para agregarlos/eliminarlos de una combinación.
  - **Interacciones clave:** Escuchadores de eventos para campos de entrada, llamadas AJAX a un hook del módulo o controlador de administración para datos, manipulación del DOM para mostrar sugerencias y elementos seleccionados.
- **`combfeat/views/js/admin-combfeat.js`**

  - **Alcance:** Back-office (página de producto de administración, pestaña "Módulos").
  - **Responsabilidad:** Este es el script principal para la funcionalidad del módulo dentro de la página de edición de productos del Back Office de PrestaShop. Inicializa los campos de características, descripción y meta título de la combinación. Probablemente escucha los cambios en la selección de la combinación (si los hay) y gestiona la visualización y el guardado de datos para cada combinación.
  - **Interacciones clave:** Manipulación del DOM para inyectar campos personalizados, escuchadores de eventos para cambios de entrada, potencialmente llamadas AJAX para guardar datos específicos de la combinación.
- **`combfeat/views/js/combfeat-append.js`**

  - **Alcance:** Front-office (página de producto).
  - **Responsabilidad:** Este script es específicamente para la opción de flujo de trabajo "Añadir". Cuando se selecciona una combinación, busca y *agrega* dinámicamente las características específicas de la combinación a las características existentes del producto en el front-end.
  - **Interacciones clave:** Escucha eventos `updateProduct` o similares (activados por la selección de la combinación), llamadas AJAX para obtener datos de la combinación, manipulación del DOM para añadir características al elemento especificado por `combfeat_ds`.
- **`combfeat/views/js/combfeat-title.js`**

  - **Alcance:** Front-office (página de producto).
  - **Responsabilidad:** Este script maneja la actualización dinámica del meta título del navegador en función de la combinación de producto seleccionada.
  - **Interacciones clave:** Escucha eventos `updateProduct` o similares, recupera el meta título de la combinación (ya sea personalizado o generado en función de la configuración del módulo) y actualiza `document.title`.
- **`combfeat/views/js/combfeat.js`**

  - **Alcance:** Front-office (página de producto).
  - **Responsabilidad:** Este es el script principal del front-office para el módulo. Orquesta la visualización dinámica de las características y descripciones específicas de la combinación. Probablemente escucha los cambios en las combinaciones de productos (por ejemplo, selección de atributos) y activa actualizaciones en los elementos DOM relevantes. Este script manejaría el flujo de trabajo "Reemplazar" para las características y la actualización de la descripción.
  - **Interacciones clave:** Escucha eventos `updateProduct` o similares (por ejemplo, `prestashop.on('updatedProduct', ...) `), llamadas AJAX para recuperar datos de la combinación, manipulación del DOM para actualizar los elementos especificados por `combfeat_ds` y `combfeat_description`.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`combfeat/views/css/combfeat.css`**
  - **Alcance:** Tanto Front-office como Back-office.
  - **Responsabilidad:** Proporciona un estilo básico para los elementos inyectados del módulo. Esto podría incluir el estilo para los campos de entrada de características/descripciones de la combinación en el Back Office, o para los bloques de características/descripciones actualizados dinámicamente en el Front Office.
  - **Selectores de clase CSS clave:** Probablemente apunta a clases utilizadas por las plantillas y JavaScript del módulo, como `.combfeat-feature-list`, `.combfeat-description-wrapper`, o estilos específicos para el componente de autocompletado. Los desarrolladores podrían necesitar anular estos en el `custom.css` o `theme.css` de su tema para una integración perfecta.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`combfeat/views/templates/admin/combfeat.tpl`**

  - **Alcance:** Plantilla de administración.
  - **Responsabilidad:** Esta plantilla renderiza la sección personalizada dentro de la pestaña "Módulos" en la página de edición de productos en el Back Office. Muestra la interfaz para gestionar las características, descripciones y meta títulos específicos de la combinación. Probablemente itera a través de todas las combinaciones de productos y proporciona campos de entrada para cada una.
  - **Elementos clave:** Bucles para combinaciones, campos de entrada para la selección de características (posiblemente utilizando el componente `acplt.js`), editor de texto enriquecido para descripciones, entrada de texto para meta títulos.
- **`combfeat/views/templates/hook/product-details.tpl`**

  - **Alcance:** Plantilla de hook del Front-office.
  - **Responsabilidad:** Esta plantilla probablemente está enganchada a `displayProductAdditionalInfo` o hooks similares para renderizar las características y/o descripción específicas de la combinación en la página del producto del front office. Proporciona la estructura HTML que `combfeat.js` y `combfeat-append.js` poblarán y actualizarán dinámicamente.
  - **Elementos clave:** Marcadores de posición (por ejemplo, `div`s vacíos con ID o clases específicas) donde las características y descripciones de la combinación serán inyectadas por JavaScript.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo no crea nuevas tablas personalizadas. Probablemente almacena las características específicas de la combinación extendiendo la relación `ps_product_attribute_feature` o similar, y las descripciones/meta títulos de la combinación en `ps_product_attribute_lang` o una estructura similar, asociándolos con `id_product_attribute` e `id_lang`.
  - La configuración del módulo (`combfeat_ds`, `combfeat_description`, etc.) se almacena en la tabla `ps_configuration`.
- **Tabla de hooks registrados**:

| Nombre del Hook | Alcance | Momento de ejecución | Propósito técnico |
| --- | --- | --- | --- |
| `displayHeader` | Front-office | En la sección `<head>` de todas las páginas del front-office. | Registra los activos CSS y JS del front-office (`combfeat.css`, `combfeat.js`, `combfeat-append.js`, `combfeat-title.js`). |
| `DisplayHeader` | Front-office | Alias para `displayHeader`. | Igual que `displayHeader`. |
| `displayProductAdditionalInfo` | Front-office | En la página del producto, normalmente debajo de la información principal del producto. | Renderiza la plantilla `product-details.tpl`, proporcionando un marcador de posición para las características/descripciones de la combinación. |
| `ActionAdminControllerSetMedia` | Back-office | Cuando se carga un controlador de administración y se establecen sus activos multimedia. | Registra los activos CSS y JS del back-office (`combfeat.css`, `acplt.js`, `admin-combfeat.js`) para la página de edición del producto. |
| `ActionProductUpdate` | Back-office | Después de que se actualiza un producto (incluidas las combinaciones). | Potencialmente utilizado para guardar o sincronizar datos específicos de la combinación cuando se envía el formulario del producto. |
| `actionProductUpdate` | Back-office | Alias para `ActionProductUpdate`. | Igual que `ActionProductUpdate`. |
| `displayAdminProductsExtra` | Back-office | En la página de edición del producto, normalmente como una nueva pestaña o sección. | Renderiza la plantilla `admin/combfeat.tpl`, creando la sección "Características de las combinaciones de productos" en la pestaña "Módulos". |
| `DisplayAdminProductsExtra` | Back-office | Alias para `displayAdminProductsExtra`. | Igual que `displayAdminProductsExtra`. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Características de las combinaciones de productos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.

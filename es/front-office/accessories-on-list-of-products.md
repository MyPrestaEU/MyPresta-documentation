---
title: "Accesorios en la lista de productos - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Accesorios en la lista de productos' de MyPresta.eu."
sidebar:
  label: "Accesorios en la lista de productos - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Accessories on list of products en MyPresta.eu](https://mypresta.eu/modules/front-office-features/accessories-on-list-of-products.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/accessories-on-list-of-products/)
>
> ---


# Accesorios en la lista de productos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son típicamente requeridas por PrestaShop y son suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en el botón "Configurar" junto al módulo "Accesorios en la lista de productos" en el Gestor de módulos. Esto le llevará a la pantalla de configuración principal.

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo de comerciante |
| --- | --- | --- | --- | --- |
| **Corregir error del tema classic** | Este ajuste aborda un problema de visualización específico que puede ocurrir con el tema Classic predeterminado de PrestaShop o temas basados en él, donde los accesorios podrían no renderizarse correctamente. | *Cuando está habilitado:* El módulo aplica una corrección para asegurar que los accesorios se muestren correctamente en las listas de productos, especialmente con el tema Classic. *Cuando está deshabilitado:* La corrección no se aplica. Si está utilizando el tema Classic o un derivado, los accesorios podrían no aparecer correctamente o podrían tener problemas de diseño. | **SÍ** (Si utiliza el tema Classic o un tema basado en él) / **NO** (Si utiliza un tema completamente personalizado y no experimenta problemas) | Si ha instalado el módulo y los accesorios no aparecen o se ven rotos en sus páginas de categoría, habilitar este ajuste es el primer paso para solucionar problemas, especialmente si está utilizando el tema Classic. Si su tema está muy personalizado y no muestra este error, podría mantenerlo deshabilitado para evitar posibles conflictos, aunque generalmente es seguro habilitarlo. |
| **Habilitado / Deshabilitado** | Este es el interruptor principal para activar o desactivar la funcionalidad del módulo en toda su tienda. | *Cuando está habilitado:* El módulo mostrará activamente los accesorios en las páginas de listado de productos como se describe. *Cuando está deshabilitado:* La funcionalidad del módulo está completamente desactivada, y no aparecerán accesorios en las listas de productos. | **Habilitado** | Ha terminado de configurar sus accesorios para los productos y quiere que aparezcan en su tienda en vivo. Lo habilitaría. Si necesita ocultar temporalmente los accesorios para mantenimiento o una campaña especial, lo deshabilitaría. |

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Corregir error del tema classic | SÍ (para usuarios del tema Classic) | Resuelve problemas de visualización de accesorios en las listas de productos con el tema Classic. |
| Página de configuración del módulo | Habilitado / Deshabilitado | Habilitado | Activa o desactiva la funcionalidad principal del módulo. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Los accesorios no aparecen en las páginas de mi lista de productos.**
R:

1. **Verificar el estado del módulo**: Asegúrese de que el módulo esté "Habilitado" en su configuración.
2. **Verificar la asignación de accesorios**: Verifique que los productos principales realmente tengan accesorios asignados en la página de edición de productos de PrestaShop (en la pestaña "Accesorios").
3. **Compatibilidad del tema**: Si está utilizando un tema personalizado, podría anular la plantilla estándar de lista de productos de una manera que impida que el módulo se enganche correctamente. Intente habilitar la configuración "Corregir error del tema classic", incluso si no está utilizando el tema Classic, ya que podría resolver algunos problemas generales de visualización.
4. **Borrar caché**: Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, la caché de PrestaShop necesita ser actualizada para reflejar los nuevos cambios del módulo.

**P: Los accesorios se ven extraños o están desalineados en mi tienda.**
R:

1. **"Corregir error del tema classic"**: Intente habilitar esta configuración en la configuración del módulo. Aborda específicamente los problemas de diseño.
2. **Conflicto de CSS del tema**: El CSS de su tema podría estar en conflicto con el estilo del módulo. Esto a menudo requiere que un webmaster o desarrollador inspeccione el CSS y realice ajustes.
3. **Borrar caché**: Siempre borre la caché de PrestaShop después de realizar cambios en la configuración.

**P: ¿Puedo controlar qué accesorios aparecen para productos específicos?**
R: Sí, el módulo utiliza la función nativa de asignación de accesorios de PrestaShop. Para añadir o eliminar accesorios para un producto, vaya a **Catálogo > Productos**, edite el producto deseado y navegue a la pestaña "Accesorios". Aquí puede buscar y añadir/eliminar productos asociados.

**P: ¿Este módulo ralentiza mi tienda?**
R: El módulo está diseñado para ser eficiente. Aprovecha los datos de accesorios existentes de PrestaShop. Sin embargo, si tiene miles de productos, cada uno con docenas de accesorios, y sus recursos de servidor son limitados, cualquier carga de datos adicional puede tener un impacto menor. Para la mayoría de las tiendas, el impacto en el rendimiento es insignificante.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Accesorios en la lista de productos" (`accol`) es un módulo estándar de PrestaShop centrado principalmente en la visualización en el front-office. Extiende `Module` y aprovecha el sistema de hooks de PrestaShop para inyectar datos y renderizado de accesorios en las plantillas de lista de productos existentes. No introduce nuevas tablas de base de datos ni controladores personalizados complejos, lo que lo hace ligero y enfocado en su propósito de visualización. La lógica del módulo está contenida en su archivo PHP principal, con JS y CSS asociados para el estilo y la interacción.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno. El módulo inyecta su contenido directamente en las plantillas de lista de productos existentes a través de hooks.
- **Controladores de Administración de Back-Office**: Ninguno. La configuración se maneja directamente a través del método `getContent()` en el archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

- El módulo no define ninguna clase personalizada en el directorio `classes/`. Toda la lógica principal reside dentro del archivo principal del módulo `accol.php`.
- Interactúa con los métodos estándar de PrestaShop `Product` y `Product::getAccessories()` para recuperar los datos de los accesorios.

### 4.4 Activos JavaScript (`views/js/`)

- **`accol/js/accol.js`**
  - **Alcance**: Front-office.
  - **Propósito**: Este script es responsable de manejar la visualización dinámica y las posibles interacciones con las listas de accesorios. Podría incluir lógica para carruseles responsivos (si se implementan), mostrar/ocultar bloques de accesorios o llamadas AJAX para añadir accesorios al carrito (aunque la función principal del módulo es la visualización, no la adición directa al carrito mediante AJAX). Es probable que se cargue a través del hook `displayHeader` o `header`.
  - **Detalles**: Puede enlazar escuchadores de eventos a elementos de accesorios, gestionar su visibilidad o inicializar cualquier biblioteca de terceros utilizada para carruseles o deslizadores si el módulo implementa tales características para la visualización de accesorios.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`accol/css/accol.css`**
  - **Alcance**: Estilo del cliente en el front-office.
  - **Propósito**: Esta hoja de estilo proporciona el estilo visual necesario para las listas de accesorios mostradas en las páginas de productos.
  - **Componentes e contenedores principales de la interfaz de usuario**: Estiliza el contenedor de accesorios, los elementos individuales de accesorios (imágenes, nombres, precios) y, potencialmente, cualquier elemento de navegación (como flechas para carruseles).
  - **Selectores de clase CSS clave**: Los desarrolladores pueden esperar selectores como `.accol-accessories-list`, `.accol-accessory-item`, `.accol-accessory-image`, `.accol-accessory-name`, etc., que pueden ser anulados en el `custom.css` o `theme.css` de un tema personalizado para que coincidan con la estética del tema.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - `accol/accol.tpl`: Esta es la plantilla principal del front-office responsable de renderizar la lista de accesorios para un producto dado. Es probable que esté enganchada a `displayProductListReviews` o un hook similar que permita inyectar contenido en el bucle de elementos de la lista de productos. Recibe un array de productos accesorios e itera a través de ellos para mostrar sus imágenes, nombres y, potencialmente, precios.
- **Plantillas de administración (`views/templates/admin/`)**:
  - `accol/admin.tpl`: Esta plantilla se utiliza para la página de configuración del módulo en el Back Office de PrestaShop. Contiene los elementos del formulario HTML para las configuraciones "Corregir error del tema classic" y "Habilitado/Deshabilitado", junto con cualquier mensaje informativo o botones de guardar.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: El módulo no crea ninguna tabla de base de datos personalizada. Se basa en la tabla nativa `ps_product_accessory` de PrestaShop (que vincula productos con sus accesorios) y `ps_configuration` para sus propias configuraciones (`ACCOL_FIX`).
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Se utiliza para cargar los activos CSS (`accol.css`) y JavaScript (`accol.js`) para la visualización en el front-office. |
| `displayProductListReviews` | Dentro del bucle de elementos de la lista de productos, típicamente debajo de la información principal del producto. | El hook principal utilizado para inyectar la plantilla `accol.tpl`, renderizando los accesorios para cada producto en la lista. Este hook a menudo está disponible en `product-list.tpl` o plantillas similares. |
| `header` | (Alias para `displayHeader` en muchos contextos, especialmente versiones anteriores de PrestaShop). | Mismo propósito que `displayHeader`: cargar activos. |
| `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador frontal está configurando sus activos multimedia. | Se puede utilizar para añadir CSS/JS condicionalmente según el contexto de la página actual, asegurando que los activos se carguen solo cuando sea necesario. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Accesorios en la lista de productos", consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.

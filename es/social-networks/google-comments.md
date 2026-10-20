---
title: "Comentarios de Google+ - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Comentarios de Google+ de MyPresta.eu."
sidebar:
  label: "Comentarios de Google+ - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Google+ Comments en MyPresta.eu](https://mypresta.eu/modules/social-networks/google-comments.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/google-comments/)
>
> ---


# Comentarios de Google+

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo Comentarios de Google+. Aquí encontrará todos los ajustes para controlar cómo aparecen y funcionan los comentarios en su tienda.

**Acceso:** Navegue a **Módulos > Gestor de Módulos**, busque "Comentarios de Google+", y haga clic en **"Configurar"**.

#### Ajustes y Opciones

1.  **Mostrar Comentarios de Google+ en la Página del Producto**

    -   **Qué hace este ajuste:** Este interruptor controla si la sección de comentarios de Google+ se muestra en las páginas de sus productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (SÍ):* La sección de comentarios de Google+ aparecerá en todas las páginas de sus productos, permitiendo a los clientes ver y añadir comentarios.
        -   *Cuando está deshabilitado (NO):* La sección de comentarios de Google+ se ocultará de todas las páginas de productos.
    -   **Valor recomendado:** SÍ (si desea utilizar la función de comentarios).
    -   **Escenario / ejemplo del comerciante:** Si desea fomentar la interacción con el cliente y aprovechar el contenido generado por el usuario, habilite esta opción. Si prefiere un sistema de comentarios diferente o ningún comentario, desactívela.
2.  **Elegir Hook para Comentarios de Google+**

    -   **Qué hace este ajuste:** Este desplegable le permite seleccionar dónde se mostrará el bloque de comentarios de Google+ en la página del producto (u otras páginas). Los hooks son ubicaciones específicas en su tema de PrestaShop donde los módulos pueden inyectar contenido.
    -   **Efecto de cambiar este ajuste:**
        -   *Seleccionar `displayProductExtraContent` (o un hook similar de página de producto):* Los comentarios aparecerán dentro del área de contenido principal de la página del producto, típicamente debajo de la descripción del producto o las pestañas. Esta es la ubicación más común y recomendada.
        -   *Seleccionar `displayLeftColumn` o `displayRightColumn`:* El bloque de comentarios aparecerá en la barra lateral izquierda o derecha de su tienda (si su tema las tiene y están activas en las páginas de productos). Esto generalmente no es ideal para una sección de comentarios completa.
        -   *Seleccionar `displayFooter`:* El bloque de comentarios aparecerá en la sección del pie de página de su tienda. De nuevo, no es ideal para comentarios específicos del producto.
    -   **Valor recomendado:** `displayProductExtraContent` o un hook similar que coloque los comentarios directamente en el área de contenido de la página del producto. El nombre exacto del hook puede variar ligeramente entre versiones de PrestaShop o temas, pero apunte a uno que se integre bien con los detalles del producto.
    -   **Escenario / ejemplo del comerciante:** Desea que los comentarios sean fácilmente visibles cuando un cliente está revisando un producto. Elegir `displayProductExtraContent` asegura que sea parte del flujo de información principal del producto.
3.  **Ancho del Bloque de Comentarios de Google+ (en píxeles)**

    -   **Qué hace este ajuste:** Este campo de entrada le permite definir el ancho fijo de la sección de comentarios de Google+ en píxeles.
    -   **Efecto de cambiar este ajuste:**
        -   *Establecer un valor de píxeles específico (por ejemplo, `600`):* El bloque de comentarios siempre intentará renderizarse con ese ancho exacto. Si la pantalla es más pequeña, podría desbordarse o causar problemas de diseño.
        -   *Dejar vacío o establecer en `100%` (si el módulo lo permite, aunque típicamente espera píxeles):* El módulo podría intentar ajustarse automáticamente, pero para los comentarios de Google+, a menudo se espera un ancho fijo en píxeles.
    -   **Valor recomendado:** Un valor que se ajuste bien al área de contenido principal de su página de producto, típicamente de `600` a `800` píxeles, dependiendo del diseño de su tema. Es posible que deba experimentar para encontrar el mejor ajuste.
    -   **Escenario / ejemplo del comerciante:** El área de contenido de su página de producto tiene 700px de ancho. Establecer esto en `650`px asegura que el bloque de comentarios encaje bien sin romper el diseño.
4.  **Número de Comentarios a Mostrar**

    -   **Qué hace este ajuste:** Este campo de entrada controla cuántos comentarios se cargan y muestran inicialmente en la sección de comentarios de Google+. Normalmente, el usuario puede cargar más comentarios haciendo clic en un botón "Cargar más" proporcionado por Google.
    -   **Efecto de cambiar este ajuste:**
        -   *Establecer un número bajo (por ejemplo, `5`):* Solo se mostrarán unos pocos comentarios inicialmente, lo que hará que la página se cargue más rápido y parezca menos desordenada. Los usuarios deberán hacer clic para ver más.
        -   *Establecer un número alto (por ejemplo, `20`):* Se verán más comentarios inmediatamente, lo que puede ser bueno para productos con muchos comentarios, pero podría hacer que la página sea más larga.
    -   **Valor recomendado:** `5` a `10`. Esto proporciona un buen equilibrio entre mostrar participación y mantener la página concisa.
    -   **Escenario / ejemplo del comerciante:** Tiene muchos comentarios en productos populares. Establecer esto en `7` muestra suficiente participación sin abrumar al cliente con un desplazamiento muy largo.

#### Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Mostrar Comentarios de Google+ en la Página del Producto | SÍ | Habilita/deshabilita la sección de comentarios en las páginas de productos. |
| Configuración del Módulo | Elegir Hook para Comentarios de Google+ | `displayProductExtraContent` | Determina dónde aparece el bloque de comentarios en la página. |
| Configuración del Módulo | Ancho del Bloque de Comentarios de Google+ (en píxeles) | `600` - `800` | Establece el ancho fijo de la sección de comentarios. Ajustar para que se adapte a su tema. |
| Configuración del Módulo | Número de Comentarios a Mostrar | `5` - `10` | Controla cuántos comentarios son visibles inicialmente. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: La sección de comentarios no aparece en las páginas de mis productos después de la instalación.**
R:

1.  **Verifique la Configuración del Módulo:** Vaya a **Módulos > Gestor de Módulos > Comentarios de Google+ > Configurar**. Asegúrese de que "Mostrar Comentarios de Google+ en la Página del Producto" esté configurado en SÍ.
2.  **Verifique la Selección del Hook:** Asegúrese de que "Elegir Hook para Comentarios de Google+" esté configurado en un hook relevante de la página del producto como `displayProductExtraContent`. Si su tema utiliza un hook personalizado para el contenido del producto, es posible que deba seleccionarlo o consultar a su desarrollador de temas.
3.  **Borrar Caché:** Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty"). A veces, la caché de PrestaShop impide que el nuevo contenido del módulo aparezca inmediatamente.
4.  **Compatibilidad del Tema:** Algunos temas altamente personalizados pueden anular los hooks estándar de PrestaShop. Si el problema persiste, póngase en contacto con el desarrollador de su tema o con el soporte de MyPresta.eu.

**P: La sección de comentarios se ve demasiado ancha/estrecha o rompe mi diseño.**
R:

1.  **Ajustar la Configuración de Ancho:** En la configuración del módulo, modifique el ajuste "Ancho del Bloque de Comentarios de Google+ (en píxeles)". Experimente con diferentes valores (por ejemplo, 600, 700, 800) hasta que se ajuste al diseño de su página de producto.
2.  **Verificar el CSS del Tema:** Si ajustar el ancho no ayuda, el CSS de su tema podría estar interfiriendo. Es posible que necesite un webmaster para inspeccionar el elemento y agregar CSS personalizado a su tema para asegurar una visualización adecuada.

**P: ¿Puedo moderar los comentarios antes de que aparezcan?**
R: El módulo Comentarios de Google+ utiliza el propio sistema de comentarios de Google. Las capacidades de moderación se manejan típicamente dentro de la propia plataforma de Google, no directamente dentro de PrestaShop. Deberá consultar las políticas y herramientas de Google para la moderación de comentarios relacionados con widgets incrustados.

**P: Mis clientes tienen problemas para publicar comentarios.**
R:

1.  **Requisito de Cuenta de Google:** Recuerde a los clientes que necesitan haber iniciado sesión en una cuenta de Google para publicar comentarios.
2.  **Problemas del Navegador:** Aconseje a los clientes que prueben con un navegador diferente o que borren la caché y las cookies de su navegador.
3.  **Estado del Servicio de Google:** Ocasionalmente, los servicios de Google pueden experimentar interrupciones temporales. Verifique las páginas de estado de Google si muchos usuarios informan problemas simultáneamente.

**P: ¿Este módulo sigue funcionando desde que Google+ fue cerrado?**
R: Aunque Google+ como red social ha sido desaprobado, Google todavía proporciona widgets de comentarios incrustados que aprovechan las cuentas de Google. Este módulo se integra con esa infraestructura subyacente de comentarios de Google. Puede que no proporcione el "impulso de SEO" directo de los "+1" como lo hizo una vez, pero aún funciona como un sistema de comentarios impulsado por Google.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una visión técnica para desarrolladores y webmasters que trabajan con el módulo Comentarios de Google+.

### 4.1 Visión General de la Arquitectura

El módulo `Comentarios de Google+` es un módulo de PrestaShop sencillo implementado principalmente dentro de su archivo PHP principal (`google-comments.php`). Aprovecha la clase `Module` y la clase `Configuration` de PrestaShop para gestionar la configuración. Su funcionalidad principal implica inyectar un fragmento de JavaScript proporcionado por Google en el front-office, que luego renderiza el widget de comentarios. No hay controladores personalizados, modelos o interacciones AJAX complejas dentro del propio módulo; se basa en gran medida en el script externo de Google para su funcionalidad de front-end.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. La visualización del front-office del módulo se maneja mediante la conexión a los hooks de visualización estándar de PrestaShop y la renderización de una plantilla Smarty que contiene el código de incrustación de comentarios de Google.
-   **Controladores de Administración de Back-Office**: Ninguno. Toda la configuración se maneja a través del método `getContent()` en el archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

-   No hay clases personalizadas ni definiciones de `ObjectModel` presentes en este módulo. Todos los datos se almacenan directamente en la tabla `ps_configuration` de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

-   No se incluyen archivos JavaScript personalizados en este módulo. La funcionalidad del módulo se basa completamente en la biblioteca JavaScript externa de Google que incrusta.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   No se incluyen archivos CSS personalizados en este módulo. El estilo del widget de comentarios de Google es controlado por los propios estilos incrustados de Google. Cualquier estilo personalizado necesitaría apuntar a los elementos/iframe de Google generados a través de anulaciones de tema (lo que puede ser un desafío debido a las restricciones de iframe de dominio cruzado).

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El módulo utiliza una única plantilla Smarty para renderizar el widget de comentarios de Google.

-   **Plantillas de Hook (`views/templates/hook/`)**:
    -   `googlecomments.tpl`: Esta plantilla se renderiza cuando el módulo está enganchado. Contiene la estructura HTML para el widget de comentarios de Google, incluyendo el elemento `<div>` con los atributos `data-href`, `data-width` y `data-num-comments`, y la etiqueta `script` para cargar el SDK de JavaScript de la Plataforma de Google.
        -   **Propósito:** Incrustar el widget de comentarios de Google en el front-office.
        -   **Variables utilizadas:**
            -   `{$link->getModuleLink('googlecomments', 'ajax', array(), true)|escape:'htmlall':'UTF-8'}`: Esto es probablemente un remanente o marcador de posición, ya que el módulo no utiliza un controlador AJAX. El atributo `data-href` para los comentarios de Google típicamente apunta a la URL canónica de la página donde se muestran los comentarios (por ejemplo, la URL de la página del producto).
            -   `{Configuration::get('GOOGLE_COMMENTS_WIDTH')}`: Recupera el ancho configurado para el bloque de comentarios.
            -   `{Configuration::get('GOOGLE_COMMENTS_NUM')}`: Recupera el número configurado de comentarios a mostrar.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:
    El módulo no crea ninguna tabla de base de datos personalizada. Todos sus ajustes de configuración se almacenan en la tabla `ps_configuration`:

    -   `GOOGLE_COMMENTS_ENABLED`: Almacena `1` (habilitado) o `0` (deshabilitado) para mostrar comentarios.
    -   `GOOGLE_COMMENTS_HOOK`: Almacena el nombre del hook seleccionado (por ejemplo, `displayProductExtraContent`).
    -   `GOOGLE_COMMENTS_WIDTH`: Almacena el ancho del bloque de comentarios en píxeles.
    -   `GOOGLE_COMMENTS_NUM`: Almacena el número de comentarios a mostrar.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para registrar activos (aunque este módulo no lo usa para eso, es un hook común). |
| `displayProductExtraContent` | Dentro del área de contenido principal de una página de producto, a menudo en una pestaña o debajo de la descripción. | **Hook principal para mostrar el bloque de comentarios en las páginas de productos.** |
| `displayLeftColumn` | En la barra lateral izquierda de la tienda. | Hook opcional para mostrar el bloque de comentarios (menos común para comentarios completos). |
| `displayRightColumn` | En la barra lateral derecha de la tienda. | Hook opcional para mostrar el bloque de comentarios (menos común para comentarios completos). |
| `displayFooter` | En la sección del pie de página de la tienda. | Hook opcional para mostrar el bloque de comentarios (menos común para comentarios completos). |
| `actionFrontControllerSetMedia` | Antes de que el controlador frontal renderice la página, permitiendo que los módulos añadan JS/CSS. | Se utiliza para añadir el SDK de JavaScript de la Plataforma de Google a la página. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo Comentarios de Google+, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a brindar asistencia y garantizar el buen funcionamiento de sus módulos.

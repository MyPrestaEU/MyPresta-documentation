---
title: "Comentarios DISQUS - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Comentarios DISQUS' de MyPresta.eu."
sidebar:
  label: "Comentarios DISQUS - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo DISQUS comments en MyPresta.eu](https://mypresta.eu/modules/front-office-features/disqus-comments.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/disqus-comments/)
>
> ---


# Comentarios DISQUS

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y para la comunicación con servicios externos como Disqus.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Comentarios DISQUS)

Esta es la pantalla de configuración principal donde configurará cómo se integra Disqus con su tienda.

#### **1. Nombre corto del sitio**

-   **Qué hace este ajuste:** Este es el identificador único de su sitio web de Disqus. Lo obtiene de su cuenta de Disqus cuando registra su sitio web. Le dice a Disqus qué hilos de comentarios pertenecen a su tienda.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se configura correctamente:* Los comentarios de Disqus se cargarán y guardarán correctamente para sus productos.
    -   *Cuando es incorrecto o está vacío:* Disqus no podrá cargar los comentarios, o podría cargar comentarios de un sitio diferente, lo que provocaría errores o la falta de comentarios.
-   **Valor recomendado:** Su nombre corto único de Disqus (por ejemplo, `nombredetutienda`).
-   **Escenario / ejemplo de comerciante:** Si registró su sitio web en Disqus como "Mi Tienda Impresionante", su nombre corto podría ser "mitiendaimpresionante". Introduzca esa cadena exacta aquí.

#### **2. Posición del widget de comentarios**

-   **Qué hace este ajuste:** Esto controla dónde aparece la sección principal de comentarios de Disqus en sus páginas de producto.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en "Sección de pestaña de producto":* Los comentarios aparecerán en una nueva pestaña en la página del producto (por ejemplo, junto a "Descripción" o "Ficha técnica"). Los clientes hacen clic en la pestaña para ver los comentarios.
    -   *Cuando se establece en "Sección de pie de página del producto":* Los comentarios aparecerán en la parte inferior de la página del producto, debajo de la información principal del producto. Los clientes los verán a medida que se desplacen hacia abajo.
-   **Valor recomendado:** "Sección de pestaña de producto" para un diseño de página de producto más limpio, o "Sección de pie de página del producto" si desea que los comentarios sean inmediatamente visibles sin hacer clic en una pestaña.
-   **Escenario / ejemplo de comerciante:** Si sus páginas de producto ya son muy largas, colocar los comentarios en una pestaña mantiene la vista inicial ordenada. Si desea enfatizar los comentarios de los clientes, colocarlos en el pie de página los hace más prominentes.

#### **3. Página de testimonios**

-   **Qué hace este ajuste:** Esto habilita o deshabilita una página dedicada en su tienda que agrega todos los comentarios de Disqus de todos sus productos.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está "Habilitado":* Se creará una nueva página en una URL como `sutienda.com/testimonials` (o similar, dependiendo de sus URLs amigables) mostrando todos los comentarios.
    -   *Cuando está "Deshabilitado":* No estará disponible dicha página.
-   **Valor recomendado:** "Habilitado" para proporcionar un centro central para los comentarios de los clientes.
-   **Escenario / ejemplo de comerciante:** Habilitar esto le permite vincular a una página de "Reseñas de clientes" o "Lo que dicen nuestros clientes" desde su pie de página, mostrando todos los comentarios positivos en un solo lugar.

#### **4. Apariencia del enlace de testimonios**

-   **Qué hace este ajuste:** Si la "Página de testimonios" está habilitada, esto controla dónde aparece un enlace a esa página en el diseño de su tienda.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está "Ocultar":* La página de testimonios existirá, pero el módulo no añadirá ningún enlace automático. Tendría que añadir un enlace manualmente (por ejemplo, en el menú del pie de página de su tema).
    -   *Cuando está "Columna izquierda":* Aparecerá un enlace a la página de testimonios en la columna izquierda de su tienda.
    -   *Cuando está "Columna derecha":* Aparecerá un enlace a la página de testimonios en la columna derecha de su tienda.
-   **Valor recomendado:** "Columna derecha" o "Columna izquierda" para que la página de testimonios sea fácilmente detectable.
-   **Escenario / ejemplo de comerciante:** Si su tienda utiliza una columna izquierda para las categorías, colocar el enlace de testimonios en la columna derecha podría ser más apropiado.

#### **5. Comentarios recientes en la página de inicio**

-   **Qué hace este ajuste:** Esto controla si un bloque que muestra los comentarios más recientes de Disqus aparece en la página de inicio de su tienda.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está "Habilitado":* Se mostrará un bloque con comentarios recientes en su página de inicio.
    -   *Cuando está "Deshabilitado":* No aparecerá ningún bloque de comentarios recientes en la página de inicio.
-   **Valor recomendado:** "Habilitado" para mantener su página de inicio dinámica y resaltar la actividad reciente de los clientes.
-   **Escenario / ejemplo de comerciante:** Mostrar comentarios recientes en la página de inicio puede animar a los visitantes a explorar productos que tienen discusiones activas, lo que podría generar más ventas.

#### **6. Comentarios recientes en la columna derecha**

-   **Qué hace este ajuste:** Esto controla si un bloque que muestra los comentarios más recientes de Disqus aparece en la columna derecha de su tienda.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está "Habilitado":* Se mostrará un bloque con comentarios recientes en la columna derecha en las páginas donde la columna derecha está activa.
    -   *Cuando está "Deshabilitado":* No aparecerá ningún bloque de comentarios recientes en la columna derecha.
-   **Valor recomendado:** "Habilitado" para mantener la participación en todo su sitio.
-   **Escenario / ejemplo de comerciante:** Si su tienda tiene una columna derecha, mostrar comentarios recientes allí puede proporcionar un flujo constante de contenido fresco y fomentar la exploración.

#### **7. Comentarios recientes en la columna izquierda**

-   **Qué hace este ajuste:** Esto controla si un bloque que muestra los comentarios más recientes de Disqus aparece en la columna izquierda de su tienda.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está "Habilitado":* Se mostrará un bloque con comentarios recientes en la columna izquierda en las páginas donde la columna izquierda está activa.
    -   *Cuando está "Deshabilitado":* No aparecerá ningún bloque de comentarios recientes en la columna izquierda.
-   **Valor recomendado:** "Habilitado" para mantener la participación en todo su sitio.
-   **Escenario / ejemplo de comerciante:** Similar a la columna derecha, usar la columna izquierda para comentarios recientes puede ser efectivo si su tema utiliza principalmente la columna izquierda para la navegación u otros bloques.

#### **8. Mostrar Disqus solo para usuarios registrados que compraron el producto**

-   **Qué hace este ajuste:** Este es un ajuste potente para restringir quién puede ver e interactuar con los comentarios de Disqus en las páginas de producto.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está "Habilitado":* Solo los clientes que han iniciado sesión en su cuenta Y han comprado previamente el producto específico verán la sección de comentarios de Disqus. Todos los demás visitantes no la verán.
    -   *Cuando está "Deshabilitado":* Todos los visitantes (registrados o invitados, compradores o no) verán la sección de comentarios de Disqus.
-   **Valor recomendado:** "Deshabilitado" para una máxima participación y beneficios de SEO. "Habilitado" si desea asegurarse de que solo los compradores verificados puedan comentar, lo que puede aumentar la credibilidad de las reseñas pero reducir el volumen de comentarios.
-   **Escenario / ejemplo de comerciante:** Si tiene problemas con el spam o los comentarios irrelevantes, habilitar esto puede filtrar a los no compradores. Sin embargo, si su objetivo es una discusión amplia y SEO, manténgalo deshabilitado.

#### **9. ¿Cuántos comentarios recientes mostrar?**

-   **Qué hace este ajuste:** Esto determina el número de comentarios recientes que se muestran en los bloques de "Comentarios recientes" (en la página de inicio, columnas izquierda o derecha).
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en un número (por ejemplo, 5):* Los bloques mostrarán esa cantidad de los comentarios más recientes.
    -   *Cuando se establece en 0 o vacío:* No se mostrarán comentarios recientes en los bloques, incluso si los bloques están habilitados.
-   **Valor recomendado:** De 3 a 5 comentarios para un bloque compacto, o hasta 10 para una visualización más prominente.
-   **Escenario / ejemplo de comerciante:** Mostrar 5 comentarios proporciona un buen equilibrio entre mostrar actividad y no hacer el bloque demasiado largo.

#### **Tabla de referencia rápida de configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Nombre corto del sitio | Su nombre corto de Disqus | Identificador único para su cuenta de Disqus; esencial para que los comentarios se carguen. |
| Configuración del módulo | Posición del widget de comentarios | Sección de pestaña de producto | Dónde aparece la sección principal de comentarios en las páginas de producto (pestaña o pie de página). |
| Configuración del módulo | Página de testimonios | Habilitado | Crea una página dedicada que agrega todos los comentarios. |
| Configuración del módulo | Apariencia del enlace de testimonios | Columna derecha | Dónde aparece un enlace a la página de testimonios (si está habilitado). |
| Configuración del módulo | Comentarios recientes en la página de inicio | Habilitado | Muestra un bloque de comentarios recientes en la página de inicio. |
| Configuración del módulo | Comentarios recientes en la columna derecha | Habilitado | Muestra un bloque de comentarios recientes en la columna derecha. |
| Configuración del módulo | Comentarios recientes en la columna izquierda | Habilitado | Muestra un bloque de comentarios recientes en la columna izquierda. |
| Configuración del módulo | Mostrar Disqus solo para usuarios registrados que compraron el producto | Deshabilitado | Restringe la visibilidad/interacción de los comentarios a los compradores verificados. |
| Configuración del módulo | ¿Cuántos comentarios recientes mostrar? | 5 | Número de comentarios a mostrar en los bloques de comentarios recientes. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis comentarios de Disqus no aparecen en las páginas de producto. ¿Qué debo hacer?**

-   **R:** Primero, verifique su "Nombre corto del sitio" en la configuración del módulo. Debe coincidir exactamente con el nombre corto de su cuenta de Disqus. Además, asegúrese de haber establecido la "Posición del widget de comentarios" en "Sección de pestaña de producto" o "Sección de pie de página del producto". Finalmente, borre la caché de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché) y la caché de su navegador.

**P2: Los bloques de "Comentarios recientes" no aparecen en mis columnas/página de inicio.**

-   **R:** Verifique que haya habilitado "Comentarios recientes en la página de inicio", "Comentarios recientes en la columna derecha" o "Comentarios recientes en la columna izquierda" en la configuración del módulo. Además, asegúrese de que "¿Cuántos comentarios recientes mostrar?" esté configurado en un número mayor que 0. Si su tema no muestra las columnas izquierda/derecha en ciertas páginas, los bloques no aparecerán allí. Borre la caché después de realizar cambios.

**P3: Habilité la "Página de testimonios", pero no encuentro un enlace a ella.**

-   **R:** Si configuró "Apariencia del enlace de testimonios" en "Ocultar", el módulo no agregará automáticamente un enlace. Deberá agregar un enlace manualmente a la página (por ejemplo, en el menú del pie de página de su tema). La URL de la página de testimonios suele ser `sutienda.com/module/disqus/testimonials` (o una versión de URL amigable si está habilitada). Si eligió "Columna izquierda" o "Columna derecha", asegúrese de que esas columnas estén activas en las páginas que está viendo.

**P4: Solo algunos usuarios pueden ver los comentarios, o no puedo verlos como invitado.**

-   **R:** Verifique la configuración "Mostrar Disqus solo para usuarios registrados que compraron el producto". Si está habilitada, solo los clientes que hayan iniciado sesión y hayan comprado el producto específico verán los comentarios. Deshabilite esta configuración si desea que todos los visitantes vean e interactúen con los comentarios.

**P5: El estilo de mi tema personalizado está chocando con los comentarios de Disqus.**

-   **R:** El widget de Disqus en sí es en gran parte autónomo y está diseñado por Disqus. Sin embargo, el contenedor o la pestaña que contiene el widget podría verse afectado por el CSS de su tema. Es posible que necesite un desarrollador web para inspeccionar los elementos utilizando las herramientas de desarrollo del navegador y agregar CSS personalizado a su tema para ajustar el espaciado, las fuentes o los colores alrededor del widget de Disqus.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada del módulo de comentarios DISQUS para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura

El módulo de comentarios DISQUS sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente los hooks para la visualización en el front-office y un método `getContent()` para la configuración en el back-office. Integra el Código de incrustación universal de Disqus dinámicamente. El módulo utiliza un controlador frontal personalizado para la página de testimonios y otro para las llamadas AJAX (aunque actualmente, el controlador AJAX parece ser un marcador de posición o no se utiliza mucho para la funcionalidad principal de Disqus). La configuración se almacena en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

-   **Controladores del Front-Office**:

    -   `controllers/front/index.php`
        -   **Nombre de la clase:** `DisqusIndexModuleFrontController` (extiende `ModuleFrontController`)
        -   **Responsabilidad:** Este controlador es probablemente un valor predeterminado o de reserva para el enrutamiento del front-office del módulo. En el contexto de Disqus, podría usarse para acciones generales de front-end relacionadas con el módulo, aunque la incrustación principal de Disqus generalmente se maneja a través de hooks. Podría servir como base para futuras funcionalidades AJAX o simples visualizaciones de páginas si fuera necesario.
    -   `controllers/front/testimonials.php`
        -   **Nombre de la clase:** `DisqusTestimonialsModuleFrontController` (extiende `ModuleFrontController`)
        -   **Responsabilidad:** Este controlador es responsable de renderizar la página dedicada de "Testimonios". Recupera la configuración necesaria (por ejemplo, `disqus_shortname`) y la pasa a la plantilla `testimonials.tpl`, que luego incrusta el Código de incrustación universal de Disqus configurado para mostrar todos los comentarios para el nombre corto dado. Este controlador maneja la ruta `module/disqus/testimonials`.
-   **Controladores de administración del Back-Office**: Ninguno definido explícitamente en el inventario proporcionado. Toda la configuración se maneja a través del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

No hay clases personalizadas ni definiciones de `ObjectModel` presentes en el directorio `classes/` según el inventario. El módulo se basa en la clase `Configuration` de PrestaShop para almacenar sus ajustes.

### 4.4 Activos de JavaScript (`views/js/`)

No hay archivos JavaScript personalizados presentes en el directorio `views/js/` según el inventario. El módulo incrusta directamente el Código de incrustación universal de Disqus (generalmente una etiqueta `<script>` con `DISQUS.init()` o lógica similar) en las plantillas Smarty relevantes. Esto significa que el propio JavaScript de Disqus se carga directamente desde `disqus.com`.

### 4.5 Hojas de estilo CSS (`views/css/`)

No hay archivos CSS personalizados presentes en el directorio `views/css/` según el inventario. El estilo del widget de comentarios de Disqus en sí es manejado por Disqus. Cualquier estilo específico de integración (por ejemplo, para los bloques de comentarios recientes o el diseño de la página de testimonios) sería mínimo, heredado del tema o en línea dentro de las plantillas.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   `last-comments.tpl`: Esta plantilla se utiliza para mostrar el bloque de "Comentarios recientes". Itera a través de una lista de comentarios recientes (obtenidos de Disqus a través de JavaScript o una llamada del lado del servidor si se implementa) y los muestra. Esta plantilla probablemente se renderiza en los hooks `displayHome`, `displayLeftColumn` y `displayRightColumn`.
    -   `leftColumn.tpl`: Esta plantilla es probablemente un envoltorio o contenido específico para el hook `displayLeftColumn`, que potencialmente incluye `last-comments.tpl` o el enlace de testimonios.
    -   `productfooter.tpl`: Esta plantilla se renderiza en el hook `displayProductFooter`. Contiene el Código de incrustación universal de Disqus para los comentarios del producto cuando la "Posición del widget de comentarios" se establece en "Sección de pie de página del producto".
    -   `rightColumn.tpl`: Similar a `leftColumn.tpl`, esto es para el hook `displayRightColumn`, que potencialmente incluye `last-comments.tpl` o el enlace de testimonios.
-   **Plantillas de administración (`views/templates/admin/`)**: Ninguna.
-   **Plantillas del Front-Office (`views/templates/front/`)**:

    -   `testimonials.tpl`: Esta plantilla es renderizada por `DisqusTestimonialsModuleFrontController`. Contiene el Código de incrustación universal de Disqus configurado para mostrar todos los comentarios para el nombre corto del sitio, creando efectivamente la página de testimonios agregados.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**: El módulo no crea ninguna tabla SQL personalizada. Todos los ajustes de configuración se almacenan en la tabla `ps_configuration` utilizando claves como `DISQUS_SHORTNAME`, `DISQUS_HOOK`, `DISQUS_TEST`, `DISQUS_TEST_WHERE`, `DISQUS_RIGHTRECENT`, `DISQUS_LEFTRECENT`, `DISQUS_FORLOGGED`, `DISQUS_LASTCOMMENTS`, `DISQUS_LASTC_NB`.
-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Potencialmente utilizado para incluir variables de configuración global de Disqus o CSS/JS si es necesario, aunque la incrustación principal está en hooks de contenido específicos. |
| `displayProductExtraContent` | Dentro de la página del producto, a menudo utilizado para pestañas o bloques de contenido adicionales. | Se utiliza para mostrar la sección de comentarios de Disqus dentro de una pestaña de producto cuando la "Posición del widget de comentarios" se establece en "Sección de pestaña de producto". |
| `displayRightColumn` | En la columna derecha de las páginas. | Se utiliza para mostrar el bloque de "Comentarios recientes" o el "Enlace de testimonios" si está configurado. |
| `displayProductFooter` | En la parte inferior del contenido de la página del producto. | Se utiliza para mostrar la sección de comentarios de Disqus cuando la "Posición del widget de comentarios" se establece en "Sección de pie de página del producto". |
| `displayLeftColumn` | En la columna izquierda de las páginas. | Se utiliza para mostrar el bloque de "Comentarios recientes" o el "Enlace de testimonios" si está configurado. |
| `displayHome` | En la página de inicio. | Se utiliza para mostrar el bloque de "Comentarios recientes" en la página de inicio. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Este hook se enumera en el método `install()` del módulo, lo que sugiere una posible característica futura o una verificación de productos comprados. Es probable que se utilice junto con la configuración "Mostrar Disqus solo para usuarios registrados que compraron el producto" para verificar el historial de compras. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con el módulo de comentarios DISQUS.

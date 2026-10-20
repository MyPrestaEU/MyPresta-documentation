---
title: "Facebook Like Box Free - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo gratuito de PrestaShop Facebook Like Box Free de MyPresta.eu."
sidebar:
  label: "Facebook Like Box Free - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook Like Box Free en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-box-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-like-box-free/)
>
> ---


# Facebook Like Box Free

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser requeridas por PrestaShop y son suficientes para este módulo. No hay requisitos de alojamiento especiales más allá de una configuración estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada grupo de ajustes por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo Facebook Like Box Free. Aquí encontrará todos los ajustes para controlar su apariencia y comportamiento.

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo de comerciante |
| --- | --- | --- | --- | --- |
| **Activado** / **Desactivado** | Controla si la Facebook Like Box está activa y visible en su tienda. | *Cuando está Activado:* La Like Box aparecerá en su tienda en la posición elegida. *Cuando está Desactivado:* La Like Box estará oculta de su tienda. | **Activado** | Desea comenzar a promocionar su página de Facebook. |
| **Posición** | Determina dónde se mostrará la Like Box en su tienda. | *Cuando se establece en Columna izquierda:* La Like Box aparece en la barra lateral izquierda. *Cuando se establece en Columna derecha:* La Like Box aparece en la barra lateral derecha. *Cuando se establece en Página de inicio:* La Like Box aparece en el área de contenido principal de su página de inicio. *Cuando se establece en Pie de página:* La Like Box aparece en la parte inferior de cada página. | **Columna derecha** o **Página de inicio** | Desea que la Like Box sea prominentemente visible sin interferir con la visualización del producto. |
| **URL de la página de Facebook** | Este es el enlace directo a su página oficial de Facebook. | *Cuando se establece en la URL de su página (por ejemplo, `https://www.facebook.com/MyPrestaEU`):* La Like Box mostrará contenido y un botón de "Me gusta" para *su* página de Facebook específica. *Cuando se deja vacío o es incorrecto:* La Like Box puede no mostrarse correctamente o mostrará un error. | La URL real de su página de Facebook | Desea conectar a los visitantes de su tienda con la presencia de su marca en Facebook. |
| **Ancho** | Establece el ancho de la Like Box en píxeles. | *Cuando se establece en un valor de píxel específico (por ejemplo, `280`):* La Like Box tendrá exactamente ese ancho. *Cuando se deja vacío:* El módulo intentará ajustar automáticamente el ancho, pero a menudo es mejor establecer un valor específico para un diseño consistente. | `280` (o ajuste para adaptarse a su columna/diseño) | Su columna derecha tiene 300px de ancho, por lo que establece el ancho de la Like Box en 280px para que encaje bien con algo de relleno. |
| **Altura** | Establece la altura de la Like Box en píxeles. | *Cuando se establece en un valor de píxel específico (por ejemplo, `500`):* La Like Box tendrá exactamente esa altura. *Cuando se deja vacío:* El módulo intentará ajustar automáticamente la altura. | `500` (o ajuste según el contenido que desee mostrar) | Desea mostrar algunas publicaciones recientes, por lo que establece la altura en 500px para permitir suficiente espacio. |
| **Ocultar portada** | Controla si la foto de portada grande de su página de Facebook se muestra en la parte superior de la Like Box. | *Cuando está activado:* La foto de portada estará oculta, haciendo que la Like Box sea más compacta. *Cuando está desactivado:* La foto de portada será visible. | **Activado** (para una apariencia más limpia) | Prefiere un diseño minimalista y desea que la Like Box ocupe menos espacio vertical. |
| **Fotos de perfil** (Mostrar Facepile) | Determina si las fotos de perfil de las personas a las que les gusta su página se muestran debajo del botón "Me gusta". | *Cuando está activado:* Aparecerá una fila de pequeñas fotos de perfil, mostrando prueba social. *Cuando está desactivado:* Estas fotos de perfil no se mostrarán. | **Activado** (para prueba social) | Desea mostrar a los visitantes que a muchos otros ya les gusta su página, animándolos a hacer lo mismo. |
| **Mostrar publicaciones** (Mostrar Stream) | Controla si las publicaciones recientes de su página de Facebook se muestran dentro de la Like Box. | *Cuando está activado:* Sus últimas publicaciones de Facebook serán visibles, haciendo que la Like Box sea más dinámica. *Cuando está desactivado:* Solo se mostrará el botón "Me gusta" y el facepile (si está activado). | **Activado** | Publica activamente en Facebook y desea mostrar su contenido más reciente directamente en su tienda. |
| **Botón de llamada a la acción** (Ocultar CTA) | Controla si el botón de "Llamada a la acción" (por ejemplo, "Enviar mensaje", "Comprar ahora") de su página de Facebook está oculto. | *Cuando está activado:* El botón CTA estará oculto. *Cuando está desactivado:* El botón CTA será visible si está configurado en su página de Facebook. | **Activado** (a menudo para una apariencia más limpia) | Desea centrarse únicamente en obtener un "Me gusta" y no desea que otro botón distraiga a los visitantes. |
| **Encabezado pequeño** | Hace que el encabezado de la Like Box sea más pequeño. | *Cuando está activado:* El encabezado (que contiene el nombre de su página y el botón "Me gusta") será más compacto. *Cuando está desactivado:* El encabezado tendrá un tamaño estándar. | **Activado** (para un diseño más compacto) | Desea que la Like Box sea menos intrusiva y se integre más perfectamente en el diseño de su tienda. |
| **Biblioteca de Facebook** (Incluir App) | Este ajuste controla si se carga el SDK de JavaScript de Facebook necesario. | *Cuando está activado:* El módulo cargará el SDK de Facebook, que es esencial para que la Like Box funcione correctamente. *Cuando está desactivado:* Es probable que la Like Box no se muestre o no funcione correctamente. | **Activado** | Esto es crucial para que la Like Box funcione. |

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Activado/Desactivado | Activado | Activa/Desactiva la Like Box en su tienda. |
| Configuración del módulo | Posición | Columna derecha / Página de inicio | Determina dónde aparece la Like Box (Columna izquierda/derecha, Página de inicio, Pie de página). |
| Configuración del módulo | URL de la página de Facebook | La URL de su página de Facebook | Vincula la Like Box a su página de Facebook específica. |
| Configuración del módulo | Ancho | 280 | Establece el ancho de la Like Box en píxeles. |
| Configuración del módulo | Altura | 500 | Establece la altura de la Like Box en píxeles. |
| Configuración del módulo | Ocultar portada | Activado | Oculta la foto de portada grande para una apariencia más compacta. |
| Configuración del módulo | Fotos de perfil (Mostrar Facepile) | Activado | Muestra fotos de perfil de personas a las que les gusta su página (prueba social). |
| Configuración del módulo | Mostrar publicaciones (Mostrar Stream) | Activado | Muestra publicaciones recientes de su página de Facebook. |
| Configuración del módulo | Botón de llamada a la acción (Ocultar CTA) | Activado | Oculta el botón de llamada a la acción de la página de Facebook. |
| Configuración del módulo | Encabezado pequeño | Activado | Hace que el encabezado de la Like Box sea más compacto. |
| Configuración del módulo | Biblioteca de Facebook (Incluir App) | Activado | Carga el SDK de JavaScript de Facebook necesario para la funcionalidad. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: La Facebook Like Box no aparece en mi tienda. ¿Qué debo hacer?**
R:

1.  **Verificar el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Facebook Like Box Free" esté instalado y activado.
2.  **Verificar la configuración:** Vaya a la página de configuración del módulo.
    - Asegúrese de que "Activado" esté configurado en SÍ.
    - Verifique que la "URL de la página de Facebook" sea correcta y completa (por ejemplo, `https://www.facebook.com/MyPrestaEU`).
    - Asegúrese de que "Biblioteca de Facebook" (Incluir App) esté activada.
3.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los archivos de caché antiguos impiden que aparezcan nuevos módulos.
4.  **Verificar la posición del hook:** Asegúrese de que la "Posición" que seleccionó (por ejemplo, Columna derecha, Página de inicio) esté realmente activa en su tema. Algunos temas pueden no mostrar ciertas columnas. Puede verificar **Diseño > Posiciones** para ver si el módulo está enganchado correctamente.

**P: La Like Box se ve demasiado ancha/estrecha o demasiado alta/corta.**
R: Ajuste los ajustes de "Ancho" y "Altura" en la página de configuración del módulo. Experimente con diferentes valores de píxeles hasta que se ajuste perfectamente al diseño de su tema. Recuerde borrar la caché de su navegador después de realizar cambios para ver la actualización.

**P: Cambié la configuración, pero no pasó nada en mi tienda.**
R: Después de guardar los cambios en la configuración del módulo, siempre borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**) y luego borre la caché de su navegador (Ctrl+F5 o Cmd+R) para asegurarse de que está viendo la última versión de su tienda.

**P: La Like Box muestra un mensaje de error o no carga contenido.**
R:

1.  **URL incorrecta:** La razón más común es una "URL de la página de Facebook" incorrecta. Verifíquela dos veces para detectar errores tipográficos.
2.  **Problemas con la API de Facebook:** Ocasionalmente, puede haber problemas temporales con la API de Facebook. Espere un poco y verifique de nuevo.
3.  **Conflictos de tema:** Rara vez, el JavaScript o CSS de su tema podría entrar en conflicto. Si los pasos anteriores no funcionan, intente cambiar temporalmente al tema predeterminado de PrestaShop para descartar un conflicto de tema.

**P: ¿Puedo traducir el texto "Me gusta la página" a otros idiomas?**
R: El texto dentro de la propia Facebook Like Box (como "Me gusta la página" o el contenido de la publicación) está controlado por Facebook y se adaptará automáticamente a la configuración de idioma de Facebook del usuario. Los ajustes del back-office del módulo son traducibles a través de **Internacional > Traducciones** en PrestaShop.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica para desarrolladores y webmasters que trabajan con el módulo Facebook Like Box Free.

### 4.1 Descripción general de la arquitectura

El módulo `Facebook Like Box Free` es un módulo de PrestaShop sencillo diseñado principalmente para incrustar el complemento de página de Facebook (anteriormente Like Box) utilizando el SDK de JavaScript oficial de Facebook. Sigue una estructura básica de módulo de PrestaShop, aprovechando la clase `Module` para la instalación, desinstalación y configuración. Su funcionalidad principal gira en torno a la visualización del widget de Facebook a través de una plantilla Smarty enganchada en varias posiciones del front-office. No hay tablas de base de datos personalizadas ni ObjectModels complejos involucrados; toda la configuración se almacena en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador de Front-Office o Back-Office Admin personalizado. Toda la lógica está encapsulada dentro del archivo principal del módulo (`likeboxfree.php`).

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** define ninguna clase u ObjectModels personalizados en el directorio `classes/`. Toda la lógica del módulo reside en el archivo principal `likeboxfree.php`.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo **no** incluye ningún archivo JavaScript personalizado en `views/js/`.
El SDK de JavaScript de Facebook se carga dinámicamente mediante la plantilla del módulo si la configuración `lbf_includeapp` está habilitada. Esto lo maneja el propio script de Facebook, no un script de módulo personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`likeboxfree/css.css`**
  - **Alcance:** Estilo del cliente del front-office.
  - **Componentes principales de la interfaz de usuario y contenedores que estiliza:** Este archivo proporciona un estilo básico para el contenedor alrededor de la Facebook Like Box para asegurar que se integre limpiamente en el diseño de PrestaShop, particularmente para los hooks de columna. Puede contener reglas para relleno, márgenes o capacidad de respuesta básica.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:** Los desarrolladores pueden inspeccionar el HTML generado para encontrar el elemento contenedor (por ejemplo, un `div` con un ID o clase específica generada por el módulo) y anular sus estilos en el `custom.css` o `theme.css` de su tema.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - **`likeboxfree/rightcolumn.tpl`**
    - **Enganchado en:** `displayHome`, `displayFooter`, `displayRightColumn`, `displayLeftColumn` (dependiendo de la configuración `likeboxfree_position`).
    - **Salida del bloque visual:** Esta plantilla es responsable de renderizar la estructura HTML que incrusta el complemento de página de Facebook. Genera dinámicamente el elemento `div` con la clase `fb-page` y los atributos de datos (`data-href`, `data-width`, `data-height`, etc.) basados en la configuración del módulo. También incluye el fragmento de JavaScript necesario para inicializar el SDK de Facebook y analizar el complemento.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:
  Este módulo no crea ninguna tabla de base de datos personalizada. Todos los ajustes de configuración se almacenan en la tabla `ps_configuration` utilizando claves con el prefijo `likeboxfree_` o `lbf_`.

  - Entradas de `ps_configuration`:
    - `likeboxfree_position`: Almacena la posición de hook elegida (por ejemplo, `displayRightColumn`).
    - `lbf_width`: Ancho de la Like Box.
    - `lbf_height`: Altura de la Like Box.
    - `lbf_hide_cover`: Booleano (0/1) para ocultar la foto de portada.
    - `lbf_show_facepile`: Booleano (0/1) para mostrar fotos de perfil.
    - `lbf_show_posts`: Booleano (0/1) para mostrar publicaciones.
    - `lbf_hide_cta`: Booleano (0/1) para ocultar el botón de llamada a la acción.
    - `lbf_small_header`: Booleano (0/1) para un encabezado pequeño.
    - `lbf_url`: La URL de la página de Facebook.
    - `lbf_includeapp`: Booleano (0/1) para incluir el SDK de Facebook.
    - (También pueden existir claves heredadas/no utilizadas de versiones anteriores, pero las anteriores están activas).
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHome` | Renderiza contenido en la página de inicio. | Muestra la Facebook Like Box en el área de contenido principal de la página de inicio si está configurada. |
| `displayFooter` | Renderiza contenido en el pie de página de la tienda. | Muestra la Facebook Like Box en la parte inferior de cada página si está configurada. |
| `displayRightColumn` | Renderiza contenido en la barra lateral derecha. | Muestra la Facebook Like Box en la columna derecha de las páginas si está configurada. |
| `displayLeftColumn` | Renderiza contenido en la barra lateral izquierda. | Muestra la Facebook Like Box en la columna izquierda de las páginas si está configurada. |

Los métodos `hookDisplay*` del módulo verifican el valor de configuración `likeboxfree_position` y solo renderizan la plantilla `rightcolumn.tpl` si el hook actual coincide con la posición configurada.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Facebook Like Box Free", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.

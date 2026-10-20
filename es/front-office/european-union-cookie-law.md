---
title: "Ley de Cookies de la Unión Europea - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Ley de Cookies de la Unión Europea de MyPresta.eu."
sidebar:
  label: "Ley de Cookies de la Unión Europea - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo European Union Cookie Law en MyPresta.eu](https://mypresta.eu/modules/front-office-features/european-union-cookie-law.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/european-union-cookie-law/)
>
> ---


# Ley de Cookies de la Unión Europea

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido Completo de Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo Ley de Cookies de la Unión Europea. Aquí encontrarás todos los ajustes para personalizar tu notificación de cookies.

#### **Habilitar / Deshabilitar Módulo**

- **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar la notificación de cookies en toda tu tienda.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* La barra de notificación de cookies aparecerá en tu front office según tus otras configuraciones.
  - *Cuando está deshabilitado:* La barra de notificación de cookies no se mostrará a ningún visitante.
- **Valor recomendado:** SÍ (a menos que tengas otro método para el cumplimiento de cookies).
- **Escenario / ejemplo de comerciante:** Acabas de instalar el módulo y quieres activar el aviso de cookies. Configúralo en "SÍ". Si necesitas ocultarlo temporalmente para mantenimiento o pruebas, puedes configurarlo en "NO".

#### **Texto de la Cookie**

- **Qué hace este ajuste:** Este es el mensaje real que se mostrará a tus clientes con respecto al uso de cookies. Admite varios idiomas, lo que te permite proporcionar un mensaje localizado para cada idioma habilitado en tu tienda.
- **Efecto de cambiar este ajuste:** El texto que introduzcas aquí se mostrará en la barra de notificación de cookies. Puedes usar el editor de texto enriquecido para formatear el texto, añadir enlaces (por ejemplo, a tu página de política de privacidad completa) y enfatizar información importante.
- **Valor recomendado:** Un mensaje claro y conciso que informe a los usuarios sobre las cookies e idealmente incluya un enlace a tu política de privacidad completa o página de política de cookies.
- **Escenario / ejemplo de comerciante:** Podrías escribir: "Este sitio web utiliza cookies para asegurar que obtengas la mejor experiencia en nuestro sitio web. [Enlace a la Política de Privacidad]". Asegúrate de traducir esto a todos los idiomas activos de tu tienda.

#### **Texto del Botón**

- **Qué hace este ajuste:** Esto define el texto que se muestra en el botón que los clientes hacen clic para reconocer o aceptar la política de cookies. Al igual que el texto de la cookie, admite varios idiomas.
- **Efecto de cambiar este ajuste:** El botón mostrará el texto que especifiques. Al hacer clic en este botón, se descartará la notificación de cookies para el usuario.
- **Valor recomendado:** "Entiendo", "Aceptar", "De acuerdo", "Continuar" o "OK".
- **Escenario / ejemplo de comerciante:** Para dejar claro que los usuarios están reconociendo la política, podrías configurarlo como "Entiendo y acepto".

#### **Posición**

- **Qué hace este ajuste:** Determina dónde aparece la barra de notificación de cookies en tu sitio web.
- **Efecto de cambiar este ajuste:**
  - *Superior:* La barra aparecerá fija en la parte superior de la ventana del navegador.
  - *Inferior:* La barra aparecerá fija en la parte inferior de la ventana del navegador.
- **Valor recomendado:** Inferior (a menudo menos intrusivo que la superior, que a veces puede interferir con los elementos del encabezado).
- **Escenario / ejemplo de comerciante:** Quieres que el aviso de cookies sea visible pero que no obstruya tu navegación principal o tu logotipo. Elegir "Inferior" suele ser un buen compromiso.

#### **Color de Fondo**

- **Qué hace este ajuste:** Te permite elegir el color de fondo de la barra de notificación de cookies. Esto ayuda a integrar visualmente la barra con el diseño de tu tienda.
- **Efecto de cambiar este ajuste:** El fondo de la barra de cookies cambiará al color seleccionado. Normalmente se proporciona una herramienta de selección de color para facilitar la elección.
- **Valor recomendado:** Un color que contraste bien con el color de tu texto y complemente la marca de tu tienda.
- **Escenario / ejemplo de comerciante:** Tu tienda usa mucho azul. Podrías elegir un azul claro o un gris sutil para el fondo para que coincida con tu tema.

#### **Color del Texto**

- **Qué hace este ajuste:** Te permite elegir el color del texto dentro de la barra de notificación de cookies.
- **Efecto de cambiar este ajuste:** El texto de la barra de cookies cambiará al color seleccionado.
- **Valor recomendado:** Un color que proporcione un buen contraste con el color de fondo elegido para facilitar la lectura.
- **Escenario / ejemplo de comerciante:** Si tu color de fondo es oscuro, elige un color de texto claro (por ejemplo, blanco, gris claro). Si tu fondo es claro, elige un color de texto oscuro (por ejemplo, negro, gris oscuro).

#### **Color del Enlace**

- **Qué hace este ajuste:** Te permite elegir el color de cualquier enlace incluido en tu "Texto de la Cookie" (por ejemplo, un enlace a tu política de privacidad).
- **Efecto de cambiar este ajuste:** Todas las etiquetas `<a>` dentro del texto de la barra de cookies se mostrarán en este color.
- **Valor recomendado:** Un color que destaque del color del texto principal pero que aún se ajuste a tu marca.
- **Escenario / ejemplo de comerciante:** Quieres que el enlace a tu política de privacidad sea fácilmente visible. Podrías elegir el color de acento de tu marca para el enlace.

#### **Color de Fondo del Botón**

- **Qué hace este ajuste:** Establece el color de fondo del botón "Texto del Botón".
- **Efecto de cambiar este ajuste:** El botón tendrá el color de fondo seleccionado.
- **Valor recomendado:** Un color que haga que el botón destaque y fomente los clics, a menudo coincidiendo con el color del botón de llamada a la acción principal de tu tienda.
- **Escenario / ejemplo de comerciante:** Los botones "Añadir al carrito" de tu tienda son verdes. Podrías elegir el verde para el fondo del botón de cookies para mantener la coherencia.

#### **Color del Texto del Botón**

- **Qué hace este ajuste:** Establece el color del texto en el botón "Texto del Botón".
- **Efecto de cambiar este ajuste:** El texto del botón se mostrará en este color.
- **Valor recomendado:** Un color que proporcione un buen contraste con el color de fondo del botón para facilitar la lectura.
- **Escenario / ejemplo de comerciante:** Si el fondo de tu botón es verde oscuro, elige blanco o un color muy claro para el texto del botón.

#### **Expiración de la Cookie (en días)**

- **Qué hace este ajuste:** Determina cuánto tiempo permanece oculta la notificación de cookies después de que un usuario hace clic en el botón "Entiendo". Después de este período, la notificación volverá a aparecer para el usuario.
- **Efecto de cambiar este ajuste:**
  - *Configurado en 30:* La notificación se ocultará durante 30 días para ese usuario específico.
  - *Configurado en 0:* La notificación podría reaparecer en cada visita o sesión, lo cual generalmente no se recomienda ya que puede ser molesto.
- **Valor recomendado:** 30 a 365 días. Una práctica común es 90 o 180 días.
- **Escenario / ejemplo de comerciante:** Para evitar molestar repetidamente a los clientes que regresan, configuras esto en "180" días. Esto significa que un cliente que acepta la política no volverá a ver la barra durante seis meses.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | **Habilitar / Deshabilitar Módulo** | SÍ | Interruptor principal para la visibilidad de la barra de cookies. |
| Configuración del Módulo | **Texto de la Cookie** | Personalizable | El mensaje principal sobre el uso de cookies, admite texto enriquecido y varios idiomas. |
| Configuración del Módulo | **Texto del Botón** | Personalizable | Texto en el botón para descartar el aviso, varios idiomas. |
| Configuración del Módulo | **Posición** | Inferior | Dónde aparece la barra (Superior o Inferior de la pantalla). |
| Configuración del Módulo | **Color de Fondo** | Personalizable | Color de fondo de la barra de cookies. |
| Configuración del Módulo | **Color del Texto** | Personalizable | Color del texto principal en la barra de cookies. |
| Configuración del Módulo | **Color del Enlace** | Personalizable | Color de cualquier enlace dentro del texto de la cookie. |
| Configuración del Módulo | **Color de Fondo del Botón** | Personalizable | Color de fondo del botón de descarte. |
| Configuración del Módulo | **Color del Texto del Botón** | Personalizable | Color del texto en el botón de descarte. |
| Configuración del Módulo | **Expiración de la Cookie (en días)** | 180-365 días | Cuánto tiempo permanece oculto el aviso después de la aceptación del usuario. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: La barra de cookies no aparece en mi tienda.**
R1:

- **Verifica "Habilitar / Deshabilitar Módulo":** Asegúrate de que este ajuste esté configurado en "SÍ" en la configuración del módulo.
- **Borrar Caché:** Ve a **Parámetros Avanzados > Rendimiento** y haz clic en "Borrar caché" en la parte superior derecha. A veces, el contenido antiguo en caché impide que aparezcan los nuevos cambios del módulo.
- **Verifica Conflictos:** Deshabilita temporalmente otros módulos instalados recientemente para ver si hay un conflicto.
- **Caché del Navegador:** Intenta borrar la caché de tu navegador o abrir tu tienda en una ventana de navegación de incógnito/privada.

**P2: He actualizado el texto, pero no cambia en el front office.**
R2:

- **Guardar Cambios:** Asegúrate de haber hecho clic en el botón "Guardar" después de realizar cambios en la configuración del módulo.
- **Borrar Caché de PrestaShop:** Como se mencionó anteriormente, a menudo es necesario borrar la caché de Smarty (en **Parámetros Avanzados > Rendimiento**) para que los cambios de plantilla y texto surtan efecto.
- **Verificar Idioma:** Asegúrate de que estás editando el texto para el idioma correcto si tu tienda es multilingüe.

**P3: La barra de cookies se ve extraña o no encaja con mi tema.**
R3:

- **Ajustar Colores:** Utiliza los ajustes "Color de Fondo", "Color del Texto", "Color del Enlace", "Color de Fondo del Botón" y "Color del Texto del Botón" para que coincidan con la paleta de tu tema.
- **Conflictos de Tema:** Algunos temas personalizados pueden tener estilos CSS conflictivos. Si ajustar los colores no ayuda, es posible que necesites un desarrollador web para inspeccionar el CSS y realizar pequeños ajustes.

**P4: ¿Cómo añado un enlace a mi Política de Privacidad en el texto de la cookie?**
R4:

- En el campo "Texto de la Cookie", utiliza el editor de texto enriquecido. Escribe el texto que quieres que sea un enlace (por ejemplo, "Política de Privacidad"), selecciónalo y luego haz clic en el icono "Enlace" en la barra de herramientas del editor. Introduce la URL de tu página de Política de Privacidad.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica detallada para desarrolladores, webmasters y agencias que trabajan con el módulo Ley de Cookies de la Unión Europea.

### 4.1 Resumen de la Arquitectura

El módulo `uecookie` es un módulo de PrestaShop sencillo diseñado principalmente para inyectar una plantilla de front-office en un hook de visualización, controlado por un método de configuración `getContent()` estándar. Aprovecha la clase `Module` de PrestaShop para la instalación, desinstalación y configuración, y utiliza plantillas Smarty para renderizar la notificación de cookies. La lógica del lado del cliente para descartar la barra de cookies se maneja a través de JavaScript.

### 4.2 Controladores (`controllers/`)

- Este módulo **no** contiene ningún controlador de Front-Office o Back-Office Admin personalizado. Toda la funcionalidad se maneja dentro del archivo principal del módulo y sus plantillas y activos asociados.

### 4.3 Clases y Modelos Principales (`classes/`)

- Este módulo **no** contiene ninguna clase personalizada o definiciones de `ObjectModel`. Toda la configuración se almacena directamente en `ps_configuration` utilizando `Configuration::get()` y `Configuration::updateValue()`.

### 4.4 Activos JavaScript (`views/js/`)

- `uecookie/jscolor/jscolor.js`:
  - **Ámbito:** Back-office.
  - **Propósito:** Proporciona una funcionalidad de selector de color JavaScript para el formulario de configuración del módulo, permitiendo a los administradores seleccionar visualmente los colores para la barra de cookies.
- `uecookie/tinymce-original.js`:
  - **Ámbito:** Back-office.
  - **Propósito:** Una versión completa del editor de texto enriquecido TinyMCE, utilizada para el campo "Texto de la Cookie" en la configuración del módulo. Esto permite a los administradores formatear texto, añadir enlaces, etc.
- `uecookie/tinymce16.inc.js`:
  - **Ámbito:** Back-office.
  - **Propósito:** Probablemente un archivo de inclusión o configuración para TinyMCE, posiblemente personalizando su barra de herramientas u opciones para la compatibilidad con PrestaShop 1.6 o necesidades específicas del módulo.
- `uecookie/views/js/scripts.js`:
  - **Ámbito:** Front-office.
  - **Propósito:** Este script maneja la lógica del lado del cliente para la barra de notificación de cookies.
    - **Detectores de Eventos:** Probablemente escucha un evento de clic en el botón "Entiendo".
    - **Manipulación del DOM:** Oculta el elemento de la barra de cookies del DOM al descartarlo.
    - **Gestión de Cookies:** Establece una cookie del navegador (por ejemplo, `uecookie_accepted`) con una fecha de caducidad (determinada por el ajuste "Expiración de la Cookie") para evitar que la barra reaparezca durante la duración especificada.
    - **Verificación Inicial:** Al cargar la página, verifica la presencia de la cookie `uecookie_accepted` para determinar si se debe mostrar la barra o no.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- Este módulo **no** contiene ningún archivo CSS personalizado en `views/css/`. El estilo de la barra de cookies es probablemente en línea o generado dinámicamente en función de los ajustes de color, o se basa en estilos predeterminados mínimos del navegador. Los desarrolladores que deseen personalizar aún más la apariencia tendrían que apuntar a la estructura HTML generada por `top.tpl` utilizando el CSS personalizado de su tema.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de Hook (`views/templates/hook/`)**:
  - `uecookie/top.tpl`:
    - **Hook:** Esta plantilla está diseñada principalmente para ser renderizada en un hook de front-office como `displayHeader`, `displayFooter`, `displayTop` o `displayBeforeBodyClosingTag`. El método `hookDisplayHeader` del módulo es típicamente responsable de registrar y renderizar esta plantilla.
    - **Salida:** Genera la estructura HTML para la barra de notificación de cookies, incluyendo el texto personalizable, el botón y el estilo dinámico basado en los ajustes de configuración del módulo (color de fondo, color de texto, etc.). También incluye el JavaScript necesario (`scripts.js`) para manejar el descarte y la configuración de cookies.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - Este módulo no crea ninguna tabla de base de datos personalizada.
  - Todos los ajustes de configuración se almacenan en la tabla `ps_configuration`. Las entradas de configuración clave incluirían:
    - `UECOOKIE_ENABLED` (booleano)
    - `UECOOKIE_TEXT` (cadena multilingüe)
    - `UECOOKIE_BUTTON_TEXT` (cadena multilingüe)
    - `UECOOKIE_POSITION` (cadena: 'top' o 'bottom')
    - `UECOOKIE_BG_COLOR` (cadena: código de color hexadecimal)
    - `UECOOKIE_TEXT_COLOR` (cadena: código de color hexadecimal)
    - `UECOOKIE_LINK_COLOR` (cadena: código de color hexadecimal)
    - `UECOOKIE_BUTTON_BG_COLOR` (cadena: código de color hexadecimal)
    - `UECOOKIE_BUTTON_TEXT_COLOR` (cadena: código de color hexadecimal)
    - `UECOOKIE_EXPIRATION` (entero: días)
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página del front-office. | Se utiliza para inyectar los archivos CSS (si los hay) y JavaScript del módulo, y potencialmente la estructura HTML inicial de la barra de cookies si se posiciona en la parte superior. |
| `displayFooter` | Se ejecuta en la parte inferior de cada página del front-office, antes de la etiqueta de cierre `</body>`. | Se puede utilizar para inyectar el HTML y JavaScript de la barra de cookies, especialmente si se posiciona en la parte inferior. |
| `displayTop` | Se ejecuta en la sección del encabezado del tema, típicamente encima del contenido principal. | Hook alternativo para mostrar la barra de cookies en la parte superior. |
| `displayBeforeBodyClosingTag` | Se ejecuta justo antes de la etiqueta `</body>`. | Un hook robusto para inyectar JavaScript y elementos HTML que deben aparecer al final de la página. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Ley de Cookies de la Unión Europea", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto a la funcionalidad e integración del módulo.

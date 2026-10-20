---
title: "Zopim Chat Free - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Zopim Chat Free para PrestaShop de MyPresta.eu."
sidebar:
  label: "Zopim Chat Free - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Zopim Chat Free en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/zopim-chat-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/zopim-chat-free/)
>
> ---


# Zopim Chat Free

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop en sí y para cualquier integración de API externa, incluido Zendesk Chat.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Zopim Chat Free)

Esta es la pantalla de configuración principal y única para el módulo Zopim Chat Free. Aquí introducirás tu clave de cuenta de Zendesk Chat (Zopim) y decidirás dónde se debe cargar el script del widget de chat en tu tienda.

#### **Clave de Cuenta de Zopim**

-   **Qué hace esta configuración:** Esta es la configuración más crucial. Aquí es donde introduces el identificador único proporcionado por Zendesk Chat (Zopim) para tu widget de chat en vivo. Esta clave le dice al módulo qué widget de chat cargar en tu sitio web. Puedes encontrar esta clave dentro de tu panel de control de Zendesk Chat (normalmente en Configuración > Widget > Código de Inserción).
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se introduce una clave válida:* El widget de chat de Zopim asociado a tu cuenta de Zendesk Chat aparecerá en el front-office de tu tienda, permitiendo a los clientes iniciar chats.
    -   *Cuando se deja vacío o se introduce una clave no válida:* El widget de chat de Zopim no aparecerá en tu tienda y la funcionalidad de chat en vivo no estará disponible.
-   **Valor recomendado:** Tu clave de cuenta única de Zendesk Chat (Zopim).
-   **Escenario / ejemplo de comerciante:** Después de registrarte en Zendesk Chat, recibirás un fragmento de código. Dentro de ese código, encontrarás una cadena específica (por ejemplo, `zopim.setAndDefer('account', 'TU_CLAVE_DE_CUENTA');`). Copia `TU_CLAVE_DE_CUENTA` y pégala aquí.

#### **Cargar Zopim Chat en Hook**

-   **Qué hace esta configuración:** Esta opción determina dónde se inyectará el script de chat de Zopim en el código de tu tienda PrestaShop. Si bien el widget de chat en sí mismo suele flotar en la pantalla, la ubicación del script a veces puede afectar la velocidad de carga o la compatibilidad con temas específicos.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se establece en `displayHeader` (Cabecera):* El script de chat se cargará muy temprano, típicamente antes de la mayor parte del contenido de tu página. Esto puede hacer que el widget de chat aparezca rápidamente.
    -   *Cuando se establece en `displayRightColumn` (Columna Derecha):* El script se cargará con el contenido de la columna derecha. Esto es menos común para los widgets de chat y podría no ser ideal si tu tema no siempre muestra una columna derecha.
    -   *Cuando se establece en `displayLeftColumn` (Columna Izquierda):* Similar a la columna derecha, el script se carga con el contenido de la columna izquierda.
    -   *Cuando se establece en `displayProductButtons` (Botones de Página de Producto):* El script se cargará específicamente en las páginas de productos, cerca del área del botón "Añadir al carrito". Esto podría ser útil si principalmente deseas soporte de chat en las páginas de productos.
    -   *Cuando se establece en `displayFooter` (Pie de Página):* El script se cargará al final del contenido de tu página. Esto puede mejorar la velocidad de carga inicial de la página percibida por el usuario, ya que el contenido principal se carga primero y el widget de chat se carga después.
-   **Valor recomendado:** `displayHeader` o `displayFooter`. Para la mayoría de las tiendas, `displayHeader` asegura que el chat se cargue rápidamente. Si experimentas algún conflicto o quieres priorizar la carga del contenido, `displayFooter` es una buena alternativa.
-   **Escenario / ejemplo de comerciante:** Si tus clientes hacen preguntas con frecuencia *antes* incluso de empezar a navegar por los productos, cargar el chat en el `displayHeader` asegura que esté disponible inmediatamente. Si notas que tu página se carga lentamente y sospechas del script de chat, cambiar a `displayFooter` podría ayudar, ya que el chat se cargará después del contenido principal de la página.

#### Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | Clave de Cuenta de Zopim | Tu clave única de Zendesk Chat | Conecta tu tienda a tu cuenta de Zendesk Chat. Esencial para que aparezca el widget. |
| Página de Configuración del Módulo | Cargar Zopim Chat en Hook | `displayHeader` o `displayFooter` | Determina dónde se inyecta el script de chat (Cabecera, Columnas, Producto, Pie de página). Afecta el orden de carga y la posible compatibilidad con el tema. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: El widget de chat de Zopim no aparece en mi tienda. ¿Qué debo hacer?**
R1:

1.  **Verifica tu Clave de Cuenta de Zopim:** Ve a la página de configuración del módulo y asegúrate de que tu Clave de Cuenta de Zopim esté introducida correctamente. Incluso un solo error tipográfico impedirá que se cargue.
2.  **Verifica el Estado de Zendesk Chat:** Inicia sesión en tu panel de control de Zendesk Chat. ¿Está activo tu widget? ¿Están tus agentes en línea?
3.  **Borra la Caché de PrestaShop:** Ve a **Parámetros Avanzados > Rendimiento** en el back office de tu PrestaShop y haz clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los archivos de caché antiguos impiden que aparezcan los nuevos cambios del módulo.
4.  **Verifica Conflictos de Tema:** Cambia temporalmente al tema predeterminado de PrestaShop (por ejemplo, Classic) y ve si aparece el widget. Si lo hace, tu tema personalizado podría estar causando un conflicto. Contacta con el desarrollador de tu tema o con un webmaster.
5.  **Inspecciona la Consola del Navegador:** Abre las herramientas de desarrollador de tu navegador (F12) y revisa la pestaña "Consola" en busca de errores de JavaScript. Esto puede proporcionar pistas si el script no se carga.

**P2: El widget de chat se carga, pero se ve extraño o está posicionado incorrectamente.**
R2: El módulo inyecta el script de Zopim, pero el estilo visual y el posicionamiento exacto del widget están controlados en gran medida por la configuración de tu cuenta de Zendesk Chat y el CSS de tu tienda.

1.  **Panel de Control de Zendesk Chat:** Inicia sesión en tu panel de control de Zendesk Chat y revisa la configuración de apariencia de tu widget (por ejemplo, posición, colores, tamaño).
2.  **CSS del Tema:** El CSS de tu tema personalizado podría estar anulando algunos estilos predeterminados de Zopim. Un webmaster puede inspeccionar el elemento usando las herramientas de desarrollador del navegador e identificar reglas CSS en conflicto.

**P3: ¿Puedo traducir el texto del widget de chat a diferentes idiomas?**
R3: El módulo Zopim Chat Free en sí mismo no maneja las traducciones para la interfaz del widget. Esta funcionalidad se gestiona directamente dentro de la configuración de tu cuenta de Zendesk Chat. Zendesk Chat admite varios idiomas, y puedes configurar el widget para que se muestre en el idioma preferido del cliente según la configuración de su navegador o tu configuración de Zendesk Chat.

**P4: ¿Este módulo ralentizará mi sitio web?**
R4: El módulo Zopim Chat Free solo inyecta el script necesario de Zendesk Chat. El impacto en el rendimiento depende principalmente del propio servicio de Zendesk Chat y de tu conexión a internet. Puedes intentar establecer la opción "Cargar Zopim Chat en Hook" en `displayFooter` para asegurar que el contenido principal de tu página se cargue antes que el script de chat, lo que puede mejorar la velocidad de carga percibida de la página inicial.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una visión técnica para desarrolladores y webmasters que trabajan con el módulo Zopim Chat Free.

### 4.1 Visión General de la Arquitectura

El módulo `ZopimFree` es un módulo de PrestaShop sencillo diseñado para integrar el widget de Zendesk Chat (anteriormente Zopim). Funciona principalmente inyectando el script de inserción de Zendesk Chat en el front-office de la tienda PrestaShop. El módulo sigue una estructura de módulo estándar de PrestaShop, utilizando la clase `Module` para la instalación, desinstalación y manejo de la configuración a través de `getContent()`. Registra un único hook (`displayHeader` por defecto, pero configurable) para generar el JavaScript necesario.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. El módulo inyecta contenido directamente en los hooks.
-   **Controladores de Administración de Back-Office**: Ninguno. Toda la configuración se maneja dentro del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Principales (`classes/`)

-   No hay clases personalizadas ni definiciones de `ObjectModel` presentes en este módulo. Toda la lógica reside dentro del archivo principal `zopimfree.php`.

### 4.4 Activos JavaScript (`views/js/`)

-   No se incluyen archivos JavaScript personalizados en este módulo. El módulo genera el script de inserción de Zendesk Chat directamente en la plantilla, que luego carga el JS necesario desde el CDN de Zendesk.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   No se incluyen archivos CSS personalizados en este módulo. El estilo del widget de chat es manejado por el propio servicio de Zendesk Chat, con posibles anulaciones del tema activo de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de Hook (`views/templates/hook/`)**:
    -   `zopimfree/header-new-widget.tpl`
        -   **Hook:** Esta plantilla está diseñada para ser renderizada dentro de un hook de PrestaShop, específicamente el elegido en la configuración del módulo (por ejemplo, `displayHeader`, `displayFooter`).
        -   **Propósito:** Contiene la etiqueta `<script>` responsable de incrustar el widget de Zendesk Chat. Inserta dinámicamente la `ZOPIMFREE_ACCOUNT_KEY` de la configuración del módulo en el script de inicialización de Zendesk Chat.
        -   **Salida:** Genera el código de inserción estándar de Zendesk Chat, que luego carga el widget de chat desde los servidores de Zendesk.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El módulo no crea ninguna tabla SQL personalizada.
    -   Almacena su configuración en la tabla `ps_configuration`:
        -   `ZOPIMFREE_ACCOUNT_KEY`: Almacena la clave de cuenta de Zendesk Chat.
        -   `ZOPIMFREE_HOOK`: Almacena el nombre del hook donde se debe inyectar el script (por ejemplo, `displayHeader`, `displayFooter`).
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Ejecutado en la sección `<head>` de cada página. | Hook predeterminado para inyectar el script de Zendesk Chat temprano en la carga de la página. |
| `displayRightColumn` | Ejecutado en la columna derecha de las páginas donde está activo. | Hook alternativo para la inyección de scripts, menos común para los widgets de chat. |
| `displayLeftColumn` | Ejecutado en la columna izquierda de las páginas donde está activo. | Hook alternativo para la inyección de scripts, menos común para los widgets de chat. |
| `displayProductButtons` | Ejecutado en las páginas de productos, típicamente cerca del botón de añadir al carrito. | Hook específico para inyectar el script de chat solo en las páginas de productos. |
| `displayFooter` | Ejecutado justo antes de la etiqueta de cierre `</body>`. | Hook alternativo para inyectar el script de Zendesk Chat más tarde en la carga de la página, mejorando potencialmente la velocidad de carga inicial percibida. |

El módulo registra estos hooks dinámicamente basándose en el valor de configuración `ZOPIMFREE_HOOK`. El método `install()` registra todos los hooks potenciales, y `uninstall()` los desregistra. El método `hook{HookName}` luego verifica la configuración para decidir si debe renderizar la plantilla.

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, correcciones de errores y soporte para desarrolladores del módulo Zopim Chat Free, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Asegúrate de descargar la última versión compatible con tu instalación de PrestaShop.

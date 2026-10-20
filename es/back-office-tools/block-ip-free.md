---
title: "Bloquear IP gratis - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Bloquear IP gratis de MyPresta.eu."
sidebar:
  label: "Bloquear IP gratis - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Block IP free en MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/block-ip-free/)
>
> ---


# Bloquear IP gratis

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No hay requisitos especiales más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Bloquear IP gratis)

Esta es la pantalla de configuración principal y única para el módulo "Bloquear IP gratis". Aquí encontrará todos los ajustes para gestionar sus direcciones IP bloqueadas y el mensaje que se les muestra.

**Nombre de la pantalla y ubicación del menú:**

- **Ruta del menú:** Back Office > Módulos > Gestor de módulos > Bloquear IP gratis > Configurar

#### Ajustes y opciones:

1.  **Dirección IP (Campo de entrada)**

    - **Qué hace este ajuste:** Aquí es donde introduce la dirección IP que desea bloquear para que no acceda a su tienda.
    - **Efecto de cambiar este ajuste:**
        - *Cuando se añade una IP a la lista:* Cualquier visitante que intente acceder a su tienda desde esta dirección IP específica se le denegará el acceso y se le mostrará el "Mensaje de acceso bloqueado".
        - *Cuando se elimina una IP de la lista:* Los visitantes de esa dirección IP recuperarán el acceso completo a su tienda.
    - **Valor recomendado:** Introduzca la dirección IP exacta que desea bloquear. Puede añadir varias IPs, una a la vez, introduciendo cada una y haciendo clic en "Añadir".
    - **Escenario / ejemplo del comerciante:** Si observa que una dirección IP específica (por ejemplo, `192.168.1.100`) está intentando repetidamente pedidos fraudulentos o extrayendo datos de sus productos, introduciría `192.168.1.100` aquí y haría clic en "Añadir" para bloquearla.
2.  **Mensaje de acceso bloqueado (Área de texto)**

    - **Qué hace este ajuste:** Esto le permite personalizar el mensaje que verán los visitantes bloqueados cuando intenten acceder a su tienda.
    - **Efecto de cambiar este ajuste:**
        - *Cuando se introduce un mensaje personalizado:* Los visitantes bloqueados verán su mensaje personalizado en lugar de uno predeterminado. Esto le permite ser educado, informativo o firme.
        - *Cuando se deja por defecto:* Se mostrará un mensaje estándar de "Acceso denegado".
    - **Valor recomendado:** Un mensaje claro y conciso. Algo como: "El acceso a esta tienda ha sido bloqueado desde su dirección IP. Si cree que esto es un error, póngase en contacto con soporte."
    - **Escenario / ejemplo del comerciante:** Podría querer mostrar un mensaje como "Debido a actividad sospechosa, el acceso desde su dirección IP ha sido restringido temporalmente. Póngase en contacto con nuestro equipo de soporte si cree que esto es un error." Esto proporciona una mejor experiencia de usuario que un error genérico.

#### Gestión de la lista de IP bloqueadas:

Debajo del campo de entrada "Dirección IP", verá una lista de todas las direcciones IP actualmente bloqueadas.

- **Para añadir una IP:** Escriba la dirección IP en el campo "Dirección IP" y haga clic en el botón "Añadir".
- **Para eliminar una IP:** Junto a cada dirección IP listada, habrá un botón "Eliminar" (a menudo representado por un icono de papelera). Haga clic en este botón para desbloquear esa IP específica.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Dirección IP | Vacío (añadir IPs según sea necesario) | Añade/elimina direcciones IP específicas de la lista de bloqueo. Las IPs bloqueadas no pueden acceder a la tienda. |
| Página de configuración del módulo | Mensaje de acceso bloqueado | "Acceso denegado" (o similar) | Personaliza el mensaje que se muestra a los visitantes de direcciones IP bloqueadas. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Bloqueé una IP, pero el usuario todavía puede acceder a mi tienda. ¿Por qué?**
R:

1.  **Caché:** Su tienda PrestaShop o servidor podría tener la caché habilitada. Borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**) y cualquier caché del lado del servidor (como Varnish, caché de LiteSpeed, Cloudflare) si corresponde.
2.  **IP dinámica:** El usuario podría tener una dirección IP dinámica que ha cambiado desde que bloqueó la anterior.
3.  **Proxy/VPN:** El usuario podría estar utilizando un servidor VPN o proxy, que enmascara su dirección IP real. Tendría que bloquear la IP del servidor VPN/proxy si puede identificarla.
4.  **IP incorrecta:** Vuelva a comprobar que ha introducido la dirección IP correcta.

**P: ¡Bloqueé accidentalmente mi propia dirección IP y ahora no puedo acceder a mi Back Office! ¿Qué hago?**
R: Esta es una situación crítica pero solucionable. Necesita acceder a su servidor directamente:

1.  **Vía FTP/SFTP:** Conéctese al servidor de su tienda usando un cliente FTP (como FileZilla).
2.  **Navegue a la carpeta de módulos:** Vaya a `su_raiz_prestashop/modules/`.
3.  **Cambie el nombre de la carpeta del módulo:** Busque la carpeta `banipfree` y cámbiele el nombre a algo como `banipfree_DISABLED`. Esto deshabilitará efectivamente el módulo.
4.  **Acceda al Back Office:** Ahora debería poder iniciar sesión en su Back Office de PrestaShop.
5.  **Vuelva a habilitar y configure:** Vuelva a cambiar el nombre de la carpeta a `banipfree`, luego vaya a **Módulos > Gestor de módulos**, busque "Bloquear IP gratis" y haga clic en "Configurar" para eliminar su IP de la lista de bloqueados.

**P: ¿Puedo bloquear un rango de direcciones IP en lugar de solo una?**
R: La versión actual del módulo "Bloquear IP gratis" permite bloquear direcciones IP individuales. Para bloquear rangos completos (por ejemplo, `192.168.1.0/24`), normalmente necesitaría una configuración a nivel de servidor (por ejemplo, reglas `.htaccess` o configuraciones de firewall) o un módulo de seguridad más avanzado.

**P: ¿Este módulo ralentizará mi tienda?**
R: No, el módulo es muy ligero. Comprueba la dirección IP del visitante muy temprano en el proceso de carga de PrestaShop. Si la IP está bloqueada, el contenido de la tienda no se carga en absoluto, lo que en realidad puede ahorrar recursos del servidor al evitar que el tráfico no deseado procese completamente las solicitudes.

**P: ¿Cómo encuentro la dirección IP de un visitante problemático?**
R: Puede encontrar direcciones IP en varios lugares:

-   **Registros de acceso del servidor:** Su panel de control de alojamiento web (cPanel, Plesk) suele proporcionar acceso a los registros de acceso sin procesar, que enumeran la dirección IP de cada visitante.
-   **Detalles del pedido de PrestaShop:** Para los pedidos, la dirección IP del cliente suele registrarse en la página de detalles del pedido en el Back Office.
-   **Herramientas de análisis:** Algunas herramientas de análisis avanzadas pueden mostrar las direcciones IP de los visitantes, aunque a menudo anonimizadas.
-   **Módulos de seguridad de terceros:** Otros módulos de seguridad pueden registrar actividades sospechosas con direcciones IP.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Bloquear IP gratis".

### 4.1 Resumen de la arquitectura

El módulo "Bloquear IP gratis" es un módulo de PrestaShop simple de un solo archivo (`banipfree.php`) que aprovecha principalmente el hook `actionDispatcher`. Este hook se ejecuta muy temprano en el ciclo de vida de la solicitud de PrestaShop, lo que permite al módulo verificar la dirección IP del visitante antes de que ocurra cualquier procesamiento o renderizado significativo del contenido de la tienda. Si la IP se encuentra en la lista de bloqueados, el módulo termina inmediatamente la solicitud y muestra un mensaje personalizado, actuando efectivamente como un firewall de etapa temprana. La configuración se maneja a través del método estándar `getContent()`, almacenando los ajustes en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

- Este módulo **no** contiene ningún controlador personalizado de Front-Office o Back-Office. Toda la lógica está encapsulada dentro del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

- Este módulo **no** contiene ninguna clase personalizada o definiciones de `ObjectModel` en el directorio `classes/`. Todo el manejo de datos es directo a través de `Configuration::get()` y `Configuration::updateValue()`.

### 4.4 Activos JavaScript (`views/js/`)

- Este módulo **no** contiene ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

- Este módulo **no** contiene ningún archivo CSS personalizado. El mensaje de acceso bloqueado se muestra con un estilo mínimo en línea o con el estilo predeterminado del navegador.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- Este módulo **no** contiene ningún archivo de plantilla Smarty personalizado. El mensaje de acceso bloqueado se genera directamente como HTML/texto sin formato dentro del método `hookActionDispatcher`.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

El módulo no crea ninguna tabla de base de datos personalizada. Almacena sus configuraciones en la tabla estándar `ps_configuration`:

- `BANIPFREE_LIST`: Almacena una cadena de direcciones IP bloqueadas separadas por comas.
- `BANIPFREE_MSG`: Almacena el mensaje personalizado que se muestra a los usuarios bloqueados.
- `mypresta_updates`, `update_`, `updatev_`: Claves internas utilizadas por MyPresta.eu para las comprobaciones de actualización del módulo.

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionDispatcher` | Se ejecuta muy temprano en el ciclo de vida de la solicitud de PrestaShop, antes del despacho del controlador. | Este es el hook principal utilizado por el módulo. Recupera la dirección IP del visitante, la compara con `BANIPFREE_LIST`, y si se encuentra una coincidencia, genera `BANIPFREE_MSG` y termina la ejecución del script (`die()`), impidiendo una mayor carga de la tienda. |

### 4.8 Archivo principal del módulo (`banipfree/banipfree.php`)

Este es el núcleo del módulo.

-   **`__construct()`**: Inicializa los metadatos del módulo (nombre, pestaña, versión, autor, etc.).
-   **`install()`**:
    - Llama a `parent::install()`.
    - Registra el hook `actionDispatcher`.
    - Establece los valores de configuración iniciales para `BANIPFREE_LIST` (vacío) y `BANIPFREE_MSG` (mensaje predeterminado).
-   **`uninstall()`**:
    - Llama a `parent::uninstall()`.
    - Desregistra el hook `actionDispatcher`.
    - Elimina los valores de configuración (`BANIPFREE_LIST`, `BANIPFREE_MSG`).
-   **`getContent()`**:
    - Maneja el envío del formulario para guardar direcciones IP y el mensaje personalizado.
    - Recupera y muestra la lista actual de IPs bloqueadas.
    - Renderiza el formulario de configuración utilizando elementos estándar de `HelperForm` de PrestaShop (campo de texto para IP, área de texto para el mensaje, lista para IPs bloqueadas con botones de eliminar).
-   **`hookActionDispatcher()`**:
    - Este es el método crítico para el bloqueo.
    - Recupera la dirección IP del visitante (`$_SERVER['REMOTE_ADDR']`).
    - Obtiene `BANIPFREE_LIST` de `Configuration`.
    - Comprueba si la IP actual está presente en la lista separada por comas.
    - Si la IP está bloqueada, recupera `BANIPFREE_MSG`, genera una página HTML simple con el mensaje y llama a `die()` para detener una mayor ejecución.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Bloquear IP gratis", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad del módulo.

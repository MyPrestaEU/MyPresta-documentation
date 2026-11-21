---
title: Ban IP Pro - documentación y manual de usuario
sidebar:
  label: Ban IP Pro - documentación y manual de usuario
description: Manual de configuración y de resolución de problemas para tiendas que ya tienen Ban IP Pro.
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Block IP address Pro en MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/block-ip-address-pro/)
>
> ---


## 1. Requisitos

Ban IP Pro funciona dentro de PrestaShop. No necesita otro módulo.

Las etiquetas del módulo en pantalla están en inglés. En este manual aparecen tal como se ven en el back office.

- PrestaShop 1.7.1.0 hasta PrestaShop 9.
- PHP 7.1 o posterior, y al menos la versión de PHP que exige esa versión de PrestaShop. La instalación se detiene con PHP anterior a 7.1.
- La consulta de país y el bloqueo por país necesitan PHP 7.2 o posterior y un archivo de países de MaxMind que usted sube. Los bloqueos, la lista de permitidos, la comprobación de accesos y el límite de peticiones funcionan sin ese archivo, también en PHP 7.1.
- No hace falta ninguna extensión PHP adicional. La comprobación de actualizaciones usa cURL cuando el servidor lo tiene. Sin cURL, la comprobación lee la dirección solo si el servidor permite lecturas remotas.
- No hace falta ningún otro módulo. Una cuenta de MaxMind solo hace falta si quiere el archivo de países. El módulo no descarga ese archivo.
- Una importación admite hasta 5000 líneas y un archivo de hasta 2 MB. Una lista larga de reglas se lee de un archivo de caché en cada visita, así que una lista muy larga agranda ese archivo. Después de una importación grande use **Rebuild cache** en **Tools** si los contadores parecen desactualizados.

## 2. Instalación

1. En el back office abra **Módulos** y luego **Gestor de módulos**.
2. Suba el zip del módulo y pulse **Instalar**.
3. Abra **Configurar** en **Ban IP pro**. La página se abre en **Dashboard**. La barra también tiene **Statistics**, **Behavior**, **Automation**, **Network**, **Tools** y **Updates**.
4. El menú izquierdo gana **Ban IP** dentro de **Parámetros avanzados**. Esa página es la lista de reglas. **Manage rules** en la página del módulo lleva a la misma lista.

La instalación escribe una caché de reglas vacía. No vacía la caché de PrestaShop. Si falta la entrada de menú después de una actualización, abra **Configurar** una vez. La página actualiza las tablas del módulo. Si esa actualización falla, la página muestra **The module database could not be updated.**

Para apagar el módulo use el interruptor del **Gestor de módulos**. Las comprobaciones se detienen. Las reglas, los registros y los ajustes se quedan. Vuelva a encenderlo y se usan las mismas reglas. El módulo no tiene un botón propio de activar o desactivar.

Para quitarlo, pulse **Desinstalar** y confirme. La desinstalación quita la entrada **Ban IP** y desengancha las comprobaciones. Las reglas, el registro de bloqueos, los totales diarios, los contadores de accesos fallidos, la lista de acciones del personal y los ajustes se quedan en la base de datos. El archivo de países subido se queda en la carpeta del módulo. Instalar de nuevo conserva esas reglas y rellena solo los ajustes que siguen vacíos.

## 3. Configuración y trabajo diario

Un visitante abre la tienda. Antes de que se construya la página, el módulo lee su IP. Una regla Allow gana a un bloqueo. Si un bloqueo coincide con la tienda, el país del visitante está en la lista, el visitante abrió una ruta de sonda o la dirección superó el límite de peticiones, el visitante ve la página de bloqueo o la redirección que usted fijó. El bloqueo se escribe en el registro. El trabajo del personal empieza en **Dashboard** o en **Parámetros avanzados**, **Ban IP**. Usted añade una regla, importa una lista o deja que **Automation** cree bloqueos. Un bloqueo puede caducar. En la primera petición de cada día, las reglas caducadas se apagan y se borran las líneas viejas del registro. El recorrido termina cuando el visitante queda bloqueado, redirigido o deja pasar.

Abra **Módulos**, **Gestor de módulos**, **Ban IP pro**, **Configurar**.

### 3.1 Dashboard

![Dashboard](https://mypresta.eu/docs/images/docs/banippro-configure-dashboard.webp)

La pantalla está en inglés. En este manual esta parte se llama **Dashboard**.

**Dashboard** es la primera pestaña. **Manage rules** abre la lista de reglas.

Los siete contadores solo muestran números. No guardan ningún ajuste.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Manage rules** | un botón | Abre **Ban IP** en **Parámetros avanzados**. |
| **Active bans** | 0 | Reglas de bloqueo que siguen activas. Las reglas Allow no entran en este número. |
| **Blocked today** | 0 | Peticiones bloqueadas desde medianoche, a partir de los totales diarios. |
| **Blocked in 7 days** | 0 | Peticiones bloqueadas en los últimos 7 días, hoy incluido. |
| **Blocked in 30 days** | 0 | Peticiones bloqueadas en los últimos 30 días, hoy incluido. |
| **Unique IPs today** | 0 | Direcciones IP distintas en el registro de hoy. |
| **Expiring in 48 hours** | 0 | Bloqueos activos cuyo fin cae dentro de las próximas 48 horas. |
| **Active automatic bans** | 0 | Bloqueos activos por acceso fallido, ruta de sonda o límite de peticiones. |

**Blocked requests** es un gráfico de los últimos 30 días. Lee los totales diarios. No guarda ningún ajuste.

**Recent blocks** lista las últimas peticiones bloqueadas: fecha, IP, país, ruta y motivo. El país queda vacío hasta que suba el archivo de países en **Network**. Una lista vacía dice **No blocked requests yet.**

**Your current IP** muestra la dirección que ve este back office. **Add to allow list** guarda esa dirección como regla Allow para la tienda y el back office. La página dice entonces **Your current IP address is on the allow list.** Si no se puede leer la dirección, la página dice **Your current IP address could not be detected.** Si no se puede guardar la fila, dice **The address could not be added to the allow list.**

**Module status** muestra cuatro líneas.

| Línea | Al inicio | Qué hace |
|---|---|---|
| **Front hook** | **Registered** tras una instalación normal | **Registered** significa que la tienda ejecuta la comprobación. **Missing** significa que la comprobación no está enganchada. Reinstale el módulo o abra **Configurar** después de una actualización. |
| **Cached rules** | 0 | Cuántas reglas activas aceptó la caché. |
| **Unreadable rules** | 0 | Filas activas que la caché no pudo leer como dirección. |
| PHP y PrestaShop | las versiones de este servidor | Para compararlas con los requisitos. |

**Quick ban** escribe un bloqueo. El alcance es el de **Default scope of new bans** en **Behavior**. Un bloqueo añadido aquí no envía el correo de alerta.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **IP address** | vacío | Una dirección, un patrón como `192.168.1.*`, una red como `10.0.0.0/8` o un rango como `192.168.1.10-192.168.1.20`. |
| **Reason** | **Manual** | **Manual**, **Fraud**, **Spam**, **Scanner**, **Chargeback** o **Competitor**. Las estadísticas usan esta etiqueta. |
| **Duration** | **Permanent** | **1 hour**, **24 hours**, **7 days**, **30 days** o **Permanent** hasta que usted borre la regla. |
| **Comment** | vacío | Una nota privada. El visitante no la ve. |
| **I confirm blocking my own IP** | apagado | Solo hace falta cuando el bloqueo coincidiría con la IP con la que está en el back office y el alcance incluye el back office. |
| **Ban this address** | un botón | Guarda el bloqueo y muestra **The address was banned.** |

**Test an address** no crea ni borra ninguna regla.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **IP address** | vacío | La dirección que quiere comprobar. |
| **Test** | un botón | Muestra el resultado de la tienda, el del back office y el país. |
| **Front office** | oculto hasta la prueba | **No matching rule.**, **Allowed by rule #…** o **Blocked by rule #…**. |
| **Back office** | oculto hasta la prueba | Los mismos tres resultados para el panel. |
| Nota bajo la línea del panel | cuando la protección está apagada | **Back office protection is disabled, so back-office bans are not enforced.** |
| **Country** | **Unknown** si falta el archivo | El código de país, más **Blocked by country rule** cuando ese país está en la lista. |

**Recent admin actions** lista las últimas acciones del personal, como crear, importar, permitir, desbloquear y reconstruir la caché. Una lista vacía dice **No admin actions yet.**

### 3.2 Statistics

![Statistics](https://mypresta.eu/docs/images/docs/banippro-configure-stats.webp)

La pantalla está en inglés. En este manual esta parte se llama **Statistics**.

**Statistics** lee el registro de bloqueos. **24h**, **7 days** y **30 days** recargan la página para ese periodo. Al abrir la pestaña por primera vez el periodo es **30 days**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **24h** | un botón | Últimas 24 horas. El gráfico usa un punto por hora. |
| **7 days** | un botón | Últimos 7 días, hoy incluido. Un punto por día. |
| **30 days** | un botón, elegido al inicio | Últimos 30 días, hoy incluido. |
| **Export CSV** | un botón | Descarga `banippro-hits.csv` del periodo en pantalla. No cambia las reglas. |
| **From** | el primer día del periodo abierto | Se usa con **To** y **Apply**. |
| **To** | hoy | Se usa con **From** y **Apply**. Si **From** es posterior a **To**, los días se intercambian. |
| **Apply** | un botón | Recarga la pestaña para esos días. No guarda ningún ajuste. |
| **Blocked requests** | 0 | Cuántos bloqueos caen en el periodo. |
| **Unique IPs** | 0 | Cuántas direcciones distintas se bloquearon en el periodo. |

El gráfico **Blocked requests** sigue los botones de arriba. Debajo:

| Bloque | Qué muestra |
|---|---|
| **Top IP addresses** | Un gráfico de barras de las 10 direcciones con más bloqueos en el periodo. |
| **Top paths** | Las 10 rutas bloqueadas con más frecuencia, con un recuento. |
| **Top reasons** | Los 10 motivos de las reglas que coinciden, con un recuento. |
| **Top countries** | Los 10 códigos de país, con un recuento. Vacío hasta que se sube el archivo de países. |
| **Block log** | Fecha, IP, país, ruta, dirección de la regla y motivo. Hasta 100 filas. |

Un desglose vacío dice **No data for this period.** Un registro vacío dice **No blocked requests in this period.**

Los totales diarios del gráfico del panel se conservan cuando acorta **Keep logs for days**. Ese ajuste borra el registro línea a línea y la lista de acciones del personal. No borra los totales diarios.

### 3.3 Behavior

![Behavior](https://mypresta.eu/docs/images/docs/banippro-configure-behavior.webp)

La pantalla está en inglés. En este manual esta parte se llama **Behavior**.

Pulse **Save**. La página muestra **Settings updated**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Message for blocked visitors** | **You are blocked** en inglés. Las tiendas en polaco, español y portugués reciben también una frase en ese idioma. Cualquier otro idioma recibe la frase inglesa. En español la frase inicial es **El acceso ha sido bloqueado.** | El texto de la página de bloqueo. Rellene cada idioma de la tienda. El visitante ve la frase del idioma de la página. |
| **Redirect blocked visitors** | **No** | **Yes** envía a los visitantes bloqueados a **Redirect URL** en lugar del mensaje. **No** mantiene la página de bloqueo. |
| **Redirect URL** | vacío | Un enlace completo `http` o `https`. Se ignora mientras el interruptor de arriba esté en **No**. Un enlace incorrecto vuelve el interruptor a **No** y muestra **Enter a valid http or https URL for the redirect.** |
| **Default scope of new bans** | **Front office** | Lo usan **Quick ban** e **Import** cuando esas pantallas no piden el alcance. **Front office** es la tienda. **Back office** es este panel. **Front office and back office** es ambos. |
| **Protect the back office** | **No** | **Yes** aplica también los bloqueos en este panel. Guardar rechaza **Yes** hasta que su IP actual esté en la lista de permitidos, y muestra **Add your current IP to the allow list before you protect the back office.** El interruptor se queda en **No**. |

El formulario muestra también este aviso: **Back office protection stays off until your current IP is on the allow list. Rules still apply to the shop front by default.**

### 3.4 Automation

![Automation](https://mypresta.eu/docs/images/docs/banippro-configure-automation.webp)

La pantalla está en inglés. En este manual esta parte se llama **Automation**.

Pulse **Save**. La página muestra **Settings updated**. Los bloqueos automáticos se aplican a la tienda, en todas las tiendas de la instalación. No encienden **Protect the back office**. Una dirección que ya coincide con una regla Allow no se bloquea. Una dirección que ya tiene un bloqueo activo se deja como está.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Block known probe paths** | **Yes** | **Yes** bloquea a un visitante de la tienda que abre una ruta de la lista de abajo. La carpeta de administración nunca se bloquea así. **No** detiene esta comprobación. |
| **Probe ban length in hours** | 24 | Cuánto dura ese bloqueo. 24 es un día. 0 lo mantiene hasta que usted lo borre. |
| **Probe paths** | `/.env`, `/wp-login.php`, `/wp-admin`, `/xmlrpc.php`, `/vendor/phpunit`, `/phpmyadmin`, `/.git/`, `/boaform`, `/cgi-bin/`, una por línea | Una petición cuya ruta contiene una de estas líneas se bloquea al momento. Una lista vacía se sustituye por esta lista por defecto al guardar. Una línea que es solo `/`, y una línea que es su carpeta de administración, se descartan. |
| **Ban customers after failed logins** | **No** | **Yes** cuenta contraseñas de cliente incorrectas. Un acceso de cliente correcto pone el contador a cero. |
| **Ban employees after failed logins** | **No** | El mismo recuento para el acceso de empleado. Ponga su propia IP en la lista de permitidos antes de encenderlo. El bloqueo se aplica a la tienda, no al panel, salvo que esa IP también quede cubierta por un bloqueo cuyo alcance incluye el back office. |
| **Failed logins before a ban** | 5 | Con 5, el siguiente acceso fallido dentro de la ventana crea el bloqueo. El valor guardado más pequeño es 1. |
| **Failed login window in minutes** | 15 | Los fallos más antiguos que esto se olvidan. El valor guardado más pequeño es 1. |
| **Login ban length in hours** | 24 | Cuánto dura el bloqueo por acceso. 0 lo mantiene hasta que usted lo borre. |
| **Limit requests per IP** | **No** | **Yes** cuenta peticiones de páginas de la tienda. Las imágenes y otros archivos que nunca entran en PrestaShop no se cuentan. Déjelo en **No** con tráfico normal. En una tienda con mucho tráfico un límite bajo bloquea a clientes reales. |
| **Requests allowed in the window** | 120 | Cuántas peticiones de página puede hacer una IP durante la ventana. El valor guardado más pequeño es 1. |
| **Rate limit window in minutes** | 1 | Duración de esa ventana. 1 significa que el límite de arriba se cuenta por minuto. |
| **Rate limit ban in minutes** | 15 | Cuántos minutos dura el bloqueo después de cruzar el límite. El valor guardado más pequeño es 1. |
| **Email me when an automatic ban is created** | **No** | **Yes** envía un correo cuando el módulo crea un bloqueo. Los bloqueos que usted añade a mano no lo envían. Como mucho sale un correo por hora. |
| **Alert email** | vacío | El buzón que recibe la alerta. Déjelo vacío para usar el correo de la tienda. Un valor que no es un correo se borra y la página muestra **Enter a valid alert email address.** |

El asunto del correo es **Ban IP Pro alert**. El mensaje nombra la IP, el motivo (`auto-login`, `auto-honeypot` o `auto-rate`), la hora de fin o la palabra `permanent`, y el nombre de la tienda.

### 3.5 Network

![Network](https://mypresta.eu/docs/images/docs/banippro-configure-network.webp)

La pantalla está en inglés. En este manual esta parte se llama **Network**.

Pulse **Save**. La página muestra **Settings updated**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Trust Cloudflare** | **No** | Enciéndalo solo cuando el dominio de la tienda pasa por Cloudflare. El módulo lee entonces la IP del visitante desde Cloudflare, y solo si la conexión viene de verdad de Cloudflare. Déjelo en **No** si no está seguro, o cada visitante puede parecer el proxy. |
| **Trusted reverse proxies** | vacío | Si un proxy o un balanceador está delante de la tienda, ponga aquí su IP o su red, una por línea. El módulo lee la IP del visitante solo desde ese proxy. Déjelo vacío si no está seguro. |
| **Block selected countries** | **No** | **Yes** bloquea a cada visitante cuyo país está en la lista de abajo. Empieza a funcionar después de subir la base de países. No ponga su propio país. Un bloqueo por país no añade una fila en **Ban IP**. Bloquea esa petición y escribe una línea de registro con el motivo **Country**. |
| **Country codes** | vacío | Códigos de dos letras, por ejemplo `PL`, `DE` o `US`. Sepárelos con comas, espacios o líneas nuevas. Lo que no tenga dos letras se descarta. |
| **Keep logs for days** | 90 | Cuántos días se guardan el historial de bloqueos y la lista de acciones del personal. Las filas más viejas se quitan en la primera petición de un día posterior. El valor guardado más pequeño es 1. Los valores por encima de 3650 se guardan como 3650. |
| **GeoLite2 country database** | sin archivo | Opcional. Elija un archivo cuyo nombre acabe en `.mmdb`. Después de **Save**, las estadísticas pueden mostrar el país y el bloqueo por país puede funcionar. El resto del módulo no necesita este archivo. |

Encima del campo de archivo la página muestra una de estas líneas:

| Qué ve | Qué hacer |
|---|---|
| **GeoIP database is ready.** | Nada. La consulta de país funciona. |
| **Country lookup needs PHP 7.2 or newer. The rest of the module keeps working.** | Los bloqueos siguen. Las estadísticas de país y los bloqueos por país se quedan apagados hasta que PHP sea 7.2 o posterior. |
| **Upload GeoLite2-Country.mmdb to enable country statistics and country blocks. MaxMind distributes that file.** | Suba el archivo y pulse **Save**. |

Un archivo incorrecto muestra **Upload a GeoLite2 Country file that ends with .mmdb.** Si el archivo no se puede guardar, la página muestra **The GeoIP database could not be saved.** Una subida correcta muestra **The GeoIP database was uploaded.**

### 3.6 Tools

![Tools](https://mypresta.eu/docs/images/docs/banippro-configure-tools.webp)

La pantalla está en inglés. En este manual esta parte se llama **Tools**.

**Import rules** crea bloqueos. El alcance es **Default scope of new bans**. Cada fila nueva está activa, es permanente y usa el motivo **Manual**, salvo que la línea diga otra cosa.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Addresses** | vacío, con un ejemplo en el marcador | Una dirección por línea. Una línea CSV puede ser dirección, comentario, motivo. Las líneas que empiezan por `#` se ignoran. Una dirección que ya existe se omite. |
| **File** | vacío | Un archivo de texto. Sus líneas se añaden al cuadro de arriba. Un archivo mayor de 2 MB muestra **The import file is larger than 2 MB.** y no se importa nada. |
| **Import** | un botón | Crea los bloqueos y muestra **%d rules were imported.** Las líneas omitidas muestran también **%d lines were skipped.** La importación se detiene después de 5000 líneas. |
| **Export rules CSV** | un botón | Descarga `banippro-rules.csv` de cada regla. No cambia la lista. |

**Web server snippet** muestra dos cuadros, Apache 2.4 y nginx. El encabezado incluye cuántas direcciones se exportaron. Solo entran los bloqueos activos y permanentes que son una IP suelta o una red. Un patrón como `192.168.1.*` se escribe como red. Los rangos y los bloqueos temporales quedan fuera. **Copy** copia el cuadro. El módulo no edita los archivos del servidor. Usted pega el texto en la configuración del servidor. Si no hay nada que exportar, ambos cuadros lo dicen.

**Emergency unlock** muestra una dirección. Ábrala desde un navegador que está bloqueado. El módulo añade la IP de ese navegador a la lista de permitidos, para la tienda y el back office, y deja pasar esa petición.

| Botón | Qué hace |
|---|---|
| **Copy** | Copia la dirección de desbloqueo. La clave no cambia. |
| **Create a new key** | Sustituye la clave. La página dice **A new emergency key was created. The previous unlock link no longer works.** |
| **Rebuild cache** | Reescribe la caché de reglas desde la lista actual. La página dice **The rule cache was rebuilt.** |

Guarde la dirección de desbloqueo fuera de la tienda. Quien la abre entra en la lista de permitidos.

### 3.7 Updates

![Updates](https://mypresta.eu/docs/images/docs/banippro-configure-updates.webp)

La pantalla está en inglés. En este manual esta parte se llama **Updates**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Check now** | un botón | Pregunta a MyPresta si existe una versión más nueva. **New version available!** o **Module is up to date!** La tienda nunca hace esta llamada. |
| **Updates notifications** | **Disable** | **Enable** hace la misma comprobación al abrir esta pestaña, como mucho una vez cada tres días. Una versión más nueva muestra también un aviso en la página del módulo: **New version available, check MyPresta.eu for more informations**, con **More details in changelog**. |
| **Save** | un botón | Guarda **Enable** o **Disable**. No descarga un archivo. La página dice **Settings updated**. |

El enlace bajo el formulario abre la página del módulo en mypresta.eu, donde se publica el registro de cambios. Este manual no enumera versiones.

### 3.8 Ban IP, la lista de reglas

![Ban IP, la lista de reglas](https://mypresta.eu/docs/images/docs/banippro-rules-list.webp)

La pantalla está en inglés. En este manual esta parte se llama **Ban IP, la lista de reglas**.

Abra **Parámetros avanzados**, **Ban IP**, o **Manage rules** en **Dashboard**. La línea sobre la lista dice que el panel, las estadísticas y la automatización están en la página de configuración del módulo, y ofrece **Open dashboard**.

**Add new** abre una regla en blanco. En una regla nueva puede pegar varias direcciones, una por línea. Comparten el comentario, el motivo, el tipo de regla, el alcance, la caducidad, la marca de activo y la tienda.

Las columnas son **ID**, **IP address**, **Match**, **Rule**, **Scope**, **Hits**, **Last hit**, **Expires**, **Reason** y **Active**. Cuando la tienda usa más de una tienda, se añade **Shop**.

| Columna | Qué ve |
|---|---|
| **Match** | **Exact**, **Wildcard**, **CIDR** o **Range**. |
| **Rule** | **Ban** o **Allow**. |
| **Scope** | **Front office**, **Back office** o **Front office and back office**. |
| **Hits** | Cuántas peticiones bloqueadas se registraron contra esta regla. |
| **Last hit** | Fecha de la última. |
| **Expires** | Una fecha y hora, o **Permanent**. |
| **Reason** | **Manual**, **Fraud**, **Spam**, **Scanner**, **Chargeback**, **Competitor**, **Auto ban (login)**, **Auto ban (probe)**, **Auto ban (rate limit)** o **Country**. |
| **Active** | El icono de estado. Púlselo para encender o apagar la fila. Una regla inactiva se queda en la lista y no coincide con nadie. |
| **Shop** | **All shops**, o el nombre de una tienda. Solo se muestra con multitienda. |

Use la fila de filtros para buscar. Filtrar no bloquea ni permite a nadie.

Acciones de fila:

| Acción | Qué hace |
|---|---|
| **Edit** | Abre la regla. En una fila existente solo se puede guardar una dirección. |
| **Whitelist** | Se muestra en un bloqueo. Cambia esa fila a **Allow** y reconstruye la caché. Oculto en una fila que ya es **Allow**. |
| **Delete** | Quita la fila y reconstruye la caché. |

Acciones masivas, después de marcar filas:

| Acción | Qué hace |
|---|---|
| **Enable selection** | Enciende las filas marcadas y reconstruye la caché. |
| **Disable selection** | Apaga las filas marcadas y reconstruye la caché. Se quedan en la lista. |
| **Delete selected** | Pregunta **Delete selected items?** y luego quita las filas marcadas y reconstruye la caché. |

Una regla Allow se comprueba antes que los bloqueos. Una regla Allow que coincide deja pasar al visitante aunque un bloqueo también coincidiera.

Una regla cuyo fin ya pasó deja de coincidir al momento. En la primera petición del día siguiente también se pone inactiva.

### 3.9 El formulario de la regla

![El formulario de la regla](https://mypresta.eu/docs/images/docs/banippro-rule-form.webp)

La pantalla está en inglés. En este manual esta parte se llama **El formulario de la regla**.

**Save** escribe la regla, reconstruye la caché y vuelve a la lista cuando cada línea es válida.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **IP address** | vacío | En una regla nueva, una dirección por línea. En una edición, una dirección. Una IP suelta, un patrón como `192.168.1.*`, una red como `10.0.0.0/8` o un rango como `192.168.1.10-192.168.1.20`. Los patrones son IPv4 y los asteriscos tienen que ir al final. IPv6 vale para una dirección suelta, una red y un rango. |
| **Comment** | vacío | Una nota privada que solo usted ve en esta lista. Los visitantes no la ven. |
| **Reason** | **Manual** | Por qué esta dirección está en la lista. Las estadísticas lo usan para distinguir un bloqueo manual de uno automático. Los motivos automáticos no están en este desplegable. El módulo los escribe él. |
| **Rule** | **Ban** | **Ban** bloquea la dirección. **Allow** siempre la deja pasar, aunque otra regla fuera a bloquearla. |
| **Scope** | el valor de **Default scope of new bans** | **Front office** es lo que ven los clientes. **Back office** es este panel. **Front office and back office** significa que la regla vale en la tienda y en el panel. |
| **Expires at** | vacío | Déjelo vacío para conservar la regla hasta que usted la borre. O escriba la fecha y la hora en que debe parar, por ejemplo `2026-12-31 18:00`. Un valor incorrecto muestra **The expiry date is not valid.** |
| **Active** | **Yes** | **No** deja la regla en la lista, pero no bloquea ni permite a nadie. |
| **I confirm blocking my own IP** | **No** | La línea de ayuda muestra su IP actual, o **unknown**. La confirmación hace falta cuando un bloqueo coincidiría con esta IP en el back office. |
| **Shop** | **All shops** | Solo se muestra con multitienda. **All shops** significa que la regla vale en cada tienda de esta instalación. Elija una tienda para limitar la regla a ella. |
| **Save** | un botón | Guarda las filas. |

Una entrada vacía muestra **Enter an IP address.** Un patrón que coincidiría con todas las direcciones, como `*.*.*.*` o una red con prefijo `0`, muestra **This rule would block every address.** Una dirección incorrecta muestra **This IP address or range is not valid.** Una segunda regla activa con la misma dirección y el mismo tipo de bloqueo o permiso muestra **This rule already exists.** Un bloqueo que coincide con su IP actual en el back office, sin el interruptor de confirmación, muestra **This ban matches your current IP in the back office. Confirm it before saving.** Más de una línea en una edición muestra **Edit one address at a time.** Una línea incorrecta en una regla nueva se omite con **Line … was skipped:** y el motivo. Una línea duplicada se omite con **Line was skipped because it already exists:** y la dirección. Cuando unas líneas se guardaron y otras no, la página muestra también **%d rules were saved.** y se queda en el formulario. Si la fila no se puede escribir, la página muestra **The rule could not be saved.** Una fila que no está muestra **Rule not found.**

## 4. Frente de la tienda

El tema de la tienda no imprime un bloque, una insignia ni un widget de este módulo. En una página normal de producto, de carrito o de inicio no hay nada que fotografiar.

Un visitante que no está bloqueado ve la tienda como siempre. Un visitante bloqueado ve una página sencilla: el logotipo de la tienda cuando la tienda tiene uno, el encabezado 403, el **Message for blocked visitors** del idioma de la página y la IP del visitante. La página pide a los buscadores que no la indexen. Si **Redirect blocked visitors** está en **Yes** y **Redirect URL** es un enlace `http` o `https` válido, el visitante va a esa dirección y no ve el mensaje.

La misma página de bloqueo se usa en el back office cuando **Protect the back office** está en **Yes** y la IP del empleado coincide allí con un bloqueo y no coincide con una regla Allow.

Estas comprobaciones solo corren en peticiones que entran en PrestaShop. Los archivos que sirve directamente el servidor web, como las imágenes, no se comprueban y no los cuenta **Limit requests per IP**.

No hay página de cuenta del cliente ni formulario para reclamar. El visitante pasa, ve la página de bloqueo o cae en la redirección.

| Qué ve el visitante | Qué hace usted |
|---|---|
| La tienda, como siempre | Ningún bloqueo coincide, o coincidió una regla Allow. |
| La página de bloqueo con su mensaje y la IP del visitante | Coincidió un bloqueo, el país está bloqueado, se abrió una ruta de sonda o se cruzó el límite de peticiones. La redirección está en **No**. |
| Otro sitio, sin mensaje | La redirección está en **Yes** y la URL es válida. |
| El back office, como siempre | **Protect the back office** está en **No**, o esta IP está en la lista de permitidos. |

## 5. Problemas

**La página del módulo dice Ban IP Pro requires PHP 7.1 or newer.**  
El servidor está en PHP anterior a 7.1. La instalación se rechaza y **Configurar** solo muestra esa frase. Pase la tienda a PHP 7.1 o posterior y vuelva a instalar.

**Configurar dice The module database could not be updated.**  
No se pudieron crear o actualizar las tablas. Pida al alojamiento que permita al usuario de la base crear y alterar tablas, y abra **Configurar** otra vez.

**Front hook dice Missing.**  
La comprobación no está enganchada. Reinstale el módulo, o desactívelo y actívelo de nuevo desde el **Gestor de módulos**. Las reglas existentes se quedan.

**Guardar en Behavior rechaza Protect the back office.**  
La página dice **Add your current IP to the allow list before you protect the back office.** En **Dashboard**, pulse **Add to allow list**, ponga el interruptor en **Yes** y guarde otra vez.

**Se quedó fuera del back office.**  
Abra la dirección de emergencia de **Tools**, **Emergency unlock**, en un navegador que todavía llega a la tienda. La IP de ese navegador se añade a la lista de permitidos y la petición pasa. Si no puede abrir **Tools**, use una copia de la dirección que guardó antes. **Create a new key** deja inservible la dirección antigua, así que actualice su copia después de usarla.

**Un bloqueo de su propia IP se rechaza.**  
La página dice **This ban matches your current IP in the back office. Confirm it before saving.** Encienda **I confirm blocking my own IP**, o cambie el alcance a **Front office** si solo quiere bloquear esa IP en la tienda.

**La importación dice The import file is larger than 2 MB.**  
Parta el archivo. Cada importación se detiene después de 5000 líneas y entonces muestra que la importación se detuvo. Pase el resto en otra importación. Las líneas omitidas muestran **%d lines were skipped.** Las direcciones que ya existen se omiten a propósito.

**La dirección se guardó, pero la tienda sigue dejándola pasar.**  
Compruebe **Active**, **Scope** y **Expires at**. Una regla del back office no afecta a la tienda. Una regla Allow para esa IP gana. En **Dashboard**, use **Test an address**. Luego pulse **Rebuild cache** en **Tools**.

**Los bloqueos del back office no hacen nada.**  
**Test an address** añade **Back office protection is disabled, so back-office bans are not enforced.** Encienda **Protect the back office** en **Behavior** después de que su IP esté en la lista de permitidos.

**El bloqueo por país no hace nada.**  
**Block selected countries** tiene que estar en **Yes**, los códigos tienen que ser de dos letras y la página tiene que decir **GeoIP database is ready.** En PHP anterior a 7.2 la página dice que la consulta de país necesita PHP 7.2 o posterior. No ponga su propio país en la lista.

**Los clientes se bloquean durante una venta normal.**  
**Limit requests per IP** está encendido y el límite es bajo para esta tienda. Póngalo en **No**, o suba **Requests allowed in the window**. Borre los bloqueos automáticos en **Ban IP**. Su motivo es **Auto ban (rate limit)**.

**Un acceso fallido de empleado no bloqueó el back office.**  
Ese bloqueo automático se aplica a la tienda. El panel se bloquea solo cuando **Protect the back office** está en **Yes** y un bloqueo cuyo alcance incluye el back office coincide con esa IP.

**El correo de alerta no llega nunca.**  
**Email me when an automatic ban is created** tiene que estar en **Yes**. Los bloqueos manuales no envían correo. Un segundo bloqueo automático dentro de la misma hora no envía otro correo. El buzón es **Alert email**, o el correo de la tienda cuando ese campo está vacío. La tienda tiene que poder enviar correo ya.

**El gráfico sigue mostrando días viejos después de acortar el registro.**  
**Keep logs for days** quita el registro línea a línea y las acciones del personal. Los totales diarios que usa el gráfico del panel se quedan.

**New version available, check MyPresta.eu for more informations.**  
Abra **Updates** y use el enlace, o pulse **Check now**. Este manual no enumera los cambios.

## 6. Para el desarrollador

### 6.1 Resumen

Nombre técnico `banippro`, versión 2.0.0, clase `banippro`, nombre en la lista **Ban IP pro**, autor MyPresta.eu, pestaña `administration`. Página del producto: `https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html`.

`actionDispatcherBefore` llama a `BanIpGuard::protect()`. El guard resuelve la IP, aplica el desbloqueo de emergencia y luego `BanIpMatcher::decide()` sobre la caché de `cache/rules.php`. Allow gana a ban. El bloqueo por país, los bloqueos de sonda y el límite de peticiones corren en la tienda. Un bloqueo registra un hit y o redirige o pinta `blocked.tpl` con estado 403 y termina la petición. `actionDispatcherAfter` ejecuta `BanIpAutoBan::evaluate()` para un acceso que se armó antes. Los ajustes son valores de configuración globales leídos por `BanIpInstaller`. El controlador de menú `AdminBanIpPro` edita la tabla `ban`.

No hay sustitución de `enable()` ni de `disable()`. El apagado de PrestaShop desregistra los hooks, así que el guard no corre. Los datos se quedan.

### 6.2 Archivos

| Archivo | Función |
|---|---|
| `banippro.php` | Instalación, hooks, pestañas, bloqueo rápido, importación, prueba. |
| `controllers/admin/AdminBanIpProController.php` | Lista, formulario, CSV, acción de lista blanca. |
| `models/banip.php` | Modelo de `ban`, más `storeRule()` e `importLines()`. |
| `classes/BanIpGuard.php` | Comprobación, página de bloqueo, mantenimiento diario. |
| `classes/BanIpMatcher.php` | Exact, wildcard, CIDR y range. Decide allow y después ban. |
| `classes/BanIpClientIp.php` | Dirección remota, Cloudflare, proxies de confianza. |
| `classes/BanIpCache.php` | Construye e incluye `cache/rules.php`. |
| `classes/BanIpAutoBan.php` | Sonda, acceso fallido, límite, correo de alerta. |
| `classes/BanIpStats.php` | Panel, informe, CSV, fragmentos de servidor. |
| `classes/BanIpGeo.php` | Lee `geo/GeoLite2-Country.mmdb` sin la biblioteca de MaxMind. |
| `classes/BanIpInstaller.php` | Tablas y configuración por defecto. |
| `classes/BanIpUpdate.php` | Comprobación de versión contra `dev.mypresta.eu`. |
| `views/templates/admin/*.tpl` | Panel, estadísticas, herramientas, carcasa. |
| `views/templates/front/blocked.tpl` | Página de bloqueo. |
| `views/js/dashboard.js` | Gráficos y botones de copiar. |
| `mails/en/banippro_alert.txt`, `mails/pl/banippro_alert.txt` | Cuerpos de la alerta. El asunto está fijo en `BanIpAutoBan::alert()`. |
| `upgrade/upgrade-2.0.0.php` | Ejecuta `BanIpInstaller::upgrade()`, cambia los hooks antiguos por el conjunto 2.0.0 y reconstruye la caché. |
| `lib/searchTool/` | Se carga en la página de configuración. Ningún campo de configuración lo llama. |
| `tests/matcher_test.php` | Comprobaciones CLI del matcher. |

### 6.3 Controladores

`AdminBanIpPro` extiende `ModuleAdminController`. La pestaña padre es `AdminAdvancedParameters`. Nombre de clase `AdminBanIpPro`. Tabla `ban`, identificador `id_ban`, objeto `banip`.

Los filtros de lista usan los nombres habituales del helper (`banFilter_ip` y el resto de campos). Acciones de fila: editar, `displayWhitelistLink` (`banippro_whitelist`), borrar. En masa: delete, enable, disable. `exportHits` envía el CSV de hits. `exportRules` envía el CSV de reglas.

No hay controlador de frente. La respuesta de bloqueo se pinta dentro del hook del dispatcher y la petición termina.

`?banippro_unlock=` lo lee `BanIpGuard::tryUnlock()`. El valor tiene que coincidir con `banippro_emergency_key` mediante `hash_equals`. Una coincidencia llama a `BanIpAutoBan::ensureAllow()` con alcance tienda y back office (`apply_to` 3, `id_shop` 0) y audita `unlock`.

### 6.4 Hooks

Registrados en la instalación:

| Hook | Llamada |
|---|---|
| `actionDispatcherBefore` | `BanIpGuard::protect()`. |
| `actionDispatcherAfter` | `BanIpAutoBan::evaluate()`. También se registra después de la comprobación principal de la instalación. |
| `actionFrontControllerSetMedia` | `BanIpAutoBan::arm('customer')`. |
| `actionAuthentication` | `BanIpAutoBan::markSuccess('customer')`. |
| `actionAdminControllerInitAfter` | `BanIpAutoBan::arm('employee')`. |

`upgrade-2.0.0.php` desregistra `header`, `displayHeader`, `home`, `displayHome`, `actionFrontControllerAfterInit` y `actionAdminControllerSetMedia`.

El módulo no registra un hook propio. El armado del acceso busca `submitLogin` en la petición. Un acceso correcto de cliente limpia el contador de fallos del cliente. El éxito del empleado se detecta cuando el empleado está conectado en `evaluate()`.

### 6.5 Sustituciones

El módulo no sustituye ninguna clase ni controlador de PrestaShop.

### 6.6 Base de datos

La desinstalación no borra estas tablas ni las claves de configuración. `BanIpInstaller::ensure()` añade las columnas que faltan en `{prefix}ban` al abrir **Configurar**, así que una tabla `ban` antigua se conserva y se amplía. Reinstalar no vacía las filas.

| Tabla | Contenido |
|---|---|
| `{prefix}ban` | `id_ban`, `ip`, `ip_end`, `match_type` (`exact`, `wildcard`, `cidr`, `range`), `rule_type` (1 ban, 2 allow), `apply_to` (1 tienda, 2 panel, 3 ambos), `views`, `comment`, `reason`, `active`, `date_add`, `date_upd`, `date_end`, `last_hit`, `id_employee`, `id_shop` (0 significa todas las tiendas), `range_start`, `range_end`. |
| `{prefix}banippro_hit` | Una fila por bloqueo: `id_ban`, `ip`, `request_uri`, `user_agent`, `country_iso`, `id_shop`, `date_add`. |
| `{prefix}banippro_daily` | `day`, `id_shop`, `blocked`, `auto_banned`. No se borra al podar los registros. |
| `{prefix}banippro_fail` | `ip`, `context` (`customer`, `employee`, `rate`), `hits`, `window_start`. |
| `{prefix}banippro_audit` | `id_employee`, `action`, `details`, `date_add`. |

`BanIpGuard::dailyMaintenance()` corre una vez por día de calendario. Pone `active` a 0 en las reglas cuyo `date_end` está en el pasado, reconstruye la caché si cambió alguna fila y borra filas de hit y de audit más viejas que `banippro_log_days`.

### 6.7 Claves y traducciones

Todas las claves son globales (`id_shop` 0). Si falta una clave, se usa el valor por defecto entre paréntesis.

| Clave | Por defecto |
|---|---|
| `banippro_emergency_key` | 32 caracteres hex de `random_bytes`, u OpenSSL, o `md5` |
| `banippro_msg` | Por idioma. `en` You are blocked. `pl` Dostęp został zablokowany. `es` El acceso ha sido bloqueado. `pt` y `br` O acesso foi bloqueado. Los demás idiomas reciben la frase inglesa. En el almacenamiento se permite HTML. |
| `banippro_redirect` | 0 |
| `banippro_url` | vacío |
| `banippro_default_apply` | 1 |
| `banippro_protect_admin` | 0 |
| `banippro_honeypot` | 1 |
| `banippro_honeypot_hours` | 24 |
| `banippro_honeypot_paths` | `BanIpInstaller::defaultHoneypotPaths()` |
| `banippro_autoban_customer` | 0 |
| `banippro_autoban_employee` | 0 |
| `banippro_autoban_threshold` | 5 |
| `banippro_autoban_window` | 15 |
| `banippro_autoban_hours` | 24 |
| `banippro_ratelimit` | 0 |
| `banippro_ratelimit_max` | 120 |
| `banippro_ratelimit_window` | 1 |
| `banippro_ratelimit_ban_minutes` | 15 |
| `banippro_alert` | 0 |
| `banippro_alert_email` | vacío |
| `banippro_alert_last` | tiempo unix del último correo de alerta, escrito al enviarlo |
| `banippro_cloudflare` | 0 |
| `banippro_trusted_proxies` | vacío |
| `banippro_countries_enabled` | 0 |
| `banippro_countries` | vacío |
| `banippro_log_days` | 90 |
| `banippro_last_maintenance` | `Y-m-d` del último mantenimiento diario |
| `mypresta_updates` | no se siembra; el formulario trata un valor ausente como 0 |
| `update_banippro` | 0, luego el tiempo unix de la última comprobación |
| `updatev_banippro` | cadena de versión remota de la última comprobación |

`BanIpInstaller::seedConfig()` copia un `banippro_redirect` y un `banippro_url` antiguos, ligados a la tienda, a las claves globales cuando el valor global está vacío. Un `banippro_msg` antiguo no vacío se copia a cada idioma antes de usar las frases por defecto.

Los textos del back office pasan por `$this->l()` / `$this->module->l()`. Los archivos de traducción están en `translations/{iso}.php`. El mensaje de la página de bloqueo es el valor de configuración, no una clave de traducción. El asunto del correo `Ban IP Pro alert` es un literal en `BanIpAutoBan::alert()`. La ayuda de los campos es el `desc` de cada input de HelperForm en `banippro.php` y `AdminBanIpProController.php`.

Los valores automáticos de `reason` que escribe el módulo son `auto-login`, `auto-honeypot` y `auto-rate`. Los bloqueos por país registran `country` y no insertan una fila `ban`. `banip::importLines()` se detiene después de 5000 líneas no vacías que no son comentario. Las subidas de más de 2097152 bytes se rechazan. `BanIpMatcher` rechaza un valor vacío, una red `/0` y un comodín de cuatro asteriscos (`too_broad`). Un duplicado es una fila activa con la misma IP guardada y el mismo `rule_type`.

`BanIpAutoBan::ensureBan()` guarda siempre `apply_to` 1 e `id_shop` 0. `ensureAllow()` guarda `apply_to` 3 e `id_shop` 0.

### 6.8 Ampliación

El tema puede sustituir `views/templates/front/blocked.tpl`. El módulo llama a `$module->fetch('blocked.tpl')`. Las variables asignadas son `banippro_message`, `banippro_shop`, `banippro_logo`, `banippro_year`, `banippro_ip` y `banippro_lang`. Si el fetch falla, el guard imprime una página HTML mínima con el mismo mensaje y sigue terminando con estado 403.

No se pinta ninguna plantilla de producto, carrito o inicio. No hay un hook para que el tema añada un widget en la tienda. Las plantillas de administración están en `views/templates/admin/` y no forman parte del tema.

## 7. Ayuda

Página del módulo: [Ban IP pro](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html).

Inicie sesión en su cuenta de cliente en [mypresta.eu](https://mypresta.eu), abra el formulario de contacto y elija **Support for paid modules**. El formulario indica que para ese tema hace falta iniciar sesión. Después de entrar, elija este módulo en el historial de compras.

---
title: Contact page - spam protection PRO - documentación y manual de usuario
sidebar:
  label: Contact page - spam protection PRO - documentación y manual de usuario
description: Guía de configuración y de resolución de problemas para tiendas que ya tienen la protección antispam de la página de contacto.
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Contact page - spam protection PRO en MyPresta.eu](https://mypresta.eu/modules/administration-tools/contact-page-spam-protection-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/contact-page-spam-protection-pro/)
>
> ---


## 1. Requisitos

El módulo funciona en PrestaShop 1.7.7 hasta 9. PHP en la versión que exige esa versión de PrestaShop. Basta la página de contacto de la tienda. No hace falta otro módulo.

Una cuenta de Google reCAPTCHA solo hace falta si quiere la casilla o la puntuación invisible. Tras la instalación el interruptor de reCAPTCHA está activado, pero la comprobación sigue apagada hasta que guarde las dos claves.

Una cuenta de CleanTalk solo hace falta para la API de pago. La comprobación gratuita pasa por el proxy de MyPresta y no necesita cuenta de CleanTalk. CleanTalk gratuito necesita las funciones OpenSSL de PHP. Si no están, esa comprobación se omite y el mensaje se admite.

StopForumSpam es una consulta pública. La cuenta y la clave API son opcionales. La clave guardada no se usa en la consulta.

Las consultas usan cURL cuando PHP lo tiene. Sin cURL, StopForumSpam, CleanTalk y la comprobación de actualizaciones leen la dirección de forma directa si el servidor lo permite. La verificación de reCAPTCHA usa cURL cuando está disponible.

## 2. Instalación

Abra **Módulos** y luego **Gestor de módulos**. Suba el zip y pulse **Instalar**.

En el menú izquierdo aparece **Protección de contacto**. Al abrirla llega a la configuración. Debajo están **Intentos de envío de mensajes** y **Direcciones IP bloqueadas**.

La instalación no vacía la caché en un paso aparte.

Para apagarlo use el interruptor del gestor de módulos. La página de contacto deja de comprobarse. Los ajustes, los intentos y los bloqueos se quedan. Al volver a encenderlo se usan igual. Las entradas del menú quedan ocultas mientras el módulo está apagado.

Para quitarlo pulse **Desinstalar** y confirme **¿Seguro que quieres desinstalar este módulo?** La desinstalación quita las entradas del menú, los ajustes guardados y las dos listas. Los archivos se quedan en el servidor hasta que borre el módulo. Una instalación nueva empieza con listas vacías y los ajustes de una instalación limpia. Los intentos y los bloqueos antiguos no vuelven.

## 3. Configuración y trabajo diario

Las capturas de este capítulo son el back office en inglés. Los nombres de abajo son los del panel en español.

Abra **Protección de contacto**. Las pestañas son **Resumen**, **Antiflood**, **CleanTalk**, **StopForumSpam**, **reCAPTCHA**, **Filtros de mensajes**, **Lista blanca**, **Protección** y **Correo electrónico**. **Actualizaciones** está al final de la fila. **Guardar** en una pestaña la guarda y confirma **Configuración guardada.** La pestaña de actualizaciones confirma **Configuración de actualizaciones guardada.**

Mientras se cumpla la condición, una página de configuración puede mostrar:

**reCAPTCHA está activado, pero la clave del sitio o la clave secreta está vacía. El captcha permanece desactivado hasta que se guarden ambas claves.**

**La API de pago de CleanTalk está activada, pero la clave de acceso está vacía.**

El segundo aviso aparece cuando el interruptor de pago está activado y la clave está vacía. Tras una instalación limpia ese interruptor está apagado, así que el aviso no se ve hasta que active la API de pago sin clave.

Un mensaje se comprueba en este orden. Decide el primer acierto.

1. Una dirección de la lista blanca, y un cliente conectado cuando **Omitir comprobaciones para clientes conectados** está activado, sigue al formulario. El intento no se escribe en **Intentos de envío de mensajes**.
2. Si todas las comprobaciones están apagadas y la dirección no está en la lista de bloqueos, el mensaje sigue y no se registra. El interruptor de reCAPTCHA solo no cuenta como comprobación mientras las dos claves estén vacías.
3. Después: bloqueo activo, honeypot, tiempo mínimo, identificador de navegador vacío, antiflood, duplicado de un mensaje de al menos 20 caracteres, demasiados enlaces, palabra bloqueada, correo desechable, reCAPTCHA (solo con las dos claves guardadas), StopForumSpam, CleanTalk gratuito y CleanTalk de pago.
4. Si nada coincide, el intento se guarda como permitido y el formulario envía el mensaje.
5. Un bloqueo **Demasiado rápido** o **reCAPTCHA** solo detiene ese mensaje. No bloquea la dirección, no envía correo a la tienda y no redirige. Con reCAPTCHA el cliente ve **La verificación captcha ha fallado. Inténtalo de nuevo.** Si fue demasiado rápido ve **No se ha podido enviar tu mensaje. Inténtalo de nuevo dentro de unos minutos.**
6. Cualquier otro bloqueo puede bloquear la dirección, avisar a la tienda y redirigir, según las casillas de **Protección**. Si marca varias redirecciones, primero va la página de inicio, luego la página CMS y al final Google. Sin redirección el visitante se queda en la página de contacto y ve **No se ha podido enviar tu mensaje. Inténtalo de nuevo dentro de unos minutos.**

El antiflood cuenta cada intento de la ventana, también los ya bloqueados. Varios reintentos de captcha pueden llegar al límite de mensajes.

Un duplicado mira intentos anteriores con el mismo texto. Los intentos que solo fallaron por **Demasiado rápido** o **reCAPTCHA** no cuentan como copia anterior.

StopForumSpam y las dos comprobaciones de CleanTalk dejan pasar el mensaje si el servicio no responde. reCAPTCHA hace lo contrario: si Google no responde, el mensaje se bloquea.

### 3.1 Resumen

![Resumen](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-overview.webp)

El **Resumen** cuenta mensajes de contacto, mensajes bloqueados y bloqueos activos para las fechas de **Parámetros de análisis**. Un cliente que pasa cuenta como mensaje. Un visitante que no pasa una comprobación cuenta como bloqueado y aparece abajo con el motivo.

Las tarjetas son **Mensajes**, **Permitidos**, **Bloqueados**, **Tasa de bloqueo**, **Direcciones IP bloqueadas** y **Bloqueos activos**.

El gráfico **Bloqueados y permitidos** muestra **Diario** y **Semanal** cuando el período tiene más de 7 días. **Semanal** agrupa los días de siete en siete desde el inicio del período. El último grupo puede ser más corto. La leyenda es **Permitidos**, **Bloqueados** y **Total**. Si no hay filas, el gráfico dice **No hay mensajes en este período.**

**Bloqueos por motivo** muestra cuántos bloqueos produjo cada comprobación. Los nombres de esta página son **IP bloqueada**, **Honeypot**, **Demasiado rápido**, **User agent vacío**, **Antiflood**, **Mensaje duplicado**, **Demasiados enlaces**, **Palabra bloqueada**, **Correo desechable**, **reCAPTCHA**, **StopForumSpam** y **CleanTalk**. Un motivo vacío se muestra como **Desconocido**.

**Últimos mensajes bloqueados** tiene las columnas **Fecha**, **IP**, **Correo electrónico** y **Motivo**. Si no se bloqueó nada, la tabla dice **No se ha bloqueado nada en este período.**

Los botones **Intentos de envío de mensajes** y **Direcciones IP bloqueadas** abren esas listas.

Las insignias de color bajo el gráfico muestran qué comprobaciones están activas. **reCAPTCHA** solo está en verde cuando las dos claves están guardadas. El interruptor solo no pone esa insignia en verde. Tras la instalación están activos **Antiflood**, **Honeypot**, **Tiempo mínimo** y **Límite de enlaces**.

La línea bajo las insignias tiene la forma **Mensajes: 0 entre el 2026-10-13 y el 2026-11-11. Bloqueados: 0, permitidos: 0. Nuevos bloqueos en este período: 0.** Las fechas siguen el período elegido. Un período móvil termina hoy. Las fechas son la ventana actual de la tienda, no un valor fijo del módulo.

### 3.2 Parámetros de análisis

![Parámetros de análisis](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-overview-analytics.webp)

Abra el panel cerrado **Parámetros de análisis** en el **Resumen**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Período de estadísticas** | Últimos 30 días | **Últimos 7 días**, **Últimos 30 días**, **Últimos 90 días**, **Últimos 180 días**, **Últimos 365 días** o **Rango personalizado**. Las tarjetas, el gráfico y la última lista usan esta ventana. El inicio son los últimos 30 días. Los últimos 7 días muestran un pico corto y quitan bloqueos antiguos del gráfico. Los últimos 365 días cubren un año, así que un día intenso es un trozo pequeño. El rango personalizado usa **Desde** y **Hasta**. Las demás opciones ignoran esas fechas y siempre terminan hoy. |
| **Desde** | el inicio de la ventana actual | Fecha AAAA-MM-DD. Se usa cuando el **Período de estadísticas** es **Rango personalizado**. Una fecha posterior a **Hasta** se intercambia con **Hasta**. Un rango de más de 366 días se acorta por este lado. Una fecha futura vuelve a hoy. Una fecha vacía o no válida se sustituye por la de hace 30 días. Los períodos móviles ignoran este campo. |
| **Hasta** | hoy | Fecha AAAA-MM-DD. Se usa cuando el **Período de estadísticas** es **Rango personalizado**. Una fecha futura vuelve a hoy. Si **Hasta** es anterior a **Desde**, las fechas se intercambian. Una fecha vacía o no válida se sustituye por hoy. Los períodos móviles ignoran este campo y siempre terminan hoy. |

**Guardar** guarda el período. La página confirma **Configuración guardada.**

### 3.3 Antiflood

![Antiflood](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-antiflood.webp)

El antiflood cuenta cuántos mensajes de contacto envía una IP en la ventana de tiempo. Un cliente que escribe unas veces sigue pasando. El siguiente mensaje por encima del límite se rechaza, y **Protección** puede bloquear esa dirección si la casilla de bloqueo está marcada.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Activar antiflood** | Sí | Activado: cada IP se cuenta en la ventana y el siguiente mensaje por encima del límite se bloquea. Desactivado: un script puede seguir enviando desde la misma IP sin límite de esta comprobación. Un límite bajo también bloquea a un cliente que envía una corrección desde la misma oficina. Déjelo activado en una página de contacto pública. Apáguelo solo mientras envía mensajes de prueba desde una dirección. |
| **Ventana de tiempo** | 10 minutos | Minutos. Solo cuentan los mensajes de contacto de los últimos X minutos. 1 o 2 minutos pillan un pico y luego lo olvidan, así que un script lento puede seguir. 60 minutos o más también cuentan a un cliente que escribe, espera y vuelve a escribir desde la misma IP. Un 0 guardado se trata como 1. |
| **Mensajes permitidos** | 5 | Cuántos mensajes de contacto puede enviar una IP en la ventana. El siguiente se bloquea. 5 deja corregir un mensaje y enviarlo otra vez. 1 bloquea el segundo envío, así que para scripts y también a un cliente que pulsa enviar dos veces. Un valor alto, por ejemplo 20, deja pasar muchos mensajes. El contador incluye envíos anteriores de esa IP, también los bloqueados, así que varios reintentos de captcha pueden llegar al límite. Un 0 guardado se trata como 1. |

### 3.4 CleanTalk

![CleanTalk](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-cleantalk.webp)

CleanTalk comprueba la IP y el correo en una base de spam. Active la opción gratuita para usar el proxy de MyPresta sin cuenta de CleanTalk, o la de pago si tiene su propia clave. Una dirección desconocida se acepta. Una dirección ya denunciada como spam se rechaza. Si el servicio no responde, el mensaje se admite.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Activar CleanTalk gratuito** | No | Pregunta al proxy CleanTalk de MyPresta si esta IP o este correo ya constan como spam. No hace falta cuenta de CleanTalk. Desactivado omite la comprobación. Si el proxy no responde, o PHP no tiene el cifrado OpenSSL, el mensaje se admite. Un bot que no está en la base también pasa. Actívelo si no tiene clave de pago. |
| **Activar la API de pago de CleanTalk** | No | Usa la clave de acceso de su cuenta CleanTalk. Actívela después de pegar la clave. Déjela apagada si no tiene suscripción. Una clave vacía o rechazada no bloquea a nadie, así que el spam que solo pillaría esta comprobación se acepta. Una dirección de la lista se rechaza, y un cliente en la misma IP también puede rechazarse. |
| **Clave de acceso** | vacía | Pegue la clave de su cuenta CleanTalk, sin espacios de más. La comprobación de pago solo funciona si este campo tiene clave. Vacía, con el interruptor de pago activado, significa que no hay comprobación de pago, y la página muestra **La API de pago de CleanTalk está activada, pero la clave de acceso está vacía.** Una clave revocada se trata como comprobación fallida y el mensaje se admite. |
| **Umbral de tasa de spam** | 1 | Una puntuación de 0.0 a 1.0. Una tasa de spam de CleanTalk igual o superior a este valor se trata como spam. Una dirección que CleanTalk marca como presente en spam se bloquea con cualquier valor. 1 bloquea direcciones de las que CleanTalk está seguro. Un valor más bajo, por ejemplo 0.5, también bloquea resultados inciertos y puede parar a un cliente real en una IP compartida. Un 0 guardado se trata como 1, así que la comprobación sigue estricta. |

El enlace **Abrir la página de la cuenta de CleanTalk** abre la cuenta en una pestaña nueva.

### 3.5 StopForumSpam

![StopForumSpam](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-stopforumspam.webp)

StopForumSpam es una base gratuita de IP y correos denunciados por spam. La comprobación no necesita clave API. Un cliente que nunca fue denunciado se acepta. Una dirección con bastantes denuncias se rechaza. Si el servicio no responde, el mensaje se admite.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Activar StopForumSpam** | No | Se consultan la IP del visitante y el correo del formulario. Desactivado omite la comprobación. Si el servicio no responde, el mensaje se admite: un problema de red no bloquea clientes, y el spam que esta comprobación habría pillado también pasa. Déjelo activado en una página de contacto pública. |
| **Denuncias mínimas** | 1 | Bloquear cuando StopForumSpam ha registrado esta IP o este correo al menos tantas veces. Con 1, una sola denuncia bloquea la dirección, también a un cliente denunciado una vez por error. Con 5 o más, las direcciones con pocas denuncias pasan, así que llega más spam. Un 0 guardado se trata como 1. |
| **Clave API** | vacía | Opcional. La consulta pública funciona sin clave. Déjela vacía, o guarde una clave si ya tiene cuenta de StopForumSpam. El módulo sigue usando la consulta pública, así que una clave errónea no cambia a quién se bloquea. |

El enlace **Registrarse** abre el alta de StopForumSpam.

### 3.6 reCAPTCHA

![reCAPTCHA](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-recaptcha.webp)

Google reCAPTCHA funciona en el navegador, en la página de contacto. Úselo cuando los bots envían mensajes que parecen texto normal, y elija el mismo tipo que el de la clave en la consola de Google. v2 muestra una casilla. v3 puntúa la visita sin reto: una puntuación que pasa se acepta, y una que no pasa rechaza el mensaje sin bloquear la IP.

El texto **Cómo obtener la clave del sitio y la clave secreta** dice: cree la clave en la consola de Google y pegue abajo la clave del sitio y la clave secreta. El tipo elegido aquí tiene que ser el mismo que el de esa clave. Un tipo distinto hace fallar a todos los visitantes, también a un cliente real.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Activar reCAPTCHA** | Sí | La página de contacto exige pasar reCAPTCHA antes de aceptar el mensaje. Con claves vacías el captcha sigue apagado aunque este interruptor esté activado, y la página muestra **reCAPTCHA está activado, pero la clave del sitio o la clave secreta está vacía. El captcha permanece desactivado hasta que se guarden ambas claves.** Un cliente que falla puede volver a intentarlo. Ese fallo no bloquea la IP. |
| **Tipo de reCAPTCHA** | reCAPTCHA v2 | **reCAPTCHA v2** muestra una casilla. **reCAPTCHA v3** puntúa la visita en segundo plano y no muestra reto. Use el mismo tipo que el de la clave en la consola de Google. Un desajuste hace fallar cada envío, también el de clientes reales. v2 es más claro si quiere una comprobación visible. v3 se nota menos y usa el umbral de abajo. |
| **Clave del sitio** | vacía | La clave pública de la administración de Google reCAPTCHA para el dominio de esta tienda. Pegue la clave del sitio del tipo elegido arriba, sin espacios. Hacen falta las dos claves. Una clave del sitio vacía deja el captcha apagado. Una clave de otro dominio o de otro tipo hace fallar a los clientes reales. |
| **Clave secreta** | vacía | La clave secreta se queda en el servidor. No se envía al navegador. Use la clave secreta de la misma pareja que la clave del sitio. Una clave secreta vacía deja el captcha apagado. Una clave secreta de otro sitio hace que Google rechace cada visita, y los clientes no pueden enviar el formulario. |
| **Tema de v2** | Claro | Color **Claro** u **Oscuro** de la casilla v2. Claro en una página de contacto blanca, Oscuro en una oscura. v3 ignora este ajuste y usa la insignia estándar de Google. El tema no cambia a quién se bloquea. Un widget oscuro en una página blanca se ve peor, así que más gente se salta la casilla y el mensaje se rechaza. |
| **Umbral de puntuación de v3** | 0.5 | Una puntuación de 0.0 a 1.0. Se usa cuando el tipo es v3. Google puntúa la visita y una puntuación por debajo de este valor se rechaza. El inicio es 0.5. Un valor más alto, por ejemplo 0.9, es más estricto y puede rechazar clientes de una red compartida o poco habitual. Un valor más bajo, por ejemplo 0.1, deja pasar más visitas automáticas. Un rechazo no bloquea la IP. Si falta el valor guardado, se usa 0.5. |

### 3.7 Filtros de mensajes

![Filtros de mensajes, primeros campos](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-filters.webp)

![Filtros de mensajes, campos siguientes](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-filters-content.webp)

Los filtros corren en la tienda, antes de cualquier servicio externo. En una página de contacto pública deje el honeypot y el tiempo mínimo, y añada enlaces, palabras, correos desechables o duplicados cuando la lista de bloqueos muestre un patrón que se repite. Un cliente que rellena el formulario de forma normal se acepta. Un script se rechaza. Un captcha fallido o un envío demasiado rápido no bloquean la IP. Los otros filtros pueden bloquearla si la casilla de bloqueo está marcada en **Protección**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Campo honeypot** | Sí | Añade un campo oculto que las personas no ven. El cliente lo deja vacío y el mensaje sigue. Un script que rellena todos los campos se bloquea, y **Protección** puede bloquear esa IP. Apáguelo si un autocompletado rellena el campo oculto y bloquea a sus clientes. |
| **Tiempo mínimo en la página** | Sí | Bloquea un envío más rápido que el límite desde que arranca el script de la página. Un cliente que lee y escribe necesita más de unos segundos. Un script que envía al momento se bloquea. La falta del contador se acepta, así que un navegador sin JavaScript todavía puede enviar. Este bloqueo no bloquea la IP. Apagado deja pasar los envíos inmediatos por esta comprobación. |
| **Segundos mínimos** | 3 | Segundos. Se usa cuando el tiempo mínimo está activado. 1 segundo sigue pillando un script inmediato y rara vez toca a un cliente. 15 segundos o más bloquean a un cliente que ya conoce el texto y envía rápido. El contador empieza cuando corre el script de la página. Un 0 guardado se trata como 1. |
| **Limitar enlaces en el mensaje** | Sí | Cuenta http://, https:// y www. en el mensaje. Activado cuando el spam que recibe son sobre todo enlaces. Desactivado cuando los clientes suelen pegar una dirección de producto. Desactivado acepta un mensaje lleno de enlaces. Activado, con un máximo bajo, también bloquea a un cliente que pega varias direcciones. |
| **Máximo de enlaces** | 3 | Un mensaje con más enlaces se bloquea. Solo se cuenta si el límite de enlaces está activado. 3 deja pegar unas pocas direcciones. 0 bloquea cada mensaje que contiene un enlace, incluso a una página de producto. Un valor alto, por ejemplo 20, deja pasar un spam de enlaces típico. |
| **Palabras bloqueadas** | No | Búsqueda sin distinguir mayúsculas en el correo y en el mensaje. Actívelo después de añadir frases que haya visto en el spam. Apagado, o activado con la lista vacía, no bloquea nada. Una palabra corta y corriente también bloquea a un cliente real que la usó. |
| **Palabras y frases** | vacío | Una palabra o frase por línea. Se usa cuando las palabras bloqueadas están activadas. Déjelo vacío hasta que copie frases de spam real. Una frase coincide en cualquier sitio del correo o del mensaje, así que un trozo corto como win también coincide con window y bloquea una pregunta normal. Una frase larga y concreta solo bloquea ese texto. |
| **Bloquear correos desechables** | No | Bloquea una lista integrada de dominios de buzones temporales y los dominios de abajo. Activado cuando no quiere mensajes de buzones desechables. Una dirección normal se acepta. Un buzón temporal de la lista se bloquea, y **Protección** puede bloquear esa IP. Los dominios que no están en la lista siguen pasando hasta que los añada. Desactivado acepta cualquier dominio. |
| **Dominios desechables adicionales** | vacío | Un dominio por línea, por ejemplo dropmail.test. Se usa cuando los correos desechables están bloqueados. Déjelo vacío hasta que un dominio aparezca en la lista de intentos. Un dominio escrito aquí también bloquea sus subdominios. No escriba @. Escribir un proveedor de correo real bloquea a cada cliente que lo usa. |
| **Bloquear mensajes duplicados** | No | Bloquea el mismo texto enviado otra vez en la ventana, desde cualquier IP. Activado cuando el mismo anuncio sale de muchas direcciones. Los mensajes de menos de 20 caracteres se saltan, así que un saludo corto se puede enviar otra vez. Un reintento de captcha no se trata como duplicado. Un cliente que envía la misma pregunta larga dos veces en la ventana se bloquea la segunda. Desactivado permite volver a enviar el mismo texto. |
| **Ventana de duplicados** | 60 minutos | Cuánto tiempo se recuerda el texto. Una ventana corta, por ejemplo 5 minutos, olvida el texto pronto, así que el mismo spam puede volver. Una ventana larga, por ejemplo 1440 minutos (un día), también bloquea a un cliente que envía la misma pregunta más tarde el mismo día. Solo se usa cuando el bloqueo de duplicados está activado. Un 0 guardado se trata como 1. |
| **Bloquear un user agent vacío** | No | Bloquea una petición que no envía identificador de navegador. Déjelo apagado salvo que los intentos muestren spam con identificador vacío. Los navegadores reales lo envían. Activado también bloquea herramientas de privacidad que quitan el identificador, así que esos clientes no pueden enviar. Desactivado ignora un identificador vacío. |
| **Omitir comprobaciones para clientes conectados** | No | Un cliente conectado se salta todas las comprobaciones, también un bloqueo activo. Déjelo apagado en una tienda donde cualquiera puede registrarse. Actívelo si sus clientes tienen cuentas de confianza. Los invitados se siguen comprobando. Activado deja pasar a un bot conectado. Desactivado comprueba a los clientes conectados igual que a los invitados, así que una IP de oficina bloqueada sigue bloqueada también para una cuenta. |

### 3.8 Lista blanca

![Lista blanca](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-whitelist.webp)

La lista blanca son las IP que se saltan todas las comprobaciones, también un bloqueo activo. Añada su oficina, una agencia o una herramienta de vigilancia que envía un mensaje de prueba. Los demás se siguen comprobando. Una lista vacía significa que ninguna dirección se salta nada. Una línea añadida por error deja pasar esa dirección, también a un bot que la usa.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Direcciones IP** | vacío | Una dirección por línea. Una línea que termina en * coincide con el inicio de la dirección, por ejemplo 192.168.1.*. Déjelo vacío salvo que una dirección tenga que poder escribir siempre, como su oficina. Una dirección completa se salta las comprobaciones solo para esa IP. Un prefijo con asterisco se salta todo el rango, incluido cada bot de ese rango. Una errata no coincide con nada, así que ese visitante sigue protegido. Compare IPv4 e IPv6 exactamente como los muestra la tienda. |

### 3.9 Protección

![Protección](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-protection.webp)

Una comprobación fallida siempre rechaza el mensaje. Las casillas de **Qué hacer con el spam** son pasos extra para un bloqueo, el honeypot, el flood, los filtros, StopForumSpam y CleanTalk. No se ejecutan cuando el único problema es el captcha o un envío demasiado rápido. Un cliente que pasa las comprobaciones no se ve afectado.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Acciones adicionales** | ninguna marcada | **Bloquear la dirección IP**: actívela cuando la misma dirección vuelve. El siguiente mensaje de esa IP se rechaza hasta que apague el bloqueo. Una IP de oficina compartida bloquea entonces a cada cliente que la usa. **Avisar a la tienda por correo**: actívela si quiere un aviso en el buzón. Un correo por IP y luego silencio durante 30 minutos. Apagada deja el spam bloqueado solo en la lista de intentos. **Redirigir a la página de inicio**, **Redirigir a una página CMS** y **Redirigir a Google**: déjelas apagadas para que el visitante se quede en la página de contacto y lea el error. Si marca varias, primero va la página de inicio, luego la CMS y luego Google. |
| **Página CMS** | la primera página de la lista de la tienda | Se usa cuando está marcada **Redirigir a una página CMS**. Elija una página corta que diga que el mensaje no se envió. Si la tienda no tiene páginas CMS, la lista contiene **Sin página CMS**. Sin página elegida, la redirección CMS se omite. Si también está marcada **Redirigir a Google**, después se usa Google. Si no, el visitante se queda en la página de contacto con el error. Un cliente que pasa las comprobaciones no ve esta página por el módulo. Las páginas de la lista son las páginas CMS de la tienda. Si la tienda ya tiene páginas, la elección vacía guardada no está en la lista, así que se muestra la primera. Pulse **Guardar** solo cuando esa sea la página que quiere. |

### 3.10 Correo electrónico

![Correo electrónico](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-mail.webp)

El panel **Correo a la tienda** fija el asunto del correo que se envía a la dirección de la tienda cuando se bloquea un mensaje. El correo solo sale si **Avisar a la tienda por correo** está marcado en **Protección**, y solo para bloqueos que no sean un captcha fallido o un envío demasiado rápido. Se envía un correo en el primer bloqueo de una IP. Los siguientes bloqueos de esa IP durante 30 minutos no envían correo. Un cliente aceptado no dispara este correo. Si el correo de la tienda en Parámetros de la tienda está vacío, no se envía nada.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Asunto** | Contact form spam blocked | Asunto del aviso a la tienda. Al final se añade el nombre corto de la comprobación, por ejemplo [flood]. El mensaje va al correo de la tienda de Parámetros de la tienda. Use un asunto corto que reconozcan las reglas del buzón, rellenado para cada idioma de la tienda. Un asunto vacío se sustituye por Contact form spam blocked. El asunto no cambia a quién se bloquea. |

El botón de idioma cambia el asunto a otro idioma de la tienda. El cuerpo del correo es la plantilla del módulo para ese idioma. El texto en inglés empieza por **Contact form blocked.** y luego indica la comprobación, la IP, el correo, la fecha y el inicio del mensaje.

### 3.11 Actualizaciones

![Actualizaciones](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-updates.webp)

Esta página pregunta a MyPresta.eu si hay una versión más nueva del módulo. Los ajustes de aquí solo afectan a la comprobación de actualizaciones. No cambian la protección de la página de contacto.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Buscar actualizaciones** | — | **Comprobar ahora** pregunta al momento a MyPresta.eu si hay una versión más nueva. Úselo después de instalar y otra vez antes de un período de mucho tráfico. El botón no descarga ni instala un archivo. Si el servidor de la tienda no llega a MyPresta.eu, el clic no muestra una versión nueva. |
| **Notificaciones de actualizaciones** | Activar | **Activar** consulta MyPresta.eu y muestra un aviso en el back office cuando se publica una versión más nueva. La comprobación automática va más o menos cada 3 días mientras trabaja en el back office. **Desactivar** para esa comprobación y el aviso. Una versión nueva pasa entonces desapercibida hasta que pulse **Comprobar ahora**. Esta elección no cambia la protección del formulario. |
| **Página del módulo** | Contact page - spam protection PRO | Un enlace directo a la página del módulo en MyPresta.eu. El historial de cambios de esa página muestra qué cambió. Ábrala antes de actualizar. El enlace no instala un archivo. Si la página no carga, abra la dirección en una pestaña nueva. |

**Guardar** confirma **Configuración de actualizaciones guardada.**

Cuando hay una versión más nueva, el back office puede mostrar **Nueva versión disponible, consulta http://MyPresta.eu para más información** y **Más detalles en el registro de cambios**. **Comprobar ahora** responde **¡Nueva versión disponible!** o **¡El módulo está actualizado!**

### 3.12 Intentos de envío de mensajes

![Intentos de envío de mensajes](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-attempts.webp)

Abra **Intentos de envío de mensajes** bajo **Protección de contacto**, o el botón del mismo nombre en el **Resumen**.

La tienda escribe una fila cuando se comprueba un mensaje de contacto. No hay botón de añadir. Desde esta lista no se edita una fila. Puede borrar una fila.

Las columnas son **ID**, **IP**, **Correo electrónico**, **Motivo**, **Bloqueados** y **Fecha**. La fila más nueva va primero. Una lista vacía dice en la captura en inglés **No records found**.

**Motivo** en esta lista es el nombre corto, no el nombre largo del **Resumen**:

| En el resumen | En esta lista |
|---|---|
| **IP bloqueada** | ban |
| **Honeypot** | honeypot |
| **Demasiado rápido** | timing |
| **User agent vacío** | user-agent |
| **Antiflood** | flood |
| **Mensaje duplicado** | duplicate |
| **Demasiados enlaces** | links |
| **Palabra bloqueada** | keyword |
| **Correo desechable** | disposable |
| **reCAPTCHA** | recaptcha |
| **StopForumSpam** | stopforumspam |
| **CleanTalk** | cleantalk |

Un mensaje permitido tiene el motivo vacío y **Bloqueados** en no.

La acción de fila es borrar. Marque filas y use **Eliminar seleccionados**. La tienda pregunta **¿Eliminar los elementos seleccionados?**

### 3.13 Direcciones IP bloqueadas

![Direcciones IP bloqueadas](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-bans.webp)

Abra **Direcciones IP bloqueadas** bajo **Protección de contacto**, o el botón del mismo nombre en el **Resumen**.

Las columnas son **ID**, **IP**, **Fecha** y **Activo**. La fila más nueva va primero. Una lista vacía dice en la captura en inglés **No records found**.

El signo más abre el alta. El título del formulario es **Dirección IP bloqueada**.

![Nueva dirección IP bloqueada](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-ban-form.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Dirección IP** | vacía | Una dirección IP. Obligatoria. Mientras el bloqueo está activo, los mensajes de contacto de esta IP se rechazan. Pegue la dirección de la lista de intentos, exactamente como se registró. Un dígito mal puesto bloquea a otro visitante, o a nadie. Una dirección de oficina compartida también bloquea a clientes reales de esa IP hasta que apague el bloqueo. |
| **Activo** | No | **Sí** mantiene el bloqueo y el formulario rechaza esta IP. **No** conserva la fila y deja de bloquear, así que la dirección puede volver a escribir salvo que la pare otra comprobación. Elija **Sí** mientras esa dirección siga enviando spam. Elija **No** cuando un cliente de esa IP tenga que pasar y quiera conservar el registro. Un bloqueo creado desde **Protección** se guarda ya activo. |

**Guardar** guarda la fila. Cancelar vuelve a la lista sin guardar.

En una fila existente, **Editar** abre el mismo formulario, borrar quita la fila y el icono **Activo** enciende o apaga el bloqueo. Marque filas y use **Eliminar seleccionados**. La tienda pregunta **¿Eliminar los elementos seleccionados?**

Un bloqueo de **Protección** rechaza el siguiente mensaje de contacto de esa IP con el motivo **IP bloqueada** (nombre corto ban) y no crea un segundo bloqueo para el mismo acierto.

## 4. Tienda

El módulo solo actúa en la página de contacto de la tienda. En otras páginas no añade nada.

Con los ajustes de la instalación, antes de guardar las dos claves de reCAPTCHA, el cliente ve el formulario de contacto normal del tema. En la página no hay nada extra que capturar: el honeypot está fuera de la pantalla, el contador está oculto y la casilla de reCAPTCHA no se muestra.

Cuando guarde las dos claves y deje **Activar reCAPTCHA** en Sí:

- **reCAPTCHA v2** añade la casilla. Si el cliente envía sin marcarla, la página dice **Confirma que no eres un robot.** y el formulario no sale.
- **reCAPTCHA v3** no muestra reto. Puede aparecer la insignia de Google. Una puntuación por debajo del umbral se rechaza en el servidor.

| Qué ha pasado | Qué ve el cliente |
|---|---|
| Casilla v2 sin marcar | **Confirma que no eres un robot.** El formulario se queda en la página. |
| El captcha falló, o Google no respondió | **La verificación captcha ha fallado. Inténtalo de nuevo.** |
| Cualquier otro bloqueo, y ninguna redirección marcada | **No se ha podido enviar tu mensaje. Inténtalo de nuevo dentro de unos minutos.** |
| Redirección a la página de inicio marcada | La página de inicio de la tienda. No hay error en la página de contacto. |
| Redirección CMS marcada, con página elegida, y la de inicio no | Esa página CMS. |
| Redirección a Google marcada, y las otras no se usan | https://www.google.com |

Un mensaje que pasa lo envía el formulario de contacto como siempre. El módulo no cambia esa confirmación.

El tema puede sustituir la hoja de estilo y el script de la tienda. No puede sustituir una plantilla de módulo del formulario, porque el formulario es el de contacto de la tienda. Si el tema quita el botón de envío de ese formulario, el honeypot, el contador y el captcha no se enganchan.

## 5. Problemas

**El cliente ve «Confirma que no eres un robot.»**

La casilla v2 no estaba marcada. Pídale que la marque y envíe otra vez. Esto no bloquea la IP.

**El cliente ve «La verificación captcha ha fallado. Inténtalo de nuevo.»**

El captcha no pasó, o la tienda no llegó a Google. Compruebe que el **Tipo de reCAPTCHA** coincide con la clave de la consola de Google, que **Clave del sitio** y **Clave secreta** son la pareja de este dominio y que el servidor de la tienda llega a Google. Un captcha fallido no bloquea la IP. El cliente puede volver a intentarlo.

**El cliente ve «No se ha podido enviar tu mensaje. Inténtalo de nuevo dentro de unos minutos.»**

Otra comprobación rechazó el mensaje y no hay redirección marcada. Abra **Intentos de envío de mensajes**, busque la IP o el correo y lea **Motivo**. Después:

- flood: suba **Mensajes permitidos** o **Ventana de tiempo**, o espere a que pase la ventana.
- honeypot: un script o el autocompletado rellenó el campo oculto. Apague **Campo honeypot** si se bloquea a sus propios clientes.
- timing: el formulario salió antes de **Segundos mínimos**. Suba ese número solo si se bloquea a clientes reales. Este bloqueo no bloquea la IP.
- user-agent: apague **Bloquear un user agent vacío** si interviene una herramienta de privacidad.
- duplicate: el mismo texto de al menos 20 caracteres se envió otra vez dentro de **Ventana de duplicados**.
- links: el mensaje tiene más enlaces que **Máximo de enlaces**.
- keyword: una línea de **Palabras y frases** coincide con el correo o el mensaje.
- disposable: el dominio del correo está en la lista integrada o en **Dominios desechables adicionales**.
- stopforumspam o cleantalk: la dirección está en ese servicio. Suba **Denuncias mínimas** o **Umbral de tasa de spam**, o añada la dirección a la **Lista blanca** si es un cliente.
- ban: la dirección está en **Direcciones IP bloqueadas** con **Activo** en **Sí**. Póngalo en **No** o borre la fila.

**El cliente acaba en la página de inicio, en una página CMS o en Google.**

Hubo un bloqueo duro y en **Protección** hay una redirección marcada. Desmarque **Redirigir a la página de inicio**, **Redirigir a una página CMS** y **Redirigir a Google** si quiere que el error se quede en la página de contacto. Si hay varias, gana la página de inicio, luego la CMS y luego Google.

**Toda una oficina no puede escribir.**

La oficina comparte una IP. Esa IP está bloqueada, ha pasado el límite de antiflood o está en un servicio. Abra **Direcciones IP bloqueadas** y ponga **Activo** en **No**, o añada la dirección a la **Lista blanca**. Una línea de la lista blanca se salta todas las comprobaciones, también el bloqueo.

**reCAPTCHA sigue apagado.**

El aviso dice **reCAPTCHA está activado, pero la clave del sitio o la clave secreta está vacía. El captcha permanece desactivado hasta que se guarden ambas claves.** Pegue las dos claves y pulse **Guardar**.

**CleanTalk de pago no bloquea a nadie.**

El aviso dice **La API de pago de CleanTalk está activada, pero la clave de acceso está vacía.** Pegue **Clave de acceso** y pulse **Guardar**. Una clave rechazada también deja pasar el mensaje. Si el servicio no responde, el mensaje se admite.

**No llega correo a la tienda.**

**Avisar a la tienda por correo** tiene que estar marcado. El bloqueo tiene que ser algo distinto del captcha o de demasiado rápido. La misma IP solo envía un correo cada 30 minutos. El correo de la tienda en Parámetros de la tienda tiene que estar relleno. El asunto recibe el nombre corto de la comprobación, por ejemplo [flood].

**Comprobar ahora no muestra nada nuevo.**

El servidor de la tienda no llegó a MyPresta.eu, o el módulo ya está al día. La respuesta **¡El módulo está actualizado!** significa que no se informó de una versión más nueva. **Comprobar ahora** no descarga el archivo.

**Las listas están vacías después de instalar otra vez.**

La desinstalación borra los intentos y los bloqueos. Una instalación nueva no los devuelve.

## 6. Para desarrolladores

### 6.1 Visión general

Clase principal `mycontactprotectionpro`, versión `1.0.0`, autor MyPresta.eu, pestaña `administration`. El nombre en la lista es **Contact page - spam protection PRO**. La compatibilidad del archivo es PrestaShop 1.7.7.0 hasta 9.99.99.

Los ajustes se leen con `Configuration::get` en el contexto de tienda activo al pulsar **Guardar**. Un POST de la página de contacto con `submitMessage` ejecuta `hookActionFrontControllerInitAfter`. Un pase escribe una fila permitida y deja enviar el formulario. Un bloqueo escribe una fila bloqueada, y un motivo duro puede crear un bloqueo, enviar el correo a la tienda y redirigir.

`install()` llama a la instalación padre, escribe la configuración, crea las dos tablas, crea el menú y registra los tres hooks. No vacía la caché. No hay `enable()` ni `disable()` propios. `uninstall()` borra las claves de 6.7 más `update_mycontactprotectionpro` y `updatev_mycontactprotectionpro`, borra las pestañas del menú, hace DROP de las dos tablas y llama a la desinstalación padre. No borra `mypresta_updates`. Los archivos se quedan hasta que se quite el directorio del módulo.

### 6.2 Archivos

| Archivo | Función |
|---|---|
| mycontactprotectionpro.php | install, uninstall, hooks, formularios, orden de comprobación, panel, correo a la tienda |
| controllers/admin/AdminMycontactprotectionpro.php | padre del menú; redirige a la configuración del módulo |
| controllers/admin/AdminMycontactprotectionproAttempts.php | lista de intentos y borrado |
| controllers/admin/AdminMycontactprotectionproBans.php | lista de bloqueos, alta, edición, borrado, interruptor active |
| models/attempt.php | tabla de intentos y contadores |
| models/ban.php | tabla de bloqueos y `banIp()` |
| lib/sfs.php | consulta StopForumSpam |
| lib/ctalk.php | CleanTalk gratuito y de pago |
| lib/updatesChecker.php | comprobación de actualizaciones, clase `mycontactprotectionproUpdate` |
| lib/recaptcha/ | biblioteca reCAPTCHA que usa el módulo |
| views/templates/admin/configure.tpl | barra de pestañas y marcado del resumen |
| views/css/admin.css | disposición de la configuración en el back office |
| views/css/front.css | coloca el honeypot fuera de la pantalla |
| views/js/front.js | honeypot, contador, casilla v2 y token v3 en el formulario |
| mails/{iso}/mcpp_merchant.html | cuerpo HTML del aviso; no pasa por `$this->l()` |
| mails/{iso}/mcpp_merchant.txt | cuerpo de texto del aviso |
| translations/{iso}.php | textos del back office y del cliente |
| key.php | valor enviado con la consulta gratuita de CleanTalk |

No hay controlador de tienda ni plantilla de tienda para el formulario de contacto.

### 6.3 Controladores

| Clase | Padre en el menú | Qué acepta |
|---|---|---|
| AdminMycontactprotectionproController | id 0, icono security, título Contact protection | redirige a AdminModules con `configure=mycontactprotectionpro` |
| AdminMycontactprotectionproAttemptsController | AdminMycontactprotectionpro | tabla `mcpp_attempt`, orden `id_mcpp_attempt` DESC, `list_no_link`, borrar fila, borrado masivo. Sin alta. |
| AdminMycontactprotectionproBansController | AdminMycontactprotectionpro | tabla `mcpp_ban`, orden `id_mcpp_ban` DESC, editar y borrar fila, borrado masivo, estado en `active`. Formulario: `ip` (obligatorio) y `active`. |

La configuración es `getContent()` del módulo, no un controlador aparte. La pestaña va en `mcpp_tab`. Los nombres de envío son `submitMcppAntiFlood`, `submitMcppCleanTalk`, `submitMcppStopForumSpam`, `submitMcppRecaptcha`, `submitMcppFilters`, `submitMcppWhitelist`, `submitMcppProtection`, `submitMcppMail`. El formulario de actualizaciones envía `submit_settings_updates` y `submit_settings_updates_now`.

No hay controlador de tienda. La página de contacto es el `ContactController` de la tienda.

### 6.4 Hooks

| Hook | Cuándo se ejecuta |
|---|---|
| actionFrontControllerSetMedia | en la página de contacto, cuando el honeypot, el contador o un reCAPTCHA listo están activos; añade front.css y front.js y pasa al script los ajustes públicos |
| actionFrontControllerInitAfter | en un POST de la página de contacto con submitMessage; comprueba y vuelve, detiene el formulario o redirige |
| displayBackOfficeHeader | añade views/css/admin.css |

El módulo no registra un hook de visualización propio. La página de contacto se reconoce por `php_self` igual a `contact`, o por la clase `ContactController` o `ContactControllerCore`.

En el back office el constructor llama a `runUpdateSetUp()`. Ese método consulta MyPresta más o menos cada 259200 segundos cuando `mypresta_updates` no es 0, guarda el resultado en `updatev_mycontactprotectionpro` y añade un aviso del controlador cuando la versión guardada es más nueva.

### 6.5 Sobrescrituras

El módulo no trae sobrescritura de clases ni de controladores.

### 6.6 Base de datos

El prefijo es el de la tienda. Abrir una página no añade columnas. La desinstalación borra las dos tablas.

| Tabla | Contenido |
|---|---|
| mcpp_attempt | `id_mcpp_attempt` int clave primaria, `ip` varchar 64, `email` varchar 255, `message_hash` varchar 64 (MD5 del mensaje en minúsculas), `reason` varchar 255 (nombre corto, vacío si se admitió), `blocked` tinyint, `date_add` datetime. Claves `ip_date` (`ip`, `date_add`) y `hash_date` (`message_hash`, `date_add`). |
| mcpp_ban | `id_mcpp_ban` int clave primaria, `ip` varchar 64, `date_add` datetime, `active` tinyint por defecto 1. Clave `ip_active` (`ip`, `active`). El formulario de alta abre con Activo en No. `banIp()` inserta o actualiza la fila con `active` 1. |

### 6.7 Claves y traducciones

Valor cuando falta la clave:

| Clave | Si falta |
|---|---|
| mcpp_af | 1 |
| mcpp_time | 10 |
| mcpp_atmpt | 5 |
| mcpp_ct | 0 |
| mcpp_ct_paid | 0 |
| mcpp_ct_key | vacío |
| mcpp_ct_rate | 1, y un 0 guardado también se trata como 1 |
| mcpp_sfs | 0 |
| mcpp_sfs_key | vacío |
| mcpp_sfs_freq | 1, y un 0 guardado también se trata como 1 |
| mcpp_rc | 1 |
| mcpp_rc_type | 0, que es v2; 1 es v3 |
| mcpp_rc_site | vacío |
| mcpp_rc_secret | vacío |
| mcpp_rc_theme | light, salvo que el valor guardado sea dark |
| mcpp_rc_score | 0.5 |
| mcpp_hp | 1 |
| mcpp_tg | 1 |
| mcpp_tg_sec | 3, y un 0 guardado se trata como 1 |
| mcpp_links | 1 |
| mcpp_links_max | 3 |
| mcpp_kw | 0 |
| mcpp_kw_list | vacío |
| mcpp_disp | 0 |
| mcpp_disp_extra | vacío |
| mcpp_dup | 0 |
| mcpp_dup_min | 60, y un 0 guardado se trata como 1 |
| mcpp_ua | 0 |
| mcpp_bypass | 0 |
| mcpp_ptype_1 | 0, bloquear la IP |
| mcpp_ptype_4 | 0, correo a la tienda |
| mcpp_ptype_7 | 0, redirección a la página de inicio |
| mcpp_ptype_6 | 0, redirección CMS |
| mcpp_ptype_5 | 0, redirección a Google |
| mcpp_cms | 0 |
| mcpp_wh_ip | vacío |
| mcpp_mtitle | Contact form spam blocked, por idioma; un asunto vacío usa esta frase en inglés |
| mcpp_dash_preset | 30; cualquier valor distinto de 7, 30, 90, 180, 365 o custom vuelve a 30 |
| mcpp_dash_from | vacío hasta que el resumen construye la ventana |
| mcpp_dash_to | vacío hasta que el resumen construye la ventana |

`mypresta_updates` es compartido. Si falta, las notificaciones se tratan como activadas. La desinstalación no lo borra. `key.php` asigna `mkey`. Si está vacío, la consulta gratuita de CleanTalk usa `nlc`. La comprobación de actualizaciones usa `nokey` cuando falta el valor.

Dominios desechables integrados, coinciden en el dominio y sus subdominios: mailinator.com, guerrillamail.com, guerrillamail.info, guerrillamail.biz, guerrillamail.de, guerrillamail.net, guerrillamail.org, guerrillamailblock.com, sharklasers.com, grr.la, yopmail.com, yopmail.fr, yopmail.net, trashmail.com, trashmail.de, trash-mail.com, tempmail.com, temp-mail.org, 10minutemail.com, 10minutemail.net, throwawaymail.com, getnada.com, dispostable.com, maildrop.cc, fakeinbox.com, mailnesia.com, mohmal.com, emailondeck.com, tempail.com, moakt.com, spam4.me, byom.de, mintemail.com, mytemp.email, tmpmail.net, tmpmail.org, discard.email, discardmail.com, inboxkitten.com, getairmail.com, generator.email, mailcatch.com. Los dominios de `mcpp_disp_extra` se añaden igual.

Las etiquetas, las descripciones de campos y las tres frases del cliente son `$this->l()` en `mycontactprotectionpro.php`, `lib/updatesChecker.php` (fuente `updatesChecker`), `AdminMycontactprotectionproAttempts.php` (fuente `AdminMycontactprotectionproAttempts`) y `AdminMycontactprotectionproBans.php` (fuente `AdminMycontactprotectionproBans`). Añada un idioma con `translations/{iso}.php`. Las descripciones de campos están en el `desc` de cada campo HelperForm de la clase principal y del controlador de bloqueos.

Los cuerpos de `mails/{iso}/mcpp_merchant.html` y `mails/{iso}/mcpp_merchant.txt` no pasan por `$this->l()`. El texto en inglés empieza por `Contact form blocked.` El asunto es `mcpp_mtitle` del idioma del correo, con el motivo corto añadido, por ejemplo ` [flood]`. El correo va a `PS_SHOP_EMAIL`. Un correo de tienda vacío no envía nada. En el cuerpo van los primeros 500 caracteres del mensaje sin etiquetas.

### 6.8 Ampliación

Un tema puede sobrescribir `views/css/front.css` y `views/js/front.js`. No hay plantilla de tienda para el formulario, así que el tema no tiene una plantilla de formulario del módulo que sobrescribir. El marcado es el formulario de contacto de la tienda. `front.js` busca `form [name=submitMessage]`. Si falta ese botón, el script vuelve y no añade nada.

El nombre del honeypot es `mcpp_website`. El nombre del contador es `mcpp_ts`. Un honeypot relleno es un acierto. La falta del contador no es un acierto. Un contador en el futuro es un acierto. reCAPTCHA v3 usa la acción `contact`.

El orden de comprobación es fijo: ban, honeypot, timing, user agent vacío, flood, duplicate, links, keyword, disposable, recaptcha, stopforumspam, CleanTalk gratuito, CleanTalk de pago. Gana el primer acierto. La lista blanca y la excepción del cliente conectado vuelven antes de escribir una fila. Si `protectionEnabled()` es falso y la IP no está bloqueada, el hook vuelve sin escribir. `protectionEnabled()` es verdadero cuando cualquiera de `mcpp_af`, `mcpp_ct`, `mcpp_ct_paid`, `mcpp_sfs`, `mcpp_hp`, `mcpp_tg`, `mcpp_links`, `mcpp_kw`, `mcpp_disp`, `mcpp_dup`, `mcpp_ua` es 1, o cuando reCAPTCHA está listo (interruptor activado y las dos claves no vacías).

Los motivos duros son todos menos `timing` y `recaptcha`. Solo un motivo duro puede crear un bloqueo, enviar el correo a la tienda y redirigir. La prioridad de redirección es `mcpp_ptype_7` (página de inicio), luego `mcpp_ptype_6` cuando `mcpp_cms` es mayor que 0, luego `mcpp_ptype_5` (`https://www.google.com`). Si no, el módulo quita `submitMessage` y añade el error. Un bloqueo recaptcha usa la frase del captcha. Cualquier otro bloqueo que se queda en la página usa la frase de unos minutos.

CleanTalk gratuito se omite si no existe `openssl_encrypt`. StopForumSpam y CleanTalk admiten el mensaje si la llamada remota falla. reCAPTCHA bloquea el mensaje si la llamada remota falla. Flood usa `countByIpSince`, que cuenta cada intento de la ventana. Duplicate usa `countDuplicateSince`, que ignora filas cuyo motivo es `timing` o `recaptcha`, y solo corre cuando el mensaje tiene al menos 20 caracteres.

Llamadas PHP: `curl_init` si existe, si no `file_get_contents` para StopForumSpam, CleanTalk y la comprobación de actualizaciones cuando `allow_url_fopen` está activo. `openssl_encrypt` para la consulta gratuita de CleanTalk. `json_decode` para las respuestas de StopForumSpam, CleanTalk de pago y reCAPTCHA. No hace falta otro módulo.

## 7. Ayuda

Página del módulo: https://mypresta.eu/modules/administration-tools/contact-page-spam-protection-pro.html

Para preguntar por este módulo, inicie sesión en la cuenta de cliente de [https://mypresta.eu/](https://mypresta.eu/) y abra el formulario de contacto. Elija el tema **Support for paid modules**. El formulario indica que el inicio de sesión es obligatorio. Después elija este módulo en el historial de compras. La página es [https://mypresta.eu/contact-form](https://mypresta.eu/contact-form).

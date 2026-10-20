---
title: "Cupón de Cumpleaños - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Cupón de Cumpleaños de MyPresta.eu."
sidebar:
  label: "Cupón de Cumpleaños - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Happy Birthday Coupon en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/happy-birthday-coupon.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/happy-birthday-coupon/)
>
> ---


# Cupón de Cumpleaños

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Asegúrate de que la funcionalidad de cron job de tu servidor esté habilitada para el envío automatizado de cupones.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Cupón de Cumpleaños)

Esta es la pantalla de configuración principal donde defines cómo se generarán y enviarán tus cupones de cumpleaños.

#### Ajustes Generales

-   **Días antes del cumpleaños del cliente para enviar el cupón (bp\_daysbefore)**

    -   **Qué hace este ajuste:** Determina cuántos días *antes* del cumpleaños real de un cliente se enviará el correo electrónico del cupón.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en 0:* El cupón se enviará en el cumpleaños del cliente.
        -   *Cuando se establece en 7:* El cupón se enviará 7 días antes del cumpleaños del cliente. Esto les da una semana para planificar una compra.
    -   **Valor recomendado:** `7` días. Esto proporciona a los clientes tiempo suficiente para navegar por tu tienda y tomar una decisión de compra, en lugar de recibirlo el mismo día en que podrían estar ocupados.
    -   **Escenario / ejemplo de comerciante:** Quieres que los clientes reciban su regalo de cumpleaños con una semana de antelación para que tengan tiempo de usarlo para una compra especial de cumpleaños. Configurar esto en `7` asegura que reciban el correo electrónico con tiempo suficiente.
-   **Habilitar opción de boletín (bpro\_nletter)**

    -   **Qué hace este ajuste:** Controla si la funcionalidad del cupón de cumpleaños está vinculada al estado de suscripción al boletín del cliente.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (SÍ):* Solo los clientes que están suscritos a tu boletín recibirán un cupón de cumpleaños.
        -   *Cuando está deshabilitado (NO):* Todos los clientes con una fecha de nacimiento válida en su cuenta recibirán un cupón de cumpleaños, independientemente de su suscripción al boletín.
    -   **Valor recomendado:** `NO`. Para maximizar el impacto y el alcance, generalmente es mejor enviar cupones de cumpleaños a todos los clientes con una fecha de nacimiento, ya que es un gesto personal. Sin embargo, si deseas recompensar a los suscriptores del boletín específicamente, configúralo en `SÍ`.
    -   **Escenario / ejemplo de comerciante:** Quieres recompensar a todos tus clientes leales en su cumpleaños, no solo a los suscritos a tu boletín. Configurarías esto en `NO`.
-   **Grupos de clientes a incluir (birthdaypro\_groups)**

    -   **Qué hace este ajuste:** Te permite seleccionar grupos de clientes específicos que son elegibles para recibir cupones de cumpleaños.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan grupos específicos:* Solo los clientes que pertenecen a estos grupos elegidos recibirán cupones de cumpleaños.
        -   *Cuando no se seleccionan grupos (o se seleccionan todos):* Todos los clientes (sujetos a otros ajustes como la opción de boletín) serán elegibles.
    -   **Valor recomendado:** Selecciona `Cliente` y cualquier otro grupo que desees incluir. Evita seleccionar `Visitante` o `Invitado` ya que normalmente no tienen cuentas con fechas de nacimiento.
    -   **Escenario / ejemplo de comerciante:** Tienes un grupo de "Clientes VIP" y un grupo de "Mayoristas". Solo quieres enviar cupones de cumpleaños a tu grupo de "Cliente" regular y a "Clientes VIP", pero no a tus socios mayoristas. Seleccionarías "Cliente" y "Clientes VIP" de la lista.
-   **Lista de clientes (Informativo)**

    -   **Qué hace este ajuste:** No es un ajuste para cambiar, sino una sección informativa que probablemente muestra una lista de clientes que han recibido o son elegibles para cupones de cumpleaños. Te ayuda a monitorear la actividad del módulo.
    -   **Efecto de cambiar este ajuste:** No tiene un efecto directo ya que es una función de solo visualización.
    -   **Valor recomendado:** N/A
    -   **Escenario / ejemplo de comerciante:** Quieres ver rápidamente qué clientes tienen fechas de nacimiento registradas y podrían recibir cupones pronto.

#### Ajustes de Vale (Personalización Avanzada)

El módulo permite una amplia personalización de los vales generados. Estos ajustes reflejan las opciones estándar de las reglas de carrito (vales) de PrestaShop.

-   **Prefijo del Código del Vale:** (por ejemplo, `CUMPLEAÑOS-`)

    -   **Qué hace este ajuste:** Define un prefijo para todos los códigos de cupón de cumpleaños generados.
    -   **Efecto de cambiar este ajuste:** Todos los códigos únicos comenzarán con este prefijo, lo que los hace fácilmente identificables.
    -   **Valor recomendado:** `CUMPLEAÑOS-` o `CDP-`.
    -   **Escenario / ejemplo de comerciante:** Quieres distinguir fácilmente los cupones de cumpleaños de otras promociones en tu historial de pedidos.
-   **Tipo de Descuento:** (por ejemplo, Porcentaje, Cantidad, Envío Gratuito)

    -   **Qué hace este ajuste:** Determina el tipo de descuento que ofrece el cupón.
    -   **Efecto de cambiar este ajuste:**
        -   *Porcentaje:* Aplica un descuento porcentual al pedido.
        -   *Cantidad:* Aplica un descuento monetario fijo.
        -   *Envío Gratuito:* Proporciona envío gratuito.
    -   **Valor recomendado:** `Porcentaje` o `Cantidad`, dependiendo de tu estrategia de marketing.
    -   **Escenario / ejemplo de comerciante:** Quieres ofrecer un 15% de descuento por cumpleaños. Seleccionarías `Porcentaje` y establecerías el valor en `15`.
-   **Valor del Descuento:** (por ejemplo, `15` para porcentaje, `10.00` para cantidad)

    -   **Qué hace este ajuste:** El valor real del descuento.
    -   **Efecto de cambiar este ajuste:** Impacta directamente el descuento aplicado al pedido del cliente.
    -   **Valor recomendado:** Un valor que sea atractivo pero también rentable para tu tienda (por ejemplo, `10` para 10% o `5.00` para 5€).
    -   **Escenario / ejemplo de comerciante:** Siguiendo el ejemplo anterior, introducirías `15` aquí.
-   **Cantidad Mínima:**

    -   **Qué hace este ajuste:** Establece una cantidad mínima de compra requerida para que el cupón sea válido.
    -   **Efecto de cambiar este ajuste:** Anima a los clientes a gastar más para calificar para el descuento.
    -   **Valor recomendado:** Una cantidad razonable que fomente la venta adicional sin ser prohibitiva.
    -   **Escenario / ejemplo de comerciante:** Quieres que los clientes gasten al menos 50€ para usar su cupón de cumpleaños. Establecerías esto en `50.00`.
-   **Período de Validez:** (por ejemplo, `30` días)

    -   **Qué hace este ajuste:** Define cuántos días es válido el cupón desde la fecha en que se envía.
    -   **Efecto de cambiar este ajuste:** Crea urgencia para que el cliente use el cupón.
    -   **Valor recomendado:** `30` días. Esto da a los clientes un buen margen para usar su regalo sin sentirse apresurados.
    -   **Escenario / ejemplo de comerciante:** Quieres que los clientes usen su cupón de cumpleaños dentro de un mes de haberlo recibido. Establecerías esto en `30`.
-   **Aplicar a Productos/Categorías Específicos:**

    -   **Qué hace este ajuste:** Te permite restringir el uso del cupón a ciertos productos o categorías.
    -   **Efecto de cambiar este ajuste:** Se puede usar para promocionar artículos específicos o liquidar stock antiguo.
    -   **Valor recomendado:** Déjalo vacío a menos que tengas un objetivo promocional específico.
    -   **Escenario / ejemplo de comerciante:** Solo quieres que el cupón de cumpleaños sea válido para artículos de tu categoría "Novedades".
-   **Otras Opciones de Vale:** (por ejemplo, acumulable con otros vales, productos de regalo, etc.)

    -   **Qué hace este ajuste:** El módulo probablemente expone otras opciones avanzadas de reglas de carrito de PrestaShop, como si el vale se puede combinar con otros descuentos, si se aplica a transportistas específicos o si ofrece un regalo.
    -   **Efecto de cambiar este ajuste:** Te da un control granular sobre el comportamiento y las restricciones del vale.
    -   **Valor recomendado:** Configura según tu estrategia promocional específica. Ten cuidado con la acumulabilidad para evitar descuentos excesivos.
    -   **Escenario / ejemplo de comerciante:** Quieres asegurarte de que el cupón de cumpleaños no se pueda combinar con otras promociones en curso. Deshabilitarías la opción "Acumulable con otros vales".

#### Ajustes de Plantilla de Correo Electrónico

-   **Asunto del Correo Electrónico:** (por ejemplo, `¡Feliz Cumpleaños de parte de {shop_name}! ¡Aquí tienes un regalo!`)

    -   **Qué hace este ajuste:** Define la línea de asunto del correo electrónico de cumpleaños.
    -   **Efecto de cambiar este ajuste:** Esto es lo primero que ven los clientes; un asunto atractivo aumenta las tasas de apertura.
    -   **Valor recomendado:** Algo cálido, personal y que indique claramente un regalo. Usa `{shop_name}` y `{customer_firstname}` si están disponibles.
    -   **Escenario / ejemplo de comerciante:** Quieres un asunto pegadizo que haga que los clientes se sientan especiales.
-   **Contenido del Correo Electrónico:** (editor HTML)

    -   **Qué hace este ajuste:** Te permite personalizar el contenido completo del correo electrónico de cumpleaños.
    -   **Efecto de cambiar este ajuste:** Aquí es donde transmites tus deseos de cumpleaños, explicas el descuento y animas a comprar.
    -   **Valor recomendado:** Incluye un saludo cálido, indica claramente el código de descuento y su valor, explica cómo usarlo y añade una llamada a la acción. Usa marcadores de posición como `{customer_firstname}`, `{voucher_code}`, `{shop_name}`, `{shop_url}`.
    -   **Escenario / ejemplo de comerciante:** Quieres escribir un mensaje sincero, incluir el logotipo de tu marca y mostrar claramente el código de descuento.

#### Información del Cron Job

-   **URL del Cron Job:** (por ejemplo, `http://tutienda.com/modules/birthdaypro/controllers/front/cron.php?token=TU_TOKEN_SEGURO`)
    -   **Qué hace este ajuste:** Muestra la URL que necesitas configurar como un cron job en tu servidor. Este cron job es esencial para que el módulo verifique automáticamente los próximos cumpleaños y envíe cupones.
    -   **Efecto de cambiar este ajuste:** No es un ajuste para cambiar, sino una instrucción. Si el cron job no se configura correctamente, no se enviarán cupones de cumpleaños automáticamente.
    -   **Valor recomendado:** Configura un cron job para ejecutar esta URL una vez cada 24 horas (por ejemplo, diariamente a medianoche).
    -   **Escenario / ejemplo de comerciante:** Has configurado todos los ajustes, pero no se envían correos electrónicos. Lo primero que debes verificar es si tu proveedor de alojamiento ha configurado correctamente el cron job utilizando esta URL.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Días antes del cumpleaños del cliente para enviar el cupón | `7` | Envía el cupón X días antes del cumpleaños, fomentando compras planificadas. |
| Configuración del Módulo | Habilitar opción de boletín | `NO` | Determina si solo los suscriptores del boletín reciben cupones. `NO` para un mayor alcance. |
| Configuración del Módulo | Grupos de clientes a incluir | `Cliente` (y otros según sea necesario) | Restringe el envío de cupones a segmentos de clientes específicos. |
| Configuración del Módulo | Prefijo del Código del Vale | `CUMPLEAÑOS-` | Añade un prefijo único a los códigos de cupón generados para una fácil identificación. |
| Configuración del Módulo | Tipo de Descuento | `Porcentaje` o `Cantidad` | Define la naturaleza del descuento (por ejemplo, 15% de descuento, 10€ de descuento). |
| Configuración del Módulo | Valor del Descuento | `10` (para 10%) o `5.00` (para 5€) | El valor real del descuento. |
| Configuración del Módulo | Cantidad Mínima | (Vacío o valor específico) | Establece un valor de pedido mínimo para que el cupón sea válido. |
| Configuración del Módulo | Período de Validez | `30` días | Cuánto tiempo es válido el cupón desde la fecha de envío, creando urgencia. |
| Configuración del Módulo | Aplicar a Productos/Categorías Específicos | (Vacío o selección específica) | Restringe el uso del cupón a ciertos productos o categorías. |
| Configuración del Módulo | Otras Opciones de Vale | (Según la estrategia) | Control granular sobre el comportamiento del vale (por ejemplo, acumulabilidad). |
| Configuración del Módulo | Asunto del Correo Electrónico | `¡Feliz Cumpleaños de parte de {shop_name}!` | La línea de asunto del correo electrónico de cumpleaños. |
| Configuración del Módulo | Contenido del Correo Electrónico | (HTML personalizado) | El cuerpo del correo electrónico de cumpleaños, incluyendo saludos y detalles del cupón. |
| Configuración del Módulo | URL del Cron Job | (URL mostrada) | Esencial para las comprobaciones diarias automatizadas y el envío de cupones. Debe configurarse en el servidor. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mis clientes no reciben correos electrónicos de cumpleaños. ¿Qué debo verificar primero?**
R1:

1.  **Cron Job:** La razón más común. Asegúrate de que la URL del cron job proporcionada en la configuración del módulo esté configurada correctamente en tu servidor de alojamiento para que se ejecute diariamente. Sin ella, el módulo no puede enviar correos electrónicos automáticamente.
2.  **Fechas de Nacimiento de los Clientes:** Verifica que tus clientes realmente tengan sus fechas de nacimiento ingresadas en sus cuentas de PrestaShop. El módulo se basa en estos datos.
3.  **Configuración de Correo Electrónico:** Revisa la configuración de correo electrónico de tu PrestaShop (Parámetros Avanzados > E-mail) para asegurarte de que tu tienda pueda enviar correos electrónicos con éxito. Prueba a enviar un correo electrónico general desde PrestaShop.
4.  **Carpetas de Spam:** Aconseja a los clientes que revisen sus carpetas de spam o correo no deseado.
5.  **Configuración del Módulo:** Vuelve a verificar "Días antes del cumpleaños del cliente", "Habilitar opción de boletín" y "Grupos de clientes a incluir" para asegurarte de que los clientes sean elegibles.

**P2: El código de descuento no funciona para mis clientes.**
R2:

1.  **Validez del Vale:** Verifica la configuración de "Período de Validez" en el módulo. ¿Ha caducado el cupón?
2.  **Cantidad Mínima:** ¿El carrito del cliente cumple con el requisito de "Cantidad Mínima" establecido para el vale?
3.  **Restricciones de Producto/Categoría:** Si aplicaste restricciones, ¿el cliente está intentando comprar un producto elegible?
4.  **Acumulable con otros vales:** Si deshabilitaste esto, asegúrate de que el cliente no esté intentando combinarlo con otro descuento.
5.  **Errores tipográficos:** Pide al cliente que verifique si hay errores tipográficos al introducir el código.

**P3: ¿Cómo cambio la apariencia del correo electrónico de cumpleaños?**
R3: Puedes personalizar completamente el contenido del correo electrónico utilizando el editor HTML en la configuración "Contenido del Correo Electrónico" en la página de configuración del módulo. Puedes añadir tu logotipo, cambiar fuentes, colores y diseño. Asegúrate de usar los marcadores de posición disponibles (como `{customer_firstname}`, `{voucher_code}`, `{shop_name}`) para personalizar el mensaje.

**P4: ¿Puedo enviar diferentes cupones de cumpleaños a diferentes grupos de clientes?**
R4: El módulo Cupón de Cumpleaños, en su configuración estándar, envía un tipo de cupón basado en los ajustes que definas. Para enviar diferentes cupones a diferentes grupos (por ejemplo, un 10% de descuento para clientes regulares y un 20% de descuento para VIP), tendrías que:
a) Crear y enviar manualmente vales separados para grupos específicos (lo que anula la automatización).
b) Usar las "Reglas de Carrito" nativas de PrestaShop para grupos específicos y gestionarlas manualmente.
c) Considerar una personalización avanzada o una solución de automatización de marketing más compleja si este es un requisito crítico.

**P5: El módulo parece estar funcionando, pero no veo ninguna evidencia de que se generen cupones en la sección "Reglas de Carrito" de PrestaShop.**
R5: El módulo genera reglas de carrito únicas (vales) dinámicamente cuando se acerca el cumpleaños de un cliente. Estas son reglas de carrito reales de PrestaShop. Deberías poder verlas en **Catálogo > Descuentos > Reglas de Carrito** (o **Reglas de Precio > Reglas de Carrito** en versiones anteriores). Busca reglas con el prefijo que definiste (por ejemplo, `CUMPLEAÑOS-`). Si no aparecen, vuelve a verificar la configuración de tu cron job y la configuración del módulo.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo Cupón de Cumpleaños.

### 4.1 Descripción General de la Arquitectura

El módulo Cupón de Cumpleaños (`birthdaypro`) sigue una arquitectura de módulo estándar de PrestaShop, utilizando `Module` como su base. Funciona principalmente a través de un cron job que activa un controlador frontal para identificar clientes elegibles y generar objetos `CartRule` de PrestaShop. El módulo no extiende `ObjectModel` para sus propios datos, sino que se basa en los datos de clientes existentes de PrestaShop y la funcionalidad de `CartRule`. Utiliza un motor de vales personalizado y una herramienta de búsqueda de autocompletado, probablemente para la selección de clientes en el back-office o para pruebas.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

Estos controladores están diseñados para ser accedidos externamente, principalmente a través de cron jobs.

-   **`controllers/front/cron.php`**

    -   **Nombre de la clase y clase padre:** `BirthdayproCronModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Esta es la lógica central para la generación y envío automatizado de cupones. Está diseñado para ser llamado por un cron job del lado del servidor.
        -   Obtiene las fechas de nacimiento de los clientes.
        -   Determina qué clientes son elegibles según la configuración de `bp_daysbefore`, `bpro_nletter` y `birthdaypro_groups`.
        -   Para cada cliente elegible, genera una `CartRule` (vale) única de PrestaShop con los parámetros configurados.
        -   Envía un correo electrónico de cumpleaños que contiene el código del vale al cliente.
        -   Incluye una verificación de token de seguridad para evitar accesos no autorizados.
-   **`controllers/front/index.php`**

    -   **Nombre de la clase y clase padre:** `BirthdayproIndexModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este controlador probablemente sirve como un marcador de posición o un punto de entrada simple, posiblemente para pruebas o para manejar solicitudes que no coinciden con otros controladores frontales específicos. En muchos módulos, un `index.php` en un directorio de controladores es un fallback o un controlador básico tipo "hola mundo". Puede que no tenga una lógica de negocio significativa.

#### Controladores de Administración del Back-Office

El módulo no parece tener controladores de administración personalizados dedicados según el inventario proporcionado. Toda la configuración del back-office se maneja dentro del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Principales (`classes/`)

El inventario proporcionado indica que no hay clases o modelos personalizados en el directorio `classes/`. El módulo probablemente utiliza directamente las clases nativas `Customer`, `CartRule` y `Mail` de PrestaShop. El "voucherengine" y "searchTool" mencionados en las rutas JS/CSS sugieren clases o funciones auxiliares internas dentro de `birthdaypro.php` o sus bibliotecas incluidas, en lugar de archivos `classes/` independientes.

### 4.4 Activos JavaScript (`views/js/`)

-   **`lib/searchTool/views/js/autocomplete.js`**

    -   **Alcance:** Probablemente Back-office.
    -   **Detalles:** Este script proporciona funcionalidad de autocompletado, probablemente para buscar clientes o productos dentro de la configuración del módulo o una interfaz de administración relacionada. Se vincularía a los campos de entrada, realizaría solicitudes AJAX a un punto final de backend (posiblemente el archivo principal del módulo o un controlador de administración dedicado si existiera), y mostraría sugerencias.
-   **`lib/voucherengine/script.js`**

    -   **Alcance:** Probablemente Back-office.
    -   **Detalles:** Este script forma parte del "motor de vales" del módulo. Probablemente maneja elementos de formulario dinámicos relacionados con la creación de vales dentro de la página de configuración del módulo. Esto podría incluir mostrar/ocultar campos según la selección del tipo de descuento, validar la entrada de valores de vales o interactuar con otros ajustes relacionados con los vales.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   **`lib/searchTool/views/css/autocomplete.css`**

    -   **Alcance:** Probablemente Back-office.
    -   **Detalles:** Proporciona estilos para el menú desplegable de sugerencias de autocompletado y posiblemente el propio campo de entrada, asegurando que se integre visualmente con el back office de PrestaShop.
-   **`lib/voucherengine/ps16.css`**

    -   **Alcance:** Probablemente Back-office.
    -   **Detalles:** Esta hoja de estilo proporciona estilos específicos para los elementos de configuración de vales, posiblemente dirigidos a la estética del back-office de PrestaShop 1.6. Podría incluir estilos para grupos de formularios, campos de entrada y etiquetas relacionadas con la configuración de vales.
-   **`views/css/css.css`**

    -   **Alcance:** Probablemente Back-office.
    -   **Detalles:** Una hoja de estilo general para el módulo, que potencialmente contiene estilos para la página de configuración principal (`admin.tpl`) o cualquier elemento personalizado introducido por el módulo en el back office. Podría incluir estilos básicos de diseño, botones o alertas.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **`lib/searchTool/views/scripts.tpl`**

    -   **Alcance:** Back-office.
    -   **Detalles:** Esta plantilla probablemente incluye código JavaScript o variables Smarty necesarias para que el script `autocomplete.js` funcione correctamente, como URLs AJAX, cadenas de idioma o datos iniciales. Se incluiría en la plantilla de configuración principal del administrador.
-   **`views/templates/admin.tpl`**

    -   **Alcance:** Back-office.
    -   **Detalles:** Esta es la plantilla principal para la página de configuración del módulo, renderizada por el método `getContent()` en `birthdaypro.php`. Contiene la estructura HTML para todos los ajustes descritos en la Sección 4.1, incluidos los campos de formulario, botones y posiblemente inclusiones para otras plantillas como `scripts.tpl`.
-   **`views/templates/script.tpl`**

    -   **Alcance:** Back-office.
    -   **Detalles:** Similar a `scripts.tpl` en la biblioteca `searchTool`, esta plantilla probablemente contiene JavaScript o variables Smarty específicas del módulo que se inyectan en la página de configuración del back-office. Podría manejar el comportamiento dinámico o el paso de datos para el motor de vales.
-   **`views/templates/test.tpl`**

    -   **Alcance:** Back-office o pruebas internas.
    -   **Detalles:** El propósito de esta plantilla es menos claro solo por el nombre. Podría ser una plantilla utilizada para pruebas internas durante el desarrollo, una plantilla de salida de depuración o un simple marcador de posición. Es poco probable que forme parte de la configuración estándar orientada al comerciante.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de la Base de Datos**:

    -   El módulo no crea tablas de base de datos personalizadas según el inventario proporcionado.
    -   Almacena sus ajustes de configuración (por ejemplo, `bp_daysbefore`, `bpro_nletter`, `birthdaypro_groups`) en la tabla `ps_configuration` de PrestaShop.
    -   Interactúa con las tablas existentes de PrestaShop: `ps_customer` (para fechas de nacimiento), `ps_cart_rule` (para crear vales), `ps_cart_rule_lang`, `ps_cart_rule_shop`, `ps_cart_rule_product_rule_group`, etc.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento / Contexto de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Típicamente utilizado para añadir CSS, JS o meta etiquetas. La descripción del módulo lo menciona, pero su función principal se basa en cron, por lo que este hook podría usarse para una configuración mínima del front-end o no usarse activamente para la funcionalidad principal. |
| `displayRightColumn` | En la columna derecha de las páginas del front-office. | Muestra contenido en la barra lateral derecha. Es poco probable que sea utilizado por este módulo dada su operación en segundo plano. |
| `displayLeftColumn` | En la columna izquierda de las páginas del front-office. | Muestra contenido en la barra lateral izquierda. Es poco probable que sea utilizado por este módulo dada su operación en segundo plano. |
| `displayFooter` | En la sección del pie de página de cada página del front-office. | Muestra contenido en el pie de página. Es poco probable que sea utilizado por este módulo dada su operación en segundo plano. |
| `displayProductButtons` / `displayProductExtraContent` (o hooks de Producto similares) | En la página del producto. | Es poco probable que sea utilizado por este módulo. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Podría usarse potencialmente para rastrear el uso de cupones o el comportamiento del cliente después de aplicar un cupón de cumpleaños, aunque no se enumera explícitamente como una función principal. |
| `actionCustomerAccountAdd` / `actionCustomerAccountUpdate` | Cuando se crea o actualiza una cuenta de cliente. | Podría usarse para verificar la entrada de la fecha de nacimiento o activar la configuración inicial para nuevos clientes, aunque el cron job es el disparador principal. |
| (Implícito) Ejecución del Cron Job | Diariamente, a través de un cron externo del servidor. | **CRÍTICO:** Este es el "hook" principal para la funcionalidad central del módulo, que activa `controllers/front/cron.php` para procesar cumpleaños y enviar correos electrónicos. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo Cupón de Cumpleaños, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo se dedica a garantizar que tu módulo funcione de manera óptima y te ayude a alcanzar tus objetivos de comercio electrónico.
"""

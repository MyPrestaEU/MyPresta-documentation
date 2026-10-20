---
title: "Advanced Contact Form Builder Pro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Advanced Contact Form Builder Pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "Advanced Contact Form Builder Pro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Advanced Contact Form Builder Pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/advanced-contact-form-builder-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/advanced-contact-form-builder-pro/)
>
> ---


# Advanced Contact Form Builder Pro

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x (hasta 12.x según la definición del módulo)
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y para funciones como webhooks o reCAPTCHA.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla principal donde configura el comportamiento general y las opciones predeterminadas para sus formularios de contacto.

- **Perfil de soporte de plantilla**

  - **Qué hace este ajuste:** Este ajuste ayuda al módulo a adaptar su salida visual para que coincida mejor con el tema de su tienda. Los diferentes temas de PrestaShop pueden tener estructuras HTML ligeramente diferentes.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 'Classic' (o similar):* El módulo utilizará plantillas optimizadas para el tema Classic predeterminado de PrestaShop o temas basados en él. Esto asegura que los formularios se vean bien sin un esfuerzo de estilo adicional.
    - *Cuando se establece en 'Personalizado' u otro nombre de tema:* El módulo podría usar plantillas o reglas de estilo específicas adaptadas para ese tema en particular, si están disponibles.
  - **Valor recomendado:** Elija la opción que mejor se adapte a su tema activo de PrestaShop. Si está utilizando el tema Classic predeterminado o un tema derivado de él, 'Classic' suele ser la mejor opción. Si sus formularios no se ven del todo bien, intente experimentar con este ajuste.
  - **Escenario / ejemplo del comerciante:** Si sus formularios aparecen sin estilo o desalineados después de la instalación, cambiar esto de 'Classic' a otro perfil disponible (si lo hay) podría resolver el problema.
- **Correo electrónico de respuesta automática**

  - **Qué hace este ajuste:** Esta es la dirección de correo electrónico desde la cual se enviarán correos electrónicos de confirmación automáticos a sus clientes después de que envíen un formulario.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en una dirección de correo electrónico válida:* Los clientes recibirán un correo electrónico inmediato de "Gracias por su consulta" desde esta dirección.
    - *Cuando se deja vacío:* No se enviará ningún correo electrónico de confirmación automático al cliente.
  - **Valor recomendado:** Utilice una dirección de correo electrónico profesional asociada con su tienda, por ejemplo, `info@sutieneda.com` o `noreply@sutieneda.com`.
  - **Escenario / ejemplo del comerciante:** Configurar esto en `soporte@mitienda.com` asegura que los clientes sepan que su mensaje fue recibido y les proporciona un punto de contacto para el seguimiento.
- **Título del correo electrónico (para el propietario de la tienda)**

  - **Qué hace este ajuste:** Esto define la línea de asunto para las notificaciones por correo electrónico que usted (el propietario de la tienda) recibe cuando un cliente envía un formulario.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "Nueva consulta de Mi Tienda":* Sus correos electrónicos de notificación tendrán este asunto, lo que los hará fáciles de identificar.
  - **Valor recomendado:** Algo claro y descriptivo, como "Nuevo envío de formulario de contacto - [Nombre de su tienda]".
  - **Escenario / ejemplo del comerciante:** Usar "Nueva consulta de cliente - MyPresta.eu" le ayuda a detectar rápidamente mensajes importantes en su bandeja de entrada.
- **Correo(s) electrónico(s) del destinatario**

  - **Qué hace este ajuste:** Aquí es donde especifica una o más direcciones de correo electrónico que recibirán notificaciones cuando un cliente envíe *cualquier* formulario creado por este módulo. Puede separar varios correos electrónicos con una coma.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en `ventas@sutieneda.com`:* Todos los envíos de formularios se enviarán al departamento de ventas.
    - *Cuando se establece en `ventas@sutieneda.com, soporte@sutieneda.com`:* Ambos departamentos recibirán copias de todos los envíos.
  - **Valor recomendado:** La(s) dirección(es) de correo electrónico principal(es) de su equipo de atención al cliente o de ventas.
  - **Escenario / ejemplo del comerciante:** Si tiene un equipo de atención al cliente dedicado, introduciría `atencionalcliente@sutieneda.com` aquí.
- **CCO para el correo electrónico de notificación de la tienda**

  - **Qué hace este ajuste:** Le permite enviar una "Copia oculta" del correo electrónico de notificación del propietario de la tienda a direcciones de correo electrónico adicionales. Estos destinatarios no serán visibles para el destinatario principal.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en `gerente@sutieneda.com`:* El gerente recibirá una copia oculta de todas las notificaciones de envío de formularios.
  - **Valor recomendado:** Utilice esto para seguimiento interno, copia de seguridad o para gerentes que necesiten monitorear las consultas sin ser el contacto principal. Déjelo vacío si no es necesario.
  - **Escenario / ejemplo del comerciante:** Su equipo de marketing podría querer enviarse una CCO para rastrear la generación de leads de los formularios sin estar directamente involucrado en las respuestas a los clientes.
- **Sí / No (para varias configuraciones de visibilidad/requisito de campo)**

  - **Qué hace este ajuste:** Son interruptores generales para habilitar o deshabilitar funciones específicas o hacer que ciertos campos sean obligatorios/opcionales en sus formularios.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* La función está activa (por ejemplo, el campo de teléfono es visible, se permiten archivos adjuntos).
    - *Cuando está deshabilitado (No):* La función está inactiva (por ejemplo, el campo de teléfono está oculto, no se permiten archivos adjuntos).
  - **Valor recomendado:** Depende completamente de las necesidades de su negocio para cada configuración específica (consulte las configuraciones individuales a continuación).
- **Cumplimiento del GDPR**

  - **Qué hace este ajuste:** Habilita una casilla de verificación en sus formularios donde los clientes deben aceptar explícitamente su política de privacidad antes de enviar sus datos. Esto es crucial para el cumplimiento del GDPR.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparece una casilla de verificación obligatoria en sus formularios, que normalmente indica algo como "Acepto la política de privacidad". El formulario no se puede enviar hasta que se marque esta casilla.
    - *Cuando está deshabilitado:* No aparecerá ninguna casilla de verificación de consentimiento GDPR.
  - **Valor recomendado:** **SÍ** si su tienda opera en regiones sujetas al GDPR (por ejemplo, la UE) o si desea garantizar las mejores prácticas para la privacidad de los datos.
  - **Escenario / ejemplo del comerciante:** Una tienda con sede en la UE *debe* habilitar esto para recopilar legalmente datos de clientes a través de formularios.
- **Página de política de privacidad**

  - **Qué hace este ajuste:** Si el cumplimiento del GDPR está habilitado, este ajuste le permite vincular a la página CMS de política de privacidad de su tienda. La casilla de verificación de consentimiento GDPR normalmente incluirá un enlace a esta página.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se selecciona una página:* El texto de consentimiento GDPR incluirá un enlace en el que se puede hacer clic a la página de política de privacidad elegida.
    - *Cuando no se selecciona ninguna página:* El texto de consentimiento GDPR podría aparecer sin un enlace, o vincular a una página predeterminada, lo cual no es ideal para el cumplimiento.
  - **Valor recomendado:** Seleccione la página CMS de política de privacidad oficial de su tienda.
  - **Escenario / ejemplo del comerciante:** Después de habilitar el GDPR, seleccionaría la página CMS titulada "Política de privacidad" de la lista desplegable.
- **ReCaptcha (v2)**

  - **Qué hace este ajuste:** Habilita Google reCAPTCHA v2 en sus formularios para protegerse contra el spam y los bots.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* La casilla de verificación reCAPTCHA "No soy un robot" aparecerá en sus formularios. Los usuarios deben completar este desafío antes de enviar.
    - *Cuando está deshabilitado:* No hay protección reCAPTCHA activa.
  - **Valor recomendado:** **SÍ** para evitar envíos de spam. También deberá configurar la Clave del sitio y la Clave secreta a continuación.
  - **Escenario / ejemplo del comerciante:** Si está recibiendo mucho spam a través de sus formularios de contacto, habilitar reCAPTCHA es el primer paso para combatirlo.
- **Clave del sitio ReCaptcha**

  - **Qué hace este ajuste:** Esta es una clave pública proporcionada por Google reCAPTCHA que permite a su sitio web mostrar el widget reCAPTCHA.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce correctamente:* El widget reCAPTCHA aparecerá y funcionará correctamente en sus formularios.
    - *Cuando es incorrecta o está vacía:* reCAPTCHA no funcionará y los formularios podrían no enviarse o mostrar errores.
  - **Valor recomendado:** La clave del sitio obtenida de su cuenta de Google reCAPTCHA.
  - **Escenario / ejemplo del comerciante:** Después de crear un par de claves reCAPTCHA v2 en la consola de administración de Google reCAPTCHA, copiaría la "Clave del sitio" aquí.
- **Clave secreta ReCaptcha**

  - **Qué hace este ajuste:** Esta es una clave privada proporcionada por Google reCAPTCHA que permite a su servidor verificar la respuesta reCAPTCHA. Debe mantenerse en secreto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce correctamente:* Su servidor puede verificar con éxito si un usuario pasó el desafío reCAPTCHA.
    - *Cuando es incorrecta o está vacía:* La verificación fallará y los usuarios legítimos podrían no poder enviar formularios.
  - **Valor recomendado:** La clave secreta obtenida de su cuenta de Google reCAPTCHA.
  - **Escenario / ejemplo del comerciante:** Copiaría la "Clave secreta" de su consola de administración de Google reCAPTCHA aquí.
- **URL de Webhook (Slack/Discord)**

  - **Qué hace este ajuste:** Le permite enviar notificaciones de envío de formularios a un canal específico de Slack o Discord a través de un webhook. Esto proporciona alertas instantáneas al equipo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce una URL válida:* Cada envío de formulario activará una notificación a su canal de Slack/Discord configurado.
    - *Cuando está vacío:* No se enviarán notificaciones de webhook.
  - **Valor recomendado:** Su URL de webhook de Slack o Discord. Déjelo vacío si no utiliza estos servicios para notificaciones.
  - **Escenario / ejemplo del comerciante:** Su equipo de atención al cliente utiliza Slack. Configura un webhook en Slack, pega la URL aquí y ahora cada nueva consulta aparece directamente en su canal #atencion-al-cliente.
- **CSS personalizado (escaparate)**

  - **Qué hace este ajuste:** Proporciona un área de texto donde puede agregar su propio código CSS personalizado para dar estilo a los formularios en su escaparate. Esto es útil para ajustar la apariencia para que coincida perfectamente con su marca.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce CSS:* Los estilos definidos aquí se aplicarán a sus formularios, anulando los estilos predeterminados del módulo.
  - **Valor recomendado:** Utilice esto solo si tiene necesidades de estilo específicas más allá de la apariencia predeterminada del módulo. Consulte a un diseñador web si no está seguro.
  - **Escenario / ejemplo del comerciante:** Desea que el botón de envío del formulario sea un tono específico de verde que coincida con su logotipo. Agregaría CSS como `.cfrompro-form button[type="submit"] { background-color: #00FF00; }` aquí.
- **Longitud mínima de la pregunta (caracteres)**

  - **Qué hace este ajuste:** Establece el número mínimo de caracteres requeridos para el campo principal de "Pregunta" o "Mensaje" en sus formularios.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 10:* Los clientes deben escribir al menos 10 caracteres en el campo de mensaje para enviar el formulario.
    - *Cuando se establece en 0 (o muy bajo):* Permite mensajes muy cortos.
  - **Valor recomendado:** 10-20 caracteres para animar a los clientes a proporcionar suficientes detalles.
  - **Escenario / ejemplo del comerciante:** Para evitar consultas vagas como "Hola", establece esto en 15, asegurando que los clientes proporcionen un mensaje más descriptivo.
- **Longitud máxima de la pregunta (caracteres)**

  - **Qué hace este ajuste:** Establece el número máximo de caracteres permitidos para el campo principal de "Pregunta" o "Mensaje".
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 500:* Los clientes no pueden escribir más de 500 caracteres en el campo de mensaje.
  - **Valor recomendado:** 500-1000 caracteres, dependiendo de cuán detalladas espere que sean las consultas. Demasiado bajo podría frustrar a los usuarios, demasiado alto podría llevar a mensajes excesivamente largos.
  - **Escenario / ejemplo del comerciante:** Desea evitar ensayos extremadamente largos en el formulario de contacto, por lo que establece esto en 750 caracteres.
- **Permitir adjuntar imágenes**

  - **Qué hace este ajuste:** Habilita o deshabilita la capacidad de los clientes para subir archivos (como imágenes, PDF) con el envío de su formulario.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un campo de carga de archivos en sus formularios.
    - *Cuando está deshabilitado:* No habrá opción de carga de archivos disponible.
  - **Valor recomendado:** **SÍ** si los clientes a menudo necesitan proporcionar capturas de pantalla, confirmaciones de pedidos u otros documentos. **NO** si desea mantener los formularios simples.
  - **Escenario / ejemplo del comerciante:** Para un formulario de soporte, habilitar los archivos adjuntos permite a los clientes enviar capturas de pantalla de los problemas, lo cual es muy útil.
- **Tamaño máximo de archivo adjunto (MB)**

  - **Qué hace este ajuste:** Si se permiten archivos adjuntos, este ajuste define el tamaño máximo de archivo (en megabytes) que un cliente puede subir.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 5:* Los clientes pueden subir archivos de hasta 5 MB. Los archivos más grandes serán rechazados.
  - **Valor recomendado:** 2-5 MB suele ser suficiente para la mayoría de los documentos e imágenes sin sobrecargar su servidor.
  - **Escenario / ejemplo del comerciante:** Permite archivos adjuntos pero desea evitar archivos enormes, por lo que establece el límite en 3 MB.
- **Duración del mensaje de éxito (ms)**

  - **Qué hace este ajuste:** Controla cuánto tiempo permanece visible el mensaje "Formulario enviado correctamente" (a menudo una notificación "toast") para el cliente después de enviar un formulario. Se mide en milisegundos (1000 ms = 1 segundo).
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 3000:* El mensaje de éxito desaparecerá después de 3 segundos.
    - *Cuando se establece en 0:* El mensaje podría permanecer indefinidamente o desaparecer inmediatamente (dependiendo del tema/navegador).
  - **Valor recomendado:** 3000-5000 ms (3-5 segundos) es un buen equilibrio, dando a los clientes tiempo suficiente para leerlo sin ser intrusivo.
  - **Escenario / ejemplo del comerciante:** Desea que los clientes vean claramente la confirmación, por lo que lo establece en 4000 ms.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

El módulo añade nuevos elementos de menú en **"Advanced Contact Form Pro"** en su Back Office de PrestaShop.

#### 2.2.1 Gestión de formularios (Back Office > Advanced Contact Form Pro > Formularios)

Esta pantalla le permite crear, editar y gestionar todos sus formularios de contacto personalizados.

- **Nombre de la pantalla y ubicación del menú:** **Advanced Contact Form Pro > Formularios**
- **Acciones y configuraciones disponibles:**
  - **Vista de lista (Cuadrícula):** Muestra una tabla de todos sus formularios creados, mostrando su nombre, ID y estado.
  - **Añadir nuevo formulario:** Haga clic en el botón "Añadir nuevo formulario" para crear un formulario personalizado completamente nuevo.
  - **Editar formulario:** Haga clic en el icono "Editar" junto a un formulario en la lista para modificar su configuración.
  - **Eliminar formulario:** Haga clic en el icono "Eliminar" para eliminar un formulario.
  - **Campos de configuración del formulario (al añadir/editar):**
    - **Nombre del formulario:** Un nombre interno claro para su formulario (por ejemplo, "Consulta de venta al por mayor", "Soporte de producto").
    - **Shortcode:** Un código único (por ejemplo, `[cfrompro id="1"]`) que utilizará para incrustar este formulario específico en páginas CMS o descripciones de productos.
    - **Estado del formulario:** Habilitar/Deshabilitar el formulario. Los formularios deshabilitados no aparecerán en el escaparate.
    - **Correo(s) electrónico(s) del destinatario para ESTE formulario:** Puede anular el(los) correo(s) electrónico(s) del destinatario global para este formulario específico. Esto es muy potente para enrutar consultas.
    - **Correo electrónico de respuesta automática para ESTE formulario:** Anule el correo electrónico de respuesta automática global para este formulario.
    - **Título del correo electrónico (para el propietario de la tienda) para ESTE formulario:** Anule el asunto del correo electrónico global para las notificaciones de este formulario.
    - **Campos personalizados:** Aquí es donde define los campos únicos para *este* formulario. Puede añadir entradas de texto, áreas de texto, desplegables, casillas de verificación, botones de radio, cargas de archivos y más. Para cada campo personalizado, puede establecer:
      - **Etiqueta:** Lo que ve el cliente (por ejemplo, "Nombre de su empresa").
      - **Tipo:** (Texto, Área de texto, Selección, Casilla de verificación, Radio, Archivo, etc.).
      - **Requerido:** ¿Es este campo obligatorio?
      - **Marcador de posición:** Texto de sugerencia dentro del campo de entrada.
      - **Opciones (para Selección, Casilla de verificación, Radio):** Defina las opciones que los clientes pueden elegir.
      - **Reglas de validación:** (por ejemplo, formato de correo electrónico, solo números).
    - **Configuración del activador flotante:**
      - **Habilitar activador flotante:** Mostrar un botón flotante en el escaparate que abre este formulario.
      - **Texto del activador:** Qué texto aparece en el botón flotante (por ejemplo, "Contáctenos").
      - **Posición del activador:** Dónde aparece el botón (por ejemplo, izquierda, derecha, abajo a la izquierda).
      - **Icono del activador:** Elija un icono para el botón.
      - **Retraso del activador (ms):** Cuánto tiempo esperar antes de que aparezca el botón flotante (por ejemplo, 2000ms = 2 segundos).
      - **Color del activador, Color del texto, Color al pasar el ratón:** Personalice la apariencia del botón.
- **Efecto de los cambios:**
  - Añadir/editar un formulario lo hace disponible para incrustar o como un activador flotante.
  - Los cambios en los campos personalizados afectan directamente lo que los clientes ven y rellenan en ese formulario específico.
  - Los cambios en los correos electrónicos de los destinatarios dirigen los envíos a diferentes departamentos.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Decida qué tipo de consulta desea manejar (por ejemplo, "Solicitud de venta al por mayor").
  2. Vaya a **Formularios** y haga clic en "Añadir nuevo formulario".
  3. Dele un nombre claro.
  4. Agregue todos los campos personalizados específicos que necesite (por ejemplo, Nombre de la empresa, NIF/CIF, Tipo de negocio, Volumen de pedido esperado).
  5. Establezca un correo electrónico de destinatario específico si este formulario debe ir a un equipo en particular (por ejemplo, `ventamayorista@sutieneda.com`).
  6. Guarde el formulario. Anote su shortcode.
  7. Incruste el shortcode en una página CMS relevante (por ejemplo, "Información para mayoristas").

#### 2.2.2 Gestión de preguntas (Back Office > Advanced Contact Form Pro > Preguntas)

Esta pantalla sirve como su bandeja de entrada para todos los envíos de formularios.

- **Nombre de la pantalla y ubicación del menú:** **Advanced Contact Form Pro > Preguntas**
- **Acciones y configuraciones disponibles:**
  - **Vista de lista (Cuadrícula):** Muestra una tabla de todas las preguntas/consultas enviadas.
    - **Columnas:** Muestra información como Nombre del formulario, Nombre del cliente, Correo electrónico, Tema (si corresponde), Fecha de envío y Estado.
  - **Ver pregunta:** Haga clic en el icono "Ver" (lupa) junto a una consulta para ver sus detalles completos.
    - **Vista de detalles:** Muestra toda la información enviada por el cliente, incluidas las respuestas a los campos personalizados, los archivos adjuntos (con enlaces de descarga) y el formulario del que proviene.
    - **Sección de respuesta:** Le permite responder directamente al cliente desde el Back Office de PrestaShop. Esta respuesta se enviará desde el correo electrónico de contacto predeterminado de su tienda.
    - **Cambiar estado:** Puede actualizar el estado de una consulta (por ejemplo, "Nuevo", "En progreso", "Resuelto").
  - **Eliminar pregunta:** Eliminar una consulta de la lista.
- **Efecto de los cambios:**
  - Ver una pregunta le permite procesar las consultas de los clientes de manera eficiente.
  - Responder desde aquí mantiene un registro de la comunicación (aunque el módulo no almacena el historial completo de respuestas dentro de sí mismo, envía un correo electrónico estándar).
  - Cambiar el estado le ayuda a rastrear el progreso de cada consulta.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Revise regularmente esta sección de "Preguntas".
  2. Para cada nueva consulta, haga clic en "Ver" para leer los detalles.
  3. Si se necesita una respuesta, use la función "Responder".
  4. Actualice el estado (por ejemplo, a "En progreso") para indicar que se está manejando.
  5. Una vez resuelto, cambie el estado a "Resuelto".

#### 2.2.3 index.php (cfrompro/controllers/admin/index.php)

Este archivo es típicamente un marcador de posición o un redirigidor en los módulos de PrestaShop y no representa una pantalla directa y configurable para el comerciante. Asegura que si alguien intenta acceder al directorio `controllers/admin` directamente, sea redirigido o se realice una acción predeterminada, evitando vulnerabilidades de listado de directorios. Los comerciantes no interactuarán con esto directamente.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| **Configuración principal del módulo** | Perfil de soporte de plantilla | Classic | Adapta el estilo del formulario a su tema. |
| | Correo electrónico de respuesta automática | `info@sutieneda.com` | Dirección de correo electrónico para confirmaciones de clientes. |
| | Título del correo electrónico (para el propietario de la tienda) | Nuevo envío de formulario de contacto | Línea de asunto para sus correos electrónicos de notificación. |
| | Correo(s) electrónico(s) del destinatario | `contacto@sutieneda.com` | Dónde se envían todos los envíos de formularios (globalmente). |
| | CCO para el correo electrónico de notificación de la tienda | Vacío | Copia oculta de las notificaciones para seguimiento interno. |
| | Cumplimiento del GDPR | SÍ | Añade una casilla de verificación obligatoria de consentimiento de política de privacidad. |
| | Página de política de privacidad | Su página CMS de política de privacidad | Vincula la casilla de verificación GDPR a su política. |
| | ReCaptcha (v2) | SÍ | Habilita Google reCAPTCHA para protección contra spam. |
| | Clave del sitio ReCaptcha | Su clave del sitio de Google | Clave pública para el widget reCAPTCHA. |
| | Clave secreta ReCaptcha | Su clave secreta de Google | Clave privada para la verificación reCAPTCHA. |
| | URL de Webhook (Slack/Discord) | Vacío | Envía notificaciones a Slack/Discord. |
| | CSS personalizado (escaparate) | Vacío | Añade estilos personalizados a sus formularios. |
| | Longitud mínima de la pregunta (caracteres) | 10-20 | Caracteres mínimos para el campo de mensaje principal. |
| | Longitud máxima de la pregunta (caracteres) | 500-1000 | Caracteres máximos para el campo de mensaje principal. |
| | Permitir adjuntar imágenes | SÍ | Habilita la carga de archivos en los formularios. |
| | Tamaño máximo de archivo adjunto (MB) | 2-5 | Tamaño máximo para los archivos subidos. |
| | Duración del mensaje de éxito (ms) | 3000-5000 | Cuánto tiempo permanece visible la notificación de éxito. |
| **Gestión de formularios** | Nombre del formulario | Nombre descriptivo | Nombre interno para su formulario personalizado. |
| | Shortcode | `[cfrompro id="X"]` autogenerado | Código para incrustar el formulario. |
| | Estado del formulario | Habilitado | Activa/desactiva el formulario. |
| | Correo(s) electrónico(s) del destinatario para ESTE formulario | Correo(s) electrónico(s) específico(s) | Anula el destinatario global para este formulario. |
| | Campos personalizados | Varía | Define campos de entrada únicos para cada formulario. |
| | Habilitar activador flotante | NO (o SÍ para formularios específicos) | Muestra un botón flotante para abrir el formulario. |
| | Texto del activador | "Contáctenos" | Texto en el botón flotante. |
| | Posición del activador | Derecha/Izquierda | Ubicación del botón flotante. |
| **Gestión de preguntas** | Ver pregunta | N/A | Muestra los detalles completos de una consulta del cliente. |
| | Responder | N/A | Envía una respuesta por correo electrónico al cliente. |
| | Cambiar estado | Nuevo, En progreso, Resuelto | Rastrea el manejo de las consultas. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis formularios no se ven bien o el estilo está roto.**
R:

-   **Verifique el "Perfil de soporte de plantilla":** Vaya a **Módulos > Gestor de módulos > Advanced Contact Form Builder Pro > Configurar** y asegúrese de que el "Perfil de soporte de plantilla" coincida con su tema actual de PrestaShop (por ejemplo, 'Classic' para el tema predeterminado).
-   **Borrar caché de Smarty:** Vaya a **Parámetros avanzados > Rendimiento**, desplácese hasta "Caché" y haga clic en "Borrar caché". A veces, los archivos de estilo antiguos pueden quedarse atascados.
-   **CSS personalizado:** Si ha añadido CSS personalizado, revíselo para detectar errores. Elimínelo temporalmente para ver si está causando el problema.
-   **Conflictos de tema:** Si el problema persiste, su tema podría tener un conflicto. Póngase en contacto con el desarrollador de su tema o con el soporte de MyPresta.eu.

**P: No recibo notificaciones por correo electrónico cuando se envía un formulario.**
R:

-   **Verifique los correos electrónicos de los destinatarios:** Vaya a **Módulos > Gestor de módulos > Advanced Contact Form Builder Pro > Configurar** y verifique que los "Correo(s) electrónico(s) del destinatario" sean correctos. Además, verifique la configuración de cada formulario en **Advanced Contact Form Pro > Formularios** para ver si un formulario específico anula el destinatario global.
-   **Verifique la carpeta de spam:** Los correos electrónicos podrían estar yendo a su carpeta de spam o correo no deseado.
-   **Configuración de correo del servidor:** Asegúrese de que la configuración de correo electrónico de su tienda PrestaShop esté configurada correctamente (**Parámetros avanzados > Correo electrónico**). Pruebe a enviar un correo electrónico normal desde PrestaShop.
-   **Proveedor de alojamiento:** Su proveedor de alojamiento podría tener límites o problemas de envío de correo electrónico. Revise los registros de su servidor o póngase en contacto con ellos.

**P: reCAPTCHA no funciona o los formularios no se envían con reCAPTCHA habilitado.**
R:

-   **Verifique las claves:** Vuelva a verificar su "Clave del sitio ReCaptcha" y "Clave secreta ReCaptcha" en la configuración principal del módulo. Asegúrese de que no haya errores tipográficos y que correspondan a una configuración de reCAPTCHA v2 en su cuenta de Google.
-   **Registro de dominio:** Asegúrese de que el nombre de dominio de su tienda esté correctamente registrado en su cuenta de Google reCAPTCHA.
-   **Problemas de red:** Deshabilite temporalmente reCAPTCHA para ver si los formularios se envían. Si lo hacen, el problema es definitivamente con la configuración de reCAPTCHA o la comunicación con los servidores de Google.

**P: ¿Cómo traduzco los campos y mensajes del formulario a otros idiomas?**
R:

-   **Sistema de traducción de PrestaShop:** Vaya a **Internacional > Traducciones**.
-   **Tipo de traducción:** Seleccione "Traducciones de módulos instalados".
-   **Seleccione su tema:** Elija su tema actual.
-   **Seleccione su idioma:** Elija el idioma al que desea traducir.
-   **Módulo:** Seleccione "cfrompro" (el nombre técnico del módulo).
-   Luego verá una lista de todas las cadenas traducibles del módulo, incluidas las etiquetas de los campos, los mensajes de éxito y los mensajes de error. Tradúzcalas y guarde.

**P: Mi botón de activación flotante no aparece.**
R:

-   **Habilitar activador:** Vaya a **Advanced Contact Form Pro > Formularios**, edite el formulario que desea activar y asegúrese de que "Habilitar activador flotante" esté configurado en SÍ.
-   **Retraso del activador:** Verifique la configuración de "Retraso del activador (ms)". Si es un número alto, es posible que solo necesite esperar más tiempo para que aparezca.
-   **Conflictos de tema:** Algunos temas pueden tener CSS que oculta el botón o JavaScript que interfiere. Revise la consola de desarrollador de su navegador en busca de errores.
-   **Caché:** Borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento**).

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura

El módulo **Advanced Contact Form Builder Pro** (`cfrompro`) sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, extendiendo las clases principales de PrestaShop para su funcionalidad. Aprovecha `ObjectModel` para gestionar formularios personalizados y preguntas enviadas, utiliza controladores de administración dedicados para la gestión del Back Office e se integra con varios hooks de PrestaShop para la visualización del front-office y las acciones del backend. Los campos personalizados se gestionan a través de una clase dedicada y se almacenan como JSON.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

-   `cfrompro/controllers/front/index.php`
    -   **Nombre de la clase:** `CfromproIndexModuleFrontController` (probablemente, según el nombre del archivo)
    -   **Clase padre:** `ModuleFrontController`
    -   **Responsabilidad:** Este controlador es probablemente responsable de manejar la visualización inicial de un formulario si se accede a él a través de una URL directa (aunque la mayoría de los formularios se incrustan o se abren a través de AJAX). También podría manejar la representación inicial del activador flotante o del modal que contiene el formulario.
-   `cfrompro/controllers/front/question.php`
    -   **Nombre de la clase:** `CfromproQuestionModuleFrontController` (probablemente)
    -   **Clase padre:** `ModuleFrontController`
    -   **Responsabilidad:** Este es el controlador principal para procesar los envíos de formularios. Recibe datos POST de los formularios, realiza la validación (incluido reCAPTCHA, longitud de campo, campos obligatorios, tamaño de archivo adjunto), guarda los datos enviados (pregunta y campos personalizados) en la base de datos, envía notificaciones por correo electrónico al propietario de la tienda y una respuesta automática al cliente, y potencialmente activa el webhook. Devuelve respuestas JSON para envíos AJAX (por ejemplo, mensajes de éxito/error).

#### Controladores de administración del Back-Office

-   `cfrompro/controllers/admin/AdminCfromproForm.php`
    -   **Nombre de la clase:** `AdminCfromproFormController`
    -   **Clase padre:** `ModuleAdminController`
    -   **Nombre de la pestaña:** "Formularios" en "Advanced Contact Form Pro"
    -   **Entidad gestionada:** `CfromproForm` (`ObjectModel` hipotético para formularios)
    -   **Responsabilidad:** Gestiona las operaciones CRUD (Crear, Leer, Actualizar, Eliminar) para formularios personalizados. Define la vista de lista (cuadrícula) para formularios y la estructura del formulario para añadir/editar un formulario. Este controlador maneja el guardado de la configuración del formulario, incluida la compleja estructura JSON para campos personalizados.
-   `cfrompro/controllers/admin/AdminCfromproQuestion.php`
    -   **Nombre de la clase:** `AdminCfromproQuestionController`
    -   **Clase padre:** `ModuleAdminController`
    -   **Nombre de la pestaña:** "Preguntas" en "Advanced Contact Form Pro"
    -   **Entidad gestionada:** `CfromproQuestion` (`ObjectModel` hipotético para preguntas enviadas)
    -   **Responsabilidad:** Gestiona las operaciones CRUD para preguntas enviadas. Muestra la lista de consultas, permite ver los detalles de preguntas individuales y proporciona funcionalidad para responder a los clientes y cambiar el estado de una consulta.
-   `cfrompro/controllers/admin/index.php`
    -   **Nombre de la clase:** (Ninguno, típicamente)
    -   **Clase padre:** (Ninguno, típicamente)
    -   **Responsabilidad:** Esta es una práctica estándar de PrestaShop para evitar el listado directo de directorios. Por lo general, contiene un simple `header('Location: ../../index.php?controller=AdminHome');` o similar para redirigir al panel de control del Back Office. No representa un controlador funcional para la lógica del módulo.

### 4.3 Clases y modelos principales (`classes/`)

-   `cfrompro/classes/CfromproCustomFields.php`
    -   **Nombre de la clase:** `CfromproCustomFields`
    -   **Clase padre:** (Probablemente `ObjectModel` o una clase base personalizada para manejar datos complejos)
    -   **Tabla de la base de datos:** (Probablemente `ps_cfrompro_form` si almacena definiciones de campos personalizados dentro del objeto del formulario, o una tabla `ps_cfrompro_custom_field` separada si los campos son entidades independientes). El dossier del módulo indica `cfrompro_form` y `cfrompro_question` como tablas gestionadas, lo que sugiere que los campos personalizados probablemente se serializan dentro de la tabla `cfrompro_form`.
    -   **Campos `$definition`:** Si extiende `ObjectModel`, definiría campos relacionados con las propiedades de los campos personalizados (por ejemplo, `id_cfrompro_custom_field`, `id_cfrompro_form`, `type`, `label`, `required`, `options`, `validation`). Dada la descripción del módulo, es más probable que los campos personalizados se almacenen como una cadena JSON dentro de la tabla `cfrompro_form`, y esta clase proporciona métodos auxiliares para analizar, validar y renderizar estos campos.
    -   **Métodos públicos clave y lógica de negocio:**
        -   Métodos para añadir, editar y eliminar definiciones de campos personalizados dentro de un formulario.
        -   Métodos para renderizar campos personalizados en la plantilla del front-office.
        -   Métodos para validar los datos de campos personalizados enviados.
        -   Métodos para serializar/deserializar configuraciones de campos personalizados a/desde JSON.

### 4.4 Activos de JavaScript (`views/js/`)

-   `cfrompro/views/cfrompro.js`
    -   **Ámbito:** Front-office.
    -   **Responsabilidad:** Este es el archivo JavaScript principal del front-office. Probablemente maneja:
        -   Mostrar y gestionar el botón de activación flotante (eventos de clic, retrasos).
        -   Abrir y cerrar el modal/ventana emergente del formulario.
        -   Envío AJAX de formularios (recopilación de datos, envío al controlador `question.php`).
        -   Mostrar mensajes de éxito/error (notificaciones toast).
        -   Validación del lado del cliente de los campos del formulario.
        -   Integración con reCAPTCHA v2 (renderizar el widget, obtener el token de respuesta).
        -   Actualizaciones dinámicas basadas en tipos de campos personalizados (por ejemplo, mostrar/ocultar opciones para desplegables).
-   `cfrompro/views/js/admin-button-style.js`
    -   **Ámbito:** Back-office (AdminCfromproFormController).
    -   **Responsabilidad:** Proporciona funcionalidad JavaScript para dar estilo al botón de activación flotante dentro de la interfaz de configuración del formulario. Esto podría incluir selectores de color, vistas previas de iconos y actualizaciones en tiempo real de una vista previa del botón.
-   `cfrompro/views/js/admin-form-layout.js`
    -   **Ámbito:** Back-office (AdminCfromproFormController).
    -   **Responsabilidad:** Maneja el diseño dinámico y la gestión de campos personalizados dentro de la interfaz de creación/edición de formularios. Esto incluiría:
        -   Añadir nuevos campos personalizados (generando dinámicamente HTML para diferentes tipos de campos).
        -   Reordenar campos (arrastrar y soltar).
        -   Editar propiedades de campo (etiqueta, tipo, requerido, opciones).
        -   Eliminar campos.
        -   Serializar la configuración de campos personalizados en una cadena JSON antes de guardar el formulario.
-   `cfrompro/views/js/admin-icon-picker-data.js`
    -   **Ámbito:** Back-office (AdminCfromproFormController).
    -   **Responsabilidad:** Contiene los datos (por ejemplo, una matriz de clases de iconos o rutas SVG) utilizados por el selector de iconos para el botón de activación flotante.
-   `cfrompro/views/js/admin-icon-picker.js`
    -   **Ámbito:** Back-office (AdminCfromproFormController).
    -   **Responsabilidad:** Implementa la interfaz de usuario y la lógica para seleccionar un icono para el botón de activación flotante. Utiliza los datos de `admin-icon-picker-data.js` para mostrar los iconos disponibles y actualiza el icono seleccionado en el formulario.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `cfrompro/views/cfrompro.css`
    -   **Ámbito:** Estilo del cliente del Front-office.
    -   **Responsabilidad:** Proporciona el estilo principal para los formularios de contacto, el activador flotante, las ventanas emergentes modales y los mensajes de éxito/error en el escaparate. Define el diseño general, la tipografía, los colores y la capacidad de respuesta.
    -   **Selectores de clase CSS clave:** `.cfrompro-form`, `.cfrompro-field`, `.cfrompro-trigger`, `.cfrompro-modal`, `.cfrompro-toast`.
-   `cfrompro/views/css/admin-button-style.css`
    -   **Ámbito:** Estilo del formulario de administración del Back-office.
    -   **Responsabilidad:** Estiliza los elementos relacionados con la configuración del botón de activación flotante dentro del Back Office (por ejemplo, selectores de color, áreas de vista previa de iconos).
-   `cfrompro/views/css/admin-custom-fields.css`
    -   **Ámbito:** Estilo del formulario de administración del Back-office.
    -   **Responsabilidad:** Estiliza la interfaz para gestionar campos personalizados dentro del constructor de formularios (por ejemplo, asas de arrastrar y soltar, paneles de configuración de campos).
-   `cfrompro/views/css/admin-form-layout.css`
    -   **Ámbito:** Estilo del formulario de administración del Back-office.
    -   **Responsabilidad:** Proporciona el diseño general y el estilo para la página de creación/edición de formularios en el Back Office.
-   `cfrompro/views/css/admin-icon-picker.css`
    -   **Ámbito:** Estilo del formulario de administración del Back-office.
    -   **Responsabilidad:** Estiliza la interfaz de selección de iconos para el botón de activación flotante.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

-   `cfrompro/views/templates/hook/dashboard_recent_messages.tpl`
    -   **Hook:** `displaydashboardZoneTwo` (o un hook de panel similar).
    -   **Salida:** Un bloque en el panel de PrestaShop que muestra los envíos de formularios recientes, proporcionando una visión general rápida para el comerciante.

#### Plantillas de administración (`views/templates/admin/`)

-   `cfrompro/views/templates/admin/button_style_block.tpl`
    -   **Ámbito:** AdminCfromproFormController (página de edición de formularios).
    -   **Salida:** HTML para la sección donde el comerciante configura la apariencia del botón de activación flotante (colores, texto, icono).
-   `cfrompro/views/templates/admin/conversation_reply.tpl`
    -   **Ámbito:** AdminCfromproQuestionController (página de vista de preguntas).
    -   **Salida:** HTML para el formulario de respuesta y la sección de actualización de estado al ver una pregunta enviada.
-   `cfrompro/views/templates/admin/custom_fields_block.tpl`
    -   **Ámbito:** AdminCfromproFormController (página de edición de formularios).
    -   **Salida:** El contenedor principal y los controles para añadir, editar y organizar campos personalizados dentro de un formulario. Esta plantilla probablemente funciona en conjunto con `admin-form-layout.js`.
-   `cfrompro/views/templates/admin/form_layout_block.tpl`
    -   **Ámbito:** AdminCfromproFormController (página de edición de formularios).
    -   **Salida:** Estructura de diseño general para la página de configuración del formulario, envolviendo otros bloques como campos personalizados y estilos de botones.
-   `cfrompro/views/templates/admin/question_extras.tpl`
    -   **Ámbito:** AdminCfromproQuestionController (página de vista de preguntas).
    -   **Salida:** Muestra detalles adicionales relacionados con una pregunta enviada, como archivos adjuntos o metadatos específicos.
-   `cfrompro/views/templates/admin/question_form_profile.tpl`
    -   **Ámbito:** AdminCfromproQuestionController (página de vista de preguntas).
    -   **Salida:** Muestra detalles sobre el formulario desde el que se envió la pregunta.
-   `cfrompro/views/templates/admin/topic_options_block.tpl`
    -   **Ámbito:** AdminCfromproFormController (página de edición de formularios).
    -   **Salida:** Si el módulo admite temas predefinidos, esta plantilla renderizaría las opciones para configurarlos.

#### Plantillas del Front-office (`views/templates/front/` y raíz `views/`)

-   `cfrompro/views/cfrompro-extra-forms.tpl`
    -   **Hook:** Probablemente `displayFooter` o `actionOutputHTMLBefore` para renderizar formularios que no están incrustados directamente sino que aparecen en modales.
    -   **Salida:** Contiene la estructura HTML para formularios que están destinados a mostrarse en una ventana modal, a menudo activada por un botón flotante.
-   `cfrompro/views/cfrompro-extra-trigger.tpl`
    -   **Hook:** Probablemente `displayHeader` o `actionOutputHTMLBefore` para renderizar el botón de activación flotante.
    -   **Salida:** El HTML para el botón flotante que, al hacer clic, abre un formulario de contacto.
-   `cfrompro/views/cfrompro-form-body.tpl`
    -   **Ámbito:** Utilizado por otras plantillas (por ejemplo, `cfrompro-extra-forms.tpl`) o directamente al incrustar un formulario a través de un shortcode.
    -   **Salida:** La estructura HTML principal para un único formulario de contacto, incluidos campos, etiquetas, reCAPTCHA, casilla de verificación GDPR y botón de envío. Esta plantilla se rellena dinámicamente con campos personalizados.
-   `cfrompro/views/classic/cfrompro-extra-forms.tpl`
    -   **Ámbito:** Anulación específica del tema para `cfrompro-extra-forms.tpl`.
    -   **Salida:** Igual que `cfrompro-extra-forms.tpl` pero específicamente adaptado para la estructura HTML del tema Classic.
-   `cfrompro/views/classic/cfrompro-extra-trigger.tpl`
    -   **Ámbito:** Anulación específica del tema para `cfrompro-extra-trigger.tpl`.
    -   **Salida:** Igual que `cfrompro-extra-trigger.tpl` pero específicamente adaptado para el tema Classic.
-   `cfrompro/views/partials/cfrompro-custom-field-single.tpl`
    -   **Ámbito:** Incluido por `cfrompro-form-body.tpl`.
    -   **Salida:** Renderiza el HTML para un único campo personalizado según su tipo (texto, área de texto, selección, etc.).
-   `cfrompro/views/partials/cfrompro-custom-fields.tpl`
    -   **Ámbito:** Incluido por `cfrompro-form-body.tpl`.
    -   **Salida:** Itera a través de las definiciones de campos personalizados para un formulario y renderiza cada uno utilizando `cfrompro-custom-field-single.tpl`.
-   `cfrompro/views/partials/cfrompro-field-fragment.tpl`
    -   **Ámbito:** Incluido por `cfrompro-form-body.tpl` o `cfrompro-custom-field-single.tpl`.
    -   **Salida:** Un fragmento reutilizable de HTML para elementos de campo comunes como etiquetas, mensajes de error o envoltorios.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

-   `ps_cfrompro_form`: Almacena las definiciones de cada formulario de contacto personalizado creado por el módulo.
    -   `id_cfrompro_form`: Clave primaria.
    -   `name`: Nombre interno del formulario.
    -   `shortcode`: Identificador único para incrustar.
    -   `active`: (booleano) Estado del formulario.
    -   `recipient_emails`: (texto) Correos electrónicos de destinatarios anulados para este formulario.
    -   `autoresponder_email`: (texto) Correo electrónico de respuesta automática anulado para este formulario.
    -   `email_title`: (texto) Asunto del correo electrónico anulado para este formulario.
    -   `custom_fields_json`: (texto/JSON) Cadena JSON serializada que contiene las definiciones de todos los campos personalizados para este formulario (tipo, etiqueta, requerido, opciones, validación, etc.).
    -   `trigger_enabled`: (booleano) Si el activador flotante está activo para este formulario.
    -   `trigger_text`: (texto) Texto en el activador flotante.
    -   `trigger_position`: (texto) Posición del activador flotante.
    -   `trigger_icon`: (texto) Clase de icono para el activador.
    -   `trigger_delay_ms`: (int) Retraso para la aparición del activador.
    -   `trigger_color`, `trigger_text_color`, `trigger_hover_color`: (texto) Estilo para el activador.
-   `ps_cfrompro_question`: Almacena cada pregunta/consulta enviada.
    -   `id_cfrompro_question`: Clave primaria.
    -   `id_cfrompro_form`: Clave externa a `ps_cfrompro_form`.
    -   `customer_name`: Nombre del cliente que envía.
    -   `customer_email`: Correo electrónico del cliente que envía.
    -   `customer_phone`: Número de teléfono (si es visible/requerido).
    -   `topic`: Tema seleccionado (si es visible/requerido).
    -   `message`: Contenido principal de la pregunta/mensaje.
    -   `submitted_data_json`: (texto/JSON) Cadena JSON serializada que contiene todos los valores de campos personalizados enviados.
    -   `attachments`: (texto/JSON) Ruta(s) a los archivos subidos.
    -   `ip_address`: Dirección IP del remitente.
    -   `date_add`: Marca de tiempo de envío.
    -   `status`: (int/texto) Estado de la consulta (por ejemplo, 0=Nuevo, 1=En progreso, 2=Resuelto).
-   `ps_configuration`: La configuración del módulo se almacena aquí con claves como `cfrompro_TITLE`, `cfrompro_AUTORESPONDER`, `cfrompro_GDPR`, `cfrompro_recaptcha_sitekey`, etc.

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionOutputHTMLBefore` | Antes de que la salida HTML se envíe al navegador. | Inyectar HTML del activador flotante, formularios modales o CSS/JS personalizado globalmente. |
| `displaydashboardZoneTwo` | Renderiza contenido en la segunda zona del panel de PrestaShop. | Mostrar un resumen de los envíos de formularios recientes en el Back Office. |
| `actionAdminControllerSetMedia` | Cuando un controlador de administración está configurando sus medios (JS/CSS). | Encolar JS (`admin-button-style.js`, `admin-form-layout.js`, etc.) y CSS (`admin-button-style.css`, `admin-custom-fields.css`, etc.) específicos del Back Office para las páginas de configuración del módulo. |
| `displayHeader` | En la sección `<head>` del front-office. | Encolar JS (`cfrompro.js`) y CSS (`cfrompro.css`) específicos del front-office, y potencialmente scripts de reCAPTCHA. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto al módulo **Advanced Contact Form Builder Pro**.

---
title: "Preguntar sobre el producto - formularios de contacto pro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Preguntar sobre el producto - formularios de contacto pro' de MyPresta.eu."
sidebar:
  label: "Preguntar sobre el producto - formularios de contacto pro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Ask about product - contact forms pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/ask-about-product-contact-forms-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/ask-about-product-contact-forms-pro/)
>
> ---


# Preguntar sobre el producto - formularios de contacto pro

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL) para que el módulo funcione correctamente, especialmente para funciones como reCAPTCHA y webhooks. Estas suelen estar disponibles en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

Este módulo ofrece amplias opciones de personalización para adaptar los formularios de contacto a sus necesidades específicas. Repasaremos cada pantalla y ajuste de configuración.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es el área de configuración principal del módulo, a la que se accede directamente después de la instalación o navegando a **Módulos > Gestor de módulos** y haciendo clic en "Configurar" junto a "Preguntar sobre el producto - formularios de contacto pro".

#### Configuración general

- **Perfil de soporte de plantilla**

  - **Qué hace este ajuste:** Este ajuste le permite seleccionar un perfil de plantilla predefinido que mejor se adapte a su tema de PrestaShop. Diferentes temas pueden requerir diferentes estilos o ajustes estructurales para que el formulario se muestre correctamente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "Classic" (o similar):* El módulo utilizará plantillas y estilos optimizados para el tema Classic predeterminado de PrestaShop o temas basados en él.
    - *Cuando se establece en un perfil de tema específico:* El módulo cargará plantillas y CSS diseñados para integrarse sin problemas con ese tema en particular, asegurando una mejor coherencia visual.
  - **Valor recomendado:** Elija el perfil que corresponda a su tema activo de PrestaShop. Si no está seguro, comience con "Classic" y ajuste si surgen problemas de estilo.
  - **Escenario/ejemplo del comerciante:** Si está utilizando un tema personalizado, es posible que deba probar diferentes perfiles o usar la opción "CSS personalizado" para ajustar la apariencia.
- **Título del correo electrónico (para el propietario de la tienda)**

  - **Qué hace este ajuste:** Esta es la línea de asunto para la notificación por correo electrónico que *usted* (el propietario/administrador de la tienda) recibe cuando un cliente envía una pregunta.
  - **Efecto de cambiar este ajuste:** Cambia la línea de asunto de los correos electrónicos de notificación internos.
  - **Valor recomendado:** Algo claro e informativo, como "Nueva pregunta de producto de su tienda - [Nombre del producto]".
  - **Escenario/ejemplo del comerciante:** Establecer esto en "URGENTE: Nueva consulta para [Nombre del producto]" puede ayudar a su equipo a priorizar.
- **Correo(s) electrónico(s) del destinatario**

  - **Qué hace este ajuste:** Especifica la(s) dirección(es) de correo electrónico a la(s) que se enviarán las consultas de productos. Puede introducir varios correos electrónicos separados por comas.
  - **Efecto de cambiar este ajuste:** Determina quién en su organización recibe las preguntas de los clientes.
  - **Valor recomendado:** La dirección de correo electrónico de su equipo de atención al cliente o del departamento relevante.
  - **Escenario/ejemplo del comerciante:** Si tiene una dirección dedicada "[ventas@sutienda.com](mailto:ventas@sutienda.com)" o "[soporte@sutienda.com](mailto:soporte@sutienda.com)", introdúzcala aquí. Para equipos más grandes, puede enviarla a una lista de distribución.
- **CCO para el correo electrónico de notificación de la tienda**

  - **Qué hace este ajuste:** Le permite enviar una copia oculta (CCO) del correo electrónico de notificación de la tienda a direcciones de correo electrónico adicionales. Estos destinatarios no serán visibles para el destinatario principal.
  - **Efecto de cambiar este ajuste:** Proporciona una forma discreta de notificar a otros miembros del equipo o archivar consultas sin saturar la bandeja de entrada del destinatario principal ni revelar destinatarios adicionales.
  - **Valor recomendado:** Déjelo vacío a menos que tenga una necesidad específica de seguimiento interno o notificaciones secundarias.
  - **Escenario/ejemplo del comerciante:** Puede enviar una CCO a su gerente de marketing para rastrear el interés del cliente, o a una dirección de correo electrónico de archivo interno.
- **Correo electrónico de respuesta automática**

  - **Qué hace este ajuste:** Esta es la línea de asunto para el correo electrónico automático enviado *al cliente* después de que envía una pregunta.
  - **Efecto de cambiar este ajuste:** Cambia la línea de asunto del correo electrónico de confirmación que reciben sus clientes.
  - **Valor recomendado:** "Gracias por su consulta - [Nombre de su tienda]".
  - **Escenario/ejemplo del comerciante:** Un asunto claro de respuesta automática asegura al cliente que su mensaje fue recibido.
- **Duración del mensaje de éxito (ms)**

  - **Qué hace este ajuste:** Controla cuánto tiempo permanece visible en la pantalla la notificación "Su mensaje ha sido enviado con éxito" después de que un cliente envía un formulario, medido en milisegundos (ms).
  - **Efecto de cambiar este ajuste:**
    - *Valor más alto (por ejemplo, 5000ms):* El mensaje permanece visible más tiempo, dando a los clientes más tiempo para leerlo.
    - *Valor más bajo (por ejemplo, 2000ms):* El mensaje desaparece rápidamente.
  - **Valor recomendado:** 3000-5000ms (3-5 segundos) suele ser un buen equilibrio.
  - **Escenario/ejemplo del comerciante:** Si sus clientes a menudo tienen conexiones más lentas o necesitan más tiempo para procesar la información, una duración más larga podría ser beneficiosa.
- **Ocultar "Hacer una pregunta" para productos agotados (aappro_HIDE_OOS)**

  - **Qué hace este ajuste:** Si está habilitado, el formulario o botón "Hacer una pregunta" no se mostrará en las páginas de productos donde el producto está actualmente agotado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Evita que los clientes pregunten sobre productos no disponibles, lo que podría reducir las consultas irrelevantes para su equipo.
    - *Cuando está deshabilitado:* El formulario permanece visible independientemente del estado del stock.
  - **Valor recomendado:** "Sí" para reducir las consultas sobre artículos no disponibles, a menos que desee específicamente captar interés para futuras reposiciones.
  - **Escenario/ejemplo del comerciante:** Si vende artículos únicos o de edición limitada que no se repondrán, ocultar el formulario para productos agotados tiene sentido. Si desea evaluar el interés para futuras reposiciones, manténgalo deshabilitado.
- **Permitir que solo los clientes registrados hagan preguntas (aappro_LOGGED_CUSTOMERS_ONLY)**

  - **Qué hace este ajuste:** Restringe la capacidad de enviar preguntas sobre productos solo a los clientes que han iniciado sesión en sus cuentas de tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los usuarios no registrados o invitados no verán ni podrán usar el formulario "Hacer una pregunta". Esto puede ayudar a reducir el spam y garantizar que tenga los detalles de la cuenta del cliente vinculados a las consultas.
    - *Cuando está deshabilitado:* Cualquiera puede enviar una pregunta, incluidos los invitados.
  - **Valor recomendado:** "No" para el máximo alcance del cliente, "Sí" si prioriza la participación de clientes registrados y desea reducir las consultas anónimas.
  - **Escenario/ejemplo del comerciante:** Si tiene una tienda B2B donde todas las interacciones requieren una cuenta, habilitar esto sería apropiado. Para una tienda minorista general, mantenerlo deshabilitado suele ser mejor para la conversión.

#### Campos del formulario y validación

- **Sí / No (aappro_FIELD_PHONE_REQUIRED, aappro_FIELD_PHONE_VISIBLE, aappro_FIELD_TOPIC_VISIBLE, aappro_QUOTE_QUANTITY_VISIBLE)**

  - **Qué hace este ajuste:** Son un grupo de interruptores "Sí/No" que controlan la visibilidad y la obligatoriedad de campos específicos dentro de sus formularios de consulta de productos:
    - **Número de teléfono visible:** Muestra el campo del número de teléfono.
    - **Número de teléfono obligatorio:** Hace que el campo del número de teléfono sea obligatorio si es visible.
    - **Selección de tema visible:** Muestra un desplegable para que los clientes seleccionen un tema para su pregunta (por ejemplo, "Envío", "Especificaciones técnicas", "Disponibilidad").
    - **Cantidad de presupuesto visible:** Muestra un campo donde los clientes pueden solicitar un presupuesto para una cantidad específica del producto.
  - **Efecto de cambiar este ajuste:**
    - *Habilitado (Visible):* El campo aparece en el formulario.
    - *Deshabilitado (Visible):* El campo está oculto.
    - *Habilitado (Obligatorio):* El cliente *debe* rellenar el campo para enviar el formulario.
  - **Valor recomendado:**
    - **Teléfono:** Visible "No", Obligatorio "No" (a menos que el contacto telefónico sea crítico para su modelo de negocio).
    - **Tema:** Visible "Sí" (ayuda a categorizar las consultas), Obligatorio "No".
    - **Cantidad de presupuesto:** Visible "Sí" (si ofrece descuentos por volumen o ventas B2B), Obligatorio "No".
  - **Escenario/ejemplo del comerciante:** Si vende productos electrónicos complejos, hacer visible la "Selección de tema" con opciones como "Soporte técnico" o "Compatibilidad" sería muy útil. Si es mayorista, la "Cantidad de presupuesto" es esencial.
- **Longitud mínima de la pregunta (caracteres)**

  - **Qué hace este ajuste:** Establece el número mínimo de caracteres que un cliente debe escribir en el campo de la pregunta antes de poder enviar el formulario.
  - **Efecto de cambiar este ajuste:** Evita preguntas muy cortas, potencialmente inútiles o de spam.
  - **Valor recomendado:** 10-20 caracteres.
  - **Escenario/ejemplo del comerciante:** Establecer esto en 15 caracteres asegura que los clientes proporcionen suficientes detalles más allá de solo "Pregunta".
- **Longitud máxima de la pregunta (caracteres)**

  - **Qué hace este ajuste:** Establece el número máximo de caracteres que un cliente puede escribir en el campo de la pregunta.
  - **Efecto de cambiar este ajuste:** Evita preguntas excesivamente largas que podrían ser difíciles de leer o indicar que un cliente intenta usar el formulario como un chat general.
  - **Valor recomendado:** 500-1000 caracteres.
  - **Escenario/ejemplo del comerciante:** Un límite de 750 caracteres suele ser suficiente para la mayoría de las consultas de productos.
- **Permitir adjuntar imágenes**

  - **Qué hace este ajuste:** Permite a los clientes subir un archivo de imagen (por ejemplo, una captura de pantalla, una foto de un artículo dañado o un diagrama) junto con su pregunta.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparece un campo "Subir archivo" en el formulario.
    - *Cuando está deshabilitado:* No hay opción de adjuntar.
  - **Valor recomendado:** "Sí" puede ser muy útil para consultas visuales, pero asegúrese de que su servidor pueda manejar el almacenamiento.
  - **Escenario/ejemplo del comerciante:** Un cliente podría querer adjuntar una foto de una parte específica de un producto sobre la que tiene una pregunta, o una captura de pantalla de un error que está encontrando.
- **Tamaño máximo del archivo adjunto (MB)**

  - **Qué hace este ajuste:** Si la opción de adjuntar imágenes está habilitada, esto establece el tamaño máximo del archivo (en megabytes) permitido para cada archivo adjunto.
  - **Efecto de cambiar este ajuste:** Controla la carga del servidor y el uso del almacenamiento.
  - **Valor recomendado:** 2-5 MB suele ser suficiente para la mayoría de las imágenes.
  - **Escenario/ejemplo del comerciante:** Establecerlo en 3MB evita que los clientes suban imágenes muy grandes y de alta resolución que no son necesarias para una consulta.

#### Seguridad y cumplimiento

- **Cumple con el RGPD**

  - **Qué hace este ajuste:** Habilita funciones para ayudar a sus formularios a cumplir con los requisitos del RGPD (Reglamento General de Protección de Datos), típicamente añadiendo una casilla de verificación para el consentimiento al procesamiento de datos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá una casilla de verificación en el formulario, que requerirá que los clientes acepten explícitamente su política de privacidad antes de enviar su pregunta.
    - *Cuando está deshabilitado:* No se muestra ninguna casilla de verificación de consentimiento del RGPD.
  - **Valor recomendado:** "Sí" si su tienda opera o atiende a clientes en regiones sujetas al RGPD (por ejemplo, la UE).
  - **Escenario/ejemplo del comerciante:** Si vende a clientes en Europa, habilitar esto es legalmente importante.
- **Página de política de privacidad**

  - **Qué hace este ajuste:** Si el cumplimiento del RGPD está habilitado, este ajuste le permite seleccionar la página CMS que contiene la política de privacidad de su tienda. La casilla de verificación de consentimiento del RGPD se vinculará a esta página.
  - **Efecto de cambiar este ajuste:** Proporciona a los clientes un fácil acceso a su política de privacidad, cumpliendo un requisito clave del RGPD.
  - **Valor recomendado:** Seleccione su página CMS dedicada a la Política de Privacidad.
  - **Escenario/ejemplo del comerciante:** Después de habilitar el RGPD, debe seleccionar la página CMS correcta para que los clientes puedan revisar sus prácticas de manejo de datos.
- **ReCaptcha (v2)**

  - **Qué hace este ajuste:** Integra Google reCAPTCHA v2 (la casilla de verificación "No soy un robot") en sus formularios para evitar el spam y los envíos de bots.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* La casilla de verificación reCAPTCHA aparece en el formulario, requiriendo la interacción del usuario para demostrar que es humano.
    - *Cuando está deshabilitado:* No se utiliza reCAPTCHA.
  - **Valor recomendado:** "Sí" para reducir significativamente el spam, especialmente si experimenta muchos envíos de bots.
  - **Escenario/ejemplo del comerciante:** Si recibe muchas consultas basura, habilitar reCAPTCHA es una defensa sólida.
- **Clave del sitio ReCaptcha**

  - **Qué hace este ajuste:** Esta es la clave pública proporcionada por Google cuando registra su sitio web para reCAPTCHA. Se utiliza para mostrar el widget reCAPTCHA en su sitio.
  - **Efecto de cambiar este ajuste:** Esencial para que reCAPTCHA funcione. Sin ella, reCAPTCHA no aparecerá ni funcionará.
  - **Valor recomendado:** Su clave de sitio reCAPTCHA única de Google.
  - **Escenario/ejemplo del comerciante:** Deberá ir a la consola de administración de Google reCAPTCHA, registrar su dominio y copiar esta clave en la configuración del módulo.
- **Clave secreta de ReCaptcha**

  - **Qué hace este ajuste:** Esta es la clave privada proporcionada por Google, utilizada para la verificación del lado del servidor de la respuesta de reCAPTCHA.
  - **Efecto de cambiar este ajuste:** Esencial para que reCAPTCHA funcione de forma segura. El módulo utiliza esta clave para confirmar que el usuario realmente pasó el desafío reCAPTCHA.
  - **Valor recomendado:** Su clave secreta reCAPTCHA única de Google.
  - **Escenario/ejemplo del comerciante:** Esta clave debe mantenerse confidencial y nunca exponerse en el código del lado del cliente.

#### Integración y personalización

- **URL de Webhook (Slack/Discord)**

  - **Qué hace este ajuste:** Le permite enviar notificaciones de nuevas consultas de productos a una URL de webhook, típicamente utilizada para servicios como Slack o Discord.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se proporciona una URL:* Las nuevas consultas activarán una notificación al canal de chat especificado.
    - *Cuando está vacío:* No se envían notificaciones de webhook.
  - **Valor recomendado:** Déjelo vacío a menos que utilice activamente Slack, Discord u otro servicio que admita webhooks entrantes para la comunicación en equipo.
  - **Escenario/ejemplo del comerciante:** Su equipo de atención al cliente utiliza Slack. Puede configurar un webhook entrante en Slack y pegar su URL aquí, para que cada nueva pregunta de producto aparezca inmediatamente en su canal #soporte-al-cliente.
- **CSS personalizado (solo página de producto)**

  - **Qué hace este ajuste:** Proporciona un área de texto donde puede añadir reglas CSS personalizadas para estilizar el formulario de consulta de producto específicamente en las páginas de producto.
  - **Efecto de cambiar este ajuste:** Le permite anular los estilos predeterminados del módulo o los estilos de su tema para que coincidan perfectamente con la estética de su marca sin modificar directamente los archivos del módulo.
  - **Valor recomendado:** Úselo con moderación para ajustes menores. Para un estilo importante, considere las anulaciones del tema.
  - **Escenario/ejemplo del comerciante:** Desea cambiar el color del botón "Enviar" al color principal de su marca, o ajustar el espaciado alrededor de los campos del formulario. Puede añadir `.aappro-form-submit-button { background-color: #FF0000; }` aquí.
- **Campos personalizados (aappro_CUSTOM_FIELDS_JSON)**

  - **Qué hace este ajuste:** Esta es una característica potente que le permite definir campos adicionales y personalizados para sus formularios de contacto. Puede especificar tipos de campo (texto, área de texto, selección, casilla de verificación), etiquetas y si son obligatorios. Esto se gestiona típicamente a través de una interfaz dedicada, no un campo JSON sin procesar.
  - **Efecto de cambiar este ajuste:** Añade nuevos campos de entrada a sus formularios, lo que le permite recopilar información más específica de los clientes.
  - **Valor recomendado:** Añada campos relevantes para sus productos o servicios (por ejemplo, "Número de pedido" para clientes existentes, "Uso previsto" para B2B).
  - **Escenario/ejemplo del comerciante:** Para una tienda de ropa, podría añadir un campo personalizado "Talla deseada" si los clientes suelen preguntar por tallas específicas no listadas. Para una tienda de tecnología, "Modelo de dispositivo actual" podría ser útil.
- **Permitir comentarios (aappro_ALLOW_COMMENTS)**

  - **Qué hace este ajuste:** Este ajuste probablemente controla si los clientes pueden dejar comentarios generales en la página del producto, posiblemente separados del formulario específico de "Hacer una pregunta".
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Puede aparecer una sección de comentarios generales.
    - *Cuando está deshabilitado:* Solo está disponible el formulario estructurado "Hacer una pregunta".
  - **Valor recomendado:** "No" si desea mantener la comunicación centrada a través del formulario de preguntas estructurado. "Sí" si desea fomentar una discusión pública más amplia.
  - **Escenario/ejemplo del comerciante:** Si prefiere consultas directas y privadas en lugar de comentarios públicos, deshabilite esto.
- **PS_STOCK_MANAGEMENT**

  - **Qué hace este ajuste:** Esta es una configuración central de PrestaShop, no controlada directamente por el módulo, pero el módulo podría leer su valor. Determina si la gestión de stock está habilitada globalmente en su tienda.
  - **Efecto de cambiar este ajuste:** Si la gestión de stock está deshabilitada, la configuración del módulo "Ocultar para productos agotados" podría no funcionar como se espera, ya que los productos no tendrán un estado de stock claro.
  - **Valor recomendado:** "Sí" para la mayoría de las tiendas de comercio electrónico para rastrear con precisión el inventario.
  - **Escenario/ejemplo del comerciante:** Si vende productos digitales, podría deshabilitar la gestión de stock. Sin embargo, para productos físicos, es crucial.
- **PS_LANG_DEFAULT, PS_BO_ALLOW_EMPLOYEE_FORM_LANG**

  - **Qué hacen estos ajustes:** Estas son configuraciones centrales de PrestaShop relacionadas con el idioma. `PS_LANG_DEFAULT` establece el idioma predeterminado del front-office, y `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` permite a los empleados elegir su idioma del back-office. El módulo utiliza estos para asegurar una visualización adecuada del idioma para formularios y notificaciones.
  - **Efecto de cambiar estos ajustes:** Afecta el idioma de los formularios y las notificaciones.
  - **Valor recomendado:** Establezca `PS_LANG_DEFAULT` en el idioma principal de su tienda. `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` se puede habilitar si tiene un equipo multilingüe.
  - **Escenario/ejemplo del comerciante:** Si el idioma principal de su tienda es el francés, asegúrese de que `PS_LANG_DEFAULT` esté configurado en francés.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración principal | Perfil de soporte de plantilla | Su tema / Classic | Asegura el estilo y la integración correctos con su tema. |
| Configuración principal | Título del correo electrónico (para el propietario de la tienda) | "Nueva pregunta de producto" | Línea de asunto para los correos electrónicos de notificación interna del administrador. |
| Configuración principal | Correo(s) electrónico(s) del destinatario | Su correo electrónico de administrador | Dónde se envían las preguntas de los clientes. |
| Configuración principal | CCO para el correo electrónico de notificación de la tienda | Vacío | Envía discretamente copias de las notificaciones a otros. |
| Configuración principal | Correo electrónico de respuesta automática | "Gracias por su consulta" | Línea de asunto para los correos electrónicos de confirmación del cliente. |
| Configuración principal | Duración del mensaje de éxito (ms) | 3000-5000 | Cuánto tiempo permanece visible la notificación de "mensaje enviado". |
| Configuración principal | Ocultar para productos agotados | Sí | Evita preguntas sobre productos no disponibles. |
| Configuración principal | Permitir solo clientes registrados | No | Restringe el acceso al formulario a usuarios registrados. |
| Configuración principal | Número de teléfono visible | No | Muestra/oculta el campo del número de teléfono. |
| Configuración principal | Número de teléfono obligatorio | No | Hace que el número de teléfono sea obligatorio si es visible. |
| Configuración principal | Selección de tema visible | Sí | Muestra/oculta un desplegable para los temas de las preguntas. |
| Configuración principal | Cantidad de presupuesto visible | Sí (si es B2B) | Muestra/oculta un campo para solicitudes de presupuesto por cantidad. |
| Configuración principal | Longitud mínima de la pregunta | 15 caracteres | Evita preguntas demasiado cortas. |
| Configuración principal | Longitud máxima de la pregunta | 750 caracteres | Evita preguntas demasiado largas. |
| Configuración principal | Permitir adjuntar imágenes | Sí | Permite a los clientes subir archivos. |
| Configuración principal | Tamaño máximo del archivo adjunto (MB) | 3 MB | Limita el tamaño de los archivos subidos. |
| Configuración principal | Cumple con el RGPD | Sí (si aplica) | Añade una casilla de verificación de consentimiento para el procesamiento de datos. |
| Configuración principal | Página de política de privacidad | Su CMS de política de privacidad | Vincula la casilla de verificación del RGPD a su página de política. |
| Configuración principal | ReCaptcha (v2) | Sí | Integra Google reCAPTCHA para protección contra spam. |
| Configuración principal | Clave del sitio ReCaptcha | Su clave de sitio de Google | Clave pública para la visualización del widget reCAPTCHA. |
| Configuración principal | Clave secreta de ReCaptcha | Su clave secreta de Google | Clave privada para la verificación del lado del servidor de reCAPTCHA. |
| Configuración principal | URL de Webhook (Slack/Discord) | Vacío | Envía notificaciones a servicios de chat externos. |
| Configuración principal | CSS personalizado (solo página de producto) | Vacío | Añade CSS personalizado para estilizar el formulario. |
| Configuración principal | Campos personalizados | Configurado a través de AdminAapproForm | Define campos adicionales para sus formularios. |
| Configuración principal | Permitir comentarios | No | Controla los comentarios generales del producto frente a las preguntas estructuradas. |

### 2.2 Pantallas de administración dedicadas y vistas de controlador

Más allá de la configuración principal, este módulo proporciona secciones dedicadas en su Back Office de PrestaShop para gestionar formularios, preguntas y campos personalizados.

#### 2.2.1 AdminAapproFormController: Gestión de formularios (Back Office > Módulos > Preguntar sobre el producto > Formularios)

Esta pantalla le permite crear y gestionar diferentes formularios de consulta de productos y especificar dónde aparecen en su tienda.

- **Nombre de la pantalla y ubicación del menú:** **Módulos > Preguntar sobre el producto > Formularios**
- **Acciones y ajustes disponibles:**
  - **Tabla de listado:** Muestra todos sus formularios creados con sus nombres, estado y productos/categorías/fabricantes asociados.
  - **Botón Añadir nuevo formulario:** Haga clic para crear un nuevo formulario.
  - **Acciones de editar/eliminar:** Modifique o elimine formularios existentes.
  - **Campos del formulario:** Al añadir o editar un formulario, configurará:
    - **Nombre del formulario:** Nombre interno para su referencia.
    - **Activo:** Habilita o deshabilita el formulario.
    - **Mostrar en la página del producto:** Elija si este formulario debe aparecer en las páginas de producto.
    - **Mostrar en la página de categoría:** Elija si este formulario debe aparecer en las páginas de categoría.
    - **Mostrar en la página del fabricante:** Elija si este formulario debe aparecer en las páginas del fabricante.
    - **Correo(s) electrónico(s) del destinatario para este formulario:** Anule el correo electrónico del destinatario global para este formulario específico. Esto es crucial para dirigir las preguntas a equipos específicos.
    - **Productos:** Seleccione productos específicos donde debe aparecer este formulario.
    - **Categorías:** Seleccione categorías específicas donde debe aparecer este formulario.
    - **Fabricantes:** Seleccione fabricantes específicos donde debe aparecer este formulario.
    - **Campos personalizados:** Aquí es donde define los campos únicos para *este formulario específico*. Puede añadir entradas de texto, áreas de texto, desplegables, casillas de verificación, etc., y marcarlos como obligatorios.
- **Efecto de los cambios:**
  - La creación de un nuevo formulario le permite definir un conjunto único de preguntas y reglas de enrutamiento.
  - La asociación de formularios con productos, categorías o fabricantes específicos significa que solo se mostrará ese formulario en particular cuando un cliente vea un artículo que coincida con esos criterios.
  - La anulación de los correos electrónicos de los destinatarios garantiza que las preguntas sobre, por ejemplo, "Electrónica" vayan al departamento de electrónica, mientras que las preguntas sobre "Ropa" vayan al equipo de moda.
  - Los campos personalizados le permiten recopilar información altamente específica relevante para el contexto del formulario.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. **Identificar necesidades:** Determine si necesita diferentes formularios para diferentes tipos de productos, departamentos o segmentos de clientes.
  2. **Crear formularios:** Vaya a **Formularios** y haga clic en "Añadir nuevo formulario".
  3. **Configurar enrutamiento:** Establezca los "Correo(s) electrónico(s) del destinatario para este formulario" específicos para asegurar que las preguntas vayan al lugar correcto.
  4. **Definir alcance:** Utilice los selectores de "Productos", "Categorías" y "Fabricantes" para controlar dónde aparece cada formulario.
  5. **Añadir campos personalizados:** Adapte las preguntas formuladas en cada formulario utilizando la sección "Campos personalizados" para recopilar información relevante.
  6. **Probar:** Siempre pruebe sus formularios en el front-office para asegurarse de que aparecen correctamente y envían correos electrónicos a los destinatarios correctos.

#### 2.2.2 AdminAapproQuestionController: Gestión de preguntas (Back Office > Módulos > Preguntar sobre el producto > Preguntas)

Esta pantalla sirve como su centro neurálgico para ver y gestionar todas las preguntas enviadas por los clientes.

- **Nombre de la pantalla y ubicación del menú:** **Módulos > Preguntar sobre el producto > Preguntas**
- **Tabla / Entidad gestionada:** `aappro_question` (almacena todas las consultas enviadas)
- **Campos y columnas del formulario:**
  - **Vista de cuadrícula / gestión:** Muestra una lista de todas las preguntas enviadas.
    - **Columnas:** Normalmente incluye: Nombre del cliente, Correo electrónico del cliente, Nombre del producto (si aplica), Tema de la pregunta, Fecha de envío, Estado (por ejemplo, Nuevo, Respondido, Cerrado).
    - **Filtrado y clasificación:** Funciones estándar de la lista de PrestaShop para filtrar por fecha, cliente, producto o estado.
  - **Acción Ver/Responder:** Al hacer clic en una pregunta, puede ver sus detalles completos y responder al cliente.
    - **Detalles de la pregunta:** Muestra el mensaje completo del cliente, la información de contacto, los detalles del producto y cualquier archivo adjunto.
    - **Interfaz de respuesta:** Un área de texto para redactar su respuesta, que se enviará directamente a la dirección de correo electrónico del cliente.
    - **Actualización de estado:** Opción para cambiar el estado de la pregunta (por ejemplo, de "Nuevo" a "Respondido").
- **Efecto de los cambios:**
  - Esta pantalla proporciona una bandeja de entrada centralizada para todas las consultas relacionadas con productos, lo que facilita el seguimiento y la respuesta.
  - Responder directamente desde aquí garantiza que el historial de conversaciones se mantenga dentro de PrestaShop y se vincule al producto específico.
  - La actualización del estado ayuda a su equipo a gestionar la carga de trabajo y garantiza que no se pierda ninguna pregunta.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. **Revisar regularmente:** Adquiera el hábito de revisar esta sección diariamente (o varias veces al día, según el volumen).
  2. **Priorizar:** Utilice filtros para identificar preguntas urgentes o sin respuesta.
  3. **Ver y responder:** Haga clic en "Ver" en una pregunta, lea los detalles y redacte una respuesta clara y útil.
  4. **Actualizar estado:** Después de responder, cambie el estado de la pregunta a "Respondido" o "Cerrado" para mantener su cola organizada.
  5. **Utilizar el contexto del producto:** El módulo vincula automáticamente la pregunta al producto, por lo que tiene todo el contexto necesario al responder.

#### 2.2.3 index.php (aappro/controllers/admin/index.php)

Este archivo es una práctica estándar de PrestaShop para evitar la lista directa de directorios en el Back Office. Normalmente contiene un simple `header('Location: ../../index.php?controller=AdminHome');` o una redirección similar, asegurando que si alguien intenta acceder al directorio `controllers/admin/` directamente, sea enviado de vuelta al panel de administración principal. No gestiona ninguna entidad específica ni tiene campos configurables.

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

- **P: Mi formulario no aparece en la página del producto.**

  - **R:**
    1. **Verificar el estado del módulo:** Asegúrese de que el módulo esté instalado y habilitado en **Módulos > Gestor de módulos**.
    2. **Verificar la configuración del formulario:** Vaya a **Módulos > Preguntar sobre el producto > Formularios**. Asegúrese de que el formulario específico que espera ver esté "Activo" y correctamente asociado con el producto, categoría o fabricante que está viendo.
    3. **Ubicación del hook:** Verifique que el módulo esté enganchado a un área de visualización que su tema renderice (por ejemplo, `displayProductExtraContent`, `displayProductAdditionalInfo`). A veces, los temas anulan las posiciones predeterminadas de los hooks.
    4. **Compatibilidad del tema:** Si está utilizando un tema altamente personalizado, intente cambiar temporalmente al tema Classic predeterminado para ver si aparece el formulario. Si lo hace, podría haber un conflicto con los archivos de plantilla o CSS de su tema personalizado.
    5. **Caché:** Borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**).
- **P: No recibo notificaciones por correo electrónico cuando un cliente envía una pregunta.**

  - **R:**
    1. **Verificar los correos electrónicos del destinatario:** Verifique los "Correo(s) electrónico(s) del destinatario" en la configuración principal del módulo y también los "Correo(s) electrónico(s) del destinatario para este formulario" específicos dentro de la configuración del formulario (**Módulos > Preguntar sobre el producto > Formularios > Editar formulario**). Asegúrese de que sean correctos y no contengan errores tipográficos.
    2. **Carpeta de spam:** Revise la carpeta de spam o correo no deseado de su correo electrónico.
    3. **Configuración de correo del servidor:** Asegúrese de que la configuración de correo electrónico de su tienda PrestaShop esté configurada correctamente (**Parámetros avanzados > Correo electrónico**). Envíe un correo electrónico de prueba desde PrestaShop para confirmar que su servidor puede enviar correos electrónicos.
    4. **Proveedor de alojamiento:** Póngase en contacto con su proveedor de alojamiento para verificar si hay restricciones o problemas de envío de correo electrónico del lado del servidor.
    5. **Registros del módulo:** Verifique los registros de errores de PrestaShop (si están disponibles) o los registros de errores de PHP de su servidor para detectar cualquier error relacionado con el correo.
- **P: El reCAPTCHA no funciona o no aparece.**

  - **R:**
    1. **Habilitar reCAPTCHA:** Asegúrese de que "ReCaptcha (v2)" esté configurado en "Sí" en la configuración principal del módulo.
    2. **Claves:** Verifique que su "Clave del sitio ReCaptcha" y "Clave secreta de ReCaptcha" estén correctamente introducidas y coincidan con las claves de su cuenta de Google reCAPTCHA para su dominio.
    3. **Registro de dominio:** Asegúrese de que su dominio esté correctamente registrado en la consola de administración de Google reCAPTCHA.
    4. **Problemas del navegador:** Pruebe en diferentes navegadores y borre la caché del navegador. A veces, los bloqueadores de anuncios pueden interferir con reCAPTCHA.
- **P: ¿Cómo traduzco los campos del formulario y los mensajes a otros idiomas?**

  - **R:**
    1. Vaya a **Internacional > Traducciones**.
    2. Seleccione "Traducciones de módulos instalados".
    3. Elija su tema, el idioma que desea traducir y luego seleccione "Preguntar sobre el producto - formularios de contacto pro" de la lista de módulos.
    4. Luego puede traducir todas las cadenas visibles, etiquetas de campo y mensajes utilizados por el módulo. Recuerde guardar sus cambios.
- **P: El estilo del formulario se ve mal con mi tema personalizado.**

  - **R:**
    1. **Perfil de soporte de plantilla:** Intente ajustar la configuración "Perfil de soporte de plantilla" en la configuración principal del módulo para ver si un perfil diferente funciona mejor.
    2. **CSS personalizado:** Utilice el campo "CSS personalizado (solo página de producto)" en la configuración del módulo para añadir reglas CSS específicas para anular o ajustar el estilo. Necesitará conocimientos básicos de CSS o un desarrollador web para esto.
    3. **Anulaciones de tema:** Para cambios más extensos, un desarrollador podría necesitar crear anulaciones de tema para los archivos de plantilla (`.tpl`) o archivos CSS del módulo, colocándolos en el directorio `modules/aappro/` de su tema.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada del módulo "Preguntar sobre el producto - formularios de contacto pro", destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Resumen de la arquitectura

El módulo sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, extendiendo las clases principales de PrestaShop para su funcionalidad. Utiliza `ModuleFrontController` para las interacciones del front-office (envío de formularios, respuestas) y `AdminController` para la gestión del back-office de formularios y preguntas. Se utilizan clases `ObjectModel` personalizadas (`AapproCustomFields`, `AapproFormMatcher`) para persistir los datos específicos del módulo. Los hooks se utilizan ampliamente para integrar el formulario en varias partes del front-office.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `AapproIndexModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Probablemente maneja la representación inicial del formulario o un disparador para el formulario, potencialmente a través de AJAX. Podría preparar datos para la plantilla del formulario.
- `controllers/front/question.php`
  - **Nombre de la clase y clase padre:** `AapproQuestionModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador es responsable de procesar el envío del formulario de consulta de producto. Valida la entrada, maneja la verificación de reCAPTCHA, procesa las cargas de archivos (si están habilitadas), guarda la pregunta en la base de datos, envía notificaciones por correo electrónico al propietario de la tienda y, potencialmente, una respuesta automática al cliente. Devuelve respuestas JSON para envíos AJAX.
- `controllers/front/reply.php`
  - **Nombre de la clase y clase padre:** `AapproReplyModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador probablemente maneja el mecanismo de respuesta orientado al cliente, si el módulo permite a los clientes ver las respuestas en el front-office o proporciona un enlace específico para ver las respuestas. Obtendría la pregunta y las respuestas asociadas.

#### Controladores de administración de Back-Office

- `controllers/admin/AdminAapproForm.php`
  - **Nombre de la clase y clase padre:** `AdminAapproFormController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Gestiona formularios de consulta personalizados. Accesible a través de **Módulos > Preguntar sobre el producto > Formularios**. Maneja las operaciones CRUD para objetos `AapproFormMatcher`, incluida la definición de nombres de formularios, estado de activación, productos/categorías/fabricantes asociados y campos personalizados.
- `controllers/admin/AdminAapproQuestion.php`
  - **Nombre de la clase y clase padre:** `AdminAapproQuestionController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Gestiona las preguntas enviadas por los clientes. Accesible a través de **Módulos > Preguntar sobre el producto > Preguntas**. Proporciona una vista de lista de preguntas, permite ver los detalles completos de las preguntas y ofrece una interfaz para responder a los clientes y actualizar el estado de las preguntas.
- `controllers/admin/index.php`
  - **Nombre de la clase y clase padre:** No es un controlador funcional.
  - **Responsabilidad:** Archivo de seguridad estándar de PrestaShop para evitar la lista de directorios. Normalmente redirige al panel de administración.

### 4.3 Clases y modelos principales (`classes/`)

- `classes/AapproCustomFields.php`
  - **Con qué tabla de base de datos interactúa:** Probablemente `ps_aappro_custom_field` (o similar).
  - **Extiende ObjectModel:** Sí, extiende `ObjectModel`.
  - **Campos `$definition`:** Definiría campos como `id_aappro_custom_field`, `id_aappro_form`, `name`, `type`, `label`, `required`, `options` (para campos de selección, a menudo codificados en JSON), `position`, `active`.
  - **Métodos públicos clave y lógica de negocio:** Métodos para guardar, recuperar y eliminar definiciones de campos personalizados asociados con formularios específicos. Lógica para analizar y renderizar datos de campos personalizados.
- `classes/AapproFormMatcher.php`
  - **Con qué tabla de base de datos interactúa:** Probablemente `ps_aappro_form` (o similar).
  - **Extiende ObjectModel:** Sí, extiende `ObjectModel`.
  - **Campos `$definition`:** Definiría campos como `id_aappro_form`, `name`, `active`, `recipient_emails`, `products` (array de IDs de producto codificado en JSON), `categories` (array de IDs de categoría codificado en JSON), `manufacturers` (array de IDs de fabricante codificado en JSON), `display_product`, `display_category`, `display_manufacturer`.
  - **Métodos públicos clave y lógica de negocio:** Métodos para gestionar configuraciones de formularios, incluida la asociación de guardado con productos/categorías/fabricantes, y la recuperación del formulario correcto según el contexto actual (ID de producto, ID de categoría).

### 4.4 Activos JavaScript (`views/js/`)

- `aappro/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office.
  - **Descripción:** Proporciona funcionalidad de autocompletado para seleccionar productos, categorías o fabricantes al configurar formularios en `AdminAapproFormController`. Se vincula a los campos de entrada para sugerir entidades a medida que el usuario escribe, mejorando la UX para la asociación de formularios.
- `aappro/views/aappro.js`
  - **Alcance:** Front-office.
  - **Descripción:** Script principal del front-office para el módulo.
    - **Escuchadores de eventos:** Vincula eventos de clic a botones/enlaces "Hacer una pregunta", eventos de envío a los formularios de consulta.
    - **Manipulación del DOM:** Maneja la visualización/ocultación del formulario (por ejemplo, en un modal o sección expandible), mostrando mensajes de éxito/error (notificaciones toast).
    - **Llamadas AJAX:** Envía datos del formulario de forma asíncrona a `AapproQuestionModuleFrontController`, maneja la respuesta de reCAPTCHA y actualiza la interfaz de usuario en función de la respuesta JSON del servidor.
    - **Validación:** Puede incluir validación del lado del cliente para los campos del formulario (por ejemplo, longitud mínima/máxima).
- `aappro/views/js/admin-button-style.js`
  - **Alcance:** Back-office.
  - **Descripción:** Probablemente proporciona elementos interactivos o vistas previas para configurar estilos de botones (por ejemplo, selectores de color, deslizadores de tamaño) dentro de la configuración del módulo o las pantallas de gestión de formularios.
- `aappro/views/js/admin-form-layout.js`
  - **Alcance:** Back-office.
  - **Descripción:** Maneja el diseño dinámico y la interacción para crear/editar formularios en `AdminAapproFormController`, especialmente para gestionar campos personalizados. Esto podría incluir añadir/eliminar filas de campos personalizados, reordenar campos y gestionar opciones específicas del tipo de campo.
- `aappro/views/js/admin-icon-picker-data.js`
  - **Alcance:** Back-office.
  - **Descripción:** Contiene datos (por ejemplo, una matriz de clases de iconos o rutas SVG) para una interfaz de selección de iconos utilizada en el back-office, posiblemente para iconos de campos personalizados u opciones de visualización de formularios.
- `aappro/views/js/admin-icon-picker.js`
  - **Alcance:** Back-office.
  - **Descripción:** Implementa la lógica de la interfaz de usuario del selector de iconos, permitiendo a los administradores seleccionar iconos de un conjunto predefinido, probablemente utilizado en conjunción con `admin-icon-picker-data.js`.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `aappro/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back-office.
  - **Descripción:** Estilos para los desplegables de autocompletado y los campos de entrada utilizados en la configuración del formulario de administración (por ejemplo, para seleccionar productos/categorías).
- `aappro/views/aappro.css`
  - **Alcance:** Estilo del cliente de Front-office.
  - **Descripción:** Estilo principal para los formularios de consulta de productos, botones, modales, mensajes de éxito/error (notificaciones toast) y cualquier otro elemento del front-office renderizado por el módulo.
  - **Selectores de clase CSS clave:** `.aappro-form-container`, `.aappro-form-trigger`, `.aappro-modal`, `.aappro-field-group`, `.aappro-submit-button`, `.aappro-success-toast`, `.aappro-error-toast`.
- `aappro/views/css/admin-button-style.css`
  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Descripción:** Estilos para los elementos de configuración de botones dentro de la interfaz de administración del módulo.
- `aappro/views/css/admin-custom-fields.css`
  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Descripción:** Estilos para la interfaz de gestión dinámica de campos personalizados en `AdminAapproFormController`, asegurando un diseño claro y utilizable para añadir/editar campos personalizados.
- `aappro/views/css/admin-form-layout.css`
  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Descripción:** Diseño y estilo general para las pantallas de creación/edición de formularios en el panel de administración, proporcionando una apariencia consistente.
- `aappro/views/css/admin-icon-picker.css`
  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Descripción:** Estilos para la interfaz del selector de iconos utilizada en el panel de administración.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

- `aappro/views/aappro-extra-forms.tpl`
  - **Hook:** `displayProductExtraContent` o similar.
  - **Salida:** Renderiza formularios adicionales o bloques de contenido relacionados con el producto, potencialmente incluyendo el propio formulario de consulta o un disparador para el mismo.
- `aappro/views/aappro-extra-trigger.tpl`
  - **Hook:** `displayProductButtons`, `displayProductAdditionalInfo`.
  - **Salida:** Renderiza un botón o enlace (por ejemplo, "Hacer una pregunta") que activa la visualización del formulario de consulta, a menudo en un modal o una sección oculta.
- `aappro/views/aappro-extra.tpl`
  - **Hook:** `displayProductExtraContent`, `displayProductAdditionalInfo`.
  - **Salida:** Una plantilla general para contenido extra en la página del producto, que potencialmente envuelve el formulario o su disparador.
- `aappro/views/aappro-faq-tab-title.tpl`
  - **Hook:** `displayProductTab`.
  - **Salida:** Renderiza el título de una pestaña de producto (por ejemplo, "Hacer una pregunta" o "Preguntas frecuentes") que, al hacer clic, revela el contenido del formulario.
- `aappro/views/aappro-faq-tab.tpl`
  - **Hook:** `displayProductTabContent`.
  - **Salida:** Renderiza el contenido real de la pestaña del producto, que sería el propio formulario de consulta.
- `aappro/views/aappro-form-body.tpl`
  - **Hook:** Inclusión interna.
  - **Salida:** La estructura HTML principal para los campos del formulario de consulta (nombre, correo electrónico, pregunta, campos personalizados, reCAPTCHA, casilla de verificación RGPD). Es probable que sea incluido por otras plantillas.
- `aappro/views/aappro-form-tab.tpl`
  - **Hook:** `displayProductTabContent`.
  - **Salida:** Similar a `aappro-faq-tab.tpl`, específicamente para renderizar el formulario dentro de una pestaña de producto.
- `aappro/views/aappro-product-embed.tpl`
  - **Hook:** `displayProductAdditionalInfo`, `displayReassurance`.
  - **Salida:** Incrusta el formulario de consulta directamente en el contenido de la página del producto, en lugar de en una pestaña o modal.
- `aappro/views/classic/` (y `views/partials/`)
  - Estos directorios contienen plantillas específicas del tema (para el tema Classic) y parciales reutilizables. Reflejan la estructura del directorio principal `views/` pero están optimizados o estilizados específicamente para el tema Classic.
  - `aappro-custom-field-single.tpl`: Renderiza un único campo personalizado según su tipo.
  - `aappro-custom-fields.tpl`: Itera y renderiza todos los campos personalizados para un formulario.
  - `aappro-field-fragment.tpl`: Un fragmento reutilizable para renderizar elementos comunes de campos de formulario.

#### Plantillas de administración (`views/templates/admin/`)

- `aappro/views/templates/admin/button_style_block.tpl`
  - **Propósito:** Renderiza la interfaz para configurar los estilos de los botones dentro del panel de administración.
- `aappro/views/templates/admin/conversation_reply.tpl`
  - **Propósito:** Renderiza la interfaz de respuesta al ver una pregunta de un cliente en `AdminAapproQuestionController`.
- `aappro/views/templates/admin/custom_fields_block.tpl`
  - **Propósito:** Renderiza la interfaz dinámica para añadir, editar y gestionar campos personalizados dentro de `AdminAapproFormController`.
- `aappro/views/templates/admin/form_layout_block.tpl`
  - **Propósito:** Renderiza opciones de diseño general para formularios en el panel de administración.
- `aappro/views/templates/admin/question_extras.tpl`
  - **Propósito:** Muestra detalles o acciones adicionales relacionadas con una pregunta específica en `AdminAapproQuestionController`.
- `aappro/views/templates/admin/question_product_preview.tpl`
  - **Propósito:** Renderiza una pequeña vista previa del producto asociado a una pregunta en `AdminAapproQuestionController`.
- `aappro/views/templates/admin/topic_options_block.tpl`
  - **Propósito:** Renderiza la interfaz de configuración para definir los temas disponibles para el desplegable "Selección de tema".
- `aappro/views/templates/admin/view_question.tpl`
  - **Propósito:** La plantilla principal para mostrar una única pregunta de cliente y sus detalles en `AdminAapproQuestionController`.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

- `ps_aappro_form`: Almacena las definiciones de cada formulario de consulta personalizado creado por el comerciante.

  - `id_aappro_form` (PK)
  - `name` (VARCHAR)
  - `active` (TINYINT)
  - `recipient_emails` (TEXT)
  - `products` (TEXT, array de IDs de producto codificado en JSON)
  - `categories` (TEXT, array de IDs de categoría codificado en JSON)
  - `manufacturers` (TEXT, array de IDs de fabricante codificado en JSON)
  - `display_product` (TINYINT)
  - `display_category` (TINYINT)
  - `display_manufacturer` (TINYINT)
- `ps_aappro_custom_field`: Almacena las definiciones de campos personalizados asociados a cada formulario.

  - `id_aappro_custom_field` (PK)
  - `id_aappro_form` (FK a `ps_aappro_form`)
  - `name` (VARCHAR)
  - `type` (VARCHAR, por ejemplo, 'text', 'textarea', 'select', 'checkbox')
  - `label` (TEXT, multi-idioma)
  - `required` (TINYINT)
  - `options` (TEXT, codificado en JSON para opciones de selección/radio)
  - `position` (INT)
  - `active` (TINYINT)
- `ps_aappro_question`: Almacena cada pregunta de cliente enviada.

  - `id_aappro_question` (PK)
  - `id_product` (FK a `ps_product`)
  - `id_customer` (FK a `ps_customer`, si ha iniciado sesión)
  - `id_aappro_form` (FK a `ps_aappro_form`)
  - `customer_name` (VARCHAR)
  - `customer_email` (VARCHAR)
  - `customer_phone` (VARCHAR, si está habilitado)
  - `topic` (VARCHAR, si está habilitado)
  - `quantity_request` (INT, si está habilitado)
  - `question_text` (TEXT)
  - `attachment_path` (VARCHAR, si está habilitado)
  - `custom_fields_data` (TEXT, array de valores de campos personalizados codificado en JSON)
  - `ip_address` (VARCHAR)
  - `date_add` (DATETIME)
  - `status` (VARCHAR, por ejemplo, 'new', 'replied', 'closed')
- `ps_aappro_question_reply`: Almacena las respuestas del administrador a las preguntas de los clientes.

  - `id_aappro_question_reply` (PK)
  - `id_aappro_question` (FK a `ps_aappro_question`)
  - `id_employee` (FK a `ps_employee`)
  - `reply_text` (TEXT)
  - `date_add` (DATETIME)
- **Registros de configuración (en la tabla `ps_configuration`):**

  - `aappro_TITLE`
  - `aappro_AUTORESPONDER`
  - `aappro_FIELD_PHONE_REQUIRED`
  - `aappro_FIELD_PHONE_VISIBLE`
  - `aappro_FIELD_TOPIC_VISIBLE`
  - `aappro_QUOTE_QUANTITY_VISIBLE`
  - `aappro_WEBHOOK_URL`
  - `aappro_Q_LEN_MIN`
  - `aappro_Q_LEN_MAX`
  - `aappro_ATTACHMENT_ENABLE`
  - `aappro_ATTACHMENT_MAX_MB`
  - `aappro_SHOP_MAIL_BCC`
  - `aappro_TOAST_MS`
  - `aappro_FLOAT_DELAY_MS`
  - `aappro_THEME_SUPPORT`
  - `aappro_CUSTOM_CSS`
  - `aappro_CUSTOM_FIELDS_JSON` (probablemente obsoleto en favor de la tabla `ps_aappro_custom_field`)
  - `aappro_recaptcha`
  - `aappro_GDPR`
  - `aappro_GDPRCMS`
  - `aappro_recaptcha_sitekey`
  - `aappro_ALLOW_COMMENTS`
  - `aappro_recaptcha_secretkey`
  - `aappro_emailslist`
  - `aappro_HIDE_OOS`
  - `aappro_LOGGED_CUSTOMERS_ONLY`

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Registra activos CSS/JS, inicializa variables JS globales o renderiza elementos ocultos para la funcionalidad del módulo. |
| `displayFooter` | Al final de cada página, antes de `</body>`. | Puede usarse para inyectar HTML modal, botones flotantes o scripts que necesitan ejecutarse después de la carga de la página. |
| `displayProductExtraContent` | En el bloque de "contenido extra" en las páginas de producto (a menudo debajo de la descripción). | Renderiza el formulario de consulta o un disparador para el mismo, a menudo como un bloque completo. |
| `displayProductAdditionalInfo` | En el bloque de información del producto, típicamente cerca del precio/añadir al carrito. | Renderiza un disparador más pequeño o un formulario compacto directamente dentro de la información principal del producto. |
| `displayProductButtons` | Cerca del botón "Añadir al carrito". | Renderiza un botón o enlace para abrir el formulario de consulta. |
| `displayProductTab` | Para añadir un nuevo título de pestaña en la página del producto. | Renderiza el título de la pestaña "Hacer una pregunta" o "Preguntas frecuentes". |
| `displayProductTabContent` | Para añadir contenido a una nueva pestaña en la página del producto. | Renderiza el formulario de consulta real dentro de su pestaña de producto dedicada. |
| `displayReassurance` | En el bloque de reafirmación (por ejemplo, "pago seguro", "envío gratuito"). | Puede usarse para inyectar un pequeño enlace o icono de "Hacer una pregunta" dentro del bloque de reafirmación. |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración y se están configurando sus activos multimedia. | Registra CSS y JS específicos del módulo para los controladores del back-office (`AdminAapproForm`, `AdminAapproQuestion`). |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | (No utilizado directamente por la función principal de este módulo, pero podría usarse para preguntas de seguimiento después de la compra si se extiende). |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Preguntar sobre el producto - formularios de contacto pro", consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo de soporte está disponible para ayudar con cualquier problema técnico o pregunta relacionada con la funcionalidad del módulo. Asegúrese siempre de estar ejecutando la última versión compatible del módulo para un rendimiento y seguridad óptimos.

---
title: "Vale por comentario de producto - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Vale por comentario de producto' de MyPresta.eu."
sidebar:
  label: "Vale por comentario de producto - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Voucher for product comment en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-for-product-comment.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/voucher-for-product-comment/)
>
> ---


# Vale por comentario de producto

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para que PrestaShop funcione correctamente. No se necesitan extensiones adicionales específicas para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es el área de configuración principal para el módulo "Vale por comentario de producto". Aquí encontrará todos los ajustes relacionados con los recordatorios de comentarios y la generación de vales.

#### **Configuración de recordatorios de comentarios**

-   **Pedir permisos para enviar recordatorios**

    *   **Qué hace este ajuste:** Si está habilitado, aparecerá una casilla de verificación en sus formularios de registro de cliente y actualización de identidad (Mi cuenta > Información) preguntando a los clientes si aceptan recibir recordatorios de comentarios. Esto es importante para el cumplimiento del GDPR y el respeto de la privacidad del cliente.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* Los clientes deben optar explícitamente por recibir recordatorios. Solo los clientes que marquen esta casilla recibirán correos electrónicos de recordatorio.
        *   *Cuando está deshabilitado:* Todos los clientes que cumplan otros criterios (por ejemplo, productos comprados, no han comentado) recibirán recordatorios, sin una opción explícita.
    *   **Valor recomendado:** SÍ (Muy recomendado para el cumplimiento del GDPR y mejores relaciones con los clientes).
    *   **Escenario / ejemplo de comerciante:** Desea asegurarse de que sus prácticas de marketing cumplan con las regulaciones de protección de datos. Habilitar esto da a los clientes control sobre sus preferencias de comunicación.
-   **Enviar recordatorio de comentario**

    *   **Qué hace este ajuste:** Este es el interruptor maestro para la función de recordatorio de comentarios. Si está deshabilitado, no se enviarán correos electrónicos de recordatorio de comentarios, independientemente de otros ajustes.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* El módulo enviará activamente correos electrónicos de recordatorio según sus otros ajustes.
        *   *Cuando está deshabilitado:* No se enviarán correos electrónicos de recordatorio.
    *   **Valor recomendado:** SÍ
    *   **Escenario / ejemplo de comerciante:** Ha decidido recopilar activamente más reseñas y desea comenzar a enviar recordatorios.
-   **Recordar comentarios después de:**

    *   **Qué hace este ajuste:** Define el número de días después de que un pedido alcanza un estado específico (definido a continuación) en que se enviará el primer correo electrónico de recordatorio de comentario.
    *   **Efecto de cambiar este ajuste:**
        *   *Cambiar el número:* Determina el retraso. Un retraso más corto significa que los clientes reciben recordatorios antes; un retraso más largo les da más tiempo antes de ser solicitados.
    *   **Valor recomendado:** 7 días (Da a los clientes tiempo suficiente para recibir y usar el producto).
    *   **Escenario / ejemplo de comerciante:** Desea dar a los clientes una semana para recibir su producto y formarse una opinión antes de pedir una reseña.
-   **Repetir recordatorio**

    *   **Qué hace este ajuste:** Si un cliente aún no ha dejado un comentario después del recordatorio inicial, este ajuste determina si se debe enviar un segundo recordatorio y cuándo.
    *   **Efecto de cambiar este ajuste:**
        *   *Establecer un número (por ejemplo, 14):* Se enviará un segundo recordatorio 14 días después del *primer* recordatorio, si no se ha dejado ningún comentario.
        *   *Establecer en 0 o dejar vacío:* No se enviará un segundo recordatorio.
    *   **Valor recomendado:** 14 (Proporciona un seguimiento suave sin ser demasiado agresivo).
    *   **Escenario / ejemplo de comerciante:** Algunos clientes pueden perder el primer correo electrónico o simplemente olvidarlo. Un segundo recordatorio después de dos semanas puede volver a llamar su atención.
-   **Título del correo electrónico**

    *   **Qué hace este ajuste:** Le permite personalizar la línea de asunto de los correos electrónicos de recordatorio de comentarios. Esto es crucial para las tasas de apertura de correo electrónico.
    *   **Efecto de cambiar este ajuste:**
        *   *Cambiar el texto:* Cambia directamente la línea de asunto que los clientes ven en su bandeja de entrada.
    *   **Valor recomendado:** "¡Nos encantaría saber su opinión sobre su compra reciente!" o "¡Comparta su experiencia y ayude a otros compradores!"
    *   **Escenario / ejemplo de comerciante:** Desea que la línea de asunto del correo electrónico sea atractiva y clara, animando a los clientes a abrirlo.
-   **Seleccionar estados de pedido**

    *   **Qué hace este ajuste:** Determina qué estados de pedido activan el proceso de recordatorio de comentarios. Los recordatorios solo se enviarán para productos de pedidos que hayan alcanzado uno de los estados seleccionados.
    *   **Efecto de cambiar este ajuste:**
        *   *Seleccionar estados (por ejemplo, "Entregado"):* Los recordatorios solo se enviarán para pedidos marcados como entregados.
        *   *No seleccionar un estado relevante:* Es posible que los recordatorios no se envíen en el momento adecuado (por ejemplo, si solo selecciona "Pago aceptado" pero los productos aún no se han enviado).
    *   **Valor recomendado:** "Entregado" (Esto asegura que los clientes hayan recibido sus productos antes de que se les pida que los revisen).
    *   **Escenario / ejemplo de comerciante:** Solo desea pedir reseñas una vez que el cliente haya recibido su pedido, por lo que selecciona "Entregado" y "Enviado".
-   **Grupo de clientes (para recordatorios)**

    *   **Qué hace este ajuste:** Le permite dirigirse a grupos de clientes específicos para los recordatorios de comentarios. Solo los clientes que pertenezcan a los grupos seleccionados recibirán recordatorios.
    *   **Efecto de cambiar este ajuste:**
        *   *Seleccionar grupos (por ejemplo, "Clientes"):* Solo los clientes del grupo "Clientes" recibirán recordatorios.
        *   *No seleccionar ningún grupo:* Los recordatorios se enviarán a todos los clientes (a menos que se apliquen otros filtros).
    *   **Valor recomendado:** "Clientes" (Normalmente, desea recordar a todos sus clientes habituales).
    *   **Escenario / ejemplo de comerciante:** Tiene un grupo de clientes "VIP" especial y desea enviarles recordatorios personalizados, o desea excluir a los clientes mayoristas de los recordatorios.
-   **Enviar recordatorios sobre comentarios de productos de pedidos:**

    *   **Qué hace este ajuste:** Este es un filtro de fecha. Los recordatorios solo se enviarán para productos comprados en pedidos realizados *después* de esta fecha especificada.
    *   **Efecto de cambiar este ajuste:**
        *   *Establecer una fecha:* Evita enviar recordatorios para pedidos muy antiguos, centrándose en compras recientes.
        *   *Dejar vacío:* Los recordatorios podrían enviarse potencialmente para todos los pedidos anteriores, lo que podría no ser deseable.
    *   **Valor recomendado:** Establezca una fecha reciente, o la fecha en que instaló el módulo, para evitar enviar spam a clientes antiguos.
    *   **Escenario / ejemplo de comerciante:** Acaba de instalar el módulo y no desea enviar recordatorios para pedidos de hace un año; solo le interesan los pedidos de los últimos 3 meses.
-   **Tamaño de imagen para las fotos de productos**

    *   **Qué hace este ajuste:** Determina el tamaño de las imágenes de los productos incluidas en los correos electrónicos de recordatorio.
    *   **Efecto de cambiar este ajuste:**
        *   *Seleccionar un tamaño (por ejemplo, "home\_default"):* Las imágenes de los productos en el correo electrónico se renderizarán a ese tamaño específico, afectando el diseño del correo electrónico y el tiempo de carga.
    *   **Valor recomendado:** "home\_default" o "small\_default" (Una imagen de tamaño mediano que se vea bien sin hacer que el correo electrónico sea demasiado pesado).
    *   **Escenario / ejemplo de comerciante:** Desea que las imágenes de los productos en sus correos electrónicos de recordatorio sean claras pero no excesivamente grandes, por lo que elige un tamaño de imagen adecuado definido en su tema.

#### **Configuración de generación de vales**

-   **Enviar código de vale por comentario**

    *   **Qué hace este ajuste:** Este es el interruptor maestro para la función de generación de vales. Si está deshabilitado, no se generarán ni enviarán vales, incluso si se dejan comentarios.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* El módulo generará y enviará un código de vale único a los clientes que dejen un comentario de producto.
        *   *Cuando está deshabilitado:* No se enviarán vales.
    *   **Valor recomendado:** SÍ (Esta es una característica central para incentivar los comentarios).
    *   **Escenario / ejemplo de comerciante:** Desea recompensar a los clientes por su esfuerzo al dejar una reseña, animándolos a comprar de nuevo.
-   **Enviar vale solo a clientes que compraron el producto**

    *   **Qué hace este ajuste:** Si está habilitado, un vale *solo* se enviará si el cliente que dejó el comentario también compró el producto. Esto evita que las personas que no han comprado en su tienda obtengan vales simplemente dejando comentarios.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* Los vales se restringen a compradores verificados.
        *   *Cuando está deshabilitado:* Cualquiera que deje un comentario (por ejemplo, un invitado o alguien que no compró el producto) podría recibir un vale.
    *   **Valor recomendado:** SÍ (Muy recomendado para garantizar que los vales se entreguen a clientes reales y evitar abusos).
    *   **Escenario / ejemplo de comerciante:** Desea recompensar a los clientes leales que ya han realizado una compra, no solo a cualquiera que deje un comentario.
-   **¿Cuándo generar el vale?**

    *   **Qué hace este ajuste:** Determina cuándo se genera y se envía el vale al cliente.
    *   **Efecto de cambiar este ajuste:**
        *   *Opción 1 (por ejemplo, "Después de añadir el comentario"):* El vale se envía inmediatamente después de que el cliente envía su comentario.
        *   *Opción 2 (por ejemplo, "Después de aprobar el comentario"):* El vale se envía solo después de que un administrador haya aprobado manualmente el comentario en el Back Office.
    *   **Valor recomendado:** "Después de aprobar el comentario" (Evita dar vales por spam o comentarios inapropiados).
    *   **Escenario / ejemplo de comerciante:** Modera todos los comentarios de productos para mantener la calidad. Desea asegurarse de que solo los comentarios aprobados y valiosos reciban un vale.
-   **Generar vales para comentarios:**

    *   **Qué hace este ajuste:** Esta sección le permite definir las propiedades del vale que se generará. Esto incluye el tipo de descuento (porcentaje, cantidad), valor, compra mínima, validez y más.
    *   **Efecto de cambiar este ajuste:**
        *   *Cada campo aquí (por ejemplo, "Tipo de descuento", "Valor", "Cantidad mínima"):* Configura directamente las reglas y beneficios del vale de descuento generado.
        *   *Dejar campos vacíos o configurados incorrectamente:* Podría dar lugar a vales no válidos o vales que no cumplan sus objetivos de marketing.
    *   **Valor recomendado:**
        *   **Tipo de descuento:** Porcentaje (por ejemplo, 10%) o Cantidad (por ejemplo, 5 €).
        *   **Valor:** Un incentivo razonable (por ejemplo, 5, 10, 15).
        *   **Cantidad mínima:** Establezca una compra mínima para garantizar la rentabilidad (por ejemplo, 50 €).
        *   **Validez:** 30 días (Fomenta el uso rápido).
        *   **Descripción:** "¡Gracias por su reseña de producto!"
    *   **Escenario / ejemplo de comerciante:** Desea ofrecer un 10% de descuento en su próximo pedido, válido por 30 días, con una compra mínima de 50 €, como agradecimiento por su reseña.
-   **Grupo de clientes (para vales)**

    *   **Qué hace este ajuste:** Similar al ajuste de recordatorio, esto le permite restringir la generación de vales a grupos de clientes específicos.
    *   **Efecto de cambiar este ajuste:**
        *   *Seleccionar grupos:* Solo los clientes de los grupos seleccionados recibirán vales.
        *   *No seleccionar ningún grupo:* Los vales se enviarán a todos los clientes (a menos que se apliquen otros filtros).
    *   **Valor recomendado:** "Clientes"
    *   **Escenario / ejemplo de comerciante:** Solo desea dar vales a su grupo de "Clientes" estándar, no a "Invitados" o "Mayoristas".
-   **Limitar el número de correos electrónicos**

    *   **Qué hace este ajuste:** Esta es una característica de seguridad para evitar que su servidor envíe demasiados correos electrónicos en un corto período, lo que podría llevar a que sus correos electrónicos se marquen como spam o a que su proveedor de alojamiento imponga límites.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* El módulo respetará el ajuste "Límite de correos electrónicos".
        *   *Cuando está deshabilitado:* El módulo no aplicará ningún límite de envío de correos electrónicos.
    *   **Valor recomendado:** SÍ
    *   **Escenario / ejemplo de comerciante:** Tiene un gran número de recordatorios pendientes y desea enviarlos gradualmente para evitar sobrecargar su servidor de correo.
-   **Límite de correos electrónicos:**

    *   **Qué hace este ajuste:** Especifica el número máximo de correos electrónicos (recordatorios o vales) que el módulo puede enviar en un solo ciclo de ejecución (por ejemplo, cuando se ejecuta el cron job).
    *   **Efecto de cambiar este ajuste:**
        *   *Establecer un número (por ejemplo, 50):* El módulo enviará un máximo de 50 correos electrónicos por ejecución del cron job. Si hay más, se enviarán en ejecuciones posteriores.
    *   **Valor recomendado:** 50-100 (Ajuste según los límites de envío de correo electrónico de su proveedor de alojamiento y la capacidad del servidor).
    *   **Escenario / ejemplo de comerciante:** Su proveedor de alojamiento permite 100 correos electrónicos por hora. Establece este límite en 50 para mantenerse dentro de sus directrices.

#### **Filtros de producto (para recordatorios y vales)**

-   **Habilitar filtros**

    *   **Qué hace este ajuste:** Activa opciones de filtrado adicionales tanto para recordatorios como para vales, lo que le permite especificar qué productos o fabricantes son elegibles.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* El filtro "Fabricantes" se activa.
        *   *Cuando está deshabilitado:* No se aplicarán filtros específicos de productos.
    *   **Valor recomendado:** NO (A menos que tenga una necesidad específica de filtrar).
    *   **Escenario / ejemplo de comerciante:** Solo desea enviar recordatorios o vales para productos de ciertos fabricantes.
-   **Fabricantes**

    *   **Qué hace este ajuste:** Si "Habilitar filtros" está activo, esto le permite seleccionar fabricantes específicos. Los recordatorios y vales solo se enviarán para productos de los fabricantes seleccionados.
    *   **Efecto de cambiar este ajuste:**
        *   *Seleccionar fabricantes:* Reduce el alcance de la operación del módulo a solo productos de esas marcas.
    *   **Valor recomendado:** Dejar todos sin seleccionar (a menos que tenga una necesidad específica).
    *   **Escenario / ejemplo de comerciante:** Está ejecutando una promoción con una marca específica y solo desea incentivar comentarios para sus productos.

#### **Tabla de referencia rápida de configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Pedir permisos para enviar recordatorios | SÍ | Garantiza el cumplimiento del GDPR; los clientes optan por recibir recordatorios. |
| Configuración del módulo | Enviar recordatorio de comentario | SÍ | Interruptor maestro para enviar correos electrónicos de recordatorio. |
| Configuración del módulo | Recordar comentarios después de: | 7 días | Retraso (en días) después del cambio de estado del pedido para el primer recordatorio. |
| Configuración del módulo | Repetir recordatorio | 14 días | Retraso (en días) después del primer recordatorio para un segundo (0 para ninguno). |
| Configuración del módulo | Título del correo electrónico (Recordatorio) | Personalizable | Línea de asunto para los correos electrónicos de recordatorio. |
| Configuración del módulo | Seleccionar estados de pedido | Entregado | Estados de pedido que activan el proceso de recordatorio. |
| Configuración del módulo | Grupo de clientes (Recordatorio) | Clientes | Restringe los recordatorios a los grupos de clientes seleccionados. |
| Configuración del módulo | Enviar recordatorios sobre comentarios de productos de pedidos: | Fecha reciente / Vacío | Filtro de fecha para pedidos elegibles. |
| Configuración del módulo | Tamaño de imagen para las fotos de productos | home\_default | Tamaño de las imágenes de los productos en los correos electrónicos de recordatorio. |
| Configuración del módulo | Enviar código de vale por comentario | SÍ | Interruptor maestro para generar y enviar vales. |
| Configuración del módulo | Enviar vale solo a clientes que compraron el producto | SÍ | Restringe los vales a los compradores reales. |
| Configuración del módulo | ¿Cuándo generar el vale? | Después de aprobar el comentario | Momento de la generación del vale (después del envío o la aprobación). |
| Configuración del módulo | Generar vales para comentarios: (Propiedades del vale) | Personalizable | Define el tipo de descuento, valor, validez, etc., del vale. |
| Configuración del módulo | Grupo de clientes (Vale) | Clientes | Restringe los vales a los grupos de clientes seleccionados. |
| Configuración del módulo | Limitar el número de correos electrónicos | SÍ | Habilita la limitación de la tasa de envío de correos electrónicos. |
| Configuración del módulo | Límite de correos electrónicos: | 50-100 | Máximo de correos electrónicos enviados por ejecución del cron job. |
| Configuración del módulo | Habilitar filtros | NO | Activa el filtrado de productos/fabricantes. |
| Configuración del módulo | Fabricantes | Todos sin seleccionar | Filtra los productos elegibles por fabricante. |

### 2.2 Pantallas de administración dedicadas y vistas de controlador

El módulo añade varias pantallas dedicadas a su Back Office de PrestaShop para gestionar recordatorios, vales y clientes dados de baja. Puede encontrarlas en el elemento de menú **"Vale por comentario"**, que suele estar ubicado en **"Catálogo"** o **"Marketing"**.

#### **4.2.1 AdminComRemCommentsController: Gestión de recordatorios de comentarios**

-   **Nombre de la pantalla y ubicación del menú:** **Vale por comentario > Recordatorios de comentarios**
-   **Acciones y ajustes disponibles:** Esta pantalla muestra una lista de todos los recordatorios de comentarios pendientes, enviados o fallidos. Verá detalles como el nombre del cliente, el correo electrónico, el producto sobre el que debe comentar, el ID del pedido, la fecha en que se envió (o está programado) el recordatorio y su estado actual.
    *   **Vista de cuadrícula / Gestión:** Puede ver, filtrar y buscar en la lista de recordatorios. Esto le permite supervisar la actividad del módulo.
    *   **Acciones masivas:** Dependiendo de la versión del módulo, es posible que pueda enviar recordatorios manualmente o eliminar entradas.
-   **Efecto de los cambios:** Esta pantalla es principalmente para monitoreo. Eliminar una entrada aquí evitaría que se enviara un recordatorio programado. Enviar un recordatorio manualmente activaría un correo electrónico al cliente.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise periódicamente esta pantalla para asegurarse de que los recordatorios se envían según lo esperado. Si observa que un cliente no ha recibido un recordatorio, puede investigar o activarlo manualmente.

#### **4.2.2 AdminComUnsubController: Clientes dados de baja**

-   **Nombre de la pantalla y ubicación del menú:** **Vale por comentario > Clientes dados de baja**
-   **Acciones y ajustes disponibles:** Esta pantalla enumera a los clientes que han optado por no recibir recordatorios de comentarios (si el ajuste "Pedir permisos" está habilitado). Verá su ID de cliente y dirección de correo electrónico.
    *   **Vista de cuadrícula / Gestión:** Le permite ver y gestionar la lista de clientes dados de baja.
-   **Efecto de los cambios:** Eliminar un cliente de esta lista lo haría elegible para recibir recordatorios nuevamente (suponiendo que cumpla otros criterios y no haya optado explícitamente por no participar en otro lugar).
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Esta es una pantalla relacionada con el cumplimiento. Generalmente no necesitará interactuar con ella a diario, pero es importante saber dónde encontrar y gestionar las preferencias de exclusión voluntaria del cliente.

#### **4.2.3 AdminComVouCommentsController: Gestión de vales por comentarios**

-   **Nombre de la pantalla y ubicación del menú:** **Vale por comentario > Vales por comentarios**
-   **Acciones y ajustes disponibles:** Esta pantalla proporciona una lista completa de todos los vales generados por el módulo en respuesta a los comentarios de productos. Verá detalles como el cliente que recibió el vale, el producto sobre el que comentó, el código de vale generado, su valor, validez y si se ha utilizado.
    *   **Vista de cuadrícula / Gestión:** Puede filtrar, buscar y ordenar vales. Esto es útil para rastrear la efectividad de su programa de incentivos.
    *   **Claves de configuración asociadas:** Las opciones de visualización y filtrado aquí pueden estar influenciadas por `cvo_filters` y `cvo_fil_manuf` de la configuración principal.
-   **Efecto de los cambios:** Esta pantalla es principalmente para monitoreo. Puede ver qué vales se han emitido y si se han canjeado.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise esta pantalla para rastrear cuántos vales se están emitiendo y sus tasas de canje. Estos datos pueden ayudarle a evaluar el éxito de su programa de incentivos de reseñas.

#### **4.2.4 index.php (Marcador de posición del controlador de administración)**

-   **Nombre de la pantalla y ubicación del menú:** Este archivo `index.php` suele servir como marcador de posición o redirección dentro del directorio `controllers/admin` del módulo, asegurando que el acceso directo al directorio no exponga información sensible. No representa una pantalla orientada al usuario en el Back Office de PrestaShop.

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis clientes no reciben correos electrónicos de recordatorio. ¿Qué debo verificar?**
R1:

-   **Módulo habilitado:** Asegúrese de que "Enviar recordatorio de comentario" esté configurado en SÍ en la configuración del módulo.
-   **Estados de pedido:** Verifique que los pedidos en cuestión hayan alcanzado uno de los "Seleccionar estados de pedido" que ha elegido (por ejemplo, "Entregado").
-   **Retraso del recordatorio:** Verifique "Recordar comentarios después de:" para asegurarse de que hayan pasado suficientes días desde el cambio de estado del pedido.
-   **Cron Job:** El módulo se basa en el cron job de PrestaShop para enviar correos electrónicos. Asegúrese de que su cron job esté configurado correctamente y se ejecute regularmente en su servidor. Por lo general, puede encontrar instrucciones de cron job en su panel de alojamiento o en la sección "Parámetros avanzados > Información" de PrestaShop.
-   **Configuración de correo electrónico:** Verifique la configuración de correo electrónico de su PrestaShop (Parámetros avanzados > Correo electrónico) para asegurarse de que los correos electrónicos se envían correctamente desde su tienda en general.
-   **Opción de cliente:** Si "Pedir permisos para enviar recordatorios" está habilitado, asegúrese de que los clientes realmente hayan optado por participar.
-   **Límites de correo electrónico:** Verifique los ajustes "Limitar el número de correos electrónicos" y "Límite de correos electrónicos". Si se alcanza el límite, los correos electrónicos se enviarán en la siguiente ejecución del cron.
-   **Carpetas de spam:** Pida a los clientes que revisen sus carpetas de spam o correo no deseado.

**P2: No se envían vales después de dejar comentarios.**
R2:

-   **Módulo habilitado:** Asegúrese de que "Enviar código de vale por comentario" esté configurado en SÍ.
-   **Momento de generación del vale:** Verifique "¿Cuándo generar el vale?". Si está configurado en "Después de aprobar el comentario", asegúrese de que los comentarios realmente hayan sido aprobados en su Back Office de PrestaShop (Catálogo > Comentarios de productos, si usa el módulo predeterminado, o su módulo de reseñas de terceros).
-   **Solo comprador:** Si "Enviar vale solo a clientes que compraron el producto" está habilitado, verifique que el cliente que dejó el comentario realmente compró ese producto específico.
-   **Configuración del vale:** Vuelva a verificar todos los ajustes en "Generar vales para comentarios" para asegurarse de que se pueda crear un vale válido (por ejemplo, valor de descuento, validez).
-   **Configuración de correo electrónico y Cron Job:** Similar a los problemas de recordatorio, asegúrese de que su configuración de correo electrónico y cron job estén funcionando.

**P3: El módulo envía demasiados correos electrónicos o los correos electrónicos se retrasan.**
R3:

-   **Límite de correos electrónicos:** Vaya a la configuración del módulo y asegúrese de que "Limitar el número de correos electrónicos" esté habilitado y que "Límite de correos electrónicos" esté configurado en un número razonable (por ejemplo, 50-100). Esto evita que su servidor se sobrecargue.
-   **Frecuencia del Cron Job:** Si su cron job se ejecuta con mucha frecuencia (por ejemplo, cada minuto) y tiene un límite de correo electrónico alto, podría enviar muchos correos electrónicos rápidamente. Ajuste la frecuencia del cron job o el límite de correo electrónico.
-   **Límites de alojamiento:** Póngase en contacto con su proveedor de alojamiento para comprender sus límites de envío de correo electrónico por hora/día. Ajuste el "Límite de correos electrónicos" del módulo en consecuencia.

**P4: ¿Cómo traduzco los textos del módulo o las plantillas de correo electrónico?**
R4:

-   **Traducción del Back Office:** Vaya a **Internacional > Traducciones**.
-   **Tipo de traducción:** Seleccione "Traducciones de módulos instalados".
-   **Seleccione su tema:** Elija su tema actual.
-   **Seleccione su idioma:** Elija el idioma que desea traducir.
-   **Módulo:** Busque "Vale por comentario de producto" en la lista.
-   Luego puede editar las cadenas de texto para la configuración del módulo, los elementos del front-office (como la casilla de verificación de opción) y las plantillas de correo electrónico. Recuerde guardar sus cambios.

**P5: La casilla de verificación del front-office del módulo (para permisos) no se ve bien en mi tema.**
R5:

-   **Compatibilidad del tema:** Los temas personalizados a veces requieren pequeños ajustes de CSS para los nuevos elementos del módulo.
-   **Borrar caché:** Primero, intente borrar la caché de su PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché).
-   **Contactar con soporte:** Si el problema persiste, podría requerir un pequeño ajuste de CSS. Póngase en contacto con el soporte de MyPresta.eu con capturas de pantalla y el nombre de su tema.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada del módulo "Vale por comentario de producto" para desarrolladores y webmasters.

### 4.1 Resumen de la arquitectura

El módulo sigue una arquitectura de módulo estándar de PrestaShop, aprovechando los patrones MVC cuando corresponde. Se integra con el núcleo de PrestaShop a través de hooks para la visualización del front-office y las acciones del back-office. Utiliza AdminControllers personalizados para gestionar sus entidades de datos (recordatorios, vales, cancelaciones de suscripción) y un FrontController para la ejecución de cron jobs. La configuración se gestiona a través de `Configuration::get()` y `Configuration::updateValue()`. El módulo no parece utilizar clases `ObjectModel` personalizadas, sino que probablemente gestiona sus datos directamente o a través de entidades existentes de PrestaShop (como `CartRule` para vales).

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

-   `comvou/controllers/front/CronJob.php`
    *   **Nombre de la clase y clase padre:** `ComvouCronJobModuleFrontController` que extiende `ModuleFrontController`.
    *   **Responsabilidad:** Este controlador está diseñado para ser ejecutado a través de un cron job. Maneja las tareas en segundo plano del módulo, como verificar pedidos elegibles, enviar recordatorios de comentarios y generar/enviar vales basados en nuevos comentarios. Normalmente no renderiza una página visual, sino que realiza acciones y sale. Es el corazón de la automatización del módulo.

#### Controladores de administración del Back-Office

-   `comvou/controllers/admin/AdminComRemComments.php`

    *   **Nombre de la pestaña y entidad gestionada:** "Recordatorios de comentarios" (en el menú "Vale por comentario"). Gestiona las entidades `cvor` (Comment Voucher Order Reminder), que representan recordatorios programados o enviados.
    *   **Responsabilidad:** Proporciona una lista (vista de cuadrícula) de todos los recordatorios de comentarios. Permite a los administradores ver el estado de los recordatorios, filtrarlos y, potencialmente, realizar acciones como enviar manualmente un recordatorio o eliminar una entrada. Extiende `AdminController` y utiliza `HelperList` para la visualización.
-   `comvou/controllers/admin/AdminComUnsub.php`

    *   **Nombre de la pestaña y entidad gestionada:** "Clientes dados de baja" (en el menú "Vale por comentario"). Gestiona las entidades `cunsub` (Comment Unsubscribe).
    *   **Responsabilidad:** Muestra una lista de clientes que se han dado de baja de los recordatorios de comentarios. Este controlador proporciona una interfaz para ver y gestionar estas preferencias de exclusión voluntaria, normalmente utilizando `HelperList`.
-   `comvou/controllers/admin/AdminComVouComments.php`

    *   **Nombre de la pestaña y entidad gestionada:** "Vales por comentarios" (en el menú "Vale por comentario"). Gestiona las entidades `cvov` (Comment Voucher Order Voucher), que representan los vales generados.
    *   **Responsabilidad:** Presenta una lista de todos los vales generados por el módulo, detallando qué cliente lo recibió, para qué producto, el código del vale, su valor y el estado de uso. Utiliza `HelperList` para la visualización y permite el filtrado. La visualización podría incorporar lógica basada en las claves de configuración `cvo_filters` y `cvo_fil_manuf`.
-   `comvou/controllers/admin/index.php`

    *   **Nombre de la pestaña y entidad gestionada:** No es una pantalla directamente orientada al usuario.
    *   **Responsabilidad:** Esta es una medida de seguridad estándar en PrestaShop. Normalmente contiene `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../../../"); exit;` para evitar la lista de directorios y redirigir a la raíz de la tienda.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo podría estar manejando sus datos directamente dentro del archivo principal `comvou.php` o sus controladores, utilizando potencialmente `ObjectModel`s existentes de PrestaShop (como `Order`, `Customer`, `Product`, `CartRule`) y consultas directas a la base de datos para su almacenamiento de datos personalizado (por ejemplo, para recordatorios y registros de vales).

### 4.4 Activos de JavaScript (`views/js/`)

-   `comvou/lib/voucherengine/script.js`
    *   **Alcance:** Probablemente Back-office.
    *   **Detalles:** Este script probablemente está asociado con la configuración de generación de vales dentro de la configuración del módulo o el controlador AdminComVouComments. Podría manejar elementos de formulario dinámicos, validación o interacciones AJAX relacionadas con los parámetros de creación de vales (por ejemplo, mostrar/ocultar campos según el tipo de descuento, calcular valores). También podría usarse para mejoras generales de la interfaz de usuario en las páginas de administración del módulo.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `comvou/lib/voucherengine/ps16.css`
    *   **Alcance:** Estilo del formulario de administración del Back-office.
    *   **Detalles:** Esta hoja de estilo proporciona un estilo específico para la página de configuración del módulo y, potencialmente, sus vistas de controlador de administración personalizadas, asegurando que se vean consistentes con el diseño del back-office de PrestaShop 1.6. Podría contener reglas para diseños de formularios, campos de entrada, botones y visualizaciones de cuadrícula. Los desarrolladores que anulen esto se dirigirían a ID o clases específicas utilizadas por las plantillas de administración del módulo.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

-   `comvou/views/templates/hook/form.tpl`

    *   **Hook:** Potencialmente `displayAdditionalCustomerFormFields` o `displayCustomerAccountForm`.
    *   **Salida:** Esta plantilla probablemente renderiza la casilla de verificación "Pedir permisos para enviar recordatorios" en los formularios de registro de cliente o actualización de identidad en el front office. Contendría el HTML para la casilla de verificación y su etiqueta asociada.
-   `comvou/views/templates/hook/header.tpl`

    *   **Hook:** `displayHeader`
    *   **Salida:** Esta plantilla se utiliza normalmente para incluir archivos CSS o JavaScript que deben cargarse en la sección `<head>` de las páginas del front-office. Podría cargar condicionalmente activos según la configuración del módulo o la página actual.
-   `comvou/views/templates/hook/identity.tpl`

    *   **Hook:** Potencialmente `displayCustomerAccountForm` o hooks similares en la página de identidad del cliente.
    *   **Salida:** Similar a `form.tpl`, esta plantilla probablemente renderiza la casilla de verificación de opción específicamente en la página "Mi cuenta > Información" del cliente, permitiendo a los clientes existentes gestionar sus preferencias de recordatorio.

#### Plantillas de administración (`views/templates/admin/`)

-   `comvou/views/templates/admin/com_rem_comments/helpers/form/form.tpl`

    *   **Propósito:** Esta plantilla es utilizada por `AdminComRemCommentsController` para renderizar el formulario (si lo hay) para añadir/editar un recordatorio de comentario, o más probablemente, para personalizar la visualización del asistente de lista.
-   `comvou/views/templates/admin/com_vou_comments/helpers/form/form.tpl`

    *   **Propósito:** Esta plantilla es utilizada por `AdminComVouCommentsController` para renderizar el formulario (si lo hay) para añadir/editar una entrada de vale, o para personalizar la visualización del asistente de lista para los vales generados.
-   `comvou/views/templates/admin/orderstates.tpl`

    *   **Propósito:** Esta plantilla se utiliza probablemente dentro de la configuración principal del módulo (`getContent()`) para renderizar la lista de selección múltiple de estados de pedido, permitiendo al comerciante elegir qué estados activan los recordatorios.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

La descripción del módulo y el análisis del código sugieren que el módulo almacena sus datos personalizados (recordatorios, vales, cancelaciones de suscripción) en tablas de base de datos dedicadas. Aunque no se enumeran archivos SQL específicos, los `AdminComRemCommentsController`, `AdminComUnsubController` y `AdminComVouCommentsController` implican la existencia de tablas como:

-   `ps_cvor`: Almacena registros relacionados con recordatorios de comentarios (por ejemplo, ID de cliente, ID de producto, ID de pedido, estado del recordatorio, última fecha de envío).
-   `ps_cunsub`: Almacena registros de clientes que se han dado de baja de los recordatorios (por ejemplo, ID de cliente, correo electrónico).
-   `ps_cvov`: Almacena registros de vales generados (por ejemplo, ID de cliente, ID de producto, `id_cart_rule` generado, código de vale, estado).
-   Los valores de configuración se almacenan en `ps_configuration` con claves como `cvo_r_d`, `cvo_r`, `cvo_repeat`, `cvo_orderstates`, `CR_ALLOWED`, `cvo_v`, `cvo_v_fn`, `cvo_v_t`, `cvo_filters`, `cvo_fil_manuf`, `CVOR_TITLE`, `CVOV_TITLE`, `cvo_customergroups_reminder`, `cvo_customergroups_voucher`, `cvo_r_fn`, `cvo_r_date`, `cvo_vonlycust`, `cvo_v_date`, `cvo_img_type`, `CVO_LIM_M_V`, `CVO_LIM_M`.

#### Tabla de hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Cuando se inicializa un AdminController y se están configurando sus medios (JS/CSS). | Para inyectar JS/CSS específicos del módulo en el Back Office. |
| `actionOrderStatusUpdate` | Después de que se ha actualizado el estado de un pedido. | Para detectar cuándo un pedido alcanza un estado "entregado" o relevante, lo que activa el proceso de recordatorio. |
| `actionCustomerAccountAdd` | Después de que se crea una nueva cuenta de cliente. | Para verificar las preferencias de suscripción iniciales para nuevos clientes. |
| `displayHeader` | En la sección `<head>` de las páginas del front-office. | Para incluir CSS/JS del front-office o metaetiquetas. |
| `displayCustomerAccountForm` | En la página "Mi cuenta > Información" del cliente. | Para mostrar la casilla de verificación de suscripción para clientes existentes. |
| `displayAdditionalCustomerFormFields` | En el formulario de registro de cliente. | Para mostrar la casilla de verificación de suscripción para nuevos registros de clientes. |
| `validateCustomerFormFields` | Cuando se envía un formulario de cliente (registro/identidad). | Para procesar la selección de la casilla de verificación de suscripción y guardar la preferencia del cliente. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte técnico profesional, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Asegúrese de estar ejecutando la última versión compatible del módulo para su tienda PrestaShop para beneficiarse de todas las mejoras y parches de seguridad.

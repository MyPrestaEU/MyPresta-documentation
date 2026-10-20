---
title: "Recompensas - Códigos de cupón después de los pedidos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Recompensas - Códigos de cupón después de los pedidos' de MyPresta.eu."
sidebar:
  label: "Recompensas - Códigos de cupón después de los pedidos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Rewards - Voucher codes after orders en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/rewards-voucher-codes-after-orders.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/rewards-voucher-codes-after-orders/)
>
> ---


# Recompensas - Códigos de cupón después de los pedidos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para que una tienda PrestaShop funcione correctamente. Este módulo no tiene requisitos de alojamiento inusuales o adicionales más allá de una configuración estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Recompensas - Códigos de cupón después de los pedidos)

Esta es la pantalla de configuración principal donde se definen las reglas para generar y enviar códigos de cupón.

#### Ajustes generales

- **Activar módulo:**

  - **Qué hace este ajuste:** Este es el interruptor principal del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El módulo supervisará activamente los pedidos y generará/enviará cupones según sus reglas.
    - *Cuando está desactivado:* El módulo estará inactivo y no se generarán ni enviarán cupones, independientemente de otros ajustes.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Ha terminado de configurar todas sus reglas y está listo para lanzar su programa de recompensas. Actívelo para comenzar a enviar cupones. Si necesita pausar temporalmente el programa para mantenimiento, desactívelo.
- **Estados de pedido para la generación de cupones:**

  - **Qué hace este ajuste:** Determina qué estados de pedido activarán el proceso de generación de cupones. Solo los pedidos que alcancen uno de estos estados seleccionados calificarán para una recompensa.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está seleccionado:* Los pedidos con estos estados se verificarán para determinar la elegibilidad del cupón.
    - *Cuando no está seleccionado:* Los pedidos con estos estados serán ignorados por el módulo.
  - **Valor recomendado:** Típicamente "Pago aceptado" y "Entregado". También podría incluir "Enviado" si desea enviar el cupón antes.
  - **Escenario / ejemplo de comerciante:** Desea asegurarse de que los clientes solo reciban un cupón después de que su pago sea confirmado y el pedido esté siendo procesado o haya sido entregado. Seleccione "Pago aceptado" y "Entregado" para evitar el envío de cupones para pedidos cancelados o pendientes.
- **Total mínimo del pedido para el cupón:**

  - **Qué hace este ajuste:** Establece un valor total mínimo (excluyendo el envío) que un pedido debe cumplir para calificar para un cupón.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un valor (por ejemplo, 50):* Solo los pedidos con un total mayor o igual a 50 activarán un cupón.
    - *Cuando se establece en 0 (o vacío):* Todos los pedidos, independientemente de su valor, serán elegibles (si se cumplen otras condiciones).
  - **Valor recomendado:** Un valor que tenga sentido comercial para su valor promedio de pedido, o 0 si desea recompensar todos los pedidos.
  - **Escenario / ejemplo de comerciante:** Desea fomentar compras más grandes. Establezca esto en 50 € para que solo los clientes que gasten 50 € o más reciban un descuento, haciendo del cupón una recompensa por transacciones de mayor valor.

#### Ajustes del código de cupón

- **Prefijo del código de cupón:**

  - **Qué hace este ajuste:** Una cadena de caracteres que aparecerá al principio de cada código de cupón generado. Esto le ayuda a identificar los cupones de este módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece (por ejemplo, "REWARD"):* Los códigos se verán como "REWARDABCD123".
    - *Cuando está vacío:* Los códigos serán puramente caracteres aleatorios.
  - **Valor recomendado:** Un prefijo corto y descriptivo como "REWARD", "THANKYOU" o las iniciales de su tienda.
  - **Escenario / ejemplo de comerciante:** Realiza varias promociones. Usar "REWARD" como prefijo le ayuda a identificar rápidamente qué cupones provienen de este módulo en sus reglas de descuento de PrestaShop.
- **Longitud del código de cupón:**

  - **Qué hace este ajuste:** Define el número total de caracteres en el código de cupón generado (incluido el prefijo).
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 10 con un prefijo "REWARD":* La parte aleatoria tendrá 4 caracteres de largo (10 - 6 para "REWARD").
    - *Cuando se establece en un número menor:* Códigos más cortos, potencialmente más fáciles de escribir pero menos únicos.
    - *Cuando se establece en un número mayor:* Códigos más largos, más seguros pero más difíciles de escribir.
  - **Valor recomendado:** 8-12 caracteres (incluido el prefijo) para un buen equilibrio entre seguridad y usabilidad.
  - **Escenario / ejemplo de comerciante:** Desea que los códigos sean fáciles de recordar pero aún únicos. Una longitud de 10-12 caracteres suele ser suficiente.
- **Tipo de valor del cupón:**

  - **Qué hace este ajuste:** Determina si el cupón ofrece un descuento porcentual o una cantidad fija.
  - **Efecto de cambiar este ajuste:**
    - *Porcentaje:* El cupón deducirá un porcentaje del total del pedido.
    - *Cantidad fija:* El cupón deducirá un valor monetario específico.
  - **Valor recomendado:** Depende de su estrategia de marketing. El porcentaje es bueno para fomentar pedidos más grandes, la cantidad fija es más simple y clara.
  - **Escenario / ejemplo de comerciante:** Desea ofrecer un 10% de descuento en el próximo pedido, por lo que selecciona "Porcentaje". Si desea ofrecer un descuento fijo de 5 €, seleccione "Cantidad fija".
- **Valor del cupón:**

  - **Qué hace este ajuste:** El valor de descuento real. Será un porcentaje (por ejemplo, 10) o una cantidad fija (por ejemplo, 5.00) dependiendo del ajuste "Tipo de valor del cupón".
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 10 y "Porcentaje":* Los clientes obtienen un 10% de descuento.
    - *Cuando se establece en 5.00 y "Cantidad fija":* Los clientes obtienen 5 € de descuento.
  - **Valor recomendado:** Un valor que haga la oferta atractiva pero que sea sostenible para su negocio.
  - **Escenario / ejemplo de comerciante:** Decide ofrecer un 15% de descuento, por lo que introduce "15" aquí después de seleccionar "Porcentaje" arriba.
- **Total mínimo del pedido para el uso del cupón:**

  - **Qué hace este ajuste:** Establece un importe mínimo de compra requerido para que el cliente pueda usar el código de cupón generado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 20:* El cliente debe gastar al menos 20 € en su próximo pedido para aplicar el cupón.
    - *Cuando se establece en 0 (o vacío):* El cupón se puede usar en cualquier pedido, independientemente de su valor.
  - **Valor recomendado:** Un valor ligeramente superior a su valor promedio de pedido para fomentar las ventas adicionales, o 0 si desea la máxima usabilidad.
  - **Escenario / ejemplo de comerciante:** Desea asegurarse de que el cupón fomente una nueva compra, no solo un pequeño complemento. Establezca esto en 25 €, para que el cliente necesite comprar algo sustancial para usar su cupón de 5 €.
- **Validez del cupón (Días):**

  - **Qué hace este ajuste:** Define cuántos días será válido el código de cupón generado a partir de la fecha de su creación.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 30:* El cupón caducará 30 días después de su envío.
    - *Cuando se establece en 0 (o vacío):* El cupón será válido indefinidamente (no recomendado, ya que elimina la urgencia).
  - **Valor recomendado:** 30-90 días para crear urgencia sin ser demasiado restrictivo.
  - **Escenario / ejemplo de comerciante:** Desea que los clientes usen su cupón dentro de un plazo razonable. Establezca esto en 60 días para darles dos meses para realizar otra compra.
- **Aplicar cupón a grupos de clientes específicos:**

  - **Qué hace este ajuste:** Le permite restringir el uso del cupón generado a grupos de clientes específicos (por ejemplo, "Clientes VIP", "Mayoristas").
  - **Efecto de cambiar este ajuste:**
    - *Cuando está seleccionado:* Solo los clientes que pertenecen a los grupos elegidos pueden usar el cupón.
    - *Cuando no está seleccionado (o todos los grupos seleccionados):* Cualquier cliente puede usar el cupón.
  - **Valor recomendado:** Deje todos seleccionados a menos que tenga una estrategia de segmentación específica.
  - **Escenario / ejemplo de comerciante:** Desea ofrecer un descuento especial solo a su grupo de "Clientes registrados". Seleccione solo ese grupo aquí.
- **Aplicar cupón a productos/categorías específicos:**

  - **Qué hace este ajuste:** Le permite restringir la aplicabilidad del cupón a ciertos productos o categorías de productos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está seleccionado:* El cupón solo se aplicará a los artículos de los productos/categorías elegidos.
    - *Cuando no está seleccionado (o ninguno seleccionado):* El cupón se aplica a todos los productos del carrito.
  - **Valor recomendado:** Deje sin seleccionar para descuentos generales en toda la tienda. Use esto para promociones dirigidas.
  - **Escenario / ejemplo de comerciante:** Desea promocionar una nueva colección específica. Puede configurar el cupón para que solo se aplique a los productos dentro de esa categoría.
- **Excluir productos con descuento:**

  - **Qué hace este ajuste:** Si está activado, el cupón no se puede usar en productos que ya están en oferta o tienen un precio específico.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Evita la "acumulación" de descuentos, asegurando que los clientes no obtengan descuentos dobles.
    - *Cuando está desactivado:* Los cupones se pueden aplicar a artículos ya rebajados.
  - **Valor recomendado:** SÍ, para proteger sus márgenes de beneficio.
  - **Escenario / ejemplo de comerciante:** Está realizando una venta del 20% en toda la tienda. No quiere que los clientes usen su cupón de recompensa además de eso, dándoles efectivamente un 30% de descuento. Active esto para evitarlo.
- **Excluir envío:**

  - **Qué hace este ajuste:** Determina si el descuento del cupón se aplica al costo de envío del pedido.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El cupón solo reduce el total del producto, no la tarifa de envío.
    - *Cuando está desactivado:* El cupón puede reducir el valor total del pedido, incluido el envío.
  - **Valor recomendado:** SÍ, ya que los costos de envío suelen ser fijos y no forman parte de su margen de producto.
  - **Escenario / ejemplo de comerciante:** Ofrece envío gratuito por encima de un cierto umbral. Desea que el cupón solo afecte los precios de los productos, no el costo de envío. Active esto.
- **Cupón para el N-ésimo pedido:**

  - **Qué hace este ajuste:** Esta es una característica poderosa que le permite especificar para qué número de pedido (1º, 2º, 3º, etc.) un cliente recibe un cupón.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 1:* Solo el primer pedido del cliente activará un cupón.
    - *Cuando se establece en 2:* Solo su segundo pedido activará un cupón.
    - *Cuando se establece en 0 (o vacío):* Cada pedido que califique activará un cupón (si se cumplen otras condiciones).
  - **Valor recomendado:** 1 para una oferta de "bienvenida", o 0 para un programa de lealtad general. También puede crear múltiples reglas (ver sección 4.2) para diferentes N-ésimos pedidos.
  - **Escenario / ejemplo de comerciante:** Desea dar un "gracias" especial a los compradores primerizos. Establezca esto en "1". Para un programa de lealtad general, déjelo en "0" o cree reglas específicas para el 2º, 3º, etc., pedidos.

#### Ajustes de la plantilla de correo electrónico

- **Asunto del correo electrónico:**

  - **Qué hace este ajuste:** La línea de asunto del correo electrónico que los clientes reciben con su código de cupón.
  - **Efecto de cambiar este ajuste:** Esto es lo que los clientes ven en su bandeja de entrada. Una línea de asunto atractiva aumenta las tasas de apertura.
  - **Valor recomendado:** Algo atractivo como "¡Su descuento especial para su próximo pedido!" o "¡Gracias! Aquí tiene un regalo de nuestra parte."
  - **Escenario / ejemplo de comerciante:** Desea dejar claro que se trata de una recompensa. Establezca el asunto en "¡Su cupón exclusivo de [Nombre de su tienda]!"
- **Contenido del correo electrónico:**

  - **Qué hace este ajuste:** El cuerpo principal del correo electrónico. Puede usar marcadores de posición como `{customer_name}`, `{voucher_code}`, `{voucher_value}`, `{min_order_total}`, `{validity_days}` para personalizar el mensaje.
  - **Efecto de cambiar este ajuste:** Aquí es donde comunica el valor del cupón y cómo usarlo. Un mensaje claro y amigable fomenta el uso.
  - **Valor recomendado:** Un mensaje de bienvenida, instrucciones claras y todos los detalles relevantes del cupón.
  - **Escenario / ejemplo de comerciante:** "Estimado/a {customer\_name}, ¡gracias por su reciente compra! Como muestra de nuestro agradecimiento, aquí tiene un código de descuento de {voucher\_value} para su próximo pedido: **{voucher\_code}**. Este cupón es válido por {validity\_days} días y se puede usar en pedidos superiores a {min\_order\_total}. ¡Felices compras!"
- **Enviar correo electrónico al cliente:**

  - **Qué hace este ajuste:** Controla si el correo electrónico que contiene el cupón se envía realmente al cliente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes reciben el correo electrónico.
    - *Cuando está desactivado:* Los cupones se siguen generando (si está activado), pero los clientes no reciben una notificación por correo electrónico. En ese caso, deberá comunicar el código de cupón a través de otro canal.
  - **Valor recomendado:** SÍ, ya que el correo electrónico es el método de entrega principal de este módulo.
  - **Escenario / ejemplo de comerciante:** Ha configurado todo y desea que los clientes reciban sus recompensas. Active esto. Si está probando o prefiere enviar códigos manualmente, podría desactivarlo temporalmente.

#### Ajustes de la tarea programada (Cron Job)

- **URL de la tarea programada (Cron Job):**
  - **Qué hace este ajuste:** Esta es una URL única que, al ser accedida, activa el módulo para verificar nuevos pedidos que califican y generar/enviar cupones.
  - **Efecto de cambiar este ajuste:** Esta URL es crucial para la automatización del módulo. Debe ser llamada regularmente.
  - **Valor recomendado:** NO cambie esta URL. Cópiela y configúrela en el panel de control de su alojamiento.
  - **Escenario / ejemplo de comerciante:** Copia esta URL y la pega en el gestor de tareas programadas (cron job) de su proveedor de alojamiento (por ejemplo, cPanel, Plesk) para que se ejecute cada 15-30 minutos. Esto asegura que los cupones se envíen rápidamente después de que se procesen los pedidos.

### 2.2 Pantalla de administración dedicada: Lista de recompensas (Back Office > Recompensas > Lista de recompensas)

Esta pantalla proporciona una visión general completa de todos los códigos de cupón que han sido generados por el módulo. Actúa como un registro y una interfaz de gestión para su programa de recompensas.

- **Nombre de la pantalla y ubicación del menú:** **Lista de recompensas** (se encuentra bajo un nuevo elemento de menú "Recompensas" en su Back Office de PrestaShop, o potencialmente bajo "Catálogo" o "Marketing" dependiendo de su versión y tema de PrestaShop).
- **Acciones y configuraciones disponibles:**
  - **Columnas de la tabla:** Verá una tabla con las siguientes columnas:
    - **ID:** El identificador único para la entrada de recompensa.
    - **ID de pedido:** El ID del pedido de PrestaShop que activó esta recompensa.
    - **Cliente:** El nombre del cliente que recibió el cupón.
    - **Correo electrónico:** La dirección de correo electrónico del cliente.
    - **Referencia del pedido:** El número de referencia único del pedido.
    - **Código de recompensa:** El código de cupón real generado y enviado al cliente.
    - **Fecha de generación:** La fecha y hora en que se generó el cupón.
  - **Filtrado y búsqueda:** Normalmente puede filtrar o buscar por cualquiera de estas columnas (por ejemplo, buscar un correo electrónico de cliente específico, ID de pedido o código de cupón) para encontrar entradas de recompensa específicas.
  - **Sin botones "Añadir/Editar":** Esta pantalla es principalmente para ver las recompensas generadas. Los cupones se crean automáticamente según su configuración, no se añaden manualmente aquí.
- **Efecto de los cambios:** Esta pantalla es un registro de solo lectura. Los cambios en la configuración del módulo (Sección 4.1) afectarán a las generaciones de cupones *futuras*, pero las entradas existentes aquí reflejan eventos pasados.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  - Revise periódicamente esta lista para monitorear la actividad de su programa de recompensas.
  - Si un cliente afirma que no recibió un cupón, puede buscar rápidamente su pedido aquí, encontrar el "Código de recompensa" y confirmar su fecha de generación. Luego puede proporcionar manualmente el código al cliente si es necesario.
  - Utilice las opciones de filtrado para analizar qué pedidos están activando recompensas o para solucionar consultas específicas de los clientes.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | Activar módulo | SÍ | Interruptor principal para la funcionalidad del módulo. |
|  | Estados de pedido para la generación de cupones | Pago aceptado, Entregado | Define qué estados de pedido activan la generación de cupones. |
|  | Total mínimo del pedido para el cupón | 0 (o su valor deseado) | Valor mínimo del pedido para que un pedido califique para un cupón. |
|  | Prefijo del código de cupón | REWARD (o su elección) | Prefijo para los códigos de cupón generados. |
|  | Longitud del código de cupón | 8-12 | Longitud total del código de cupón. |
|  | Tipo de valor del cupón | Porcentaje / Cantidad fija | Elija entre un descuento porcentual o de cantidad fija. |
|  | Valor del cupón | Su valor deseado (por ejemplo, 10 o 5.00) | El valor de descuento real del cupón. |
|  | Total mínimo del pedido para el uso del cupón | 0 (o su valor deseado) | Valor mínimo del pedido requerido para *usar* el cupón. |
|  | Validez del cupón (Días) | 30-90 | Cuántos días es válido el cupón después de su generación. |
|  | Aplicar cupón a grupos de clientes específicos | Todos seleccionados | Restringe el uso del cupón a los grupos de clientes seleccionados. |
|  | Aplicar cupón a productos/categorías específicos | Ninguno seleccionado | Restringe el uso del cupón a los productos/categorías seleccionados. |
|  | Excluir productos con descuento | SÍ | Evita que los cupones se apliquen a artículos ya rebajados. |
|  | Excluir envío | SÍ | Evita que los cupones reduzcan los costos de envío. |
|  | Cupón para el N-ésimo pedido | 0 (o 1 para el primer pedido) | Especifica para qué número de pedido (1º, 2º, etc.) se genera un cupón. |
|  | Asunto del correo electrónico | ¡Su descuento especial! | Línea de asunto del correo electrónico que contiene el cupón. |
|  | Contenido del correo electrónico | Mensaje personalizado con marcadores de posición | Cuerpo del correo electrónico, incluidos los detalles del cupón. |
|  | Enviar correo electrónico al cliente | SÍ | Controla si el correo electrónico del cupón se envía al cliente. |
|  | URL de la tarea programada (Cron Job) | NO cambiar | URL esencial para la generación automática de cupones. |
| **Lista de recompensas** | ID, ID de pedido, Cliente, Correo electrónico, Referencia del pedido, Código de recompensa, Fecha de generación | N/A (solo lectura) | Muestra un registro de todos los cupones generados para monitoreo y resolución de problemas. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis clientes no reciben los correos electrónicos de los cupones. ¿Qué debo verificar?**
R:

1.  **¿Módulo activado?** Verifique que "Activar módulo" esté configurado en SÍ en la configuración del módulo.
2.  **Estados del pedido:** Asegúrese de que el estado del pedido coincida con uno de los "Estados de pedido para la generación de cupones" que seleccionó.
3.  **Tarea programada (Cron Job):** Verifique que su tarea programada esté configurada correctamente y se ejecute regularmente en su alojamiento. La "URL de la tarea programada (Cron Job)" debe ser llamada para que el módulo procese los pedidos.
4.  **Envío de correo electrónico activado:** Asegúrese de que "Enviar correo electrónico al cliente" esté configurado en SÍ.
5.  **Carpeta de spam:** Pida a los clientes que revisen sus carpetas de spam o correo no deseado.
6.  **Configuración de correo electrónico de PrestaShop:** Verifique la configuración principal de correo electrónico de su PrestaShop (Parámetros avanzados > Correo electrónico) para asegurarse de que los correos electrónicos se envían correctamente desde su tienda.

**P: Se están generando cupones, pero no parecen funcionar para los clientes.**
R:

1.  **Validez del cupón:** Verifique el ajuste "Validez del cupón (Días)". ¿Ha caducado el cupón?
2.  **Total mínimo del pedido para el uso:** ¿El carrito actual del cliente cumple con el "Total mínimo del pedido para el uso del cupón"?
3.  **Grupos de clientes:** ¿El cliente forma parte de los "Aplicar cupón a grupos de clientes específicos" seleccionados?
4.  **Restricciones de producto/categoría:** ¿Los productos en el carrito del cliente son elegibles según "Aplicar cupón a productos/categorías específicos"?
5.  **Productos con descuento excluidos:** ¿El cliente está intentando usar el cupón en un producto ya rebajado y "Excluir productos con descuento" está activado?
6.  **Errores tipográficos:** Pida al cliente que revise el código del cupón para detectar cualquier error tipográfico.

**P: Quiero ofrecer diferentes cupones para diferentes números de pedido (por ejemplo, 1º, 2º, 5º pedido). ¿Cómo lo hago?**
R: La descripción del módulo indica soporte para "muchos tipos de acciones como: cupón para el primer pedido, cupón para el segundo pedido, quinto, sexto, etc.". Esto implica que el módulo tiene un mecanismo para definir múltiples reglas basadas en el N-ésimo pedido.

- **Verificar pestañas de reglas múltiples:** Busque pestañas o secciones adicionales dentro de la configuración del módulo que le permitan "Añadir nueva regla" o definir configuraciones separadas para diferentes valores de "N-ésimo pedido". Si existe dicha interfaz, crearía una regla separada para cada N-ésimo pedido con sus ajustes de cupón específicos.
- **Si solo existe un campo "Cupón para el N-ésimo pedido":** Si el módulo solo presenta un único campo "Cupón para el N-ésimo pedido" en la página de configuración principal, significa que solo puede establecer *una* de estas reglas a la vez. Para implementar un sistema por niveles, necesitaría cambiar manualmente este ajuste después de un cierto período o considerar si la versión actual del módulo admite esta funcionalidad avanzada a través de una interfaz menos obvia. Para la mayoría de los usuarios, configurarlo en `0` (cada pedido) o `1` (solo el primer pedido) es el caso de uso principal.

**P: El módulo está ralentizando mi Back Office / Front Office.**
R: Este módulo opera principalmente en segundo plano a través de una tarea programada y tiene un impacto mínimo en el rendimiento del front-office. Si nota ralentizaciones:

1.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y borre la caché de su PrestaShop.
2.  **Verificar recursos del servidor:** Monitoree el uso de CPU y memoria de su servidor, especialmente cuando se ejecuta la tarea programada. Si su servidor tiene poca potencia, incluso las tareas simples pueden causar ralentizaciones.
3.  **Otros módulos:** Desactive temporalmente otros módulos instalados recientemente para ver si hay un conflicto.

**P: ¿Puedo personalizar aún más la plantilla de correo electrónico?**
R: Sí, el módulo proporciona los campos "Asunto del correo electrónico" y "Contenido del correo electrónico" con marcadores de posición para una personalización básica. Para cambios de diseño avanzados (por ejemplo, añadir el logotipo de su tienda, cambiar fuentes/colores), normalmente necesitaría modificar directamente los archivos de plantilla de correo electrónico del módulo. Esto generalmente requiere un webmaster o desarrollador. La estructura interna del módulo sugiere que utiliza `lib/emailTemplatesManager`, lo que podría ofrecer una gestión de plantillas más avanzada dentro del propio módulo, pero la configuración principal se realiza a través de los campos de texto.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura

El módulo "Recompensas - Códigos de cupón después de los pedidos" sigue una arquitectura estándar de módulo de PrestaShop, aprovechando los principios MVC cuando corresponde. Su funcionalidad principal gira en torno a un mecanismo de tarea programada (cron job) que verifica periódicamente los pedidos que califican y, al encontrarlos, genera objetos `CartRule` (cupones) de PrestaShop y envía correos electrónicos. El módulo extiende `Module` para su funcionalidad principal y utiliza `AdminController` para su interfaz de gestión del Back Office. También incorpora varias bibliotecas de utilidad para la gestión de plantillas de correo electrónico y la funcionalidad de búsqueda.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

- `controllers/front/cronJob.php`
  - **Nombre de la clase:** `OrdercouponsCronJobModuleFrontController` (probablemente, basado en el nombre del archivo)
  - **Clase padre:** `ModuleFrontController`
  - **Responsabilidad:** Este controlador está diseñado para ser accedido a través de la URL de la tarea programada (Cron Job) proporcionada en la configuración del módulo. Cuando se invoca, activa la lógica principal dentro del archivo del módulo `cronjob.php` para procesar pedidos, generar cupones y enviar correos electrónicos. Normalmente no renderiza ningún contenido del front-office, sino que ejecuta tareas en segundo plano.
- `controllers/front/index.php`
  - **Nombre de la clase:** `OrdercouponsIndexModuleFrontController` (probablemente)
  - **Clase padre:** `ModuleFrontController`
  - **Responsabilidad:** Este es a menudo un marcador de posición o un controlador de redirección simple. En muchos módulos, `index.php` en un directorio de controlador simplemente asegura que el acceso directo al directorio no resulte en una lista de directorios, o podría contener una lógica mínima para una vista predeterminada del front-office si el módulo tuviera una. Para este módulo, es poco probable que tenga una responsabilidad significativa de renderizado del front-office.

#### Controladores de administración del Back-Office

- `controllers/admin/AdminOrderCouponsRewards.php`
  - **Nombre de la clase:** `AdminOrderCouponsRewardsController`
  - **Clase padre:** `ModuleAdminController` (o `AdminController` en versiones anteriores)
  - **Nombre de la pestaña:** "Lista de recompensas" (bajo un elemento de menú "Recompensas")
  - **Entidad gestionada:** `orewards_list` (probablemente una tabla de base de datos personalizada para registrar las recompensas generadas).
  - **Responsabilidad:** Este controlador gestiona la "Lista de recompensas" en el Back Office de PrestaShop. Muestra una lista de todos los códigos de cupón generados, los ID de pedido asociados, los detalles del cliente y las fechas de generación. Utiliza `HelperList` para renderizar la tabla y proporciona capacidades de filtrado. No permite la creación o edición manual de recompensas, ya que se generan automáticamente.
- `controllers/admin/index.php`
  - **Nombre de la clase:** `AdminOrdercouponsIndexController` (probablemente)
  - **Clase padre:** `ModuleAdminController` (o `AdminController`)
  - **Responsabilidad:** Similar al `index.php` del front-office, este es probablemente un marcador de posición o un controlador predeterminado para la sección de administración, asegurando la protección del directorio o proporcionando una vista de respaldo. La funcionalidad principal de administración es manejada por `AdminOrderCouponsRewards.php`.

### 4.3 Clases y modelos principales (`classes/`)

El inventario proporcionado no indica clases personalizadas en el directorio `classes/`. Esto sugiere que la lógica central del módulo para la generación de cupones podría estar directamente dentro del archivo principal del módulo `cronjob.php` o aprovecha el `ObjectModel` `CartRule` (Descuento) incorporado de PrestaShop y sus métodos asociados.

- **Interacción con `CartRule`:** El módulo interactuaría directamente con la clase `CartRule` de PrestaShop para crear nuevos códigos de descuento. Esto implica establecer propiedades como `code`, `value`, `reduction_type`, `minimum_amount`, `date_from`, `date_to`, `quantity`, `quantity_per_user`, `id_customer`, `id_group`, `id_product`, `id_category`, `reduction_exclude_special`, `free_shipping`, etc., basándose en la configuración del módulo.
- **Tabla personalizada `orewards_list`:** Aunque no se enumera explícitamente ningún `ObjectModel`, el `AdminOrderCouponsRewardsController` gestiona `orewards_list`. Esto implica fuertemente que existe una tabla de base de datos personalizada `ps_orewards_list` (o un prefijo similar) para registrar las recompensas generadas. El controlador consultaría directamente esta tabla o usaría una capa de acceso a datos simple.

### 4.4 Activos JavaScript (`views/js/`)

- `ordercoupons/js/script.js`
  - **Alcance:** Probablemente Back-office.
  - **Responsabilidad:** JavaScript general para la página de configuración del módulo o las pantallas de administración. Esto podría incluir validación de formularios, llamadas AJAX para guardar configuraciones, actualizaciones dinámicas de la interfaz de usuario o detectores de eventos para opciones de configuración específicas.
- `ordercoupons/lib/emailTemplatesManager/js/emailTemplatesManager.js`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Gestiona la interfaz de edición de plantillas de correo electrónico. Este script manejaría la inserción dinámica de marcadores de posición, capacidades de edición de texto enriquecido, funcionalidad de vista previa y guardado del contenido del correo electrónico.
- `ordercoupons/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Proporciona funcionalidad de autocompletado para campos de entrada, probablemente utilizada para seleccionar productos, categorías o grupos de clientes específicos dentro de los formularios de configuración del módulo. Manejaría las solicitudes AJAX para obtener resultados de búsqueda y mostrarlos al usuario.
- `ordercoupons/lib/voucherengine/script.js`
  - **Alcance:** Back-office.
  - **Responsabilidad:** JavaScript específico relacionado con el motor de generación de cupones. Esto podría incluir lógica para el cálculo dinámico de la longitud del código de cupón, la validación de los valores de los cupones o la interacción con los ajustes de `CartRule` en el formulario de configuración.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `ordercoupons/css.css`
  - **Alcance:** Principalmente Back-office, potencialmente algo de front-office si el módulo tuviera elementos visibles. Dada la naturaleza del módulo, es principalmente para el estilo de administración.
  - **Componentes principales de la interfaz de usuario:** Estilo general para la página de configuración del módulo y la tabla "Lista de recompensas".
  - **Selectores de clase CSS clave:** `.ordercoupons-config`, `.ordercoupons-table`, `.ordercoupons-form-group`.
- `ordercoupons/lib/emailTemplatesManager/css/emailTemplatesManager.css`
  - **Alcance:** Back-office.
  - **Componentes principales de la interfaz de usuario:** Estilos para la interfaz del editor de plantillas de correo electrónico, incluyendo áreas de texto, botones y secciones de vista previa.
  - **Selectores de clase CSS clave:** `.email-template-editor`, `.template-preview`.
- `ordercoupons/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back-office.
  - **Componentes principales de la interfaz de usuario:** Estilo para los desplegables de autocompletado y los campos de entrada.
  - **Selectores de clase CSS clave:** `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item`.
- `ordercoupons/lib/voucherengine/ps16.css`
  - **Alcance:** Back-office.
  - **Componentes principales de la interfaz de usuario:** Ajustes de estilo específicos para la compatibilidad con PrestaShop 1.6 o elementos específicos relacionados con el motor de cupones, asegurando una apariencia consistente en diferentes versiones de PS.
  - **Selectores de clase CSS clave:** `.voucher-engine-settings`, `.ps16-compat`.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

#### Plantillas de gancho (`views/templates/hook/`)

El inventario no enumera ninguna plantilla directamente bajo `views/templates/hook/`. Esto confirma que el módulo no renderiza ningún contenido visual directamente en los ganchos estándar de PrestaShop como `displayHeader`, `displayRightColumn`, `displayFooter`, etc. Su interacción con el front-office es puramente a través del correo electrónico.

#### Plantillas de administración (`views/templates/admin/`)

- `ordercoupons/views/templates/admin/admin.tpl`
  - **Propósito:** La plantilla principal para la página de configuración del módulo (accesible a través de `getContent()` en `cronjob.php`). Contendría la estructura del formulario para todos los ajustes descritos en la Sección 4.1.
- `ordercoupons/views/templates/admin/customerGroups.tpl`
  - **Propósito:** Una plantilla parcial probablemente utilizada dentro de `admin.tpl` para renderizar la interfaz de selección de "Aplicar cupón a grupos de clientes específicos".
- `ordercoupons/views/templates/admin/orderstates.tpl`
  - **Propósito:** Una plantilla parcial probablemente utilizada dentro de `admin.tpl` para renderizar la interfaz de selección de "Estados de pedido para la generación de cupones".
- `ordercoupons/views/templates/admin/scripts.tpl`
  - **Propósito:** Una plantilla parcial utilizada para incluir archivos JavaScript o JavaScript en línea específicos de la página de configuración de administración. Esta es una práctica común para mantener el JS separado de la estructura HTML principal.

#### Plantillas del Front-office (`views/templates/front/`)

El inventario no enumera ninguna plantilla directamente bajo `views/templates/front/`. Esto es consistente con el comportamiento del módulo de no mostrar contenido del front-office.

#### Plantillas de biblioteca

- `ordercoupons/lib/emailTemplatesManager/views/buttonManager.tpl`
- `ordercoupons/lib/emailTemplatesManager/views/createTemplateForm.tpl`
- `ordercoupons/lib/emailTemplatesManager/views/editTemplateForm.tpl`
- `ordercoupons/lib/emailTemplatesManager/views/mainForm.tpl`
- `ordercoupons/lib/emailTemplatesManager/views/selectInput.tpl`
  - **Propósito:** Estas plantillas forman parte de la biblioteca `emailTemplatesManager` y se utilizan para renderizar la interfaz para gestionar y editar plantillas de correo electrónico dentro de la configuración del módulo. `mainForm.tpl` probablemente sería el punto de entrada principal, siendo las otras parciales para elementos específicos de la interfaz de usuario.
- `ordercoupons/lib/searchTool/views/scripts.tpl`
  - **Propósito:** Una plantilla para incluir archivos JavaScript o scripts en línea para la biblioteca `searchTool`, específicamente para la funcionalidad de autocompletado.

### 4.7 Esquema de la base de datos y mapa de ganchos

#### Tablas de la base de datos

- **`ps_configuration`**: El módulo almacena sus ajustes de configuración (por ejemplo, `ORDERCOUPONS_ENABLED`, `ORDERCOUPONS_ORDER_STATES`, `ORDERCOUPONS_VOUCHER_VALUE`) en la tabla estándar `ps_configuration` de PrestaShop.
- **`ps_orewards_list` (Tabla personalizada implícita)**: Basado en el `AdminOrderCouponsRewardsController` que gestiona `orewards_list`, es muy probable que el módulo cree una tabla de base de datos personalizada, probablemente llamada `ps_orewards_list`, para registrar cada cupón generado.
  - **Esquema (Campos probables):**
    - `id_orewards_list` (CLAVE PRIMARIA, INT)
    - `id_order` (INT)
    - `id_customer` (INT)
    - `customer_email` (VARCHAR)
    - `order_reference` (VARCHAR)
    - `reward_code` (VARCHAR)
    - `date_add` (DATETIME)

#### Tabla de ganchos registrados

La descripción del módulo menciona "Ganchos del Front-Office: Cabecera, Columnas, Producto o Pie de página". Sin embargo, el inventario de archivos y la función principal del módulo (envío de cupones por correo electrónico) sugieren que es probable que *no* se utilicen para mostrar contenido, sino quizás para procesamiento interno o carga de activos si el módulo tuviera algún componente de front-end. Dada la naturaleza del módulo, los ganchos más críticos son los ganchos de acción.

| Nombre del gancho | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionValidateOrder` | Después de que un pedido ha sido validado y guardado con éxito en la base de datos. | Este es el gancho más probable para que el módulo detecte nuevos pedidos que deben procesarse para la generación de cupones. El módulo escucharía este evento para identificar posibles candidatos. |
| `actionOrderStatusPostUpdate` | Después de que el estado de un pedido ha sido cambiado en el Back Office. | Crucial para que el módulo verifique si un pedido ha alcanzado uno de los "Estados de pedido para la generación de cupones" configurados (por ejemplo, "Pago aceptado", "Entregado"). Aquí es donde la tarea programada probablemente activaría la lógica de generación de cupones. |
| `displayBackOfficeHeader` | Renderiza contenido en la sección `<head>` del Back Office. | Se utiliza para incluir archivos CSS y JavaScript específicos del módulo para las páginas de configuración de administración y la pantalla "Lista de recompensas". |
| `moduleRoutes` | Permite a los módulos definir URLs amigables personalizadas. | Menos probable para este módulo, pero posible si necesitara una ruta específica para su tarea programada u otros procesos internos. |
| `displayHeader` | Renderiza contenido en la sección `<head>` del front office. | Si el módulo necesitara cargar cualquier JS/CSS global para posibles futuras características de front-end, o para fines de seguimiento. (Improbable para la funcionalidad actual). |
| `displayRightColumn` / `displayLeftColumn` | Renderiza contenido en las columnas laterales del front office. | No utilizado para la funcionalidad actual de este módulo. |
| `displayFooter` | Renderiza contenido en el pie de página del front office. | No utilizado para la funcionalidad actual de este módulo. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Recompensas - Códigos de cupón después de los pedidos", consulte su cuenta de cliente en MyPresta.eu. Puede descargar las versiones más recientes desde su historial de pedidos y acceder a canales de soporte dedicados para cualquier asistencia técnica o consulta.

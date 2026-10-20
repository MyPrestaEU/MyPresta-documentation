---
title: "Transferencia bancaria con descuento - Manual del comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Transferencia bancaria con descuento' de MyPresta.eu."
sidebar:
  label: "Transferencia bancaria con descuento - Manual del comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Bankwire with discount en MyPresta.eu](https://mypresta.eu/modules/payment-process/bankwire-with-discount.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/bankwire-with-discount/)
>
> ---


# Transferencia bancaria con descuento

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son necesarias para PrestaShop y generalmente están disponibles en todos los entornos de alojamiento modernos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Transferencia bancaria con descuento)

Esta es la pantalla de configuración principal donde configurará todas las funcionalidades principales del módulo.

#### **Configuración general**

- **Habilitar pago por transferencia bancaria:**

  - **Qué hace este ajuste:** Este es el interruptor principal para habilitar o deshabilitar el método de pago "Transferencia bancaria con descuento" en su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes verán "Pagar por transferencia bancaria" como una opción de pago durante el proceso de compra.
    - *Cuando está deshabilitado:* La opción de pago por transferencia bancaria estará oculta para los clientes.
  - **Valor recomendado:** SÍ (para usar las funciones del módulo).
  - **Escenario del comerciante:** Desea ofrecer pagos por transferencia bancaria.
- **Título de la transferencia bancaria:**

  - **Qué hace este ajuste:** Define el título que se muestra para la opción de pago por transferencia bancaria en la página de pago.
  - **Efecto de cambiar este ajuste:** Cambia el texto que ven los clientes al elegir este método de pago.
  - **Valor recomendado:** "Pagar por transferencia bancaria", "Transferencia bancaria (¡con descuento!)" o similar.
  - **Escenario del comerciante:** Desea etiquetar claramente el método de pago para los clientes.
- **Instrucciones de pago (Resumen en el proceso de compra):**

  - **Qué hace este ajuste:** Un texto corto que se muestra en la página de selección de pago (antes de la confirmación) para dar a los clientes instrucciones rápidas o información sobre la transferencia bancaria.
  - **Efecto de cambiar este ajuste:** Proporciona un contexto inmediato al cliente sobre el método de transferencia bancaria.
  - **Valor recomendado:** "Recibirá los datos bancarios después de confirmar su pedido. ¡Descuento aplicado!"
  - **Escenario del comerciante:** Desea informar a los clientes sobre los próximos pasos o destacar el beneficio del descuento con antelación.
- **Instrucciones de pago (Después de la confirmación del pedido):**

  - **Qué hace este ajuste:** Instrucciones detalladas que se muestran en la página de confirmación del pedido después de que un cliente ha realizado un pedido por transferencia bancaria. Aquí es donde debe introducir los datos de su cuenta bancaria.
  - **Efecto de cambiar este ajuste:** Proporciona la información esencial para que los clientes realicen la transferencia bancaria.
  - **Valor recomendado:** Incluya el nombre de su banco, el titular de la cuenta, el IBAN, el SWIFT/BIC y cualquier nota específica (por ejemplo, "Incluya la referencia de su pedido en la descripción de la transferencia").
  - **Escenario del comerciante:** Esto es crucial para que los clientes completen con éxito su pago.

#### **Datos de la cuenta bancaria**

Estos campos se utilizan para proporcionar la información de su cuenta bancaria a los clientes.

- **Titular de la cuenta:**

  - **Qué hace este ajuste:** El nombre del titular de la cuenta bancaria.
  - **Efecto de cambiar este ajuste:** Muestra este nombre al cliente.
  - **Valor recomendado:** El nombre de su empresa o su nombre personal.
  - **Escenario del comerciante:** Esencial para la transferencia bancaria.
- **Nombre del banco:**

  - **Qué hace este ajuste:** El nombre de su banco.
  - **Efecto de cambiar este ajuste:** Muestra este nombre al cliente.
  - **Valor recomendado:** Por ejemplo, "Deutsche Bank", "Bank of America".
  - **Escenario del comerciante:** Esencial para la transferencia bancaria.
- **Dirección:**

  - **Qué hace este ajuste:** La dirección de su banco.
  - **Efecto de cambiar este ajuste:** Muestra esta dirección al cliente.
  - **Valor recomendado:** La dirección de la sucursal de su banco.
  - **Escenario del comerciante:** Puede ser necesaria para transferencias internacionales.
- **IBAN (Número de cuenta bancaria internacional):**

  - **Qué hace este ajuste:** Su IBAN, un número de cuenta bancaria internacional estandarizado.
  - **Efecto de cambiar este ajuste:** Muestra este número al cliente.
  - **Valor recomendado:** Su IBAN completo.
  - **Escenario del comerciante:** Crucial para transferencias bancarias, especialmente dentro de Europa.
- **SWIFT/BIC (Código de identificación bancaria):**

  - **Qué hace este ajuste:** Su código SWIFT/BIC, utilizado para transferencias bancarias internacionales.
  - **Efecto de cambiar este ajuste:** Muestra este código al cliente.
  - **Valor recomendado:** Su código SWIFT/BIC completo.
  - **Escenario del comerciante:** Esencial para transferencias bancarias internacionales.
- **Información adicional:**

  - **Qué hace este ajuste:** Cualquier nota o instrucción adicional que desee proporcionar con respecto a la transferencia bancaria (por ejemplo, "Permita de 1 a 3 días hábiles para el procesamiento").
  - **Efecto de cambiar este ajuste:** Proporciona orientación adicional al cliente.
  - **Valor recomendado:** Cualquier instrucción específica no cubierta por otros campos.
  - **Escenario del comerciante:** Desea gestionar las expectativas del cliente sobre los tiempos de transferencia.

#### **Configuración de descuentos y recargos**

Esta sección le permite configurar descuentos o recargos por usar la transferencia bancaria.

- **Tipo de descuento:**

  - **Qué hace este ajuste:** Determina cómo se calcula el descuento.
  - **Efecto de cambiar este ajuste:**
    - *Porcentaje:* El descuento es un porcentaje del total del pedido.
    - *Cantidad fija:* El descuento es una cantidad fija, independientemente del total del pedido.
  - **Valor recomendado:** Porcentaje (a menudo más atractivo para valores de pedido variables).
  - **Escenario del comerciante:** Desea ofrecer un 5% de descuento o un descuento fijo de 10 €.
- **Valor del descuento:**

  - **Qué hace este ajuste:** El valor real del descuento (por ejemplo, "5" para el 5% o "10" para una cantidad fija).
  - **Efecto de cambiar este ajuste:** Aplica directamente el descuento al total del pedido si se elige la transferencia bancaria.
  - **Valor recomendado:** Un valor que haga atractiva la transferencia bancaria sin perjudicar sus márgenes.
  - **Escenario del comerciante:** Decide ofrecer un 3% de descuento o un descuento de 5 €.
- **Base del porcentaje (si el tipo de descuento es Porcentaje):**

  - **Qué hace este ajuste:** Especifica a qué parte del total del pedido se aplica el descuento porcentual.
  - **Efecto de cambiar este ajuste:** Cambia la cantidad base para el cálculo del descuento.
    - *Total del pedido (con impuestos):* Descuento calculado sobre el precio total, incluidos los impuestos.
    - *Total del pedido (sin impuestos):* Descuento calculado sobre el precio antes de impuestos.
    - *Total de productos (con impuestos):* Descuento solo sobre el valor del producto, incluidos los impuestos.
    - *Total de productos (sin impuestos):* Descuento solo sobre el valor del producto, excluidos los impuestos.
  - **Valor recomendado:** Total del pedido (con impuestos) para mayor simplicidad y claridad para el cliente.
  - **Escenario del comerciante:** Desea ofrecer un 5% de descuento sobre el precio final completo que ve el cliente.
- **Valor mínimo del carrito:**

  - **Qué hace este ajuste:** El valor total mínimo que debe tener un pedido para que se aplique el descuento por transferencia bancaria.
  - **Efecto de cambiar este ajuste:** El descuento solo aparecerá y se aplicará si el total del carrito cumple o supera este valor.
  - **Valor recomendado:** Dejar vacío si no hay mínimo, o establecer un valor para fomentar pedidos más grandes.
  - **Escenario del comerciante:** Solo desea ofrecer un descuento en pedidos superiores a 100 €.
- **Valor máximo del carrito:**

  - **Qué hace este ajuste:** El valor total máximo que puede tener un pedido para que se aplique el descuento por transferencia bancaria.
  - **Efecto de cambiar este ajuste:** El descuento no se aplicará si el total del carrito supera este valor.
  - **Valor recomendado:** Dejar vacío si no hay máximo, o establecer un valor para limitar la exposición al descuento en pedidos muy grandes.
  - **Escenario del comerciante:** No desea aplicar un descuento en pedidos superiores a 1000 €.
- **Monedas:**

  - **Qué hace este ajuste:** Selecciona las monedas para las que estará disponible el método de pago por transferencia bancaria (y su descuento).
  - **Efecto de cambiar este ajuste:** La opción de pago solo aparecerá para los clientes que compren en las monedas seleccionadas.
  - **Valor recomendado:** Seleccione todas las monedas que acepte.
  - **Escenario del comerciante:** Solo acepta transferencias bancarias en EUR y USD.
- **Zonas:**

  - **Qué hace este ajuste:** Selecciona las zonas geográficas para las que estará disponible el método de pago por transferencia bancaria (y su descuento).
  - **Efecto de cambiar este ajuste:** La opción de pago solo aparecerá para los clientes cuya dirección de envío se encuentre dentro de las zonas seleccionadas.
  - **Valor recomendado:** Seleccione todas las zonas a las que realiza envíos.
  - **Escenario del comerciante:** Solo ofrece transferencia bancaria en Europa.
- **Países:**

  - **Qué hace este ajuste:** Selecciona países específicos donde estará disponible el método de pago por transferencia bancaria (y su descuento).
  - **Efecto de cambiar este ajuste:** Anula la configuración de zona para países específicos.
  - **Valor recomendado:** Seleccione todos los países a los que realiza envíos.
  - **Escenario del comerciante:** Desea excluir un país específico de los pagos por transferencia bancaria.
- **Grupos de clientes:**

  - **Qué hace este ajuste:** Selecciona qué grupos de clientes pueden ver y usar el método de pago por transferencia bancaria (y su descuento).
  - **Efecto de cambiar este ajuste:** Solo los clientes que pertenezcan a los grupos seleccionados verán esta opción de pago.
  - **Valor recomendado:** Seleccione todos los grupos de clientes relevantes (por ejemplo, "Cliente", "Visitante", "Invitado").
  - **Escenario del comerciante:** Solo desea ofrecer transferencia bancaria a clientes registrados.

#### **Gestión de pedidos impagados**

Estas funciones le ayudan a gestionar los pedidos que se realizan mediante transferencia bancaria pero aún no se han pagado.

- **Enviar recordatorios para pedidos impagados:**

  - **Qué hace este ajuste:** Habilita o deshabilita los recordatorios automáticos por correo electrónico a los clientes para pedidos por transferencia bancaria impagados.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El módulo enviará correos electrónicos de recordatorio.
    - *Cuando está deshabilitado:* No se enviarán recordatorios.
  - **Valor recomendado:** SÍ (ayuda a reducir los pagos abandonados).
  - **Escenario del comerciante:** Desea recordar suavemente a los clientes que completen su pago.
- **Primer recordatorio después de (días):**

  - **Qué hace este ajuste:** El número de días después de realizar un pedido antes de que se envíe el primer correo electrónico de recordatorio.
  - **Efecto de cambiar este ajuste:** Controla el momento del primer recordatorio.
  - **Valor recomendado:** 2-3 días (da tiempo a los clientes para pagar, pero no demasiado).
  - **Escenario del comerciante:** Desea enviar un recordatorio si el pago no se recibe en 2 días.
- **Máx. recordatorios por pedido:**

  - **Qué hace este ajuste:** El número máximo de correos electrónicos de recordatorio que activará un pedido.
  - **Efecto de cambiar este ajuste:** Evita enviar spam a los clientes con demasiados recordatorios.
  - **Valor recomendado:** 1-2 (suficiente para recordar sin molestar).
  - **Escenario del comerciante:** Desea enviar solo un correo electrónico de recordatorio.
- **Cancelar automáticamente pedidos impagados:**

  - **Qué hace este ajuste:** Habilita o deshabilita la cancelación automática de pedidos por transferencia bancaria que permanecen impagados después de un período especificado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los pedidos se cancelarán automáticamente, liberando inventario.
    - *Cuando está deshabilitado:* Los pedidos permanecerán en estado "Pendiente de pago por transferencia bancaria" indefinidamente.
  - **Valor recomendado:** SÍ (automatiza la gestión de inventario y mantiene limpia la lista de pedidos).
  - **Escenario del comerciante:** No desea retener inventario para pedidos impagados durante demasiado tiempo.
- **Cancelar después de (días):**

  - **Qué hace este ajuste:** El número de días después de realizar un pedido antes de que se cancele automáticamente si no se ha pagado.
  - **Efecto de cambiar este ajuste:** Controla cuándo se cancelan los pedidos impagados.
  - **Valor recomendado:** 5-7 días (permite un tiempo razonable para el pago, pero evita retenciones indefinidas).
  - **Escenario del comerciante:** Desea cancelar pedidos si el pago no se recibe en 7 días.
- **Poner automáticamente en lista negra a los infractores:**

  - **Qué hace este ajuste:** Si está habilitado, los clientes que repetidamente realizan pedidos por transferencia bancaria y luego los cancelan debido a la falta de pago se añadirán a una lista negra.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes que superen el umbral serán incluidos en la lista negra.
    - *Cuando está deshabilitado:* Ningún cliente será incluido en la lista negra automáticamente.
  - **Valor recomendado:** SÍ (ayuda a disuadir a clientes fraudulentos o que hacen perder el tiempo).
  - **Escenario del comerciante:** Desea evitar que los clientes que nunca pagan realicen futuros pedidos por transferencia bancaria.
- **Umbral de pedidos cancelados:**

  - **Qué hace este ajuste:** El número de pedidos por transferencia bancaria cancelados que puede tener un cliente antes de ser incluido automáticamente en la lista negra.
  - **Efecto de cambiar este ajuste:** Define la tolerancia a la falta de pago antes de la inclusión en la lista negra.
  - **Valor recomendado:** 2-3 (permite errores genuinos pero detecta a los reincidentes).
  - **Escenario del comerciante:** Desea incluir en la lista negra a un cliente después de 3 pedidos por transferencia bancaria impagados y cancelados.

#### **Configuración avanzada**

- **Token de tarea programada (Cron Job Token):**

  - **Qué hace este ajuste:** Un token de seguridad único utilizado para proteger la URL de la tarea programada del módulo. Esto es esencial para que funcionen las funciones automatizadas de recordatorio y cancelación.
  - **Efecto de cambiar este ajuste:** La tarea programada solo se ejecutará si este token se incluye correctamente en la URL.
  - **Valor recomendado:** Dejar como está generado. No cambiar a menos que sepa lo que está haciendo.
  - **Escenario del comerciante:** Necesita configurar una tarea programada en su servidor para ejecutar las tareas automatizadas del módulo. La URL de la tarea programada se verá algo así: `su_tienda.com/module/bankwiredis/cron?token=SU_TOKEN_AQUI`.
- **Selectores CSS para actualizaciones dinámicas:**

  - **Qué hace este ajuste:** Estos campos le permiten especificar selectores CSS para elementos en su página de pago que muestran el total del carrito, el subtotal y el coste de envío. El módulo los utiliza para actualizar dinámicamente los precios cuando se aplica un descuento.
  - **Efecto de cambiar este ajuste:** Si su tema utiliza clases CSS no estándar para estos elementos, ajustar estos selectores garantiza que el descuento se refleje correctamente en los precios mostrados durante el proceso de compra.
  - **Valor recomendado:** Dejar como predeterminado a menos que el descuento no se muestre correctamente en su página de pago. Si hay problemas, consulte a su desarrollador de temas o a un webmaster.
  - **Escenario del comerciante:** Su tema personalizado utiliza `.my-custom-total-price` en lugar del predeterminado `.cart-total-price`. Debería actualizar este campo para asegurarse de que el descuento se aplique visualmente.
- **Plantilla de correo electrónico:**

  - **Qué hace este ajuste:** Le permite seleccionar una plantilla de correo electrónico personalizada para las instrucciones de pago por transferencia bancaria y los recordatorios.
  - **Efecto de cambiar este ajuste:** Cambia el diseño y el contenido de los correos electrónicos enviados por el módulo.
  - **Valor recomendado:** Predeterminado (a menos que tenga una plantilla personalizada).
  - **Escenario del comerciante:** Desea utilizar una plantilla de correo electrónico de marca para las comunicaciones de transferencia bancaria.

#### **Reglas de visibilidad (Segmentación avanzada de descuentos)**

Esta sección le permite crear reglas altamente específicas para cuándo se ofrece el descuento por transferencia bancaria.

- **Nombre de la regla:**

  - **Qué hace este ajuste:** Un nombre descriptivo para su regla de descuento (por ejemplo, "Descuento de vacaciones para transferencia bancaria").
  - **Efecto de cambiar este ajuste:** Le ayuda a identificar y gestionar diferentes reglas.
  - **Valor recomendado:** Nombre claro y conciso.
  - **Escenario del comerciante:** Tiene varias reglas de descuento y necesita distinguirlas.
- **Activa:**

  - **Qué hace este ajuste:** Habilita o deshabilita esta regla de descuento específica.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* La regla está activa y se comprobarán sus condiciones.
    - *Cuando está deshabilitado:* La regla se ignora.
  - **Valor recomendado:** SÍ (si desea que se aplique la regla).
  - **Escenario del comerciante:** Desea deshabilitar temporalmente un descuento estacional.
- **Posición (prioridad):**

  - **Qué hace este ajuste:** Determina el orden en que se evalúan las reglas si se pudieran aplicar varias reglas. Los números más bajos tienen mayor prioridad.
  - **Efecto de cambiar este ajuste:** Si el carrito de un cliente coincide con varias reglas, se aplicará la que tenga la posición más baja.
  - **Valor recomendado:** Utilice números secuenciales (1, 2, 3...) para gestionar la prioridad.
  - **Escenario del comerciante:** Si un cliente califica tanto para una regla de "5% de descuento general" (posición 10) como para una regla de "10% de descuento VIP" (posición 5), se aplicará la regla VIP.
- **Tipo de descuento, Valor del descuento, Base del porcentaje, Valor mínimo del carrito, Valor máximo del carrito, Monedas, Zonas, Países, Grupos de clientes:**

  - **Qué hace este ajuste:** Estos son los mismos ajustes descritos en la sección "Configuración de descuentos y recargos" anterior, pero aplicados específicamente a *esta regla individual*. Esto le permite tener diferentes cantidades o condiciones de descuento para diferentes escenarios.
  - **Efecto de cambiar este ajuste:** El descuento definido dentro de esta regla solo se aplicará si se cumplen todas sus condiciones específicas.
  - **Valor recomendado:** Configure según su estrategia promocional específica.
  - **Escenario del comerciante:** Desea ofrecer un 10% de descuento para pagos por transferencia bancaria solo para clientes del grupo "Mayorista", y solo para pedidos superiores a 500 €.
- **Productos:**

  - **Qué hace este ajuste:** Le permite especificar que esta regla de descuento solo se aplica si ciertos productos están en el carrito.
  - **Efecto de cambiar este ajuste:** El descuento por transferencia bancaria solo se ofrecerá si uno o más de los productos seleccionados están presentes en el carrito del cliente.
  - **Valor recomendado:** Dejar vacío para aplicar a todos los productos, o seleccionar productos específicos para promociones dirigidas.
  - **Escenario del comerciante:** Desea ofrecer un descuento por transferencia bancaria solo si un cliente compra un artículo específico de alto valor.
- **Categorías:**

  - **Qué hace este ajuste:** Le permite especificar que esta regla de descuento solo se aplica si hay productos de ciertas categorías en el carrito.
  - **Efecto de cambiar este ajuste:** El descuento por transferencia bancaria solo se ofrecerá si uno o más productos de las categorías seleccionadas están presentes en el carrito del cliente.
  - **Valor recomendado:** Dejar vacío para aplicar a todas las categorías, o seleccionar categorías específicas para promociones dirigidas.
  - **Escenario del comerciante:** Desea ofrecer un descuento por transferencia bancaria solo para productos de su categoría "Electrónica".

#### **Tabla de referencia rápida de configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | Habilitar pago por transferencia bancaria | SÍ | Activa/desactiva el método de pago. |
|  | Título de la transferencia bancaria | "Pagar por transferencia bancaria" | Texto que se muestra para la opción de pago. |
|  | Instrucciones de pago (Proceso de compra) | Texto corto y claro | Información que se muestra en la página de selección de pago. |
|  | Instrucciones de pago (Confirmación) | Información bancaria detallada | Datos bancarios e instrucciones después del pedido. |
|  | Titular de la cuenta | Nombre de su empresa | Nombre en la cuenta bancaria. |
|  | Nombre del banco | Su banco | Nombre de su banco. |
|  | Dirección | Dirección de su banco | Dirección de su banco. |
|  | IBAN | Su IBAN | Número de cuenta bancaria internacional. |
|  | SWIFT/BIC | Su SWIFT/BIC | Código de identificación bancaria para transferencias internacionales. |
|  | Información adicional | Notas opcionales | Instrucciones adicionales para los clientes. |
|  | Tipo de descuento | Porcentaje | Cómo se calcula el descuento (porcentaje/fijo). |
|  | Valor del descuento | 0 (o valor deseado) | La cantidad o porcentaje real del descuento. |
|  | Base del porcentaje | Total del pedido (con impuestos) | A qué cantidad se aplica el descuento porcentual. |
|  | Valor mínimo del carrito | Vacío (o valor deseado) | Valor mínimo del pedido para el descuento. |
|  | Valor máximo del carrito | Vacío (o valor deseado) | Valor máximo del pedido para el descuento. |
|  | Monedas | Todas activas | Monedas donde la transferencia bancaria está disponible. |
|  | Zonas | Todas activas | Zonas geográficas donde la transferencia bancaria está disponible. |
|  | Países | Todos activos | Países específicos donde la transferencia bancaria está disponible. |
|  | Grupos de clientes | Todos activos | Grupos de clientes que pueden usar la transferencia bancaria. |
|  | Enviar recordatorios para pedidos impagados | SÍ | Habilita los recordatorios por correo electrónico para pedidos impagados. |
|  | Primer recordatorio después de (días) | 2-3 días | Retraso antes del primer recordatorio. |
|  | Máx. recordatorios por pedido | 1-2 | Número máximo de correos electrónicos de recordatorio. |
|  | Cancelar automáticamente pedidos impagados | SÍ | Cancela automáticamente los pedidos impagados. |
|  | Cancelar después de (días) | 5-7 días | Retraso antes de la cancelación automática. |
|  | Poner automáticamente en lista negra a los infractores | SÍ | Pone en lista negra a los clientes con demasiados pedidos cancelados. |
|  | Umbral de pedidos cancelados | 2-3 | Número de pedidos cancelados antes de la inclusión en la lista negra. |
|  | Token de tarea programada (Cron Job Token) | Autogenerado | Token de seguridad para la tarea programada. |
|  | Selectores CSS | Predeterminado (o específico del tema) | Para actualizaciones dinámicas de precios en el proceso de compra. |
|  | Plantilla de correo electrónico | Predeterminado | Plantilla de correo electrónico para comunicaciones de transferencia bancaria. |
|  | **Reglas de visibilidad** | Nombre de la regla | Nombre descriptivo |
|  | Activa | SÍ | Activa/desactiva una regla específica. |
|  | Posición (prioridad) | 1, 2, 3… | Orden de evaluación de reglas (menor = mayor prioridad). |
|  | Productos | Vacío (o productos específicos) | El descuento se aplica solo si estos productos están en el carrito. |
|  | Categorías | Vacío (o categorías específicas) | El descuento se aplica solo si hay productos de estas categorías en el carrito. |

### 2.2 Pantalla del controlador del Back-Office: AdminBankwiredisSearchController

- **Nombre de la pantalla y ubicación del menú:** Este controlador se utiliza normalmente para gestionar entidades específicas relacionadas con el módulo, como clientes en la lista negra o reglas de descuento específicas, a menudo accesibles a través de una subpestaña en la configuración principal del módulo o un elemento de menú dedicado. En este módulo, es probable que se utilice para gestionar las reglas de visibilidad o los clientes en la lista negra.
  - **Ubicación del menú:** Probablemente se accede a través de una pestaña o enlace dentro de la página de configuración principal del módulo "Transferencia bancaria con descuento", o potencialmente en **Vender > Pedidos > Lista negra de transferencia bancaria con descuento** (ejemplo, la ubicación real puede variar según la versión de PrestaShop y el diseño del módulo).
- **Acciones y configuraciones disponibles:** Esta pantalla proporciona una vista de gestión basada en cuadrícula.
  - **Tabla de listado:** Muestra una lista de elementos (por ejemplo, clientes en la lista negra, reglas de descuento). Cada fila suele mostrar detalles relevantes como ID de cliente, correo electrónico del cliente, motivo de la lista negra, nombre de la regla, estado activo, etc.
  - **Botones Añadir/Editar:** Permite añadir manualmente nuevas entradas (por ejemplo, poner manualmente a un cliente en la lista negra) o editar las existentes.
  - **Acciones masivas:** Opciones para realizar acciones en varios elementos seleccionados (por ejemplo, eliminar varios clientes de la lista negra).
  - **Buscar/Filtrar:** Herramientas para encontrar entradas específicas dentro de la lista.
- **Efecto de los cambios:**
  - **Añadir/Editar entradas de la lista negra:** Afecta directamente a qué clientes se les impide utilizar el método de pago por transferencia bancaria.
  - **Añadir/Editar reglas de descuento:** Modifica las condiciones bajo las cuales se aplican los descuentos, afectando los precios y los incentivos para los clientes.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Revise regularmente la lista de clientes en la lista negra para asegurarse de que esté actualizada.
  2. Si necesita poner manualmente a un cliente en la lista negra (por ejemplo, después de una comunicación directa), utilice la función "Añadir" aquí.
  3. Si necesita ajustar o crear nuevas reglas de descuento, aquí es donde las gestionaría, asegurándose de que se alineen con sus promociones actuales.

### 2.3 Pantalla del controlador del Back-Office: index.php (Controlador de administración)

- **Nombre de la pantalla y ubicación del menú:** El archivo `index.php` en un directorio de controlador de administración a menudo sirve como marcador de posición o redirección, o en algunos casos, puede ser el punto de entrada para un panel de control o un listado simple. Dadas las características del módulo, esto podría ser un panel de control para estadísticas de transferencia bancaria o un listado simple de pedidos pendientes de transferencia bancaria.
  - **Ubicación del menú:** Potencialmente una subpestaña en la configuración principal del módulo, o un elemento de menú dedicado como **Vender > Pedidos > Panel de control de transferencia bancaria con descuento**.
- **Acciones y configuraciones disponibles:** Esta pantalla probablemente presenta una cuadrícula o un panel de control.
  - **Vista de cuadrícula / gestión:** Podría mostrar una lista de pedidos recientes por transferencia bancaria, su estado, recordatorios de pago enviados o estado de cancelación.
  - **Análisis/Estadísticas:** Podría mostrar gráficos o resúmenes relacionados con los pagos por transferencia bancaria, como tasas de conversión, descuento promedio aplicado o número de pedidos impagados.
- **Efecto de los cambios:** Esta pantalla es típicamente para monitoreo e informes, en lugar de cambios directos de configuración. Cualquier acción realizada aquí (por ejemplo, marcar manualmente un pedido como pagado) actualizaría el estado del pedido en PrestaShop.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Revise periódicamente este panel de control para monitorear el rendimiento de su método de pago por transferencia bancaria.
  2. Revise los pedidos pendientes de transferencia bancaria para asegurarse de que se estén procesando o recordando/cancelando según lo esperado.
  3. Utilice las estadísticas disponibles para evaluar la eficacia de sus descuentos por transferencia bancaria y el sistema de recordatorios.

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: La opción de pago por transferencia bancaria no aparece en mi página de pago.**

- **R:** Primero, compruebe si "Habilitar pago por transferencia bancaria" está configurado en SÍ en la configuración del módulo.
- **R:** A continuación, verifique la configuración de sus "Monedas", "Zonas", "Países" y "Grupos de clientes". Si el contexto del cliente (moneda, dirección de envío o grupo) no coincide con sus selecciones, el método de pago no aparecerá.
- **R:** Si tiene reglas de visibilidad específicas, asegúrese de que el carrito del cliente cumpla todas las condiciones (valor mínimo/máximo del carrito, productos/categorías específicos).
- **R:** Borre la caché de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché).

**P2: El descuento no se aplica o no se muestra correctamente en la página de pago.**

- **R:** Vuelva a comprobar la configuración de "Tipo de descuento" y "Valor del descuento".
- **R:** Revise cualquier configuración de "Valor mínimo del carrito" o "Valor máximo del carrito"; el total del carrito debe estar dentro de estos rangos.
- **R:** Si está utilizando un tema personalizado, es posible que el módulo no pueda encontrar los selectores CSS correctos para actualizar los precios dinámicamente. Vaya a la sección "Configuración avanzada" y asegúrese de que los "Selectores CSS para actualizaciones dinámicas" coincidan con los selectores reales de su tema para el total del carrito, el subtotal y el envío. Es posible que necesite un webmaster para inspeccionar el código de su tema.
- **R:** Borre la caché de PrestaShop.

**P3: Los recordatorios o cancelaciones automáticas no funcionan.**

- **R:** Esto es casi siempre un problema de la tarea programada (cron job). Debe configurar una tarea programada en su servidor para ejecutar periódicamente las tareas del módulo.
- **R:** En la sección "Configuración avanzada" del módulo, copie el "Token de tarea programada" y la URL completa de la tarea programada.
- **R:** Acceda a su panel de control de alojamiento (cPanel, Plesk, etc.) y busque la sección "Tareas programadas".
- **R:** Añada una nueva tarea programada que ejecute la URL proporcionada cada pocas horas (por ejemplo, `wget -O /dev/null "https://su_tienda.com/module/bankwiredis/cron?token=SU_TOKEN_AQUI"`).
- **R:** Asegúrese de que "Enviar recordatorios para pedidos impagados" y "Cancelar automáticamente pedidos impagados" estén habilitados, y que los días estén configurados correctamente.

**P4: ¿Cómo traduzco los textos del módulo a otros idiomas?**

- **R:** En su Back Office de PrestaShop, vaya a **Internacional > Traducciones**.
- **R:** Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Transferencia bancaria con descuento" en el menú desplegable del módulo.
- **R:** A continuación, puede editar todas las cadenas traducibles del módulo. Recuerde guardar los cambios.

**P5: Un cliente fue incluido en la lista negra, pero quiero permitirle usar la transferencia bancaria de nuevo.**

- **R:** Navegue a la pantalla de administración dedicada del módulo (probablemente en **Vender > Pedidos > Lista negra de transferencia bancaria con descuento** o similar, o una pestaña dentro de la configuración del módulo).
- **R:** Busque al cliente en la lista y elimine su entrada de la lista negra o edítela para desactivar la lista negra para él.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura

El módulo "Transferencia bancaria con descuento" (`bankwiredis`) amplía la funcionalidad de pago de PrestaShop, adhiriéndose al patrón MVC. Se integra con el proceso de pago a través de los hooks `PaymentOptions`, gestiona los estados de los pedidos e implementa tareas automatizadas (recordatorios, cancelaciones, inclusión en la lista negra) a través de una tarea programada. La lógica de descuento se aplica dinámicamente durante el proceso de pago y se mantiene con el pedido. Los controladores de administración personalizados proporcionan interfaces de gestión para las reglas de descuento y los clientes en la lista negra.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `controllers/front/cron.php`
  - **Nombre de la clase:** `BankwiredisCronModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Este controlador gestiona la ejecución de tareas programadas. Está diseñado para ser llamado por una tarea programada del lado del servidor utilizando un token seguro. Procesa los recordatorios de pedidos impagados, las cancelaciones automáticas y la inclusión de clientes en la lista negra basándose en la configuración del módulo. No renderiza ningún contenido de front-office directamente, sino que realiza operaciones en segundo plano.
- `controllers/front/index.php`
  - **Nombre de la clase:** `BankwiredisIndexModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** A menudo un marcador de posición o un punto de entrada predeterminado. En este módulo, podría gestionar redirecciones o servir como respaldo si no se encuentran otros controladores frontales específicos. Normalmente no tiene una función directa de cara al usuario.
- `controllers/front/payment.php`
  - **Nombre de la clase:** `BankwiredisPaymentModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Este controlador es responsable de mostrar los detalles e instrucciones de pago por transferencia bancaria al cliente *después* de que haya seleccionado la transferencia bancaria como su método de pago pero *antes* de que el pedido esté completamente validado. Prepara los datos (datos bancarios, importe final con descuento) para la plantilla `payment.tpl` o `validation.tpl`.
- `controllers/front/validation.php`
  - **Nombre de la clase:** `BankwiredisValidationModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Este es el controlador crucial que procesa la validación final de un pedido por transferencia bancaria. Después de que el cliente confirma su elección, este controlador crea el pedido en PrestaShop, establece su estado inicial (por ejemplo, "Pendiente de pago por transferencia bancaria"), aplica el descuento calculado y redirige al cliente a la página de confirmación del pedido.

#### Controladores de administración del Back-Office

- `controllers/admin/AdminBankwiredisSearchController.php`
  - **Nombre de la clase:** `AdminBankwiredisSearchController` (extiende `ModuleAdminController`)
  - **Nombre de la pestaña:** Probablemente una subpestaña en la configuración principal del módulo o una entrada de menú dedicada.
  - **Entidad gestionada:** Este controlador gestiona las entidades personalizadas del módulo, específicamente las reglas de visibilidad de descuentos y, potencialmente, los clientes en la lista negra. Proporciona una interfaz estándar de PrestaShop `HelperList` o `HelperForm` para ver, añadir, editar y eliminar estos registros.
- `controllers/admin/index.php`
  - **Nombre de la clase:** `AdminBankwiredisIndexController` (extiende `ModuleAdminController`)
  - **Nombre de la pestaña:** Similar a `AdminBankwiredisSearchController`, esta sería una página de administración dedicada.
  - **Entidad gestionada:** Dadas las características del módulo, este controlador probablemente sirve como un panel de control o una interfaz de gestión para los datos centrales del módulo, como una lista de pedidos pendientes de transferencia bancaria, estadísticas o una vista simplificada de los clientes en la lista negra.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto sugiere que los datos del módulo (como las reglas de descuento, los clientes en la lista negra) podrían almacenarse directamente en `ps_configuration` o gestionarse a través de instancias genéricas de `ObjectModel` definidas dentro del archivo principal `bankwiredis.php` o directamente dentro de los controladores de administración.

- **Nota:** Si se utilizan tablas personalizadas, sus definiciones de `ObjectModel` residirían típicamente aquí. El módulo probablemente utiliza `Configuration::get()` y `Configuration::updateValue()` para la mayoría de las configuraciones y, potencialmente, `Db::getInstance()` para interacciones directas con la base de datos para estructuras de datos más complejas como reglas de descuento o clientes en la lista negra, si no están mapeadas a un `ObjectModel` personalizado.

### 4.4 Activos de JavaScript (`views/js/`)

- `bankwiredis/lib/searchTool/views/js/autocomplete.js`
  - **Ámbito:** Back-office.
  - **Funcionalidad:** Proporciona funcionalidad de autocompletado, probablemente utilizada en formularios de administración (por ejemplo, `AdminBankwiredisSearchController`) para seleccionar productos o categorías al definir reglas de visibilidad de descuentos. Escucha la entrada del usuario en campos de texto específicos y realiza solicitudes AJAX para sugerir elementos coincidentes.
- `bankwiredis/views/js/adminBankwiredisAccounts.js`
  - **Ámbito:** Back-office.
  - **Funcionalidad:** Probablemente gestiona el comportamiento dinámico en la página de configuración del módulo relacionado con los detalles de la cuenta bancaria. Esto podría incluir mostrar/ocultar campos según las opciones seleccionadas, la validación de entrada o las llamadas AJAX para guardar la información de la cuenta.
- `bankwiredis/views/js/adminBankwiredisDashboard.js`
  - **Ámbito:** Back-office.
  - **Funcionalidad:** Gestiona elementos interactivos y visualización de datos en el panel de administración del módulo (por ejemplo, `AdminBankwiredisIndexController`). Esto podría implicar la obtención de datos a través de AJAX para rellenar gráficos, tablas o actualizar estadísticas, y la gestión de las interacciones del usuario con los widgets del panel de control.
- `bankwiredis/views/js/bankwiredis-checkout.js`
  - **Ámbito:** Front-office.
  - **Funcionalidad:** Este es un script crítico para la experiencia del cliente. Escucha la selección de la opción de pago por transferencia bancaria en la página de pago. Al seleccionarla, realiza una llamada AJAX al controlador frontal del módulo para calcular y mostrar el descuento dinámico, actualizando el total del pedido, el subtotal y los elementos del coste de envío en la página. Utiliza los selectores CSS configurados en el back office (`BDIS_CSS_PAY_INPUT`, `BDIS_CSS_CART_TOTAL`, etc.) para dirigirse a los elementos DOM correctos para la actualización.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `bankwiredis/lib/searchTool/views/css/autocomplete.css`
  - **Ámbito:** Back-office.
  - **Funcionalidad:** Estiliza las sugerencias desplegables de autocompletado y los campos de entrada utilizados en las herramientas de búsqueda de administración.
- `bankwiredis/views/css/admin_bankwiredis.css`
  - **Ámbito:** Back-office.
  - **Funcionalidad:** Proporciona un estilo específico para la página de configuración del módulo y las vistas del controlador de administración personalizado, garantizando una interfaz coherente y fácil de usar dentro del back office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

- `bankwiredis/views/templates/hook/infos.tpl`
  - **Hook:** Probablemente `displayPaymentInfo` o similar.
  - **Salida:** Muestra información general o un resumen sobre el método de pago por transferencia bancaria, potencialmente incluyendo la oferta de descuento, en la página de selección de pago o en el resumen del pedido.
- `bankwiredis/views/templates/hook/payment.tpl`
  - **Hook:** `displayPaymentOptions` (PrestaShop 1.7+), `displayPayment` (PrestaShop 1.6).
  - **Salida:** Renderiza la opción de pago por transferencia bancaria real en la página de pago, incluyendo su título, descripción y la cantidad de descuento calculada dinámicamente. Aquí es donde el cliente selecciona "Pagar por transferencia bancaria".
- `bankwiredis/views/templates/hook/payment_return.tpl`
  - **Hook:** `displayPaymentReturn`.
  - **Salida:** Muestra los datos de la cuenta bancaria y las instrucciones de pago en la página de confirmación del pedido después de que un cliente haya realizado con éxito un pedido por transferencia bancaria.
- `bankwiredis/views/templates/hook/payment_return_pdf_invoice.tpl`
  - **Hook:** `displayPDFInvoice` (o similar para la generación de PDF).
  - **Salida:** Proporciona el contenido necesario (datos bancarios, resumen del descuento) para ser incluido en la factura en PDF generada para pedidos por transferencia bancaria.

#### Plantillas de administración (`views/templates/admin/`)

- `bankwiredis/lib/searchTool/views/scripts.tpl`
  - **Salida:** Probablemente incluye activos de JavaScript y CSS para la herramienta de búsqueda de autocompletado dentro de los formularios de administración.
- `bankwiredis/views/templates/admin/scopeSelector.tpl`
  - **Salida:** Una plantilla para seleccionar el ámbito (por ejemplo, tienda, grupo, todas las tiendas) en un entorno multitienda, a menudo utilizada en formularios de configuración.
- `bankwiredis/views/templates/admin/selectedProducts.tpl`
  - **Salida:** Muestra una lista de productos que se han seleccionado para una regla de descuento específica (por ejemplo, en `AdminBankwiredisSearchController` al configurar una regla basada en productos).

#### Plantillas de Front-office (`views/templates/front/`)

- `bankwiredis/views/templates/front/validation.tpl`
  - **Salida:** Esta plantilla es renderizada por `BankwiredisPaymentModuleFrontController` o `BankwiredisValidationModuleFrontController` para mostrar los datos bancarios finales y las instrucciones *antes* de que el pedido se confirme por completo o inmediatamente después, proporcionando una página dedicada para las instrucciones de pago.

### 4.7 Esquema de la base de datos y mapa de Hooks

#### Tablas de la base de datos

El módulo utiliza principalmente la tabla `ps_configuration` de PrestaShop para la mayoría de sus configuraciones (por ejemplo, `BANK_WIRE_DIS_OWNER_`, `BDIS_CRON_TOKEN`, `BANK_WIRE_DIS_CHARGEP`).
Para datos más complejos como las reglas de visibilidad de descuentos y los clientes en la lista negra, el módulo probablemente crea tablas personalizadas durante su método `install()`. Basándose en las opciones de configuración, estas tablas serían típicamente:

- `ps_bankwiredis_rules`: Almacena la definición de cada regla de descuento (nombre de la regla, estado activo, tipo de descuento, valor, carrito mínimo/máximo, monedas, zonas, países, grupos de clientes, productos, categorías).
- `ps_bankwiredis_blacklist`: Almacena registros de clientes en la lista negra (ID de cliente, correo electrónico, motivo, fecha de inclusión en la lista negra).
- `ps_bankwiredis_reminders`: Almacena un registro de los correos electrónicos de recordatorio enviados para cada pedido para rastrear `Max reminders per order`.

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Se utiliza para cargar activos CSS y JavaScript del front-office (`bankwiredis-checkout.js`) para la visualización dinámica de descuentos. |
| `actionAdminControllerSetMedia` | Cuando un controlador de administración carga sus activos multimedia. | Se utiliza para cargar activos CSS y JavaScript del back-office (`admin_bankwiredis.css`, `adminBankwiredisAccounts.js`, `autocomplete.js`) para la configuración del módulo y las páginas de administración. |
| `displayPaymentOptions` | En la página de pago, cuando se enumeran las opciones de pago. | Renderiza la opción de pago por transferencia bancaria, incluido el descuento calculado, utilizando `payment.tpl`. |
| `displayPaymentReturn` | En la página de confirmación del pedido después de un pedido exitoso. | Muestra los datos de la cuenta bancaria y las instrucciones de pago al cliente, utilizando `payment_return.tpl`. |
| `displayPDFInvoice` | Cuando se genera una factura en PDF. | Inyecta los datos de la cuenta bancaria y la información del descuento en la factura en PDF generada para pedidos por transferencia bancaria. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Se utiliza para capturar los detalles del pedido, aplicar el descuento final y, potencialmente, registrar el pedido para el procesamiento de recordatorios/cancelaciones. |
| `displayPaymentInfo` | (Implícito) A menudo se utiliza para mostrar información adicional en la selección de pago. | Renderiza `infos.tpl` con información general de transferencia bancaria. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial del desarrollador, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Asegúrese de estar ejecutando la última versión compatible del módulo para su tienda PrestaShop.

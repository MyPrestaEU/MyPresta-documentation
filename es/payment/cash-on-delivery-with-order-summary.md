---
title: "Pago contra reembolso con resumen de pedido - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Pago contra reembolso con resumen de pedido' de MyPresta.eu."
sidebar:
  label: "Pago contra reembolso con resumen de pedido"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Cash on delivery with order summary en MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-delivery-with-order-summary.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/cash-on-delivery-with-order-summary/)
>
> ---


# Pago contra reembolso con resumen de pedido

## 1. Requisitos y compatibilidad

-   **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilidad con PHP**: PHP 5.6 - 8.5
-   **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser requeridas por PrestaShop y son suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde se establece el comportamiento central y las tarifas para su método de pago contra reembolso.

-   **Ubicación del menú:** Back Office > Módulos > Gestor de módulos > Busque "Pago contra reembolso con resumen de pedido" > Haga clic en "Configurar".

#### Configuración general

1.  **Desactivar COD para transportistas específicos**
    -   **Qué hace este ajuste:** Le permite evitar que la opción de pago contra reembolso esté disponible si un cliente elige ciertos transportistas.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (marcado para transportistas específicos):* Si un cliente selecciona uno de los transportistas elegidos durante el proceso de pago, la opción de pago contra reembolso no aparecerá.
        -   *Cuando está deshabilitado (desmarcado para todos los transportistas):* El pago contra reembolso estará disponible independientemente del transportista elegido (a menos que se apliquen otras restricciones).
    -   **Valor recomendado:** Depende de su logística de envío. Si algunos transportistas no admiten COD o cobran tarifas excesivas, habilítelo.
    -   **Escenario / ejemplo de comerciante:** Utiliza un servicio de mensajería específico que no gestiona pagos en efectivo. Marcaría ese transportista en esta lista para deshabilitar el COD para ellos.

2.  **¿Cómo incluir la tarifa?**
    -   **Qué hace este ajuste:** Determina cómo se calcula y aplica la tarifa de pago contra reembolso al pedido.
    -   **Efecto de cambiar este ajuste:**
        -   *Incluir en los gastos de envío:* La tarifa de COD se añadirá directamente al costo de envío que se muestra al cliente. Esto puede simplificar la visualización del proceso de pago, pero podría ocultar el cargo de COD por separado.
        -   *Incluir como producto separado:* La tarifa de COD aparecerá como un elemento de línea distinto en el carrito y el resumen del pedido, a menudo etiquetado como "Tarifa de pago contra reembolso" o similar. Esto proporciona la máxima transparencia.
    -   **Valor recomendado:** "Incluir como producto separado" para mayor claridad y cumplimiento legal, especialmente en la UE.
    -   **Escenario / ejemplo de comerciante:** Para mostrar claramente a los clientes el costo exacto de usar COD, seleccionaría "Incluir como producto separado".

3.  **Estado del pedido después de la compra con el módulo COD**
    -   **Qué hace este ajuste:** Establece el estado inicial de un pedido realizado utilizando el método de pago contra reembolso.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Pago aceptado":* El pedido se marcará inmediatamente como pagado, lo que podría ser engañoso ya que aún no se ha cobrado el efectivo.
        -   *Cuando se establece en "Esperando validación de pago contra reembolso" (o similar):* El pedido estará en un estado pendiente, lo que indica que se espera el pago en el momento de la entrega. Esto es generalmente más seguro y preciso.
    -   **Valor recomendado:** Un estado pendiente como "Esperando validación de pago contra reembolso" o "Pago pendiente" para reflejar con precisión el estado del pago.
    -   **Escenario / ejemplo de comerciante:** Para evitar enviar prematuramente un pedido que no se ha pagado, lo establecería en un estado pendiente.

4.  **Mostrar resumen adicional antes de la confirmación**
    -   **Qué hace este ajuste:** Controla si el módulo muestra la página de resumen de pedido dedicada previa a la confirmación. Esta es la característica principal de cumplimiento del módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Después de seleccionar COD, los clientes verán un resumen detallado de su pedido, incluidos todos los costos, antes de que puedan hacer clic en el botón final "Confirmar pedido".
        -   *Cuando está deshabilitado:* El módulo omitirá esta página de resumen, y los clientes procederán directamente a la confirmación de pedido estándar de PrestaShop (lo que podría no ser legalmente compatible en algunas regiones).
    -   **Valor recomendado:** **Habilitado**. Esta es una característica clave para el cumplimiento legal y la confianza del cliente.
    -   **Escenario / ejemplo de comerciante:** Para cumplir con las leyes de consumo de la UE que exigen un resumen claro del pedido antes de la confirmación final, **debe** habilitar este ajuste.

#### Restricciones de valor del carrito

5.  **Valor mínimo total del carrito**
    -   **Qué hace este ajuste:** Establece el valor total mínimo que debe tener un pedido para que la opción de pago contra reembolso esté disponible.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en un valor (por ejemplo, 10.00):* Si el total del carrito del cliente está por debajo de esta cantidad, el pago contra reembolso no se ofrecerá como opción de pago.
        -   *Cuando se deja vacío o se establece en 0:* No habrá restricción de valor mínimo del carrito para COD.
    -   **Valor recomendado:** Establezca un mínimo razonable si el costo operativo de procesar pedidos pequeños de COD es demasiado alto. De lo contrario, déjelo vacío.
    -   **Escenario / ejemplo de comerciante:** Si el costo de procesar un pedido de COD (tarifas de mensajería, trabajo administrativo) es de 5 €, podría establecer un valor mínimo de carrito de 10 € para garantizar la rentabilidad.

6.  **Valor máximo total del carrito**
    -   **Qué hace este ajuste:** Establece el valor total máximo que puede tener un pedido para que la opción de pago contra reembolso esté disponible.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en un valor (por ejemplo, 500.00):* Si el total del carrito del cliente excede esta cantidad, el pago contra reembolso no se ofrecerá como opción de pago.
        -   *Cuando se deja vacío o se establece en 0:* No habrá restricción de valor máximo del carrito para COD.
    -   **Valor recomendado:** Establezca un máximo si desea limitar su riesgo para pedidos de muy alto valor que podrían estar sujetos a fraude o falta de cobro. De lo contrario, déjelo vacío.
    -   **Escenario / ejemplo de comerciante:** Para mitigar el riesgo de impago de pedidos muy caros, podría establecer un valor máximo de carrito de 200 € para COD.

#### Configuración de la tarifa de pago contra reembolso

7.  **Tipo de tarifa COD (Porcentaje o Cantidad)**
    -   **Qué hace este ajuste:** Determina si la tarifa de COD es una cantidad fija o un porcentaje del total del pedido.
    -   **Efecto de cambiar este ajuste:**
        -   *Porcentaje:* La tarifa se calculará como un porcentaje del total del pedido.
        -   *Cantidad:* La tarifa será un valor monetario fijo.
    -   **Valor recomendado:** Elija según su estructura de costos. Si sus costos aumentan con el valor del pedido, use el porcentaje. Si es una tarifa de manejo fija, use la cantidad.
    -   **Escenario / ejemplo de comerciante:** Si su banco cobra un porcentaje del valor de la transacción por el manejo de efectivo, elegiría "Porcentaje". Si su mensajero cobra una tarifa fija por COD, elegiría "Cantidad".

8.  **Valor de la tarifa COD (Porcentaje)** (Aparece si se selecciona "Porcentaje" arriba)
    -   **Qué hace este ajuste:** El valor porcentual que se cobrará como tarifa de COD.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en 5:* La tarifa de COD será el 5% del total del pedido.
    -   **Valor recomendado:** Un porcentaje que cubra sus costos sin disuadir a los clientes.
    -   **Escenario / ejemplo de comerciante:** Para cubrir un cargo bancario del 2% por depósitos en efectivo, podría establecerlo en "2".

9.  **Valor de la tarifa COD (Cantidad)** (Aparece si se selecciona "Cantidad" arriba)
    -   **Qué hace este ajuste:** El valor monetario fijo que se cobrará como tarifa de COD.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en 2.50:* La tarifa de COD será de 2.50 € (o su moneda predeterminada) independientemente del total del pedido.
    -   **Valor recomendado:** Una cantidad fija que cubra sus costos de manejo fijos.
    -   **Escenario / ejemplo de comerciante:** Si su mensajero cobra 3 € fijos por el servicio de COD, lo establecería en "3".

10. **Tarifa mínima de COD**
    -   **Qué hace este ajuste:** Establece una cantidad mínima para la tarifa de COD, independientemente del cálculo del porcentaje.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en 1.00 y el porcentaje calcula 0.50:* La tarifa será 1.00.
        -   *Cuando se establece en 1.00 y el porcentaje calcula 2.00:* La tarifa será 2.00.
    -   **Valor recomendado:** Útil si tiene un costo mínimo asociado con el COD incluso para pedidos pequeños.
    -   **Escenario / ejemplo de comerciante:** Si el 5% de un pedido de 10 € es solo 0.50 €, pero su costo mínimo de manejo es de 1 €, lo establecería en "1.00".

11. **Tarifa máxima de COD**
    -   **Qué hace este ajuste:** Establece una cantidad máxima para la tarifa de COD, independientemente del cálculo del porcentaje.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en 10.00 y el porcentaje calcula 15.00:* La tarifa será 10.00.
        -   *Cuando se establece en 10.00 y el porcentaje calcula 5.00:* La tarifa será 5.00.
    -   **Valor recomendado:** Útil para evitar que la tarifa de COD sea excesivamente alta en pedidos muy grandes.
    -   **Escenario / ejemplo de comerciante:** Para asegurarse de que la tarifa de COD no sea prohibitiva para pedidos grandes, podría limitarla a 15 €.

12. **Aplicar impuestos a la tarifa de COD**
    -   **Qué hace este ajuste:** Determina si la tarifa de pago contra reembolso está sujeta a impuestos sobre las ventas.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Podrá seleccionar una regla de impuestos para aplicar a la tarifa de COD.
        -   *Cuando está deshabilitado:* La tarifa de COD estará exenta de impuestos.
    -   **Valor recomendado:** Consulte sus regulaciones fiscales locales. En muchas regiones, las tarifas de procesamiento de pagos son gravables.
    -   **Escenario / ejemplo de comerciante:** Si las leyes fiscales de su país le exigen cobrar el IVA sobre las tarifas de los servicios de pago, habilitaría esto y seleccionaría la regla fiscal adecuada.

13. **Regla fiscal para la tarifa de COD** (Aparece si "Aplicar impuestos a la tarifa de COD" está habilitado)
    -   **Qué hace este ajuste:** Le permite seleccionar una regla fiscal existente de su tienda PrestaShop para aplicar a la tarifa de COD.
    -   **Efecto de cambiar este ajuste:** La tasa de impuestos seleccionada se aplicará a la tarifa de COD calculada.
    -   **Valor recomendado:** Seleccione la regla fiscal que corresponda a las tarifas de procesamiento de pagos en su jurisdicción.
    -   **Escenario / ejemplo de comerciante:** Si tiene una regla fiscal "IVA 20%", la seleccionaría aquí para aplicar el 20% de IVA a la tarifa de COD.

#### Configuración avanzada de visualización

14. **Selector CSS para el total del carrito**
    -   **Qué hace este ajuste:** Le permite especificar el selector CSS para el elemento que muestra el valor total del carrito en su página de pago. Esto ayuda al módulo a actualizar con precisión el total cuando se aplica una tarifa de COD.
    -   **Efecto de cambiar este ajuste:** Si se configura correctamente, el módulo puede actualizar dinámicamente el total en la página de pago para incluir la tarifa de COD. Si es incorrecto, el total podría no actualizarse, lo que generaría confusión.
    -   **Valor recomendado:** Déjelo vacío a menos que experimente problemas de visualización con el total que no se actualiza. Si es necesario, consulte al desarrollador de su tema o use las herramientas de desarrollo del navegador para encontrar el selector correcto (por ejemplo, `.cart-total-value`).
    -   **Escenario / ejemplo de comerciante:** Si su tema utiliza una clase personalizada como `.mytheme-total-price` para el total del carrito, la introduciría aquí.

15. **Selector CSS para el subtotal del carrito**
    -   **Qué hace este ajuste:** Similar al total del carrito, esto especifica el selector CSS para el subtotal del carrito.
    -   **Efecto de cambiar este ajuste:** Ayuda al módulo a identificar y, potencialmente, actualizar correctamente la visualización del subtotal.
    -   **Valor recomendado:** Déjelo vacío a menos que ocurran problemas de visualización.
    -   **Escenario / ejemplo de comerciante:** Si su tema tiene un elemento específico para el subtotal, es posible que deba introducir su selector aquí.

16. **Selector CSS para el envío del carrito**
    -   **Qué hace este ajuste:** Similar al total del carrito, esto especifica el selector CSS para la visualización del costo de envío.
    -   **Efecto de cambiar este ajuste:** Ayuda al módulo a identificar y, potencialmente, actualizar correctamente la visualización del costo de envío, especialmente si la tarifa de COD se incluye en el envío.
    -   **Valor recomendado:** Déjelo vacío a menos que ocurran problemas de visualización.
    -   **Escenario / ejemplo de comerciante:** Si su tema tiene un elemento específico para el costo de envío, es posible que deba introducir su selector aquí.

17. **Logotipo de COD**
    -   **Qué hace este ajuste:** Le permite subir un logotipo personalizado que se mostrará junto a la opción de pago contra reembolso durante el proceso de pago.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se sube:* Aparecerá un icono o logotipo visual, haciendo que la opción de COD sea más prominente y visualmente atractiva.
        -   *Cuando está vacío:* No se mostrará ningún logotipo personalizado.
    -   **Valor recomendado:** Suba un logotipo pequeño y claro (por ejemplo, un icono de efectivo) para mejorar la experiencia del usuario.
    -   **Escenario / ejemplo de comerciante:** Para que la opción de COD destaque, podría subir una pequeña imagen de billetes o monedas.

#### Configuración de análisis (Uso interno del módulo)

Estos ajustes son típicamente para el análisis interno del módulo y generalmente no requieren la intervención del comerciante.

18. **CODPRO_ANALYTICS_DEFAULT_CHART, CODPRO_ANALYTICS_PERIOD, CODPRO_ANALYTICS_IMPACT_DAYS, CODPRO_ANALYTICS_CHART_WEEKS, CODPRO_ANALYTICS_CHART_MONTHS**
    -   **Qué hacen estos ajustes:** Estas son claves de configuración internas utilizadas por el módulo para posibles futuras características de análisis o visualizaciones de paneles dentro de la propia administración del módulo. Controlan cómo se podrían recopilar o mostrar los datos para el monitoreo del rendimiento.
    -   **Efecto de cambiar estos ajustes:** Es poco probable que tenga un impacto directo e inmediato en la experiencia del cliente en el front-office. Afecta principalmente a los posibles informes del back-office.
    -   **Valor recomendado:** Déjelos en sus valores predeterminados.
    -   **Escenario / ejemplo de comerciante:** Estos no suelen ser ajustados por los comerciantes.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

El módulo proporciona dos pantallas de administración adicionales para un control más granular sobre las tarifas de COD, especialmente útil para estrategias complejas de envío y precios.

#### 2.2.1 AdminCodProCarriersFeesController: Tarifas de COD específicas del transportista

-   **Nombre de la pantalla y ubicación del menú:** Back Office > Módulos > Gestor de módulos > Busque "Pago contra reembolso con resumen de pedido" > Haga clic en "Configurar" > Busque una pestaña o enlace etiquetado como "Tarifas de transportista" o similar (esto podría estar integrado en la configuración principal o en un elemento de menú separado según la versión de PrestaShop).
-   **Acciones y ajustes disponibles:** Esta pantalla suele presentar una cuadrícula o tabla donde puede definir diferentes tarifas de pago contra reembolso según el transportista de envío seleccionado. Puede agregar, editar o eliminar estas reglas de tarifas específicas del transportista.
    -   **Selección de transportista:** Elija un transportista de envío específico.
    -   **Tipo de tarifa:** Seleccione si la tarifa es una cantidad fija o un porcentaje.
    -   **Valor de la tarifa:** Introduzca la cantidad o el porcentaje.
    -   **Regla fiscal:** Aplique una regla fiscal específica a la tarifa de COD de este transportista.
-   **Efecto de los cambios:** Cuando un cliente selecciona un transportista para el que ha definido una tarifa de COD específica aquí, esa tarifa anulará la tarifa de COD general establecida en la configuración principal del módulo. Esto permite una fijación de precios altamente personalizada.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Acceda a esta pantalla si necesita cobrar diferentes tarifas de COD según el mensajero que entregue el paquete.
    2.  Haga clic en "Agregar nueva tarifa de transportista" (o botón similar).
    3.  Seleccione el transportista, defina el tipo de tarifa (cantidad/porcentaje), el valor y la regla fiscal.
    4.  Guarde sus cambios.
    5.  Revise la lista para asegurarse de que todas las tarifas específicas del transportista estén configuradas correctamente.
-   **Escenario / ejemplo de comerciante:** Su servicio postal nacional cobra una tarifa fija de 2 € por COD, pero un mensajero exprés privado cobra el 3% del valor del pedido. Utilizaría esta pantalla para establecer estas tarifas distintas para cada transportista.

#### 2.2.2 AdminCodProCarriersRangeFeesController: Tarifas de COD específicas del transportista y del rango total

-   **Nombre de la pantalla y ubicación del menú:** Back Office > Módulos > Gestor de módulos > Busque "Pago contra reembolso con resumen de pedido" > Haga clic en "Configurar" > Busque una pestaña o enlace etiquetado como "Tarifas por rango" o similar.
-   **Acciones y ajustes disponibles:** Esta pantalla proporciona un nivel aún más avanzado de control de tarifas. Puede definir tarifas de COD que varían no solo por transportista, sino también por el *valor total del carrito del cliente*. Esto a menudo se presenta como una cuadrícula donde se definen rangos (por ejemplo, "Total del pedido de 0 € a 50 €", "Total del pedido de 50 € a 100 €").
    -   **Selección de transportista:** Elija un transportista de envío específico.
    -   **Total mínimo del pedido:** El límite inferior del rango de valor del pedido.
    -   **Total máximo del pedido:** El límite superior del rango de valor del pedido.
    -   **Tipo de tarifa:** Cantidad fija o porcentaje.
    -   **Valor de la tarifa:** La cantidad o el porcentaje para este transportista y rango de total de pedido específicos.
    -   **Regla fiscal:** Aplique una regla fiscal específica.
-   **Efecto de los cambios:** Estas tarifas basadas en rangos tienen prioridad sobre la tarifa de COD general y las tarifas simples específicas del transportista. Permiten estrategias de precios altamente dinámicas.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Utilice esta pantalla para las estructuras de tarifas de COD más complejas.
    2.  Haga clic en "Agregar nueva tarifa por rango" (o similar).
    3.  Seleccione el transportista, defina el total mínimo y máximo del pedido para esta regla.
    4.  Especifique el tipo de tarifa, el valor y la regla fiscal para este rango en particular.
    5.  Guarde y repita para todos los rangos y transportistas necesarios.
-   **Escenario / ejemplo de comerciante:** Para un transportista específico, podría cobrar una tarifa de COD de 3 € para pedidos inferiores a 50 €, pero una tarifa del 2% para pedidos entre 50 € y 200 €, y una tarifa fija de 5 € para pedidos superiores a 200 €. Esta pantalla le permite configurar dicha fijación de precios por niveles.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
|---|---|---|---|
| **Configuración del módulo** | Desactivar COD para transportistas específicos | No (todos habilitados) | Restringe la disponibilidad de COD por transportista de envío elegido. |
| | ¿Cómo incluir la tarifa? | Incluir como producto separado | Determina cómo aparece la tarifa de COD en el carrito/pedido. "Producto separado" para mayor claridad. |
| | Estado del pedido después de la compra con el módulo COD | Esperando validación de COD | Establece el estado inicial del pedido; "Esperando validación de COD" se recomienda para mayor precisión. |
| | Mostrar resumen adicional antes de la confirmación | Habilitado | **CRÍTICO:** Muestra el resumen legal previo a la confirmación. **Habilitado** para cumplimiento. |
| | Valor mínimo total del carrito | Vacío / 0 | Valor mínimo del pedido para COD. Establecer si los pedidos pequeños no son rentables. |
| | Valor máximo total del carrito | Vacío / 0 | Valor máximo del pedido para COD. Establecer para mitigar el riesgo en pedidos grandes. |
| | Tipo de tarifa COD | Cantidad | Elija si la tarifa es fija o basada en porcentaje. |
| | Valor de la tarifa COD (Porcentaje) | 0 | Porcentaje del total del pedido para la tarifa de COD. |
| | Valor de la tarifa COD (Cantidad) | 0 | Cantidad monetaria fija para la tarifa de COD. |
| | Tarifa mínima de COD | 0 | Asegura que se cobre una tarifa mínima, incluso si el porcentaje es bajo. |
| | Tarifa máxima de COD | 0 | Limita la tarifa de COD para evitar que sea demasiado alta. |
| | Aplicar impuestos a la tarifa de COD | No | Determina si se aplican impuestos a la tarifa de COD. Consulte las leyes fiscales locales. |
| | Regla fiscal para la tarifa de COD | (Ninguna) | Selecciona la regla fiscal si "Aplicar impuestos" está habilitado. |
| | Selector CSS para el total del carrito | Vacío | Avanzado: Selector CSS para la visualización del total del carrito. Dejar vacío a menos que haya problemas. |
| | Selector CSS para el subtotal del carrito | Vacío | Avanzado: Selector CSS para la visualización del subtotal del carrito. Dejar vacío a menos que haya problemas. |
| | Selector CSS para el envío del carrito | Vacío | Avanzado: Selector CSS para la visualización del costo de envío. Dejar vacío a menos que haya problemas. |
| | Logotipo de COD | Vacío | Suba un logotipo personalizado para la opción de pago contra reembolso. |
| **AdminCodProCarriersFees** | Tarifas específicas del transportista | N/A | Define tarifas de COD que varían según el transportista de envío. |
| **AdminCodProCarriersRangeFees** | Tarifas específicas del transportista y del rango | N/A | Define tarifas de COD que varían según el transportista Y el rango total del pedido. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: La opción de COD no aparece para los clientes.**
R1: Compruebe lo siguiente:
    *   **Módulo habilitado:** ¿Está habilitado el módulo "Pago contra reembolso con resumen de pedido" en **Módulos > Gestor de módulos**?
    *   **Restricciones de pago:** Vaya a **Parámetros de la tienda > Configuración de pedidos > Pagos** (o **Pago > Preferencias** en versiones anteriores). Asegúrese de que "Pago contra reembolso con resumen de pedido" no esté restringido por grupo de clientes, moneda o país.
    *   **Restricciones de transportista:** En la configuración del módulo, marque "Desactivar COD para transportistas específicos". ¿Está marcado accidentalmente el transportista elegido por el cliente?
    *   **Restricciones de valor del carrito:** Compruebe "Valor mínimo total del carrito" y "Valor máximo total del carrito" en la configuración del módulo. ¿El carrito del cliente se encuentra dentro de estos límites?
    *   **Zonas geográficas:** Asegúrese de que el módulo esté habilitado para el país del cliente en **Parámetros de la tienda > Configuración de pedidos > Pagos > Restricciones por zona/país**.

**P2: La tarifa de COD no aparece o no se calcula correctamente.**
R2:
    *   **Configuración de tarifas:** Vuelva a verificar la configuración de "Tipo de tarifa COD" (Porcentaje/Cantidad) y "Valor de la tarifa COD" en la configuración principal del módulo.
    *   **Tarifas de transportista/rango:** Si está utilizando `AdminCodProCarriersFees` o `AdminCodProCarriersRangeFees`, asegúrese de que las reglas estén definidas correctamente para el transportista y el total del pedido específicos. Estas reglas específicas anulan la configuración general.
    *   **Reglas fiscales:** Si "Aplicar impuestos a la tarifa de COD" está habilitado, asegúrese de que se seleccione una regla fiscal válida.
    *   **Caché:** Borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**). A veces, los datos antiguos pueden impedir que las tarifas se actualicen.

**P3: La página de resumen previa a la confirmación no se muestra, o el pedido va directamente a la confirmación.**
R3:
    *   **Ajuste "Mostrar resumen adicional antes de la confirmación":** En la configuración principal del módulo, asegúrese de que este ajuste esté **Habilitado**. Esto es crucial para que aparezca la página de resumen.
    *   **Compatibilidad del tema:** Si bien el módulo está diseñado para ser compatible, algunos temas muy personalizados podrían interferir. Si la página de resumen aún no aparece, cambie temporalmente al tema predeterminado de PrestaShop para descartar un conflicto de tema. Si funciona en el tema predeterminado, póngase en contacto con el desarrollador de su tema o con un experto en PrestaShop.

**P4: La tarifa de COD no aparece en la factura en PDF.**
R4:
    *   **Módulo activo:** Asegúrese de que el módulo esté habilitado.
    *   **Generación de facturas:** Vuelva a generar la factura en PDF para un pedido realizado con COD *después* de que el módulo se configurara correctamente. Las facturas antiguas podrían no reflejar la nueva configuración.
    *   **Versión de PrestaShop:** Asegúrese de que su versión de PrestaShop sea totalmente compatible. Si bien el módulo busca una amplia compatibilidad, las versiones muy antiguas o muy nuevas podrían tener pequeñas peculiaridades de visualización.

**P5: ¿Cómo cambio el texto "Pago contra reembolso" o la descripción de la tarifa?**
R5:
    *   **Traducciones:** Vaya a **Internacional > Traducciones**. Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Pago contra reembolso con resumen de pedido". Luego podrá encontrar y modificar todas las cadenas traducibles utilizadas por el módulo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura
El módulo "Pago contra reembolso con resumen de pedido" (`codpro`) es un módulo de pago estándar de PrestaShop que sigue el patrón MVC (Modelo-Vista-Controlador). Extiende `PaymentModule` y aprovecha varios hooks de PrestaShop para inyectar su opción de pago, mostrar el resumen previo a la confirmación y gestionar el estado del pedido y las tarifas. Utiliza valores de configuración almacenados en `ps_configuration` para sus ajustes e incluye controladores de administración personalizados para la gestión avanzada de tarifas. El módulo calcula y muestra dinámicamente las tarifas de COD, integrándolas en el carrito y los totales del pedido.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office
-   `controllers/front/index.php`
    *   **Nombre de la clase:** `CodProIndexModuleFrontController` (probablemente, según la convención de nombres de archivos)
    *   **Clase padre:** `ModuleFrontController`
    *   **Responsabilidad:** Este controlador podría ser un marcador de posición o manejar el enrutamiento inicial para los componentes de front-office del módulo. Dado el controlador `validation.php`, `index.php` podría no tener una ruta directa orientada al usuario, pero podría usarse para la lógica interna del módulo o redirecciones.
-   `controllers/front/validation.php`
    *   **Nombre de la clase:** `CodProValidationModuleFrontController`
    *   **Clase padre:** `ModuleFrontController`
    *   **Responsabilidad:** Este es el controlador crítico para procesar la confirmación final del pedido. Recibe los datos POST de la página de resumen previa a la confirmación, valida el pedido, crea el pedido en PrestaShop y redirige al cliente a la página de confirmación del pedido (`paymentReturn`). Maneja la lógica para aplicar la tarifa de COD al pedido.

#### Controladores de administración de Back-Office
-   `controllers/admin/AdminCodProCarriersFees.php`
    *   **Nombre de la clase:** `AdminCodProCarriersFeesController`
    *   **Clase padre:** `ModuleAdminController`
    *   **Nombre de la pestaña:** Probablemente una subpestaña bajo la configuración principal del módulo o una entrada de menú personalizada.
    *   **Entidad gestionada:** Gestiona las entradas de configuración relacionadas con las tarifas de COD específicas del transportista.
    *   **Responsabilidad:** Proporciona la interfaz (un `HelperList` o `HelperForm` basado en patrones de `AdminController`) para que los administradores definan, editen y eliminen las tarifas de pago contra reembolso que son específicas de los transportistas de envío individuales. Maneja las operaciones CRUD para estas reglas de tarifas.
-   `controllers/admin/AdminCodProCarriersRangeFees.php`
    *   **Nombre de la clase:** `AdminCodProCarriersRangeFeesController`
    *   **Clase padre:** `ModuleAdminController`
    *   **Nombre de la pestaña:** Probablemente una subpestaña bajo la configuración principal del módulo.
    *   **Entidad gestionada:** Gestiona las entradas en la tabla `codprototal` (o similar, según las claves de configuración `CODPRO_MOD_MAXCART_V` y `CODPRO_MOD_MINCART_V`).
    *   **Responsabilidad:** Proporciona la interfaz para que los administradores definan, editen y eliminen las tarifas de pago contra reembolso que dependen tanto del transportista de envío seleccionado como del valor total del carrito del cliente (es decir, tarifas basadas en rangos). Maneja las operaciones CRUD para estas complejas reglas de tarifas.
-   `controllers/admin/index.php`
    *   **Nombre de la clase:** (No es una clase de controlador típica, generalmente una redirección o medida de seguridad)
    *   **Clase padre:** N/A
    *   **Responsabilidad:** A menudo, una medida de seguridad para evitar la lista directa de directorios o para redirigir a la configuración principal del módulo. Normalmente contiene un simple `header('Location: ../../index.php?controller=AdminModules&token=...')` o `die('Forbidden');`.

### 4.3 Clases y modelos principales (`classes/`)
La información del módulo proporcionada indica que no hay clases personalizadas en el directorio `classes/`. Esto sugiere que la lógica central del módulo, el manejo de datos y, potencialmente, las definiciones de `ObjectModel` (si se utilizan tablas personalizadas más allá de `ps_configuration`) están encapsuladas directamente dentro del archivo principal `codpro.php` o se manejan a través de `ObjectModel`s estándar de PrestaShop como `Order` y `Cart`.

### 4.4 Activos JavaScript (`views/js/`)

-   `codpro/views/js/adminCodProCarriersFees.js`
    *   **Alcance:** Back-office (AdminCodProCarriersFeesController)
    *   **Responsabilidad:** Probablemente maneja las interacciones dinámicas en la página de administración de tarifas específicas del transportista. Esto podría incluir llamadas AJAX para agregar/editar tarifas, validación de formularios o actualización de la visualización de la lista de tarifas.
-   `codpro/views/js/adminCodProDashboard.js`
    *   **Alcance:** Back-office (potencialmente la página de configuración principal del módulo si incluye análisis)
    *   **Responsabilidad:** Dadas las claves de configuración `CODPRO_ANALYTICS_`, este script es probablemente responsable de renderizar gráficos, diagramas u otros datos analíticos relacionados con los pedidos de COD dentro de la interfaz de back-office del módulo. Podría usar una biblioteca de gráficos (por ejemplo, Chart.js) y realizar solicitudes AJAX para obtener datos.
-   `codpro/views/js/codpro-checkout.js`
    *   **Alcance:** Front-office (Página de pago)
    *   **Responsabilidad:** Este es un script crucial para la experiencia del front-office. Escucha los cambios en el proceso de pago (por ejemplo, seleccionar COD como método de pago, cambiar el transportista de envío, actualizar la cantidad del carrito). Actualiza dinámicamente las visualizaciones del total del carrito, el subtotal y el costo de envío (utilizando los selectores CSS definidos en la configuración del módulo) para reflejar la tarifa de COD calculada. También podría manejar la redirección a la página de resumen previa a la confirmación.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `codpro/views/css/admin_codpro.css`
    *   **Alcance:** Back-office (páginas de administración relacionadas con el módulo)
    *   **Responsabilidad:** Proporciona estilos para los formularios de configuración del módulo, listas y, potencialmente, cualquier elemento de panel personalizado dentro del back office de PrestaShop. Garantiza una interfaz de administración consistente y fácil de usar.
    *   **Selectores de clase CSS clave:** Probablemente apunta a elementos dentro de las plantillas `HelperForm` o `HelperList` del módulo, o elementos personalizados específicos de las vistas de administración del módulo.
-   `codpro/views/css/codpro.css`
    *   **Alcance:** Front-office (página de pago, resumen previo a la confirmación, detalles del pedido)
    *   **Responsabilidad:** Estiliza la visualización de la opción de pago contra reembolso, la página de resumen previa a la confirmación y la visualización de la tarifa de COD en las páginas de detalles del pedido y las facturas. Asegura que los elementos del módulo se integren visualmente con el tema de la tienda.
    *   **Selectores de clase CSS clave:** Apuntará a elementos como el bloque de opción de pago de COD, la tabla de resumen, los elementos de línea de tarifas y, potencialmente, cualquier alerta o mensaje personalizado introducido por el módulo. Los desarrolladores pueden anularlos en el `custom.css` de su tema o utilizando selectores más específicos.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)
-   `codpro/views/templates/hook/confirmation.tpl`
    *   **Hook:** `displayPaymentReturn`
    *   **Salida:** Contenido que se muestra en la página de confirmación del pedido después de un pedido de COD exitoso. Podría incluir un mensaje que recuerde al cliente el pago en efectivo en el momento de la entrega.
-   `codpro/views/templates/hook/displayAdminOrder16.tpl`
    *   **Hook:** `displayAdminOrder` (para PrestaShop 1.6.x)
    *   **Salida:** Agrega información específica relacionada con el pago de COD (por ejemplo, detalles de la tarifa) a la página de vista del pedido en el back office de PrestaShop 1.6.
-   `codpro/views/templates/hook/displayAdminOrder17.tpl`
    *   **Hook:** `displayAdminOrder` (para PrestaShop 1.7.x, 8.x, 9.x)
    *   **Salida:** Similar a `displayAdminOrder16.tpl`, pero adaptado para la vista de pedidos del back office de PrestaShop 1.7+, mostrando los detalles de pago de COD.
-   `codpro/views/templates/hook/displayOrderDetail.tpl`
    *   **Hook:** `displayOrderDetail`
    *   **Salida:** Muestra información específica de COD (por ejemplo, el desglose de la tarifa) en la página de detalles del pedido del cliente en el front office.
-   `codpro/views/templates/hook/payment.tpl`
    *   **Hook:** `paymentOptions` o `displayPaymentOptions`
    *   **Salida:** Renderiza el bloque de opción de pago "Pago contra reembolso" en la página de pago, incluyendo el logotipo del módulo y cualquier tarifa mostrada.
-   `codpro/views/templates/hook/pdf.tpl`
    *   **Hook:** `displayPDFInvoice`
    *   **Salida:** Inyecta la tarifa de pago contra reembolso como un elemento de línea o resumen en las facturas en PDF generadas.

#### Plantillas de Front-office (`views/templates/front/`)
-   `codpro/views/templates/front/validation.tpl`
    *   **Salida:** Esta es la plantilla para la crucial página de resumen del pedido previa a la confirmación. Muestra el resumen completo del carrito, la dirección de envío, los costos totales (incluida la tarifa de COD) y el botón final "Confirmar pedido". Esta plantilla es renderizada por el controlador de front `validation.php`.

### 4.7 Esquema de la base de datos y mapa de Hooks

#### Tablas de la base de datos
El módulo utiliza principalmente la tabla estándar `ps_configuration` para almacenar sus ajustes (por ejemplo, `CODPRO_MOD_MAXCART`, `CODPRO_FEEPAY`, `CODPRO_CHARGEP_V`, etc.).

Según el `AdminCodProCarriersRangeFeesController` que gestiona la entidad `codprototal`, es muy probable que el módulo cree una tabla de base de datos personalizada, probablemente llamada `ps_codprototal` (o similar, siguiendo la convención de prefijo `ps_` de PrestaShop).
-   **`ps_codprototal` (Tabla probable):**
    *   **Propósito:** Almacena las reglas de tarifas de COD basadas en rangos, vinculando transportistas, totales mínimos/máximos del carrito, cantidades/porcentajes de tarifas y reglas fiscales.
    *   **Campos probables:** `id_codprototal` (PK), `id_carrier`, `min_total`, `max_total`, `fee_type` (por ejemplo, 'amount', 'percentage'), `fee_value`, `id_tax_rule`.

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
|---|---|---|
| `displayHeader` | En la sección `<head>` de cada página. | Para incluir los activos CSS/JS del módulo (por ejemplo, `codpro-checkout.js`, `codpro.css`) en las páginas relevantes del front-office. |
| `paymentOptions` | Durante el proceso de pago, cuando se enumeran las opciones de pago. | Para inyectar la opción de pago "Pago contra reembolso" en la lista. |
| `displayPaymentOptions` | (Alias o alternativa a `paymentOptions` para algunas versiones) | Para inyectar la opción de pago "Pago contra reembolso" en la lista. |
| `paymentReturn` | En la página de confirmación del pedido después de un pedido exitoso. | Para mostrar un mensaje de confirmación específico para pedidos de COD. |
| `displayAdminOrder` | En la página de detalles del pedido en el back office de PrestaShop. | Para mostrar los detalles de la tarifa de COD y la información del método de pago al administrador. |
| `displayOrderDetail` | En la página de detalles del pedido del cliente en el front office. | Para mostrar los detalles de la tarifa de COD al cliente. |
| `displayPDFInvoice` | Cuando se genera una factura en PDF. | Para asegurar que la tarifa de COD se incluya y muestre correctamente en la factura. |
| `ActionAdminControllerSetMedia` | Cuando se inicializa un controlador de administración y se configuran sus activos multimedia. | Para incluir los activos CSS/JS específicos de administración del módulo (por ejemplo, `admin_codpro.css`, `adminCodProCarriersFees.js`, `adminCodProDashboard.js`). |

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial para desarrolladores, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Asegúrese de utilizar siempre la versión del módulo compatible con su instalación específica de PrestaShop.

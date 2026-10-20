---
title: "Pago en tienda al recoger (+tarifa) - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Pago en tienda al recoger (+tarifa) de MyPresta.eu."
sidebar:
  label: "Pago en tienda al recoger (+tarifa) - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Cash on pickup at store (+fee) en MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-pickup-at-store-fee.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/cash-on-pickup-at-store-fee/)
>
> ---


# Pago en tienda al recoger (+tarifa)

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias y generalmente están habilitadas por defecto en la mayoría de los entornos de alojamiento.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde establecerá todas las opciones para su método de pago "Pago en tienda al recoger".

#### **Configuración general**

- **Logotipo de pago**

  - **Qué hace este ajuste:** Le permite subir una imagen personalizada (logotipo) que se mostrará junto a la opción de pago "Pago en tienda al recoger" durante el proceso de compra. Esto ayuda a los clientes a identificar visualmente el método de pago.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se sube una imagen:* La imagen elegida aparecerá junto al nombre del método de pago en la página de selección de pago.
    - *Cuando no se sube ninguna imagen:* Se mostrará un logotipo predeterminado o ninguno, dependiendo de su tema.
  - **Valor recomendado:** Suba un logotipo claro y pequeño que represente "recogida" o "efectivo" para un mejor reconocimiento.
  - **Escenario / ejemplo de comerciante:** Podría subir un icono de una bolsa de la compra o de una fachada de tienda para que la opción de pago destaque.
- **Título del método de pago** (Clave de configuración: `COPPRO_TITLE`)

  - **Qué hace este ajuste:** Define el nombre del método de pago tal como aparece a los clientes durante el proceso de compra.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se cambia:* El nuevo título se mostrará en la página de selección de pago, la confirmación del pedido y las facturas.
  - **Valor recomendado:** "Pago en tienda al recoger" o "Pagar al recoger en tienda".
  - **Escenario / ejemplo de comerciante:** Si tiene un nombre de marca específico para su servicio de recogida, puede usarlo aquí, por ejemplo, "Recogida local de MiTienda".
- **Estado del pedido para nuevos pedidos** (Clave de configuración: `COPPRO_OS`)

  - **Qué hace este ajuste:** Selecciona el estado inicial que tendrá un pedido en su Back Office cuando un cliente elija "Pago en tienda al recoger".
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "Esperando pago en tienda al recoger":* Los nuevos pedidos se asignarán automáticamente a este estado, lo que le facilitará la identificación de los pedidos que deben prepararse para la recogida y el pago.
  - **Valor recomendado:** Cree un estado de pedido personalizado como "Esperando pago en tienda al recoger" o "Listo para recoger" para mayor claridad.
  - **Escenario / ejemplo de comerciante:** Podría establecerlo en "Esperando pago en tienda al recoger" para que su personal sepa que debe preparar los artículos pero no enviarlos.
- **Estado del pedido cuando se paga** (Clave de configuración: `COPPRO_OS_READY`)

  - **Qué hace este ajuste:** Selecciona el estado del pedido al que debe cambiarse un pedido una vez que el cliente ha pagado y recogido sus artículos en su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "Pago aceptado":* Una vez que actualice manualmente el pedido en el Back Office después de la recogida y el pago, pasará a este estado, marcándolo como completado.
  - **Valor recomendado:** "Pago aceptado" o "Entregado".
  - **Escenario / ejemplo de comerciante:** Después de que el cliente recoja y pague, cambiaría el estado del pedido a "Pago aceptado" para finalizar la transacción en su sistema.

#### **Restricciones de valor del carrito**

- **Valor mínimo total del carrito** (Clave de configuración: `COPPRO_MINCART`, `COPPRO_MINCART_V`)

  - **Qué hace este ajuste:** Le permite establecer un valor total mínimo para que un pedido sea elegible para "Pago en tienda al recoger". Si el total del carrito está por debajo de este valor, el método de pago no se mostrará.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un valor (por ejemplo, 10 €):* Los clientes con un total de carrito inferior a 10 € no verán "Pago en tienda al recoger" como opción.
    - *Cuando se deja vacío o 0:* No habrá restricción de valor mínimo del carrito.
  - **Valor recomendado:** Dejar vacío o 0 a menos que tenga razones operativas específicas para requerir un mínimo.
  - **Escenario / ejemplo de comerciante:** Podría establecer un mínimo de 5 € para evitar pedidos muy pequeños que no sean rentables para su personal procesar para la recogida.
- **Valor máximo total del carrito** (Clave de configuración: `COPPRO_MAXCART`, `COPPRO_MAXCART_V`)

  - **Qué hace este ajuste:** Le permite establecer un valor total máximo para que un pedido sea elegible para "Pago en tienda al recoger". Si el total del carrito excede este valor, el método de pago no se mostrará.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un valor (por ejemplo, 500 €):* Los clientes con un total de carrito superior a 500 € no verán "Pago en tienda al recoger" como opción.
    - *Cuando se deja vacío o 0:* No habrá restricción de valor máximo del carrito.
  - **Valor recomendado:** Dejar vacío o 0 a menos que tenga preocupaciones específicas sobre el manejo de pagos en efectivo muy grandes.
  - **Escenario / ejemplo de comerciante:** Podría establecer un máximo de 1000 € si no se siente cómodo con que el personal maneje grandes sumas de efectivo en el punto de recogida.

#### **Configuración de tarifa / descuento**

- **Aplicar descuento (no tarifa)** (Clave de configuración: `COPPRO_DISCOUNT`)

  - **Qué hace este ajuste:** Este es un interruptor. Si está habilitado, el módulo aplicará un *descuento* al total del pedido en lugar de una *tarifa* cuando se seleccione "Pago en tienda al recoger".
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El valor que establezca para "Valor de cargo porcentual" o "Valor de cargo fijo" se restará del total del pedido.
    - *Cuando está deshabilitado:* El valor que establezca se añadirá al total del pedido como una tarifa.
  - **Valor recomendado:** Deshabilitado (para aplicar una tarifa) si desea cubrir los costos operativos, o Habilitado (para aplicar un descuento) si desea incentivar las recogidas.
  - **Escenario / ejemplo de comerciante:** Podría habilitar esto y establecer un descuento del 5% para animar a los clientes a recoger sus pedidos, ahorrándole costos de envío.
- **Valor de la tarifa cerca del método de pago** (Clave de configuración: `COPPRO_FEEPAY`)

  - **Qué hace este ajuste:** Este es un interruptor. Si está habilitado, el importe de la tarifa o el descuento se mostrará directamente junto al nombre del método de pago en la página de pago.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes verán "Pago en tienda al recoger (+ X,XX € de tarifa)" o "Pago en tienda al recoger (- X,XX € de descuento)".
    - *Cuando está deshabilitado:* Solo se mostrará el nombre del método de pago, y la tarifa/descuento se aplicará al total del carrito sin mención explícita junto al método.
  - **Valor recomendado:** Habilitado, para mayor transparencia con sus clientes.
  - **Escenario / ejemplo de comerciante:** Desea que los clientes sean plenamente conscientes de cualquier costo o ahorro adicional por adelantado, por lo que habilita esto.
- **Cargo porcentual** (Clave de configuración: `COPPRO_CHARGEP`, `COPPRO_CHARGEP_V`)

  - **Qué hace este ajuste:** Le permite aplicar una tarifa o descuento basado en un porcentaje del total del pedido.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado y se introduce un valor (por ejemplo, 5):* Se añadirá/restará una tarifa del 5% (o descuento si "Aplicar descuento" está habilitado) del total del pedido.
    - *Cuando está deshabilitado:* No se aplicará ninguna tarifa/descuento basado en porcentaje.
  - **Valor recomendado:** Deshabilitado, a menos que desee específicamente un cargo basado en porcentaje. Si está habilitado, un valor entre 1-10% es común para tarifas, o 2-10% para descuentos.
  - **Escenario / ejemplo de comerciante:** Desea cobrar una tarifa del 3% para cubrir el costo de procesamiento de efectivo y manejo, por lo que habilita esto e introduce "3".
- **Cargo fijo** (Clave de configuración: `COPPRO_CHARGEA`, `COPPRO_CHARGEA_V`)

  - **Qué hace este ajuste:** Le permite aplicar una tarifa o descuento de cantidad fija al total del pedido.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado y se introduce un valor (por ejemplo, 2.50):* Se añadirá/restará una tarifa fija de 2,50 € (o descuento si "Aplicar descuento" está habilitado) del total del pedido.
    - *Cuando está deshabilitado:* No se aplicará ninguna tarifa/descuento de cantidad fija.
  - **Valor recomendado:** Habilitado, con una pequeña cantidad fija (por ejemplo, 1,00 € - 3,00 €) si desea una tarifa simple y consistente.
  - **Escenario / ejemplo de comerciante:** Desea cobrar una tarifa plana de 2 € para todos los pedidos de recogida, por lo que habilita esto e introduce "2.00".

#### **Configuración avanzada de visualización y compatibilidad**

- **Resumen del carrito** (Clave de configuración: `COPPRO_CARTPRESENTER`)

  - **Qué hace este ajuste:** Este es un interruptor que controla si la tarifa/descuento se muestra explícitamente en el bloque de resumen del carrito (por ejemplo, en la columna derecha o en la parte inferior de la página del carrito).
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* La tarifa/descuento se detallará en el resumen del carrito, mostrando cómo afecta al total.
    - *Cuando está deshabilitado:* La tarifa/descuento se aplicará al total pero podría no desglosarse explícitamente en el resumen del carrito antes del paso de pago.
  - **Valor recomendado:** Habilitado, para una transparencia total.
  - **Escenario / ejemplo de comerciante:** Desea que los clientes vean la línea de "Tarifa de recogida" en el resumen de su carrito antes incluso de llegar al paso de pago, por lo que habilita esto.
- **Resumen de la dirección** (Clave de configuración: `COPPRO_HOWFEE`)

  - **Qué hace este ajuste:** Este ajuste controla dónde se muestra la tarifa/descuento en la sección de resumen de la dirección del proceso de compra.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* La tarifa/descuento será visible en el resumen de la dirección, generalmente cerca del costo de envío.
    - *Cuando está deshabilitado:* La tarifa/descuento se aplicará pero no se mostrará explícitamente en el resumen de la dirección.
  - **Valor recomendado:** Habilitado, para consistencia y transparencia.
  - **Escenario / ejemplo de comerciante:** Desea que la tarifa sea visible en múltiples etapas del proceso de compra, incluido el resumen de la dirección, por lo que habilita esto.
- **Habilitado** (Clave de configuración: `COPPRO_EVENTLISTENER`)

  - **Qué hace este ajuste:** Este es un interruptor general para habilitar o deshabilitar la funcionalidad principal del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El método de pago "Pago en tienda al recoger" estará activo y disponible para los clientes.
    - *Cuando está deshabilitado:* El método de pago estará oculto e no disponible.
  - **Valor recomendado:** Habilitado, una vez que haya configurado todos los demás ajustes.
  - **Escenario / ejemplo de comerciante:** Ha terminado de configurar el módulo y está listo para ofrecer este método de pago, por lo que lo habilita.
- **Deshabilitado** (Clave de configuración: `PS_ONE_PAGE_CHECKOUT_ENABLED`)

  - **Qué hace este ajuste:** Este ajuste probablemente está relacionado con la compatibilidad con el proceso de compra de una sola página de PrestaShop. Podría ser un ajuste heredado o un indicador de visualización.
  - **Efecto de cambiar este ajuste:** Es probable que sea un indicador de solo lectura o un ajuste que generalmente debe dejarse en su valor predeterminado a menos que el soporte indique lo contrario.
  - **Valor recomendado:** Dejar como predeterminado.
  - **Escenario / ejemplo de comerciante:** No se espera interacción directa del comerciante.
- **Selectores CSS para elementos del carrito** (Claves de configuración: `COPPRO_CSS_CART_TOTAL`, `COPPRO_CSS_CART_SUBTOTAL`, `COPPRO_CSS_CART_SHIPPING`)

  - **Qué hacen estos ajustes:** Estos campos le permiten especificar los selectores CSS para los elementos de total del carrito, subtotal y costo de envío de su tema. Esto es crucial para que el módulo actualice correctamente estos valores cuando se aplica una tarifa/descuento, especialmente si su tema utiliza selectores no estándar.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se configura correctamente:* El módulo actualizará con precisión los totales del carrito, subtotales y costos de envío mostrados en la página de pago para reflejar la tarifa/descuento.
    - *Cuando se configura incorrectamente o se deja vacío:* Los totales del carrito podrían no actualizarse correctamente, lo que llevaría a confusión del cliente o precios mostrados incorrectos.
  - **Valor recomendado:** Dejar vacío inicialmente. Si nota que los totales del carrito no se actualizan correctamente después de seleccionar "Pago en tienda al recoger", es posible que deba consultar al desarrollador de su tema o a un webmaster para encontrar los selectores CSS correctos.
  - **Escenario / ejemplo de comerciante:** Después de instalar el módulo, nota que el precio total no cambia en la página de pago cuando se aplica la tarifa de recogida. Su webmaster inspeccionaría el código de su tema para encontrar los selectores CSS correctos (por ejemplo, `#cart-total-price`, `.product-total-price`) y los introduciría aquí.

#### **Reglas de exclusión**

- **Excluir productos** (Clave de configuración: `COPPRO_EXCL_PRODUCTS`)

  - **Qué hace este ajuste:** Le permite evitar que productos específicos se compren con el método de pago "Pago en tienda al recoger". Si algún producto excluido está en el carrito, este método de pago no estará disponible.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se seleccionan productos:* Si un cliente añade uno de estos productos a su carrito, la opción "Pago en tienda al recoger" desaparecerá de los métodos de pago.
    - *Cuando no se seleccionan productos:* Todos los productos son elegibles.
  - **Valor recomendado:** Dejar vacío a menos que tenga productos específicos que no puedan ser recogidos o pagados en efectivo.
  - **Escenario / ejemplo de comerciante:** Vende artículos de muy alto valor (por ejemplo, joyas caras) para los que prefiere aceptar solo pagos seguros en línea. Añadiría estos productos a la lista de exclusión.
- **Excluir categorías** (Clave de configuración: `COPPRO_EXCL_CAT`)

  - **Qué hace este ajuste:** Similar a la exclusión de productos, esto le permite evitar que categorías enteras de productos se compren con "Pago en tienda al recoger".
  - **Efecto de cambiar este ajuste:**
    - *Cuando se seleccionan categorías:* Si un cliente añade cualquier producto de estas categorías a su carrito, la opción "Pago en tienda al recoger" no estará disponible.
    - *Cuando no se seleccionan categorías:* Todas las categorías son elegibles.
  - **Valor recomendado:** Dejar vacío a menos que tenga categorías específicas que no sean adecuadas para la recogida.
  - **Escenario / ejemplo de comerciante:** Tiene una categoría de "Descargas digitales". Dado que estos artículos no requieren recogida física, excluiría esta categoría.
- **Habilitar exclusiones** (Clave de configuración: `COPPRO_EXCL_ENABLE`)

  - **Qué hace este ajuste:** Este es un interruptor maestro para habilitar o deshabilitar todas las reglas de exclusión de productos y categorías que haya configurado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Sus reglas de exclusión de productos y categorías estarán activas.
    - *Cuando está deshabilitado:* Todos los productos y categorías serán elegibles para "Pago en tienda al recoger", independientemente de lo que haya seleccionado en las listas de exclusión.
  - **Valor recomendado:** Habilitado, si ha definido alguna regla de exclusión.
  - **Escenario / ejemplo de comerciante:** Ha configurado exclusiones para ciertos productos y desea que estas reglas estén activas, por lo que habilita este interruptor.

#### **Análisis y configuración interna**

- **Configuración de análisis** (Claves de configuración: `COPPRO_ANALYTICS_DEFAULT_CHART`, `COPPRO_ANALYTICS_PERIOD`, `COPPRO_ANALYTICS_IMPACT_DAYS`, `COPPRO_ANALYTICS_CHART_WEEKS`, `COPPRO_ANALYTICS_CHART_MONTHS`, `COPPRO_ANALYTICS_CHART_YEARS`)

  - **Qué hacen estos ajustes:** Estos son ajustes internos relacionados con cualquier función de análisis o informes que el módulo pueda tener, lo que le permite configurar cómo se recopilan o muestran los datos para uso interno.
  - **Efecto de cambiar este ajuste:** Estos suelen afectar solo a las vistas de informes del Back Office, no a la experiencia del cliente en el front-office.
  - **Valor recomendado:** Dejar como predeterminado a menos que tenga necesidades de informes específicas.
  - **Escenario / ejemplo de comerciante:** No se espera interacción directa del comerciante para las operaciones diarias.
- **Fecha de cambio de tarifa / instantánea** (Claves de configuración: `COPPRO_FEE_CHANGE_DATE`, `COPPRO_FEE_CHANGE_SNAPSHOT`)

  - **Qué hacen estos ajustes:** Es probable que estos sean ajustes internos del módulo para rastrear cuándo se cambiaron por última vez las configuraciones de tarifas o para almacenar una instantánea de las configuraciones de tarifas anteriores. Esto suele ser para fines de auditoría o depuración.
  - **Efecto de cambiar este ajuste:** No hay un impacto directo en la experiencia del cliente.
  - **Valor recomendado:** Dejar como predeterminado.
  - **Escenario / ejemplo de comerciante:** No se espera interacción directa del comerciante.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

Este módulo no parece tener controladores de administración personalizados dedicados más allá de su página de configuración principal. Todos los ajustes se gestionan a través del método `getContent()` del archivo principal del módulo.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Logotipo de pago | Subir imagen relevante | Identificación visual del método de pago. |
| Configuración del módulo | Título del método de pago | "Pago en tienda al recoger" | Nombre mostrado a los clientes para la opción de pago. |
| Configuración del módulo | Estado del pedido para nuevos pedidos | Personalizado "Esperando pago en tienda al recoger" | Estado inicial para pedidos que utilizan este método. |
| Configuración del módulo | Estado del pedido cuando se paga | "Pago aceptado" / "Entregado" | Estado final después de que el cliente paga y recoge. |
| Configuración del módulo | Valor mínimo total del carrito | Vacío / 0 | Valor mínimo del pedido para que aparezca este método de pago. |
| Configuración del módulo | Valor máximo total del carrito | Vacío / 0 | Valor máximo del pedido para que aparezca este método de pago. |
| Configuración del módulo | Aplicar descuento (no tarifa) | Deshabilitado | Determina si se aplica un descuento o una tarifa. |
| Configuración del módulo | Valor de la tarifa cerca del método de pago | Habilitado | Muestra la tarifa/descuento junto al nombre del método de pago. |
| Configuración del módulo | Cargo porcentual | Deshabilitado | Aplica una tarifa/descuento basado en porcentaje. |
| Configuración del módulo | Valor de cargo porcentual | 0 | El valor porcentual para el cargo/descuento. |
| Configuración del módulo | Cargo fijo | Habilitado (con valor) | Aplica una tarifa/descuento de cantidad fija. |
| Configuración del módulo | Valor de cargo fijo | por ejemplo, 2.00 | La cantidad fija para el cargo/descuento. |
| Configuración del módulo | Resumen del carrito | Habilitado | Muestra la tarifa/descuento detallado en el resumen del carrito. |
| Configuración del módulo | Resumen de la dirección | Habilitado | Muestra la tarifa/descuento en el resumen de la dirección. |
| Configuración del módulo | Habilitado | Habilitado | Activa/desactiva el método de pago. |
| Configuración del módulo | Excluir productos | Vacío | Evita que productos específicos utilicen este método. |
| Configuración del módulo | Excluir categorías | Vacío | Evita que productos de categorías específicas utilicen este método. |
| Configuración del módulo | Habilitar exclusiones | Habilitado (si se establecen reglas) | Interruptor maestro para las reglas de exclusión de productos/categorías. |
| Configuración del módulo | Selectores CSS (Total del carrito, Subtotal, Envío) | Vacío (ajustar si es necesario) | Asegura las actualizaciones correctas del total del carrito con el tema. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: El método de pago "Pago en tienda al recoger" no aparece durante el proceso de compra.**
R:

- **Verifique el ajuste "Habilitado":** Vaya a Módulos > Gestor de módulos > Configurar para "Pago en tienda al recoger (+tarifa)" y asegúrese de que el interruptor principal "Habilitado" esté ENCENDIDO.
- **Verifique las restricciones de valor del carrito:** Verifique sus ajustes de "Valor mínimo total del carrito" y "Valor máximo total del carrito". Si el total del carrito del cliente está fuera de este rango, el método no aparecerá.
- **Verifique las exclusiones:** Si ha configurado exclusiones de productos o categorías, asegúrese de que el carrito actual no contenga ningún artículo excluido. Además, verifique si "Habilitar exclusiones" está ENCENDIDO.
- **Verifique las restricciones geográficas:** Asegúrese de que el método de pago no esté restringido por país o moneda en la configuración general de pagos de PrestaShop (Pago > Preferencias).
- **Borrar caché:** A veces, la caché de PrestaShop puede evitar que los cambios aparezcan inmediatamente. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché".

**P2: La tarifa/descuento no se aplica o no se muestra correctamente en la página de pago.**
R:

- **Verifique la configuración de tarifa/descuento:** Vuelva a verificar que "Cargo porcentual" o "Cargo fijo" esté habilitado y que el valor correspondiente se haya introducido correctamente. Además, asegúrese de que "Aplicar descuento (no tarifa)" esté configurado según lo previsto.
- **Verifique la configuración de visualización:** Asegúrese de que "Valor de la tarifa cerca del método de pago", "Resumen del carrito" y "Resumen de la dirección" estén todos habilitados para una máxima visibilidad.
- **Selectores CSS (Avanzado):** Si su tema está muy personalizado, es posible que el módulo no pueda encontrar los elementos correctos para actualizar. Verifique los ajustes de "Selectores CSS para elementos del carrito". Es posible que necesite un webmaster para identificar los selectores correctos para los elementos de total del carrito, subtotal y envío de su tema.

**P3: ¿Cómo cambio el texto "Pago en tienda al recoger" por otra cosa?**
R:

- Puede cambiar el nombre de visualización directamente en la configuración del módulo. Busque el ajuste "Título del método de pago" en la página de configuración principal.
- Para tiendas multilingües, asegúrese de seleccionar el idioma correcto en el menú desplegable en la parte superior de la página de configuración del módulo (si está disponible) o utilice la herramienta de traducción de PrestaShop (Internacional > Traducciones > Traducciones de módulos instalados).

**P4: ¿Puedo restringir este método de pago solo a ciertos transportistas o grupos de clientes?**
R:

- **Transportistas:** Sí, las preferencias de pago principales de PrestaShop le permiten restringir los métodos de pago por transportista. Vaya a **Pago > Preferencias** en su Back Office. En la sección "Restricciones de transportista", asegúrese de que "Pago en tienda al recoger (+tarifa)" esté seleccionado para los transportistas con los que desea permitirlo (por ejemplo, su transportista de "Recogida local").
- **Grupos de clientes:** De manera similar, en **Pago > Preferencias**, puede restringir los métodos de pago por grupo de clientes. Asegúrese de que los grupos de clientes relevantes (por ejemplo, "Cliente", "Visitante") estén seleccionados para este método de pago.

**P5: ¿Qué estado de pedido debo usar para los pedidos de "Pago al recoger"?**
R:

- Se recomienda encarecidamente crear un estado de pedido personalizado en PrestaShop (Pedidos > Estados de pedido) específicamente para los pedidos de "Pago al recoger", como "Esperando pago en tienda al recoger" o "Listo para recoger". Esto le ayuda a identificar fácilmente estos pedidos en su Back Office.
- Luego, en la configuración del módulo, establezca "Estado del pedido para nuevos pedidos" en este estado personalizado.
- Una vez que el cliente haya pagado y recogido, cambie manualmente el estado del pedido a "Pago aceptado" o "Entregado" en la página de detalles del pedido.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo `Pago en tienda al recoger (+tarifa)` (`coppro`) es un módulo de pago estándar de PrestaShop que sigue el patrón MVC. Extiende `PaymentModule` y se integra principalmente a través de hooks para mostrar opciones de pago, procesar la validación y mostrar información del pedido. El módulo calcula dinámicamente tarifas/descuentos basándose en la configuración y actualiza los totales del carrito a través de JavaScript en el front-office durante el proceso de compra. Utiliza `Configuration` para el almacenamiento de ajustes y no introduce clases `ObjectModel` personalizadas ni tablas de base de datos.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `controllers/front/index.php`
    - Nombre de la clase: `CopproIndexModuleFrontController` (probablemente extiende `ModuleFrontController`)
    - Responsabilidad: Este controlador podría servir como un punto de entrada predeterminado o manejar solicitudes generales del front-office relacionadas con el módulo que no encajan en flujos de pago específicos. Dado su nombre, podría ser un fallback o un controlador de visualización simple.
  - `controllers/front/store.php`
    - Nombre de la clase: `CopproStoreModuleFrontController` (probablemente extiende `ModuleFrontController`)
    - Responsabilidad: Potencialmente maneja la lógica relacionada con las ubicaciones de las tiendas o los puntos de recogida, aunque la descripción del módulo no menciona explícitamente múltiples ubicaciones de tiendas. Podría ser un marcador de posición o para una futura expansión.
  - `controllers/front/validation.php`
    - Nombre de la clase: `CopproValidationModuleFrontController` (probablemente extiende `ModuleFrontController`)
    - Responsabilidad: Este es el controlador crítico para el procesamiento de pagos. Recibe la confirmación de pago del proceso de compra, valida el pedido y redirige al cliente a la página de confirmación del pedido. Interactúa con el módulo principal `coppro.php` para finalizar el pedido con el estado correcto y las tarifas/descuentos aplicados.
- **Controladores de administración de Back-Office**:

  - Este módulo no incluye ningún controlador de administración personalizado. Toda la configuración del Back Office se maneja directamente dentro del método `getContent()` del archivo principal del módulo `coppro.php`.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no parece definir ninguna clase personalizada dentro de un directorio `classes/`. Su lógica central reside dentro del archivo principal del módulo `coppro.php`, que extiende `PaymentModule`.

### 4.4 Activos JavaScript (`views/js/`)

- `coppro/lib/searchTool/views/js/autocomplete.js`
  - Alcance: Probablemente Back-office.
  - Responsabilidad: Proporciona funcionalidad de autocompletado, probablemente para la selección de productos o categorías en la configuración del módulo (por ejemplo, para listas de exclusión). Se vincula a los campos de entrada y realiza solicitudes AJAX para obtener sugerencias.
- `coppro/views/js/adminCopproDashboard.js`
  - Alcance: Back-office.
  - Responsabilidad: Gestiona JavaScript para cualquier panel de administración o funciones de análisis dentro de la página de configuración del módulo. Podría manejar la representación de gráficos o la visualización de datos.
- `coppro/views/js/adminCopproProductSearch.js`
  - Alcance: Back-office.
  - Responsabilidad: Maneja específicamente la interfaz de búsqueda de productos dentro de la configuración de administración del módulo, probablemente para el ajuste "Excluir productos". Gestiona la entrada de búsqueda, la visualización de resultados y la selección.
- `coppro/views/js/adminCopproSelector.js`
  - Alcance: Back-office.
  - Responsabilidad: Gestiona la lógica de selección para varios elementos en el panel de administración, posiblemente para categorías u otras listas configurables.
- `coppro/views/js/coppro-checkout.js`
  - Alcance: Front-office.
  - Responsabilidad: Este es el script principal del front-office. Escucha los cambios en la selección del método de pago durante el proceso de compra. Cuando se elige "Pago en tienda al recoger", actualiza dinámicamente el resumen del carrito (total, subtotal, envío) para reflejar la tarifa o el descuento calculado. Utiliza los selectores CSS definidos en la configuración del módulo (`COPPRO_CSS_CART_TOTAL`, etc.) para apuntar y modificar los elementos del DOM. También podría manejar llamadas AJAX para recalcular los totales si se necesita el backend.
- `coppro/views/js/copproBoMockConsole.js`
  - Alcance: Back-office.
  - Responsabilidad: Probablemente una utilidad de depuración o desarrollo, posiblemente para simular la salida de la consola o el registro dentro del Back Office.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `coppro/lib/searchTool/views/css/autocomplete.css`
  - Alcance: Back-office.
  - Responsabilidad: Estiliza los desplegables de autocompletado y los campos de entrada de búsqueda utilizados en la configuración de administración.
- `coppro/views/css/admin_coppro.css`
  - Alcance: Estilo del formulario de administración del Back-office.
  - Responsabilidad: Proporciona un estilo específico para la página de configuración del módulo en el Back Office de PrestaShop, asegurando una interfaz consistente y fácil de usar.
- `coppro/views/css/coppro.css`
  - Alcance: Estilo del cliente del Front-office.
  - Responsabilidad: Contiene estilos para la visualización de la opción de pago "Pago en tienda al recoger", potencialmente para el logotipo de pago, el texto de la tarifa/descuento o cualquier elemento personalizado introducido por el módulo en la página de pago. Los desarrolladores pueden anular estos estilos en el `custom.css` de su tema o en un tema hijo.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:

  - `coppro/views/templates/hook/confirmation.tpl`
    - Hook: Probablemente `displayPaymentReturn` o similar.
    - Salidas: Contenido para la página de confirmación del pedido después de un pedido exitoso de "Pago al recoger", informando al cliente sobre el pago al recoger.
  - `coppro/views/templates/hook/displayAdminOrder16.tpl`
    - Hook: `displayAdminOrder` (para PrestaShop 1.6.x).
    - Salidas: Información adicional o acciones relacionadas con los pedidos de "Pago al recoger" dentro de la página de detalles del pedido del Back Office para PS 1.6.
  - `coppro/views/templates/hook/displayAdminOrder17.tpl`
    - Hook: `displayAdminOrder` (para PrestaShop 1.7.x, 8.x, 9.x).
    - Salidas: Similar a `displayAdminOrder16.tpl` pero adaptado para la página de detalles del pedido del Back Office de PS 1.7+, mostrando potencialmente instrucciones de recogida o detalles de la tarifa.
  - `coppro/views/templates/hook/displayOrderDetail.tpl`
    - Hook: `displayOrderDetail`.
    - Salidas: Información sobre el método de pago "Pago en tienda al recoger" dentro de la página de detalles del pedido del front-office del cliente.
  - `coppro/views/templates/hook/payment.tpl`
    - Hook: `paymentOptions` (o `displayPaymentOptions`).
    - Salidas: La estructura HTML para la opción de pago "Pago en tienda al recoger" en la página de pago, incluyendo el logotipo de pago, el título y el texto de la tarifa/descuento calculado dinámicamente.
- **Plantillas de administración (`views/templates/admin/`)**:

  - `coppro/lib/searchTool/views/scripts.tpl`
    - Hook: Probablemente `actionAdminControllerSetMedia` o incluido directamente en `getContent()`.
    - Salidas: Incluye activos JavaScript y CSS para la herramienta de búsqueda utilizada en la configuración de administración.
  - `coppro/views/templates/admin/productSearchTool.tpl`
    - Salidas: La estructura HTML para la interfaz de búsqueda y selección de productos dentro de la configuración del módulo, utilizada para el ajuste "Excluir productos".
  - `coppro/views/templates/admin/scopeSelector.tpl`
    - Salidas: HTML para un selector de alcance genérico, potencialmente utilizado para categorías u otras listas filtrables en la configuración de administración.
- **Plantillas de Front-office (`views/templates/front/`)**:

  - `coppro/views/templates/front/validation.tpl`
    - Salidas: Contenido mostrado por `CopproValidationModuleFrontController` después de la validación del pago, típicamente una redirección o un mensaje simple antes de la página de confirmación final.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:
  El módulo no crea tablas de base de datos personalizadas. Todos sus ajustes de configuración se almacenan en la tabla `ps_configuration` utilizando los métodos `Configuration::updateValue()` y `Configuration::get()`, con claves prefijadas por `COPPRO_`.
  Ejemplo de claves de configuración:

  - `COPPRO_OS`
  - `COPPRO_OS_READY`
  - `COPPRO_MAXCART_V`
  - `COPPRO_MINCART_V`
  - `COPPRO_FEEPAY`
  - `COPPRO_DISCOUNT`
  - `COPPRO_CHARGEP_V`
  - `COPPRO_CHARGEA_V`
  - `COPPRO_EXCL_PRODUCTS`
  - `COPPRO_EXCL_CAT`
  - `COPPRO_TITLE`
  - `COPPRO_CARTPRESENTER`
  - `COPPRO_HOWFEE`
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Para incluir activos CSS (`coppro.css`) y JavaScript (`coppro-checkout.js`) del front-office. |
| `displayPaymentOptions` | Durante el proceso de compra, para listar los métodos de pago disponibles. | Para mostrar la opción de pago "Pago en tienda al recoger" con su título, logotipo y tarifa/descuento calculado. |
| `paymentOptions` | Alias para `displayPaymentOptions` (versiones anteriores de PS). | Igual que `displayPaymentOptions`. |
| `displayPaymentReturn` | En la página de confirmación del pedido después del pago. | Para mostrar instrucciones específicas o mensajes de confirmación para pedidos de "Pago al recoger". |
| `displayPDFInvoice` | Cuando se genera una factura PDF. | Para asegurar que el método de pago "Pago en tienda al recoger" se indique correctamente en la factura. |
| `displayOrderDetail` | En la página de detalles del pedido del cliente en el front-office. | Para mostrar el método de pago elegido y cualquier detalle relacionado. |
| `displayAdminOrder` | En la página de detalles del pedido en el Back Office. | Para mostrar información adicional o herramientas de gestión específicas para pedidos de "Pago al recoger" para los administradores. |
| `actionAdminControllerSetMedia` | Cuando un controlador de administración carga sus activos multimedia. | Para incluir activos CSS (`admin_coppro.css`, `autocomplete.css`) y JavaScript (`adminCopproDashboard.js`, `adminCopproProductSearch.js`, `adminCopproSelector.js`, `autocomplete.js`) del Back-office para la página de configuración del módulo. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Para realizar cualquier acción posterior a la validación, como actualizar el estado del pedido o registrar detalles, específicos de los pedidos de "Pago al recoger". |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte técnico oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con el módulo "Pago en tienda al recoger (+tarifa)".

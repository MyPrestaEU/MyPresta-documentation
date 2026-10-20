---
title: "Pago contra reembolso con recargo - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Pago contra reembolso con recargo de MyPresta.eu."
sidebar:
  label: "Pago contra reembolso con recargo - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Cash on delivery with fee en MyPresta.eu](https://mypresta.eu/modules/payment-process/cash-on-delivery-with-fee.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/cash-on-delivery-with-fee/)
>
> ---


# Pago contra reembolso con recargo

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y normalmente están disponibles en cualquier entorno de alojamiento moderno.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Pago contra reembolso con recargo", accesible directamente después de la instalación o navegando a **Módulos > Gestor de módulos**, buscando "Pago contra reembolso con recargo" y haciendo clic en "Configurar".

#### **Configuración General**

-   **Desactivar / Activar / Desactivado (Estado Principal del Módulo)**

    -   **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar todo el método de pago contra reembolso con recargo en su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está Activado:* La opción de pago COD, junto con sus recargos configurados, estará disponible para los clientes durante el proceso de compra.
        -   *Cuando está Desactivado:* La opción de pago COD no se mostrará a los clientes, independientemente de otros ajustes.
    -   **Valor recomendado:** `Activado` si tiene la intención de ofrecer COD.
    -   **Escenario / ejemplo de comerciante:** Si está probando el módulo o desea dejar de ofrecer COD temporalmente, lo establecería en `Desactivado`.
-   **Valor (Valor del Recargo por COD)**

    -   **Qué hace este ajuste:** Este campo determina la cantidad base o el porcentaje del recargo por COD. La interpretación exacta (cantidad fija o porcentaje) depende del ajuste "Cómo incluir el recargo?" a continuación.
    -   **Efecto de cambiar este ajuste:** Cambia directamente el coste añadido a los pedidos COD.
    -   **Valor recomendado:** Comience con `0.00` y ajuste según las tarifas de su transportista.
    -   **Escenario / ejemplo de comerciante:** Si su transportista cobra 2,50 € por COD, podría introducir `2.50`. Si cobra el 1% del pedido, podría introducir `1`.
-   **Cómo incluir el recargo?**

    -   **Qué hace este ajuste:** Define cómo se aplica el "Valor" (del ajuste anterior) al total del pedido.
    -   **Efecto de cambiar este ajuste:**
        -   *Incluir en los costes de envío:* El recargo por COD se añade al coste de envío mostrado al cliente. Esto puede simplificar la visualización del proceso de compra al combinar los cargos.
        -   *Incluir como un producto/servicio separado:* El recargo por COD aparece como una línea de artículo distinta en el resumen del carrito y la factura, a menudo etiquetado como "Recargo por COD" o similar. Esto proporciona la máxima transparencia.
    -   **Valor recomendado:** `Incluir como un producto/servicio separado` para mayor claridad y cumplimiento legal.
    -   **Escenario / ejemplo de comerciante:** Si desea que los clientes vean claramente el cargo por COD como un artículo separado, elija "Incluir como un producto/servicio separado". Si prefiere un coste de envío más limpio y combinado, elija "Incluir en los costes de envío".
-   **Estado del pedido después de la compra con el módulo COD**

    -   **Qué hace este ajuste:** Especifica el estado inicial de un pedido realizado utilizando el método de pago COD.
    -   **Efecto de cambiar este ajuste:** Determina cómo aparecen los pedidos COD en su Back Office inmediatamente después de ser realizados.
    -   **Valor recomendado:** `Pago aceptado` (o un estado similar de "esperando pago" que haya configurado). Esto le permite diferenciar los pedidos COD que están confirmados pero aún no pagados físicamente.
    -   **Escenario / ejemplo de comerciante:** Podría establecerlo en "Esperando pago contra reembolso" (si ha creado dicho estado) para filtrar y gestionar fácilmente los pedidos COD que están pendientes de pago físico en el momento de la entrega.
-   **Mostrar resumen adicional antes de la confirmación**

    -   **Qué hace este ajuste:** Controla si se muestra un bloque de resumen adicional en el paso final del proceso de compra, justo antes de que el cliente confirme su pedido.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Se mostrará un desglose detallado que incluye el total del carrito, el envío y el recargo por COD.
        -   *Cuando está desactivado:* Se utilizará el resumen estándar de PrestaShop, que podría no desglosar explícitamente el recargo por COD como una línea de artículo separada.
    -   **Valor recomendado:** `Activado` para máxima transparencia y cumplimiento legal.
    -   **Escenario / ejemplo de comerciante:** Para asegurarse de que los clientes estén completamente informados de todos los cargos antes de comprometerse, especialmente el recargo por COD, active esta opción.
-   **Resumen del carrito / Resumen de la dirección / Valor mínimo del total del carrito (Selectores CSS)**

    -   **Qué hace este ajuste:** Estos campos le permiten especificar selectores CSS para varios elementos en su página de pago. El módulo utiliza estos selectores para inyectar correctamente la información del recargo por COD en el resumen de pago de su tema.
    -   **Efecto de cambiar este ajuste:** Si su tema utiliza clases CSS no estándar para estos elementos, ajustar estos selectores asegura que el recargo por COD se muestre correctamente. Los valores incorrectos pueden hacer que el recargo no aparezca o aparezca en el lugar equivocado.
    -   **Valor recomendado:** Dejar vacío para la detección automática o usar los valores predeterminados proporcionados por el módulo. Solo cambie si la visualización del recargo por COD está rota en su tema personalizado.
    -   **Escenario / ejemplo de comerciante:** Si ha instalado un tema personalizado y el recargo por COD no aparece en el resumen del carrito, su desarrollador web podría necesitar inspeccionar el HTML de su tema y actualizar estos selectores para que coincidan con la estructura de su tema.

#### **Cálculo y Condiciones del Recargo**

-   **Desactivar / Activar / Desactivado (Condición de Valor Máximo del Carrito)**

    -   **Qué hace este ajuste:** Activa o desactiva una condición en la que el método de pago COD solo está disponible si el total del carrito es *inferior* a un cierto valor máximo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está Activado:* Los clientes con carritos que superen el valor máximo especificado no verán COD como una opción de pago.
        -   *Cuando está Desactivado:* No se aplica ninguna restricción de valor máximo del carrito a COD.
    -   **Valor recomendado:** `Desactivado` a menos que tenga razones específicas para limitar los pedidos COD de alto valor.
    -   **Escenario / ejemplo de comerciante:** Si ha tenido problemas con pedidos COD fraudulentos o no cobrados de alto valor, podría activar esto y establecer un `CODPRO_MOD_MAXCART_V` en 500 € para mitigar el riesgo.
-   **CODPRO\_MOD\_MAXCART\_V (Valor Máximo del Carrito)**

    -   **Qué hace este ajuste:** El valor monetario específico para la condición de total máximo del carrito.
    -   **Efecto de cambiar este ajuste:** Define el límite superior para la elegibilidad de COD.
    -   **Valor recomendado:** Establezca un valor que se alinee con su tolerancia al riesgo para los pedidos COD.
    -   **Escenario / ejemplo de comerciante:** Si `Desactivar / Activar / Desactivado (Condición de Valor Máximo del Carrito)` está activado, y lo establece en `500.00`, los clientes con pedidos superiores a 500 € no podrán usar COD.
-   **Desactivar / Activar / Desactivado (Condición de Valor Mínimo del Carrito)**

    -   **Qué hace este ajuste:** Activa o desactiva una condición en la que el método de pago COD solo está disponible si el total del carrito es *superior* a un cierto valor mínimo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está Activado:* Los clientes con carritos por debajo del valor mínimo especificado no verán COD como una opción de pago.
        -   *Cuando está Desactivado:* No se aplica ninguna restricción de valor mínimo del carrito a COD.
    -   **Valor recomendado:** `Desactivado` a menos que tenga razones específicas para evitar pedidos COD muy pequeños.
    -   **Escenario / ejemplo de comerciante:** Si el recargo fijo por COD hace que los pedidos muy pequeños no sean rentables, podría activar esto y establecer un `CODPRO_MOD_MINCART_V` en 10 €.
-   **CODPRO\_MOD\_MINCART\_V (Valor Mínimo del Carrito)**

    -   **Qué hace este ajuste:** El valor monetario específico para la condición de total mínimo del carrito.
    -   **Efecto de cambiar este ajuste:** Define el límite inferior para la elegibilidad de COD.
    -   **Valor recomendado:** Establezca un valor que haga que COD sea rentable para usted.
    -   **Escenario / ejemplo de comerciante:** Si `Desactivar / Activar / Desactivado (Condición de Valor Mínimo del Carrito)` está activado, y lo establece en `10.00`, los clientes con pedidos inferiores a 10 € no podrán usar COD.
-   **CODPRO\_CHARGEP\_V (Valor del Recargo Porcentual)**

    -   **Qué hace este ajuste:** Este campo define el valor porcentual del recargo por COD.
    -   **Efecto de cambiar este ajuste:** Si "Cómo incluir el recargo?" está configurado para una opción basada en porcentaje, este valor se utilizará para calcular el recargo.
    -   **Valor recomendado:** `0.00` inicialmente, ajuste según el cargo porcentual de su transportista.
    -   **Escenario / ejemplo de comerciante:** Si su transportista cobra el 1,5% del valor del pedido por COD, introduciría `1.5` aquí.
-   **CODPRO\_PERCENTAGE\_TYPE (Base de Cálculo del Porcentaje)**

    -   **Qué hace este ajuste:** Determina *sobre qué* se calcula el recargo porcentual.
    -   **Efecto de cambiar este ajuste:**
        -   *Total del carrito (con envío):* El porcentaje se calcula sobre el importe total, incluyendo productos y envío.
        -   *Total del carrito (sin envío):* El porcentaje se calcula solo sobre el subtotal de los productos.
    -   **Valor recomendado:** `Total del carrito (con envío)` ya que así es como los transportistas suelen calcular sus recargos por COD.
    -   **Escenario / ejemplo de comerciante:** Si su transportista cobra el 1% del *importe total* que cobra al cliente (productos + envío), elija "Total del carrito (con envío)".
-   **CODPRO\_CHARGEA\_V (Valor del Recargo de Cantidad Fija)**

    -   **Qué hace este ajuste:** Este campo define la cantidad monetaria fija del recargo por COD.
    -   **Efecto de cambiar este ajuste:** Si "Cómo incluir el recargo?" está configurado para una opción de cantidad fija, se utilizará este valor.
    -   **Valor recomendado:** `0.00` inicialmente, ajuste según el cargo fijo de su transportista.
    -   **Escenario / ejemplo de comerciante:** Si su transportista cobra una tarifa plana de 3,00 € por COD, introduciría `3.00` aquí.
-   **CODPRO\_MIN\_CHARGEV (Cargo Mínimo para Recargo Porcentual)**

    -   **Qué hace este ajuste:** Si está utilizando un recargo basado en porcentaje, esto establece una cantidad fija mínima que tendrá el recargo por COD, incluso si el porcentaje calculado es menor.
    -   **Efecto de cambiar este ajuste:** Asegura que siempre recupere al menos una cierta cantidad por COD, especialmente en pedidos pequeños donde un porcentaje podría ser muy bajo.
    -   **Valor recomendado:** `0.00` (sin mínimo) o una pequeña cantidad como `1.00` o `2.00` si tiene un coste mínimo.
    -   **Escenario / ejemplo de comerciante:** Si su recargo porcentual es del 1%, y un pedido de 50 € resultaría en un recargo de 0,50 €, pero desea asegurar un mínimo de 1,50 €, lo establecería en `1.50`.
-   **CODPRO\_MAX\_CHARGEV (Cargo Máximo para Recargo Porcentual)**

    -   **Qué hace este ajuste:** Si está utilizando un recargo basado en porcentaje, esto establece una cantidad fija máxima que tendrá el recargo por COD, incluso si el porcentaje calculado es mayor.
    -   **Efecto de cambiar este ajuste:** Evita que el recargo por COD sea excesivamente alto en pedidos muy grandes.
    -   **Valor recomendado:** `0.00` (sin máximo) o un límite razonable como `10.00` o `15.00`.
    -   **Escenario / ejemplo de comerciante:** Si su recargo porcentual es del 1% y un pedido de 2000 € resultaría en un recargo de 20 €, pero desea limitar el recargo por COD a 10 €, lo establecería en `10.00`.
-   **CODPRO\_FEETAX (Aplicar Impuesto al Recargo)**

    -   **Qué hace este ajuste:** Determina si el propio recargo por COD debe estar sujeto a IVA/impuestos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El recargo por COD tendrá impuestos aplicados según la regla fiscal seleccionada.
        -   *Cuando está desactivado:* El recargo por COD se tratará como exento de impuestos.
    -   **Valor recomendado:** `Activado` si sus regulaciones fiscales locales requieren que los recargos sean gravados. Consulte a su contable.
    -   **Escenario / ejemplo de comerciante:** En muchos países, las tarifas de servicio como los cargos por COD están sujetas a IVA. Activaría esto para garantizar el cumplimiento.
-   **CODPRO\_FEETAXRULE (Regla Fiscal para el Recargo)**

    -   **Qué hace este ajuste:** Si `CODPRO_FEETAX` está activado, este desplegable le permite seleccionar qué regla fiscal de PrestaShop se aplica al recargo por COD.
    -   **Efecto de cambiar este ajuste:** La tasa impositiva seleccionada se aplicará al recargo por COD.
    -   **Valor recomendado:** Seleccione la regla fiscal apropiada para los servicios en su país.
    -   **Escenario / ejemplo de comerciante:** Si tiene una regla fiscal "IVA Estándar (20%)" para servicios, la seleccionaría aquí.

#### **Recargos Específicos por Transportista**

-   **codpro\_carrier (Selección de Transportista)**
    -   **Qué hace este ajuste:** Esta sección le permite definir diferentes recargos por COD para cada transportista que ofrezca.
    -   **Efecto de cambiar este ajuste:** Cuando un cliente selecciona un transportista específico durante el proceso de compra, se aplicará el recargo por COD asociado a ese transportista en lugar del recargo general.
    -   **Valor recomendado:** Configure los recargos para todos los transportistas que ofrezcan COD.
    -   **Escenario / ejemplo de comerciante:** Si el Transportista A cobra 3,00 € por COD y el Transportista B cobra el 1,5% del valor del pedido, puede configurar estas tarifas distintas aquí.

#### **Configuración Avanzada (Normalmente para Desarrolladores/Escenarios Específicos)**

-   **PS\_LANG\_DEFAULT / PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG (Configuración de Idioma)**

    -   **Qué hace este ajuste:** Estos son valores de configuración estándar de PrestaShop relacionados con el idioma predeterminado y el idioma del formulario del empleado. El módulo podría mostrarlos como referencia, pero normalmente no requiere modificación aquí.
    -   **Efecto de cambiar este ajuste:** No tiene un efecto directo en la funcionalidad principal del módulo, pero asegura la correcta visualización del idioma en el Back Office.
    -   **Valor recomendado:** Dejar como predeterminado.
-   **CODPRO\_ANALYTICS\_DEFAULT\_CHART / CODPRO\_ANALYTICS\_PERIOD / CODPRO\_ANALYTICS\_IMPACT\_DAYS / CODPRO\_ANALYTICS\_CHART\_WEEKS / CODPRO\_ANALYTICS\_CHART\_MONTHS (Configuración de Análisis)**

    -   **Qué hace este ajuste:** Estos ajustes se relacionan con posibles funciones internas de análisis o panel de control dentro del módulo (si están implementadas). Controlan cómo se pueden mostrar o filtrar los datos.
    -   **Efecto de cambiar este ajuste:** Cambia cómo se pueden presentar los datos analíticos relacionados con los pedidos COD en el Back Office.
    -   **Valor recomendado:** Dejar como predeterminado a menos que tenga requisitos analíticos específicos.
    -   **Escenario / ejemplo de comerciante:** Si el módulo incluye un panel de control, estos ajustes podrían controlar la vista predeterminada (por ejemplo, los últimos 7 días, el último mes) para el rendimiento de los pedidos COD.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### **4.2.1 AdminCodProCarriersFeesController (Back Office > Módulos > Pago contra reembolso con recargo > Recargos por Transportista)**

-   **Nombre de la Pantalla y Ubicación del Menú:** "Recargos por Transportista" (normalmente se encuentra bajo el elemento de menú "Pago contra reembolso con recargo" en el Back Office de PrestaShop).
-   **Acciones y Ajustes Disponibles:** Esta pantalla proporciona una vista de cuadrícula o lista para gestionar los recargos por COD específicamente para cada transportista que ofrezca. Puede añadir nuevas reglas específicas por transportista, editar las existentes o eliminarlas. Para cada transportista, puede definir:
    -   Si el recargo es una cantidad fija o un porcentaje.
    -   La cantidad fija o el valor porcentual específico.
    -   Cargos mínimos y máximos para los recargos porcentuales.
    -   Si se aplica impuestos y qué regla fiscal utilizar.
-   **Efecto de los cambios:** Cualquier regla configurada aquí anulará la configuración general del recargo por COD para los transportistas especificados. Si un transportista tiene una regla aquí, se aplicará el recargo de esa regla. Si un transportista no aparece aquí, se aplicará la configuración general del recargo por COD.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise regularmente esta sección si sus contratos con transportistas o los cargos por COD cambian. Añada nuevos transportistas a medida que los introduzca en su tienda y configure sus recargos específicos por COD.

#### **4.2.2 AdminCodProCarriersRangeFeesController (Back Office > Módulos > Pago contra reembolso con recargo > Recargos por Rango)**

-   **Nombre de la Pantalla y Ubicación del Menú:** "Recargos por Rango" (normalmente se encuentra bajo el elemento de menú "Pago contra reembolso con recargo" en el Back Office de PrestaShop).
-   **Acciones y Ajustes Disponibles:** Esta pantalla le permite definir recargos por COD basados en el valor total del carrito del cliente. Puede configurar diferentes estructuras de recargos para varios rangos de precios (por ejemplo, pedidos de 0 € a 50 €, de 50 € a 100 €, etc.). Para cada rango, puede definir:
    -   El valor mínimo y máximo del carrito para el rango.
    -   Si el recargo es una cantidad fija o un porcentaje.
    -   La cantidad fija o el valor porcentual específico.
    -   Cargos mínimos y máximos para los recargos porcentuales dentro de ese rango.
    -   Si se aplica impuestos y qué regla fiscal utilizar.
-   **Efecto de los cambios:** Estas reglas basadas en rangos proporcionan una capa adicional de flexibilidad. Si el total del carrito de un cliente se encuentra dentro de un rango definido, se aplicará el recargo especificado para ese rango. Estas reglas pueden interactuar con las reglas específicas del transportista, lo que potencialmente permite un control muy granular (por ejemplo, el Transportista A cobra X por pedidos inferiores a 50 € e Y por pedidos superiores a 50 €).
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esta sección para implementar precios dinámicos para COD basados en el valor del pedido. Esto es particularmente útil para gestionar el riesgo en pedidos de alto valor o para hacer que COD sea más atractivo para pedidos de rango medio.

#### **4.2.3 index.php (Back Office > Módulos > Pago contra reembolso con recargo > Panel de Control/Análisis)**

-   **Nombre de la Pantalla y Ubicación del Menú:** Este controlador `index.php` suele servir como marcador de posición o punto de entrada predeterminado para la sección de administración de un módulo. En el contexto de este módulo, podría usarse para mostrar un panel de control o análisis relacionados con los pedidos COD.
-   **Acciones y Ajustes Disponibles:** Si este controlador se utiliza para un panel de control, probablemente mostraría gráficos, estadísticas o indicadores clave de rendimiento (KPI) relacionados con los pedidos COD (por ejemplo, número de pedidos COD, ingresos totales de COD, recargo promedio de COD cobrado). Podría haber filtros para rangos de fechas u otros parámetros.
-   **Efecto de los cambios:** La interacción con un panel de control aquí solo cambiaría los datos mostrados, no la configuración de la tienda.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise periódicamente este panel de control (si está disponible) para monitorear el rendimiento y el impacto de su método de pago COD.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración Principal del Módulo** | Activado / Desactivado | Activado | Interruptor maestro para el método de pago COD. |
| | Valor (Recargo Base) | 0.00 | Cantidad/porcentaje de recargo predeterminado. |
| | ¿Cómo incluir el recargo? | Incluir como un producto/servicio separado | Determina cómo aparece el recargo en el carrito/factura. |
| | Estado del pedido después de la compra | Pago aceptado | Estado inicial para pedidos COD. |
| | Mostrar resumen adicional | Activado | Muestra un desglose detallado del recargo antes de la confirmación. |
| | Condición de Valor Máximo del Carrito | Desactivado | Restringe el COD para pedidos superiores a un valor. |
| | Valor Máximo del Carrito | 0.00 | El valor máximo específico del carrito. |
| | Condición de Valor Mínimo del Carrito | Desactivado | Restringe el COD para pedidos inferiores a un valor. |
| | Valor Mínimo del Carrito | 0.00 | El valor mínimo específico del carrito. |
| | Valor del Recargo Porcentual | 0.00 | El valor porcentual para el recargo por COD. |
| | Base de Cálculo del Porcentaje | Total del carrito (con envío) | Sobre qué se calcula el porcentaje. |
| | Valor del Recargo de Cantidad Fija | 0.00 | El valor de cantidad fija para el recargo por COD. |
| | Cargo Mínimo (para %) | 0.00 | Asegura un recargo mínimo para los cálculos porcentuales. |
| | Cargo Máximo (para %) | 0.00 | Limita el recargo para los cálculos porcentuales. |
| | Aplicar Impuesto al Recargo | Activado (si aplica) | Determina si el recargo por COD está gravado. |
| | Regla Fiscal para el Recargo | Seleccionar regla fiscal apropiada | Qué regla fiscal se aplica al recargo. |
| **AdminCodProCarriersFees** | Reglas de recargo específicas por transportista | Configurar según sea necesario | Anula el recargo general para transportistas específicos. |
| **AdminCodProCarriersRangeFees** | Reglas de recargo por rango de valor de pedido | Configurar según sea necesario | Aplica diferentes recargos según los rangos del total del carrito. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: El recargo por COD no aparece en mi página de pago, o está en el lugar equivocado.**
R1: Esto suele ocurrir con temas personalizados.
-   **Verifique "Mostrar resumen adicional antes de la confirmación":** Asegúrese de que esté `Activado` en la configuración principal del módulo.
-   **Selectores CSS:** Si su tema utiliza clases CSS no estándar, es posible que el módulo no encuentre los lugares correctos para inyectar el recargo. Vaya a la página de configuración del módulo y verifique los campos de selector CSS "Resumen del carrito", "Resumen de la dirección" y "Valor mínimo del total del carrito". Es posible que necesite un desarrollador web para inspeccionar el HTML de su tema y proporcionar los selectores correctos.
-   **Borrar Caché:** Siempre borre la caché de PrestaShop (Parámetros Avanzados > Rendimiento > Borrar Caché) después de realizar cambios en la configuración.

**P2: He configurado un recargo, pero no se aplica a los pedidos.**
R2:
-   **Módulo Activado:** Asegúrese de que el interruptor principal "Activado / Desactivado" del módulo esté configurado en `Activado`.
-   **Valor del Recargo:** Verifique que haya introducido un "Valor" distinto de cero en la configuración principal, o que haya configurado recargos específicos en las secciones "Recargos por Transportista" o "Recargos por Rango".
-   **Condiciones Cumplidas:** Verifique que el carrito del cliente cumpla con las condiciones de "Valor Mínimo del Carrito" o "Valor Máximo del Carrito" que haya establecido.
-   **Anulaciones Específicas del Transportista:** Si ha configurado recargos en "Recargos por Transportista", asegúrese de que el cliente esté seleccionando uno de esos transportistas. Si no, se debería aplicar el recargo general.
-   **Regla Fiscal:** Si está utilizando una regla fiscal para el recargo, asegúrese de que la propia regla fiscal esté configurada correctamente en PrestaShop.

**P3: ¿Cómo traduzco el texto del módulo (por ejemplo, "Recargo por COD") a otros idiomas?**
R3: Puede traducir las cadenas del módulo directamente dentro de PrestaShop:
-   Navegue a **Internacional > Traducciones**.
-   Seleccione "Traducciones de módulos instalados".
-   Elija su tema, su idioma y luego seleccione "Pago contra reembolso con recargo" del desplegable del módulo.
-   Verá una lista de todas las cadenas traducibles del módulo. Introduzca sus traducciones y guarde.

**Q4: ¿Puedo ofrecer COD solo para grupos de clientes o países específicos?**
R4: El módulo "Pago contra reembolso con recargo" en sí mismo no tiene opciones integradas para restricciones de grupos de clientes o países. Sin embargo, se pueden utilizar las restricciones del módulo de pago principal de PrestaShop:
-   Vaya a **Parámetros de la tienda > Configuración de pedidos > Pago**.
-   Puede restringir los métodos de pago por moneda, país o grupo. Busque "Pago contra reembolso con recargo" y aplique las restricciones deseadas allí.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo "Pago contra reembolso con recargo" (`codpro`) sigue una arquitectura de módulo estándar de PrestaShop, extendiendo `PaymentModule` para integrarse en el flujo de pago. Utiliza varios controladores frontales y de administración para funcionalidades específicas como la validación de pagos, la gestión de recargos específicos por transportista y las configuraciones de recargos basados en rangos. El módulo se basa en gran medida en el sistema de hooks de PrestaShop para inyectar su lógica y elementos de visualización en varias etapas del front-office (pago, confirmación de pedido, factura) y back-office (vista de pedido). La configuración se almacena principalmente en `ps_configuration`, con tablas personalizadas probablemente utilizadas para las definiciones de recargos basados en transportistas y rangos.

### 4.2 Controladores (`controllers/`)

#### **Controladores del Front-Office**

-   `controllers/front/index.php`
    -   Nombre de la clase: `CodProIndexModuleFrontController` (probablemente extiende `ModuleFrontController`)
    -   Responsabilidad: Este controlador podría servir como un punto de entrada predeterminado o manejar el enrutamiento básico para las acciones del módulo en el front-office. Dado el propósito del módulo, podría ser un marcador de posición o usarse para solicitudes AJAX simples relacionadas con actualizaciones de cálculo de recargos durante el proceso de compra.
-   `controllers/front/validation.php`
    -   Nombre de la clase: `CodProValidationModuleFrontController` (probablemente extiende `ModuleFrontController`)
    -   Responsabilidad: Este es el controlador crítico para procesar el pago cuando un cliente elige "Pago contra reembolso con recargo". Maneja la validación final del pedido, aplica el recargo por COD calculado al carrito y redirige al cliente a la página de confirmación del pedido. Interactúa con la clase principal del módulo `codpro.php` para recuperar la configuración de los recargos y actualizar el pedido.

#### **Controladores de Administración del Back-Office**

-   `controllers/admin/AdminCodProCarriersFees.php`
    -   Nombre de la clase: `AdminCodProCarriersFeesController` (extiende `ModuleAdminController`)
    -   Nombre de la pestaña: "Recargos por Transportista" (o similar, accesible a través del menú del módulo).
    -   Entidad gestionada: `Configuration` (aunque gestiona entradas de configuración específicas relacionadas con los transportistas).
    -   Responsabilidad: Proporciona la interfaz para gestionar los recargos por COD por transportista. Muestra una lista de los recargos por transportista configurados, permite añadir nuevos y editar/eliminar entradas existentes. Probablemente utiliza `HelperList` y `HelperForm` de PrestaShop para su interfaz de usuario.
-   `controllers/admin/AdminCodProCarriersRangeFees.php`
    -   Nombre de la clase: `AdminCodProCarriersRangeFeesController` (extiende `ModuleAdminController`)
    -   Nombre de la pestaña: "Recargos por Rango" (o similar, accesible a través del menú del módulo).
    -   Entidad gestionada: `CodProTotal` (probablemente un `ObjectModel` personalizado para recargos basados en rangos).
    -   Responsabilidad: Gestiona los recargos por COD basados en rangos de valor de pedido. Proporciona una cuadrícula para definir, editar y eliminar reglas de recargos para diferentes rangos de valor del carrito. Este controlador también aprovecha `HelperList` y `HelperForm` de PrestaShop para su interfaz administrativa.
-   `controllers/admin/index.php`
    -   Nombre de la clase: `AdminCodProIndexController` (probablemente extiende `ModuleAdminController`)
    -   Nombre de la pestaña: Marcador de posición o Panel de control.
    -   Entidad gestionada: Ninguna directamente.
    -   Responsabilidad: Este controlador probablemente sirve como punto de entrada para un panel de control del módulo o una vista predeterminada al navegar a la sección de administración del módulo. Podría mostrar análisis o un resumen de los pedidos COD.

### 4.3 Clases y Modelos Principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto sugiere que la lógica central para gestionar los recargos por transportista y por rango podría manejarse directamente dentro de `AdminCodProCarriersFeesController` y `AdminCodProCarriersRangeFeesController` utilizando interacciones directas con la base de datos o definiendo matrices simples para la configuración. Sin embargo, `AdminCodProCarriersRangeFeesController` gestionando `codprototal` implica que *debería* haber un `ObjectModel` llamado `CodProTotal` (o similar) en el directorio `classes/`, incluso si no se lista explícitamente en el dossier. Si no es así, significa que se utilizan consultas SQL directas, lo cual es menos ideal.

### 4.4 Activos JavaScript (`views/js/`)

-   `views/js/adminCodProCarriersFees.js`
    -   Alcance: Back-office (AdminCodProCarriersFeesController).
    -   Funcionalidad: Probablemente maneja el comportamiento dinámico en la página de configuración de recargos por transportista. Esto podría incluir llamadas AJAX para guardar/cargar datos, validación de formularios o elementos interactivos para añadir/eliminar reglas de recargos por transportista.
-   `views/js/adminCodProDashboard.js`
    -   Alcance: Back-office (AdminCodProIndexController o vista de panel de control similar).
    -   Funcionalidad: Responsable de renderizar gráficos, actualizar estadísticas y manejar elementos interactivos en el panel de control del módulo. Podría utilizar bibliotecas de gráficos (por ejemplo, Chart.js) y realizar solicitudes AJAX para obtener datos analíticos.
-   `views/js/codpro-checkout.js`
    -   Alcance: Front-office (Página de pago).
    -   Funcionalidad: Esto es crucial para la experiencia del usuario en el front-end. Escucha los cambios en la selección del método de pago (específicamente a "Pago contra reembolso con recargo"), actualiza el resumen del pedido dinámicamente para reflejar el recargo por COD y potencialmente maneja solicitudes AJAX para recalcular los recargos si el transportista o el contenido del carrito cambian. Asegura que el recargo sea visible antes de la confirmación del pedido.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `views/css/admin_codpro.css`
    -   Alcance: Back-office (Panel de administración).
    -   Funcionalidad: Proporciona estilos para las páginas de configuración del módulo, la gestión de recargos por transportista, la gestión de recargos por rango y cualquier elemento del panel de control. Asegura una apariencia consistente dentro del Back Office de PrestaShop.
    -   Selectores clave: Probablemente apunta a IDs o clases específicas dentro de los formularios y listas de administración del módulo (por ejemplo, `.codpro-admin-form`, `.codpro-dashboard-chart`).
-   `views/css/codpro.css`
    -   Alcance: Front-office (Página de pago, confirmación de pedido, factura).
    -   Funcionalidad: Estiliza la visualización del recargo por COD en el resumen del pago, las opciones de pago, la página de confirmación del pedido y, potencialmente, la factura en PDF. Asegura que el recargo sea claramente visible e integrado con el tema de la tienda.
    -   Selectores clave: Apunta a elementos donde se inyecta el recargo por COD (por ejemplo, `.codpro-fee-display`, `.payment_option_codpro`, `.order-summary-cod-fee`). Los desarrolladores podrían necesitar anular estos en su tema para una integración visual perfecta.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### **Plantillas de Hook (`views/templates/hook/`)**

-   `views/templates/hook/confirmation.tpl`
    -   Hook: `paymentReturn` o similar.
    -   Salidas: Los detalles del recargo por COD en la página de confirmación del pedido después de un pedido COD exitoso.
-   `views/templates/hook/displayAdminOrder16.tpl`
    -   Hook: `displayAdminOrder` (para PrestaShop 1.6).
    -   Salidas: Información adicional sobre el recargo por COD dentro de la página de detalles del pedido en el Back Office de PrestaShop 1.6.
-   `views/templates/hook/displayAdminOrder17.tpl`
    -   Hook: `displayAdminOrder` (para PrestaShop 1.7+).
    -   Salidas: Similar a `displayAdminOrder16.tpl`, pero adaptado para el diseño de la página de detalles del pedido del Back Office de PrestaShop 1.7+.
-   `views/templates/hook/displayOrderDetail.tpl`
    -   Hook: `displayOrderDetail` (historial de pedidos del cliente en el front-office).
    -   Salidas: Muestra el recargo por COD como parte del resumen del pedido cuando un cliente ve los detalles de su pedido anterior en su sección "Mi cuenta".
-   `views/templates/hook/payment.tpl`
    -   Hook: `displayPaymentOptions` o `paymentOptions`.
    -   Salidas: La opción de pago "Pago contra reembolso con recargo" en la página de pago, incluyendo la cantidad del recargo calculada dinámicamente.
-   `views/templates/hook/pdf.tpl`
    -   Hook: `displayPDFInvoice`.
    -   Salidas: El recargo por COD como una línea de artículo en la factura en PDF generada para el pedido.

#### **Plantillas del Front-office (`views/templates/front/`)**

-   `views/templates/front/validation.tpl`
    -   Propósito: Esta plantilla es probablemente utilizada por el controlador frontal `validation.php`. Podría mostrar un mensaje simple durante el proceso de validación del pago o servir como una página de redirección.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

#### **Tablas de la Base de Datos**

-   `ps_configuration`: Almacena todas las configuraciones generales del módulo (por ejemplo, `CODPRO_MOD_MAXCART_V`, `CODPRO_CHARGEP_V`, `CODPRO_FEETAX`).
-   `ps_codpro_carrier_fees` (probable): Una tabla personalizada para almacenar reglas de recargos por COD específicas del transportista.
    -   Columnas: `id_codpro_carrier_fee`, `id_carrier`, `fee_type` (fijo/porcentaje), `fee_value`, `min_charge`, `max_charge`, `tax_enabled`, `id_tax_rule`.
-   `ps_codpro_range_fees` (probable): Una tabla personalizada para almacenar reglas de recargos por COD basadas en rangos de valor de pedido.
    -   Columnas: `id_codpro_range_fee`, `min_value`, `max_value`, `fee_type`, `fee_value`, `min_charge`, `max_charge`, `tax_enabled`, `id_tax_rule`.

#### **Tabla de Hooks Registrados**

| Nombre del Hook | Alcance | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | En la sección `<head>` de todas las páginas. | Para incluir CSS (`codpro.css`) y JS (`codpro-checkout.js`) del front-office en las páginas relevantes (por ejemplo, pago). |
| `displayPaymentOptions` | Front-Office | Durante la selección del método de pago en el proceso de compra. | Para mostrar "Pago contra reembolso con recargo" como una opción de pago, incluyendo el recargo calculado. |
| `paymentOptions` | Front-Office | Equivalente a `displayPaymentOptions` en PrestaShop 1.6. | Para mostrar "Pago contra reembolso con recargo" como una opción de pago. |
| `paymentReturn` | Front-Office | En la página de confirmación del pedido después del pago. | Para mostrar los detalles del recargo por COD en la página de confirmación. |
| `displayPaymentReturn` | Front-Office | Equivalente a `paymentReturn` en PrestaShop 1.6. | Para mostrar los detalles del recargo por COD en la página de confirmación. |
| `displayPDFInvoice` | Front-Office (Generación de PDF) | Cuando se genera una factura en PDF. | Para añadir el recargo por COD como una línea de artículo en la factura. |
| `displayOrderDetail` | Front-Office (Mi Cuenta) | Cuando un cliente ve los detalles de su pedido. | Para mostrar el recargo por COD en el historial de pedidos del cliente. |
| `displayAdminOrder` | Back-Office (Vista de Pedido) | Cuando un administrador ve un pedido en el Back Office. | Para mostrar los detalles del recargo por COD dentro del resumen del pedido para revisión del administrador. |
| `ActionAdminControllerSetMedia` | Back-Office (Páginas de Administración) | Antes de que un controlador de administración renderice su vista. | Para incluir CSS (`admin_codpro.css`) y JS (`adminCodProCarriersFees.js`, `adminCodProDashboard.js`) del back-office en las páginas de administración del módulo. |
| `actionValidateOrder` | Back-Office (Procesamiento de Pedidos) | Después de que un pedido ha sido validado. | Para realizar potencialmente acciones adicionales o registro de datos relacionados con los pedidos COD. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en MyPresta.eu.

-   **Historial de Pedidos y Descargas de MyPresta.eu:** <https://mypresta.eu/my-account/orders/>
-   **Soporte de MyPresta.eu:** <https://mypresta.eu/contact>

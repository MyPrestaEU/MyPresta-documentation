---
title: "Validar IVA en VIES y establecer 0% IVA - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Validar IVA en VIES y establecer 0% IVA' de MyPresta.eu."
sidebar:
  label: "Validar IVA en VIES y establecer 0% IVA"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Validate VAT in VIES and set 0% VAT en MyPresta.eu](https://mypresta.eu/modules/ordering-process/validate-vat-in-vies-and-set-0-vat.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/validate-vat-in-vies-and-set-0-vat/)
>
> ---


# Validar IVA en VIES y establecer 0% IVA

## 1. Requisitos y compatibilidad

Para garantizar el buen funcionamiento del módulo "Validar IVA en VIES y establecer 0% IVA", revise los siguientes requisitos:

*   **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
*   **Compatibilidad con PHP**: PHP 7.1 - 8.5
*   **Requisitos de alojamiento**: Su entorno de alojamiento debe ser compatible con las extensiones PHP estándar como `cURL` (para comunicarse con el sistema VIES), `JSON` y `OpenSSL`. Estas suelen estar habilitadas por defecto en la mayoría de los proveedores de alojamiento modernos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es el área de configuración principal del módulo, donde controla su comportamiento y apariencia. Navegue a **Módulos > Gestor de módulos**, busque "Validar IVA en VIES y establecer 0% IVA" y haga clic en "Configurar".

#### **Configuración general**

*   **Su país:**
    *   **Qué hace este ajuste:** Define el país donde está registrada su empresa. Esto es crucial para determinar si el número de IVA de un cliente califica para el 0% de IVA (es decir, si es de un país *diferente* de la UE).
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando se establece en su país:* El módulo identificará correctamente las ventas intracomunitarias.
        *   *Cuando se establece incorrectamente:* La lógica de validación del IVA podría fallar o aplicar el 0% de IVA incorrectamente.
    *   **Valor recomendado:** El país de registro oficial de su tienda (por ejemplo, "España").
    *   **Escenario / ejemplo de comerciante:** Si su tienda tiene su sede en Alemania, seleccionaría "Alemania". Un cliente de Francia con un número de IVA francés válido sería entonces elegible para el 0% de IVA.
*   **Países elegibles:**
    *   **Qué hace este ajuste:** Le permite seleccionar qué países de la UE son elegibles para la regla del 0% de IVA. Puede elegir países específicos o seleccionar todos los países de la UE.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando se seleccionan países específicos:* Solo los clientes de esos países (con IVA válido) obtendrán el 0% de IVA.
        *   *Cuando se seleccionan todos los países de la UE:* Todos los países de la UE (excluyendo el suyo) serán elegibles.
    *   **Valor recomendado:** Seleccione todos los países de la UE a menos que tenga razones comerciales específicas para excluir algunos.
    *   **Escenario / ejemplo de comerciante:** Si solo desea ofrecer el 0% de IVA a empresas en Francia, Alemania y España, solo seleccionaría esos países.
*   **Seleccionar regla de impuestos:**
    *   **Qué hace este ajuste:** Especifica qué regla de impuestos de PrestaShop debe aplicarse cuando el IVA de un cliente se valida como 0%. Debe tener una regla de impuestos configurada en PrestaShop para el 0% de IVA.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando se selecciona una regla de impuestos del 0%:* El módulo aplicará esta regla a los pedidos elegibles.
        *   *Cuando se selecciona una regla de impuestos incorrecta:* Se podría aplicar la tasa de impuestos incorrecta, o el módulo podría no funcionar como se espera.
    *   **Valor recomendado:** Una regla de impuestos que haya creado en PrestaShop con una tasa de impuestos del 0%.
    *   **Escenario / ejemplo de comerciante:** Crearía una regla de impuestos llamada "IVA B2B UE 0%" con una tasa del 0% y la seleccionaría aquí.
*   **Deshabilitar módulo para idiomas seleccionados:**
    *   **Qué hace este ajuste:** Le permite deshabilitar la funcionalidad de validación de IVA para idiomas específicos en su tienda. Esto puede ser útil si opera en países no pertenecientes a la UE con diferentes regulaciones fiscales, pero aún utiliza la misma instancia de PrestaShop.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando se seleccionan idiomas:* El formulario y la lógica de validación de IVA no aparecerán ni se aplicarán para los clientes que naveguen en esos idiomas.
        *   *Cuando no se seleccionan idiomas:* El módulo estará activo para todos los idiomas.
    *   **Valor recomendado:** Déjelo vacío a menos que tenga requisitos fiscales específicos basados en el idioma.
    *   **Escenario / ejemplo de comerciante:** Si tiene una versión en inglés de su tienda dirigida tanto a clientes de la UE como de EE. UU., pero solo desea la validación de IVA para clientes de la UE, es posible que no la desactive. Sin embargo, si tiene una vista de tienda separada para un país no perteneciente a la UE (por ejemplo, "Japón"), podría deshabilitarla para el idioma japonés.

#### **Configuración de visualización (Visibilidad en el Front-Office)**

Estos ajustes controlan dónde aparecen el formulario de entrada de IVA y los mensajes de estado para sus clientes.

*   **Mostrar formulario de cambio de IVA en la barra de encabezado:**
    *   **Qué hace este ajuste:** Muestra un pequeño formulario o notificación en el área del encabezado de su tienda, pidiendo a los clientes que introduzcan su número de IVA.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* Aparece una barra en la parte superior de su sitio.
        *   *Cuando está deshabilitado:* No hay formulario/notificación de IVA en el encabezado.
    *   **Valor recomendado:** "Desactivado" a menos que desee una alta visibilidad para los clientes B2B.
    *   **Escenario / ejemplo de comerciante:** Podría habilitar esto si su tienda es principalmente B2B y desea informar inmediatamente a los clientes empresariales sobre el 0% de IVA.
*   **Mostrar formulario de cambio de IVA en displayCustomhtml1 (tema personalizado sp_topdeals):**
    *   **Qué hace este ajuste:** Este es un hook específico a menudo utilizado por temas personalizados (como 'sp_topdeals') para mostrar contenido personalizado. Habilitar esto colocará el formulario de IVA en esa área específica.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* El formulario de IVA aparece en el área del hook `displayCustomhtml1`.
        *   *Cuando está deshabilitado:* El formulario no aparecerá en esta área personalizada específica.
    *   **Valor recomendado:** "Desactivado" a menos que su tema utilice este hook y desee el formulario allí.
    *   **Escenario / ejemplo de comerciante:** Si su tema tiene un área de banner prominente en la parte superior y desea el formulario de IVA allí, habilitaría esto.
*   **Mostrar barra de estado de IVA para clientes registrados:**
    *   **Qué hace este ajuste:** Muestra una barra o mensaje a los clientes registrados, indicando su estado actual de IVA (por ejemplo, "Su IVA es válido, 0% aplicado").
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* Los clientes registrados ven su estado de IVA.
        *   *Cuando está deshabilitado:* No hay barra de estado de IVA específica para usuarios registrados.
    *   **Valor recomendado:** "Activado" para proporcionar claridad y tranquilidad a sus clientes B2B.
    *   **Escenario / ejemplo de comerciante:** Un cliente empresarial que regresa inicia sesión e inmediatamente ve "Su IVA es válido, 0% de IVA aplicado a su carrito", lo que mejora su experiencia de compra.
*   **Mostrar barra de IVA en el paso de información personal del pago:**
    *   **Qué hace este ajuste:** Muestra el campo de entrada de IVA y el estado de validación en el primer paso del proceso de pago (donde los clientes introducen su nombre, dirección, etc.). Esta es la ubicación más común y recomendada.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* El campo de IVA es visible e interactivo en el paso de información personal.
        *   *Cuando está deshabilitado:* El campo de IVA no aparecerá en este paso, lo que podría dificultar que los clientes apliquen el 0% de IVA.
    *   **Valor recomendado:** "Activado" (Altamente recomendado).
    *   **Escenario / ejemplo de comerciante:** Un cliente llega al pago, introduce la dirección de su empresa y luego introduce su número de IVA en el campo dedicado. El módulo lo valida y el precio se actualiza.
*   **Mostrar barra de IVA en el resumen del pago:**
    *   **Qué hace este ajuste:** Muestra el estado del IVA (por ejemplo, "IVA: 0%") en la página de resumen del pago, antes del pago final.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* Los clientes ven su estado de IVA en el resumen.
        *   *Cuando está deshabilitado:* No hay estado de IVA específico en el resumen.
    *   **Valor recomendado:** "Activado" para mayor transparencia.
    *   **Escenario / ejemplo de comerciante:** Un cliente revisa su pedido antes del pago y ve una confirmación clara de que se ha aplicado el 0% de IVA.
*   **Mostrar barra de IVA en el paso de pago:**
    *   **Qué hace este ajuste:** Muestra el estado del IVA en el paso final de pago del proceso de compra.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* Los clientes ven su estado de IVA en el paso de pago.
        *   *Cuando está deshabilitado:* No hay estado de IVA específico en el paso de pago.
    *   **Valor recomendado:** "Activado" para la confirmación final.
    *   **Escenario / ejemplo de comerciante:** Justo antes de hacer clic en "Pagar ahora", el cliente ve "Total: 100,00 € (IVA 0%)", confirmando la correcta aplicación de impuestos.
*   **Mostrar barra de cambio de IVA en la página de producto:**
    *   **Qué hace este ajuste:** Muestra un formulario de entrada de IVA o un mensaje de estado directamente en las páginas de productos individuales.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* Aparece un formulario/mensaje de IVA en las páginas de productos.
        *   *Cuando está deshabilitado:* No hay formulario/mensaje de IVA en las páginas de productos.
    *   **Valor recomendado:** "Desactivado" para evitar el desorden, a menos que tenga un fuerte enfoque B2B y desee mostrar los precios sin IVA temprano.
    *   **Escenario / ejemplo de comerciante:** Un cliente empresarial que navega por una página de producto puede introducir su número de IVA para ver inmediatamente el precio sin IVA, lo que les ayuda en sus decisiones de compra.
*   **Mostrar formulario de cambio de IVA en displayProductAdditionalInfo:**
    *   **Qué hace este ajuste:** Este es un hook estándar de PrestaShop en la página del producto, típicamente utilizado para información adicional. Habilitar esto colocará el formulario de IVA en esa área.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* El formulario de IVA aparece en el área del hook `displayProductAdditionalInfo`.
        *   *Cuando está deshabilitado:* El formulario no aparecerá en esta área específica.
    *   **Valor recomendado:** "Desactivado" a menos que lo desee específicamente allí.
    *   **Escenario / ejemplo de comerciante:** Similar al ajuste "Mostrar barra de cambio de IVA en la página de producto", pero apunta a un hook específico.
*   **Mostrar formulario de cambio de IVA en displayBanner:**
    *   **Qué hace este ajuste:** Muestra el formulario o el estado del IVA en el hook `displayBanner`, que a menudo se utiliza para banners superiores o mensajes promocionales.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* El formulario/estado del IVA aparece en el área del banner.
        *   *Cuando está deshabilitado:* No hay formulario/estado del IVA en el área del banner.
    *   **Valor recomendado:** "Desactivado" para evitar el desorden, a menos que tenga un diseño de banner específico para esto.
    *   **Escenario / ejemplo de comerciante:** Podría usar esto para mostrar un mensaje "¿Es usted una empresa? ¡Introduzca su IVA para un 0% de impuestos!" en un banner prominente.
*   **Mostrar formulario de cambio de IVA en displayCustomhtml1 (tema personalizado sp_topdeals):** (Duplicado, ya cubierto anteriormente)
*   **Mostrar barra de estado de IVA para clientes registrados:** (Duplicado, ya cubierto anteriormente)
*   **Mostrar barra de IVA en el paso de información personal del pago:** (Duplicado, ya cubierto anteriormente)
*   **Mostrar barra de IVA en el resumen del pago:** (Duplicado, ya cubierto anteriormente)
*   **Mostrar barra de IVA en el paso de pago:** (Duplicado, ya cubierto anteriormente)
*   **Nota de inversión del sujeto pasivo en la factura:**
    *   **Qué hace este ajuste:** Cuando se aplica el 0% de IVA debido a una verificación VIES válida, este ajuste garantiza que se añada automáticamente una nota de "Inversión del sujeto pasivo" a la factura del cliente. Este es un requisito legal para las ventas B2B intracomunitarias.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* Las facturas de pedidos con 0% de IVA incluirán la nota de inversión del sujeto pasivo.
        *   *Cuando está deshabilitado:* Las facturas no incluirán la nota, lo que podría llevar al incumplimiento.
    *   **Valor recomendado:** "Activado" (Altamente recomendado para el cumplimiento legal).
    *   **Escenario / ejemplo de comerciante:** Un cliente empresarial alemán compra en su tienda polaca con un número de IVA válido. La factura indica automáticamente "Inversión del sujeto pasivo - IVA no aplicable según el artículo 196 de la Directiva 2006/112/CE del Consejo".

#### **Configuración avanzada**

*   **Revalidar el número de IVA del cliente en cada pedido:**
    *   **Qué hace este ajuste:** Si está habilitado, el módulo volverá a verificar el número de IVA del cliente con VIES cada vez que realice un pedido, incluso si ya se validó previamente.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* Garantiza que el número de IVA esté siempre actualizado y sea válido, pero añade un ligero retraso al proceso de pago.
        *   *Cuando está deshabilitado:* Se basa en la validación inicial, que es más rápida pero podría pasar por alto cambios en el estado del IVA.
    *   **Valor recomendado:** "Activado" para la máxima conformidad y precisión.
    *   **Escenario / ejemplo de comerciante:** El número de IVA de un cliente empresarial podría dejar de ser válido con el tiempo. La revalidación garantiza que no aplique erróneamente el 0% de IVA a un número no válido.
*   **Prevenir la saturación de solicitudes VIES (bloquear durante X minutos):**
    *   **Qué hace este ajuste:** Si un cliente introduce repetidamente números de IVA no válidos, este ajuste bloquea temporalmente los intentos de validación posteriores durante un período específico para evitar el abuso o la sobrecarga del sistema VIES.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* Después de varios intentos fallidos, el cliente es bloqueado temporalmente para que no vuelva a intentarlo.
        *   *Cuando está deshabilitado:* No hay protección contra la saturación, lo que permite intentos ilimitados.
    *   **Valor recomendado:** "Activado" con un tiempo de bloqueo razonable (por ejemplo, 5-10 minutos).
    *   **Escenario / ejemplo de comerciante:** Un bot o un usuario malintencionado intenta adivinar números de IVA. Este ajuste evita que accedan continuamente a la API de VIES.
*   **Almacenar en caché los resultados de la validación VIES durante X horas:**
    *   **Qué hace este ajuste:** Almacena los resultados de las validaciones VIES exitosas durante un número específico de horas. Esto reduce el número de llamadas directas al sistema VIES, acelerando el proceso y reduciendo el uso de la API externa.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* Validación más rápida para clientes recurrentes o dentro del período de caché.
        *   *Cuando está deshabilitado:* Cada validación es una llamada VIES en vivo, lo que puede ser más lento.
    *   **Valor recomendado:** "Activado" con un tiempo de caché de 24-72 horas (por ejemplo, 48 horas).
    *   **Escenario / ejemplo de comerciante:** Un cliente valida su número de IVA. Si regresa a su sitio dentro de las 48 horas, el módulo utiliza el resultado almacenado en caché en lugar de realizar una nueva solicitud VIES.
*   **Volver a comprobar el estado del IVA del carrito cada X segundos:**
    *   **Qué hace este ajuste:** Define la frecuencia con la que el módulo vuelve a comprobar el estado del IVA del carrito en segundo plano, especialmente útil si los precios son dinámicos o si el cliente cambia su dirección/número de IVA durante el proceso de pago.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando se establece un valor bajo:* Actualizaciones más frecuentes, experiencia potencialmente más fluida pero mayor carga del servidor.
        *   *Cuando se establece un valor alto:* Actualizaciones menos frecuentes, podría requerir una actualización manual de la página para que se reflejen los cambios de IVA.
    *   **Valor recomendado:** 5-10 segundos.
    *   **Escenario / ejemplo de comerciante:** Un cliente introduce su número de IVA, y en 5 segundos, el total del carrito se actualiza para reflejar el 0% de IVA sin recargar la página.
*   **Habilitar la revalidación automática del número de IVA (Tarea programada - Cron Job):**
    *   **Qué hace este ajuste:** Activa una tarea en segundo plano (tarea programada) que revalida periódicamente todos los números de IVA de los clientes almacenados con VIES. Esto garantiza que incluso los números de IVA antiguos sigan siendo válidos.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando está habilitado:* Los números de IVA se verifican periódicamente para su validez, lo que garantiza el cumplimiento.
        *   *Cuando está deshabilitado:* Los números de IVA solo se verifican en el momento de la entrada o del pedido, lo que podría dar lugar a información desactualizada.
    *   **Valor recomendado:** "Activado" (Altamente recomendado para el cumplimiento a largo plazo).
    *   **Escenario / ejemplo de comerciante:** Un cliente realizó un pedido hace 6 meses con un número de IVA válido. La tarea programada lo vuelve a verificar y descubre que ahora no es válido, lo que le permite marcarlo para futuros pedidos.
*   **Intervalo de revalidación de la tarea programada (días):**
    *   **Qué hace este ajuste:** Establece la frecuencia con la que se ejecuta la tarea programada para revalidar los números de IVA.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando se establece un número bajo:* Revalidaciones más frecuentes, mayor precisión, pero más solicitudes VIES.
        *   *Cuando se establece un número alto:* Revalidaciones menos frecuentes, menor precisión, menos solicitudes VIES.
    *   **Valor recomendado:** 30-90 días (por ejemplo, 60 días).
    *   **Escenario / ejemplo de comerciante:** Establecerlo en 30 días significa que todos los números de IVA se vuelven a verificar una vez al mes.
*   **Clave API de VIES (Opcional):**
    *   **Qué hace este ajuste:** Le permite utilizar API de validación de IVA alternativas (como Apilayer, AbstractAPI, VATStack) en lugar del sistema VIES predeterminado. Estas a veces pueden ofrecer características más robustas u opciones de respaldo.
    *   **Efecto de cambiar este ajuste:**
        *   *Cuando se introduce una clave:* El módulo intentará utilizar la API de terceros especificada para la validación.
        *   *Cuando está vacío:* El módulo utiliza por defecto el sistema VIES oficial.
    *   **Valor recomendado:** Déjelo vacío a menos que experimente problemas con VIES o requiera características específicas de una API de terceros. Si utiliza una, introduzca la clave proporcionada por ese servicio.
    *   **Escenario / ejemplo de comerciante:** Si el sistema VIES está frecuentemente inactivo o lento, podría suscribirse al servicio de validación de IVA de Apilayer e introducir su clave API aquí como una alternativa fiable.

#### **Claves API (Opcional - para servicios alternativos de validación de IVA)**

*   **Clave API de Apilayer:**
    *   **Qué hace este ajuste:** Introduzca su clave API si se suscribe al servicio de validación de IVA de Apilayer.
    *   **Efecto de cambiar este ajuste:** Habilita la validación a través de Apilayer.
    *   **Valor recomendado:** Déjelo vacío a menos que tenga una cuenta de Apilayer.
*   **Clave API de AbstractAPI:**
    *   **Qué hace este ajuste:** Introduzca su clave API si se suscribe al servicio de validación de IVA de AbstractAPI.
    *   **Efecto de cambiar este ajuste:** Habilita la validación a través de AbstractAPI.
    *   **Valor recomendado:** Déjelo vacío a menos que tenga una cuenta de AbstractAPI.
*   **Clave API de VATStack:**
    *   **Qué hace este ajuste:** Introduzca su clave API si se suscribe al servicio de validación de IVA de VATStack.
    *   **Efecto de cambiar este ajuste:** Habilita la validación a través de VATStack.
    *   **Valor recomendado:** Déjelo vacío a menos que tenga una cuenta de VATStack.

#### **Tabla de referencia rápida de configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Config. Principal | Su país | País de su tienda | Define el país de su negocio para ventas intracomunitarias. |
| Config. Principal | Países elegibles | Todos los países de la UE | Selecciona los países de la UE donde se aplica el 0% de IVA. |
| Config. Principal | Seleccionar regla de impuestos | Su regla de impuestos del 0% | Especifica la regla de impuestos de PrestaShop para el 0% de IVA. |
| Config. Principal | Deshabilitar módulo para idiomas seleccionados | Vacío | Deshabilita el módulo para idiomas específicos. |
| Config. Principal | Mostrar formulario de cambio de IVA en la barra de encabezado | Desactivado | Muestra el formulario de IVA en el encabezado. |
| Config. Principal | Mostrar formulario de cambio de IVA en displayCustomhtml1 | Desactivado | Muestra el formulario de IVA en el hook del tema personalizado. |
| Config. Principal | Mostrar barra de estado de IVA para clientes registrados | Activado | Muestra el estado de IVA a los usuarios registrados. |
| Config. Principal | Mostrar barra de IVA en el paso de información personal del pago | Activado (Altamente recomendado) | Muestra el campo de IVA en el primer paso del pago. |
| Config. Principal | Mostrar barra de IVA en el resumen del pago | Activado | Muestra el estado de IVA en el resumen del pago. |
| Config. Principal | Mostrar barra de IVA en el paso de pago | Activado | Muestra el estado de IVA en el paso de pago. |
| Config. Principal | Mostrar barra de cambio de IVA en la página de producto | Desactivado | Muestra el formulario de IVA en las páginas de productos. |
| Config. Principal | Mostrar formulario de cambio de IVA en displayProductAdditionalInfo | Desactivado | Muestra el formulario de IVA en el hook de información adicional del producto. |
| Config. Principal | Mostrar formulario de cambio de IVA en displayBanner | Desactivado | Muestra el formulario de IVA en el hook del banner. |
| Config. Principal | Nota de inversión del sujeto pasivo en la factura | Activado (Altamente recomendado) | Añade la nota legal de "Inversión del sujeto pasivo" a las facturas. |
| Config. Principal | Revalidar el número de IVA del cliente en cada pedido | Activado | Vuelve a verificar el IVA para cada nuevo pedido. |
| Config. Principal | Prevenir la saturación de solicitudes VIES (bloquear durante X minutos) | Activado (5-10 minutos) | Bloquea los intentos repetidos de IVA no válidos. |
| Config. Principal | Almacenar en caché los resultados de la validación VIES durante X horas | Activado (24-72 horas) | Almacena en caché los resultados de VIES para acelerar la validación. |
| Config. Principal | Volver a comprobar el estado del IVA del carrito cada X segundos | 5-10 segundos | Frecuencia de actualización del estado del IVA del carrito. |
| Config. Principal | Habilitar la revalidación automática del número de IVA (Tarea programada - Cron Job) | Activado (Altamente recomendado) | Activa la revalidación en segundo plano de todos los números de IVA. |
| Config. Principal | Intervalo de revalidación de la tarea programada (días) | 30-90 días (por ejemplo, 60) | Frecuencia de revalidación de la tarea programada. |
| Config. Principal | Clave API de Apilayer | Vacío | Clave para el servicio de validación de IVA de Apilayer. |
| Config. Principal | Clave API de AbstractAPI | Vacío | Clave para el servicio de validación de IVA de AbstractAPI. |
| Config. Principal | Clave API de VATStack | Vacío | Clave para el servicio de validación de IVA de VATStack. |

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### **Auditoría de validación de IVA (Back Office > Clientes > Auditoría de validación de IVA)**

Esta sección dedicada le permite revisar y gestionar todos los intentos de validación de IVA realizados a través de su tienda.

*   **Nombre de la pantalla y ubicación del menú:** **Clientes > Auditoría de validación de IVA** (Este nuevo elemento de menú es añadido por el módulo).
*   **Acciones y configuraciones disponibles:**
    *   **Vista de cuadrícula / Gestión:** Esta pantalla presenta una tabla (cuadrícula) de todos los intentos de validación de IVA. Para cada entrada, normalmente verá:
        *   **Nombre del cliente:** El nombre del cliente asociado a la validación.
        *   **Número de IVA:** El número de IVA que se introdujo.
        *   **País:** El código de país asociado al número de IVA.
        *   **Estado de validación:** Si el número de IVA era "Válido", "No válido" o "Error" (por ejemplo, sistema VIES no disponible).
        *   **Fecha de validación:** Cuándo ocurrió el intento de validación.
        *   **ID de pedido:** Si la validación llevó a un pedido, el ID de pedido asociado.
        *   **Fuente:** Dónde tuvo lugar la validación (por ejemplo, "Pago", "Cuenta de cliente").
        *   **Detalles/Razón:** Más información sobre el resultado de la validación, especialmente para entradas no válidas.
    *   **Filtrado y clasificación:** Normalmente puede filtrar la lista por cliente, número de IVA, estado o rango de fechas para encontrar entradas específicas. La clasificación le permite organizar los datos.
    *   **Exportar:** El módulo puede ofrecer una opción para exportar este registro de auditoría, lo que es útil para la contabilidad y las auditorías fiscales.
*   **Efecto de los cambios:** Esta pantalla es principalmente para auditoría e informes. No puede cambiar directamente el estado del IVA de un cliente aquí, pero puede revisar el historial de validaciones. Estos datos son cruciales para demostrar el cumplimiento durante las inspecciones fiscales.
*   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Revise periódicamente este registro de auditoría, especialmente si observa discrepancias en la aplicación del IVA o recibe consultas de clientes sobre el IVA.
    2.  Busque los estados "No válido" o "Error" para identificar posibles problemas con la entrada del cliente o la disponibilidad del sistema VIES.
    3.  Utilice la función de exportación para proporcionar datos a su contable o a las autoridades fiscales si se le solicita.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Auditoría de validación de IVA | Vista de cuadrícula | N/A | Muestra un registro histórico de todos los intentos de validación de IVA. |
| Auditoría de validación de IVA | Filtros y clasificación | N/A | Ayuda a localizar entradas de validación específicas. |
| Auditoría de validación de IVA | Exportar datos | N/A | Permite exportar el registro de auditoría para fines de registro y fiscales. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis clientes están introduciendo números de IVA válidos, pero no se aplica el 0% de IVA.**
*   **R:**
    1.  **Verifique la configuración de "Su país":** Asegúrese de que esté configurado correctamente en el país de su tienda en la configuración del módulo.
    2.  **Verifique "Países elegibles":** Asegúrese de que el país del cliente esté seleccionado en la lista de países elegibles.
    3.  **Confirme "Seleccionar regla de impuestos":** Asegúrese de tener una regla de impuestos del 0% creada en PrestaShop (**Internacional > Impuestos > Reglas de impuestos**) y de que esté seleccionada correctamente en la configuración del módulo.
    4.  **Borrar caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché". A veces, la caché antigua puede impedir que se apliquen las nuevas configuraciones.
    5.  **Verifique la disponibilidad de VIES:** El sistema VIES a veces puede no estar disponible temporalmente. Puede verificar su estado en el sitio web oficial de la Comisión Europea.

**P2: El formulario de validación de IVA no aparece en mi página de pago.**
*   **R:**
    1.  **Verifique la configuración de visualización:** En la configuración del módulo, asegúrese de que "Mostrar barra de IVA en el paso de información personal del pago" (y otras opciones de visualización relevantes) esté configurado en "Activado".
    2.  **Compatibilidad del tema:** Si está utilizando un tema altamente personalizado, podría anular los hooks estándar de PrestaShop. Verifique si su tema tiene áreas específicas para `displayProductAdditionalInfo`, `displayCustomhtml1` u otros hooks donde haya intentado colocar el formulario. Es posible que deba consultar a su desarrollador de temas.
    3.  **Conflictos de módulos:** Deshabilite temporalmente otros módulos relacionados con el pago para ver si hay un conflicto.

**P3: Estoy viendo mensajes de "Error" o "VIES no disponible" durante la validación.**
*   **A:**
    1.  **Estado del sistema VIES:** El sistema VIES puede experimentar tiempos de inactividad. Verifique el sitio web oficial de VIES para conocer el estado actual.
    2.  **Extensión cURL:** Asegúrese de que su proveedor de alojamiento tenga habilitada la extensión PHP `cURL`. Esto es esencial para que el módulo se comunique con API externas como VIES. Póngase en contacto con su host si no está seguro.
    3.  **Cortafuegos/Seguridad:** El cortafuegos o la configuración de seguridad de su servidor podrían estar bloqueando las conexiones salientes al servidor VIES. De nuevo, póngase en contacto con su proveedor de alojamiento.
    4.  **Claves API:** Si está intentando utilizar una API de terceros (Apilayer, AbstractAPI, VATStack), asegúrese de que la clave API esté correctamente introducida y activa con ese servicio.

**P4: ¿Cómo me aseguro de que la tarea programada para la revalidación se está ejecutando?**
*   **R:**
    1.  **Habilitar tarea programada:** En la configuración del módulo, asegúrese de que "Habilitar la revalidación automática del número de IVA (Tarea programada - Cron Job)" esté "Activado".
    2.  **Módulo Cron de PrestaShop:** Necesita un módulo de tarea programada de PrestaShop separado (por ejemplo, "Gestor de tareas cron" de PrestaShop) instalado y configurado para activar periódicamente la tarea cron del módulo.
    3.  **Cron de alojamiento:** Alternativamente, puede configurar una tarea programada a nivel de servidor (a través de cPanel, Plesk o SSH) para llamar a la URL de la tarea programada del módulo. La configuración del módulo suele proporcionar la URL exacta a utilizar.
    4.  **Verificar registro de auditoría:** Después de que la tarea programada debería haberse ejecutado, verifique la pantalla "Auditoría de validación de IVA" en el Back Office. Debería ver nuevas entradas de validación con una fuente "Cron".

**P5: ¿Por qué algunos países de la UE no aparecen en la lista de "Países elegibles"?**
*   **R:** El módulo se basa en la lista de países de PrestaShop. Asegúrese de que todos los países de la UE deseados estén habilitados en su tienda PrestaShop (**Internacional > Ubicaciones > Países**) y que estén marcados como "Es un país de la UE" y "Contiene estados" (si corresponde).

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Validar IVA en VIES y establecer 0% IVA", diseñado para desarrolladores y webmasters.

### 4.1 Resumen de la arquitectura

El módulo sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, aprovechando en gran medida los hooks para la integración en el front y back office. Introduce varias clases personalizadas para la lógica de negocio, la interacción con la API y la gestión de datos. Los componentes clave incluyen:

*   **Clase principal del módulo (`eurovat.php`):** Gestiona la instalación, desinstalación, registro de hooks y el formulario de configuración principal (`getContent()`).
*   **Controladores frontales:** Gestionan las solicitudes AJAX para la validación de IVA y el envío de formularios.
*   **Controladores de administración:** Proporcionan interfaces dedicadas para la auditoría de validación de IVA.
*   **Clases principales:** Encapsulan la lógica de negocio para la interacción con VIES, la gestión de impuestos, el análisis y la persistencia de datos (a menudo extendiendo `ObjectModel` o utilizando un patrón de repositorio).
*   **Plantillas:** Plantillas Smarty para renderizar formularios de front-office, configuración de back-office y vistas de auditoría.
*   **Hooks:** Uso extensivo de hooks para inyectar funcionalidad en varios puntos del ciclo de vida de PrestaShop (por ejemplo, página de producto, pago, procesamiento de pedidos, vista de cliente de administración).

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

*   `controllers/front/cron.php`
    *   **Nombre de la clase:** `EurovatCronModuleFrontController` (extiende `ModuleFrontController`)
    *   **Responsabilidad:** Gestiona la ejecución de la tarea programada del módulo. Este controlador suele ser llamado por un servicio de tarea programada externo (por ejemplo, la tarea programada del servidor o el módulo `Cron tasks manager` de PrestaShop) para activar tareas en segundo plano como la revalidación de números de IVA. Procesa el hook `ActionCronJob`.
*   `controllers/front/form.php`
    *   **Nombre de la clase:** `EurovatFormModuleFrontController` (extiende `ModuleFrontController`)
    *   **Responsabilidad:** Probablemente gestiona la visualización y el envío del formulario de entrada de IVA en varios contextos del front-office (por ejemplo, página de producto, bloques HTML personalizados). Podría renderizar `views/templates/front/form.tpl`.
*   `controllers/front/index.php`
    *   **Nombre de la clase:** `EurovatIndexModuleFrontController` (extiende `ModuleFrontController`)
    *   **Responsabilidad:** Un controlador frontal genérico, potencialmente utilizado para lógica de reserva o visualización simple. A menudo, `index.php` en un directorio de controladores sirve como marcador de posición o como base para otros controladores.
*   `controllers/front/validate.php`
    *   **Nombre de la clase:** `EurovatValidateModuleFrontController` (extiende `ModuleFrontController`)
    *   **Responsabilidad:** El punto final AJAX principal para la validación de números de IVA en tiempo real. Recibe el número de IVA y los datos del país, interactúa con el cliente VIES y devuelve una respuesta JSON que indica la validez y, potencialmente, actualiza el estado fiscal del carrito.

#### Controladores de administración de Back-Office

*   `controllers/admin/AdminEurovatVatValidationAuditController.php`
    *   **Nombre de la clase:** `AdminEurovatVatValidationAuditController` (extiende `ModuleAdminController`)
    *   **Nombre de la pestaña:** "Auditoría de validación de IVA" (en el menú Clientes)
    *   **Entidad gestionada:** `EurovatValidation` (tabla personalizada `ps_eurovat_validation`)
    *   **Responsabilidad:** Proporciona la interfaz administrativa para ver, filtrar y gestionar el registro de auditoría de todos los intentos de validación de IVA. Utiliza los componentes `HelperList` o `Grid` de PrestaShop para mostrar los datos de la tabla `ps_eurovat_validation`.
*   `controllers/admin/index.php`
    *   **Nombre de la clase:** `EurovatIndexAdminController` (extiende `ModuleAdminController`)
    *   **Responsabilidad:** Similar al `index.php` del front-office, este es probablemente un marcador de posición o un controlador base. Podría redirigir a la configuración principal o al controlador de auditoría.

### 4.3 Clases y modelos principales (`classes/`)

*   `classes/EurovatAlertService.php`
    *   **Responsabilidad:** Gestiona y muestra alertas o notificaciones dentro del módulo, posiblemente relacionadas con el estado de VIES, problemas de claves API o problemas de configuración.
*   `classes/EurovatAlertsHelper.php`
    *   **Responsabilidad:** Una clase de ayuda para `EurovatAlertService`, que proporciona funciones de utilidad para la gestión de alertas.
*   `classes/EurovatAnalyticsService.php`
    *   **Responsabilidad:** Recopila y procesa datos relacionados con la validación de IVA, como tasas de éxito, tipos de error y uso de la API, potencialmente para su visualización en un widget del panel de control.
*   `classes/EurovatApiUsageHelper.php`
    *   **Responsabilidad:** Rastrea y gestiona el uso de API de validación de IVA externas (VIES, Apilayer, etc.), implementando potencialmente la limitación de velocidad o la supervisión.
*   `classes/EurovatAuditHelper.php`
    *   **Responsabilidad:** Ayuda a `AdminEurovatVatValidationAuditController` a gestionar y consultar la tabla `ps_eurovat_validation`.
*   `classes/EurovatConfiguration.php`
    *   **Responsabilidad:** Una clase estática o singleton para centralizar el acceso a los valores de configuración del módulo (`Configuration::get('EUROVAT_...')`). Proporciona una forma más limpia de recuperar la configuración.
*   `classes/EurovatCronHelper.php`
    *   **Responsabilidad:** Contiene la lógica ejecutada por la tarea programada, como la iteración a través de los números de IVA de los clientes y el inicio de la revalidación.
*   `classes/EurovatErrorClassifier.php`
    *   **Responsabilidad:** Clasifica y proporciona mensajes fáciles de usar para diferentes tipos de errores de validación de IVA (por ejemplo, formato no válido, VIES no disponible, falta de coincidencia de país).
*   `classes/EurovatExportService.php`
    *   **Responsabilidad:** Gestiona la exportación de datos de auditoría de validación de IVA, probablemente en formato CSV o Excel.
*   `classes/EurovatOrderProofHelper.php`
    *   **Responsabilidad:** Recopila y prepara datos relacionados con la validación de IVA para un pedido específico, utilizados para generar pruebas de aplicación del 0% de IVA.
*   `classes/EurovatOrderTaxNormalizer.php`
    *   **Responsabilidad:** Ajusta los detalles de los impuestos del pedido cuando se aplica el 0% de IVA, garantizando la coherencia en el carrito, el pedido y la factura.
*   `classes/EurovatProofPackService.php`
    *   **Responsabilidad:** Potencialmente crea un "paquete de prueba" (por ejemplo, un documento PDF) que contiene todas las pruebas necesarias para una transacción con 0% de IVA.
*   `classes/EurovatTaxManager.php`
    *   **Responsabilidad:** La clase central para aplicar y gestionar los cambios de impuestos basados en los resultados de la validación de IVA, interactuando con el sistema fiscal de PrestaShop.
*   `classes/EurovatTaxService.php`
    *   **Responsabilidad:** Proporciona métodos de utilidad relacionados con los cálculos y la aplicación de impuestos dentro del módulo.
*   `classes/EurovatValidationRepository.php`
    *   **Con qué tabla de base de datos interactúa:** `ps_eurovat_validation`
    *   **Si extiende `ObjectModel`:** Probablemente no directamente, pero gestiona objetos `EurovatValidation` o consultas de base de datos sin procesar.
    *   **Métodos públicos clave y lógica de negocio encapsulada:** Operaciones CRUD para registros de validación de IVA, consulta del historial de validación, almacenamiento de resultados de validación.
*   `classes/EurovatViesClient.php`
    *   **Responsabilidad:** La interfaz principal para comunicarse con el sistema VIES (o API alternativas como Apilayer, AbstractAPI, VATStack). Gestiona las solicitudes, respuestas y el manejo de errores de la API.
*   `classes/index.php`
    *   **Responsabilidad:** Un marcador de posición de seguridad para evitar la lista de directorios.

### 4.4 Activos JavaScript (`views/js/`)

*   `eurovat/views/js/adminEurovatAlerts.js`
    *   **Alcance:** Back-office
    *   **Descripción:** Gestiona la visualización y la interacción con las alertas en el panel de administración, posiblemente actualizaciones dinámicas o mensajes que se pueden descartar.
*   `eurovat/views/js/adminEurovatCountries.js`
    *   **Alcance:** Back-office
    *   **Descripción:** Gestiona la interfaz de selección de país en la configuración del módulo, posiblemente con funcionalidad de selección múltiple o filtrado dinámico.
*   `eurovat/views/js/adminEurovatCron.js`
    *   **Alcance:** Back-office
    *   **Descripción:** Proporciona lógica de interfaz de usuario para la configuración de la tarea programada, mostrando potencialmente los últimos tiempos de ejecución, la próxima ejecución programada u opciones de activación manual.
*   `eurovat/views/js/adminEurovatDashboard.js`
    *   **Alcance:** Back-office
    *   **Descripción:** Impulsa el widget del panel de control (si lo hay) que muestra análisis o métricas clave relacionadas con la validación de IVA. Utiliza AJAX para obtener datos y, potencialmente, bibliotecas de gráficos.
*   `eurovat/views/js/adminEurovatTooltips.js`
    *   **Alcance:** Back-office
    *   **Descripción:** Inicializa y gestiona los tooltips para las opciones de configuración en el panel de administración, proporcionando un contexto útil.
*   `eurovat/views/js/eurovat.js`
    *   **Alcance:** Front-office
    *   **Descripción:** El JavaScript principal del front-office.
        *   **Detectores de eventos:** Se vincula a los eventos de entrada en el campo del número de IVA (por ejemplo, `keyup`, `change`), envíos de formularios y, potencialmente, `prestashop.on('updateCart')` o eventos similares.
        *   **Manipulación del DOM:** Muestra dinámicamente mensajes de estado de validación (válido/no válido), actualiza los totales del carrito, muestra/oculta elementos según el estado del IVA.
        *   **Llamadas AJAX:** Envía el número de IVA y los datos del país a `controllers/front/validate.php` para la validación en tiempo real.
        *   **Otros:** Implementa el intervalo de "volver a comprobar el estado del IVA del carrito", la lógica de protección contra la saturación.
*   `eurovat/views/js/eurovatBoMockConsole.js`
    *   **Alcance:** Back-office (desarrollo/depuración)
    *   **Descripción:** Probablemente una utilidad para simular la salida de la consola o proporcionar capacidades de depuración mejoradas dentro del Back Office de PrestaShop, no utilizada normalmente en producción.

### 4.5 Hojas de estilo CSS (`views/css/`)

*   `eurovat/views/css/admin_eurovat.css`
    *   **Alcance:** Estilo del formulario de administración del Back-office.
    *   **Principales componentes y contenedores de la interfaz de usuario que estiliza:** Elementos de la página de configuración, tabla de la lista de auditoría, widgets del panel de control, alertas y tooltips dentro de la interfaz de administración del módulo.
    *   **Selectores de clase CSS clave que los desarrolladores pueden anular:** `.eurovat-admin-config`, `.eurovat-alert`, `.eurovat-dashboard-widget`, `.eurovat-audit-table`.
*   `eurovat/views/css/eurovat.css`
    *   **Alcance:** Estilo del cliente del Front-office.
    *   **Principales componentes y contenedores de la interfaz de usuario que estiliza:** Campos de entrada de IVA, mensajes de estado de validación (éxito/error), barras de estado de IVA en el encabezado/página de producto/pago, notas de inversión del sujeto pasivo.
    *   **Selectores de clase CSS clave que los desarrolladores pueden anular:** `.eurovat-vat-form`, `.eurovat-status-message.valid`, `.eurovat-status-message.invalid`, `.eurovat-header-bar`, `.eurovat-product-vat-info`, `.eurovat-checkout-vat-status`.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

*   `eurovat/views/templates/hook/adminDashboardWidget.tpl`
    *   **Hook:** Potencialmente `displayAdminHomeQuickview` o un hook de panel de control personalizado.
    *   **Salidas:** Un widget para el panel de control de administración de PrestaShop, que muestra análisis o estadísticas rápidas relacionadas con la validación de IVA.
*   `eurovat/views/templates/hook/adminOrderProofPack.tpl`
    *   **Hook:** `displayAdminOrder` o `displayAdminOrderTabContent` (en la página de vista de pedido).
    *   **Salidas:** Un bloque o pestaña dentro de la página de detalles del pedido de administración, que permite a los administradores ver o generar documentos de prueba de IVA para un pedido específico.
*   `eurovat/views/templates/hook/customerHistory.tpl`
    *   **Hook:** `displayCustomerAccount` o `displayMyAccountBlock`.
    *   **Salidas:** Información sobre el historial de validación de IVA del cliente o el estado actual dentro de su área de cuenta personal.
*   `eurovat/views/templates/hook/displayBanner.tpl`
    *   **Hook:** `displayBanner` (o un hook de banner global similar).
    *   **Salidas:** El formulario de entrada de IVA o un mensaje promocional sobre el 0% de IVA, que normalmente se muestra en la parte superior de la tienda.

#### Plantillas de administración (`views/templates/admin/`)

*   `eurovat/views/templates/admin/alerts.tpl`
    *   **Salidas:** Estructura HTML para mostrar varias alertas y notificaciones en el Back Office.
*   `eurovat/views/templates/admin/audit.tpl`
    *   **Salidas:** La plantilla principal para `AdminEurovatVatValidationAuditController`, que renderiza la lista de auditoría de validación de IVA.
*   `eurovat/views/templates/admin/configure.tpl`
    *   **Salidas:** El formulario de configuración principal para el módulo, renderizado por `getContent()` en `eurovat.php`. Contiene todos los ajustes descritos en la sección 4.1.
*   `eurovat/views/templates/admin/countriesSelector.tpl`
    *   **Salidas:** Una plantilla reutilizable para la interfaz de selección de país dentro de la configuración.
*   `eurovat/views/templates/admin/cron.tpl`
    *   **Salidas:** La sección de configuración relacionada con los ajustes de la tarea programada, incluyendo el intervalo y la activación.
*   `eurovat/views/templates/admin/dashboard.tpl`
    *   **Salidas:** La vista completa del panel de control, que potencialmente integra `adminDashboardWidget.tpl` y otros análisis.
*   `eurovat/views/templates/admin/hooksRepair.tpl`
    *   **Salidas:** Una plantilla de utilidad, posiblemente para diagnosticar y reparar hooks faltantes o registrados incorrectamente.
*   `eurovat/views/templates/admin/proof_pack_view.tpl`
    *   **Salidas:** Una vista detallada para un paquete de prueba de IVA, probablemente dentro de la página de detalles del pedido.
*   `eurovat/views/templates/admin/vat_audit_list_settings.tpl`
    *   **Salidas:** Ajustes o filtros específicos para la visualización de la lista de auditoría de IVA.
*   `eurovat/views/templates/admin/vat_audit_tabs.tpl`
    *   **Salidas:** Navegación por pestañas para la sección de auditoría de IVA, si hay varias subsecciones (por ejemplo, registro de auditoría, análisis).

#### Plantillas de front-office (`views/templates/front/`)

*   `eurovat/views/templates/front/form.tpl`
    *   **Salidas:** La estructura HTML principal para el formulario de entrada del número de IVA, utilizado en varios hooks del front-office (página de producto, pago, encabezado).

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

*   `ps_eurovat_validation`
    *   **Propósito:** Almacena un registro histórico de todos los intentos de validación de IVA.
    *   **Campos clave (esperados):**
        *   `id_eurovat_validation` (Clave primaria)
        *   `id_customer` (Clave externa a `ps_customer`)
        *   `id_cart` (Clave externa a `ps_cart`)
        *   `id_order` (Clave externa a `ps_order`)
        *   `vat_number` (El número de IVA introducido)
        *   `country_code` (El código de país asociado al número de IVA)
        *   `validation_status` (por ejemplo, 'valid', 'invalid', 'error')
        *   `validation_response` (Respuesta sin procesar de VIES/API)
        *   `validation_date` (Marca de tiempo de la validación)
        *   `source` (por ejemplo, 'checkout', 'customer_account', 'cron')
        *   `ip_address` (Dirección IP del usuario que realizó la validación)

*   `ps_configuration`
    *   **Propósito:** Almacena todos los ajustes de configuración del módulo.
    *   **Claves de configuración clave:**
        *   `EUROVAT_YOUR_COUNTRY`
        *   `EUROVAT_ELIGIBLE_COUNTRIES`
        *   `EUROVAT_TAX_RULE`
        *   `EUROVAT_DISPLAY_HEADER`
        *   `EUROVAT_DISPLAY_CUSTOMHTML1`
        *   `EUROVAT_DISPLAY_LOGGED_STATUS`
        *   `EUROVAT_DISPLAY_CHECKOUT_PERSONAL`
        *   `EUROVAT_DISPLAY_CHECKOUT_SUMMARY`
        *   `EUROVAT_DISPLAY_CHECKOUT_PAYMENT`
        *   `EUROVAT_DISPLAY_PRODUCT_PAGE`
        *   `EUROVAT_REVERSE_CHARGE_NOTE`
        *   `EUROVAT_REVALIDATE_ON_ORDER`
        *   `EUROVAT_FLOOD_OFF_MINUTES`
        *   `EUROVAT_CACHE_TTL_HOURS`
        *   `EUROVAT_CART_RECHECK_INTERVAL`
        *   `EUROVAT_CRON_REVALIDATE_ENABLED`
        *   `EUROVAT_CRON_INTERVAL_DAYS`
        *   `EUROVAT_APILAYER_KEY`
        *   `EUROVAT_ABSTRACTAPI_KEY`
        *   `EUROVAT_VATSTACK_KEY`
        *   `EUROVAT_DISABLED_LANGS`

#### Tabla de hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyectar CSS/JS, o mostrar una barra de estado de IVA global. |
| `displayProductAdditionalInfo` | En la página del producto, normalmente debajo de la descripción del producto. | Mostrar formulario de entrada de IVA o estado en las páginas de productos. |
| `displayCustomhtml1` | Hook personalizado, a menudo en la sección superior del tema (por ejemplo, `sp_topdeals`). | Mostrar formulario de entrada de IVA en áreas específicas del tema. |
| `displayPaymentTop` | En la parte superior del paso de pago en el proceso de compra. | Mostrar estado o formulario de IVA antes del pago. |
| `displayBanner` | En un área de banner, normalmente en la parte superior del sitio. | Mostrar formulario de entrada de IVA o mensaje promocional. |
| `displayAdminCustomers` | En la lista de clientes o en la página de detalles del cliente en el BO. | Añadir información o acciones relacionadas con el IVA para los clientes. |
| `ActionDispatcher` | Antes de que se envíe un controlador. | Modificar el enrutamiento o el contexto según el estado del IVA. |
| `ActionGetProductPropertiesAfter` | Después de recuperar las propiedades del producto. | Ajustar los precios de los productos según el estado del IVA del cliente. |
| `ActionProductPriceCalculation` | Durante el cálculo del precio del producto. | Aplicar 0% de IVA a los precios de los productos si es elegible. |
| `ActionBeforeValidateOrder` | Justo antes de que se valide un pedido. | Realizar la validación final del IVA, ajustar los impuestos del pedido. |
| `ActionCronJob` | Activado por el módulo cron de PrestaShop. | Ejecutar tareas en segundo plano como la revalidación de IVA. |
| `ActionObjectAddressUpdateAfter` | Después de que se actualiza un objeto de dirección (por ejemplo, en la cuenta del cliente). | Revalidar el IVA si cambian los detalles de la dirección. |
| `ActionTaxManager` | Cuando se gestionan o aplican las reglas fiscales. | Interceptar y modificar la aplicación de impuestos según la validación del IVA. |
| `ActionPresentCart` | Antes de que se muestre el carrito. | Actualizar los totales del carrito y mostrar el estado del IVA. |
| `ActionFilterDeliveryOptionList` | Filtra las opciones de entrega disponibles. | Potencialmente ajustar los costos de entrega según el estado del IVA (menos común). |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo se dedica a garantizar que el módulo funcione de manera óptima y siga siendo compatible con las versiones más recientes de PrestaShop.

*   **Historial de pedidos y descargas de MyPresta.eu:** [https://mypresta.eu/my-account/orders/](https://mypresta.eu/my-account/orders/)
*   **Soporte de MyPresta.eu:** [https://mypresta.eu/contact](https://mypresta.eu/contact)

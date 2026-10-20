---
title: "Perfect Money - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Perfect Money para PrestaShop de MyPresta.eu."
sidebar:
  label: "Perfect Money - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Perfect Money en MyPresta.eu](https://mypresta.eu/modules/payment-process/perfect-money.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/perfect-money/)
>
> ---


# Perfect Money

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 1.6.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una comunicación segura con la pasarela de pago, y casi siempre están disponibles en entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Perfect Money)

Esta es la pantalla de configuración principal para el módulo Perfect Money, donde introducirá los detalles de su cuenta Perfect Money y configurará cómo aparece y funciona el método de pago en su tienda.

#### **Configuración de la Cuenta Perfect Money**

-   **Qué hace este ajuste:** Estos campos son cruciales para conectar su tienda PrestaShop a su cuenta de comerciante de Perfect Money. Le indican al módulo a qué cuenta de Perfect Money enviar los pagos y cómo verificar las transacciones.
-   **Efecto de cambiar este ajuste:** Los valores incorrectos impedirán que los clientes realicen pagos, o los pagos podrían no atribuirse correctamente a su cuenta.
    *   *Cuando está configurado correctamente:* Los pagos se procesarán con éxito a través de su cuenta Perfect Money.
    *   *Cuando está configurado incorrectamente:* Los pagos fallarán o los clientes encontrarán errores durante el proceso de compra.
-   **Valor recomendado:** Introduzca los detalles exactos proporcionados por su cuenta de comerciante de Perfect Money.
-   **Escenario / ejemplo de comerciante:** Ha registrado una cuenta de comerciante con Perfect Money. Le proporcionan un "ID de Cuenta Perfect Money" (por ejemplo, U1234567) y un "Nombre de Cuenta Perfect Money" (por ejemplo, PagosDeMiTienda). También configura una "Frase de Contraseña Alternativa de Perfect Money" dentro de la configuración de su cuenta Perfect Money para una seguridad mejorada. Debe introducir estos valores exactos aquí.

#### **Configuración de Visualización de Pago**

-   **Qué hace este ajuste:** Esta sección controla cómo se presenta la opción de pago Perfect Money a sus clientes durante el proceso de compra.
-   **Efecto de cambiar este ajuste:**
    *   *Cuando está habilitado:* Los clientes verán la opción Perfect Money y podrán elegirla para el pago.
    *   *Cuando está deshabilitado:* Perfect Money no aparecerá como opción de pago.
-   **Valor recomendado:** "SÍ" (Habilitado) si desea ofrecer Perfect Money como método de pago.
-   **Escenario / ejemplo de comerciante:** Desea ofrecer Perfect Money como opción de pago. Lo habilita. Si desea deshabilitarlo temporalmente por mantenimiento o si ya no desea aceptar Perfect Money, lo configuraría en "NO".

#### **Configuración de Estado del Pedido**

-   **Qué hace este ajuste:** Estos ajustes determinan el estado que tendrá un pedido en el back office de su PrestaShop después de que un cliente complete un pago a través de Perfect Money.
-   **Efecto de cambiar este ajuste:**
    *   *Cuando se establece en "Pago aceptado":* Los pedidos pagados a través de Perfect Money se marcarán automáticamente como "Pago aceptado" en el back office de su PrestaShop, indicando una transacción exitosa.
    *   *Cuando se establece en "Error de pago":* Si un pago falla o ocurre un problema, el pedido se marcará con este estado.
-   **Valor recomendado:**
    *   **Estado del pedido para un pago exitoso:** "Pago aceptado" (o un estado similar que haya configurado para pagos exitosos).
    *   **Estado del pedido para un error de pago:** "Error de pago" (o un estado similar para pagos fallidos).
-   **Escenario / ejemplo de comerciante:** Un cliente paga con éxito con Perfect Money. Desea identificar rápidamente estos pedidos como listos para su procesamiento. Al establecer el "Estado del pedido para un pago exitoso" en "Pago aceptado", su equipo sabe inmediatamente que el pago se ha liquidado. Si un cliente intenta pagar pero la transacción falla, el pedido se marcará como "Error de pago", lo que le permitirá hacer un seguimiento o que el cliente lo intente de nuevo.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | ID de Cuenta Perfect Money | Su ID de Cuenta Perfect Money (ej. U1234567) | Identifica su cuenta de comerciante Perfect Money para recibir pagos. **CRÍTICO para el procesamiento de pagos.** |
| Configuración del Módulo | Nombre de Cuenta Perfect Money | Su Nombre de Cuenta Perfect Money | El nombre asociado a su cuenta Perfect Money. |
| Configuración del Módulo | Frase de Contraseña Alternativa de Perfect Money | Su Frase de Contraseña Alternativa de Perfect Money | Clave de seguridad para verificar transacciones. Configúrela en su cuenta Perfect Money. **CRÍTICO para la seguridad.** |
| Configuración del Módulo | Habilitar Pago Perfect Money | SÍ | Alterna la visibilidad de Perfect Money como opción de pago en su página de pago. |
| Configuración del Módulo | Estado del pedido para un pago exitoso | Pago aceptado | El estado de pedido de PrestaShop asignado a los pedidos pagados con éxito a través de Perfect Money. |
| Configuración del Módulo | Estado del pedido para un error de pago | Error de pago | El estado de pedido de PrestaShop asignado a los pedidos donde el pago de Perfect Money falló. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Mis clientes ven un error al intentar pagar con Perfect Money.**
R:

-   **Verifique la Configuración de su Cuenta Perfect Money:** Vuelva a comprobar que su "ID de Cuenta Perfect Money", "Nombre de Cuenta Perfect Money" y "Frase de Contraseña Alternativa de Perfect Money" se introducen *exactamente* como aparecen en su cuenta de comerciante de Perfect Money. Incluso un pequeño error tipográfico puede causar errores.
-   **Verifique el Estado de la Cuenta Perfect Money:** Inicie sesión directamente en su cuenta Perfect Money para asegurarse de que está activa, en buen estado y configurada para recibir pagos.
-   **Revise los Registros de Errores de PrestaShop:** En el back office de su PrestaShop, navegue a **Parámetros Avanzados > Registros** para ver si se están registrando errores específicos relacionados con el módulo Perfect Money.

**P: Los pedidos no se marcan como "Pago aceptado" después de un pago exitoso con Perfect Money.**
R:

-   **Verifique la Configuración del Estado del Pedido:** Vaya a la configuración del módulo y asegúrese de que "Estado del pedido para un pago exitoso" esté configurado en el estado correcto (por ejemplo, "Pago aceptado").
-   **IPN/Callback de Perfect Money:** Asegúrese de que su cuenta Perfect Money esté configurada correctamente para enviar Notificaciones de Pago Instantáneas (IPN) o callbacks a su tienda PrestaShop. El módulo se basa en estas notificaciones para actualizar los estados de los pedidos. Aunque el módulo gestiona la URL, a veces la configuración de la cuenta Perfect Money puede interferir.

**P: Perfect Money no aparece como opción de pago en mi página de pago.**
R:

-   **Módulo Habilitado:** En la configuración del módulo, asegúrese de que "Habilitar Pago Perfect Money" esté configurado en "SÍ".
-   **Módulo Instalado:** Verifique que el módulo esté correctamente instalado y habilitado en **Módulos > Gestor de Módulos**.
-   **Caché:** Borre la caché de su PrestaShop (en **Parámetros Avanzados > Rendimiento**) y la caché de su navegador. A veces, los datos antiguos en caché pueden impedir que aparezcan nuevas opciones de pago.
-   **Compatibilidad con el Tema:** Aunque el módulo está diseñado para ser compatible, los temas muy personalizados pueden requerir ocasionalmente pequeños ajustes. Si sospecha un conflicto con el tema, intente cambiar temporalmente al tema predeterminado de PrestaShop para ver si aparece la opción.

**P: ¿Puedo personalizar el logotipo o el texto de Perfect Money en la página de pago?**
R: El módulo utiliza una plantilla estándar para mostrar la opción de pago. Normalmente puede personalizar el texto yendo a **Internacional > Traducciones** en el back office de su PrestaShop, seleccionando "Traducciones de módulos instalados", eligiendo su tema y luego buscando el módulo "Perfect Money". Para cambios de logotipo, necesitaría modificar el archivo de plantilla del módulo (`perfectmoney.tpl`) o usar anulaciones de CSS en su tema.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una visión técnica detallada del módulo Perfect Money para desarrolladores y webmasters.

### 4.1 Visión General de la Arquitectura

El módulo Perfect Money sigue la arquitectura estándar de módulos de PrestaShop, utilizando principalmente una clase de módulo principal (`PerfectMoney`) para la instalación, desinstalación y configuración, y clases `ModuleFrontController` para manejar la redirección de pago y los procesos de validación. Se integra con la pasarela de pago Perfect Money utilizando un modelo de comunicación de servidor a servidor (IPN/callback) para confirmar transacciones y actualizar los estados de los pedidos.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

Estos controladores manejan los aspectos orientados al cliente del proceso de pago, incluida la redirección a Perfect Money y la gestión de la devolución de llamada después del pago.

-   **`perfectmoney/controllers/front/index.php`**

    -   **Nombre de la Clase**: `PerfectMoneyIndexModuleFrontController`
    -   **Clase Padre**: `ModuleFrontController`
    -   **Responsabilidad**: Este controlador es típicamente responsable de iniciar el proceso de pago. Cuando un cliente selecciona Perfect Money y confirma su pedido, este controlador prepara los parámetros de la solicitud de pago (ID de comerciante, cantidad, moneda, descripción del pedido, URLs de retorno) y redirige el navegador del cliente a la pasarela de pago de Perfect Money. Recopila los detalles necesarios del pedido del carrito y construye el formulario de pago.
-   **`perfectmoney/controllers/front/validation.php`**

    -   **Nombre de la Clase**: `PerfectMoneyValidationModuleFrontController`
    -   **Clase Padre**: `ModuleFrontController`
    -   **Responsabilidad**: Este es el controlador crucial que maneja la devolución de llamada (Notificación de Pago Instantánea - IPN) de Perfect Money después de que se ha procesado un pago.
        -   Recibe datos POST de Perfect Money que contienen detalles de la transacción y un hash de seguridad.
        -   Verifica la integridad y autenticidad de la notificación de pago utilizando la Frase de Contraseña Alternativa configurada.
        -   Si el pago es válido y exitoso, actualiza el estado del pedido de PrestaShop (por ejemplo, a "Pago aceptado"), crea una entrada en el historial de pedidos y, potencialmente, envía correos electrónicos de confirmación de pedido.
        -   Si el pago falla o no es válido, actualiza el estado del pedido en consecuencia (por ejemplo, a "Error de pago").
        -   Luego redirige al cliente de vuelta a la página de PrestaShop apropiada (por ejemplo, página de confirmación de pedido o página de error).

### 4.3 Clases y Modelos Centrales (`classes/`)

El módulo no parece definir ninguna clase personalizada que extienda `ObjectModel` u otras clases centrales de PrestaShop en un directorio `classes/` dedicado. Toda la lógica central probablemente está encapsulada dentro de la clase principal del módulo `PerfectMoney` (`index.php`) y los controladores frontales.

### 4.4 Activos JavaScript (`views/js/`)

No se detectaron archivos JavaScript personalizados en el archivo del módulo. El proceso de pago se maneja principalmente mediante redirecciones del lado del servidor y la propia interfaz de pago de Perfect Money.

### 4.5 Hojas de Estilo CSS (`views/css/`)

No se detectaron archivos CSS personalizados en el archivo del módulo. El estilo para la opción de pago en la página de pago probablemente se hereda del tema de PrestaShop o de estilos en línea dentro de la plantilla.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **`perfectmoney/views/admin.tpl`**

    -   **Alcance**: Configuración de administración del Back-office.
    -   **Propósito**: Esta plantilla se utiliza para renderizar el formulario de configuración del módulo dentro del back office de PrestaShop. Muestra los campos de entrada para el ID de Cuenta Perfect Money, Nombre de Cuenta, Frase de Contraseña Alternativa y los desplegables de selección de estado del pedido. Utiliza los ayudantes de formulario y el estilo estándar de PrestaShop.
-   **`perfectmoney/views/perfectmoney.tpl`**

    -   **Alcance**: Front-office (paso de pago del proceso de compra).
    -   **Propósito**: Esta plantilla es responsable de mostrar la opción de pago Perfect Money al cliente en la página de pago. Típicamente incluye el título del método de pago, la descripción y, potencialmente, el logotipo de Perfect Money. Se renderiza dentro de un hook de pago (por ejemplo, `displayPaymentOptions` en PS 1.7+ o `displayPayment` en PS 1.6).
-   **`perfectmoney/views/success_page.tpl`**

    -   **Alcance**: Front-office (página de confirmación/éxito del pedido).
    -   **Propósito**: Esta plantilla probablemente se utiliza para mostrar un mensaje de éxito personalizado o información adicional al cliente después de un pago exitoso con Perfect Money, antes o como parte de la página de confirmación de pedido estándar. Podría ser renderizada por el controlador `validation.php`.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El módulo no parece crear ninguna tabla SQL personalizada.
    -   La configuración (ID de Cuenta Perfect Money, Frase de Contraseña, etc.) se almacena en la tabla `ps_configuration`, utilizando claves con el prefijo `PERFECTMONEY_`.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayPaymentOptions` (PS 1.7+) | En la página de pago, paso de pago. | Renderiza la opción de pago Perfect Money usando `perfectmoney.tpl`. |
| `displayPayment` (PS 1.6) | En la página de pago, paso de pago. | Renderiza la opción de pago Perfect Money usando `perfectmoney.tpl`. |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Potencialmente utilizado para cargar activos específicos del módulo (JS/CSS) si hubiera alguno, o para metaetiquetas. (No se detectaron activos, por lo que probablemente para la inicialización del módulo o compatibilidad). |
| `actionPaymentConfirmation` | Después de que se confirma el estado de pago de un pedido. | Podría usarse para el procesamiento posterior al pago, aunque la actualización principal del estado es manejada por el controlador `validation.php`. |
| `actionValidateOrder` | Después de que un pedido ha sido validado y creado con éxito. | Utilizado por el módulo para crear el pedido en PrestaShop con el estado inicial antes de la redirección a Perfect Money. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo Perfect Money, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.

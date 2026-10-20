---
title: "Google Customer Reviews para PrestaShop - opt-in y encuesta (GCR) - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Google Customer Reviews para PrestaShop - opt-in & survey (GCR) de MyPresta.eu."
sidebar:
  label: "Google Customer Reviews para PrestaShop - opt-in y encuesta (GCR) - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Google Customer Reviews for PrestaShop - opt-in & survey (GCR) en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/google-customer-reviews-for-prestashop-opt-in-survey-gcr.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/google-customer-reviews-for-prestashop-opt-in-survey-gcr/)
>
> ---


# Google Customer Reviews para PrestaShop - opt-in y encuesta (GCR)

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo de Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Para acceder a la configuración del módulo, vaya a **Módulos > Gestor de Módulos**, busque "Google Customer Reviews" y haga clic en el botón "Configurar".

#### **ID de Comerciante de Google**

-   **Qué hace esta configuración:** Este es el identificador único de su cuenta de Google Merchant Center. Google utiliza este ID para asociar las reseñas recopiladas con su negocio específico.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se introduce correctamente:* El script de suscripción a Google Customer Reviews funcionará correctamente, enviando datos de reseñas a su cuenta de Google Merchant Center.
    -   *Cuando es incorrecto o está vacío:* El script de suscripción no funcionará y Google no recopilará reseñas para su tienda.
-   **Valor recomendado:** Su ID exacto de Google Merchant Center. Puede encontrar este ID iniciando sesión en su cuenta de Google Merchant Center (merchant.google.com); generalmente se muestra en la esquina superior derecha.
-   **Escenario / ejemplo de comerciante:** Si su ID de Google Merchant Center es `123456789`, introduciría `123456789` en este campo. Sin él, Google no sabe a qué comerciante atribuir las reseñas.

#### **Incluir lista de GTIN de productos en la carga útil de GCR**

-   **Qué hace esta configuración:** Esta opción controla si los Números Globales de Artículos Comerciales (GTIN) de los productos en el pedido del cliente se incluyen cuando los datos de suscripción se envían a Google. Los GTIN (como EAN, UPC, ISBN) ayudan a Google a identificar productos específicos para reseñas a nivel de producto.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando está habilitado (Sí):* El módulo intentará recuperar e incluir los GTIN de cada producto en el pedido. Esto permite a Google recopilar potencialmente reseñas específicas de productos, que pueden aparecer en las páginas de productos y en Google Shopping.
    -   *Cuando está deshabilitado (No):* Solo se recopilarán reseñas del vendedor. No se enviarán GTIN específicos de productos, lo que significa que Google no solicitará a los clientes reseñas sobre productos individuales de ese pedido.
-   **Valor recomendado:** **Sí**. Incluir GTIN es muy recomendable si desea recopilar reseñas a nivel de producto, que son muy valiosas para la visibilidad y la confianza del producto. Asegúrese de que sus productos en PrestaShop tengan sus campos EAN/UPC correctamente rellenados.
-   **Escenario / ejemplo de comerciante:** Si vende una "Camiseta Azul" con EAN `1234567890123`, habilitar esto asegura que Google sepa *qué* producto compró el cliente, permitiéndoles revisar ese artículo específico. Si está deshabilitado, Google solo pediría una reseña general de su tienda.

#### **Desplazamiento de entrega de respaldo (días)**

-   **Qué hace esta configuración:** Este ajuste determina el número estimado de días después de realizar un pedido en que se espera que el cliente reciba su entrega. Google utiliza esta fecha para programar cuándo enviar el correo electrónico de la encuesta de reseñas.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se establece en un número específico (por ejemplo, 7):* El módulo calcula la fecha de entrega estimada sumando este número de días a la fecha del pedido. Google enviará el correo electrónico de la encuesta alrededor de esta fecha de entrega calculada.
    -   *Cuando se establece en 0 o un número muy bajo:* Google podría enviar la encuesta demasiado pronto, antes de que el cliente haya recibido su producto, lo que llevaría a reseñas irrelevantes o negativas.
    -   *Cuando se establece en un número muy alto:* Google podría enviar la encuesta demasiado tarde, y el cliente podría haber olvidado los detalles de su experiencia de compra.
-   **Valor recomendado:** Esto depende de sus tiempos de envío promedio. Un punto de partida común es **7 días**. Ajuste esto según su rendimiento de entrega real.
-   **Escenario / ejemplo de comerciante:** Si su tiempo de entrega promedio es de 5 a 7 días hábiles, establecerlo en `7` días es apropiado. Si realiza envíos internacionales y las entregas tardan de 2 a 3 semanas, podría establecerlo en `14` o `21` días. Esto asegura que la encuesta llegue cuando el cliente haya tenido tiempo de recibir y experimentar el producto.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | ID de Comerciante de Google | Su ID de Comerciante | Vincula las reseñas recopiladas a su cuenta de Google Merchant Center. **CRÍTICO para su funcionamiento.** |
| Configuración del Módulo | Incluir lista de GTIN de productos en la carga útil de GCR | Sí | Permite la recopilación de reseñas específicas de productos enviando identificadores de productos. |
| Configuración del Módulo | Desplazamiento de entrega de respaldo (días) | 7 | Establece la fecha de entrega estimada para la programación de la encuesta. Ajuste según el tiempo de envío promedio. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: He configurado el módulo, pero no veo la opción de suscripción a Google Customer Reviews en mi página de confirmación de pedido.**
R:

1.  **Verifique su ID de Comerciante de Google:** Vuelva a verificar que ha introducido el ID de Comerciante de Google correcto en la configuración del módulo. Un ID incorrecto impedirá que el script se cargue.
2.  **Borre la Caché de PrestaShop:** Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, el contenido en caché puede impedir que aparezcan nuevos scripts de módulos.
3.  **Verifique si hay Errores de JavaScript:** Abra la consola de desarrollador de su navegador (generalmente F12) en la página de confirmación del pedido. Busque cualquier error de JavaScript, que podría indicar un conflicto con otro módulo o su tema.
4.  **Verifique la Ejecución del Hook:** Asegúrese de que su tema llama correctamente al hook `displayOrderConfirmation`. Aunque es estándar, algunos temas muy personalizados podrían omitir o renombrar hooks.

**P: La opción de suscripción aparece, pero no veo ninguna reseña en mi Google Merchant Center.**
R:

1.  **Estado de Google Merchant Center:** Inicie sesión en su cuenta de Google Merchant Center y navegue a la sección "Google Customer Reviews". Asegúrese de que el programa esté activo y de que no se informen problemas. Puede llevar algún tiempo que las reseñas comiencen a aparecer después de la configuración inicial.
2.  **Tasa de Suscripción del Cliente:** No todos los clientes se suscribirán a la encuesta. Un cierto porcentaje de clientes debe aceptar recibir el correo electrónico de la encuesta de Google.
3.  **Finalización de la Encuesta:** Incluso si un cliente se suscribe, aún debe completar la encuesta enviada por Google.

**P: ¿Puedo personalizar la apariencia de la opción de suscripción o la insignia de Google Customer Reviews?**
R: La apariencia del aviso de suscripción y la insignia de Google Customer Reviews está controlada por Google y no se puede personalizar directamente a través del módulo de PrestaShop. Google mantiene una experiencia de marca consistente para estos elementos. Sin embargo, puede elegir dónde mostrar la insignia en su sitio a través de la configuración de su Google Merchant Center (por ejemplo, pie de página, barra lateral).

**P: Mis productos tienen GTIN, pero no estoy obteniendo reseñas a nivel de producto.**
R:

1.  **Habilite los GTIN en el Módulo:** Asegúrese de que la opción "Incluir lista de GTIN de productos en la carga útil de GCR" esté configurada en "Sí" en la configuración del módulo.
2.  **Formato Correcto de GTIN:** Verifique que sus GTIN de productos (EAN, UPC, ISBN) estén correctamente introducidos en las páginas de sus productos de PrestaShop y sigan los formatos estándar. Los GTIN con formato incorrecto podrían ser ignorados por Google.
3.  **Discreción de Google:** Incluso con los GTIN proporcionados, Google decide en última instancia si solicita reseñas a nivel de producto. Factores como la popularidad del producto y el volumen de reseñas pueden influir en esto.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo `gcroptin` es un módulo ligero de PrestaShop diseñado para inyectar el script oficial de suscripción a Google Customer Reviews en el hook `displayOrderConfirmation`. Aprovecha la clase `Module` de PrestaShop y el motor de plantillas `Smarty`. La lógica central reside en el archivo principal del módulo, manejando el almacenamiento de la configuración y la inyección dinámica de datos en la plantilla Smarty. No introduce controladores personalizados, modelos o activos complejos de JavaScript/CSS, centrándose únicamente en la inyección de script requerida con datos de pedido dinámicos.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. El módulo opera enganchándose a `displayOrderConfirmation` y renderizando una plantilla directamente.
-   **Controladores de Administración de Back-Office**: Ninguno. Toda la configuración se maneja dentro del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

-   No se definen clases personalizadas ni instancias de `ObjectModel`. Toda la lógica está autocontenida dentro de `gcroptin.php`.

### 4.4 Activos de JavaScript (`views/js/`)

-   Ninguno. El módulo genera directamente el fragmento de JavaScript de Google Customer Reviews dentro de una plantilla Smarty.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   Ninguno. La interfaz de usuario de suscripción a Google Customer Reviews es renderizada por el script de Google y no requiere estilos personalizados del módulo.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de Hook (`views/templates/hook/`)**:
    -   `gcroptin/views/templates/hook/gcroptin-order-confirmation.tpl`
        -   **Propósito:** Esta plantilla se renderiza cuando se ejecuta el hook `displayOrderConfirmation`. Contiene el fragmento de JavaScript principal de suscripción a Google Customer Reviews.
        -   **Datos Disponibles:** Esta plantilla recibe varias variables específicas del pedido del módulo, incluyendo:
            -   `{$gcr_merchant_id}`: El ID de Google Merchant Center configurado en el back office.
            -   `{$gcr_order_id}`: El ID del pedido de PrestaShop.
            -   `{$gcr_currency_iso_code}`: Código ISO de la moneda del pedido.
            -   `{$gcr_total_paid}`: Importe total pagado por el pedido.
            -   `{$gcr_customer_email}`: Dirección de correo electrónico del cliente.
            -   `{$gcr_delivery_country}`: Código ISO del país de entrega.
            -   `{$gcr_delivery_date}`: Fecha de entrega estimada calculada.
            -   `{$gcr_product_gtins_json}`: Array codificado en JSON de GTIN de productos (si está habilitado).
        -   **Salida:** Genera una etiqueta `<script>` que contiene el código de suscripción a Google Customer Reviews, poblado dinámicamente con los detalles del pedido.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**: El módulo no crea ninguna tabla de base de datos personalizada. Almacena su configuración en la tabla `ps_configuration` de PrestaShop utilizando claves como `GCROPTIN_MERCHANT_ID`, `GCROPTIN_INCLUDE_GTIN` y `GCROPTIN_DELIVERY_OFFSET`.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayOrderConfirmation` | Se ejecuta en la página de confirmación del pedido después de una compra exitosa. | Inyecta el fragmento de JavaScript de suscripción a Google Customer Reviews con datos de pedido dinámicos. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con el módulo "Google Customer Reviews para PrestaShop - opt-in y encuesta (GCR)".

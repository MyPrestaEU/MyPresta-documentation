---
title: "Impresora de Vales y Cartas - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Voucher & Letters Printer' de MyPresta.eu."
sidebar:
  label: "Impresora de Vales y Cartas - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Voucher & Letters Printer en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-letters-printer.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/voucher-letters-printer/)
>
> ---


# Impresora de Vales y Cartas

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL). No hay requisitos de alojamiento especiales más allá de una configuración típica de PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Impresora de Vales y Cartas)

Esta es la pantalla de configuración principal donde definirá los parámetros para sus vales y cartas.

#### **Ajustes Generales**

- **Qué hace este ajuste:** Estos ajustes controlan el comportamiento general y la apariencia de los vales y cartas generados.
- **Efecto de cambiar este ajuste:** Los cambios aquí impactarán directamente el contenido y el formato de los documentos que imprima.

#### **Generación de Códigos de Vale**

- **Prefijo del Vale:**

  - **Qué hace este ajuste:** Este texto se añadirá al principio de cada código de vale generado. Le ayuda a identificar el origen del vale (por ejemplo, "BIENVENIDA-", "LEALTAD-").
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "OFERTA-":* Todos los códigos generados comenzarán con "OFERTA-", como "OFERTA-ABC123XYZ".
    - *Cuando se deja vacío:* Los códigos serán caracteres puramente aleatorios, por ejemplo, "ABC123XYZ".
  - **Valor recomendado:** Un prefijo corto y descriptivo relacionado con su campaña.
  - **Escenario / ejemplo del comerciante:** Si está enviando una recompensa por lealtad, use "LEALTAD-". Para una venta de temporada, "VERANO-".
- **Sufijo del Vale:**

  - **Qué hace este ajuste:** Similar al prefijo, este texto se añadirá al final de cada código de vale generado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "-2024":* Todos los códigos generados terminarán con "-2024", como "ABC123XYZ-2024".
    - *Cuando se deja vacío:* Los códigos no tendrán un sufijo.
  - **Valor recomendado:** Dejar vacío a menos que tenga una necesidad de seguimiento específica.
  - **Escenario / ejemplo del comerciante:** Podría usar un sufijo de año como "-2024" para campañas anuales.
- **Longitud del Código del Vale (excluyendo prefijo/sufijo):**

  - **Qué hace este ajuste:** Determina el número de caracteres aleatorios en el propio código del vale, entre el prefijo y el sufijo. Un código más largo es más seguro pero más difícil de escribir.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 8:* Los códigos tendrán 8 caracteres aleatorios (por ejemplo, "ABC123XY").
    - *Cuando se establece en 12:* Los códigos tendrán 12 caracteres aleatorios (por ejemplo, "ABC123XYZ456").
  - **Valor recomendado:** 8-12 caracteres para un buen equilibrio entre seguridad y usabilidad.
  - **Escenario / ejemplo del comerciante:** Para una promoción general, 8 caracteres suelen ser suficientes. Para vales exclusivos de alto valor, podría optar por 10-12.

#### **Contenido del Vale y la Carta**

- **Valor del Vale:**

  - **Qué hace este ajuste:** Este es el valor monetario o el porcentaje de descuento que proporcionará el vale generado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "10":* El vale otorgará un descuento de 10 unidades (por ejemplo, 10 €, 10 $).
    - *Cuando se establece en "20%":* El vale otorgará un descuento del 20%.
  - **Valor recomendado:** Un valor que fomente las compras sin afectar significativamente sus márgenes.
  - **Escenario / ejemplo del comerciante:** Ofrezca 15 € de descuento para un pedido mínimo de 100 €, o un 10% de descuento en todo el carrito.
- **Importe Mínimo del Vale:**

  - **Qué hace este ajuste:** El total mínimo del pedido (antes del envío) requerido para que el cliente use el vale.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "50":* Los clientes deben gastar al menos 50 € para usar el vale.
    - *Cuando se establece en "0" o se deja vacío:* No se requiere una compra mínima.
  - **Valor recomendado:** Establezca un importe mínimo para asegurar la rentabilidad, típicamente 2-3 veces el valor del vale.
  - **Escenario / ejemplo del comerciante:** Si el vale es de 10 €, establezca un mínimo de 30 € para fomentar una compra mayor.
- **Fecha de Caducidad del Vale (Días desde la Generación):**

  - **Qué hace este ajuste:** Define cuántos días después de la generación del vale este caducará. Esto crea urgencia.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "30":* El vale será válido durante 30 días a partir de la fecha de su creación.
    - *Cuando se establece en "0" o se deja vacío:* El vale no tendrá fecha de caducidad (no recomendado para la mayoría de las campañas).
  - **Valor recomendado:** 30-90 días, dependiendo de la urgencia que desee crear.
  - **Escenario / ejemplo del comerciante:** Para una venta rápida, 30 días. Para una recompensa por lealtad, 90 días.
- **Texto del Encabezado de la Carta:**

  - **Qué hace este ajuste:** Este es el título o saludo principal que aparecerá en la parte superior de su carta personalizada.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "Estimado Cliente Valioso,":* Esta será la línea de apertura de cada carta.
    - *Cuando se establece en "¡Una Oferta Especial Solo Para Ti!":* Este será el encabezado prominente.
  - **Valor recomendado:** Un saludo cálido y personal.
  - **Escenario / ejemplo del comerciante:** "Hola [Nombre del Cliente]," (si planea insertar nombres manualmente o usar una herramienta de combinación de correspondencia más tarde) o "¡Gracias por ser un Cliente Fiel!"
- **Texto del Cuerpo de la Carta:**

  - **Qué hace este ajuste:** Este es el contenido principal de su carta, donde explica la oferta, agradece al cliente y proporciona cualquier otra información relevante. Puede usar marcadores de posición para contenido dinámico (aunque el módulo en sí no ofrece marcadores de posición directos, normalmente usaría una herramienta de combinación de correspondencia para esto después de la exportación).
  - **Efecto de cambiar este ajuste:** Este texto formará el mensaje central de su carta física.
  - **Valor recomendado:** Texto claro, conciso y persuasivo que explique los beneficios del vale y fomente su canje.
  - **Escenario / ejemplo del comerciante:** "Como muestra de nuestro agradecimiento, disfrute de [Valor del Vale] de descuento en su próxima compra de [Importe Mínimo]. Use el código: [Código del Vale]. Válido hasta [Fecha de Caducidad]."
- **Texto del Pie de Página de la Carta:**

  - **Qué hace este ajuste:** Este texto aparece en la parte inferior de su carta, típicamente para la información de contacto de su tienda, sitio web o una nota de cierre.
  - **Efecto de cambiar este ajuste:** Esta será la sección de cierre de su carta.
  - **Valor recomendado:** El sitio web de su tienda, correo electrónico de contacto o un cierre amigable como "Atentamente, El equipo de [Nombre de Su Tienda]."
  - **Escenario / ejemplo del comerciante:** "Visítenos en [www.sutienda.com](http://www.sutienda.com) para más productos increíbles!"

#### **Opciones de Impresión y Diseño**

- **Imprimir Código de Vale en la Carta:**

  - **Qué hace este ajuste:** Un simple interruptor para incluir el código de vale generado directamente dentro de la carta impresa.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* El código de vale único se insertará automáticamente en el cuerpo de la carta donde lo especifique (o en una posición predeterminada si no se especifica en el texto del cuerpo).
    - *Cuando está deshabilitado (NO):* El código de vale no se imprimirá en la carta. Podría elegir esto si está imprimiendo tarjetas de vale separadas.
  - **Valor recomendado:** SÍ, por conveniencia y para asegurar que el cliente tenga el código.
  - **Escenario / ejemplo del comerciante:** Si desea un solo documento para el cliente, habilite esta opción.
- **Color del Texto (para Carta/Vale):**

  - **Qué hace este ajuste:** Le permite elegir el color del texto en sus documentos impresos.
  - **Efecto de cambiar este ajuste:** Cambia el color de la tinta utilizada para el texto.
  - **Valor recomendado:** Negro o un color oscuro y legible que contraste bien con el papel blanco.
  - **Escenario / ejemplo del comerciante:** Use el color de texto principal de su marca para mayor coherencia.
- **Color de Fondo (para la Sección del Vale):**

  - **Qué hace este ajuste:** Si está imprimiendo vales directamente en la carta, esto establece un color de fondo para el área del código del vale para que destaque.
  - **Efecto de cambiar este ajuste:** Crea un cuadro de color detrás del código del vale.
  - **Valor recomendado:** Un color claro y sutil que no oculte el texto, o déjelo en blanco si lo prefiere.
  - **Escenario / ejemplo del comerciante:** Un gris claro o una versión pastel del color de su marca para resaltar el vale.
- **Tamaño de Fuente (para Carta/Vale):**

  - **Qué hace este ajuste:** Controla el tamaño del texto en sus documentos impresos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "12px":* El texto tendrá un tamaño estándar legible.
    - *Cuando se establece en "16px":* El texto será más grande, más fácil de leer para algunos.
  - **Valor recomendado:** 10-14px para el texto del cuerpo, ligeramente más grande para los encabezados.
  - **Escenario / ejemplo del comerciante:** Si su público objetivo incluye datos demográficos mayores, un tamaño de fuente ligeramente mayor podría ser beneficioso.

#### **Selección y Generación de Clientes**

- **Seleccionar Clientes:**

  - **Qué hace este ajuste:** Esta sección le permite elegir qué clientes recibirán las cartas y vales personalizados. Puede seleccionar clientes específicos de una lista.
  - **Efecto de cambiar este ajuste:** Solo los clientes seleccionados tendrán vales generados para ellos, y sus detalles se utilizarán para las cartas.
  - **Valor recomendado:** Seleccione clientes según los objetivos de su campaña (por ejemplo, nuevos clientes, clientes leales, clientes inactivos).
  - **Escenario / ejemplo del comerciante:** Seleccione todos los clientes que no han comprado en los últimos 6 meses para volver a interactuar con ellos.
- **Botón Generar Vales y Cartas:**

  - **Qué hace este ajuste:** Después de configurar todos los ajustes y seleccionar a los clientes, al hacer clic en este botón se iniciará el proceso de generación de los códigos de vale únicos y la preparación de las cartas personalizadas para su impresión.
  - **Efecto de cambiar este ajuste:** Esta acción crea nuevas reglas de carrito (vales) en su tienda PrestaShop y genera los documentos imprimibles.
  - **Valor recomendado:** Haga clic solo después de revisar cuidadosamente todos los ajustes.
  - **Escenario / ejemplo del comerciante:** Una vez que se planifica una campaña, haga clic en esto para preparar el envío.

#### **Tabla de Referencia Rápida de Configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Config. Principal | Prefijo del Vale | `LEALTAD-` | Texto al inicio del código del vale. Ayuda a identificar la campaña. |
| Config. Principal | Sufijo del Vale | Vacío | Texto al final del código del vale. Útil para el seguimiento. |
| Config. Principal | Longitud del Código del Vale | 8-12 | Número de caracteres aleatorios en el código. Afecta la seguridad/usabilidad. |
| Config. Principal | Valor del Vale | `10` (ej., 10 € o 10%) | Cantidad o porcentaje de descuento. |
| Config. Principal | Importe Mínimo del Vale | `0` (o 2-3x valor del vale) | Pedido mínimo para usar el vale. Asegura la rentabilidad. |
| Config. Principal | Fecha de Caducidad del Vale (Días) | `30-90` | Días hasta que caduca el vale. Crea urgencia. |
| Config. Principal | Texto del Encabezado de la Carta | `Estimado Cliente Valioso,` | Saludo/título principal de la carta. |
| Config. Principal | Texto del Cuerpo de la Carta | (Mensaje personalizado) | Contenido principal de la carta, explicando la oferta. |
| Config. Principal | Texto del Pie de Página de la Carta | `www.sutienda.com` | Notas de cierre, información de contacto. |
| Config. Principal | Imprimir Código de Vale en la Carta | SÍ | Incluye el código del vale directamente en la carta. |
| Config. Principal | Color del Texto | Negro | Color de todo el texto en los documentos impresos. |
| Config. Principal | Color de Fondo | Blanco (o gris claro) | Color de fondo para el área del código del vale. |
| Config. Principal | Tamaño de Fuente | `12px` | Tamaño del texto en los documentos impresos. |
| Config. Principal | Seleccionar Clientes | (Selección específica) | Elija qué clientes reciben el envío. |
| Config. Principal | Generar Vales y Cartas | (Clic en el botón) | Crea vales y documentos imprimibles. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Generé vales, pero no parecen funcionar en mi tienda.**
R1: Después de la generación, el módulo crea "Reglas de Carrito" en PrestaShop.
1. **Verificar Reglas de Carrito:** Vaya a **Catálogo > Descuentos > Reglas de Carrito** en su Back Office. Asegúrese de que los vales generados estén listados allí y estén "Activados".
2. **Verificar Condiciones:** Verifique que las condiciones del vale (importe mínimo, fecha de caducidad, restricciones de cliente) coincidan con lo que pretendía. Si un cliente intenta usar un vale que no cumple los criterios, no se aplicará.
3. **Borrar Caché:** A veces, la caché de PrestaShop puede impedir que las nuevas configuraciones surtan efecto inmediatamente. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché".

**P2: Las cartas impresas no se ven bien o los colores están mal.**
R2:
1. **Verificar Configuración del Módulo:** Vuelva a la página de configuración del módulo. Vuelva a verificar sus ajustes de "Color del Texto", "Color de Fondo" y "Tamaño de Fuente". Asegúrese de haber seleccionado colores que se impriman bien.
2. **Configuración de la Impresora:** La calidad de la salida final depende en gran medida de su impresora física. Verifique los niveles de tinta de su impresora, el tipo de papel y la configuración de calidad de impresión. Intente imprimir una página de prueba desde otra aplicación.
3. **Vista Previa de Impresión del Navegador:** Cuando inicie la impresión desde su navegador, use la función de vista previa de impresión para ver cómo se verá antes de consumir tinta y papel. Ajuste la configuración de impresión del navegador (por ejemplo, márgenes, encabezados/pies de página) si es necesario.

**P3: ¿Puedo traducir el contenido de la carta a diferentes idiomas para clientes internacionales?**
R3: La versión actual del módulo no ofrece campos multilingües incorporados para el contenido de la carta directamente dentro de su configuración. Tendría que:
1. **Generar para cada idioma:** Configure el módulo con el contenido de la carta en un idioma, genere las cartas para los clientes relevantes y luego repita el proceso para otros idiomas y grupos de clientes.
2. **Traducción Manual:** Si exporta los datos del cliente y los códigos de vale, podría usar una herramienta de combinación de correspondencia separada para crear cartas multilingües.

**P4: Quiero enviar cartas a clientes de un país específico solamente. ¿Cómo puedo hacerlo?**
R4: La función "Seleccionar Clientes" del módulo le permite elegir clientes individuales. Si necesita filtrar por país u otros criterios, normalmente debería:
1. **Exportar Datos de Clientes:** Vaya a **Clientes > Clientes** en su Back Office y use la función de exportación para obtener una lista de todos sus clientes.
2. **Filtrar Externamente:** Use un programa de hoja de cálculo (como Excel o Google Sheets) para filtrar su lista de clientes por país o cualquier otro criterio deseado.
3. **Selección Manual:** Vuelva al módulo y seleccione manualmente los clientes filtrados de la lista. Esto puede ser tedioso para listas grandes.
4. **Personalización del Desarrollador (Avanzado):** Para necesidades de filtrado muy grandes o complejas, un desarrollador podría extender el módulo para agregar opciones de filtrado de clientes más avanzadas.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Impresora de Vales y Cartas".

### 4.1 Descripción General de la Arquitectura

El módulo "Impresora de Vales y Cartas" es un módulo estándar de PrestaShop que opera principalmente dentro del Back Office. Aprovecha la clase `Module` de PrestaShop para su funcionalidad principal y la clase `Configuration` para almacenar la configuración. El propósito principal del módulo es generar objetos `CartRule` (vales) y luego renderizar contenido HTML imprimible basado en la configuración del módulo y los datos de los clientes seleccionados. No introduce tablas de base de datos personalizadas ni estructuras `ObjectModel` complejas más allá de lo que PrestaShop ya proporciona para `CartRule` y `Customer`.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores de administración de Front-Office o Back-Office personalizados. Toda la configuración y la lógica se manejan dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no define ninguna clase personalizada en el directorio `classes/`. Interactúa directamente con las clases principales de PrestaShop, principalmente:

- `Module`: La clase base para el módulo en sí.
- `Configuration`: Para almacenar y recuperar la configuración del módulo.
- `Customer`: Para recuperar datos del cliente para la personalización de la carta.
- `CartRule`: Para crear y gestionar los códigos de vale generados.

### 4.4 Activos JavaScript (`views/js/`)

- **`voucherletter/js/jscolor/jscolor.js`**

  - **Alcance:** Back-office.
  - **Descripción:** Esta es una biblioteca JavaScript de terceros para un selector de color avanzado. Permite al usuario administrador seleccionar visualmente colores para texto y fondo dentro del formulario de configuración del módulo.
  - **Funcionalidad:** Se vincula a campos de entrada con clases específicas (por ejemplo, `jscolor`) para mostrar una paleta de colores y actualizar el valor de entrada con el código de color hexadecimal elegido.
- **`voucherletter/js/script.js`**

  - **Alcance:** Back-office (página de configuración del módulo).
  - **Descripción:** Contiene lógica JavaScript personalizada específica para el formulario de configuración del módulo.
  - **Funcionalidad:**
    - Probablemente maneja solicitudes AJAX para generar vales y cartas (aunque el dossier del módulo implica que `getContent()` maneja el proceso completo, este script podría ayudar con el envío del formulario o las actualizaciones dinámicas).
    - Podría incluir lógica de validación para los campos del formulario (por ejemplo, asegurar que el valor del vale sea un número).
    - Podría gestionar la visualización/ocultación de ciertos elementos del formulario basándose en otras selecciones.
    - Potencialmente activa la funcionalidad de impresión en el navegador después de que se genera el contenido de la carta.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El dossier del módulo indica que no hay archivos CSS personalizados presentes en `views/css/`. El estilo para la configuración del Back Office se basaría en el CSS del tema de administración predeterminado de PrestaShop. Cualquier estilo para la *salida impresa* sería CSS en línea generado por el código PHP o un estilo HTML muy básico.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El dossier del módulo indica que no hay archivos `.tpl` personalizados presentes en `views/templates/`. Esto sugiere que:

- El formulario de configuración del Back Office probablemente se renderiza directamente dentro del método `getContent()` utilizando `HelperForm` de PrestaShop o concatenando cadenas HTML.
- El contenido de la carta imprimible se genera dinámicamente como una cadena HTML dentro del código PHP y luego se envía para la función de impresión del navegador.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo no crea ninguna tabla de base de datos personalizada.
  - Almacena su configuración en la tabla `ps_configuration` de PrestaShop. Las claves de configuración seguirían típicamente un patrón como `VOUCHERLETTER_PREFIX`, `VOUCHERLETTER_VALUE`, etc.
  - Crea nuevas entradas en las tablas `ps_cart_rule` y tablas relacionadas (`ps_cart_rule_lang`, `ps_cart_rule_product_rule_group`, etc.) al generar vales.
- **Tabla de Hooks Registrados**:
  El dossier del módulo indica que el módulo no registra ningún hook de front-office (Encabezado, Columnas, Producto, Pie de página). Esto confirma su función principal como una herramienta de Back Office para generar correo físico.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionModuleInstall` | Durante la instalación del módulo | Establece los valores de configuración predeterminados en `ps_configuration`. |
| `actionModuleUninstall` | Durante la desinstalación del módulo | Limpia los valores de configuración de `ps_configuration`. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y cualquier asistencia adicional con el módulo "Impresora de Vales y Cartas", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.

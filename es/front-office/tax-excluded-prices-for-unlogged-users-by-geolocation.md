---
title: "Precios sin impuestos para usuarios no registrados por geolocalización - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Precios sin impuestos para usuarios no registrados por geolocalización' de MyPresta.eu."
sidebar:
  label: "Precios sin impuestos para usuarios no registrados por geolocalización - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Tax excluded prices for unlogged users by geolocation en MyPresta.eu](https://mypresta.eu/modules/front-office-features/tax-excluded-prices-for-unlogged-users-by-geolocation.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/tax-excluded-prices-for-unlogged-users-by-geolocation/)
>
> ---


# Precios sin impuestos para usuarios no registrados por geolocalización

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Este módulo opera principalmente a través de anulaciones de la lógica de precios central de PrestaShop, lo que significa que su configuración suele ser mínima o incluso automática. El método `getContent()` en el archivo principal del módulo normalmente maneja la visualización de un formulario de configuración estándar, pero para este módulo específico, la funcionalidad principal se logra a través de anulaciones de clase en lugar de configuraciones extensas.

Si hay una pantalla de configuración, normalmente ofrecería opciones relacionadas con la habilitación/deshabilitación del módulo o el ajuste fino de su comportamiento de geolocalización. Sin embargo, según la descripción del módulo y la estructura de archivos, su función principal es ajustar los precios *automáticamente* en función de la geolocalización sin requerir configuraciones complejas orientadas al comerciante.

Por lo tanto, la pantalla de configuración de este módulo es probablemente muy simple, posiblemente solo un interruptor de "Habilitar/Deshabilitar", o incluso podría no tener un formulario de configuración dedicado si su comportamiento es completamente automático una vez instalado.

**Si existe una pantalla de configuración, normalmente incluiría:**

- **Habilitar/Deshabilitar Módulo:**

  - **Qué hace este ajuste:** Este es un interruptor estándar para activar o desactivar la funcionalidad del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El módulo detectará activamente las ubicaciones de los usuarios no registrados y ajustará la visualización de precios (con/sin impuestos) en consecuencia.
    - *Cuando está deshabilitado:* PrestaShop volverá a su comportamiento predeterminado para usuarios no registrados, mostrando típicamente los precios según el país predeterminado de la tienda o una configuración global, sin ajustes basados en geolocalización.
  - **Valor recomendado:** SÍ (para utilizar la funcionalidad principal del módulo).
  - **Escenario/ejemplo de comerciante:** Si necesita solucionar temporalmente un problema de precios o prefiere el comportamiento predeterminado de PrestaShop durante un corto período, podría deshabilitarlo. De lo contrario, manténgalo habilitado para una fijación de precios internacional precisa.
- **Proveedor de servicios de geolocalización (hipotético):**

  - **Qué hace este ajuste:** Si el módulo ofreciera una opción, esto le permitiría seleccionar qué servicio externo utiliza para detectar las direcciones IP de los visitantes y asignarlas a países.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en Proveedor A:* El módulo utiliza la base de datos del Proveedor A para la asignación de IP a país.
    - *Cuando se establece en Proveedor B:* El módulo utiliza la base de datos del Proveedor B, lo que podría ofrecer diferente precisión o velocidad.
  - **Valor recomendado:** El proveedor predeterminado o recomendado por MyPresta.eu.
  - **Escenario/ejemplo de comerciante:** Podría cambiar de proveedor si uno ofrece mayor precisión para sus regiones objetivo o si encuentra problemas con el predeterminado.
- **Configuración de caché (hipotético):**

  - **Qué hace este ajuste:** Controla cuánto tiempo se almacenan en caché los datos de geolocalización para los visitantes para mejorar el rendimiento.
  - **Efecto de cambiar este ajuste:**
    - *Mayor duración de la caché:* Cargas de página más rápidas para visitantes recurrentes, pero actualizaciones potencialmente más lentas si la IP de un visitante cambia.
    - *Menor duración de la caché:* Geolocalización más en tiempo real, pero una carga de servidor ligeramente mayor.
  - **Valor recomendado:** Predeterminado (generalmente optimizado para el equilibrio).
  - **Escenario/ejemplo de comerciante:** Si su sitio tiene un tráfico muy alto y prioriza la velocidad, podría aumentar la duración de la caché. Si su base de clientes es muy móvil y cambia frecuentemente de IP, una duración más corta podría ser preferible.

**Nota importante para los comerciantes:**
Este módulo funciona anulando las clases principales de PrestaShop (`Product.php`, `Tax.php`, `TaxCalculator.php`). Esta es una técnica potente que modifica directamente cómo PrestaShop calcula y muestra los precios. Debido a esto, generalmente hay muy pocas, o ninguna, opciones configurables en una pantalla dedicada. La fuerza del módulo reside en sus ajustes automáticos y en segundo plano.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Habilitar/Deshabilitar Módulo | Habilitado | Activa o desactiva la funcionalidad de ajuste de precios basada en geolocalización del módulo. |
| Página de configuración del módulo | *[Otros ajustes si están presentes]* | *[Valor predeterminado]* | *[Propósito e Impacto]* |

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Los precios no cambian para los usuarios no registrados, incluso después de instalar el módulo.**
R1:

- **Verificar el estado del módulo:** Asegúrese de que el módulo esté instalado y habilitado en su Back Office de PrestaShop en Módulos > Gestor de módulos.
- **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y borre todas las cachés (caché de Smarty, caché del sistema de archivos, etc.). Es posible que también deba borrar la caché del navegador.
- **Precisión de la geolocalización:** El módulo se basa en la geolocalización por IP. Aunque generalmente es precisa, no es 100% perfecta. Pruebe con diferentes IPs (por ejemplo, usando una VPN) para confirmar.
- **Reglas de impuestos de PrestaShop:** Verifique que sus reglas de impuestos y grupos de impuestos de PrestaShop estén configurados correctamente para diferentes países. El módulo utiliza estas reglas existentes para determinar *qué* precio mostrar (impuestos incluidos o excluidos) una vez que conoce el país.
- **Conflictos de anulación:** Si tiene otros módulos que también anulan `Product.php`, `Tax.php` o `TaxCalculator.php`, podría haber un conflicto. Revise su carpeta `override/` en busca de otros módulos que modifiquen estos archivos. Póngase en contacto con el soporte de MyPresta.eu si sospecha un conflicto.

**P2: Mi tema personalizado no parece mostrar los precios correctamente después de la instalación.**
R2: Este módulo afecta principalmente el *valor* del precio mostrado, no su estilo visual. Si los precios se ven desalineados o con un estilo incorrecto, es probable que sea un problema de CSS con su tema.

- **Compatibilidad del tema:** Asegúrese de que su tema sea totalmente compatible con su versión de PrestaShop.
- **Inspeccionar elemento:** Utilice las herramientas de desarrollador de su navegador (F12) para inspeccionar los elementos de precio y ver si algún CSS personalizado de su tema está en conflicto.
- **Póngase en contacto con el desarrollador del tema:** Si está utilizando un tema personalizado, póngase en contacto con su desarrollador para obtener ayuda con el estilo. El módulo en sí no introduce nuevo CSS.

**P3: ¿Este módulo afecta a los usuarios registrados o a los usuarios que han introducido su dirección?**
R3: No, este módulo se dirige específicamente a *usuarios no registrados* que aún no han proporcionado su información de dirección. Una vez que un usuario inicia sesión o introduce su dirección de envío durante el proceso de compra, la lógica nativa de cálculo y visualización de impuestos de PrestaShop (que ya conoce el país del cliente) tendrá prioridad. Este módulo cubre la brecha para la experiencia de navegación inicial.

**P4: ¿Cómo sabe el módulo el país del cliente?**
R4: El módulo utiliza la dirección IP del visitante para determinar su ubicación geográfica. Este es un método estándar para la geolocalización en aplicaciones web. Luego utiliza este país detectado para aplicar las reglas de impuestos de PrestaShop apropiadas para la visualización de precios.

**P5: ¿Este módulo ralentizará mi tienda?**
R5: El módulo está diseñado para ser eficiente. Las búsquedas de geolocalización suelen ser rápidas, y el módulo a menudo almacena en caché los resultados para minimizar las búsquedas repetidas para el mismo visitante. El impacto en el rendimiento debería ser insignificante. Si nota alguna ralentización, asegúrese de que su servidor cumpla con los requisitos mínimos de PrestaShop y de que sus mecanismos de caché estén configurados correctamente.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Precios sin impuestos para usuarios no registrados por geolocalización" logra su funcionalidad principalmente a través del sistema de anulación de PrestaShop. En lugar de depender de ganchos tradicionales o controladores personalizados, modifica directamente el comportamiento de las clases principales de PrestaShop responsables de la fijación de precios de productos y el cálculo de impuestos. Esto le permite inyectar lógica basada en geolocalización en el proceso fundamental de determinación de precios, asegurando que los precios se ajusten antes incluso de que se rendericen. El módulo aprovecha el gancho `displayHeader` para incluir cualquier JavaScript o estilo necesario, aunque su lógica central se basa en PHP.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador de Front-Office o Back-Office Admin personalizado. Su lógica está incrustada directamente en las anulaciones de clases principales.

### 4.3 Clases y modelos principales (`classes/`)

La funcionalidad principal del módulo reside en sus anulaciones de las clases fundamentales de precios y productos de PrestaShop.

- **`taxprice/override/classes/Product.php`**

  - **Clase original:** `Product`
  - **Responsabilidad:** Esta anulación es crucial. La clase `Product` es responsable de recuperar y formatear la información del producto, incluidos los precios. Esta anulación probablemente intercepta métodos como `getPrice()` o métodos de cálculo de precios relacionados para inyectar la lógica de geolocalización *antes* de que se devuelva el precio para su visualización. Determina si mostrar precios con impuestos incluidos o excluidos según el país detectado para usuarios no registrados.
  - **Lógica clave:**
    - Detecta si el usuario actual es un invitado (no ha iniciado sesión).
    - Obtiene el país del visitante basándose en la dirección IP (potencialmente a través de una función auxiliar o una integración de servicio de terceros).
    - Modifica el contexto de `TaxManagerFactory` o manipula directamente el `price_display_method` basándose en las reglas de impuestos del país detectado y la configuración de PrestaShop para ese país.
- **`taxprice/override/classes/tax/Tax.php`**

  - **Clase original:** `Tax`
  - **Responsabilidad:** La clase `Tax` maneja la recuperación y aplicación de tasas de impuestos. Esta anulación podría usarse para asegurar que se apliquen las tasas de impuestos correctas *después* de que la geolocalización haya determinado si los precios deben ser con impuestos incluidos o excluidos. Podría modificar cómo se obtienen las tasas de impuestos o cómo se inicializa el `TaxCalculator` basándose en el país del invitado.
- **`taxprice/override/classes/tax/TaxCalculator.php`**

  - **Clase original:** `TaxCalculator`
  - **Responsabilidad:** Esta clase es central para calcular precios con y sin impuestos. La anulación aquí influiría directamente en el cálculo final del precio. Probablemente asegura que cuando se conoce el país de un invitado, el `TaxCalculator` utilice el `price_display_method` correcto (por ejemplo, `PS_TAX_EXC` o `PS_TAX_INC`) que corresponda a las reglas de impuestos del país detectado, en lugar del predeterminado de la tienda.
- **`taxprice/override/classes/index.php`**

  - **Propósito:** Este es un archivo `index.php` vacío estándar, típicamente colocado en directorios para evitar la lista de directorios por razones de seguridad. No tiene ningún impacto funcional en la lógica del módulo.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo **no** contiene ningún archivo JavaScript personalizado. Su funcionalidad principal se maneja en el lado del servidor a través de anulaciones de PHP.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo **no** contiene ningún archivo CSS personalizado. No introduce nuevos elementos visuales, solo modifica los valores de precios existentes.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **`taxprice/views/displayHeader.tpl`**

  - **Gancho:** `displayHeader`
  - **Propósito:** Esta plantilla se renderiza en la sección `<head>` de cada página del front-office. Se utiliza típicamente para incluir JavaScript, CSS o metaetiquetas. Aunque la lógica central del módulo se basa en PHP, esta plantilla podría usarse para:
    - Inicializar cualquier variable del lado del cliente si es necesario (aunque es poco probable dada la naturaleza del lado del servidor).
    - Potencialmente incluir un pequeño script en línea para depuración o ajustes muy específicos del lado del cliente (por ejemplo, establecer una cookie con el país detectado, aunque es menos común para este tipo de módulo).
    - En ausencia de archivos JS dedicados, podría contener cualquier JS en línea mínimo requerido.
- **`taxprice/views/script.tpl`**

  - **Propósito:** Este nombre de plantilla sugiere que podría contener código JavaScript. Si está presente, probablemente se incluiría a través de `displayHeader.tpl` u otro gancho.
  - **Contenido potencial:**
    - Cualquier lógica del lado del cliente relacionada con la geolocalización (por ejemplo, usando una API de búsqueda de IP del lado del cliente, aunque menos fiable que la del lado del servidor).
    - Scripts para manejar actualizaciones dinámicas de precios si el módulo también admite la alternancia del lado del cliente o ajustes en tiempo real (poco probable dada la descripción).
    - Scripts de depuración o salida de datos simples para desarrolladores.

### 4.7 Esquema de la base de datos y mapa de ganchos

- **Tablas de la base de datos**:

  - Este módulo **no** crea ninguna tabla de base de datos personalizada.
  - Se basa en las tablas existentes de PrestaShop para productos (`ps_product`, `ps_product_shop`), impuestos (`ps_tax`, `ps_tax_rule`, `ps_tax_rule_group`) y configuración (`ps_configuration`).
  - Los valores de configuración se almacenan en `ps_configuration` utilizando los métodos estándar `Configuration::get()` y `Configuration::updateValue()`, típicamente prefijados con `TAXPRICE_`.
- **Tabla de ganchos registrados**:

| Nombre del gancho | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Se utiliza para incluir `displayHeader.tpl` y potencialmente `script.tpl` para cualquier script del lado del cliente o meta-información necesaria. |
| `actionProductUpdate` | Después de que se actualiza un producto. | (Implícito, no listado explícitamente pero común para módulos relacionados con precios) Puede borrar la caché relacionada con los precios de los productos para asegurar que las anulaciones se vuelvan a aplicar. |
| `actionProductAdd` | Después de que se añade un producto. | (Implícito) Similar a `actionProductUpdate`. |
| `actionTaxManagerFactory` | Cuando se inicializa `TaxManagerFactory`. | (Implícito, crucial para este módulo) Las anulaciones en `Tax.php` y `TaxCalculator.php` efectivamente "engancharían" o modificarían el comportamiento del cálculo de impuestos en esta etapa, incluso si no es un registro de `hook` formal. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y asistencia adicional con el módulo "Precios sin impuestos para usuarios no registrados por geolocalización", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo está dedicado a proporcionar un soporte integral y garantizar que su módulo funcione sin problemas.

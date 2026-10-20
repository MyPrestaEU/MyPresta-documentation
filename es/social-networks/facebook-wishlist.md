---
title: "Facebook Wishlist - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Facebook Wishlist de MyPresta.eu."
sidebar:
  label: "Facebook Wishlist - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook Wishlist en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-wishlist.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-wishlist/)
>
> ---


# Facebook Wishlist

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y generalmente están disponibles por defecto. No hay requisitos de alojamiento especiales más allá de una configuración estándar de PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haz clic en "Configurar" junto al módulo Facebook Wishlist en el Gestor de Módulos. Esto te llevará a la pantalla de configuración principal.

#### **ID de la Aplicación de Facebook**

- **Qué hace este ajuste:** Este es un identificador único proporcionado por Facebook para tu aplicación específica (en este caso, la integración de tu tienda PrestaShop con Facebook). Le dice a Facebook qué aplicación está solicitando la acción de la lista de deseos.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce correctamente:* El botón "Añadir a la lista de deseos de Facebook" funcionará correctamente, permitiendo que los productos se añadan a las líneas de tiempo de Facebook.
  - *Cuando es incorrecto o está vacío:* Es probable que el botón no funcione, o Facebook mostrará un error, impidiendo que los clientes añadan productos a sus listas de deseos.
- **Valor recomendado:** Este campo *debe* contener tu ID de aplicación de Facebook válido. Deberás crear una aplicación de Facebook en el sitio web [Facebook para Desarrolladores](https://developers.facebook.com/) para obtener este ID.
- **Escenario / ejemplo de comerciante:** Has creado una aplicación de Facebook para tu tienda, y Facebook te ha dado un ID de aplicación como `123456789012345`. Introducirías este número exacto aquí. Sin él, Facebook no sabrá qué tienda está intentando compartir contenido.

#### **Secreto de la Aplicación de Facebook**

- **Qué hace este ajuste:** Esta es una clave secreta asociada con tu ID de aplicación de Facebook. Se utiliza para la comunicación segura entre tu tienda PrestaShop y los servidores de Facebook. Ayuda a verificar que las solicitudes provienen de tu aplicación legítima.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce correctamente:* Se establece una comunicación segura y el módulo funciona según lo previsto.
  - *Cuando es incorrecto o está vacío:* La comunicación con Facebook puede fallar, lo que lleva a errores o a que las funciones de la lista de deseos no funcionen.
- **Valor recomendado:** Este campo *debe* contener tu Secreto de aplicación de Facebook válido. Al igual que el ID de aplicación, lo obtienes de la configuración de tu aplicación de Facebook en el sitio web [Facebook para Desarrolladores](https://developers.facebook.com/). Mantén este secreto seguro y nunca lo compartas públicamente.
- **Escenario / ejemplo de comerciante:** Después de crear tu aplicación de Facebook, encontrarás tanto el ID de aplicación como el Secreto de aplicación en el panel de control de tu aplicación. El secreto podría parecer una larga cadena de letras y números (por ejemplo, `abcdef1234567890abcdef1234567890`). Introdúcelo exactamente como lo proporciona Facebook.

#### **URL de la Página de Facebook**

- **Qué hace este ajuste:** Esto te permite vincular la página oficial de Facebook de tu tienda a la funcionalidad de la lista de deseos. Cuando los clientes interactúan con la lista de deseos, a veces puede hacer referencia o enlazar a tu página principal de Facebook.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce correctamente:* Mejora la visibilidad de la marca en Facebook y proporciona un enlace directo a tu página oficial.
  - *Cuando es incorrecto o está vacío:* El módulo seguirá funcionando, pero podrías perder la oportunidad de dirigir a los usuarios a tu presencia principal en Facebook.
- **Valor recomendado:** Introduce la URL completa de la página oficial de Facebook de tu tienda (por ejemplo, `https://www.facebook.com/TuNombreDeTienda`). Si no tienes una página oficial, puedes dejar este campo vacío.
- **Escenario / ejemplo de comerciante:** Tu tienda tiene una página de Facebook en `https://www.facebook.com/MyPrestaEu`. Introducir esta URL aquí asegura que cualquier intercambio social relacionado con la lista de deseos pueda dirigir potencialmente a los usuarios a la página principal de tu marca en Facebook.

#### **Posición del botón**

- **Qué hace este ajuste:** Esto controla dónde aparece el botón "Añadir a la lista de deseos de Facebook" en tus páginas de producto.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en 'Página de producto':* El botón se mostrará de forma prominente en la página de detalles del producto, normalmente cerca del botón "Añadir al carrito". Esta es la ubicación más común y recomendada.
  - *Cuando se establece en otras opciones (por ejemplo, 'Cabecera', 'Columnas', 'Pie de página'):* El módulo podría intentar mostrar el botón en estas áreas, pero su funcionalidad está principalmente ligada a información específica del producto, lo que hace que 'Página de producto' sea la opción más lógica. Otras posiciones podrían no mostrar el botón o no funcionar correctamente sin un contexto de producto específico.
- **Valor recomendado:** **Página de producto**. Esto asegura que el botón sea visible cuando los clientes están viendo activamente un producto que podrían querer añadir a su lista de deseos.
- **Escenario / ejemplo de comerciante:** Quieres que los clientes encuentren fácilmente el botón de la lista de deseos justo cuando están considerando comprar un producto. Establecer esto en 'Página de producto' lo coloca lógicamente junto a otras acciones relacionadas con la compra.

#### **Mostrar botón en la página de producto**

- **Qué hace este ajuste:** Este es un simple interruptor de ENCENDIDO/APAGADO para habilitar o deshabilitar la visualización del botón "Añadir a la lista de deseos de Facebook" en tus páginas de producto.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El botón será visible y funcional en todas las páginas de producto.
  - *Cuando está deshabilitado (NO):* El botón estará oculto, y los clientes no podrán añadir productos a sus listas de deseos de Facebook a través de tu tienda.
- **Valor recomendado:** **SÍ**. Para utilizar la funcionalidad principal del módulo, esto siempre debe estar habilitado.
- **Escenario / ejemplo de comerciante:** Has completado toda la configuración y quieres que tus clientes empiecen a usar la función. Establecerías esto en SÍ. Si temporalmente quieres ocultar la función por mantenimiento o una campaña, podrías establecerlo en NO.

#### **Mostrar botón en la página de categoría**

- **Qué hace este ajuste:** Esto controla si el botón "Añadir a la lista de deseos de Facebook" aparece en los listados de productos dentro de las páginas de categoría.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Aparecerá un botón de lista de deseos junto a cada producto en las páginas de categoría y listado. Esto puede ser útil para añadir rápidamente a la lista de deseos, pero podría saturar el diseño dependiendo de tu tema.
  - *Cuando está deshabilitado (NO):* El botón solo aparecerá en las páginas de producto individuales, manteniendo las páginas de categoría más limpias.
- **Valor recomendado:** **NO**. Aunque potencialmente útil, mostrar el botón en las páginas de categoría a veces puede llevar a una experiencia de usuario menos óptima o a un desorden visual. Generalmente es más efectivo en la página de producto dedicada.
- **Escenario / ejemplo de comerciante:** Tienes un diseño de página de categoría muy limpio y quieres minimizar las distracciones. Establecerías esto en NO, asegurando que la acción de la lista de deseos solo esté disponible cuando un cliente se concentra en un solo producto.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | ID de la Aplicación de Facebook | Tu ID de Aplicación de Facebook | Identificador único para la integración de tu tienda con Facebook. **Crítico para la funcionalidad.** |
| Configuración del Módulo | Secreto de la Aplicación de Facebook | Tu Secreto de Aplicación de Facebook | Clave segura para la comunicación con Facebook. **Crítico para la funcionalidad.** |
| Configuración del Módulo | URL de la Página de Facebook | `https://www.facebook.com/TuNombreDeTienda` (si aplica) | Enlaza a tu Página oficial de Facebook, mejorando la visibilidad de la marca. |
| Configuración del Módulo | Posición del botón | Página de producto | Determina dónde aparece el botón de la lista de deseos. **Se recomienda la página de producto.** |
| Configuración del Módulo | Mostrar botón en la página de producto | SÍ | Habilita/deshabilita el botón en las páginas de producto individuales. **Recomendado: SÍ.** |
| Configuración del Módulo | Mostrar botón en la página de categoría | NO | Habilita/deshabilita el botón en los listados de productos en las páginas de categoría. **Recomendado: NO.** |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: El botón "Añadir a la lista de deseos de Facebook" no aparece en mis páginas de producto.**
R:

- **Verifica el Estado del Módulo:** Asegúrate de que el módulo esté instalado y habilitado en **Módulos > Gestor de Módulos**.
- **Configuración del Módulo:** Ve a la página de configuración del módulo y verifica que "Mostrar botón en la página de producto" esté configurado en **SÍ**.
- **ID/Secreto de la Aplicación de Facebook:** Vuelve a verificar que tu ID de aplicación de Facebook y el Secreto de aplicación estén introducidos correctamente. Las credenciales incorrectas evitarán que el botón se cargue o funcione.
- **Compatibilidad del Tema:** Algunos temas altamente personalizados podrían requerir ajustes menores. Si el botón sigue sin aparecer, intenta cambiar temporalmente al tema predeterminado de PrestaShop (Classic) para descartar un conflicto de tema. Si aparece en Classic, es posible que el desarrollador de tu tema necesite integrarlo.
- **Borrar Caché:** Siempre borra la caché de tu PrestaShop (**Parámetros Avanzados > Rendimiento**) y la caché de tu navegador después de realizar cambios en la configuración.

**P2: El botón aparece, pero no pasa nada cuando hago clic en él, o recibo un error de Facebook.**
R:

- **ID/Secreto de la Aplicación de Facebook:** Esto casi siempre se debe a un ID de aplicación de Facebook o un Secreto de aplicación incorrectos o faltantes. Revisa la configuración de tu aplicación en Facebook para Desarrolladores y asegúrate de que los valores estén copiados con precisión.
- **Configuración de la Aplicación de Facebook:** En la plataforma Facebook para Desarrolladores, asegúrate de que tu aplicación esté "Activa" (no en modo de desarrollo) y de que la plataforma "Sitio web" esté añadida con la URL de tu tienda correctamente configurada.
- **Lista Blanca de Dominios:** En la configuración de tu aplicación de Facebook, en "Configuración > Básica", asegúrate de que el dominio de tu sitio web esté listado en el campo "Dominios de la aplicación".
- **Etiquetas Open Graph:** El módulo se basa en las metaetiquetas Open Graph predeterminadas de PrestaShop para la información del producto. Asegúrate de que tu tienda PrestaShop esté generando estas correctamente (puedes verificar el código fuente de tu página de producto en busca de etiquetas `<meta property="og:..."`).

**P3: ¿Cómo obtengo un ID de aplicación de Facebook y un Secreto de aplicación?**
R:

1. Ve a [Facebook para Desarrolladores](https://developers.facebook.com/) e inicia sesión con tu cuenta de Facebook.
2. Haz clic en "Mis aplicaciones" > "Crear aplicación".
3. Elige el tipo de aplicación (por ejemplo, "Consumidor" o "Negocio") y sigue las indicaciones para nombrar tu aplicación.
4. Una vez creada, navega a "Configuración > Básica" en el panel de control de tu nueva aplicación.
5. Allí encontrarás tu **ID de aplicación** y **Secreto de aplicación**.
6. Asegúrate de añadir el dominio de tu sitio web (por ejemplo, `tutienda.com`) al campo "Dominios de la aplicación" y guarda los cambios.
7. Añade una plataforma "Sitio web" a tu aplicación e introduce la URL de tu sitio.
8. Finalmente, asegúrate de que tu aplicación esté configurada en modo "Activo" (normalmente hay un interruptor en la parte superior del panel de control).

**P4: ¿Este módulo ralentizará mi sitio web?**
R: El módulo en sí es muy ligero. La interacción principal es un pequeño botón y una ventana emergente alojada en Facebook, que carga contenido directamente desde los servidores de Facebook. Cualquier ralentización percibida es más probable que esté relacionada con los propios tiempos de carga de Facebook o problemas generales de rendimiento del sitio web, en lugar del módulo en sí.

**P5: ¿Puedo personalizar la apariencia del botón?**
R: El módulo suele utilizar el estilo de botón estándar de Facebook o se integra con los estilos de botón existentes de tu tema. Aunque no hay una configuración directa en el módulo para cambiar su apariencia, un desarrollador web puede personalizarlo usando CSS, apuntando a las clases o IDs CSS específicos del elemento del botón.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo Facebook Wishlist (`facebook-wishlist`) es un módulo de PrestaShop sencillo diseñado principalmente para inyectar la funcionalidad de "Añadir a la lista de deseos" basada en Open Graph en el front-office. Aprovecha el sistema de hooks de PrestaShop para renderizar su botón en las páginas de producto y se basa en el SDK de JavaScript de Facebook y el protocolo Open Graph para su funcionalidad principal. La configuración del módulo se gestiona a través del método estándar `getContent()` en el archivo principal del módulo, almacenando la configuración en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores personalizados de front-office o back-office. Toda la lógica está encapsulada dentro del archivo principal del módulo y su configuración.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no define ninguna clase personalizada u `ObjectModel`. Toda la configuración se maneja a través de `Configuration::get()` y `Configuration::updateValue()`.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo no incluye archivos JavaScript personalizados. Se basa en el SDK de JavaScript de Facebook, que normalmente se carga de forma asíncrona y es gestionado por el propio Facebook una vez que las metaetiquetas Open Graph y el ID de aplicación correctos están presentes.

### 4.5 Hojas de Estilo CSS (`views/css/`)

Este módulo no incluye archivos CSS personalizados. La apariencia del botón es manejada por el estilo predeterminado de Facebook para sus plugins sociales o hereda estilos del tema activo de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

Este módulo no contiene un directorio `views/templates`. El HTML del botón probablemente se genera directamente dentro de los métodos de hook del archivo principal del módulo.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

- **Tablas de la Base de Datos**:
  Este módulo no crea ninguna tabla de base de datos personalizada. Todos los ajustes de configuración se almacenan en la tabla `ps_configuration` utilizando claves como `FACEBOOK_WISHLIST_APP_ID`, `FACEBOOK_WISHLIST_APP_SECRET`, `FACEBOOK_WISHLIST_PAGE_URL`, `FACEBOOK_WISHLIST_BUTTON_POSITION`, `FACEBOOK_WISHLIST_SHOW_PRODUCT_PAGE` y `FACEBOOK_WISHLIST_SHOW_CATEGORY_PAGE`.
- **Tabla de Hooks Registrados**:
  El módulo registra y utiliza los siguientes hooks de PrestaShop:

  | Nombre del Hook | Momento de Ejecución | Propósito Técnico |
  | --- | --- | --- |
  | `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para inyectar el código de inicialización del SDK de JavaScript de Facebook y las metaetiquetas Open Graph (si no están ya presentes por el núcleo de PrestaShop). Esto es crucial para que Facebook reconozca tu sitio y aplicación. |
  | `displayProductButtons` | En la página de producto, normalmente cerca del botón "Añadir al carrito". | Renderiza el botón "Añadir a la lista de deseos de Facebook". Este es el hook principal para la visualización del módulo en el front-office. |
  | `displayProductListFunctionalButtons` | En las páginas de categoría/listado, junto a cada producto. | Renderiza el botón "Añadir a la lista de deseos de Facebook" para productos en listas, si está habilitado en la configuración. |
  | `displayFooter` | En el pie de página de cada página. | Potencialmente utilizado para la carga de scripts adicionales o la colocación de botones de respaldo, aunque `displayProductButtons` es el principal. |
  | `displayLeftColumn` | En la columna izquierda de las páginas. | Posición alternativa para el botón, si está configurado. |
  | `displayRightColumn` | En la columna derecha de las páginas. | Posición alternativa para el botón, si está configurado. |

  La funcionalidad principal del módulo se basa en el hook `displayHeader` para asegurar que el SDK de Facebook se cargue y en el hook `displayProductButtons` (o `displayProductListFunctionalButtons`) para renderizar el botón interactivo. El botón en sí, cuando se hace clic, activa la acción `og:product:wishlist` de Facebook Open Graph, que requiere que metaetiquetas Open Graph específicas (como `og:title`, `og:description`, `og:image`, `og:url`, `og:type=product`) estén presentes en el HTML de la página de producto. PrestaShop suele generar estas etiquetas por defecto.

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo Facebook Wishlist, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto a la funcionalidad e integración del módulo.
"""

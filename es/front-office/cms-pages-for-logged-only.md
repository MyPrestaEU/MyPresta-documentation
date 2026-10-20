---
title: "Páginas CMS solo para usuarios registrados - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'CMS pages for logged only' de MyPresta.eu."
sidebar:
  label: "Páginas CMS solo para usuarios registrados - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo CMS pages for logged only en MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-pages-for-logged-only.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/cms-pages-for-logged-only/)
>
> ---


# Páginas CMS solo para usuarios registrados

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones especiales del servidor más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Páginas CMS solo para usuarios registrados". Verá una única pantalla de configuración.

![Ejemplo de pantalla de configuración de páginas CMS solo para usuarios registrados](https://mypresta.eu/images/art/cms-pages-for-logged-only-configuration.png)

Esta pantalla presenta una lista de todas sus páginas CMS existentes. Para cada página, verá un simple interruptor para habilitar o deshabilitar la restricción "solo para usuarios registrados".

- **Nombre del ajuste:** `cmsp` (Este es el identificador interno, verá los títulos reales de las páginas CMS).
- **Qué hace este ajuste:** Este ajuste le permite seleccionar qué páginas CMS específicas estarán restringidas solo a clientes que han iniciado sesión. Cada fila representa una de las páginas CMS de su tienda.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (el interruptor está ENCENDIDO/verde):* La página CMS seleccionada solo será accesible para los clientes que hayan iniciado sesión en sus cuentas. Si un cliente no registrado intenta visitar esta página, será redirigido a la página de inicio de sesión. Después de un inicio de sesión exitoso, será enviado de vuelta a esta página CMS específica.
  - *Cuando está deshabilitado (el interruptor está APAGADO/rojo):* La página CMS seleccionada será accesible públicamente para todos los visitantes, estén o no registrados. Este es el comportamiento predeterminado para todas las páginas CMS en PrestaShop.
- **Valor recomendado:** Esto depende completamente de sus necesidades comerciales. Habilítelo para cualquier página CMS que contenga información sensible, exclusiva o solo para miembros.
- **Escenario/ejemplo de comerciante:**
  - Tiene una página CMS de "Términos y condiciones de venta al por mayor". Habilitaría el interruptor junto a esta página para que solo sus clientes mayoristas registrados puedan verla.
  - Crea una página CMS de "Guía de contenido premium" para clientes leales. Habilitaría el interruptor para esta página para fomentar el registro y recompensar a los clientes existentes.
  - Tiene una página estándar "Sobre nosotros". Dejaría el interruptor deshabilitado, ya que esta página debe ser visible públicamente para todos los visitantes.

Después de hacer sus selecciones, recuerde hacer clic en el botón **"Guardar"** en la parte inferior de la página para aplicar sus cambios.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Interruptores individuales de páginas CMS | Deshabilitado (APAGADO) | Controla si una página CMS específica requiere que un cliente haya iniciado sesión para verla. Habilitar redirige a los usuarios no registrados a la página de inicio de sesión, y luego de vuelta a la página CMS después de un inicio de sesión exitoso. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He habilitado la restricción para una página CMS, pero los usuarios no registrados aún pueden verla. ¿Qué está mal?**
R:

1. **Borrar caché:** La razón más común es el almacenamiento en caché. Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Es posible que también deba borrar la caché de su navegador.
2. **Guardar configuración:** Asegúrese de haber hecho clic en el botón "Guardar" en la página de configuración del módulo después de habilitar la restricción para la página CMS específica.
3. **Verificar URL de la página CMS:** Verifique dos veces que está probando la URL correcta para la página CMS que restringió.

**P: Después de iniciar sesión, el cliente es redirigido a la página de inicio en lugar de a la página CMS restringida. ¿Por qué?**
R: Este módulo está diseñado para redirigir al cliente de vuelta a la página CMS restringida original después de un inicio de sesión exitoso. Si esto no sucede, podría deberse a:

1. **Redirecciones de inicio de sesión personalizadas:** Otro módulo o una modificación de tema personalizada podría estar anulando el comportamiento de redirección de inicio de sesión predeterminado de PrestaShop. Deshabilite temporalmente otros módulos que afecten el inicio de sesión/redirección para probar.
2. **Especificidades de la versión de PrestaShop:** Si bien el módulo es compatible con muchas versiones, anulaciones de tema o de núcleo muy específicas en versiones antiguas/nuevas de PrestaShop podrían interferir. Asegúrese de que sus archivos principales de PrestaShop sean estándar.

**P: ¿Puedo restringir categorías o productos en lugar de páginas CMS?**
R: No, este módulo está diseñado específicamente solo para páginas CMS. No proporciona funcionalidad para restringir categorías, productos u otros tipos de contenido. Necesitaría un módulo diferente para esos propósitos.

**P: ¿Este módulo afecta el SEO?**
R: Cuando una página está restringida, los rastreadores de motores de búsqueda (como Googlebot) normalmente serán redirigidos a la página de inicio de sesión, al igual que un usuario humano. Esto significa que el contenido de la página CMS restringida no será indexado por los motores de búsqueda. Si el contenido debe ser público e indexado, no lo restrinja con este módulo. Para contenido que debe estar oculto a los motores de búsqueda pero aún accesible para los usuarios que han iniciado sesión, este comportamiento es deseado.

**P: ¿Cómo traduzco el texto del módulo (si lo hay)?**
R: Este módulo tiene muy poco texto en el front-office, ya que principalmente maneja la redirección. Cualquier mensaje relacionado con el inicio de sesión es manejado por la página de autenticación principal de PrestaShop. Si hubiera algún texto específico del módulo, lo traduciría a través de **Internacional > Traducciones** en su Back Office. Seleccione "Traducciones de módulos instalados", elija su tema y luego busque "Páginas CMS solo para usuarios registrados" en la lista.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Páginas CMS solo para usuarios registrados" (`privatecms`) opera principalmente anulando el `CmsController` principal para interceptar las solicitudes de páginas CMS. Verifica si una página CMS solicitada está configurada para acceso "solo para usuarios registrados" y, si el usuario no ha iniciado sesión, activa una redirección a la página de autenticación. Tras un inicio de sesión exitoso, el mecanismo de redirección predeterminado de PrestaShop (que el módulo aprovecha) envía al usuario de vuelta a la página solicitada originalmente. La configuración se gestiona a través de un método `getContent()` estándar en el archivo principal del módulo, almacenando la configuración en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `override/controllers/front/CmsController.php`
    - **Nombre de la clase:** `CmsController` (anula el `CmsController` principal de PrestaShop)
    - **Clase padre:** `CmsControllerCore`
    - **Responsabilidad:** Esta anulación es el núcleo de la funcionalidad del módulo. Intercepta el método `init()` del `CmsController`. Antes de que se renderice la página CMS, verifica si el ID de la página CMS actual (`$this->cms->id`) está presente en la lista de páginas restringidas almacenadas en la configuración del módulo. Si la página está restringida y el cliente no ha iniciado sesión (`$this->context->customer->isLogged()`), redirige al usuario a la página de autenticación (`$this->context->link->getPageLink('authentication')`). También incluye un parámetro `back` en la URL de redirección, asegurando que PrestaShop redirija al usuario de vuelta a la página CMS original después de un inicio de sesión exitoso.
- **Controladores de administración de Back-Office**: Ninguno. Toda la configuración se maneja a través del método `getContent()` del módulo principal.

### 4.3 Clases y modelos principales (`classes/`)

Ninguno. El módulo no define ninguna clase personalizada o entidades `ObjectModel`. Interactúa directamente con las clases principales existentes de PrestaShop como `Configuration`, `Cms`, `Customer` y `Link`.

### 4.4 Activos de JavaScript (`views/js/`)

Ninguno. El módulo no incluye ningún archivo JavaScript personalizado. Su funcionalidad es puramente del lado del servidor (redirección basada en PHP).

### 4.5 Hojas de estilo CSS (`views/css/`)

- `privatecms/css.css`
  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Componentes principales de la interfaz de usuario y contenedores que estiliza:** Esta hoja de estilo probablemente contiene un estilo mínimo para el formulario de configuración del módulo en el Back Office de PrestaShop, asegurando que el diseño y los elementos (como la lista de páginas CMS y los interruptores) se muestren correctamente y de manera consistente con el tema de administración de PrestaShop.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:** Los selectores específicos se encontrarían dentro del archivo, típicamente apuntando a elementos dentro de la plantilla `admin.tpl`.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - `privatecms/admin.tpl`
    - **Propósito:** Esta plantilla es renderizada por el método `getContent()` del archivo principal del módulo (`privatecms.php`). Muestra la lista de todas las páginas CMS disponibles en el Back Office, junto con un interruptor de palanca para cada página, permitiendo al administrador habilitar o deshabilitar la restricción "solo para usuarios registrados". Itera a través de las páginas CMS y muestra sus títulos y el estado actual de la restricción (marcado/desmarcado).

### 4.7 Esquema de la base de datos y mapa de ganchos

- **Tablas de la base de datos**:

  - El módulo no crea ninguna tabla SQL personalizada.
  - La configuración se almacena en la tabla `ps_configuration` (o prefijo `_configuration`).
    - **Clave:** `cmsp`
    - **Valor:** Un array serializado (o cadena JSON, dependiendo de la versión de PrestaShop y la implementación del módulo) que contiene los ID de las páginas CMS seleccionadas para el acceso "solo para usuarios registrados".
- **Tabla de ganchos registrados**:
  El módulo no registra explícitamente ningún gancho estándar de PrestaShop en su método `install()`. Su funcionalidad principal se basa en anular el `CmsController`, que es una forma más directa de interceptar las solicitudes de páginas CMS.

| Nombre del gancho | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `override/controllers/front/CmsController.php` | Durante la inicialización de `CmsController` | Intercepta las solicitudes de páginas CMS para verificar el estado de inicio de sesión y redirigir si es necesario. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Páginas CMS solo para usuarios registrados", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con la funcionalidad y compatibilidad del módulo.

---
title: "Encabezado fijo - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Encabezado fijo' de MyPresta.eu."
sidebar:
  label: "Encabezado fijo - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Fixed sticky header en MyPresta.eu](https://mypresta.eu/modules/front-office-features/fixed-sticky-header.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/fixed-sticky-header/)
>
> ---


# Encabezado fijo

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL). El módulo funciona con las plantillas default-bootstrap y classic y con todos los temas con una estructura similar.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Encabezado fijo" en su Gestor de módulos. Esto le llevará a la página de configuración principal del módulo.

#### Ajustes generales

- **Qué hace este ajuste:** Esta sección suele incluir los ajustes estándar de los módulos de MyPresta.eu relacionados con las actualizaciones y el soporte.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* Permite que el módulo verifique si hay actualizaciones disponibles de MyPresta.eu y, potencialmente, muestre notificaciones en su Back Office. Esto asegura que siempre esté ejecutando la versión más reciente, segura y con más funciones del módulo.
  - *Cuando está deshabilitado:* El módulo no verificará automáticamente las actualizaciones. Tendría que verificar manualmente las nuevas versiones iniciando sesión en su cuenta de MyPresta.eu.
- **Valor recomendado:** **SÍ** (o habilitado). Mantener este ajuste activo es muy recomendable para asegurarse de recibir actualizaciones y correcciones de errores a tiempo, que son cruciales para la seguridad y la compatibilidad con futuras versiones de PrestaShop.
- **Escenario / ejemplo de comerciante:** Desea recibir una notificación si se lanza una nueva versión del módulo que corrige un error o agrega una nueva función. Mantener esto habilitado garantiza que siempre esté informado.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Comprobaciones de actualización (mypresta\_updates, update\_, updatev\_) | Habilitado | Permite que el módulo verifique y le notifique sobre las actualizaciones disponibles de MyPresta.eu, asegurando que tenga las últimas funciones y correcciones de seguridad. |

## 3. Resolución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: El encabezado no se fija o se superpone a otros elementos. ¿Qué debo hacer?**
R1: Esto a menudo ocurre debido a conflictos con el CSS o JavaScript de su tema, especialmente si su tema tiene una estructura de encabezado muy personalizada.
\* **Borrar caché:** Primero, intente borrar la caché de PrestaShop. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la parte superior derecha.
\* **Compatibilidad del tema:** El módulo está diseñado para funcionar con temas estándar de PrestaShop (como Classic) y temas con estructuras similares. Si tiene un tema muy personalizado, es posible que necesite pequeños ajustes de CSS.
\* **Contactar con soporte:** Si el problema persiste, recopile capturas de pantalla y detalles sobre su tema, y póngase en contacto con el soporte de MyPresta.eu. Ellos pueden ayudar a diagnosticar y proporcionar fragmentos de CSS personalizados si es necesario.

**P2: Mi encabezado se ve extraño o tiene espacio adicional cuando se vuelve fijo.**
R2: Esto puede ser un problema de estilo.
\* **Inspeccionar elemento:** Utilice las herramientas de desarrollo de su navegador (haga clic derecho en su encabezado y seleccione "Inspeccionar") para ver qué reglas CSS se están aplicando. Busque `position: fixed;` y `top: 0;`.
\* **Estilo del tema:** Su tema podría tener reglas específicas de relleno o margen que entran en conflicto. Es posible que deba agregar CSS personalizado para ajustar la apariencia del encabezado fijo. El soporte de MyPresta.eu puede guiarle.

**P3: ¿Este módulo ralentizará mi sitio web?**
R3: El módulo "Encabezado fijo" es muy ligero, utilizando un mínimo de JavaScript y CSS. Debería tener un impacto insignificante en la velocidad de carga y el rendimiento de su sitio web. El efecto se activa solo al desplazarse, por lo que no añade sobrecarga a la carga inicial de la página.

**P4: ¿Cómo traduzco el módulo si tuviera algún texto visible?**
R4: Aunque este módulo principalmente proporciona un efecto visual y no suele tener texto visible para el usuario, si alguna versión futura introduce texto configurable, lo traduciría a través de:
\* **Internacional > Traducciones** en su Back Office de PrestaShop.
\* Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Encabezado fijo" del menú desplegable del módulo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Encabezado fijo" es un módulo ligero de características de front-office diseñado para mejorar la experiencia del usuario al hacer que el encabezado principal sea fijo al desplazarse. Principalmente aprovecha JavaScript para detectar eventos de desplazamiento y aplicar clases CSS al elemento del encabezado, lo que luego activa el estilo `position: fixed`. Se adhiere a la estructura estándar del módulo de PrestaShop, utilizando el hook `displayHeader` para inyectar sus activos.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno. La funcionalidad del módulo se maneja completamente a través de JavaScript inyectado mediante un hook.
- **Controladores de Back-Office Admin**: Ninguno. La configuración se gestiona directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

- No se utilizan clases personalizadas ni definiciones de `ObjectModel`. El módulo opera manipulando elementos DOM existentes.

### 4.4 Activos de JavaScript (`views/js/`)

- **`fixedheader/fixedheader.js`**
  - **Alcance:** Front-office.
  - **Propósito:** Este script es responsable de la funcionalidad principal del encabezado fijo.
  - **Detalles:**
    - Escucha el evento `scroll` en el objeto `window`.
    - Determina la posición de desplazamiento y el desplazamiento inicial del elemento del encabezado.
    - Cuando el usuario se desplaza más allá de un cierto umbral (la altura inicial del encabezado), agrega una clase CSS específica (por ejemplo, `fixed-header-active` o similar, como se define en `fixedheader.css`) al contenedor principal del encabezado.
    - Cuando el usuario se desplaza hacia arriba por encima del umbral, elimina esta clase.
    - Probablemente apunta a un selector de encabezado común (por ejemplo, `#header`, `.header-container`, o similar, dependiendo de la estructura del tema) para aplicar el comportamiento fijo.
    - También puede manejar la adición de un `padding-top` al `body` o a un contenedor de contenido principal para evitar que el contenido "salte" o se oculte detrás del encabezado fijo.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`fixedheader/fixedheader.css`**
  - **Alcance:** Estilo del cliente de front-office.
  - **Propósito:** Proporciona las reglas CSS necesarias para hacer que el encabezado sea fijo cuando JavaScript agrega la clase de activación.
  - **Detalles:**
    - Define estilos para el estado activo del encabezado fijo. Las propiedades clave incluirán:
      - `position: fixed;`
      - `top: 0;`
      - `width: 100%;`
      - `z-index: 1000;` (o un valor alto para asegurar que permanezca por encima de otro contenido).
      - Potencialmente `box-shadow` o `background-color` para distinguir visualmente el encabezado fijo.
    - También podría incluir reglas para manejar el relleno o margen del `body` para evitar la superposición de contenido.
    - **Selectores de clase CSS clave que los desarrolladores pueden anular:** La clase principal agregada por el JS (por ejemplo, `.fixed-header-active` o similar) y el selector para el propio elemento del encabezado (por ejemplo, `#header`, `.header-container`). Los desarrolladores pueden anular estos estilos en el CSS personalizado de su tema para que coincidan con su diseño.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- No se utilizan archivos `.tpl` personalizados. El módulo inyecta su JavaScript y CSS directamente en la sección `<head>` a través del hook `displayHeader`.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: No se crean tablas de base de datos personalizadas. La configuración se almacena en `ps_configuration` utilizando claves como `MYPRESTA_UPDATES`, `UPDATE_FIXEDHEADER`, `UPDATEV_FIXEDHEADER`.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Inyecta los archivos CSS (`fixedheader.css`) y JavaScript (`fixedheader.js`) del módulo en la página, asegurando que se carguen antes de que se renderice el contenido de la página y estén disponibles para su ejecución inmediata. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y las últimas versiones del módulo "Encabezado fijo", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.

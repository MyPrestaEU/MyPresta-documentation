---
title: "Material Icons + Font Awesome - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Material Icons + Font Awesome para PrestaShop de MyPresta.eu."
sidebar:
  label: "Material Icons + Font Awesome - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Material Icons + Font Awesome en MyPresta.eu](https://mypresta.eu/modules/front-office-features/material-icons-font-awesome.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/material-icons-font-awesome/)
>
> ---


# Material Icons + Font Awesome

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No hay requisitos especiales más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo "Material Icons + Font Awesome". La encontrará navegando a **Módulos > Gestor de módulos**, buscando "Material Icons + Font Awesome" y haciendo clic en "Configurar".

#### **Añadir Font Awesome**

- **Qué hace este ajuste:** Este interruptor controla si la biblioteca de iconos Font Awesome se carga en el front-office de su tienda (lo que ven los clientes) y en el back-office (su panel de administración).
- **Efecto de cambiar este ajuste:**
  - *Cuando está activado:* El archivo CSS de Font Awesome se añadirá a la sección `<head>` de su sitio web, haciendo que todos los iconos de Font Awesome estén disponibles para su uso. Esto solucionará cualquier icono de Font Awesome que falte.
  - *Cuando está desactivado:* El archivo CSS de Font Awesome NO será cargado por este módulo. Si su tema u otro módulo ya carga Font Awesome, o si no lo necesita, puede desactivarlo para evitar cargarlo dos veces.
- **Valor recomendado:**
  - **Activado** si nota que faltan iconos de Font Awesome en su tienda o en el back-office, o si planea usar iconos de Font Awesome en su contenido.
  - **Desactivado** si todos los iconos de Font Awesome ya se muestran correctamente (lo que significa que su tema u otro módulo ya lo está cargando) para evitar una carga redundante.
- **Escenario / ejemplo de comerciante:** Ha instalado un nuevo módulo de pago, y sus iconos de método de pago (por ejemplo, un símbolo de tarjeta de crédito) se muestran como cuadros vacíos. Si estos iconos se basan en Font Awesome, activar este ajuste hará que aparezcan correctamente.

#### **Añadir Material Icons**

- **Qué hace este ajuste:** Este interruptor controla si la biblioteca de Material Icons (de Google) se carga en el front-office y back-office de su tienda.
- **Efecto de cambiar este ajuste:**
  - *Cuando está activado:* El archivo CSS de Material Icons se añadirá a la sección `<head>` de su sitio web, haciendo que todos los Material Icons estén disponibles para su uso. Esto solucionará cualquier Material Icon que falte.
  - *Cuando está desactivado:* El archivo CSS de Material Icons NO será cargado por este módulo. Si su tema u otro módulo ya carga Material Icons, o si no los necesita, puede desactivarlo.
- **Valor recomendado:**
  - **Activado** si nota que faltan Material Icons en su tienda o en el back-office.
  - **Desactivado** si todos los Material Icons ya se muestran correctamente (lo que significa que su tema u otro módulo ya los está cargando) para evitar una carga redundante.
- **Escenario / ejemplo de comerciante:** Su tema utiliza Material Icons para sus flechas de navegación o algunos elementos de la página de producto, pero después de una actualización del tema, han desaparecido. Activar este ajuste probablemente los hará volver.

#### **Tabla de Referencia Rápida de Configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Añadir Font Awesome | Activado (si es necesario) | Carga la biblioteca de iconos Font Awesome para el front y back office. Soluciona la falta de iconos de Font Awesome. |
| Configuración del Módulo | Añadir Material Icons | Activado (si es necesario) | Carga la biblioteca de Material Icons para el front y back office. Soluciona la falta de Material Icons. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: He habilitado los ajustes, pero los iconos siguen faltando. ¿Qué debo hacer?**
R: Primero, borre la caché de PrestaShop. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. Además, borre la caché de su navegador (Ctrl+F5 o Cmd+Shift+R). Si los iconos siguen faltando, es posible que los iconos que busca pertenezcan a una biblioteca de iconos diferente no cubierta por este módulo, o que haya un conflicto de CSS en su tema.

**P: ¿Este módulo ralentizará mi sitio web?**
R: El módulo carga archivos CSS estándar para las bibliotecas de iconos. Si solo habilita las bibliotecas que necesita y no están ya cargadas por su tema, el impacto en el rendimiento es mínimo y necesario para una visualización correcta. Si habilita una biblioteca que ya está cargada por su tema, la cargará dos veces, lo que puede causar una ligera ralentización. Siempre verifique si su tema ya incluye estas bibliotecas antes de habilitarlas aquí.

**P: Mi tema personalizado tiene su propio conjunto de iconos. ¿Este módulo interferirá?**
R: No debería interferir directamente. Este módulo añade las bibliotecas de iconos especificadas. Si su tema utiliza un conjunto de iconos diferente (por ejemplo, SVG personalizados u otra biblioteca de iconos de fuentes), este módulo simplemente añadirá Font Awesome y/o Material Icons junto a él. Si experimenta conflictos, puede intentar deshabilitar una o ambas opciones en el módulo para ver si resuelve el problema.

**P: ¿Cómo sé si mi tema ya carga Font Awesome o Material Icons?**
R: La forma más fácil es hacer clic derecho en la página de su tienda (front-office) y seleccionar "Ver código fuente de la página" o "Inspeccionar elemento". Luego, busque "font-awesome.css" o "material-icons.css" dentro de la sección `<head>`. Si los encuentra, es probable que su tema ya los esté cargando. Alternativamente, si todos los iconos se muestran correctamente sin este módulo, entonces su tema u otro módulo ya lo está gestionando.

**P: ¿Puedo usar Font Awesome y Material Icons al mismo tiempo?**
R: Sí, absolutamente. Puede habilitar ambas opciones en la configuración del módulo. Esto a menudo es necesario si diferentes partes de su tienda (por ejemplo, su tema y un módulo de terceros) dependen de diferentes bibliotecas de iconos.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Material Icons + Font Awesome" es un módulo ligero de PrestaShop diseñado principalmente para inyectar hojas de estilo CSS externas para bibliotecas de iconos. Sigue una estructura de módulo estándar de PrestaShop, aprovechando los hooks para integrar su funcionalidad en el front-office y el back-office. No introduce controladores, modelos o tablas de base de datos personalizados, centrándose únicamente en la gestión de activos.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador personalizado de front-office o back-office. Toda la lógica se maneja dentro del archivo principal del módulo (`fonticons.php`) a través de hooks.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no define ninguna clase personalizada ni extiende `ObjectModel`. Toda la configuración se almacena directamente en `ps_configuration` utilizando las claves definidas a continuación.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de Estilo CSS (`views/css/`)

La funcionalidad principal del módulo se basa en estos archivos CSS:

- **`fonticons/views/css/font-awesome.css`**:

  - **Alcance**: Front-office y Back-office.
  - **Propósito**: Contiene las reglas CSS y las declaraciones `@font-face` para la biblioteca de iconos Font Awesome. Este archivo es responsable de hacer que los iconos de Font Awesome estén disponibles en toda la tienda.
  - **Selectores de clase CSS clave**: `fa`, `fas`, `far`, `fal`, `fab` (para diferentes estilos de Font Awesome), seguidos de clases de iconos específicas como `fa-shopping-cart`, `fa-user`, etc. Los desarrolladores pueden anularlos apuntando a estas clases en el CSS de su tema.
- **`fonticons/views/css/material-icons.css`**:

  - **Alcance**: Front-office y Back-office.
  - **Propósito**: Contiene las reglas CSS y las declaraciones `@font-face` para la biblioteca de Material Icons de Google. Este archivo hace que los Material Icons estén disponibles.
  - **Selectores de clase CSS clave**: `material-icons`. Los iconos suelen renderizarse colocando el nombre de la ligadura del icono dentro de un elemento con esta clase (por ejemplo, `<i class="material-icons">shopping_cart</i>`). Los desarrolladores pueden anular el estilo de esta clase.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **`fonticons/views/advert.tpl`**:
  - **Alcance**: Back-office (página de configuración del módulo).
  - **Propósito**: Esta plantilla se utiliza para mostrar un anuncio o mensaje promocional dentro de la página de configuración del módulo en el back-office de PrestaShop. Se renderiza mediante el método `getContent()`.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:
  Este módulo no crea ninguna tabla de base de datos personalizada. Almacena sus ajustes de configuración en la tabla estándar `ps_configuration`.

  - Entradas de `ps_configuration`:
    - `fonticons_FA`: Almacena el estado (1 para activado, 0 para desactivado) de la inclusión de Font Awesome para el front-office.
    - `fonticons_MI`: Almacena el estado (1 para activado, 0 para desactivado) de la inclusión de Material Icons para el front-office.
    - `BO_fonticons_FA`: Almacena el estado (1 para activado, 0 para desactivado) de la inclusión de Font Awesome para el back-office.
    - `BO_fonticons_MI`: Almacena el estado (1 para activado, 0 para desactivado) de la inclusión de Material Icons para el back-office.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página del front-office. | Se utiliza para cargar los archivos CSS de Font Awesome y/o Material Icons para la parte de la tienda visible para el cliente, basándose en la configuración `fonticons_FA` y `fonticons_MI`. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un AdminController está configurando sus activos multimedia (CSS/JS). | Se utiliza para cargar los archivos CSS de Font Awesome y/o Material Icons para el back-office de PrestaShop, basándose en la configuración `BO_fonticons_FA` y `BO_fonticons_MI`. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Allí encontrará sus módulos comprados y enlaces de descarga. Para asistencia técnica o cualquier pregunta, utilice los canales de soporte proporcionados en MyPresta.eu.

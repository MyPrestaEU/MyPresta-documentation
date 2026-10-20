---
title: "Pestaña de ofertas en la página de inicio (promociones) - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Pestaña de ofertas en la página de inicio (promociones)' de MyPresta.eu."
sidebar:
  label: "Pestaña de ofertas en la página de inicio (promociones)"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Homepage tab on sale (promotions) en MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-on-sale-promotions.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/homepage-tab-on-sale-promotions/)
>
> ---


# Pestaña de ofertas en la página de inicio (promociones)

## 1. Requisitos y compatibilidad
-   **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilidad con PHP**: PHP 7.1 - 8.5
-   **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Esta es la pantalla de configuración principal y única para el módulo "Pestaña de ofertas en la página de inicio (promociones)". Puede acceder a ella navegando a **Módulos > Gestor de módulos** y buscando "Pestaña de ofertas en la página de inicio (promociones)", luego haciendo clic en el botón "Configurar".

#### Ajustes y opciones:

-   **Número de productos a mostrar**
    -   **Qué hace este ajuste:** Esto controla cuántos productos se mostrarán en la pestaña "En oferta" de su página de inicio. Si tiene más productos en oferta que este número, solo se mostrará la cantidad especificada.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece un número mayor (por ejemplo, 10):* Más productos en oferta serán visibles para sus clientes a la vez, lo que potencialmente aumenta la posibilidad de que encuentren algo que les guste. Sin embargo, podría hacer la página más larga y requerir más desplazamiento.
        -   *Cuando se establece un número menor (por ejemplo, 4):* Se mostrarán menos productos en oferta, lo que hará que la pestaña sea más concisa y potencialmente más rápida de cargar. Esto puede ser bueno para un diseño limpio, pero podría ocultar algunas ofertas atractivas.
    -   **Valor recomendado:** Comience con un valor entre **8 y 12**. Este es un buen equilibrio para la mayoría de los temas, proporcionando suficiente variedad sin abrumar al cliente.
    -   **Escenario / ejemplo de comerciante:** Si tiene muchos productos en oferta y desea destacar la variedad, podría configurarlo en 12. Si prefiere un aspecto minimalista o solo tiene unas pocas promociones clave, configurarlo en 6 podría ser mejor.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista             | Ajuste / Opción               | Predeterminado / Recomendado | Propósito e impacto
El módulo de PrestaShop "Pestaña de ofertas en la página de inicio (promociones)" es una herramienta simple pero efectiva para destacar los productos que actualmente están en oferta especial o descuento directamente en la página de inicio de su tienda. Crea una nueva pestaña en su página de inicio, junto a las existentes como "Nuevos productos" o "Más vendidos", dedicada específicamente a mostrar estos artículos promocionales.

## 3. Requisitos y compatibilidad
-   **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilidad con PHP**: PHP 7.1 - 8.5 (Siempre extendiéndose a PHP 8.5)
-   **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 4. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 4.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Esta es la pantalla de configuración principal y única para el módulo "Pestaña de ofertas en la página de inicio (promociones)". Puede acceder a ella yendo a **Módulos > Gestor de módulos**, buscando "Pestaña de ofertas en la página de inicio (promociones)" y luego haciendo clic en el botón "Configurar".

#### Ajustes y opciones:

-   **Número de productos a mostrar**
    -   **Qué hace este ajuste:** Este ajuste determina el número máximo de productos con descuento que se mostrarán dentro de la pestaña "En oferta" en la página de inicio de su tienda. Si tiene más productos actualmente en oferta que el número que especifique aquí, el módulo solo mostrará esta cantidad establecida.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado / se establece un número mayor (por ejemplo, 12):* Sus clientes verán una selección más grande de productos promocionales cuando hagan clic en la pestaña "En oferta". Esto puede ser beneficioso para tiendas con muchos descuentos activos, ofreciendo más opciones y potencialmente aumentando la probabilidad de una compra. Sin embargo, mostrar demasiados productos podría hacer la página más larga y podría aumentar ligeramente el tiempo de carga.
        -   *Cuando está deshabilitado / se establece un número menor (por ejemplo, 4):* Se verán menos productos en oferta. Esto puede crear una visualización más limpia y enfocada, lo que podría ser preferible si solo tiene unas pocas promociones clave o desea mantener su página de inicio muy concisa. También puede conducir a una carga de página más rápida.
    -   **Valor recomendado:** Un buen punto de partida es **8 a 10 productos**. Esto proporciona una selección decente sin abrumar al cliente ni hacer la página excesivamente larga. Puede ajustarlo según su número promedio de artículos en oferta y el diseño de su tema.
    -   **Escenario / ejemplo de comerciante:**
        -   *Escenario 1 (Inventario grande, ventas frecuentes):* Realiza promociones semanales con más de 50 productos en oferta. Podría configurarlo en **12** para dar a los clientes una buena visión general de la variedad de ofertas disponibles directamente desde la página de inicio.
        -   *Escenario 2 (Tienda boutique, pocas promociones clave):* Normalmente tiene solo 3-5 artículos de alto valor en oferta en un momento dado. Podría configurarlo en **6** para asegurarse de que todas sus promociones clave sean visibles sin espacios vacíos o desplazamientos innecesarios.

### 4.2 Tabla de referencia rápida de configuración

| Pantalla / Vista             | Ajuste / Opción               | Predeterminado / Recomendado | Propósito e impacto
La

---
title: "Código de cupón por 'Me gusta' en Facebook - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Código de cupón por 'Me gusta' en Facebook' de MyPresta.eu."
sidebar:
  label: "Código de cupón por 'Me gusta' en Facebook"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook like voucher code en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-voucher-code.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-like-voucher-code/)
>
> ---


# Código de cupón por 'Me gusta' en Facebook

## 1. Requisitos y Compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y cualquier módulo que interactúe con APIs externas como Facebook.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)
Esta es la pantalla de configuración principal para el módulo "Código de cupón por 'Me gusta' en Facebook", accesible después de la instalación haciendo clic en el botón "Configurar". Aquí definirás cómo aparece el botón de 'Me gusta' de Facebook y cómo se generan los códigos de cupón.

#### **URL de la página de Facebook**
- **Qué hace esta configuración:** Este es el ajuste más crucial. Le indica al módulo a qué página de Facebook deben darle "Me gusta" tus clientes para recibir el cupón.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece la URL de tu página de Facebook (por ejemplo, `https://www.facebook.com/MyPresta.eu`):* El botón "Me gusta" de tu tienda se vinculará directamente y rastreará los 'Me gusta' de esta página de Facebook específica.
  - *Cuando se deja vacío o se establece incorrectamente:* El botón "Me gusta" no funcionará correctamente, o podría vincularse a una página inexistente, impidiendo que los clientes reciban cupones.
- **Valor recomendado:** Introduce la URL completa de tu página oficial de negocios de Facebook.
- **Escenario / ejemplo de comerciante:** Si tu página de Facebook es `https://www.facebook.com/mitiendagenial`, deberías introducir esa URL exacta aquí.

#### **Prefijo del código de cupón**
- **Qué hace esta configuración:** Te permite añadir un prefijo personalizado a todos los códigos de cupón generados por este módulo. Esto te ayuda a identificar fácilmente qué cupones provienen de tu promoción de Facebook.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en "FB":* Todos los códigos de cupón generados comenzarán con "FB" (por ejemplo, FB123456).
  - *Cuando se deja vacío:* Los códigos de cupón se generarán sin un prefijo específico, lo que los hará más difíciles de distinguir de otros tipos de cupones.
- **Valor recomendado:** Un prefijo corto y memorable como "FB", "LIKE" o "SOCIAL".
- **Escenario / ejemplo de comerciante:** Usar "FB" te permite filtrar rápidamente tus códigos de cupón en el Back Office de PrestaShop para ver cuántos se generaron a través de este módulo.

#### **Valor del código de cupón**
- **Qué hace esta configuración:** Define el valor de descuento del código de cupón. Puede ser una cantidad fija o un porcentaje.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en "10" y "Porcentaje":* Los clientes reciben un 10% de descuento.
  - *Cuando se establece en "5" y "Cantidad":* Los clientes reciben un descuento de 5 $ (o tu moneda predeterminada).
- **Valor recomendado:** Un valor que sea lo suficientemente atractivo como para fomentar una compra, pero también sostenible para tus márgenes de beneficio (por ejemplo, 5, 10, 15).
- **Escenario / ejemplo de comerciante:** Ofrecer "10" y "Porcentaje" para un descuento del 10% es una estrategia común y efectiva para animar a los compradores primerizos.

#### **Tipo de código de cupón**
- **Qué hace esta configuración:** Determina si el código de cupón ofrece un descuento porcentual o un descuento de cantidad fija.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en "Porcentaje":* El "Valor del código de cupón" se interpretará como un porcentaje (por ejemplo, 10% de descuento).
  - *Cuando se establece en "Cantidad":* El "Valor del código de cupón" se interpretará como una cantidad monetaria fija (por ejemplo, 10 $ de descuento).
- **Valor recomendado:** "Porcentaje" suele ser más atractivo ya que se escala con el valor del pedido, pero "Cantidad" puede ser efectivo para artículos de menor precio o promociones específicas.
- **Escenario / ejemplo de comerciante:** Si quieres dar un descuento fijo de 5 $ independientemente del tamaño del pedido, elige "Cantidad". Si quieres dar un descuento que aumente con el valor del pedido, elige "Porcentaje".

#### **Cantidad mínima del código de cupón**
- **Qué hace esta configuración:** Establece un total mínimo de pedido (antes del envío) que un cliente debe alcanzar para poder usar el código de cupón.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en "50":* El cupón solo se puede usar si el total del carrito es de 50 $ o más.
  - *Cuando se deja vacío o se establece en "0":* El cupón se puede usar en cualquier cantidad de pedido.
- **Valor recomendado:** Un valor que anime a los clientes a añadir más artículos a su carrito, aumentando el valor medio del pedido (por ejemplo, 25, 50).
- **Escenario / ejemplo de comerciante:** Si tu valor medio de pedido es de 40 $, establecer una cantidad mínima de 50 $ para un cupón del 10% anima a los clientes a añadir un artículo extra para calificar para el descuento.

#### **Días de caducidad del código de cupón**
- **Qué hace esta configuración:** Define cuántos días será válido el código de cupón generado desde el momento en que se emite.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en "7":* El código de cupón caducará 7 días después de que el cliente lo reciba.
  - *Cuando se deja vacío o se establece en "0":* El código de cupón no tendrá fecha de caducidad (o una muy larga por defecto establecida por PrestaShop).
- **Valor recomendado:** Un plazo razonable para crear urgencia sin ser demasiado restrictivo (por ejemplo, 7, 14, 30 días).
- **Escenario / ejemplo de comerciante:** Establecerlo en "7" días anima a los clientes a realizar una compra antes, evitando que se olviden del cupón.

#### **Descripción del código de cupón**
- **Qué hace esta configuración:** Te permite añadir una descripción personalizada al código de cupón generado en tu Back Office de PrestaShop. Esto te ayuda a rastrear el propósito del cupón.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en "Promoción 'Me gusta' de Facebook":* Esta descripción será visible cuando veas los detalles del cupón en tu Back Office de PrestaShop, dejando claro de dónde se originó el cupón.
  - *Cuando se deja vacío:* El cupón no tendrá una descripción específica, lo que dificultará la identificación de su origen.
- **Valor recomendado:** Una descripción clara y concisa como "Cupón 'Me gusta' de Facebook" o "Promoción de Redes Sociales".
- **Escenario / ejemplo de comerciante:** Usar "Promoción 'Me gusta' de Facebook" ayuda a tu equipo de atención al cliente a comprender el contexto del cupón si un cliente tiene preguntas al respecto.

#### **Mostrar bloque en**
- **Qué hace esta configuración:** Determina dónde aparecerá el bloque del botón "Me gusta" de Facebook en el front office de tu tienda.
- **Efecto de cambiar esta configuración:**
  - *Cuando se selecciona "Cabecera":* El bloque aparece en la parte superior de cada página.
  - *Cuando se selecciona "Columna izquierda":* El bloque aparece en la barra lateral izquierda.
  - *Cuando se selecciona "Columna derecha":* El bloque aparece en la barra lateral derecha.
  - *Cuando se selecciona "Página de producto":* El bloque aparece en las páginas de productos individuales.
  - *Cuando se selecciona "Pie de página":* El bloque aparece en la parte inferior de cada página.
- **Valor recomendado:** "Cabecera" o "Página de producto" para una máxima visibilidad e impacto, o "Columna izquierda/derecha" si prefieres una ubicación menos intrusiva.
- **Escenario / ejemplo de comerciante:** Colocarlo en la "Cabecera" asegura que cada visitante lo vea. Colocarlo en la "Página de producto" se dirige a los clientes que ya están interesados en realizar una compra.

#### **Mensaje emergente del código de cupón**
- **Qué hace esta configuración:** Este es el mensaje que los clientes verán en la ventana emergente junto con su código de cupón después de darle "Me gusta" a tu página de Facebook.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en "¡Gracias por darnos 'Me gusta'! Aquí tienes tu código de descuento: {voucher_code}":* El cliente verá este mensaje exacto con su código único insertado.
  - *Cuando se deja vacío:* El cliente podría ver solo el código sin ningún texto que lo acompañe, lo que podría ser confuso.
- **Valor recomendado:** Un mensaje amigable y claro que agradezca al cliente y declare explícitamente que el código es para un descuento. **Incluye siempre `{voucher_code}`** para que se muestre el código real.
- **Escenario / ejemplo de comerciante:** "¡Gracias por unirte a nuestra comunidad! Aquí tienes un regalo especial para ti: {voucher_code}. ¡Disfruta de tus compras!"

#### **Título emergente del código de cupón**
- **Qué hace esta configuración:** Establece el título de la ventana emergente que muestra el código de cupón.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en "¡Tu descuento exclusivo!":* Este título aparecerá en la parte superior de la ventana emergente.
  - *Cuando se deja vacío:* La ventana emergente podría tener un título genérico o ningún título, lo que es menos profesional.
- **Valor recomendado:** Un título pegadizo y claro que refuerce la recompensa (por ejemplo, "¡Tu cupón gratis!", "¡Gracias por darnos 'Me gusta'!").
- **Escenario / ejemplo de comerciante:** "¡Tu descuento exclusivo!" le dice inmediatamente al cliente que ha recibido una valiosa recompensa.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
"""

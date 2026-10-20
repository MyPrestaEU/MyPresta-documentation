---
title: "Homepage-Tab neue Produkte – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Homepage-Tab neue Produkte' von MyPresta.eu."
sidebar:
  label: "Homepage-Tab neue Produkte"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Homepage tab new products auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/homepage-tab-new-products.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/homepage-tab-new-products/)
>
> ---


# Homepage-Tab neue Produkte

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Klicken Sie nach der Installation im Modul-Manager neben dem Modul „Homepage-Tab neue Produkte“ auf „Konfigurieren“. Sie gelangen zum Hauptkonfigurationsbildschirm.

#### **Anzahl der anzuzeigenden Produkte**
-   **Was diese Einstellung bewirkt:** Dies steuert, wie viele Ihrer neuesten Produkte im Tab „Neue Produkte“ auf Ihrer Homepage angezeigt werden.
-   **Auswirkungen einer Änderung dieser Einstellung:**
    -   *Bei Einstellung auf eine höhere Zahl (z.B. 12):* Mehr neue Produkte werden den Kunden sichtbar, ohne dass sie zu einer vollständigen „Neue Produkte“-Seite navigieren müssen. Dies kann für Shops mit einem hohen Volumen an Neuheiten großartig sein.
    -   *Bei Einstellung auf eine niedrigere Zahl (z.B. 4):* Weniger Produkte werden angezeigt, was zu einem saubereren, weniger überladenen Aussehen führt. Dies könnte bevorzugt werden, wenn Sie nur die absolut frischesten Artikel hervorheben möchten oder begrenzten Platz haben.
-   **Empfohlener Wert:** Beginnen Sie mit `8` oder `12`. Passen Sie dies basierend auf dem Layout Ihres Themes und der Anzahl der Produkte an, die Sie typischerweise hinzufügen.
-   **Händlerszenario / Beispiel:** Wenn Sie ein Modegeschäft betreiben und wöchentlich 20 neue Artikel hinzufügen, stellt die Einstellung auf `12` sicher, dass immer eine gute Auswahl sichtbar ist. Wenn Sie hochwertige Nischenprodukte verkaufen und nur 2-3 neue Artikel monatlich hinzufügen, könnten `4` ausreichen, um leere Flächen zu vermeiden.

#### **Produktlistenklassen**
-   **Was diese Einstellung bewirkt:** Diese erweiterte Einstellung ermöglicht es Ihnen, dem Container, der die Liste der neuen Produkte enthält, benutzerdefinierte CSS-Klassen hinzuzufügen. Dies wird hauptsächlich für Styling-Zwecke verwendet, oft um sich nahtlos in das spezifische Design Ihres PrestaShop-Themes zu integrieren.
-   **Auswirkungen einer Änderung dieser Einstellung:**
    -   *Wenn Klassen hinzugefügt werden (z.B. `product-grid-container my-custom-style`):* Das CSS Ihres Themes oder Ihr benutzerdefiniertes CSS kann diese Klassen dann ansprechen, um spezifisches Styling (z.B. Änderung des Spaltenlayouts, Abstände, Schriftgrößen, Farben) auf die neue Produktliste anzuwenden.
    -   *Wenn leer gelassen:* Das Modul verwendet sein Standard-Styling oder erbt Stile von der allgemeinen Produktliste Ihres Themes.
-   **Empfohlener Wert:** Leer lassen, es sei denn, Sie oder Ihr Webentwickler müssen spezifisches benutzerdefiniertes Styling auf die Produktliste anwenden. Wenn Sie unsicher sind, ändern Sie diese Einstellung nicht.
-   **Händlerszenario / Beispiel:** Ihr Theme zeigt Produktraster mit 3 Spalten an, aber Sie möchten, dass der Tab „Neue Produkte“ 4 Spalten anzeigt. Ihr Webentwickler könnte Ihnen sagen, dass Sie hier eine Klasse wie `col-lg-3` (wenn Ihr Theme Bootstrap-Grid-Klassen verwendet) hinzufügen und dann benutzerdefiniertes CSS hinzufügen sollen, damit es funktioniert.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung
|---|---|---|---|
| Modulkonfigurationsseite | Anzahl der anzuzeigenden Produkte | 8 oder 12 | Steuert, wie viele neue Produkte im Tab angezeigt werden. Höhere Zahlen zeigen mehr Produkte, niedrigere Zahlen sorgen für ein saubereres Aussehen.
| Modulkonfigurationsseite | Produktlistenklassen | Leer | Ermöglicht das Hinzufügen benutzerdefinierter CSS-Klassen für Styling-Zwecke. Nur ändern, wenn spezifisches Styling erforderlich ist.

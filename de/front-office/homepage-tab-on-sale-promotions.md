---
title: "Startseiten-Tab „Im Angebot“ (Aktionen) – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Startseiten-Tab „Im Angebot“ (Aktionen)“ von MyPresta.eu."
sidebar:
  label: "Startseiten-Tab „Im Angebot“ (Aktionen)"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Homepage tab on sale (promotions) auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/homepage-tab-on-sale-promotions.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/homepage-tab-on-sale-promotions/)
>
> ---


# Startseiten-Tab „Im Angebot“ (Aktionen)

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Dies ist der primäre und einzige Konfigurationsbildschirm für das Modul „Startseiten-Tab „Im Angebot“ (Aktionen)“. Sie können darauf zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, nach „Startseiten-Tab „Im Angebot“ (Aktionen)“ suchen und dann auf die Schaltfläche „Konfigurieren“ klicken.

#### Einstellungen & Optionen:

-   **Anzahl der anzuzeigenden Produkte**
    -   **Was diese Einstellung bewirkt:** Diese Einstellung bestimmt die maximale Anzahl der reduzierten Produkte, die im Tab „Im Angebot“ auf der Startseite Ihres Shops angezeigt werden. Wenn Sie mehr Produkte im Angebot haben, als Sie hier angeben, zeigt das Modul nur diese festgelegte Menge an.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert / auf eine höhere Zahl eingestellt (z.B. 12):* Ihre Kunden sehen eine größere Auswahl an Aktionsprodukten, wenn sie auf den Tab „Im Angebot“ klicken. Dies kann für Shops mit vielen aktiven Rabatten von Vorteil sein, da es mehr Auswahl bietet und die Wahrscheinlichkeit eines Kaufs potenziell erhöht. Das Anzeigen von zu vielen Produkten kann jedoch die Seite länger machen und die Ladezeit leicht erhöhen.
        -   *Wenn deaktiviert / auf eine niedrigere Zahl eingestellt (z.B. 4):* Es werden weniger Aktionsprodukte angezeigt. Dies kann eine sauberere, fokussiertere Anzeige schaffen, was bevorzugt werden könnte, wenn Sie nur wenige wichtige Aktionen haben oder Ihre Startseite sehr prägnant halten möchten. Es kann auch zu schnelleren Seitenladezeiten führen.
    -   **Empfohlener Wert:** Ein guter Ausgangspunkt sind **8 bis 10 Produkte**. Dies bietet eine angemessene Auswahl, ohne den Kunden zu überfordern oder die Seite übermäßig lang zu machen. Sie können dies basierend auf Ihrer durchschnittlichen Anzahl von Angebotsartikeln und dem Layout Ihres Themes anpassen.
    -   **Händlerszenario / Beispiel:**
        -   *Szenario 1 (Großer Lagerbestand, häufige Verkäufe):* Sie führen wöchentliche Aktionen mit über 50 Produkten im Angebot durch. Sie könnten dies auf **12** einstellen, um Kunden einen guten Überblick über die Vielfalt der verfügbaren Angebote direkt von der Startseite aus zu geben.
        -   *Szenario 2 (Boutique-Shop, wenige wichtige Aktionen):* Sie haben typischerweise nur 3-5 hochwertige Artikel gleichzeitig im Angebot. Sie könnten dies auf **6** einstellen, um sicherzustellen, dass alle Ihre wichtigen Aktionen sichtbar sind, ohne leere Bereiche oder unnötiges Scrollen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht      | Einstellung / Option             | Standard / Empfohlen | Zweck & Auswirkung
Das PrestaShop-Modul „Startseiten-Tab „Im Angebot“ (Aktionen)“ ist ein einfaches, aber effektives Tool, um Produkte, die derzeit im Sonderangebot oder mit Rabatt angeboten werden, direkt auf der Startseite Ihres Shops hervorzuheben. Es erstellt einen neuen Tab auf Ihrer Startseite, neben bestehenden wie „Neue Produkte“ oder „Bestseller“, der speziell der Anzeige dieser Aktionsartikel gewidmet ist.

## 3. Anforderungen & Kompatibilität
-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 7.1 - 8.5 (Wird immer auf PHP 8.5 erweitert)
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 4. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 4.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Dies ist der primäre und einzige Konfigurationsbildschirm für das Modul „Startseiten-Tab „Im Angebot“ (Aktionen)“. Sie können darauf zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, nach „Startseiten-Tab „Im Angebot“ (Aktionen)“ suchen und dann auf die Schaltfläche „Konfigurieren“ klicken.

#### Einstellungen & Optionen:

-   **Anzahl der anzuzeigenden Produkte**
    -   **Was diese Einstellung bewirkt:** Diese Einstellung bestimmt die maximale Anzahl der reduzierten Produkte, die im Tab „Im Angebot“ auf der Startseite Ihres Shops angezeigt werden. Wenn Sie mehr Produkte im Angebot haben, als Sie hier angeben, zeigt das Modul nur diese festgelegte Menge an.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert / auf eine höhere Zahl eingestellt (z.B. 12):* Ihre Kunden sehen eine größere Auswahl an Aktionsprodukten, wenn sie auf den Tab „Im Angebot“ klicken. Dies kann für Shops mit vielen aktiven Rabatten von Vorteil sein, da es mehr Auswahl bietet und die Wahrscheinlichkeit eines Kaufs potenziell erhöht. Das Anzeigen von zu vielen Produkten kann jedoch die Seite länger machen und die Ladezeit leicht erhöhen.
        -   *Wenn deaktiviert / auf eine niedrigere Zahl eingestellt (z.B. 4):* Es werden weniger Aktionsprodukte angezeigt. Dies kann eine sauberere, fokussiertere Anzeige schaffen, was bevorzugt werden könnte, wenn Sie nur wenige wichtige Aktionen haben oder Ihre Startseite sehr prägnant halten möchten. Es kann auch zu schnelleren Seitenladezeiten führen.
    -   **Empfohlener Wert:** Ein guter Ausgangspunkt sind **8 bis 10 Produkte**. Dies bietet eine angemessene Auswahl, ohne den Kunden zu überfordern oder die Seite übermäßig lang zu machen. Sie können dies basierend auf Ihrer durchschnittlichen Anzahl von Angebotsartikeln und dem Layout Ihres Themes anpassen.
    -   **Händlerszenario / Beispiel:**
        -   *Szenario 1 (Großer Lagerbestand, häufige Verkäufe):* Sie führen wöchentliche Aktionen mit über 50 Produkten im Angebot durch. Sie könnten dies auf **12** einstellen, um Kunden einen guten Überblick über die Vielfalt der verfügbaren Angebote direkt von der Startseite aus zu geben.
        -   *Szenario 2 (Boutique-Shop, wenige wichtige Aktionen):* Sie haben typischerweise nur 3-5 hochwertige Artikel gleichzeitig im Angebot. Sie könnten dies auf **6** einstellen, um sicherzustellen, dass alle Ihre wichtigen Aktionen sichtbar sind, ohne leere Bereiche oder unnötiges Scrollen.

### 4.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht      | Einstellung / Option             | Standard / Empfohlen | Zweck & Auswirkung
Das

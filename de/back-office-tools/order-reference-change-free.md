---
title: "Bestellreferenz ändern kostenlos - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Bestellreferenz ändern kostenlos“ von MyPresta.eu."
sidebar:
  label: "Bestellreferenz ändern kostenlos - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Order reference change free auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/order-reference-change-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/order-reference-change-free/)
>
> ---


# Bestellreferenz ändern kostenlos

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Keine besonderen Anforderungen über eine Standard-PrestaShop-Hosting-Umgebung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modul „Bestellreferenz ändern kostenlos“. Sie sehen den Hauptkonfigurationsbildschirm.

#### **Bestellreferenzformat**

Dies ist die Kerneinstellung des Moduls, mit der Sie das Muster für Ihre Bestellreferenznummern definieren können.

- **Was diese Einstellung bewirkt:** Dieses Eingabefeld ermöglicht es Ihnen, eine Vorlage für die Generierung neuer Bestellreferenznummern festzulegen. Sie können eine Kombination aus Sonderzeichen und Platzhaltern verwenden, um Ihr gewünschtes Format zu erstellen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf ein bestimmtes Format eingestellt (z. B. `[0-9]{6}`):* Alle neuen Bestellungen erhalten eine Referenznummer, die diesem Muster streng folgt. Zum Beispiel würde `[0-9]{6}` eine 6-stellige numerische Referenz wie `123456` generieren.
  - *Wenn auf Standard belassen (PrestaShops Standardverhalten):* Das Modul ändert die Generierung der Bestellreferenz nicht, und PrestaShop verwendet sein Standard-alphanumerisches Format (z. B. `ABCDEF123`).
- **Empfohlener Wert:** Dies hängt vollständig von Ihren Geschäftsanforderungen ab.
  - Wenn Sie eine einfache, rein numerische Referenz benötigen, versuchen Sie `[0-9]{6}` für eine 6-stellige Zahl.
  - Wenn Sie eine Mischung aus Großbuchstaben und Zahlen wünschen, würde `[A-Z0-9]{8}` eine 8-stellige alphanumerische Referenz ergeben.
  - Sie können auch statische Präfixe hinzufügen, z. B. würde `MYSTORE-[0-9]{5}` `MYSTORE-12345` generieren.
- **Händlerszenario / Beispiel:**
  - **Szenario 1: Rein numerische Referenzen für die Buchhaltung.** Ihre Buchhaltungssoftware erfordert, dass alle Bestellreferenzen rein numerisch und 8-stellig sind. Sie würden dies auf `[0-9]{8}` einstellen.
  - **Szenario 2: Kürzere, einprägsame Referenzen.** Sie möchten kürzere, 6-stellige Referenzen, die nur Großbuchstaben und Zahlen verwenden, um die Kundenkommunikation zu erleichtern. Sie würden dies auf `[A-Z0-9]{6}` einstellen.
  - **Szenario 3: Markenreferenzen.** Sie möchten, dass alle Referenzen mit dem Anfangsbuchstaben Ihrer Marke gefolgt von einer 5-stelligen Zahl beginnen. Sie würden dies auf `M-[0-9]{5}` einstellen.

**Verfügbare Platzhalter & Zeichen:**
Das Modul verwendet eine reguläre Ausdrucks-ähnliche Syntax zur Definition des Formats:

- `[0-9]`: Repräsentiert eine einzelne Ziffer von 0 bis 9.
- `[a-z]`: Repräsentiert einen einzelnen Kleinbuchstaben von a bis z.
- `[A-Z]`: Repräsentiert einen einzelnen Großbuchstaben von A bis Z.
- `[a-zA-Z]`: Repräsentiert einen einzelnen Buchstaben (Groß- oder Kleinbuchstabe).
- `[A-Z0-9]`: Repräsentiert einen einzelnen Großbuchstaben oder eine Ziffer.
- `{n}`: Gibt an, dass das vorhergehende Zeichen oder die Gruppe genau `n` Mal wiederholt werden soll. Zum Beispiel bedeutet `[0-9]{6}` 6 Ziffern.
- `{n,m}`: Gibt an, dass das vorhergehende Zeichen oder die Gruppe zwischen `n` und `m` Mal wiederholt werden soll.
- Jedes andere Zeichen (z. B. `-`, `_`, `MYSTORE-`) wird wörtlich in die Referenz aufgenommen.

**Wichtiger Hinweis:** Das Modul stellt sicher, dass die generierte Referenz eindeutig ist. Wenn eine generierte Referenz bereits existiert, versucht es, eine neue zu generieren, bis eine eindeutige Referenz gefunden wird.

#### **Speichern-Schaltfläche**

- **Was diese Einstellung bewirkt:** Diese Schaltfläche speichert alle Änderungen, die Sie auf der Konfigurationsseite vorgenommen haben.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Beim Klicken:* Ihr neues Bestellreferenzformat wird sofort auf alle *neuen* Bestellungen angewendet, die in Ihrem Shop aufgegeben werden. Bestehende Bestellreferenzen werden nicht geändert.
- **Empfohlener Wert:** Klicken Sie immer auf „Speichern“, nachdem Sie Änderungen vorgenommen haben, um sicherzustellen, dass diese angewendet werden.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Bestellreferenzformat | PrestaShop-Standard (alphanumerisch) | Definiert das Muster für neue Bestellreferenznummern (z. B. `[0-9]{6}`, `MYSTORE-[A-Z0-9]{5}`). Beeinflusst, wie neue Bestellungen in Ihrem Shop und auf Kundendokumenten referenziert werden. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Format geändert, aber alte Bestellungen haben immer noch die alte Referenz. Warum?**
A: Dieses Modul betrifft nur *neue* Bestellungen, die nach dem Speichern der Konfiguration aufgegeben werden. Es ändert bestehende Bestellreferenzen nicht rückwirkend, da dies zu Dateninkonsistenzen mit früheren Aufzeichnungen, Rechnungen und Kundenkommunikationen führen könnte.

**F: Meine neuen Bestellreferenzen folgen nicht dem von mir festgelegten Format.**
A:

1. **Haben Sie auf „Speichern“ geklickt?** Stellen Sie sicher, dass Sie auf die Schaltfläche „Speichern“ geklickt haben, nachdem Sie Änderungen auf der Modulkonfigurationsseite vorgenommen haben.
2. **Überprüfen Sie die Formatsyntax:** Überprüfen Sie Ihre Zeichenfolge für das `Order Reference Format` auf Tippfehler oder falsche Zeichen. Beachten Sie den Abschnitt „Verfügbare Platzhalter & Zeichen“ oben.
3. **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort wirksam werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
4. **Modulkonflikte:** Obwohl selten, könnte ein anderes Modul, das den Bestellprozess stark modifiziert, einen Konflikt verursachen. Versuchen Sie, andere kürzlich installierte Module vorübergehend zu deaktivieren, um zu sehen, ob das Problem behoben wird.

**F: Kann ich die Bestellreferenz kürzer oder länger machen?**
A: Ja, absolut! Verwenden Sie die Syntax `{n}` oder `{n,m}`, um die genaue Länge oder einen Bereich anzugeben. Zum Beispiel `[0-9]{4}` für eine 4-stellige Zahl oder `[A-Z0-9]{10}` für eine 10-stellige alphanumerische Referenz.

**F: Was passiert, wenn das Modul eine Referenz generiert, die bereits existiert?**
A: Das Modul ist so konzipiert, dass es die Eindeutigkeit gewährleistet. Wenn es eine Referenz generiert, die bereits verwendet wird, versucht es automatisch, eine andere zu generieren, bis eine eindeutige Referenz gefunden wird. Dieser Vorgang ist in der Regel sofort und stellt sicher, dass keine zwei Bestellungen dieselbe Referenz teilen.

**F: Beeinflusst dieses Modul SEO oder die Leistung meines Shops?**
A: Nein, dieses Modul arbeitet ausschließlich auf der Backend-Logik der Bestellreferenzgenerierung. Es hat keinen direkten Einfluss auf die SEO oder die Front-Office-Leistung Ihres Shops.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Bestellreferenz ändern kostenlos“ erreicht seine Funktionalität durch eine Überschreibung der PrestaShop-Kernklasse `Order`. Anstatt sich direkt in Event-Listener einzuhaken, modifiziert es das Standardverhalten der Methode `Order::generateReference()`, die für die Erstellung der eindeutigen Bestellreferenz verantwortlich ist. Dieser Ansatz stellt sicher, dass die benutzerdefinierte Referenzgenerierungslogik immer dann angewendet wird, wenn eine neue Bestellung erstellt wird, unabhängig vom spezifischen Front-Office-Fluss.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Die gesamte Konfiguration wird über die `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- **`refchange/override/classes/order/Order.php`**
  - **Zweck**: Diese Datei enthält die Überschreibung für die PrestaShop-Kernklasse `Order`. Ihre Hauptfunktion besteht darin, die Standardmethode `generateReference()` durch eine benutzerdefinierte Logik zu ersetzen, die das in der Modulkonfiguration definierte Format anwendet.
  - **Elternklasse**: Erweitert `OrderCore`.
  - **Schlüsselmethoden**:
    - `generateReference()`: Diese überschriebene Methode ist das Herzstück des Moduls.
      - Sie ruft das benutzerdefinierte Referenzformat aus `Configuration::get('REFCHANGE_FORMAT')` ab.
      - Wenn ein benutzerdefiniertes Format definiert ist, verwendet es eine Schleife, um eine Referenzzeichenfolge basierend auf dem konfigurierten Muster zu generieren (unter Verwendung von `preg_match` und `rand` für die Zeichenauswahl).
      - Anschließend überprüft es die Tabelle `ps_orders`, um sicherzustellen, dass die generierte Referenz eindeutig ist. Wenn nicht eindeutig, wird sie neu generiert, bis eine eindeutige gefunden wird.
      - Wenn kein benutzerdefiniertes Format definiert ist, fällt es auf die übergeordnete Methode `OrderCore::generateReference()` zurück.
  - **Datenbankinteraktion**: Interagiert mit der Tabelle `ps_orders`, um nach bestehenden Referenzen zu suchen.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Die Konfigurationsoberfläche wird direkt innerhalb der `getContent()`-Methode der Hauptmoduldatei gerendert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - `ps_configuration`: Speichert die Konfigurationseinstellung des Moduls:
    - `REFCHANGE_FORMAT`: Die benutzerdefinierte Bestellreferenzformatzeichenfolge (z. B. `[0-9]{6}`).
- **Registrierte Hooks-Tabelle**:
  Dieses Modul registriert keine Hooks explizit in der Tabelle `ps_hook_module`. Seine Funktionalität wird durch eine Klassenüberschreibung implementiert, was bedeutet, dass es das Kernverhalten direkt modifiziert, anstatt auf spezifische Hook-Ereignisse zu reagieren.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Bestellreferenz ändern kostenlos“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Team ist bestrebt, sicherzustellen, dass das Modul optimal mit Ihrem PrestaShop-Shop funktioniert.

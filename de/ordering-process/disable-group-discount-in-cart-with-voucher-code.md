---
title: "Gruppenrabatt im Warenkorb mit Gutscheincode deaktivieren - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Gruppenrabatt im Warenkorb mit Gutscheincode deaktivieren' von MyPresta.eu."
sidebar:
  label: "Gruppenrabatt im Warenkorb mit Gutscheincode deaktivieren - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Disable group discount in cart with voucher code auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/disable-group-discount-in-cart-with-voucher-code.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/disable-group-discount-in-cart-with-voucher-code/)
>
> ---


# Gruppenrabatt im Warenkorb mit Gutscheincode deaktivieren

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modulnamen, um auf dessen Einstellungen zuzugreifen.

#### Einstellung: Gruppenrabatt im Warenkorb mit Warenkorb-Regel deaktivieren

Dies ist der Hauptschalter für die Funktionalität des Moduls.

- **Was diese Einstellung bewirkt:** Diese Einstellung bestimmt, ob das Modul aktiv eingreift, um Gruppenrabatte zu deaktivieren, wenn ein Gutscheincode im Warenkorb vorhanden ist.
- **Auswirkung der Änderung dieser Einstellung:**
  - ***Wenn aktiviert:*** Wenn ein Kunde zu einer Gruppe mit einem speziellen Rabatt gehört (z. B. 10 % Rabatt für „Großhandelskunden“) UND er einen Gutscheincode (Warenkorb-Regel) auf seinen Warenkorb anwendet, wird der Gruppenrabatt ignoriert. Nur der Gutscheinrabatt wird auf den Gesamtbetrag der Bestellung angewendet. Dies verhindert, dass der Kunde beide Rabatte gleichzeitig erhält.
  - ***Wenn deaktiviert:*** Das Modul greift nicht ein. Das Standardverhalten von PrestaShop wird angewendet, was bedeutet, dass, wenn ein Kunde sowohl für einen Gruppenrabatt als auch für einen Gutscheinrabatt berechtigt ist, beide angewendet werden können, wodurch die Rabatte möglicherweise gestapelt werden.
- **Empfohlener Wert:** **Aktiviert**. Dies ist die Kernfunktionalität des Moduls und wird im Allgemeinen empfohlen, um unbeabsichtigtes Stapeln von Rabatten zu verhindern und Ihre Gewinnmargen während Gutscheinkampagnen zu schützen.
- **Händlerszenario / Beispiel:**
  - *Szenario 1 (Aktiviert):* Sie haben eine Gruppe „VIP-Kunden“, die 5 % Rabatt auf alle Produkte erhält. Sie führen auch einen Gutscheincode „SUMMER20“ für 20 % Rabatt ein. Ein VIP-Kunde legt Artikel in seinen Warenkorb und wendet „SUMMER20“ an. Mit **aktiviertem** Modul erhält er nur die 20 % Rabatt vom Gutschein, nicht 5 % + 20 %.
  - *Szenario 2 (Deaktiviert):* Im selben Beispiel, wenn das Modul **deaktiviert** ist, könnte der VIP-Kunde sowohl den 5 % Gruppenrabatt als auch den 20 % Gutscheinrabatt erhalten, was zu einem Gesamtrabatt von 25 % führt (oder einer komplexeren Berechnung, abhängig von der internen Rabattanwendungsreihenfolge von PrestaShop).

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Gruppenrabatt im Warenkorb mit Warenkorb-Regel deaktivieren | Aktiviert | Wenn aktiviert, werden Gruppenrabatte ignoriert, wenn ein Gutscheincode im Warenkorb vorhanden ist, wodurch sichergestellt wird, dass nur der Gutscheinrabatt angewendet wird. Verhindert das Stapeln von Rabatten. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul aktiviert, aber Kunden erhalten immer noch beide Rabatte. Was ist falsch?**
A1: Stellen Sie zunächst sicher, dass das Modul in seiner Konfiguration tatsächlich „Aktiviert“ ist. Zweitens, leeren Sie Ihren PrestaShop-Cache (Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie dann oben rechts auf „Cache leeren“). Manchmal können alte Cache-Daten verhindern, dass Änderungen sofort wirksam werden. Testen Sie auch mit einem frischen Warenkorb und einer neuen Kundensitzung (z. B. in einem Inkognito-Browserfenster).

**F2: Wirkt sich dieses Modul auf meine spezifischen Preise oder Katalogpreisregeln aus?**
A2: Nein, dieses Modul zielt speziell auf *Gruppenrabatte* und *Warenkorb-Regeln (Gutscheincodes)* ab. Es greift nicht in spezifische Preise ein, die für einzelne Produkte, Produktkombinationen oder Katalogpreisregeln festgelegt wurden, die auf Menge oder anderen Bedingungen basieren. Es ändert nur die Interaktion zwischen Kundengruppenrabatten und Gutscheincodes.

**F3: Funktioniert dieses Modul mit allen Arten von Gutscheincodes (Prozentsatz, fester Betrag, kostenloser Versand)?**
A3: Ja, die Logik des Moduls ist so konzipiert, dass sie das Vorhandensein *jeder* aktiven Warenkorb-Regel (Gutscheincode) im Warenkorb erkennt. Sobald eine Warenkorb-Regel erkannt wird, deaktiviert sie den Gruppenrabatt, unabhängig von der Art des Rabatts, den der Gutschein bietet (Prozentsatz, fester Betrag, kostenloser Versand usw.).

**F4: Was ist, wenn ich Gruppenrabatte UND einen Gutscheincode für eine bestimmte Aktion zulassen möchte?**
A4: Wenn Sie eine bestimmte Aktion haben, bei der Sie *beide* Rabatte stapeln möchten, müssten Sie dieses Modul in seiner Konfiguration vorübergehend **deaktivieren**. Denken Sie daran, es wieder zu aktivieren, sobald diese spezifische Aktion beendet ist, wenn Sie zum „nur Gutschein“-Rabattverhalten zurückkehren möchten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Dieses Modul funktioniert hauptsächlich durch eine Überschreibung einer PrestaShop-Kernklasse. Anstatt Hooks zu verwenden, modifiziert es direkt das Verhalten der `Product`-Klasse, um anzupassen, wie Preise berechnet werden, wenn ein Kundengruppenrabatt involviert ist und eine Warenkorb-Regel aktiv ist. Dieser Ansatz stellt sicher, dass die Rabattlogik auf einer fundamentalen Ebene während des Produktpreisabrufs angewendet wird.

### 4.2 Controller (`controllers/`)

- Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Seine Funktionalität wird über Klassenüberschreibungen implementiert.

### 4.3 Kernklassen & Modelle (`classes/`)

- **Dateipfad**: `exgcr/override/classes/Product.php`

  - **Klassenname**: `Product` (überschreibt die Kernklasse `Product`)
  - **Elternklasse**: `ProductCore`
  - **Verantwortlichkeit**: Diese Überschreibung modifiziert die Methode `getPriceStatic` der `Product`-Klasse. Die Methode `getPriceStatic` ist entscheidend, da sie für die Berechnung des Endpreises eines Produkts verantwortlich ist, unter Berücksichtigung verschiedener Faktoren wie Steuern, spezifische Preise, Kundengruppen und Warenkorb-Regeln.
  - **Schlüssellogik**:
    - Die Überschreibung prüft, ob das Modul `exgcr` aktiviert ist.
    - Anschließend prüft sie, ob eine aktive `CartRule` (Gutscheincode) auf den aktuellen Warenkorb angewendet wird.
    - Wenn beide Bedingungen erfüllt sind (Modul aktiviert UND Gutschein vorhanden), modifiziert sie die an die übergeordnete `getPriceStatic`-Methode übergebenen Parameter, um den Kundengruppenrabatt effektiv zu ignorieren. Insbesondere setzt sie den Parameter `$use_group_reduction` auf `false` beim Aufruf der übergeordneten Methode, wodurch verhindert wird, dass der Gruppenrabatt angewendet wird.
    - Dies stellt sicher, dass, wenn ein Gutschein verwendet wird, die Preisberechnung so erfolgt, als ob der Kunde keiner rabattierten Gruppe angehört, wodurch das Stapeln von Gruppenrabatten mit Gutscheinrabatten verhindert wird.
- **Dateipfad**: `exgcr/override/classes/index.php`

  - **Zweck**: Dies ist eine standardmäßige leere `index.php`-Datei, die in Verzeichnissen platziert wird, um die Verzeichnisauflistung zu verhindern (Sicherheitsmaßnahme). Sie enthält keinen funktionalen Code.

### 4.4 JavaScript-Assets (`views/js/`)

- Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

- Dieses Modul enthält keine benutzerdefinierten CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Seine Konfiguration wird direkt innerhalb der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es speichert seine Konfigurationseinstellung (`exgcr`) in der Standardtabelle `ps_configuration`.
    - `PS_CONFIGURATION`-Eintrag: `EXGCR_ENABLED` (speichert `1` für aktiviert, `0` für deaktiviert).
- **Registrierte Hooks-Tabelle**:

  - Dieses Modul registriert keine spezifischen Hooks in der Tabelle `ps_hook_module`. Seine Funktionalität wird durch eine Klassenüberschreibung implementiert, was eine direktere Möglichkeit ist, das Kernverhalten zu ändern, ohne auf die Ausführung von Hooks angewiesen zu sein.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Gruppenrabatt im Warenkorb mit Gutscheincode deaktivieren“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls in Ihren PrestaShop-Shop zur Verfügung.

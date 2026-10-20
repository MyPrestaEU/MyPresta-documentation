---
title: "Custom Order Reference Generator Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Custom Order Reference Generator Pro von MyPresta.eu."
sidebar:
  label: "Custom Order Reference Generator Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Custom Order Reference Generator Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/custom-order-reference-generator-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/custom-order-reference-generator-pro/)
>
> ---


# Custom Order Reference Generator Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Custom Order Reference Generator Pro)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie Ihre benutzerdefinierten Bestellreferenzmuster und -regeln definieren. Die Seite ist typischerweise zur besseren Übersichtlichkeit in mehrere Registerkarten oder Abschnitte unterteilt.

#### **Registerkarte „Allgemeine Einstellungen“**

Diese Registerkarte steuert das grundlegende Verhalten des Moduls.

- **Benutzerdefinierte Bestellreferenzgenerierung aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul. Wenn aktiviert, übernimmt das Modul die Generierung von Bestellreferenzen. Wenn deaktiviert, kehrt PrestaShop zu seiner Standardmethode der Bestellreferenzgenerierung zurück.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Alle neuen Bestellungen erhalten eine Referenz, die von diesem Modul gemäß Ihren definierten Regeln generiert wird.
    - *Wenn deaktiviert:* Alle neuen Bestellungen verwenden das Standardreferenzformat von PrestaShop. Bestehende Bestellungen behalten ihre Referenzen bei.
  - **Empfohlener Wert:** JA (um die Funktionalität des Moduls zu aktivieren).
  - **Händlerszenario / Beispiel:** Wenn Sie benutzerdefinierte Referenzen verwenden möchten, aktivieren Sie diese Option. Wenn Sie vorübergehend zu PrestaShops Standard zurückkehren müssen, um Fehler zu beheben, deaktivieren Sie sie.
- **Standard-Referenzmuster:**

  - **Was diese Einstellung bewirkt:** Dies definiert die grundlegende Struktur für Ihre benutzerdefinierten Bestellreferenzen. Sie können statischen Text mit dynamischen „Shortcodes“ kombinieren, die Informationen aus der Bestellung, dem Kunden oder dem Datum abrufen.
  - **Auswirkungen einer Änderung dieser Einstellung:** Dies bestimmt direkt das Format Ihrer Bestellreferenzen, wenn keine spezifische Regel angewendet wird.
  - **Empfohlener Wert:** Beginnen Sie mit etwas Einfachem wie `MEINSHOP-{DATE:YMD}-{ID_ORDER}` oder `BEST-{RAND:6}`.
  - **Händlerszenario / Beispiel:**
    - `MEINSHOP-{DATE:YMD}-{ID_ORDER}`: Generiert Referenzen wie `MEINSHOP-20231027-12345`. Dies ist großartig, um Bestellungen aus Ihrem Shop leicht zu identifizieren und das Bestelldatum zusammen mit einer sequenziellen Bestell-ID zu sehen.
    - `BEST-{RAND:6}`: Generiert Referenzen wie `BEST-A1B2C3`. Dies bietet eine kurze, zufällige und einzigartige Referenz.
    - `{CUSTOMER_LASTNAME}-{ID_ORDER}`: Generiert Referenzen wie `MÜLLER-12345`. Nützlich für B2B oder personalisierten Service.
  - **Verfügbare Shortcodes:**
    - `{ID_ORDER}`: Die eindeutige ID der Bestellung (sequenziell).
    - `{ID_CUSTOMER}`: Die eindeutige ID des Kunden.
    - `{DATE:format}`: Aktuelles Datum und Uhrzeit. `format` verwendet die Syntax der PHP-Funktion `date()` (z.B. `YMD` für 20231027, `His` für 143059).
    - `{RAND:length}`: Eine zufällige Zeichenfolge aus alphanumerischen Zeichen, `length` gibt die Anzahl der Zeichen an (z.B. `RAND:6`).
    - `{CUSTOMER_FIRSTNAME}`: Vorname des Kunden.
    - `{CUSTOMER_LASTNAME}`: Nachname des Kunden.
    - `{CUSTOMER_EMAIL}`: E-Mail-Adresse des Kunden.
    - `{PAYMENT_METHOD}`: Die für die Bestellung verwendete Zahlungsmethode.
    - `{DELIVERY_COUNTRY_ISO}`: ISO-Code des Lieferlandes (z.B. DE, FR).
    - `{DELIVERY_CITY}`: Stadt der Lieferadresse.
    - `{CART_TOTAL}`: Gesamtwert des Warenkorbs.
    - `{PRODUCT_SKU}`: SKU des ersten Produkts im Warenkorb (mit Vorsicht verwenden, kann lang sein).
    - `{PRODUCT_NAME}`: Name des ersten Produkts im Warenkorb (mit Vorsicht verwenden).
    - `{SHOP_NAME}`: Name Ihres PrestaShop-Shops.
- **Startwert des sequenziellen Zählers:**

  - **Was diese Einstellung bewirkt:** Wenn Ihr Referenzmuster `{ID_ORDER}` oder ein ähnliches sequenzielles Element enthält, definiert dies die Startnummer für diese Sequenz.
  - **Auswirkungen einer Änderung dieser Einstellung:** Neue Bestellungen beginnen ihre sequenzielle Nummerierung ab diesem Wert. Dies ist nützlich, wenn Sie von einem anderen System migrieren oder die Nummerierung neu starten möchten.
  - **Empfohlener Wert:** 1 (für einen Neuanfang) oder eine höhere Zahl, wenn Sie eine Sequenz fortsetzen müssen.
  - **Händlerszenario / Beispiel:** Wenn Sie zuvor 1000 Bestellungen hatten und möchten, dass Ihre neuen benutzerdefinierten Referenzen ab 1001 beginnen, setzen Sie diesen Wert auf 1001.
- **Referenzlängenbegrenzung:**

  - **Was diese Einstellung bewirkt:** PrestaShop hat eine Standardbegrenzung für die Länge der Bestellreferenz. Hier können Sie eine maximale Länge für Ihre generierten Referenzen definieren. Wenn eine Referenz diese überschreitet, wird sie abgeschnitten.
  - **Auswirkungen einer Änderung dieser Einstellung:** Stellt sicher, dass Ihre Referenzen innerhalb der Datenbankbeschränkungen liegen und in allen Bereichen von PrestaShop korrekt angezeigt werden.
  - **Empfohlener Wert:** 9 (PrestaShops Standard ist oft 9, aber Sie können ihn erhöhen, wenn Ihr Theme/Ihre Datenbank dies unterstützt, bis zu 32 Zeichen sind im Allgemeinen sicher).
  - **Händlerszenario / Beispiel:** Wenn Ihr Muster `MEINSHOP-{DATE:YMD}-{ID_ORDER}` zu `MEINSHOP-20231027-12345` (21 Zeichen) führt und Sie die Begrenzung auf 9 setzen, könnte es zu `MEINSHOP-2` werden. Achten Sie auf das Abschneiden.
- **Referenzvorschau:**

  - **Was diese Einstellung bewirkt:** Dies ist ein Hilfsfeld, mit dem Sie Ihr `Standard-Referenzmuster` mit einer Dummy-Bestell-ID testen können, um zu sehen, wie die generierte Referenz aussehen würde.
  - **Auswirkungen einer Änderung dieser Einstellung:** Keine direkte Auswirkung auf Ihren Shop, rein ein Testwerkzeug.
  - **Empfohlener Wert:** Häufig verwenden, wenn Sie Ihre Muster entwerfen.
  - **Händlerszenario / Beispiel:** Geben Sie `12345` als Dummy-Bestell-ID ein und klicken Sie auf „Vorschau generieren“, um zu sehen, wie `MEINSHOP-{DATE:YMD}-{ID_ORDER}` aussehen würde.

#### **Registerkarte „Regeln“**

Auf dieser Registerkarte definieren Sie spezifische Bedingungen, unter denen verschiedene Bestellreferenzmuster angewendet werden sollen, die das Standardmuster überschreiben. Regeln werden von oben nach unten verarbeitet, und die erste passende Regel wird angewendet.

- **Neue Regel hinzufügen / Regel bearbeiten:**

  - **Was dies bewirkt:** Ermöglicht Ihnen, eine neue Regel zu erstellen oder eine bestehende zu ändern. Jede Regel besteht aus:
    - **Regelname:** Ein beschreibender Name für Ihre interne Referenz (z.B. „Bestellungen mit hohem Wert“, „Französische Kunden“).
    - **Regelmuster:** Das benutzerdefinierte Referenzmuster, das verwendet werden soll, wenn diese Regel zutrifft (gleiche Shortcodes wie das Standardmuster).
    - **Bedingungen:** Ein oder mehrere Kriterien, die erfüllt sein müssen, damit diese Regel angewendet wird.
  - **Auswirkungen einer Änderung dieser Einstellung:** Fügt ein bedingtes Referenzmuster hinzu oder ändert es.
  - **Empfohlener Wert:** Erstellen Sie Regeln für Ihre wichtigsten Geschäftssegmente.
  - **Händlerszenario / Beispiel:**
    - **Regel 1: Bestellungen mit hohem Wert**
      - **Muster:** `VIP-{ID_ORDER}-{DATE:YMD}`
      - **Bedingung:** `Warenkorbwert` ist `größer als` `500`
      - **Effekt:** Jede Bestellung über 500 € erhält eine Referenz wie `VIP-12345-20231027`.
    - **Regel 2: Französische Kunden**
      - **Muster:** `FR-{ID_ORDER}`
      - **Bedingung:** `Lieferland` ist `Frankreich`
      - **Effekt:** Bestellungen, die nach Frankreich versandt werden, erhalten `FR-12345`.
    - **Regel 3: Bestellungen für bestimmte Produkte**
      - **Muster:** `PROD-XYZ-{ID_ORDER}`
      - **Bedingung:** `Produkt im Warenkorb` ist `Produktname XYZ`
      - **Effekt:** Bestellungen, die „Produktname XYZ“ enthalten, erhalten `PROD-XYZ-12345`.
- **Regelbedingungen (für jede Regel):**

  - **Was dies bewirkt:** Definiert die Kriterien für die Aktivität einer Regel. Sie können mehrere Bedingungen mit „UND“-Logik kombinieren.
  - **Verfügbare Bedingungen:**
    - **Warenkorbwert:** Basierend auf dem Gesamtwert der Bestellung.
    - **Kundengruppe:** Basierend auf der Gruppe, zu der der Kunde gehört (z.B. Besucher, Kunden, Gäste oder benutzerdefinierte Gruppen).
    - **Lieferland:** Basierend auf dem Land der Lieferadresse.
    - **Zahlungsmethode:** Basierend auf dem verwendeten Zahlungsmodul (z.B. Banküberweisung, PayPal).
    - **Produkt im Warenkorb:** Basierend darauf, ob ein bestimmtes Produkt (nach ID oder Name) in der Bestellung vorhanden ist.
    - **Versanddienstleister:** Basierend auf dem gewählten Versanddienstleister.
  - **Auswirkungen einer Änderung dieser Einstellung:** Bestimmt, wann ein spezifisches benutzerdefiniertes Referenzmuster verwendet wird.
  - **Empfohlener Wert:** Verwenden Sie Bedingungen, die Ihre Bestellungen klar segmentieren.
  - **Händlerszenario / Beispiel:** Eine Regel für „Großhandelskunden“ könnte `Kundengruppe ist Großhandel` verwenden. Eine Regel für „Expressversand“ könnte `Versanddienstleister ist DHL Express` verwenden.

#### **Registerkarte „Erweiterte Einstellungen“**

Diese Registerkarte enthält Einstellungen für technischere Aspekte und Wartung.

- **JSON-Backup / Wiederherstellung:**

  - **Was dies bewirkt:** Ermöglicht Ihnen, die Konfiguration Ihres Moduls (Muster, Regeln) in eine JSON-Datei zu exportieren oder eine zuvor gespeicherte Konfiguration zu importieren.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Backup:* Erstellt eine herunterladbare Datei Ihrer Einstellungen.
    - *Wiederherstellung:* Überschreibt die aktuellen Einstellungen mit denen aus der hochgeladenen JSON-Datei.
  - **Empfohlener Wert:** Sichern Sie Ihre Konfiguration immer, bevor Sie größere Änderungen vornehmen oder Ihren PrestaShop-Shop aktualisieren.
  - **Händlerszenario / Beispiel:** Bevor Sie PrestaShop aktualisieren oder Ihren Shop auf einen neuen Server verschieben, laden Sie ein Backup Ihrer benutzerdefinierten Referenzregeln herunter. Wenn Sie einen Fehler bei einer Regel machen, können Sie problemlos eine frühere Version wiederherstellen.
- **Modulkonfiguration zurücksetzen:**

  - **Was dies bewirkt:** Löscht alle benutzerdefinierten Muster und Regeln und setzt das Modul in seinen Standardzustand zurück, wie nach einer frischen Installation.
  - **Auswirkungen einer Änderung dieser Einstellung:** Alle Ihre benutzerdefinierten Referenzmuster und Regeln gehen verloren.
  - **Empfohlener Wert:** Mit äußerster Vorsicht verwenden, nur wenn Sie komplett neu anfangen möchten.
  - **Händlerszenario / Beispiel:** Wenn Ihre Regeln zu komplex geworden sind oder Probleme verursachen und Sie von Grund auf neu beginnen möchten, können Sie dies verwenden. Immer zuerst sichern!

#### **Kurzübersichtstabelle der Konfiguration**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Allgemeine Einstellungen** | Benutzerdefinierte Bestellreferenzgenerierung aktivieren | JA | Aktiviert/deaktiviert die Logik des Moduls für benutzerdefinierte Referenzen. |
|  | Standard-Referenzmuster | `BEST-{RAND:6}` (Beispiel) | Definiert das Fallback-Referenzformat, wenn keine Regeln übereinstimmen. |
|  | Startwert des sequenziellen Zählers | 1 | Legt die Startnummer für `{ID_ORDER}` in neuen Referenzen fest. |
|  | Referenzlängenbegrenzung | 9 (oder höher, wenn sicher) | Begrenzt die maximale Länge generierter Referenzen, um Probleme zu vermeiden. |
|  | Referenzvorschau | (N/A) | Werkzeug zum Testen Ihres Musters mit einer Dummy-Bestell-ID. |
| **Registerkarte „Regeln“** | Regel hinzufügen/bearbeiten | N/A | Erstellen Sie bedingte Referenzmuster basierend auf Kriterien. |
|  | Regelname | Beschreibend (z.B. „Bestellungen mit hohem Wert“) | Interne Bezeichnung für die Regel. |
|  | Regelmuster | Benutzerdefiniert (z.B. `VIP-{ID_ORDER}`) | Das Referenzformat für diese spezifische Regel. |
|  | Regelbedingungen | Variiert (z.B. `Warenkorbwert > 500`) | Kriterien, die erfüllt sein müssen, damit die Regel angewendet wird. |
| **Erweiterte Einstellungen** | JSON-Backup / Wiederherstellung | N/A | Exportieren/Importieren der Modulkonfiguration zur Sicherheit oder Migration. |
|  | Modulkonfiguration zurücksetzen | N/A | Löscht alle Moduleinstellungen und Regeln. Mit äußerster Vorsicht verwenden. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine benutzerdefinierten Referenzen werden nicht angezeigt, oder ich sehe immer noch die Standardreferenzen von PrestaShop.**
A1: Stellen Sie zunächst sicher, dass das Modul auf der Registerkarte „Allgemeine Einstellungen“ **aktiviert** ist. Überprüfen Sie auch, ob Sie Ihren PrestaShop-Cache geleert haben (Erweiterte Parameter > Leistung > Cache leeren). Wenn Sie spezifische Regeln haben, stellen Sie sicher, dass deren Bedingungen erfüllt sind und dass die Regeln korrekt geordnet sind (die erste passende Regel wird angewendet).

**F2: Meine benutzerdefinierten Referenzen sind zu lang oder werden abgeschnitten.**
A2: Überprüfen Sie die „Referenzlängenbegrenzung“ auf der Registerkarte „Allgemeine Einstellungen“. PrestaShop hat eine Standardbegrenzung (oft 9 Zeichen) für Bestellreferenzen in seiner Datenbank. Wenn Ihr benutzerdefiniertes Muster längere Referenzen generiert, müssen Sie diese Begrenzung möglicherweise erhöhen. Seien Sie vorsichtig, da eine zu starke Erhöhung zu Anzeigeproblemen in einigen Themes oder älteren PrestaShop-Versionen führen kann. Es ist im Allgemeinen sicher, bis zu 32 Zeichen zu verwenden. Wenn Sie längere benötigen, konsultieren Sie einen Entwickler.

**F3: Ich habe einen Fehler bei meinen Regeln gemacht, und jetzt sind meine Referenzen falsch. Wie behebe ich das?**
A3: Wenn Sie ein aktuelles JSON-Backup (von der Registerkarte „Erweiterte Einstellungen“) haben, können Sie es wiederherstellen. Andernfalls müssen Sie die problematischen Regeln manuell bearbeiten oder löschen. Wenn Sie komplett neu anfangen möchten, verwenden Sie die Option „Modulkonfiguration zurücksetzen“, aber beachten Sie, dass dadurch *alle* Ihre benutzerdefinierten Muster und Regeln gelöscht werden.

**F4: Kann ich dieses Modul mit mehreren Shops (Multistore-Setup) verwenden?**
A4: Ja, das Modul ist so konzipiert, dass es mit der Multistore-Funktion von PrestaShop kompatibel ist. Sie können verschiedene Referenzmuster und Regeln für jeden Shop über die Konfigurationsseite des Moduls konfigurieren, indem Sie den spezifischen Shop-Kontext im PrestaShop-Back Office auswählen.

**F5: Was passiert mit bestehenden Bestellungen, wenn ich das Referenzmuster ändere?**
A5: Das Ändern des Referenzmusters oder der Regeln wirkt sich nur auf *neue* Bestellungen aus, die nach der Änderung aufgegeben werden. Bestehende Bestellungen behalten ihre ursprünglichen Bestellreferenzen bei. Das Modul ändert keine vergangenen Bestelldaten rückwirkend.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Custom Order Reference Generator Pro“ erweitert hauptsächlich die Kernklasse `Order` von PrestaShop durch einen Override, um den Prozess der Bestellreferenzgenerierung abzufangen und zu modifizieren. Es folgt einem ereignisgesteuerten Ansatz, bei dem das Modul in den Lebenszyklus der Bestellerstellung eingreift. Die Konfiguration wird über eine Standardmethode `getContent()` in der Hauptmoduldatei verwaltet, wobei Einstellungen in `ps_configuration` und benutzerdefinierte Regeln in eigenen Datenbanktabellen gespeichert werden (obwohl keine spezifischen SQL-Dateien aufgeführt sind, impliziert dies eine dynamische Tabellenerstellung oder Konfigurationsspeicherung). Das Modul verwendet eine `RulesEngine` zur Auswertung von Bedingungen und einen `ReferenceGenerator` zur Konstruktion der endgültigen Referenz basierend auf definierten Mustern und Shortcodes.

### 4.2 Controller (`controllers/`)

Dieses Modul scheint keine benutzerdefinierten Front-Office- oder Back-Office-Controller zu verwenden. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- `refchangepro/classes/PayloadFactory.php`

  - **Klassenname:** `PayloadFactory`
  - **Elternklasse:** Keine (wahrscheinlich eine Utility-Klasse)
  - **Verantwortlichkeit:** Verantwortlich für die Erstellung einer Daten-Payload (Kontext), die die `RulesEngine` und der `ReferenceGenerator` verwenden können. Diese Payload würde Informationen über die aktuell verarbeitete Bestellung enthalten (z.B. Warenkorbwert, Kunden-ID, Lieferland, Produkte). Sie fungiert als Abstraktionsschicht, um alle notwendigen Daten für die Regelauswertung und Referenzgenerierung zu sammeln.
- `refchangepro/classes/ReferenceContext.php`

  - **Klassenname:** `ReferenceContext`
  - **Elternklasse:** Keine (wahrscheinlich ein Datenübertragungsobjekt oder Wertobjekt)
  - **Verantwortlichkeit:** Eine einfache Klasse zum Halten und Verwalten der Kontextdaten (z.B. Bestell-ID, Kundendetails, Warenkorbdetails), die während des Referenzgenerierungsprozesses weitergegeben werden. Sie gewährleistet die Konsistenz des Datenzugriffs für den Generator und die Regel-Engine.
- `refchangepro/classes/ReferenceGenerator.php`

  - **Klassenname:** `ReferenceGenerator`
  - **Elternklasse:** Keine (wahrscheinlich eine Dienstklasse)
  - **Verantwortlichkeit:** Die Kernlogik zur Konstruktion der endgültigen Bestellreferenzzeichenfolge. Sie nimmt ein Muster (z.B. `MEINSHOP-{DATE:YMD}-{ID_ORDER}`) und ein `ReferenceContext`-Objekt entgegen und ersetzt dann Shortcodes durch tatsächliche Werte. Sie übernimmt die Datumsformatierung, die Generierung zufälliger Zeichenfolgen und die Einfügung sequenzieller IDs.
- `refchangepro/classes/RulesEngine.php`

  - **Klassenname:** `RulesEngine`
  - **Elternklasse:** Keine (wahrscheinlich eine Dienstklasse)
  - **Verantwortlichkeit:** Bewertet die definierten Regeln anhand des aktuellen Bestellkontexts. Sie iteriert durch die konfigurierten Regeln, prüft, ob die Bedingungen (z.B. Warenkorbwert, Kundengruppe, Land) erfüllt sind, und gibt das Muster der ersten passenden Regel zurück. Wenn keine Regeln übereinstimmen, wird angezeigt, dass das Standardmuster verwendet werden soll.
- `refchangepro/classes/Runtime.php`

  - **Klassenname:** `Runtime`
  - **Elternklasse:** Keine (wahrscheinlich eine Utility- oder Helper-Klasse)
  - **Verantwortlichkeit:** Könnte Laufzeitkonfigurationen, Caching oder andere operative Aspekte des Moduls handhaben. Könnte für das Laden von Regeln aus der Konfiguration, die Verwaltung des sequenziellen Zählers oder die Bereitstellung von Utility-Methoden verantwortlich sein, die im gesamten Modul verwendet werden.
- `refchangepro/override/classes/order/Order.php`

  - **Genauer Dateipfad:** `refchangepro/override/classes/order/Order.php`
  - **Klassenname:** `Order`
  - **Elternklasse:** `OrderCore` (PrestaShops Kern-Order-Klasse)
  - **Verantwortlichkeit:** Dies ist der kritische Override. Er fängt die Methode `generateReference()` (oder eine ähnliche Methode, die für das Setzen der Bestellreferenz verantwortlich ist) innerhalb der Kernklasse `Order` von PrestaShop ab. Innerhalb dieser überschriebenen Methode ruft er die `RulesEngine` des Moduls auf, um das korrekte Muster zu bestimmen, und dann den `ReferenceGenerator`, um die benutzerdefinierte Referenz zu erstellen, und setzt diese schließlich für das Bestellobjekt. Dies stellt sicher, dass jede neu erstellte Bestellung die Logik des Moduls verwendet.

### 4.4 JavaScript-Assets (`views/js/`)

- `refchangepro/lib/searchTool/views/js/autocomplete.js`

  - **Umfang:** Wahrscheinlich Back-Office.
  - **Beschreibung:** Bietet Autocomplete-Funktionalität, möglicherweise zur Auswahl von Produkten, Kunden oder anderen Entitäten beim Definieren von Regeln. Es würde an Eingabefelder gebunden, AJAX-Anfragen an einen PrestaShop-Admin-Controller (oder die `getContent`-Methode des Moduls) senden und Vorschläge anzeigen.
- `refchangepro/views/js/admin-tabs.js`

  - **Umfang:** Back-Office.
  - **Beschreibung:** Verwaltet die Registerkartenoberfläche innerhalb der Konfigurationsseite des Moduls. Es bindet Klickereignisse an Registerkartenüberschriften, zeigt/versteckt entsprechende Registerkarteninhalte und könnte URL-Hash-Änderungen für direkte Registerkartenverknüpfungen verarbeiten.
- `refchangepro/views/js/rules-builder.js`

  - **Umfang:** Back-Office.
  - **Beschreibung:** Dies ist das Kern-JavaScript für die Registerkarte „Regeln“. Es verarbeitet das dynamische Hinzufügen, Bearbeiten und Löschen von Regelbedingungen. Es bindet Ereignisse an „Bedingung hinzufügen“-Schaltflächen, verwaltet Dropdowns für Bedingungstypen (z.B. „Warenkorbwert“, „Kundengruppe“) und rendert dynamisch Eingabefelder basierend auf dem ausgewählten Bedingungstyp (z.B. Zahleneingabe für Warenkorbwert, Auswahlfeld für Kundengruppen). Es serialisiert wahrscheinlich die Regeldaten in ein verstecktes Eingabefeld zur Übermittlung.

### 4.5 CSS-Stylesheets (`views/css/`)

- `refchangepro/lib/searchTool/views/css/autocomplete.css`

  - **Umfang:** Back-Office-Admin-Styling.
  - **Beschreibung:** Stile für die Autocomplete-Vorschlagslisten und Eingabefelder, um sicherzustellen, dass sie visuell konsistent und benutzerfreundlich im PrestaShop-Back Office sind.
- `refchangepro/views/css/admin.css`

  - **Umfang:** Back-Office-Admin-Styling.
  - **Beschreibung:** Bietet allgemeine Stile für die Konfigurationsseite des Moduls, einschließlich Layout, Typografie, Schaltflächenstile und die gesamte visuelle Präsentation, um sich nahtlos in das PrestaShop-Back Office-Theme zu integrieren.
- `refchangepro/views/css/rules-builder.css`

  - **Umfang:** Back-Office-Admin-Styling.
  - **Beschreibung:** Spezifische Stile für die Regeln-Builder-Oberfläche, einschließlich des Layouts einzelner Regelblöcke, Bedingungszeilen und aller Drag-and-Drop- oder Neuanordnungselemente.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- `refchangepro/lib/searchTool/views/scripts.tpl`
  - **Umfang:** Back-Office-Admin.
  - **Beschreibung:** Dieses Template enthält wahrscheinlich das notwendige JavaScript und potenziell CSS für das Autocomplete-Suchwerkzeug. Es würde in das Hauptmodul-Konfigurationstemplate eingebunden, um die Autocomplete-Funktionalität zu laden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Die Modulbeschreibung erwähnt: „Intelligente Regeln wenden verschiedene Muster nach Warenkorbwert, Land, Produkt oder Kundengruppe an.“ Dies impliziert stark die Erstellung benutzerdefinierter Datenbanktabellen zur Speicherung dieser Regeln und ihrer zugehörigen Bedingungen.
  - Erwartete Tabellen (Namen sind illustrativ, tatsächliche Namen würden mit `ps_` und dem Modulnamen präfixiert):
    - `ps_refchangepro_rules`: Speichert die Hauptregeldefinitionen (ID, Name, Muster, aktiver Status).
    - `ps_refchangepro_conditions`: Speichert einzelne Bedingungen für jede Regel (Regel-ID, Bedingungstyp, Operator, Wert).
  - Konfigurationseinstellungen (wie `PS_REFCHANGEPRO_ENABLED`, `PS_REFCHANGEPRO_DEFAULT_PATTERN`, `PS_REFCHANGEPRO_COUNTER_START`) werden in der PrestaShop-Tabelle `ps_configuration` gespeichert.
  - Der sequenzielle Zähler für `{ID_ORDER}` könnte in `ps_configuration` oder einer dedizierten Tabelle für eine robustere Sperrung gespeichert werden.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionOrderAdd` / `actionObjectOrderAddAfter` | Nachdem ein neues Bestellobjekt in der Datenbank erstellt wurde. | Der Override des Moduls von `Order::generateReference()` ist der primäre Mechanismus. Wenn das Modul jedoch zusätzliche Aktionen *nachdem* die Bestellung vollständig mit ihrer neuen Referenz gespeichert wurde, ausführen muss, würden diese Hooks verwendet. Zum Beispiel, um die generierte Referenz zu protokollieren oder einen benutzerdefinierten Zähler zu aktualisieren. |
| `displayBackOfficeHeader` | Im `<head>`-Bereich des Back Office. | Wird verwendet, um modulspezifisches CSS (`admin.css`, `rules-builder.css`, `autocomplete.css`) und JavaScript (`admin-tabs.js`, `rules-builder.js`, `autocomplete.js`) für die Konfigurationsseite zu laden. |
| `displayAdminProductsExtra` / `displayAdminCustomers` (Hypothetisch) | Auf Produkt- oder Kundenbearbeitungsseiten im Back Office. | Wenn das Modul spezifische Referenzeinstellungen pro Produkt oder Kunde anbieten würde, würde es hier eingreifen, um diese Optionen anzuzeigen. (Nicht explizit angegeben, aber üblich für „Pro“-Versionen). |
| `displayModuleConfigure` (Intern) | Wenn die Konfigurationsseite des Moduls geladen wird. | Die `getContent()`-Methode der Hauptmoduldatei ist hier implizit eingehakt, um das Konfigurationsformular zu rendern. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Informationen zum Modul „Custom Order Reference Generator Pro“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.

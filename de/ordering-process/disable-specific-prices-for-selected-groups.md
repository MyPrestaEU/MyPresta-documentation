---
title: "Spezifische Preise für ausgewählte Gruppen deaktivieren – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Spezifische Preise für ausgewählte Gruppen deaktivieren“ von MyPresta.eu."
sidebar:
  label: "Spezifische Preise für ausgewählte Gruppen deaktivieren – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Disable specific prices for selected groups auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/disable-specific-prices-for-selected-groups.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/disable-specific-prices-for-selected-groups/)
>
> ---


# Spezifische Preise für ausgewählte Gruppen deaktivieren

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Spezifische Preise für ausgewählte Gruppen deaktivieren“. Sie finden ihn, indem Sie zu **Module > Modul-Manager** navigieren, nach „Spezifische Preise für ausgewählte Gruppen deaktivieren“ suchen und auf „Konfigurieren“ klicken.

#### **1. Spezifische Preisrabatte für ausgewählte Gruppen deaktivieren**

Dies ist die Kerneinstellung des Moduls. Sie bestimmt, welche Kundengruppen *keine* spezifischen Preisrabatte erhalten.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt zeigt eine Liste aller in Ihrem PrestaShop-Shop definierten Kundengruppen an. Sie können eine oder mehrere Gruppen aus dieser Liste auswählen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn eine oder mehrere Gruppen ausgewählt sind:* Kunden, die zu einer der ausgewählten Gruppen gehören, sehen oder profitieren *nicht* von spezifischen Preisrabatten, die für Produkte konfiguriert sind. Sie sehen und zahlen immer den Standardproduktpreis.
  - *Wenn keine Gruppen ausgewählt sind:* Das Modul deaktiviert keine spezifischen Preise für irgendeine Gruppe. Alle Kunden erhalten spezifische Preisrabatte, wie in Ihren Produkteinstellungen konfiguriert.
- **Empfohlener Wert:** Wählen Sie die spezifischen Kundengruppen aus, für die Sie spezifische Preisrabatte deaktivieren möchten. Wenn Sie beispielsweise eine Gruppe „Großhandel“ haben, die immer den Standardpreis zahlen soll, wählen Sie diese Gruppe aus.
- **Händlerszenario / Beispiel:** Sie haben eine Kundengruppe „Gast“ und eine Gruppe „Neue Kunden“. Sie möchten spezifische Preisrabatte (wie Mengenpreise oder temporäre Aktionen) nur Ihrer Gruppe „Treue Kunden“ vorbehalten. Indem Sie hier „Gast“ und „Neue Kunden“ auswählen, sehen diese beiden Gruppen immer den regulären Preis, während „Treue Kunden“ weiterhin von allen spezifischen Preisen profitieren, die Sie eingerichtet haben.

#### **2. Aktiviert**

Dies ist der globale Ein-/Ausschalter für die Funktionalität des Moduls.

- **Was diese Einstellung bewirkt:** Dies ist ein einfacher Schalter zum Aktivieren oder Deaktivieren der Kernlogik des Moduls.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Modul deaktiviert aktiv spezifische Preise für die Gruppen, die Sie im Abschnitt „Spezifische Preisrabatte für ausgewählte Gruppen deaktivieren“ ausgewählt haben.
  - *Wenn deaktiviert (NEIN):* Das Modul ist inaktiv. Alle spezifischen Preise funktionieren wie im Standard-PrestaShop-Verhalten, unabhängig von den im obigen Abschnitt ausgewählten Gruppen. Dies schaltet die Auswirkungen des Moduls effektiv aus, ohne es zu deinstallieren.
- **Empfohlener Wert:** **JA**, wenn Sie die Funktionalität des Moduls nutzen möchten. **NEIN**, wenn Sie es vorübergehend deaktivieren möchten, ohne Ihre Gruppenauswahlen zu verlieren.
- **Händlerszenario / Beispiel:** Sie haben das Modul so konfiguriert, dass spezifische Preise für Ihre Kundengruppe „Einzelhandel“ deaktiviert werden. Wenn Sie eine temporäre Aktion durchführen möchten, bei der *alle* Gruppen, einschließlich „Einzelhandel“, spezifische Preisrabatte erhalten sollen, können Sie einfach „Aktiviert“ auf **NEIN** setzen. Sobald die Aktion beendet ist, schalten Sie es wieder auf **JA**, um die Deaktivierung spezifischer Preise für „Einzelhandel“-Kunden wieder zu aktivieren.

#### **3. Immer den niedrigsten Preis zurückgeben**

Diese Einstellung bietet eine zusätzliche Kontrollebene, insbesondere wenn spezifische Preise mit anderen Preisregeln interagieren könnten.

- **Was diese Einstellung bewirkt:** Dieser Schalter bestimmt, ob das Modul den Standardpreis für ausgewählte Gruppen strikt durchsetzen soll, oder ob es weiterhin den *niedrigsten möglichen Preis* (der andere Arten von Rabatten enthalten könnte, die nicht durch spezifische Preise verwaltet werden) berücksichtigen soll, falls dieser niedriger als der Standardpreis ist.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Für die ausgewählten Gruppen werden spezifische Preise ignoriert. Wenn es jedoch einen *anderen* Mechanismus gibt (z. B. eine Warenkorbregel, einen globalen Rabatt oder eine andere Art von Preisreduzierung), der zu einem niedrigeren Preis als dem Standardpreis führt, erlaubt das Modul, dass dieser niedrigste Preis angewendet wird. Dies stellt sicher, dass Kunden immer den absolut niedrigsten verfügbaren Preis *außerhalb* der spezifischen Preise erhalten.
  - *Wenn deaktiviert (NEIN):* Für die ausgewählten Gruppen werden spezifische Preise ignoriert, und das Modul setzt strikt den *Standardproduktpreis* durch. Keine anderen potenziellen niedrigeren Preise (es sei denn, sie sind Teil des Grundpreises selbst) werden berücksichtigt. Dies bietet die strengste Kontrolle über die Preisgestaltung für die ausgewählten Gruppen.
- **Empfohlener Wert:** **NEIN** für strikte Kontrolle, um sicherzustellen, dass ausgewählte Gruppen immer den Standardpreis zahlen. **JA**, wenn Sie spezifische Preise deaktivieren möchten, aber dennoch zulassen möchten, dass andere, nicht-spezifische-preisbezogene Rabatte angewendet werden, wenn sie zu einem niedrigeren Preis führen.
- **Händlerszenario / Beispiel:**
  - *Szenario 1 (Empfohlen: NEIN):* Sie möchten, dass Ihre Gruppe „Großhandel“ *immer* den vollen Standardpreis zahlt und niemals von spezifischen Preisrabatten oder anderen potenziellen Preisreduzierungen profitiert. Sie würden dies auf **NEIN** setzen.
  - *Szenario 2 (Empfohlen: JA):* Sie möchten spezifische Preise für Ihre Gruppe „Gast“ deaktivieren, haben aber auch eine allgemeine Warenkorbregel „5 % Rabatt auf alle Produkte“, die für alle gilt. Wenn Sie „Immer den niedrigsten Preis zurückgeben“ auf **JA** setzen, erhalten Gäste keine spezifischen Preisrabatte, aber sie *erhalten* weiterhin den 5 % Warenkorbregel-Rabatt, wenn dieser den Preis niedriger als den Standardpreis macht. Wenn auf **NEIN** gesetzt, würden sie den vollen Standardpreis zahlen und sogar die 5 % Warenkorbregel ignorieren.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Spezifische Preisrabatte für ausgewählte Gruppen deaktivieren | Gruppen nach Bedarf auswählen | Wählen Sie Kundengruppen aus, für die spezifische Preisrabatte ignoriert werden. |
| Modulkonfiguration | Aktiviert | JA | Globaler EIN/AUS-Schalter für die Funktionalität des Moduls. |
| Modulkonfiguration | Immer den niedrigsten Preis zurückgeben | NEIN (für strikte Kontrolle) / JA (für Flexibilität) | Bestimmt, ob andere nicht-spezifische Preisrabatte weiterhin angewendet werden können, wenn sie zu einem niedrigeren Preis für betroffene Gruppen führen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul konfiguriert, aber Kunden in der ausgewählten Gruppe sehen immer noch spezifische Preise. Was ist falsch?**
A:

1. **Einstellung „Aktiviert“ prüfen:** Stellen Sie sicher, dass der Schalter „Aktiviert“ in der Modulkonfiguration auf **JA** steht.
2. **Gruppenauswahl überprüfen:** Überprüfen Sie nochmals, ob die korrekte(n) Kundengruppe(n) unter „Spezifische Preisrabatte für ausgewählte Gruppen deaktivieren“ ausgewählt ist/sind.
3. **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“. PrestaShop speichert Preisinformationen oft im Cache.
4. **Kundengruppe überprüfen:** Stellen Sie sicher, dass der Kunde, mit dem Sie testen, tatsächlich der Gruppe zugewiesen ist, die Sie im Modul ausgewählt haben. Dies können Sie unter **Kunden > Kunden** im Back Office überprüfen.
5. **Theme-Kompatibilität:** Obwohl selten, können einige stark angepasste Themes stören. Wenn das Problem weiterhin besteht, versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme zu wechseln, um Theme-Konflikte auszuschließen.

**F: Was passiert, wenn ein Kunde in mehreren Gruppen ist und eine Gruppe für die Deaktivierung spezifischer Preise ausgewählt ist, während eine andere nicht ausgewählt ist?**
A: Die Kernlogik von PrestaShop priorisiert typischerweise den niedrigsten Preis. Die Überschreibung dieses Moduls versucht, spezifische Preise für *jede* ausgewählte Gruppe zu entfernen. Wenn ein Kunde in einer Gruppe ist, für die spezifische Preise deaktiviert werden *sollten*, versucht das Modul, den Standardpreis durchzusetzen. Die Einstellung „Immer den niedrigsten Preis zurückgeben“ bestimmt dann, ob andere nicht-spezifische Preisrabatte weiterhin berücksichtigt werden.

**F: Beeinflusst dieses Modul andere Arten von Rabatten, wie Warenkorbregeln oder Katalogpreisregeln?**
A: Dieses Modul zielt speziell auf „spezifische Preise“ ab, wie sie in PrestaShop definiert sind (die Rabatte, die direkt auf Produktseiten oder per CSV-Import festgelegt werden).

- Wenn „Immer den niedrigsten Preis zurückgeben“ auf **NEIN** steht, setzt das Modul den Standardpreis für ausgewählte Gruppen strikt durch und überschreibt potenziell andere Rabatte, wenn diese zu einem niedrigeren Preis als dem Standardpreis führen.
- Wenn „Immer den niedrigsten Preis zurückgeben“ auf **JA** steht, deaktiviert das Modul spezifische Preise, erlaubt aber weiterhin, dass andere Arten von Rabatten (wie Warenkorbregeln oder Katalogpreisregeln) angewendet werden, wenn diese zu einem niedrigeren Preis als dem Standardpreis führen.

**F: Ich möchte das Modul vorübergehend deaktivieren, ohne meine Einstellungen zu verlieren. Wie mache ich das?**
A: Gehen Sie einfach zur Konfigurationsseite des Moduls und setzen Sie den Schalter „Aktiviert“ auf **NEIN**. Alle Ihre ausgewählten Gruppen und andere Einstellungen bleiben erhalten, und Sie können es jederzeit wieder aktivieren, indem Sie es wieder auf **JA** stellen.

**F: Wie übersetze ich den Text des Moduls in andere Sprachen?**
A: Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**. Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Spezifische Preise für ausgewählte Gruppen deaktivieren“. Sie können dann alle sichtbaren Textzeichenfolgen übersetzen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Spezifische Preise für ausgewählte Gruppen deaktivieren“ funktioniert hauptsächlich durch das Überschreiben von PrestaShop-Kernklassen, die sich auf die Produktpreisgestaltung beziehen, insbesondere `Product.php` und `SpecificPrice.php`. Dies ermöglicht es, die Logik abzufangen und zu ändern, die bestimmt, ob spezifische Preise auf ein Produkt angewendet werden, basierend auf der Gruppe des aktuellen Kunden und der Modulkonfiguration. Es folgt einer Standard-PrestaShop-Modulstruktur mit einer Hauptmoduldatei und Klassenüberschreibungen.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird über die Methode `getContent()` der Hauptmodulklasse abgewickelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Die Kernfunktionalität des Moduls wird durch Klassenüberschreibungen implementiert.

- **`exsdis/override/classes/index.php`**:

  - Dies ist eine standardmäßige leere `index.php`-Datei, die typischerweise in Verzeichnissen platziert wird, um die Verzeichnisauflistung zu verhindern. Sie hat keine funktionale Auswirkung auf die Modullogik.
- **`exsdis/override/classes/Product.php`**:

  - **Originalklasse**: `classes/Product.php`
  - **Zweck**: Diese Überschreibung modifiziert die `Product`-Klasse, die zentral dafür ist, wie Produktinformationen, einschließlich Preise, in PrestaShop abgerufen und berechnet werden. Die Modullogik innerhalb dieser Überschreibung fängt Aufrufe zum Abrufen spezifischer Preise für ein Produkt ab.
  - **Schlüssellogik**: Sie prüft, ob das Modul aktiviert ist und ob die Gruppe des aktuellen Kunden zu denjenigen gehört, für die spezifische Preise deaktiviert werden sollen. Wenn ja, manipuliert sie den Prozess zum Abrufen spezifischer Preise, um sicherzustellen, dass für diesen Kunden keine spezifischen Preise zurückgegeben werden. Sie berücksichtigt auch die Konfiguration `exsdis_lowest`, um zu bestimmen, ob der absolut niedrigste Preis (ohne spezifische Preise) dennoch zurückgegeben werden soll.
- **`exsdis/override/classes/SpecificPrice.php`**:

  - **Originalklasse**: `classes/SpecificPrice.php`
  - **Zweck**: Diese Überschreibung zielt auf die `SpecificPrice`-Klasse ab, die für die Verwaltung und Anwendung spezifischer Preisregeln verantwortlich ist.
  - **Schlüssellogik**: Sie modifiziert wahrscheinlich Methoden innerhalb dieser Klasse (z. B. `getSpecificPrice()`, `getSpecificPrices()`), um zu verhindern, dass spezifische Preisobjekte für Kunden in den vorgesehenen Gruppen erstellt oder zurückgegeben werden. Dies arbeitet in Verbindung mit der `Product.php`-Überschreibung, um sicherzustellen, dass spezifische Preise effektiv ignoriert werden.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Das Konfigurationsformular wird dynamisch durch die Methode `getContent()` in `exsdis.php` gerendert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen in der Standardtabelle `ps_configuration`.

  - `ps_configuration`-Einträge:
    - `exsdis_`: (Präfix für allgemeine Moduleinstellungen)
    - `exsdis_groups`: Speichert ein serialisiertes Array oder eine kommagetrennte Zeichenfolge von Kundengruppen-IDs, für die spezifische Preise deaktiviert sind.
    - `exsdis_lowest`: Speichert den Wert (0 oder 1) für die Einstellung „Immer den niedrigsten Preis zurückgeben“.
    - `mypresta_updates`, `update_`, `updatev_`: Bezogen auf MyPresta.eu-Update-Prüfungen.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert in seiner `install()`-Methode keine expliziten Standard-PrestaShop-Hooks. Seine Funktionalität wird hauptsächlich durch Klassenüberschreibungen erreicht, die das Kernverhalten von PrestaShop direkt ändern, anstatt auf Hook-Ereignisse zu reagieren.
  Die Modulbeschreibung erwähnt „Front-Office Hooks: Header, Columns, Product, or Footer“, dies ist jedoch wahrscheinlich eine generische Aussage darüber, wo *Preise* angezeigt werden könnten, nicht wo das Modul selbst Inhalte über Hooks injiziert. Die Überschreibungen behandeln die Preislogik auf einer niedrigeren Ebene.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Spezifische Preise für ausgewählte Gruppen deaktivieren“ wenden Sie sich bitte an Ihr MyPresta.eu-Kundenkonto. Sie können die neuesten Versionen aus Ihrem Bestellverlauf herunterladen und auf die von MyPresta.eu bereitgestellten speziellen Supportkanäle zugreifen.
"""

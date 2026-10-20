---
title: "Zugriff auf Produkte nach Land – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Zugriff auf Produkte nach Land“ von MyPresta.eu."
sidebar:
  label: "Zugriff auf Produkte nach Land – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Access to products by country auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/access-to-products-by-country.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/access-to-products-by-country/)
>
> ---


# Zugriff auf Produkte nach Land

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Zugriff auf Produkte nach Land“. Hier finden Sie alle Einstellungen, um festzulegen, wie der Produktzugriff eingeschränkt wird.

#### Allgemeine Einstellungen

- **Aktiviert / Deaktiviert (Modulstatus)**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul filtert Produkte aktiv basierend auf Länderbeschränkungen.
    - *Wenn deaktiviert:* Das Modul ist inaktiv, und alle Produkte sind für alle Kunden sichtbar, unabhängig von ihrem Land.
  - **Empfohlener Wert:** **Aktiviert**, sobald Sie Ihre Regeln konfiguriert haben.
  - **Händlerszenario / Beispiel:** Sie richten das Modul zum ersten Mal ein; lassen Sie es deaktiviert, bis Sie alle Ihre Regeln definiert haben, und aktivieren Sie es dann, um live zu gehen.
- **Was möchten Sie tun? (Einschränkungstyp)**

  - **Was diese Einstellung bewirkt:** Definiert die Kernlogik Ihrer Länderbeschränkungen: Möchten Sie Produkte in ausgewählten Ländern *blockieren* oder Produkte *NUR* in ausgewählten Ländern *zulassen*?
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Zugriff auf Produkte in ausgewählten Ländern blockieren“ eingestellt:* Produkte, die Sie konfigurieren, werden Kunden in den von Ihnen angegebenen Ländern verborgen. Sie sind überall sonst sichtbar.
    - *Wenn auf „Zugriff auf Produkte NUR in ausgewählten Ländern zulassen“ eingestellt:* Produkte, die Sie konfigurieren, sind *nur* für Kunden in den von Ihnen angegebenen Ländern sichtbar. Sie werden überall sonst verborgen.
  - **Empfohlener Wert:** Wählen Sie basierend auf Ihrem primären Anwendungsfall. Wenn Sie einige Länder haben, in denen ein Produkt eingeschränkt ist, wählen Sie „Blockieren“. Wenn ein Produkt exklusiv für einige Länder ist, wählen Sie „NUR zulassen“.
  - **Händlerszenario / Beispiel:**
    - *Blockieren:* Sie verkaufen eine bestimmte Marke, die nicht nach Kanada versandt werden kann. Sie würden „Zugriff blockieren“ auswählen und dann Kanada für dieses Produkt wählen.
    - *NUR zulassen:* Sie haben ein Sondereditionsprodukt, das nur in den USA und Mexiko zum Verkauf steht. Sie würden „Zugriff NUR zulassen“ auswählen und dann USA und Mexiko für dieses Produkt wählen.
- **Länder auswählen**

  - **Was diese Einstellung bewirkt:** Hier wählen Sie die spezifischen Länder aus, die von der Regel „Was möchten Sie tun?“ betroffen sind.
  - **Auswirkung der Änderung dieser Einstellung:** Die ausgewählten Länder werden entweder daran gehindert, das Produkt zu sehen, oder sind die einzigen, denen es erlaubt ist, es zu sehen, abhängig von der Einstellung „Was möchten Sie tun?“.
  - **Empfohlener Wert:** Wählen Sie alle relevanten Länder basierend auf Ihren Produktbeschränkungen aus.
  - **Händlerszenario / Beispiel:** Wenn Sie Verkäufe nach Kanada und Australien blockieren, würden Sie sowohl Kanada als auch Australien aus der Liste auswählen.
- **Kategorien auswählen**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, die Länderbeschränkungsregeln auf ganze Produktkategorien anstatt auf einzelne Produkte anzuwenden.
  - **Auswirkung der Änderung dieser Einstellung:** Alle Produkte innerhalb der ausgewählten Kategorien erben die oben definierten Länderbeschränkungsregeln.
  - **Empfohlener Wert:** Verwenden Sie dies für umfassende Beschränkungen. Lassen Sie es leer, wenn Sie Beschränkungen produktweise verwalten möchten.
  - **Händlerszenario / Beispiel:** Alle Produkte in Ihrer Kategorie „Elektronik“ können nicht in Brasilien verkauft werden. Sie würden hier die Kategorie „Elektronik“ auswählen.
- **Hersteller auswählen**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, die Länderbeschränkungsregeln auf alle Produkte bestimmter Hersteller anzuwenden.
  - **Auswirkung der Änderung dieser Einstellung:** Alle Produkte der ausgewählten Hersteller erben die Länderbeschränkungsregeln.
  - **Empfohlener Wert:** Verwenden Sie dies für markenbezogene Beschränkungen. Lassen Sie es leer, wenn Sie Beschränkungen produktweise oder kategorieweise verwalten möchten.
  - **Händlerszenario / Beispiel:** Sie haben eine Vertriebsvereinbarung, die Sie daran hindert, Produkte der „Marke X“ in Europa zu verkaufen. Sie würden hier „Marke X“ auswählen.

#### Kunden- & Gruppenausschlüsse

- **Kundengruppen ausschließen**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, bestimmte Kundengruppen von den Länderbeschränkungen auszunehmen. Zum Beispiel könnten Sie eine spezielle B2B-Gruppe haben, der der Kauf eingeschränkter Produkte gestattet ist.
  - **Auswirkung der Änderung dieser Einstellung:** Kunden, die zu den ausgewählten Gruppen gehören, unterliegen *nicht* den von diesem Modul definierten Länderbeschränkungen. Sie sehen alle Produkte.
  - **Empfohlener Wert:** Wählen Sie Gruppen aus, die besonderen Zugriff benötigen, wie z. B. „Großhandelskunden“ oder „Mitarbeiter“. Lassen Sie es leer, wenn alle Kunden Beschränkungen unterliegen sollen.
  - **Händlerszenario / Beispiel:** Sie haben eine Gruppe „VIP-Kunden“, denen der Kauf von Produkten gestattet ist, die in ihrem Land sonst eingeschränkt sind. Sie würden hier die Gruppe „VIP-Kunden“ auswählen.
- **Kunden ausschließen**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, bestimmte einzelne Kunden von den Länderbeschränkungen auszunehmen.
  - **Auswirkung der Änderung dieser Einstellung:** Die ausgewählten einzelnen Kunden unterliegen *nicht* den Länderbeschränkungen. Sie sehen alle Produkte.
  - **Empfohlener Wert:** Verwenden Sie dies für spezifische Ausnahmen. Lassen Sie es leer, wenn nicht benötigt.
  - **Händlerszenario / Beispiel:** Ein bestimmter Kunde ist ein langjähriger Partner und benötigt unabhängig von seinem Standort Zugriff auf alle Produkte. Sie würden hier sein Kundenkonto auswählen.

#### Geolocation- & Simulationseinstellungen

- **Priorität der Herkunftsidentifikationsmethoden festlegen**

  - **Was diese Einstellung bewirkt:** Bestimmt die Reihenfolge, in der das Modul versucht, das Land des Kunden zu identifizieren. Dies ist entscheidend für die Genauigkeit.
  - **Auswirkung der Änderung dieser Einstellung:** Das Modul versucht zuerst die Methode ganz oben in der Liste. Wenn diese fehlschlägt oder nicht verfügbar ist, geht es zur nächsten über.
  - **Empfohlener Wert:**
    1. **Lieferadresse (falls verfügbar):** Dies ist die genaueste für die tatsächliche Kaufabsicht.
    2. **Geolocation:** Gut für das anfängliche Browsen.
    3. **Land des Kundenkontos:** Wenn angemeldet.
  - **Händlerszenario / Beispiel:** Ein Kunde surft aus den USA (Geolocation), beabsichtigt aber, nach Kanada zu versenden. Wenn „Lieferadresse“ priorisiert wird, verwendet das Modul Kanada für Beschränkungen, sobald diese im Warenkorb eingegeben wurde.
- **Lieferadresse verwenden**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, berücksichtigt das Modul das im Warenkorb ausgewählte Lieferland des Kunden als dessen „Herkunft“ für die Anwendung von Beschränkungen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Wenn ein Kunde ein eingeschränktes Produkt in den Warenkorb legt und dann eine Lieferadresse in einem blockierten Land auswählt, verhindert das Modul den Checkout oder entfernt das Produkt.
    - *Wenn deaktiviert:* Das Modul verlässt sich ausschließlich auf die IP-Geolocation oder das registrierte Land des Kunden, was möglicherweise nicht mit dem beabsichtigten Versandziel übereinstimmt.
  - **Empfohlener Wert:** **JA**. Dies bietet die genaueste und praktischste Durchsetzung von Beschränkungen während des Checkout-Prozesses.
  - **Händlerszenario / Beispiel:** Ein Kunde aus Deutschland (wo ein Produkt erlaubt ist) legt es in den Warenkorb, wählt dann aber eine Lieferadresse in Österreich (wo das Produkt blockiert ist). Mit dieser Einstellung verhindert das Modul die Bestellung.
- **Besuch simulieren**

  - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, Ihre Länderbeschränkungen zu testen, indem Sie einen Besuch aus einem bestimmten Land simulieren, ohne Ihre IP-Adresse tatsächlich zu ändern.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul behandelt Ihre aktuelle Sitzung so, als ob Sie aus dem unter „IP simulieren“ angegebenen Land surfen würden.
    - *Wenn deaktiviert:* Das Modul verwendet Ihre tatsächliche IP-Adresse für die Geolocation.
  - **Empfohlener Wert:** **Deaktiviert** für Live-Shops. **Aktiviert** nur zum Testen.
  - **Händlerszenario / Beispiel:** Sie möchten überprüfen, ob ein Produkt für Kunden in Frankreich korrekt ausgeblendet wird. Sie aktivieren „Besuch simulieren“, geben eine französische IP-Adresse ein (oder wählen Frankreich aus, falls verfügbar) und durchsuchen dann Ihren Shop.
- **IP simulieren**

  - **Was diese Einstellung bewirkt:** Wenn „Besuch simulieren“ aktiviert ist, können Sie in diesem Feld eine IP-Adresse aus dem Land eingeben, das Sie simulieren möchten, oder ein Land aus einer Dropdown-Liste auswählen.
  - **Auswirkung der Änderung dieser Einstellung:** Das Modul verwendet diese IP/dieses Land für alle Beschränkungsprüfungen während Ihrer simulierten Sitzung.
  - **Empfohlener Wert:** Geben Sie eine gültige IP-Adresse ein oder wählen Sie ein Land zu Testzwecken aus.
  - **Händlerszenario / Beispiel:** Um einen Besuch aus Deutschland zu simulieren, könnten Sie `88.130.179.0` (eine deutsche IP) eingeben oder einfach „Deutschland“ aus der Liste auswählen.

#### Whitelist-Einstellungen

- **Whitelist aktivieren**

  - **Was diese Einstellung bewirkt:** Diese Einstellung nutzt die integrierte Geolocation-Whitelist-Funktion von PrestaShop. Wenn die Geolocation von PrestaShop aktiv ist, können Sie mit dieser Whitelist bestimmte IP-Adressen oder IP-Bereiche definieren, die *immer* Zugriff auf Ihren Shop haben sollen, unabhängig von ihrem erkannten Land. Dies ist nützlich für Ihre eigenen Büro-IPs oder vertrauenswürdige Partner.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul respektiert die Geolocation-Whitelist von PrestaShop. IPs auf dieser Liste umgehen alle Länderbeschränkungen.
    - *Wenn deaktiviert:* Die Whitelist wird nicht berücksichtigt.
  - **Empfohlener Wert:** **JA**, wenn Sie die Geolocation von PrestaShop verwenden und IPs haben, die Sie whitelisten möchten.
  - **Händlerszenario / Beispiel:** Ihr Büro befindet sich in einem Land, in dem bestimmte Produkte eingeschränkt sind, Sie müssen aber für administrative Zwecke darauf zugreifen. Sie würden die IP-Adresse Ihres Büros zur Geolocation-Whitelist von PrestaShop hinzufügen und diese Einstellung aktivieren.
- **Whitelist**

  - **Was diese Einstellung bewirkt:** Hier verwalten Sie die spezifischen IP-Adressen oder IP-Bereiche, die auf der Whitelist stehen. Dies entspricht direkt der PrestaShop-Einstellung `PS_GEOLOCATION_WHITELIST`.
  - **Auswirkung der Änderung dieser Einstellung:** Jede hier eingegebene IP-Adresse oder jeder Bereich umgeht alle Geolocation-basierten Beschränkungen.
  - **Empfohlener Wert:** Fügen Sie Ihre eigenen Büro-IP-Adressen, Entwicklungs-Server-IPs oder andere vertrauenswürdige IPs hinzu, die immer vollen Zugriff haben sollen.
  - **Händlerszenario / Beispiel:** Sie fügen `192.168.1.1/24` (Ihr Büronetzwerk) hinzu, um sicherzustellen, dass alle Mitarbeiter auf alle Produkte zugreifen können.

#### Update-Einstellungen (Intern)

- **mypresta\_updates, update\_, updatev\_**
  - **Was diese Einstellungen bewirken:** Dies sind interne Einstellungen, die von MyPresta.eu-Modulen zur Verwaltung von Updates und Versionsprüfungen verwendet werden. Sie sind nicht für die direkte Interaktion des Händlers gedacht.
  - **Auswirkung der Änderung dieser Einstellung:** Eine Änderung könnte die Benachrichtigungen über Modul-Updates beeinträchtigen.
  - **Empfohlener Wert:** Lassen Sie diese Einstellungen unverändert.
  - **Händlerszenario / Beispiel:** Kein Händlerszenario; diese sind für die interne Modulverwaltung.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Aktiviert / Deaktiviert** | Aktiviert | Hauptschalter für die Modulfunktionalität. |
| Modulkonfiguration | **Was möchten Sie tun?** | Zugriff blockieren | Definiert, ob Regeln den Zugriff blockieren oder NUR zulassen. |
| Modulkonfiguration | **Länder auswählen** | (Keine) | Länder, die von der Beschränkungsregel betroffen sind. |
| Modulkonfiguration | **Kategorien auswählen** | (Keine) | Kategorien, deren Produkte von der Regel betroffen sind. |
| Modulkonfiguration | **Hersteller auswählen** | (Keine) | Hersteller, deren Produkte von der Regel betroffen sind. |
| Modulkonfiguration | **Kundengruppen ausschließen** | (Keine) | Kundengruppen, die von Beschränkungen ausgenommen sind. |
| Modulkonfiguration | **Kunden ausschließen** | (Keine) | Einzelne Kunden, die von Beschränkungen ausgenommen sind. |
| Modulkonfiguration | **Priorität der Herkunftsidentifikationsmethoden festlegen** | Lieferadresse, Geolocation, Land des Kundenkontos | Reihenfolge der Methoden zur Bestimmung des Kundenlandes. |
| Modulkonfiguration | **Lieferadresse verwenden** | JA | Berücksichtigt die Lieferadresse für die Durchsetzung von Beschränkungen. |
| Modulkonfiguration | **Besuch simulieren** | Deaktiviert | Aktiviert/deaktiviert die IP-Simulation zum Testen. |
| Modulkonfiguration | **IP simulieren** | (Leer) | IP-Adresse/Land zur Simulation für Tests. |
| Modulkonfiguration | **Whitelist aktivieren** | JA | Aktiviert/deaktiviert die Geolocation-Whitelist von PrestaShop. |
| Modulkonfiguration | **Whitelist** | (Leer) | Liste der IP-Adressen/Bereiche zum Umgehen von Beschränkungen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Produkte sind in einem blockierten Land immer noch sichtbar, was soll ich tun?**
A1: Überprüfen Sie zuerst Ihre Modulkonfiguration:
\* Ist das Modul „Aktiviert“?
\* Ist „Was möchten Sie tun?“ korrekt eingestellt (z. B. „Zugriff blockieren“, wenn Sie sie ausblenden möchten)?
\* Sind die richtigen „Länder auswählen“ gewählt?
\* Sind die „Kategorien auswählen“ oder „Hersteller auswählen“ korrekt auf die betreffenden Produkte angewendet?
\* Wenn Sie testen, stellen Sie sicher, dass „Besuch simulieren“ aktiviert und „IP simulieren“ auf das richtige Land eingestellt ist.
\* Leeren Sie schließlich Ihren PrestaShop-Cache (**Erweiterte Parameter > Leistung > Cache leeren**) und Ihren Browser-Cache.

**F2: Meine eigene IP-Adresse scheint blockiert zu sein, obwohl ich mich in einem erlaubten Land befinde.**
A2: Dies kann passieren, wenn Ihre IP-Adresse irgendwie falsch identifiziert wird oder wenn Sie einen Fehler in Ihrer Konfiguration gemacht haben.
\* Überprüfen Sie die Einstellung „Whitelist“ und stellen Sie sicher, dass Ihre Büro- oder persönliche IP-Adresse dort hinzugefügt ist, wenn Sie alle Beschränkungen umgehen möchten.
\* Überprüfen Sie Ihre tatsächliche öffentliche IP-Adresse (Sie können Websites wie „what is my IP“ verwenden).
\* Stellen Sie sicher, dass „Whitelist aktivieren“ aktiviert ist, wenn Sie die integrierte Geolocation-Whitelist von PrestaShop verwenden.

**F3: Wie bestimmt das Modul das Land eines Kunden?**
A3: Das Modul verwendet ein Prioritätssystem:
1. **Lieferadresse:** Wenn „Lieferadresse verwenden“ aktiviert ist und der Kunde eine Lieferadresse im Warenkorb eingegeben hat, wird diese priorisiert.
2. **Geolocation:** Es verwendet die IP-Adresse des Kunden, um seinen geografischen Standort zu bestimmen.
3. **Land des Kundenkontos:** Wenn der Kunde angemeldet ist, wird das in seinem Konto registrierte Land verwendet.
Sie können die Priorität dieser Methoden in der Modulkonfiguration anpassen.

**F4: Ich habe ein benutzerdefiniertes Theme, funktioniert dieses Modul damit?**
A4: Ja, das Modul ist so konzipiert, dass es mit Standard-PrestaShop-Themes funktioniert. Es filtert Produkte hauptsächlich auf Datenebene, bevor sie vom Theme gerendert werden. Wenn Ihr benutzerdefiniertes Theme jedoch eine sehr ungewöhnliche Produktlistenlogik aufweist oder Kern-PrestaShop-Produktanzeige-Hooks überschreibt, könnten geringfügige Anpassungen erforderlich sein. Wenn Sie Probleme feststellen, wenden Sie sich an den MyPresta.eu-Support.

**F5: Kann ich den Zugriff auf bestimmte Produkte einschränken, nicht nur auf Kategorien oder Hersteller?**
A5: Ja, das Modul funktioniert durch das Filtern von Produkten. Während der Hauptkonfigurationsbildschirm die Auswahl von Kategorien und Herstellern ermöglicht, gilt die Kernlogik des Moduls für einzelne Produkte. Sie können „Kategorien auswählen“ und „Hersteller auswählen“ leer lassen und Beschränkungen direkt auf einzelnen Produktseiten verwalten (wenn das Modul dort einen Tab hinzufügt, was bei solchen Modulen üblich ist). *Basierend auf den bereitgestellten Informationen funktioniert das Modul, indem es Regeln konfiguriert, die auf Produkte basierend auf den in der Hauptkonfiguration ausgewählten Kategorien/Herstellern angewendet werden. Es wird kein expliziter Produkt-Tab für die Konfiguration erwähnt, aber die Beschreibung impliziert „jedes Produkt einzeln“. Wenn es keinen Produkt-Tab gibt, ist die Auswahl von Kategorie/Hersteller der primäre Weg, Produkte anzusprechen.*

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Zugriff auf Produkte nach Land“ (`atpbc`) ist als Standard-PrestaShop-Modul aufgebaut und nutzt das MVC-Muster, wo immer es angebracht ist. Seine Hauptfunktion besteht darin, Produktabfragen abzufangen und Ergebnisse basierend auf konfigurierten Länderbeschränkungen und dem identifizierten Kundenstandort zu filtern. Es integriert sich in den PrestaShop-Kern, indem es sich in verschiedene Anzeige- und Aktionspunkte einklinkt, insbesondere solche, die mit dem Abrufen und Anzeigen von Produkten zusammenhängen. Geolocation ist eine Schlüsselkomponente, die den Ursprung des Kunden bestimmt, der dann mit den Modulregeln abgeglichen wird.

### 4.2 Controller (`controllers/`)

Das Modul scheint basierend auf dem bereitgestellten Inventar keine benutzerdefinierten Front-Office- oder Back-Office-Controller in seinem `controllers/`-Verzeichnis zu haben. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul scheint keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen in einem `classes/`-Verzeichnis zu haben. Die Kernlogik und Datenverarbeitung sind wahrscheinlich in der Hauptdatei `atpbc.php` gekapselt, wobei `Configuration` für Einstellungen und direkte Datenbankabfragen oder PrestaShop-Klassen `Product` und `Category` für die Datenmanipulation verwendet werden.

### 4.4 JavaScript-Assets (`views/js/`)

- **`atpbc/lib/searchTool/views/js/autocomplete.js`**
  - **Umfang:** Back-Office.
  - **Zweck:** Dieses Skript bietet wahrscheinlich eine Autocomplete-Funktionalität für Eingabefelder innerhalb der Modulkonfiguration, z. B. zur Auswahl von Kunden, Kategorien oder Herstellern. Es verbessert die Benutzererfahrung, indem es Optionen vorschlägt, während der Administrator tippt, wodurch Fehler reduziert und die Konfiguration beschleunigt wird.
  - **Funktionalität:** Bindet Event-Listener an bestimmte Eingabefelder (z. B. `keyup`, `focus`), sendet AJAX-Anfragen an einen Back-Office-Endpunkt (wahrscheinlich von der Hauptmoduldatei oder einem PrestaShop-Kern-Admin-Controller behandelt), um Vorschläge abzurufen, und zeigt diese Vorschläge in einer Dropdown-Liste an. Es behandelt die Auswahl und das Ausfüllen des Eingabefeldes.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`atpbc/lib/searchTool/views/css/autocomplete.css`**
  - **Umfang:** Back-Office-Admin-Formular-Styling.
  - **Zweck:** Bietet Styling für das Autocomplete-Vorschlags-Dropdown und möglicherweise die Eingabefelder selbst, um ein konsistentes und benutzerfreundliches Erscheinungsbild innerhalb des PrestaShop Back Office zu gewährleisten.
  - **Schlüsselselektoren:** Zielt wahrscheinlich auf Klassen wie `.autocomplete-suggestions`, `.autocomplete-suggestion-item`, `.autocomplete-input` ab, um Layout, Farben, Schriftarten und Hover-Zustände zu steuern. Entwickler können diese in ihrem benutzerdefinierten Admin-Theme oder durch Hinzufügen von CSS mit höherer Spezifität überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`atpbc/lib/searchTool/views/scripts.tpl`**

  - **Umfang:** Back-Office.
  - **Zweck:** Dieses Template wird wahrscheinlich verwendet, um das `autocomplete.js`-Skript und möglicherweise andere JavaScript-bezogene Konfigurationen oder Inline-Skripte für die `searchTool`-Funktionalität einzubinden. Es könnte auch Variablen definieren, die an das JavaScript übergeben werden.
  - **Gerendert in:** Wahrscheinlich in `actionAdminControllerSetMedia` eingehängt oder direkt in das Hauptkonfigurationstemplate eingebunden.
- **`atpbc/views/templates/admin/AdminTab.tpl`**

  - **Umfang:** Back-Office.
  - **Zweck:** Dieses Template ist wahrscheinlich ein generisches Template für einen benutzerdefinierten Admin-Tab oder einen Abschnitt innerhalb der Modulkonfiguration. Es könnte die Struktur für die Anzeige von Listen, Formularen oder anderen administrativen Inhalten enthalten.
  - **Gerendert in:** Könnte von `configuration.tpl` eingebunden oder verwendet werden, wenn das Modul einen dedizierten Admin-Controller hätte.
- **`atpbc/views/templates/admin/button-subcategories.tpl`**

  - **Umfang:** Back-Office.
  - **Zweck:** Dieses Template rendert wahrscheinlich eine Schaltfläche oder ein UI-Element speziell für die Verwaltung von Unterkategorien innerhalb der Modulkonfiguration, möglicherweise für die Einstellung „Kategorien auswählen“, um Kategoriebäume zu erweitern/reduzieren.
  - **Gerendert in:** Innerhalb der `configuration.tpl` bei der Anzeige von Kategorieauswahloptionen.
- **`atpbc/views/templates/admin/configuration.tpl`**

  - **Umfang:** Back-Office.
  - **Zweck:** Dies ist das Haupt-Smarty-Template für die Konfigurationsseite des Moduls, das von der `getContent()`-Methode in `atpbc.php` gerendert wird. Es enthält alle HTML-Formulare, Eingabefelder, Schalter und Auswahllisten für die Moduleinstellungen.
  - **Gerendert in:** Beim Zugriff auf die Konfigurationsseite des Moduls im PrestaShop Back Office.
- **`atpbc/views/templates/hook/displayHeader.tpl`**

  - **Umfang:** Front-Office.
  - **Zweck:** Dieses Template ist in `displayHeader` eingehängt. Es wird typischerweise verwendet, um Front-Office-CSS, JavaScript oder Meta-Tags einzubinden, die früh auf der Seite geladen werden müssen. Für dieses Modul könnte es Logik enthalten, um das Land des Kunden zu erkennen oder clientseitige Variablen für die spätere Verwendung einzurichten.
  - **Gerendert in:** Dem `<head>`-Bereich jeder Front-Office-Seite.
- **`atpbc/views/templates/hook/displayHeaderNoAccess.tpl`**

  - **Umfang:** Front-Office.
  - **Zweck:** Dieses Template ist wahrscheinlich ein Fallback oder eine spezifische Anzeige, wenn ein Kunde als „keinen Zugriff“ auf ein bestimmtes Produkt oder eine Seite erkannt wird. Es könnte ein Umleitungsskript, eine Nachricht oder spezifisches Styling zum Ausblenden von Inhalten enthalten.
  - **Gerendert in:** Potenziell innerhalb von `displayHeader` oder einem anderen Hook, bedingt durch Zugriffsrechte.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul verwendet hauptsächlich die PrestaShop-Tabelle `ps_configuration`, um seine Einstellungen zu speichern (z. B. `atpbc_EXCLUDE_GROUP`, `atpbc_EXCLUDE_CUSTOMER`, `atpbc_COUNTRY`, `atpbc_WTD`, `atpbc_MANUFACT`, `atpbc_CATEGORIES`, `atpbc_PRIORITY`, `atpbc_SIMULATE_ON`, `atpbc_SIMULATE_IP`, `atpbc_DELIVERY`, `atpbc_WHITELIST_ON`).
  - Es scheint basierend auf dem bereitgestellten Inventar keine benutzerdefinierten SQL-Tabellen zu erstellen.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Bevor der Inhalt eines Admin-Controllers gerendert wird, nachdem Medien gesetzt wurden. | Zum Einbinden von Back-Office-JS/CSS (z. B. `autocomplete.js`, `autocomplete.css`) für die Konfigurationsseite des Moduls. |
| `actionDispatcherAfter` | Nachdem der Dispatcher eine Anfrage verarbeitet hat. | Potenziell verwendet, um Umleitungen durchzuführen oder die Antwort basierend auf Zugriffsregeln zu ändern, nachdem eine Seite identifiziert wurde. |
| `displayFilterProductSearch` | Während der Produktfiltersuche. | Zum Ändern der Produktsuchergebnisse, Entfernen eingeschränkter Produkte basierend auf dem Land. |
| `actionProductUpdate` | Nachdem ein Produkt im Back Office aktualisiert wurde. | Um den Cache bezüglich der Produktverfügbarkeit zu leeren oder Regeln für das aktualisierte Produkt neu zu bewerten. |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | Zum Hinzufügen zusätzlicher Felder oder eines Tabs für produktspezifische Zugriffsregeln (obwohl nicht explizit angegeben, ist dies eine häufige Verwendung für diesen Hook). |
| `actionCartSave` | Nachdem ein Warenkorb gespeichert oder aktualisiert wurde. | Um zu überprüfen, ob Produkte im Warenkorb für das identifizierte Land des Kunden erlaubt sind (insbesondere wenn „Lieferadresse verwenden“ aktiviert ist). |
| `FilterProductSearch` | Während der Produktfiltersuche (ähnlich `displayFilterProductSearch`, oft zur direkten Manipulation der Abfrage). | Zum Ändern der Datenbankabfrage für Produktsuchen, um sicherzustellen, dass eingeschränkte Produkte nicht abgerufen werden. |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Zum Einbinden von Front-Office-JavaScript/CSS (z. B. `displayHeader.tpl`, `displayHeaderNoAccess.tpl`) oder zur frühzeitigen Ländererkennung. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und professionellen Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, sicherzustellen, dass Ihr Modul optimal funktioniert und das bestmögliche Erlebnis für Ihren Shop bietet.

---
title: "Bedingte Bestellvalidierung – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Bedingte Bestellvalidierung' von MyPresta.eu."
sidebar:
  label: "Bedingte Bestellvalidierung – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Conditional Order Validation auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/conditional-order-validation.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/conditional-order-validation/)
>
> ---


# Bedingte Bestellvalidierung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Bedingte Bestellvalidierung)

Dies ist der Haupteinstiegspunkt für globale Moduleinstellungen.

- **Menüpfad:** Back Office > Module > Modul-Manager > Bedingte Bestellvalidierung > Konfigurieren

#### 2.1.1 Allgemeine Einstellungen

| Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- |
| **Bedingte Bestellvalidierung aktivieren** | JA | **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das gesamte Modul. Wenn deaktiviert, sind keine Ihrer definierten Richtlinien aktiv, und Kunden können ohne Einschränkungen durch dieses Modul zur Kasse gehen.   **Auswirkung einer Änderung dieser Einstellung:**   *Wenn aktiviert:* Das Modul beginnt, alle aktiven Richtlinien, die Sie erstellt haben, zu bewerten. Wenn ein Warenkorb gegen eine Richtlinie verstößt, sehen Kunden Warnungen oder werden gemäß Ihren Richtlinieneinstellungen vom Checkout blockiert.   *Wenn deaktiviert:* Das Modul wird inaktiv. Es werden keine Richtlinien überprüft und keine Nachrichten angezeigt.   **Empfohlener Wert:** JA (sobald Sie Ihre Richtlinien konfiguriert haben).   **Händlerszenario:** Aktivieren Sie dies, nachdem Sie Ihre ersten Richtlinien eingerichtet und diese mit dem Simulator getestet haben. |
| **Validierungsmeldungen anzeigen auf** | Warenkorb & Checkout | **Was diese Einstellung bewirkt:** Steuert, wo die Warn- oder Blockiermeldungen des Moduls dem Kunden angezeigt werden.   **Auswirkung einer Änderung dieser Einstellung:**   *Wenn auf „Warenkorb & Checkout“ eingestellt:* Nachrichten werden sowohl auf der Warenkorbseite als auch während der verschiedenen Schritte des Checkout-Prozesses angezeigt. Dies bietet maximale Sichtbarkeit und frühes Feedback für den Kunden.   *Wenn auf „Nur Warenkorb“ eingestellt:* Nachrichten werden nur auf der Warenkorbseite angezeigt. Kunden könnten weiter in den Checkout gelangen, bevor sie blockiert werden, wenn sie die Warenkorbwarnung ignorieren.   *Wenn auf „Nur Checkout“ eingestellt:* Nachrichten werden nur während des Checkout-Prozesses angezeigt. Kunden sehen keine Warnungen auf der Warenkorbseite, was später im Prozess zu Frustration führen könnte.   **Empfohlener Wert:** Warenkorb & Checkout.   **Händlerszenario:** Für die beste Kundenerfahrung zeigen Sie Nachrichten frühzeitig und häufig an (Warenkorb & Checkout), damit Kunden ihren Warenkorb korrigieren können, bevor sie Zeit in den Checkout-Prozess investieren. |
| **Checkout mit Warnungen erlauben** | NEIN | **Was diese Einstellung bewirkt:** Bestimmt, ob Kunden den Checkout fortsetzen können, auch wenn ihr Warenkorb eine „Warn“-Richtlinie (im Gegensatz zu einer „Blockier“-Richtlinie) auslöst.   **Auswirkung einer Änderung dieser Einstellung:**   *Wenn aktiviert (JA):* Wenn eine Richtlinie auf „Warnung“ eingestellt ist, sieht der Kunde die Warnmeldung, kann aber trotzdem auf die Schaltfläche „Zur Kasse gehen“ oder „Bestellung aufgeben“ klicken. Dies ist nützlich für sanfte Empfehlungen oder nicht-kritische Probleme.   *Wenn deaktiviert (NEIN):* Wenn eine Richtlinie auf „Warnung“ eingestellt ist, sieht der Kunde die Warnmeldung, und die Schaltfläche „Zur Kasse gehen“ oder „Bestellung aufgeben“ wird deaktiviert, bis die Warnbedingung behoben ist. Dies bewirkt effektiv, dass „Warnungen“ im Checkout-Stadium wie „Blockierungen“ wirken.   **Empfohlener Wert:** NEIN (es sei denn, Sie haben sehr spezifische „sanfte“ Warnungen).   **Händlerszenario:** Wenn Sie eine Richtlinie wie „Kunden, die über 100 $ kaufen, erhalten kostenlosen Versand“ haben und Sie *vorschlagen* möchten, dass sie mehr in ihren Warenkorb legen, es aber nicht *erzwingen* wollen, könnten Sie dies aktivieren. Für die meisten Geschäftsregeln möchten Sie es jedoch deaktivieren, um die Einhaltung sicherzustellen. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul führt zwei leistungsstarke neue Bereiche in Ihrem PrestaShop Back Office-Menü ein: „Richtlinien“ und „Audit-Log“.

#### 2.2.1 Richtlinien (Back Office > Bedingte Bestellvalidierung > Richtlinien)

Hier definieren, verwalten und aktivieren Sie Ihre Regeln für die bedingte Bestellvalidierung. Jede „Richtlinie“ ist eine Reihe von Bedingungen, die, wenn sie erfüllt sind, den Kunden entweder blockieren oder warnen.

- **Menüpfad:** Back Office > Bedingte Bestellvalidierung > Richtlinien
- **Verfügbare Aktionen & Einstellungen:**

  - **Richtlinienliste:** Eine Tabelle, die alle von Ihnen erstellten Richtlinien anzeigt, mit deren Namen, Status (aktiviert/deaktiviert), Typ (blockierend/warnend) und Priorität.
  - **Neue Richtlinie hinzufügen:** Klicken Sie auf diese Schaltfläche, um eine neue Validierungsrichtlinie zu erstellen.
  - **Richtlinie bearbeiten:** Ändern Sie den Namen, die Bedingungen, die Nachrichten und den Status einer bestehenden Richtlinie.
  - **Richtlinie duplizieren:** Erstellen Sie schnell eine Kopie einer bestehenden Richtlinie, um sie als Ausgangspunkt für eine neue zu verwenden. Dies spart Zeit beim Erstellen ähnlicher Regeln.
  - **Richtlinie aktivieren/deaktivieren:** Schalten Sie den aktiven Status einer Richtlinie um, ohne sie zu löschen.
  - **Richtlinie löschen:** Entfernen Sie eine Richtlinie dauerhaft.
  - **Simulator:** Ein entscheidendes Werkzeug (oft auf dem Bildschirm zur Richtlinienerstellung/-bearbeitung oder als dedizierter Tab zu finden), das es Ihnen ermöglicht, Ihre Richtlinien mit einem simulierten Warenkorb zu testen, bevor sie live gehen. Dies hilft, unbeabsichtigtes Blockieren legitimer Bestellungen zu verhindern.
- **Formular zur Richtlinienerstellung/-bearbeitung:**

  - **Richtlinienname:** Ein beschreibender Name für Ihre Richtlinie (z. B. „Mindestbestellwert für Großhandel“, „Altersbeschränkung für Alkohol“).
  - **Status:** Aktivieren oder Deaktivieren der Richtlinie.
  - **Richtlinientyp:**
    - **Blockierend:** Wenn die Bedingungen erfüllt sind, wird der Kunde am Checkout *gehindert*.
    - **Warnung:** Wenn die Bedingungen erfüllt sind, sieht der Kunde eine Warnmeldung, kann aber je nach globaler Einstellung „Checkout mit Warnungen erlauben“ *möglicherweise* fortfahren oder auch nicht.
  - **Priorität:** Wenn mehrere Richtlinien aktiv sind und ausgelöst werden, bestimmt dies die Reihenfolge, in der Nachrichten angezeigt werden oder welche Richtlinie Vorrang hat (niedrigere Zahl = höhere Priorität).
  - **Bedingungs-Builder:** Dies ist der Kern der Richtlinie. Sie erstellen einen Baum von Bedingungen mit „UND“ / „ODER“-Logik.
    - **Bedingungstypen:** Sie können typischerweise aus einer Vielzahl von Bedingungen wählen:
      - **Warenkorb-Ebene:** Gesamtwert des Warenkorbs, Gesamtmenge der Artikel, Anzahl der einzigartigen Produkte.
      - **Produkt-Ebene:** Spezifische Produkt-IDs, Kategorien, Hersteller, Lieferanten, Produktattribute, Mindest-/Höchstmenge eines bestimmten Produkts.
      - **Kunden-Ebene:** Kundengruppe, spezifische Kunden-ID, Land des Kunden.
      - **Versand-Ebene:** Ausgewählter Spediteur, Versandzone.
    - **Operatoren:** (z. B. „ist gleich“, „ist größer als“, „enthält“, „ist nicht“).
    - **Werte:** Der spezifische Datenpunkt, mit dem verglichen werden soll (z. B. „100“ für einen Mindestwert, „Elektronik“ für eine Kategorie).
  - **Kundenmeldung:** Die Nachricht, die dem Kunden im Front Office angezeigt wird, wenn diese Richtlinie ausgelöst wird. Machen Sie sie klar, hilfreich und umsetzbar (z. B. „Ihr Warenkorb muss mindestens 5 Einheiten von Produkt X enthalten, um fortzufahren.“).
  - **Admin-Meldung (Optional):** Eine interne Notiz für Sie selbst oder andere Administratoren.
- **Auswirkung von Änderungen:**

  - Das Hinzufügen/Ändern einer Richtlinie wirkt sich direkt auf das Front-Office-Checkout-Erlebnis für Kunden aus.
  - Das Aktivieren einer Richtlinie aktiviert ihre Regeln. Das Deaktivieren deaktiviert sie ohne Löschung.
  - Der Simulator ermöglicht es Ihnen, Änderungen zu testen, ohne Live-Kunden zu beeinflussen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

  1. Identifizieren Sie eine Geschäftsregel, die Sie durchsetzen möchten (z. B. „Großhandelskunden müssen mindestens 500 $ bestellen“).
  2. Gehen Sie zu „Richtlinien“ und klicken Sie auf „Neue Richtlinie hinzufügen“.
  3. Geben Sie ihr einen klaren Namen, setzen Sie sie auf „Blockierend“ und definieren Sie die Bedingungen (z. B. „Kundengruppe IST Großhandel“ UND „Warenkorb-Gesamt IST GRÖSSER ALS ODER GLEICH 500“).
  4. Schreiben Sie eine hilfreiche Kundenmeldung (z. B. „Großhandelsbestellungen erfordern einen Mindestgesamtbetrag von 500 $. Bitte fügen Sie weitere Artikel zu Ihrem Warenkorb hinzu.“).
  5. Verwenden Sie den „Simulator“, um verschiedene Szenarien zu testen (z. B. ein Großhandelskunde mit einem 400 $-Warenkorb, ein Einzelhandelskunde mit einem 400 $-Warenkorb, ein Großhandelskunde mit einem 600 $-Warenkorb).
  6. Sobald Sie zufrieden sind, aktivieren Sie die Richtlinie.

#### 2.2.2 Audit-Log (Back Office > Bedingte Bestellvalidierung > Audit-Log)

Das Audit-Log bietet eine historische Aufzeichnung darüber, wann Richtlinien ausgelöst wurden, von wem und was das Ergebnis war. Dies ist von unschätzbarem Wert für die Fehlerbehebung und das Verständnis des Kundenverhaltens.

- **Menüpfad:** Back Office > Bedingte Bestellvalidierung > Audit-Log
- **Verfügbare Aktionen & Einstellungen:**

  - **Protokollliste:** Eine Tabelle, die Einträge für jedes Mal anzeigt, wenn eine Richtlinie bewertet und ausgelöst wurde.
  - **Spalten:**
    - **Datum/Uhrzeit:** Wann das Ereignis aufgetreten ist.
    - **Kunde:** Der Kunde, der die Richtlinie ausgelöst hat (falls angemeldet).
    - **Warenkorb-ID:** Die ID des beteiligten Warenkorbs.
    - **Richtlinienname:** Der Name der Richtlinie, die ausgelöst wurde.
    - **Richtlinientyp:** Ob es sich um eine „Blockier“- oder „Warn“-Richtlinie handelte.
    - **Nachricht:** Die dem Kunden angezeigte Nachricht.
    - **Status:** Ob die Bestellung letztendlich validiert, blockiert oder gewarnt wurde.
  - **Filtern/Suchen:** Die Standard-PrestaShop-Listenfilterung ermöglicht die Suche nach Kunde, Richtlinie, Datumsbereich usw.
  - **Warenkorbdetails anzeigen:** Oft können Sie auf eine Warenkorb-ID klicken, um den Inhalt des Warenkorbs zum Zeitpunkt der Richtlinienauslösung zu überprüfen.
- **Auswirkung von Änderungen:** Dieser Bildschirm dient nur zur Anzeige und Überprüfung; Sie können hier keine Änderungen vornehmen. Es ist eine Aufzeichnung von Ereignissen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

  - Wenn ein Kunde ein Problem beim Checkout meldet, überprüfen Sie das Audit-Log, um zu sehen, ob Richtlinien für seinen Warenkorb ausgelöst wurden. Dies kann schnell identifizieren, ob eine Richtlinie falsch konfiguriert ist oder ob der Kunde die Anforderungen einfach nicht erfüllt hat.
  - Überprüfen Sie das Protokoll regelmäßig, um zu verstehen, welche Richtlinien am häufigsten ausgelöst werden und ob Anpassungen erforderlich sind.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| **Modulkonfiguration** | Bedingte Bestellvalidierung aktivieren | JA | Hauptschalter für die Funktionalität des Moduls. |
| **Modulkonfiguration** | Validierungsmeldungen anzeigen auf | Warenkorb & Checkout | Wo Kundenmeldungen erscheinen (Warenkorb, Checkout oder beides). |
| **Modulkonfiguration** | Checkout mit Warnungen erlauben | NEIN | Bestimmt, ob „Warn“-Richtlinien den Checkout blockieren oder nur informieren. |
| **Richtlinien (Admin)** | Richtlinienname | N/A | Beschreibende Kennung für Ihre Regel. |
| **Richtlinien (Admin)** | Status | Aktiviert | Aktiviert oder deaktiviert eine spezifische Richtlinie. |
| **Richtlinien (Admin)** | Richtlinientyp | Blockierend / Warnung | Definiert, ob die Richtlinie den Checkout verhindert oder nur eine Nachricht anzeigt. |
| **Richtlinien (Admin)** | Priorität | N/A | Reihenfolge der Bewertung/Anzeige für mehrere ausgelöste Richtlinien. |
| **Richtlinien (Admin)** | Bedingungs-Builder | N/A | Definiert die logischen Regeln, wann die Richtlinie ausgelöst wird. |
| **Richtlinien (Admin)** | Kundenmeldung | N/A | Die Nachricht, die dem Kunden angezeigt wird, wenn die Richtlinie ausgelöst wird. |
| **Richtlinien (Admin)** | Admin-Meldung | N/A | Interne Notizen für Administratoren. |
| **Audit-Log (Admin)** | (Alle Spalten) | N/A | Zeichnet alle Instanzen von ausgelösten Richtlinien zur Überprüfung auf. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Richtlinien funktionieren nicht, oder Kunden checken immer noch aus, obwohl sie es nicht sollten.**
A:

1.  **Ist das Modul aktiviert?** Überprüfen Sie „Bedingte Bestellvalidierung aktivieren“ in der Hauptmodulkonfiguration.
2.  **Sind die spezifischen Richtlinien aktiviert?** Gehen Sie zu „Richtlinien“ und stellen Sie sicher, dass die Spalte „Status“ für Ihre Richtlinien auf „Aktiviert“ gesetzt ist.
3.  **Richtlinientyp überprüfen:** Ist er auf „Blockierend“ oder „Warnung“ eingestellt? Wenn „Warnung“, überprüfen Sie die globale Einstellung „Checkout mit Warnungen erlauben“. Wenn diese aktiviert ist, können Kunden Warnungen umgehen.
4.  **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort wirksam werden. Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“.
5.  **Simulator:** Verwenden Sie den integrierten „Simulator“ auf dem Bildschirm zur Richtlinienerstellung/-bearbeitung, um Ihre Bedingungen mit verschiedenen Warenkorbszenarien zu testen. Dies ist der effektivste Weg zur Fehlerbehebung.
6.  **Audit-Log:** Überprüfen Sie das „Audit-Log“, um zu sehen, ob Ihre Richtlinien überhaupt ausgelöst werden und was das Ergebnis war.

**F: Die Warn-/Blockiermeldungen sehen in meinem Theme nicht gut aus.**
A: Das Modul verwendet, wo möglich, Standard-PrestaShop-Styling, aber benutzerdefinierte Themes könnten spezifische CSS-Anpassungen überschreiben oder erfordern.

1.  **Grundlegendes CSS:** Das CSS des Moduls ist generisch gestaltet. Wenn Ihr Theme sehr spezifisches Styling hat, müssen Sie möglicherweise einen Webmaster beauftragen, benutzerdefiniertes CSS in die `custom.css`-Datei Ihres Themes einzufügen, um es an Ihr Branding anzupassen.
2.  **Template-Overrides:** Fortgeschrittene Benutzer können die Template-Dateien des Moduls (z. B. `views/templates/hook/validation_banner.tpl`) in ihrem Theme überschreiben, um die HTML-Struktur und das Erscheinungsbild vollständig anzupassen.

**F: Kann ich die Nachrichten für verschiedene Sprachen übersetzen?**
A: Ja, alle kundenorientierten Nachrichten, die Sie in Ihren Richtlinien definieren, sind übersetzbar.

1.  Gehen Sie in Ihrem Back Office zu **International > Übersetzungen**.
2.  Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und die Sprache aus.
3.  Suchen Sie das Modul „Bedingte Bestellvalidierung“ und übersetzen Sie dort die Richtlinienmeldungen.

**F: Ich habe eine Richtlinie erstellt, aber sie blockiert *alle* Bestellungen, auch gültige.**
A: Dies bedeutet normalerweise, dass Ihre Bedingungen zu breit oder falsch konfiguriert sind.

1.  **Bedingungen überprüfen:** Lesen Sie jede Bedingung in Ihrer Richtlinie sorgfältig durch. Stellen Sie sicher, dass die Operatoren (z. B. „IST“, „IST NICHT“, „GRÖSSER ALS“) und Werte korrekt sind.
2.  **UND/ODER-Logik:** Achten Sie genau darauf, ob Sie „UND“ oder „ODER“ zwischen Bedingungsgruppen verwenden. „UND“ bedeutet, dass *alle* Bedingungen wahr sein müssen; „ODER“ bedeutet, dass *mindestens eine* Bedingung wahr sein muss. Ein häufiger Fehler ist die Verwendung von „ODER“, wenn „UND“ beabsichtigt ist, oder umgekehrt.
3.  **Verwenden Sie den Simulator:** Dies ist entscheidend. Simulieren Sie verschiedene „gute“ und „schlechte“ Warenkörbe, um genau zu sehen, warum die Richtlinie ausgelöst wird.

**F: Wie gehe ich mit Multi-Store-Setups um?**
A: Das Modul ist Multi-Store-kompatibel. Beim Erstellen oder Bearbeiten von Richtlinien sollten Sie eine Option sehen, um auszuwählen, für welche Shops die Richtlinie gelten soll. Stellen Sie sicher, dass Ihre Richtlinien den richtigen Shop-Kontexten zugewiesen sind.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „Bedingte Bestellvalidierung“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „Bedingte Bestellvalidierung“ folgt einem robusten MVC-Muster (Model-View-Controller) innerhalb des PrestaShop-Frameworks. Es nutzt `ObjectModel` stark für die Datenpersistenz (Richtlinien, Audit-Logs), benutzerdefinierte Admin-Controller zur Verwaltung dieser Entitäten und eine ausgeklügelte Bedingungsbewertungs-Engine zur Echtzeitverarbeitung von Regeln. Das Modul integriert sich tief in die Bestellvalidierungs- und Warenkorb-Präsentations-Hooks, um sicherzustellen, dass Richtlinien in kritischen Phasen der Kundenreise durchgesetzt werden. Ein Schlüsselaspekt ist die `ConordervalidEngine`, die die Bewertung von `ConordervalidPolicy`-Objekten orchestriert, wobei jedes ein `ConordervalidConditionTree` enthält.

### 4.2 Controller (`controllers/`)

#### 4.2.1 Front-Office-Controller

- `conordervalid/controllers/front/index.php`
  - **Klassenname:** `ConordervalidIndexModuleFrontController` (erweitert wahrscheinlich `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller könnte als allgemeiner Einstiegspunkt dienen oder spezifische Front-Office-AJAX-Anfragen im Zusammenhang mit der Warenkorbvalidierung oder der Anzeige von Nachrichten bearbeiten. Angesichts seines Namens könnte es ein Fallback oder ein einfacher Anzeige-Controller sein.
- `conordervalid/controllers/front/validate.php`
  - **Klassenname:** `ConordervalidValidateModuleFrontController` (erweitert wahrscheinlich `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller ist entscheidend für die Echtzeit-Warenkorbvalidierung. Er verarbeitet wahrscheinlich AJAX-Anfragen von den Warenkorb- oder Checkout-Seiten, um zu überprüfen, ob der aktuelle Warenkorbstatus gegen aktive Richtlinien verstößt. Er würde JSON-Antworten zurückgeben, die angeben, ob der Warenkorb gültig ist, Warnmeldungen oder Blockierungsgründe. Hier würde die `ConordervalidEngine` aufgerufen werden.

#### 4.2.2 Back-Office-Admin-Controller

- `conordervalid/controllers/admin/AdminconordervalidAuditLog.php`
  - **Klassenname:** `AdminconordervalidAuditLogController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Audit-Log (unter dem Menü „Bedingte Bestellvalidierung“)
  - **Verwaltete Entität:** `ConordervalidAuditLog` (zugeordnet zur Tabelle `ps_conordervalid_log`)
  - **Verantwortlichkeit:** Verwaltet die Anzeige und Filterung der Audit-Log-Einträge. Es verwendet `HelperList` zum Rendern des Rasters, sodass Administratoren historische Aufzeichnungen von Richtlinienauslösern anzeigen können.
- `conordervalid/controllers/admin/AdminconordervalidPolicies.php`
  - **Klassenname:** `AdminconordervalidPoliciesController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Richtlinien (unter dem Menü „Bedingte Bestellvalidierung“)
  - **Verwaltete Entität:** `ConordervalidPolicy` (zugeordnet zur Tabelle `ps_conordervalid_policy`)
  - **Verantwortlichkeit:** Dies ist der primäre Controller zur Verwaltung von Validierungsrichtlinien. Er behandelt die CRUD-Operationen für Richtlinien, einschließlich der komplexen Bedingungs-Builder-Oberfläche. Er verwendet `HelperList` für die Richtlinienübersicht und `HelperForm` für die Richtlinienerstellung/-bearbeitung, wobei die Logik von `ConordervalidConditionTree` und `ConordervalidConditionBuilder` integriert wird.
- `conordervalid/controllers/admin/index.php`
  - **Klassenname:** (Wahrscheinlich eine einfache Weiterleitung oder ein Platzhalter)
  - **Verantwortlichkeit:** Oft ist `index.php` in einem Controller-Verzeichnis eine Sicherheitsmaßnahme, um direkte Verzeichnisauflistungen zu verhindern, oder eine einfache Weiterleitung zur Hauptmodulkonfiguration oder zum Dashboard.

### 4.3 Kernklassen & Modelle (`classes/`)

- `conordervalid/classes/ConordervalidAdmin.php`
  - **Verantwortlichkeit:** Enthält wahrscheinlich Hilfsmethoden oder Dienstprogramme speziell für die Admin-Oberfläche, wie z. B. Menüregistrierung, Tab-Verwaltung oder allgemeine Formular-Rendering-Logik.
- `conordervalid/classes/ConordervalidAuditLog.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `ps_conordervalid_log`
  - **`$definition`-Felder:** `id_conordervalid_log`, `id_cart`, `id_customer`, `id_policy`, `policy_name`, `policy_type`, `message`, `date_add`.
  - **Verantwortlichkeit:** Repräsentiert einen einzelnen Eintrag im Audit-Log und speichert Details zu einer ausgelösten Richtlinie.
- `conordervalid/classes/ConordervalidCartState.php`
  - **Verantwortlichkeit:** Eine Dienstprogrammklasse, die den aktuellen Zustand des Warenkorbs eines Kunden (Produkte, Mengen, Gesamtbetrag, Kundeninformationen, ausgewählter Spediteur usw.) kapselt. Dieses Objekt wird an den `ConordervalidConditionEvaluator` übergeben.
- `conordervalid/classes/ConordervalidCompatibility.php`
  - **Verantwortlichkeit:** Behandelt Kompatibilitätsschichten für verschiedene PrestaShop-Versionen (z. B. Unterschiede in Hook-Namen, Klassenstrukturen oder API-Aufrufen zwischen PS 1.7, 8.x und 9.x).
- `conordervalid/classes/ConordervalidCondition.php`
  - **Erweitert:** (Wahrscheinlich eine Basisklasse oder `ObjectModel`, wenn Bedingungen einzeln gespeichert werden)
  - **Verantwortlichkeit:** Repräsentiert eine einzelne Bedingung innerhalb einer Richtlinie (z. B. „Warenkorb-Gesamt > 100“). Es definiert den Bedingungstyp, den Operator und den Wert.
- `conordervalid/classes/ConordervalidConditionEvaluator.php`
  - **Verantwortlichkeit:** Die Kernlogik zur Bewertung einer `ConordervalidCondition` oder `ConordervalidConditionGroup` anhand eines `ConordervalidCartState`-Objekts. Es enthält Methoden zum Vergleichen verschiedener Datentypen und zum Anwenden von Operatoren.
- `conordervalid/classes/ConordervalidConditionGroup.php`
  - **Erweitert:** (Wahrscheinlich eine Basisklasse)
  - **Verantwortlichkeit:** Repräsentiert eine logische Gruppierung von Bedingungen (z. B. „Bedingung A UND (Bedingung B ODER Bedingung C)“). Verwaltet die `UND`/`ODER`-Logik.
- `conordervalid/classes/ConordervalidConditionTree.php`
  - **Erweitert:** (Wahrscheinlich eine Basisklasse oder `ObjectModel`)
  - **Verantwortlichkeit:** Repräsentiert die gesamte hierarchische Struktur der Bedingungen für eine Richtlinie. Es ist eine baumartige Datenstruktur, die aus `ConordervalidConditionGroup`- und `ConordervalidCondition`-Objekten besteht.
- `conordervalid/classes/ConordervalidContext.php`
  - **Verantwortlichkeit:** Ein Wrapper oder eine Erweiterung der PrestaShop-`Context`-Klasse, die möglicherweise modulspezifische Kontextdaten oder Hilfsmethoden hinzufügt.
- `conordervalid/classes/ConordervalidDashboard.php`
  - **Verantwortlichkeit:** Liefert wahrscheinlich Daten und Logik für ein potenzielles Modul-Dashboard im Back Office, das die Richtlinienleistung oder Audit-Log-Statistiken zusammenfasst.
- `conordervalid/classes/ConordervalidEngine.php`
  - **Verantwortlichkeit:** Der zentrale Orchestrator. Er ruft aktive `ConordervalidPolicy`-Objekte ab, iteriert sie und verwendet `ConordervalidConditionEvaluator`, um zu überprüfen, ob ein gegebener Warenkorb gegen eine Richtlinie verstößt. Er bestimmt das Endergebnis (blockiert, gewarnt, gültig) und sammelt Nachrichten.
- `conordervalid/classes/ConordervalidListRenderer.php`
  - **Verantwortlichkeit:** Eine Dienstprogrammklasse zum Rendern von Listen oder Tabellen im Back Office, die möglicherweise das Verhalten von `HelperList` anpasst oder spezifische Spaltenformatierungen bereitstellt.
- `conordervalid/classes/ConordervalidLog.php`
  - **Erweitert:** `ObjectModel` (wahrscheinlich ein Alias oder eine ältere Version von `ConordervalidAuditLog`)
  - **Datenbanktabelle:** `ps_conordervalid_log`
  - **`$definition`-Felder:** Ähnlich wie `ConordervalidAuditLog`.
  - **Verantwortlichkeit:** Speichert Audit-Log-Einträge.
- `conordervalid/classes/ConordervalidPolicy.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `ps_conordervalid_policy`
  - **`$definition`-Felder:** `id_conordervalid_policy`, `name`, `active`, `type` (blocking/warning), `priority`, `conditions_json` (speichert den `ConordervalidConditionTree` als JSON), `customer_message`, `admin_message`, `date_add`, `date_upd`.
  - **Verantwortlichkeit:** Repräsentiert eine einzelne Validierungsrichtlinie, einschließlich ihrer Bedingungen, Nachrichten und Einstellungen.
- `conordervalid/classes/ConordervalidPolicyDuplicator.php`
  - **Verantwortlichkeit:** Behandelt die Logik zum Duplizieren von `ConordervalidPolicy`-Objekten und stellt sicher, dass alle zugehörigen Bedingungen und Einstellungen korrekt kopiert werden.
- `conordervalid/classes/ConordervalidPreset.php`
  - **Verantwortlichkeit:** Definiert wahrscheinlich vordefinierte Bedingungssätze oder Richtlinienvorlagen, die von Administratoren schnell geladen werden können.
- `conordervalid/classes/ConordervalidRule.php`
  - **Erweitert:** (Wahrscheinlich eine Basisklasse oder `ObjectModel`)
  - **Verantwortlichkeit:** Könnte ein Alias für `ConordervalidCondition` oder eine höhere Abstraktion für eine einzelne Regel innerhalb einer Richtlinie sein.
- `conordervalid/classes/ConordervalidTreeRepository.php`
  - **Verantwortlichkeit:** Verwaltet die Speicherung und den Abruf von `ConordervalidConditionTree`-Objekten, wahrscheinlich durch Serialisierung/Deserialisierung in/aus dem Feld `conditions_json` in `ConordervalidPolicy`.
- `conordervalid/classes/index.php`
  - **Verantwortlichkeit:** Standard-Sicherheitsmaßnahme zur Verhinderung von Verzeichnisauflistungen.

### 4.4 JavaScript-Assets (`views/js/`)

- `conordervalid/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back Office (Admin-Formulare)
  - **Verantwortlichkeit:** Bietet Autocomplete-Funktionalität für Eingabefelder im Admin, wahrscheinlich verwendet bei der Auswahl von Produkten, Kategorien, Kunden usw. innerhalb des Bedingungs-Builders.
- `conordervalid/lib/searchTool/views/views/js/autocomplete.js`
  - **Geltungsbereich:** Back Office (Admin-Formulare)
  - **Verantwortlichkeit:** Duplikat des oben Genannten, wahrscheinlich ein Fehler in der Paketierung oder ein veralteter Pfad.
- `conordervalid/views/js/adminConditionBuilder.js`
  - **Geltungsbereich:** Back Office (`AdminconordervalidPoliciesController`)
  - **Verantwortlichkeit:** Treibt die interaktive Bedingungs-Builder-Oberfläche im Formular zur Richtlinienerstellung/-bearbeitung an. Behandelt das Hinzufügen/Entfernen von Bedingungen, die Verwaltung der UND/ODER-Logik und die Aktualisierung der zugrunde liegenden JSON-Struktur des Bedingungsbaums.
- `conordervalid/views/js/adminConordervalidDashboard.js`
  - **Geltungsbereich:** Back Office (Admin-Dashboard, falls implementiert)
  - **Verantwortlichkeit:** Bietet dynamische Funktionalität für ein potenzielles Modul-Dashboard, wie z. B. Diagramm-Rendering, Datenfilterung oder AJAX-Updates.
- `conordervalid/views/js/adminConordervalidSearchTool.js`
  - **Geltungsbereich:** Back Office (Admin-Formulare)
  - **Verantwortlichkeit:** Integriert das Suchwerkzeug (z. B. für Produkte, Kategorien) in verschiedene Admin-Formulare, wahrscheinlich verwendet vom Bedingungs-Builder.
- `conordervalid/views/js/adminConordervalidSimulator.js`
  - **Geltungsbereich:** Back Office (`AdminconordervalidPoliciesController`)
  - **Verantwortlichkeit:** Behandelt die Logik für den Richtlinien-Simulator. Erfasst simulierte Warenkorbdaten, sendet diese per AJAX an einen Front-Controller (z. B. `validate.php`) und zeigt die Validierungsergebnisse an.
- `conordervalid/views/js/adminPolicyRules.js`
  - **Geltungsbereich:** Back Office (`AdminconordervalidPoliciesController`)
  - **Verantwortlichkeit:** Enthält spezifische JS-Logik zur Verwaltung der Anzeige und Interaktion von Richtlinienregeln innerhalb der Admin-Oberfläche, möglicherweise im Zusammenhang mit Drag-and-Drop-Neuanordnung oder schnellen Bearbeitungen.
- `conordervalid/views/js/validation.js`
  - **Geltungsbereich:** Front Office (Warenkorb-, Checkout-Seiten)
  - **Verantwortlichkeit:** Dies ist das primäre Front-Office-JS. Es überwacht Warenkorbänderungen (z. B. Mengenaktualisierung, Produktentfernung), löst AJAX-Aufrufe an den `validate.php`-Front-Controller aus und aktualisiert dann dynamisch die Benutzeroberfläche, um Warn-/Blockiermeldungen anzuzeigen oder Checkout-Buttons basierend auf der Antwort zu aktivieren/deaktivieren. Es verwendet wahrscheinlich `prestashop.on` für die Ereignisbindung.

### 4.5 CSS-Stylesheets (`views/css/`)

- `conordervalid/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back Office (Admin-Formulare)
  - **Haupt-UI-Komponenten:** Stile für die Autocomplete-Dropdowns und Eingabefelder, die im Admin-Suchwerkzeug verwendet werden.
  - **Schlüsselselektoren:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`.
- `conordervalid/lib/searchTool/views/views/css/autocomplete.css`
  - **Geltungsbereich:** Back Office (Admin-Formulare)
  - **Haupt-UI-Komponenten:** Duplikat des oben Genannten.
  - **Schlüsselselektoren:** Wie oben.
- `conordervalid/views/css/admin_conordervalid.css`
  - **Geltungsbereich:** Back Office (Admin-Formulare und Listen)
  - **Haupt-UI-Komponenten:** Stile für die Richtlinienliste, das Formular zur Richtlinienerstellung/-bearbeitung, den Bedingungs-Builder und das Audit-Log.
  - **Schlüsselselektoren:** `.conordervalid-policy-card`, `.conordervalid-condition-group`, `.conordervalid-condition-row`, `.conordervalid-simulator-results`.
- `conordervalid/views/css/front.css`
  - **Geltungsbereich:** Front Office (Warenkorb-, Checkout-Seiten)
  - **Haupt-UI-Komponenten:** Stile für die Warn-/Blockierbanner und Nachrichten, die Kunden angezeigt werden.
  - **Schlüsselselektoren:** `.conordervalid-validation-banner`, `.conordervalid-warning`, `.conordervalid-blocking`, `.conordervalid-message-list`.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### 4.6.1 Hook-Templates (`views/templates/hook/`)

- `conordervalid/views/templates/hook/admin_order.tpl`
  - **Hook:** `DisplayAdminOrder`
  - **Ausgabe:** Ein Block innerhalb der Back Office-Bestellansicht, der möglicherweise anzeigt, welche Richtlinien für eine bestimmte Bestellung oder einen Warenkorb ausgelöst wurden.
- `conordervalid/views/templates/hook/validation_banner.tpl`
  - **Hook:** `DisplayPaymentTop`, `DisplayShoppingCartFooter`, `DisplayCheckoutSummaryTop`
  - **Ausgabe:** Die HTML-Struktur für die Front-Office-Warn-/Blockiermeldungen, die dem Kunden angezeigt werden. Dieses Template empfängt Variablen wie `$validation_messages`, `$is_blocked` usw.

#### 4.6.2 Admin-Templates (`views/templates/admin/`)

- `conordervalid/lib/searchTool/views/scripts.tpl`
  - **Ausgabe:** Smarty-Template zum Einbinden von JS/CSS-Assets im Zusammenhang mit dem Suchwerkzeug im Admin.
- `conordervalid/lib/searchTool/views/views/scripts.tpl`
  - **Ausgabe:** Duplikat des oben Genannten.
- `conordervalid/views/templates/admin/auditPreview.tpl`
  - **Ausgabe:** Ein partielles Template zur Anzeige einer Vorschau oder Zusammenfassung von Audit-Log-Einträgen, möglicherweise verwendet innerhalb eines Dashboards oder einer spezifischen Ansicht.
- `conordervalid/views/templates/admin/dashboard.tpl`
  - **Ausgabe:** Das Haupttemplate für ein potenzielles Modul-Dashboard im Back Office, das Statistiken, aktuelle Logs oder Richtlinienzusammenfassungen anzeigt.
- `conordervalid/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Ausgabe:** Benutzerdefinierte Aktionsschaltfläche zum Duplizieren von Richtlinien innerhalb der `HelperList`-Ansicht für `AdminconordervalidPoliciesController`.
- `conordervalid/views/templates/admin/policiesPreview.tpl`
  - **Ausgabe:** Ein partielles Template zur Anzeige einer Vorschau oder Zusammenfassung von Richtlinien, ähnlich wie `auditPreview.tpl`.
- `conordervalid/views/templates/admin/policyConditionBuilder.tpl`
  - **Ausgabe:** Die komplexe HTML-Struktur für die interaktive Bedingungs-Builder-Oberfläche, die beim Erstellen oder Bearbeiten einer Richtlinie verwendet wird. Dieses Template arbeitet eng mit `adminConditionBuilder.js` zusammen.
- `conordervalid/views/templates/admin/policyRuleCard.tpl`
  - **Ausgabe:** Ein kleineres, wiederverwendbares Template zur Anzeige einer einzelnen Regel oder Bedingung innerhalb des Bedingungs-Builders.
- `conordervalid/views/templates/admin/policyRulesTable.tpl`
  - **Ausgabe:** Eine tabellenartige Struktur zur Anzeige einer Liste von Regeln, möglicherweise verwendet in der Richtlinienübersicht oder im Simulator.
- `conordervalid/views/templates/admin/scopeSelector.tpl`
  - **Ausgabe:** Template zur Auswahl des Geltungsbereichs einer Richtlinie (z. B. spezifische Shops in einer Multi-Store-Umgebung).

#### 4.6.3 Front-Office-Templates (`views/templates/front/`)

- (Keine dedizierten eigenständigen Front-Office-Templates identifiziert, da die Front-Office-Anzeige über Hook-Templates wie `validation_banner.tpl` erfolgt.)

### 4.7 Datenbankschema & Hooks-Map

#### 4.7.1 Datenbanktabellen

- `ps_conordervalid_policy`
  - **Zweck:** Speichert die Definition jeder Validierungsrichtlinie.
  - **Schlüsselfelder:** `id_conordervalid_policy` (PK), `name`, `active` (boolean), `type` (enum: ‘blocking’, ‘warning’), `priority`, `conditions_json` (TEXT, speichert serialisierten `ConordervalidConditionTree`), `customer_message` (TEXT), `admin_message` (TEXT), `date_add`, `date_upd`.
- `ps_conordervalid_log`
  - **Zweck:** Speichert Audit-Trail-Einträge für ausgelöste Richtlinien.
  - **Schlüsselfelder:** `id_conordervalid_log` (PK), `id_cart`, `id_customer`, `id_policy`, `policy_name`, `policy_type`, `message`, `date_add`.
- `ps_configuration`
  - **Zweck:** Speichert globale Moduleinstellungen.
  - **Schlüsselfelder:** `CONORDERVALID_DISPLAY_SURFACES` (z. B. ‘cart,checkout’), `CONORDERVALID_ENABLED` (boolean), `CONORDERVALID_ALLOW_WARN_CHECKOUT` (boolean).

#### 4.7.2 Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt & Kontext | Technischer Zweck |
| --- | --- | --- |
| `DisplayHeader` | Rendert im `<head>`-Bereich aller Front-Office-Seiten. | Fügt Front-Office-CSS (`front.css`) und JS (`validation.js`) Assets ein. |
| `ActionFrontControllerInitAfter` | Nach der Initialisierung eines Front-Controllers. | Potenziell zur Initialisierung des Modulkontextes, zum Laden von Richtlinien oder zur Durchführung früher Validierungsprüfungen verwendet. |
| `ActionObjectProductInCartDeleteBefore` | Bevor ein Produkt aus dem Warenkorb entfernt wird. | Könnte verwendet werden, um den Warenkorbzustand vor einer Änderung zu protokollieren oder das Löschen zu verhindern, wenn es gegen eine Richtlinie verstößt. |
| `ActionObjectProductInCartDeleteAfter` | Nachdem ein Produkt aus dem Warenkorb entfernt wurde. | Erneute Bewertung der Warenkorbrichtlinien nach einer Produktentfernung, Auslösen eines AJAX-Updates. |
| `ActionCartSave` | Nachdem ein Warenkorb gespeichert wurde (z. B. Mengenaktualisierung, Produkt hinzufügen/entfernen). | Löst die erneute Bewertung aller aktiven Richtlinien gegen den aktualisierten Warenkorb aus. |
| `actionPresentCart` | Wenn der Warenkorb zur Anzeige vorbereitet wird (z. B. auf der Warenkorbseite). | Fügt Validierungsmeldungen in das Warenkorbseiten-Template ein. |
| `DisplayShoppingCartFooter` | Am unteren Ende der Warenkorbseite. | Rendert das `validation_banner.tpl` mit allen Warn-/Blockiermeldungen. |
| `DisplayPaymentTop` | Am oberen Ende des Zahlungsbereichs während des Checkouts. | Rendert das `validation_banner.tpl` mit allen Warn-/Blockiermeldungen, möglicherweise Deaktivierung von Zahlungsoptionen. |
| `DisplayCheckoutSummaryTop` | Am oberen Ende der Checkout-Zusammenfassungsseite (vor der endgültigen Bestellbestätigung). | Rendert das `validation_banner.tpl` mit allen Warn-/Blockiermeldungen, möglicherweise Deaktivierung des Bestellbestätigungsbuttons. |
| `ActionFilterPaymentOptions` | Filtert verfügbare Zahlungsoptionen während des Checkouts. | Kann verwendet werden, um Zahlungsmethoden auszublenden oder zu deaktivieren, wenn eine Richtlinie verletzt wird (z. B. „Nachnahme nicht erlaubt für Bestellungen über X $“). |
| `ActionValidateOrderBefore` | Kurz bevor eine Bestellung offiziell validiert wird. | Die letzte kritische Prüfung, um eine Bestellung zu blockieren, wenn blockierende Richtlinien verletzt werden. Protokolliert den Versuch. |
| `ActionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert und erstellt wurde. | Protokolliert die erfolgreiche Bestellvalidierung, zeichnet möglicherweise auf, welche Richtlinien *nicht* verletzt wurden. |
| `DisplayAdminOrder` | Rendert einen Block innerhalb der Back Office-Bestelldetailseite. | Zeigt Informationen über Richtlinien an, die für die spezifische Bestellung ausgelöst (oder bestanden) wurden, unter Verwendung von `admin_order.tpl`. |
| `ActionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Medien (JS/CSS) einstellt. | Fügt Back Office-spezifisches JS (`adminConditionBuilder.js`, `adminConordervalidSimulator.js`) und CSS (`admin_conordervalid.css`) für die Richtlinienverwaltung ein. |
| `DisplayReassurance` | Oft verwendet zur Anzeige von Vertrauenselementen (z. B. sichere Zahlungssymbole). | Könnte potenziell verwendet werden, um eine kleine, persistente Warnung oder einen Status anzuzeigen, wenn ein Warenkorb ungültig ist. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Bedingte Bestellvalidierung“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Konfiguration des Moduls zur Verfügung.

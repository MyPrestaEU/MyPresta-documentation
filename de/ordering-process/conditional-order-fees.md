---
title: "Conditional Order Fees – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Conditional Order Fees“ von MyPresta.eu."
sidebar:
  label: "Conditional Order Fees – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Conditional Order Fees auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/conditional-order-fees.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/conditional-order-fees/)
>
> ---


# Conditional Order Fees

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL), die typischerweise in den meisten PrestaShop-kompatiblen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Conditional Order Fees)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das Modul aktivieren oder deaktivieren und das grundlegende „Produkt“ einrichten, das Ihre Gebühren darstellt.

- **Menüpfad:** Back Office > Module > Modul-Manager > Conditional Order Fees > Konfigurieren

#### Allgemeine Einstellungen

- **Modul aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das gesamte Modul.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul bewertet Ihre definierten Gebührenrichtlinien aktiv und wendet Gebühren auf Warenkörbe an, die die Bedingungen erfüllen.
    - *Wenn deaktiviert:* Es werden keine Gebühren von diesem Modul angewendet, unabhängig von Ihren Richtlinieneinstellungen.
  - **Empfohlener Wert:** JA (sobald Sie Ihre Richtlinien konfiguriert haben).
  - **Händlerszenario / Beispiel:** Sie haben alle Ihre Gebührenrichtlinien eingerichtet und sind bereit, live zu gehen. Aktivieren Sie dies, um Gebühren zu erheben. Wenn Sie alle Gebühren vorübergehend für Wartungsarbeiten oder eine Aktion stoppen müssen, deaktivieren Sie es.
- **Gebühren-Produkt-ID:**

  - **Was diese Einstellung bewirkt:** Diese entscheidende Einstellung verknüpft Ihre Gebühren mit einem spezifischen, versteckten Produkt in Ihrem Katalog. PrestaShop benötigt ein „Produkt“, um jeden Artikel darzustellen, der dem Warenkorb hinzugefügt wird, selbst wenn es sich um eine Dienstleistung oder eine Gebühr handelt. Dieses Modul erstellt zu diesem Zweck während der Installation ein spezielles, nicht sichtbares Produkt.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf eine gültige Produkt-ID gesetzt:* Das Modul verwendet dieses Produkt, um die Gebühr im Warenkorb, im Checkout und in den Bestelldetails darzustellen. Der Produktname wird durch das benutzerdefinierte Gebührenlabel ersetzt, und sein Preis wird durch die berechnete Gebühr überschrieben.
    - *Wenn auf eine ungültige oder nicht existierende Produkt-ID gesetzt:* Das Modul kann keine Gebühren zum Warenkorb hinzufügen, da es kein gültiges „Platzhalter“-Produkt verwenden kann.
  - **Empfohlener Wert:** Verwenden Sie die ID des speziellen Produkts „Conditional Order Fee“, das vom Modul während der Installation erstellt wurde. Sie finden diese ID, indem Sie in Ihrer Produktliste nach „Conditional Order Fee“ suchen (obwohl es normalerweise im Front Office ausgeblendet ist). Das Modul füllt dies oft für Sie vorab aus.
  - **Händlerszenario / Beispiel:** Das Modul erstellt automatisch ein Produkt namens „Conditional Order Fee“ (oder ähnlich) und setzt dessen ID hier. Sie sollten dies im Allgemeinen nicht ändern, es sei denn, Sie möchten absichtlich ein anderes Produkt als Gebührenplatzhalter verwenden (was für die meisten Benutzer nicht empfohlen wird).

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul bietet dedizierte Bereiche in Ihrem PrestaShop Back Office, um Ihre Gebührenrichtlinien zu verwalten und deren Anwendung zu überprüfen.

#### 2.2.1 Conditional Order Fees Dashboard (Back Office > Conditional Order Fees > Dashboard)

Dieser Bildschirm bietet einen Überblick über die Aktivitäten Ihres Moduls, einschließlich einer Zusammenfassung der angewendeten Gebühren und schnellen Zugriff auf die Richtlinienverwaltung.

- **Bildschirmname & Menüpfad:** **Conditional Order Fees > Dashboard** (zu finden unter dem Hauptmenüpunkt „Conditional Order Fees“ in der linken Seitenleiste).
- **Verfügbare Aktionen & Einstellungen:**
  - **Zusammenfassende Statistiken:** Zeigen Sie wichtige Kennzahlen wie die insgesamt erhobenen Gebühren, die Anzahl der Bestellungen mit Gebühren und die durchschnittliche Gebühr pro Bestellung an. Dies hilft Ihnen, die Auswirkungen Ihrer Gebührenrichtlinien zu verstehen.
  - **Zuletzt angewendete Gebühren:** Eine schnelle Liste der jüngsten Bestellungen, bei denen eine bedingte Gebühr angewendet wurde, einschließlich Bestell-ID, Kunde und Gebührenbetrag.
  - **Schnelllinks:** Direkte Links zu „Richtlinien verwalten“ und „Audit-Log anzeigen“.
- **Auswirkung von Änderungen:** Dieser Bildschirm dient hauptsächlich der Überwachung und Navigation. Hier werden keine direkten Änderungen vorgenommen, aber er spiegelt die Auswirkungen Ihrer Gebührenrichtlinien wider.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie dieses Dashboard regelmäßig, um die Leistung Ihrer Gebührenrichtlinien zu überwachen und sicherzustellen, dass sie wie erwartet funktionieren.

#### 2.2.2 Gebührenrichtlinien verwalten (Back Office > Conditional Order Fees > Policies)

Hier definieren, bearbeiten und verwalten Sie alle Ihre bedingten Gebührenregeln. Jede „Richtlinie“ ist ein Satz von Bedingungen, die, wenn sie erfüllt sind, eine spezifische Gebühr anwenden.

- **Bildschirmname & Menüpfad:** **Conditional Order Fees > Policies** (zu finden unter dem Hauptmenüpunkt „Conditional Order Fees“ in der linken Seitenleiste).
- **Verfügbare Aktionen & Einstellungen:**
  - **Richtlinienliste:** Eine Tabelle, die alle Ihre bestehenden Gebührenrichtlinien anzeigt, einschließlich ihres Namens, Status (aktiviert/deaktiviert), Priorität und des Gebührenbetrags/-typs.
  - **Neue Richtlinie hinzufügen:** Klicken Sie auf die Schaltfläche „Neue Richtlinie hinzufügen“, um eine neue Gebührenregel zu erstellen.
    - **Richtlinienname:** Ein beschreibender Name für Ihre interne Referenz (z. B. „Bearbeitungsgebühr für Kleinbestellungen“, „Zuschlag für zerbrechliche Verpackung“).
    - **Status:** Aktivieren oder deaktivieren Sie die Richtlinie.
    - **Priorität:** Wenn mehrere Richtlinien auf denselben Warenkorb zutreffen könnten, wird diejenige mit der höchsten Priorität (niedrigste Zahl) zuerst bewertet. Wenn „Weitere Regeln nicht verarbeiten“ aktiviert ist, wird nur die übereinstimmende Regel mit der höchsten Priorität angewendet.
    - **Gebührentyp:**
      - **Fester Betrag:** Ein spezifischer Geldbetrag (z. B. 5,00 €).
      - **Prozentsatz des Warenkorb-Gesamtbetrags:** Ein Prozentsatz des Warenkorb-Zwischensumme (z. B. 2 %).
      - **Prozentsatz der Produkte im Warenkorb:** Ein Prozentsatz des Gesamtpreises der Produkte im Warenkorb (ohne Versand/Steuern).
    - **Gebührenwert:** Der tatsächliche Betrag oder Prozentsatz basierend auf dem ausgewählten Gebührentyp.
    - **Gebührenlabel (Mehrsprachig):** Der Text, den Kunden in ihrem Warenkorb und ihrer Bestellübersicht sehen werden (z. B. „Bearbeitungsgebühr“, „Servicegebühr“). Dies kann für verschiedene Sprachen übersetzt werden.
    - **Bedingungs-Builder:** Dies ist der Kern der Richtlinie. Sie können komplexe Regeln mit „UND“ / „ODER“-Gruppen erstellen, die Bedingungen kombinieren wie:
      - Warenkorbwert (Gesamt, Zwischensumme, Menge)
      - Kundengruppe
      - Land, Bundesland oder Zone
      - Versanddienstleister
      - Spezifische Produkte im Warenkorb (nach ID, Kategorie, Hersteller, Lieferant)
      - Zahlungsmethode
      - Und mehr…
    - **Weitere Regeln nicht verarbeiten:** Wenn aktiviert, werden, sobald diese Richtlinie angewendet wird, keine anderen Richtlinien mit niedrigerer Priorität für denselben Warenkorb bewertet.
  - **Richtlinien bearbeiten/löschen:** Bestehende Richtlinien ändern oder entfernen.
  - **Richtlinie duplizieren:** Erstellen Sie schnell eine neue Richtlinie basierend auf einer bestehenden, um Zeit beim Erstellen ähnlicher Regeln zu sparen.
- **Auswirkung von Änderungen:** Das Hinzufügen, Bearbeiten oder Löschen von Richtlinien wirkt sich direkt darauf aus, welche Gebühren auf Kundenwarenkörbe und unter welchen Umständen angewendet werden. Falsch konfigurierte Richtlinien können zu unerwarteten Gebühren oder entgangenen Einnahmen führen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Beginnen Sie mit der Definition Ihrer häufigsten Gebührenszenarien.
  2. Verwenden Sie die Schaltfläche „Neue Richtlinie hinzufügen“, um jede Regel zu erstellen.
  3. Erstellen Sie Ihre Bedingungen sorgfältig mit dem Builder. Testen Sie gründlich mit dem Simulator (falls verfügbar, siehe Audit-Log), um sicherzustellen, dass sie wie erwartet funktionieren.
  4. Legen Sie geeignete Prioritäten fest, insbesondere wenn Sie überlappende Bedingungen haben.
  5. Überprüfen und aktualisieren Sie die Richtlinien regelmäßig, wenn sich Ihre Geschäftsanforderungen oder Aktionen ändern.

#### 2.2.3 Audit-Log (Back Office > Conditional Order Fees > Audit Log)

Das Audit-Log bietet eine detaillierte Historie jeder Instanz, in der das Modul einen Warenkorb bewertet und eine Gebühr angewendet (oder nicht angewendet) hat. Dies ist von unschätzbarem Wert für die Fehlerbehebung und das Verständnis, warum bestimmte Gebühren erhoben oder nicht erhoben wurden.

- **Bildschirmname & Menüpfad:** **Conditional Order Fees > Audit Log** (zu finden unter dem Hauptmenüpunkt „Conditional Order Fees“ in der linken Seitenleiste).
- **Verfügbare Aktionen & Einstellungen:**
  - **Log-Einträge:** Eine Tabelle, die jedes Bewertungsereignis anzeigt, einschließlich:
    - Datum und Uhrzeit
    - Kunde (falls angemeldet)
    - Warenkorb-ID
    - Angewendete Richtlinie (falls vorhanden)
    - Gebührenbetrag (falls angewendet)
    - Status (z. B. „Gebühr angewendet“, „Keine Gebühr angewendet“, „Richtlinie nicht erfüllt“)
  - **Detaillierte Ansicht:** Klicken Sie auf einen Log-Eintrag, um eine vollständige Aufschlüsselung zu sehen, wie die Bedingungen für diesen spezifischen Warenkorb bewertet wurden, und welche Bedingungen bestanden und welche fehlschlugen. Dies ist wie ein „Simulator“ für vergangene Ereignisse.
  - **Filtern & Suchen:** Filtern Sie Log-Einträge nach Datum, Kunde, Warenkorb-ID oder Richtlinie, um schnell spezifische Ereignisse zu finden.
- **Auswirkung von Änderungen:** Dieser Bildschirm dient der Überprüfung und Fehlerbehebung. Hier werden keine direkten Änderungen vorgenommen, aber er liefert kritische Einblicke in das Verhalten des Moduls.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Wenn ein Kunde eine unerwartete Gebühr oder das Fehlen einer erwarteten Gebühr meldet, verwenden Sie das Audit-Log zur Untersuchung.
  2. Filtern Sie nach dem Namen des Kunden oder der Warenkorb-ID, um genau zu sehen, welche Richtlinien bewertet wurden und warum.
  3. Verwenden Sie die Detailansicht, um genau zu bestimmen, welche spezifische Bedingung dazu führte, dass eine Richtlinie bestanden oder fehlschlug.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Modul aktivieren | JA | Hauptschalter zum Aktivieren/Deaktivieren aller Modulfunktionen. |
|  | Gebühren-Produkt-ID | Automatisch generierte ID | Verknüpft Gebühren mit einem versteckten Produkt für das PrestaShop-Warenkorbsystem. Nicht ändern, es sei denn, Sie werden dazu angewiesen. |
| **Richtlinien** | Richtlinienname | N/A | Interne Bezeichnung für Ihre Gebührenregel. |
|  | Status | Aktiviert | Aktiviert/deaktiviert eine einzelne Gebührenrichtlinie. |
|  | Priorität | 1 (niedrigste Zahl = höchste Priorität) | Bestimmt die Bewertungsreihenfolge, wenn mehrere Richtlinien zutreffen könnten. |
|  | Gebührentyp | Fester Betrag | Wählen Sie, wie die Gebühr berechnet wird (fest, % des Warenkorbs, % der Produkte). |
|  | Gebührenwert | 0.00 | Der Betrag oder Prozentsatz der Gebühr. |
|  | Gebührenlabel | „Bearbeitungsgebühr“ (Beispiel) | Kundenorientierter Text für die Gebühr im Warenkorb/in der Bestellung. |
|  | Bedingungs-Builder | N/A | Definieren Sie die spezifischen Kriterien (Warenkorb, Kunde, Produkt usw.), damit die Gebühr angewendet wird. |
|  | Weitere Regeln nicht verarbeiten | Nein | Wenn aktiviert, verhindert dies, dass Richtlinien mit niedrigerer Priorität angewendet werden, sobald diese übereinstimmt. |
| **Audit-Log** | (Alle Einträge) | N/A | Bietet eine detaillierte Historie der Gebührenbewertungen zur Fehlerbehebung und Überwachung. |

## 3. Fehlerbehebung für Händler & Häufig gestellte Fragen (FAQ)

**F1: Ich habe eine Richtlinie eingerichtet, aber die Gebühr erscheint nicht im Warenkorb.**
A1:

- **Modulstatus prüfen:** Stellen Sie sicher, dass die Einstellung „Modul aktivieren“ auf der Hauptkonfigurationsseite auf JA gesetzt ist.
- **Richtlinienstatus prüfen:** Stellen Sie sicher, dass die spezifische Richtlinie, die angewendet werden soll, in der Richtlinienliste „Aktiviert“ ist.
- **Bedingungen überprüfen:** Überprüfen Sie die Bedingungen Ihrer Richtlinie. Sind sie alle wirklich vom aktuellen Warenkorb erfüllt? Verwenden Sie das Audit-Log (Conditional Order Fees > Audit Log), um zu sehen, wie Ihre Bedingungen für einen Testwarenkorb bewertet wurden.
- **Gebühren-Produkt-ID:** Überprüfen Sie, ob die „Gebühren-Produkt-ID“ auf der Hauptkonfigurationsseite korrekt ist und auf das vom Modul erstellte spezielle Produkt verweist.
- **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung) und Ihren Browser-Cache.

**F2: Die Gebühr wird angezeigt, aber das Label oder der Betrag ist falsch.**
A2:

- **Richtlinieneinstellungen:** Gehen Sie zur spezifischen Richtlinie unter „Conditional Order Fees > Policies“ und überprüfen Sie die Einstellungen „Gebührenwert“ und „Gebührenlabel“. Stellen Sie sicher, dass das Label für die Sprache, die Sie testen, korrekt übersetzt ist.
- **Mehrere Richtlinien:** Wenn potenziell mehrere Richtlinien zutreffen könnten, überprüfen Sie deren „Priorität“ und die Einstellung „Weitere Regeln nicht verarbeiten“. Eine Richtlinie mit höherer Priorität könnte anstelle der von Ihnen erwarteten angewendet werden.

**F3: Kann ich das Gebührenlabel für verschiedene Sprachen übersetzen?**
A3: Ja! Beim Bearbeiten einer Richtlinie verfügt das Feld „Gebührenlabel“ typischerweise über eine Sprachauswahl (ein Flaggensymbol). Klicken Sie darauf, um Übersetzungen für jede in Ihrem Shop installierte Sprache einzugeben.

**F4: Was passiert, wenn ich das „Gebühren-Produkt“ lösche, das das Modul verwendet?**
A4: Wenn Sie das in der Einstellung „Gebühren-Produkt-ID“ angegebene Produkt löschen, kann das Modul keine Gebühren mehr zum Warenkorb hinzufügen. Es ist entscheidend, dieses Produkt nicht zu löschen. Wenn es versehentlich gelöscht wird, müssen Sie das Modul möglicherweise neu installieren (wodurch es neu erstellt wird) oder manuell ein neues verstecktes Produkt erstellen und die Einstellung „Gebühren-Produkt-ID“ aktualisieren.

**F5: Das Modul scheint meinen Checkout-Prozess zu verlangsamen.**
A5: Obwohl das Modul auf Leistung optimiert ist, können komplexe Richtlinien mit vielen Bedingungen, insbesondere solche, die umfangreiche Produktprüfungen beinhalten, einen geringen Overhead verursachen.

- **Bedingungen vereinfachen:** Überprüfen Sie Ihre Richtlinien. Können Bedingungen vereinfacht oder kombiniert werden?
- **Priorisieren:** Verwenden Sie die Einstellungen „Priorität“ und „Weitere Regeln nicht verarbeiten“ effektiv, um die Anzahl der Richtlinien zu minimieren, die für einen bestimmten Warenkorb vollständig bewertet werden müssen.
- **Serverressourcen:** Stellen Sie sicher, dass Ihre Hosting-Umgebung die empfohlenen Spezifikationen von PrestaShop erfüllt.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Conditional Order Fees“ ist nach dem MVC-Muster von PrestaShop aufgebaut und nutzt `ObjectModel` für die Datenpersistenz sowie eine robuste ereignisgesteuerte Architektur über PrestaShop-Hooks. Es führt eine ausgeklügelte Bedingungsbewertungs-Engine ein, die komplexe, verschachtelte `AND`/`OR`-Logik zur Bestimmung der Gebührenanwendbarkeit ermöglicht. Das Modul integriert sich nahtlos in den Warenkorb- und Bestellabwicklungsprozess, indem es dynamisch ein „virtuelles Produkt“ zum Warenkorb hinzufügt, wenn die Bedingungen erfüllt sind. Die Admin-Oberflächen werden mit PrestaShops `AdminController` und `HelperList`/`HelperForm`-Komponenten erstellt, mit benutzerdefiniertem JavaScript für den Bedingungs-Builder und Simulator.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `conorderfee/controllers/front/index.php`
  - **Klassenname:** `ConorderfeeIndexModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller dient wahrscheinlich als Fallback oder einfacher Einstiegspunkt, aber die Kernlogik für die Anwendung von Gebühren wird hauptsächlich über Hooks und nicht über direkte Front-Controller-Routen gehandhabt. Er könnte für grundlegende Modulinformationen oder Weiterleitungen verwendet werden, wenn direkt darauf zugegriffen wird.

#### Back-Office-Admin-Controller

- `conorderfee/controllers/admin/AdminconorderfeeAuditLog.php`
  - **Klassenname:** `AdminconorderfeeAuditLogController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Conditional Order Fees > Audit-Log
  - **Verwaltete Entität:** `ConorderfeeLog` (ORM für die Tabelle `ps_conorderfee_log`).
  - **Verantwortlichkeit:** Verwaltet die Anzeige und Filterung des Gebühren-Audit-Logs. Es verwendet `HelperList`, um die Tabelle der Log-Einträge zu rendern, und bietet detaillierte Ansichten für einzelne Log-Einträge, die den Bedingungsbewertungsprozess zeigen.
- `conorderfee/controllers/admin/AdminconorderfeePolicies.php`
  - **Klassenname:** `AdminconorderfeePoliciesController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Conditional Order Fees > Richtlinien
  - **Verwaltete Entität:** `ConorderfeePolicy` (ORM für die Tabelle `ps_conorderfee_policy`).
  - **Verantwortlichkeit:** Verwaltet die Erstellung, Bearbeitung, Duplizierung und Löschung von Gebührenrichtlinien. Es verwendet `HelperList` für die Richtlinienübersicht und `HelperForm` für das Formular zur Richtlinienerstellung/-bearbeitung, das die komplexe Bedingungs-Builder-Oberfläche enthält.
- `conorderfee/controllers/admin/index.php`
  - **Klassenname:** `ConorderfeeIndexModuleAdminController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Conditional Order Fees > Dashboard
  - **Verwaltete Entität:** N/A (Dashboard-Ansicht)
  - **Verantwortlichkeit:** Dient als Haupt-Dashboard für das Modul im Back Office und zeigt Statistiken und Schnelllinks an. Es ist der Standard-Controller, der geladen wird, wenn auf den Hauptmenüpunkt des Moduls geklickt wird.

### 4.3 Kernklassen & Modelle (`classes/`)

- `conorderfee/classes/ConorderfeeAdmin.php`
  - **Verantwortlichkeit:** Dienstprogrammklasse für admin-spezifische Funktionalitäten, die potenziell die Menüregistrierung, Tab-Verwaltung und allgemeine admin-bezogene Hilfsfunktionen handhabt.
- `conorderfee/classes/ConorderfeeAuditLog.php`
  - **Datenbanktabelle:** `ps_conorderfee_log`
  - **Erweitert ObjectModel:** Ja.
  - **`$definition`-Felder:** `id_conorderfee_log`, `id_cart`, `id_order`, `id_customer`, `id_conorderfee_policy`, `fee_amount`, `fee_label`, `conditions_snapshot`, `evaluation_result`, `date_add`.
  - **Wichtige öffentliche Methoden:** Methoden zum Speichern von Log-Einträgen, Abrufen von Log-Daten und potenziell Formatieren von Log-Details zur Anzeige.
- `conorderfee/classes/ConorderfeeCartState.php`
  - **Verantwortlichkeit:** Eine Hilfsklasse zur Kapselung des aktuellen Zustands des Warenkorbs und des zugehörigen Kontexts (Kunde, Adresse, Versanddienstleister usw.) für die Bedingungsbewertung. Sie bietet Methoden zum Abrufen verschiedener Warenkorb-Eigenschaften, die von Bedingungen benötigt werden.
- `conorderfee/classes/ConorderfeeCompatibility.php`
  - **Verantwortlichkeit:** Handhabt Kompatibilitätsschichten für verschiedene PrestaShop-Versionen (z. B. 1.7 vs. 8.x vs. 9.x), um sicherzustellen, dass das Modul in allen unterstützten Versionen korrekt funktioniert.
- `conorderfee/classes/ConorderfeeCondition.php`
  - **Datenbanktabelle:** `ps_conorderfee_condition`
  - **Erweitert ObjectModel:** Ja.
  - **`$definition`-Felder:** `id_conorderfee_condition`, `id_conorderfee_condition_group`, `type`, `operator`, `value`, `is_inverted`.
  - **Wichtige öffentliche Methoden:** Repräsentiert eine einzelne Bedingung innerhalb einer Richtlinie (z. B. „Warenkorb-Gesamt > 100“). Methoden zum Speichern, Laden und potenziell Validieren von Bedingungsdaten.
- `conorderfee/classes/ConorderfeeConditionEvaluator.php`
  - **Verantwortlichkeit:** Die Kernlogik-Engine zur Bewertung eines `ConorderfeeConditionTree` gegen einen `ConorderfeeCartState`. Sie verarbeitet rekursiv Bedingungsgruppen und einzelne Bedingungen, um festzustellen, ob eine Richtlinie zutrifft.
- `conorderfee/classes/ConorderfeeConditionGroup.php`
  - **Datenbanktabelle:** `ps_conorderfee_condition_group`
  - **Erweitert ObjectModel:** Ja.
  - **`$definition`-Felder:** `id_conorderfee_condition_group`, `id_conorderfee_policy`, `id_parent_group`, `operator` (`AND`/`OR`).
  - **Wichtige öffentliche Methoden:** Repräsentiert eine Gruppe von Bedingungen (z. B. „Bedingung A UND (Bedingung B ODER Bedingung C)“). Verwaltet ihre Kindbedingungen und Untergruppen.
- `conorderfee/classes/ConorderfeeConditionTree.php`
  - **Verantwortlichkeit:** Repräsentiert die hierarchische Struktur der Bedingungen für eine Richtlinie (Stammgruppe, Untergruppen, einzelne Bedingungen). Wird vom `ConorderfeeConditionEvaluator` verwendet.
- `conorderfee/classes/ConorderfeeContext.php`
  - **Verantwortlichkeit:** Ein Wrapper um das `Context`-Objekt von PrestaShop, der potenziell modulspezifische Kontextdaten hinzufügt oder den Zugriff auf gemeinsame Kontextelemente vereinfacht.
- `conorderfee/classes/ConorderfeeDashboard.php`
  - **Verantwortlichkeit:** Stellt Daten und Logik für die Dashboard-Ansicht des Moduls bereit, ruft Statistiken und aktuelle Log-Einträge ab.
- `conorderfee/classes/ConorderfeeEngine.php`
  - **Verantwortlichkeit:** Der zentrale Orchestrator für die Front-Office-Logik des Moduls. Er bindet sich in verschiedene PrestaShop-Ereignisse ein, ruft aktive Richtlinien ab, verwendet den `ConorderfeeConditionEvaluator`, um Bedingungen zu prüfen, und fügt das Gebührenprodukt gegebenenfalls zum Warenkorb hinzu.
- `conorderfee/classes/ConorderfeeFeeProduct.php`
  - **Verantwortlichkeit:** Verwaltet das spezielle „Gebührenprodukt“, das die bedingte Gebühr im Warenkorb darstellt. Es kümmert sich um dessen Erstellung während der Installation und stellt sicher, dass es korrekt als virtuelles, nicht sichtbares Produkt konfiguriert ist.
- `conorderfee/classes/ConorderfeeListRenderer.php`
  - **Verantwortlichkeit:** Eine Hilfsklasse zum Rendern von Listen im Back Office, die potenziell `HelperList` erweitert oder benutzerdefinierte Spalten-Rendering-Logik bereitstellt.
- `conorderfee/classes/ConorderfeeLog.php`
  - **Datenbanktabelle:** `ps_conorderfee_log` (gleich wie `ConorderfeeAuditLog`, wahrscheinlich ein Alias oder eine Basisklasse)
  - **Erweitert ObjectModel:** Ja.
  - **`$definition`-Felder:** Gleich wie `ConorderfeeAuditLog`.
  - **Wichtige öffentliche Methoden:** Methoden zum Protokollieren von Ereignissen, Speichern von Bewertungsergebnissen und Abrufen von Protokolldaten.
- `conorderfee/classes/ConorderfeePolicy.php`
  - **Datenbanktabelle:** `ps_conorderfee_policy`
  - **Erweitert ObjectModel:** Ja.
  - **`$definition`-Felder:** `id_conorderfee_policy`, `name`, `active`, `priority`, `fee_type`, `fee_value`, `fee_label`, `stop_further_rules`, `date_add`, `date_upd`.
  - **Wichtige öffentliche Methoden:** Repräsentiert eine vollständige Gebührenrichtlinie. Methoden zum Speichern, Laden und Verwalten der zugehörigen `ConorderfeeConditionGroup`s.
- `conorderfee/classes/ConorderfeePolicyDuplicator.php`
  - **Verantwortlichkeit:** Handhabt die Logik zum Duplizieren einer bestehenden Gebührenrichtlinie, einschließlich aller zugehörigen Bedingungen und Gruppen, um die Richtlinienerstellung zu optimieren.
- `conorderfee/classes/ConorderfeePreset.php`
  - **Verantwortlichkeit:** Verwaltet vordefinierte Bedingungstypen und Operatoren für den Bedingungs-Builder (z. B. „Warenkorb-Gesamt“, „Kundengruppe“, „ist größer als“, „ist eines von“).
- `conorderfee/classes/ConorderfeeRule.php`
  - **Verantwortlichkeit:** Wahrscheinlich eine abstrakte oder Basisklasse zum Definieren von Regeln oder ein spezifischer Regeltyp innerhalb des Bedingungs-Builders.
- `conorderfee/classes/ConorderfeeTreeRepository.php`
  - **Verantwortlichkeit:** Verwaltet die Persistenz und den Abruf der Bedingungsbaumstruktur (Richtlinien, Gruppen, Bedingungen) aus der Datenbank.
- `conorderfee/classes/index.php`
  - **Verantwortlichkeit:** Leere Datei, typischerweise verwendet, um das Auflisten von Verzeichnissen zu verhindern.

### 4.4 JavaScript-Assets (`views/js/`)

- `conorderfee/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Bietet Autocomplete-Funktionalität für Suchfelder, wahrscheinlich verwendet zur Auswahl von Produkten, Kategorien, Kunden usw. innerhalb des Bedingungs-Builders.
- `conorderfee/lib/searchTool/views/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Duplikat des oben Genannten, wahrscheinlich ein Pfadfehler oder eine veraltete Datei.
- `conorderfee/views/js/adminConditionBuilder.js`
  - **Geltungsbereich:** Back-Office (`AdminconorderfeePoliciesController`).
  - **Beschreibung:** Das Kern-JavaScript für die interaktive Bedingungs-Builder-Oberfläche. Es handhabt das Hinzufügen/Entfernen von Bedingungen und Gruppen, die Verwaltung der `AND`/`OR`-Logik, das dynamische Laden von Bedingungstypen und Operatoren sowie die Aktualisierung der Benutzeroberfläche basierend auf Benutzereingaben.
- `conorderfee/views/js/adminConorderfeeDashboard.js`
  - **Geltungsbereich:** Back-Office (`AdminconorderfeeDashboardController`).
  - **Beschreibung:** JavaScript für das Dashboard, das potenziell AJAX-Updates für Statistiken, Diagramm-Rendering oder interaktive Elemente auf dem Dashboard handhabt.
- `conorderfee/views/js/adminConorderfeeSearchTool.js`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Integriert das Autocomplete-Suchwerkzeug (aus `lib/searchTool`) in verschiedene Admin-Formulare, insbesondere zur Auswahl von Entitäten in Bedingungen.
- `conorderfee/views/js/adminConorderfeeSimulator.js`
  - **Geltungsbereich:** Back-Office (wahrscheinlich auf der Richtlinienbearbeitungsseite oder im Audit-Log).
  - **Beschreibung:** Bietet ein Echtzeit- oder simuliertes Bedingungsbewertungswerkzeug im Back Office, das Administratoren ermöglicht, Richtlinien gegen hypothetische Warenkorbszenarien zu testen, ohne eine echte Bestellung aufzugeben.
- `conorderfee/views/js/adminPolicyRules.js`
  - **Geltungsbereich:** Back-Office (`AdminconorderfeePoliciesController`).
  - **Beschreibung:** Handhabt allgemeine JavaScript-Interaktionen auf der Richtlinienliste und den Bearbeitungsseiten, wie das Aktivieren/Deaktivieren von Richtlinien, das Verwalten von Duplikationen und das Verwalten des gesamten Richtlinienformulars.
- `conorderfee/views/js/checkout.js`
  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Dieses Skript überwacht wahrscheinlich Änderungen im Warenkorb während des Checkout-Prozesses (z. B. Mengenaktualisierungen, Versanddienstleisterauswahl) und löst AJAX-Aufrufe zur Neubewertung von Gebühren aus, um sicherzustellen, dass der Warenkorb-Gesamtbetrag immer korrekt ist. Es könnte auch die Anzeige der Gebührenposition aktualisieren.

### 4.5 CSS-Stylesheets (`views/css/`)

- `conorderfee/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office (Admin).
  - **Beschreibung:** Stile für die Autocomplete-Suchfelder und deren Dropdown-Vorschläge.
- `conorderfee/lib/searchTool/views/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office (Admin).
  - **Beschreibung:** Duplikat des oben Genannten, wahrscheinlich ein Pfadfehler oder eine veraltete Datei.
- `conorderfee/views/css/admin_conorderfee.css`
  - **Geltungsbereich:** Back-Office (Admin).
  - **Beschreibung:** Allgemeine Stile für die Back-Office-Oberflächen des Moduls, einschließlich Dashboard, Richtlinienliste, Audit-Log und insbesondere des komplexen Bedingungs-Builders, um ein konsistentes und benutzerfreundliches Layout zu gewährleisten.
- `conorderfee/views/css/front.css`
  - **Geltungsbereich:** Front-Office (Kunde).
  - **Beschreibung:** Minimale Stile dafür, wie die Gebührenposition in der Warenkorbzusammenfassung und auf den Checkout-Seiten erscheint, um eine visuelle Integration mit dem Shop-Theme zu gewährleisten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `conorderfee/views/templates/hook/admin_order.tpl`
  - **Hook:** `displayAdminOrder`
  - **Ausgabe:** Zeigt Informationen über angewendete bedingte Gebühren in der PrestaShop Back Office Bestellansicht an, sodass Administratoren sehen können, welche Richtlinien auf eine bestimmte Bestellung angewendet wurden.

#### Admin-Templates (`views/templates/admin/`)

- `conorderfee/lib/searchTool/views/scripts.tpl`
  - **Ausgabe:** Enthält die notwendigen JavaScript- und CSS-Dateien für das Suchwerkzeug im Back Office.
- `conorderfee/lib/searchTool/views/views/scripts.tpl`
  - **Ausgabe:** Duplikat des oben Genannten, wahrscheinlich ein Pfadfehler oder eine veraltete Datei.
- `conorderfee/views/templates/admin/auditPreview.tpl`
  - **Ausgabe:** Rendert die detaillierte Ansicht eines einzelnen Audit-Log-Eintrags, der den vollständigen Bedingungsbewertungsprozess zeigt.
- `conorderfee/views/templates/admin/dashboard.tpl`
  - **Ausgabe:** Die Haupt-Dashboard-Ansicht für das Modul, die Statistiken und Schnelllinks anzeigt.
- `conorderfee/views/templates/admin/helpers/list/list_action_duplicate.tpl`
  - **Ausgabe:** Benutzerdefiniertes Template für die Schaltfläche „Duplizieren“ in `HelperList`-Ansichten, speziell für Richtlinien.
- `conorderfee/views/templates/admin/policiesPreview.tpl`
  - **Ausgabe:** Rendert eine Vorschau oder Zusammenfassung einer Richtlinie, potenziell verwendet im Audit-Log oder einem Simulator.
- `conorderfee/views/templates/admin/policyConditionBuilder.tpl`
  - **Ausgabe:** Die komplexe HTML-Struktur für die interaktive Bedingungs-Builder-Oberfläche, die beim Erstellen oder Bearbeiten einer Richtlinie verwendet wird.
- `conorderfee/views/templates/admin/policyRuleCard.tpl`
  - **Ausgabe:** Rendert eine einzelne Regel oder Bedingung innerhalb des Bedingungs-Builders, typischerweise eine visuelle Karte oder einen Block.
- `conorderfee/views/templates/admin/policyRulesTable.tpl`
  - **Ausgabe:** Rendert die Tabelle der Richtlinien in der Listenansicht `AdminconorderfeePolicies`.
- `conorderfee/views/templates/admin/scopeSelector.tpl`
  - **Ausgabe:** Ein Template zur Auswahl des Geltungsbereichs einer Bedingung (z. B. „Warenkorb“, „Produkt“, „Kunde“), verwendet innerhalb des Bedingungs-Builders.

#### Front-Office-Templates (`views/templates/front/`)

- `conorderfee/controllers/front/index.php` (Keine spezifische .tpl-Datei aufgeführt, wahrscheinlich direkte Ausgabe oder Weiterleitung)

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- `ps_conorderfee_policy`: Speichert die Hauptdefinitionen der Gebührenrichtlinien (Name, aktiver Status, Gebührentyp, Wert, Label, Priorität).
- `ps_conorderfee_condition_group`: Speichert die hierarchische Struktur der Bedingungsgruppen (UND/ODER-Logik) innerhalb jeder Richtlinie.
- `ps_conorderfee_condition`: Speichert einzelne Bedingungen (Typ, Operator, Wert), die mit Bedingungsgruppen verknüpft sind.
- `ps_conorderfee_log`: Speichert einen Audit-Trail jedes Mal, wenn eine Gebühr bewertet wurde, einschließlich Warenkorbdetails, angewendeter Richtlinie, Gebührenbetrag und einer Momentaufnahme des Bewertungsergebnisses.
- `ps_configuration`: Speichert modulspezifische Konfigurationswerte wie `CONORDERFEE_ENABLED` und `CONORDERFEE_FEE_PRODUCT_ID`.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Nicht explizit in den Modulinformationen aufgeführt, wird aber oft zum Laden von Front-Office-CSS/JS verwendet. |
| `displayBeforeCarrier` | Vor der Auswahl des Versanddienstleisters auf der Checkout-Seite. | Potenziell verwendet, um Gebühren neu zu bewerten, wenn die Auswahl des Versanddienstleisters Bedingungen beeinflusst. |
| `actionObjectProductInCartDeleteBefore` | Bevor ein Produkt aus dem Warenkorb entfernt wird. | Gebühren neu bewerten, um sie anzupassen, wenn das entfernte Produkt Teil einer Bedingung war. |
| `actionPresentCart` | Wenn die Warenkorbdaten dem Front Office präsentiert werden. | **KRITISCH:** Haupt-Hook zum Einfügen der Gebührenposition in die Warenkorbzusammenfassung. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird, vor seinem Inhalt. | Lädt Back-Office-CSS und JavaScript für die Admin-Oberflächen des Moduls. |
| `actionPresentProductListing` | Wenn Produktlisten präsentiert werden. | Nicht direkt gebührenrelevant, könnte aber für produktspezifische Gebührenindikatoren verwendet werden. |
| `actionValidateOrderBefore` | Kurz bevor eine Bestellung validiert wird. | Letzte Prüfung und Anwendung von Gebühren, um sicherzustellen, dass der Gesamtbetrag der Bestellung korrekt ist. |
| `actionGetProductPropertiesAfter` | Nachdem Produkteigenschaften abgerufen wurden. | Potenziell verwendet, um spezifische Produkte zu identifizieren, die Gebühren auslösen. |
| `displayAdminOrder` | Auf der Back-Office-Bestelldetailseite. | Zeigt Informationen über angewendete Gebühren für eine spezifische Bestellung an. |
| `actionFrontControllerInitAfter` | Nachdem ein Front-Controller initialisiert wurde. | Allgemeine Front-Office-Initialisierung, potenziell Einrichtung des Kontexts für die Gebührenbewertung. |
| `actionPresentProduct` | Wenn ein einzelnes Produkt präsentiert wird. | Ähnlich wie `actionPresentProductListing`. |
| `actionPresentCartProduct` | Wenn ein Produkt im Warenkorb präsentiert wird. | Ermöglicht die Änderung von Warenkorb-Produktdaten, potenziell für gebührenbezogene Anzeige. |
| `actionProductPriceCalculation` | Während der Produktpreisberechnung. | Stellt sicher, dass der Preis des Gebührenprodukts korrekt durch die berechnete Gebühr überschrieben wird. |
| `actionFrontControllerSetVariables` | Bevor Smarty-Variablen in einem Front-Controller zugewiesen werden. | Übergibt gebührenbezogene Daten an Front-Office-Templates. |
| `actionCartSave` | Nachdem ein Warenkorb gespeichert wurde (z. B. Mengenänderung, Produkt hinzufügen/entfernen). | **KRITISCH:** Löst die Hauptlogik zur Gebührenbewertung aus, wann immer sich der Warenkorbinhalt ändert. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Protokolliert die endgültige Gebührenanwendung und verknüpft sie mit der neuen Bestell-ID. |

## 5. Offizieller Support & Updates

Für offizielle Updates, Fehlerbehebungen und dedizierten Entwickler-Support wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Stellen Sie sicher, dass Sie immer die neueste Version herunterladen, die mit Ihrer PrestaShop-Installation kompatibel ist.

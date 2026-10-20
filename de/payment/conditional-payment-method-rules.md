---
title: "Bedingte Zahlungsregel-Regeln - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Bedingte Zahlungsregel-Regeln“ von MyPresta.eu."
sidebar:
  label: "Bedingte Zahlungsregel-Regeln - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Conditional Payment Method Rules auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/conditional-payment-method-rules.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/conditional-payment-method-rules/)
>
> ---


# Bedingte Zahlungsregel-Regeln

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Die Konfiguration des Moduls wird hauptsächlich über dedizierte Administrationsbildschirme verwaltet, die es Ihnen ermöglichen, Ihre Zahlungsrichtlinien zu erstellen und zu verwalten.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupteinstiegspunkt für das Modul. Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zu einem Dashboard oder einer allgemeinen Einstellungsseite.

#### Allgemeine Einstellungen & Dashboard

Dieser Bildschirm bietet einen Überblick über den Status Ihres Moduls und schnellen Zugriff auf wichtige Funktionen.

- **Was dieser Bildschirm tut:** Zeigt eine Zusammenfassung Ihrer aktiven Richtlinien, der letzten Audit-Log-Einträge und schnelle Links zur Verwaltung von Richtlinien oder zur Anzeige des Audit-Logs. Es ist Ihre zentrale Anlaufstelle zur Überwachung der Modulaktivität.
- **Auswirkung von Einstellungsänderungen:** Dieser Bildschirm dient hauptsächlich der Information und Navigation. Alle Änderungen, die Sie hier vornehmen (z. B. das Aktivieren/Deaktivieren einer Richtlinie), wirken sich direkt darauf aus, wie Zahlungsmethoden an der Kasse angezeigt werden.
- **Empfohlener Wert:** Behalten Sie das Dashboard im Auge, um Richtlinienkonflikte oder unerwartetes Verhalten zu erkennen.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul führt mehrere neue Menüpunkte unter dem Abschnitt „Zahlung“ in Ihrem PrestaShop Back Office ein.

#### 2.2.1 Zahlungsrichtlinien (Back Office > Zahlung > Zahlungsregel-Regeln > Richtlinien)

Hier definieren und verwalten Sie alle Ihre Regeln zum Anzeigen oder Ausblenden von Zahlungsmethoden.

- **Bildschirmname & Menüpfad:** **Zahlung > Zahlungsregel-Regeln > Richtlinien**
- **Verfügbare Aktionen & Einstellungen:**

  - **Richtlinienliste:** Eine Tabelle, die alle von Ihnen erstellten Richtlinien, deren Status (aktiv/inaktiv) und die betroffenen Zahlungsmethoden anzeigt.
  - **Neue Richtlinie hinzufügen:** Klicken Sie auf diese Schaltfläche, um eine neue Regel zu erstellen.
  - **Richtlinie bearbeiten/löschen:** Verwalten Sie einzelne Richtlinien aus der Liste.
  - **Richtlinie duplizieren:** Erstellen Sie schnell eine Kopie einer bestehenden Richtlinie, um sie zu ändern.
  - **Richtlinie aktivieren/deaktivieren:** Schalten Sie den aktiven Status einer Richtlinie um, ohne sie zu löschen.
  - **Richtlinien importieren/exportieren (JSON):** Sichern Sie Ihre Richtlinien oder übertragen Sie sie zwischen Shops.
- **Erstellen/Bearbeiten einer Richtlinie:**
  Wenn Sie eine Richtlinie hinzufügen oder bearbeiten, konfigurieren Sie mehrere wichtige Aspekte:

  1. **Richtlinienname:**

     - **Was diese Einstellung tut:** Ein beschreibender Name für Ihre Richtlinie (z. B. „Nachnahme für internationale Bestellungen ausblenden“).
     - **Auswirkung von Einstellungsänderungen:** Hilft Ihnen, die Richtlinie in der Liste zu identifizieren.
     - **Empfohlener Wert:** Machen Sie ihn klar und prägnant.
     - **Händlerszenario:** Die Benennung einer Richtlinie „Kostenloser Versand nur mit PayPal“ sagt Ihnen sofort ihren Zweck.
  2. **Status (Aktiviert/Deaktiviert):**

     - **Was diese Einstellung tut:** Steuert, ob die Richtlinie aktiv ist und an der Kasse angewendet wird.
     - **Auswirkung von Einstellungsänderungen:**
       - *Wenn aktiviert:* Die Regeln innerhalb dieser Richtlinie werden ausgewertet und beeinflussen die Sichtbarkeit der Zahlungsmethode.
       - *Wenn deaktiviert:* Die Richtlinie wird ignoriert, und ihre Regeln haben keine Auswirkung.
     - **Empfohlener Wert:** Aktivieren Sie Richtlinien nur, wenn Sie sicher sind, dass sie korrekt konfiguriert sind.
     - **Händlerszenario:** Sie könnten eine Richtlinie während einer Aktion oder bei der Fehlerbehebung vorübergehend deaktivieren.
  3. **Betroffene Zahlungsmethoden:**

     - **Was diese Einstellung tut:** Wählen Sie aus, welche spezifischen Zahlungsmethoden diese Richtlinie steuern soll.
     - **Auswirkung von Einstellungsänderungen:** Nur die ausgewählten Zahlungsmethoden unterliegen den Regeln dieser Richtlinie.
     - **Empfohlener Wert:** Wählen Sie alle für diese Richtlinie relevanten Zahlungsmethoden aus.
     - **Händlerszenario:** Wenn Sie „Nachnahme“ und „Banküberweisung“ unter bestimmten Bedingungen ausblenden möchten, würden Sie hier beide auswählen.
  4. **Richtlinientyp (Anzeigen/Ausblenden):**

     - **Was diese Einstellung tut:** Bestimmt, ob die Bedingungen der Richtlinie die ausgewählten Zahlungsmethoden *anzeigen* oder *ausblenden* sollen.
     - **Auswirkung von Einstellungsänderungen:**
       - *Wenn auf „Anzeigen“ gesetzt:* Die ausgewählten Zahlungsmethoden sind *nur* sichtbar, wenn ALLE Bedingungen in dieser Richtlinie erfüllt sind. Wenn die Bedingungen nicht erfüllt sind, werden sie ausgeblendet.
       - *Wenn auf „Ausblenden“ gesetzt:* Die ausgewählten Zahlungsmethoden werden ausgeblendet, wenn ALLE Bedingungen in dieser Richtlinie erfüllt sind. Wenn die Bedingungen nicht erfüllt sind, sind sie sichtbar.
     - **Empfohlener Wert:** Wählen Sie basierend auf Ihrem Hauptziel. „Ausblenden“ ist oft einfacher für spezifische Einschränkungen, während „Anzeigen“ gut für exklusive Angebote ist.
     - **Händlerszenario:**
       - *Ausblenden:* „Nachnahme ausblenden, wenn der Warenkorbwert über 500 $ liegt.“
       - *Anzeigen:* „Ratenzahlung NUR anzeigen, wenn die Kundengruppe ‚VIP‘ ist UND der Warenkorbwert über 1000 $ liegt.“
  5. **Bedingungs-Builder:**

     - **Was diese Einstellung tut:** Dies ist der Kern Ihrer Richtlinie. Sie erstellen komplexe Regeln mit „UND“- und „ODER“-Logik basierend auf verschiedenen Kriterien.
     - **Auswirkung von Einstellungsänderungen:** Die hier definierten Bedingungen bestimmen, *wann* die „Anzeigen“- oder „Ausblenden“-Aktion der Richtlinie ausgelöst wird.
     - **Verfügbare Bedingungen (Beispiele):**
       - **Warenkorbwert:** Basierend auf dem Gesamtwert des Warenkorbs des Kunden.
       - **Kundengruppe:** Basierend auf der Gruppe, zu der der Kunde gehört (z. B. Gast, Kunde, VIP, Großhändler).
       - **Land:** Basierend auf dem Versand- oder Rechnungsland des Kunden.
       - **Versanddienstleister:** Basierend auf dem ausgewählten Versanddienstleister.
       - **Produkte im Warenkorb:** Basierend auf bestimmten Produkten, Kategorien, Herstellern oder Lieferanten im Warenkorb.
       - **Währung:** Basierend auf der für die Bestellung verwendeten Währung.
       - **Gewicht:** Basierend auf dem Gesamtgewicht des Warenkorbs.
       - **Datum/Uhrzeit:** Basierend auf bestimmten Daten oder Uhrzeiten (z. B. für Aktionen).
       - **Shop:** Für Multi-Store-Setups.
     - **Empfohlener Wert:** Beginnen Sie mit einfachen Bedingungen und testen Sie gründlich. Verwenden Sie „UND“ für strengere Anforderungen und „ODER“ für eine breitere Anwendbarkeit.
     - **Händlerszenario:**
       - „PayPal ausblenden, wenn (Land IST ‚USA‘ UND Warenkorbwert IST WENIGER ALS 10 $) ODER (Kundengruppe IST ‚Großhändler‘).“
       - „Banküberweisung anzeigen, wenn (Kundengruppe IST ‚B2B‘) UND (Warenkorbwert IST GRÖSSER ALS 1000 $).“
  6. **Nachricht bei Nichtverfügbarkeit:**

     - **Was diese Einstellung tut:** Eine benutzerdefinierte Nachricht, die dem Kunden angezeigt wird, wenn eine Zahlungsmethode durch diese Richtlinie ausgeblendet wird.
     - **Auswirkung von Einstellungsänderungen:** Bietet dem Kunden klare Kommunikation darüber, warum eine Zahlungsoption nicht verfügbar ist, und verhindert Verwirrung.
     - **Empfohlener Wert:** Halten Sie sie höflich und informativ (z. B. „Nachnahme ist für Bestellungen über 500 $ nicht verfügbar. Bitte wählen Sie eine andere Zahlungsmethode.“).
     - **Händlerszenario:** „Diese Zahlungsmethode ist nur für VIP-Kunden verfügbar.“ oder „Bitte wählen Sie eine andere Versandmethode, um diese Zahlungsoption zu nutzen.“
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

  1. **Bedarf identifizieren:** „Ich möchte die Nachnahme für Bestellungen über 200 $ nicht mehr anbieten.“
  2. **Neue Richtlinie erstellen:** Benennen Sie sie „Nachnahme-Limit 200 $“.
  3. **Wählen Sie „Ausblenden“** als Richtlinientyp.
  4. **Wählen Sie „Nachnahme“** als betroffene Zahlungsmethode.
  5. **Fügen Sie eine Bedingung hinzu:** „Warenkorbwert IST GRÖSSER ALS 200 $“.
  6. **Fügen Sie eine Nachricht bei Nichtverfügbarkeit hinzu:** „Nachnahme ist für Bestellungen über 200 $ nicht verfügbar. Bitte wählen Sie eine andere Zahlungsmethode.“
  7. **Aktivieren und Speichern.**
  8. **Testen Sie mit dem Simulator** (siehe nächster Abschnitt).

#### 2.2.2 Audit-Log (Back Office > Zahlung > Zahlungsregel-Regeln > Audit-Log)

Dieser Bildschirm bietet eine detaillierte Historie, wie Ihre Zahlungsregeln angewendet wurden.

- **Bildschirmname & Menüpfad:** **Zahlung > Zahlungsregel-Regeln > Audit-Log**
- **Verfügbare Aktionen & Einstellungen:**
  - **Protokollliste:** Eine Tabelle, die jede Instanz anzeigt, bei der die Sichtbarkeit einer Zahlungsmethode durch eine Richtlinie beeinflusst wurde.
  - **Details:** Zeigen Sie spezifische Informationen zu jedem Protokolleintrag an, einschließlich des Kunden, der Warenkorbdetails, der ausgewerteten Richtlinien und des Endergebnisses (welche Zahlungsmethoden angezeigt/ausgeblendet wurden).
  - **Filterung:** Filtern Sie Protokolleinträge nach Datum, Kunde, Richtlinie oder Zahlungsmethode, um bestimmte Ereignisse schnell zu finden.
- **Auswirkung von Änderungen:** Dieser Bildschirm dient der Anzeige und Prüfung. Sie können hier keine Änderungen vornehmen, aber er ist von unschätzbarem Wert, um zu verstehen, warum bestimmte Zahlungsmethoden einem Kunden angezeigt oder nicht angezeigt wurden.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie regelmäßig das Audit-Log, wenn Sie Kundenanfragen zu fehlenden Zahlungsmethoden erhalten oder wenn Sie vermuten, dass eine Richtlinie nicht wie erwartet funktioniert. Es ist Ihr Debugging-Tool.

#### 2.2.3 Simulator (Back Office > Zahlung > Zahlungsregel-Regeln > Simulator)

Der Simulator ist ein leistungsstarkes Tool, um Ihre Richtlinien zu testen, ohne eine echte Bestellung aufzugeben.

- **Bildschirmname & Menüpfad:** **Zahlung > Zahlungsregel-Regeln > Simulator**
- **Verfügbare Aktionen & Einstellungen:**
  - **Eingabefelder:** Geben Sie verschiedene Kriterien wie Kundengruppe, Land, Versanddienstleister, Warenkorbwert ein und fügen Sie sogar bestimmte Produkte zu einem simulierten Warenkorb hinzu.
  - **Simulieren-Schaltfläche:** Klicken Sie, um zu sehen, welche Zahlungsmethoden basierend auf Ihren eingegebenen Kriterien und aktiven Richtlinien verfügbar wären.
  - **Ergebnisanzeige:** Zeigt eine Liste der verfügbaren und nicht verfügbaren Zahlungsmethoden sowie die Gründe an (welche Richtlinien dazu führten, dass sie ausgeblendet/angezeigt wurden).
- **Auswirkung von Änderungen:** Dieser Bildschirm ermöglicht es Ihnen, mit verschiedenen Szenarien zu experimentieren und sofort die Auswirkungen Ihrer Richtlinien zu sehen. Er beeinflusst Ihren Live-Shop nicht.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie den Simulator *immer* nach dem Erstellen oder Ändern einer Richtlinie. Testen Sie Grenzfälle und gängige Szenarien, um sicherzustellen, dass Ihre Regeln genau wie beabsichtigt funktionieren, bevor sie live gehen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Richtlinien (Hinzufügen/Bearbeiten)** | Richtlinienname | Beschreibender Name | Interne Identifizierung der Regel. |
|  | Status | Aktiviert | Aktiviert/deaktiviert die Richtlinie. |
|  | Betroffene Zahlungsmethoden | Relevante Methoden auswählen | Legt fest, welche Zahlungs-Gateways diese Richtlinie steuert. |
|  | Richtlinientyp | Ausblenden | Bestimmt, ob Bedingungen ausgewählte Methoden *ausblenden* oder *anzeigen*. |
|  | Bedingungs-Builder | Variiert je nach Regel | Definiert die Kriterien (z. B. Warenkorbwert, Kundengruppe) für die Anwendung der Richtlinie. |
|  | Nachricht bei Nichtverfügbarkeit | Klarer, informativer Text | Nachricht, die Kunden angezeigt wird, wenn eine Zahlungsmethode ausgeblendet ist. |
| **Audit-Log** | Protokolleinträge | N/A | Bietet eine historische Aufzeichnung der Richtlinienauswertungen. |
|  | Filter | N/A | Hilft beim Suchen und Analysieren spezifischer Protokollereignisse. |
| **Simulator** | Simulations-Eingaben | N/A | Ermöglicht das Testen von Richtlinien mit verschiedenen Kunden-/Warenkorb-Szenarien. |
|  | Simulationsergebnisse | N/A | Zeigt an, welche Zahlungsmethoden für das simulierte Szenario verfügbar/nicht verfügbar wären. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Eine Zahlungsmethode wird nicht angezeigt, aber ich habe keine Richtlinien eingerichtet, um sie auszublenden. Was ist falsch?**
A: Überprüfen Sie zunächst das **Audit-Log** des Moduls auf Einträge, die sich auf diese Zahlungsmethode und den Kunden beziehen. Das Protokoll zeigt Ihnen, ob eine Richtlinie sie *tatsächlich* ausgeblendet hat. Wenn nicht, liegt das Problem möglicherweise außerhalb dieses Moduls:
\* Ist die Zahlungsmethode selbst unter **Zahlung > Zahlungsmethoden** aktiviert?
\* Gibt es Einschränkungen, die direkt im Zahlungsmodul festgelegt sind (z. B. Länder-, Währungs-, Gruppenbeschränkungen innerhalb der eigenen Konfiguration des Zahlungsmoduls)?
\* Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung**).

**F: Meine Richtlinien scheinen nicht zu funktionieren. Was soll ich tun?**
A:
1. **Richtlinienstatus überprüfen:** Stellen Sie sicher, dass die Richtlinie auf dem Bildschirm **Richtlinien** „Aktiviert“ ist.
2. **Simulator verwenden:** Gehen Sie zu **Zahlung > Zahlungsregel-Regeln > Simulator** und geben Sie die genauen Bedingungen ein, die Sie testen. Sehen Sie, was der Simulator vorhersagt. Dies ist der schnellste Weg, Ihre Bedingungen zu debuggen.
3. **Bedingungen überprüfen:** Überprüfen Sie Ihre „UND“- und „ODER“-Logik. Eine einzige falsche Bedingung kann verhindern, dass die gesamte Richtlinie ausgelöst wird.
4. **Betroffene Zahlungsmethoden überprüfen:** Stellen Sie sicher, dass die Zahlungsmethode, die Sie erwarten, tatsächlich in der Richtlinie ausgewählt ist.
5. **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung**), nachdem Sie wesentliche Änderungen an Moduleinstellungen oder Richtlinien vorgenommen haben.

**F: Wie gehe ich mit mehreren Richtlinien um, die dieselbe Zahlungsmethode betreffen?**
A: Das Modul wertet alle aktiven Richtlinien aus.
\* Wenn mehrere „Ausblenden“-Richtlinien für dieselbe Zahlungsmethode gelten und *eine* davon ausgelöst wird, wird die Zahlungsmethode ausgeblendet.
\* Wenn mehrere „Anzeigen“-Richtlinien für dieselbe Zahlungsmethode gelten und *eine* davon ausgelöst wird, wird die Zahlungsmethode angezeigt.
\* **Konfliktlösung:** Wenn eine Richtlinie „Anzeigen“ und eine andere „Ausblenden“ für dieselbe Zahlungsmethode unter denselben Bedingungen besagt, hat das Modul eine definierte Zusammenführungsstrategie (typischerweise hat „Ausblenden“ Vorrang, um Sicherheit zu gewährleisten und unbeabsichtigte Verfügbarkeit zu verhindern). Verwenden Sie den **Simulator** und das **Audit-Log**, um das genaue Ergebnis widersprüchlicher Richtlinien zu verstehen.

**F: Kann ich die „Nachricht bei Nichtverfügbarkeit“ für verschiedene Sprachen übersetzen?**
A: Ja, beim Bearbeiten einer Richtlinie hat das Feld „Nachricht bei Nichtverfügbarkeit“ typischerweise einen Sprachwähler (ein Flaggensymbol) daneben. Klicken Sie auf die Flagge, um Übersetzungen für jede in Ihrem Shop aktivierte Sprache einzugeben.

**F: Mein benutzerdefiniertes Theme zeigt die Nachrichten bei Nichtverfügbarkeit nicht korrekt an. Was kann ich tun?**
A: Dies deutet normalerweise auf einen CSS-Konflikt oder eine fehlende Template-Überschreibung in Ihrem Theme hin.
\* **`front.css` überprüfen:** Das Modul enthält seine eigene `front.css` für grundlegendes Styling. Ihr Theme könnte diese überschreiben.
\* **Elemente inspizieren:** Verwenden Sie die Entwicklertools Ihres Browsers (F12), um den Bereich zu inspizieren, in dem die Nachricht erscheinen sollte. Suchen Sie nach CSS-Regeln, die sie möglicherweise ausblenden oder falsch positionieren.
\* **Theme-Entwickler kontaktieren:** Wenn Sie mit CSS nicht vertraut sind, wenden Sie sich an Ihren Theme-Entwickler oder einen PrestaShop-Experten, um Unterstützung zu erhalten. Sie können helfen, das Styling des Moduls in Ihr Theme zu integrieren.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Bedingte Zahlungsregel-Regeln“ folgt einem robusten, objektorientierten Designmuster innerhalb des PrestaShop MVC-Frameworks. Es nutzt `ObjectModel` intensiv zur Verwaltung von Richtlinien und Audit-Logs, eine dedizierte `ConditionTree`-Struktur für die komplexe Regelauswertung und eine `PaymethodrulesEngine`, um diese Regeln im Checkout-Schritt anzuwenden. Das Modul injiziert seine Logik hauptsächlich über Hooks, insbesondere `actionPaymentOptionsModifier` (oder ähnliche für ältere PS-Versionen), um die Liste der verfügbaren Zahlungsmethoden zu manipulieren. Admin-Controller bieten eine reichhaltige Benutzeroberfläche für die Richtlinienverwaltung, Simulation und Prüfung.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/index.php`
  - **Klassenname:** `PaymethodrulesIndexModuleFrontController` (oder ähnlich, typischerweise erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller könnte als Fallback oder einfacher Einstiegspunkt dienen, aber die Kernlogik für die Änderung der Zahlungsmethode wird normalerweise über Hooks abgewickelt. Er könnte für spezifische AJAX-Anfragen im Zusammenhang mit der Front-Office-Regelauswertung verwendet werden, falls erforderlich, obwohl die primäre Auswertung während des Renderings der Zahlungsoptionen erfolgt.
- `controllers/front/simulate.php`
  - **Klassenname:** `PaymethodrulesSimulateModuleFrontController` (oder ähnlich, erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Während der Hauptsimulator im BO ist, könnte ein Front-Controller für eine vereinfachte Front-End-Simulation existieren oder um Simulationsergebnisse über AJAX für Debugging-Zwecke bereitzustellen.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminPaymethodrulesAuditLog.php`
  - **Klassenname:** `AdminPaymethodrulesAuditLogController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Zahlungsregel-Regeln -> Audit-Log
  - **Verwaltete Entität:** `PaymethodrulesAuditLog` (zugeordnet zur Tabelle `ps_paymethodrules_log`)
  - **Verantwortlichkeit:** Verwaltet die Anzeige und Filterung der Audit-Log-Einträge. Es verwendet `HelperList`, um die Rasteransicht zu rendern, und bietet Aktionen zum Anzeigen von Log-Details.
- `controllers/admin/AdminPaymethodrulesPolicies.php`
  - **Klassenname:** `AdminPaymethodrulesPoliciesController` (erweitert `ModuleAdminController`)
  - **Tab-Name:** Zahlungsregel-Regeln -> Richtlinien
  - **Verwaltete Entität:** `PaymethodrulesPolicy` (zugeordnet zur Tabelle `ps_paymethodrules_policy`)
  - **Verantwortlichkeit:** Dies ist der zentrale Controller zur Verwaltung von Zahlungsrichtlinien. Er verwaltet:
    - Auflistung von Richtlinien mit `HelperList`.
    - Hinzufügen/Bearbeiten von Richtlinien mit `HelperForm` mit komplexem Feld-Rendering für den Bedingungs-Builder.
    - Aktivieren/Deaktivieren, Duplizieren und Löschen von Richtlinien.
    - Handhabung des JSON-Imports/-Exports von Richtlinien.
- `controllers/admin/index.php`
  - **Klassenname:** `AdminPaymethodrulesDashboardController` (oder ähnlich, erweitert `ModuleAdminController`)
  - **Tab-Name:** Zahlungsregel-Regeln -> Dashboard (oder Hauptmodul-Konfigurationslink)
  - **Verwaltete Entität:** N/A (Dashboard-Ansicht)
  - **Verantwortlichkeit:** Bietet den Haupteinstiegspunkt und die Dashboard-Ansicht für das Modul im Back Office. Es aggregiert Informationen von anderen Controllern (z. B. Richtlinienanzahl, aktuelle Log-Einträge) und bietet Navigation. Es verwendet typischerweise Smarty-Templates zum Rendern der Dashboard-Widgets.

### 4.3 Kernklassen & Modelle (`classes/`)

- `classes/index.php`: Standardleere Datei, um das Auflisten von Verzeichnissen zu verhindern.
- `classes/PaymethodrulesAdmin.php`: Wahrscheinlich eine Hilfsklasse für allgemeine adminbezogene Funktionen, wie Menüregistrierung, Tab-Verwaltung oder gemeinsame Formular-Rendering-Logik.
- `classes/PaymethodrulesAuditLog.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `ps_paymethodrules_log`
  - **`$definition`-Felder:** `id_paymethodrules_log`, `id_cart`, `id_customer`, `id_shop`, `context_data` (JSON), `policies_applied` (JSON), `payment_methods_before` (JSON), `payment_methods_after` (JSON), `date_add`.
  - **Wichtige öffentliche Methoden:** Methoden zum Protokollieren von Ereignissen, Abrufen von Protokolleinträgen und möglicherweise zum Bereinigen alter Protokolle.
- `classes/PaymethodrulesCompatibility.php`: Behandelt Kompatibilitätsebenen für verschiedene PrestaShop-Versionen (z. B. Unterschiede in Hook-Namen, Objektstrukturen oder `Tools`-Funktionen).
- `classes/PaymethodrulesCondition.php`
  - **Erweitert:** `ObjectModel` (oder eine Basisklasse für Bedingungen)
  - **Datenbanktabelle:** `ps_paymethodrules_condition` (wenn Bedingungen einzeln gespeichert werden)
  - **`$definition`-Felder:** `id_paymethodrules_condition`, `id_paymethodrules_policy`, `type`, `operator`, `value`, `id_parent_group`.
  - **Wichtige öffentliche Methoden:** Methoden zum Definieren von Bedingungstypen, Operatoren und Werten. Teil der Bedingungsbaumstruktur.
- `classes/PaymethodrulesConditionEvaluator.php`: Enthält die Kernlogik zur Auswertung einer einzelnen `PaymethodrulesCondition` anhand eines gegebenen Kontexts (Warenkorb, Kunde usw.).
- `classes/PaymethodrulesConditionGroup.php`
  - **Erweitert:** `ObjectModel` (oder eine Basisklasse für Bedingungsgruppen)
  - **Datenbanktabelle:** `ps_paymethodrules_condition_group` (wenn Gruppen einzeln gespeichert werden)
  - **`$definition`-Felder:** `id_paymethodrules_condition_group`, `id_paymethodrules_policy`, `operator` (`AND`/`OR`), `id_parent_group`.
  - **Wichtige öffentliche Methoden:** Verwaltet eine Sammlung von Bedingungen oder verschachtelten Bedingungsgruppen und wendet die `AND`/`OR`-Logik an.
- `classes/PaymethodrulesConditionTree.php`: Repräsentiert die gesamte hierarchische Struktur von Bedingungen und Bedingungsgruppen für eine Richtlinie. Bietet Methoden zum Erstellen, Durchlaufen und Auswerten des Baums.
- `classes/PaymethodrulesContext.php`: Eine Dienstprogrammklasse, die alle relevanten Daten kapselt, die für die Regelauswertung benötigt werden (aktueller Warenkorb, Kunde, Adresse, Versanddienstleister, Währung usw.). Sie fungiert als Datenlieferant für die `PaymethodrulesEngine`.
- `classes/PaymethodrulesDashboard.php`: Hilfsklasse zum Abrufen von Daten und zum Vorbereiten von Statistiken/Zusammenfassungen für die Dashboard-Ansicht des Moduls.
- `classes/PaymethodrulesEngine.php`: Die zentrale Klasse, die für die Orchestrierung der Regelauswertung verantwortlich ist.
  - **Wichtige öffentliche Methoden:** `evaluatePolicies(PaymethodrulesContext $context, array $payment_options)`: Nimmt den aktuellen Kontext und eine Liste der verfügbaren Zahlungsoptionen entgegen, wendet alle aktiven Richtlinien an und gibt die geänderte Liste zurück. Es verwendet `PaymethodrulesConditionTree` und `PaymethodrulesConditionEvaluator`.
- `classes/PaymethodrulesListRenderer.php`: Ein spezialisierter Helfer zum Rendern von Listen im Back Office, der möglicherweise `HelperList` erweitert oder benutzerdefiniertes Spalten-Rendering bereitstellt.
- `classes/PaymethodrulesLog.php`: Alias oder spezifische Implementierung für `PaymethodrulesAuditLog`.
- `classes/PaymethodrulesPolicy.php`
  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `ps_paymethodrules_policy`
  - **`$definition`-Felder:** `id_paymethodrules_policy`, `name`, `active`, `policy_type` (`show`/`hide`), `payment_methods` (JSON-Array von Modulnamen), `unavailable_message` (mehrsprachig), `conditions_tree` (JSON-Darstellung des Bedingungsbaums), `date_add`, `date_upd`.
  - **Wichtige öffentliche Methoden:** Methoden zum Speichern/Laden von Richtliniendaten, Abrufen zugehöriger Bedingungen und Bereitstellen richtlinienspezifischer Logik.
- `classes/PaymethodrulesPolicyDuplicator.php`: Dienstprogrammklasse speziell zum Duplizieren von `PaymethodrulesPolicy`-Objekten, um sicherzustellen, dass alle zugehörigen Bedingungen und Gruppen ebenfalls korrekt kopiert werden.
- `classes/PaymethodrulesPreset.php`: Behandelt wahrscheinlich vordefinierte Sätze von Bedingungen oder Richtlinien, die vom Händler schnell geladen werden können.
- `classes/PaymethodrulesRule.php`: Könnte ein älterer oder alternativer Name für `PaymethodrulesCondition` oder `PaymethodrulesPolicy` sein, oder eine Basisklasse für Regelkomponenten.
- `classes/PaymethodrulesTreeRepository.php`: Verwaltet die Persistenz und den Abruf der `PaymethodrulesConditionTree`-Struktur, wahrscheinlich durch Konvertierung in/aus JSON zur Speicherung im `PaymethodrulesPolicy`-Objekt.

### 4.4 JavaScript-Assets (`views/js/`)

- `paymethodrules/lib/searchTool/views/js/autocomplete.js`: Generische Autocomplete-Funktionalität, wahrscheinlich verwendet zur Auswahl von Produkten, Kategorien oder anderen Entitäten innerhalb des Bedingungs-Builders.
- `paymethodrules/lib/searchTool/views/views/js/autocomplete.js`: Duplikat oder spezifische Version des Autocomplete-Skripts.
- `paymethodrules/views/js/adminConditionBuilder.js`:
  - **Umfang:** Back-Office (Richtlinienerstellungs-/Bearbeitungsbildschirm).
  - **Funktionalität:** Handhabt die dynamische Erstellung, Änderung und Löschung von Bedingungen und Bedingungsgruppen innerhalb des Richtlinienformulars. Verwaltet die „UND“/„ODER“-Logik, fügt neue Bedingungszeilen hinzu, handhabt Änderungen des Bedingungstyps (z. B. Anzeige verschiedener Eingabefelder für „Warenkorbwert“ vs. „Produkt“).
- `paymethodrules/views/js/adminPaymethodrulesDashboard.js`:
  - **Umfang:** Back-Office (Dashboard-Bildschirm).
  - **Funktionalität:** Könnte AJAX-Aufrufe für Dashboard-Widgets, Datenaktualisierung oder interaktive Elemente auf dem Dashboard verwalten.
- `paymethodrules/views/js/adminPaymethodrulesSearchTool.js`:
  - **Umfang:** Back-Office (Bedingungs-Builder).
  - **Funktionalität:** Integriert die `autocomplete.js`-Bibliothek zum Suchen und Auswählen von Entitäten (Produkte, Kategorien, Kunden, Versanddienstleister) beim Erstellen von Bedingungen.
- `paymethodrules/views/js/adminPaymethodrulesSimulator.js`:
  - **Umfang:** Back-Office (Simulator-Bildschirm).
  - **Funktionalität:** Erfasst Benutzereingaben für Simulationskriterien, sendet AJAX-Anfragen an den Simulator-Controller und aktualisiert dynamisch die Anzeige mit der simulierten Verfügbarkeit der Zahlungsmethode.
- `paymethodrules/views/js/adminPolicyRules.js`:
  - **Umfang:** Back-Office (Richtlinienliste und Bearbeitungsbildschirme).
  - **Funktionalität:** Allgemeines JS für die Richtlinienverwaltung, wie z. B. die Handhabung von Aktivieren/Deaktivieren-Umschaltern, Duplizierungsaktionen und potenziell die Formularübermittlungslogik für Richtliniendetails.
- `paymethodrules/views/js/checkout.js`:
  - **Umfang:** Front-Office (Checkout-Seite).
  - **Funktionalität:** Dies ist entscheidend. Es überwacht Änderungen im Checkout-Prozess (z. B. Auswahl der Versandmethode, Adressänderung, Warenkorbaktualisierung) und könnte AJAX-Aufrufe auslösen, um die Verfügbarkeit der Zahlungsmethode neu zu bewerten oder die Anzeige von Nachrichten bei Nichtverfügbarkeit dynamisch zu aktualisieren. Es stellt sicher, dass die Zahlungsoptionen immer aktuell sind.
- `paymethodrules/views/js/unavailableUi.js`:
  - **Umfang:** Front-Office (Checkout-Seite).
  - **Funktionalität:** Verwaltet die Anzeige und das Styling der „Nachricht bei Nichtverfügbarkeit“ für ausgeblendete Zahlungsmethoden. Es könnte die Nachricht dynamisch einfügen, CSS-Klassen anwenden oder Animationen verwalten.

### 4.5 CSS-Stylesheets (`views/css/`)

- `paymethodrules/lib/searchTool/views/css/autocomplete.css`: Stile für das Autocomplete-Suchwerkzeug im Back Office.
- `paymethodrules/lib/searchTool/views/views/css/autocomplete.css`: Duplikat oder spezifische Version des Autocomplete-CSS.
- `paymethodrules/views/css/admin_paymethodrules.css`:
  - **Umfang:** Back-Office (Alle Modul-Admin-Bildschirme).
  - **Funktionalität:** Bietet Styling für die Richtlinienliste, den Bedingungs-Builder, das Dashboard, den Simulator und das Audit-Log. Enthält Stile für Formularelemente, Tabellen und benutzerdefinierte UI-Komponenten, die spezifisch für das Modul sind.
  - **Wichtige CSS-Klassenselektoren:** `.paymethodrules-policy-card`, `.condition-group`, `.condition-row`, `.paymethodrules-dashboard-widget`.
- `paymethodrules/views/css/front.css`:
  - **Umfang:** Front-Office (Checkout-Seite).
  - **Funktionalität:** Bietet grundlegendes Styling für die Nachrichten bei nicht verfügbaren Zahlungsmethoden oder visuelle Hinweise im Zusammenhang mit ausgeblendeten Zahlungsoptionen auf der Checkout-Seite.
  - **Wichtige CSS-Klassenselektoren:** `.paymethodrules-unavailable-message`, `.paymethodrules-hidden-payment`.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `paymethodrules/views/templates/hook/payment_top.tpl`:
  - **Hook:** `displayPaymentTop` (oder ähnlich, je nach PS-Version)
  - **Visueller Block:** Dieses Template könnte verwendet werden, um eine allgemeine Nachricht oder Informationen zu Zahlungsregeln am oberen Rand des Zahlungsbereichs anzuzeigen. Die primäre Interaktion besteht jedoch normalerweise darin, das Array der Zahlungsoptionen direkt zu ändern. Es könnte auch verwendet werden, um die Skripte `checkout.js` und `unavailableUi.js` einzufügen.

#### Admin-Templates (`views/templates/admin/`)

- `paymethodrules/lib/searchTool/views/scripts.tpl`: Enthält JS/CSS für das Suchwerkzeug im Admin-Bereich.
- `paymethodrules/lib/searchTool/views/views/scripts.tpl`: Duplikat oder spezifische Version der Suchwerkzeug-Skripte.
- `paymethodrules/views/templates/admin/auditPreview.tpl`: Rendert die Detailansicht für einen einzelnen Audit-Log-Eintrag, zeigt Kontext, angewendete Richtlinien und Änderungen der Zahlungsmethode.
- `paymethodrules/views/templates/admin/dashboard.tpl`: Rendert das Hauptmodul-Dashboard, einschließlich Widgets für die Richtlinienzusammenfassung, aktuelle Protokolle und schnelle Links.
- `paymethodrules/views/templates/admin/helpers/list/list_action_duplicate.tpl`: Benutzerdefiniertes Template für die Schaltfläche „Duplizieren“ in der `HelperList` für Richtlinien.
- `paymethodrules/views/templates/admin/policiesPreview.tpl`: Könnte für eine schnelle Vorschau der Regeln einer Richtlinie verwendet werden, ohne das vollständige Bearbeitungsformular aufzurufen, oder zur Anzeige von Richtliniendetails im Audit-Log.
- `paymethodrules/views/templates/admin/policyConditionBuilder.tpl`: Das Kerntemplate zum Rendern der dynamischen Bedingungs-Builder-Oberfläche innerhalb des Richtlinien-Hinzufügen-/Bearbeitungsformulars. Es enthält Partials für einzelne Bedingungen und Gruppen.
- `paymethodrules/views/templates/admin/policyRuleCard.tpl`: Rendert eine einzelne Richtlinie als Karte oder Zeile in einer Liste, potenziell verwendet im Dashboard oder einer vereinfachten Richtlinienansicht.
- `paymethodrules/views/templates/admin/policyRulesTable.tpl`: Rendert die Haupttabelle der Richtlinien auf dem Bildschirm `AdminPaymethodrulesPolicies`.
- `paymethodrules/views/templates/admin/scopeSelector.tpl`: Ein wiederverwendbares Template zur Auswahl des Umfangs (z. B. Shop, Sprache) innerhalb von Admin-Formularen.

#### Front-Office-Templates (`views/templates/front/`)

- Es sind keine dedizierten Front-Office-Seitentemplates aufgeführt, was darauf hindeutet, dass das Modul hauptsächlich in bestehende Checkout-Templates integriert wird, indem es Daten ändert, anstatt völlig neue Seiten zu rendern.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- `ps_paymethodrules_policy`: Speichert die Hauptrichtliniendefinitionen, einschließlich Name, Status, betroffene Zahlungsmethoden, Richtlinientyp, Nachrichten bei Nichtverfügbarkeit (mehrsprachig) und die JSON-Darstellung des Bedingungsbaums.
- `ps_paymethodrules_log`: Speichert Audit-Log-Einträge, einschließlich `id_cart`, `id_customer`, `context_data`, `policies_applied`, `payment_methods_before`, `payment_methods_after` und `date_add`.
- (Potenziell) `ps_paymethodrules_condition` und `ps_paymethodrules_condition_group`, wenn der Bedingungsbaum in einer normalisierten Weise und nicht vollständig als JSON innerhalb von `ps_paymethodrules_policy` gespeichert wird. Die Datei `install.sql` wird dies bestätigen.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionPaymentOptionsModifier` | Während des Checkout-Prozesses, bevor Zahlungsmethoden angezeigt werden. | **Primärer Hook:** Die `PaymethodrulesEngine` des Moduls wird hier aufgerufen, um das Array der verfügbaren Zahlungsoptionen basierend auf aktiven Richtlinien und dem aktuellen Warenkorbkontext zu filtern und zu ändern. |
| `displayBackOfficeHeader` | Bei jedem Laden einer Back-Office-Seite. | Fügt modulspezifisches CSS und JS für Admin-Controller ein (z. B. `admin_paymethodrules.css`, `adminConditionBuilder.js`). |
| `displayHeader` | Bei jedem Laden einer Front-Office-Seite. | Fügt modulspezifisches CSS und JS für das Front Office ein (z. B. `front.css`, `checkout.js`, `unavailableUi.js`), insbesondere auf der Checkout-Seite. |
| `moduleRoutes` | Während der Routenkompilierung von PrestaShop. | Registriert benutzerdefinierte Front-Office- und Back-Office-Routen für die Controller des Moduls (z. B. `/module/paymethodrules/simulate`). |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird. | Fügt modulspezifisches CSS und JS für den aktuellen Admin-Controller ein, um sicherzustellen, dass Assets nur bei Bedarf geladen werden. |
| `actionObject*AddAfter` / `actionObject*UpdateAfter` | Nachdem ein Objekt (z. B. `Cart`, `Customer`) hinzugefügt oder aktualisiert wurde. | Potenziell verwendet, um interne Caches zu leeren oder eine Neubewertung auszulösen, wenn das Modul zwischengespeicherte Daten verwaltet. |
| `displayAdminProductsExtra` (oder ähnlich) | Auf der Produktbearbeitungsseite im BO. | Könnte verwendet werden, um produktspezifische Bedingungen direkt auf der Produktseite hinzuzufügen, obwohl dies in der Dateiliste nicht explizit erwähnt wird. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Bedingte Zahlungsregel-Regeln“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.

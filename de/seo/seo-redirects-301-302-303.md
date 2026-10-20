---
title: "Seo Redirects 301, 302, 303 - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Seo Redirects 301, 302, 303 von MyPresta.eu."
sidebar:
  label: "Seo Redirects 301, 302, 303 - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Seo Redirects 301, 302, 303 auf MyPresta.eu kaufen](https://mypresta.eu/modules/seo/seo-redirects-301-302-303.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/seo/seo-redirects-301-302-303/)
>
> ---


# Seo Redirects 301, 302, 303

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Seo Redirects 301, 302, 303“ bietet eine umfassende Suite von Tools, die über ein dediziertes Menü in Ihrem PrestaShop Back Office zugänglich sind. Nach der Installation finden Sie einen neuen Menüpunkt, typischerweise unter **„SEO & SEM“** oder **„Erweiterte Einstellungen“**, mit dem Namen **„Seo Redirects“** oder ähnlich. Dieses Menü enthält mehrere Unterpunkte, die jeweils zu einem spezifischen Konfigurationsbildschirm führen.

### 2.1 Hauptkonfigurationsseite des Moduls (Back Office > Module > Konfigurieren)

Dieser anfängliche Konfigurationsbildschirm (zugänglich durch Klicken auf „Konfigurieren“ nach der Installation) bietet allgemeine Einstellungen für das Modul.

- **Was diese Einstellung bewirkt:** Dieser Bildschirm enthält typischerweise grundlegende Modulaktivierung und vielleicht einige globale Einstellungen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Aktivieren des Moduls:* Aktiviert die Weiterleitungslogik in Ihrem Shop.
  - *Deaktivieren des Moduls:* Stoppt alle von diesem Modul verwalteten Weiterleitungen.
- **Empfohlener Wert:** **Aktiviert**, damit das Modul funktioniert.
- **Händlerszenario / Beispiel:** Nach der Installation möchten Sie sicherstellen, dass das Modul aktiv ist, damit es Ihre Weiterleitungen verwalten kann.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul organisiert seine leistungsstarken Funktionen in mehrere verschiedene Abschnitte, die jeweils von einem dedizierten Admin-Controller verwaltet werden. Sie finden diese unter dem Hauptmenüpunkt „Seo Redirects“ in Ihrem PrestaShop Back Office.

#### 2.2.1 Dashboard (AdminSeoRedirectDashboardController)

**Bildschirmname & Menüpfad:** **Seo Redirects > Dashboard**
Dieser Bildschirm bietet einen Überblick über die Leistung und den Status Ihrer Weiterleitungen. Es ist Ihre zentrale Anlaufstelle, um schnell zu verstehen, wie Ihre Weiterleitungen funktionieren.

- **Verfügbare Aktionen & Einstellungen:**
  - **Übersicht der Weiterleitungen:** Zeigt Statistiken wie die Gesamtzahl der aktiven Weiterleitungen, erstellte Weiterleitungen und möglicherweise die Häufigkeit, mit der Weiterleitungen ausgelöst wurden.
  - **Weiterleitungsverlauf/Aktivität:** Kann aktuelle Weiterleitungsversuche anzeigen, einschließlich erfasster 404-Fehler und erfolgreich weitergeleiteter URLs.
  - **SEOR\_DASHBOARD\_PERIOD:** Diese Einstellung steuert wahrscheinlich den Zeitraum, für den die Dashboard-Statistiken angezeigt werden (z. B. letzte 7 Tage, letzte 30 Tage, Gesamtzeit).
- **Auswirkung von Änderungen:** Das Ändern des Dashboard-Zeitraums aktualisiert die angezeigten Statistiken, um den ausgewählten Zeitraum widerzuspiegeln, und hilft Ihnen, Trends über verschiedene Zeiträume zu analysieren.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie dieses Dashboard regelmäßig, um den Zustand Ihrer Weiterleitungen zu überwachen, neue 404-Fehler zu identifizieren, die behoben werden müssen, und sicherzustellen, dass Ihre SEO-Bemühungen Früchte tragen.

#### 2.2.2 Weiterleitungsliste (AdminSeoRedirectListController)

**Bildschirmname & Menüpfad:** **Seo Redirects > Weiterleitungsliste**
Dies ist der Kern des Moduls, wo Sie individuelle Weiterleitungsregeln erstellen, bearbeiten und verwalten.

- **Verfügbare Aktionen & Einstellungen:**
  - **Neue Weiterleitung hinzufügen:** Ein Formular zum Erstellen einer neuen Weiterleitungsregel.
    - **Alte URL (Quell-URL):** Die exakte URL, die nicht mehr gültig ist oder von der Sie weiterleiten möchten.
    - **Neue URL (Ziel-URL):** Die exakte URL, an die Besucher und Suchmaschinen gesendet werden sollen.
    - **Weiterleitungstyp:**
      - **301 Permanente Weiterleitung:** Teilt Suchmaschinen mit, dass die Seite dauerhaft verschoben wurde. Dies ist der häufigste und SEO-freundlichste Typ, der fast den gesamten „Link Juice“ weitergibt. Verwenden Sie dies, wenn eine Seite dauerhaft verschwunden und durch eine andere ersetzt wurde.
      - **302 Gefunden / Temporäre Weiterleitung:** Teilt Suchmaschinen mit, dass die Verschiebung temporär ist. Verwenden Sie dies, wenn Sie erwarten, dass die alte URL in Zukunft wieder aktiv wird (z. B. für saisonale Produkte, A/B-Tests). Es wird weniger SEO-Wert weitergegeben.
      - **303 Siehe Andere:** Ähnlich wie 302, oft nach einer POST-Anfrage verwendet, um zu einer neuen Seite weiterzuleiten, um eine erneute Übermittlung zu verhindern. Weniger verbreitet für allgemeine SEO-Weiterleitungen.
    - **Status (Aktiviert/Deaktiviert):** Ermöglicht es Ihnen, eine spezifische Weiterleitungsregel zu aktivieren oder zu deaktivieren, ohne sie zu löschen.
  - **Weiterleitungen bearbeiten/löschen:** Bestehende Regeln ändern oder entfernen.
  - **Suchen/Filtern:** Finden Sie spezifische Weiterleitungen nach alter oder neuer URL.
  - **Massenaktionen:** Wenden Sie Aktionen (aktivieren, deaktivieren, löschen) auf mehrere ausgewählte Weiterleitungen an.
- **Auswirkung von Änderungen:**
  - *Hinzufügen einer Weiterleitung:* Beginnt sofort, den Traffic von der alten URL gemäß dem angegebenen Typ auf die neue umzuleiten.
  - *Bearbeiten einer Weiterleitung:* Aktualisiert das Weiterleitungsverhalten.
  - *Löschen einer Weiterleitung:* Entfernt die Regel, was potenziell zu 404-Fehlern führen kann, wenn die alte URL noch aufgerufen wird.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Wann immer Sie ein Produkt entfernen, eine Kategorie-URL ändern oder die Adresse einer Seite aktualisieren, erstellen Sie sofort eine 301-Weiterleitung von der alten URL zur neuen.
  2. Überprüfen Sie regelmäßig Ihre 404-Fehlerprotokolle (z. B. in der Google Search Console oder im Audit-Bereich des Moduls) und fügen Sie Weiterleitungen für häufig auftretende defekte Links hinzu.

#### 2.2.3 Weiterleitungen importieren (AdminSeoRedirectImportController)

**Bildschirmname & Menüpfad:** **Seo Redirects > Importieren**
Dieser Bildschirm ermöglicht es Ihnen, eine Datei (typischerweise CSV) hochzuladen, die viele Weiterleitungsregeln enthält, was die Verwaltung einer großen Anzahl von Weiterleitungen erleichtert.

- **Verfügbare Aktionen & Einstellungen:**
  - **CSV-Datei hochladen:** Wählen Sie eine Datei von Ihrem Computer aus. Die Datei sollte Spalten für „Alte URL“, „Neue URL“ und „Weiterleitungstyp“ enthalten.
  - **IV\_COL\_DELIMITER:** Diese Einstellung definiert das Zeichen, das zum Trennen von Spalten in Ihrer CSV-Datei verwendet wird (z. B. Komma, Semikolon, Tabulator).
  - **SEOR\_SAFE\_ROLLOUT:** Diese Einstellung steuert wahrscheinlich einen „sicheren Modus“ für Importe, der es Ihnen möglicherweise ermöglicht, Änderungen vorab anzuzeigen oder Weiterleitungen schrittweise zu aktivieren, um versehentliche Probleme zu vermeiden.
- **Auswirkung von Änderungen:**
  - *Importieren einer Datei:* Erstellt mehrere Weiterleitungsregeln in großen Mengen, was erhebliche manuelle Arbeit spart.
  - *Ändern des Trennzeichens:* Stellt sicher, dass das Modul Ihre CSV-Datei korrekt parst.
  - *Sicherer Rollout:* Wenn aktiviert, könnte dies eine gestaffelte Bereitstellung von Weiterleitungen ermöglichen, sodass Sie Zeit zur Überprüfung haben, bevor sie live gehen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie diese Funktion, wenn Sie einen Shop migrieren, eine größere Website-Umstrukturierung durchführen oder eine große Anzahl angesammelter 404-Fehler bereinigen. Testen Sie immer zuerst eine kleine Charge, wenn möglich.

#### 2.2.4 Audit (AdminSeoRedirectAuditController)

**Bildschirmname & Menüpfad:** **Seo Redirects > Audit**
Das Audit-Tool hilft Ihnen, defekte Links (404-Fehler) auf Ihrer Website zu identifizieren, die primäre Kandidaten für eine Weiterleitung sind.

- **Verfügbare Aktionen & Einstellungen:**
  - **Nach 404-Fehlern suchen:** Startet einen Scan Ihrer Website (oder eines bestimmten Teils), um Seiten zu finden, die einen 404-Status zurückgeben.
  - **Liste der 404-Fehler:** Zeigt eine Tabelle der erkannten defekten Links an, oft mit der verweisenden Seite (wo der defekte Link gefunden wurde) und der Häufigkeit des Zugriffs.
  - **Option zum Erstellen einer Weiterleitung:** Erstellen Sie direkt von diesem Bildschirm aus eine Weiterleitungsregel für einen erkannten 404-Fehler.
- **Auswirkung von Änderungen:** Das Ausführen eines Audits hilft Ihnen, Probleme proaktiv zu finden und zu beheben, die SEO und Benutzererfahrung schaden.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Führen Sie regelmäßig (z. B. monatlich) ein Audit durch, um neue defekte Links zu erkennen, die aufgrund von Inhaltsänderungen oder externen Links auftreten könnten. Priorisieren Sie die Behebung von 404-Fehlern, die häufig aufgerufen oder von wichtigen Seiten verlinkt werden.

#### 2.2.5 Verlauf (AdminSeoRedirectHistoryController)

**Bildschirmname & Menüpfad:** **Seo Redirects > Verlauf**
Dieser Bildschirm protokolliert alle Weiterleitungsereignisse und bietet eine klare Aufzeichnung darüber, wann und wie Weiterleitungen verwendet werden.

- **Verfügbare Aktionen & Einstellungen:**
  - **Tabelle der Weiterleitungsereignisse:** Zeigt Details wie die ursprünglich angeforderte URL, die neue URL, zu der weitergeleitet wurde, den Weiterleitungstyp, Datum/Uhrzeit und möglicherweise den User Agent oder die IP-Adresse.
  - **Suchen/Filtern:** Hilft Ihnen, spezifische Weiterleitungsereignisse zu finden.
- **Auswirkung von Änderungen:** Dies ist ein Berichts- und Diagnosetool. Es ändert das Shop-Verhalten nicht, liefert aber wertvolle Einblicke in die Leistung Ihrer Weiterleitungen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie den Verlauf, um zu überprüfen, ob bestimmte Weiterleitungen wie erwartet funktionieren, unerwartete Weiterleitungsschleifen zu beheben oder Traffic-Muster zu weitergeleiteten Seiten zu analysieren.

#### 2.2.6 Einstellungen (AdminSeoRedirectSettingsController)

**Bildschirmname & Menüpfad:** **Seo Redirects > Einstellungen**
Dieser Abschnitt enthält erweiterte Konfigurationsoptionen, die das globale Verhalten des Moduls steuern.

- **Verfügbare Aktionen & Einstellungen:**
  - **seor\_pos\_exclude:**
    - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, bestimmte URLs oder Muster vom automatischen Weiterleiten oder Audit auszuschließen. Dies ist nützlich für Seiten, die Sie absichtlich einen 404 zurückgeben lassen möchten (z. B. alte Testseiten).
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Hinzufügen von URLs:* Das Modul ignoriert diese URLs bei der Durchführung von Weiterleitungen oder Audits.
      - *Entfernen von URLs:* Diese URLs unterliegen der Weiterleitungslogik des Moduls.
    - **Empfohlener Wert:** Halten Sie diese Liste mit allen URLs aktuell, die tatsächlich 404 sein und nicht weitergeleitet werden sollen.
    - **Händlerszenario / Beispiel:** Sie haben möglicherweise eine temporäre Landingpage, die Sie vollständig entfernen möchten, und Sie möchten nicht, dass das Modul versucht, sie weiterzuleiten.
  - **seor\_unavorder:**
    - **Was diese Einstellung bewirkt:** Steuert wahrscheinlich, wie das Modul Weiterleitungen für nicht verfügbare Produkte oder ausverkaufte Produkte handhabt.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Aktiviert:* Das Modul leitet nicht verfügbare Produktseiten möglicherweise automatisch zu einer Kategorieseite oder einer benutzerdefinierten „Produkt nicht gefunden“-Seite weiter.
      - *Deaktiviert:* Nicht verfügbare Produktseiten geben einen Standard-404-Fehler zurück.
    - **Empfohlener Wert:** **Aktiviert**, um die Benutzererfahrung und SEO für eingestellte Produkte zu verbessern.
    - **Händlerszenario / Beispiel:** Wenn ein Produkt aus Ihrem Katalog entfernt wird, können Sie seine alte URL automatisch zu seiner übergeordneten Kategorie oder einem ähnlichen Produkt weiterleiten, anstatt einen 404 anzuzeigen.
  - **seor\_pos\_category, seor\_pins\_category, seor\_pos\_exclude\_cat, seor\_oos\_cat\_include, seor\_emptycat\_exclusions, seor\_pos, seor\_emptycat:**
    - **Was diese Einstellungen bewirken:** Dies ist wahrscheinlich eine Gruppe von Einstellungen, die sich darauf beziehen, wie das Modul Weiterleitungen für Kategorien handhabt, insbesondere leere Kategorien, ausverkaufte Produkte innerhalb von Kategorien oder spezifische Kategorieausschlüsse.
      - `seor_pos_category`: Allgemeine Einstellung für Kategorieweiterleitungen.
      - `seor_pins_category`: Kann sich auf „angeheftete“ Kategorien oder spezifisches Kategorieweiterleitungsverhalten beziehen.
      - `seor_pos_exclude_cat`: Schließt bestimmte Kategorien von der automatischen Weiterleitungslogik aus.
      - `seor_oos_cat_include`: Bezieht ausverkaufte Produkte in die Kategorieweiterleitungslogik ein.
      - `seor_emptycat_exclusions`: Schließt bestimmte leere Kategorien von der Weiterleitung aus.
      - `seor_pos`: Allgemeine Einstellung für Produkt-/Kategorienpositionsweiterleitungen.
      - `seor_emptycat`: Steuert automatische Weiterleitungen für leere Kategorien.
    - **Auswirkung der Änderung dieser Einstellungen:** Diese Einstellungen ermöglichen eine feingranulare Kontrolle darüber, wie Kategorie-URLs verwaltet werden, wenn Kategorien leer sind, Produkte nicht vorrätig sind oder Kategorien entfernt werden. Sie können 404-Fehler für dynamische Inhalte verhindern.
    - **Empfohlener Wert:** Überprüfen Sie diese basierend auf den spezifischen Anforderungen Ihres Shops. Zum Beispiel kann das automatische Weiterleiten leerer Kategorien zu ihrer übergeordneten Kategorie vorteilhaft sein.
    - **Händlerszenario / Beispiel:** Wenn eine Kategorie leer wird, weil alle Produkte ausverkauft sind, möchten Sie möglicherweise ihre URL automatisch zur übergeordneten Kategorie weiterleiten, um einen 404 zu vermeiden.

#### 2.2.7 Tools (AdminSeoRedirectToolsController)

**Bildschirmname & Menüpfad:** **Seo Redirects > Tools**
Dieser Abschnitt bietet Dienstprogrammfunktionen, möglicherweise einschließlich der Integration mit externen Diensten.

- **Verfügbare Aktionen & Einstellungen:**
  - **SEOR\_GSC\_TOKEN, SEOR\_GSC\_SITE:** Diese Einstellungen deuten auf eine Integration mit der Google Search Console (GSC) hin.
    - **Was diese Einstellungen bewirken:** Ermöglichen es Ihnen, Ihren PrestaShop-Shop mit Ihrem Google Search Console-Konto zu verbinden. Dies könnte es dem Modul ermöglichen, von Google gemeldete 404-Fehler automatisch abzurufen oder Sitemaps/Weiterleitungen an die GSC zu übermitteln.
    - **Auswirkung der Änderung dieser Einstellung:**
      - *Konfigurieren von GSC:* Ermöglicht den Datenaustausch zwischen Ihrem Shop und der Google Search Console, wodurch die Erkennung defekter Links automatisiert und Ihr SEO-Workflow verbessert werden kann.
      - *Nicht konfiguriert:* Sie müssen die GSC manuell auf 404-Fehler überprüfen und Weiterleitungen hinzufügen.
    - **Empfohlener Wert:** Konfigurieren Sie dies, wenn Sie die Google Search Console aktiv für die SEO Ihres Shops nutzen.
    - **Händlerszenario / Beispiel:** Anstatt die Google Search Console manuell auf neue 404-Fehler zu überprüfen, könnte das Modul diese direkt abrufen, sodass Sie Weiterleitungen schneller erstellen können.

#### 2.2.8 Statistiken (AdminSeoRedirectStatsController)

**Bildschirmname & Menüpfad:** **Seo Redirects > Statistiken**
Dieser Bildschirm bietet Statistiken zur allgemeinen Gesundheit Ihres Shops, möglicherweise einschließlich der Auswirkungen von Weiterleitungen.

- **Verfügbare Aktionen & Einstellungen:**
  - **PS\_SHOP\_ENABLE:** Dies ist ein Standard-PrestaShop-Konfigurationsschlüssel, der angibt, ob Ihr Shop derzeit aktiviert oder im Wartungsmodus ist. Das Modul könnte dies als schnelle Statusprüfung anzeigen.
  - **Weiterleitungsleistungsmetriken:** Kann aggregierte Daten darüber anzeigen, wie viele Weiterleitungen stattgefunden haben, welche Typen am häufigsten sind und deren Gesamtauswirkungen.
- **Auswirkung von Änderungen:** Dies ist in erster Linie ein Informationsbildschirm. Er hilft Ihnen, die Gesamtleistung und Nutzung des Moduls zu verstehen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie diese Statistiken regelmäßig, um das Volumen der Weiterleitungen zu verstehen und sicherzustellen, dass das Modul aktiv zu einer gesunden Website beiträgt.

#### 2.2.9 API-Controller (AdminSeoRedirectApiController)

**Bildschirmname & Menüpfad:** **Seo Redirects > API** (oder ähnlich, könnte ein technischer Abschnitt sein)
Dieser Bildschirm ist für fortgeschrittene Benutzer oder Entwickler gedacht, die programmgesteuert mit der Weiterleitungsfunktion des Moduls interagieren möchten.

- **Verfügbare Aktionen & Einstellungen:**
  - **API-Dokumentation:** Bietet Informationen zur Verwendung der API des Moduls, um Weiterleitungen von externen Anwendungen oder benutzerdefinierten Skripten zu erstellen, abzurufen, zu aktualisieren oder zu löschen.
  - **API-Schlüsselverwaltung:** Ermöglicht das Generieren und Verwalten von API-Schlüsseln für sicheren Zugriff.
- **Auswirkung von Änderungen:** Das Konfigurieren des API-Zugriffs ermöglicht externen Systemen (z. B. einem benutzerdefinierten Bestandsverwaltungssystem, einem SEO-Tool eines Drittanbieters), mit Ihren Weiterleitungen zu interagieren.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie dies nur, wenn Sie spezifische Integrationsanforderungen und technisches Fachwissen haben.

#### 2.2.10 CLI-Controller (AdminSeoRedirectCliController)

**Bildschirmname & Menüpfad:** **Seo Redirects > CLI** (oder ähnlich, könnte ein technischer Abschnitt sein)
Dieser Bildschirm bietet Informationen und Tools für Befehlszeilen-Schnittstellen (CLI)-Operationen im Zusammenhang mit dem Modul.

- **Verfügbare Aktionen & Einstellungen:**
  - **CLI-Befehlsdokumentation:** Erklärt, wie modulspezifische Aufgaben von der Befehlszeile Ihres Servers aus ausgeführt werden (z. B. `php bin/console seoredirect:audit`).
  - **Cron-Job-Einrichtung:** Bietet Anweisungen zum Einrichten von Cron-Jobs zur Automatisierung von Aufgaben wie regelmäßigen Audits oder Weiterleitungsbereinigungen.
- **Auswirkung von Änderungen:** Die Verwendung von CLI-Tools ermöglicht die Automatisierung von Aufgaben, was besonders nützlich für große Shops oder komplexe Operationen ist.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Konsultieren Sie diesen Abschnitt, wenn Sie Aufgaben wie tägliche 404-Audits oder regelmäßige Überprüfungen der Weiterleitungsgesundheit mithilfe von Server-Cron-Jobs automatisieren möchten.

#### 2.2.11 Such-Controller (AdminSeoredirectSearchController)

**Bildschirmname & Menüpfad:** **Seo Redirects > Suche** (oder in andere Bildschirme integriert)
Dieser Controller treibt wahrscheinlich erweiterte Suchfunktionen innerhalb der verschiedenen Raster und Listen des Moduls an und hilft Ihnen, schnell spezifische Weiterleitungen, 404-Fehler oder Verlaufseinträge zu finden.

- **Verfügbare Aktionen & Einstellungen:**
  - **Erweiterte Suchfilter:** Bietet granularere Suchoptionen über die einfache Textsuche hinaus, möglicherweise einschließlich Datumsbereichen, Weiterleitungstypen oder Status.
- **Auswirkung von Änderungen:** Verbessert Ihre Fähigkeit, große Datensätze innerhalb des Moduls zu navigieren und zu verwalten.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie dies, wenn Sie schnell eine bestimmte Weiterleitungsregel finden oder eine Untermenge Ihrer Daten analysieren müssen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Dashboard** | `SEOR_DASHBOARD_PERIOD` | Letzte 30 Tage | Steuert den Zeitraum für Dashboard-Statistiken. |
| **Weiterleitungsliste** | Alte URL | N/A | Die URL, von der weitergeleitet werden soll. |
|  | Neue URL | N/A | Die URL, zu der weitergeleitet werden soll. |
|  | Weiterleitungstyp | 301 Permanent | Art der Weiterleitung (301, 302, 303). 301 ist am besten für SEO. |
|  | Status | Aktiviert | Aktiviert/deaktiviert eine spezifische Weiterleitungsregel. |
| **Importieren** | `IV_COL_DELIMITER` | Komma (`,`) | Zeichen, das Spalten in der CSV-Importdatei trennt. |
|  | `SEOR_SAFE_ROLLOUT` | Nein | Aktiviert einen sicheren Modus für Importe (z. B. gestaffelte Bereitstellung). |
| **Einstellungen** | `seor_pos_exclude` | Leer | Liste der URLs/Muster, die von Weiterleitung/Audit ausgeschlossen werden sollen. |
|  | `seor_unavorder` | Ja | Leitet nicht verfügbare Produkte automatisch weiter. |
|  | `seor_pos_category` | Ja | Allgemeine Einstellung für Kategorieweiterleitungen. |
|  | `seor_pins_category` | Nein | Spezifisches Kategorieweiterleitungsverhalten. |
|  | `seor_pos_exclude_cat` | Leer | Schließt bestimmte Kategorien von der automatischen Weiterleitung aus. |
|  | `seor_oos_cat_include` | Ja | Bezieht ausverkaufte Produkte in die Kategorieweiterleitungslogik ein. |
|  | `seor_emptycat_exclusions` | Leer | Schließt bestimmte leere Kategorien von der Weiterleitung aus. |
|  | `seor_pos` | Ja | Allgemeine Einstellung für Produkt-/Kategorienpositionsweiterleitungen. |
|  | `seor_emptycat` | Ja | Steuert automatische Weiterleitungen für leere Kategorien. |
| **Tools** | `SEOR_GSC_TOKEN` | Leer | Google Search Console API-Token für die Integration. |
|  | `SEOR_GSC_SITE` | Leer | Ihre in der Google Search Console registrierte Website-URL. |
| **Statistiken** | `PS_SHOP_ENABLE` | Ja | Zeigt den aktuellen Shop-Status an (aktiviert/Wartung). |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe eine Weiterleitung hinzugefügt, aber sie funktioniert nicht. Was soll ich tun?**
A1:

- **Auf Tippfehler prüfen:** Stellen Sie sicher, dass die „Alte URL“ und „Neue URL“ in der Weiterleitungsliste exakt korrekt eingegeben wurden.
- **Cache leeren:** PrestaShop verwendet Caching. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“. Leeren Sie auch den Cache Ihres Browsers.
- **Modulstatus:** Stellen Sie sicher, dass das Modul „Seo Redirects 301, 302, 303“ unter **Module > Modul-Manager** aktiviert ist.
- **Weiterleitungsreihenfolge:** Wenn Sie mehrere Weiterleitungsmodule oder `.htaccess`-Regeln haben, kann es zu einem Konflikt kommen. Dieses Modul hat normalerweise Vorrang, aber überprüfen Sie die `.htaccess`-Datei Ihres Servers auf widersprüchliche Regeln.
- **Absolute URL vs. Relative URL:** Stellen Sie sicher, dass Sie das richtige Format für Ihre URLs verwenden (z. B. `/alte-seite.html` für relative Pfade oder `https://www.ihrshop.com/alte-seite.html` für vollständige Pfade, je nachdem, wie das Modul sie erwartet).

**F2: Wird dieses Modul meinen Shop verlangsamen?**
A2: Das Modul ist auf Effizienz ausgelegt. Weiterleitungen erfolgen in einem sehr frühen Stadium des Anfrageprozesses, wodurch die Auswirkungen minimiert werden. Zehntausende von Weiterleitungen können jedoch einen geringen Overhead verursachen. Regelmäßiges Auditieren und Bereinigen unnötiger Weiterleitungen (z. B. alte temporäre 302er) kann helfen, die Leistung aufrechtzuerhalten.

**F3: Wie gehe ich mit Weiterleitungen für Produkte um, die vorübergehend nicht vorrätig sind?**
A3:

- Für temporäre Situationen ist eine **302 Temporäre Weiterleitung** zu einer relevanten Kategorieseite oder einer „Benachrichtigen Sie mich, wenn verfügbar“-Seite angemessen. Dies teilt Suchmaschinen mit, dass das Produkt möglicherweise zurückkehrt.
- Überprüfen Sie den Bildschirm **Einstellungen** auf Optionen wie `seor_unavorder` oder `seor_oos_cat_include`, die eine automatische Handhabung für nicht vorrätige Produkte bieten könnten.

**F4: Kann ich Wildcards in meinen Weiterleitungsregeln verwenden (z. B. alle Seiten in einem alten Verzeichnis weiterleiten)?**
A4: Die Dokumentation oder Benutzeroberfläche des Moduls gibt an, ob es reguläre Ausdrücke oder Wildcard-Zeichen (wie `*`) unterstützt. Wenn ja, können Sie leistungsstarke Regeln wie `/alte-kategorie/*` zu `/neue-kategorie/$1` erstellen (wobei `$1` den Rest der URL erfasst). Wenn nicht, müssen Sie jede Weiterleitung einzeln auflisten oder die Importfunktion verwenden. Testen Sie Wildcard-Weiterleitungen immer sorgfältig!

**F5: Mein benutzerdefiniertes Theme zeigt die Funktionen des Moduls nicht korrekt an (z. B. im Audit-Modal).**
A5: Die Back-Office-Oberflächen des Moduls sind im Allgemeinen unabhängig von Ihrem Front-Office-Theme. Wenn Sie Anzeigeprobleme im Admin-Panel haben, könnte dies ein Konflikt mit einem anderen Admin-Modul oder einer Änderung an einer PrestaShop-Kerndatei sein.

- **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und leeren Sie den Cache.
- **Browser-Konsole überprüfen:** Öffnen Sie die Entwicklertools Ihres Browsers (F12) und suchen Sie nach JavaScript-Fehlern oder CSS-Warnungen im Tab „Konsole“, wenn Sie sich auf den Konfigurationsseiten des Moduls befinden. Dies kann Hinweise auf Konflikte geben.
- **Support kontaktieren:** Wenn das Problem weiterhin besteht, senden Sie Screenshots und alle Konsolenfehler an den MyPresta.eu-Support.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Seo Redirects 301, 302, 303“ ist nach dem MVC-Muster (Model-View-Controller) von PrestaShop aufgebaut, mit einem starken Fokus auf administrative Kontrolle und Datenmanagement. Es nutzt `ModuleAdminController` für seine umfangreiche Back-Office-Oberfläche, `ObjectModel` für die Verwaltung von Weiterleitungsdaten und überschreibt den `FrontController`, um Anfragen frühzeitig abzufangen und die Weiterleitungslogik anzuwenden. Das Modul enthält auch API- und CLI-Controller für die programmgesteuerte und automatisierte Verwaltung.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller bearbeiten Anfragen auf der kundenorientierten Seite des Shops.

- `seoredirect/controllers/front/api.php`
  - **Klassenname & Elternklasse:** `SeoredirectApiModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller dient wahrscheinlich als Front-Office-API-Endpunkt, möglicherweise für externe Dienste, um den Weiterleitungsstatus abzufragen oder für interne AJAX-Aufrufe im Zusammenhang mit der Front-Office-Weiterleitungslogik (obwohl die meisten Weiterleitungen über die `FrontController`-Überschreibung gehandhabt werden). Er würde auf spezifische, vom Modul definierte Routen reagieren.
- `seoredirect/controllers/front/cronjob.php`
  - **Klassenname & Elternklasse:** `SeoredirectCronjobModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Bietet einen über das Front-Office zugänglichen Endpunkt zum Ausführen von Cron-Jobs. Dies ermöglicht es serverseitigen Cron-Aufgaben (z. B. `wget`- oder `curl`-Befehle), Modulfunktionen wie Auditing, Bereinigung oder Datensynchronisation auszulösen, ohne eine Back-Office-Authentifizierung zu erfordern.
- `seoredirect/controllers/front/index.php`
  - **Klassenname & Elternklasse:** `SeoredirectIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Ein Platzhalter oder Standard-Front-Controller. In vielen Modulen könnte dies eine einfache Standardroute behandeln oder als Basis für andere Front-Controller dienen. Angesichts der Natur des Moduls liegt seine primäre Front-Office-Logik wahrscheinlich in der `FrontController`-Überschreibung.

#### Back-Office-Admin-Controller

Diese Controller verwalten die Schnittstelle und Daten des Moduls innerhalb des PrestaShop Back Office.

- `seoredirect/controllers/admin/AdminSeoRedirectApiController.php`
  - **Tab-Name und verwaltete Entität:** „API“ (oder ähnlich, unter dem Menü „Seo Redirects“). Verwaltet API-Schlüssel und bietet API-Dokumentation.
  - **Verantwortlichkeit:** Handhabt die Anzeige und Verwaltung von API-Zugangsdaten und Dokumentation für die programmgesteuerte Interaktion mit dem Modul.
- `seoredirect/controllers/admin/AdminSeoRedirectAuditController.php`
  - **Tab-Name und verwaltete Entität:** „Audit“ (unter dem Menü „Seo Redirects“). Verwaltet den Audit-Prozess für 404-Fehler.
  - **Verantwortlichkeit:** Bietet die Schnittstelle zum Scannen des Shops nach 404-Fehlern, zur Anzeige der Ergebnisse und zur Bereitstellung von Optionen zum Erstellen von Weiterleitungen aus erkannten defekten Links.
- `seoredirect/controllers/admin/AdminSeoRedirectCliController.php`
  - **Tab-Name und verwaltete Entität:** „CLI“ (oder ähnlich, unter dem Menü „Seo Redirects“). Bietet CLI-Befehlsdokumentation.
  - **Verantwortlichkeit:** Zeigt Informationen und Anweisungen zur Verwendung der Befehlszeilentools des Moduls an, nützlich für Automatisierung und erweiterte Aufgaben.
- `seoredirect/controllers/admin/AdminSeoRedirectDashboardController.php`
  - **Tab-Name und verwaltete Entität:** „Dashboard“ (unter dem Menü „Seo Redirects“). Zeigt Modulstatistiken und Übersicht an.
  - **Verantwortlichkeit:** Präsentiert Schlüsselmetriken und eine Übersicht über die Weiterleitungsaktivität, möglicherweise einschließlich Diagrammen und Grafiken. Verwaltet die Konfiguration `SEOR_DASHBOARD_PERIOD`.
- `seoredirect/controllers/admin/AdminSeoRedirectHistoryController.php`
  - **Tab-Name und verwaltete Entität:** „Verlauf“ (unter dem Menü „Seo Redirects“). Verwaltet `seor_history`-Datensätze.
  - **Verantwortlichkeit:** Zeigt ein Protokoll aller Weiterleitungsereignisse an, einschließlich Quelle, Ziel, Typ und Zeitstempel.
- `seoredirect/controllers/admin/AdminSeoRedirectImport.php`
  - **Tab-Name und verwaltete Entität:** „Importieren“ (unter dem Menü „Seo Redirects“). Verwaltet den Massenimport von Weiterleitungen.
  - **Verantwortlichkeit:** Bietet die Schnittstelle zum Hochladen von CSV-Dateien, um mehrere Weiterleitungsregeln zu erstellen. Verwaltet die Konfigurationen `IV_COL_DELIMITER` und `SEOR_SAFE_ROLLOUT`.
- `seoredirect/controllers/admin/AdminSeoRedirectListController.php`
  - **Tab-Name und verwaltete Entität:** „Weiterleitungsliste“ (unter dem Menü „Seo Redirects“). Verwaltet `seor` (Weiterleitungs)-Datensätze.
  - **Verantwortlichkeit:** Die primäre Schnittstelle zum Hinzufügen, Bearbeiten, Löschen und Auflisten individueller 301-, 302-, 303-Weiterleitungsregeln.
- `seoredirect/controllers/admin/AdminSeoredirectSearchController.php`
  - **Tab-Name und verwaltete Entität:** „Suche“ (oder integriert). Treibt die Suchfunktion an.
  - **Verantwortlichkeit:** Bietet wahrscheinlich erweiterte Such- und Filterfunktionen, die in verschiedenen Admin-Rastern innerhalb des Moduls verwendet werden.
- `seoredirect/controllers/admin/AdminSeoRedirectSettings.php`
  - **Tab-Name und verwaltete Entität:** „Einstellungen“ (unter dem Menü „Seo Redirects“). Verwaltet `ps_configuration`-Einstellungen im Zusammenhang mit dem Modul.
  - **Verantwortlichkeit:** Bietet die Schnittstelle zum Konfigurieren des globalen Modulverhaltens, wie z. B. Ausschlüsse, automatische Weiterleitungen für nicht verfügbare Produkte/leere Kategorien und andere erweiterte Optionen. Verwaltet `seor_pos_exclude`, `seor_unavorder`, `seor_pos_category`, `seor_pins_category`, `seor_pos_exclude_cat`, `seor_oos_cat_include`, `seor_emptycat_exclusions`, `seor_pos`, `seor_emptycat`.
- `seoredirect/controllers/admin/AdminSeoRedirectStats.php`
  - **Tab-Name und verwaltete Entität:** „Statistiken“ (unter dem Menü „Seo Redirects“). Zeigt allgemeine Shop- und Modulstatistiken an.
  - **Verantwortlichkeit:** Bietet eine Übersicht über den Shop-Status (`PS_SHOP_ENABLE`) und möglicherweise aggregierte Weiterleitungsleistungsdaten.
- `seoredirect/controllers/admin/AdminSeoRedirectToolsController.php`
  - **Tab-Name und verwaltete Entität:** „Tools“ (unter dem Menü „Seo Redirects“). Bietet Dienstprogrammfunktionen.
  - **Verantwortlichkeit:** Enthält Tools wie die Google Search Console-Integration (`SEOR_GSC_TOKEN`, `SEOR_GSC_SITE`) und andere Dienstprogrammfunktionen.
- `seoredirect/controllers/admin/index.php`
  - **Tab-Name und verwaltete Entität:** Kein direkter Controller, typischerweise eine leere Datei oder eine Sicherheitsmaßnahme, um die Verzeichnisauflistung zu verhindern.

### 4.3 Kernklassen & Modelle (`classes/`)

- `seoredirect/override/classes/controller/FrontController.php`
  - **Was es tut:** Dies ist eine kritische Überschreibung. Sie erweitert die Kernklasse `FrontController` von PrestaShop.
  - **Wichtige öffentliche Methoden und Geschäftslogik:** Die Überschreibung fängt wahrscheinlich die Methode `init()` oder `postProcess()` des `FrontController` ab. Bevor PrestaShop die Anfrage an einen spezifischen Seiten-Controller weiterleitet, überprüft diese Überschreibung die angeforderte URL anhand der gespeicherten Weiterleitungsregeln des Moduls. Wenn eine Übereinstimmung gefunden wird, sendet sie den entsprechenden 301-, 302- oder 303-HTTP-Weiterleitungsheader und beendet die Anfrage, wodurch ein 404 verhindert und der Benutzer zur neuen URL gesendet wird. Hier befindet sich die Kern-Weiterleitungslogik.
- `seoredirect/override/classes/controller/index.php`
  - **Was es tut:** Platzhalterdatei, normalerweise für die Sicherheit.
- `seoredirect/override/classes/index.php`
  - **Was es tut:** Platzhalterdatei, normalerweise für die Sicherheit.

*(Hinweis: Das Moduldossier listete keine expliziten benutzerdefinierten `ObjectModel`-Klassen wie `SeoRedirect` oder `SeoRedirectHistory` auf. Angesichts der Präsenz von `AdminSeoRedirectListController`, der `seor` verwaltet, und `AdminSeoRedirectHistoryController`, der `seor_history` verwaltet, ist es jedoch sehr wahrscheinlich, dass es entsprechende `SeoRedirect`- und `SeoRedirectHistory`-Klassen (oder ähnliche Namen) gibt, die `ObjectModel` innerhalb des Hauptverzeichnisses des Moduls oder eines `classes/`-Unterverzeichnisses erweitern, das nicht explizit im Inventar aufgeführt ist. Diese würden das Datenbankschema für Weiterleitungen und Verlaufseinträge definieren.)*

### 4.4 JavaScript-Assets (`views/js/`)

- `seoredirect/examples/console-mock-dashboard-audit.js`
  - **Geltungsbereich:** Wahrscheinlich für Entwicklung/Tests, nicht für die Produktion.
  - **Details:** Beispiel- oder Mock-Daten/Logik für Dashboard- und Audit-Funktionen, möglicherweise für Konsolen-Debugging oder Demonstrationszwecke verwendet.
- `seoredirect/views/js/adminSeoRedirectApi.js`
  - **Geltungsbereich:** Back-Office (AdminSeoRedirectApiController).
  - **Details:** Handhabt clientseitige Interaktionen auf dem API-Konfigurationsbildschirm, wie das Generieren von API-Schlüsseln, das Kopieren von Schlüsseln in die Zwischenablage oder das Anzeigen von API-Dokumentationsmodals.
- `seoredirect/views/js/adminSeoRedirectAudit.js`
  - **Geltungsbereich:** Back-Office (AdminSeoRedirectAuditController).
  - **Details:** Verwaltet den Audit-Prozess, einschließlich AJAX-Aufrufen zum Auslösen von Scans, Aktualisieren von Fortschrittsanzeigen, Anzeigen von Audit-Ergebnissen in einer dynamischen Tabelle und Handhabung von Aktionen wie dem Erstellen von Weiterleitungen aus Audit-Ergebnissen. Kann modale Popups zum Anzeigen oder Bestätigen von Weiterleitungen enthalten.
- `seoredirect/views/js/adminSeoRedirectConfig.js`
  - **Geltungsbereich:** Back-Office (Hauptmodulkonfiguration oder AdminSeoRedirectSettingsController).
  - **Details:** Allgemeines JavaScript für die Hauptkonfigurationsformulare des Moduls. Dies könnte Formularvalidierung, dynamische Feldsichtbarkeit basierend auf anderen Einstellungen oder AJAX-Aufrufe zum Speichern der Konfiguration umfassen.
- `seoredirect/views/js/adminSeoRedirectDashboard.js`
  - **Geltungsbereich:** Back-Office (AdminSeoRedirectDashboardController).
  - **Details:** Treibt die interaktiven Elemente des Dashboards an, wie das Laden von Daten über AJAX, das Rendern von Diagrammen (falls vorhanden) und das Handhaben von Änderungen der Periodenauswahl (`SEOR_DASHBOARD_PERIOD`).
- `seoredirect/views/js/adminSeoRedirectImport.js`
  - **Geltungsbereich:** Back-Office (AdminSeoRedirectImportController).
  - **Details:** Verwaltet den CSV-Importprozess, einschließlich Dateiauswahl, Fortschrittsanzeigen, Anzeigen von Import-Ergebnissen/Fehlern und möglicherweise die Handhabung der `SEOR_SAFE_ROLLOUT`-Logik auf der Clientseite.

### 4.5 CSS-Stylesheets (`views/css/`)

- `seoredirect/views/css/seoredirect-admin.css`
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Details:** Enthält spezifische Stile für die verschiedenen Administrationsbildschirme des Moduls, um eine konsistente und benutzerfreundliche Oberfläche innerhalb des PrestaShop Back Office zu gewährleisten. Dies würde das Styling für Raster, Formulare, Schaltflächen, Modals und Dashboard-Elemente umfassen.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Suchen Sie nach Klassen, die mit `seor-` oder `admin-seoredirect-` beginnen, für spezifische Modulelemente.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - Die Modulbeschreibung erwähnt Front-Office-Hooks (Header, Spalten, Produkt, Footer), aber das Dateiverzeichnis listet keine spezifischen Hook-Templates in `views/templates/hook/` auf. Dies deutet darauf hin, dass die Front-Office-Interaktion hauptsächlich durch die `FrontController`-Überschreibung für Weiterleitungen erfolgt, anstatt sichtbaren Inhalt in Hooks zu rendern. Wenn Hook-Templates existieren, wären sie für sehr spezifische, nicht weiterleitungsbezogene Anzeigeelemente.
- **Admin-Templates (`views/templates/admin/`)**:

  - `seoredirect/lib/searchTool/views/scripts.tpl`: Enthält wahrscheinlich JavaScript- oder Smarty-Logik für ein generisches Suchwerkzeug, das über mehrere Admin-Bildschirme hinweg verwendet wird.
  - `seoredirect/views/admin/adminSearch.tpl`: Template für eine generische Suchoberfläche im Admin.
  - `seoredirect/views/admin/adminSearchCategory.tpl`: Template zum Suchen/Auswählen von Kategorien im Admin.
  - `seoredirect/views/admin/adminSearchCategoryToMove.tpl`: Template für die Kategoriemigration-Suche.
  - `seoredirect/views/admin/adminSearchCategoryToMoveInStock.tpl`: Template für die Kategoriemigration-Suche, speziell für vorrätige Artikel.
  - `seoredirect/views/admin/adminSeoRedirectImport.tpl`: Das Haupttemplate für den Importbildschirm (AdminSeoRedirectImportController).
  - `seoredirect/views/admin/stats.tpl`: Template für den Statistikbildschirm (AdminSeoRedirectStatsController).
  - `seoredirect/views/templates/admin/api.tpl`: Template für den API-Konfigurationsbildschirm (AdminSeoRedirectApiController).
  - `seoredirect/views/templates/admin/audit.tpl`: Template für den Audit-Bildschirm (AdminSeoRedirectAuditController).
  - `seoredirect/views/templates/admin/cli.tpl`: Template für den CLI-Dokumentationsbildschirm (AdminSeoRedirectCliController).
  - `seoredirect/views/templates/admin/dashboard.tpl`: Template für das Modul-Dashboard (AdminSeoRedirectDashboardController).
  - `seoredirect/views/templates/admin/employee_permissions.tpl`: Template zur Verwaltung von Mitarbeiterberechtigungen im Zusammenhang mit den Admin-Tabs des Moduls.
  - `seoredirect/views/templates/admin/import.tpl`: Ein weiteres Template für die Importfunktion (könnte ein Wrapper oder ein spezifischer Teil des Importprozesses sein).
  - `seoredirect/views/templates/admin/seo_redirect_settings/helpers/options/options.tpl`: Ein Teiltemplate zum Rendern von Optionen innerhalb des Einstellungsbildschirms (AdminSeoRedirectSettingsController).
  - `seoredirect/views/templates/admin/tools.tpl`: Template für den Tools-Bildschirm (AdminSeoRedirectToolsController).
  - `seoredirect/views/templates/admin/_api_documentation_modal.tpl`: Ein Modal-Template zur Anzeige der API-Dokumentation.
  - `seoredirect/views/templates/admin/_audit_preview_modal.tpl`: Ein Modal-Template zur Vorschau von Audit-Ergebnissen oder Weiterleitungserstellungen.
  - `seoredirect/views/templates/admin/_cli_documentation_modal.tpl`: Ein Modal-Template zur Anzeige der CLI-Dokumentation.
- **Front-Office-Templates (`views/templates/front/`)**:

  - Es sind keine spezifischen Front-Office-Templates aufgeführt, was die Annahme verstärkt, dass der Front-End-Betrieb des Moduls hauptsächlich über die `FrontController`-Überschreibung für die Weiterleitung erfolgt und nicht über sichtbaren Inhalt.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_seor`: Speichert die Hauptweiterleitungsregeln (Alte URL, Neue URL, Weiterleitungstyp, Status usw.). Diese Tabelle wird vom `AdminSeoRedirectListController` und dem `SeoRedirect` `ObjectModel` (impliziert) verwaltet.
  - `ps_seor_history`: Speichert ein Protokoll aller ausgelösten Weiterleitungen (Ursprüngliche Anfrage, Weitergeleitet an, Typ, Zeitstempel usw.). Diese Tabelle wird vom `AdminSeoRedirectHistoryController` und dem `SeoRedirectHistory` `ObjectModel` (impliziert) verwaltet.
  - `ps_configuration`: Speichert modulspezifische globale Einstellungen wie `SEOR_DASHBOARD_PERIOD`, `IV_COL_DELIMITER`, `SEOR_SAFE_ROLLOUT`, `seor_pos_exclude`, `seor_unavorder`, `seor_pos_category`, `seor_pins_category`, `seor_pos_exclude_cat`, `seor_oos_cat_include`, `seor_emptycat_exclusions`, `seor_pos`, `seor_emptycat`, `SEOR_GSC_TOKEN`, `SEOR_GSC_SITE`.
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `actionFrontControllerSetMedia` | Bevor der Front-Controller Inhalte rendert | Lädt potenziell Front-Office-JS/CSS, falls vorhanden, obwohl unwahrscheinlich für ein Weiterleitungsmodul. |
  | `actionDispatcherBefore` | Sehr früh im Anfragelebenszyklus, bevor an einen Controller weitergeleitet wird. | **KRITISCH:** Dies ist der wahrscheinlichste Hook für die `FrontController`-Überschreibung, um die Anfrage abzufangen und die Weiterleitungslogik anzuwenden. Er ermöglicht es dem Modul, weiterzuleiten, bevor PrestaShop überhaupt versucht, die ursprüngliche Seite zu finden. |
  | `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | Könnte verwendet werden, um den Weiterleitungsstatus für ein Produkt anzuzeigen oder das Erstellen einer Weiterleitung vorzuschlagen, wenn die Produkt-URL geändert wird. |
  | `displayAdminCategoriesExtra` | Auf der Kategoriebearbeitungsseite im Back Office. | Ähnlich wie bei Produkten könnte der Weiterleitungsstatus angezeigt oder Weiterleitungen für Kategorie-URL-Änderungen vorgeschlagen werden. |
  | `displayHeader` | Im `<head>`-Abschnitt jeder Front-Office-Seite. | Unwahrscheinlich für die Kern-Weiterleitungslogik, könnte aber zum Hinzufügen von Meta-Tags oder Canonical-Tags im Zusammenhang mit Weiterleitungen verwendet werden, falls erforderlich. |
  | `displayRightColumn` | In der rechten Spalte der Front-Office-Seiten. | Unwahrscheinlich für dieses Modul. |
  | `displayFooter` | Im Footer jeder Front-Office-Seite. | Unwahrscheinlich für dieses Modul. |
  | `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Könnte verwendet werden, um Weiterleitungen im Zusammenhang mit Checkout-Prozessen zu protokollieren oder zu prüfen, obwohl weniger direkt. |
  | `actionModuleInstall` | Während der Modulinstallation. | Erstellt Datenbanktabellen, registriert Hooks, setzt Standardkonfigurationswerte. |
  | `actionModuleUninstall` | Während der Moduldeinstallation. | Bereinigt Datenbanktabellen, deregistriert Hooks, entfernt Konfigurationswerte. |
  | `actionAdminControllerSetMedia` | Bevor ein Admin-Controller Inhalte rendert. | Lädt Back-Office-JS/CSS für die Admin-Seiten des Moduls. |
  | `actionAdminSeoRedirectSave` | Benutzerdefinierter Hook, wahrscheinlich ausgelöst, nachdem eine Weiterleitungsregel im Back Office gespeichert wurde. | Ermöglicht anderen Modulen oder benutzerdefiniertem Code, auf Weiterleitungsänderungen zu reagieren. |
  | `actionAdminSeoRedirectDelete` | Benutzerdefinierter Hook, wahrscheinlich ausgelöst, nachdem eine Weiterleitungsregel gelöscht wurde. | Ermöglicht anderen Modulen oder benutzerdefiniertem Code, auf Weiterleitungslöschungen zu reagieren. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „Seo Redirects 301, 302, 303“ zur Verfügung.

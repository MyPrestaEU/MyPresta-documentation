---
title: "Suchprotokoll – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Suchprotokoll von MyPresta.eu."
sidebar:
  label: "Suchprotokoll – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Search log auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/search-log.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/search-log/)
>
> ---


# Suchprotokoll

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Keine besonderen Anforderungen über eine Standard-PrestaShop-Hosting-Umgebung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Suchprotokoll)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Suchprotokoll“. Er bietet eine einfache Benutzeroberfläche zum Aktivieren oder Deaktivieren der Protokollierungsfunktion.

- **Menüpfad:** Back Office > Module > Modul-Manager > Suchprotokoll > Konfigurieren

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **Suchprotokoll aktivieren** (Schalter) | Dieser Schalter steuert, ob das Modul Kunden-Suchanfragen aktiv aufzeichnet. | *Wenn aktiviert (JA):* Jedes Mal, wenn ein Kunde die Suchleiste Ihres Shops verwendet, wird sein Suchbegriff im Protokoll des Moduls gespeichert. Sie können diese Protokolle dann im dedizierten Menü „Suchprotokoll“ einsehen. *Wenn deaktiviert (NEIN):* Das Modul stoppt die Aufzeichnung neuer Suchanfragen. Bestehende Protokolle bleiben erhalten, aber es werden keine neuen Daten gesammelt. | **JA** | Sie haben das Modul gerade installiert und möchten sofort mit dem Sammeln von Daten beginnen, um zu verstehen, wonach Ihre Kunden suchen. Sie würden dies auf JA setzen. Wenn Sie die Protokollierung vorübergehend stoppen müssen (z. B. während der Wartung oder wenn Sie zu viele Daten haben), könnten Sie es auf NEIN stellen. |

### 2.2 Dedizierter Admin-Bildschirm: Suchprotokoll-Verwaltung (Back Office > Suchprotokoll)

Auf diesem Bildschirm können Sie alle vom Modul aufgezeichneten Suchanfragen anzeigen und verwalten. Er bietet eine umfassende Liste dessen, wonach Ihre Kunden suchen.

- **Bildschirmname & Menüpfad:** Back Office > **Suchprotokoll** (Dies wird als neuer Menüpunkt angezeigt, normalerweise unter „Shop-Parameter“ oder „Erweiterte Parameter“, je nach Ihrer PrestaShop-Version).

**Verfügbare Aktionen & Einstellungen:**
Dieser Bildschirm präsentiert typischerweise ein Raster (Liste) aller aufgezeichneten Suchbegriffe. Für jeden Eintrag sehen Sie normalerweise:

- **Suchbegriff:** Der genaue Begriff oder die Phrase, die der Kunde in die Suchleiste eingegeben hat.
- **Anzahl der Suchen:** Wie oft dieser spezifische Suchbegriff gesucht wurde.
- **Datum der letzten Suche:** Wann dieser Suchbegriff zuletzt gesucht wurde.
- **Anzahl der Ergebnisse:** Wie viele Produkte für diesen Suchbegriff gefunden wurden (dies ist entscheidend für die Identifizierung von Suchen „ohne Ergebnisse“).

**Raster- / Verwaltungsansicht:**
Das Raster ermöglicht Ihnen:

- **Sortieren:** Klicken Sie auf Spaltenüberschriften (z. B. „Suchbegriff“, „Anzahl der Suchen“), um die Liste zu sortieren.
- **Filtern:** Verwenden Sie die Filterfelder über den Spalten, um die Liste einzugrenzen (z. B. nach einem bestimmten Suchbegriff suchen oder nach der Anzahl der Ergebnisse filtern).
- **Exportieren:** Einige Versionen bieten möglicherweise eine Exportoption an, um die Daten zur weiteren Analyse in einem Tabellenkalkulationsprogramm herunterzuladen.
- **Löschen:** Sie haben möglicherweise Optionen zum Löschen einzelner Sucheinträge oder zum Leeren des gesamten Protokolls.

**Auswirkung von Änderungen:**

- **Anzeigen der Liste:** Bietet sofortige Einblicke in das Suchverhalten der Kunden.
- **Sortieren/Filtern:** Hilft Ihnen, schnell beliebte Suchen, Suchen ohne Ergebnisse oder Trends im Laufe der Zeit zu identifizieren.
- **Löschen von Einträgen:** Entfernt Daten aus dem Protokoll. Dies kann nützlich sein, um irrelevante Einträge zu bereinigen oder die Datenbankgröße zu verwalten, aber im Allgemeinen ist es am besten, die Daten für die historische Analyse zu behalten.

**Empfohlener Workflow für die tägliche Shop-Verwaltung:**

1. **Überprüfen Sie diesen Bildschirm regelmäßig:** Machen Sie es sich zur Gewohnheit, das „Suchprotokoll“ mindestens einmal pro Woche zu überprüfen.
2. **Konzentrieren Sie sich auf Suchen „ohne Ergebnisse“:** Priorisieren Sie Keywords, die null Ergebnisse lieferten. Dies sind Ihre größten Chancen:
   - Haben Sie das Produkt, aber es ist nicht korrekt indiziert oder die Beschreibung ist schlecht?
   - Ist es ein Produkt, das Sie in Betracht ziehen sollten, auf Lager zu nehmen?
   - Ist es eine häufige Rechtschreibfehler, die Sie mit Synonymen berücksichtigen können?
3. **Identifizieren Sie beliebte Suchen:** Sehen Sie, woran Kunden am meisten interessiert sind. Stellen Sie sicher, dass diese Produkte prominent angezeigt, gut beschrieben und leicht zu finden sind.
4. **Analysieren Sie Trends:** Gibt es saisonale Suchbegriffe? Neue Produktideen, die aus Kundenanfragen entstehen?

### 2.3 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Suchprotokoll aktivieren | JA | Steuert, ob Kunden-Suchanfragen aufgezeichnet werden. |
| Suchprotokoll-Verwaltung | Suchbegriff (Rasterspalte) | N/A | Zeigt den tatsächlichen Suchbegriff an, der von Kunden verwendet wurde. |
| Suchprotokoll-Verwaltung | Anzahl der Suchen (Rasterspalte) | N/A | Zeigt an, wie oft ein bestimmtes Keyword gesucht wurde. |
| Suchprotokoll-Verwaltung | Datum der letzten Suche (Rasterspalte) | N/A | Zeigt das jüngste Vorkommen eines Suchbegriffs an. |
| Suchprotokoll-Verwaltung | Anzahl der Ergebnisse (Rasterspalte) | N/A | Entscheidend für die Identifizierung von Suchen, die keine Produkte ergaben. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul aktiviert, aber es werden keine Suchprotokolle angezeigt.**
A:

1. **Prüfen Sie, ob Kunden tatsächlich suchen:** Stellen Sie sicher, dass die Suchleiste Ihres Shops sichtbar ist und von Besuchern genutzt wird.
2. **Cache leeren:** Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal kann Caching verhindern, dass Module vollständig initialisiert werden.
3. **Selbst testen:** Führen Sie ein paar Suchen im Front Office durch, während Sie abgemeldet sind (oder im Inkognito-Modus), und überprüfen Sie dann den Admin-Bildschirm „Suchprotokoll“.
4. **Modulposition:** Obwohl das Modul keine sichtbare Front-Office-Komponente hat, stellen Sie sicher, dass es korrekt eingehängt ist. Das Modul hängt sich typischerweise in `displayHeader` oder ähnliches ein, was automatisch gehandhabt wird. Wenn Probleme weiterhin bestehen, versuchen Sie eine Neuinstallation.

**F: Das Suchprotokoll wird sehr groß. Wird dies meinen Shop verlangsamen?**
A: Obwohl eine sehr große Datenbanktabelle theoretisch die Leistung beeinträchtigen kann, ist es für die meisten Shops unwahrscheinlich, dass die von diesem Modul erstellte `slog`-Tabelle signifikante Verlangsamungen verursacht. Es ist eine einfache Protokolltabelle. Wenn Sie Millionen von Einträgen haben und Probleme bemerken, können Sie ältere Einträge regelmäßig über den Verwaltungsbildschirm „Suchprotokoll“ löschen oder das Modul vorübergehend deaktivieren.

**F: Kann ich sehen, welcher Kunde eine bestimmte Suche durchgeführt hat?**
A: Nein, dieses Modul ist für die aggregierte Keyword-Analyse konzipiert, nicht für die individuelle Kundenverfolgung. Es protokolliert das Keyword, nicht die Kunden-ID. Dies gewährleistet die Privatsphäre der Kunden und liefert dennoch wertvolle Geschäftseinblicke.

**F: Wie exportiere ich die Suchprotokolldaten zur Analyse in Excel?**
A: Der Verwaltungsbildschirm „Suchprotokoll“ in Ihrem Back Office sollte eine Schaltfläche „Exportieren“ haben (oft oben rechts im Raster oder als Massenaktion). Klicken Sie darauf, um die Daten herunterzuladen, normalerweise im CSV-Format, das mit Excel oder Google Sheets geöffnet werden kann.

**F: Die Suchleiste meines benutzerdefinierten Themes scheint nicht protokolliert zu werden.**
A: Das Modul hängt sich typischerweise in die Standard-Suchfunktionalität von PrestaShop ein. Wenn Ihr benutzerdefiniertes Theme eine völlig benutzerdefinierte, nicht standardmäßige Suchimplementierung verwendet (z. B. eine AJAX-Suche, die den PrestaShop-Kern-Suchcontroller umgeht), erfasst das Modul diese Abfragen möglicherweise nicht. In solchen Fällen müssten Sie einen Entwickler beauftragen, die Protokollierungsfunktion direkt in Ihr benutzerdefiniertes Suchskript zu integrieren.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „Suchprotokoll“ ist ein unkompliziertes PrestaShop-Modul, das sich hauptsächlich auf die Datenprotokollierung konzentriert. Es folgt einem Standard-PrestaShop-MVC-Muster für seine Back-Office-Komponente und verwendet einen `AdminController` zur Verwaltung der protokollierten Suchdaten. Der Front-Office-Protokollierungsmechanismus integriert sich direkt in den Kern-Suchprozess von PrestaShop, typischerweise durch Einhängen in einen Hook, der nach der Durchführung einer Suche ausgelöst wird. Es erstellt eine dedizierte Datenbanktabelle zum Speichern von Suchanfragen.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Das Modul integriert sich über Hooks in die bestehende PrestaShop-Suchfunktionalität, anstatt einen eigenen Front-Controller bereitzustellen.
- **Back-Office-Admin-Controller**:

  - `searchlog/controllers/admin/AdminSlog.php`

    - **Klassenname & Elternklasse**: `AdminSlogController` erweitert `ModuleAdminController`.
    - **Verantwortlichkeit**: Dies ist der primäre Controller für die Verwaltung der Suchprotokolleinträge im PrestaShop Back Office. Er handhabt die Anzeige des Suchprotokollrasters, einschließlich Sortierung, Filterung und potenzieller Löschaktionen. Er ist verantwortlich für das Abrufen von Daten aus der Datenbanktabelle `slog` und deren Rendering mithilfe der PrestaShop-Komponenten `HelperList` oder `HelperGrid`.
    - **Tab-Name**: „Suchprotokoll“ (oder ähnlich, je nach Installation).
    - **Verwaltete Entität**: Die Datenbanktabelle `slog`.
  - `searchlog/controllers/admin/index.php`

    - **Klassenname & Elternklasse**: Keine Klasse, sondern eine Standard-PrestaShop-Datei `index.php` innerhalb eines Admin-Controller-Verzeichnisses.
    - **Verantwortlichkeit**: Diese Datei dient typischerweise als Sicherheitsmaßnahme in PrestaShop-Admin-Verzeichnissen, um direkte Verzeichnisauflistungen zu verhindern. Sie enthält normalerweise eine einfache `header('Location: ../../index.php?controller=AdminHome'); exit;` oder eine ähnliche Weiterleitung, oder einfach eine `die('Forbidden');`-Anweisung. Sie enthält keine modulspezifische Logik.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` auf. Die Kernlogik für die Interaktion mit der `slog`-Tabelle wird wahrscheinlich direkt im `AdminSlogController` oder der Hauptmoduldatei `searchlog/index.php` gehandhabt, möglicherweise unter Verwendung eines generischen `Db::getInstance()->execute()` für einfache Datenoperationen oder einer grundlegenden `ObjectModel`-Definition, falls eine implizit erstellt oder nicht im Dossier aufgeführt wurde. Angesichts der Einfachheit ist eine direkte `Db`-Interaktion wahrscheinlicher.

### 4.4 JavaScript-Assets (`views/js/`)

Es sind keine benutzerdefinierten JavaScript-Dateien im Modularchiv aufgeführt. Dies deutet darauf hin, dass das Modul vollständig auf die Kern-JS von PrestaShop für seine Back-Office-Rasterfunktionalität angewiesen ist und keine benutzerdefinierten Front-Office-JS einführt.

### 4.5 CSS-Stylesheets (`views/css/`)

Es sind keine benutzerdefinierten CSS-Dateien im Modularchiv aufgeführt. Dies deutet darauf hin, dass das Modul die Standard-Back-Office-Stile von PrestaShop für seine Konfigurations- und Verwaltungsbildschirme verwendet und keine benutzerdefinierten Front-Office-Stile einführt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Es sind keine benutzerdefinierten Template-Dateien im Modularchiv aufgeführt. Dies impliziert, dass das Konfigurationsformular des Moduls und die Rasteransicht des `AdminSlogController` mithilfe der Standard-`HelperForm`- und `HelperList`- (oder `HelperGrid`)-Templates von PrestaShop gerendert werden, die Teil des PrestaShop-Kernframeworks sind.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_slog` (oder `_slog` mit Ihrem Tabellenpräfix):
    - Diese Tabelle wird vom Modul während der Installation erstellt.
    - Sie speichert die protokollierten Suchanfragen.
    - Typische Felder wären:
      - `id_slog` (Primärschlüssel, INT)
      - `keyword` (VARCHAR, speichert den Suchbegriff)
      - `results` (INT, Anzahl der für das Keyword gefundenen Ergebnisse)
      - `counter` (INT, Anzahl der Suchen nach diesem Keyword)
      - `date_add` (DATETIME, Zeitstempel der ersten Suche nach diesem Keyword)
      - `date_upd` (DATETIME, Zeitstempel der letzten Suche nach diesem Keyword)
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Front-Office-Seite ausgeführt. | Obwohl das Dossier `Header` als Front-Office-Hook auflistet, wird `displayHeader` für ein Protokollierungsmodul oft verwendet, um Assets zu registrieren oder sicherzustellen, dass das Modul auf allen Seiten aktiv ist, auf denen eine Suche stattfinden könnte. Die eigentliche Protokollierungslogik ist wahrscheinlicher an einen `action`-Hook gebunden. |
| `displayRightColumn` | Wird in der rechten Spalte des Front Office ausgeführt. | Unwahrscheinlich für die Protokollierung verwendet zu werden, möglicherweise für eine zukünftige Funktion oder einen Platzhalter. |
| `displayLeftColumn` | Wird in der linken Spalte des Front Office ausgeführt. | Unwahrscheinlich für die Protokollierung verwendet zu werden, möglicherweise für eine zukünftige Funktion oder einen Platzhalter. |
| `displayFooter` | Wird im Footer-Bereich jeder Front-Office-Seite ausgeführt. | Ähnlich wie `displayHeader` könnte es für die Asset-Registrierung oder die Sicherstellung des Modulkontexts verwendet werden, aber nicht für die direkte Protokollierung. |
| `actionSearch` | Wird ausgeführt, nachdem eine Suchanfrage vom PrestaShop-Kern-Suchcontroller verarbeitet wurde. | **Dies ist der wichtigste Hook für dieses Modul.** Er ermöglicht es dem Modul, den Suchbegriff und die Anzahl der Ergebnisse abzufangen, *nachdem* PrestaShop seine interne Suche durchgeführt hat, wodurch die Protokollierung des `keyword` und der `results`-Anzahl in die `ps_slog`-Tabelle ermöglicht wird. |
| `actionModuleInstall` | Wird bei der Installation des Moduls ausgeführt. | Wird verwendet, um die Datenbanktabelle `ps_slog` zu erstellen und notwendige Hooks zu registrieren. |
| `actionModuleUninstall` | Wird bei der Deinstallation des Moduls ausgeführt. | Wird zur Bereinigung verwendet (z. B. Löschen der `ps_slog`-Tabelle, Deregistrierung von Hooks). |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Entwickler-Support für das Modul „Suchprotokoll“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, Unterstützung zu leisten und sicherzustellen, dass das Modul optimal mit Ihrem PrestaShop-Shop funktioniert.

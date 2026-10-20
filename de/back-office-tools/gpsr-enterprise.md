---
title: "GPSR Enterprise - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul GPSR Enterprise von MyPresta.eu."
sidebar:
  label: "GPSR Enterprise"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul GPSR Enterprise auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/gpsr-enterprise.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/gpsr-enterprise/)
>
> ---


# GPSR Enterprise

## 1. Anforderungen & Kompatibilität

*   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
*   **PHP-Kompatibilität**: PHP 7.1 - 8.5
*   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich und in den meisten modernen Hosting-Umgebungen typischerweise verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das GPSR Enterprise Modul bietet einen umfassenden Satz von Konfigurationsoptionen, die sich über die Hauptkonfigurationsseite und mehrere dedizierte Verwaltungsbildschirme verteilen.

### 2.1 Modulkonfigurationsseite (Backoffice > Module > Modul-Manager > GPSR Enterprise > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie dessen allgemeines Verhalten und die Front-Office-Anzeige steuern.

*   **Modul aktiviert**
    *   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das gesamte GPSR Enterprise Modul.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert (Ja):* Das Modul ist aktiv, zeigt GPSR-Informationen auf Produktseiten an, ermöglicht die Verwaltung von Entitäten, Warnungen und Mappings und aktiviert die API und Cron-Jobs.
        *   *Wenn deaktiviert (Nein):* Das Modul ist vollständig inaktiv. Es werden keine GPSR-Informationen im Front-Office angezeigt, und Backend-Verwaltungsfunktionen sind nicht verfügbar oder nicht funktionsfähig.
    *   **Empfohlener Wert:** **Ja** (um die Funktionen des Moduls zu nutzen).
    *   **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal einrichten, lassen Sie es deaktiviert, bis alle Konfigurationen abgeschlossen sind, und aktivieren Sie es dann, um live zu gehen.

*   **Storefront-Theme-Profil**
    *   **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl des visuellen Styling-Profils für den GPSR-Informationsblock auf Ihren Produktseiten, optimiert für verschiedene PrestaShop-Themes.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn auf 'Classic' eingestellt:* Das Modul verwendet ein Styling, das für das Standard-PrestaShop Classic Theme (und viele kompatible Themes) optimiert ist.
        *   *Wenn auf 'Hummingbird' eingestellt:* Das Modul verwendet ein Styling, das für das neuere PrestaShop Hummingbird Theme (PrestaShop 8.1+) optimiert ist.
    *   **Empfohlener Wert:** Wählen Sie das Profil, das am besten zu Ihrem aktuellen PrestaShop-Theme passt. Wenn Sie unsicher sind, versuchen Sie zuerst 'Classic'.
    *   **Händlerszenario / Beispiel:** Wenn Ihr Shop PrestaShop 8.1+ mit dem Standard-Theme verwendet, wählen Sie 'Hummingbird' für die beste visuelle Integration. Wenn Sie PrestaShop 1.7 oder 8.0 mit dem Classic Theme verwenden, wählen Sie 'Classic'.

*   **Anzeigemodus**
    *   **Was diese Einstellung bewirkt:** Steuert, wie der GPSR-Informationsblock auf der Produktseite präsentiert wird.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Optionen variieren (z.B. 'Tab', 'Accordion', 'Block'):*
            *   **Tab:** Die GPSR-Informationen erscheinen als neuer Tab neben "Beschreibung", "Produktdetails" usw.
            *   **Accordion:** Die Informationen werden in einem erweiterbaren/einklappbaren Akkordeon-Abschnitt präsentiert.
            *   **Block:** Die Informationen werden als statischer Block innerhalb des Produktseiten-Inhaltsflusses angezeigt.
    *   **Empfohlener Wert:** **Tab** oder **Accordion** für ein saubereres Produktseitenlayout, insbesondere wenn Sie viele Informationen haben.
    *   **Händlerszenario / Beispiel:** Wenn Ihre Produktseiten bereits sehr lang sind, sorgt die Verwendung eines 'Tab'- oder 'Accordion'-Modus für eine aufgeräumte Seite, während die Informationen dennoch zugänglich bleiben.

*   **Visueller Stil**
    *   **Was diese Einstellung bewirkt:** Definiert die Gesamtästhetik des GPSR-Informationsblocks.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Optionen variieren (z.B. 'Standard', 'Minimal', 'Detailliert'):* Dies ändert die visuelle Dichte, die Verwendung von Symbolen und die allgemeine Präsentation der Informationen.
    *   **Empfohlener Wert:** **Standard** oder **Minimal** für ein sauberes Aussehen. Experimentieren Sie, um zu sehen, was am besten zu Ihrem Theme passt.
    *   **Händlerszenario / Beispiel:** Wenn Ihr Theme sehr minimalistisch ist, sorgt die Wahl eines 'Minimal'-Visualstils für den GPSR-Block für eine bessere Integration.

*   **Blocktitel anzeigen**
    *   **Was diese Einstellung bewirkt:** Legt fest, ob ein Titel über dem GPSR-Informationsblock auf der Produktseite angezeigt wird.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert (Ja):* Der in "Blocktiteltext" angegebene Text wird als Überschrift angezeigt.
        *   *Wenn deaktiviert (Nein):* Es wird kein Titel angezeigt, wodurch der Block nahtloser integriert wird oder sich auf den Kontext verlässt.
    *   **Empfohlener Wert:** **Ja** zur Klarheit, damit Kunden sofort verstehen, was der Block enthält.
    *   **Händlerszenario / Beispiel:** Wenn Sie dies mit einem Titel wie "Produktsicherheitsinformationen" aktivieren, wird den Kunden klar, was sie sehen.

*   **Blocktiteltext**
    *   **Was diese Einstellung bewirkt:** Ermöglicht die Anpassung des Titels des GPSR-Informationsblocks. Diese Einstellung gilt nur, wenn "Blocktitel anzeigen" aktiviert ist.
    *   **Auswirkungen einer Änderung dieser Einstellung:** Der hier eingegebene Text wird als Überschrift für den GPSR-Informationsblock auf der Produktseite angezeigt.
    *   **Empfohlener Wert:** Ein klarer, beschreibender Titel wie "Produktsicherheit & Konformität", "EU-Sicherheitsinformationen" oder "Produktdetails".
    *   **Händlerszenario / Beispiel:** Sie können dies auf "EU-Produktsicherheitsinformationen" setzen, um Ihren europäischen Kunden den Zweck des Blocks klar zu kommunizieren.

*   **Block ausblenden, wenn Daten unvollständig sind**
    *   **Was diese Einstellung bewirkt:** Steuert, ob der GPSR-Informationsblock auf der Produktseite angezeigt wird, wenn nicht alle erforderlichen Daten (Hersteller, EU-verantwortliche Person, Warnungen, Dokumente) für dieses Produkt vollständig konfiguriert wurden.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert (Ja):* Wenn GPSR-Daten für ein Produkt fehlen, wird der gesamte Block im Front-Office nicht angezeigt. Dies verhindert die Anzeige unvollständiger oder irreführender Informationen.
        *   *Wenn deaktiviert (Nein):* Der Block wird immer angezeigt, auch wenn einige Abschnitte leer sind. Dies könnte einen teilweise gefüllten Block anzeigen, was verwirrend sein könnte.
    *   **Empfohlener Wert:** **Ja**, um ein professionelles Erscheinungsbild zu wahren und die Anzeige halb leerer Abschnitte zu vermeiden.
    *   **Händlerszenario / Beispiel:** Sie sind noch dabei, GPSR-Daten zu all Ihren Produkten hinzuzufügen. Wenn Sie dies aktivieren, stellen Sie sicher, dass nur vollständig konforme Produktseiten den Block anzeigen, um Kundenverwirrung bei Produkten zu vermeiden, die noch aktualisiert werden.

*   **Hersteller-Entität anzeigen**
    *   **Was diese Einstellung bewirkt:** Legt fest, ob die GPSR-Entitätsdetails des Herstellers im Front-Office-Block angezeigt werden.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert (Ja):* Name, Adresse und andere konfigurierte Details des Herstellers werden sichtbar sein.
        *   *Wenn deaktiviert (Nein):* Der Herstellerbereich wird ausgeblendet.
    *   **Empfohlener Wert:** **Ja**, da dies eine zentrale GPSR-Anforderung ist.
    *   **Händlerszenario / Beispiel:** Um die GPSR vollständig einzuhalten, müssen Sie die Details des Herstellers anzeigen. Lassen Sie dies aktiviert.

*   **EU-verantwortliche Person anzeigen**
    *   **Was diese Einstellung bewirkt:** Legt fest, ob die GPSR-Entitätsdetails der EU-verantwortlichen Person im Front-Office-Block angezeigt werden.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert (Ja):* Name, Adresse und andere konfigurierte Details der EU-verantwortlichen Person werden sichtbar sein.
        *   *Wenn deaktiviert (Nein):* Der Bereich der EU-verantwortlichen Person wird ausgeblendet.
    *   **Empfohlener Wert:** **Ja**, da dies eine zentrale GPSR-Anforderung für in der EU verkaufte Produkte ist.
    *   **Händlerszenario / Beispiel:** Wenn Ihre Produkte eine EU-verantwortliche Person erfordern, stellt die Aktivierung sicher, dass deren Details angezeigt werden.

*   **Sicherheitshinweise anzeigen**
    *   **Was diese Einstellung bewirkt:** Legt fest, ob zugehörige Sicherheitshinweise im Front-Office-Block angezeigt werden.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert (Ja):* Konfigurierte Sicherheitshinweise für das Produkt werden sichtbar sein.
        *   *Wenn deaktiviert (Nein):* Der Bereich der Sicherheitshinweise wird ausgeblendet.
    *   **Empfohlener Wert:** **Ja**, um Kunden über potenzielle Gefahren zu informieren.
    *   **Händlerszenario / Beispiel:** Für Produkte mit spezifischen Sicherheitshinweisen (z.B. "Außer Reichweite von Kindern aufbewahren") stellt die Aktivierung sicher, dass diese Warnungen prominent angezeigt werden.

*   **Verknüpfte Dokumente anzeigen**
    *   **Was diese Einstellung bewirkt:** Legt fest, ob Links zu zugehörigen Dokumenten (wie Handbücher, Erklärungen) im Front-Office-Block angezeigt werden.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert (Ja):* Links zu hochgeladenen Dokumenten werden sichtbar sein.
        *   *Wenn deaktiviert (Nein):* Der Bereich der verknüpften Dokumente wird ausgeblendet.
    *   **Empfohlener Wert:** **Ja**, um Kunden wichtige Produktdokumentation zur Verfügung zu stellen.
    *   **Händlerszenario / Beispiel:** Wenn Sie eine "Konformitätserklärung" oder ein detailliertes Benutzerhandbuch bereitstellen müssen, ermöglicht die Aktivierung den Kunden einen einfachen Zugriff auf diese Dateien.

*   **Produktpass-Schaltfläche anzeigen**
    *   **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit der Schaltfläche "Produktpass herunterladen" auf der Produktseite.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert (Ja):* Eine Schaltfläche erscheint, die es Kunden ermöglicht, ein PDF mit allen GPSR-Informationen für das Produkt herunterzuladen.
        *   *Wenn deaktiviert (Nein):* Die Schaltfläche wird nicht angezeigt.
    *   **Empfohlener Wert:** **Ja**, da der Produktpass ein zentrales GPSR-Merkmal ist.
    *   **Händlerszenario / Beispiel:** Um Kunden eine umfassende, herunterladbare Zusammenfassung aller Sicherheits- und Konformitätsinformationen anzubieten, lassen Sie dies aktiviert.

*   **Mappings über alle Shops hinweg teilen**
    *   **Was diese Einstellung bewirkt:** (Nur in einer Multi-Store-Einrichtung sichtbar) Legt fest, ob GPSR-Mappings (wie Entitäten, Warnungen und Dokumente Produkten, Kategorien oder Herstellern zugewiesen werden) über alle Ihre PrestaShop-Shops hinweg geteilt werden.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert (Ja):* Alle von Ihnen erstellten GPSR-Mappings gelten für alle Shops in Ihrer Multi-Store-Umgebung. Dies vereinfacht die Verwaltung, wenn Ihr Produktkatalog und Ihre Compliance-Anforderungen in allen Shops ähnlich sind.
        *   *Wenn deaktiviert (Nein):* Jeder Shop hat seinen eigenen unabhängigen Satz von GPSR-Mappings, was shop-spezifische Compliance-Konfigurationen ermöglicht.
    *   **Empfohlener Wert:** **Ja**, wenn Ihre Compliance-Anforderungen in allen Shops konsistent sind; andernfalls **Nein**.
    *   **Händlerszenario / Beispiel:** Wenn Sie mehrere länderspezifische Shops betreiben, aber dieselben Produkte mit denselben Compliance-Anforderungen verkaufen, spart die Aktivierung viel Zeit, indem Sie Mappings einmal verwalten.

*   **Aktion beim Aktivieren der Freigabe**
    *   **Was diese Einstellung bewirkt:** (Nur in einer Multi-Store-Einrichtung sichtbar, erscheint, wenn "Mappings über alle Shops hinweg teilen" aktiviert ist) Definiert, was mit bestehenden shop-spezifischen Mappings geschieht, wenn Sie auf geteilte Mappings umstellen.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Optionen variieren (z.B. 'Zusammenführen', 'Überschreiben', 'Aktuellen Shop beibehalten'):*
            *   **Zusammenführen:** Versucht, bestehende Mappings aus allen Shops zu einem einzigen geteilten Satz zu kombinieren.
            *   **Überschreiben:** Ersetzt alle bestehenden shop-spezifischen Mappings durch die Mappings des aktuell aktiven Shops.
            *   **Aktuellen Shop beibehalten:** Verwendet die Mappings des aktuell aktiven Shops als geteilte Mappings und verwirft andere.
    *   **Empfohlener Wert:** Wählen Sie sorgfältig basierend auf Ihren Daten. **Sichern Sie Ihre Datenbank**, bevor Sie dies ändern!
    *   **Händlerszenario / Beispiel:** Wenn Sie GPSR-Daten bisher für jeden Shop separat verwaltet haben und nun zentralisieren möchten, müssen Sie entscheiden, ob Sie alle Daten kombinieren möchten oder ob die Daten eines Shops zum Master werden sollen.

*   **Aktion beim Deaktivieren der Freigabe**
    *   **Was diese Einstellung bewirkt:** (Nur in einer Multi-Store-Einrichtung sichtbar, erscheint, wenn "Mappings über alle Shops hinweg teilen" deaktiviert ist) Definiert, was mit den geteilten Mappings geschieht, wenn Sie wieder auf shop-spezifische Mappings umstellen.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Optionen variieren (z.B. 'In alle Shops duplizieren', 'Nur für aktuellen Shop beibehalten'):*
            *   **In alle Shops duplizieren:** Die aktuellen geteilten Mappings werden in jeden einzelnen Shop kopiert, sodass sie danach unabhängig bearbeitet werden können.
            *   **Nur für aktuellen Shop beibehalten:** Die geteilten Mappings werden nur dem aktuell aktiven Shop zugewiesen, und andere Shops beginnen ohne GPSR-Mappings.
    *   **Empfohlener Wert:** Wählen Sie sorgfältig basierend auf Ihren Daten. **Sichern Sie Ihre Datenbank**, bevor Sie dies ändern!
    *   **Händlerszenario / Beispiel:** Wenn Sie sich entscheiden, von geteilten Mappings wieder zur individuellen Shop-Verwaltung zurückzukehren, müssen Sie entscheiden, ob die geteilten Daten als Ausgangspunkt in alle Shops kopiert werden sollen oder ob nur der aktuelle Shop sie behalten soll.

*   **Benutzerdefiniertes CSS**
    *   **Was diese Einstellung bewirkt:** Bietet ein Textfeld, in dem Sie benutzerdefinierte CSS-Regeln hinzufügen können, um den GPSR-Informationsblock in Ihrem Shop weiter zu gestalten.
    *   **Auswirkungen einer Änderung dieser Einstellung:** Jeder hier eingegebene gültige CSS-Code wird auf die Front-Office-Elemente des GPSR-Moduls angewendet, sodass Sie Farben, Schriftarten, Abstände usw. feinabstimmen können, um perfekt zu Ihrem Theme zu passen.
    *   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Styling-Anforderungen und sind mit CSS vertraut.
    *   **Händlerszenario / Beispiel:** Ihr Theme verwendet einen bestimmten Blauton für Überschriften. Sie können hier CSS hinzufügen, um sicherzustellen, dass der GPSR-Blocktitel ebenfalls genau dieses Blau verwendet, um die visuelle Konsistenz zu wahren.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das GPSR Enterprise Modul fügt mehrere neue Menüpunkte unter einem Hauptmenü "GPSR Enterprise" in Ihrem PrestaShop-Backoffice hinzu. Diese Bildschirme sind der Ort, an dem Sie alle detaillierten Compliance-Daten verwalten.

#### 2.2.1 GPSR Enterprise Dashboard (Backoffice > GPSR Enterprise > Dashboard)

Dieser Bildschirm bietet einen Überblick über Ihren GPSR-Compliance-Status und schnellen Zugriff auf wichtige Verwaltungsbereiche.

*   **Verfügbare Aktionen & Einstellungen:**
    *   **Zusammenfassende Statistiken:** Zeigt möglicherweise die Anzahl der konfigurierten Entitäten, Warnungen, zugeordneten Produkte usw. an.
    *   **Schnelllinks:** Schaltflächen oder Links, um direkt zur Verwaltung von Entitäten, Warnungen, Mappings, Dokumenten usw. zu springen.
    *   **Cron-Job-Status:** Informationen über den letzten Lauf und das Ergebnis des GPSR-Cron-Jobs (für Re-Indizierung oder Datensynchronisation).
    *   **API-Token:** Zeigt Ihr eindeutiges API-Token für externe Integrationen an.
    *   **Cron-Token:** Zeigt Ihr eindeutiges Cron-Job-Token für die sichere Ausführung an.
*   **Auswirkungen von Änderungen:** Dieser Bildschirm dient hauptsächlich der Überwachung und Navigation. Änderungen hier (z.B. das Generieren neuer API-/Cron-Tokens) wirken sich direkt auf die Sicherheit und Funktionalität externer Integrationen und automatisierter Aufgaben aus.
*   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie dieses Dashboard regelmäßig, um Ihren Compliance-Status zu überwachen und sicherzustellen, dass Cron-Jobs korrekt ausgeführt werden.

#### 2.2.2 Entitäten (Backoffice > GPSR Enterprise > Entitäten)

Auf diesem Bildschirm definieren und verwalten Sie die von der GPSR geforderten "Entitäten", wie Hersteller und EU-verantwortliche Personen.

*   **Verfügbare Aktionen & Einstellungen:**
    *   **Entitätenliste:** Eine Tabelle, die alle konfigurierten Entitäten anzeigt, mit Spalten für Name, Typ (Hersteller, EU-verantwortliche Person), Adresse, Kontakt usw.
    *   **Neue Entität hinzufügen:** Eine Schaltfläche zum Erstellen einer neuen Entität.
    *   **Bearbeiten/Löschen:** Aktionen für jede Entität in der Liste.
    *   **Entitätsformular:** Beim Hinzufügen/Bearbeiten finden Sie Felder für:
        *   **Name:** Der offizielle Name der Entität.
        *   **Typ:** Wählen Sie, ob es sich um einen Hersteller oder eine EU-verantwortliche Person handelt.
        *   **Adresse:** Vollständige Postanschrift.
        *   **Kontaktinformationen:** E-Mail, Telefon, Website.
        *   **Mehrsprachige Felder:** Einige Felder können für verschiedene Sprachen übersetzbar sein.
*   **Auswirkungen von Änderungen:** Das Erstellen oder Aktualisieren von Entitäten hier macht sie für die Auswahl beim Zuordnen von GPSR-Daten zu Produkten verfügbar. Falsche oder unvollständige Entitätsdaten führen zu Nichtkonformität.
*   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Stellen Sie vor dem Zuordnen von Produkten sicher, dass alle Ihre Hersteller und EU-verantwortlichen Personen hier korrekt eingegeben sind. Aktualisieren Sie Details umgehend, wenn sie sich ändern.

#### 2.2.3 Warnungen (Backoffice > GPSR Enterprise > Warnungen)

Auf diesem Bildschirm können Sie verschiedene Sicherheitshinweise definieren und verwalten, die Ihren Produkten zugeordnet werden können.

*   **Verfügbare Aktionen & Einstellungen:**
    *   **Warnungsliste:** Eine Tabelle, die alle erstellten Warnungen anzeigt, mit Spalten für Titel, Symbol und Inhalt.
    *   **Neue Warnung hinzufügen:** Eine Schaltfläche zum Erstellen einer neuen Warnung.
    *   **Bearbeiten/Löschen:** Aktionen für jede Warnung in der Liste.
    *   **Warnungsformular:** Beim Hinzufügen/Bearbeiten finden Sie Felder für:
        *   **Titel:** Ein kurzer, beschreibender Titel für die Warnung.
        *   **Symbol:** Eine Option zur Auswahl eines visuellen Symbols, das die Warnung begleitet (z.B. ein Gefahrensymbol).
        *   **Inhalt:** Der vollständige Text des Sicherheitshinweises (mehrsprachig).
        *   **Schweregrad/Typ:** (Falls verfügbar) Kategorisieren Sie die Warnung.
*   **Auswirkungen von Änderungen:** Hier erstellte Warnungen werden für die Auswahl beim Zuordnen von GPSR-Daten zu Produkten verfügbar. Sie erscheinen dann auf der Front-Office-Produktseite.
*   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Erstellen Sie hier zuerst alle notwendigen Sicherheitshinweise. Stellen Sie sicher, dass der Inhalt für alle unterstützten Sprachen korrekt und rechtlich konform ist.

#### 2.2.4 Dokumente (Backoffice > GPSR Enterprise > Dokumente)

Dieser Bildschirm dient zum Hochladen und Verwalten von Dokumenten, die mit Produkten verknüpft werden müssen, wie z.B. Konformitätserklärungen, Benutzerhandbücher oder Sicherheitsdatenblätter.

*   **Verfügbare Aktionen & Einstellungen:**
    *   **Dokumentenliste:** Eine Tabelle, die hochgeladene Dokumente anzeigt, mit Spalten für Name, Dateityp und zugehörige Produkte.
    *   **Neues Dokument hochladen:** Eine Schaltfläche zum Hochladen einer neuen Datei.
    *   **Bearbeiten/Löschen:** Aktionen für jedes Dokument.
    *   **Dokumentenformular:** Beim Hochladen/Bearbeiten finden Sie Felder für:
        *   **Name:** Ein beschreibender Name für das Dokument (mehrsprachig).
        *   **Dateiupload:** Die eigentliche Datei (z.B. PDF).
        *   **Typ:** (Falls verfügbar) Kategorisieren Sie das Dokument (z.B. "Handbuch", "Erklärung").
*   **Auswirkungen von Änderungen:** Hochgeladene Dokumente werden für die Auswahl beim Zuordnen von GPSR-Daten zu Produkten verfügbar. Links zu diesen Dokumenten erscheinen auf der Front-Office-Produktseite.
*   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Laden Sie hier alle relevanten Produktdokumentationen hoch. Stellen Sie sicher, dass die Dokumente aktuell und korrekt benannt sind, um eine einfache Identifizierung zu ermöglichen.

#### 2.2.5 Mappings (Backoffice > GPSR Enterprise > Mappings)

Dies ist der Kern der Modulautomatisierung, der es Ihnen ermöglicht, zu definieren, wie GPSR-Daten Produkten basierend auf verschiedenen Kriterien zugewiesen werden. Dieser Abschnitt enthält wahrscheinlich mehrere Unterabschnitte für verschiedene Mapping-Typen.

*   **Verfügbare Aktionen & Einstellungen:**
    *   **Globale Mappings:** Wenden Sie GPSR-Daten standardmäßig auf alle Produkte an.
    *   **Kategorie-Mappings:** Wenden Sie GPSR-Daten auf alle Produkte innerhalb einer bestimmten Kategorie an.
    *   **Hersteller-Mappings:** Wenden Sie GPSR-Daten auf alle Produkte eines bestimmten Herstellers an.
    *   **Produkt-/Kombinations-Mappings:** Wenden Sie GPSR-Daten auf einzelne Produkte oder spezifische Produktkombinationen (Varianten) an.
    *   **Mapping-Formulare:** Für jeden Mapping-Typ konfigurieren Sie:
        *   **Zugewiesene Hersteller-Entität:** Wählen Sie eine im Abschnitt "Entitäten" definierte Entität aus.
        *   **Zugewiesene EU-verantwortliche Person-Entität:** Wählen Sie eine im Abschnitt "Entitäten" definierte Entität aus.
        *   **Zugewiesene Warnungen:** Wählen Sie eine oder mehrere im Abschnitt "Warnungen" definierte Warnungen aus.
        *   **Zugewiesene Dokumente:** Wählen Sie ein oder mehrere im Abschnitt "Dokumente" hochgeladene Dokumente aus.
        *   **Prioritäts-/Überschreibungsregeln:** (Falls verfügbar) Definieren Sie, wie Mappings von verschiedenen Ebenen (global, Kategorie, Hersteller, Produkt) interagieren und sich gegenseitig überschreiben.
*   **Auswirkungen von Änderungen:** Änderungen hier bestimmen direkt, welche GPSR-Informationen auf Ihren Produktseiten angezeigt werden. Eine gut strukturierte Mapping-Strategie reduziert den manuellen Aufwand erheblich.
*   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Beginnen Sie mit globalen Mappings und verfeinern Sie diese dann mit Kategorie- und Hersteller-Mappings. Verwenden Sie Produkt-/Kombinations-Mappings nur für Ausnahmen oder einzigartige Produkte. Überprüfen Sie Ihre Mappings regelmäßig, insbesondere wenn Sie neue Produkte oder Kategorien hinzufügen.

#### 2.2.6 Massenaktionen (Backoffice > GPSR Enterprise > Massenaktionen)

Dieser Bildschirm bietet Tools zum gleichzeitigen Anwenden von GPSR-Daten auf mehrere Produkte oder zum Ausführen von Massenvorgängen.

*   **Verfügbare Aktionen & Einstellungen:**
    *   **Produktraster:** Eine filterbare und durchsuchbare Liste von Produkten.
    *   **Massen-Zuweisung:** Wählen Sie mehrere Produkte aus und weisen Sie dann eine Hersteller-Entität, eine EU-verantwortliche Person, Warnungen oder Dokumente allen ausgewählten Produkten zu.
    *   **Massen-Entfernung:** Entfernen Sie GPSR-Daten von ausgewählten Produkten.
    *   **Import/Export:** (Falls verfügbar) Tools zum Importieren von GPSR-Daten aus einer CSV-Datei oder zum Exportieren vorhandener Daten.
*   **Auswirkungen von Änderungen:** Massenaktionen können GPSR-Daten für eine große Anzahl von Produkten schnell aktualisieren und so erhebliche Zeit sparen. Mit Vorsicht verwenden, da Änderungen breit angewendet werden.
*   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie dies nach der Ersteinrichtung, um gemeinsame GPSR-Daten schnell auf große Produktsätze anzuwenden. Auch nützlich zum Aktualisieren von Daten über viele Produkte hinweg, wenn sich eine Vorschrift ändert.

#### 2.2.7 Matcher (Backoffice > GPSR Enterprise > Matcher)

Dieser Bildschirm hilft, Produkte zu identifizieren, denen möglicherweise GPSR-Daten fehlen, oder schlägt potenzielle Mappings vor.

*   **Verwaltete Tabelle / Entität:** `gpsr_match_suggestion`
*   **Verfügbare Aktionen & Einstellungen:**
    *   **Vorschlagsliste:** Zeigt Produkte oder Produktgruppen an, die das Modul als potenziell GPSR-Daten benötigend oder unvollständige Daten aufweisend identifiziert.
    *   **Matching-Regeln:** (Falls verfügbar) Konfigurieren Sie Regeln, wie das Modul Übereinstimmungen vorschlägt (z.B. basierend auf Produktnamen-Keywords, vorhandenen Attributen).
    *   **Vorschläge anwenden/ablehnen:** Aktionen, um die vorgeschlagenen GPSR-Daten entweder anzuwenden oder den Vorschlag abzulehnen.
*   **Auswirkungen von Änderungen:** Das Anwenden von Vorschlägen aktualisiert die GPSR-Daten für die identifizierten Produkte. Dies hilft, eine umfassende Compliance sicherzustellen.
*   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie diesen Bildschirm regelmäßig, um Produkte zu finden, die möglicherweise durch Ihre Mapping-Strategie gerutscht sind.

#### 2.2.8 Audit-Log (Backoffice > GPSR Enterprise > Audit-Log)

Dieser Bildschirm bietet eine historische Aufzeichnung der Änderungen, die an GPSR-Daten innerhalb des Moduls vorgenommen wurden.

*   **Verwaltete Tabelle / Entität:** `gpsr_audit_log`
*   **Verfügbare Aktionen & Einstellungen:**
    *   **Log-Raster:** Eine Tabelle, die Einträge mit Details anzeigt wie:
        *   **Datum/Uhrzeit:** Wann die Änderung erfolgte.
        *   **Benutzer:** Welcher Administrator die Änderung vorgenommen hat.
        *   **Aktion:** Welche Aktion durchgeführt wurde (z.B. "Entität erstellt", "Produkt zugeordnet", "Warnung aktualisiert").
        *   **Details:** Spezifische Details der Änderung.
*   **Auswirkungen von Änderungen:** Dieser Bildschirm dient der Prüfung und Überwachung. Es werden hier keine direkten Änderungen an GPSR-Daten vorgenommen, aber er bietet eine entscheidende Aufzeichnung für die Rechenschaftspflicht und Fehlerbehebung.
*   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie dieses Protokoll, um Änderungen zu überprüfen, insbesondere wenn Sie mehrere Administratoren haben, die GPSR-Daten verwalten, oder wenn Sie Fehler beheben müssen, warum bestimmte Daten im Front-Office angezeigt werden (oder nicht angezeigt werden).

#### 2.2.9 Ledger (Backoffice > GPSR Enterprise > Ledger)

Dieser Bildschirm bietet wahrscheinlich eine detailliertere, "stille" Aufzeichnung aller auf Produkte angewendeten GPSR-Daten, möglicherweise einschließlich historischer Versionen oder eines umfassenden Überblicks für regulatorische Zwecke.

*   **Verfügbare Aktionen & Einstellungen:**
    *   **Produktzentrierte Ansicht:** Eine Möglichkeit, alle mit einem bestimmten Produkt verbundenen GPSR-Daten anzuzeigen, möglicherweise einschließlich der Art und Weise, wie sie abgeleitet wurden (z.B. aus einem Kategorie-Mapping oder direkt zugewiesen).
    *   **Exportoptionen:** (Falls verfügbar) Exportieren Sie das vollständige Ledger zur externen Überprüfung oder Archivierung.
*   **Auswirkungen von Änderungen:** Dieser Bildschirm dient hauptsächlich der Berichterstattung und detaillierten Überprüfung. Er ändert keine direkten Front-Office-Daten, liefert aber die zugrunde liegende Compliance-Aufzeichnung.
*   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie dies für detaillierte Compliance-Prüfungen oder bei der Vorbereitung auf behördliche Audits.

#### 2.2.10 API (Backoffice > GPSR Enterprise > API)

Dieser Bildschirm bietet Informationen und Einstellungen zur API des Moduls für externe Integrationen.

*   **Verfügbare Aktionen & Einstellungen:**
    *   **API-Token:** Zeigt das eindeutige Token an, das zur Authentifizierung von API-Anfragen erforderlich ist.
    *   **Neues Token generieren:** Eine Schaltfläche zum Generieren eines neuen API-Tokens (nützlich für die Sicherheit, wenn ein Token kompromittiert wurde).
    *   **API-Dokumentationslink:** Ein Link zur technischen Dokumentation für Entwickler zur Verwendung der API.
*   **Auswirkungen von Änderungen:** Das Generieren eines neuen Tokens macht das alte ungültig, sodass alle externen Systeme, die die API verwenden, mit dem neuen Token aktualisiert werden müssen.
*   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Greifen Sie nur darauf zu, wenn Sie das GPSR-Modul mit externen Systemen (z.B. ERP, PIM) integrieren. Bewahren Sie Ihr API-Token sicher auf.

#### 2.2.11 Cron (Backoffice > GPSR Enterprise > Cron)

Dieser Bildschirm verwaltet die geplanten Aufgaben des Moduls, wie z.B. die Neuindizierung von GPSR-Daten oder die Synchronisierung von Informationen.

*   **Verfügbare Aktionen & Einstellungen:**
    *   **Cron-Job-URL:** Die URL zum externen Auslösen des Cron-Jobs (z.B. über den Cron-Dienst Ihres Hosting-Anbieters).
    *   **Cron-Token:** Das eindeutige Token für die sichere Ausführung des Cron-Jobs.
    *   **Cron aktivieren/deaktivieren:** Ein Schalter zum Aktivieren oder Deaktivieren des Cron-Jobs.
    *   **Letzter Lauf/Ergebnis:** Informationen über den letzten Lauf des Cron-Jobs und dessen Ergebnis.
    *   **Re-Index-Einstellungen:** Optionen für die Häufigkeit und Anzahl der pro Lauf neu zu indizierenden Produkte (z.B. `GPSR_CRON_REINDEX_OFFSET`, `GPSR_CRON_REINDEX_LIMIT`).
*   **Auswirkungen von Änderungen:** Die Aktivierung des Cron-Jobs stellt sicher, dass GPSR-Daten regelmäßig im Hintergrund verarbeitet und aktualisiert werden, wodurch Ihre Front-Office-Informationen aktuell bleiben. Falsche Cron-Einstellungen können zu veralteten Daten oder Problemen mit der Serverlast führen.
*   **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Stellen Sie sicher, dass der Cron-Job aktiviert und auf Ihrem Hosting-Server korrekt konfiguriert ist, um die Datenverarbeitung zu automatisieren. Überwachen Sie seinen Status auf dem Dashboard.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :------------ | :--------------- | :-------------------- | :--------------- |
| **Modulkonfiguration** | Modul aktiviert | Ja | Hauptschalter für die Modulfunktionalität. |
| | Storefront-Theme-Profil | Passend zu Ihrem Theme | Optimiert die visuelle Gestaltung für Classic- oder Hummingbird-Themes. |
| | Anzeigemodus | Tab / Akkordeon | Wie der GPSR-Block erscheint (Tab, Akkordeon, Block). |
| | Visueller Stil | Standard / Minimal | Ästhetik des GPSR-Informationsblocks. |
| | Blocktitel anzeigen | Ja | Zeigt einen Titel über dem GPSR-Block an. |
| | Blocktiteltext | "Produktsicherheit & Konformität" | Benutzerdefinierter Text für den Blocktitel. |
| | Block ausblenden, wenn Daten unvollständig sind | Ja | Verhindert die Anzeige unvollständiger GPSR-Informationen. |
| | Hersteller-Entität anzeigen | Ja | Zeigt Herstellerdetails an. |
| | EU-verantwortliche Person anzeigen | Ja | Zeigt Details zur EU-verantwortlichen Person an. |
| | Sicherheitshinweise anzeigen | Ja | Zeigt Produktsicherheitshinweise an. |
| | Verknüpfte Dokumente anzeigen | Ja | Zeigt Links zu Produktdokumenten an. |
| | Produktpass-Schaltfläche anzeigen | Ja | Zeigt Schaltfläche zum Herunterladen des PDF-Produktpasses an. |
| | Mappings über alle Shops hinweg teilen | Ja (wenn Multi-Store) | Zentralisiert GPSR-Mappings für Multi-Store. |
| | Aktion beim Aktivieren der Freigabe | (Sorgfältige Wahl) | Definiert die Datenverarbeitung beim Aktivieren geteilter Mappings. |
| | Aktion beim Deaktivieren der Freigabe | (Sorgfältige Wahl) | Definiert die Datenverarbeitung beim Deaktivieren geteilter Mappings. |
| | Benutzerdefiniertes CSS | Leer | Fügt benutzerdefiniertes CSS für das Front-Office-Styling hinzu. |
| **Entitäten** | Entität hinzufügen/bearbeiten | N/A | Definiert Hersteller und EU-verantwortliche Personen. |
| **Warnungen** | Warnung hinzufügen/bearbeiten | N/A | Erstellt und verwaltet Sicherheitshinweise. |
| **Dokumente** | Dokument hochladen/verwalten | N/A | Lädt produktbezogene Dokumente hoch und verknüpft sie. |
| **Mappings** | Globale/Kategorie-/Hersteller-/Produkt-Mappings | N/A | Weist GPSR-Daten basierend auf Produktkriterien zu. |
| **Massenaktionen** | Massen-Zuweisung/-Entfernung | N/A | Wendet/entfernt GPSR-Daten für mehrere Produkte. |
| **Matcher** | Vorschläge überprüfen | N/A | Identifiziert Produkte, die GPSR-Daten benötigen. |
| **Audit-Log** | Protokoll anzeigen | N/A | Verfolgt Änderungen an GPSR-Daten. |
| **Ledger** | Daten anzeigen/exportieren | N/A | Umfassende Aufzeichnung der Produkt-GPSR-Daten. |
| **API** | API-Token, Neues Token generieren | N/A | Verwaltet den API-Zugriff für externe Integrationen. |
| **Cron** | Cron-Job-URL, Aktivieren/Deaktivieren | Aktiviert | Automatisiert die Hintergrundverarbeitung von GPSR-Daten. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe alles konfiguriert, aber der GPSR-Block wird auf meinen Produktseiten nicht angezeigt.**
A:
1.  **"Modul aktiviert" überprüfen:** Gehen Sie zu **Module > Modul-Manager > GPSR Enterprise > Konfigurieren** und stellen Sie sicher, dass "Modul aktiviert" auf "Ja" gesetzt ist.
2.  **"Block ausblenden, wenn Daten unvollständig sind" überprüfen:** Wenn dies auf "Ja" gesetzt ist, wird der Block nicht angezeigt, wenn für dieses spezifische Produkt erforderliche Daten (Hersteller, EU-verantwortliche Person, Warnungen, Dokumente) fehlen. Stellen Sie sicher, dass dem Produkt vollständige GPSR-Daten über Mappings oder direkte Produktbearbeitungen zugewiesen sind.
3.  **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf "Cache leeren" (oder "Smarty-Cache leeren" in älteren Versionen). Manchmal verhindert alter Cache-Inhalt, dass neue Modulelemente angezeigt werden.
4.  **Theme-Kompatibilität:** Stellen Sie sicher, dass Ihre Einstellung "Storefront-Theme-Profil" zu Ihrem Theme passt (Classic oder Hummingbird). Wenn Sie ein stark angepasstes Theme haben, kann es zu einem CSS-Konflikt kommen. Versuchen Sie, benutzerdefiniertes CSS hinzuzufügen, um die Sichtbarkeit zu erzwingen, oder wenden Sie sich an den Support.

**F: Mein GPSR-Informationsblock sieht seltsam oder falsch ausgerichtet auf meiner Website aus.**
A:
1.  **Theme-Profil:** Überprüfen Sie Ihre Einstellung "Storefront-Theme-Profil" in der Modulkonfiguration. Stellen Sie sicher, dass es auf das richtige Profil für Ihr PrestaShop-Theme (Classic oder Hummingbird) eingestellt ist.
2.  **Benutzerdefiniertes CSS:** Wenn Sie benutzerdefiniertes CSS in Ihrem Theme oder im Feld "Benutzerdefiniertes CSS" des Moduls haben, könnte es zu Konflikten kommen. Versuchen Sie, benutzerdefiniertes CSS vorübergehend zu entfernen, um zu sehen, ob das Problem behoben wird.
3.  **Browser-Cache:** Leeren Sie den Cache Ihres Browsers (Strg+F5 oder Cmd+R), um sicherzustellen, dass Sie das neueste Styling sehen.
4.  **Support kontaktieren:** Wenn das Problem weiterhin besteht, hat Ihr Theme möglicherweise ein einzigartiges Styling, das spezifische Anpassungen erfordert. Kontaktieren Sie den MyPresta.eu-Support mit Screenshots und Ihrem Theme-Namen.

**F: Wie stelle ich sicher, dass meine GPSR-Daten für internationale Kunden übersetzt werden?**
A:
1.  **Mehrsprachige Felder:** Stellen Sie beim Erstellen von **Entitäten** und **Warnungen** sicher, dass Sie den Inhalt für alle in Ihrem Shop aktivierten Sprachen ausfüllen. Achten Sie auf Sprachflaggen neben den Eingabefeldern.
2.  **PrestaShop-Übersetzungen:** Für die Standardphrasen des Moduls (wie "Produktpass herunterladen" oder den Blocktitel) gehen Sie zu **International > Übersetzungen**, wählen Sie "Übersetzungen installierter Module", wählen Sie "GPSR Enterprise" und wählen Sie Ihre Zielsprache. Übersetzen Sie dort alle fehlenden Phrasen.
3.  **Produktpass:** Der generierte PDF-Produktpass spiegelt die Sprache der von Ihnen eingegebenen Produktdaten und Warnungen wider.

**F: Der Cron-Job scheint nicht zu laufen, oder meine Daten werden nicht automatisch aktualisiert.**
A:
1.  **Cron aktiviert:** Stellen Sie im Bildschirm **Cron** des Moduls (Backoffice > GPSR Enterprise > Cron) sicher, dass der Cron-Job aktiviert ist.
2.  **Hosting-Cron-Setup:** Überprüfen Sie, ob Sie den Cron-Job auf Ihrem Hosting-Server korrekt mit der bereitgestellten "Cron-Job-URL" und dem "Cron-Token" eingerichtet haben. Dies geschieht normalerweise in Ihrem Hosting-Kontrollpanel (cPanel, Plesk usw.). Der Cron-Job muss regelmäßig ausgelöst werden (z.B. jede Stunde).
3.  **Status des letzten Laufs:** Überprüfen Sie "Letzter Lauf" und "Letztes Ergebnis" auf dem Cron-Bildschirm. Wenn Fehler angezeigt werden oder er in letzter Zeit nicht ausgeführt wurde, liegt ein Problem mit der Cron-Einrichtung oder ein serverseitiges Problem vor.
4.  **Server-Logs:** Überprüfen Sie die PHP-Fehlerprotokolle Ihres Servers auf Meldungen im Zusammenhang mit der Cron-Job-Ausführung.

**F: Ich habe bei einer Massenaktion einen Fehler gemacht, und jetzt haben viele Produkte falsche GPSR-Daten.**
A:
1.  **Audit-Log:** Überprüfen Sie sofort den **Audit-Log** (Backoffice > GPSR Enterprise > Audit-Log), um genau zu identifizieren, welche Änderungen von wem vorgenommen wurden.
2.  **Manuell/Über Massenaktionen rückgängig machen:** Je nach Ausmaß des Fehlers müssen Sie möglicherweise den Bildschirm **Massenaktionen** erneut verwenden, um die Daten zu korrigieren, oder einzelne Produkt-Mappings manuell bearbeiten, wenn nur wenige betroffen waren.
3.  **Datenbank-Backup:** Wenn der Fehler schwerwiegend und weit verbreitet ist und Sie ein aktuelles Datenbank-Backup von *vor* dem Fehler haben, könnte die Wiederherstellung dieses Backups die schnellste Lösung sein. Deshalb sind regelmäßige Backups so wichtig.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des GPSR Enterprise Moduls, gedacht für Entwickler, Webmaster und technische Agenturen.

### 4.1 Architekturübersicht

Das GPSR Enterprise Modul folgt dem MVC-Muster (Model-View-Controller) von PrestaShop, erweitert Kernfunktionen und führt benutzerdefinierte Entitäten ein. Es nutzt `ObjectModel` für Datenbankinteraktionen, `ModuleFrontController` für die Bereitstellung von Front-Office-Daten (API, Cron, Passgenerierung) und `AdminController` für die umfassende Back-Office-Verwaltung. Das Modul stützt sich stark auf Hooks für die Integration in Produktseiten und administrative Schnittstellen, um eine nicht-intrusive, aber leistungsstarke Lösung zu gewährleisten. Die Datenzuordnung ist hierarchisch und ermöglicht globale, kategorie-, hersteller- und produktspezifische Überschreibungen.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

*   `controllers/front/api.php`
    *   **Klassenname:** `GpsrEnterpriseApiModuleFrontController`
    *   **Elternklasse:** `ModuleFrontController`
    *   **Verantwortlichkeit:** Verarbeitet API-Anfragen für GPSR-Daten. Bietet Endpunkte für externe Systeme, um Produktsicherheitsinformationen, Entitäten, Warnungen und Dokumente abzufragen. Erfordert Authentifizierung über `GPSR_API_TOKEN`. Gibt JSON-Payloads zurück.
*   `controllers/front/cron.php`
    *   **Klassenname:** `GpsrEnterpriseCronModuleFrontController`
    *   **Elternklasse:** `ModuleFrontController`
    *   **Verantwortlichkeit:** Dient als Endpunkt für geplante Aufgaben (Cron-Jobs). Löst Hintergrundprozesse wie die Neuindizierung von GPSR-Daten, die Synchronisierung von Mappings oder die Datenbereinigung aus. Erfordert Authentifizierung über `GPSR_CRON_TOKEN`.
*   `controllers/front/data.php`
    *   **Klassenname:** `GpsrEnterpriseDataModuleFrontController`
    *   **Elternklasse:** `ModuleFrontController`
    *   **Verantwortlichkeit:** Bietet AJAX-Endpunkte zum dynamischen Abrufen von GPSR-Daten auf der Front-Office-Produktseite. Dieser Controller ruft wahrscheinlich den spezifischen Hersteller, die EU-verantwortliche Person, Warnungen und Dokumente für eine bestimmte Produkt-ID oder Kombinations-ID ab.
*   `controllers/front/index.php`
    *   **Klassenname:** `GpsrEnterpriseIndexModuleFrontController`
    *   **Elternklasse:** `ModuleFrontController`
    *   **Verantwortlichkeit:** Ein Platzhalter oder Fallback-Front-Controller. Wird oft für grundlegendes Modul-Routing oder zur Verhinderung von Verzeichnisauflistungen verwendet.
*   `controllers/front/passport.php`
    *   **Klassenname:** `GpsrEnterprisePassportModuleFrontController`
    *   **Elternklasse:** `ModuleFrontController`
    *   **Verantwortlichkeit:** Generiert und stellt den PDF-Produktpass für ein bestimmtes Produkt bereit. Es sammelt alle relevanten GPSR-Daten für das Produkt und rendert sie in ein herunterladbares PDF-Dokument.

#### Back-Office-Admin-Controller

Alle Admin-Controller erweitern `GpsrAdminController` (eine benutzerdefinierte Basisklasse innerhalb des Moduls), die wiederum `ModuleAdminController` erweitert.

*   `controllers/admin/AdminGpsrAuditController.php`
    *   **Tab-Name:** GPSR Enterprise > Audit-Log
    *   **Verwaltete Entität:** `GpsrAuditLogEntry`
    *   **Verantwortlichkeit:** Verwaltet die Anzeige und Filterung der Tabelle `gpsr_audit_log`, die alle wesentlichen Änderungen innerhalb des GPSR-Moduls aufzeichnet.
*   `controllers/admin/AdminGpsrController.php`
    *   **Tab-Name:** GPSR Enterprise (Haupteinstiegspunkt)
    *   **Verantwortlichkeit:** Dient wahrscheinlich als Haupt-Dashboard oder als Weiterleitung zum primären Konfigurations-/Dashboard-Bildschirm für das Modul.
*   `controllers/admin/AdminGpsrDocumentsController.php`
    *   **Tab-Name:** GPSR Enterprise > Dokumente
    *   **Verwaltete Entität:** `GpsrDocument` (impliziert, da keine spezifische Klasse aufgeführt wurde, aber Dokumente verwaltet)
    *   **Verantwortlichkeit:** Verwaltet das Hochladen, Auflisten und Verwalten von GPSR-bezogenen Dokumenten (z.B. PDFs).
*   `controllers/admin/AdminGpsrEnterpriseController.php`
    *   **Tab-Name:** GPSR Enterprise > Dashboard (oder Hauptkonfiguration)
    *   **Verantwortlichkeit:** Verwaltet die Hauptkonfigurationseinstellungen des Moduls, einschließlich API-/Cron-Tokens, globaler Anzeigeoptionen und Multi-Shop-Freigabe.
*   `controllers/admin/AdminGpsrEntitiesController.php`
    *   **Tab-Name:** GPSR Enterprise > Entitäten
    *   **Verwaltete Entität:** `GpsrEntity`
    *   **Verantwortlichkeit:** Verwaltet das Erstellen, Bearbeiten und Löschen von GPSR-Entitäten (Hersteller, EU-verantwortliche Personen).
*   `controllers/admin/AdminGpsrLedgerController.php`
    *   **Tab-Name:** GPSR Enterprise > Ledger
    *   **Verantwortlichkeit:** Bietet eine umfassende Ansicht und Verwaltungsoberfläche für das "stille Ledger" der GPSR-Daten, die mit Produkten verbunden sind, möglicherweise einschließlich historischer Daten.
*   `controllers/admin/AdminGpsrMapBrandsController.php`
    *   **Tab-Name:** GPSR Enterprise > Mappings > Marken
    *   **Verwaltete Entität:** `Manufacturer` (PrestaShop-Kern)
    *   **Verantwortlichkeit:** Verwaltet GPSR-Daten-Mappings basierend auf PrestaShop-Herstellern.
*   `controllers/admin/AdminGpsrMapCategoriesController.php`
    *   **Tab-Name:** GPSR Enterprise > Mappings > Kategorien
    *   **Verwaltete Entität:** `Category` (PrestaShop-Kern)
    *   **Verantwortlichkeit:** Verwaltet GPSR-Daten-Mappings basierend auf PrestaShop-Kategorien.
*   `controllers/admin/AdminGpsrMapCombinationsController.php`
    *   **Tab-Name:** GPSR Enterprise > Mappings > Kombinationen
    *   **Verwaltete Entität:** `ProductCombination` (impliziert)
    *   **Verantwortlichkeit:** Verwaltet GPSR-Daten-Mappings für spezifische Produktattributkombinationen.
*   `controllers/admin/AdminGpsrMapGlobalController.php`
    *   **Tab-Name:** GPSR Enterprise > Mappings > Global
    *   **Verantwortlichkeit:** Verwaltet globale GPSR-Daten-Mappings, die standardmäßig auf alle Produkte angewendet werden.
*   `controllers/admin/AdminGpsrMassController.php`
    *   **Tab-Name:** GPSR Enterprise > Massenaktionen
    *   **Verantwortlichkeit:** Bietet Tools für die Massenzuweisung und -entfernung von GPSR-Daten für mehrere Produkte.
*   `controllers/admin/AdminGpsrMatcherController.php`
    *   **Tab-Name:** GPSR Enterprise > Matcher
    *   **Verwaltete Entität:** `GpsrMatchSuggestion`
    *   **Verantwortlichkeit:** Verwaltet Vorschläge für Produkte, die möglicherweise GPSR-Daten benötigen oder unvollständige Mappings haben.
*   `controllers/admin/AdminGpsrWarningsController.php`
    *   **Tab-Name:** GPSR Enterprise > Warnungen
    *   **Verwaltete Entität:** `GpsrWarning`
    *   **Verantwortlichkeit:** Verwaltet das Erstellen, Bearbeiten und Löschen von Sicherheitshinweisen.
*   `controllers/admin/index.php`
    *   **Verantwortlichkeit:** Standardmäßige leere `index.php`-Datei von PrestaShop, um Verzeichnisauflistungen zu verhindern.

### 4.3 Kernklassen & Modelle (`classes/`)

*   `classes/GpsrAdminController.php`
    *   **Verantwortlichkeit:** Eine benutzerdefinierte Basisklasse für alle Admin-Controller innerhalb des GPSR-Moduls. Sie bietet wahrscheinlich gemeinsame Methoden, Eigenschaften und Template-Variablen, die über die Back-Office-Schnittstellen des Moduls hinweg verwendet werden, um Konsistenz zu gewährleisten und Code-Duplizierung zu reduzieren.
*   `classes/GpsrAuditLogEntry.php`
    *   **Erweitert:** `ObjectModel`
    *   **Datenbanktabelle:** `ps_gpsr_audit_log`
    *   **`$definition`-Felder:** `id_gpsr_audit_log`, `id_employee`, `action`, `object_type`, `object_id`, `details`, `date_add`
    *   **Wichtige öffentliche Methoden:** Methoden zum Protokollieren von Audit-Einträgen, Abrufen von Protokolldaten.
    *   **Geschäftslogik:** Zeichnet jede wichtige Aktion auf, die innerhalb des GPSR-Moduls für Auditing und Compliance durchgeführt wird.
*   `classes/GpsrCompatibility.php`
    *   **Verantwortlichkeit:** Verwaltet Kompatibilitätsschichten für verschiedene PrestaShop-Versionen (1.7.x, 8.x, 9.x). Diese Klasse enthält wahrscheinlich statische Methoden, um versionsspezifische Unterschiede in API-Aufrufen, Hook-Namen oder Template-Rendering zu abstrahieren und so sicherzustellen, dass das Modul nahtlos über unterstützte Versionen hinweg funktioniert.
*   `classes/GpsrEntity.php`
    *   **Erweitert:** `ObjectModel`
    *   **Datenbanktabelle:** `ps_gpsr_entity` (und `ps_gpsr_entity_lang` für mehrsprachige Felder)
    *   **`$definition`-Felder:** `id_gpsr_entity`, `type`, `name`, `address`, `contact_email`, `contact_phone`, `contact_website`, `active`, `date_add`, `date_upd` (und mehrsprachige Felder wie `name_lang`, `address_lang` usw.)
    *   **Wichtige öffentliche Methoden:** Methoden für CRUD-Operationen auf Entitäten, Abrufen von Entitäten nach Typ, Verknüpfen von Entitäten mit Produkten/Mappings.
    *   **Geschäftslogik:** Verwaltet die Daten für Hersteller und EU-verantwortliche Personen.
*   `classes/GpsrWarning.php`
    *   **Erweitert:** `ObjectModel`
    *   **Datenbanktabelle:** `ps_gpsr_warning` (und `ps_gpsr_warning_lang` für mehrsprachige Felder)
    *   **`$definition`-Felder:** `id_gpsr_warning`, `icon`, `active`, `date_add`, `date_upd` (und mehrsprachige Felder wie `title`, `content`)
    *   **Wichtige öffentliche Methoden:** Methoden für CRUD-Operationen auf Warnungen, Abrufen von Warnungen nach ID, Verknüpfen von Warnungen mit Produkten/Mappings.
    *   **Geschäftslogik:** Verwaltet die Daten für Sicherheitshinweise.
*   `classes/index.php`
    *   **Verantwortlichkeit:** Standardmäßige leere `index.php`-Datei von PrestaShop, um Verzeichnisauflistungen zu verhindern.

### 4.4 JavaScript-Assets (`views/js/`)

*   `gpsrenterprise/lib/searchTool/views/js/autocomplete.js`
    *   **Geltungsbereich:** Wahrscheinlich Back-Office.
    *   **Verantwortlichkeit:** Bietet Autocomplete-Funktionalität für Suchfelder innerhalb der Admin-Oberfläche, möglicherweise zur Auswahl von Produkten, Kategorien oder Entitäten in Mapping-Bildschirmen.
*   `gpsrenterprise/views/js/admin-api.js`
    *   **Geltungsbereich:** Back-Office (AdminGpsrEnterpriseController, API-Tab).
    *   **Verantwortlichkeit:** Handhabt AJAX-Interaktionen für den API-Konfigurationsbildschirm, wie das Generieren neuer API-Tokens oder das Anzeigen von API-Dokumentationsmodals.
*   `gpsrenterprise/views/js/admin-combination-map.js`
    *   **Geltungsbereich:** Back-Office (AdminGpsrMapCombinationsController).
    *   **Verantwortlichkeit:** Verwaltet die Benutzeroberfläche und AJAX-Aufrufe für das Mapping von GPSR-Daten zu spezifischen Produktkombinationen. Dies beinhaltet wahrscheinlich das dynamische Laden von Kombinationslisten und die Handhabung von Zuweisungen.
*   `gpsrenterprise/views/js/admin-combination-picker.js`
    *   **Geltungsbereich:** Back-Office (Produktseiten-Tab, Mapping-Formulare).
    *   **Verantwortlichkeit:** Bietet eine Benutzeroberflächenkomponente zur Auswahl von Produktkombinationen, die oft in Mapping-Formularen oder im Produktbearbeitungs-Tab verwendet wird.
*   `gpsrenterprise/views/js/admin-country-rules.js`
    *   **Geltungsbereich:** Back-Office (Potenziell innerhalb von Entitäts- oder Warnungsformularen).
    *   **Verantwortlichkeit:** Verwaltet die UI-Logik zum Anwenden von GPSR-Regeln basierend auf spezifischen Ländern, falls das Modul länderspezifische Compliance unterstützt.
*   `gpsrenterprise/views/js/admin-entity-picker.js`
    *   **Geltungsbereich:** Back-Office (Mapping-Formulare, Produktseiten-Tab).
    *   **Verantwortlichkeit:** Bietet eine Benutzeroberflächenkomponente zur Auswahl von `GpsrEntity`-Instanzen (Hersteller, EU-verantwortliche Personen) aus einem Dropdown-Menü oder einer Suchoberfläche.
*   `gpsrenterprise/views/js/admin-icon-picker-data.js`
    *   **Geltungsbereich:** Back-Office (Warnungsformulare).
    *   **Verantwortlichkeit:** Enthält Daten (z.B. ein Array von Symbolnamen/-pfaden), die von `admin-icon-picker.js` verwendet werden.
*   `gpsrenterprise/views/js/admin-icon-picker.js`
    *   **Geltungsbereich:** Back-Office (Warnungsformulare).
    *   **Verantwortlichkeit:** Implementiert eine Benutzeroberflächenkomponente zur visuellen Auswahl eines Symbols, das einer `GpsrWarning` zugeordnet werden soll.
*   `gpsrenterprise/views/js/admin-identifier-shortcodes.js`
    *   **Geltungsbereich:** Back-Office (Textbereiche in Formularen, z.B. für Produktpass-Vorlagen).
    *   **Verantwortlichkeit:** Bietet Funktionalität zum Einfügen vordefinierter "Shortcodes" oder Platzhalter in Textfelder, die beim Rendern dynamisch durch Produktdaten ersetzt werden.
*   `gpsrenterprise/views/js/admin-item-picker.js`
    *   **Geltungsbereich:** Back-Office (Allgemeine Mapping-Formulare).
    *   **Verantwortlichkeit:** Eine generische Benutzeroberflächenkomponente zur Auswahl verschiedener Elemente (Produkte, Kategorien, Dokumente, Warnungen) aus einer Liste oder Suche.
*   `gpsrenterprise/views/js/admin-mass-grid.js`
    *   **Geltungsbereich:** Back-Office (AdminGpsrMassController).
    *   **Verantwortlichkeit:** Verwaltet das interaktive Produktraster und die Massenaktionsfunktionalität auf dem Bildschirm "Massenaktionen".
*   `gpsrenterprise/views/js/admin-product-tab.js`
    *   **Geltungsbereich:** Back-Office (Produktbearbeitungsseite).
    *   **Verantwortlichkeit:** Fügt den benutzerdefinierten GPSR-Tab auf der PrestaShop-Produktbearbeitungsseite ein und verwaltet ihn, um die direkte Zuweisung von GPSR-Daten zu einzelnen Produkten zu ermöglichen.
*   `gpsrenterprise/views/js/adminGpsrDashboard.js`
    *   **Geltungsbereich:** Back-Office (AdminGpsrController/AdminGpsrEnterpriseController Dashboard).
    *   **Verantwortlichkeit:** Handhabt dynamische Elemente und AJAX-Updates auf dem Dashboard des Moduls, wie das Aktualisieren des Cron-Status oder das Anzeigen von Statistiken.
*   `gpsrenterprise/views/js/front.js`
    *   **Geltungsbereich:** Front-Office.
    *   **Verantwortlichkeit:** Haupt-JavaScript für den Front-Office-GPSR-Informationsblock. Handhabt das dynamische Laden von Daten (über den `data.php`-Controller), Tab-/Akkordeon-Funktionalität und potenziell Interaktionen mit der Produktpass-Schaltfläche.
*   `gpsrenterprise/views/js/gpsr-barcode.js`
    *   **Geltungsbereich:** Front-Office oder Back-Office (Produktpass-Generierung).
    *   **Verantwortlichkeit:** Wahrscheinlich ein Dienstprogramm-Skript zum Generieren oder Anzeigen von Barcodes, das möglicherweise im Produktpass-PDF oder zur Produktidentifikation verwendet wird.

### 4.5 CSS-Stylesheets (`views/css/`)

*   `gpsrenterprise/lib/searchTool/views/css/autocomplete.css`
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Stile für die Autocomplete-Suchfelder, die in der Admin-Oberfläche verwendet werden.
*   `gpsrenterprise/views/css/admin-api.css`
    *   **Geltungsbereich:** Back-Office (AdminGpsrEnterpriseController, API-Tab).
    *   **Verantwortlichkeit:** Stile speziell für die API-Konfiguration und Dokumentationsanzeige.
*   `gpsrenterprise/views/css/admin-combination-map.css`
    *   **Geltungsbereich:** Back-Office (AdminGpsrMapCombinationsController).
    *   **Verantwortlichkeit:** Stile für die Kombinations-Mapping-Oberfläche.
*   `gpsrenrterprise/views/css/admin-combination-picker.css`
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Stile für die Produktkombinationsauswahlkomponente.
*   `gpsrenterprise/views/css/admin-config.css`
    *   **Geltungsbereich:** Back-Office (Modulkonfigurationsseite).
    *   **Verantwortlichkeit:** Allgemeine Stile für das Hauptmodulkonfigurationsformular.
*   `gpsrenterprise/views/css/admin-country-rules.css`
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Stile für länderspezifische Regelkonfigurationsoberflächen.
*   `gpsrenterprise/views/css/admin-dashboard.css`
    *   **Geltungsbereich:** Back-Office (AdminGpsrController/AdminGpsrEnterpriseController Dashboard).
    *   **Verantwortlichkeit:** Stile für das administrative Dashboard des Moduls.
*   `gpsrenterprise/views/css/admin-help.css`
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Stile für Hilfetexte, Tooltips oder Dokumentationsabschnitte innerhalb des Admin-Bereichs.
*   `gpsrenterprise/views/css/admin-item-picker.css`
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Stile für die generische Elementauswahlkomponente.
*   `gpsrenterprise/views/css/admin-list-enhanced.css`
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Verbesserungen des Standard-PrestaShop-Listen-/Raster-Stylings für bessere Lesbarkeit oder Funktionalität.
*   `gpsrenterprise/views/css/admin-mass-grid.css`
    *   **Geltungsbereich:** Back-Office (AdminGpsrMassController).
    *   **Verantwortlichkeit:** Stile für das Produktraster der Massenaktionen.
*   `gpsrenterprise/views/css/admin-nav.css`
    *   **Geltungsbereich:** Back-Office.
    *   **Verantwortlichkeit:** Stile für die benutzerdefinierten Navigations-Tabs oder Menüpunkte des Moduls innerhalb des Admin-Bereichs.
*   `gpsrenterprise/views/css/admin-product-tab.css`
    *   **Geltungsbereich:** Back-Office (Produktbearbeitungsseite).
    *   **Verantwortlichkeit:** Stile für den GPSR-Tab, der der PrestaShop-Produktbearbeitungsseite hinzugefügt wurde.
*   `gpsrenterprise/views/css/front-classic.css`
    *   **Geltungsbereich:** Front-Office (Classic Theme).
    *   **Verantwortlichkeit:** Spezifisches Styling für den GPSR-Block, wenn das Theme-Profil "Classic" ausgewählt ist.
*   `gpsrenterprise/views/css/front-hummingbird.css`
    *   **Geltungsbereich:** Front-Office (Hummingbird Theme).
    *   **Verantwortlichkeit:** Spezifisches Styling für den GPSR-Block, wenn das Theme-Profil "Hummingbird" ausgewählt ist.
*   `gpsrenterprise/views/css/front.css`
    *   **Geltungsbereich:** Front-Office.
    *   **Verantwortlichkeit:** Allgemeine Basisstile für den GPSR-Informationsblock im Shop, die unabhängig vom Theme-Profil angewendet werden und dann möglicherweise von `front-classic.css` oder `front-hummingbird.css` überschrieben werden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

*   `gpsrenterprise/views/templates/hook/product-gpsr-classic.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (abhängig von der Konfiguration)
    *   **Ausgabe:** Der Haupt-GPSR-Informationsblock für die Front-Office-Produktseite, speziell für das Classic-Theme-Profil gestaltet.
*   `gpsrenterprise/views/templates/hook/product-gpsr-hummingbird.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (abhängig von der Konfiguration)
    *   **Ausgabe:** Der Haupt-GPSR-Informationsblock für die Front-Office-Produktseite, speziell für das Hummingbird-Theme-Profil gestaltet.
*   `gpsrenterprise/views/templates/hook/product-gpsr.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (abhängig von der Konfiguration)
    *   **Ausgabe:** Ein generisches oder Basis-Template für den GPSR-Informationsblock, das möglicherweise Logik enthält, um entweder die klassischen oder die Hummingbird-spezifischen Templates basierend auf der Modulkonfiguration zu laden.
*   `gpsrenterprise/views/templates/hook/_product-gpsr-attrs.tpl`
    *   **Hook:** Internes Teil-Template.
    *   **Ausgabe:** Rendert spezifische Attribute oder Details innerhalb des Haupt-GPSR-Produktblocks, wie z.B. einzelne Warnungen, Entitätsdetails oder Dokumentenlinks. Dies wird wahrscheinlich von `product-gpsr.tpl` oder seinen Theme-spezifischen Varianten eingebunden.

#### Admin-Templates (`views/templates/admin/`)

*   `gpsrenterprise/lib/searchTool/views/scripts.tpl`
    *   **Ausgabe:** Enthält JavaScript- oder Smarty-Logik für die Funktionalität des Suchwerkzeugs, wahrscheinlich in verschiedenen Admin-Seiten enthalten.
*   `gpsrenterprise/views/templates/admin/api.tpl`
    *   **Ausgabe:** Rendert den Inhalt für den API-Konfigurationsbildschirm, einschließlich Token-Anzeige, Generierungs-Schaltfläche und Dokumentationslink.
*   `gpsrenterprise/views/templates/admin/back-office.tpl`
    *   **Ausgabe:** Ein allgemeines Back-Office-Template, möglicherweise für das Hauptmodul-Dashboard oder einen Wrapper für andere Admin-Ansichten.
*   `gpsrenterprise/views/templates/admin/combination-list.tpl`
    *   **Ausgabe:** Zeigt eine Liste von Produktkombinationen an, die in Mapping- oder Picker-Oberflächen verwendet werden.
*   `gpsrenterprise/views/templates/admin/combination-picker.tpl`
    *   **Ausgabe:** Rendert die Benutzeroberfläche zur Auswahl von Produktkombinationen.
*   `gpsrenterprise/views/templates/admin/combination-script.tpl`
    *   **Ausgabe:** Enthält JavaScript, das spezifisch für die Kombinationsverwaltung ist, wahrscheinlich in Seiten enthalten, die sich mit Produktkombinationen befassen.
*   `gpsrenterprise/views/templates/admin/configure.tpl`
    *   **Ausgabe:** Rendert das Hauptmodulkonfigurationsformular (Zugriff über Module > Konfigurieren).
*   `gpsrenterprise/views/templates/admin/country-rules-panel.tpl`
    *   **Ausgabe:** Rendert ein Panel zur Verwaltung länderspezifischer GPSR-Regeln.
*   `gpsrenterprise/views/templates/admin/cron.tpl`
    *   **Ausgabe:** Rendert den Inhalt für den Cron-Job-Konfigurations- und Statusbildschirm.
*   `gpsrenterprise/views/templates/admin/dashboard.tpl`
    *   **Ausgabe:** Rendert das Haupt-Dashboard des Moduls mit Statistiken und Schnelllinks.
*   `gpsrenterprise/views/templates/admin/documents.tpl`
    *   **Ausgabe:** Rendert die Liste und Verwaltungsoberfläche für GPSR-Dokumente.
*   `gpsrenterprise/views/templates/admin/entities-list.tpl`
    *   **Ausgabe:** Zeigt die Liste der konfigurierten GPSR-Entitäten an.
*   `gpsrenterprise/views/templates/admin/entities.tpl`
    *   **Ausgabe:** Haupt-Wrapper-Template für den Entitäten-Verwaltungsbildschirm.
*   `gpsrenterprise/views/templates/admin/entity-form.tpl`
    *   **Ausgabe:** Rendert das Formular zum Hinzufügen oder Bearbeiten einer `GpsrEntity`.
*   `gpsrenterprise/views/templates/admin/entity-picker.tpl`
    *   **Ausgabe:** Rendert die Benutzeroberfläche zur Auswahl einer `GpsrEntity`.
*   `gpsrenterprise/views/templates/admin/getCombinations.tpl`
    *   **Ausgabe:** Ein Template, das wahrscheinlich für AJAX-Antworten verwendet wird, um Produktkombinationen dynamisch zu laden.
*   `gpsrenterprise/views/templates/admin/item-picker.tpl`
    *   **Ausgabe:** Rendert eine generische Benutzeroberflächenkomponente zur Auswahl von Elementen.
*   `gpsrenterprise/views/templates/admin/ledger.tpl`
    *   **Ausgabe:** Rendert die detaillierte GPSR-Ledger-Ansicht.
*   `gpsrenterprise/views/templates/admin/map-fields.tpl`
    *   **Ausgabe:** Ein Teil-Template, das gemeinsame Felder für GPSR-Mappings enthält (z.B. Entitätsselektoren, Warnungsselektoren).
*   `gpsrenterprise/views/templates/admin/map-form-category.tpl`
    *   **Ausgabe:** Rendert das Formular zum Erstellen/Bearbeiten von GPSR-Mappings auf Kategorieebene.
*   `gpsrenterprise/views/templates/admin/map-form-combination.tpl`
    *   **Ausgabe:** Rendert das Formular zum Erstellen/Bearbeiten von GPSR-Mappings auf Produktkombinationsebene.
*   `gpsrenterprise/views/templates/admin/map-form-global.tpl`
    *   **Ausgabe:** Rendert das Formular zum Erstellen/Bearbeiten globaler GPSR-Mappings.
*   `gpsrenterprise/views/templates/admin/map-form-manufacturer.tpl`
    *   **Ausgabe:** Rendert das Formular zum Erstellen/Bearbeiten von GPSR-Mappings auf Herstellerebene.
*   `gpsrenterprise/views/templates/admin/mappings.tpl`
    *   **Ausgabe:** Haupt-Wrapper-Template für den Mappings-Bereich, wahrscheinlich einschließlich Navigation für verschiedene Mapping-Typen.
*   `gpsrenterprise/views/templates/admin/mass-grid.tpl`
    *   **Ausgabe:** Rendert das Produktraster und die Massenaktionssteuerungen für den Bildschirm "Massenaktionen".
*   `gpsrenterprise/views/templates/admin/matcher.tpl`
    *   **Ausgabe:** Rendert die Oberfläche für den GPSR-Matcher, der Vorschläge anzeigt.
*   `gpsrenterprise/views/templates/admin/nav-tabs.tpl`
    *   **Ausgabe:** Rendert die Navigations-Tabs für die Back-Office-Bereiche des Moduls (Dashboard, Entitäten, Warnungen, Mappings usw.).
*   `gpsrenterprise/views/templates/admin/product-preview-card.tpl`
    *   **Ausgabe:** Rendert eine kleine Vorschaukarte für ein Produkt, möglicherweise in Picker-Komponenten oder Massenaktionsrastern verwendet.
*   `gpsrenterprise/views/templates/admin/product-tab.tpl`
    *   **Ausgabe:** Rendert den Inhalt des benutzerdefinierten GPSR-Tabs auf der PrestaShop-Produktbearbeitungsseite.
*   `gpsrenterprise/views/templates/admin/warning-form.tpl`
    *   **Ausgabe:** Rendert das Formular zum Hinzufügen oder Bearbeiten einer `GpsrWarning`.
*   `gpsrenterprise/views/templates/admin/warnings-list.tpl`
    *   **Ausgabe:** Zeigt die Liste der konfigurierten GPSR-Warnungen an.
*   `gpsrenterprise/views/templates/admin/_api_documentation_modal.tpl`
    *   **Ausgabe:** Rendert den Inhalt für ein modales Fenster, das die API-Dokumentation anzeigt.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

*   `ps_gpsr_audit_log`: Speichert Audit-Trail-Einträge für Änderungen, die innerhalb des Moduls vorgenommen wurden.
    *   `id_gpsr_audit_log` (PK)
    *   `id_employee` (FK zu `ps_employee`)
    *   `action` (z.B. 'add', 'edit', 'delete', 'map')
    *   `object_type` (z.B. 'entity', 'warning', 'product_mapping')
    *   `object_id`
    *   `details` (JSON oder Text für weitere Informationen)
    *   `date_add`
*   `ps_gpsr_entity`: Speichert Details für Hersteller und EU-verantwortliche Personen.
    *   `id_gpsr_entity` (PK)
    *   `type` (z.B. 'manufacturer', 'eu_responsible')
    *   `active`
    *   `date_add`, `date_upd`
*   `ps_gpsr_entity_lang`: Mehrsprachige Felder für `ps_gpsr_entity`.
    *   `id_gpsr_entity` (FK)
    *   `id_lang` (FK)
    *   `name`
    *   `address`
    *   `contact_email`
    *   `contact_phone`
    *   `contact_website`
*   `ps_gpsr_warning`: Speichert Definitionen von Sicherheitshinweisen.
    *   `id_gpsr_warning` (PK)
    *   `icon`
    *   `active`
    *   `date_add`, `date_upd`
*   `ps_gpsr_warning_lang`: Mehrsprachige Felder für `ps_gpsr_warning`.
    *   `id_gpsr_warning` (FK)
    *   `id_lang` (FK)
    *   `title`
    *   `content`
*   `ps_gpsr_document`: Speichert Details hochgeladener Dokumente.
    *   `id_gpsr_document` (PK)
    *   `filename`
    *   `mime_type`
    *   `file_size`
    *   `date_add`, `date_upd`
*   `ps_gpsr_document_lang`: Mehrsprachige Felder für `ps_gpsr_document` (z.B. `name`).
*   `ps_gpsr_product_mapping`: Direkte GPSR-Datenzuweisungen auf Produktebene.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK, für Kombinationen)
    *   `id_gpsr_entity_manufacturer` (FK zu `ps_gpsr_entity`)
    *   `id_gpsr_entity_eu_responsible` (FK zu `ps_gpsr_entity`)
    *   `date_add`, `date_upd`
*   `ps_gpsr_product_warning`: Verbindungstabelle für Produkt-Warnungs-Beziehungen.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK)
    *   `id_gpsr_warning` (FK)
*   `ps_gpsr_product_document`: Verbindungstabelle für Produkt-Dokument-Beziehungen.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK)
    *   `id_gpsr_document` (FK)
*   `ps_gpsr_category_mapping`: GPSR-Datenzuweisungen auf Kategorieebene.
    *   `id_category` (FK)
    *   `id_gpsr_entity_manufacturer`
    *   `id_gpsr_entity_eu_responsible`
*   `ps_gpsr_category_warning`: Verbindungstabelle für Kategorie-Warnungs-Beziehungen.
*   `ps_gpsr_category_document`: Verbindungstabelle für Kategorie-Dokument-Beziehungen.
*   `ps_gpsr_manufacturer_mapping`: GPSR-Datenzuweisungen auf Herstellerebene.
    *   `id_manufacturer` (FK)
    *   `id_gpsr_entity_manufacturer`
    *   `id_gpsr_entity_eu_responsible`
*   `ps_gpsr_manufacturer_warning`: Verbindungstabelle für Hersteller-Warnungs-Beziehungen.
*   `ps_gpsr_manufacturer_document`: Verbindungstabelle für Hersteller-Dokument-Beziehungen.
*   `ps_gpsr_global_mapping`: Speichert globale Standard-GPSR-Daten.
*   `ps_gpsr_match_suggestion`: Speichert vom Matcher generierte Vorschläge.
    *   `id_gpsr_match_suggestion` (PK)
    *   `id_product`
    *   `suggestion_type`
    *   `suggested_data` (JSON)
    *   `date_add`
*   `ps_configuration`: Moduleinstellungen werden hier mit Schlüsseln wie `GPSR_ENABLED`, `GPSR_CUSTOM_CSS`, `GPSR_API_TOKEN`, `GPSR_CRON_TOKEN` usw. gespeichert.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| :-------- | :--------------- | :---------------- |
| `actionProductSave` | Nach dem Speichern eines Produkts (Hinzufügen oder Aktualisieren). | Löst die Neubewertung der GPSR-Daten für das Produkt aus, aktualisiert Mappings oder protokolliert Änderungen. |
| `actionAfterUpdateProductFormHandler` | Nach der Aktualisierung eines Produktformulars im BO. | Aktualisiert die im Produkt-Tab angezeigten GPSR-Daten oder löst verwandte Updates aus. |
| `actionObjectProductDeleteAfter` | Nach dem Löschen eines Produktobjekts. | Bereinigt zugehörige GPSR-Daten und Mappings für das gelöschte Produkt. |
| `actionAfterCreateProductFormHandler` | Nach dem Erstellen eines Produktformulars im BO. | Initialisiert GPSR-Daten für ein neues Produkt, wendet möglicherweise Standard-Mappings an. |
| `displayAfterProductThumbs` | Auf der Produktseite, nach den Produktbildern. | Rendert den Front-Office-GPSR-Informationsblock. (Platzierung hängt von Theme/Konfiguration ab) |
| `actionObjectProductAddAfter` | Nach dem Hinzufügen eines neuen Produktobjekts. | Löst die anfängliche GPSR-Datenzuweisung für das neue Produkt aus. |
| `displayProductAdditionalInfo` | Auf der Produktseite, im Abschnitt "Zusätzliche Informationen". | Rendert den Front-Office-GPSR-Informationsblock, oft als Tab. |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back-Office. | Fügt den benutzerdefinierten GPSR-Tab für die produktspezifische Datenverwaltung ein. |
| `displayBackOfficeHeader` | Im Header jeder Back-Office-Seite. | Lädt modulspezifisches CSS/JS für Admin-Oberflächen, fügt Menüpunkte hinzu. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Medien (CSS/JS) festlegt. | Lädt modulspezifisches CSS/JS für relevante Admin-Seiten. |
| `displayProductExtraContent` | Auf der Produktseite, für zusätzliche Inhaltsblöcke. | Rendert den Front-Office-GPSR-Informationsblock und bietet flexible Platzierung. |
| `displayFooterProduct` | Im Fußbereich der Produktseite. | Rendert den Front-Office-GPSR-Informationsblock, oft als Block unter dem Hauptinhalt. |
| `displayReassurance` | Im Produkt-Reassurance-Block (z.B. kostenloser Versand, sichere Zahlung). | Rendert den Front-Office-GPSR-Informationsblock, möglicherweise als kleines, beruhigendes Abzeichen oder Link. |
| `actionProductAttributeUpdate` | Nach der Aktualisierung einer Produktkombination (Attribut). | Löst die Neubewertung der GPSR-Daten für die spezifische Kombination aus. |
| `actionFrontControllerSetMedia` | Wenn ein Front-Controller seine Medien (CSS/JS) festlegt. | Lädt modulspezifisches CSS/JS für Front-Office-Seiten, auf denen GPSR-Daten angezeigt werden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das GPSR Enterprise Modul besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Fragen oder Problemen bezüglich der Funktionalität oder Integration des Moduls gerne zur Verfügung.

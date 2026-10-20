---
title: "LLMS.txt Generator Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul LLMS.txt Generator Pro von MyPresta.eu."
sidebar:
  label: "LLMS.txt Generator Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul LLMS.txt Generator Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/seo/llmstxt-generator-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/seo/llmstxt-generator-pro/)
>
> ---


# LLMS.txt Generator Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Ihr Server muss auch das Schreiben von Dateien in das Stammverzeichnis zulassen, damit die `llms.txt`-Datei generiert werden kann.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > LLMS.txt Generator Pro)

Dies ist das Hauptkontrollfeld für Ihr LLMS.txt Generator Pro-Modul. Hier definieren Sie, wie Ihre `llms.txt`-Datei generiert wird und welche Inhalte sie enthält.

#### Allgemeine Einstellungen

- **LLMS.txt-Generierung aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul generiert und stellt die `llms.txt`-Datei gemäß Ihren Einstellungen bereit. KI-Crawler können darauf zugreifen.
    - *Wenn deaktiviert:* Die `llms.txt`-Datei wird vom Modul nicht generiert oder bereitgestellt. KI-Crawler erhalten keine spezifische Anleitung von Ihrem Shop.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten beginnen, KI-Bots zu leiten. Aktivieren Sie dies. Wenn Sie die KI-Anleitung für Wartungsarbeiten vorübergehend stoppen müssen, können Sie sie hier deaktivieren.
- **LLMS.txt-Dateityp:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob die `llms.txt`-Datei als statische Datei (auf Ihren Server geschrieben) oder dynamisch bei Bedarf bereitgestellt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Statisch:* Das Modul schreibt eine physische `llms.txt`-Datei in das Stammverzeichnis Ihres Shops. Dies ist für KI-Bots im Allgemeinen schneller, da es bei jeder Anfrage keine PHP-Verarbeitung erfordert.
    - *Dynamisch:* Die `llms.txt`-Datei wird jedes Mal, wenn ein KI-Bot sie anfordert, vom PHP-Code von PrestaShop generiert. Dies gewährleistet die aktuellsten Inhalte, kann aber etwas langsamer sein.
  - **Empfohlener Wert:** Statisch (für die Leistung, es sei denn, Sie haben häufige, Echtzeit-Inhaltsänderungen, die sofort widergespiegelt werden müssen).
  - **Händlerszenario / Beispiel:** Für die meisten Shops ist statisch in Ordnung. Wenn Sie einen Shop mit sehr hohem Traffic und ständig wechselnden Produktpreisen oder Lagerbeständen haben, könnte dynamisch bevorzugt werden, aber berücksichtigen Sie die Leistungsauswirkungen.
- **llms-full.txt generieren:**

  - **Was diese Einstellung bewirkt:** Steuert, ob eine zusätzliche, umfassendere `llms-full.txt`-Datei ebenfalls generiert wird. Diese Datei enthält typischerweise detailliertere oder weniger eingeschränkte Informationen als die Standard-`llms.txt`.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine `llms-full.txt`-Datei wird neben `llms.txt` erstellt und bietet KI-Crawlern einen reichhaltigeren Datensatz.
    - *Wenn deaktiviert:* Nur die Standard-`llms.txt`-Datei wird generiert.
  - **Empfohlener Wert:** JA (um KI maximale Daten zur Verfügung zu stellen, es sei denn, Sie haben spezifische Gründe, diese einzuschränken).
  - **Händlerszenario / Beispiel:** Sie möchten, dass KI-Modelle Zugriff auf so viele relevante Informationen wie möglich über Ihre Produkte haben, einschließlich potenziell weniger kritischer, aber dennoch nützlicher Details.
- **Produktseiten einschließen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob einzelne Produktseiten in der `llms.txt`-Datei aufgeführt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* URLs für alle Ihre aktiven Produktseiten werden aufgenommen, wodurch sie für KI auffindbar werden.
    - *Wenn deaktiviert:* Produktseiten werden ausgeschlossen, was bedeutet, dass KI-Bots über `llms.txt` nicht explizit zu ihnen geleitet werden.
  - **Empfohlener Wert:** JA (Produkte sind in der Regel der Kern eines E-Commerce-Shops).
  - **Händlerszenario / Beispiel:** Sie möchten, dass KI Kunden hilft, bestimmte Produkte zu finden.
- **Kategorieseiten einschließen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob Kategorieseiten (die Produktgruppen auflisten) in der `llms.txt`-Datei aufgeführt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* URLs für alle Ihre aktiven Kategorieseiten werden aufgenommen.
    - *Wenn deaktiviert:* Kategorieseiten werden ausgeschlossen.
  - **Empfohlener Wert:** JA (Kategorien helfen KI, die Struktur Ihres Shops zu verstehen).
  - **Händlerszenario / Beispiel:** Sie möchten, dass KI die verschiedenen Arten von Produkten versteht, die Sie verkaufen, und Kunden zu relevanten Abschnitten leitet.
- **CMS-Seiten einschließen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob Ihre Content-Management-System (CMS)-Seiten (z. B. Über uns, Kontakt, Versandinformationen, Datenschutzrichtlinie) aufgeführt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* URLs für aktive CMS-Seiten werden aufgenommen.
    - *Wenn deaktiviert:* CMS-Seiten werden ausgeschlossen.
  - **Empfohlener Wert:** JA (Wichtig für KI, um Ihr Geschäft und Ihre Richtlinien zu verstehen).
  - **Händlerszenario / Beispiel:** Sie möchten, dass KI Fragen zu den Richtlinien oder der Geschichte Ihres Shops beantworten kann.
- **Hersteller-/Markenseiten einschließen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob Seiten, die bestimmten Herstellern oder Marken gewidmet sind, aufgeführt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* URLs für aktive Hersteller-/Markenseiten werden aufgenommen.
    - *Wenn deaktiviert:* Hersteller-/Markenseiten werden ausgeschlossen.
  - **Empfohlener Wert:** JA (Wenn Marken für Ihr Produktangebot wichtig sind).
  - **Händlerszenario / Beispiel:** Sie verkaufen Produkte bekannter Marken und möchten, dass KI dies erkennt.
- **Lieferantenseiten einschließen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob Seiten, die bestimmten Lieferanten gewidmet sind, aufgeführt werden. (Weniger üblich für die Front-Office-Sichtbarkeit, oft für interne Zwecke verwendet).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* URLs für aktive Lieferantenseiten werden aufgenommen.
    - *Wenn deaktiviert:* Lieferantenseiten werden ausgeschlossen.
  - **Empfohlener Wert:** NEIN (Es sei denn, Sie bewerben Lieferanten explizit in Ihrem Front-Office).
  - **Händlerszenario / Beispiel:** Sie haben ein einzigartiges Geschäftsmodell, bei dem Lieferanten öffentlich sichtbar sind und Sie möchten, dass KI sie indexiert.
- **Seite „Neue Produkte“ einschließen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob die Auflistungsseite „Neue Produkte“ aufgenommen wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die URL für die Seite „Neue Produkte“ wird aufgenommen.
    - *Wenn deaktiviert:* Die Seite „Neue Produkte“ wird ausgeschlossen.
  - **Empfohlener Wert:** JA (Um Ihre neuesten Angebote für KI hervorzuheben).
  - **Händlerszenario / Beispiel:** Sie fügen häufig neue Produkte hinzu und möchten, dass KI schnell darauf aufmerksam wird.
- **Seite „Beste Verkäufe“ einschließen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob die Auflistungsseite „Beste Verkäufe“ oder „Top-Seller“ aufgenommen wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die URL für die Seite „Beste Verkäufe“ wird aufgenommen.
    - *Wenn deaktiviert:* Die Seite „Beste Verkäufe“ wird ausgeschlossen.
  - **Empfohlener Wert:** JA (Um Ihre beliebtesten Artikel zu bewerben).
  - **Händlerszenario / Beispiel:** Sie möchten, dass KI Ihren Kunden Ihre meistverkauften Artikel empfiehlt.
- **Seite „Preissenkungen“ einschließen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob die Auflistungsseite „Preissenkungen“ oder „Im Angebot“ aufgenommen wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die URL für die Seite „Preissenkungen“ wird aufgenommen.
    - *Wenn deaktiviert:* Die Seite „Preissenkungen“ wird ausgeschlossen.
  - **Empfohlener Wert:** JA (Um Ihre reduzierten Artikel hervorzuheben).
  - **Händlerszenario / Beispiel:** Sie führen Aktionen durch und möchten, dass KI Kunden über aktuelle Angebote informiert.
- **Kontaktseite einschließen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob die Kontaktseite Ihres Shops aufgenommen wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die URL für die Kontaktseite wird aufgenommen.
    - *Wenn deaktiviert:* Die Kontaktseite wird ausgeschlossen.
  - **Empfohlener Wert:** JA (Wichtig für KI, um Kundendienstinformationen bereitzustellen).
  - **Händlerszenario / Beispiel:** Sie möchten, dass KI Kunden mitteilen kann, wie sie Ihr Support-Team erreichen können.
- **Sitemap-Seite einschließen:**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob die Haupt-Sitemap-Seite Ihres Shops (falls vorhanden) aufgenommen wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die URL für die Sitemap-Seite wird aufgenommen.
    - *Wenn deaktiviert:* Die Sitemap-Seite wird ausgeschlossen.
  - **Empfohlener Wert:** JA (Kann KI helfen, mehr Inhalte zu entdecken, ähnlich wie Suchmaschinen-Sitemaps).
  - **Händlerszenario / Beispiel:** Sie möchten KI einen umfassenden Überblick über die Struktur Ihres Shops geben.
- **Benutzerdefinierte URLs einschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, manuell spezifische URLs hinzuzufügen, die nicht automatisch von PrestaShop generiert werden, die Sie aber dennoch von KI entdeckt haben möchten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Textbereich wird angezeigt, in dem Sie eine URL pro Zeile auflisten können. Diese URLs werden Ihrer `llms.txt`-Datei hinzugefügt.
    - *Wenn deaktiviert:* Es werden keine benutzerdefinierten URLs hinzugefügt.
  - **Empfohlener Wert:** JA (Wenn Sie wichtige statische Seiten oder Blogbeiträge außerhalb der Kernstruktur von PrestaShop haben).
  - **Händlerszenario / Beispiel:** Sie haben einen separaten Blog auf einer Subdomain oder spezifische Landing Pages, die Sie von KI indexieren lassen möchten.
- **Spezifische URLs ausschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, manuell URLs anzugeben, die *nicht* in der `llms.txt`-Datei enthalten sein sollen, auch wenn sie sonst generiert würden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Textbereich wird angezeigt, in dem Sie eine URL pro Zeile auflisten können. Diese URLs werden explizit ausgeschlossen.
    - *Wenn deaktiviert:* Es werden keine URLs explizit durch diese Einstellung ausgeschlossen.
  - **Empfohlener Wert:** Bei Bedarf für sensible oder irrelevante Seiten verwenden.
  - **Händlerszenario / Beispiel:** Sie haben interne Testseiten, veraltete Aktionen oder sensible Kundendaten-Seiten, auf die KI absolut keinen Zugriff haben soll.
- **Produkte nach Kategorie ausschließen:**

  - **Was diese Einstellung bewirkt:** Bietet eine Möglichkeit, alle Produkte, die zu bestimmten Kategorien gehören, aus der `llms.txt`-Datei auszuschließen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine Liste Ihrer Kategorien wird angezeigt, sodass Sie auswählen können, welche ausgeschlossen werden sollen. Alle Produkte innerhalb der ausgewählten Kategorien werden weggelassen.
    - *Wenn deaktiviert:* Alle Produkte werden für die Aufnahme berücksichtigt, unabhängig von der Kategorie.
  - **Empfohlener Wert:** Bei Bedarf verwenden.
  - **Händlerszenario / Beispiel:** Sie verkaufen sowohl öffentliche Produkte als auch eine Reihe von B2B-Produkten in einer bestimmten Kategorie, die Sie nicht von KI für die allgemeine öffentliche Suche indexieren lassen möchten.
- **Produkte nach Hersteller ausschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, alle Produkte bestimmter Hersteller auszuschließen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine Liste Ihrer Hersteller wird zur Auswahl angezeigt. Produkte ausgewählter Hersteller werden weggelassen.
    - *Wenn deaktiviert:* Alle Produkte werden für die Aufnahme berücksichtigt, unabhängig vom Hersteller.
  - **Empfohlener Wert:** Bei Bedarf verwenden.
  - **Händlerszenario / Beispiel:** Sie haben den Verkauf von Produkten einer bestimmten Marke vorübergehend eingestellt und möchten nicht, dass KI diese anzeigt, auch wenn sie noch in Ihrem Katalog sind.
- **Produkte nach Lieferant ausschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, alle Produkte bestimmter Lieferanten auszuschließen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine Liste Ihrer Lieferanten wird zur Auswahl angezeigt. Produkte ausgewählter Lieferanten werden weggelassen.
    - *Wenn deaktiviert:* Alle Produkte werden für die Aufnahme berücksichtigt, unabhängig vom Lieferanten.
  - **Empfohlener Wert:** Bei Bedarf verwenden.
  - **Händlerszenario / Beispiel:** Sie haben einen Lieferanten, dessen Produkte nicht für die öffentliche KI-Indexierung bestimmt sind.
- **Produkte nach Merkmal ausschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte basierend auf spezifischen Produktmerkmalen auszuschließen (z. B. „Farbe: Rot“, „Material: Holz“).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sie können Merkmale und deren Werte auswählen. Produkte, die diesen Merkmalen entsprechen, werden weggelassen.
    - *Wenn deaktiviert:* Produktmerkmale werden nicht für den Ausschluss verwendet.
  - **Empfohlener Wert:** Bei Bedarf verwenden.
  - **Händlerszenario / Beispiel:** Sie haben Produkte mit dem Merkmal „Auslaufmodell“ gekennzeichnet, die Sie vor KI verbergen möchten.
- **Produkte nach Attribut ausschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte basierend auf spezifischen Produktattributen auszuschließen (z. B. „Größe: XL“, „Gewicht: 1kg“).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sie können Attribute und deren Werte auswählen. Produkte, die diesen Attributen entsprechen, werden weggelassen.
    - *Wenn deaktiviert:* Produktattribute werden nicht für den Ausschluss verwendet.
  - **Empfohlener Wert:** Bei Bedarf verwenden.
  - **Händlerszenario / Beispiel:** Sie haben Produkte mit einer Attributkombination „Nicht auf Lager“, die Sie nicht von KI anzeigen lassen möchten.
- **Produkte nach Preisspanne ausschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte auszuschließen, die in eine angegebene Preisspanne fallen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sie können einen Mindest- und Höchstpreis eingeben. Produkte mit Preisen innerhalb dieser Spanne werden weggelassen.
    - *Wenn deaktiviert:* Produktpreise werden nicht für den Ausschluss verwendet.
  - **Empfohlener Wert:** Bei Bedarf verwenden.
  - **Händlerszenario / Beispiel:** Sie möchten, dass KI nur Ihre Premium-Produkte indexiert (z. B. Produkte unter 10 $ ausschließen).
- **Produkte nach Lagerbestand ausschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte basierend auf ihrer aktuellen Lagerbestandsmenge auszuschließen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sie können eine Mindestlagerbestandsmenge festlegen. Produkte mit einem Lagerbestand unter dieser Menge werden weggelassen.
    - *Wenn deaktiviert:* Die Produktlagerbestandsmenge wird nicht für den Ausschluss verwendet.
  - **Empfohlener Wert:** JA (Produkte mit 0 Lagerbestand ausschließen, um zu vermeiden, dass KI nicht verfügbare Artikel empfiehlt).
  - **Händlerszenario / Beispiel:** Sie möchten nicht, dass KI Produkte anzeigt, die nicht auf Lager sind. Stellen Sie dies so ein, dass Produkte mit einem Lagerbestand <= 0 ausgeschlossen werden.
- **Produkte nach Sichtbarkeit ausschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte basierend auf ihrer PrestaShop-Sichtbarkeitseinstellung auszuschließen (z. B. „Nur Katalog“, „Nur Suche“, „Überall“).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sie können auswählen, welche Sichtbarkeitsoptionen ausgeschlossen werden sollen. Produkte, die diesen entsprechen, werden weggelassen.
    - *Wenn deaktiviert:* Die Produktsichtbarkeit wird nicht für den Ausschluss verwendet.
  - **Empfohlener Wert:** Bei Bedarf verwenden.
  - **Händlerszenario / Beispiel:** Sie haben Produkte auf „Nur Katalog“ (nicht durchsuchbar) eingestellt, die Sie auch vor KI verbergen möchten.
- **Produkte nach Status ausschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte basierend auf ihrem aktiven/inaktiven Status auszuschließen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sie können wählen, inaktive Produkte auszuschließen.
    - *Wenn deaktiviert:* Sowohl aktive als auch inaktive Produkte werden berücksichtigt.
  - **Empfohlener Wert:** JA (Inaktive Produkte ausschließen).
  - **Händlerszenario / Beispiel:** Sie möchten, dass KI nur aktuell verfügbare und aktive Produkte anzeigt.
- **Produkte nach Hinzufügedatum ausschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte basierend auf dem Zeitpunkt ihrer Hinzufügung zu Ihrem Shop auszuschließen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sie können einen Datumsbereich festlegen. Produkte, die außerhalb dieses Bereichs hinzugefügt wurden, werden weggelassen.
    - *Wenn deaktiviert:* Das Produkthinzufügedatum wird nicht für den Ausschluss verwendet.
  - **Empfohlener Wert:** Bei Bedarf verwenden.
  - **Händlerszenario / Beispiel:** Sie möchten, dass KI nur Produkte indexiert, die im letzten Jahr hinzugefügt wurden.
- **Produkte nach Aktualisierungsdatum ausschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Produkte basierend auf ihrem letzten Aktualisierungsdatum auszuschließen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sie können einen Datumsbereich festlegen. Produkte, die außerhalb dieses Bereichs aktualisiert wurden, werden weggelassen.
    - *Wenn deaktiviert:* Das Produktaktualisierungsdatum wird nicht für den Ausschluss verwendet.
  - **Empfohlener Wert:** Bei Bedarf verwenden.
  - **Händlerszenario / Beispiel:** Sie möchten, dass KI nur Produkte indexiert, die kürzlich aktualisiert oder überprüft wurden.
- **Produkte nach spezifischen Produkt-IDs ausschließen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, manuell eine durch Kommas getrennte Liste spezifischer Produkt-IDs einzugeben, die ausgeschlossen werden sollen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Produkte mit den angegebenen IDs werden weggelassen.
    - *Wenn deaktiviert:* Es werden keine Produkte nach ID ausgeschlossen.
  - **Empfohlener Wert:** Bei Bedarf verwenden.
  - **Händlerszenario / Beispiel:** Sie haben einige spezifische Produkte, die problematisch oder sensibel sind und niemals von KI indexiert werden dürfen.

#### Erweiterte Einstellungen

- **Regenerierungszeitplan (Cron-Job):**

  - **Was diese Einstellung bewirkt:** Definiert, wie oft die `llms.txt`-Datei automatisch neu generiert werden soll. Dies ist entscheidend, um die Datei ohne manuelles Eingreifen auf dem neuesten Stand zu halten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Täglich / Wöchentlich / Monatlich:* Das Modul stellt eine Cron-Job-URL bereit. Wenn diese URL aufgerufen wird (z. B. durch den Cron-Dienst Ihres Hosting-Anbieters), wird die `llms.txt`-Datei neu erstellt.
    - *Manuell:* Sie müssen die Schaltfläche „LLMS.txt generieren“ jedes Mal manuell anklicken, wenn Sie die Datei aktualisieren möchten.
  - **Empfohlener Wert:** Täglich (für die meisten aktiven Shops).
  - **Händlerszenario / Beispiel:** Sie fügen regelmäßig neue Produkte hinzu oder aktualisieren Preise. Eine tägliche Regenerierung stellt sicher, dass KI-Crawler immer die neuesten Informationen erhalten. Das Modul zeigt die Cron-URL an, die Sie auf Ihrem Server einrichten müssen.
- **Multistore-Unterstützung:**

  - **Was diese Einstellung bewirkt:** Wenn Sie einen PrestaShop Multistore betreiben, können Sie mit dieser Option separate `llms.txt`-Dateien für jeden Ihrer Shops oder eine einzelne Datei für alle Shops generieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Aktiviert:* Das Modul berücksichtigt Ihren Multistore-Kontext und generiert Dateien, die spezifisch für den Inhalt jedes Shops sind.
    - *Deaktiviert:* Das Modul könnte eine einzelne Datei basierend auf dem Standard-Shop generieren oder sich in einer Multistore-Umgebung unerwartet verhalten.
  - **Empfohlener Wert:** JA (wenn Sie Multistore verwenden).
  - **Händlerszenario / Beispiel:** Sie haben unterschiedliche Produktkataloge oder Sprachen für jeden Shop in Ihrem Multistore-Setup und benötigen separate `llms.txt`-Dateien für jeden.
- **Cache-Lebensdauer (Minuten):**

  - **Was diese Einstellung bewirkt:** Bestimmt, wie lange die generierte `llms.txt`-Datei zwischengespeichert wird, bevor sie als „veraltet“ gilt und neu generiert werden muss (für dynamischen Dateityp).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Höherer Wert:* Weniger häufige Regenerierung, potenziell schneller für KI-Bots, aber der Inhalt könnte etwas älter sein.
    - *Niedrigerer Wert:* Häufigere Regenerierung, gewährleistet frischere Inhalte, aber potenziell höhere Serverlast.
  - **Empfohlener Wert:** 60 (1 Stunde) für dynamisch, oder irrelevant für statisch.
  - **Händlerszenario / Beispiel:** Wenn Sie die dynamische Generierung verwenden und Ihre Produktdaten stündlich wechseln, stellen Sie dies auf 60 ein. Wenn Änderungen seltener sind, können Sie den Wert erhöhen.
- **Analyse & Bot-Tracking aktivieren:**

  - **Was diese Einstellung bewirkt:** Aktiviert eine Funktion, um zu verfolgen, wann KI-Bots auf Ihre `llms.txt`-Datei zugreifen, und liefert Einblicke in deren Aktivität.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul protokolliert Zugriffe auf die `llms.txt`-Datei, die im Dashboard des Moduls angezeigt werden können.
    - *Wenn deaktiviert:* Es werden keine Bot-Zugriffsdaten gesammelt.
  - **Empfohlener Wert:** JA (Nützlich, um die Aktivität von KI-Crawlern zu verstehen).
  - **Händlerszenario / Beispiel:** Sie möchten sehen, wie oft KI-Modelle Ihren Shop crawlen und welche am aktivsten sind.
- **Cache leeren Schaltfläche:**

  - **Was diese Einstellung bewirkt:** Eine manuelle Schaltfläche zum Leeren aller zwischengespeicherten `llms.txt`-Dateien.
  - **Auswirkung der Änderung dieser Einstellung:** Entfernt sofort alle gespeicherten `llms.txt`-Dateien und erzwingt eine neue Generierung bei der nächsten Anfrage (für dynamisch) oder wenn die Schaltfläche „LLMS.txt generieren“ angeklickt wird (für statisch).
  - **Empfohlener Wert:** Klicken Sie, wenn Sie wesentliche Änderungen an Ihren Einstellungen oder Ihrem Produktkatalog vornehmen und sicherstellen möchten, dass die `llms.txt`-Datei sofort aktualisiert wird.
  - **Händlerszenario / Beispiel:** Sie haben gerade eine wichtige neue Produktlinie hinzugefügt und möchten, dass KI sie sofort entdeckt, also leeren Sie den Cache und generieren neu.
- **LLMS.txt generieren Schaltfläche:**

  - **Was diese Einstellung bewirkt:** Eine manuelle Schaltfläche zum sofortigen Generieren oder Regenerieren der `llms.txt`-Datei basierend auf Ihren aktuellen Einstellungen.
  - **Auswirkung der Änderung dieser Einstellung:** Das Modul verarbeitet Ihren Katalog und Ihre Einstellungen und erstellt oder aktualisiert dann die `llms.txt`-Datei.
  - **Empfohlener Wert:** Klicken Sie nach jeder Konfigurationsänderung oder wenn Sie eine sofortige Aktualisierung benötigen, insbesondere wenn Sie die statische Dateigenerierung verwenden.
  - **Händlerszenario / Beispiel:** Sie haben alle Ihre Ausschlussregeln konfiguriert und möchten die anfängliche `llms.txt`-Datei erstellen.

#### Pro-Produkt-Überschreibungen (Admin-Produktseite)

Das Modul integriert sich auch direkt in Ihre Produktbearbeitungsseiten im Back Office.

- **Dieses Produkt aus LLMS.txt ausschließen:**
  - **Was diese Einstellung bewirkt:** Ein Kontrollkästchen auf einzelnen Produktseiten, mit dem Sie globale Einstellungen überschreiben und ein einzelnes Produkt explizit aus der `llms.txt`-Datei ausschließen können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Dieses spezifische Produkt wird nicht in der `llms.txt`-Datei enthalten sein, unabhängig von anderen globalen Einschlussregeln.
    - *Wenn deaktiviert:* Die Aufnahme des Produkts wird durch die globalen Einstellungen bestimmt.
  - **Empfohlener Wert:** Bei Bedarf für spezifische Produkte verwenden.
  - **Händlerszenario / Beispiel:** Sie haben ein Produkt, das vorübergehend nicht verfügbar ist, oder einen sehr Nischenartikel, den Sie nicht von KI weit verbreitet bewerben lassen möchten.

#### Pro-Kategorie-Überschreibungen (Admin-Kategorieseite)

Ähnlich integriert sich das Modul in Ihre Kategoriebearbeitungsseiten.

- **Diese Kategorie aus LLMS.txt ausschließen:**
  - **Was diese Einstellung bewirkt:** Ein Kontrollkästchen auf einzelnen Kategorieseiten, mit dem Sie globale Einstellungen überschreiben und eine ganze Kategorie (und ihre Produkte) explizit aus der `llms.txt`-Datei ausschließen können.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Diese spezifische Kategorie und alle Produkte darin werden nicht in der `llms.txt`-Datei enthalten sein.
    - *Wenn deaktiviert:* Die Aufnahme der Kategorie wird durch die globalen Einstellungen bestimmt.
  - **Empfohlener Wert:** Bei Bedarf für spezifische Kategorien verwenden.
  - **Händlerszenario / Beispiel:** Sie haben eine „Ausverkauf“-Kategorie, die sich häufig ändert, und Sie möchten nicht, dass KI sie indexiert, oder eine Kategorie für den internen Gebrauch.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### Dashboard (Back Office > Module > LLMS.txt Generator Pro > Dashboard)

- **Bildschirmname & Menüpfad:** Dieser Bildschirm ist über die Hauptkonfigurationsseite des Moduls zugänglich, normalerweise über einen „Dashboard“-Tab oder Link. Er bietet einen Überblick über die Aktivität von KI-Bots und den Modulstatus.
- **Verfügbare Aktionen & Einstellungen:**
  - **Bot-Traffic-Analyse:** Zeigt Diagramme oder Tabellen an, die zeigen, welche KI-Crawler (User Agents) auf Ihre `llms.txt`-Datei zugegriffen haben, wie oft und wann.
  - **Letzter Generierungsstatus:** Zeigt an, wann die `llms.txt`-Datei zuletzt generiert wurde, ihre Größe und die Anzahl der enthaltenen URLs.
  - **Fehlerprotokolle:** Alle während der Generierung aufgetretenen Probleme werden hier angezeigt.
- **Auswirkung von Änderungen:** Dieser Bildschirm dient hauptsächlich der Überwachung und Berichterstattung. Änderungen hier beziehen sich typischerweise auf das Anzeigen von Daten, nicht auf das Ändern des Shop-Verhaltens.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie regelmäßig das Dashboard, um sicherzustellen, dass Ihre `llms.txt`-Datei wie erwartet von KI-Bots aufgerufen wird und um nach Fehlern zu suchen. Dies hilft Ihnen, die Auswirkungen Ihrer KI-Sichtbarkeitsstrategie zu verstehen.

#### Vorschau (Back Office > Module > LLMS.txt Generator Pro > Vorschau)

- **Bildschirmname & Menüpfad:** Zugänglich über die Hauptkonfigurationsseite des Moduls, normalerweise über einen „Vorschau“-Tab oder Link.
- **Verfügbare Aktionen & Einstellungen:**
  - **LLMS.txt-Inhaltsanzeige:** Zeigt den tatsächlichen Inhalt der `llms.txt`-Datei an, der KI-Crawlern basierend auf Ihren aktuellen Einstellungen bereitgestellt würde.
  - **llms-full.txt-Inhaltsanzeige:** Wenn aktiviert, wird auch der Inhalt der `llms-full.txt`-Datei angezeigt.
- **Auswirkung von Änderungen:** Dieser Bildschirm dient der Überprüfung. Er ermöglicht es Ihnen, den generierten Inhalt zu überprüfen, bevor er live geschaltet wird oder nachdem Änderungen vorgenommen wurden, um sicherzustellen, dass er Ihren Anforderungen entspricht.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Nach wesentlichen Änderungen an Ihren Moduleinstellungen oder Ihrem Produktkatalog verwenden Sie den Vorschaubildschirm, um zu überprüfen, ob die richtigen URLs enthalten und ausgeschlossen sind.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfig | LLMS.txt-Generierung aktivieren | JA | Aktiviert/deaktiviert die Kernfunktion des Moduls. |
| Modulkonfig | LLMS.txt-Dateityp | Statisch | Wählen Sie statisch für Leistung, dynamisch für Echtzeit-Updates. |
| Modulkonfig | llms-full.txt generieren | JA | Stellt eine umfassendere Datei für KI bereit. |
| Modulkonfig | Produktseiten einschließen | JA | Macht Produkt-URLs für KI auffindbar. |
| Modulkonfig | Kategorieseiten einschließen | JA | Macht Kategorie-URLs für KI auffindbar. |
| Modulkonfig | CMS-Seiten einschließen | JA | Macht Informationsseiten für KI auffindbar. |
| Modulkonfig | Hersteller-/Markenseiten einschließen | JA | Macht Markenseiten für KI auffindbar. |
| Modulkonfig | Lieferantenseiten einschließen | NEIN | Im Allgemeinen nicht für die öffentliche KI-Indexierung erforderlich. |
| Modulkonfig | Seite „Neue Produkte“ einschließen | JA | Hebt die neuesten Produkte für KI hervor. |
| Modulkonfig | Seite „Beste Verkäufe“ einschließen | JA | Bewirbt meistverkaufte Artikel für KI. |
| Modulkonfig | Seite „Preissenkungen“ einschließen | JA | Hebt reduzierte Artikel für KI hervor. |
| Modulkonfig | Kontaktseite einschließen | JA | Stellt Kontaktinformationen für KI bereit. |
| Modulkonfig | Sitemap-Seite einschließen | JA | Hilft KI, mehr Inhalte zu entdecken. |
| Modulkonfig | Benutzerdefinierte URLs einschließen | Bei Bedarf verwenden | Fügen Sie spezifische, nicht-PrestaShop-URLs hinzu. |
| Modulkonfig | Spezifische URLs ausschließen | Bei Bedarf verwenden | Verbergen Sie sensible oder irrelevante URLs. |
| Modulkonfig | Produkte nach Kategorie ausschließen | Bei Bedarf verwenden | Filtern Sie Produkte nach Kategorie. |
| Modulkonfig | Produkte nach Hersteller ausschließen | Bei Bedarf verwenden | Filtern Sie Produkte nach Hersteller. |
| Modulkonfig | Produkte nach Lieferant ausschließen | Bei Bedarf verwenden | Filtern Sie Produkte nach Lieferant. |
| Modulkonfig | Produkte nach Merkmal ausschließen | Bei Bedarf verwenden | Filtern Sie Produkte nach spezifischen Merkmalen. |
| Modulkonfig | Produkte nach Attribut ausschließen | Bei Bedarf verwenden | Filtern Sie Produkte nach spezifischen Attributen. |
| Modulkonfig | Produkte nach Preisspanne ausschließen | Bei Bedarf verwenden | Filtern Sie Produkte innerhalb einer Preisspanne. |
| Modulkonfig | Produkte nach Lagerbestand ausschließen | JA (<=0) | Verbergen Sie nicht vorrätige Produkte vor KI. |
| Modulkonfig | Produkte nach Sichtbarkeit ausschließen | Bei Bedarf verwenden | Filtern Sie Produkte nach PrestaShop-Sichtbarkeit. |
| Modulkonfig | Produkte nach Status ausschließen | JA (inaktiv) | Verbergen Sie inaktive Produkte vor KI. |
| Modulkonfig | Produkte nach Hinzufügedatum ausschließen | Bei Bedarf verwenden | Filtern Sie Produkte nach Erstellungsdatum. |
| Modulkonfig | Produkte nach Aktualisierungsdatum ausschließen | Bei Bedarf verwenden | Filtern Sie Produkte nach letztem Aktualisierungsdatum. |
| Modulkonfig | Produkte nach spezifischen Produkt-IDs ausschließen | Bei Bedarf verwenden | Schließen Sie einzelne Produkte nach ID aus. |
| Modulkonfig | Regenerierungszeitplan (Cron-Job) | Täglich | Automatisiert `llms.txt`-Updates. |
| Modulkonfig | Multistore-Unterstützung | JA (falls zutreffend) | Ermöglicht separate Dateien für jeden Shop. |
| Modulkonfig | Cache-Lebensdauer (Minuten) | 60 (für dynamisch) | Legt fest, wie lange die dynamische Datei zwischengespeichert wird. |
| Modulkonfig | Analyse & Bot-Tracking aktivieren | JA | Überwacht die Aktivität von KI-Crawlern. |
| Modulkonfig | Cache leeren Schaltfläche | Bei Bedarf klicken | Erzwingt das Leeren des Caches für sofortige Updates. |
| Modulkonfig | LLMS.txt generieren Schaltfläche | Bei Bedarf klicken | Generiert die `llms.txt`-Datei manuell. |
| Produktbearbeitungsseite | Dieses Produkt aus LLMS.txt ausschließen | Nicht aktiviert | Überschreibt globale Einstellungen für ein einzelnes Produkt. |
| Kategoriebearbeitungsseite | Diese Kategorie aus LLMS.txt ausschließen | Nicht aktiviert | Überschreibt globale Einstellungen für eine ganze Kategorie. |
| Dashboard | Bot-Traffic-Analyse | N/A | Überwacht den Zugriff von KI-Bots. |
| Dashboard | Letzter Generierungsstatus | N/A | Zeigt den Status der `llms.txt`-Datei an. |
| Vorschau | LLMS.txt-Inhaltsanzeige | N/A | Zeigt den generierten `llms.txt`-Inhalt an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine `llms.txt`-Datei wird nicht angezeigt oder aktualisiert.**
A:

1.  **„LLMS.txt-Generierung aktivieren“ überprüfen:** Stellen Sie sicher, dass dies in der Modulkonfiguration auf JA eingestellt ist.
2.  **Dateityp überprüfen:** Wenn auf „Statisch“ eingestellt, stellen Sie sicher, dass Ihr Server Schreibberechtigungen für das PrestaShop-Stammverzeichnis hat. Klicken Sie außerdem manuell auf die Schaltfläche „LLMS.txt generieren“.
3.  **Cron-Job:** Wenn Sie einen Cron-Job verwenden, überprüfen Sie, ob er auf Ihrem Hosting korrekt eingerichtet ist und die vom Modul bereitgestellte URL zugänglich ist.
4.  **Cache leeren:** Gehen Sie in PrestaShop zu **Erweiterte Einstellungen > Leistung** und leeren Sie den Smarty-Cache. Versuchen Sie dann, die `llms.txt`-Datei neu zu generieren.
5.  **Modul-Dashboard:** Überprüfen Sie das Dashboard des Moduls auf Fehlermeldungen während der Generierung.

**F: Ich habe Änderungen vorgenommen, aber die `llms.txt`-Datei spiegelt diese nicht wider.**
A:

1.  **Manuell neu generieren:** Klicken Sie in der Modulkonfiguration auf die Schaltfläche „LLMS.txt generieren“.
2.  **Cron-Job-Timing:** Wenn Sie sich auf einen Cron-Job verlassen, denken Sie daran, dass dieser nur in geplanten Intervallen ausgeführt wird. Ihre Änderungen werden nach dem nächsten geplanten Lauf angezeigt.
3.  **Cache:** Wenn Sie die dynamische Generierung verwenden, könnte die `llms.txt`-Datei zwischengespeichert sein. Klicken Sie auf die Schaltfläche „Cache leeren“ im Modul oder leeren Sie den PrestaShop-Cache unter **Erweiterte Einstellungen > Leistung**.

**F: Woher weiß ich, ob KI-Bots meine `llms.txt`-Datei tatsächlich verwenden?**
A: Aktivieren Sie „Analyse & Bot-Tracking“ in den Moduleinstellungen. Das Dashboard des Moduls zeigt Ihnen dann Statistiken darüber an, welche KI-User-Agents wann auf Ihre `llms.txt`-Datei zugegriffen haben.

**F: Die `llms.txt`-Datei ist zu groß oder enthält zu viele irrelevante URLs.**
A:

1.  **Einschluss-Einstellungen überprüfen:** Gehen Sie die „Einschließen…“-Optionen durch und deaktivieren Sie alle Inhaltstypen, die Sie nicht von KI indexieren lassen möchten (z. B. Lieferantenseiten).
2.  **Ausschlussfilter nutzen:** Nutzen Sie die „Produkte ausschließen nach…“-Filter (Kategorie, Lagerbestand, Preis usw.) und „Spezifische URLs ausschließen“ ausgiebig, um den Inhalt zu verfeinern.
3.  **Pro-Produkt-/Kategorie-Überschreibungen:** Für sehr spezifische Fälle verwenden Sie die Ausschluss-Kontrollkästchen auf einzelnen Produkt- und Kategoriebearbeitungsseiten.

**F: Mein benutzerdefiniertes Theme zeigt die Funktionen des Moduls nicht korrekt an (z. B. zusätzliche Felder auf der Produktseite).**
A: Die Integration des Moduls in Produkt-/Kategorieseiten ist Standard. Wenn Sie Probleme feststellen, handelt es sich wahrscheinlich um einen Konflikt mit Ihrem benutzerdefinierten Theme oder einem anderen Modul, das die Produkt-/Kategorie-Bearbeitungsformulare stark modifiziert.

1.  **Auf Konflikte prüfen:** Deaktivieren Sie vorübergehend andere Module, die Produkt-/Kategorieseiten ändern, um zu sehen, ob das Problem behoben wird.
2.  **Theme-Überschreibungen:** Ihr Theme könnte Template-Überschreibungen haben, die verhindern, dass die zusätzlichen Felder des Moduls gerendert werden. Kontaktieren Sie Ihren Theme-Entwickler oder einen PrestaShop-Experten, um dies zu untersuchen.
3.  **Cache leeren:** Leeren Sie immer den PrestaShop-Cache nach Theme- oder Moduländerungen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul LLMS.txt Generator Pro folgt einer Standard-PrestaShop-Modularchitektur und nutzt MVC-Prinzipien. Es arbeitet hauptsächlich über eine Hauptmodulklasse (`llmstxtpro/index.php`) für Konfiguration und Hook-Management und eine Reihe dedizierter Klassen (`classes/`) für Geschäftslogik, Datenverarbeitung und Dateigenerierung. Front-Controller kümmern sich um die dynamische `llms.txt`-Bereitstellung und die Ausführung von Cron-Jobs. Die Konfiguration wird in `ps_configuration` und benutzerdefinierten Tabellen gespeichert.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller sind für die Bereitstellung der `llms.txt`- und `llms-full.txt`-Dateien sowie für die Bearbeitung von Cron-Job-Anfragen verantwortlich.

- `controllers/front/aicatalog.php`
  - **Klassenname & übergeordnete Klasse:** `LlmsTxtProAiCatalogModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Behandelt wahrscheinlich spezifische KI-Kataloganfragen, potenziell für strukturiertere Datenformate jenseits von `llms.txt`. Es könnte eine JSON- oder XML-Darstellung des Katalogs für die KI-Nutzung bereitstellen.
- `controllers/front/cron.php`
  - **Klassenname & übergeordnete Klasse:** `LlmsTxtProCronModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist dafür konzipiert, von einem serverseitigen Cron-Job aufgerufen zu werden. Beim Zugriff löst er den Regenerierungsprozess der `llms.txt` (und `llms-full.txt`) basierend auf der Modulkonfiguration aus. Er gibt typischerweise eine einfache Erfolgs-/Fehlermeldung zurück.
- `controllers/front/index.php`
  - **Klassenname & übergeordnete Klasse:** `LlmsTxtProIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dies könnte ein Platzhalter oder ein generischer Einstiegspunkt sein. Angesichts der anderen spezifischen Controller ist es weniger wahrscheinlich, dass er eine direkte, einzigartige Funktion für die `llms.txt`-Generierung selbst hat, könnte aber für die allgemeine Front-Office-Weiterleitung oder Informationsbereitstellung des Moduls verwendet werden.
- `controllers/front/llmsfull.php`
  - **Klassenname & übergeordnete Klasse:** `LlmsTxtProLlmsFullModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Wenn der `llms-full.txt`-Dateityp auf dynamisch eingestellt ist, stellt dieser Controller den Inhalt der `llms-full.txt`-Datei bereit. Er fragt die Datenbank ab und generiert die vollständige Liste der URLs und zugehörigen Daten.
- `controllers/front/llmstxt.php`
  - **Klassenname & übergeordnete Klasse:** `LlmsTxtProLlmsTxtModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Wenn der `llms.txt`-Dateityp auf dynamisch eingestellt ist, stellt dieser Controller den Inhalt der Standard-`llms.txt`-Datei bereit. Er fragt die Datenbank ab und generiert die Liste der URLs basierend auf der Modulkonfiguration und den Ausschlussregeln.

#### Back-Office-Admin-Controller

Das Modul scheint keine dedizierten benutzerdefinierten Admin-Controller (`controllers/admin/`) zu haben. Die gesamte Konfiguration wird über die `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- `classes/index.php`
  - **Verantwortlichkeit:** Typischerweise eine leere Datei, um die Verzeichnisauflistung zu verhindern, keine funktionale Klasse.
- `classes/LlmsTxtProAiCatalog.php`
  - **Verantwortlichkeit:** Enthält wahrscheinlich die Logik zur Generierung eines strukturierteren KI-Katalogs (z. B. JSON-LD, schema.org-Markup), der von `aicatalog.php` bereitgestellt werden könnte. Es würde Methoden zum Abfragen von Produkt-, Kategorie- und CMS-Daten mit KI-spezifischer Formatierung kapseln.
- `classes/LlmsTxtProAnalytics.php`
  - **Verantwortlichkeit:** Verwaltet die Protokollierung und den Abruf von KI-Bot-Zugriffsdaten. Es würde mit einer benutzerdefinierten Datenbanktabelle interagieren, um User Agent, Zeitstempel und die aufgerufene Datei (`llms.txt` oder `llms-full.txt`) zu speichern. Bietet Methoden zur Berichterstattung dieser Daten an das Admin-Dashboard.
- `classes/LlmsTxtProConfig.php`
  - **Verantwortlichkeit:** Eine Hilfsklasse zur Verwaltung der Modulkonfigurationseinstellungen. Sie würde statische Methoden zum Abrufen und Festlegen von Konfigurationswerten aus `Configuration::get()` und `Configuration::updateValue()` bereitstellen, potenziell mit Standardwerten und Typumwandlung.
- `classes/LlmsTxtProGenerator.php`
  - **Verantwortlichkeit:** Dies ist die Kernlogikklasse zur Generierung des `llms.txt`- und `llms-full.txt`-Inhalts. Sie enthält Methoden zum:
    - Abrufen von Produkten, Kategorien, CMS-Seiten, Herstellern, Lieferanten usw.
    - Anwenden aller Einschluss- und Ausschlussfilter (nach Kategorie, Hersteller, Preis, Lagerbestand, benutzerdefinierten URLs usw.).
    - Formatieren der URLs gemäß dem `llms.txt`-Standard.
    - Handhaben des statischen Dateischreibens in das Stammverzeichnis.
    - Potenzielles Verwalten des Cachings für die dynamische Generierung.
- `classes/LlmsTxtProLogger.php`
  - **Verantwortlichkeit:** Eine Dienstprogrammklasse zum Protokollieren modulspezifischer Ereignisse, Warnungen oder Fehler. Sie könnte in eine benutzerdefinierte Protokolldatei schreiben oder sich in den Standard-Logger von PrestaShop integrieren. Nützlich zur Fehlerbehebung bei Generierungsproblemen.

### 4.4 JavaScript-Assets (`views/js/`)

- `llmstxtpro/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office.
  - **Verantwortlichkeit:** Bietet Autocomplete-Funktionalität für Eingabefelder in der Admin-Konfiguration, wahrscheinlich zur Auswahl von Produkten, Kategorien, Herstellern oder spezifischen URLs zum Ausschluss. Es bindet an Eingabefelder und führt AJAX-Aufrufe aus, um Vorschläge abzurufen.
- `llmstxtpro/views/js/adminLlmsTxtProDashboard.js`
  - **Geltungsbereich:** Back-Office (Dashboard-Bildschirm).
  - **Verantwortlichkeit:** Verwaltet die dynamische Anzeige von Analysedaten auf dem Dashboard des Moduls. Es könnte AJAX verwenden, um Bot-Traffic-Statistiken von `LlmsTxtProAnalytics` abzurufen und diese mithilfe von Diagrammbibliotheken oder Datentabellen zu rendern.

### 4.5 CSS-Stylesheets (`views/css/`)

- `llmstxtpro/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office.
  - **Verantwortlichkeit:** Gestaltet die Autocomplete-Dropdowns und Vorschläge, die in den Admin-Konfigurationsformularen verwendet werden.
- `llmstxtpro/views/css/admin-config.css`
  - **Geltungsbereich:** Back-Office (Modulkonfigurationsseite).
  - **Verantwortlichkeit:** Bietet spezifisches Styling für das Hauptkonfigurationsformular des Moduls, um ein konsistentes und benutzerfreundliches Layout innerhalb des PrestaShop Back Office zu gewährleisten.
- `llmstxtpro/views/css/admin-dashboard.css`
  - **Geltungsbereich:** Back-Office (Dashboard-Bildschirm).
  - **Verantwortlichkeit:** Gestaltet die Dashboard-Elemente, einschließlich Diagramme, Tabellen und Statusanzeigen für Bot-Traffic-Analysen und den Generierungsstatus.
- `llmstxtpro/views/css/admin-searchtool.css`
  - **Geltungsbereich:** Back-Office.
  - **Verantwortlichkeit:** Allgemeines Styling für suchbezogene UI-Komponenten innerhalb des Admin-Bereichs, potenziell gemeinsam mit `autocomplete.css` oder für andere Such-/Filteroberflächen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**: Die Modulbeschreibung listet keine expliziten Hook-Templates auf, was darauf hindeutet, dass die Front-Office-Präsenz hauptsächlich über die generierte `llms.txt`-Datei selbst erfolgt, nicht über visuelle Elemente.
- **Admin-Templates (`views/templates/admin/`)**:
  - `llmstxtpro/views/templates/admin/category-extra.tpl`
    - **Zweck:** Rendert das Kontrollkästchen „Diese Kategorie aus LLMS.txt ausschließen“ und alle zugehörigen Felder auf der PrestaShop-Kategoriebearbeitungsseite. Dieses Template ist wahrscheinlich in `displayAdminProductsExtra` oder ähnliches eingehängt.
  - `llmstxtpro/views/templates/admin/configure.tpl`
    - **Zweck:** Das Haupttemplate für die Konfigurationsseite des Moduls (`getContent()`-Methode). Es rendert alle allgemeinen Einstellungen, Einschluss-/Ausschlussoptionen, erweiterten Einstellungen und Aktionsschaltflächen.
  - `llmstxtpro/views/templates/admin/dashboard.tpl`
    - **Zweck:** Rendert das Analyse-Dashboard des Moduls, das Bot-Traffic, Generierungsstatus und potenziell Fehlerprotokolle anzeigt.
  - `llmstxtpro/views/templates/admin/preview.tpl`
    - **Zweck:** Rendert den Inhalt der generierten `llms.txt`- und `llms-full.txt`-Dateien zur Überprüfung im Back Office.
  - `llmstxtpro/views/templates/admin/product-extra.tpl`
    - **Zweck:** Rendert das Kontrollkästchen „Dieses Produkt aus LLMS.txt ausschließen“ und alle zugehörigen Felder auf der PrestaShop-Produktbearbeitungsseite. Dieses Template ist wahrscheinlich in `displayAdminProductsExtra` oder ähnliches eingehängt.
- **Front-Office-Templates (`views/templates/front/`)**: Keine explizit aufgeführt, was bestätigt, dass die Front-Office-Interaktion des Moduls hauptsächlich maschinell über die `llms.txt`-Datei erfolgt.
- `llmstxtpro/lib/searchTool/views/scripts.tpl`
  - **Zweck:** Enthält wahrscheinlich JavaScript- und CSS-Assets für das Suchwerkzeug (z. B. autocomplete.js, autocomplete.css) im Admin-Kontext.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - `ps_configuration`: Speichert alle Modulkonfigurationseinstellungen (z. B. `LLMSTXTPRO_ENABLED`, `LLMSTXTPRO_FILE_TYPE`, `LLMSTXTPRO_INCLUDE_PRODUCTS`, `LLMSTXTPRO_EXCLUDE_URLS` usw.).
  - `ps_llmstxtpro_product_override`: Eine benutzerdefinierte Tabelle zum Speichern von produktspezifischen Ausschluss-Einstellungen. (Wahrscheinlich `id_product`, `excluded`).
  - `ps_llmstxtpro_category_override`: Eine benutzerdefinierte Tabelle zum Speichern von kategoriespezifischen Ausschluss-Einstellungen. (Wahrscheinlich `id_category`, `excluded`).
  - `ps_llmstxtpro_analytics_log`: Eine benutzerdefinierte Tabelle zum Speichern von Bot-Zugriffsprotokollen (z. B. `id_llmstxtpro_analytics_log`, `user_agent`, `access_time`, `file_type`).
  - `ps_llmstxtpro_urls`: Potenziell eine Tabelle zum Zwischenspeichern generierter URLs für die Leistung, insbesondere bei statischer Dateigenerierung. (Wahrscheinlich `id_url`, `url`, `file_type`, `date_add`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Bevor der Admin-Controller seinen Inhalt rendert. | Fügt die CSS/JS des Moduls für die Admin-Konfiguration, das Dashboard und die zusätzlichen Produkt-/Kategorie-Felder ein. |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite. | Rendert das Kontrollkästchen „Dieses Produkt aus LLMS.txt ausschließen“. |
| `displayAdminCategoriesExtra` | Auf der Kategoriebearbeitungsseite. | Rendert das Kontrollkästchen „Diese Kategorie aus LLMS.txt ausschließen“. |
| `actionModuleInstall` | Während der Modulinstallation. | Erstellt Datenbanktabellen, setzt Standardkonfigurationswerte. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Löscht Datenbanktabellen und Konfigurationswerte. |
| `displayHeader` | Im `<head>`-Abschnitt der Front-Office-Seiten. | (Weniger wahrscheinlich für dieses Modul, könnte aber bei Bedarf für Meta-Tags oder KI-spezifische Links verwendet werden). |
| `displayRightColumn` | In der rechten Spalte der Front-Office-Seiten. | (Nicht direkt relevant für die `llms.txt`-Generierung). |
| `displayFooter` | Im Footer der Front-Office-Seiten. | (Nicht direkt relevant für die `llms.txt`-Generierung). |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts. | Löst potenziell eine Cache-Leerung aus oder markiert zur Regenerierung, wenn dynamische `llms.txt` verwendet wird. |
| `actionCategoryUpdate` | Nach der Aktualisierung einer Kategorie. | Löst potenziell eine Cache-Leerung aus oder markiert zur Regenerierung. |
| `actionObjectProductAddAfter` | Nach dem Hinzufügen eines neuen Produkts. | Löst potenziell eine Cache-Leerung aus oder markiert zur Regenerierung. |
| `actionObjectCategoryAddAfter` | Nach dem Hinzufügen einer neuen Kategorie. | Löst potenziell eine Cache-Leerung aus oder markiert zur Regenerierung. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen zum LLMS.txt Generator Pro-Modul zur Verfügung.

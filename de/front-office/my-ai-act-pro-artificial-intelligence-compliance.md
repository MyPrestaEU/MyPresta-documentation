---
title: "My AI Act Pro - Artificial Intelligence Compliance - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul My AI Act Pro - Artificial Intelligence Compliance von MyPresta.eu."
sidebar:
  label: "My AI Act Pro - Artificial Intelligence Compliance - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul My AI Act Pro - Artificial Intelligence Compliance auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/my-ai-act-pro-artificial-intelligence-compliance.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/my-ai-act-pro-artificial-intelligence-compliance/)
>
> ---


# My AI Act Pro - Artificial Intelligence Compliance

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.6.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Stellen Sie sicher, dass Ihr Server die allgemeinen Anforderungen von PrestaShop für optimale Leistung erfüllt.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > My AI Act Pro)

Dies ist das Hauptkontrollfeld für Ihr AI Act Compliance-Modul. Hier aktivieren Sie Funktionen, definieren globale Einstellungen und verwalten das Gesamtverhalten der KI-Offenlegungen.

#### Registerkarte „Allgemeine Einstellungen“

- **AI Act Compliance aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das gesamte Modul.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Alle Funktionen des Moduls (Badges, Banner, Protokolle usw.) werden in Ihrem Shop gemäß ihren individuellen Einstellungen aktiv.
    - *Wenn deaktiviert:* Das Modul zeigt keine AI Act-bezogenen Inhalte mehr in Ihrem Front Office an, und seine Hintergrundprozesse werden angehalten.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Aktivieren Sie dies, sobald Sie bereit sind, Ihre AI Act Compliance live zu schalten. Wenn Sie alle Offenlegungen vorübergehend für Wartungsarbeiten deaktivieren müssen, schalten Sie dies aus.
- **KI-Offenlegungs-Badge auf Produktseiten anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob das KI-Offenlegungs-Badge auf einzelnen Produktseiten erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das KI-Badge wird auf Produktseiten für Produkte sichtbar sein, die als KI-generiert markiert sind.
    - *Wenn deaktiviert:* Das Badge wird auf Produktseiten nicht angezeigt, auch wenn Produkte gekennzeichnet sind.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Dies ist entscheidend für die direkte Produkttransparenz. Lassen Sie es aktiviert, um Kunden direkt über das Produkt zu informieren, das sie gerade ansehen.
- **KI-Offenlegungs-Badge in Produktlisten anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob das KI-Offenlegungs-Badge auf Kategorieseiten, Suchergebnissen oder anderen Produktlistenansichten erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein kleineres KI-Badge erscheint auf Produkt-Thumbnails in Listen.
    - *Wenn deaktiviert:* In Produktlisten wird kein Badge angezeigt.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Dies ermöglicht sofortige Transparenz beim Stöbern der Kunden und hilft ihnen, KI-generierte Inhalte zu identifizieren, bevor sie auf eine Produktseite klicken.
- **Position des KI-Offenlegungs-Badges (Produktseite):**

  - **Was diese Einstellung bewirkt:** Bestimmt, wo das KI-Badge auf der Produktseite platziert wird. Optionen umfassen typischerweise „Über dem Produktbild“, „Unter dem Produktbild“, „In der Nähe des Produktnamens“, „In der Produktbeschreibung“ usw.
  - **Auswirkung der Änderung dieser Einstellung:** Das Badge wird an die ausgewählte Position auf der Produktseite verschoben.
  - **Empfohlener Wert:** Experimentieren Sie, um die beste Passform für Ihr Theme zu finden, oft „Über dem Produktbild“ oder „In der Nähe des Produktnamens“ für bessere Sichtbarkeit.
  - **Händlerszenario / Beispiel:** Wenn Ihre Produktbilder sehr groß sind, könnte die Platzierung des Badges „Unter dem Produktbild“ weniger aufdringlich sein. Wenn es sofort auffallen soll, ist „Über dem Produktbild“ besser.
- **Layout des KI-Offenlegungs-Badges:**

  - **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl eines vordefinierten visuellen Stils für das KI-Badge aus dem „Layout Studio“.
  - **Auswirkung der Änderung dieser Einstellung:** Das Erscheinungsbild des KI-Badges (Symbol, Text, Farben, Form) ändert sich entsprechend dem ausgewählten Layout.
  - **Empfohlener Wert:** Wählen Sie ein Layout, das zum Branding Ihres Shops passt und deutlich sichtbar ist.
  - **Händlerszenario / Beispiel:** Sie könnten ein benutzerdefiniertes Layout mit Ihren Markenfarben und einem spezifischen Symbol erstellen, um sicherzustellen, dass das Badge professionell aussieht und gut integriert ist.
- **Link zur KI-Richtlinienseite:**

  - **Was diese Einstellung bewirkt:** Ermöglicht das Verknüpfen mit einer dedizierten CMS-Seite oder externen URL, die die KI-Richtlinie Ihres Shops erklärt.
  - **Auswirkung der Änderung dieser Einstellung:** Das Modul verwendet diese URL, wenn es von Badges, Bannern oder anderen Offenlegungselementen auf Ihre KI-Richtlinie verlinkt.
  - **Empfohlener Wert:** Erstellen Sie eine detaillierte CMS-Seite (z. B. „Unsere KI-Transparenzrichtlinie“) und verlinken Sie sie hier.
  - **Händlerszenario / Beispiel:** Dieser Link ist entscheidend, um Kunden, die mehr über Ihre KI-Nutzung erfahren möchten, umfassende Informationen zu bieten.
- **KI-Offenlegungs-Banner aktivieren:**

  - **Was diese Einstellung bewirkt:** Aktiviert ein shopweites Banner, um Kunden über Ihre KI-Nutzung zu informieren.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Banner erscheint im ausgewählten Hook (z. B. Header oder Footer).
    - *Wenn deaktiviert:* Es wird kein Banner angezeigt.
  - **Empfohlener Wert:** JA, insbesondere für die erste Einführung oder wenn Ihr Shop KI intensiv nutzt.
  - **Händlerszenario / Beispiel:** Verwenden Sie dieses Banner, um eine allgemeine Aussage über die KI-Richtlinie Ihres Shops zu machen, vielleicht mit einem Link zu Ihrer speziellen Richtlinienseite.
- **Position des KI-Offenlegungs-Banners (Hook):**

  - **Was diese Einstellung bewirkt:** Wählt aus, wo das Banner erscheinen soll (z. B. `displayHeader`, `displayFooter`).
  - **Auswirkung der Änderung dieser Einstellung:** Das Banner wird an der gewählten Position gerendert.
  - **Empfohlener Wert:** `displayHeader` für maximale Sichtbarkeit oder `displayFooter` für einen weniger aufdringlichen Ansatz.
  - **Händlerszenario / Beispiel:** Die Platzierung im `displayHeader` stellt sicher, dass jeder Besucher es sofort beim Betreten Ihrer Website sieht.
- **Inhalt des KI-Offenlegungs-Banners:**

  - **Was diese Einstellung bewirkt:** Ermöglicht die Anpassung des Textes und des HTML-Inhalts des Banners.
  - **Auswirkung der Änderung dieser Einstellung:** Das Banner zeigt Ihre benutzerdefinierte Nachricht an.
  - **Empfohlener Wert:** Eine prägnante Nachricht wie „Wir nutzen KI, um Ihr Einkaufserlebnis zu verbessern. [Mehr erfahren]“ mit einem Link zu Ihrer Richtlinienseite.
  - **Händlerszenario / Beispiel:** Sie können dies verwenden, um Ihre KI-Nutzung kurz zu erklären und Kunden auf Ihre vollständige Richtlinie zu verweisen.
- **Menschliche Fallback-Informationen aktivieren:**

  - **Was diese Einstellung bewirkt:** Zeigt eine Nachricht an, die auf menschliche Aufsicht hinweist oder menschliche Unterstützung für KI-generierte Inhalte anbietet.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine konfigurierbare Nachricht erscheint auf relevanten Seiten.
    - *Wenn deaktiviert:* Es wird keine menschliche Fallback-Nachricht angezeigt.
  - **Empfohlener Wert:** JA, wenn Sie Kunden versichern möchten, dass menschliche Überprüfung stattfindet oder einen Kontaktpunkt bereitstellen möchten.
  - **Händlerszenario / Beispiel:** Wenn Ihre KI-generierten Produktbeschreibungen immer von einem menschlichen Redakteur überprüft werden, können Sie dies verwenden, um zu sagen: „Alle KI-generierten Inhalte werden von unserem Team überprüft. Kontaktieren Sie uns, wenn Sie Fragen haben.“
- **Menschliche Fallback-Nachricht:**

  - **Was diese Einstellung bewirkt:** Passt den Text für die menschliche Fallback-Information an.
  - **Auswirkung der Änderung dieser Einstellung:** Die Nachricht wird wie eingegeben angezeigt.
  - **Empfohlener Wert:** Eine klare, beruhigende Nachricht.
  - **Händlerszenario / Beispiel:** „Unsere KI-Tools werden von menschlichen Experten überwacht. Bei Bedenken wenden Sie sich bitte an unseren Kundenservice.“
- **Audit-Log aktivieren:**

  - **Was diese Einstellung bewirkt:** Zeichnet alle AI Act-bezogenen Aktionen und Offenlegungen in einem Protokoll für Compliance-Zwecke auf.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Jedes Mal, wenn eine KI-Offenlegung erfolgt oder ein Produkt gekennzeichnet wird, wird ein Eintrag im Audit-Log des Moduls gespeichert.
    - *Wenn deaktiviert:* Es wird kein Audit-Trail geführt.
  - **Empfohlener Wert:** JA, dies ist entscheidend für den Nachweis der Compliance und die Fehlerbehebung.
  - **Händlerszenario / Beispiel:** Wenn eine Regulierungsbehörde einen Nachweis Ihrer KI-Offenlegungen verlangt, bietet das Audit-Log eine historische Aufzeichnung.

#### Registerkarte „API & Integrationen“

- **REST API aktivieren:**

  - **Was diese Einstellung bewirkt:** Aktiviert einen REST-API-Endpunkt für externe Systeme zur Interaktion mit dem Modul (z. B. Kennzeichnung von Produkten als KI-generiert).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die API wird aktiv und ermöglicht die programmatische Interaktion.
    - *Wenn deaktiviert:* Die API ist inaktiv.
  - **Empfohlener Wert:** NEIN, es sei denn, Sie haben einen spezifischen technischen Bedarf zur Integration mit externen KI-Tools oder -Systemen.
  - **Händlerszenario / Beispiel:** Wenn Sie einen externen KI-Bildgenerierungsdienst verwenden, könnten Sie die API nutzen, um Bilder in PrestaShop automatisch als KI-generiert zu kennzeichnen.
- **API-Schlüsselverwaltung:**

  - **Was diese Einstellung bewirkt:** Ermöglicht das Generieren und Verwalten von API-Schlüsseln für den sicheren Zugriff auf die REST-API des Moduls.
  - **Auswirkung der Änderung dieser Einstellung:** Neue Schlüssel können erstellt, bestehende widerrufen werden, wodurch der Zugriff auf die API kontrolliert wird.
  - **Empfohlener Wert:** Generieren Sie einen starken, eindeutigen Schlüssel für jede Integration.
  - **Händlerszenario / Beispiel:** Erstellen Sie einen spezifischen API-Schlüssel für Ihren KI-Bildgenerator und einen weiteren für Ihren KI-Inhaltsautor und widerrufen Sie diese, wenn eine Integration nicht mehr benötigt wird.
- **Wasserzeichen-CRON aktivieren:**

  - **Was diese Einstellung bewirkt:** Aktiviert eine geplante Aufgabe (CRON-Job), um automatisch Wasserzeichen auf KI-generierte Bilder anzuwenden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der CRON-Job wird regelmäßig ausgeführt und wendet ein konfigurierbares Wasserzeichen auf gekennzeichnete Bilder an.
    - *Wenn deaktiviert:* Es erfolgt keine automatische Wasserzeichenanwendung.
  - **Empfohlener Wert:** NEIN, es sei denn, Sie benötigen speziell Wasserzeichen für KI-Bilder.
  - **Händlerszenario / Beispiel:** Wenn Sie einen visuellen Indikator direkt auf dem Bild selbst (z. B. ein kleines „AI“-Logo) für alle KI-generierten Produktbilder wünschen, aktivieren Sie dies.
- **Wasserzeichen-Bild/Text:**

  - **Was diese Einstellung bewirkt:** Definiert das anzuwendende Wasserzeichen (z. B. eine Bilddatei oder eine Textzeichenfolge).
  - **Auswirkung der Änderung dieser Einstellung:** Der CRON-Job verwendet dieses Wasserzeichen.
  - **Empfohlener Wert:** Ein subtiler, klarer Indikator, falls verwendet.
  - **Händlerszenario / Beispiel:** Laden Sie ein kleines, halbtransparentes „AI Generated“-Bild hoch oder geben Sie „AI“ als Text ein.

#### Registerkarte „Shortcodes“

- **Shortcode-Liste & Verwendung:**
  - **Was diese Einstellung bewirkt:** Bietet eine Liste der verfügbaren Shortcodes, die in Produktbeschreibungen, CMS-Seiten oder anderen Textbereichen eingefügt werden können.
  - **Auswirkung der Änderung dieser Einstellung:** Keine direkte Änderung, aber die Verwendung dieser Shortcodes in Ihrem Inhalt zeigt die entsprechenden KI-Offenlegungselemente an.
  - **Empfohlener Wert:** Verwenden Sie diese Shortcodes, um spezifische Offenlegungen einzubetten, wo globale Einstellungen möglicherweise nicht ausreichen.
  - **Händlerszenario / Beispiel:** Sie könnten ein Produkt haben, bei dem nur ein bestimmter Absatz der Beschreibung KI-generiert wurde. Sie können diesen Absatz mit einem Shortcode umgeben, um ein kleines Badge daneben anzuzeigen.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 AI Act > Massenproduktverwaltung (AdminMyAiActBulkController)

- **Bildschirmname & Menüpfad:** Navigieren Sie in Ihrem PrestaShop Back Office zu **AI Act > Massenproduktverwaltung**.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm bietet eine leistungsstarke Rasteransicht zur gleichzeitigen Verwaltung des AI Act-Status mehrerer Produkte.
  - **Produktliste:** Zeigt eine Liste all Ihrer Produkte mit Spalten für Produktname, ID und, am wichtigsten, deren AI Act-Status.
  - **Filter & Suche:** Ermöglicht das Filtern von Produkten nach verschiedenen Kriterien (z. B. Kategorie, Lieferant, AI Act-Status), um schnell bestimmte Artikel zu finden.
  - **Massenaktionen:**
    - **Als KI-generiert markieren:** Wählen Sie mehrere Produkte aus und wenden Sie gleichzeitig das Flag „KI-generiert“ an.
    - **Als nicht KI-generiert markieren:** Entfernen Sie das Flag „KI-generiert“ von ausgewählten Produkten.
    - **Spezifische AI Act-Tags anwenden:** Weisen Sie mehreren Produkten benutzerdefinierte Tags oder Regeln (falls konfiguriert) zu.
- **Auswirkung von Änderungen:**
  - Wenn Sie Produkte als KI-generiert markieren, erscheinen die Front-Office-Badges und Offenlegungen für diese Produkte gemäß den allgemeinen Einstellungen Ihres Moduls.
  - Das Entfernen der Markierung von Produkten entfernt diese Offenlegungen.
  - Das Anwenden von Tags ermöglicht eine granularere Kontrolle über spezifische Offenlegungstypen oder Nachrichten.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Nach dem Import neuer Produkte oder der Generierung von Inhalten mit KI verwenden Sie die Filter, um diese Produkte schnell zu finden.
  2. Wählen Sie alle relevanten Produkte über die Kontrollkästchen aus.
  3. Verwenden Sie die Massenaktion „Als KI-generiert markieren“, um das Flag anzuwenden.
  4. Überprüfen Sie regelmäßig Produkte, um sicherzustellen, dass ihr AI Act-Status korrekt ist.

#### 2.2.2 AI Act > Audit-Protokolle (AdminMyAiActLogsController)

- **Bildschirmname & Menüpfad:** Navigieren Sie in Ihrem PrestaShop Back Office zu **AI Act > Audit-Protokolle**.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt ein detailliertes Protokoll aller AI Act-bezogenen Ereignisse und Offenlegungen an, vorausgesetzt, die Einstellung „Audit-Log aktivieren“ ist aktiv.
  - **Protokolleinträge:** Jeder Eintrag enthält typischerweise:
    - **Zeitstempel:** Wann das Ereignis aufgetreten ist.
    - **Aktion/Ereignis:** Was passiert ist (z. B. „Produkt X als KI gekennzeichnet“, „KI-Badge für Produkt Y angezeigt“).
    - **Benutzer/System:** Wer die Aktion initiiert hat (z. B. „Admin-Benutzer Z“, „CRON-Job“, „Front-Office-Besucher“).
    - **Produkt-ID/Kontext:** Welches Produkt oder welche Entität betroffen war.
    - **Details:** Alle zusätzlichen relevanten Informationen.
  - **Filter & Suche:** Ermöglicht das Filtern von Protokolleinträgen nach Datumsbereich, Ereignistyp oder Produkt, um spezifische Vorfälle zu untersuchen.
- **Auswirkung von Änderungen:** Dieser Bildschirm dient nur zur Ansicht; Sie können hier keine direkten Änderungen vornehmen. Er dient als historische Aufzeichnung.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Überprüfen Sie regelmäßig die Audit-Protokolle, insbesondere nach wesentlichen Änderungen an den AI Act-Einstellungen oder Produktdaten, um sicherzustellen, dass alles wie erwartet funktioniert.
  2. Im Falle eines Compliance-Audits oder einer Kundenanfrage verwenden Sie dieses Protokoll, um spezifische Offenlegungsereignisse abzurufen.

#### 2.2.3 AI Act > Layout Studio (AdminMyAiActLayoutsController - *Abgeleitet aus Vorlagen und Beschreibung*)

- **Bildschirmname & Menüpfad:** Navigieren Sie in Ihrem PrestaShop Back Office zu **AI Act > Layout Studio** (oder ähnlich, basierend auf der Modulmenüstruktur).
- **Verfügbare Aktionen & Einstellungen:** Auf diesem Bildschirm gestalten und verwalten Sie das visuelle Erscheinungsbild Ihrer KI-Offenlegungs-Badges und anderer Elemente.
  - **Layout-Liste:** Eine Tabelle, die alle vorhandenen Badge-Layouts anzeigt.
  - **Neues Layout hinzufügen / Layout bearbeiten:**
    - **Layout-Name:** Ein beschreibender Name für Ihr Layout.
    - **Badge-Typ:** Wählen Sie zwischen nur Symbol, nur Text oder Symbol + Text.
    - **Symbolauswahl:** Wählen Sie aus einem Katalog von Symbolen oder laden Sie Ihr eigenes hoch.
    - **Textinhalt:** Geben Sie den Text ein, der auf dem Badge angezeigt werden soll (z. B. „KI-generiert“).
    - **Stiloptionen:**
      - **Farben:** Hintergrundfarbe, Textfarbe, Symbolfarbe.
      - **Ränder:** Randstil, Breite, Farbe.
      - **Schatten:** Schlagschatteneffekte.
      - **Verläufe:** Hintergrundverlaufsoptionen.
      - **Abstand & Ränder:** Abstände um das Badge.
      - **Schrifteinstellungen:** Schriftgröße, -stärke.
    - **Vorschau:** Eine Live-Vorschau Ihres Badges während der Gestaltung.
- **Auswirkung von Änderungen:**
  - Das Erstellen neuer Layouts gibt Ihnen mehr Optionen für das Aussehen Ihrer KI-Offenlegungen.
  - Das Bearbeiten eines vorhandenen Layouts aktualisiert sofort das Erscheinungsbild aller Badges, die dieses Layout verwenden, in Ihrem gesamten Shop.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Beginnen Sie mit einem Standardlayout und passen Sie es an die Ästhetik Ihrer Marke an.
  2. Erstellen Sie bei Bedarf verschiedene Layouts für verschiedene Arten von KI-Offenlegungen (z. B. eines für KI-Bilder, ein anderes für KI-Text).
  3. Testen Sie Layouts auf verschiedenen Geräten, um sicherzustellen, dass sie sichtbar sind und gut aussehen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | AI Act Compliance aktivieren | JA | Hauptschalter für alle Modulfunktionen. |
|  | KI-Offenlegungs-Badge auf Produktseiten anzeigen | JA | Zeigt Badge auf Produktdetailseiten an. |
|  | KI-Offenlegungs-Badge in Produktlisten anzeigen | JA | Zeigt Badge auf Kategorie-/Suchseiten an. |
|  | Position des KI-Offenlegungs-Badges (Produktseite) | *Theme-abhängig* | Steuert die Platzierung des Badges auf Produktseiten. |
|  | Layout des KI-Offenlegungs-Badges | *Anpassbar* | Visueller Stil des KI-Badges. |
|  | Link zur KI-Richtlinienseite | *Ihre CMS-Seiten-URL* | Link zur KI-Richtlinie Ihres Shops. |
|  | KI-Offenlegungs-Banner aktivieren | JA | Aktiviert ein shopweites Informationsbanner. |
|  | Position des KI-Offenlegungs-Banners (Hook) | `displayHeader` | Platzierung des Banners (z. B. oben/unten auf der Seite). |
|  | Inhalt des KI-Offenlegungs-Banners | *Anpassbarer Text/HTML* | Im Banner angezeigte Nachricht. |
|  | Menschliche Fallback-Informationen aktivieren | JA | Zeigt Nachricht über menschliche Aufsicht an. |
|  | Menschliche Fallback-Nachricht | *Anpassbarer Text* | Inhalt der menschlichen Fallback-Nachricht. |
|  | Audit-Log aktivieren | JA | Zeichnet alle AI Act-bezogenen Aktionen für Compliance auf. |
|  | REST API aktivieren | NEIN | Aktiviert API für externe Integrationen. |
|  | API-Schlüsselverwaltung | *N/A* | API-Schlüssel für sicheren Zugriff generieren/verwalten. |
|  | Wasserzeichen-CRON aktivieren | NEIN | Automatische Wasserzeichen für KI-generierte Bilder. |
|  | Wasserzeichen-Bild/Text | *N/A* | Definiert den Wasserzeicheninhalt. |
|  | Shortcode-Liste & Verwendung | *N/A* | Bietet Shortcodes für granulare Inhalts-Offenlegung. |
| **AI Act > Massenproduktverwaltung** | Als KI-generiert markieren (Massenaktion) | N/A | Kennzeichnet mehrere Produkte als KI-generiert. |
|  | Als nicht KI-generiert markieren (Massenaktion) | N/A | Entfernt das KI-generiert-Flag von Produkten. |
|  | Spezifische AI Act-Tags anwenden (Massenaktion) | N/A | Weist Produkten benutzerdefinierte Offenlegungs-Tags zu. |
| **AI Act > Audit-Protokolle** | Protokolleinträge anzeigen | N/A | Bietet eine historische Aufzeichnung von AI Act-Ereignissen. |
| **AI Act > Layout Studio** | Layouts erstellen/bearbeiten | N/A | Entwirft benutzerdefinierte visuelle Stile für KI-Badges. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul konfiguriert, sehe aber keine KI-Badges oder Banner in meinem Shop. Was ist falsch?**
A1:

- **Hauptschalter prüfen:** Stellen Sie zunächst sicher, dass „AI Act Compliance aktivieren“ in der Hauptkonfiguration des Moduls auf JA gesetzt ist.
- **Individuelle Funktionsschalter:** Überprüfen Sie, ob „KI-Offenlegungs-Badge auf Produktseiten anzeigen“, „KI-Offenlegungs-Badge in Produktlisten anzeigen“ und „KI-Offenlegungs-Banner aktivieren“ ebenfalls auf JA gesetzt sind, wenn Sie diese Funktionen aktiv haben möchten.
- **Produktstatus:** Damit Badges erscheinen, müssen Produkte explizit als „KI-generiert“ markiert sein. Überprüfen Sie dies auf der Produktbearbeitungsseite (unter einem dedizierten Tab) oder über „AI Act > Massenproduktverwaltung“.
- **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung > Cache leeren) und Ihren Browser-Cache. Manchmal werden alte Inhalte angezeigt.
- **Theme-Kompatibilität:** Obwohl das Modul auf Kompatibilität ausgelegt ist, können einige stark angepasste Themes geringfügige Anpassungen erfordern. Überprüfen Sie die Entwicklerkonsole Ihres Browsers auf JavaScript-Fehler.

**F2: Das KI-Badge erscheint, sieht aber mit dem Design meines Themes nicht gut aus. Wie kann ich sein Aussehen ändern?**
A2:

- **Layout Studio:** Navigieren Sie in Ihrem Back Office zu **AI Act > Layout Studio**. Hier können Sie Badge-Layouts erstellen und bearbeiten. Sie haben umfangreiche Optionen für Farben, Symbole, Text, Schatten und Verläufe.
- **Layout auswählen:** Nachdem Sie ein Layout erstellt oder bearbeitet haben, kehren Sie zur Hauptkonfiguration des Moduls zurück und wählen Sie Ihr gewünschtes Layout unter „Layout des KI-Offenlegungs-Badges“ aus.
- **CSS-Überschreibungen (Erweitert):** Wenn das Layout Studio nicht genügend Anpassungsmöglichkeiten bietet, kann ein Webmaster benutzerdefiniertes CSS in Ihrem Theme verwenden, um die Standardstile des Moduls zu überschreiben (siehe Abschnitt 7.5 für CSS-Dateispeicherorte).

**F3: Wie markiere ich Produkte effizient als KI-generiert, besonders wenn ich viele habe?**
A3:

- **Massenproduktverwaltung:** Gehen Sie zu **AI Act > Massenproduktverwaltung**. Dieser Bildschirm ermöglicht es Ihnen, Ihre Produkte zu filtern und mehrere Artikel auszuwählen, um sie in einem Arbeitsgang als KI-generiert zu markieren oder die Markierung aufzuheben. Dies ist die effizienteste Methode für große Kataloge.
- **Einzelne Produktseite:** Für einzelne Produkte finden Sie beim Bearbeiten eines Produkts im Back Office einen dedizierten Tab (z. B. „AI Act Compliance“), wo Sie den KI-Status umschalten können.

**F4: Ich möchte eine detaillierte Erklärung meiner KI-Richtlinie bereitstellen. Wo soll ich sie platzieren?**
A4:

- **Dedizierte CMS-Seite:** Erstellen Sie eine neue CMS-Seite (Design > Seiten) mit einem Titel wie „Unsere KI-Transparenzrichtlinie“ oder „Wie wir KI nutzen“. Schreiben Sie hier Ihre umfassende Richtlinie.
- **Link im Modul:** Legen Sie in der Hauptkonfiguration des Moduls den „Link zur KI-Richtlinienseite“ auf die URL Ihrer neu erstellten CMS-Seite fest. Dieser Link wird dann von Bannern und Badges verwendet, um Kunden zu Ihrer Richtlinie zu leiten.

**F5: Der CRON-Job für die Wasserzeichenfunktion funktioniert nicht. Was sollte ich überprüfen?**
A5:

- **Wasserzeichen-CRON aktivieren:** Stellen Sie sicher, dass „Wasserzeichen-CRON aktivieren“ in der Modulkonfiguration auf JA gesetzt ist.
- **CRON-Job-Einrichtung:** Überprüfen Sie, ob der CRON-Job selbst auf Ihrem Server korrekt eingerichtet ist. Das Modul stellt normalerweise den genauen Befehlszeilenbefehl bereit, der in den CRON-Manager Ihres Hosting-Panels eingefügt werden muss. Wenn Sie unsicher sind, wenden Sie sich an Ihren Hosting-Anbieter oder einen Webmaster.
- **Berechtigungen:** Stellen Sie sicher, dass das Modul und die Bildordner die richtigen Schreibberechtigungen haben.
- **Fehlerprotokolle:** Überprüfen Sie die PHP-Fehlerprotokolle Ihres Servers und den PrestaShop-Debug-Modus auf verwandte Fehler.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „My AI Act Pro“ folgt der Standard-MVC-Architektur (Model-View-Controller) von PrestaShop. Es nutzt `ObjectModel` für Datenbankinteraktionen, registriert verschiedene Hooks für die Front-Office-Anzeige und enthält dedizierte Admin-Controller für Konfiguration und Datenverwaltung. Das Modul führt mehrere benutzerdefinierte Klassen ein, um spezifische Geschäftslogik im Zusammenhang mit der AI Act-Compliance zu kapseln, wie z. B. API-Verwaltung, Badge-Layout-Verwaltung und Audit-Protokollierung. Es enthält auch Front-Controller für die API- und CRON-Job-Ausführung, die externe Integrationen und geplante Aufgaben ermöglichen.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/api.php`
  - **Klassenname & übergeordnete Klasse:** `MyaiactproApiModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller verwaltet die REST-API-Endpunkte des Moduls. Er verarbeitet eingehende Anfragen (z. B. zum Kennzeichnen von Produkten als KI-generiert, zum Abrufen des KI-Status) und gibt JSON-Antworten zurück. Er ist verantwortlich für die API-Schlüsselvalidierung und das Weiterleiten von Anfragen an die entsprechenden Methoden der Klasse `AiActApi`.
- `controllers/front/cron.php`
  - **Klassenname & übergeordnete Klasse:** `MyaiactproCronModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller dient als Endpunkt für die CRON-Jobs des Moduls, insbesondere für die Wasserzeichenanwendung. Wenn er über eine geplante Aufgabe aufgerufen wird, löst er den Wasserzeichenprozess für KI-generierte Bilder aus.
- `controllers/front/index.php`
  - **Klassenname & übergeordnete Klasse:** `MyaiactproIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Ein Platzhalter oder Standard-Front-Controller. In vielen Modulen könnte dies eine Standardroute behandeln oder umleiten. Für dieses Modul könnte es ein Fallback sein oder für spezifische, einfache Front-Office-Interaktionen verwendet werden, die nicht von `api.php` oder `cron.php` abgedeckt werden.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminMyAiActBulkController.php`
  - **Klassenname & übergeordnete Klasse:** `AdminMyAiActBulkController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Zugänglich über **AI Act > Massenproduktverwaltung**. Verwaltet die `product`-Entität indirekt, indem es Massenaktualisierungen ihres AI Act-Status ermöglicht.
  - **Verantwortlichkeit:** Bietet eine Rasteroberfläche zum Auflisten von Produkten und zum Anwenden von Massenaktionen im Zusammenhang mit der AI Act-Compliance (z. B. Kennzeichnen von Produkten als KI-generiert, Anwenden von Tags). Es verarbeitet Formularübermittlungen für Massenaktualisierungen.
- `controllers/admin/AdminMyAiActLogsController.php`
  - **Klassenname & übergeordnete Klasse:** `AdminMyAiActLogsController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Zugänglich über **AI Act > Audit-Protokolle**. Verwaltet die Entität `aiact_audit_log`.
  - **Verantwortlichkeit:** Zeigt eine paginierte Liste von Audit-Protokolleinträgen an, die eine historische Aufzeichnung von AI Act-bezogenen Ereignissen bieten. Es verwaltet das Filtern und Anzeigen von Protokolldetails.
- `controllers/admin/index.php`
  - **Klassenname & übergeordnete Klasse:** `MyaiactproAdminIndexModuleAdminController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Typischerweise ein Standard- oder einführender Admin-Controller für den Haupteintrag des Modulmenüs.
  - **Verantwortlichkeit:** Kann als Weiterleitung zur Hauptkonfiguration oder als Dashboard für das Modul dienen.

### 4.3 Kernklassen & Modelle (`classes/`)

- `classes/AiActApi.php`
  - **Datenbanktabelle:** Keine direkte Tabelleninteraktion, aber interagiert mit `AiActApiKey` und `AiActAuditLog`.
  - **Erweitert `ObjectModel`:** Nein.
  - **Wichtige öffentliche Methoden:** Verarbeitet die API-Anforderungsanalyse, Authentifizierung und leitet Aktionen zur Aktualisierung des Produkt-KI-Status weiter.
- `classes/AiActApiDocumentation.php`
  - **Datenbanktabelle:** Keine.
  - **Erweitert `ObjectModel`:** Nein.
  - **Wichtige öffentliche Methoden:** Generiert und stellt Dokumentation für die REST-API des Moduls bereit, typischerweise zur Anzeige im Back Office.
- `classes/AiActApiKey.php`
  - **Datenbanktabelle:** `ps_myaiactpro_api_key`
  - **Erweitert `ObjectModel`:** Ja.
  - **`$definition`-Felder:** `id_myaiactpro_api_key`, `key_value`, `description`, `active`, `date_add`, `date_upd`.
  - **Wichtige öffentliche Methoden:** Verwaltet die Erstellung, den Abruf, die Validierung und das Löschen von API-Schlüsseln für den sicheren API-Zugriff.
- `classes/AiActAuditLog.php`
  - **Datenbanktabelle:** `ps_myaiactpro_audit_log`
  - **Erweitert `ObjectModel`:** Ja.
  - **`$definition`-Felder:** `id_myaiactpro_audit_log`, `id_employee`, `id_customer`, `id_product`, `action`, `details`, `ip_address`, `date_add`.
  - **Wichtige öffentliche Methoden:** Zeichnet Audit-Protokolleinträge für AI Act-Compliance-Aktionen auf und ruft sie ab.
- `classes/AiActBadgeLayout.php`
  - **Datenbanktabelle:** `ps_myaiactpro_badge_layout`
  - **Erweitert `ObjectModel`:** Ja.
  - **`$definition`-Felder:** `id_myaiactpro_badge_layout`, `name`, `type`, `icon_class`, `text_content`, `styles_json`, `active`.
  - **Wichtige öffentliche Methoden:** Verwaltet die Erstellung, Speicherung und den Abruf benutzerdefinierter visueller Layouts für KI-Offenlegungs-Badges.
- `classes/AiActConfigureUi.php`
  - **Datenbanktabelle:** Keine.
  - **Erweitert `ObjectModel`:** Nein.
  - **Wichtige öffentliche Methoden:** Hilfsklasse zum Erstellen und Rendern der Konfigurationsformulare des Moduls im Back Office, abstrahiert UI-Elemente.
- `classes/AiActDisplayResolver.php`
  - **Datenbanktabelle:** Keine.
  - **Erweitert `ObjectModel`:** Nein.
  - **Wichtige öffentliche Methoden:** Bestimmt, welche AI Act-Offenlegungen (Badges, Banner usw.) im Front Office angezeigt werden sollen, basierend auf Moduleinstellungen, Produktstatus und aktuellem Kontext.
- `classes/AiActFlag.php`
  - **Datenbanktabelle:** `ps_myaiactpro_product_flag` (oder ähnlich, verknüpft Produkte mit KI-Status)
  - **Erweitert `ObjectModel`:** Ja (wahrscheinlich, oder eine benutzerdefinierte Klasse, die Produkt-KI-Statusbeziehungen verwaltet).
  - **`$definition`-Felder:** `id_product`, `is_ai_generated`, `id_myaiactpro_badge_layout`, `date_add`, `date_upd`.
  - **Wichtige öffentliche Methoden:** Verwaltet den KI-generierten Status einzelner Produkte und deren zugehörige Badge-Layouts.
- `classes/AiActIconCatalog.php`
  - **Datenbanktabelle:** Keine.
  - **Erweitert `ObjectModel`:** Nein.
  - **Wichtige öffentliche Methoden:** Bietet eine Liste oder einen Katalog verfügbarer Symbole zur Verwendung in Badge-Layouts, oft integriert mit Font Awesome oder ähnlichen Symbolbibliotheken.
- `classes/AiActShortcode.php`
  - **Datenbanktabelle:** Keine.
  - **Erweitert `ObjectModel`:** Nein.
  - **Wichtige öffentliche Methoden:** Verarbeitet und rendert benutzerdefinierte Shortcodes, die in Inhalte eingebettet sind, und ersetzt sie durch KI-Offenlegungselemente.
- `classes/AiActTagRule.php`
  - **Datenbanktabelle:** `ps_myaiactpro_tag_rule` (oder ähnlich für benutzerdefinierte Tags/Regeln)
  - **Erweitert `ObjectModel`:** Ja.
  - **`$definition`-Felder:** `id_myaiactpro_tag_rule`, `name`, `description`, `badge_layout_id`, `active`.
  - **Wichtige öffentliche Methoden:** Verwaltet benutzerdefinierte Regeln oder Tags, die auf Produkte angewendet werden können, um spezifischere KI-Offenlegungen über ein einfaches „KI-generiert“-Flag hinaus zu ermöglichen.
- `classes/index.php`
  - **Datenbanktabelle:** Keine.
  - **Erweitert `ObjectModel`:** Nein.
  - **Wichtige öffentliche Methoden:** Typischerweise eine leere Datei, um das Auflisten von Verzeichnissen zu verhindern.

### 4.4 JavaScript-Assets (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office (wahrscheinlich für die Produktsuche in der Massenverwaltung).
  - **Beschreibung:** Bietet Autocomplete-Funktionalität für Eingabefelder, typischerweise in Admin-Formularen zur Suche nach Produkten, Kategorien oder anderen Entitäten verwendet.
- `views/js/admin_api.js`
  - **Geltungsbereich:** Back-Office (API & Integrationen-Tab).
  - **Beschreibung:** Verwaltet clientseitige Interaktionen für die API-Schlüsselverwaltungs-Oberfläche, einschließlich des Generierens neuer Schlüssel, des Widerrufens von Schlüsseln und des Anzeigens von API-Dokumentations-Modals.
- `views/js/admin_icon_picker.js`
  - **Geltungsbereich:** Back-Office (Layout Studio).
  - **Beschreibung:** Verwaltet die Symbolauswahl-Oberfläche innerhalb des Layout Studios, die es Administratoren ermöglicht, Symbole für Badges zu durchsuchen und auszuwählen.
- `views/js/admin_layouts.js`
  - **Geltungsbereich:** Back-Office (Layout Studio).
  - **Beschreibung:** Treibt die Layout Studio-Oberfläche an, verwaltet Echtzeit-Vorschau-Updates, Stil-Anpassungen (Farben, Schatten, Verläufe) und Formularübermittlungen für Badge-Layouts.
- `views/js/front.js`
  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Enthält clientseitige Logik zum Anzeigen und Interagieren mit KI-Offenlegungselementen im Front Office. Dies könnte umfassen:
    - Initialisieren von Badge-Tooltips oder Popovers.
    - Behandeln von Klickereignissen auf Badges, um weitere Informationen anzuzeigen oder zur KI-Richtlinienseite zu navigieren.
    - Sicherstellen der mobilen Responsivität von Offenlegungselementen.
- `views/js/tinymce_ai_button.js`
  - **Geltungsbereich:** Back-Office (Produkt-/CMS-Editor).
  - **Beschreibung:** Integriert eine benutzerdefinierte Schaltfläche in den TinyMCE-Editor (verwendet für Produktbeschreibungen und CMS-Seiten), um AI Act-Shortcodes einfach einzufügen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Stile für die Autocomplete-Such-Eingabefelder und deren Dropdown-Ergebnisse, verwendet in Admin-Formularen.
- `views/css/admin.css`
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Beschreibung:** Enthält allgemeine Styling-Regeln für die Back-Office-Oberflächen des Moduls, einschließlich der Konfigurationsseite, Massenverwaltung, Audit-Protokolle und Layout Studio. Entwickler können Klassen wie `.myaiactpro-admin-form`, `.myaiactpro-layout-preview` usw. überschreiben.
- `views/css/front.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Beschreibung:** Bietet das Standard-Styling für KI-Offenlegungs-Badges, Banner und andere Front-Office-Elemente. Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können, sind:
    - `.myaiactpro-badge` (für den Haupt-Badge-Container)
    - `.myaiactpro-badge-icon` (für das Symbol innerhalb des Badges)
    - `.myaiactpro-badge-text` (für den Text innerhalb des Badges)
    - `.myaiactpro-banner` (für das shopweite Offenlegungs-Banner)
    - `.myaiactpro-additional-info` (für zusätzliche Informationsblöcke)
    - `.myaiactpro-human-fallback` (für menschliche Fallback-Nachrichten)

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `hook/additional_info.tpl`
  - **Hook:** Potenziell `displayProductExtraContent` oder benutzerdefinierter Hook.
  - **Ausgabe:** Rendert einen zusätzlichen Informationsblock auf der Produktseite, oft verwendet für detaillierte KI-Offenlegungen oder Richtlinienlinks.
- `hook/ai_badge.tpl`
  - **Hook:** `displayProductListReviews`, `displayProductButtons`, `displayProductPriceBlock` oder benutzerdefinierte Hooks.
  - **Ausgabe:** Rendert das KI-Offenlegungs-Badge auf Produktseiten oder in Listen, unter Verwendung des ausgewählten Layouts.
- `hook/banner.tpl`
  - **Hook:** `displayHeader`, `displayFooter`.
  - **Ausgabe:** Rendert das shopweite KI-Offenlegungs-Banner.
- `hook/human_fallback.tpl`
  - **Hook:** Potenziell `displayProductExtraContent` oder benutzerdefinierter Hook.
  - **Ausgabe:** Rendert die menschliche Fallback-Nachricht auf relevanten Seiten.
- `hook/shortcode_badge.tpl`
  - **Hook:** Dynamisch gerendert von der Klasse `AiActShortcode`.
  - **Ausgabe:** Rendert ein spezifisches KI-Badge, wenn ein Shortcode im Inhalt verwendet wird.

#### Admin-Templates (`views/templates/admin/`)

- `admin/api.tpl`
  - **Zweck:** Rendert das API- & Integrations-Konfigurationspanel, einschließlich API-Schlüsselverwaltung und Dokumentation.
- `admin/bulk_intro.tpl`
  - **Zweck:** Bietet eine einführende Nachricht oder Anweisungen für den Bildschirm zur Massenproduktverwaltung.
- `admin/configure.tpl`
  - **Zweck:** Die Hauptkonfigurationsvorlage für das Modul, gerendert von `getContent()`, enthält allgemeine Einstellungen, Funktionsschalter und Links zu anderen Admin-Bildschirmen.
- `admin/configure_shell.tpl`
  - **Zweck:** Eine Wrapper- oder Shell-Vorlage für die Hauptkonfigurationsseite, die ein konsistentes Layout bietet.
- `admin/cron_box.tpl`
  - **Zweck:** Zeigt Informationen zur CRON-Job-Einrichtung an, einschließlich des CRON-Befehls.
- `admin/layouts_form.tpl`
  - **Zweck:** Rendert das Formular zum Erstellen oder Bearbeiten eines KI-Badge-Layouts innerhalb des Layout Studios.
- `admin/layouts_list.tpl`
  - **Zweck:** Zeigt die Liste der vorhandenen KI-Badge-Layouts im Layout Studio an.
- `admin/mass_settings.tpl`
  - **Zweck:** Rendert die Oberfläche zum Anwenden von Masseneinstellungen oder -aktionen auf Produkte, verwendet im Massenverwaltungs-Controller.
- `admin/overrides_entity.tpl`
  - **Zweck:** Wahrscheinlich zur Verwaltung spezifischer Überschreibungen oder Ausnahmen für AI Act-Regeln auf Entitätsbasis (z. B. pro Kategorie, pro Hersteller).
- `admin/overrides_fields.tpl`
  - **Zweck:** Rendert Formularfelder zum Definieren von Überschreibungsregeln.
- `admin/overrides_list.tpl`
  - **Zweck:** Zeigt eine Liste der konfigurierten Überschreibungsregeln an.
- `admin/partials/gradient_editor.tpl`
  - **Zweck:** Eine Teilvorlage für den Farbverlaufs-Farbwähler/-Editor, der im Layout Studio verwendet wird.
- `admin/partials/icon_picker.tpl`
  - **Zweck:** Eine Teilvorlage für die Symbolauswahl-Oberfläche, die im Layout Studio verwendet wird.
- `admin/partials/shadow_editor.tpl`
  - **Zweck:** Eine Teilvorlage für den Schatteneffekt-Editor, der im Layout Studio verwendet wird.
- `admin/product_tab.tpl`
  - **Zweck:** Rendert den Inhalt des dedizierten „AI Act Compliance“-Tabs innerhalb der PrestaShop-Produktbearbeitungsseite.
- `admin/shortcodes.tpl`
  - **Zweck:** Zeigt die Liste der verfügbaren Shortcodes und deren Verwendungsanweisungen an.
- `admin/_api_documentation_modal.tpl`
  - **Zweck:** Rendert den Inhalt für ein modales Popup, das die API-Dokumentation anzeigt.

#### Front-Office-Templates (`views/templates/front/`)

- Keine explizit als eigenständige Seitenvorlagen aufgeführt, was darauf hindeutet, dass Front-Office-Inhalte hauptsächlich über Hooks gerendert werden.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- `ps_myaiactpro_api_key`: Speichert API-Schlüssel für die REST-API des Moduls.
  - `id_myaiactpro_api_key` (PK)
  - `key_value` (VARCHAR)
  - `description` (TEXT)
  - `active` (TINYINT)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_myaiactpro_audit_log`: Zeichnet AI Act-bezogene Ereignisse auf.
  - `id_myaiactpro_audit_log` (PK)
  - `id_employee` (INT)
  - `id_customer` (INT)
  - `id_product` (INT)
  - `action` (VARCHAR)
  - `details` (TEXT)
  - `ip_address` (VARCHAR)
  - `date_add` (DATETIME)
- `ps_myaiactpro_badge_layout`: Speichert benutzerdefinierte visuelle Layouts für KI-Badges.
  - `id_myaiactpro_badge_layout` (PK)
  - `name` (VARCHAR)
  - `type` (VARCHAR)
  - `icon_class` (VARCHAR)
  - `text_content` (VARCHAR)
  - `styles_json` (TEXT)
  - `active` (TINYINT)
- `ps_myaiactpro_product_flag`: Verknüpft Produkte mit ihrem KI-generierten Status und dem gewählten Badge-Layout.
  - `id_product` (PK, INT)
  - `is_ai_generated` (TINYINT)
  - `id_myaiactpro_badge_layout` (INT, FK zu `ps_myaiactpro_badge_layout`)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_myaiactpro_tag_rule`: Speichert benutzerdefinierte AI Act-Tag-Regeln.
  - `id_myaiactpro_tag_rule` (PK)
  - `name` (VARCHAR)
  - `description` (TEXT)
  - `badge_layout_id` (INT, FK zu `ps_myaiactpro_badge_layout`)
  - `active` (TINYINT)
- Konfigurationseinträge in `ps_configuration`: Moduleinstellungen werden hier gespeichert (z. B. `MYAIACTPRO_ENABLED`, `MYAIACTPRO_BADGE_LAYOUT_ID`, `MYAIACTPRO_POLICY_LINK`).

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck | Gerenderte Templates |
| --- | --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | CSS/JS injizieren, oberes Banner rendern. | `hook/banner.tpl` (falls konfiguriert) |
| `displayFooter` | Am Ende jeder Seite. | Unteres Banner rendern, JS injizieren. | `hook/banner.tpl` (falls konfiguriert) |
| `displayProductAdditionalInfo` | Auf der Produktseite, normalerweise unter der Beschreibung. | Zusätzliche KI-Offenlegungsinformationen anzeigen. | `hook/additional_info.tpl`, `hook/human_fallback.tpl` |
| `displayProductListReviews` | In Produktlisten, in der Nähe von Produktname/Bild. | KI-Badge auf Produkt-Thumbnails anzeigen. | `hook/ai_badge.tpl` |
| `displayProductButtons` | Auf der Produktseite, in der Nähe des „In den Warenkorb“-Buttons. | KI-Badge auf der Produktseite anzeigen. | `hook/ai_badge.tpl` |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | Einen dedizierten Tab für AI Act-Einstellungen hinzufügen. | `admin/product_tab.tpl` |
| `actionProductUpdate` | Nach der Aktualisierung eines Produkts im Back Office. | AI Act-Flags/Status für das Produkt aktualisieren. | N/A |
| `actionProductDelete` | Nach dem Löschen eines Produkts. | Zugehörige AI Act-Daten bereinigen. | N/A |
| `actionFrontControllerSetMedia` | Bevor der Front-Controller Inhalte rendert. | Front-Office-CSS/JS registrieren. | N/A |
| `actionAdminControllerSetMedia` | Bevor der Admin-Controller Inhalte rendert. | Back-Office-CSS/JS registrieren. | N/A |
| `actionRegisterShortcode` | Bei Modulinstallation/-aktualisierung. | Registriert benutzerdefinierte Shortcodes für die Inhaltsanalyse. | N/A |
| `displayBackOfficeHeader` | Im `<head>`-Bereich jeder Admin-Seite. | Admin-CSS/JS injizieren. | N/A |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „My AI Act Pro - Artificial Intelligence Compliance“ gerne zur Verfügung.

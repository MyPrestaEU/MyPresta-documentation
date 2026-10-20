---
title: "Warenkorb-Bedingungen Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Warenkorb-Bedingungen Pro von MyPresta.eu."
sidebar:
  label: "Warenkorb-Bedingungen Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Cart conditions pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/cart-conditions-pro/)
>
> ---


# Warenkorb-Bedingungen Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Warenkorb-Bedingungen Pro)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, auf dem Sie globale Verhaltensweisen festlegen und auf die spezifischen Bereiche zur Bedingungsverwaltung zugreifen.

- **Was diese Einstellung bewirkt:** Steuert das Gesamtverhalten des Moduls und bietet schnelle Links zur Verwaltung Ihrer Bedingungen.
- **Auswirkung der Änderung dieser Einstellung:** Bestimmt, wie weit die Bedingungen angewendet werden und wie bestimmte Grenzfälle behandelt werden.

#### Allgemeine Einstellungen

1. **Kunden von Bedingungen ausschließen**

   - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, bestimmte Kundengruppen oder einzelne Kunden festzulegen, die von allen von Ihnen eingerichteten Warenkorb-Bedingungen ausgenommen sind.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn aktiviert (und Kunden/Gruppen ausgewählt):* Die ausgewählten Kunden/Gruppen können immer zur Kasse gehen, unabhängig davon, ob ihr Warenkorb die Bedingungen erfüllt.
     - *Wenn deaktiviert (oder keine Kunden/Gruppen ausgewählt):* Alle Kunden unterliegen den Warenkorb-Bedingungen.
   - **Empfohlener Wert:** Standardmäßig „Aus“, es sei denn, Sie haben spezifische B2B-Kunden oder VIPs, die Sie ausnehmen möchten.
   - **Händlerszenario / Beispiel:** Sie haben eine Großhandelskundengruppe, die immer eine Sonderbehandlung erhält und nicht durch Mindestbestellwerte eingeschränkt werden sollte.
2. **Produkte von Bedingungen ausschließen**

   - **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, bestimmte Produkte festzulegen, die nicht in die Warenkorb-Bedingungen einbezogen oder von diesen beeinflusst werden. Dies ist nützlich für kostenlose Geschenke, Muster oder spezifische Werbeartikel.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn aktiviert (und Produkte ausgewählt):* Die ausgewählten Produkte werden bei der Bewertung der Warenkorb-Bedingungen ignoriert. Wenn Sie beispielsweise eine Bedingung „mindestens 3 Artikel“ haben und ein Kunde 2 reguläre Artikel + 1 ausgeschlossenen Artikel hat, könnte die Bedingung immer noch fehlschlagen.
     - *Wenn deaktiviert (oder keine Produkte ausgewählt):* Alle Produkte im Warenkorb werden bei der Bewertung der Bedingungen berücksichtigt.
   - **Empfohlener Wert:** Standardmäßig „Aus“. Nur aktivieren, wenn Sie spezifische Produkte haben, die von Bedingungen ausgenommen sein sollten.
   - **Händlerszenario / Beispiel:** Sie bieten zu jeder Bestellung ein kostenloses Musterprodukt an. Sie möchten nicht, dass dieses Muster bei einer Mindestproduktmengenbedingung berücksichtigt wird.
3. **Bestellung von Produkten mit unterschiedlichem Verfügbarkeitsdatum blockieren**

   - **Was diese Einstellung bewirkt:** Diese Option betrifft speziell Produkte mit unterschiedlichen Verfügbarkeitsdaten (z. B. Vorbestellungsartikel mit gestaffelten Veröffentlichungsterminen). Wenn aktiviert, verhindert sie, dass Kunden eine Mischung aus sofort verfügbaren und zukünftig verfügbaren Produkten im selben Warenkorb bestellen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn „An“:* Wenn der Warenkorb eines Kunden Produkte mit unterschiedlichen Verfügbarkeitsdaten enthält, wird er am Checkout gehindert. Er müsste separate Bestellungen für Artikel mit unterschiedlicher Verfügbarkeit aufgeben.
     - *Wenn „Aus“:* Kunden können Produkte mit verschiedenen Verfügbarkeitsdaten in einem einzigen Warenkorb bestellen.
   - **Empfohlener Wert:** „Aus“, es sei denn, Sie haben spezifische logistische Gründe, Bestellungen nach Verfügbarkeit zu trennen.
   - **Händlerszenario / Beispiel:** Sie verkaufen sowohl Lagerartikel als auch Vorbestellungsartikel. Um den Versand zu vereinfachen und das Zurückhalten von Bestellungen zu vermeiden, möchten Sie, dass Kunden separate Bestellungen für Vorbestellungsartikel aufgeben.

#### Links zur Bedingungsverwaltung

Unter den allgemeinen Einstellungen finden Sie Links zur Verwaltung verschiedener Arten von Bedingungen. Diese Links führen Sie zu dedizierten Verwaltungsbildschirmen.

- **Bedingungen verwalten (Allgemein):** Hier definieren Sie allgemeine Bedingungen basierend auf Produktzuordnungen, Kategorien oder anderen allgemeinen Regeln.
- **Länderbedingungen verwalten:** Definieren Sie Bedingungen, die nur für Kunden aus bestimmten Ländern gelten.
- **Mengenbedingungen verwalten:** Legen Sie Mindest- oder Höchstmengen von Produkten/Kategorien fest, die im Warenkorb erforderlich sind.
- **Wertbedingungen verwalten:** Legen Sie Mindest- oder Höchstwerte für den gesamten Warenkorb fest.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### 2.2.1 AdminCartConditionController (Back Office > Module > Warenkorb-Bedingungen Pro > Bedingungen verwalten)

Dieser Bildschirm ermöglicht es Ihnen, allgemeine Bedingungen zu definieren, oft basierend auf Produkt- oder Kategoriezuordnungen.

- **Bildschirmname & Menüpfad:** „Bedingungen verwalten“ (zugänglich von der Hauptkonfigurationsseite des Moduls).
- **Verfügbare Aktionen & Einstellungen:**
  - **Auflistungstabelle:** Zeigt alle vorhandenen allgemeinen Bedingungen mit ihren Namen, zugeordneten Produkten/Kategorien und Status an.
  - **Schaltfläche „Neue Bedingung hinzufügen“:** Ermöglicht das Erstellen einer neuen Bedingung.
    - **Bedingungsname:** Ein beschreibender Name für Ihre interne Referenz.
    - **Produkte/Kategorien:** Wählen Sie spezifische Produkte oder ganze Kategorien aus, die im Warenkorb vorhanden sein müssen (oder nicht vorhanden sein dürfen).
    - **Kundengruppen:** Wenden Sie diese Bedingung nur auf bestimmte Kundengruppen an.
    - **Mindest-/Höchstmenge:** Definieren Sie einen Bereich für die Anzahl der ausgewählten Produkte/Kategorien.
    - **Mindest-/Höchstwert:** Definieren Sie einen Bereich für den Gesamtwert der ausgewählten Produkte/Kategorien.
    - **Nachricht:** Die Nachricht, die dem Kunden angezeigt wird, wenn die Bedingung nicht erfüllt ist.
    - **Aktiv:** Aktivieren oder deaktivieren Sie die Bedingung.
  - **Schaltflächen „Bearbeiten/Löschen“:** Vorhandene Bedingungen ändern oder entfernen.
- **Auswirkung von Änderungen:**
  - Das Hinzufügen einer neuen Bedingung wendet diese Regel sofort auf die Warenkörbe der Kunden an.
  - Das Ändern einer Bedingung aktualisiert deren Kriterien und Nachricht.
  - Das Löschen einer Bedingung entfernt die Einschränkung.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Überprüfen Sie Ihre Bedingungen regelmäßig, insbesondere nach dem Hinzufügen neuer Produkte, Kategorien oder dem Ausführen von Aktionen, um sicherzustellen, dass sie mit Ihrer aktuellen Verkaufsstrategie übereinstimmen.

#### 2.2.2 AdminCartAssociationsConditionController (Back Office > Module > Warenkorb-Bedingungen Pro > Bedingungen verwalten > (Spezifische Bedingung) > Zuordnungen)

Dieser Bildschirm wird typischerweise beim Bearbeiten einer allgemeinen Bedingung aufgerufen und ermöglicht es Ihnen, festzulegen, welche Produkte oder Kategorien mit dieser Bedingung *verknüpft* sind.

- **Bildschirmname & Menüpfad:** Wird durch Bearbeiten einer Bedingung unter „Bedingungen verwalten“ aufgerufen.
- **Verfügbare Aktionen & Einstellungen:**
  - **Produkte/Kategorien suchen & auswählen:** Tools zum Suchen und Hinzufügen spezifischer Produkte oder ganzer Kategorien, die Teil dieser Bedingung sind.
  - **Liste der ausgewählten Produkte/Kategorien:** Zeigt alle Artikel an, die derzeit mit der Bedingung verknüpft sind.
  - **Schaltfläche „Entfernen“:** Entfernt einen Artikel aus der Zuordnung.
- **Auswirkung von Änderungen:** Wirkt sich direkt darauf aus, welche Produkte oder Kategorien von der übergeordneten Bedingung bewertet werden. Wenn eine Bedingung beispielsweise besagt: „Warenkorb muss mindestens 2 Artikel aus der Kategorie ‚Elektronik‘ enthalten“, wird auf diesem Bildschirm definiert, welche Produkte für diese spezifische Bedingung zu dieser Kategorie „Elektronik“ gehören.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Stellen Sie beim Erstellen oder Aktualisieren einer Bedingung sicher, dass alle relevanten Produkte und Kategorien korrekt zugeordnet sind.

#### 2.2.3 AdminCartCountryConditionController (Back Office > Module > Warenkorb-Bedingungen Pro > Länderbedingungen verwalten)

Dieser Bildschirm ermöglicht es Ihnen, Bedingungen zu definieren, die spezifisch für das Versandland des Kunden sind.

- **Bildschirmname & Menüpfad:** „Länderbedingungen verwalten“ (zugänglich von der Hauptmodulkonfigurationsseite).
- **Verfügbare Aktionen & Einstellungen:**
  - **Auflistungstabelle:** Zeigt vorhandene länderspezifische Bedingungen an.
  - **Schaltfläche „Neue Bedingung hinzufügen“:**
    - **Land:** Wählen Sie das Zielland aus.
    - **Mindest-/Höchstmenge:** Für alle Produkte im Warenkorb oder spezifische Produkte/Kategorien.
    - **Mindest-/Höchstwert:** Für den gesamten Warenkorbwert.
    - **Nachricht:** Die Nachricht, die angezeigt wird, wenn die Bedingung nicht erfüllt ist.
    - **Aktiv:** Aktivieren oder deaktivieren.
- **Auswirkung von Änderungen:** Wendet spezifische Warenkorbregeln nur auf Kunden an, deren Lieferadresse sich im ausgewählten Land befindet.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Nützlich für internationale Shops mit unterschiedlichen Versandkosten, Zollbestimmungen oder Marktstrategien pro Land.

#### 2.2.4 AdminCartQuantityConditionController (Back Office > Module > Warenkorb-Bedingungen Pro > Mengenbedingungen verwalten)

Dieser Bildschirm konzentriert sich auf Bedingungen, die sich auf die Gesamtzahl der Artikel im Warenkorb oder die Menge bestimmter Artikel/Kategorien beziehen.

- **Bildschirmname & Menüpfad:** „Mengenbedingungen verwalten“ (zugänglich von der Hauptmodulkonfigurationsseite).
- **Verfügbare Aktionen & Einstellungen:**
  - **Auflistungstabelle:** Zeigt alle mengenbasierten Bedingungen an.
  - **Schaltfläche „Neue Bedingung hinzufügen“:**
    - **Bedingungsname:**
    - **Mindest-/Höchstgesamtmenge:** Für den gesamten Warenkorb.
    - **Mindest-/Höchstmenge spezifischer Produkte/Kategorien:** Wählen Sie Artikel aus und legen Sie Mengenregeln für diese fest.
    - **Kundengruppen:** Auf bestimmte Gruppen anwenden.
    - **Nachricht:**
    - **Aktiv:**
- **Auswirkung von Änderungen:** Erzwingt Regeln basierend auf der Anzahl der Artikel im Warenkorb, was zur Förderung von Großeinkäufen oder zur Bestandsverwaltung verwendet werden kann.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie dies für „Kaufe X, erhalte Y“-Aktionen, Mindestbestellmengen (MOQ) für den Großhandel oder um sicherzustellen, dass Kunden einen bestimmten Schwellenwert für kostenlosen Versand erreichen.

#### 2.2.5 AdminCartValueConditionController (Back Office > Module > Warenkorb-Bedingungen Pro > Wertbedingungen verwalten)

Dieser Bildschirm dient zum Festlegen von Bedingungen basierend auf dem gesamten Geldwert des Warenkorbs des Kunden.

- **Bildschirmname & Menüpfad:** „Wertbedingungen verwalten“ (zugänglich von der Hauptmodulkonfigurationsseite).
- **Verfügbare Aktionen & Einstellungen:**
  - **Auflistungstabelle:** Zeigt vorhandene wertbasierte Bedingungen an.
  - **Schaltfläche „Neue Bedingung hinzufügen“:**
    - **Bedingungsname:**
    - **Mindest-/Höchstgesamtwarenkorbwert:** Legen Sie einen Bereich für den Wert des gesamten Warenkorbs fest.
    - **Kundengruppen:**
    - **Nachricht:**
    - **Aktiv:**
- **Auswirkung von Änderungen:** Erzwingt Regeln basierend auf dem Geldwert des Warenkorbs, was sich direkt auf den durchschnittlichen Bestellwert auswirkt.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Ideal zum Festlegen eines Mindestbestellwerts für kostenlosen Versand oder eines allgemeinen Mindestbestellwerts zur Sicherstellung der Rentabilität.

#### 2.2.6 index.php (cartcon/controllers/admin/index.php)

Diese Datei ist eine Standard-PrestaShop-Praxis, um die Verzeichnisauflistung zu verhindern, und stellt keinen konfigurierbaren Bildschirm dar. Sie enthält lediglich `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;`, um umzuleiten, wenn jemand versucht, direkt auf das Verzeichnis zuzugreifen.

### 2.3 Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Kunden von Bedingungen ausschließen | Aus | Bestimmte Kunden/Gruppen von allen Bedingungen ausnehmen. |
|  | Produkte von Bedingungen ausschließen | Aus | Bestimmte Produkte von allen Bedingungen ausnehmen. |
|  | Bestellung von Produkten mit unterschiedlichem Verfügbarkeitsdatum blockieren | Aus | Gemischte Bestellungen von Lager- und Vorbestellungsartikeln verhindern. |
| **Bedingungen verwalten** | Bedingungsname | Benutzerdefiniert | Interne Bezeichnung für die Bedingung. |
|  | Produkte/Kategorien | Benutzerdefiniert | Artikel/Kategorien auswählen, die erforderlich oder eingeschränkt sind. |
|  | Kundengruppen | Alle | Bedingung auf bestimmte Kundensegmente anwenden. |
|  | Min./Max. Menge | Benutzerdefiniert | Mengenbereich für ausgewählte Artikel/Kategorien festlegen. |
|  | Min./Max. Wert | Benutzerdefiniert | Wertebereich für ausgewählte Artikel/Kategorien festlegen. |
|  | Nachricht | Benutzerdefiniert | Kundenorientierte Nachricht, wenn die Bedingung nicht erfüllt ist. |
|  | Aktiv | Ja | Bedingung aktivieren/deaktivieren. |
| **Länderbedingungen verwalten** | Land | Benutzerdefiniert | Bestimmte Länder für Bedingungen ansprechen. |
|  | Min./Max. Menge | Benutzerdefiniert | Mengenbereich für Warenkörbe aus dem ausgewählten Land. |
|  | Min./Max. Wert | Benutzerdefiniert | Wertebereich für Warenkörbe aus dem ausgewählten Land. |
|  | Nachricht | Benutzerdefiniert | Kundennachricht bei länderspezifischem Fehler. |
|  | Aktiv | Ja | Länderbedingung aktivieren/deaktivieren. |
| **Mengenbedingungen verwalten** | Bedingungsname | Benutzerdefiniert | Interne Bezeichnung für die Mengenbedingung. |
|  | Min./Max. Gesamtmenge | Benutzerdefiniert | Mengenbereich für den gesamten Warenkorb. |
|  | Min./Max. Menge spezifischer Produkte/Kategorien | Benutzerdefiniert | Mengenbereich für ausgewählte Artikel/Kategorien. |
|  | Kundengruppen | Alle | Auf bestimmte Kundensegmente anwenden. |
|  | Nachricht | Benutzerdefiniert | Kundennachricht bei Mengenfehler. |
|  | Aktiv | Ja | Mengenbedingung aktivieren/deaktivieren. |
| **Wertbedingungen verwalten** | Bedingungsname | Benutzerdefiniert | Interne Bezeichnung für die Wertbedingung. |
|  | Min./Max. Gesamtwert des Warenkorbs | Benutzerdefiniert | Wertebereich für den gesamten Warenkorb. |
|  | Kundengruppen | Alle | Auf bestimmte Kundensegmente anwenden. |
|  | Nachricht | Benutzerdefiniert | Kundennachricht bei Wertfehler. |
|  | Aktiv | Ja | Wertbedingung aktivieren/deaktivieren. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Bedingungen sind eingestellt, aber sie scheinen im Front Office nicht zu funktionieren. Was ist falsch?**
**A1:**

- **Bedingungsstatus prüfen:** Stellen Sie sicher, dass der Schalter „Aktiv“ für jede von Ihnen festgelegte Bedingung auf „Ja“ steht.
- **Cache leeren:** PrestaShop speichert Inhalte oft im Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
- **Modulposition:** Überprüfen Sie, ob das Modul korrekt eingehängt ist. Die Hooks `displayShoppingCart` und `displayPaymentTop` sind entscheidend. Wenn Ihr Theme benutzerdefinierte Hooks hat, benötigen Sie möglicherweise Entwicklerhilfe.
- **Kundengruppen:** Überprüfen Sie nochmals, ob die Bedingungen auf die richtigen Kundengruppen angewendet werden und ob Ihr Testkunde zu dieser Gruppe gehört.
- **Produkt-/Kategorie-IDs:** Stellen Sie beim Auswählen von Produkten oder Kategorien sicher, dass Sie die richtigen ausgewählt haben. Manchmal können ähnliche Namen zu Verwechslungen führen.

**F2: Die dem Kunden angezeigte Nachricht ist nicht klar oder sieht mit meinem Theme nicht gut aus.**
**A2:**

- **Nachricht bearbeiten:** Gehen Sie zur spezifischen Bedingung (z. B. Wertbedingungen verwalten, dann die Bedingung bearbeiten) und aktualisieren Sie das Feld „Nachricht“ mit einem klareren, hilfreichereren Text.
- **Theme-Styling:** Das visuelle Erscheinungsbild (Schriftart, Farbe, Größe) der Nachricht wird durch das CSS Ihres PrestaShop-Themes gesteuert. Wenn Sie das Styling ändern müssen, müssen Sie einen Webdesigner oder Entwickler konsultieren, um benutzerdefinierte CSS-Regeln zu Ihrem Theme hinzuzufügen. Die CSS-Dateien des Moduls (`cartcon.css`) bieten das Basis-Styling.

**F3: Kann ich unterschiedliche Bedingungen für verschiedene Sprachen/Länder festlegen?**
**A3:**

- **Länderspezifische Bedingungen:** Ja, verwenden Sie den Bildschirm „Länderbedingungen verwalten“, um Regeln festzulegen, die nur für Kunden aus bestimmten Ländern gelten.
- **Mehrsprachige Nachrichten:** Beim Bearbeiten einer Bedingung hat das Feld „Nachricht“ normalerweise einen Sprachwähler (ein Flaggensymbol). Klicken Sie darauf, um Übersetzungen für Ihre Nachricht in allen aktiven Sprachen Ihres Shops bereitzustellen.

**F4: Ich möchte ein bestimmtes Produkt von ALLEN Bedingungen ausschließen. Wie mache ich das?**
**A4:**

- Auf der Hauptmodulkonfigurationsseite (Back Office > Module > Konfigurieren > Warenkorb-Bedingungen Pro) verwenden Sie die Einstellung „Produkte von Bedingungen ausschließen“. Sie können die spezifischen Produkte suchen und auswählen, die Sie ausnehmen möchten.

**F5: Das Modul blockiert den Checkout, aber ich kann nicht herausfinden, welche Bedingung dies verursacht.**
**A5:**

- **Alle Bedingungen überprüfen:** Gehen Sie die Bildschirme „Bedingungen verwalten“, „Länderbedingungen verwalten“, „Mengenbedingungen verwalten“ und „Wertbedingungen verwalten“ einzeln durch. Überprüfen Sie den Status „Aktiv“ jeder Bedingung und deren Kriterien.
- **Systematisch testen:** Wenn Sie viele Bedingungen haben, versuchen Sie, diese einzeln (oder in Gruppen) zu deaktivieren und den Warenkorb zu testen, bis Sie den Übeltäter identifiziert haben. Aktivieren Sie sie dann wieder und passen Sie die problematische Bedingung an.
- **Kundengruppe überprüfen:** Stellen Sie sicher, dass Ihr Testkunde nicht Teil einer ausgeschlossenen Kundengruppe ist.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Warenkorb-Bedingungen Pro“ folgt dem Standard-PrestaShop-MVC-Muster (Model-View-Controller), wobei es hauptsächlich `Module` für seine Hauptkonfiguration und `AdminController` für dedizierte Verwaltungsoberflächen erweitert. Es nutzt das PrestaShop-Hook-System, um Logik einzufügen und Nachrichten an kritischen Stellen im Front-Office (Warenkorb, Zahlung) anzuzeigen, und verwendet implizit `ObjectModel` zur Verwaltung seiner verschiedenen Bedingungsentitäten. Das Modul stützt sich auf benutzerdefinierte Datenbanktabellen, um seine komplexen Bedingungsregeln zu speichern.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Das bereitgestellte Inventar scheint keine dedizierten Front-Controller zu enthalten. Die Front-Office-Logik und -Anzeige werden wahrscheinlich direkt über die Hauptmoduldatei `cartcon.php` mittels Hook-Callbacks gehandhabt.

#### Back-Office-Admin-Controller

Alle Admin-Controller erweitern `ModuleAdminController` (oder `AdminController` in älteren PrestaShop-Versionen) und sind für die Verwaltung der verschiedenen Bedingungstypen verantwortlich.

- `cartcon/controllers/admin/AdminCartAssociationsConditionController.php`

  - **Klassenname:** `AdminCartAssociationsConditionController`
  - **Elternklasse:** `ModuleAdminController`
  - **Verantwortlichkeit:** Verwaltet die Zuordnungen (Produkte, Kategorien), die mit einer spezifischen allgemeinen Warenkorb-Bedingung verknüpft sind. Dieser Controller bietet die Schnittstelle zum Suchen und Auswählen von Produkten/Kategorien, die Teil der Kriterien einer Bedingung sind. Er interagiert mit der Tabelle `cartcon_ass`.
- `cartcon/controllers/admin/AdminCartConditionController.php`

  - **Klassenname:** `AdminCartConditionController`
  - **Elternklasse:** `ModuleAdminController`
  - **Verantwortlichkeit:** Verwaltet die Haupt-, allgemeinen Warenkorb-Bedingungen. Dies ist die primäre Schnittstelle zum Erstellen, Bearbeiten und Löschen von Bedingungen basierend auf Produkt-/Kategoriepräsenz, Menge oder Wert. Er interagiert mit der Tabelle `cartcon`.
- `cartcon/controllers/admin/AdminCartCountryConditionController.php`

  - **Klassenname:** `AdminCartCountryConditionController`
  - **Elternklasse:** `ModuleAdminController`
  - **Verantwortlichkeit:** Verwaltet Warenkorb-Bedingungen, die speziell an Kundenländer gebunden sind. Er ermöglicht die Definition von Regeln, die nur gelten, wenn das Versandland des Kunden mit einem angegebenen Land übereinstimmt. Er interagiert mit der Tabelle `cartcon_country`.
- `cartcon/controllers/admin/AdminCartQuantityConditionController.php`

  - **Klassenname:** `AdminCartQuantityConditionController`
  - **Elternklasse:** `ModuleAdminController`
  - **Verantwortlichkeit:** Verwaltet Bedingungen basierend auf der Gesamtmenge der Artikel im Warenkorb oder der Menge spezifischer Produkte/Kategorien. Er interagiert mit der Tabelle `cartcon_quantity`.
- `cartcon/controllers/admin/AdminCartValueConditionController.php`

  - **Klassenname:** `AdminCartValueConditionController`
  - **Elternklasse:** `ModuleAdminController`
  - **Verantwortlichkeit:** Verwaltet Bedingungen basierend auf dem gesamten Geldwert des Warenkorbs. Er interagiert mit der Tabelle `cartcon_value`.
- `cartcon/controllers/admin/index.php`

  - **Verantwortlichkeit:** Standard-PrestaShop-Sicherheitsdatei zur Verhinderung der Verzeichnisauflistung. Sie leitet zum übergeordneten Verzeichnis um.

### 4.3 Kernklassen & Modelle (`classes/`)

Das bereitgestellte Inventar listet keine expliziten Dateien in einem `classes/`-Verzeichnis auf. Dies deutet darauf hin, dass die Kernlogik des Moduls und die `ObjectModel`-Definitionen (falls vorhanden) entweder in der Hauptdatei `cartcon.php` oder in den Admin-Controller-Dateien selbst eingebettet sind, was ein gängiges Muster für einfachere Module oder ältere PrestaShop-Versionen ist. Wenn `ObjectModel`s verwendet werden, würden ihre `$definition`-Arrays innerhalb der jeweiligen Controller- oder Hauptmodulklasse gefunden werden.

### 4.4 JavaScript-Assets (`views/js/`)

- `cartcon/lib/searchTool/views/js/autocomplete.js`

  - **Geltungsbereich:** Back-Office.
  - **Verantwortlichkeit:** Bietet Autocomplete-Funktionalität für die Suche nach Produkten, Kategorien oder Kunden in den Admin-Formularen (z. B. beim Einrichten von Ausschlüssen oder Bedingungszuordnungen). Es bindet wahrscheinlich an Eingabefelder, sendet AJAX-Anfragen an einen Such-Endpunkt und zeigt Vorschläge an.
- `cartcon/views/js/cartcon.js`

  - **Geltungsbereich:** Front-Office und potenziell Back-Office.
  - **Verantwortlichkeit:**
    - **Front-Office:** Verwaltet die dynamische Anzeige von Warenkorb-Bedingungsnachrichten, das Deaktivieren/Aktivieren der Schaltfläche „Zur Kasse gehen“ basierend auf AJAX-Antworten vom Server bezüglich der Warenkorb-Gültigkeit. Es könnte auf Warenkorb-Updates (`prestashop.on('updateCart', ...)` oder ähnliche Ereignisse) hören, um Bedingungen neu zu bewerten.
    - **Back-Office:** Könnte Logik für Formularvalidierung, dynamische Feldsichtbarkeit oder andere UI-Verbesserungen enthalten, die spezifisch für die Konfigurationsseiten des Moduls sind.

### 4.5 CSS-Stylesheets (`views/css/`)

- `cartcon/lib/searchTool/views/css/autocomplete.css`

  - **Geltungsbereich:** Back-Office.
  - **Verantwortlichkeit:** Gestaltet die Autocomplete-Vorschlags-Dropdowns und Such-Eingabefelder, die in den Admin-Formularen verwendet werden, um ein konsistentes und benutzerfreundliches Sucherlebnis zu gewährleisten.
- `cartcon/views/css/cartcon.css`

  - **Geltungsbereich:** Front-Office und Back-Office.
  - **Verantwortlichkeit:**
    - **Front-Office:** Gestaltet die Benachrichtigungsmeldungen, die auf der Warenkorbseite, Zahlungsseite oder Produktseite angezeigt werden, wenn Bedingungen nicht erfüllt sind. Es definiert das Aussehen der Warnfelder, des Textes und möglicherweise den deaktivierten Zustand der Checkout-Schaltfläche.
    - **Back-Office:** Bietet Styling für die Konfigurationsformulare und Listen-Tabellen des Moduls, um sicherzustellen, dass sie gut in das PrestaShop-Back-Office-Theme integriert sind.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Suchen Sie in dieser Datei nach Klassen wie `.cartcon-alert`, `.cartcon-message`, `.cartcon-disabled-button` oder ähnlichen, um die Front-Office-Ausgabe des Moduls anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

Die Front-Office-Anzeigelogik des Moduls ist wahrscheinlich direkt in den Hook-Methoden der Hauptdatei `cartcon.php` eingebettet, die dann diese Templates rendern.

- `cartcon/views/templates/front/displayShoppingCart.tpl`

  - **Gerendert im Hook:** `displayShoppingCart`
  - **Zweck:** Zeigt die Warenkorb-Bedingungsnachrichten an und deaktiviert möglicherweise die Checkout-Schaltfläche auf der Haupt-Warenkorbseite, wenn die Bedingungen nicht erfüllt sind. Es empfängt Variablen von der `hookDisplayShoppingCart`-Methode des Moduls, die die Gültigkeit des Warenkorbs und die anzuzeigende Nachricht angeben.
- `cartcon/views/templates/front/displayShoppingCartEmpty.tpl`

  - **Gerendert im Hook:** Potenziell `displayShoppingCart` oder ein verwandter Hook, wenn der Warenkorb leer ist.
  - **Zweck:** Bietet ein spezifisches Template zum Anzeigen von Nachrichten oder alternativen Inhalten, wenn der Warenkorb leer ist, möglicherweise im Zusammenhang mit Mindestbestellanforderungen.
- `cartcon/views/templates/front/productActions.tpl`

  - **Gerendert im Hook:** `displayProductActions` (typischerweise in der Nähe der Schaltfläche „In den Warenkorb“ auf der Produktseite).
  - **Zweck:** Kann verwendet werden, um subtile Hinweise oder Warnungen direkt auf der Produktseite anzuzeigen, wenn das Hinzufügen des Produkts eine Warenkorb-Bedingung verletzen würde oder wenn das Produkt den Kauf anderer Artikel erfordert.

#### Admin-Templates (`views/templates/admin/`)

- `cartcon/lib/searchTool/views/scripts.tpl`

  - **Zweck:** Enthält wahrscheinlich JavaScript-Abhängigkeiten oder initialisiert die Autocomplete-Skripte für die Admin-Formulare.
- `cartcon/views/templates/admin/AdminCartAssociationsCondition.tpl`

  - **Zweck:** Das Haupttemplate für den `AdminCartAssociationsConditionController`, das die Oberfläche zur Verwaltung von Produkt-/Kategoriezuordnungen für eine Bedingung anzeigt. Dies würde Suchfelder, Listen ausgewählter Artikel und Speicher-Schaltflächen umfassen.
- `cartcon/views/templates/admin/adminSearchCustomer.tpl`

  - **Zweck:** Template für die Kundensuchoberfläche, die beim Ausschließen von Kunden von Bedingungen verwendet wird.
- `cartcon/views/templates/admin/script.tpl`

  - **Zweck:** Allgemeines Admin-Skript-Template, das möglicherweise modulspezifisches JavaScript oder Konfigurationsvariablen für das Back Office enthält.
- `cartcon/views/templates/admin/search-attribute-value-result.tpl`

  - **Zweck:** Template zum Anzeigen der Ergebnisse einer Attribut-/Wertsuche innerhalb des Admin-Panels, wahrscheinlich in Verbindung mit Produktsuchen verwendet.
- `cartcon/views/templates/admin/search-attribute-value.tpl`

  - **Zweck:** Template für das Such-Eingabefeld und zugehörige UI-Elemente zum Suchen von Produktattributen/-werten im Admin.
- `cartcon/views/templates/admin/selectedProducts.tpl`

  - **Zweck:** Template zum Anzeigen der Liste der Produkte, die in den Admin-Formularen ausgewählt und einer bestimmten Bedingung zugeordnet wurden.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt benutzerdefinierte Tabellen, um seine verschiedenen Bedingungen und Zuordnungen zu speichern. Diese Tabellen sind typischerweise mit `ps_cartcon_` oder `cartcon_` präfixiert.

- `ps_cartcon`: Speichert allgemeine Warenkorb-Bedingungen (Name, Nachricht, aktiver Status usw.).
- `ps_cartcon_ass`: Speichert Zuordnungen zwischen Bedingungen und spezifischen Produkten/Kategorien.
- `ps_cartcon_country`: Speichert länderspezifische Bedingungen.
- `ps_cartcon_quantity`: Speichert mengenbasierte Bedingungen.
- `ps_cartcon_value`: Speichert wertbasierte Bedingungen.
- `ps_configuration`: Moduleinstellungen wie `CARTCON_CUSTOMERS`, `ccon_visibility_rule`, `CARTCON_FUTURE` usw. werden hier gespeichert.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird zum Laden der CSS- und JavaScript-Assets des Moduls für Front-Office und Back-Office verwendet. |
| `displayPaymentTop` | Oben auf der Zahlungsauswahlseite während des Checkouts. | Entscheidend für die Neubewertung der Warenkorb-Bedingungen kurz vor der Zahlung und gegebenenfalls deren Blockierung. |
| `displayShoppingCart` | Auf der Haupt-Warenkorbseite. | Primärer Hook zum Anzeigen von Bedingungsnachrichten und zum Deaktivieren der Checkout-Schaltfläche. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird und seine Medien (JS/CSS) gesetzt werden. | Wird zum Laden spezifischer JS/CSS-Assets für die Back-Office-Konfigurationsseiten des Moduls verwendet. |
| `displayProductActions` | Typischerweise in der Nähe der Schaltfläche „In den Warenkorb“ auf der Produktseite. | Kann verwendet werden, um produktspezifische Bedingungshinweise oder Warnungen anzuzeigen. |
| `actionCartSave` | Nachdem ein Warenkorb gespeichert wurde (z. B. Produkt hinzugefügt/entfernt, Menge geändert). | (Implizit/Wahrscheinlich) Das Modul würde wahrscheinlich einen `actionCartSave` oder ähnlichen Hook verwenden, um die Neubewertung der Warenkorb-Bedingungen auf Serverseite auszulösen, die dann das Front-Office-JS informiert. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Warenkorb-Bedingungen Pro“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, sicherzustellen, dass das Modul optimal mit Ihrem PrestaShop-Shop funktioniert.

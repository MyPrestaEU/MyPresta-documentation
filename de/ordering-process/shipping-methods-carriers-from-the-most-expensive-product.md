---
title: "Versandmethoden (Versanddienstleister) basierend auf dem teuersten Produkt – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Versandmethoden (Versanddienstleister) basierend auf dem teuersten Produkt“ von MyPresta.eu."
sidebar:
  label: "Versandmethoden (Versanddienstleister) basierend auf dem teuersten Produkt – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Shipping methods (carriers) from the most expensive product auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/shipping-methods-carriers-from-the-most-expensive-product.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/shipping-methods-carriers-from-the-most-expensive-product/)
>
> ---


# Versandmethoden (Versanddienstleister) basierend auf dem teuersten Produkt

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation neben dem Modulnamen auf „Konfigurieren“, um auf die Einstellungen zuzugreifen.

#### **Modul aktivieren / deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul ändert die Standardlogik der Versanddienstleisterauswahl von PrestaShop und stellt sicher, dass während des Checkouts nur die Versanddienstleister angezeigt werden, die mit dem teuersten Produkt im Warenkorb verknüpft sind.
  - *Wenn deaktiviert:* PrestaShop kehrt zu seinem Standardverhalten zurück, bei dem Versanddienstleister nur angezeigt werden, wenn sie *alle* Produkte im Warenkorb versenden können.
- **Empfohlener Wert:** „Aktiviert“, wenn Sie die Funktionalität des Moduls nutzen möchten.
- **Händlerszenario / Beispiel:** Wenn Sie das Modul testen oder vorübergehend zum Standardverhalten von PrestaShop zurückkehren möchten, ohne es zu deinstallieren, können Sie es hier deaktivieren.

#### **Wie werden Versanddienstleister ermittelt?**

- **Was diese Einstellung bewirkt:** Diese entscheidende Einstellung definiert, *wie* das Modul das „teuerste Produkt“ identifiziert und anschließend die verfügbaren Versanddienstleister bestimmt. Es bietet zwei verschiedene Methoden.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf „Vom teuersten Produkt (nach Preis)“ eingestellt:* Das Modul berechnet den Gesamtpreis jedes einzelnen Produkts im Warenkorb (Menge * Einzelpreis) und identifiziert das Produkt mit dem höchsten Gesamtpreis. Die Versanddienstleister, die mit *diesem spezifischen Produkt* verknüpft sind, werden dann verwendet, um die verfügbaren Versandoptionen zu filtern.
  - *Wenn auf „Vom teuersten Produkt (nach Preis) - KOSTENLOSER VERSAND“ eingestellt:* Diese Option funktioniert ähnlich wie die erste, berücksichtigt aber auch, ob das teuerste Produkt für kostenlosen Versand qualifiziert ist. Wenn für das teuerste Produkt kostenloser Versand aktiviert ist, werden kostenlose Versandoptionen gemäß Ihren Versanddienstleistereinstellungen priorisiert oder verfügbar gemacht.
  - *Wenn auf „Vom teuersten Produkt (nach Preis) - KOSTEN“ eingestellt:* Diese Option identifiziert ebenfalls das teuerste Produkt nach Preis, konzentriert sich aber speziell auf die *Kosten*, die mit dem Versand dieses Produkts verbunden sind. Sie stellt sicher, dass die angezeigten Versandkosten und -optionen direkt an die Versandkonfiguration des teuersten Artikels gebunden sind.
- **Empfohlener Wert:**
  - „Vom teuersten Produkt (nach Preis)“ ist die gebräuchlichste und empfohlene Wahl für den allgemeinen Gebrauch, da es das Kernversprechen des Moduls direkt umsetzt.
  - Wählen Sie „Vom teuersten Produkt (nach Preis) - KOSTENLOSER VERSAND“, wenn Sie häufig kostenlosen Versand für hochwertige Artikel anbieten und dies eine primäre Überlegung bei der Versanddienstleisterauswahl sein soll.
  - Wählen Sie „Vom teuersten Produkt (nach Preis) - KOSTEN“, wenn Sie komplexe Versandkostenregeln haben, die an bestimmte hochwertige Produkte gebunden sind, und möchten, dass diese Regeln die verfügbaren Versanddienstleister bestimmen.
- **Händlerszenario / Beispiel:**
  - Sie verkaufen einen 1000-Dollar-Fernseher und eine 10-Dollar-Fernbedienung. Wenn der Fernseher mit bestimmten Versanddienstleistern (z.B. versicherter Fracht) und die Fernbedienung mit einem Standard-Postdienst konfiguriert ist, stellt die Auswahl von „Vom teuersten Produkt (nach Preis)“ sicher, dass die Versanddienstleister des Fernsehers angezeigt werden.
  - Wenn Ihr 1000-Dollar-Fernseher mit kostenlosem Versand geliefert wird, würde die Auswahl von „Vom teuersten Produkt (nach Preis) - KOSTENLOSER VERSAND“ sicherstellen, dass kostenlose Versandoptionen angezeigt werden, sofern für den Fernseher verfügbar.

#### **Konfigurations-Kurzübersichtstabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Modul aktivieren / deaktivieren | Aktiviert | Aktiviert/deaktiviert die Logik des Moduls zur Versanddienstleisterauswahl basierend auf dem teuersten Produkt. |
| Modulkonfigurationsseite | Wie werden Versanddienstleister ermittelt? | Vom teuersten Produkt (nach Preis) | Definiert die Methode zur Identifizierung des „teuersten Produkts“ und seiner zugehörigen Versanddienstleister. Optionen: „nach Preis“, „nach Preis - KOSTENLOSER VERSAND“, „nach Preis - KOSTEN“. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul aktiviert, aber ich sehe immer noch die alten Versandoptionen oder gar keine Versanddienstleister.**
A:

1. **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Änderungen an der Modulkonfiguration vorgenommen haben. Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie oben rechts auf „Cache leeren“.
2. **Produkt-Versanddienstleister-Zuordnungen prüfen:** Stellen Sie sicher, dass Ihre Produkte, insbesondere Ihre teuersten, in ihren Produkteinstellungen (**Katalog > Produkte > Produkt bearbeiten > Versand-Tab**) korrekt den gewünschten Versanddienstleistern zugeordnet sind.
3. **Modul ist aktiviert:** Überprüfen Sie nochmals, ob die Einstellung „Modul aktivieren / deaktivieren“ in der Modulkonfiguration auf „Aktiviert“ steht.
4. **Theme-Kompatibilität:** Obwohl dies bei dieser Art von Modul selten ist, könnte ein stark angepasstes Theme stören. Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um dies auszuschließen.

**F: Wie geht das Modul mit zwei Produkten um, die genau den gleichen höchsten Preis haben?**
A: In Fällen, in denen zwei oder mehr Produkte genau den gleichen höchsten Preis haben, wählt das Modul typischerweise eines davon basierend auf der internen PrestaShop-Produkt-ID-Reihenfolge oder der Reihenfolge, in der sie dem Warenkorb hinzugefügt wurden. Es verwendet dann die Versanddienstleister, die mit diesem ausgewählten Produkt verknüpft sind. Für Konsistenz ist es am besten, sicherzustellen, dass Ihre Versanddienstleisterkonfigurationen robust genug sind, um ähnliche hochwertige Artikel abzudecken.

**F: Beeinflusst dieses Modul die Versandkosten oder nur die Verfügbarkeit der Versanddienstleister?**
A: Dieses Modul beeinflusst primär die *Verfügbarkeit der Versanddienstleister*. Es bestimmt, *welche* Versanddienstleister angezeigt werden. Die tatsächlichen Versandkosten für den gewählten Dienstleister werden weiterhin von PrestaShops Standardmechanismen (basierend auf Gewicht, Preis, Zone usw.) für den *gesamten Warenkorb* berechnet, jedoch nur für die Versanddienstleister, die durch die Logik dieses Moduls verfügbar gemacht werden.

**F: Was passiert, wenn das teuerste Produkt keine Versanddienstleister zugeordnet hat?**
A: Wenn das teuerste Produkt im Warenkorb in seinen Produkteinstellungen keine explizit zugeordneten Versanddienstleister hat, werden während des Checkouts keine Versanddienstleister angezeigt, was möglicherweise zu einer Meldung „Keine Versandmethode verfügbar“ führt. Stellen Sie immer sicher, dass Ihren hochwertigen Produkten entsprechende Versanddienstleister zugewiesen sind.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Versandmethoden (Versanddienstleister) basierend auf dem teuersten Produkt“ erreicht seine Funktionalität durch das Überschreiben einer PrestaShop-Kernklasse, `Cart`. Dies ist eine gängige und leistungsstarke Methode in PrestaShop, um grundlegende Verhaltensweisen zu ändern, ohne Kerndateien direkt zu modifizieren. Durch das Überschreiben von `Cart::getAvailableCarriers()` injiziert das Modul seine benutzerdefinierte Logik, um Versanddienstleister basierend auf dem teuersten Produkt zu filtern, anstatt der Standardregel „alle Produkte müssen kompatibel sein“.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Das Modul arbeitet durch das Überschreiben einer Kernklasse, nicht durch die Einführung neuer Front-Office-Routen oder Seiten.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration des Moduls wird direkt in der `getContent()`-Methode der Hauptmodulklasse gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Die Kernlogik des Moduls befindet sich in einem Override der `Cart`-Klasse.

- **`cfep/override/classes/Cart.php`**

  - **Klassenname**: `Cart` (überschreibt `PrestaShop\Classes\Cart\Cart` oder `CartCore` je nach PrestaShop-Version und Kontext).
  - **Elternklasse**: `CartCore`
  - **Verantwortlichkeit**: Diese Datei enthält die überschriebene Methode `getAvailableCarriers()`. Diese Methode ist entscheidend für die Bestimmung, welche Versanddienstleister dem Kunden während des Checkouts präsentiert werden. Der Override führt die Logik ein, um:
    1. Das teuerste Produkt im aktuellen Warenkorb basierend auf der Modulkonfiguration (`CFEP`, `CFEP_FREE`, `CFEP_COST`) zu identifizieren.
    2. Die Versanddienstleister abzurufen, die speziell mit diesem teuersten Produkt verknüpft sind.
    3. Die Liste aller verfügbaren Versanddienstleister so zu filtern, dass nur diejenigen enthalten sind, die mit dem teuersten Produkt kompatibel sind.
    4. Diese gefilterte Liste von Versanddienstleistern zurückzugeben.
  - **Wichtige öffentliche Methoden**:
    - `getAvailableCarriers(bool $return_full_list = false, int $id_zone = null, bool $use_cache = true)`: Dies ist die überschriebene Methode. Sie erweitert die ursprüngliche `CartCore::getAvailableCarriers`, um die benutzerdefinierte Logik zur Filterung von Versanddienstleistern zu implementieren. Sie ruft zuerst die Elternmethode auf, um alle potenziell verfügbaren Versanddienstleister zu erhalten, und wendet dann ihre eigene Filterung basierend auf dem teuersten Produkt an.
- **`cfep/override/classes/index.php`**

  - **Verantwortlichkeit**: Dies ist eine standardmäßige leere `index.php`-Datei, die typischerweise in Verzeichnissen platziert wird, um das Auflisten von Verzeichnissen zu verhindern, wenn direkt über einen Webbrowser darauf zugegriffen wird. Sie hat keine funktionale Auswirkung auf die Logik des Moduls.

### 4.4 JavaScript-Assets (`views/js/`)

- Keine. Das Modul fügt dem Front- oder Back-Office kein benutzerdefiniertes JavaScript hinzu.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Das Modul fügt dem Front- oder Back-Office kein benutzerdefiniertes CSS hinzu.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- Keine. Das Modul verwendet keine benutzerdefinierten Smarty-Templates. Seine Konfigurationsoberfläche wird dynamisch von `getContent()` in der Hauptmoduldatei generiert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen in der Standardtabelle `ps_configuration`.

  - `ps_configuration`-Einträge:
    - `CFEP`: Speichert die ausgewählte Methode zum Abrufen von Versanddienstleistern (z.B. 'price', 'free', 'cost').
    - `mypresta_updates`: Wird für interne MyPresta.eu-Update-Prüfungen verwendet.
    - `update_`: Wird für interne MyPresta.eu-Update-Prüfungen verwendet.
    - `updatev_`: Wird für interne MyPresta.eu-Update-Prüfungen verwendet.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert keine Hooks explizit in der Tabelle `ps_hook_module`. Seine Funktionalität wird durch einen Klassen-Override implementiert, was eine direktere Methode ist, um das PrestaShop-Kernverhalten zu ändern, ohne sich auf spezifische Hook-Ausführungspunkte zu verlassen.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Versandmethoden (Versanddienstleister) basierend auf dem teuersten Produkt“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.

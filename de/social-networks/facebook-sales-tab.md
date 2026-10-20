---
title: "Facebook Sales Tab – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Facebook Sales Tab von MyPresta.eu."
sidebar:
  label: "Facebook Sales Tab – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook Sales Tab auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-sales-tab.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-sales-tab/)
>
> ---


# Facebook Sales Tab

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).
- **Externe Anforderungen**: Eine aktive Facebook-Fanpage (Business Page), bei der Sie Administrator sind. Sie müssen außerdem eine Facebook-Anwendung erstellen, um Ihren Shop mit Ihrer Fanpage zu verknüpfen, was die Beschaffung einer App ID und eines App Secret vom Facebook Developer Portal beinhaltet.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > Facebook Sales Tab)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul Facebook Sales Tab. Hier verknüpfen Sie Ihren PrestaShop-Store mit Ihrer Facebook-Fanpage und definieren, welche Inhalte angezeigt werden.

Um auf diese Seite zuzugreifen, gehen Sie zu **Back Office > Module > Modul-Manager**, suchen Sie nach „Facebook Sales Tab“ und klicken Sie auf „Konfigurieren“.

#### **Facebook-Anwendungseinstellungen**

Diese Einstellungen sind entscheidend für die Herstellung der Verbindung zwischen Ihrem PrestaShop-Store und Ihrer Facebook-Fanpage. Sie müssen eine Facebook-Anwendung über das Facebook Developer Portal erstellen, um diese Anmeldeinformationen zu erhalten.

- **Facebook App ID:**

  - **Was diese Einstellung bewirkt:** Dies ist eine eindeutige Kennung für Ihre Facebook-Anwendung. Sie teilt Facebook mit, welche Anwendung versucht, sich mit Ihrer Fanpage zu verbinden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Bei korrekter Eingabe:* Ermöglicht Ihrem Modul die Kommunikation mit Facebook und die Anzeige des Verkaufs-Tabs.
    - *Bei falscher oder leerer Eingabe:* Das Modul kann keine Verbindung zu Facebook herstellen, und der Verkaufs-Tab funktioniert nicht oder erscheint nicht auf Ihrer Fanpage.
  - **Empfohlener Wert:** Die genaue App ID, die Facebook Ihnen bei der Erstellung Ihrer Anwendung zur Verfügung stellt.
  - **Händlerszenario / Beispiel:** Sie haben eine Facebook-App namens „MyStore Sales Tab“ auf developers.facebook.com erstellt, und Facebook hat ihr eine App ID wie `123456789012345` zugewiesen. Sie würden diese Nummer hier eingeben.
- **Facebook App Secret:**

  - **Was diese Einstellung bewirkt:** Dies ist ein geheimer Schlüssel, der mit Ihrer Facebook-Anwendung verknüpft ist und zur Authentifizierung der Anfragen Ihrer Anwendung an Facebook verwendet wird. Er sollte vertraulich behandelt werden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Bei korrekter Eingabe:* Gewährleistet eine sichere Kommunikation zwischen Ihrem Shop und Facebook.
    - *Bei falscher oder leerer Eingabe:* Facebook lehnt die Verbindungsversuche ab, und der Verkaufs-Tab funktioniert nicht.
  - **Empfohlener Wert:** Das genaue App Secret, das Facebook Ihnen bei der Erstellung Ihrer Anwendung zur Verfügung stellt.
  - **Händlerszenario / Beispiel:** Zusammen mit Ihrer App ID stellt Facebook ein App Secret zur Verfügung (z. B. `abcdef1234567890abcdef1234567890`). Sie geben diese Zeichenfolge hier ein.
- **Facebook Page ID:**

  - **Was diese Einstellung bewirkt:** Dies ist die eindeutige Kennung für Ihre spezifische Facebook-Fanpage, auf der der Verkaufs-Tab erscheinen soll.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Bei korrekter Eingabe:* Das Modul weiß, welche Fanpage für das Hinzufügen des Verkaufs-Tabs angesprochen werden soll.
    - *Bei falscher oder leerer Eingabe:* Der Verkaufs-Tab wird nicht zu Ihrer gewünschten Fanpage hinzugefügt, oder er könnte zu einer falschen hinzugefügt werden, wenn eine falsche ID eingegeben wird.
  - **Empfohlener Wert:** Die genaue Page ID Ihrer Facebook-Fanpage. Diese finden Sie normalerweise im Abschnitt „Info“ Ihrer Fanpage oder mithilfe eines Facebook Page ID Finder-Tools.
  - **Händlerszenario / Beispiel:** Die Facebook-Fanpage Ihres Shops ist „Mein toller Shop“. Sie finden ihre Page ID (z. B. `987654321098765`) und geben sie hier ein.

#### **Einstellungen für den Inhalt des Verkaufs-Tabs**

Diese Einstellungen steuern, welche Produkte oder Aktionen auf Ihrem Facebook Sales Tab angezeigt werden.

- **Anzahl der anzuzeigenden Produkte:**

  - **Was diese Einstellung bewirkt:** Bestimmt, wie viele Produkte aus Ihrer speziellen Verkaufsaktion auf dem Facebook-Tab angezeigt werden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Bei Einstellung auf eine höhere Zahl (z. B. 20):* Mehr Produkte werden sichtbar, was den Kunden eine größere Auswahl bietet.
    - *Bei Einstellung auf eine niedrigere Zahl (z. B. 5):* Weniger Produkte werden angezeigt, wodurch die Aufmerksamkeit möglicherweise auf Ihre Top-Angebote gelenkt wird.
  - **Empfohlener Wert:** 10-20, je nachdem, wie viele aktive Verkäufe Sie normalerweise haben und wie viel Inhalt Sie präsentieren möchten.
  - **Händlerszenario / Beispiel:** Sie haben 15 Produkte im Angebot. Wenn Sie dies auf „15“ setzen, werden alle auf Ihrem Facebook-Tab angezeigt. Wenn Sie nur die Top 5 hervorheben möchten, würden Sie es auf „5“ setzen.
- **Produkte aus bestimmten Kategorien anzeigen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die auf dem Facebook-Tab angezeigten Produkte so zu filtern, dass nur solche aus ausgewählten Kategorien in Ihrem PrestaShop-Store enthalten sind.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn bestimmte Kategorien ausgewählt sind:* Nur Produkte, die zu diesen Kategorien gehören, erscheinen auf dem Facebook-Tab, auch wenn andere Produkte im Angebot sind.
    - *Wenn keine Kategorien ausgewählt sind (oder alle ausgewählt sind):* Alle Produkte, die die „Verkaufs“-Kriterien erfüllen, werden angezeigt.
  - **Empfohlener Wert:** Wählen Sie Kategorien aus, die für Ihre aktuellen Aktionen oder Bestseller relevant sind, die Sie auf Facebook hervorheben möchten.
  - **Händlerszenario / Beispiel:** Sie führen eine Sonderaktion für „Sommerkleider“ und „Strandaccessoires“ durch. Sie würden diese beiden Kategorien auswählen, um sicherzustellen, dass nur diese Produkte auf Ihrem Facebook Sales Tab erscheinen.
- **Produkte mit bestimmten Rabatten/Verkäufen anzeigen:**

  - **Was diese Einstellung bewirkt:** Dies ist der Kernfilter dafür, was ein „Verkaufs“-Produkt ausmacht. Sie können wählen, ob Produkte mit einer bestimmten Preisreduzierung angezeigt werden sollen.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert und konfiguriert:* Nur Produkte mit aktiven Sonderpreisen oder prozentualen Rabatten werden angezeigt.
    - *Wenn deaktiviert:* Das Modul könnte reguläre Produkte oder Produkte basierend auf anderen Kriterien anzeigen (obwohl der Hauptzweck des Moduls „Verkäufe“ ist).
  - **Empfohlener Wert:** JA, und stellen Sie sicher, dass Ihre Produkte aktive Sonderpreise in PrestaShop konfiguriert haben.
  - **Händlerszenario / Beispiel:** Sie haben in Ihren PrestaShop-Produkteinstellungen einen Rabatt von 10 % auf alle „Wintermäntel“ eingerichtet. Diese Einstellung stellt sicher, dass diese reduzierten Mäntel auf Ihrem Facebook-Tab erscheinen.

#### **Allgemeine Anzeigeeinstellungen**

- **Tab-Titel auf Facebook:**

  - **Was diese Einstellung bewirkt:** Dies ist der Text, der als Name des Tabs auf Ihrer Facebook-Fanpage erscheint.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf „Sonderangebote“ gesetzt:* Ihr Tab wird auf Facebook als „Sonderangebote“ bezeichnet.
    - *Wenn auf „Jetzt einkaufen“ gesetzt:* Ihr Tab wird als „Jetzt einkaufen“ bezeichnet.
  - **Empfohlener Wert:** Etwas Klares und Einladendes wie „Sonderangebote“, „Jetzt einkaufen“ oder „Unsere Deals“.
  - **Händlerszenario / Beispiel:** Sie möchten deutlich machen, dass dieser Tab für Aktionen ist, also setzen Sie den Titel auf „Blitzverkäufe!“.
- **Tab-Symbol:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen das Hochladen eines benutzerdefinierten Symbols, das neben Ihrem Tab-Titel auf Facebook erscheint. Dies hilft Ihrem Tab, sich abzuheben.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn ein Symbol hochgeladen wird:* Ihr Tab erhält eine benutzerdefinierte visuelle Kennung.
    - *Wenn kein Symbol hochgeladen wird:* Facebook verwendet ein Standardsymbol, oder der Tab erscheint möglicherweise ohne ein spezifisches Symbol.
  - **Empfohlener Wert:** Ein kleines, klares und relevantes Symbol (z. B. ein Einkaufswagen, ein Stern, ein Prozentzeichen), das zu Ihrer Marke passt.
  - **Händlerszenario / Beispiel:** Sie laden ein kleines Bild eines Einkaufswagens hoch, um Ihren „Jetzt einkaufen“-Tab visuell ansprechend und leicht erkennbar zu machen.

#### **Konfigurations-Kurzübersichtstabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Facebook App ID | Ihre Facebook App ID | Verknüpft Ihren Shop zur Authentifizierung mit Ihrer Facebook App. |
| Modulkonfiguration | Facebook App Secret | Ihr Facebook App Secret | Authentifiziert Ihre App sicher bei Facebook. |
| Modulkonfiguration | Facebook Page ID | Ihre Facebook Fanpage ID | Gibt an, welcher Fanpage der Verkaufs-Tab hinzugefügt wird. |
| Modulkonfiguration | Anzahl der anzuzeigenden Produkte | 10-20 | Steuert, wie viele Verkaufsprodukte auf dem Tab angezeigt werden. |
| Modulkonfiguration | Produkte aus bestimmten Kategorien anzeigen | Relevante Kategorien auswählen | Filtert Produkte nach Kategorie für die Anzeige auf dem Tab. |
| Modulkonfiguration | Produkte mit bestimmten Rabatten/Verkäufen anzeigen | JA | Stellt sicher, dass nur reduzierte Produkte auf dem Tab angezeigt werden. |
| Modulkonfiguration | Tab-Titel auf Facebook | „Sonderangebote“ / „Jetzt einkaufen“ | Legt den sichtbaren Namen des Tabs auf Ihrer Facebook-Fanpage fest. |
| Modulkonfiguration | Tab-Symbol | Ein relevantes Symbol hochladen | Bietet ein benutzerdefiniertes visuelles Symbol für Ihren Facebook-Tab. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein Facebook Sales Tab erscheint nicht auf meiner Fanpage. Was soll ich tun?**
A1:

- **App ID, App Secret und Page ID überprüfen:** Überprüfen Sie nochmals, ob alle drei Werte in der Modulkonfiguration korrekt eingegeben wurden. Schon ein einziger Tippfehler verhindert die Verbindung.
- **Facebook App Status:** Stellen Sie sicher, dass Ihre Facebook-Anwendung live und öffentlich verfügbar ist (nicht im Entwicklungsmodus). Dies können Sie in Ihrem Facebook Developer Dashboard überprüfen.
- **Berechtigungen:** Stellen Sie sicher, dass Ihre Facebook-App die notwendigen Berechtigungen zur Verwaltung von Seiten hat.
- **Cache:** Leeren Sie den PrestaShop Smarty-Cache (Erweiterte Einstellungen > Performance) und Ihren Browser-Cache. Manchmal dauert es einen Moment, bis Änderungen übernommen werden.
- **Facebook Page Admin:** Stellen Sie sicher, dass das Facebook-Konto, das Sie zur Verwaltung der Fanpage verwenden, Administratorrechte sowohl für die Fanpage als auch für die Facebook-App besitzt.

**F2: Die auf dem Facebook-Tab angezeigten Produkte sind nicht die, die ich erwarte.**
A2:

- **Einstellung „Produkte mit bestimmten Rabatten/Verkäufen anzeigen“:** Stellen Sie sicher, dass diese aktiviert ist, wenn Sie nur reduzierte Artikel anzeigen möchten.
- **Produktrabatte:** Überprüfen Sie, ob die Produkte, die Sie *erwarten* zu sehen, tatsächlich aktive Sonderpreise oder prozentuale Rabatte in Ihren PrestaShop-Produkteinstellungen konfiguriert haben.
- **Einstellung „Produkte aus bestimmten Kategorien anzeigen“:** Wenn Sie bestimmte Kategorien ausgewählt haben, stellen Sie sicher, dass die Produkte, die Sie anzeigen möchten, zu diesen Kategorien gehören.
- **„Anzahl der anzuzeigenden Produkte“:** Wenn Sie viele Verkäufe haben, diese Zahl aber niedrig ist, werden nur die ersten paar angezeigt.

**F3: Wie erhalte ich eine Facebook App ID, App Secret und Page ID?**
A3:

- **Facebook App ID & App Secret:** Gehen Sie zu [developers.facebook.com](https://developers.facebook.com/), melden Sie sich an und erstellen Sie eine neue App. Befolgen Sie die Anweisungen von Facebook, um eine neue App einzurichten, wählen Sie typischerweise einen „Business“- oder „Website“-Typ. Nach der Erstellung finden Sie die App ID und das App Secret in den Dashboard-Einstellungen Ihrer App.
- **Facebook Page ID:** Navigieren Sie zu Ihrer Facebook-Fanpage. Die Page ID finden Sie oft im Abschnitt „Info“ Ihrer Seite. Alternativ gibt es Online-Tools (suchen Sie nach „Facebook Page ID Finder“), in die Sie Ihre Fanpage-URL einfügen können, um deren ID abzurufen.

**F4: Das Tab-Symbol oder der Titel wird auf Facebook nicht aktualisiert.**
A4:

- **Facebook-Caching:** Facebook selbst kann Seiteninformationen zwischenspeichern. Es kann einige Zeit (bis zu ein paar Stunden) dauern, bis Änderungen am Tab-Titel oder -Symbol global sichtbar werden.
- **Modulkonfiguration speichern:** Stellen Sie sicher, dass Sie die Modulkonfiguration nach Änderungen gespeichert haben.
- **Cache leeren:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Performance) und Ihren Browser-Cache.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Facebook Sales Tab` (`prestasales`) ist ein Standard-PrestaShop-Modul, das für die Integration mit der Facebook-Plattform entwickelt wurde. Seine Hauptfunktion besteht darin, Inhalte (insbesondere eine Liste von Verkaufsprodukten) bereitzustellen, die in einem Facebook-Fanpage-Tab eingebettet werden können. Das Modul nutzt das PrestaShop-Konfigurationssystem, um Facebook-API-Anmeldeinformationen und Anzeigepräferenzen zu speichern. Es führt keine komplexen MVC-Muster oder benutzerdefinierten Datenbanktabellen ein, sondern verlässt sich auf die Kernfunktionen von PrestaShop für den Produktabruf und die Konfigurationsverwaltung. Die Hauptlogik des Moduls befindet sich in seiner `de.php`-Datei und behandelt Installation, Deinstallation und Konfigurationsanzeige.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird direkt innerhalb der `getContent()`-Methode der Hauptmodulklasse behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen ein. Es interagiert direkt mit den PrestaShop-Kernklassen `Product` und `Category` sowie der `Configuration`-Klasse für Einstellungen.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`prestasales/css/css.css`**:
  - **Umfang:** Dieses Stylesheet ist für die Gestaltung des im Facebook-Tab angezeigten Inhalts vorgesehen.
  - **Wichtige UI-Komponenten und Container, die es gestaltet:** Es würde typischerweise Stile für Produktlisten, Bilder, Preise, Rabattabzeichen und „In den Warenkorb“- oder „Produkt ansehen“-Schaltflächen innerhalb des eingebetteten Facebook-Tabs enthalten.
  - **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können:** Entwickler sollten die HTML-Ausgabe innerhalb des Facebook-Tabs überprüfen, um spezifische Klassennamen zu identifizieren. Gängige Selektoren könnten `.prestasales-product-list`, `.prestasales-product-item`, `.prestasales-product-image`, `.prestasales-product-name`, `.prestasales-price`, `.prestasales-discount`, `.prestasales-button` sein.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul listet in der bereitgestellten Inventur keine `.tpl`-Dateien explizit auf. Basierend auf seiner Funktionalität würde es jedoch typischerweise Folgendes enthalten:

- **Hook-Templates (`views/templates/hook/`)**:

  - Es ist sehr wahrscheinlich, dass ein Template wie `views/templates/hook/displayFacebookSalesTab.tpl` (oder ähnlich) intern in der `de.php`-Datei des Moduls existiert oder dynamisch generiert wird. Dieses Template wäre für das Rendern der HTML-Struktur der Produktliste verantwortlich, die dann an Facebook gesendet wird.
  - **Zweck:** Dieses Template würde die ausgewählten Verkaufsprodukte durchlaufen und deren Bilder, Namen, Preise und Links anzeigen, formatiert für die Einbettung in ein Facebook-Iframe.
- **Admin-Templates (`views/templates/admin/`)**:

  - Da die Konfiguration von `getContent()` behandelt wird, würde ein Template wie `views/templates/admin/configure.tpl` oder `views/templates/admin/configuration_form.tpl` verwendet, um das Back-Office-Konfigurationsformular des Moduls zu rendern. Dieses Template würde die Eingabefelder für App ID, App Secret, Page ID, Produktanzeigeoptionen usw. enthalten.
- **Front-Office-Templates (`views/templates/front/`)**:

  - Es werden keine dedizierten Front-Office-Templates erwartet, da die Ausgabe des Moduls hauptsächlich für die Facebook-Plattform bestimmt ist.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Alle Konfigurationseinstellungen werden in der PrestaShop-Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `PRESTASALES_APP_ID`, `PRESTASALES_APP_SECRET`, `PRESTASALES_PAGE_ID`, `PRESTASALES_NUM_PRODUCTS`, `PRESTASALES_CATEGORIES`, `PRESTASALES_DISCOUNTS_ONLY`, `PRESTASALES_TAB_TITLE`, `PRESTASALES_TAB_ICON` gespeichert.
- **Registrierte Hooks-Tabelle**:
  Die primäre Interaktion des Moduls mit dem PrestaShop-Hook-System wäre für seine Konfiguration und möglicherweise für das Rendern des Inhalts, den Facebook abruft.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Abschnitt jeder Front-Office-Seite. | Obwohl das Modul keine Inhalte direkt im Shop anzeigt, könnte es diesen Hook verwenden, um notwendige Facebook SDK-Skripte oder Meta-Tags zu laden, wenn es erweiterte Facebook-Integrationsfunktionen (z. B. Open Graph-Tags) implementieren würde, obwohl dies für die Kernfunktion dieses Moduls nicht explizit angegeben ist. |
| `displayBackOfficeHeader` | Im `<head>`-Abschnitt jeder Back-Office-Seite. | Wird verwendet, um modulspezifisches CSS oder JS für die Konfigurationsseite zu laden, falls vorhanden. |
| `moduleRoutes` | Während der Initialisierung der URL-Umschreibung. | Wird von diesem Modul nicht explizit verwendet, da es keine benutzerdefinierten Front-Office-Routen definiert. |
| `actionProductUpdate` / `actionProductAdd` | Nach der Aktualisierung oder Hinzufügung eines Produkts. | Nicht explizit verwendet, könnte aber zum Leeren des Caches im Zusammenhang mit Produktlisten für den Facebook-Tab verwendet werden. |
| `actionModuleInstall` | Während der Modulinstallation. | Zum Registrieren von Konfigurationsstandards und möglicherweise zum Einrichten erster Schritte der Facebook App-Integration. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Zum Bereinigen von Konfigurationsdaten aus `ps_configuration`. |

Die Kernfunktionalität der Bereitstellung des Inhalts an Facebook wird wahrscheinlich durch eine direkte Anfrage an die Haupt-PHP-Datei des Moduls (`de.php`) oder eine spezifische interne Methode, die die Produktliste rendert, gehandhabt, anstatt durch einen Standard-PrestaShop-`display`-Hook. Dieser Inhalt wird dann in einem Iframe auf der Facebook-Fanpage eingebettet.

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul „Facebook Sales Tab“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.

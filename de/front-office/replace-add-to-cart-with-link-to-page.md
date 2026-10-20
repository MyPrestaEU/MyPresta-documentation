---
title: "Warenkorb-Button durch Link zu Seite ersetzen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Warenkorb-Button durch Link zu Seite ersetzen“ von MyPresta.eu."
sidebar:
  label: "Warenkorb-Button durch Link zu Seite ersetzen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Replace add to cart with link to page auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/replace-add-to-cart-with-link-to-page.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/replace-add-to-cart-with-link-to-page/)
>
> ---


# Warenkorb-Button durch Link zu Seite ersetzen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptbildschirm, auf dem Sie das globale Verhalten des Moduls steuern.

- **Aktiviert**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die Funktionalität des Moduls in Ihrem gesamten Shop ein- oder auszuschalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul beginnt, „In den Warenkorb“-Buttons durch benutzerdefinierte Links zu ersetzen, basierend auf Ihren produktspezifischen Einstellungen und anderen globalen Konfigurationen.
    - *Wenn deaktiviert:* Das Modul ist inaktiv, und alle „In den Warenkorb“-Buttons kehren zu ihrem Standard-PrestaShop-Verhalten zurück.
  - **Empfohlener Wert:** JA (um das Modul zu aktivieren).
  - **Händlerszenario / Beispiel:** Wenn Sie das Modul testen oder seine Funktionalität vorübergehend deaktivieren möchten, ohne es zu deinstallieren, können Sie dies auf NEIN setzen. Für den aktiven Gebrauch sollte es JA sein.
- **Button-Text**

  - **Was diese Einstellung bewirkt:** Definiert den Text, der auf dem benutzerdefinierten Button erscheint und den „In den Warenkorb“-Text ersetzt. Dieser Text kann in verschiedene Sprachen übersetzt werden.
  - **Auswirkung der Änderung dieser Einstellung:** Der Text auf dem Button ändert sich zu Ihrem angegebenen Wert.
  - **Empfohlener Wert:** Etwas Beschreibendes wie „Mehr erfahren“, „Angebot anfordern“, „Details anzeigen“ oder „Partnerseite besuchen“.
  - **Händlerszenario / Beispiel:** Wenn Sie auf eine externe Website für weitere Informationen verlinken, könnten Sie dies auf „Mehr erfahren“ setzen. Wenn Sie Kunden zu einem Angebotsformular leiten, wäre „Angebot anfordern“ passend.
- **Mengenfeld ausblenden**

  - **Was diese Einstellung bewirkt:** Steuert, ob das Mengeneingabefeld (wo Kunden die Anzahl der hinzuzufügenden Artikel auswählen) auf Produktseiten sichtbar ist, wenn das Modul aktiv ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Mengenauswahl wird ausgeblendet, da sie irrelevant ist, wenn der Button umleitet, anstatt in den Warenkorb zu legen.
    - *Wenn deaktiviert:* Die Mengenauswahl bleibt sichtbar, was verwirrend sein könnte, wenn der Button nicht in den Warenkorb legt.
  - **Empfohlener Wert:** JA.
  - **Händlerszenario / Beispiel:** Da der Button nicht mehr in den Warenkorb legt, ist ein Mengenfeld normalerweise nicht erforderlich. Das Ausblenden vereinfacht die Benutzeroberfläche und vermeidet Verwirrung.
- **CSS-Klasse des „In den Warenkorb“-Buttons auf der Produktseite**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, eine benutzerdefinierte CSS-Klasse für den Ersatz-Button auf der Produktseite anzugeben. Dies ist nützlich, um den Button an Ihr Theme anzupassen oder ihn hervorzuheben.
  - **Auswirkung der Änderung dieser Einstellung:** Der Button erbt die durch diese CSS-Klasse in der Stylesheet-Datei Ihres Themes definierten Stile.
  - **Empfohlener Wert:** Leer lassen, wenn die Standard-Button-Gestaltung Ihres Themes akzeptabel ist, oder eine Klasse wie `btn btn-primary` oder `my-custom-button` verwenden, wenn Sie spezifische Stile haben.
  - **Händlerszenario / Beispiel:** Wenn Ihr Theme `btn-success` für primäre Aktionsbuttons verwendet, könnten Sie hier `btn-success` eingeben, um Ihren benutzerdefinierten Button grün und prominent zu machen.
- **Mengen-CSS-Klasse**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, eine CSS-Klasse für das Mengeneingabefeld auf der Produktseite anzugeben. Dies ist hauptsächlich für fortgeschrittenes Styling oder wenn Sie das Mengenfeld mit benutzerdefiniertem CSS ansprechen müssen.
  - **Auswirkung der Änderung dieser Einstellung:** Das Mengeneingabefeld erhält diese CSS-Klasse.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben einen spezifischen Styling-Bedarf.
  - **Händlerszenario / Beispiel:** Ein Entwickler könnte dies verwenden, um dem Mengenfeld eine bestimmte Breite oder Polsterung zuzuweisen, wenn es nicht ausgeblendet ist.
- **Modul auf Produktlisten anwenden**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob die Funktionalität des Moduls (Ersetzen von „In den Warenkorb“ durch einen benutzerdefinierten Link) auch auf Produktbuttons angewendet wird, die in Listen angezeigt werden (z. B. Kategorieseiten, Suchergebnisse, vorgestellte Produkte auf der Startseite).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* „In den Warenkorb“-Buttons in Produktlisten werden ebenfalls durch den benutzerdefinierten Link ersetzt.
    - *Wenn deaktiviert:* Nur der „In den Warenkorb“-Button der Produktseite ist betroffen; Produktlisten-Buttons behalten ihr Standardverhalten bei.
  - **Empfohlener Wert:** JA, für Konsistenz in Ihrem Shop, insbesondere wenn der benutzerdefinierte Link ein kritischer Bestandteil Ihres Verkaufstrichters ist.
  - **Händlerszenario / Beispiel:** Wenn alle Produkte, die diesen benutzerdefinierten Link erfordern, Dienstleistungen sind, die ein Angebot benötigen, möchten Sie dies aktivieren, damit Kunden nicht versuchen, von einer Kategorieseite aus „in den Warenkorb“ zu legen.
- **CSS-Klasse des Elements mit Produkt**

  - **Was diese Einstellung bewirkt:** Dies ist eine technische Einstellung, die dem Modul hilft, den Hauptcontainer für ein Produkt in einer Listenansicht zu identifizieren. Es ist entscheidend, dass das Modul den „In den Warenkorb“-Button innerhalb jedes Produktelements korrekt findet und modifiziert.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn falsch, kann das Modul seine Änderungen möglicherweise nicht auf Produktlistenelemente anwenden.
  - **Empfohlener Wert:** Dies ist stark Theme-abhängig. Gängige Werte sind `product-miniature`, `product-container`, `product-item`. Möglicherweise müssen Sie den HTML-Code Ihres Themes überprüfen, um die richtige Klasse zu finden.
  - **Händlerszenario / Beispiel:** Wenn Ihr Theme `<div class="product-card">` für jedes Produkt in einer Liste verwendet, würden Sie hier `product-card` eingeben.
- **CSS-Klasse von** (Dies bezieht sich wahrscheinlich auf den „In den Warenkorb“-Button selbst innerhalb eines Produktlistenelements)

  - **Was diese Einstellung bewirkt:** Gibt die CSS-Klasse des „In den Warenkorb“-Buttons innerhalb von Produktlistenelementen an. Dies hilft dem Modul, den richtigen Button für den Ersatz anzusprechen.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn falsch, ersetzt das Modul möglicherweise den „In den Warenkorb“-Button in Produktlisten nicht.
  - **Empfohlener Wert:** Dies ist stark Theme-abhängig. Gängige Werte sind `add-to-cart`, `product-add-to-cart`, `btn-primary`. Überprüfen Sie den HTML-Code Ihres Themes.
  - **Händlerszenario / Beispiel:** Wenn der „In den Warenkorb“-Button Ihres Themes in Listen die Klasse `btn-add-to-cart` hat, würden Sie dies hier eingeben.
- **CSS-Klasse des Mengenfeldes in Produktlisten**

  - **Was diese Einstellung bewirkt:** Ähnlich wie die Einstellung für die Produktseite können Sie hier die CSS-Klasse für das Mengeneingabefeld angeben, wenn Produkte in einer Liste angezeigt werden. Dies wird verwendet, um es auszublenden, wenn `Mengenfeld ausblenden` aktiviert ist.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn falsch, bleibt das Mengenfeld möglicherweise in Produktlisten sichtbar, selbst wenn Sie es ausgeblendet haben.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben einen spezifischen Styling-Bedarf oder das Mengenfeld wird nicht korrekt ausgeblendet. Überprüfen Sie den HTML-Code Ihres Themes.
  - **Händlerszenario / Beispiel:** Wenn Ihr Theme `product-quantity-input` für das Mengenfeld in Listen verwendet, würden Sie dies hier eingeben.
- **Tooltip über Button ausblenden**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Standard-PrestaShop-Tooltip (oft „In den Warenkorb“ oder Ähnliches anzeigend) beim Überfahren des benutzerdefinierten Buttons erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Tooltip wird ausgeblendet, wodurch potenziell verwirrende Nachrichten verhindert werden.
    - *Wenn deaktiviert:* Der Standard-Tooltip könnte weiterhin erscheinen, was mit dem Zweck des benutzerdefinierten Buttons kollidieren könnte.
  - **Empfohlener Wert:** JA.
  - **Händlerszenario / Beispiel:** Wenn Ihr benutzerdefinierter Button „Angebot anfordern“ sagt, möchten Sie keinen Tooltip, der „In den Warenkorb“ anzeigt. Das Ausblenden sorgt für eine klare Botschaft.
- **rel=„nofollow“ hinzufügen**

  - **Was diese Einstellung bewirkt:** Fügt dem benutzerdefinierten Link das Attribut `rel="nofollow"` hinzu. Dies weist Suchmaschinen an, dem Link nicht zu folgen und keinen „Link-Juice“ an das Ziel weiterzugeben.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Link hat `rel="nofollow"`, was nützlich ist für externe Links, die Sie nicht unterstützen möchten, oder für interne Links, die für SEO nicht kritisch sind (z. B. Anmeldeseiten).
    - *Wenn deaktiviert:* Der Link ist ein standardmäßig verfolgter Link.
  - **Empfohlener Wert:** JA für externe Links, insbesondere Affiliate-Links oder Links zu Websites, die Sie nicht vollständig kontrollieren. NEIN für interne Links innerhalb Ihrer eigenen Website, die Suchmaschinen crawlen sollen.
  - **Händlerszenario / Beispiel:** Wenn Sie auf die Website eines Affiliate-Partners verlinken, ist die Aktivierung von `nofollow` eine bewährte Methode, um potenzielle SEO-Strafen zu vermeiden und klar anzuzeigen, dass es sich um einen gesponserten oder externen Link handelt.
- **Links in neuem Fenster (Tab) öffnen**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob der benutzerdefinierte Link im selben Browser-Tab oder in einem neuen geöffnet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Link wird in einem neuen Browser-Tab geöffnet, wobei Ihre Shop-Seite im ursprünglichen Tab geöffnet bleibt.
    - *Wenn deaktiviert:* Der Link wird im selben Tab geöffnet, wodurch der Kunde von Ihrem Shop wegnavigiert wird.
  - **Empfohlener Wert:** JA für externe Links, um Kunden auf Ihrer Website zu halten. NEIN für interne Links, bei denen der Kunde innerhalb Ihres Shops navigieren soll.
  - **Händlerszenario / Beispiel:** Wenn Sie Kunden auf eine externe Partnerseite leiten, ist das Öffnen in einem neuen Tab im Allgemeinen besser, damit sie leicht zu Ihrer Produktseite zurückkehren können.
- **Modulsichtbarkeit für ausgewählte Produkte**

  - **Was diese Einstellung bewirkt:** Dies ist eine entscheidende Einstellung, die definiert, *welche* Produkte ihren „In den Warenkorb“-Button ersetzt bekommen. Sie funktioniert in Verbindung mit den produktspezifischen Einstellungen, die Sie auf der Bearbeitungsseite jedes Produkts finden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Aktiviert:* Das Modul wird nur auf Produkte angewendet, bei denen Sie explizit eine benutzerdefinierte URL in deren Produkteinstellungen definiert haben.
    - *Deaktiviert:* Das Modul wird auf keine Produkte angewendet, unabhängig von deren individuellen Einstellungen.
  - **Empfohlener Wert:** Aktiviert. Dies ermöglicht Ihnen, die benutzerdefinierte Linkfunktion selektiv auf bestimmte Produkte anzuwenden.
  - **Händlerszenario / Beispiel:** Sie möchten den „In den Warenkorb“-Button nur für Ihre maßgefertigten Möbel ersetzen, nicht für Standardzubehör. Sie würden diese Einstellung aktivieren und dann zu jedem Möbelprodukt gehen und dessen benutzerdefinierte URL festlegen.

#### Produktspezifische Einstellungen (Back Office > Katalog > Produkte > Produkt bearbeiten > Module-Tab)

Sobald das Modul installiert und aktiviert ist, finden Sie neue Einstellungen beim Bearbeiten einzelner Produkte.

- **Produkt-URL-Feld**
  - **Was diese Einstellung bewirkt:** Hier geben Sie die spezifische URL ein, zu der der „In den Warenkorb“-Button für *dieses bestimmte Produkt* weiterleiten soll.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn ein Kunde auf den benutzerdefinierten Button auf der Seite dieses Produkts (oder in einer Liste, falls aktiviert) klickt, wird er zu dieser URL weitergeleitet.
  - **Empfohlener Wert:** Eine vollständige, gültige URL (z. B. `https://example.com/request-a-quote` oder `/contact-us`).
  - **Händlerszenario / Beispiel:** Für ein Produkt „Kundenspezifischer Design-Service“ könnten Sie hier `https://ihrshop.com/kontakt?betreff=Anfrage%20kundenspezifisches%20Design` eingeben.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### AdminAtcurlSearchController (Back Office > Module > Warenkorb-Button durch Link zu Seite ersetzen > Konfigurieren > „Ausgewählte Produkte“-Tab)

Dieser Bildschirm bietet eine zentrale Möglichkeit, zu verwalten und anzuzeigen, welche Produkte mit benutzerdefinierten URLs konfiguriert sind.

- **Bildschirmname & Menüpfad:** Sie greifen auf diesen Bildschirm zu, indem Sie zu **Module > Modul-Manager** navigieren, „Warenkorb-Button durch Link zu Seite ersetzen“ finden, auf „Konfigurieren“ klicken und dann den Tab „Ausgewählte Produkte“ (oder ähnlich, je nach Modulversion) auswählen.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt typischerweise ein Raster oder eine Liste von Produkten an, die derzeit eine benutzerdefinierte URL definiert haben.
  - **Spalten:** Sie sehen normalerweise Spalten wie Produkt-ID, Produktname und die benutzerdefinierte URL.
  - **Suchen/Filtern:** Es können Such- oder Filteroptionen vorhanden sein, um schnell bestimmte Produkte zu finden.
  - **Bearbeiten/Löschen:** Sie können direkte Links zum Bearbeiten des Produkts (was Sie zur Standard-Produktbearbeitungsseite führt) oder zum Entfernen der benutzerdefinierten URL für ein Produkt direkt aus dieser Liste haben.
- **Auswirkung von Änderungen:**
  - Das Ändern einer URL hier (falls direkte Bearbeitung verfügbar ist) oder über die Produktbearbeitungsseite ändert sofort, wohin der Button für dieses Produkt weiterleitet.
  - Das Entfernen eines Produkts aus dieser Liste (oder das Löschen seiner benutzerdefinierten URL auf der Produktbearbeitungsseite) setzt den „In den Warenkorb“-Button auf das Standard-PrestaShop-Verhalten zurück.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie diesen Bildschirm, um schnell zu überprüfen, welche Produkte die benutzerdefinierte Linkfunktion verwenden. Wenn Sie viele Produktlinks aktualisieren müssen, hilft Ihnen diese Ansicht, den Überblick zu behalten. Zum Hinzufügen neuer Links ist es normalerweise effizienter, direkt zur Bearbeitungsseite des Produkts zu gehen.

#### index.php (atcurl/controllers/admin/index.php)

Diese Datei ist ein Platzhalter und stellt typischerweise keinen benutzerorientierten Admin-Bildschirm dar. In PrestaShop werden `index.php`-Dateien in Controller-Verzeichnissen oft verwendet, um direkte Verzeichnisauflistungen zu verhindern oder andere Dateien einzuschließen. Es ist kein Konfigurationsbildschirm für Händler.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Aktiviert | JA | Hauptschalter zum Aktivieren/Deaktivieren der Modulfunktionalität. |
|  | Button-Text | „Mehr erfahren“ (Beispiel) | Text, der auf dem benutzerdefinierten Button angezeigt wird. |
|  | Mengenfeld ausblenden | JA | Blendet die Mengenauswahl auf Produktseiten aus. |
|  | CSS-Klasse des „In den Warenkorb“-Buttons auf der Produktseite | (Leer / Theme-abhängig) | Benutzerdefinierte CSS-Klasse für den Button auf Produktseiten. |
|  | Mengen-CSS-Klasse | (Leer) | Benutzerdefinierte CSS-Klasse für die Mengeneingabe auf Produktseiten. |
|  | Modul auf Produktlisten anwenden | JA | Erweitert die Modulfunktionalität auf Produktlistenseiten. |
|  | CSS-Klasse des Elements mit Produkt | `product-miniature` (Beispiel) | Hilft dem Modul, Produktcontainer in Listen zu identifizieren. |
|  | CSS-Klasse von (In den Warenkorb-Button in Liste) | `add-to-cart` (Beispiel) | Hilft dem Modul, „In den Warenkorb“-Buttons in Listen zu identifizieren. |
|  | CSS-Klasse des Mengenfeldes in Produktlisten | (Leer) | Benutzerdefinierte CSS-Klasse für die Mengeneingabe in Produktlisten. |
|  | Tooltip über Button ausblenden | JA | Verhindert den Standard-„In den Warenkorb“-Tooltip auf dem benutzerdefinierten Button. |
|  | rel=„nofollow“ hinzufügen | JA (für extern) / NEIN (für intern) | Fügt dem benutzerdefinierten Link das `nofollow`-Attribut hinzu. |
|  | Links in neuem Fenster (Tab) öffnen | JA (für extern) / NEIN (für intern) | Öffnet den benutzerdefinierten Link in einem neuen Browser-Tab. |
|  | Modulsichtbarkeit für ausgewählte Produkte | Aktiviert | Aktiviert die produktspezifische URL-Konfiguration. |
| **Produktbearbeitungsseite (Module-Tab)** | Produkt-URL-Feld | (Benutzerdefinierte URL) | Definiert die spezifische Weiterleitungs-URL für *dieses* Produkt. |
| **AdminAtcurlSearchController** | Raster der Produkte mit benutzerdefinierten URLs | N/A | Zentrale Ansicht zur Verwaltung von Produkten mit benutzerdefinierten Links. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein „In den Warenkorb“-Button ändert sich nicht, obwohl ich eine URL konfiguriert habe.**
A1:

- **Modulstatus überprüfen:** Stellen Sie zunächst sicher, dass der Schalter „Aktiviert“ auf der Hauptkonfigurationsseite des Moduls auf JA steht.
- **Produktsichtbarkeit überprüfen:** Stellen Sie sicher, dass „Modulsichtbarkeit für ausgewählte Produkte“ auf der Konfigurationsseite des Moduls auf „Aktiviert“ steht.
- **Produkt-URL überprüfen:** Vergewissern Sie sich, dass Sie eine gültige URL im „Produkt-URL-Feld“ für das spezifische Produkt, das Sie testen, eingegeben haben (auf der Produktbearbeitungsseite unter dem Tab „Module“).
- **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal speichert PrestaShop alte Inhalte im Cache.
- **Theme-Kompatibilität:** Ihr Theme verwendet möglicherweise nicht-standardmäßige CSS-Klassen für seinen „In den Warenkorb“-Button oder Produktcontainer. Überprüfen Sie die Einstellungen „CSS-Klasse des Elements mit Produkt“ und „CSS-Klasse von“ auf der Modulkonfigurationsseite. Möglicherweise müssen Sie die Entwicklertools Ihres Browsers (F12) verwenden, um den HTML-Code zu überprüfen und die richtigen Klassen zu finden.

**F2: Das Mengenfeld ist immer noch sichtbar, obwohl ich es ausgeblendet habe.**
A2:

- **„Mengenfeld ausblenden“ überprüfen:** Stellen Sie sicher, dass diese Einstellung auf der Konfigurationsseite des Moduls aktiviert ist.
- **„CSS-Klasse des Mengenfeldes“ überprüfen:** Wenn Ihr Theme eine nicht-standardmäßige Klasse für die Mengeneingabe verwendet, kann das Modul diese möglicherweise nicht finden und ausblenden. Verwenden Sie die Entwicklertools Ihres Browsers, um das Mengeneingabefeld zu überprüfen und seine CSS-Klasse in die Einstellung „Mengen-CSS-Klasse“ (für die Produktseite) und „CSS-Klasse des Mengenfeldes in Produktlisten“ (für Produktlisten) einzugeben.
- **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Konfigurationsänderungen vorgenommen haben.

**F3: Das Modul funktioniert auf Produktseiten, aber nicht auf Kategorie-/Listenseiten.**
A3:

- **„Modul auf Produktlisten anwenden“ überprüfen:** Stellen Sie sicher, dass diese Einstellung auf der Konfigurationsseite des Moduls aktiviert ist.
- **CSS-Klassen für Listen überprüfen:** Das Modul muss wissen, wie Ihr Theme Produktlisten strukturiert. Überprüfen Sie, ob die Einstellungen „CSS-Klasse des Elements mit Produkt“ und „CSS-Klasse von“ (für den Button) für Ihr Theme korrekt sind. Diese unterscheiden sich oft von den Klassen der Produktseite. Verwenden Sie die Entwicklertools des Browsers, um Elemente auf einer Kategorieseite zu überprüfen.
- **Cache leeren:** Leeren Sie Ihren PrestaShop-Cache.

**F4: Mein benutzerdefinierter Button sieht nicht richtig aus (falsche Farbe, Größe usw.).**
A4:

- **CSS-Klasse für Styling:** Verwenden Sie die Einstellung „CSS-Klasse des „In den Warenkorb“-Buttons auf der Produktseite“. Geben Sie eine CSS-Klasse ein, die bereits in Ihrem Theme existiert und das gewünschte Styling bietet (z. B. `btn btn-primary`, `btn-success`).
- **Benutzerdefiniertes CSS:** Wenn Sie ein einzigartiges Styling benötigen, müssen Sie Ihrem Theme benutzerdefiniertes CSS hinzufügen. Sie können den Button über die Klasse ansprechen, die Sie in der Modulkonfiguration festgelegt haben, oder indem Sie seinen HTML-Code überprüfen. Zum Beispiel:

  ```
  .my-custom-button-class { background-color: #ff6600; color: white; border-radius: 5px; padding: 10px 20px;}
  ```

  Fügen Sie dieses CSS in die benutzerdefinierte CSS-Datei Ihres Themes oder über ein benutzerdefiniertes CSS-Modul hinzu.
- **Cache leeren:** Leeren Sie Ihren PrestaShop-Cache.

**F5: Wie übersetze ich den Button-Text in andere Sprachen?**
A5:

- Gehen Sie im PrestaShop Back Office zu **International > Übersetzungen**.
- Wählen Sie „Installierte Modulübersetzungen“, wählen Sie Ihr Theme und dann die Sprache aus, in die Sie übersetzen möchten.
- Suchen Sie das Modul „Warenkorb-Button durch Link zu Seite ersetzen“. Dort sehen Sie das Feld „Button-Text“, in dem Sie Übersetzungen für jede Sprache eingeben können.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Warenkorb-Button durch Link zu Seite ersetzen“ (`atcurl`) ist ein Standard-PrestaShop-Modul, das einem MVC-ähnlichen Muster folgt. Es erweitert hauptsächlich bestehende PrestaShop-Funktionalität durch Hooks, um die Front-Office-Anzeige von Produktseiten und Produktlisten zu modifizieren. Die Konfiguration wird über die `getContent()`-Methode des Hauptmoduls gehandhabt und in `ps_configuration` gespeichert. Produktspezifische URLs werden als `Product::specific_fields` oder möglicherweise in einer benutzerdefinierten Tabelle gespeichert, wobei ein Admin-Controller (`AdminAtcurlSearchController`) eine Verwaltungsoberfläche bereitstellt. JavaScript wird intensiv verwendet, um Buttons dynamisch zu ersetzen und Elemente im Front-Office auszublenden.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Dieses Modul enthält keine dedizierten Front-Office-Controller. Alle Front-Office-Modifikationen werden über Hooks und JavaScript gehandhabt.
- **Back-Office-Admin-Controller**:

  - `atcurl/controllers/admin/AdminAtcurlSearchController.php`
    - **Klassenname & Elternklasse:** `AdminAtcurlSearchController` erweitert `ModuleAdminController`.
    - **Tab-Name und verwaltete Entität:** Dieser Controller ist wahrscheinlich dafür verantwortlich, ein Raster oder eine Liste von Produkten anzuzeigen, die eine vom Modul konfigurierte benutzerdefinierte URL haben. Er bietet eine zentrale Ansicht zur Verwaltung dieser Produktzuordnungen und ermöglicht möglicherweise schnelle Bearbeitungen oder Entfernungen der benutzerdefinierten URL. Er verwaltet kein dediziertes `ObjectModel`, sondern interagiert mit Produktdaten und der Modulkonfiguration.
  - `atcurl/controllers/admin/index.php`
    - Dies ist eine Standard-PrestaShop-Platzhalterdatei, die typischerweise `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../../../"); exit;` enthält, um direkte Verzeichnisauflistungen zu verhindern und zum Haupt-Admin-Panel umzuleiten. Sie bietet keine funktionale Controller-Logik.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul scheint keine benutzerdefinierten Klassen oder `ObjectModel`s im Verzeichnis `classes/` zu definieren. Produktspezifische URLs werden wahrscheinlich als `Product::specific_fields` oder direkt in der Tabelle `ps_configuration` gespeichert, mit der Produkt-ID als Schlüssel, oder möglicherweise als benutzerdefiniertes Feld, das der Produktentität hinzugefügt wurde.

### 4.4 JavaScript-Assets (`views/js/`)

- `atcurl/lib/js/admin/atcurl177.js`
  - **Umfang:** Back-Office (Admin).
  - **Verantwortlichkeit:** Behandelt wahrscheinlich die Logik, die spezifisch für die Konfigurationsseite des Moduls oder den `AdminAtcurlSearchController` für PrestaShop 1.7.7+ Versionen ist. Dies könnte AJAX-Aufrufe zum Speichern von Einstellungen, dynamische Updates der Benutzeroberfläche oder Interaktionen mit dem Produktsuch-/Auswahlwerkzeug umfassen.
- `atcurl/lib/js/front/atcurl-list-177.js`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Zielt speziell auf Produktlistenseiten (Kategorie, Suche, Startseitenblöcke) ab. Es überwacht DOM-Änderungen (z. B. wenn Produkte über AJAX geladen werden) und ersetzt dynamisch „In den Warenkorb“-Buttons durch den benutzerdefinierten Link, blendet Mengenfelder aus und wendet benutzerdefinierte CSS-Klassen gemäß der Konfiguration an. Es ist für PrestaShop 1.7.7+ Themes zugeschnitten.
- `atcurl/lib/js/front/atcurl177.js`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Zielt hauptsächlich auf die einzelne Produktseite ab. Es identifiziert den „In den Warenkorb“-Button, ersetzt ihn durch den benutzerdefinierten Link, blendet die Mengeneingabe aus und wendet `nofollow`- oder `target="_blank"`-Attribute basierend auf den Moduleinstellungen an. Es kümmert sich auch um das Ausblenden von Tooltips. Zugeschnitten für PrestaShop 1.7.7+ Themes.
- `atcurl/lib/searchTool/views/js/autocomplete.js`
  - **Umfang:** Back-Office (Admin).
  - **Verantwortlichkeit:** Bietet Autocomplete-Funktionalität, wahrscheinlich zur Auswahl von Produkten in der Modulkonfiguration oder im `AdminAtcurlSearchController`-Raster. Dies hilft Administratoren, Produkte schnell zu finden und mit benutzerdefinierten URLs zu verknüpfen.

### 4.5 CSS-Stylesheets (`views/css/`)

- `atcurl/lib/searchTool/views/css/autocomplete.css`
  - **Umfang:** Back-Office (Admin).
  - **Verantwortlichkeit:** Gestaltet das Autocomplete-Dropdown und verwandte UI-Elemente, die im Admin-Suchwerkzeug verwendet werden, um sicherzustellen, dass es visuell in das PrestaShop Back Office Theme integriert ist.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `atcurl/views/hook/displayProductAdditionalInfo.tpl`
    - **Hook:** `displayProductAdditionalInfo`
    - **Zweck:** Dieses Template wird wahrscheinlich auf der Produktseite gerendert und stellt den Container oder den eigentlichen benutzerdefinierten Button-HTML-Code bereit, der den Standard-„In den Warenkorb“-Button ersetzt. Es würde die Logik enthalten, um den benutzerdefinierten Button-Text und Link anzuzeigen.
  - `atcurl/views/hook/displayProductListReviews.tpl`
    - **Hook:** `displayProductListReviews` (Dieser Hook-Name ist ungewöhnlich für den Button-Ersatz und könnte ein Tippfehler oder eine indirekte Methode sein, um JS/CSS für Produktlisten zu injizieren. Es ist üblicher, `displayProductListFunctionalButtons` oder `displayProductActions` für Button-Modifikationen in Listen zu verwenden).
    - **Zweck:** Falls verwendet, würde dieses Template JavaScript oder ein verstecktes Element in Produktlistenelemente injizieren, das das Skript `atcurl-list-177.js` dann verwendet, um den Button-Ersatz durchzuführen. Es ist weniger wahrscheinlich, dass es den Button-HTML-Code direkt enthält.
- **Admin-Templates (`views/templates/admin/`)**:

  - `atcurl/lib/searchTool/views/scripts.tpl`
    - **Zweck:** Dieses Template wird wahrscheinlich im Back Office eingebunden, um die notwendigen JavaScript-Dateien (`autocomplete.js`) und möglicherweise CSS-Dateien (`autocomplete.css`) für das Produktsuch-/Auswahlwerkzeug zu laden, das in der Modulkonfiguration oder im `AdminAtcurlSearchController` verwendet wird.
  - `atcurl/views/tpl/selectedProducts.tpl`
    - **Zweck:** Dieses Template wird vom `AdminAtcurlSearchController` verwendet, um das Raster oder die Liste der Produkte zu rendern, die benutzerdefinierte URLs konfiguriert haben. Es definiert die Tabellenstruktur und wie die Informationen jedes Produkts (ID, Name, URL) angezeigt werden.
- **Front-Office-Templates (`views/templates/front/`)**: Keine explizit aufgeführt, da Front-Office-Änderungen hauptsächlich durch JS und Hook-Templates gehandhabt werden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul scheint keine benutzerdefinierten SQL-Tabellen zu erstellen.
  - **`ps_configuration`**: Speichert globale Moduleinstellungen (z. B. `ATC_URL_BUTTON_FRONT`, `ATC_URL_BUTTON_TEXT`, `ATC_URL_BLANK`, `ATC_URL_NOFOLLOW`, `ATC_HIDE_TOOLTIP`, `ATC_URL_PL`, `ATC_URL_visibility_rule`, `ATC_URL_BUTTON_QTY_HIDE`, `ATC_URL_visibility_products`, `ATC_URL_visibility_cat`).
  - **`ps_product_shop` / `ps_product_lang`**: Produktspezifische URLs werden wahrscheinlich als zusätzliches Feld gespeichert, das dem Produkt zugeordnet ist, möglicherweise unter Verwendung des `specific_fields`-Mechanismus von PrestaShop oder durch direkte Aktualisierung von Produkteigenschaften. Die `install()`-Methode des Moduls würde dieses Feld hinzufügen.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Umfang | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- | --- |
| `displayProductAdditionalInfo` | Front-Office | Auf der Produktseite, normalerweise unter der Produktbeschreibung oder dem Preisblock. | Fügt den benutzerdefinierten Button-HTML-Code oder einen Platzhalter für JS zum Ansprechen ein. |
| `ActionAdminControllerSetMedia` | Back-Office | Wenn ein Admin-Controller seine Medien (JS/CSS) lädt. | Lädt admin-spezifisches JavaScript (`atcurl177.js`, `autocomplete.js`) und CSS (`autocomplete.css`) für die Modulkonfiguration und Produktverwaltung. |
| `actionProductUpdate` | Back-Office | Nach dem Aktualisieren/Speichern eines Produkts im Back Office. | Ermöglicht dem Modul, die dem Produkt zugeordnete benutzerdefinierte URL zu speichern. |
| `displayHeader` | Front-Office | Im `<head>`-Bereich jeder Front-Office-Seite. | Fügt Front-Office-JavaScript (`atcurl177.js`, `atcurl-list-177.js`) und möglicherweise Inline-CSS oder Konfigurationsvariablen für die JS-Skripte ein. |
| `displayProductListReviews` | Front-Office | Innerhalb von Produktlistenelementen, oft in der Nähe des Produktnamens oder der Bewertung. | (Wie oben erwähnt, ist dieser Hook ungewöhnlich für den Button-Ersatz. Er wird wahrscheinlich verwendet, um JS für die Listenartikelverarbeitung zu injizieren, oder es könnte ein Legacy-Hook sein. Entwickler sollten seine tatsächliche Verwendung im Modulcode überprüfen.) |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Warenkorb-Button durch Link zu Seite ersetzen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Team ist bestrebt, sicherzustellen, dass das Modul optimal mit Ihrem PrestaShop-Shop funktioniert.

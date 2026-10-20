---
title: "Unverbindliche Preisempfehlung (UVP) des Herstellers - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Unverbindliche Preisempfehlung (UVP) des Herstellers“ von MyPresta.eu."
sidebar:
  label: "Unverbindliche Preisempfehlung (UVP) des Herstellers - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Manufacturer suggested / recommended retail price (MSRP) auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/manufacturer-suggested-recommended-retail-price-msrp.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/manufacturer-suggested-recommended-retail-price-msrp/)
>
> ---


# Unverbindliche Preisempfehlung (UVP) des Herstellers

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das UVP-Modul, der nach der Installation durch Klicken auf die Schaltfläche „Konfigurieren“ zugänglich ist. Hier definieren Sie, wie UVPs in Ihrem Shop angezeigt und verwaltet werden.

#### **UVP-Anzeige aktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die UVP-Funktion für Ihren gesamten Shop ein- oder auszuschalten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Modul beginnt, UVP-Informationen auf Ihren Produktseiten und in Produktlisten anzuzeigen, vorausgesetzt, Sie haben UVPs für Ihre Produkte eingegeben.
  - *Wenn deaktiviert (NEIN):* Die UVP-Funktion ist vollständig inaktiv, und es werden keine UVP-Informationen für Kunden angezeigt, selbst wenn Sie Werte eingegeben haben.
- **Empfohlener Wert:** JA (um die Funktionen des Moduls zu nutzen).
- **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal einrichten, aktivieren Sie es, um die Änderungen zu sehen. Wenn Sie UVPs vorübergehend für eine Aktion oder Wartung ausblenden müssen, können Sie es hier deaktivieren.

#### **UVP auf Produktseite anzeigen**

- **Was diese Einstellung bewirkt:** Steuert, ob die UVP auf einzelnen Produktdetailseiten angezeigt wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Die UVP, Ihr Preis und die Information „Sie sparen“ werden auf der Produktseite angezeigt.
  - *Wenn deaktiviert (NEIN):* Die UVP wird auf der Produktseite nicht angezeigt, auch wenn sie global aktiviert ist.
- **Empfohlener Wert:** JA (Dies ist ein primärer Ort für Kunden, um den Wert zu sehen).
- **Händlerszenario / Beispiel:** Sie könnten dies deaktivieren, wenn Sie Einsparungen nur auf Kategorieseiten hervorheben möchten oder wenn Ihr Produktseiten-Design bereits sehr überladen ist.

#### **UVP in Produktliste anzeigen**

- **Was diese Einstellung bewirkt:** Steuert, ob die UVP auf Seiten angezeigt wird, die mehrere Produkte anzeigen, wie z. B. Kategorieseiten, Suchergebnisse oder hervorgehobene Produktblöcke.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Die UVP, Ihr Preis und die Information „Sie sparen“ werden für jedes Produkt in den Produktlisten angezeigt.
  - *Wenn deaktiviert (NEIN):* Die UVP wird auf Produktlistenseiten nicht angezeigt.
- **Empfohlener Wert:** JA (Ideal für schnelle Vergleiche und die Hervorhebung des Werts beim Stöbern).
- **Händlerszenario / Beispiel:** Die Aktivierung hilft Kunden, beim Durchsuchen von Kategorien schnell gute Angebote zu erkennen, was potenziell die Klickraten auf Produktseiten erhöht.

#### **Preis inkl. Steuern anzeigen**

- **Was diese Einstellung bewirkt:** Bestimmt, ob die angezeigte UVP Steuern enthalten oder als steuerfrei angezeigt werden soll.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Die UVP wird mit den anfallenden Steuern angezeigt, was den Endpreis widerspiegelt, den ein Kunde zahlen würde.
  - *Wenn deaktiviert (NEIN):* Die UVP wird ohne Steuern angezeigt.
- **Empfohlener Wert:** JA (Im Allgemeinen bevorzugen Kunden die Anzeige von Endpreisen, insbesondere im B2C-Kontext).
- **Händlerszenario / Beispiel:** Wenn Ihr Shop hauptsächlich B2C-Kunden bedient, ist die Anzeige von Preisen inklusive Steuern klarer. Für B2B-Shops könnte die Anzeige von Preisen exklusive Steuern bevorzugt werden.

#### **Preis exkl. Steuern anzeigen**

- **Was diese Einstellung bewirkt:** Bestimmt, ob die angezeigte UVP Steuern ausschließen oder als steuerpflichtig angezeigt werden soll.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Die UVP wird ohne Steuern angezeigt.
  - *Wenn deaktiviert (NEIN):* Die UVP wird mit den anfallenden Steuern angezeigt.
- **Empfohlener Wert:** NEIN (Es sei denn, Sie richten sich speziell an B2B-Kunden oder agieren in einer Region, in der steuerfreie Preise für die Erstansicht Standard sind).
- **Händlerszenario / Beispiel:** Wenn Sie „Preis inkl. Steuern anzeigen“ aktivieren, würden Sie diese Option typischerweise deaktivieren, um Verwirrung zu vermeiden. Aktivieren Sie beide nur, wenn Sie beide Werte nebeneinander anzeigen möchten (was für Kunden verwirrend sein könnte).

#### **Information „Sie sparen“ anzeigen**

- **Was diese Einstellung bewirkt:** Steuert, ob das Modul die monetäre Differenz zwischen der UVP und dem Verkaufspreis Ihres Shops berechnet und anzeigt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Modul zeigt eine Nachricht wie „Sie sparen X,XX €“ oder „Sie sparen X%“ neben der UVP und Ihrem Preis an.
  - *Wenn deaktiviert (NEIN):* Es werden nur die UVP und Ihr Preis angezeigt, ohne die explizite Ersparnisberechnung.
- **Empfohlener Wert:** JA (Dies ist ein Hauptvorteil der Nutzung des Moduls, der Käufe stark motiviert).
- **Händlerszenario / Beispiel:** Diese Funktion hebt das Wertversprechen direkt hervor. Wenn Ihre Preise durchweg niedriger als die UVP sind, wird die Aktivierung den wahrgenommenen Wert erheblich steigern.

#### **UVP-Feld für Produkte**

- **Was diese Einstellung bewirkt:** Diese Einstellung definiert, wo Sie die UVP für jedes Produkt in Ihrem PrestaShop Back Office eingeben.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ausgewählt:* Das Modul verwendet das gewählte Produktfeld, um den UVP-Wert abzurufen. Sie müssen die UVP für jedes Produkt manuell in das angegebene Feld eingeben.
- **Empfohlener Wert:** Das Modul erstellt normalerweise ein benutzerdefiniertes Feld oder schlägt die Verwendung eines vorhandenen vor. Befolgen Sie die Anweisungen des Moduls, um das richtige Feld zu identifizieren.
- **Händlerszenario / Beispiel:** Nach der Installation des Moduls gehen Sie zu **Katalog > Produkte**, bearbeiten ein Produkt und finden ein neues Eingabefeld (oder ein umfunktioniertes vorhandenes), in das Sie die UVP für dieses spezifische Produkt eingeben können.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | UVP-Anzeige aktivieren | JA | Hauptschalter zum Aktivieren/Deaktivieren der UVP-Funktion im gesamten Shop. |
| Modulkonfiguration | UVP auf Produktseite anzeigen | JA | UVP auf einzelnen Produktdetailseiten anzeigen. |
| Modulkonfiguration | UVP in Produktliste anzeigen | JA | UVP auf Kategorie-/Suchergebnisseiten anzeigen. |
| Modulkonfiguration | Preis inkl. Steuern anzeigen | JA | UVP mit Steuern anzeigen (B2C-freundlich). |
| Modulkonfiguration | Preis exkl. Steuern anzeigen | NEIN | UVP ohne Steuern anzeigen (B2B-freundlich, Konflikt mit „Preis inkl. Steuern“ vermeiden). |
| Modulkonfiguration | Information „Sie sparen“ anzeigen | JA | Die berechneten Einsparungen anzeigen (UVP - Ihr Preis). |
| Modulkonfiguration | UVP-Feld für Produkte | (Modulspezifisch) | Definiert, welches Produktfeld im BO den UVP-Wert speichert. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul aktiviert und UVPs eingegeben, aber nichts wird in meinem Shop angezeigt. Was ist falsch?**
A1:

-   **Globale Aktivierung prüfen:** Stellen Sie sicher, dass „UVP-Anzeige aktivieren“ in der Modulkonfiguration auf JA eingestellt ist.
-   **Spezifische Anzeigeeinstellungen prüfen:** Vergewissern Sie sich, dass „UVP auf Produktseite anzeigen“ und „UVP in Produktliste anzeigen“ ebenfalls auf JA eingestellt sind für die Bereiche, in denen Sie die Anzeige erwarten.
-   **Cache leeren:** PrestaShop verwendet Caching. Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
-   **Produktspezifische UVP:** Überprüfen Sie nochmals, ob Sie tatsächlich einen UVP-Wert für die spezifischen Produkte eingegeben haben, die Sie testen.
-   **Theme-Kompatibilität:** Manchmal erfordern stark angepasste Themes geringfügige Anpassungen, um neue Elemente anzuzeigen. Wenn es nach dem Leeren des Caches immer noch nicht erscheint, kontaktieren Sie den MyPresta.eu-Support.

**F2: Der Betrag „Sie sparen“ scheint falsch zu sein oder wird nicht angezeigt.**
A2:

-   **„Sie sparen“ aktivieren:** Stellen Sie sicher, dass „Information „Sie sparen“ anzeigen“ in den Moduleinstellungen aktiviert ist.
-   **UVP vs. Ihr Preis:** Die Berechnung von „Sie sparen“ hängt sowohl von der UVP als auch vom Verkaufspreis Ihres Produkts ab. Stellen Sie sicher, dass beide Werte für das Produkt korrekt eingestellt sind. Wenn Ihr Verkaufspreis höher oder gleich der UVP ist, werden keine Einsparungen angezeigt.
-   **Steuereinstellungen:** Die Berechnung kann davon beeinflusst werden, ob Sie Preise inklusive oder exklusive Steuern anzeigen. Stellen Sie sicher, dass Ihre Steuereinstellungen konsistent sind.

**F3: Wie gebe ich die UVP für jedes Produkt ein?**
A3: Nach der Installation des Moduls navigieren Sie im PrestaShop Back Office zu **Katalog > Produkte**. Bearbeiten Sie ein bestehendes Produkt oder erstellen Sie ein neues. Innerhalb der Produktbearbeitungsoberfläche sollten Sie ein neues Feld speziell für „UVP“ (oder ein umfunktioniertes bestehendes Feld, wie in der Modulkonfiguration definiert) finden. Geben Sie dort die unverbindliche Preisempfehlung des Herstellers ein und speichern Sie das Produkt.

**F4: Der UVP-Text passt nicht zum Design/Schriftart meines Shops. Wie kann ich das ändern?**
A4: Das Modul verwendet sein eigenes CSS für die Gestaltung. Für kleinere Anpassungen (wie Schriftgröße, Farbe) können Sie diese Stile oft in der benutzerdefinierten CSS-Datei Ihres Themes überschreiben (z. B. `themes/yourtheme/assets/css/custom.css` oder `themes/yourtheme/css/custom.css`). Für umfangreichere Änderungen benötigen Sie möglicherweise einen Webentwickler, um das CSS des Moduls zu überprüfen und spezifischere Überschreibungen anzuwenden.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Unverbindliche Preisempfehlung (UVP) des Herstellers“ ist ein Standard-PrestaShop-Modul, das zur Erweiterung der Front-Office-Produktanzeigefunktionen entwickelt wurde. Es arbeitet hauptsächlich, indem es sich in bestehende PrestaShop-Anzeigepunkte (wie Produktseiten und Produktlisten) einklinkt, um UVP-Informationen einzufügen. Es nutzt das PrestaShop-Konfigurationssystem für seine Einstellungen und Smarty-Templates für die Darstellung der Front-Office-Ausgabe. Die Kernlogik des Moduls befindet sich in seiner Haupt-PHP-Datei, die Installation, Deinstallation, Konfiguration und Hook-Registrierung verwaltet.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird über die Methode `getContent()` in der Hauptmoduldatei gehandhabt, und die Front-Office-Anzeige wird über Hooks und Template-Rendering verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen im Verzeichnis `classes/`. Es interagiert direkt mit vorhandenen PrestaShop-Produktdaten und -Konfigurationen.

### 4.4 JavaScript-Assets (`views/js/`)

-   **`msrp/views/admin/js/msrp.js`**

    -   **Geltungsbereich:** Back-Office.
    -   **Zweck:** Dieses Skript verarbeitet wahrscheinlich dynamisches Verhalten oder Validierungen innerhalb des Konfigurationsformulars des Moduls im PrestaShop Back Office. Dies könnte das Anzeigen/Ausblenden von Feldern basierend auf anderen Auswahlen, AJAX-Aufrufe zum Speichern von Einstellungen oder clientseitige Validierung umfassen.
    -   **Details:** Bindet Event-Listener an Konfigurationsformular-Elemente, führt die Formularübermittlungsbehandlung durch und aktualisiert möglicherweise die Benutzeroberfläche basierend auf Benutzereingaben.
-   **`msrp/views/js/msrp.js`**

    -   **Geltungsbereich:** Front-Office.
    -   **Zweck:** Dieses Skript ist für alle clientseitigen Interaktionen oder dynamischen Aktualisierungen im Zusammenhang mit der UVP-Anzeige im Front Office verantwortlich. Dies könnte das dynamische Aktualisieren des Betrags „Sie sparen“ umfassen, wenn sich Produktattribute ändern (z. B. Auswahl einer anderen Größe/Farbe, die den Preis beeinflusst), oder die Handhabung der Anzeigelogik.
    -   **Details:** Bindet an `prestashop.on`-Ereignisse (z. B. `updatedProduct` für Preisänderungen auf der Produktseite), manipuliert DOM-Elemente, um die UVP- oder Einsparungsanzeige zu aktualisieren, und gewährleistet Responsivität.

### 4.5 CSS-Stylesheets (`views/css/`)

-   **`msrp/views/admin/css/msrp.css`**

    -   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    -   **Zweck:** Bietet spezifisches Styling für die Konfigurationsseite des Moduls im PrestaShop Back Office, um eine konsistente und benutzerfreundliche Oberfläche zu gewährleisten.
    -   **Schlüsselselektoren:** Zielt auf Elemente innerhalb der `getContent()`-Ausgabe des Moduls ab, wie Formularfelder, Beschriftungen und Abschnitte.
-   **`msrp/views/css/msrp.css`**

    -   **Geltungsbereich:** Front-Office-Kunden-Styling.
    -   **Zweck:** Gestaltet die angezeigte UVP, Ihren Preis und die Information „Sie sparen“ auf Produktseiten und in Produktlisten. Dies stellt sicher, dass die Informationen klar sichtbar sind und sich gut in das Gesamtdesign des Shops integrieren.
    -   **Schlüsselselektoren:** Zielt auf spezifische `div`- oder `span`-Elemente ab, die von den Smarty-Templates des Moduls generiert werden (z. B. `.msrp-price`, `.msrp-you-save`, `.msrp-old-price`). Entwickler können diese Klassen in der `custom.css` ihres Themes überschreiben, um sie an ihr Branding anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **`msrp/views/admin/msrp.tpl`**

    -   **Geltungsbereich:** Admin-Templates.
    -   **Zweck:** Dieses Template rendert das Konfigurationsformular des Moduls im PrestaShop Back Office. Es enthält die HTML-Struktur für alle in Abschnitt 4.1 beschriebenen Einstellungen.
    -   **Details:** Verwendet die Helper-Formular-Komponenten von PrestaShop (z. B. `helperForm`), um Eingabefelder, Schalter und Schaltflächen für Moduleinstellungen zu erstellen.
-   **`msrp/views/templates/msrp-product-list.tpl`**

    -   **Geltungsbereich:** Hook-Templates (z. B. `displayProductPriceBlock` oder ähnliches für Produktlisten).
    -   **Zweck:** Dieses Template ist für die Anzeige der UVP-Informationen auf Produktlistenseiten (Kategorien, Suchergebnisse usw.) verantwortlich. Es empfängt typischerweise Produktdaten und Modulkonfigurationseinstellungen, um die UVP, den aktuellen Preis und die Nachricht „Sie sparen“ zu rendern.
    -   **Details:** Enthält Logik zur Überprüfung, ob die UVP verfügbar ist, ob „Sie sparen“ angezeigt werden soll, und formatiert die Preise gemäß den Steuereinstellungen.
-   **`msrp/views/templates/msrp-product-page.tpl`**

    -   **Geltungsbereich:** Hook-Templates (z. B. `displayProductPriceBlock` oder `displayProductButtons` auf Produktseiten).
    -   **Zweck:** Dieses Template rendert die UVP-Informationen auf einzelnen Produktdetailseiten. Es ist so konzipiert, dass es sich nahtlos in den Hauptproduktpreisblock integriert.
    -   **Details:** Ähnlich wie `msrp-product-list.tpl` behandelt es die bedingte Anzeige von UVP, aktuellem Preis und Einsparungen, wobei Steuerregeln und Formatierung angewendet werden.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    -   Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
    -   Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert, typischerweise mit Schlüsseln, die mit `MSRP_` beginnen (z. B. `MSRP_ENABLE`, `MSRP_DISPLAY_PRODUCT_PAGE`).
    -   UVP-Werte für Produkte werden in einem vorhandenen Produktfeld gespeichert, wie im Modul konfiguriert (z. B. `ps_product_lang.description_short` oder ein benutzerdefiniertes Produktfeld, falls vom Modul erstellt).
-   **Registrierte Hooks-Tabelle**:
    Das Modul registriert Hooks, um seinen Inhalt in das Front Office einzufügen und seinen Lebenszyklus zu verwalten.

    | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
    | --- | --- | --- |
    | `install()` | Während der Modulinstallation | Erstellt Konfigurationseinträge, registriert Hooks, fügt möglicherweise Produktfelder hinzu. |
    | `uninstall()` | Während der Moduldeinstallation | Bereinigt Konfigurationseinträge, deregistriert Hooks, entfernt Produktfelder. |
    | `displayHeader` | Im `<head>`-Bereich jeder Seite | Fügt die CSS- und JS-Dateien des Moduls für die Front-Office-Anzeige ein. |
    | `displayProductPriceBlock` | Innerhalb des Produktpreisblocks auf Produktseiten und in Listen | Haupt-Hook zum Rendern von UVP, aktuellem Preis und „Sie sparen“-Informationen. Dieser Hook wird mehrmals mit verschiedenen Parametern aufgerufen (z. B. `type='after_price'`). |
    | `actionProductUpdate` | Nach der Aktualisierung eines Produkts im Back Office | Wird möglicherweise verwendet, um sicherzustellen, dass UVP-Daten korrekt gespeichert oder verarbeitet werden. |
    | `actionProductSave` | Nach dem Speichern eines Produkts im Back Office | Ähnlich wie `actionProductUpdate`, gewährleistet die Integrität der UVP-Daten. |
    | `actionProductDelete` | Nach dem Löschen eines Produkts | Bereinigt alle zugehörigen UVP-Daten, falls separat gespeichert. |
    | `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office | Fügt das UVP-Eingabefeld zum Produktformular hinzu. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul „Unverbindliche Preisempfehlung (UVP) des Herstellers“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team und unsere Entwickler stehen Ihnen zur Verfügung, um Ihnen zu helfen, das Potenzial dieses Moduls für Ihren PrestaShop-Shop zu maximieren.

---
title: "Compari.ro - Umfrage-E-Mails für vertrauenswürdiges Kaufprogramm - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Compari.ro - Umfrage-E-Mails für vertrauenswürdiges Kaufprogramm“ von MyPresta.eu."
sidebar:
  label: "Compari.ro - Umfrage-E-Mails für vertrauenswürdiges Kaufprogramm - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Compari.ro - trusted purchase program survey emails auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/compariro-trusted-purchase-program-survey-emails.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/compariro-trusted-purchase-program-survey-emails/)
>
> ---


# Compari.ro - Umfrage-E-Mails für vertrauenswürdiges Kaufprogramm

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Compari.ro-Modul. Sie können darauf zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, nach „Compari.ro“ suchen und auf die Schaltfläche „Konfigurieren“ klicken.

#### **1. Compari.ro WebApiKey**

- **Was diese Einstellung bewirkt:** Dies ist Ihre eindeutige Kennung, die von Compari.ro bereitgestellt wird und Ihren PrestaShop-Shop mit Ihrem Compari.ro-Händlerkonto verknüpft. Sie ist unerlässlich, damit das „Trusted Purchase Program“ Umfrageanfragen Ihrem Shop korrekt zuordnen kann.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Bei korrekter Eingabe:* Das Modul kann Bestelldaten an Compari.ro senden, sodass diese Umfrage-E-Mails an Ihre Kunden senden können.
  - *Bei falscher oder leerer Eingabe:* Die Integration schlägt fehl, und Compari.ro erhält keine Bestellinformationen, was bedeutet, dass keine Umfrage-E-Mails gesendet werden.
- **Empfohlener Wert:** Geben Sie den genauen WebApiKey ein, den Sie von Compari.ro erhalten haben.
- **Händlerszenario / Beispiel:** Sie haben sich für das „Trusted Purchase Program“ von Compari.ro registriert und eine E-Mail mit Ihrem API-Schlüssel erhalten. Sie müssen diesen Schlüssel hier kopieren und einfügen, damit die Integration funktioniert.

#### **2. Produktidentifikator (Feed ITEM\_ID)**

- **Was diese Einstellung bewirkt:** Diese Einstellung definiert, welcher Produktidentifikator aus Ihrem PrestaShop-Shop als `ITEM_ID` verwendet werden soll, wenn Produktinformationen an Compari.ro gesendet werden. Dies ist entscheidend, um Produkte in Ihrem Compari.ro-Feed mit den Produkten in Ihren Bestellungen abzugleichen.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf `id_product` (Standard) eingestellt:* Die interne PrestaShop-Produkt-ID wird verwendet. Dies ist im Allgemeinen die sicherste Option, wenn Sie keinen spezifischen benutzerdefinierten Identifikator haben.
  - *Wenn auf `reference` eingestellt:* Der Referenzcode des Produkts wird verwendet. Wählen Sie dies, wenn Ihr Compari.ro-Produktfeed die Produktreferenz als `ITEM_ID` verwendet.
  - *Wenn auf `ean13` eingestellt:* Der EAN-13-Barcode des Produkts wird verwendet. Wählen Sie dies, wenn Ihr Compari.ro-Produktfeed EAN-13 als `ITEM_ID` verwendet.
  - *Wenn auf `upc` eingestellt:* Der UPC-Code des Produkts wird verwendet. Wählen Sie dies, wenn Ihr Compari.ro-Produktfeed UPC als `ITEM_ID` verwendet.
- **Empfohlener Wert:** `id_product` (es sei denn, Ihr Compari.ro-Produktfeed verwendet explizit `reference`, `ean13` oder `upc` als `ITEM_ID`).
- **Händlerszenario / Beispiel:** Ihr Compari.ro-Produktfeed verwendet den eindeutigen EAN-13-Barcode für jedes Produkt. Sie würden hier `ean13` auswählen, um sicherzustellen, dass Compari.ro die von Ihren Kunden gekauften Produkte korrekt identifizieren kann.

#### **3. Kundenzustimmung erforderlich**

- **Was diese Einstellung bewirkt:** Diese Option bestimmt, ob Ihre Kunden während des Bestellvorgangs explizit zustimmen müssen, am Compari.ro-Umfrageprogramm teilzunehmen. Dies ist wichtig für die DSGVO-Konformität und die Achtung der Datenschutzpräferenzen der Kunden.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (auf „Ja“ gesetzt):* Während des Bestellvorgangs (z. B. auf der Zahlungsseite oder in der Bestellübersicht) wird ein Kontrollkästchen angezeigt. Kunden müssen dieses Kästchen ankreuzen, um die Übermittlung ihrer Bestelldaten an Compari.ro für Umfragezwecke zu gestatten. Wenn sie nicht zustimmen, wird für ihre Bestellung keine Umfrage-E-Mail gesendet.
  - *Wenn deaktiviert (auf „Nein“ gesetzt):* Es wird kein Zustimmungs-Kontrollkästchen angezeigt. Bestelldaten werden für alle Bestellungen an Compari.ro gesendet, vorausgesetzt, der `WebApiKey` ist korrekt.
- **Empfohlener Wert:** „Ja“, wenn Sie in Regionen mit strengen Datenschutzgesetzen (wie der DSGVO) tätig sind oder wenn Sie Kunden die volle Kontrolle über ihre Datenfreigabe geben möchten. „Nein“, wenn Sie festgestellt haben, dass eine explizite Zustimmung für Ihren spezifischen rechtlichen Kontext nicht erforderlich ist oder wenn Sie die Umfrageteilnahme maximieren möchten.
- **Händlerszenario / Beispiel:** Um die DSGVO-Bestimmungen einzuhalten, aktivieren Sie diese Einstellung. Während des Bestellvorgangs sehen Kunden ein Kontrollkästchen „Ich stimme der Teilnahme an der Compari.ro Trusted Purchase Program Umfrage zu.“ Nur Kunden, die dieses Kästchen ankreuzen, erhalten eine Umfrage-E-Mail.

#### **4. Fehler in log.txt schreiben**

- **Was diese Einstellung bewirkt:** Dies ist eine Debugging-Option, die steuert, ob das Modul während seines Betriebs auftretende Fehler (z. B. Probleme beim Senden von Daten an Compari.ro) in eine `log.txt`-Datei im Modulverzeichnis aufzeichnet.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (auf „Ja“ gesetzt):* Alle technischen Fehler werden in `compari/log.txt` geschrieben. Diese Datei kann für Ihren Webmaster oder den MyPresta.eu-Support sehr hilfreich sein, um Probleme zu diagnostizieren.
  - *Wenn deaktiviert (auf „Nein“ gesetzt):* Fehler werden nicht explizit in eine Datei protokolliert. Dies wird im Allgemeinen für Live-Produktionsshops bevorzugt, um die Generierung großer Protokolldateien zu vermeiden, es sei denn, Sie beheben aktiv Probleme.
- **Empfohlener Wert:** „Nein“ für einen Live-Produktionsshop. „Ja“, wenn Sie Probleme mit der Integration haben und debuggen müssen. Denken Sie daran, es zu deaktivieren, sobald das Problem behoben ist.
- **Händlerszenario / Beispiel:** Sie haben das Modul konfiguriert, aber Kunden erhalten keine Umfrage-E-Mails. Sie aktivieren „Fehler in log.txt schreiben“ und geben dann eine Testbestellung auf. Anschließend überprüfen Sie die `log.txt`-Datei auf Hinweise, warum die Integration möglicherweise fehlschlägt.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Compari.ro WebApiKey | Ihr eindeutiger API-Schlüssel | Verknüpft Ihren Shop mit Compari.ro für die Umfrageautomatisierung. **Entscheidend für die Funktionalität.** |
| Modulkonfiguration | Produktidentifikator (Feed ITEM\_ID) | `id_product` (oder passend zu Ihrem Feed) | Gibt an, welche Produkt-ID (intern, Referenz, EAN, UPC) an Compari.ro gesendet werden soll. |
| Modulkonfiguration | Kundenzustimmung erforderlich | Ja (für DSGVO) | Zeigt ein Zustimmungs-Kontrollkästchen während des Checkouts an. Wenn nicht angekreuzt, wird keine Umfrage-E-Mail gesendet. |
| Modulkonfiguration | Fehler in log.txt schreiben | Nein (für Debugging aktivieren) | Protokolliert technische Fehler in `compari/log.txt` zur Fehlerbehebung. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden erhalten keine Umfrage-E-Mails von Compari.ro, obwohl das Modul konfiguriert ist.**
A1:

- **WebApiKey überprüfen:** Überprüfen Sie nochmals, ob Ihr „Compari.ro WebApiKey“ korrekt und exakt so eingegeben wurde, wie er von Compari.ro bereitgestellt wurde. Schon ein einziger Tippfehler verhindert die Funktion der Integration.
- **Zustimmungseinstellung überprüfen:** Wenn „Kundenzustimmung erforderlich“ auf „Ja“ gesetzt ist, stellen Sie sicher, dass Ihre Testkunden das Zustimmungsfeld während des Checkouts tatsächlich ankreuzen.
- **Compari.ro-Konto überprüfen:** Melden Sie sich in Ihrem Compari.ro-Händlerkonto an, um zu sehen, ob Fehlermeldungen vorliegen oder ob Bestellungen von Ihrem Shop empfangen werden.
- **Protokollierung aktivieren:** Setzen Sie „Fehler in log.txt schreiben“ in der Modulkonfiguration auf „Ja“, geben Sie eine Testbestellung auf und überprüfen Sie dann die Datei `compari/log.txt` auf Fehlermeldungen. Dies liefert spezifische technische Details.
- **Cache leeren:** Manchmal kann der PrestaShop-Cache stören. Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie auf „Cache leeren“.

**F2: Ich habe „Kundenzustimmung erforderlich“ aktiviert, sehe aber kein Kontrollkästchen während des Checkouts.**
A2:

- **Theme-Kompatibilität:** Das Modul verwendet Standard-PrestaShop-Hooks (`displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`), um das Zustimmungs-Kontrollkästchen anzuzeigen. Wenn Ihr benutzerdefiniertes Theme den Checkout-Prozess stark modifiziert, werden diese Hooks möglicherweise nicht gerendert, oder die Formatierung könnte das Kontrollkästchen unsichtbar machen.
- **Cache:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Performance**).
- **Modulposition:** Stellen Sie sicher, dass das Modul für die spezifischen Hooks, die es verwendet, nicht deaktiviert ist. Obwohl dies für ein Zustimmungs-Kontrollkästchen seltener ist, lohnt es sich, dies unter **Design > Positionen** zu überprüfen.

**F3: Was passiert, wenn ein Kunde seine Meinung bezüglich der Zustimmung nach der Bestellung ändert?**
A3: Das Modul verarbeitet die Zustimmung zum Zeitpunkt der Bestellung. Wenn ein Kunde die Zustimmung für zukünftige Umfragen widerrufen möchte, müsste er dies normalerweise direkt bei Compari.ro oder über die allgemeinen DSGVO-Datenverwaltungstools Ihres Shops (falls vorhanden) verwalten. Das Modul selbst bietet keine direkte „Rückgängig“-Funktion für vergangene Bestellungen, integriert sich aber in die DSGVO-Hooks von PrestaShop für Datenlöschung und -export.

**F4: Ich sehe, dass eine `log.txt`-Datei sehr groß wird. Was soll ich tun?**
A4: Wenn Sie nicht aktiv Fehler beheben, setzen Sie die Option „Fehler in log.txt schreiben“ in der Modulkonfiguration auf „Nein“. Dies verhindert, dass das Modul weitere Einträge in die Protokolldatei schreibt. Sie können die `log.txt`-Datei dann sicher löschen, um Speicherplatz freizugeben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das `Compari`-Modul ist ein unkompliziertes PrestaShop-Modul, das sich hauptsächlich auf die Integration mit einer externen API (Compari.ro) basierend auf Bestellereignissen konzentriert. Es folgt einer Standard-PrestaShop-Modulstruktur und nutzt Hooks, um Inhalte (DSGVO-Zustimmung) einzufügen und Aktionen (Senden von Bestelldaten) auszulösen. Es führt keine benutzerdefinierten Controller oder komplexen ObjectModels ein, sondern verlässt sich auf die Kerndaten `Order` und `Customer` von PrestaShop. Die Hauptlogik befindet sich in der Datei `compari.php` und behandelt Konfiguration, Installation und Hook-Rückrufe.

### 4.2 Controller (`controllers/`)

- Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Logik wird innerhalb der Hauptdatei `compari.php` über Hooks verarbeitet.

### 4.3 Kernklassen & Modelle (`classes/`)

- Dieses Modul enthält **keine** benutzerdefinierten Klassen oder ObjectModels im Verzeichnis `classes/`. Die gesamte Datenverarbeitung erfolgt direkt in der Datei `compari.php` unter Verwendung der PrestaShop-Kernentitäten `Order`, `Customer` und `Product`.

### 4.4 JavaScript-Assets (`views/js/`)

- Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

- Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Die Formatierung für das Zustimmungs-Kontrollkästchen wird voraussichtlich vom Theme geerbt oder durch die Formatierung des PrestaShop-Kern-DSGVO-Moduls gehandhabt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `compari/views/templates/hook/consent.tpl`:
    - **Hook:** `displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`
    - **Zweck:** Rendert das DSGVO-Zustimmungs-Kontrollkästchen und den zugehörigen Text, sodass Kunden dem Compari.ro-Umfrageprogramm zustimmen oder es ablehnen können. Dieses Template wird nur gerendert, wenn die Konfiguration `COMPARI_CONSENT` aktiviert ist.
    - **Ausgabe:** Ein Kontrollkästchen-Eingabefeld mit einer Beschriftung.
  - `compari/views/templates/hook/displayOrderConfirmation.tpl`:
    - **Hook:** `displayOrderConfirmation`
    - **Zweck:** Dieses Template ist im Hook `displayOrderConfirmation` enthalten. Obwohl es eine Template-Datei ist, besteht seine primäre Rolle hier darin, die Backend-Logik innerhalb von `hookDisplayOrderConfirmation` in `compari.php` auszulösen, um Bestelldaten an Compari.ro zu senden. Es gibt keine sichtbaren Inhalte für den Benutzer aus.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt **keine** benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der Tabelle `ps_configuration`:
    - `COMPARI_FILE_LOG`: Speichert den booleschen Wert für die Fehlerprotokollierung.
    - `COMPARI_ID`: Speichert den Compari.ro WebApiKey.
    - `COMPARI_PRODUCT_ID`: Speichert den ausgewählten Produktidentifikatortyp (z. B. `id_product`, `reference`).
    - `COMPARI_CONSENT`: Speichert den booleschen Wert für die Anforderung der Kundenzustimmung.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `install()` | Während der Modulinstallation | Setzt Standardkonfigurationswerte, registriert Hooks. |
| `uninstall()` | Während der Moduldeinstallation | Löscht Konfigurationswerte, deregistriert Hooks. |
| `hookDisplayGDPRConsent` | Wird auf Seiten gerendert, auf denen die DSGVO-Zustimmung eingeholt wird (z. B. Checkout) | Zeigt das Zustimmungs-Kontrollkästchen für die Teilnahme an der Compari.ro-Umfrage an. |
| `hookActionDeleteGDPRCustomer` | Wenn ein Kunde die Löschung von DSGVO-Daten anfordert | Behandelt die Löschung aller Compari.ro-bezogenen Kundendaten (obwohl keine direkt vom Modul gespeichert werden, ist es ein Compliance-Hook). |
| `hookActionExportGDPRData` | Wenn ein Kunde den Export von DSGVO-Daten anfordert | Behandelt den Export aller Compari.ro-bezogenen Kundendaten (keine direkt gespeichert). |
| `hookDisplayOrderConfirmation` | Auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf | Löst das Senden von Bestelldaten an Compari.ro aus, wenn die Zustimmung erteilt wurde (oder nicht erforderlich ist). |
| `hookDisplayPaymentTop` | Oberhalb des Zahlungsschritts im Checkout | Alternativer Hook zum Anzeigen des Zustimmungs-Kontrollkästchens. |
| `hookDisplayCheckoutSummaryTop` | Oberhalb des Checkout-Zusammenfassungsschritts | Alternativer Hook zum Anzeigen des Zustimmungs-Kontrollkästchens. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Compari.ro - Umfrage-E-Mails für vertrauenswürdiges Kaufprogramm“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen gerne zur Verfügung.

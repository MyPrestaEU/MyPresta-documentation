---
title: "Arukereso.hu – Vertrauenswürdiges Kaufprogramm Umfrage-E-Mails – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Arukereso.hu – Vertrauenswürdiges Kaufprogramm Umfrage-E-Mails von MyPresta.eu."
sidebar:
  label: "Arukereso.hu – Vertrauenswürdiges Kaufprogramm Umfrage-E-Mails – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Arukereso.hu - trusted purchase program survey emails auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/arukeresohu-trusted-purchase-program-survey-emails.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/arukeresohu-trusted-purchase-program-survey-emails/)
>
> ---


# Arukereso.hu – Vertrauenswürdiges Kaufprogramm Umfrage-E-Mails

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Arukereso.hu-Modul. Sie können darauf zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, nach „Arukereso.hu“ suchen und auf „Konfigurieren“ klicken.

#### 2.1.1 Arukereso.hu WebApiKey

- **Was diese Einstellung bewirkt:** Dies ist Ihre eindeutige Kennung, die von Arukereso.hu bereitgestellt wird. Sie ist unerlässlich, damit Arukereso.hu die Umfrageanfragen, die von Ihrem PrestaShop-Shop kommen, mit Ihrem spezifischen Händlerkonto auf deren Plattform verknüpfen kann.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Bei korrekter Eingabe:* Das Modul kann erfolgreich mit den Systemen von Arukereso.hu kommunizieren, wodurch der automatisierte Umfrage-E-Mail-Prozess ermöglicht wird.
  - *Bei falscher oder leerer Eingabe:* Arukereso.hu kann Ihren Shop nicht identifizieren, und die Umfrage-E-Mails werden nicht an Ihre Kunden gesendet. Die Integration schlägt fehl.
- **Empfohlener Wert:** Geben Sie den genauen API-Schlüssel ein, den Sie von Arukereso.hu erhalten haben. Dieser befindet sich normalerweise in den Einstellungen Ihres Händlerkontos auf der Arukereso.hu-Website.
- **Händlerszenario / Beispiel:** Sie registrieren sich für das „Vertrauenswürdige Kaufprogramm“ auf Arukereso.hu. Sie erhalten eine Zeichenfolge wie `abcdef1234567890`. Sie kopieren diese und fügen sie in dieses Feld ein.

#### 2.1.2 Produkt-Identifikator (Feed ITEM\_ID)

- **Was diese Einstellung bewirkt:** Diese Einstellung bestimmt, welcher Produkt-Identifikator aus Ihrem PrestaShop-Shop an Arukereso.hu gesendet wird. Arukereso.hu verwendet diese ID, um das gekaufte Produkt mit seinem Eintrag auf ihrer Plattform abzugleichen und so sicherzustellen, dass die Umfrage relevant ist.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn auf „Produkt-ID“ eingestellt:* Die interne PrestaShop-Produkt-ID (z. B. `123`) wird verwendet. Dies ist die häufigste und normalerweise sicherste Option.
  - *Wenn auf „Produktreferenz“ eingestellt:* Der Referenzcode Ihres Produkts (z. B. `SKU-001`) wird verwendet. Dies erfordert, dass Ihre Produktreferenzen eindeutig und konsistent mit den Erwartungen von Arukereso.hu sind.
  - *Wenn auf „Produkt EAN13“ eingestellt:* Der EAN-13-Barcode des Produkts wird verwendet. Dies ist geeignet, wenn Ihre EANs konsistent verwendet werden und mit dem Produktkatalog von Arukereso.hu übereinstimmen.
  - *Wenn auf „Produkt UPC“ eingestellt:* Der UPC-Code des Produkts wird verwendet. Ähnlich wie bei EAN13 erfordert dies konsistente Daten.
- **Empfohlener Wert:** „Produkt-ID“ ist im Allgemeinen die sicherste und zuverlässigste Option, es sei denn, Sie haben einen spezifischen Grund (und mit Arukereso.hu verifiziert), einen anderen Identifikator zu verwenden.
- **Händlerszenario / Beispiel:** Wenn Sie ein Produkt „Rotes T-Shirt“ mit der internen ID `15`, der Referenz `TSHIRT-RED` und der EAN `1234567890123` haben, wird bei Auswahl von „Produkt-ID“ `15` an Arukereso.hu gesendet. Wenn Sie „Produktreferenz“ wählen, wird `TSHIRT-RED` gesendet. Stellen Sie sicher, dass der gewählte Identifikator dem entspricht, was Arukereso.hu erwartet, um Produkte korrekt zu verknüpfen.

#### 2.1.3 Kundenzustimmung erforderlich

- **Was diese Einstellung bewirkt:** Diese entscheidende Einstellung steuert, ob Ihre Kunden während des Checkouts ausdrücklich zustimmen müssen, am Arukereso.hu-Umfrageprogramm teilzunehmen. Dies ist entscheidend für die Einhaltung von Datenschutzbestimmungen wie der DSGVO.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert („Ja“):* Ein Kontrollkästchen oder ein ähnlicher Zustimmungsmechanismus wird während des Checkout-Prozesses angezeigt. Nur Kunden, die dieses Kästchen ankreuzen, erhalten ihre Bestelldaten zur Umfragezwecken an Arukereso.hu gesendet. Dies gewährleistet die Einhaltung der DSGVO.
  - *Wenn deaktiviert („Nein“):* Es wird keine Zustimmungsoption angezeigt. Alle Kunden, die eine Bestellung abschließen, werden automatisch in das Arukereso.hu-Umfrageprogramm aufgenommen. **Mit Vorsicht verwenden und nur, wenn Sie sicher sind, dass Ihre lokalen Vorschriften keine ausdrückliche Zustimmung für diese Art der Datenweitergabe erfordern.**
- **Empfohlener Wert:** „Ja“. Es wird dringend empfohlen, diese Option zu aktivieren, um die Einhaltung der DSGVO und anderer Datenschutzgesetze zu gewährleisten und den Kunden die Kontrolle über ihre Daten zu geben.
- **Händlerszenario / Beispiel:** Sie sind in der EU tätig. Um die DSGVO einzuhalten, aktivieren Sie diese Einstellung. Während des Checkouts sehen Kunden ein Kontrollkästchen: „Ja, ich stimme zu, eine Kundenzufriedenheitsumfrage von Arukereso.hu bezüglich meines Kaufs zu erhalten.“ Nur wenn sie dieses Kästchen ankreuzen, werden ihre Daten weitergegeben.

#### 2.1.4 Fehler in log.txt schreiben

- **Was diese Einstellung bewirkt:** Diese Einstellung steuert, ob das Modul Fehler oder Probleme, die während des Betriebs auftreten, in eine `log.txt`-Datei im Modulverzeichnis aufzeichnet.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert („Ja“):* Alle Probleme (z. B. fehlgeschlagene Verbindung zu Arukereso.hu, Probleme mit ungültigem API-Schlüssel) werden in `arukereso/log.txt` geschrieben. Dies ist äußerst hilfreich bei der Fehlerbehebung.
  - *Wenn deaktiviert („Nein“):* Fehler werden nicht in eine Datei protokolliert. Obwohl dies die Festplattenaktivität geringfügig reduziert, erschwert es die Diagnose von Problemen erheblich.
- **Empfohlener Wert:** „Ja“ während der Ersteinrichtung und wenn Sie Probleme haben. Sobald das Modul reibungslos läuft, können Sie es deaktivieren, wenn Sie möchten, aber es ist oft am besten, es für die laufende Überwachung aktiviert zu lassen.
- **Händlerszenario / Beispiel:** Sie haben das Modul konfiguriert, aber Kunden erhalten keine Umfragen. Sie aktivieren diese Einstellung, und nach einigen Testbestellungen überprüfen Sie `arukereso/log.txt` und finden eine Fehlermeldung, die „Ungültiger API-Schlüssel“ anzeigt. Dies zeigt Ihnen sofort, wo Sie nach dem Problem suchen müssen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Arukereso.hu WebApiKey | Ihr Arukereso.hu Schlüssel | Eindeutige Kennung für Ihren Shop auf Arukereso.hu. **Für die Integration erforderlich.** |
| Modulkonfiguration | Produkt-Identifikator (Feed ITEM\_ID) | Produkt-ID | Definiert, welche Produkt-ID (PrestaShop ID, Referenz, EAN, UPC) an Arukereso.hu gesendet wird. |
| Modulkonfiguration | Kundenzustimmung erforderlich | Ja | Zeigt ein Zustimmungs-Kontrollkästchen während des Checkouts an. **Sehr empfohlen für die DSGVO-Konformität.** |
| Modulkonfiguration | Fehler in log.txt schreiben | Ja | Protokolliert Modulfehler in `arukereso/log.txt` zur Fehlerbehebung. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kunden erhalten keine Umfrage-E-Mails von Arukereso.hu. Was sollte ich überprüfen?**
A:

1.  **Arukereso.hu WebApiKey:** Überprüfen Sie nochmals, ob Ihr API-Schlüssel in der Modulkonfiguration korrekt eingegeben ist. Schon ein einziger Tippfehler verhindert die Funktion der Integration.
2.  **Zustimmungseinstellung:** Wenn „Kundenzustimmung erforderlich“ aktiviert ist, stellen Sie sicher, dass Kunden das Zustimmungsfeld während des Checkouts tatsächlich ankreuzen. Wenn nicht, werden keine Daten gesendet.
3.  **Log-Datei:** Aktivieren Sie „Fehler in log.txt schreiben“ in der Modulkonfiguration und überprüfen Sie die Datei `arukereso/log.txt` nach einer Testbestellung auf Fehlermeldungen. Dies ist der direkteste Weg zur Diagnose von Problemen.
4.  **Arukereso.hu-Konto:** Melden Sie sich in Ihrem Arukereso.hu-Händlerkonto an und überprüfen Sie den Status Ihrer „Vertrauenswürdiges Kaufprogramm“-Integration. Dort könnten spezifische Protokolle oder Statusanzeigen vorhanden sein.
5.  **Bestellstatus:** Stellen Sie sicher, dass der Bestellstatus, der die Umfrage auslöst (normalerweise „Zahlung akzeptiert“ oder „Geliefert“), auf Arukereso.hu korrekt konfiguriert ist und Ihre PrestaShop-Bestellungen diesen Status erreichen.

**F: Ich habe „Kundenzustimmung erforderlich“ aktiviert, aber ich sehe das Kontrollkästchen während des Checkouts nicht.**
A:

1.  **Theme-Kompatibilität:** Das Modul verwendet Standard-PrestaShop-Hooks (`displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`). Wenn Ihr Theme stark angepasst ist, rendert es diese Hooks möglicherweise nicht korrekt.
2.  **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung > Cache leeren).
3.  **Modulposition:** Gehen Sie zu Design > Positionen und suchen Sie nach den oben genannten Hooks. Stellen Sie sicher, dass das Arukereso.hu-Modul in diesen Hooks aufgeführt und aktiv ist. Falls nicht, versuchen Sie, es zu transplantieren.
4.  **Modulkonflikte:** Deaktivieren Sie vorübergehend andere Module, die den Checkout-Prozess ändern, um Konflikte auszuschließen.

**F: Was passiert, wenn ein Kunde die Löschung seiner Daten verlangt (DSGVO-Recht auf Vergessenwerden)?**
A: Das Modul ist so konzipiert, dass es sich in die DSGVO-Tools von PrestaShop integriert. Wenn ein Kunde über das PrestaShop-DSGVO-Modul die Datenlöschung anfordert, reagiert dieses Arukereso.hu-Modul auf den Hook `actionDeleteGDPRCustomer` und stellt sicher, dass alle vom Modul gespeicherten kundenbezogenen Daten (z. B. Zustimmungsdatensätze) entfernt werden. Es ist jedoch wichtig zu beachten, dass dieses Modul Daten an Arukereso.hu *sendet*. Sie müssten sich auch direkt an Arukereso.hu wenden, um die Löschung der Daten dieses Kunden aus deren Systemen zu beantragen.

**F: Kann ich das Aussehen des Zustimmungs-Kontrollkästchens anpassen?**
A: Das Aussehen des Zustimmungs-Kontrollkästchens wird hauptsächlich durch das CSS Ihres PrestaShop-Themes gesteuert. Das Modul stellt die HTML-Struktur über seine `consent.tpl`-Vorlage bereit. Sie können diese Vorlage in Ihrem Theme überschreiben oder benutzerdefiniertes CSS hinzufügen, um das Element zu gestalten, wenn Sie sein Aussehen ändern müssen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Arukereso.hu-Modul ist ein leichtgewichtiges PrestaShop-Modul, das sich hauptsächlich auf die Integration mit dem Arukereso.hu „Vertrauenswürdiges Kaufprogramm“ konzentriert. Es nutzt das Hook-System von PrestaShop, um eine Zustimmungsoption während des Checkouts einzufügen und Bestelldaten bei Bestellbestätigung an Arukereso.hu zu senden. Es folgt einer Standard-PrestaShop-Modulstruktur, wobei seine Kernlogik in der Hauptmoduldatei (`arukereso.php`) liegt und Smarty-Templates für die Front-Office-Anzeige verwendet werden. Es führt keine benutzerdefinierten Controller oder ObjectModels ein, sondern verlässt sich auf die `Configuration`-Klasse von PrestaShop für die Speicherung von Einstellungen.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Logik wird innerhalb der Hauptmoduldatei `arukereso.php` verarbeitet, hauptsächlich durch Hook-Methoden.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert **keine** benutzerdefinierten Klassen oder ObjectModels im Verzeichnis `classes/`. Es arbeitet direkt innerhalb der Datei `arukereso.php` unter Verwendung von Standard-PrestaShop-Klassen und -Funktionen.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien. Die gesamte Front-Office-Interaktion (z. B. Zustimmungs-Kontrollkästchen) wird über Standard-HTML-Formulare und serverseitige Verarbeitung abgewickelt.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Jegliche Gestaltung für das Zustimmungs-Kontrollkästchen oder andere Elemente würde vom aktiven PrestaShop-Theme geerbt werden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `arukereso/views/templates/hook/consent.tpl`
  - **Hook:** `displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop` (abhängig vom Theme und der PrestaShop-Version wird einer davon die Zustimmung rendern).
  - **Zweck:** Dieses Template rendert den HTML-Code für das Kunden-Zustimmungs-Kontrollkästchen während des Checkout-Prozesses. Es enthält typischerweise ein Label, das Kontrollkästchen-Eingabefeld und möglicherweise einen Link zur Datenschutzerklärung oder weitere Informationen über Arukereso.hu.
  - **Ausgabe:** Ein kleines Formularelement, das dem Kunden ermöglicht, dem Umfrageprogramm zuzustimmen.
- `arukereso/views/templates/hook/displayOrderConfirmation.tpl`
  - **Hook:** `displayOrderConfirmation`
  - **Zweck:** Dieses Template wird auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf gerendert. Es kann eine Nachricht an den Kunden anzeigen, die seine Teilnahme am Umfrageprogramm bestätigt (falls die Zustimmung erteilt wurde) oder Informationen über die bevorstehende Umfrage bereitstellt.
  - **Ausgabe:** Ein kleiner Informationsblock auf der Bestellbestätigungsseite.

#### Admin-Templates (`views/templates/admin/`)

Dieses Modul enthält **keine** benutzerdefinierten Admin-Templates über das hinaus, was von `getContent()` in der Hauptmoduldatei gerendert wird.

#### Front-Office-Templates (`views/templates/front/`)

Dieses Modul enthält **keine** dedizierten eigenständigen Front-Office-Seitentemplates.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Dieses Modul erstellt **keine** benutzerdefinierten Datenbanktabellen. Alle seine Konfigurationseinstellungen werden in der `ps_configuration`-Tabelle von PrestaShop unter Verwendung der folgenden Schlüssel gespeichert:

- `ARUKERESO_FILE_LOG`: Speichert den booleschen Wert für die Fehlerprotokollierung.
- `ARUKERESO_ID`: Speichert den Arukereso.hu WebApiKey.
- `ARUKERESO_PRODUCT_ID`: Speichert den gewählten Produktidentifikatortyp (z. B. 'id\_product', 'reference').
- `ARUKERESO_CONSENT`: Speichert den booleschen Wert für die Anforderung der Kundenzustimmung.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Ein Standard-PrestaShop-Konfigurationsschlüssel, der nicht direkt von diesem Modul verwaltet wird, aber möglicherweise für die Sprachbehandlung im Back Office verwendet wird.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayGDPRConsent` | Während des Checkouts, typischerweise in der Nähe der Datenschutzerklärung. | Rendert das Kunden-Zustimmungs-Kontrollkästchen für die Teilnahme an der Arukereso.hu-Umfrage. |
| `actionDeleteGDPRCustomer` | Wird ausgelöst, wenn ein Kunde über das PrestaShop-DSGVO-Modul die Datenlöschung anfordert. | Behandelt die Löschung aller vom Modul gespeicherten kundenspezifischen Daten (z. B. Zustimmungsstatus). |
| `actionExportGDPRData` | Wird ausgelöst, wenn ein Kunde über das PrestaShop-DSGVO-Modul die Datenexport anfordert. | Stellt alle vom Modul gespeicherten kundenspezifischen Daten für den Export bereit. |
| `displayOrderConfirmation` | Auf der Bestellbestätigungsseite nach einem erfolgreichen Kauf. | Rendert eine Informationsnachricht an den Kunden und sendet, entscheidend, die Bestelldaten an die Arukereso.hu-API, wenn die Zustimmung erteilt wurde. |
| `displayPaymentTop` | Am oberen Rand des Zahlungsbereichs während des Checkouts. | Alternativer Hook zum Rendern des Kunden-Zustimmungs-Kontrollkästchens, abhängig vom Theme. |
| `displayCheckoutSummaryTop` | Am oberen Rand des Checkout-Zusammenfassungsbereichs. | Alternativer Hook zum Rendern des Kunden-Zustimmungs-Kontrollkästchens, abhängig vom Theme. |
| `DisplayGDPRConsent` | (Alias/Ältere Version von `displayGDPRConsent`) | Rendert das Kunden-Zustimmungs-Kontrollkästchen. |
| `DisplayPaymentTop` | (Alias/Ältere Version von `displayPaymentTop`) | Rendert das Kunden-Zustimmungs-Kontrollkästchen. |
| `DisplayOrderConfirmation` | (Alias/Ältere Version von `displayOrderConfirmation`) | Rendert Informationen und sendet Bestelldaten. |
| `ActionDeleteGDPRCustomer` | (Alias/Ältere Version von `actionDeleteGDPRCustomer`) | Behandelt die Löschung von Kundendaten. |
| `ActionExportGDPRData` | (Alias/Ältere Version von `actionExportGDPRData`) | Behandelt den Export von Kundendaten. |
| `DisplayCheckoutSummaryTop` | (Alias/Ältere Version von `displayCheckoutSummaryTop`) | Rendert das Kunden-Zustimmungs-Kontrollkästchen. |

Die Kernlogik des Moduls zum Senden von Bestelldaten an Arukereso.hu befindet sich in der Methode `hookDisplayOrderConfirmation` in `arukereso.php`. Diese Methode prüft die Kundenzustimmung (falls erforderlich) und erstellt und sendet dann eine HTTP-Anfrage an die Arukereso.hu-API mit den Bestelldetails.

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zum Modul Arukereso.hu – Vertrauenswürdiges Kaufprogramm Umfrage-E-Mails gerne zur Verfügung.

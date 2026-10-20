---
title: "MyPazaruvaj - Pazaruvaj Umfrage-E-Mail - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul MyPazaruvaj - Pazaruvaj Umfrage-E-Mail von MyPresta.eu."
sidebar:
  label: "MyPazaruvaj - Pazaruvaj Umfrage-E-Mail - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul MyPazaruvaj - Pazaruvaj survey email auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/mypazaruvaj-pazaruvaj-survey-email.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/mypazaruvaj-pazaruvaj-survey-email/)
>
> ---


# MyPazaruvaj - Pazaruvaj Umfrage-E-Mail

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5 (Das Modul ist so konzipiert, dass es mit verschiedenen PHP-Versionen, bis zur neuesten stabilen Version, die von PrestaShop 8 und 9 unterstützt wird, weitgehend kompatibel ist.)
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind für dieses Modul ausreichend. Es sind keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > MyPazaruvaj)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das MyPazaruvaj-Modul. Hier legen Sie alle notwendigen Parameter fest, um Ihren Shop mit Pazaruvaj.com zu verbinden.

#### **Pazaruvaj.com Shop-ID**

- **Was diese Einstellung bewirkt:** Dies ist Ihre eindeutige Kennung, die Ihnen von Pazaruvaj.com für Ihren Online-Shop zur Verfügung gestellt wird. Sie teilt Pazaruvaj mit, zu welchem Shop die Bestelldaten gehören.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Bei korrekter Einstellung:* Das Modul sendet Bestelldaten erfolgreich an Ihr Pazaruvaj.com Shop-Profil.
  - *Bei falscher oder leerer Einstellung:* Pazaruvaj.com kann Ihren Shop nicht identifizieren, und es werden keine Umfrage-E-Mails an Ihre Kunden gesendet.
- **Empfohlener Wert:** Geben Sie die genaue Shop-ID ein, die Ihnen von Pazaruvaj.com zur Verfügung gestellt wurde. Dies ist ein Pflichtfeld.
- **Händlerszenario / Beispiel:** Sie haben Ihren Shop auf Pazaruvaj.com registriert und sie haben Ihnen eine Shop-ID wie `12345` gegeben. Sie müssen hier `12345` eingeben, damit die Integration funktioniert.

#### **Pazaruvaj.com Produkt-ID-Feld**

- **Was diese Einstellung bewirkt:** Diese Option bestimmt, welcher Produktidentifikator aus Ihrem PrestaShop-Shop an Pazaruvaj.com gesendet werden soll. Pazaruvaj.com verwendet diese ID, um das gekaufte Produkt mit seiner Auflistung auf ihrer Plattform abzugleichen.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf „Produkt-ID“ eingestellt:* Die interne PrestaShop-Produkt-ID (z.B. `id_product`) wird gesendet. Dies ist normalerweise die sicherste Option, wenn Ihr Pazaruvaj.com-Feed diese IDs verwendet.
  - *Wenn auf „Produktreferenz“ eingestellt:* Der Referenzcode des Produkts (z.B. `reference`) wird gesendet. Wählen Sie dies, wenn Ihr Pazaruvaj.com-Feed Produkte anhand ihrer Referenz abgleicht.
  - *Wenn auf „Produkt EAN13“ eingestellt:* Der EAN13-Barcode des Produkts wird gesendet. Nützlich, wenn Ihr Pazaruvaj.com-Feed auf EANs basiert.
  - *Wenn auf „Produkt UPC“ eingestellt:* Der UPC-Code des Produkts wird gesendet.
- **Empfohlener Wert:** „Produkt-ID“ ist oft der zuverlässigste Standardwert. Sie **müssen** jedoch überprüfen, welchen Identifikator Ihr Produkt-Feed auf Pazaruvaj.com zum Abgleich von Produkten verwendet. Wenn Ihr Feed Produktreferenzen verwendet, wählen Sie „Produktreferenz“.
- **Händlerszenario / Beispiel:** Wenn Ihr Produkt-Feed auf Pazaruvaj.com die eindeutige interne ID verwendet, die PrestaShop jedem Produkt zuweist, sollten Sie „Produkt-ID“ auswählen. Wenn Sie einen Feed hochgeladen haben, bei dem jedes Produkt durch eine spezifische SKU oder Referenznummer (z.B. `REF-001`) identifiziert wird, wählen Sie „Produktreferenz“.

#### **Einwilligung zur Datenübermittlung an Pazaruvaj.com aktivieren**

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob Kunden der Übermittlung ihrer Bestelldaten an Pazaruvaj.com für die Umfrage explizit zustimmen müssen. Wenn aktiviert, erscheint ein Kontrollkästchen während des Bestellvorgangs.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Ein Kontrollkästchen erscheint auf der Checkout-Seite. Nur Kunden, die dieses Kästchen ankreuzen, erhalten ihre Bestelldaten an Pazaruvaj.com gesendet. Dies hilft bei der Einhaltung der DSGVO und anderer Datenschutzbestimmungen.
  - *Wenn deaktiviert (NEIN):* Bestelldaten werden für *alle* abgeschlossenen Bestellungen an Pazaruvaj.com gesendet, ohne dass eine explizite Kundenzustimmung erforderlich ist. Dies ist einfacher für Kunden, entspricht aber möglicherweise nicht allen Datenschutzgesetzen in Ihrer Region.
- **Empfohlener Wert:** „JA“ wird im Allgemeinen zur Einhaltung von Datenschutzbestimmungen (wie der DSGVO) empfohlen.
- **Händlerszenario / Beispiel:** Um sicherzustellen, dass Ihr Shop vollständig den Datenschutzgesetzen entspricht, aktivieren Sie diese Einstellung. Während des Bestellvorgangs sehen Ihre Kunden ein Kontrollkästchen mit der Aufschrift „Ich stimme zu, meine Bestelldaten für eine Bewertungs-Umfrage mit Pazaruvaj.com zu teilen.“ Nur wenn sie es ankreuzen, werden die Daten gesendet.

#### **Einwilligung anzeigen auf**

- **Was diese Einstellung bewirkt:** Wenn „Einwilligung aktivieren“ auf JA gesetzt ist, bestimmt diese Option, wo das Einwilligungs-Kontrollkästchen im Front-Office Ihres Shops angezeigt wird.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Header, Spalten, Produkt, Footer:* Das Einwilligungs-Kontrollkästchen wird im ausgewählten Hook-Bereich angezeigt. Die genaue visuelle Platzierung hängt vom Layout Ihres Themes für diesen Hook ab.
- **Empfohlener Wert:** Wählen Sie einen prominenten, aber nicht aufdringlichen Ort. Der „Footer“ oder eine spezifische „Spalte“ (wenn Ihr Theme eine geeignete hat) sind oft gute Optionen für datenschutzbezogene Hinweise. Möglicherweise müssen Sie verschiedene Optionen testen, um zu sehen, was mit Ihrem Theme am besten aussieht.
- **Händlerszenario / Beispiel:** Sie haben die Einwilligung aktiviert. Sie entscheiden sich, das Einwilligungs-Kontrollkästchen im „Footer“ anzuzeigen, damit es sichtbar ist, aber den Haupt-Checkout-Fluss nicht überladen.

#### **Fehlerprotokoll aktivieren**

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob das Modul Fehler aufzeichnet, die während des Datenübertragungsprozesses an Pazaruvaj.com auftreten.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Modul speichert Details zu fehlgeschlagenen Datenübermittlungen in einer Protokolldatei. Dies ist von unschätzbarem Wert für die Fehlerbehebung, wenn Umfragen nicht gesendet werden.
  - *Wenn deaktiviert (NEIN):* Es werden keine Fehlerinformationen aufgezeichnet, was die Diagnose von Problemen erschwert.
- **Empfohlener Wert:** „JA“ wird dringend empfohlen, insbesondere während der Ersteinrichtung und für die laufende Überwachung.
- **Händlerszenario / Beispiel:** Sie sind sich nicht sicher, ob die Integration perfekt funktioniert. Sie aktivieren das Fehlerprotokoll. Wenn Pazaruvaj.com keine Daten empfängt, können Sie das Protokoll überprüfen, um festzustellen, ob spezifische Fehlermeldungen vorliegen, wie z.B. eine ungültige Shop-ID oder Verbindungsprobleme.

#### **Fehlerprotokoll löschen**

- **Was diese Einstellung bewirkt:** Diese Schaltfläche ermöglicht es Ihnen, alle Einträge aus dem Fehlerprotokoll des Moduls zu löschen.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Beim Klicken:* Alle zuvor aufgezeichneten Fehler werden dauerhaft aus der Protokolldatei entfernt.
- **Empfohlener Wert:** Verwenden Sie dies, nachdem Sie Probleme überprüft und behoben haben oder wenn die Protokolldatei zu groß wird.
- **Händlerszenario / Beispiel:** Sie haben ein Problem mit Ihrer Pazaruvaj.com Shop-ID behoben. Sie klicken auf „Fehlerprotokoll löschen“, um neu zu beginnen und sicherzustellen, dass nur neue, relevante Fehler aufgezeichnet werden.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Pazaruvaj.com Shop-ID | Ihre Pazaruvaj ID (Obligatorisch) | Eindeutige Kennung für Ihren Shop auf Pazaruvaj.com. Wesentlich für die Datenübertragung. |
| Modulkonfiguration | Pazaruvaj.com Produkt-ID-Feld | Produkt-ID (Mit Pazaruvaj-Feed überprüfen) | Bestimmt, welcher PrestaShop-Produktidentifikator (ID, Referenz, EAN13, UPC) an Pazaruvaj.com für den Produktabgleich gesendet wird. |
| Modulkonfiguration | Einwilligung zur Datenübermittlung an Pazaruvaj.com aktivieren | JA (Zur Einhaltung) | Erfordert die Kundenzustimmung über ein Kontrollkästchen während des Bestellvorgangs, bevor Daten an Pazaruvaj.com gesendet werden. |
| Modulkonfiguration | Einwilligung anzeigen auf | Footer (Für beste Platzierung testen) | Gibt den Front-Office-Hook an, in dem das Einwilligungs-Kontrollkästchen angezeigt wird, falls aktiviert. |
| Modulkonfiguration | Fehlerprotokoll aktivieren | JA (Zur Fehlerbehebung) | Aktiviert die Protokollierung von Fehlern während der Datenübermittlung an Pazaruvaj.com. |
| Modulkonfiguration | Fehlerprotokoll löschen | N/A (Schaltfläche) | Löscht alle Einträge aus dem Fehlerprotokoll des Moduls. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kunden erhalten keine Umfrage-E-Mails von Pazaruvaj.com. Was soll ich überprüfen?**
A:

1.  **Pazaruvaj.com Shop-ID:** Überprüfen Sie nochmals, ob Ihre „Pazaruvaj.com Shop-ID“ in der Modulkonfiguration absolut korrekt ist und mit der von Pazaruvaj.com bereitgestellten ID übereinstimmt.
2.  **Fehlerprotokoll:** Aktivieren Sie das „Fehlerprotokoll“ in der Modulkonfiguration und suchen Sie nach einem Testauftrag nach aufgezeichneten Fehlern. Dies wird oft das genaue Problem aufzeigen.
3.  **Einwilligungseinstellung:** Wenn „Einwilligung zur Datenübermittlung an Pazaruvaj.com aktivieren“ aktiviert ist, stellen Sie sicher, dass Kunden das Kontrollkästchen während des Bestellvorgangs tatsächlich ankreuzen. Wenn nicht, werden keine Daten gesendet.
4.  **Bestellstatus:** Stellen Sie sicher, dass die Bestellung in PrestaShop den Status „Zahlung akzeptiert“ oder einen ähnlichen endgültigen Status erreicht, da das Modul typischerweise bei erfolgreichem Abschluss der Bestellung ausgelöst wird.
5.  **Pazaruvaj.com-Konto:** Melden Sie sich in Ihrem Pazaruvaj.com-Konto an, um zu sehen, ob es dort Probleme oder Warnungen bezüglich Ihres Shops oder Datenfeeds gibt.

**F: Das Einwilligungs-Kontrollkästchen wird auf meiner Checkout-Seite nicht angezeigt.**
A:

1.  **„Einwilligung aktivieren“-Einstellung:** Stellen Sie zunächst sicher, dass „Einwilligung zur Datenübermittlung an Pazaruvaj.com aktivieren“ in der Modulkonfiguration auf JA gesetzt ist.
2.  **„Einwilligung anzeigen auf“-Einstellung:** Überprüfen Sie, welchen Hook Sie für „Einwilligung anzeigen auf“ ausgewählt haben. Wenn Ihr Theme in diesem spezifischen Hook (z.B. einem benutzerdefinierten `displayMyCustomHook`) keine Inhalte aktiv anzeigt, wird das Kontrollkästchen nicht erscheinen. Versuchen Sie, zu einem gängigen Hook wie `displayFooter` oder `displayHeader` zu wechseln, um dies zu testen.
3.  **Theme-Kompatibilität:** Einige stark angepasste Themes können Standard-Hook-Platzierungen überschreiben. Wenn das Problem weiterhin besteht, müssen Sie möglicherweise einen Webmaster bitten, die Template-Dateien Ihres Themes zu überprüfen.
4.  **Smarty-Cache:** Leeren Sie Ihren PrestaShop Smarty-Cache unter **Erweiterte Einstellungen > Leistung** (Kompilierung erzwingen und Cache leeren).

**F: Ich habe eine Einstellung geändert, aber nichts ist in meinem Shop passiert.**
A: Nachdem Sie Änderungen in der Modulkonfiguration vorgenommen haben, leeren Sie immer Ihren PrestaShop-Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung**, klicken Sie dann auf „Cache leeren“ und optional auf „Kompilierung erzwingen“, wenn Sie templatebezogene Änderungen vornehmen. Der Cache Ihres Browsers muss möglicherweise ebenfalls geleert werden (Strg+F5 oder Cmd+R).

**F: Kann ich den Text des Einwilligungs-Kontrollkästchens anpassen?**
A: Ja, der Text für das Einwilligungs-Kontrollkästchen ist übersetzbar. Sie können ihn über das PrestaShop-Übersetzungssystem ändern:

1.  Gehen Sie zu **International > Übersetzungen**.
2.  Wählen Sie „Übersetzungen installierter Module“.
3.  Wählen Sie Ihr Theme, die Sprache und dann „MyPazaruvaj“.
4.  Dort finden Sie die Zeichenfolge, die sich auf die Einwilligungsnachricht bezieht, und können sie bearbeiten.

**F: Was ist, wenn ich mehrere Shops (Multistore) aktiviert habe?**
A: Das Modul sollte in einer Multistore-Umgebung für jeden Shop einzeln konfiguriert werden. Stellen Sie sicher, dass Sie den richtigen Shop-Kontext im PrestaShop-Backoffice auswählen, bevor Sie das Modul für diesen spezifischen Shop konfigurieren. Jeder Shop wird wahrscheinlich seine eigene eindeutige Pazaruvaj.com Shop-ID haben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem MyPazaruvaj-Modul arbeiten.

### 4.1 Architekturübersicht

Das MyPazaruvaj-Modul folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse und ihre Methoden `install()`, `uninstall()` und `getContent()` für die Konfiguration verwendet. Seine Kernfunktionalität ist ereignisgesteuert und nutzt PrestaShop-Hooks, um Bestellbestätigungsereignisse abzufangen und optionale Einwilligungen anzuzeigen. Die Datenübermittlung an Pazaruvaj.com wird direkt in der Haupt-PHP-Datei des Moduls gehandhabt, ohne dedizierte Front- oder Admin-Controller, was es zu einer leichten und effizienten Lösung macht.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Controller. Die gesamte Konfigurationslogik wird innerhalb der `getContent()`-Methode der Hauptmoduldatei behandelt, und die Front-Office-Anzeigelogik wird direkt über Hook-Templates verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Die gesamte Logik ist in der Hauptklasse `MyPazaruvaj` enthalten, die in `mypazaruvaj/index.php` definiert ist.

Die Hauptklasse `MyPazaruvaj` erweitert `Module` und enthält:

- `__construct()`: Setzt Moduleigenschaften (Name, Tab, Version, Autor, `need_instance`, `ps_versions_compliancy`, Bootstrap).
- `install()`: Registriert notwendige Hooks (`displayOrderConfirmation`, `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`), erstellt Konfigurationseinträge und initialisiert die Fehlerprotokolldatei.
- `uninstall()`: Deregistriert Hooks und löscht Konfigurationseinträge.
- `getContent()`: Rendert das Back-Office-Konfigurationsformular des Moduls, verarbeitet Formularübermittlungen und aktualisiert Konfigurationswerte.
- `hookDisplayOrderConfirmation()`: Der primäre Hook für die Datenübermittlung. Er ruft Bestelldetails, Kundeninformationen und Produktdaten ab, konstruiert die Anfrage an Pazaruvaj.com und sendet sie. Er behandelt auch die optionale Einwilligungsprüfung.
- `hookDisplayHeader()`, `hookDisplayFooter()`, `hookDisplayLeftColumn()`, `hookDisplayRightColumn()`: Diese Hooks werden verwendet, um das Einwilligungs-Kontrollkästchen anzuzeigen, wenn es aktiviert und für die Anzeige an diesen Stellen konfiguriert ist. Sie rendern das `consent.tpl`-Template.
- `_clearLog()`: Interne Methode zum Löschen der Fehlerprotokolldatei.
- `_writeLog()`: Interne Methode zum Schreiben von Nachrichten in die Fehlerprotokolldatei.
- `_displayForm()`: Interne Methode zum Rendern des Konfigurationsformulars mit PrestaShop’s `HelperForm`.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Jegliche Formatierung für das Einwilligungs-Kontrollkästchen würde auf den Standard-Formularelement-Stilen des Themes basieren.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `mypazaruvaj/views/templates/hook/consent.tpl`:
    - **Zweck:** Rendert das optionale Einwilligungs-Kontrollkästchen für die Datenübermittlung an Pazaruvaj.com.
    - **Gerendert in Hooks:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn` (abhängig von der Modulkonfiguration).
    - **Variablen:** Prüft typischerweise auf `$consent_enabled` und zeigt ein Formularfeld an.
    - **Ausgabe:** Ein einfaches HTML-Kontrollkästchen und Beschriftung.
  - `mypazaruvaj/views/templates/hook/displayOrderConfirmation.tpl`:
    - **Zweck:** Dieses Template ist wahrscheinlich ein Platzhalter oder wird für interne Modullogik verwendet, die keine sichtbaren Inhalte direkt an den Kunden ausgibt. Die primäre Datenübermittlungslogik für `displayOrderConfirmation` wird in der PHP-Hook-Methode selbst behandelt, nicht unbedingt über eine Template-Ausgabe. Es könnte verwendet werden, um Variablen zu übergeben oder JS auszulösen, falls das Modul dies hätte. Im Kontext dieses Moduls ist es hauptsächlich die PHP-Hook-Methode, die die Aktion ausführt.
- **Admin-Templates (`views/templates/admin/`)**:

  - Dieses Modul verwendet keine dedizierten Admin-Templates. Das Konfigurationsformular wird programmatisch mit `HelperForm` innerhalb von `getContent()` generiert.
- **Front-Office-Templates (`views/templates/front/`)**:

  - Dieses Modul enthält keine dedizierten Front-Office-Templates über die Hook-Templates hinaus.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der Standard-PrestaShop-Tabelle `ps_configuration`.
    - `MYPAZARUVAJ_SHOP_ID`: Speichert die Pazaruvaj.com Shop-ID.
    - `MYPAZARUVAJ_PRODUCT_ID_FIELD`: Speichert das ausgewählte Produkt-ID-Feld (z.B. 'id\_product', 'reference').
    - `MYPAZARUVAJ_CONSENT_ENABLED`: Boolean (0 oder 1) zum Aktivieren/Deaktivieren der Einwilligung.
    - `MYPAZARUVAJ_CONSENT_HOOK`: Speichert den Namen des Hooks, in dem die Einwilligung angezeigt wird.
    - `MYPAZARUVAJ_ERROR_LOG_ENABLED`: Boolean (0 oder 1) zum Aktivieren/Deaktivieren des Fehlerprotokolls.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayOrderConfirmation` | Nachdem ein Kunde eine Bestellung erfolgreich abgeschlossen hat. | **Primärer Hook für die Datenübermittlung.** Ruft Bestell- und Produktdetails ab, konstruiert die Pazaruvaj.com-Anfrage und sendet sie. Prüft auf Einwilligung, falls aktiviert. |
| `displayHeader` | Im `<head>`-Bereich oder oben auf jeder Seite. | Rendert `consent.tpl`, wenn für die Anzeige der Einwilligung hier konfiguriert. |
| `displayFooter` | Im Footer-Bereich jeder Seite. | Rendert `consent.tpl`, wenn für die Anzeige der Einwilligung hier konfiguriert. |
| `displayLeftColumn` | In der linken Seitenleistenspalte (falls im Theme aktiv). | Rendert `consent.tpl`, wenn für die Anzeige der Einwilligung hier konfiguriert. |
| `displayRightColumn` | In der rechten Seitenleistenspalte (falls im Theme aktiv). | Rendert `consent.tpl`, wenn für die Anzeige der Einwilligung hier konfiguriert. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support wenden Sie sich bitte an Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum MyPazaruvaj-Modul gerne zur Verfügung.

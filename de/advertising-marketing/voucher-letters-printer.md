---
title: "Voucher & Letters Printer - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Voucher & Letters Printer“ von MyPresta.eu."
sidebar:
  label: "Voucher & Letters Printer - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Voucher & Letters Printer auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/voucher-letters-printer.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/voucher-letters-printer/)
>
> ---


# Voucher & Letters Printer

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Keine speziellen Hosting-Anforderungen über eine typische PrestaShop-Einrichtung hinaus.

## 2. Vollständige Konfigurationsanleitung (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > Voucher & Letters Printer)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie die Parameter für Ihre Gutscheine und Briefe definieren.

#### **Allgemeine Einstellungen**

- **Was diese Einstellung bewirkt:** Diese Einstellungen steuern das Gesamtverhalten und Aussehen der generierten Gutscheine und Briefe.
- **Auswirkung der Änderung dieser Einstellung:** Änderungen hier wirken sich direkt auf den Inhalt und das Format der Dokumente aus, die Sie drucken.

#### **Gutscheincode-Generierung**

- **Gutschein-Präfix:**

  - **Was diese Einstellung bewirkt:** Dieser Text wird an den Anfang jedes generierten Gutscheincodes angefügt. Er hilft Ihnen, die Herkunft des Gutscheins zu identifizieren (z. B. „WILLKOMMEN-“, „TREUE-“).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „SALE-“ gesetzt:* Alle generierten Codes beginnen mit „SALE-“, z. B. „SALE-ABC123XYZ“.
    - *Wenn leer gelassen:* Codes bestehen aus rein zufälligen Zeichen, z. B. „ABC123XYZ“.
  - **Empfohlener Wert:** Ein kurzes, beschreibendes Präfix, das mit Ihrer Kampagne zusammenhängt.
  - **Händlerszenario / Beispiel:** Wenn Sie eine Treueprämie versenden, verwenden Sie „TREUE-“. Für einen saisonalen Verkauf „SOMMER-“.
- **Gutschein-Suffix:**

  - **Was diese Einstellung bewirkt:** Ähnlich wie das Präfix wird dieser Text an das Ende jedes generierten Gutscheincodes angefügt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „-2024“ gesetzt:* Alle generierten Codes enden mit „-2024“, z. B. „ABC123XYZ-2024“.
    - *Wenn leer gelassen:* Codes haben kein Suffix.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben einen spezifischen Tracking-Bedarf.
  - **Händlerszenario / Beispiel:** Sie könnten ein Jahres-Suffix wie „-2024“ für jährliche Kampagnen verwenden.
- **Länge des Gutscheincodes (ohne Präfix/Suffix):**

  - **Was diese Einstellung bewirkt:** Bestimmt die Anzahl der zufälligen Zeichen im Gutscheincode selbst, zwischen Präfix und Suffix. Ein längerer Code ist sicherer, aber schwieriger einzugeben.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 8 gesetzt:* Codes haben 8 zufällige Zeichen (z. B. „ABC123XY“).
    - *Wenn auf 12 gesetzt:* Codes haben 12 zufällige Zeichen (z. B. „ABC123XYZ456“).
  - **Empfohlener Wert:** 8-12 Zeichen für ein gutes Gleichgewicht zwischen Sicherheit und Benutzerfreundlichkeit.
  - **Händlerszenario / Beispiel:** Für eine allgemeine Aktion sind 8 Zeichen in der Regel ausreichend. Für hochwertige, exklusive Gutscheine könnten Sie 10-12 wählen.

#### **Gutschein- & Briefinhalt**

- **Gutscheinwert:**

  - **Was diese Einstellung bewirkt:** Dies ist der monetäre Wert oder prozentuale Rabatt, den der generierte Gutschein bietet.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „10“ gesetzt:* Der Gutschein gewährt einen Rabatt von 10 Einheiten (z. B. 10 €, 10 $).
    - *Wenn auf „20%“ gesetzt:* Der Gutschein gewährt einen Rabatt von 20 %.
  - **Empfohlener Wert:** Ein Wert, der zum Kauf anregt, ohne Ihre Margen wesentlich zu beeinträchtigen.
  - **Händlerszenario / Beispiel:** Bieten Sie 15 € Rabatt bei einem Mindestbestellwert von 100 € oder 10 % Rabatt auf den gesamten Warenkorb an.
- **Gutschein-Mindestbetrag:**

  - **Was diese Einstellung bewirkt:** Der Mindestbestellwert (vor Versand), der erforderlich ist, damit der Kunde den Gutschein verwenden kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „50“ gesetzt:* Kunden müssen mindestens 50 € ausgeben, um den Gutschein zu verwenden.
    - *Wenn auf „0“ gesetzt oder leer gelassen:* Es ist kein Mindestkauf erforderlich.
  - **Empfohlener Wert:** Legen Sie einen Mindestbetrag fest, um die Rentabilität zu gewährleisten, typischerweise das 2-3-fache des Gutscheinwerts.
  - **Händlerszenario / Beispiel:** Wenn der Gutschein für 10 € ist, legen Sie ein Minimum von 30 € fest, um einen größeren Kauf zu fördern.
- **Gutschein-Ablaufdatum (Tage ab Generierung):**

  - **Was diese Einstellung bewirkt:** Definiert, wie viele Tage nach der Generierung der Gutschein abläuft. Dies erzeugt Dringlichkeit.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „30“ gesetzt:* Der Gutschein ist 30 Tage ab dem Erstellungsdatum gültig.
    - *Wenn auf „0“ gesetzt oder leer gelassen:* Der Gutschein hat kein Ablaufdatum (nicht empfohlen für die meisten Kampagnen).
  - **Empfohlener Wert:** 30-90 Tage, abhängig von der Dringlichkeit, die Sie erzeugen möchten.
  - **Händlerszenario / Beispiel:** Für einen schnellen Verkauf 30 Tage. Für eine Treueprämie 90 Tage.
- **Briefkopf-Text:**

  - **Was diese Einstellung bewirkt:** Dies ist der Haupttitel oder die Begrüßung, die oben in Ihrem personalisierten Brief erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Sehr geehrter Kunde,“ gesetzt:* Dies ist die Eröffnungszeile jedes Briefes.
    - *Wenn auf „Ein besonderes Angebot nur für Sie!“ gesetzt:* Dies ist die prominente Überschrift.
  - **Empfohlener Wert:** Eine herzliche, persönliche Begrüßung.
  - **Händlerszenario / Beispiel:** „Hallo [Kundenname],“ (wenn Sie planen, Namen manuell einzufügen oder später ein Serienbrieftool zu verwenden) oder „Vielen Dank, dass Sie ein treuer Kunde sind!“
- **Brieftext:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptinhalt Ihres Briefes, in dem Sie das Angebot erklären, dem Kunden danken und alle anderen relevanten Informationen bereitstellen. Sie können Platzhalter für dynamische Inhalte verwenden (obwohl das Modul selbst keine direkten Platzhalter bietet, würden Sie hierfür typischerweise nach dem Export ein Serienbrieftool verwenden).
  - **Auswirkung der Änderung dieser Einstellung:** Dieser Text bildet die Kernbotschaft Ihres physischen Briefes.
  - **Empfohlener Wert:** Klarer, prägnanter und überzeugender Text, der die Vorteile des Gutscheins erklärt und zur Einlösung anregt.
  - **Händlerszenario / Beispiel:** „Als Zeichen unserer Wertschätzung erhalten Sie [Gutscheinwert] Rabatt auf Ihren nächsten Einkauf ab [Mindestbetrag]. Verwenden Sie den Code: [Gutscheincode]. Gültig bis [Ablaufdatum].“
- **Brief-Fußzeilentext:**

  - **Was diese Einstellung bewirkt:** Dieser Text erscheint am Ende Ihres Briefes, typischerweise für die Kontaktinformationen Ihres Shops, die Website oder eine Schlussbemerkung.
  - **Auswirkung der Änderung dieser Einstellung:** Dies ist der abschließende Abschnitt Ihres Briefes.
  - **Empfohlener Wert:** Die Website Ihres Shops, Kontakt-E-Mail oder ein freundlicher Abschluss wie „Mit freundlichen Grüßen, Ihr [Name Ihres Shops]-Team.“
  - **Händlerszenario / Beispiel:** „Besuchen Sie uns unter [www.ihrshop.de](http://www.ihrshop.de) für weitere tolle Produkte!“

#### **Druck- & Designoptionen**

- **Gutscheincode auf Brief drucken:**

  - **Was diese Einstellung bewirkt:** Ein einfacher Schalter, um den generierten Gutscheincode direkt in den gedruckten Brief aufzunehmen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Der einzigartige Gutscheincode wird automatisch in den Brieftext eingefügt, wo immer Sie ihn angeben (oder an einer Standardposition, wenn nicht im Brieftext angegeben).
    - *Wenn deaktiviert (NEIN):* Der Gutscheincode wird nicht auf dem Brief gedruckt. Sie könnten dies wählen, wenn Sie separate Gutscheinkarten drucken.
  - **Empfohlener Wert:** JA, aus Bequemlichkeit und um sicherzustellen, dass der Kunde den Code hat.
  - **Händlerszenario / Beispiel:** Wenn Sie ein einziges Dokument für den Kunden wünschen, aktivieren Sie dies.
- **Textfarbe (für Brief/Gutschein):**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl der Textfarbe auf Ihren gedruckten Dokumenten.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die Tintenfarbe, die für den Text verwendet wird.
  - **Empfohlener Wert:** Schwarz oder eine dunkle, lesbare Farbe, die gut mit weißem Papier kontrastiert.
  - **Händlerszenario / Beispiel:** Verwenden Sie die primäre Textfarbe Ihrer Marke für Konsistenz.
- **Hintergrundfarbe (für Gutscheinbereich):**

  - **Was diese Einstellung bewirkt:** Wenn Sie Gutscheine direkt auf den Brief drucken, legt dies eine Hintergrundfarbe für den Gutscheincode-Bereich fest, um ihn hervorzuheben.
  - **Auswirkung der Änderung dieser Einstellung:** Erstellt ein farbiges Feld hinter dem Gutscheincode.
  - **Empfohlener Wert:** Eine helle, dezente Farbe, die den Text nicht verdeckt, oder lassen Sie es weiß, wenn Sie dies bevorzugen.
  - **Händlerszenario / Beispiel:** Ein helles Grau oder eine Pastellversion Ihrer Markenfarbe, um den Gutschein hervorzuheben.
- **Schriftgröße (für Brief/Gutschein):**

  - **Was diese Einstellung bewirkt:** Steuert die Größe des Textes auf Ihren gedruckten Dokumenten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „12px“ gesetzt:* Der Text hat eine Standard-Lesegröße.
    - *Wenn auf „16px“ gesetzt:* Der Text ist größer, für manche leichter zu lesen.
  - **Empfohlener Wert:** 10-14px für den Fließtext, etwas größer für Überschriften.
  - **Händlerszenario / Beispiel:** Wenn Ihre Zielgruppe ältere Demografien umfasst, könnte eine etwas größere Schriftgröße vorteilhaft sein.

#### **Kundenauswahl & Generierung**

- **Kunden auswählen:**

  - **Was diese Einstellung bewirkt:** Dieser Abschnitt ermöglicht es Ihnen, auszuwählen, welche Kunden die personalisierten Briefe und Gutscheine erhalten sollen. Sie können bestimmte Kunden aus einer Liste auswählen.
  - **Auswirkung der Änderung dieser Einstellung:** Nur die ausgewählten Kunden erhalten generierte Gutscheine, und ihre Details werden für die Briefe verwendet.
  - **Empfohlener Wert:** Wählen Sie Kunden basierend auf Ihren Kampagnenzielen aus (z. B. Neukunden, treue Kunden, inaktive Kunden).
  - **Händlerszenario / Beispiel:** Wählen Sie alle Kunden aus, die in den letzten 6 Monaten nichts gekauft haben, um sie erneut zu aktivieren.
- **Gutscheine & Briefe generieren-Schaltfläche:**

  - **Was diese Einstellung bewirkt:** Nach der Konfiguration aller Einstellungen und der Auswahl der Kunden initiiert das Klicken auf diese Schaltfläche den Prozess der Generierung der einzigartigen Gutscheincodes und der Vorbereitung der personalisierten Briefe zum Drucken.
  - **Auswirkung der Änderung dieser Einstellung:** Diese Aktion erstellt neue Warenkorbregeln (Gutscheine) in Ihrem PrestaShop-Shop und generiert die druckbaren Dokumente.
  - **Empfohlener Wert:** Klicken Sie erst, nachdem Sie alle Einstellungen sorgfältig überprüft haben.
  - **Händlerszenario / Beispiel:** Sobald eine Kampagne geplant ist, klicken Sie hier, um den Versand vorzubereiten.

#### **Konfigurations-Kurzübersichtstabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Hauptkonfiguration | Gutschein-Präfix | `TREUE-` | Text am Anfang des Gutscheincodes. Hilft bei der Kampagnenidentifikation. |
| Hauptkonfiguration | Gutschein-Suffix | Leer | Text am Ende des Gutscheincodes. Nützlich für das Tracking. |
| Hauptkonfiguration | Länge des Gutscheincodes | 8-12 | Anzahl der Zufallszeichen im Code. Beeinflusst Sicherheit/Benutzerfreundlichkeit. |
| Hauptkonfiguration | Gutscheinwert | `10` (z. B. 10 € oder 10 %) | Rabattbetrag oder Prozentsatz. |
| Hauptkonfiguration | Gutschein-Mindestbetrag | `0` (oder 2-3x Gutscheinwert) | Mindestbestellwert für die Gutscheinnutzung. Gewährleistet Rentabilität. |
| Hauptkonfiguration | Gutschein-Ablaufdatum (Tage) | `30-90` | Tage bis zum Ablauf des Gutscheins. Erzeugt Dringlichkeit. |
| Hauptkonfiguration | Briefkopf-Text | `Sehr geehrter Kunde,` | Hauptbegrüßung/Titel des Briefes. |
| Hauptkonfiguration | Brieftext | (Benutzerdefinierte Nachricht) | Hauptinhalt des Briefes, der das Angebot erklärt. |
| Hauptkonfiguration | Brief-Fußzeilentext | `www.ihrshop.de` | Schlussbemerkungen, Kontaktinformationen. |
| Hauptkonfiguration | Gutscheincode auf Brief drucken | JA | Fügt den Gutscheincode direkt in den Brief ein. |
| Hauptkonfiguration | Textfarbe | Schwarz | Farbe des gesamten Textes auf gedruckten Dokumenten. |
| Hauptkonfiguration | Hintergrundfarbe | Weiß (oder hellgrau) | Hintergrundfarbe für den Gutscheincode-Bereich. |
| Hauptkonfiguration | Schriftgröße | `12px` | Größe des Textes auf gedruckten Dokumenten. |
| Hauptkonfiguration | Kunden auswählen | (Spezifische Auswahl) | Wählen Sie aus, welche Kunden die Sendung erhalten. |
| Hauptkonfiguration | Gutscheine & Briefe generieren | (Schaltflächenklick) | Erstellt Gutscheine und druckbare Dokumente. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe Gutscheine generiert, aber sie scheinen in meinem Shop nicht zu funktionieren.**
A1: Nach der Generierung erstellt das Modul „Warenkorbregeln“ in PrestaShop.
1. **Warenkorbregeln überprüfen:** Gehen Sie in Ihrem Back Office zu **Katalog > Rabatte > Warenkorbregeln**. Stellen Sie sicher, dass die generierten Gutscheine dort aufgeführt und „Aktiviert“ sind.
2. **Bedingungen überprüfen:** Überprüfen Sie, ob die Bedingungen des Gutscheins (Mindestbetrag, Ablaufdatum, Kundenbeschränkungen) Ihren Absichten entsprechen. Wenn ein Kunde versucht, einen Gutschein zu verwenden, der die Kriterien nicht erfüllt, wird er nicht angewendet.
3. **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass neue Einstellungen sofort wirksam werden. Gehen Sie zu **Erweiterte Parameter > Leistung** und klicken Sie auf „Cache leeren“.

**F2: Die gedruckten Briefe sehen nicht richtig aus oder die Farben stimmen nicht.**
A2:
1. **Moduleinstellungen überprüfen:** Rufen Sie die Modulkonfigurationsseite erneut auf. Überprüfen Sie Ihre Einstellungen für „Textfarbe“, „Hintergrundfarbe“ und „Schriftgröße“. Stellen Sie sicher, dass Sie Farben ausgewählt haben, die gut drucken.
2. **Druckereinstellungen:** Die endgültige Ausgabequalität hängt stark von Ihrem physischen Drucker ab. Überprüfen Sie die Tintenstände, den Papiertyp und die Druckqualitätseinstellungen Ihres Druckers. Versuchen Sie, eine Testseite aus einer anderen Anwendung zu drucken.
3. **Browser-Druckvorschau:** Wenn Sie den Druck über Ihren Browser starten, verwenden Sie die Druckvorschau, um zu sehen, wie es aussehen wird, bevor Sie Tinte und Papier verbrauchen. Passen Sie bei Bedarf die Browser-Druckeinstellungen (z. B. Ränder, Kopf-/Fußzeilen) an.

**F3: Kann ich den Briefinhalt für internationale Kunden in verschiedene Sprachen übersetzen?**
A3: Die aktuelle Version des Moduls bietet keine integrierten mehrsprachigen Felder für den Briefinhalt direkt in seiner Konfiguration. Sie müssten:
1. **Für jede Sprache generieren:** Konfigurieren Sie das Modul mit dem Briefinhalt in einer Sprache, generieren Sie die Briefe für die relevanten Kunden und wiederholen Sie den Vorgang für andere Sprachen und Kundengruppen.
2. **Manuelle Übersetzung:** Wenn Sie die Kundendaten und Gutscheincodes exportieren, könnten Sie ein separates Serienbrieftool verwenden, um mehrsprachige Briefe zu erstellen.

**F4: Ich möchte Briefe nur an Kunden aus einem bestimmten Land senden. Wie kann ich das tun?**
A4: Die Funktion „Kunden auswählen“ des Moduls ermöglicht es Ihnen, einzelne Kunden auszuwählen. Wenn Sie nach Land oder anderen Kriterien filtern müssen, würden Sie typischerweise:
1. **Kundendaten exportieren:** Gehen Sie in Ihrem Back Office zu **Kunden > Kunden** und verwenden Sie die Exportfunktion, um eine Liste all Ihrer Kunden zu erhalten.
2. **Extern filtern:** Verwenden Sie ein Tabellenkalkulationsprogramm (wie Excel oder Google Sheets), um Ihre Kundenliste nach Land oder anderen gewünschten Kriterien zu filtern.
3. **Manuelle Auswahl:** Kehren Sie zum Modul zurück und wählen Sie die gefilterten Kunden manuell aus der Liste aus. Dies kann bei großen Listen mühsam sein.
4. **Entwickleranpassung (Fortgeschritten):** Für sehr große oder komplexe Filteranforderungen könnte ein Entwickler das Modul erweitern, um erweiterte Kundenfilteroptionen hinzuzufügen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Voucher & Letters Printer“ arbeiten.

### 4.1 Architekturübersicht

Das Modul „Voucher & Letters Printer“ ist ein Standard-PrestaShop-Modul, das hauptsächlich im Back Office betrieben wird. Es nutzt die `Module`-Klasse von PrestaShop für seine Kernfunktionalität und die `Configuration`-Klasse zum Speichern von Einstellungen. Der Hauptzweck des Moduls besteht darin, `CartRule`-Objekte (Gutscheine) zu generieren und dann druckbaren HTML-Inhalt basierend auf Moduleinstellungen und ausgewählten Kundendaten zu rendern. Es führt keine benutzerdefinierten Datenbanktabellen oder komplexen `ObjectModel`-Strukturen ein, die über das hinausgehen, was PrestaShop bereits für `CartRule` und `Customer` bereitstellt.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration und Logik wird innerhalb der `getContent()`-Methode der Hauptmoduldatei behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Es interagiert direkt mit den Kernklassen von PrestaShop, hauptsächlich:

- `Module`: Die Basisklasse für das Modul selbst.
- `Configuration`: Zum Speichern und Abrufen von Moduleinstellungen.
- `Customer`: Zum Abrufen von Kundendaten für die Briefpersonalisierung.
- `CartRule`: Zum Erstellen und Verwalten der generierten Gutscheincodes.

### 4.4 JavaScript-Assets (`views/js/`)

- **`voucherletter/js/jscolor/jscolor.js`**

  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Dies ist eine JavaScript-Bibliothek eines Drittanbieters für einen erweiterten Farbwähler. Sie ermöglicht es dem Administrator, Farben für Text und Hintergrund im Konfigurationsformular des Moduls visuell auszuwählen.
  - **Funktionalität:** Bindet an Eingabefelder mit spezifischen Klassen (z. B. `jscolor`), um eine Farbpalette anzuzeigen und den Eingabewert mit dem gewählten hexadezimalen Farbcode zu aktualisieren.
- **`voucherletter/js/script.js`**

  - **Geltungsbereich:** Back-Office (Modulkonfigurationsseite).
  - **Beschreibung:** Enthält benutzerdefinierte JavaScript-Logik, die spezifisch für das Konfigurationsformular des Moduls ist.
  - **Funktionalität:**
    - Behandelt wahrscheinlich AJAX-Anfragen zum Generieren von Gutscheinen und Briefen (obwohl das Moduldossier impliziert, dass `getContent()` den gesamten Prozess abwickelt, könnte dieses Skript bei der Formularübermittlung oder dynamischen Aktualisierungen helfen).
    - Könnte Validierungslogik für Formularfelder enthalten (z. B. Sicherstellen, dass der Gutscheinwert eine Zahl ist).
    - Könnte die Anzeige/Ausblendung bestimmter Formularelemente basierend auf anderen Auswahlen verwalten.
    - Löst möglicherweise die Druckfunktion im Browser aus, nachdem der Briefinhalt generiert wurde.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Moduldossier weist darauf hin, dass keine benutzerdefinierten CSS-Dateien in `views/css/` vorhanden sind. Das Styling für die Back-Office-Konfiguration würde auf dem Standard-Admin-Theme-CSS von PrestaShop basieren. Jegliches Styling für die *gedruckte Ausgabe* wäre Inline-CSS, das vom PHP-Code generiert wird, oder sehr grundlegendes HTML-Styling.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Moduldossier weist darauf hin, dass keine benutzerdefinierten `.tpl`-Dateien in `views/templates/` vorhanden sind. Dies deutet darauf hin, dass:

- Das Back-Office-Konfigurationsformular wahrscheinlich direkt innerhalb der `getContent()`-Methode mit PrestaShops `HelperForm` oder durch Verketten von HTML-Strings gerendert wird.
- Der druckbare Briefinhalt dynamisch als HTML-String innerhalb des PHP-Codes generiert und dann für die Druckfunktion des Browsers ausgegeben wird.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es speichert seine Konfigurationseinstellungen in der `ps_configuration`-Tabelle von PrestaShop. Konfigurationsschlüssel würden typischerweise einem Muster wie `VOUCHERLETTER_PREFIX`, `VOUCHERLETTER_VALUE` usw. folgen.
  - Es erstellt neue Einträge in der `ps_cart_rule` und verwandten Tabellen (`ps_cart_rule_lang`, `ps_cart_rule_product_rule_group` usw.), wenn Gutscheine generiert werden.
- **Registrierte Hooks-Tabelle**:
  Das Moduldossier weist darauf hin, dass das Modul keine Front-Office-Hooks (Header, Spalten, Produkt, Footer) registriert. Dies bestätigt seine Hauptfunktion als Back-Office-Tool zum Generieren physischer Post.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionModuleInstall` | Während der Modulinstallation | Richtet Standardkonfigurationswerte in `ps_configuration` ein. |
| `actionModuleUninstall` | Während der Moduldeinstallation | Bereinigt Konfigurationswerte aus `ps_configuration`. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul „Voucher & Letters Printer“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.

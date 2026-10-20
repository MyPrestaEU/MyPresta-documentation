---
title: "Produkt-Datumsänderung – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Produkt-Datumsänderung' von MyPresta.eu."
sidebar:
  label: "Produkt-Datumsänderung – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product date change auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/product-date-change.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/product-date-change/)
>
> ---


# Produkt-Datumsänderung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptkonfigurationsseite des Moduls „Produkt-Datumsänderung“. Hier wählen Sie Produkte aus und ändern deren Daten.

#### **Produktauswahl**

- **Was diese Einstellung bewirkt:** Dieser Abschnitt ermöglicht es Ihnen, die spezifischen Produkte zu suchen und auszuwählen, deren Daten Sie ändern möchten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Suche nach einem Produkt:* Die Eingabe in das Suchfeld filtert Ihre Produktliste, wodurch es einfacher wird, das genaue Produkt zu finden, das Sie benötigen.
  - *Auswahl eines Produkts:* Sobald ein Produkt ausgewählt ist, werden dessen aktuelle Erstellungs- und Aktualisierungsdaten angezeigt, und Sie können neue Daten eingeben.
- **Empfohlener Wert:** Verwenden Sie die Suchleiste, um Produkte schnell nach Namen oder ID zu finden.
- **Händlerszenario / Beispiel:** Sie möchten das Datum für „Sommerkleid 2023“ ändern. Sie geben „Sommerkleid“ in das Suchfeld ein, und das Modul zeigt passende Produkte an. Anschließend klicken Sie auf „Sommerkleid 2023“, um es auszuwählen.

#### **Produkt-Erstellungsdatum ändern**

- **Was diese Einstellung bewirkt:** Dieses Feld ermöglicht es Ihnen, ein neues `date_add` (Erstellungsdatum) für das ausgewählte Produkt festzulegen. Dieses Datum wird oft von PrestaShop verwendet, um zu bestimmen, ob ein Produkt „neu“ ist.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein neues Datum eingegeben und gespeichert wird:* Das Erstellungsdatum des Produkts in Ihrer Datenbank wird aktualisiert. Dies kann dazu führen, dass das Produkt in „Neue Produkte“-Blöcken wieder erscheint oder seine Position beim Sortieren nach „Hinzugefügt am“ ändert.
  - *Wenn unverändert gelassen:* Das ursprüngliche Erstellungsdatum des Produkts bleibt erhalten.
- **Empfohlener Wert:** Legen Sie ein Datum fest, das widerspiegelt, wann das Produkt als „neu“ betrachtet werden soll oder wann es tatsächlich zu Ihrem Katalog hinzugefügt wurde. Zum erneuten Hervorheben ist ein aktuelles Datum (heute oder gestern) ideal.
- **Händlerszenario / Beispiel:** Ihr Produkt „Wintermantel“ wurde letztes Jahr hinzugefügt. Sie möchten es als „Neuheit“ für die kommende Wintersaison bewerben. Sie wählen das Produkt aus und setzen das „Produkt-Erstellungsdatum ändern“ auf das heutige Datum. Nun wird es in Ihrem Bereich „Neue Produkte“ angezeigt.

#### **Produkt-Aktualisierungsdatum ändern**

- **Was diese Einstellung bewirkt:** Dieses Feld ermöglicht es Ihnen, ein neues `date_upd` (Datum der letzten Aktualisierung) für das ausgewählte Produkt festzulegen. Dieses Datum wird für die interne Nachverfolgung verwendet und kann auch die Produktsortierung beeinflussen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein neues Datum eingegeben und gespeichert wird:* Das Datum der letzten Aktualisierung des Produkts in Ihrer Datenbank wird geändert. Dies kann Sortieroptionen beeinflussen, bei denen Kunden nach „Zuletzt aktualisiert“ sortieren.
  - *Wenn unverändert gelassen:* Das ursprüngliche Aktualisierungsdatum des Produkts bleibt erhalten.
- **Empfohlener Wert:** Legen Sie ein Datum fest, das die letzte signifikante Änderung am Produkt widerspiegelt (z. B. aktualisierte Beschreibung, Preis, Bilder) oder wenn Sie es an die Spitze von „kürzlich aktualisierten“ Listen bringen möchten.
- **Händlerszenario / Beispiel:** Sie haben gerade die Beschreibung aktualisiert und neue Bilder für Ihr Produkt „Bio-Kaffeebohnen“ hinzugefügt. Sie möchten, dass dieses Produkt höher erscheint, wenn Kunden nach „kürzlich aktualisiert“ sortieren. Sie wählen das Produkt aus und setzen das „Produkt-Aktualisierungsdatum ändern“ auf das heutige Datum.

#### **Speichern-Schaltfläche**

- **Was diese Einstellung bewirkt:** Diese Schaltfläche wendet alle Datumsänderungen an, die Sie für das ausgewählte Produkt vorgenommen haben.
- **Auswirkung der Änderung dieser Einstellung:** Durch Klicken auf „Speichern“ werden die neuen Erstellungs- und/oder Aktualisierungsdaten in Ihrer PrestaShop-Datenbank gespeichert. Sie sehen normalerweise eine Erfolgsmeldung.
- **Empfohlener Wert:** Klicken Sie immer auf „Speichern“, nachdem Sie Datumsänderungen vorgenommen haben.
- **Händlerszenario / Beispiel:** Nachdem Sie sowohl das Erstellungs- als auch das Aktualisierungsdatum für Ihre „Limited Edition Sneakers“ festgelegt haben, klicken Sie auf „Speichern“, um diese Änderungen in Ihrem Shop anzuwenden.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Produktsuchfeld | N/A | Finden Sie Produkte nach Namen oder ID, um deren Daten zu ändern. |
| Modulkonfigurationsseite | Produkt-Erstellungsdatum ändern | Aktuelles `date_add` des Produkts | Legt ein neues Erstellungsdatum fest. Beeinflusst die Sichtbarkeit von „Neuen Produkten“ und die Sortierung nach „Hinzugefügt am“. Empfohlen: Ein aktuelles Datum zum erneuten Hervorheben. |
| Modulkonfigurationsseite | Produkt-Aktualisierungsdatum ändern | Aktuelles `date_upd` des Produkts | Legt ein neues Datum der letzten Aktualisierung fest. Beeinflusst die Sortierung nach „Zuletzt aktualisiert“. Empfohlen: Ein aktuelles Datum nach signifikanten Produktänderungen. |
| Modulkonfigurationsseite | Speichern-Schaltfläche | N/A | Wendet alle ausgewählten Datumsänderungen auf das Produkt in der Datenbank an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Datum geändert, aber das Produkt wird auf meiner Startseite nicht als „neu“ angezeigt. Was ist falsch?**
A1:

- **Cache leeren:** PrestaShop ist stark auf Caching angewiesen. Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Dies ist die häufigste Lösung.
- **Modulkonfiguration:** Überprüfen Sie die Einstellungen Ihres „Neue Produkte“-Moduls (z. B. „Block neue Produkte“ oder „Seite neue Produkte“). Stellen Sie sicher, dass es so konfiguriert ist, dass Produkte basierend auf ihrem Erstellungsdatum angezeigt werden und dass die Anzahl der Tage für „neue“ Produkte entsprechend eingestellt ist (z. B. 30 Tage). Wenn Sie das Erstellungsdatum eines Produkts älter als diesen Schwellenwert festlegen, wird es nicht als neu angezeigt.
- **Theme-Besonderheiten:** Einige Themes haben möglicherweise ihren eigenen Cache oder eine benutzerdefinierte Logik für „neue Produkte“. Wenn das Leeren des Caches nicht funktioniert, konsultieren Sie die Dokumentation oder den Support Ihres Themes.

**F2: Wirkt sich das Ändern des Produktdatums auf meine SEO aus?**
A2: Direkt, nein. Suchmaschinen wie Google konzentrieren sich hauptsächlich auf den Inhalt Ihrer Produktseite (Beschreibung, Bilder, Bewertungen) und externe Links, nicht auf interne PrestaShop-Produktdaten. Indirekt jedoch, wenn die Datumsänderung dazu führt, dass das Produkt als „neu“ erscheint und mehr internen Traffic oder Verkäufe generiert, kann dieses erhöhte Engagement im Laufe der Zeit die SEO positiv beeinflussen. Es geht mehr um Benutzererfahrung und Merchandising als um direkte SEO-Manipulation.

**F3: Kann ich Daten für mehrere Produkte gleichzeitig ändern (Massenbearbeitung)?**
A3: Dieses Modul ist für individuelle Produkt-Datumsänderungen konzipiert. Wenn Sie Daten für eine große Anzahl von Produkten in großen Mengen bearbeiten müssen, benötigen Sie normalerweise ein fortschrittlicheres Import-/Export-Tool oder ein benutzerdefiniertes Skript. Für einige Produkte ist die Bearbeitung einzeln mit diesem Modul effizient.

**F4: Was passiert, wenn ich ein zukünftiges Datum festlege?**
A4: PrestaShop akzeptiert ein zukünftiges Datum. Die praktische Auswirkung könnte jedoch begrenzt sein. Ein Produkt mit einem zukünftigen Erstellungsdatum wird möglicherweise erst dann in „neue Produkte“-Listen angezeigt, wenn dieses Datum erreicht ist. Es wird generell empfohlen, aktuelle oder vergangene Daten zu verwenden.

**F5: Ich habe das Datum geändert, aber wenn ich das Produkt im Back Office bearbeite, ist das alte Datum immer noch vorhanden.**
A5: Dieses Modul ändert direkt die Felder `date_add` und `date_upd` in der Datenbank. Wenn Sie ein Produkt auf der Standard-PrestaShop-Produktbearbeitungsseite anzeigen, sollten diese Änderungen widergespiegelt werden. Wenn dies nicht der Fall ist, stellen Sie sicher, dass Sie in der Modulkonfiguration auf „Speichern“ geklickt, Ihren PrestaShop-Cache geleert und die Produktbearbeitungsseite neu geladen haben. Wenn das Problem weiterhin besteht, könnte ein Konflikt mit einem anderen Modul oder ein tieferes Caching-Problem vorliegen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Übersicht)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul `Product date change` (`pdc`) ist ein unkompliziertes PrestaShop-Modul, das für die direkte Interaktion mit dem `Product` ObjectModel entwickelt wurde. Es nutzt die Standardmethode `getContent()` für seine Back Office-Konfiguration und bietet ein einfaches Formular zur Auswahl eines Produkts und zur Änderung seiner Felder `date_add` und `date_upd`. Es führt keine neuen Datenbanktabellen, komplexen Controller oder umfangreiche Front-Office-Logik ein, wodurch es leichtgewichtig und auf seine zentrale administrative Aufgabe konzentriert ist.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Logik ist in der `getContent()`-Methode der Hauptmoduldatei gekapselt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder ObjectModels im Verzeichnis `classes/` ein. Es interagiert direkt mit PrestaShops Kern-`Product`-ObjectModel.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Das Styling wird voraussichtlich durch die Standard-Back Office-Styles von PrestaShop gehandhabt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`pdc/views/pdc.tpl`**:
  - **Umfang**: Back-Office-Admin-Konfiguration.
  - **Zweck**: Dieses Template rendert das Hauptkonfigurationsformular für das Modul. Es enthält:
    - Ein Suchfeld zum Finden von Produkten.
    - Anzeigebereiche für das aktuelle `date_add` und `date_upd` des ausgewählten Produkts.
    - Eingabefelder (wahrscheinlich Datumsauswähler) zum Festlegen neuer `date_add`- und `date_upd`-Werte.
    - Eine Absende-Schaltfläche zum Speichern der Änderungen.
  - **Verwendung**: Dieses Template wird von der `getContent()`-Methode des `pdc`-Moduls gerendert.
  - **Schlüsselselektoren**: Entwickler können den generierten HTML-Code auf spezifische IDs oder Klassen überprüfen, um das Styling bei Bedarf zu überschreiben, obwohl dies für ein einfaches Admin-Formular normalerweise nicht erforderlich ist.

### 4.7 Datenbankschema & Hooks-Übersicht

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es ändert direkt die Spalten `date_add` und `date_upd` innerhalb der bestehenden Tabelle `ps_product` (und möglicherweise `ps_product_shop`, wenn kontextspezifische Daten verwaltet werden, obwohl die Modulbeschreibung eine direkte Produktobjektmodifikation impliziert).
  - Konfigurationswerte (falls vorhanden, obwohl keine explizit über die direkte Produktmanipulation hinaus aufgeführt sind) würden in `ps_configuration` gespeichert.
- **Registrierte Hooks-Tabelle**:
  Dieses Modul registriert keine spezifischen Hooks für die Front-Office-Anzeige oder Back-Office-Aktionen über den Standard `displayBackOfficeHeader` (für Assets, falls vorhanden) und `moduleRoutes` (falls benutzerdefinierte URLs benötigt würden, was bei diesem Modul nicht der Fall ist) hinaus. Seine primäre Interaktion erfolgt über die `getContent()`-Methode.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayBackOfficeHeader` | Wird im `<head>`-Bereich der Back Office-Seiten gerendert. | (Potenziell) Zum Einbinden notwendiger JS/CSS für die Konfigurationsseite des Moduls, obwohl in diesem Modul keine vorhanden sind. |
| `actionProductUpdate` | Wird nach der Aktualisierung eines Produkts ausgeführt. | Die interne Logik des Moduls zur Aktualisierung von Produktdaten könnte diesen Hook auslösen, aber das Modul selbst registriert sich nicht explizit, um darauf zu hören oder Aktionen basierend darauf auszuführen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Produkt-Datumsänderung“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.

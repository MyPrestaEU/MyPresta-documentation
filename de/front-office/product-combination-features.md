---
title: "Produktkombinationsmerkmale – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Produktkombinationsmerkmale“ von MyPresta.eu."
sidebar:
  label: "Produktkombinationsmerkmale – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product combination features auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-combination-features.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-combination-features/)
>
> ---


# Produktkombinationsmerkmale

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Produktkombinationsmerkmale“. Sie können darauf zugreifen, indem Sie zu **Module > Modul-Manager** navigieren, nach „Produktkombinationsmerkmale“ suchen und auf „Konfigurieren“ klicken.

#### **Merkmale für Kombinationen aktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Kernfunktionalität, einzigartige Merkmale Produktkombinationen zuzuweisen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Sie sehen einen neuen Abschnitt auf Ihren Produktbearbeitungsseiten (unter dem Tab „Module“), in dem Sie jeder Kombination spezifische Merkmale und deren Werte zuweisen können. Wenn Kunden eine Kombination im Front Office auswählen, wird das Datenblatt des Produkts dynamisch aktualisiert, um diese kombinationsspezifischen Merkmale anzuzeigen.
  - *Wenn deaktiviert:* Der Abschnitt zur Verwaltung von Kombinationsmerkmalen wird auf den Produktbearbeitungsseiten nicht angezeigt, und das Front Office zeigt unabhängig von der ausgewählten Kombination nur die Merkmale des Hauptprodukts an.
- **Empfohlener Wert:** **Aktiviert** (wenn Sie die primäre Funktion des Moduls nutzen möchten).
- **Händlerszenario / Beispiel:** Wenn Sie T-Shirts verkaufen und „Material: 100 % Baumwolle“ für das weiße Hemd und „Material: 50 % Baumwolle, 50 % Polyester“ für das graue Hemd wünschen, müssen Sie dies *aktivieren*.

#### **Datenblatt CSS-Klasse**

- **Was diese Einstellung bewirkt:** Hiermit können Sie eine CSS-Klasse oder HTML-Element-ID angeben, die das Modul beim Aktualisieren des Merkmalsbereichs auf der Produktseite ansprechen soll. Dies ist entscheidend, damit das Modul korrekt identifizieren kann, wo die kombinationsspezifischen Merkmale in Ihrem Theme angezeigt werden sollen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn korrekt eingestellt:* Das Modul findet das angegebene Element und fügt die Kombinationsmerkmale dynamisch darin ein oder aktualisiert sie.
  - *Wenn falsch eingestellt oder leer gelassen:* Die Kombinationsmerkmale werden möglicherweise nicht im Front Office angezeigt oder erscheinen an einer unerwarteten Stelle, da das Modul nicht weiß, wo sie platziert werden sollen.
- **Empfohlener Wert:** Dies hängt vollständig von Ihrem PrestaShop-Theme ab. Eine gängige Klasse ist `.product-features` oder `.data-sheet`. Möglicherweise müssen Sie den HTML-Code Ihrer Produktseite überprüfen, um den richtigen Selektor zu finden. Im Zweifelsfall wenden Sie sich an Ihren Theme-Entwickler oder einen Webmaster.
- **Händlerszenario / Beispiel:** Ihr Theme zeigt Produktmerkmale in einem `div` mit der Klasse `product-specifications` an. Sie würden hier `.product-specifications` eingeben.

#### **Workflow**

- **Was diese Einstellung bewirkt:** Dies steuert, wie das Modul Merkmale behandelt, wenn eine Kombination ausgewählt wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Anhängen“ gesetzt:* Kombinationsspezifische Merkmale werden zu den Merkmalen des Hauptprodukts *hinzugefügt*. Sie sehen also sowohl die allgemeinen Produktmerkmale als auch die einzigartigen Kombinationsmerkmale.
  - *Wenn auf „Ersetzen“ gesetzt:* Kombinationsspezifische Merkmale *ersetzen* die Merkmale des Hauptprodukts. Es werden nur die Merkmale angezeigt, die für die ausgewählte Kombination relevant sind.
- **Empfohlener Wert:** **Ersetzen** für die meisten Fälle, da dies die präzisesten Informationen liefert. Wählen Sie „Anhängen“, wenn Sie allgemeine Merkmale haben, die für alle Kombinationen gelten, plus spezifische.
- **Händlerszenario / Beispiel:**
  - *Ersetzen:* Bei einem Laptop möchten Sie möglicherweise, dass „Prozessor: i7“, „RAM: 16 GB“ vollständig „Prozessor: i5“, „RAM: 8 GB“ ersetzt, wenn ein Kunde die i7/16 GB-Kombination auswählt.
  - *Anhängen:* Bei einem T-Shirt möchten Sie möglicherweise immer „Marke: MeineMarke“ anzeigen (allgemeines Merkmal), aber dann „Material: Bio-Baumwolle“ *hinzufügen*, wenn eine bestimmte Kombination ausgewählt wird.

#### **Beschreibungen für Kombinationen aktivieren**

- **Was diese Einstellung bewirkt:** Dies aktiviert oder deaktiviert die Möglichkeit, jeder Produktkombination einzigartige Beschreibungen zuzuweisen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Ein neues Feld erscheint auf Ihren Produktbearbeitungsseiten (unter dem Tab „Module“), das Ihnen ermöglicht, eine spezifische Beschreibung für jede Kombination einzugeben. Wenn Kunden eine Kombination auswählen, ersetzt diese Beschreibung dynamisch die Hauptproduktbeschreibung.
  - *Wenn deaktiviert:* Das Feld für die Kombinationsbeschreibung wird nicht angezeigt, und das Front Office zeigt immer die Beschreibung des Hauptprodukts an.
- **Empfohlener Wert:** **Aktiviert** (wenn Sie kombinationsspezifische Beschreibungen benötigen).
- **Händlerszenario / Beispiel:** Sie verkaufen individuellen Schmuck. Ein Produkt „Silberring“ könnte eine Kombination „Gravur: Ja“ haben. Sie könnten eine Kombinationsbeschreibung verwenden, um den Gravurprozess und die Zeichenbegrenzungen zu erklären, was für die Kombination „Gravur: Nein“ nicht relevant ist.

#### **CSS-Klasse / Objekt-ID der Beschreibung**

- **Was diese Einstellung bewirkt:** Ähnlich wie bei der „Datenblatt CSS-Klasse“ teilt dies dem Modul mit, welches HTML-Element auf Ihrer Produktseite die Hauptproduktbeschreibung enthält, die durch die kombinationsspezifische Beschreibung ersetzt werden soll.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn korrekt eingestellt:* Das Modul findet das angegebene Element und aktualisiert dessen Inhalt dynamisch mit der Kombinationsbeschreibung.
  - *Wenn falsch eingestellt oder leer gelassen:* Die Kombinationsbeschreibung wird möglicherweise nicht angezeigt oder erscheint an einer unerwarteten Stelle.
- **Empfohlener Wert:** Dies hängt von Ihrem Theme ab. Gängige Selektoren sind `.product-description`, `#description_short` oder `#product-description-short`. Sie müssen den HTML-Code Ihrer Produktseite überprüfen.
- **Händlerszenario / Beispiel:** Ihr Theme verwendet ein `div` mit der ID `product-description-full` für die Hauptbeschreibung. Sie würden hier `#product-description-full` eingeben.

#### **Meta-Titel für Kombinationen aktivieren**

- **Was diese Einstellung bewirkt:** Dies aktiviert oder deaktiviert die Möglichkeit, jeder Produktkombination einen einzigartigen Meta-Titel zuzuweisen. Dieser Meta-Titel erscheint im Browser-Tab und wird von Suchmaschinen verwendet.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Ein neues Feld erscheint auf Ihren Produktbearbeitungsseiten (unter dem Tab „Module“), das Ihnen ermöglicht, einen spezifischen Meta-Titel für jede Kombination einzugeben. Wenn ein Kunde eine Kombination auswählt, wird der Browser-Tab-Titel dynamisch aktualisiert.
  - *Wenn deaktiviert:* Das Feld für den Kombinations-Meta-Titel wird nicht angezeigt, und der Browser-Tab zeigt immer den Meta-Titel des Hauptprodukts an.
- **Empfohlener Wert:** **Aktiviert** (wenn Sie die SEO für spezifische Kombinationen verbessern oder klarere Browser-Tab-Titel bereitstellen möchten).
- **Händlerszenario / Beispiel:** Für ein Produkt „Smartphone“ könnten Sie eine Kombination „Farbe: Blau, Speicher: 128 GB“ haben. Sie könnten dessen Meta-Titel auf „Blaues Smartphone 128 GB – [Ihr Shop-Name]“ setzen, um die Sichtbarkeit in Suchmaschinen zu verbessern.

#### **Standard-Titelmodus**

- **Was diese Einstellung bewirkt:** Dies definiert, wie der Meta-Titel der Kombination erstellt wird, wenn Sie keinen explizit für eine Kombination festlegen oder wenn Sie den Produkttitel mit Kombinationsattributen kombinieren möchten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Produktname + Kombinationsname“ gesetzt:* Der Meta-Titel ist der Hauptproduktname, gefolgt von den Attributnamen der ausgewählten Kombination (z. B. „T-Shirt – Rot, Groß“).
  - *Wenn auf „Kombinationsname + Produktname“ gesetzt:* Der Meta-Titel ist die Attributnamen der ausgewählten Kombination, gefolgt vom Hauptproduktnamen (z. B. „Rot, Groß – T-Shirt“).
  - *Wenn auf „Kombinationsname“ gesetzt:* Es werden nur die Attributnamen der Kombination verwendet (z. B. „Rot, Groß“).
  - *Wenn auf „Produktname“ gesetzt:* Der Meta-Titel ist immer der Hauptproduktname, Kombinationen werden ignoriert.
- **Empfohlener Wert:** **„Produktname + Kombinationsname“** oder **„Kombinationsname + Produktname“** für eine gute Balance zwischen Produktidentität und Kombinationsspezifität.
- **Händlerszenario / Beispiel:** Sie verkaufen Schuhe. Wenn ein Kunde „Größe 10, Farbe Schwarz“ auswählt und „Produktname + Kombinationsname“ gewählt ist, wird der Titel zu „Laufschuhe – Größe 10, Schwarz“.

#### **Titel-Trennzeichen**

- **Was diese Einstellung bewirkt:** Hiermit können Sie das Zeichen oder die Zeichenfolge definieren, die zur Trennung der verschiedenen Teile des dynamisch generierten Meta-Titels verwendet wird (z. B. zwischen Produktname und Kombinationsname).
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „-“ gesetzt:* Der Titel könnte so aussehen: „Produktname - Kombination“.
  - *Wenn auf „|“ gesetzt:* Der Titel könnte so aussehen: „Produktname | Kombination“.
  - *Wenn leer gelassen:* Die Teile des Titels könnten ohne ein klares Trennzeichen zusammenlaufen.
- **Empfohlener Wert:** **-** (Bindestrich) oder **|** (Pipe) sind gängige und klare Trennzeichen.
- **Händlerszenario / Beispiel:** Wenn Ihr Standard-Titelmodus „Produktname + Kombinationsname“ ist und das Trennzeichen auf „|“ gesetzt ist, könnte ein Titel „Mein tolles T-Shirt | Rot, Groß“ lauten.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Dieses Modul erstellt keine dedizierten Top-Level-Admin-Bildschirme. Stattdessen integriert es sich direkt in die bestehende **Produktbearbeitungsseite** in Ihrem PrestaShop Back Office.

- **Bildschirmname & Menüpfad:**

  - Navigieren Sie zu **Katalog > Produkte**.
  - Bearbeiten Sie ein bestehendes Produkt oder erstellen Sie ein neues.
  - Auf der Produktbearbeitungsseite klicken Sie auf den Tab **„Module“**.
  - Sie finden einen neuen Abschnitt mit dem Titel **„Produktkombinationsmerkmale“** (oder ähnlich, je nach Modulversion/Übersetzungen).
- **Verfügbare Aktionen & Einstellungen:**

  - In diesem Abschnitt sehen Sie eine Liste aller für das aktuelle Produkt konfigurierten Kombinationen.
  - Für jede Kombination haben Sie Felder zum:
    - **Merkmale zuweisen:** Sie können bestehende Merkmale und deren Werte auswählen oder sogar neue Merkmalswerte speziell für diese Kombination erstellen. Das Modul unterstützt Multi-Merkmale, d.h. eine Kombination kann mehrere Werte für dasselbe Merkmal haben (z.B. „Material: Baumwolle, Material: Elasthan“).
    - **Kombinationsbeschreibung eingeben:** Ein Rich-Text-Editor (wie der Standard-PrestaShop-Beschreibungseditor) steht zur Verfügung, um eine einzigartige Beschreibung für diese Kombination einzugeben.
    - **Kombinations-Meta-Titel eingeben:** Ein Textfeld zur Eingabe eines einzigartigen Meta-Titels für diese Kombination.
  - **Änderungen speichern:** Denken Sie daran, den Haupt-„Speichern“-Button für das Produkt zu klicken, um alle kombinationsspezifischen Änderungen zu übernehmen.
- **Auswirkung der Änderungen:**

  - Alle Merkmale, Beschreibungen oder Meta-Titel, die Sie hier festlegen, werden in der Datenbank gespeichert und dynamisch auf der Front-Office-Produktseite angezeigt, wenn die entsprechende Kombination von einem Kunden ausgewählt wird.
  - Wenn Sie eine Kombination löschen, werden auch die zugehörigen Merkmale, Beschreibungen und Meta-Titel entfernt.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**

  1. Erstellen Sie zuerst Ihr Produkt und dessen Kombinationen wie gewohnt in PrestaShop (unter dem Tab „Kombinationen“).
  2. Sobald die Kombinationen erstellt sind, gehen Sie zum Tab **„Module“** auf der Produktbearbeitungsseite.
  3. Weisen Sie für jede Kombination sorgfältig die relevanten Merkmale zu, schreiben Sie eine spezifische Beschreibung und legen Sie einen optimierten Meta-Titel fest.
  4. Speichern Sie das Produkt.
  5. Testen Sie immer im Front Office, um sicherzustellen, dass die Merkmale, Beschreibungen und Titel korrekt aktualisiert werden, wenn Kombinationen ausgewählt werden.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Merkmale für Kombinationen aktivieren | Aktiviert | Hauptschalter für Kombinationsmerkmale. |
| Modulkonfiguration | Datenblatt CSS-Klasse | `.product-features` (Theme-abhängig) | CSS-Selektor, wo Kombinationsmerkmale angezeigt werden. |
| Modulkonfiguration | Workflow | Ersetzen | Wie Kombinationsmerkmale mit Hauptproduktmerkmalen interagieren (anhängen oder ersetzen). |
| Modulkonfiguration | Beschreibungen für Kombinationen aktivieren | Aktiviert | Hauptschalter für Kombinationsbeschreibungen. |
| Modulkonfiguration | CSS-Klasse / Objekt-ID der Beschreibung | `#product-description-short` (Theme-abhängig) | CSS-Selektor, wo Kombinationsbeschreibungen angezeigt werden. |
| Modulkonfiguration | Meta-Titel für Kombinationen aktivieren | Aktiviert | Hauptschalter für Kombinations-Meta-Titel. |
| Modulkonfiguration | Standard-Titelmodus | Produktname + Kombinationsname | Wie Meta-Titel generiert werden, wenn nicht explizit festgelegt. |
| Modulkonfiguration | Titel-Trennzeichen | `-` | Zeichen, das zur Trennung von Teilen des Meta-Titels verwendet wird. |
| Produktbearbeitungsseite > Module-Tab | Merkmale pro Kombination zuweisen | N/A | Einzigartige Merkmale und Werte jeder Kombination zuweisen. |
| Produktbearbeitungsseite > Module-Tab | Kombinationsbeschreibung | N/A | Einzigartige Rich-Text-Beschreibung für jede Kombination eingeben. |
| Produktbearbeitungsseite > Module-Tab | Kombinations-Meta-Titel | N/A | Einzigartigen Meta-Titel für jede Kombination eingeben. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kombinationsmerkmale/Beschreibungen werden auf der Produktseite nicht angezeigt.**
A:

1. **Modulkonfiguration prüfen:** Stellen Sie sicher, dass „Merkmale für Kombinationen aktivieren“ und/oder „Beschreibungen für Kombinationen aktivieren“ in der Modulkonfiguration aktiviert sind.
2. **CSS-Selektoren überprüfen:** Die Einstellungen „Datenblatt CSS-Klasse“ und „CSS-Klasse / Objekt-ID der Beschreibung“ sind entscheidend. Diese müssen exakt mit der CSS-Klasse oder ID der Elemente in Ihrem Theme übereinstimmen, wo die Merkmale/Beschreibung angezeigt werden. Verwenden Sie die Entwicklertools Ihres Browsers (F12), um Ihre Produktseite zu überprüfen und die korrekten Selektoren zu finden. Im Zweifelsfall wenden Sie sich an Ihren Theme-Entwickler.
3. **PrestaShop-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“. Manchmal verhindert alter Cache-Inhalt, dass neue Modulausgaben angezeigt werden.
4. **Produkteinstellungen prüfen:** Stellen Sie sicher, dass Sie tatsächlich Merkmale/Beschreibungen den spezifischen Kombinationen auf der Produktbearbeitungsseite unter dem Tab „Module“ zugewiesen haben.

**F: Die Kombinationsmerkmale/Beschreibungen werden angezeigt, sehen aber unformatiert oder fehl am Platz aus.**
A: Dies ist normalerweise ein CSS-Konflikt mit Ihrem Theme.

1. **Mit Browser-Tools überprüfen:** Verwenden Sie F12, um zu sehen, welche CSS-Regeln auf die Modulausgabe angewendet werden.
2. **CSS-Klasse anpassen:** Wenn die Modulausgabe in einem generischen `div` verpackt ist, müssen Sie möglicherweise die „Datenblatt CSS-Klasse“ oder „CSS-Klasse / Objekt-ID der Beschreibung“ an einen spezifischeren Container anpassen, den Ihr Theme bereits formatiert.
3. **Benutzerdefiniertes CSS:** Möglicherweise müssen Sie benutzerdefiniertes CSS zu Ihrem Theme-Stylesheet (oder über ein benutzerdefiniertes CSS-Modul) hinzufügen, um die Kombinationsmerkmale/Beschreibungen an das Aussehen Ihres Themes anzupassen.

**F: Meine Kombinations-Meta-Titel ändern sich nicht im Browser-Tab.**
A:

1. **Einstellung aktivieren:** Stellen Sie sicher, dass „Meta-Titel für Kombinationen aktivieren“ in der Modulkonfiguration aktiviert ist.
2. **Titel festlegen:** Stellen Sie sicher, dass Sie spezifische Meta-Titel für Ihre Kombinationen auf der Produktbearbeitungsseite eingegeben haben.
3. **Browser-Verhalten:** Einige Browser aktualisieren den Tab-Titel für bereits geöffnete Tabs möglicherweise nicht sofort. Versuchen Sie, die Produktseite in einem neuen Tab zu öffnen oder Ihren Browser-Cache zu leeren.
4. **SEO-Implikationen:** Während das Modul den clientseitigen Titel aktualisiert, müssen Suchmaschinen in der Lage sein, die dynamisch generierten Inhalte zu crawlen und zu indizieren, damit diese kombinationsspezifischen Titel übernommen werden. Stellen Sie sicher, dass Ihre Website crawlbar ist und überlegen Sie, ob diese dynamischen Titel für Ihre SEO-Strategie im Vergleich zu statischen Produkttiteln wirklich vorteilhaft sind.

**F: Kann ich dieses Modul mit mehrsprachigen Shops verwenden?**
A: Ja, das Modul unterstützt vollständig Mehrsprachigkeit. Wenn Sie Kombinationsmerkmale, Beschreibungen oder Meta-Titel auf der Produktseite bearbeiten, sehen Sie den Standard-PrestaShop-Sprachselektor, der Ihnen die Eingabe von Inhalten für jede Sprache ermöglicht.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Produktkombinationsmerkmale“ (`combfeat`) erweitert die Kernproduktverwaltung von PrestaShop, indem es benutzerdefinierte Felder und Logik in die Produktbearbeitungsseite des Back Office einfügt und Front-Office-Inhalte basierend auf ausgewählten Produktkombinationen dynamisch aktualisiert. Es nutzt das Hook-System von PrestaShop, um sich nahtlos zu integrieren, ohne Kerndateien zu ändern. Das Modul arbeitet hauptsächlich über JavaScript im Frontend für dynamische Updates und PHP im Backend für Konfiguration und Datenverwaltung. Es führt keine neuen Datenbanktabellen ein, sondern speichert seine Daten in bestehenden PrestaShop-Strukturen (wahrscheinlich `ps_product_attribute_feature` für Merkmale und `ps_product_attribute_lang` für Beschreibungen/Titel oder `ps_configuration` für Moduleinstellungen).

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Admin-Controller. Seine Logik zum Anzeigen und Speichern von Kombinationsdaten ist direkt in die Hauptmoduldatei `combfeat.php` und über JavaScript integriert.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Seine Kernlogik ist in der Hauptdatei `combfeat.php` enthalten und interagiert direkt mit den PrestaShop `Product`- und `Combination` (ProductAttribute) `ObjectModel`s.

### 4.4 JavaScript-Assets (`views/js/`)

- **`combfeat/views/js/acplt.js`**

  - **Geltungsbereich:** Wahrscheinlich Back-Office (Admin-Produktseite).
  - **Verantwortlichkeit:** Dieses Skript scheint eine benutzerdefinierte Autocomplete-Bibliothek oder eine Komponente zu sein, die zum Auswählen von Merkmalen und deren Werten für Kombinationen verwendet wird. Es würde AJAX-Anfragen zur Abfrage verfügbarer Merkmale und Werte verarbeiten und die Benutzeroberfläche zum Hinzufügen/Entfernen dieser aus einer Kombination verwalten.
  - **Schlüsselinteraktionen:** Event-Listener für Eingabefelder, AJAX-Aufrufe an einen Modul-Hook oder Admin-Controller für Daten, DOM-Manipulation zur Anzeige von Vorschlägen und ausgewählten Elementen.
- **`combfeat/views/js/admin-combfeat.js`**

  - **Geltungsbereich:** Back-Office (Admin-Produktseite, Tab „Module“).
  - **Verantwortlichkeit:** Dies ist das Hauptskript für die Funktionalität des Moduls innerhalb der PrestaShop Back Office Produktbearbeitungsseite. Es initialisiert die Felder für Kombinationsmerkmale, -beschreibungen und -meta-Titel. Es lauscht wahrscheinlich auf Änderungen in der Kombinationsauswahl (falls vorhanden) und verwaltet die Anzeige und Speicherung von Daten für jede Kombination.
  - **Schlüsselinteraktionen:** DOM-Manipulation zum Einfügen benutzerdefinierter Felder, Event-Listener für Eingabeänderungen, potenziell AJAX-Aufrufe zum Speichern kombinationsspezifischer Daten.
- **`combfeat/views/js/combfeat-append.js`**

  - **Geltungsbereich:** Front-Office (Produktseite).
  - **Verantwortlichkeit:** Dieses Skript ist speziell für die Workflow-Option „Anhängen“. Wenn eine Kombination ausgewählt wird, ruft es dynamisch die kombinationsspezifischen Merkmale ab und *fügt* sie den vorhandenen Produktmerkmalen im Frontend hinzu.
  - **Schlüsselinteraktionen:** Lauscht auf `updateProduct` oder ähnliche Ereignisse (ausgelöst durch Kombinationsauswahl), AJAX-Aufrufe zum Abrufen von Kombinationsdaten, DOM-Manipulation zum Anhängen von Merkmalen an das durch `combfeat_ds` angegebene Element.
- **`combfeat/views/js/combfeat-title.js`**

  - **Geltungsbereich:** Front-Office (Produktseite).
  - **Verantwortlichkeit:** Dieses Skript handhabt die dynamische Aktualisierung des Meta-Titels des Browsers basierend auf der ausgewählten Produktkombination.
  - **Schlüsselinteraktionen:** Lauscht auf `updateProduct` oder ähnliche Ereignisse, ruft den Meta-Titel der Kombination ab (entweder benutzerdefiniert oder basierend auf Moduleinstellungen generiert) und aktualisiert `document.title`.
- **`combfeat/views/js/combfeat.js`**

  - **Geltungsbereich:** Front-Office (Produktseite).
  - **Verantwortlichkeit:** Dies ist das primäre Front-Office-Skript für das Modul. Es orchestriert die dynamische Anzeige von kombinationsspezifischen Merkmalen und Beschreibungen. Es lauscht wahrscheinlich auf Änderungen in Produktkombinationen (z. B. Attributauswahl) und löst Aktualisierungen der relevanten DOM-Elemente aus. Dieses Skript würde den „Ersetzen“-Workflow für Merkmale und die Beschreibungsaktualisierung handhaben.
  - **Schlüsselinteraktionen:** Lauscht auf `updateProduct` oder ähnliche Ereignisse (z. B. `prestashop.on('updatedProduct', ...) `), AJAX-Aufrufe zum Abrufen von Kombinationsdaten, DOM-Manipulation zum Aktualisieren der durch `combfeat_ds` und `combfeat_description` angegebenen Elemente.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`combfeat/views/css/combfeat.css`**
  - **Geltungsbereich:** Sowohl Front-Office als auch Back-Office.
  - **Verantwortlichkeit:** Bietet grundlegendes Styling für die vom Modul eingefügten Elemente. Dies könnte Styling für die Eingabefelder für Kombinationsmerkmale/-beschreibungen im Back Office oder für die dynamisch aktualisierten Merkmals-/Beschreibungsblöcke im Front Office umfassen.
  - **Wichtige CSS-Klassenselektoren:** Zielt wahrscheinlich auf Klassen ab, die von den Modul-Templates und JavaScript verwendet werden, wie z. B. `.combfeat-feature-list`, `.combfeat-description-wrapper` oder spezifische Stile für die Autocomplete-Komponente. Entwickler müssen diese möglicherweise in der `custom.css` oder `theme.css` ihres Themes überschreiben, um eine perfekte Integration zu gewährleisten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`combfeat/views/templates/admin/combfeat.tpl`**

  - **Geltungsbereich:** Admin-Template.
  - **Verantwortlichkeit:** Dieses Template rendert den benutzerdefinierten Abschnitt innerhalb des Tabs „Module“ auf der Produktbearbeitungsseite im Back Office. Es zeigt die Benutzeroberfläche zur Verwaltung von kombinationsspezifischen Merkmalen, Beschreibungen und Meta-Titeln an. Es iteriert wahrscheinlich durch alle Produktkombinationen und stellt Eingabefelder für jede bereit.
  - **Schlüsselelemente:** Schleifen für Kombinationen, Eingabefelder für die Merkmalsauswahl (möglicherweise unter Verwendung der `acplt.js`-Komponente), Rich-Text-Editor für Beschreibungen, Texteingabe für Meta-Titel.
- **`combfeat/views/templates/hook/product-details.tpl`**

  - **Geltungsbereich:** Front-Office-Hook-Template.
  - **Verantwortlichkeit:** Dieses Template ist wahrscheinlich in `displayProductAdditionalInfo` oder ähnliche Hooks eingehängt, um die kombinationsspezifischen Merkmale und/oder Beschreibungen auf der Front-Office-Produktseite zu rendern. Es bietet die HTML-Struktur, die `combfeat.js` und `combfeat-append.js` dynamisch füllen und aktualisieren werden.
  - **Schlüsselelemente:** Platzhalter (z. B. leere `div`s mit spezifischen IDs oder Klassen), in die die Kombinationsmerkmale und -beschreibungen von JavaScript eingefügt werden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine neuen benutzerdefinierten Tabellen. Es speichert kombinationsspezifische Merkmale wahrscheinlich durch Erweiterung der `ps_product_attribute_feature`-Beziehung oder ähnliches, und Kombinationsbeschreibungen/-meta-Titel in `ps_product_attribute_lang` oder einer ähnlichen Struktur, die sie mit `id_product_attribute` und `id_lang` verknüpft.
  - Modulkonfigurationseinstellungen (`combfeat_ds`, `combfeat_description` usw.) werden in der Tabelle `ps_configuration` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Geltungsbereich | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- | --- |
| `displayHeader` | Front-Office | Im `<head>`-Bereich aller Front-Office-Seiten. | Registriert Front-Office-CSS- und JS-Assets (`combfeat.css`, `combfeat.js`, `combfeat-append.js`, `combfeat-title.js`). |
| `DisplayHeader` | Front-Office | Alias für `displayHeader`. | Gleich wie `displayHeader`. |
| `displayProductAdditionalInfo` | Front-Office | Auf der Produktseite, typischerweise unterhalb der Hauptproduktinformationen. | Rendert das `product-details.tpl`-Template und stellt einen Platzhalter für Kombinationsmerkmale/-beschreibungen bereit. |
| `ActionAdminControllerSetMedia` | Back-Office | Wenn ein Admin-Controller geladen und seine Medien-Assets gesetzt werden. | Registriert Back-Office-CSS- und JS-Assets (`combfeat.css`, `acplt.js`, `admin-combfeat.js`) für die Produktbearbeitungsseite. |
| `ActionProductUpdate` | Back-Office | Nach der Aktualisierung eines Produkts (einschließlich Kombinationen). | Potenziell zum Speichern oder Synchronisieren kombinationsspezifischer Daten beim Absenden des Produktformulars verwendet. |
| `actionProductUpdate` | Back-Office | Alias für `ActionProductUpdate`. | Gleich wie `ActionProductUpdate`. |
| `displayAdminProductsExtra` | Back-Office | Auf der Produktbearbeitungsseite, typischerweise als neuer Tab oder Abschnitt. | Rendert das `admin/combfeat.tpl`-Template und erstellt den Abschnitt „Produktkombinationsmerkmale“ unter dem Tab „Module“. |
| `DisplayAdminProductsExtra` | Back-Office | Alias für `displayAdminProductsExtra`. | Gleich wie `displayAdminProductsExtra`. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Produktkombinationsmerkmale“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.

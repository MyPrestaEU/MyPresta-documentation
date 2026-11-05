---
title: "Google Merchant Center Feed - Anleitung für den Händler"
sidebar:
  label: "Google Merchant Center Feed - Anleitung für den Händler"
description: "So konfigurieren Sie die Produktdatei für Google Merchant Center, und was Sie tun, wenn diese Datei fehlschlägt."
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Google merchant center feed auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/google-merchant-center-feed/)
>
> ---


## 1. Anforderungen

Das Modul läuft auf PrestaShop 1.6, 1.7, 8 und 9 und auf PHP 5.6 bis 8.5.

Der Server braucht cURL und JSON. Ein anderes Modul braucht es nicht.

Bei Zehntausenden von Produkten dauert das Öffnen der Dateiadresse länger und braucht mehr Speicher.

Das Konto bei Google Merchant Center legen Sie selbst an.

## 2. Installation

1. Laden Sie das Modul unter **Module**, **Modul-Manager** hoch und schalten Sie es ein.
2. Nach der Installation steht im **Katalog** der Eintrag **Google Merchant Feed**.
3. Das Modul leert bei der Installation keinen Cache.

Die Deinstallation nimmt nur den Eintrag im Katalog weg. Die Dateiliste, die Kategoriepaare, die auf dem Server gespeicherten Dateien und die Einstellung zum Kategoriebaum bleiben. Nach einer neuen Installation sind sie wieder da.

## 3. Konfiguration

Die Bilder stammen aus einem englischen Backoffice.

### 3.1 Seite der Moduleinstellungen

Öffnen Sie **Module**, **Modul-Manager**, **Google Merchant Center Feed**, **Konfigurieren**. Die Beschriftung auf diesem Bildschirm ist tschechisch. Die Überschrift lautet **Nastavení modulu**. Es gibt ein Feld.

![Moduleinstellungen](https://mypresta.eu/docs/images/docs/gmfeed-settings.webp)

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **Zobrazit strom kategorií** | **Ne** | **Ano** zeigt übergeordnete Kategorien, während Sie Google-Kategorien zuordnen. Es wählt keine Produkte für die Datei aus. |

Klicken Sie auf **Save**. Sie sehen **Nastavení bylo úspěšně uloženo**.

### 3.2 Dashboard

Öffnen Sie **Katalog**, **Google Merchant Feed**. Die Überschrift lautet **Google Merchant Center-Feeds**. Die Registerkarte heißt **Dashboard**.

![Dashboard](https://mypresta.eu/docs/images/docs/gmfeed-dashboard.webp)

Das Dashboard zeigt, wie viele Dateien gespeichert sind, wie oft heute jemand eine Adresse geöffnet hat, wie oft in den letzten 7 Tagen, und wie viele Dateien auf dem Server liegen. Diagramm und Liste der letzten Läufe bleiben leer, bis jemand eine Adresse öffnet. Unten steht die Liste der Dateien, die auf dem Server gespeichert werden.

### 3.3 Dateiliste

Die Registerkarte heißt **Feeds**.

![Feeds](https://mypresta.eu/docs/images/docs/gmfeed-feeds.webp)

Ist die Liste leer, sehen Sie **Sie haben noch keine Feeds**.

Gibt es Dateien, zeigt eine Zeile Status, Name, Shop, letzten Lauf und die Adresse. **Create new feed** steht über der Liste.

- Der Schalter schaltet eine Datei ein oder aus. Die Adresse bleibt.
- Eine Live-Datei hat eine Adresse. Google liest diese Adresse, und die Liste entsteht bei jedem Öffnen.
- Speichern auf dem Server hat zwei Adressen. Die Generierungsadresse baut die Liste und schreibt die Datei. In Google fügen Sie die Dateiadresse ein, nicht die Generierungsadresse. Liegt die Datei noch nicht da, öffnen Sie zuerst die Generierungsadresse.
- **Edit** öffnet das Formular. Eine Kopie hängt ein Kopierkennzeichen an den Namen. **Delete** fragt nach und nimmt die Zeile weg. Die Datei auf der Festplatte bleibt.

### 3.4 Updates

Die Registerkarte heißt **Updates**.

![Updates](https://mypresta.eu/docs/images/docs/gmfeed-updates.webp)

- **MyPresta-Updates**
- **Check Now** fragt einmal, ob es eine neuere Version gibt.
- Automatische Hinweise: **Enabled** oder **Disabled**. **Enabled** prüft etwa alle drei Tage und kann einen Hinweis im Backoffice zeigen.
- **Product Page** öffnet die Modulseite.
- **Save** speichert diese Einstellungen.

### 3.5 Dateiformular

Klicken Sie auf **Create new feed** oder **Edit**. Unten stehen **Save feed** und **Save & download**.

Das Bild zeigt den Anfang des Formulars.

![Dateiformular](https://mypresta.eu/docs/images/docs/gmfeed-form.webp)

Ein leerer Name wird beim Speichern zu **Unbenannter Feed**.

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **Feed name** | leer, erforderlich | Der Name in der Liste. |
| **Active** | **Yes** | **No** behält die Adresse. Beim Öffnen steht, dass die Datei aus ist. |
| **Shop** | der aktuelle Shop | Das Feld gibt es nur bei mehreren Shops. Die Adresse gilt im gewählten Shop. |

### 3.6 Katalogoptionen

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **Remember settings** | **Yes** | Die nächste neue Datei startet mit denselben Wahlen. Die eben gespeicherte Datei behält ihre eigenen. |

### 3.7 Was exportiert wird

Hier legen Sie fest, welche Datei Google liest, und ob die Liste bei jedem Öffnen entsteht oder als Datei auf dem Server liegt.

![Was exportiert wird](https://mypresta.eu/docs/images/docs/gmfeed-form-export.webp)

Lassen Sie **CSV**, außer Google muss XML bekommen. **Products** ist eine Zeile je Produkt. Die andere Wahl ist eine Zeile je Variante. Nur dann erscheint **Combination title**. **Save to file** auf **No** zeigt die Liste sofort und schreibt nichts auf die Platte. **Yes** speichert zusätzlich auf dem Server. Die Adresse aus der Liste enthält den Schlüssel schon. Ohne Schlüssel sehen Sie **Access denied**.

| Feld | Am Anfang | Was es tut |
|---|---|---|
| Dateityp | **CSV** | **CSV** oder **XML**. |
| Was exportiert wird | **Products** | **Products**: eine Zeile je Produkt. Die andere Wahl: eine Zeile je Variante. |
| **Save to file** | **No** | **No**: die Adresse zeigt die Liste sofort. **Yes**: die Liste wird zusätzlich auf dem Server gespeichert. Zum Schreiben muss die Adresse den Schlüssel von dieser Seite enthalten. Ohne Schlüssel sehen Sie **Access denied**. Im Backoffice angemeldet schreiben Sie die Datei ohne den Schlüssel. |
| **File name** | leer | Buchstaben, Ziffern, Bindestrich und Unterstrich bleiben. Ein leerer Name wird aus der Exportart gefüllt. |
| Wie das Produkt erkannt wird | Produkt-ID | Produkt-ID, Varianten-ID oder beides. Das ist die ID-Spalte in der Datei. |

### 3.8 Größe, Geschlecht, Farbe und Alter

Diese Spalten will Google bei Kleidung und Ähnlichem. Am Anfang sind sie aus. Schalten Sie eine Gruppe nur ein, wenn der Shop den Wert wirklich hat. Die weiteren Felder erscheinen, nachdem Sie die Gruppe auf **Yes** stellen.

![Größe, Geschlecht, Farbe und Alter](https://mypresta.eu/docs/images/docs/gmfeed-form-attributes.webp)

| Gruppe | Felder |
|---|---|
| Größe | exportieren oder nicht, Größenattribut, Standardwert |
| Geschlecht | exportieren oder nicht, Quelle, Merkmal, Attribut, Standard: male, female, unisex |
| Farbe | exportieren oder nicht, Quelle, Attribut, Merkmal, Standardwert |
| Alter | exportieren oder nicht, Quelle, Merkmal, Attribut, Standard: newborn, infant, toddler, kids, adult |

### 3.9 Dateieinstellungen

Hier steht der Inhalt einer Zeile: Kennungen, Versand, Beschreibungen, Namen, Lager, Bilder und Preise. Lassen Sie die Anfangswerte, wenn Google einen gewöhnlichen Katalog bekommen soll.

![Kennungen und Versand](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-a.webp)

**Include item_group_id** verbindet Varianten eines Produkts. **Unique product identifier** startet auf UPC. Die letzte Wahl lässt das Feld leer. **Include shipping price** fügt am Anfang nichts ein. Eine Berechnung je Position braucht mehr Serverleistung als ein fester Betrag.

![Versand, Beschreibungen und Name](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-b.webp)

![Format, Sprache und Lager](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-c.webp)

**Format name** lassen Sie unverändert, außer die Namen im Shop stehen in Großbuchstaben. Google nimmt das nicht an. **Delimiter** ist am Anfang ein senkrechter Strich.

![Bilder und Preise](https://mypresta.eu/docs/images/docs/gmfeed-form-feed-d.webp)

Währung und Land starten als Währung und Land des Shops. Das Bild zeigt die Werte des Testshops.

| Feld | Am Anfang | Was es tut |
|---|---|---|
| Gruppenkennung | **No** | Spalte, die Varianten eines Produkts zusammenhält. |
| Eindeutige Produktkennung | UPC | UPC, EAN-13, Referenz, MPN, ISBN oder leer. Leer heißt, die Kennung gibt es nicht. |
| Feld identifier_exists | **No** | Spalte, ob eine Kennung existiert. |
| Feld adult | nicht einfügen | Weglassen, als true einfügen oder als false einfügen. |
| Versandpreis | nicht einfügen | Je Position berechnet oder von Hand eingetragen. |
| Zusätzliche Versandkosten des Produkts | **No** | Rechnet die zusätzliche Versandgebühr von der Produktseite dazu. |
| Manueller Versandbetrag | 0 | Der Betrag, wenn der Versand manuell ist. |
| Zone für die Versandberechnung | die erste Zone | Die Zone, aus der der Versandpreis kommt. |
| Gewicht | **No** | Gewichtsspalte. |
| Produkttyp | **No** | Ihr eigener Kategoriepfad in der Datei. |
| Kategorie-ID an den Typ hängen | **No** | Die Kategorienummer neben dem Namen. |
| Kurzbeschreibung | Kurzbeschreibung | Kurzbeschreibung oder Langbeschreibung. |
| HTML aus Beschreibungen entfernen | **No** | **Yes** nimmt die Tags weg. |
| Produktname | Produktname | Oder der Meta-Titel. |
| Variantentitel | nur der Produktname | Der Name, der Name plus Variantenwert, oder der Name plus „Etikett: Wert“. |
| Namensformat | unverändert | Erster Buchstabe, jedes Wort oder nur Kleinbuchstaben. |
| Zeichen, die aus dem Namen fallen | leer | Die eingetragenen Zeichen verschwinden aus dem Namen. |
| Sprache | Shopsprache | Namen und Beschreibungen in der Datei. |
| Trennzeichen | senkrechter Strich | Das Zeichen zwischen den CSV-Spalten. |
| Anführungszeichen um Text | **No** | **Yes** setzt Felder in Anführungszeichen. |
| Lagerinfo | der echte Bestand | Alle auf Lager, alle nicht auf Lager, alle Nachbestellung, oder Nachbestellung als auf Lager. |
| Verfügbarkeitsdatum | leer | Das Datum für Nachbestellungen, wenn das Produkt kein eigenes hat. |
| Stückzahl | **No** | **Yes** setzt die Menge ein. |
| Marke, wenn keine da ist | Default | Der Markentext ohne Hersteller. |
| Bildgröße | Größen aus dem Shop | Welche Bildgröße in die Adresse kommt. |
| Produktbild, wenn die Variante keines hat | **No** | Für Varianten ohne eigenes Bild. |
| Wie viele Bilder | nur das Titelbild | Oder alle Bilder. |
| Währung | Shopwährung | Preise in der Datei. |
| Steuer im Preis | mit Steuer | Mit Steuer oder ohne. |
| Sonderpreise | **Yes** | Wenn die Dateiwährung nicht die Währung ist, in der Sie den Shop ansehen. |
| Preisgruppe | Besuchergruppe | Preise für diese Kundengruppe. |
| Grundpreis | **No** | Eine zusätzliche Spalte für den Grundpreis. |
| Preisland | Shopland | Das Land für Steuer und Rabatte. |

### 3.10 Ausgewählte Produkte

Lassen Sie **All**, wenn alle Hersteller, Lieferanten und Kategorien in die Datei sollen. Eine einzelne Wahl schneidet den Katalog zu. Sie ersetzt die Ausschlüsse darunter nicht.

![Hersteller, Lieferant und Kategorie](https://mypresta.eu/docs/images/docs/gmfeed-form-products.webp)

| Feld | Am Anfang | Was es tut |
|---|---|---|
| Hersteller | **All** | Ein Hersteller oder alle. |
| Lieferant | **All** | Ein Lieferant oder alle. |
| Kategorie | **All** | Eine Kategorie oder alle. |

### 3.11 Ausschlüsse

Hier fallen Produkte weg, die den Filter aus Punkt 3.10 überstanden haben. Am Anfang bleibt fast alles drin.

![Ausschlüsse](https://mypresta.eu/docs/images/docs/gmfeed-form-exclude.webp)

| Feld | Am Anfang | Was es tut |
|---|---|---|
| Kategorien zum Überspringen | leer | Tippen Sie einen Namen. Produkte aus dieser Kategorie fallen weg. |
| Produkte ohne Bild | **No** | **Yes** lässt Produkte ohne Bild weg. |
| Verfügbarkeit | alle Produkte | Oder nur die im Shop aktivierten. |
| Lager | alle Produkte | Oder nur die auf Lager. |
| Nach Referenz überspringen | aus | Schaltet einen Filter auf den Anfang der Referenz ein. Gilt auch für Varianten. |
| Anfang der Referenz | leer | Text, ab dem eine Referenz wegfällt. |
| Günstigere überspringen | aus | Eine Preisschwelle in der Shopwährung. |
| Schwellenbetrag | leer | Produkte unter diesem Betrag fallen weg. |
| Genannte Produkte | leer | Ein Suchfeld für Produkte, die wegfallen. |

### 3.12 Limit

Lassen Sie 0, wenn der ganze Katalog in eine Datei soll. Neben dem Feld steht die Produktzahl des Shops. Bei schwachem Hosting setzen Sie ein Limit und eine Teilnummer. Das Formular nennt das Beispiel: 3000 Produkte und Limit 1000 ergeben die Teile 1, 2 und 3.

![Limit und Shopcode](https://mypresta.eu/docs/images/docs/gmfeed-form-limit.webp)

| Feld | Am Anfang | Was es tut |
|---|---|---|
| Produktlimit | 0 | 0 oder leer heißt kein Limit. Die Produktzahl im Shop steht neben dem Feld. |
| Teil der Datei | 0 | Die Teilnummer, wenn Sie einen Katalog auf mehrere Dateien teilen. Bei 3000 Produkten und einem Limit von 1000 machen Sie die Teile 1, 2 und 3. |

### 3.13 Code des Ladengeschäfts

| Feld | Am Anfang | Was es tut |
|---|---|---|
| Shopcode einfügen | **No** | Eine Spalte für den Code des Ladengeschäfts. |
| Shopcode | leer | Derselbe Code wie in Google Business. Groß- und Kleinschreibung zählt. |

### 3.14 Google-Kategorien

Unten gibt es eine Zeile je Shopsprache. **Pair categories** öffnet die Zuordnung. **Synchronize** holt die Google-Liste für diese Sprache. Fehlt die Liste, ist die Schaltfläche rot. Auf dem Bild hat en-us die Datei, fr noch nicht.

![Google-Kategorien](https://mypresta.eu/docs/images/docs/gmfeed-form-categories.webp)

**Zobrazit strom kategorií** aus Punkt 3.1 ändert nur die Zeichnung dieser Liste. Unten stehen noch einmal **Save & download** und **Save feed**.

## 4. Shop-Frontend

Kunden sehen auf der Shopseite nichts. Es gibt keinen Block auf der Produktseite, im Warenkorb oder in der Fußzeile. Einen Shop-Screenshot gibt es nicht.

Es gibt eine Adresse, die Google oder ein Browser öffnet. Kopieren Sie sie aus der Liste. Setzen Sie sie nicht selbst zusammen.

Ein Live-Öffnen liefert CSV oder XML. Beim Speichern auf dem Server schreibt die Generierungsadresse die Datei, und die Adresse für Google ist die Dateiadresse.

Eigene Parameter ändern nichts. Das Modul nimmt die Einstellungen dieser Datei.

Das Speichern des Formulars schickt keine Produkte an Google. Die Liste entsteht beim Öffnen der Adresse.

| Was Sie beim Öffnen sehen | Was Sie tun |
|---|---|
| feed does not exists | Die Nummer stimmt nicht, oder die Datei wurde entfernt. Kopieren Sie die Adresse aus der Liste. |
| Feed is disabled | Schalten Sie **Active** ein. |
| Feed is not available in this store | Die Datei gehört zu einem anderen Shop. |
| Access denied | Speichern auf dem Server ist an, und in der Adresse fehlt der Schlüssel. Kopieren Sie die Adresse aus der Liste. |
| Invalid export path | Kürzen Sie den Dateinamen. |
| Unable to save export file | Prüfen Sie den Speicherplatz und das Schreibrecht im Modulordner. |

## 5. Probleme

**Google zeigt noch die Produkte von gestern.** Das Modul schickt nichts an Google. Öffnen Sie die Adresse und prüfen Sie die Liste. Rufen Sie die Datei danach im Merchant Center von Hand ab.

**In der Datei stehen fast keine Produkte.** Prüfen Sie, ob nur aktive Produkte, nur Produkte auf Lager, ein Hersteller, ein Lieferant, eine Kategorie, Ausschlüsse, ein Limit oder eine Teilnummer übrig sind.

**Der Kategoriebaum ist an, und die Datei hat dieselben Produkte.** Der Baum zeigt nur übergeordnete Kategorien beim Zuordnen.

**Ich habe das Modul entfernt, und die Liste ist weg.** Installieren Sie es erneut. Die Daten bleiben. Weg ist nur der Eintrag im Katalog.

**Ein großer Katalog bricht mittendrin ab.** Setzen Sie ein Limit und eine Teilnummer. Machen Sie mehrere Dateien.

## 6. Für Entwickler

### 6.1 Überblick

`gmfeed` 2.4.3. Die Klasse `gmfeed` erweitert `Module`. Der Name in der Modulliste ist die feste Zeichenkette `Google Merchant Center Feed`. Autor MyPresta.eu. Tab `administration`.

Das Formular speichert eine Zeile `gms`. Das Feld `conf` ist ein Query-String. Die Front-Adresse liest diese Zeile, baut CSV oder XML und beendet die Antwort. Speichern in eine Datei schreibt sie unter `/modules/gmfeed/`.

### 6.2 Dateien

- `gmfeed.php`: install, uninstall, die Konfigurationsseite, der Schreibschlüssel, Bereinigung von Name, Erweiterung und Typ.
- `controllers/admin/AdminExportProductsFeedGoogle.php`: Dashboard, Liste, Formular, Speichern.
- `controllers/front/feed.php`: Erzeugung. `initContent()` ruft `generateFeed()` und `die()`.
- `model/gms.php`: Dateizeile und Adresse. Klasse `gms`.
- `model/google.php`: Kategoriepaare. Klasse `pixelgoogle`.
- `lib/updateChecker.php`: Klasse `gmfeedUpdate`.
- `lib/searchTool/searchTool.php`: Vorschläge für Kategorien und Produkte.
- `views/templates/admin/`: `layout.tpl`, `dashboard.tpl`, `feeds.tpl`, `form-chrome.tpl`.
- `google/en-us.txt`: die Taxonomie. Erste Zeile `# Google_Product_Taxonomy_Version: 2015-02-19`.
- `.htaccess` im Modulordner blockiert PHP.

### 6.3 Controller

Admin: `AdminExportProductsFeedGoogle`, Elternteil `AdminCatalog`. Ansichten in `gmfeed_view`: `dashboard`, `feeds`, `form`, `updates`.

Front: `gmfeedfeedModuleFrontController`. Adresse `module/gmfeed/feed?feed=` plus die Nummer.

Der Schreibschlüssel ist HMAC-SHA256 aus `gmfeed.write.` und der Shop-ID, Geheimnis `_COOKIE_KEY_`. Ein angemeldeter Mitarbeiter schreibt ohne Schlüssel. Eingehende Parameter `export_` und `gmfeed_` werden verworfen und durch die gespeicherten ersetzt. Schlüssel und `debug_feed` bleiben.

Eine ausgeschaltete Datei liefert HTTP 503 und `Feed is disabled`. Ein leeres oder zu kurzes `conf` endet mit `feed does not exists`. Eine andere `id_shop` endet mit `Feed is not available in this store`.

### 6.4 Hooks

Es gibt einen Hook: `actionAdminControllerSetMedia`. Er lädt Fancybox und Autocomplete nur auf `AdminExportProductsFeedGoogle`. Das Modul stellt keine eigenen Hooks bereit. Es gibt kein `enable()` und kein `disable()`.

### 6.5 Overrides

Dieses Modul überschreibt keine PrestaShop-Klassen und keine Controller.

### 6.6 Datenbank

| Tabelle | Inhalt |
|---|---|
| `pixelgoogle` | Ein Kategoriepaar: `id_google`, `id_category`, `id_lang`, `value`. |
| `gms` | Eine Datei: `name`, `id_shop`, `conf`, `active`. `CREATE` setzt keinen Primärschlüssel. |
| `gms_log` | Ein Öffnen der Adresse: Zeit, Anzahl, Status, Dateischreiben, Name, Format, Quelle. |

`ensureSchema` auf der Katalogseite ergänzt `active` und `id_shop`, legt `gms_log` an, wenn sie fehlt, und füllt `id_shop` 0 mit dem Standardshop. Die Deinstallation löscht die Tabellen nicht.

### 6.7 Schlüssel und Übersetzungen

`pf_tree`: ein fehlender Schlüssel bedeutet aus. Der Rest des Formulars liegt in `gms.conf`. **Remember settings** als 1 kopiert die Felder zusätzlich nach `gm_{Feld}`, ohne Schreibschlüssel, Kurzlink, Aktiv, Shop und Datei-ID. Bei geöffneter Datei nimmt ein fehlendes Feld den Formularstandard, nicht die Kopie `gm_`. Ein älterer Schlüssel `notepad_products` wird nach `gmfeed_products` kopiert, wenn der neue fehlt.

Updates: `mypresta_updates`, `update_gmfeed` (172800 Sekunden zwischen den Prüfungen), `updatev_gmfeed`. Ein fehlendes `mkey` geht als `nokey`.

Eine neue Sprache ist eine Datei `translations/{iso}.php`. Texte aus `$this->l()` stammen aus der englischen Quelle. Der Name in der Modulliste geht nicht durch `$this->l()`. In `translations/de.php` sind die Texte der Konfigurationsseite tschechisch.

Der gespeicherte Exporttyp `product` wird beim Erzeugen als `products` behandelt. Erlaubte Dateiendungen sind `csv`, `xml` und `txt`. Das Formular zeigt CSV und XML.

### 6.8 Erweitern

Das Theme hat auf der Shopseite nichts zu überschreiben, weil das Frontend kein Template rendert. Ein anderes Spaltenlayout heißt, den Modulcode zu ändern. Eine Taxonomie in einer anderen Sprache legen Sie als `google/{code}.txt` dazu.

## 7. Support

Modulseite: [Google Merchant Center Feed](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html).

Um zu diesem Modul zu schreiben, melden Sie sich im Kundenkonto auf [mypresta.eu](https://mypresta.eu/) an, öffnen Sie den [Kontakt](https://mypresta.eu/contact.html) und wählen Sie das Thema **Support for paid modules**. Das Formular gibt an, dass die Anmeldung erforderlich ist. Nach der Anmeldung wählen Sie dieses Modul aus der Kaufhistorie.

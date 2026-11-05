---
title: "Microsoft Merchant Center Product Feed - Dokumentation und Benutzerhandbuch"
description: "Benutzerhandbuch für Personen, die das Modul bereits besitzen und Microsoft Merchant Center-Feeds konfigurieren oder Probleme bei der Feed-Erstellung und im Katalog beheben möchten."
sidebar:
  label: "Microsoft Merchant Center Product Feed - Dokumentation und Benutzerhandbuch"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Microsoft Merchant Center Product Feed auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-product-feed.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/microsoft-merchant-center-product-feed/)
>
> ---


## 1. Anforderungen

Stellen Sie vor der Installation sicher, dass Shop und Hosting diese Anforderungen erfüllen:

- PrestaShop 1.7, 8 oder 9.
- PHP 7.1 bis 8.5.
- PHP-Erweiterungen: cURL, JSON, hash und SimpleXML, wenn Sie XML-Feeds erzeugen.
- Ein aktives Microsoft Merchant Center-Konto, in dem Sie einen Katalog erstellen und dessen Feed-Adresse angeben können.
- Es ist kein weiteres PrestaShop-Modul erforderlich.

Ein großer Katalog benötigt genügend PHP-Ausführungszeit und Arbeitsspeicher, um Produkte zu erfassen, Preise und Versand zu berechnen und die Ausgabe zu erstellen. Wenn ein vollständiger Feed die Grenzen Ihres Hostings überschreitet, teilen Sie ihn mit **Limit number of products in feed** und **Part of feed** in kleinere Feeds auf.

## 2. Installation

1. Öffnen Sie **Modules → Module Manager**.
2. Klicken Sie auf **Upload a module** und laden Sie die ZIP-Datei des Moduls hoch.
3. Installieren Sie **Microsoft Merchant Center Feed**.
4. Öffnen Sie **Catalog → Microsoft Merchant Feed**. Dies ist der Arbeitsbereich zum Erstellen von Feeds, Kopieren von Katalogadressen, Überwachen von Läufen und Zuordnen von Kategorien.
5. Wenn Kategorienamen in verschiedenen Zweigen Ihres Katalogs mehrfach vorkommen, öffnen Sie **Modules → Module Manager**, suchen Sie das Modul, klicken Sie auf **Configure** und aktivieren Sie **Show categories tree**.

Bei der Installation wird der PrestaShop-Cache nicht geleert.

Um das Modul zu entfernen, deinstallieren Sie es im **Module Manager**. Die Deinstallation entfernt **Microsoft Merchant Feed** aus dem Menü **Catalog**, behält jedoch gespeicherte Feeds, Erstellungsverlauf, Kategoriezuordnungen, gemerkte Formulareinstellungen, erzeugte Katalogdateien und heruntergeladene Taxonomiedaten. Nach einer Neuinstallation kann das Modul diese Daten daher wiederverwenden.

## 3. Konfiguration und Backoffice-Arbeitsablauf

Veröffentlichen Sie einen Katalog wie folgt:

1. Öffnen Sie **Catalog → Microsoft Merchant Feed** und wählen Sie **Create new feed**.
2. Geben Sie einen **Feed name** ein, lassen Sie **Active** auf **Yes**, wählen Sie Ausgabe- und Produktoptionen, ordnen Sie **Microsoft Categories** zu und klicken Sie auf **Save feed**.
3. Wählen Sie eine Veröffentlichungsmethode:
   - Lassen Sie für einen Live-Feed **Save to file** auf **No**. Kopieren Sie die **Live catalog URL**. Microsoft ruft diese Adresse ab, und das Modul erzeugt den Feed bei jedem Abruf neu.
   - Setzen Sie für eine statische Datei **Save to file** auf **Yes**. Rufen Sie die geheime **Generate / cron URL** manuell oder über einen Scheduler auf. Kopieren Sie nach der ersten erfolgreichen Erstellung die **Catalog file URL**. Übermitteln Sie Microsoft Merchant Center die Katalogdateiadresse, niemals die Erstellungsadresse.
4. Erstellen oder öffnen Sie den passenden Katalog in Microsoft Merchant Center und fügen Sie die kopierte Live- oder Katalogdateiadresse als Feed-Quelle ein.
5. Kehren Sie zum **Dashboard** zurück und prüfen Sie, ob Läufe erfasst werden und bei Verwendung des Dateimodus eine gespeicherte Datei bereitsteht.
6. Öffnen Sie im Feed den Bereich **Microsoft Categories**, synchronisieren Sie die Taxonomie für die Feed-Sprache und verbinden Sie mit **Pair categories** die Shop-Kategorien mit den Microsoft-Shopping-Kategorien.
7. Um die Veröffentlichung ohne Änderung der Adresse anzuhalten, schalten Sie den Feed unter **Feeds** aus. **Active** auf **No** stoppt die Erstellung; das erneute Einschalten setzt denselben Feed unter derselben Adresse fort.

Die Screenshots in diesem Handbuch stammen aus einem englischen Backoffice.

### 3.1 Moduleinstellungen

Öffnen Sie **Modules → Module Manager**, suchen Sie **Microsoft Merchant Center Feed** und klicken Sie auf **Configure**.

![Moduleinstellungen mit Show categories tree](https://mypresta.eu/docs/images/docs/mmcfeed-module-settings.webp)

| Feld | Ausgangswert | Funktion |
|---|---|---|
| **Show categories tree** | No | Der Feed-Arbeitsbereich befindet sich unter **Catalog → Microsoft Merchant Feed**. Dort können Sie Shop-Kategorien Microsoft-Shopping-Kategorien zuordnen. Setzen Sie dieses Feld auf **Yes**, um im Zuordnungsfenster den übergeordneten Pfad jeder Kategorie anzuzeigen. Dadurch lassen sich Kategorien mit gleichem Namen unterscheiden. Klicken Sie auf **Save**; die Seite bestätigt **Settings saved properly**. |

### 3.2 Feed-Liste

Öffnen Sie **Catalog → Microsoft Merchant Feed** und wählen Sie **Feeds**.

![Feed-Liste](https://mypresta.eu/docs/images/docs/mmcfeed-feeds.webp)

Wenn noch kein Feed existiert, zeigt die Seite **You have no feeds yet** und **Create your first feed**. Andernfalls stehen diese Spalten zur Verfügung:

| Spalte | Anzeige |
|---|---|
| **Status** | **On** oder **Off**. Mit dem Schalter halten Sie den Feed an oder setzen ihn fort, ohne ihn zu löschen oder seine Adresse zu ändern. |
| **Feed** | Feed-Name sowie Kennzeichen für Dateiformat, Produkt- oder Variantenexport, Sprache und Modus **Live** oder **File**. |
| **Shop** | Der Shop, zu dem der Feed gehört. Im Multistore wird ein Feed außerhalb des aktuellen Shops mit **Not available in this store** gekennzeichnet. |
| **Last run** | Anzahl der erzeugten Artikel und Zeitpunkt des letzten Laufs. Vor dem ersten Aufruf erscheinen **Never** und **No cron call yet**. |
| **Catalog URL** | Im Live-Modus die Adresse **Live catalog**. Im Dateimodus die geheime Adresse **Generate / cron** und die öffentliche Adresse **Catalog file**. Kopieren Sie die Adresse mit der benachbarten Schaltfläche. |
| **Actions** | Die für den Feed verfügbaren Befehle. |

Verwenden Sie die Aktionen wie folgt:

- **Edit** öffnet alle gespeicherten Optionen.
- **Duplicate** erstellt eine Kopie und öffnet sie zur Prüfung. Ändern Sie vor dem Speichern Name, Dateiname, Shop, Filter oder andere Einstellungen, wenn die Kopie unabhängig sein soll.
- **Generate** ruft im Dateimodus den Generator auf.
- **Open file** öffnet im Dateimodus die gespeicherte Datei.
- **Open** erzeugt und öffnet einen Live-Feed.
- **Delete** löscht den Feed-Datensatz nach Bestätigung dauerhaft.

Nach einem Vorgang kann die Seite folgende Meldungen anzeigen:

- **Feed saved. Its catalog URL is ready to use.**
- **Feed removed.**
- **Feed duplicated. Review the copy and save if you need a different filename or URL.**

### 3.3 Dashboard

Wählen Sie **Dashboard**, um die Feed-Aktivität zu überwachen.

![Dashboard](https://mypresta.eu/docs/images/docs/mmcfeed-dashboard.webp)

Die Zusammenfassung zeigt **Saved feeds**, erfolgreiche **Cron runs today**, heute erzeugte Produkte, **Runs last 7 days**, die durchschnittliche Erstellungsdauer und die Anzahl bereiter **Saved files**. **Catalog generation activity** stellt die letzten 14 Tage dar. **Recent runs** listet Feed, Zeitpunkt, Artikelanzahl, Dauer, Format und Angabe, ob eine Datei geschrieben wurde.

Die Tabelle **Generated files** zeigt jeden Feed im Dateimodus mit Shop, Dateiname, Größe, Status und letzter Aktualisierung. **Waiting for first cron** bedeutet, dass der Feed gespeichert ist, die Erstellungsadresse seine Datei aber noch nicht erzeugt hat. **On disk** bedeutet, dass die Datei unter ihrer Katalogdateiadresse verfügbar ist.

### 3.4 Registerkarte Updates

Wählen Sie **Updates**, um das installierte Modul mit den MyPresta-Updates zu vergleichen.

![Registerkarte Updates](https://mypresta.eu/docs/images/docs/mmcfeed-updates.webp)

| Feld | Ausgangswert | Funktion |
|---|---|---|
| **Manual Check** | Kein Ergebnis bis zur Prüfung | Klicken Sie nach der Installation oder wenn Sie eine neue Version erwarten auf **Check Now**. Das Modul kontaktiert einmal den Update-Dienst, vergleicht die Versionen und meldet sofort **Module is up to date!** oder **New version available!**. |
| **Automatic Notifications** | Aktuelle gemeinsame MyPresta-Update-Einstellung | Setzen Sie **Enabled**, um im Backoffice ungefähr alle drei Tage zu prüfen und Mitarbeiter bei einer neueren Version zu warnen. Wählen Sie **Disabled**, wenn Sie manuell prüfen. Klicken Sie zum Übernehmen auf **Save**. |
| **Product Page** | Link verfügbar | Öffnen Sie die offizielle Modulseite, um Modul- und Supportinformationen aufzurufen. Es ist keine Einstellung erforderlich. |

### 3.5 Feed erstellen/bearbeiten

Wählen Sie **Create new feed** oder klicken Sie neben einem vorhandenen Feed auf **Edit**. Die Felder erscheinen in der folgenden Bildschirmreihenfolge. Als shopabhängig bezeichnete Optionen stammen aus den in PrestaShop konfigurierten Sprachen, Währungen, Ländern, Gruppen, Bildtypen, Merkmalen, Attributen, Kategorien, Herstellern, Lieferanten, Zonen und Shops.

Klicken Sie auf **Save feed**, um zu speichern und zur Liste zurückzukehren. Mit **Save & download** speichern Sie die Einstellungen und laden sofort eine neu erzeugte CSV- oder XML-Datei herunter. Beim Bearbeiten zeigt die Seite außerdem die passende **Live catalog URL** beziehungsweise **Generate / cron URL** und **Catalog file URL**.

![Feed erstellen oder bearbeiten: Name, Status, Format, Typ und Dateimodus](https://mypresta.eu/docs/images/docs/mmcfeed-form-top.webp)

**Feed-Identität und Ausgabe**

| Feld | Ausgangswert | Funktion |
|---|---|---|
| **Feed name** | Leer | Geben Sie einen erforderlichen, aussagekräftigen Namen für die Feed-Liste ein. Erreicht eine leere Übermittlung den Speichervorgang, wird sie als **Untitled feed** gespeichert. |
| **Active** | Yes | Aktiviert lassen, um die Erstellung zuzulassen. Mit **No** halten Sie den Feed an und behalten Adresse und Einstellungen. |
| **Shop** | Aktueller Shop; nur im Multistore sichtbar | Weisen Sie den Feed einem Shop zu. Seine Katalogadresse funktioniert nur für diesen Shop. |
| **Remember settings** | Yes | Speichert die Formularauswahl als Startwerte für den nächsten neuen Feed. Wählen Sie **No**, wenn die Auswahl dieses Feeds nicht als Standard gespeichert werden soll. |
| **Type of file module will generate** | CSV | Wählen Sie **CSV** für einen Text-Feed oder **XML** für einen Atom-Shopping-Feed. Für TSV wählen Sie **CSV** und setzen **Delimiter** auf `Tab`; TSV ist eine CSV-Ausgabe mit Tabulator als Trennzeichen. |
| **What you want to export?** | Products | Wählen Sie **Products** für eine Zeile pro Produkt oder **All products variants**, um Kombinationen getrennt zu exportieren. |
| **Save to file** | No | **No** erzeugt den Feed live und gibt ihn bei jedem Aufruf seiner Katalogadresse zurück. **Yes** lässt die Erstellungsadresse eine statische Datei schreiben; planen Sie diese geheime Adresse und übermitteln Sie Microsoft die getrennte Katalogdateiadresse. |
| **File name** | Leer | Geben Sie bei aktiviertem **Save to file** den Basisnamen der statischen Feed-Datei ein. Bleibt das Feld leer, verwendet das Modul den Exporttyp. Buchstaben, Zahlen, Bindestriche und Unterstriche ergeben einen vorhersehbaren Namen. |
| **How to identify product?** | `id_product` | Wählen Sie `id_product`, `id_combination` oder `id_product-id_attribute`. Dieser Wert wird zur eindeutigen Artikel-ID im Feed. Verwenden Sie beim getrennten Variantenexport eine kombinationsfähige Auswahl. |

**Größe, Geschlecht, Farbe und Altersgruppe**

![Felder für Größe, Geschlecht, Farbe und Alter](https://mypresta.eu/docs/images/docs/mmcfeed-form-attributes.webp)

| Feld | Ausgangswert | Funktion |
|---|---|---|
| **Export size** | No | Setzen Sie auf **Yes**, um das Feld `size` einzuschließen. |
| **Size attribute** | None | Wählen Sie die Produktattributgruppe mit der Größe. Halten Sie beim Klicken Strg gedrückt, um mehrere Gruppen auszuwählen. Produkte ohne gewählten Größenwert verwenden **Default size value**. |
| **Default size value** | Leer | Geben Sie die Ersatzgröße ein, wenn ein Produkt in der gewählten Attributgruppe keinen Wert besitzt. |
| **Export gender** | No | Setzen Sie auf **Yes**, um das Feld `gender` einzuschließen. |
| **Export gender value from** | Keine Quelle gewählt | Wählen Sie **Attribute** oder **Feature** als Quelle der Geschlechtsangabe und füllen Sie das passende Quellfeld aus. |
| **Gender feature** | Kein Merkmal gewählt | Wählen Sie bei Quelle **Feature** das Produktmerkmal, das das Geschlecht speichert. |
| **Gender attribute** | Kein Attribut gewählt | Wählen Sie bei Quelle **Attribute** die Produktattributgruppe, die das Geschlecht speichert. |
| **Default gender value** | Leer | Wählen Sie **Male**, **Female** oder **Unisex** als Ersatz, wenn das Produkt über die gewählte Quelle keinen Geschlechtswert liefert. |
| **Export color** | No | Setzen Sie auf **Yes**, um das Feld `color` einzuschließen. |
| **Export color value from** | Keine Quelle gewählt | Wählen Sie **Attribute** oder **Feature** als Quelle der Farbangabe. |
| **Color attribute** | Kein Attribut gewählt | Wählen Sie bei Quelle **Attribute** die Produktattributgruppe mit der Farbe. |
| **Color feature** | Kein Merkmal gewählt | Wählen Sie bei Quelle **Feature** das Produktmerkmal mit der Farbe. |
| **Default color value** | Leer | Geben Sie den Ersatz ein, wenn die gewählte Farbquelle leer ist. Verwenden Sie englische Farbnamen, da Microsoft für dieses Feld englische Namen akzeptiert. |
| **Export age_group** | No | Setzen Sie auf **Yes**, um das Feld `age_group` einzuschließen. |
| **Export age group value from** | Keine Quelle gewählt | Wählen Sie **Attribute** oder **Feature** als Quelle der Altersgruppe. |
| **age group feature** | Kein Merkmal gewählt | Wählen Sie bei Quelle **Feature** das Produktmerkmal mit der Altersgruppe. |
| **age group attribute** | Kein Attribut gewählt | Wählen Sie bei Quelle **Attribute** die Produktattributgruppe mit der Altersgruppe. |
| **Default age group value** | Kein Ersatz gewählt | Wählen Sie den Ersatz bei fehlendem Quellwert: **adult**, **kids**, **toddler**, **infant** oder den angezeigten Wert **newbord**. Verwenden Sie für Produktionsdaten die von Microsoft akzeptierten Altersgruppenwerte. |

**Feed-Felder, Versand, Text, Bestand, Bilder und Preise**

![Feed-Einstellungen mit Kennungen, Versand, Beschreibungen, Sprache und Trennzeichen](https://mypresta.eu/docs/images/docs/mmcfeed-form-feed-settings.webp)

| Feld | Ausgangswert | Funktion |
|---|---|---|
| **Include item_group_id** | No | Mit **Yes** gruppieren Sie Varianten, die sich etwa durch Größe, Farbe, Muster, Altersgruppe oder Geschlecht unterscheiden. Microsoft behandelt sie dadurch als Varianten eines Produkts statt als unabhängige Angebote. |
| **Unique product identifier** | Product UPC barcode | Wählen Sie das Produktfeld für GTIN- oder Kennungsdaten: **Product UPC barcode**, **Product ean13 / JAN barcode**, **Product reference number**, **Product MPN code**, **Product ISBN code** oder **Make this field empty, identifier_exists field will have value false then**. Geben Sie verfügbare Herstellerkennungen an; sie verbessern Produktabgleich und Angebotsqualität. |
| **Include identifier_exists field** | No | Mit **Yes** fügen Sie `identifier_exists` hinzu. Das Feld teilt Microsoft mit, ob ein Artikel eine eindeutige Produktkennung besitzt. |
| **Include adult field** | Do not include | Wählen Sie **Include as true** für altersbeschränkte Erwachsenenprodukte, **Include as false** für einen ausdrücklichen Falschwert oder **- do not include -**, um das Feld wegzulassen. Das Formular zeigt außerdem die unpassende vierte Bezeichnung **Lowercase all letters, example: product name**; verwenden Sie sie für dieses Feld nicht. |
| **Include shipping price** | Do not include | Wählen Sie **Do not include**, **Include (shipping price calculated for each item separately)** oder **Set shipping price manually**. Die automatische Berechnung erfolgt produktspezifisch; der manuelle Modus verwendet einen eingegebenen Betrag. |
| **Include product's additional shipping cost** | No | Mit **Yes** addieren Sie die zusätzliche Versandgebühr jedes Produkts zum exportierten Versandpreis. |
| **Manual shipping value** | 0 | Geben Sie bei manuellem Versand den Betrag ein, der für jeden Artikel gilt. |
| **Automatic shipping price zone select** | Anfängliche Shop-Zone | Wählen Sie bei automatischem Versand die Zielzone für die Berechnung. Die Berechnung je Artikel beansprucht mehr Hosting-Ressourcen als ein manueller Pauschalbetrag. |
| **Include weight** | No | Mit **Yes** schließen Sie das Versandgewicht in der Gewichtseinheit des Shops ein. |
| **Product type** | No | Mit **Yes** schließen Sie die eigene Kategoriestruktur des Shops als `product_type` ein. |
| **Product type - include category ID** | No | Setzen Sie bei aktiviertem **Product type** auf **Yes**, um die Kategorie-ID anzuhängen und gleichnamige Kategorien zu unterscheiden. |
| **Short description** | Short description | Wählen Sie **Short description** oder **Long description** als Quelle des Beschreibungswerts. |
| **Remove html from descriptions** | Yes | Microsoft verlangt Klartext. HTML-Tags und störende Zeilenumbrüche werden auch bei **No** entfernt; lassen Sie **Yes** als zutreffenden Hinweis auf die Ausgabe aktiviert. |
| **Product name** | Product name | Wählen Sie **Product name** oder **Meta title** als Quelle des Feed-Titels. |
| **Format name** | Do not format name | Lassen Sie den Namen unverändert, schreiben Sie nur den ersten Buchstaben oder jedes Wort groß oder alle Buchstaben klein. Verwenden Sie die Formatierung, wenn Katalogtitel vollständig großgeschrieben sind und Microsoft dies nicht akzeptiert. |
| **Remove selected characters from product name** | Leer | Geben Sie alle aus Titeln zu entfernenden Zeichen ein; `x=,` entfernt beispielsweise `x`, `=` und `,`. Lassen Sie das Feld ohne Leerzeichen wirklich leer, um nichts zu entfernen. |
| **Language** | Standardsprache des Shops | Wählen Sie die Sprache für Produkttitel, Beschreibungen und andere übersetzte Katalogdaten. |
| **Delimiter** | `|` | Legen Sie das Trennzeichen für CSV fest. Geben Sie `Tab` für das von Microsoft Merchant Center empfohlene TSV ein. Auch Pipe und Komma sind möglich. XML wird davon nicht beeinflusst. |
| **Wrap strings in double quotes** | Yes | Aktiviert lassen, damit Text mit Trenn- oder Sonderzeichen keine CSV-Zeilen beschädigt. |
| **Information about stock** | Include real stock information | Verwenden Sie den tatsächlichen Bestand oder erzwingen Sie für alle exportierten Produkte **in-stock**, **out-of-stock** oder **backorder**. Die letzte Option meldet Produkte mit erlaubten Nachbestellungen als vorrätig statt als nachbestellt. |
| **Availability date** | Leer | Geben Sie ein Ersatzdatum für nachbestellbare Produkte ohne eigenes Verfügbarkeitsdatum ein. Microsoft verlangt dieses Datum für solche Angebote. |
| **Include quantity info** | No | Mit **Yes** fügen Sie eine Bestandsspalte mit der Produkt- oder Kombinationsmenge hinzu. |
| **Default manufacturer value** | `Default` | Geben Sie den Marken-Ersatzwert für Produkte ohne zugeordneten Hersteller ein. |
| **Image size for product pictures** | Shopabhängiger anfänglicher Bildtyp | Wählen Sie den PrestaShop-Bildtyp, mit dem Produktbildadressen erstellt werden. |
| **Use default product picture if combination will not have associated photo** | No | Mit **Yes** wird das Hauptproduktbild verwendet, wenn eine exportierte Kombination kein zugeordnetes Bild besitzt. |
| **How many pictures you want to export?** | Export cover only | Wählen Sie **Export cover only** oder **Export all pictures**. Alle Bilder fügen weitere Bildlinks hinzu. |
| **Currency** | Standardwährung des Shops | Wählen Sie die Währung der exportierten Preise. Sie muss zum Zielmarkt des Katalogs in Microsoft Merchant Center passen. |
| **Price tax included or excluded** | Price Tax Included | Wählen Sie, ob reguläre und Angebotspreise Steuern ein- oder ausschließen. |
| **Include specific prices** | Yes | Aktiviert lassen, wenn PrestaShop-spezifische Preise für Währungen oder andere Kontexte im Feed berücksichtigt werden müssen. |
| **Export prices for selected group** | Gruppe für nicht identifizierte Shop-Kunden | Wählen Sie die Kundengruppe, deren Preiskontext das Modul verwendet. |
| **Export also unit price** | No | Mit **Yes** schließen Sie bei Varianten-Feeds verfügbare Grundpreisangaben ein. |
| **Export prices for selected country** | Standardland des Shops | Wählen Sie den Länderkontext für Steuern und länderabhängige Rabatte der Preisberechnung. |

**Produktauswahl, Ausschlüsse, Grenzen, lokaler Bestand und Kategoriezuordnung**

![Filter, Grenzen, Shop-Code und Microsoft Categories](https://mypresta.eu/docs/images/docs/mmcfeed-form-filters.webp)

| Feld | Ausgangswert | Funktion |
|---|---|---|
| **Product Manufacturer** | All | Exportieren Sie alle Hersteller oder nur Produkte des gewählten Herstellers. |
| **Product Supplier** | All | Exportieren Sie alle Lieferanten oder nur Produkte des gewählten Lieferanten. |
| **Product Category** | All | Exportieren Sie alle Kategorien oder beschränken Sie den Feed auf die gewählte Kategorie. |
| **Exclude categories** | Leer | Suchen Sie Kategorien und fügen Sie sie der Ausschlussliste hinzu. Produkte, die einer ausgewählten ausgeschlossenen Kategorie zugeordnet sind, werden ausgelassen. |
| **Exclude products without pictures** | No | Mit **Yes** lassen Sie Produkte ohne verwendbares Bild aus. |
| **Products's availability** | Export all products | Wählen Sie **Export only active products**, um deaktivierte Katalogprodukte auszulassen. |
| **Products's stock** | Export all products | Wählen Sie **Export only in-stock products**, um Produkte ohne Bestand auszulassen. |
| **Exclude products with specific reference** | No | Mit **Yes** aktivieren Sie die Filterung nach Referenzpräfix. |
| **Exclude product where reference starts with:** | Leer | Geben Sie das auszulassende Präfix ein. Es gilt für Produkte und Kombinationen, deren Referenz mit diesem Text beginnt. |
| **Exclude products worth less than defined value** | No | Mit **Yes** lassen Sie Produkte unter einem Mindestwert in der Standardwährung des Shops aus. |
| **Value of products (worth less) to exclude** | Leer | Geben Sie den Mindestwert für den vorherigen Filter ein. Produkte mit niedrigerem Preis werden ausgelassen. |
| **Exclude products** | Leere Liste | Beginnen Sie einen Produktnamen einzugeben und wählen Sie das Produkt für die Ausschlussliste. Mit **Add all search results** schließen Sie alle aktuellen Suchergebnisse aus; über die Entfernen-Schaltfläche löschen Sie einen Eintrag. |
| **Limit number of products in feed** | 0 | Geben Sie die maximale Produktzahl für diesen Feed ein. Leer oder `0` bedeutet keine Grenze. Verwenden Sie eine Grenze, wenn ein großer Katalog die verfügbare Ausführungszeit oder den Speicher überschreitet. |
| **Part of feed** | 0 | Verwenden Sie `0`, wenn der Feed nicht aufgeteilt wird. Erstellen Sie für geteilte Feeds getrennte Feeds mit gleicher Grenze und fortlaufenden Teilen. Für 3.000 Produkte und eine Grenze von 1.000 verwenden Sie die Teile 1, 2 und 3. |
| **Include store code to feed** | No | Mit **Yes** kennzeichnen Sie in einem lokalen Bestandsfeed eine Filiale. Verwenden Sie dieselbe Kennung wie in Ihrem Microsoft-Geschäftskonto. |
| **Store code** | Leer | Geben Sie die exakte, groß-/kleinschreibungssensitive alphanumerische Filialkennung von Microsoft ein. |
| **Microsoft Categories** | Taxonomie möglicherweise nicht synchronisiert | Prüfen Sie für jede Sprache den Dateistatus. Klicken Sie auf **Synchronize** oder wählen Sie unter **Synchronize specific** eine Quelle, wenn die normale Quelle diese Sprache nicht abdeckt. Klicken Sie danach auf **Pair categories**, suchen Sie neben jeder Shop-Kategorie die passende Microsoft-Kategorie und speichern Sie die Zuordnung. Das Wiederholungssymbol überträgt einen Wert auf alle Felder; das Löschsymbol entfernt eine Zuordnung. |

## 4. Storefront- und Feed-Adressen

Das Modul fügt dem Storefront weder Block noch Schaltfläche, Produktseiteninhalt, Kundenformular, Kontoseite oder eine andere Oberfläche hinzu. Kunden interagieren nicht damit.

Externe Dienste verwenden die unter **Feeds** kopierte Katalogadresse:

- **Live catalog URL** erzeugt den Katalog bei jedem Abruf neu und gibt ihn zurück. Es wird keine statische Datei gespeichert.
- **Generate / cron URL** enthält das Geheimnis zum Schreiben einer statischen Datei. Rufen Sie sie per Scheduler oder **Generate** auf. Geben Sie sie nicht an Microsoft Merchant Center weiter.
- **Catalog file URL** verweist auf die von der Erstellungsadresse erzeugte statische Datei. Verwenden Sie diese Adresse als Feed-Quelle, wenn **Save to file** aktiviert ist.

Beim Öffnen einer nicht verfügbaren Adresse kann Folgendes erscheinen:

| Anzeige | Maßnahme |
|---|---|
| **Feed is disabled** | Öffnen Sie **Feeds** und setzen Sie den Feed auf **On**, oder bearbeiten Sie ihn und setzen Sie **Active** auf **Yes**. |
| **feed does not exists** | Kopieren Sie die aktuelle Adresse erneut aus **Feeds**. Der gespeicherte Feed wurde gelöscht, die Adresse ist unvollständig oder die Konfiguration ungültig. |
| **Feed is not available in this store** | Wechseln Sie zum zugewiesenen Shop, bearbeiten Sie **Shop** und kopieren Sie die für diesen Shop erzeugte Adresse. |
| **Access denied** | Verwenden Sie im Dateimodus die vollständige, von der Feed-Seite kopierte **Generate / cron URL**. Entfernen oder ändern Sie den geheimen Teil nicht. |

## 5. Probleme und Lösungen

### 5.1 Der Feed meldet, dass er deaktiviert ist

**Symptom:** Beim Öffnen der Adresse erscheint **Feed is disabled**.

**Ursache:** Der Statusschalter ist aus oder **Active** steht auf **No**.

**Maßnahme:** Öffnen Sie **Catalog → Microsoft Merchant Feed → Feeds** und setzen Sie den Feed auf **On**. Seine vorhandene Adresse bleibt gültig.

### 5.2 Der Feed existiert nicht

**Symptom:** Beim Öffnen der Adresse erscheint **feed does not exists**.

**Ursache:** Die Adresse verweist auf einen gelöschten Feed, ist unvollständig oder der gespeicherte Feed besitzt keine verwendbare Konfiguration.

**Maßnahme:** Öffnen Sie **Feeds** und kopieren Sie die Adresse erneut. Fehlt der Feed, erstellen und speichern Sie ihn neu.

### 5.3 Der Feed gehört zu einem anderen Shop

**Symptom:** Die Liste zeigt **Not available in this store** oder die Adresse zeigt **Feed is not available in this store**.

**Ursache:** Im Multistore ist der Feed einem anderen Shop zugewiesen.

**Maßnahme:** Wechseln Sie im Backoffice zum zugewiesenen Shop oder bearbeiten Sie **Shop**, speichern Sie und kopieren Sie die neue Adresse.

### 5.4 Eine Erstellung im Dateimodus meldet verweigerten Zugriff

**Symptom:** Der Aufruf des Dateigenerators zeigt **Access denied**, und keine Datei wird aktualisiert.

**Ursache:** In der Adresse fehlt die vom Modul hinzugefügte geheime Schreibberechtigung.

**Maßnahme:** Kopieren Sie **Generate / cron URL** erneut aus **Feeds** oder der Bearbeitungsseite und verwenden Sie sie unverändert im Scheduler. Halten Sie diese Adresse geheim.

### 5.5 Microsoft erhält die Generatorantwort statt einer stabilen Datei

**Symptom:** Der geplante Abruf durch Microsoft schlägt fehl oder startet bei jedem Abruf unerwartet die Erstellung, obwohl **Save to file** aktiviert ist.

**Ursache:** Die **Generate / cron URL** wurde in Microsoft Merchant Center eingefügt.

**Maßnahme:** Verwenden Sie die Erstellungsadresse nur in Ihrem Scheduler. Rufen Sie sie einmal auf, prüfen Sie **On disk** im **Dashboard** und fügen Sie die **Catalog file URL** in Microsoft Merchant Center ein.

### 5.6 Der Feed ist leer oder Produkte fehlen

**Symptom:** Die Erstellung ist erfolgreich, liefert aber keine oder weniger Artikel als erwartet.

**Ursache:** Einstellungen für Hersteller, Lieferant, Kategorie, ausgeschlossene Kategorien oder Produkte, Bilder, Aktivstatus, Bestand, Referenzpräfix, Mindestwert, Grenze oder Teil entfernen Produkte.

**Maßnahme:** Bearbeiten Sie den Feed und prüfen Sie alle Felder für Produktauswahl und Ausschlüsse. Wählen Sie vorübergehend **All**, deaktivieren Sie Ausschlussschalter, leeren Sie Ausschlusslisten und setzen Sie Grenze und Teil auf `0`. Speichern und erzeugen Sie erneut; führen Sie Filter danach einzeln wieder ein.

### 5.7 Microsoft-Kategorien fehlen

**Symptom:** Der Feed enthält keine brauchbaren Microsoft-Kategoriewerte oder **Pair categories** kann die Taxonomie nicht durchsuchen.

**Ursache:** Die Taxonomie für die gewählte Sprache ist nicht synchronisiert oder Shop-Kategorien sind nicht zugeordnet.

**Maßnahme:** Bearbeiten Sie den Feed, gehen Sie zu **Microsoft Categories** und klicken Sie für die Sprache auf **Synchronize**. Ist diese Quelle nicht verfügbar, wählen Sie unter **Synchronize specific** eine Quelle. Sobald die Datei verfügbar ist, klicken Sie auf **Pair categories** und vervollständigen die Zuordnungen.

### 5.8 Ein großer Katalog führt zu Zeitüberschreitung oder Speichermangel

**Symptom:** Die Erstellung stoppt, dauert zu lange oder die gespeicherte Datei wird nicht aktualisiert.

**Ursache:** Das Hosting kann den gesamten Katalog, Preiskontext, Bilder und automatische Versandberechnungen nicht in einem Lauf verarbeiten.

**Maßnahme:** Geben Sie eine sinnvolle **Limit number of products in feed** ein und erstellen Sie getrennte Feeds mit fortlaufenden **Part of feed**-Werten. Bevorzugen Sie gegebenenfalls einen manuellen Versandpauschalbetrag gegenüber der automatischen Berechnung je Artikel und planen Sie die Teile getrennt.

### 5.9 Microsoft meldet Probleme mit der Datenqualität

**Symptom:** Microsoft Merchant Center warnt vor Kennungen, Beschreibungen, Preisen, Verfügbarkeit, Bildern, Varianten, Altersgruppen, Geschlecht, Farben oder Versand.

**Ursache:** Gewählte Quellfelder sind leer, verwenden einen nicht unterstützten Wert oder passen nicht zum Markt des Microsoft-Katalogs.

**Maßnahme:** Öffnen Sie den Feed und gleichen Sie **Language**, **Currency** sowie Länder- und Steuerkontext mit dem Microsoft-Katalog ab. Stellen Sie gültige GTIN-Daten, Marken-Ersatzwert, Klartextbeschreibungen, aktuelle Verfügbarkeit, geeignete Bilder und Kategoriezuordnungen bereit. Prüfen Sie bei Bekleidung **size**, **gender**, **color**, **age_group** und **item_group_id**. Erzeugen Sie den Feed neu und prüfen Sie die Diagnose in Microsoft Merchant Center erneut.

## 6. Entwicklerreferenz

### 6.1 Modulübersicht

| Element | Wert |
|---|---|
| Technischer Name | `mmcfeed` |
| Version | `1.1.0` |
| Anzeigename | `Microsoft Merchant Center Feed` |
| Autor | `MyPresta.eu` |
| Modulregisterkarte | `administration` |
| Backoffice-Registerkarte | `AdminExportProductsFeedMicrosoft`, unter `AdminCatalog` installiert |
| Front-Endpunkt | `controllers/front/feed.php` |

`mmcfeed` erweitert `Module`. Das ObjectModel `mmc` speichert Feed-Definitionen als Name, Shop, Aktivkennzeichen und serialisierte Konfiguration. Direkte Backoffice-Downloads und Aufrufe des Front-Controllers erzeugen CSV oder XML aus PrestaShop-Produktdaten. Der Dateimodus schreibt einen bereinigten Dateinamen; der Live-Modus streamt die Antwort.

### 6.2 Wichtige Dateien und Klassen

| Datei | Aufgabe |
|---|---|
| `mmcfeed.php` | Modulmetadaten, Installation und Deinstallation, globales Formular, Bereinigung, sichere Pfade und HMAC-Tokenprüfung. |
| `controllers/admin/AdminExportProductsFeedMicrosoft.php` | Dashboard, Feed-Liste, Formular, Duplizieren, Löschen, Taxonomie, Zuordnung, direkte Exporte und Formularstandards. |
| `controllers/front/feed.php` | Lädt und prüft den Feed, wendet Optionen an, streamt die Ausgabe oder schreibt eine Datei. |
| `model/mmc.php` | ObjectModel `mmc`, Schemamigration, Feed-URLs, Listen, Protokollierung, Statistiken und Dateimetadaten. |
| `model/categorymap.php` | Definiert das ObjectModel `pixelgoogle` für Kategoriezuordnungen. |
| `model/google.php` | Duplicates the same `pixelgoogle` class definition and methods as `model/categorymap.php`; loading both definitions in one request would cause a class redeclaration. |
| `lib/updateChecker.php` | `mmcfeedUpdate`, Update-Prüfungen, Benachrichtigungseinstellung und Updates-Formular. |
| `lib/searchTool/searchTool.php` | Produkt- und Kategorie-Autovervollständigung für Ausschlussfelder. |
| `views/templates/admin/layout.tpl` | Application header, navigation tabs, notices, and shared assets. |
| `views/templates/admin/feeds.tpl` | Feed cards, URLs, states, and row actions. |
| `views/templates/admin/dashboard.tpl` | KPIs, activity chart, recent runs, and generated files. |
| `views/templates/admin/form-chrome.tpl` | Form header and live/file URL presentation. |
| `views/category_taxonomy.tpl` | Taxonomy status, synchronization, and pairing entry points. |
| `views/categories-fancybox.tpl` | Category mapping dialog and optional parent paths. |
| `views/exclude-products.tpl` | Product exclusion autocomplete and selected-product list. |
| `views/js/admin-app.js` and `views/css/admin-app.css` | Back-office application interactions and styling. |

### 6.3 Controller und Anfrageablauf

`AdminExportProductsFeedMicrosoftController` erweitert `ModuleAdminController`. `mmcfeed_view` wählt `dashboard`, `feeds`, `updates` oder `form`. Der Controller verarbeitet:

- `saveonly` zum Speichern und Zurückkehren zur Liste.
- `submitExport` zum Speichern und sofortigen Herunterladen.
- `updatemmc` mit `id_mmc` zum Bearbeiten.
- `duplicatemmc` und `deletemmc` für Zeilenaktionen.
- AJAX `toggleFeedActive`.
- AJAX taxonomy synchronization, category mapping, autocomplete, association saving, and association deletion.

`mmcfeedfeedModuleFrontController` erweitert `ModuleFrontController`. Er lädt nur gespeicherte Parameter, weist fehlende, deaktivierte oder einem anderen Shop gehörende Feeds ab und startet die Erzeugung. Im Dateimodus benötigt er `mmcfeed_write_key`. Eingehende Debug- und Exportparameter werden entfernt oder ignoriert.

Das Modul besitzt Platzhalterdateien `index.php`, aber keinen zweiten funktionsfähigen Front-Controller.

### 6.4 Hooks und Lebenszyklus

Der einzige registrierte Hook ist `actionAdminControllerSetMedia`. Für `AdminExportProductsFeedMicrosoft` aktiviert er Fancybox und die jQuery-Autovervollständigung. Er erzeugt keine Frontoffice-Ausgabe.

Das Modul definiert keine eigenen Methoden `enable()` oder `disable()` und stellt keine eigenen Hooks bereit.

`install()` ruft den übergeordneten Installer auf, registriert den Hook, erstellt Registerkarte und Tabellen und vervollständigt das Schema. Der Cache bleibt erhalten. `uninstall()` löscht die Registerkarte und ruft `parent::uninstall()` auf, behält aber Tabellen, Konfiguration, Feeds und Taxonomiedateien.

### 6.5 Overrides

Das Modul installiert keine Overrides für PrestaShop-Klassen oder -Controller.

### 6.6 Datenbank

Das tatsächliche Tabellenpräfix ist das für den Shop konfigurierte Datenbankpräfix.

| Tabelle | Inhalt |
|---|---|
| `pixelgoogle` | Category mapping records: primary key `id_pixelgoogle`, legacy `id_google`, PrestaShop `id_category`, `id_lang`, and mapped taxonomy `value`. |
| `mmc` | Saved feeds: primary key `id_mmc`, `name`, owner `id_shop`, serialized `conf`, and `active`. Schema checks add `active` and `id_shop` to older installations and assign legacy feeds to the default shop. |
| `mmc_log` | Generation history: feed ID, timestamp, duration, item count, status, file-mode flag, filename, format, and source. Entries older than 90 days are removed when a run is logged. |

Die Deinstallation behält alle drei Tabellen sowie Feed-Datensätze, Zuordnungen und Laufhistorie.

### 6.7 Konfigurationsschlüssel und Standardwerte

Die globalen und Update-Schlüssel sind:

| Schlüssel | Standardwert oder Verhalten |
|---|---|
| `mmc_pf_tree` | Missing value behaves as `0`; controls parent paths in category mapping. |
| `mypresta_updates` | Shared MyPresta update preference; a missing value behaves as disabled in the periodic check. |
| `update_mmcfeed` | Timestamp of the latest update check; written during checks. |
| `updatev_mmcfeed` | Latest version returned by the update service. |

Bei aktiviertem **Remember settings** werden Formularstandards mit dem Präfix `mmc_` gespeichert:

| Schlüssel | Ersatzwerte |
|---|---|
| `mmc_export_igid`, `mmc_export_active`, `mmc_export_instock`, `mmc_export_product_type`, `mmc_export_product_type_id`, `mmc_export_product_weight`, `mmc_export_shipping_info`, `mmc_export_unit_price`, `mmc_export_save_file`, `mmc_export_nophoto_exclude`, `mmc_export_adult`, `mmc_export_color`, `mmc_export_gender`, `mmc_export_age_group`, `mmc_export_size`, `mmc_export_storecode`, `mmc_export_mainpicture`, `mmc_export_inventory`, `mmc_export_ie` | `0` or false. |
| `mmc_export_additional_sc`, `mmc_export_exworthless` | False. |
| `mmc_remember_settings`, `mmc_export_specific`, `mmc_export_enclosure`, `mmc_export_removehtml` | `1` or true. |
| `mmc_export_file_format` | `csv`. |
| `mmc_export_type` | Legacy fallback `product`, normalized to `products` for generation. |
| `mmc_export_identification` | `id_product`. |
| `mmc_export_gtin` | `upc`. |
| `mmc_export_product_name` | `name`. |
| `mmc_export_product_name_format`, `mmc_export_instock_info`, `mmc_export_what_pictures` | `0`. |
| `mmc_export_short_description_what` | `short`. |
| `mmc_export_delimiter` | `|`. |
| `mmc_export_tax` | `price_tin`. |
| `mmc_export_manufacturers_default` | `Default`. |
| `mmc_export_language`, `mmc_export_currency`, `mmc_export_country_prices`, `mmc_export_group_prices` | Corresponding shop defaults. |
| `mmc_export_category`, `mmc_export_manufacturers`, `mmc_export_suppliers` | Legacy fallback `all`; the visible selector uses its **All** option. |
| `mmc_export_shipping_info_price`, `mmc_limit_limit`, `mmc_limit_page` | `0`. |
| `mmc_export_shipping_id_zone` | `1`. |
| `mmc_export_filename`, `mmc_export_remove_char_product_name`, `mmc_export_exclude`, `mmc_export_exclude_categories`, `mmc_export_color_type`, `mmc_export_color_default`, `mmc_export_gender_default`, `mmc_export_size_default`, `mmc_export_availability_date`, `mmc_export_exreference`, `mmc_export_exreference_value`, `mmc_export_sc`, `mmc_export_exworthless_value` | Empty string. |
| `mmc_export_color_attribute`, `mmc_export_color_feature`, `mmc_export_gender_type`, `mmc_export_gender_feature`, `mmc_export_gender_attribute`, `mmc_export_age_group_type`, `mmc_export_age_group_feature`, `mmc_export_age_group_attribute`, `mmc_export_age_group_default` | `0`. |
| `mmc_export_size_attribute` | Comma-separated IDs; empty by default. |
| `mmc_mmcfeed_products` | Comma-separated excluded product IDs; empty by default. |

Das Formular liest `delete_images` auch als `mmc_delete_images`, obwohl diese Version kein sichtbares Feld dafür besitzt. Die Deinstallation löscht keinen dieser Schlüssel.

### 6.8 Erzeugte Dateien, Taxonomie, Sicherheit und Erweiterungen

Statische Feeds werden als `modules/mmcfeed/{sanitized-name}.{csv|xml|txt}` geschrieben. Namen werden auf Buchstaben, Ziffern, Bindestriche und Unterstriche reduziert; Pfadprüfungen verhindern das Verlassen des Modulverzeichnisses. Taxonomien liegen unter `modules/mmcfeed/google/{language-code}.txt`. Beide Gruppen bleiben bei der Deinstallation erhalten.

Das Schreib-Token lautet `hash_hmac('sha256', 'mmcfeed.write.' . $idShop, _COOKIE_KEY_)`. Ein Backoffice-Mitarbeiter darf direkt schreiben; ein externer Aufruf muss das mit `hash_equals` verglichene Token übermitteln. Der Controller verwirft nicht vertrauenswürdige Parameter `export_*`, `mmcfeed_*`, `mmc_*`, `pf_*` sowie Grenz-, Debug- und Ausschlussparameter.

CSV verwendet `fputcsv`, ein normalisiertes Trennzeichen und doppelte Anführungszeichen. Der Text wird dekodiert und normalisiert; Zeilenumbrüche, Tabulatoren und HTML werden entfernt. XML verwendet `SimpleXMLElement`. Update-Prüfungen verwenden cURL oder URL-fähigen Dateizugriff.

Übersetzungen verwenden `translations/{iso}.php`. Die meisten Texte durchlaufen Modulübersetzungen; einige Bezeichnungen wie **All**, **Price Tax Included** und **Price Tax Excluded** bleiben englisch. Feldbeschreibungen stehen in den HelperForm-Arrays des Admin-Controllers, Update-Beschreibungen in `lib/updateChecker.php`.

There is no storefront template to override in a theme. Back-office Smarty templates can be changed only by modifying or extending the module. For safer customization, extend feed generation through a maintained module fork or a separate integration instead of editing PrestaShop core files; no formal extension hook is exposed.

## 7. Hilfe

Produktseite: [Microsoft Merchant Center Product Feed](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-feed.html)

Melden Sie sich für Support bei Ihrem Kundenkonto auf mypresta.eu an, öffnen Sie die Kontaktseite und wählen Sie **Support for paid modules**. Für dieses Thema ist eine Anmeldung erforderlich; wählen Sie danach das Modul aus Ihrer Kaufhistorie und beschreiben Sie Feed, Shop und die genaue angezeigte Meldung.

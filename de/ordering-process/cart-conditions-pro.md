---
title: "Cart Conditions - Dokumentation und Benutzerhandbuch"
sidebar:
  label: "Cart Conditions - Dokumentation und Benutzerhandbuch"
description: "Handbuch zur Einrichtung und zur Fehlersuche für Shops, die Cart Conditions bereits nutzen."
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Cart conditions pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/cart-conditions-pro/)
>
> ---


## 1. Anforderungen

Cart Conditions läuft im Shop. Es braucht kein weiteres Modul und kein Konto bei einem externen Dienst.

- PrestaShop 1.7, 8 und 9. Dieses Handbuch wurde auf PrestaShop 9.2.0 geprüft.
- Die PHP-Version, die diese PrestaShop-Version verlangt. Das Modul verlangt keine zusätzliche PHP-Erweiterung.
- Kein anderes Modul ist erforderlich.
- Die Regeln lesen den aktuellen Warenkorb. Die Größe des Katalogs ändert die Prüfung nicht.

## 2. Installation

1. Öffnen Sie **Module**, dann **Module Manager**.
2. Laden Sie die Zip-Datei hoch und installieren Sie das Modul. Die Installation schaltet es ein.
3. Öffnen Sie **Katalog**. Fünf Einträge erscheinen in dieser Reihenfolge. Die Namen bleiben in jeder Back-Office-Sprache englisch:

- **Cart Conditions**
- **Cart Value Conditions**
- **Cart Quantity Conditions**
- **Cart Associations Conditions**
- **Cart value by country conditions**

Die Installation leert den Shop-Cache nicht.

Die Deinstallation entfernt diese fünf Menüeinträge und hängt das Modul aus. Gespeicherte Regeln, die Ausschlussliste, die Verfügbarkeitseinstellung und die Update-Einstellung bleiben. Eine erneute Installation bringt das Menü zurück, und die alten Regeln sind noch da.

## 3. Konfiguration und tägliche Arbeit

Der Kunde füllt den Warenkorb. Auf der Warenkorbseite listet der Shop jede verletzte Regel in einem roten Hinweis. Geht der Kunde zur Zahlung weiter, schickt der Shop ihn zum Warenkorb zurück, bis jede aktive Regel erfüllt ist. Ein Kunde unter **Exclude customers from conditions** überspringt jede Regel und kann bestellen.

Bereiten Sie den Shop in dieser Reihenfolge vor:

1. Öffnen Sie **Configure** und legen Sie fest, wen und welche Produkte die Regeln ignorieren.
2. Legen Sie fest, ob künftige Verfügbarkeitsdaten gemischt werden dürfen.
3. Öffnen Sie jede Liste unter **Katalog**, klicken Sie **Add new**, füllen Sie das Formular, setzen Sie **Active** auf **On** und klicken Sie **Save**.
4. Legen Sie eine Testbestellung mit einem normalen Kunden und mit einem ausgeschlossenen Kunden an.

Ein neues Formular öffnet sich mit **Active** auf **Off**. **Save** speichert die Zeile, und der Warenkorb ignoriert sie, bis Sie **On** setzen. Die Konfigurationsseite antwortet **Saved**. Die Regellisten zeigen die übliche Back-Office-Bestätigung nach **Save**.

Der blaue Hinweis auf **Configure** lautet: "Management of this module is located under Price Rules menu." Die fünf Links in diesem Hinweis und die Einträge unter **Katalog** öffnen die Listen. Einen Price-Rules-Eintrag gibt es für dieses Modul nicht.

Die Bildschirme in diesem Handbuch sind das englische Back Office. Schaltflächen und Felder heißen so, wie sie dort stehen.

![Links auf der Konfigurationsseite](https://mypresta.eu/docs/images/docs/cartcon-configure-links.webp)

### 3.1 Konfigurationsseite

Öffnen Sie **Module**, **Module Manager**, suchen Sie **Cart Conditions** und klicken Sie **Configure**.

#### Kunden und Produkte ausschließen

![Ausschlussformular](https://mypresta.eu/docs/images/docs/cartcon-configure-exclude.webp)

Suchen Sie einen Kunden, klicken Sie das Ergebnis, und die Person steht auf der Ausschlussliste. Entfernen Sie eine Person aus derselben Liste, bevor Sie speichern. Ausgeschlossene Kunden überspringen jede Warenkorbregel, auch die Verfügbarkeitsprüfung.

| Feld | Startwert | Wirkung |
|---|---|---|
| **Exclude customers from conditions** | leer | Kunden auf dieser Liste bestellen ohne Warenkorbregel. **Save** speichert die Liste. |
| **Exclude products from conditions** | **Do not exclude products** | **Exclude selected products** lässt die Regeln die gewählten Produkte und Kategorien aus. **Do not exclude products** zählt jedes Produkt. |
| **Categories** | nichts markiert | Markierte Kategorien werden ausgelassen, wenn der Schalter oben **Exclude selected products** ist. |
| **Save** | - | Speichert Kunden, Schalter, Produkte und Kategorien. Die Seite zeigt **Saved**. |

Produktsuche und Kategoriebaum stehen auf demselben Formular. Ein Produkt wählen Sie wie einen Kunden: suchen, dann das Ergebnis klicken.

#### Globale Bedingungen

![Vergleich der Verfügbarkeit](https://mypresta.eu/docs/images/docs/cartcon-configure-availability.webp)

Die Prüfung sieht nur Produkte ohne Lagerbestand, deren **Availability date** noch in der Zukunft liegt. Produkte auf Lager, mit leerem oder vergangenem Datum, und ausgeschlossene Produkte bleiben außen vor. Ein künftiges Datum im Warenkorb blockiert nicht. Zwei oder mehr verschiedene Werte blockieren.

| Feld | Startwert | Wirkung |
|---|---|---|
| **Block order of products with Various availabiltiy date** | **Off** | **On** blockiert den Warenkorb, wenn diese künftigen Daten nicht zum Vergleich unten passen. **Off** überspringt die Prüfung. PrestaShop erlaubt bereits die Bestellung eines später verfügbaren Produkts. Dieser Schalter entscheidet, ob verschiedene Daten in einem Warenkorb stehen dürfen. |
| **How to compare availability dates** | **Exact date** | **Exact date** blockiert, wenn die künftigen Daten nicht derselbe Tag sind. **Same calendar month** erlaubt verschiedene Tage im selben Monat und Jahr und blockiert, wenn Monat oder Jahr abweicht. Der 5. November 2026 und der 20. November 2026 gehen durch. Der 2. Dezember 2026 nicht. Der 5. November 2027 nicht. |
| **Save** | - | Speichert Schalter und Vergleich. Die Seite zeigt **Saved**. Diese Schaltfläche legt keine Katalogregel an. |

Warenkorbtext für **Exact date**: "Availability dates of products in your cart are different. You cant place an order." Für **Same calendar month**: "Availability months of products in your cart are different. You cant place an order."

#### MyPresta-Updates

![Update-Prüfung](https://mypresta.eu/docs/images/docs/cartcon-configure-updates.webp)

| Feld | Startwert | Wirkung |
|---|---|---|
| **Check updates** / **Check now** | - | Fragt MyPresta, ob eine neuere Datei existiert. **Module is up to date!** bedeutet, diese Datei ist aktuell. **New version available!** bedeutet, eine neuere Datei ist veröffentlicht. Die Schaltfläche installiert sie nicht. |
| **Updates notifications** | **Disable** | **Enable** zeigt eine Back-Office-Warnung, wenn eine neuere Version erscheint. **Disable** bleibt still. **Save** speichert die Wahl. |
| **Module page** | Link | Öffnet die Modulseite mit der Änderungsliste. |
| **Save** | - | Speichert die Benachrichtigung. |

### 3.2 Cart Conditions

Öffnen Sie **Katalog**, dann **Cart Conditions**. Diese Regeln gelten für jeden Kunden, der nicht ausgeschlossen ist. Ein Kundengruppenfeld gibt es auf dieser Liste nicht.

![Liste Cart Conditions](https://mypresta.eu/docs/images/docs/cartcon-conditions-list.webp)

Spalten: **ID**, **Cart condition**, **Target type**, **Target item**, **Active**. Ein leerer Shop zeigt **No records found**. Filter stehen über den Spalten. Zeilenaktionen: Bearbeiten, Löschen, Symbol **Active**. Sammelaktion: Löschen. **Add new** öffnet das Formular.

![Neue Cart-Conditions-Regel](https://mypresta.eu/docs/images/docs/cartcon-conditions-form.webp)

| Feld | Startwert | Wirkung |
|---|---|---|
| **Condition** | **Must have** | **Must have** verlangt das Ziel. **Can't have** blockiert es. |
| **Target type** | **Category** | **Category** ist eine Kategorie-ID. **Product** ist eine Produkt-ID. **More than defined number of products** ist eine Stückzahl des ganzen Warenkorbs. |
| **Target item** | leer | Kategorie-ID, Produkt-ID oder Stückzahl. Der Hinweis verlangt eine ID oder eine Produktzahl. |
| **Active** | **Off** | **On** prüft die Zeile. **Off** behält die Zeile und überspringt sie. |
| **Save** | - | Speichert die Regel. |

Was der Kunde sieht:

- **Must have** und **Category**: "To place an order you must order product from category: ...".
- **Can't have** und **Category**: "Your cart contains product from forbidden category: .... To continue order please remove it from cart."
- **Must have** und **Product**: "To place an order you must order product: ...".
- **Can't have** und **Product**: "Your cart contains forbidden product: .... To continue order please remove it from cart."
- **Must have** und Stückzahl: "Your cart contains less products than required (...). To continue order please increase quantity of products in your cart".
- **Can't have** und Stückzahl: "Your cart contains more products than allowed (...). To continue order please decrease quantity of products in your cart".

Die Stückzahl ist die Summe der Mengen im Warenkorb nach Abzug ausgeschlossener Produkte. **Must have** verlangt, dass der Warenkorb diese Zahl erreicht. **Can't have** blockiert einen Warenkorb über dieser Zahl.

### 3.3 Cart Value Conditions

Öffnen Sie **Katalog**, dann **Cart Value Conditions**. Jede Zeile ist eine Kundengruppe, eine Kategorie und ein Mindestbetrag.

![Werteliste](https://mypresta.eu/docs/images/docs/cartcon-value-list.webp)

Spalten: **ID**, **Customer group**, **Cart condition**, **Target**, **Value**, **Active**. Leere Liste: **No records found**. Zeilenaktionen: Bearbeiten, Löschen, Symbol **Active**. Sammelaktion: Löschen. **Add new** öffnet das Formular.

![Neue Wertregel](https://mypresta.eu/docs/images/docs/cartcon-value-form.webp)

| Feld | Startwert | Wirkung |
|---|---|---|
| **Customer Group** | erste Gruppe im Shop (Visitor in einem Standardshop) | Geprüft werden nur Käufer dieser Gruppe. Ein angemeldeter Kunde wird in jeder seiner Gruppen geprüft. |
| **Condition** | **Must order from selected category** | Das ist die einzige Wahl. Die Regel läuft, wenn der Warenkorb diese Kategorie schon enthält. |
| **Target item** | leer | Kategorie-ID. |
| **Value** | leer | Mindestsumme brutto der Produkte aus dieser Kategorie. Tragen Sie sie in der Standardwährung des Shops ein. Das Währungszeichen ist die Shop-Währung. |
| **Active** | **Off** | **On** wendet die Zeile an. **Off** speichert sie ungenutzt. |
| **Save** | - | Speichert die Regel. |

Fehlt die Kategorie im Warenkorb, bleibt die Regel still. Ist sie da und liegt die Bruttosumme unter **Value**, zeigt der Warenkorb: "To place an order you must order for: ... from category: ...".

### 3.4 Cart Quantity Conditions

Öffnen Sie **Katalog**, dann **Cart Quantity Conditions**.

![Mengenliste](https://mypresta.eu/docs/images/docs/cartcon-quantity-list.webp)

Spalten: **ID**, **Customer group**, **Cart condition**, **Target**, **Quantity**, **Active**. Leere Liste: **No records found**. Zeilenaktionen: Bearbeiten, Löschen, Symbol **Active**. Sammelaktion: Löschen.

![Neue Mengenregel](https://mypresta.eu/docs/images/docs/cartcon-quantity-form.webp)

| Feld | Startwert | Wirkung |
|---|---|---|
| **Customer Group** | erste Gruppe im Shop | Nur diese Gruppe wird geprüft. |
| **Condition** | **Must order at least X products from selected category** | Wählen Sie das Limit. Die volle Liste steht unten. |
| **Target country** | erstes Land im Shop | Nur für die zwei Regeln "from Y category". Bei jeder anderen Bedingung verbirgt die Seite diese Liste. |
| **Target item** | leer | Kategorie-, Produkt-, Hersteller-ID oder Attributwert, je nach **Condition**. Der Hinweis verlangt die ID des Ziels. Bei ganzen Warenkorbregeln setzt die Seite das Wort Cart und sperrt das Feld. |
| **Quantity** | leer | Die Zahl X der gewählten Bedingung. |
| **Accept only multiplied qty** | **Off** | **On** akzeptiert nur Vielfache von **Quantity**, zum Beispiel 6, 12, 18, 24 bei **Quantity** 6. **Off** akzeptiert jede Zahl, die die Regel erfüllt. |
| **Active** | **Off** | **On** wendet die Zeile an. |
| **Save** | - | Speichert die Regel. |

**Condition** in der Reihenfolge des Formulars:

- **Must order at least X products from selected category**
- **Can't more than X products from selected category**
- **Must order at least X products from selected manufacturer**
- **Can't more than X products from selected manufacturer**
- **Must order at least X quantity of selected product**
- **Can't order more than X quantity of selected product**
- **Must order at least X quantity of each product**
- **Can't order more than X quantity of each product**
- **Can't order more than X products with the same attribute value**
- **Cart must have at least X products**
- **Cart can't have more than X products**
- **Cart must have at least X different products**
- **Cart can't have more than X different products**
- **Cart of user from selected country must have more than X products**
- **Cart of user from selected country can't have more than X products**
- **Cart of user from selected country must have more than X products from Y category**
- **Cart of user from selected country can't have more than X products from Y category**

Bei den letzten beiden setzen Sie **Target country** und tragen die Kategorie-ID in **Target item** ein. Bei den zwei Länderregeln ohne Kategorie verbirgt die Seite **Target country**, ein Land wählen Sie dort also nicht. Für ein Geldbetragslimit nutzen Sie **Cart value by country conditions**. Für eine Stückzahl aus einer Kategorie nutzen Sie die letzten beiden Mengenregeln.

**Search for attribute value** erscheint nur bei **Can't order more than X products with the same attribute value**. Suchen Sie, klicken Sie einen Wert, und er wird **Target item**.

Der Warenkorbtext folgt der Wahl. Kategorie- und Herstellerregeln sagen "at least" oder "can't order more than" und nennen Kategorie oder Hersteller. Eine Produktregel nennt die aktuelle Menge. Eine Warenkorbregel sagt "you must order more than" oder "you can't order more than" und nennt die aktuelle Menge. Mit **Accept only multiplied qty** auf **On** ergänzt der Warenkorb: "We accept only multiplied quantity...".

Auf der Produktseite kann das Theme "You must order at least: ... quantity of this product" zeigen, für **Must order at least X quantity of selected product**, wenn dieses Produkt das Ziel ist und der Besucher zur Gruppe passt. Das ist ein Hinweis. Die Sperre geschieht im Warenkorb.

### 3.5 Cart Associations Conditions

Öffnen Sie **Katalog**, dann **Cart Associations Conditions**. Eine Zeile verbindet ein Element mit einem anderen für eine Kundengruppe. Die Regel startet erst, wenn das erste Element schon im Warenkorb liegt.

![Zuordnungsliste](https://mypresta.eu/docs/images/docs/cartcon-associations-list.webp)

Spalten: **ID**, **Customer group**, **Cart condition**, **Target item (1)**, **Associated item (2)**, **Active**. Leere Liste: **No records found**. Zeilenaktionen: Bearbeiten, Löschen, Symbol **Active**. Sammelaktion: Löschen.

![Neue Zuordnung](https://mypresta.eu/docs/images/docs/cartcon-associations-form.webp)

| Feld | Startwert | Wirkung |
|---|---|---|
| **Active** | **Off** | **On** wendet die Zeile an. |
| **Type of condition** | **Associations between product and product** | **Associations between product and category** oder **Associations between category and category** ändert die Bedeutung der beiden IDs. |
| **For what customer group** | erste Gruppe im Shop | Nur diese Gruppe wird geprüft. |
| **Target item (1)** | leer | Produkt- oder Kategorie-ID. Die Regel läuft, wenn der Kunde dieses Objekt in den Warenkorb legt. |
| **Condition** | **If customer will add to cart Target item (1) then it must order Associated item (2)** | Die Wahlmöglichkeiten stehen unten. |
| **Associated item (2)** | leer | Die verlangte oder verbotene Produkt- oder Kategorie-ID. |
| **Save** | - | Speichert das Paar. |

Wahlmöglichkeiten von **Condition**:

- **If customer will add to cart Target item (1) then it must order Associated item (2)**. Warenkorbtext: "If your cart has a product: ... you must order also product: ..." oder das Kategorie-Gegenstück.
- **If customer will add to cart Target item (1) then cart must have at least one different product**. Nur bei Produkt und Produkt sichtbar. Die Warenkorbprüfung zeigt für diese Wahl keinen Text. Nutzen Sie eine andere Wahl, wenn der Warenkorb sperren soll.
- **If customer will add to cart Target item (1) then it will be forbidden to order Associated item (2)**. Text: "If your cart has a product: ... you can't place an order for: ...".
- **If customer will add to cart Target item (1) then it will be forbidden to add any other product to cart**. Die Seite verbirgt **Associated item (2)**. Text: "If your cart has a product: ... you can't place an order for any other product."
- **If customer will add to cart Target item (1) then it will be forbidden to add products from categories other than Target item (1)**. Nur bei Kategorie und Kategorie. Die Seite verbirgt **Associated item (2)**.

Das Formular enthält auch **Include subcategories of Target item (1)** und **Include subcategories of Associated item (2)**. Die Seite verbirgt beide Schalter bei jedem Typ. Die Regel nutzt die IDs, die Sie eintragen.

### 3.6 Cart value by country conditions

Öffnen Sie **Katalog**, dann **Cart value by country conditions**. Die Regel nutzt das Land der Lieferadresse.

![Länderbeträge](https://mypresta.eu/docs/images/docs/cartcon-country-list.webp)

Spalten: **ID**, **Customer group**, **Condition**, **Country**, **Value**, **Active**. Leere Liste: **No records found**. Zeilenaktionen: Bearbeiten, Löschen, Symbol **Active**. Sammelaktion: Löschen.

![Neuer Länderbetrag](https://mypresta.eu/docs/images/docs/cartcon-country-form.webp)

| Feld | Startwert | Wirkung |
|---|---|---|
| **Customer Group** | erste Gruppe im Shop | Nur diese Gruppe wird geprüft. |
| **Target country** | erstes Land im Shop | Die Regel läuft, wenn die Lieferadresse dieses Land hat. Die Liste ist die Länderliste des Shops. |
| **Condition** | **Cart must be worth at least ...** | **Cart can't be worth more than ...** ist das Maximum. |
| **Condition tax** | **Tax included** | **Tax excluded** vergleicht die Summe ohne Steuer. Der Warenkorbtext wiederholt die gewählte Steuerbezeichnung. |
| **Cart value type** | **Products + shipping** | **Products** lässt den Versand aus der verglichenen Summe. |
| **Value** | leer | Der Betrag in der Standardwährung des Shops. |
| **Active** | **Off** | **On** wendet die Zeile an. |
| **Save** | - | Speichert die Regel. |

Unter dem Minimum zeigt der Warenkorb: "To place an order from country: ... your cart must be worth at least ..., while you cart is worth ...". Über dem Maximum: "To place an order from country: ... your cart can't be worth more than ..., while you cart is worth ...".

## 4. Shop-Frontend

Der Kunde öffnet keine eigene Seite. Das Modul spricht auf der Produktseite und im Warenkorb.

Auf der Produktseite, und nur bei einer aktiven Regel **Must order at least X quantity of selected product** für dieses Produkt, kann das Theme zeigen: "You must order at least: ... quantity of this product". Das Theme muss den Produktaktionsbereich ausgeben. Dieses Handbuch hat kein Shop-Bild, weil diese Zeile im Test-Theme nicht bestätigt wurde.

Im Warenkorb ist jede verletzte Regel eine Zeile eines roten Hinweises. Namen verlangter oder verbotener Produkte und Kategorien sind Links. Öffnet der Kunde die Zahlung bei einer verletzten Regel, kehrt der Shop zum Warenkorb zurück und zeigt denselben Hinweis.

Ein Kunde auf der Ausschlussliste sieht keine dieser Meldungen und wird nicht zurückgeschickt.

Eine Front-Adresse zum Kopieren gibt es nicht. Ein Formular, in dem der Kunde eine Regel annimmt oder ablehnt, gibt es nicht.

## 5. Probleme

**Die fünf Einträge fehlen unter Katalog.** Das Modul ist nicht installiert oder wurde deinstalliert. Installieren Sie es im **Module Manager** erneut. Alte Regeln kommen mit.

**Der blaue Hinweis sagt Price Rules, und unter Price Rules gibt es keinen Cart-Conditions-Eintrag.** Nutzen Sie die fünf Links im Hinweis oder **Katalog**. Der Menüelternteil ist Katalog.

**Eine gespeicherte Regel tut nichts.** **Active** ist **Off**, der Kunde steht auf der Ausschlussliste, oder er ist nicht in der gewählten Gruppe. Ein nicht angemeldeter Besucher wird als Gruppe Visitor geprüft. Öffnen Sie die Zeile, setzen Sie **Active** auf **On** und testen Sie mit einem Kunden dieser Gruppe.

**Eine Wertregel bleibt still.** Die Kategorie fehlt im Warenkorb. Legen Sie ein Produkt aus dieser Kategorie hinein. Die verglichene Summe ist brutto.

**Zwei Ländermengenregeln ignorieren das Land.** **Target country** ist verborgen, solange **Condition** nicht eine der zwei Zeilen "from Y category" ist. Wählen Sie eine davon, oder nutzen Sie **Cart value by country conditions** für ein Geldbetragslimit.

**Same calendar month blockiert November und November.** Die Jahre unterscheiden sich. Der 5. November 2026 und der 5. November 2027 sind verschieden. Das Produkt muss außerdem ohne Bestand und mit künftigem **Availability date** sein. Produkte auf Lager werden nicht verglichen.

**Check now zeigt nichts, oder die Warnung erscheint nie.** Der Shop-Server kann die entfernte MyPresta-Adresse nicht öffnen. **Check now** meldet nur eine Version. Es lädt die Datei nicht herunter und installiert sie nicht. Öffnen Sie **Module page** und holen Sie die neue Datei dort.

**Der Warenkorbhinweis fehlt, und die Zahlung kehrt trotzdem zum Warenkorb zurück.** Das Theme gibt den Warenkorbblock nicht aus. Die Rückkehr zum Warenkorb läuft trotzdem. Überschreiben Sie die Warenkorbvorlage im Theme oder prüfen Sie, ob das Theme den Warenkorb-Hook ausgibt.

**Die Deinstallation hat das Menü entfernt, und eine spätere Installation zeigt die alten Regeln.** So arbeitet die Deinstallation. Löschen Sie die Zeilen in den Listen vor der Deinstallation, wenn das Modul danach leer sein soll.

## 6. Für Entwickler

### 6.1 Überblick

Hauptklasse `cartcon`, Version 2.1.9, Listenname **Cart Conditions**, Autor MyPresta.eu, Tab `advertising_marketing`. `cartconPrestashopNewCompatibility` erweitert `cartcon` für die Preisformatierung und ist nicht die Modulinstanz. `psversion()` bildet Major 8 und höher auf den 1.7-Zweig für einige Back-Office-Markup-Entscheidungen ab. Es gibt kein `enable()`- oder `disable()`-Override.

`getRestrictions()` liest aktive Zeilen des aktuellen Shops, überspringt Kunden aus `CARTCON_CUSTOMERS` und füllt `errors_cartcon`. `hookDisplayShoppingCart` gibt diese Liste aus. `hookDisplayPaymentTop` leitet zum Warenkorb mit `cartcon=show` um, wenn die Liste nicht leer ist. `hookDisplayProductActions` gibt eine Mindestmenge nur für `cartcon_quantity.c_type = 2` dieser Produkt-ID aus.

### 6.2 Dateien

- `cartcon.php` - Installation, Konfigurationsformulare, Prüfungen, Hooks.
- `lib/prestashop9compatibility.php` - `cartconPrestashopNewCompatibility`.
- `controllers/admin/AdminCartConditionController.php` - Must-have und Can't-have.
- `controllers/admin/AdminCartValueConditionController.php` - Kategoriemindestbetrag.
- `controllers/admin/AdminCartQuantityConditionController.php` - Mengenregeln.
- `controllers/admin/AdminCartAssociationsConditionController.php` - Paare.
- `controllers/admin/AdminCartCountryConditionController.php` - Länderbeträge.
- `models/CartCondition.php`, `CartValueCondition.php`, `CartQuantityCondition.php`, `CartAssociationsCondition.php`, `CartCountryCondition.php` - Objektmodelle.
- `views/templates/front/displayShoppingCart.tpl` - roter Hinweis.
- `views/templates/front/productActions.tpl` - Mindestmenge auf der Produktseite.
- `views/templates/admin/script.tpl` - Verhalten des Mengenformulars.
- `views/templates/admin/search-attribute-value.tpl` - Attributsuche, sichtbar bei Mengentyp 7.
- `lib/searchTool/searchTool.php` - `initTool()` injiziert nur Skripte. Es rendert kein Panel.

### 6.3 Controller

Alle fünf Admin-Controller erweitern `ModuleAdminController`. `createMenu()` legt je Sprache einen Tab mit englischem Namen an, Elternteil `AdminCatalog` (`Sell > Catalog` unter PrestaShop 9). Klassen: `AdminCartCondition`, `AdminCartValueCondition`, `AdminCartQuantityCondition`, `AdminCartAssociationsCondition`, `AdminCartCountryCondition`. Einen Front-Controller gibt es nicht. Das einzige Front-Flag, das das Modul liest, ist `cartcon=show`, gesetzt von der Zahlungsweiterleitung.

`script.tpl` deaktiviert **Target item** und setzt den Wert auf das Wort `Cart` für Mengentypen 4, 5, 8, 9, 15 und 16. Die Länderauswahl wird für Typen 8 und 9 gezeigt und vom nächsten Block verborgen, außer der Typ ist 10 oder 11. Sichtbares Ergebnis: ein Länderfeld nur für Typen 10 und 11. Typ 7 zeigt `.searchAttributeValue`.

Das Zuordnungsskript verbirgt `.subcatt` und `.subcata` bei jedem Typ. Bedingungs-ID 4 ist nur für Kategorie-Kategorie (Typ 3) aktiv. ID 5 ist nur für Produkt-Produkt (Typ 1) sichtbar. IDs 3, 4 und 5 verbergen **Associated item (2)**. `getRestrictions()` vergleicht Zuordnungs-`c_value` 1, 2, 3 und 4. Es vergleicht `c_value` 5 nicht.

### 6.4 Hooks

- `displayHeader` - Front-CSS und JS sowie der Ajax-Aufruf `getCartConditions`.
- `displayShoppingCart` - Hinweisliste.
- `displayProductActions` - Hinweis zur Mindestmenge.
- `displayPaymentTop` - Rückkehr zum Warenkorb, wenn ein Fehler existiert.
- `actionAdminControllerSetMedia` - Admin-Assets.

Das Modul registriert keine eigenen Hooks.

### 6.5 Overrides

Keine. Kein Klassen- oder Controller-Override.

### 6.6 Datenbank

Tabellen mit Shop-Präfix. `inconsistency()` / `maybeUpdateDatabase()` ergänzen fehlende Spalten in `installdb()` und über die Update-Schaltfläche. Sie laufen nicht bei jedem Aufruf der Konfiguration. Die Deinstallation löscht die Tabellen nicht.

| Tabelle | Inhalt |
|---|---|
| `cartcon` | `id_cartcon`, `c_type`, `c_value`, `c_option`, `active` Standard 1, `id_shop` später ergänzt. Keine Kundengruppe. |
| `cartcon_value` | `id_cartcon_value`, `c_type`, `c_target`, `c_value`, `active`, `c_only_if_in_cart` Standard 0, `c_group`, `id_shop`. `c_only_if_in_cart` steht nicht im Formular. |
| `cartcon_quantity` | `id_cartcon_quantity`, `c_type`, `c_target`, `c_value`, `active`, `c_only_if_in_cart` Standard 0, `c_group`, `id_shop`, `multiply` Standard 0, `c_country` Standard 0. |
| `cartcon_ass` | `id_cartcon_ass`, `c_type`, `c_target1`, `c_target2`, `c_value`, `active`, `c_group`, `id_shop`, `subcatt` Standard 0, `subcata` Standard 0. Die Kategoriezuordnung liest `subcatt` und `subcata`, wenn sie 1 sind. Das Formular verbirgt beide Schalter. |
| `cartcon_country` | `id_cartcon_country`, `c_type`, `c_target`, `c_value`, `active`, `c_group`, `id_shop`, `c_tax` Standard 1, `c_cartValueType` Standard 1. |

Neue HelperForm-Masken senden **Active** als 0, weil Off gewählt ist. Der Spaltenstandard 1 gilt nur, wenn die Spalte weggelassen wird.

### 6.7 Schlüssel und Übersetzungen

| Schlüssel | Wenn er fehlt |
|---|---|
| `CARTCON_CUSTOMERS` | leer. Kunden-IDs, durch Komma getrennt. Diese Kunden verlassen `getRestrictions()` sofort. |
| `ccon_visibility_rule` | `0` heißt nicht ausschließen. `1` überspringt gewählte Produkte und Kategorien. |
| `ccon_visibility_products` | leere Produkt-ID-Liste. |
| `ccon_visibility_cat` | leere Kategorie-ID-Liste. |
| `CARTCON_FUTURE` | nicht gesetzt, gilt als aus. `1` startet den Datumsvergleich. |
| `CARTCON_FUTURE_MODE` | fehlend wird zu `0` (**Exact date**). `1` gruppiert mit `date('Y-m')`. Verglichene Produkte brauchen `stock_quantity <= 0` und `available_date` strikt in der Zukunft. Mehr als ein verschiedener Schlüssel blockiert die Bestellung. |
| `mypresta_updates` | `0` schaltet die automatische Warnung aus. `1` schaltet sie ein. |
| `update_cartcon` | Zeitstempel der letzten Prüfung. |
| `updatev_cartcon` | Versionsstring der letzten Prüfung. |

Die Prüfung nutzt `allow_url_fopen` und `file_get_contents` gegen `dev.mypresta.eu`. Shop-Übersetzungen liegen in `translations/{iso}.php`. Menünamen schreibt `createMenu()` auf Englisch für jede Sprache, sie laufen nicht über eine Übersetzungsdatei. Feldbeschreibungen stehen in den `l()`-Aufrufen der Controller und in den HelperForm-`desc`-Zeichenketten in `cartcon.php`. `getCustomerGroups()` bildet Warenkorb `id_customer` 0 auf Gruppen-ID 1 ab. Der Gastzweig läuft nur, wenn `id_customer` nicht gesetzt ist.

### 6.8 Erweitern

Überschreiben Sie aus dem Theme `views/templates/front/displayShoppingCart.tpl` und `views/templates/front/productActions.tpl`. Ruft das Theme `displayShoppingCart` oder `displayProductActions` nie auf, gibt es nichts zu überschreiben, und der Kunde sieht den Hinweis nicht. Die Zahlungsweiterleitung läuft weiter.

## 7. Hilfe

Modulseite: [Cart Conditions Pro](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html).

Schreiben Sie zu diesem Modul, indem Sie sich im Kundenkonto auf mypresta.eu anmelden, das Kontaktformular öffnen und **Support for paid modules** wählen. Das Formular sagt, dass für kostenpflichtige Module eine Anmeldung nötig ist. Nach der Anmeldung wählen Sie dieses Modul aus der Kaufhistorie.

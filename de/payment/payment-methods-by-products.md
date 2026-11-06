---
title: "Zahlungsarten nach Produkt - Dokumentation und Anleitung für Händler"
description: "Diese Anleitung zeigt, wie Sie Zahlungsarten je Produkt setzen, sie im Warenkorb zusammenführen und eine Kasse korrigieren, die noch die falsche Methode anzeigt."
sidebar:
  label: "Zahlungsarten nach Produkt - Dokumentation und Anleitung für Händler"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Payment methods by products auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/payment-methods-by-products/)
>
> ---


## 1. Anforderungen

Prüfen Sie diese Punkte vor der Installation.

- Verwenden Sie PrestaShop 1.7.0.0 oder neuer, einschließlich PrestaShop 8 und 9. Das Modul akzeptiert Shopversionen bis 9.99.99.
- Behalten Sie die PHP-Version, die diese PrestaShop-Version verlangt. Der Installer prüft PHP nicht extra.
- Aktivieren Sie die PHP-Erweiterung cURL, wenn die Update-Prüfung MyPresta.eu erreichen soll. Fehlt cURL, versucht die Prüfung die Adresse über die Server-Einstellung für entfernte Lesezugriffe. Die Zahlungsregeln selbst brauchen kein cURL.
- Es ist kein weiteres PrestaShop-Modul nötig. Die Methodenliste kommt aus den bereits installierten Zahlungsmodulen. Ohne installiertes Modul sind die Kontrollkästchen leer.
- Installieren und aktivieren Sie mindestens ein Zahlungsmodul, wenn eine Methode an der Kasse erscheinen soll.
- Das Modul verlangt kein externes Konto.

Die Modultexte im Backoffice sind Englisch. Nur Polnisch wird mitgeliefert. Die Namen in dieser Anleitung sind die deutschen Bezeichnungen der englischen Beschriftung.

## 2. Installation

1. Öffnen Sie **Module**, dann **Modul-Manager**.
2. Klicken Sie auf **Modul hochladen** und laden Sie die ZIP-Datei hoch.
3. Klicken Sie bei **Payment options by products** auf **Installieren**.

Die Installation bewirkt Folgendes:

- Sie legt **Payment - Product associations** unter **Verbessern**, dann **Zahlung** an. Fehlt dieses Menü, liegt der Eintrag unter **Verbessern**.
- Sie legt die Tabelle an. Eine Zeile ist ein Produkt, ein Zahlungsmodul, ein Shop und ein Land.
- Sie registriert den Kassenfilter und den Reiter auf der Produktseite.
- Sie kopiert die Kassen-Überschreibung. PrestaShop muss Überschreibungen erlauben. Sind sie aus, laufen der Produktreiter und der Kassenfilter trotzdem. Der gelbe Hinweis auf der Konfigurationsseite sagt das.
- Sie leert den Shop-Cache nicht. Leeren Sie ihn unter **Erweiterte Parameter**, **Leistung**, nur wenn ein alter Bildschirm sichtbar bleibt.
- Sie legt keine Produktregel an. Die Kasse bleibt unverändert, bis Sie eine Regel speichern.

**Konfigurieren** im **Modul-Manager** öffnet die Einstellungen. Der Menüpunkt **Payment - Product associations** öffnet die Regelliste.

Deinstallation:

- Entfernt den Menüpunkt **Payment - Product associations**.
- Entfernt die Kassen-Überschreibung und die registrierten Hooks.
- Entfernt die gespeicherte Modulversion der Aktualisierung.
- Löscht die gespeicherten Produktregeln nicht. Eine neue Installation liest diese Zeilen wieder.
- Schaltet die shopweiten Update-Hinweise anderer MyPresta-Module nicht ab.
- Lässt den Modulordner stehen, bis Sie ihn im **Modul-Manager** oder auf dem Server löschen.

Wenn Sie das Modul im **Modul-Manager** deaktivieren, stoppt der Kassenfilter. Die Regeln bleiben in der Datenbank.

## 3. Konfiguration und Arbeit im Backoffice

Eine Regel ist eine Liste von Zahlungsarten für ein Produkt, im Shop, den Sie bearbeiten, für ein Lieferland oder für alle Länder.

So gehen Sie vor:

1. Öffnen Sie **Konfigurieren** und wählen Sie, wie mehrere eingeschränkte Produkte in einem Warenkorb zusammenkommen. Klicken Sie auf **Save**. Dieser Schritt ist optional. Bis Sie speichern, behält der Shop jede Methode, die mindestens ein eingeschränktes Produkt erlaubt.
2. Öffnen Sie ein Produkt und den Reiter **Payment methods**, oder **Verbessern**, **Zahlung**, **Payment - Product associations**, und legen Sie eine Zeile an.
3. Markieren Sie die Methoden, die bleiben sollen, wenn dieses Produkt im Warenkorb liegt. Wählen Sie **All countries** oder ein Land. Speichern Sie.
4. An der Kasse liest der Shop die Lieferadresse und blendet Methoden aus, die die Regeln nicht erlauben.

Ein Produkt ohne gespeicherte Regel entfernt keine Zahlungsarten. **Free order** bleibt, wenn es die einzige Methode bei einem Warenkorb mit Summe null ist.

Es gibt keinen Bestellstatus. Das Ergebnis ist die Zahlungsliste auf der Kassenseite.

Die Aufnahmen in diesem Kapitel zeigen das englische Backoffice. Die Bildunterschrift nennt den Namen aus dieser Anleitung.

### 3.1 Modulkonfiguration

Öffnen Sie **Module**, **Modul-Manager**, **Payment options by products**, **Konfigurieren**.

Oben stehen zwei Hinweise. Der erste Link öffnet **Payment - Product associations**. Der zweite verweist auf den Reiter **Payment methods** am Produkt. Keiner der Hinweise speichert eine Regel.

Sind Überschreibungen aus, sagt der gelbe Hinweis: „Overrides are disabled. Checkout filtering still runs through the payment options hook.“ Lassen Sie sie aus, wenn Sie nur PrestaShop 8 oder 9 nutzen. Schalten Sie sie unter **Erweiterte Parameter**, **Leistung** ein, nur wenn Sie auch die ältere Kassen-Überschreibung brauchen.

Das Panel **Settings** erklärt die Landesregel und den Kombinationsmodus. Der Text über der Auswahl speichert nichts.

![Settings](https://mypresta.eu/docs/images/docs/pobp-configure-settings.webp)

**Konfigurieren**, Panel **Settings**. Der blaue Text erklärt die Länder. Die Auswahl ist **How to get available payment methods?**.

| Feld | Beim Start | Wirkung |
|---|---|---|
| **How to get available payment methods?** | **Show all payment methods from products**, bis Sie eine andere Wahl speichern | **Show the same payment methods available for all products in cart** behält eine Methode nur, wenn jedes eingeschränkte Produkt im Warenkorb sie erlaubt. **Show all payment methods from products** behält eine Methode, wenn mindestens ein eingeschränktes Produkt sie erlaubt. Ein Produkt ohne Regel entfernt keine Methode. |
| **Save** | — | Speichert nur diese Wahl. Es ändert keine Produktregel. Die Seite lädt mit dem gewählten Wert neu. |

### 3.2 Payment - Product associations

Öffnen Sie **Verbessern**, **Zahlung**, **Payment - Product associations**. Der Hinweis oben wiederholt, dass dieselbe Regel am Produkt im Reiter **Payment methods** liegt.

Die Liste zeigt eine Zeile je Produkt im aktuellen Shop.

![Payment - Product associations](https://mypresta.eu/docs/images/docs/pobp-associations-list.webp)

**Payment - Product associations** ohne Zeilen. Die Spalten sind **ID**, **Product**, **Payment** und **Country**. Das Plus ist **Add new**.

| Spalte | Inhalt |
|---|---|
| **ID** | Die Zeilennummer. Das ist nicht die Produktnummer. |
| **Product** | Produktnummer und Name. |
| **Payment** | Jede für dieses Produkt gespeicherte Methode, untereinander. |
| **Country** | **All countries** oder das gespeicherte Lieferland. Der Spaltentext sagt: Ein gewähltes Land gilt nur bei einer Lieferadresse in diesem Land. **All countries** gilt bei jeder Lieferadresse. |

**Add new** öffnet ein leeres Formular. **Edit** öffnet das Formular dieses Produkts. **Delete** löscht diese eine Datenbankzeile, nicht jede Methode in der Spalte **Payment**. **Delete selected** macht dasselbe für die markierten Zeilen. Eine leere Auswahl speichert dieses Formular nicht. Löschen Sie die übrigen Zeilen, oder leeren Sie die Regel im Produktreiter, wo eine leere Auswahl erlaubt ist.

Suche und Filter der Liste sind die üblichen Backoffice-Filter dieser Spalten.

### 3.3 Formular der Zuordnung

Bei **Add new** oder **Edit**:

![Zuordnungsformular](https://mypresta.eu/docs/images/docs/pobp-associations-form.webp)

**Add new**, für dieses Bild ausgefüllt und nicht gespeichert. **ID Product** ist 1. **Payment methods** und **Country** (**All countries**) stehen auf diesem Formular.

| Feld | Beim Start | Wirkung |
|---|---|---|
| **ID Product** | Leer bei einer neuen Zeile. Gefüllt bei der Bearbeitung. | Tragen Sie die Produktnummer ein oder nutzen Sie **Search**. Der Hilfetext sagt: Suche nach Name, ID oder Referenz. **Save** ohne Produkt zeigt „Product is required.“ und schreibt keine Regel. |
| **Payment methods** | Bei einer neuen Zeile nicht markiert. Bei der Bearbeitung sind die bereits gespeicherten Methoden markiert. | Markieren Sie die Methoden, die an der Kasse bleiben, wenn der Warenkorb dieses Produkt enthält und das Lieferland zum Land darunter passt. Die Beschriftung zeigt den Namen des Zahlungsmoduls. |
| **Country** | **All countries** | Wenn Sie ein Land wählen, gelten die markierten Methoden nur, wenn die Lieferadresse des Kunden in diesem Land liegt. **All countries** gilt bei jeder Lieferadresse. |
| **Save** | — | Ersetzt alle für dieses Produkt in diesem Shop gespeicherten Methoden durch die Markierungen und das Land dieses Formulars. Ist nichts markiert, zeigt die Seite „There was a problem with form. No payment method selected“ und die alten Zeilen bleiben. |

Ein Produkt hat ein Land. Ein erneutes Speichern ersetzt die vorherigen Methoden dieses Produkts in diesem Shop. Regeln in einem anderen Shop bleiben. Wechseln Sie den Shop-Kontext, bevor Sie dort bearbeiten.

### 3.4 Produktseite

Öffnen Sie **Katalog**, **Produkte**, die Bearbeitung, dann den Reiter **Payment methods**.

![Payment methods am Produkt](https://mypresta.eu/docs/images/docs/pobp-product-tab.webp)

Produkt Hummingbird printed t-shirt, Reiter **Payment methods**. Hier stehen **Country** und **Available payment methods**. Die Häkchen sind nur auf diesem Bild. Das Produkt wurde nicht gespeichert.

| Feld | Beim Start | Wirkung |
|---|---|---|
| **Country** | **All countries**, wenn das Produkt keine Regel hat. Sonst das bereits gespeicherte Land. | Wenn Sie ein Land wählen, gelten die markierten Zahlungsarten nur bei einer Lieferadresse in diesem Land. **All countries** gilt bei jeder Lieferadresse. |
| **Available payment methods** | Nicht markiert, wenn keine Regel existiert. Sonst sind die gespeicherten Methoden markiert. | Markierte Methoden bleiben an der Kasse, wenn der Warenkorb dieses Produkt enthält und das Lieferland zum Land darüber passt. Nichts markiert hebt die Einschränkung für dieses Produkt auf. |

Klicken Sie am Produkt auf **Save**. PrestaShop bestätigt die Produktspeicherung. Die Zahlungsregel wird mit dieser Speicherung für den bearbeiteten Shop geschrieben. Eine leere Auswahl löscht die Regel dieses Produkts in diesem Shop. Das Zuordnungsformular verweigert dagegen das Speichern, wenn nichts markiert ist.

Dieselben Daten stehen in **Payment - Product associations**.

### 3.5 MyPresta-Updates

Unter den Einstellungen auf **Konfigurieren** prüft **MyPresta Updates**, ob eine neuere Datei existiert. Es installiert sie nicht.

![MyPresta Updates](https://mypresta.eu/docs/images/docs/pobp-updates.webp)

**MyPresta Updates**, unter den Einstellungen auf **Konfigurieren**.

| Feld | Beim Start | Wirkung |
|---|---|---|
| **Check updates** | — | **Check now** fragt MyPresta.eu, ob eine neuere Datei existiert. Die Zeile über der Schaltfläche zeigt eine neue Version oder dass das Modul aktuell ist. Es lädt die Datei nicht herunter und installiert sie nicht. |
| **Updates notifications** | Aktiv, bis Sie **Disable** speichern | **Enable** zeigt eine Backoffice-Warnung, wenn eine neuere Version erscheint. **Disable** stoppt diese automatische Prüfung. **Save** speichert die Wahl und zeigt „Update settings saved.“ |
| **Module page** | — | Öffnet die Modulseite auf MyPresta.eu mit dem Changelog. Es speichert keine Einstellung. |
| **Save** | — | Speichert nur **Updates notifications**. |

## 4. Shop-Frontend

Das Modul fügt keinen Block, keine Seite und keine Meldung auf Produkt, Warenkorb oder Kundenkonto hinzu. Dort gibt es nichts im Theme zu ändern.

Der Kunde sieht die Wirkung im Zahlungsschritt der Kasse. Methoden, die die Regeln nicht erlauben, fehlen in der Liste. Methoden ohne Regel und **Free order**, wenn es die einzige Wahl ist, bleiben.

Das Land ist das Land der Lieferadresse. Bevor eine Lieferadresse existiert, gelten nur Regeln mit **All countries**. Eine Regel für ein Land wartet, bis die Lieferadresse in diesem Land liegt.

## 5. Probleme

**Die Zahlungsliste hat sich nicht geändert.** Das Produkt hat keine gespeicherte Regel, oder kein Produkt im Warenkorb hat eine. Öffnen Sie das Produkt, **Payment methods**, markieren Sie die Methoden und speichern Sie das Produkt. Ein Produkt ohne Markierung begrenzt die Kasse nicht.

**Eine Methode fehlt nur für ein Land.** Das Regelland ist nicht **All countries**, und die Lieferadresse liegt in diesem Land. Setzen Sie **All countries**, wenn die Regel bei jeder Lieferadresse gelten soll.

**Eine Methode wird weiter angeboten.** Ein anderes Produkt im Warenkorb erlaubt sie, und **How to get available payment methods?** steht auf **Show all payment methods from products**. Wechseln Sie auf **Show the same payment methods available for all products in cart**, wenn jedes eingeschränkte Produkt die Methode erlauben muss. Ein Produkt ohne Regel blockiert sie nicht.

**Auf der Konfiguration steht „Overrides are disabled…“, und Sie wissen nicht, ob gefiltert wird.** In PrestaShop 8 und 9 läuft der Filter weiter. Der gelbe Text sagt, dass der Kassen-Hook filtert. Schalten Sie Überschreibungen nur ein, wenn Sie auch die ältere Überschreibungsdatei brauchen.

**Save bei Payment - Product associations zeigt „Product is required.“** Das Produktfeld ist leer. Suchen Sie das Produkt oder tragen Sie die Nummer ein und klicken Sie erneut auf **Save**.

**Save zeigt „There was a problem with form. No payment method selected“.** Es ist keine Methode markiert. Markieren Sie mindestens eine. Die bisherige Regel wurde nicht ersetzt. Um eine Regel ganz zu entfernen, nutzen Sie den Reiter **Payment methods** am Produkt und speichern Sie ohne Markierung.

**Delete in der Liste hat nur eine Methode entfernt.** **Delete** löscht die einzelne Zeile hinter der Linie, während **Payment** jede Methode ausgibt. Öffnen Sie **Edit** und **Save**, um den ganzen Satz neu zu schreiben, oder löschen Sie, bis das Produkt aus der Liste verschwindet.

**Free order ist die einzige Methode und steht nicht in der Regel.** Ein Warenkorb mit Summe null behält **Free order**. Das Modul entfernt diese einzelne Methode nicht.

**Die Regel eines Shops fehlt im anderen.** Regeln werden je Shop gespeichert. Wechseln Sie den Shop in der Multishop-Kopfzeile und speichern Sie die Regel dort.

## 6. Für Entwickler

### 6.1 Überblick

Hauptklasse `pobp`, Version `1.4.0`, Anzeigename **Payment options by products**, Autor MyPresta.eu, Tab `administration`. Kompatibilität `1.7.0.0` bis `9.99.99`.

Eine Zeile in `ps_pobp` ist ein erlaubtes Zahlungsmodul für ein Produkt, einen Shop und ein Land (`id_country` `0` bedeutet jedes Land). Die Kasse liest Warenkorbprodukte und Lieferadresse in `pobp::filterPaymentOptions()`. Der Hook `actionPresentPaymentOptions` entfernt Modulschlüssel, die der Filter verworfen hat. Die Überschreibung `PaymentOptionsFinder::find()` liefert denselben Filter, wenn das Modul aktiv ist. `pobp_innerjoin` wahr bedeutet die Schnittmenge der eingeschränkten Produkte. Jeder andere Wert, auch ein fehlender Schlüssel, bedeutet die Vereinigung. Produkte ohne passende Zeilen werden ignoriert. Der Schlüssel `free_order` wird nie entfernt. Eine Liste, die nur `free_order` enthält, bleibt unverändert.

### 6.2 Dateien

| Datei | Aufgabe |
|---|---|
| `pobp.php` | Installation, Einstellungsformular, Kassenfilter, Produktreiter. |
| `lib/updatesChecker.php` | Klasse `pobpUpdate`. Update-Prüfung und Formular MyPresta Updates. |
| `lib/searchTool/searchTool.php` | Produktsuche im Zuordnungsformular. |
| `models/pob.php` | ObjectModel `pob` und `replaceForProduct()`. |
| `controllers/admin/AdminPobpController.php` | Liste und Formular der Zuordnungen. |
| `override/classes/checkout/PaymentOptionsFinder.php` | `find()` ruft `filterPaymentOptions()` auf. |
| `upgrade/upgrade-1.4.0.php` | Ruft `ensureModuleComplements()` auf und speichert `POBP_VERSION`. |
| `translations/pl.php` | Polnische Texte. |

Es gibt keinen Front-Controller und kein Front-Template.

### 6.3 Controller

`AdminPobpController` erweitert `ModuleAdminController`. Tab-Klasse `AdminPobp`, Elternteil `AdminParentPayment`, oder `IMPROVE`, wenn dieses Elternteil fehlt. Icon `credit_card`. Sichtbarer Name **Payment - Product associations**.

Die Liste gruppiert mit einer Unterabfrage auf `MIN(id_pobp)` je Produkt und Shop. `processAdd()` und `processUpdate()` rufen `pob::replaceForProduct()` auf. Eine leere Methodenliste oder ein fehlendes Produkt gibt false zurück und ersetzt keine Zeilen. Texte laufen über `$this->module->l(..., 'AdminPobpController')`.

Die Modulkonfiguration ist `getContent()` in `pobp`, kein eigener Controller.

### 6.4 Hooks

Registriert in `registerHooks()`:

| Hook | Aufgabe |
|---|---|
| `actionPresentPaymentOptions` | Entfernt vom Filter verworfene Zahlungsmodule. Das Array wird an Ort und Stelle geändert. |
| `actionProductFormBuilderModifier` | Fügt den Reiter `pobp` (Land und Zahlungen) am Produktformular hinzu. |
| `actionAfterUpdateProductFormHandler` | Schreibt `form_data['pobp']` für das gespeicherte Produkt. |
| `actionAfterCreateProductFormHandler` | Dieselbe Speicherung nach dem Anlegen eines Produkts. |

Es gibt kein eigenes `enable()` oder `disable()`. Deaktivieren deregistriert die Hooks. Die Überschreibung lädt weiter und gibt die Elternliste zurück, wenn `Module::isEnabled('pobp')` falsch ist.

Der erste Backoffice-Aufruf nach dem Hochladen ruft `ensureModuleComplements()` auf, wenn `POBP_VERSION` von der Dateiversion abweicht.

### 6.5 Überschreibungen

`override/classes/checkout/PaymentOptionsFinder.php` ersetzt nur `find()`. Es überschreibt weder `present()` noch `findFree()`.

### 6.6 Datenbank

| Tabelle | Inhalt |
|---|---|
| `ps_pobp` | `id_pobp`, `id_product`, `id_payment` (Modul-ID), `id_shop`, `id_country`. `id_country` ergänzt `inconsistency()`, wenn die Spalte fehlt. `0` bedeutet jedes Land. |

Die Deinstallation löscht `ps_pobp` nicht. Die Installation nutzt `CREATE TABLE IF NOT EXISTS`, eine neue Installation behält alte Zeilen.

### 6.7 Schlüssel und Übersetzungen

| Schlüssel | Wenn er fehlt |
|---|---|
| `pobp_innerjoin` | Gilt als aus. Die Kasse nutzt die Vereinigung der eingeschränkten Produkte. |
| `POBP_VERSION` | Die nächste Backoffice-Anfrage führt `ensureModuleComplements()` aus und speichert danach die Dateiversion. |
| `mypresta_updates` | Gilt als an. `0` stoppt die automatische Update-Prüfung. Der Schlüssel ist mit anderen MyPresta-Modulen geteilt. |
| `update_pobp` | Zeitstempel der letzten Prüfung. |
| `updatev_pobp` | Versionszeichenkette des Update-Servers. |

Shoptexte laufen über `$this->l()`. Das Update-Panel nutzt die Quelle `updatesChecker`. Der Zuordnungs-Controller nutzt `AdminPobpController`. Polnisch liegt in `translations/pl.php`. Eine weitere Sprache legen Sie als `translations/{iso}.php` mit derselben Schlüsselform an.

`key.php` im Modulordner kann `$this->mkey` setzen. Fehlt die Datei, sendet die Prüfung `nlc`.

### 6.8 Erweitern

Das Frontend rendert kein Modul-Template, das Theme hat für dieses Modul nichts zu überschreiben. Für die Kassenliste bleiben Sie beim Payment-Options-Hook oder bei der Überschreibung von `PaymentOptionsFinder`. Für den Produktreiter erweitern Sie `hookActionProductFormBuilderModifier` und behalten die Formularschlüssel `pobp`, sonst ignoriert der Speicher-Hook die Daten.

## 7. Hilfe

Modulseite: [https://mypresta.eu/modules/payment-process/payment-methods-by-products.html](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)

Schreiben Sie zu diesem Modul, indem Sie sich im Kundenkonto auf mypresta.eu anmelden, das Kontaktformular öffnen und das Thema **Support for paid modules** wählen. Das Formular sagt, dass für dieses Thema eine Anmeldung nötig ist. Nach der Anmeldung wählen Sie dieses Modul aus der Kaufhistorie.

---
title: MyFAQ Free - Dokumentation und Benutzerhandbuch
sidebar:
  label: MyFAQ Free - Dokumentation und Benutzerhandbuch
description: Anleitung zur Einrichtung und zur Fehlersuche für Shops, die MyFAQ Free bereits haben.
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Free Product FAQ auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/free-product-faq.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/free-product-faq/)
>
> ---


## 1. Anforderungen

MyFAQ Free läuft innerhalb von PrestaShop. Es braucht kein weiteres Modul.

- PrestaShop 1.7.0.0 bis PrestaShop 9.
- Die PHP-Version, die diese PrestaShop-Version verlangt. Das Modul prüft die PHP-Version nicht selbst.
- Keine zusätzliche PHP-Erweiterung ist nötig. Die Update-Prüfung nutzt cURL, wenn der Server es hat. Fehlt cURL, liest die Prüfung die Adresse nur, wenn der Server entfernte Adressen lesen darf.
- Kein anderes Modul ist nötig. Die Produktseite des Themes muss die Produktfußzeile oder die zusätzlichen Produktregister drucken, damit der Kunde die Fragen sieht.
- Für die drei Fragen brauchen Sie kein Konto bei einem externen Dienst. Die PayPal-Spende auf der Konfigurationsseite ist freiwillig. Die Update-Prüfung braucht nur, dass der Shop MyPresta.eu erreicht.

Jedes Produkt speichert drei Fragen. Einen Import gibt es nicht, deshalb startet ein großer Katalog keinen Lauf und hebt den Speicher, den das Modul verlangt, nicht an.

## 2. Installation

1. Öffnen Sie im Backoffice **Module**, dann **Modul-Manager**.
2. Laden Sie das Zip hoch und klicken Sie auf **Installieren**.
3. Öffnen Sie **Konfigurieren** bei **MyFAQ Free**. Die Seite öffnet sich auf **Unlock Pro**. In der Leiste stehen außerdem **Settings** und **Updates**.
4. MyFAQ Free fügt keinen Eintrag im linken Menü hinzu. Die Fragen schreiben Sie am Produkt.

Die Installation leert den PrestaShop-Cache nicht. Zeigt die Produktseite nach einem Update noch das alte Layout, leeren Sie den Cache unter **Erweiterte Parameter**, **Leistung**.

Zum Abschalten nutzen Sie den Schalter im **Modul-Manager**. Die Produktseite druckt die Fragen nicht mehr, und die Produktbearbeitung zeigt den FAQ-Block nicht mehr. Fragen und Platzierung bleiben. Schalten Sie das Modul wieder ein, werden sie wie zuvor verwendet. Das Modul hat keinen eigenen Ein- oder Ausschalter.

Zum Entfernen klicken Sie auf **Deinstallieren** und bestätigen. Die Deinstallation entfernt die Fragen, die Platzierung, den Registertitel und die Überschrift. Die versteckte Seite, die die Fragen speichert, wird entfernt. Die Moduldateien bleiben auf dem Server, bis Sie das Modul löschen. Eine neue Installation startet mit leeren Fragen, **Product footer**, dem Registertitel FAQ und einer leeren Überschrift. Die alten Fragen kommen nicht zurück. Der Schalter für Update-Hinweise ist mit anderen MyPresta-Modulen geteilt und bleibt, wie Sie ihn gelassen haben.

## 3. Konfiguration und tägliche Arbeit

Die Bildschirme in dieser Anleitung sind auf Englisch. Danach verwende ich die Namen aus dieser Anleitung und zitiere die Beschriftung so, wie sie im Backoffice steht.

Die Fragen schreiben Sie am Produkt, nicht auf der Modulseite. Öffnen Sie **Katalog**, **Produkte** und bearbeiten Sie das Produkt. Hat der Shop mehrere Läden, verlangt die Produktseite, dass Sie im Multishop-Kopf einen Laden wählen. Öffnen Sie den Reiter **Modules** und wählen Sie unter **Module to configure** **MyFAQ Free**. Tragen Sie bis zu drei Fragen ein, setzen Sie **Show on the product page** und klicken Sie auf **Save these questions**. Ein Slot mit leerer Frage bleibt von der Produktseite weg.

Auf der Modulseite wählen Sie nur, wo der Block gedruckt wird und wie er heißt. **Product footer** druckt das Akkordeon unter dem Produkt. **Product tab** fügt ein Produktregister hinzu und lässt die Fußzeile leer. Ein Produkt ohne Frage zeigt an beiden Stellen nichts.

Der Kunde öffnet das Produkt, klickt eine Frage und liest die Antwort. Es gibt kein Formular, mit dem der Kunde eine neue Frage schickt. Der Weg endet, wenn die Produktseite das Akkordeon zeigt, oder wenn das Produkt nichts zu zeigen hat.

Öffnen Sie **Module**, **Modul-Manager**, **MyFAQ Free**, **Konfigurieren**. Über der Leiste steht **I am developing this module for free - if you want** und der Knopf **send me a donation**. Darunter liegt ein Streifen mit anderen Modulen. Der Hinweis unter der Leiste sagt, dass die Fragen an jedem Produkt gesetzt werden.

### 3.1 Unlock Pro

![Unlock Pro](https://mypresta.eu/docs/images/docs/myfaqfree-configure-unlock.webp)

Der Bildschirm ist der Bereich **Unlock Pro**, mit der Spendenzeile über der Leiste.

**Unlock Pro** speichert keine Einstellung und schreibt keine Fragen. Die Zeile unter der Leiste heißt **MyFAQ without the three-question limit**. Sie sagt, dass MyFAQ jede schon geschriebene Frage behält und den Katalog, den KI-Schreiber und die API hinzufügt, und dass die Fragen am Produkt im kostenlosen Modul bleiben, bis Sie sie verschieben.

Der Kasten **The full FAQ for the catalogue** listet, was das kostenpflichtige Modul hinzufügt, und endet mit **See MyFAQ**. Der Knopf öffnet die Seite des kostenpflichtigen Moduls in einem neuen Tab. Dieser Reiter speichert nichts für das kostenlose Modul.

### 3.2 Settings

![Settings](https://mypresta.eu/docs/images/docs/myfaqfree-configure-settings.webp)

Der Bildschirm ist der Bereich **Settings**. Das Bild zeigt einen Shop, der bereits **Product tab** und eine Überschrift gespeichert hat. Eine frische Installation nutzt die Werte in der Tabelle.

Die Zeile unter der Leiste heißt **Where the three questions are shown**. Sie sagt, dass das kostenlose Modul die FAQ an jedem Produkt schreibt, höchstens drei Fragen, und dass Sie hier nur die Produktfußzeile oder ein Produktregister und die Namen des Blocks wählen.

Der Formulartitel ist **Placement**.

| Feld | Am Start | Was es tut |
|---|---|---|
| **Show the FAQ** | Product footer | **Product footer** druckt das Akkordeon unter dem Produkt. **Product tab** fügt ein Produktregister hinzu und lässt die Fußzeile leer. Ein Produkt ohne Frage zeigt an beiden Stellen nichts. |
| **Tab title** | FAQ in jeder Sprache | Name des Produktregisters, wenn **Show the FAQ** auf **Product tab** steht. Füllen Sie jede Sprache über die Sprachschaltfläche. Eine leere Sprache zeigt FAQ. |
| **Heading** | leer | Titel über den Fragen, in der Fußzeile und im Register. Füllen Sie jede Sprache über die Sprachschaltfläche. Leer lässt nur die Fragen stehen. |

Klicken Sie auf **Save**. Die Seite zeigt **Settings saved.**

Die Sprachschaltfläche zeigt die Sprachen dieses Shops. Im Shop auf dem Bild sind das Englisch, Französisch und Polnisch.

### 3.3 Updates

![Updates](https://mypresta.eu/docs/images/docs/myfaqfree-configure-updates.webp)

Der Bildschirm ist der Bereich **Updates**.

Die Zeile unter der Leiste heißt **Newer versions of MyFAQ Free**. Sie sagt, dass die Prüfung eine Version meldet und das Einspielen des Pakets ein manueller Download bleibt.

Der Formulartitel ist **MyPresta Updates**.

| Feld | Am Start | Was es tut |
|---|---|---|
| **Check updates** | **Check now** | Prüft von Hand, ob auf den Servern von MyPresta.eu eine neuere Version dieses Moduls liegt. Der Knopf lädt das Paket nicht herunter und installiert es nicht. Nach der Prüfung steht neben dem Knopf **New version available!** oder **Module is up to date!** |
| **Updates notifications** | Enable | Eingeschaltet prüft MyPresta.eu automatisch und zeigt einen Hinweis auf neue Versionen dieses Addons. **Disable** stoppt diese automatische Prüfung. Der Schalter ist geteilt: andere MyPresta-Module in diesem Shop nutzen denselben Schalter. Die automatische Prüfung läuft etwa alle drei Tage, solange das Backoffice benutzt wird. |
| **Module page** | ein Link namens **MyFAQ Free** | Direkter Link zur offiziellen Addon-Seite, auf der Sie Änderungen am Modul lesen können (Changelog). Der Link öffnet [https://mypresta.eu/](https://mypresta.eu/). |

Klicken Sie auf **Save**. Die Seite zeigt **Update settings saved.**

Wurde eine neuere Version gemeldet und sind die Hinweise an, zeigt das Backoffice **New version available, check http://MyPresta.eu for more informations** und den Link **More details in changelog**. Der Link öffnet dieselbe Adresse wie **Module page**.

### 3.4 Fragen am Produkt

![FAQ am Produkt](https://mypresta.eu/docs/images/docs/myfaqfree-product-block.webp)

Der Bildschirm ist der Block **MyFAQ Free** am Produkt, im Reiter **Modules**. Das Bild zeigt ein Produkt, das schon drei Fragen hat. Ein neues Produkt startet mit leeren Feldern. EN, FR und PL sind die Sprachen dieses Shops.

Öffnen Sie **Katalog**, **Produkte**, bearbeiten Sie das Produkt, öffnen Sie **Modules** und wählen Sie unter **Module to configure** **MyFAQ Free**.

Bei einem noch nicht gespeicherten Produkt sagt der Block **Save the product first** und **The three FAQ slots appear after the product has an id.** Speichern Sie das Produkt und kehren Sie zu diesem Block zurück.

Der Kasten **Three questions on this product** wiederholt den Hinweis auf das kostenpflichtige Modul und endet mit **See MyFAQ**. Er speichert die kostenlosen Fragen nicht.

Darunter sagt **FAQ for this product**: drei Fragen, eine leere Frage bleibt von der Seite weg, und **Save these questions** lässt Sie auf diesem Produkt. Die Sprachschaltflächen wechseln Frage und Antwort. Sie erscheinen, wenn der Shop mehr als eine Sprache hat.

| Feld | Am Start | Was es tut |
|---|---|---|
| **Question 1**, **Question 2**, **Question 3** | drei leere Slots, **Show on the product page** gesetzt | Die drei Slots dieses Produkts in diesem Shop. Der Kunde sieht sie in dieser Reihenfolge. |
| **Show on the product page** | gesetzt | Gesetzt zeigt den Slot, wenn die Frage gefüllt ist. Nehmen Sie das Häkchen weg, um den Text zu behalten und den Slot zu verbergen. |
| **Question** | leer | Die Zeile, die der Kunde anklickt. Das Feld nimmt 512 Zeichen. Eine leere Frage bleibt von der Seite weg. Füllen Sie die Frage in jeder Sprache, in der Sie verkaufen. Eine Sprache mit leerer Frage wird in dieser Sprache nicht gezeigt. |
| **Answer** | leer | Der Text unter der Frage. Ein Zeilenumbruch im Feld wird auf der Produktseite eine neue Zeile. Getippter Text wird als Text gezeigt. |
| **Save these questions** | ein Knopf | Speichert die drei Slots und bleibt auf diesem Produkt. Während des Speicherns sagt die Zeile unter dem Knopf **Saving the three questions…** Nach dem Speichern sagt sie **The three FAQ slots are saved. A slot with an empty question stays off the product page.** |

Außerhalb des Produkts gibt es keine Fragenliste und keine Massenaktion. Löschen Sie das Produkt, werden seine drei Fragen gelöscht. Fragen, die Sie in einem Laden geschrieben haben, erscheinen in einem anderen Laden erst, wenn Sie sie dort schreiben.

## 4. Shop-Frontend

![Fragen auf der Produktseite](https://mypresta.eu/docs/images/docs/myfaqfree-front-tab.webp)

Der Shop-Bildschirm ist auf Englisch.

Der Kunde sieht den Block nur auf einer Produktseite, und nur wenn dieses Produkt mindestens eine Frage hat, die gefüllt ist, **Show on the product page** gesetzt hat und in der Sprache des Kunden geschrieben ist.

Steht **Show the FAQ** auf **Product footer**, sitzt das Akkordeon unter dem Produkt. Steht es auf **Product tab**, steht dasselbe Akkordeon in einem Produktregister und die Fußzeile bleibt leer. Der Registername ist **Tab title**. Ein leerer Registertitel erscheint als FAQ. Das Bild ist das Register in diesem Shop: das Register heißt FAQ, die Überschrift ist **Questions before you buy**.

Die Überschrift, wenn Sie eine eingetragen haben, steht über den Fragen. Die erste Frage ist beim Laden offen. Der Kunde klickt eine Frage, um die Antwort zu öffnen oder zu schließen. Ein Kunde ohne JavaScript sieht jede Antwort. Unter der Liste führt **Powered by MyFAQ for PrestaShop** zum kostenpflichtigen Modul.

Es gibt keine eigene Seite, keine Adresse zum Kopieren und kein Formular für den Kunden. Ein Produkt ohne etwas zum Zeigen druckt keinen Block.

## 5. Probleme

**Das Produkt zeigt keine Fragen.** Die Frage in dieser Sprache ist leer, **Show on the product page** ist nicht gesetzt, das Modul ist aus, oder das Theme druckt die gewählte Stelle nicht. Öffnen Sie das Produkt, prüfen Sie den Slot und bestätigen Sie auf **Settings** **Show the FAQ**. **Product footer** braucht ein Theme, das die Produktfußzeile druckt. **Product tab** braucht ein Theme, das zusätzliche Produktregister druckt. Ein Produkt ohne gefüllte Frage zeigt an beiden Stellen nichts.

**Der Block an einem neuen Produkt sagt Save the product first.** Das Produkt hat noch keine Id. Speichern Sie das Produkt, öffnen Sie es erneut, und die drei Slots erscheinen. Klicken Sie vorher auf **Save these questions**, sagt die Zeile **Save the product first, then add the FAQ.**

**Save these questions endet mit The FAQ could not be saved.** Klicken Sie erneut auf **Save these questions**. Scheitert es weiter, prüfen Sie, ob das Modul installiert ist und ob Ihr Mitarbeiterprofil Produkte bearbeiten darf.

**Die Zeile sagt The FAQ could not reach the shop.** Der Browser hat das Backoffice nicht erreicht. Prüfen Sie die Verbindung und klicken Sie erneut auf **Save these questions**. Während der Anfrage sagt die Zeile **Saving the three questions…**

**Die Frage im Shop ist kürzer als die getippte.** Das Fragenfeld endet bei 512 Zeichen.

**Die Antwort zeigt die getippten Tags.** Die Antwort ist einfacher Text. Ein Zeilenumbruch bleibt. Tags erscheinen als Zeichen.

**Die Fußzeile ist leer, nachdem Sie Product tab gewählt haben.** So arbeitet die Einstellung. **Product tab** lässt die Fußzeile leer und legt das Akkordeon in das Produktregister. Wählen Sie auf **Settings** **Product footer** und klicken Sie auf **Save**, wenn das Akkordeon unter dem Produkt stehen soll.

**Ein anderer Laden zeigt die Fragen nicht.** Die drei Slots gehören zu dem Laden, den Sie bearbeitet haben. Stellen Sie den Multishop-Kopf auf diesen Laden, öffnen Sie das Produkt und schreiben Sie die Fragen dort.

**Die Produktseite im Backoffice verlangt, einen Laden zu wählen.** Die Produktbearbeitung arbeitet in einem Laden zurzeit. Wählen Sie den Laden im Multishop-Kopf und öffnen Sie dann **Modules**.

**Check now sagt Module is up to date!, und Sie haben eine neuere Version erwartet.** Die Prüfung hat keine Version von MyPresta.eu gelesen, oder dieses Paket ist das, das der Server gemeldet hat. Prüfen Sie, ob der Shop MyPresta.eu erreicht, und klicken Sie erneut auf **Check now**. Der Knopf installiert das Paket nie.

**Eine Warnung sagt New version available, check http://MyPresta.eu for more informations.** Die Hinweise sind an und eine neuere Version wurde gemeldet. Öffnen Sie **Updates**, lesen Sie **Module page** und spielen Sie das Paket selbst ein, wenn Sie es wollen. **Disable** bei **Updates notifications** stoppt die Warnung. Der Schalter ist mit anderen MyPresta-Modulen geteilt.

**Der Spendenstreifen bleibt leer.** Der Rest der Konfigurationsseite arbeitet weiter. Schreiben Sie die Fragen am Produkt und setzen Sie die Platzierung unter **Settings**.

## 6. Für Entwickler

### 6.1 Überblick

Hauptklasse `myfaqfree`, Version `1.0.0`, Listenname **MyFAQ Free**, Autor mypresta.eu, Tab `front_office_features`. Die Kompatibilität ist von `1.7.0.0` bis `9.99.99` erklärt.

Die Platzierung wird aus `MYFAQFREE_DISPLAY` gelesen (`footer`, solange der Wert nicht `tab` ist). Registertitel und Überschrift werden je Sprache aus `MYFAQFREE_TAB_TITLE` und `MYFAQFREE_HEADING` gelesen. Die Produktseite lädt höchstens drei aktive Slots des aktuellen Shops und der aktuellen Sprache über `MyfaqfreeRepository::frontItems()` und rendert `views/templates/hook/product.tpl`. Der erste Eintrag erhält im Template `is-open`. Die Antwort wird escaped und durch `nl2br` geschickt.

### 6.2 Dateien

- `myfaqfree.php` — Installation, Konfiguration, Produktpanel, Front-Render.
- `lib/MyfaqfreeRepository.php` — drei Slots, Tabellen, Speichern und Löschen.
- `lib/updatesChecker.php` — Klasse `myfaqfreeUpdate`, Update-Prüfung.
- `lib/prestashop9compatibility.php` — HelperForm-Templateverzeichnisse und `curl_close` vor PHP 8.
- `controllers/admin/AdminMyfaqfreeController.php` — Ajax-Speichern. Der Controller ist ein versteckter Tab.
- `views/templates/admin/configure.tpl` — Unlock Pro, Settings, Updates.
- `views/templates/admin/_pro.tpl` — Kasten des kostenpflichtigen Moduls.
- `views/templates/admin/product.tpl` — drei Slots am Produkt.
- `views/templates/hook/product.tpl` — Akkordeon. Variablen: `mff_heading`, `mff_items` (`id`, `question`, `answer`), `mff_pro_url`.
- `views/js/admin.js` — Sprachwechsel und Speichern am Produkt.
- `views/js/front.js` — Frage öffnen und schließen.
- `views/css/admin.css`, `views/css/front.css`.
- `translations/en.php` — vorhanden und leer. Die englischen Texte sind die Quelltexte.

### 6.3 Controller

`AdminMyfaqfree` erweitert `ModuleAdminController`. Der Tab wird mit `id_parent = -1` angelegt und steht deshalb nicht im linken Menü. Der Klassenname des Tabs ist `AdminMyfaqfree`, die Beschriftung ist MyFAQ Free. `ajaxProcessSave` reicht an `myfaqfree::ajaxProcessSave()` weiter. Der Produktblock sendet `id_product`, `mff_on_{position}`, `mff_q_{position}_{id_lang}` und `mff_a_{position}_{id_lang}` an `AdminMyfaqfree` mit `ajax=1` und `action=Save`.

Einen Front-Controller gibt es nicht. Das Akkordeon kommt aus den Hooks.

`getContent()` ist die Konfigurationsseite. `mff_tab` nimmt `unlock`, `settings` und `updates`. Jeder andere Wert öffnet `unlock`.

### 6.4 Hooks

In `install()` registriert:

| Hook | Rolle |
|---|---|
| `displayHeader` | CSS und JS nur auf der Produktseite. |
| `displayFooterProduct` | Akkordeon, wenn die Platzierung die Fußzeile ist. |
| `displayProductFooter` | Dasselbe Akkordeon. Ein statisches Flag druckt es einmal pro Request. |
| `displayProductExtraContent` | Ein Produktregister, wenn die Platzierung das Register ist. Sonst ein leeres Array. |
| `displayAdminProductsExtra` | Die drei Slots auf der Produktbearbeitung. |
| `actionAdminControllerSetMedia` | Admin-CSS und -JS auf der Produktseite und auf der Modulkonfiguration. |
| `actionProductDelete` | Löscht die Slots dieses Produkts. |

Die Klasse definiert weder `enable()` noch `disable()`. Das Abschalten im Modul-Manager nutzt den Schalter des Kerns. Die Klasse stellt keinen eigenen Hook bereit.

`ensureHiddenTab()` und `grantHiddenTabAccess()` laufen aus dem Konstruktor, wenn das Objekt `myfaqfree` ist, aus `getContent()` und aus dem Produkthook. Der Zugriff gibt `view`, `add`, `edit` und `delete` an Profil 1 und an das aktuelle Mitarbeiterprofil.

### 6.5 Überschreibungen

Das Modul überschreibt keine Klasse und keinen Controller.

### 6.6 Datenbank

| Tabelle | Inhalt |
|---|---|
| `ps_myfaqfree_item` | `id_item`, `id_product`, `id_shop`, `position` (1–3), `active`, `date_upd`. Eindeutiger Schlüssel auf Produkt, Shop und Position. |
| `ps_myfaqfree_item_lang` | `id_item`, `id_lang`, `question` (varchar 512), `answer` (text). |

`uninstall()` löscht beide Tabellen, wenn `parent::uninstall()` true liefert. Liefert `parent::uninstall()` false, bleiben die Tabellen. Der Tab und die drei Konfigurationsschlüssel werden vor diesem Return gelöscht. Das Löschen eines Produkts löscht seine Zeilen in beiden Tabellen. Ein Slot, dessen jede Sprache eine leere Frage hat, wird beim Speichern gelöscht. Eine Sprache mit leerer Frage wird nicht eingefügt.

Die Tabellen entstehen bei der Installation. Das Öffnen der Konfigurationsseite fügt keine Spalte hinzu.

### 6.7 Schlüssel und Übersetzungen

| Schlüssel | Wenn er fehlt oder bei der Installation |
|---|---|
| `MYFAQFREE_DISPLAY` | Die Installation schreibt `footer`. Jeder Wert außer `tab` gilt als Fußzeile. |
| `MYFAQFREE_TAB_TITLE` | Die Installation schreibt `FAQ` für jede Sprache. Eine leere Sprache fällt beim Rendern auf den Quelltext FAQ zurück. |
| `MYFAQFREE_HEADING` | Die Installation schreibt eine leere Zeichenkette für jede Sprache. Eine leere Überschrift wird nicht gedruckt. |
| `mypresta_updates` | Dieses Modul legt ihn nicht an. Fehlt er, gilt er als eingeschaltet. **Disable** schreibt `0`. Die Deinstallation löscht ihn nicht. |
| `update_myfaqfree` | Unix-Zeit der letzten Prüfung. Die Deinstallation löscht ihn nicht. |
| `updatev_myfaqfree` | Versionsstring, den die Prüfung geliefert hat. Die Deinstallation löscht ihn nicht. |

Die Prüfadresse ist `https://dev.mypresta.eu/update/get.php`. Der Abstand ist 259200 Sekunden. cURL wird genutzt, wenn `curl_init` existiert, mit 3 Sekunden Timeout. Sonst `file_get_contents`, wenn `allow_url_fopen` an ist. Der Antwortkörper wird von Tags befreit und als verfügbare Version gespeichert.

Backoffice-Texte laufen über `$this->l()`. Das Update-Formular nutzt die Quelle `updatesChecker`. Eine Sprache legen Sie mit `translations/{iso}.php` an. Texte, die nicht über `$this->l()` laufen: **Saving the three questions…**, **The FAQ could not reach the shop.** und die JavaScript-Fallbacks **The FAQ could not be saved.** und **Saved.** in `views/js/admin.js`. Der Front-Hinweis **Powered by MyFAQ for PrestaShop** steht fest in `product.tpl`.

Die Feldbeschreibungen sind die `desc`-Texte in `renderSettingsForm()` und in `renderUpdateForm()`.

### 6.8 Erweitern

Überschreiben Sie `views/templates/hook/product.tpl` aus dem Theme unter `themes/{theme}/modules/myfaqfree/views/templates/hook/product.tpl`. Ebenso `views/css/front.css` und `views/js/front.js`. Das Template wird nicht gerendert, wenn das Produkt keinen sichtbaren Slot hat, dann hat eine Theme-Überschreibung nichts zu drucken.

## 7. Hilfe

Modulseite: [https://mypresta.eu/](https://mypresta.eu/)

Wenn Sie zu diesem Modul fragen wollen, melden Sie sich im Kundenkonto auf [mypresta.eu](https://mypresta.eu) an, öffnen Sie das Kontaktformular und wählen Sie das Thema **Support for paid modules**. Das Formular sagt, dass für dieses Thema eine Anmeldung nötig ist. Nach der Anmeldung wählen Sie dieses Modul aus der Kaufhistorie. Dieses Modul ist kostenlos. Nennen Sie **MyFAQ Free** in der Nachricht, wenn es in dieser Historie nicht steht.

---
title: "HTML Box Pro - Anleitung für den Händler"
sidebar:
  label: "HTML Box Pro - Anleitung für den Händler"
description: "Konfiguration der HTML-Boxen, Hook-Positionen und Sichtbarkeitsregeln für einen Shop, der das Modul bereits hat."
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul HTML Box Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/html-box-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/html-box-pro/)
>
> ---


Der technische Name des Moduls ist `htmlboxpro`, Version 4.0.5. In dieser Sprache zeigt die Modulliste **HTML Box Pro**.

## Wo die Bildschirme liegen

Module, dann Modul-Manager, dann das Modul **HTML Box Pro**, dann Konfigurieren. Die Seite ist die Modulkonfiguration (`configure=htmlboxpro`).

Die Leiste unter dem Titel hat zwei Schaltflächen: **Einstellungen** und **Boxen**. **Einstellungen** schreibt `hbp_lasttab` = 1. **Boxen** schreibt `hbp_lasttab` = 2. Fehlt der Schlüssel, schreibt das Öffnen der Seite 1, der erste Blick ist also **Einstellungen**.

In derselben Leiste öffnet **Support** `https://mypresta.eu/contact.html` in einem neuen Tab. **Updates** öffnet die Modulseite bei MyPresta in einem neuen Tab. Die Versionsprüfung ist das Panel unten in **Einstellungen**, nicht diese Schaltfläche.

Es gibt keinen Import und keinen Block auf der Produktbearbeitung. Eine Box erscheint im Shop erst, wenn ihr Hook an ist, der Block **Aktiv** ist und die Filter weiter unten passen.

Ist `firsttime_hbp` nicht 1, zeigt die Seite einen Hinweis mit `https://www.youtube.com/watch?v=uxzhSr5TrF4`. Das Schließen sendet `firsttime_hbp` = 1, der Hinweis kommt nicht wieder.

## Was die Installation schreibt

Die Installation führt die Elterninstallation aus, legt die Tabellen an, schreibt `hbp_notinyjs` = 1 und registriert `actionAdminControllerSetMedia` sowie jeden Hook aus der Liste weiter unten.

Sie schaltet diese Hooks nicht an. Ein Hook gibt Boxen nur aus, wenn der Konfigurationsschlüssel `hbp_` plus Hookname gleich 1 ist. Bis das Kontrollkästchen unter **Boxen** gespeichert ist, fehlt der Schlüssel und der Hook liefert nichts.

Jedes Öffnen der Konfiguration prüft die Spalten und ergänzt fehlende Spalten in `hbp_block`. Vorhandene Zeilen bleiben.

## Einstellungen

![Bildschirm auf Englisch. Settings ist Einstellungen. Global module settings ist Globale Moduleinstellungen. Updates notifications ist Update-Benachrichtigungen.](https://mypresta.eu/docs/images/docs/htmlboxpro-settings.webp)

Die Überschrift ist **Globale Moduleinstellungen**. Die Schaltfläche ist **Speichern**. Jeder Schalter ist **Ein** (1) oder **Aus** (0).

| Beschriftung | Schlüssel | Nach der Installation |
| --- | --- | --- |
| Internen Rich-Text-Editor des Moduls verwenden | `hbp_tiny` | Schlüssel fehlt; das Formular zeigt **Aus** |
| Entfernen von URLs aus Bildern verhindern | `hbp_forceurls` | Schlüssel fehlt; das Formular zeigt **Aus** |
| Boxen mit Ajax-Abfragen auf der Produktseite nicht laden (duplizieren) | `hbp_noajax` | Schlüssel fehlt; das Formular zeigt **Aus** |
| tinyMCE-Bibliotheken nicht laden | `hbp_notinyjs` | 1, also **Ein** |

**Speichern** sendet die vier Schalternamen. Das Modul schreibt jeden gesendeten Wert. `hbp_tiny` = 1 lädt auf dieser Seite `views/js/tinymce16.inc.js`. Derselbe Schalter zusammen mit `hbp_forceurls` = 1 lädt stattdessen `views/js/tinymce16-force-urls.inc.js`. `hbp_tiny` = 0 lädt die Shopdatei `js/admin/tinymce.inc.js` und ruft `tinySetup()` auf. `hbp_notinyjs` = 1 lässt `js/tiny_mce/tinymce.min.js` weg. Die Seite bindet weiter `js/tiny_mce/tiny_mce.js`, `views/js/script.js` und `views/css/styles.css` ein.

`hbp_noajax` = 1 lässt `generateHookContents` nichts zurückgeben, wenn die Anfrage `ajax` = 1 und `action` = refresh hat. Andere Anfragen geben die Boxen weiter aus.

Unter den Schaltern hängt die Seite das Update-Panel aus `checkforupdates` an. Die Liste **Update-Benachrichtigungen** hat `-- select --`, **Aktivieren** (1) und **Deaktivieren** (0). **Jetzt prüfen** ist die Schaltfläche `submit_settings_updates_now`. **Speichern** in diesem Panel ist `submit_settings_updates` und schreibt nur `mypresta_updates`.

Der Konstruktor fragt den entfernten Server, wenn `mypresta_updates` nicht 0 ist oder der Schlüssel fehlt (`Configuration::get` ist false) und `update_htmlboxpro` älter als 259200 Sekunden ist. Die Anfrage läuft, wenn `allow_url_fopen` an ist. Der Lizenzwert dieses Pakets ist `nlc`. Eine Warnung erscheint, wenn die gelieferte Version höher als 4.0.5 ist und die Anfrage kein Ajax ist. **Deaktivieren** (0) geht weiter in den Zeit-Zweig; die Warnbedingung ist die dieses Zweigs.

## Boxen

![Bildschirm auf Englisch. Boxes ist Boxen. Default positions ist Standardpositionen. Search hooks hat keinen Eintrag in translations/de.php, der Bildschirm zeigt diese englische Quelle.](https://mypresta.eu/docs/images/docs/htmlboxpro-boxes.webp)

**Boxen** hat zwei Spalten. Links steht **Standardpositionen**. Über den Zeilen liegt ein Suchfeld. Der Platzhalter **Search hooks** steht nicht in `translations/de.php`, der Bildschirm zeigt diese englische Quelle. **Benutzerdefinierte Positionen** ist das Panel unter dieser Liste, in derselben linken Spalte. Die rechte Spalte zeigt die Blöcke des gewählten Hooks oder den leeren Zustand. Die Hauptspalte beginnt mit der Überschrift **No box selected** und dem Satz **Bitte wählen Sie Blöcke aus der Liste auf der linken Seite aus. Oder erstellen Sie einen neuen Block.** **No box selected** und **No boxes in this position yet** (leerer aufgeklappter Hook) stehen nicht in `translations/de.php`, der Bildschirm zeigt diese englische Quelle.

Jeder Standard-Hook ist eine Zeile: Kontrollkästchen, Hookname und die Schaltfläche für eine neue Box. Der Hookname führt zu `https://mypresta.eu/prestashop/hook/` plus den Namen in Kleinbuchstaben. Das Kontrollkästchen sendet `togglehook`. Angehakt schreibt es `hbp_{hook}` = 1 und ruft `registerHook` erneut auf. Abgehakt sendet es kein `status`, der Schlüssel wird 0. Das Ausschalten trägt den Hook nicht aus. Der Erfolgstext ist **Sichtbarkeit des Hooks korrekt geändert**.

Eine Blockzeile zeigt den internen Namen oder **kein interner Blockname**, wenn der Name leer ist. Die Schaltflächen sind **Diesen Block bearbeiten**, **Diesen Block duplizieren** und **Diesen Block entfernen**. Der Erfolg des Aktiv-Schalters ist **Sichtbarkeit des Blocks korrekt geändert**. Das Ziehen einer Zeile sendet `action=updateSlidesPosition` und `elements{hook}[]` und schreibt `hbp_block.position`. Der Tab lädt jQuery UI sortable. Ein leerer Hook zeigt **keine Blöcke definiert**. Im Multishop kann die Zeile **für diesen Shop** zeigen.

**Diesen Block duplizieren** kopiert den Block und setzt `[duplizieren] ` vor den Namen. Der Erfolgstext ist **Block korrekt dupliziert**. **Diesen Block entfernen** löscht die Zeile über das Objektmodell. Der Erfolgstext ist **Block korrekt entfernt**. Der Aktiv-Schalter in der Liste führt `smart_clean` auf jedem Sprachtext aus, speichert den Block und setzt `active` per SQL.

## Block anlegen und bearbeiten

![Bildschirm auf Englisch. Create new block ist Neuen Block erstellen. Contents ist Inhalte. Smarty templates manager ist Smarty-Vorlagen-Manager. Placement hat keinen Übersetzungseintrag.](https://mypresta.eu/docs/images/docs/htmlboxpro-block-form.webp)

Eine neue Box öffnet **Neuen Block erstellen**. Bearbeiten öffnet **Vorhandenen Block bearbeiten**. Die Schaltfläche ist **Speichern**. Anlegen sendet `submitAddNewHbox`. Bearbeiten sendet `submitEditHbox`. Der Text beim Anlegen ist **Block korrekt hinzugefügt**. Der Text beim Speichern ist **Block korrekt gespeichert**.

Der Text jeder Shopsprache liegt in `hbp_block_lang.body`. Vor dem Speichern läuft `addslashes(smart_clean(...))`. `smart_clean` zieht ein wiederholtes Leerraumzeichen auf ein Zeichen zusammen und schneidet die Enden ab. Die letzte Ersetzung in `prepare()` schreibt `\'`, `\\` und `\"` um. Die früheren Zeilen in `prepare()` nehmen die ursprüngliche Zeichenkette und ändern den Rückgabewert nicht. Die Funktion entfernt keine HTML-Tags. Dieselbe Reinigung läuft erneut, wenn der Schalter in der Liste **Aktiv** ändert.

Die Feldbeschriftungen stehen in `translations/de.php`. Der Produkttitel ist **Produkte**. **Placement**, **Pages**, **Cart**, **Customers** und **Schedule** haben dort keinen Eintrag, der Bildschirm zeigt diese englische Quelle.

| Abschnitt | Was die Felder tun |
| --- | --- |
| Inhalt | **Inhalte** (`hbp_body`, je Sprache ein Wert) und **Name** (`hbp_name`, 150 Zeichen). Der Editor-Schalter in `views/js/script.js` ruft `tinyMCE.execCommand('mceToggleEditor')` für das Feld dieser Sprache auf. Unter dem Editor steht **Smarty-Vorlagen-Manager**. Der Knopf öffnet den Vorlagenmanager aus `lib/smartyTemplatesManager/`. |
| Placement | Shop, Position (`hbp_hook`), **Active** (`hbp_active`, in der Tabelle 0, bis das Speichern 1 schreibt), nur SSL-Seiten (`hbp_bssl`), **Active on mobile devices**, **Active on tablet devices**, **Active on PC devices**. Ein fehlender Gerätewert wird als 1 gespeichert. Die deutschen Beschriftungen stehen in `translations/de.php`. |
| Pages | Startseite, Sonderangebote, Bestellbestätigung, Kategorie, Kategorie plus Unterkategorien, ausgeschlossene Kategorien, CMS-Kategorie, CMS-Seite, Herstellseite, genaue URL und Suchwörter. IDs sind kommagetrennt. Das Suchfeld neben einer ID ist das Suchwerkzeug des Moduls (`ajax=1` und `searchType`). |
| Products | Produkt-IDs ein- oder ausschließen, alle Produktseiten, Sonderpreis, nicht vorrätig, kaufbar, nicht kaufbar, auf Lager, Mindest- und Höchstwert, Produktkategorie, Hersteller, Lieferant und Merkmalwert. |
| Cart | Die Box nur, wenn der Warenkorb die genannten Kategorie- oder Produkt-IDs enthält oder nicht enthält. |
| Customers | **All users** (0), **Logged only** (1), **Unlogged only** (2) in `hbp_logged`. Die deutschen Texte dieser drei Optionen stehen in `translations/de.php`. **Show for all groups** und die Gruppenfelder gehen als kommagetrennte Liste nach `hbp_cgroup`. **Hide for (users' groups)** ist `hbp_hcgroup`. Geolokalisierung und Lieferland liegen in diesem Abschnitt. |
| Schedule | Währung, Datum von / bis, Wochentage und Uhrzeit von / bis. |

Die Wochentage rufen die Übersetzung mit der Domain `forms` auf (`Sunday` bis `Saturday`). Die Dateien `translations/*.php` speichern diese Wörter unter der Domain `htmlboxpro`, nicht `forms`. Der Bildschirm zeigt die englische Quelle: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday.

Der Geotext verweist auf `https://mypresta.eu/prestashop-17/geolite2-city-geolocation-download.html` und das Verzeichnis `/app/Resources/geoip/`. Derselbe Text sagt, dass die Geolokalisierung auf localhost nicht arbeitet. Gewählte Länder liegen in `selected_geoip`, getrennt durch Semikolon. Lieferländer liegen in `delivery_address_selected`, getrennt durch Semikolon. Das ist ein anderer Schalter als die Geolokalisierung.

## Wann der Shop einen Block verbirgt

`generateHookContents` lädt Blöcke mit `active` = 1 für die aktuelle Sprache und den aktuellen Hook, sortiert nach `position`. Ist Multishop an, muss `shop` die aktuelle Shop-ID oder 0 sein. Die Vorlage `html.tpl` verbirgt den Text, wenn eine Regel unten nicht passt. Ein Schalter auf **Aus** wendet diese Regel nicht an.

| Schalter an | Der Text wird verborgen, wenn |
| --- | --- |
| Nur Startseite | der Controller nicht `index` ist |
| Datumsbereich | heute vor dem Von-Datum oder nach dem Bis-Datum liegt (`Y-m-d`) |
| Suchwörter | die Suche keines der kommagetrennten Wörter ist |
| Nur SSL-Seiten | `$_SERVER['HTTPS']` nicht `on` ist |
| Nur angemeldet | der Kunde nicht angemeldet ist |
| Nur nicht angemeldet | der Kunde angemeldet ist |
| Nur gewählte Produktseiten | die Produkt-ID nicht in der Liste steht. Ein leeres erstes Listenelement lässt den Block, wenn eine Produkt-ID da ist |
| Nicht vorrätig | der vom Template genutzte Bestand größer als 0 ist |
| Auf Lager | dieser Bestand nicht größer als 0 ist |
| Nicht kaufbar / kaufbar | der `oos`-Wert nicht zur Deny- oder Allow-Regel in `html.tpl` passt |
| Sonderpreis / kein Sonderpreis | `hook_params.product` keinen passenden Sonderpreis hat |
| Gewählte Kategorien | der Controller nicht der Kategorie-Controller ist oder die ID nicht gewählt ist |
| Kategorien plus Unterkategorien | die Kategorie nicht gewählt ist und nach `htmlboxpro::checkIfChildren` kein Kind ist |
| CMS-Kategorie, CMS-Seite, Herstellseite | die aktuelle ID nicht in der Liste steht oder der Controller eine andere Seite ist |
| Genaue URL | `htmlboxpro::currentPageURL()` nicht in der gespeicherten Liste steht. Der Vergleich entfernt `rand=` |
| Produkt in Kategorie | die Produktkategorien die Liste nicht schneiden |
| Merkmal | kein gewählter Merkmalwert am Produkt hängt |
| Bestellbestätigung | der Controller nicht `orderconfirmation` ist |
| Hersteller oder Lieferant des Produkts | Hersteller oder Lieferant nicht gewählt ist |
| Warenkorb, Kategorie oder Produkt, enthalten oder nicht | der Warenkorb nicht zur Liste passt. Das PHP in `get_blocks` entfernt den Block vor dem Template für diese vier Filter |
| Für Gruppe verbergen | die Kundengruppe zu `hbp_hcgroup` passt. Gruppen 1 und 2 werden mit der Standardgruppe verglichen. Eine andere Gruppe verbirgt den Block, wenn sie unter den Gruppen des Kunden ist |
| Gerät | `Context::getDevice()` 1 ist und PC aus ist; 2 und Tablet aus ist; 4 und Mobil aus ist |
| Mindest- / Höchstwert | der umgerechnete Preis außerhalb des Betrags liegt oder der Hook kein Produkt hat |
| Wochentage | `hbp_daytype_on` 1 ist und das heutige `%w` nicht in der Liste steht |
| Währung | `hbp_currency_on` 1 ist und die Währungs-ID nicht `hbp_currency` ist |
| Lieferadresse | das Lieferland nicht in `delivery_address_selected` steht |
| Geolokalisierung | `hbp_geoip` 1 ist und das ermittelte Land nicht in `selected_geoip` steht |
| Ausgeschlossene Produkte, alle Produktseiten, ausgeschlossene Kategorien | das aktuelle Produkt oder die Kategorie ausgeschlossen ist |

Der Zeitfilter läuft in PHP, vor dem Template. Ist `hbp_tim` 1, werden `timfrom` und `timto` mit `date("H:i:s")` verglichen, nachdem die Doppelpunkte weg sind. `timto` geht durch `ltrim` mit der Zeichenmaske `0`, führende Nullen dieser Grenze fallen weg. Ein Block außerhalb des Fensters fällt aus der Liste.

## Platzhalter im Boxtext

Die Ersetzung läuft, wenn die Anfrage einen `controller` hat und das nicht `AdminModules` ist. Ein nicht gefüllter Platzhalter wird am Ende eine leere Zeichenkette. Ausnahme ist `{current_url}`.

| Platzhalter | Gefüllt, wenn |
| --- | --- |
| `{currency_iso}` | eine Währung geladen ist; der Wert ist der ISO-Code |
| `{id_lang}` | immer in diesem Zweig; der Wert ist der ISO-Code der Sprache, nicht die numerische ID |
| `{id_customer}`, `{email_customer}`, `{customer_firstname}`, `{customer_lastname}` | der Kunde angemeldet ist |
| `{id_product}`, `{id_product_attribute}`, `{product_name}`, `{product_ean13}`, `{product_isbn}`, `{manufacturer_name}` | der Controller `product` ist oder der Hook `product` erhält |
| `{product_price_tax_incl}`, `{product_price_tax_excl}` | Produktseite; Betrag über den Preishelfer des Moduls |
| `{product_price_tax_incl_no_currency}`, `{product_price_tax_excl_no_currency}` | dieselben Beträge ohne Währungszeichen |
| `{id_category}`, `{name_category}`, `{path_array_category}` | eine Kategorie-ID in der Anfrage steht |
| `{cart_products_id}`, `{cart_total}`, `{cart_total_with_currency}` | ein Warenkorb da ist |
| `{order_id}`, `{order_customer_email}`, `{order_currency_iso_code}`, `{order_total_paid}`, `{order_total_paid_tax_excl}`, `{order_total_paid_tax_incl}`, `{order_total_products_tax_included}`, `{order_total_products_tax_excluded}`, `{order_products_id}`, `{order_products_id_google}`, `{order_delivery_date}`, `{order_delivery_country}` | der Bestellbestätigungszweig eine Bestell-ID hat |
| `{current_url}` | jede Anfrage, nach dem Zweig oben. Schema, Host und URI |
| `{HOOK:HookName}` | `Hook::exec` dieses Namens, außer der Name ist der Hook, der diese Box gerade ausgibt; dann ist der Platzhalter leer |
| `{HOOK:HookName:moduleName}` | `Hook::exec` begrenzt auf die ID dieses Moduls |
| `{smartyTemplate:name}` | die Vorlage aus `loadSmartyTemplateFromManager` |

`{shop_name}` wird auf den Shopnamen gesetzt, der Aufräumdurchlauf ersetzt `{shop_name}` danach durch eine leere Zeichenkette. Der Platzhalter bleibt nicht als Shopname stehen. `{id_product_attribute}` ist leer, wenn die Attribut-ID 0 ist.

## Benutzerdefinierte Positionen

![Bildschirm auf Englisch. Custom positions ist Benutzerdefinierte Positionen. Add support of new hook ist Unterstützung für neuen Hook hinzufügen. Hook name ist Hook-Name. Add new hook ist Neuen Hook hinzufügen. regenerate now! ist jetzt neu generieren!](https://mypresta.eu/docs/images/docs/htmlboxpro-custom-hooks.webp)

**Benutzerdefinierte Positionen** listet Zeilen aus `hbp_customhook`. Die Überschrift über dem Feld ist **Unterstützung für neuen Hook hinzufügen**. **Neuen Hook hinzufügen** liest **Hook-Name**. Der gespeicherte Name behält nur Buchstaben und Ziffern (`preg_replace("/[^\da-z]/i", '')`). Hat der Shop keinen Hook dieses Namens, legt das Modul eine `Hook`-Zeile an mit `live_edit` 1, `position` 1, dem Titel gleich dem Namen und der Beschreibung `Custom hook created with usage of HTML BOX PRO module`. Es fügt `hbp_customhook` ein, wenn die Zeile fehlt, schreibt `htmlboxpro.php` um und registriert den Hook.

Existiert der Hook und die Methode `hook{Name}` steht schon in `htmlboxpro.php`, zeigt die Seite **Hook existiert bereits in der Shop-Datenbank** und fügt keine weitere Zeile ein. Existiert der Hook und die Methode fehlt, schreibt das Modul die Datei trotzdem um und registriert den Hook.

**jetzt neu generieren!** sendet `hbp_rh_submit`. Der Hinweis an der Schaltfläche ist **verwenden Sie diese Option, um die Moduldatei neu zu erstellen, wenn benutzerdefinierte Hooks nicht funktionieren**. Die Überschrift daneben ist **Hooks neu generieren**. Das Umschreiben ersetzt den Teil von `htmlboxpro.php` zwischen `//~~explode~~//` durch eine Methode je Hook: `hook{Name}` gibt `generateHookContents("{Name}", $params)` zurück. Die Datei muss beschreibbar sein. Fehlertext: **Die Hauptmoduldatei ist nicht beschreibbar. Bitte überprüfen Sie die Berechtigungen (CHMOD) für die Datei /modules/htmlboxpro/htmlboxpro.php**. Erfolgtext: **Hauptmoduldatei korrekt neu erstellt. Das Modul sollte jetzt benutzerdefinierte Hooks unterstützen.**

**Remove hook** fragt **Remove this custom hook?** Diese beiden Zeichenketten stehen nicht in `translations/de.php`, der Bildschirm zeigt diese englische Quelle. Die Aktion löscht die Zeile `hbp_customhook` und, wenn die Hook-ID im Shop existiert, diesen `Hook`, danach schreibt sie die Datei um.

Der Link **Wie verwendet man benutzerdefinierte Hooks?** öffnet `https://mypresta.eu/en/art/news/html-content-box-custom-hooks.html`. Im Formular zeigt ein Block an einem eigenen Hook **Dieser Block verwendet einen benutzerdefinierten Hook** und zwei Schnipsel:

`{hook::exec('HookName') nofilter}`

`{hook h='HookName' product=$product}`

Das zweite Schnipsel ist das für eine Produktliste.

## Bei der Installation registrierte Hooks

`actionAdminControllerSetMedia` fügt das jQuery-Autocomplete nur hinzu, wenn `configure` `htmlboxpro` ist. Es gibt keine Box aus.

Diese Hooks rufen `generateHookContents` mit dem Hooknamen auf. Die Ausgabe hängt weiter an `hbp_{hook}` = 1 und an einem aktiven Block:

`displayHeader`, `displayBanner`, `displayNav1`, `displayNav2`, `displayNavFullWidth`, `displayTop`, `displayHome`, `displayFooterBefore`, `displayFooter`, `displayFooterAfter`, `displayMyAccountBlock`, `displayBeforeBodyClosingTag`, `displayLeftColumn`, `displayLeftColumnProduct`, `displayRightColumn`, `displayRightColumnProduct`, `displayOrderConfirmation`, `displayCustomerAccount`, `displayCustomerAccountForm`, `displayProductAdditionalInfo`, `displayReassurance`, `displayFooterProduct`, `displayAfterProductThumbs`, `displayProductListReviews`, `actionProductOutOfStock`, `displayShoppingCart`, `displayCartExtraProductActions`, `displayShoppingCartFooter`, `displayExpressCheckout`, `displayCustomerLoginFormAfter`, `displayBeforeCarrier`, `displayAfterCarrier`, `displayPaymentTop`, `displayPaymentByBinaries`.

`displayHeader` hängt im Shop keine CSS- oder JS-Datei an. Es gibt die Boxen dieses Hooks aus. Der Shop bekommt kein eigenes Modul-Stylesheet. HTML, CSS und JavaScript sind der vom Händler gespeicherte Text.

`registerHook` nutzt die Elternmethode, wenn `hook{Name}` schon existiert. Sonst fügt es bei Bedarf die `Hook`-Zeile ein und fügt `hook_module` ein.

## Tabellen und Dateien

Die Installation legt drei Tabellen an, wenn sie fehlen, Engine InnoDB, Zeichensatz `utf8_general_ci`. Vor dem Namen steht das Shop-Präfix.

| Tabelle | Spalten der CREATE-Anweisung |
| --- | --- |
| `hbp_block` | `id` (auto increment, Primärschlüssel), `position` Standard 1, `hook` varchar(50), `active` Standard 0, `logged` Standard 0, `name` varchar(150), Index `indek1` |
| `hbp_customhook` | `id`, `hook` varchar(70) |
| `hbp_block_lang` | `id`, `id_lang`, `body` text. Die CREATE-Anweisung hat keinen Primärschlüssel |

Das Modell `models/hbox.php` bildet `hbp_block` ab, `body` ist mehrsprachig. Das nächste Öffnen der Konfiguration ergänzt die Filterspalten: `bssl`, `shop` (Standard 1), die Seiten- und Produktflags, die Textspalten der gewählten IDs, `datefrom`, `dateto`, `timfrom`, `timto`, `cgroup` (geändert auf varchar 250), `hcgroup`, `onmobile`, `ontablet`, `onpc` (Standard 1), Preisfelder, `daytype`, `currency`, `geoip` sowie die Warenkorb- und Lieferspalten. `inconsistency()` verbreitert `hook` auf varchar(255).

Weitere Dateien: `views/templates/hook/html.tpl` ist der Shoptext, `views/templates/admin/_configure/helpers/form/form.tpl` ersetzt das Helferformular dieses Moduls, `lib/searchTool/` ist die ID-Suche, `lib/smartyTemplatesManager/` bedient `{smartyTemplate:name}`, `lib/prestashop9compatibility.php` ist der Preishelfer. `key.php` ist optional und nicht in diesem Paket. Die Update-Lizenz in `checkforupdates` ist das Literal `nlc`.

Konfigurationsschlüssel, die keine Spalten sind: `hbp_notinyjs`, `hbp_tiny`, `hbp_forceurls`, `hbp_noajax`, `hbp_lasttab`, `firsttime_hbp`, `hbp_{hookname}`, `mypresta_updates`, `update_htmlboxpro`, `updatev_htmlboxpro`.

## Deaktivieren, aktivieren, deinstallieren

Die Klasse hat kein `disable()` und kein `enable()`. Deaktivieren nutzt den PrestaShop-Elternteil: das Modul bleibt installiert, Tabellen und Konfiguration bleiben, die Hooks laufen nicht. Aktivieren nutzt das Eltern-Aktivieren.

Die Klasse hat kein `uninstall()`. Die Deinstallation nutzt die Elternmethode: das Modul wird abgemeldet, die von PrestaShop gespeicherten Hook-Registrierungen werden entfernt. Die Elternmethode löscht `hbp_block`, `hbp_block_lang` und `hbp_customhook` nicht. Sie löscht die Konfigurationsschlüssel oben nicht. Sie löscht keine eigenen `Hook`-Zeilen aus **Neuen Hook hinzufügen** und stellt `htmlboxpro.php` nach **jetzt neu generieren!** oder nach einem eigenen Hook nicht wieder her. Eine spätere Installation nutzt `CREATE TABLE IF NOT EXISTS`, übrig gebliebene Zeilen bleiben.

## Leere Fläche unter den Tabs

Der Code nimmt `selecttab` = 3 an und kann `hbp_lasttab` = 3 speichern. Die Leiste hat keine dritte Schaltfläche, der Formular-Renderer hat keine Seite für 3. Bei diesem Wert ist die Fläche unter der Leiste leer. **Einstellungen** oder **Boxen** schreiben wieder 1 oder 2.

## Support

Modulseite: [HTML Box Pro](https://mypresta.eu/modules/front-office-features/html-box-pro.html).

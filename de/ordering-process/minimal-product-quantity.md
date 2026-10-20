---
title: "Mindestbestellmenge pro Produkt – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Mindestbestellmenge pro Produkt“ von MyPresta.eu."
sidebar:
  label: "Mindestbestellmenge pro Produkt – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Minimal product quantity auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/minimal-product-quantity.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/minimal-product-quantity/)
>
> ---


# Mindestbestellmenge pro Produkt

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptseite der Einstellungen für das Modul „Mindestbestellmenge pro Produkt“. Hier legen Sie die Kernregeln für Mindestmengen fest.

Die Konfigurationsseite ist intuitiv gestaltet und ermöglicht es Ihnen, Mindestmengen für einzelne Produkte und spezifische Kundengruppen festzulegen.

**So legen Sie eine Mindestmenge für ein Produkt fest:**

1. **Suchen Sie nach einem Produkt:**

   - Sie sehen eine Suchleiste oder eine Produktliste. Beginnen Sie, den Namen des Produkts einzugeben, das Sie konfigurieren möchten. Während der Eingabe schlägt das Modul passende Produkte vor.
   - *Was diese Einstellung bewirkt:* Ermöglicht Ihnen, das spezifische Produkt schnell zu finden, für das Sie eine Mindestmengenregel anwenden möchten.
   - *Auswirkung der Änderung dieser Einstellung:* N/A (Suchfunktion).
   - *Empfohlener Wert:* Geben Sie den genauen Produktnamen für Präzision ein.
   - *Händlerszenario:* Sie möchten eine Mindestmenge für „Bio-Kaffeebohnen (1kg)“ festlegen. Geben Sie „Bio-Kaffee“ ein.
2. **Wählen Sie das Produkt aus:**

   - Klicken Sie auf das gewünschte Produkt aus den Suchergebnissen. Dies fügt es einer Liste der konfigurierten Produkte darunter hinzu.
   - *Was diese Einstellung bewirkt:* Bestätigt, auf welches Produkt Sie die Regel anwenden.
   - *Auswirkung der Änderung dieser Einstellung:* Das Produkt erscheint in der Konfigurationsliste, bereit für Mengen- und Gruppeneinstellungen.
   - *Empfohlener Wert:* Wählen Sie das richtige Produkt aus.
   - *Händlerszenario:* Nachdem Sie „Bio-Kaffee“ eingegeben haben, klicken Sie auf „Bio-Kaffeebohnen (1kg)“.
3. **Mindestmenge festlegen:**

   - Neben dem ausgewählten Produkt befindet sich ein Eingabefeld (z. B. „Mindestmenge“). Geben Sie die niedrigste Anzahl von Einheiten ein, die ein Kunde für dieses spezifische Produkt kaufen muss.
   - *Was diese Einstellung bewirkt:* Definiert die absolute Mindestanzahl von Einheiten für dieses Produkt.
   - *Auswirkung der Änderung dieser Einstellung:*
     - *Wenn auf 5 gesetzt:* Kunden müssen mindestens 5 Einheiten dieses Produkts in ihren Warenkorb legen. Wenn sie versuchen, 1, 2, 3 oder 4 hinzuzufügen, erhalten sie eine Fehlermeldung.
     - *Wenn auf 1 gesetzt (oder Standard-PrestaShop-Verhalten):* Es wird keine spezielle Mindestmenge über die PrestaShop-Standardeinstellung hinaus erzwungen.
   - *Empfohlener Wert:* Eine Zahl größer als 1, die Ihren Geschäftsanforderungen entspricht (z. B. 6, 12, 24).
   - *Händlerszenario:* Sie verkaufen Kaffeebohnen in großen Mengen. Sie setzen die „Mindestmenge“ auf 5.
4. **Kundengruppe auswählen (Optional):**

   - Sie sehen wahrscheinlich ein Dropdown-Menü oder eine Liste von Kundengruppen (z. B. „Gast“, „Kunde“, „Großhändler“). Sie können eine oder mehrere Gruppen auswählen, für die diese Mindestmenge gilt.
   - *Was diese Einstellung bewirkt:* Ermöglicht es Ihnen, unterschiedliche Mindestmengenregeln basierend auf der Kundengruppe anzuwenden. Wenn keine Gruppe ausgewählt ist, gilt die Regel für alle Kunden.
   - *Auswirkung der Änderung dieser Einstellung:*
     - *Wenn „Großhändler“ ausgewählt ist:* Nur Kunden, die der Gruppe „Großhändler“ angehören, unterliegen dieser Mindestmenge. Andere Gruppen haben möglicherweise eine andere Mindestmenge (oder keine Mindestmenge).
     - *Wenn keine spezifische Gruppe ausgewählt ist (oder „Alle Kunden“ impliziert ist):* Die Mindestmenge gilt für jeden Kunden, unabhängig von seiner Gruppe.
   - *Empfohlener Wert:* Wählen Sie spezifische Gruppen aus, wenn Sie unterschiedliche Preis- oder Verkaufsstrategien für diese haben. Andernfalls lassen Sie es für „Alle Kunden“.
   - *Händlerszenario:* Sie möchten, dass Großhändler mindestens 10 Einheiten kaufen, aber normale Kunden müssen nur 5 kaufen. Sie würden zwei separate Regeln für dasselbe Produkt erstellen, eine für die Gruppe „Großhändler“ mit Menge 10 und eine andere für die Gruppe „Kunde“ mit Menge 5.
5. **Änderungen speichern:**

   - Nachdem Sie das/die Produkt(e) und deren Mindestmengen/Gruppen konfiguriert haben, denken Sie daran, auf die Schaltfläche „Speichern“ oder „Aktualisieren“ zu klicken, um Ihre Einstellungen zu übernehmen.
   - *Was diese Einstellung bewirkt:* Speichert Ihre Konfigurationsänderungen in der Datenbank.
   - *Auswirkung der Änderung dieser Einstellung:* Die neuen Mindestmengenregeln werden sofort im Front Office aktiv.
   - *Empfohlener Wert:* Immer nach Änderungen speichern.
   - *Händlerszenario:* Sie haben alle Ihre Mindestmengen eingerichtet; jetzt klicken Sie auf „Speichern“, um sie live zu schalten.

**Allgemeine Moduleinstellungen (falls vorhanden):**

Während die primäre Funktion produktbezogene Mindestmengen sind, können einige Module allgemeine Einstellungen enthalten:

- **Modul aktivieren/deaktivieren:**

  - *Was diese Einstellung bewirkt:* Schaltet die gesamte Funktionalität des Moduls ein oder aus.
  - *Auswirkung der Änderung dieser Einstellung:*
    - *Wenn aktiviert:* Mindestmengenregeln werden durchgesetzt.
    - *Wenn deaktiviert:* Alle Mindestmengenregeln werden ignoriert, und Kunden können beliebige Mengen hinzufügen.
  - *Empfohlener Wert:* JA (aktiviert) nach der Konfiguration.
  - *Händlerszenario:* Sie testen das Modul und möchten es vorübergehend deaktivieren, ohne Ihre Einstellungen zu verlieren.
- **Fehlermeldungstyp anzeigen (z. B. Pop-up, Inline):**

  - *Was diese Einstellung bewirkt:* Steuert, wie der Kunde benachrichtigt wird, wenn er versucht, weniger als die Mindestmenge hinzuzufügen.
  - *Auswirkung der Änderung dieser Einstellung:*
    - *Wenn auf Pop-up gesetzt:* Ein modales Fenster erscheint, das den Benutzerfluss unterbricht und das Problem klar darstellt.
    - *Wenn auf Inline gesetzt:* Eine Nachricht erscheint direkt auf der Produktseite oder im Warenkorb, ohne Pop-up.
  - *Empfohlener Wert:* Pop-up ist oft effektiver für kritische Fehler wie Mindestmengen, da es Aufmerksamkeit erfordert.
  - *Händlerszenario:* Sie möchten sicherstellen, dass Kunden die Mindestmengenanforderung nicht übersehen, daher wählen Sie ein Pop-up.

### 2.2 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfigurationsseite | Produktsuche | N/A | Produkte finden, um Mindestmengenregeln anzuwenden. |
| Modul-Konfigurationsseite | Mindestmenge (pro Produkt) | Variiert (z. B. 5, 10) | Legt die niedrigste Anzahl von Einheiten fest, die ein Kunde für dieses Produkt kaufen muss. |
| Modul-Konfigurationsseite | Kundengruppe (pro Produkt) | Alle Kunden | Wendet die Mindestmengenregel auf spezifische Kundengruppen oder alle Kunden an. |
| Modul-Konfigurationsseite | Speichern-Button | N/A | Wendet alle konfigurierten Mindestmengenregeln auf den Shop an. |
| Modul-Konfigurationsseite | Modul aktivieren/deaktivieren | Aktiviert | Schaltet die Funktionalität des Moduls global ein oder aus. |
| Modul-Konfigurationsseite | Fehlermeldungstyp | Pop-up | Definiert, wie Mindestmengenfehler den Kunden angezeigt werden. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe eine Mindestmenge festgelegt, aber sie funktioniert in meinem Shop nicht. Was ist falsch?**
A:

1. **Ist das Modul aktiviert?** Überprüfen Sie die Hauptkonfigurationsseite, um sicherzustellen, dass das Modul „Mindestbestellmenge pro Produkt“ aktiv ist.
2. **Haben Sie Ihre Änderungen gespeichert?** Klicken Sie immer auf die Schaltfläche „Speichern“ oder „Aktualisieren“, nachdem Sie Konfigurationsänderungen vorgenommen haben.
3. **Leeren Sie Ihren PrestaShop-Cache:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal speichert PrestaShop alte Einstellungen im Cache.
4. **Auf Theme-Konflikte prüfen:** Wenn Sie ein stark angepasstes Theme haben, kann es die Art und Weise beeinträchtigen, wie das Modul Nachrichten anzeigt oder mit dem „In den Warenkorb“-Button interagiert. Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme (Classic oder Hummingbird), um zu sehen, ob das Problem weiterhin besteht. Wenn es sich löst, muss Ihr Theme angepasst werden.
5. **Kundengruppe:** Stellen Sie sicher, dass der Kunde, mit dem Sie testen, der Gruppe angehört, für die die Mindestmenge festgelegt ist. Wenn keine Gruppe angegeben ist, sollte es für alle gelten.

**F2: Die Pop-up-Benachrichtigung sieht seltsam aus oder passt nicht zum Design meines Shops.**
A: Das Modul verwendet sein eigenes CSS für das Pop-up. Wenn Ihr Theme sehr spezifische Styling-Regeln hat, können diese überschrieben werden oder in Konflikt geraten.

1. **Moduleinstellungen prüfen:** Sehen Sie nach, ob das Modul Optionen zur Anpassung des Pop-up-Erscheinungsbilds oder zur Auswahl einer anderen Anzeigemethode (z. B. Inline-Nachricht statt Pop-up) bietet.
2. **Benutzerdefiniertes CSS:** Für Entwickler oder Webmaster kann benutzerdefiniertes CSS in die `custom.css`-Datei Ihres Themes eingefügt werden, um die Standardstile des Moduls zu überschreiben und an das Branding Ihres Shops anzupassen. (Siehe Abschnitt 7.5 für Details zur CSS-Datei).

**F3: Kann ich eine Mindestmenge für Produktkombinationen (Attribute) festlegen?**
A: Das Modul wendet Mindestmengen typischerweise auf Produktebene an. Wenn Sie spezifische Mindestmengen für Kombinationen benötigen (z. B. „Rotes T-Shirt, Größe S“ vs. „Blaues T-Shirt, Größe L“), müssen Sie prüfen, ob das Modul dies in seiner Konfiguration explizit unterstützt. Falls nicht, würden Sie die Mindestmenge für das übergeordnete Produkt festlegen, die dann für jede Kombination dieses Produkts gilt.

**F4: Wie übersetze ich die Nachrichten des Moduls in andere Sprachen?**
A:

1. Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
2. Wählen Sie „Übersetzungen installierter Module“.
3. Wählen Sie Ihr Theme, die Sprache, in die Sie übersetzen möchten, und dann „Mindestbestellmenge pro Produkt“ aus der Modulliste.
4. Sie finden alle übersetzbaren Zeichenketten, die vom Modul verwendet werden (z. B. „Sie müssen mindestens X Einheiten dieses Produkts hinzufügen“). Übersetzen Sie diese und speichern Sie.

**F5: Was passiert, wenn ein Kunde ein Produkt in seinem Warenkorb hat, für das später eine Mindestmenge festgelegt wird?**
A: Wenn der Kunde das nächste Mal seinen Warenkorb besucht oder versucht, zur Kasse zu gehen, erkennt das Modul die Diskrepanz. Er wird mit der Fehlermeldung aufgefordert und daran gehindert, fortzufahren, bis er die Menge anpasst, um die neue Mindestmenge zu erfüllen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Mindestbestellmenge pro Produkt“ (`minqc`) folgt einer Standard-PrestaShop-Modularchitektur und nutzt hauptsächlich Hooks, um seine Logik und Front-End-Assets zu injizieren. Es funktioniert, indem es Mengenänderungen und Warenkorb-Hinzufügungen abfängt, diese gegen konfigurierte Mindestmengen validiert und dem Benutzer Feedback anzeigt. Die Kernlogik des Moduls befindet sich in seiner Hauptdatei `index.php`, die Installation, Deinstallation, Konfiguration und Hook-Registrierung verwaltet. Die Front-End-Interaktion wird über eine Reihe von JavaScript-Dateien verwaltet, die auf verschiedene PrestaShop-Versionen und Kontexte (Produktseite, Warenkorb, Schnellansicht) zugeschnitten sind.

### 4.2 Controller (`controllers/`)

Dieses Modul scheint keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller zu verwenden. Seine Konfiguration wird direkt in der Methode `getContent()` der Hauptmodulklasse behandelt, und Front-Office-Interaktionen werden über JavaScript und AJAX-Aufrufe an Kern-PrestaShop-Funktionen oder die eigene `ajax.php` des Moduls (falls vorhanden, obwohl nicht explizit als dedizierter Controller aufgeführt, ist es ein gängiges Muster für Module, AJAX-Anfragen über ihre Hauptdatei oder ein einfaches Skript zu behandeln) verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Basierend auf dem bereitgestellten Inventar definiert dieses Modul keine benutzerdefinierten `ObjectModel`-Klassen oder andere komplexe PHP-Klassen in einem dedizierten `classes/`-Verzeichnis. Seine Logik ist wahrscheinlich in der Hauptdatei `minqc/index.php` gekapselt und interagiert direkt mit `Configuration` für Einstellungen und potenziell `Db` für die Speicherung benutzerdefinierter Daten, falls produktspezifische Mindestmengen außerhalb von `ps_configuration` gespeichert werden.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul verwendet JavaScript ausgiebig, um eine dynamische Benutzererfahrung zu bieten und Mengenregeln in Echtzeit durchzusetzen.

- `minqc/views/js/minqc.js`:

  - **Umfang:** Wahrscheinlich eine Kern-JS-Datei, die potenziell global oder auf mehreren Seiten geladen wird.
  - **Verantwortlichkeit:** Enthält allgemeine Hilfsfunktionen, Ereignisbindung für gemeinsame Elemente und möglicherweise die Hauptlogik zur Überprüfung von Mindestmengen vor dem Hinzufügen zum Warenkorb oder der Aktualisierung des Warenkorbs. Es könnte die Anzeige der Pop-up-Benachrichtigung verwalten.
  - **Interaktionen:** Bindet an `click`-Ereignisse auf „In den Warenkorb“-Buttons, `change`-Ereignisse auf Mengeneingabefeldern und potenziell `prestashop.on`-Ereignisse für AJAX-Warenkorb-Updates.
- `minqc/views/js/minqc-17500.js`:

  - **Umfang:** Front-Office, speziell für PrestaShop 1.7.5.0 und neuere Versionen (oder ähnliche Versionsbereiche).
  - **Verantwortlichkeit:** Enthält versionsspezifische JavaScript-Logik zur Anpassung an Änderungen in der PrestaShop-Front-Office-Struktur, dem AJAX-Warenkorb-Verhalten oder den auf diesen Versionen eingeführten Produktseitenelementen.
  - **Interaktionen:** Überschreibt oder erweitert `minqc.js` für spezifische PrestaShop 1.7+ DOM-Strukturen und Ereignisbehandlung.
- `minqc/views/js/minqc-admin-product.js`:

  - **Umfang:** Back-Office, speziell auf der Produktbearbeitungsseite (`AdminProducts`).
  - **Verantwortlichkeit:** Wenn das Modul das Festlegen von Mindestmengen direkt auf der Produktbearbeitungsseite erlaubt, würde dieses Skript die Benutzeroberfläche dafür verwalten (z. B. Hinzufügen von Eingabefeldern, Speichern von Werten über AJAX).
  - **Interaktionen:** Bindet an Ereignisse auf Produktformular-Elementen, führt AJAX-Aufrufe zum Speichern produktspezifischer Mindestmengen durch.
- `minqc/views/js/minqc-cart.js`:

  - **Umfang:** Front-Office, speziell auf der Warenkorbseite.
  - **Verantwortlichkeit:** Überwacht Mengenänderungen im Warenkorb, validiert diese gegen Mindestmengen und verhindert den Checkout, wenn Regeln verletzt werden. Zeigt Fehlermeldungen oder Pop-ups auf der Warenkorbseite an.
  - **Interaktionen:** Bindet an Änderungen der Mengeneingabe, Klicks auf den „Zur Kasse gehen“-Button und potenziell `prestashop.on`-Ereignisse im Zusammenhang mit Warenkorb-Updates.
- `minqc/views/js/minqc-front.js`:

  - **Umfang:** Allgemeine Front-Office-Nutzung.
  - **Verantwortlichkeit:** Könnte ein generischeres Front-End-Skript sein, das möglicherweise die Anzeige von Mindestmengeninformationen in Produktlisten oder auf anderen nicht-spezifischen Produkt-/Warenkorbseiten handhabt.
  - **Interaktionen:** DOM-Manipulation zur Anzeige von Nachrichten, potenziell AJAX-Aufrufe zur Validierung.
- `minqc/views/js/minqc-no-autoadd.js`:

  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Schlägt ein spezifisches Verhalten vor, das sich auf die Verhinderung des automatischen Hinzufügens von Produkten zum Warenkorb bezieht, wenn Mindestmengen nicht erfüllt sind, oder auf die Behandlung von Szenarien, in denen ein Produkt automatisch hinzugefügt werden könnte, aber dann die Validierung fehlschlägt.
  - **Interaktionen:** Modifiziert das Standardverhalten von „In den Warenkorb“, um sicherzustellen, dass die Validierung *vor* dem Hinzufügen des Artikels erfolgt.
- `minqc/views/js/minqc-product-classic.js`:

  - **Umfang:** Front-Office, speziell für Themes, die auf dem PrestaShop Classic Theme basieren (PrestaShop 1.7+).
  - **Verantwortlichkeit:** Passt die Durchsetzung und Anzeige der Mindestmenge an die DOM-Struktur und die JavaScript-Ereignisse an, die spezifisch für die Produktseite des Classic Themes sind.
  - **Interaktionen:** Bindet an den „In den Warenkorb“-Button und Mengeneingabeelemente auf der Produktseite des Classic Themes.
- `minqc/views/js/minqc-product-hummingbird.js`:

  - **Umfang:** Front-Office, speziell für Themes, die auf dem PrestaShop Hummingbird Theme basieren (PrestaShop 8+).
  - **Verantwortlichkeit:** Passt die Durchsetzung und Anzeige der Mindestmenge an die DOM-Struktur und die JavaScript-Ereignisse an, die spezifisch für die Produktseite des Hummingbird Themes sind.
  - **Interaktionen:** Bindet an den „In den Warenkorb“-Button und Mengeneingabeelemente auf der Produktseite des Hummingbird Themes.

### 4.5 CSS-Stylesheets (`views/css/`)

- `minqc/views/css/minqc.css`:
  - **Umfang:** Front-Office und potenziell Back-Office für modulspezifische UI-Elemente.
  - **Haupt-UI-Komponenten:** Stile für die Pop-up-Benachrichtigung (modaler Hintergrund, Inhaltsfeld, Schließen-Button, Nachrichtentext), Inline-Fehlermeldungen und potenziell visuelle Indikatoren auf Produktseiten.
  - **Wichtige CSS-Klassenselektoren:** Entwickler können den HTML-Output des Moduls überprüfen, um spezifische Klassen (z. B. `.minqc-popup`, `.minqc-error-message`, `.minqc-quantity-input-error`) zu identifizieren und diese in der `custom.css` oder `theme.css` ihres Themes zu überschreiben, um sie an das Branding ihres Shops anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**: Nicht explizit aufgeführt, aber üblich für Module, `displayHeader` für JS/CSS oder `displayProductActions` für Produktseitenmeldungen zu verwenden.
- **Admin-Templates (`views/templates/admin/`)**:

  - `minqc/views/templates/admin/admin.tpl`: Wahrscheinlich das Hauptkonfigurationstemplate für das Modul, gerendert durch die `getContent()`-Methode. Es würde die Produktsuche, die Liste der konfigurierten Produkte und allgemeine Einstellungen enthalten.
  - `minqc/views/templates/admin/admintab.tpl`: Könnte ein Untertemplate für einen spezifischen Tab oder Abschnitt innerhalb der Admin-Konfiguration oder ein älteres Template sein.
  - `minqc/views/templates/admin/_configure/helpers/list/list_content.tpl`: Dies deutet darauf hin, dass das Modul PrestaShops `HelperList` verwendet, um die Liste der Produkte mit konfigurierten Mindestmengen im Back Office anzuzeigen. Dieses Template würde definieren, wie jede Zeile in dieser Liste gerendert wird.
- **Ajax-Templates (`views/templates/ajax/`)**:

  - `minqc/views/templates/ajax/minqcErrors.tpl`: Dieses Template wird wahrscheinlich verwendet, um den HTML-Inhalt des Fehler-Pop-ups oder der Inline-Nachrichten zu rendern, die dem Kunden angezeigt werden, wenn eine Mindestmenge nicht erfüllt ist. Es würde über AJAX geladen.
- **Front-Office-Templates (`views/templates/front/`)**:

  - `minqc/views/templates/front/beforeShoppingCart.tpl`: Dieses Template wird wahrscheinlich an einer Position vor dem Hauptinhalt des Warenkorbs eingehängt, um möglicherweise eine Warnung oder Zusammenfassung bezüglich der Mindestmengen anzuzeigen, wenn der Warenkorb ungültig ist.
  - `minqc/views/templates/front/product-details.tpl`: Dieses Template würde verwendet, um Mindestmengeninformationen oder Warnungen direkt in die Produktdetailseite einzufügen, oft in der Nähe des Mengenselektors oder des „In den Warenkorb“-Buttons.
  - `minqc/views/templates/front/productActions.tpl`: Ähnlich wie `product-details.tpl` würde dieses Template in den `displayProductActions`-Hook (oder ähnliches) eingehängt, um Nachrichten anzuzeigen oder das Verhalten des „In den Warenkorb“-Buttons basierend auf Mindestmengenregeln zu ändern.
  - `minqc/views/templates/front/qv.tpl`: Dieses Template ist speziell für die „Schnellansicht“-Funktionalität und fügt Mindestmengeninformationen oder Warnungen in das Schnellansicht-Modal ein.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul speichert seine Konfiguration für produktspezifische Mindestmengen und Kundengruppen-Zuordnungen wahrscheinlich in der Tabelle `ps_configuration` für einfache globale Einstellungen.
  - Für produkt- und gruppenspezifische Mindestmengen ist es sehr wahrscheinlich, dass das Modul eine eigene benutzerdefinierte Datenbanktabelle (z. B. `ps_minqc_product_quantity`) erstellt, um `id_product`, `id_customer_group` und `min_quantity`-Werte zu speichern. Diese Tabelle würde während der `install()`-Methode erstellt und während der `uninstall()`-Methode gelöscht.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Fügt die CSS- (`minqc.css`) und JavaScript-Dateien (`minqc.js`, `minqc-front.js`, versionsspezifisches JS wie `minqc-17500.js`, `minqc-product-classic.js`, `minqc-product-hummingbird.js`, `minqc-cart.js`, `minqc-no-autoadd.js`) des Moduls für die Front-End-Funktionalität ein. |
| `displayProductActions` | Auf der Produktseite, typischerweise in der Nähe des „In den Warenkorb“-Buttons. | Fügt `productActions.tpl` ein, um Mindestmengenanforderungen oder Warnungen direkt auf der Produktseite anzuzeigen. |
| `displayProductExtraContent` (oder ähnlich) | Auf der Produktseite, für zusätzliche Inhaltsblöcke. | Könnte verwendet werden, um `product-details.tpl` oder andere Informationen anzuzeigen. |
| `displayShoppingCartFooter` (oder ähnlich) | Am unteren Rand der Warenkorbzusammenfassung. | Fügt `beforeShoppingCart.tpl` oder ähnliches ein, um Warnungen anzuzeigen, wenn Warenkorbartikel die Mindestmengen nicht erfüllen, wodurch der Checkout verhindert wird. |
| `actionCartSave` | Nachdem ein Warenkorb gespeichert oder aktualisiert wurde. | Löst die PHP-Logik des Moduls aus, um alle Mengen im Warenkorb erneut gegen konfigurierte Mindestmengen zu validieren. |
| `actionValidateOrder` | Bevor eine Bestellung offiziell validiert wird. | Letzte Überprüfung, um sicherzustellen, dass alle Produktmengen im Warenkorb ihre Mindestmengen erfüllen, bevor die Bestellung aufgegeben wird. |
| `actionProductUpdate` / `actionProductAdd` | Wenn ein Produkt im Back Office aktualisiert oder hinzugefügt wird. | Potenziell verwendet, um zwischengespeicherte Mindestmengen-Daten für dieses Produkt zu aktualisieren oder zu löschen. |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | Fügt UI-Elemente (z. B. über `admintab.tpl` oder `admin.tpl`) ein, um das Festlegen produktspezifischer Mindestmengen direkt aus dem Produktformular zu ermöglichen, unter Verwendung von `minqc-admin-product.js`. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul „Mindestbestellmenge pro Produkt“ zur Verfügung.

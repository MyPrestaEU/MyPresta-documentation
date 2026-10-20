---
title: "Produktdetailseite Kombinationstabelle - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Produktdetailseite Kombinationstabelle' von MyPresta.eu."
sidebar:
  label: "Produktdetailseite Kombinationstabelle - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product page combinations table auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-page-combinations-table/)
>
> ---


# Produktdetailseite Kombinationstabelle

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie steuern, wie die Kombinationstabelle auf Ihren Produktdetailseiten angezeigt wird und sich verhält.

#### Allgemeine Einstellungen

- **Filterfunktion aktivieren**

  - **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert ein Filtersystem oberhalb der Kombinationstabelle, das es Kunden ermöglicht, Optionen schnell nach bestimmten Attributwerten einzugrenzen (z. B. „Nur rote Hemden anzeigen“).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine Filterleiste erscheint oberhalb der Tabelle, die es Kunden erleichtert, spezifische Kombinationen in großen Listen zu finden.
    - *Wenn deaktiviert:* Es wird keine Filterleiste angezeigt, und alle Kombinationen werden ohne Filteroptionen dargestellt.
  - **Empfohlener Wert:** JA (wenn Sie viele Kombinationen pro Produkt haben oder wenn Kunden oft nach spezifischen Attributen suchen).
  - **Händlerszenario / Beispiel:** Ein Bekleidungsgeschäft mit Dutzenden von Größen und Farben für ein einzelnes T-Shirt. Filter helfen Kunden, schnell „Groß Blau“ Hemden zu finden.
- **Besten Preis hervorheben**

  - **Was diese Einstellung bewirkt:** Hebt die Kombination mit dem niedrigsten Preis in der Tabelle visuell hervor und lenkt die Aufmerksamkeit der Kunden auf die günstigste Option.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Zeile, die der günstigsten Kombination entspricht, wird hervorgehoben (z. B. mit einer anderen Hintergrundfarbe).
    - *Wenn deaktiviert:* Keine spezielle Hervorhebung für den niedrigsten Preis.
  - **Empfohlener Wert:** JA (kann Käufe fördern, indem der Wert hervorgehoben wird).
  - **Händlerszenario / Beispiel:** Ein Produkt mit verschiedenen Bundles oder Konfigurationen, bei denen eine Kombination ein deutlich besseres Angebot bietet.
- **Spalte für Ersparnisse anzeigen**

  - **Was diese Einstellung bewirkt:** Fügt der Tabelle eine zusätzliche Spalte hinzu, die den Betrag oder Prozentsatz anzeigt, den ein Kunde beim Kauf einer bestimmten Kombination spart, besonders nützlich bei Mengenrabatten oder Sonderpreisen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine Spalte „Ersparnisse“ erscheint, die den Rabatt für jede Kombination anzeigt, falls zutreffend.
    - *Wenn deaktiviert:* Diese Spalte wird nicht angezeigt.
  - **Empfohlener Wert:** JA (wenn Sie häufig Rabatte anbieten oder mengenbasierte Preise haben).
  - **Händlerszenario / Beispiel:** Verkauf eines Produkts mit einem Grundpreis, aber bestimmte Kombinationen (z. B. eine „Bundle“-Kombination) haben einen reduzierten Preis, und Sie möchten die Ersparnis anzeigen.
- **Mengenrabatt-Schwellenwert-Tipp**

  - **Was diese Einstellung bewirkt:** Zeigt einen kleinen Tooltip oder eine Nachricht an, die die erforderliche Menge angibt, um einen bestimmten Rabatt freizuschalten, und ermutigt Kunden, mehr zu kaufen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Wenn ein Kunde über ein Mengeneingabefeld fährt oder damit interagiert, kann ein Tipp erscheinen, der anzeigt: „Kaufe 5 für 10% Rabatt!“.
    - *Wenn deaktiviert:* Solche Tipps werden nicht angezeigt.
  - **Empfohlener Wert:** JA (wenn Sie die Mengenrabattfunktion von PrestaShop verwenden).
  - **Händlerszenario / Beispiel:** Ein Geschäft, das Büromaterial verkauft, bei dem der Kauf von 10 Stiften einen Rabatt von 5% erhält, und dieser Tipp erinnert den Kunden daran.
- **Mobiles Kartenlayout**

  - **Was diese Einstellung bewirkt:** Legt fest, wie die Kombinationstabelle auf mobilen Geräten angezeigt wird. Anstelle einer breiten Tabelle kann sie zu einem benutzerfreundlicheren „Karten“-Layout wechseln.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Auf Smartphones wird jede Kombination als separate, vertikal gestapelte Karte dargestellt, was das Lesen und die Interaktion erleichtert.
    - *Wenn deaktiviert:* Das Modul versucht, die vollständige Tabelle anzuzeigen, was auf Mobilgeräten horizontales Scrollen erfordern könnte und die Benutzerfreundlichkeit potenziell beeinträchtigt.
  - **Empfohlener Wert:** JA (entscheidend für die mobile Responsivität und ein gutes Benutzererlebnis).
  - **Händlerszenario / Beispiel:** Ein Kunde, der Ihren Shop auf seinem Telefon durchsucht. Das Kartenlayout stellt sicher, dass er Kombinationen einfach sehen und auswählen kann, ohne zu zoomen oder übermäßig zu scrollen.
- **Spaltenreihenfolge**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, die Reihenfolge der Spalten (z. B. Bild, Referenz, Preis, Menge) in der Kombinationstabelle anzupassen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei Änderung:* Die Spalten ordnen sich in der Front-Office-Tabelle entsprechend Ihrer angegebenen Reihenfolge neu an.
  - **Empfohlener Wert:** Ordnen Sie die Spalten in einer intuitiven Reihenfolge an, die für Ihre Produkte sinnvoll ist (z. B. Bild, Attribute, Preis, Menge, In den Warenkorb).
  - **Händlerszenario / Beispiel:** Für ein Modegeschäft möchten Sie vielleicht zuerst „Bild“, dann „Farbe“, dann „Größe“, dann „Preis“. Für Elektronik könnte „Referenz“ wichtiger sein.
- **Klicken und Kombination wechseln**

  - **Was diese Einstellung bewirkt:** Steuert, ob das Klicken auf eine Kombinationszeile in der Tabelle automatisch das Hauptproduktbild, den Preis und andere Details auf der Produktdetailseite aktualisiert, um diese spezifische Kombination widerzuspiegeln.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Klicken auf eine Zeile aktualisiert dynamisch die Hauptproduktanzeige und gibt dem Kunden eine visuelle Bestätigung seiner Auswahl.
    - *Wenn deaktiviert:* Die Hauptproduktanzeige ändert sich nicht, wenn eine Zeile angeklickt wird; nur die Mengeneingabe und der „In den Warenkorb“-Button für diese Zeile sind aktiv.
  - **Empfohlener Wert:** JA (verbessert das Benutzererlebnis durch visuelles Feedback).
  - **Händlerszenario / Beispiel:** Ein Kunde klickt auf eine Kombination „Rot, Groß“, und das Hauptproduktbild wechselt sofort zur roten Version des Produkts.

#### Bildeinstellungen

- **Bild anzeigen**

  - **Was diese Einstellung bewirkt:** Legt fest, ob ein Miniaturbild für jede Kombination in der Tabelle angezeigt werden soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine Bildspalte erscheint, die das spezifische Bild anzeigt, das jeder Kombination zugeordnet ist (falls verfügbar).
    - *Wenn deaktiviert:* Es wird keine Bildspalte angezeigt.
  - **Empfohlener Wert:** JA (Bilder sind für die Produktauswahl sehr aussagekräftig).
  - **Händlerszenario / Beispiel:** Ein Bekleidungsgeschäft, in dem jede Farbvariante ein eigenes Bild hat.
- **Bildspalte anzeigen, wenn mindestens eine Kombination ein Bild hat**

  - **Was diese Einstellung bewirkt:** Steuert die Sichtbarkeit der Bildspalte basierend darauf, ob überhaupt eine Kombination ein spezifisches Bild zugewiesen bekommen hat.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Wenn auch nur eine Kombination ein Bild hat, erscheint die Bildspalte für alle Kombinationen (wobei das Standardproduktbild für diejenigen ohne spezifische Kombinationsbilder angezeigt wird).
    - *Wenn deaktiviert:* Die Bildspalte erscheint nur, wenn *alle* Kombinationen spezifische Bilder haben, oder sie erscheint möglicherweise überhaupt nicht, wenn Sie auch „Standardproduktbild verwenden“ sorgfältig nutzen.
  - **Empfohlener Wert:** JA (verhindert eine leere Bildspalte, wenn nur wenige Kombinationen Bilder haben).
  - **Händlerszenario / Beispiel:** Sie haben 20 Kombinationen, aber nur 5 haben einzigartige Bilder. Dies stellt sicher, dass die Bildspalte trotzdem angezeigt wird und das Hauptproduktbild für die anderen 15 verwendet wird.
- **Standardproduktbild verwenden**

  - **Was diese Einstellung bewirkt:** Wenn eine spezifische Kombination kein eigenes Bild hat, bestimmt diese Einstellung, ob das Hauptproduktbild als Fallback verwendet werden soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kombinationen ohne spezifische Bilder zeigen das Hauptproduktbild an.
    - *Wenn deaktiviert:* Kombinationen ohne spezifische Bilder zeigen einen Platzhalter oder kein Bild an.
  - **Empfohlener Wert:** JA (stellt sicher, dass alle Kombinationen eine visuelle Darstellung haben).
  - **Händlerszenario / Beispiel:** Ein Produkt mit vielen Größenvarianten, aber nur einem Bild pro Farbe. Dies stellt sicher, dass alle Größen einer bestimmten Farbe das richtige Farbbild anzeigen.
- **Fancybox-Zoom aktivieren**

  - **Was diese Einstellung bewirkt:** Ermöglicht Kunden, auf Kombinationsbilder in der Tabelle zu klicken, um eine größere, gezoomte Version in einem Pop-up (Fancybox) anzuzeigen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Klicken auf ein Kombinationsbild öffnet es in einem Fancybox-Pop-up.
    - *Wenn deaktiviert:* Bilder sind nicht zum Zoomen anklickbar.
  - **Empfohlener Wert:** JA (verbessert das Bildanzeigeerlebnis).
  - **Händlerszenario / Beispiel:** Ein Kunde möchte die Textur oder Details einer bestimmten Farbvariante genauer sehen.
- **Anzuzeigender Bildtyp**

  - **Was diese Einstellung bewirkt:** Wählt die Größe/den Typ des Bildes (z. B. `small_default`, `medium_default`), das als Miniaturansicht in der Kombinationstabelle angezeigt werden soll.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei Änderung:* Die Größe der Bilder in der Tabelle wird auf den ausgewählten Bildtyp aktualisiert.
  - **Empfohlener Wert:** `small_default` oder `medium_default` (wählen Sie eine Größe, die gut in Ihr Tabellenlayout passt, ohne zu groß oder zu klein zu sein).
  - **Händlerszenario / Beispiel:** Sie möchten, dass die Bilder in der Tabelle etwas größer sind als die winzigen `small_default`, aber nicht so groß wie `large_default`.
- **Bildtyp zum Vergrößern der Miniaturansicht**

  - **Was diese Einstellung bewirkt:** Wählt die Größe/den Typ des Bildes, das verwendet werden soll, wenn die Fancybox-Zoomfunktion aktiviert ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei Änderung:* Das im Fancybox-Pop-up angezeigte Bild hat die ausgewählte Größe.
  - **Empfohlener Wert:** `large_default` oder `thickbox_default` (wählen Sie den größten, qualitativ hochwertigsten Bildtyp zum Zoomen).
  - **Händlerszenario / Beispiel:** Ein Kunde zoomt in ein Bild und erwartet eine hochauflösende Version.

#### Attribute-Anzeigeeinstellungen

- **Anzeigemethode für Attribute**

  - **Was diese Einstellung bewirkt:** Steuert, wie die Attributnamen (z. B. „Größe“, „Farbe“) in der Tabellenüberschrift angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Optionen (z. B. „Vollständiger Name“, „Kurzname“, „ID“):* Ändert, wie die Attributüberschriften erscheinen.
  - **Empfohlener Wert:** „Vollständiger Name“ (am aussagekräftigsten für Kunden).
  - **Händlerszenario / Beispiel:** Sie möchten, dass „Größe“ als „Größe“ und nicht als „S“ oder „ID: 1“ angezeigt wird.
- **Attributzuordnungen mit Shop (Multistore)**

  - **Was diese Einstellung bewirkt:** In einer Multistore-Umgebung können Sie hier festlegen, welche Attributgruppen für welche Shops relevant sind, um zu verhindern, dass irrelevante Attribute angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei Konfiguration:* Nur Attribute, die dem aktuellen Shop-Kontext zugeordnet sind, werden in der Tabelle angezeigt.
  - **Empfohlener Wert:** Sorgfältig konfigurieren, wenn Sie einen Multistore mit unterschiedlichen Produktkatalogen betreiben.
  - **Händlerszenario / Beispiel:** Shop A verkauft Kleidung (Größe, Farbe), Shop B verkauft Elektronik (Speicher, RAM). Dies verhindert, dass „Speicher“ in der Kombinationstabelle von Shop A erscheint.
- **Bezeichnung zum Attributnamen hinzufügen**

  - **Was diese Einstellung bewirkt:** Fügt den Attributgruppennamen als Präfix zum Attributwert hinzu (z. B. „Größe: S“, „Farbe: Rot“).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Attributwerte werden aussagekräftiger.
    - *Wenn deaktiviert:* Nur der Attributwert wird angezeigt (z. B. „S“, „Rot“).
  - **Empfohlener Wert:** JA (verbessert die Klarheit, insbesondere wenn Attributwerte nicht selbsterklärend sind).
  - **Händlerszenario / Beispiel:** Ein Produkt hat den Attributwert „Standard“. Ist es eine Standardgröße, Standardfarbe oder Standardausführung? „Ausführung: Standard“ klärt dies.
- **Farbattribut**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen festzulegen, welche Attributgruppe „Farbe“ in Ihrem Shop repräsentiert. Dies ist wichtig, damit das Modul Farbfelder oder farbspezifische Logik korrekt anzeigt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Bei Auswahl:* Das Modul behandelt Werte aus dieser Attributgruppe als Farben und zeigt sie möglicherweise als Farbfelder anstelle von Text an.
  - **Empfohlener Wert:** Wählen Sie Ihre primäre „Farb“-Attributgruppe aus.
  - **Händlerszenario / Beispiel:** Sie haben eine Attributgruppe namens „Farbe“ mit Werten wie „Rot“, „Blau“, „Grün“. Die Auswahl dieser Gruppe stellt sicher, dass diese als tatsächliche Farbfelder angezeigt werden.

#### Anzeigeoptionen

- **Tabellenkopf ausblenden**

  - **Was diese Einstellung bewirkt:** Entfernt die Kopfzeile aus der Kombinationstabelle (z. B. „Bild | Größe | Farbe | Preis | Menge“).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Tabelle beginnt direkt mit den Kombinationszeilen, ohne Spaltentitel.
    - *Wenn deaktiviert:* Die Kopfzeile ist sichtbar.
  - **Empfohlener Wert:** NEIN (Kopfzeilen sind in der Regel wichtig für die Klarheit, es sei denn, Ihre Tabelle ist sehr einfach und selbsterklärend).
  - **Händlerszenario / Beispiel:** Für ein sehr einfaches Produkt mit nur einem Attribut (z. B. „Packungsgröße“) könnten Sie die Kopfzeile ausblenden, wenn der Spalteninhalt offensichtlich ist.
- **Nicht vorrätige Kombinationen ausblenden**

  - **Was diese Einstellung bewirkt:** Verhindert, dass Kombinationen, die derzeit nicht vorrätig sind, in der Tabelle angezeigt werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Nur vorrätige Kombinationen sind sichtbar, was die Unübersichtlichkeit reduziert und Kundenfrustration verhindert.
    - *Wenn deaktiviert:* Nicht vorrätige Kombinationen werden weiterhin angezeigt, oft mit einem „Ausverkauft“-Label oder einem deaktivierten „In den Warenkorb“-Button.
  - **Empfohlener Wert:** JA (generell besser für das Benutzererlebnis, es sei denn, Sie möchten alle Optionen für Vorbestellungen oder Benachrichtigungen bei Wiederverfügbarkeit anzeigen).
  - **Händlerszenario / Beispiel:** Ein beliebtes Schuhmodell ist in Größe 10 ausverkauft. Das Ausblenden verhindert, dass Kunden versuchen, es auszuwählen.
- **Kombinationen mit Preis = 0 ausblenden**

  - **Was diese Einstellung bewirkt:** Schließt Kombinationen mit einem Preis von Null von der Anzeige in der Tabelle aus.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kombinationen mit einem Nullpreis werden nicht angezeigt.
    - *Wenn deaktiviert:* Nullpreis-Kombinationen werden aufgelistet.
  - **Empfohlener Wert:** JA (es sei denn, Sie bieten absichtlich kostenlose Kombinationen an, was selten ist).
  - **Händlerszenario / Beispiel:** Manchmal kann eine Kombination aufgrund einer Fehlkonfiguration einen Nullpreis haben. Das Ausblenden dieser verhindert Verwirrung.
- **Nur Kombinationen mit Bildern anzeigen**

  - **Was diese Einstellung bewirkt:** Filtert die Tabelle, um nur Kombinationen anzuzeigen, denen ein spezifisches Bild zugewiesen ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Nur Kombinationen mit einzigartigen Bildern werden aufgelistet.
    - *Wenn deaktiviert:* Alle Kombinationen werden angezeigt, unabhängig davon, ob sie ein spezifisches Bild haben.
  - **Empfohlener Wert:** NEIN (es ist in der Regel besser, alle Kombinationen anzuzeigen, bei Bedarf mit Standardbildern, es sei denn, die visuelle Differenzierung ist von größter Bedeutung).
  - **Händlerszenario / Beispiel:** Wenn Sie nur Kombinationen präsentieren möchten, die deutliche visuelle Unterschiede aufweisen, und Sie nicht für alle Bilder hochgeladen haben.
- **Preis anzeigen**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Preis für jede Kombination in der Tabelle angezeigt wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine Spalte „Preis“ ist sichtbar.
    - *Wenn deaktiviert:* Die Preisspalte wird ausgeblendet.
  - **Empfohlener Wert:** JA (Preis ist ein entscheidender Faktor für Kunden).
  - **Händlerszenario / Beispiel:** Ein Kunde möchte Preise für verschiedene Größen oder Materialien eines Produkts vergleichen.
- **Stückpreis anzeigen**

  - **Was diese Einstellung bewirkt:** Zeigt den Stückpreis (z. B. Preis pro kg, pro Liter) für jede Kombination an, falls zutreffend.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Eine zusätzliche Spalte „Stückpreis“ erscheint.
    - *Wenn deaktiviert:* Diese Spalte wird nicht angezeigt.
  - **Empfohlener Wert:** JA (wenn Ihre Produkte nach Gewicht/Volumen verkauft werden und die Stückpreisgestaltung relevant ist).
  - **Händlerszenario / Beispiel:** Verkauf von Kaffeebohnen in verschiedenen Beutelgrößen, und Kunden möchten den Preis pro 100g vergleichen.
- **Preis nur für eingeloggte Kunden anzeigen**

  - **Was diese Einstellung bewirkt:** Blendet Kombinationspreise für Besucher aus, die nicht in ihren Kundenkonten angemeldet sind.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Gäste sehen keine Preise; sie sehen möglicherweise eine Nachricht, die sie zur Anmeldung auffordert.
    - *Wenn deaktiviert:* Preise sind für alle sichtbar.
  - **Empfohlener Wert:** NEIN (es sei denn, Sie betreiben einen B2B-Shop oder haben spezifische Preisstrategien, die eine Anmeldung erfordern).
  - **Händlerszenario / Beispiel:** Ein Großhandelsgeschäft, in dem die Preise verhandelt werden oder spezifisch für registrierte Geschäftskonten sind.
- **Steuerkennzeichnung anzeigen**

  - **Was diese Einstellung bewirkt:** Zeigt eine Kennzeichnung an, die angibt, ob die angezeigten Preise inklusive oder exklusive Steuern sind (z. B. „inkl. MwSt.“, „exkl. MwSt.“).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Steuerstatus wird deutlich neben den Preisen angezeigt.
    - *Wenn deaktiviert:* Es wird keine Steuerkennzeichnung angezeigt.
  - **Empfohlener Wert:** JA (verbessert die Transparenz und entspricht den gesetzlichen Anforderungen in vielen Regionen).
  - **Händlerszenario / Beispiel:** Kunden in Europa erwarten „inkl. MwSt.“-Preise zu sehen, während B2B-Kunden möglicherweise „exkl. MwSt.“ bevorzugen.

#### Weitere Konfigurationsschlüssel (Erweitert/Intern)

Diese Einstellungen werden typischerweise intern vom Modul verwaltet oder seltener von Händlern angepasst.

- `mypresta_updates`, `update_`, `updatev_`: Interne Schlüssel für Modul-Updates und Versionsverfolgung.
- `ctp_position`: Steuert die Hook-Position, an der die Tabelle angezeigt wird.
- `ctp_lasttab`: Bezogen auf die Anzeige der Tabelle in einem Produkt-Tab.
- `ctp_reference`, `ctp_ean`, `ctp_mpn`: Steuern die Anzeige der Spalten Referenz, EAN13/JAN und MPN.
- `ctp_cname`: Steuert die Anzeige des Kombinationsnamens.
- `ctp_atc`, `ctp_atcq`: Steuern den „In den Warenkorb“-Button und die Mengeneingabe.
- `ctp_ajax`: Bestimmt, ob AJAX für das Hinzufügen zum Warenkorb verwendet wird.
- `ctp_sort`: Sortieroptionen für Kombinationen innerhalb der Tabelle.
- `ctp_quantity`, `ctp_quantity_sum`: Anzeige der Lagerbestandsmenge und der Summe der Mengen.
- `ctp_availability`, `ctp_availability_d`: Anzeige des Verfügbarkeitsstatus und des Datums.
- `ctp_imagetype`, `ctp_imagetype_zoom`, `ctp_grid_imagetype`, `ctp_grid_defimg`: Bildeinstellungen (oben behandelt).
- `ctp_attributes_method`: Attribut-Anzeigemethode (oben behandelt).
- `ctp_prices_tax`: Steueranzeigeeinstellungen (oben behandelt).
- `ctp_color_method`: Wie Farbattribute angezeigt werden (z. B. Farbfelder).
- `ctp_hide_default`, `ctp_hide_r`: Standardkombination ausblenden, Kombinationen mit Nullpreis ausblenden (oben behandelt).
- `ctp_where`, `ctp_tabtype`: Platzierung der Tabelle (Hook, Tab-Typ).
- `ctp_quantity_pm`: Plus/Minus-Buttons für die Mengeneingabe.
- `ctp_view_mode`: Gesamter Tabellen-Ansichtsmodus (Tabelle, Raster usw.).
- `ctp_grid_row_attr`, `ctp_grid_col_attr`: Einstellungen für das Rasterlayout (welche Attribute Zeilen/Spalten bilden).

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### AdminCombinationstabSearchController (Back Office > Module > Produktdetailseite Kombinationstabelle > Suche)

Dieser Controller bietet eine dedizierte Schnittstelle innerhalb des PrestaShop Back Office, wahrscheinlich zur Verwaltung oder Suche von Kombinationen, möglicherweise über mehrere Produkte hinweg, oder für erweiterte Konfigurationen im Zusammenhang mit der Kombinationsanzeige.

- **Bildschirmname & Menüpfad:** Sie finden in der Regel einen neuen Menüpunkt unter **Module > Produktdetailseite Kombinationstabelle** (oder ähnlich, je nach PrestaShop-Version) mit der Bezeichnung „Suche“ oder „Kombinationssuche“.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm präsentiert wahrscheinlich eine Raster- oder Verwaltungsansicht von Produktkombinationen. Er könnte Ihnen ermöglichen:
  - Nach spezifischen Kombinationen nach Attributen, Referenz, EAN oder Produktnamen zu suchen.
  - Details von Kombinationen anzuzeigen, wie Lagerbestand, Preis und zugehöriges Produkt.
  - Möglicherweise Massenaktionen durchzuführen, wie das Aktualisieren von Lagerbestand oder Preis für mehrere Kombinationen (obwohl dies oft von der PrestaShop-Kernproduktseite gehandhabt wird).
  - Dieser Bildschirm dient hauptsächlich dazu, Kombinationsdaten strukturiert zu *verwalten* und *anzuzeigen*, getrennt von der Hauptseite zur Produktbearbeitung.
- **Auswirkung von Änderungen:** Alle hier vorgenommenen Änderungen (falls die Bearbeitung aktiviert ist) würden die Kombinationsdaten in Ihrer PrestaShop-Datenbank direkt aktualisieren und Preise, Lagerbestand und Verfügbarkeit im Front Office beeinflussen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:** Verwenden Sie diesen Bildschirm, um Kombinationsdaten schnell zu überprüfen, spezifische Kombinationen zu finden oder Lagerbestände zu überprüfen, ohne zu einzelnen Produktseiten navigieren zu müssen. Es ist ein leistungsstarkes Werkzeug für Shops mit einem großen Produktkatalog und vielen Kombinationen.

#### index.php (combinationstab/controllers/admin/index.php)

Diese Datei dient typischerweise als Platzhalter oder Weiterleitung für den Haupt-Admin-Controller des Moduls. Sie könnte einfach den `AdminCombinationstabSearchController` laden oder eine grundlegende Landingpage für den Admin-Bereich des Moduls präsentieren. Sie hat normalerweise keine direkten konfigurierbaren Einstellungen, fungiert aber als Einstiegspunkt.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Filterfunktion aktivieren | JA | Aktiviert Attributfilter für die Kombinationstabelle. |
|  | Besten Preis hervorheben | JA | Hebt die preisgünstigste Kombination visuell hervor. |
|  | Spalte für Ersparnisse anzeigen | JA | Zeigt den Rabattbetrag/-prozentsatz in einer dedizierten Spalte an. |
|  | Mengenrabatt-Schwellenwert-Tipp | JA | Zeigt Tipps für mengenbasierte Rabatte an. |
|  | Mobiles Kartenlayout | JA | Optimiert die Tabellenanzeige für mobile Geräte. |
|  | Spaltenreihenfolge | Anpassbar | Definiert die Reihenfolge der Spalten in der Tabelle. |
|  | Klicken und Kombination wechseln | JA | Aktualisiert das Hauptproduktbild/-details beim Klicken auf eine Zeile. |
|  | Bild anzeigen | JA | Zeigt Kombinationsbilder in der Tabelle an. |
|  | Bildspalte anzeigen, wenn mindestens eine Kombination ein Bild hat | JA | Stellt sicher, dass die Bildspalte erscheint, wenn eine Kombination ein Bild hat. |
|  | Standardproduktbild verwenden | JA | Fallback auf das Hauptproduktbild, wenn die Kombination kein spezifisches Bild hat. |
|  | Fancybox-Zoom aktivieren | JA | Ermöglicht das Zoomen von Kombinationsbildern. |
|  | Anzuzeigender Bildtyp | `medium_default` | Legt die Miniaturbildgröße in der Tabelle fest. |
|  | Bildtyp zum Vergrößern der Miniaturansicht | `large_default` | Legt die Zoom-Bildgröße fest. |
|  | Anzeigemethode für Attribute | Vollständiger Name | Wie Attributüberschriften beschriftet werden (z. B. „Größe“). |
|  | Attributzuordnungen mit Shop (Multistore) | Nach Bedarf konfigurieren | Filtert Attribute nach Shop im Multistore. |
|  | Bezeichnung zum Attributnamen hinzufügen | JA | Fügt den Attributgruppennamen zum Wert hinzu (z. B. „Größe: S“). |
|  | Farbattribut | Ihr Farbattribut auswählen | Identifiziert das Farbattribut für die spezielle Anzeige. |
|  | Tabellenkopf ausblenden | NEIN | Hält Spaltentitel zur besseren Übersicht sichtbar. |
|  | Nicht vorrätige Kombinationen ausblenden | JA | Entfernt nicht verfügbare Kombinationen aus der Tabelle. |
|  | Kombinationen mit Preis = 0 ausblenden | JA | Entfernt Kombinationen mit Nullpreis. |
|  | Nur Kombinationen mit Bildern anzeigen | NEIN | Zeigt alle Kombinationen an, bei Bedarf mit Standardbildern. |
|  | Preis anzeigen | JA | Zeigt den Preis für jede Kombination an. |
|  | Stückpreis anzeigen | JA (falls zutreffend) | Zeigt den Preis pro Einheit (z. B. pro kg) an. |
|  | Preis nur für eingeloggte Kunden anzeigen | NEIN | Macht Preise für alle Besucher sichtbar. |
|  | Steuerkennzeichnung anzeigen | JA | Zeigt an, ob Preise inklusive/exklusive Steuern sind. |
| **AdminCombinationstabSearchController** | Raster- / Verwaltungsansicht | N/A | Suchen, anzeigen und potenziell Kombinationen über Produkte hinweg verwalten. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Die Kombinationstabelle wird auf meiner Produktdetailseite nicht angezeigt.**
A1:

- **Modulposition überprüfen:** Gehen Sie im Back Office zu **Design > Positionen** (oder **Module > Positionen** in älteren PrestaShop-Versionen). Suchen Sie nach dem Modul „Produktdetailseite Kombinationstabelle“. Stellen Sie sicher, dass es in einen relevanten Anzeigepunkt (Hook) wie `displayProductFooter`, `displayProductExtraContent` oder `displayProductTabContent` eingehängt ist. Falls nicht, klicken Sie auf „Modul transplantieren“ und fügen Sie es dem gewünschten Hook hinzu.
- **Modulkonfiguration:** Überprüfen Sie die Konfigurationsseite des Moduls, um sicherzustellen, dass es aktiviert und nicht durch andere Einstellungen ausgeblendet ist (z. B. „Kombinationen mit Preis = 0 ausblenden“ könnte alle ausblenden, wenn alle Null sind).
- **Produkt hat Kombinationen:** Stellen Sie sicher, dass das Produkt, das Sie anzeigen, tatsächlich Kombinationen in seinen Produkteinstellungen definiert hat.
- **Cache leeren:** Gehen Sie zu **Erweiterte Parameter > Performance** und klicken Sie auf „Cache leeren“. Manchmal verhindert alter Cache-Inhalt die Anzeige neuer Module.

**F2: Meine Kombinationsbilder werden nicht angezeigt oder haben die falsche Größe.**
A2:

- **Bildeinstellungen:** Überprüfen Sie die Einstellungen „Anzuzeigender Bildtyp“ und „Bildtyp zum Vergrößern der Miniaturansicht“ in der Modulkonfiguration. Stellen Sie sicher, dass Sie geeignete Bildtypen ausgewählt haben, die in Ihrem PrestaShop-Theme existieren.
- **Kombinationsbilder hochgeladen:** Überprüfen Sie, ob Sie tatsächlich spezifische Bilder für Ihre Produktkombinationen im Tab „Kombinationen“ des Produkts im Back Office hochgeladen haben. Falls nicht, greift das Modul auf das Hauptproduktbild zurück (wenn „Standardproduktbild verwenden“ aktiviert ist).
- **Miniaturansichten neu generieren:** Wenn Sie Bildtypen geändert oder neue Bilder hochgeladen haben, gehen Sie zu **Design > Bildeinstellungen** (oder **Einstellungen > Bilder**) und klicken Sie auf „Miniaturansichten neu generieren“ für die relevanten Bildtypen (z. B. `medium_default`, `large_default`).

**F3: Die Tabelle sieht auf meinem benutzerdefinierten Theme seltsam oder falsch ausgerichtet aus.**
A3:

- **CSS-Konflikte:** Benutzerdefinierte Themes haben manchmal widersprüchliche CSS-Stile. Dieses Modul versucht, kompatibel zu sein, aber kleinere Anpassungen könnten erforderlich sein.
- **Support kontaktieren:** Wenn Sie mit CSS vertraut sind, können Sie die Elemente mit den Entwicklertools Ihres Browsers überprüfen und versuchen, widersprüchliche Stile zu überschreiben. Andernfalls kontaktieren Sie den MyPresta.eu-Support mit Details zu Ihrem Theme und einem Screenshot; sie können oft eine schnelle Lösung anbieten.
- **Modul-Updates:** Stellen Sie sicher, dass Sie die neueste Version des Moduls verwenden, da Kompatibilitätsverbesserungen oft in Updates enthalten sind.

**F4: Preise werden nicht korrekt angezeigt oder sind ausgeblendet.**
A4:

- **Preisanzeigeeinstellungen:** Überprüfen Sie „Preis anzeigen“ und „Preis nur für eingeloggte Kunden anzeigen“ in der Modulkonfiguration. Wenn Letzteres aktiviert ist, stellen Sie sicher, dass Sie als Kunde angemeldet sind, um Preise zu sehen.
- **PrestaShop Kernpreise:** Überprüfen Sie, ob die Preise für Ihre Kombinationen im Tab „Kombinationen“ des Produkts korrekt eingestellt sind.
- **Steuereinstellungen:** Überprüfen Sie „Steuerkennzeichnung anzeigen“ und Ihre allgemeinen PrestaShop-Steuereinstellungen (**International > Steuern**), um sicherzustellen, dass die Preise wie erwartet berechnet und angezeigt werden (inkl./exkl. Steuern).

**F5: Wie ändere ich die Reihenfolge der Attribute in der Tabelle?**
A5:

- Die Einstellung „Spaltenreihenfolge“ des Moduls ermöglicht es Ihnen, die Spalten neu anzuordnen. Für die Reihenfolge der Attribute selbst (z. B. „Größe“ vor „Farbe“) wird dies typischerweise im PrestaShop-Kern verwaltet: **Katalog > Attribute & Funktionen > Attribute** und **Attributgruppen**. Die dort festgelegte Reihenfolge beeinflusst normalerweise, wie sie in der Modultabelle erscheinen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Produktdetailseite Kombinationstabelle“ (`combinationstab`) folgt einer Standard-PrestaShop-Modularchitektur, die Hooks für die Front-Office-Anzeige und benutzerdefinierte Admin-Controller für erweiterte Konfiguration und Datenverwaltung stark nutzt. Es integriert sich tief in die Kernprodukt- und Kombinationsdaten von PrestaShop und rendert dynamisch HTML-Tabellen oder -Raster mithilfe von Smarty-Templates. AJAX wird für Funktionen wie „In den Warenkorb“ und das Umschalten von Kombinationen für ein nahtloses Benutzererlebnis verwendet. Das Modul führt keine benutzerdefinierten `ObjectModel`-Klassen ein, sondern arbeitet direkt mit bestehenden `Product`- und `Combination`-Objekten.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller verarbeiten spezifische AJAX-Anfragen oder dedizierte Front-Office-Funktionalitäten.

- `controllers/front/BackInStock.php`
  - **Klassenname & Elternklasse:** `CombinationstabBackInStockModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Verarbeitet wahrscheinlich AJAX-Anfragen im Zusammenhang mit „Wieder auf Lager“-Benachrichtigungen für bestimmte Kombinationen. Dies könnte das Absenden eines Formulars zur Registrierung für Benachrichtigungen beinhalten, wenn eine nicht vorrätige Kombination verfügbar wird.
- `controllers/front/CsvImport.php`
  - **Klassenname & Elternklasse:** `CombinationstabCsvImportModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Deutet auf Funktionalität zum Importieren von Kombinationsdaten über CSV vom Front-Office hin, möglicherweise für spezifische Benutzergruppen oder B2B-Szenarien. Dies würde das Parsen von CSV-Dateien und das Aktualisieren von Produktkombinationen beinhalten.
- `controllers/front/Export.php`
  - **Klassenname & Elternklasse:** `CombinationstabExportModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Bietet Funktionalität zum Exportieren von Kombinationsdaten, möglicherweise für bestimmte Produkte oder gefilterte Sets, wahrscheinlich im CSV- oder ähnlichen Format. Nützlich für B2B oder Datenanalyse.
- `controllers/front/index.php`
  - **Klassenname & Elternklasse:** `CombinationstabIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Oft ein Platzhalter oder ein Standard-Dispatcher. Er könnte allgemeine AJAX-Anfragen im Zusammenhang mit der Kombinationstabelle verarbeiten, die nicht in spezifischere Controller passen, oder einfach weiterleiten.
- `controllers/front/PriceCalculator.php`
  - **Klassenname & Elternklasse:** `CombinationstabPriceCalculatorModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Verarbeitet AJAX-Anfragen zur dynamischen Berechnung und Rückgabe von Preisen für Kombinationen, besonders relevant für Mengenrabatte oder komplexe Preisregeln, um Echtzeit-Preisaktualisierungen ohne Seitenneuladungen zu gewährleisten.
- `controllers/front/Reorder.php`
  - **Klassenname & Elternklasse:** `CombinationstabReorderModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Erleichtert wahrscheinlich die Nachbestellung zuvor gekaufter Kombinationen, möglicherweise von der Kundenkontoseite oder einer dedizierten „Nachbestellungs“-Liste.
- `controllers/front/Wishlist.php`
  - **Klassenname & Elternklasse:** `CombinationstabWishlistModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Verwaltet AJAX-Interaktionen mit einer Wunschlistenfunktion, die in die Kombinationstabelle integriert ist, sodass Kunden spezifische Kombinationen zu ihrer Wunschliste hinzufügen können.

#### Back-Office Admin-Controller

Diese Controller stellen die administrative Schnittstelle für das Modul bereit.

- `controllers/admin/AdminCombinationstabSearchController.php`
  - **Tab-Name und verwaltete Entität:** „Kombinationssuche“ (oder ähnlich, zugänglich über das Modulmenü). Verwaltet `Product`-Kombinationen.
  - **Verantwortlichkeit:** Implementiert eine Such- und Verwaltungsschnittstelle für Produktkombinationen. Dieser Controller verwendet wahrscheinlich eine `HelperList` oder `HelperForm`, um ein filterbares und sortierbares Raster von Kombinationen anzuzeigen, das Administratoren ermöglicht, Kombinationsdaten (z. B. Lagerbestand, Preis, Referenz) schnell zu finden und potenziell zu bearbeiten, ohne zu einzelnen Produktseiten navigieren zu müssen. Er könnte auch Massenaktionen verarbeiten.
- `controllers/admin/index.php`
  - **Tab-Name und verwaltete Entität:** N/A (Einstiegspunkt).
  - **Verantwortlichkeit:** Ein gängiges Muster für Admin-Controller-Verzeichnisse. Diese Datei dient typischerweise als Standard-Einstiegspunkt oder als Weiterleitung zum Haupt-`AdminCombinationstabSearchController`. Sie enthält normalerweise keine direkte Logik, stellt aber sicher, dass der Admin-Menüpunkt auf einen gültigen Controller verweist.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier zeigt keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Dies deutet darauf hin, dass das Modul hauptsächlich bestehende PrestaShop-Kernfunktionen und -objekte (`Product`, `Combination`, `Attribute`, `AttributeGroup`) erweitert, anstatt neue Datenmodelle einzuführen. Die gesamte Geschäftslogik ist wahrscheinlich in der Hauptdatei `combinationstab.php` und ihren Controllern gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul verwendet eine Vielzahl von JavaScript-Dateien, um dynamische Front-Office- und Back-Office-Funktionalitäten bereitzustellen.

- `combinationstab/js/admin.js`
  - **Geltungsbereich:** Back-Office.
  - **Details:** Verarbeitet die JavaScript-Logik für die Administrationsseiten des Moduls, einschließlich Formularinteraktionen, AJAX-Aufrufen für Konfigurationsaktualisierungen und potenziell dynamische Elemente innerhalb der `AdminCombinationstabSearchController`-Schnittstelle.
- `combinationstab/js/atc.js`
  - **Geltungsbereich:** Front-Office.
  - **Details:** Verwaltet die „In den Warenkorb“-Funktionalität für die Kombinationstabelle. Es bindet Klickereignisse an „In den Warenkorb“-Buttons, verarbeitet Mengeneingaben und sendet AJAX-Anfragen an den PrestaShop-Warenkorb-Controller, um ausgewählte Kombinationen (potenziell mehrere gleichzeitig) ohne Seitenneuladung hinzuzufügen.
- `combinationstab/js/combinationstab-switch.js`
  - **Geltungsbereich:** Front-Office.
  - **Details:** Implementiert die Funktion „Klicken und Kombination wechseln“. Es lauscht auf Klicks auf Kombinationszeilen in der Tabelle und aktualisiert dynamisch das Hauptproduktbild, den Preis und andere Produktdetails auf der Seite, um die ausgewählte Kombination widerzuspiegeln.
- `combinationstab/js/combinationstab.js`
  - **Geltungsbereich:** Front-Office.
  - **Details:** Die Haupt-Front-Office-JavaScript-Datei für die Kombinationstabelle. Sie initialisiert die Tabelle, verarbeitet allgemeine Interaktionen, verwaltet potenziell die Anzeige von Lagerbestand, Verfügbarkeit und Preisaktualisierungen basierend auf Benutzereingaben oder -auswahlen.
- `combinationstab/js/ctp-extras.js`
  - **Geltungsbereich:** Front-Office.
  - **Details:** Enthält zusätzliche, nicht-kernbezogene JavaScript-Funktionalitäten für die Kombinationstabelle, wie z. B. Tooltip-Anzeigen, kleinere UI-Verbesserungen oder spezifische Interaktionen, die nicht von den Hauptskripten abgedeckt werden.
- `combinationstab/js/ctp-filters.js`
  - **Geltungsbereich:** Front-Office.
  - **Details:** Implementiert die Filterlogik für die Kombinationstabelle. Es lauscht auf Änderungen in Filter-Dropdowns oder Eingabefeldern, blendet Tabellenzeilen basierend auf ausgewählten Attributwerten dynamisch aus/ein und aktualisiert die sichtbaren Kombinationen.
- `combinationstab/js/ctp-mobile.js`
  - **Geltungsbereich:** Front-Office.
  - **Details:** Verarbeitet das responsive Verhalten der Kombinationstabelle, insbesondere die Implementierung der Funktion „Mobiles Kartenlayout“. Es erkennt die Bildschirmgröße und transformiert die Tabelle in ein kartenbasiertes Layout für eine bessere mobile Benutzerfreundlichkeit.
- `combinationstab/js/ctp-wishlist-toast.js`
  - **Geltungsbereich:** Front-Office.
  - **Details:** Bietet visuelles Feedback (z. B. eine Toast-Benachrichtigung), wenn eine Kombination zu einer Wunschliste hinzugefügt wird, was das Benutzererlebnis verbessert.
- `combinationstab/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office (wahrscheinlich).
  - **Details:** Bietet Autocomplete-Funktionalität, wahrscheinlich für Produkt- oder Kombinationssuchfelder innerhalb der Admin-Oberflächen des Moduls (z. B. `AdminCombinationstabSearchController`).
- `combinationstab/views/js/wishlist.js`
  - **Geltungsbereich:** Front-Office.
  - **Details:** Dediziertes JavaScript für die Wunschlistenintegration, das AJAX-Aufrufe zum Hinzufügen/Entfernen von Elementen aus der Wunschliste direkt aus der Kombinationstabelle verarbeitet.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält mehrere CSS-Dateien für das Front-Office-Styling und die Back-Office-Administration.

- `combinationstab/css/admin.css`
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Details:** Gestaltet die Konfigurationsseite des Moduls und alle benutzerdefinierten Admin-Oberflächen (wie `AdminCombinationstabSearchController`), um ein konsistentes Erscheinungsbild innerhalb des PrestaShop Back Office zu gewährleisten.
- `combinationstab/css/combinationstab.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Details:** Enthält das Kern-Styling für die Kombinationstabelle, einschließlich Tabellenlayout, Zellauffüllung, Textausrichtung und grundlegender Responsivität.
- `combinationstab/css.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Details:** Potenziell ein älteres oder ergänzendes Stylesheet für das Front-Office oder spezifische Überschreibungen.
- `combinationstab/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office (wahrscheinlich).
  - **Details:** Stile für die Autocomplete-Suchfelder, die im Admin-Panel verwendet werden.
- `combinationstab/views/css/ctp-admin.css`
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Details:** Zusätzliches oder spezifisches Admin-Styling, möglicherweise für neuere Funktionen oder Überschreibungen von `admin.css`.
- `combinationstab/views/css/wishlist.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Details:** Stile für den Wunschlisten-Button und alle zugehörigen Elemente innerhalb der Kombinationstabelle.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet Smarty-Templates, um alle seine Front-Office- und Back-Office-Ansichten zu rendern.

#### Hook-Templates (`views/templates/hook/`)

Diese Templates sind so konzipiert, dass sie gerendert werden, wenn spezifische PrestaShop-Hooks ausgeführt werden.

- `views/templates/hook/columns/cells.tpl`
  - **Hook:** Wahrscheinlich innerhalb des Haupt-Kombinationstabellen-Templates gerendert.
  - **Ausgabe:** Definiert die Struktur und den Inhalt einzelner Datenzellen innerhalb der Tabellenzeilen (z. B. Anzeige von Attributwerten, Preis, Mengeneingabe).
- `views/templates/hook/columns/headers.tpl`
  - **Hook:** Wahrscheinlich innerhalb des Haupt-Kombinationstabellen-Templates gerendert.
  - **Ausgabe:** Definiert die Kopfzellen für die Kombinationstabelle und zeigt Spaltentitel wie „Bild“, „Größe“, „Preis“ an.
- `views/templates/hook/columns/_wishlist_btn.tpl`
  - **Hook:** In Kombinationszeilen integriert.
  - **Ausgabe:** Rendert den „Zur Wunschliste hinzufügen“-Button oder das Symbol für jede Kombination in der Tabelle.
- `views/templates/hook/customer_account.tpl`
  - **Hook:** `displayCustomerAccount`
  - **Ausgabe:** Fügt einen Link oder Block zur Kundenkontoseite hinzu, möglicherweise für den Zugriff auf Nachbestellungslisten, exportierte Daten oder die Wunschlistenverwaltung.
- `views/templates/hook/grid/_axis_label.tpl`
  - **Hook:** Intern verwendet, wenn `ctp_view_mode` auf ein Rasterlayout eingestellt ist.
  - **Ausgabe:** Rendert Beschriftungen für die Achsen (Zeilen/Spalten) einer rasterartigen Kombinationsanzeige.
- `views/templates/hook/grid/_cell.tpl`
  - **Hook:** Intern verwendet, wenn `ctp_view_mode` auf ein Rasterlayout eingestellt ist.
  - **Ausgabe:** Rendert einzelne Zellen innerhalb einer rasterartigen Kombinationsanzeige, die Kombinationsdetails enthalten.
- `views/templates/hook/productfooter.tpl`
  - **Hook:** `displayProductFooter`
  - **Ausgabe:** Das primäre Template zum Rendern der Kombinationstabelle, wenn sie unterhalb des Hauptproduktinhalts platziert wird. Dies ist oft die Standard- oder häufigste Platzierung.
- `views/templates/hook/productfooter_grid.tpl`
  - **Hook:** `displayProductFooter` (bedingt durch den Ansichtsmodus).
  - **Ausgabe:** Ein alternatives Template für `displayProductFooter`, speziell zum Rendern der Kombinationen in einem Rasterlayout anstelle einer traditionellen Tabelle.
- `views/templates/hook/quickViewScripts.tpl`
  - **Hook:** Potenziell `displayHeader` oder `actionFrontControllerSetMedia` (für Quick-View-Modals).
  - **Ausgabe:** Enthält notwendiges JavaScript oder initialisiert Modulfunktionalität speziell für Produkt-Quick-View-Modals, um sicherzustellen, dass die Kombinationstabelle in diesen Pop-ups funktioniert.
- `views/templates/hook/tab.tpl`
  - **Hook:** `displayProductTabContent` (oder ähnlich für Produkt-Tabs).
  - **Ausgabe:** Rendert die Kombinationstabelle innerhalb eines dedizierten Produkt-Tabs auf der Produktdetailseite.
- `views/templates/hook/volume_discounts.tpl`
  - **Hook:** In Kombinationszeilen integriert oder als Tooltip.
  - **Ausgabe:** Zeigt Informationen zu Mengenrabatten für spezifische Kombinationen an.
- `views/templates/hook/_filters.tpl`
  - **Hook:** Oberhalb der Kombinationstabelle gerendert.
  - **Ausgabe:** Rendert die Attributfilter-Oberfläche für die Kombinationstabelle.
- `views/templates/hook/_toolbar.tpl`
  - **Hook:** Oberhalb der Kombinationstabelle gerendert.
  - **Ausgabe:** Rendert eine Symbolleiste, die potenziell Filter, Suche oder andere interaktive Elemente für die Kombinationstabelle enthält.

#### Admin-Templates (`views/templates/admin/`)

Diese Templates werden für die Back-Office-Konfigurations- und Verwaltungsbildschirme des Moduls verwendet.

- `views/templates/admin/b2b.tpl`
  - **Ausgabe:** Template für B2B-spezifische Einstellungen oder Funktionen innerhalb des Admin-Panels.
- `views/templates/admin/b2b_groups.tpl`
  - **Ausgabe:** Template zur Verwaltung von B2B-Kundengruppen oder deren spezifischen Preis-/Sichtbarkeitseinstellungen.
- `views/templates/admin/column_editor.tpl`
  - **Ausgabe:** Bietet eine Oberfläche für Administratoren, um die Reihenfolge und Sichtbarkeit der Spalten in der Front-Office-Kombinationstabelle anzupassen.
- `views/templates/admin/getCombinations.tpl`
  - **Ausgabe:** Wird von `AdminCombinationstabSearchController` verwendet, um eine Liste oder ein Raster von Kombinationen anzuzeigen.
- `views/templates/admin/getProducts.tpl`
  - **Ausgabe:** Wird von `AdminCombinationstabSearchController` oder anderen Admin-Tools verwendet, um eine Liste von Produkten anzuzeigen.
- `views/templates/admin/grid_block_editor.tpl`
  - **Ausgabe:** Oberfläche zur Konfiguration der rasterartigen Anzeige von Kombinationen, potenziell zur Definition, welche Attribute Zeilen und Spalten bilden.
- `views/templates/admin/menu.tpl`
  - **Ausgabe:** Rendert die Untermenüpunkte des Moduls innerhalb des PrestaShop Back Office.
- `views/templates/admin/overrides_entity.tpl`
  - **Ausgabe:** Template zur Verwaltung von entitätsspezifischen Überschreibungen (z. B. produktspezifische Einstellungen für die Tabelle).
- `views/templates/admin/overrides_fields.tpl`
  - **Ausgabe:** Template zur Verwaltung von feldspezifischen Überschreibungen.
- `views/templates/admin/overrides_list.tpl`
  - **Ausgabe:** Template zur Auflistung und Verwaltung verschiedener für das Modul konfigurierter Überschreibungen.
- `views/templates/admin/presets.tpl`
  - **Ausgabe:** Oberfläche zum Speichern und Laden von Konfigurations-Presets für die Kombinationstabelle.
- `views/templates/admin/selectedProducts.tpl`
  - **Ausgabe:** Zeigt eine Liste von Produkten an, die für spezifische Modulkonfigurationen oder Überschreibungen ausgewählt wurden.
- `views/templates/admin/subtabs.tpl`
  - **Ausgabe:** Rendert Unter-Navigations-Tabs innerhalb der Konfigurationsoberfläche des Moduls.
- `views/templates/admin/tabs.tpl`
  - **Ausgabe:** Rendert Haupt-Navigations-Tabs für die Modulkonfiguration.
- `views/templates/admin/tabstype.tpl`
  - **Ausgabe:** Konfigurationsoptionen bezüglich der Anzeige der Kombinationstabelle innerhalb von Produkt-Tabs.

#### Front-Office-Templates (`views/templates/front/`)

- `views/templates/front/wishlist.tpl`
  - **Ausgabe:** Rendert die Front-Office-Wunschlistenoberfläche, potenziell eine dedizierte Seite oder ein Modal, das über die Kombinationstabelle zur Wunschliste hinzugefügte Artikel anzeigt.

#### Andere Templates

- `combinationstab/lib/searchTool/views/scripts.tpl`
  - **Ausgabe:** Enthält JavaScript-Snippets oder initialisiert Skripte für die Suchwerkzeugfunktionalität.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Moduldossier zeigt keine benutzerdefinierten SQL-Dateien. Dies impliziert, dass das Modul hauptsächlich die PrestaShop-Tabelle `ps_configuration` verwendet, um seine Einstellungen zu speichern, und sich auf bestehende Kerntabellen wie `ps_product_attribute`, `ps_product_attribute_combination`, `ps_product_attribute_shop`, `ps_stock_available` usw. für Kombinationsdaten verlässt.

- **`ps_configuration`**: Speichert alle Moduleinstellungen (z. B. `CTP_POSITION`, `CTP_IMAGE`, `CTP_PRICE_LOGGED`, `CTP_MOBILE_CARD_LAYOUT`).

#### Registrierte Hooks-Tabelle

Das Modul registriert sich bei verschiedenen PrestaShop-Hooks, um seinen Inhalt und seine Funktionalität einzufügen.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `ActionAdminControllerSetMedia` | Wenn ein Admin-Controller initialisiert und Medien (JS/CSS) gesetzt werden. | Fügt modulspezifisches JS/CSS in das Back Office ein. |
| `displayRightColumn` | Rendert Inhalte in der rechten Spalte des Front Office. | Zeigt die Kombinationstabelle in der rechten Spalte an (weniger üblich für Tabellen). |
| `displayProductFooter` | Rendert Inhalte unterhalb der Hauptproduktinformationen auf der Produktdetailseite. | Primärer Hook zum Anzeigen der Kombinationstabelle unterhalb des Produkts. |
| `displayHeader` | Rendert Inhalte im `<head>`-Bereich des Front Office. | Fügt modulspezifisches JS/CSS, Meta-Tags oder andere Head-Elemente für die Front-Office-Funktionalität ein. |
| `displayProductExtraContent` | Rendert zusätzliche Inhaltsblöcke auf der Produktdetailseite. | Bietet Flexibilität, die Kombinationstabelle in einem benutzerdefinierten Inhaltsblock zu platzieren. |
| `displayRightColumnProduct` | Rendert Inhalte in der rechten Spalte speziell auf der Produktdetailseite. | Ähnlich wie `displayRightColumn`, aber auf Produktdetailseiten ausgerichtet. |
| `displayCustomerAccount` | Rendert Inhalte auf der Kundenkontoseite. | Fügt Links oder Informationen zu Nachbestellungen, Wunschlisten oder Exporten hinzu. |
| `actionUpdateQuantity` | Nach der Aktualisierung der Produktmenge (Lagerbestand). | Löst potenziell Aktualisierungen der Kombinationstabellenanzeige aus (z. B. „nicht vorrätig“-Status). |
| `displayProductListFunctionalButtons` | Rendert Buttons in Produktlisten (z. B. Kategorieseiten). | Könnte Quick-View- oder Vergleichsbuttons im Zusammenhang mit Kombinationen hinzufügen. |
| `displayExtraLeft` | Rendert Inhalte in einer zusätzlichen linken Spalte (falls das Theme dies unterstützt). | Eine weitere Platzierungsoption für die Kombinationstabelle. |
| `CombinationsTable` | **Benutzerdefinierter Hook** | Ein vom Modul selbst definierter benutzerdefinierter Hook, der es anderen Modulen oder Themes ermöglicht, sich in die Tabellenausgabe zu integrieren oder diese zu überschreiben. |
| `displayLeftColumnProduct` | Rendert Inhalte in der linken Spalte speziell auf der Produktdetailseite. | Ähnlich wie `displayRightColumnProduct`, aber für die linke Spalte. |
| `displayProductTabContent` | Rendert Inhalte innerhalb eines Produkt-Tabs. | Zeigt die Kombinationstabelle in einem dedizierten Produkt-Tab an. |
| `displayCombinationsTable` | **Benutzerdefinierter Hook** | Ein weiterer benutzerdefinierter Hook, wahrscheinlich für das Haupt-Rendering der Kombinationstabelle, der eine Alternative zu `displayProductFooter` bietet. |
| `displayProductActions` | Rendert Inhalte in der Nähe des „In den Warenkorb“-Buttons auf der Produktdetailseite. | Könnte für einen kompakten Kombinationswähler oder schnelle Hinzufügen-Buttons verwendet werden. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, technischen Support und alle Fragen zum Modul „Produktdetailseite Kombinationstabelle“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen gerne zur Verfügung.

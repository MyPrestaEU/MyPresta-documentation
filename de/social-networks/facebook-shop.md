---
title: "Facebook Shop - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Facebook Shop von MyPresta.eu."
sidebar:
  label: "Facebook Shop - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook Shop auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-shop.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-shop/)
>
> ---


# Facebook Shop

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).
- **Facebook-Fanpage**: Sie müssen eine aktive Facebook-Fanpage (kein persönliches Profil) haben, auf der Sie Administrator sind.
- **SSL-Zertifikat**: Ihr PrestaShop-Shop muss über ein aktives SSL-Zertifikat (HTTPS) verfügen, damit der Facebook Shop korrekt funktioniert, da Facebook sichere Verbindungen für eingebettete Anwendungen erfordert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für Ihr Facebook Shop-Modul. Sie finden eine Reihe von Tabs oder Abschnitten, um anzupassen, wie Ihr Shop auf Facebook erscheint und funktioniert.

#### Tab „Allgemeine Einstellungen“ (oder ähnliche Anfangsansicht)

- **MyPresta.eu Updates anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob Sie Benachrichtigungen über Updates von MyPresta.eu direkt in Ihrer Modulkonfiguration sehen.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Sie erhalten Benachrichtigungen über neue Versionen oder wichtige Nachrichten von MyPresta.eu, die Ihnen helfen, Ihr Modul auf dem neuesten Stand zu halten.
    - *Wenn deaktiviert:* Sie sehen diese Benachrichtigungen nicht, was bedeuten könnte, dass Sie wichtige Updates oder Fehlerbehebungen verpassen.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Lassen Sie dies aktiviert, um sicherzustellen, dass Sie immer über die neuesten Verbesserungen und Sicherheitspatches für Ihr Facebook Shop-Modul informiert sind.
- **Facebook Shop Sprachanzeige:** (`faceshop_lang_disp`)

  - **Was diese Einstellung bewirkt:** Legt fest, ob die Sprachauswahl in Ihrem Facebook Shop sichtbar ist.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können die Sprache Ihres Facebook Shops wechseln, nützlich für internationale Shops.
    - *Wenn deaktiviert:* Der Shop wird in der Standardsprache oder der von Facebook erkannten Sprache angezeigt, ohne eine explizite Auswahl.
  - **Empfohlener Wert:** JA (wenn Sie mehrere Sprachen in PrestaShop aktiviert haben)
  - **Händlerszenario / Beispiel:** Wenn Sie an Kunden in verschiedenen Ländern verkaufen und Ihren PrestaShop-Shop übersetzt haben, aktivieren Sie dies, damit sie in ihrer bevorzugten Sprache stöbern können.
- **Facebook Shop Währungsanzeige:** (`faceshop_curr_disp`)

  - **Was diese Einstellung bewirkt:** Legt fest, ob die Währungsauswahl in Ihrem Facebook Shop sichtbar ist.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können die in Ihrem Facebook Shop angezeigte Währung wechseln, nützlich für internationale Shops.
    - *Wenn deaktiviert:* Der Shop zeigt die Preise in Ihrer Standardwährung an.
  - **Empfohlener Wert:** JA (wenn Sie mehrere Währungen in PrestaShop aktiviert haben)
  - **Händlerszenario / Beispiel:** Wenn Sie Zahlungen in USD, EUR und GBP akzeptieren, aktivieren Sie dies, damit Kunden die Preise in ihrer lokalen Währung sehen können.
- **Modul-Rewrite aktivieren (SEO-freundliche URLs):** (`faceshop_modrew`)

  - **Was diese Einstellung bewirkt:** Steuert, ob das Modul SEO-freundliche URLs innerhalb des Facebook Shops verwendet, ähnlich wie Ihr Haupt-PrestaShop-Shop.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* URLs für Produkte und Kategorien innerhalb des Facebook Shops sind sauber und beschreibend (z.B. `ihrshop.com/produkt/mein-tolles-produkt`). Dies ist im Allgemeinen besser für SEO und Benutzererfahrung.
    - *Wenn deaktiviert:* URLs könnten weniger lesbar sein (z.B. `ihrshop.com/index.php?id_product=123`).
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Aktivieren Sie dies immer für eine bessere Suchmaschinen-Sichtbarkeit und ein professionelleres Aussehen Ihrer von Facebook geteilten Produktlinks.

#### Tab „Startseiten-Einstellungen“

- **Anzahl der Startseiten-Artikel anzeigen:** (`faceshop_homepage_itemcount`)

  - **Was diese Einstellung bewirkt:** Legt die Anzahl der Produkte fest, die auf der Startseite Ihres Facebook Shops angezeigt werden sollen.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf 10 gesetzt:* Die Startseite Ihres Facebook Shops zeigt 10 Produkte an.
    - *Wenn auf 20 gesetzt:* Die Startseite Ihres Facebook Shops zeigt 20 Produkte an.
  - **Empfohlener Wert:** 12-24 (genug, um Vielfalt zu zeigen, ohne die Seite zu überladen).
  - **Händlerszenario / Beispiel:** Wenn Sie sofort eine große Auswahl an Produkten präsentieren möchten, stellen Sie eine höhere Zahl ein. Wenn Sie ein saubereres Aussehen mit weniger, prominenteren Artikeln bevorzugen, stellen Sie eine niedrigere Zahl ein.
- **Reduzierte Produkte auf der Startseite anzeigen:** (`faceshop_homepage_disphot`)

  - **Was diese Einstellung bewirkt:** Steuert, ob reduzierte (im Angebot befindliche) Produkte auf der Startseite Ihres Facebook Shops angezeigt werden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Aktuell reduzierte Produkte werden prominent angezeigt, was Impulskäufe fördert.
    - *Wenn deaktiviert:* Nur Produkte zum regulären Preis erscheinen auf der Startseite (es sei denn, andere Anzeigeoptionen sind aktiviert).
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Nutzen Sie dies, um die Aufmerksamkeit auf Ihre Aktionen zu lenken und Lagerbestände abzubauen.
- **Neue Produkte auf der Startseite anzeigen:** (`faceshop_homepage_dispnew`)

  - **Was diese Einstellung bewirkt:** Steuert, ob Ihre neuesten Produkte auf der Startseite Ihres Facebook Shops angezeigt werden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kürzlich hinzugefügte Produkte werden präsentiert, wodurch Ihr Shop für wiederkehrende Besucher frisch und spannend bleibt.
    - *Wenn deaktiviert:* Neue Produkte haben keinen eigenen Bereich auf der Startseite.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Wenn Sie häufig neue Artikel hinzufügen, ist dies eine großartige Möglichkeit, diese hervorzuheben und wiederholte Besuche zu fördern.
- **Startseiten-Stammkategorie anzeigen:** (`faceshop_homepage_root`)

  - **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl einer bestimmten Stammkategorie, aus der Produkte auf der Startseite Ihres Facebook Shops angezeigt werden sollen. Wenn leer gelassen, werden Produkte aus Ihrer Standard-PrestaShop-Stammkategorie angezeigt.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn eine bestimmte Kategorie ausgewählt ist:* Nur Produkte aus dieser Kategorie und ihren Unterkategorien erscheinen auf der Startseite.
    - *Wenn leer gelassen:* Produkte aus der Standard-Stammkategorie Ihres gesamten Shops werden für die Startseitenanzeige berücksichtigt.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben eine spezifische Marketingstrategie.
  - **Händlerszenario / Beispiel:** Wenn Sie eine spezielle Kampagne für „Sommerkollektion“ durchführen und nur diese Produkte auf der Startseite Ihres Facebook Shops anzeigen möchten, würden Sie hier die Kategorie „Sommerkollektion“ auswählen.

#### Tab „Header-Einstellungen“

- **Header im Facebook Shop anzeigen:** (`faceshop_header_disp`)
  - **Was diese Einstellung bewirkt:** Steuert, ob der Header-Bereich Ihres PrestaShop-Shops (Logo, Suchleiste, Warenkorb-Zusammenfassung) innerhalb des eingebetteten Facebook Shops sichtbar ist.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ihr Facebook Shop hat einen vertrauten Header, wodurch er sich mehr wie Ihr Haupt-Shop anfühlt.
    - *Wenn deaktiviert:* Der Header wird ausgeblendet, was ein minimalistischeres Aussehen bietet.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Das Sichtbarhalten des Headers trägt zur Markenkonsistenz bei und bietet wesentliche Navigationselemente wie die Suchleiste.

#### Tab „Kategorieseiten-Einstellungen“

- **Stammkategorie für Facebook Shop:** (`faceshop_cat_root`)

  - **Was diese Einstellung bewirkt:** Definiert die Hauptkategorie, ab der Ihr Facebook Shop Produkte und Kategorien anzeigt. Dies fungiert als „Wurzel“ für die Navigation Ihres Facebook Shops.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn „Startseite“ (Standard-PrestaShop-Wurzel) ausgewählt ist:* Alle Kategorien und Produkte aus Ihrem gesamten Shop sind zugänglich.
    - *Wenn eine bestimmte Kategorie (z.B. „Bekleidung“) ausgewählt ist:* Nur „Bekleidung“ und ihre Unterkategorien/Produkte sind im Facebook Shop sichtbar.
  - **Empfohlener Wert:** „Startseite“ (oder die Stammkategorie Ihres Haupt-Shops), es sei denn, Sie möchten den Umfang Ihres Facebook Shops einschränken.
  - **Händlerszenario / Beispiel:** Wenn Sie nur eine bestimmte Produktlinie (z.B. „Elektronik“) auf Facebook verkaufen möchten, würden Sie dies auf Ihre Kategorie „Elektronik“ einstellen.
- **Neue Produkte auf Kategorieseiten anzeigen:** (`faceshop_cat_dispnew`)

  - **Was diese Einstellung bewirkt:** Steuert, ob neue Produkte auf Kategorieseiten innerhalb Ihres Facebook Shops hervorgehoben werden oder einen eigenen Bereich haben.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden, die Kategorien durchsuchen, werden leicht kürzlich hinzugefügte Artikel entdecken.
    - *Wenn deaktiviert:* Neue Produkte erscheinen einfach in der regulären Liste ohne besondere Betonung.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Hilft Kunden, Ihre neuesten Artikel zu entdecken, auch wenn sie bestimmte Produkttypen durchsuchen.
- **Reduzierte Produkte auf Kategorieseiten anzeigen:** (`faceshop_cat_disphot`)

  - **Was diese Einstellung bewirkt:** Steuert, ob reduzierte Produkte auf Kategorieseiten innerhalb Ihres Facebook Shops hervorgehoben werden oder einen eigenen Bereich haben.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden, die Kategorien durchsuchen, werden leicht reduzierte Artikel entdecken.
    - *Wenn deaktiviert:* Reduzierte Produkte erscheinen einfach in der regulären Liste ohne besondere Betonung.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Fördert Käufe, indem reduzierte Artikel innerhalb relevanter Kategorien sichtbarer gemacht werden.
- **Anzahl der Artikel pro Kategorieseite:** (`faceshop_cat_itemcount`)

  - **Was diese Einstellung bewirkt:** Legt die Anzahl der Produkte fest, die pro Seite angezeigt werden, wenn Kunden Kategorien in Ihrem Facebook Shop durchsuchen.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf 12 gesetzt:* Jede Kategorieseite zeigt 12 Produkte vor der Paginierung an.
    - *Wenn auf 30 gesetzt:* Jede Kategorieseite zeigt 30 Produkte an.
  - **Empfohlener Wert:** 12-24 (Standard für die meisten E-Commerce-Websites).
  - **Händlerszenario / Beispiel:** Eine höhere Zahl reduziert Klicks, kann aber die Ladezeit der Seiten verlangsamen. Eine niedrigere Zahl erfordert mehr Klicks, kann aber weniger überwältigend wirken.
- **Kategorie-Anzeigestil:** (`faceshop_cat_dispstyle`)

  - **Was diese Einstellung bewirkt:** Legt fest, wie Kategorien im Facebook Shop präsentiert werden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Option A (z.B. „Rasteransicht“):* Kategorien werden als Raster von Bildern/Namen angezeigt.
    - *Option B (z.B. „Listenansicht“):* Kategorien werden als vertikale Liste angezeigt.
  - **Empfohlener Wert:** Rasteransicht (oft visuell ansprechender).
  - **Händlerszenario / Beispiel:** Wählen Sie den Stil, der am besten zur Ästhetik Ihrer Marke passt und wie Sie möchten, dass Kunden Ihr Produktsortiment navigieren.

#### Tab „Slider-Einstellungen“

- **Slider im Facebook Shop anzeigen:** (`faceshop_slider_disp`)

  - **Was diese Einstellung bewirkt:** Steuert, ob ein Bild-Slider (Karussell) in Ihrem Facebook Shop angezeigt wird. Dieser Slider zeigt typischerweise ausgewählte Produkte, Aktionen oder Banner.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein rotierendes Banner oder Produkt-Slider wird angezeigt und zieht Aufmerksamkeit auf sich.
    - *Wenn deaktiviert:* Es wird kein Slider angezeigt, was zu einem statischen Layout führt.
  - **Empfohlener Wert:** JA (wenn Sie über ansprechende Bilder für einen Slider verfügen).
  - **Händlerszenario / Beispiel:** Verwenden Sie den Slider, um Ihre neueste Kollektion, saisonale Verkäufe oder Bestseller direkt oben in Ihrem Facebook Shop hervorzuheben.
- **Slider-Übergangszeit (in Millisekunden):** (`faceshop_slider_time`)

  - **Was diese Einstellung bewirkt:** Legt fest, wie lange jede Folie sichtbar bleibt, bevor sie zur nächsten übergeht.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf 3000 (3 Sekunden) gesetzt:* Folien wechseln alle 3 Sekunden.
    - *Wenn auf 5000 (5 Sekunden) gesetzt:* Folien wechseln alle 5 Sekunden.
  - **Empfohlener Wert:** 4000-6000 (4-6 Sekunden), um Benutzern genügend Zeit zum Lesen zu geben.
  - **Händlerszenario / Beispiel:** Passen Sie dies an die Menge der Informationen auf Ihren Folien an. Kürzere Zeiten für reine Bildfolien, längere für Folien mit Text.
- **Slider-Platzierung:** (`faceshop_slider_place`)

  - **Was diese Einstellung bewirkt:** Legt fest, wo der Slider in Ihrem Facebook Shop erscheint (z.B. oben auf der Seite, unter den Kategorien).
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf „Oben“ gesetzt:* Der Slider ist das Erste, was Kunden sehen.
    - *Wenn auf „Unter Produkte“ gesetzt:* Der Slider erscheint weiter unten auf der Seite.
  - **Empfohlener Wert:** Oben (für maximale Sichtbarkeit).
  - **Händlerszenario / Beispiel:** Platzieren Sie den Slider oben, um sofort die Aufmerksamkeit mit Ihren wichtigsten Aktionen zu erregen.

#### Tab „Menü-Einstellungen“

- **Link „Neue Produkte“ im Menü anzeigen:** (`faceshop_menu_newproducts`)

  - **Was diese Einstellung bewirkt:** Fügt einen Link zu „Neue Produkte“ im Navigationsmenü Ihres Facebook Shops hinzu.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können leicht klicken, um alle Ihre neuesten Ergänzungen zu sehen.
    - *Wenn deaktiviert:* Dieser spezifische Link wird nicht im Menü angezeigt.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Wesentlich für Shops, die häufig ihr Inventar aktualisieren, um Kunden zu helfen, neue Artikel zu entdecken.
- **Link „Sale-Produkte“ im Menü anzeigen:** (`faceshop_menu_saleproducts`)

  - **Was diese Einstellung bewirkt:** Fügt einen Link zu „Sale-Produkte“ oder „Rabatte“ im Navigationsmenü Ihres Facebook Shops hinzu.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können schnell alle Ihre reduzierten Artikel finden.
    - *Wenn deaktiviert:* Dieser spezifische Link wird nicht im Menü angezeigt.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Großartig, um Traffic auf Ihre Aktionen zu lenken und den Umsatz zu steigern.
- **Link „Informationsseiten“ im Menü anzeigen:** (`faceshop_menu_informations`)

  - **Was diese Einstellung bewirkt:** Fügt einen Link zu Ihren PrestaShop CMS (Informations-)Seiten (z.B. Über uns, Lieferung, AGB) im Navigationsmenü hinzu.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können wichtige nicht-produktbezogene Informationen direkt abrufen.
    - *Wenn deaktiviert:* Diese Links werden nicht im Menü angezeigt.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Entscheidend für den Aufbau von Vertrauen und die Bereitstellung notwendiger Kundendienstinformationen.
- **Link „Kontaktseite“ im Menü anzeigen:** (`faceshop_menu_contact`)

  - **Was diese Einstellung bewirkt:** Fügt einen Link zu Ihrer PrestaShop-Kontaktseite im Navigationsmenü hinzu.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können leicht finden, wie sie Sie kontaktieren können.
    - *Wenn deaktiviert:* Dieser spezifische Link wird nicht im Menü angezeigt.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Bietet einen direkten Kanal für Kundenanfragen und verbessert den Support.
- **Menü-Kategorie-Anzeigestil:** (`faceshop_menu_catstyle`)

  - **Was diese Einstellung bewirkt:** Legt fest, wie Kategorien im Hauptnavigationsmenü Ihres Facebook Shops angezeigt werden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Option A (z.B. „Dropdown“):* Kategorien erscheinen in einem Dropdown-Menü.
    - *Option B (z.B. „Horizontale Liste“):* Kategorien erscheinen als horizontale Liste.
  - **Empfohlener Wert:** Dropdown (für viele Kategorien) oder Horizontale Liste (für wenige Kategorien).
  - **Händlerszenario / Beispiel:** Wenn Sie viele Produktkategorien haben, hält ein Dropdown-Menü die Navigation sauber. Wenn Sie nur wenige Hauptkategorien haben, könnte eine horizontale Liste direkter sein.
- **Link „Hersteller“ im Menü anzeigen:** (`faceshop_menu_manuf`)

  - **Was diese Einstellung bewirkt:** Fügt einen Link zu Ihrer PrestaShop-Herstellerseite im Navigationsmenü hinzu.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können Produkte nach Marke oder Hersteller durchsuchen.
    - *Wenn deaktiviert:* Dieser spezifische Link wird nicht im Menü angezeigt.
  - **Empfohlener Wert:** JA (wenn Sie Produkte von mehreren verschiedenen Marken verkaufen).
  - **Händlerszenario / Beispiel:** Wenn Sie ein Wiederverkäufer verschiedener Marken sind, hilft dies Kunden, Produkte ihrer Lieblingshersteller zu finden.

#### Tab „Produktseiten-Einstellungen“

- **Breadcrumb-Navigation anzeigen:** (`faceshop_display_breadcrumb`)

  - **Was diese Einstellung bewirkt:** Steuert, ob die „Breadcrumb“-Navigation (z.B. Startseite > Kategorie > Unterkategorie > Produkt) auf Produktseiten angezeigt wird.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Hilft Kunden, ihren Standort innerhalb der Shop-Hierarchie zu verstehen und leicht zu übergeordneten Kategorien zurückzunavigieren.
    - *Wenn deaktiviert:* Der Breadcrumb-Pfad wird ausgeblendet.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Verbessert die Benutzererfahrung durch klare Navigationspfade, insbesondere für Shops mit tiefen Kategorienstrukturen.
- **Produktbeschreibung kürzen:** (`faceshop_pdisp_trim`)

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, werden lange Produktbeschreibungen auf der Produktseite gekürzt, oft mit einem „Mehr lesen“-Link.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Produktseiten erscheinen sauberer, und Benutzer können die Beschreibung bei Interesse erweitern.
    - *Wenn deaktiviert:* Vollständige Produktbeschreibungen werden immer angezeigt, was Seiten sehr lang machen kann.
  - **Empfohlener Wert:** JA (für Produkte mit sehr langen Beschreibungen).
  - **Händlerszenario / Beispiel:** Verhindert, dass Produktseiten übermäßig lang werden, insbesondere auf Mobilgeräten, indem zuerst eine prägnante Zusammenfassung angezeigt wird.
- **Produktpreis anzeigen:** (`faceshop_pdisp_price`)

  - **Was diese Einstellung bewirkt:** Steuert, ob der Produktpreis auf Produktseiten sichtbar ist.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Preis wird deutlich angezeigt.
    - *Wenn deaktiviert:* Der Preis wird ausgeblendet.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Das Ausblenden von Preisen ist für einen E-Commerce-Shop im Allgemeinen nicht empfehlenswert, es sei denn, Sie haben eine spezifische B2B-Strategie, die Angebote erfordert. Für die meisten Einzelhändler sind Preise unerlässlich.
- **Produktname anzeigen:** (`faceshop_pdisp_name`)

  - **Was diese Einstellung bewirkt:** Steuert, ob der Produktname auf Produktseiten sichtbar ist.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Produktname wird angezeigt.
    - *Wenn deaktiviert:* Der Produktname wird ausgeblendet.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Der Produktname ist grundlegend für die Identifizierung; lassen Sie dies immer aktiviert.
- **Produktbild anzeigen:** (`faceshop_pdisp_image`)

  - **Was diese Einstellung bewirkt:** Steuert, ob das Produktbild auf Produktseiten sichtbar ist.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Hauptproduktbild und zusätzliche Bilder werden angezeigt.
    - *Wenn deaktiviert:* Produktbilder werden ausgeblendet.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Produktbilder sind entscheidend für Online-Verkäufe; lassen Sie dies immer aktiviert.

#### Tab „Social Sharing Einstellungen“

- **Facebook Teilen-Button anzeigen:** (`faceshop_social_facebook`)

  - **Was diese Einstellung bewirkt:** Fügt einen Facebook „Teilen“-Button zu Produktseiten innerhalb Ihres Facebook Shops hinzu.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können Produkte leicht mit ihren Facebook-Freunden teilen, was das virale Marketing erhöht.
    - *Wenn deaktiviert:* Der Facebook Teilen-Button wird nicht angezeigt.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Ermutigen Sie Kunden, Ihre Produkte in ihren eigenen Timelines zu verbreiten.
- **Pinterest Teilen-Button anzeigen:** (`faceshop_social_pinterest`)

  - **Was diese Einstellung bewirkt:** Fügt einen Pinterest „Pin It“-Button zu Produktseiten innerhalb Ihres Facebook Shops hinzu.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden können Produktbilder leicht auf ihren Pinterest-Boards pinnen, was Traffic von Pinterest generiert.
    - *Wenn deaktiviert:* Der Pinterest Teilen-Button wird nicht angezeigt.
  - **Empfohlener Wert:** JA (besonders wenn Ihre Produkte visuell ansprechend sind).
  - **Händlerszenario / Beispiel:** Großartig für Mode, Wohndekoration, Handwerk und andere visuell orientierte Produkte, um das Pinterest-Publikum zu nutzen.
- **Google+ Teilen-Button anzeigen:** (`faceshop_social_google`)

  - **Was diese Einstellung bewirkt:** Fügt einen Google+ Teilen-Button zu Produktseiten innerhalb Ihres Facebook Shops hinzu.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *When enabled:* Customers can share products on Google+.
    - *When disabled:* The Google+ share button will not appear.
  - **Empfohlener Wert:** NEIN (Google+ wurde eingestellt).
  - **Händlerszenario / Beispiel:** Diese Plattform ist nicht mehr aktiv, daher ist es unnötig, sie aktiviert zu lassen.

#### Tab „Footer-Einstellungen“

- **Footer im Facebook Shop anzeigen:** (`faceshop_footer_disp`)
  - **Was diese Einstellung bewirkt:** Steuert, ob der Footer-Bereich Ihres PrestaShop-Shops (Copyright, Links, Zahlungssymbole) innerhalb des eingebetteten Facebook Shops sichtbar ist.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ihr Facebook Shop hat einen vertrauten Footer, der die Markenkonsistenz aufrechterhält und zusätzliche Links bereitstellt.
    - *Wenn deaktiviert:* Der Footer wird ausgeblendet.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Der Footer enthält oft wichtige rechtliche Links (Datenschutzrichtlinie, Nutzungsbedingungen) und Kontaktinformationen, die für Vertrauen und Compliance sichtbar bleiben sollten.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Allgemeine Einstellungen** | MyPresta.eu Updates anzeigen | JA | Modul-Update-Benachrichtigungen erhalten. |
|  | Facebook Shop Sprachanzeige (`faceshop_lang_disp`) | JA | Kunden erlauben, die Shop-Sprache zu ändern. |
|  | Facebook Shop Währungsanzeige (`faceshop_curr_disp`) | JA | Kunden erlauben, die Shop-Währung zu ändern. |
|  | Modul-Rewrite aktivieren (SEO-freundliche URLs) (`faceshop_modrew`) | JA | Saubere, beschreibende URLs für besseres SEO und UX verwenden. |
| **Startseiten-Einstellungen** | Anzahl der Startseiten-Artikel anzeigen (`faceshop_homepage_itemcount`) | 12-24 | Anzahl der Produkte, die auf der Startseite angezeigt werden. |
|  | Reduzierte Produkte auf der Startseite anzeigen (`faceshop_homepage_disphot`) | JA | Produkte im Angebot auf der Startseite hervorheben. |
|  | Neue Produkte auf der Startseite anzeigen (`faceshop_homepage_dispnew`) | JA | Neuheiten auf der Startseite hervorheben. |
|  | Startseiten-Stammkategorie anzeigen (`faceshop_homepage_root`) | Leer (Standard-Wurzel) | Eine spezifische Kategorie für Startseiten-Produkte auswählen. |
| **Header-Einstellungen** | Header im Facebook Shop anzeigen (`faceshop_header_disp`) | JA | Den Header Ihres Shops (Logo, Suche, Warenkorb) anzeigen. |
| **Kategorieseiten-Einstellungen** | Stammkategorie für Facebook Shop (`faceshop_cat_root`) | Startseite (Standard-Wurzel) | Definiert die Startkategorie für den Facebook Shop. |
|  | Neue Produkte auf Kategorieseiten anzeigen (`faceshop_cat_dispnew`) | JA | Neue Produkte innerhalb von Kategorien hervorheben. |
|  | Reduzierte Produkte auf Kategorieseiten anzeigen (`faceshop_cat_disphot`) | JA | Sale-Produkte innerhalb von Kategorien hervorheben. |
|  | Anzahl der Artikel pro Kategorieseite (`faceshop_cat_itemcount`) | 12-24 | Anzahl der Produkte, die pro Kategorieseite angezeigt werden. |
|  | Kategorie-Anzeigestil (`faceshop_cat_dispstyle`) | Rasteransicht | Wie Kategorien präsentiert werden (Raster/Liste). |
| **Slider-Einstellungen** | Slider im Facebook Shop anzeigen (`faceshop_slider_disp`) | JA | Einen Bild-/Produkt-Slider anzeigen. |
|  | Slider-Übergangszeit (in Millisekunden) (`faceshop_slider_time`) | 4000-6000 | Geschwindigkeit der Slider-Übergänge. |
|  | Slider-Platzierung (`faceshop_slider_place`) | Oben | Position des Sliders (z.B. oben auf der Seite). |
| **Menü-Einstellungen** | Link „Neue Produkte“ im Menü anzeigen (`faceshop_menu_newproducts`) | JA | „Neue Produkte“ zum Navigationsmenü hinzufügen. |
|  | Link „Sale-Produkte“ im Menü anzeigen (`faceshop_menu_saleproducts`) | JA | „Sale-Produkte“ zum Navigationsmenü hinzufügen. |
|  | Link „Informationsseiten“ im Menü anzeigen (`faceshop_menu_informations`) | JA | Links zu CMS-Seiten (Über uns, etc.) hinzufügen. |
|  | Link „Kontaktseite“ im Menü anzeigen (`faceshop_menu_contact`) | JA | Einen „Kontakt“-Link hinzufügen. |
|  | Menü-Kategorie-Anzeigestil (`faceshop_menu_catstyle`) | Dropdown | Wie Kategorien im Menü erscheinen (Dropdown/Liste). |
|  | Link „Hersteller“ im Menü anzeigen (`faceshop_menu_manuf`) | JA | Einen Link zu Herstellern/Marken hinzufügen. |
| **Produktseiten-Einstellungen** | Breadcrumb-Navigation anzeigen (`faceshop_display_breadcrumb`) | JA | Navigationspfad anzeigen (Startseite > Kategorie > Produkt). |
|  | Produktbeschreibung kürzen (`faceshop_pdisp_trim`) | JA | Lange Produktbeschreibungen kürzen. |
|  | Produktpreis anzeigen (`faceshop_pdisp_price`) | JA | Produktpreis anzeigen. |
|  | Produktname anzeigen (`faceshop_pdisp_name`) | JA | Produktname anzeigen. |
|  | Produktbild anzeigen (`faceshop_pdisp_image`) | JA | Produktbilder anzeigen. |
| **Social Sharing Einstellungen** | Facebook Teilen-Button anzeigen (`faceshop_social_facebook`) | JA | Teilen auf Facebook erlauben. |
|  | Pinterest Teilen-Button anzeigen (`faceshop_social_pinterest`) | JA | Teilen auf Pinterest erlauben. |
|  | Google+ Teilen-Button anzeigen (`faceshop_social_google`) | NEIN | Google+ wurde eingestellt. |
| **Footer-Einstellungen** | Footer im Facebook Shop anzeigen (`faceshop_footer_disp`) | JA | Den Footer Ihres Shops anzeigen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein Facebook Shop wird nicht angezeigt, oder ich sehe eine Fehlermeldung.**
A1:

- **SSL überprüfen:** Stellen Sie sicher, dass Ihr PrestaShop-Shop über ein gültiges SSL-Zertifikat (HTTPS) verfügt. Facebook erfordert sichere Verbindungen für eingebettete Anwendungen. Wenn Ihr Shop nicht HTTPS ist, wird der Facebook Shop nicht geladen.
- **Facebook-Seiteneinstellungen:** Überprüfen Sie nochmals, ob Sie Administrator der Facebook-Fanpage sind und ob der „Shop“-Tab auf Facebook selbst korrekt hinzugefügt und konfiguriert ist.
- **Modulkonfiguration:** Gehen Sie zurück zur Modulkonfiguration in PrestaShop und stellen Sie sicher, dass alle Einstellungen korrekt gespeichert sind.
- **Cache leeren:** Gehen Sie in PrestaShop zu **Erweiterte Einstellungen > Leistung** und leeren Sie den Smarty-Cache, den Browser-Cache und alle anderen Caches.

**F2: Produkte werden nicht korrekt angezeigt, oder Bilder fehlen.**
A2:

- **Produkteinstellungen:** Überprüfen Sie, ob die Produkte, die Sie erwarten, in Ihrem Haupt-PrestaShop-Shop aktiv und sichtbar sind.
- **Bildpfade:** Stellen Sie sicher, dass Ihre Produktbilder korrekte Pfade haben und öffentlich zugänglich sind.
- **Moduleinstellungen:** Überprüfen Sie die Einstellungen `faceshop_pdisp_image`, `faceshop_pdisp_name`, `faceshop_pdisp_price`, um sicherzustellen, dass sie aktiviert sind.
- **Stammkategorie:** Bestätigen Sie, dass Ihre Einstellungen `faceshop_cat_root` und `faceshop_homepage_root` korrekt auf Kategorien verweisen, die Produkte enthalten.

**F3: Das Modul sieht auf mobilen Geräten innerhalb von Facebook anders aus.**
A3:

- **Facebook App vs. Browser:** Das Erlebnis kann zwischen der mobilen Facebook-App und dem Zugriff auf Facebook über einen mobilen Browser leicht variieren. Das Modul ist responsiv gestaltet, aber der Facebook-eigene Wrapper kann das endgültige Aussehen beeinflussen.
- **Responsivität überprüfen:** Testen Sie Ihren Haupt-PrestaShop-Shop auf Mobilgeräten, um sicherzustellen, dass er vollständig responsiv ist. Der Facebook Shop erbt einen Großteil seines Stylings von Ihrem Haupt-Shop.
- **Benutzerdefiniertes CSS:** Wenn Sie benutzerdefiniertes CSS in Ihrem PrestaShop-Theme haben, könnte es zu Interferenzen kommen. Konsultieren Sie einen Webentwickler, um das CSS innerhalb des Facebook-iFrames zu überprüfen.

**F4: Wie übersetze ich den Facebook Shop in andere Sprachen?**
A4:

- **PrestaShop-Übersetzungen:** Das Facebook Shop-Modul zieht Inhalte (Produktnamen, Beschreibungen, Kategorienamen) direkt aus Ihrem PrestaShop-Shop. Stellen Sie sicher, dass alle Ihre Produkt- und Kategorieinhalte in PrestaShop selbst übersetzt sind.
- **Modultext:** Für den eigenen Interface-Text des Moduls (z.B. Link „Neue Produkte“) gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**. Wählen Sie „Übersetzungen installierter Module“, Ihr Theme, Ihre Sprache und suchen Sie dann das Modul „Facebook Shop“, um dessen spezifische Zeichenketten zu übersetzen.
- **Sprachauswahl:** Stellen Sie sicher, dass `faceshop_lang_disp` in der Modulkonfiguration aktiviert ist, damit Kunden die Sprache wechseln können.

**F5: Mein Facebook Shop lädt langsam.**
A5:

- **Bildoptimierung:** Stellen Sie sicher, dass Ihre Produktbilder für die Webnutzung optimiert sind (komprimiert, passende Abmessungen). Große Bilder sind eine häufige Ursache für langsames Laden.
- **Hosting-Leistung:** Überprüfen Sie die Leistung Ihres Webhostings. Ein langsamer Server wirkt sich sowohl auf Ihren Haupt-Shop als auch auf Ihren Facebook Shop aus.
- **Anzahl der Produkte:** Wenn Sie eine sehr hohe Anzahl von Produkten auf der Startseite oder den Kategorieseiten anzeigen (`faceshop_homepage_itemcount`, `faceshop_cat_itemcount`), sollten Sie diese Zahlen reduzieren.
- **Caching:** Stellen Sie sicher, dass die Caching-Mechanismen von PrestaShop korrekt konfiguriert sind (**Erweiterte Einstellungen > Leistung**).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Facebook Shop-Modul (`faceshop`) ist als Standard-PrestaShop-Modul konzipiert, das hauptsächlich die Klasse `Module` erweitert. Es nutzt das PrestaShop-Konfigurationssystem (`Configuration::get()`, `Configuration::updateValue()`), um seine Einstellungen zu speichern. Die Kernfunktionalität des Moduls besteht darin, eine vereinfachte Version des PrestaShop-Front-Office innerhalb eines iFrames auf einer Facebook-Fanpage zu rendern. Dies wird erreicht, indem die Anzeige dynamisch basierend auf einem spezifischen URL-Parameter (`?fc=module&module=faceshop&controller=shop`) angepasst wird. Das Modul führt keine benutzerdefinierten Datenbanktabellen oder komplexen ObjectModels ein, sondern manipuliert die bestehende PrestaShop-Front-Office-Anzeige durch Hooks und Template-Overrides.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** dedizierten Front-Office- oder Back-Office-Controller im Verzeichnis `controllers/`.
Seine Front-Office-Funktionalität wird hauptsächlich von der Hauptdatei `faceshop.php` gehandhabt, die Anfragen über einen benutzerdefinierten `shop`-Controller-Parameter abfängt (z.B. `index.php?fc=module&module=faceshop&controller=shop`). Dieser Ansatz ermöglicht es dem Modul, eine modifizierte Version des Standard-PrestaShop-Front-Office innerhalb des Facebook-iFrames zu rendern, anstatt völlig neue Seitenstrukturen zu erstellen.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul führt keine benutzerdefinierten Klassen oder ObjectModels in einem `classes/`-Verzeichnis ein. Die gesamte Kernlogik ist in der Hauptdatei `faceshop/faceshop.php` gekapselt.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält mehrere JavaScript-Dateien, hauptsächlich zur Verbesserung der Front-Office-Anzeige innerhalb des Facebook-iFrames.

- `faceshop/jscolor/jscolor.js`
  - **Geltungsbereich:** Back-Office (wahrscheinlich im Modulkonfigurationsformular verwendet).
  - **Beschreibung:** Eine JavaScript-Bibliothek für einen Farbwähler. Sie ermöglicht Administratoren die einfache Auswahl von Farben für Moduleinstellungen, obwohl in den Konfigurationsschlüss keine expliziten Farbeinstellungen identifiziert wurden, ist dies ein gängiges Dienstprogramm für die UI-Anpassung.
- `faceshop/js/advajax.js`
  - **Geltungsbereich:** Front-Office (innerhalb des Facebook-iFrames).
  - **Beschreibung:** Wahrscheinlich ein benutzerdefiniertes AJAX-Dienstprogramm-Skript. Es würde asynchrone Anfragen zum Laden von Produktdaten, Paginierung oder anderen dynamischen Inhalten innerhalb des Facebook Shops ohne vollständige Seitenneuladungen verarbeiten. Dies verbessert die Benutzererfahrung, indem der Shop reaktionsschneller wirkt.
- `faceshop/js/jquery.nivo.slider.pack.js`
  - **Geltungsbereich:** Front-Office (innerhalb des Facebook-iFrames).
  - **Beschreibung:** Eine gepackte Version des Nivo Slider jQuery-Plugins. Dieses Skript ist für die Funktionalität des Bild-Sliders (`faceshop_slider_disp`) auf der Facebook Shop-Startseite verantwortlich und verwaltet Übergänge, Navigation und Auto-Play.
- `faceshop/js/shop2.js`
  - **Geltungsbereich:** Front-Office (innerhalb des Facebook-iFrames).
  - **Beschreibung:** Dies ist wahrscheinlich die wichtigste benutzerdefinierte JavaScript-Datei für die Front-End-Logik des Facebook Shops. Sie würde Code enthalten für:
    - Initialisierung des Nivo Sliders.
    - Handhabung des dynamischen Ladens von Inhalten (z.B. „Mehr laden“-Buttons für Produkte).
    - Anpassung des Layouts oder Verhaltens speziell für die Facebook-iFrame-Umgebung.
    - Potenzielle Handhabung von Interaktionen mit dem Facebook SDK (obwohl nicht explizit erwähnt, üblich für Facebook-Apps).
    - Alle benutzerdefinierten UI-Verbesserungen oder Event-Listener, die spezifisch für den eingebetteten Shop sind.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält mehrere CSS-Dateien, um den eingebetteten Facebook Shop zu gestalten und sicherzustellen, dass er konsistent aussieht und innerhalb des iFrames korrekt funktioniert.

- `faceshop/css.css`
  - **Geltungsbereich:** Front-Office (innerhalb des Facebook-iFrames).
  - **Beschreibung:** Ein allgemeines Stylesheet für den Facebook Shop. Es enthält wahrscheinlich Kern-Layout-Regeln, Typografie und grundlegendes Styling für gängige Elemente (Buttons, Links, Formulare), um ein konsistentes Aussehen zu gewährleisten.
- `faceshop/css/style.css`
  - **Geltungsbereich:** Front-Office (innerhalb des Facebook-iFrames).
  - **Beschreibung:** Dies könnte ein spezifischeres Stylesheet sein, das `css.css` möglicherweise überschreibt oder erweitert. Es könnte Stile für spezifische Modul-Funktionen oder Layout-Anpassungen enthalten, um besser in die Facebook-Umgebung zu passen.
- `faceshop/default/default.css`
  - **Geltungsbereich:** Front-Office (innerhalb des Facebook-iFrames).
  - **Beschreibung:** Dieses Stylesheet ist wahrscheinlich Teil des Nivo Slider-Plugins und bietet Standard-Styling für die Navigation, Beschriftungen und das allgemeine Erscheinungsbild des Sliders. Entwickler können diese Stile überschreiben, um sie an das Theme des Shops anzupassen.
- `faceshop/style.css`
  - **Geltungsbereich:** Front-Office (innerhalb des Facebook-iFrames).
  - **Beschreibung:** Ähnlich wie `faceshop/css/style.css` könnte dies ein weiteres primäres Stylesheet oder eine Fallback-/Legacy-Datei sein. Es würde die visuelle Präsentation der Shop-Elemente definieren und sicherstellen, dass sie innerhalb des Facebook-iFrames korrekt gerendert werden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Moduldossier weist darauf hin, dass keine spezifischen `.tpl`-Dateien in `views/templates/` gefunden wurden. Dies deutet darauf hin, dass das Modul hauptsächlich funktioniert, indem es:

1. **Standard-PrestaShop-Front-Office-Anfragen abfängt:** Beim Zugriff über die Facebook Shop-URL modifiziert das Modul wahrscheinlich die globalen Smarty-Variablen oder Template-Pfade, um bestehende PrestaShop-Theme-Templates zu rendern.
2. **`display`-Methoden innerhalb von `faceshop.php` verwendet:** Die `display()`-Methoden des Moduls könnten direkt HTML rendern oder Snippets aus dem Haupt-PrestaShop-Theme einbinden, wobei Elemente dynamisch basierend auf seiner Konfiguration hinzugefügt oder entfernt werden.
3. **JavaScript-gesteuertes Rendering:** Einige Elemente könnten nach dem anfänglichen Seitenaufbau dynamisch von den JavaScript-Dateien eingefügt oder modifiziert werden.

Wenn benutzerdefinierte Templates vorhanden wären, würden sie typischerweise gefunden in:

- `views/templates/hook/`: Für Inhalte, die in spezifischen PrestaShop-Hooks gerendert werden.
- `views/templates/admin/`: Für benutzerdefinierte Back-Office-Formulare oder Anzeigen.
- `views/templates/front/`: Für eigenständige Front-Office-Seiten oder spezifische Modulinhalte.

Das Fehlen expliziter `.tpl`-Dateien impliziert eine direktere Manipulation des bestehenden PrestaShop-Front-Office-Rendering-Prozesses.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle seine Konfigurationseinstellungen werden in der Tabelle `ps_configuration` (oder `_configuration` je nach Tabellenpräfix) unter Verwendung der in Abschnitt 4.1 aufgeführten Konfigurationsschlüssel gespeichert.
- **Registrierte Hooks-Tabelle**:
  Das Modul interagiert hauptsächlich mit der PrestaShop-Front-Office-Anzeige. Während das Dossier „Header, Spalten, Produkt oder Footer“ als Front-Office-Hooks auflistet, besteht die Kernfunktionalität des Moduls darin, das *gesamte* Front-Office einzubetten. Es verwendet wahrscheinlich eine Kombination aus:

  - **`hookDisplayHeader`**: Zum Einfügen seiner CSS- und JavaScript-Assets und möglicherweise zur Änderung des `<head>`-Abschnitts für die Facebook-iFrame-Kompatibilität.
  - **`hookDisplayFooter`**: Zum Einfügen zusätzlicher Skripte oder Inhalte am unteren Rand der Seite.
  - **`actionFrontControllerSetMedia`**: (PrestaShop 1.7+) Zum Registrieren seiner CSS- und JS-Dateien.
  - **Interne Logik zum Rendern des Shops**: Das Modul hat wahrscheinlich eine interne Logik, die, wenn sie als innerhalb des Facebook-iFrames geladen erkannt wird, die Standard-PrestaShop-Front-Office-Ausgabe modifiziert, um Elemente basierend auf seinen Konfigurationseinstellungen (z.B. `faceshop_header_disp`, `faceshop_footer_disp`) auszublenden/anzuzeigen. Dies wird oft durch Überschreiben oder Manipulieren von Smarty-Variablen und Template-Zuweisungen innerhalb der `display()`- oder `hook`-Methoden des Moduls erreicht.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Vor dem Hauptinhalt der Seite, innerhalb des `<head>`-Abschnitts. | Einfügen der CSS- und JavaScript-Dateien des Moduls, möglicherweise Änderung der Meta-Tags für den Facebook-iFrame. |
| `displayFooter` | Am Ende des Seiteninhalts, vor dem schließenden `</body>`-Tag. | Einfügen zusätzlicher Skripte oder Tracking-Codes oder Ändern des Footer-Inhalts, wenn `faceshop_footer_disp` aktiviert ist. |
| `actionFrontControllerSetMedia` (PS 1.7+) | Während der Medien-Einstellungsphase eines Front-Controllers. | Registrieren von CSS- und JS-Dateien für optimales Laden. |
| (Implizit) Produktseiten-Hooks | Auf Produktdetailseiten. | Ändern der Produktseitenanzeige basierend auf `faceshop_pdisp_trim`, `faceshop_pdisp_price` usw. und Einfügen von Social-Sharing-Buttons. |
| (Implizit) Kategorieseiten-Hooks | Auf Kategorieseiten. | Ändern der Kategorieseitenanzeige basierend auf `faceshop_cat_dispnew`, `faceshop_cat_disphot` usw. |
| (Implizit) Startseiten-Hooks | Auf der Startseite des Shops. | Rendern von Slider, ausgewählten Produkten, neuen Produkten und reduzierten Produkten basierend auf den Moduleinstellungen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für Ihr Facebook Shop-Modul wenden Sie sich bitte an Ihr Kundenkonto bei MyPresta.eu. Unser Team ist bestrebt, sicherzustellen, dass Ihr Modul optimal funktioniert und Ihnen hilft, Ihre Online-Verkäufe zu maximieren.

- **MyPresta.eu Bestellhistorie & Downloads:** <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Support-Kontakt:** <https://mypresta.eu/contact>

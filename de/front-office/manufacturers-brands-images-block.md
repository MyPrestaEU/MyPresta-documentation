---
title: "Hersteller (Marken) Bilderblock - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Hersteller (Marken) Bilderblock' von MyPresta.eu."
sidebar:
  label: "Hersteller (Marken) Bilderblock - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Manufacturers (brands) images block auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/manufacturers-brands-images-block.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/manufacturers-brands-images-block/)
>
> ---


# Hersteller (Marken) Bilderblock

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend. Es sind in der Regel keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zur Hauptseite der Einstellungen für das Modul „Hersteller (Marken) Bilderblock“. Hier können Sie anpassen, wie der Markenblock in Ihrem Shop erscheint und sich verhält.

#### **Position des Herstellerblocks**

- **Was diese Einstellung bewirkt:** Diese entscheidende Einstellung bestimmt, wo der Block mit Markenbildern auf Ihrer Website erscheint. Sie können aus verschiedenen vordefinierten Positionen (Hooks) innerhalb Ihres PrestaShop-Themes wählen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf `displayRightColumn` (oder `displayLeftColumn`) eingestellt:* Der Markenblock erscheint in der rechten (oder linken) Seitenleiste Ihres Shops, typischerweise neben anderen Blöcken wie Kategorien oder Bestsellern. Dies ist ideal für konstante Sichtbarkeit.
  - *Wenn auf `displayFooter` eingestellt:* Der Block erscheint ganz unten auf Ihrer Website, oft für ergänzende Navigation verwendet.
  - *Wenn auf `displayTop` (oder `displayTopColumn`) eingestellt:* Der Block ist oben auf Ihrer Seite sichtbar, oft im Header-Bereich, wodurch Marken sofort auffallen.
  - *Wenn auf `displayHome` eingestellt:* Der Block erscheint nur auf der Startseite Ihres Shops und ist somit ein zentrales Element zur Markenentdeckung.
- **Empfohlener Wert:** `displayHome` für eine prominente Startseitenfunktion oder `displayRightColumn` (oder `displayLeftColumn`) für konsistente Sichtbarkeit auf Produkt- und Kategorieseiten.
- **Händlerszenario / Beispiel:** Wenn Kunden beim Einkaufen von Produkten einfach Marken durchsuchen sollen, wählen Sie `displayRightColumn`. Wenn Sie auf Ihrer Startseite ein starkes Markenstatement abgeben möchten, wählen Sie `displayHome`.

#### **Karussell aktivieren**

- **Was diese Einstellung bewirkt:** Diese Einstellung verwandelt das statische Raster von Markenlogos in ein animiertes, scrollendes Karussell.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Markenlogos scrollen horizontal, sodass Sie viele Marken auf kompaktem Raum anzeigen können. Dies ist visuell dynamisch und spart Bildschirmfläche.
  - *Wenn deaktiviert (NEIN):* Markenlogos werden als statisches Raster angezeigt, das alle verfügbaren Logos auf einmal anzeigt (oder so viele, wie in die Abmessungen des Blocks passen). Dies bietet einen sofortigen Überblick ohne Interaktion.
- **Empfohlener Wert:** `JA`, wenn Sie viele Marken haben oder ein moderneres, dynamischeres Aussehen wünschen. `NEIN`, wenn Sie nur wenige Marken haben und eine statische Anzeige bevorzugen.
- **Händlerszenario / Beispiel:** Wenn Sie über 50 Marken führen, ist die Aktivierung des Karussells unerlässlich, um einen sehr langen, überladenen Block zu vermeiden. Wenn Sie nur 5-10 Marken haben, kann eine statische Anzeige ausreichend sein.

#### **Kategoriefilter aktivieren**

- **Was diese Einstellung bewirkt:** Dies ermöglicht dem Modul, nur jene Hersteller anzuzeigen, die mit Produkten innerhalb der *aktuell angezeigten Kategorie* verknüpft sind.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Auf einer Kategorieseite (z. B. „T-Shirts“) zeigt der Markenblock nur Logos von Herstellern an, die T-Shirts produzieren. Dies macht den Block für den aktuellen Browsing-Kontext des Kunden hochrelevant.
  - *Wenn deaktiviert (NEIN):* Der Markenblock zeigt immer *alle* aktiven Hersteller in Ihrem Shop an, unabhängig von der aktuellen Seite oder Kategorie.
- **Empfohlener Wert:** `JA` für eine bessere Benutzererfahrung und Relevanz, insbesondere in Shops mit vielfältigen Produktkategorien.
- **Händlerszenario / Beispiel:** Ein Kunde, der „Smartphones“ durchsucht, sieht nur Marken wie Apple, Samsung und Xiaomi, wenn dies aktiviert ist, anstatt auch Bekleidungsmarken zu sehen. Dies hilft ihm, seine Suche einzugrenzen.

#### **Auto-Scroll für Karussell aktivieren**

- **Was diese Einstellung bewirkt:** Wenn das Karussell aktiviert ist, steuert diese Einstellung, ob die Markenlogos automatisch ohne Kundeninteraktion scrollen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Karussell gleitet automatisch mit einer festgelegten Geschwindigkeit durch die Markenlogos und erzeugt einen dynamischen visuellen Effekt.
  - *Wenn deaktiviert (NEIN):* Das Karussell scrollt nur, wenn der Kunde manuell auf Navigationspfeile klickt oder das Karussell zieht.
- **Empfohlener Wert:** `JA` für eine ansprechendere und dynamischere Anzeige, aber stellen Sie sicher, dass die Geschwindigkeit nicht zu schnell ist.
- **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass alle Ihre Marken eine gewisse Sichtbarkeit erhalten, auch wenn Kunden nicht mit dem Karussell interagieren. Die Aktivierung des Auto-Scrolls erreicht dies.

#### **Geschwindigkeit des Auto-Scrolls**

- **Was diese Einstellung bewirkt:** Diese Einstellung definiert, wie schnell das Karussell automatisch von einem Satz von Marken zum nächsten scrollt, gemessen in Millisekunden. (Nur anwendbar, wenn „Auto-Scroll für Karussell aktivieren“ auf JA steht).
- **Auswirkung der Änderung dieser Einstellung:**
  - *Höherer Wert (z. B. 5000ms = 5 Sekunden):* Langsamere Scroll-Geschwindigkeit, die Kunden mehr Zeit gibt, jeden Satz von Logos anzusehen.
  - *Niedrigerer Wert (z. B. 2000ms = 2 Sekunden):* Schnellere Scroll-Geschwindigkeit, die das Karussell dynamischer, aber potenziell schwerer lesbar macht.
- **Empfohlener Wert:** 3000-5000 Millisekunden (3-5 Sekunden) für ein angenehmes Seherlebnis.
- **Händlerszenario / Beispiel:** Wenn Sie viele Marken haben und möchten, dass Kunden sie alle sehen, ohne sich gehetzt zu fühlen, stellen Sie eine langsamere Geschwindigkeit wie 4000ms ein.

#### **Karussell bei Mouseover pausieren**

- **Was diese Einstellung bewirkt:** Wenn Auto-Scroll aktiviert ist, steuert diese Einstellung, ob das Karussell vorübergehend aufhört zu scrollen, wenn ein Kunde den Mauszeiger über den Markenblock bewegt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Karussell pausiert, sodass der Kunde ein Markenlogo bequem untersuchen oder anklicken kann, ohne dass das Karussell weiterrückt. Dies verbessert die Benutzererfahrung.
  - *Wenn deaktiviert (NEIN):* Das Karussell scrollt weiterhin automatisch, auch wenn die Maus darüber ist, was für Kunden, die interagieren möchten, frustrierend sein kann.
- **Empfohlener Wert:** `JA` für eine bessere Benutzererfahrung.
- **Händlerszenario / Beispiel:** Ein Kunde sieht eine Marke, die ihm gefällt, und bewegt die Maus, um darauf zu klicken. Wenn das Karussell pausiert, kann er leicht klicken. Wenn nicht, könnte die Marke weiterrücken, bevor er reagieren kann.

#### **Größe des Markenbildes**

- **Was diese Einstellung bewirkt:** Diese Einstellung ermöglicht es Ihnen, die maximale Breite der im Block angezeigten Markenbilder zu definieren. Die Höhe wird proportional skaliert.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Größerer Wert (z. B. 150px):* Markenlogos erscheinen größer, wodurch sie prominenter und leichter sichtbar werden. Dies kann mehr Platz im Block einnehmen.
  - *Kleinerer Wert (z. B. 80px):* Markenlogos erscheinen kleiner, wodurch mehr Logos in einen bestimmten Bereich passen, aber potenziell weniger auffällig sind.
- **Empfohlener Wert:** 100-120 Pixel für ein gutes Gleichgewicht zwischen Sichtbarkeit und Platzeffizienz. Passen Sie dies an das Layout Ihres Themes an.
- **Händlerszenario / Beispiel:** Wenn Ihre Seitenleiste schmal ist, müssen Sie möglicherweise eine kleinere Bildgröße (z. B. 80px) einstellen, um zu verhindern, dass Logos überlaufen. In einem breiten Homepage-Block könnten Sie 150px für eine größere Wirkung verwenden.

#### Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Position des Herstellerblocks | `displayHome` oder `displayRightColumn` | Bestimmt, wo der Markenblock erscheint (z. B. Startseite, Seitenleiste, Fußzeile). |
| Modulkonfiguration | Karussell aktivieren | `JA` | Verwandelt das statische Raster in ein scrollendes Karussell für eine dynamische Anzeige. |
| Modulkonfiguration | Kategoriefilter aktivieren | `JA` | Zeigt nur Marken an, die für die aktuell angezeigte Kategorie relevant sind. |
| Modulkonfiguration | Auto-Scroll für Karussell aktivieren | `JA` | Lässt das Karussell automatisch durch Marken scrollen. |
| Modulkonfiguration | Geschwindigkeit des Auto-Scrolls | 3000-5000ms | Steuert, wie schnell das Karussell scrollt (in Millisekunden). |
| Modulkonfiguration | Karussell bei Mouseover pausieren | `JA` | Stoppt das Auto-Scroll, wenn ein Kunde mit der Maus über den Block fährt. |
| Modulkonfiguration | Größe des Markenbildes | 100-120px | Legt die maximale Breite für Markenlogos im Block fest. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein Markenblock wird nach der Installation nicht angezeigt oder befindet sich an der falschen Stelle.**

- **A:** Überprüfen Sie zunächst die Konfigurationsseite des Moduls in Ihrem Back Office. Stellen Sie sicher, dass die Einstellung „Position des Herstellerblocks“ korrekt ausgewählt ist. Wenn sie auf `displayHome` eingestellt ist, wird sie nur auf der Startseite angezeigt. Wenn sie auf eine Spalte eingestellt ist, stellen Sie sicher, dass Ihr Theme diese Spalte auf den von Ihnen angezeigten Seiten tatsächlich anzeigt.
- **A:** Leeren Sie Ihren PrestaShop-Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie dann oben rechts auf „Cache leeren“. Manchmal erfordern Theme-Änderungen oder neue Modulinstallationen eine Cache-Aktualisierung.
- **A:** Überprüfen Sie die „Positionen“ Ihres Themes (Design > Positionen in PS 1.7/8). Stellen Sie sicher, dass das Modul an der gewünschten Position eingehängt ist. Wenn es nicht aufgeführt ist, versuchen Sie, die Konfiguration des Moduls erneut zu speichern.

**F2: Meine Markenbilder sehen verzerrt aus oder haben nicht die richtige Größe.**

- **A:** Gehen Sie zur Modulkonfiguration und passen Sie die Einstellung „Größe des Markenbildes“ an. Dies steuert die maximale Breite.
- **A:** Stellen Sie sicher, dass die ursprünglich in PrestaShop hochgeladenen Herstellerbilder (Katalog > Hersteller) von guter Qualität sind und idealerweise ein konsistentes Seitenverhältnis aufweisen. Obwohl das Modul sie skaliert, sehen stark verzerrte Quellbilder immer noch schlecht aus.
- **A:** Nach dem Ändern der Bildgrößen ist es oft eine gute Idee, Miniaturansichten neu zu generieren. Gehen Sie zu **Design > Bildeinstellungen** (oder **Einstellungen > Bilder** in älteren PS-Versionen) und klicken Sie auf „Miniaturansichten neu generieren“. Wählen Sie „Hersteller“ als Bildtyp aus.

**F3: Das Karussell scrollt nicht oder der Auto-Scroll funktioniert nicht.**

- **A:** Überprüfen Sie, ob „Karussell aktivieren“ auf `JA` eingestellt ist. Wenn nicht, handelt es sich um einen statischen Block.
- **A:** Wenn das Karussell aktiviert ist, überprüfen Sie, ob „Auto-Scroll für Karussell aktivieren“ ebenfalls auf `JA` eingestellt ist. Wenn dies `NEIN` ist, bewegt sich das Karussell nur manuell.
- **A:** Wenn beides aktiviert ist, überprüfen Sie die Entwicklerkonsole Ihres Browsers (F12) auf JavaScript-Fehler. Konflikte mit anderen Modulen oder Theme-Skripten können manchmal die Funktion von Karussells verhindern. Versuchen Sie, andere Module vorübergehend zu deaktivieren, um das Problem zu isolieren.

**F4: Der „Kategoriefilter aktivieren“ funktioniert nicht; ich sehe immer noch alle Marken auf Kategorieseiten.**

- **A:** Stellen Sie sicher, dass diese Einstellung in der Modulkonfiguration auf `JA` gesetzt ist.
- **A:** Überprüfen Sie, ob Ihre Produkte in Ihrem PrestaShop-Katalog sowohl einer Kategorie als auch einem Hersteller korrekt zugeordnet sind. Wenn ein Produkt nicht mit einem Hersteller verknüpft ist oder der Hersteller nicht mit Produkten in dieser Kategorie verknüpft ist, wird es beim Filtern nicht angezeigt.
- **A:** Leeren Sie Ihren PrestaShop-Cache, nachdem Sie Änderungen an Produkt-/Herstellerzuordnungen vorgenommen haben.

**F5: Wie übersetze ich den Titel oder Text des Moduls?**

- **A:** Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und die Sprache, in die Sie übersetzen möchten.
- Suchen Sie das Modul „Hersteller (Marken) Bilderblock“ in der Liste und Sie können alle übersetzbaren Zeichenketten bearbeiten, die es bereitstellt (z. B. den Blocktitel).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Hersteller (Marken) Bilderblock“ (`mib`) ist ein Standard-PrestaShop-Modul, das einem MVC-ähnlichen Muster folgt. Es nutzt hauptsächlich das Hook-System von PrestaShop, um seinen Inhalt in verschiedene Front-Office-Positionen einzufügen. Die Kernlogik befindet sich in der Hauptdatei `mib.php`, die Installation, Deinstallation, Konfiguration und Inhaltsrendering für die Hooks verwaltet. Es verwendet eine JavaScript-Bibliothek von Drittanbietern (`lightslider.js`) für die Karussellfunktionalität und benutzerdefiniertes CSS für das Styling. Konfigurationseinstellungen werden in `ps_configuration` gespeichert.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird über die Methode `getContent()` in der Hauptmoduldatei gehandhabt, und das Front-Office-Rendering erfolgt direkt über Hook-Methoden.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Entitäten. Es interagiert direkt mit den PrestaShop-Kernobjekten `Manufacturer` und `Category` sowie `Configuration` für die Einstellungen.

### 4.4 JavaScript-Assets (`views/js/`)

- **`mib/lib/js/lightslider.js`**
  - **Umfang:** Front-Office.
  - **Beschreibung:** Dies ist ein jQuery-Plugin von Drittanbietern, das für die Erstellung des responsiven Inhaltskarussells verantwortlich ist. Es verwaltet die Schiebeanimation, Navigationssteuerungen und das responsive Verhalten für die Markenlogos, wenn die Karusselloption aktiviert ist.
  - **Schlüsselfunktionalität:** Initialisiert `lightSlider` auf einem angegebenen HTML-Element, verwaltet Folienübergänge, Touch-/Wischgesten und responsive Anpassungen.
- **`mib/views/js/mib.js`**
  - **Umfang:** Front-Office.
  - **Beschreibung:** Dies ist die benutzerdefinierte JavaScript-Datei des Moduls. Sie enthält die Initialisierungslogik für das `lightslider.js`-Plugin basierend auf den Konfigurationseinstellungen des Moduls.
  - **Schlüsselfunktionalität:**
    - Überprüft, ob das Karussell aktiviert ist (`MIB_CAROUSEL`-Konfiguration).
    - Initialisiert den `lightSlider` auf dem `#lightSlider`-Element innerhalb der Modulvorlage.
    - Übergibt Konfigurationsoptionen an `lightSlider` wie `auto`, `pause`, `pauseOnHover`, `item`, `slideMove`, `speed`, `loop`, `controls`, `responsive` basierend auf den Einstellungen `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED` und `MIB_IMG`.
    - Stellt sicher, dass der Slider nur initialisiert wird, wenn das Element existiert.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`mib/lib/css/lightslider.css`**
  - **Umfang:** Front-Office-Kunden-Styling.
  - **Beschreibung:** Dies ist das Kern-Stylesheet für das `lightslider.js`-Plugin. Es bietet das notwendige Styling für die Karussellstruktur, Navigationspfeile und Paginierungspunkte.
  - **Wichtige CSS-Selektoren:** `.lightSlider`, `.lSAction`, `.lSPager`, `.lslide` usw. Entwickler können diese überschreiben, um das Aussehen des Karussells anzupassen.
- **`mib/mib.css`**
  - **Umfang:** Front-Office-Kunden-Styling.
  - **Beschreibung:** Dies ist das benutzerdefinierte Stylesheet des Moduls. Es bietet spezifisches Styling für den Markenblock-Container, einzelne Markenbilder und eventuelle Hover-Effekte.
  - **Wichtige CSS-Selektoren:**
    - `#manufacturers_block_top`, `#manufacturers_block_left`, `#manufacturers_block_right`, `#manufacturers_block_home`, `#manufacturers_block_footer`: Hauptcontainer-IDs für verschiedene Hook-Positionen.
    - `.mib_manufacturer_item`: Stile für einzelne Herstellerlinks/-container.
    - `.mib_manufacturer_item img`: Stile für die Markenbilder, einschließlich `max-width`- und `height`-Anpassungen.
    - `.mib_manufacturer_item:hover img`: Definiert die Hover-Animation (z. B. `transform: scale(1.1)` für einen Zoom-Effekt).

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - **`mib/views/templates/hook/mib.tpl`**
    - **Eingehängt an:** `displayRightColumn`, `displayFooter`, `displayTop`, `displayLeftColumn`, `displayHome`, `displayTopColumn`.
    - **Zweck:** Dies ist die Haupt-Front-Office-Vorlage, die für das Rendern des Markenblocks verantwortlich ist. Sie generiert dynamisch die HTML-Struktur für ein statisches Raster von Herstellerlogos oder das `lightSlider`-Karussell, basierend auf der Konfiguration des Moduls.
    - **Schlüsselelemente:**
      - Bedingtes Rendering für Karussell (`{if $mib_carousel}`).
      - Schleife durch das `$manufacturers`-Array, um das Bild und den Link jeder Marke anzuzeigen.
      - Enthält `mib.js` und `lightslider.js`, wenn das Karussell aktiviert ist.
      - Enthält `mib.css` und `lightslider.css`.
      - Verwendet `{$link->getManufacturerLink($manufacturer.id_manufacturer, $manufacturer.link_rewrite)}` für Hersteller-URLs.
      - Verwendet `{$manufacturer.image}` für Markenbildpfade.
- **Admin-Vorlagen (`views/templates/admin/`)**:
  - **`mib/views/templates/admin/admin.tpl`**
    - **Zweck:** Diese Vorlage rendert das Konfigurationsformular des Moduls im PrestaShop Back Office. Sie zeigt alle Einstellungen (Position, Karusselloptionen, Bildgröße usw.) als Eingabefelder, Auswahlfelder und Schalter an.
    - **Schlüsselelemente:**
      - Standard-PrestaShop-Helfer-Formularstruktur (`{include file="{$smarty.const._PS_ROOT_DIR_}/src/PrestaShopBundle/Resources/views/Admin/Configure/AdvancedParameters/Blocks/form_block_content.html.twig"}`).
      - Eingabefelder für `MIB_WHERE`, `MIB_CAROUSEL`, `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED`, `MIB_FROM_CAT`, `MIB_IMG`.
      - Verwendet `{$mib_form_action}` für die Formularübermittlung.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  - Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `MIB_CAROUSEL`, `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED`, `MIB_FROM_CAT`, `MIB_IMG`, `MIB_WHERE` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt & Ort | Technischer Zweck |
| --- | --- | --- |
| `displayRightColumn` | Rendert in der rechten Seitenleiste des Front-Office. | Zeigt den Markenblock in der rechten Spalte an. |
| `displayFooter` | Rendert im Fußbereich des Front-Office. | Zeigt den Markenblock in der Fußzeile des Shops an. |
| `displayTop` | Rendert im oberen Bereich des Front-Office (oft Header). | Zeigt den Markenblock im Header-Bereich an. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien-Assets festlegt. | Wird verwendet, um die CSS- und JS-Dateien des Moduls im Back Office für die Konfiguration einzubinden. |
| `displayLeftColumn` | Rendert in der linken Seitenleiste des Front-Office. | Zeigt den Markenblock in der linken Spalte an. |
| `displayHome` | Rendert auf der Startseite des Front-Office. | Zeigt den Markenblock prominent auf der Startseite an. |
| `displayHeader` | Wird im `<head>`-Bereich jeder Front-Office-Seite ausgeführt. | Wird verwendet, um notwendige CSS- und JS-Dateien für die Front-Office-Anzeige einzubinden. |
| `displayTopColumn` | Rendert im oberen Spaltenbereich des Front-Office (unter `displayTop`). | Zeigt den Markenblock im oberen Spaltenbereich an. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Hersteller (Marken) Bilderblock“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zur Funktionalität und Integration des Moduls zur Verfügung.

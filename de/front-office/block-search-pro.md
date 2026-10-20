---
title: "Block Search Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Block Search Pro von MyPresta.eu."
sidebar:
  label: "Block Search Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Block Search Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/block-search-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/block-search-pro/)
>
> ---


# Block Search Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Block Search Pro)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie steuern, wie sich das Modul Block Search Pro verhält und in Ihrem Shop angezeigt wird.

#### 2.1.1 Allgemeine Einstellungen

**1. AJAX-Suche aktivieren**

- **Was diese Einstellung bewirkt:** Dies steuert, ob Suchergebnisse sofort erscheinen, während der Kunde tippt (AJAX), oder ob er die Eingabetaste drücken/auf die Suchschaltfläche klicken muss, um Ergebnisse zu sehen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Während Kunden in die Suchleiste tippen, erscheint eine Dropdown-Liste mit passenden Produkten in Echtzeit unterhalb des Suchfeldes. Dies bietet sofortiges Feedback und beschleunigt den Suchvorgang.
  - *Wenn deaktiviert (NEIN):* Kunden müssen ihre vollständige Suchanfrage eingeben und dann die Eingabetaste drücken oder auf die Suchschaltfläche klicken, um zur Suchergebnisseite weitergeleitet zu werden.
- **Empfohlener Wert:** JA. Dies verbessert die Benutzererfahrung erheblich, indem es sofortige Ergebnisse liefert und die Schritte zum Auffinden eines Produkts reduziert.
- **Händlerszenario / Beispiel:** Ein Kunde tippt „Kleid“ und sieht sofort Vorschläge wie „Rotes Partykleid“, „Sommer Maxikleid“ und „Schwarzes Cocktailkleid“ erscheinen, wodurch er direkt zu einer Produktseite klicken kann, ohne zu warten.

**2. Sofortsuche**

- **Was diese Einstellung bewirkt:** Ähnlich der AJAX-Suche bezieht sich dies speziell auf die „sofortige“ Anzeige von Suchergebnissen auf der Suchergebnisseite selbst, die sich aktualisiert, wenn der Benutzer seine Abfrage verfeinert. (Hinweis: In vielen modernen PrestaShop-Versionen umfasst „AJAX-Suche“ oft das sofortige Dropdown, während „Sofortsuche“ sich auf das Verhalten auf der eigentlichen Suchergebnisseite beziehen könnte).
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Wenn ein Kunde auf der Suchergebnisseite ist und seine Suchanfrage in der Suchleiste ändert, werden die Ergebnisse auf dieser Seite sofort aktualisiert, ohne dass die Seite komplett neu geladen wird.
  - *Wenn deaktiviert (NEIN):* Der Kunde müsste die geänderte Suchanfrage erneut absenden, damit die Ergebnisseite aktualisiert wird.
- **Empfohlener Wert:** JA. Dies bietet ein dynamischeres und reaktionsschnelleres Sucherlebnis.
- **Händlerszenario / Beispiel:** Ein Kunde sucht nach „Schuhe“, landet auf der Suchergebnisseite und tippt dann „rot“ in die Suchleiste auf dieser Seite. Mit der Sofortsuche filtern sich die Ergebnisse sofort, um nur rote Schuhe anzuzeigen.

**3. Leere Suchanfrage zulassen**

- **Was diese Einstellung bewirkt:** Legt fest, ob ein Kunde die Suchschaltfläche klicken oder die Eingabetaste drücken kann, ohne Suchbegriffe einzugeben.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Wenn ein Kunde mit einer leeren Eingabe auf die Suche klickt, wird er zur allgemeinen Suchergebnisseite weitergeleitet, die je nach Ihrem Theme alle Produkte oder eine Standardmeldung anzeigen kann. Dies kann manchmal zum Durchsuchen aller Produkte verwendet werden.
  - *Wenn deaktiviert (NEIN):* Die Suchschaltfläche ist inaktiv oder zeigt eine Fehlermeldung an, wenn das Eingabefeld leer ist, wodurch der Kunde gezwungen wird, ein Schlüsselwort einzugeben, bevor er sucht.
- **Empfohlener Wert:** NEIN. Im Allgemeinen ist es besser, Kunden zur Eingabe einer Abfrage anzuleiten, um Verwirrung oder leere Suchergebnisseiten zu vermeiden.
- **Händlerszenario / Beispiel:** Wenn ein Kunde versehentlich auf die Suche klickt, ohne etwas einzugeben, verhindert die Deaktivierung, dass er auf einer potenziell verwirrenden leeren Seite landet.

**4. Mindestwortlänge (in Zeichen)**

- **Was diese Einstellung bewirkt:** Legt die Mindestanzahl von Zeichen fest, die ein Kunde eingeben muss, bevor die Suchfunktion (einschließlich AJAX/Sofortsuche) mit der Suche nach Ergebnissen beginnt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Auf 3 gesetzt:* Kunden müssen mindestens drei Zeichen (z.B. „rot“) eingeben, bevor Suchvorschläge erscheinen oder eine Suche abgeschickt werden kann.
  - *Auf 1 gesetzt:* Schon ein einzelnes Zeichen (z.B. „a“) löst die Suche aus.
- **Empfohlener Wert:** 3. Dies gleicht Reaktionsfähigkeit mit Relevanz aus. Ein zu niedriger Wert (z.B. 1-2 Zeichen) kann zu viele irrelevante Vorschläge generieren, während ein zu hoher Wert Benutzer frustrieren könnte.
- **Händlerszenario / Beispiel:** Wenn auf 3 gesetzt, zeigt die Eingabe von „sh“ keine Ergebnisse, aber die Eingabe von „sch“ beginnt, Vorschläge für „Schuhe“, „Shorts“ usw. anzuzeigen.

#### 2.1.2 Suchfilteroptionen

**5. Kategorien auswählen**

- **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, die Suche auf bestimmte Produktkategorien zu beschränken. Das Modul liefert nur Ergebnisse aus den hier ausgewählten Kategorien.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn bestimmte Kategorien ausgewählt sind:* Die Suche sucht nur nach Produkten innerhalb dieser ausgewählten Kategorien. Produkte in nicht ausgewählten Kategorien erscheinen nicht in den Suchergebnissen, selbst wenn sie dem Schlüsselwort entsprechen.
  - *Wenn keine Kategorien ausgewählt sind:* Die Suche durchsucht standardmäßig alle Kategorien in Ihrem Shop.
- **Empfohlener Wert:** Wählen Sie Kategorien aus, wenn Sie Kunden zu bestimmten Produkttypen führen möchten, oder lassen Sie das Feld leer, wenn Sie eine breite Suche wünschen.
- **Händlerszenario / Beispiel:** Wenn Sie sowohl Kleidung als auch Elektronik verkaufen, aber möchten, dass die Suchleiste im Header nur Kleidung findet, würden Sie hier nur Ihre Kleidungskategorien auswählen.

**6. In Unterkategorien suchen**

- **Was diese Einstellung bewirkt:** Diese Option funktioniert in Verbindung mit „Kategorien auswählen“. Sie bestimmt, ob die Suche auch Produkte innerhalb der Unterkategorien der ausgewählten Oberkategorien einschließen soll.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Wenn Sie „Elektronik“ als Kategorie auswählen, sucht die Suche auch in „Laptops“, „Smartphones“ und allen anderen Unterkategorien von „Elektronik“.
  - *Wenn deaktiviert (NEIN):* Die Suche sucht nur nach Produkten, die direkt den ausgewählten Oberkategorien zugeordnet sind, und ignoriert deren Unterkategorien.
- **Empfohlener Wert:** JA. Die meisten Händler möchten, dass Suchen innerhalb eines ausgewählten Kategoriebaums umfassend sind.
- **Händlerszenario / Beispiel:** Wenn Sie „Bekleidung“ auswählen und „In Unterkategorien suchen“ aktivieren, findet eine Suche nach „Hemd“ Hemden in „Herren-T-Shirts“, „Damenblusen“ usw.

**7. Hersteller**

- **Was diese Einstellung bewirkt:** Ermöglicht es Ihnen, die Suche auf Produkte bestimmter Hersteller zu beschränken.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn bestimmte Hersteller ausgewählt sind:* Die Suche liefert nur Produkte der ausgewählten Hersteller. Produkte von nicht ausgewählten Herstellern erscheinen nicht.
  - *Wenn keine Hersteller ausgewählt sind:* Die Suche durchsucht standardmäßig alle Hersteller in Ihrem Shop.
- **Empfohlener Wert:** Wählen Sie Hersteller aus, wenn Sie eine markenspezifische Suche anbieten möchten, oder lassen Sie das Feld für eine allgemeine Suche leer.
- **Händlerszenario / Beispiel:** Wenn Sie einen speziellen Suchblock für „Premium-Marken“ haben, könnten Sie hier nur High-End-Hersteller auswählen.

#### 2.1.3 Anzeigeeinstellungen

**8. Größe des Suchblocks**

- **Was diese Einstellung bewirkt:** Steuert die visuelle Breite des Sucheingabefeldes in Pixeln.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Auf 280px gesetzt:* Die Suchleiste ist 280 Pixel breit.
  - *Auf 100% gesetzt (oder leer lassen für automatische Erkennung):* Die Suchleiste passt sich dem verfügbaren Platz an und füllt oft ihren Container aus.
- **Empfohlener Wert:** Leer lassen für automatische Erkennung oder auf einen Prozentsatz (z.B. 100%) setzen, um Responsivität zu gewährleisten. Wenn Sie aus Designgründen eine feste Breite benötigen, geben Sie einen Pixelwert an.
- **Händlerszenario / Beispiel:** Wenn Ihr Theme einen sehr schmalen Header hat, müssen Sie dies möglicherweise anpassen, um sicherzustellen, dass die Suchleiste passt, ohne das Layout zu zerstören. Für die meisten modernen Themes ist es am besten, das Theme die Breite handhaben zu lassen.

#### 2.1.4 Weitere Einstellungen

**9. MyPresta.eu Live Update Einstellungen (`mypresta_updates`, `update_`, `updatev_`)**

- **Was diese Einstellung bewirkt:** Dies sind interne Einstellungen, die mit dem Modul-Update-System von MyPresta.eu zusammenhängen. Sie ermöglichen es dem Modul, nach neuen Versionen zu suchen und Sie darüber zu informieren.
- **Auswirkung der Änderung dieser Einstellung:** Diese sind nicht direkt über die Benutzeroberfläche vom Benutzer konfigurierbar, sondern werden vom Modul selbst verwaltet. Die Sicherstellung, dass Ihr Shop über ausgehenden Internetzugang verfügt, ermöglicht die Funktion dieser Prüfungen.
- **Empfohlener Wert:** Diese sind intern und sollten nicht manuell geändert werden.
- **Händlerszenario / Beispiel:** Sie erhalten eine Benachrichtigung in Ihrem PrestaShop Back Office, wenn eine neue Version von Block Search Pro verfügbar ist, wodurch Sie Ihr Modul mit den neuesten Funktionen und Sicherheitskorrekturen auf dem neuesten Stand halten können.

**10. `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`**

- **Was diese Einstellung bewirkt:** Dies sind Standard-PrestaShop-Konfigurationsvariablen, die sich auf die Standardsprache Ihres Shops beziehen und darauf, ob Mitarbeiter die Sprache von Formularen im Back Office ändern können. Das Modul verwendet diese, um sicherzustellen, dass es in der aktiven Back Office-Sprache korrekt angezeigt wird.
- **Auswirkung der Änderung dieser Einstellung:** Dies sind globale PrestaShop-Einstellungen und werden nicht direkt von Block Search Pro gesteuert. Das Modul liest sie lediglich, um seine Anzeige anzupassen.
- **Empfohlener Wert:** Wird durch Ihre allgemeine PrestaShop-Konfiguration verwaltet.
- **Händlerszenario / Beispiel:** Wenn Ihr Back Office auf Französisch eingestellt ist, erscheinen die Konfigurationsbeschriftungen des Moduls auf Französisch (sofern Übersetzungen verfügbar sind).

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | AJAX-Suche aktivieren | JA | Zeigt sofortige Produktvorschläge während der Kundeneingabe an. |
| Modulkonfiguration | Sofortsuche | JA | Aktualisiert die Suchergebnisseite sofort bei Abfrageänderung. |
| Modulkonfiguration | Leere Suchanfrage zulassen | NEIN | Verhindert die Suche mit einem leeren Eingabefeld. |
| Modulkonfiguration | Mindestwortlänge (in Zeichen) | 3 | Mindestanzahl von Zeichen, die zum Auslösen der Suche erforderlich sind. |
| Modulkonfiguration | Kategorien auswählen | Leer lassen (durchsucht alle) | Beschränkt die Suche auf ausgewählte Kategorien. |
| Modulkonfiguration | In Unterkategorien suchen | JA | Schließt Unterkategorien ein, wenn Oberkategorien ausgewählt sind. |
| Modulkonfiguration | Hersteller | Leer lassen (durchsucht alle) | Beschränkt die Suche auf ausgewählte Hersteller. |
| Modulkonfiguration | Größe des Suchblocks | Leer lassen (automatische Erkennung) | Visuelle Breite des Sucheingabefeldes. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Suchergebnisse zeigen keine Produkte an, von denen ich weiß, dass sie existieren. Was ist falsch?**
A1: Überprüfen Sie Ihre Einstellungen für „Kategorien auswählen“ und „Hersteller“ in der Modulkonfiguration. Wenn Sie die Suche auf bestimmte Kategorien oder Hersteller beschränkt haben, werden Produkte außerhalb dieser Auswahl nicht angezeigt. Stellen Sie außerdem sicher, dass Ihre Produkte aktiv und in den ausgewählten Kategorien sichtbar sind.

**F2: Die Sofortsuche (AJAX) funktioniert nicht, oder die Dropdown-Vorschläge erscheinen nicht.**
A2:
\* **AJAX-Suche aktivieren:** Stellen Sie sicher, dass „AJAX-Suche aktivieren“ in der Modulkonfiguration auf JA gesetzt ist.
\* **Mindestwortlänge:** Überprüfen Sie die „Mindestwortlänge“. Wenn sie zu hoch eingestellt ist, erscheinen Vorschläge erst, wenn genügend Zeichen eingegeben wurden.
\* **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und leeren Sie Ihren PrestaShop-Cache (Smarty-Cache, Dateisystem-Cache).
\* **Theme-Konflikte:** Manchmal können benutzerdefinierte Themes oder andere Module mit der AJAX-Funktionalität in Konflikt geraten. Deaktivieren Sie vorübergehend andere Module oder wechseln Sie zum Standard-PrestaShop-Theme, um dies zu diagnostizieren.
\* **JavaScript-Fehler:** Öffnen Sie die Entwicklerkonsole Ihres Browsers (F12) und suchen Sie nach JavaScript-Fehlern. Wenn Sie Fehler sehen, wenden Sie sich an den MyPresta.eu-Support.

**F3: Der Suchblock sieht seltsam aus oder passt nicht zu meinem Theme.**
A3:
\* **Größe des Suchblocks:** Passen Sie die Einstellung „Größe des Suchblocks“ in der Modulkonfiguration an. Versuchen Sie, sie für die automatische Erkennung leer zu lassen oder auf einen Prozentsatz (z.B. 100%) einzustellen.
\* **CSS-Konflikte:** Das CSS Ihres Themes könnte die Stile des Moduls überschreiben. Dies erfordert normalerweise, dass ein Webmaster das CSS überprüft.
\* **Hook-Platzierung:** Stellen Sie sicher, dass das Modul an einer geeigneten Position (z.B. `displayTop`) eingehängt ist, die in Ihrem Theme genügend Platz bietet. Sie können die Modulpositionen unter **Design > Positionen** verwalten.

**F4: Wie übersetze ich den Text des Suchblocks (z.B. „Unseren Katalog durchsuchen“)?**
A4:
\* Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
\* Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann Ihre Sprache.
\* Suchen Sie das Modul „Block Search Pro“ in der Liste und Sie können die Textzeichenfolgen dort bearbeiten.

**F5: Ich möchte den Suchblock an einer anderen Stelle auf meiner Website platzieren.**
A5:
\* Navigieren Sie zu **Design > Positionen** (oder **Module > Positionen** in älteren PS-Versionen).
\* Suchen Sie das Modul „Block Search Pro“ in der Liste der Module.
\* Sie können das Modul an verschiedene verfügbare Hooks „transplantieren“ (einhängen), z.B. `displayHeader`, `displayTop`, `displayLeftColumn`, `displayRightColumn` oder `displayNav`. Ziehen Sie es per Drag & Drop, um die Reihenfolge innerhalb eines Hooks zu ändern.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul Block Search Pro für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul Block Search Pro erweitert die Kernsuchfunktionalität von PrestaShop, indem es die Klasse `Search` überschreibt, wodurch es benutzerdefinierte Filterlogik (Kategorien, Hersteller) in die Suchabfrage injizieren kann. Es nutzt Standard-PrestaShop-MVC-Muster für seine Front-Office-Anzeige (Hooks, Templates) und Back-Office-Konfiguration (`getContent()`-Methode in der Hauptmoduldatei). Die AJAX-Funktionalität wird über eine dedizierte JavaScript-Datei abgewickelt, die mit dem PrestaShop-Kernsuchmechanismus interagiert.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller ein. Seine Front-Office-Funktionalität wird hauptsächlich durch die überschriebene `Search`-Klasse und deren Anzeige über Modul-Hooks abgewickelt. Die Back-Office-Konfiguration wird direkt in der `getContent()`-Methode der Moduldatei `blocksearchpro.php` verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

- **`blocksearchpro/override/classes/index.php`**:

  - Dies ist eine standardmäßige leere `index.php`-Datei, die typischerweise in Verzeichnissen platziert wird, um die Verzeichnisauflistung zu verhindern. Sie hat keine funktionale Auswirkung auf die Modullogik.
- **`blocksearchpro/override/classes/Search.php`**:

  - **Klassenname**: `Search` (überschreibt die Kernklasse `Search`)
  - **Elternklasse**: `SearchCore`
  - **Verantwortlichkeit**: Dies ist die wichtigste Datei. Sie überschreibt die Standard-PrestaShop-Klasse `Search` und modifiziert insbesondere die Methode `find()` (oder ähnliche suchbezogene Methoden), um die benutzerdefinierte Filterlogik des Moduls zu integrieren.
    - Sie liest Konfigurationswerte (`bsp_cat_exc`, `bsp_subcat`, `bsp_cat`, `bsp_man`) aus `ps_configuration`.
    - Sie modifiziert die für die Produktsuche verwendete SQL-Abfrage, um `WHERE`-Klauseln einzuschließen, die nach ausgewählten Kategorien und/oder Herstellern filtern.
    - Sie stellt sicher, dass die Suche die Einstellung „In Unterkategorien suchen“ berücksichtigt, wenn Kategoriefilter angewendet werden.
    - Diese Überschreibung ermöglicht es dem Modul, seine Filterfunktionen direkt in den PrestaShop-Kernsuchmechanismus zu injizieren.

### 4.4 JavaScript-Assets (`views/js/`)

- **`blocksearchpro/blocksearchpro.js`**:
  - **Geltungsbereich**: Front-Office.
  - **Verantwortlichkeit**: Dieses Skript verbessert die Benutzererfahrung für den Suchblock.
    - Es bindet wahrscheinlich Event-Listener an das Sucheingabefeld (z.B. `keyup`, `focus`, `blur`).
    - Es verarbeitet die AJAX-Anfragen für sofortige Suchvorschläge und sendet den aktuellen Eingabewert an den PrestaShop-Kern-Such-AJAX-Endpunkt.
    - Es verarbeitet die JSON-Antwort des AJAX-Aufrufs und füllt dynamisch die Dropdown-Liste der Produktvorschläge unterhalb der Suchleiste.
    - Es verwaltet die Anzeige und das Ausblenden der Vorschlagsliste, die Tastaturnavigation innerhalb der Vorschläge und Klickereignisse auf Vorschläge zur Weiterleitung zu Produktseiten.
    - Es kann auch die Logik „Leere Suchanfrage zulassen“ auf der Client-Seite verarbeiten.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`blocksearchpro/blocksearchpro.css`**:
  - **Geltungsbereich**: Front-Office-Kundenstyling.
  - **Wichtige UI-Komponenten und Container, die es stylt**:
    - Das Sucheingabefeld selbst (`#search_query_top`, `.search_query`).
    - Die Suchschaltfläche (`#search_button`, `.button-search`).
    - Der Container für AJAX-Suchvorschläge (`.ac_results`, `.block_search_pro_results`).
    - Einzelne Vorschlagselemente innerhalb des Dropdowns.
    - Gewährleistet Responsivität für verschiedene Bildschirmgrößen.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können**:
    - `.block_search_pro` (Hauptcontainer)
    - `.search_query` (Eingabefeld)
    - `.button-search` (Senden-Schaltfläche)
    - `.ac_results` (AJAX-Ergebniscontainer)
    - `.ac_odd`, `.ac_even`, `.ac_over` (Styling für Vorschlagselemente und Hover-Zustände)
    - Entwickler können diese Stile in der `custom.css` ihres Themes oder durch Erstellen eines Child-Themes überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - **`blocksearchpro/blocksearchpro-top.tpl`**:
    - **Hook**: `displayTop`, `displayNav` (und potenziell `displayHeader` je nach Theme).
    - **Zweck**: Rendert das Sucheingabefeld und die Schaltfläche, typischerweise für die Haupt-Header-Suchleiste. Es enthält die notwendige HTML-Struktur für das Suchformular und den Container für AJAX-Ergebnisse.
  - **`blocksearchpro/blocksearchpro.tpl`**:
    - **Hook**: `displayLeftColumn`, `displayRightColumn`.
    - **Zweck**: Rendert einen Suchblock für Seitenleisten. Dieses Template könnte ein etwas anderes Layout oder Styling im Vergleich zur oberen Suchleiste haben, optimiert für engere Spaltenbereiche. Es enthält auch das Suchformular und den AJAX-Ergebniscontainer.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der Standard-PrestaShop-Tabelle `ps_configuration`.
  - Verwendete Konfigurationsschlüssel: `mypresta_updates`, `update_`, `updatev_`, `PS_SEARCH_AJAX`, `bsp_cat_exc`, `PS_INSTANT_SEARCH`, `bsp_empty`, `PS_SEARCH_MINWORDLEN`, `bsp_subcat`, `bsp_cat`, `bsp_man`, `bsp_size`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Fügt CSS (`blocksearchpro.css`) und JavaScript (`blocksearchpro.js`) Assets für die Front-Office-Funktionalität ein. |
| `displayTop` | Typischerweise im Haupt-Header-Bereich des Shops. | Rendert den Suchblock mit `blocksearchpro-top.tpl`. |
| `displayNav` | Oft in der obersten Navigationsleiste (über `displayTop`). | Rendert den Suchblock mit `blocksearchpro-top.tpl`. |
| `displayLeftColumn` | In der linken Seitenleiste von Seiten, die eine haben. | Rendert den Suchblock mit `blocksearchpro.tpl`. |
| `displayRightColumn` | In der rechten Seitenleiste von Seiten, die eine haben. | Rendert den Suchblock mit `blocksearchpro.tpl`. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | (Wird von diesem Modul nicht direkt für seine Kernsuchfunktionalität verwendet, aber ein häufiger Hook für andere Module. Keine spezifische Aktion hier für Block Search Pro.) |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und weitere Unterstützung zum Modul Block Search Pro besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.

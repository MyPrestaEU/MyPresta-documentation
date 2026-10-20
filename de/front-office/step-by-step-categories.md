---
title: "Schritt für Schritt - Kategorien - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, Bildschirm-für-Bildschirm-Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Schritt für Schritt - Kategorien“ von MyPresta.eu."
sidebar:
  label: "Schritt für Schritt - Kategorien - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Step by step - categories auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/step-by-step-categories/)
>
> ---


# Schritt für Schritt - Kategorien

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Keine speziellen Serveranforderungen über eine Standard-PrestaShop-Hosting-Umgebung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ zum Hauptkonfigurationsbildschirm für „Schritt für Schritt - Kategorien“. Hier steuern Sie, wie sich das Modul verhält und in Ihrem Shop angezeigt wird.

| Einstellung / Option | Was diese Einstellung bewirkt | Auswirkung der Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **Block im Header anzeigen** | Steuert, ob die Schritt-für-Schritt-Kategorienavigation im Header-Bereich Ihres Shops angezeigt wird. | *Wenn aktiviert:* Die Kategorie-Dropdowns sind oben auf Ihrer Website sichtbar, oft in der Nähe des Logos oder der Hauptnavigation. Dies bietet sofortigen Zugriff auf die Kategoriefilterung. *Wenn deaktiviert:* Der Block wird nicht im Header angezeigt. | **JA** (wenn Sie eine prominente Navigation wünschen) | Sie möchten, dass Kunden Produkte von jeder Seite aus leicht finden können, daher macht die Platzierung im Header sie immer zugänglich. |
| **Block in linker Spalte anzeigen** | Steuert, ob die Schritt-für-Schritt-Kategorienavigation in der linken Seitenleiste Ihres Shops angezeigt wird. | *Wenn aktiviert:* Die Kategorie-Dropdowns sind in der linken Spalte Ihrer Website sichtbar (sofern Ihr Theme eine linke Spalte unterstützt). Dies ist eine traditionelle Platzierung für Kategoriefilter. *Wenn deaktiviert:* Der Block wird nicht in der linken Spalte angezeigt. | **JA** (wenn Ihr Theme eine linke Spalte hat und Sie eine Seitenleisten-Navigation wünschen) | Ihr Theme hat eine linke Seitenleiste, und Sie bevorzugen es, Navigationselemente dort zu organisieren, ähnlich einem Standard-Kategoriebaum. |
| **Block in rechter Spalte anzeigen** | Steuert, ob die Schritt-für-Schritt-Kategorienavigation in der rechten Seitenleiste Ihres Shops angezeigt wird. | *Wenn aktiviert:* Die Kategorie-Dropdowns sind in der rechten Spalte Ihrer Website sichtbar (sofern Ihr Theme eine rechte Spalte unterstützt). *Wenn deaktiviert:* Der Block wird nicht in der rechten Spalte angezeigt. | **NEIN** (es sei denn, Ihr Theme verwendet speziell eine rechte Spalte für die Navigation) | Ihr Theme verwendet die rechte Spalte für ergänzende Informationen, und Sie möchten die Kategorienavigation dort anstelle der linken platzieren. |
| **Block im Footer anzeigen** | Steuert, ob die Schritt-für-Schritt-Kategorienavigation im Footer-Bereich Ihres Shops angezeigt wird. | *Wenn aktiviert:* Die Kategorie-Dropdowns sind am unteren Rand Ihrer Website sichtbar. Dies ist weniger üblich für die primäre Navigation, kann aber für den sekundären Zugriff nützlich sein. *Wenn deaktiviert:* Der Block wird nicht im Footer angezeigt. | **NEIN** (es sei denn, aus spezifischen Designgründen) | Sie haben einen sehr minimalistischen Header und Spalten, und Sie möchten die Kategorienavigation im Footer als Alternative für Benutzer anbieten, die nach unten scrollen. |
| **Block auf Produktseite anzeigen** | Steuert, ob die Schritt-für-Schritt-Kategorienavigation auf einzelnen Produktseiten angezeigt wird. | *Wenn aktiviert:* Die Kategorie-Dropdowns sind auf Produktdetailseiten sichtbar. Dies kann Kunden helfen, andere Kategorien oder verwandte Produkte zu erkunden. *Wenn deaktiviert:* Der Block wird nicht auf Produktseiten angezeigt. | **NEIN** (es sei denn, Sie haben einen spezifischen Bedarf dafür) | Sie möchten Kunden, die ein Produkt ansehen, ermutigen, einfach zu anderen Kategorien zu springen, ohne die Produktseite zu verlassen, vielleicht um Artikel zu vergleichen. |
| **„Go“-Button anzeigen** | Bestimmt, ob ein „Go“- oder „Suchen“-Button neben dem letzten Kategorie-Dropdown angezeigt wird. | *Wenn aktiviert:* Ein Button wird angezeigt. Kunden müssen diesen Button klicken, um zur ausgewählten Kategorieseite weitergeleitet zu werden. *Wenn deaktiviert:* Kunden werden automatisch zur ausgewählten Kategorieseite weitergeleitet, sobald sie die endgültige Auswahl im letzten Dropdown treffen. | **JA** (für mehr Kontrolle) | Sie möchten, dass Kunden ihre Kategorieauswahl bestätigen, bevor sie weitergeleitet werden, um ihnen die Möglichkeit zu geben, ihre Wahl zu überprüfen. |
| **Anzahl der Dropdowns** | Legt die maximale Anzahl der Kategorieebenen (Tiefe) fest, die als Dropdowns angezeigt werden. | *Wenn auf 1 gesetzt:* Nur die Top-Level-Kategorien werden in einem Dropdown angezeigt. *Wenn auf 3 gesetzt:* Bis zu drei Kategorieebenen (z.B. Hauptkategorie > Unterkategorie 1 > Unterkategorie 2) werden in separaten Dropdowns angezeigt. | **3** (oder basierend auf Ihrer Kategorietiefe) | Ihr Shop hat Kategorien, die bis zu 3 oder 4 Ebenen tief verschachtelt sind, und Sie möchten, dass Kunden effizient tiefer gehen können. |
| **Stammkategorie** | Gibt den Startpunkt für die Kategorienavigation an. Nur Kategorien innerhalb dieser Stammkategorie werden angezeigt. | *Wenn auf „Home“ gesetzt:* Alle Kategorien, beginnend ganz oben in Ihrem Katalog, sind verfügbar. *Wenn auf „Elektronik“ gesetzt:* Nur Kategorien unter „Elektronik“ (z.B. „Laptops“, „Smartphones“) werden in den Dropdowns angezeigt. | **Home** (es sei denn, Sie möchten die Navigation einschränken) | Sie möchten nur eine Schritt-für-Schritt-Navigation für einen bestimmten Teil Ihres Katalogs anbieten, wie z.B. „Bekleidung“, und andere Bereiche wie „Haus & Garten“ ausschließen. |

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Block im Header anzeigen | JA | Zeigt Kategorie-Dropdowns im Shop-Header für prominente Navigation an. |
| Modulkonfiguration | Block in linker Spalte anzeigen | JA | Zeigt Kategorie-Dropdowns in der linken Seitenleiste für traditionelle Navigation an. |
| Modulkonfiguration | Block in rechter Spalte anzeigen | NEIN | Zeigt Kategorie-Dropdowns in der rechten Seitenleiste an. |
| Modulkonfiguration | Block im Footer anzeigen | NEIN | Zeigt Kategorie-Dropdowns im Shop-Footer an. |
| Modulkonfiguration | Block auf Produktseite anzeigen | NEIN | Zeigt Kategorie-Dropdowns auf Produktdetailseiten an. |
| Modulkonfiguration | „Go“-Button anzeigen | JA | Erfordert, dass Kunden einen Button klicken, um zur ausgewählten Kategorie zu navigieren. |
| Modulkonfiguration | Anzahl der Dropdowns | 3 | Legt die maximale Tiefe der angezeigten Kategorieebenen fest. |
| Modulkonfiguration | Stammkategorie | Home | Definiert den Startpunkt für die Kategorienavigation. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Das Modul ist installiert, aber ich sehe die Dropdowns nicht in meinem Shop.**
A1:

- **Konfiguration prüfen:** Gehen Sie zu **Module > Modul-Manager > Schritt für Schritt - Kategorien > Konfigurieren**. Stellen Sie sicher, dass mindestens eine Option „Block anzeigen in…“ (z.B. „Block im Header anzeigen“, „Block in linker Spalte anzeigen“) auf **JA** gesetzt ist.
- **Cache leeren:** PrestaShop speichert Inhalte oft im Cache. Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
- **Theme-Kompatibilität:** Einige stark angepasste Themes erfordern möglicherweise geringfügige Anpassungen. Wenn das Leeren des Caches nicht hilft, versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme zu wechseln, um zu sehen, ob das Modul erscheint. Wenn ja, überschreibt Ihr Theme möglicherweise die Standard-Hook-Positionen.

**F2: Die Dropdowns erscheinen, aber sie aktualisieren sich nicht, wenn ich eine Kategorie auswähle.**
A2:

- **AJAX-Probleme:** Dies deutet normalerweise auf einen JavaScript-Fehler hin. Öffnen Sie die Entwicklerkonsole Ihres Browsers (F12) und suchen Sie im Tab „Konsole“ nach Fehlern.
- **Konfliktierendes JavaScript:** Ein anderes Modul oder das JavaScript Ihres Themes könnte stören. Versuchen Sie, andere Front-Office-Module nacheinander zu deaktivieren, um Konflikte zu identifizieren.
- **Moduldateien:** Stellen Sie sicher, dass alle Moduldateien korrekt hochgeladen wurden und nicht beschädigt sind. Ein erneutes Hochladen des Moduls könnte dies beheben.

**F3: Wie ändere ich das Styling (Farben, Schriftarten, Größe) der Dropdowns?**
A3:

- Das Modul verwendet Standard-CSS. Sie benötigen grundlegende CSS-Kenntnisse oder einen Webmaster.
- Die CSS-Dateien des Moduls (z.B. `sbs-block.css`, `sbs-header.css`) definieren die Standardstile.
- **Best Practice:** Ändern Sie die CSS-Dateien des Moduls NICHT direkt, da Ihre Änderungen bei Updates verloren gehen. Verwenden Sie stattdessen die benutzerdefinierte CSS-Datei Ihres Themes (oft in `themes/yourtheme/assets/css/custom.css` oder ähnlich zu finden), um die Stile des Moduls zu überschreiben. Verwenden Sie den Browser-Inspektor (F12), um die von den Dropdowns verwendeten CSS-Klassen zu identifizieren.

**F4: Meine Kategorien sind sehr tief, aber ich sehe nur wenige Dropdowns.**
A4:

- **Einstellung „Anzahl der Dropdowns“:** Gehen Sie zu **Module > Modul-Manager > Schritt für Schritt - Kategorien > Konfigurieren** und passen Sie die Einstellung „Anzahl der Dropdowns“ an. Erhöhen Sie diesen Wert, um die maximale Tiefe der Kategorien anzupassen, die Sie anzeigen möchten. Denken Sie daran, dass das Anzeigen von zu vielen Dropdowns die Benutzeroberfläche überladen könnte.

**F5: Das Modul zeigt Kategorien an, die ich nicht in die Schritt-für-Schritt-Navigation aufnehmen möchte.**
A5:

- **Einstellung „Stammkategorie“:** Verwenden Sie in der Modulkonfiguration die Einstellung „Stammkategorie“. Wählen Sie eine bestimmte übergeordnete Kategorie aus, von der aus die Schritt-für-Schritt-Navigation beginnen soll. Nur Kategorien und Unterkategorien unter Ihrer gewählten Stammkategorie werden angezeigt.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Schritt für Schritt - Kategorien“ ist primär eine Front-Office-Funktion, die die PrestaShop-Modularchitektur nutzt. Es verwendet eine Standard-`Module`-Klasse für Installation und Konfiguration und `ModuleFrontController`-Klassen zur Handhabung von AJAX-Anfragen für dynamisches Laden von Kategorien. Es führt keine benutzerdefinierten `ObjectModel`-Klassen oder Datenbanktabellen ein, sondern verlässt sich auf PrestaShops natives `Category`-Objekt für Daten. Das Modul nutzt Smarty-Templates für die Darstellung und JavaScript für interaktive AJAX-Funktionalität.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:
  - `controllers/front/ajaxload.php`
    - Klassenname: `StepbystepAjaxloadModuleFrontController`
    - Übergeordnete Klasse: `ModuleFrontController`
    - Verantwortung: Dieser Controller ist der Kern der AJAX-Funktionalität. Er reagiert auf Anfragen vom Front-Office-JavaScript, um Unterkategorien basierend auf einer übergeordneten Kategorie-ID abzurufen. Er gibt typischerweise JSON-Daten zurück, die Kategorienamen und IDs zum Füllen nachfolgender Dropdowns enthalten.
  - `controllers/front/index.php`
    - Klassenname: `StepbystepIndexModuleFrontController`
    - Übergeordnete Klasse: `ModuleFrontController`
    - Verantwortung: Dieser Controller dient wahrscheinlich als Standard-Einstiegspunkt oder Fallback für das Front-Office-Routing des Moduls, obwohl seine primäre Funktion angesichts der AJAX-gesteuerten Natur minimal sein könnte. Er könnte die anfängliche Anzeigelogik oder Weiterleitung handhaben, falls das Modul eine dedizierte Seite hätte.
  - `controllers/front/tree.php`
    - Klassenname: `StepbystepTreeModuleFrontController`
    - Übergeordnete Klasse: `ModuleFrontController`
    - Verantwortung: Dieser Controller könnte für das Rendern einer vollständigen Kategoriebaumstruktur verantwortlich sein, möglicherweise zum Debuggen oder als alternative Anzeigemethode, obwohl die Hauptfunktion des Moduls die Dropdowns sind. Er könnte auch verwendet werden, um die anfänglichen Daten für das erste Dropdown zu generieren.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul enthält keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Es verwendet direkt die Kernklasse `Category` von PrestaShop und andere Hilfsfunktionen, um Kategoriedaten abzurufen.

### 4.4 JavaScript-Assets (`views/js/`)

- `stepbystep/js/advajax.js`
  - Geltungsbereich: Front-Office
  - Dies ist die primäre JavaScript-Datei, die für das interaktive Verhalten des Moduls verantwortlich ist.
  - Sie bindet Event-Listener an die `<select>`-Elemente der Kategorie-Dropdowns.
  - Wenn eine Auswahl in einem Dropdown getroffen wird, löst sie eine AJAX-Anfrage (wahrscheinlich an `ajaxload.php`) aus, um die nächste Ebene von Unterkategorien abzurufen.
  - Sie erstellt und füllt dynamisch nachfolgende Dropdowns mit den empfangenen Daten.
  - Sie handhabt die Weiterleitung zur finalen Kategorieseite, wenn eine Auswahl getroffen oder der „Go“-Button geklickt wird.
  - Sie verwaltet die Sichtbarkeit und den Zustand der Dropdowns basierend auf Benutzerinteraktion und Modulkonfiguration (z.B. „Anzahl der Dropdowns“).

### 4.5 CSS-Stylesheets (`views/css/`)

- `stepbystep/css/sbs-block.css`
  - Geltungsbereich: Front-Office Kunden-Styling
  - Gestaltet das allgemeine Erscheinungsbild des Schritt-für-Schritt-Kategorieblocks, einschließlich Polsterung, Rändern und des Gesamtlayouts, wenn er in Spalten oder anderen blockartigen Positionen platziert wird.
  - Schlüssel-Selektoren: `.sbs-block`, `.sbs-category-select-wrapper`
- `stepbystep/css/sbs-header.css`
  - Geltungsbereich: Front-Office Kunden-Styling
  - Gestaltet das Modul speziell, wenn es in die `displayHeader`-Position eingehängt ist, möglicherweise angepasst an Header-Layouts (z.B. Inline-Anzeige, spezifische Breiten).
  - Schlüssel-Selektoren: `.sbs-header-container`
- `stepbystep/css/sbs-top.css`
  - Geltungsbereich: Front-Office Kunden-Styling
  - Gestaltet das Modul wahrscheinlich, wenn es in `displayTop` oder ähnliche Positionen am Seitenanfang eingehängt ist, ähnlich wie `sbs-header.css`, aber für andere visuelle Kontexte.
  - Schlüssel-Selektoren: `.sbs-top-container`
- `stepbystep/css.css`
  - Geltungsbereich: Front-Office Kunden-Styling
  - Ein allgemeines Stylesheet, das gemeinsame Stile enthalten könnte, die für alle Platzierungen anwendbar sind, oder Fallback-Stile.
  - Schlüssel-Selektoren: `.sbs-select`, `.sbs-go-button`

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `block.tpl`: Dieses Template wird wahrscheinlich verwendet, wenn das Modul in `displayLeftColumn` oder `displayRightColumn` eingehängt ist. Es rendert die Schritt-für-Schritt-Dropdowns innerhalb einer Standard-PrestaShop-Blockstruktur.
  - `blockSbs.tpl`: Dies könnte ein alternatives oder ein generischeres Block-Template sein, das möglicherweise für andere Spalten-Hooks oder spezifische benutzerdefinierte Platzierungen verwendet wird.
  - `displaySearch.tpl`: Dieses Template könnte für die Integration in der Nähe einer Suchleiste oder als Teil eines suchbezogenen Hooks gedacht sein, um die Dropdowns als Suchverfeinerungswerkzeug bereitzustellen.
  - `header.tpl`: Dieses Template wird verwendet, wenn das Modul in `displayHeader` eingehängt ist. Es rendert die Dropdowns innerhalb des Header-Bereichs des Shops.
  - `top.tpl`: Dieses Template wird verwendet, wenn das Modul in `displayTop` eingehängt ist. Ähnlich wie `header.tpl`, aber für den `displayTop`-Hook, der oft für die Hauptnavigationsleiste verwendet wird.
- **Admin-Templates (`views/templates/admin/`)**: Keine identifiziert. Die Konfiguration wird direkt in `getContent()` behandelt.
- **Front-Office-Templates (`views/templates/front/`)**: Keine als eigenständige Seiten identifiziert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Es speichert seine Konfigurationseinstellungen in der PrestaShop-Tabelle `ps_configuration` unter Schlüsseln wie `STEPMYSTEP_HEADER`, `STEPMYSTEP_LEFT`, `STEPMYSTEP_RIGHT`, `STEPMYSTEP_FOOTER`, `STEPMYSTEP_PRODUCT`, `STEPMYSTEP_GO_BUTTON`, `STEPMYSTEP_DROPDOWNS`, `STEPMYSTEP_ROOT_CATEGORY`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert Inhalte innerhalb des `<head>`-Abschnitts des HTML oder ganz oben im `<body>` vor anderen Inhalten. | Fügt CSS/JS-Assets und möglicherweise die HTML-Struktur des Moduls ein, wenn für die Header-Anzeige konfiguriert. |
| `displayLeftColumn` | Rendert Inhalte in der linken Seitenleiste des Shops. | Zeigt die Schritt-für-Schritt-Kategorie-Dropdowns in der linken Spalte an. |
| `displayRightColumn` | Rendert Inhalte in der rechten Seitenleiste des Shops. | Zeigt die Schritt-für-Schritt-Kategorie-Dropdowns in der rechten Spalte an. |
| `displayFooter` | Rendert Inhalte im Footer-Bereich des Shops. | Zeigt die Schritt-für-Schritt-Kategorie-Dropdowns im Footer an. |
| `displayProductAdditionalInfo` (oder ähnlicher Produktseiten-Hook) | Rendert Inhalte auf der Produktseite, oft unter der Produktbeschreibung oder in einem spezifischen Block. | Zeigt die Schritt-für-Schritt-Kategorie-Dropdowns auf Produktseiten an. |
| `displayTop` | Rendert Inhalte im oberen Bereich der Seite, typischerweise über oder innerhalb der Hauptnavigation. | Zeigt die Schritt-für-Schritt-Kategorie-Dropdowns in der oberen Leiste an. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Schritt für Schritt - Kategorien“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.

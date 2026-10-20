---
title: "Homepage-Tab beliebte Produkte – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Homepage-Tab beliebte Produkte“ von MyPresta.eu."
sidebar:
  label: "Homepage-Tab beliebte Produkte – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Homepage tab popular products auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/homepage-tab-popular-products.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/homepage-tab-popular-products/)
>
> ---


# Homepage-Tab beliebte Produkte

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend. Es sind in der Regel keine speziellen Serverkonfigurationen über eine Standard-PrestaShop-Hosting-Umgebung hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager auf die Schaltfläche „Konfigurieren“ neben dem Modul „Homepage-Tab beliebte Produkte“. Dies führt Sie zum Hauptkonfigurationsbildschirm.

#### Allgemeine Einstellungen

- **Was diese Einstellung bewirkt:** Dieses Modul konzentriert sich hauptsächlich auf die Anzeige beliebter Produkte. Der Konfigurationsbildschirm für dieses Modul ist recht einfach und enthält oft Standardeinstellungen für MyPresta.eu-Update-Benachrichtigungen. Die Kernfunktionalität der Anzeige von „beliebten Produkten“ wird normalerweise automatisch durch die interne Logik von PrestaShop zur Identifizierung beliebter Artikel (z. B. basierend auf Verkäufen, Ansichten oder einer Kombination) gehandhabt.
- **Auswirkungen der Änderung dieser Einstellung:**
  - **`mypresta_updates` (MyPresta.eu Update-Benachrichtigungen aktivieren/deaktivieren):**
    - *Wenn aktiviert:* Sie erhalten Benachrichtigungen in Ihrem PrestaShop Back Office, wenn neue Versionen oder wichtige Updates für MyPresta.eu-Module (einschließlich dieses) verfügbar sind. Dies hilft Ihnen, Ihre Module sicher und auf dem neuesten Stand mit den neuesten Funktionen und Fehlerbehebungen zu halten.
    - *Wenn deaktiviert:* Sie erhalten diese Benachrichtigungen nicht. Sie müssten Ihr MyPresta.eu-Konto manuell auf Updates überprüfen.
  - **`update_` und `updatev_` (Interne Update-Prüfparameter):** Dies sind typischerweise interne Einstellungen, die von MyPresta.eu-Modulen zur Verwaltung und Verfolgung von Update-Prüfungen verwendet werden. Sie sind normalerweise nicht für die direkte Interaktion des Händlers vorgesehen.
- **Empfohlener Wert:**
  - Für `mypresta_updates`: **JA** (Aktiviert). Wenn diese Option aktiviert bleibt, werden Sie immer über kritische Updates informiert, was die Sicherheit und Leistung Ihres Shops verbessert.
  - Für `update_` und `updatev_`: Als Standard belassen. Diese sind intern und sollten nicht geändert werden.
- **Händlerszenario / Beispiel:**
  - Sie möchten sicherstellen, dass Ihr Shop immer die neuesten, sichersten Versionen Ihrer MyPresta.eu-Module verwendet. Durch die Aktivierung von Update-Benachrichtigungen sehen Sie eine deutliche Warnung in Ihrem PrestaShop-Admin-Panel, sobald ein Update für „Homepage-Tab beliebte Produkte“ (oder ein anderes MyPresta.eu-Modul) veröffentlicht wird. Dies ermöglicht es Ihnen, die neue Version umgehend herunterzuladen und zu installieren und von Verbesserungen zu profitieren, ohne ständig manuell nachsehen zu müssen.

#### Wichtiger Hinweis zur Logik „Beliebte Produkte“:

Dieses Modul nutzt die bestehenden Mechanismen von PrestaShop, um zu bestimmen, was ein „beliebtes Produkt“ ausmacht. Typischerweise identifiziert PrestaShop beliebte Produkte basierend auf Verkaufsdaten (Produkte mit den meisten Bestellungen) oder Ansichten. Das Modul selbst bietet normalerweise keine spezifischen Einstellungen zur Definition von „Popularität“ (z. B. „Produkte anzeigen, die in den letzten 30 Tagen verkauft wurden“ oder „Produkte mit X Ansichten“). Es verlässt sich hierfür auf die Kernfunktionalität von PrestaShop. Wenn Sie beeinflussen möchten, welche Produkte als „beliebt“ erscheinen, müssten Sie im Allgemeinen deren Verkäufe oder Sichtbarkeit durch andere Marketingmaßnahmen erhöhen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | MyPresta.eu Update-Benachrichtigungen | Aktiviert (JA) | Erhalten Sie Benachrichtigungen für Modul-Updates, um Sicherheit und neue Funktionen zu gewährleisten. |
| Modulkonfigurationsseite | `update_` | Standard | Interne Einstellung zur Update-Verfolgung. Unverändert lassen. |
| Modulkonfigurationsseite | `updatev_` | Standard | Interne Einstellung zur Update-Verfolgung. Unverändert lassen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der „Beliebte Produkte“-Tab wird nicht auf meiner Startseite angezeigt.**
A1:

- **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass „Homepage-Tab beliebte Produkte“ installiert und aktiviert ist.
- **Cache leeren:** Manchmal verhindert der PrestaShop-Cache, dass neue Inhalte angezeigt werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“, falls verfügbar).
- **Theme-Kompatibilität:** Obwohl das Modul für PrestaShop 1.7.x, 8.x und 9.x entwickelt wurde, erfordern einige stark angepasste Themes möglicherweise geringfügige Anpassungen. Wenn das Leeren des Caches nicht funktioniert, wenden Sie sich an Ihren Theme-Entwickler oder den MyPresta.eu-Support.
- **Hook-Prüfung:** Stellen Sie sicher, dass der `displayHome`-Hook aktiv ist und von Ihrem Theme gerendert wird.

**F2: Die im „Beliebte Produkte“-Tab angezeigten Produkte erscheinen mir nicht „beliebt“.**
A2:

- **PrestaShops Definition:** Das Modul verlässt sich auf die interne Logik von PrestaShop zur Identifizierung beliebter Produkte, die typischerweise auf dem Verkaufsvolumen oder den Produktansichten basiert. Wenn Ihr Shop neu ist oder geringe Verkaufszahlen aufweist, ist die Liste der „beliebten“ Produkte möglicherweise nicht so dynamisch.
- **Datenaktualisierung:** Stellen Sie sicher, dass Ihr Shop über aktuelle Verkaufsdaten verfügt. Die „Popularität“ wird im Laufe der Zeit berechnet.
- **Cache:** Leeren Sie Ihren PrestaShop-Cache wie in F1 beschrieben.

**F3: Kann ich den Titel des Tabs ändern (z. B. von „Beliebte Produkte“ zu „Unsere Bestseller“)?**
A3:

- Dieses Modul verwendet typischerweise einen Standardtitel. Um ihn zu ändern, müssten Sie normalerweise die Übersetzungsdateien des Moduls bearbeiten oder in einigen Fällen direkt die Template-Datei ändern.
  - Gehen Sie zu **International > Übersetzungen**.
  - Wählen Sie „Übersetzungen installierter Module“, Ihr Theme und Ihre Sprache aus.
  - Suchen Sie das Modul „Homepage-Tab beliebte Produkte“ und suchen Sie nach der Zeichenfolge des Tab-Titels.
  - Wenn es auf diese Weise nicht übersetzbar ist, könnte eine kleine Codeänderung in `homepagetabs.tpl` erforderlich sein (siehe Abschnitt 7).

**F4: Das Styling der Produkte im Tab passt nicht zu meinem Theme.**
A4:

- Das Modul verwendet sein eigenes CSS (`homepagetabs.css`). Das CSS Ihres Themes könnte einige Stile überschreiben, oder die Stile des Moduls könnten in Konflikt stehen.
- **Benutzerdefiniertes CSS:** Der beste Ansatz ist, benutzerdefiniertes CSS in die `custom.css`-Datei Ihres Themes (oder eine entsprechende Datei) hinzuzufügen, um die Stile des Moduls zu überschreiben und es perfekt an Ihr Theme anzupassen. Verwenden Sie die Entwicklertools Ihres Browsers, um die Elemente zu untersuchen und die vom Modul verwendeten CSS-Selektoren zu identifizieren.

**F5: Wie übersetze ich den Tab-Titel oder andere Modultexte in verschiedene Sprachen?**
A5:

- Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“, dann Ihr Theme und die Sprache, in die Sie übersetzen möchten.
- Suchen Sie das Modul „Homepage-Tab beliebte Produkte“ in der Liste, und Sie sollten die damit verbundenen Textzeichenfolgen bearbeiten können.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „Homepage-Tab beliebte Produkte“, der für Entwickler, Webmaster und technische Agenturen bestimmt ist.

### 4.1 Architekturübersicht

Das Modul `Homepage-Tab beliebte Produkte` (`homepagetabs`) ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich dazu dient, den `displayHome`-Hook zu erweitern. Es folgt einem standardmäßigen PrestaShop MVC-ähnlichen Muster für Module, bei dem die Hauptmoduldatei (`homepagetabs.php`) die Installation, Deinstallation, Konfiguration und Hook-Registrierung handhabt. Das Modul fügt einen benutzerdefinierten Tab und dessen Inhalt in die Startseite ein und nutzt PrestaShops bestehende Produktabrufmechanismen für „beliebte Produkte“.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Logik ist in der Hauptmoduldatei und den zugehörigen Templates und Assets gekapselt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Es arbeitet, indem es die Kernfunktionalitäten von PrestaShop für den Produktabruf nutzt.

### 4.4 JavaScript-Assets (`views/js/`)

- **`homepagetabs/views/js/homepagetabs.js`**
  - **Umfang:** Front-Office.
  - **Zweck:** Diese Datei enthält wahrscheinlich die JavaScript-Logik zur Handhabung der Tab-Umschaltfunktion auf der Startseite. Sie könnte auf Klickereignisse auf dem „Beliebte Produkte“-Tab reagieren, den entsprechenden Produktinhalt ein-/ausblenden und möglicherweise mit anderen Homepage-Tabs interagieren, um sicherzustellen, dass immer nur der Inhalt eines Tabs sichtbar ist. Sie kann auch Logik für responsives Verhalten oder Lazy Loading von Produktbildern innerhalb des Tabs enthalten.
  - **Schlüsselfunktionalität:**
    - Event-Listener für Tab-Klicks.
    - DOM-Manipulation zum Umschalten der Sichtbarkeit von Produktlisten.
    - Potenziell Integration mit PrestaShops Standard-Tab-Verhalten oder benutzerdefinierten Theme-Tab-Systemen.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`homepagetabs/views/css/homepagetabs.css`**
  - **Umfang:** Front-Office-Kundenstyling.
  - **Zweck:** Dieses Stylesheet definiert das visuelle Erscheinungsbild des „Beliebte Produkte“-Tabs und der darin enthaltenen Produktlisten. Es stellt sicher, dass der Tab richtig positioniert, gestylt und dass das Produktgitter/-liste ordentlich präsentiert wird.
  - **Wichtigste gestylte UI-Komponenten:**
    - Der Tab-Header selbst (z. B. `.homepagetabs-tab-title`).
    - Der Container für die beliebten Produkte (z. B. `.homepagetabs-products-container`).
    - Einzelne Produktelemente innerhalb des Tabs (z. B. Produktbilder, Namen, Preise, Schaltflächen).
    - Responsive Anpassungen für verschiedene Bildschirmgrößen.
  - **Wichtige CSS-Klassenselektoren zum Überschreiben:** Entwickler können den generierten HTML-Code überprüfen, um spezifische Selektoren zu finden. Gängige könnten sein:
    - `.homepagetabs-tab`
    - `.homepagetabs-tab-content`
    - `.homepagetabs-product-list`
    - `.homepagetabs-product-item`

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - **`homepagetabs/views/templates/hook/homepagetabs.tpl`**
    - **Hook:** `displayHome`
    - **Zweck:** Dies ist das primäre Front-Office-Template. Es ist verantwortlich für das Rendern des „Beliebte Produkte“-Tab-Headers und des Containers für die Produktliste. Es wird typischerweise eine Sammlung beliebter Produkte, die ihm von der `hookDisplayHome`-Methode des Moduls übergeben wurden, durchlaufen und jedes Produkt mithilfe eines Standard-PrestaShop-Produktlisten-Partials (oder eines benutzerdefinierten, das innerhalb des Moduls definiert ist) rendern. Dieses Template ist der Ort, an dem die eigentliche HTML-Struktur für den Tab und seinen Inhalt generiert wird.
- **Admin-Templates (`views/templates/admin/`)**:
  - **`homepagetabs/views/templates/admin/homepagetabs.tpl`**
    - **Zweck:** Dieses Template rendert das Konfigurationsformular des Moduls im PrestaShop Back Office. Es zeigt die Einstellungen für Update-Benachrichtigungen (`mypresta_updates`) und möglicherweise andere modulspezifische Optionen an, falls diese hinzugefügt werden sollten. Es verwendet PrestaShops Helper-Formular-Klassen, um die Eingabefelder und Speicher-Buttons zu generieren.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen (wie `mypresta_updates`) in der Standardtabelle `ps_configuration`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHome` | Rendert Inhalte auf der Startseite des Shops. | Fügt den „Beliebte Produkte“-Tab und dessen Inhalt in den Hauptbereich der Startseite ein. |
| `displayHeader` | Wird im `<head>`-Bereich jeder Seite ausgeführt. | Wird verwendet, um die CSS- (`homepagetabs.css`) und JavaScript-Dateien (`homepagetabs.js`) des Moduls in die Warteschlange zu stellen, um sicherzustellen, dass sie für die Front-Office-Anzeige korrekt geladen werden. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und alle Anfragen bezüglich des Moduls „Homepage-Tab beliebte Produkte“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team und unsere Ressourcen stehen Ihnen bei Installation, Konfiguration und Fehlerbehebung zur Verfügung.

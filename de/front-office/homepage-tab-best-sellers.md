---
title: "Homepage-Tab Bestseller – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Homepage-Tab Bestseller' von MyPresta.eu."
sidebar:
  label: "Homepage-Tab Bestseller – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Homepage tab best sellers auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/homepage-tab-best-sellers.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/homepage-tab-best-sellers/)
>
> ---


# Homepage-Tab Bestseller

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und in jeder modernen Hosting-Umgebung verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager neben dem Modul „Homepage-Tab Bestseller“ auf „Konfigurieren“. Sie werden zur Konfigurationsseite weitergeleitet.

#### Anzahl der anzuzeigenden Produkte

- **Was diese Einstellung bewirkt:** Diese Einstellung steuert, wie viele meistverkaufte Produkte im Tab „Bestseller“ auf Ihrer Startseite angezeigt werden.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Bei Einstellung auf eine höhere Zahl (z.B. 12):* Es werden mehr Produkte im Tab angezeigt, was Kunden eine größere Auswahl Ihrer Bestseller zum Durchsuchen bietet. Dies kann gut für Shops mit vielen beliebten Artikeln sein.
  - *Bei Einstellung auf eine niedrigere Zahl (z.B. 4):* Es werden weniger Produkte angezeigt, was eine prägnantere und fokussiertere Präsentation schafft. Dies kann vorteilhaft für Shops mit weniger Bestsellern sein oder wenn Sie nur eine ausgewählte Anzahl hervorheben möchten.
- **Empfohlener Wert:** Ein guter Ausgangspunkt liegt typischerweise zwischen **8 und 12** Produkten. Dies bietet genügend Vielfalt, ohne den Kunden zu überfordern oder die Seite zu lang zu machen.
- **Händlerszenario / Beispiel:** Wenn Sie einen großen Katalog und viele Produkte haben, die sich konstant gut verkaufen, könnten Sie dies auf 10 oder 12 einstellen, um mehr Ihrer beliebten Artikel zu präsentieren. Wenn Sie eine sauberere, minimalistischere Startseite bevorzugen, könnten Sie es auf 6 einstellen.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung ## 5. Praktische Anwendungsfälle & Best Practices (Profi-Tipps)

1. **Social Proof für neue Besucher nutzen:**
   - **Szenario:** Ein neuer Kunde landet auf Ihrer Startseite. Er kennt weder Ihre Marke noch Ihre Produkte.
   - **Profi-Tipp:** Der Tab „Bestseller“ liefert sofort Social Proof und zeigt, was andere Kunden kaufen und lieben. Stellen Sie sicher, dass Ihre Bestseller gute Produktbilder und klare Beschreibungen haben. Erwägen Sie, eine temporäre Aktion (z.B. „Unsere Top 5 Bestseller – Diese Woche 10% Rabatt!“) zu starten, um noch mehr Aufmerksamkeit auf diesen Bereich zu lenken.
2. **Für saisonale & trendige Produkte optimieren:**
   - **Szenario:** Ihr Shop erlebt saisonale Verkaufsspitzen (z.B. Weihnachtsgeschenke, Sommerbekleidung) oder hat Produkte, die plötzlich im Trend liegen.
   - **Profi-Tipp:** Während das Modul Bestseller automatisch identifiziert, können Sie dies indirekt beeinflussen, indem Sie bestimmte Produkte strategisch bewerben. Wenn Sie beispielsweise im Sommer möchten, dass Ihre Bademode in den „Bestsellern“ erscheint, stellen Sie sicher, dass sie gut bestückt, wettbewerbsfähig bepreist und vielleicht in anderen Marketingmaßnahmen beworben wird. Wenn sie sich mehr verkaufen, steigen sie natürlich in den Bestseller-Rankings auf und erscheinen im Tab.
3. **Cross-Promotion mit anderen Homepage-Bereichen:**
   - **Szenario:** Sie haben andere Produktbereiche auf Ihrer Startseite (z.B. „Neue Produkte“, „Empfohlene Produkte“).
   - **Profi-Tipp:** Nutzen Sie den Tab „Bestseller“ als ergänzenden Bereich. Wenn ein Produkt neu ist und sich außergewöhnlich gut verkauft, könnte es sowohl unter „Neue Produkte“ als auch unter „Bestseller“ erscheinen, was seine Beliebtheit verstärkt. Vermeiden Sie möglichst zu viele überlappende Produkte, um Kunden mehr Vielfalt zu bieten, aber verstecken Sie ein wirklich gut verkauftes neues Produkt nicht nur der Vielfalt halber. Die automatische Natur des Moduls wird dies natürlich handhaben.

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein „Bestseller“-Tab wird nicht auf der Startseite angezeigt.**

- **A:** Stellen Sie zunächst sicher, dass das Modul unter **Module > Modul-Manager** installiert und aktiviert ist. Überprüfen Sie dann dessen Konfiguration. Wenn der Tab immer noch nicht erscheint, könnte es ein Caching-Problem sein. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Wenn Ihr Theme stark angepasst ist, bindet es sich möglicherweise nicht korrekt in `displayHomeTab` und `displayHomeTabContent` ein. In diesem Fall müssen Sie möglicherweise Ihren Theme-Entwickler oder einen PrestaShop-Experten konsultieren.

**F2: Die Produkte im „Bestseller“-Tab scheinen nicht meine tatsächlichen Bestseller zu sein.**

- **A:** Das Modul stützt sich auf die internen Verkaufsdaten von PrestaShop, um Bestseller zu ermitteln.
  - Stellen Sie sicher, dass Sie tatsächliche Verkaufsdaten für Produkte haben. Neue Shops oder Shops mit sehr wenigen Verkäufen haben möglicherweise nicht genügend Daten für eine aussagekräftige „Bestseller“-Liste.
  - Die „Bestseller“-Berechnung basiert normalerweise auf der Anzahl der verkauften Einheiten über einen bestimmten Zeitraum. Es kann einige Zeit dauern, bis sich aktuelle Verkäufe in der Liste widerspiegeln.
  - Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**), um sicherzustellen, dass die neuesten Daten abgerufen werden.

**F3: Wie oft wird die „Bestseller“-Liste aktualisiert?**

- **A:** Die Liste der Bestseller wird von PrestaShop dynamisch auf Basis der Verkaufsdaten generiert. Sie wird automatisch aktualisiert, sobald Bestellungen aufgegeben und verarbeitet werden. Damit die Änderungen im Front Office sichtbar werden, müssen Sie jedoch möglicherweise Ihren PrestaShop-Cache leeren, insbesondere wenn Sie aggressives Caching aktiviert haben.

**F4: Kann ich den Titel des Tabs ändern (z.B. von „Bestseller“ zu „Unsere Top-Auswahl“)?**

- **A:** Ja, das können Sie. Der Tab-Titel ist typischerweise ein übersetzbarer String innerhalb des Moduls.
  1. Gehen Sie zu **International > Übersetzungen**.
  2. Wählen Sie „Übersetzungen installierter Module“.
  3. Wählen Sie Ihr Theme.
  4. Wählen Sie Ihre Sprache.
  5. Suchen Sie das Modul „Homepage-Tab Bestseller“ in der Liste.
  6. Suchen Sie den Textstring für den Tab-Titel (z.B. „Bestseller“) und ändern Sie ihn in Ihren gewünschten Text. Denken Sie daran, Ihre Änderungen zu speichern.

**F5: Die Produkte sehen im Tab seltsam oder falsch ausgerichtet aus.**

- **A:** Dies ist normalerweise ein CSS-Styling-Konflikt mit Ihrem PrestaShop-Theme. Das Modul liefert die Produktdaten, aber Ihr Theme ist dafür verantwortlich, wie diese Daten angezeigt werden (Layout, Schriftarten, Farben, Bildgrößen).
  - Stellen Sie sicher, dass Ihr Theme auf dem neuesten Stand ist.
  - Versuchen Sie, Ihren PrestaShop-Cache zu leeren (**Erweiterte Einstellungen > Leistung**).
  - Wenn das Problem weiterhin besteht, müssen Sie möglicherweise benutzerdefiniertes CSS zu Ihrem Theme hinzufügen, um die Standardstile des Moduls oder des Themes zu überschreiben. Dies erfordert normalerweise einen Webentwickler.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Homepage-Tab Bestseller“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul `Homepage tab best sellers` ist ein unkompliziertes PrestaShop-Modul, das für die nahtlose Integration in das Homepage-Tab-System entwickelt wurde. Es folgt einer klassischen PrestaShop-Modulstruktur, die hauptsächlich die `Module`-Klasse und Front-Office-Hooks verwendet. Es führt keine benutzerdefinierten Controller, Modelle oder komplexe JavaScript/CSS ein, sondern verlässt sich stattdessen auf die Kernfunktionen von PrestaShop für den Abruf von Produktdaten und auf das vorhandene Theme-Styling für die Präsentation. Seine Hauptlogik befindet sich in der Datei `homebestsellerstab.php`, die die Konfiguration und Hook-Registrierung handhabt.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Der Front-Office-Inhalt des Moduls wird direkt über Smarty-Templates gerendert, die in `displayHomeTab` und `displayHomeTabContent` eingebunden sind.
- **Back-Office-Admin-Controller**: Keine. Die Modulkonfiguration wird durch die Methode `getContent()` innerhalb der Hauptmodulklasse gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine. Das Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Es nutzt die Kernklassen `Product` und `ProductSale` von PrestaShop (oder ähnliche interne Mechanismen), um Daten zu meistverkauften Produkten abzurufen.

### 4.4 JavaScript-Assets (`views/js/`)

- Keine. Das Modul enthält keine benutzerdefinierten JavaScript-Dateien. Jedes interaktive Verhalten (wie das Umschalten von Tabs) wird voraussichtlich vom vorhandenen JavaScript des PrestaShop-Themes gehandhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Das Modul enthält keine benutzerdefinierten CSS-Dateien. Das Styling des Tabs und der Produktlisten darin hängt vollständig vom aktiven PrestaShop-Theme ab. Entwickler sollten das generierte HTML inspizieren und relevante Klassen/IDs im CSS ihres Themes ansprechen, um das Erscheinungsbild anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet zwei Smarty-Template-Dateien, beide im Verzeichnis `views/templates/hook/`, um seinen Inhalt im Front Office zu rendern.

- **`views/templates/hook/tab.tpl`**

  - **Hook**: `displayHomeTab`
  - **Zweck**: Dieses Template ist für das Rendern des tatsächlich anklickbaren Tab-Elements auf der Startseite verantwortlich. Es enthält typischerweise das `<li>`- oder `<a>`-Tag, das den „Bestseller“-Tab darstellt, einschließlich seines übersetzbaren Titels.
  - **Ausgabe**: Ein Tab-Element, das beim Klicken den Inhalt anzeigt, der von `homebestsellerstab.tpl` gerendert wird.
- **`views/templates/hook/homebestsellerstab.tpl`**

  - **Hook**: `displayHomeTabContent`
  - **Zweck**: Dieses Template rendert die eigentliche Liste oder das Raster der meistverkauften Produkte, wenn der „Bestseller“-Tab aktiv ist. Es empfängt ein Array von Produktdaten aus der PHP-Logik des Moduls.
  - **Ausgabe**: HTML-Markup zur Anzeige von Produkten (z.B. `div`-Container, Produktbilder, Namen, Preise, In-den-Warenkorb-Buttons). Es iteriert typischerweise über die an es übergebene Variable `$products`.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfiguration (z.B. `HOME_BEST_NBR`) in der PrestaShop-Tabelle `ps_configuration`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck Der Konfigurationsschlüssel `HOME_BEST_NBR` wird verwendet, um die Anzahl der anzuzeigenden Produkte zu speichern.
`PS_LANG_DEFAULT` und `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` sind PrestaShop-Kernkonfigurationsschlüssel, die zur Verwaltung der Standardsprache und der Spracheinstellungen für Mitarbeiterformulare verwendet werden. Diese werden nicht direkt vom Modul konfiguriert, sondern für den Kontext abgerufen.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Homepage-Tab Bestseller“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Sie können die aktuellste Version des Moduls aus Ihrer Bestellhistorie herunterladen. Für technische Unterstützung oder Anfragen nutzen Sie bitte die auf der MyPresta.eu-Website bereitgestellten Support-Kanäle.

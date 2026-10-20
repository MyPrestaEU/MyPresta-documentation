---
title: "European Union Cookie Law Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul European Union Cookie Law Pro von MyPresta.eu."
sidebar:
  label: "European Union Cookie Law Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul European Union Cookie Law Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/european-union-cookie-law-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/european-union-cookie-law-pro/)
>
> ---


# European Union Cookie Law Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > European Union Cookie Law Pro)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das Erscheinungsbild, den Inhalt und das Verhalten Ihres Cookie-Hinweises definieren. Das Modul bietet eine Live-Vorschau-Funktion, mit der Sie Ihre Änderungen in Echtzeit im Back Office sehen können, bevor Sie speichern.

#### **Allgemeine Einstellungen**

- **Cookie-Gesetz-Modul aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um den Cookie-Hinweis in Ihrem gesamten Shop ein- oder auszuschalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Der Cookie-Hinweis wird den Besuchern gemäß Ihren anderen Einstellungen angezeigt.
    - *Wenn deaktiviert (NEIN):* Der Cookie-Hinweis wird in Ihrem Shop nicht angezeigt, und es wird keine Cookie-Zustimmung von diesem Modul erfasst.
  - **Empfohlener Wert:** JA (um die rechtliche Compliance zu gewährleisten).
  - **Händlerszenario / Beispiel:** Sie würden dies vorübergehend während der Wartung oder wenn Sie eine andere Cookie-Lösung testen, deaktivieren.
- **Cookie-Ablaufzeit (in Tagen):**

  - **Was diese Einstellung bewirkt:** Bestimmt, wie lange die Cookie-Zustimmung eines Benutzers von Ihrem Shop gespeichert wird. Nach diesem Zeitraum wird der Benutzer erneut um Zustimmung gebeten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 365 gesetzt:* Die Zustimmung eines Benutzers ist ein Jahr lang gültig.
    - *Wenn auf 30 gesetzt:* Die Zustimmung ist einen Monat lang gültig.
  - **Empfohlener Wert:** 365 (ein Jahr) ist ein üblicher und angemessener Zeitraum für die meisten Vorschriften. Überprüfen Sie die lokalen Gesetze auf spezifische Anforderungen.
  - **Händlerszenario / Beispiel:** Wenn Ihre lokalen Vorschriften eine erneute Zustimmung alle 6 Monate erfordern, würden Sie dies auf 180 setzen.
- **Auf Mobilgeräten anzeigen:**

  - **Was diese Einstellung bewirkt:** Steuert, ob der Cookie-Hinweis Benutzern angezeigt wird, die auf Smartphones und Tablets surfen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Der Cookie-Hinweis wird auf mobilen Geräten angezeigt und passt sein Layout an kleinere Bildschirme an.
    - *Wenn deaktiviert (NEIN):* Mobile Benutzer sehen den Cookie-Hinweis nicht.
  - **Empfohlener Wert:** JA (für vollständige Compliance auf allen Geräten).
  - **Händlerszenario / Beispiel:** Sie sollten dies immer aktivieren, da mobile Benutzer denselben Datenschutzgesetzen unterliegen.
- **Nur Besuchern aus EU-Ländern anzeigen:**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, wird der Cookie-Hinweis nur Besuchern angezeigt, deren IP-Adresse darauf hinweist, dass sie aus einem EU-Mitgliedstaat surfen.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Nicht-EU-Besucher sehen den Banner nicht.
    - *Wenn deaktiviert (NEIN):* Alle Besucher, unabhängig von ihrem Standort, sehen den Banner.
  - **Empfohlener Wert:** Hängt von Ihrer Zielgruppe und rechtlicher Beratung ab. Wenn Sie nur EU-Kunden bedienen, könnte JA angemessen sein. Wenn Sie ein globales Publikum bedienen und auf Nummer sicher gehen wollen, ist NEIN besser.
  - **Händlerszenario / Beispiel:** Ein australischer Shop, der hauptsächlich australische Kunden bedient, könnte dies aktivieren, um den Banner seinem Hauptpublikum nicht anzuzeigen, während er dennoch für die wenigen EU-Besucher konform ist. Ein globaler Shop könnte es deaktivieren, um universell konform zu sein.

#### **Inhalt & Links**

- **Cookie-Gesetz-Nachricht:**

  - **Was diese Einstellung bewirkt:** Dies ist der Haupttext, der im Cookie-Hinweis angezeigt wird und Benutzer über die Cookie-Nutzung informiert. Sie können einen Rich-Text-Editor verwenden, um ihn zu formatieren.
  - **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Text ist die primäre Nachricht, die Ihre Kunden lesen.
  - **Empfohlener Wert:** Eine klare, prägnante Nachricht wie „Diese Website verwendet Cookies, um sicherzustellen, dass Sie die beste Erfahrung auf unserer Website erhalten. [Mehr erfahren]“
  - **Händlerszenario / Beispiel:** Sie könnten Informationen über die verwendeten Cookie-Typen aufnehmen (z.B. „Wir verwenden Cookies für Analysen und zur Verbesserung Ihres Einkaufserlebnisses.“).
- **Text der Schaltfläche „Akzeptieren“:**

  - **Was diese Einstellung bewirkt:** Definiert den Text, der auf der Schaltfläche angezeigt wird, die Benutzer anklicken, um Cookies zu akzeptieren.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die Beschriftung der Akzeptanzschaltfläche.
  - **Empfohlener Wert:** „Akzeptieren“, „Verstanden“, „OK“, „Ich verstehe“.
  - **Händlerszenario / Beispiel:** Sie könnten „Akzeptieren & Weiter“ verwenden, um Benutzer zum Fortfahren zu ermutigen.
- **Text der Schaltfläche „Weitere Informationen“:**

  - **Was diese Einstellung bewirkt:** Definiert den Text, der auf der Schaltfläche angezeigt wird, die Benutzer anklicken, um mehr über Ihre Cookie-Richtlinie zu erfahren.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die Beschriftung der Informationsschaltfläche.
  - **Empfohlener Wert:** „Mehr erfahren“, „Weitere Informationen“, „Datenschutzerklärung“.
  - **Händlerszenario / Beispiel:** Sie könnten „Cookie-Einstellungen“ verwenden, wenn Sie ein detailliertes Präferenzverwaltungssystem haben.
- **Link zur Datenschutzerklärung:**

  - **Was diese Einstellung bewirkt:** Gibt die URL an, unter der Benutzer Ihre vollständige Datenschutz- oder Cookie-Richtlinie finden können. Dieser Link wird an die Schaltfläche „Weitere Informationen“ oder einen bestimmten Teil Ihrer Nachricht angehängt.
  - **Auswirkung der Änderung dieser Einstellung:** Wenn Benutzer auf die Schaltfläche „Weitere Informationen“ klicken, werden sie zu dieser URL weitergeleitet.
  - **Empfohlener Wert:** Die vollständige URL Ihrer CMS-Seite (z.B. `https://ihrshop.com/content/3-agb`).
  - **Händlerszenario / Beispiel:** Sie erstellen eine dedizierte CMS-Seite in PrestaShop (Design > Seiten) für Ihre „Cookie-Richtlinie“ und verlinken sie hier.

#### **Anzeigeoptionen & Styling**

- **Position des Cookie-Hinweises:**

  - **Was diese Einstellung bewirkt:** Bestimmt, wo der Cookie-Hinweis auf Ihrer Website erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Obere Leiste:* Banner erscheint oben im Browserfenster.
    - *Untere Leiste:* Banner erscheint unten im Browserfenster.
    - *Zentrales Modal:* Ein Pop-up in der Mitte des Bildschirms.
    - *Schwebendes Feld (Oben-Links, Oben-Rechts, Unten-Links, Unten-Rechts):* Ein kleineres, festes Feld in einer der Ecken.
  - **Empfohlener Wert:** Untere Leiste oder Schwebendes Feld sind im Allgemeinen weniger aufdringlich. Zentrales Modal ist sehr sichtbar, kann aber störend sein.
  - **Händlerszenario / Beispiel:** Ein Modegeschäft könnte eine subtile „Untere Leiste“ bevorzugen, um den Fokus auf die Produkte zu legen, während ein dienstleistungsbasiertes Unternehmen ein „Zentrales Modal“ für maximale Sichtbarkeit verwenden könnte.
- **Hintergrundfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Haupt-Hintergrundfarbe des Cookie-Hinweis-Banners fest.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert den visuellen Hintergrund des Hinweises.
  - **Empfohlener Wert:** Eine Farbe, die gut mit Ihrem Text kontrastiert und zu Ihrer Marke passt.
  - **Händlerszenario / Beispiel:** Verwenden Sie die Primärfarbe Ihrer Marke oder ein neutrales Grau.
- **Textfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Farbe des Hauptnachrichtentextes innerhalb des Hinweises fest.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die Farbe des Nachrichtentextes.
  - **Empfohlener Wert:** Eine Farbe, die eine gute Lesbarkeit vor dem gewählten Hintergrund bietet.
  - **Händlerszenario / Beispiel:** Weißer Text auf dunklem Hintergrund oder dunkelgrauer Text auf hellem Hintergrund.
- **Linkfarbe:**

  - **Was diese Einstellung bewirkt:** Legt die Farbe für alle Links innerhalb Ihrer Cookie-Nachricht fest (z.B. der Link „Mehr erfahren“, wenn er Teil der Nachricht ist).
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die Farbe des anklickbaren Textes innerhalb der Nachricht.
  - **Empfohlener Wert:** Die Akzentfarbe Ihrer Marke oder ein Standardblau für Links.
  - **Händlerszenario / Beispiel:** Verwenden Sie eine helle Farbe, um den Link „Mehr erfahren“ hervorzuheben.
- **Hintergrundfarbe der Schaltfläche:**

  - **Was diese Einstellung bewirkt:** Legt die Hintergrundfarbe für die Schaltflächen „Akzeptieren“ und „Weitere Informationen“ fest.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert den visuellen Hintergrund der Schaltflächen.
  - **Empfohlener Wert:** Eine Farbe, die die Schaltflächen deutlich sichtbar und anklickbar macht.
  - **Händlerszenario / Beispiel:** Verwenden Sie die Call-to-Action-Farbe Ihrer Marke.
- **Textfarbe der Schaltfläche:**

  - **Was diese Einstellung bewirkt:** Legt die Farbe des Textes auf den Schaltflächen „Akzeptieren“ und „Weitere Informationen“ fest.
  - **Auswirkung der Änderung dieser Einstellung:** Ändert die Farbe der Schaltflächenbeschriftungen.
  - **Empfohlener Wert:** Eine Farbe, die einen guten Kontrast zum Schaltflächenhintergrund bietet.
  - **Händlerszenario / Beispiel:** Weißer Text auf einer farbigen Schaltfläche oder schwarzer Text auf einer hellen Schaltfläche.
- **Hintergrundfarbe der Schaltfläche beim Hover:**

  - **Was diese Einstellung bewirkt:** Legt die Hintergrundfarbe der Schaltflächen fest, wenn ein Benutzer den Mauszeiger darüber bewegt.
  - **Auswirkung der Änderung dieser Einstellung:** Bietet dem Benutzer visuelles Feedback, dass die Schaltfläche interaktiv ist.
  - **Empfohlener Wert:** Ein etwas dunklerer oder hellerer Farbton der normalen Schaltflächen-Hintergrundfarbe.
  - **Händlerszenario / Beispiel:** Eine subtile Farbänderung, um Interaktivität anzuzeigen.
- **Textfarbe der Schaltfläche beim Hover:**

  - **Was diese Einstellung bewirkt:** Legt die Textfarbe der Schaltflächen fest, wenn ein Benutzer den Mauszeiger darüber bewegt.
  - **Auswirkung der Änderung dieser Einstellung:** Bietet visuelles Feedback.
  - **Empfohlener Wert:** Oft dieselbe wie die normale Schaltflächen-Textfarbe oder eine kontrastierende Farbe, wenn sich der Hintergrund erheblich ändert.
  - **Händlerszenario / Beispiel:** Wenn der Schaltflächenhintergrund beim Hover dunkel wird, könnten Sie den Text auf Weiß ändern.
- **Border Radius (px):**

  - **Was diese Einstellung bewirkt:** Steuert die Rundung der Ecken des Cookie-Hinweises und seiner Schaltflächen. Ein Wert von 0 bedeutet scharfe Ecken, höhere Werte bedeuten rundere Ecken.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *0px:* Scharfe, eckige Ecken.
    - *5px:* Leicht abgerundete Ecken.
    - *20px:* Sehr abgerundete, pillenförmige Ecken.
  - **Empfohlener Wert:** 0-5px für einen modernen, sauberen Look; höher für ein weicheres, freundlicheres Gefühl.
  - **Händlerszenario / Beispiel:** Passen Sie dies an den in Ihrem Theme verwendeten Border-Radius an, um Konsistenz zu gewährleisten.
- **Glaseffekt:**

  - **Was diese Einstellung bewirkt:** Wendet einen durchscheinenden, mattierten Glas-ähnlichen Effekt auf den Hintergrund des Cookie-Hinweises an.
  - **Auswirkung der Änderung dieser Einstellung:** Macht den Hintergrund leicht transparent und unscharf, sodass der Inhalt dahinter subtil durchscheint.
  - **Empfohlener Wert:** Probieren Sie es aus und sehen Sie, ob es zu Ihrem Design passt. Es kann ein Premium-Gefühl verleihen.
  - **Händlerszenario / Beispiel:** Verwenden Sie dies, wenn Ihr Theme eine moderne, minimalistische Ästhetik hat.
- **Verlaufshintergrund:**

  - **Was diese Einstellung bewirkt:** Ermöglicht die Verwendung eines sanften Übergangs zwischen zwei Farben für den Hintergrund des Cookie-Hinweises anstelle einer einzelnen Volltonfarbe.
  - **Auswirkung der Änderung dieser Einstellung:** Erzeugt eine visuell ansprechende Farbmischung. Sie haben typischerweise Optionen für eine Start- und Endfarbe.
  - **Empfohlener Wert:** Verwenden Sie Farben, die sich gegenseitig und Ihre Marke ergänzen.
  - **Händlerszenario / Beispiel:** Ein Technikgeschäft könnte einen Blau-zu-Lila-Verlauf für einen modernen Look verwenden.
- **Hintergrundfarbe der Überlagerung (für Zentrales Modal):**

  - **Was diese Einstellung bewirkt:** Bei Verwendung der Position „Zentrales Modal“ legt dies die Farbe der halbtransparenten Ebene fest, die den Rest der Seite hinter dem Modal bedeckt.
  - **Auswirkung der Änderung dieser Einstellung:** Steuert den visuellen Fokus auf das Modal. Eine dunklere, undurchsichtigere Überlagerung lässt das Modal stärker hervorstechen.
  - **Empfohlener Wert:** Ein halbtransparentes Schwarz (`rgba(0,0,0,0.7)`) oder ein dunkler Farbton, der zu Ihrem Theme passt.
  - **Händlerszenario / Beispiel:** Verwenden Sie eine dunkle, leicht transparente Überlagerung, um sicherzustellen, dass das Cookie-Modal beim Erscheinen im Vordergrund steht.
- **Benutzerdefiniertes CSS:**

  - **Was diese Einstellung bewirkt:** Bietet einen Textbereich, in dem Sie Ihre eigenen benutzerdefinierten CSS-Regeln hinzufügen können, um den Cookie-Hinweis weiter zu gestalten und die Standardstile des Moduls zu überschreiben.
  - **Auswirkung der Änderung dieser Einstellung:** Ermöglicht erweiterte Anpassungen über die bereitgestellten Optionen hinaus.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Designanforderungen und CSS-Kenntnisse.
  - **Händlerszenario / Beispiel:** Sie könnten dies verwenden, um die Schriftgröße der Nachricht zu ändern, einen Schatten hinzuzufügen oder den Abstand anzupassen, wenn die integrierten Optionen nicht ausreichen.

#### **Voreinstellungen & Live-Vorschau**

- **Voreinstellung laden:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, schnell eine vordefinierte Reihe von Styling-Optionen (Farben, Positionen, Effekte) aus einer Bibliothek von vorgefertigten Designs anzuwenden.
  - **Auswirkung der Änderung dieser Einstellung:** Verändert das Aussehen Ihres Cookie-Hinweises sofort, um der gewählten Voreinstellung zu entsprechen. Alle individuellen Styling-Einstellungen werden aktualisiert.
  - **Empfohlener Wert:** Durchsuchen Sie die Voreinstellungen, um eine zu finden, die Ihrer Marke am nächsten kommt, und passen Sie sie dann an.
  - **Händlerszenario / Beispiel:** Sie suchen einen dunklen, minimalistischen Banner. Sie wählen eine „Dunkles Theme“-Voreinstellung und passen dann nur die genauen Schwarz- und Grautöne an.
- **Live-Vorschau:**

  - **Was diese Einstellung bewirkt:** Dieser Abschnitt der Konfigurationsseite zeigt eine Echtzeit-Vorschau Ihres Cookie-Hinweises an, während Sie die Einstellungen anpassen.
  - **Auswirkung der Änderung dieser Einstellung:** Zeigt Ihnen genau, wie Ihr Banner im Front Office aussehen wird, ohne dass Sie speichern und Ihren Shop aktualisieren müssen.
  - **Empfohlener Wert:** Verwenden Sie immer die Live-Vorschau, um Ihre Designentscheidungen vor dem Speichern zu überprüfen.
  - **Händlerszenario / Beispiel:** Sie experimentieren mit verschiedenen Schaltflächenfarben; die Live-Vorschau zeigt Ihnen sofort, welche Kombination am besten aussieht.

### 2.2 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Cookie-Gesetz-Modul aktivieren | JA | Hauptschalter für den Cookie-Hinweis. |
| | Cookie-Ablaufzeit (Tage) | 365 | Wie lange die Zustimmung gespeichert wird. |
| | Auf Mobilgeräten anzeigen | JA | Banner auf Telefonen/Tablets anzeigen. |
| | Nur EU-Besuchern anzeigen | NEIN (für globale Compliance) | EU-Besucher oder alle Besucher ansprechen. |
| | Cookie-Gesetz-Nachricht | Anpassbar | Haupttext des Cookie-Hinweises. |
| | Text der Schaltfläche „Akzeptieren“ | „Akzeptieren“ | Beschriftung für die Zustimmungs-Schaltfläche. |
| | Text der Schaltfläche „Weitere Informationen“ | „Mehr erfahren“ | Beschriftung für die Info-Schaltfläche. |
| | Link zur Datenschutzerklärung | Ihre Richtlinien-URL | URL für detaillierte Cookie-Richtlinie. |
| | Position des Cookie-Hinweises | Untere Leiste / Schwebendes Feld | Wo der Banner erscheint (Obere/Untere Leiste, Zentrales Modal, Schwebendes Feld). |
| | Hintergrundfarbe | Anpassbar | Haupt-Hintergrundfarbe des Hinweises. |
| | Textfarbe | Anpassbar | Farbe des Nachrichtentextes. |
| | Linkfarbe | Anpassbar | Farbe der Links innerhalb der Nachricht. |
| | Hintergrundfarbe der Schaltfläche | Anpassbar | Hintergrundfarbe der Aktionsschaltflächen. |
| | Textfarbe der Schaltfläche | Anpassbar | Textfarbe auf Aktionsschaltflächen. |
| | Hintergrundfarbe der Schaltfläche beim Hover | Anpassbar | Hintergrundfarbe beim Hover über die Schaltfläche. |
| | Textfarbe der Schaltfläche beim Hover | Anpassbar | Textfarbe beim Hover über die Schaltfläche. |
| | Border Radius (px) | 0-5 | Rundung der Ecken. |
| | Glaseffekt | NEIN | Fügt einen durchscheinenden, mattierten Effekt hinzu. |
| | Verlaufshintergrund | NEIN | Verwendet einen Farbverlauf für den Hintergrund. |
| | Hintergrundfarbe der Überlagerung | Halbtransparent dunkel | Farbe der Hintergrundüberlagerung für Zentrales Modal. |
| | Benutzerdefiniertes CSS | Leer | Für erweiterte Styling-Überschreibungen. |
| | Voreinstellung laden | Eine auswählen | Vordefinierte Styling-Optionen anwenden. |
| | Live-Vorschau | N/A | Visuelles Echtzeit-Feedback der Einstellungen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul konfiguriert, aber der Cookie-Banner wird in meinem Shop nicht angezeigt.**
A:

1. **Überprüfen Sie „Cookie-Gesetz-Modul aktivieren“:** Stellen Sie sicher, dass es in der Modulkonfiguration auf JA gesetzt ist.
2. **Cache leeren:** Gehen Sie im PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Der Browser-Cache muss möglicherweise ebenfalls geleert werden (Strg+F5 oder Cmd+R).
3. **EU-Ländereinstellung überprüfen:** Wenn „Nur Besuchern aus EU-Ländern anzeigen“ aktiviert ist, stellen Sie sicher, dass Sie von einer EU-IP-Adresse aus testen. Versuchen Sie, diese Einstellung vorübergehend zu deaktivieren, um zu testen.
4. **Theme-Kompatibilität:** Obwohl das Modul auf Kompatibilität ausgelegt ist, können einige stark angepasste Themes Konflikte aufweisen. Überprüfen Sie die Entwicklerkonsole Ihres Browsers (F12) auf JavaScript-Fehler.

**F: Der Banner sieht in meinem Shop anders aus als in der Live-Vorschau.**
A:

1. **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung**), nachdem Sie Änderungen vorgenommen haben. Ihr Browser-Cache zeigt möglicherweise auch eine ältere Version an.
2. **Benutzerdefinierte CSS-Konflikte:** Wenn Sie „Benutzerdefiniertes CSS“ hinzugefügt haben oder Ihr Theme widersprüchliche Stile aufweist, könnten diese die Einstellungen des Moduls überschreiben. Entfernen Sie Ihr benutzerdefiniertes CSS vorübergehend, um zu sehen, ob das Problem dadurch behoben wird.
3. **Theme-Überschreibungen:** Ihr Theme könnte spezifische CSS-Regeln haben, die spezifischer sind als die des Moduls. Ein Entwickler kann helfen, diese zu identifizieren und zu beheben.

**F: Wie übersetze ich die Cookie-Nachricht und die Schaltflächentexte in andere Sprachen?**
A:

1. Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
2. Wählen Sie „Übersetzungen installierter Module“ als Übersetzungstyp.
3. Wählen Sie Ihr Theme.
4. Wählen Sie die Sprache aus, in die Sie übersetzen möchten.
5. Suchen Sie das Modul „European Union Cookie Law Pro“ in der Liste. Dort können Sie die „Cookie-Gesetz-Nachricht“, den „Text der Schaltfläche Akzeptieren“ und den „Text der Schaltfläche Weitere Informationen“ übersetzen.

**F: Der Cookie-Banner verdeckt einen wichtigen Teil meiner Website (z.B. ein Chat-Widget, einen Menüpunkt).**
A:

1. **Position anpassen:** Experimentieren Sie mit der Einstellung „Position des Cookie-Hinweises“. Wenn eine untere Leiste ein Chat-Widget verdeckt, versuchen Sie eine obere Leiste oder ein schwebendes Feld in einer anderen Ecke.
2. **Benutzerdefiniertes CSS (Erweitert):** Wenn keine Position funktioniert, kann ein Entwickler das Feld „Benutzerdefiniertes CSS“ verwenden, um die `z-index`-Eigenschaft des Cookie-Banners oder des kollidierenden Elements anzupassen, um sicherzustellen, dass das richtige Element oben liegt.

**F: Behandelt dieses Modul verschiedene Cookie-Kategorien (z.B. essentielle, Analyse-, Marketing-Cookies)?**
A: Dieses Modul konzentriert sich hauptsächlich auf die Anzeige eines allgemeinen Cookie-Zustimmungshinweises und die Erfassung einer einzelnen „Akzeptieren“- oder „Ablehnen“-Zustimmung (durch Nicht-Akzeptieren). Für eine erweiterte, granulare Verwaltung von Cookie-Kategorien (bei der Benutzer auswählen können, welche Arten von Cookies sie zulassen) benötigen Sie in der Regel eine komplexere Lösung oder die Integration mit einer dedizierten Consent Management Platform (CMP). Dieses Modul ist für eine unkomplizierte Compliance konzipiert.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die das Modul „European Union Cookie Law Pro“ verstehen, anpassen oder debuggen möchten.

### 4.1 Architekturübersicht

Das Modul `uecookiepro` folgt einer Standard-PrestaShop-Modularchitektur, wobei es hauptsächlich die `Module`-Klasse für seine Kernfunktionalität und `getContent()` für die Back-Office-Konfiguration nutzt. Es injiziert seinen Front-Office-Inhalt direkt in einen ausgewählten Hook und rendert den Cookie-Banner dynamisch basierend auf den Konfigurationseinstellungen. Das Styling wird über Inline-Stile und potenziell benutzerdefiniertes CSS verwaltet, wobei JavaScript die Benutzerinteraktion und die Speicherung der Zustimmung übernimmt.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei gehandhabt, und die Front-Office-Anzeige wird über Hooks verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen. Alle Konfigurationen werden direkt in der Tabelle `ps_configuration` unter Verwendung von Standard-PrestaShop-Konfigurationsschlüsseln gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält mehrere JavaScript-Dateien, hauptsächlich für Verbesserungen der Back-Office-Konfiguration und die Front-Office-Interaktion.

- `uecookiepro/jscolor/jscolor.js`:
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Bietet die Farbauswahlfunktion, die im Konfigurationsformular des Moduls verwendet wird, sodass Händler Farben für den Banner visuell auswählen können.
- `uecookiepro/tinymce-original.js`:
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Die Kernbibliothek des TinyMCE Rich-Text-Editors. Diese wird für das Feld „Cookie-Gesetz-Nachricht“ verwendet, um Händlern die Formatierung ihrer Nachricht mit HTML zu ermöglichen.
- `uecookiepro/tinymce16.inc.js`:
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Eine Include-Datei, die wahrscheinlich spezifische TinyMCE-Initialisierungs- und Konfigurationseinstellungen enthält, die auf PrestaShop 1.6.x-Umgebungen zugeschnitten sind, um sicherzustellen, dass der Editor innerhalb der Modulkonfiguration korrekt funktioniert.
- `uecookiepro/views/js/patterns.js`:
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Enthält wahrscheinlich vordefinierte Muster oder Konfigurationen für die Styling-Voreinstellungen des Moduls, die verwendet werden, um schnell verschiedene visuelle Themes für den Cookie-Banner zu laden.
- `uecookiepro/views/js/presets-community.js`:
  - **Umfang:** Back-Office.
  - **Verantwortlichkeit:** Enthält zusätzliche von der Community beigesteuerte oder erweiterte Voreinstellungen für das visuelle Styling des Cookie-Banners, die mehr gebrauchsfertige Designoptionen bieten.
- `uecookiepro/views/js/scripts.js`:
  - **Umfang:** Front-Office und Back-Office.
  - **Verantwortlichkeit:** Dies ist die wichtigste benutzerdefinierte JavaScript-Datei für das Modul.
    - **Front-Office:** Verwaltet die Anzeigelogik des Cookie-Banners, lauscht auf Klicks auf die Schaltfläche „Akzeptieren“, setzt das Zustimmungs-Cookie und blendet den Banner aus. Es verwaltet auch die Sichtbarkeit basierend auf der `Cookie Expiration Time`.
    - **Back-Office:** Enthält wahrscheinlich Logik für die Live-Vorschau-Funktionalität, die den Vorschau-Banner dynamisch aktualisiert, wenn Einstellungen im Konfigurationsformular geändert werden. Es könnte auch Interaktionen mit der Funktion „Voreinstellung laden“ verwalten.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul listet in der bereitgestellten Inventur keine `.css`-Dateien explizit auf. Dies deutet darauf hin, dass das Styling hauptsächlich über Folgendes erfolgt:

1. **Inline-Stile:** Dynamisch vom Modul generiert basierend auf den Konfigurationseinstellungen (Farben, Positionen usw.).
2. **`jscolor.js`'s internes CSS:** Für die Farbauswahl-Benutzeroberfläche.
3. **`tinymce`'s internes CSS:** Für die Rich-Text-Editor-Benutzeroberfläche.
4. **Benutzerdefiniertes CSS-Feld:** Ermöglicht Händlern, ihre eigenen Stile einzufügen.
   Entwickler, die Stile überschreiben möchten, sollten den gerenderten HTML-Code des Cookie-Banners überprüfen und seine Elemente mit spezifischeren CSS-Regeln im Stylesheet ihres Themes oder über das benutzerdefinierte CSS-Feld des Moduls ansprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `uecookiepro/top.tpl`:
    - **Hook:** Dieses Template ist so konzipiert, dass es in verschiedenen Front-Office-Hooks wie `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn` oder sogar direkt in den Theme-Dateien `product.tpl` oder `index.tpl` gerendert wird, abhängig von der gewählten „Position des Cookie-Hinweises“ und der Implementierung der `hookDisplay*`-Methoden des Moduls.
    - **Ausgabe:** Es gibt die HTML-Struktur für den Cookie-Zustimmungsbanner aus, einschließlich des Nachrichtentextes, der Schaltfläche „Akzeptieren“ und des Links „Weitere Informationen“. Das dynamische Styling (Farben, Position, Effekte) wird entweder als Inline-Stile oder durch JavaScript-Manipulation in dieses Template injiziert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle Konfigurationseinstellungen werden in der Standard-PrestaShop-Tabelle `ps_configuration` gespeichert. Konfigurationsschlüssel folgen typischerweise dem Muster `UECOOKIEPRO_SETTING_NAME`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Seite gerendert. | Potenziell zum Laden von CSS/JS-Assets oder zum Einfügen des Banners ganz oben auf der Seite verwendet. |
| `displayFooter` | Wird am Ende jeder Seite, vor dem schließenden `</body>`-Tag, gerendert. | Häufiger Hook zum Einfügen des Cookie-Banners (Position untere Leiste) oder des zugehörigen JavaScripts. |
| `displayLeftColumn` | Wird in der linken Seitenleiste gerendert (falls vom Theme aktiviert). | Weniger üblich für Cookie-Banner, könnte aber für ein schwebendes Feld in der linken Spalte verwendet werden. |
| `displayRightColumn` | Wird in der rechten Seitenleiste gerendert (falls vom Theme aktiviert). | Weniger üblich für Cookie-Banner, könnte aber für ein schwebendes Feld in der rechten Spalte verwendet werden. |
| `displayProductAdditionalInfo` (oder ähnlicher Produktdetailseiten-Hook) | Wird auf der Produktseite gerendert, oft unterhalb der Produktbeschreibung oder Details. | Könnte verwendet werden, um ein schwebendes Feld speziell auf Produktseiten zu platzieren. |
| `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien (CSS/JS) setzt. | Ideal zum bedingten Laden modulspezifischer CSS- und JavaScript-Dateien nur bei Bedarf, was die Leistung verbessert. |

Das Modul wählt dynamisch, welcher Hook verwendet werden soll, basierend auf der Einstellung „Position des Cookie-Hinweises“. Wenn beispielsweise „Untere Leiste“ ausgewählt ist, wird wahrscheinlich `displayFooter` verwendet. Wenn „Obere Leiste“ ausgewählt ist, könnte `displayHeader` verwendet werden. Die Positionen „Schwebendes Feld“ oder „Zentrales Modal“ werden typischerweise durch Einfügen des HTML-Codes in einen allgemeinen Hook wie `displayFooter` und anschließende Verwendung von CSS (`position: fixed;`) und JavaScript zur Steuerung der genauen Platzierung und Sichtbarkeit verwaltet.

## 5. Offizieller Support & Updates

Für offiziellen Support, Modul-Updates und weitere Unterstützung wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, zeitnahen Support zu leisten und sicherzustellen, dass Ihr Modul optimal funktioniert.

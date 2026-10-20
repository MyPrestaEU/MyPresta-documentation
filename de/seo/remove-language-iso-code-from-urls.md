---
title: "Sprach-ISO-Code aus URLs entfernen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Sprach-ISO-Code aus URLs entfernen“ von MyPresta.eu."
sidebar:
  label: "Sprach-ISO-Code aus URLs entfernen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Remove language ISO code from urls auf MyPresta.eu kaufen](https://mypresta.eu/modules/seo/remove-language-iso-code-from-urls.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/seo/remove-language-iso-code-from-urls/)
>
> ---


# Sprach-ISO-Code aus URLs entfernen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich, die über die von PrestaShop selbst benötigten hinausgehen.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Modulnamen „Sprach-ISO-Code aus URLs entfernen“, um auf dessen Einstellungen zuzugreifen.

Die Konfigurationsseite für dieses Modul ist bewusst einfach gehalten, da seine Kernfunktion unkompliziert ist.

**Bildschirmname:** Sprach-ISO-Code aus URLs entfernen Konfiguration
**Menüpfad:** Back Office > Module > Modul-Manager > Sprach-ISO-Code aus URLs entfernen > Konfigurieren

Auf diesem Bildschirm finden Sie typischerweise eine einzige, entscheidende Einstellung:

- **Einstellungsname:** Modul aktivieren / deaktivieren
  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für die Funktionalität des Moduls. Er steuert, ob das Modul den Sprach-ISO-Code aktiv aus den URLs Ihrer Standardsprache entfernt oder nicht.
  - **Auswirkung der Änderung dieser Einstellung:**
    - **Wenn aktiviert (JA):** Das Modul wird aktiv. Für die Standardsprache Ihres Shops wird der Sprach-ISO-Code (z.B. `/de/`, wenn Deutsch Standard ist) aus allen generierten URLs entfernt. URLs für andere Sprachen bleiben unverändert.
    - **Wenn deaktiviert (NEIN):** Das Modul ist inaktiv. Alle URLs, einschließlich derer für Ihre Standardsprache, zeigen weiterhin den Sprach-ISO-Code an (z.B. `/de/`, `/fr/`).
  - **Empfohlener Wert:** **JA**. Der Hauptzweck der Installation dieses Moduls ist die Nutzung seiner Funktionalität, daher ist die Aktivierung die Standardempfehlung.
  - **Händlerszenario / Beispiel:**
    - Sie haben das Modul gerade installiert und möchten, dass Ihre deutschen (Standard-)URLs wie `www.ihrshop.com/mein-produkt` aussehen. Sie würden dies auf **JA** setzen.
    - Wenn Sie später entscheiden, dass Sie den Sprach-ISO-Code aus irgendeinem Grund in allen URLs beibehalten möchten (z.B. eine Änderung der spezifischen SEO-Strategie), könnten Sie dies auf **NEIN** setzen, um das Verhalten rückgängig zu machen, ohne das Modul zu deinstallieren.

**Wichtiger Hinweis nach der Konfiguration:**
Nach dem Aktivieren oder Deaktivieren des Moduls wird dringend empfohlen:

1. **Leeren Sie Ihren PrestaShop-Cache:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“.
2. **Generieren Sie Ihre `.htaccess`-Datei neu:** Gehen Sie zu **Shop-Parameter > Traffic & SEO**, scrollen Sie zum Abschnitt „URLs einrichten“ und klicken Sie auf „Speichern“ (auch wenn Sie nichts ändern). Dies stellt sicher, dass die URL-Rewrite-Regeln korrekt aktualisiert werden.
3. **Testen Sie Ihre URLs:** Durchsuchen Sie Ihren Shop in Ihrer Standardsprache und überprüfen Sie, ob der Sprach-ISO-Code tatsächlich aus den URLs entfernt wurde. Testen Sie auch andere Sprachen, um sicherzustellen, dass deren URLs weiterhin den ISO-Code enthalten.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren / deaktivieren | JA | Steuert, ob das Modul den Sprach-ISO-Code aus den URLs der Standardsprache entfernt. **JA** für sauberere URLs, **NEIN**, um ISO-Codes für alle Sprachen beizubehalten. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul aktiviert, aber der Sprach-ISO-Code wird immer noch in meinen Standardsprachen-URLs angezeigt. Was soll ich tun?**
A: Dies ist normalerweise ein Caching-Problem oder die `.htaccess`-Datei wurde nicht neu generiert.
1. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.
2. Gehen Sie zu **Shop-Parameter > Traffic & SEO**, scrollen Sie zu „URLs einrichten“ und klicken Sie auf „Speichern“.
3. Überprüfen Sie auch Ihren Browser-Cache oder versuchen Sie, in einem Inkognito-/privaten Fenster zu surfen.

**F: Beeinflusst dieses Modul meine URLs in Nicht-Standardsprachen?**
A: Nein, das Modul ist speziell darauf ausgelegt, den Sprach-ISO-Code nur für Ihre *Standardsprache* zu entfernen. Alle anderen Sprachversionen zeigen weiterhin ihre jeweiligen ISO-Codes an (z.B. `/fr/`, `/de/`).

**F: Wird dieses Modul mein bestehendes SEO beeinträchtigen oder 404-Fehler für alte URLs verursachen?**
A: Das Modul funktioniert, indem es die Kern-URL-Generierung und -Verteilung von PrestaShop überschreibt. Es sollte Weiterleitungen intern handhaben. Für maximale Sicherheit, insbesondere bei etablierten Shops, ist es jedoch immer eine gute Idee:
1. **Sichern Sie Ihre Datenbank und Dateien** vor der Installation.
2. **Testen Sie gründlich** zuerst in einer Staging-Umgebung.
3. Überwachen Sie nach der Aktivierung Ihre Server-Zugriffsprotokolle und die Google Search Console auf 404-Fehler. Sollten Sie welche finden, müssen Sie möglicherweise manuell 301-Weiterleitungen für bestimmte alte URLs zu ihren neuen, saubereren Versionen in Ihrer `.htaccess`-Datei hinzufügen, obwohl dies bei diesem Modul selten erforderlich ist.

**F: Mein benutzerdefiniertes Theme hat nach der Installation des Moduls einige Probleme. Was könnte falsch sein?**
A: Dieses Modul beeinflusst hauptsächlich die URL-Generierung und das Routing, nicht die visuelle Anzeige. Es ist unwahrscheinlich, dass es direkt Theme-Probleme verursacht. Wenn Ihr Theme jedoch sehr spezifische, fest codierte URL-Strukturen hat oder auf JavaScript angewiesen ist, das URLs auf ungewöhnliche Weise parst, besteht eine sehr geringe Konfliktwahrscheinlichkeit.
\* Leeren Sie zuerst Ihren Smarty-Cache (**Erweiterte Einstellungen > Leistung**).
\* Wenn das Problem weiterhin besteht, deaktivieren Sie das Modul vorübergehend, um zu sehen, ob das Problem verschwindet. Wenn ja, wenden Sie sich mit den Details des Problems an den MyPresta.eu-Support.

**F: Unterstützt dieses Modul alle in PrestaShop installierten Sprachen?**
A: Ja, es unterstützt alle Sprachen. Es identifiziert Ihre *Standardsprache* und entfernt deren ISO-Code, während die ISO-Codes für alle anderen installierten Sprachen intakt bleiben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Übersicht)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Implementierung des Moduls „Sprach-ISO-Code aus URLs entfernen“, der für Entwickler, Webmaster und technische Agenturen bestimmt ist.

### 4.1 Architekturübersicht

Das Modul „Sprach-ISO-Code aus URLs entfernen“ erreicht seine Funktionalität durch das Überschreiben von PrestaShop-Kernklassen, die für die URL-Generierung (`Link`) und die URL-Verteilung (`Dispatcher`) verantwortlich sind. Dies ermöglicht es, abzufangen und zu modifizieren, wie URLs von PrestaShop konstruiert und interpretiert werden, wobei speziell die Entfernung des Sprach-ISO-Codes für die Standardsprache angestrebt wird. Es nutzt das PrestaShop-Override-System, um seine benutzerdefinierte Logik einzuschleusen, ohne Kerndateien direkt zu modifizieren.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Logik wird hauptsächlich durch Klassen-Overrides implementiert.

### 4.3 Kernklassen & Modelle (`classes/`)

Die Kernfunktionalität des Moduls liegt in seinen Klassen-Overrides. Diese Dateien werden in `removeiso/override/classes/` platziert, um sicherzustellen, dass das PrestaShop-Override-System sie aufnimmt.

- **`removeiso/override/classes/Dispatcher.php`**
  - **Klassenname:** `Dispatcher` (überschreibt PrestaShops Kernklasse `Dispatcher`)
  - **Elternklasse:** `DispatcherCore`
  - **Verantwortlichkeit:** Dieser Override ist entscheidend dafür, wie PrestaShop eingehende URLs *interpretiert*. Er modifiziert die Methode `dispatch()` (oder eine verwandte Methode), um Anfragen, die den Standard-Sprach-ISO-Code nicht mehr enthalten, korrekt weiterzuleiten. Wenn eine URL wie `www.ihrshop.com/mein-produkt` eingeht, stellt dieser überschriebene `Dispatcher` sicher, dass PrestaShop versteht, dass sie zur Standardsprache gehört, auch ohne das Segment `/de/`. Er handhabt wahrscheinlich auch die Logik, um sicherzustellen, dass, wenn der Standard-Sprach-ISO *vorhanden* ist (z.B. `www.ihrshop.com/de/mein-produkt`), auf die sauberere URL umgeleitet wird.
- **`removeiso/override/classes/Link.php`**
  - **Klassenname:** `Link` (überschreibt PrestaShops Kernklasse `Link`)
  - **Elternklasse:** `LinkCore`
  - **Verantwortlichkeit:** Dieser Override ist dafür verantwortlich, wie PrestaShop ausgehende URLs *generiert*. Er modifiziert Methoden wie `getLanguageLink()`, `getProductLink()`, `getCategoryLink()` usw., um die Aufnahme des Sprach-ISO-Codes zu verhindern, wenn die Zielsprache die Standardsprache des Shops ist. Dies stellt sicher, dass alle von PrestaShop generierten Links (z.B. in Templates, Modulen) für die Standardsprache sauber sind.
- **`removeiso/override/classes/Tools.php`**
  - **Klassenname:** `Tools` (überschreibt PrestaShops Kernklasse `Tools`)
  - **Elternklasse:** `ToolsCore`
  - **Verantwortlichkeit:** Die Klasse `Tools` enthält viele Hilfsfunktionen. Dieser Override könnte verwendet werden, um die Handhabung bestimmter globaler Parameter oder URL-bezogener Zeichenketten zu modifizieren, möglicherweise in Verbindung mit den `Dispatcher`- und `Link`-Overrides, um Konsistenz bei verschiedenen URL-Manipulationsaufgaben zu gewährleisten. Er könnte beispielsweise beeinflussen, wie `$_SERVER['REQUEST_URI']` interpretiert wird oder wie `Tools::redirect()` sich in bestimmten Szenarien im Zusammenhang mit Sprachcodes verhält.
- **`removeiso/override/classes/index.php`**
  - **Klassenname:** N/A (leere Datei)
  - **Elternklasse:** N/A
  - **Verantwortlichkeit:** Dies ist eine Standard-Sicherheitspraxis in PrestaShop-Modulen, um die Verzeichnisauflistung zu verhindern, wenn die Datei `index.php` direkt aufgerufen wird. Sie enthält keinen ausführbaren Code.

### 4.4 JavaScript-Assets (`views/js/`)

- **`removeiso/views/js/removeiso.js`**
  - **Geltungsbereich:** Back-Office (wahrscheinlich auf der Modulkonfigurationsseite geladen).
  - **Verantwortlichkeit:** Angesichts der Funktion des Moduls ist diese JS-Datei wahrscheinlich minimal. Sie könnte enthalten:
    - Einfache Event-Listener für das Konfigurationsformular (z.B. ein Klick auf die Schaltfläche „Speichern“).
    - AJAX-Aufrufe zum Speichern von Konfigurationseinstellungen, wenn das Formular eine asynchrone Übermittlung verwendet.
    - Grundlegende UI-Verbesserungen oder Validierung für den einzelnen „Aktivieren/Deaktivieren“-Schalter.
    - Es scheint keine Front-Office-Verantwortlichkeiten oder komplexe clientseitige Logik im Zusammenhang mit der URL-Manipulation zu haben, da dies serverseitig durch die PHP-Overrides gehandhabt wird.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul enthält keine benutzerdefinierten CSS-Dateien. Dies deutet darauf hin, dass seine Konfigurationsoberfläche auf dem Standard-Back-Office-Styling von PrestaShop basiert.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`removeiso/views/templates/admin/removeiso.tpl`**
  - **Geltungsbereich:** Admin-Template für die Konfigurationsseite des Moduls.
  - **Verantwortlichkeit:** Dieses Template rendert das Konfigurationsformular des Moduls im PrestaShop Back Office. Es enthält die HTML-Struktur für den Schalter „Modul aktivieren / deaktivieren“ und die Standard-PrestaShop-Formularelemente (z.B. `submit`-Schaltfläche, `alert`-Meldungen). Es wird typischerweise von der Methode `getContent()` der Hauptmodulklasse gerendert.

### 4.7 Datenbankschema & Hooks-Übersicht

- **Datenbanktabellen**:
  - Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Seine Konfigurationseinstellungen (z.B. der „Aktivieren/Deaktivieren“-Status) werden in der Tabelle `ps_configuration` gespeichert, wobei die Schlüssel typischerweise mit `REMOVEISO_` oder ähnlichem präfixiert sind (z.B. `PS_REMOVEISO_ENABLED`).
- **Registrierte Hooks-Tabelle**:
  Dieses Modul registriert sich nicht explizit bei vielen Standard-PrestaShop-Hooks für seine Kernfunktionalität, da sein primärer Mechanismus das Überschreiben von Klassen ist. Die `install()`-Methode des Moduls könnte sich bei `actionModuleInstall` oder `actionModuleUninstall` für die Bereinigung registrieren, aber sein Laufzeitverhalten wird durch die überschriebenen Klassen gesteuert.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert Inhalte im `<head>`-Bereich von Front-Office-Seiten. | Obwohl nicht direkt für die Kern-URL-Logik verwendet, könnte ein Modul hier eingreifen, um JS/CSS zu laden oder erste Prüfungen durchzuführen. (Von diesem Modul nicht direkt für seine Kernfunktion verwendet). |
| `displayRightColumn` / `displayLeftColumn` | Rendert Inhalte in den Seitenleisten. | (Von diesem Modul nicht direkt verwendet). |
| `displayProduct` | Rendert Inhalte auf der Produktseite. | (Von diesem Modul nicht direkt verwendet). |
| `displayFooter` | Rendert Inhalte im Footer-Bereich. | (Von diesem Modul nicht direkt verwendet). |
| `actionDispatcherBefore` | Bevor der Dispatcher die Anfrage verarbeitet. | Die überschriebene `Dispatcher`-Klasse handhabt dies implizit, aber ein Modul könnte diesen Hook auch für Pre-Dispatch-Logik verwenden. |
| `actionDispatcherAfter` | Nachdem der Dispatcher die Anfrage verarbeitet hat. | (Von diesem Modul nicht direkt verwendet). |
| `actionModuleInstall` | Wird ausgeführt, wenn das Modul installiert wird. | Um Setup-Aufgaben wie das Registrieren von Overrides, das Hinzufügen von Konfiguration zu `ps_configuration` durchzuführen. |
| `actionModuleUninstall` | Wird ausgeführt, wenn das Modul deinstalliert wird. | Um Bereinigungsaufgaben wie das Entfernen von Overrides, das Löschen von Konfiguration aus `ps_configuration` durchzuführen. |

Der Kern der Funktionsweise dieses Moduls sind seine Klassen-Overrides, die automatisch vom PrestaShop-Autoloader-System geladen werden, wenn das Modul aktiviert ist, anstatt sich für die Haupt-URL-Manipulation auf explizite Hook-Registrierungen zu verlassen.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Sprach-ISO-Code aus URLs entfernen“ verweisen wir auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.

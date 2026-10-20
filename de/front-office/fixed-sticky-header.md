---
title: "Fixed sticky header - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Fixed sticky header' von MyPresta.eu."
sidebar:
  label: "Fixed sticky header - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Fixed sticky header auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/fixed-sticky-header.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/fixed-sticky-header/)
>
> ---


# Fixed sticky header

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Das Modul funktioniert mit den Standard-Bootstrap- und Classic-Templates sowie mit allen Themes mit ähnlicher Struktur.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager neben dem Modul „Fixed sticky header“ auf „Konfigurieren“. Dies führt Sie zur Hauptkonfigurationsseite des Moduls.

#### Allgemeine Einstellungen

- **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält typischerweise Standardeinstellungen für MyPresta.eu-Module, die sich auf Updates und Support beziehen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Ermöglicht dem Modul, nach verfügbaren Updates von MyPresta.eu zu suchen und möglicherweise Benachrichtigungen in Ihrem Back Office anzuzeigen. Dies stellt sicher, dass Sie immer die neueste, sicherste und funktionsreichste Version des Moduls verwenden.
  - *Wenn deaktiviert:* Das Modul sucht nicht automatisch nach Updates. Sie müssten manuell nach neuen Versionen suchen, indem Sie sich in Ihrem MyPresta.eu-Konto anmelden.
- **Empfohlener Wert:** **JA** (oder aktiviert). Es wird dringend empfohlen, diese Einstellung aktiv zu lassen, um sicherzustellen, dass Sie zeitnahe Updates und Fehlerbehebungen erhalten, die für die Sicherheit und Kompatibilität mit zukünftigen PrestaShop-Versionen entscheidend sind.
- **Händlerszenario / Beispiel:** Sie möchten benachrichtigt werden, wenn eine neue Version des Moduls veröffentlicht wird, die einen Fehler behebt oder eine neue Funktion hinzufügt. Wenn diese Einstellung aktiviert ist, sind Sie immer informiert.

#### Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfigurationsseite | Update-Prüfungen (mypresta\_updates, update\_, updatev\_) | Aktiviert | Ermöglicht dem Modul, nach verfügbaren Updates von MyPresta.eu zu suchen und Sie darüber zu benachrichtigen, um sicherzustellen, dass Sie die neuesten Funktionen und Sicherheitskorrekturen erhalten. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der Header bleibt nicht kleben oder überlappt andere Elemente. Was soll ich tun?**
A1: Dies geschieht oft aufgrund von Konflikten mit dem CSS oder JavaScript Ihres Themes, insbesondere wenn Ihr Theme eine sehr individuelle Header-Struktur hat.
\* **Cache leeren:** Versuchen Sie zunächst, Ihren PrestaShop-Cache zu leeren. Gehen Sie zu **Erweiterte Einstellungen > Performance** und klicken Sie oben rechts auf „Cache leeren“.
\* **Theme-Kompatibilität:** Das Modul ist so konzipiert, dass es mit Standard-PrestaShop-Themes (wie Classic) und Themes mit ähnlichen Strukturen funktioniert. Wenn Sie ein stark angepasstes Theme haben, sind möglicherweise geringfügige CSS-Anpassungen erforderlich.
\* **Support kontaktieren:** Wenn das Problem weiterhin besteht, sammeln Sie Screenshots und Details zu Ihrem Theme und kontaktieren Sie den MyPresta.eu-Support. Sie können bei der Diagnose helfen und bei Bedarf benutzerdefinierte CSS-Snippets bereitstellen.

**F2: Mein Header sieht seltsam aus oder hat zusätzlichen Platz, wenn er klebrig wird.**
A2: Dies kann ein Styling-Problem sein.
\* **Element untersuchen:** Verwenden Sie die Entwicklertools Ihres Browsers (klicken Sie mit der rechten Maustaste auf Ihren Header und wählen Sie „Untersuchen“), um zu sehen, welche CSS-Regeln angewendet werden. Suchen Sie nach `position: fixed;` und `top: 0;`.
\* **Theme-Styling:** Ihr Theme könnte spezifische Padding- oder Margin-Regeln haben, die in Konflikt stehen. Möglicherweise müssen Sie benutzerdefiniertes CSS hinzufügen, um das Aussehen des Sticky Headers anzupassen. Der MyPresta.eu-Support kann Sie dabei unterstützen.

**F3: Wird dieses Modul meine Website verlangsamen?**
A3: Das Modul „Fixed sticky header“ ist sehr leichtgewichtig und verwendet minimales JavaScript und CSS. Es sollte einen vernachlässigbaren Einfluss auf die Ladezeit und Leistung Ihrer Website haben. Der Effekt wird nur beim Scrollen aktiviert, sodass er keine zusätzliche Last beim anfänglichen Seitenaufbau verursacht.

**F4: Wie übersetze ich das Modul, falls es sichtbaren Text hätte?**
A4: Obwohl dieses Modul hauptsächlich einen visuellen Effekt bietet und normalerweise keinen benutzerseitigen Text enthält, würden Sie ihn, falls eine zukünftige Version konfigurierbaren Text einführt, über Folgendes übersetzen:
\* **International > Übersetzungen** in Ihrem PrestaShop Back Office.
\* Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Fixed sticky header“ aus dem Modul-Dropdown.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Fixed sticky header“ ist ein leichtgewichtiges Front-Office-Feature-Modul, das die Benutzererfahrung durch einen klebrigen Header beim Scrollen verbessern soll. Es nutzt hauptsächlich JavaScript, um Scroll-Ereignisse zu erkennen und CSS-Klassen auf das Header-Element anzuwenden, was dann das `position: fixed`-Styling auslöst. Es folgt der Standard-PrestaShop-Modulstruktur und verwendet den `displayHeader`-Hook, um seine Assets zu injizieren.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Die Funktionalität des Moduls wird vollständig über JavaScript abgewickelt, das über einen Hook injiziert wird.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration wird direkt in der `getContent()`-Methode der Hauptmoduldatei verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

- Es werden keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen verwendet. Das Modul arbeitet durch Manipulation vorhandener DOM-Elemente.

### 4.4 JavaScript-Assets (`views/js/`)

- **`fixedheader/fixedheader.js`**
  - **Umfang:** Front-Office.
  - **Zweck:** Dieses Skript ist für die Kernfunktionalität des Sticky Headers verantwortlich.
  - **Details:**
    - Es lauscht auf das `scroll`-Ereignis des `window`-Objekts.
    - Es bestimmt die Scroll-Position und den anfänglichen Offset des Header-Elements.
    - Wenn der Benutzer über einen bestimmten Schwellenwert (die anfängliche Höhe des Headers) hinaus scrollt, fügt es dem Haupt-Header-Container eine spezifische CSS-Klasse hinzu (z. B. `fixed-header-active` oder ähnlich, wie in `fixedheader.css` definiert).
    - Wenn der Benutzer wieder über den Schwellenwert nach oben scrollt, entfernt es diese Klasse.
    - Es zielt wahrscheinlich auf einen gemeinsamen Header-Selektor ab (z. B. `#header`, `.header-container` oder ähnlich, abhängig von der Theme-Struktur), um das Sticky-Verhalten anzuwenden.
    - Es kann auch das Hinzufügen eines `padding-top` zum `body` oder einem Hauptinhalts-Wrapper handhaben, um zu verhindern, dass Inhalte „springen“ oder hinter dem fixierten Header verborgen werden.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`fixedheader/fixedheader.css`**
  - **Umfang:** Front-Office-Kunden-Styling.
  - **Zweck:** Bietet die notwendigen CSS-Regeln, um den Header klebrig zu machen, wenn das JavaScript die Aktivierungsklasse hinzufügt.
  - **Details:**
    - Es definiert Stile für den aktiven Sticky-Header-Zustand. Wichtige Eigenschaften sind:
      - `position: fixed;`
      - `top: 0;`
      - `width: 100%;`
      - `z-index: 1000;` (oder ein hoher Wert, um sicherzustellen, dass es über anderen Inhalten bleibt).
      - Potenziell `box-shadow` oder `background-color`, um den Sticky Header visuell zu unterscheiden.
    - Es kann auch Regeln zur Behandlung des `body`-Padding oder -Margin enthalten, um Inhaltsüberlappungen zu vermeiden.
    - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Die primäre Klasse, die vom JS hinzugefügt wird (z. B. `.fixed-header-active` oder ähnlich) und der Selektor für das Header-Element selbst (z. B. `#header`, `.header-container`). Entwickler können diese Stile in ihrem benutzerdefinierten CSS des Themes überschreiben, um sie an ihr Design anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- Es werden keine benutzerdefinierten `.tpl`-Dateien verwendet. Das Modul injiziert sein JavaScript und CSS direkt in den `<head>`-Bereich über den `displayHeader`-Hook.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Es werden keine benutzerdefinierten Datenbanktabellen erstellt. Die Konfiguration wird in `ps_configuration` unter Verwendung von Schlüsseln wie `MYPRESTA_UPDATES`, `UPDATE_FIXEDHEADER`, `UPDATEV_FIXEDHEADER` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Injiziert die CSS- (`fixedheader.css`) und JavaScript- (`fixedheader.js`) Dateien des Moduls in die Seite, um sicherzustellen, dass sie vor dem Rendern des Seiteninhalts geladen werden und sofort zur Ausführung verfügbar sind. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und die neuesten Versionen des Moduls „Fixed sticky header“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.

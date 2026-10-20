---
title: "Material Icons + Font Awesome - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Material Icons + Font Awesome von MyPresta.eu."
sidebar:
  label: "Material Icons + Font Awesome - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Material Icons + Font Awesome auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/material-icons-font-awesome.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/material-icons-font-awesome/)
>
> ---


# Material Icons + Font Awesome

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Keine besonderen Anforderungen über eine Standard-PrestaShop-Hosting-Umgebung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Material Icons + Font Awesome“. Sie finden ihn, indem Sie zu **Module > Modul-Manager** navigieren, nach „Material Icons + Font Awesome“ suchen und auf „Konfigurieren“ klicken.

#### **Font Awesome hinzufügen**

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob die Font Awesome Icon-Bibliothek in das Front-Office Ihres Shops (was Kunden sehen) und das Back-Office (Ihr Admin-Panel) geladen wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Die Font Awesome CSS-Datei wird dem `<head>`-Bereich Ihrer Website hinzugefügt, wodurch alle Font Awesome Icons zur Verfügung stehen. Dies behebt alle fehlenden Font Awesome Icons.
  - *Wenn deaktiviert:* Die Font Awesome CSS-Datei wird von diesem Modul NICHT geladen. Wenn Ihr Theme oder ein anderes Modul bereits Font Awesome lädt oder wenn Sie es nicht benötigen, können Sie dies deaktivieren, um ein doppeltes Laden zu vermeiden.
- **Empfohlener Wert:**
  - **Aktiviert**, wenn Sie fehlende Font Awesome Icons in Ihrem Shop oder im Back-Office bemerken oder wenn Sie Font Awesome Icons in Ihrem Inhalt verwenden möchten.
  - **Deaktiviert**, wenn alle Font Awesome Icons bereits korrekt angezeigt werden (was bedeutet, dass Ihr Theme oder ein anderes Modul es bereits lädt), um redundantes Laden zu verhindern.
- **Händlerszenario / Beispiel:** Sie haben ein neues Zahlungsmodul installiert, und dessen Zahlungsmethoden-Icons (z. B. ein Kreditkartensymbol) werden als leere Kästchen angezeigt. Wenn diese Icons auf Font Awesome basieren, werden sie durch Aktivieren dieser Einstellung korrekt angezeigt.

#### **Material Icons hinzufügen**

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob die Material Icons Bibliothek (von Google) in das Front-Office und Back-Office Ihres Shops geladen wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Die Material Icons CSS-Datei wird dem `<head>`-Bereich Ihrer Website hinzugefügt, wodurch alle Material Icons zur Verfügung stehen. Dies behebt alle fehlenden Material Icons.
  - *Wenn deaktiviert:* Die Material Icons CSS-Datei wird von diesem Modul NICHT geladen. Wenn Ihr Theme oder ein anderes Modul bereits Material Icons lädt oder wenn Sie sie nicht benötigen, können Sie dies deaktivieren.
- **Empfohlener Wert:**
  - **Aktiviert**, wenn Sie fehlende Material Icons in Ihrem Shop oder im Back-Office bemerken.
  - **Deaktiviert**, wenn alle Material Icons bereits korrekt angezeigt werden (was bedeutet, dass Ihr Theme oder ein anderes Modul es bereits lädt), um redundantes Laden zu verhindern.
- **Händlerszenario / Beispiel:** Ihr Theme verwendet Material Icons für seine Navigationspfeile oder einige Produktseitenelemente, aber nach einem Theme-Update sind sie verschwunden. Durch Aktivieren dieser Einstellung werden sie wahrscheinlich wieder angezeigt.

#### **Kurzübersichtstabelle der Konfiguration**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Font Awesome hinzufügen | Aktiviert (falls benötigt) | Lädt die Font Awesome Icon-Bibliothek für Front- und Back-Office. Behebt fehlende Font Awesome Icons. |
| Modulkonfiguration | Material Icons hinzufügen | Aktiviert (falls benötigt) | Lädt die Material Icons Bibliothek für Front- und Back-Office. Behebt fehlende Material Icons. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe die Einstellungen aktiviert, aber Icons fehlen immer noch. Was soll ich tun?**
A: Leeren Sie zuerst Ihren PrestaShop-Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Leeren Sie auch den Cache Ihres Browsers (Strg+F5 oder Cmd+Umschalt+R). Wenn Icons immer noch fehlen, ist es möglich, dass die gesuchten Icons zu einer anderen Icon-Bibliothek gehören, die nicht von diesem Modul abgedeckt wird, oder es gibt einen CSS-Konflikt in Ihrem Theme.

**F: Wird dieses Modul meine Website verlangsamen?**
A: Das Modul lädt Standard-CSS-Dateien für die Icon-Bibliotheken. Wenn Sie nur die benötigten Bibliotheken aktivieren und diese nicht bereits von Ihrem Theme geladen werden, ist der Leistungseinfluss minimal und für die korrekte Anzeige notwendig. Wenn Sie eine Bibliothek aktivieren, die bereits von Ihrem Theme geladen wird, laden Sie sie zweimal, was zu einer leichten Verlangsamung führen kann. Überprüfen Sie immer, ob Ihr Theme diese Bibliotheken bereits enthält, bevor Sie sie hier aktivieren.

**F: Mein benutzerdefiniertes Theme hat einen eigenen Icon-Satz. Wird dieses Modul stören?**
A: Es sollte nicht direkt stören. Dieses Modul fügt die angegebenen Icon-Bibliotheken hinzu. Wenn Ihr Theme einen anderen Icon-Satz verwendet (z. B. benutzerdefinierte SVGs oder eine andere Schriftart-Icon-Bibliothek), fügt dieses Modul einfach Font Awesome und/oder Material Icons daneben hinzu. Wenn Sie Konflikte feststellen, können Sie versuchen, eine oder beide Optionen im Modul zu deaktivieren, um zu sehen, ob dies das Problem löst.

**F: Woher weiß ich, ob mein Theme bereits Font Awesome oder Material Icons lädt?**
A: Der einfachste Weg ist, mit der rechten Maustaste auf die Seite Ihres Shops (Front-Office) zu klicken und „Seitenquelltext anzeigen“ oder „Element untersuchen“ auszuwählen. Suchen Sie dann im `<head>`-Bereich nach „font-awesome.css“ oder „material-icons.css“. Wenn Sie sie finden, lädt Ihr Theme sie wahrscheinlich bereits. Alternativ, wenn alle Icons ohne dieses Modul korrekt angezeigt werden, dann handhabt Ihr Theme oder ein anderes Modul dies bereits.

**F: Kann ich Font Awesome und Material Icons gleichzeitig verwenden?**
A: Ja, absolut. Sie können beide Optionen in der Modulkonfiguration aktivieren. Dies ist oft notwendig, wenn verschiedene Teile Ihres Shops (z. B. Ihr Theme und ein Drittanbieter-Modul) auf unterschiedliche Icon-Bibliotheken angewiesen sind.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Material Icons + Font Awesome“ ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, externe CSS-Stylesheets für Icon-Bibliotheken zu injizieren. Es folgt einer Standard-PrestaShop-Modulstruktur und nutzt Hooks, um seine Funktionalität in das Front-Office und Back-Office zu integrieren. Es führt keine benutzerdefinierten Controller, Modelle oder Datenbanktabellen ein, sondern konzentriert sich ausschließlich auf die Asset-Verwaltung.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Logik wird innerhalb der Hauptmoduldatei (`fonticons.php`) über Hooks behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Die gesamte Konfiguration wird direkt in `ps_configuration` unter Verwendung der unten definierten Schlüssel gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Die Kernfunktionalität des Moduls basiert auf diesen CSS-Dateien:

- **`fonticons/views/css/font-awesome.css`**:

  - **Geltungsbereich**: Front-Office und Back-Office.
  - **Zweck**: Enthält die CSS-Regeln und `@font-face`-Deklarationen für die Font Awesome Icon-Bibliothek. Diese Datei ist dafür verantwortlich, Font Awesome Icons im gesamten Shop verfügbar zu machen.
  - **Wichtige CSS-Klassenselektoren**: `fa`, `fas`, `far`, `fal`, `fab` (für verschiedene Font Awesome-Stile), gefolgt von spezifischen Icon-Klassen wie `fa-shopping-cart`, `fa-user` usw. Entwickler können diese überschreiben, indem sie diese Klassen im CSS ihres Themes ansprechen.
- **`fonticons/views/css/material-icons.css`**:

  - **Geltungsbereich**: Front-Office und Back-Office.
  - **Zweck**: Enthält die CSS-Regeln und `@font-face`-Deklarationen für die Material Icons Bibliothek von Google. Diese Datei macht Material Icons verfügbar.
  - **Wichtige CSS-Klassenselektoren**: `material-icons`. Icons werden typischerweise gerendert, indem der Ligaturname des Icons in ein Element mit dieser Klasse platziert wird (z. B. `<i class="material-icons">shopping_cart</i>`). Entwickler können das Styling für diese Klasse überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`fonticons/views/advert.tpl`**:
  - **Geltungsbereich**: Back-Office (Modulkonfigurationsseite).
  - **Zweck**: Dieses Template wird verwendet, um eine Werbung oder Werbebotschaft innerhalb der Modulkonfigurationsseite im PrestaShop Back-Office anzuzeigen. Es wird von der Methode `getContent()` gerendert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen in der Standardtabelle `ps_configuration`.

  - `ps_configuration`-Einträge:
    - `fonticons_FA`: Speichert den Status (1 für aktiviert, 0 für deaktiviert) der Font Awesome-Einbindung für das Front-Office.
    - `fonticons_MI`: Speichert den Status (1 für aktiviert, 0 für deaktiviert) der Material Icons-Einbindung für das Front-Office.
    - `BO_fonticons_FA`: Speichert den Status (1 für aktiviert, 0 für deaktiviert) der Font Awesome-Einbindung für das Back-Office.
    - `BO_fonticons_MI`: Speichert den Status (1 für aktiviert, 0 für deaktiviert) der Material Icons-Einbindung für das Back-Office.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Front-Office-Seite ausgeführt. | Wird verwendet, um die CSS-Dateien von Font Awesome und/oder Material Icons für den kundenorientierten Teil des Shops zu laden, basierend auf der Konfiguration von `fonticons_FA` und `fonticons_MI`. |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein AdminController seine Medien-Assets (CSS/JS) festlegt. | Wird verwendet, um die CSS-Dateien von Font Awesome und/oder Material Icons für das PrestaShop Back-Office zu laden, basierend auf der Konfiguration von `BO_fonticons_FA` und `BO_fonticons_MI`. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Dort finden Sie Ihre gekauften Module und Download-Links. Für technische Unterstützung oder Fragen nutzen Sie bitte die auf MyPresta.eu bereitgestellten Support-Kanäle.

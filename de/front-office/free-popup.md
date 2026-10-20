---
title: "Free PopUp - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Free PopUp von MyPresta.eu."
sidebar:
  label: "Free PopUp - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Free PopUp auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/free-popup.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/free-popup/)
>
> ---


# Free PopUp

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Free PopUp-Modul. Hier finden Sie alle Einstellungen, um den Inhalt und das Verhalten Ihres Pop-ups zu steuern.

#### **1. Pop-up aktivieren / deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für Ihr Pop-up.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Pop-up wird in Ihrem Front Office gemäß Ihren anderen Einstellungen angezeigt.
  - *Wenn deaktiviert (NEIN):* Das Pop-up wird in Ihrem Front Office nicht angezeigt, unabhängig von anderen Einstellungen.
- **Empfohlener Wert:** JA (wenn Sie das Pop-up aktiv haben möchten), NEIN (wenn Sie es vorübergehend ausblenden möchten).
- **Händlerszenario / Beispiel:** Aktivieren Sie es, wenn eine neue Aktion läuft. Deaktivieren Sie es während der Wartung oder wenn Sie vorübergehend eine andere Kampagne durchführen möchten.

#### **2. Pop-up-Inhalt**

- **Was diese Einstellung bewirkt:** Hier geben Sie die eigentliche Nachricht, das Angebot oder die Informationen ein, die Sie im Pop-up anzeigen möchten. Es verwendet einen Rich-Text-Editor (TinyMCE), mit dem Sie Text formatieren, Bilder, Links und mehr hinzufügen können.
- **Auswirkung der Änderung dieser Einstellung:** Was Sie hier eingeben und formatieren, wird direkt Ihren Kunden im Pop-up-Fenster angezeigt.
- **Empfohlener Wert:** Ihre spezifische Werbebotschaft, Ihr Willkommenstext oder Ihre wichtige Ankündigung.
- **Händlerszenario / Beispiel:** „Willkommen in unserem Shop! Verwenden Sie den Code WELCOME10 für 10 % Rabatt auf Ihre erste Bestellung!“ oder „Kostenloser Versand für alle Bestellungen über 50 € diese Woche!“ Sie können auch ein Bild eines neuen Produkts oder ein Markenlogo hinzufügen.

#### **3. Cookie-Ablauf (Tage)**

- **Was diese Einstellung bewirkt:** Dies bestimmt, wie lange das Pop-up ausgeblendet bleibt, nachdem ein Kunde es geschlossen hat. Es wird ein Cookie im Browser des Kunden gesetzt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf 0 gesetzt:* Das Pop-up wird bei *jedem* Seitenaufruf angezeigt, selbst wenn der Kunde es gerade geschlossen hat. Dies wird im Allgemeinen nicht empfohlen, da es störend sein kann.
  - *Wenn auf eine positive Zahl gesetzt (z.B. 7):* Das Pop-up wird beim ersten Besuch angezeigt. Nach dem Schließen wird es für die nächsten 7 Tage für diesen spezifischen Kunden in diesem spezifischen Browser nicht erneut angezeigt.
- **Empfohlener Wert:** 7 (für wöchentliche Aktionen), 30 (für monatliche Willkommensnachrichten) oder 1 (wenn es täglich wieder erscheinen soll).
- **Händlerszenario / Beispiel:** Wenn Sie eine allgemeine Willkommensnachricht haben, ist eine Einstellung von 30 Tagen gut. Wenn Sie einen wöchentlichen Verkauf durchführen, stellen 7 Tage sicher, dass Kunden das neue Angebot nächste Woche sehen.

#### **4. Testmodus**

- **Was diese Einstellung bewirkt:** Dies ermöglicht Ihnen, das Erscheinungsbild und den Inhalt Ihres Pop-ups zu testen, ohne auf den Cookie-Ablauf warten zu müssen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Pop-up wird bei jeder Seitenaktualisierung angezeigt, selbst wenn Sie es gerade geschlossen haben. Dies überschreibt die Einstellung „Cookie-Ablauf“ zu Testzwecken.
  - *Wenn deaktiviert (NEIN):* Das Pop-up verhält sich normal und berücksichtigt die Einstellung „Cookie-Ablauf“.
- **Empfohlener Wert:** JA (während Sie das Pop-up einrichten und anpassen), NEIN (sobald Sie mit der Einrichtung zufrieden sind und möchten, dass es für Kunden normal funktioniert).
- **Händlerszenario / Beispiel:** Sie haben gerade Ihren Pop-up-Inhalt aktualisiert und möchten sofort sehen, wie er im Front Office aussieht. Aktivieren Sie den Testmodus, aktualisieren Sie Ihre Shop-Seite, und das Pop-up wird angezeigt. Sobald Sie zufrieden sind, deaktivieren Sie den Testmodus.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Pop-up aktivieren / deaktivieren | JA | Hauptschalter zum Anzeigen oder Ausblenden des Pop-ups in Ihrem Shop. |
| Modulkonfigurationsseite | Pop-up-Inhalt | Ihre Nachricht | Der eigentliche Text, Bilder und Links, die im Pop-up angezeigt werden. |
| Modulkonfigurationsseite | Cookie-Ablauf (Tage) | 7 | Wie viele Tage das Pop-up ausgeblendet bleibt, nachdem ein Kunde es geschlossen hat. |
| Modulkonfigurationsseite | Testmodus | NEIN | Erzwingt die Anzeige des Pop-ups bei jeder Aktualisierung zu Testzwecken. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein Pop-up wird im Front Office nicht angezeigt, selbst nachdem ich es aktiviert habe.**

- **A:** Überprüfen Sie zunächst, ob „Pop-up aktivieren / deaktivieren“ auf JA eingestellt ist. Wenn ja, versuchen Sie, den „Testmodus“ zu aktivieren, um zu sehen, ob es erscheint. Wenn es immer noch nicht angezeigt wird, leeren Sie Ihren Browser-Cache und den Smarty-Cache von PrestaShop (Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie dann oben rechts auf „Cache leeren“). Stellen Sie außerdem sicher, dass Sie Ihre Konfiguration nach Änderungen gespeichert haben.

**F2: Das Pop-up erschien einmal, aber jetzt wird es nicht mehr angezeigt.**

- **A:** Dies ist ein normales Verhalten aufgrund der Einstellung „Cookie-Ablauf“. Das Modul setzt ein Cookie in Ihrem Browser, um zu verhindern, dass das Pop-up für die angegebene Anzahl von Tagen erneut erscheint. Um es zu Testzwecken zu erzwingen, aktivieren Sie den „Testmodus“ in der Modulkonfiguration. Um es als neuer Besucher zu sehen, löschen Sie die Cookies Ihres Browsers für die Domain Ihres Shops oder verwenden Sie ein Inkognito-/privates Browserfenster.

**F3: Wie kann ich das Aussehen des Pop-ups ändern (Farben, Schriftarten usw.)?**

- **A:** Das Modul bietet ein einfaches weißes Modal mit einem 70%igen Overlay. Für fortgeschrittenes Styling benötigen Sie benutzerdefiniertes CSS. Dies wird typischerweise von einem Webentwickler gehandhabt. Sie können benutzerdefiniertes CSS in die `custom.css`-Datei Ihres Themes einfügen oder direkt die `front.css` des Moduls bearbeiten (obwohl letzteres nicht empfohlen wird, da Updates es überschreiben würden).

**F4: Kann ich verschiedene Pop-ups für verschiedene Seiten oder Kundengruppen haben?**

- **A:** Das Free PopUp-Modul ist für eine einzige, shopweite Kampagne konzipiert. Es zeigt allen Besuchern den gleichen Inhalt an. Für fortgeschrittenere, gezielte Pop-ups benötigen Sie ein funktionsreicheres (und wahrscheinlich kostenpflichtiges) Pop-up-Modul.

**F5: Meine Bilder oder Links im Pop-up-Inhalt funktionieren nicht richtig.**

- **A:** Stellen Sie sicher, dass Sie vollständige, absolute URLs für Bilder und Links verwenden (z.B. `https://ihrshop.com/img/ihrbild.jpg` anstelle von `/img/ihrbild.jpg`). Der TinyMCE-Editor sollte dies automatisch handhaben, aber manchmal treten Probleme auf, wenn Sie Inhalte aus externen Quellen kopieren und einfügen. Überprüfen Sie den HTML-Quellcode, wenn Sie damit vertraut sind.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Free PopUp-Modul ist ein unkompliziertes PrestaShop-Modul, das einem grundlegenden MVC-Muster folgt. Es verwendet hauptsächlich die `Module`-Klasse für seine Kernfunktionalität, Konfigurationsverwaltung und Hook-Registrierung. Die Front-Office-Anzeige wird durch ein einzelnes Template verwaltet, das über einen Hook gerendert wird, und sein Verhalten wird durch eine einfache JavaScript-Datei gesteuert. Das Styling wird durch dedizierte CSS-Dateien für das Admin- und Front-Office übernommen.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmodulklasse gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen. Alle Konfigurationsdaten werden direkt in der `ps_configuration`-Tabelle von PrestaShop unter Verwendung der Standardmethoden `Configuration::get()` und `Configuration::updateValue()` gespeichert.

### 4.4 JavaScript-Assets (`views/js/`)

- **`myfreepopup/js/front.js`**
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Dieses Skript ist für das clientseitige Verhalten des Pop-ups verantwortlich.
  - **Details:**
    - Es prüft das Vorhandensein eines spezifischen Cookies (`myfreepopup_closed`).
    - Wenn das Cookie nicht gefunden wird (was bedeutet, dass der Benutzer das Pop-up kürzlich nicht geschlossen hat oder es sein erster Besuch ist), zeigt es das Pop-up an, indem es CSS-Eigenschaften manipuliert (z.B. `display: block`).
    - Es fügt einen Event-Listener an den Schließen-Button innerhalb des Pop-ups an.
    - Wenn der Schließen-Button geklickt wird, blendet es das Pop-up aus und setzt das `myfreepopup_closed`-Cookie mit einem Ablaufdatum basierend auf der Modulkonfiguration.
    - Es behandelt auch die Logik des „Testmodus“, um sicherzustellen, dass die Cookie-Prüfung umgangen wird, wenn der Testmodus aktiv ist.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`myfreepopup/css/admin.css`**
  - **Umfang:** Styling des Admin-Formulars im Back-Office.
  - **Details:** Enthält grundlegende Styling-Regeln für die Konfigurationsseite des Moduls im PrestaShop Back Office, um ein konsistentes Erscheinungsbild innerhalb des Admin-Panels zu gewährleisten.
- **`myfreepopup/css/front.css`**
  - **Umfang:** Styling für Kunden im Front-Office.
  - **Details:** Definiert das visuelle Erscheinungsbild des Pop-ups selbst. Dies beinhaltet:
    - Styling für das modale Overlay (z.B. `position: fixed`, `background-color`, `opacity`, `z-index`).
    - Styling für das Haupt-Pop-up-Inhaltsfeld (z.B. `background-color: #fff`, `border`, `box-shadow`, `max-width`, `padding`, `text-align`, `position: fixed`, `top`, `left`, `transform` zur Zentrierung).
    - Styling für den Schließen-Button (z.B. `position: absolute`, `font-size`, `cursor: pointer`).
    - Responsive Anpassungen für verschiedene Bildschirmgrößen mittels Media Queries.
  - **Wichtige CSS-Klassenselektoren zum Überschreiben:** `.myfreepopup_overlay`, `.myfreepopup_content`, `.myfreepopup_close`.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`myfreepopup/views/admin_banner.tpl`**
  - **Umfang:** Admin-Template.
  - **Zweck:** Zeigt ein Werbebanner oder eine Informationsnachricht innerhalb der Konfigurationsseite des Moduls im Back Office an.
- **`myfreepopup/views/admin_locks.tpl`**
  - **Umfang:** Admin-Template.
  - **Zweck:** Wahrscheinlich zur Anzeige von Informationen bezüglich der Modullizenzierung oder zusätzlicher Funktionen, oft mit einem Schloss-Symbol.
- **`myfreepopup/views/front.tpl`**
  - **Umfang:** Front-Office-Hook-Template.
  - **Zweck:** Dies ist das Haupt-Template, das für das Rendern der HTML-Struktur des Pop-ups im Front Office verantwortlich ist.
  - **Gerendert in Hook:** `displayHeader` (oder ähnlicher globaler Hook, wo JS/CSS geladen werden kann).
  - **Inhalt:** Enthält das HTML für das Overlay, das Pop-up-Inhaltsfeld, den Schließen-Button und fügt dynamisch die Variable `{$popup_content}` ein (die aus dem TinyMCE-Editor im Back Office stammt). Es enthält auch die notwendigen JavaScript- und CSS-Dateien.

### 4.7 Datenbank-Schema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der Standardtabelle `ps_configuration` unter Verwendung von Schlüsseln wie `MYFREEPOPUP_ENABLED`, `MYFREEPOPUP_CONTENT`, `MYFREEPOPUP_COOKIE_DAYS`, `MYFREEPOPUP_TEST_MODE`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Front-Office-Seite ausgeführt. | Wird verwendet, um die CSS- und JavaScript-Dateien des Moduls einzubinden und die anfängliche HTML-Struktur des Pop-ups (`front.tpl`) zu rendern, die dann von JavaScript gesteuert wird. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Free PopUp-Modul gerne zur Verfügung.

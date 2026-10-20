---
title: "An einen Freund senden - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „An einen Freund senden“ von MyPresta.eu."
sidebar:
  label: "An einen Freund senden - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Send to a friend auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/send-to-a-friend.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/send-to-a-friend/)
>
> ---


# An einen Freund senden

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für eine PrestaShop-Installation erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „An einen Freund senden“. Hier können Sie steuern, wie sich die Funktion verhält und auf Ihren Produktseiten erscheint.

#### Allgemeine Einstellungen

- **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält die Kerneinstellungen zum Aktivieren oder Deaktivieren des Moduls und zur Steuerung seiner grundlegenden Funktionalität.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Der Link/Button „An einen Freund senden“ und die Funktionalität werden auf Ihren Produktseiten wie konfiguriert angezeigt.
  - *Wenn deaktiviert:* Die Funktion wird vollständig aus Ihrem Shop ausgeblendet, und es können keine E-Mails darüber gesendet werden.
- **Empfohlener Wert:** **JA** (Aktiviert), um Kunden die Nutzung der Funktion zu ermöglichen.
- **Händlerszenario / Beispiel:** Wenn Sie die Funktion vorübergehend für Wartungsarbeiten oder eine bestimmte Marketingkampagne deaktivieren möchten, würden Sie dies auf „NEIN“ stellen. Andernfalls lassen Sie es auf „JA“, um Mundpropaganda-Marketing zu nutzen.

#### Anzeigeoptionen

- **Was diese Einstellung bewirkt:** Diese Optionen steuern, wo der Link oder Button „An einen Freund senden“ auf Ihren Produktseiten angezeigt wird. Das Modul nutzt das Hook-System von PrestaShop, um die Funktion in verschiedenen Bereichen zu platzieren.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Auswahl eines Hooks (z.B. `displayProductButtons`):* Der Link „An einen Freund senden“ wird in diesem spezifischen Bereich Ihrer Produktseite gerendert.
  - *Keine Auswahl eines Hooks:* Die Funktion wird möglicherweise überhaupt nicht angezeigt, oder sie wird an einem Standardort angezeigt, wenn Ihr Theme eine spezifische Fallback-Darstellung hat.
- **Empfohlener Wert:** `displayProductButtons` oder `displayProductActions` sind gängige und empfohlene Hooks, da sie den Link in der Nähe des „In den Warenkorb“-Buttons platzieren und ihn so leicht auffindbar machen. Sie könnten auch `displayFooterProduct` in Betracht ziehen, wenn Sie ihn lieber am Ende der Produktdetails haben möchten.
- **Händlerszenario / Beispiel:** Wenn der Link „An einen Freund senden“ gut sichtbar und in der Nähe des Haupt-Call-to-Action sein soll, wählen Sie `displayProductButtons`. Wenn Sie ihn weniger prominent, vielleicht am Ende der Produktinformationen, platzieren möchten, wählen Sie `displayFooterProduct`. Experimentieren Sie mit verschiedenen Hooks, um zu sehen, was am besten zu Ihrem Theme passt.

#### E-Mail-Vorlage & Inhalt

- **Was diese Einstellung bewirkt:** Dieser Abschnitt ermöglicht es Ihnen, den Betreff und den Inhalt der E-Mail anzupassen, die an den Freund gesendet wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Ändern des Betreffs:* Die E-Mail-Betreffzeile spiegelt Ihren benutzerdefinierten Text wider, wodurch sie ansprechender oder markengerechter wird.
  - *Ändern des Inhalts:* Der E-Mail-Text enthält Ihre benutzerdefinierte Nachricht, sodass Sie die Empfehlung personalisieren können. Sie können Platzhalter wie `{product_name}` und `{product_link}` verwenden, die automatisch durch die tatsächlichen Produktdetails ersetzt werden.
- **Empfohlener Wert:** Verwenden Sie eine klare, einladende Betreffzeile (z.B. „Schauen Sie sich dieses Produkt von {your\_shop\_name} an!“) und eine freundliche, informative Nachricht im Text. Fügen Sie immer `{product_name}` und `{product_link}` ein, um sicherzustellen, dass der Freund weiß, was empfohlen wird und wie er es findet.
- **Händlerszenario / Beispiel:** Sie könnten die E-Mail anpassen, um zu sagen: „Hallo {friend\_name}, {customer\_name} dachte, dieses Produkt von Meinem Super Shop könnte Ihnen gefallen! Es heißt {product\_name} und Sie finden es hier: {product\_link}. Viel Spaß beim Einkaufen!“

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren/deaktivieren | Aktiviert | Steuert, ob die Funktion „An einen Freund senden“ in Ihrem Shop aktiv ist. |
| Modulkonfiguration | Anzeige-Hook | `displayProductButtons` | Bestimmt, wo der Link „An einen Freund senden“ auf Produktseiten erscheint. |
| Modulkonfiguration | E-Mail-Betreff | „Schauen Sie sich dieses Produkt an!“ | Passt die Betreffzeile der an den Freund gesendeten E-Mail an. |
| Modulkonfiguration | E-Mail-Inhalt | „Hallo {friend\_name}, {customer\_name} dachte, dieses Produkt könnte Ihnen gefallen: {product\_name}. Sie finden es hier: {product\_link}“ | Passt den E-Mail-Text an, einschließlich dynamischer Produktdetails. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der Link „An einen Freund senden“ wird auf meinen Produktseiten nicht angezeigt. Was soll ich tun?**
A:

1. **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass das Modul „An einen Freund senden“ installiert und aktiviert ist.
2. **Konfiguration überprüfen:** Gehen Sie zur Konfigurationsseite des Moduls und stellen Sie sicher, dass das Modul „Aktiviert“ ist und Sie mindestens einen „Anzeige-Hook“ (z.B. `displayProductButtons`) ausgewählt haben.
3. **Cache leeren:** PrestaShop speichert Inhalte oft im Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
4. **Theme-Kompatibilität:** Wenn Sie ein benutzerdefiniertes Theme verwenden, ist es möglicherweise nicht explizit darauf ausgelegt, alle PrestaShop-Hooks zu rendern. Versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme zu wechseln, um zu sehen, ob der Link angezeigt wird. Wenn ja, erfordert Ihr Theme möglicherweise eine kleine Änderung durch einen Webmaster, um den ausgewählten Hook anzuzeigen.

**F: Meine Kunden senden E-Mails, aber diese werden von ihren Freunden nicht empfangen.**
A:

1. **Spam-Ordner überprüfen:** Bitten Sie den Freund, seinen Spam- oder Junk-Mail-Ordner zu überprüfen.
2. **E-Mail-Einstellungen überprüfen:** Stellen Sie sicher, dass die E-Mail-Einstellungen Ihres PrestaShop-Shops unter **Erweiterte Einstellungen > E-Mail** korrekt konfiguriert sind. Testen Sie das Senden einer allgemeinen E-Mail von PrestaShop, um zu bestätigen, dass Ihr Mailserver funktioniert.
3. **Modulprotokolle (Entwicklerprüfung):** Ein Entwickler kann die Mail-Protokolle von PrestaShop (falls aktiviert) oder Server-Fehlerprotokolle auf Probleme beim Senden von E-Mails überprüfen.

**F: Kann ich den Text des Links „An einen Freund senden“ oder der Formularfelder ändern?**
A: Ja, Sie können die Textzeichenfolgen (Beschriftungen, Schaltflächentext usw.) des Moduls mit dem PrestaShop-Übersetzungstool übersetzen oder ändern. Gehen Sie zu **International > Übersetzungen**, wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann das Modul „An einen Freund senden“. Sie können dann den gesamten sichtbaren Text bearbeiten.

**F: Das Pop-up-Formular sieht seltsam aus oder ist auf meinem Mobilgerät nicht korrekt formatiert.**
A:

1. **Browser-Cache leeren:** Bitten Sie den Kunden, den Browser-Cache auf seinem Mobilgerät zu leeren.
2. **Theme-Konflikte:** Benutzerdefinierte Themes können manchmal das Styling von Modulen überschreiben oder damit in Konflikt geraten. Obwohl das Modul sein eigenes CSS (`send2friend.css`) enthält, könnte das CSS Ihres Themes Vorrang haben. Ein Webmaster kann die Seite mit den Browser-Entwicklertools überprüfen, um CSS-Konflikte zu identifizieren und zu beheben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul „An einen Freund senden“ (`send2friend`) ist ein Standard-PrestaShop-Modul, das das MVC-Muster implementiert. Es verwendet hauptsächlich Front-Controller für AJAX-Anfragen, Smarty-Vorlagen für die Formularwiedergabe und Hooks zur Integration in die Produktseite. Es führt keine benutzerdefinierten Datenbanktabellen oder komplexen ObjectModels ein, sondern stützt sich auf die Kern-Mail-Funktionalität von PrestaShop.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- **`controllers/front/AjaxSend.php`**
  - **Klassenname:** `Send2FriendAjaxSendModuleFrontController`
  - **Elternklasse:** `ModuleFrontController`
  - **Verantwortlichkeit:** Dieser Controller verarbeitet die AJAX-Anfrage, die ausgelöst wird, wenn ein Benutzer das Formular „An einen Freund senden“ absendet. Er empfängt den Namen des Absenders, den Namen des Freundes, die E-Mail-Adresse des Freundes und die Produkt-ID. Anschließend erstellt und sendet er die E-Mail mithilfe der `Mail::Send()`-Methode von PrestaShop. Er gibt eine JSON-Antwort zurück, die den Erfolg oder Misserfolg anzeigt.
- **`controllers/front/index.php`**
  - **Klassenname:** `Send2FriendIndexModuleFrontController`
  - **Elternklasse:** `ModuleFrontController`
  - **Verantwortlichkeit:** Dies ist ein Platzhalter oder Standard-Front-Controller. In vielen Modulen könnte dieser eine dedizierte Front-Office-Seite verwalten. Für „An einen Freund senden“ könnte seine Hauptrolle darin bestehen, sicherzustellen, dass die Front-Office-Assets des Moduls geladen werden oder als Basis für andere Front-Controller zu dienen. Angesichts der Funktionalität des Moduls ist der `AjaxSend`-Controller der aktivere.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul enthält keine benutzerdefinierten Klassen oder Modelle im Verzeichnis `classes/`. Es nutzt die Kernfunktionen von PrestaShop, insbesondere `Mail` zum Senden von E-Mails und `Product` zum Abrufen von Produktinformationen.

### 4.4 JavaScript-Assets (`views/js/`)

- **`views/js/send2friend.js`**
  - **Geltungsbereich:** Front-Office.
  - **Details:** Dieses Skript ist für die Front-End-Interaktion der Funktion „An einen Freund senden“ verantwortlich.
    - Es hängt wahrscheinlich einen Event-Listener an den Link/Button „An einen Freund senden“ an, um das Modal zu öffnen oder das Formular anzuzeigen.
    - Es verarbeitet die Formularübermittlung und sammelt Daten (Absendername, Freundesname, Freundes-E-Mail, Produkt-ID).
    - Es sendet eine AJAX-Anfrage an den `AjaxSend.php`-Front-Controller.
    - Es verarbeitet die JSON-Antwort vom Server (Erfolg/Fehler) und gibt dem Benutzer Feedback (z.B. „E-Mail erfolgreich gesendet!“ oder „Fehler beim Senden der E-Mail.“).
    - Es kann Logik zur Formularvalidierung enthalten (z.B. Überprüfung auf gültige E-Mail-Formate).
    - Es verwendet jQuery für DOM-Manipulation und AJAX-Aufrufe, was im PrestaShop-Front-Office üblich ist.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`views/css/send2friend.css`**
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Details:** Dieses Stylesheet bietet das grundlegende visuelle Styling für den Link „An einen Freund senden“, das Pop-up-Modal (falls verwendet) und die Formularfelder darin.
    - Es definiert Stile für den Button/Link, Eingabefelder, Beschriftungen und alle Erfolgs-/Fehlermeldungen.
    - Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können, wären typischerweise Klassen wie `.send2friend-button`, `.send2friend-modal`, `.send2friend-form`, `.send2friend-input` usw. Entwickler können das gerenderte HTML überprüfen, um die genauen verwendeten Klassen zu finden.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **`views/templates/hook/send2friend-extra.tpl`**
  - **Geltungsbereich:** Front-Office.
  - **Hook-Rendering:** Diese Vorlage ist so konzipiert, dass sie in verschiedenen Produktseiten-Hooks (z.B. `displayProductButtons`, `displayProductActions`, `displayFooterProduct`) gerendert wird.
  - **Visueller Block:** Sie gibt die HTML-Struktur für den Link/Button „An einen Freund senden“ und das zugehörige Modal oder Inline-Formular aus. Dies umfasst die Eingabefelder für Namen und E-Mail-Adressen sowie den Absende-Button. Sie enthält auch die notwendigen versteckten Felder (wie `product_id`) und möglicherweise die Struktur zur Anzeige von Erfolgs-/Fehlermeldungen.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul „An einen Freund senden“ erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen (wie aktivierter Status, gewählter Hook, E-Mail-Betreff und -Inhalt) in der `ps_configuration`-Tabelle von PrestaShop.

- **`ps_configuration`**: Speichert Moduleinstellungen mit Schlüsseln, die typischerweise mit `SEND2FRIEND_` beginnen.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird verwendet, um CSS- und JavaScript-Assets des Moduls global zu laden. |
| `displayProductButtons` | In der Nähe des „In den Warenkorb“-Buttons auf Produktseiten. | Häufige Platzierung für den Link „An einen Freund senden“. |
| `displayProductActions` | Ein weiterer häufiger Hook in der Nähe von Produktaktionen. | Alternative Platzierung für den Link „An einen Freund senden“. |
| `displayFooterProduct` | Am Ende des Produktinformationsblocks. | Weniger prominente Platzierung für den Link „An einen Freund senden“. |
| `displayRightColumnProduct` | In der rechten Spalte der Produktseite (falls vom Theme aktiviert). | Mögliche Platzierung für den Link „An einen Freund senden“. |
| `displayLeftColumnProduct` | In der linken Spalte der Produktseite (falls vom Theme aktiviert). | Mögliche Platzierung für den Link „An einen Freund senden“. |

Die `install()`-Methode des Moduls registriert diese Hooks, und die `uninstall()`-Methode hebt deren Registrierung auf. Der vom Händler in der Konfiguration gewählte spezifische Hook bestimmt, welcher aktiv zum Anzeigen der Vorlage verwendet wird.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „An einen Freund senden“ besuchen Sie bitte Ihr MyPresta.eu-Kundenkonto. Sie können die neuesten Versionen herunterladen und direkt über [MyPresta.eu](https://mypresta.eu) auf Support-Ressourcen zugreifen.

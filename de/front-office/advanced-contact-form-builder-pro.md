---
title: "Advanced Contact Form Builder Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Advanced Contact Form Builder Pro von MyPresta.eu."
sidebar:
  label: "Advanced Contact Form Builder Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Advanced Contact Form Builder Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/advanced-contact-form-builder-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/advanced-contact-form-builder-pro/)
>
> ---


# Advanced Contact Form Builder Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x (bis 12.x gemäß Moduldefinition)
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst und für Funktionen wie Webhooks oder reCAPTCHA erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptbildschirm, auf dem Sie das allgemeine Verhalten und die Standardoptionen für Ihre Kontaktformulare einrichten.

-   **Profil für Template-Unterstützung**

    *   **Was diese Einstellung bewirkt:** Diese Einstellung hilft dem Modul, seine visuelle Ausgabe besser an das Theme Ihres Shops anzupassen. Verschiedene PrestaShop-Themes können leicht unterschiedliche HTML-Strukturen haben.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn auf „Classic“ (oder ähnlich) eingestellt:* Das Modul verwendet Templates, die für das Standard-PrestaShop-Classic-Theme oder darauf basierende Themes optimiert sind. Dies stellt sicher, dass die Formulare ohne zusätzlichen Styling-Aufwand gut aussehen.
        *   *Wenn auf „Custom“ oder einen anderen Theme-Namen eingestellt:* Das Modul verwendet möglicherweise spezifische Templates oder Styling-Regeln, die auf dieses bestimmte Theme zugeschnitten sind, falls verfügbar.
    *   **Empfohlener Wert:** Wählen Sie die Option, die am besten zu Ihrem aktiven PrestaShop-Theme passt. Wenn Sie das Standard-Classic-Theme oder ein davon abgeleitetes Theme verwenden, ist „Classic“ normalerweise die beste Wahl. Wenn Ihre Formulare nicht ganz richtig aussehen, versuchen Sie, mit dieser Einstellung zu experimentieren.
    *   **Händlerszenario / Beispiel:** Wenn Ihre Formulare nach der Installation ungestylt oder falsch ausgerichtet erscheinen, könnte das Umschalten von „Classic“ auf ein anderes verfügbares Profil (falls vorhanden) das Problem beheben.
-   **Autoresponder-E-Mail**

    *   **Was diese Einstellung bewirkt:** Dies ist die E-Mail-Adresse, von der automatische Bestätigungs-E-Mails an Ihre Kunden gesendet werden, nachdem sie ein Formular abgeschickt haben.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn auf eine gültige E-Mail-Adresse eingestellt:* Kunden erhalten eine sofortige „Vielen Dank für Ihre Anfrage“-E-Mail von dieser Adresse.
        *   *Wenn leer gelassen:* Es wird keine automatische Bestätigungs-E-Mail an den Kunden gesendet.
    *   **Empfohlener Wert:** Verwenden Sie eine professionelle E-Mail-Adresse, die mit Ihrem Shop verbunden ist, z. B. `info@ihrshop.com` oder `noreply@ihrshop.com`.
    *   **Händlerszenario / Beispiel:** Wenn Sie dies auf `support@meinshop.com` einstellen, wissen Kunden, dass ihre Nachricht empfangen wurde, und erhalten einen Kontaktpunkt für die Nachverfolgung.
-   **E-Mail-Titel (für Shop-Inhaber)**

    *   **Was diese Einstellung bewirkt:** Dies definiert die Betreffzeile für die E-Mail-Benachrichtigungen, die Sie (der Shop-Inhaber) erhalten, wenn ein Kunde ein Formular absendet.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn auf „Neue Anfrage von meinem Shop“ eingestellt:* Ihre Benachrichtigungs-E-Mails haben diesen Betreff, wodurch sie leicht zu identifizieren sind.
    *   **Empfohlener Wert:** Etwas Klares und Beschreibendes, wie „Neue Kontaktformular-Einreichung - [Ihr Shop-Name]“.
    *   **Händlerszenario / Beispiel:** Die Verwendung von „Neue Kundenanfrage - MyPresta.eu“ hilft Ihnen, wichtige Nachrichten in Ihrem Posteingang schnell zu erkennen.
-   **Empfänger-E-Mail(s)**

    *   **Was diese Einstellung bewirkt:** Hier geben Sie eine oder mehrere E-Mail-Adressen an, die Benachrichtigungen erhalten, wenn ein Kunde *irgendein* Formular absendet, das mit diesem Modul erstellt wurde. Sie können mehrere E-Mails durch ein Komma trennen.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn auf `sales@ihrshop.com` eingestellt:* Alle Formular-Einreichungen werden an die Verkaufsabteilung gesendet.
        *   *Wenn auf `sales@ihrshop.com, support@ihrshop.com` eingestellt:* Beide Abteilungen erhalten Kopien aller Einreichungen.
    *   **Empfohlener Wert:** Die primäre(n) E-Mail-Adresse(n) für Ihren Kundenservice oder Ihr Verkaufsteam.
    *   **Händlerszenario / Beispiel:** Wenn Sie ein dediziertes Kundenservice-Team haben, würden Sie hier `kundenservice@ihrshop.com` eingeben.
-   **BCC für Shop-Benachrichtigungs-E-Mail**

    *   **Was diese Einstellung bewirkt:** Ermöglicht das Senden einer „Blindkopie“ der Shop-Inhaber-Benachrichtigungs-E-Mail an zusätzliche E-Mail-Adressen. Diese Empfänger sind für den primären Empfänger nicht sichtbar.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn auf `manager@ihrshop.com` eingestellt:* Der Manager erhält eine versteckte Kopie aller Formular-Einreichungsbenachrichtigungen.
    *   **Empfohlener Wert:** Verwenden Sie dies für interne Nachverfolgung, Sicherung oder für Manager, die Anfragen überwachen müssen, ohne der primäre Kontakt zu sein. Leer lassen, wenn nicht benötigt.
    *   **Händlerszenario / Beispiel:** Ihr Marketingteam möchte sich möglicherweise selbst per BCC benachrichtigen lassen, um die Lead-Generierung aus Formularen zu verfolgen, ohne direkt in die Kundenantworten involviert zu sein.
-   **Ja / Nein (für verschiedene Sichtbarkeits-/Anforderungseinstellungen von Feldern)**

    *   **Was diese Einstellung bewirkt:** Dies sind allgemeine Schalter zum Aktivieren oder Deaktivieren spezifischer Funktionen oder zum Festlegen, ob bestimmte Felder in Ihren Formularen obligatorisch/optional sind.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert (Ja):* Die Funktion ist aktiv (z. B. Telefonfeld ist sichtbar, Anhänge sind erlaubt).
        *   *Wenn deaktiviert (Nein):* Die Funktion ist inaktiv (z. B. Telefonfeld ist ausgeblendet, Anhänge sind nicht erlaubt).
    *   **Empfohlener Wert:** Hängt vollständig von Ihren Geschäftsanforderungen für jede spezifische Einstellung ab (siehe individuelle Einstellungen unten).
-   **DSGVO-konform**

    *   **Was diese Einstellung bewirkt:** Aktiviert ein Kontrollkästchen in Ihren Formularen, bei dem Kunden Ihrer Datenschutzerklärung explizit zustimmen müssen, bevor sie ihre Daten übermitteln. Dies ist entscheidend für die DSGVO-Konformität.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Ein obligatorisches Kontrollkästchen erscheint in Ihren Formularen, das typischerweise etwas wie „Ich stimme der Datenschutzerklärung zu“ besagt. Das Formular kann erst abgeschickt werden, wenn dieses Kästchen aktiviert ist.
        *   *Wenn deaktiviert:* Es erscheint kein DSGVO-Einwilligungs-Kontrollkästchen.
    *   **Empfohlener Wert:** **JA**, wenn Ihr Shop in Regionen tätig ist, die der DSGVO unterliegen (z. B. EU), oder wenn Sie Best Practices für den Datenschutz sicherstellen möchten.
    *   **Händlerszenario / Beispiel:** Ein in der EU ansässiger Shop *muss* dies aktivieren, um Kundendaten über Formulare legal zu sammeln.
-   **Datenschutzerklärung-Seite**

    *   **Was diese Einstellung bewirkt:** Wenn die DSGVO-Konformität aktiviert ist, können Sie mit dieser Einstellung auf die CMS-Seite Ihrer Datenschutzerklärung verlinken. Das DSGVO-Einwilligungs-Kontrollkästchen enthält typischerweise einen Link zu dieser Seite.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn eine Seite ausgewählt ist:* Der DSGVO-Einwilligungstext enthält einen anklickbaren Link zu Ihrer ausgewählten Datenschutzerklärung-Seite.
        *   *Wenn keine Seite ausgewählt ist:* Der DSGVO-Einwilligungstext erscheint möglicherweise ohne Link oder verlinkt auf eine Standardseite, was für die Konformität nicht ideal ist.
    *   **Empfohlener Wert:** Wählen Sie die offizielle CMS-Seite Ihrer Datenschutzerklärung.
    *   **Händlerszenario / Beispiel:** Nach der Aktivierung der DSGVO würden Sie die CMS-Seite mit dem Titel „Datenschutzerklärung“ aus der Dropdown-Liste auswählen.
-   **ReCaptcha (v2)**

    *   **Was diese Einstellung bewirkt:** Aktiviert Google reCAPTCHA v2 in Ihren Formularen, um vor Spam und Bots zu schützen.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Das reCAPTCHA-Kontrollkästchen „Ich bin kein Roboter“ erscheint in Ihren Formularen. Benutzer müssen diese Herausforderung vor dem Absenden abschließen.
        *   *Wenn deaktiviert:* Es ist kein reCAPTCHA-Schutz aktiv.
    *   **Empfohlener Wert:** **JA**, um Spam-Einreichungen zu verhindern. Sie müssen auch den Site Key und Secret Key unten konfigurieren.
    *   **Händlerszenario / Beispiel:** Wenn Sie viele Spam-Nachrichten über Ihre Kontaktformulare erhalten, ist die Aktivierung von reCAPTCHA der erste Schritt, um dies zu bekämpfen.
-   **ReCaptcha Site Key**

    *   **Was diese Einstellung bewirkt:** Dies ist ein öffentlicher Schlüssel, der von Google reCAPTCHA bereitgestellt wird und es Ihrer Website ermöglicht, das reCAPTCHA-Widget anzuzeigen.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn korrekt eingegeben:* Das reCAPTCHA-Widget wird korrekt in Ihren Formularen angezeigt und funktioniert.
        *   *Wenn falsch oder leer:* reCAPTCHA funktioniert nicht, und Formulare können möglicherweise nicht gesendet werden oder zeigen Fehler an.
    *   **Empfohlener Wert:** Der Site Key, den Sie von Ihrem Google reCAPTCHA-Konto erhalten haben.
    *   **Händlerszenario / Beispiel:** Nachdem Sie ein reCAPTCHA v2-Schlüsselpaar in der Google reCAPTCHA-Admin-Konsole erstellt haben, würden Sie den „Site Key“ hierher kopieren.
-   **ReCaptcha Secret Key**

    *   **Was diese Einstellung bewirkt:** Dies ist ein privater Schlüssel, der von Google reCAPTCHA bereitgestellt wird und es Ihrem Server ermöglicht, die reCAPTCHA-Antwort zu überprüfen. Er sollte geheim gehalten werden.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn korrekt eingegeben:* Ihr Server kann erfolgreich überprüfen, ob ein Benutzer die reCAPTCHA-Herausforderung bestanden hat.
        *   *Wenn falsch oder leer:* Die Überprüfung schlägt fehl, und legitime Benutzer können möglicherweise keine Formulare absenden.
    *   **Empfohlener Wert:** Der Secret Key, den Sie von Ihrem Google reCAPTCHA-Konto erhalten haben.
    *   **Händlerszenario / Beispiel:** Sie würden den „Secret Key“ aus Ihrer Google reCAPTCHA-Admin-Konsole hierher kopieren.
-   **Webhook-URL (Slack/Discord)**

    *   **Was diese Einstellung bewirkt:** Ermöglicht das Senden von Formular-Einreichungsbenachrichtigungen an einen bestimmten Slack- oder Discord-Kanal über einen Webhook. Dies bietet sofortige Team-Benachrichtigungen.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn eine gültige URL eingegeben ist:* Jede Formular-Einreichung löst eine Benachrichtigung an Ihren konfigurierten Slack/Discord-Kanal aus.
        *   *Wenn leer:* Es werden keine Webhook-Benachrichtigungen gesendet.
    *   **Empfohlener Wert:** Ihre Slack- oder Discord-Webhook-URL. Leer lassen, wenn Sie diese Dienste nicht für Benachrichtigungen verwenden.
    *   **Händlerszenario / Beispiel:** Ihr Kundensupport-Team verwendet Slack. Sie konfigurieren einen Webhook in Slack, fügen die URL hier ein, und jetzt erscheint jede neue Anfrage direkt in ihrem #customer-support-Kanal.
-   **Benutzerdefiniertes CSS (Storefront)**

    *   **Was diese Einstellung bewirkt:** Bietet einen Textbereich, in dem Sie Ihren eigenen benutzerdefinierten CSS-Code hinzufügen können, um die Formulare in Ihrem Shop zu gestalten. Dies ist nützlich, um das Erscheinungsbild perfekt an Ihre Marke anzupassen.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn CSS eingegeben ist:* Die hier definierten Stile werden auf Ihre Formulare angewendet und überschreiben die Standardstile des Moduls.
    *   **Empfohlener Wert:** Verwenden Sie dies nur, wenn Sie spezifische Styling-Anforderungen haben, die über das Standard-Erscheinungsbild des Moduls hinausgehen. Konsultieren Sie einen Webdesigner, wenn Sie unsicher sind.
    *   **Händlerszenario / Beispiel:** Sie möchten, dass der Absende-Button des Formulars einen bestimmten Grünton hat, der zu Ihrem Logo passt. Sie würden hier CSS wie `.cfrompro-form button[type="submit"] { background-color: #00FF00; }` hinzufügen.
-   **Minimale Fragenlänge (Zeichen)**

    *   **Was diese Einstellung bewirkt:** Legt die minimale Anzahl von Zeichen fest, die für das Hauptfeld „Frage“ oder „Nachricht“ in Ihren Formularen erforderlich sind.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn auf 10 eingestellt:* Kunden müssen mindestens 10 Zeichen in das Nachrichtenfeld eingeben, um das Formular abzusenden.
        *   *Wenn auf 0 (oder sehr niedrig) eingestellt:* Ermöglicht sehr kurze Nachrichten.
    *   **Empfohlener Wert:** 10-20 Zeichen, um Kunden zu ermutigen, genügend Details anzugeben.
    *   **Händlerszenario / Beispiel:** Um vage Anfragen wie „Hallo“ zu vermeiden, stellen Sie dies auf 15 ein, um sicherzustellen, dass Kunden eine detailliertere Nachricht senden.
-   **Maximale Fragenlänge (Zeichen)**

    *   **Was diese Einstellung bewirkt:** Legt die maximale Anzahl von Zeichen fest, die für das Hauptfeld „Frage“ oder „Nachricht“ erlaubt sind.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn auf 500 eingestellt:* Kunden können nicht mehr als 500 Zeichen in das Nachrichtenfeld eingeben.
    *   **Empfohlener Wert:** 500-1000 Zeichen, je nachdem, wie detailliert Sie die Anfragen erwarten. Zu niedrig könnte Benutzer frustrieren, zu hoch könnte zu übermäßig langen Nachrichten führen.
    *   **Händlerszenario / Beispiel:** Sie möchten extrem lange Aufsätze im Kontaktformular verhindern, daher stellen Sie dies auf 750 Zeichen ein.
-   **Bildanhang erlauben**

    *   **Was diese Einstellung bewirkt:** Aktiviert oder deaktiviert die Möglichkeit für Kunden, Dateien (wie Bilder, PDFs) mit ihrer Formular-Einreichung hochzuladen.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn aktiviert:* Ein Dateiupload-Feld erscheint in Ihren Formularen.
        *   *Wenn deaktiviert:* Es ist keine Dateiupload-Option verfügbar.
    *   **Empfohlener Wert:** **JA**, wenn Kunden oft Screenshots, Bestellbestätigungen oder andere Dokumente bereitstellen müssen. **NEIN**, wenn Sie die Formulare einfach halten möchten.
    *   **Händlerszenario / Beispiel:** Für ein Support-Formular ermöglicht das Aktivieren von Anhängen Kunden, Screenshots von Problemen zu senden, was sehr hilfreich ist.
-   **Maximale Anhangsgröße (MB)**

    *   **Was diese Einstellung bewirkt:** Wenn Anhänge erlaubt sind, definiert diese Einstellung die maximale Dateigröße (in Megabyte), die ein Kunde hochladen kann.
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn auf 5 eingestellt:* Kunden können Dateien bis zu 5 MB hochladen. Größere Dateien werden abgelehnt.
    *   **Empfohlener Wert:** 2-5 MB ist in der Regel ausreichend für die meisten Dokumente und Bilder, ohne Ihren Server zu überlasten.
    *   **Händlerszenario / Beispiel:** Sie erlauben Anhänge, möchten aber riesige Dateien verhindern, daher legen Sie das Limit auf 3 MB fest.
-   **Dauer der Erfolgsmeldung (ms)**

    *   **Was diese Einstellung bewirkt:** Steuert, wie lange die Meldung „Formular erfolgreich gesendet“ (oft eine „Toast“-Benachrichtigung) für den Kunden sichtbar bleibt, nachdem er ein Formular abgeschickt hat. Gemessen in Millisekunden (1000 ms = 1 Sekunde).
    *   **Auswirkungen einer Änderung dieser Einstellung:**
        *   *Wenn auf 3000 eingestellt:* Die Erfolgsmeldung verschwindet nach 3 Sekunden.
        *   *Wenn auf 0 eingestellt:* Die Meldung bleibt möglicherweise unbegrenzt oder verschwindet sofort (abhängig von Theme/Browser).
    *   **Empfohlener Wert:** 3000-5000 ms (3-5 Sekunden) ist ein gutes Gleichgewicht, das Kunden genügend Zeit zum Lesen gibt, ohne aufdringlich zu sein.
    *   **Händlerszenario / Beispiel:** Sie möchten, dass Kunden die Bestätigung deutlich sehen, daher stellen Sie sie auf 4000 ms ein.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Das Modul fügt neue Menüpunkte unter **„Advanced Contact Form Pro“** in Ihrem PrestaShop Back Office hinzu.

#### 2.2.1 Formularverwaltung (Back Office > Advanced Contact Form Pro > Formulare)

Dieser Bildschirm ermöglicht es Ihnen, alle Ihre benutzerdefinierten Kontaktformulare zu erstellen, zu bearbeiten und zu verwalten.

-   **Bildschirmname & Menüpfad:** **Advanced Contact Form Pro > Formulare**
-   **Verfügbare Aktionen & Einstellungen:**
    *   **Listenansicht (Raster):** Zeigt eine Tabelle aller Ihrer erstellten Formulare mit deren Namen, ID und Status an.
    *   **Neues Formular hinzufügen:** Klicken Sie auf die Schaltfläche „Neues Formular hinzufügen“, um ein brandneues benutzerdefiniertes Formular zu erstellen.
    *   **Formular bearbeiten:** Klicken Sie auf das „Bearbeiten“-Symbol neben einem Formular in der Liste, um dessen Einstellungen zu ändern.
    *   **Formular löschen:** Klicken Sie auf das „Löschen“-Symbol, um ein Formular zu entfernen.
    *   **Formularkonfigurationsfelder (beim Hinzufügen/Bearbeiten):**
        *   **Formularname:** Ein klarer interner Name für Ihr Formular (z. B. „Großhandelsanfrage“, „Produktsupport“).
        *   **Shortcode:** Ein eindeutiger Code (z. B. `[cfrompro id="1"]`), den Sie verwenden, um dieses spezifische Formular in CMS-Seiten oder Produktbeschreibungen einzubetten.
        *   **Formularstatus:** Formular aktivieren/deaktivieren. Deaktivierte Formulare werden im Shop nicht angezeigt.
        *   **Empfänger-E-Mail(s) für DIESES Formular:** Sie können die globalen Empfänger-E-Mails für dieses spezifische Formular überschreiben. Dies ist sehr leistungsstark für die Weiterleitung von Anfragen.
        *   **Autoresponder-E-Mail für DIESES Formular:** Überschreiben Sie die globale Autoresponder-E-Mail für dieses Formular.
        *   **E-Mail-Titel (für Shop-Inhaber) für DIESES Formular:** Überschreiben Sie den globalen E-Mail-Betreff für Benachrichtigungen von diesem Formular.
        *   **Benutzerdefinierte Felder:** Hier definieren Sie die einzigartigen Felder für *dieses* Formular. Sie können Texteingaben, Textbereiche, Dropdowns, Kontrollkästchen, Optionsfelder, Dateiuploads und mehr hinzufügen. Für jedes benutzerdefinierte Feld können Sie festlegen:
            *   **Beschriftung:** Was der Kunde sieht (z. B. „Ihr Firmenname“).
            *   **Typ:** (Text, Textarea, Select, Checkbox, Radio, File usw.).
            *   **Erforderlich:** Ist dieses Feld obligatorisch?
            *   **Platzhalter:** Hinweistext im Eingabefeld.
            *   **Optionen (für Select, Checkbox, Radio):** Definieren Sie die Auswahlmöglichkeiten, die Kunden treffen können.
            *   **Validierungsregeln:** (z. B. E-Mail-Format, nur Zahlen).
        *   **Einstellungen für schwebenden Auslöser:**
            *   **Schwebenden Auslöser aktivieren:** Zeigt einen schwebenden Button im Shop an, der dieses Formular öffnet.
            *   **Auslöser-Text:** Welcher Text auf dem schwebenden Button erscheint (z. B. „Kontaktieren Sie uns“).
            *   **Auslöser-Position:** Wo der Button erscheint (z. B. links, rechts, unten links).
            *   **Auslöser-Symbol:** Wählen Sie ein Symbol für den Button.
            *   **Auslöser-Verzögerung (ms):** Wie lange gewartet werden soll, bevor der schwebende Button erscheint (z. B. 2000 ms = 2 Sekunden).
            *   **Auslöser-Farbe, Textfarbe, Hover-Farbe:** Passen Sie das Erscheinungsbild des Buttons an.
-   **Auswirkungen von Änderungen:**
    *   Das Hinzufügen/Bearbeiten eines Formulars macht es für die Einbettung oder als schwebenden Auslöser verfügbar.
    *   Änderungen an benutzerdefinierten Feldern wirken sich direkt darauf aus, was Kunden in diesem spezifischen Formular sehen und ausfüllen.
    *   Änderungen an Empfänger-E-Mails leiten Einreichungen an verschiedene Abteilungen weiter.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  Entscheiden Sie, welche Art von Anfrage Sie bearbeiten möchten (z. B. „Großhandelsantrag“).
    2.  Gehen Sie zu **Formulare** und klicken Sie auf „Neues Formular hinzufügen“.
    3.  Geben Sie ihm einen klaren Namen.
    4.  Fügen Sie alle spezifischen benutzerdefinierten Felder hinzu, die Sie benötigen (z. B. Firmenname, USt-IdNr., Geschäftstyp, erwartetes Bestellvolumen).
    5.  Legen Sie eine spezifische Empfänger-E-Mail fest, wenn dieses Formular an ein bestimmtes Team gehen soll (z. B. `grosshandel@ihrshop.com`).
    6.  Speichern Sie das Formular. Notieren Sie sich seinen Shortcode.
    7.  Betten Sie den Shortcode in eine relevante CMS-Seite ein (z. B. „Großhandelsinformationen“).

#### 2.2.2 Fragenverwaltung (Back Office > Advanced Contact Form Pro > Fragen)

Dieser Bildschirm dient als Ihr Posteingang für alle Formular-Einreichungen.

-   **Bildschirmname & Menüpfad:** **Advanced Contact Form Pro > Fragen**
-   **Verfügbare Aktionen & Einstellungen:**
    *   **Listenansicht (Raster):** Zeigt eine Tabelle aller eingereichten Fragen/Anfragen an.
        *   **Spalten:** Zeigt Informationen wie Formularname, Kundenname, E-Mail, Thema (falls zutreffend), Einreichungsdatum und Status an.
    *   **Frage anzeigen:** Klicken Sie auf das „Anzeigen“-Symbol (Lupe) neben einer Anfrage, um deren vollständige Details anzuzeigen.
        *   **Detailansicht:** Zeigt alle vom Kunden übermittelten Informationen, einschließlich Antworten auf benutzerdefinierte Felder, Anhänge (mit Download-Links) und das Formular, von dem es stammt.
        *   **Antwortbereich:** Ermöglicht es Ihnen, direkt aus dem PrestaShop Back Office auf den Kunden zu antworten. Diese Antwort wird von der Standard-Kontakt-E-Mail Ihres Shops gesendet.
        *   **Status ändern:** Sie können den Status einer Anfrage aktualisieren (z. B. „Neu“, „In Bearbeitung“, „Gelöst“).
    *   **Frage löschen:** Entfernen Sie eine Anfrage aus der Liste.
-   **Auswirkungen von Änderungen:**
    *   Das Anzeigen einer Frage ermöglicht es Ihnen, Kundenanfragen effizient zu bearbeiten.
    *   Das Antworten von hier aus speichert eine Aufzeichnung der Kommunikation (obwohl das Modul die vollständige Antworthistorie nicht selbst speichert, sendet es eine Standard-E-Mail).
    *   Das Ändern des Status hilft Ihnen, den Fortschritt jeder Anfrage zu verfolgen.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  Überprüfen Sie regelmäßig diesen Bereich „Fragen“.
    2.  Klicken Sie für jede neue Anfrage auf „Anzeigen“, um die Details zu lesen.
    3.  Wenn eine Antwort erforderlich ist, verwenden Sie die Funktion „Antworten“.
    4.  Aktualisieren Sie den Status (z. B. auf „In Bearbeitung“), um anzuzeigen, dass sie bearbeitet wird.
    5.  Sobald gelöst, ändern Sie den Status auf „Gelöst“.

#### 2.2.3 index.php (cfrompro/controllers/admin/index.php)

Diese Datei ist typischerweise ein Platzhalter oder eine Weiterleitung in PrestaShop-Modulen und stellt keinen direkten, konfigurierbaren Bildschirm für den Händler dar. Sie stellt sicher, dass, wenn jemand versucht, direkt auf das Verzeichnis `controllers/admin` zuzugreifen, er umgeleitet wird oder eine Standardaktion ausgeführt wird, um Verzeichnislisten-Schwachstellen zu verhindern. Händler werden nicht direkt damit interagieren.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modul-Hauptkonfiguration** | Profil für Template-Unterstützung | Classic | Passt das Formular-Styling an Ihr Theme an. |
| | Autoresponder-E-Mail | `info@ihrshop.com` | E-Mail-Adresse für Kundenbestätigungen. |
| | E-Mail-Titel (für Shop-Inhaber) | Neue Kontaktformular-Einreichung | Betreffzeile für Ihre Benachrichtigungs-E-Mails. |
| | Empfänger-E-Mail(s) | `kontakt@ihrshop.com` | Wohin alle Formular-Einreichungen gesendet werden (global). |
| | BCC für Shop-Benachrichtigungs-E-Mail | Leer | Versteckte Kopie von Benachrichtigungen zur internen Nachverfolgung. |
| | DSGVO-konform | JA | Fügt ein obligatorisches Kontrollkästchen für die Datenschutzerklärung hinzu. |
| | Datenschutzerklärung-Seite | Ihre Datenschutzerklärung-CMS-Seite | Verknüpft das DSGVO-Kontrollkästchen mit Ihrer Richtlinie. |
| | ReCaptcha (v2) | JA | Aktiviert Google reCAPTCHA zum Spam-Schutz. |
| | ReCaptcha Site Key | Ihr Google Site Key | Öffentlicher Schlüssel für das reCAPTCHA-Widget. |
| | ReCaptcha Secret Key | Ihr Google Secret Key | Privater Schlüssel für die reCAPTCHA-Verifizierung. |
| | Webhook-URL (Slack/Discord) | Leer | Sendet Benachrichtigungen an Slack/Discord. |
| | Benutzerdefiniertes CSS (Storefront) | Leer | Fügen Sie benutzerdefinierte Stile zu Ihren Formularen hinzu. |
| | Minimale Fragenlänge (Zeichen) | 10-20 | Minimale Zeichen für das Hauptnachrichtenfeld. |
| | Maximale Fragenlänge (Zeichen) | 500-1000 | Maximale Zeichen für das Hauptnachrichtenfeld. |
| | Bildanhang erlauben | JA | Aktiviert Dateiuploads in Formularen. |
| | Maximale Anhangsgröße (MB) | 2-5 | Maximale Größe für hochgeladene Dateien. |
| | Dauer der Erfolgsmeldung (ms) | 3000-5000 | Wie lange die Erfolgsbenachrichtigung sichtbar bleibt. |
| **Formularverwaltung** | Formularname | Beschreibender Name | Interner Name für Ihr benutzerdefiniertes Formular. |
| | Shortcode | Automatisch generiert `[cfrompro id="X"]` | Code zum Einbetten des Formulars. |
| | Formularstatus | Aktiviert | Aktiviert/deaktiviert das Formular. |
| | Empfänger-E-Mail(s) für DIESES Formular | Spezifische E-Mail(s) | Überschreibt den globalen Empfänger für dieses Formular. |
| | Benutzerdefinierte Felder | Variiert | Definieren Sie einzigartige Eingabefelder für jedes Formular. |
| | Schwebenden Auslöser aktivieren | NEIN (oder JA für spezifische Formulare) | Zeigt einen schwebenden Button zum Öffnen des Formulars an. |
| | Auslöser-Text | „Kontaktieren Sie uns“ | Text auf dem schwebenden Button. |
| | Auslöser-Position | Rechts/Links | Platzierung des schwebenden Buttons. |
| **Fragenverwaltung** | Frage anzeigen | N/A | Zeigt vollständige Details einer Kundenanfrage an. |
| | Antworten | N/A | Senden Sie eine E-Mail-Antwort an den Kunden. |
| | Status ändern | Neu, In Bearbeitung, Gelöst | Verfolgen Sie die Bearbeitung von Anfragen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Formulare sehen nicht richtig aus, oder das Styling ist fehlerhaft.**
A:

-   **„Profil für Template-Unterstützung“ überprüfen:** Gehen Sie zu **Module > Modul-Manager > Advanced Contact Form Builder Pro > Konfigurieren** und stellen Sie sicher, dass das „Profil für Template-Unterstützung“ Ihrem aktuellen PrestaShop-Theme entspricht (z. B. „Classic“ für das Standard-Theme).
-   **Smarty-Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung**, scrollen Sie nach unten zu „Cache“ und klicken Sie auf „Cache leeren“. Manchmal können alte Styling-Dateien hängen bleiben.
-   **Benutzerdefiniertes CSS:** Wenn Sie benutzerdefiniertes CSS hinzugefügt haben, überprüfen Sie es auf Fehler. Entfernen Sie es vorübergehend, um zu sehen, ob es das Problem verursacht.
-   **Theme-Konflikte:** Wenn das Problem weiterhin besteht, könnte Ihr Theme einen Konflikt haben. Kontaktieren Sie Ihren Theme-Entwickler oder den MyPresta.eu-Support.

**F: Ich erhalte keine E-Mail-Benachrichtigungen, wenn ein Formular gesendet wird.**
A:

-   **Empfänger-E-Mails überprüfen:** Gehen Sie zu **Module > Modul-Manager > Advanced Contact Form Builder Pro > Konfigurieren** und überprüfen Sie, ob die „Empfänger-E-Mail(s)“ korrekt sind. Überprüfen Sie auch die individuellen Formulareinstellungen unter **Advanced Contact Form Pro > Formulare**, um zu sehen, ob ein bestimmtes Formular den globalen Empfänger überschreibt.
-   **Spam-Ordner überprüfen:** Die E-Mails könnten in Ihrem Spam- oder Junk-Ordner landen.
-   **Server-Mail-Einstellungen:** Stellen Sie sicher, dass die E-Mail-Einstellungen Ihres PrestaShop-Shops korrekt konfiguriert sind (**Erweiterte Einstellungen > E-Mail**). Testen Sie das Senden einer regulären E-Mail von PrestaShop.
-   **Hosting-Anbieter:** Ihr Hosting-Anbieter hat möglicherweise E-Mail-Sendebeschränkungen oder -probleme. Überprüfen Sie Ihre Serverprotokolle oder kontaktieren Sie ihn.

**F: reCAPTCHA funktioniert nicht, oder Formulare können mit aktiviertem reCAPTCHA nicht gesendet werden.**
A:

-   **Schlüssel überprüfen:** Überprüfen Sie Ihre „ReCaptcha Site Key“ und „ReCaptcha Secret Key“ in der Hauptkonfiguration des Moduls. Stellen Sie sicher, dass keine Tippfehler vorhanden sind und sie einer reCAPTCHA v2-Einrichtung in Ihrem Google-Konto entsprechen.
-   **Domain-Registrierung:** Stellen Sie sicher, dass der Domainname Ihres Shops korrekt in Ihrem Google reCAPTCHA-Konto registriert ist.
-   **Netzwerkprobleme:** Deaktivieren Sie reCAPTCHA vorübergehend, um zu sehen, ob Formulare gesendet werden. Wenn ja, liegt das Problem definitiv an der reCAPTCHA-Einrichtung oder der Kommunikation mit den Google-Servern.

**F: Wie übersetze ich die Formularfelder und Nachrichten in andere Sprachen?**
A:

-   **PrestaShop-Übersetzungssystem:** Gehen Sie zu **International > Übersetzungen**.
-   **Übersetzungstyp:** Wählen Sie „Übersetzungen installierter Module“.
-   **Wählen Sie Ihr Theme:** Wählen Sie Ihr aktuelles Theme.
-   **Wählen Sie Ihre Sprache:** Wählen Sie die Sprache, in die Sie übersetzen möchten.
-   **Modul:** Wählen Sie „cfrompro“ (den technischen Namen des Moduls).
-   Sie sehen dann eine Liste aller übersetzbaren Zeichenfolgen des Moduls, einschließlich Feldbezeichnungen, Erfolgsmeldungen und Fehlermeldungen. Übersetzen Sie diese und speichern Sie.

**F: Mein schwebender Auslöse-Button wird nicht angezeigt.**
A:

-   **Auslöser aktivieren:** Gehen Sie zu **Advanced Contact Form Pro > Formulare**, bearbeiten Sie das Formular, das Sie auslösen möchten, und stellen Sie sicher, dass „Schwebenden Auslöser aktivieren“ auf JA eingestellt ist.
-   **Auslöser-Verzögerung:** Überprüfen Sie die Einstellung „Auslöser-Verzögerung (ms)“. Wenn es eine hohe Zahl ist, müssen Sie möglicherweise länger warten, bis es erscheint.
-   **Theme-Konflikte:** Einige Themes haben möglicherweise CSS, das den Button ausblendet, oder JavaScript, das stört. Überprüfen Sie die Entwicklerkonsole Ihres Browsers auf Fehler.
-   **Cache:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung**).

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul **Advanced Contact Form Builder Pro** (`cfrompro`) folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller) und erweitert die Kern-PrestaShop-Klassen für seine Funktionalität. Es nutzt `ObjectModel` zur Verwaltung benutzerdefinierter Formulare und eingereichter Fragen, verwendet dedizierte Admin-Controller für die Back-Office-Verwaltung und integriert sich in verschiedene PrestaShop-Hooks für die Front-Office-Anzeige und Backend-Aktionen. Benutzerdefinierte Felder werden über eine dedizierte Klasse verwaltet und als JSON gespeichert.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

-   `cfrompro/controllers/front/index.php`
    *   **Klassenname:** `CfromproIndexModuleFrontController` (wahrscheinlich, basierend auf dem Dateinamen)
    *   **Elternklasse:** `ModuleFrontController`
    *   **Verantwortlichkeit:** Dieser Controller ist wahrscheinlich für die anfängliche Anzeige eines Formulars verantwortlich, wenn es über eine direkte URL aufgerufen wird (obwohl die meisten Formulare eingebettet oder über AJAX geöffnet werden). Er könnte auch das anfängliche Rendern des schwebenden Auslösers oder des Modals, das das Formular enthält, übernehmen.
-   `cfrompro/controllers/front/question.php`
    *   **Klassenname:** `CfromproQuestionModuleFrontController` (wahrscheinlich)
    *   **Elternklasse:** `ModuleFrontController`
    *   **Verantwortlichkeit:** Dies ist der Kern-Controller für die Verarbeitung von Formular-Einreichungen. Er empfängt POST-Daten von den Formularen, führt Validierungen durch (einschließlich reCAPTCHA, Feldlänge, Pflichtfelder, Anhangsgröße), speichert die übermittelten Daten (Frage und benutzerdefinierte Felder) in der Datenbank, sendet E-Mail-Benachrichtigungen an den Shop-Inhaber und Autoresponder an den Kunden und löst möglicherweise den Webhook aus. Er gibt JSON-Antworten für AJAX-Einreichungen zurück (z. B. Erfolgs-/Fehlermeldungen).

#### Back-Office-Admin-Controller

-   `cfrompro/controllers/admin/AdminCfromproForm.php`
    *   **Klassenname:** `AdminCfromproFormController`
    *   **Elternklasse:** `ModuleAdminController`
    *   **Tab-Name:** „Formulare“ unter „Advanced Contact Form Pro“
    *   **Verwaltete Entität:** `CfromproForm` (hypothetisches `ObjectModel` für Formulare)
    *   **Verantwortlichkeit:** Verwaltet die CRUD-Operationen (Create, Read, Update, Delete) für benutzerdefinierte Formulare. Es definiert die Listenansicht (Raster) für Formulare und die Formularstruktur zum Hinzufügen/Bearbeiten eines Formulars. Dieser Controller behandelt das Speichern von Formulareinstellungen, einschließlich der komplexen JSON-Struktur für benutzerdefinierte Felder.
-   `cfrompro/controllers/admin/AdminCfromproQuestion.php`
    *   **Klassenname:** `AdminCfromproQuestionController`
    *   **Elternklasse:** `ModuleAdminController`
    *   **Tab-Name:** „Fragen“ unter „Advanced Contact Form Pro“
    *   **Verwaltete Entität:** `CfromproQuestion` (hypothetisches `ObjectModel` für eingereichte Fragen)
    *   **Verantwortlichkeit:** Verwaltet die CRUD-Operationen für eingereichte Fragen. Es zeigt die Liste der Anfragen an, ermöglicht das Anzeigen individueller Fragedetails und bietet Funktionen zum Antworten auf Kunden und zum Ändern des Status einer Anfrage.
-   `cfrompro/controllers/admin/index.php`
    *   **Klassenname:** (Keine, typischerweise)
    *   **Elternklasse:** (Keine, typischerweise)
    *   **Verantwortlichkeit:** Dies ist eine Standard-PrestaShop-Praxis, um direkte Verzeichnislisten zu verhindern. Es enthält normalerweise ein einfaches `header('Location: ../../index.php?controller=AdminHome');` oder ähnliches, um zum Back-Office-Dashboard umzuleiten. Es stellt keinen funktionalen Controller für die Modullogik dar.

### 4.3 Kernklassen & Modelle (`classes/`)

-   `cfrompro/classes/CfromproCustomFields.php`
    *   **Klassenname:** `CfromproCustomFields`
    *   **Elternklasse:** (Wahrscheinlich `ObjectModel` oder eine benutzerdefinierte Basisklasse zur Handhabung komplexer Daten)
    *   **Datenbanktabelle:** (Wahrscheinlich `ps_cfrompro_form`, wenn es benutzerdefinierte Felddefinitionen innerhalb des Formularobjekts speichert, oder eine separate Tabelle `ps_cfrompro_custom_field`, wenn Felder eigenständige Entitäten sind). Das Moduldossier weist `cfrompro_form` und `cfrompro_question` als verwaltete Tabellen aus, was darauf hindeutet, dass benutzerdefinierte Felder wahrscheinlich als JSON-String in der Tabelle `cfrompro_form` serialisiert werden.
    *   **`$definition`-Felder:** Wenn es `ObjectModel` erweitert, würde es Felder definieren, die sich auf benutzerdefinierte Feldeigenschaften beziehen (z. B. `id_cfrompro_custom_field`, `id_cfrompro_form`, `type`, `label`, `required`, `options`, `validation`). Angesichts der Modulbeschreibung ist es wahrscheinlicher, dass benutzerdefinierte Felder als JSON-String in der Tabelle `cfrompro_form` gespeichert werden und diese Klasse Hilfsmethoden zum Parsen, Validieren und Rendern dieser Felder bereitstellt.
    *   **Wichtige öffentliche Methoden und Geschäftslogik:**
        *   Methoden zum Hinzufügen, Bearbeiten und Löschen von benutzerdefinierten Felddefinitionen innerhalb eines Formulars.
        *   Methoden zum Rendern benutzerdefinierter Felder in der Front-Office-Vorlage.
        *   Methoden zum Validieren übermittelter benutzerdefinierter Felddaten.
        *   Methoden zum Serialisieren/Deserialisieren von benutzerdefinierten Feldkonfigurationen in/aus JSON.

### 4.4 JavaScript-Assets (`views/js/`)

-   `cfrompro/views/cfrompro.js`
    *   **Geltungsbereich:** Front-Office.
    *   **Verantwortlichkeit:** Dies ist die Haupt-JavaScript-Datei des Front-Office. Sie behandelt wahrscheinlich:
        *   Anzeigen und Verwalten des schwebenden Auslöse-Buttons (Klickereignisse, Verzögerungen).
        *   Öffnen und Schließen des Formular-Modals/Popups.
        *   AJAX-Übermittlung von Formularen (Datenerfassung, Senden an den `question.php`-Controller).
        *   Anzeigen von Erfolgs-/Fehlermeldungen (Toast-Benachrichtigungen).
        *   Clientseitige Validierung von Formularfeldern.
        *   Integration mit reCAPTCHA v2 (Rendern des Widgets, Abrufen des Antwort-Tokens).
        *   Dynamische Aktualisierungen basierend auf benutzerdefinierten Feldtypen (z. B. Anzeigen/Ausblenden von Optionen für Dropdowns).
-   `cfrompro/views/js/admin-button-style.js`
    *   **Geltungsbereich:** Back-Office (`AdminCfromproFormController`).
    *   **Verantwortlichkeit:** Bietet JavaScript-Funktionalität zum Stylen des schwebenden Auslöse-Buttons innerhalb der Formular-Konfigurationsoberfläche. Dies könnte Farbwähler, Symbolvorschauen und Echtzeit-Updates einer Vorschau des Buttons umfassen.
-   `cfrompro/views/js/admin-form-layout.js`
    *   **Geltungsbereich:** Back-Office (`AdminCfromproFormController`).
    *   **Verantwortlichkeit:** Verwaltet das dynamische Layout und die Verwaltung benutzerdefinierter Felder innerhalb der Formularerstellungs-/Bearbeitungsoberfläche. Dies würde umfassen:
        *   Hinzufügen neuer benutzerdefinierter Felder (dynamisches Generieren von HTML für verschiedene Feldtypen).
        *   Neuanordnen von Feldern (Drag-and-Drop).
        *   Bearbeiten von Feldeigenschaften (Beschriftung, Typ, erforderlich, Optionen).
        *   Entfernen von Feldern.
        *   Serialisieren der benutzerdefinierten Feldkonfiguration in einen JSON-String vor dem Speichern des Formulars.
-   `cfrompro/views/js/admin-icon-picker-data.js`
    *   **Geltungsbereich:** Back-Office (`AdminCfromproFormController`).
    *   **Verantwortlichkeit:** Enthält die Daten (z. B. ein Array von Symbolklassen oder SVG-Pfaden), die vom Symbolwähler für den schwebenden Auslöse-Button verwendet werden.
-   `cfrompro/views/js/admin-icon-picker.js`
    *   **Geltungsbereich:** Back-Office (`AdminCfromproFormController`).
    *   **Verantwortlichkeit:** Implementiert die Benutzeroberfläche und Logik zur Auswahl eines Symbols für den schwebenden Auslöse-Button. Es verwendet die Daten aus `admin-icon-picker-data.js`, um verfügbare Symbole anzuzeigen und das ausgewählte Symbol im Formular zu aktualisieren.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `cfrompro/views/cfrompro.css`
    *   **Geltungsbereich:** Front-Office-Kunden-Styling.
    *   **Verantwortlichkeit:** Bietet das Kern-Styling für die Kontaktformulare, den schwebenden Auslöser, modale Popups und Erfolgs-/Fehlermeldungen im Shop. Es definiert das allgemeine Layout, die Typografie, Farben und die Responsivität.
    *   **Wichtige CSS-Klassenselektoren:** `.cfrompro-form`, `.cfrompro-field`, `.cfrompro-trigger`, `.cfrompro-modal`, `.cfrompro-toast`.
-   `cfrompro/views/css/admin-button-style.css`
    *   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    *   **Verantwortlichkeit:** Stylt die Elemente, die mit der Konfiguration des schwebenden Auslöse-Buttons im Back Office zusammenhängen (z. B. Farbwähler, Symbolvorschau-Bereiche).
-   `cfrompro/views/css/admin-custom-fields.css`
    *   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    *   **Verantwortlichkeit:** Stylt die Oberfläche zur Verwaltung benutzerdefinierter Felder im Formular-Builder (z. B. Drag-and-Drop-Griffe, Feldkonfigurationspanels).
-   `cfrompro/views/css/admin-form-layout.css`
    *   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    *   **Verantwortlichkeit:** Bietet allgemeines Layout und Styling für die Formularerstellungs-/Bearbeitungsseite im Back Office.
-   `cfrompro/views/css/admin-icon-picker.css`
    *   **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
    *   **Verantwortlichkeit:** Stylt die Symbolauswahl-Oberfläche für den schwebenden Auslöse-Button.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

-   `cfrompro/views/templates/hook/dashboard_recent_messages.tpl`
    *   **Hook:** `displaydashboardZoneTwo` (oder ähnlicher Dashboard-Hook).
    *   **Ausgabe:** Ein Block auf dem PrestaShop-Dashboard, der die letzten Formular-Einreichungen anzeigt und dem Händler einen schnellen Überblick verschafft.

#### Admin-Templates (`views/templates/admin/`)

-   `cfrompro/views/templates/admin/button_style_block.tpl`
    *   **Geltungsbereich:** `AdminCfromproFormController` (Formularbearbeitungsseite).
    *   **Ausgabe:** HTML für den Bereich, in dem der Händler das Erscheinungsbild des schwebenden Auslöse-Buttons (Farben, Text, Symbol) konfiguriert.
-   `cfrompro/views/templates/admin/conversation_reply.tpl`
    *   **Geltungsbereich:** `AdminCfromproQuestionController` (Fragenansichtsseite).
    *   **Ausgabe:** HTML für das Antwortformular und den Statusaktualisierungsbereich beim Anzeigen einer eingereichten Frage.
-   `cfrompro/views/templates/admin/custom_fields_block.tpl`
    *   **Geltungsbereich:** `AdminCfromproFormController` (Formularbearbeitungsseite).
    *   **Ausgabe:** Der Hauptcontainer und die Steuerelemente zum Hinzufügen, Bearbeiten und Anordnen benutzerdefinierter Felder innerhalb eines Formulars. Dieses Template arbeitet wahrscheinlich in Verbindung mit `admin-form-layout.js`.
-   `cfrompro/views/templates/admin/form_layout_block.tpl`
    *   **Geltungsbereich:** `AdminCfromproFormController` (Formularbearbeitungsseite).
    *   **Ausgabe:** Allgemeine Layoutstruktur für die Formular-Konfigurationsseite, die andere Blöcke wie benutzerdefinierte Felder und Button-Stile umschließt.
-   `cfrompro/views/templates/admin/question_extras.tpl`
    *   **Geltungsbereich:** `AdminCfromproQuestionController` (Fragenansichtsseite).
    *   **Ausgabe:** Zeigt zusätzliche Details zu einer eingereichten Frage an, wie z. B. Anhänge oder spezifische Metadaten.
-   `cfrompro/views/templates/admin/question_form_profile.tpl`
    *   **Geltungsbereich:** `AdminCfromproQuestionController` (Fragenansichtsseite).
    *   **Ausgabe:** Zeigt Details zum Formular an, von dem die Frage übermittelt wurde.
-   `cfrompro/views/templates/admin/topic_options_block.tpl`
    *   **Geltungsbereich:** `AdminCfromproFormController` (Formularbearbeitungsseite).
    *   **Ausgabe:** Wenn das Modul vordefinierte Themen unterstützt, würde dieses Template die Optionen zur Konfiguration dieser rendern.

#### Front-Office-Templates (`views/templates/front/` und Root `views/`)

-   `cfrompro/views/cfrompro-extra-forms.tpl`
    *   **Hook:** Wahrscheinlich `displayFooter` oder `actionOutputHTMLBefore` zum Rendern von Formularen, die nicht direkt eingebettet sind, sondern in Modals erscheinen.
    *   **Ausgabe:** Enthält die HTML-Struktur für Formulare, die in einem modalen Fenster angezeigt werden sollen, oft ausgelöst durch einen schwebenden Button.
-   `cfrompro/views/cfrompro-extra-trigger.tpl`
    *   **Hook:** Wahrscheinlich `displayHeader` oder `actionOutputHTMLBefore` zum Rendern des schwebenden Auslöse-Buttons.
    *   **Ausgabe:** Das HTML für den schwebenden Button, der beim Klicken ein Kontaktformular öffnet.
-   `cfrompro/views/cfrompro-form-body.tpl`
    *   **Geltungsbereich:** Wird von anderen Templates (z. B. `cfrompro-extra-forms.tpl`) oder direkt beim Einbetten eines Formulars über Shortcode verwendet.
    *   **Ausgabe:** Die Kern-HTML-Struktur für ein einzelnes Kontaktformular, einschließlich Feldern, Beschriftungen, reCAPTCHA, DSGVO-Kontrollkästchen und Absende-Button. Dieses Template wird dynamisch mit benutzerdefinierten Feldern gefüllt.
-   `cfrompro/views/classic/cfrompro-extra-forms.tpl`
    *   **Geltungsbereich:** Theme-spezifische Überschreibung für `cfrompro-extra-forms.tpl`.
    *   **Ausgabe:** Dasselbe wie `cfrompro-extra-forms.tpl`, aber speziell auf die HTML-Struktur des Classic-Themes zugeschnitten.
-   `cfrompro/views/classic/cfrompro-extra-trigger.tpl`
    *   **Geltungsbereich:** Theme-spezifische Überschreibung für `cfrompro-extra-trigger.tpl`.
    *   **Ausgabe:** Dasselbe wie `cfrompro-extra-trigger.tpl`, aber speziell auf das Classic-Theme zugeschnitten.
-   `cfrompro/views/partials/cfrompro-custom-field-single.tpl`
    *   **Geltungsbereich:** Eingebunden von `cfrompro-form-body.tpl`.
    *   **Ausgabe:** Rendert das HTML für ein einzelnes benutzerdefiniertes Feld basierend auf seinem Typ (Text, Textarea, Select usw.).
-   `cfrompro/views/partials/cfrompro-custom-fields.tpl`
    *   **Geltungsbereich:** Eingebunden von `cfrompro-form-body.tpl`.
    *   **Ausgabe:** Iteriert durch die benutzerdefinierten Felddefinitionen für ein Formular und rendert jedes einzelne mithilfe von `cfrompro-custom-field-single.tpl`.
-   `cfrompro/views/partials/cfrompro-field-fragment.tpl`
    *   **Geltungsbereich:** Eingebunden von `cfrompro-form-body.tpl` oder `cfrompro-custom-field-single.tpl`.
    *   **Ausgabe:** Ein wiederverwendbares HTML-Fragment für gemeinsame Feldelemente wie Beschriftungen, Fehlermeldungen oder Wrapper.

### 4.7 Datenbank-Schema & Hooks-Map

#### Datenbanktabellen

-   `ps_cfrompro_form`: Speichert die Definitionen jedes vom Modul erstellten benutzerdefinierten Kontaktformulars.
    *   `id_cfrompro_form`: Primärschlüssel.
    *   `name`: Interner Name des Formulars.
    *   `shortcode`: Eindeutiger Bezeichner zum Einbetten.
    *   `active`: (boolean) Formularstatus.
    *   `recipient_emails`: (text) Überschriebene Empfänger-E-Mails für dieses Formular.
    *   `autoresponder_email`: (text) Überschriebene Autoresponder-E-Mail für dieses Formular.
    *   `email_title`: (text) Überschriebener E-Mail-Betreff für dieses Formular.
    *   `custom_fields_json`: (text/JSON) Serialisierter JSON-String, der die Definitionen aller benutzerdefinierten Felder für dieses Formular enthält (Typ, Beschriftung, erforderlich, Optionen, Validierung usw.).
    *   `trigger_enabled`: (boolean) Ob der schwebende Auslöser für dieses Formular aktiv ist.
    *   `trigger_text`: (text) Text auf dem schwebenden Auslöser.
    *   `trigger_position`: (text) Position des schwebenden Auslösers.
    *   `trigger_icon`: (text) Symbolklasse für den Auslöser.
    *   `trigger_delay_ms`: (int) Verzögerung für das Erscheinen des Auslösers.
    *   `trigger_color`, `trigger_text_color`, `trigger_hover_color`: (text) Styling für den Auslöser.
-   `ps_cfrompro_question`: Speichert jede eingereichte Frage/Anfrage.
    *   `id_cfrompro_question`: Primärschlüssel.
    *   `id_cfrompro_form`: Fremdschlüssel zu `ps_cfrompro_form`.
    *   `customer_name`: Name des absendenden Kunden.
    *   `customer_email`: E-Mail des absendenden Kunden.
    *   `customer_phone`: Telefonnummer (falls sichtbar/erforderlich).
    *   `topic`: Ausgewähltes Thema (falls sichtbar/erforderlich).
    *   `message`: Der Hauptfragen-/Nachrichteninhalt.
    *   `submitted_data_json`: (text/JSON) Serialisierter JSON-String, der alle übermittelten benutzerdefinierten Feldwerte enthält.
    *   `attachments`: (text/JSON) Pfad(e) zu hochgeladenen Dateien.
    *   `ip_address`: IP-Adresse des Absenders.
    *   `date_add`: Einreichungszeitstempel.
    *   `status`: (int/text) Status der Anfrage (z. B. 0=Neu, 1=In Bearbeitung, 2=Gelöst).
-   `ps_configuration`: Moduleinstellungen werden hier mit Schlüsseln wie `cfrompro_TITLE`, `cfrompro_AUTORESPONDER`, `cfrompro_GDPR`, `cfrompro_recaptcha_sitekey` usw. gespeichert.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionOutputHTMLBefore` | Bevor die HTML-Ausgabe an den Browser gesendet wird. | Einfügen von schwebendem Auslöser-HTML, modalen Formularen oder benutzerdefiniertem CSS/JS global. |
| `displaydashboardZoneTwo` | Rendert Inhalte in der zweiten Zone des PrestaShop-Dashboards. | Anzeige einer Zusammenfassung der letzten Formular-Einreichungen im Back Office. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Medien (JS/CSS) einstellt. | Einreihen von Back-Office-spezifischem JS (`admin-button-style.js`, `admin-form-layout.js` usw.) und CSS (`admin-button-style.css`, `admin-custom-fields.css` usw.) für die Konfigurationsseiten des Moduls. |
| `displayHeader` | Im `<head>`-Bereich des Front-Office. | Einreihen von Front-Office-spezifischem JS (`cfrompro.js`) und CSS (`cfrompro.css`) sowie potenziell reCAPTCHA-Skripten. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul **Advanced Contact Form Builder Pro** zur Verfügung.

---
title: "Produkt anfragen kostenlos - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Produkt anfragen kostenlos“ von MyPresta.eu."
sidebar:
  label: "Produkt anfragen kostenlos - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Ask about product free auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/ask-about-product-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/ask-about-product-free/)
>
> ---


# Produkt anfragen kostenlos

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Produkt anfragen kostenlos“, auf dem Sie dessen Verhalten und Aussehen steuern.

- **Menüpfad:** Back Office > Module > Modul-Manager > „Produkt anfragen kostenlos“ > Konfigurieren

#### Einstellungen & Optionen:

1. **Produktzusammenfassung im Popup anzeigen**

   - **Was diese Einstellung bewirkt:** Steuert, ob eine kleine Zusammenfassung des Produkts (wie Name und Bild) im Popup-Formular „Produkt anfragen“ angezeigt wird.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn aktiviert (Ja):* Das Popup-Formular enthält eine kurze Übersicht über das Produkt, zu dem der Kunde anfragt. Dies hilft dem Kunden zu bestätigen, dass er nach dem richtigen Artikel fragt, und bietet Ihnen Kontext, wenn Sie die E-Mail erhalten.
     - *Wenn deaktiviert (Nein):* Das Popup-Formular enthält nur die Felder für den Namen des Kunden, die E-Mail-Adresse und die Frage, ohne eine produktspezifische Zusammenfassung.
   - **Empfohlener Wert:** **Ja**.
   - **Händlerszenario / Beispiel:** Das Aktivieren hilft, Verwirrung zu vermeiden. Ein Kunde könnte mehrere Tabs geöffnet haben und vergessen, nach welchem Produkt er fragt. Die Zusammenfassung bestätigt es für ihn und für Sie.
2. **Aktiviert**

   - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der gesamten „Produkt anfragen“-Funktion in Ihrem Shop.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn aktiviert (Ja):* Der „Produkt anfragen“-Button wird auf den Produktseiten angezeigt, und das Popup-Formular ist funktionsfähig.
     - *Wenn deaktiviert (Nein):* Der „Produkt anfragen“-Button wird auf den Produktseiten ausgeblendet, und Kunden können diese Funktion nicht nutzen.
   - **Empfohlener Wert:** **Ja** (um das Modul zu verwenden).
   - **Händlerszenario / Beispiel:** Sie könnten es vorübergehend deaktivieren, wenn Sie Wartungsarbeiten durchführen oder wenn Sie alle Anfragen für einen bestimmten Zeitraum über einen anderen Kanal bearbeiten möchten.
3. **DSGVO-konform**

   - **Was diese Einstellung bewirkt:** Aktiviert ein Kontrollkästchen im Formular „Produkt anfragen“, das Kunden auffordert, Ihrer Datenschutzerklärung explizit zuzustimmen, bevor sie ihre Frage absenden. Dies hilft Ihrem Shop, die DSGVO und andere Datenschutzbestimmungen einzuhalten.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn aktiviert (Ja):* Ein obligatorisches Kontrollkästchen erscheint im Formular, typischerweise mit der Aufschrift „Ich stimme der Datenschutzerklärung zu.“ Der Kunde muss dieses Kästchen aktivieren, um seine Frage abzusenden.
     - *Wenn deaktiviert (Nein):* Das Kontrollkästchen für die Datenschutzerklärung wird nicht angezeigt, und Kunden können ihre Fragen ohne explizite Zustimmung absenden.
   - **Empfohlener Wert:** **Ja**.
   - **Händlerszenario / Beispiel:** Wenn Ihr Shop in Regionen mit strengen Datenschutzgesetzen (wie der EU) betrieben wird, ist die Aktivierung dieser Funktion für die Einhaltung der gesetzlichen Bestimmungen entscheidend.
4. **Seite der Datenschutzerklärung**

   - **Was diese Einstellung bewirkt:** Wenn „DSGVO-konform“ aktiviert ist, können Sie mit dieser Einstellung auswählen, welche CMS-Seite (Content Management System) aus Ihrem Shop als Ihre Datenschutzerklärung verlinkt werden soll.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn eine Seite ausgewählt ist:* Der Text „Ich stimme der Datenschutzerklärung zu“ im Popup-Formular enthält einen anklickbaren Link zur ausgewählten CMS-Seite, sodass Kunden Ihre Richtlinie leicht überprüfen können.
     - *Wenn keine Seite ausgewählt ist (oder DSGVO-konform auf Nein steht):* Es wird kein Link bereitgestellt, oder die DSGVO-Funktion ist nicht aktiv.
   - **Empfohlener Wert:** Wählen Sie die offizielle Datenschutzerklärung Ihres Shops aus.
   - **Händlerszenario / Beispiel:** Sie müssen eine dedizierte CMS-Seite haben, die Ihre Datenverarbeitungspraktiken darlegt. Diese Einstellung stellt sicher, dass Kunden leicht darauf zugreifen können.
5. **E-Mail-Titel**

   - **Was diese Einstellung bewirkt:** Definiert die Betreffzeile für die E-Mail, die Sie erhalten, wenn ein Kunde eine Frage über das Formular absendet.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn ein spezifischer Titel festgelegt ist (z.B. „Neue Produktanfrage“):* Alle eingehenden E-Mails von diesem Modul verwenden diese Betreffzeile, wodurch sie in Ihrem Posteingang leicht zu identifizieren sind.
     - *Wenn Standard belassen:* Das Modul verwendet seine Standard-Betreffzeile, die möglicherweise weniger aussagekräftig ist.
   - **Empfohlener Wert:** Etwas Klares und Beschreibendes, wie „Neue Produktanfrage von [Name Ihres Shops]“.
   - **Händlerszenario / Beispiel:** Eine klare Betreffzeile hilft Ihnen, Kundenanfragen schnell zu priorisieren und zu beantworten, insbesondere wenn Sie täglich viele E-Mails erhalten.
6. **Empfänger der E-Mail aus dem Formular**

   - **Was diese Einstellung bewirkt:** Gibt die E-Mail-Adresse(n) an, an die Kundenfragen, die über das Formular „Produkt anfragen“ gesendet werden, gesendet werden.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn eine oder mehrere E-Mail-Adressen eingegeben werden (durch Kommas getrennt):* Das Modul sendet alle Kundenanfragen an diese angegebenen Adressen.
     - *Wenn leer gelassen:* Das Modul könnte standardmäßig die Hauptkontakt-E-Mail des Shops verwenden, oder die Funktion funktioniert möglicherweise nicht richtig.
   - **Empfohlener Wert:** Ihre Kundendienst-E-Mail-Adresse (z.B. `support@ihrshop.com`) oder eine dedizierte E-Mail für Produktanfragen. Sie können mehrere E-Mails durch Kommas getrennt hinzufügen, wenn mehrere Teammitglieder diese erhalten sollen.
   - **Händlerszenario / Beispiel:** Das Weiterleiten dieser E-Mails an das richtige Team gewährleistet schnelle Antworten und verbessert die Kundenzufriedenheit.
7. **ReCaptcha-Schutz (v2)**

   - **Was diese Einstellung bewirkt:** Integriert Google reCAPTCHA v2 (das Kontrollkästchen „Ich bin kein Roboter“) in das Formular „Produkt anfragen“, um vor Spam und automatisierten Übermittlungen zu schützen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn aktiviert (Ja):* Das reCAPTCHA-Kontrollkästchen erscheint im Formular und erfordert, dass Kunden die Herausforderung bestehen, bevor sie absenden.
     - *Wenn deaktiviert (Nein):* Das Formular hat keinen reCAPTCHA-Schutz und ist potenziell anfällig für Spam-Bots.
   - **Empfohlener Wert:** **Ja**.
   - **Händlerszenario / Beispiel:** Wenn Sie viele Spam-Anfragen über das Formular erhalten, ist die Aktivierung von reCAPTCHA unerlässlich, um illegitime Nachrichten herauszufiltern.
8. **reCaptcha-Site-Key**

   - **Was diese Einstellung bewirkt:** Dies ist der öffentliche Schlüssel, der von Google reCAPTCHA bereitgestellt wird und es Ihrer Website ermöglicht, das reCAPTCHA-Widget anzuzeigen. Sie erhalten diesen Schlüssel, wenn Sie Ihre Website bei Google reCAPTCHA registrieren.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn korrekt eingegeben:* Das reCAPTCHA-Widget wird korrekt angezeigt und funktioniert in Ihrem Formular.
     - *Wenn falsch oder leer:* reCAPTCHA funktioniert nicht, und Sie sehen möglicherweise eine Fehlermeldung oder das Formular wird nicht gesendet.
   - **Empfohlener Wert:** Der Site-Key, den Sie von Ihrem Google reCAPTCHA-Konto erhalten haben.
   - **Händlerszenario / Beispiel:** Sie müssen Ihre Domain bei Google reCAPTCHA (v2) registrieren, um sowohl einen Site-Key als auch einen Secret-Key zu erhalten.
9. **reCaptcha-Secret-Key**

   - **Was diese Einstellung bewirkt:** Dies ist der private Schlüssel, der von Google reCAPTCHA bereitgestellt wird und es Ihrem Server ermöglicht, die reCAPTCHA-Antwort zu überprüfen. Er wird für die serverseitige Validierung verwendet.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn korrekt eingegeben:* Ihr Server kann erfolgreich überprüfen, ob ein Kunde die reCAPTCHA-Herausforderung bestanden hat.
     - *Wenn falsch oder leer:* Selbst wenn das reCAPTCHA-Widget angezeigt wird, schlägt die Formularübermittlung die Validierung fehl, und die Frage wird nicht gesendet.
   - **Empfohlener Wert:** Der Secret-Key, den Sie von Ihrem Google reCAPTCHA-Konto erhalten haben.
   - **Händlerszenario / Beispiel:** Dieser Schlüssel ist entscheidend für den Sicherheitsaspekt von reCAPTCHA, um sicherzustellen, dass nur legitime Übermittlungen verarbeitet werden.

#### Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Produktzusammenfassung im Popup anzeigen | Ja | Zeigt Produktdetails im Popup zur Klarheit an. |
| Modulkonfiguration | Aktiviert | Ja | Aktiviert/deaktiviert die Funktion „Produkt anfragen“. |
| Modulkonfiguration | DSGVO-konform | Ja | Fügt ein Kontrollkästchen für die Datenschutzerklärung zum Formular hinzu. |
| Modulkonfiguration | Seite der Datenschutzerklärung | Wählen Sie Ihre CMS-Datenschutzerklärung aus | Verlinkt zur Datenschutzerklärung Ihres Shops für die DSGVO. |
| Modulkonfiguration | E-Mail-Titel | „Neue Produktanfrage von [Name Ihres Shops]“ | Legt die Betreffzeile für eingehende Anfragen-E-Mails fest. |
| Modulkonfiguration | Empfänger der E-Mail aus dem Formular | Ihre Kundendienst-E-Mail (z.B. `support@ihrshop.com`) | Gibt an, wohin Kundenfragen gesendet werden. |
| Modulkonfiguration | ReCaptcha-Schutz (v2) | Ja | Aktiviert Google reCAPTCHA, um Spam zu verhindern. |
| Modulkonfiguration | reCaptcha-Site-Key | Ihr Google reCAPTCHA Site Key | Öffentlicher Schlüssel zum Anzeigen des reCAPTCHA-Widgets. |
| Modulkonfiguration | reCaptcha-Secret-Key | Ihr Google reCAPTCHA Secret Key | Privater Schlüssel für die serverseitige reCAPTCHA-Validierung. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### AdminAapfreeQuestionController (Back Office > Produkt anfragen > Fragen)

Dieser dedizierte Administrationsbildschirm ermöglicht es Ihnen, alle über das Formular „Produkt anfragen“ eingereichten Fragen anzuzeigen und zu verwalten.

- **Bildschirmname & Menüpfad:** Back Office > **Produkt anfragen** (neuer Menüpunkt) > **Fragen**
- **Verfügbare Aktionen & Einstellungen:**
  - **Auflistungstabelle:** Dieser Bildschirm zeigt eine Tabelle aller eingereichten Fragen an. Jede Zeile zeigt typischerweise:
    - **ID:** Eindeutige Kennung für die Frage.
    - **Kundenname:** Der vom Kunden angegebene Name.
    - **Kunden-E-Mail:** Die vom Kunden angegebene E-Mail-Adresse.
    - **Produktname:** Der Name des Produkts, um das es in der Frage geht.
    - **Frage:** Ein Ausschnitt oder der vollständige Text der Kundenfrage.
    - **Hinzugefügt am:** Wann die Frage eingereicht wurde.
    - **Status:** (z.B. Neu, Beantwortet, Ausstehend) - *Hinweis: Das Moduldossier gibt kein explizites Statusfeld an, aber es ist ein häufiges Merkmal für solche Listen. Falls nicht vorhanden, werden einfach alle Fragen aufgelistet.*
  - **Details anzeigen:** Sie können normalerweise auf eine Frage in der Liste klicken, um deren vollständige Details anzuzeigen, einschließlich des vollständigen Fragetextes und möglicherweise des Produktlinks.
  - **Löschen:** Optionen zum Löschen einzelner Fragen oder möglicherweise zum Massenlöschen ausgewählter Fragen.
- **Auswirkung von Änderungen:**
  - **Fragen anzeigen:** Ermöglicht Ihnen, alle Kundenanfragen an einem zentralen Ort in Ihrem PrestaShop Back Office zu überprüfen, auch wenn Sie diese auch per E-Mail erhalten.
  - **Fragen löschen:** Entfernt den Fragen-Datensatz aus Ihrer Datenbank. Dies ist nützlich, um alte oder irrelevante Anfragen zu bereinigen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Überprüfen Sie regelmäßig diese „Fragen“-Liste (oder Ihren E-Mail-Posteingang, wie konfiguriert) auf neue Anfragen.
  2. Priorisieren und beantworten Sie Fragen umgehend, um einen guten Kundenservice aufrechtzuerhalten.
  3. Nach der Beantwortung können Sie die Frage aus dieser Liste löschen, um sie übersichtlich zu halten, oder, falls das Modul dies unterstützt, als „Beantwortet“ markieren.

#### index.php (aapfree/controllers/admin/index.php)

Diese Datei ist typischerweise ein Platzhalter oder eine Weiterleitung innerhalb des Verzeichnisses `controllers/admin` und stellt keinen eigenständigen, konfigurierbaren Bildschirm für den Händler dar. Es ist eine Standard-PrestaShop-Praxis, eine `index.php` in Unterverzeichnissen zu haben, um die Verzeichnisauflistung zu verhindern, oder sie könnte grundlegende Routing-Logik enthalten. Sie verwaltet keine spezifische Tabelle oder Entität für die direkte Interaktion des Händlers.

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der Button „Produkt anfragen“ wird auf meinen Produktseiten nicht angezeigt.**

- **A:** Überprüfen Sie zunächst, ob das Modul in seinen Konfigurationseinstellungen „Aktiviert“ ist (Back Office > Module > Modul-Manager > Produkt anfragen kostenlos > Konfigurieren). Wenn ja, versuchen Sie, Ihren PrestaShop-Cache zu leeren (Erweiterte Einstellungen > Leistung > Cache leeren). Manchmal können Theme-Konflikte oder spezifische benutzerdefinierte Theme-Strukturen das Erscheinen des Buttons verhindern. Wenn er immer noch fehlt, wenden Sie sich an Ihren Webmaster oder den MyPresta.eu-Support.

**F2: Ich erhalte keine E-Mails, wenn Kunden Fragen senden.**

- **A:**
  1. Überprüfen Sie die Einstellung „Empfänger der E-Mail aus dem Formular“ in der Modulkonfiguration. Stellen Sie sicher, dass die E-Mail-Adresse(n) korrekt und durch Kommas getrennt sind, falls es mehrere gibt.
  2. Überprüfen Sie Ihren Spam-/Junk-Ordner im Posteingang des Empfängers.
  3. Stellen Sie sicher, dass die E-Mail-Einstellungen Ihres Shops in PrestaShop korrekt konfiguriert sind (Erweiterte Einstellungen > E-Mail). Testen Sie das Senden einer allgemeinen E-Mail von PrestaShop, um zu bestätigen, dass Ihr Mailserver funktioniert.
  4. Wenn ReCAPTCHA aktiviert ist, stellen Sie sicher, dass sowohl der „reCaptcha-Site-Key“ als auch der „reCaptcha-Secret-Key“ korrekt eingegeben wurden. Falsche Schlüssel verhindern die Übermittlung.

**F3: Das reCAPTCHA funktioniert nicht, oder ich sehe eine Fehlermeldung.**

- **A:** Dies bedeutet normalerweise, dass Ihre reCAPTCHA-Schlüssel falsch oder nicht richtig bei Google konfiguriert sind.
  1. Gehen Sie zur Google reCAPTCHA-Admin-Konsole und stellen Sie sicher, dass Ihre Domain korrekt für reCAPTCHA v2 registriert ist.
  2. Kopieren Sie den „Site Key“ und den „Secret Key“ genau wie von Google bereitgestellt und fügen Sie sie in die Konfigurationsfelder des Moduls ein.
  3. Leeren Sie Ihren PrestaShop-Cache, nachdem Sie Änderungen vorgenommen haben.

**F4: Wie ändere ich den Text auf dem Button „Produkt anfragen“ oder im Popup-Formular?**

- **A:** Sie können die Textzeichenfolgen des Moduls direkt in PrestaShop übersetzen. Gehen Sie zu **International > Übersetzungen**, wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Produkt anfragen kostenlos“. Dort finden Sie alle übersetzbaren Zeichenfolgen, einschließlich Button-Beschriftungen, Formularfeld-Beschriftungen und Bestätigungsnachrichten.

**F5: Das Popup sieht seltsam aus oder wird auf meinem Mobiltelefon nicht richtig angezeigt.**

- **A:** Obwohl das Modul responsiv gestaltet ist, können benutzerdefinierte Themes manchmal dessen Styling überschreiben oder damit in Konflikt geraten.
  1. Leeren Sie Ihren Browser-Cache und den PrestaShop-Cache.
  2. Wenn das Problem weiterhin besteht, handelt es sich wahrscheinlich um einen CSS-Konflikt mit Ihrem Theme. Ihr Webmaster oder ein Entwickler müsste die Seite mit den Browser-Entwicklertools untersuchen, um den CSS-Konflikt zu identifizieren und zu beheben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Produkt anfragen kostenlos“ folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller), das sich hauptsächlich auf die Front-Office-Interaktion und die Back-Office-Verwaltung eingereichter Fragen konzentriert. Es nutzt das Hook-System von PrestaShop zur Integration in Produktseiten und verwendet dedizierte Front-Controller für AJAX-Anfragen und Formularübermittlungen. Die Back-Office-Komponente bietet eine einfache Listenverwaltungsschnittstelle für Fragen.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/index.php`
    - **Klassenname & Elternklasse:** `AapfreeIndexModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit:** Dieser Controller behandelt wahrscheinlich die anfängliche Anzeigelogik für die Front-Office-Komponente des Moduls, möglicherweise das Rendern des Buttons oder das Vorbereiten von Daten für das Popup. Er könnte auch als Auffangbecken für modulspezifische Front-Office-Routen dienen.
  - `controllers/front/question.php`
    - **Klassenname & Elternklasse:** `AapfreeQuestionModuleFrontController` erweitert `ModuleFrontController`.
    - **Verantwortlichkeit:** Dies ist der Kern-Controller für die Bearbeitung der Formularübermittlung „Produkt anfragen“. Er empfängt POST-Daten vom Popup-Formular, validiert Eingaben (einschließlich reCAPTCHA, falls aktiviert), verarbeitet die Frage, sendet die E-Mail an die konfigurierten Empfänger und speichert die Frage in der Datenbank. Er gibt JSON-Antworten für AJAX-Anfragen zurück (z.B. Erfolgs-/Fehlermeldungen).
- **Back-Office-Admin-Controller**:

  - `controllers/admin/AdminAapfreeQuestion.php`
    - **Klassenname & Elternklasse:** `AdminAapfreeQuestionController` erweitert `ModuleAdminController`.
    - **Tab-Name und verwaltete Entität:** Dieser Controller erstellt und verwaltet den Tab „Fragen“ unter dem Menü „Produkt anfragen“ im PrestaShop Back Office. Er ist verantwortlich für die Anzeige einer Liste (Raster) aller eingereichten Fragen, die es Administratoren ermöglicht, Details anzuzeigen und Einträge zu löschen. Er interagiert mit dem `AapfreeQuestion` `ObjectModel` (falls vorhanden, ansonsten direkt mit der Datenbank).
  - `controllers/admin/index.php`
    - **Klassenname & Elternklasse:** Kein funktionaler Controller im traditionellen Sinne.
    - **Tab-Name und verwaltete Entität:** Diese Datei ist eine Standard-PrestaShop-Sicherheitsmaßnahme, um die Verzeichnisauflistung zu verhindern. Sie enthält typischerweise ein einfaches `header('Location: ../../index.php?controller=AdminHome');` oder eine ähnliche Weiterleitung, oder einfach `<?php exit;`. Sie verwaltet keine spezifische Entität und bietet keinen konfigurierbaren Bildschirm.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Dies deutet darauf hin, dass das Modul Datenbankinteraktionen direkt in seinen Controllern oder der Hauptmoduldatei handhaben könnte, oder es könnte ein generisches `ObjectModel` für `aapfreequestion` verwenden, falls es implizit definiert ist.

- **Implizites Modell (wahrscheinlich):** Angesichts der Tatsache, dass der `AdminAapfreeQuestionController` eine Tabelle verwaltet, gibt es ein implizites `AapfreeQuestion`-Modell, auch wenn es nicht explizit in `classes/` vorhanden ist. Dieses Modell würde der Datenbanktabelle `_aapfree_question` zugeordnet.
  - **Datenbanktabelle:** `ps_aapfree_question` (oder ähnlich, basierend auf dem Modulpräfix).
  - **Erweitert `ObjectModel`:** Ja, implizit.
  - **`$definition`-Felder (erwartet):** `id_aapfree_question`, `id_product`, `customer_name`, `customer_email`, `question_text`, `date_add`.

### 4.4 JavaScript-Assets (`views/js/`)

- `aapfree/views/aapfree.js`
  - **Umfang:** Front-Office.
  - **Ereignis-Listener:**
    - Bindet Klick-Ereignisse an den Button „Produkt anfragen“ (`.aapfree-button`).
    - Bindet Submit-Ereignisse an das Formular „Produkt anfragen“ innerhalb des Popups (`#aapfree-form`).
    - Behandelt Ereignisse im Zusammenhang mit dem reCAPTCHA-Widget (falls aktiviert).
  - **DOM-Manipulation:**
    - Öffnet und schließt das modale Popup (`#aapfree-modal`).
    - Füllt Produktsummen-Daten in das Popup.
    - Zeigt Erfolgs- oder Fehlermeldungen an den Benutzer nach dem Absenden des Formulars.
    - Verwaltet Formularfeldzustände (z.B. Deaktivieren des Absende-Buttons während AJAX).
  - **AJAX-Aufrufe:**
    - Sendet Formulardaten an den `AapfreeQuestionModuleFrontController` (z.B. `index.php?fc=module&module=aapfree&controller=question`).
    - Verarbeitet JSON-Antworten vom Server.
  - **Externe SDK-Aufrufe:** Initialisiert und rendert das Google reCAPTCHA v2-Widget, falls `aapfree_recaptcha` aktiviert ist, unter Verwendung des `aapfree_recaptcha_sitekey`.

### 4.5 CSS-Stylesheets (`views/css/`)

- `aapfree/views/aapfree.css`
  - **Umfang:** Front-Office-Kunden-Styling.
  - **Haupt-UI-Komponenten und Container, die es stylt:**
    - Der Button „Produkt anfragen“ (`.aapfree-button`).
    - Der modale Popup-Container (`#aapfree-modal`).
    - Die Formularelemente innerhalb des Popups (Eingabefelder, Textbereiche, Labels, Kontrollkästchen).
    - Anzeigen von Erfolgs- und Fehlermeldungen.
    - Responsive Anpassungen für verschiedene Bildschirmgrößen.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** `.aapfree-button`, `.aapfree-modal`, `.aapfree-modal-content`, `.aapfree-form-group`, `.aapfree-product-summary`, `.aapfree-success-message`, `.aapfree-error-message`. Entwickler können diese Stile in der `custom.css` ihres Themes oder durch die Verwendung der PrestaShop-Theme-Anpassungsfunktionen überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `aapfree/views/aapfree-extra.tpl`
    - **Hook:** `displayProductAdditionalInfo` (oder ähnlicher Produktseiten-Hook wie `displayProductButtons`, `displayProductActions`).
    - **Visuelle Blockausgabe:** Dieses Template ist für das Rendern des Buttons „Produkt anfragen“ auf der Produktseite verantwortlich. Es enthält auch die HTML-Struktur für das modale Popup-Formular, das anfänglich ausgeblendet ist und über JavaScript angezeigt wird. Es enthält Platzhalter für die Produktzusammenfassung, Formularfelder, DSGVO-Kontrollkästchen und reCAPTCHA.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_aapfree_question`:
    - `id_aapfree_question` (INT, PRIMARY KEY, AUTO_INCREMENT)
    - `id_product` (INT, Fremdschlüssel zu `ps_product`)
    - `customer_name` (VARCHAR)
    - `customer_email` (VARCHAR)
    - `question_text` (TEXT)
    - `date_add` (DATETIME)
    - (Potenziell weitere Felder wie `ip_address`, `status`, `id_customer`, falls implementiert)
  - **Konfigurationsdatensätze (in `ps_configuration`):**
    - `AAPFREE_TITLE`: E-Mail-Betreffzeile.
    - `AAPFREE_GDPR`: DSGVO-Konformitätsstatus (0/1).
    - `AAPFREE_GDPRCMS`: ID der CMS-Seite für die Datenschutzerklärung.
    - `AAPFREE_SUMMARY`: Status der Produktzusammenfassungsanzeige (0/1).
    - `AAPFREE_RECAPTCHA`: reCAPTCHA-Schutzstatus (0/1).
    - `AAPFREE_RECAPTCHA_SITEKEY`: Google reCAPTCHA Site Key.
    - `AAPFREE_RECAPTCHA_SECRETKEY`: Google reCAPTCHA Secret Key.
    - `AAPFREE_EMAILSLIST`: Kommagetrennte Liste der Empfänger-E-Mails.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayProductAdditionalInfo` | Auf Produktseiten, typischerweise unterhalb der Produktbeschreibung oder des Preises. | Rendert den Button „Produkt anfragen“ und die versteckte modale Popup-Struktur. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Assets (CSS/JS) lädt. | Fügt modulspezifisches CSS (`aapfree.css`) und JavaScript (`aapfree.js`) in das Back Office für den `AdminAapfreeQuestionController` ein. |
| `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Potenziell zum Laden globaler JavaScript-Variablen, CSS oder des Google reCAPTCHA API-Skripts, falls reCAPTCHA aktiviert ist. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul „Produkt anfragen kostenlos“ besuchen Sie bitte Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Team ist bestrebt, den reibungslosen Betrieb und die kontinuierliche Verbesserung Ihres Moduls sicherzustellen.

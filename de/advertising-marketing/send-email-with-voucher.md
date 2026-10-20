---
title: "E-Mail mit Gutschein senden - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „E-Mail mit Gutschein senden“ von MyPresta.eu."
sidebar:
  label: "E-Mail mit Gutschein senden - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Send email with voucher auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/send-email-with-voucher.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/send-email-with-voucher/)
>
> ---


# E-Mail mit Gutschein senden

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und in jeder modernen Hosting-Umgebung normalerweise verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > E-Mail mit Gutschein senden)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie die Einstellungen für den Versand Ihrer Gutschein-E-Mails verwalten.

#### **Abschnitt E-Mail-Vorlagen-Manager**

In diesem Abschnitt definieren Sie den Inhalt und das Erscheinungsbild der E-Mails, die Ihre Gutscheincodes enthalten.

-   **Was dieser Abschnitt leistet:** Dieses leistungsstarke Tool ermöglicht es Ihnen, verschiedene E-Mail-Vorlagen zu erstellen, zu bearbeiten und zu verwalten. Jede Vorlage kann eine eigene Betreffzeile und einen eigenen Inhalt haben, was es einfach macht, verschiedene Arten von Gutscheinangeboten zu versenden (z. B. „Willkommensrabatt“, „Geburtstagsgeschenk“, „Angebot für abgebrochenen Warenkorb“).
-   **Auswirkungen von Einstellungsänderungen:**
    *   *Erstellen einer neuen Vorlage:* Sie definieren ein neues E-Mail-Design und eine Betreffzeile, die Sie später beim Versenden von Gutscheinen auswählen können.
    *   *Bearbeiten einer bestehenden Vorlage:* Änderungen am Betreff oder Inhalt gelten für alle zukünftigen E-Mails, die mit dieser spezifischen Vorlage gesendet werden.
    *   *Löschen einer Vorlage:* Die Vorlage steht nicht mehr zur Auswahl.
-   **Empfohlener Arbeitsablauf:** Beginnen Sie damit, einige Standardvorlagen für Ihre häufigsten Gutscheinkampagnen zu erstellen. Zum Beispiel eine „Willkommens“-Vorlage für neue Kunden, eine „Treue“-Vorlage für Stammkäufer und eine „Sonderangebot“-Vorlage für Aktionen.

#### **Abschnitt Gutschein-Engine**

In diesem Abschnitt generieren und versenden Sie die Gutscheincodes.

-   **Was dieser Abschnitt leistet:** Dies ist die Kernfunktionalität zum Erstellen von Rabattregeln (Gutscheinen) und zum Senden an bestimmte E-Mail-Adressen. Sie können den Rabatttyp (Prozentsatz, fester Betrag), den Wert, Bedingungen (Mindestbestellwert, bestimmte Produkte) und den Gültigkeitszeitraum definieren.
-   **Auswirkungen von Einstellungsänderungen:**
    *   *Erstellen eines neuen Gutscheins:* Eine neue Rabattregel wird in Ihrem PrestaShop-Katalog erstellt und ein einzigartiger Code generiert.
    *   *Senden eines Gutscheins:* Eine E-Mail mit dem einzigartigen Code und dem Inhalt der ausgewählten Vorlage wird an den/die angegebenen Empfänger versandt.
    *   *Verknüpfung mit einem Kunden:* Der Gutschein kann mit dem Konto eines bestimmten Kunden verknüpft werden, was bedeutet, dass nur dieser Kunde ihn verwenden kann.
-   **Empfohlener Arbeitsablauf:**
    1.  Erstellen oder wählen Sie zunächst eine geeignete E-Mail-Vorlage aus dem Abschnitt „E-Mail-Vorlagen-Manager“.
    2.  Verwenden Sie dann die „Gutschein-Engine“, um Ihre Rabattparameter zu definieren (z. B. 10 % Rabatt, gültig für 30 Tage, Mindestbestellwert 50 $).
    3.  Geben Sie die E-Mail-Adresse(n) des Empfängers an.
    4.  Wählen Sie, ob der Gutschein mit einem bestehenden Kundenkonto verknüpft werden soll.
    5.  Klicken Sie auf „Senden“, um den personalisierten Gutschein zu generieren und zu versenden.

#### **Spezifische Einstellungen innerhalb der Konfigurationsseite**

Obwohl die primäre Schnittstelle des Moduls über die Abschnitte „E-Mail-Vorlagen-Manager“ und „Gutschein-Engine“ erfolgt, gibt es zugrunde liegende Konfigurationsschlüssel, die das Standardverhalten steuern. Diese werden oft implizit von der Moduloberfläche verwaltet, aber es ist gut, ihren Zweck zu verstehen.

-   **Mail-Titel**

    -   **Was diese Einstellung bewirkt:** Dies ist die Standard-Betreffzeile für die mit Gutscheinen gesendeten E-Mails, falls sie nicht durch eine spezifische Vorlage überschrieben wird.
    -   **Auswirkungen einer Änderung dieser Einstellung:**
        -   *Wenn auf „Ihr besonderer Rabatt“ eingestellt:* E-Mails verwenden standardmäßig diese Betreffzeile.
        -   *Wenn auf „Exklusives Angebot von [Ihr Shop-Name]“ geändert:* Alle neuen E-Mails (ohne eine spezifische Vorlage, die sie überschreibt) verwenden diesen neuen Betreff.
    -   **Empfohlener Wert:** Etwas Klares und Verlockendes, wie „Ihr exklusiver Gutschein von [Ihr Shop-Name]“.
    -   **Händlerszenario / Beispiel:** Sie möchten, dass alle Ihre Gutschein-E-Mails eine konsistente Markenbotschaft in der Betreffzeile haben.
-   **E-Mail-Vorlagendatei**

    -   **Was diese Einstellung bewirkt:** Dies bezieht sich auf die Standard-E-Mail-Vorlagendatei, die zum Versenden von Gutscheinen verwendet wird. Der Abschnitt „E-Mail-Vorlagen-Manager“ bietet eine benutzerfreundlichere Möglichkeit, Vorlagen zu verwalten und auszuwählen.
    -   **Auswirkungen einer Änderung dieser Einstellung:**
        -   *Wenn auf `voucher_email.html` eingestellt:* Das Modul verwendet diese spezifische Datei für den E-Mail-Text, wenn keine andere Vorlage ausgewählt ist.
    -   **Empfohlener Wert:** Verwenden Sie die Oberfläche des „E-Mail-Vorlagen-Managers“, um Vorlagen zu erstellen und auszuwählen, da dies flexibler ist und keine direkte Dateimanipulation erfordert.
    -   **Händlerszenario / Beispiel:** Sie haben eine benutzerdefinierte HTML-E-Mail-Vorlagendatei, die Sie als Basis für alle Ihre Gutschein-E-Mails verwenden möchten.

#### **Weitere Konfigurationsschlüssel (Intern)**

Dies sind interne PrestaShop-Konfigurationsschlüssel, auf die das Modul für seine Operationen verweisen könnte, die Sie jedoch normalerweise nicht direkt in der Moduloberfläche konfigurieren werden.

-   `PS_SHOP_EMAIL`: Die Hauptkontakt-E-Mail-Adresse Ihres Shops. Wird als Absender-E-Mail für Gutscheine verwendet.
-   `PS_SHOP_NAME`: Der Name Ihres Shops. Wird in E-Mail-Betreffzeilen oder -Texten verwendet.
-   `PS_LANG_DEFAULT`: Die Standardsprache Ihres Shops.
-   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Einstellung bezüglich der Mitarbeitersprache im Back Office.
-   `mypresta_updates`, `update_`, `updatev_`: Interne Schlüssel, die von MyPresta.eu-Modulen für Update-Prüfungen und Versionsverwaltung verwendet werden.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | **E-Mail-Vorlagen-Manager** | N/A (nach Bedarf erstellen) | Erstellen und Verwalten benutzerdefinierter E-Mail-Vorlagen für Gutschein-E-Mails. |
| Modulkonfigurationsseite | **Gutschein-Engine** | N/A (nach Bedarf erstellen) | Generieren Sie einzigartige Gutscheincodes mit spezifischen Regeln und versenden Sie diese per E-Mail. |
| Modulkonfigurationsseite | Mail-Titel | „Ihr besonderer Rabatt“ (Beispiel) | Standard-Betreffzeile für Gutschein-E-Mails. |
| Modulkonfigurationsseite | E-Mail-Vorlagendatei | `voucher_email.html` (Beispiel) | Standard-HTML-Datei, die für den E-Mail-Inhalt verwendet wird. Verwenden Sie den E-Mail-Vorlagen-Manager für bessere Kontrolle. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kunden erhalten die Gutschein-E-Mails nicht. Was soll ich überprüfen?**
A:

1.  **Überprüfen Sie die E-Mail-Einstellungen Ihres Shops:** Gehen Sie in Ihrem PrestaShop-Back Office zu **Erweiterte Einstellungen > E-Mail**. Stellen Sie sicher, dass Ihre E-Mail-Konfiguration (SMTP oder PHP-Mail) korrekt ist und testen Sie den Versand einer allgemeinen E-Mail.
2.  **Spam-Ordner:** Bitten Sie Ihre Kunden, ihre Spam- oder Junk-Mail-Ordner zu überprüfen.
3.  **Inhalt der E-Mail-Vorlage:** Stellen Sie sicher, dass Ihre E-Mail-Vorlagen nicht zu „spammy“ sind (z. B. übermäßige Verwendung von Großbuchstaben, zu viele Ausrufezeichen).
4.  **Modul-Protokolle:** Überprüfen Sie, ob das Modul während des Sendeprozesses Protokolle oder Fehlermeldungen bereitstellt. (Dies erfordert möglicherweise Entwicklerhilfe).

**F: Der Gutscheincode wurde gesendet, aber der Kunde sagt, er funktioniert nicht.**
A:

1.  **Gutscheingültigkeit prüfen:** Gehen Sie in Ihrem PrestaShop-Back Office zu **Katalog > Rabatte > Warenkorbregeln**. Suchen Sie den Gutscheincode und überprüfen Sie dessen Gültigkeitsdaten, Mindestbetrag, Kundenbeschränkungen und ob er bereits verwendet wurde.
2.  **Kundenbindung:** Wenn der Gutschein einem bestimmten Kunden zugeordnet war, stellen Sie sicher, dass der Kunde im richtigen Konto angemeldet ist, wenn er versucht, ihn zu verwenden.
3.  **Tippfehler:** Bitten Sie den Kunden, den Code noch einmal auf Tippfehler zu überprüfen.

**F: Kann ich denselben Gutscheincode an mehrere Kunden senden?**
A: Ja, Sie können einen einzigen Gutscheincode generieren und an mehrere E-Mail-Adressen senden. Für eine bessere Nachverfolgung und zur Vermeidung von Missbrauch wird jedoch im Allgemeinen empfohlen, für jeden Empfänger einzigartige Codes zu generieren, insbesondere bei personalisierten Angeboten. Die „Gutschein-Engine“ des Moduls ist darauf ausgelegt, einzigartige Codes zu generieren.

**F: Wie passe ich das Aussehen der E-Mail-Vorlagen an?**
A: Verwenden Sie den Abschnitt „E-Mail-Vorlagen-Manager“ in der Modulkonfiguration. Er bietet eine Oberfläche zum Bearbeiten des Betreffs und des Inhalts Ihrer E-Mail-Vorlagen. Für fortgeschrittene HTML/CSS-Anpassungen müssen Sie möglicherweise die zugrunde liegenden Vorlagendateien bearbeiten (siehe Abschnitt 7 für Entwickler).

**F: Das Modul wird nach der Installation nicht korrekt angezeigt, oder ich sehe eine leere Seite.**
A:

1.  **Smarty-Cache leeren:** Gehen Sie in Ihrem PrestaShop-Back Office zu **Erweiterte Einstellungen > Performance**. Stellen Sie „Template-Kompilierung“ auf „Templates neu kompilieren, wenn die Dateien aktualisiert wurden“ und „Cache“ auf „Nein“. Klicken Sie dann oben rechts auf „Cache leeren“. Nach der Überprüfung können Sie „Cache“ wieder auf „Ja“ und „Template-Kompilierung“ auf „Nie neu kompilieren…“ für die Performance zurücksetzen.
2.  **PHP-Version prüfen:** Stellen Sie sicher, dass Ihre PHP-Version innerhalb des unterstützten Bereichs liegt (PHP 5.6 - 8.5).
3.  **Server-Fehlerprotokolle:** Überprüfen Sie die PHP-Fehlerprotokolle Ihres Servers auf spezifische Fehlermeldungen. Dies erfordert normalerweise Zugriff auf Ihr Hosting-Kontrollpanel.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „E-Mail mit Gutschein senden“ folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse für ihre Kernfunktionalität und Konfiguration nutzt. Es integriert benutzerdefiniertes JavaScript und CSS für seine Back-Office-Oberfläche, insbesondere für die E-Mail-Vorlagenverwaltung und die Gutscheingenerierungstools. Das Modul führt keine benutzerdefinierten Front-Office-Controller oder komplexen `ObjectModel`-Entitäten ein, sondern interagiert mit PrestaShops integrierten `CartRule`- (Rabatt) und `Mail`-Klassen.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Controller im Verzeichnis `controllers/`. Die gesamte administrative Logik und Konfiguration wird innerhalb der Methode `getContent()` der Hauptmoduldatei (`sendvouchers.php`) behandelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder Modelle innerhalb eines `classes/`-Verzeichnisses. Es stützt sich auf die Kernklassen von PrestaShop, wie `CartRule` für die Rabattverwaltung und `Mail` für den E-Mail-Versand.

### 4.4 JavaScript-Assets (`views/js/`)

-   **`sendvouchers/lib/emailTemplatesManager/js/emailTemplatesManager.js`**

    -   **Geltungsbereich:** Back-Office (Modulkonfigurationsseite).
    -   **Verantwortlichkeit:** Verwaltet die interaktiven Elemente der Benutzeroberfläche zur Erstellung, Bearbeitung und Löschung von E-Mail-Vorlagen. Dieses Skript verarbeitet wahrscheinlich AJAX-Aufrufe zum Speichern/Aktualisieren von Vorlagendaten, rendert Formulare dynamisch und verwaltet Benutzerinteraktionen innerhalb des Abschnitts „E-Mail-Vorlagen-Manager“. Es könnte jQuery für DOM-Manipulation und Ereignisbindung verwenden.
-   **`sendvouchers/lib/voucherengine/script.js`**

    -   **Geltungsbereich:** Back-Office (Modulkonfigurationsseite).
    -   **Verantwortlichkeit:** Betreibt den Abschnitt „Gutschein-Engine“. Dieses Skript ist verantwortlich für die Generierung von Gutscheincodes, die Einrichtung von Rabattregeln (z. B. Prozentsatz, fester Betrag, Bedingungen), die Auswahl von E-Mail-Vorlagen und die Initiierung des Gutscheinversandprozesses. Es führt wahrscheinlich clientseitige Validierungen und AJAX-Anfragen an die `getContent()`-Methode des Moduls zur serverseitigen Verarbeitung durch.

### 4.5 CSS-Stylesheets (`views/css/`)

-   **`sendvouchers/lib/emailTemplatesManager/css/emailTemplatesManager.css`**

    -   **Geltungsbereich:** Styling des Admin-Formulars im Back-Office.
    -   **Verantwortlichkeit:** Bietet Styling für die Benutzeroberfläche des „E-Mail-Vorlagen-Managers“, einschließlich Formularen zum Erstellen/Bearbeiten von Vorlagen, Schaltflächen und möglicherweise Listenansichten.
    -   **Wichtige CSS-Klassenselektoren:** Entwickler können die HTML-Ausgabe des Moduls im Back-Office überprüfen, um spezifische Klassen (z. B. `.email-template-form`, `.template-list-item`) für Überschreibungen in ihren benutzerdefinierten Admin-Themes oder über `override.css` zu identifizieren.
-   **`sendvouchers/lib/voucherengine/ps16.css`**

    -   **Geltungsbereich:** Styling des Admin-Formulars im Back-Office, speziell für PrestaShop 1.6-Kompatibilität.
    -   **Verantwortlichkeit:** Bietet Styling für den Abschnitt „Gutschein-Engine“, möglicherweise einschließlich Formularlayouts, Eingabefeldern und Schaltflächen, mit Anpassungen an das PrestaShop 1.6 Back-Office-Theme. Diese Datei könnte auch auf neueren PS-Versionen für Abwärtskompatibilität geladen werden, aber ihr Hauptzweck ist für PS 1.6.
    -   **Wichtige CSS-Klassenselektoren:** Ähnlich wie bei `emailTemplatesManager.css` sollten Entwickler die generierte HTML auf spezifische Selektoren überprüfen, die für Überschreibungen vorgesehen sind.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

Alle Vorlagen befinden sich im Verzeichnis `sendvouchers/lib/emailTemplatesManager/views/`, was darauf hindeutet, dass sie hauptsächlich zum Rendern der Back-Office-Oberfläche des E-Mail-Vorlagen-Managers verwendet werden.

-   **`sendvouchers/lib/emailTemplatesManager/views/buttonManager.tpl`**

    -   **Geltungsbereich:** Admin-Vorlage.
    -   **Zweck:** Rendert wahrscheinlich Schaltflächen oder Steuerelemente zur Verwaltung von E-Mail-Vorlagen (z. B. „Neue Vorlage hinzufügen“, „Vorlagen verwalten“).
-   **`sendvouchers/lib/emailTemplatesManager/views/createTemplateForm.tpl`**

    -   **Geltungsbereich:** Admin-Vorlage.
    -   **Zweck:** Rendert das HTML-Formular zum Erstellen einer neuen E-Mail-Vorlage, einschließlich Feldern für Betreff, Text und möglicherweise Sprachauswahl.
-   **`sendvouchers/lib/emailTemplatesManager/views/editTemplateForm.tpl`**

    -   **Geltungsbereich:** Admin-Vorlage.
    -   **Zweck:** Rendert das HTML-Formular zum Bearbeiten einer bestehenden E-Mail-Vorlage, wobei die Felder mit den aktuellen Vorlagendaten vorab ausgefüllt werden.
-   **`sendvouchers/lib/emailTemplatesManager/views/mainForm.tpl`**

    -   **Geltungsbereich:** Admin-Vorlage.
    -   **Zweck:** Dies ist wahrscheinlich die Haupt-Wrapper-Vorlage für den Abschnitt „E-Mail-Vorlagen-Manager“, die die Anzeige der Vorlagenliste, des Erstellungsformulars und des Bearbeitungsformulars orchestriert.
-   **`sendvouchers/lib/emailTemplatesManager/views/selectInput.tpl`**

    -   **Geltungsbereich:** Admin-Vorlage.
    -   **Zweck:** Ein wiederverwendbares Vorlagen-Snippet zum Rendern eines `<select>`-HTML-Eingabefeldes, möglicherweise für die Sprachauswahl oder die Auswahl einer vorhandenen Vorlage.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    -   Das Modul erstellt während `install()` keine expliziten benutzerdefinierten SQL-Tabellen.
    -   Es speichert seine Konfigurationseinstellungen (wie `sendvouchersTemplate`, `sendvouchersTitle`) in der `ps_configuration`-Tabelle von PrestaShop.
    -   Es interagiert mit den Kern-PrestaShop-Tabellen `ps_cart_rule` und `ps_cart_rule_lang` beim Erstellen und Verwalten von Rabattgutscheinen.
-   **Registrierte Hooks-Tabelle**:
    Die primäre Funktionalität des Moduls wird über seine `getContent()`-Methode im Back Office ausgeführt. Obwohl die Modulbeschreibung „Front-Office Hooks: Header, Columns, Product, or Footer“ erwähnt, zeigt das bereitgestellte Code-Inventar keine entsprechenden Vorlagendateien oder expliziten `hook`-Methoden in `sendvouchers.php`, die Inhalte in diesen Front-Office-Hooks rendern würden. Dies deutet darauf hin, dass, falls Front-Office-Hooks registriert sind, diese entweder für die interne Verarbeitung (z. B. `actionFrontControllerSetMedia` zum Laden von Assets) oder Überreste früherer Versionen sind und nicht aktiv zur Anzeige visueller Inhalte verwendet werden.

    Die Kernfunktionalität des Versendens von E-Mails mit Gutscheinen wird durch Benutzeraktionen im Back Office ausgelöst, nicht durch das Laden von Front-Office-Seiten.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayBackOfficeHeader` | Bei jedem Laden einer Back-Office-Seite. | Potenziell zum Laden modulspezifischer CSS/JS für die Konfigurationsseite verwendet. |
| `moduleRoutes` | Während der Initialisierung des URL-Routings. | (Falls implementiert) Zum Definieren benutzerdefinierter sprechender URLs für Modulseiten. (In diesem Modul nicht explizit erkannt). |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird. | Zum Hinzufügen modulspezifischer JavaScript- und CSS-Dateien zur Back-Office-Konfigurationsseite. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und zum Herunterladen der neuesten Versionen des Moduls „E-Mail mit Gutschein senden“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.

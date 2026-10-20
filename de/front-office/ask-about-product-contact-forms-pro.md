---
title: "Produkt anfragen - Kontaktformulare Pro - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Produkt anfragen - Kontaktformulare Pro“ von MyPresta.eu."
sidebar:
  label: "Produkt anfragen - Kontaktformulare Pro - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Ask about product - contact forms pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/ask-about-product-contact-forms-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/ask-about-product-contact-forms-pro/)
>
> ---


# Produkt anfragen - Kontaktformulare Pro

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, damit das Modul korrekt funktioniert, insbesondere für Funktionen wie reCAPTCHA und Webhooks. Diese sind typischerweise in den meisten modernen Hosting-Umgebungen verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Dieses Modul bietet umfangreiche Anpassungsoptionen, um die Kontaktformulare an Ihre spezifischen Bedürfnisse anzupassen. Wir werden jeden Konfigurationsbildschirm und jede Einstellung durchgehen.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbereich für das Modul, der direkt nach der Installation oder durch Navigieren zu **Module > Modul-Manager** und Klicken auf „Konfigurieren“ neben „Produkt anfragen - Kontaktformulare Pro“ aufgerufen wird.

#### Allgemeine Einstellungen

- **Template-Support-Profil**

  - **Was diese Einstellung bewirkt:** Diese Einstellung ermöglicht es Ihnen, ein vordefiniertes Template-Profil auszuwählen, das am besten zu Ihrem PrestaShop-Theme passt. Verschiedene Themes erfordern möglicherweise unterschiedliche Styling- oder strukturelle Anpassungen, damit das Formular korrekt angezeigt wird.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn auf „Classic“ (oder ähnlich) eingestellt:* Das Modul verwendet Templates und Styling, die für das Standard-PrestaShop Classic-Theme oder darauf basierende Themes optimiert sind.
    - *Wenn auf ein spezifisches Theme-Profil eingestellt:* Das Modul lädt Templates und CSS, die für eine reibungslose Integration mit diesem bestimmten Theme entwickelt wurden, um eine bessere visuelle Konsistenz zu gewährleisten.
  - **Empfohlener Wert:** Wählen Sie das Profil, das Ihrem aktiven PrestaShop-Theme entspricht. Im Zweifelsfall beginnen Sie mit „Classic“ und passen es an, wenn Styling-Probleme auftreten.
  - **Händlerszenario / Beispiel:** Wenn Sie ein benutzerdefiniertes Theme verwenden, müssen Sie möglicherweise verschiedene Profile testen oder die Option „Benutzerdefiniertes CSS“ verwenden, um das Erscheinungsbild zu optimieren.
- **E-Mail-Titel (für Shop-Betreiber)**

  - **Was diese Einstellung bewirkt:** Dies ist die Betreffzeile für die E-Mail-Benachrichtigung, die *Sie* (der Shop-Betreiber/Admin) erhalten, wenn ein Kunde eine Frage stellt.
  - **Auswirkungen einer Änderung dieser Einstellung:** Ändert die Betreffzeile der internen Benachrichtigungs-E-Mails.
  - **Empfohlener Wert:** Etwas Klares und Informatives, wie „Neue Produktfrage aus Ihrem Shop - [Produktname]“.
  - **Händlerszenario / Beispiel:** Wenn Sie dies auf „DRINGEND: Neue Anfrage für [Produktname]“ setzen, kann Ihr Team Prioritäten setzen.
- **Empfänger-E-Mail(s)**

  - **Was diese Einstellung bewirkt:** Gibt die E-Mail-Adresse(n) an, an die Produktanfragen gesendet werden. Sie können mehrere E-Mails durch Kommas getrennt eingeben.
  - **Auswirkungen einer Änderung dieser Einstellung:** Bestimmt, wer in Ihrer Organisation die Kundenfragen erhält.
  - **Empfohlener Wert:** Die E-Mail-Adresse Ihres Kundenservice-Teams oder der zuständigen Abteilung.
  - **Händlerszenario / Beispiel:** Wenn Sie eine dedizierte „[sales@ihrshop.com](mailto:sales@ihrshop.com)“ oder „[support@ihrshop.com](mailto:support@ihrshop.com)“-Adresse haben, geben Sie diese hier ein. Für größere Teams können Sie sie an eine Verteilerliste senden.
- **BCC für Shop-Benachrichtigungs-E-Mail**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, eine Blindkopie (BCC) der Shop-Benachrichtigungs-E-Mail an zusätzliche E-Mail-Adressen zu senden. Diese Empfänger sind für den primären Empfänger nicht sichtbar.
  - **Auswirkungen einer Änderung dieser Einstellung:** Bietet eine diskrete Möglichkeit, andere Teammitglieder zu benachrichtigen oder Anfragen zu archivieren, ohne den Posteingang des primären Empfängers zu überladen oder zusätzliche Empfänger preiszugeben.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben einen spezifischen Bedarf für interne Nachverfolgung oder sekundäre Benachrichtigungen.
  - **Händlerszenario / Beispiel:** Sie könnten Ihren Marketingmanager per BCC benachrichtigen, um das Kundeninteresse zu verfolgen, oder eine interne Archiv-E-Mail-Adresse.
- **Autoresponder-E-Mail**

  - **Was diese Einstellung bewirkt:** Dies ist die Betreffzeile für die automatische E-Mail, die *an den Kunden* gesendet wird, nachdem er eine Frage gestellt hat.
  - **Auswirkungen einer Änderung dieser Einstellung:** Ändert die Betreffzeile der Bestätigungs-E-Mail, die Ihre Kunden erhalten.
  - **Empfohlener Wert:** „Vielen Dank für Ihre Anfrage - [Ihr Shop-Name]“.
  - **Händlerszenario / Beispiel:** Eine klare Autoresponder-Betreffzeile versichert dem Kunden, dass seine Nachricht empfangen wurde.
- **Dauer der Erfolgsmeldung (ms)**

  - **Was diese Einstellung bewirkt:** Steuert, wie lange die Benachrichtigung „Ihre Nachricht wurde erfolgreich gesendet“ auf dem Bildschirm sichtbar bleibt, nachdem ein Kunde ein Formular abgeschickt hat, gemessen in Millisekunden (ms).
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Höherer Wert (z. B. 5000ms):* Die Nachricht bleibt länger sichtbar, was Kunden mehr Zeit zum Lesen gibt.
    - *Niedrigerer Wert (z. B. 2000ms):* Die Nachricht verschwindet schnell.
  - **Empfohlener Wert:** 3000-5000ms (3-5 Sekunden) ist normalerweise eine gute Balance.
  - **Händlerszenario / Beispiel:** Wenn Ihre Kunden oft langsamere Verbindungen haben oder mehr Zeit benötigen, um Informationen zu verarbeiten, könnte eine längere Dauer vorteilhaft sein.
- **„Frage stellen“ für nicht vorrätige Produkte ausblenden (aappro\_HIDE\_OOS)**

  - **Was diese Einstellung bewirkt:** Wenn aktiviert, wird das „Frage stellen“-Formular oder der Button auf Produktseiten, auf denen das Produkt derzeit nicht vorrätig ist, nicht angezeigt.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Verhindert, dass Kunden nach Produkten fragen, die nicht verfügbar sind, wodurch potenziell irrelevante Anfragen für Ihr Team reduziert werden.
    - *Wenn deaktiviert:* Das Formular bleibt unabhängig vom Lagerbestand sichtbar.
  - **Empfohlener Wert:** „Ja“, um Anfragen zu nicht verfügbaren Artikeln zu reduzieren, es sei denn, Sie möchten gezielt Interesse für Nachbestellungen erfassen.
  - **Händlerszenario / Beispiel:** Wenn Sie einzigartige oder limitierte Artikel verkaufen, die nicht nachbestellt werden, ist es sinnvoll, das Formular für nicht vorrätige Produkte auszublenden. Wenn Sie Interesse für zukünftige Nachbestellungen messen möchten, lassen Sie es deaktiviert.
- **Nur eingeloggten Kunden erlauben, Fragen zu stellen (aappro\_LOGGED\_CUSTOMERS\_ONLY)**

  - **Was diese Einstellung bewirkt:** Beschränkt die Möglichkeit, Produktfragen zu stellen, nur auf Kunden, die in ihren Shop-Konten angemeldet sind.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Nicht registrierte oder Gastbenutzer sehen das „Frage stellen“-Formular nicht und können es nicht verwenden. Dies kann helfen, Spam zu reduzieren und sicherzustellen, dass Sie Kundenkontodaten mit Anfragen verknüpft haben.
    - *Wenn deaktiviert:* Jeder kann eine Frage stellen, einschließlich Gäste.
  - **Empfohlener Wert:** „Nein“ für maximale Kundenreichweite, „Ja“, wenn Sie das Engagement registrierter Kunden priorisieren und anonyme Anfragen reduzieren möchten.
  - **Händlerszenario / Beispiel:** Wenn Sie einen B2B-Shop betreiben, in dem alle Interaktionen ein Konto erfordern, wäre die Aktivierung dieser Option angemessen. Für einen allgemeinen Einzelhandelsshop ist es normalerweise besser für die Konversion, sie deaktiviert zu lassen.

#### Formularfelder & Validierung

- **Ja / Nein (aappro\_FIELD\_PHONE\_REQUIRED, aappro\_FIELD\_PHONE\_VISIBLE, aappro\_FIELD\_TOPIC\_VISIBLE, aappro\_QUOTE\_QUANTITY\_VISIBLE)**

  - **Was diese Einstellung bewirkt:** Dies ist eine Gruppe von „Ja/Nein“-Schaltern, die die Sichtbarkeit und Erforderlichkeit spezifischer Felder in Ihren Produktanfrageformularen steuern:
    - **Telefonnummer sichtbar:** Zeigt das Telefonnummernfeld an.
    - **Telefonnummer erforderlich:** Macht das Telefonnummernfeld obligatorisch, wenn es sichtbar ist.
    - **Themenauswahl sichtbar:** Zeigt ein Dropdown-Menü an, in dem Kunden ein Thema für ihre Frage auswählen können (z. B. „Versand“, „Technische Daten“, „Verfügbarkeit“).
    - **Angebotsmenge sichtbar:** Zeigt ein Feld an, in dem Kunden ein Angebot für eine bestimmte Menge des Produkts anfordern können.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Aktiviert (Sichtbar):* Das Feld erscheint im Formular.
    - *Deaktiviert (Sichtbar):* Das Feld ist ausgeblendet.
    - *Aktiviert (Erforderlich):* Der Kunde *muss* das Feld ausfüllen, um das Formular abzusenden.
  - **Empfohlener Wert:**
    - **Telefon:** Sichtbar „Nein“, Erforderlich „Nein“ (es sei denn, telefonischer Kontakt ist für Ihr Geschäftsmodell entscheidend).
    - **Thema:** Sichtbar „Ja“ (hilft bei der Kategorisierung von Anfragen), Erforderlich „Nein“.
    - **Angebotsmenge:** Sichtbar „Ja“ (wenn Sie Mengenrabatte oder B2B-Verkäufe anbieten), Erforderlich „Nein“.
  - **Händlerszenario / Beispiel:** Wenn Sie komplexe Elektronik verkaufen, wäre es sehr hilfreich, die „Themenauswahl“ mit Optionen wie „Technischer Support“ oder „Kompatibilität“ sichtbar zu machen. Wenn Sie ein Großhändler sind, ist die „Angebotsmenge“ unerlässlich.
- **Minimale Fragenlänge (Zeichen)**

  - **Was diese Einstellung bewirkt:** Legt die minimale Anzahl von Zeichen fest, die ein Kunde in das Fragenfeld eingeben muss, bevor er das Formular absenden kann.
  - **Auswirkungen einer Änderung dieser Einstellung:** Verhindert sehr kurze, potenziell nutzlose oder spamartige Fragen.
  - **Empfohlener Wert:** 10-20 Zeichen.
  - **Händlerszenario / Beispiel:** Wenn Sie dies auf 15 Zeichen setzen, stellen Sie sicher, dass Kunden genügend Details über eine einfache „Frage“ hinaus angeben.
- **Maximale Fragenlänge (Zeichen)**

  - **Was diese Einstellung bewirkt:** Legt die maximale Anzahl von Zeichen fest, die ein Kunde in das Fragenfeld eingeben kann.
  - **Auswirkungen einer Änderung dieser Einstellung:** Verhindert übermäßig lange Fragen, die schwer zu lesen sein könnten oder darauf hindeuten, dass ein Kunde das Formular als allgemeinen Chat verwenden möchte.
  - **Empfohlener Wert:** 500-1000 Zeichen.
  - **Händlerszenario / Beispiel:** Eine Begrenzung von 750 Zeichen ist für die meisten Produktanfragen in der Regel ausreichend.
- **Bildanhang erlauben**

  - **Was diese Einstellung bewirkt:** Ermöglicht Kunden, eine Bilddatei (z. B. einen Screenshot, ein Foto eines beschädigten Artikels oder ein Diagramm) zusammen mit ihrer Frage hochzuladen.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein „Datei hochladen“-Feld erscheint im Formular.
    - *Wenn deaktiviert:* Es ist keine Anhangsoption verfügbar.
  - **Empfohlener Wert:** „Ja“ kann für visuelle Anfragen sehr hilfreich sein, stellen Sie jedoch sicher, dass Ihr Server den Speicherplatz verwalten kann.
  - **Händlerszenario / Beispiel:** Ein Kunde möchte möglicherweise ein Foto eines bestimmten Teils eines Produkts anhängen, zu dem er eine Frage hat, oder einen Screenshot eines Fehlers, auf den er stößt.
- **Maximale Anhangsgröße (MB)**

  - **Was diese Einstellung bewirkt:** Wenn der Bildanhang aktiviert ist, legt dies die maximale Dateigröße (in Megabyte) fest, die für jeden Anhang zulässig ist.
  - **Auswirkungen einer Änderung dieser Einstellung:** Steuert die Serverlast und die Speichernutzung.
  - **Empfohlener Wert:** 2-5 MB sind für die meisten Bilder in der Regel ausreichend.
  - **Händlerszenario / Beispiel:** Wenn Sie es auf 3 MB setzen, verhindern Sie, dass Kunden sehr große, hochauflösende Bilder hochladen, die für eine Anfrage nicht notwendig sind.

#### Sicherheit & Compliance

- **DSGVO-konform**

  - **Was diese Einstellung bewirkt:** Aktiviert Funktionen, die Ihren Formularen helfen, die Anforderungen der DSGVO (Datenschutz-Grundverordnung) zu erfüllen, typischerweise durch Hinzufügen eines Kontrollkästchens zur Zustimmung zur Datenverarbeitung.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Kontrollkästchen erscheint im Formular, das Kunden dazu verpflichtet, Ihrer Datenschutzerklärung explizit zuzustimmen, bevor sie ihre Frage absenden.
    - *Wenn deaktiviert:* Es wird kein DSGVO-Zustimmungskontrollkästchen angezeigt.
  - **Empfohlener Wert:** „Ja“, wenn Ihr Shop in Regionen tätig ist oder Kunden in Regionen bedient, die der DSGVO unterliegen (z. B. EU).
  - **Händlerszenario / Beispiel:** Wenn Sie an Kunden in Europa verkaufen, ist die Aktivierung dieser Option rechtlich wichtig.
- **Datenschutzerklärung-Seite**

  - **Was diese Einstellung bewirkt:** Wenn die DSGVO-Konformität aktiviert ist, können Sie mit dieser Einstellung die CMS-Seite auswählen, die die Datenschutzerklärung Ihres Shops enthält. Das DSGVO-Zustimmungskontrollkästchen verlinkt auf diese Seite.
  - **Auswirkungen einer Änderung dieser Einstellung:** Bietet Kunden einfachen Zugang zu Ihrer Datenschutzerklärung und erfüllt eine wichtige DSGVO-Anforderung.
  - **Empfohlener Wert:** Wählen Sie Ihre dedizierte Datenschutzerklärung-CMS-Seite aus.
  - **Händlerszenario / Beispiel:** Nach der Aktivierung der DSGVO müssen Sie die richtige CMS-Seite auswählen, damit Kunden Ihre Datenverarbeitungspraktiken überprüfen können.
- **ReCaptcha (v2)**

  - **Was diese Einstellung bewirkt:** Integriert Google reCAPTCHA v2 (das „Ich bin kein Roboter“-Kontrollkästchen) in Ihre Formulare, um Spam und Bot-Einreichungen zu verhindern.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das reCAPTCHA-Kontrollkästchen erscheint im Formular und erfordert eine Benutzerinteraktion, um zu beweisen, dass es sich um einen Menschen handelt.
    - *Wenn deaktiviert:* Es wird kein reCAPTCHA verwendet.
  - **Empfohlener Wert:** „Ja“, um Spam erheblich zu reduzieren, insbesondere wenn Sie viele Bot-Einreichungen erhalten.
  - **Händlerszenario / Beispiel:** Wenn Sie viele unerwünschte Anfragen erhalten, ist die Aktivierung von reCAPTCHA eine starke Verteidigung.
- **ReCaptcha-Site-Key**

  - **Was diese Einstellung bewirkt:** Dies ist der öffentliche Schlüssel, den Google bereitstellt, wenn Sie Ihre Website für reCAPTCHA registrieren. Er wird verwendet, um das reCAPTCHA-Widget auf Ihrer Website anzuzeigen.
  - **Auswirkungen einer Änderung dieser Einstellung:** Wesentlich für die Funktion von reCAPTCHA. Ohne ihn wird reCAPTCHA nicht angezeigt oder funktioniert nicht.
  - **Empfohlener Wert:** Ihr einzigartiger reCAPTCHA-Site-Key von Google.
  - **Händlerszenario / Beispiel:** Sie müssen zur Google reCAPTCHA-Admin-Konsole gehen, Ihre Domain registrieren und diesen Schlüssel in die Moduleinstellungen kopieren.
- **ReCaptcha-Secret-Key**

  - **Was diese Einstellung bewirkt:** Dies ist der private Schlüssel, den Google bereitstellt und der für die serverseitige Überprüfung der reCAPTCHA-Antwort verwendet wird.
  - **Auswirkungen einer Änderung dieser Einstellung:** Wesentlich für die sichere Funktion von reCAPTCHA. Das Modul verwendet diesen Schlüssel, um zu bestätigen, dass der Benutzer die reCAPTCHA-Herausforderung tatsächlich bestanden hat.
  - **Empfohlener Wert:** Ihr einzigartiger reCAPTCHA-Secret-Key von Google.
  - **Händlerszenario / Beispiel:** Dieser Schlüssel sollte vertraulich behandelt und niemals im clientseitigen Code offengelegt werden.

#### Integration & Anpassung

- **Webhook-URL (Slack/Discord)**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, Benachrichtigungen über neue Produktanfragen an eine Webhook-URL zu senden, die typischerweise für Dienste wie Slack oder Discord verwendet wird.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn eine URL angegeben ist:* Neue Anfragen lösen eine Benachrichtigung an den angegebenen Chat-Kanal aus.
    - *Wenn leer:* Es werden keine Webhook-Benachrichtigungen gesendet.
  - **Empfohlener Wert:** Leer lassen, es sei denn, Sie verwenden aktiv Slack, Discord oder einen anderen Dienst, der eingehende Webhooks für die Teamkommunikation unterstützt.
  - **Händlerszenario / Beispiel:** Ihr Kundenservice-Team verwendet Slack. Sie können einen eingehenden Webhook in Slack konfigurieren und dessen URL hier einfügen, sodass jede neue Produktfrage sofort in Ihrem #customer-support-Kanal erscheint.
- **Benutzerdefiniertes CSS (nur Produktseite)**

  - **Was diese Einstellung bewirkt:** Bietet einen Textbereich, in dem Sie benutzerdefinierte CSS-Regeln hinzufügen können, um das Produktanfrageformular speziell auf Produktseiten zu gestalten.
  - **Auswirkungen einer Änderung dieser Einstellung:** Ermöglicht es Ihnen, Standardmodulstile oder die Stile Ihres Themes zu überschreiben, um die Ästhetik Ihrer Marke perfekt anzupassen, ohne Moduldateien direkt zu ändern.
  - **Empfohlener Wert:** Sparsam für kleinere Anpassungen verwenden. Für größere Stiländerungen sollten Sie Theme-Overrides in Betracht ziehen.
  - **Händlerszenario / Beispiel:** Sie möchten die Schaltflächenfarbe des „Senden“-Buttons in die Primärfarbe Ihrer Marke ändern oder den Abstand um die Formularfelder anpassen. Sie können hier `.aappro-form-submit-button { background-color: #FF0000; }` hinzufügen.
- **Benutzerdefinierte Felder (aappro\_CUSTOM\_FIELDS\_JSON)**

  - **Was diese Einstellung bewirkt:** Dies ist eine leistungsstarke Funktion, mit der Sie zusätzliche, benutzerdefinierte Felder für Ihre Kontaktformulare definieren können. Sie können Feldtypen (Text, Textarea, Select, Checkbox), Beschriftungen und ob sie erforderlich sind, angeben. Dies wird typischerweise über eine dedizierte Oberfläche verwaltet, nicht über ein rohes JSON-Feld.
  - **Auswirkungen einer Änderung dieser Einstellung:** Fügt neue Eingabefelder zu Ihren Formularen hinzu, sodass Sie spezifischere Informationen von Kunden sammeln können.
  - **Empfohlener Wert:** Fügen Sie Felder hinzu, die für Ihre Produkte oder Dienstleistungen relevant sind (z. B. „Bestellnummer“ für bestehende Kunden, „Verwendungszweck“ für B2B).
  - **Händlerszenario / Beispiel:** Für einen Bekleidungsgeschäft könnten Sie ein benutzerdefiniertes Feld „Gewünschte Größe“ hinzufügen, wenn Kunden oft nach bestimmten, nicht aufgeführten Größen fragen. Für einen Technik-Shop könnte „Aktuelles Gerätemodell“ nützlich sein.
- **Kommentare erlauben (aappro\_ALLOW\_COMMENTS)**

  - **Was diese Einstellung bewirkt:** Diese Einstellung steuert wahrscheinlich, ob Kunden allgemeine Kommentare auf der Produktseite hinterlassen können, möglicherweise getrennt vom spezifischen „Frage stellen“-Formular.
  - **Auswirkungen einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein allgemeiner Kommentarbereich könnte erscheinen.
    - *Wenn deaktiviert:* Nur das strukturierte „Frage stellen“-Formular ist verfügbar.
  - **Empfohlener Wert:** „Nein“, wenn Sie die Kommunikation auf das strukturierte Fragenformular konzentrieren möchten. „Ja“, wenn Sie eine breitere öffentliche Diskussion fördern möchten.
  - **Händlerszenario / Beispiel:** Wenn Sie direkte, private Anfragen gegenüber öffentlichen Kommentaren bevorzugen, deaktivieren Sie diese Option.
- **PS\_STOCK\_MANAGEMENT**

  - **Was diese Einstellung bewirkt:** Dies ist eine PrestaShop-Kerndatei, die nicht direkt vom Modul gesteuert wird, aber das Modul könnte ihren Wert lesen. Sie bestimmt, ob die Lagerverwaltung global in Ihrem Shop aktiviert ist.
  - **Auswirkungen einer Änderung dieser Einstellung:** Wenn die Lagerverwaltung deaktiviert ist, funktioniert die Einstellung „Für nicht vorrätige Produkte ausblenden“ des Moduls möglicherweise nicht wie erwartet, da Produkte keinen klaren Lagerstatus haben.
  - **Empfohlener Wert:** „Ja“ für die meisten E-Commerce-Shops, um den Lagerbestand genau zu verfolgen.
  - **Händlerszenario / Beispiel:** Wenn Sie digitale Produkte verkaufen, können Sie die Lagerverwaltung deaktivieren. Für physische Güter ist sie jedoch entscheidend.
- **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**

  - **Was diese Einstellungen bewirken:** Dies sind PrestaShop-Kerndateien, die sich auf die Sprache beziehen. `PS_LANG_DEFAULT` legt die Standardsprache des Front-Office fest, und `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` ermöglicht es Mitarbeitern, ihre Back-Office-Sprache zu wählen. Das Modul verwendet diese, um die korrekte Sprachanzeige für Formulare und Benachrichtigungen sicherzustellen.
  - **Auswirkungen einer Änderung dieser Einstellungen:** Beeinflusst die Sprache der Formulare und Benachrichtigungen.
  - **Empfohlener Wert:** Setzen Sie `PS_LANG_DEFAULT` auf Ihre primäre Shop-Sprache. `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` kann aktiviert werden, wenn Sie ein mehrsprachiges Team haben.
  - **Händlerszenario / Beispiel:** Wenn die primäre Sprache Ihres Shops Französisch ist, stellen Sie sicher, dass `PS_LANG_DEFAULT` auf Französisch eingestellt ist.

#### Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Hauptkonfiguration | Template-Support-Profil | Ihr Theme / Classic | Stellt die korrekte Gestaltung und Integration mit Ihrem Theme sicher. |
| Hauptkonfiguration | E-Mail-Titel (für Shop-Betreiber) | „Neue Produktfrage“ | Betreffzeile für interne Admin-Benachrichtigungs-E-Mails. |
| Hauptkonfiguration | Empfänger-E-Mail(s) | Ihre Admin-E-Mail | Wohin Kundenfragen gesendet werden. |
| Hauptkonfiguration | BCC für Shop-Benachrichtigungs-E-Mail | Leer | Senden Sie diskret Kopien von Benachrichtigungen an andere. |
| Hauptkonfiguration | Autoresponder-E-Mail | „Vielen Dank für Ihre Anfrage“ | Betreffzeile für Kundenbestätigungs-E-Mails. |
| Hauptkonfiguration | Dauer der Erfolgsmeldung (ms) | 3000-5000 | Wie lange die „Nachricht gesendet“-Benachrichtigung sichtbar bleibt. |
| Hauptkonfiguration | Für nicht vorrätige Produkte ausblenden | Ja | Verhindert Fragen zu nicht verfügbaren Produkten. |
| Hauptkonfiguration | Nur eingeloggten Kunden erlauben | Nein | Beschränkt den Formularzugriff auf registrierte Benutzer. |
| Hauptkonfiguration | Telefonnummer sichtbar | Nein | Zeigt/versteckt das Telefonnummernfeld. |
| Hauptkonfiguration | Telefonnummer erforderlich | Nein | Macht die Telefonnummer obligatorisch, wenn sichtbar. |
| Hauptkonfiguration | Themenauswahl sichtbar | Ja | Zeigt/versteckt ein Dropdown-Menü für Fragenthemen. |
| Hauptkonfiguration | Angebotsmenge sichtbar | Ja (wenn B2B) | Zeigt/versteckt ein Feld für Mengenangebotsanfragen. |
| Hauptkonfiguration | Minimale Fragenlänge | 15 Zeichen | Verhindert übermäßig kurze Fragen. |
| Hauptkonfiguration | Maximale Fragenlänge | 750 Zeichen | Verhindert übermäßig lange Fragen. |
| Hauptkonfiguration | Bildanhang erlauben | Ja | Ermöglicht Kunden das Hochladen von Dateien. |
| Hauptkonfiguration | Maximale Anhangsgröße (MB) | 3 MB | Begrenzt die Größe hochgeladener Dateien. |
| Hauptkonfiguration | DSGVO-konform | Ja (falls zutreffend) | Fügt ein Zustimmungs-Kontrollkästchen zur Datenverarbeitung hinzu. |
| Hauptkonfiguration | Datenschutzerklärung-Seite | Ihre Datenschutzerklärung-CMS | Verknüpft das DSGVO-Kontrollkästchen mit Ihrer Datenschutzerklärung. |
| Hauptkonfiguration | ReCaptcha (v2) | Ja | Integriert Google reCAPTCHA zum Spamschutz. |
| Hauptkonfiguration | ReCaptcha-Site-Key | Ihr Google Site Key | Öffentlicher Schlüssel für die Anzeige des reCAPTCHA-Widgets. |
| Hauptkonfiguration | ReCaptcha-Secret-Key | Ihr Google Secret Key | Privater Schlüssel für die serverseitige reCAPTCHA-Verifizierung. |
| Hauptkonfiguration | Webhook-URL (Slack/Discord) | Leer | Sendet Benachrichtigungen an externe Chat-Dienste. |
| Hauptkonfiguration | Benutzerdefiniertes CSS (nur Produktseite) | Leer | Fügen Sie benutzerdefiniertes CSS hinzu, um das Formular zu gestalten. |
| Hauptkonfiguration | Benutzerdefinierte Felder | Konfiguriert über AdminAapproForm | Definieren Sie zusätzliche Felder für Ihre Formulare. |
| Hauptkonfiguration | Kommentare erlauben | Nein | Steuert allgemeine Produktkommentare vs. strukturierte Fragen. |

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Neben der Hauptkonfiguration bietet dieses Modul dedizierte Bereiche in Ihrem PrestaShop Back Office, um Formulare, Fragen und benutzerdefinierte Felder zu verwalten.

#### 2.2.1 AdminAapproFormController: Formularverwaltung (Back Office > Module > Produkt anfragen > Formulare)

Dieser Bildschirm ermöglicht es Ihnen, verschiedene Produktanfrageformulare zu erstellen und zu verwalten und festzulegen, wo sie in Ihrem Shop erscheinen.

- **Bildschirmname & Menüpfad:** **Module > Produkt anfragen > Formulare**
- **Verfügbare Aktionen & Einstellungen:**
  - **Auflistungstabelle:** Zeigt alle Ihre erstellten Formulare mit ihren Namen, Status und zugehörigen Produkten/Kategorien/Herstellern an.
  - **Neues Formular hinzufügen-Button:** Klicken Sie hier, um ein neues Formular zu erstellen.
  - **Bearbeiten/Löschen-Aktionen:** Vorhandene Formulare ändern oder entfernen.
  - **Formularfelder:** Beim Hinzufügen oder Bearbeiten eines Formulars konfigurieren Sie:
    - **Formularname:** Interner Name für Ihre Referenz.
    - **Aktiv:** Aktivieren oder deaktivieren Sie das Formular.
    - **Auf Produktseite anzeigen:** Wählen Sie, ob dieses Formular auf Produktseiten erscheinen soll.
    - **Auf Kategorieseite anzeigen:** Wählen Sie, ob dieses Formular auf Kategorieseiten erscheinen soll.
    - **Auf Herstellerseite anzeigen:** Wählen Sie, ob dieses Formular auf Herstellerseiten erscheinen soll.
    - **Empfänger-E-Mail(s) für dieses Formular:** Überschreiben Sie die globale Empfänger-E-Mail für dieses spezifische Formular. Dies ist entscheidend für die Weiterleitung von Fragen an bestimmte Teams.
    - **Produkte:** Wählen Sie spezifische Produkte aus, auf denen dieses Formular erscheinen soll.
    - **Kategorien:** Wählen Sie spezifische Kategorien aus, auf denen dieses Formular erscheinen soll.
    - **Hersteller:** Wählen Sie spezifische Hersteller aus, auf denen dieses Formular erscheinen soll.
    - **Benutzerdefinierte Felder:** Hier definieren Sie die einzigartigen Felder für *dieses spezifische Formular*. Sie können Texteingaben, Textbereiche, Dropdowns, Kontrollkästchen usw. hinzufügen und sie als erforderlich markieren.
- **Auswirkungen von Änderungen:**
  - Das Erstellen eines neuen Formulars ermöglicht es Ihnen, einen einzigartigen Satz von Fragen und Weiterleitungsregeln zu definieren.
  - Die Verknüpfung von Formularen mit bestimmten Produkten, Kategorien oder Herstellern bedeutet, dass nur dieses bestimmte Formular angezeigt wird, wenn ein Kunde einen Artikel ansieht, der diesen Kriterien entspricht.
  - Das Überschreiben von Empfänger-E-Mails stellt sicher, dass Fragen zu beispielsweise „Elektronik“ an die Elektronikabteilung gehen, während „Bekleidung“-Fragen an das Modeteam gehen.
  - Benutzerdefinierte Felder ermöglichen es Ihnen, hochspezifische Informationen zu sammeln, die für den Kontext des Formulars relevant sind.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Bedarf ermitteln:** Bestimmen Sie, ob Sie verschiedene Formulare für verschiedene Produkttypen, Abteilungen oder Kundensegmente benötigen.
  2. **Formulare erstellen:** Gehen Sie zu **Formulare** und klicken Sie auf „Neues Formular hinzufügen“.
  3. **Weiterleitung konfigurieren:** Legen Sie die spezifischen „Empfänger-E-Mail(s) für dieses Formular“ fest, um sicherzustellen, dass Fragen an den richtigen Ort gelangen.
  4. **Umfang definieren:** Verwenden Sie die Selektoren „Produkte“, „Kategorien“ und „Hersteller“, um zu steuern, wo jedes Formular erscheint.
  5. **Benutzerdefinierte Felder hinzufügen:** Passen Sie die auf jedem Formular gestellten Fragen im Abschnitt „Benutzerdefinierte Felder“ an, um relevante Informationen zu sammeln.
  6. **Testen:** Testen Sie Ihre Formulare immer im Front-Office, um sicherzustellen, dass sie korrekt erscheinen und E-Mails an die richtigen Empfänger senden.

#### 2.2.2 AdminAapproQuestionController: Fragenverwaltung (Back Office > Module > Produkt anfragen > Fragen)

Dieser Bildschirm dient als Ihre zentrale Anlaufstelle zum Anzeigen und Verwalten aller eingereichten Kundenfragen.

- **Bildschirmname & Menüpfad:** **Module > Produkt anfragen > Fragen**
- **Verwaltete Tabelle / Entität:** `aappro_question` (speichert alle eingereichten Anfragen)
- **Formularfelder & Spalten:**
  - **Raster- / Verwaltungsansicht:** Zeigt eine Liste aller eingereichten Fragen an.
    - **Spalten:** Enthält typischerweise: Kundenname, Kunden-E-Mail, Produktname (falls zutreffend), Fragenthema, Datum der Einreichung, Status (z. B. Neu, Beantwortet, Geschlossen).
    - **Filtern & Sortieren:** Standard-PrestaShop-Listenfunktionen zum Filtern nach Datum, Kunde, Produkt oder Status.
  - **Anzeigen/Antworten-Aktion:** Durch Klicken auf eine Frage können Sie deren vollständige Details anzeigen und dem Kunden antworten.
    - **Fragedetails:** Zeigt die vollständige Nachricht des Kunden, Kontaktinformationen, Produktdetails und eventuelle Anhänge an.
    - **Antwort-Oberfläche:** Ein Textbereich zum Verfassen Ihrer Antwort, die direkt an die E-Mail-Adresse des Kunden gesendet wird.
    - **Statusaktualisierung:** Option zum Ändern des Status der Frage (z. B. von „Neu“ zu „Beantwortet“).
- **Auswirkungen von Änderungen:**
  - Dieser Bildschirm bietet einen zentralen Posteingang für alle produktbezogenen Anfragen, wodurch die Nachverfolgung und Beantwortung erleichtert wird.
  - Das direkte Antworten von hier aus stellt sicher, dass der Gesprächsverlauf innerhalb von PrestaShop erhalten bleibt und mit dem spezifischen Produkt verknüpft ist.
  - Die Aktualisierung des Status hilft Ihrem Team, die Arbeitslast zu verwalten und stellt sicher, dass keine Fragen übersehen werden.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Regelmäßig prüfen:** Machen Sie es sich zur Gewohnheit, diesen Bereich täglich (oder mehrmals täglich, je nach Volumen) zu überprüfen.
  2. **Priorisieren:** Verwenden Sie Filter, um dringende oder unbeantwortete Fragen zu identifizieren.
  3. **Anzeigen & Antworten:** Klicken Sie auf „Anzeigen“ bei einer Frage, lesen Sie die Details und verfassen Sie eine klare, hilfreiche Antwort.
  4. **Status aktualisieren:** Ändern Sie nach dem Antworten den Status der Frage auf „Beantwortet“ oder „Geschlossen“, um Ihre Warteschlange organisiert zu halten.
  5. **Produktkontext nutzen:** Das Modul verknüpft die Frage automatisch mit dem Produkt, sodass Sie beim Antworten alle notwendigen Kontextinformationen haben.

#### 2.2.3 index.php (aappro/controllers/admin/index.php)

Diese Datei ist eine Standard-PrestaShop-Praxis, um die direkte Verzeichnisauflistung im Back Office zu verhindern. Sie enthält typischerweise eine einfache `header('Location: ../../index.php?controller=AdminHome');` oder eine ähnliche Weiterleitung, die sicherstellt, dass, wenn jemand versucht, direkt auf das Verzeichnis `controllers/admin/` zuzugreifen, er zum Haupt-Admin-Dashboard zurückgeleitet wird. Sie verwaltet keine spezifische Entität und hat keine konfigurierbaren Felder.

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

- **F: Mein Formular wird nicht auf der Produktseite angezeigt.**

  - **A:**
    1. **Modulstatus prüfen:** Stellen Sie sicher, dass das Modul unter **Module > Modul-Manager** installiert und aktiviert ist.
    2. **Formularkonfiguration prüfen:** Gehen Sie zu **Module > Produkt anfragen > Formulare**. Stellen Sie sicher, dass das spezifische Formular, das Sie erwarten, „Aktiv“ ist und korrekt mit dem Produkt, der Kategorie oder dem Hersteller verknüpft ist, den Sie anzeigen.
    3. **Hook-Platzierung:** Überprüfen Sie, ob das Modul in einen Anzeigebereich eingehängt ist, den Ihr Theme rendert (z. B. `displayProductExtraContent`, `displayProductAdditionalInfo`). Manchmal überschreiben Themes Standard-Hook-Positionen.
    4. **Theme-Kompatibilität:** Wenn Sie ein stark angepasstes Theme verwenden, versuchen Sie, vorübergehend zum Standard-Classic-Theme zu wechseln, um zu sehen, ob das Formular erscheint. Wenn ja, könnte es einen Konflikt mit den Template-Dateien oder dem CSS Ihres benutzerdefinierten Themes geben.
    5. **Cache:** Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**).
- **F: Ich erhalte keine E-Mail-Benachrichtigungen, wenn ein Kunde eine Frage stellt.**

  - **A:**
    1. **Empfänger-E-Mails prüfen:** Überprüfen Sie die „Empfänger-E-Mail(s)“ in der Hauptmodulkonfiguration und auch die spezifischen „Empfänger-E-Mail(s) für dieses Formular“ in den Formulareinstellungen (**Module > Produkt anfragen > Formulare > Formular bearbeiten**). Stellen Sie sicher, dass sie korrekt und fehlerfrei sind.
    2. **Spam-Ordner:** Überprüfen Sie den Spam- oder Junk-Ordner Ihrer E-Mails.
    3. **Server-Mail-Einstellungen:** Stellen Sie sicher, dass die E-Mail-Einstellungen Ihres PrestaShop-Shops korrekt konfiguriert sind (**Erweiterte Einstellungen > E-Mail**). Senden Sie eine Test-E-Mail von PrestaShop, um zu bestätigen, dass Ihr Server E-Mails senden kann.
    4. **Hosting-Anbieter:** Kontaktieren Sie Ihren Hosting-Anbieter, um eventuelle serverseitige E-Mail-Versandbeschränkungen oder -probleme zu überprüfen.
    5. **Modul-Logs:** Überprüfen Sie die Fehlerprotokolle von PrestaShop (falls verfügbar) oder die PHP-Fehlerprotokolle Ihres Servers auf E-Mail-bezogene Fehler.
- **F: Das reCAPTCHA funktioniert nicht oder wird nicht angezeigt.**

  - **A:**
    1. **reCAPTCHA aktivieren:** Stellen Sie sicher, dass „ReCaptcha (v2)“ in der Hauptkonfiguration des Moduls auf „Ja“ eingestellt ist.
    2. **Schlüssel:** Überprüfen Sie nochmals, ob Ihr „ReCaptcha-Site-Key“ und „ReCaptcha-Secret-Key“ korrekt eingegeben sind und mit den Schlüsseln aus Ihrem Google reCAPTCHA-Konto für Ihre Domain übereinstimmen.
    3. **Domain-Registrierung:** Stellen Sie sicher, dass Ihre Domain in Ihrer Google reCAPTCHA-Admin-Konsole korrekt registriert ist.
    4. **Browser-Probleme:** Testen Sie in verschiedenen Browsern und leeren Sie den Browser-Cache. Manchmal können Ad-Blocker reCAPTCHA stören.
- **F: Wie übersetze ich die Formularfelder und Nachrichten in andere Sprachen?**

  - **A:**
    1. Gehen Sie zu **International > Übersetzungen**.
    2. Wählen Sie „Übersetzungen installierter Module“.
    3. Wählen Sie Ihr Theme, die Sprache, in die Sie übersetzen möchten, und dann „Produkt anfragen - Kontaktformulare Pro“ aus der Modulliste.
    4. Sie können dann alle sichtbaren Zeichenfolgen, Feldbezeichnungen und Nachrichten, die vom Modul verwendet werden, übersetzen. Denken Sie daran, Ihre Änderungen zu speichern.
- **F: Das Formular-Styling sieht mit meinem benutzerdefinierten Theme seltsam aus.**

  - **A:**
    1. **Template-Support-Profil:** Versuchen Sie, die Einstellung „Template-Support-Profil“ in der Hauptkonfiguration des Moduls anzupassen, um zu sehen, ob ein anderes Profil besser funktioniert.
    2. **Benutzerdefiniertes CSS:** Verwenden Sie das Feld „Benutzerdefiniertes CSS (nur Produktseite)“ in der Modulkonfiguration, um spezifische CSS-Regeln hinzuzufügen, um das Styling zu überschreiben oder anzupassen. Hierfür benötigen Sie grundlegende CSS-Kenntnisse oder einen Webentwickler.
    3. **Theme-Overrides:** Für umfangreichere Änderungen muss ein Entwickler möglicherweise Theme-Overrides für die Template-Dateien (`.tpl`) oder CSS-Dateien des Moduls erstellen und diese in das `modules/aappro/`-Verzeichnis Ihres Themes legen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul „Produkt anfragen - Kontaktformulare Pro“, der für Entwickler, Webmaster und technische Agenturen bestimmt ist.

### 4.1 Architekturübersicht

Das Modul folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller) und erweitert PrestaShop-Kernklassen für seine Funktionalität. Es nutzt `ModuleFrontController` für Front-Office-Interaktionen (Formularübermittlung, Antworten) und `AdminController` für die Back-Office-Verwaltung von Formularen und Fragen. Benutzerdefinierte `ObjectModel`-Klassen (`AapproCustomFields`, `AapproFormMatcher`) werden verwendet, um modulspezifische Daten zu speichern. Hooks werden ausgiebig verwendet, um das Formular in verschiedene Teile des Front-Office zu integrieren.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/index.php`
  - **Klassenname & übergeordnete Klasse:** `AapproIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Behandelt wahrscheinlich das anfängliche Rendern des Formulars oder einen Trigger für das Formular, möglicherweise über AJAX. Es könnte Daten für das Formular-Template vorbereiten.
- `controllers/front/question.php`
  - **Klassenname & übergeordnete Klasse:** `AapproQuestionModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist für die Verarbeitung der Übermittlung des Produktanfrageformulars verantwortlich. Er validiert Eingaben, handhabt die reCAPTCHA-Verifizierung, verarbeitet Dateiuploads (falls aktiviert), speichert die Frage in der Datenbank, sendet E-Mail-Benachrichtigungen an den Shop-Betreiber und möglicherweise eine automatische Antwort an den Kunden. Er gibt JSON-Antworten für AJAX-Übermittlungen zurück.
- `controllers/front/reply.php`
  - **Klassenname & übergeordnete Klasse:** `AapproReplyModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller handhabt wahrscheinlich den kundenorientierten Antwortmechanismus, wenn das Modul es Kunden ermöglicht, Antworten im Front-Office anzuzeigen oder einen spezifischen Link zur Anzeige von Antworten bereitstellt. Er würde die Frage und die zugehörigen Antworten abrufen.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminAapproForm.php`
  - **Klassenname & übergeordnete Klasse:** `AdminAapproFormController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Verwaltet benutzerdefinierte Anfrageformulare. Zugänglich über **Module > Produkt anfragen > Formulare**. Es handhabt die CRUD-Operationen für `AapproFormMatcher`-Objekte, einschließlich der Definition von Formularnamen, Aktivierungsstatus, zugehörigen Produkten/Kategorien/Herstellern und benutzerdefinierten Feldern.
- `controllers/admin/AdminAapproQuestion.php`
  - **Klassenname & übergeordnete Klasse:** `AdminAapproQuestionController` erweitert `ModuleAdminController`.
  - **Tab-Name und verwaltete Entität:** Verwaltet eingereichte Kundenfragen. Zugänglich über **Module > Produkt anfragen > Fragen**. Es bietet eine Listenansicht der Fragen, ermöglicht die Anzeige vollständiger Fragedetails und bietet eine Oberfläche zum Antworten auf Kunden und zum Aktualisieren des Fragenstatus.
- `controllers/admin/index.php`
  - **Klassenname & übergeordnete Klasse:** Kein funktionaler Controller.
  - **Verantwortlichkeit:** Standard-PrestaShop-Sicherheitsdatei zur Verhinderung der Verzeichnisauflistung. Sie leitet typischerweise zum Admin-Dashboard weiter.

### 4.3 Kernklassen & Modelle (`classes/`)

- `classes/AapproCustomFields.php`
  - **Mit welcher Datenbanktabelle interagiert es:** Wahrscheinlich `ps_aappro_custom_field` (oder ähnlich).
  - **Erweitert ObjectModel:** Ja, es erweitert `ObjectModel`.
  - **`$definition`-Felder:** Würde Felder wie `id_aappro_custom_field`, `id_aappro_form`, `name`, `type`, `label`, `required`, `options` (für Auswahlfelder, oft JSON-kodiert), `position`, `active` definieren.
  - **Wichtige öffentliche Methoden und Geschäftslogik:** Methoden zum Speichern, Abrufen und Löschen von benutzerdefinierten Felddefinitionen, die mit spezifischen Formularen verknüpft sind. Logik zum Parsen und Rendern von benutzerdefinierten Felddaten.
- `classes/AapproFormMatcher.php`
  - **Mit welcher Datenbanktabelle interagiert es:** Wahrscheinlich `ps_aappro_form` (oder ähnlich).
  - **Erweitert ObjectModel:** Ja, es erweitert `ObjectModel`.
  - **`$definition`-Felder:** Würde Felder wie `id_aappro_form`, `name`, `active`, `recipient_emails`, `products` (JSON-kodiertes Array von Produkt-IDs), `categories` (JSON-kodiertes Array von Kategorie-IDs), `manufacturers` (JSON-kodiertes Array von Hersteller-IDs), `display_product`, `display_category`, `display_manufacturer` definieren.
  - **Wichtige öffentliche Methoden und Geschäftslogik:** Methoden zur Verwaltung von Formular-Konfigurationen, einschließlich des Speicherns von Verknüpfungen mit Produkten/Kategorien/Herstellern und des Abrufens des korrekten Formulars basierend auf dem aktuellen Kontext (Produkt-ID, Kategorie-ID).

### 4.4 JavaScript-Assets (`views/js/`)

- `aappro/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Bietet Autocomplete-Funktionalität zur Auswahl von Produkten, Kategorien oder Herstellern bei der Konfiguration von Formularen im `AdminAapproFormController`. Bindet an Eingabefelder, um Entitäten vorzuschlagen, während der Benutzer tippt, was die UX für die Formularzuordnung verbessert.
- `aappro/views/aappro.js`
  - **Geltungsbereich:** Front-Office.
  - **Beschreibung:** Haupt-Front-Office-Skript für das Modul.
    - **Event-Listener:** Bindet Klick-Events an „Frage stellen“-Buttons/Links, Submit-Events an die Anfrageformulare.
    - **DOM-Manipulation:** Handhabt das Anzeigen/Ausblenden des Formulars (z. B. in einem Modal oder einem erweiterbaren Bereich), das Anzeigen von Erfolgs-/Fehlermeldungen (Toast-Benachrichtigungen).
    - **AJAX-Aufrufe:** Sendet Formulardaten asynchron an `AapproQuestionModuleFrontController`, verarbeitet die reCAPTCHA-Antwort und aktualisiert die Benutzeroberfläche basierend auf der JSON-Antwort des Servers.
    - **Validierung:** Kann clientseitige Validierung für Formularfelder (z. B. minimale/maximale Länge) enthalten.
- `aappro/views/js/admin-button-style.js`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Bietet wahrscheinlich interaktive Elemente oder Vorschauen zur Konfiguration von Button-Stilen (z. B. Farbwähler, Größenregler) innerhalb der Konfigurations- oder Formularverwaltungsbildschirme des Moduls.
- `aappro/views/js/admin-form-layout.js`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Handhabt das dynamische Layout und die Interaktion zum Erstellen/Bearbeiten von Formularen im `AdminAapproFormController`, insbesondere zur Verwaltung benutzerdefinierter Felder. Dies könnte das Hinzufügen/Entfernen von benutzerdefinierten Feldzeilen, das Neuanordnen von Feldern und die Verwaltung feldspezifischer Optionen umfassen.
- `aappro/views/js/admin-icon-picker-data.js`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Enthält Daten (z. B. ein Array von Icon-Klassen oder SVG-Pfaden) für eine Icon-Picker-Oberfläche, die im Back-Office verwendet wird, möglicherweise für benutzerdefinierte Feld-Icons oder Formularanzeigeoptionen.
- `aappro/views/js/admin-icon-picker.js`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Implementiert die UI-Logik des Icon-Pickers, die es Administratoren ermöglicht, Icons aus einem vordefinierten Satz auszuwählen, wahrscheinlich in Verbindung mit `admin-icon-picker-data.js`.

### 4.5 CSS-Stylesheets (`views/css/`)

- `aappro/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back-Office.
  - **Beschreibung:** Stile für die Autocomplete-Dropdowns und Eingabefelder, die in der Admin-Formularkonfiguration verwendet werden (z. B. zur Auswahl von Produkten/Kategorien).
- `aappro/views/aappro.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Beschreibung:** Kern-Styling für die Produktanfrageformulare, Buttons, Modals, Erfolgs-/Fehlermeldungen (Toast-Benachrichtigungen) und alle anderen Front-Office-Elemente, die vom Modul gerendert werden.
  - **Wichtige CSS-Klassenselektoren:** `.aappro-form-container`, `.aappro-form-trigger`, `.aappro-modal`, `.aappro-field-group`, `.aappro-submit-button`, `.aappro-success-toast`, `.aappro-error-toast`.
- `aappro/views/css/admin-button-style.css`
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Beschreibung:** Stile für die Button-Konfigurationselemente innerhalb der Admin-Oberfläche des Moduls.
- `aappro/views/css/admin-custom-fields.css`
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Beschreibung:** Stile für die dynamische Verwaltungsoberfläche für benutzerdefinierte Felder im `AdminAapproFormController`, die ein klares und benutzerfreundliches Layout zum Hinzufügen/Bearbeiten von benutzerdefinierten Feldern gewährleisten.
- `aappro/views/css/admin-form-layout.css`
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Beschreibung:** Allgemeines Layout und Styling für die Formularerstellungs-/Bearbeitungsbildschirme im Admin-Panel, das ein konsistentes Erscheinungsbild bietet.
- `aappro/views/css/admin-icon-picker.css`
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Beschreibung:** Stile für die Icon-Picker-Oberfläche, die im Admin-Panel verwendet wird.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `aappro/views/aappro-extra-forms.tpl`
  - **Hook:** `displayProductExtraContent` oder ähnlich.
  - **Ausgabe:** Rendert zusätzliche Formulare oder Inhaltsblöcke, die mit dem Produkt zusammenhängen, möglicherweise das Anfrageformular selbst oder einen Trigger dafür.
- `aappro/views/aappro-extra-trigger.tpl`
  - **Hook:** `displayProductButtons`, `displayProductAdditionalInfo`.
  - **Ausgabe:** Rendert einen Button oder Link (z. B. „Frage stellen“), der die Anzeige des Anfrageformulars auslöst, oft in einem Modal oder einem ausgeblendeten Bereich.
- `aappro/views/aappro-extra.tpl`
  - **Hook:** `displayProductExtraContent`, `displayProductAdditionalInfo`.
  - **Ausgabe:** Ein allgemeines Template für zusätzlichen Inhalt auf der Produktseite, das möglicherweise das Formular oder seinen Trigger umschließt.
- `aappro/views/aappro-faq-tab-title.tpl`
  - **Hook:** `displayProductTab`.
  - **Ausgabe:** Rendert den Titel für einen Produkt-Tab (z. B. „Frage stellen“ oder „FAQ“), der beim Klicken den Formularinhalt enthüllt.
- `aappro/views/aappro-faq-tab.tpl`
  - **Hook:** `displayProductTabContent`.
  - **Ausgabe:** Rendert den eigentlichen Inhalt des Produkt-Tabs, der das Anfrageformular selbst wäre.
- `aappro/views/aappro-form-body.tpl`
  - **Hook:** Interne Einbindung.
  - **Ausgabe:** Die Kern-HTML-Struktur für die Anfrageformularfelder (Name, E-Mail, Frage, benutzerdefinierte Felder, reCAPTCHA, DSGVO-Kontrollkästchen). Dies wird wahrscheinlich von anderen Templates eingebunden.
- `aappro/views/aappro-form-tab.tpl`
  - **Hook:** `displayProductTabContent`.
  - **Ausgabe:** Ähnlich wie `aappro-faq-tab.tpl`, speziell zum Rendern des Formulars innerhalb eines Produkt-Tabs.
- `aappro/views/aappro-product-embed.tpl`
  - **Hook:** `displayProductAdditionalInfo`, `displayReassurance`.
  - **Ausgabe:** Bettet das Anfrageformular direkt in den Produktseiteninhalt ein, anstatt in einem Tab oder Modal.
- `aappro/views/classic/` (und `views/partials/`)
  - Diese Verzeichnisse enthalten themenspezifische Templates (für das Classic-Theme) und wiederverwendbare Partials. Sie spiegeln die Struktur des Hauptverzeichnisses `views/` wider, sind aber für das Classic-Theme optimiert oder speziell gestaltet.
  - `aappro-custom-field-single.tpl`: Rendert ein einzelnes benutzerdefiniertes Feld basierend auf seinem Typ.
  - `aappro-custom-fields.tpl`: Iteriert und rendert alle benutzerdefinierten Felder für ein Formular.
  - `aappro-field-fragment.tpl`: Ein wiederverwendbares Fragment zum Rendern gängiger Formularfeldelemente.

#### Admin-Templates (`views/templates/admin/`)

- `aappro/views/templates/admin/button_style_block.tpl`
  - **Zweck:** Rendert die Oberfläche zur Konfiguration von Button-Stilen innerhalb des Admin-Panels.
- `aappro/views/templates/admin/conversation_reply.tpl`
  - **Zweck:** Rendert die Antwortoberfläche beim Anzeigen einer Kundenfrage im `AdminAapproQuestionController`.
- `aappro/views/templates/admin/custom_fields_block.tpl`
  - **Zweck:** Rendert die dynamische Oberfläche zum Hinzufügen, Bearbeiten und Verwalten von benutzerdefinierten Feldern im `AdminAapproFormController`.
- `aappro/views/templates/admin/form_layout_block.tpl`
  - **Zweck:** Rendert allgemeine Layout-Optionen für Formulare im Admin-Panel.
- `aappro/views/templates/admin/question_extras.tpl`
  - **Zweck:** Zeigt zusätzliche Details oder Aktionen zu einer spezifischen Frage im `AdminAapproQuestionController an`.
- `aappro/views/templates/admin/question_product_preview.tpl`
  - **Zweck:** Rendert eine kleine Vorschau des Produkts, das mit einer Frage im `AdminAapproQuestionController` verknüpft ist.
- `aappro/views/templates/admin/topic_options_block.tpl`
  - **Zweck:** Rendert die Konfigurationsoberfläche zur Definition verfügbarer Themen für das Dropdown-Menü „Themenauswahl“.
- `aappro/views/templates/admin/view_question.tpl`
  - **Zweck:** Das Haupt-Template zur Anzeige einer einzelnen Kundenfrage und ihrer Details im `AdminAapproQuestionController`.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- `ps_aappro_form`: Speichert die Definitionen jedes vom Händler erstellten benutzerdefinierten Anfrageformulars.

  - `id_aappro_form` (PK)
  - `name` (VARCHAR)
  - `active` (TINYINT)
  - `recipient_emails` (TEXT)
  - `products` (TEXT, JSON-kodiertes Array von Produkt-IDs)
  - `categories` (TEXT, JSON-kodiertes Array von Kategorie-IDs)
  - `manufacturers` (TEXT, JSON-kodiertes Array von Hersteller-IDs)
  - `display_product` (TINYINT)
  - `display_category` (TINYINT)
  - `display_manufacturer` (TINYINT)
- `ps_aappro_custom_field`: Speichert die Definitionen benutzerdefinierter Felder, die mit jedem Formular verknüpft sind.

  - `id_aappro_custom_field` (PK)
  - `id_aappro_form` (FK zu `ps_aappro_form`)
  - `name` (VARCHAR)
  - `type` (VARCHAR, z. B. „text“, „textarea“, „select“, „checkbox“)
  - `label` (TEXT, mehrsprachig)
  - `required` (TINYINT)
  - `options` (TEXT, JSON-kodiert für Auswahl-/Radiooptionen)
  - `position` (INT)
  - `active` (TINYINT)
- `ps_aappro_question`: Speichert jede eingereichte Kundenfrage.

  - `id_aappro_question` (PK)
  - `id_product` (FK zu `ps_product`)
  - `id_customer` (FK zu `ps_customer`, falls angemeldet)
  - `id_aappro_form` (FK zu `ps_aappro_form`)
  - `customer_name` (VARCHAR)
  - `customer_email` (VARCHAR)
  - `customer_phone` (VARCHAR, falls aktiviert)
  - `topic` (VARCHAR, falls aktiviert)
  - `quantity_request` (INT, falls aktiviert)
  - `question_text` (TEXT)
  - `attachment_path` (VARCHAR, falls aktiviert)
  - `custom_fields_data` (TEXT, JSON-kodiertes Array von benutzerdefinierten Feldwerten)
  - `ip_address` (VARCHAR)
  - `date_add` (DATETIME)
  - `status` (VARCHAR, z. B. „new“, „replied“, „closed“)
- `ps_aappro_question_reply`: Speichert Antworten des Admins auf Kundenfragen.

  - `id_aappro_question_reply` (PK)
  - `id_aappro_question` (FK zu `ps_aappro_question`)
  - `id_employee` (FK zu `ps_employee`)
  - `reply_text` (TEXT)
  - `date_add` (DATETIME)
- **Konfigurationsdatensätze (in der Tabelle `ps_configuration`):**

  - `aappro_TITLE`
  - `aappro_AUTORESPONDER`
  - `aappro_FIELD_PHONE_REQUIRED`
  - `aappro_FIELD_PHONE_VISIBLE`
  - `aappro_FIELD_TOPIC_VISIBLE`
  - `aappro_QUOTE_QUANTITY_VISIBLE`
  - `aappro_WEBHOOK_URL`
  - `aappro_Q_LEN_MIN`
  - `aappro_Q_LEN_MAX`
  - `aappro_ATTACHMENT_ENABLE`
  - `aappro_ATTACHMENT_MAX_MB`
  - `aappro_SHOP_MAIL_BCC`
  - `aappro_TOAST_MS`
  - `aappro_FLOAT_DELAY_MS`
  - `aappro_THEME_SUPPORT`
  - `aappro_CUSTOM_CSS`
  - `aappro_CUSTOM_FIELDS_JSON` (wahrscheinlich zugunsten der Tabelle `ps_aappro_custom_field` veraltet)
  - `aappro_recaptcha`
  - `aappro_GDPR`
  - `aappro_GDPRCMS`
  - `aappro_recaptcha_sitekey`
  - `aappro_ALLOW_COMMENTS`
  - `aappro_recaptcha_secretkey`
  - `aappro_emailslist`
  - `aappro_HIDE_OOS`
  - `aappro_LOGGED_CUSTOMERS_ONLY`

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Registriert CSS/JS-Assets, initialisiert globale JS-Variablen oder rendert versteckte Elemente für die Modulfunktionalität. |
| `displayFooter` | Am Ende jeder Seite, vor `</body>`. | Kann verwendet werden, um Modal-HTML, schwebende Buttons oder Skripte einzufügen, die nach dem Laden der Seite ausgeführt werden müssen. |
| `displayProductExtraContent` | Im „Extra-Inhalt“-Block auf Produktseiten (oft unter der Beschreibung). | Rendert das Anfrageformular oder einen Trigger dafür, oft als vollständiger Block. |
| `displayProductAdditionalInfo` | Im Produktinformationsblock, typischerweise in der Nähe von Preis/In den Warenkorb. | Rendert einen kleineren Trigger oder ein kompaktes Formular direkt innerhalb der Hauptproduktinformationen. |
| `displayProductButtons` | In der Nähe des „In den Warenkorb“-Buttons. | Rendert einen Button oder Link zum Öffnen des Anfrageformulars. |
| `displayProductTab` | Zum Hinzufügen eines neuen Tab-Titels auf der Produktseite. | Rendert den Tab-Titel „Frage stellen“ oder „FAQ“. |
| `displayProductTabContent` | Zum Hinzufügen von Inhalt zu einem neuen Tab auf der Produktseite. | Rendert das eigentliche Anfrageformular innerhalb seines dedizierten Produkt-Tabs. |
| `displayReassurance` | Im Reassurance-Block (z. B. „sichere Zahlung“, „kostenloser Versand“). | Kann verwendet werden, um einen kleinen „Frage stellen“-Link oder ein Icon innerhalb des Reassurance-Blocks einzufügen. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller geladen wird und seine Medien-Assets gesetzt werden. | Registriert modulspezifisches CSS und JS für die Back-Office-Controller (`AdminAapproForm`, `AdminAapproQuestion`). |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | (Nicht direkt von der Kernfunktion dieses Moduls verwendet, könnte aber für Folgefragen nach dem Kauf verwendet werden, wenn erweitert). |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Produkt anfragen - Kontaktformulare Pro“ besuchen Sie bitte Ihr Kundenkonto bei MyPresta.eu. Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Modulfunktionalität gerne zur Verfügung. Stellen Sie immer sicher, dass Sie die neueste kompatible Version des Moduls verwenden, um optimale Leistung und Sicherheit zu gewährleisten.

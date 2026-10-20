---
title: "EU Return Button – Online Withdrawal Form - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „EU Return Button – Online Withdrawal Form“ von MyPresta.eu."
sidebar:
  label: "EU Return Button – Online Withdrawal Form - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul EU Return Button – Online Withdrawal Form auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/eu-return-button-online-withdrawal-form/)
>
> ---


# EU Return Button – Online Withdrawal Form

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten modernen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Backoffice > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das allgemeine Verhalten und Aussehen des Rücksende-Buttons und -Formulars steuern.

#### Registerkarte Allgemeine Einstellungen

- **Modul aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das gesamte Modul.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Rücksende-Button und das Online-Widerrufsformular werden aktiv und sind für Kunden gemäß Ihren anderen Einstellungen sichtbar.
    - *Wenn deaktiviert:* Das Modul ist vollständig deaktiviert. Der Button wird nicht angezeigt und die Formulare sind nicht zugänglich.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Sie würden dies nur deaktivieren, wenn Sie vorübergehend keine Online-Rücksendungen anbieten möchten, z. B. während Wartungsarbeiten oder einer Richtlinienänderung.
- **Rücksende-Button anzeigen in:**

  - **Was diese Einstellung bewirkt:** Legt fest, wo der Haupt-Button „Rücksenden“ oder „Widerruf“ im Front-Office Ihres Shops angezeigt wird. Sie können mehrere Standorte auswählen.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn ausgewählt (z. B. Header):* Ein Button erscheint an der gewählten Stelle und bietet einen direkten Link zum Rücksendeformular.
    - *Wenn nicht ausgewählt:* Der Button erscheint nicht an diesem spezifischen Ort.
  - **Empfohlener Wert:** Header und/oder Footer für einfachen Zugang, und Produktseite, um Kunden im Voraus zu informieren.
  - **Händlerszenario / Beispiel:** Wenn Kunden die Rücksendeoption von jeder Seite aus leicht finden sollen, aktivieren Sie „Header“ und „Footer“. Wenn Sie Ihre Rückgaberichtlinien auf Produktseiten hervorheben möchten, aktivieren Sie „Produktseite“.
- **Button-Text:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, den auf dem Rücksende-Button angezeigten Text anzupassen.
  - **Auswirkungen der Änderung dieser Einstellung:** Der Text auf dem Button ändert sich zu Ihrem angegebenen Wert.
  - **Empfohlener Wert:** „Rücksendeanfrage“, „Online-Widerrufsformular“ oder „Rücksendung starten“.
  - **Händlerszenario / Beispiel:** Sie könnten ihn von „Rücksenden“ in „Widerrufsformular“ ändern, um ihn an spezifische rechtliche Terminologie in Ihrer Region anzupassen.
- **Mindestbestellstatus für Widerruf:**

  - **Was diese Einstellung bewirkt:** Definiert den frühesten Bestellstatus, bei dem ein Kunde eine Rücksendeanfrage für eine Bestellung initiieren kann. Bestellungen mit einem Status unterhalb dessen sind nicht berechtigt.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn auf „Zahlung akzeptiert“ gesetzt:* Kunden können eine Rücksendung erst anfordern, wenn ihre Zahlung erfolgreich verarbeitet wurde.
    - *Wenn auf „Versandt“ gesetzt:* Kunden können eine Rücksendung erst anfordern, nachdem ihre Bestellung als versandt markiert wurde.
  - **Empfohlener Wert:** „Zahlung akzeptiert“ oder „Versandt“, je nach Ihrer Richtlinie.
  - **Händlerszenario / Beispiel:** Wenn Sie Rücksendungen nur für Artikel akzeptieren, die tatsächlich bezahlt und bearbeitet wurden, setzen Sie dies auf „Zahlung akzeptiert“. Wenn Sie Rücksendungen nur für Artikel akzeptieren, die Ihr Lager bereits verlassen haben, setzen Sie es auf „Versandt“.
- **Maximale Tage für Widerruf:**

  - **Was diese Einstellung bewirkt:** Legt die maximale Anzahl von Tagen nach der Bestellung (oder dem Versand, je nach Ihrer Richtlinie) fest, innerhalb derer ein Kunde eine Rücksendeanfrage einreichen kann.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn auf 14 gesetzt:* Kunden haben 14 Tage ab Bestelldatum Zeit, eine Rücksendung anzufordern. Nach 14 Tagen ist die Option für diese Bestellung nicht mehr verfügbar.
    - *Wenn auf 30 gesetzt:* Kunden haben 30 Tage Zeit.
  - **Empfohlener Wert:** 14 (für Standard-EU-Konformität) oder 30 (wenn Sie eine verlängerte Rückgabefrist anbieten).
  - **Händlerszenario / Beispiel:** Um dem standardmäßigen 14-tägigen EU-Widerrufsrecht zu entsprechen, setzen Sie dies auf 14. Wenn Sie eine großzügigere Richtlinie anbieten, können Sie es auf 30 oder mehr Tage verlängern.
- **Gäste-Widerrufe zulassen:**

  - **Was diese Einstellung bewirkt:** Legt fest, ob Kunden, die als Gäste bestellt haben (ohne ein Konto zu erstellen), das Online-Widerrufsformular nutzen können.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Gastkunden können auf das Formular zugreifen, indem sie ihre Bestellreferenz und E-Mail-Adresse angeben.
    - *Wenn deaktiviert:* Nur registrierte Kunden, die angemeldet sind, können eine Rücksendung initiieren.
  - **Empfohlener Wert:** JA (für maximalen Kundenkomfort und EU-Konformität).
  - **Händlerszenario / Beispiel:** Die Aktivierung dieser Option stellt sicher, dass alle Kunden, unabhängig von ihrer Checkout-Methode, problemlos eine Rücksendung initiieren können, was für die Einhaltung der Vorschriften und die Kundenzufriedenheit entscheidend ist.
- **Anhänge zulassen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Kunden das Hochladen von Dateien (z. B. Fotos von beschädigten Produkten, Kaufbeleg) beim Einreichen ihrer Rücksendeanfrage.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Upload-Feld erscheint im Formular.
    - *Wenn deaktiviert:* Kunden können keine Dateien hochladen.
  - **Empfohlener Wert:** JA (insbesondere für Produkte, bei denen visueller Nachweis für Schäden oder Mängel erforderlich sein könnte).
  - **Händlerszenario / Beispiel:** Wenn Sie zerbrechliche Artikel verkaufen, hilft das Zulassen von Anhängen Kunden, schnell Beweise für Schäden zu liefern, was den Lösungsprozess beschleunigt.
- **Maximale Anhangsgröße (MB):**

  - **Was diese Einstellung bewirkt:** Legt die maximale Dateigröße für jeden Anhang fest, den ein Kunde hochladen kann.
  - **Auswirkungen der Änderung dieser Einstellung:** Dateien, die größer als dieses Limit sind, werden vom Formular abgelehnt.
  - **Empfohlener Wert:** 2-5 MB.
  - **Händlerszenario / Beispiel:** Das Festlegen eines angemessenen Limits verhindert, dass Kunden übermäßig große Dateien hochladen, die Ihren Server oder Ihr E-Mail-System verlangsamen könnten.
- **Zulässige Anhangs-Erweiterungen (kommagetrennt):**

  - **Was diese Einstellung bewirkt:** Gibt an, welche Dateitypen (z. B. jpg, png, pdf) Kunden hochladen dürfen.
  - **Auswirkungen der Änderung dieser Einstellung:** Nur Dateien mit diesen Erweiterungen werden akzeptiert.
  - **Empfohlener Wert:** jpg, jpeg, png, gif, pdf.
  - **Händlerszenario / Beispiel:** Die Beschränkung auf gängige Bild- und Dokumentformate stellt sicher, dass Sie brauchbare Dateien erhalten und bösartige Uploads verhindert werden.
- **Statusnachricht erforderlich:**

  - **Was diese Einstellung bewirkt:** Wenn Sie den Status einer Rücksendeanfrage im Backoffice ändern, bestimmt diese Einstellung, ob Sie eine Nachricht an den Kunden hinzufügen müssen.
  - **Auswirkungen der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Ein Eingabefeld für eine Nachricht ist obligatorisch, wenn ein Rücksendestatus aktualisiert wird.
    - *Wenn deaktiviert:* Sie können Status ändern, ohne eine Nachricht hinzuzufügen.
  - **Empfohlener Wert:** JA (für klare Kommunikation und Audit-Trails).
  - **Händlerszenario / Beispiel:** Die Aktivierung dieser Option stellt sicher, dass Ihr Team dem Kunden beim Ändern des Status immer einen Grund oder ein Update mitteilt, was die Transparenz verbessert.

#### Registerkarte Bestellstatus

Diese Registerkarte ermöglicht es Ihnen, die verschiedenen Status für Rücksendeanfragen zu definieren und wie sie mit Ihren bestehenden PrestaShop-Bestellstatus interagieren.

- **Neuer Widerrufsstatus:**

  - **Was diese Einstellung bewirkt:** Wählt den PrestaShop-Bestellstatus aus, der einer neuen Rücksendeanfrage zugewiesen wird, wenn sie zum ersten Mal von einem Kunden eingereicht wird.
  - **Auswirkungen der Änderung dieser Einstellung:** Alle neuen Rücksendeanfragen werden in Ihrem Backoffice automatisch mit diesem Status markiert.
  - **Empfohlener Wert:** Erstellen Sie einen neuen benutzerdefinierten Bestellstatus wie „Rücksendung angefordert“ oder „Widerruf ausstehend“ zur klaren Identifizierung.
  - **Händlerszenario / Beispiel:** Durch die Erstellung eines spezifischen Status „Rücksendung angefordert“ kann Ihr Kundenservice-Team neue Rücksendeanfragen, die ihre Aufmerksamkeit erfordern, leicht filtern und identifizieren.
- **Akzeptierter Widerrufsstatus:**

  - **Was diese Einstellung bewirkt:** Wählt den PrestaShop-Bestellstatus aus, der zugewiesen wird, wenn Sie als Händler die Rücksendeanfrage eines Kunden akzeptieren.
  - **Auswirkungen der Änderung dieser Einstellung:** Wenn Sie eine Rücksendung im Modul als „Akzeptiert“ markieren, ändert sich ihr Status zu diesem ausgewählten Bestellstatus.
  - **Empfohlener Wert:** Erstellen Sie einen neuen benutzerdefinierten Bestellstatus wie „Rücksendung akzeptiert“ oder „Widerruf genehmigt“.
  - **Händlerszenario / Beispiel:** Sobald Sie eine Anfrage überprüft und genehmigt haben, kann die Änderung ihres Status auf „Rücksendung akzeptiert“ eine E-Mail an den Kunden mit weiteren Anweisungen auslösen.
- **Abgelehnter Widerrufsstatus:**

  - **Was diese Einstellung bewirkt:** Wählt den PrestaShop-Bestellstatus aus, der zugewiesen wird, wenn Sie die Rücksendeanfrage eines Kunden ablehnen.
  - **Auswirkungen der Änderung dieser Einstellung:** Wenn Sie eine Rücksendung im Modul als „Abgelehnt“ markieren, ändert sich ihr Status zu diesem ausgewählten Bestellstatus.
  - **Empfohlener Wert:** Erstellen Sie einen neuen benutzerdefinierten Bestellstatus wie „Rücksendung abgelehnt“ oder „Widerruf abgelehnt“.
  - **Händlerszenario / Beispiel:** Wenn eine Rücksendeanfrage außerhalb Ihrer Richtlinien liegt (z. B. nach Ablauf der Rückgabefrist), würden Sie ihren Status auf „Rücksendung abgelehnt“ ändern und idealerweise eine Nachricht senden, die den Grund erklärt.
- **Geschlossener Widerrufsstatus:**

  - **Was diese Einstellung bewirkt:** Wählt den PrestaShop-Bestellstatus aus, der zugewiesen wird, wenn eine Rücksendeanfrage abgeschlossen oder gelöst ist (z. B. Rückerstattung erfolgt, Ersatz gesendet).
  - **Auswirkungen der Änderung dieser Einstellung:** Wenn Sie eine Rücksendung im Modul als „Geschlossen“ markieren, ändert sich ihr Status zu diesem ausgewählten Bestellstatus.
  - **Empfohlener Wert:** Erstellen Sie einen neuen benutzerdefinierten Bestellstatus wie „Rücksendung abgeschlossen“ oder „Widerruf geschlossen“.
  - **Händlerszenario / Beispiel:** Nachdem eine Rückerstattung bearbeitet wurde, bietet die Markierung der Rücksendung als „Rücksendung abgeschlossen“ einen klaren Audit-Trail und entfernt sie aus Ihrer aktiven Rücksende-Warteschlange.
- **Bestellstatus, die vom Widerruf ausgeschlossen werden sollen:**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl spezifischer PrestaShop-Bestellstatus, für die Kunden *keine* Rücksendeanfrage initiieren können, selbst wenn sie andere Kriterien erfüllen.
  - **Auswirkungen der Änderung dieser Einstellung:** Bestellungen mit einem der ausgewählten Status zeigen dem Kunden die Rücksendeoption nicht an.
  - **Empfohlener Wert:** „Storniert“, „Erstattet“, „Fehler“ oder jeder andere Status, der anzeigt, dass eine Bestellung nicht mehr für eine neue Rücksendeanfrage berechtigt ist.
  - **Händlerszenario / Beispiel:** Wenn eine Bestellung bereits „Erstattet“ wurde, möchten Sie nicht, dass ein Kunde eine weitere Rücksendeanfrage dafür einreichen kann.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### Widerrufsanfragen (Backoffice > Bestellungen > Widerrufsanfragen)

Dies ist die zentrale Anlaufstelle für die Verwaltung aller Rücksende- und Widerrufsanfragen, die von Ihren Kunden eingereicht wurden.

- **Bildschirmname & Menüpfad:** Sie finden diesen Bildschirm, indem Sie im PrestaShop-Backoffice-Menü zu **Bestellungen > Widerrufsanfragen** navigieren.
- **Verfügbare Aktionen & Einstellungen:**
  - **Listentabelle:** Zeigt eine umfassende Liste aller Rücksendeanfragen, einschließlich:
    - **ID:** Eindeutiger Bezeichner für die Anfrage.
    - **Kundenname:** Der Kunde, der die Anfrage eingereicht hat.
    - **Bestellreferenz:** Die zugehörige PrestaShop-Bestellung.
    - **Datum:** Wann die Anfrage eingereicht wurde.
    - **Status:** Der aktuelle Status der Anfrage (z. B. „Rücksendung angefordert“, „Rücksendung akzeptiert“).
    - **Aktionen:** Schaltflächen zum „Anzeigen“ der Anfragedetails, Ändern des Status oder Ausführen anderer Verwaltungsaufgaben.
  - **Filtern & Suchen:** Sie können die Liste nach Status, Kunde, Bestellreferenz und Datumsbereich filtern, um schnell bestimmte Anfragen zu finden.
  - **Massenaktionen:** Ermöglicht Ihnen, mehrere Anfragen auszuwählen und Aktionen wie das gleichzeitige Ändern ihres Status durchzuführen.
  - **Details anzeigen:** Durch Klicken auf „Anzeigen“ für eine bestimmte Anfrage wird eine Detailseite geöffnet, auf der Sie:
    - Alle vom Kunden bereitgestellten Informationen (Grund, Kommentare, angehängte Dateien) sehen können.
    - Die in der Rücksendeanfrage enthaltenen Produkte überprüfen können.
    - Eine Historie der Statusänderungen und interne Notizen einsehen können.
    - Private Notizen für die interne Teamkommunikation hinzufügen können.
    - Den Status der Anfrage ändern können (z. B. von „Rücksendung angefordert“ zu „Rücksendung akzeptiert“).
    - Nachrichten an den Kunden senden können (wenn „Statusnachricht erforderlich“ aktiviert ist).
    - Anhänge herunterladen können.
    - Das Widerrufsformular drucken können.
- **Auswirkungen von Änderungen:**
  - **Status ändern:** Aktualisiert den Status der Rücksendeanfrage, was E-Mail-Benachrichtigungen an den Kunden auslösen und die Anzeige in dessen Kundenkonto aktualisieren kann.
  - **Notizen hinzufügen:** Zeichnet interne Kommunikation oder Entscheidungen im Zusammenhang mit der Anfrage auf, die nur für Backoffice-Benutzer sichtbar sind.
  - **Nachrichten senden:** Kommuniziert direkt mit dem Kunden bezüglich seiner Rücksendeanfrage.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. Überprüfen Sie regelmäßig die Liste „Widerrufsanfragen“ auf neue Anfragen (Status „Rücksendung angefordert“).
  2. Überprüfen Sie jede neue Anfrage, indem Sie die Bestelldetails, Kundenkommentare und eventuelle Anhänge prüfen.
  3. Entscheiden Sie, ob Sie die Anfrage basierend auf der Rückgaberichtlinie Ihres Shops annehmen oder ablehnen.
  4. Ändern Sie den Status entsprechend (z. B. auf „Rücksendung akzeptiert“ oder „Rücksendung abgelehnt“). Wenn „Statusnachricht erforderlich“ aktiviert ist, geben Sie dem Kunden eine klare Nachricht.
  5. Führen Sie die nächsten Schritte aus (z. B. Rückerstattung veranlassen, Rücksendung arrangieren) und aktualisieren Sie den Status auf „Rücksendung abgeschlossen“, sobald der Fall gelöst ist.
  6. Verwenden Sie interne Notizen für die Teamkommunikation oder zur Aufzeichnung spezifischer durchgeführter Aktionen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Modul aktivieren | JA | Aktiviert/deaktiviert das gesamte Modul. |
|  | Rücksende-Button anzeigen in | Header, Footer, Produktseite | Steuert, wo der Rücksende-Button im Front-Office erscheint. |
|  | Button-Text | „Rücksendeanfrage“ | Passt den Text auf dem Rücksende-Button an. |
|  | Mindestbestellstatus für Widerruf | „Zahlung akzeptiert“ | Legt den frühesten Bestellstatus für die Rücksendeberechtigung fest. |
|  | Maximale Tage für Widerruf | 14 | Definiert das Rückgabezeitfenster in Tagen ab Bestelldatum. |
|  | Gäste-Widerrufe zulassen | JA | Ermöglicht nicht registrierten Kunden die Nutzung des Formulars. |
|  | Anhänge zulassen | JA | Aktiviert/deaktiviert Dateiuploads im Formular. |
|  | Maximale Anhangsgröße (MB) | 2-5 MB | Legt die maximale Größe für hochgeladene Dateien fest. |
|  | Zulässige Anhangs-Erweiterungen | jpg, jpeg, png, gif, pdf | Gibt zulässige Dateitypen für Uploads an. |
|  | Statusnachricht erforderlich | JA | Macht eine Nachricht beim Ändern des Rücksendestatus obligatorisch. |
| **Registerkarte Bestellstatus** | Neuer Widerrufsstatus | „Rücksendung angefordert“ (benutzerdefiniert) | Status für neu eingereichte Anfragen. |
|  | Akzeptierter Widerrufsstatus | „Rücksendung akzeptiert“ (benutzerdefiniert) | Status, wenn Händler eine Anfrage genehmigt. |
|  | Abgelehnter Widerrufsstatus | „Rücksendung abgelehnt“ (benutzerdefiniert) | Status, wenn Händler eine Anfrage ablehnt. |
|  | Geschlossener Widerrufsstatus | „Rücksendung abgeschlossen“ (benutzerdefiniert) | Status, wenn eine Anfrage vollständig gelöst ist. |
|  | Bestellstatus, die vom Widerruf ausgeschlossen werden sollen | „Storniert“, „Erstattet“ | Verhindert Rücksendungen für Bestellungen mit diesen Status. |
| **Widerrufsanfragen (Admin)** | Anfrage anzeigen/bearbeiten | N/A | Einzelne Rücksendeanfragen verwalten, Status ändern, Notizen hinzufügen. |
|  | Filtern/Suchen | N/A | Spezifische Anfragen nach verschiedenen Kriterien finden. |
|  | Massenaktionen | N/A | Aktionen für mehrere ausgewählte Anfragen durchführen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der Rücksende-Button wird in meinem Shop nicht angezeigt. Was soll ich tun?**
A1:

- **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager**, suchen Sie „EU Return Button – Online Withdrawal Form“ und stellen Sie sicher, dass es „Aktiviert“ ist.
- **Anzeigestellen überprüfen:** Überprüfen Sie in der Modulkonfiguration unter der Registerkarte „Allgemeine Einstellungen“, ob Sie mindestens einen „Rücksende-Button anzeigen in“-Ort (z. B. Header, Footer) ausgewählt haben.
- **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindert alter Cache-Inhalt, dass neue Modulelemente angezeigt werden.
- **Theme-Kompatibilität:** Obwohl das Modul für eine breite Kompatibilität ausgelegt ist, können benutzerdefinierte Themes geringfügige Anpassungen erfordern. Wenn der Button immer noch nicht angezeigt wird, kontaktieren Sie den MyPresta.eu-Support mit Details zu Ihrem Theme.

**F2: Kunden berichten, dass sie für eine bestimmte Bestellung keine Rücksendung einreichen können, obwohl sie innerhalb der Rückgabefrist liegt.**
A2:

- **Mindestbestellstatus überprüfen:** Überprüfen Sie in der Modulkonfiguration unter „Allgemeine Einstellungen“ den „Mindestbestellstatus für Widerruf“. Stellen Sie sicher, dass die Bestellung des Kunden diesen Status erreicht hat. Wenn er beispielsweise auf „Versandt“ eingestellt ist und die Bestellung noch „Zahlung akzeptiert“ ist, wird die Option nicht angezeigt.
- **Ausgeschlossene Bestellstatus überprüfen:** Überprüfen Sie in der Modulkonfiguration unter der Registerkarte „Bestellstatus“ die „Bestellstatus, die vom Widerruf ausgeschlossen werden sollen“. Wenn die Bestellung des Kunden einen dieser Status hat (z. B. „Storniert“, „Erstattet“), kann er keine neue Rücksendung initiieren.
- **Maximale Tage für Widerruf:** Überprüfen Sie die Einstellung „Maximale Tage für Widerruf“. Das Rückgabezeitfenster könnte für diese spezifische Bestellung abgelaufen sein.

**F3: Ich habe eine Einstellung geändert, aber sie wird im Front-Office nicht angezeigt.**
A3:

- **Cache leeren:** Dies ist der häufigste Grund. Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Konfigurationsänderungen in einem Modul vorgenommen haben. Navigieren Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“. Wenn Sie ein Drittanbieter-Caching-Modul oder CDN verwenden, leeren Sie auch deren Caches.
- **Browser-Cache:** Bitten Sie Ihre Kunden (oder sich selbst), ihren Browser-Cache zu leeren oder versuchen Sie, die Seite in einem Inkognito-/privaten Fenster anzuzeigen, um browserseitige Caching-Probleme auszuschließen.

**F4: Wie übersetze ich den Text des Moduls in andere Sprachen?**
A4:

- Gehen Sie in Ihrem PrestaShop-Backoffice zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“.
- Wählen Sie Ihr Theme, die Sprache, in die Sie übersetzen möchten, und dann „EU Return Button – Online Withdrawal Form“ aus der Modulliste.
- Sie sehen dann eine Liste aller übersetzbaren Zeichenfolgen innerhalb des Moduls, einschließlich Button-Text, Formularbeschriftungen und Nachrichten. Geben Sie Ihre Übersetzungen ein und speichern Sie.

**F5: Ich möchte das Aussehen des Rücksendeformulars an mein Theme anpassen.**
A5:

- Das Modul enthält CSS-Dateien (`front-classic.css`, `front-hummingbird.css`, `front.css`), die für gängige PrestaShop-Themes entwickelt wurden.
- Für fortgeschrittenes Styling benötigen Sie einen Webentwickler. Dieser kann die HTML-Struktur des Moduls untersuchen und dessen CSS-Regeln in der `custom.css`-Datei Ihres Themes überschreiben oder ein neues Stylesheet erstellen, das nach dem CSS des Moduls geladen wird. Vermeiden Sie es, die CSS-Dateien des Moduls direkt zu bearbeiten, da Ihre Änderungen bei Updates verloren gehen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „EU Return Button – Online Withdrawal Form“ (`rbpro`) folgt der Standard-MVC-Architektur (Model-View-Controller) von PrestaShop. Es nutzt `ModuleFrontController` für kundenorientierte Interaktionen und `AdminController` für die Backoffice-Verwaltung. Die Kern-Geschäftslogik ist in dedizierten Service- und ObjectModel-Klassen gekapselt, um Datenintegrität und die Trennung von Belangen zu gewährleisten. Das Modul integriert sich in das Hook-System von PrestaShop für die dynamische Inhaltseinfügung und verwendet Smarty für die Templating. Es enthält auch Kompatibilitätsschichten für verschiedene PrestaShop-Versionen und eine Sicherheitsklasse für die Eingabevalidierung.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller verwalten Kundeninteraktionen im Zusammenhang mit dem Rücksendeformular und der Statusverfolgung.

- `rbpro/controllers/front/confirm.php`

  - **Klassenname:** `RbpConfirmModuleFrontController` (erweitert `RbpModuleFrontController`)
  - **Verantwortlichkeit:** Zeigt den letzten Bestätigungsschritt des Widerrufsformulars an. Verarbeitet die übermittelten Formulardaten, erstellt den `RbpWithdrawal`-Eintrag und leitet zur Erfolgs- oder Fehlerseite weiter. Behandelt die Datenvalidierung vor dem Speichern.
- `rbpro/controllers/front/form.php`

  - **Klassenname:** `RbpFormModuleFrontController` (erweitert `RbpModuleFrontController`)
  - **Verantwortlichkeit:** Rendert das Haupt-Online-Widerrufsformular. Behandelt die anfängliche Anzeige berechtigter Bestellungen/Produkte, verarbeitet Benutzerauswahlen und bereitet Daten für den Bestätigungsschritt vor. Verwaltet den Gastzugriff über Bestellreferenz und E-Mail.
- `rbpro/controllers/front/print.php`

  - **Klassenname:** `RbpPrintModuleFrontController` (erweitert `RbpModuleFrontController`)
  - **Verantwortlichkeit:** Bietet eine druckbare Version des Widerrufsformulars oder der Anfragedetails. Wird typischerweise von Kunden verwendet, um sie ihrem zurückgesendeten Paket beizulegen.
- `rbpro/controllers/front/RbpModuleFrontController.php`

  - **Klassenname:** `RbpModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Dies ist eine Basisklasse für alle Front-Office-Controller innerhalb des `rbpro`-Moduls. Sie bietet gemeinsame Funktionalitäten wie das Einrichten von Breadcrumbs, die Handhabung modulspezifischer Assets und potenziell gemeinsame Sicherheitsprüfungen oder Dateninitialisierungen.
- `rbpro/controllers/front/status.php`

  - **Klassenname:** `RbpStatusModuleFrontController` (erweitert `RbpModuleFrontController`)
  - **Verantwortlichkeit:** Zeigt dem Kunden den aktuellen Status und die Historie einer spezifischen Rücksendeanfrage an. Zugänglich über einen eindeutigen Tracking-Link oder vom Kundenkonto aus.
- `rbpro/controllers/front/track.php`

  - **Klassenname:** `RbpTrackModuleFrontController` (erweitert `RbpModuleFrontController`)
  - **Verantwortlichkeit:** Bietet eine einfache Schnittstelle für Kunden (insbesondere Gäste), um eine Bestellreferenz und E-Mail einzugeben, um den Status ihrer Widerrufsanfrage zu verfolgen.

#### Back-Office-Admin-Controller

- `rbpro/controllers/admin/AdminRbpWithdrawalController.php`
  - **Klassenname:** `AdminRbpWithdrawalController` (erweitert `ModuleAdminController`)
  - **Registerkartenname:** „Widerrufsanfragen“ (unter „Bestellungen“)
  - **Verwaltete Entität:** `RbpWithdrawal`
  - **Verantwortlichkeit:** Verwaltet die Auflistung, Anzeige, Bearbeitung und Statusaktualisierungen aller Kunden-Widerrufsanfragen im PrestaShop-Backoffice. Implementiert `renderList()` für die Übersichtsliste und `renderForm()` für die Detailansicht einer einzelnen Anfrage. Behandelt Aktionen wie Statusänderung, Notizen hinzufügen und Anhänge verwalten.

### 4.3 Kernklassen & Modelle (`classes/`)

- `rbpro/classes/index.php`

  - **Verantwortlichkeit:** Standardmäßig leere `index.php`-Datei, um das Auflisten von Verzeichnissen zu verhindern.
- `rbpro/classes/RbpCompatibility.php`

  - **Verantwortlichkeit:** Bietet statische Methoden zur Handhabung von Kompatibilitätsproblemen über verschiedene PrestaShop-Versionen hinweg (z. B. `_PS_VERSION_`-spezifische Logik, Ersetzungen veralteter Funktionen). Stellt sicher, dass das Modul von PS 1.6 bis 9.x korrekt funktioniert.
- `rbpro/classes/RbpSecurity.php`

  - **Verantwortlichkeit:** Enthält statische Methoden für sicherheitsrelevante Aufgaben, wie Eingabevalidierung, Bereinigung und potenziell CSRF-Token-Generierung/-Verifizierung für modulspezifische Formulare.
- `rbpro/classes/RbpStatsService.php`

  - **Verantwortlichkeit:** Eine Serviceklasse, die für das Sammeln und potenzielle Verarbeiten von Statistiken im Zusammenhang mit Widerrufsanfragen zuständig ist (z. B. Anzahl der Anfragen, durchschnittliche Bearbeitungszeit).
- `rbpro/classes/RbpWithdrawal.php`

  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `rbp_withdrawal`
  - **`$definition`-Felder:** Definiert die Struktur einer Widerrufsanfrage, einschließlich Feldern wie `id_customer`, `id_order`, `id_order_state`, `reference`, `email`, `date_add`, `date_upd`, `status`, `reason`, `message` usw.
  - **Wichtige öffentliche Methoden:** Methoden für CRUD-Operationen an Widerrufsanfragen, Abrufen zugehöriger Produkte, Historie und Notizen.
- `rbpro/classes/RbpWithdrawalAttachment.php`

  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `rbp_withdrawal_attachment`
  - **`$definition`-Felder:** Definiert die Struktur für Anhänge, die mit einer Widerrufsanfrage verknüpft sind, einschließlich `id_rbp_withdrawal`, `filename`, `original_filename`, `mime_type`, `date_add`.
  - **Wichtige öffentliche Methoden:** Methoden zur Verwaltung von Anhangsdateien (Hochladen, Abrufen, Löschen).
- `rbpro/classes/RbpWithdrawalHistory.php`

  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `rbp_withdrawal_history`
  - **`$definition`-Felder:** Definiert die Historie der Statusänderungen für eine Widerrufsanfrage, einschließlich `id_rbp_withdrawal`, `id_order_state`, `id_employee`, `message`, `date_add`.
  - **Wichtige öffentliche Methoden:** Methoden zum Protokollieren und Abrufen von Statusänderungen und zugehörigen Nachrichten.
- `rbpro/classes/RbpWithdrawalNote.php`

  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `rbp_withdrawal_note`
  - **`$definition`-Felder:** Definiert interne Notizen, die von Mitarbeitern zu einer Widerrufsanfrage hinzugefügt wurden, einschließlich `id_rbp_withdrawal`, `id_employee`, `note`, `date_add`.
  - **Wichtige öffentliche Methoden:** Methoden zum Hinzufügen und Abrufen interner Notizen.
- `rbpro/classes/RbpWithdrawalProduct.php`

  - **Erweitert:** `ObjectModel`
  - **Datenbanktabelle:** `rbp_withdrawal_product`
  - **`$definition`-Felder:** Definiert die spezifischen Produkte, die in einer Widerrufsanfrage enthalten sind, mit Verknüpfung zu `id_rbp_withdrawal`, `id_order_detail`, `id_product`, `id_product_attribute`, `quantity`, `reason`.
  - **Wichtige öffentliche Methoden:** Methoden zur Verwaltung der Produktliste innerhalb einer Rücksendeanfrage.
- `rbpro/classes/RbpWithdrawalService.php`

  - **Verantwortlichkeit:** Eine Service-Layer-Klasse, die komplexe Geschäftslogik orchestriert, die mehrere `RbpWithdrawal`-bezogene ObjectModels umfasst. Beispiele hierfür sind das Erstellen einer neuen Widerrufsanfrage (die `RbpWithdrawal`, `RbpWithdrawalProduct`, `RbpWithdrawalHistory` umfasst), das Aktualisieren ihres Status, das Senden von E-Mail-Benachrichtigungen und die Handhabung von Anhängen.

### 4.4 JavaScript-Assets (`views/js/`)

- `rbpro/lib/searchTool/views/js/autocomplete.js`

  - **Geltungsbereich:** Backoffice (wahrscheinlich zum Suchen von Bestellungen/Kunden in Admin-Formularen).
  - **Details:** Implementiert die Autocomplete-Funktionalität für Eingabefelder, typischerweise zum Suchen von Kunden oder Bestellungen beim manuellen Erstellen/Bearbeiten von Widerrufsanfragen im Backoffice. Bindet an `keyup`-Ereignisse und führt AJAX-Aufrufe durch, um Vorschläge abzurufen.
- `rbpro/views/js/admin-order-state-picker.js`

  - **Geltungsbereich:** Backoffice (Modulkonfiguration und `AdminRbpWithdrawalController`).
  - **Details:** Verbessert die Dropdown-Menüs zur Auswahl des Bestellstatus in der Modulkonfiguration und potenziell in der Widerrufsdetailansicht. Kann visuelle Hinweise oder Filterfunktionen hinzufügen.
- `rbpro/views/js/front.js`

  - **Geltungsbereich:** Front-Office (Widerrufsformulare und Statusseiten).
  - **Details:** Behandelt clientseitige Interaktionen im Widerrufsformular, wie zum Beispiel:
    - Dynamische Produktauswahl basierend auf der Bestellung.
    - Validierung von Formularfeldern vor dem Absenden.
    - AJAX-Aufrufe für die Formularübermittlung oder das Laden von Daten.
    - Anzeigen von Nachrichten oder Handhabung von Dateiuploads.
- `rbpro/views/js/order-history.js`

  - **Geltungsbereich:** Front-Office (Kundenkonto > Bestellhistorie).
  - **Details:** Integriert den Button oder Link „Rücksendung anfordern“ in die Bestellhistorie des Kunden. Kann AJAX verwenden, um die Bestellberechtigung zu überprüfen oder den Button dynamisch ein-/auszublenden.

### 4.5 CSS-Stylesheets (`views/css/`)

- `rbpro/lib/searchTool/views/css/autocomplete.css`

  - **Geltungsbereich:** Backoffice.
  - **Details:** Stile für die Autocomplete-Dropdowns und Such-Eingabefelder, die im Admin-Panel verwendet werden.
- `rbpro/views/css/admin-config.css`

  - **Geltungsbereich:** Backoffice (Modulkonfigurationsseite).
  - **Details:** Stile für das Hauptkonfigurationsformular des Moduls, einschließlich Registerkarten, Eingabefelder und allgemeines Layout.
- `rbpro/views/css/admin-dashboard.css`

  - **Geltungsbereich:** Backoffice (potenziell für ein Modul-Dashboard oder eine Statistikansicht).
  - **Details:** Stile für alle benutzerdefinierten Dashboard-Elemente oder statistischen Anzeigen innerhalb der Admin-Oberfläche des Moduls.
- `rbpro/views/css/admin-order-state-picker.css`

  - **Geltungsbereich:** Backoffice.
  - **Details:** Spezifische Stile für die erweiterten Bestellstatus-Auswahlelemente im Admin.
- `rbpro/views/css/admin-searchtool.css`

  - **Geltungsbereich:** Backoffice.
  - **Details:** Allgemeine Stile für Suchwerkzeuge und Filterkomponenten innerhalb der Admin-Oberfläche.
- `rbpro/views/css/admin-withdrawal-view.css`

  - **Geltungsbereich:** Backoffice (`AdminRbpWithdrawalController` Detailansicht).
  - **Details:** Stile für die Detailansicht einer einzelnen Widerrufsanfrage, einschließlich Abschnitten für Kundeninformationen, Produkte, Historie und Notizen.
- `rbpro/views/css/front-classic.css`

  - **Geltungsbereich:** Front-Office (für Classic-Theme-Kompatibilität).
  - **Details:** Spezifische Styling-Anpassungen für das Widerrufsformular und die Buttons, um sich nahtlos in das PrestaShop Classic-Theme zu integrieren.
- `rbpro/views/css/front-hummingbird.css`

  - **Geltungsbereich:** Front-Office (für Hummingbird-Theme-Kompatibilität).
  - **Details:** Spezifische Styling-Anpassungen für das Widerrufsformular und die Buttons, um sich nahtlos in das PrestaShop Hummingbird-Theme zu integrieren.
- `rbpro/views/css/front.css`

  - **Geltungsbereich:** Front-Office (allgemeines Styling).
  - **Details:** Kern-CSS für das Front-Office-Widerrufsformular, Buttons und Statusseiten, das einen Basisstil bietet, der durch themenspezifische Stylesheets überschrieben werden kann.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

Diese Templates werden gerendert, wenn das Modul an bestimmten Anzeigepunkten eingehängt wird.

- `rbpro/views/templates/hook/account-link-classic.tpl`

  - **Hook:** `displayCustomerAccount` (oder ähnlich)
  - **Ausgabe:** Ein Link im Bereich „Mein Konto“ des Kunden für das Classic-Theme, der zum Widerrufsformular oder zur Tracking-Seite führt.
- `rbpro/views/templates/hook/account-link-hummingbird.tpl`

  - **Hook:** `displayCustomerAccount` (oder ähnlich)
  - **Ausgabe:** Ein Link im Bereich „Mein Konto“ des Kunden für das Hummingbird-Theme.
- `rbpro/views/templates/hook/button-classic.tpl`

  - **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (oder ähnlich)
  - **Ausgabe:** Der Haupt-Button „Rücksenden“ oder „Widerruf“, im Stil des Classic-Themes.
- `rbpro/views/templates/hook/button-hummingbird.tpl`

  - **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (oder ähnlich)
  - **Ausgabe:** Der Haupt-Button „Rücksenden“ oder „Widerruf“, im Stil des Hummingbird-Themes.
- `rbpro/views/templates/hook/button.tpl`

  - **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (oder ähnlich)
  - **Ausgabe:** Ein generischer Button „Rücksenden“ oder „Widerruf“, der als Fallback oder Basis für themenspezifische Buttons dient.
- `rbpro/views/templates/hook/order-detail-classic.tpl`

  - **Hook:** `displayOrderDetail` (oder ähnlich)
  - **Ausgabe:** Eine Option oder ein Button auf der individuellen Bestelldetailseite des Kunden für das Classic-Theme, der es ihm ermöglicht, eine Rücksendung für diese spezifische Bestellung zu initiieren.
- `rbpro/views/templates/hook/order-detail-hummingbird.tpl`

  - **Hook:** `displayOrderDetail` (oder ähnlich)
  - **Ausgabe:** Eine Option oder ein Button auf der individuellen Bestelldetailseite des Kunden für das Hummingbird-Theme.
- `rbpro/views/templates/hook/order-detail.tpl`

  - **Hook:** `displayOrderDetail` (oder ähnlich)
  - **Ausgabe:** Eine generische Option oder ein Button auf der individuellen Bestelldetailseite des Kunden.
- `rbpro/views/templates/hook/order-withdrawal-notice.tpl`

  - **Hook:** `displayAdminOrder` (oder ähnlich)
  - **Ausgabe:** Ein Hinweis oder eine Zusammenfassung von Widerrufsanfragen, die sich auf eine bestimmte Bestellung beziehen, angezeigt in der PrestaShop-Admin-Bestellansicht.

#### Admin-Templates (`views/templates/admin/`)

Diese Templates werden für die Backoffice-Oberfläche des Moduls verwendet.

- `rbpro/lib/searchTool/views/scripts.tpl`

  - **Ausgabe:** JavaScript- und CSS-Includes für die Suchwerkzeugbibliothek, typischerweise in Admin-Formularen enthalten, die Autocomplete verwenden.
- `rbpro/views/templates/admin/configure.tpl`

  - **Ausgabe:** Das Hauptkonfigurationsformular für das Modul, gerendert von `getContent()` in `index.php`. Enthält alle in Abschnitt 4.1 beschriebenen Einstellungen.
- `rbpro/views/templates/admin/dashboard.tpl`

  - **Ausgabe:** Ein Dashboard oder eine Übersichtsansicht für das Modul, das potenziell Statistiken oder aktuelle Widerrufsanfragen anzeigt.
- `rbpro/views/templates/admin/order-state-picker.tpl`

  - **Ausgabe:** Ein benutzerdefiniertes Template zur Auswahl von Bestellstatus, das in der Modulkonfiguration oder der Admin-Widerrufsansicht verwendet wird.
- `rbpro/views/templates/admin/order-withdrawal-notice.tpl`

  - **Ausgabe:** Ein kleines Widget oder ein Hinweis, der auf der PrestaShop-Bestelldetailseite im Backoffice angezeigt wird und angibt, ob eine aktive Widerrufsanfrage für diese Bestellung vorliegt.
- `rbpro/views/templates/admin/updates.tpl`

  - **Ausgabe:** Ein Template zur Anzeige von Modul-Update-Benachrichtigungen oder Changelogs innerhalb der Admin-Oberfläche.
- `rbpro/views/templates/admin/view.tpl`

  - **Ausgabe:** Das detaillierte Ansichtstemplate für eine einzelne Widerrufsanfrage, gerendert von `AdminRbpWithdrawalController::renderForm()`. Zeigt alle Anfragedetails, Produkte, Historie, Notizen und Statusänderungsoptionen an.

#### Front-Office-Templates (`views/templates/front/`)

Dies sind eigenständige Seitenvorlagen für den kundenorientierten Widerrufsprozess.

- `rbpro/views/templates/front/confirm_step.tpl`

  - **Ausgabe:** Der Bestätigungsschritt des Widerrufsformulars, der die Auswahl des Kunden vor der endgültigen Übermittlung zusammenfasst.
- `rbpro/views/templates/front/error.tpl`

  - **Ausgabe:** Eine generische Fehlerseite, die angezeigt wird, wenn während des Widerrufsprozesses etwas schiefgeht (z. B. ungültige Bestellung, technisches Problem).
- `rbpro/views/templates/front/form.tpl`

  - **Ausgabe:** Das Haupt-Online-Widerrufsanfrageformular, das Kunden ermöglicht, Bestellungen, Produkte auszuwählen und Details anzugeben.
- `rbpro/views/templates/front/print.tpl`

  - **Ausgabe:** Eine druckbare Version der Widerrufsanfrage, typischerweise ein vereinfachtes Layout ohne Navigation.
- `rbpro/views/templates/front/status.tpl`

  - **Ausgabe:** Die Seite, die den aktuellen Status und die Historie einer spezifischen Widerrufsanfrage anzeigt.
- `rbpro/views/templates/front/success.tpl`

  - **Ausgabe:** Eine Erfolgsmeldungsseite, die angezeigt wird, nachdem eine Widerrufsanfrage erfolgreich übermittelt wurde.
- `rbpro/views/templates/front/track.tpl`

  - **Ausgabe:** Das Formular, in dem Kunden ihre Bestellreferenz und E-Mail eingeben können, um eine Widerrufsanfrage zu verfolgen.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt und verwaltet mehrere benutzerdefinierte Tabellen:

- `ps_rbp_withdrawal`: Speichert die Hauptdetails der Widerrufsanfrage (Kunde, Bestellung, Status, Grund usw.).
- `ps_rbp_withdrawal_attachment`: Speichert Details zu Dateien, die von Kunden für eine Widerrufsanfrage hochgeladen wurden.
- `ps_rbp_withdrawal_history`: Protokolliert alle Statusänderungen und zugehörigen Nachrichten für jede Widerrufsanfrage.
- `ps_rbp_withdrawal_note`: Speichert interne Notizen, die von Mitarbeitern zu einer Widerrufsanfrage hinzugefügt wurden.
- `ps_rbp_withdrawal_product`: Verknüpft spezifische Produkte einer Bestellung mit einer Widerrufsanfrage, einschließlich Menge und Grund.

Konfigurationsdatensätze werden in `ps_configuration` mit Schlüsseln gespeichert, die typischerweise mit `RBP_` beginnen (z. B. `RBP_ALLOW_GUEST_WITHDRAWAL`, `RBP_MIN_ORDER_STATUS`).

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | CSS/JS injizieren, Rücksende-Button anzeigen (falls konfiguriert). |
| `displayFooter` | Im Footer jeder Seite. | Rücksende-Button anzeigen (falls konfiguriert). |
| `displayLeftColumn` | In der linken Spalte der Seiten. | Rücksende-Button anzeigen (falls konfiguriert). |
| `displayRightColumn` | In der rechten Spalte der Seiten. | Rücksende-Button anzeigen (falls konfiguriert). |
| `displayProductButtons` | Auf der Produktseite, in der Nähe des In-den-Warenkorb-Buttons. | Rücksende-Button anzeigen (falls konfiguriert). |
| `displayCustomerAccount` | Auf der Seite „Mein Konto“ des Kunden. | Link zum Widerrufsformular/Tracking hinzufügen. |
| `displayOrderDetail` | Auf der individuellen Bestelldetailseite des Kunden. | Option zum Anfordern einer Rücksendung für diese Bestellung hinzufügen. |
| `displayAdminOrder` | Im PrestaShop-Backoffice, auf der Bestelldetailseite. | Hinweis oder Zusammenfassung der zugehörigen Widerrufsanfragen anzeigen. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Potenziell Bestelldetails für zukünftige Widerrufsberechtigungsprüfungen protokollieren. |
| `actionOrderStatusUpdate` | Nachdem der Status einer Bestellung geändert wurde. | Überprüfen, ob der Bestellstatus die Widerrufsberechtigung beeinflusst oder Benachrichtigungen auslöst. |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seinen Inhalt rendert. | Front-Office-spezifische CSS- und JavaScript-Assets laden. |
| `actionAdminControllerSetMedia` | Bevor ein Admin-Controller seinen Inhalt rendert. | Back-Office-spezifische CSS- und JavaScript-Assets laden. |
| `actionModuleInstall` | Während der Modulinstallation. | Datenbanktabellen erstellen, Standardkonfigurationswerte festlegen. |
| `actionModuleUninstall` | Während der Moduldeinstallation. | Datenbanktabellen entfernen, Konfigurationswerte bereinigen. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und alle Fragen zum Modul „EU Return Button – Online Withdrawal Form“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team und unsere Entwickler stehen Ihnen bei allen Problemen oder Anfragen gerne zur Verfügung.

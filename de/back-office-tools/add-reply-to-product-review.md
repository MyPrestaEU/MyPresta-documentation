---
title: "Antwort auf Produktbewertung hinzufügen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Antwort auf Produktbewertung hinzufügen“ von MyPresta.eu."
sidebar:
  label: "Antwort auf Produktbewertung hinzufügen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Add reply to product review auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/add-reply-to-product-review.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/add-reply-to-product-review/)
>
> ---


# Antwort auf Produktbewertung hinzufügen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL). Dieses Modul funktioniert mit dem Standard-PrestaShop-Produktkommentar-Modul.

## 2. Vollständige Konfigurationsanleitung (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation neben dem Modul „Antwort auf Produktbewertung hinzufügen“ auf „Konfigurieren“, um auf dessen Einstellungen zuzugreifen.

#### **Modul aktivieren / deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die Funktionalität des Moduls in Ihrem gesamten Shop ein- oder auszuschalten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Ihre Antworten auf Produktbewertungen werden auf den Produktseiten sichtbar sein, und Sie können im Back Office Antworten hinzufügen.
  - *Wenn deaktiviert:* Die gesamte Modulfunktionalität wird eingestellt. Bestehende Antworten werden nicht mehr angezeigt, und Sie können keine neuen hinzufügen.
- **Empfohlener Wert:** JA
- **Händlerszenario / Beispiel:** Sie könnten es vorübergehend deaktivieren, wenn Sie Wartungsarbeiten durchführen oder wenn Sie sich entscheiden, die Funktion für einen bestimmten Zeitraum nicht mehr zu nutzen. Für den normalen Betrieb sollte es immer aktiviert sein.

#### **E-Mail-Benachrichtigung an Kunden senden, wenn eine Antwort hinzugefügt wird**

- **Was diese Einstellung bewirkt:** Dies steuert, ob der Kunde, der die ursprüngliche Bewertung hinterlassen hat, eine E-Mail-Benachrichtigung erhält, wenn Sie eine Antwort auf seinen Kommentar veröffentlichen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Eine E-Mail wird an die registrierte E-Mail-Adresse des Kunden gesendet, die ihn darüber informiert, dass seine Bewertung eine Antwort vom Shop erhalten hat. Dies ermutigt ihn, die Produktseite erneut zu besuchen und Ihre Antwort zu sehen.
  - *Wenn deaktiviert:* Es wird keine E-Mail-Benachrichtigung an den Kunden gesendet. Er sieht Ihre Antwort nur, wenn er zufällig die Produktseite erneut besucht.
- **Empfohlener Wert:** JA
- **Händlerszenario / Beispiel:** Dies zu aktivieren ist sehr empfehlenswert. Es ist eine proaktive Möglichkeit, Kunden zu binden, insbesondere wenn Sie ein Anliegen ansprechen oder sich für eine positive Bewertung bedanken. Es zeigt, dass Sie aufmerksam sind und ihr Feedback schätzen, was potenziell zu erhöhter Loyalität und Wiederholungsgeschäften führen kann. Wenn Sie es vorziehen, Kunden nicht mit E-Mails zu „belästigen“, könnten Sie es deaktivieren, verlieren aber eine wertvolle Engagement-Möglichkeit.

#### **Antworten auf Produktseite anzeigen**

- **Was diese Einstellung bewirkt:** Dies bestimmt, ob die von Ihnen im Back Office hinzugefügten Antworten den Kunden auf den Front-Office-Produktseiten tatsächlich angezeigt werden.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Ihre Antworten sind für alle Besucher auf den jeweiligen Produktseiten unter den Kundenbewertungen sichtbar.
  - *Wenn deaktiviert:* Selbst wenn Sie im Back Office Antworten geschrieben haben, werden diese im Front Office nicht angezeigt. Dies verbirgt Ihre Antworten effektiv vor Kunden, obwohl die Antworten weiterhin in Ihrem System gespeichert sind.
- **Empfohlener Wert:** JA
- **Händlerszenario / Beispiel:** Sie sollten dies fast immer aktiviert haben, da der Hauptzweck des Moduls darin besteht, Ihr Engagement anzuzeigen. Sie könnten es vorübergehend deaktivieren, wenn Sie Ihr Produktseiten-Layout überarbeiten und Antworten während des Prozesses ausblenden möchten oder wenn Sie neue Inhalte testen und diese noch nicht live schalten möchten.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren / deaktivieren | JA | Schaltet die Kernfunktionalität des Moduls ein oder aus. |
| Modulkonfiguration | E-Mail-Benachrichtigung an Kunden senden, wenn eine Antwort hinzugefügt wird | JA | Sendet eine E-Mail an den Kunden, wenn seine Bewertung eine Antwort erhält. Fördert das Engagement. |
| Modulkonfiguration | Antworten auf Produktseite anzeigen | JA | Steuert die Sichtbarkeit Ihrer Antworten auf den Front-Office-Produktseiten. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Antworten werden nicht auf der Produktseite angezeigt, obwohl ich sie im Back Office hinzugefügt habe.**
A:

1. **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass das Modul „Antwort auf Produktbewertung hinzufügen“ installiert und aktiviert ist.
2. **Modulkonfiguration überprüfen:** Gehen Sie zur Konfigurationsseite des Moduls und stellen Sie sicher, dass „Antworten auf Produktseite anzeigen“ auf JA gesetzt ist.
3. **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass neue Inhalte angezeigt werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung**, scrollen Sie nach unten zu „Cache leeren“ und klicken Sie auf „Cache leeren“.
4. **Theme-Kompatibilität:** Wenn Sie ein stark angepasstes Theme verwenden, könnte es die Standardvorlage für Produktkommentare überschreiben. Kontaktieren Sie Ihren Theme-Entwickler oder einen PrestaShop-Experten für Unterstützung.

**F: Kunden erhalten keine E-Mail-Benachrichtigungen, wenn ich auf ihre Bewertungen antworte.**
A:

1. **Modulkonfiguration überprüfen:** Stellen Sie sicher, dass „E-Mail-Benachrichtigung an Kunden senden, wenn eine Antwort hinzugefügt wird“ in der Modulkonfiguration auf JA gesetzt ist.
2. **PrestaShop E-Mail-Einstellungen überprüfen:** Vergewissern Sie sich, dass die E-Mail-Einstellungen Ihres Shops unter **Erweiterte Einstellungen > E-Mail** korrekt konfiguriert sind. Senden Sie eine Test-E-Mail von dieser Seite, um zu bestätigen, dass Ihr Mailserver funktioniert.
3. **Spam-Ordner:** Weisen Sie Kunden darauf hin, ihre Spam- oder Junk-Ordner zu überprüfen, da automatisierte E-Mails manchmal gefiltert werden können.
4. **Kunden-E-Mail-Adresse:** Stellen Sie sicher, dass die mit der Bewertung verknüpfte E-Mail-Adresse des Kunden gültig ist.

**F: Kann ich eine Antwort bearbeiten oder löschen, nachdem ich sie veröffentlicht habe?**
A: Ja, Sie sollten Antworten im PrestaShop Back Office bearbeiten oder löschen können, typischerweise im Bereich der Produktkommentarverwaltung, wo Sie die Antwort ursprünglich hinzugefügt haben. Suchen Sie nach einer Option „Bearbeiten“ oder „Löschen“ neben Ihrer Antwort.

**F: Funktioniert dieses Modul mit benutzerdefinierten Produktbewertungsmodulen?**
A: Dieses Modul ist so konzipiert, dass es mit dem *Standard*-PrestaShop-Produktkommentar-Modul funktioniert. Wenn Sie ein Produktbewertungsmodul eines Drittanbieters (z. B. von einem externen Marktplatz) verwenden, ist die Kompatibilität nicht garantiert. Möglicherweise müssen Sie sich an den MyPresta.eu-Support wenden, um Optionen für eine benutzerdefinierte Integration zu erhalten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Antwort auf Produktbewertung hinzufügen“ (`reviewsreply`) ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich die Klasse `Module` erweitert. Seine Kernfunktionalität dreht sich um die Verbesserung des bestehenden Produktkommentarsystems, indem es Shop-Administratoren ermöglicht, Antworten hinzuzufügen. Es integriert sich in die Front-Office-Anzeige über eine Hook-Vorlage und verwaltet seine Konfiguration über die Standardmethode `getContent()`. Das Modul führt keine komplexen MVC-Muster mit dedizierten Controllern oder benutzerdefinierten `ObjectModel`-Klassen ein, sondern nutzt PrestaShops Konfigurations- und Templating-System.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte administrative Konfiguration wird innerhalb der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen in einem `classes/`-Verzeichnis ein. Seine Logik ist in der Hauptdatei `reviewsreply/index.php` enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`reviewsreply/views/css/reviewsreply.css`**
  - **Umfang:** Front-Office-Kundenstyling.
  - **Haupt-UI-Komponenten und Container, die es stylt:** Dieses Stylesheet ist für die visuelle Darstellung der Shop-Antworten auf Produktkommentare auf der Produktseite verantwortlich. Es zielt wahrscheinlich auf spezifische CSS-Klassen ab, die von der Vorlage `displayProductComment.tpl` hinzugefügt wurden, um Antworten von ursprünglichen Kommentaren zu unterscheiden (z. B. Hintergrundfarbe, Rahmen, Schriftstil, Autorenbezeichnung).
  - **Wichtige CSS-Klassenselektoren, die Entwickler in ihrem Theme überschreiben können:** Entwickler können den gerenderten HTML-Code auf der Produktseite überprüfen, um die vom Modul verwendeten spezifischen Klassen (z. B. `.reviewsreply-reply-container`, `.reviewsreply-author`, `.reviewsreply-content`) zu identifizieren und sie in der `custom.css` oder `theme.css` ihres Themes zu überschreiben, um sie an das Branding ihres Shops anzupassen.

### 4.6 Smarty-Vorlagenstruktur (`views/templates/`)

- **Hook-Vorlagen (`views/templates/hook/`)**:
  - **`reviewsreply/views/templates/hook/displayProductComment.tpl`**
    - **Hook:** Diese Vorlage ist wahrscheinlich in `displayProductComment` (oder einen ähnlichen Hook, der vom Standardmodul `productcomments` bereitgestellt wird) eingehängt oder direkt in die Produktseitenvorlage eingefügt, um den Antwortbereich zu rendern.
    - **Visuelle Blockausgabe:** Diese Vorlage ist für das Rendern der tatsächlichen Antwort des Shop-Betreibers für jeden Produktkommentar verantwortlich. Sie enthält die Logik zur Anzeige des Antworttextes, möglicherweise des Autors (z. B. „Shop-Betreiber“ oder „Mein Shop“) und eines Zeitstempels. Sie enthält auch die notwendige HTML-Struktur und CSS-Klassen für das Styling, wie in `reviewsreply.css` definiert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine eigenen benutzerdefinierten SQL-Tabellen. Es speichert die Antworten wahrscheinlich direkt in der bestehenden Tabelle `ps_product_comment` oder einer verwandten Tabelle, möglicherweise durch Hinzufügen einer neuen Spalte (z. B. `reply_text`, `reply_date`, `reply_employee_id`) oder durch Verwendung eines spezifischen Feldes `id_parent` oder `type`, um Antworten mit ursprünglichen Kommentaren zu verknüpfen.
  - Konfigurationseinstellungen werden in `ps_configuration` mit Schlüsseln wie `REVIEWSREPLY_ENABLED`, `REVIEWSREPLY_SEND_EMAIL`, `REVIEWSREPLY_DISPLAY_FRONT` gespeichert.
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayProductComment` | Wird im Produktkommentarbereich auf der Produktseite ausgeführt. | Fügt die Modulvorlage (`displayProductComment.tpl`) ein, um die Antwort des Shop-Betreibers unter jeder Kundenbewertung anzuzeigen. |
  | `actionProductCommentAdd` | Wird ausgelöst, nachdem ein neuer Produktkommentar hinzugefügt wurde. | (Potenziell) Zur Vorbereitung von Antworten oder verwandten Aktionen, obwohl die Hauptfunktion des Moduls das Antworten *auf* bestehende Kommentare ist. |
  | `actionProductCommentReply` | (Hypothetisch/Intern) Wird ausgelöst, wenn eine Antwort im BO hinzugefügt/gespeichert wird. | Zum Senden von E-Mail-Benachrichtigungen an den Kunden, falls aktiviert. |
  | `displayBackOfficeHeader` | Wird im `<head>`-Abschnitt der Back Office-Seiten ausgeführt. | (Potenziell) Zum Einbinden modulspezifischer CSS oder JS für Admin-Formulare, obwohl keine im Inventar aufgeführt sind. |
  | `displayHeader` | Wird im `<head>`-Abschnitt der Front-Office-Seiten ausgeführt. | (Potenziell) Zum Einbinden modulspezifischer CSS (`reviewsreply.css`) oder JS für das Front Office. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und dedizierten technischen Support für das Modul „Antwort auf Produktbewertung hinzufügen“ verweisen wir auf Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Händlern und Entwicklern bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.

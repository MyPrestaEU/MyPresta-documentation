---
title: "Anhänge nur für eingeloggte Benutzer - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Anhänge nur für eingeloggte Benutzer“ von MyPresta.eu."
sidebar:
  label: "Anhänge nur für eingeloggte Benutzer - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Attachments for logged users only auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/attachments-for-logged-users-only.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/attachments-for-logged-users-only/)
>
> ---


# Anhänge nur für eingeloggte Benutzer

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation des Moduls klicken Sie auf „Konfigurieren“, um auf dessen Einstellungen zuzugreifen. Dies ist der Hauptbildschirm, auf dem Sie das Verhalten des Moduls steuern.

#### **Funktion aktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für das Modul. Er bestimmt, ob die Funktion zur Anhangsbeschränkung in Ihrem Shop aktiv oder inaktiv ist.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert („Aktiviert“):* Das Modul beschränkt aktiv das Herunterladen von Produktanhängen nur auf eingeloggte Kunden. Nicht eingeloggte Benutzer können keine Anhänge herunterladen.
  - *Wenn deaktiviert („Deaktiviert“):* Das Modul ist inaktiv. Produktanhänge verhalten sich wie standardmäßig in PrestaShop, d.h. jeder (eingeloggt oder Gast) kann sie herunterladen.
- **Empfohlener Wert:** „Aktiviert“, wenn Sie das Herunterladen von Anhängen einschränken möchten.
- **Händlerszenario / Beispiel:** Wenn Sie von Kunden verlangen möchten, sich anzumelden, um Handbücher herunterzuladen, stellen Sie dies auf „Aktiviert“. Wenn Sie testen oder vorübergehend zum Standardverhalten von PrestaShop zurückkehren möchten, stellen Sie es auf „Deaktiviert“.

#### **Download nur für Kunden**

- **Was diese Einstellung bewirkt:** Diese Einstellung verfeinert die „Funktion aktivieren“, indem sie Ihnen ermöglicht, festzulegen, *welche* Kunden Anhänge basierend auf ihrer Bestellhistorie herunterladen können.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Nur Kunden, die angemeldet sind UND mindestens eine Bestellung mit einem ausgewählten Status haben (siehe „Bestellstatus auswählen“ unten), können Anhänge herunterladen. Dies fügt eine zusätzliche Ebene der Exklusivität hinzu.
  - *Wenn deaktiviert:* Jeder eingeloggte Kunde (unabhängig von seiner Bestellhistorie) kann Anhänge herunterladen, vorausgesetzt, die „Funktion aktivieren“ ist aktiviert.
- **Empfohlener Wert:** „Deaktiviert“ für die meisten Fälle, um jedem eingeloggten Kunden den Download zu ermöglichen. „Aktiviert“, wenn Sie Anhänge als Vorteil für *zahlende* Kunden anbieten möchten.
- **Händlerszenario / Beispiel:** Sie verkaufen Software und möchten Updates oder Premium-Anleitungen nur Kunden zur Verfügung stellen, die die Software tatsächlich gekauft haben. Sie würden diese Einstellung aktivieren und „Zahlung akzeptiert“ in der Option „Bestellstatus auswählen“ auswählen.

#### **Bestellstatus auswählen**

- **Was diese Einstellung bewirkt:** Diese Option erscheint nur, wenn „Download nur für Kunden“ aktiviert ist. Sie ermöglicht Ihnen die Auswahl, welche Bestellstatus einen Kunden zum Herunterladen von Anhängen berechtigen. Ein Kunde muss mindestens eine Bestellung mit einem der ausgewählten Status haben, um Zugang zu erhalten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein oder mehrere Status ausgewählt sind:* Nur eingeloggte Kunden mit einer Bestellung, die einem dieser Status entspricht, können Anhänge herunterladen.
  - *Wenn keine Status ausgewählt sind (und „Download nur für Kunden“ aktiviert ist):* Diese Konfiguration könnte dazu führen, dass keine Kunden Anhänge herunterladen können, da keine qualifizierenden Bestellstatus definiert sind. Es ist entscheidend, mindestens einen Status auszuwählen, wenn Sie „Download nur für Kunden“ aktivieren.
- **Empfohlener Wert:** Wenn „Download nur für Kunden“ aktiviert ist, wählen Sie relevante Status wie „Zahlung akzeptiert“, „Geliefert“ oder „Versandt“, um Kunden, die eine Bestellung erfolgreich abgeschlossen haben, Zugang zu gewähren.
- **Händlerszenario / Beispiel:** Wenn Sie den Zugriff auf Anhänge nur Kunden gewähren möchten, deren Bestellungen erfolgreich bezahlt und bearbeitet wurden, würden Sie „Zahlung akzeptiert“ und „Geliefert“ auswählen. Dies verhindert, dass Kunden mit ausstehenden oder stornierten Bestellungen auf die Dateien zugreifen.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Funktion aktivieren | Aktiviert | Hauptschalter zum Aktivieren/Deaktivieren der Anhangsbeschränkung. |
| Modulkonfiguration | Download nur für Kunden | Deaktiviert | Wenn aktiviert, können nur eingeloggte Kunden mit bestimmten Bestellstatus herunterladen. |
| Modulkonfiguration | Bestellstatus auswählen | (Keine ausgewählt) | Wenn „Download nur für Kunden“ aktiv ist, wählen Sie Bestellstatus aus, die den Download-Zugriff gewähren. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Anhänge können immer noch von jedem heruntergeladen werden, selbst nachdem ich das Modul aktiviert habe. Was ist falsch?**
A:

1. **„Funktion aktivieren“ überprüfen:** Stellen Sie sicher, dass die Einstellung „Funktion aktivieren“ auf der Konfigurationsseite des Moduls auf „Aktiviert“ steht.
2. **Cache leeren:** PrestaShop verwendet Caching. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Dies behebt oft Anzeigeprobleme nach Änderungen an der Modulkonfiguration.
3. **Modulposition:** Stellen Sie sicher, dass das Modul korrekt eingehängt ist. Obwohl das Modul dies automatisch handhabt, können manchmal Theme-Konflikte auftreten.

**F: Ich habe „Download nur für Kunden“ aktiviert und Bestellstatus ausgewählt, aber meine eingeloggten Kunden können immer noch nicht herunterladen.**
A:

1. **Bestellstatus überprüfen:** Überprüfen Sie nochmals, ob der Kunde, der versucht herunterzuladen, tatsächlich eine Bestellung mit einem der *genauen* Status hat, die Sie unter „Bestellstatus auswählen“ ausgewählt haben.
2. **Kundenanmeldung:** Bestätigen Sie, dass der Kunde tatsächlich in seinem Konto angemeldet ist.
3. **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung).

**F: Wie übersetze ich die Nachrichten, die nicht eingeloggten Benutzern angezeigt werden?**
A: Das Modul sollte in das Übersetzungssystem von PrestaShop integriert sein.

1. Gehen Sie zu **International > Übersetzungen**.
2. Wählen Sie „Übersetzungen installierter Module“.
3. Wählen Sie Ihr Theme, Ihre Sprache und dann das Modul „Anhänge nur für eingeloggte Benutzer“.
4. Dort sollten Sie die relevanten Textzeichenfolgen zur Übersetzung finden.

**F: Funktioniert dieses Modul mit meinem benutzerdefinierten Theme?**
A: Ja, das Modul ist so konzipiert, dass es mit den Standard-PrestaShop-Anhangsmechanismen funktioniert. Es fängt hauptsächlich die Download-Anfrage ab, anstatt die visuelle Anzeige von Anhängen stark zu modifizieren. Wenn Ihr benutzerdefiniertes Theme jedoch die Art und Weise, wie Anhänge angezeigt oder verknüpft werden, vollständig überschreibt, könnten geringfügige Anpassungen erforderlich sein. Testen Sie immer gründlich nach der Installation.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Anhänge nur für eingeloggte Benutzer“ funktioniert hauptsächlich durch Überschreiben des Standard-`AttachmentController`, um Download-Anfragen abzufangen. Es nutzt das Hook-System von PrestaShop (`displayHeader`, `header`), um notwendiges JavaScript und CSS einzufügen, und seine Hauptlogik befindet sich in der Datei `atlogged.php`, die die Konfiguration und die Kernüberschreibung handhabt. Das Modul verwendet eine einfache Konfigurationsstruktur, die in `ps_configuration` gespeichert ist, und enthält Front-Office-Controller für AJAX-Interaktionen und potenzielle Fallback-Logik.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `atlogged/controllers/front/index.php`

  - **Klassenname:** `AtloggedIndexModuleFrontController` (wahrscheinlich, basierend auf der Dateibenennungskonvention)
  - **Elternklasse:** `ModuleFrontController`
  - **Verantwortlichkeit:** Dieser Controller könnte als allgemeiner Einstiegspunkt für modulspezifische Front-Office-Aktionen dienen, möglicherweise Umleitungen handhaben oder Nachrichten anzeigen, wenn ein Anhangs-Download eingeschränkt ist. Er könnte auch ein Platzhalter sein oder für spezifisches Routing verwendet werden.
- `atlogged/controllers/front/popuploader.php`

  - **Klassenname:** `AtloggedPopuploaderModuleFrontController`
  - **Elternklasse:** `ModuleFrontController`
  - **Verantwortlichkeit:** Dieser Controller verarbeitet wahrscheinlich AJAX-Anfragen im Zusammenhang mit der Anzeige einer Anmelde-/Registrierungsaufforderung oder einer spezifischen Nachricht, wenn ein Benutzer versucht, einen eingeschränkten Anhang herunterzuladen. Er könnte ein kleines Template (z. B. `atlogged-ajax.tpl`) mit dem entsprechenden Inhalt rendern.
- `atlogged/override/controllers/front/AttachmentController.php`

  - **Klassenname:** `AttachmentController` (überschreibt Kernklasse)
  - **Elternklasse:** `AttachmentControllerCore`
  - **Verantwortlichkeit:** Dies ist der kritischste Teil der Front-Office-Logik des Moduls. Er überschreibt direkt den Kern-`AttachmentController` von PrestaShop. Seine Hauptfunktion ist:
    1. Überprüfen, ob das Modul aktiviert ist (`ATLOGGED_ON`).
    2. Überprüfen, ob der aktuelle Benutzer angemeldet ist.
    3. Wenn `ATLOGGED_C_ON` (Download nur für Kunden) aktiviert ist, wird zusätzlich die Bestellhistorie des Benutzers mit den konfigurierten `atlogged_ostates` verglichen.
    4. Wenn der Benutzer die Kriterien nicht erfüllt, verhindert es den Standard-Anhangs-Download-Prozess und leitet den Benutzer stattdessen um oder löst eine modulspezifische Aktion aus (z. B. Anzeige einer Anmeldeaufforderung über AJAX).
- `atlogged/override/controllers/front/index.php`

  - **Klassenname:** `IndexController` (überschreibt Kernklasse)
  - **Elternklasse:** `IndexControllerCore`
  - **Verantwortlichkeit:** Das Überschreiben des `IndexController` ist für anhangsspezifische Logik weniger üblich. Dies könnte verwendet werden für:
    1. Globale Prüfungen oder Umleitungen im Zusammenhang mit dem Modul auf der Startseite.
    2. Sicherstellen, dass bestimmte modulspezifische Assets (JS/CSS) global geladen werden.
    3. Potenziell die Umleitung zur Anmeldeseite, wenn ein Anhangslink direkt ohne Anmeldung vom Startseitenkontext aus aufgerufen wird.

#### Back-Office-Admin-Controller

- Keine identifiziert. Die Modulkonfiguration wird direkt in der `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Keine identifiziert. Das Modul scheint keine benutzerdefinierten `ObjectModel`-Klassen zu definieren. Es arbeitet wahrscheinlich direkt mit bestehenden PrestaShop-Kernobjekten (z. B. `Customer`, `Order`, `Attachment`) und Konfigurationswerten.

### 4.4 JavaScript-Assets (`views/js/`)

- `atlogged/views/js/atlogged.js`
  - **Geltungsbereich:** Front-Office.
  - **Details:** Dieses Skript ist wahrscheinlich verantwortlich für:
    1. Abfangen von Klicks auf Anhangs-Download-Links (`<a>`-Tags mit spezifischen Klassen oder Datenattributen).
    2. Ausführen von AJAX-Aufrufen an die Front-Controller `popuploader.php` oder `index.php`, wenn ein eingeschränkter Download von einem nicht qualifizierten Benutzer versucht wird.
    3. Anzeigen von Modal-Popups oder Nachrichten (z. B. „Bitte melden Sie sich an, um herunterzuladen“) basierend auf der AJAX-Antwort.
    4. Potenzielles Umleiten von Benutzern zur Anmeldeseite, wenn die AJAX-Antwort dies vorschreibt.
    5. Sicherstellen einer reibungslosen Benutzererfahrung, wenn der Zugriff verweigert wird.

### 4.5 CSS-Stylesheets (`views/css/`)

- `atlogged/views/css/atlogged.css`
  - **Geltungsbereich:** Front-Office-Kundenstyling.
  - **Details:** Dieses Stylesheet bietet das notwendige Styling für alle vom Modul eingeführten benutzerdefinierten Elemente, wie z. B.:
    1. Styling für das Anmelde-/Registrierungsaufforderungs-Modal oder die Nachrichtenbox.
    2. Anpassungen des Erscheinungsbilds von Anhangslinks, wenn diese deaktiviert oder visuell geändert werden, wenn sie eingeschränkt sind.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Entwickler sollten die vom Modul-Template (z. B. `atlogged-ajax.tpl`) generierte HTML-Ausgabe überprüfen, um spezifische Klassen (z. B. `.atlogged-modal`, `.atlogged-message`, `.atlogged-login-button`) für die Theme-Integration und Anpassung zu identifizieren.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:

  - `atlogged/views/templates/admin/orderstates.tpl`
    - **Zweck:** Dieses Template wird innerhalb der `getContent()`-Methode des Moduls im Back Office verwendet. Es rendert die Liste der Bestellstatus (`atlogged_ostates`) für die Konfigurationsoption „Bestellstatus auswählen“, typischerweise als Mehrfachauswahl-Dropdown oder eine Liste von Kontrollkästchen.
- **Front-Office-Templates (`views/templates/front/`)**:

  - `atlogged/views/templates/front/atlogged-ajax.tpl`
    - **Zweck:** Dieses Template wird wahrscheinlich vom Front-Controller `popuploader.php` als Antwort auf eine AJAX-Anfrage gerendert. Es enthält den HTML-Inhalt für die Nachricht, die Benutzern angezeigt wird, die einen Anhang nicht herunterladen können (z. B. „Bitte melden Sie sich an, um fortzufahren“, mit Links zur Anmeldung/Registrierung).
  - `atlogged/views/templates/front/atlogged.tpl`
    - **Zweck:** Dieses Template könnte über einen Hook (z. B. `displayHeader`) oder direkt von einem Front-Controller eingebunden werden. Es könnte enthalten:
      1. Versteckte Elemente oder Datenattribute, die von `atlogged.js` verwendet werden.
      2. Anfängliche Einrichtung oder Konfigurationsvariablen für das JavaScript.
      3. Fallback-Nachrichten oder Elemente, die immer vorhanden, aber bedingt durch JS angezeigt werden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Konfigurationseinträge werden in der Tabelle `ps_configuration` gespeichert:
    - `ATLOGGED_ON`: Speichert den booleschen Wert für die Einstellung „Funktion aktivieren“.
    - `ATLOGGED_C_ON`: Speichert den booleschen Wert für die Einstellung „Download nur für Kunden“.
    - `atlogged_ostates`: Speichert ein serialisiertes Array oder eine kommagetrennte Zeichenfolge der ausgewählten Bestellstatus-IDs für die Einstellung „Bestellstatus auswählen“.
    - `mypresta_updates`, `update_`, `updatev_`: Wird für Modul-Update-Prüfungen durch MyPresta.eu verwendet.
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Ein PrestaShop-Kernkonfigurationsschlüssel, der wahrscheinlich für den Sprachkontext im Back Office abgerufen wird.
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayHeader` | Im `<head>`-Bereich jeder Front-Office-Seite. | Wird verwendet, um `atlogged.js` und `atlogged.css` in die Seite einzufügen, um sicherzustellen, dass die clientseitige Logik und das Styling des Moduls geladen werden. |
  | `header` | Alias für `displayHeader` in einigen PrestaShop-Versionen/Kontexten. | Gleicher Zweck wie `displayHeader`. |
  | `actionFrontControllerSetMedia` | Wenn ein Front-Controller seine Medien-Assets einstellt. | Könnte verwendet werden, um JS/CSS nur auf bestimmten Seiten (z. B. Produktseiten) zur Leistungsoptimierung bedingt zu laden. |
  | `actionDispatcherBefore` | Bevor ein Front-Controller versendet wird. | Potenziell von der `AttachmentController`-Überschreibung verwendet, um die Download-Anfrage sehr früh abzufangen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und dedizierten technischen Support für das Modul „Anhänge nur für eingeloggte Benutzer“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Fragen oder Problemen, die auftreten können, gerne zur Verfügung.

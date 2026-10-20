---
title: "Zusätzliche Checkboxen während der Registrierung – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Zusätzliche Checkboxen während der Registrierung“ von MyPresta.eu."
sidebar:
  label: "Zusätzliche Checkboxen während der Registrierung – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Additional checkboxes during register auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/additional-checkboxes-during-register.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/additional-checkboxes-during-register/)
>
> ---


# Zusätzliche Checkboxen während der Registrierung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten PrestaShop-kompatiblen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, der durch Klicken auf „Konfigurieren“ nach der Installation aufgerufen wird.

- **Was diese Einstellung bewirkt:** Dieser Bildschirm verwaltet hauptsächlich die allgemeinen Moduleinstellungen und ermöglicht Ihnen die Verwaltung von Updates.
- **Auswirkungen der Änderung dieser Einstellung:**
  - `mypresta_updates`: Dies ist eine allgemeine Einstellung für MyPresta.eu-Module, um nach Updates zu suchen.
    - *Wenn aktiviert:* Das Modul sucht regelmäßig auf MyPresta.eu nach neuen Versionen und benachrichtigt Sie im Back Office, wenn ein Update verfügbar ist. Dies hilft Ihnen, Ihr Modul sicher und auf dem neuesten Stand mit den neuesten Funktionen und Fehlerbehebungen zu halten.
    - *Wenn deaktiviert:* Das Modul sucht nicht automatisch nach Updates. Sie müssten manuell in Ihrem MyPresta.eu-Konto nach neuen Versionen suchen.
  - `update_`: Diese Einstellung bezieht sich auf die Update-Prüffunktion.
  - `updatev_`: Diese Einstellung bezieht sich auf die Update-Prüffunktion.
- **Empfohlener Wert:** Für `mypresta_updates` wird im Allgemeinen **empfohlen, es aktiviert zu lassen**, um sicherzustellen, dass Sie immer über die neuesten Modulversionen informiert sind. Die anderen beiden Einstellungen sind intern und sollten im Allgemeinen so belassen werden, wie sie sind.
- **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Ihr Shop immer die sicherste und funktionsreichste Version des Moduls verwendet. Die Aktivierung der Update-Prüfungen bedeutet, dass Sie direkt in Ihrem PrestaShop-Admin benachrichtigt werden, wenn eine neue Version veröffentlicht wird, was es einfach macht, auf dem neuesten Stand zu bleiben.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### AdminAddTosListController (Back Office > Module > Zusätzliche Checkboxen > Checkboxen-Liste)

Auf diesem Bildschirm definieren und verwalten Sie alle einzelnen Checkboxen, die während der Kundenregistrierung angezeigt werden.

- **Bildschirmname & Menüpfad:** Sie finden diesen Bildschirm, indem Sie im PrestaShop Back Office-Menü zu **Module > Zusätzliche Checkboxen > Checkboxen-Liste** navigieren.
- **Verfügbare Aktionen & Einstellungen:**
  - **Liste der Checkboxen:** Diese Seite zeigt eine Tabelle aller von Ihnen erstellten benutzerdefinierten Checkboxen. Jede Zeile zeigt den Namen der Checkbox, ob sie erforderlich ist, ihren Status (aktiviert/deaktiviert) und ihre Position.
  - **Neue Checkbox hinzufügen:** Es gibt eine Schaltfläche (z. B. „Neue Checkbox hinzufügen“ oder ein Plus-Symbol), um eine brandneue Checkbox zu erstellen. Beim Hinzufügen/Bearbeiten einer Checkbox konfigurieren Sie typischerweise:
    - **Name/Beschriftung:** Der Text, der neben der Checkbox erscheint (z. B. „Ich stimme der Datenschutzerklärung zu“). Dieser sollte klar und prägnant sein.
    - **Link (Optional):** Eine URL zu einer Seite (z. B. Ihrer Datenschutzerklärung, einer spezifischen Geschäftsbedingungen-Seite), die Kunden anklicken können, um die vollständigen Details zu lesen. Dies ist entscheidend für die Transparenz.
    - **Erforderlich:** Ein Umschalter (Ja/Nein), um festzulegen, ob der Kunde dieses Kästchen ankreuzen *muss*, um die Registrierung abzuschließen.
      - *Wenn aktiviert (Ja):* Kunden können sich nicht registrieren, ohne dieses Kästchen anzukreuzen. Dies ist ideal für wesentliche rechtliche Vereinbarungen.
      - *Wenn deaktiviert (Nein):* Kunden können sich auch dann registrieren, wenn sie dieses Kästchen nicht ankreuzen. Dies ist geeignet für optionale Zustimmungen wie Newsletter-Abonnements.
    - **Aktiv:** Ein Umschalter (Ja/Nein), um die Anzeige der Checkbox im Front Office zu aktivieren oder zu deaktivieren.
      - *Wenn aktiviert (Ja):* Die Checkbox ist auf dem Registrierungsformular sichtbar.
      - *Wenn deaktiviert (Nein):* Die Checkbox wird auf dem Registrierungsformular ausgeblendet, bleibt aber im Back Office für die zukünftige Verwendung erhalten.
    - **Position:** Eine Ganzzahl zur Steuerung der Reihenfolge, in der die Checkboxen auf dem Registrierungsformular erscheinen. Kleinere Zahlen erscheinen weiter oben.
  - **Bearbeiten/Löschen:** Jede Checkbox in der Liste hat Aktionen zum Bearbeiten ihrer Details oder zum vollständigen Löschen.
- **Auswirkungen von Änderungen:**
  - **Hinzufügen einer neuen Checkbox:** Die neue Checkbox erscheint sofort auf Ihrem Kundenregistrierungsformular (wenn aktiv) und auf der Seite „Meine persönlichen Informationen“ des Kunden.
  - **Bearbeiten einer Checkbox:** Änderungen an der Beschriftung, dem Link, dem erforderlichen Status oder dem aktiven Status werden sofort im Front Office widergespiegelt.
  - **Löschen einer Checkbox:** Die Checkbox wird aus dem Front Office entfernt. Bestehende Kundenzustimmungen für diese spezifische Checkbox bleiben in der Historie erhalten, aber es können keine neuen Zustimmungen gegeben werden.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Zustimmungsbedürfnisse identifizieren:** Bestimmen Sie vor dem Hinzufügen, welche spezifischen Zustimmungen Sie benötigen (z. B. Datenschutzerklärung, Newsletter, Altersverifikation, spezifische Servicebedingungen).
  2. **Inhaltsseiten erstellen:** Stellen Sie sicher, dass Sie dedizierte CMS-Seiten (oder externe Links) für jede Richtlinie oder Bedingung haben, auf die Sie verlinken möchten.
  3. **Checkboxen hinzufügen:** Gehen Sie zu „Checkboxen-Liste“ und klicken Sie auf „Neue Checkbox hinzufügen“. Füllen Sie die Beschriftung und den Link aus, legen Sie fest, ob sie erforderlich/optional ist, und aktivieren Sie sie.
  4. **Checkboxen anordnen:** Verwenden Sie das Feld „Position“, um sie logisch anzuordnen.
  5. **Front Office überprüfen:** Testen Sie immer den Registrierungsprozess im Front Office Ihres Shops, nachdem Sie Änderungen vorgenommen haben, um sicherzustellen, dass alles wie erwartet angezeigt wird und funktioniert.

#### AdminAddTosHistoryController (Back Office > Module > Zusätzliche Checkboxen > Historie)

Dieser Bildschirm bietet eine historische Aufzeichnung der Kundenzustimmungen für jede Checkbox.

- **Bildschirmname & Menüpfad:** Sie finden diesen Bildschirm, indem Sie im PrestaShop Back Office-Menü zu **Module > Zusätzliche Checkboxen > Historie** navigieren.
- **Verfügbare Aktionen & Einstellungen:**
  - **Zustimmungshistorie-Tabelle:** Diese Seite zeigt ein detailliertes Protokoll darüber an, wann jeder Kunde einer bestimmten Checkbox zugestimmt (oder widersprochen) hat.
  - **Spalten umfassen typischerweise:**
    - **Kundenname:** Der Name des Kunden.
    - **Checkbox-Name:** Die Beschriftung der Checkbox, mit der interagiert wurde.
    - **Zustimmungsstatus:** Ob das Kästchen akzeptiert (angekreuzt) oder abgelehnt (nicht angekreuzt) wurde.
    - **Datum:** Der Zeitstempel, wann die Zustimmung aufgezeichnet wurde.
    - **IP-Adresse:** Die IP-Adresse, von der aus die Zustimmung erteilt wurde (wichtig für die Einhaltung gesetzlicher Vorschriften).
  - **Filtern/Suchen:** Sie können diese Liste normalerweise nach Kunde, Checkbox oder Datumsbereich filtern, um spezifische Zustimmungsdatensätze zu finden.
- **Auswirkungen von Änderungen:** Dieser Bildschirm dient hauptsächlich der Anzeige und Prüfung. Sie können Zustimmungsdatensätze hier nicht direkt ändern, da sie historische Fakten darstellen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  - **Prüfung & Compliance:** Verwenden Sie diesen Bildschirm, um Kundenzustimmungen bei Streitigkeiten oder für interne Compliance-Audits zu überprüfen.
  - **Datenschutzanfragen:** Wenn ein Kunde wissen möchte, welche Daten Sie speichern oder welchen er zugestimmt hat, bietet diese Historie eine klare Aufzeichnung.

#### index.php (addtos/controllers/admin/index.php)

Diese Datei ist ein Platzhalter und enthält typischerweise eine einfache `header('Location: ../../../index.php?controller=AdminHome');` oder eine ähnliche Weiterleitung, um den direkten Zugriff auf das Verzeichnis zu verhindern. Sie stellt keinen konfigurierbaren Bildschirm für den Händler dar.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | MyPresta.eu Updates prüfen | Aktiviert | Benachrichtigt Sie über neue Modulversionen für Sicherheit und Funktionen. |
| **Checkboxen-Liste** | Checkbox Name/Beschriftung | N/A (Benutzerdefiniert) | Der sichtbare Text neben der Checkbox auf dem Registrierungsformular. |
| **Checkboxen-Liste** | Link (URL) | N/A (Benutzerdefiniert) | URL zu einer Richtlinienseite; bietet Details zur Checkbox. |
| **Checkboxen-Liste** | Erforderlich | Nein (Optional) | Wenn Ja, *muss* der Kunde das Kästchen ankreuzen, um sich zu registrieren. Wenn Nein, ist es optional. |
| **Checkboxen-Liste** | Aktiv | Ja | Wenn Ja, ist die Checkbox im Front Office sichtbar. Wenn Nein, ist sie ausgeblendet. |
| **Checkboxen-Liste** | Position | N/A (Benutzerdefiniert) | Bestimmt die Anzeigereihenfolge der Checkboxen auf dem Formular. |
| **Historie** | Kundenname | N/A (Nur Ansicht) | Zeigt an, welcher Kunde die Zustimmung erteilt hat. |
| **Historie** | Checkbox Name | N/A (Nur Ansicht) | Zeigt an, mit welcher Checkbox interagiert wurde. |
| **Historie** | Zustimmungsstatus | N/A (Nur Ansicht) | Zeigt an, ob der Kunde akzeptiert oder abgelehnt hat. |
| **Historie** | Datum | N/A (Nur Ansicht) | Zeitstempel der Zustimmungsaufzeichnung. |
| **Historie** | IP-Adresse | N/A (Nur Ansicht) | IP-Adresse, von der die Zustimmung erteilt wurde. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe eine neue Checkbox hinzugefügt, aber sie wird auf der Registrierungsseite nicht angezeigt.**
**A1:**

- **„Aktiv“-Status überprüfen:** Gehen Sie zu **Module > Zusätzliche Checkboxen > Checkboxen-Liste** und stellen Sie sicher, dass der Schalter „Aktiv“ für Ihre Checkbox auf „Ja“ steht.
- **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass neue Inhalte sofort angezeigt werden. Gehen Sie zu **Erweiterte Einstellungen > Performance**, scrollen Sie nach unten zu „Cache leeren“ und klicken Sie auf „Cache leeren“.
- **Modulposition:** Stellen Sie sicher, dass das Modul korrekt eingehängt ist. Obwohl das Modul dies normalerweise automatisch handhabt, kann es sich lohnen, die Hooks des Moduls unter **Design > Positionen** (oder **Module > Positionen** in älteren Versionen) zu überprüfen, wenn Sie Theme-Änderungen vorgenommen haben. Das Modul verwendet typischerweise `displayAdditionalCustomerFormFields` oder ähnliche Hooks.

**F2: Mein Checkbox-Text ist zu lang und sieht auf Mobilgeräten schlecht aus.**
**A2:**

- **Halten Sie es prägnant:** Versuchen Sie, die Beschriftung der Checkbox auf das Wesentliche zu kürzen (z. B. „Datenschutzerklärung zustimmen“ statt „Ich habe die Allgemeinen Geschäftsbedingungen der Datenschutzerklärung dieser Website gelesen und stimme ihnen zu“).
- **Links verwenden:** Legen Sie die detaillierten Informationen auf eine separate CMS-Seite und verlinken Sie von der Checkbox-Beschriftung darauf. Dies hält das Formular sauber und bietet gleichzeitig volle Transparenz.
- **Theme-Anpassung:** Wenn das Problem weiterhin besteht, könnte das CSS Ihres Themes die Anzeige einschränken. Ein Webmaster kann das CSS für die Klasse `.addtos-checkbox` oder ähnliche Klassen anpassen, um die Responsivität zu verbessern.

**F3: Kann ich die Checkbox-Beschriftungen in verschiedene Sprachen übersetzen?**
**A3:** Ja! Wenn Sie eine Checkbox unter **Module > Zusätzliche Checkboxen > Checkboxen-Liste** bearbeiten, sollten Sie neben dem Feld „Name/Beschriftung“ einen Sprachwähler (oft ein Flaggen-Symbol) sehen. Klicken Sie auf die Flagge, um zu einer anderen Sprache zu wechseln und geben Sie den übersetzten Text für diese Sprache ein. Denken Sie daran, Ihre Änderungen für jede Sprache zu speichern.

**F4: Was passiert, wenn ich eine Checkbox lösche? Wird dadurch die Zustimmungshistorie des Kunden gelöscht?**
**A4:** Nein, das Löschen einer Checkbox aus der „Checkboxen-Liste“ entfernt sie aus dem Front-Office-Registrierungsformular, aber es **löscht nicht die historischen Zustimmungsdatensätze**, die Kunden zuvor für diese Checkbox gegeben haben. Diese Datensätze bleiben im Abschnitt „Historie“ für Prüfungs- und Compliance-Zwecke erhalten. Neue Kunden sehen diese Checkbox einfach nicht mehr.

**F5: Ich möchte die Reihenfolge der Checkboxen auf der Registrierungsseite ändern.**
**A5:** Gehen Sie zu **Module > Zusätzliche Checkboxen > Checkboxen-Liste**. In der Tabelle sollten Sie eine Spalte „Position“ sehen. Sie können die Zeilen normalerweise per Drag & Drop neu anordnen, oder es gibt möglicherweise Auf-/Ab-Pfeile oder ein bearbeitbares Zahlenfeld, um die Position zu ändern. Denken Sie daran, Ihre Änderungen bei Bedarf zu speichern.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Zusätzliche Checkboxen während der Registrierung“ folgt einem standardmäßigen PrestaShop MVC (Model-View-Controller)-Muster, das hauptsächlich `Module` für seine Kernfunktionalität und `AdminController` für die Back Office-Verwaltung erweitert. Es nutzt das Hook-System von PrestaShop, um benutzerdefinierte Felder in die Kundenregistrierungs- und Identitätsformulare einzufügen und Zustimmungsdaten aufzuzeichnen. Das Modul führt benutzerdefinierte Datenbanktabellen ein, um Checkbox-Definitionen und die Kunden-Zustimmungshistorie zu speichern.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Dieses Modul verwendet keine dedizierten Front-Controller. Alle Front-Office-Interaktionen (Anzeige von Checkboxen, Verarbeitung von Zustimmungen) werden direkt über die PrestaShop-Kernkunden-Controller durch Nutzung spezifischer Hooks abgewickelt.
- **Back-Office-Admin-Controller**:

  - `addtos/controllers/admin/AdminAddTosHistory.php`
    - **Klassenname & Elternklasse**: `AdminAddTosHistoryController` erweitert `ModuleAdminController`.
    - **Tab-Name und verwaltete Entität**: Verwaltet die historischen Aufzeichnungen der Kundenzustimmungen. Es ist über den Tab „Historie“ im Hauptmenü des Moduls zugänglich. Dieser Controller zeigt eine `list`-Ansicht der `TosHistory`-Objekte an, die Kunde, Checkbox, Zustimmungsstatus, Datum und IP anzeigen. Er erlaubt keine Bearbeitung oder Hinzufügung von Datensätzen, da es sich um ein historisches Protokoll handelt.
  - `addtos/controllers/admin/AdminAddTosList.php`
    - **Klassenname & Elternklasse**: `AdminAddTosListController` erweitert `ModuleAdminController`.
    - **Tab-Name und verwaltete Entität**: Verwaltet die Definition der benutzerdefinierten Checkboxen. Es ist über den Tab „Checkboxen-Liste“ zugänglich. Dieser Controller bietet `list`-, `add`- und `edit`-Ansichten für `Tos`-Objekte, die es Administratoren ermöglichen, die Checkbox-Beschriftung, den Link, den erforderlichen Status, den aktiven Status und die Position zu definieren.
  - `addtos/controllers/admin/index.php`
    - Dies ist eine Standard-Platzhalterdatei, um das Auflisten von Verzeichnissen zu verhindern. Sie enthält typischerweise `header('Location: ../../../index.php?controller=AdminHome');` oder Ähnliches. Sie hat keine funktionale Rolle in der Modullogik.

### 4.3 Kernklassen & Modelle (`classes/`)

Die Kernklassen des Moduls sind wahrscheinlich innerhalb der Hauptdatei `addtos.php` oder direkt im Verzeichnis `classes/` definiert (obwohl das Inventar darauf hindeutet, dass sie sich in der Hauptdatei befinden könnten).

- `Tos` (Wahrscheinlich definiert in `addtos.php` oder `classes/Tos.php`):

  - **Datenbanktabelle**: `ps_addtos_tos` (oder ähnlich, basierend auf dem Entitätsnamen `tos`).
  - **Erweitert `ObjectModel`**: Ja.
  - **`$definition`-Felder**:
    - `id_tos`: Primärschlüssel.
    - `name`: `HTML`-Feld, `isLang` (mehrsprachig) – die Checkbox-Beschriftung.
    - `link`: `HTML`-Feld, `isLang` (mehrsprachig) – die URL für weitere Informationen.
    - `required`: `BOOL` – ob die Checkbox obligatorisch ist.
    - `active`: `BOOL` – ob die Checkbox aktuell angezeigt wird.
    - `position`: `INT` – Anzeigereihenfolge.
  - **Wichtige öffentliche Methoden**: Standard `ObjectModel`-Methoden für CRUD-Operationen.
- `TosHistory` (Wahrscheinlich definiert in `addtos.php` oder `classes/TosHistory.php`):

  - **Datenbanktabelle**: `ps_addtos_toshistory` (oder ähnlich, basierend auf dem Entitätsnamen `toshistory`).
  - **Erweitert `ObjectModel`**: Ja.
  - **`$definition`-Felder**:
    - `id_toshistory`: Primärschlüssel.
    - `id_customer`: `INT` – ID des Kunden, der die Zustimmung erteilt hat.
    - `id_tos`: `INT` – ID der Checkbox.
    - `accepted`: `BOOL` – `1` wenn akzeptiert, `0` wenn abgelehnt (oder `NULL` wenn optional und nicht angekreuzt).
    - `date_add`: `DATE` – Zeitstempel der Zustimmung.
    - `ip_address`: `STRING` – IP-Adresse des Kunden zum Zeitpunkt der Zustimmung.
  - **Wichtige öffentliche Methoden**: Hauptsächlich für `add`- und `read`-Operationen, da Historienaufzeichnungen unveränderlich sind.

### 4.4 JavaScript-Assets (`views/js/`)

Das Inventar zeigt an, dass keine spezifischen JavaScript-Dateien vorhanden sind. Dies deutet darauf hin, dass clientseitige Validierungen oder dynamisches Verhalten für die Checkboxen entweder durch das Kern-JS von PrestaShop, das JS des Themes oder nicht als primäre Funktion dieses Moduls (basierend auf serverseitiger Validierung) gehandhabt werden.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Inventar zeigt an, dass keine spezifischen CSS-Dateien vorhanden sind. Dies impliziert, dass das Modul sich auf das Standard-PrestaShop-Styling für Formularelemente oder das CSS des aktiven Themes verlässt, um die Checkboxen zu gestalten. Entwickler, die das Erscheinungsbild anpassen möchten, würden Standard-Formular-Input-Selektoren oder potenziell vom Modul in seinen Templates hinzugefügte Klassen ansprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - `addtos/views/templates/hook/addtos_bo.tpl`: Dieses Template wird wahrscheinlich im Back Office verwendet, möglicherweise zur Anzeige eines Modulblocks oder von Informationen innerhalb einer Admin-Seite oder zum Rendern von Inhalten auf der Konfigurationsseite des Moduls (z. B. Update-Benachrichtigungen).
- **Admin-Templates (`views/templates/admin/`)**: Es sind keine dedizierten Admin-Templates aufgeführt, was darauf hindeutet, dass `AdminAddTosListController` und `AdminAddTosHistoryController` sich auf die Standard-`list.tpl`- und `form.tpl`-Templates von PrestaShop verlassen, um ihre Ansichten zu rendern.
- **Front-Office-Templates (`views/templates/front/`)**:
  - `addtos/views/templates/front/identity.tpl`: Dieses Template ist wahrscheinlich in die Seite „Meine persönlichen Informationen“ (Identität) des Kunden eingehängt. Es würde die Liste der Checkboxen und den aktuellen Zustimmungsstatus des Kunden anzeigen und ihm möglicherweise erlauben, seine Präferenzen nach der Registrierung zu aktualisieren.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_addtos_tos`: Speichert die Definitionen jeder benutzerdefinierten Checkbox (Beschriftung, Link, erforderlicher Status, aktiver Status, Position).
  - `ps_addtos_tos_lang`: Speichert den mehrsprachigen Inhalt für die Felder `name` und `link` der Tabelle `ps_addtos_tos`.
  - `ps_addtos_toshistory`: Speichert die historischen Aufzeichnungen der Kundenzustimmungen (Kunden-ID, Checkbox-ID, akzeptierter Status, Zeitstempel, IP-Adresse).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionValidateOrder` | Nach der Validierung einer Bestellung. | Potenziell zur Aufzeichnung von Zustimmungen im Zusammenhang mit bestellspezifischen Bedingungen verwendet, obwohl dies für Registrierungs-Checkboxen weniger üblich ist. |
| `validateCustomerFormFields` | Während der Validierung der Kundenregistrierungsformular-Einreichung. | Entscheidend für die serverseitige Validierung erforderlicher Checkboxen. Wenn eine erforderliche Checkbox nicht angekreuzt ist, würde dieser Hook die Registrierung verhindern. |
| `displayAdditionalCustomerFormFields` | Rendert zusätzliche Felder auf dem Kundenregistrierungsformular. | Primärer Hook zur Anzeige der benutzerdefinierten Checkboxen auf der Front-Office-Registrierungsseite. |
| `displaytermsAndConditions` | Rendert Inhalte für Allgemeine Geschäftsbedingungen. | Könnte verwendet werden, um Checkboxen in der Nähe der Standard-AGB oder als Alternative anzuzeigen. |
| `displayvalidateCustomerFormFields` | Rendert Validierungsmeldungen für Kundenformularfelder. | Wird verwendet, um Fehlermeldungen anzuzeigen, wenn eine erforderliche Checkbox nicht angekreuzt ist. |
| `additionalCustomerFormFields` | Ähnlich wie `displayAdditionalCustomerFormFields`, potenziell für verschiedene Kontexte oder Versionen. | Ein weiterer Hook zum Einfügen benutzerdefinierter Felder in Kundenformulare. |
| `termsAndConditions` | Ähnlich wie `displaytermsAndConditions`. | Ein weiterer Hook zum Einfügen von Allgemeinen Geschäftsbedingungen. |
| `actionCustomerAccountAdd` | Nach erfolgreicher Erstellung eines neuen Kundenkontos. | Wird verwendet, um die Zustimmung des Kunden für alle aktiven Checkboxen in der Tabelle `ps_addtos_toshistory` aufzuzeichnen. |
| `displayAdminCustomers` | Rendert Inhalte auf der Admin-Kundenliste/-bearbeitungsseite. | Könnte verwendet werden, um eine Zusammenfassung der Kundenzustimmungen direkt im Back Office-Profil anzuzeigen. |
| `displayCustomerAccountForm` | Rendert Inhalte auf der Seite „Meine persönlichen Informationen“ (Identität) des Kunden. | Wird verwendet, um die Checkboxen anzuzeigen und Kunden zu ermöglichen, ihre Zustimmungseinstellungen nach der Registrierung anzuzeigen/zu aktualisieren. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Zusätzliche Checkboxen während der Registrierung“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Konfiguration des Moduls zur Verfügung.

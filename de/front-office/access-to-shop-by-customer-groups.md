---
title: "Zugang zum Shop nach Kundengruppen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Zugang zum Shop nach Kundengruppen“ von MyPresta.eu."
sidebar:
  label: "Zugang zum Shop nach Kundengruppen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Access to shop by customer groups auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/access-to-shop-by-customer-groups.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/access-to-shop-by-customer-groups/)
>
> ---


# Zugang zum Shop nach Kundengruppen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und in jeder modernen Hosting-Umgebung verfügbar.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation neben dem Modulnamen auf „Konfigurieren“, um auf dessen Einstellungen zuzugreifen.

#### **Kundengruppen ohne Zugang zum Shop**

Dies ist die wichtigste Einstellung. Sie bestimmt, welche Kundengruppen daran gehindert werden, Ihren Shop anzuzeigen.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt zeigt eine Liste aller in Ihrem PrestaShop-Shop definierten Kundengruppen an. Sie können eine oder mehrere Gruppen aus dieser Liste auswählen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn eine oder mehrere Gruppen ausgewählt sind:* Jeder Kunde, der zu *einer* der ausgewählten Gruppen gehört, wird daran gehindert, auf das Front Office des Shops zuzugreifen. Stattdessen wird ihm der unten definierte benutzerdefinierte Inhalt angezeigt.
  - *Wenn keine Gruppen ausgewählt sind:* Das Modul blockiert keine Kunden aufgrund ihrer Gruppenzugehörigkeit. Alle Kunden haben Zugang zum Shop (es sei denn, Sie aktivieren die Option „Zugang für nicht angemeldete Kunden blockieren“).
- **Empfohlener Wert:** Wählen Sie die spezifischen Gruppen aus, die Sie einschränken möchten. Wenn Sie beispielsweise eine Gruppe „Großhandel – Genehmigung ausstehend“ haben, könnten Sie diese hier auswählen.
- **Händlerszenario / Beispiel:** Sie haben eine neue Kundengruppe namens „Neue Registrierungen – Überprüfung ausstehend“ erstellt. Sie wählen diese Gruppe hier aus. Nun wird jeder neue Kunde, der sich registriert, automatisch dieser Gruppe zugeordnet und kann Ihren Shop erst durchsuchen, wenn Sie ihn manuell in eine Gruppe „Genehmigte Kunden“ verschieben.

#### **Zugang für nicht angemeldete Kunden blockieren**

Diese Einstellung steuert den Zugang für Besucher, die nicht in Ihrem Shop angemeldet sind.

- **Was diese Einstellung bewirkt:** Dies ist ein einfacher EIN/AUS-Schalter.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Alle Besucher, die nicht in einem Kundenkonto angemeldet sind, werden daran gehindert, auf den Shop zuzugreifen. Sie sehen die Seite mit dem benutzerdefinierten Inhalt. Sobald sie sich anmelden (und wenn sie zu einer erlaubten Gruppe gehören), erhalten sie Zugang.
  - *Wenn deaktiviert (NEIN):* Nicht angemeldete Besucher haben Zugang zum Shop, es sei denn, sie werden explizit durch die Zugehörigkeit zu einer „Kundengruppen ohne Zugang zum Shop“ blockiert.
- **Empfohlener Wert:**
  - **JA:** Wenn Sie möchten, dass Ihr gesamter Shop privat ist und alle Besucher sich zuerst anmelden müssen (z.B. ein B2B-Shop, ein Club nur für Mitglieder).
  - **NEIN:** Wenn Sie möchten, dass Ihr Shop öffentlich sichtbar ist, aber nur bestimmte Kundengruppen einschränken.
- **Händlerszenario / Beispiel:** Sie betreiben einen reinen Großhandels-Shop. Sie aktivieren diese Einstellung. Nun muss sich jeder, der Ihre Website besucht, zuerst anmelden, um Ihre Produkte und Preise zu sehen.

#### **Anmeldeformular auf blockierter Seite anzeigen**

Diese Einstellung bestimmt, ob ein Anmeldeformular auf der Seite angezeigt wird, die blockierten Kunden gezeigt wird.

- **Was diese Einstellung bewirkt:** Dies ist ein einfacher EIN/AUS-Schalter.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Ein Standard-PrestaShop-Anmeldeformular wird auf der Seite mit dem benutzerdefinierten Inhalt angezeigt, sodass blockierte Kunden versuchen können, sich anzumelden.
  - *Wenn deaktiviert (NEIN):* Es wird kein Anmeldeformular angezeigt. Kunden sehen nur Ihre benutzerdefinierte Nachricht.
- **Empfohlener Wert:**
  - **JA:** Wenn Sie erwarten, dass blockierte Kunden bestehende Kunden sind, die sich einfach anmelden müssen, um Zugang zu erhalten. Dies verbessert die Benutzererfahrung.
  - **NEIN:** Wenn Sie Kunden zwingen möchten, sich zuerst zu registrieren, oder wenn die Zugangsbeschränkung für bestimmte Gruppen dauerhaft ist.
- **Händlerszenario / Beispiel:** Sie haben den Zugang für nicht angemeldete Benutzer blockiert. Durch die Aktivierung dieser Option können sich Kunden direkt von der eingeschränkten Seite aus anmelden, ohne zu einer separaten Anmeldeseite navigieren zu müssen.

#### **Registrierung auf blockierter Seite erlauben**

Diese Einstellung bestimmt, ob ein Registrierungslink auf der Seite angezeigt wird, die blockierten Kunden gezeigt wird.

- **Was diese Einstellung bewirkt:** Dies ist ein einfacher EIN/AUS-Schalter.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Ein Link zur Kundenregistrierungsseite wird auf der Seite mit dem benutzerdefinierten Inhalt angezeigt.
  - *Wenn deaktiviert (NEIN):* Es wird kein Registrierungslink angezeigt.
- **Empfohlener Wert:**
  - **JA:** Wenn Sie neuen Kunden erlauben möchten, sich von der eingeschränkten Seite aus zu registrieren.
  - **NEIN:** Wenn Sie die Registrierung separat steuern möchten oder wenn Ihr Shop ausschließlich für vorab genehmigte Kunden bestimmt ist.
- **Händlerszenario / Beispiel:** Sie betreiben einen B2B-Shop, der eine Registrierung erfordert. Sie aktivieren diese Einstellung, damit potenzielle neue Kunden direkt von der zugangsbeschränkten Seite aus ein Konto erstellen können.

#### **Benutzerdefinierte Inhalte anzeigen**

Hier definieren Sie die Nachricht und den Inhalt, die blockierten Kunden angezeigt werden.

- **Was diese Einstellung bewirkt:** Dies ist ein Rich-Text-Editor (WYSIWYG), in dem Sie Text, Bilder, HTML und sogar Videos eingeben können. Er unterstützt mehrsprachige Inhalte, sodass Sie verschiedene Nachrichten für verschiedene in Ihrem Shop installierte Sprachen bereitstellen können.
- **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Inhalt wird jedem Kunden angezeigt, der vom Zugriff auf Ihren Shop blockiert ist.
- **Empfohlener Wert:** Geben Sie eine klare, höfliche und informative Nachricht an.
- **Händlerszenario / Beispiel:**
  - *Für einen B2B-Shop:* „Willkommen in unserem Großhandelsportal! Bitte melden Sie sich mit Ihren Zugangsdaten an oder registrieren Sie sich für ein neues Konto, um unseren Produktkatalog anzuzeigen.“
  - *Für eine temporäre Einschränkung:* „Unser Shop wird derzeit gewartet. Wir sind bald wieder online! Vielen Dank für Ihre Geduld.“
  - *Für exklusiven Zugang:* „Dieser Bereich unseres Shops ist VIP-Mitgliedern vorbehalten. Bitte melden Sie sich an oder kontaktieren Sie den Support für den Zugang.“

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | **Kundengruppen ohne Zugang zum Shop** | Keine ausgewählt | Wählen Sie Gruppen aus, die vom Anzeigen des Shops blockiert werden sollen. Kunden in diesen Gruppen sehen benutzerdefinierte Inhalte. |
| Modulkonfiguration | **Zugang für nicht angemeldete Kunden blockieren** | NEIN | JA: Alle nicht angemeldeten Besucher werden blockiert. NEIN: Nicht angemeldete Besucher haben Zugang (es sei denn, sie sind in einer blockierten Gruppe). |
| Modulkonfiguration | **Anmeldeformular auf blockierter Seite anzeigen** | JA | JA: Zeigt ein Anmeldeformular auf der eingeschränkten Seite an. NEIN: Es wird kein Anmeldeformular angezeigt. |
| Modulkonfiguration | **Registrierung auf blockierter Seite erlauben** | JA | JA: Zeigt einen Registrierungslink auf der eingeschränkten Seite an. NEIN: Es wird kein Registrierungslink angezeigt. |
| Modulkonfiguration | **Benutzerdefinierte Inhalte anzeigen** | Leer | Definiert die Nachricht/den HTML-Inhalt, der blockierten Kunden angezeigt wird. Unterstützt Mehrsprachigkeit. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Mein Shop ist komplett blockiert, sogar für mich! Was soll ich tun?**
A1: Dies geschieht normalerweise, wenn Sie „Zugang für nicht angemeldete Kunden blockieren“ aktiviert haben und nicht angemeldet sind, oder wenn Ihr Admin-Konto irgendwie mit einer blockierten Kundengruppe verknüpft ist.
\* **Lösung 1 (Empfohlen):** Melden Sie sich in Ihrem PrestaShop Back Office an. Das Modul blockiert nur das Front Office. Sobald Sie im BO angemeldet sind, navigieren Sie zu Module > Modul-Manager, suchen Sie „Zugang zum Shop nach Kundengruppen“ und klicken Sie auf „Konfigurieren“. Passen Sie die Einstellungen an, um Ihren Zugang zu ermöglichen.
\* **Lösung 2 (Wenn Sie keinen Zugriff auf das BO haben):** Wenn Sie komplett ausgesperrt sind, müssen Sie das Modul möglicherweise vorübergehend per FTP deaktivieren. Gehen Sie zu `modules/asg/` und benennen Sie die Datei `asg.php` um (z.B. `asg.php.bak`). Dadurch wird das Modul deaktiviert. Dann können Sie sich in Ihr BO einloggen und es wieder aktivieren/neu konfigurieren. Denken Sie daran, die Datei danach wieder in `asg.php` umzubenennen.

**F2: Der benutzerdefinierte Inhalt sieht schlicht aus oder passt nicht zu meinem Theme.**
A2: Der Bereich für benutzerdefinierte Inhalte verwendet eine einfache Vorlage.
\* **Lösung:** Sie können den Rich-Text-Editor verwenden, um HTML, Inline-CSS oder Bilder hinzuzufügen, um Ihre Nachricht zu gestalten. Für fortgeschrittenere Stiländerungen kann ein Webmaster die Datei `custom.css` oder die Vorlage `custom-contents.tpl` ändern (siehe Entwicklerbereich). Stellen Sie sicher, dass Ihr benutzerdefinierter Inhalt gut formatiert und responsiv ist.

**F3: Warum wird das Anmelde-/Registrierungsformular nicht angezeigt?**
A3: Überprüfen Sie die Modulkonfiguration:
\* Stellen Sie sicher, dass „Anmeldeformular auf blockierter Seite anzeigen“ auf JA gesetzt ist.
\* Stellen Sie sicher, dass „Registrierung auf blockierter Seite erlauben“ auf JA gesetzt ist.
\* Stellen Sie außerdem sicher, dass die Kundenregistrierung in Ihren PrestaShop-Einstellungen allgemein aktiviert ist (Kunden > Einstellungen > Kontoerstellung aktivieren).

**F4: Ich habe Änderungen vorgenommen, aber sie erscheinen nicht im Front Office.**
A4: PrestaShop verwendet Caching, was manchmal die Anzeige von Änderungen verzögern kann.
\* **Lösung:** Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Parameter > Leistung**. Klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Dies sollte Ihr Front Office aktualisieren.

**F5: Wie verwalte ich, welche Kunden in welchen Gruppen sind?**
A5: Sie verwalten Kundengruppen über die Standard-PrestaShop-Oberfläche:
\* Gehen Sie zu **Kunden > Kunden**, um einzelne Kundenkonten zu bearbeiten und sie Gruppen zuzuweisen.
\* Gehen Sie zu **Kunden > Gruppen**, um neue Gruppen zu erstellen oder bestehende zu bearbeiten.
\* Denken Sie daran, dass ein Kunde mehreren Gruppen angehören kann. Wenn ein Kunde zu *einer* Gruppe gehört, die Sie als „ohne Zugang“ markiert haben, wird er blockiert.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Zugang zum Shop nach Kundengruppen“ (`asg`) arbeitet hauptsächlich durch das Einhaken in das `displayHeader`-Ereignis. Dies ermöglicht es, seine Logik sehr früh im Seitenlade-Prozess auszuführen, bevor Inhalte gerendert werden. Wenn ein Kunde als eingeschränkt eingestuft wird, übernimmt das Modul die Kontrolle, verhindert das weitere Rendern der Standard-PrestaShop-Seite und zeigt stattdessen seine benutzerdefinierte Zugangsseite an. Es nutzt das PrestaShop-Konfigurationssystem für Einstellungen und Smarty für die Templating.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Controller. Die gesamte Logik ist in der Hauptmoduldatei (`asg.php`) gekapselt und wird über Hooks oder die Methode `getContent()` zur Konfiguration ausgeführt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Entitäten. Es interagiert direkt mit den PrestaShop-Kernklassen `Customer`, `Group` und `Configuration`.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`asg/views/css/custom.css`**
  - **Geltungsbereich:** Front-Office-Kunden-Styling für die Seite mit eingeschränktem Zugang.
  - **Wichtige UI-Komponenten und Container, die es gestaltet:** Diese Datei bietet grundlegendes Styling für den Wrapper des benutzerdefinierten Inhalts, das Anmeldeformular und den Registrierungslink auf der Seite mit eingeschränktem Zugang. Sie stellt sicher, dass der angezeigte Inhalt zentriert und lesbar ist.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:**
    - `.asg_wrapper`: Der Hauptcontainer für den gesamten eingeschränkten Inhalt.
    - `.asg_content`: Das Div, das die benutzerdefinierte HTML-Nachricht enthält.
    - `.asg_login_form`: Der Container für das Anmeldeformular.
    - `.asg_registration_link`: Der Container für den Registrierungslink.
    - Standard-PrestaShop-Formularelemente innerhalb des Anmeldeformulars.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**: Keine explizit als Hook-Templates definiert. Das Modul rendert Templates direkt basierend auf seiner internen Logik.
- **Admin-Templates (`views/templates/admin/`)**:
  - **`asg/views/admin.tpl`**: Dieses Template wird von der Methode `getContent()` in `asg.php` gerendert. Es enthält die HTML-Struktur für das Konfigurationsformular des Moduls im PrestaShop Back Office. Es umfasst die Auswahl der Kundengruppe, Umschalter für Anmeldung/Registrierung und den Rich-Text-Editor für benutzerdefinierte Inhalte.
- **Front-Office-Templates (`views/templates/front/`)**:
  - **`asg/views/custom-contents.tpl`**: Dies ist das primäre Template, das gerendert wird, wenn ein Kunde blockiert ist. Es zeigt den in der Modulkonfiguration definierten benutzerdefinierten Inhalt an. Es enthält bedingt `login-form.tpl` und `registration-link.tpl` basierend auf den Moduleinstellungen.
  - **`asg/views/login-form.tpl`**: Dieses Template enthält den HTML-Code für das Standard-PrestaShop-Kundenanmeldeformular. Es wird in `custom-contents.tpl` eingefügt, wenn die Option „Anmeldeformular anzeigen“ aktiviert ist.
  - **`asg/views/registration-link.tpl`**: Dieses Template enthält den HTML-Code für den Link zur Kundenregistrierungsseite. Es wird in `custom-contents.tpl` eingefügt, wenn die Option „Registrierung erlauben“ aktiviert ist.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Es speichert seine Konfigurationseinstellungen in der Tabelle `ps_configuration` (oder `_configuration` je nach Präfix) unter Verwendung von Schlüsseln wie:
    - `ASG_ALLOWREGAUTH`: Boolean für die Erlaubnis der Registrierung.
    - `ASG_SHOWLOGINFORM`: Boolean für die Anzeige des Anmeldeformulars.
    - `ASG_CCONTENTS`: Mehrsprachiges Feld für benutzerdefinierte Inhalte (HTML).
    - `ASG_WHATTOSHOW`: Serialisiertes Array von Kundengruppen-IDs, die blockiert sind.
    - `ASG_BLOCK_NOT_LOGGED`: Boolean für das Blockieren nicht angemeldeter Benutzer.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird sehr früh beim Laden der Front-Office-Seite innerhalb des `<head>`-Abschnitts ausgeführt. | Dies ist der primäre Hook, der vom Modul verwendet wird. Er überprüft den Anmeldestatus des Kunden und die Gruppenzugehörigkeit. Wenn ein Kunde eingeschränkt ist, beendet er sofort den Standard-PrestaShop-Rendering-Prozess und gibt die benutzerdefinierte Zugangsseite (`custom-contents.tpl`) aus. |
| `actionCustomerGroupsUpdate` | Wird ausgeführt, wenn Kundengruppen aktualisiert werden. | Wird verwendet, um den internen Cache des Moduls bezüglich der Kundengruppen zu leeren, um sicherzustellen, dass Änderungen an Gruppenzuweisungen sofort widergespiegelt werden. |
| `actionObjectCustomerAddAfter` | Wird ausgeführt, nachdem ein neuer Kunde hinzugefügt wurde. | Wird verwendet, um den internen Cache des Moduls bezüglich der Kundengruppen zu leeren, um sicherzustellen, dass neue Kunden korrekt auf den Zugang geprüft werden. |
| `actionObjectCustomerUpdateAfter` | Wird ausgeführt, nachdem ein bestehender Kunde aktualisiert wurde. | Wird verwendet, um den internen Cache des Moduls bezüglich der Kundengruppen zu leeren, um sicherzustellen, dass Änderungen an den Kundengruppenzuweisungen sofort widergespiegelt werden. |

## 5. Offizieller Support & Updates

Für offizielle Updates, Fehlerbehebungen und dedizierten Entwicklersupport für das Modul „Zugang zum Shop nach Kundengruppen“ verweisen wir auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, zeitnahe Unterstützung zu leisten und die Kompatibilität des Moduls mit den neuesten PrestaShop-Versionen sicherzustellen.

---
title: "Datenbankoptimierung - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Datenbankoptimierung von MyPresta.eu."
sidebar:
  label: "Datenbankoptimierung - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Database Optimization auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/database-optimization.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/database-optimization/)
>
> ---


# Datenbankoptimierung

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul Datenbankoptimierung. Sie finden ihn, indem Sie zu **Module > Modul-Manager** navigieren und neben „Datenbankoptimierung“ auf „Konfigurieren“ klicken.

#### **Unerwünschte Warenkörbe**

- **Was diese Einstellung bewirkt:** Diese Option steuert, ob das Modul alte, abgebrochene Warenkörbe aus Ihrer Datenbank entfernt. Dies sind Warenkörbe, die Kunden begonnen, aber nie eine Bestellung dafür abgeschlossen haben.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Ja“ gesetzt:* Das Modul löscht diese alten, unvollständigen Warenkörbe regelmäßig. Dies reduziert die Größe Ihrer Datenbank und kann die Leistung verbessern, da PrestaShop keine Daten für Tausende von abgebrochenen Warenkörben verwalten muss.
  - *Wenn auf „Nein“ gesetzt:* Alte Warenkörbe bleiben in Ihrer Datenbank. Obwohl dies historische Daten bewahrt, kann es im Laufe der Zeit zu einer Aufblähung der Datenbank beitragen.
- **Empfohlener Wert:** **Ja**. Sofern Sie keinen spezifischen geschäftlichen Grund haben, alle Daten abgebrochener Warenkörbe zu behalten (z.B. für sehr tiefe historische Analysen), ist deren Bereinigung vorteilhaft für die Leistung.
- **Händlerszenario / Beispiel:** Wenn Sie feststellen, dass Ihre Datenbank sehr groß wird und Ihr Shop langsamer wird, ist die Aktivierung dieser Option ein schneller Gewinn, um eine häufige Quelle unnötiger Daten zu entfernen.

#### **Verbindungen**

- **Was diese Einstellung bewirkt:** Diese Option steuert, ob das Modul alte Verbindungsprotokolle aus Ihrer Datenbank entfernt. PrestaShop zeichnet jede Verbindung eines Besuchers zu Ihrem Shop auf, was sich schnell ansammeln kann.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Ja“ gesetzt:* Das Modul löscht alte Verbindungsprotokolle regelmäßig. Dies reduziert die Datenbankgröße erheblich, da Verbindungsprotokolle eine der größten Tabellen in einem stark frequentierten Shop sein können.
  - *Wenn auf „Nein“ gesetzt:* Verbindungsprotokolle werden unbegrenzt beibehalten, was potenziell zu einer sehr großen Datenbank führen kann.
- **Empfohlener Wert:** **Ja**. Für die meisten Shops sind sehr alte Verbindungsprotokolle für den täglichen Betrieb nicht kritisch und können sicher entfernt werden, um die Leistung zu verbessern.
- **Händlerszenario / Beispiel:** Wenn Ihr Shop ein hohes Verkehrsaufkommen hat, können Verbindungsprotokolle extrem schnell wachsen. Die Aktivierung dieser Option hilft, zu verhindern, dass Ihre Datenbank übermäßig groß und langsam wird.

#### **Verbindungsseiten**

- **Was diese Einstellung bewirkt:** Diese Option zielt speziell auf Verbindungsprotokolle ab, die sich auf besuchte einzelne Seiten beziehen. Sie funktioniert in Verbindung mit der Einstellung „Verbindungen“.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Ja“ gesetzt:* Wenn „Verbindungen“ ebenfalls auf „Ja“ gesetzt ist, entfernt das Modul alte Protokolle, die detailliert angeben, welche spezifischen Seiten Besucher angesehen haben.
  - *Wenn auf „Nein“ gesetzt:* Auch wenn „Verbindungen“ auf „Ja“ gesetzt ist, behält das Modul die seitenbezogenen Verbindungsprotokolle bei.
- **Empfohlener Wert:** **Ja**. Ähnlich wie bei allgemeinen Verbindungen können seitenbezogene Protokolle sehr zahlreich sein und werden oft nicht für eine langfristige Analyse benötigt, wenn Sie externe Analysetools wie Google Analytics verwenden.
- **Händlerszenario / Beispiel:** Wenn Sie sich für Seitenaufrufstatistiken auf Google Analytics verlassen, benötigen Sie wahrscheinlich nicht, dass PrestaShop diese granularen Daten unbegrenzt speichert, was eine sichere Bereinigung ermöglicht.

#### **Verbindungsquellen**

- **Was diese Einstellung bewirkt:** Diese Option zielt speziell auf Verbindungsprotokolle ab, die sich auf die Quelle des Besuchers beziehen (z.B. direkt, Suchmaschine, Verweis). Sie funktioniert in Verbindung mit der Einstellung „Verbindungen“.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Ja“ gesetzt:* Wenn „Verbindungen“ ebenfalls auf „Ja“ gesetzt ist, entfernt das Modul alte Protokolle, die detailliert angeben, woher Besucher kamen.
  - *Wenn auf „Nein“ gesetzt:* Auch wenn „Verbindungen“ auf „Ja“ gesetzt ist, behält das Modul die quellenspezifischen Verbindungsprotokolle bei.
- **Empfohlener Wert:** **Ja**. Wie andere Verbindungsdaten können diese oft von externen Analysetools verwaltet werden.
- **Händlerszenario / Beispiel:** Wenn Ihr Marketingteam Tools wie Google Analytics oder andere CRM-Systeme verwendet, um Traffic-Quellen zu verfolgen, könnten die internen PrestaShop-Protokolle redundant sein und können bereinigt werden, um Datenbankplatz zu sparen.

#### **Gäste**

- **Was diese Einstellung bewirkt:** Diese Option steuert, ob das Modul alte, inaktive Gastkonten aus Ihrer Datenbank entfernt. Dies sind Konten, die für Besucher erstellt wurden, die einen Checkout als Gast begonnen, ihn aber nie abgeschlossen haben, oder einfach nur ohne Registrierung gebrowst haben.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Ja“ gesetzt:* Das Modul löscht diese alten Gastkonten regelmäßig. Dies hilft, Ihre Kundendatenbank sauber und auf aktive oder registrierte Benutzer konzentriert zu halten.
  - *Wenn auf „Nein“ gesetzt:* Alte Gastkonten bleiben unbegrenzt in Ihrer Datenbank.
- **Empfohlener Wert:** **Ja**. Sofern Sie keinen spezifischen Bedarf haben, jeden einzelnen Gastdatensatz zu behalten, hilft deren Bereinigung, eine aufgeräumte Datenbank zu pflegen.
- **Händlerszenario / Beispiel:** Wenn Ihr Shop viele Besucher hat, die browsen, sich aber nicht registrieren oder Käufe abschließen, kann die Gasttabelle erheblich wachsen. Die Bereinigung dieser hilft, Ihre Kundendaten überschaubar zu halten.

#### **Updates prüfen**

- **Was diese Einstellung bewirkt:** Diese Einstellung steuert, ob das Modul automatisch nach neuen Versionen und Updates von MyPresta.eu sucht.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Aktivieren“ gesetzt:* Das Modul verbindet sich regelmäßig mit MyPresta.eu, um zu prüfen, ob eine neuere Version verfügbar ist. Wenn ja, erhalten Sie eine Benachrichtigung in Ihrem PrestaShop Back Office.
  - *Wenn auf „Deaktivieren“ gesetzt:* Das Modul sucht nicht nach Updates. Sie müssen manuell in Ihrem MyPresta.eu-Konto nach neuen Versionen suchen.
- **Empfohlener Wert:** **Aktivieren**. Dies stellt sicher, dass Sie immer über verfügbare Updates informiert sind, die oft Fehlerbehebungen, Leistungsverbesserungen und neue Funktionen enthalten.
- **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Ihre Module immer auf dem neuesten Stand sind, um Sicherheit und Leistung zu gewährleisten. Die Aktivierung dieser Option bietet bequeme Benachrichtigungen.

#### **Update-Benachrichtigungen**

- **Was diese Einstellung bewirkt:** Diese Einstellung steuert, ob Sie Benachrichtigungen in Ihrem PrestaShop Back Office erhalten, wenn ein Update verfügbar ist (wenn „Updates prüfen“ aktiviert ist).
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Aktivieren“ gesetzt:* Sie sehen eine Benachrichtigung in Ihrem Back Office, wenn eine neue Version des Moduls erkannt wird.
  - *Wenn auf „Deaktivieren“ gesetzt:* Auch wenn „Updates prüfen“ aktiviert ist und ein Update verfügbar ist, erhalten Sie keine sichtbare Benachrichtigung im Back Office.
- **Empfohlener Wert:** **Aktivieren**. Dies arbeitet Hand in Hand mit „Updates prüfen“, um Sie auf dem Laufenden zu halten.
- **Händlerszenario / Beispiel:** Sie möchten sofort benachrichtigt werden, wenn ein Update bereit ist, damit Sie dessen Installation planen können, um sicherzustellen, dass Ihr Shop von den neuesten Verbesserungen profitiert.

#### **Modulseite**

- **Was diese Einstellung bewirkt:** Diese Einstellung ist wahrscheinlich eine Anzeigeoption für die eigene Seite oder Informationen des Moduls innerhalb des Back Office. (Basierend auf der typischen MyPresta.eu-Modulstruktur könnte dies einen Link oder ein spezifisches Anzeigeelement steuern, das sich auf das Modul selbst bezieht).
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Aktivieren“ gesetzt:* Zeigt wahrscheinlich einen Link oder einen Abschnitt an, der sich auf die Modulinformationen oder andere MyPresta.eu-Module bezieht.
  - *Wenn auf „Deaktivieren“ gesetzt:* Dieser Link oder Abschnitt wird ausgeblendet.
- **Empfohlener Wert:** **Aktivieren**. Es bietet normalerweise schnellen Zugriff auf Support oder andere nützliche Ressourcen.
- **Händlerszenario / Beispiel:** Sie möchten einfachen Zugriff auf MyPresta.eu-Ressourcen direkt von Ihrer Modulkonfigurationsseite aus.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Unerwünschte Warenkörbe | Ja | Entfernt alte, abgebrochene Warenkörbe, um die Datenbankgröße zu reduzieren und die Leistung zu verbessern. |
| Modulkonfiguration | Verbindungen | Ja | Entfernt alte Besucher-Verbindungsprotokolle, um die Datenbankgröße erheblich zu reduzieren. |
| Modulkonfiguration | Verbindungsseiten | Ja | Entfernt alte Protokolle spezifischer Seiten, die von Verbindungen besucht wurden. |
| Modulkonfiguration | Verbindungsquellen | Ja | Entfernt alte Protokolle der Traffic-Quellen für Verbindungen. |
| Modulkonfiguration | Gäste | Ja | Entfernt alte, inaktive Gastkonten, um Kundendaten sauber zu halten. |
| Modulkonfiguration | Updates prüfen | Aktivieren | Prüft automatisch MyPresta.eu auf Modul-Updates. |
| Modulkonfiguration | Update-Benachrichtigungen | Aktivieren | Zeigt Back Office-Benachrichtigungen an, wenn Modul-Updates verfügbar sind. |
| Modulkonfiguration | Modulseite | Aktivieren | Steuert die Anzeige von modulbezogenen Links/Informationen auf der Konfigurationsseite. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Nachdem ich das Modul aktiviert habe, scheint mein Shop nicht schneller zu sein. Woran liegt das?**
A: Datenbankoptimierung ist ein Teil des Leistungs-Puzzles. Während es unnötige Daten bereinigt, können andere Faktoren wie Serverressourcen, Bildoptimierung, schwere Module oder unoptimierte benutzerdefinierte Themes Ihren Shop immer noch verlangsamen. Stellen Sie sicher, dass Sie auch Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung) nach der Konfiguration geleert haben.

**F: Löscht dieses Modul wichtige Kundendaten oder Bestellungen?**
A: Nein. Dieses Modul ist speziell darauf ausgelegt, *unerwünschte* und *inaktive* Daten zu löschen: abgebrochene Warenkörbe, alte Verbindungsprotokolle und Gastkonten, die nie konvertiert wurden. Es berührt keine abgeschlossenen Bestellungen, aktiven Kundenkonten, Produktdaten oder andere kritische Shop-Informationen.

**F: Wie oft bereinigt das Modul die Datenbank? Ist es automatisch?**
A: Das Modul führt seine Bereinigungsvorgänge aus, wenn seine Konfiguration gespeichert wird oder wenn bestimmte Hintergrundaufgaben von PrestaShop ausgelöst werden. Es ist kein kontinuierlicher, Echtzeit-Reiniger. Der Hauptvorteil ergibt sich aus der Entfernung angesammelter alter Daten. Für eine kontinuierliche, geplante Bereinigung müssen Sie es möglicherweise mit einem Cron-Job kombinieren, der die Bereinigungslogik des Moduls regelmäßig auslöst (obwohl sich dieses Modul hauptsächlich auf einmalige oder beim Speichern erfolgende Bereinigung konzentriert).

**F: Ich habe „Updates prüfen“ und „Update-Benachrichtigungen“ deaktiviert, möchte aber jetzt über Updates informiert werden. Wie aktiviere ich sie wieder?**
A: Gehen Sie einfach zurück zur Konfigurationsseite des Moduls (Module > Modul-Manager > Datenbankoptimierung konfigurieren) und setzen Sie sowohl „Updates prüfen“ als auch „Update-Benachrichtigungen“ auf „Aktivieren“. Speichern Sie Ihre Änderungen, und das Modul wird wieder nach neuen Versionen suchen und Sie darüber benachrichtigen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul Datenbankoptimierung ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich zur Ausführung von Datenbankbereinigungsvorgängen entwickelt wurde. Es folgt der Standard-PrestaShop-Modulstruktur und nutzt die `Module`-Klasse sowie deren `install()`- und `uninstall()`-Methoden für die Einrichtung und den Abbau. Seine Kernfunktionalität liegt in der `getContent()`-Methode, die das Back Office-Konfigurationsformular verarbeitet und die Datenbankoptimierungslogik bei Formularübermittlung auslöst. Es führt keine benutzerdefinierten Controller, Modelle oder Front-Office-Assets ein, was es zu einem leichtgewichtigen und fokussierten Dienstprogramm macht.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Alle Operationen werden im Back Office oder über die Hauptmodulklasse abgewickelt.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration wird direkt in der `getContent()`-Methode der Datei `dboptimization.php` verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

- **Hauptmodulklasse**: `dboptimization/dboptimization.php`
  - **Klassenname**: `DbOptimization`
  - **Elternklasse**: `Module`
  - **Verantwortlichkeit**:
    - Verwaltet die Modulinstallation (`install()`) und Deinstallation (`uninstall()`).
    - Verwaltet die Anzeige und Übermittlung des Back Office-Konfigurationsformulars (`getContent()`).
    - Enthält die Kernlogik für die Datenbankbereinigung basierend auf den konfigurierten Optionen.
    - Registriert und deregistriert Hooks (obwohl dieses Modul hauptsächlich `displayBackOfficeHeader` für Update-Prüfungen verwendet, nicht für die Front-Office-Anzeige).
    - Verwaltet Konfigurationswerte mithilfe von `Configuration::get()` und `Configuration::updateValue()`.
    - Enthält die Logik zur Update-Prüfung (`checkforupdates()`) und zur Anzeige von Benachrichtigungen.

### 4.4 JavaScript-Assets (`views/js/`)

- Keine. Das Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

- Keine. Das Modul enthält keine benutzerdefinierten CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- Keine. Das Modul rendert sein Konfigurationsformular direkt innerhalb der `getContent()`-Methode unter Verwendung von PrestaShops `HelperForm` (oder ähnlicher interner Rendering-Logik) anstatt externer `.tpl`-Dateien.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es interagiert mit bestehenden PrestaShop-Tabellen, hauptsächlich:
    - `ps_cart`: Für „Unerwünschte Warenkörbe“.
    - `ps_connections`: Für „Verbindungen“.
    - `ps_connections_page`: Für „Verbindungsseiten“.
    - `ps_connections_source`: Für „Verbindungsquellen“.
    - `ps_guest`: Für „Gäste“.
  - Konfigurationswerte werden in der Tabelle `ps_configuration` gespeichert:
    - `dbopt_cart`
    - `dbopt_connections`
    - `dbopt_connections_page`
    - `dbopt_connections_source`
    - `dbopt_guest`
    - `update_dboptimization` (für den Zeitstempel der Update-Prüfung)
    - `mypresta_updates` (globale Update-Benachrichtigungseinstellung)
    - `dbopt_check_updates`
    - `dbopt_updates_notifications`
    - `dbopt_module_page`
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Datei / Methode | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- | --- |
| `displayBackOfficeHeader` | `dboptimization.php` | Wird im Header der Back Office-Seiten gerendert. | Wird vom Modul verwendet, um Update-Benachrichtigungen einzufügen, wenn `dbopt_check_updates` und `dbopt_updates_notifications` aktiviert sind. |
| `actionAdminControllerSetMedia` | `dboptimization.php` | Wird ausgeführt, wenn ein Admin-Controller seine Medien (CSS/JS) festlegt. | Potenziell für Update-Prüfungen oder um sicherzustellen, dass alle notwendigen Assets (falls vorhanden) im Admin geladen werden. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und umfassenden Support für das Modul Datenbankoptimierung besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser engagiertes Support-Team steht Händlern und Entwicklern bei Fragen oder Problemen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.

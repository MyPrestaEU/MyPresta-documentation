---
title: "NBU Wechselkurse & Raten - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul NBU Wechselkurse & Raten von MyPresta.eu."
sidebar:
  label: "NBU Wechselkurse & Raten"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul NBU Currency Exchange & Rates (National Bank of Ukraine) auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/nbu-currency-exchange-rates-national-bank-of-ukraine.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/nbu-currency-exchange-rates-national-bank-of-ukraine/)
>
> ---


# NBU Wechselkurse & Raten

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind für das Abrufen von Daten von externen APIs erforderlich. Die meisten modernen Hosting-Umgebungen erfüllen diese Anforderungen standardmäßig.

## 2. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)
Nach der Installation klicken Sie auf "Konfigurieren", um auf die Einstellungen des Moduls zuzugreifen. Hier legen Sie fest, wie die NBU-Kurse auf Ihren Store angewendet werden.

**Bildschirmname:** NBU Wechselkurse & Raten Konfiguration

**Einstellungen & Optionen:**

1.  **CRON-Job-URL:**
    -   **Was diese Einstellung bewirkt:** Dies zeigt die eindeutige URL an, die der CRON-Scheduler Ihres Servers regelmäßig aufrufen muss. Wenn diese URL aufgerufen wird, ruft das Modul automatisch die neuesten NBU-Wechselkurse ab und aktualisiert sie in Ihrem PrestaShop-Store.
    -   **Auswirkung einer Änderung dieser Einstellung:** Sie können diese URL nicht direkt ändern. Sie wird vom Modul generiert. Wenn Sie keinen CRON-Job einrichten, um diese URL aufzurufen, werden die Wechselkurse nicht automatisch aktualisiert, und Sie müssten Aktualisierungen manuell auslösen (falls eine solche Option existiert, was für die Hauptfunktion dieses Moduls nicht der Fall ist).
    -   **Empfohlener Wert:** Kopieren Sie diese URL und richten Sie sie im CRON-Job-Scheduler Ihres Hosting-Kontrollpanels ein.
    -   **Händlerszenario / Beispiel:** Sie kopieren `https://ihrstore.com/module/nburates/cronjob?token=IHR_SICHERER_TOKEN` und fügen es Ihren cPanel- oder Plesk-CRON-Jobs hinzu, um es einmal täglich (z.B. um 3 Uhr morgens) auszuführen. Dies stellt sicher, dass Ihre UAH-Preise immer aktuell sind, bevor Ihre Kunden mit dem Einkaufen beginnen.

2.  **CRON-Job-Frequenz:**
    -   **Was diese Einstellung bewirkt:** Dies ist eine Empfehlung, wie oft Sie den CRON-Job ausführen sollten. Die NBU aktualisiert die Kurse typischerweise einmal täglich.
    -   **Auswirkung einer Änderung dieser Einstellung:** Dies ist rein informativ. Eine Änderung Ihrer tatsächlichen CRON-Job-Frequenz (in Ihrem Hosting-Panel) wirkt sich darauf aus, wie oft die Kurse aktualisiert werden. Eine zu häufige Ausführung (z.B. jede Minute) ist unnötig und kann Serverressourcen ohne Nutzen verbrauchen, da sich die NBU-Kurse nicht so oft ändern. Eine zu seltene Ausführung (z.B. einmal pro Woche) bedeutet, dass Ihre Kurse veraltet sein könnten.
    -   **Empfohlener Wert:** Einmal täglich.
    -   **Händlerszenario / Beispiel:** Sie stellen den CRON-Job Ihres Servers so ein, dass er `0 3 * * *` (jeden Tag um 3 Uhr morgens) ausgeführt wird, um den täglichen Updates der NBU zu entsprechen.

3.  **Zu aktualisierende Währung (UAH):**
    -   **Was diese Einstellung bewirkt:** Dieses Feld ermöglicht es Ihnen, die ID der ukrainischen Hrywnja (UAH) in Ihrem PrestaShop-Store anzugeben. Das Modul muss wissen, welche Währung für Updates angesprochen werden soll.
    -   **Auswirkung einer Änderung dieser Einstellung:** Wenn die ID falsch oder leer ist, kann das Modul die UAH-Währung nicht finden und aktualisieren, und Ihre Preise spiegeln die NBU-Kurse nicht wider.
    -   **Empfohlener Wert:** Die ID Ihrer UAH-Währung. Sie finden diese, indem Sie im PrestaShop Back Office zu **International > Währungen** navigieren, die UAH-Währung bearbeiten und die URL überprüfen (z.B. `id_currency=3` bedeutet, die ID ist 3).
    -   **Händlerszenario / Beispiel:** Ihre UAH-Währung hat die ID `3`. Sie geben `3` in dieses Feld ein. Wenn der CRON-Job nun ausgeführt wird, weiß das Modul, dass es den Wechselkurs für die Währung mit der ID `3` aktualisieren muss.

4.  **Marge (%):**
    -   **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, eine prozentuale Marge (Aufschlag oder Abschlag) zu den abgerufenen NBU-Wechselkursen hinzuzufügen. Ein positiver Wert erhöht den Kurs (macht UAH-Preise höher), und ein negativer Wert verringert ihn (macht UAH-Preise niedriger).
    -   **Auswirkung einer Änderung dieser Einstellung:**
        -   *Wenn auf 0 gesetzt:* Das Modul verwendet den exakten NBU-Kurs.
        -   *Wenn auf 2 gesetzt:* Der UAH-Wechselkurs ist 2% höher als der offizielle NBU-Kurs. Wenn die NBU beispielsweise 1 EUR = 40 UAH angibt, verwendet Ihr Store mit einer Marge von 2% 1 EUR = 40,8 UAH. Dies kann helfen, Transaktionsgebühren zu decken oder einen kleinen Gewinnpuffer zu bieten.
        -   *Wenn auf -1 gesetzt:* Der UAH-Wechselkurs ist 1% niedriger als der offizielle NBU-Kurs. Dies könnte für Aktionspreise oder zur Gewährung eines kleinen Rabatts verwendet werden.
    -   **Empfohlener Wert:** Hängt von Ihrer Geschäftsstrategie ab. `0` für exakte NBU-Kurse oder ein kleiner positiver Prozentsatz (z.B. `1` oder `2`), um Kosten zu decken.
    -   **Händlerszenario / Beispiel:** Sie möchten Zahlungs-Gateway-Gebühren für UAH-Transaktionen leicht ausgleichen. Sie setzen die Marge auf `1.5`. Nun werden alle UAH-Preise mit dem NBU-Kurs plus zusätzlichen 1,5% berechnet.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfiguration | CRON-Job-URL | N/A (Generiert) | Die URL zum Auslösen täglicher Kursaktualisierungen. Muss im Hosting-CRON eingerichtet werden. |
| Modulkonfiguration | CRON-Job-Frequenz | Einmal täglich | Informative Empfehlung für die CRON-Job-Planung. |
| Modulkonfiguration | Zu aktualisierende Währung (UAH) | ID der UAH-Währung | Gibt an, welche Währung in PrestaShop mit NBU-Kursen aktualisiert werden soll. Entscheidend für die Modulfunktion. |
| Modulkonfiguration | Marge (%) | 0 | Fügt einen prozentualen Aufschlag/Abschlag zum NBU-Kurs für Preisgestaltungsflexibilität hinzu. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine UAH-Preise werden nicht aktualisiert. Was soll ich tun?**
A1:
*   **CRON-Job überprüfen:** Der häufigste Grund ist ein falsch eingerichteter oder fehlender CRON-Job. Überprüfen Sie, ob die CRON-Job-URL aus der Modulkonfiguration korrekt in Ihrem Hosting-Panel hinzugefügt und zur Ausführung geplant ist.
*   **UAH-Währungs-ID überprüfen:** Stellen Sie sicher, dass die Einstellung "Zu aktualisierende Währung (UAH)" in der Modulkonfiguration mit der genauen ID Ihrer UAH-Währung in PrestaShop (**International > Währungen**) übereinstimmt.
*   **NBU-Verfügbarkeit überprüfen:** Gelegentlich kann die NBU-API vorübergehend nicht verfügbar sein. Warten Sie ein paar Stunden und versuchen Sie es erneut. Das Modul ist so konzipiert, dass es den zuletzt bekannten Kurs verwendet, wenn die API ausgefallen ist.
*   **Server-Logs:** Überprüfen Sie die CRON-Job-Logs Ihres Servers (falls verfügbar) auf Fehler, wenn die CRON-URL aufgerufen wird.

**F2: Das Modul ist installiert, aber ich sehe keine visuellen Änderungen in meinem Store.**
A2: Dieses Modul arbeitet im Hintergrund, um Wechselkurse zu aktualisieren. Es fügt Ihrem Store keine neuen Blöcke oder visuellen Elemente hinzu. Seine Wirkung zeigt sich in der genauen Berechnung der Produktpreise, wenn UAH die ausgewählte Währung ist.

**F3: Kann ich die Kurse manuell aktualisieren, wenn der CRON-Job fehlschlägt?**
A3: Der primäre Mechanismus des Moduls ist der CRON-Job. Während Sie Wechselkurse in PrestaShop manuell aktualisieren können (**International > Währungen**), würde dies die NBU-Kurse überschreiben. Die beste Vorgehensweise ist, sicherzustellen, dass Ihr CRON-Job korrekt funktioniert. Wenn Sie eine sofortige Aktualisierung benötigen, können Sie die CRON-URL einmal manuell auslösen, indem Sie sie in Ihrem Browser besuchen (obwohl dies nicht die beabsichtigte langfristige Lösung ist).

**F4: Was passiert an Bankfeiertagen, wenn die NBU keine neuen Kurse veröffentlicht?**
A4: Das Modul ist so konzipiert, dass es dies intelligent handhabt. Wenn die NBU an einem bestimmten Tag (z.B. Wochenenden oder Feiertagen) keine neuen Kurse veröffentlicht, behält das Modul typischerweise den zuletzt erfolgreich abgerufenen Kurs bei. Dies stellt sicher, dass Ihre UAH-Preise stabil und konsistent bleiben.

**F5: Wie lösche ich den Smarty-Cache, wenn ich Änderungen vornehme und diese nicht sehe?**
A5: Obwohl die Änderungen dieses Moduls hauptsächlich datengesteuert sind (Wechselkurse) und weniger visuelle Templates betreffen, kann das Löschen des Caches manchmal helfen. Gehen Sie in Ihrem PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung**. Setzen Sie "Template-Kompilierung" auf "Templates neu kompilieren, wenn die Dateien aktualisiert wurden" oder "Kompilierung erzwingen" und klicken Sie auf "Cache leeren". Denken Sie daran, nach der Fehlerbehebung für die Produktionsleistung wieder auf "Template-Dateien niemals neu kompilieren" zurückzuschalten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)
Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster.

### 4.1 Architekturübersicht
Das Modul `NBU Wechselkurse & Raten` ist ein leichtgewichtiges PrestaShop-Modul, das entwickelt wurde, um externe Wechselkurse von der API der Nationalbank der Ukraine (NBU) zu integrieren. Es folgt einem einfachen MVC-ähnlichen Muster innerhalb der PrestaShop-Modulstruktur. Die Kernlogik befindet sich in der Hauptmoduldatei (`cronjob.php`), die die Konfiguration, Installation und die primäre CRON-Job-Ausführung handhabt. Es verwendet die `Configuration`-Klasse von PrestaShop zum Speichern von Einstellungen und das `Currency`-ObjectModel zum Aktualisieren von Kursen. Die Hauptfunktionalität des Moduls wird über einen Front-Controller bereitgestellt, der speziell für den Aufruf durch einen serverseitigen CRON-Job konzipiert ist.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**:
    *   `nburates/controllers/front/cronjob.php`
        *   **Klassenname:** `NburatesCronjobModuleFrontController` (erweitert `ModuleFrontController`)
        *   **Verantwortlichkeit:** Dies ist der kritische Endpunkt für den CRON-Job. Beim Zugriff führt er die folgenden Aktionen aus:
            1.  Validiert einen sicheren Token (`token`), der in der URL übergeben wird, um unbefugten Zugriff zu verhindern.
            2.  Ruft die Modulkonfigurationseinstellungen ab (UAH-Währungs-ID, Marge).
            3.  Ruft die neuesten NBU-Wechselkurse von der offiziellen NBU-API ab (wahrscheinlich `https://bank.gov.ua/NBUStatService/v1/statdirectory/exchangenew?json`).
            4.  Analysiert die JSON-Antwort, um relevante Wechselkurse zu extrahieren.
            5.  Wendet die konfigurierte Marge auf die abgerufenen Kurse an.
            6.  Aktualisiert den Wechselkurs für die angegebene UAH-Währung in der Tabelle `ps_currency` unter Verwendung des `Currency`-ObjectModels von PrestaShop.
            7.  Behandelt Fehlerbedingungen (z.B. API nicht erreichbar, ungültige Antwort) durch Protokollierung oder Rückgriff auf frühere Kurse.
            8.  Gibt eine einfache Erfolgs- oder Fehlermeldung aus, die für die CRON-Job-Protokollierung geeignet ist.
    *   `nburates/controllers/front/index.php`
        *   **Klassenname:** `NburatesIndexModuleFrontController` (erweitert `ModuleFrontController`)
        *   **Verantwortlichkeit:** Dies ist ein standardmäßiger leerer `index.php`-Front-Controller, der oft in Modulen enthalten ist, um die Verzeichnisauflistung zu verhindern oder als Platzhalter zu dienen. Er enthält typischerweise keine spezifische Logik für die Kernfunktion dieses Moduls.

-   **Back-Office-Admin-Controller**:
    *   Keine. Die gesamte Konfiguration wird direkt innerhalb der Methode `getContent()` der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)
-   Keine. Das Modul interagiert direkt mit dem Kern-`Currency`-ObjectModel und der `Configuration`-Klasse von PrestaShop.

### 4.4 JavaScript-Assets (`views/js/`)
-   Keine. Das Modul verwendet kein benutzerdefiniertes JavaScript.

### 4.5 CSS-Stylesheets (`views/css/`)
-   Keine. Das Modul verwendet kein benutzerdefiniertes CSS. Die Admin-Konfigurationsseite basiert auf dem Standard-Back-Office-Styling von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Admin-Templates (`views/templates/admin/`)**:
    *   `nburates/views/admin.tpl`
        *   **Zweck:** Dieses Template rendert das Konfigurationsformular des Moduls im PrestaShop Back Office.
        *   **Inhalt:** Es zeigt die CRON-Job-URL, die CRON-Frequenzempfehlung, Eingabefelder für die UAH-Währungs-ID und den Margenprozentsatz an. Es verwendet typischerweise Standard-PrestaShop-Formularhelfer und -Styling.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Das Modul erstellt keine benutzerdefinierten Datenbanktabellen.
    *   Es interagiert mit der Tabelle `ps_configuration`, um seine Einstellungen zu speichern (z.B. `NBU_RATES_UAH_CURRENCY_ID`, `NBU_RATES_MARGIN`, `NBU_RATES_SECURE_TOKEN`).
    *   Es aktualisiert die Tabelle `ps_currency`, insbesondere die Spalte `conversion_rate` für die UAH-Währung.

-   **Registrierte Hooks-Tabelle**:
    Das Modul registriert keine traditionellen Anzeige-Hooks (`displayHeader`, `displayFooter` usw.), die Inhalte im Front Office rendern. Sein primärer "Hook" ist die `action`, die es ausführt, wenn sein Front-Controller vom CRON-Job aufgerufen wird.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
|---|---|---|
| `actionModuleInstall` | Während der Modulinstallation | Erstellt Konfigurationseinträge, generiert sicheren Token. |
| `actionModuleUninstall` | Während der Moduldeinstallation | Bereinigt Konfigurationseinträge. |
| (Implizit) `ModuleFrontController::initContent()` für `NburatesCronjobModuleFrontController` | Wenn die CRON-URL aufgerufen wird | Ruft NBU-Kurse ab, wendet Marge an, aktualisiert UAH-Wechselkurs. |

## 5. Offizieller Support & Updates
Für offizielle Updates, Fehlerbehebungen und Entwickler-Support für das Modul "NBU Wechselkurse & Raten" verweisen wir auf Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, zeitnahe Unterstützung zu leisten und die Kompatibilität des Moduls mit den neuesten PrestaShop-Versionen sicherzustellen.

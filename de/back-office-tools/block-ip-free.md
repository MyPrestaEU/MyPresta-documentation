---
title: "Block IP free - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Block IP free von MyPresta.eu."
sidebar:
  label: "Block IP free - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Block IP free auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/block-ip-free.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/block-ip-free/)
>
> ---


# Block IP free

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Keine besonderen Anforderungen über eine Standard-PrestaShop-Hosting-Umgebung hinaus.

## 2. Vollständige Konfigurationsanleitung (Alle Einstellungen nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > Block IP free)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul „Block IP free“. Hier finden Sie alle Einstellungen, um Ihre blockierten IP-Adressen und die ihnen angezeigte Nachricht zu verwalten.

**Bildschirmname & Menüpfad:**

- **Menüpfad:** Back Office > Module > Modul-Manager > Block IP free > Konfigurieren

#### Einstellungen & Optionen:

1. **IP-Adresse (Eingabefeld)**

   - **Was diese Einstellung bewirkt:** Hier geben Sie die IP-Adresse ein, die Sie vom Zugriff auf Ihren Shop blockieren möchten.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn eine IP zur Liste hinzugefügt wird:* Jeder Besucher, der versucht, von dieser spezifischen IP-Adresse aus auf Ihren Shop zuzugreifen, wird abgewiesen und erhält die „Nachricht bei blockiertem Zugriff“ angezeigt.
     - *Wenn eine IP aus der Liste entfernt wird:* Besucher von dieser IP-Adresse erhalten wieder vollen Zugriff auf Ihren Shop.
   - **Empfohlener Wert:** Geben Sie die genaue IP-Adresse ein, die Sie blockieren möchten. Sie können mehrere IPs nacheinander hinzufügen, indem Sie jede eingeben und auf „Hinzufügen“ klicken.
   - **Händlerszenario / Beispiel:** Wenn Sie feststellen, dass eine bestimmte IP-Adresse (z. B. `192.168.1.100`) wiederholt betrügerische Bestellungen versucht oder Ihre Produktdaten abgreift, würden Sie `192.168.1.100` hier eingeben und auf „Hinzufügen“ klicken, um sie zu blockieren.
2. **Nachricht bei blockiertem Zugriff (Textfeld)**

   - **Was diese Einstellung bewirkt:** Hier können Sie die Nachricht anpassen, die blockierte Besucher sehen, wenn sie versuchen, auf Ihren Shop zuzugreifen.
   - **Auswirkung der Änderung dieser Einstellung:**
     - *Wenn eine benutzerdefinierte Nachricht eingegeben wird:* Blockierte Besucher sehen Ihre personalisierte Nachricht anstelle einer Standardnachricht. Dies ermöglicht es Ihnen, höflich, informativ oder bestimmt zu sein.
     - *Wenn als Standard belassen:* Eine Standardnachricht „Zugriff verweigert“ wird angezeigt.
   - **Empfohlener Wert:** Eine klare und prägnante Nachricht. So etwas wie: „Der Zugriff auf diesen Shop wurde von Ihrer IP-Adresse aus blockiert. Wenn Sie glauben, dass dies ein Fehler ist, kontaktieren Sie bitte den Support.“
   - **Händlerszenario / Beispiel:** Sie könnten eine Nachricht wie „Aufgrund verdächtiger Aktivitäten wurde der Zugriff von Ihrer IP-Adresse vorübergehend eingeschränkt. Bitte kontaktieren Sie unser Support-Team, wenn Sie glauben, dass dies ein Fehler ist.“ anzeigen. Dies bietet eine bessere Benutzererfahrung als eine generische Fehlermeldung.

#### Verwalten der Liste blockierter IPs:

Unter dem Eingabefeld „IP-Adresse“ sehen Sie eine Liste aller aktuell blockierten IP-Adressen.

- **Um eine IP hinzuzufügen:** Geben Sie die IP-Adresse in das Feld „IP-Adresse“ ein und klicken Sie auf die Schaltfläche „Hinzufügen“.
- **Um eine IP zu entfernen:** Neben jeder aufgelisteten IP-Adresse befindet sich eine Schaltfläche „Löschen“ (oft durch ein Papierkorb-Symbol dargestellt). Klicken Sie auf diese Schaltfläche, um diese spezifische IP zu entsperren.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfigurationsseite | IP-Adresse | Leer (IPs nach Bedarf hinzufügen) | Fügt bestimmte IP-Adressen zur Blockierliste hinzu/entfernt sie. Blockierte IPs können nicht auf den Shop zugreifen. |
| Modul-Konfigurationsseite | Nachricht bei blockiertem Zugriff | „Zugriff verweigert“ (oder ähnlich) | Passt die Nachricht an, die Besuchern von blockierten IP-Adressen angezeigt wird. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe eine IP blockiert, aber der Benutzer kann immer noch auf meinen Shop zugreifen. Warum?**
A:

1. **Caching:** Ihr PrestaShop-Shop oder Server hat möglicherweise Caching aktiviert. Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**) und gegebenenfalls jeden serverseitigen Cache (wie Varnish, LiteSpeed Cache, Cloudflare).
2. **Dynamische IP:** Der Benutzer hat möglicherweise eine dynamische IP-Adresse, die sich geändert hat, seit Sie die vorherige blockiert haben.
3. **Proxy/VPN:** Der Benutzer verwendet möglicherweise einen VPN- oder Proxy-Server, der seine echte IP-Adresse maskiert. Sie müssten die IP des VPN-/Proxy-Servers blockieren, wenn Sie ihn identifizieren können.
4. **Falsche IP:** Überprüfen Sie nochmals, ob Sie die richtige IP-Adresse eingegeben haben.

**F: Ich habe versehentlich meine eigene IP-Adresse blockiert und kann jetzt nicht mehr auf mein Back Office zugreifen! Was soll ich tun?**
A: Dies ist eine kritische, aber behebbare Situation. Sie müssen direkt auf Ihren Server zugreifen:

1. **Via FTP/SFTP:** Verbinden Sie sich mit einem FTP-Client (wie FileZilla) mit dem Server Ihres Shops.
2. **Navigieren Sie zum Module-Ordner:** Gehen Sie zu `Ihr_prestashop_root/modules/`.
3. **Benennen Sie den Modul-Ordner um:** Suchen Sie den Ordner `banipfree` und benennen Sie ihn in etwas wie `banipfree_DISABLED` um. Dies deaktiviert das Modul effektiv.
4. **Zugriff auf das Back Office:** Sie sollten sich nun in Ihr PrestaShop Back Office einloggen können.
5. **Wieder aktivieren und konfigurieren:** Benennen Sie den Ordner zurück in `banipfree`, gehen Sie dann zu **Module > Modul-Manager**, suchen Sie „Block IP free“ und klicken Sie auf „Konfigurieren“, um Ihre IP aus der Blockierliste zu entfernen.

**F: Kann ich einen Bereich von IP-Adressen blockieren, anstatt nur eine einzelne?**
A: Die aktuelle Version des Moduls „Block IP free“ ermöglicht das Blockieren einzelner IP-Adressen. Für das Blockieren ganzer Bereiche (z. B. `192.168.1.0/24`) benötigen Sie in der Regel eine Server-Konfiguration (z. B. `.htaccess`-Regeln oder Firewall-Einstellungen) oder ein fortschrittlicheres Sicherheitsmodul.

**F: Wird dieses Modul meinen Shop verlangsamen?**
A: Nein, das Modul ist sehr leichtgewichtig. Es überprüft die IP-Adresse des Besuchers sehr früh im PrestaShop-Ladevorgang. Wenn die IP blockiert ist, wird der Shop-Inhalt überhaupt nicht geladen, was tatsächlich Serverressourcen sparen kann, indem verhindert wird, dass unerwünschter Traffic Anfragen vollständig verarbeitet.

**F: Wie finde ich die IP-Adresse eines problematischen Besuchers?**
A: Sie können IP-Adressen an mehreren Stellen finden:

- **Server-Zugriffsprotokolle:** Ihr Webhosting-Kontrollpanel (cPanel, Plesk) bietet in der Regel Zugriff auf Roh-Zugriffsprotokolle, die die IP-Adresse jedes Besuchers auflisten.
- **PrestaShop-Bestelldetails:** Bei Bestellungen wird die IP-Adresse des Kunden normalerweise auf der Bestelldetailseite im Back Office erfasst.
- **Analysetools:** Einige fortgeschrittene Analysetools zeigen möglicherweise Besucher-IP-Adressen an, oft jedoch anonymisiert.
- **Drittanbieter-Sicherheitsmodule:** Andere Sicherheitsmodule protokollieren möglicherweise verdächtige Aktivitäten mit IP-Adressen.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul „Block IP free“ arbeiten.

### 4.1 Architekturübersicht

Das Modul „Block IP free“ ist ein einfaches, einteiliges PrestaShop-Modul (`banipfree.php`), das hauptsächlich den `actionDispatcher`-Hook nutzt. Dieser Hook wird sehr früh im PrestaShop-Anfragezyklus ausgeführt, wodurch das Modul die IP-Adresse des Besuchers überprüfen kann, bevor eine signifikante Verarbeitung oder Darstellung des Shop-Inhalts erfolgt. Wenn die IP in der Blockierliste gefunden wird, beendet das Modul die Anfrage sofort und zeigt eine benutzerdefinierte Nachricht an, wodurch es effektiv als frühe Firewall fungiert. Die Konfiguration wird über die Standardmethode `getContent()` gehandhabt, wobei die Einstellungen in `ps_configuration` gespeichert werden.

### 4.2 Controller (`controllers/`)

- Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Logik ist in der Hauptmoduldatei gekapselt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Dieses Modul enthält **keine** benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/`. Die gesamte Datenverarbeitung erfolgt direkt über `Configuration::get()` und `Configuration::updateValue()`.

### 4.4 JavaScript-Assets (`views/js/`)

- Dieses Modul enthält **keine** benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

- Dieses Modul enthält **keine** benutzerdefinierten CSS-Dateien. Die Nachricht bei blockiertem Zugriff wird mit minimalem, Inline-Styling oder Standard-Browser-Styling angezeigt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- Dieses Modul enthält **keine** benutzerdefinierten Smarty-Template-Dateien. Die Nachricht bei blockiertem Zugriff wird direkt als rohes HTML/Text innerhalb der Methode `hookActionDispatcher` ausgegeben.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen in der Standardtabelle `ps_configuration`:

- `BANIPFREE_LIST`: Speichert eine kommagetrennte Zeichenfolge von blockierten IP-Adressen.
- `BANIPFREE_MSG`: Speichert die benutzerdefinierte Nachricht, die blockierten Benutzern angezeigt wird.
- `mypresta_updates`, `update_`, `updatev_`: Interne Schlüssel, die von MyPresta.eu für Modul-Update-Prüfungen verwendet werden.

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionDispatcher` | Wird sehr früh im PrestaShop-Anfragezyklus ausgeführt, vor dem Controller-Dispatch. | Dies ist der primäre Hook, der vom Modul verwendet wird. Er ruft die IP-Adresse des Besuchers ab, überprüft sie anhand der `BANIPFREE_LIST`, und wenn eine Übereinstimmung gefunden wird, gibt er die `BANIPFREE_MSG` aus und beendet die Skriptausführung (`die()`), wodurch ein weiteres Laden des Shops verhindert wird. |

### 4.8 Hauptmoduldatei (`banipfree/banipfree.php`)

Dies ist der Kern des Moduls.

- **`__construct()`**: Initialisiert Modul-Metadaten (Name, Tab, Version, Autor usw.).
- **`install()`**:
  - Ruft `parent::install()` auf.
  - Registriert den `actionDispatcher`-Hook.
  - Setzt anfängliche Konfigurationswerte für `BANIPFREE_LIST` (leer) und `BANIPFREE_MSG` (Standardnachricht).
- **`uninstall()`**:
  - Ruft `parent::uninstall()` auf.
  - Deregistriert den `actionDispatcher`-Hook.
  - Löscht Konfigurationswerte (`BANIPFREE_LIST`, `BANIPFREE_MSG`).
- **`getContent()`**:
  - Verarbeitet die Formularübermittlung zum Speichern von IP-Adressen und der benutzerdefinierten Nachricht.
  - Ruft die aktuelle Liste der blockierten IPs ab und zeigt sie an.
  - Rendert das Konfigurationsformular mit Standard-PrestaShop `HelperForm`-Elementen (Texteingabe für IP, Textbereich für Nachricht, Liste für blockierte IPs mit Löschschaltflächen).
- **`hookActionDispatcher()`**:
  - Dies ist die kritische Methode zum Blockieren.
  - Sie ruft die IP-Adresse des Besuchers (`$_SERVER['REMOTE_ADDR']`) ab.
  - Sie ruft die `BANIPFREE_LIST` aus der `Configuration` ab.
  - Sie überprüft, ob die aktuelle IP in der kommagetrennten Liste vorhanden ist.
  - Wenn die IP blockiert ist, ruft sie `BANIPFREE_MSG ab`, gibt eine einfache HTML-Seite mit der Nachricht aus und ruft `die()` auf, um die weitere Ausführung zu stoppen.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Block IP free“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.

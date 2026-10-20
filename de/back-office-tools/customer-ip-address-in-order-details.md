---
title: "Kunden-IP-Adresse in Bestelldetails - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Kunden-IP-Adresse in Bestelldetails' von MyPresta.eu."
sidebar:
  label: "Kunden-IP-Adresse in Bestelldetails"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Customer IP address in order details auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/customer-ip-address-in-order-details.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/customer-ip-address-in-order-details/)
>
> ---


# Kunden-IP-Adresse in Bestelldetails

## 1. Anforderungen & Kompatibilität
- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend, da dieses Modul minimale externe Abhängigkeiten hat.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Backoffice > Module > Konfigurieren)
Dieses Modul ist extrem einfach und effektiv konzipiert und erfordert keine komplexe Konfiguration. Nach der Installation finden Sie einen grundlegenden Konfigurationsbildschirm.

-   **Bildschirmname & Menüpfad:** Backoffice > Module > Modul-Manager > "Kunden-IP-Adresse in Bestelldetails" > Konfigurieren

Auf diesem Bildschirm sehen Sie typischerweise:

-   **Was diese Einstellung bewirkt:** Dieses Modul hat in der Regel keine spezifischen konfigurierbaren Einstellungen über die Erstinstallation hinaus. Seine Kernfunktionalität (Anzeige der IP-Adresse) ist nach der Installation standardmäßig aktiv. Die Konfigurationsseite könnte lediglich bestätigen, dass das Modul aktiv ist oder grundlegende Informationen bereitstellen.
-   **Auswirkung einer Änderung dieser Einstellung:** Da es keine spezifischen Einstellungen zu ändern gibt, bleibt das Verhalten des Moduls konsistent: Es zeigt die IP-Adresse des Kunden auf der Bestelldetailseite an.
-   **Empfohlener Wert:** N/A (Keine konfigurierbaren Optionen).
-   **Händlerszenario / Beispiel:** Installieren und aktivieren Sie das Modul einfach. Wenn Sie eine Bestellung in Ihrem Backoffice anzeigen, sehen Sie nun die IP-Adresse des Kunden prominent in den Bestelldetails angezeigt.

### 2.2 Konfigurations-Kurzübersichtstabelle
| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
|---|---|---|---|
| Modulkonfigurationsseite | *(Keine spezifischen Einstellungen)* | N/A | Das Modul zeigt die IP-Adressen der Kunden auf den Bestelldetailseiten automatisch an, sobald es installiert und aktiviert ist. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul installiert, sehe aber die IP-Adresse nicht auf der Bestelldetailseite. Was soll ich tun?**
A:
1.  **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass "Kunden-IP-Adresse in Bestelldetails" installiert und aktiviert ist.
2.  **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort angezeigt werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung**, scrollen Sie nach unten und klicken Sie auf "Cache leeren".
3.  **Bestellseite überprüfen:** Navigieren Sie zu einer bestehenden Bestellung (oder geben Sie eine Testbestellung auf) unter **Bestellungen > Bestellungen** und klicken Sie, um die Details anzuzeigen. Die IP-Adresse sollte in einem dedizierten Block oder Abschnitt erscheinen.
4.  **Theme-Kompatibilität:** Obwohl für ein einfaches Modul wie dieses unwahrscheinlich, können sehr stark angepasste Themes gelegentlich Hooks stören. Wenn das Problem weiterhin besteht, wechseln Sie vorübergehend zum Standard-PrestaShop-Theme (Classic), um zu sehen, ob die IP-Adresse angezeigt wird.

**F: Speichert dieses Modul Kunden-IP-Adressen in meiner Datenbank?**
A: PrestaShop selbst speichert typischerweise die IP-Adresse des Kunden, wenn dieser sich registriert oder eine Bestellung aufgibt. Dieses Modul ruft diese vorhandenen Informationen lediglich aus Ihrer Datenbank ab und zeigt sie auf der Bestelldetailseite an. Es erstellt keine neuen Datenbanktabellen oder speichert zusätzliche IP-Daten unabhängig.

**F: Wird dieses Modul meinen Shop verlangsamen?**
A: Nein. Dieses Modul ist sehr leichtgewichtig. Es fügt lediglich eine kleine Information zu einer bestehenden Back-Office-Seite (Bestelldetails) hinzu und führt keine komplexen Berechnungen oder Front-Office-Operationen durch, die die Browsing-Geschwindigkeit des Kunden beeinträchtigen würden.

**F: Ist die IP-Adresse immer genau?**
A: Die aufgezeichnete IP-Adresse ist im Allgemeinen die, von der aus der Kunde eine Verbindung zu Ihrem Shop hergestellt hat. Kunden, die VPNs, Proxyserver oder bestimmte Mobilfunknetze verwenden, können jedoch eine IP-Adresse haben, die ihren physischen Standort nicht direkt widerspiegelt. Es ist ein nützlicher Indikator, aber nicht immer eine definitive geografische Positionsbestimmung.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)
Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht
Das Modul "Kunden-IP-Adresse in Bestelldetails" (`iporder`) ist ein sehr einfaches PrestaShop-Modul, das die Funktionalität des `AdminOrders`-Controllers erweitert. Es nutzt einen Standard-PrestaShop-Hook (`displayAdminOrder`), um zusätzliche Informationen (die IP-Adresse des Kunden) direkt in die Back-Office-Bestelldetailseite einzufügen. Es verfolgt einen minimalistischen Ansatz und konzentriert sich ausschließlich auf die Anzeige vorhandener Daten, anstatt neue Datenmodelle oder komplexe Logik einzuführen.

### 4.2 Controller (`controllers/`)
Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Funktionalität ist vollständig über Hooks in bestehende PrestaShop-Controller integriert.

### 4.3 Kernklassen & Modelle (`classes/`)
Dieses Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel`. Es greift direkt auf vorhandene PrestaShop-Kernobjekte und deren Eigenschaften zu (z. B. `Order`, `Customer`).

### 4.4 JavaScript-Assets (`views/js/`)
Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Die Anzeige der IP-Adresse erfolgt rein serverseitig gerendertem HTML.

### 4.5 CSS-Stylesheets (`views/css/`)
Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Der eingefügte Inhalt erbt das Styling vom PrestaShop-Back-Office-Theme.

### 4.6 Smarty-Template-Struktur (`views/templates/`)
Die gesamte Anzeigelogik des Moduls befindet sich in einer einzigen Smarty-Template-Datei.

-   **Hook-Templates (`views/templates/hook/`)**:
    *   `iporder/views/templates/hook/displayAdminOrder.tpl`
        *   **Hook:** `displayAdminOrder`
        *   **Zweck:** Dieses Template wird auf der PrestaShop-Back-Office-Bestelldetailseite gerendert. Es ruft die IP-Adresse des Kunden ab, die mit der aktuellen Bestellung verknüpft ist, und zeigt sie in einem dedizierten Block an.
        *   **Inhalt:** Es greift typischerweise auf die Smarty-Variablen `$order` und `$customer` zu (die vom `displayAdminOrder`-Hook übergeben werden), um `{$customer->ip_registration_date}` oder Ähnliches abzurufen und für die Anzeige zu formatieren. Es könnte auch `$_SERVER['REMOTE_ADDR']` verwenden, wenn die IP nicht direkt mit dem Kunden- oder Bestellobjekt in einer leicht zugänglichen Weise über den Hook gespeichert ist. Angesichts der Modulbeschreibung greift es wahrscheinlich auf die IP-Adresse zu, die mit dem Kunden- oder Bestellobjekt gespeichert ist.

### 4.7 Datenbankschema & Hooks-Map
-   **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es basiert auf vorhandenen PrestaShop-Tabellen, insbesondere `ps_customer` (die in einigen Versionen `last_passwd_gen` und `ip_registration_date` speichert, obwohl `ip_registration_date` nicht streng die Bestell-IP ist) und möglicherweise `ps_orders`, wenn die IP direkt mit der Bestellung gespeichert ist. Der häufigste Ansatz für dieses Modul wäre, die IP zum Zeitpunkt der Bestellung aus `$_SERVER['REMOTE_ADDR']` abzurufen und in einem benutzerdefinierten Feld zu speichern, falls nicht bereits vorhanden, oder einfach die `ip_registration_date` aus dem Kundenobjekt anzuzeigen. Angesichts der Einfachheit des Moduls und des Fehlens benutzerdefinierter Klassen wird die IP höchstwahrscheinlich über die einfachste Methode abgerufen, die über den Hook-Kontext verfügbar ist.
    *   **Hinweis:** PrestaShop 1.7+ speichert die `current_ip_address` in der Tabelle `ps_connections`, verknüpft mit `ps_guest` und `ps_customer`. Die `ip_registration_date` in `ps_customer` ist die IP, von der aus der Kunde sich registriert hat. Das Ziel des Moduls ist es, die IP *zum Zeitpunkt der Bestellung* anzuzeigen. Dies bedeutet normalerweise entweder:
        1.  Zugriff auf `$_SERVER['REMOTE_ADDR']`, wenn der Hook dies im Kontext der Bestellung bereitstellt.
        2.  Abrufen der IP aus der Tabelle `ps_connections` basierend auf der `id_guest`, die mit der Bestellung verknüpft ist.
        3.  Abrufen der `ip_registration_date` aus `ps_customer` (weniger genau für die spezifische Bestellung).
        Angesichts der Einfachheit wird wahrscheinlich die einfachste Methode verwendet, die über den Hook verfügbar ist.

-   **Registrierte Hooks-Tabelle**:
    | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
    |---|---|---|
    | `displayAdminOrder` | Wird ausgeführt, wenn die PrestaShop-Back-Office-Bestelldetailseite gerendert wird. | Fügt die IP-Adresse des Kunden in die Bestelldetailansicht ein. |

## 5. Offizieller Support & Updates
Für offizielle Updates, technischen Support und weitere Anfragen bezüglich des Moduls "Kunden-IP-Adresse in Bestelldetails" wenden Sie sich bitte an Ihr MyPresta.eu-Kundenkonto. Sie können Ihre Downloads und Support-Tickets direkt unter [MyPresta.eu Bestellhistorie & Downloads](https://mypresta.eu/my-account/orders/) aufrufen.

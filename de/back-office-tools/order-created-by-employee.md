---
title: "Bestellung von Mitarbeiter erstellt – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Bestellung von Mitarbeiter erstellt“ von MyPresta.eu."
sidebar:
  label: "Bestellung von Mitarbeiter erstellt – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Order created by employee auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/order-created-by-employee.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/order-created-by-employee/)
>
> ---


# Bestellung von Mitarbeiter erstellt

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL), die typischerweise in jeder PrestaShop-kompatiblen Hosting-Umgebung verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf die Schaltfläche „Konfigurieren“ zur Hauptkonfigurationsseite des Moduls.

Dieses Modul ist extrem einfach und effektiv konzipiert und erfordert minimale Konfiguration. Nach der Installation beginnt es automatisch mit der Erfassung der notwendigen Daten.

**Was dieser Bildschirm leistet:**
Diese Seite dient als Bestätigung, dass das Modul installiert und aktiv ist. Es werden keine konfigurierbaren Einstellungen angezeigt, da die Kernfunktionalität des Moduls (Protokollierung von Bestellungen, die von Mitarbeitern erstellt wurden) standardmäßig nach der Installation aktiviert ist.

**Auswirkung der Änderung dieser Einstellung:**
Auf diesem Bildschirm gibt es keine Einstellungen zu ändern. Die Funktionalität des Moduls ist nach der Installation „immer aktiv“.

**Empfohlener Wert:**
Keine Werte einzustellen. Stellen Sie einfach sicher, dass das Modul installiert und aktiviert ist.

**Händlerszenario / Beispiel:**
Sie haben das Modul gerade installiert. Sie navigieren zur Konfigurationsseite und sehen eine einfache Nachricht, die den Status bestätigt. Von diesem Zeitpunkt an wird jede neue Bestellung, die von einem Mitarbeiter über das PrestaShop Back Office erstellt wird, als solche gekennzeichnet. Wenn Sie die Details einer Bestellung anzeigen, sehen Sie einen neuen Abschnitt, der angibt, ob sie von einem Mitarbeiter erstellt wurde und welcher Mitarbeiter dies getan hat.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Dieses Modul fügt keine neuen dedizierten Menüpunkte oder komplexen Admin-Bildschirme hinzu. Seine Funktionalität integriert sich direkt in die bestehende PrestaShop-Bestelldetailseite.

**Bildschirmname & Menüpfad:**
Die von diesem Modul bereitgestellten Informationen werden direkt auf der **Bestelldetailseite** angezeigt.
Um darauf zuzugreifen:

1. Navigieren Sie in Ihrem PrestaShop Back Office zu **Bestellungen > Bestellungen**.
2. Klicken Sie auf eine beliebige Bestellung aus der Liste, um deren Details anzuzeigen.

**Verfügbare Aktionen & Einstellungen:**
Auf der Bestelldetailseite finden Sie einen neuen Abschnitt (typischerweise oben oder in einem dedizierten Block), der anzeigt, ob die Bestellung von einem Mitarbeiter erstellt wurde. Wenn ja, wird auch der Name des Mitarbeiters angezeigt, der sie erstellt hat.

**Auswirkung von Änderungen:**
Auf dieser Ansicht gibt es keine Aktionen oder Einstellungen zu ändern. Dieser Abschnitt ist rein informativ und liefert Ihnen die vom Modul gesammelten Daten.

**Empfohlener Workflow für die tägliche Shop-Verwaltung:**
Überprüfen Sie bei der Durchsicht von Bestellungen, insbesondere solchen, die ungewöhnlich erscheinen, oder bei der Durchführung interner Audits immer den Abschnitt „Bestellung von Mitarbeiter erstellt“ auf der Bestelldetailseite. Diese schnelle Überprüfung kann sofortigen Kontext über den Ursprung der Bestellung liefern und Ihnen helfen zu verstehen, ob es sich um einen direkten Kauf eines Kunden oder eine interne Eingabe handelte.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfigurationsseite | *(Keine konfigurierbaren Einstellungen)* | N/A | Bestätigt die Modulinstallation und -aktivierung. Die Modulfunktionalität ist immer aktiv. |
| Bestelldetailseite (Back Office) | Informationsblock „Bestellung von Mitarbeiter erstellt“ | N/A | Zeigt an, ob die Bestellung von einem Mitarbeiter erstellt wurde und dessen Namen. Rein informativ. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul installiert, sehe aber keine Änderungen an alten Bestellungen.**
A: Dieses Modul beginnt mit der Datenerfassung ab dem Zeitpunkt seiner Installation. Es kann nicht rückwirkend feststellen, ob frühere Bestellungen von einem Mitarbeiter erstellt wurden. Sie sehen die Informationen „Bestellung von Mitarbeiter erstellt“ nur bei Bestellungen, die *nach* der erfolgreichen Installation und Aktivierung des Moduls aufgegeben wurden.

**F: Ich habe eine Bestellung im Back Office erstellt, sehe aber die Mitarbeiterinformationen auf der Bestelldetailseite nicht.**
A: Stellen Sie zunächst sicher, dass das Modul installiert und aktiviert ist (prüfen Sie unter **Module > Modul-Manager**). Wenn ja, leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung**). Wenn das Problem weiterhin besteht, stellen Sie sicher, dass Sie eine Bestellung anzeigen, die *tatsächlich von einem Mitarbeiter* im Back Office *nach* der Installation des Moduls erstellt wurde.

**F: Beeinträchtigt dieses Modul die Leistung meines Shops?**
A: Nein, das Modul ist sehr leichtgewichtig. Es fügt lediglich ein kleines Datenelement während des Bestellvorgangs im Back Office hinzu und zeigt diese Daten auf der Bestelldetailseite an. Es hat keine Auswirkungen auf die Leistung Ihres Front Office oder das Kundenerlebnis.

**F: Kann ich die Funktionalität des Moduls deaktivieren, ohne es zu deinstallieren?**
A: Dieses Modul hat keinen Ein-/Ausschalter in seiner Konfiguration. Um seine Funktionalität zu stoppen, müssten Sie das Modul über den Modul-Manager deaktivieren oder deinstallieren. Angesichts seines Nutzens für die interne Nachverfolgung wird jedoch generell empfohlen, es aktiv zu lassen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Bestellung von Mitarbeiter erstellt“ (`logoe`) ist ein unkompliziertes PrestaShop-Modul, das die Kernfunktionalität von `Order` erweitern soll. Es funktioniert hauptsächlich, indem es sich in den Bestellvorgang im Back Office einklinkt, um die `id_employee` zu erfassen, die für die Bestellung verantwortlich ist. Diese Informationen werden dann auf der bestehenden Bestelldetailseite im Back Office angezeigt. Es folgt einem einfachen ereignisgesteuerten Muster unter Verwendung von PrestaShop-Hooks.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Die gesamte Logik wird innerhalb der Hauptmoduldatei und über Hooks abgewickelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen ein. Es interagiert direkt mit dem `Order`-Objekt und der `Configuration` für seine Einstellungen.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Die Formatierung der angezeigten Informationen ist typischerweise minimal und basiert auf vorhandenen PrestaShop Back Office-Stilen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul verwendet eine einzelne Template-Datei zur Anzeige von Informationen im Back Office.

- **Admin-Templates (`views/templates/admin/`)**:
  - `logoe/views/templates/admin/logoelog.tpl`: Dieses Template ist für das Rendern des Informationsblocks „Bestellung von Mitarbeiter erstellt“ auf der PrestaShop Back Office-Bestelldetailseite verantwortlich. Es zeigt typischerweise den Namen des Mitarbeiters an, wenn die Bestellung von einem Mitarbeiter erstellt wurde. Es wird wahrscheinlich über einen Hook wie `displayAdminOrder` oder `displayAdminOrderTabContent` gerendert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Das Modul erstellt keine neue dedizierte Datenbanktabelle. Stattdessen erweitert es die bestehende Tabelle `ps_orders` durch Hinzufügen einer neuen Spalte während der Installation.

  - `ps_orders`: Eine neue Spalte, wahrscheinlich `id_employee_created`, wird dieser Tabelle hinzugefügt, um die ID des Mitarbeiters zu speichern, der die Bestellung erstellt hat. Diese Spalte wäre `INT(10) UNSIGNED` und nullable, mit einem Standardwert von `NULL`.
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `actionOrderAdd` | Nachdem eine neue Bestellung erfolgreich in die Datenbank hinzugefügt wurde. | Dieser Hook ist entscheidend. Er wird verwendet, um die `id_employee` aus der aktuellen Back Office-Sitzung zu erfassen und die `id_employee_created`-Spalte der neu erstellten Bestellung in `ps_orders` zu aktualisieren. |
  | `displayAdminOrder` (oder ähnlich, z. B. `displayAdminOrderTabContent`, `displayAdminOrderMain`) | Wenn die Back Office-Bestelldetailseite gerendert wird. | Dieser Hook wird verwendet, um das Template `logoelog.tpl` in die Bestelldetailseite einzufügen und die `id_employee_created`-Informationen (z. B. Mitarbeitername) anzuzeigen. |

## 5. Offizieller Support & Updates

Für offiziellen Support, Modul-Updates und weitere Unterstützung besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, zeitnahen Support zu bieten und sicherzustellen, dass Ihr Modul perfekt funktioniert.

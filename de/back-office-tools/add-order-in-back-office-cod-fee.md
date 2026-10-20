---
title: "Bestellung im Back Office hinzufügen + Nachnahmegebühr - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Bestellung im Back Office hinzufügen + Nachnahmegebühr' von MyPresta.eu."
sidebar:
  label: "Bestellung im Back Office hinzufügen + Nachnahmegebühr - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Add order in back office + cod fee auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/add-order-in-back-office-cod-fee.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/add-order-in-back-office-cod-fee/)
>
> ---


# Bestellung im Back Office hinzufügen + Nachnahmegebühr

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).
- **Vorausgesetztes Modul**: Dieses Modul erfordert, dass ein „Nachnahme mit Gebühr“-Zahlungsmodul in Ihrem Shop installiert und konfiguriert ist. Dieses Modul *erweitert* die Funktionalität eines solchen Zahlungsmoduls innerhalb des Back Office.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dieses Modul hat eine sehr einfache Konfigurationsseite. Seine Hauptfunktion ist es, die Kernfunktionalität des Moduls zu aktivieren oder zu deaktivieren.

**Zugriff:** Back Office > Module > Modul-Manager > Suchen Sie nach „Bestellung im Back Office hinzufügen + Nachnahmegebühr“ > Klicken Sie auf „Konfigurieren“

#### **Modulfunktionalität aktivieren / deaktivieren**

- **Was diese Einstellung bewirkt:** Dies ist ein Standard-Umschalter, der steuert, ob die Funktionalität des Moduls aktiv oder inaktiv ist. Wenn aktiviert, fügt das Modul automatisch Nachnahmegebühren zu manuell erstellten Bestellungen im Back Office hinzu. Wenn deaktiviert, wird diese Funktionalität eingestellt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Modul überwacht aktiv den Bestellvorgang im Back Office. Wenn Sie eine Zahlungsart „Nachnahme mit Gebühr“ auswählen, während Sie eine Bestellung erstellen, wird die zugehörige Gebühr automatisch berechnet und zur Bestellsumme hinzugefügt.
  - *Wenn deaktiviert (NEIN):* Das Modul greift nicht in den Bestellvorgang im Back Office ein. Wenn Sie eine Zahlungsart „Nachnahme mit Gebühr“ auswählen, wird die Gebühr *nicht* automatisch hinzugefügt, und Sie müssten die Bestellsumme manuell anpassen, wenn Sie sie einschließen möchten.
- **Empfohlener Wert:** **JA**. Um den Hauptzweck des Moduls, die Automatisierung der Nachnahmegebührenerfassung, zu nutzen, sollte es aktiviert sein.
- **Händlerszenario / Beispiel:** Sie nehmen eine telefonische Bestellung von einem Kunden entgegen, der per Nachnahme bezahlen möchte. Sie gehen zu Back Office > Bestellungen > Neue Bestellung hinzufügen. Nachdem Sie Produkte hinzugefügt und den Kunden ausgewählt haben, wählen Sie Ihre Zahlungsart „Nachnahme mit Gebühr“. Wenn dieses Modul aktiviert ist, erscheint die Nachnahmegebühr sofort in der Bestellübersicht, um sicherzustellen, dass der Kunde korrekt belastet wird. Wenn deaktiviert, würde die Gebühr fehlen, was möglicherweise zu einer falschen Bestellsumme führen würde.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren / deaktivieren | JA | Steuert, ob das Modul automatisch Nachnahmegebühren zu manuell erstellten Back Office-Bestellungen hinzufügt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul installiert, aber die Nachnahmegebühr erscheint nicht, wenn ich eine Bestellung im Back Office erstelle.**
A:

1. **Modulstatus überprüfen:** Gehen Sie zu Module > Modul-Manager und stellen Sie sicher, dass „Bestellung im Back Office hinzufügen + Nachnahmegebühr“ installiert und **aktiviert** ist.
2. **Voraussetzung prüfen:** Dieses Modul *erfordert* ein separates „Nachnahme mit Gebühr“-Zahlungsmodul, das installiert und konfiguriert ist. Stellen Sie sicher, dass Sie ein solches Modul haben und es korrekt mit seinen Gebühren eingerichtet ist. Dieses Modul *erweitert* diese Funktionalität, es bietet nicht selbst den Nachnahmegebührenmechanismus.
3. **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass neue Modulfunktionalitäten sofort angezeigt werden. Gehen Sie zu Erweiterte Einstellungen > Leistung und klicken Sie oben rechts auf „Cache leeren“.
4. **Zahlungsmethode überprüfen:** Stellen Sie sicher, dass Sie die *spezifische* Zahlungsart „Nachnahme mit Gebühr“ auswählen, die Ihr anderes Modul bereitstellt, und nicht eine generische „Nachnahme“-Option ohne Gebühr.

**F: Wirkt sich dieses Modul auf Bestellungen aus, die von Kunden im Front-Office meines Shops aufgegeben werden?**
A: Nein, dieses Modul beeinflusst nur den Prozess der *manuellen* Erstellung von Bestellungen im PrestaShop Back Office. Es ändert nicht, wie Kunden Bestellungen aufgeben oder wie Gebühren im Front-End-Checkout-Prozess berechnet werden.

**F: Was ist, wenn ich mehrere „Nachnahme mit Gebühr“-Module habe?**
A: Dieses Modul ist so konzipiert, dass es sich in die Standardweise integriert, wie PrestaShop Zahlungsmodule und deren zugehörige Gebühren handhabt. Es sollte mit jedem „Nachnahme mit Gebühr“-Modul funktionieren, das seine Gebührenberechnung ordnungsgemäß im PrestaShop-Zahlungsframework registriert. Wenn Sie Probleme haben, wenden Sie sich bitte an den MyPresta.eu-Support.

**F: Erstellt dieses Modul selbst die Zahlungsoption „Nachnahme mit Gebühr“?**
A: Nein, das tut es nicht. Dieses Modul ist eine *Erweiterung* für ein bestehendes „Nachnahme mit Gebühr“-Zahlungsmodul. Sie müssen ein separates Zahlungsmodul installiert haben, das die eigentliche Nachnahme-Zahlungsmethode und deren Gebührenkonfiguration bereitstellt.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Bestellung im Back Office hinzufügen + Nachnahmegebühr“ ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, die Funktionalität des `AdminOrdersController` zu erweitern. Es erreicht seinen Zweck, indem es sich in spezifische Aktionen innerhalb des Bestellvorgangs im Back Office einklinkt, insbesondere wenn eine Zahlungsmethode ausgewählt oder aktualisiert wird. Seine Kernlogik befindet sich in der Hauptmoduldatei und nutzt PrestaShops Hook-System, um bestehendes Verhalten ohne direkte Änderung von Kerndateien zu modifizieren. Es ist auf das Vorhandensein eines separaten „Nachnahme mit Gebühr“-Zahlungsmoduls angewiesen, um die eigentliche Gebührenberechnungslogik bereitzustellen.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Funktionalität wird über Hooks in den bestehenden `AdminOrdersController` injiziert.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`-Instanzen. Die gesamte Logik ist in der Hauptmoduldatei enthalten.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Die Funktionalität wird serverseitig verarbeitet.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Seine Konfiguration wird durch die Standardmethode `getContent()` gehandhabt, die typischerweise PrestaShops Hilfsformulare verwendet.

### 4.7 Datenbankschema & Hooks-Map

**Datenbanktabellen**:
Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfiguration (z.B. Aktivierungs-/Deaktivierungsstatus) in der Standardtabelle `ps_configuration`, unter Verwendung eines Schlüssels wie `ADDORDERINBACKOFFICECODFEE_ENABLED`.

**Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin-Controller seine Medien-Assets setzt. | Wird verwendet, um bei Bedarf JS/CSS zu injizieren, obwohl dieses Modul es dafür nicht verwendet. Es ist ein gängiger Hook für serverseitige Modifikationen. |
| `actionAdminOrdersControllerSaveAfter` | Wird ausgeführt, nachdem eine Bestellung in `AdminOrdersController` gespeichert wurde. | Dies ist der primäre Hook, der vom Modul verwendet wird. Er ermöglicht es dem Modul, die neu gespeicherte Bestellung zu überprüfen, die ausgewählte Zahlungsmethode zu prüfen und, falls es sich um eine Nachnahme mit Gebühr handelt, die Gebühr anzuwenden. |
| `displayAdminOrder` | Wird auf der Bestelldetailseite im Back Office ausgeführt. | Könnte verwendet werden, um zusätzliche Informationen bezüglich der Nachnahmegebühr in der Bestellansicht anzuzeigen, obwohl die Kernfunktion des Moduls darin besteht, die Gebühr *hinzuzufügen*, nicht nur anzuzeigen. |

**Schlüssellogik innerhalb von `add-order-in-back-office-cod-fee.php`:**

Die Kernfunktionalität des Moduls ist wahrscheinlich in der Methode `hookActionAdminOrdersControllerSaveAfter` implementiert. Diese Methode würde:

1. Das gerade gespeicherte `Order`-Objekt abrufen.
2. Das für die Bestellung verwendete `PaymentModule` identifizieren.
3. Prüfen, ob das ausgewählte Zahlungsmodul vom Typ „Nachnahme mit Gebühr“ ist (dies beinhaltet typischerweise die Überprüfung des Modulnamens oder einer spezifischen Eigenschaft/Methode, die es exponiert).
4. Falls ja, würde es dann eine Methode dieses Zahlungsmoduls aufrufen (oder direkt basierend auf dessen Konfiguration berechnen), um die Nachnahmegebühr zu erhalten.
5. Schließlich würde es die Gesamtsumme der Bestellung aktualisieren, ein neues `OrderInvoice`-Detail hinzufügen (oder ein bestehendes ändern), um die Nachnahmegebühr widerzuspiegeln, und diese Änderungen in der Datenbank speichern. Dies könnte die Erstellung eines neuen `OrderPayment`-Eintrags oder die Anpassung der Felder `total_paid_tax_incl` und `total_paid_tax_excl` des `Order`-Objekts beinhalten.

Entwickler sollten sich bewusst sein, dass dieses Modul stark von der internen Struktur und dem Verhalten des „Nachnahme mit Gebühr“-Zahlungsmoduls abhängt, mit dem es interagiert. Alle benutzerdefinierten Nachnahme-Zahlungsmodule könnten Anpassungen oder spezifische Kompatibilitätsprüfungen erfordern.

## 5. Offizieller Support & Updates

Für offiziellen Support, Updates und weitere Informationen zum Modul „Bestellung im Back Office hinzufügen + Nachnahmegebühr“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) oder kontaktieren Sie direkt den MyPresta.eu-Support.

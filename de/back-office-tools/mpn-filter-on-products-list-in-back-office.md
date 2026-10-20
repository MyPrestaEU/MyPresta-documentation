---
title: "MPN-Filter in der Produktliste im Back Office – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'MPN-Filter in der Produktliste im Back Office' von MyPresta.eu."
sidebar:
  label: "MPN-Filter in der Produktliste im Back Office – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul MPN filter on products list in back office auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/mpn-filter-on-products-list-in-back-office.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/mpn-filter-on-products-list-in-back-office/)
>
> ---


# MPN-Filter in der Produktliste im Back Office

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend und auf den meisten Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dieses Modul ist als Plug-and-Play konzipiert. Es verfügt über keinen dedizierten Konfigurationsbildschirm mit einzustellenden Optionen. Nach der Installation integriert das Modul automatisch die MPN-Spalte und die Filterfunktionen in Ihre Produktliste.

Sie sehen nach der Installation eine Standard-Schaltfläche „Konfigurieren“, aber ein Klick darauf zeigt normalerweise eine einfache Meldung an, dass das Modul aktiv ist und keine weitere Konfiguration erfordert.

**So verwenden Sie das Modul nach der Installation:**

1. Navigieren Sie in Ihrem PrestaShop-Back Office zu **Katalog > Produkte**.
2. Sie sehen nun eine neue Spalte mit der Bezeichnung „MPN“ in Ihrer Produktliste.
3. Sie können auf den Spaltenkopf „MPN“ klicken, um Ihre Produkte in aufsteigender oder absteigender Reihenfolge nach MPN zu sortieren.
4. Oberhalb der Produktliste, im Filterbereich, finden Sie ein neues Eingabefeld unter der Spalte „MPN“. Sie können eine MPN (oder einen Teil einer MPN) in dieses Feld eingeben und die Eingabetaste drücken oder auf die Schaltfläche „Filtern“ klicken, um Ihre Produktliste nach dieser MPN zu filtern.

### 2.2 Kurzübersichtstabelle zur Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | (Keine konfigurierbaren Einstellungen) | N/A | Das Modul funktioniert automatisch nach der Installation und fügt die MPN-Spalte und den Filter zu Katalog > Produkte hinzu. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul installiert, sehe aber die MPN-Spalte nicht in meiner Produktliste.**
A: Stellen Sie zunächst sicher, dass Sie sich auf der Seite „Katalog > Produkte“ in Ihrem PrestaShop-Back Office befinden. Wenn es immer noch nicht sichtbar ist, versuchen Sie, Ihren PrestaShop-Cache zu leeren:
1. Gehen Sie zu **Erweiterte Einstellungen > Leistung**.
2. Klicken Sie oben rechts auf „Cache leeren“.
3. Leeren Sie auch den Cache Ihres Browsers.
4. Wenn das Problem weiterhin besteht, stellen Sie sicher, dass das Modul im Modul-Manager aktiviert ist.

**F: Kann ich dieses Modul verwenden, um MPN für Kunden im Front Office hinzuzufügen?**
A: Nein, dieses Modul ist ausschließlich für die Back-Office-Verwaltung gedacht. Es ändert das Front Office nicht und zeigt Kunden keine MPNs an. Für die Anzeige von MPNs im Front Office benötigen Sie ein separates Modul oder eine benutzerdefinierte Entwicklung.

**F: Erstellt dieses Modul neue Datenbankfelder für MPN?**
A: Nein, PrestaShop verfügt bereits über ein `mpn`-Feld in der Tabelle `ps_product`. Dieses Modul macht dieses vorhandene Feld lediglich in der Produktliste des Back Office sichtbar und filterbar. Es fügt keine neuen Datenbanktabellen oder -felder hinzu.

**F: Der Filter funktioniert nicht, oder die Spalte wird nicht richtig sortiert.**
A: Dies könnte ein Caching-Problem oder ein Konflikt mit einem anderen Modul sein, das die Produktliste ändert.
1. Leeren Sie den PrestaShop-Cache (wie oben beschrieben).
2. Wenn Sie andere Module haben, die die Seite „Katalog > Produkte“ stark anpassen, versuchen Sie, diese nacheinander vorübergehend zu deaktivieren, um einen Konflikt zu identifizieren.
3. Stellen Sie sicher, dass Ihre PrestaShop-Version vollständig mit der von Ihnen heruntergeladenen Modulversion kompatibel ist.

**F: Wie gebe oder bearbeite ich die MPN für ein Produkt?**
A: Sie bearbeiten die MPN direkt auf der Bearbeitungsseite des Produkts:
1. Gehen Sie zu **Katalog > Produkte**.
2. Klicken Sie neben dem Produkt, das Sie ändern möchten, auf „Bearbeiten“.
3. Navigieren Sie zur Registerkarte „Mengen“ (oder „Grundeinstellungen“ in älteren Versionen).
4. Dort finden Sie das Feld „MPN (Herstellerteilenummer)“. Geben Sie den Wert ein oder aktualisieren Sie ihn und speichern Sie das Produkt. Die neue MPN wird dann in der Produktliste angezeigt.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „MPN-Filter in der Produktliste im Back Office“ ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, die bestehende Funktionalität der Produktliste im Back Office zu erweitern. Dies wird durch das Überschreiben spezifischer Twig-Templates erreicht, die für das Rendern der Produktkatalogseite in PrestaShop 1.7.x, 8.x und 9.x verantwortlich sind. Es führt keine neuen Controller, Modelle oder komplexen JavaScript-/CSS-Assets ein. Seine Kernfunktion besteht darin, die MPN-Spalte und den zugehörigen Filter in die Standard-Produktlistenansicht zu injizieren.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Die gesamte Funktionalität wird durch Template-Overrides und PrestaShops Kernmodulmechanismen erreicht.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten PHP-Klassen oder `ObjectModel`-Definitionen ein. Es nutzt das vorhandene `Product` `ObjectModel` und dessen `mpn`-Feld.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Die Filter- und Sortierfunktion für die neue MPN-Spalte wird von PrestaShops bestehender DataTables.js-Implementierung für die Produktliste übernommen, die sich automatisch an neue Spalten anpasst.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Das Styling der neuen MPN-Spalte und des Filterfeldes wird direkt vom PrestaShop-Back-Office-Theme übernommen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Der primäre Mechanismus des Moduls besteht darin, die Kern-PrestaShop-Back-Office-Twig-Templates zu überschreiben, um die MPN-Spalte einzufügen.

- **`mpnmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`**:
  - **Zweck**: Dieses Template ist ein direktes Override des Kern-PrestaShop-Produktlisten-Templates (`admin-dev/themes/new-theme/template/catalog/products/list.html.twig` oder ähnlicher Pfad je nach PS-Version).
  - **Funktionalität**: Es modifiziert die Struktur der Produktliste, um den MPN-Spaltenkopf und das entsprechende Filter-Eingabefeld einzuschließen. Es stellt sicher, dass das MPN-Feld als sortierbare und filterbare Spalte innerhalb der DataTables-Konfiguration erkannt wird.
- **`mpnmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`**:
  - **Zweck**: Dieses Template ist ein direktes Override des Kern-PrestaShop-Produkttabellen-Templates (`admin-dev/themes/new-theme/template/catalog/products/products_table.html.twig` oder ähnlicher Pfad).
  - **Funktionalität**: Es modifiziert die Tabellenzeilen, um den tatsächlichen MPN-Wert für jedes Produkt in der neu hinzugefügten Spalte anzuzeigen. Es greift auf die Eigenschaft `product.mpn` aus den an das Template übergebenen Produktdaten zu.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt keine neuen Datenbanktabellen. Es basiert auf der vorhandenen `mpn`-Spalte innerhalb der Tabelle `ps_product` (oder `ps_product_shop` für shopspezifische MPNs, obwohl es typischerweise in `ps_product` ist).
- **Registrierte Hooks-Tabelle**: Dieses Modul registriert keine explizit neuen Hooks. Seine Funktionalität wird durch Template-Overrides erreicht. Obwohl es in seiner `install()`-Methode keine `displayHeader`, `displayRightColumn`, `actionValidateOrder` usw. verwendet, registriert es sich wahrscheinlich für Template-Overrides, was eine implizite Form des Einhakens in den Rendering-Prozess ist.

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und alle Anfragen bezüglich des Moduls „MPN-Filter in der Produktliste im Back Office“ wenden Sie sich bitte an Ihr MyPresta.eu-Kundenkonto. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zur Verfügung.

- **MyPresta.eu Bestellhistorie & Downloads**: <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Support-Kontakt**: <https://mypresta.eu/contact>

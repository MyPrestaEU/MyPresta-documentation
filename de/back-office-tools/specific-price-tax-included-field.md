---
title: "Spezifischer Preis inklusive Steuerfeld - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Spezifischer Preis inklusive Steuerfeld' von MyPresta.eu."
sidebar:
  label: "Spezifischer Preis inklusive Steuerfeld - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Specific price tax included field auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/specific-price-tax-included-field.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/specific-price-tax-included-field/)
>
> ---


# Spezifischer Preis inklusive Steuerfeld

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager neben dem Modul „Spezifischer Preis inklusive Steuerfeld“ auf „Konfigurieren“. Dies führt Sie zum Hauptkonfigurationsbildschirm des Moduls.

#### Allgemeine Einstellungen

- **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält typischerweise allgemeine Einstellungen im Zusammenhang mit Modul-Updates und Versionsprüfungen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul prüft regelmäßig auf neue Versionen, die von MyPresta.eu verfügbar sind, und benachrichtigt Sie im Back Office. Dies stellt sicher, dass Sie immer die neueste, sicherste und funktionsreichste Version verwenden.
  - *Wenn deaktiviert:* Das Modul führt keine automatischen Update-Prüfungen durch. Sie müssten manuell nach Updates suchen, indem Sie Ihr MyPresta.eu-Konto besuchen.
- **Empfohlener Wert:** **JA** (oder aktiviert). Wenn dies aktiviert bleibt, bleiben Sie über wichtige Updates und Fehlerbehebungen informiert.
- **Händlerszenario / Beispiel:** Sie möchten benachrichtigt werden, wenn eine neue Version des Moduls veröffentlicht wird, die Kompatibilitätskorrekturen für eine neue PrestaShop-Version oder Leistungsverbesserungen enthält. Wenn dies aktiviert bleibt, wird eine Benachrichtigung in Ihrem Back Office angezeigt.

### 2.2 Kurzübersichtstabelle der Konfiguration

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Update-Prüfungen (mypresta\_updates, update\_, updatev\_) | Aktiviert | Prüft regelmäßig auf neue Modulversionen und benachrichtigt Sie im Back Office. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul installiert, sehe aber das neue Feld „Preis inklusive Steuer“ nicht.**
A: Stellen Sie zunächst sicher, dass das Modul unter **Module > Modul-Manager** aktiviert ist. Navigieren Sie dann zu einer Produktseite, gehen Sie zum Tab „Preise“ und klicken Sie auf „Neuen spezifischen Preis hinzufügen“ oder „Bearbeiten“ eines bestehenden. Das neue Feld sollte innerhalb des Formulars zur Erstellung/Bearbeitung spezifischer Preise erscheinen. Wenn es immer noch nicht sichtbar ist, versuchen Sie, Ihren PrestaShop-Cache zu leeren (**Erweiterte Einstellungen > Leistung**, dann auf „Cache leeren“ klicken).

**F: Der berechnete Preis ohne Steuer scheint falsch zu sein.**
A: Das Modul basiert auf der dem Produkt zugewiesenen Steuerregel.
1. **Überprüfen Sie die Steuerregel des Produkts:** Gehen Sie zur Produktseite, Tab „Preise“, und überprüfen Sie, ob die korrekte „Steuerregel“ für das Produkt ausgewählt ist.
2. **Überprüfen Sie die Konfiguration der Steuerregel:** Gehen Sie zu **International > Steuern > Steuerregeln** und stellen Sie sicher, dass die für die ausgewählte Steuerregel definierten Steuersätze für Ihre Zielländer/Zonen korrekt sind.
3. **Cache leeren:** Nachdem Sie die Steuereinstellungen überprüft und möglicherweise korrigiert haben, leeren Sie Ihren PrestaShop-Cache.

**F: Beeinflusst dieses Modul bestehende spezifische Preise?**
A: Nein, dieses Modul fügt lediglich ein neues Eingabefeld zum Formular zur Erstellung/Bearbeitung spezifischer Preise hinzu. Es ändert oder berechnet keine spezifischen Preise neu, die vor seiner Installation oder mit dem Standardfeld „Preis exklusive Steuer“ erstellt wurden. Es bietet lediglich eine alternative Möglichkeit zur Eingabe neuer spezifischer Preise.

**F: Funktioniert dieses Modul mit meinem benutzerdefinierten Theme?**
A: Ja, dieses Modul ändert hauptsächlich ein Standard-PrestaShop Back Office-Formular. Es verwendet Standard-PrestaShop-Hooks und JavaScript, um das neue Feld einzufügen. Es ist sehr unwahrscheinlich, dass es mit Front-Office-Custom-Themes in Konflikt gerät, da es keine Front-Office-Anzeigekomponenten hat.

**F: Ich erhalte einen Fehler nach dem Update von PrestaShop.**
A: Nach jedem größeren PrestaShop-Update ist es eine gute Praxis:
1. Leeren Sie Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung**).
2. Suchen Sie in Ihrem MyPresta.eu-Konto nach einer neuen Version des Moduls „Spezifischer Preis inklusive Steuerfeld“, da Updates oft Kompatibilitätskorrekturen enthalten.
3. Wenn das Problem weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Spezifischer Preis inklusive Steuerfeld“ (`sptincl`) ist ein leichtgewichtiges PrestaShop 1.7.x-Modul, das die Verwaltungsoberfläche für spezifische Preise im Back Office verbessern soll. Es funktioniert hauptsächlich, indem es JavaScript in den Hook `actionAdminControllerSetMedia` injiziert, der dann das DOM des Formulars für spezifische Preise modifiziert, um das Feld „Preis inklusive Steuer“ hinzuzufügen und die notwendige clientseitige Berechnungslogik zu implementieren. Es führt keine neuen Datenbanktabellen, Controller oder komplexe Geschäftslogik auf der Serverseite ein, abgesehen von seiner Konfiguration.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller ein. Alle seine Funktionen werden über Hooks und JavaScript in bestehende PrestaShop-Admin-Seiten injiziert.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten PHP-Klassen oder `ObjectModel`-Definitionen ein. Seine Kernlogik befindet sich in der Hauptmoduldatei (`sptincl.php`).

### 4.4 JavaScript-Assets (`views/js/`)

- **`sptincl/views/js/sptincl.js`**
  - **Umfang:** Back-Office (insbesondere das Formular zur Erstellung/Bearbeitung spezifischer Preise).
  - **Zweck:** Dieses Skript ist für die primäre Funktionalität des Moduls verantwortlich.
    - **DOM-Manipulation:** Es fügt dem Formular für spezifische Preise dynamisch ein neues Eingabefeld für „Preis inklusive Steuer“ hinzu. Es ändert auch das Verhalten des bestehenden Feldes „Preis exklusive Steuer“.
    - **Event-Listener:** Es fügt Event-Listener (z. B. `keyup`, `change`) sowohl dem neuen Feld „Preis inklusive Steuer“ als auch dem bestehenden Feld „Preis exklusive Steuer“ sowie dem Steuerregel-Selektor hinzu.
    - **Berechnungslogik:** Wenn ein Benutzer einen Wert in das Feld „Preis inklusive Steuer“ eingibt oder die Steuerregel ändert, berechnet das Skript den entsprechenden Wert „Preis exklusive Steuer“ unter Verwendung des ausgewählten Steuersatzes. Umgekehrt, wenn das Feld „Preis exklusive Steuer“ geändert wird, berechnet es den Wert „Preis inklusive Steuer“.
    - **AJAX (Implizit):** Obwohl es keine direkten AJAX-Aufrufe durchführt, stützt es sich auf die im DOM verfügbaren oder durch PrestaShops bestehende Mechanismen abgerufenen Steuersätze, um seine Berechnungen durchzuführen. Es verwendet die Funktion `getTaxRate()` (die eine globale PrestaShop-JS-Funktion oder eine benutzerdefinierte innerhalb des Skripts definierte sein könnte), um den aktuellen Steuersatz basierend auf der ausgewählten Steuerregel abzurufen.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Es stützt sich auf die Standard-PrestaShop-Stile für Formularelemente, um eine nahtlose Integration in die Back Office-Benutzeroberfläche zu gewährleisten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul verwendet keine benutzerdefinierten Smarty-Template-Dateien. Seine Konfiguration wird direkt in der Methode `getContent()` der Hauptmodulklasse gehandhabt, und seine Front-End-Modifikationen sind rein JavaScript-gesteuert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Es speichert seine Konfigurationseinstellungen (wie `mypresta_updates`, `update_`, `updatev_`) in der Standardtabelle `ps_configuration`.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Admin Controller initialisiert wird und seine Medien-Assets (JS/CSS) festgelegt werden. | Dies ist der primäre Hook, der vom Modul verwendet wird. Er injiziert die JavaScript-Datei `sptincl.js` in das Back Office, speziell für das Formular zur Erstellung/Bearbeitung spezifischer Preise. Dies ermöglicht es dem Modul, das DOM des Formulars zu modifizieren und seine clientseitige Berechnungslogik hinzuzufügen. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Spezifischer Preis inklusive Steuerfeld“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.

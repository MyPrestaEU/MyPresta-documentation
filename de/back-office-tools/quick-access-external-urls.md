---
title: "Schnellzugriff - externe URLs - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Schnellzugriff - externe URLs' von MyPresta.eu."
sidebar:
  label: "Schnellzugriff - externe URLs - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Quick Access - external urls auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/quick-access-external-urls.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/quick-access-external-urls/)
>
> ---


# Schnellzugriff - externe URLs

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Dieses Modul integriert sich direkt in das bestehende PrestaShop-Schnellzugriffsverwaltungssystem. Es gibt keinen separaten Konfigurationsbildschirm für das Modul selbst. Stattdessen ändert es das Verhalten der Standard-Schnellzugriffsfunktion in Ihrem Back Office.

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Wenn Sie für das Modul „Schnellzugriff - externe URLs“ auf „Konfigurieren“ klicken, sehen Sie normalerweise eine einfache Bestätigung, dass das Modul installiert und aktiv ist. Es gibt keine spezifischen Einstellungen auf dieser Seite anzupassen, da das Modul durch das Überschreiben des PrestaShop-Kernverhaltens funktioniert.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

Die Funktionalität des Moduls wird über das Standard-PrestaShop-Schnellzugriffsmenü verwaltet.

**Bildschirmname & Menüpfad:**

- **Back Office > Verwaltung > Schnellzugriff** (oder **Konfigurieren > Erweiterte Einstellungen > Schnellzugriff** in älteren PrestaShop 1.7.x-Versionen).
- Sie können auch direkt über das Schnellzugriffsmenü selbst (das kleine Uhrensymbol oben in Ihrem Back Office) darauf zugreifen, indem Sie auf „Schnellzugriff verwalten“ klicken.

**Verfügbare Aktionen & Einstellungen:**
Auf diesem Bildschirm sehen Sie eine Liste Ihrer bestehenden Schnellzugriffslinks.

- **Einen neuen Schnellzugriffslink hinzufügen:**

  1. Klicken Sie auf die Schaltfläche **„Neuen Schnellzugriff hinzufügen“** (oder ähnlich, normalerweise ein Plus-Symbol).
  2. Sie sehen ein Formular mit Feldern wie:
     - **Name:** Der Text, der in Ihrem Schnellzugriffsmenü angezeigt wird (z. B. „DHL Versandportal“, „Stripe Dashboard“, „Google Analytics“).
     - **URL:** Dies ist das entscheidende Feld. **Mit diesem Modul können Sie jetzt JEDE gültige URL eingeben, einschließlich externer Websites.** Zum Beispiel:
       - `https://www.dhl.com/global-en/home/tracking.html`
       - `https://dashboard.stripe.com/`
       - `https://analytics.google.com/`
       - `https://mypresta.eu/`
     - **In neuem Fenster öffnen:** (Empfohlen: JA) Diese Option bestimmt, ob der Link in einem neuen Browser-Tab/Fenster geöffnet wird.
       - *Wenn aktiviert:* Der externe Link wird in einem neuen Tab geöffnet, wodurch Ihr PrestaShop Back Office im aktuellen Tab geöffnet bleibt. Dies wird im Allgemeinen für externe Links empfohlen, um ein Wegnavigieren von Ihrem Admin-Panel zu vermeiden.
       - *Wenn deaktiviert:* Der Link wird im selben Tab geöffnet und ersetzt Ihre PrestaShop Back Office-Ansicht.
  3. Klicken Sie auf **„Speichern“**.
- **Einen bestehenden Schnellzugriffslink bearbeiten:**

  1. Suchen Sie den Link in der Liste und klicken Sie auf das „Bearbeiten“-Symbol (Bleistift).
  2. Ändern Sie den Namen oder die URL nach Bedarf.
  3. Klicken Sie auf „Speichern“.
- **Einen Schnellzugriffslink löschen:**

  1. Suchen Sie den Link in der Liste und klicken Sie auf das „Löschen“-Symbol (Mülleimer).
  2. Bestätigen Sie die Löschung.

**Auswirkungen der Änderungen:**

- Alle Schnellzugriffslinks, die Sie auf diesem Bildschirm hinzufügen, bearbeiten oder löschen, werden sofort im Schnellzugriffsmenü (das Uhrensymbol) oben in Ihrem PrestaShop Back Office angezeigt.
- Wenn Sie auf einen Schnellzugriffslink klicken, der auf eine externe URL verweist, navigiert Ihr Browser zu dieser externen Website (entweder im selben Tab oder in einem neuen, abhängig von Ihrer Einstellung „In neuem Fenster öffnen“).

**Empfohlener Workflow für die tägliche Shop-Verwaltung:**

1. **Häufig verwendete externe Tools identifizieren:** Denken Sie an die Websites, die Sie täglich oder wöchentlich besuchen, um Ihren Shop zu verwalten (z. B. Versand, Zahlung, Marketing, Support, Lieferantenportale).
2. **Diese zum Schnellzugriff hinzufügen:** Gehen Sie zu **Verwaltung > Schnellzugriff** und fügen Sie jede externe URL mit einem klaren, beschreibenden Namen hinzu.
3. **„In neuem Fenster öffnen“ aktivieren:** Stellen Sie für alle externen Links „In neuem Fenster öffnen“ auf JA. Dies stellt sicher, dass Ihr PrestaShop Back Office geöffnet und zugänglich bleibt.
4. **Für Ihr Team organisieren:** Wenn Sie mehrere Admin-Benutzer haben, überlegen Sie, welche Schnelllinks für jede Rolle am vorteilhaftesten wären.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Back Office > Verwaltung > Schnellzugriff** | **Name** | Benutzerdefiniert | Text, der im Schnellzugriffsmenü angezeigt wird. |
|  | **URL** | Benutzerdefiniert (Externe URL) | Die Webadresse, auf die der Link verweist. **Dieses Modul ermöglicht hier externe URLs.** |
|  | **In neuem Fenster öffnen** | JA (für externe Links) | Bestimmt, ob der Link in einem neuen Browser-Tab/Fenster geöffnet wird. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe das Modul installiert, kann aber immer noch keine externen URLs zum Schnellzugriff hinzufügen. Was ist falsch?**
A1:

- **Cache leeren:** Leeren Sie nach der Installation immer Ihren PrestaShop-Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“.
- **Modulstatus überprüfen:** Stellen Sie sicher, dass das Modul aktiviert ist. Gehen Sie zu **Module > Modul-Manager**, suchen Sie nach „Schnellzugriff - externe URLs“ und überprüfen Sie, ob es aktiv ist.
- **Installation überprüfen:** Manchmal kann eine Installation stillschweigend fehlschlagen. Versuchen Sie, das Modul zu deinstallieren und neu zu installieren.
- **Browser-Cache:** Leeren Sie den Cache und die Cookies Ihres Browsers oder versuchen Sie, das Back Office in einem Inkognito-/privaten Fenster aufzurufen.

**F2: Meine Schnellzugriffslinks öffnen sich im selben Tab, auch für externe Websites. Wie behebe ich das?**
A2:

- Stellen Sie beim Hinzufügen oder Bearbeiten eines Schnellzugriffslinks sicher, dass die Option **„In neuem Fenster öffnen“** auf **JA** eingestellt ist. Diese Einstellung steuert, ob der Link in einem neuen Tab oder im aktuellen geöffnet wird.

**F3: Beeinflusst dieses Modul die Leistung oder SEO meines Shops?**
A3:

- Nein. Dieses Modul arbeitet vollständig innerhalb des PrestaShop Back Office. Es fügt dem Front Office Ihres Shops (was Kunden sehen) keinen Code, kein Styling oder keine Funktionalität hinzu. Daher hat es keine Auswirkungen auf die Ladezeit, SEO oder das Kundenerlebnis Ihres Shops.

**F4: Ich habe viele Schnellzugriffslinks hinzugefügt. Kann ich sie organisieren?**
A4:

- Die Standard-Schnellzugriffsfunktion von PrestaShop bietet keine erweiterte Organisation wie Ordner oder Kategorien. Sie können jedoch die Reihenfolge der Links steuern, indem Sie sie auf der Seite **Verwaltung > Schnellzugriff** per Drag & Drop verschieben. Sie können auch beschreibende Namen verwenden, um sie leicht identifizierbar zu machen.

**F5: Was passiert, wenn ich dieses Modul deinstalliere? Werden meine externen Schnellzugriffslinks verschwinden?**
A5:

- Wenn Sie dieses Modul deinstallieren, wird die Möglichkeit, *neue* externe URLs hinzuzufügen, entfernt. Bestehende externe URLs, die Sie hinzugefügt haben, während das Modul aktiv war, *könnten* weiterhin funktionieren, aber die Kernvalidierung von PrestaShop könnte deren Bearbeitung verhindern oder Probleme verursachen. Es ist am besten, das Modul installiert zu lassen, wenn Sie auf externe Schnellzugriffslinks angewiesen sind.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Schnellzugriff - externe URLs“ (`qae`) erreicht seine Funktionalität durch das Überschreiben von PrestaShop-Kernklassen und -Controllern. Insbesondere zielt es auf das `QuickAccess` `ObjectModel` und den `AdminQuickAccessesController` ab, um die Validierung zu entfernen, die Schnellzugriffs-URLs auf interne Back Office-Pfade beschränkt. Dies ist ein gängiges PrestaShop-Override-Muster.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Dieses Modul enthält keine Front-Office-Controller, da seine Funktionalität ausschließlich für das Back Office bestimmt ist.
- **Back-Office-Admin-Controller**:

  - **`qae/override/controllers/admin/AdminQuickAccessesController.php`**
    - **Klassenname**: `AdminQuickAccessesController` (überschreibt den Kern-`AdminQuickAccessesController`)
    - **Elternklasse**: `AdminController`
    - **Verantwortlichkeit**: Dieses Override ist entscheidend. Der ursprüngliche `AdminQuickAccessesController` enthält Logik zur Validierung des `url`-Feldes eines Schnellzugriffseintrags, um sicherzustellen, dass es sich um einen internen PrestaShop Back Office-Pfad handelt. Dieses Override modifiziert oder entfernt diese Validierung, wodurch externe URLs gespeichert werden können. Entwickler sollten die Methoden `postProcess()` oder `renderForm()` auf die spezifischen Änderungen bezüglich der URL-Validierung überprüfen.

### 4.3 Kernklassen & Modelle (`classes/`)

- **`qae/override/classes/index.php`**

  - Dies ist typischerweise eine leere Datei oder eine Datei, die nur `<?php exit; ?>` enthält, um die direkte Verzeichnisauflistung zu verhindern. Es ist eine Sicherheitsmaßnahme und kein Teil der Kernlogik des Moduls.
- **`qae/override/classes/Link.php`**

  - **Klassenname**: `Link` (überschreibt die Kern-`Link`-Klasse)
  - **Elternklasse**: `LinkCore`
  - **Verantwortlichkeit**: Die `Link`-Klasse ist für die Generierung von URLs in PrestaShop verantwortlich. Während die primäre Änderung für externe URLs in `QuickAccess` und `AdminQuickAccessesController` liegt, könnte ein Override von `Link` vorhanden sein, um sicherzustellen, dass alle internen URL-Generierungs- oder Validierungsmethoden, auf die `QuickAccess` angewiesen ist, mit der neuen externen URL-Zulassung kompatibel sind oder um unbeabsichtigte Nebenwirkungen zu verhindern. Entwickler sollten nach Modifikationen in Methoden suchen, die sich auf die URL-Validierung oder -Bereinigung beziehen.
- **`qae/override/classes/QuickAccess.php`**

  - **Klassenname**: `QuickAccess` (überschreibt das Kern-`QuickAccess` `ObjectModel`)
  - **Elternklasse**: `ObjectModel`
  - **Datenbanktabelle**: `ps_quick_access`
  - **`$definition`-Felder**: Diese Klasse definiert die Struktur eines Schnellzugriffseintrags, einschließlich `id_quick_access`, `name`, `url` und `new_window`.
  - **Wichtige öffentliche Methoden & Geschäftslogik**: Dieses Override ist fundamental. Das ursprüngliche `QuickAccess` `ObjectModel` enthält wahrscheinlich Validierungsregeln für das `url`-Feld innerhalb seiner `validateFields()`- oder `add()`/`update()`-Methoden. Dieses Override entfernt oder lockert diese Validierungsregeln, wodurch das `url`-Feld jede Zeichenfolge, einschließlich externer URLs, speichern kann, ohne Validierungsfehler auszulösen.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Die Änderungen sind rein serverseitig (PHP-Overrides).

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Die visuelle Darstellung des Schnellzugriffsmenüs wird durch das Standard-PrestaShop Back Office-Theme gehandhabt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält keine benutzerdefinierten Smarty-Template-Dateien. Es nutzt die vorhandenen Templates des PrestaShop Back Office für die Darstellung der Schnellzugriffsverwaltungsseite und des Schnellzugriffsmenüs selbst.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine neuen Datenbanktabellen. Es ändert das Verhalten, wie Daten für die bestehende Tabelle `ps_quick_access` gespeichert und validiert werden.
  - Konfigurationseinträge werden von diesem Modul nicht in `ps_configuration` gespeichert, da es hauptsächlich auf Klassen-/Controller-Overrides basiert.
- **Registrierte Hooks-Tabelle**:
  Dieses Modul registriert keine spezifischen Hooks im traditionellen Sinne (z. B. `displayHeader`, `actionValidateOrder`). Seine Funktionalität wird durch das PrestaShop-Override-System implementiert, das Kernklassen und -Controller direkt modifiziert, anstatt Code über Hooks einzuschleusen.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Schnellzugriff - externe URLs“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen gerne zur Verfügung.

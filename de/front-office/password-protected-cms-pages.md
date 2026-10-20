---
title: "Passwortgeschützte CMS-Seiten – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Passwortgeschützte CMS-Seiten“ von MyPresta.eu."
sidebar:
  label: "Passwortgeschützte CMS-Seiten – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Password protected CMS pages auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/password-protected-cms-pages.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/password-protected-cms-pages/)
>
> ---


# Passwortgeschützte CMS-Seiten

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Nach der Installation gelangen Sie durch Klicken auf „Konfigurieren“ des Moduls zum Hauptkonfigurationsbildschirm. Dieser Bildschirm dient hauptsächlich als Einstiegspunkt zum dedizierten Verwaltungsbereich für Ihre passwortgeschützten CMS-Seiten.

- **Was dieser Bildschirm tut:** Diese Seite bietet typischerweise eine kurze Übersicht oder einen direkten Link zur Hauptverwaltungsoberfläche, wo Sie Ihre passwortgeschützten CMS-Seiten tatsächlich einrichten und verwalten. Sie könnte auch allgemeine Einstellungen enthalten, falls das Modul welche hätte, aber für dieses Modul wird die Kernfunktionalität in einem separaten Bereich verwaltet.
- **Auswirkung von Einstellungsänderungen:** Alle hier vorgenommenen Einstellungen würden das globale Verhalten oder Aussehen des Moduls direkt beeinflussen.
- **Empfohlener Wert:** Befolgen Sie die Anweisungen auf dem Bildschirm, normalerweise durch Klicken auf eine Schaltfläche, um zur CMS-Seitenverwaltung zu gelangen.
- **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert. Sie werden wahrscheinlich eine Schaltfläche wie „Geschützte CMS-Seiten verwalten“ oder „CMS-Passwörter konfigurieren“ sehen. Durch Klicken darauf gelangen Sie zum dedizierten Bildschirm, um Ihre Seiten zu schützen.

### 2.2 Dedizierter Admin-Bildschirm: Geschützte CMS-Seiten verwalten (Back Office > Module > Passwortgeschützte CMS-Seiten > Konfigurieren > [Link zur Verwaltung])

Dies ist der primäre Bildschirm, auf dem Sie verwalten, welche CMS-Seiten geschützt sind und welche Passwörter sie haben. Sie gelangen zu diesem Bildschirm normalerweise, indem Sie auf einen Link oder eine Schaltfläche auf der Hauptkonfigurationsseite des Moduls klicken.

- **Bildschirmname & Menüpfad:** Sie finden typischerweise einen neuen Menüpunkt unter **Module > Modul-Manager > Passwortgeschützte CMS-Seiten > Konfigurieren**, der Sie dann zur Verwaltungsoberfläche weiterleitet. Die URL könnte etwa so aussehen: `admin/index.php?controller=AdminPcmsController`.
- **Verfügbare Aktionen & Einstellungen:**
  - **Auflistungstabelle:** Dieser Bildschirm zeigt eine Tabelle mit all Ihren vorhandenen CMS-Seiten an. Für jede Seite sehen Sie ihren Namen, ihre ID und ob sie derzeit geschützt ist.
  - **Schutz hinzufügen/bearbeiten:** Für jede CMS-Seite in der Liste finden Sie typischerweise eine Schaltfläche/ein Symbol „Bearbeiten“ oder „Konfigurieren“. Durch Klicken darauf öffnet sich ein Formular, in dem Sie:
    - **Schutz aktivieren/deaktivieren:** Ein einfacher Schalter (Ja/Nein), um den Passwortschutz für diese spezifische CMS-Seite ein- oder auszuschalten.
      - *Wenn aktiviert:* Die Seite erfordert ein Passwort, um ihren Inhalt im Front Office anzuzeigen.
      - *Wenn deaktiviert:* Die Seite ist als Standard-CMS-Seite öffentlich zugänglich.
      - *Empfohlener Wert:* „Ja“ für Seiten, die Sie schützen möchten, „Nein“ für öffentliche Seiten.
      - *Händlerszenario:* Sie möchten Ihre Seite „VIP-Angebote“ schützen, also aktivieren Sie den Schutz.
    - **Passwort festlegen:** Ein Eingabefeld, in dem Sie das Passwort für diese spezifische CMS-Seite definieren.
      - *Auswirkung der Änderung:* Dies ist das genaue Passwort, das Kunden eingeben müssen, um die Seite anzuzeigen.
      - *Empfohlener Wert:* Wählen Sie ein starkes, einzigartiges Passwort für jede geschützte Seite.
      - *Händlerszenario:* Sie legen „MEINGEHEIMERDEAL“ als Passwort für Ihre Seite „VIP-Angebote“ fest.
  - **Massenaktionen:** Je nach Modulversion kann es Optionen geben, den Schutz für mehrere Seiten gleichzeitig zu aktivieren/deaktivieren, obwohl die individuelle Seitenverwaltung für Passworteinstellungen häufiger ist.
- **Auswirkung von Änderungen:**
  - Wenn Sie den Schutz aktivieren und ein Passwort für eine CMS-Seite festlegen, wird diese Seite sofort im Front Office passwortgeschützt. Kunden, die ihre URL besuchen, sehen die Passwortabfrage.
  - Das Deaktivieren des Schutzes macht die Seite wieder öffentlich sichtbar.
- **Empfohlener Arbeitsablauf für die tägliche Shop-Verwaltung:**
  1. Entscheiden Sie, welche CMS-Seiten privat oder exklusiv sein sollen.
  2. Navigieren Sie zu diesem Bildschirm „Geschützte CMS-Seiten verwalten“.
  3. Suchen Sie die gewünschte CMS-Seite in der Liste.
  4. Klicken Sie auf „Bearbeiten“ oder die entsprechende Aktion für diese Seite.
  5. Aktivieren Sie den Passwortschutzschalter.
  6. Geben Sie ein starkes, einzigartiges Passwort ein.
  7. Speichern Sie Ihre Änderungen.
  8. Teilen Sie das Passwort Ihrem vorgesehenen Publikum mit.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Geschützte CMS-Seiten verwalten** | Schutz aktivieren/deaktivieren | Nein / Ja (nach Bedarf) | Steuert, ob eine bestimmte CMS-Seite ein Passwort erfordert, um angezeigt zu werden. |
| | Passwort für CMS-Seite | (Leer) / Starkes, einzigartiges Passwort | Die genaue Zeichenfolge, die Kunden eingeben müssen, um auf den geschützten Inhalt zuzugreifen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe ein Passwort festgelegt, aber die Seite ist immer noch ohne sichtbar. Was ist falsch?**
A:

1. **Überprüfen Sie, ob der Schutz aktiviert ist:** Gehen Sie zum Bildschirm „Geschützte CMS-Seiten verwalten“ und stellen Sie sicher, dass der Schalter „Schutz aktivieren“ für diese spezifische CMS-Seite auf „Ja“ steht.
2. **Leeren Sie den Browser-Cache:** Ihr Browser zeigt Ihnen möglicherweise eine zwischengespeicherte Version der Seite an. Versuchen Sie, den Cache Ihres Browsers zu leeren oder die Seite in einem Inkognito-/privaten Fenster zu öffnen.
3. **Leeren Sie den PrestaShop-Cache:** Gehen Sie im Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Dies stellt sicher, dass PrestaShop die neueste Konfiguration bereitstellt.

**F: Kann ich verschiedene Passwörter für verschiedene CMS-Seiten haben?**
A: Ja! Dieses Modul ist genau dafür konzipiert. Jede CMS-Seite kann ihr eigenes einzigartiges Passwort haben, sodass Sie mehrere Ebenen geschützter Inhalte erstellen können.

**F: Was passiert, wenn ein Kunde das falsche Passwort eingibt?**
A: Das Modul zeigt eine Fehlermeldung an (z. B. „Falsches Passwort. Bitte versuchen Sie es erneut.“) und das Passworteingabeformular erscheint erneut, sodass der Kunde das Passwort erneut eingeben kann.

**F: Kann ich das Aussehen des Passworteingabeformulars anpassen?**
A: Das Modul verwendet eine grundlegende Formatierung für das Passwortformular. Für fortgeschrittene Anpassungen benötigen Sie einen Webmaster oder Entwickler, um die CSS-Datei des Moduls (`css.css`) zu ändern oder dessen Template (`cms.tpl`) zu überschreiben.

**F: Ich habe mein PrestaShop-Theme aktualisiert, und jetzt sieht das Passwortformular seltsam aus. Was soll ich tun?**
A: Benutzerdefinierte Themes haben manchmal ihre eigene Formatierung, die mit der Anzeige von Modulen in Konflikt geraten kann.

1. **Leeren Sie den PrestaShop-Cache:** Versuchen Sie dies immer zuerst (**Erweiterte Einstellungen > Leistung > Cache leeren**).
2. **Kontaktieren Sie Ihren Theme-Entwickler:** Er hat möglicherweise spezifische Anweisungen zur Modulkompatibilität.
3. **Konsultieren Sie einen Webmaster:** Ein Entwickler kann das CSS und HTML überprüfen, um Styling-Konflikte zu identifizieren und zu beheben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Passwortgeschützte CMS-Seiten“ (`passcms`) funktioniert hauptsächlich durch das Überschreiben des Kern-`CmsController`, um Anfragen für CMS-Seiten abzufangen. Wenn eine geschützte CMS-Seite angefordert wird, prüft es auf ein gültiges Passwort in der Session. Wenn kein gültiges Passwort gefunden wird, rendert es ein Passworteingabeformular anstelle des tatsächlichen CMS-Inhalts. Das Modul verwendet einen dedizierten Admin-Controller (`AdminPcmsController`) zur Verwaltung der Passworteinstellungen für jede CMS-Seite.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `passcms/override/controllers/front/CmsController.php`
    - **Klassenname & Elternklasse**: `CmsController` (überschreibt den Kern-`CmsController`)
    - **Verantwortlichkeit**: Dies ist der Kern der Front-Office-Funktionalität. Es fängt die Methode `initContent()` des ursprünglichen `CmsController` ab. Es prüft, ob die angeforderte CMS-Seite (identifiziert durch `id_cms`) als passwortgeschützt konfiguriert ist. Wenn dies der Fall ist und kein gültiges Passwort in der Session vorhanden ist, rendert es das Template `cms.tpl` mit dem Passworteingabeformular. Es verarbeitet auch die POST-Anfrage zur Passworteingabe, validiert diese gegen das gespeicherte Passwort und setzt bei Erfolg eine Session-Variable.
  - `passcms/override/controllers/front/index.php`
    - **Klassenname & Elternklasse**: Keine Klasse, typischerweise eine leere Datei oder eine grundlegende Sicherheitsmaßnahme, um direkte Verzeichnisauflistungen zu verhindern.
    - **Verantwortlichkeit**: Standard-PrestaShop-Praxis für `override`-Verzeichnisse.
- **Back-Office-Admin-Controller**:

  - `passcms/controllers/admin/AdminPcmsController.php`
    - **Tab-Name und verwaltete Entität**: Verwaltet die Passwortschutz-Einstellungen für einzelne CMS-Seiten. Dieser Controller erweitert `ModuleAdminController` und bietet die Schnittstelle zum Auflisten von CMS-Seiten und zum Konfigurieren ihrer Passwörter. Er verarbeitet die CRUD-Operationen für die Entität `pcms` (obwohl kein explizites `ObjectModel` aufgeführt ist, interagiert es wahrscheinlich direkt mit `ps_configuration` oder einer benutzerdefinierten Tabelle zur Passwortspeicherung). Es rendert die Rasteransicht der CMS-Seiten und das Formular zum Bearbeiten der Passworteinstellungen.
  - `passcms/controllers/admin/index.php`
    - **Klassenname & Elternklasse**: Keine Klasse, typischerweise eine leere Datei oder eine grundlegende Sicherheitsmaßnahme, um direkte Verzeichnisauflistungen zu verhindern.
    - **Verantwortlichkeit**: Standard-PrestaShop-Praxis für Controller-Verzeichnisse.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` auf. Dies deutet darauf hin, dass das Modul seine Konfiguration wahrscheinlich direkt in der Tabelle `ps_configuration` speichert, wobei Schlüssel wie `PCMS_PASSWORD_ID_CMS_X` verwendet werden, wobei `X` die `id_cms` ist, oder es könnte eine benutzerdefinierte Tabelle verwenden, die direkt vom `AdminPcmsController` ohne ein dediziertes `ObjectModel` verwaltet wird.

### 4.4 JavaScript-Assets (`views/js/`)

Das Moduldossier weist keine benutzerdefinierten JavaScript-Dateien auf. Die Passwortübermittlung wird wahrscheinlich über ein Standard-HTML-Formular-POST oder einfaches Inline-JS gehandhabt, falls dynamisches Verhalten vorhanden ist.

### 4.5 CSS-Stylesheets (`views/css/`)

- `passcms/css.css`
  - **Umfang**: Front-Office-Kunden-Styling.
  - **Wichtige UI-Komponenten und Container, die es stylt**: Diese Datei enthält das grundlegende Styling für das Passworteingabeformular, das auf geschützten CMS-Seiten angezeigt wird. Es zielt wahrscheinlich auf Elemente wie den Formularcontainer, das Eingabefeld und die Schaltfläche zum Absenden ab.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können**: Entwickler können das gerenderte HTML des Passwortformulars überprüfen, um spezifische Klassen (z. B. `.passcms-form`, `.passcms-input`, `.passcms-button`, `.passcms-error`) zu identifizieren und diese in der `custom.css` oder `theme.css` ihres Themes zu überschreiben, um sie an das Branding des Shops anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Admin-Templates (`views/templates/admin/`)**:

  - `passcms/admin.tpl`
    - **Zweck**: Dieses Template wird wahrscheinlich für die Hauptkonfigurationsseite des Moduls verwendet, um den Einstiegspunkt oder allgemeine Informationen bereitzustellen und möglicherweise auf die Verwaltungsoberfläche des `AdminPcmsController` zu verlinken.
  - `passcms/views/templates/admin/script.tpl`
    - **Zweck**: Dieses Template könnte Inline-JavaScript oder Smarty-Variablen enthalten, die im Back Office für den `AdminPcmsController` gerendert werden, um dynamisches Verhalten oder die Datenübergabe zu handhaben.
- **Front-Office-Templates (`views/templates/front/`)**:

  - `passcms/views/templates/front/cms.tpl`
    - **Zweck**: Dies ist das entscheidende Template, das vom überschriebenen `CmsController` gerendert wird, wenn eine geschützte CMS-Seite ohne gültiges Passwort aufgerufen wird. Es enthält die HTML-Struktur für das Passworteingabeformular, einschließlich des Eingabefeldes, der Absende-Schaltfläche und etwaiger Fehlermeldungen.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt laut Dossier keine explizite benutzerdefinierte SQL-Tabelle. Es ist sehr wahrscheinlich, dass die Passworteinstellungen für jede CMS-Seite in der Tabelle `ps_configuration` unter Verwendung eindeutiger Konfigurationsschlüssel gespeichert werden, z. B. `PCMS_PASSWORD_ID_CMS_X`, wobei `X` die `id_cms` ist.
  - `ps_configuration`: Speichert Modulkonfigurationswerte, einschließlich potenziell der Passwörter für jede CMS-Seite.
- **Registrierte Hooks-Tabelle**:
  Das Modul arbeitet hauptsächlich über Controller-Overrides und nicht über traditionelle Hooks für seine Kernfunktionalität. Es könnte jedoch einige Standard-Hooks für die allgemeine Modulintegration oder Anzeige registrieren.

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Wird im `<head>`-Bereich der Back-Office-Seiten gerendert. | Wird verwendet, um CSS (`css.css`) oder JS für die `AdminPcmsController`-Schnittstelle einzubinden. |
  | `displayHeader` | Wird im `<head>`-Bereich der Front-Office-Seiten gerendert. | Könnte verwendet werden, um Front-Office-CSS (`css.css`) oder JS bei Bedarf global einzubinden, obwohl es wahrscheinlicher ist, dass es bedingt durch den `CmsController`-Override geladen wird. |
  | `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien-Assets festlegt. | Alternative zu `displayHeader` zum bedingten Laden von Assets basierend auf dem aktuellen Controller. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Passwortgeschützte CMS-Seiten“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.

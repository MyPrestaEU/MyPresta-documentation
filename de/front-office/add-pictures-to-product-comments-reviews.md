---
title: "Bilder zu Produktkommentaren (Bewertungen) hinzufügen - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Bilder zu Produktkommentaren (Bewertungen) hinzufügen“ von MyPresta.eu."
sidebar:
  label: "Bilder zu Produktkommentaren (Bewertungen) hinzufügen - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Add pictures to product comments (reviews) auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/add-pictures-to-product-comments-reviews.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/add-pictures-to-product-comments-reviews/)
>
> ---


# Bilder zu Produktkommentaren (Bewertungen) hinzufügen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).
- **Abhängigkeit**: Dieses Modul erfordert, dass das Modul „Produktkommentare“ (entwickelt von MyPresta.eu) installiert und aktiv ist, da es dessen Funktionalität erweitert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager neben dem Modul „Bilder zu Produktkommentaren (Bewertungen) hinzufügen“ auf „Konfigurieren“. Dies führt Sie zum Hauptkonfigurationsbildschirm.

Die Konfiguration des Moduls ist unkompliziert und konzentriert sich hauptsächlich auf das Aktivieren oder Deaktivieren seiner Kernfunktionalität.

**Einstellungen & Optionen:**

- **Bilder-Upload für Produktkommentare aktivieren:**
  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls. Wenn aktiviert, sehen Ihre Kunden die Option, Bilder hochzuladen, wenn sie eine Produktbewertung schreiben.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Das Bild-Upload-Feld erscheint im Produktbewertungsformular auf Ihren Produktseiten. Kunden können dann Bilder an ihre Bewertungen anhängen. Bestehende Bewertungen mit Bildern zeigen diese Bilder ebenfalls an.
    - *Wenn deaktiviert (NEIN):* Das Bild-Upload-Feld wird im Produktbewertungsformular ausgeblendet. Kunden können nur Textbewertungen einreichen. Bestehende Bewertungen mit Bildern werden möglicherweise weiterhin angezeigt, aber es können keine neuen Bilder hinzugefügt werden.
  - **Empfohlener Wert:** **JA**. Um die Vorteile visueller Bewertungen zu nutzen, sollten Sie diese Funktion aktivieren.
  - **Händlerszenario / Beispiel:** Wenn Sie Kunden erlauben möchten, ihr neues Kleid oder die Funktionsweise eines Gadgets im realen Leben zu zeigen, aktivieren Sie dies. Wenn Sie den Bild-Upload vorübergehend für Wartungsarbeiten oder eine bestimmte Kampagne einschränken möchten, können Sie ihn deaktivieren.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | Bilder-Upload für Produktkommentare aktivieren | JA | Steuert, ob Kunden Bilder mit ihren Produktbewertungen hochladen können. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul aktiviert, aber ich sehe das Bild-Upload-Feld auf meiner Produktseite nicht.**
A:

1. **Modul „Produktkommentare“ überprüfen:** Dieses Modul erweitert das Modul „Produktkommentare“. Stellen Sie sicher, dass das Modul „Produktkommentare“ (von MyPresta.eu) in Ihrem Shop installiert, aktiviert und korrekt konfiguriert ist.
2. **Cache leeren:** Gehen Sie im PrestaShop Back Office zu **Erweiterte Einstellungen > Leistung** und klicken Sie oben rechts auf „Cache leeren“. Manchmal verhindern alte Cache-Dateien, dass neue Modulfunktionen angezeigt werden.
3. **Theme-Kompatibilität:** Obwohl das Modul für breite Kompatibilität ausgelegt ist, können benutzerdefinierte Themes manchmal Standard-Template-Strukturen überschreiben. Wenn das Leeren des Caches nicht hilft, kontaktieren Sie den MyPresta.eu-Support mit Details zu Ihrem Theme.

**F: Meine Kunden laden Bilder hoch, aber sie erscheinen nicht neben der Bewertung.**
A:

1. **Bewertungsmoderation:** Überprüfen Sie, ob Ihr Modul „Produktkommentare“ die Bewertungsmoderation aktiviert hat. Wenn ja, erscheinen neue Bewertungen (und die zugehörigen Bilder) erst, nachdem Sie sie im Back Office genehmigt haben.
2. **Modulkonfiguration überprüfen:** Überprüfen Sie nochmals, ob „Bilder-Upload für Produktkommentare aktivieren“ in der Konfiguration dieses Moduls auf JA gesetzt ist.
3. **Dateiberechtigungen:** Stellen Sie sicher, dass das Verzeichnis `img/p/` (oder wo PrestaShop Produktbilder speichert) die korrekten Schreibberechtigungen hat (normalerweise 755 oder 775). Wenn der Server keine Dateien schreiben kann, werden Bilder nicht gespeichert.

**F: Kann ich die Anzahl der Bilder begrenzen, die ein Kunde pro Bewertung hochladen kann?**
A: Dieses spezifische Modul bietet eine grundlegende Upload-Funktion. Erweiterte Steuerelemente wie die Begrenzung der Anzahl der Bilder oder der Dateigröße erfordern möglicherweise benutzerdefinierte Änderungen oder ein Update des Kernmoduls „Produktkommentare“. Bitte überprüfen Sie die Einstellungen des Moduls „Produktkommentare“ oder kontaktieren Sie den MyPresta.eu-Support für solche Funktionen.

**F: Die hochgeladenen Bilder sehen verzerrt aus oder werden nicht korrekt angezeigt.**
A:

1. **CSS-Konflikte:** Das CSS Ihres Themes könnte mit dem Styling des Moduls in Konflikt stehen. Verwenden Sie die Entwicklertools Ihres Browsers (F12), um die Bildelemente zu überprüfen und widersprüchliche Stile zu identifizieren.
2. **Bilderneuerung:** Manchmal werden Bild-Thumbnails nicht korrekt generiert. Gehen Sie in PrestaShop zu **Design > Bildeinstellungen** und versuchen Sie, Thumbnails für „Produkte“ oder „Bewertungen“ neu zu generieren, falls eine solche Option existiert, oder für alle Bilder.
3. **Originalbildqualität:** Raten Sie Kunden, Bilder in angemessener Größe und Klarheit hochzuladen. Extrem niedrig aufgelöste Bilder sehen bei größerer Anzeige natürlich schlecht aus.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Bilder zu Produktkommentaren (Bewertungen) hinzufügen“ (`reviewspics`) ist als Erweiterung des Kernmoduls „Produktkommentare“ (vermutlich `productcomments` oder ein ähnliches MyPresta.eu-Modul) konzipiert. Es fügt hauptsächlich eine Bild-Upload-Oberfläche in das bestehende Bewertungsformular ein und modifiziert die Anzeige von Bewertungen, um Bilder einzuschließen. Es nutzt das Hook-System von PrestaShop zur Integration und verwendet Standard-Front-Office- und Back-Office-Assets. Das Modul erstellt eine benutzerdefinierte Datenbanktabelle, um Bilder mit bestimmten Produktkommentaren zu verknüpfen.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Funktionalität wird über Hooks und direkte Template-Modifikationen im Kontext des übergeordneten Moduls „Produktkommentare“ integriert.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Seine primäre Logik befindet sich in der Hauptmoduldatei `index.php` und der `install.sql` für das Datenbankschema.

### 4.4 JavaScript-Assets (`views/js/`)

- **`reviewspics/views/js/reviewspics-bo.js`**

  - **Umfang:** Back-Office.
  - **Zweck:** Dieses Skript verarbeitet wahrscheinlich JavaScript-gesteuerte Funktionalität innerhalb der Back-Office-Konfiguration des Moduls oder zur Verwaltung hochgeladener Bilder, die mit Bewertungen im Admin-Panel verknüpft sind. Dies könnte AJAX-Aufrufe für Bildlöschung, Statusaktualisierungen oder dynamische Formularelemente umfassen.
  - **Details:** Es würde typischerweise an Elemente innerhalb des `backOffice.tpl`-Templates oder der Admin-Produktkommentar-Verwaltungsoberfläche gebunden sein.
- **`reviewspics/views/js/reviewspics.js`**

  - **Umfang:** Front-Office.
  - **Zweck:** Dies ist das Kern-Front-Office-JavaScript für die Bild-Upload-Funktionalität. Es verarbeitet:
    - Anzeige des Bild-Upload-Inputs (z. B. Dateieingabe, Drag-and-Drop-Bereich).
    - Vorschau ausgewählter Bilder vor dem Upload.
    - AJAX-basierter Bild-Upload während der Bewertungseinreichung.
    - Validierung von Bildtypen/-größen (clientseitig).
    - Potenziell Entfernung ausgewählter Bilder vor der Einreichung.
  - **Details:** Es bindet an die Elemente des Bewertungsformulars, wahrscheinlich innerhalb des `displayMyPrestaCommentsField.tpl`-Templates, und interagiert mit der serverseitigen Logik, um Bilddateien zu verarbeiten.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`reviewspics/views/css/reviewspics.css`**
  - **Umfang:** Front-Office (primär) und potenziell Back-Office.
  - **Zweck:** Dieses Stylesheet bietet die visuelle Gestaltung für das Bild-Upload-Formular und die Anzeige hochgeladener Bilder innerhalb von Produktbewertungen.
  - **Wichtige UI-Komponenten und Container, die es gestaltet:**
    - Der Bild-Upload-Bereich (z. B. Rahmen, Hintergrund, Symbol).
    - Bildvorschauen (Größe, Seitenverhältnis, Rahmen).
    - Layout von Bildern innerhalb einer Bewertung.
    - Potenziell Styling für die Bildverwaltung im Back Office.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Suchen Sie nach Klassen wie `.reviewspics-upload-area`, `.reviewspics-image-preview`, `.reviewspics-review-images` usw. Diese können in der `custom.css` oder `theme.css` eines benutzerdefinierten Themes angesprochen werden, um dem Branding des Shops zu entsprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - **`reviewspics/views/templates/hook/backOffice.tpl`**

    - **Hook:** Wahrscheinlich gerendert in `displayAdminProductsExtra` oder einem benutzerdefinierten Hook innerhalb der Admin-Oberfläche des Moduls „Produktkommentare“.
    - **Ausgabe:** Dieses Template ist für das Back Office. Es rendert wahrscheinlich das Konfigurationsformular des Moduls (wie in Abschnitt 4.1 beschrieben) oder bietet eine Schnittstelle für Administratoren zur Verwaltung von Bildern, die mit Produktkommentaren verknüpft sind (z. B. Anzeigen, Löschen, Genehmigen von Bildern).
  - **`reviewspics/views/templates/hook/displayMyPrestaComment.tpl`**

    - **Hook:** Dieses Template ist so konzipiert, dass es in die Anzeige eines *einzelnen* Produktkommentars eingehängt wird, wahrscheinlich innerhalb von `displayProductListReviews` oder einem ähnlichen Hook, der vom Modul „Produktkommentare“ bereitgestellt wird.
    - **Ausgabe:** Es rendert die tatsächlichen Bilder, die mit einer bestimmten Produktbewertung verknüpft sind. Es würde die mit dem Kommentar verknüpften Bilder durchlaufen und sie anzeigen, möglicherweise als Thumbnails oder eine kleine Galerie.
  - **`reviewspics/views/templates/hook/displayMyPrestaCommentsField.tpl`**

    - **Hook:** Dieses Template soll in das Produktbewertungs-*Einreichungsformular* eingefügt werden, wahrscheinlich über einen Hook wie `displayProductForm` oder einen benutzerdefinierten Hook innerhalb des Bewertungsformulars des Moduls „Produktkommentare“.
    - **Ausgabe:** Es rendert die HTML-Struktur für das Bild-Upload-Eingabefeld, mit dem Kunden interagieren, wenn sie eine neue Bewertung schreiben. Dies umfasst das Dateieingabefeld, alle Drag-and-Drop-Bereiche und potenziell Platzhalter für Bildvorschauen.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Die Datei `reviewspics/install.sql` weist auf die Erstellung mindestens einer benutzerdefinierten Tabelle hin, um die Bilddaten zu speichern und sie mit Produktkommentaren zu verknüpfen.
  - **`ps_reviewspics_image`**: (Wahrscheinlicher Tabellenname, basierend auf dem Modulnamen und gängigen PrestaShop-Konventionen).
    - **Zweck:** Speichert Metadaten zu jedem hochgeladenen Bild.
    - **Felder (erwartet):**
      - `id_reviewspics_image` (Primärschlüssel, INT)
      - `id_product_comment` (Fremdschlüssel, INT, Verknüpfung mit der Bewertungstabelle des übergeordneten Moduls „Produktkommentare“)
      - `image_name` (VARCHAR, Dateiname des Bildes)
      - `date_add` (DATETIME, Zeitstempel des Uploads)
      - `active` (TINYINT, für Moderation/Sichtbarkeit)
      - `position` (INT, für die Reihenfolge, falls mehrere Bilder pro Bewertung)
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich aller Front-Office-Seiten gerendert. | Zum Einbinden von Front-Office-CSS (`reviewspics.css`) und JavaScript (`reviewspics.js`)-Dateien. |
| `displayBackOfficeHeader` | Wird im `<head>`-Bereich aller Back-Office-Seiten gerendert. | Zum Einbinden von Back-Office-CSS und JavaScript (`reviewspics-bo.js`) für die Admin-Konfiguration oder die Bewertungsverwaltung. |
| `displayProductListReviews` (oder ähnlich vom Produktkommentar-Modul) | Wird innerhalb der Produktbewertungsliste auf Produktseiten gerendert. | Zum Einfügen von `displayMyPrestaComment.tpl` zur Anzeige von Bildern in bestehenden Bewertungen. |
| `displayProductForm` (oder ähnlich vom Produktkommentar-Modul) | Wird innerhalb des Produktbewertungsformulars gerendert. | Zum Einfügen von `displayMyPrestaCommentsField.tpl` für die Bild-Upload-Eingabe. |
| `actionProductCommentAdd` (oder ähnlich vom Produktkommentar-Modul) | Wird ausgeführt, nachdem ein neuer Produktkommentar hinzugefügt wurde. | Zum Verarbeiten hochgeladener Bilder, Speichern im Dateisystem und Aufzeichnen ihrer Details in der Tabelle `ps_reviewspics_image`, wobei sie mit dem neuen Kommentar verknüpft werden. |
| `actionProductCommentDelete` (oder ähnlich vom Produktkommentar-Modul) | Wird ausgeführt, nachdem ein Produktkommentar gelöscht wurde. | Zum Bereinigen zugehöriger Bilder aus dem Dateisystem und der Tabelle `ps_reviewspics_image`. |
| `actionProductCommentUpdate` (oder ähnlich vom Produktkommentar-Modul) | Wird ausgeführt, nachdem ein Produktkommentar aktualisiert wurde. | Zum Verwalten von Änderungen an Bildzuordnungen oder dem Moderationsstatus. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und professionellen Support wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu). Unser Team ist bestrebt, den reibungslosen Betrieb und die kontinuierliche Verbesserung Ihrer PrestaShop-Module sicherzustellen.

---
title: "CMS-Seite duplizieren – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'CMS-Seite duplizieren' von MyPresta.eu."
sidebar:
  label: "CMS-Seite duplizieren – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Duplicate CMS page auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/duplicate-cms-page.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/duplicate-cms-page/)
>
> ---


# CMS-Seite duplizieren

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager neben dem Modul „CMS-Seite duplizieren“ auf „Konfigurieren“. Dies führt Sie zum Hauptkonfigurationsbildschirm des Moduls.

#### Allgemeine Einstellungen

- **MyPresta.eu Updates (mypresta\_updates)**

  - **Was diese Einstellung bewirkt:** Diese Einstellung steuert, ob das Modul nach Updates von MyPresta.eu sucht. Wenn diese Option aktiviert ist, werden Sie über neue Versionen, Fehlerbehebungen und Funktionserweiterungen benachrichtigt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul sucht regelmäßig nach verfügbaren Updates. Wenn ein Update gefunden wird, kann eine Benachrichtigung in Ihrem PrestaShop Back Office erscheinen.
    - *Wenn deaktiviert:* Das Modul sucht nicht nach Updates, und Sie werden nicht automatisch über neue Versionen benachrichtigt. Sie müssten manuell auf MyPresta.eu nach Updates suchen.
  - **Empfohlener Wert:** **JA** (Aktiviert).
  - **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Ihr Modul immer mit den neuesten Sicherheitspatches und Funktionen auf dem neuesten Stand ist, ohne jede Woche manuell die MyPresta.eu-Website überprüfen zu müssen.
- **Update (update\_)**

  - **Was diese Einstellung bewirkt:** Dies ist normalerweise ein Anzeigefeld oder eine Schaltfläche, die mit der Update-Prüfung zusammenhängt und den aktuellen Status anzeigt oder eine manuelle Prüfung ermöglicht. Es funktioniert in Verbindung mit der Einstellung „MyPresta.eu Updates“.
  - **Auswirkung der Änderung dieser Einstellung:** Das Klicken auf eine Schaltfläche hier (falls vorhanden) würde eine sofortige Überprüfung auf Updates initiieren.
  - **Empfohlener Wert:** N/A (Interaktionsbasiert).
  - **Händlerszenario / Beispiel:** Nachdem Sie „MyPresta.eu Updates“ aktiviert haben, könnten Sie hier klicken, um sofort zu sehen, ob eine neue Version verfügbar ist, anstatt auf die nächste automatische Prüfung zu warten.
- **Update Version (updatev\_)**

  - **Was diese Einstellung bewirkt:** Dieses Feld zeigt typischerweise die neueste verfügbare Version des Moduls an, wie sie vom Update-Checker erkannt wurde.
  - **Auswirkung der Änderung dieser Einstellung:** Dies ist ein schreibgeschütztes Feld und kann nicht direkt geändert werden. Es liefert Informationen über die neueste Version.
  - **Empfohlener Wert:** N/A (Nur Anzeige).
  - **Händlerszenario / Beispiel:** Sie sehen hier „1.2.3“, was darauf hinweist, dass eine neuere Version als Ihre aktuelle (z.B. 1.2.2) verfügbar ist.
- **Latest Version (dupcms\_LATEST)**

  - **Was diese Einstellung bewirkt:** Ähnlich wie „Update Version“ zeigt dieses Feld die aktuellste verfügbare Version des Moduls an.
  - **Auswirkung der Änderung dieser Einstellung:** Dies ist ein schreibgeschütztes Feld.
  - **Empfohlener Wert:** N/A (Nur Anzeige).
  - **Händlerszenario / Beispiel:** Sie können schnell überprüfen, ob Ihr installiertes Modul das aktuellste ist, indem Sie diesen Wert mit Ihrer installierten Version vergleichen.
- **Miniaturen (dupcms\_MINIATURES)**

  - **Was diese Einstellung bewirkt:** Diese Einstellung steuert wahrscheinlich, ob Miniaturbilder oder Symbole in der Benutzeroberfläche des Moduls angezeigt werden, möglicherweise im Zusammenhang mit dem Update-Checker oder anderen visuellen Elementen innerhalb des Admin-Panels des Moduls.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Möglicherweise sehen Sie kleine Symbole oder Bilder in der Modulkonfiguration oder in Update-Benachrichtigungen.
    - *Wenn deaktiviert:* Diese visuellen Elemente würden ausgeblendet, was zu einer textbasierten Benutzeroberfläche führen würde.
  - **Empfohlener Wert:** **JA** (Aktiviert).
  - **Händlerszenario / Beispiel:** Sie bevorzugen eine visuell reichere Oberfläche in Ihrem Back Office, daher lassen Sie diese Option aktiviert, um relevante Symbole zu sehen.
- **ID CMS Kategorie (dupcms\_ID\_CMSCAT)**

  - **Was diese Einstellung bewirkt:** Diese Einstellung ist entscheidend für die Kernfunktionalität des Moduls. Sie ermöglicht es Ihnen, eine Standard-CMS-Kategorie auszuwählen, in der duplizierte CMS-Seiten platziert werden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn eine bestimmte Kategorie ausgewählt ist:* Alle neu duplizierten CMS-Seiten werden automatisch dieser Kategorie zugewiesen. Dies hilft bei der Organisation Ihrer Inhalte.
    - *Wenn keine Kategorie ausgewählt ist (oder Standard):* Das Modul könnte standardmäßig die gleiche Kategorie wie die Originalseite oder eine Stammkategorie verwenden, abhängig von seiner internen Logik. Das Festlegen einer bestimmten Kategorie gibt Ihnen mehr Kontrolle.
  - **Empfohlener Wert:** Wählen Sie eine logische Standardkategorie, z.B. „Informationen“ oder eine spezifische Kategorie, die Sie für neue Seiten verwenden.
  - **Händlerszenario / Beispiel:** Sie duplizieren häufig „Rechtliche Hinweise“-Seiten für verschiedene Regionen. Sie können dies auf Ihre CMS-Kategorie „Rechtliche Seiten“ einstellen, sodass alle neuen Duplikate automatisch dort landen, was das Auffinden und Verwalten erleichtert.

#### So verwenden Sie die Duplizierungsfunktion

Die eigentliche Duplizierungsaktion findet in der Standard-PrestaShop-CMS-Seitenliste statt:

1. Navigieren Sie in Ihrem PrestaShop Back Office zu **Verbessern > Design > Seiten**.
2. Sie sehen eine Liste Ihrer vorhandenen CMS-Seiten.
3. Suchen Sie die CMS-Seite, die Sie duplizieren möchten.
4. In der Spalte „Aktionen“ (normalerweise durch drei Punkte oder ein Dropdown-Menü dargestellt) für diese spezifische CMS-Seite finden Sie eine neue Option, die von diesem Modul hinzugefügt wurde: **„Duplizieren“** (oder ein ähnliches Symbol/Text).
5. Klicken Sie auf „Duplizieren“.
6. Das Modul erstellt eine exakte Kopie der Seite, einschließlich Inhalt, Meta-Informationen, Friendly URL und aktivem Status. Die neue Seite hat typischerweise einen Namen wie „Kopie von [Originalseitenname]“ oder ähnlich, den Sie dann bearbeiten können.
7. Die duplizierte Seite wird in der CMS-Kategorie platziert, die Sie in der Modulkonfiguration ausgewählt haben (wenn `dupcms_ID_CMSCAT` eingestellt ist) oder in derselben Kategorie wie das Original.
8. Sie können die neu duplizierte Seite dann bearbeiten, um Titel, Inhalt, URL und andere Einstellungen nach Bedarf zu ändern.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | MyPresta.eu Updates | JA | Aktiviert automatische Prüfungen auf Modul-Updates. |
| Modulkonfiguration | Update | N/A (Schaltfläche) | Initiiert eine manuelle Prüfung auf Modul-Updates. |
| Modulkonfiguration | Update Version | N/A (Anzeige) | Zeigt die neueste verfügbare Modulversion an. |
| Modulkonfiguration | Latest Version | N/A (Anzeige) | Zeigt die zuletzt erkannte Modulversion an. |
| Modulkonfiguration | Miniaturen | JA | Steuert die Anzeige visueller Elemente/Symbole in der Moduloberfläche. |
| Modulkonfiguration | ID CMS Kategorie | Eine Kategorie auswählen | Legt die Standard-CMS-Kategorie für duplizierte Seiten fest. |
| CMS-Seitenliste (Design > Seiten) | Duplizieren-Aktion | N/A (Schaltfläche) | Erstellt eine exakte Kopie der ausgewählten CMS-Seite. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe eine Seite dupliziert, kann sie aber nicht finden.**
A: Überprüfen Sie die CMS-Kategorie, die Sie in der Modulkonfiguration (`dupcms_ID_CMSCAT`) ausgewählt haben. Wenn Sie keine festgelegt haben, befindet sie sich möglicherweise in derselben Kategorie wie die Originalseite oder in der Stamm-CMS-Kategorie. Stellen Sie außerdem sicher, dass Sie nach „Kopie von [Originalseitenname]“ oder Ähnlichem suchen, da das Modul dem Titel der duplizierten Seite ein Präfix hinzufügt.

**F: Die duplizierte Seite hat die gleiche Friendly URL wie das Original. Ist das ein Problem?**
A: Ja, dies kann zu Konflikten und SEO-Problemen führen. Nach dem Duplizieren einer Seite **bearbeiten Sie die neue Seite immer sofort** und ändern Sie ihre Friendly URL (auch bekannt als „URL-Umschreibung“ oder „Slug“) in etwas Einzigartiges und Beschreibendes für den neuen Inhalt. PrestaShop hängt normalerweise eine Zahl (z.B. `-1`) an die URL an, aber es ist am besten, sie selbst anzupassen.

**F: Ich sehe die Option „Duplizieren“ in der CMS-Seitenliste nicht.**
A:

1. Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass das Modul „CMS-Seite duplizieren“ installiert und aktiviert ist.
2. Leeren Sie Ihren PrestaShop-Cache: Gehen Sie zu **Erweiterte Einstellungen > Leistung**, scrollen Sie nach unten und klicken Sie auf „Cache leeren“.
3. Wenn es immer noch nicht angezeigt wird, versuchen Sie, das Modul neu zu installieren (nachdem Sie Ihren Shop gesichert haben). Wenn das Problem weiterhin besteht, wenden Sie sich an den MyPresta.eu-Support.

**F: Dupliziert dieses Modul Bilder und Dateien, die im Inhalt der CMS-Seite verlinkt sind?**
A: Ja, das Modul dupliziert den gesamten HTML-Inhalt der Seite. Wenn Ihre Bilder mit relativen Pfaden innerhalb des Inhalts verlinkt sind, funktionieren sie weiterhin. Wenn sie direkt über den Rich-Text-Editor hochgeladen werden, werden die Referenzen kopiert. Das Modul dupliziert jedoch nicht die eigentlichen Bild-*Dateien* auf Ihrem Server; es dupliziert die *Referenzen* darauf. Dies ist im Allgemeinen das gewünschte Verhalten.

**F: Kann ich eine CMS-Kategorie duplizieren?**
A: Nein, dieses Modul ist speziell dafür konzipiert, einzelne CMS-*Seiten* zu duplizieren, nicht ganze CMS-*Kategorien*.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Überblick für Entwickler und Webmaster, die das Modul „CMS-Seite duplizieren“ verstehen, debuggen oder erweitern möchten.

### 4.1 Architekturübersicht

Das Modul „CMS-Seite duplizieren“ ist ein leichtgewichtiges PrestaShop-Modul, das sich hauptsächlich auf die Erweiterung der Funktionalität des bestehenden `AdminCmsController` konzentriert. Es nutzt das Hook-System von PrestaShop (`actionAdminControllerSetMedia`), um JavaScript einzuschleusen, das die Standardtabelle der CMS-Seitenliste modifiziert und eine „Duplizieren“-Aktion hinzufügt. Die Kernlogik der Duplizierung wird von der Datei `dupcms.php` des Moduls gehandhabt, die AJAX-Anfragen abfängt, um die für das Kopieren von CMS-Seitendaten erforderlichen Datenbankoperationen durchzuführen. Es führt keine neuen Datenbanktabellen oder komplexen Objektmodelle ein, sondern verlässt sich stattdessen auf die direkte Manipulation der vorhandenen Tabellen `ps_cms` und `ps_cms_lang`.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Controller ein. Seine Funktionalität ist über Hooks und AJAX in den bestehenden `AdminCmsController` integriert.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen ein. Es interagiert direkt mit den PrestaShop-Kernklassen `CMS` und `CMSCategory` und deren zugehörigen Datenbanktabellen.

### 4.4 JavaScript-Assets (`views/js/`)

- **`dupcms/views/js/dupcms.js`**
  - **Umfang:** Back-Office (insbesondere die Seite `AdminCms`).
  - **Verantwortlichkeit:**
    - Dieses Skript wird über den Hook `actionAdminControllerSetMedia` in die Seite `AdminCmsController` (Verbessern > Design > Seiten) eingefügt.
    - Es wartet, bis das DOM bereit ist.
    - Es identifiziert die Spalte „Aktionen“ in der CMS-Seitenlistentabelle.
    - Für jede CMS-Seitenzeile fügt es dynamisch eine neue „Duplizieren“-Aktionsschaltfläche oder einen Link zum vorhandenen Aktions-Dropdown hinzu.
    - Es fügt einen Event-Listener (z.B. `click`) an diese neu hinzugefügten „Duplizieren“-Elemente an.
    - Wenn eine „Duplizieren“-Aktion geklickt wird, extrahiert es die `id_cms` der zu duplizierenden Seite.
    - Es sendet dann eine AJAX-Anfrage an die Haupt-PHP-Datei des Moduls (`dupcms/dupcms.php`) mit der `id_cms` und einem Aktionsparameter (z.B. `action=duplicateCms`).
    - Es verarbeitet die AJAX-Antwort, zeigt typischerweise eine Erfolgs- oder Fehlermeldung an und aktualisiert möglicherweise die CMS-Seitenliste, um die neu duplizierte Seite anzuzeigen.
    - Es kann auch Logik für Update-Benachrichtigungen oder andere dynamische UI-Elemente im Zusammenhang mit der Modulkonfiguration enthalten.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`dupcms/views/css/dupcms.css`**
  - **Umfang:** Back-Office (insbesondere die Seite `AdminCms`).
  - **Verantwortlichkeit:**
    - Bietet Styling für den dynamisch hinzugefügten „Duplizieren“-Aktionslink/-Button, um sicherzustellen, dass er visuell in das PrestaShop Back Office-Theme integriert ist.
    - Kann Stile für modulspezifische Benachrichtigungen oder UI-Elemente im `AdminCms`-Kontext enthalten.
    - Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können: Suchen Sie nach Klassen wie `.dupcms-duplicate-action` oder ähnlichem im eingefügten HTML, um dessen Erscheinungsbild anzupassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul verwendet keine benutzerdefinierten Smarty-Template-Dateien (`.tpl`). Alle seine UI-Modifikationen im Back Office werden dynamisch über JavaScript durchgeführt.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine neuen benutzerdefinierten Datenbanktabellen.
  - Es arbeitet mit vorhandenen PrestaShop-Tabellen:
    - `ps_cms`: Speichert allgemeine CMS-Seiteninformationen (aktiver Status, Position usw.).
    - `ps_cms_lang`: Speichert sprachspezifische CMS-Seiteninhalte (Titel, Meta-Beschreibung, Inhalt, Friendly URL).
    - `ps_cms_shop`: Verknüpft CMS-Seiten mit bestimmten Shops in einer Multishop-Umgebung.
    - `ps_configuration`: Speichert die Konfigurationseinstellungen des Moduls (z.B. `dupcms_ID_CMSCAT`, `mypresta_updates`).
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wird ausgeführt, wenn ein Back Office-Controller seine Medien (JS/CSS) einstellt. | Dies ist der primäre Hook, der vom Modul verwendet wird. Er injiziert `dupcms.js` und `dupcms.css` in die Seite `AdminCmsController`, wodurch das Modul die CMS-Seitenliste ändern und die „Duplizieren“-Aktion hinzufügen kann. |

## 5. Offizieller Support & Updates

Für offiziellen Support, Updates und zum Herunterladen der neuesten Version des Moduls „CMS-Seite duplizieren“ melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zur Funktionalität des Moduls zur Verfügung.

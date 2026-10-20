---
title: "Hooks Manager - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Hooks Manager von MyPresta.eu."
sidebar:
  label: "Hooks Manager - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Hooks Manager auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/hooks-manager.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/hooks-manager/)
>
> ---


# Hooks Manager

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation auf „Konfigurieren“ neben dem Hooks Manager-Modul. Sie sehen eine Liste aller von Ihnen erstellten benutzerdefinierten Hooks sowie Optionen zum Hinzufügen neuer Hooks.

#### Hinzufügen eines neuen benutzerdefinierten Hooks:

Oben auf der Konfigurationsseite finden Sie die Felder zum Erstellen eines neuen Hooks.

- **Hook-Name:**

  - **Was diese Einstellung bewirkt:** Dies ist der eindeutige, technische Name für Ihren neuen Hook. Er muss mit `display` beginnen (z.B. `displayMyCustomHook`, `displayProductExtraInfo`). Dieser Name ist das, was Sie später in den `.tpl`-Dateien Ihres Themes verwenden werden, um den Hook „aufzurufen“.
  - **Auswirkung einer Änderung dieser Einstellung:** Dieser Name ist entscheidend für Entwickler, um den Hook in Ihrem Theme zu platzieren. Eine Änderung nach der Erstellung würde eine Aktualisierung Ihrer Theme-Dateien erfordern.
  - **Empfohlener Wert:** Verwenden Sie beschreibende, camelCase-Namen, die mit `display` beginnen. Beispiel: `displayProductBelowAddToCart`, `displayHomepagePromoBanner`.
  - **Händlerszenario / Beispiel:** Sie möchten ein Banner unter dem „In den Warenkorb“-Button auf Produktseiten hinzufügen. Sie könnten den Hook `displayProductBelowAddToCart` nennen.
- **Hook-Titel:**

  - **Was diese Einstellung bewirkt:** Dies ist ein freundlicher, menschenlesbarer Titel für Ihren Hook, der in Ihrem PrestaShop Back Office angezeigt wird (z.B. wenn Sie zu **Design > Positionen** gehen, um Module Hooks zuzuweisen).
  - **Auswirkung einer Änderung dieser Einstellung:** Erleichtert die Identifizierung Ihres benutzerdefinierten Hooks unter den vielen Standard-Hooks im Back Office.
  - **Empfohlener Wert:** Ein klarer, beschreibender Titel. Beispiel: „Produktseite - Unter In den Warenkorb“, „Startseite - Top Promo Banner“.
  - **Händlerszenario / Beispiel:** Für den Hook `displayProductBelowAddToCart` würden Sie den Titel auf „Produktseite - Unter In den Warenkorb“ setzen.
- **Hook-Beschreibung:**

  - **Was diese Einstellung bewirkt:** Eine optionale, längere Beschreibung, um mehr Kontext über den beabsichtigten Zweck oder die Platzierung des Hooks bereitzustellen. Dies ist ebenfalls für den internen Gebrauch im Back Office.
  - **Auswirkung einer Änderung dieser Einstellung:** Hilft Ihnen und Ihrem Team, den spezifischen Anwendungsfall für jeden benutzerdefinierten Hook zu merken.
  - **Empfohlener Wert:** Erklären Sie kurz, wo der Hook platziert werden soll und welche Art von Inhalt er enthalten soll. Beispiel: „Vorgesehen für Vertrauensabzeichen oder kleine Werbebotschaften direkt unter dem In den Warenkorb-Button.“
  - **Händlerszenario / Beispiel:** Für den Hook `displayProductBelowAddToCart` könnten Sie hinzufügen: „Verwenden Sie dies für kleine Vertrauensabzeichen oder eine kostenlose Versandnachricht.“
- **Sichtbarkeit:**

  - **Was diese Einstellung bewirkt:** Dies bestimmt, ob der Hook in der Liste der verfügbaren Hooks sichtbar ist, wenn Sie in Ihrem PrestaShop Back Office zu **Design > Positionen** gehen.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Hook wird in der Liste angezeigt, sodass Sie Module einfach zuweisen können.
    - *Wenn deaktiviert:* Der Hook existiert weiterhin und funktioniert, wenn er in Ihrem Theme aufgerufen wird, aber er wird nicht in der Liste „Design > Positionen“ angezeigt, was die Verwaltung von Modulen für ihn erschwert.
  - **Empfohlener Wert:** **Aktiviert (Ja)**, es sei denn, Sie haben einen sehr spezifischen Grund, ihn zu verbergen.
  - **Händlerszenario / Beispiel:** Sie haben einen neuen Hook erstellt und möchten sofort Module zuweisen. Lassen Sie ihn aktiviert.

#### Verwalten bestehender benutzerdefinierter Hooks:

Unter dem Abschnitt „Neuen Hook hinzufügen“ sehen Sie eine Tabelle, die alle von Ihnen erstellten benutzerdefinierten Hooks auflistet.

- **Aktiviert / Deaktiviert-Schalter (für jeden Hook):**

  - **Was diese Einstellung bewirkt:** Dieser Schalter ermöglicht es Ihnen, einen einzelnen benutzerdefinierten Hook zu aktivieren oder zu deaktivieren.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Der Hook ist aktiv, und alle ihm zugewiesenen Module rendern ihren Inhalt, wenn der Hook in Ihrem Theme aufgerufen wird.
    - *Wenn deaktiviert:* Der Hook ist inaktiv. Selbst wenn er in Ihrem Theme aufgerufen wird, rendert er keinen Inhalt von ihm zugewiesenen Modulen. Dies ist eine sanfte Methode, um Inhalte vorübergehend auszublenden, ohne Module zu entkoppeln.
  - **Empfohlener Wert:** **Aktiviert** für Hooks, die Sie verwenden möchten, **Deaktiviert** für Hooks, die Sie vorübergehend ausblenden möchten.
  - **Händlerszenario / Beispiel:** Sie haben ein saisonales Werbebanner über einen benutzerdefinierten Hook platziert. Wenn die Aktion endet, können Sie den Hook deaktivieren, um das Banner auszublenden, ohne das Modul zu entfernen.
- **Live-Bearbeitung (für jeden Hook):**

  - **Was diese Einstellung bewirkt:** Dies ist ein schneller Link zur Seite „Design > Positionen“, gefiltert, um nur den ausgewählten benutzerdefinierten Hook anzuzeigen.
  - **Auswirkung einer Änderung dieser Einstellung:** Durch Klicken auf diese Schaltfläche gelangen Sie direkt zu der Seite, auf der Sie andere Module an diesen spezifischen benutzerdefinierten Hook „anhängen“ (zuweisen) können.
  - **Empfohlener Wert:** Verwenden Sie diese Schaltfläche immer, wenn Sie ein Modul Ihrem neu erstellten benutzerdefinierten Hook zuweisen möchten.
  - **Händlerszenario / Beispiel:** Sie haben gerade `displayProductBelowAddToCart` erstellt und möchten nun Ihr „Vertrauensabzeichen“-Modul daran zuweisen. Klicken Sie auf „Live-Bearbeitung“ neben `displayProductBelowAddToCart`.

#### Andere Konfigurationsschlüssel (Intern):

Möglicherweise sehen Sie `mypresta_updates`, `update_`, `updatev_` in der internen Konfiguration des Moduls. Diese beziehen sich typischerweise auf Modul-Updates und Lizenzprüfungen von MyPresta.eu und erfordern keine Interaktion des Händlers.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Hook-Name | Beschreibend, `display`-Präfix | Eindeutiger technischer Bezeichner für den Hook. Wird in Theme-Dateien verwendet. |
| Modulkonfiguration | Hook-Titel | Klar, menschenlesbar | Erscheint unter Design > Positionen zur einfachen Identifizierung. |
| Modulkonfiguration | Hook-Beschreibung | Optional, informativ | Bietet Kontext für den Zweck des Hooks. |
| Modulkonfiguration | Sichtbarkeit | Aktiviert (Ja) | Macht den Hook unter Design > Positionen für die Modulzuweisung sichtbar. |
| Modulkonfiguration | Aktiviert / Deaktiviert (pro Hook) | Aktiviert | Aktiviert/deaktiviert die Fähigkeit des benutzerdefinierten Hooks, Inhalte zu rendern. |
| Modulkonfiguration | Live-Bearbeitung (pro Hook) | N/A (Aktionsschaltfläche) | Direkter Link zu Design > Positionen, um Module dem Hook zuzuweisen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe einen Hook erstellt und ein Modul zugewiesen, aber nichts wird in meinem Shop angezeigt. Was ist falsch?**
A: Dies ist das häufigste Problem. Das Hooks Manager-Modul *erstellt* den Hook, aber Sie (oder Ihr Webmaster) müssen diesen Hook immer noch in die `.tpl`-Dateien Ihres Themes *platzieren*.
- **Lösung:** Sie müssen Ihre Theme-Dateien (z.B. `product.tpl`, `index.tpl`, `header.tpl`, `footer.tpl`) bearbeiten und den folgenden Code-Snippet an der Stelle einfügen, an der der Hook erscheinen soll: `{$hook_name}`. Ersetzen Sie `hook_name` durch den tatsächlichen Namen Ihres Hooks (z.B. `{$hook_displayProductBelowAddToCart}`).
- **Überprüfen Sie auch:**
1. Ist der Hook in der Hooks Manager-Konfiguration „Aktiviert“?
2. Ist das Modul, das Sie anzeigen möchten, tatsächlich unter **Design > Positionen** an Ihren benutzerdefinierten Hook „angehängt“?
3. Haben Sie Ihren PrestaShop-Cache geleert (**Erweiterte Einstellungen > Leistung**)?

**F: Kann ich denselben benutzerdefinierten Hook mehrmals an verschiedenen Stellen verwenden?**
A: Ja, das können Sie. Wenn Sie `{$hook_displayMyCustomHook}` in `product.tpl` und auch in `category.tpl` platzieren, wird jedes Modul, das `displayMyCustomHook` zugewiesen ist, an beiden Stellen gerendert. Dies ist leistungsstark, um konsistente Inhalte über verschiedene Seitentypen hinweg anzuzeigen.

**F: Mein benutzerdefinierter Hook wird angezeigt, aber das Styling stimmt nicht. Was kann ich tun?**
A: Das Hooks Manager-Modul stellt nur den „Slot“ bereit. Das Styling des Inhalts innerhalb dieses Slots wird durch das Modul, das Sie dort platziert haben, und das CSS Ihres Themes bestimmt.
- **Lösung:** Möglicherweise müssen Sie Ihrem Theme benutzerdefiniertes CSS hinzufügen, um den Inhalt zu stylen, der vom Modul in Ihrem benutzerdefinierten Hook gerendert wird. Ihr Webmaster kann Ihnen dabei helfen.

**F: Ich möchte einen benutzerdefinierten Hook entfernen. Wie mache ich das sicher?**
A: In der Hooks Manager-Konfiguration sehen Sie neben jedem benutzerdefinierten Hook eine Schaltfläche „Löschen“.
- **Wichtig:** Stellen Sie vor dem Löschen sicher, dass Sie alle Aufrufe dieses Hooks (`{$hook_yourCustomHookName}`) aus den `.tpl`-Dateien Ihres Themes entfernt haben. Wenn Sie den Hook löschen, aber den Aufruf in Ihrem Theme belassen, kann dies zu einem kleinen Fehler führen oder einfach nichts rendern. Entfernen Sie auch alle Module über **Design > Positionen**.

**F: Beeinträchtigt dieses Modul die Leistung meines Shops?**
A: Das Modul selbst ist sehr leichtgewichtig. Das Hinzufügen weiterer Hooks und das Zuweisen weiterer Module *kann* die Ladezeit der Seite schrittweise erhöhen, aber dies gilt für jeden zusätzlichen Inhalt auf Ihrer Seite, unabhängig davon, wie er angehängt wird. Die Auswirkungen sind im Allgemeinen vernachlässigbar, es sei denn, Sie fügen Dutzende komplexer Module zu einer einzigen Seite hinzu.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Hooks Manager-Modul ist ein unkompliziertes PrestaShop-Modul, das entwickelt wurde, um den Kern-Hooking-Mechanismus zu erweitern. Es nutzt hauptsächlich die PrestaShop-Klasse `Module` und die Tabelle `Configuration`, um benutzerdefinierte Hook-Definitionen zu verwalten. Es führt keine komplexen MVC-Muster oder benutzerdefinierten Datenbanktabellen ein, sondern manipuliert die Tabellen `ps_hook` und `ps_hook_module` indirekt über die PrestaShop-API. Die Kernfunktionalität des Moduls befindet sich in seiner Haupt-PHP-Datei `hooksmanager.php`, die die Installation, Deinstallation und die Back Office-Konfigurationsoberfläche verwaltet.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Das gesamte Front-Office-Rendering wird von der Standard-PrestaShop-Methode `Hook::exec()` übernommen, wenn der benutzerdefinierte Hook in einer `.tpl`-Datei aufgerufen wird.
- **Back-Office-Admin-Controller**: Keine. Die gesamte Administration wird direkt innerhalb der Methode `getContent()` der Datei `hooksmanager.php` gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

- Es sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` vorhanden. Das Modul interagiert direkt mit den PrestaShop-Kernklassen `Hook` und `Module`.

### 4.4 JavaScript-Assets (`views/js/`)

- Es sind keine benutzerdefinierten JavaScript-Dateien im Modul vorhanden. Die Back Office-Konfiguration basiert auf Standard-PrestaShop-Formularelementen und möglicherweise jQuery, falls global von PrestaShop eingebunden.

### 4.5 CSS-Stylesheets (`views/css/`)

- Es sind keine benutzerdefinierten CSS-Dateien im Modul vorhanden. Die Back Office-Konfiguration verwendet das Standard-Admin-Theme-Styling von PrestaShop.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- Es sind keine benutzerdefinierten Smarty-Template-Dateien im Modul vorhanden. Die gesamte Konfigurationsoberfläche wird direkt innerhalb der Methode `getContent()` von `hooksmanager.php` unter Verwendung von reinem HTML und PrestaShop-Hilfsklassen gerendert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt keine eigenen benutzerdefinierten Datenbanktabellen.
  - Es interagiert hauptsächlich mit den folgenden PrestaShop-Kerntabellen:
    - `ps_hook`: Speichert die Definitionen aller Hooks, einschließlich derer, die von diesem Modul erstellt wurden.
    - `ps_hook_lang`: Speichert die übersetzbaren Titel und Beschreibungen für Hooks.
    - `ps_module_hook`: Verknüpft Module mit Hooks und definiert, welches Modul in welchem Hook angezeigt wird.
    - `ps_configuration`: Speichert modulspezifische Konfigurationswerte (z.B. `mypresta_updates`, `update_`, `updatev_` für die interne Modulverwaltung).
- **Registrierte Hooks-Tabelle**:
  Das Modul selbst registriert keine Hooks, um eigene Inhalte anzuzeigen. Sein Zweck ist es, neue Hooks für andere Module zu *erstellen*.

  Die Kernfunktionalität des Moduls umfasst:

  - `install()`:
    - Registriert das Modul bei `displayAdminProductsExtra` (oder ähnlich, obwohl nicht explizit im Dossier angegeben, ist dies für Admin-Tools üblich, um einen Link anzuzeigen).
    - Erstellt einen neuen Tab im Back Office (falls zutreffend, obwohl für dieses Modul nicht explizit angegeben, ist dies für Admin-Tools üblich).
    - Setzt Standardkonfigurationswerte in `ps_configuration`.
  - `uninstall()`:
    - Löscht alle vom Modul erstellten benutzerdefinierten Hooks aus `ps_hook` und `ps_hook_lang`.
    - Entfernt zugehörige `ps_module_hook`-Einträge.
    - Bereinigt Konfigurationswerte aus `ps_configuration`.
  - `getContent()`:
    - Verarbeitet die Übermittlung des Back Office-Konfigurationsformulars.
    - Verarbeitet die Erstellung, Aktualisierung und Löschung benutzerdefinierter Hooks.
    - Rendert den HTML-Code für die Konfigurationsseite, listet vorhandene Hooks auf und stellt das Formular zum Hinzufügen neuer Hooks bereit.
    - Verwendet die Methoden `Hook::add()` und `Hook::remove()`, um Hook-Einträge in der Datenbank zu verwalten.

  **Entwicklerhinweis zur Verwendung benutzerdefinierter Hooks:**
  Um einen mit diesem Modul erstellten benutzerdefinierten Hook zu verwenden, muss ein Entwickler die Smarty-Variable `{$hook_YOUR_CUSTOM_HOOK_NAME}` manuell in die gewünschte `.tpl`-Datei innerhalb des aktiven PrestaShop-Themes einfügen. Wenn beispielsweise ein Hook namens `displayProductBelowAddToCart` erstellt wird, würde der Entwickler `{$hook_displayProductBelowAddToCart}` an der gewünschten Stelle in `themes/your_theme/templates/catalog/_partials/product-details.tpl` oder `product.tpl` hinzufügen. Die PrestaShop-Kernmethode `Hook::exec()` übernimmt dann das Rendern der diesem benutzerdefinierten Hook zugewiesenen Module.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Hooks Manager-Modul besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, die optimale Funktion Ihres Moduls sicherzustellen und Sie bei technischen Fragen zu unterstützen.

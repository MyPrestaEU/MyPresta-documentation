---
title: "CMS-Tab auf der Produktseite – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'CMS-Tab auf der Produktseite' von MyPresta.eu."
sidebar:
  label: "CMS-Tab auf der Produktseite – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product page CMS tab auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-page-cms-tab.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-page-cms-tab/)
>
> ---


# CMS-Tab auf der Produktseite

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und auf den meisten Hosting-Umgebungen standardmäßig verfügbar. Für dieses Modul sind keine speziellen oder ungewöhnlichen Erweiterungen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager neben dem Modul „CMS-Tab auf der Produktseite“ auf „Konfigurieren“. Dies führt Sie zum Hauptkonfigurationsbildschirm.

#### **CMS-Seite auswählen, die als Tab angezeigt werden soll**

Dies ist die Kerneinstellung des Moduls. Sie bestimmt, welche Ihrer bestehenden CMS-Seiten als neuer Tab auf allen Produktseiten angezeigt wird.

- **Was diese Einstellung bewirkt:** Dieses Dropdown-Menü listet alle CMS-Seiten auf, die Sie in Ihrem PrestaShop-Shop erstellt haben (zu finden unter **Design > Seiten** oder **Design > CMS** in älteren Versionen). Sie müssen eine dieser Seiten auswählen.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn eine CMS-Seite ausgewählt ist:* Ein neuer Tab erscheint auf jeder Produktseite in Ihrem Shop. Der Titel dieses Tabs ist der Titel der ausgewählten CMS-Seite, und der Inhalt, der beim Klicken auf den Tab angezeigt wird, ist der Inhalt dieser CMS-Seite.
  - *Wenn „--- Auswählen ---“ gewählt ist:* Es erscheint kein neuer Tab auf den Produktseiten. Das Modul ist in Bezug auf die Front-Office-Anzeige effektiv inaktiv.
- **Empfohlener Wert:** Wählen Sie die CMS-Seite aus, die Informationen enthält, die Sie universell auf allen Ihren Produktseiten teilen möchten (z.B. eine Seite „Versandinformationen“, „Größenratgeber“ oder „Garantiedetails“).
- **Händlerszenario / Beispiel:** Sie möchten einen detaillierten „Größenratgeber“ für alle Bekleidungsprodukte bereitstellen. Zuerst erstellen Sie eine CMS-Seite mit dem Titel „Größenratgeber“ mit allen relevanten Informationen. Dann wählen Sie in der Konfiguration dieses Moduls „Größenratgeber“ aus dem Dropdown-Menü. Nun hat jede Produktseite einen „Größenratgeber“-Tab.

#### **Tab-Typ**

Diese Einstellung steuert, wie das Modul in das Tab-System von PrestaShop integriert wird, insbesondere für verschiedene PrestaShop-Versionen.

- **Was diese Einstellung bewirkt:** Dieses Dropdown ermöglicht es Ihnen, die Methode zu wählen, die das Modul zur Anzeige des Tabs verwendet. Es ist primär eine Kompatibilitätseinstellung für verschiedene PrestaShop-Versionen.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn „PrestaShop 1.7 / 8.x / 9.x“ ausgewählt ist:* Das Modul verwendet den Hook `displayProductExtraContent`, was die Standard- und empfohlene Methode ist, um neue Tabs in modernen PrestaShop-Versionen hinzuzufügen. Dies gewährleistet ein natives Erscheinungsbild.
  - *Wenn „PrestaShop 1.6“ ausgewählt ist:* Das Modul verwendet ältere Hooks wie `productTab` und `productTabContent`, die in PrestaShop 1.6 Standard waren. Diese Option dient der Abwärtskompatibilität, falls Sie einen älteren, nicht unterstützten PrestaShop 1.6 Shop betreiben (obwohl das Modul offiziell für 1.7+ ist).
- **Empfohlener Wert:** Für PrestaShop 1.7, 8.x und 9.x Shops wählen Sie immer **„PrestaShop 1.7 / 8.x / 9.x“**.
- **Händlerszenario / Beispiel:** Wenn Sie PrestaShop 8.1 betreiben, würden Sie „PrestaShop 1.7 / 8.x / 9.x“ auswählen, um sicherzustellen, dass der Tab korrekt angezeigt wird und sich nahtlos in das Design Ihres Themes integriert. Wenn Sie dieses Modul aus irgendeinem Grund auf einem alten PrestaShop 1.6 Shop verwenden würden, würden Sie „PrestaShop 1.6“ auswählen.

#### **MyPresta.eu Live-Updates**

Dieser Abschnitt ist in allen MyPresta.eu-Modulen üblich und hilft Ihnen bei der Verwaltung von Modul-Updates.

- **Was diese Einstellung bewirkt:** Diese Funktion prüft direkt bei MyPresta.eu auf neue Versionen des Moduls.
- **Auswirkungen einer Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul prüft regelmäßig auf Updates. Wenn eine neue Version verfügbar ist, sehen Sie eine Benachrichtigung in Ihrer Modulliste oder auf der Konfigurationsseite des Moduls. Dies hilft Ihnen, mit Fehlerbehebungen und neuen Funktionen auf dem Laufenden zu bleiben.
  - *Wenn deaktiviert:* Das Modul prüft nicht automatisch auf Updates. Sie müssten Ihr MyPresta.eu-Konto manuell auf neue Versionen überprüfen.
- **Empfohlener Wert:** **JA**. Das Aktualisieren von Modulen ist entscheidend für Sicherheit, Kompatibilität und den Zugriff auf die neuesten Funktionen.
- **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass Ihr Modul immer die neuesten Sicherheitspatches hat. Durch die Aktivierung werden Sie benachrichtigt, wenn ein Update verfügbar ist, und aufgefordert, es herunterzuladen und zu installieren.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | **CMS-Seite auswählen, die als Tab angezeigt werden soll** | --- Auswählen --- / Ihre gewählte CMS-Seite | Bestimmt, welcher CMS-Seiteninhalt als neuer Tab auf allen Produktseiten erscheint. |
| Modulkonfigurationsseite | **Tab-Typ** | PrestaShop 1.7 / 8.x / 9.x | Gewährleistet die korrekte Tab-Anzeige und Integration in die Architektur Ihrer PrestaShop-Version. |
| Modulkonfigurationsseite | **MyPresta.eu Live-Updates** | JA | Ermöglicht automatische Prüfungen auf Modul-Updates von MyPresta.eu. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der neue Tab wird auf meinen Produktseiten nicht angezeigt. Was soll ich tun?**
A:

1. **Modulkonfiguration überprüfen:** Gehen Sie zu **Module > Modul-Manager**, suchen Sie „CMS-Tab auf der Produktseite“ und klicken Sie auf „Konfigurieren“. Stellen Sie sicher, dass Sie eine gültige CMS-Seite aus dem Dropdown-Menü „CMS-Seite auswählen, die als Tab angezeigt werden soll“ ausgewählt haben. Wenn „--- Auswählen ---“ gewählt ist, wird kein Tab angezeigt.
2. **Tab-Typ überprüfen:** Stellen Sie sicher, dass „Tab-Typ“ für moderne PrestaShop-Versionen auf „PrestaShop 1.7 / 8.x / 9.x“ eingestellt ist.
3. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindert der PrestaShop-Cache, dass Änderungen sofort angezeigt werden.
4. **Status der CMS-Seite überprüfen:** Stellen Sie sicher, dass die ausgewählte CMS-Seite aktiv und öffentlich sichtbar ist (nicht deaktiviert oder auf privat gesetzt). Dies können Sie unter **Design > Seiten** überprüfen.
5. **Theme-Kompatibilität:** Obwohl das Modul Standard-PrestaShop-Hooks verwendet, können sehr stark angepasste Themes manchmal stören. Wenn die oben genannten Schritte nicht funktionieren, wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um zu sehen, ob der Tab erscheint. Wenn ja, benötigt Ihr Theme möglicherweise eine kleine Anpassung.

**F: Kann ich verschiedene CMS-Tabs für verschiedene Produkte haben?**
A: Dieses Modul ist darauf ausgelegt, *eine spezifische CMS-Seite* als Tab auf *allen* Produktseiten anzuzeigen. Es unterstützt nicht die Zuweisung verschiedener CMS-Seiten zu einzelnen Produkten. Wenn Sie produktspezifische Tabs benötigen, benötigen Sie typischerweise ein fortschrittlicheres Modul oder eine kundenspezifische Entwicklung.

**F: Der Inhalt im Tab sieht seltsam oder unformatiert aus.**
A: Das Modul zieht einfach den Inhalt von Ihrer CMS-Seite. Die Formatierung dieses Inhalts wird normalerweise durch das CSS Ihres PrestaShop-Themes gehandhabt.

1. **Inhalt der CMS-Seite überprüfen:** Stellen Sie sicher, dass der Inhalt auf Ihrer ursprünglichen CMS-Seite (unter **Design > Seiten**) korrekt formatiert ist und kein fehlerhaftes HTML enthält.
2. **Theme-CSS:** Das CSS Ihres Themes hat möglicherweise keine spezifischen Stile für Inhalte innerhalb von Produkt-Tabs, oder es überschreibt Standardstile. Wenn Sie einen Webentwickler haben, kann dieser die Seite überprüfen, um Stilkonflikte zu identifizieren und zu beheben.

**F: Ich habe meine CMS-Seite aktualisiert, aber der Tab-Inhalt auf den Produktseiten hat sich nicht geändert.**
A: Nach dem Aktualisieren einer CMS-Seite leeren Sie immer Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung > Cache leeren**). Ihr Shop könnte eine ältere, zwischengespeicherte Version des Inhalts bereitstellen.

**F: Wie übersetze ich den Tab-Titel, wenn mein Shop mehrsprachig ist?**
A: Der Tab-Titel wird automatisch aus dem Titel der ausgewählten CMS-Seite übernommen. Um ihn zu übersetzen, müssen Sie die CMS-Seite selbst bearbeiten (**Design > Seiten**) und Übersetzungen für ihren Titel und Inhalt für jede von Ihnen unterstützte Sprache bereitstellen. Das Modul zeigt dann den korrekten übersetzten Titel basierend auf der vom Kunden ausgewählten Sprache an.

## 4. Entwickler- & Webmaster-Leitfaden (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „CMS-Tab auf der Produktseite“ (`cmstab`) ist ein leichtgewichtiges PrestaShop-Modul, das entwickelt wurde, um vorhandenen CMS-Seiteninhalt als neuen Tab in Produktseiten einzufügen. Es nutzt hauptsächlich das Hook-System von PrestaShop, um dies zu erreichen. Die Kernlogik des Moduls befindet sich in seiner Haupt-PHP-Datei, `cmstab.php`, die Installation, Deinstallation, Konfiguration und Hook-Registrierung verwaltet. Es führt keine benutzerdefinierten Datenbanktabellen oder komplexen ObjectModels ein, sondern verlässt sich stattdessen auf die native `CMS`-Klasse von PrestaShop zur Inhaltsabfrage. Das Modul bietet zwei Sätze von Templates, um die Kompatibilität mit den Tab-Rendering-Mechanismen von PrestaShop 1.6 und 1.7+ zu gewährleisten, die über die Back-Office-Konfiguration ausgewählt werden können.

### 4.2 Controller (`controllers/`)

Dieses Modul führt keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller ein. Die gesamte Funktionalität wird über die Hauptmodulklasse und das PrestaShop-Hook-System verwaltet.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul führt keine benutzerdefinierten Klassen oder ObjectModels im Verzeichnis `classes/` ein. Es verwendet direkt die Kernklasse `CMS` von PrestaShop, um Inhalte basierend auf der konfigurierten CMS-Seiten-ID abzurufen.

### 4.4 JavaScript-Assets (`views/js/`)

- **`cmstab/trusted.js`**
  - **Geltungsbereich:** Back-Office (Modulkonfigurationsseite).
  - **Zweck:** Dieses Skript ist typischerweise in MyPresta.eu-Modulen enthalten, um die Funktionalität „MyPresta.eu Live-Updates“ zu handhaben. Es kommuniziert mit der MyPresta.eu-API, um nach neuen Modulversionen zu suchen und Update-Benachrichtigungen im PrestaShop-Back-Office anzuzeigen. Es beeinflusst weder die Front-Office-Anzeige noch die Kundeninteraktion.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Die Gestaltung des Tabs und seines Inhalts wird vom aktiven PrestaShop-Theme geerbt. Entwickler, die den Tab gestalten möchten, sollten die entsprechenden Selektoren des Themes oder des Kern-Tab-Systems von PrestaShop ansprechen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul bietet zwei Sätze von Templates, um den unterschiedlichen Tab-Rendering-Ansätzen der PrestaShop-Versionen gerecht zu werden. Der spezifische Satz, der verwendet wird, wird durch die Einstellung „Tab-Typ“ in der Modulkonfiguration bestimmt.

- **Hook-Templates (`views/templates/hook/`)**: Dieses Verzeichnis wird in diesem Modul nicht explizit für die direkte Hook-Wiedergabe verwendet. Templates werden direkt aus `views/front/` referenziert.
- **Front-Office-Templates (`views/templates/front/`)**:

  - **`cmstab/views/front/tab.tpl`**

    - **Zweck:** Dieses Template ist für die PrestaShop 1.6-Kompatibilität konzipiert. Es wird gerendert, wenn der „Tab-Typ“ auf „PrestaShop 1.6“ eingestellt ist. Es gibt das HTML für den Tab- *Header* (den anklickbaren Teil des Tabs) unter Verwendung des CMS-Seitentitels aus.
    - **Hook:** `productTab` (PrestaShop 1.6 spezifisch)
    - **Variablen:** `$cmstab_title` (der Titel der ausgewählten CMS-Seite).
  - **`cmstab/views/front/tab16.tpl`**

    - **Zweck:** Dieses Template ist ebenfalls für die PrestaShop 1.6-Kompatibilität. Es gibt das HTML für den Tab- *Inhaltsbereich* aus und zeigt den tatsächlichen Inhalt der ausgewählten CMS-Seite an.
    - **Hook:** `productTabContent` (PrestaShop 1.6 spezifisch)
    - **Variablen:** `$cmstab_content` (der HTML-Inhalt der ausgewählten CMS-Seite).
  - **`cmstab/views/front/tabcontents.tpl`**

    - **Zweck:** Dieses Template ist für die PrestaShop 1.7, 8.x und 9.x-Kompatibilität. Es wird gerendert, wenn der „Tab-Typ“ auf „PrestaShop 1.7 / 8.x / 9.x“ eingestellt ist. Es gibt die gesamte Tab-Struktur aus, einschließlich des Tab-Headers und seines Inhalts, wie es vom Hook `displayProductExtraContent` erwartet wird.
    - **Hook:** `displayProductExtraContent` (PrestaShop 1.7+ Standard)
    - **Variablen:**
      - `$cmstab_title`: Der Titel der ausgewählten CMS-Seite.
      - `$cmstab_content`: Der HTML-Inhalt der ausgewählten CMS-Seite.
      - `$cmstab_id`: Eine eindeutige ID für den Tab, abgeleitet von der CMS-Seiten-ID.
  - **`cmstab/views/front/tabcontents16.tpl`**

    - **Zweck:** Dieses Template scheint eine redundante oder alternative Version von `tab16.tpl` oder `tabcontents.tpl` zu sein, wahrscheinlich für spezifische 1.6-Szenarien oder eine ältere Implementierung. Angesichts der aktuellen Modullogik wird `tabcontents.tpl` für 1.7+ und `tab.tpl`/`tab16.tpl` für 1.6 verwendet. Entwickler sollten sich hauptsächlich auf `tabcontents.tpl` für moderne PrestaShop-Versionen konzentrieren.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen.
  - Es speichert seine Konfigurationseinstellungen in der PrestaShop-Tabelle `ps_configuration`:
    - `CMSTAB_ID`: Speichert die ID der ausgewählten CMS-Seite.
    - `CMSTAB_TYPE`: Speichert den ausgewählten Tab-Typ (z.B. '17' für PrestaShop 1.7+, '16' für PrestaShop 1.6).
    - `MYPRESTA_UPDATES`: Speichert die Einstellung für Live-Updates.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird vom Modul verwendet, um sein JavaScript für Live-Updates im Back Office zu registrieren. |
| `displayBackOfficeHeader` | Im `<head>`-Bereich jeder Back-Office-Seite. | Wird vom Modul verwendet, um sein JavaScript für Live-Updates im Back Office zu registrieren. |
| `displayProductExtraContent` | Auf Produktseiten, zum Hinzufügen neuer Tabs (PrestaShop 1.7+). | Haupt-Hook zum Rendern des CMS-Tabs und seines Inhalts auf modernen PrestaShop-Versionen. |
| `productTab` | Auf Produktseiten, zum Hinzufügen neuer Tab-Header (PrestaShop 1.6). | Wird für die Abwärtskompatibilität verwendet, um den Tab-Header auf PrestaShop 1.6 zu rendern. |
| `productTabContent` | Auf Produktseiten, zum Hinzufügen neuer Tab-Inhalte (PrestaShop 1.6). | Wird für die Abwärtskompatibilität verwendet, um den Tab-Inhalt auf PrestaShop 1.6 zu rendern. |
| `actionAdminControllerSetMedia` | Wenn ein Admin-Controller seine Medien-Assets festlegt. | Wird vom Modul verwendet, um sein JavaScript für Live-Updates im Back Office zu registrieren. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und professionellen Support wenden Sie sich bitte an Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, zeitnahe Unterstützung zu leisten und die optimale Leistung Ihrer Module sicherzustellen.

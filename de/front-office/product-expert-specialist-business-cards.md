---
title: "Produktexperte - Spezialisten-Visitenkarten - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Produktexperte - Spezialisten-Visitenkarten“ von MyPresta.eu."
sidebar:
  label: "Produktexperte - Spezialisten-Visitenkarten - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Product expert - Specialist Business Cards auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/product-expert-specialist-business-cards.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/product-expert-specialist-business-cards/)
>
> ---


# Produktexperte - Spezialisten-Visitenkarten

## 1. Anforderungen & Kompatibilität

Um einen reibungslosen Betrieb des Moduls „Produktexperte - Spezialisten-Visitenkarten“ zu gewährleisten, beachten Sie bitte die folgenden Anforderungen:

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen wie cURL, JSON und OpenSSL sind erforderlich und typischerweise in den meisten modernen Hosting-Umgebungen verfügbar. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Das Modul „Produktexperte - Spezialisten-Visitenkarten“ bietet umfangreiche Konfigurationsoptionen auf mehreren Bildschirmen in Ihrem PrestaShop Back Office.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Modul-Manager > Produktexperte - Spezialisten-Visitenkarten konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für allgemeine Moduleinstellungen, der direkt nach der Installation oder durch Klicken auf „Konfigurieren“ im Modul-Manager zugänglich ist.

-   **Modul aktivieren/deaktivieren:**
    -   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter für die Funktionalität des Moduls.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Die Funktionen des Moduls (Expertenkarten, Zuweisungen) sind in Ihrem Front Office aktiv.
        -   *Wenn deaktiviert:* Alle Modulfunktionen werden im Front Office ausgeblendet, und Expertenkarten werden nicht angezeigt.
    -   **Empfohlener Wert:** JA (es sei denn, Sie deaktivieren es vorübergehend für Wartungsarbeiten).
    -   **Händlerszenario / Beispiel:** Sie könnten es deaktivieren, wenn Sie ein größeres Theme-Update durchführen und sicherstellen möchten, dass keine Konflikte auftreten, und es dann nach Abschluss der Tests wieder aktivieren.
-   **Experten auf Produktseite anzeigen:**
    -   **Was diese Einstellung bewirkt:** Steuert, ob Expertenkarten auf einzelnen Produktseiten angezeigt werden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Experten, die Produkten, Kategorien, Marken oder Lieferanten zugewiesen sind, erscheinen auf den entsprechenden Produktseiten.
        -   *Wenn deaktiviert:* Experten werden auf Produktseiten nicht angezeigt, unabhängig von ihren Zuweisungen.
    -   **Empfohlener Wert:** JA (dies ist eine Kernfunktion des Moduls).
    -   **Händlerszenario / Beispiel:** Wenn Sie Experten nur für B2B-Anfragen auf einer dedizierten Seite und nicht direkt in Produktlisten verwenden möchten, könnten Sie dies deaktivieren.
-   **Experten im Hook anzeigen:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl eines bestimmten PrestaShop-Hooks, in dem die Expertenkarten angezeigt werden. Gängige Hooks sind `displayProductButtons`, `displayProductExtraContent`, `displayRightColumn`, `displayLeftColumn`, `displayFooter`.
    -   **Auswirkung der Änderung dieser Einstellung:** Die Expertenkarten werden an der gewählten Stelle auf Ihren Produktseiten oder anderen Seiten, auf denen der Hook aktiv ist, gerendert.
    -   **Empfohlener Wert:** `displayProductExtraContent` oder `displayProductButtons` sind oft gute Optionen für Produktseiten, da sie normalerweise prominent sind. Experimentieren Sie, um die beste Passform für Ihr Theme zu finden.
    -   **Händlerszenario / Beispiel:** Wenn Ihr Theme einen dedizierten „zusätzlichen Inhalt“-Tab oder -Abschnitt hat, könnte `displayProductExtraContent` ideal sein. Wenn Sie Experten in der Nähe des „In den Warenkorb“-Buttons wünschen, könnte `displayProductButtons` funktionieren.
-   **Kontaktformular aktivieren:**
    -   **Was diese Einstellung bewirkt:** Bestimmt, ob ein Kontaktformular für Kunden verfügbar ist, um Experten direkt Nachrichten zu senden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Eine Schaltfläche oder ein Link „Experten kontaktieren“ erscheint auf der Expertenkarte und öffnet ein Formular, in dem Kunden eine Nachricht senden können.
        -   *Wenn deaktiviert:* Die Kontaktformularoption wird von den Expertenkarten entfernt.
    -   **Empfohlener Wert:** JA (sehr empfehlenswert für Kundenbindung).
    -   **Händlerszenario / Beispiel:** Durch die Aktivierung können Kunden spezifische Fragen zu einem Produkt direkt an den Experten stellen, was zu fundierteren Käufen führt.
-   **DSGVO-Konformität für Kontaktformular:**
    -   **Was diese Einstellung bewirkt:** Wenn das Kontaktformular aktiviert ist, fügt diese Einstellung ein Kontrollkästchen hinzu, damit Kunden der Datenverarbeitung zustimmen können, was für die DSGVO-Konformität entscheidend ist.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Ein obligatorisches Kontrollkästchen erscheint auf dem Kontaktformular, das die Zustimmung des Kunden vor dem Senden einer Nachricht erfordert.
        -   *Wenn deaktiviert:* Es wird kein DSGVO-Zustimmungskontrollkästchen angezeigt.
    -   **Empfohlener Wert:** JA (unerlässlich für die Einhaltung gesetzlicher Vorschriften in vielen Regionen).
    -   **Händlerszenario / Beispiel:** Aktivieren Sie dies immer, wenn Ihre Zielgruppe in der EU oder einer Region mit ähnlichen Datenschutzgesetzen ist.
-   **Standard-Expertenkarten-Layout:**
    -   **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl eines vordefinierten oder benutzerdefinierten Layouts für die Anzeige einzelner Experten-Visitenkarten. Dies umfasst Optionen für die Fotoplatzierung, Textausrichtung und das allgemeine Kartendesign.
    -   **Auswirkung der Änderung dieser Einstellung:** Ändert das visuelle Erscheinungsbild aller Expertenkarten in Ihrem Shop, es sei denn, dies wird durch die Einstellungen eines bestimmten Experten überschrieben.
    -   **Empfohlener Wert:** Wählen Sie ein Layout, das am besten zur Ästhetik Ihres Shops passt. Sie können verschiedene Optionen in der Vorschau anzeigen.
    -   **Händlerszenario / Beispiel:** Sie könnten ein „Modernes“ Layout für einen schlanken, minimalistischen Shop oder ein „Klassisches“ Layout für ein traditionelleres Gefühl wählen.
-   **Standard-Expertenlisten-Layout:**
    -   **Was diese Einstellung bewirkt:** Bestimmt, wie mehrere Expertenkarten angeordnet werden, wenn mehr als ein Experte angezeigt wird (z. B. in einem Raster, einer Liste oder einem Karussell).
    -   **Auswirkung der Änderung dieser Einstellung:** Steuert die Gesamtpräsentation mehrerer Experten auf einer Seite.
    -   **Empfohlener Wert:** „Raster“ für eine kompakte Anzeige, „Karussell“ für platzsparendes und interaktives Browsing oder „Liste“ für eine detailliertere, gestapelte Ansicht.
    -   **Händlerszenario / Beispiel:** Wenn Sie viele Experten für eine Kategorie haben, kann ein „Karussell“ Platz sparen. Wenn Sie nur ein oder zwei haben, könnte ein „Raster“ sauberer aussehen.
-   **Experten-Suchwerkzeug anzeigen:**
    -   **Was diese Einstellung bewirkt:** Aktiviert eine Suchleiste, mit der Kunden Experten nach Namen oder Spezialität finden können.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Ein Suchfeld erscheint, normalerweise in der Nähe der Expertenkarten, das es Kunden ermöglicht, Experten zu filtern.
        -   *Wenn deaktiviert:* Das Experten-Suchwerkzeug ist nicht sichtbar.
    -   **Empfohlener Wert:** JA (verbessert die Benutzerfreundlichkeit, insbesondere bei vielen Experten).
    -   **Händlerszenario / Beispiel:** Wenn Sie ein großes Team von Spezialisten haben, hilft die Aktivierung des Suchwerkzeugs Kunden, schnell die richtige Person zu finden.
-   **Hook für Experten-Suchwerkzeug:**
    -   **Was diese Einstellung bewirkt:** Gibt an, wo das Experten-Suchwerkzeug in Ihrem Front Office angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:** Die Suchleiste erscheint an der gewählten Hook-Position.
    -   **Empfohlener Wert:** `displayTop` oder `displayNav` für globale Sichtbarkeit, oder `displayLeftColumn`/`displayRightColumn`, wenn Sie es neben anderen Filtern wünschen.
    -   **Händlerszenario / Beispiel:** Die Platzierung in `displayTop` macht es von jeder Seite aus leicht zugänglich, ähnlich einer Produktsuche.

### 2.2 Dedizierter Admin-Bildschirm: Experten (Back Office > Produktexperte > Experten)

Auf diesem Bildschirm verwalten Sie individuelle Expertenprofile, erstellen neue Experten und bearbeiten bestehende.

-   **Bildschirmname & Menüpfad:** **Produktexperte > Experten**
-   **Verfügbare Aktionen & Einstellungen:**
    -   **Expertenliste (Rasteransicht):** Zeigt eine Tabelle aller Ihrer erstellten Experten an. Sie sehen deren Namen, Rolle, Status (aktiv/inaktiv) und Aktionen wie „Bearbeiten“ oder „Löschen“.
    -   **Schaltfläche „Neuen Experten hinzufügen“:** Durch Klicken auf diese Schaltfläche gelangen Sie zu einem Formular, um ein neues Expertenprofil zu erstellen.
    -   **Bearbeiten/Löschen-Aktionen:** Für jeden Experten in der Liste können Sie auf „Bearbeiten“ klicken, um dessen Details zu ändern, oder auf „Löschen“, um ihn zu entfernen.
    -   **Massenaktionen:** Ermöglicht die Auswahl mehrerer Experten und die gleichzeitige Durchführung von Aktionen wie „Aktivieren“, „Deaktivieren“ oder „Löschen“.
-   **Experten-Erstellungs-/Bearbeitungsformular:**
    -   **Name:** Der vollständige Name Ihres Experten.
    -   **Rolle/Titel:** Deren Berufsbezeichnung oder Rolle (z. B. „Senior Sales Manager“, „Technischer Support-Spezialist“, „Modeberater“).
    -   **Kurze Biografie:** Eine kurze Beschreibung ihrer Expertise oder ihres Hintergrunds. Dies hilft Kunden, ihre Qualifikationen zu verstehen.
    -   **Foto:** Laden Sie ein professionelles Foto des Experten hoch. Dies ist entscheidend für den Aufbau von Vertrauen und persönlicher Verbindung.
    -   **Kontakt-Links:**
        -   **E-Mail:** E-Mail-Adresse des Experten.
        -   **Telefon:** Telefonnummer des Experten.
        -   **WhatsApp:** WhatsApp-Nummer (generiert einen direkten Chat-Link).
        -   **LinkedIn:** Link zu ihrem LinkedIn-Profil.
        -   **Weitere benutzerdefinierte Links:** Sie können zusätzliche benutzerdefinierte Links mit Symbolen hinzufügen (z. B. einen Link zu ihrem persönlichen Blog, einem spezifischen Produktportfolio).
    -   **Aktiv:** Ein Schalter zum Aktivieren oder Deaktivieren des Experten.
        -   *Wenn aktiviert:* Der Experte steht zur Zuweisung und Anzeige zur Verfügung.
        -   *Wenn deaktiviert:* Der Experte erscheint nicht im Front Office, auch wenn er zugewiesen ist.
    -   **Expertenkarten-Layout-Überschreibung:** Ermöglicht die Auswahl eines spezifischen Kartenlayouts für *diesen einzelnen Experten*, das die globale Standardeinstellung in der Modulkonfiguration überschreibt. Dies ist nützlich, um bestimmte Experten hervorzuheben oder deren persönliche Marke anzupassen.
    -   **Zuweisungen (Produkte, Kategorien, Marken, Lieferanten):** Hier verknüpfen Sie Experten mit spezifischen Shop-Entitäten.
        -   **Produkte:** Suchen und wählen Sie einzelne Produkte aus, denen dieser Experte zugeordnet ist.
        -   **Kategorien:** Wählen Sie Kategorien aus, in denen die Karte dieses Experten auf Produkten innerhalb dieser Kategorien erscheinen soll.
        -   **Marken:** Wählen Sie spezifische Marken aus, auf die sich dieser Experte spezialisiert hat.
        -   **Lieferanten:** Wählen Sie Lieferanten aus, deren Produkte dieser Experte beraten kann.
        -   *Auswirkung von Änderungen:* Wenn ein Kunde ein Produkt ansieht, das einer dieser Zuweisungen entspricht, wird die Karte des Experten angezeigt. Wenn mehrere Experten zugewiesen sind, werden alle relevanten Experten gemäß dem Listenlayout angezeigt.
-   **Auswirkung von Änderungen:**
    -   Das Hinzufügen eines neuen Experten macht ihn für die Zuweisung zu Produkten, Kategorien usw. verfügbar.
    -   Das Bearbeiten eines Experten aktualisiert dessen angezeigte Informationen und Kontaktdaten im gesamten Shop.
    -   Das Löschen eines Experten entfernt ihn und seine Zuweisungen aus Ihrem Shop.
    -   Das Ändern von Zuweisungen wirkt sich sofort darauf aus, welche Expertenkarten auf welchen Produktseiten erscheinen.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  **Neue Experten erstellen:** Wenn ein neues Teammitglied hinzukommt oder eine neue Spezialisierung benötigt wird, erstellen Sie hier dessen Profil.
    2.  **Experten zuweisen:** Überprüfen Sie regelmäßig Ihren Produktkatalog und weisen Sie neuen Produkten, Kategorien oder Marken relevante Experten zu.
    3.  **Profile aktualisieren:** Halten Sie Expertenfotos, Biografien und Kontaktdaten auf dem neuesten Stand.
    4.  **Deaktivieren/Reaktivieren:** Verwenden Sie den Schalter „Aktiv“, um einen Experten vorübergehend auszublenden (z. B. wenn er im Urlaub ist), ohne sein Profil zu löschen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfiguration** | Modul aktivieren/deaktivieren | JA | Hauptschalter für die Modulfunktionalität. |
| | Experten auf Produktseite anzeigen | JA | Expertenkarten auf Produktseiten anzeigen. |
| | Experten im Hook anzeigen | `displayProductExtraContent` | Wählen Sie, wo Expertenkarten auf Produktseiten erscheinen. |
| | Kontaktformular aktivieren | JA | Kunden erlauben, Experten direkt Nachrichten zu senden. |
| | DSGVO-Konformität für Kontaktformular | JA | Zustimmungs-Kontrollkästchen zum Kontaktformular hinzufügen. |
| | Standard-Expertenkarten-Layout | (Wählen Sie basierend auf dem Theme) | Visueller Stil einzelner Expertenkarten. |
| | Standard-Expertenlisten-Layout | Raster / Karussell | Wie mehrere Expertenkarten angeordnet werden. |
| | Experten-Suchwerkzeug anzeigen | JA | Eine Suchleiste für Experten aktivieren. |
| | Hook für Experten-Suchwerkzeug | `displayTop` / `displayNav` | Wo das Experten-Suchwerkzeug erscheint. |
| **Produktexperte > Experten** | Neuen Experten hinzufügen | N/A | Neue Expertenprofile erstellen. |
| | Experten bearbeiten | N/A | Expertendetails ändern (Name, Rolle, Biografie, Foto, Kontakte). |
| | Aktiv (Expertenstatus) | JA | Sichtbarkeit einzelner Experten aktivieren/deaktivieren. |
| | Expertenkarten-Layout-Überschreibung | N/A | Globales Kartenlayout für einen bestimmten Experten überschreiben. |
| | Produkten zuweisen | N/A | Experten mit bestimmten Produkten verknüpfen. |
| | Kategorien zuweisen | N/A | Experten mit Produkten innerhalb bestimmter Kategorien verknüpfen. |
| | Marken zuweisen | N/A | Experten mit Produkten bestimmter Marken verknüpfen. |
| | Lieferanten zuweisen | N/A | Experten mit Produkten bestimmter Lieferanten verknüpfen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

Hier sind einige häufig gestellte Fragen und Tipps zur Fehlerbehebung für Shop-Betreiber, die das Modul „Produktexperte - Spezialisten-Visitenkarten“ verwenden:

**F1: Meine Expertenkarten werden nicht auf der Produktseite angezeigt.**

-   **A:** Überprüfen Sie zunächst, ob das Modul unter **Module > Modul-Manager** **aktiviert** ist.
-   **A:** Gehen Sie als Nächstes zur Konfigurationsseite des Moduls und stellen Sie sicher, dass „Experten auf Produktseite anzeigen“ auf **JA** eingestellt ist.
-   **A:** Vergewissern Sie sich, dass Sie tatsächlich einen Experten dem spezifischen Produkt, seiner Kategorie, Marke oder seinem Lieferanten unter **Produktexperte > Experten > [Experten bearbeiten] > Zuweisungen** **zugewiesen** haben.
-   **A:** Überprüfen Sie den Schalter „Aktiv“ für den einzelnen Experten unter **Produktexperte > Experten**. Wenn dieser inaktiv ist, wird er nicht angezeigt.
-   **A:** Leeren Sie Ihren PrestaShop-Cache: Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie dann oben rechts auf „Cache leeren“. Manchmal verhindern alte Cache-Inhalte, dass neue Modulelemente angezeigt werden.

**F2: Die Expertenkarten sehen seltsam aus oder passen nicht zum Design meines Themes.**

-   **A:** Das Modul bietet in seiner Konfiguration ein „Standard-Expertenkarten-Layout“ und ein „Standard-Expertenlisten-Layout“. Experimentieren Sie mit verschiedenen Optionen, um zu sehen, welche am besten zu Ihrem Theme passt.
-   **A:** Wenn Sie ein benutzerdefiniertes Theme haben, kann es spezifische CSS-Regeln geben, die mit dem Styling des Moduls in Konflikt stehen. Möglicherweise benötigen Sie einen Webentwickler, um das CSS zu überprüfen und kleinere Anpassungen vorzunehmen.
-   **A:** Stellen Sie sicher, dass Ihr Theme auf dem neuesten Stand ist. Veraltete Themes können manchmal Anzeigeprobleme mit neueren Modulen verursachen.

**F3: Das Kontaktformular sendet keine E-Mails.**

-   **A:** Stellen Sie zunächst sicher, dass „Kontaktformular aktivieren“ in der Modulkonfiguration auf **JA** eingestellt ist.
-   **A:** Überprüfen Sie, ob die E-Mail-Adresse des Experten in seinem Profil (**Produktexperte > Experten > [Experten bearbeiten]**) korrekt eingegeben ist.
-   **A:** Überprüfen Sie Ihre PrestaShop-E-Mail-Einstellungen (**Erweiterte Einstellungen > E-Mail**). Senden Sie eine Test-E-Mail von PrestaShop, um sicherzustellen, dass die E-Mail-Konfiguration Ihres Shops korrekt funktioniert. Wenn PrestaShop keine E-Mails senden kann, kann das Modul dies auch nicht.
-   **A:** Überprüfen Sie die Mail-Protokolle Ihres Servers auf Fehler. Dies erfordert möglicherweise Unterstützung von Ihrem Hosting-Anbieter.

**F4: Wie übersetze ich den Text des Moduls in andere Sprachen?**

-   **A:** Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
-   **A:** Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann das Modul „Produktexperte - Spezialisten-Visitenkarten“ aus.
-   **A:** Sie können dann alle Zeichenketten des Moduls in Ihre gewünschten Sprachen übersetzen. Denken Sie daran, Ihre Änderungen zu speichern.

**F5: Ich möchte Experten an einem anderen Ort als den verfügbaren Hooks anzeigen.**

-   **A:** Das Modul bietet eine Auswahl an Standard-PrestaShop-Hooks. Wenn Sie Experten an einem sehr spezifischen, nicht standardmäßigen Ort anzeigen müssen (z. B. innerhalb eines benutzerdefinierten Tabs oder eines einzigartigen Abschnitts Ihrer Produktseitenvorlage), erfordert dies eine benutzerdefinierte Theme-Entwicklung. Ein Webentwickler müsste die Hook-Funktion des Moduls manuell direkt in den `.tpl`-Dateien Ihres Themes aufrufen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Architektur und den Code des Moduls „Produktexperte - Spezialisten-Visitenkarten“, der für Entwickler, Webmaster und technische Agenturen bestimmt ist.

### 4.1 Architekturübersicht

Das Modul „Produktexperte - Spezialisten-Visitenkarten“ folgt einem standardmäßigen PrestaShop MVC-Muster (Model-View-Controller) und nutzt `ObjectModel` stark für die Datenpersistenz. Es führt benutzerdefinierte Admin-Controller zur Verwaltung von Experten und deren Zuweisungen sowie Front-Controller für AJAX-Interaktionen und die Anzeige von Experteninformationen ein. Das Modul verwendet eine robuste Klassenstruktur zur Verwaltung von Expertenkarten-Layouts, Stilen und Präsentationslogik, was eine hohe Anpassbarkeit ermöglicht. Es integriert sich mit verschiedenen PrestaShop-Hooks, um seinen Inhalt dynamisch in das Front Office einzufügen.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

-   `controllers/front/ajax.php`
    -   **Klassenname:** `ProductexpertAjaxModuleFrontController` (erweitert `ModuleFrontController`)
    -   **Verantwortlichkeit:** Behandelt AJAX-Anfragen vom Front Office. Dies umfasst typischerweise die Verarbeitung von Experten-Kontaktformular-Einreichungen, das dynamische Laden von Expertendaten oder andere interaktive Elemente, die eine serverseitige Kommunikation ohne vollständiges Neuladen der Seite erfordern. Es gibt JSON-Antworten zurück.
-   `controllers/front/index.php`
    -   **Klassenname:** `ProductexpertIndexModuleFrontController` (erweitert `ModuleFrontController`)
    -   **Verantwortlichkeit:** Ein Platzhalter oder Standard-Front-Controller. In vielen Modulen könnte dies eine dedizierte Modulseite behandeln, falls eine existiert, oder einfach umleiten, wenn seine primäre Funktion über Hooks oder AJAX erfolgt. Für dieses Modul ist seine primäre Rolle wahrscheinlich minimal, wobei `ajax.php` die meisten Front-End-Interaktionen übernimmt.

#### Back-Office-Admin-Controller

-   `controllers/admin/AdminProductExpertController.php`
    -   **Klassenname:** `AdminProductExpertController` (erweitert `ModuleAdminController`)
    -   **Tab-Name:** „Experten“ unter dem Menü „Produktexperte“.
    -   **Verwaltete Entität:** `ProductExpertExpert` (über `classes/ProductExpertExpert.php`).
    -   **Verantwortlichkeit:** Dies ist der Hauptadministrations-Controller zur Verwaltung individueller Expertenprofile. Er verwaltet die Auflistung von Experten (mithilfe von `HelperList`) und die Erstellungs-/Bearbeitungsformulare für Experten (mithilfe von `HelperForm`). Er verwaltet die CRUD-Operationen für Expertendaten, einschließlich Name, Rolle, Biografie, Foto, Kontaktlinks und, am wichtigsten, deren Zuweisungen zu Produkten, Kategorien, Marken und Lieferanten. Er verwaltet auch die Layout-Überschreibungen für einzelne Expertenkarten.
-   `controllers/admin/index.php`
    -   **Klassenname:** (Keine spezifische Klasse, oft eine Umleitung oder Sicherheitsmaßnahme)
    -   **Verantwortlichkeit:** Diese Datei ist typischerweise eine Sicherheitsmaßnahme, um direkte Verzeichnisauflistungen oder Zugriffe zu verhindern. Sie enthält oft ein einfaches `header('Location: ../../index.php'); exit;` oder Ähnliches, um zum Haupt-Admin-Panel umzuleiten. Sie verwaltet keine spezifische Entität oder Form.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul verfügt über einen reichen Satz von Klassen zur Verwaltung seiner komplexen Funktionen, insbesondere im Bereich der Expertenkarten-Layouts und Konfigurationen.

-   `classes/ProductExpertExpert.php`
    -   **Datenbanktabelle:** `ps_productexpert_expert`
    -   **Erweitert:** `ObjectModel`
    -   **`$definition`-Felder:** Definiert das Schema für Expertenprofile (id\_expert, name, role, bio, photo\_id, active, date\_add, date\_upd, layout\_preset\_id). Behandelt mehrsprachige Felder, falls zutreffend.
    -   **Wichtige öffentliche Methoden:** Methoden zum Speichern, Abrufen und Löschen von Expertendaten. Enthält Logik zur Handhabung von Foto-Uploads und -Zuordnungen.
-   `classes/ProductExpertExpertLinks.php`
    -   **Datenbanktabelle:** `ps_productexpert_expert_link`
    -   **Erweitert:** `ObjectModel`
    -   **`$definition`-Felder:** Definiert das Schema für Experten-Kontaktlinks (id\_expert\_link, id\_expert, type, value, icon, position).
    -   **Wichtige öffentliche Methoden:** Verwaltet die verschiedenen Kontaktlinks (E-Mail, Telefon, WhatsApp, LinkedIn, benutzerdefiniert), die einem Experten zugeordnet sind.
-   `classes/ProductExpertExpertPhoto.php`
    -   **Datenbanktabelle:** `ps_productexpert_expert_photo`
    -   **Erweitert:** `ObjectModel`
    -   **`$definition`-Felder:** Verwaltet Expert-Fotodetails (id\_photo, filename, mime\_type, size).
    -   **Wichtige öffentliche Methoden:** Handhabt die Speicherung und den Abruf von Expertenprofilbildern.
-   `classes/ProductExpertConfig.php`
    -   **Datenbanktabelle:** `ps_configuration` (speichert Konfigurationswerte)
    -   **Erweitert:** (Wahrscheinlich nicht `ObjectModel`, sondern eine Dienstprogrammklasse)
    -   **Wichtige öffentliche Methoden:** Bietet statische Methoden zum Abrufen und Festlegen modulspezifischer Konfigurationswerte (z. B. `PE_DISPLAY_ON_PRODUCT_PAGE`, `PE_CONTACT_FORM_ENABLED`).
-   `classes/ProductExpertResolver.php`
    -   **Erweitert:** (Wahrscheinlich eine benutzerdefinierte Klasse)
    -   **Wichtige öffentliche Methoden:** Enthält die Kernlogik zur Bestimmung, welche Experten für ein bestimmtes Produkt basierend auf dessen Kategorie, Marke, Lieferanten und direkten Produktzuweisungen angezeigt werden sollen. Es löst die Expertenliste für das Front Office auf.
-   `classes/ProductExpertListPresenter.php`
    -   **Erweitert:** (Wahrscheinlich eine benutzerdefinierte Klasse)
    -   **Wichtige öffentliche Methoden:** Verantwortlich für die Aufbereitung der Daten aufgelöster Experten in ein Format, das für die Anzeige in den Smarty-Templates geeignet ist, unter Anwendung ausgewählter Listenlayouts (Raster, Karussell, Liste).
-   `classes/ExpertCardLayout.php`, `ExpertCardLayoutPresets.php`, `ExpertCardLayoutPresetsBuiltin.php`, `ExpertCardLayoutPresetsBuiltinData.php`, `ExpertCardLayoutPresetsFilesystem.php`, `ExpertCardLayoutInstances.php`
    -   **Erweitert:** (Wahrscheinlich benutzerdefinierte Klassen)
    -   **Verantwortlichkeit:** Ein komplexer Satz von Klassen, die sich der Verwaltung des visuellen Designs und der Struktur von Experten-Visitenkarten widmen. Dies umfasst die Definition von Layoutelementen, Stilen, Verläufen und die Handhabung integrierter Voreinstellungen sowie benutzerdefinierter Layouts, die vom Benutzer gespeichert wurden. Dies ist der Kern der Funktionalität des „Visuellen Visitenkarten-Designers“.
-   `classes/ExpertCardAdminUi.php`, `ProductExpertSettingsAdminUi.php`, `ProductExpertListLayoutAdminUi.php`
    -   **Erweitert:** (Wahrscheinlich benutzerdefinierte Klassen)
    -   **Verantwortlichkeit:** Hilfsklassen zum Rendern der komplexen UI-Elemente in den Back Office-Konfigurationsformularen, insbesondere für das Layout-Studio und die allgemeinen Moduleinstellungen.
-   `classes/PeCompatibility.php`
    -   **Erweitert:** (Wahrscheinlich eine Dienstprogrammklasse)
    -   **Wichtige öffentliche Methoden:** Bietet Methoden zur Handhabung von Kompatibilitätsproblemen über verschiedene PrestaShop-Versionen hinweg (z. B. Unterschiede in Hook-Namen, API-Aufrufen oder veralteten Funktionen).
-   `classes/ProductExpertInstallSamples.php`
    -   **Erweitert:** (Wahrscheinlich eine Dienstprogrammklasse)
    -   **Wichtige öffentliche Methoden:** Enthält Logik zur Installation von Beispieldaten (z. B. Beispiel-Experten, Layouts) während der Modulinstallation, um Händlern einen schnellen Start zu ermöglichen.

### 4.4 JavaScript-Assets (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    -   **Geltungsbereich:** Front-Office.
    -   **Beschreibung:** Bietet Autocomplete-Funktionalität für das Experten-Suchwerkzeug, das Expert-Namen oder Spezialitäten vorschlägt, während der Benutzer tippt.
-   `lib/searchTool/views/pe-searchtool-init.js`
    -   **Geltungsbereich:** Front-Office.
    -   **Beschreibung:** Initialisiert das Experten-Suchwerkzeug, bindet Event-Listener an das Suchfeld und integriert die Autocomplete-Funktionalität.
-   `views/js/admin-element-editor.js`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Treibt den visuellen Editor für einzelne Elemente innerhalb eines Expertenkarten-Layouts an (z. B. Textfelder, Bilder, Symbole). Handhabt Drag-and-Drop, Größenänderung und Anpassungen von Stil-Eigenschaften.
-   `views/js/admin-expert-photo.js`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Verwaltet die Foto-Upload- und Vorschau-Funktionalität für Expertenprofile im Admin-Panel.
-   `views/js/admin-layout-studio.js`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Das Haupt-JavaScript für den „Visuellen Visitenkarten-Designer“. Es verwaltet die gesamte Layout-Leinwand, die Elementverwaltung, das Speichern/Laden von Layouts und das Anwenden von Stilen.
-   `views/js/admin-list-layout-studio.js`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Verwaltet das Studio zum Entwerfen, wie mehrere Expertenkarten angezeigt werden (Raster, Karussell, Liste), einschließlich Optionen für Responsivität und Navigation.
-   `views/js/front.js`
    -   **Geltungsbereich:** Front-Office.
    -   **Beschreibung:** Enthält allgemeines Front-Office-JavaScript für das Modul, einschließlich:
        -   Event-Listener für die Übermittlung des Kontaktformulars (AJAX-Aufrufe an `ajax.php`).
        -   Logik zum Anzeigen und Ausblenden des Kontaktformular-Modals.
        -   Initialisierung von Karussell- oder Slider-Funktionalitäten für Expertenlisten.
        -   Allgemeine UI-Verbesserungen für Expertenkarten.

### 4.5 CSS-Stylesheets (`views/css/`)

#### Front-Office-CSS

-   `lib/searchTool/views/css/autocomplete.css`
    -   **Geltungsbereich:** Front-Office.
    -   **Beschreibung:** Stile für die Autocomplete-Dropdown-Vorschläge im Experten-Suchwerkzeug.
-   `views/css/front.css`
    -   **Geltungsbereich:** Front-Office.
    -   **Beschreibung:** Allgemeine Front-Office-Stile für das Modul, einschließlich grundlegendem Layout, Typografie und Responsivität für Expertenkarten und -listen.
-   `views/css/pe-expert-card-front.css`
    -   **Geltungsbereich:** Front-Office.
    -   **Beschreibung:** Spezifisches Styling für die einzelnen Experten-Visitenkarten, das das gewählte Layout und die Elementstile anwendet.
-   `views/css/pe-front-contact.css`
    -   **Geltungsbereich:** Front-Office.
    -   **Beschreibung:** Stile für das Experten-Kontaktformular, einschließlich Modal-Präsentation, Eingabefeldern und Schaltflächen.
-   `views/css/pe-front-experts.css`
    -   **Geltungsbereich:** Front-Office.
    -   **Beschreibung:** Stile für die Gesamtanzeige mehrerer Experten, wie z. B. Rasterlayouts, Listenlayouts oder Karussell-Navigation.

#### Back-Office-CSS

-   `views/css/admin-config.css`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Allgemeine Stile für die Hauptkonfigurationsseite des Moduls im Admin-Panel.
-   `views/css/admin-element-editor.css`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Stile für den visuellen Element-Editor innerhalb des Layout-Studios.
-   `views/css/admin-expert-card-studio.css`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Kern-CSS für die Benutzeroberfläche des Expertenkarten-Layout-Studios.
-   `views/css/admin-expert-photo.css`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Stile für den Expertenfoto-Upload- und Vorschau-Bereich in den Admin-Formularen.
-   `views/css/admin-experts-list.css`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Stile für die Listenansicht von Experten in `AdminProductExpertController`.
-   `views/css/admin-layout-builder.css`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Stile im Zusammenhang mit den Layout-Building-Komponenten.
-   `views/css/admin-layout-studio.css`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Umfassende Stile für die Benutzeroberfläche des Layout-Studios.
-   `views/css/admin-list-layout-studio.css`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Stile für die Benutzeroberfläche des Listenlayout-Studios.
-   `views/css/admin-pe-overrides.css`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Spezifische CSS-Überschreibungen oder Anpassungen für die Standard-Admin-Stile von PrestaShop, um die Konsistenz der Modul-Benutzeroberfläche zu gewährleisten.
-   `views/css/admin-searchtool.css`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Stile für das Suchwerkzeug im Admin-Panel (falls zutreffend, z. B. zum Suchen von Produkten/Kategorien während der Zuweisung).

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   `lib/searchTool/views/scripts.tpl`
    -   **Geltungsbereich:** Front-Office.
    -   **Beschreibung:** Enthält wahrscheinlich die notwendigen JavaScript- und CSS-Dateien für das Suchwerkzeug, oft in `displayHeader` oder `displayFooter` eingehängt, um Assets zu laden.
-   `views/templates/admin/configure.tpl`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Das Haupt-Template für die Konfigurationsseite des Moduls (`getContent()`-Methode), das das allgemeine Einstellungsformular rendert.
-   `views/templates/admin/list-layout.tpl`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Template für das Listenlayout-Studio im Admin, das die Konfiguration der Anzeige mehrerer Expertenkarten ermöglicht.
-   `views/templates/admin/product-tab.tpl`
    -   **Geltungsbereich:** Back-Office.
    -   **Beschreibung:** Dieses Template wird wahrscheinlich verwendet, um einen benutzerdefinierten Tab oder Abschnitt in die PrestaShop-Produktbearbeitungsseite einzufügen, der die direkte Zuweisung von Experten zu einem Produkt vom Bearbeitungsbildschirm aus ermöglicht.
-   `views/templates/hook/product-experts.tpl`
    -   **Geltungsbereich:** Front-Office.
    -   **Hook:** `displayProductButtons`, `displayProductExtraContent`, `displayRightColumn`, `displayLeftColumn`, `displayFooter` (wie konfiguriert).
    -   **Beschreibung:** Das primäre Template, das für das Rendern des Blocks von Expertenkarten im Front Office verantwortlich ist. Es iteriert durch die aufgelösten Experten und enthält `_pe-expert-card-element.tpl` für jeden.
-   `views/templates/hook/_pe-expert-card-element.tpl`
    -   **Geltungsbereich:** Front-Office.
    -   **Hook:** Eingebunden von `product-experts.tpl`.
    -   **Beschreibung:** Rendert eine einzelne Experten-Visitenkarte, wendet das gewählte Layout an und zeigt das Foto, den Namen, die Rolle, die Biografie und die Kontaktlinks des Experten an. Es enthält wahrscheinlich `_pe-expert-card-row.tpl` für strukturierte Inhalte.
-   `views/templates/hook/_pe-expert-card-row.tpl`
    -   **Geltungsbereich:** Front-Office.
    -   **Hook:** Eingebunden von `_pe-expert-card-element.tpl`.
    -   **Beschreibung:** Rendert eine einzelne Zeile oder einen Abschnitt innerhalb einer Expertenkarte, der zum Strukturieren der Inhaltselemente verwendet wird (z. B. eine Zeile für Kontaktsymbole, eine Zeile für Name und Rolle).

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

-   `ps_productexpert_expert`: Speichert Kerninformationen des Expertenprofils (Name, Rolle, Biografie, Foto-ID, aktiver Status, Layout-Voreinstellung).
-   `ps_productexpert_expert_lang`: Speichert mehrsprachige Felder für Experten (falls vorhanden, z. B. Biografie).
-   `ps_productexpert_expert_link`: Speichert individuelle Kontaktlinks für jeden Experten (Typ, Wert, Symbol).
-   `ps_productexpert_expert_photo`: Speichert Metadaten für Expertenprofilbilder.
-   `ps_productexpert_expert_product`: Many-to-many-Beziehungstabelle, die Experten mit Produkten verknüpft.
-   `ps_productexpert_expert_category`: Many-to-many-Beziehungstabelle, die Experten mit Kategorien verknüpft.
-   `ps_productexpert_expert_manufacturer`: Many-to-many-Beziehungstabelle, die Experten mit Marken (Herstellern) verknüpft.
-   `ps_productexpert_expert_supplier`: Many-to-many-Beziehungstabelle, die Experten mit Lieferanten verknüpft.
-   `ps_productexpert_layout_preset`: Speichert Definitionen von benutzerdefinierten Expertenkarten-Layouts, die vom Händler erstellt wurden.
-   `ps_productexpert_list_layout`: Speichert Definitionen von benutzerdefinierten Expertenlisten-Layouts (Raster, Karussell usw.).
-   `ps_configuration`: Speichert globale Konfigurationseinstellungen des Moduls (z. B. `PE_DISPLAY_ON_PRODUCT_PAGE`, `PE_DEFAULT_CARD_LAYOUT_ID`).

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Abschnitt jeder Seite. | Laden von CSS- und JS-Assets des Moduls für das Front-Office. |
| `displayBackOfficeHeader` | Im `<head>`-Abschnitt jeder Back Office-Seite. | Laden von CSS- und JS-Assets des Moduls für Admin-Bildschirme. |
| `displayModuleConfigureExtraButtons` | Auf der Modul-Manager-Seite, neben der Schaltfläche „Konfigurieren“. | Schnelle Links zu „Experten verwalten“ oder „Layout Studio“ hinzufügen. |
| `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | Den Expertenzuweisungs-Tab/Abschnitt für Produkte einfügen. |
| `displayProductButtons` | In der Nähe der Schaltfläche „In den Warenkorb“ auf Produktseiten. | Expertenkarten in einem prominenten produktspezifischen Bereich anzeigen. |
| `displayProductExtraContent` | In einem dedizierten Abschnitt/Tab auf Produktseiten. | Expertenkarten als zusätzlichen Produktinhalt anzeigen. |
| `displayLeftColumn` | In der linken Seitenleiste der zutreffenden Seiten. | Expertenkarten oder das Experten-Suchwerkzeug in der linken Spalte anzeigen. |
| `displayRightColumn` | In der rechten Seitenleiste der zutreffenden Seiten. | Expertenkarten oder das Experten-Suchwerkzeug in der rechten Spalte anzeigen. |
| `displayFooter` | Im Footer-Abschnitt aller Seiten. | Expertenkarten oder einen Link zu einer Expertenseite im Footer anzeigen. |
| `displayTop` | Im oberen Bereich des Shops (Header). | Das Experten-Suchwerkzeug für globalen Zugriff anzeigen. |
| `displayNav` | In der Navigationsleiste (oft über `displayTop`). | Das Experten-Suchwerkzeug für globalen Zugriff anzeigen. |
| `actionFrontControllerSetMedia` | Bevor der Front-Controller rendert, zum Hinzufügen von Assets. | Dynamisches Hinzufügen von Front-Office-spezifischem JS/CSS basierend auf dem Kontext. |
| `actionAdminControllerSetMedia` | Bevor der Admin-Controller rendert, zum Hinzufügen von Assets. | Dynamisches Hinzufügen von Back-Office-spezifischem JS/CSS basierend auf dem Kontext. |
| `actionObjectProductAddAfter` | Nachdem ein neues Produkt hinzugefügt wurde. | Potenziell Expertenzuweisungslogik oder Cache-Löschung auslösen. |
| `actionObjectProductUpdateAfter` | Nachdem ein Produkt aktualisiert wurde. | Potenziell Expertenzuweisungslogik oder Cache-Löschung auslösen. |
| `actionObjectProductDeleteAfter` | Nachdem ein Produkt gelöscht wurde. | Alle Expertenzuweisungen im Zusammenhang mit dem gelöschten Produkt bereinigen. |
| `actionObjectCategoryUpdateAfter` | Nachdem eine Kategorie aktualisiert wurde. | Cache im Zusammenhang mit kategoriebasierten Expertenzuweisungen leeren. |
| `actionObjectManufacturerUpdateAfter` | Nachdem ein Hersteller (Marke) aktualisiert wurde. | Cache im Zusammenhang mit markenbasierten Expertenzuweisungen leeren. |
| `actionObjectSupplierUpdateAfter` | Nachdem ein Lieferant aktualisiert wurde. | Cache im Zusammenhang mit lieferantenbasierten Expertenzuweisungen leeren. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen technischen Support besuchen Sie bitte Ihr Kundenkonto bei MyPresta.eu. Unser Team ist bestrebt, umfassende Unterstützung zu bieten und sicherzustellen, dass Ihr Modul reibungslos funktioniert.

-   **MyPresta.eu Bestellverlauf & Downloads:** <https://mypresta.eu/my-account/orders/>
-   **MyPresta.eu Support:** Greifen Sie über Ihr Konto auf unser Support-Portal zu, um direkte Unterstützung zu erhalten.

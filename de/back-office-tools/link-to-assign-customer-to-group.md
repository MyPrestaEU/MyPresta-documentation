---
title: "Link zum Zuweisen eines Kunden zu einer Gruppe – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Link zum Zuweisen eines Kunden zu einer Gruppe' von MyPresta.eu."
sidebar:
  label: "Link zum Zuweisen eines Kunden zu einer Gruppe"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Link to assign customer to group auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/link-to-assign-customer-to-group.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/link-to-assign-customer-to-group/)
>
> ---


# Link zum Zuweisen eines Kunden zu einer Gruppe

## 1. Anforderungen & Kompatibilität
-   **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **PHP-Kompatibilität**: PHP 5.6 - 8.5
-   **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Modul-Manager > Link zum Zuweisen eines Kunden zu einer Gruppe konfigurieren)

Dies ist der Haupt- und einzige Konfigurationsbildschirm für das Modul. Hier können Sie definieren, wie sich das Modul verhält, wenn Kunden Gruppen zugewiesen werden.

#### **Gruppe auf Standard ändern**
-   **Was diese Einstellung bewirkt:** Diese Einstellung bestimmt, ob das Modul den Kunden zusätzlich zu der in der URL angegebenen Gruppe auch der "Standard"-Kundengruppe zuweisen soll.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (JA):* Wenn ein Kunde auf einen Link klickt, um der "Gruppe X" zugewiesen zu werden, wird er auch der "Standard"-Gruppe zugewiesen. Das bedeutet, er wird sowohl Teil von "Gruppe X" als auch von "Standard" sein. Dies kann nützlich sein, wenn Ihre "Standard"-Gruppe bestimmte Basisberechtigungen oder Rabatte hat, die Kunden immer haben sollen, unabhängig von anderen Gruppen, denen sie beitreten.
    -   *Wenn deaktiviert (NEIN):* Der Kunde wird nur der in der URL angegebenen Gruppe (z. B. "Gruppe X") zugewiesen. Er wird nicht automatisch zur "Standard"-Gruppe hinzugefügt, es sei denn, er ist bereits Teil davon oder ein anderer Mechanismus fügt ihn hinzu.
-   **Empfohlener Wert:** **NEIN**. In den meisten Fällen möchten Sie Kunden einer *spezifischen* Gruppe zuweisen, ohne sie unbedingt der "Standard"-Gruppe hinzuzufügen, insbesondere wenn Ihre "Standard"-Gruppe keine besondere Bedeutung hat oder wenn Sie Gruppen präziser verwalten möchten. Aktivieren Sie dies nur, wenn Sie einen spezifischen Grund haben, die "Standard"-Gruppe immer einzuschließen.
-   **Händlerszenario / Beispiel:** Sie haben eine "VIP"-Gruppe mit speziellen Rabatten. Wenn Sie dies aktivieren, ist ein Kunde, der auf einen VIP-Link klickt, sowohl in "VIP" als auch in "Standard". Wenn "Standard" einen shopweiten Rabatt von 5 % und "VIP" einen Rabatt von 15 % auf bestimmte Produkte hat, profitiert der Kunde von beiden, wo zutreffend. Wenn deaktiviert, würde er nur die "VIP"-Vorteile erhalten.

#### **Kunden aus anderen Gruppen entfernen**
-   **Was diese Einstellung bewirkt:** Diese Einstellung steuert, ob das Modul den Kunden aus *allen anderen* Kundengruppen entfernen soll, wenn er über den speziellen Link einer neuen Gruppe zugewiesen wird.
-   **Auswirkung der Änderung dieser Einstellung:**
    -   *Wenn aktiviert (JA):* Wenn ein Kunde derzeit in "Gruppe A" und "Gruppe B" ist und dann auf einen Link klickt, um der "Gruppe X" zugewiesen zu werden, wird er aus "Gruppe A" und "Gruppe B" entfernt und bleibt nur in "Gruppe X" (und möglicherweise "Standard", wenn die vorherige Einstellung aktiviert ist). Dies stellt sicher, dass der Kunde *nur* in der Zielgruppe ist.
    -   *Wenn deaktiviert (NEIN):* Der Kunde wird der neuen Gruppe ("Gruppe X") *hinzugefügt*, bleibt aber in allen anderen Gruppen, denen er bereits angehörte (z. B. "Gruppe A", "Gruppe B"). Dies ermöglicht es Kunden, gleichzeitig Mitglied mehrerer Gruppen zu sein.
-   **Empfohlener Wert:** **NEIN**. Kunden die Mitgliedschaft in mehreren Gruppen zu ermöglichen, bietet mehr Flexibilität für komplexe Segmentierungen. Aktivieren Sie dies nur, wenn Sie strikte, sich gegenseitig ausschließende Gruppen benötigen (z. B. ein Kunde kann nur "Einzelhandel" ODER "Großhandel" sein, niemals beides).
-   **Händlerszenario / Beispiel:**
    -   *Aktiviert (JA):* Sie haben die Gruppen "Standardkunde" und "Großhandelskunde". Ein Kunde klickt auf einen Link, um "Großhandel" zu werden. Wenn aktiviert, wird er aus "Standardkunde" entfernt und bleibt nur "Großhandel". Dies ist ideal für klare, unterschiedliche Kundentypen.
    -   *Deaktiviert (NEIN):* Sie haben die Gruppen "Newsletter-Abonnent" und "Treueprogramm-Mitglied". Ein Kunde klickt auf einen Link, um dem "Treueprogramm" beizutreten. Wenn deaktiviert, bleibt er "Newsletter-Abonnent" *und* wird "Treueprogramm-Mitglied". Dies ist ideal für additive Vorteile.

#### **So erstellen Sie den speziellen Link**
Das Modul funktioniert, indem es einen speziellen Parameter zu jeder URL in Ihrem Shop hinzufügt. Das Parameterformat ist: `?asg={group_id}`

1.  **Finden Sie die Gruppen-ID:**
    -   Gehen Sie in Ihrem PrestaShop Back Office zu **Kunden > Gruppen**.
    -   Notieren Sie sich die ID-Nummer neben der Gruppe, der Sie Kunden zuweisen möchten. Wenn zum Beispiel "Großhandel" eine ID von `3` hat, dann ist `3` Ihre `group_id`.
2.  **Erstellen Sie den Link:**
    -   Nehmen Sie eine beliebige URL aus Ihrem Shop (z. B. `https://ihrshop.com/`)
    -   Fügen Sie `?asg={group_id}` hinzu.
    -   **Beispiel:** Um einen Kunden der Gruppe mit der ID `3` (z. B. "Großhandel") zuzuweisen und ihn auf Ihre Startseite umzuleiten: `https://ihrshop.com/?asg=3`
    -   **Beispiel:** Um einen Kunden der Gruppe mit der ID `5` (z. B. "VIP") zuzuweisen und ihn auf eine bestimmte Produktseite umzuleiten: `https://ihrshop.com/de/produkt/123-tolles-produkt?asg=5`

:::warning
Der `asg`-Parameter muss der *erste* Parameter sein, wenn keine anderen Parameter in der URL vorhanden sind (d.h. verwenden Sie `?`). Wenn die URL bereits Parameter enthält (z. B. `https://ihrshop.com/kategorie/1-kleidung?id_category=1`), müssen Sie `&` verwenden, um den `asg`-Parameter hinzuzufügen: `https://ihrshop.com/kategorie/1-kleidung?id_category=1&asg=3`.
:::

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Modulkonfiguration | Gruppe auf Standard ändern | NEIN | Wenn JA, wird der Kunde auch der 'Standard'-Gruppe hinzugefügt. Wenn NEIN, nur der angegebenen Gruppe. |
| Modulkonfiguration | Kunden aus anderen Gruppen entfernen | NEIN | Wenn JA, wird der Kunde aus allen anderen Gruppen entfernt. Wenn NEIN, bleibt der Kunde in bestehenden Gruppen und wird der neuen hinzugefügt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Der Kunde hat auf den Link geklickt, wurde aber der Gruppe nicht zugewiesen. Was ist falsch?**
A:
1.  **Kunde nicht angemeldet:** Das Modul funktioniert nur für *angemeldete* Kunden. Wenn sie nicht angemeldet waren, werden sie einfach auf die Seite weitergeleitet, ohne Gruppenzuweisung.
2.  **Falsche Gruppen-ID:** Überprüfen Sie die `group_id` in Ihrer URL mit der tatsächlichen ID unter **Kunden > Gruppen**.
3.  **Falscher URL-Parameter:** Stellen Sie sicher, dass Sie `?asg=` für den ersten Parameter und `&asg=` für nachfolgende Parameter verwenden.
4.  **Modul nicht aktiviert:** Überprüfen Sie, ob das Modul unter **Module > Modul-Manager** installiert und aktiviert ist.
5.  **Cache:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren) und Ihren Browser-Cache.

**F: Kann ich einen Kunden mit einem Link mehreren Gruppen zuweisen?**
A: Nein, der `asg`-Parameter unterstützt nur die Zuweisung zu einer Gruppe gleichzeitig. Wenn jedoch "Kunden aus anderen Gruppen entfernen" auf NEIN gesetzt ist, wird der Kunde der neuen Gruppe *hinzugefügt*, während er die Mitgliedschaft in seinen bestehenden Gruppen behält.

**F: Beeinflusst dieses Modul die SEO?**
A: Nein, dieses Modul hat keinen direkten Einfluss auf die SEO Ihres Shops. Der `asg`-Parameter ist ein dynamischer Parameter, den Suchmaschinen typischerweise ignorieren.

**F: Was passiert, wenn ein Kunde den Link mehrmals anklickt?**
A: Wenn der Kunde bereits in der Zielgruppe ist, ändert sich nichts. Wenn nicht, wird er ihr zugewiesen. Das Modul ist so konzipiert, dass es dies fehlerfrei handhabt.

**F: Ich möchte einen Kunden über einen Link aus einer Gruppe entfernen. Ist das möglich?**
A: Nein, dieses Modul ist nur für das *Zuweisen* von Kunden zu Gruppen konzipiert. Es bietet keine Funktionalität, um Kunden über eine URL aus Gruppen zu entfernen. Dies müssten Sie manuell im Back Office oder mit einem anderen Modul/einer benutzerdefinierten Entwicklung tun.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht
Das Modul "Link zum Zuweisen eines Kunden zu einer Gruppe" (`assigntogroup`) ist ein leichtgewichtiges PrestaShop-Modul, das hauptsächlich dazu dient, Front-Office-Anfragen abzufangen und Kundengruppenzuweisungen basierend auf einem URL-Parameter zu ändern. Es nutzt PrestaShops Hook-System (`displayHeader`), um seine Logik frühzeitig im Seitenladevorgang auszuführen und sicherzustellen, dass Gruppenänderungen angewendet werden, bevor der Seiteninhalt gerendert wird. Es führt keine benutzerdefinierten Controller, Modelle oder komplexe JavaScript/CSS ein. Seine Kernfunktionalität liegt innerhalb der Hauptmodulklasse.

### 4.2 Controller (`controllers/`)
-   **Front-Office-Controller**: Keine. Die Logik des Moduls wird über einen Hook ausgeführt, nicht über einen dedizierten Front-Controller.
-   **Back-Office-Admin-Controller**: Keine. Die gesamte Konfiguration wird innerhalb der `getContent()`-Methode des Hauptmoduls gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)
-   Es sind keine benutzerdefinierten Klassen oder ObjectModels im Verzeichnis `classes/` definiert. Das Modul interagiert direkt mit den PrestaShop-Kern-ObjectModels `Customer` und `Group`.

### 4.4 JavaScript-Assets (`views/js/`)
-   Mit diesem Modul sind keine JavaScript-Dateien enthalten.

### 4.5 CSS-Stylesheets (`views/css/`)
-   Mit diesem Modul sind keine CSS-Dateien enthalten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**:
    *   `assigntogroup/views/templates/hook/form.tpl`
        *   **Zweck**: Dieses Template wird verwendet, um das Konfigurationsformular des Moduls im PrestaShop Back Office zu rendern. Es wird von der `getContent()`-Methode der Hauptmodulklasse gerendert.
        *   **Inhalt**: Enthält die HTML-Struktur für die beiden Konfigurationsschalter (`asg_unassign`, `asg_default`) und die Schaltfläche zum Absenden des Formulars. Es verwendet PrestaShops Standard-Hilfsformular-Elemente.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:
    *   Das Modul erstellt keine benutzerdefinierten SQL-Tabellen.
    *   Es speichert seine Konfigurationseinstellungen in der Tabelle `ps_configuration`:
        *   `PS_ASG_UNASSIGN`: Speichert den Wert der Einstellung "Kunden aus anderen Gruppen entfernen" (0 oder 1).
        *   `PS_ASG_DEFAULT`: Speichert den Wert der Einstellung "Gruppe auf Standard ändern" (0 oder 1).

-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Wird frühzeitig beim Laden der Front-Office-Seite innerhalb des `<head>`-Abschnitts ausgeführt. | Dies ist der primäre Hook, der vom Modul verwendet wird. Er prüft auf den `asg`-URL-Parameter, verifiziert, ob ein Kunde angemeldet ist, und führt dann die Gruppenzuweisungslogik basierend auf den Konfigurationseinstellungen des Moduls (`PS_ASG_UNASSIGN`, `PS_ASG_DEFAULT`) aus. |

### 4.8 Haupt-Modul-PHP-Datei (`assigntogroup/assigntogroup.php`)

Dies ist die zentrale Datei für das Modul, die seine Installation, Deinstallation, Konfiguration und Kernlogik enthält.

-   **Klassenname**: `Assigntogroup`
-   **Elternklasse**: `Module`
-   **Schlüsselmethoden**:
    *   `__construct()`: Initialisiert Modulmetadaten (Name, Tab, Version, Autor usw.).
    *   `install()`:
        *   Registriert den `displayHeader`-Hook.
        *   Setzt Standardkonfigurationswerte für `PS_ASG_UNASSIGN` (0) und `PS_ASG_DEFAULT` (0) in `ps_configuration`.
        *   Gibt bei Erfolg `true` zurück.
    *   `uninstall()`:
        *   Hebt die Registrierung des `displayHeader`-Hooks auf.
        *   Löscht die Konfigurationswerte `PS_ASG_UNASSIGN` und `PS_ASG_DEFAULT` aus `ps_configuration`.
        *   Gibt bei Erfolg `true` zurück.
    *   `getContent()`:
        *   Verarbeitet die Übermittlung des Back-Office-Konfigurationsformulars des Moduls.
        *   Aktualisiert `PS_ASG_UNASSIGN` und `PS_ASG_DEFAULT` in `ps_configuration` basierend auf Benutzereingaben.
        *   Rendert das Konfigurationsformular mit `display(__FILE__, 'views/templates/hook/form.tpl')`.
    *   `hookDisplayHeader()`:
        *   **Kernlogik**: Diese Methode wird bei jedem Laden einer Front-Office-Seite ausgeführt.
        *   Prüft, ob der `asg`-GET-Parameter vorhanden ist und eine gültige Ganzzahl darstellt, die eine `id_group` ist.
        *   Verifiziert, ob ein Kunde angemeldet ist (`$this->context->customer->isLogged()`).
        *   Ruft das Ziel-`Group`-Objekt ab.
        *   Ruft das aktuelle `Customer`-Objekt ab.
        *   Basierend auf der Konfiguration `PS_ASG_UNASSIGN` und `PS_ASG_DEFAULT`:
            *   Verwaltet die Gruppenzuordnungen des Kunden (`$customer->updateGroup()`).
            *   Fügt den Kunden der angegebenen Gruppe hinzu.
            *   Entfernt optional den Kunden aus anderen Gruppen.
            *   Fügt optional den Kunden der Standardgruppe hinzu.
        *   Leitet den Benutzer auf die aktuelle URL ohne den `asg`-Parameter um, um eine erneute Verarbeitung beim Aktualisieren zu verhindern.

## 5. Offizieller Support & Updates
Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul "Link zum Zuweisen eines Kunden zu einer Gruppe" besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.

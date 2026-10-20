---
title: "Maximaler Einkaufswert pro Hersteller – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Maximaler Einkaufswert pro Hersteller' von MyPresta.eu."
sidebar:
  label: "Maximaler Einkaufswert pro Hersteller – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Maximum purchase value by manufacturer auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-manufacturer.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/maximum-purchase-value-by-manufacturer/)
>
> ---


# Maximaler Einkaufswert pro Hersteller

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind in der Regel ausreichend. Es sind normalerweise keine speziellen Serverkonfigurationen erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie das Modul aktivieren oder deaktivieren und auf den speziellen Verwaltungsbereich zum Einrichten der Herstellerlimits zugreifen können.

- **Was diese Einstellung bewirkt:** Dieser Abschnitt enthält typischerweise einen einfachen Schalter zum Aktivieren oder Deaktivieren der Kernfunktionalität des Moduls. Er bietet auch einen direkten Link zum speziellen Bildschirm, auf dem Sie die tatsächlichen maximalen Einkaufswerte für Hersteller definieren.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul überprüft aktiv die Warenkörbe der Kunden anhand der definierten Herstellerlimits und verhindert Bestellungen, wenn Limits überschritten werden.
  - *Wenn deaktiviert:* Das Modul stellt seine Funktion ein, und es werden keine Hersteller-Einkaufslimits durchgesetzt.
- **Empfohlener Wert:** „JA“ (Aktiviert), wenn Sie die Funktionen des Moduls nutzen möchten.
- **Händlerszenario / Beispiel:** Sie haben das Modul gerade installiert und möchten Limits einrichten. Sie würden es hier aktivieren und dann zum Abschnitt „Herstellerlimits verwalten“ übergehen.

### 2.2 Dedizierter Admin-Bildschirm: Herstellerlimits (Back Office > Module > Maximaler Einkaufswert pro Hersteller > Konfigurieren > Schaltfläche „Herstellerlimits verwalten“ oder ein dedizierter Menüeintrag)

Auf diesem Bildschirm definieren und verwalten Sie die tatsächlichen maximalen Einkaufswerte für jeden Hersteller. Er wird typischerweise eine Liste Ihrer Hersteller präsentieren und Ihnen ermöglichen, Regeln hinzuzufügen, zu bearbeiten oder zu löschen.

**Bildschirmname & Menüpfad:**
Sie gelangen zu diesem Bildschirm, indem Sie im Modul-Manager auf die Schaltfläche „Konfigurieren“ neben dem Modul klicken und dann wahrscheinlich auf eine prominente Schaltfläche wie „Herstellerlimits verwalten“ oder „Neue Regel hinzufügen“. Alternativ könnte das Modul einen neuen Menüpunkt unter „Katalog“ oder „Shop-Parameter“ für den direkten Zugriff auf `AdminMaobm` erstellen.

**Verfügbare Aktionen & Einstellungen:**

1. **Auflistungstabelle der bestehenden Regeln:**

   - Sie sehen eine Tabelle, die alle von Ihnen bereits eingerichteten Herstellerlimits auflistet.
   - Die Spalten umfassen typischerweise: Herstellername, Maximalwert und Aktionen wie „Bearbeiten“ oder „Löschen“.
   - **Auswirkung von Änderungen:** Diese Tabelle bietet einen Überblick über Ihre aktiven Regeln. Das Löschen einer Regel entfernt das Einkaufslimit für diesen spezifischen Hersteller.
   - **Empfohlener Workflow:** Überprüfen Sie diese Tabelle regelmäßig, um sicherzustellen, dass Ihre Limits Ihren Geschäftsanforderungen entsprechen.
2. **Formular zum Hinzufügen/Bearbeiten von Regeln:**

   - Wenn Sie auf „Neu hinzufügen“ oder „Bearbeiten“ einer bestehenden Regel klicken, sehen Sie typischerweise ein Formular mit den folgenden Feldern:
     - **Hersteller:** Eine Dropdown-Liste oder ein Suchfeld zur Auswahl des Herstellers, für den Sie das Limit anwenden möchten.
       - **Was diese Einstellung bewirkt:** Gibt an, für welchen Hersteller diese Regel gilt.
       - **Auswirkung der Änderung dieser Einstellung:** Die Regel gilt nur für Produkte, die dem ausgewählten Hersteller zugeordnet sind.
       - **Empfohlener Wert:** Wählen Sie den spezifischen Hersteller aus, den Sie begrenzen möchten.
       - **Händlerszenario / Beispiel:** Sie möchten ein Limit für „Acme Corp.“-Produkte festlegen, also wählen Sie „Acme Corp.“ aus der Liste.
     - **Maximaler Einkaufswert:** Ein Eingabefeld, in das Sie den maximalen Gesamtwert (in der Standardwährung Ihres Shops) eingeben, den ein Kunde von dem ausgewählten Hersteller in einer einzigen Bestellung kaufen kann.
       - **Was diese Einstellung bewirkt:** Definiert die monetäre Obergrenze für Produkte des ausgewählten Herstellers.
       - **Auswirkung der Änderung dieser Einstellung:** Wenn der Gesamtwert der Produkte dieses Herstellers im Warenkorb eines Kunden diese Zahl überschreitet, wird er am Bestellen gehindert.
       - **Empfohlener Wert:** Ein numerischer Wert, der den maximal zulässigen Gesamtbetrag darstellt, z. B. „500.00“ für 500 Einheiten Ihrer Standardwährung.
       - **Händlerszenario / Beispiel:** Sie möchten „Acme Corp.“-Produkte auf maximal 500 $ pro Bestellung begrenzen. Sie würden hier „500“ eingeben.
     - **Speichern-Schaltfläche:** Um Ihre Änderungen zu übernehmen.
       - **Auswirkung von Änderungen:** Speichert die neue Regel oder aktualisiert eine bestehende in der Datenbank, wodurch sie sofort aktiv wird.

**Empfohlener Workflow für die tägliche Shop-Verwaltung:**

- **Ersteinrichtung:** Gehen Sie Ihre Herstellerliste durch und identifizieren Sie alle, für die Sie Einkaufslimits festlegen müssen. Fügen Sie für jeden eine neue Regel hinzu.
- **Überwachung:** Behalten Sie Ihre Verkäufe und Ihren Lagerbestand im Auge. Wenn Sie feststellen, dass Produkte eines Herstellers in übermäßigen Mengen gekauft werden oder sich Lieferantenvereinbarungen ändern, kehren Sie zu diesem Bildschirm zurück, um Limits anzupassen oder neue hinzuzufügen.
- **Updates:** Wenn neue Hersteller zu Ihrem Shop hinzugefügt werden, überlegen Sie, ob diese eine Einkaufslimit-Regel benötigen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modul-Konfigurationsseite | Modulstatus (Aktivieren/Deaktivieren) | Aktiviert | Aktiviert oder deaktiviert die Funktionalität des Moduls. |
| AdminMaobmController (Herstellerlimits) | Hersteller | Aus Liste auswählen | Gibt den Hersteller an, für den das Limit gilt. |
| AdminMaobmController (Herstellerlimits) | Maximaler Einkaufswert | Ihr gewünschtes monetäres Limit (z. B. 500.00) | Legt den maximalen Gesamtwert für Produkte des ausgewählten Herstellers in einer einzigen Bestellung fest. Eine Überschreitung blockiert den Checkout. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ein Kunde versucht, zur Kasse zu gehen, sieht aber eine Meldung, dass ein Herstellerlimit überschritten wurde. Was soll ich tun?**
A: Das bedeutet, dass das Modul wie vorgesehen funktioniert. Der Kunde hat zu viele Artikel eines bestimmten Herstellers in seinem Warenkorb, und der Gesamtwert dieser Artikel überschreitet das von Ihnen festgelegte Limit. Sie können entweder:
1. Dem Kunden raten, die Menge der Artikel dieses Herstellers zu reduzieren.
2. Das Limit für diesen Hersteller in der Modulkonfiguration vorübergehend deaktivieren oder anpassen, wenn Sie die Bestellung für akzeptabel halten (seien Sie jedoch vorsichtig dabei).

**F: Ich habe ein Limit festgelegt, aber es scheint nicht zu funktionieren. Kunden können immer noch mehr als das Maximum bestellen.**
A:
1. **Modulstatus überprüfen:** Stellen Sie sicher, dass das Modul unter **Module > Modul-Manager** und auf seiner Hauptkonfigurationsseite aktiviert ist.
2. **Regel überprüfen:** Überprüfen Sie die von Ihnen erstellte Regel unter dem Bildschirm „Herstellerlimits verwalten“. Ist der richtige Hersteller ausgewählt? Ist der „Maximale Einkaufswert“ korrekt eingestellt?
3. **Cache leeren:** Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort wirksam werden. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“.
4. **Produkthersteller:** Stellen Sie sicher, dass die betreffenden Produkte dem Hersteller korrekt zugeordnet sind, für den Sie das Limit festgelegt haben. Überprüfen Sie die Produkteinstellungen in Ihrem Katalog.

**F: Kann ich unterschiedliche Limits für verschiedene Kundengruppen festlegen?**
A: Dieses Modul wendet in seiner Standardform ein einziges Limit pro Hersteller für alle Kunden an. Wenn Sie kundengruppenspezifische Limits benötigen, wäre dies eine kundenspezifische Entwicklung.

**F: Die Warnmeldung ist nicht klar oder passt nicht zur Sprache/zum Theme meines Shops.**
A:
1. **Übersetzungen:** Gehen Sie zu **International > Übersetzungen**, wählen Sie „Übersetzungen installierter Module“, Ihr Theme und das Modul „Maximaler Einkaufswert pro Hersteller“. Dort können Sie den Text der Warnmeldung anpassen.
2. **Theme-Styling:** Das Modul verwendet Standard-PrestaShop-Styling für seine Nachrichten. Wenn es fehl am Platz aussieht, hat Ihr Theme möglicherweise benutzerdefiniertes CSS, das angepasst werden muss. Ein Webmaster kann die Datei `maobm.css` und das CSS Ihres Themes überprüfen, um es visuell konsistent zu machen.

**F: Was passiert, wenn einem Produkt kein Hersteller zugewiesen ist?**
A: Produkte ohne zugewiesenen Hersteller unterliegen keinen Limits, die von diesem Modul festgelegt wurden, da die Regeln herstellerspezifisch sind.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Maximaler Einkaufswert pro Hersteller“ (`maobm`) folgt einer Standard-PrestaShop-Modularchitektur. Es verwendet hauptsächlich eine `Module`-Klasse für die Installation und grundlegende Konfiguration, einen `AdminController` zur Verwaltung der Herstellerlimits und `FrontController`s zur Bearbeitung von AJAX-Anfragen und zur Integration in den Front-Office-Warenkorbprozess. Das Modul nutzt das Hook-System von PrestaShop, um seine Logik in den Warenkorb- und Checkout-Fluss einzuschleusen und Bestellungen zu verhindern, wenn Limits überschritten werden. Es speichert seine Konfiguration in `ps_configuration` und verwaltet spezifische Herstellerlimits über eine dedizierte Datenbanktabelle (obwohl kein `ObjectModel` explizit aufgeführt ist, impliziert dies eine direkte DB-Interaktion oder einen einfachen `AdminController`, der die Konfiguration verwaltet).

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/ajax.php`
    - **Klassenname**: `MaobmAjaxModuleFrontController` (impliziert, erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dieser Controller verarbeitet wahrscheinlich AJAX-Anfragen vom Front-Office, z. B. wenn ein Kunde seinen Warenkorb aktualisiert. Er würde die Herstellerlimits neu bewerten und eine Antwort zurückgeben (z. B. eine Warnmeldung oder einen Status, der angibt, ob die Bestellung fortgesetzt werden kann). Er könnte in `actionCartSave` oder ähnliche Ereignisse eingehängt werden, um Echtzeit-Feedback zu geben.
  - `controllers/front/index.php`
    - **Klassenname**: `MaobmIndexModuleFrontController` (impliziert, erweitert `ModuleFrontController`)
    - **Verantwortlichkeit**: Dieser Controller könnte als Fallback oder einfacher Einstiegspunkt dienen, obwohl seine primäre Funktion minimal sein könnte, wenn `ajax.php` die meisten Front-End-Interaktionen übernimmt. Er könnte potenziell eine generische Nachricht anzeigen oder umleiten, wenn direkt darauf zugegriffen wird.
- **Back-Office-Admin-Controller**:

  - `controllers/admin/AdminMaobm.php`
    - **Klassenname**: `AdminMaobmController` (erweitert `ModuleAdminController`)
    - **Tab-Name**: Wahrscheinlich ein vom Modul erstellter benutzerdefinierter Tab oder über die Konfigurationsseite des Moduls zugänglich.
    - **Verwaltete Entität**: Verwaltet die spezifischen Herstellerlimit-Regeln. Es bietet die Schnittstelle zum Auflisten, Hinzufügen, Bearbeiten und Löschen dieser Regeln. Dieser Controller würde direkt mit der Datenbank interagieren, um die Hersteller-IDs und ihre zugehörigen Maximalwerte zu speichern und abzurufen. Er würde typischerweise `HelperList` für die Übersichts-Tabelle und `HelperForm` für das Hinzufügen/Bearbeiten-Formular verwenden.
  - `controllers/admin/index.php`
    - **Klassenname**: `AdminMaobmIndexController` (impliziert, erweitert `ModuleAdminController`)
    - **Verantwortlichkeit**: Ähnlich wie das Front-Office `index.php` könnte dies ein Platzhalter oder eine einfache Weiterleitung sein. In PrestaShop dienen `index.php`-Dateien in Controller-Verzeichnissen oft als Sicherheitsmaßnahmen, um direkte Verzeichnisauflistungen zu verhindern.

### 4.3 Kernklassen & Modelle (`classes/`)

Das bereitgestellte Inventar zeigt keine benutzerdefinierten Klassen im Verzeichnis `classes/`. Dies deutet darauf hin, dass das Modul entweder:

1. Datenbanktabellen (z. B. `ps_maobm_limits`) direkt über `Db::getInstance()` in seinen Controllern oder der Hauptmoduldatei manipuliert.
2. Alle Konfigurationen in `ps_configuration` mithilfe von `Configuration::updateValue()` speichert, wobei der `AdminMaobmController` diese Konfigurationseinträge verwaltet.
   Angesichts der Funktion „unbegrenzte Anzahl von Regeln“ ist eine direkte DB-Interaktion für eine benutzerdefinierte Tabelle wahrscheinlicher als `ps_configuration` zum Speichern mehrerer Herstellerlimits.

### 4.4 JavaScript-Assets (`views/js/`)

- `views/js/maobm.js`
  - **Geltungsbereich**: Wahrscheinlich Front-Office.
  - **Details**: Dieses Skript wäre für clientseitige Interaktionen im Zusammenhang mit der Funktionalität des Moduls verantwortlich. Es könnte:
    - Event-Listener an Warenkorb-Aktualisierungsaktionen binden (z. B. Mengenänderungen, Produktentfernung).
    - AJAX-Aufrufe an `controllers/front/ajax.php` tätigen, um Herstellerlimits in Echtzeit ohne vollständiges Neuladen der Seite neu zu bewerten.
    - Warnmeldungen anzeigen oder die Checkout-Schaltfläche deaktivieren, wenn Limits überschritten werden, basierend auf der AJAX-Antwort.
    - Potenziell mit den `prestashop.on`-Ereignissen von PrestaShop für eine bessere Kompatibilität integrieren.

### 4.5 CSS-Stylesheets (`views/css/`)

- `views/css/maobm.css`
  - **Geltungsbereich**: Primär Front-Office, möglicherweise einige Back-Office-Styling für benutzerdefinierte Elemente.
  - **Details**: Dieses Stylesheet würde die notwendigen CSS-Regeln enthalten, um die Warnmeldungen zu gestalten, die dem Kunden im Warenkorb oder Checkout-Prozess angezeigt werden. Es könnte Klassen definieren für:
    - `#maobm-warning-message` oder ähnliche Container für den Fehlertext.
    - Styling für deaktivierte Checkout-Schaltflächen.
    - Sicherstellung der Responsivität über verschiedene Bildschirmgrößen hinweg.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können**: Suchen Sie nach Klassen wie `.maobm-alert`, `.maobm-error-message` oder spezifischen IDs, die für den Warncontainer verwendet werden.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `views/templates/front/displayShoppingCart.tpl`
    - **Hook**: Dieses Template wird wahrscheinlich in einem Hook gerendert, der auf der Warenkorbseite erscheint, wie `displayShoppingCartFooter` oder `displayShoppingCart`.
    - **Ausgabe**: Es wäre dafür verantwortlich, dem Kunden die Warnmeldung anzuzeigen (`displayShoppingCart.tpl`), wenn Hersteller-Einkaufslimits überschritten werden. Es würde Variablen vom Modul erhalten, die angeben, ob ein Limit überschritten wurde und die entsprechende Nachricht, die angezeigt werden soll.
- **Admin-Templates (`views/templates/admin/`)**: (Nicht explizit aufgeführt, aber durch `AdminMaobmController` impliziert)

  - Der `AdminMaobmController` würde typischerweise die `HelperList`- und `HelperForm`-Templates von PrestaShop für seine Benutzeroberfläche verwenden, könnte aber benutzerdefinierte `.tpl`-Dateien für bestimmte Teile seiner Konfiguration oder zur Anzeige einer Liste von Regeln haben. Diese würden normalerweise in `views/templates/admin/maobm/` oder ähnlichem gefunden werden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - `ps_maobm_limits` (Impliziert): Eine benutzerdefinierte Tabelle zum Speichern der Herstellerlimits.
    - `id_maobm_limit` (Primärschlüssel, AUTO_INCREMENT)
    - `id_manufacturer` (Fremdschlüssel zu `ps_manufacturer.id_manufacturer`)
    - `max_value` (Dezimal oder Float, speichert den maximal zulässigen Einkaufswert)
    - `date_add`, `date_upd` (Standard-PrestaShop-Zeitstempel)
  - `ps_configuration`: Das Modul könnte allgemeine Einstellungen (wie den Modul-Aktivierungs-/Deaktivierungsstatus) hier speichern.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich aller Front-Office-Seiten gerendert. | Zum Einbinden von `maobm.css` und `maobm.js` Assets. |
| `displayShoppingCart` oder `displayShoppingCartFooter` | Rendert Inhalte auf der Warenkorbseite. | Zum Anzeigen der Warnmeldung (`displayShoppingCart.tpl`), wenn Limits überschritten werden. |
| `actionCartSave` | Wird ausgeführt, nachdem ein Warenkorb gespeichert oder aktualisiert wurde. | Zum Neubewerten der Herstellerlimits und potenziellen Aktualisieren des Warenkorbstatus oder Anzeigen von Nachrichten. |
| `actionValidateOrder` | Wird ausgeführt, bevor eine Bestellung offiziell validiert wird. | **KRITISCH**: Um eine letzte Überprüfung der Herstellerlimits durchzuführen und die Bestellvalidierung zu verhindern, wenn Limits überschritten werden. Hier würde die Logik zur Bestellblockierung liegen. |
| `displayAdminProductsExtra` (oder ähnlich) | Könnte verwendet werden, um Herstellerlimit-Informationen direkt auf der Produktbearbeitungsseite im BO anzuzeigen. | (Optional) Um schnellen Zugriff auf Limit-Informationen für den Hersteller des Produkts zu ermöglichen. |
| `displayBackOfficeHeader` | Wird im `<head>`-Bereich aller Back-Office-Seiten gerendert. | Zum Einbinden von Back-Office-spezifischem CSS/JS für `AdminMaobmController`. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Maximaler Einkaufswert pro Hersteller“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Konfiguration des Moduls zur Verfügung.

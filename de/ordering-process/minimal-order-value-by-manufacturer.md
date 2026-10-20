---
title: "Mindestbestellwert nach Hersteller – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Mindestbestellwert nach Hersteller“ von MyPresta.eu."
sidebar:
  label: "Mindestbestellwert nach Hersteller – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Minimal order value by manufacturer auf MyPresta.eu kaufen](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-manufacturer.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ordering-process/minimal-order-value-by-manufacturer/)
>
> ---


# Mindestbestellwert nach Hersteller

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL).

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul, der direkt nach der Installation oder durch Klicken auf „Konfigurieren“ neben dem Modul im Modul-Manager zugänglich ist.

- **Was dieser Bildschirm leistet:** Diese Seite ermöglicht es Ihnen, das Modul zu aktivieren/deaktivieren und die Kerneinstellungen zu verwalten, die sein Verhalten steuern.

#### Einstellungen & Optionen

- **Modul aktivieren / deaktivieren:**

  - **Was diese Einstellung leistet:** Dies ist ein globaler Schalter, um die gesamte Funktionalität des Moduls ein- oder auszuschalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Das Modul prüft aktiv die Mindestbestellwerte nach Hersteller in den Warenkörben der Kunden und wendet Einschränkungen an, wenn die Bedingungen nicht erfüllt sind.
    - *Wenn deaktiviert:* Das Modul funktioniert nicht mehr. Es werden keine Mindestbestellwertprüfungen durchgeführt, und Kunden können beliebige Mengen von jedem Hersteller bestellen.
  - **Empfohlener Wert:** **JA** (um die Kernfunktion des Moduls zu aktivieren).
  - **Händlerszenario / Beispiel:** Wenn Sie das Modul testen oder vorübergehend alle Mindestbestellregeln deaktivieren möchten, ohne sie zu löschen, können Sie dies ausschalten.
- **Nachricht auf der Warenkorbseite anzeigen:**

  - **Was diese Einstellung leistet:** Steuert, ob eine Warnmeldung dem Kunden auf der Warenkorbseite angezeigt wird, wenn der Mindestbestellwert eines Herstellers nicht erreicht ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden sehen eine klare, informative Meldung auf ihrer Warenkorbseite, die anzeigt, welcher Hersteller-Mindestwert nicht erreicht ist und wie viel sie noch hinzufügen müssen.
    - *Wenn deaktiviert:* Es erscheint keine Meldung auf der Warenkorbseite. Die Einschränkung gilt weiterhin, aber der Kunde könnte sie erst später während des Checkouts entdecken, was möglicherweise zu Frustration führt.
  - **Empfohlener Wert:** **JA**.
  - **Händlerszenario / Beispiel:** Die Aktivierung dieser Option bietet ein besseres Benutzererlebnis, indem Kunden frühzeitig zur Behebung des Problems angeleitet werden, anstatt sie beim Checkout zu überraschen.
- **Nachricht auf der Checkout-Seite anzeigen:**

  - **Was diese Einstellung leistet:** Steuert, ob eine Warnmeldung dem Kunden auf der Checkout-Seite angezeigt wird, wenn der Mindestbestellwert eines Herstellers nicht erreicht ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Kunden sehen eine Meldung auf der Checkout-Seite, die sie daran hindert, die Bestellung abzuschließen, bis der Mindestwert erreicht ist.
    - *Wenn deaktiviert:* Der Checkout-Prozess könnte einfach ohne klare Erklärung stoppen, oder das Modul könnte den Fortschritt ohne eine spezifische Meldung verhindern, was Kunden verwirren kann.
  - **Empfohlener Wert:** **JA**.
  - **Händlerszenario / Beispiel:** Dies ist entscheidend, um Bestellungen zu verhindern, die Ihre Kriterien nicht erfüllen, und um dem Kunden den Grund klar mitzuteilen.
- **Anzuzeigende Nachricht (für Warenkorb- und Checkout-Seiten):**

  - **Was diese Einstellung leistet:** Ermöglicht Ihnen, den Text der Warnmeldung anzupassen, die Kunden angezeigt wird, wenn ein Mindestbestellwert nicht erreicht ist. Sie können Platzhalter wie `{manufacturer_name}` und `{missing_amount}` verwenden.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn geändert:* Die benutzerdefinierte Nachricht wird im Front Office angezeigt.
    - *Wenn Standard belassen:* Eine Standardnachricht wird verwendet.
  - **Empfohlener Wert:** Anpassen, um klar und hilfreich zu sein. Beispiel: „Um Ihre Bestellung abzuschließen, müssen Sie Produkte von {manufacturer\_name} im Wert von {missing\_amount} hinzufügen.“
  - **Händlerszenario / Beispiel:** Sie möchten die Nachricht möglicherweise freundlicher gestalten, einen Call-to-Action einfügen oder sie an den Ton Ihrer Marke anpassen.

### 2.2 Dedizierte Admin-Bildschirme: Mindestbestellwert nach Hersteller-Regeln (Back Office > Katalog > Mindestbestellwert nach Hersteller)

Auf diesem Bildschirm definieren und verwalten Sie die tatsächlichen Mindestbestellwertregeln für jeden Hersteller.

- **Bildschirmname & Menüpfad:** „Mindestbestellwert nach Hersteller“ unter dem Menü **Katalog**.
- **Was dieser Bildschirm leistet:** Dies ist ein dedizierter Verwaltungsbereich zum Hinzufügen, Bearbeiten und Löschen von Regeln für Mindestbestellwerte pro Hersteller. Er zeigt eine Liste aller aktuell konfigurierten Regeln an.

#### Verfügbare Aktionen & Einstellungen

- **Liste der Regeln:**

  - **Was dies leistet:** Zeigt eine Tabelle aller bestehenden Mindestbestellwertregeln an. Jede Zeile zeigt typischerweise den Namen des Herstellers, den festgelegten Mindestwert und Optionen zum Bearbeiten oder Löschen der Regel.
  - **Auswirkung von Änderungen:** Diese Tabelle bietet einen Überblick über alle aktiven Regeln.
  - **Empfohlener Workflow:** Überprüfen Sie diese Liste regelmäßig, um sicherzustellen, dass Ihre Regeln mit Ihren Geschäftsanforderungen übereinstimmen.
- **Schaltfläche „Neue Regel hinzufügen“:**

  - **Was dies leistet:** Durch Klicken auf diese Schaltfläche gelangen Sie zu einem Formular, in dem Sie eine neue Mindestbestellwertregel erstellen können.
  - **Auswirkung von Änderungen:** Öffnet ein neues Formular.
  - **Empfohlener Workflow:** Verwenden Sie dies, wenn Sie einen neuen Mindestwert für einen Hersteller festlegen müssen, der noch nicht in der Liste ist.
- **Schaltfläche „Bearbeiten“ (für jede Regel):**

  - **Was dies leistet:** Ermöglicht Ihnen, die Einstellungen einer bestehenden Regel zu ändern.
  - **Auswirkung von Änderungen:** Öffnet das Formular der Regel mit vorausgefüllten Daten, sodass Sie den Hersteller oder den Mindestwert ändern können.
  - **Empfohlener Workflow:** Verwenden Sie dies, um Mindestwerte basierend auf neuen Lieferantenvereinbarungen oder Verkaufsstrategien anzupassen.
- **Schaltfläche „Löschen“ (für jede Regel):**

  - **Was dies leistet:** Entfernt eine spezifische Mindestbestellwertregel.
  - **Auswirkung von Änderungen:** Die Regel wird sofort entfernt, und der zugehörige Hersteller hat keine Mindestbestellwertanforderung mehr.
  - **Empfohlener Workflow:** Verwenden Sie dies, wenn ein Hersteller keinen Mindestbestellwert mehr benötigt oder wenn Sie eine Marke einstellen.

#### Formular zum Hinzufügen/Bearbeiten von Regeln

Beim Hinzufügen einer neuen Regel oder Bearbeiten einer bestehenden Regel sehen Sie typischerweise die folgenden Felder:

- **Hersteller:**

  - **Was diese Einstellung leistet:** Dieses Feld ermöglicht es Ihnen, den spezifischen Hersteller auszuwählen, für den diese Mindestbestellwertregel gelten soll. Es verfügt normalerweise über eine Autovervollständigungsfunktion, um Ihnen die einfache Suche nach Herstellern zu erleichtern.
  - **Auswirkung der Änderung dieser Einstellung:** Verknüpft die Regel mit einem bestimmten Hersteller.
  - **Empfohlener Wert:** Wählen Sie den genauen Hersteller aus, für den Sie die Regel anwenden möchten.
  - **Händlerszenario / Beispiel:** Sie könnten „Apple“ auswählen, um einen Mindestwert für alle Apple-Produkte festzulegen, oder „Samsung“ für Samsung-Produkte.
- **Mindestbestellwert:**

  - **Was diese Einstellung leistet:** Hier geben Sie den numerischen Wert (in der Standardwährung Ihres Shops, z. B. USD, EUR) ein, der den erforderlichen Mindestgesamtbetrag für Produkte des ausgewählten Herstellers darstellt.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn ein Wert festgelegt wird (z. B. 50,00):* Kunden müssen Produkte des ausgewählten Herstellers im Wert von mindestens 50,00 in ihrem Warenkorb haben, um fortzufahren.
    - *Wenn auf 0 gesetzt oder leer gelassen:* Dies deaktiviert den Mindestwert für diesen Hersteller effektiv (obwohl es besser ist, die Regel zu löschen, wenn kein Mindestwert benötigt wird).
  - **Empfohlener Wert:** Ein positiver numerischer Wert, der Ihre Geschäftsanforderungen widerspiegelt.
  - **Händlerszenario / Beispiel:** Wenn Ihr Lieferant für „MarkeX“ verlangt, dass Sie Produkte im Wert von mindestens 100 $ bestellen, würden Sie dies für „MarkeX“ auf „100,00“ setzen.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren / deaktivieren | JA | Globaler Schalter für die Modulfunktionalität. |
| Modulkonfiguration | Nachricht auf der Warenkorbseite anzeigen | JA | Zeigt Warnung im Warenkorb an, wenn Minimum nicht erreicht. |
| Modulkonfiguration | Nachricht auf der Checkout-Seite anzeigen | JA | Zeigt Warnung beim Checkout an, wenn Minimum nicht erreicht. |
| Modulkonfiguration | Anzuzeigende Nachricht | Anpassbar | Passt den Text der Warnmeldung an. |
| AdminMobmController | Hersteller (Regel hinzufügen/bearbeiten) | Aus Liste auswählen | Verknüpft Regel mit einem spezifischen Hersteller. |
| AdminMobmController | Mindestbestellwert (Regel hinzufügen/bearbeiten) | Numerischer Wert | Legt den Mindestgesamtwert für die Produkte des ausgewählten Herstellers fest. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Ich habe einen Mindestwert festgelegt, aber er funktioniert im Front Office nicht. Was sollte ich überprüfen?**
A1:

- **Ist das Modul aktiviert?** Gehen Sie zu `Module > Modul-Manager` und stellen Sie sicher, dass „Mindestbestellwert nach Hersteller“ aktiv ist.
- **Ist die spezifische Regel aktiviert?** Überprüfen Sie unter `Katalog > Mindestbestellwert nach Hersteller`, ob die Regel für den betreffenden Hersteller korrekt mit einem positiven Wert konfiguriert ist.
- **Cache leeren:** Gehen Sie zu `Erweiterte Einstellungen > Performance` und klicken Sie auf „Cache leeren“ (für alle Caches). Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort angezeigt werden.
- **Auf Konflikte prüfen:** Deaktivieren Sie vorübergehend andere Module, die den Warenkorb oder den Checkout-Prozess ändern, um zu sehen, ob ein Konflikt vorliegt.

**F2: Die Nachricht auf der Warenkorb-/Checkout-Seite wird nicht angezeigt.**
A2:

- **Modulkonfiguration prüfen:** Gehen Sie zu `Module > Modul-Manager > Konfigurieren` für „Mindestbestellwert nach Hersteller“. Stellen Sie sicher, dass „Nachricht auf der Warenkorbseite anzeigen“ und „Nachricht auf der Checkout-Seite anzeigen“ beide auf **JA** gesetzt sind.
- **Ist der Mindestwert tatsächlich nicht erreicht?** Überprüfen Sie nochmals, ob die Produkte im Warenkorb des spezifischen Herstellers tatsächlich unter dem festgelegten Minimum liegen.

**F3: Kann ich unterschiedliche Mindestwerte für verschiedene Kundengruppen festlegen?**
A3: Dieses Modul wendet in seiner Standardform einen einzigen Mindestwert pro Hersteller auf alle Kunden an. Wenn Sie kundengruppenspezifische Mindestwerte benötigen, würde dies eine kundenspezifische Entwicklung oder ein anderes Modul erfordern.

**F4: Wie geht das Modul mit Shops mit mehreren Währungen um?**
A4: Das Modul verwendet die Standardwährung Ihres Shops (wie unter `Lokalisierung > Währungen` und `Lokalisierung > Lokalisierung` definiert) für den von Ihnen festgelegten „Mindestbestellwert“. Es konvertiert den Warenkorb-Gesamtbetrag des Kunden automatisch in die Standardwährung zum Vergleich, um Konsistenz zu gewährleisten.

**F5: Das Modul scheint meine Website zu verlangsamen. Was kann ich tun?**
A5:

- **Cache leeren:** Stellen Sie sicher, dass alle Caches regelmäßig geleert werden (`Erweiterte Einstellungen > Performance`).
- **Serverressourcen:** Überprüfen Sie die Ressourcen Ihrer Hosting-Umgebung (CPU, RAM). Wenn Ihr Shop eine sehr große Anzahl von Herstellern oder Produkten hat, stellen Sie sicher, dass Ihr Server die Last bewältigen kann.
- **Modul-Updates:** Verwenden Sie immer die neueste Version des Moduls von MyPresta.eu, da Updates oft Leistungsverbesserungen enthalten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen tiefen Einblick in die technische Struktur des Moduls „Mindestbestellwert nach Hersteller“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul folgt einem Standard-PrestaShop-MVC-Muster (Model-View-Controller). Es erweitert hauptsächlich `Module` für seine Kernfunktionalität und Konfiguration, verwendet `AdminController` für die Back-Office-Verwaltung von Regeln und `ModuleFrontController` für Front-Office-AJAX-Interaktionen im Zusammenhang mit der Warenkorbvalidierung. Es scheint keine benutzerdefinierten `ObjectModel`-Klassen zu verwenden, sondern verlässt sich auf `Configuration` für allgemeine Einstellungen und direkte Datenbankinteraktion (oder möglicherweise eine einfache Array-Struktur) für herstellerspezifische Regeln. Hooks werden ausgiebig verwendet, um sich in den Warenkorb- und Checkout-Fluss zu integrieren.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `controllers/front/ajax.php`
  - **Klassenname:** `MobmAjaxModuleFrontController` (wahrscheinlich, basierend auf der Dateibenennungskonvention), erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist wahrscheinlich für die Verarbeitung von AJAX-Anfragen aus dem Front Office verantwortlich, insbesondere solcher, die sich auf Warenkorbaktualisierungen oder den Checkout-Fortschritt beziehen. Er würde Warenkorbdaten empfangen, die Mindestbestellwertprüfungen durchführen und eine JSON-Antwort zurückgeben, die angibt, ob die Bedingungen erfüllt sind und welche Nachrichten angezeigt werden sollen. Dies ist entscheidend für dynamische Aktualisierungen ohne vollständige Seitenneuladungen.
- `controllers/front/index.php`
  - **Klassenname:** `MobmIndexModuleFrontController` (wahrscheinlich), erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Diese Datei könnte ein Platzhalter sein oder für eine einfache Front-Office-Seite verwendet werden, falls das Modul eine hätte. Angesichts des Zwecks des Moduls ist es weniger wahrscheinlich, dass es eine vollständige Seite rendert, und eher wahrscheinlich, dass es ein Fallback oder Teil einer Weiterleitungskette ist, wenn `ajax.php` der primäre Interaktionspunkt ist.

#### Back-Office-Admin-Controller

- `controllers/admin/AdminMobm.php`
  - **Klassenname:** `AdminMobmController`, erweitert `ModuleAdminController`.
  - **Tab-Name:** „Mindestbestellwert nach Hersteller“ (unter Katalog).
  - **Verwaltete Entität:** Verwaltet die Entität `mobm`, die die einzelnen Mindestbestellwertregeln für Hersteller darstellt.
  - **Verantwortlichkeit:** Dies ist der primäre Controller für die Verwaltung der Liste der Hersteller-Mindestbestellregeln. Er behandelt:
    - Anzeige der Liste der bestehenden Regeln (mit `renderList()`).
    - Hinzufügen neuer Regeln (mit `renderForm()` für das Hinzufügen-Formular).
    - Bearbeiten bestehender Regeln (mit `renderForm()` für das Bearbeiten-Formular).
    - Löschen von Regeln.
    - Formularvalidierung und Speichern von Daten.
    - Er interagiert wahrscheinlich mit der Tabelle `ps_configuration` oder einer benutzerdefinierten Tabelle, um die Hersteller-ID und ihren zugehörigen Mindestwert zu speichern.
- `controllers/admin/index.php`
  - **Klassenname:** `AdminMobmIndexModuleAdminController` (wahrscheinlich), erweitert `ModuleAdminController`.
  - **Verantwortlichkeit:** Ähnlich wie die Front-Office-`index.php` könnte dies ein Platzhalter oder ein Standardeinstiegspunkt sein. In PrestaShop dienen `index.php`-Dateien in Controller-Verzeichnissen oft als grundlegende Sicherheitsmaßnahmen (z. B. `die('Access Denied');`) oder einfache Weiterleitungen, wenn sie nicht explizit von einem spezifischeren Controller behandelt werden.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` auf. Dies deutet darauf hin, dass das Modul entweder:

1. Seine Herstellerregeln direkt in der Tabelle `ps_configuration` speichert (z. B. als serialisiertes Array).
2. Direkte Datenbankabfragen innerhalb der Hauptmoduldatei oder des Admin-Controllers verwendet, um eine benutzerdefinierte Tabelle zu verwalten.
3. Daten als einfaches Array im Kontext des Moduls ohne formale `ObjectModel` verwaltet.

Angesichts der Tatsache, dass der `AdminMobmController` eine `mobm`-Entität verwaltet, ist es sehr wahrscheinlich, dass während der Installation eine benutzerdefinierte Tabelle (z. B. `ps_mobm`) erstellt wird und der `AdminMobmController` implizit CRUD-Operationen für diese Tabelle ohne eine dedizierte `ObjectModel`-Klasse in `classes/` handhabt. Die `$definition` für diese Entität würde dann direkt im `AdminMobmController` oder in der Hauptmoduldatei definiert.

### 4.4 JavaScript-Assets (`views/js/`)

- `mobm/lib/searchTool/views/js/autocomplete.js`
  - **Geltungsbereich:** Back Office (wahrscheinlich für das `AdminMobmController`-Formular).
  - **Verantwortlichkeit:** Bietet Autovervollständigungsfunktionen für die Auswahl von Herstellern im Formular „Regel hinzufügen/bearbeiten“. Es überwacht Benutzereingaben in einem Textfeld, sendet AJAX-Anfragen an einen Back-Office-Controller (z. B. `AdminManufacturers` oder eine benutzerdefinierte `AdminMobm`-Methode), um passende Herstellernamen abzurufen, und zeigt Vorschläge an.
- `mobm/views/js/mobm.js`
  - **Geltungsbereich:** Front Office.
  - **Verantwortlichkeit:** Dies ist das Haupt-Front-Office-JavaScript für das Modul. Es wird wahrscheinlich:
    - Ereignisse auf der Warenkorbseite binden (z. B. Mengenänderungen, Produktentfernungen).
    - Ereignisse auf der Checkout-Seite binden (z. B. Klicks auf die Schaltfläche „Zur Kasse gehen“).
    - AJAX-Anfragen an `controllers/front/ajax.php` senden, um den Warenkorb anhand der Hersteller-Mindestwerte zu validieren.
    - JSON-Antworten empfangen und die Benutzeroberfläche dynamisch mit Warnmeldungen aktualisieren oder den Fortschritt verhindern, wenn Mindestwerte nicht erreicht werden.
    - Möglicherweise Modal-Popups oder visuelle Hinweise für den Kunden handhaben.

### 4.5 CSS-Stylesheets (`views/css/`)

- `mobm/lib/searchTool/views/css/autocomplete.css`
  - **Geltungsbereich:** Back Office.
  - **Verantwortlichkeit:** Gestaltet das Autovervollständigungs-Dropdown und das Eingabefeld, das für die Herstellerauswahl im Admin-Formular verwendet wird.
  - **Wichtige CSS-Klassenselektoren:** Zielt wahrscheinlich auf Klassen wie `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected` usw. ab.
- `mobm/views/css/mobm.css`
  - **Geltungsbereich:** Front Office.
  - **Verantwortlichkeit:** Gestaltet die Warnmeldungen, die auf den Warenkorb- und Checkout-Seiten angezeigt werden. Stellt sicher, dass diese Meldungen visuell unterschiedlich sind und sich gut in das Thema integrieren.
  - **Wichtige CSS-Klassenselektoren:** Zielt wahrscheinlich auf benutzerdefinierte Klassen ab, die vom Modul zu den Warnmeldungscontainern hinzugefügt wurden, z. B. `.mobm-warning-message`, `.mobm-error-block`.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- `mobm/lib/searchTool/views/scripts.tpl`
  - **Geltungsbereich:** Back Office.
  - **Verantwortlichkeit:** Dieses Template enthält wahrscheinlich das notwendige JavaScript für die Autovervollständigungsfunktion (aus `autocomplete.js`) und möglicherweise einige Inline-Skripte oder Konfigurationen dafür. Es würde innerhalb der `renderForm()`-Methode des `AdminMobmController` gerendert werden.
- `mobm/views/templates/front/displayShoppingCart.tpl`
  - **Geltungsbereich:** Front Office.
  - **Hook:** Dieses Template ist so konzipiert, dass es in einem Hook gerendert wird, der Inhalte auf der Warenkorbseite anzeigt, wie z. B. `displayShoppingCartFooter` oder `displayBeforeShoppingCartBlock`.
  - **Verantwortlichkeit:** Zeigt dem Kunden die Warnmeldung an, wenn der Mindestbestellwert eines Herstellers nicht erreicht ist. Es enthält die Logik, die Nachricht nur anzuzeigen, wenn `{$mobm_warning_message}` (oder eine ähnliche Variable, die vom Modul übergeben wird) nicht leer ist.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

- **`ps_configuration`**: Speichert allgemeine Moduleinstellungen (z. B. `PS_MOVB_ENABLED`, `PS_MOVB_CART_MSG_ENABLED`, `PS_MOVB_CHECKOUT_MSG_ENABLED`, `PS_MOVB_CUSTOM_MESSAGE`).
- **`ps_mobm` (Wahrscheinlich benutzerdefinierte Tabelle)**: Diese Tabelle ist aufgrund des `AdminMobmController`, der eine `mobm`-Entität verwaltet, sehr wahrscheinlich.
  - **Spalten (Hypothetisch):**
    - `id_mobm` (Primärschlüssel, INT)
    - `id_manufacturer` (INT, Fremdschlüssel zu `ps_manufacturer`)
    - `min_value` (DECIMAL(20,6), speichert den Mindestbestellwert)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich aller Front-Office-Seiten. | Zum Einbinden von Front-Office-CSS (`mobm.css`) und JavaScript (`mobm.js`) Assets. |
| `actionCartSave` | Nach dem Speichern eines Warenkorbs (z. B. Mengenänderung, Produkt hinzugefügt/entfernt). | Zur Durchführung einer Echtzeitvalidierung der Hersteller-Mindestwerte und potenziellen Speicherung des Validierungsstatus. |
| `actionValidateOrder` | Bevor eine Bestellung offiziell validiert wird. | Um die Bestellvalidierung zu verhindern, wenn die Mindestwerte eines Herstellers nicht erreicht sind. |
| `displayShoppingCartFooter` (oder ähnlich) | Am unteren Ende der Warenkorbseite. | Zum Anzeigen der Warnmeldung (`displayShoppingCart.tpl`), wenn die Mindestwerte nicht erreicht sind. |
| `displayPaymentTop` (oder ähnlicher Checkout-Hook) | Am oberen Ende des Zahlungsauswahlschritts im Checkout. | Zum Anzeigen der Warnmeldung und zur Verhinderung des Fortschreitens, wenn die Mindestwerte nicht erreicht sind. |
| `displayAdminProductsExtra` (oder ähnlich) | Auf der Produktbearbeitungsseite im Back Office. | Potenziell zur Anzeige von Informationen über den Mindestwert des Herstellers direkt auf Produktseiten (weniger wahrscheinlich, aber möglich). |
| `displayBackOfficeHeader` | Im `<head>`-Bereich aller Back-Office-Seiten. | Zum Einbinden von Back-Office-CSS (`autocomplete.css`) und JavaScript (`autocomplete.js`) für das `AdminMobmController`-Formular. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und um sicherzustellen, dass Sie die neueste, kompatibelste Version des Moduls „Mindestbestellwert nach Hersteller“ verwenden, besuchen Sie bitte Ihr Kundenkonto auf [MyPresta.eu](https://mypresta.eu). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen gerne zur Verfügung.

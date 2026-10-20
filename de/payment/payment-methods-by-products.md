---
title: "Zahlungsmethoden nach Produkten - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul 'Zahlungsmethoden nach Produkten' von MyPresta.eu."
sidebar:
  label: "Zahlungsmethoden nach Produkten - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Payment methods by products auf MyPresta.eu kaufen](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/payment/payment-methods-by-products/)
>
> ---


# Zahlungsmethoden nach Produkten

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) werden typischerweise von PrestaShop selbst benötigt und sind für dieses Modul ausreichend.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

Dieses Modul verfügt über zwei Hauptkonfigurationsbereiche: die anfängliche Modulkonfigurationsseite und einen dedizierten Verwaltungsbildschirm zum Erstellen von Produkt-Zahlungs-Assoziationen.

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Zahlungsmethoden nach Produkten)

Nach dem Klicken auf „Konfigurieren“ nach der Installation gelangen Sie zur Hauptkonfigurationsseite des Moduls. Diese Seite enthält typischerweise allgemeine Einstellungen für das Modul.

**Derzeit sind auf dieser Hauptkonfigurationsseite keine spezifischen Einstellungen über die Standardmodulinformationen hinaus erkannt worden. Die Kernfunktionalität wird über den dedizierten Bildschirm „Zahlung - Produktassoziationen“ verwaltet.**

Sollten zukünftige Versionen hier Einstellungen einführen, würden diese als Schalter, Eingabefelder oder Dropdowns erscheinen. Vorerst können Sie direkt zum dedizierten Verwaltungsbildschirm übergehen.

### 2.2 Dedizierter Admin-Bildschirm: Zahlung - Produktassoziationen (Back Office > Module > Zahlungsmethoden nach Produkten > Zahlung - Produktassoziationen)

Dies ist die zentrale Anlaufstelle für die Verwaltung Ihrer Produkt-Zahlungsbeschränkungen. Sie finden diesen Bildschirm, indem Sie zu **Module > Modul-Manager** navigieren, „Zahlungsmethoden nach Produkten“ finden, auf „Konfigurieren“ klicken und dann nach einem Tab oder Link mit der Bezeichnung „Zahlung - Produktassoziationen“ suchen (oder ähnlich, je nach Navigation des Moduls).

**Bildschirmname & Menüpfad:**

- **Menüpfad:** Back Office > Module > Modul-Manager > Zahlungsmethoden nach Produkten > Konfigurieren > **Zahlung - Produktassoziationen** (oder ein ähnlicher Tab/Link auf der Konfigurationsseite).
- Dieser Bildschirm ermöglicht es Ihnen, Assoziationen zwischen Produkten und Zahlungsmethoden anzuzeigen, hinzuzufügen, zu bearbeiten und zu löschen.

**Verfügbare Aktionen & Einstellungen:**

#### 2.2.1 Die Listenansicht „Zahlung - Produktassoziationen“

Diese Ansicht präsentiert eine Tabelle aller bestehenden Produkt-Zahlungsbeschränkungen, die Sie eingerichtet haben.

| Spaltenname | Zweck & Auswirkung |
| --- | --- |
| **ID** | Eine eindeutige Kennung für jede Assoziation. |
| **Produkt** | Der Name des Produkts, das in der Beschränkung enthalten ist. |
| **Zahlung** | Der Name der Zahlungsmethode, die für dieses Produkt eingeschränkt oder erlaubt ist. |
| **Land** | (Falls zutreffend) Das Land, für das diese Beschränkung gilt. Wenn leer gelassen, gilt sie global. |
| **Aktionen** | Symbole zum **Bearbeiten** (Bleistiftsymbol) oder **Löschen** (Mülleimersymbol) einer bestehenden Assoziation. |

**Empfohlener Workflow für die tägliche Shop-Verwaltung:**

- **Bestehende Regeln überprüfen:** Überprüfen Sie diese Liste regelmäßig, um sicherzustellen, dass Ihre Beschränkungen mit Ihrem Produktkatalog und Ihren Geschäftsanforderungen übereinstimmen.
- **Konflikte identifizieren:** Suchen Sie nach überlappenden oder widersprüchlichen Regeln, insbesondere wenn Sie viele Produkte und Zahlungsmethoden haben.
- **Suche/Filter verwenden:** Wenn die Liste groß wird, verwenden Sie alle verfügbaren Such- oder Filteroptionen, um schnell spezifische Produkt- oder Zahlungsbeschränkungen zu finden.

#### 2.2.2 Hinzufügen oder Bearbeiten einer „Zahlung - Produktassoziation“

Um eine neue Beschränkung hinzuzufügen, finden Sie in der Listenansicht typischerweise eine Schaltfläche „Neu hinzufügen“. Beim Bearbeiten klicken Sie auf das Bleistiftsymbol neben einem bestehenden Eintrag. Dadurch wird ein Formular mit den folgenden Feldern geöffnet:

| Formularfeld | Was diese Einstellung bewirkt | Auswirkung einer Änderung dieser Einstellung | Empfohlener Wert | Händlerszenario / Beispiel |
| --- | --- | --- | --- | --- |
| **ID Produkt** | Dieses Feld ermöglicht Ihnen die Auswahl des spezifischen Produkts, das Sie mit Zahlungsbeschränkungen verknüpfen möchten. | Wenn Sie ein Produkt auswählen, wendet das Modul die gewählten Zahlungsbeschränkungen an, sobald dieses Produkt im Warenkorb eines Kunden liegt. | Wählen Sie das genaue Produkt aus Ihrem Katalog. Verwenden Sie die Suchfunktion, wenn Sie viele Produkte haben. | Sie verkaufen „Digitales E-Book: Marketing-Leitfaden“. Sie möchten sicherstellen, dass es nur über PayPal oder Kreditkarte bezahlt werden kann, nicht per Nachnahme. Sie wählen dieses Produkt hier aus. |
| **Zahlungsmethoden** | Dies ist eine Liste aller aktiven Zahlungsmethoden in Ihrem PrestaShop-Shop. Sie wählen aus, welche Zahlungsmethoden für das ausgewählte Produkt **erlaubt** sind. | - *Wenn Sie eine oder mehrere Zahlungsmethoden auswählen:* Nur diese ausgewählten Methoden sind an der Kasse verfügbar, wenn das zugehörige Produkt im Warenkorb liegt. Alle anderen Zahlungsmethoden werden ausgeblendet.   - *Wenn Sie KEINE Zahlungsmethoden auswählen:* Dies bedeutet effektiv, dass das Produkt nicht gekauft werden kann, oder es erbt Regeln von anderen Produkten im Warenkorb. Es wird im Allgemeinen nicht empfohlen, dieses Feld leer zu lassen, es sei denn, Sie haben einen sehr spezifischen Anwendungsfall. | Wählen Sie alle Zahlungsmethoden aus, die für das ausgewählte Produkt akzeptabel sind. | Für „Digitales E-Book: Marketing-Leitfaden“ aktivieren Sie „PayPal“ und „Kreditkarte“. Wenn ein Kunde dieses E-Book kauft, erscheinen an der Kasse nur diese beiden Optionen. |
| **Land** | (Optional) Dieses Feld ermöglicht Ihnen die Angabe eines Landes, für das diese spezielle Produkt-Zahlungsbeschränkung gilt. | - *Wenn ein Land ausgewählt ist:* Die Beschränkung (Produkt + erlaubte Zahlungen) gilt nur, wenn die Lieferadresse des Kunden in dem ausgewählten Land liegt.   - *Wenn leer gelassen:* Die Beschränkung gilt global, unabhängig vom Land des Kunden. | Lassen Sie es für globale Anwendung leer oder wählen Sie ein bestimmtes Land aus, wenn die Beschränkung geografisch begrenzt ist. | Sie verkaufen „Zerbrechliche Glasskulptur“, die aufgrund von Versandversicherungsanforderungen in Frankreich nur per „Banküberweisung“ bezahlt werden kann. Sie wählen die Skulptur, „Banküberweisung“ und „Frankreich“ aus. Für Kunden außerhalb Frankreichs könnten für dieses Produkt (wenn keine anderen globalen Regeln gelten) weiterhin andere Zahlungsmethoden verfügbar sein. |
| **Speichern** | Diese Schaltfläche speichert Ihre neue oder aktualisierte Produkt-Zahlungsassoziation. | Die Änderungen werden sofort auf den Checkout-Prozess Ihres Shops angewendet. | Klicken Sie immer auf „Speichern“, nachdem Sie Änderungen vorgenommen haben. | Nachdem Sie die Regeln für Ihr „Digitales E-Book“ eingerichtet haben, klicken Sie auf „Speichern“, um sie zu aktivieren. |

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfigurationsseite | (Keine spezifischen Einstellungen erkannt) | N/A | Allgemeine Modulinformationen. |
| Zahlung - Produktassoziationen (Liste) | ID | N/A | Eindeutige Kennung für die Assoziation. |
| Zahlung - Produktassoziationen (Liste) | Produkt | N/A | Name des Produkts in der Assoziation. |
| Zahlung - Produktassoziationen (Liste) | Zahlung | N/A | Name der Zahlungsmethode in der Assoziation. |
| Zahlung - Produktassoziationen (Liste) | Land | N/A | Land, für das die Beschränkung gilt (falls vorhanden). |
| Zahlung - Produktassoziationen (Hinzufügen/Bearbeiten-Formular) | ID Produkt | Ein Produkt auswählen | Gibt das Produkt an, für das Zahlungsmethoden eingeschränkt werden. |
| Zahlung - Produktassoziationen (Hinzufügen/Bearbeiten-Formular) | Zahlungsmethoden | Alle akzeptablen Methoden auswählen | Definiert, welche Zahlungsmethoden für das ausgewählte Produkt **erlaubt** sind. |
| Zahlung - Produktassoziationen (Hinzufügen/Bearbeiten-Formular) | Land | Für globale Anwendung leer lassen oder spezifisches auswählen | Begrenzt die Beschränkung auf ein bestimmtes Land. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe eine Beschränkung eingerichtet, aber an der Kasse werden immer noch alle Zahlungsmethoden angezeigt. Was ist falsch?**
A:

1.  **Cache:** Leeren Sie immer Ihren PrestaShop-Cache, nachdem Sie Änderungen vorgenommen haben. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen).
2.  **Produkt im Warenkorb:** Stellen Sie sicher, dass das spezifische Produkt, das Sie eingeschränkt haben, beim Testen tatsächlich im Warenkorb des Kunden liegt. Das Modul wendet Regeln nur an, wenn das Produkt vorhanden ist.
3.  **Zahlungsmethode aktiviert:** Überprüfen Sie nochmals, ob die Zahlungsmethoden, die Sie *erwarten* zu sehen, tatsächlich unter **Module > Zahlung > Zahlungsmethoden** aktiviert sind. Dieses Modul filtert *aktivierte* Methoden, es aktiviert sie nicht selbst.
4.  **Widersprüchliche Regeln:** Wenn Sie mehrere Produkte im Warenkorb haben und jedes Beschränkungen aufweist, zeigt das Modul nur Zahlungsmethoden an, die von *allen* eingeschränkten Produkten erlaubt sind. Wenn es keine gemeinsame erlaubte Methode gibt, kann es so aussehen, als ob keine Methoden angezeigt werden. Überprüfen Sie Ihre Assoziationen sorgfältig.

**F: Ich habe eine Beschränkung eingerichtet, und jetzt werden an der Kasse KEINE Zahlungsmethoden angezeigt!**
A: Dies geschieht normalerweise, wenn:

1.  **Keine gemeinsamen Methoden:** Sie haben mehrere eingeschränkte Produkte im Warenkorb, und es gibt keine Zahlungsmethoden, die von *allen* erlaubt sind. Zum Beispiel erlaubt Produkt A PayPal, Produkt B erlaubt Kreditkarte. Wenn beide im Warenkorb sind, wird keines angezeigt. Sie müssen sicherstellen, dass es mindestens eine gemeinsame erlaubte Methode gibt.
2.  **Leere erlaubte Liste:** Sie haben eine Assoziation für ein Produkt erstellt, aber *keine* Zahlungsmethoden als erlaubt ausgewählt. Das Modul blendet dann alle Methoden für dieses Produkt aus. Bearbeiten Sie die Assoziation und wählen Sie die entsprechenden Zahlungsmethoden aus.

**F: Beeinflusst dieses Modul Zahlungsmethoden für Produkte, die NICHT in einer Assoziation enthalten sind?**
A: Nein. Wenn ein Produkt nicht Teil einer „Zahlung - Produktassoziation“ ist, werden keine Beschränkungen auferlegt. Das Modul wirkt nur auf Produkte, für die Sie explizit Regeln definiert haben. Wenn ein Warenkorb nur uneingeschränkte Produkte enthält, werden alle standardmäßigen, aktivierten Zahlungsmethoden Ihres Shops angezeigt.

**F: Wie interagiert dieses Modul mit anderen Zahlungsbeschränkungsmodulen (z. B. nach Kundengruppe, nach Gesamtbetrag)?**
A: Dieses Modul funktioniert typischerweise, indem es die Kernklasse `PaymentOptionsFinder` von PrestaShop überschreibt (wie im `override`-Ordner zu sehen). Das bedeutet, es hat Vorrang oder integriert sich auf einer grundlegenden Ebene. Im Allgemeinen gilt die restriktivste Regel. Wenn ein anderes Modul eine Zahlungsmethode einschränkt und dieses Modul sie für ein Produkt erlaubt, wird die Zahlungsmethode wahrscheinlich immer noch durch das andere Modul eingeschränkt. Es ist entscheidend, gründlich zu testen, wenn Sie mehrere Beschränkungsmodule verwenden.

**F: Kann ich Zahlungsmethoden nach Land einschränken, ohne sie nach Produkt einzuschränken?**
A: Die Hauptfunktion dieses Moduls ist die produktbasierte Beschränkung. Obwohl es ein Feld „Land“ hat, gilt es *für die Produkt-Zahlungsassoziation*. Wenn Sie rein länderspezifische Zahlungsbeschränkungen benötigen (unabhängig vom Produkt), benötigen Sie möglicherweise ein separates Modul, das dafür entwickelt wurde, oder prüfen Sie, ob Ihre Zahlungsgateways direkte Länderbeschränkungen anbieten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Einblick in das Modul „Zahlungsmethoden nach Produkten“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul erweitert hauptsächlich den Kernmechanismus zur Ermittlung von Zahlungsoptionen in PrestaShop. Es nutzt einen `override`, um die Klasse `PaymentOptionsFinder` zu modifizieren, die für die Bestimmung der verfügbaren Zahlungsmethoden während des Checkouts verantwortlich ist. Dies ermöglicht es dem Modul, seine produktbasierte Filterlogik direkt in den Prozess der Zahlungsoptionsabfrage einzuschleusen und so eine nahtlose Integration in den PrestaShop-Checkout-Flow zu gewährleisten.
Das Modul folgt einem standardmäßigen PrestaShop MVC-Muster für seine Back-Office-Verwaltung und verwendet einen AdminController zur Verwaltung der `pobp`-Entität (Produkt-Zahlungs-Assoziation).

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Die Front-Office-Funktionalität des Moduls wird über einen Override einer Kernklasse und nicht über einen dedizierten Front-Controller abgewickelt.
- **Back-Office-Admin-Controller**:

  - `pobp/controllers/admin/AdminPobpController.php`
    - **Klassenname & Elternklasse**: `AdminPobpController` erweitert `ModuleAdminController`.
    - **Tab-Name**: Dieser Controller verwaltet die Entität „Zahlung - Produktassoziationen“. Er ist wahrscheinlich als Unter-Tab unter der Hauptkonfiguration des Moduls registriert.
    - **Verantwortlichkeit**: Dies ist der Haupt-CRUD-Controller (Create, Read, Update, Delete) für die Produkt-Zahlungsassoziationen. Er verwaltet:
      - Die Anzeige der Liste der bestehenden Assoziationen (ID, Produkt, Zahlung, Land).
      - Die Bereitstellung des Formulars zum Hinzufügen neuer Assoziationen oder zum Bearbeiten bestehender.
      - Die Verarbeitung von Formularübermittlungen zum Speichern neuer oder aktualisierter Assoziationen in der Datenbank.
      - Die Handhabung des Löschens von Assoziationen.
      - Die Formularfelder „ID Produkt“, „Zahlungsmethoden“ und „Land“ werden hier verwaltet.
  - `pobp/controllers/admin/index.php`
    - Diese Datei ist typischerweise ein leerer Platzhalter oder enthält grundlegende Sicherheitsmaßnahmen (z. B. `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;`). Sie stellt keine funktionale Controller-Ansicht selbst dar, sondern stellt sicher, dass der direkte Zugriff auf das Verzeichnis `controllers/admin` umgeleitet wird.

### 4.3 Kernklassen & Modelle (`classes/`)

- `pobp/override/classes/checkout/PaymentOptionsFinder.php`
  - **Zweck**: Dies ist eine kritische Override-Datei. Sie modifiziert die PrestaShop-Kernklasse, die für das Finden und Zurückgeben verfügbarer Zahlungsoptionen während des Checkouts verantwortlich ist.
  - **Klassenname & Elternklasse**: `PaymentOptionsFinder` (überschreibt die ursprüngliche `PaymentOptionsFinder`-Klasse).
  - **Schlüssellogik**: Die überschriebene Methode `getPaymentOptions()` (oder eine ähnliche Methode) enthält die Kernlogik des Moduls.
    - Sie ruft die Produkte ab, die sich derzeit im Warenkorb des Kunden befinden.
    - Für jedes Produkt prüft sie, ob in der Datenbank des Moduls „Zahlung - Produktassoziationen“ definiert sind.
    - Anschließend filtert sie die anfänglich verfügbaren Zahlungsoptionen (die von der übergeordneten `getPaymentOptions()`-Methode zurückgegeben werden) basierend auf diesen Assoziationen.
    - Die Filterlogik stellt sicher, dass nur Zahlungsmethoden zurückgegeben werden, die für *alle* eingeschränkten Produkte im Warenkorb explizit erlaubt sind. Wenn ein Produkt keine Assoziation hat, schränkt es nichts ein. Wenn mehrere Produkte Assoziationen haben, wird die Schnittmenge der erlaubten Zahlungsmethoden verwendet.
  - **Datenbankinteraktion**: Diese Klasse fragt die benutzerdefinierte Datenbanktabelle des Moduls (wahrscheinlich `ps_pobp` oder ähnlich) ab, um die Produkt-Zahlungsassoziationen abzurufen.

### 4.4 JavaScript-Assets (`views/js/`)

Es wurden keine spezifischen JavaScript-Dateien im bereitgestellten Inventar erkannt. Jedes dynamische Verhalten im Back Office (wie die Produktsuche im Assoziationsformular) wird wahrscheinlich durch PrestaShops Kern-JS oder ein minimales Inline-Skript gehandhabt.

### 4.5 CSS-Stylesheets (`views/css/`)

Es wurden keine spezifischen CSS-Dateien im bereitgestellten Inventar erkannt. Die Formatierung für die Back-Office-Formulare und -Listen wird wahrscheinlich vom Standard-Admin-Theme von PrestaShop geerbt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**: Keine explizit aufgeführt, da das Modul über einen Override und nicht über direkte Hook-Wiedergabe im Front Office arbeitet.
- **Admin-Templates (`views/templates/admin/`)**:
  - `pobp/lib/searchTool/views/scripts.tpl`
    - **Zweck**: Dieses Template enthält wahrscheinlich JavaScript- oder Smarty-Logik, die sich auf ein Suchwerkzeug im Back Office bezieht, möglicherweise zum Suchen von Produkten beim Erstellen oder Bearbeiten einer Assoziation. Es könnte AJAX-Aufrufe oder dynamische Filterung für die Produktauswahl beinhalten.
- **Front-Office-Templates (`views/templates/front/`)**: Keine.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul erstellt während seiner `install()`-Methode (definiert in `pobp/index.php`) mindestens eine benutzerdefinierte Tabelle.
  - **`ps_pobp` (oder ähnlicher Name, z. B. `ps_payment_by_product_association`)**:
    - Diese Tabelle speichert die tatsächlichen Produkt-Zahlungsassoziationen.
    - Erwartete Spalten:
      - `id_pobp` (Primärschlüssel, INT)
      - `id_product` (INT, Fremdschlüssel zu `ps_product`)
      - `id_payment_module` (INT, Fremdschlüssel zu `ps_module` oder `ps_payment_module`, falls eine solche Tabelle existiert, oder speichert einfach den Namen/die ID des Moduls)
      - `id_country` (INT, Fremdschlüssel zu `ps_country`, nullable für globale Regeln)
      - Weitere potenzielle Spalten für Einstellungen oder Zeitstempel.
  - Konfigurationswerte (falls in `getContent()` vorhanden) würden in `ps_configuration` gespeichert.
- **Registrierte Hooks-Tabelle**:
  Die Kernfunktionalität des Moduls basiert auf dem `override`-Mechanismus und nicht auf der direkten Hook-Ausführung für seine primäre Filterung. Für seine Back-Office-Integration und potenziell für zukünftige Funktionen könnte es jedoch Standard-Hooks registrieren.

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayAdminProductsExtra` | Auf der Produktbearbeitungsseite im Back Office. | Könnte verwendet werden, um einen Schnelllink oder eine Zusammenfassung der Zahlungsbeschränkungen für das aktuelle Produkt anzuzeigen. (Nicht explizit erkannt, aber ein häufiger Integrationspunkt). |
  | `actionPaymentOptionsModifier` | Während des Abrufvorgangs der Zahlungsoptionen. | Dieser Hook ist speziell für Module konzipiert, um die Liste der Zahlungsoptionen zu ändern. Der Override von `PaymentOptionsFinder` erzielt effektiv ein ähnliches Ergebnis auf einer niedrigeren Ebene. |
  | `actionModuleInstall` | Wenn das Modul installiert wird. | Zum Erstellen von Datenbanktabellen und Registrieren notwendiger Hooks. |
  | `actionModuleUninstall` | Wenn das Modul deinstalliert wird. | Zum Bereinigen von Datenbanktabellen und Deregistrieren von Hooks. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und um sicherzustellen, dass Sie die neueste kompatible Version des Moduls „Zahlungsmethoden nach Produkten“ haben, besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.

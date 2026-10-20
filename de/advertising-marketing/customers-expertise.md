---
title: "Kunden-Expertise - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Kunden-Expertise von MyPresta.eu."
sidebar:
  label: "Kunden-Expertise - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Customers Expertise auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/customers-expertise.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/customers-expertise/)
>
> ---


# Kunden-Expertise

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und in jeder modernen Hosting-Umgebung vorhanden. Keine speziellen Hosting-Anforderungen über eine Standard-PrestaShop-Installation hinaus.

## 2. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > Kunden-Expertise)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie Ihre Errungenschaften, deren Kriterien und die Belohnungen definieren. Die Konfiguration des Moduls wird über eine dedizierte Oberfläche verwaltet, die es Ihnen ermöglicht, Errungenschaften hinzuzufügen, zu bearbeiten und zu entfernen.

**Bildschirmname & Menüpfad:**
Sie können diesen Bildschirm erreichen, indem Sie zu **Module > Modul-Manager** navigieren, nach „Kunden-Expertise“ suchen und auf die Schaltfläche „Konfigurieren“ klicken.

**Verfügbare Aktionen & Einstellungen:**
Die Konfigurationsseite zeigt eine Liste Ihrer aktuell definierten Errungenschaften an. Sie finden typischerweise Optionen zum:

- **Neue Errungenschaft hinzufügen:** Eine Schaltfläche oder ein Link zum Erstellen einer neuen Errungenschaft.
- **Bestehende Errungenschaft bearbeiten:** Ein Symbol (z. B. Bleistift) neben jeder Errungenschaft in der Liste, um deren Einstellungen zu ändern.
- **Errungenschaft löschen:** Ein Symbol (z. B. Mülleimer) neben jeder Errungenschaft, um sie zu entfernen.

Beim Hinzufügen oder Bearbeiten einer Errungenschaft werden Sie typischerweise die folgenden Einstellungen finden:

#### **Errungenschaftsdetails**

- **Name der Errungenschaft:**

  - **Was diese Einstellung bewirkt:** Dies ist der Titel der Errungenschaft, den Ihre Kunden sehen werden (z. B. „Erstkäufer“, „Bewertungsmeister“, „VIP-Käufer“).
  - **Auswirkung der Änderung dieser Einstellung:** Dieser Name wird im Abschnitt „Meine Errungenschaften“ des Kunden angezeigt. Ein klarer und ansprechender Name fördert die Beteiligung.
  - **Empfohlener Wert:** Etwas Beschreibendes und Motivierendes.
  - **Händlerszenario / Beispiel:** „Held der ersten Bestellung“ für den ersten Einkauf eines Kunden.
- **Beschreibung der Errungenschaft:**

  - **Was diese Einstellung bewirkt:** Eine kurze Erklärung, worum es bei der Errungenschaft geht und wie man sie verdient. Dies hilft Kunden, das Ziel zu verstehen.
  - **Auswirkung der Änderung dieser Einstellung:** Diese Beschreibung erscheint neben dem Namen. Eine gute Beschreibung klärt die Errungenschaftskriterien.
  - **Empfohlener Wert:** Prägnant und ermutigend.
  - **Händlerszenario / Beispiel:** „Machen Sie Ihren allerersten Einkauf in unserem Shop, um dieses Abzeichen zu verdienen!“
- **Bild/Icon der Errungenschaft:**

  - **Was diese Einstellung bewirkt:** Ermöglicht das Hochladen einer visuellen Darstellung (Abzeichen, Icon) für die Errungenschaft.
  - **Auswirkung der Änderung dieser Einstellung:** Dieses Bild wird neben dem Namen der Errungenschaft angezeigt, wodurch es visuell ansprechend und erkennbar wird.
  - **Empfohlener Wert:** Ein einzigartiges, hochwertiges Bild, das das Thema der Errungenschaft widerspiegelt.
  - **Händlerszenario / Beispiel:** Ein „Stern“-Icon für eine „Top-Rezensent“-Errungenschaft.
- **Aktiv / Aktiviert:**

  - **Was diese Einstellung bewirkt:** Ein Schalter zum Aktivieren oder Deaktivieren der Errungenschaft.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert:* Die Errungenschaft ist aktiv, Kunden können sie verdienen und sie wird in ihrer Errungenschaftsliste angezeigt.
    - *Wenn deaktiviert:* Die Errungenschaft ist ausgeblendet, Kunden können sie nicht verdienen und sie wird nicht im Front Office angezeigt. Nützlich für saisonale Errungenschaften oder solche, die Sie noch vorbereiten.
  - **Empfohlener Wert:** JA für aktive Errungenschaften.
  - **Händlerszenario / Beispiel:** Deaktivieren Sie eine „Weihnachtskäufer“-Errungenschaft nach der Weihnachtszeit.

#### **Errungenschaftskriterien (Wie man sie verdient)**

Dies ist der Kern des Moduls, wo Sie die Bedingungen definieren, die ein Kunde erfüllen muss. Das Modul bietet wahrscheinlich verschiedene Kriterientypen. Häufige Beispiele sind:

- **Anzahl der Bestellungen:**

  - **Was diese Einstellung bewirkt:** Der Kunde muss eine bestimmte Anzahl von Bestellungen aufgeben.
  - **Auswirkung der Änderung dieser Einstellung:** Bestimmt, wie viele erfolgreiche Bestellungen erforderlich sind.
  - **Empfohlener Wert:** Beginnen Sie mit niedrigen Zahlen für anfängliche Errungenschaften (z. B. 1, 3) und erhöhen Sie diese für höhere Stufen.
  - **Händlerszenario / Beispiel:** Auf „1“ für „Erstkäufer“, auf „5“ für „Treuer Kunde“ setzen.
- **Gesamtausgegebener Betrag:**

  - **Was diese Einstellung bewirkt:** Die kumulierten Ausgaben des Kunden über alle Bestellungen hinweg müssen einen bestimmten Betrag erreichen.
  - **Auswirkung der Änderung dieser Einstellung:** Definiert den monetären Schwellenwert.
  - **Empfohlener Wert:** Passen Sie ihn an Ihren durchschnittlichen Bestellwert und Ihre Kundensegmente an.
  - **Händlerszenario / Beispiel:** Auf „100 €“ für „Bronze-Käufer“, auf „500 €“ für „Silber-Käufer“ setzen.
- **Anzahl der gekauften Produkte:**

  - **Was diese Einstellung bewirkt:** Der Kunde muss eine bestimmte Gesamtmenge an Produkten (über alle Bestellungen hinweg) kaufen.
  - **Auswirkung der Änderung dieser Einstellung:** Legt den Mengenschwellenwert fest.
  - **Empfohlener Wert:** Nützlich, um Großeinkäufe oder das Ausprobieren verschiedener Produkte zu fördern.
  - **Händlerszenario / Beispiel:** Auf „10“ für „Produktsammler“ setzen.
- **Anzahl der Produktbewertungen:**

  - **Was diese Einstellung bewirkt:** Der Kunde muss eine bestimmte Anzahl genehmigter Produktbewertungen einreichen.
  - **Auswirkung der Änderung dieser Einstellung:** Fördert nutzergenerierte Inhalte und Social Proof.
  - **Empfohlener Wert:** Auf „1“ für „Erster Rezensent“, auf „5“ für „Bewertungsmeister“ setzen.
  - **Händlerszenario / Beispiel:** Belohnen Sie Kunden für wertvolles Feedback.
- **Kauf eines bestimmten Produkts/einer bestimmten Kategorie:**

  - **Was diese Einstellung bewirkt:** Der Kunde muss ein Produkt aus einer bestimmten Kategorie oder ein bestimmtes Produkt selbst kaufen.
  - **Auswirkung der Änderung dieser Einstellung:** Fördert spezifische Artikel oder Kategorien.
  - **Empfohlener Wert:** Verwenden Sie dies für neue Produkteinführungen oder langsam verkaufende Bestände.
  - **Händlerszenario / Beispiel:** „Neues Kollektionsstück gekauft“ für den Kauf aus einer Kategorie „Neuheiten“.

#### **Errungenschaftsbelohnung (Rabattgutschein)**

- **Gutscheintyp:**

  - **Was diese Einstellung bewirkt:** Definiert die Art des Rabattcodes, den der Kunde erhält (z. B. Prozentsatz, fester Betrag, kostenloser Versand).
  - **Auswirkung der Änderung dieser Einstellung:** Bestimmt die Art der Belohnung.
  - **Empfohlener Wert:** Prozentuale Rabatte sind oft beliebt, aber feste Beträge können für kleinere Einkäufe gut sein.
  - **Händlerszenario / Beispiel:** „Prozentualer Rabatt“ für 10 % Rabatt auf die nächste Bestellung.
- **Gutscheinwert:**

  - **Was diese Einstellung bewirkt:** Der tatsächliche Wert des Rabatts (z. B. „10“ für 10 %, „5 €“ für einen festen Betrag).
  - **Auswirkung der Änderung dieser Einstellung:** Wirkt sich direkt auf den Anreiz für den Kunden aus.
  - **Empfohlener Wert:** Balancieren Sie Großzügigkeit mit Ihren Gewinnmargen.
  - **Händlerszenario / Beispiel:** „15“ für einen 15 % Rabatt.
- **Gutschein-Gültigkeitsdauer (Tage):**

  - **Was diese Einstellung bewirkt:** Wie viele Tage der generierte Gutschein ab dem Zeitpunkt, an dem der Kunde ihn beansprucht, gültig ist.
  - **Auswirkung der Änderung dieser Einstellung:** Erzeugt Dringlichkeit für den Kunden, den Gutschein zu verwenden.
  - **Empfohlener Wert:** 7-30 Tage sind üblich. Zu kurz kann frustrieren, zu lang reduziert die Dringlichkeit.
  - **Händlerszenario / Beispiel:** Auf „14“ Tage setzen, um einen schnellen Wiederholungskauf zu fördern.
- **Mindestbestellwert für Gutschein:**

  - **Was diese Einstellung bewirkt:** Ob der Gutschein einen Mindestbestellwert erfordert, um verwendet zu werden.
  - **Auswirkung der Änderung dieser Einstellung:** Hilft, Ihre Margen zu schützen und ermutigt Kunden, mehr auszugeben.
  - **Empfohlener Wert:** Legen Sie ein angemessenes Minimum fest, das einen Upsell fördert, ohne prohibitiv zu sein.
  - **Händlerszenario / Beispiel:** „30 €“ Mindestbestellung für einen 5 € Rabatt.
- **Gutschein-Präfix:**

  - **Was diese Einstellung bewirkt:** Ein benutzerdefiniertes Präfix für die generierten Rabattcodes (z. B. „ERFOLG-“, „ABZEICHEN-“).
  - **Auswirkung der Änderung dieser Einstellung:** Hilft Ihnen, die Quelle der Rabattcodes in Ihren PrestaShop-Verkaufsberichten zu identifizieren.
  - **Empfohlener Wert:** Ein kurzes, einprägsames Präfix.
  - **Händlerszenario / Beispiel:** „EXPERT-“, damit Sie wissen, dass der Gutschein vom Modul Kunden-Expertise stammt.

**Empfohlener Workflow für die tägliche Shop-Verwaltung:**

1. **Planen Sie Ihre Errungenschaften:** Bevor Sie erstellen, entscheiden Sie, welche Verhaltensweisen Sie belohnen möchten und wie viele Stufen von Errungenschaften Sie wünschen.
2. **Beginnen Sie einfach:** Starten Sie mit 2-3 grundlegenden Errungenschaften (z. B. erste Bestellung, Gesamtausgaben, Anzahl der Bewertungen), um die Gewässer zu testen.
3. **Erstellen Sie jede Errungenschaft:** Durchlaufen Sie den Prozess „Neue Errungenschaft hinzufügen“ und definieren Sie sorgfältig Kriterien und Belohnungen.
4. **Überwachen Sie die Kundenbindung:** Überprüfen Sie Ihre Verkäufe und Kundenkonten, um zu sehen, wie Kunden mit den Errungenschaften interagieren.
5. **Anpassen und erweitern:** Verfeinern Sie basierend auf der Leistung bestehende Errungenschaften oder führen Sie neue, komplexere ein.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modul-Konfigurationsseite** | Name der Errungenschaft | Beschreibend | Titel, der dem Kunden angezeigt wird. |
| | Beschreibung der Errungenschaft | Informativ | Erklärt, wie die Errungenschaft verdient wird. |
| | Bild/Icon der Errungenschaft | Einzigartiges Bild | Visuelle Darstellung für das Abzeichen. |
| | Aktiv / Aktiviert | JA | Schaltet die Sichtbarkeit und Berechtigung der Errungenschaft um. |
| | **Kriterien: Anzahl der Bestellungen** | 1, 3, 5 | Kunde muss X Bestellungen aufgeben. |
| | **Kriterien: Gesamtausgegebener Betrag** | 50 €, 100 €, 500 € | Die Gesamtausgaben des Kunden müssen X erreichen. |
| | **Kriterien: Anzahl der gekauften Produkte** | 5, 10, 20 | Kunde muss insgesamt X Produkte kaufen. |
| | **Kriterien: Anzahl der Produktbewertungen** | 1, 3, 5 | Kunde muss X genehmigte Bewertungen einreichen. |
| | **Kriterien: Kauf eines bestimmten Produkts/einer bestimmten Kategorie** | (Produkt/Kategorie auswählen) | Kunde muss aus einem bestimmten Produkt/einer bestimmten Kategorie kaufen. |
| | **Belohnung: Gutscheintyp** | Prozentsatz | Art des Rabatts (%, fester Betrag, kostenloser Versand). |
| | **Belohnung: Gutscheinwert** | 10 (für %) | Der Betrag des Rabatts. |
| | **Belohnung: Gutschein-Gültigkeitsdauer (Tage)** | 14-30 | Wie lange der Gutschein nach der Beanspruchung gültig ist. |
| | **Belohnung: Mindestbestellwert für Gutschein** | (Optional) | Mindestwarenkorbwert, der zur Nutzung des Gutscheins erforderlich ist. |
| | **Belohnung: Gutschein-Präfix** | EXPERT- | Benutzerdefiniertes Präfix für generierte Rabattcodes. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Meine Kunden sehen den Errungenschaften-Bereich in ihrem Konto nicht.**
A: Stellen Sie zunächst sicher, dass das Modul „Kunden-Expertise“ in Ihrem Back Office installiert und aktiviert ist. Überprüfen Sie die Modulkonfiguration, um sicherzustellen, dass Sie mindestens eine Errungenschaft erstellt und auf „Aktiv“ gesetzt haben. Überprüfen Sie außerdem, ob die `customer-account.tpl`-Datei Ihres Themes (oder eine entsprechende Datei) korrekt verknüpft ist, um den Link des Moduls anzuzeigen. Wenn Sie ein benutzerdefiniertes Theme verwenden, müssen Sie möglicherweise einen Webmaster beauftragen, um sicherzustellen, dass der Hook gerendert wird.

**F: Kunden verdienen Errungenschaften, erhalten aber keine Rabattcodes.**
A: Gehen Sie zur Modulkonfiguration und bearbeiten Sie die spezifische Errungenschaft. Überprüfen Sie nochmals, ob ein „Gutscheintyp“ und ein „Gutscheinwert“ für die Belohnung korrekt definiert sind. Stellen Sie sicher, dass keine Tippfehler oder falschen Einstellungen in den Gutscheinparametern vorhanden sind. Überprüfen Sie auch Ihre PrestaShop „Warenkorbregeln“ (oder „Rabatte“ in älteren Versionen), um zu sehen, ob die generierten Gutscheine dort erscheinen.

**F: Die Errungenschaftsbilder werden nicht korrekt angezeigt.**
A: Dies deutet normalerweise auf ein Problem beim Hochladen des Bildes oder bei den Dateiberechtigungen hin. Stellen Sie sicher, dass die hochgeladene Bilddatei ein Standard-Webformat (JPG, PNG, GIF) ist und nicht zu groß. Überprüfen Sie die Dateiberechtigungen Ihres Servers für das Bildverzeichnis des Moduls (z. B. `modules/customersexpertise/img/`), um sicherzustellen, dass PrestaShop dort Dateien schreiben und lesen kann. Das Leeren Ihres PrestaShop-Caches (Erweiterte Parameter > Leistung) kann ebenfalls helfen.

**F: Kann ich die Namen und Beschreibungen der Errungenschaften in mehrere Sprachen übersetzen?**
A: Ja, wie die meisten PrestaShop-Module sollten die Textfelder für Errungenschaftsnamen und -beschreibungen mehrsprachige Eingaben unterstützen. Suchen Sie beim Bearbeiten einer Errungenschaft nach Sprachflaggen neben den Eingabefeldern, die es Ihnen ermöglichen, Übersetzungen für jede in Ihrem Shop installierte Sprache bereitzustellen.

**F: Was passiert, wenn ein Kunde eine Errungenschaft verdient, ich sie aber später deaktiviere?**
A: Wenn eine Errungenschaft deaktiviert wird, können neue Kunden sie nicht mehr verdienen, und sie wird typischerweise aus dem Front Office ausgeblendet. Kunden, die sie bereits verdient haben, behalten in der Regel ihren verdienten Status und alle zugehörigen Gutscheine, die sie vor der Deaktivierung der Errungenschaft beansprucht haben. Sie können jedoch keine Gutscheine erneut beanspruchen, wenn die Errungenschaft wieder aktiviert wird und sie bereits einen haben.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster, die mit dem Modul Kunden-Expertise arbeiten.

### 4.1 Architekturübersicht

Das Modul Kunden-Expertise folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich Front-Controller für kundenorientierte Interaktionen und die Hauptmodulklasse für Konfiguration und Hook-Verwaltung nutzt. Es integriert Gamification-Logik, indem es Kundenaktionen (Bestellungen, Bewertungen) verfolgt und dynamisch PrestaShop `CartRule` (Gutschein)-Objekte als Belohnungen generiert. Die Kernlogik des Moduls befindet sich in seiner Haupt-PHP-Datei und dedizierten Front-Controllern, wobei Smarty-Templates die Präsentationsschicht handhaben.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller handhaben die kundenorientierte Logik und Anzeige für Errungenschaften und verwandte Funktionen.

- `controllers/front/achievements.php`

  - **Klassenname & Elternklasse:** `CustomersExpertiseAchievementsModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dies ist der primäre Controller zur Anzeige der Errungenschaften eines Kunden. Er ruft alle definierten Errungenschaften ab, überprüft die Berechtigung und den verdienten Status des aktuellen Kunden für jede Errungenschaft und bereitet die Daten für das `achievements.tpl`-Template vor. Er handhabt wahrscheinlich die Logik zum Beanspruchen von Gutscheinen, sobald eine Errungenschaft verdient wurde.
  - **Routen:** Typischerweise über eine URL wie `ihrshop.com/module/customersexpertise/achievements` zugänglich.
- `controllers/front/affiliationlink.php`

  - **Klassenname & Elternklasse:** `CustomersExpertiseAffiliationlinkModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Obwohl die Modulbeschreibung keine explizite Erwähnung von Affiliation enthält, deutet dieser Controller auf eine potenzielle Funktion hin, die es Kunden ermöglicht, Affiliationslinks zu generieren und zu verwalten, möglicherweise als Errungenschaftsbelohnung oder als eigenständige Funktion. Er würde die Anzeige und Generierung solcher Links handhaben.
  - **Routen:** Wahrscheinlich `ihrshop.com/module/customersexpertise/affiliationlink`.
- `controllers/front/index.php`

  - **Klassenname & Elternklasse:** `CustomersExpertiseIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dient oft als Standard- oder Fallback-Front-Controller. Er könnte zum `achievements`-Controller weiterleiten oder eine allgemeine Landingpage für das Modul anzeigen, wenn keine spezifische Aktion angefordert wird.
  - **Routen:** `ihrshop.com/module/customersexpertise/index` oder `ihrshop.com/module/customersexpertise`.
- `controllers/front/voucher.php`

  - **Klassenname & Elternklasse:** `CustomersExpertiseVoucherModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist wahrscheinlich für den eigentlichen Prozess der Generierung und Zuweisung eines Rabattgutscheins an einen Kunden verantwortlich, sobald dieser eine verdiente Errungenschaft beansprucht. Er würde mit dem PrestaShop `CartRule`-Objekt interagieren, um den Gutschein zu erstellen und möglicherweise den Errungenschaftsstatus des Kunden zu aktualisieren.
  - **Routen:** Könnte ein AJAX-Endpunkt oder eine direkte URL für die Gutscheinbeanspruchung sein, z. B. `ihrshop.com/module/customersexpertise/voucher`.

#### Back-Office-Admin-Controller

Das Modul scheint keine dedizierten benutzerdefinierten Admin-Controller zu haben. Die Konfiguration wird über die `getContent()`-Methode der Hauptmodulklasse gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Das bereitgestellte Inventar zeigt keine benutzerdefinierten Klassen im Verzeichnis `classes/` an. Dies deutet darauf hin, dass die Kernlogik des Moduls, die Errungenschaftsdefinitionen und die Kundenverfolgung wahrscheinlich direkt in der Hauptmoduldatei (`ajax_customersexpertise.php`) und möglicherweise durch die Nutzung bestehender PrestaShop `ObjectModel`-Klassen wie `Customer`, `Order`, `Product` und `CartRule` verwaltet werden.

Das Modul würde intern Errungenschaftsdaten verwalten, möglicherweise durch:

- Speichern von Errungenschaftsdefinitionen (Name, Beschreibung, Kriterien, Belohnung) in der Tabelle `ps_configuration` als serialisierte Arrays oder JSON.
- Speichern des Kunden-Errungenschaftsstatus (verdient, Gutschein beansprucht) in einer benutzerdefinierten Tabelle, die während der Installation erstellt wurde, oder ebenfalls in `ps_configuration` oder `ps_customer` Metafeldern.

### 4.4 JavaScript-Assets (`views/js/`)

- `customersexpertise/lib/voucherengine/script.js`
  - **Geltungsbereich:** Wahrscheinlich Front-Office.
  - **Details:** Dieses Skript ist wahrscheinlich dafür verantwortlich, die Benutzererfahrung auf der Errungenschaftenseite des Kunden zu verbessern. Es könnte Folgendes handhaben:
    - AJAX-Anfragen zum Beanspruchen von Gutscheinen (z. B. wenn ein Kunde auf eine Schaltfläche „Gutschein beanspruchen“ klickt).
    - Dynamische Aktualisierungen der Seite nach dem Beanspruchen eines Gutscheins (z. B. Anzeige des Gutscheincodes, Markierung der Errungenschaft als beansprucht).
    - Clientseitige Validierung oder interaktive Elemente im Zusammenhang mit den Gamification-Funktionen.
    - Möglicherweise interagiert es mit dem `voucher.php` Front-Controller.

### 4.5 CSS-Stylesheets (`views/css/`)

- `customersexpertise/css/customersexpertise.css`

  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Details:** Dies ist das Haupt-Stylesheet für die Front-Office-Komponenten des Moduls. Es definiert das visuelle Erscheinungsbild der Errungenschaftsliste, einzelner Errungenschaftskarten, der Gutscheinanzeige und aller anderen UI-Elemente, die dem Kunden präsentiert werden.
  - **Wichtige CSS-Klassenselektoren:** Entwickler können Klassen wie `.customersexpertise-achievements`, `.achievement-item`, `.achievement-badge`, `.voucher-code` usw. erwarten, die in der `custom.css` oder `theme.css` eines benutzerdefinierten Themes überschrieben werden können, um dem Branding des Shops zu entsprechen.
- `customersexpertise/lib/voucherengine/ps16.css`

  - **Geltungsbereich:** Front-Office-Kunden-Styling, speziell für PrestaShop 1.6-Kompatibilität.
  - **Details:** Dieses Stylesheet enthält wahrscheinlich spezifische Überschreibungen oder zusätzliche Stile, um sicherzustellen, dass die Front-Office-Anzeige des Moduls korrekt und visuell konsistent mit PrestaShop 1.6-Themes ist. Es könnte Layoutunterschiede oder spezifische Elementstile ansprechen, die sich zwischen PrestaShop-Versionen geändert haben. Für neuere PrestaShop-Versionen (1.7, 8.x, 9.x) wird diese Datei möglicherweise bedingt geladen oder ihre Stile sind weniger relevant, wobei sie sich mehr auf `customersexpertise.css` verlassen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Front-Office-Templates (`views/templates/front/`)**:

  - `customersexpertise/views/templates/front/achievements.tpl`
    - **Zweck:** Dies ist das Haupt-Template zur Anzeige der Errungenschaftenseite des Kunden. Es iteriert durch die vom `achievements.php`-Controller übergebenen Errungenschaftsdaten und zeigt verdiente Abzeichen, Kriterien für nicht verdiente Abzeichen und Optionen zum Beanspruchen von Gutscheinen an.
  - `customersexpertise/views/templates/front/affiliation-link.tpl`
    - **Zweck:** Wenn der `affiliationlink.php`-Controller aktiv ist, würde dieses Template die Oberfläche rendern, auf der Kunden ihre Affiliationslinks anzeigen oder generieren können.
  - `customersexpertise/views/templates/front/voucher.tpl`
    - **Zweck:** Dieses Template könnte verwendet werden, um einen einzelnen Gutscheincode oder eine Bestätigungsnachricht anzuzeigen, nachdem ein Gutschein beansprucht wurde, möglicherweise als Teil einer AJAX-Antwort oder einer dedizierten Seite.
- **Hook-Templates (`views/templates/hook/`)**:

  - `customersexpertise/views/templates/hook/customer-account.tpl`
    - **Hook:** `displayCustomerAccount` (oder ähnlich, je nach PrestaShop-Version).
    - **Zweck:** Dieses Template rendert den Link oder Block, der im „Mein Konto“-Dashboard des Kunden erscheint und ihn zur Seite „Meine Errungenschaften“ leitet. Es ist entscheidend für die Auffindbarkeit der Modulfunktionen durch den Kunden.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Die Modulbeschreibung und das Dateiverzeichnis listen keine expliziten benutzerdefinierten SQL-Dateien für die Tabellenerstellung auf. Dies deutet darauf hin, dass das Modul seine Daten auf eine der folgenden Weisen speichern könnte:

  - **`ps_configuration`**: Errungenschaftsdefinitionen (Kriterien, Belohnungen) könnten als serialisierte Arrays oder JSON-Strings in der Tabelle `ps_configuration` gespeichert werden, unter Verwendung eindeutiger Konfigurationsschlüssel (z. B. `CUSTOMERS_EXPERTISE_ACHIEVEMENTS`).
  - **Bestehende PrestaShop-Tabellen**: Der Kunden-Errungenschaftsstatus (welche Errungenschaften sie verdient haben, welche Gutscheine sie beansprucht haben) könnte in einem benutzerdefinierten Feld gespeichert werden, das den Tabellen `ps_customer` oder `ps_customer_group` hinzugefügt wurde, oder in einer benutzerdefinierten Tabelle, die dynamisch durch die `install()`-Methode des Moduls ohne eine dedizierte `.sql`-Datei erstellt wurde.
  - **`ps_cart_rule`**: Das Modul interagiert direkt mit dem PrestaShop `CartRule` (Rabattgutschein)-System, um Belohnungen zu generieren.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich aller Front-Office-Seiten. | Zum globalen Einbinden von CSS- und JavaScript-Assets oder zum Hinzufügen von Meta-Tags. |
| `displayLeftColumn` / `displayRightColumn` | In der linken/rechten Spalte der Front-Office-Seiten. | Zum Anzeigen eines kleinen Werbeblocks oder eines Links zur Errungenschaftenseite. |
| `displayProductButtons` / `displayProductExtraContent` (oder ähnliche Produktseiten-Hooks) | Auf der Produktseite. | Potenziell zur Verfolgung von Produktansichten/Käufen für Errungenschaftskriterien oder um auf Gamification hinzuweisen. |
| `displayFooter` | Im Footer aller Front-Office-Seiten. | Zum Anzeigen eines Links zur Errungenschaftenseite oder einer allgemeinen Gamification-Promotion. |
| `displayCustomerAccount` | Im „Mein Konto“-Dashboard des Kunden. | **KRITISCH:** Zum Hinzufügen des Links „Meine Errungenschaften“ für Kunden. |
| `actionValidateOrder` | Nachdem die Bestellung eines Kunden erfolgreich validiert wurde. | **KRITISCH:** Um zu überprüfen, ob die Bestellung Errungenschaftskriterien erfüllt (z. B. erste Bestellung, Gesamtausgaben, Produktkauf) und Errungenschaften zu vergeben. |
| `actionObjectProductAddAfter` / `actionObjectProductUpdateAfter` | Nachdem ein Produkt hinzugefügt oder aktualisiert wurde. | Weniger wahrscheinlich, könnte aber verwendet werden, um Errungenschaftskriterien zu aktualisieren, wenn sie sich auf Produktattribute beziehen. |
| `actionObjectCustomerAddAfter` | Nachdem sich ein neuer Kunde registriert hat. | Zur Initialisierung der Errungenschaftsverfolgung für neue Kunden. |
| `actionObjectReviewAddAfter` (oder ähnlich für Bewertungsmodule) | Nachdem ein Kunde eine Produktbewertung abgegeben hat. | **KRITISCH:** Um zu überprüfen, ob die Bewertung Errungenschaftskriterien erfüllt (z. B. Anzahl der Bewertungen). |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und professionellen Support für das Modul Kunden-Expertise besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, sicherzustellen, dass das Modul optimal mit Ihrem PrestaShop-Shop funktioniert.

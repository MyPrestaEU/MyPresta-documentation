---
title: "Gutschein für Freunde - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Gutschein für Freunde“ von MyPresta.eu."
sidebar:
  label: "Gutschein für Freunde - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Voucher for friend auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/voucher-for-friend.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/voucher-for-friend/)
>
> ---


# Gutschein für Freunde

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für einen PrestaShop-Shop erforderlich und ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren > Gutschein für Freunde)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Gutschein für Freunde“. Hier definieren Sie, wie sich die Gutschein-Teilen-Funktion verhält und wo sie in Ihrem Shop erscheint.

#### **Einstellungen & Optionen**

- **Link „Gutschein für Freunde“ im Mein-Konto-Block anzeigen (fvc\_b\_position)**

  - **Was diese Einstellung bewirkt:** Steuert, ob ein Link zur Seite „Gutschein für Freunde“ im „Mein Konto“-Block des Kunden erscheint, der typischerweise im Header oder in einer Spalte nach dem Login eines Kunden zu finden ist.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Ein Link, normalerweise mit der Bezeichnung „Meine Gutscheine“ oder „Gutschein für einen Freund“, wird im Kundenkontoblock sichtbar sein und schnellen Zugriff auf die Teilen-Funktion bieten.
    - *Wenn deaktiviert (Nein):* Der Link wird nicht im Kundenkontoblock erscheinen. Kunden müssten zu ihrer vollständigen „Mein Konto“-Seite navigieren, um den Link zu finden, oder eine andere Platzierungsoption verwenden.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Wenn Sie es eingeloggten Kunden super einfach machen möchten, die Funktion zu finden, aktivieren Sie diese. Es ist eine prominente Platzierung für aktive Benutzer.
- **Link „Gutschein für Freunde“ auf der Mein-Konto-Seite anzeigen (fvc\_b\_position2)**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob ein Link zur Seite „Gutschein für Freunde“ auf der Hauptseite „Mein Konto“ angezeigt wird, die alle kundenspezifischen Optionen auflistet.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Ein dedizierter Link wird auf der Seite „Mein Konto“ erscheinen, normalerweise als Symbol oder Textlink neben anderen Optionen wie „Bestellhistorie“ oder „Meine Adressen“.
    - *Wenn deaktiviert (Nein):* Der Link wird nicht auf der Seite „Mein Konto“ vorhanden sein.
  - **Empfohlener Wert:** JA
  - **Händlerszenario / Beispiel:** Dies ist ein Standard- und erwarteter Ort für Kunden, um eine solche Funktion zu finden. Die Aktivierung gewährleistet die Auffindbarkeit für alle eingeloggten Benutzer.
- **Link „Gutschein für Freunde“ in linker/rechter Spalte anzeigen (fvc\_b\_position3)**

  - **Was diese Einstellung bewirkt:** Steuert, ob ein Werbeblock oder Link für „Gutschein für Freunde“ in der linken oder rechten Spalte Ihres Shops erscheint. Dies kann sowohl für eingeloggte als auch für nicht eingeloggte Besucher sichtbar sein.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Ein Block oder Link wird in der angegebenen Spalte gerendert und ermutigt Besucher, die Gutschein-Teilen-Funktion zu nutzen oder mehr darüber zu erfahren.
    - *Wenn deaktiviert (Nein):* Es wird kein solcher Block in den Spalten erscheinen.
  - **Empfohlener Wert:** JA (wenn Sie die Funktion breit bewerben möchten)
  - **Händlerszenario / Beispiel:** Wenn Sie das Empfehlungsprogramm aktiv allen Besuchern, einschließlich der noch nicht eingeloggten, bewerben möchten, erhöht die Aktivierung die Sichtbarkeit. Sie könnten es in der rechten Spalte auf Produktseiten platzieren, um das Teilen zu fördern.
- **Anzahl der zu generierenden Gutscheine (FV\_NBC)**

  - **Was diese Einstellung bewirkt:** Definiert, wie viele einzigartige Gutscheincodes ein einzelner Kunde generieren und an Freunde senden kann.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Auf 1 gesetzt:* Jeder Kunde kann nur einen Gutschein an einen Freund senden.
    - *Auf 5 gesetzt:* Jeder Kunde kann bis zu fünf Gutscheine an fünf verschiedene Freunde senden.
    - *Auf 0 (oder eine sehr hohe Zahl) gesetzt:* Ermöglicht unbegrenzte Gutscheingenerierungen pro Kunde.
  - **Empfohlener Wert:** 3-5 (um das Teilen zu fördern, ohne das System zu überlasten oder zu viele Rabatte zu erstellen)
  - **Händlerszenario / Beispiel:** Wenn Sie die Anzahl der Empfehlungen, die ein einzelner Kunde machen kann, begrenzen möchten, um Missbrauch zu verhindern oder Ihr Rabattbudget zu verwalten, legen Sie eine bestimmte Zahl wie 3 fest. Wenn Sie maximale virale Verbreitung wünschen, legen Sie eine höhere Zahl oder 0 für unbegrenzt fest.
- **Nicht eingeloggten Benutzern das Senden von Gutscheinen erlauben (FV\_UNLOGGED)**

  - **Was diese Einstellung bewirkt:** Bestimmt, ob Besucher, die nicht in einem Kundenkonto angemeldet sind, trotzdem auf das Formular „Gutschein für Freunde“ zugreifen und einen Gutschein senden können.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Nicht eingeloggte Benutzer sehen die Links „Gutschein für Freunde“ (falls in Spalten/Footer aktiviert) und können das Formular ausfüllen. Sie werden wahrscheinlich aufgefordert, ihre eigene E-Mail-Adresse als Empfehlungsgeber einzugeben.
    - *Wenn deaktiviert (Nein):* Nur eingeloggte Kunden können die Gutschein-Teilen-Funktion nutzen. Nicht eingeloggte Benutzer, die auf den Link klicken, könnten zur Login-/Registrierungsseite weitergeleitet werden.
  - **Empfohlener Wert:** NEIN (um sicherzustellen, dass nur tatsächliche Kunden Empfehlungen abgeben und Spam/Missbrauch zu verhindern)
  - **Händlerszenario / Beispiel:** Wenn Sie streng kontrollieren möchten, wer Empfehlungen abgeben kann, und sicherstellen möchten, dass nur Ihr bestehender Kundenstamm teilnimmt, deaktivieren Sie dies. Wenn Sie jedem erlauben möchten, Empfehlungen abzugeben, auch wenn er noch nicht gekauft hat, aktivieren Sie es (aber achten Sie auf potenziellen Spam).
- **Shop-E-Mail (PS\_SHOP\_EMAIL)**

  - **Was diese Einstellung bewirkt:** Dieses Feld zeigt typischerweise die Standard-Kontakt-E-Mail-Adresse Ihres Shops an, die als „Absender“-E-Mail für die Gutscheinbenachrichtigung an Freunde verwendet wird. Es wird normalerweise aus Ihren PrestaShop-Allgemeineinstellungen übernommen.
  - **Auswirkung einer Änderung dieser Einstellung:** Eine Änderung hier könnte die systemweite Shop-E-Mail für die spezifischen E-Mails dieses Moduls überschreiben.
  - **Empfohlener Wert:** Stellen Sie sicher, dass es sich um eine gültige, professionelle E-Mail-Adresse handelt, die mit Ihrem Shop verbunden ist (z. B. `info@ihrshop.com`).
  - **Händlerszenario / Beispiel:** Der Freund, der den Gutschein erhält, sieht diese E-Mail als Absender. Es sollte eine Adresse sein, die er erkennen und der er vertrauen kann.
- **Shop-Name (PS\_SHOP\_NAME)**

  - **Was diese Einstellung bewirkt:** Dieses Feld zeigt typischerweise den offiziellen Namen Ihres Shops an, der im E-Mail-Betreff und -Text verwendet wird, wenn der Gutschein an einen Freund gesendet wird. Es wird normalerweise aus Ihren PrestaShop-Allgemeineinstellungen übernommen.
  - **Auswirkung einer Änderung dieser Einstellung:** Eine Änderung hier könnte den systemweiten Shop-Namen für die spezifischen E-Mails dieses Moduls überschreiben.
  - **Empfohlener Wert:** Ihr offizieller Shop-Name (z. B. „Mein toller Shop“).
  - **Händlerszenario / Beispiel:** Der Freund, der den Gutschein erhält, sieht diesen Namen. Er sollte klar und konsistent mit Ihrer Marke sein.

#### 2.1.1 Konfigurations-Kurzreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Link „Gutschein für Freunde“ im Mein-Konto-Block anzeigen (fvc\_b\_position) | JA | Zeigt Link im Kundenkontoblock (Header/Spalte) für schnellen Zugriff. |
| Modulkonfiguration | Link „Gutschein für Freunde“ auf der Mein-Konto-Seite anzeigen (fvc\_b\_position2) | JA | Zeigt Link auf der Hauptseite „Mein Konto“. |
| Modulkonfiguration | Link „Gutschein für Freunde“ in linker/rechter Spalte anzeigen (fvc\_b\_position3) | JA | Zeigt einen Werbeblock/Link in den Seitenleisten für alle Besucher. |
| Modulkonfiguration | Anzahl der zu generierenden Gutscheine (FV\_NBC) | 3-5 | Begrenzt, wie viele Gutscheine ein einzelner Kunde senden kann. |
| Modulkonfiguration | Nicht eingeloggten Benutzern das Senden von Gutscheinen erlauben (FV\_UNLOGGED) | NEIN | Beschränkt das Senden von Gutscheinen nur auf eingeloggte Kunden. |
| Modulkonfiguration | Shop-E-Mail (PS\_SHOP\_EMAIL) | E-Mail Ihres Shops | Absender-E-Mail für Gutscheinbenachrichtigungen. |
| Modulkonfiguration | Shop-Name (PS\_SHOP\_NAME) | Name Ihres Shops | Shop-Name, der in Gutscheinbenachrichtigungs-E-Mails verwendet wird. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden können den Link „Gutschein für Freunde“ nicht finden.**
A1: Gehen Sie zu **Module > Modul-Manager > Konfigurieren** für „Gutschein für Freunde“. Stellen Sie sicher, dass `fvc_b_position`, `fvc_b_position2` und `fvc_b_position3` für die gewünschten Platzierungen (Mein-Konto-Block, Mein-Konto-Seite, Linke/Rechte Spalte) auf „Ja“ gesetzt sind. Überprüfen Sie auch die Hook-Zuweisungen Ihres Themes unter **Design > Positionen**, um sicherzustellen, dass das Modul wie erwartet an `displayMyAccountBlock`, `displayCustomerAccount`, `displayLeftColumn` oder `displayRightColumn` gehookt ist.

**F2: Freunde erhalten die Gutschein-E-Mails nicht.**
A2:
1. **Spam-Ordner überprüfen:** Weisen Sie Ihre Kunden an, ihre Freunde zu bitten, ihre Spam- oder Junk-Mail-Ordner zu überprüfen.
2. **Shop-E-Mail-Konfiguration:** Überprüfen Sie, ob die Einstellung `PS_SHOP_EMAIL` in der Modulkonfiguration eine gültige und aktive E-Mail-Adresse ist.
3. **PrestaShop-E-Mail-Einstellungen:** Gehen Sie im PrestaShop Back Office zu **Erweiterte Einstellungen > E-Mail**. Senden Sie eine Test-E-Mail, um sicherzustellen, dass das E-Mail-System Ihres Shops ordnungsgemäß funktioniert. Wenn nicht, haben Sie möglicherweise ein Problem mit Ihrer SMTP-Serverkonfiguration.
4. **Server-Logs:** Ihr Webmaster kann die Server-Mail-Logs auf Fehler im Zusammenhang mit ausgehenden E-Mails überprüfen.

**F3: Der Gutscheincode funktioniert für den Freund nicht.**
A3:
1. **Ablaufdatum/Bedingungen überprüfen:** Stellen Sie sicher, dass der Gutschein nicht abgelaufen ist und dass der Warenkorb des Freundes alle Mindestbestellwerte oder Produktbeschränkungen erfüllt, die für den generierten Gutschein festgelegt wurden (diese werden normalerweise im nativen PrestaShop-Bereich „Warenkorb-Regeln“ definiert, den dieses Modul nutzt).
2. **Korrekte Code-Eingabe:** Bestätigen Sie, dass der Freund den Code genau so eingibt, wie er erscheint (Groß-/Kleinschreibung beachten, keine zusätzlichen Leerzeichen).
3. **Einmalige Verwendung:** Die meisten Empfehlungsgutscheine sind einmalig verwendbar. Wenn der Freund versucht hat, ihn zuvor zu verwenden, ist er möglicherweise nicht mehr gültig.

**F4: Das Modul sieht auf meinem benutzerdefinierten Theme nicht richtig aus.**
A4: Benutzerdefinierte Themes haben oft einzigartige Stile, die manchmal mit Moduldesigns in Konflikt geraten können.
1. **Cache leeren:** Versuchen Sie zunächst, Ihren PrestaShop-Cache unter **Erweiterte Einstellungen > Leistung** zu leeren.
2. **Theme-Overrides:** Ihr Webmaster muss möglicherweise CSS-Overrides in der Stylesheet-Datei Ihres Themes erstellen, um das Erscheinungsbild des Moduls anzupassen. Das Modul verwendet `views/css/ps16.css` für sein Styling, was ein Ausgangspunkt für Anpassungen sein kann.
3. **Mobile Anzeige:** Stellen Sie sicher, dass Ihr Theme vollständig responsiv ist. Wenn Probleme auf Mobilgeräten weiterhin bestehen, handelt es sich wahrscheinlich um einen CSS-Konflikt, der einen Entwicklereingriff erfordert.

**F5: Kann ich den Rabattbetrag oder die Art des Gutscheins ändern?**
A5: Das Modul selbst generiert eine Standard-PrestaShop-Warenkorb-Regel. Sie würden die Besonderheiten des generierten Gutscheins (z. B. prozentualer Rabatt, fester Betrag, Mindestbestellwert, bestimmte Produkte) typischerweise im nativen PrestaShop-Bereich **Katalog > Rabatte > Warenkorb-Regeln** konfigurieren. Das Modul erstellt den *Mechanismus* zum Teilen, aber die *Details* des Rabatts werden vom Kern-Rabatt-System von PrestaShop verwaltet.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten Einblick in die technische Struktur des Moduls „Gutschein für Freunde“, der für Entwickler, Webmaster und technische Agenturen bestimmt ist.

### 4.1 Architekturübersicht

Das Modul „Gutschein für Freunde“ folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich `ModuleFrontController` für Front-Office-Interaktionen und die Hauptmodulklasse für Konfiguration und Hook-Verwaltung nutzt. Es integriert sich in das native `CartRule`-System von PrestaShop, um Rabattgutscheine zu generieren und zu verwalten. Die Logik des Moduls ist in seiner Haupt-PHP-Datei und dedizierten Front-Controllern enthalten, wobei Smarty-Templates die Präsentation übernehmen.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

Diese Controller verwalten die kundenorientierte Logik zum Generieren und Verwalten von Gutscheinen.

- **`controllers/front/index.php`**

  - **Klassenname:** `FriendvoucherIndexModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller ist wahrscheinlich für die Anzeige des anfänglichen Formulars „Gutschein für Freunde“ verantwortlich, in das ein Kunde die Details seines Freundes eingibt. Er verarbeitet die Übermittlung dieses Formulars, validiert die Eingabe, generiert die `CartRule` (Gutschein) und sendet die E-Mail-Benachrichtigung an den Freund. Er verwaltet auch die Logik zur Begrenzung der Anzahl der Gutscheine, die ein Kunde senden kann.
  - **Routen:** Reagiert auf eine URL wie `ihrshop.com/module/friendvoucher/index`.
- **`controllers/front/myvoucher.php`**

  - **Klassenname:** `FriendvoucherMyvoucherModuleFrontController` (erweitert `ModuleFrontController`)
  - **Verantwortlichkeit:** Dieser Controller ist für die Anzeige der persönlichen Seite „Meine Gutscheine“ des Kunden verantwortlich, die typischerweise über den Bereich „Mein Konto“ aufgerufen wird. Er listet die Gutscheine auf, die der Kunde bereits gesendet hat, und bietet möglicherweise Optionen zur Anzeige ihres Status oder zum Senden neuer Gutscheine.
  - **Routen:** Reagiert auf eine URL wie `ihrshop.com/module/friendvoucher/myvoucher`.

#### Back-Office-Admin-Controller

Dieses Modul scheint keine dedizierten benutzerdefinierten Admin-Controller zu haben. Die gesamte Back-Office-Konfiguration wird über die Methode `getContent()` der Hauptmodulklasse abgewickelt.

### 4.3 Kernklassen & Modelle (`classes/`)

Basierend auf dem bereitgestellten Inventar definiert dieses Modul keine benutzerdefinierten Klassen oder `ObjectModel`s in einem `classes/`-Verzeichnis. Es verwendet wahrscheinlich die Kernklasse `CartRule` von PrestaShop für die Gutscheinverwaltung und `Customer` für Benutzerdaten.

### 4.4 JavaScript-Assets (`views/js/`)

- **`lib/voucherengine/script.js`**
  - **Geltungsbereich:** Front-Office.
  - **Details:** Dieses Skript verarbeitet wahrscheinlich clientseitige Interaktionen auf dem Formular „Gutschein für Freunde“. Dies könnte Folgendes umfassen:
    - Formularvalidierung (z. B. Überprüfung auf gültige E-Mail-Formate, Pflichtfelder).
    - AJAX-Übermittlungen der Gutscheinanfrage an den Front-Controller `index.php`.
    - Anzeige von Erfolgs- oder Fehlermeldungen an den Benutzer ohne vollständiges Neuladen der Seite.
    - Potenzielle dynamische Aktualisierungen des Formulars basierend auf Benutzereingaben.
    - Alle interaktiven Elemente im Zusammenhang mit dem Gutschein-Generierungsprozess.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`lib/voucherengine/ps16.css`**
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Details:** Dieses Stylesheet bietet das visuelle Styling für die Formulare, Links und Anzeigeblöcke von „Gutschein für Freunde“ im Front Office. Es enthält wahrscheinlich Stile für:
    - Die Elemente des Gutschein-Teilen-Formulars (Eingabefelder, Schaltflächen).
    - Die Liste „Meine Gutscheine“ auf der Kundenkontoseite.
    - Die Werbeblöcke in den linken/rechten Spalten.
    - Grundlegendes Layout und Typografie zur Gewährleistung der Lesbarkeit.
  - **Wichtige CSS-Klassenselektoren, die Entwickler überschreiben können:** Entwickler sollten das gerenderte HTML inspizieren, um spezifische Klassennamen (z. B. `.friendvoucher-form`, `.voucher-list`, `.friendvoucher-block`) zu identifizieren, die für die Theme-Integration und Anpassung verwendet werden können.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

Das Modul listet keine Templates explizit in einem `hook/`-Unterverzeichnis auf, aber die unten aufgeführten Templates werden typischerweise über Hooks gerendert.

- **`views/templates/front/footer.tpl`**

  - **Hook:** `displayFooter`
  - **Ausgabe:** Ein Link oder Block bezüglich „Gutschein für Freunde“ im Footer des Shops.
- **`views/templates/front/leftcolumn.tpl`**

  - **Hook:** `displayLeftColumn`
  - **Ausgabe:** Ein Werbeblock oder Link für „Gutschein für Freunde“ in der linken Seitenleiste des Shops.
- **`views/templates/front/rightcolumn.tpl`**

  - **Hook:** `displayRightColumn`
  - **Ausgabe:** Ein Werbeblock oder Link für „Gutschein für Freunde“ in der rechten Seitenleiste des Shops.

#### Admin-Templates (`views/templates/admin/`)

Dieses Modul scheint keine benutzerdefinierten Admin-Templates zu haben. Die Konfiguration wird wahrscheinlich direkt von der Methode `getContent()` unter Verwendung der PrestaShop-Hilfsformulare gerendert.

#### Front-Office-Templates (`views/templates/front/`)

Diese Templates werden von den Front-Controllern des Moduls gerendert.

- **`views/templates/front/my-account.tpl`**

  - **Hook:** `displayCustomerAccount` (oder `displayMyAccountBlock`)
  - **Ausgabe:** Ein Link oder Symbol auf der Hauptseite „Mein Konto“ des Kunden, der ihn zum Controller `myvoucher.php` leitet.
- **`views/templates/front/my-voucher.tpl`**

  - **Controller:** `FriendvoucherMyvoucherModuleFrontController`
  - **Ausgabe:** Die spezielle Seite, die eine Liste der vom Kunden gesendeten Gutscheine, deren Status und möglicherweise ein Formular zum Senden neuer Gutscheine anzeigt.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Dieses Modul scheint keine benutzerdefinierten SQL-Tabellen zu erstellen. Es speichert seine Konfiguration wahrscheinlich in `ps_configuration` und nutzt die Kern-PrestaShop-Tabellen `ps_cart_rule` und `ps_cart_rule_lang` für die generierten Gutscheine.

#### Registrierte Hooks-Tabelle

Das Modul registriert sich bei verschiedenen Hooks, um seine Inhalte und Funktionen anzuzeigen.

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displaymyAccountBlock` | Rendert im Kundenkontoblock (Header/Spalte) nach dem Login. | Zeigt einen Schnelllink zur Gutscheinseite für eingeloggte Benutzer an. |
| `displayrightColumn` | Rendert Inhalte in der rechten Seitenleiste. | Zeigt einen Werbeblock/Link für die Gutschein-Funktion an. |
| `displayLeftColumn` | Rendert Inhalte in der linken Seitenleiste. | Zeigt einen Werbeblock/Link für die Gutschein-Funktion an. |
| `displayFooter` | Rendert Inhalte im Footer des Shops. | Zeigt einen Link zur Gutscheinseite im Footer an. |
| `displaycustomerAccount` | Rendert Inhalte auf der Hauptseite „Mein Konto“ des Kunden. | Zeigt einen dedizierten Link/Symbol für die Gutschein-Funktion auf der Kontoseite an. |
| `actionValidateOrder` | Wird ausgeführt, nachdem eine Bestellung erfolgreich validiert wurde. | (Potenziell) Könnte verwendet werden, um Aktionen im Zusammenhang mit Empfehlungsgeber-Belohnungen oder der Verfolgung erfolgreicher Empfehlungen auszulösen, obwohl dies durch das Dateiinventar nicht explizit bestätigt wird. |

## 5. Offizieller Support & Updates

Für offiziellen Support, Modul-Updates und weitere Unterstützung wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Sie können auf Ihre gekauften Module zugreifen, die neuesten Versionen herunterladen und Support-Tickets direkt von Ihrem Konto aus einreichen.

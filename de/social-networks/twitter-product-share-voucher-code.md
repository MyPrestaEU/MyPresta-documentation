---
title: "Twitter Produkt teilen + Gutscheincode - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Twitter Produkt teilen + Gutscheincode“ von MyPresta.eu."
sidebar:
  label: "Twitter Produkt teilen + Gutscheincode - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Twitter product share + voucher code auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/twitter-product-share-voucher-code.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/twitter-product-share-voucher-code/)
>
> ---


# Twitter Produkt teilen + Gutscheincode

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop erforderlich und in den meisten Hosting-Umgebungen standardmäßig aktiviert.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Twitter Produkt teilen + Gutscheincode“, der nach der Installation durch Klicken auf den Button „Konfigurieren“ zugänglich ist. Hier definieren Sie, wie sich der Teilen-Button verhält und wie die Gutscheincodes generiert werden.

#### **Allgemeine Einstellungen**

- **Modul aktivieren:**

  - **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um das gesamte Modul ein- oder auszuschalten.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn aktiviert (JA):* Der Twitter-Teilen-Button wird auf Ihren Produktseiten angezeigt (basierend auf Ihrer Hook-Auswahl), und das Gutscheincode-Generierungssystem wird aktiv sein.
    - *Wenn deaktiviert (NEIN):* Der Twitter-Teilen-Button wird nicht angezeigt, und es werden keine Gutscheincodes für Shares generiert.
  - **Empfohlener Wert:** JA (um die Funktionalität des Moduls zu aktivieren).
  - **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal einrichten oder Wartungsarbeiten durchführen, können Sie es vorübergehend deaktivieren. Andernfalls lassen Sie es aktiviert, um von der sozialen Freigabe zu profitieren.
- **Hook zum Anzeigen des Buttons:**

  - **Was diese Einstellung bewirkt:** Bestimmt, wo der Twitter-Teilen-Button visuell auf Ihren Produktseiten platziert wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Optionen (Beispiele):* `displayProductButtons`, `displayRightColumnProduct`, `displayFooterProduct`, `displayProductExtraContent`.
    - *Wenn auf `displayProductButtons` (üblich) eingestellt:* Der Button erscheint wahrscheinlich in der Nähe des „In den Warenkorb“-Buttons oder des Produktmengenwählers.
    - *Wenn auf `displayRightColumnProduct` eingestellt:* Der Button erscheint in der rechten Spalte Ihrer Produktseite (falls Ihr Theme eine solche hat).
    - *Wenn auf `displayFooterProduct` eingestellt:* Der Button erscheint im Footer-Bereich der Produktseite.
  - **Empfohlener Wert:** `displayProductButtons` oder `displayProductExtraContent` für maximale Sichtbarkeit und Engagement, da diese typischerweise nahe an den Hauptproduktinformationen liegen.
  - **Händlerszenario / Beispiel:** Sie könnten verschiedene Hooks testen, um zu sehen, welche Platzierung auf Ihrem spezifischen Theme die meisten Shares generiert. Eine prominente Position ist in der Regel am besten.
- **Anzahl der Shares, die für einen Gutschein erforderlich sind:**

  - **Was diese Einstellung bewirkt:** Definiert, wie viele einzigartige Produkt-Shares ein Kunde durchführen muss, bevor er einen Rabattgutschein erhält.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 1 eingestellt:* Ein Kunde erhält sofort nach seinem ersten Share einen Gutschein.
    - *Wenn auf 3 eingestellt:* Ein Kunde muss drei verschiedene Produkte teilen (oder dasselbe Produkt dreimal, je nach interner Logik), bevor ein Gutschein ausgestellt wird.
  - **Empfohlener Wert:** 1 (um sofortige Aktionen und Belohnungen zu fördern) oder 2 (um etwas mehr Engagement zu fördern, ohne zu anspruchsvoll zu sein).
  - **Händlerszenario / Beispiel:** Wenn Sie es Kunden leicht machen möchten, einen Rabatt zu erhalten, stellen Sie es auf 1 ein. Wenn Sie eine umfassendere Freigabe fördern möchten, stellen Sie es höher ein, aber beachten Sie, dass eine höhere Zahl die Teilnahme verringern könnte.

#### **Gutscheincode-Einstellungen**

- **Gutscheincode-Präfix:**

  - **Was diese Einstellung bewirkt:** Eine benutzerdefinierte Zeichenfolge, die am Anfang jedes generierten Gutscheincodes erscheint.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf `TWITTER-` eingestellt:* Ein Gutscheincode könnte wie `TWITTER-ABCDE123` aussehen.
    - *Wenn leer gelassen:* Der Gutscheincode besteht aus rein zufälligen Zeichen.
  - **Empfohlener Wert:** `TWITTER-` oder `SHARE-`, um die Herkunft des Gutscheins leicht zu identifizieren.
  - **Händlerszenario / Beispiel:** Die Verwendung eines Präfixes hilft Ihnen, in Ihren PrestaShop-Verkaufsberichten zu verfolgen, welche Marketingkampagnen bestimmte Gutscheine generieren.
- **Gutscheincode-Wert (Prozentsatz):**

  - **Was diese Einstellung bewirkt:** Der prozentuale Rabatt, der durch den generierten Gutscheincode angewendet wird.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 10 eingestellt:* Der Gutschein gewährt einen Rabatt von 10% auf die Bestellung des Kunden.
    - *Wenn auf 5 eingestellt:* Der Gutschein gewährt einen Rabatt von 5%.
  - **Empfohlener Wert:** 5-15% (abhängig von Ihren Gewinnmargen und dem gewünschten Anreizniveau).
  - **Händlerszenario / Beispiel:** Ein Rabatt von 10% ist oft ein gutes Gleichgewicht zwischen der Anziehung von Kunden und der Aufrechterhaltung der Rentabilität.
- **Gutscheincode-Gültigkeit (Tage):**

  - **Was diese Einstellung bewirkt:** Wie viele Tage der generierte Gutscheincode ab dem Zeitpunkt seiner Ausstellung gültig ist.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 7 eingestellt:* Der Gutschein läuft 7 Tage nach Erhalt durch den Kunden ab.
    - *Wenn auf 30 eingestellt:* Der Gutschein ist einen Monat lang gültig.
  - **Empfohlener Wert:** 7-14 Tage (um ein Gefühl der Dringlichkeit zu erzeugen, ohne zu restriktiv zu sein).
  - **Händlerszenario / Beispiel:** Eine kürzere Gültigkeitsdauer ermutigt Kunden, früher als später einen Kauf zu tätigen, und verhindert, dass sie den Gutschein vergessen.
- **Mindestbetrag für die Gültigkeit des Gutscheins:**

  - **Was diese Einstellung bewirkt:** Der minimale Gesamtbestellwert (vor Versand), der erforderlich ist, damit der Kunde den Rabattgutschein verwenden kann.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf 50 eingestellt:* Der Gutschein kann nur verwendet werden, wenn der Warenkorb des Kunden 50 € oder mehr beträgt.
    - *Wenn auf 0 (oder leer) eingestellt:* Der Gutschein kann für jeden Bestellbetrag verwendet werden.
  - **Empfohlener Wert:** Ein angemessener Betrag, der einen etwas größeren Einkauf fördert, oder 0, wenn Sie ihn für jede Bestellung zulassen möchten.
  - **Händlerszenario / Beispiel:** Wenn Ihr durchschnittlicher Bestellwert 40 € beträgt, könnte eine Mindestgrenze von 50 € Kunden dazu ermutigen, einen weiteren Artikel in ihren Warenkorb zu legen, um den Schwellenwert zu erreichen und den Rabatt zu nutzen.
- **Gutscheincode-Beschreibung:**

  - **Was diese Einstellung bewirkt:** Eine kurze Textbeschreibung, die dem Gutscheincode in Ihrem PrestaShop Back Office zugeordnet wird (und möglicherweise für den Kunden in seinem Konto sichtbar ist, wenn er seine Gutscheine überprüft).
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Twitter Share Discount“ eingestellt:* Dieser Text erscheint in den Gutscheindetails.
  - **Empfohlener Wert:** „Rabatt für Twitter Share“ oder „Vielen Dank für das Teilen auf Twitter!“
  - **Händlerszenario / Beispiel:** Dies hilft Ihnen und Ihren Kunden, die Herkunft des Gutscheins zu verstehen.
- **Gutscheincode-Name:**

  - **Was diese Einstellung bewirkt:** Der interne Name für die Gutscheinregel in PrestaShop. Dies dient hauptsächlich Ihrer internen Organisation.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Twitter Share Coupon“ eingestellt:* Dieser Name erscheint in Ihrem PrestaShop-Bereich „Warenkorbregeln“.
  - **Empfohlener Wert:** „Twitter Share Coupon“ oder „Social Share Discount“.
  - **Händlerszenario / Beispiel:** Ein klarer Name erleichtert das Auffinden und Verwalten dieser automatisch generierten Gutscheine in Ihrem PrestaShop-Adminbereich.

#### **Twitter Share Text Einstellungen**

- **Standard-Share-Text:**
  - **Was diese Einstellung bewirkt:** Der Standardtext, der im Twitter-Sharing-Pop-up vorausgefüllt wird, wenn ein Kunde auf den Teilen-Button klickt. Dieser Text wird mit dem Produktnamen und dem Link kombiniert.
  - **Auswirkung der Änderung dieser Einstellung:**
    - *Wenn auf „Schau dir dieses tolle Produkt an!“ eingestellt:* Der Tweet könnte wie „Schau dir dieses tolle Produkt an! [Produktname] [Produktlink]“ aussehen.
  - **Empfohlener Wert:** Etwas Ansprechendes wie „Schau dir dieses tolle Produkt von [Ihr Shop-Name] an!“ oder „Ich habe gerade dieses großartige Produkt gefunden!“
  - **Händlerszenario / Beispiel:** Ein überzeugender Standardtext fördert mehr Klicks und Engagement von den Followern des Kunden.

#### **Speichern-Button**

- **Speichern:**
  - **Was dieser Button bewirkt:** Übernimmt alle Änderungen, die Sie auf dieser Konfigurationsseite vorgenommen haben.
  - **Auswirkung des Klickens auf diesen Button:** Ihre Einstellungen werden in der Datenbank gespeichert, und das Verhalten des Moduls wird sofort in Ihrem Front Office aktualisiert.
  - **Empfohlene Aktion:** Klicken Sie immer auf „Speichern“, nachdem Sie Änderungen vorgenommen haben.

### 2.2 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Modul aktivieren | JA | Schaltet das Modul ein/aus. |
| | Hook zum Anzeigen des Buttons | `displayProductButtons` | Steuert, wo der Teilen-Button auf den Produktseiten erscheint. |
| | Anzahl der Shares, die für einen Gutschein erforderlich sind | 1 | Wie viele Shares, bevor ein Kunde einen Gutschein erhält. |
| | Gutscheincode-Präfix | `TWITTER-` | Fügt generierten Gutscheincodes ein benutzerdefiniertes Präfix hinzu. |
| | Gutscheincode-Wert (Prozentsatz) | 10 | Der Rabattprozentsatz des Gutscheins. |
| | Gutscheincode-Gültigkeit (Tage) | 7-14 | Wie lange der Gutschein nach der Generierung gültig ist. |
| | Mindestbetrag für die Gültigkeit des Gutscheins | 0 (oder angemessener Betrag) | Mindestwarenkorbwert, der zur Verwendung des Gutscheins erforderlich ist. |
| | Gutscheincode-Beschreibung | „Rabatt für Twitter Share“ | Interne Beschreibung für den Gutschein. |
| | Gutscheincode-Name | „Twitter Share Coupon“ | Interner Name für die Gutscheinregel. |
| | Standard-Share-Text | „Schau dir dieses tolle Produkt an!“ | Vorausgefüllter Text für das Twitter-Share-Pop-up. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der Twitter-Teilen-Button wird auf meinen Produktseiten nicht angezeigt.**

- **A:** Stellen Sie zunächst sicher, dass das Modul in seiner Konfiguration **aktiviert** ist. Zweitens überprüfen Sie die Einstellung **„Hook zum Anzeigen des Buttons“**. Ihr Theme rendert den gewählten Hook möglicherweise nicht an einer sichtbaren Stelle, oder der Hook existiert möglicherweise nicht. Versuchen Sie, zu einem anderen gängigen Hook wie `displayProductButtons` oder `displayProductExtraContent` zu wechseln. Wenn er immer noch nicht erscheint, erfordert Ihr Theme möglicherweise eine benutzerdefinierte Integration für bestimmte Hooks, oder es könnte einen Konflikt geben.
- **Profi-Tipp:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung), nachdem Sie Änderungen an den Moduleinstellungen oder Theme-Dateien vorgenommen haben.

**F2: Kunden teilen, aber sie erhalten keine Gutscheincodes.**

- **A:**
  1. **Überprüfen Sie „Anzahl der Shares, die für einen Gutschein erforderlich sind“:** Ist sie auf 1 eingestellt? Wenn sie höher ist, müssen Kunden öfter teilen, bevor sie einen Gutschein erhalten.
  2. **Gutscheineinstellungen überprüfen:** Stellen Sie sicher, dass „Gutscheincode-Wert (Prozentsatz)“ auf eine Zahl größer als 0 und „Gutscheincode-Gültigkeit (Tage)“ ebenfalls eingestellt ist.
  3. **PrestaShop-Warenkorbregeln:** Überprüfen Sie Ihr PrestaShop Back Office unter **Katalog > Rabatte > Warenkorbregeln**. Sie sollten automatisch generierte Gutscheine mit dem von Ihnen angegebenen Namen sehen (z. B. „Twitter Share Coupon“). Wenn keine neuen Regeln erscheinen, könnte ein Problem mit der Gutscheingenerierungslogik vorliegen.
- **Profi-Tipp:** Testen Sie den Prozess selbst. Teilen Sie ein Produkt aus Ihrem Shop, während Sie als Kunde angemeldet sind, und prüfen Sie, ob ein Gutschein generiert wird.

**F3: Das Twitter-Share-Pop-up sieht seltsam aus oder funktioniert nicht richtig.**

- **A:** Dies liegt oft an JavaScript-Konflikten mit anderen Modulen oder Ihrem Theme.
  1. **Browserkonsole überprüfen:** Öffnen Sie die Entwicklertools Ihres Browsers (normalerweise F12) und suchen Sie im Tab „Konsole“ nach Fehlern, wenn Sie auf den Teilen-Button klicken.
  2. **Modulkonflikte:** Deaktivieren Sie vorübergehend andere Module, die JavaScript zu Produktseiten hinzufügen (insbesondere Social-Sharing- oder Pop-up-Module), um zu sehen, ob das Problem behoben wird.
- **Profi-Tipp:** Stellen Sie sicher, dass Ihre PrestaShop-Installation und Ihr Theme auf dem neuesten Stand sind. Veraltete Komponenten können manchmal unerwartete Konflikte verursachen.

**F4: Kann ich das Aussehen des Teilen-Buttons anpassen?**

- **A:** Das Modul verwendet seine eigenen CSS-Dateien (`twittercoupon/css.css` und `twittercoupon/css/css.css`). Sie können diese Stile in der benutzerdefinierten CSS-Datei Ihres Themes überschreiben. Überprüfen Sie den Button mit den Entwicklertools Ihres Browsers, um seine CSS-Klassen zu identifizieren, und fügen Sie dann Ihre benutzerdefinierten Stile in die `custom.css` oder eine entsprechende Datei Ihres Themes ein.
- **Profi-Tipp:** Vermeiden Sie es, die CSS-Dateien des Moduls direkt zu bearbeiten, da Ihre Änderungen bei Modul-Updates verloren gehen. Verwenden Sie immer die benutzerdefinierten CSS-Funktionen Ihres Themes.

**F5: Wie verhindert das Modul Missbrauch (z. B. wiederholtes Teilen, um mehrere Gutscheine zu erhalten)?**

- **A:** Das Modul verfolgt Shares pro Kunde (oft über IP-Adresse oder Kunden-ID, wenn angemeldet), um zu verhindern, dass ein einzelner Benutzer unbegrenzt Gutscheine generiert. Die Einstellung „Anzahl der Shares, die für einen Gutschein erforderlich sind“ hilft ebenfalls, dies zu verwalten. Für eine erweiterte Betrugsprävention benötigen Sie möglicherweise zusätzliche PrestaShop-Sicherheitsmodule.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen gedacht, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Twitter Produkt teilen + Gutscheincode“ (`twittercoupon`) ist ein Standard-PrestaShop-Modul, das hauptsächlich in seiner Haupt-PHP-Datei `ajax_twittercoupon.php` implementiert ist. Es nutzt das PrestaShop-Hook-System für die Front-Office-Anzeige und die `Configuration`-Klasse zur Speicherung von Einstellungen. Das Modul generiert dynamisch `CartRule`-Objekte (Gutscheine) basierend auf Benutzeraktionen. Seine Front-Office-Funktionalität basiert auf JavaScript, um mit der Twitter-API und einem AJAX-Endpunkt innerhalb des Moduls zu interagieren, um Shares zu verarbeiten und Gutscheine auszustellen.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine dedizierten Front-Office- oder Back-Office-Controller im Verzeichnis `controllers/`. Alle Front-Office-AJAX-Anfragen und die Back-Office-Konfigurationsverwaltung werden direkt in der Hauptmoduldatei `ajax_twittercoupon.php` verwaltet, insbesondere über die Methode `getContent()` für die Konfiguration und einen benutzerdefinierten AJAX-Dispatch für die Share-Verarbeitung.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder erweitert `ObjectModel` in einem dedizierten `classes/`-Verzeichnis. Die Kernlogik für die Gutscheingenerierung interagiert direkt mit den PrestaShop-Klassen `CartRule` und `Configuration`.

### 4.4 JavaScript-Assets (`views/js/`)

Das Modul enthält JavaScript-Dateien zur Handhabung von Front-Office-Interaktionen.

- `twittercoupon/lib/voucherengine/script.js`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Dies scheint das primäre Skript zu sein, das für die clientseitige Logik des Moduls verantwortlich ist. Es behandelt wahrscheinlich:
    - Binden von Klickereignissen an den Twitter-Teilen-Button.
    - Öffnen des Twitter-Sharing-Pop-ups (mithilfe der Twitter Web Intent API).
    - Erkennen erfolgreicher Shares (möglicherweise über Callbacks oder Polling).
    - Ausführen von AJAX-Aufrufen an das Backend des Moduls, um den Share zu registrieren und einen Gutschein anzufordern.
    - Anzeigen des Gutscheincodes für den Benutzer nach erfolgreicher Generierung.
    - Kann Logik enthalten, um mehrere Shares desselben Benutzers innerhalb kurzer Zeit zu verhindern oder die Anzahl der Shares zu verfolgen.
- `twittercoupon/trusted.js`
  - **Umfang:** Front-Office.
  - **Verantwortlichkeit:** Der Name „trusted.js“ deutet darauf hin, dass es sich um Sicherheit, Tracking oder die Sicherstellung der Integrität des Sharing-Prozesses handeln könnte. Es könnte potenziell Folgendes behandeln:
    - Clientseitige Validierung vor dem Initiieren eines Shares.
    - Verfolgung von Benutzerinteraktionen für Anti-Betrugs-Maßnahmen.
    - Integration mit anderen Tracking-Skripten oder Analysen.

### 4.5 CSS-Stylesheets (`views/css/`)

Das Modul stellt CSS-Dateien zur Gestaltung der Front-Office-Elemente bereit.

- `twittercoupon/css.css`
  - **Umfang:** Front-Office-Kundenstyling.
  - **Verantwortlichkeit:** Enthält die Hauptstile für den Twitter-Teilen-Button, alle zugehörigen Pop-ups oder Nachrichten, die dem Kunden angezeigt werden.
  - **Wichtige CSS-Klassenselektoren:** Entwickler sollten das gerenderte HTML überprüfen, um spezifische Klassen (z. B. `.twitter-share-button`, `.twitter-coupon-message`) zu identifizieren, die in der `custom.css` ihres Themes überschrieben werden sollen.
- `twittercoupon/css/css.css`
  - **Umfang:** Front-Office-Kundenstyling.
  - **Verantwortlichkeit:** Diese Datei scheint ein Duplikat oder ein alternativer Pfad für das Haupt-CSS zu sein. Es ist üblich, dass Module redundante Pfade haben oder einer ein Fallback ist. Entwickler sollten überprüfen, welche tatsächlich im Browser geladen wird.
  - **Wichtige CSS-Klassenselektoren:** Wie oben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Das Modul verwendet Smarty-Templates zur Darstellung seiner Front-Office-Inhalte.

- **Hook-Templates (`views/templates/hook/`)**:
  - `twittercoupon/share.tpl`
    - **Hook:** Dieses Template wird im in der Modulkonfiguration gewählten Hook gerendert (z. B. `displayProductButtons`, `displayRightColumnProduct`, `displayFooterProduct`).
    - **Zweck:** Es gibt das HTML für den „Auf Twitter teilen“-Button und möglicherweise einen Platzhalter für die Gutscheincode-Nachricht oder einen Modal-Trigger aus. Es wird wahrscheinlich Variablen für den Produktnamen, die Produkt-URL und den Standard-Share-Text enthalten.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul speichert seine Konfigurationseinstellungen hauptsächlich in der PrestaShop-Tabelle `ps_configuration`.
    - `PS_TWITTERCOUPON_ENABLED` (boolean)
    - `PS_TWITTERCOUPON_HOOK` (string)
    - `PS_TWITTERCOUPON_SHARES_REQUIRED` (int)
    - `PS_TWITTERCOUPON_PREFIX` (string)
    - `PS_TWITTERCOUPON_VALUE` (float)
    - `PS_TWITTERCOUPON_VALIDITY` (int)
    - `PS_TWITTERCOUPON_MIN_AMOUNT` (float)
    - `PS_TWITTERCOUPON_DESCRIPTION` (string)
    - `PS_TWITTERCOUPON_NAME` (string)
    - `PS_TWITTERCOUPON_DEFAULT_TEXT` (string)
  - Es verwendet wahrscheinlich auch eine benutzerdefinierte Tabelle (z. B. `ps_twittercoupon_shares` oder ähnlich), um einzelne Kunden-Shares (nach `id_customer` oder `ip_address`, `id_product`) zu verfolgen und Missbrauch zu verhindern, obwohl keine explizite SQL-Datei aufgeführt wurde, würde diese Logik in der `install()`-Methode des Hauptmoduls behandelt werden. Diese Tabelle würde Folgendes verfolgen:
    - `id_customer` (falls angemeldet)
    - `ip_address`
    - `id_product`
    - `share_date`
    - `voucher_issued` (boolean)
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Zum Laden der CSS- und JavaScript-Assets des Moduls (`twittercoupon/css.css`, `twittercoupon/lib/voucherengine/script.js`, `twittercoupon/trusted.js`). |
| `displayProductButtons` | Auf der Produktseite, typischerweise in der Nähe des In-den-Warenkorb-Buttons. | Zum Anzeigen des Twitter-Teilen-Buttons (`share.tpl`). |
| `displayRightColumnProduct` | Auf der Produktseite, in der rechten Spalte. | Alternativer Hook zum Anzeigen des Twitter-Teilen-Buttons (`share.tpl`). |
| `displayFooterProduct` | Auf der Produktseite, im Footer-Bereich. | Alternativer Hook zum Anzeigen des Twitter-Teilen-Buttons (`share.tpl`). |
| `displayProductExtraContent` | Auf der Produktseite, oft unterhalb der Hauptproduktbeschreibung. | Alternativer Hook zum Anzeigen des Twitter-Teilen-Buttons (`share.tpl`). |
| `actionFrontControllerSetMedia` | Bevor ein Front-Controller seinen Inhalt rendert, wodurch Module Assets hinzufügen können. | Zum Laden der CSS- und JavaScript-Assets des Moduls bedingt basierend auf der Seite. |
| (Interner AJAX-Aufruf) | Wird durch JavaScript bei einem Share-Ereignis ausgelöst. | Zum Verarbeiten des Shares, Aktualisieren der Share-Anzahl und Generieren einer `CartRule` (Gutschein), wenn die Bedingungen erfüllt sind. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und dedizierten technischen Support für das Modul „Twitter Produkt teilen + Gutscheincode“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Team ist bestrebt, zeitnahe Unterstützung zu leisten und die optimale Leistung Ihres Moduls sicherzustellen.

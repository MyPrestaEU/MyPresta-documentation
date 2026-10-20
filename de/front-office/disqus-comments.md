---
title: "DISQUS Kommentare - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul DISQUS Kommentare von MyPresta.eu."
sidebar:
  label: "DISQUS Kommentare - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul DISQUS comments auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/disqus-comments.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/disqus-comments/)
>
> ---


# DISQUS Kommentare

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop und für die Kommunikation mit externen Diensten wie Disqus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren > DISQUS Kommentare)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie einstellen, wie Disqus in Ihren Shop integriert wird.

#### **1. Site shortname**

- **Was diese Einstellung bewirkt:** Dies ist der eindeutige Bezeichner für Ihre Disqus-Website. Sie erhalten diesen von Ihrem Disqus-Konto, wenn Sie Ihre Website registrieren. Er teilt Disqus mit, welche Kommentar-Threads zu Ihrem Shop gehören.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Bei korrekter Einstellung:* Disqus-Kommentare werden korrekt für Ihre Produkte geladen und gespeichert.
  - *Bei falscher oder leerer Einstellung:* Disqus kann Kommentare nicht laden oder lädt möglicherweise Kommentare von einer anderen Website, was zu Fehlern oder fehlenden Kommentaren führt.
- **Empfohlener Wert:** Ihr eindeutiger Disqus-Shortname (z. B. `ihrshopname`).
- **Händler-Szenario / Beispiel:** Wenn Sie Ihre Website auf Disqus als „Mein toller Shop“ registriert haben, könnte Ihr Shortname „meintollershop“ sein. Geben Sie genau diese Zeichenfolge hier ein.

#### **2. Comments widget position**

- **Was diese Einstellung bewirkt:** Dies steuert, wo der Haupt-Disqus-Kommentarbereich auf Ihren Produktseiten erscheint.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf „Produkt-Tab-Bereich“ eingestellt:* Kommentare erscheinen in einem neuen Tab auf der Produktseite (z. B. neben „Beschreibung“ oder „Datenblatt“). Kunden klicken auf den Tab, um Kommentare anzuzeigen.
  - *Wenn auf „Produkt-Fußzeilenbereich“ eingestellt:* Kommentare erscheinen am unteren Rand der Produktseite, unter den Hauptproduktinformationen. Kunden sehen sie, wenn sie nach unten scrollen.
- **Empfohlener Wert:** „Produkt-Tab-Bereich“ für ein saubereres Produktseitenlayout oder „Produkt-Fußzeilenbereich“, wenn Sie möchten, dass Kommentare sofort sichtbar sind, ohne auf einen Tab klicken zu müssen.
- **Händler-Szenario / Beispiel:** Wenn Ihre Produktseiten bereits sehr lang sind, hält das Platzieren von Kommentaren in einem Tab die anfängliche Ansicht übersichtlich. Wenn Sie Kundenfeedback hervorheben möchten, macht das Platzieren in der Fußzeile sie prominenter.

#### **3. Testimonials page**

- **Was diese Einstellung bewirkt:** Dies aktiviert oder deaktiviert eine dedizierte Seite in Ihrem Shop, die alle Disqus-Kommentare von all Ihren Produkten aggregiert.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn „Aktiviert“:* Eine neue Seite wird unter einer URL wie `ihrshop.de/testimonials` (oder ähnlich, je nach Ihren sprechenden URLs) erstellt, die alle Kommentare anzeigt.
  - *Wenn „Deaktiviert“:* Eine solche Seite ist nicht verfügbar.
- **Empfohlener Wert:** „Aktiviert“, um eine zentrale Anlaufstelle für Kundenfeedback bereitzustellen.
- **Händler-Szenario / Beispiel:** Wenn Sie dies aktivieren, können Sie von Ihrer Fußzeile aus auf eine Seite „Kundenbewertungen“ oder „Was unsere Kunden sagen“ verlinken, die alle positiven Rückmeldungen an einem Ort präsentiert.

#### **4. Testimonials link appearance**

- **Was diese Einstellung bewirkt:** Wenn die „Testimonials-Seite“ aktiviert ist, steuert dies, wo ein Link zu dieser Seite im Layout Ihres Shops erscheint.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn „Verbergen“:* Die Testimonials-Seite existiert, aber es wird kein automatischer Link vom Modul hinzugefügt. Sie müssten manuell einen Link hinzufügen (z. B. im Fußzeilenmenü Ihres Themes).
  - *Wenn „Linke Spalte“:* Ein Link zur Testimonials-Seite erscheint in der linken Spalte Ihres Shops.
  - *Wenn „Rechte Spalte“:* Ein Link zur Testimonials-Seite erscheint in der rechten Spalte Ihres Shops.
- **Empfohlener Wert:** „Rechte Spalte“ oder „Linke Spalte“, um die Testimonials-Seite leicht auffindbar zu machen.
- **Händler-Szenario / Beispiel:** Wenn Ihr Shop eine linke Spalte für Kategorien verwendet, könnte das Platzieren des Testimonials-Links in der rechten Spalte angemessener sein.

#### **5. Homepage recent comments**

- **Was diese Einstellung bewirkt:** Dies steuert, ob ein Block mit den neuesten Disqus-Kommentaren auf der Startseite Ihres Shops erscheint.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn „Aktiviert“:* Ein Block mit aktuellen Kommentaren wird auf Ihrer Startseite angezeigt.
  - *Wenn „Deaktiviert“:* Es erscheint kein Block mit aktuellen Kommentaren auf der Startseite.
- **Empfohlener Wert:** „Aktiviert“, um Ihre Startseite dynamisch zu halten und die neuesten Kundenaktivitäten hervorzuheben.
- **Händler-Szenario / Beispiel:** Das Anzeigen aktueller Kommentare auf der Startseite kann Besucher dazu ermutigen, Produkte mit aktiven Diskussionen zu erkunden, was potenziell zu mehr Verkäufen führen kann.

#### **6. Right column recent comments**

- **Was diese Einstellung bewirkt:** Dies steuert, ob ein Block mit den neuesten Disqus-Kommentaren in der rechten Spalte Ihres Shops erscheint.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn „Aktiviert“:* Ein Block mit aktuellen Kommentaren wird in der rechten Spalte auf Seiten angezeigt, auf denen die rechte Spalte aktiv ist.
  - *Wenn „Deaktiviert“:* Es erscheint kein Block mit aktuellen Kommentaren in der rechten Spalte.
- **Empfohlener Wert:** „Aktiviert“, um das Engagement auf Ihrer gesamten Website aufrechtzuerhalten.
- **Händler-Szenario / Beispiel:** Wenn Ihr Shop eine rechte Spalte hat, kann das Anzeigen aktueller Kommentare dort einen konstanten Strom frischer Inhalte liefern und zur Erkundung anregen.

#### **7. Left column recent comments**

- **Was diese Einstellung bewirkt:** Dies steuert, ob ein Block mit den neuesten Disqus-Kommentaren in der linken Spalte Ihres Shops erscheint.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn „Aktiviert“:* Ein Block mit aktuellen Kommentaren wird in der linken Spalte auf Seiten angezeigt, auf denen die linke Spalte aktiv ist.
  - *Wenn „Deaktiviert“:* Es erscheint kein Block mit aktuellen Kommentaren in der linken Spalte.
- **Empfohlener Wert:** „Aktiviert“, um das Engagement auf Ihrer gesamten Website aufrechtzuerhalten.
- **Händler-Szenario / Beispiel:** Ähnlich wie bei der rechten Spalte kann die Verwendung der linken Spalte für aktuelle Kommentare effektiv sein, wenn Ihr Theme die linke Spalte hauptsächlich für Navigation oder andere Blöcke verwendet.

#### **8. Show disqus only for logged users that purchased product**

- **Was diese Einstellung bewirkt:** Dies ist eine leistungsstarke Einstellung, um einzuschränken, wer Disqus-Kommentare auf Produktseiten sehen und mit ihnen interagieren kann.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn „Aktiviert“:* Nur Kunden, die in ihrem Konto angemeldet sind UND das spezifische Produkt zuvor gekauft haben, sehen den Disqus-Kommentarbereich. Alle anderen Besucher sehen ihn nicht.
  - *Wenn „Deaktiviert“:* Alle Besucher (angemeldet oder Gast, Käufer oder nicht) sehen den Disqus-Kommentarbereich.
- **Empfohlener Wert:** „Deaktiviert“ für maximales Engagement und SEO-Vorteile. „Aktiviert“, wenn Sie sicherstellen möchten, dass nur verifizierte Käufer kommentieren können, was die Glaubwürdigkeit von Bewertungen erhöhen, aber die Anzahl der Kommentare reduzieren kann.
- **Händler-Szenario / Beispiel:** Wenn Sie mit Spam oder irrelevanten Kommentaren zu kämpfen haben, kann das Aktivieren dieser Option Nicht-Käufer herausfiltern. Wenn Ihr Ziel jedoch eine breite Diskussion und SEO ist, lassen Sie es deaktiviert.

#### **9. How many recent comments to show?**

- **Was diese Einstellung bewirkt:** Dies bestimmt die Anzahl der aktuellen Kommentare, die in den Blöcken „Aktuelle Kommentare“ (auf der Startseite, in der linken oder rechten Spalte) angezeigt werden.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf eine Zahl eingestellt (z. B. 5):* Die Blöcke zeigen so viele der neuesten Kommentare an.
  - *Wenn auf 0 oder leer eingestellt:* Es werden keine aktuellen Kommentare in den Blöcken angezeigt, selbst wenn die Blöcke aktiviert sind.
- **Empfohlener Wert:** 3 bis 5 Kommentare für einen kompakten Block oder bis zu 10 für eine prominentere Anzeige.
- **Händler-Szenario / Beispiel:** Das Anzeigen von 5 Kommentaren bietet ein gutes Gleichgewicht zwischen der Anzeige von Aktivität und der Vermeidung, dass der Block zu lang wird.

#### **Konfigurations-Kurzübersichtstabelle**

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Site shortname | Ihr Disqus-Shortname | Eindeutiger Bezeichner für Ihr Disqus-Konto; unerlässlich, damit Kommentare geladen werden. |
| Modulkonfiguration | Comments widget position | Produkt-Tab-Bereich | Wo der Hauptkommentarbereich auf Produktseiten erscheint (Tab oder Fußzeile). |
| Modulkonfiguration | Testimonials page | Aktiviert | Erstellt eine dedizierte Seite, die alle Kommentare aggregiert. |
| Modulkonfiguration | Testimonials link appearance | Rechte Spalte | Wo ein Link zur Testimonials-Seite erscheint (falls aktiviert). |
| Modulkonfiguration | Homepage recent comments | Aktiviert | Zeigt einen Block mit aktuellen Kommentaren auf der Startseite an. |
| Modulkonfiguration | Right column recent comments | Aktiviert | Zeigt einen Block mit aktuellen Kommentaren in der rechten Spalte an. |
| Modulkonfiguration | Left column recent comments | Aktiviert | Zeigt einen Block mit aktuellen Kommentaren in der linken Spalte an. |
| Modulkonfiguration | Show disqus only for logged users that purchased product | Deaktiviert | Beschränkt die Sichtbarkeit/Interaktion von Kommentaren auf verifizierte Käufer. |
| Modulkonfiguration | How many recent comments to show? | 5 | Anzahl der Kommentare, die in den Blöcken für aktuelle Kommentare angezeigt werden sollen. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Disqus-Kommentare erscheinen nicht auf den Produktseiten. Was soll ich tun?**

- **A:** Überprüfen Sie zunächst Ihren „Site shortname“ in der Modulkonfiguration. Er muss exakt mit dem Shortname Ihres Disqus-Kontos übereinstimmen. Stellen Sie außerdem sicher, dass Sie „Comments widget position“ entweder auf „Produkt-Tab-Bereich“ oder „Produkt-Fußzeilenbereich“ eingestellt haben. Leeren Sie schließlich Ihren PrestaShop-Cache (Erweiterte Parameter > Leistung > Cache leeren) und Ihren Browser-Cache.

**F2: Die Blöcke „Aktuelle Kommentare“ werden in meinen Spalten/auf der Startseite nicht angezeigt.**

- **A:** Überprüfen Sie, ob Sie „Homepage recent comments“, „Right column recent comments“ oder „Left column recent comments“ in der Modulkonfiguration aktiviert haben. Stellen Sie außerdem sicher, dass „How many recent comments to show?“ auf eine Zahl größer als 0 eingestellt ist. Wenn Ihr Theme auf bestimmten Seiten keine linken/rechten Spalten anzeigt, erscheinen die Blöcke dort nicht. Leeren Sie den Cache nach Änderungen.

**F3: Ich habe die „Testimonials-Seite“ aktiviert, aber ich finde keinen Link dazu.**

- **A:** Wenn Sie „Testimonials link appearance“ auf „Verbergen“ gesetzt haben, fügt das Modul keinen automatischen Link hinzu. Sie müssen manuell einen Link zur Seite hinzufügen (z. B. im Fußzeilenmenü Ihres Themes). Die URL für die Testimonials-Seite ist typischerweise `ihrshop.de/module/disqus/testimonials` (oder eine sprechende URL-Version, falls aktiviert). Wenn Sie „Linke Spalte“ oder „Rechte Spalte“ gewählt haben, stellen Sie sicher, dass diese Spalten auf den von Ihnen angezeigten Seiten aktiv sind.

**F4: Nur einige Benutzer können die Kommentare sehen, oder ich kann sie als Gast nicht sehen.**

- **A:** Überprüfen Sie die Einstellung „Show disqus only for logged users that purchased product“. Wenn diese aktiviert ist, sehen nur angemeldete Kunden, die das spezifische Produkt gekauft haben, die Kommentare. Deaktivieren Sie diese Einstellung, wenn Sie möchten, dass alle Besucher Kommentare sehen und mit ihnen interagieren können.

**F5: Das Styling meines benutzerdefinierten Themes kollidiert mit den Disqus-Kommentaren.**

- **A:** Das Disqus-Widget selbst ist weitgehend eigenständig und wird von Disqus gestylt. Der Container oder Tab, der das Widget enthält, könnte jedoch von der CSS Ihres Themes betroffen sein. Möglicherweise benötigen Sie einen Webentwickler, um die Elemente mit den Browser-Entwicklertools zu überprüfen und benutzerdefiniertes CSS zu Ihrem Theme hinzuzufügen, um Abstände, Schriftarten oder Farben um das Disqus-Widget herum anzupassen.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick über das Modul DISQUS Kommentare für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul DISQUS Kommentare folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich Hooks für die Front-Office-Anzeige und eine `getContent()`-Methode für die Back-Office-Konfiguration nutzt. Es integriert den Disqus Universal Embed Code dynamisch. Das Modul verwendet einen benutzerdefinierten Front-Controller für die Testimonials-Seite und einen weiteren für AJAX-Aufrufe (obwohl der AJAX-Controller derzeit ein Platzhalter zu sein scheint oder nicht stark für die Kern-Disqus-Funktionalität genutzt wird). Die Konfiguration wird in `ps_configuration` gespeichert.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**:

  - `controllers/front/index.php`
    - **Klassenname:** `DisqusIndexModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit:** Dieser Controller ist wahrscheinlich ein Standard oder Fallback für das Front-Office-Routing des Moduls. Im Kontext von Disqus könnte er für allgemeine modulbezogene Front-End-Aktionen verwendet werden, obwohl der primäre Disqus-Embed normalerweise über Hooks gehandhabt wird. Er könnte als Basis für zukünftige AJAX-Funktionalitäten oder einfache Seitenanzeigen dienen, falls erforderlich.
  - `controllers/front/testimonials.php`
    - **Klassenname:** `DisqusTestimonialsModuleFrontController` (erweitert `ModuleFrontController`)
    - **Verantwortlichkeit:** Dieser Controller ist für das Rendern der dedizierten „Testimonials“-Seite verantwortlich. Er ruft die notwendige Konfiguration (z. B. `disqus_shortname`) ab und übergibt sie an das Template `testimonials.tpl`, das dann den Disqus Universal Embed Code einbettet, der so konfiguriert ist, dass er alle Kommentare für den angegebenen Shortname anzeigt. Dieser Controller verarbeitet die Route `module/disqus/testimonials`.
- **Back-Office-Admin-Controller**: Keine explizit im bereitgestellten Inventar definiert. Die gesamte Konfiguration wird über die `getContent()`-Methode der Hauptmoduldatei gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Gemäß dem Inventar sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` vorhanden. Das Modul verlässt sich auf die `Configuration`-Klasse von PrestaShop, um seine Einstellungen zu speichern.

### 4.4 JavaScript-Assets (`views/js/`)

Gemäß dem Inventar sind keine benutzerdefinierten JavaScript-Dateien im Verzeichnis `views/js/` vorhanden. Das Modul bettet den Disqus Universal Embed Code (normalerweise ein `<script>`-Tag mit `DISQUS.init()` oder ähnlicher Logik) direkt in die relevanten Smarty-Templates ein. Dies bedeutet, dass das eigene JavaScript von Disqus direkt von `disqus.com` geladen wird.

### 4.5 CSS-Stylesheets (`views/css/`)

Gemäß dem Inventar sind keine benutzerdefinierten CSS-Dateien im Verzeichnis `views/css/` vorhanden. Das Styling des Disqus-Kommentar-Widgets selbst wird von Disqus übernommen. Jede integrationsspezifische Stilgebung (z. B. für die Blöcke der letzten Kommentare oder das Layout der Testimonials-Seite) wäre entweder minimal, vom Theme geerbt oder inline in den Templates.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:

  - `last-comments.tpl`: Dieses Template wird verwendet, um den Block „Aktuelle Kommentare“ anzuzeigen. Es iteriert durch eine Liste aktueller Kommentare (die über JavaScript oder einen serverseitigen Aufruf, falls implementiert, von Disqus abgerufen werden) und zeigt sie an. Dieses Template wird wahrscheinlich in den Hooks `displayHome`, `displayLeftColumn` und `displayRightColumn` gerendert.
  - `leftColumn.tpl`: Dieses Template ist wahrscheinlich ein Wrapper oder spezifischer Inhalt für den Hook `displayLeftColumn`, der potenziell `last-comments.tpl` oder den Testimonials-Link enthält.
  - `productfooter.tpl`: Dieses Template wird im Hook `displayProductFooter` gerendert. Es enthält den Disqus Universal Embed Code für Produktkommentare, wenn die „Comments widget position“ auf „Produkt-Fußzeilenbereich“ eingestellt ist.
  - `rightColumn.tpl`: Ähnlich wie `leftColumn.tpl` ist dies für den Hook `displayRightColumn`, der potenziell `last-comments.tpl` oder den Testimonials-Link enthält.
- **Admin-Templates (`views/templates/admin/`)**: Keine.
- **Front-Office-Templates (`views/templates/front/`)**:

  - `testimonials.tpl`: Dieses Template wird vom `DisqusTestimonialsModuleFrontController` gerendert. Es enthält den Disqus Universal Embed Code, der so konfiguriert ist, dass er alle Kommentare für den Site-Shortname anzeigt, wodurch effektiv die aggregierte Testimonials-Seite erstellt wird.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**: Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `DISQUS_SHORTNAME`, `DISQUS_HOOK`, `DISQUS_TEST`, `DISQUS_TEST_WHERE`, `DISQUS_RIGHTRECENT`, `DISQUS_LEFTRECENT`, `DISQUS_FORLOGGED`, `DISQUS_LASTCOMMENTS`, `DISQUS_LASTC_NB` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Potenziell zur Aufnahme globaler Disqus-Konfigurationsvariablen oder CSS/JS, falls erforderlich, obwohl der Haupt-Embed in spezifischen Inhalts-Hooks erfolgt. |
| `displayProductExtraContent` | Innerhalb der Produktseite, oft für Tabs oder zusätzliche Inhaltsblöcke verwendet. | Wird verwendet, um den Disqus-Kommentarbereich innerhalb eines Produkt-Tabs anzuzeigen, wenn „Comments widget position“ auf „Produkt-Tab-Bereich“ eingestellt ist. |
| `displayRightColumn` | In der rechten Spalte von Seiten. | Wird verwendet, um den Block „Aktuelle Kommentare“ oder den „Testimonials-Link“ anzuzeigen, falls konfiguriert. |
| `displayProductFooter` | Am unteren Rand des Produktseiteninhalts. | Wird verwendet, um den Disqus-Kommentarbereich anzuzeigen, wenn „Comments widget position“ auf „Produkt-Fußzeilenbereich“ eingestellt ist. |
| `displayLeftColumn` | In der linken Spalte von Seiten. | Wird verwendet, um den Block „Aktuelle Kommentare“ oder den „Testimonials-Link“ anzuzeigen, falls konfiguriert. |
| `displayHome` | Auf der Startseite. | Wird verwendet, um den Block „Aktuelle Kommentare“ auf der Startseite anzuzeigen. |
| `actionValidateOrder` | Nachdem eine Bestellung erfolgreich validiert wurde. | Dieser Hook ist in der `install()`-Methode des Moduls aufgeführt, was auf eine potenzielle zukünftige Funktion oder eine Überprüfung gekaufter Produkte hindeutet. Er wird wahrscheinlich in Verbindung mit der Einstellung „Show disqus only for logged users that purchased product“ verwendet, um die Kaufhistorie zu überprüfen. |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen zum Modul DISQUS Kommentare zur Verfügung.

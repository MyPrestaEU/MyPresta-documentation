---
title: "Google Produkt-Plus-Button + Gutschein - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Google Produkt-Plus-Button + Gutschein“ von MyPresta.eu."
sidebar:
  label: "Google Produkt-Plus-Button + Gutschein - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Google product plus button + coupon auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/google-product-plus-button-coupon.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/google-product-plus-button-coupon/)
>
> ---


# Google Produkt-Plus-Button + Gutschein

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst und jedes Modul, das mit externen APIs interagiert, erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Google Produkt-Plus-Button + Gutschein“. Hier finden Sie alle Einstellungen, um zu steuern, wie der Google +1-Button erscheint und wie die Gutscheine generiert werden.

#### **Allgemeine Einstellungen**

- **Update\_ / Updatev\_ (Interne Einstellungen)**

  - **Was diese Einstellung bewirkt:** Dies sind interne Moduleinstellungen, die zur Verfolgung von Updates und Versionierung verwendet werden. Sie sind nicht für die direkte Interaktion des Händlers gedacht.
  - **Auswirkung einer Änderung dieser Einstellung:** Sie sollten diese Werte **niemals** manuell ändern. Dies könnte Modul-Updates oder interne Prozesse stören.
  - **Empfohlener Wert:** Belassen Sie es wie es ist.
  - **Händlerszenario / Beispiel:** Diese Einstellungen stellen sicher, dass Ihr Modul korrekt aktualisiert werden kann, wenn neue Versionen von MyPresta.eu veröffentlicht werden.
- **Gutscheincode (gc\_voucher)**

  - **Was diese Einstellung bewirkt:** Dies ist der **Rabattprozentsatz**, der auf den Gutschein angewendet wird, der für Kunden generiert wird, die auf den +1-Button klicken.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf `10` (für 10%) gesetzt:* Kunden, die ein Produkt mit +1 versehen, erhalten einen Gutschein für 10% Rabatt auf ihren nächsten Einkauf.
    - *Wenn auf `0` gesetzt oder leer gelassen:* Es wird kein Rabatt angewendet, wodurch der Gutschein im Wesentlichen wertlos wird.
  - **Empfohlener Wert:** Ein angemessener Rabattprozentsatz, z.B. `5`, `10` oder `15`.
  - **Händlerszenario / Beispiel:** Sie möchten einen Rabatt von 10% anbieten, um Social Sharing zu fördern. Sie würden hier `10` eingeben.
- **Preise anzeigen (gc\_show\_prices)**

  - **Was diese Einstellung bewirkt:** Legt fest, ob die Original- und reduzierten Preise zusammen mit dem Gutscheinangebot angezeigt werden.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Der Kunde sieht den Originalpreis und den Preis nach Abzug des Rabatts, wodurch der Wert des Gutscheins klarer wird.
    - *Wenn deaktiviert (Nein):* Nur der Gutscheincode wird angezeigt, ohne explizite Preisvergleiche.
  - **Empfohlener Wert:** `Ja`. Das Anzeigen der Preisdifferenz erhöht oft den wahrgenommenen Wert des Gutscheins.
  - **Händlerszenario / Beispiel:** Ein Kunde sieht ein Produkt für 100 €. Wenn „Preise anzeigen“ aktiviert ist und der Gutschein 10% beträgt, sieht er „100 € -> 90 € mit Gutschein“, was überzeugender ist.
- **Gesamt anzeigen (gc\_show\_total)**

  - **Was diese Einstellung bewirkt:** Steuert, ob der gesamte Bestellwert (nach Rabatt) mit dem Gutschein angezeigt wird. Dies ist in der Regel relevant, wenn der Gutschein für den gesamten Warenkorb gilt.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Der Kunde könnte einen geschätzten Gesamtbestellwert mit dem angewendeten Rabatt sehen.
    - *Wenn deaktiviert (Nein):* Der Fokus bleibt auf dem Produktpreis oder dem Gutscheincode selbst.
  - **Empfohlener Wert:** `Ja`, besonders wenn der Gutschein warenkorbweit ist, da er dem Kunden hilft, seine Ersparnisse zu visualisieren.
  - **Händlerszenario / Beispiel:** Wenn der Gutschein für den gesamten Warenkorb gilt, kann das Anzeigen einer potenziellen Gesamtersparnis zu einem größeren Kauf anregen.
- **Produkte anzeigen (gc\_show\_products)**

  - **Was diese Einstellung bewirkt:** Legt fest, ob die spezifischen Produkte, für die der Gutschein gilt, aufgelistet werden, wenn der Gutschein angezeigt wird.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Die Gutscheinmeldung könnte explizit angeben „Dieser Gutschein gilt für [Produktname]“.
    - *Wenn deaktiviert (Nein):* Der Gutschein wird allgemeiner präsentiert, oder es wird angenommen, dass er für das gerade mit +1 versehene Produkt gilt.
  - **Empfohlener Wert:** `Ja`, zur Klarheit, es sei denn, Ihr Gutschein gilt immer für den gesamten Shop.
  - **Händlerszenario / Beispiel:** Wenn Ihr Gutschein nur für das Produkt gilt, das der Kunde mit +1 versehen hat, klärt das Anzeigen des Produktnamens dessen Verwendung.
- **Produkt-URL anzeigen (gc\_show\_product\_url)**

  - **Was diese Einstellung bewirkt:** Steuert, ob die URL des Produkts, das mit +1 versehen wurde, in der Gutscheinanzeige enthalten ist.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn aktiviert (Ja):* Der Kunde sieht einen direkten Link zurück zur Produktseite, was nützlich sein kann, wenn er wegnervigiert.
    - *Wenn deaktiviert (Nein):* Die URL wird weggelassen.
  - **Empfohlener Wert:** `Ja`, für eine bessere Benutzererfahrung und Navigation.
  - **Händlerszenario / Beispiel:** Ein Kunde erhält einen Gutschein und schließt dann das Pop-up. Die Produkt-URL hilft ihm, schnell zu dem Produkt zurückzukehren, an dem er interessiert war.
- **Letzter Tab (gc\_lasttab)**

  - **Was diese Einstellung bewirkt:** Diese Einstellung steuert wahrscheinlich, in welchem Tab oder Abschnitt der Produktseite der Google +1-Button und die Gutscheininformationen erscheinen, wenn Ihr Theme einen Tab-Bereich für die Produktbeschreibung verwendet.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf `1` (oder ähnlichen Wert) gesetzt:* Der Modulinhalt erscheint im letzten Tab der Produktseite.
    - *Wenn auf `0` (oder ähnlichen Wert) gesetzt:* Der Modulinhalt erscheint im ersten Tab oder an einem Standardort.
  - **Empfohlener Wert:** Experimentieren Sie mit `1`, um zu sehen, ob es zum Layout Ihres Themes passt. Wenn Ihr Theme keine Tabs verwendet, hat diese Einstellung möglicherweise keine sichtbare Auswirkung.
  - **Händlerszenario / Beispiel:** Ihre Produktseite hat die Tabs „Beschreibung“, „Datenblatt“ und „Bewertungen“. Wenn Sie dies auf `1` setzen, könnte der +1-Button und der Gutschein in einem neuen Tab „Social Share“ oder am Ende des Tabs „Beschreibung“ platziert werden.
- **Position (gc\_position)**

  - **Was diese Einstellung bewirkt:** Bestimmt den allgemeinen Bereich auf der Produktseite, in dem der Google +1-Button und das Gutscheinangebot angezeigt werden. Dies entspricht dem Hook-System von PrestaShop.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Ändern des Wertes:* Verschiebt den Inhalt des Moduls an verschiedene Stellen auf der Produktseite (z.B. über „In den Warenkorb“, unter der Beschreibung, in einer Seitenleiste).
  - **Empfohlener Wert:** `displayproductActions` oder `displayproductFooter` sind gängige und effektive Orte. Testen Sie verschiedene Positionen, um zu sehen, was am besten zu Ihrem Theme passt und für Kunden am sichtbarsten ist.
  - **Händlerszenario / Beispiel:** Sie möchten, dass der +1-Button sehr prominent ist, daher wählen Sie `displayproductActions`, um ihn in der Nähe des Buttons „In den Warenkorb“ zu platzieren.
- **Anzahl der Likes (gc\_nblikes)**

  - **Was diese Einstellung bewirkt:** Diese Einstellung steuert wahrscheinlich die Mindestanzahl von +1s, die erforderlich sind, bevor ein Gutschein ausgestellt wird, oder es könnte eine Anzeigeeinstellung für die +1-Anzahl sein. Angesichts der Kernfunktionalität des Moduls ist es wahrscheinlicher, dass es mit dem Gutschein-Trigger zusammenhängt.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Wenn auf `1` (oder `0`) gesetzt:* Ein Gutschein wird sofort nach einem einzelnen +1 ausgestellt.
    - *Wenn auf `5` gesetzt:* Ein Gutschein wird möglicherweise erst nach 5 einzigartigen +1s ausgestellt (weniger wahrscheinlich angesichts der sofortigen Belohnungsnatur, aber möglich für eine „Gruppengutschein“-Funktion). Wahrscheinlicher ist, dass es die Anzeige der +1-Anzahl steuert.
  - **Empfohlener Wert:** `1` (oder `0`, wenn es „immer anzeigen“ bedeutet). Die Stärke des Moduls ist die sofortige Belohnung.
  - **Händlerszenario / Beispiel:** Sie möchten, dass jeder Kunde, der ein +1 gibt, einen Gutschein erhält, also setzen Sie dies auf `1`.
- **Button-Stil (gc\_button\_style)**

  - **Was diese Einstellung bewirkt:** Ermöglicht Ihnen, den visuellen Stil oder die Größe des Google +1-Buttons zu wählen.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Ändern des Wertes:* Ändert das Aussehen des +1-Buttons (z.B. klein, mittel, groß, hoch, mit oder ohne Zähler).
  - **Empfohlener Wert:** Wählen Sie einen Stil, der sichtbar ist, aber das Design Ihrer Produktseite nicht stört. „Mittel“ oder „Standard“ sind in der Regel gute Ausgangspunkte.
  - **Händlerszenario / Beispiel:** Ihre Produktseite hat begrenzten Platz, daher wählen Sie einen „kleinen“ Button-Stil.
- **Teilen-Modus (gcshare\_mode)**

  - **Was diese Einstellung bewirkt:** Diese Einstellung steuert wahrscheinlich, wie die Teilen-Funktionalität funktioniert, möglicherweise bietet sie verschiedene Möglichkeiten für den Kunden, die Google+-Plattform zu teilen oder mit ihr zu interagieren.
  - **Auswirkung einer Änderung dieser Einstellung:**
    - *Ändern des Wertes:* Könnte das Pop-up-Verhalten oder den spezifischen Google+-Teilen-Dialog ändern, der erscheint.
  - **Empfohlener Wert:** Belassen Sie den Standardwert, es sei denn, Sie haben einen bestimmten Grund, ihn zu ändern, und verstehen die Auswirkungen auf die Google+-Integration.
  - **Händlerszenario / Beispiel:** Sie könnten mit verschiedenen Modi experimentieren, wenn Sie feststellen, dass das Standard-Teilen-Erlebnis für Ihre Kunden nicht optimal ist.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Gutscheincode (gc\_voucher) | 10 | Rabattprozentsatz für den generierten Gutschein. |
| Modulkonfiguration | Preise anzeigen (gc\_show\_prices) | Ja | Original- und reduzierte Preise mit Gutschein anzeigen. |
| Modulkonfiguration | Gesamt anzeigen (gc\_show\_total) | Ja | Geschätzten Gesamtbestellwert mit Rabatt anzeigen. |
| Modulkonfiguration | Produkte anzeigen (gc\_show\_products) | Ja | Spezifische Produkte auflisten, für die der Gutschein gilt. |
| Modulkonfiguration | Produkt-URL anzeigen (gc\_show\_product\_url) | Ja | Produkt-URL in der Gutscheinanzeige enthalten. |
| Modulkonfiguration | Letzter Tab (gc\_lasttab) | 1 (oder theme-abhängig) | Position in Produktseiten-Tabs (falls zutreffend). |
| Modulkonfiguration | Position (gc\_position) | displayproductActions / displayproductFooter | Allgemeine Platzierung des Buttons und Gutscheins auf der Produktseite. |
| Modulkonfiguration | Anzahl der Likes (gc\_nblikes) | 1 | Mindestanzahl von +1s für Gutschein (wahrscheinlich 1 für sofortige Belohnung). |
| Modulkonfiguration | Button-Stil (gc\_button\_style) | Standard / Mittel | Visuelle Größe und Stil des Google +1-Buttons. |
| Modulkonfiguration | Teilen-Modus (gcshare\_mode) | Standard | Steuert die Google+-Teilen-Interaktion. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

- **F: Der Google +1-Button wird auf meinen Produktseiten nicht angezeigt.**

  - **A:** Überprüfen Sie zunächst die Einstellung „Position (gc\_position)“ in der Modulkonfiguration. Stellen Sie sicher, dass Sie einen Hook ausgewählt haben, der von Ihrem Theme auf der Produktseite tatsächlich gerendert wird. Einige benutzerdefinierte Themes implementieren möglicherweise nicht alle Standard-PrestaShop-Hooks.
  - **A:** Leeren Sie Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren).
  - **A:** Suchen Sie in der Entwicklerkonsole Ihres Browsers (F12) nach JavaScript-Fehlern. Konflikte mit anderen Modulen oder Theme-Skripten können manchmal das Laden von Buttons verhindern.
  - **A:** Stellen Sie sicher, dass das Modul im Modul-Manager aktiviert ist.
- **F: Kunden klicken auf +1, erhalten aber keinen Gutschein.**

  - **A:** Überprüfen Sie, ob die Einstellung „Gutscheincode (gc\_voucher)“ einen gültigen Rabattprozentsatz enthält (z.B. `10` für 10%). Wenn sie `0` oder leer ist, wird kein effektiver Gutschein generiert.
  - **A:** Überprüfen Sie die Einstellung „Anzahl der Likes (gc\_nblikes)“. Wenn sie auf einen Wert größer als 1 gesetzt ist, wird der Gutschein erst ausgestellt, wenn dieser Schwellenwert erreicht ist. Für sofortige Gutscheine sollte er 1 sein.
  - **A:** Stellen Sie sicher, dass keine serverseitigen Fehler die Gutscheingenerierung verhindern. Überprüfen Sie Ihre PrestaShop-Fehlerprotokolle (Erweiterte Einstellungen > Protokolle).
- **F: Der Button sieht seltsam aus oder ist auf meiner mobilen Website falsch ausgerichtet.**

  - **A:** Dies ist oft ein CSS-Konflikt mit Ihrem Theme. Das Modul enthält sein eigenes CSS, aber die Stile Ihres Themes könnten es überschreiben oder damit in Konflikt geraten. Möglicherweise benötigen Sie einen Webentwickler, um das CSS zu überprüfen und kleinere Anpassungen vorzunehmen.
  - **A:** Probieren Sie verschiedene Optionen für den „Button-Stil (gc\_button\_style)“ aus, um zu sehen, ob eine andere Größe besser gerendert wird.
- **F: Kann ich die Gutscheinmeldung oder Gültigkeit anpassen?**

  - **A:** Die Konfiguration des Moduls steuert hauptsächlich den Rabattprozentsatz und die Anzeigeoptionen. Für erweiterte Gutscheinregeln (z.B. Mindestbestellwert, spezifische Kategorien, Gültigkeitsdauer) würden Sie diese typischerweise in PrestaShops nativen Bereichen „Katalogpreisregeln“ oder „Warenkorbregeln“ (Rabatte) verwalten, und das Modul würde einen Code generieren, der diesen Regeln entspricht, falls zutreffend, oder Sie müssten manuell eine spezifische Regel erstellen, die dem vom Modul generierten Gutschein entspricht. Das Modul selbst generiert einen einfachen prozentualen Rabatt.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen technischen Einblick in das Modul „Google Produkt-Plus-Button + Gutschein“ für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das Modul folgt einer Standard-PrestaShop-Modularchitektur, die hauptsächlich die `Module`-Klasse und ihre Methoden `install()`, `uninstall()` und `getContent()` nutzt. Es integriert sich über verschiedene Display-Hooks in das Front-Office, um den Google +1-Button und die zugehörige Gutscheinlogik einzufügen. Die Gutscheingenerierung und -anzeige werden dynamisch mit JavaScript und Smarty-Templates gehandhabt. Es gibt keine benutzerdefinierten `ObjectModel`-Klassen oder dedizierten Admin-Controller über die Hauptmodulkonfiguration hinaus.

### 4.2 Controller (`controllers/`)

- **Front-Office-Controller**: Keine. Alle Front-Office-Funktionalitäten werden über Modul-Hooks und direkte Template-Rendering gehandhabt.
- **Back-Office-Admin-Controller**: Keine. Die Konfiguration erfolgt vollständig innerhalb der `getContent()`-Methode des Hauptmoduls.

### 4.3 Kernklassen & Modelle (`classes/`)

- Es sind keine benutzerdefinierten Klassen oder `ObjectModel`-Definitionen im Verzeichnis `classes/` vorhanden. Die gesamte Kernlogik befindet sich in `googlecoupon/googlecoupon.php`.

### 4.4 JavaScript-Assets (`views/js/`)

- `googlecoupon/lib/voucherengine/script.js`
  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Dieses Skript ist wahrscheinlich für die Kernlogik der Gutscheingenerierung und -anzeige verantwortlich. Es würde auf das Klickereignis des Google +1-Buttons hören, den Gutscheingenerierungsprozess auslösen (möglicherweise über einen AJAX-Aufruf an die Hauptdatei des Moduls oder eine direkte JavaScript-Funktion) und dann den Gutscheincode dem Benutzer anzeigen. Es könnte auch die Interaktion mit der Google+-API handhaben (obwohl Google+-APIs weitgehend veraltet oder in andere Dienste integriert wurden).
- `googlecoupon/trusted.js`
  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Der Zweck dieses Skripts ist allein aus dem Namen weniger klar, aber es könnte sich auf die Sicherstellung der Integrität der +1-Aktion, das Tracking oder die Integration mit anderen vertrauenswürdigen Diensten beziehen. Es könnte auch ein Überbleibsel älterer Google+-API-Integrationen sein.

### 4.5 CSS-Stylesheets (`views/css/`)

- `googlecoupon/css.css`
  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Bietet das primäre Styling für den Google +1-Button, den Gutscheinanzeigebereich und alle zugehörigen Pop-ups oder Benachrichtigungen.
  - **Wichtige CSS-Klassenselektoren:** Entwickler sollten diese Datei überprüfen, um spezifische Klassen (z.B. `.googlecoupon-button-container`, `.googlecoupon-voucher-display`, `.googlecoupon-modal`) zu identifizieren, die in der `custom.css` oder `theme.css` eines benutzerdefinierten Themes überschrieben werden können, um dem Branding des Shops zu entsprechen.
- `googlecoupon/css/css.css`
  - **Geltungsbereich:** Front-Office.
  - **Verantwortlichkeit:** Dies scheint eine Duplikat- oder alternative Stylesheet zu sein. Es ist wichtig zu prüfen, ob beide geladen werden oder ob eine ein Fallback ist. Es würde wahrscheinlich ähnliche Styling-Regeln wie `googlecoupon/css.css` enthalten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**: Keine explizit aufgeführt, aber die `share.tpl` dient wahrscheinlich diesem Zweck.
- **Admin-Templates (`views/templates/admin/`)**: Keine.
- **Front-Office-Templates (`views/templates/front/`)**: Keine explizit aufgeführt, aber `share.tpl` ist das wichtigste Front-Office-Template.
  - `googlecoupon/share.tpl`
    - **Geltungsbereich:** Front-Office.
    - **Zweck:** Dieses Template ist für das Rendern des Google +1-Buttons und des Containers verantwortlich, in dem die Gutscheininformationen angezeigt werden. Es wird in die verschiedenen im Modul konfigurierten Front-Office-Hooks eingefügt. Es enthält wahrscheinlich Platzhalter für das Google+-Skript und den dynamisch generierten Gutscheincode.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Das Modul scheint keine benutzerdefinierten SQL-Tabellen zu erstellen.
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Schlüsseln wie `GC_VOUCHER`, `GC_SHOW_PRICES`, `GC_SHOW_TOTAL`, `GC_SHOW_PRODUCTS`, `GC_SHOW_PRODUCT_URL`, `GC_LASTTAB`, `GC_POSITION`, `GC_NBLIKES`, `GC_BUTTON_STYLE`, `GCSHARE_MODE` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayproductActions` | Auf der Produktseite, typischerweise in der Nähe des Buttons „In den Warenkorb“. | Fügt den Google +1-Button und die Gutscheinanzeige in einem prominenten Bereich ein. |
| `displayproductFooter` | Auf der Produktseite, am unteren Rand des Produktinformationsblocks. | Fügt den Google +1-Button und die Gutscheinanzeige nach den Hauptproduktdetails ein. |
| `productFooter` | Auf der Produktseite, ähnlich wie `displayproductFooter`, oft für zusätzliche Inhalte verwendet. | Alternative Platzierung für den Google +1-Button und die Gutscheinanzeige. |
| `extraLeft` | Auf der Produktseite, in der linken Spalte (falls vom Theme aktiviert). | Platziert den Modulinhalt in der linken Seitenleiste. |
| `productActions` | Auf der Produktseite, speziell um die Buttons „In den Warenkorb“ und die Mengenauswahl. | Alternative Platzierung für den Google +1-Button und die Gutscheinanzeige, oft sehr prominent. |
| `displayextraleft` | Auf der Produktseite, in der linken Spalte. | Ähnlich wie `extraLeft`, zum Einfügen von Inhalten in die linke Seitenleiste. |
| `extraRight` | Auf der Produktseite, in der rechten Spalte (falls vom Theme aktiviert). | Platziert den Modulinhalt in der rechten Seitenleiste. |
| `displayextraright` | Auf der Produktseite, in der rechten Spalte. | Ähnlich wie `extraRight`, zum Einfügen von Inhalten in die rechte Seitenleiste. |
| `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird verwendet, um notwendige CSS- und JavaScript-Dateien für das Modul einzubinden. |
| `header` | Im `<head>`-Bereich jeder Seite (ältere PrestaShop-Versionen). | Ähnlich wie `displayHeader`, zum Einbinden von Assets. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und zum Herunterladen der neuesten Versionen des Moduls „Google Produkt-Plus-Button + Gutschein“ melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Unser Support-Team steht Ihnen bei Fragen oder Problemen gerne zur Verfügung.

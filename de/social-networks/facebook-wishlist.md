---
title: "Facebook Wunschliste - Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Facebook Wunschliste von MyPresta.eu."
sidebar:
  label: "Facebook Wunschliste - Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook Wishlist auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-wishlist.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-wishlist/)
>
> ---


# Facebook Wunschliste

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und in der Regel standardmäßig verfügbar. Keine speziellen Hosting-Anforderungen über eine Standard-PrestaShop-Einrichtung hinaus.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Klicken Sie nach der Installation im Modul-Manager neben dem Facebook Wunschliste-Modul auf „Konfigurieren“. Dies führt Sie zum Hauptkonfigurationsbildschirm.

#### **Facebook App ID**

- **Was diese Einstellung bewirkt:** Dies ist eine eindeutige Kennung, die von Facebook für Ihre spezifische Anwendung (in diesem Fall die Integration Ihres PrestaShop-Shops mit Facebook) bereitgestellt wird. Sie teilt Facebook mit, welche App die Wunschlistenaktion anfordert.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Bei korrekter Eingabe:* Der Button „Zur Facebook Wunschliste hinzufügen“ funktioniert korrekt und ermöglicht das Hinzufügen von Produkten zu Facebook-Timelines.
  - *Bei falscher oder leerer Eingabe:* Der Button funktioniert wahrscheinlich nicht, oder Facebook zeigt einen Fehler an, der Kunden daran hindert, Produkte zu ihren Wunschlisten hinzuzufügen.
- **Empfohlener Wert:** Dieses Feld *muss* Ihre gültige Facebook App ID enthalten. Sie müssen eine Facebook App auf der [Facebook for Developers](https://developers.facebook.com/)-Website erstellen, um diese ID zu erhalten.
- **Händlerszenario / Beispiel:** Sie haben eine Facebook App für Ihren Shop erstellt, und Facebook hat Ihnen eine App ID wie `123456789012345` gegeben. Sie würden diese genaue Nummer hier eingeben. Ohne sie weiß Facebook nicht, welcher Shop Inhalte teilen möchte.

#### **Facebook App Secret**

- **Was diese Einstellung bewirkt:** Dies ist ein geheimer Schlüssel, der mit Ihrer Facebook App ID verknüpft ist. Er wird für die sichere Kommunikation zwischen Ihrem PrestaShop-Shop und den Facebook-Servern verwendet. Er hilft zu überprüfen, ob Anfragen von Ihrer legitimen Anwendung stammen.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Bei korrekter Eingabe:* Eine sichere Kommunikation wird hergestellt, und das Modul funktioniert wie vorgesehen.
  - *Bei falscher oder leerer Eingabe:* Die Kommunikation mit Facebook kann fehlschlagen, was zu Fehlern oder nicht funktionierenden Wunschlistenfunktionen führt.
- **Empfohlener Wert:** Dieses Feld *muss* Ihr gültiges Facebook App Secret enthalten. Wie die App ID erhalten Sie dies aus Ihren Facebook App-Einstellungen auf der [Facebook for Developers](https://developers.facebook.com/)-Website. Halten Sie dieses Geheimnis sicher und teilen Sie es niemals öffentlich.
- **Händlerszenario / Beispiel:** Nach dem Erstellen Ihrer Facebook App finden Sie sowohl die App ID als auch das App Secret in Ihrem App-Dashboard. Das Geheimnis könnte wie eine lange Zeichenfolge aus Buchstaben und Zahlen aussehen (z. B. `abcdef1234567890abcdef1234567890`). Geben Sie es genau so ein, wie es von Facebook bereitgestellt wird.

#### **Facebook Seiten-URL**

- **Was diese Einstellung bewirkt:** Dies ermöglicht es Ihnen, die offizielle Facebook-Seite Ihres Shops mit der Wunschlistenfunktion zu verknüpfen. Wenn Kunden mit der Wunschliste interagieren, kann dies manchmal auf Ihre Haupt-Facebook-Seite verweisen oder dorthin verlinken.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Bei korrekter Eingabe:* Verbessert die Markensichtbarkeit auf Facebook und bietet einen direkten Link zu Ihrer offiziellen Seite.
  - *Bei falscher oder leerer Eingabe:* Das Modul funktioniert weiterhin, aber Sie könnten eine Gelegenheit verpassen, Benutzer auf Ihre Haupt-Facebook-Präsenz zu leiten.
- **Empfohlener Wert:** Geben Sie die vollständige URL der offiziellen Facebook-Seite Ihres Shops ein (z. B. `https://www.facebook.com/IhrShopName`). Wenn Sie keine offizielle Seite haben, können Sie dieses Feld leer lassen.
- **Händlerszenario / Beispiel:** Ihr Shop hat eine Facebook-Seite unter `https://www.facebook.com/MyPrestaEu`. Die Eingabe dieser URL hier stellt sicher, dass jede soziale Freigabe im Zusammenhang mit der Wunschliste Benutzer potenziell auf Ihre Hauptmarkenseite auf Facebook leiten kann.

#### **Position des Buttons**

- **Was diese Einstellung bewirkt:** Dies steuert, wo der Button „Zur Facebook Wunschliste hinzufügen“ auf Ihren Produktseiten erscheint.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn auf „Produktseite“ eingestellt:* Der Button wird prominent auf der Produktdetailseite angezeigt, typischerweise in der Nähe des „In den Warenkorb“-Buttons. Dies ist die häufigste und empfohlene Platzierung.
  - *Wenn auf andere Optionen eingestellt (z. B. „Header“, „Spalten“, „Footer“):* Das Modul könnte versuchen, den Button in diesen Bereichen anzuzeigen, aber seine Funktionalität ist primär an spezifische Produktinformationen gebunden, was „Produktseite“ zur logischsten Wahl macht. Andere Positionen zeigen den Button möglicherweise nicht an oder funktionieren ohne spezifischen Produktkontext nicht korrekt.
- **Empfohlener Wert:** **Produktseite**. Dies stellt sicher, dass der Button sichtbar ist, wenn Kunden aktiv ein Produkt ansehen, das sie auf ihre Wunschliste setzen möchten.
- **Händlerszenario / Beispiel:** Sie möchten, dass Kunden den Wunschlisten-Button leicht finden, wenn sie gerade über den Kauf eines Produkts nachdenken. Wenn Sie dies auf „Produktseite“ einstellen, wird er logisch neben anderen kaufbezogenen Aktionen platziert.

#### **Button auf Produktseite anzeigen**

- **Was diese Einstellung bewirkt:** Dies ist ein einfacher EIN/AUS-Schalter, um die Anzeige des Buttons „Zur Facebook Wunschliste hinzufügen“ auf Ihren Produktseiten zu aktivieren oder zu deaktivieren.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Der Button ist auf allen Produktseiten sichtbar und funktionsfähig.
  - *Wenn deaktiviert (NEIN):* Der Button wird ausgeblendet, und Kunden können über Ihren Shop keine Produkte zu ihren Facebook-Wunschlisten hinzufügen.
- **Empfohlener Wert:** **JA**. Um die Kernfunktionalität des Moduls zu nutzen, sollte dies immer aktiviert sein.
- **Händlerszenario / Beispiel:** Sie haben die gesamte Einrichtung abgeschlossen und möchten, dass Ihre Kunden die Funktion nutzen. Sie würden dies auf JA setzen. Wenn Sie die Funktion vorübergehend für Wartungsarbeiten oder eine Kampagne ausblenden möchten, könnten Sie sie auf NEIN setzen.

#### **Button auf Kategorieseite anzeigen**

- **Was diese Einstellung bewirkt:** Dies steuert, ob der Button „Zur Facebook Wunschliste hinzufügen“ bei Produktlisten auf Kategorieseiten erscheint.
- **Auswirkung einer Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Ein Wunschlisten-Button erscheint neben jedem Produkt auf Kategorie- und Listenseiten. Dies kann für schnelles Hinzufügen zur Wunschliste nützlich sein, könnte aber je nach Ihrem Theme das Layout überladen.
  - *Wenn deaktiviert (NEIN):* Der Button erscheint nur auf den einzelnen Produktseiten, wodurch die Kategorieseiten sauberer bleiben.
- **Empfohlener Wert:** **NEIN**. Obwohl potenziell nützlich, kann die Anzeige des Buttons auf Kategorieseiten manchmal zu einer weniger optimalen Benutzererfahrung oder visueller Unordnung führen. Es ist im Allgemeinen auf der dedizierten Produktseite effektiver.
- **Händlerszenario / Beispiel:** Sie haben ein sehr sauberes Kategorieseiten-Design und möchten Ablenkungen minimieren. Sie würden dies auf NEIN setzen, um sicherzustellen, dass die Wunschlistenaktion nur verfügbar ist, wenn ein Kunde sich auf ein einzelnes Produkt konzentriert.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Facebook App ID | Ihre Facebook App ID | Eindeutige Kennung für die Facebook-Integration Ihres Shops. **Entscheidend für die Funktionalität.** |
| Modulkonfiguration | Facebook App Secret | Ihr Facebook App Secret | Sicherer Schlüssel für die Kommunikation mit Facebook. **Entscheidend für die Funktionalität.** |
| Modulkonfiguration | Facebook Seiten-URL | `https://www.facebook.com/IhrShopName` (falls zutreffend) | Verlinkt zu Ihrer offiziellen Facebook-Seite, verbessert die Markensichtbarkeit. |
| Modulkonfiguration | Position des Buttons | Produktseite | Bestimmt, wo der Wunschlisten-Button erscheint. **Produktseite wird empfohlen.** |
| Modulkonfiguration | Button auf Produktseite anzeigen | JA | Aktiviert/deaktiviert den Button auf einzelnen Produktseiten. **Empfohlen: JA.** |
| Modulkonfiguration | Button auf Kategorieseite anzeigen | NEIN | Aktiviert/deaktiviert den Button bei Produktlisten auf Kategorieseiten. **Empfohlen: NEIN.** |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Der Button „Zur Facebook Wunschliste hinzufügen“ erscheint nicht auf meinen Produktseiten.**
A:

- **Modulstatus prüfen:** Stellen Sie sicher, dass das Modul unter **Module > Modul-Manager** installiert und aktiviert ist.
- **Konfigurationseinstellungen:** Gehen Sie zur Konfigurationsseite des Moduls und überprüfen Sie, ob „Button auf Produktseite anzeigen“ auf **JA** eingestellt ist.
- **Facebook App ID/Secret:** Überprüfen Sie nochmals, ob Ihre Facebook App ID und Ihr App Secret korrekt eingegeben wurden. Falsche Anmeldeinformationen verhindern das Laden oder Funktionieren des Buttons.
- **Theme-Kompatibilität:** Einige stark angepasste Themes erfordern möglicherweise geringfügige Anpassungen. Wenn der Button immer noch nicht erscheint, versuchen Sie, vorübergehend zum Standard-PrestaShop-Theme (Classic) zu wechseln, um einen Theme-Konflikt auszuschließen. Wenn er auf Classic erscheint, muss Ihr Theme-Entwickler ihn möglicherweise integrieren.
- **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache (**Erweiterte Einstellungen > Leistung**) und Ihren Browser-Cache, nachdem Sie Konfigurationsänderungen vorgenommen haben.

**F2: Der Button erscheint, aber es passiert nichts, wenn ich ihn anklicke, oder ich erhalte einen Facebook-Fehler.**
A:

- **Facebook App ID/Secret:** Dies liegt fast immer an einer falschen oder fehlenden Facebook App ID oder einem App Secret. Überprüfen Sie Ihre Facebook for Developers App-Einstellungen und stellen Sie sicher, dass die Werte genau kopiert wurden.
- **Facebook App-Einstellungen:** Stellen Sie auf der Facebook for Developers-Plattform sicher, dass Ihre App „Live“ ist (nicht im Entwicklungsmodus) und dass die „Website“-Plattform mit der korrekt konfigurierten URL Ihres Shops hinzugefügt wurde.
- **Domain-Whitelisting:** Stellen Sie in Ihren Facebook App-Einstellungen unter „Einstellungen > Grundlegend“ sicher, dass die Domain Ihrer Website im Feld „App-Domains“ aufgeführt ist.
- **Open Graph Tags:** Das Modul verwendet die Standard-Open Graph Meta-Tags von PrestaShop für Produktinformationen. Stellen Sie sicher, dass Ihr PrestaShop-Shop diese korrekt generiert (Sie können den Quellcode Ihrer Produktseite auf `<meta property="og:..."` Tags überprüfen).

**F3: Wie erhalte ich eine Facebook App ID und ein App Secret?**
A:

1. Gehen Sie zu [Facebook for Developers](https://developers.facebook.com/) und melden Sie sich mit Ihrem Facebook-Konto an.
2. Klicken Sie auf „Meine Apps“ > „App erstellen“.
3. Wählen Sie den App-Typ (z. B. „Verbraucher“ oder „Unternehmen“) und folgen Sie den Anweisungen, um Ihrer App einen Namen zu geben.
4. Nach der Erstellung navigieren Sie zu „Einstellungen > Grundlegend“ in Ihrem neuen App-Dashboard.
5. Dort finden Sie Ihre **App ID** und Ihr **App Secret**.
6. Stellen Sie sicher, dass Sie die Domain Ihrer Website (z. B. `ihrshop.de`) zum Feld „App-Domains“ hinzufügen und die Änderungen speichern.
7. Fügen Sie Ihrer App eine „Website“-Plattform hinzu und geben Sie Ihre Website-URL ein.
8. Stellen Sie schließlich sicher, dass Ihre App auf den „Live“-Modus eingestellt ist (es gibt normalerweise einen Umschalter oben im Dashboard).

**F4: Wird dieses Modul meine Website verlangsamen?**
A: Das Modul selbst ist sehr leichtgewichtig. Die primäre Interaktion ist ein kleiner Button und ein von Facebook gehostetes Pop-up, das Inhalte direkt von Facebook-Servern lädt. Eine wahrgenommene Verlangsamung hängt eher mit den Ladezeiten von Facebook selbst oder allgemeinen Problemen mit der Website-Leistung zusammen als mit dem Modul selbst.

**F5: Kann ich das Erscheinungsbild des Buttons anpassen?**
A: Das Modul verwendet typischerweise das Standard-Facebook-Button-Styling oder integriert sich in die vorhandenen Button-Stile Ihres Themes. Obwohl es keine direkte Einstellung im Modul gibt, um sein Erscheinungsbild zu ändern, kann ein Webentwickler es mithilfe von CSS anpassen, indem er die spezifischen CSS-Klassen oder IDs des Button-Elements anspricht.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Facebook Wunschliste-Modul (`facebook-wishlist`) ist ein unkompliziertes PrestaShop-Modul, das hauptsächlich dazu dient, Open Graph-basierte „Zur Wunschliste hinzufügen“-Funktionalität in das Front-Office zu integrieren. Es nutzt das Hook-System von PrestaShop, um seinen Button auf Produktseiten zu rendern, und verlässt sich auf das JavaScript SDK von Facebook und das Open Graph-Protokoll für seine Kernfunktionalität. Die Konfiguration des Moduls wird über die Standardmethode `getContent()` in der Hauptmoduldatei verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden.

### 4.2 Controller (`controllers/`)

Dieses Modul verwendet keine benutzerdefinierten Front-Office- oder Back-Office-Controller. Die gesamte Logik ist in der Hauptmoduldatei und ihrer Konfiguration gekapselt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`s. Die gesamte Konfiguration wird über `Configuration::get()` und `Configuration::updateValue()` gehandhabt.

### 4.4 JavaScript-Assets (`views/js/`)

Dieses Modul enthält keine benutzerdefinierten JavaScript-Dateien. Es verlässt sich auf das Facebook JavaScript SDK, das typischerweise asynchron geladen und von Facebook selbst verwaltet wird, sobald die korrekten Open Graph Meta-Tags und die App ID vorhanden sind.

### 4.5 CSS-Stylesheets (`views/css/`)

Dieses Modul enthält keine benutzerdefinierten CSS-Dateien. Das Erscheinungsbild des Buttons wird entweder durch das Standard-Styling von Facebook für seine sozialen Plugins oder durch die Vererbung von Stilen des aktiven PrestaShop-Themes gehandhabt.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

Dieses Modul enthält kein `views/templates`-Verzeichnis. Der Button-HTML wird wahrscheinlich direkt in den Hook-Methoden der Hauptmoduldatei generiert.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:
  Dieses Modul erstellt keine benutzerdefinierten Datenbanktabellen. Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Verwendung von Schlüsseln wie `FACEBOOK_WISHLIST_APP_ID`, `FACEBOOK_WISHLIST_APP_SECRET`, `FACEBOOK_WISHLIST_PAGE_URL`, `FACEBOOK_WISHLIST_BUTTON_POSITION`, `FACEBOOK_WISHLIST_SHOW_PRODUCT_PAGE` und `FACEBOOK_WISHLIST_SHOW_CATEGORY_PAGE` gespeichert.
- **Registrierte Hooks-Tabelle**:
  Das Modul registriert und verwendet die folgenden PrestaShop-Hooks:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayHeader` | Im `<head>`-Bereich jeder Seite. | Wird verwendet, um den Initialisierungscode des Facebook JavaScript SDK und Open Graph Meta-Tags (falls nicht bereits durch den PrestaShop-Kern vorhanden) einzufügen. Dies ist entscheidend, damit Facebook Ihre Website und App erkennt. |
  | `displayProductButtons` | Auf der Produktseite, typischerweise in der Nähe des „In den Warenkorb“-Buttons. | Rendert den Button „Zur Facebook Wunschliste hinzufügen“. Dies ist der primäre Hook für die Front-Office-Anzeige des Moduls. |
  | `displayProductListFunctionalButtons` | Auf Kategorie-/Listenseiten, neben jedem Produkt. | Rendert den Button „Zur Facebook Wunschliste hinzufügen“ für Produkte in Listen, falls in der Konfiguration aktiviert. |
  | `displayFooter` | Im Footer jeder Seite. | Potenziell für zusätzliches Skriptladen oder Fallback-Button-Platzierung verwendet, obwohl `displayProductButtons` der Haupt-Hook ist. |
  | `displayLeftColumn` | In der linken Spalte von Seiten. | Alternative Position für den Button, falls konfiguriert. |
  | `displayRightColumn` | In der rechten Spalte von Seiten. | Alternative Position für den Button, falls konfiguriert. |

  Die Kernfunktionalität des Moduls basiert auf dem `displayHeader`-Hook, um sicherzustellen, dass das Facebook SDK geladen wird, und dem `displayProductButtons`- (oder `displayProductListFunctionalButtons`-) Hook, um den interaktiven Button zu rendern. Der Button selbst löst beim Klicken die Facebook Open Graph `og:product:wishlist`-Aktion aus, die spezifische Open Graph Meta-Tags (wie `og:title`, `og:description`, `og:image`, `og:url`, `og:type=product`) im HTML der Produktseite erfordert. PrestaShop generiert diese Tags typischerweise standardmäßig.

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Facebook Wunschliste-Modul verweisen wir Sie auf Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Integration des Moduls zur Verfügung.

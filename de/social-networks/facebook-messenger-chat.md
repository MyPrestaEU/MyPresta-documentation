---
title: "Facebook Messenger Chat – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul Facebook Messenger Chat von MyPresta.eu."
sidebar:
  label: "Facebook Messenger Chat – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Facebook Messenger chat auf MyPresta.eu kaufen](https://mypresta.eu/modules/social-networks/facebook-messenger-chat.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/social-networks/facebook-messenger-chat/)
>
> ---


# Facebook Messenger Chat

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise für PrestaShop selbst erforderlich und auf allen modernen Hosting-Umgebungen verfügbar. Für dieses Modul sind keine speziellen Erweiterungen über die Standard-PrestaShop-Anforderungen hinaus erforderlich.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für Ihr Facebook Messenger Chat-Modul. Hier finden Sie alle Optionen, um das Erscheinungsbild und die Funktion des Chats in Ihrem Store anzupassen.

- **Was diese Einstellung bewirkt:** Dies ist eine allgemeine Einstellung für MyPresta.eu-Module, um nach Updates zu suchen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (An):* Das Modul sucht regelmäßig auf MyPresta.eu nach neuen Versionen.
  - *Wenn deaktiviert (Aus):* Das Modul sucht nicht nach Updates.
- **Empfohlener Wert:** **An** (Es ist immer gut, für Sicherheit und neue Funktionen auf dem neuesten Stand zu bleiben).
- **Händlerszenario / Beispiel:** Wenn diese Option aktiviert ist, werden Sie benachrichtigt, wenn eine neue Version mit Fehlerbehebungen oder neuen Funktionen verfügbar ist, was Ihrem Store hilft, aktuell und sicher zu bleiben.

---

- **Was diese Einstellung bewirkt:** Diese Option ermöglicht es Ihnen, zwischen zwei Arten der Facebook-Chat-Integration zu wählen: einem einfachen Facebook-Seiten-Chat oder dem fortschrittlicheren Facebook Messenger Chat.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Facebook Seiten-Chat“ eingestellt:* Ein einfacheres Chat-Widget wird angezeigt, hauptsächlich zum Senden von Nachrichten an Ihre Facebook-Seite.
  - *Wenn auf „Facebook Messenger Chat“ eingestellt:* Das voll ausgestattete Facebook Messenger Chat-Widget wird angezeigt, das ein reichhaltigeres Konversationserlebnis bietet, einschließlich Begrüßungsnachrichten und potenziell fortgeschrittenerer Funktionen von Facebook.
- **Empfohlener Wert:** **Facebook Messenger Chat** (Bietet ein besseres Benutzererlebnis und mehr Funktionen).
- **Händlerszenario / Beispiel:** Wenn Sie das volle, interaktive Messenger-Erlebnis mit Begrüßungsnachrichten wünschen, wählen Sie „Facebook Messenger Chat“. Wenn Sie einen sehr einfachen, leichten Nachrichtensender bevorzugen, könnte „Facebook Seiten-Chat“ ausreichen.

---

- **Was diese Einstellung bewirkt:** Diese Einstellung hilft, die Leistungsbewertungen Ihres Stores bei Tools wie Google PageSpeed Insights zu verbessern, indem sie verhindert, dass der Facebook-Chat sofort geladen wird, was manchmal das Rendern Ihrer Seite blockieren kann.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (An):* Das Facebook-Chat-Skript wird mit einer leichten Verzögerung oder auf nicht-blockierende Weise geladen, was Ihre Google PageSpeed-Werte verbessern kann.
  - *Wenn deaktiviert (Aus):* Das Facebook-Chat-Skript wird normal geladen, was die Leistungskennzahlen der Seitenladezeit leicht beeinträchtigen könnte.
- **Empfohlener Wert:** **An** (Empfohlen für besseres SEO und Benutzererlebnis).
- **Händlerszenario / Beispiel:** Wenn Sie sich um die Leistungsmetriken Ihres Stores sorgen und sicherstellen möchten, dass der Chat diese nicht negativ beeinflusst, aktivieren Sie diese Option.

---

- **Was diese Einstellung bewirkt:** Dies steuert, ob das Facebook Application SDK (Software Development Kit) auf Ihrer Website enthalten ist. Das SDK ist für die volle Funktionalität des Facebook Messenger Chats notwendig, insbesondere für Funktionen wie die Identifizierung eingeloggter Benutzer.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (An):* Das Facebook SDK wird geladen, wodurch alle Messenger-Chat-Funktionen aktiviert werden.
  - *Wenn deaktiviert (Aus):* Einige erweiterte Messenger-Funktionen, insbesondere solche, die mit der Benutzeridentifizierung und personalisierten Begrüßungen zusammenhängen, funktionieren möglicherweise nicht korrekt.
- **Empfohlener Wert:** **An** (Erforderlich für die volle Messenger-Chat-Funktionalität).
- **Händlerszenario / Beispiel:** Wenn der Chat erkennen soll, ob ein Kunde bei Facebook angemeldet ist und eine personalisierte Begrüßung anzeigen soll, müssen Sie diese Option aktivieren.

---

- **Was diese Einstellung bewirkt:** Dies ist Ihre eindeutige Kennung für Ihre Facebook-Anwendung. Sie müssen eine Facebook-App auf der Facebook Developers-Website erstellen, um diese ID zu erhalten. Sie verknüpft Ihre Website mit Ihrer Facebook-Seite für erweiterte Messenger-Funktionen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Bei korrekter Eingabe:* Aktiviert die volle Funktionalität des Facebook Messenger Chats, einschließlich personalisierter Begrüßungen und potenziell genauerer Benutzeridentifizierung.
  - *Bei falscher oder leerer Eingabe:* Der Messenger-Chat funktioniert möglicherweise nicht korrekt oder überhaupt nicht.
- **Empfohlener Wert:** Ihre tatsächliche **Facebook App ID**. (Leer lassen, wenn „Facebook Application SDK einbinden“ auf Aus steht).
- **Händlerszenario / Beispiel:** Um die erweiterten Messenger-Chat-Funktionen zu nutzen, müssen Sie zu [developers.facebook.com](https://developers.facebook.com/) gehen, eine App erstellen, diese mit Ihrer Facebook-Seite verknüpfen und dann die App-ID hierher kopieren.

---

- **Was diese Einstellung bewirkt:** Dies ermöglicht Ihnen, die Sprache für die Benutzeroberfläche des Facebook Messenger Chats festzulegen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein Sprachcode ausgewählt ist:* Das Chat-Widget zeigt Text (wie „Senden Sie uns eine Nachricht“) in der gewählten Sprache an.
  - *Wenn leer oder falsch:* Der Chat könnte standardmäßig auf Englisch oder die Browsersprache zurückfallen.
- **Empfohlener Wert:** Wählen Sie die primäre Sprache Ihres Stores, z.B. `de_DE` für Deutsch (Deutschland), `en_US` für Englisch (Vereinigte Staaten), `fr_FR` für Französisch (Frankreich), `es_ES` für Spanisch (Spanien).
- **Händlerszenario / Beispiel:** Wenn Ihr Store hauptsächlich Kunden in Deutschland bedient, stellt die Einstellung auf `de_DE` sicher, dass die Chat-Oberfläche auf Deutsch ist, was sie für Ihre lokalen Kunden benutzerfreundlicher macht.

---

- **Was diese Einstellung bewirkt:** Dies ist die URL zu Ihrer Facebook-Fanpage. Dies ist entscheidend, da es dem Chat-Widget mitteilt, wohin Nachrichten gesendet werden sollen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Bei korrekter Eingabe:* Nachrichten, die über das Chat-Widget gesendet werden, gelangen direkt in den Posteingang Ihrer Facebook-Seite.
  - *Bei falscher oder leerer Eingabe:* Das Chat-Widget kann keine Verbindung zu Ihrer Seite herstellen, und Nachrichten werden nicht zugestellt.
- **Empfohlener Wert:** Die vollständige URL zu Ihrer Facebook-Fanpage, z.B. `https://www.facebook.com/MyPresta.eu`.
- **Händlerszenario / Beispiel:** Wenn Ihre Facebook-Seite `https://www.facebook.com/MeinTollerShop/` ist, würden Sie diese URL hier eingeben, damit Kunden Sie erreichen können.

---

- **Was diese Einstellung bewirkt:** Dies ist die anfängliche Nachricht, die Kunden angezeigt wird, die bereits bei Facebook angemeldet sind, wenn sie den Chat öffnen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn festgelegt:* Angemeldete Kunden sehen diese personalisierte Begrüßung, was die Interaktion einladender macht.
  - *Wenn leer:* Eine Standard-Facebook-Begrüßung könnte verwendet werden, oder es erscheint keine Begrüßung.
- **Empfohlener Wert:** Eine freundliche, prägnante Begrüßung, z.B. „Hallo [Kundenname], wie können wir Ihnen heute helfen?“
- **Händlerszenario / Beispiel:** Sie könnten dies auf „Willkommen zurück! Wie können wir Ihnen heute beim Einkaufen helfen?“ setzen, um wiederkehrenden Kunden das Gefühl zu geben, geschätzt zu werden.

---

- **Was diese Einstellung bewirkt:** Dies ist die anfängliche Nachricht, die Kunden angezeigt wird, die NICHT bei Facebook angemeldet sind, wenn sie den Chat öffnen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn festgelegt:* Nicht angemeldete Kunden sehen diese Begrüßung, die sie ermutigt, eine Konversation zu beginnen.
  - *Wenn leer:* Eine Standard-Facebook-Begrüßung könnte verwendet werden, oder es erscheint keine Begrüßung.
- **Empfohlener Wert:** Eine klare, einladende Nachricht, z.B. „Hallo! Wir sind hier, um zu helfen. Fragen Sie uns alles!“
- **Händlerszenario / Beispiel:** Für neue Besucher könnten Sie „Hallo! Haben Sie eine Frage zu unseren Produkten? Chatten Sie mit uns!“ verwenden.

---

- **Was diese Einstellung bewirkt:** Dies ist die numerische ID Ihrer Facebook-Seite. Sie finden diese im Abschnitt „Info“ Ihrer Facebook-Seite oder mithilfe eines Facebook-Seiten-ID-Finder-Tools. Sie ist unerlässlich, um das Chat-Widget mit Ihrer spezifischen Seite zu verknüpfen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Bei korrekter Eingabe:* Das Chat-Widget identifiziert und verbindet sich korrekt mit Ihrer Facebook-Seite.
  - *Bei falscher oder leerer Eingabe:* Das Chat-Widget funktioniert nicht, da es nicht weiß, mit welcher Seite es sich verbinden soll.
- **Empfohlener Wert:** Ihre tatsächliche **Facebook-Seiten-ID**.
- **Händlerszenario / Beispiel:** Wenn Ihre Facebook-Seiten-ID `123456789012345` ist, würden Sie diese Nummer hier eingeben. Dies ist von der App-ID zu unterscheiden.

---

- **Was diese Einstellung bewirkt:** Dies steuert die Position des Chat-Widgets auf Ihrer Website.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Links“ eingestellt:* Das Chat-Symbol/Panel erscheint auf der unteren linken Seite Ihres Bildschirms.
  - *Wenn auf „Rechts“ eingestellt:* Das Chat-Symbol/Panel erscheint auf der unteren rechten Seite Ihres Bildschirms.
- **Empfohlener Wert:** **Rechts** (Dies ist eine gängige und oft weniger aufdringliche Position, da viele Websites Navigationen oder andere Elemente auf der linken Seite haben).
- **Händlerszenario / Beispiel:** Wenn die Hauptnavigation Ihrer Website oder ein wichtiges Banner links ist, würden Sie „Rechts“ wählen, um eine Verdeckung zu vermeiden.

---

- **Was diese Einstellung bewirkt:** Dies ist der Text, der als Titel des Chatfensters oder des ausklappbaren Panels erscheint, bevor eine Konversation beginnt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn festgelegt:* Kunden sehen diesen Titel, der klar angibt, wofür der Chat ist.
  - *Wenn leer:* Ein Standardtitel könnte verwendet werden, oder es erscheint kein Titel, was verwirrend sein kann.
- **Empfohlener Wert:** Ein klarer und einladender Titel, z.B. „Chatten Sie mit uns!“, „Kundensupport“ oder „Fragen?“.
- **Händlerszenario / Beispiel:** Wenn Sie dies auf „Brauchen Sie Hilfe?“ setzen, wird den Kunden klar, dass sie über den Chat Unterstützung erhalten können.

---

- **Was diese Einstellung bewirkt:** Dies ermöglicht Ihnen, die Farbe des Textes innerhalb des Facebook Chat-Widgets anzupassen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein Farbcode eingegeben wird:* Der Text im Chat-Widget wird in der gewählten Farbe angezeigt.
  - *Wenn leer:* Die Standard-Textfarbe des Facebook Messengers wird verwendet.
- **Empfohlener Wert:** Wählen Sie eine Farbe, die gut mit Ihrer Hintergrundfarbe kontrastiert und zu Ihrer Marke passt. Verwenden Sie einen hexadezimalen Farbcode (z.B. `#FFFFFF` für Weiß, `#000000` für Schwarz).
- **Händlerszenario / Beispiel:** Wenn Ihre Markenfarben Dunkelblau und Weiß sind, könnten Sie die Schriftfarbe auf `#FFFFFF` (Weiß) setzen, wenn Ihre Hintergrundfarbe Dunkelblau ist.

---

- **Was diese Einstellung bewirkt:** Dies ermöglicht Ihnen, die Hintergrundfarbe des Facebook Chat-Widgets anzupassen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein Farbcode eingegeben wird:* Der Hintergrund des Chat-Widgets wird in der gewählten Farbe angezeigt.
  - *Wenn leer:* Die Standard-Hintergrundfarbe des Facebook Messengers wird verwendet.
- **Empfohlener Wert:** Wählen Sie eine Farbe, die das Design Ihres Stores ergänzt. Verwenden Sie einen hexadezimalen Farbcode (z.B. `#F0F2F5` für Hellgrau, `#3B5998` für Facebook-Blau).
- **Händlerszenario / Beispiel:** Um den Chat nahtlos in das Design Ihres Stores zu integrieren, könnten Sie die Hintergrundfarbe auf ein dezentes Grau oder eine Farbe aus Ihrer Markenpalette setzen.

---

- **Was diese Einstellung bewirkt:** Dies ermöglicht Ihnen, die Hauptakzentfarbe des Facebook Messenger Chats anzupassen, z.B. die Senden-Schaltfläche oder aktive Elemente.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn ein Farbcode eingegeben wird:* Wichtige interaktive Elemente im Chat-Widget werden in der gewählten Farbe angezeigt.
  - *Wenn leer:* Die Standard-Akzentfarbe des Facebook Messengers (typischerweise Facebook-Blau) wird verwendet.
- **Empfohlener Wert:** Wählen Sie eine Farbe, die mit der primären oder sekundären Akzentfarbe Ihrer Marke übereinstimmt. Verwenden Sie einen hexadezimalen Farbcode (z.B. `#1877F2` für Facebook-Blau oder die Call-to-Action-Farbe Ihrer Marke).
- **Händlerszenario / Beispiel:** Wenn die Call-to-Action-Schaltflächen Ihres Stores grün sind, wird das Chat-Widget durch die Einstellung auf ein ähnliches Grün (`#28A745`) besser in Ihre Website integriert.

---

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | MyPresta.eu Updates | An | Aktiviert Modul-Update-Prüfungen für Sicherheit und Funktionen. |
| Modulkonfiguration | Art des Chats | Facebook Messenger Chat | Wählt zwischen einfachem Facebook-Seiten-Chat und vollem Messenger-Erlebnis. |
| Modulkonfiguration | Chat für Google Insights deaktivieren | An | Verbessert PageSpeed-Werte durch verzögertes Laden des Chat-Skripts. |
| Modulkonfiguration | Facebook Application SDK einbinden | An | Aktiviert erweiterte Messenger-Funktionen wie personalisierte Begrüßungen. |
| Modulkonfiguration | Ihre APP ID | Ihre Facebook App ID | Verknüpft Ihre Website mit Ihrer Facebook App für volle Messenger-Funktionalität. |
| Modulkonfiguration | Facebook APP Sprachcodes | `de_DE` (oder die Sprache Ihres Stores) | Legt die Sprache für die Chat-Oberfläche fest. |
| Modulkonfiguration | URL zur Facebook Fanpage (Nachrichtenempfänger) | Ihre Facebook Seiten-URL | Leitet Kundennachrichten an den Posteingang Ihrer Facebook-Seite. |
| Modulkonfiguration | Begrüßungsnachricht für angemeldete Benutzer | „Hallo [Kundenname], wie können wir Ihnen heute helfen?“ | Personalisierte Begrüßung für bei Facebook angemeldete Benutzer. |
| Modulkonfiguration | Begrüßungsnachricht für nicht angemeldete Benutzer | „Hallo! Wir sind hier, um zu helfen. Fragen Sie uns alles!“ | Einladende Nachricht für Benutzer, die nicht bei Facebook angemeldet sind. |
| Modulkonfiguration | Ihre Facebook Seiten-ID | Ihre Facebook Seiten-ID | Identifiziert Ihre spezifische Facebook-Seite für die Chat-Verbindung. |
| Modulkonfiguration | Wo anzeigen? | Rechts | Positioniert das Chat-Widget auf der linken oder rechten Seite des Bildschirms. |
| Modulkonfiguration | Titel des ausklappbaren Panels | „Chatten Sie mit uns!“ | Text, der als Titel des Chatfensters angezeigt wird. |
| Modulkonfiguration | Facebook Chat Schriftfarbe | `#000000` (Schwarz) oder Ihre Markenfarbe | Passt die Textfarbe innerhalb des Chat-Widgets an. |
| Modulkonfiguration | Facebook Chat Hintergrundfarbe | `#F0F2F5` (Hellgrau) oder Ihre Markenfarbe | Passt die Hintergrundfarbe des Chat-Widgets an. |
| Modulkonfiguration | Facebook Messenger Farbe | `#1877F2` (Facebook-Blau) oder Ihre Markenfarbe | Passt die Akzentfarbe interaktiver Chat-Elemente an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Das Chat-Widget wird in meinem Store nicht angezeigt. Was soll ich tun?**
A:

1. **Modulstatus überprüfen:** Gehen Sie zu **Module > Modul-Manager** und stellen Sie sicher, dass das Modul „Facebook Messenger Chat“ installiert und aktiviert ist.
2. **Konfiguration überprüfen:** Überprüfen Sie alle Einstellungen auf der Konfigurationsseite des Moduls, insbesondere „Ihre APP ID“, „URL zur Facebook Fanpage“ und „Ihre Facebook Seiten-ID“. Schon ein einziges falsches Zeichen kann die Funktion beeinträchtigen.
3. **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder „Smarty-Cache leeren“ in älteren Versionen). Manchmal verhindern alte Cache-Dateien die Anzeige neuer Module.
4. **Theme-Kompatibilität:** Wenn Sie ein stark angepasstes Theme verwenden, könnte es zu einem Konflikt kommen. Wechseln Sie vorübergehend zum Standard-PrestaShop-Theme, um zu sehen, ob der Chat erscheint. Wenn ja, benötigt Ihr Theme möglicherweise eine kleine Anpassung.

**F: Meine Begrüßungsnachrichten werden nicht angezeigt, oder der Chat erkennt angemeldete Benutzer nicht.**
A:

1. **SDK aktivieren:** Stellen Sie sicher, dass „Facebook Application SDK einbinden“ auf **An** gesetzt ist.
2. **APP ID angeben:** Stellen Sie sicher, dass „Ihre APP ID“ korrekt eingegeben ist. Sie müssen eine Facebook-App erstellen und diese mit Ihrer Seite verknüpfen, um diese zu erhalten.
3. **Facebook-Login:** Der Kunde muss in seinem Browser bei Facebook angemeldet sein, damit die personalisierte Begrüßung funktioniert.

**F: Das Chat-Widget sieht fehl am Platz aus oder passt nicht zum Design meines Stores.**
A:

1. **Farbeinstellungen verwenden:** Gehen Sie zur Modulkonfiguration und passen Sie „Facebook Chat Schriftfarbe“, „Facebook Chat Hintergrundfarbe“ und „Facebook Messenger Farbe“ an die Farbpalette Ihrer Marke an.
2. **Positionierung:** Experimentieren Sie mit der Einstellung „Wo anzeigen?“ (Links/Rechts), um die am wenigsten aufdringliche Position für Ihre Website zu finden.

**F: Wie finde ich meine Facebook Seiten-ID und App-ID?**
A:

- **Facebook Seiten-ID:** Gehen Sie zu Ihrer Facebook-Seite, klicken Sie im linken Menü auf „Info“. Scrollen Sie nach unten, und Sie sollten „Seiten-ID“ sehen.
- **Facebook App-ID:** Sie müssen ein Facebook-Entwicklerkonto erstellen und dann eine neue App erstellen. Nach der Erstellung ist die App-ID in Ihrem App-Dashboard sichtbar. Stellen Sie sicher, dass Sie diese App mit Ihrer Facebook-Seite verknüpfen.

**F: Wird dieses Modul meine Website verlangsamen?**
A: Das Facebook SDK kann manchmal die Ladezeiten der Seite beeinflussen. Das Modul enthält jedoch die Option „Chat für Google Insights deaktivieren“. Wenn Sie diese aktivieren, können Leistungseinbußen gemindert werden, indem das Skript nicht-blockierend geladen wird, was Ihre PageSpeed-Werte verbessert.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt bietet einen detaillierten technischen Überblick für Entwickler und Webmaster.

### 4.1 Architekturübersicht

Das `Facebook Messenger chat`-Modul (`fbchat`) ist ein Standard-PrestaShop-Modul, das ein MVC-ähnliches Muster im Rahmen des Moduls befolgt. Es nutzt hauptsächlich das Hook-System von PrestaShop, um JavaScript und HTML in das Front-Office zu injizieren. Die Konfiguration wird über die Methode `getContent()` in der Hauptmodulklasse verwaltet, wobei die Einstellungen in `ps_configuration` gespeichert werden. Das Modul integriert sich direkt in das Facebook Messenger Platform SDK und stützt sich für seine Kernfunktionalität auf externe Facebook-Ressourcen.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält **keine** benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Logik wird innerhalb der Hauptmoduldatei (`fbchat.php`) verarbeitet und über Hooks injiziert.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert **keine** benutzerdefinierten Klassen oder `ObjectModel`-Instanzen im Verzeichnis `classes/`. Die gesamte Datenverarbeitung erfolgt direkt über die `Configuration`-Klasse für Einstellungen.

### 4.4 JavaScript-Assets (`views/js/`)

- **`fbchat/jscolor/jscolor.js`**

  - **Geltungsbereich:** Back-Office (Admin-Konfigurationsseite).
  - **Zweck:** Dies ist eine Drittanbieter-JavaScript-Bibliothek für einen Farbwähler. Sie wird auf der Konfigurationsseite des Moduls verwendet, um eine benutzerfreundliche Oberfläche zur Auswahl von Farben für das Chat-Widget (z.B. Schriftfarbe, Hintergrundfarbe) bereitzustellen.
  - **Interaktion:** Sie fügt bestimmten Eingabefeldern im Admin-Formular Farbwähler-Funktionalität hinzu.
- **`fbchat/js/fbchat.js`**

  - **Geltungsbereich:** Front-Office.
  - **Zweck:** Dieses benutzerdefinierte JavaScript handhabt das dynamische Laden und die Initialisierung des Facebook Messenger Chat-Widgets. Es enthält Logik zum bedingten Laden des Facebook SDK und des Messenger-Chats basierend auf Moduleinstellungen und potenziellen Leistungsoptimierungs-Flags.
  - **Interaktion:**
    - Überprüft die Konfiguration `fbchat_hack`, um festzustellen, ob das verzögerte Laden für Google Insights aktiviert ist.
    - Erstellt und hängt das Facebook SDK-Skript (`sdk.js`) dynamisch an den `<body>` an, wenn `fbchat_appsdk` aktiviert ist.
    - Initialisiert das `FB.CustomerChat`-Plugin mit Parametern, die aus der Modulkonfiguration abgerufen werden (z.B. `page_id`, `app_id`, `theme_color`, `logged_in_greeting`, `logged_out_greeting`, `locale`).
    - Handhabt die Positionierung des Chat-Widgets basierend auf `fbchat_side`.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`fbchat/css.css`**

  - **Geltungsbereich:** Back-Office (Admin-Konfigurationsseite).
  - **Zweck:** Enthält spezifische Stile für das Konfigurationsformular des Moduls im PrestaShop Back Office. Dies kann Stile für Eingabefelder, Schaltflächen oder benutzerdefinierte Layout-Elemente innerhalb der `getContent()`-Ausgabe umfassen.
  - **Wichtige Selektoren:** Zielt wahrscheinlich auf Elemente innerhalb des Konfigurationsformulars des Moduls ab.
- **`fbchat/css/fbchat_left.css`**

  - **Geltungsbereich:** Front-Office.
  - **Zweck:** Bietet Stil-Anpassungen für das Facebook Messenger Chat-Widget, wenn dessen Position auf die „linke“ Seite des Bildschirms eingestellt ist. Dies kann `right`- oder `left`-CSS-Eigenschaften umfassen, um seine feste Position zu steuern.
  - **Wichtige Selektoren:** Zielt auf den Haupt-Chat-Container oder dessen Wrapper ab, um eine korrekte Ausrichtung auf der linken Seite zu gewährleisten.
- **`fbchat/css/fbchat_right.css`**

  - **Geltungsbereich:** Front-Office.
  - **Zweck:** Bietet Stil-Anpassungen für das Facebook Messenger Chat-Widget, wenn dessen Position auf die „rechte“ Seite des Bildschirms eingestellt ist. Dies kann `right`- oder `left`-CSS-Eigenschaften umfassen, um seine feste Position zu steuern.
  - **Wichtige Selektoren:** Zielt auf den Haupt-Chat-Container oder dessen Wrapper ab, um eine korrekte Ausrichtung auf der rechten Seite zu gewährleisten.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **`fbchat/admin-script.tpl`**

  - **Geltungsbereich:** Back-Office (Admin-Konfigurationsseite).
  - **Zweck:** Dieses Template wird wahrscheinlich verwendet, um JavaScript-Code (z.B. für die Farbwähler-Initialisierung aus `jscolor.js`) oder spezifisches Styling in die Konfigurationsseite des Moduls zu injizieren. Es wird innerhalb der `getContent()`-Methode gerendert.
  - **Variablen:** Kann Konfigurationsvariablen empfangen, um anfängliche Farbwählerwerte dynamisch festzulegen.
- **`fbchat/fbchat.tpl`**

  - **Geltungsbereich:** Front-Office.
  - **Zweck:** Dies ist das Haupt-Front-Office-Template, das für das Rendern der notwendigen HTML-Struktur und JavaScript-Initialisierung für das Facebook Messenger Chat-Widget verantwortlich ist. Es wird typischerweise in `displayFooter` oder `displayHeader` eingehängt.
  - **Variablen:** Empfängt alle notwendigen Konfigurationsvariablen von den `hookDisplayFooter`- oder `hookDisplayHeader`-Methoden des Moduls, wie `fbchat_fanid`, `fbchat_appid`, `fbchat_theme`, `fbchat_bg`, `fbchat_color`, `fbchat_langarray`, `fbchat_hello_logged`, `fbchat_hello_unlogged`, `fbchat_hack`, `fbchat_appsdk`, `fbchat_type`, `fbchat_side`.
  - **Ausgabe:** Generiert das `<div class="fb-customerchat">`-Element und das `<script>`-Tag für die Facebook SDK-Initialisierung.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine benutzerdefinierten SQL-Tabellen.
  - Alle Konfigurationseinstellungen werden in der Tabelle `ps_configuration` unter Schlüsseln wie `mypresta_updates`, `fbchat_theme`, `fbchat_bg`, `fbchat_color`, `fbchat_fanpage`, `fbchat_positions`, `fbchat_hack`, `fbchat_appsdk`, `fbchat_type`, `fbchat_fanid`, `fbchat_appid`, `fbchat_title`, `fbchat_langarray`, `fbchat_hello_logged`, `fbchat_hello_unlogged`, `fbchat_side` gespeichert.
- **Registrierte Hooks-Tabelle**:

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Wird im `<head>`-Bereich jeder Front-Office-Seite ausgeführt. | Wird verwendet, um CSS-Dateien (`fbchat_left.css`, `fbchat_right.css`) und potenziell einige anfängliche JavaScript-Dateien einzubinden, falls diese frühzeitig beim Laden der Seite benötigt werden. |
| `displayFooter` | Wird direkt vor dem schließenden `</body>`-Tag jeder Front-Office-Seite ausgeführt. | Dies ist der primäre Hook zum Rendern des `fbchat.tpl`-Templates, das den HTML-Code des Facebook Messenger Chats enthält und das `fbchat.js`-Skript initialisiert. Die Platzierung hier stellt sicher, dass der Hauptseiteninhalt zuerst geladen wird, was die wahrgenommene Leistung verbessert. |

## 5. Offizieller Support & Updates

Für offizielle Updates, technischen Support und die neuesten Versionen des Moduls „Facebook Messenger Chat“ wenden Sie sich bitte an Ihr Kundenkonto bei [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität oder Integration des Moduls gerne zur Verfügung.

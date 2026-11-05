---
title: My AI Claude - AI content generation - Dokumentation und Benutzerhandbuch
description: Anleitung zu Konfiguration, täglicher Nutzung und Fehlerbehebung für Shop-Betreiber, die My AI Claude bereits installiert haben und mit ihrem Anthropic-Claude-Konto verbinden und im eigenen Katalog einsetzen möchten.
sidebar:
  label: My AI Claude - AI content generation - Dokumentation und Benutzerhandbuch
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul AI Translations with Gemini auf MyPresta.eu kaufen](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-gemini.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ai-artificial-intelligence/ai-translations-with-gemini/)
>
> ---


## 1. Voraussetzungen

My AI Claude läuft im PrestaShop-Back-Office und sendet Ihre Prompts an Anthropic Claude. Dafür wird Folgendes benötigt.

| Punkt | Anforderung | Hinweise |
|---|---|---|
| PrestaShop | 1.6, 1.7, 8 und 9 (1.6 bis 9.99.99) | Funktioniert in der klassischen und in der neuen Produktseite. |
| PHP | 7.0 oder neuer | Bei einer niedrigeren Version bricht die Installation ab und zeigt eine Meldung mit der PHP-Version Ihres Servers. |
| PHP-Erweiterungen | cURL, JSON, mbstring, DOM, fileinfo, GD | Bei den meisten Hostings Standard. cURL spricht mit Claude, DOM liest die Quellseite in **New product**, GD skaliert importierte Fotos. |
| PHP-Einstellung | `allow_url_fopen` aktiviert | Nur für **New product** nötig (Lesen der Adresse der Quellseite). |
| Andere Module | Keine | Es muss kein weiteres Modul installiert sein. |
| Datenbank | Keine zusätzliche Anforderung | Das Modul nutzt die MySQL- oder MariaDB-Version, auf der PrestaShop bereits läuft. |
| Konto außerhalb des Shops | Ein Anthropic-Konto mit API-Zugang und Guthaben | Den Schlüssel erstellen Sie unter https://console.anthropic.com/settings/keys. Jede Generierung wird von Anthropic nach den verbrauchten Tokens abgerechnet. |
| Netzwerk | Der Server kann HTTPS-Verbindungen öffnen | Der Shop kontaktiert für jede Generierung `api.anthropic.com`. Die Update-Prüfung kontaktiert den Server von MyPresta.eu. Die Funktion Images öffnet öffentliche Webseiten. |
| Browser | JavaScript aktiviert | Alle Schaltflächen im Modul sind Skripte, die im Back-Office laufen. |

**Zeit und Speicher.** Eine Generierung ist eine Anfrage an Claude und dauert von wenigen Sekunden bis etwa eine Minute. Das Wartelimit stellen Sie unter **Settings, General** bei **API timeout (seconds)** ein (anfangs 120 Sekunden, jeder Wert von 10 bis 600). Stellen Sie das PHP-Zeitlimit Ihres Servers höher als diesen Wert ein. Ein Massenlauf sendet eine Anfrage pro Produkt, pro Feld und pro Sprache, nacheinander, und arbeitet nur, solange seine Seite im Browser geöffnet bleibt. Das Modul startet keinen Hintergrundprozess und braucht keinen zusätzlichen Speicher über eine normale Back-Office-Seite hinaus.

## 2. Installation

### 2.1 Hochladen und installieren

1. Öffnen Sie **Modules → Module Manager** (PrestaShop 1.6: **Modules and Services**).
2. Klicken Sie auf **Upload a module** (PrestaShop 1.6: **Add a new module**).
3. Wählen Sie die ZIP-Datei des Moduls und warten Sie, bis der Upload beendet ist.
4. Klicken Sie auf **Install**, sobald PrestaShop es anbietet.
5. Warten Sie auf die Bestätigung. Die Installation legt den Menüeintrag, zwei Datenbanktabellen und die vorgefertigten Prompt-Vorlagen an (siehe 3.6).

Der Installer leert den Cache nicht. Erscheint der Menüeintrag nicht, öffnen Sie **Advanced Parameters → Performance**, klicken Sie auf **Clear cache** und laden Sie die Seite neu.

Nach der Installation tut das Modul nichts, bis Sie Ihren Anthropic-Schlüssel eingeben. Weiter mit Kapitel 3, Abschnitt 3.1.

### 2.2 Wo das Modul erscheint

Das Modul fügt unter **Modules** einen Menüeintrag namens **AI Content Generator** hinzu. Ein Klick darauf öffnet das Modul auf seinem **Dashboard**. Alle anderen Bildschirme erreichen Sie über das horizontale Menü oben auf der Modulseite:

**Dashboard**, **Settings** (mit den Unterseiten **General**, **Claude**, **Studio**, **Prompt templates**, **Playground**), **Generate**, **New product**, **Cron**, **History**, **Images**, **Updates**.

Das Modul fügt außerdem auf jeder Produktseite ein Panel **Modules → My AI Claude** hinzu, kleine Schaltflächen **Generate with AI** neben Textfeldern in Produkt- und Kategorieformularen, eine Verknüpfung in der oberen Leiste des Back-Office und eine Schaltfläche **My AI Claude** über der Produktliste. Die Abschnitte 3.16 und 3.17 beschreiben jede davon.

Wenn ein Mitarbeiter, der kein Super-Administrator ist, den Menüeintrag nicht öffnen kann, geben Sie dem Profil dieses Mitarbeiters unter **Advanced Parameters → Team → Permissions** Zugriff auf die Modulbildschirme.

### 2.3 Deaktivieren und Deinstallieren

- **Deaktivieren** Sie das Modul im Module Manager, um seine Bildschirme auszublenden. Solange es deaktiviert ist, führt jede Moduladresse zurück zum PrestaShop-Haupt-Dashboard. Alle Daten bleiben erhalten.
- **Deinstallieren** entfernt die Menüeinträge, die Tabelle mit den Prompt-Vorlagen, die Tabelle mit dem Generierungsverlauf und jede Moduleinstellung (API-Schlüssel, Modell, Studio-Regeln, Cron-Einstellungen und Cron-Secrets). Der Verlauf verschwindet samt seinen Wiederherstellungspunkten, ebenso die Zahlen im Dashboard.
- Die Deinstallation lässt alles bestehen, was das Modul bereits in Ihren Shop geschrieben hat: Produkt- und Kategorietexte, importierte Fotos und mit **New product** erstellte Produkte.
- Die Deinstallation lässt außerdem einige gespeicherte Bildschirmauswahlen der **Generate**-Filter und die Einstellungen der MyPresta-Update-Prüfung bestehen.
- **Neuinstallation** beginnt bei null: Der API-Schlüssel ist leer, die Secrets sind neu (die Cron-Adressen ändern sich, aktualisieren Sie also den Scheduler Ihres Servers), die History ist leer und die vorgefertigten Vorlagen haben wieder ihren ursprünglichen Wortlaut.

## 3. Konfiguration und tägliche Arbeit im Back-Office

### 3.1 Der gesamte Ablauf Schritt für Schritt

1. Erstellen Sie einen Anthropic-API-Schlüssel unter https://console.anthropic.com/settings/keys und stellen Sie sicher, dass das Konto Guthaben hat.
2. Öffnen Sie **AI Content Generator → Settings → Claude**. Fügen Sie den Schlüssel in **Anthropic Claude API KEY** ein, wählen Sie ein **Model** und klicken Sie auf **Save**.
3. Öffnen Sie **Settings → Playground**, tippen Sie eine kurze Frage und klicken Sie auf **Generate**. Eine Antwort auf der Seite bestätigt, dass der Schlüssel funktioniert.
4. Optional: Öffnen Sie **Settings → Studio** und beschreiben Sie Ihre Markenstimme, Zielgruppe, Tonalität, bevorzugte Begriffe und verbotene Wörter. Diese Regeln werden jeder Generierung hinzugefügt.
5. Öffnen Sie **Settings → Prompt templates** und lesen Sie die vorgefertigten Vorlagen. Bearbeiten Sie die, die Sie behalten möchten, und deaktivieren Sie die übrigen.
6. Öffnen Sie ein Produkt, gehen Sie zu **Modules → My AI Claude**, drücken Sie auf der Beschreibungskarte **Try**, um ein Ergebnis zu lesen, ohne das Produkt zu ändern, und drücken Sie dann **Fill**, um es ins Produkt zu schreiben.
7. Öffnen Sie **History** und prüfen Sie den Eintrag. Drücken Sie im Produktpanel auf **Restore**, wenn Sie den alten Text zurückhaben möchten.
8. Für viele Produkte öffnen Sie **Generate → Products**, filtern die Liste, schreiben oder wählen einen Prompt und klicken auf **Run on the list below**. Testen Sie zuerst mit einer kleinen Liste.
9. Für automatische Läufe durch den Server richten Sie **Cron** ein (Abschnitt 3.12).
10. Behalten Sie Kosten und Volumen im **Dashboard** und in der **History** im Blick. Legen Sie in **Studio** ein **Monthly generation budget** fest, um die Nutzung zu begrenzen.

### 3.2 Das Modul öffnen und sich darin bewegen

Klicken Sie unter **Modules** auf **AI Content Generator**. Das obere Menü des Moduls enthält **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images** und **Updates**. Einige Seiten haben eine zweite Zeile: **Settings** hat **General**, **Claude**, **Studio**, **Prompt templates** und **Playground**; **Generate** hat **Products** und **Categories**.

Die fett gesetzten Namen sind Beschriftungen des englischen Back-Office, und die Screenshots in diesem Handbuch zeigen das englische Back-Office. Wenn Ihr Back-Office in einer anderen Sprache läuft, suchen Sie die entsprechenden Einträge an derselben Stelle.

Jede Modulseite hat unten rechts eine runde Schaltfläche **Help**. Sie öffnet ein Seitenpanel mit einer kurzen Erklärung zur aktuellen Seite.

### 3.3 Dashboard

![My AI Claude dashboard with request and token cards and three charts](https://mypresta.eu/docs/images/docs/myaiclaude-dashboard.webp)

Das Dashboard zeigt, wie stark das Modul genutzt wurde. Die erste Zeile nennt den aktiven Dienst und das Modell.

Wählen Sie den Zeitraum mit einer der Schaltflächen **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time**, oder geben Sie eigene Daten in **From** und **To** ein und klicken Sie auf **Apply**. Die Seite öffnet sich mit **30 days**.

| Element | Bedeutung | Hinweise |
|---|---|---|
| Requests | Anzahl der Aufrufe an Claude im Zeitraum | Zählt jede Zeile der History: Massenläufe, Produktpanel, Playground, obere Leiste, Cron. |
| Success | Aufrufe, die Text geliefert haben | |
| Errors | Aufrufe, die fehlgeschlagen sind | Der Grund ist in der History-Zeile gespeichert. |
| Tokens sent | Tokens in Ihren Prompts | Tokens sind die Einheit, nach der Anthropic abrechnet. |
| Tokens received | Tokens in den Antworten | |
| Requests and errors | Diagramm pro Tag | Lange Zeiträume werden pro Woche gruppiert. |
| Tokens sent and received | Diagramm pro Tag | |
| Requests by model | Diagramm | Zeigt, welche Modelle die Arbeit erledigt haben. |

Das Modul fügt außerdem dem PrestaShop-Haupt-Dashboard einen Block hinzu. Die vollständigen Zahlen und Diagramme finden Sie auf dieser Seite.

### 3.4 Settings – General

![Settings General page with switches and the image search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-settings-general.webp)

Öffnen Sie **Settings → General**, ändern Sie die Felder und klicken Sie auf **Save**. Die Meldung **Settings Updated** bestätigt das.

| Feld | Anfangswert | Was es bewirkt |
|---|---|---|
| Live mode | No | Eine Markierung für Sie selbst, dass der Shop live läuft. Sie schaltet keine Funktion ein oder aus. |
| Debug mode | No | Schreibt technische Zeilen zu fehlgeschlagenen Aufrufen ins PrestaShop-Log (**Advanced Parameters → Logs**). Aktivieren Sie es, wenn der Support Details anfordert, und deaktivieren Sie es danach wieder. |
| API timeout (seconds) | 120 | Wie lange der Shop auf Claude wartet, bevor er aufgibt. Werte unter 10 werden zu 10, Werte über 600 zu 600, ein leerer oder ungültiger Wert wird zu 120. Erhöhen Sie ihn für lange Beschreibungen. |
| Product Edit History | Yes | Zeigt den Tab **History** im Produktpanel und erlaubt dort die Wiederherstellung früherer Texte. Ist es aus, verschwindet der Tab. Generierungen werden weiterhin in der Haupt-History gespeichert. |
| Admin Top Bar CTA | Yes | Zeigt das kleine My-AI-Claude-Symbol in der oberen Leiste des Back-Office (Abschnitt 3.17). |
| Product edit page Form | Yes | Zeigt das Panel **Modules → My AI Claude** auf der Produktseite. Sind dieser Schalter und **Product Edit History** beide aus, ist das Panel leer. |
| AI Image Finder | Yes | Erlaubt den Tab **Photos** auf der Produktseite. Derselbe Schalter befindet sich auf der Seite **Images**. |
| AI Image Search Prompt | Vorgefertigter Text | Die Anweisung, mit der Seiten mit Fotos eines Produkts gefunden werden. Dasselbe Feld befindet sich auf der Seite **Images** (Abschnitt 3.14). |

### 3.5 Settings – Claude

![Settings Claude page with API key, model and sampling fields](https://mypresta.eu/docs/images/docs/myaiclaude-settings-claude.webp)

Diese Seite verbindet den Shop mit Ihrem Claude-Konto. Beim ersten Öffnen zeigt das Modul möglicherweise einen Hinweis, dass Leerzeichen aus dem Schlüsselfeld entfernt wurden. Das ist normal.

| Feld | Anfangswert | Was es bewirkt |
|---|---|---|
| Anthropic Claude API KEY | Leer | Das Geheimnis, mit dem der Shop Ihr Claude-Konto aufruft. Fügen Sie den Schlüssel von https://console.anthropic.com/settings/keys ein. Leerzeichen werden beim Speichern entfernt. Lassen Sie das Feld unverändert, um den gespeicherten Schlüssel zu behalten. Ein fehlender Schlüssel lässt jeden Aufruf fehlschlagen, und der Fehler erscheint in der **History**. |
| Model | claude-sonnet-4-5 | Das Claude-Modell, das den Text schreibt. Eingebaute Namen: claude-sonnet-4-5, claude-opus-4-5, claude-haiku-4-5, claude-3-5-sonnet-latest, claude-3-5-haiku-latest, claude-3-opus-latest sowie die Namen, die Sie hinzugefügt haben. Ein Modell, das Ihr Schlüssel nicht nutzen kann, liefert einen Fehler statt Text. |
| Add a Claude model | Leer | Geben Sie den genauen Modellnamen aus Ihrem Claude-Konto ein und klicken Sie auf **Add model**. Der Name erscheint in der Liste **Model**. Neben jedem hinzugefügten Namen gibt es einen Link **Remove**. Eingebaute Namen lassen sich nicht entfernen. |
| Max Tokens | 3200 | Obergrenze für die Länge der Antwort, in Tokens gezählt. Verwenden Sie etwa 256 für eine Meta-Beschreibung und 1000 oder mehr für eine vollständige Beschreibung. Ein zu niedriger Wert schneidet die Antwort ab. Ein leerer Wert wird durch 256 ersetzt. |
| Temperature | 0.7 | Wie abwechslungsreich die Formulierung ist, von 0 bis 1. Niedriger ist gleichmäßiger, höher ist kreativer. Geben Sie 0.1 für den gleichmäßigsten Stil ein, denn eine einfache 0 wird als Anfangswert 0.7 gelesen. |
| Top P | 1 | Wird mit den anderen Feldern gespeichert, aber My AI Claude sendet es nicht an Claude. Eine Änderung hat keine Wirkung. |
| Frequency Penalty Value | 0 | Wird gespeichert, aber nicht an Claude gesendet. Eine Änderung hat keine Wirkung. |
| Presence Penalty Value | 0 | Wird gespeichert, aber nicht an Claude gesendet. Eine Änderung hat keine Wirkung. |

Klicken Sie unten im Formular auf **Save**. Eine Bestätigung erscheint, wenn die Werte gültig sind. Die Meldung **Anthropic Claude API KEY field is invalid!** bedeutet, dass das Schlüsselfeld leer ist und noch kein Schlüssel gespeichert ist.

Lehnt ein Modell eine der Einstellungen ab (zum Beispiel die Temperature), entfernt das Modul diese Einstellung, versucht es erneut und merkt sich das für dieses Modell. Sie müssen nichts tun.

Die Sampling-Werte (Max Tokens, Temperature) werden von den Massenläufen, dem Produktpanel, dem Playground, der oberen Leiste und dem Cron verwendet. **Images** nutzt eigene feste Werte.

### 3.6 Settings – Prompt templates

![Prompt templates list with title, prompt, status and actions](https://mypresta.eu/docs/images/docs/myaiclaude-settings-templates.webp)

Eine Vorlage ist eine gespeicherte Anweisung, die Sie in den Massenläufen, im Produktpanel, in der oberen Leiste und im Cron auswählen können. Die Installation legt 16 Vorlagen an, alle aktiviert.

| Vorlage | Zweck | Hinweise |
|---|---|---|
| Product name 1, Product name 2 | Kürzere oder bessere Produktnamen | Name 2 verwendet Marke und Standardkategorie. |
| Product description 1 to 6 | Produktbeschreibungen | Description 1 baut ein HTML-Layout mit Überschriften auf und verlangt absichtliche Rechtschreibfehler. Löschen Sie diesen Satz, bevor Sie sie verwenden. Description 3 verlangt außerdem H1-Ideen, Keywords, einen Meta-Titel und eine Meta-Beschreibung, die alle im Beschreibungsfeld landen. |
| Product description 7 - using product images | Beschreibung mit eingebetteten Fotos | Verwendet die Links zu den Produktbildern. |
| Product meta title 1 to 3 | Meta-Titel | Meta title 1 verlangt die englische Sprache und 60 Zeichen. |
| Product meta description 1 to 3 | Meta-Beschreibungen | Meta description 1 verlangt die englische Sprache und 160 Zeichen. Meta descriptions 2 und 3 sind identisch und erwähnen eine Smartwatch, schreiben Sie sie also für Ihre eigenen Produkte um. |
| Product tags | Fünf Tags in einer Zeile | Verlangt die englische Sprache. |

Mehrere Vorlagen verlangen Englisch im Text selbst. Wenn Sie in einer anderen Sprache verkaufen, bearbeiten Sie diese Vorlagen und entfernen Sie die Zeile.

Die Liste zeigt **ID**, **Title**, **Prompt**, **Status** (zum Aktivieren oder Deaktivieren auf den Schalter klicken), **Timestamp** und die Zeilenaktionen zum Bearbeiten oder Löschen. Markieren Sie mehrere Zeilen und nutzen Sie die Sammelaktion **Delete** (die Frage **Are you sure you want to delete the selected prompts?** fordert eine Bestätigung). Die neuesten Vorlagen stehen oben, und die Liste zeigt 50 Zeilen pro Seite.

Um eine Vorlage anzulegen, klicken Sie in der Werkzeugleiste auf die Schaltfläche **new**. Um eine zu ändern, klicken Sie in ihrer Zeile auf die Bearbeiten-Aktion.

| Feld | Anfangswert | Was es bewirkt |
|---|---|---|
| Status | Enabled bei einer neuen Vorlage | Nur aktivierte Vorlagen erscheinen in den Auswahllisten des Moduls. |
| Prompt title | Leer (Pflichtfeld) | Der Name, den Sie in den Auswahllisten und in der Liste sehen. |
| Prompt content | Leer (Pflichtfeld) | Die an Claude gesendete Anweisung. Sie können Platzhalter wie `{product_name}` verwenden (Abschnitt 3.18). Doppelte Anführungszeichen werden beim Speichern durch einfache ersetzt. |

Klicken Sie auf **Save Prompt**, um die Vorlage zu speichern. Die Meldungen lauten **Prompt template successfully added!** und **Prompt template successfully updated!**. Eine gelöschte Vorlage zeigt **Prompt template removed.**. Klicken Sie auf **Go Back to Module Settings**, um das Formular ohne Speichern zu verlassen.

Eine Vorlage sagt Claude, was zu schreiben ist. Das Modul fügt außerdem die Regeln aus **Studio** und die Sprache des Laufs hinzu (Abschnitt 3.8 beschreibt die Studio-Regeln).

### 3.7 Settings – Playground

![Playground with a text box and the Generate button](https://mypresta.eu/docs/images/docs/myaiclaude-settings-playground.webp)

Der Playground ist ein freies Textfeld zum Ausprobieren eines Prompts. Geben Sie Ihren Prompt ein und klicken Sie auf **Generate**. Die Antwort erscheint auf der Seite. Es wird nichts in ein Produkt oder eine Kategorie geschrieben.

Der Aufruf wird in der History als allgemeine Generierung gespeichert und zählt daher für das Dashboard und für das Monatsbudget. Nutzen Sie den Playground, um den API-Schlüssel, das Modell und die Wirkung der Studio-Regeln zu prüfen.

### 3.8 Settings – Studio

![Studio page with brand voice, audience, tone, glossary and forbidden words](https://mypresta.eu/docs/images/docs/myaiclaude-settings-studio.webp)

Studio enthält die Regeln, die jeder Generierung hinzugefügt werden: Massenläufen, Produktpanel, Kategorien, Cron, Playground und oberer Leiste. Selbst wenn alle Studio-Felder leer sind, teilt das Modul Claude mit, in welcher Sprache zu schreiben ist (der Sprache dieses Laufs).

| Feld | Anfangswert | Was es bewirkt |
|---|---|---|
| Brand voice | Leer | Beschreibt, wie Ihr Shop klingt. Claude folgt dem in jedem Text. |
| Audience | Leer | Beschreibt den Kunden, für den Sie schreiben. |
| Tone | Leer | Die Stimmung des Textes, zum Beispiel warm, technisch oder neutral. |
| Glossary | Leer | Begriffe, die Claude genau so beibehalten muss, wie Sie sie schreiben. Einer pro Zeile. |
| Forbidden words | Leer | Wörter, die Claude nicht verwenden darf. Eines pro Zeile. Claude wird angewiesen, sie nicht zu verwenden, und wenn das Quality gate aktiv ist, wird eine Antwort, die dennoch eines enthält, abgelehnt. |
| Monthly generation budget | 0 | Maximale Anzahl erfolgreicher Generierungen im laufenden Kalendermonat. 0 bedeutet kein Limit. Ist die Zahl erreicht, stoppen neue Aufrufe mit der Meldung **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** Fehlgeschlagene Aufrufe werden nicht gezählt. |
| Quality gate | Yes | Prüft jede Antwort vor dem Speichern auf verbotene Wörter. Eine abgelehnte Antwort wird nicht geschrieben und zeigt **The reply was rejected because it contains a forbidden word from the studio settings.** |

Klicken Sie auf **Save studio**. Die Meldung **Studio settings saved.** bestätigt das.

Das Budget zählt alle erfolgreichen Zeilen der History im Monat: Massenläufe, Produktpanel (**Try** eingeschlossen), Playground, obere Leiste und Cron. **New product** wird nicht gezählt.

### 3.9 Generate – Products

![Generate Products filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-products.webp)

Öffnen Sie **Generate → Products**. Die Seite arbeitet in zwei Schritten: Zuerst wählt ein Filter die Produkte aus, dann lässt ein Panel Claude auf dieser Liste laufen.

**Schritt 1 – der Filter.** Füllen Sie die Felder aus und klicken Sie auf **Go to next step**. Das Formular öffnet sich immer mit den unten gezeigten Werten.

| Feld | Anfangswert | Was es bewirkt |
|---|---|---|
| Product Categories | Nichts angehakt | Haken Sie Kategorien an, um die Liste auf Produkte darin zu beschränken. Leer bedeutet alle Kategorien. |
| Brand | All | Beschränkt die Liste auf eine Marke. |
| Product status | Active | Active, Disabled oder Both. |
| Product stock | All products | **Only in stock products** behält Produkte mit einer Menge über null. |
| Update only | Update all | Drei Optionen: nur Produkte, die noch keinen History-Eintrag haben, nur Produkte, die bereits einen haben, oder alle Produkte. Jeder Eintrag zählt, auch fehlgeschlagene Aufrufe und **Try**-Läufe. |
| Product IDs | Leer | Eine Liste von Produkt-IDs. |
| Product Reference | Leer | Beschränkt die Liste auf Produkte mit dieser Referenz. |
| Product Add Date From, Product Add Date To | Leer | Beschränkt die Liste nach dem Erstellungsdatum des Produkts. |
| Minimum product ID, Maximum product ID | Leer | Beschränkt die Liste auf einen ID-Bereich. |
| Product Limit | Leer | Die maximale Anzahl von Produkten in der Liste. |

**Schritt 2 – das Panel Mass product generation.** Die passenden Produkte erscheinen in einer Tabelle mit **ID**, **Reference** und **Result**. Über der Tabelle stellen Sie den Lauf ein.

| Feld | Anfangswert | Was es bewirkt |
|---|---|---|
| Template | Nichts gewählt | Wählt eine aktivierte Vorlage und kopiert ihren Text in das Prompt-Feld. Den Text können Sie danach bearbeiten. |
| Prompt | Leer | Die Anweisung für Claude, mit Platzhaltern wie `{product_name}`. Ist das Feld leer, verwendet das Modul für jedes Feld einen eingebauten Auftrag: eine HTML-Beschreibung mit Einleitung und Merkmalsliste, eine kurze reine Zusammenfassung unter 400 Zeichen, einen Meta-Titel von etwa 70 Zeichen und eine Meta-Beschreibung von etwa 160 Zeichen. |
| What to generate | Descriptions | **Descriptions** (lange und kurze Beschreibung), **Meta title and meta description** oder **Descriptions and meta together**. |
| Existing text | Replace | **Replace**, **Skip if filled**, **Add above** oder **Add below**. |
| Languages | Die aktuelle Sprache angehakt | Haken Sie jede Sprache an, die geschrieben werden soll. |

Klicken Sie auf **Run on the list below**. Eine Statuszeile zeigt den Fortschritt (zum Beispiel `3 / 40` mit dem Feldnamen) und endet mit **Finished N products.** Jede Zeile zeigt das Feld, das Ergebnis und die Meldung, zum Beispiel **Content successfully generated and updated to product.** oder **Product skipped.**

Regeln eines Laufs:

- Der Lauf sendet eine Anfrage pro Produkt, pro Feld und pro Sprache, nacheinander. Zählen Sie die Anfragen vor dem Start, denn jede wird berechnet.
- Lassen Sie die Seite geöffnet. Schließen oder Neuladen stoppt den Lauf. Bereits geschriebene Produkte bleiben geschrieben.
- Ein Fehler in einer Zeile stoppt die anderen nicht. Der Grund steht in der Zeile und in der **History**.
- Grenzen beim Speichern: Produktname 128 Zeichen, Kurzbeschreibung 800, Meta-Titel 69, Meta-Beschreibung 159. Längerer Text wird abgeschnitten.
- Der Text wird direkt im Produkt gespeichert. Nutzen Sie das Produktpanel (Abschnitt 3.16), um einen früheren Text wiederherzustellen.

### 3.10 Generate – Categories

![Generate Categories filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-categories.webp)

Öffnen Sie **Generate → Categories**. Das erste Formular hat **Categories** (ein Baum, leer bedeutet alle) und **Category status** (Active, Disabled oder Both, anfangs Active). Klicken Sie auf **Go to next step**. Die Liste kann die Kategorien Root und Home enthalten, haken Sie also die gewünschten Kategorien an.

Unter dem Filter erscheint das Panel **Run on the categories below** mit einer Tabelle aus **ID** und **Result**.

| Feld | Anfangswert | Was es bewirkt |
|---|---|---|
| Prompt | Leer | Die Anweisung für Claude. Verwenden Sie Kategorie-Platzhalter wie `{category_name}`, `{category_description}` und `{category_parent_name}`. Produkt-Platzhalter werden hier nicht gefüllt. |
| Field | Description | **Description**, **Name**, **Meta title**, **Meta description** oder **Additional description**. |
| Existing text | Replace | **Replace** oder **Skip if filled**. |
| Language | Die aktuelle Sprache | Eine Sprache pro Lauf. |

Klicken Sie auf **Run on the categories below**. Jede Zeile zeigt das Ergebnis, zum Beispiel **Content successfully generated and updated to category.** oder **Category skipped.**

Unter dem Panel zeigt die Seite ein zweites Formular namens **Generate category content**. Seine Schaltfläche startet keinen Lauf. Verwenden Sie **Run on the categories below** und ignorieren Sie das zweite Formular. Die Schaltfläche **Go Back to Category Filter** führt zurück zum Filter.

Die Grenzen beim Speichern sind dieselben wie bei Produkten: Name 128 Zeichen, Meta-Titel 69, Meta-Beschreibung 159. Das Feld **Additional description** gibt es nur in PrestaShop-Versionen, die es haben. Andernfalls zeigt die Zeile einen Fehler.

### 3.11 New product

![New product page with the product brief and the generated draft](https://mypresta.eu/docs/images/docs/myaiclaude-new-product.webp)

**New product** erstellt aus einer kurzen Beschreibung ein vollständiges Produkt. Claude schreibt einen Entwurf, Sie lesen ihn, und dann legt das Modul das Produkt in Ihrem Katalog an.

| Feld | Anfangswert | Was es bewirkt |
|---|---|---|
| What is the product? | Leer | Beschreiben Sie das Produkt in wenigen Sätzen: was es ist, für wen es gedacht ist, die wichtigsten Merkmale. Das ist das einzige Pflichtfeld. Der Text wird bei 8000 Zeichen abgeschnitten. |
| Optional source URL | Leer | Die Adresse einer Seite über das Produkt. Das Modul liest deren Titel, Meta-Beschreibung und Preis und gibt sie an Claude weiter. |
| Language | Die Standardsprache des Shops | Die Sprache des Entwurfs. |
| Default category ID | 2 | Die ID der Kategorie, in die das Produkt eingeordnet wird. 2 ist die Kategorie Home eines Standard-Shops. |

1. Füllen Sie die Felder aus und klicken Sie auf **Generate data**. Der Entwurf erscheint auf der Seite als Datenblock (Name, Beschreibungen, Meta-Felder, Tags, Merkmale, Preis). Es ist noch nichts gespeichert.
2. Lesen Sie den Entwurf. Passt er nicht, ändern Sie die Beschreibung und klicken Sie erneut auf **Generate data**.
3. Klicken Sie nur dann auf **Create product**, wenn Sie den Entwurf akzeptieren. Die Seite zeigt dann **Product #** gefolgt von der neuen Produktnummer. Das Produkt finden Sie unter **Catalog → Products**.

Das neue Produkt wird mit diesen Einstellungen angelegt: aktiv, bestellbar, Preis angezeigt, im Katalog und in der Suche sichtbar, Zustand neu, die erste Steuerregel des Shops, ein Lagerbestand von 100 Stück und der Preis aus dem Entwurf (0, wenn der Entwurf keinen enthält). Claude füllt außerdem Name, Beschreibungen, Meta-Felder, Tags, Merkmale und die Referenz (maximal 32 Zeichen). Öffnen Sie das Produkt anschließend, prüfen Sie Preis, Steuer, Lagerbestand und Fotos und fügen Sie Fotos über den Tab **Photos** des Produktpanels hinzu.

Ist kein Schlüssel gespeichert, zeigt die Seite **Add an API key in the module settings first.** Diese Seite wendet weder die Studio-Regeln noch das Monatsbudget an, und ihre Aufrufe erscheinen weder in der **History** noch im **Dashboard**.

### 3.12 Cron

![Cron page with enable switch, secret and product cron form](https://mypresta.eu/docs/images/docs/myaiclaude-cron.webp)

Mit Cron lässt Ihr Server nach Zeitplan Text generieren, ohne dass jemand klickt. Die Seite baut die Adresse, die der Server aufrufen muss. Sie startet keinen Scheduler. Die geplante Aufgabe legen Sie bei Ihrem Hosting oder Server an, und jeder Aufruf verarbeitet einen Stapel und endet.

Die Seite hat zwei Formulare: den Produkt-Cron und den Kategorie-Cron. Das Produktformular wird unten beschrieben. Das Kategorieformular folgt derselben Logik, mit eigenem Secret und eigenen Einstellungen.

Unter der Einleitung jedes Formulars zeigt die Seite die Adresse des Crons. Die Produktadresse sieht so aus: `https://your-shop/module/myaiclaude/cron?secret=...`. Die Kategorieadresse endet mit `&entity=category`.

**Vervollständigen Sie die Adresse, bevor Sie sie verwenden.** Hängen Sie `&action=generateProductContent` ans Ende der Produktadresse und `&action=generateCategoryContent` ans Ende der Kategorieadresse. Ohne das antwortet die Adresse mit **Invalid action!** und tut nichts.

Beispiel für Produkte:

`https://your-shop/module/myaiclaude/cron?secret=YOUR_SECRET&action=generateProductContent`

Die Adresse nutzt die im Formular gespeicherten Auswahlen: Feld, Ziel, Anzahl der Produkte, Sprache und Vorlage. Sie können sie in der Adresse überschreiben (Abschnitt 6.3 listet die Parameter auf).

**Formular des Produkt-Crons**

| Feld | Anfangswert | Was es bewirkt |
|---|---|---|
| Enable Cron Feature | No | Hauptschalter für beide Cron-Adressen (Produkt und Kategorie). Ist er aus, antwortet die Adresse mit **Cron Job feature is disabled. You can enable it from the module settings.** |
| Cron Job Secret Token | Zufälliger Text | Das lange Passwort in der Adresse. Ohne das richtige antwortet die Adresse mit **The token does not exist or it's wrong!** Die Schaltfläche **Generate Token** funktioniert in dieser Version nicht (Abschnitt 5.5). Geben Sie ein eigenes Secret aus mindestens 24 Buchstaben und Ziffern ein, speichern Sie und kopieren Sie die neue Adresse in Ihren Scheduler. |
| Update Field | description | Das eine Feld, das von dieser Adresse geschrieben wird: name, description, description_short, meta_title, meta_description oder tags. Für mehrere Felder legen Sie mehrere Aufgaben an. |
| Selected Products | pendingClaude | **pendingClaude** wählt Produkte, die noch keine erfolgreiche My-AI-Claude-Generierung haben (beliebiges Feld). **pendingField** wählt Produkte ohne erfolgreiche Generierung für dieses Feld, sodass Sie eine Aufgabe für die Beschreibung und eine andere für den Namen über dieselben Produkte laufen lassen können. **emptyField** wählt Produkte, deren gewähltes Feld leer ist. |
| Product Categories | Nichts angehakt | Beschränkt den Lauf auf Produkte in den angehakten Kategorien. |
| Product ID list | Leer | Nur diese Produkt-IDs, durch Kommas getrennt. Buchstaben werden beim Speichern entfernt. |
| Language | Die Standardsprache des Shops | Die Sprachversion, die geschrieben wird. Andere Sprachen brauchen eine eigene Aufgabe. |
| Product to update | 5 | Wie viele Produkte ein Aufruf verarbeitet. Beginnen Sie mit 5 oder 10, damit eine langsame Antwort das Zeitlimit des Servers nicht überschreitet. Der nächste Aufruf macht mit den Produkten weiter, die noch passen. |
| Prompt Template | Nichts gespeichert | Die gespeicherte Anweisung, die für jedes Produkt des Laufs verwendet wird. Wählen Sie eine aus und klicken Sie auf **Save**. Ohne gespeicherte Vorlage antwortet die Adresse mit **All must include all mandatory parameters!** |
| Enable Debug | No | Zeigt beim Öffnen der Adresse im Browser den Plan, die Datenbankabfrage und den endgültigen Prompt und speichert nichts. Deaktivieren Sie es, bevor der Scheduler die Adresse verwendet. |
| CRON JOB interval | Every Hour | Eine Notiz für Sie über den Rhythmus Ihres Schedulers (von jeder Minute bis alle 6 Stunden). Sie plant nichts und ändert die Adresse nicht. |
| Product Cron Job command | Die Adresse | Die Adresse des Crons. Fügen Sie den Teil `&action=` wie oben beschrieben hinzu. |

Klicken Sie unter dem Formular auf **Save**. Das Kategorieformular hat die Felder **Enable Debug**, **CRON JOB interval**, **Language**, **Prompt Template**, **Selected categories**, **Update Field** (name, description, meta_title, meta_description), **Categories to update** und das Secret sowie eine eigene Schaltfläche **Save**.

Was jeder Aufruf tut:

- Er ersetzt das gewählte Feld. Der Cron hat keine Option, Text zu behalten oder anzufügen.
- Er wendet die Studio-Regeln und das Monatsbudget an. Ist das Budget erreicht, antwortet der Aufruf mit **Error!Monthly generation budget reached.**
- Er schreibt für jeden Text eine History-Zeile, sodass Sie ihn wiederherstellen oder prüfen können.
- Beide Secrets öffnen beide Aktionen. Der Cron bleibt aus, bis **Enable Cron Feature** auf **Yes** steht.

Testen Sie mit **Enable Debug** auf **Yes** und der im Browser geöffneten Adresse. Wenn der Plan stimmt, setzen Sie es auf **No**, speichern Sie und legen Sie die Aufgabe an.

### 3.13 History

![History page with filters, cards, breakdown panels and the prompt list](https://mypresta.eu/docs/images/docs/myaiclaude-history.webp)

Die History ist das Protokoll von allem, was an Claude gesendet wurde. Die Seite öffnet sich auf **This month**.

**Filter.** Schnellschaltflächen: **Today**, **7 days**, **30 days**, **This month**, **All time**. Felder: **From**, **To**, **Model**, **Type**, **Status**, **Language**, **Employee**, **Product / category ID**, **Prompt or reply contains**. Klicken Sie auf **Filter**.

**Karten.** **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**.

**Aufschlüsselungspanels.** **By day**, **By model**, **By type**, **By language**, **By employee**. Jedes zeigt Aufrufe, gesendete Tokens, empfangene Tokens und die Summe. Zeilen ohne Mitarbeiter (alle Cron-Aufrufe) erscheinen als Unknown.

**Liste des Prompt-Verlaufs.**

| Spalte | Bedeutung | Hinweise |
|---|---|---|
| ID | Zeilennummer | |
| Status | Badge **Success** oder **Error** | |
| Prompt | Der gesendete Text | In der Liste bei 180 Zeichen abgeschnitten. |
| Reply / Error | Die Antwort oder die Fehlermeldung | In der Liste bei 180 Zeichen abgeschnitten. |
| Provider | Der Dienst, das Modell, die Fehlerstatusnummer, wenn Claude eine geliefert hat, und die Zeit in Sekunden | |
| Sent, Received, Total | Tokens | |
| Entity ID | Das Produkt oder die Kategorie | Leer bei Aufrufen aus Playground und oberer Leiste. |
| Type | Was generiert wurde | Siehe nächste Tabelle. |
| Timestamp | Datum und Uhrzeit | |

Klicken Sie in einer Zeile auf die Ansehen-Aktion, um den vollständigen Prompt und die Antwort sowie den Link **Back to the list** zu sehen. Die Liste zeigt 50 Zeilen pro Seite.

| Type | Bedeutung | Hinweise |
|---|---|---|
| general | Playground und obere Leiste | Kein Produkt, keine Kategorie. |
| product_name, product_description, product_description_short, product_meta_title, product_meta_description, product_tags | Ein Produktfeld | Geschrieben von Massenläufen, Produktpanel, den Logo-Schaltflächen und Cron. |
| product_seo_pack | Das SEO-Paket des Produktpanels | Name, Beschreibungen und Meta-Felder in einer Anfrage. |
| category_name, category_description, category_meta_title, category_meta_description, category_additional_description | Ein Kategoriefeld | |
| error | Ein fehlgeschlagener Aufruf | Der Grund steht in **Reply / Error**. |

**Clear list** in der Werkzeugleiste löscht nach Bestätigung **alle** Zeilen und zeigt **Log list successfully deleted.** Das lässt sich nicht rückgängig machen. Es entfernt außerdem die Wiederherstellungspunkte jedes Produkts, leert das Dashboard, setzt den Zähler des Monatsbudgets zurück und ändert, welche Produkte in **Update only** und in den Cron-Zielen als bereits verarbeitet gelten. Exportieren oder notieren Sie vorher, was Sie brauchen.

Gibt es im gewählten Zeitraum keine Zeilen, zeigt die Seite **No generations in this range.**

### 3.14 Images

![Images page with the image finder switch and search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-images.webp)

Diese Seite steuert den Tab **Photos** der Produktseite. Das Formular heißt **AI Image Finder**.

| Feld | Anfangswert | Was es bewirkt |
|---|---|---|
| AI Image Finder | Yes | Aktiviert den Tab **Photos** auf der Produktseite. Ist er aus, weist der Tab darauf hin, ihn unter **Settings → General** zu aktivieren. |
| AI Image Search Prompt | Vorgefertigter Text | Die an Claude gesendete Anweisung, Webseiten zu finden, die das Produkt zeigen. Verwenden Sie `{product_name}` und `{product_description}` als Platzhalter. Behalten Sie die Aufforderung bei, genau fünf Seitenadressen als Liste zurückzugeben, denn das Modul liest diese Liste. |

Der vorgefertigte Prompt verlangt genau fünf Adressen von Seiten, die das Produkt zeigen, als JSON-Liste, unter Verwendung von Produktname und Beschreibung.

Klicken Sie auf **Save**. Die Meldung **Settings saved.** bestätigt das. Die Seite und der Tab in **Settings → General** teilen sich denselben Schalter und Prompt.

### 3.15 Updates

![Updates page with manual check and automatic notifications](https://mypresta.eu/docs/images/docs/myaiclaude-updates.webp)

Die Seite **Updates** prüft, ob eine neuere Version von My AI Claude existiert. Die Prüfung sendet den Modulnamen, die Version und die Shop-Adresse an den Server von MyPresta.eu.

| Feld | Anfangswert | Was es bewirkt |
|---|---|---|
| Manual Check | Schaltfläche **Check Now** | Führt die Prüfung sofort aus. Die Antwort lautet **Module is up to date!** oder **New version available!** |
| Automatic Notifications | Enabled | Wenn aktiviert, prüft das Modul etwa alle drei Tage und zeigt im Back-Office einen Hinweis, wenn eine neue Version existiert. |
| Product Page | Ein Link | Öffnet die Modulseite auf MyPresta.eu. |

Klicken Sie auf **Save**. Die Meldung **Update settings saved.** bestätigt das.

### 3.16 Produktseite – Modules → My AI Claude

![Product page with the My AI Claude panel and field cards](https://mypresta.eu/docs/images/docs/myaiclaude-product-edit.webp)

Öffnen Sie ein beliebiges Produkt, gehen Sie zum Tab **Modules** und suchen Sie **My AI Claude**. Das Panel hat die Tabs **Generate**, **Simulate**, **Photos** und **History**. Speichern Sie ein neues Produkt einmal, bevor Sie das Panel nutzen, denn das Panel arbeitet an einem gespeicherten Produkt.

**Generate und Simulate.**

1. Wählen Sie den Sprach-Chip oder **Every language**. Anfangs ist die erste Sprache des Shops gewählt.
2. Wählen Sie unter **If the field already has text** **Replace**, **Add above**, **Add below** oder **Skip if filled**. Anfangs ist **Replace** gewählt.
3. Drücken Sie auf einer Karte **Fill**: **Description**, **Short description**, **Name**, **Meta title**, **Meta description** oder **Tags**. Der Text wird direkt ins Produkt geschrieben.
4. Die Karte **SEO pack** hat **Fill all**. Eine Anfrage liefert den Namen, beide Beschreibungen und beide Meta-Felder. Sie überschreibt diese Felder, auch den Namen. Die Meldung **SEO pack saved. Refresh the product to see it.** bestätigt das. Liefert Claude kein verwendbares Paket, meldet das Panel **The model did not return a usable SEO pack.**
5. Öffnen Sie **Use your own instruction or a saved prompt**, um zu filtern und **Standard brief** oder eine aktivierte Vorlage zu wählen, oder geben Sie im Feld **Instruction** Ihren eigenen Text ein. Bei leerem Feld wird der Standardauftrag der Karte verwendet.
6. Die Antwort und die Token-Anzahl erscheinen unter den Karten.

Im Tab **Simulate** haben dieselben Karten **Try**. **Try** zeigt die Antwort und lässt das Produkt unverändert. Es wird dennoch in der History gespeichert und aufs Budget angerechnet, und das Produkt gilt dadurch für **Update only** und für den Cron als bereits verarbeitet.

**Laden Sie die Produktseite nach Fill neu.** Das geöffnete Formular enthält noch den alten Text. Drücken Sie in PrestaShop **Save**, ohne neu zu laden, überschreibt PrestaShop den neuen Text mit dem alten.

**Photos.**

![Photos tab with found photos ready to be added](https://mypresta.eu/docs/images/docs/myaiclaude-product-photos.webp)

1. Öffnen Sie den Tab **Photos** und klicken Sie auf **Find pages**. Meldungen: **Looking for photos…** und **Reading photos…**.
2. Haken Sie die gewünschten Fotos an. Die Seite zeigt **Tick the photos you want, then add them to this product.**
3. Klicken Sie auf **Add selected to this product**. Die Meldung **Adding the photos to this product…** erscheint, danach die Zahl der importierten Bilder.
4. Laden Sie die Produktseite neu, um die Fotos zu sehen.

Der Finder liest bis zu 5 Seiten und bietet bis zu 24 Fotos an. Das erste angehakte Foto wird zum Titelbild des Produkts. Die Fotos werden in Ihren Shop heruntergeladen und auf alle Bildgrößen Ihres Shops skaliert. Prüfen Sie, ob Sie das Recht haben, sie zu verwenden. Ist der Finder deaktiviert, bittet der Tab darum, ihn unter **Settings → General** zu aktivieren.

**History.** Der Tab zeigt **When**, **Type**, **Status** und eine Schaltfläche **Restore** für die letzten 50 Einträge dieses Produkts. Die Einleitungszeile lautet **Earlier writes for this product. Restore puts the previous text back…** Ohne Einträge steht dort **No generations for this product yet.** Klicken Sie auf **Restore** und bestätigen Sie. Die Meldung **Content successfully restored. Refresh this page to see changes.** erscheint. Eine Zeile ohne vorherigen Wert zeigt **Error! This log entry has no previous value to restore.** Der Tab erscheint nur, wenn **Product Edit History** aktiv ist.

### 3.17 Weitere Stellen, an denen das Modul erscheint

**Schaltflächen Generate with AI neben Feldern.** Neben diesen Feldern erscheint eine kleine Logo-Schaltfläche.

| Stelle | Felder | Was passiert |
|---|---|---|
| Produktformular | Description, Short description, Meta title, Meta description | Claude schreibt in das Feld des geöffneten Formulars. |
| Kategorieformular | Description, Additional description, Meta title, Meta description | Claude schreibt in das Feld des geöffneten Formulars. |

Hat der Shop mehr als eine Sprache, fragt die Schaltfläche, ob die aktuelle Sprache oder alle Sprachen geschrieben werden sollen. Der Text erscheint im Feld, ist aber nicht gespeichert. Der Hinweis **Text is in the field. Save the product to keep it.** (bei Kategorien: **Save the category**) erinnert daran. Bei einem neuen, ungespeicherten Element zeigt die Schaltfläche **Save the product once before generating.** (bei Kategorien: **Save the category once…**). Jede Nutzung wird in der History gespeichert und lässt das Produkt als bereits verarbeitet gelten.

**Verknüpfung in der oberen Leiste.** Das Zaubersymbol in der oberen Leiste des Back-Office öffnet ein kleines Fenster namens **My AI Claude** mit einer Liste **Template**, einem Textfeld, **Generate** und einer Schließen-Schaltfläche. Es funktioniert wie der Playground und speichert nichts. Der Schalter ist **Admin Top Bar CTA** in **Settings → General**.

**Produktliste.** Eine Schaltfläche **My AI Claude** in der Werkzeugleiste über der Produktliste öffnet **Generate → Products**.

### 3.18 Platzhalter für Prompts

Platzhalter sind Wörter in geschweiften Klammern, die das Modul vor dem Senden des Prompts durch echte Daten ersetzt. Sie funktionieren in Vorlagen, im Prompt-Feld der Massenläufe, im Produktpanel und im Cron.

| Platzhalter | Gilt für | Wird ersetzt durch |
|---|---|---|
| `{product_name}`, `{product_description}`, `{product_description_short}`, `{product_tags}` | Produkte | Den aktuellen Namen, die Beschreibung, die Kurzbeschreibung und die Tags in der Sprache des Laufs. |
| `{product_reference}`, `{product_ean13}`, `{product_weight}` | Produkte | Referenz, EAN-13-Code und Gewicht. |
| `{product_brand}`, `{product_default_category}`, `{product_category_description}`, `{product_categories}` | Produkte | Marke, Standardkategorie mit ihrer Beschreibung und alle Kategorien. |
| `{product_attributes}`, `{product_features}`, `{product_feature_values}` | Produkte | Kombinationen, Merkmalsnamen und Merkmalswerte. |
| `{product_images}` | Produkte | Links zu den Produktfotos. |
| `{category_name}`, `{category_description}`, `{category_parent_name}` | Kategorien | Name, Beschreibung und Name der übergeordneten Kategorie. |
| `{shop_name}`, `{shop_url}`, `{shop_language}`, `{shop_country}`, `{shop_currency}` | Überall | Shop-Name, Adresse, Sprache, Land und Währung. |

Ein Platzhalter ohne Daten wird durch einen leeren Text ersetzt.

## 4. Storefront

My AI Claude fügt nichts hinzu, was Ihre Kunden sehen oder nutzen können. Es hat keine Front-Office-Seite, keinen Block, kein Widget und keine Kundeneinstellung. Die Texte, die es schreibt, werden nur dadurch sichtbar, dass sie in Ihren Produkten und Kategorien gespeichert sind, und Sie sehen sie über Ihr normales Theme.

Das Modul hat zwei Adressen, die zur Shop-Domain gehören, aber nicht für Kunden gedacht sind.

| Adresse | Wer sie nutzt | Was sie zurückgibt |
|---|---|---|
| `…/module/myaiclaude/cron?secret=…&action=…` | Der Scheduler Ihres Servers | Eine Antwort in Klartext wie **N products have been updated.**, **N categories have been updated.**, **No products to update.**, **No categories to update.** oder eine der Meldungen aus der nächsten Tabelle. |
| `…/module/myaiclaude/ajax` | Die eigenen Back-Office-Bildschirme des Moduls | Nichts Nützliches, wenn sie von Hand geöffnet wird. Sie antwortet nur auf Anfragen, die das Secret der Bildschirme tragen. |

| Meldung der Cron-Adresse | Bedeutung | Was zu tun ist |
|---|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | **Enable Cron Feature** steht auf **No**. | Auf **Yes** stellen und speichern. |
| The token does not exist or it's wrong! | Das Secret in der Adresse passt zu keinem gespeicherten Secret. | Kopieren Sie die Adresse erneut von der Seite **Cron**. |
| Invalid action! | Der Teil `&action=` fehlt oder ist falsch geschrieben. | Fügen Sie `&action=generateProductContent` oder `&action=generateCategoryContent` hinzu. |
| All must include all mandatory parameters! | Eine erforderliche Auswahl fehlt, meist die Prompt-Vorlage. | Wählen Sie im Formular eine Vorlage und klicken Sie auf **Save**. |
| updatedField parameter is wrong! | Das Feld gehört nicht zu den erlaubten Feldern. | Wählen Sie das Feld im Formular und speichern Sie. |
| productTarget parameter is wrong! Allowed values: pendingClaude, pendingField, emptyField. | Das Ziel in der Adresse ist falsch geschrieben. | Verwenden Sie einen der drei Werte. |
| No valid product IDs provided. | Die **Product ID list** enthält keine Zahlen. | Korrigieren Sie die Liste oder leeren Sie sie. |
| Error!… | Claude oder der Shop hat einen Fehler gemeldet. Der Text nach dem Wort Error erklärt ihn. | Lesen Sie den Text, siehe Kapitel 5. |

Die Storefront-Hooks des Moduls sind leer, daher fügt es Ihren Shopseiten keine Ausgabe hinzu.

## 5. Fehlerbehebung

### 5.1 Menü und Bildschirme

| Symptom | Ursache | Was zu klicken ist |
|---|---|---|
| **AI Content Generator** fehlt im Menü. | Der Cache wurde nicht geleert, das Modul ist deaktiviert oder der Mitarbeiter hat keinen Zugriff. | **Advanced Parameters → Performance → Clear cache**. Prüfen Sie **Modules → Module Manager**. Prüfen Sie **Advanced Parameters → Team → Permissions**. |
| Jede Moduladresse führt zum Haupt-Dashboard zurück. | Das Modul ist deaktiviert. | Aktivieren Sie es im **Module Manager**. |
| Das Panel **Modules → My AI Claude** auf der Produktseite ist leer. | **Product edit page Form** und **Product Edit History** sind beide aus. | Aktivieren Sie mindestens eines in **Settings → General**. |
| Das Produktpanel funktioniert bei einem neuen Produkt nicht. | Das Produkt ist noch nicht gespeichert. | Speichern Sie das Produkt einmal, dann nutzen Sie das Panel. |
| Der Tab **History** fehlt im Produktpanel. | **Product Edit History** ist aus. | Aktivieren Sie es in **Settings → General**. |
| Der My-AI-Claude-Block im PrestaShop-Haupt-Dashboard zeigt leere oder Null-Werte. | Der Block auf der Startseite enthält die Berichtsdaten nicht. | Öffnen Sie **AI Content Generator → Dashboard** für die echten Zahlen. |

### 5.2 Verbindung zu Claude

| Symptom | Ursache | Was zu klicken ist |
|---|---|---|
| Die Meldung sagt, der Anthropic-Claude-API-Schlüssel sei nicht gesetzt (**The Anthropic Claude API key is not set. Add it in the module settings.**). | Es ist kein Schlüssel gespeichert. | **Settings → Claude**, den Schlüssel in **Anthropic Claude API KEY** einfügen, **Save**. |
| **Anthropic Claude API KEY field is invalid!** | Das Schlüsselfeld ist leer und es ist kein Schlüssel gespeichert. | Schlüssel einfügen und speichern. |
| Die Meldung beginnt mit **Anthropic Claude API Error**, gefolgt von einem Text von Anthropic. | Claude hat den Aufruf abgelehnt. Typische Gründe sind ein falscher Schlüssel, ein Modell, das Ihr Konto nicht nutzen kann, kein Guthaben oder zu viele Anfragen. | Lesen Sie den Text nach dem Doppelpunkt. Prüfen Sie Schlüssel, Guthaben und Modell in Ihrem Anthropic-Konto. Wählen Sie ein anderes **Model**. |
| **Claude request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.** | Claude hat zu langsam geantwortet. | Erhöhen Sie **API timeout (seconds)** in **Settings → General** (maximal 600) oder verringern Sie **Max Tokens**. Versuchen Sie es später erneut. |
| Eine Meldung, die mit **cURL Error** beginnt | Der Server erreicht Claude nicht, oder eine Firewall blockiert es. | Bitten Sie Ihr Hosting, ausgehendes HTTPS zu `api.anthropic.com` zu erlauben. |
| Ein neues Claude-Modell fehlt in der Liste **Model**. | Die Liste enthält nur die eingebauten Namen und die von Ihnen hinzugefügten. | Geben Sie den genauen Namen in **Add a Claude model** ein und klicken Sie auf **Add model**. |
| Nach **Remove** zeigt die Liste **Model** ein Modell, das nicht zu Claude gehört. | Das Entfernen des aktiven hinzugefügten Modells schaltet den Shop auf einen Ersatznamen um, den Claude nicht kennt. | Wählen Sie in **Model** ein Claude-Modell und klicken Sie auf **Save**. |
| Das Modul meldet **OpenAi Settings Updated** oder **OpenAi Model field is invalid!**, die Spalte **Provider** in der History zeigt `openai`, die Seitenhilfe spricht von einem OpenAI-Konto, und das Beispiel in **Add a Claude model** nennt einen GPT-Namen. | Das sind Textreste der älteren Modulversion. | Nichts. Das Modul spricht nur mit Claude. Lesen Sie die Texte als Claude. |
| Die Schaltfläche **Module settings** in den Filterformularen von **Generate** öffnet eine falsche Seite. | Die Schaltfläche verweist auf die Einstellungen eines anderen Moduls (My ChatGPT), nicht auf My AI Claude. | Öffnen Sie **Settings** im oberen Menü des Moduls. |
| Das PrestaShop-Log füllt sich mit Zeilen zur Modellliste. | **Debug mode** ist aktiv. | Deaktivieren Sie **Debug mode** in **Settings → General**. |

### 5.3 Probleme bei der Generierung

| Symptom | Ursache | Was zu klicken ist |
|---|---|---|
| **Error! Prompt is missing or too short!** | Der Prompt hat weniger als 4 Zeichen. | Schreiben Sie einen längeren Prompt oder wählen Sie eine Vorlage. |
| **Error! Product not found!** | Das Produkt existiert nicht mehr. | Laden Sie die Liste neu. |
| **The model hit the token limit … Increase "Max Tokens" …** | Die Antwort hat alle Tokens verbraucht, bevor Text entstand. | Erhöhen Sie **Max Tokens** in **Settings → Claude**. |
| **The model returned an empty response.** | Claude hat keinen Text geliefert. | Versuchen Sie es erneut, formulieren Sie den Prompt um oder erhöhen Sie **Max Tokens**. |
| **The response was blocked by the provider content filter…** | Claude hat das Thema abgelehnt. | Formulieren Sie den Prompt um. |
| Der Text bricht mitten im Satz ab. | **Max Tokens** ist zu niedrig. | Erhöhen Sie **Max Tokens**. Nutzen Sie 1000 oder mehr für eine vollständige Beschreibung. |
| Die Beschreibung enthält Rechtschreibfehler, unerwünschte Überschriften, H1-Ideen oder Keyword-Listen. | Die vorgefertigte Vorlage verlangt das. | Bearbeiten Sie die Vorlage in **Settings → Prompt templates** (Abschnitt 3.6). |
| Der Text ist englisch, obwohl der Shop in einer anderen Sprache läuft. | Eine vorgefertigte Vorlage verlangt Englisch, oder es wurde die falsche Sprache gewählt. | Bearbeiten Sie die Vorlage und haken Sie im Lauf die richtige Sprache an. |
| **The reply was rejected because it contains a forbidden word from the studio settings.** | Das **Quality gate** hat ein Wort aus **Forbidden words** gefunden. | Lassen Sie den Lauf erneut laufen, entfernen Sie das Wort aus **Studio** oder schalten Sie **Quality gate** aus. |
| **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** | Die Zahl der Generierungen in diesem Monat hat **Monthly generation budget** erreicht. | Erhöhen Sie den Wert in **Settings → Studio** oder setzen Sie ihn auf 0. |
| **Error! The generated content could not be saved to the product.** | PrestaShop hat den Text abgelehnt, zum Beispiel einen Produktnamen mit nicht erlaubten Zeichen. | Lesen Sie die Details in der Zeile und in der **History**. Bearbeiten Sie den Prompt und starten Sie erneut. |
| **Error! This PrestaShop version does not support the category Additional Description field.** | Ihre PrestaShop-Version hat dieses Feld nicht. | Wählen Sie ein anderes Feld. |
| Eine Zeile sagt **Product skipped.** oder **Category skipped.** | **Skip if filled** ist gewählt und das Feld hat bereits Text. | Wählen Sie **Replace**, um zu überschreiben. |
| Nach **Fill** ist der alte Text zurück. | Das Formular wurde gespeichert, ohne die Seite neu zu laden. | Laden Sie die Produktseite nach jedem **Fill** neu und machen Sie dann weiter. |
| Ein Massenlauf wurde gestoppt. | Die Seite wurde geschlossen oder neu geladen. | Starten Sie erneut und stellen Sie **Update only** auf die Option für noch nicht aktualisierte Produkte. Fehlgeschlagene Aufrufe gelten dort als aktualisiert. |
| Die Kategorieseite hat ein zweites Formular mit **Generate content**, das nichts tut. | Dieses Formular ist nicht angebunden. | Verwenden Sie **Run on the categories below**. |
| **Error! This log entry has no previous value to restore.** | Die History-Zeile hat keinen früheren Text. | Bearbeiten Sie das Feld von Hand. |
| Das Ergebnis von **Try** erscheint nicht im Produkt, aber es gibt eine History-Zeile. | **Try** schreibt nie ins Produkt. | Drücken Sie **Fill**, um es zu schreiben. |

### 5.4 Fotos und neue Produkte

| Symptom | Ursache | Was zu klicken ist |
|---|---|---|
| Der Tab **Photos** bittet darum, den Finder zu aktivieren. | **AI Image Finder** ist aus. | Aktivieren Sie ihn in **Settings → General** oder auf **Images**. |
| **Claude API key is not configured. Please check module settings.** | Es ist kein Schlüssel gespeichert. | **Settings → Claude**. |
| **The search failed.** | Claude oder das Netzwerk haben nicht geantwortet. | Klicken Sie erneut auf **Find pages**, prüfen Sie Schlüssel und Timeout. |
| **No photos were found on the suggested pages.** | Die Seiten hatten keine verwendbaren Fotos. | Ändern Sie Produktname oder Beschreibung oder bearbeiten Sie **AI Image Search Prompt**. |
| **URL not allowed (private network).** | Die Adresse verweist auf ein privates oder lokales Netzwerk. | Verwenden Sie nur öffentliche Webseiten. |
| **No images selected** | Nichts wurde angehakt. | Haken Sie mindestens ein Foto an. |
| **No images could be imported. Details: …** | Die Fotos ließen sich nicht herunterladen oder waren keine gültigen Bilder. | Lesen Sie die Details. Versuchen Sie andere Fotos. |
| Das Titelbild hat sich geändert. | Das erste angehakte Foto wird zum Titelbild. | Ändern Sie die Reihenfolge der Fotos auf der Produktseite. |
| **Add an API key in the module settings first.** (**New product**) | Es ist kein Schlüssel gespeichert. | **Settings → Claude**. |
| **Failed to parse AI response. Please try again.** | Claude hat Text geliefert, der kein gültiger Entwurf ist. | Klicken Sie erneut auf **Generate data**. Beschreiben Sie das Produkt ausführlicher. |
| **Prompt is required**, **Invalid product data**, **Failed to create product** | Die Beschreibung ist leer, der Entwurf ist unvollständig, oder PrestaShop konnte das Produkt nicht speichern. | Füllen Sie **What is the product?** aus, generieren Sie erneut, prüfen Sie die Kategorie-ID. |

### 5.5 Cron-Probleme

| Symptom | Ursache | Was zu klicken ist |
|---|---|---|
| Die Adresse antwortet mit **Invalid action!** | Der von der Seite kopierten Cron-Adresse fehlt der Teil `&action=`. | Fügen Sie `&action=generateProductContent` (Produkte) oder `&action=generateCategoryContent` (Kategorien) hinzu. |
| Die Adresse antwortet mit **Cron Job feature is disabled…** | **Enable Cron Feature** ist aus. | Auf **Yes** stellen und **Save**. |
| **Generate Token** tut nichts. | Die Schaltfläche ist in dieser Version nicht angebunden. | Geben Sie in **Cron Job Secret Token** ein Secret aus mindestens 24 Buchstaben und Ziffern ein und klicken Sie auf **Save**. Ein kürzeres Secret wird beim nächsten Öffnen einer Admin-Seite durch ein zufälliges ersetzt. |
| Die Adresse antwortet mit **All must include all mandatory parameters!** | Das Formular wurde nie gespeichert, daher ist keine Vorlage hinterlegt. | Wählen Sie ein **Prompt Template**, dann **Save**. |
| Die Adresse antwortet mit **No products to update.**, obwohl Produkte Text brauchen. | **Selected Products** schließt sie aus. **pendingClaude** überspringt jedes Produkt mit erfolgreicher Generierung, auch **Try**-Läufe. | Verwenden Sie **emptyField** oder **pendingField** oder legen Sie die **Product ID list** fest. |
| Der Text eines Produkts wurde erneut überschrieben. | Der Cron ersetzt das Feld immer. | Verwenden Sie **emptyField**, um nur leere Felder anzufassen. |
| **Error!Monthly generation budget reached.** | Das Monatsbudget ist aufgebraucht. | Erhöhen Sie es in **Settings → Studio**. |
| **Error! Could not save product N: … (X product(s) updated before this one.)** | PrestaShop hat den Text für Produkt N abgelehnt. | Beheben Sie dieses Produkt oder schließen Sie es aus, starten Sie erneut. |
| Der Befehl auf der Seite ändert sich nicht, wenn Sie das Formular ändern. | Der Befehl zeigt nur die Basisadresse. | Fügen Sie `&action=` selbst hinzu. Die Formularwerte werden aus den gespeicherten Einstellungen gelesen. |
| Das Intervall im Formular hat keine Wirkung. | Es ist eine Notiz für Sie. | Legen Sie den Zeitplan im Panel Ihres Hostings an. |

### 5.6 History und Daten

| Symptom | Ursache | Was zu klicken ist |
|---|---|---|
| Dashboard und History sind nach **Clear list** leer. | **Clear list** löscht alle Zeilen. | Es gibt nichts wiederherzustellen. Planen Sie Exporte vor dem Leeren. |
| **This log entry no longer exists.** | Die Zeile wurde gelöscht. | Gehen Sie zurück zur Liste. |
| **Update only** zeigt keine Produkte. | Der Filter nutzt History-Einträge, und jedes Produkt hat bereits einen. | Wählen Sie **Update all**. |
| Einige Produkte fehlen bei **Update only**. | Fehlgeschlagene Aufrufe und **Try**-Läufe zählen ebenfalls als Einträge. | Wählen Sie **Update all**. |

## 6. Für Entwickler

### 6.1 Überblick

My AI Claude (`myaiclaude`, Version 1.1.0, Autor MyPresta.eu) ist ein PrestaShop-Modul für den Tab `front_office_features`. Es unterstützt PrestaShop 1.6 bis 9.99.99 und PHP 7.0 und neuer. Es ruft die Anthropic Claude Messages API unter `https://api.anthropic.com/v1` auf (Endpunkt `/messages`) und schreibt die Ergebnisse in Produkte und Kategorien.

- Die Klasse `myaiclaude` in `myaiclaude.php` enthält Installation, Deinstallation, Konfigurationsseiten und Hooks.
- Die Klasse `MyAIClaude\OpenAIService` (`src/OpenAIService.php`) ist der Client. Sie sendet `model`, `max_tokens`, `messages`, ein optionales `system` und eine optionale `temperature`, mit den Headern `x-api-key` und `anthropic-version: 2023-06-01`. Top P und die beiden Penalties werden gespeichert, aber nicht gesendet. Sie bildet `input_tokens` und `output_tokens` auf gesendete und empfangene Tokens ab. `listModels()` antwortet immer, dass die Modellliste vom Modulkatalog bereitgestellt wird, die Modellliste ist also der eingebaute Satz plus die in `EXTRA_MODELS` gehaltenen Namen. Das Timeout wird auf 10–600 Sekunden begrenzt. Antwortet die API mit 400 und nennt einen Parameter, lässt der Client diesen Parameter weg, versucht es erneut und merkt sich die Entscheidung pro Modell in `MODEL_CAPS`.
- Die Klasse `MyAIClaude\Studio` (`src/Studio.php`) umhüllt Prompts mit der Sprachzeile, Stimme, Zielgruppe, Tonalität, Glossar und verbotenen Begriffen, wendet das Monatsbudget und das Verbotswort-Gate an und baut den Prompt des SEO-Pakets.
- Die Tabs der Konfigurationsseite nutzen die URL-Parameter `mac_tab` (`dashboard`, `settings`, `updates`) und `mac_sub` (`general`, `openai`, `studio`, `templates`, `playground`). Der Wert `openai` von `mac_sub` öffnet den Tab Claude. Das Dashboard nutzt `mcg_preset` und die Daten `mac_from` und `mac_to`.
- CSS-Klassen im Back-Office verwenden das Präfix `.mac-`.
- Massenjobs laufen mit einem Element pro AJAX-Anfrage aus `back.js`.

### 6.2 Dateien

| Pfad | Zweck | Hinweise |
|---|---|---|
| `myaiclaude.php` | Modulklasse | Installation, Deinstallation, Formulare, Hooks, Tab-Platzierung. |
| `autoload.php` | Loader für den Namespace `MyAIClaude\` | |
| `src/OpenAIService.php`, `src/Studio.php` | API-Client und Studio-Regeln | |
| `controllers/admin/AdminMyAIClaude*.php` | Back-Office-Controller | Siehe 6.3. |
| `controllers/front/ajax.php`, `controllers/front/cron.php` | Front-Controller | AJAX und Cron. |
| `lib/updateChecker.php` | MyPresta-Update-Prüfung | Kontaktiert `dev.mypresta.eu/update/get.php`. |
| `lib/sectionHelp.php` | Texte der **Help**-Schublade | |
| `lib/prestashop9compatibility.php` | Kompatibilitäts-Helfer | |
| `lib/searchTool` | Autocomplete-Helfer für Admin-Formulare | |
| `views/templates/` | Smarty-Templates | Hooks, Admin-Seiten, Massen-Panels. |
| `views/js/` | `back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `dashboard.js`, `admin-help.js`, `chart.min.js` | |
| `views/css/` | Stile mit dem Präfix `.mac-` | |
| `translations/` | 34 Sprachdateien | |
| `upgrade/index.php` | Platzhalter | Das Modul hat keine Upgrade-Skripte. |

### 6.3 Controller

| Controller | Menü oder Route | Rolle |
|---|---|---|
| AdminMyAIClaudeMain | **AI Content Generator** unter **Modules** | Leitet zum Dashboard weiter. Elternteil der versteckten Tabs. |
| AdminMyAIClaude | Versteckter Tab **Mass Content Creator** | Generate: Produkte und Kategorien. |
| AdminMyAIClaudeProductCreator | Versteckter Tab **AI Product Creator** | New product. |
| AdminMyAIClaudeSettings | Versteckter Tab **Module Settings** | Leitet zum Tab Settings weiter. |
| AdminMyAIClaudeCron | Versteckter Tab **Cron Job Settings** | Die beiden Cron-Formulare. |
| AdminMyAIClaudeUsage | Versteckter Tab **Module Log and Usage** | History. |
| AdminMyAIClaudeImageFinder | Versteckter Tab **AI Image Finder** | Images. |
| Front `ajax` | `module/myaiclaude/ajax` | Aktionen `initiatePrompt`, `updateProduct`, `updateCategory`, `initiateProductRestore`, `updateSettings`, `generateAltTexts`, `generateSeoPack`. Verlangt `secret_token` gleich `TOKEN`. Ist nicht an eine Mitarbeitersitzung gebunden. Kein Bildschirm dieser Version ruft `generateAltTexts` auf. |
| Front `cron` | `module/myaiclaude/cron` | Verlangt `secret` gleich `SECRET` oder `CAT_SECRET` und `ENABLE_CRON=1`. Parameter: `action` (`generateProductContent`, `generateCategoryContent`), `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`, `categoryTarget`, `categoriesToUpdate`. Fehlende Parameter werden aus den gespeicherten Einstellungen gelesen. |

Die Unter-Tabs werden mit `active=0` unter `AdminMyAIClaudeMain` angelegt. Bei `displayBackOfficeHeader` platziert das Modul den Haupt-Tab unter dem Eltern-Tab Modules, benennt ihn um und erzeugt Secrets, die kürzer als 24 Zeichen sind, neu. Die Icon-Klasse ist `icon-openai`. Der Tab Image Finder wird bei Bedarf registriert und durch `IMAGEFINDER_TAB_OK` markiert.

Der Produkt-Cron akzeptiert die Ziele `pendingClaude`, `pendingField` und `emptyField` und zählt nur Log-Zeilen, deren Status nicht `error` ist. Der Generate-Filter **Update only** zählt jede Log-Zeile. Cron-Log-Zeilen verwenden die Methode `cron`.

### 6.4 Hooks

| Hook | Verhalten | Hinweise |
|---|---|---|
| `displayAdminProductsExtra` | Rendert das Panel **Modules → My AI Claude** | Tabs Generate, Simulate, Photos, History. |
| `displayBackOfficeHeader` | Lädt Assets, platziert das Menü, erzeugt kurze Secrets neu | Läuft auf jeder Admin-Seite. |
| `displayBackOfficeTop` | Rendert die Verknüpfung in der oberen Leiste | |
| `dashboardZoneTwo` | Rendert `dashboard.tpl` im PrestaShop-Dashboard | Das Template wird ohne seine Berichtsvariablen gerendert. |
| `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom` | Registriert, geben einen leeren String zurück | |
| `actionProductFormBuilderModifier` | Registriert, tut nichts | |
| `displayHeader`, `displayFooter` | Registriert, leer | Die Storefront erhält keine Ausgabe. |

Das Modul hat keine Methode `enable()` oder `disable()`. `displayCustomTop` und `top.tpl` existieren, werden aber nicht aufgerufen.

### 6.5 Overrides

Das Modul hat kein Verzeichnis `override` und ändert keine Core-Datei. Produktfotos werden mit den PrestaShop-Bildklassen geschrieben, und das Modul schreibt Produkte und Kategorien mit den PrestaShop-Objekten (`Product`, `Category`, `Tag::addTags`).

### 6.6 Datenbank

Tabellen (Präfix wie in Ihrem Shop, Engine wie bei PrestaShop):

| Tabelle | Spalten | Hinweise |
|---|---|---|
| `myaiclaude_prompt` | `id_prompt` (Primärschlüssel), `status`, `title`, `prompt`, `date_generated` | Enthält die 16 installierten Vorlagen und Ihre eigenen. |
| `myaiclaude_log` | Prompt, Antwort, Status, Typ, Modell, Produkt- oder Kategorie-ID, Sprache, Mitarbeiter, Token-Zahlen, Dauer, Datum | Eine Zeile pro Aufruf. Token-Spalten werden bei älteren Installationen bei Bedarf hinzugefügt. |

Die Schreibvorgänge bei Produkten und Kategorien berühren die Core-Tabellen der bearbeiteten Daten (`product`, `product_lang`, `category_lang`, `tag`, `image` und die zugehörigen Tabellen). Die Deinstallation löscht beide Modultabellen.

### 6.7 Schlüssel und Übersetzungen

Konfigurationsschlüssel verwenden das Präfix `MYPRESTA_MYAICLAUDE_`.

| Schlüssel (nach dem Präfix) | Anfangswert | Bedeutung |
|---|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | 0 | Markierung und Debug-Protokollierung. |
| `TIMEOUT` | 120 | API-Timeout. |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT`, `IMAGEFINDER_ENABLE` | 1 | Schalter der Seite General. |
| `IMAGEFINDER_PROMPT` | Vorgefertigter Text | Verwendet `{product_name}` und `{product_description}`. |
| `API_KEY` | Ein einzelnes Leerzeichen | Anthropic-Schlüssel. |
| `MODEL`, `EXTRA_MODELS`, `MODEL_CAPS` | `claude-sonnet-4-5`, leer, leer | Aktives Modell, hinzugefügte Modelle, gelernte Parameterunterstützung. |
| `TEMPERATURE`, `MAX_TOKENS`, `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 0.7, 3200, 1, 0, 0 | Sampling-Felder. Die letzten drei werden nicht gesendet. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | Leer | Studio-Textfelder. |
| `BUDGET`, `QUALITY` | 0, 1 | Monatsbudget und Quality gate. |
| `TOKEN` | Zufällige 32 Zeichen | AJAX-Secret. |
| `SECRET`, `CAT_SECRET` | Zufällige 32 Zeichen | Cron-Secrets für Produkte und Kategorien. |
| `ENABLE_CRON` | 0 | Cron-Schalter. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Intervall-Notizen. |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList` | description, pendingClaude, 5, leer, Standardsprache, leer, 0, leer | Gespeichertes Formular des Produkt-Crons. |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug`, `categories` | description, pendingClaude, 5, leer, Standardsprache, 0, leer | Gespeichertes Formular des Kategorie-Crons. |

Die Generate-Bildschirme speichern ihre letzten Filterauswahlen außerdem in Schlüsseln wie `FIELD`, `LANGUAGE`, `CONTENT`, `DELAY`, `EXISTING`, `HISTORY`, `STATUS`, `STOCK`, `CATEGORIES`, `BRANDS`, `CATEGORIESC` und mehreren `PROD_*`-Schlüsseln. Die Deinstallation löscht sie nicht, ebenso wenig `mypresta_updates`, `update_myaiclaude` und `updatev_myaiclaude` der Update-Prüfung. Die Deinstallation entfernt die übrigen Schlüssel sowie die älteren Schlüssel des früheren Anbieters.

Die Hilfetexte der Formularfelder werden mit `fieldHelp()` in die drei Teile **What it does**, **How to configure** und **Effect** gebaut. Zeichenketten laufen durch das PrestaShop-Übersetzungssystem (Übersetzungsdomänen von Modul und Controller). Eine Sprache fügen Sie hinzu, indem Sie eine Datei `translations/<iso>.php` ablegen. Die Texte der Help-Schublade stammen aus `lib/sectionHelp.php`. Cron-Antworten, Studio-Prompts und die Standard-Prompt-Texte sind einfache englische Zeichenketten im Code.

### 6.8 Erweitern

- Fügen Sie Modelle über das Feld **Add a Claude model** hinzu oder indem Sie die ID in `EXTRA_MODELS` eintragen.
- Fügen Sie Prompts als Vorlagen hinzu oder senden Sie Ihren eigenen Text mit dem Secret über die `ajax`-Aktionen.
- Platzhalter werden in `controllers/front/ajax.php` ersetzt. Die Platzhalter `{cms_title}`, `{brand_name}`, `{brand_description}` und `{brand_short_description}` werden erkannt, wenn die Anfrage eine CMS-Seiten- oder Marken-ID trägt. Kein Bildschirm dieser Version sendet diese IDs.
- Bauen Sie einen eigenen Zeitplan mit der Cron-Adresse und ihren Parametern (Abschnitt 6.3).
- Das Modul rendert kein Storefront-Template, ein Theme hat also nichts zu überschreiben.

## 7. Hilfe

Modulseite: https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai.html

So erhalten Sie Support:

1. Melden Sie sich bei mypresta.eu an.
2. Gehen Sie zu **contact**.
3. Wählen Sie **Support for paid modules**.
4. Schreiben Sie den Modulnamen (My AI Claude), seine Version (1.1.0), Ihre PrestaShop- und PHP-Versionen und was Sie getan haben, bevor das Problem auftrat. Fügen Sie den Text der angezeigten Meldung hinzu.

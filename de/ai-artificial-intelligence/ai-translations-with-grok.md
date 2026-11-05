---
title: "AI Translations with Grok - Dokumentation und Benutzerhandbuch"
description: "Anleitung zur Konfiguration und Fehlerbehebung für Shops, die AI Translations with Grok bereits einsetzen."
sidebar:
  label: "AI Translations with Grok - Dokumentation und Benutzerhandbuch"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul AI Translations with Grok auf MyPresta.eu kaufen](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-grok.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/ai-artificial-intelligence/ai-translations-with-grok/)
>
> ---


## 1. Anforderungen

Das Modul läuft auf PrestaShop 1.7.0.0 und neuer, einschließlich PrestaShop 8 und 9.

- **PrestaShop:** 1.7.0.0 oder neuer.
- **PHP:** 5.6 oder neuer.
- **PHP-Erweiterungen:** cURL, OpenSSL, SimpleXML und mbstring.
- **Andere Module:** keine erforderlich.
- **Außerhalb des Shops:** ein xAI-Konto und ein Grok-API-Schlüssel aus der xAI-Konsole. Der Server Ihres Shops muss `https://api.x.ai/v1/chat/completions` erreichen können.
- **Optional:** ein Eintrag im Zeitplan des Servers, der die Cron-Adresse aus **Einstellungen** aufruft. Ohne diesen Eintrag verarbeiten Sie die Teilstapel selbst unter **Jobs**.
- **Große Kataloge:** Eine Domain mit Tausenden Zeichenfolgen bedeutet entsprechend viele API-Aufrufe. Ein Job wird in Teilstapel der Größe **Batch-Größe** aufgeteilt. Drücken Sie vor dem Start unter **Stapel** auf **Schätzung**, um Anzahl und Kosten zu sehen.
- Der Shop braucht mindestens zwei Sprachen. Bei nur einer Sprache zeigt das Backoffice **Der Shop benötigt mindestens zwei Sprachen.** an, und es gibt nichts zu übersetzen.

## 2. Installation

1. Öffnen Sie **Module** und dann **Modulmanager**. Wählen Sie das Hochladen eines Moduls, laden Sie die ZIP-Datei hoch und klicken Sie bei **AI Translations with Grok** auf **Installieren**.
2. Nach der Installation erscheint **AI Translations with Grok** im Menü **International**.
3. Die Installation leert den Shop-Cache nicht. Das Modul tut das erst, wenn es eine Übersetzung speichert.

Öffnen Sie anschließend **AI Translations with Grok**, wechseln Sie zu **Einstellungen** und fügen Sie Ihren Grok-Schlüssel ein. Solange kein Schlüssel gespeichert ist, zeigt jede Seite des Moduls **Kein Grok-API-Schlüssel.** mit dem Link **Einstellungen öffnen**.

**Deinstallation.** Klicken Sie im **Modulmanager** auf **Deinstallieren** und bestätigen Sie die Frage **Dieses Modul und seine Daten (Jobs, Glossar, Cache) löschen?**

- Der Menüeintrag verschwindet. Gelöscht werden Jobs, Glossar, Ausschlussmuster, der Aufrufverlauf, die Warteschlange **Überprüfen**, die Rollback-Kopien, das Kostenregister und die Moduleinstellungen einschließlich des API-Schlüssels.
- Texte, die das Modul bereits in den Shop geschrieben hat, bleiben erhalten. Dazu gehören Katalogübersetzungen und die Übersetzungsdateien klassischer Module, die das Modul geschrieben hat. Auch Ihre Wahl bei der Update-Prüfung bleibt bestehen.
- Eine Neuinstallation holt gelöschte Jobs, Glossareinträge und den Verlauf nicht zurück. Sie setzt die Standardwerte und erzeugt eine neue Cron-Adresse.

## 3. Konfiguration und tägliche Arbeit

Das gesamte Modul ist auf einer Seite zu finden: **International**, dann **AI Translations with Grok**. Die Reiter heißen **Dashboard**, **Manuell**, **Stapel**, **Jobs**, **Überprüfen**, **Katalog**, **Glossar**, **Ausschlüsse**, **Verlauf** und **Einstellungen**. **Updates** steht am Ende der Leiste. Über **Hilfe** öffnen Sie das Panel des gerade offenen Reiters. Auf dem Reiter **Updates** gibt es keine Schaltfläche **Hilfe**.

Die Abbildungen in dieser Anleitung zeigen das englische Backoffice. Die Namen von Schaltflächen und Feldern im Text sind die des deutschen Backoffice.

Ein normaler Arbeitsablauf besteht aus vier Schritten.

1. **Verbindung herstellen.** Fügen Sie unter **Einstellungen** den Schlüssel ein, wählen Sie das Modell und klicken Sie auf **Verbindung testen** und dann auf **Speichern**.
2. **Kleiner Test.** Filtern Sie unter **Manuell** eine Domain, markieren Sie einige leere Zeichenfolgen und übersetzen Sie diese. Prüfen Sie das Ergebnis, bevor Sie den gesamten Katalog übersetzen.
3. **Job anlegen.** Wählen Sie unter **Stapel** Abschnitt, Sprachen und Domains, klicken Sie auf **Schätzung** und dann auf **Job starten**. Öffnen Sie den Job und klicken Sie auf **Teilstapel verarbeiten** oder **Automatische Verarbeitung**. Alternativ überlassen Sie das dem Cron-Aufruf.
4. **Ergebnisse prüfen.** Öffnen Sie **Überprüfen** für Zeilen, die die Qualitätsprüfung zurückgehalten hat, und **Verlauf**, wenn ein Aufruf fehlgeschlagen ist. Mit **Rollback** am Job stellen Sie den vorherigen Text wieder her, sofern das Modul eine Kopie behalten hat.

Das Modul startet nie von selbst eine Übersetzung. **Schätzung**, **Filtern** und **Speichern** unter **Einstellungen** schreiben keinen Katalogtext. Ein Job bleibt unter **Jobs** stehen, bis Sie ihn verarbeiten oder die Cron-Adresse ihn aufruft.

### 3.1. Modulkonfiguration

Öffnen Sie **Module**, dann **Modulmanager**, suchen Sie **AI Translations with Grok** und klicken Sie auf **Konfigurieren**. Es öffnet sich das **Dashboard**. Wechseln Sie zu **Einstellungen**.

**Speichern** und **Verbindung testen** finden Sie unten im Formular. Das Speichern dieses Formulars startet keine Übersetzung und überschreibt keine bereits gespeicherten Übersetzungen.

![Einstellungen, englisches Backoffice. Oberer Teil: API-Schlüssel, Modell, Modell hinzufügen, Tonfall und Quell-Locale.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-settings.webp)

**Verbindung**

| Feld | Standard | Bedeutung |
|---|---|---|
| **Grok-API-Schlüssel** | leer | Der geheime Schlüssel, den der Shop an Grok sendet. Fügen Sie den Schlüssel aus der xAI-Konsole ein. Ein leeres Feld behält den bereits gespeicherten Schlüssel. Ein neuer Wert ersetzt ihn. Ein leeres Feld löscht ihn nicht. Ist ein Schlüssel gespeichert, zeigt die Hilfe **Schlüssel gespeichert:** und den maskierten Schlüssel an. |
| **Modell** | grok-4.7 | Das Grok-Modell, das die Übersetzung schreibt. Die eingebauten Modelle bleiben in der Liste: grok-4.7, grok-4.6, grok-4.5, grok-4.3, grok-4.20-0309-non-reasoning und grok-4.20-0309-reasoning. Selbst hinzugefügte Modelle können Sie wieder entfernen. Die nächste Übersetzung verwendet das gewählte Modell. Kann Ihr Konto ein Modell nicht nutzen, schlägt der Aufruf fehl, und der Fehler erscheint unter **Verlauf**. |
| **Grok-Modell hinzufügen** | leer | Tragen Sie die genaue Modell-Kennung aus Ihrem xAI-Konto ein und klicken Sie auf **Modell hinzufügen**. Der Platzhalter lautet grok-4.7. Die neue Kennung erscheint unter **Modell** und wird sofort das aktive Modell. **Entfernen** löscht nur Kennungen, die Sie hier hinzugefügt haben. Eingebaute Modelle lassen sich nicht entfernen. |

Mögliche Meldungen: **Modell hinzugefügt.**, **Modell entfernt.**, **Dieses Modell ist bereits in der Liste. Es ist nun das aktive Modell.**, **Geben Sie eine Modell-ID ein, zum Beispiel grok-4.7.**, **Integrierte Modelle können nicht entfernt werden.**

**Stil und Quelle**

| Feld | Standard | Bedeutung |
|---|---|---|
| **Tonfall** | Formell | Fügt jedem Prompt eine Stilanweisung hinzu. **Formell** passt zu Shop- und Backoffice-Texten, **Locker** klingt leichter, **Marke** wird zusammen mit **Markenstimme** verwendet. Neue Übersetzungen folgen dem gewählten Stil. Bestehende Übersetzungen bleiben unverändert, bis Sie sie erneut übersetzen lassen. |
| **Markenstimme** | leer | Wird nur angezeigt, wenn **Tonfall** auf **Marke** steht. Beschreiben Sie in ein paar einfachen Sätzen, wie der Shop klingen soll, oder lassen Sie das Feld leer. Der Text fließt in den nächsten Prompt ein. Ein leeres Feld bedeutet: keine zusätzliche Stimme. Bestehende Übersetzungen werden dadurch nicht umgeschrieben. |
| **Quell-Locale** | leer | Die Sprache, die das Modell als Original behandelt. Die leere Auswahl erscheint als Strich in der Liste. Dann ist die Quelle der Bildschirm, den Sie übersetzen. Meist wählen Sie die Locale, in der Ihre Kataloge verfasst sind, also in der Regel en-US. **Manuell**, **Stapel** und die Symbole unter **International → Übersetzungen** verwenden diese Locale als Quelle. Die Standardsprache des Shops ändert sich nicht. |
| **Einzelne Feld-Schaltflächen – Shop-Formulare** | Ja | Eine Schaltfläche neben jedem mehrsprachigen Feld in den Shop-Formularen: Produkt, Kategorie, CMS und andere Backoffice-Formulare. Die Schaltfläche übersetzt nur dieses eine Feld. **Nein** blendet diese Schaltflächen im gesamten Shop aus. Gespeicherte Übersetzungen bleiben unverändert. |
| **Einzelne Feld-Kontrollkästchen – Shop-Formulare** | Ja | Jedes dieser Felder erhält ein Kontrollkästchen. Die Leiste übersetzt dann nur die markierten Felder. **Nein** blendet Kontrollkästchen und Leiste aus. Die Schaltflächen oben haben einen eigenen Schalter. |
| **Einzelne Feld-Schaltflächen – International → Übersetzungen** | Ja | Eine Schaltfläche an jedem Feld unter **International → Übersetzungen**. **Nein** blendet diese Schaltflächen aus. Shop-Formulare sind davon nicht betroffen. Ein Klick füllt das Feld. Gespeichert wird die Seite weiterhin mit **Speichern** von PrestaShop. |
| **Einzelne Feld-Kontrollkästchen – International → Übersetzungen** | Ja | Kontrollkästchen und Leiste unter **International → Übersetzungen**. **Nein** blendet sie aus. Shop-Formulare bleiben unberührt. |

**Grenzen**

![Einstellungen, englisches Backoffice. Batch-Größe und die Grenzfelder darunter.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-settings-limits.webp)

| Feld | Standard | Bedeutung |
|---|---|---|
| **Batch-Größe** | 25 | Wie viele Zeichenfolgen in einen API-Aufruf gehen. Für den Anfang eignen sich 10 bis 25. Der Wert muss zwischen 1 und 100 liegen. Größere Batches beenden einen Job mit weniger Aufrufen. Schlägt ein Batch fehl, wird ein größerer Abschnitt erneut versucht. |
| **Testlauf-Beispiel** | 10 | Wie viele Beispielzeichenfolgen **Schätzung** vor einem Stapel-Job zeigt. Der Wert muss zwischen 1 und 50 liegen. **Schätzung** listet so viele Quelltexte und eine Kostenschätzung auf. Es werden keine Übersetzungen gespeichert. |
| **Max. Token (0 = Standard)** | 0 | Begrenzt die Länge einer einzelnen Antwort. Lassen Sie 0 stehen, damit die Standardlänge von Grok gilt. Tragen Sie eine Zahl ein, wenn Antworten abgeschnitten werden oder kürzer sein sollen. Die Grenze gilt nur für den nächsten Aufruf und kürzt keine gespeicherten Übersetzungen. |
| **Budget USD / Monat** | 0 | Eine monatliche Obergrenze in US-Dollar, berechnet aus dem Nutzungsregister. 0 bedeutet keine Grenze. Tragen Sie den Betrag ein, den Sie ab dem ersten Tag des Monats ausgeben möchten. Erreicht das Register diesen Betrag, stoppen neue Übersetzungen, und der Bildschirm zeigt **Monthly API budget has been exhausted.** Bereits gespeicherte Arbeit bleibt erhalten. |
| **Rate-Limit / Min.** | 60 | Wie viele API-Aufrufe dieser Shop pro Minute starten darf. 60 ist ein gemäßigter Start. 0 schaltet diese lokale Grenze ab. Aufrufe über der Grenze werden übersprungen und unter **Verlauf** vermerkt. Grok kann zusätzlich eine eigene Grenze anwenden. |
| **Aufbewahrung der Protokolle (Tage)** | 30 | Wie viele Tage an Zeilen unter **Verlauf** bleiben. Mindestens 1. Ältere Zeilen werden entfernt, sobald ein neuer Aufruf gespeichert wird. Jobs, Glossar und gespeicherte Übersetzungen bleiben davon unberührt. |
| **Temperatur** | 0.2 | Wie frei das Modell Sätze umformulieren darf. Etwa 0,2 bleibt nah am Original. Werte nahe 1 verändern die Sätze deutlich stärker. Der Wert muss zwischen 0 und 1 liegen. Platzhalter und HTML werden danach trotzdem geprüft. Die nächste Übersetzung verwendet diesen Wert. |
| **Veröffentlichung / Speichern erlauben** | Ja | Darf das Modul Übersetzungen in PrestaShop schreiben? **Nein** blockiert das Speichern unter **Manuell**, in Stapel-Jobs und im **Katalog**. Die Symbole auf der Übersetzungsseite und in Shop-Formularen füllen nur das Formular aus. Das **Speichern** von PrestaShop ist davon getrennt. |

Nach **Speichern** sehen Sie eine dieser Meldungen:

- **Einstellungen gespeichert. Es wurde keine Übersetzung gestartet.** Die Einstellungen sind gespeichert, und nichts wurde übersetzt.
- **Einstellungen gespeichert. Es ist kein API-Schlüssel gespeichert, daher kann nichts übersetzt werden, bis Sie einen eingeben.** Fügen Sie den Schlüssel unter **Grok-API-Schlüssel** ein und klicken Sie erneut auf **Speichern**.

**E-Mail und Cron**

| Feld | Standard | Bedeutung |
|---|---|---|
| **E-Mail bei Abschluss benachrichtigen** | Nein | Sendet eine E-Mail, sobald ein Stapel-Job fertig ist. Der Job läuft in jedem Fall weiter. Es kommt nur die E-Mail hinzu oder entfällt. |
| **Benachrichtigungs-E-Mail** | leer | Die Adresse, die diese E-Mail erhält. Das Feld erscheint nur, wenn der Schalter darüber aktiv ist. Ist es leer, wird die E-Mail-Adresse des Shops verwendet. Das Speichern der Adresse allein verschickt keine Nachricht. Der Betreff beginnt mit dem Modulnamen, der Jobnummer und dem Status. |
| **CRON-URL** | eine Adresse mit Token | Eine geheime Adresse, mit der der Server einen Teilstapel eines wartenden Jobs verarbeiten kann. Kopieren Sie sie in den Zeitplan des Servers und veröffentlichen Sie sie nicht. Wer die Adresse kennt, kann einen Teilstapel starten. Das Öffnen von **Einstellungen** startet keinen Job. |

**Verbindung testen** prüft Schlüssel und Modell mit einem kurzen Aufruf. Es wird nichts übersetzt und nichts gespeichert.

- **Verbindung OK (N ms). Es wurde keine Übersetzung gestartet.** Die Verbindung funktioniert.
- **Verbindung konnte nicht hergestellt werden. Es wurde nichts übersetzt.** gefolgt vom Grund. Prüfen Sie Schlüssel und Modell. Details finden Sie unter **Verlauf**.

Ein praktischer Start: Schlüssel einfügen, Modell und Quell-Locale wählen, **Verbindung testen** klicken und dann **Speichern**. Lassen Sie die Zahlen auf den Standardwerten, bis ein Job sich auffällig verhält.

### 3.2. Dashboard

Öffnen Sie den Reiter **Dashboard**. Er zählt fehlende Katalogzeichenfolgen und zeigt danach die Grok-Nutzung als Karten, Diagramme und die zehn neuesten Prompts. Die Seite übersetzt nichts und ändert keine Zeichenfolgen.

![Dashboard, englisches Backoffice. Abdeckung einer Locale, Cron-Zeile und Verlaufsfilter.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-dashboard.webp)

**Abdeckung**

- **Locale:** die Shop-Locale, deren fehlende Zeichenfolgen gezählt werden.
- **Anzeigen:** zeichnet die Tabelle für diese Locale neu.
- Spalten: **Abschnitt**, **Gesamt**, **Fehlend**, **Fertig** und ein Fortschrittsbalken. Die Abschnitte heißen **Backoffice**, **Themes**, **Installierte Module**, **E-Mails** und **Weitere**. **Fehlend** ist die Anzahl der Zeichenfolgen ohne Übersetzung in dieser Locale.
- Unter der Tabelle zeigt **CRON** dieselbe Adresse wie **CRON-URL** unter **Einstellungen**.
- Eine leere Tabelle bedeutet, dass der Shop für diese Locale noch keinen Katalog hat. Legen Sie ihn unter **International → Übersetzungen** an.

Nach **Anzeigen** lautet die Meldung **Abdeckung für {Locale}. Diese Seite zählt nur Zeichenfolgen. Es wurde nichts übersetzt.**

**Nutzung**

- Voreinstellungen: **Heute**, **7 Tage**, **30 Tage**, **Diesen Monat** und **Gesamte Zeit**.
- Filter: **Von**, **Bis**, **Modell**, **Typ**, **Status** (**Beliebig**, **Erfolg**, **Fehler**), **Sprache**, **Mitarbeiter** und **Prompt oder Antwort enthält**. Klicken Sie auf **Filtern**.
- Karten: **Anfragen**, **Erfolg**, **Fehler**, **Gesendete Token**, **Empfangene Token**, **Token gesamt**, **Durchschnittliche Zeit** und **Geschätzte Kosten**. Die geschätzten Kosten sind eine lokale Berechnung und keine Rechnung von xAI. Ein Strich bedeutet, dass Grok für diesen Aufruf keine Tokenzahl geliefert hat.
- Diagramme: **Anfragen und Fehler**, **Gesendete und empfangene Token** und **Anfragen nach Modell**. Darunter stehen die Gruppen **Nach Tag**, **Nach Modell**, **Nach Typ**, **Nach Sprache** und **Nach Mitarbeiter** mit den Spalten **Gruppe**, **Aufrufe**, **Gesendet**, **Empfangen** und **Gesamt**. Eine leere Gruppe zeigt **Keine Anfragen in diesem Zeitraum.**
- **Neueste Prompts** listet die zehn letzten Aufrufe. **Ansicht** öffnet Prompt und Antwort. **Alle anzeigen** öffnet den **Verlauf** (Abschnitt 3.10). Ist die Liste leer, steht dort **Noch keine Anfragen.**

Filtern löscht den Verlauf nicht und ändert keine Übersetzungen.

Ist ein Abschnitt größtenteils leer, öffnen Sie **Manuell** für ein paar Zeichenfolgen oder **Stapel** für eine ganze Domain.

### 3.3. Manuell

Öffnen Sie **Manuell**. Hier übersetzen Sie eine Domain oder ein klassisches Modul, jeweils einige Dutzend Zeichenfolgen. Filtern speichert nichts.

![Manuell, englisches Backoffice. Abschnitt, Quelle, Ziel, Domain, Nur leere und Suche.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-manual.webp)

| Feld | Standard | Bedeutung |
|---|---|---|
| **Abschnitt** | Backoffice | Welcher Katalog gelesen wird: **Backoffice**, **Themes**, **Installierte Module**, **E-Mails** oder **Weitere**. Ein Wechsel lädt die Seite neu und zeigt nur die Felder dieses Abschnitts. Grok wird dabei nicht aufgerufen. |
| **Theme** | leer | Nur für **Themes**. Beschränkt die Liste auf ein Theme. |
| **Modul** | leer | Nur für **Installierte Module**. Beschränkt die Liste auf ein Modul. Ein klassisches Modul ohne Domain lädt alle Zeichenfolgen dieses Moduls. |
| **Domain** | leer | Dieselbe Gruppierung wie unter **International → Übersetzungen**. Wählen Sie eine Domain und klicken Sie auf **Filtern**. Ausgeblendet bei klassischen Modulen und bei Abschnitten ohne Domains. Die leere Zeile zeigt den Platzhalter **— auswählen —**. |
| **Quelle** | **Quell-Locale** aus **Einstellungen** oder en-US | Die Sprache, aus der die Zeichenfolgen stammen. Wählen Sie eine Sprache mit bereits gutem Text. |
| **Ziel** | die erste Sprache der Liste | Die Sprache, die Sie füllen möchten. Sie muss unter **International → Lokalisierung → Sprachen** angelegt sein. |
| **Nur leere** | Ja | Zeigt nur Zeichenfolgen ohne Übersetzung. Ausgeschaltet erscheinen alle Zeichenfolgen. Gespeicherte Übersetzungen werden nicht gelöscht. |
| **Suchen** | leer | Behält nur die Quell-Zeichenfolgen, die das eingegebene Wort enthalten. |

So gehen Sie vor:

1. Legen Sie **Abschnitt**, **Quelle** und **Ziel** fest.
2. Bei **Themes** wählen Sie ein **Theme**. Bei **Installierte Module** wählen Sie ein **Modul**.
3. Klicken Sie auf **Filtern**. Die Liste **Domain** wird aktualisiert. Wählen Sie eine Domain und klicken Sie erneut auf **Filtern**. Bei einem klassischen Modul lassen Sie die Domain weg, dann lädt **Filtern** alle Zeichenfolgen des Moduls.
4. Markieren Sie die gewünschten Zeilen. Mit **Alle auswählen** und **Alle abwählen** setzen oder leeren Sie die gesamte Liste.
5. Klicken Sie auf **Ausgewählte übersetzen (mit Überprüfung)**. Es öffnet sich die Tabelle **Vor dem Speichern prüfen** mit den Spalten **Quelle**, **KI-Vorschlag** und **Warnungen**. Entfernen Sie die Markierung bei Zeilen, die Sie nicht wollen, und korrigieren Sie einen Vorschlag direkt im Feld. Klicken Sie dann auf **Genehmigte speichern**.
6. Alternativ markieren Sie vor dem Übersetzen **Jetzt speichern (Überprüfung überspringen)**. Gültige Zeilen werden dann sofort geschrieben, ohne die Prüftabelle.

Die Liste der Zeichenfolgen hat die Spalten **Quelle**, **Aktuell** und **Status** (**leer** oder **ausgefüllt**).

Meldungen, die Sie sehen können:

- **N Zeichenfolgen geladen. Markieren Sie die gewünschten Zeilen und klicken Sie auf „Ausgewählte übersetzen“. Es ist noch nichts gespeichert.**
- **N Zeichenfolgen aus dem gesamten Modul geladen. Markieren Sie die gewünschten Zeilen und klicken Sie auf „Ausgewählte übersetzen“. Es ist noch nichts gespeichert.** Das ist die Liste eines klassischen Moduls.
- **Dieses Modul hat keine Übersetzungs-Domain. Klicken Sie auf „Filtern“, um alle Zeichenfolgen des Moduls zu laden. Es wurde nichts an Grok gesendet.**
- **Keine Zeichenfolgen entsprechen diesem Filter. Es wurde nichts an Grok gesendet.**
- **Keine Zeichenfolgen entsprechen diesem Filter. Deaktivieren Sie „Nur leere“ oder dieses Modul hat keine klassischen Zeichenfolgen. Es wurde nichts an Grok gesendet.**
- **Es wurde nichts übersetzt. Wählen Sie eine Domain und klicken Sie dann auf „Filtern“, um die Zeichenfolgen zu laden.**
- **Es wurde nichts übersetzt. Wählen Sie ein Theme und klicken Sie dann auf „Filtern“.**
- **Es wurde nichts übersetzt. Wählen Sie ein Modul und klicken Sie dann auf „Filtern“.**
- **Es wurde nichts übersetzt. Markieren Sie mindestens eine Zeile.**
- **Es wurde nichts übersetzt. Es ist kein Grok-API-Schlüssel vorhanden. Öffnen Sie die Einstellungen und fügen Sie den Schlüssel ein.**
- **Die Überprüfung ist bereit. Es wird nichts gespeichert, bis Sie auf „Genehmigte speichern“ klicken.**
- **Gespeichert. Die genehmigten Zeichenfolgen wurden für die Zielsprache geschrieben.**
- **N gespeichert. Es wurden nur die markierten Zeilen geschrieben.**
- **Es wurde nichts gespeichert. Markieren Sie bei den Zeilen, die Sie behalten möchten, „OK“.**
- **Nicht gespeichert wegen fehlerhafter Platzhalter oder HTML: N.** Diese Zeilen wurden übersprungen. Korrigieren Sie Platzhalter und Tags, sodass sie zur Quelle passen, und speichern Sie erneut.
- **Es wurde nichts gespeichert. Aktivieren Sie „Veröffentlichung erlauben“ in den Einstellungen.**
- **Es wurde nichts übersetzt. Diese Zeilen stehen nicht in der aktuellen Liste. Klicken Sie auf „Filtern“ und markieren Sie sie erneut.**

Beim Wechsel des Abschnitts erscheint außerdem ein kurzer Hinweis, zum Beispiel **Abschnitt ist Backoffice. Theme und Modul werden nicht verwendet.**, zusammen mit **Es wurde nichts an Grok gesendet.** Dasselbe gilt für **Themes**, **Installierte Module**, **E-Mails** und **Weitere**.

### 3.4. Stapel

Öffnen Sie **Stapel**. Hier legen Sie einen Job für viele Domains und Sprachen an. **Schätzung** speichert nichts. **Job starten** fügt eine Zeile unter **Jobs** hinzu. Geschrieben wird erst, wenn der Job verarbeitet wird und **Veröffentlichung / Speichern erlauben** aktiv ist.

![Stapel, englisches Backoffice. Abschnitt, Quelle, Ziele, Domains, Richtlinie und Testlauf.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-bulk.webp)

| Feld | Standard | Bedeutung |
|---|---|---|
| **Abschnitt** | Backoffice | Welchen Katalog der Job liest. Die Seite lädt neu und zeigt **Theme** nur bei **Themes** und **Modul** nur bei **Installierte Module**. Zeichenfolgen außerhalb des gewählten Abschnitts werden nicht berücksichtigt. Ein Wechsel des Abschnitts startet keinen Job. |
| **Theme** | leer | Nur für **Themes**. Andere Themes werden ausgelassen. |
| **Modul** | leer | Nur für **Installierte Module**. Ein klassisches Modul hat keine Domains, daher umfassen **Schätzung** und **Job starten** alle Zeichenfolgen des Moduls. |
| **Quelle** | **Quell-Locale** aus **Einstellungen** oder en-US | Die Locale, die der Job als Original behandelt. Jedes Ziel wird aus dieser Locale übersetzt. |
| **Ziele** | nichts markiert | Die Locales, die der Job füllt. Markieren Sie eine oder mehrere. Ein Klick ohne Strg ersetzt die bisherige Auswahl. Der Job speichert einen eigenen Satz Zeichenfolgen für jede markierte Locale. |
| **Domains** | nichts markiert | Die Domains des Jobs. Halten Sie Strg oder Cmd gedrückt, um mehrere Zeilen zu markieren. Nicht markierte Domains werden übersprungen. Lassen Sie alles unmarkiert nur dann, wenn Sie einen leeren Job wollen. Ausgeblendet bei klassischen Modulen. |
| **Richtlinie** | Leere füllen | **Leere füllen** überspringt Zeichenfolgen, die bereits eine Übersetzung haben. **Alles überschreiben** sendet jede Zeichenfolge und ersetzt fertige Übersetzungen, sofern der Job speichern darf. **Veraltet, wenn gleich der Quelle** sendet Zeichenfolgen, deren Übersetzung noch identisch mit dem Original ist. |
| **Testlauf-Job** | Nein | Führt das Modell aus, schreibt die Antwort aber nicht in PrestaShop. Der Job erscheint trotzdem unter **Jobs**. Katalogdateien und Datenbankübersetzungen bleiben unverändert. |

So gehen Sie vor:

1. Legen Sie **Abschnitt**, **Quelle** und **Ziele** fest.
2. Bei **Themes** wählen Sie ein **Theme**. Bei **Installierte Module** wählen Sie ein **Modul**.
3. Wählen Sie **Domains**, sobald die Liste erscheint. Halten Sie dafür Strg oder Cmd gedrückt.
4. Klicken Sie auf **Schätzung**. Prüfen Sie die Anzahl, die Token-Schätzung, die Kostenschätzung und die **Stichprobe**. Es wurde nichts an Grok gesendet und nichts gespeichert. Sie sehen: **Nur Schätzung: N Zeichenfolgen, ~N Token, ~$N. Es wurde nichts an Grok gesendet und nichts gespeichert.**
5. Klicken Sie auf **Job starten**. Das Modul öffnet diesen Job. Die Meldung lautet: **Job #N wartet (N Zeichenfolgen, geschätzt $N). Er wurde noch nicht ausgeführt.**

Fehlt eine erforderliche Auswahl, erhalten Sie eine dieser Meldungen:

- **Es wurde nichts gestartet. Wählen Sie mindestens eine Zielsprache aus.**
- **Es wurde nichts gestartet. Wählen Sie ein Theme aus.**
- **Es wurde nichts gestartet. Wählen Sie ein Modul aus.**
- **Es wurde nichts gestartet. Es ist kein Grok-API-Schlüssel vorhanden. Öffnen Sie die Einstellungen und fügen Sie den Schlüssel ein. Es wurde kein Job angelegt.**

### 3.5. Jobs

Öffnen Sie **Jobs**. Die Liste zeigt jeden Job. Ist sie leer, steht dort **Noch keine Jobs.**

![Jobs, englisches Backoffice. Die Jobliste mit Status, Locales, Fortschritt, Kosten, Mitarbeiter und Datum.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-jobs.webp)

Spalten: **#**, **Status**, **Locales**, **Fortschritt**, **Kosten**, **Mitarbeiter**, **Datum** und **Öffnen**.

Die Statusbezeichnungen auf diesem Bildschirm bleiben englisch: **pending**, **running**, **paused**, **cancelled**, **completed**, **completed_with_errors** und **failed**.

Klicken Sie bei einer Zeile auf **Öffnen**. Die Details zeigen **Status**, den Fortschritt als erledigt/gesamt, **fehlgeschlagen**, **übersprungen**, die Kosten, die Mitarbeiternummer und **Testlauf**, falls dieser Schalter aktiv war. Darunter liegt ein Fortschrittsbalken.

Schaltflächen eines geöffneten Jobs:

- **Teilstapel verarbeiten** übersetzt einen Teilstapel und stoppt dann. Meldung: **Ein Teilstapel wurde verarbeitet. Prüfen Sie die Zeilen unten, um zu sehen, was gespeichert, übersprungen oder fehlgeschlagen ist.** Ist nichts mehr offen, erscheint **Der Job hat keine wartenden Zeichenfolgen mehr.**
- **Automatische Verarbeitung** fordert den nächsten Teilstapel an, bis der Job fertig ist oder stoppt.
- **Pause** stoppt weitere Teilstapel. Meldung: **Job pausiert. Es werden keine weiteren Zeichenfolgen übersetzt, bis Sie ihn fortsetzen.**
- **Fortsetzen** bringt einen pausierten Job zurück in die Warteschlange. Meldung: **Job wartet wieder. Er läuft nicht von selbst weiter. Klicken Sie auf „Teilstapel verarbeiten“, „Automatische Verarbeitung“ oder lassen Sie den Cron-Aufruf ihn starten.**
- **Fehlgeschlagene wiederholen** setzt fehlgeschlagene Zeilen zurück in die Warteschlange. Meldung: **N fehlgeschlagene Elemente erneut versucht.**
- **Rollback** fragt **Diesen Job zurückrollen?** und stellt den vorherigen Text dort wieder her, wo das Modul eine Kopie behalten hat. Meldung: **Rollback: N Übersetzungen wiederhergestellt.**
- **Fehler-CSV** lädt die fehlgeschlagenen Zeilen herunter.
- **Nur Fehlgeschlagene** zeigt nur Zeilen mit dem Status **failed**.
- **Warteschlange überprüfen** öffnet **Überprüfen**.

Auf diesem Bildschirm gibt es keine Schaltfläche **Abbrechen**. Ein Job, der nicht fertig werden soll, bleibt einfach auf **paused** stehen.

Die Spalten der Zeilentabelle heißen **ID**, **Domain**, **Locale**, **Status**, **Quelle**, **Neu** und **Fehler**. Auch die Status der Einzelelemente bleiben englisch: **pending**, **processing**, **done**, **failed**, **skipped** und **rolled_back**.

Erreicht der Shop während eines Teilstapels sein eigenes Limit pro Minute, pausiert der Job automatisch. Die Fehlerzeile lautet dann **Rate limit — job auto-paused. Resume later.** Klicken Sie später auf **Fortsetzen** und danach auf **Teilstapel verarbeiten**.

Ein Testlauf-Job ruft Grok auf und speichert den Vorschlag am Job. Der Katalog wird dabei nicht geändert.

### 3.6. Überprüfen

Öffnen Sie **Überprüfen**. Das ist die Warteschlange der Ergebnisse aus Stapel-Jobs, die eine Kontrolle brauchen. Die Seite zeigt **Warteschlange zur Überprüfung (Qualitätswert / Flags).** Ist die Warteschlange leer, steht dort **Die Warteschlange ist leer.**

![Überprüfen, englisches Backoffice. Die Warteschlange zur Überprüfung.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-review.webp)

Spalten: **ID**, **Wert**, **Domain**, **Quelle**, **KI**, **Flags**, **Genehmigen** und **Ablehnen**.

Eine Zeile landet hier, wenn die Qualitätsprüfung unter 70 liegt, wenn Platzhalter oder HTML nicht übereinstimmen oder wenn die Übersetzung deutlich länger ist als das Original. Durfte der Job veröffentlichen und hat die Zeichenfolge die Prüfung bestanden, enthält der Katalog den Vorschlag womöglich schon. **Genehmigen** und **Ablehnen** ändern nur diese Warteschlange. Sie schreiben keine neue Übersetzung und stellen auch die alte nicht wieder her. Nach jedem Klick erscheint **Überprüfung aktualisiert.**, und die Zeile verschwindet aus der Warteschlange.

Die Prüftabelle unter **Manuell** ist ein eigener Bildschirm. Dort gibt es die Schaltfläche **Genehmigte speichern**.

### 3.7. Katalog

Öffnen Sie **Katalog**. Hier übersetzen Sie Felder von Produkten, Kategorien oder CMS-Seiten. Das ist nicht derselbe Katalog wie unter **International → Übersetzungen**. Ein Durchlauf verarbeitet höchstens 100 Datensätze.

![Katalog, englisches Backoffice. Entität, Felder, Quellsprache, Zielsprache, Nur leere und Beginn nach ID.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-catalog.webp)

| Feld | Standard | Bedeutung |
|---|---|---|
| **Entität** | product | Welche Datensätze gelesen werden: **product**, **category** oder **cms**. Diese drei Begriffe bleiben englisch. Die Seite lädt neu und zeigt nur die Feldliste dieses Typs. Ein Wechsel übersetzt nichts. Meldung: **Felder für {Entität} werden angezeigt. Es wurde nichts übersetzt.** |
| **Felder** | alle Felder der Entität | Welche Texte dieser Batch sendet. Halten Sie Strg oder Cmd gedrückt, um mehrere zu wählen. **Titel** ist der Produktname, der Kategoriename oder der Titel der CMS-Seite. **Inhalt** ist der Text einer CMS-Seite. Lassen Sie **Freundliche URL** weg, wenn Links unverändert bleiben sollen. Nur die gewählten Felder werden übersetzt. |
| **Quellsprache** | die Sprachliste des Shops | Die Sprache, aus der die Felder kopiert werden. Die Quellsprache selbst wird nicht verändert. |
| **Zielsprache** | die Sprachliste des Shops | Die Sprache, die die Übersetzung erhält. Sie muss sich von der Quelle unterscheiden. Es werden bis zu 100 Datensätze geschrieben. |
| **Nur leere** | Ja | Überspringt Felder, die in der Zielsprache bereits Text haben. **Nein** kann diesen Text überschreiben, sofern das Veröffentlichen erlaubt ist. |
| **Beginn nach ID** | 0 | Überspringt Datensätze bis zu dieser ID. Bei 0 beginnt die Verarbeitung beim ersten Datensatz. Nach einem Durchlauf zeigt das Feld die zuletzt gelesene ID. Klicken Sie erneut auf die Schaltfläche, um weiterzumachen. |

Produktfelder: **Titel**, **Kurzbeschreibung**, **Beschreibung**, **Meta-Titel**, **Meta-Beschreibung** und **Freundliche URL**.

Kategoriefelder: **Titel**, **Beschreibung**, **Meta-Titel**, **Meta-Beschreibung** und **Freundliche URL**.

CMS-Felder: **Titel**, **Meta-Beschreibung**, **Meta-Schlüsselwörter**, **Inhalt** und **Freundliche URL**.

Klicken Sie auf **Batch übersetzen (max. 100)**. Am Ende lautet die Meldung **Katalog abgeschlossen: N gespeichert, N fehlgeschlagen.** Unter dem Formular sehen Sie außerdem die Zähler **Gespeichert** und **fehlgeschlagen**.

- **Es wurde nichts übersetzt. Es ist kein Grok-API-Schlüssel vorhanden. Öffnen Sie die Einstellungen und fügen Sie den Schlüssel ein.**
- **Es wurde nichts gespeichert. Aktivieren Sie „Veröffentlichung erlauben“ in den Einstellungen.**
- **Es wurde nichts übersetzt. Quell- und Zielsprache müssen verschieden sein.**
- **Es wurde nichts übersetzt. Wählen Sie mindestens ein Feld aus.**

### 3.8. Glossar

Öffnen Sie **Glossar**. Die Liste enthält Wörter, die das Modell unverändert lassen oder immer gleich wiedergeben soll. Ein neuer Eintrag schreibt vorhandene Übersetzungen nicht um. Die nächste Übersetzung berücksichtigt jedoch die Liste.

![Glossar, englisches Backoffice. Begriff hinzufügen und das CSV-Formular.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-glossary.webp)

| Feld | Standard | Bedeutung |
|---|---|---|
| **Quellbegriff** | leer | Die Formulierung, wie sie in der Quellsprache vorkommt. Geben Sie das genaue Wort oder die Wendung ein, bei Bedarf mit Großschreibung. Pflichtfeld. |
| **Ziel-Locale** | leer | Beschränkt den Eintrag auf eine Ziel-Locale, zum Beispiel de-DE. Leer bedeutet: der Eintrag gilt für jedes Ziel. Eine ausgefüllte Locale wird für andere Sprachen ignoriert. |
| **Zielbegriff** | leer | Die Formulierung, die in der Übersetzung erscheinen soll. Leer lassen Sie das Feld nur, wenn **Nicht übersetzen** aktiv ist. |
| **Nicht übersetzen** | Nein | **Ja** weist das Modell an, den Quellbegriff unverändert zu übernehmen. Verwenden Sie das für Markennamen, SKUs und Platzhalter. **Nein** bedeutet, dass der **Zielbegriff** die gewünschte Übersetzung ist. |

Klicken Sie auf **Hinzufügen**.

- **Glossareintrag hinzugefügt. Bereits gespeicherte Übersetzungen wurden nicht geändert.**
- **Nichts hinzugefügt. Geben Sie einen Quellbegriff ein.**

Die Tabelle hat die Spalten **Quelle**, **Locale**, **Ziel**, **Nicht übersetzen** (**Ja** oder **Nein**) und **Löschen**. Ist die Tabelle leer, steht dort **Noch keine Glossareinträge.** Mit **Löschen** entfernen Sie die Zeile. Die Meldung lautet **Glossareintrag gelöscht.**

**Glossar-CSV**

| Feld | Standard | Bedeutung |
|---|---|---|
| **CSV-Datei** | leer | Die Datei braucht die Spalten source_term, target_locale, target_term und do_not_translate. **CSV importieren** fügt alle lesbaren Zeilen hinzu. **CSV exportieren** lädt die aktuelle Liste herunter und ignoriert das Dateifeld. Der Export ändert das Glossar nicht. |

- **N Zeilen importiert.**
- **CSV-Datei fehlt.** Wählen Sie eine Datei und klicken Sie erneut auf **CSV importieren**.
- **CSV-Datei kann nicht geöffnet werden.** Speichern Sie die Datei als CSV und versuchen Sie es noch einmal.

### 3.9. Ausschlüsse

Öffnen Sie **Ausschlüsse**. Die Liste enthält Quell-Zeichenfolgen, die das Modul überspringen soll. Eine passende Zeichenfolge wird nicht an Grok gesendet und nicht aus PrestaShop gelöscht. Das Speichern eines Musters ändert bereits gespeicherte Zeichenfolgen nicht.

![Ausschlüsse, englisches Backoffice. Muster, Typ und die Mustertabelle.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-excludes.webp)

| Feld | Standard | Bedeutung |
|---|---|---|
| **Muster** | leer | Der Text, der mit jeder Quell-Zeichenfolge verglichen wird. Pflichtfeld. |
| **Typ** | exact | **exact** passt auf die gesamte Zeichenfolge, **prefix** auf den Anfang, **contains** auf einen Teil und **regex** ist ein PHP-regulärer Ausdruck, der genau so angewendet wird, wie er geschrieben ist. Testen Sie zuerst ein kurzes Muster. Ein falscher Typ kann zu viel oder gar nichts ausschließen. |

Klicken Sie auf **Hinzufügen**.

- **Ausschlussmuster hinzugefügt. Passende Zeichenfolgen werden beim nächsten Durchlauf übersprungen. Jetzt wurde nichts übersetzt.**
- **Nichts hinzugefügt. Geben Sie ein Muster ein.**

Die Tabelle hat die Spalten **Muster**, **Typ**, **Aktiv** und **Löschen**. In der Spalte **Aktiv** steht 1, wenn das Muster verwendet wird. Ist die Tabelle leer, steht dort **Noch keine Muster.** Mit **Löschen** entfernen Sie die Zeile. Die Meldung lautet **Muster gelöscht.**

### 3.10. Verlauf

Öffnen Sie **Verlauf**. Das ist die vollständige Liste aller Aufrufe an Grok, einschließlich Verbindungstests und Aufrufen, die blockiert wurden, bevor sie gesendet werden konnten. Die Diagramme und die zehn neuesten Prompts finden Sie im **Dashboard**. Ein Klick auf **Alle anzeigen** dort öffnet diesen Reiter.

![Verlauf, englisches Backoffice. Die Aufrufliste und Verlauf löschen.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-history.webp)

Spalten: **ID**, **Wann**, **Status**, **Typ**, **Modell**, **Sprachen**, **Gesendet**, **Empfangen**, **Gesamt**, **Zeit**, **Prompt** und **Ansicht**.

**Typ** ist eines von **Manuell**, **Übersetzungsseite**, **Stapel-Job**, **Katalog**, **Verbindungstest**, **Übersetzen** oder **Nicht gesendet**. **Status** ist **Erfolg** oder **Fehler**.

**Ansicht** öffnet Prompt und **Antwort** sowie **HTTP**, **Gesendet**, **Empfangen** und **Gesamt**. **Zurück zur Liste** bringt Sie zur Tabelle zurück. Wurde die Zeile entfernt, lautet die Meldung **Dieser Verlaufseintrag existiert nicht mehr.** Lassen sich die Details nicht laden, erscheint **Diese Anfrage konnte nicht geladen werden.**

Mit **Zurück** und **Weiter** blättern Sie durch die Seiten. Die Zeile zeigt **Seite N / N**.

**Verlauf löschen** fragt **Gespeicherten Verlauf löschen? Gespeicherte Übersetzungen bleiben erhalten.** Die Bestätigung löscht nur diese Zeilen. Meldung: **Verlauf gelöscht. Gespeicherte Übersetzungen wurden nicht geändert.** Ist die Liste leer, steht dort **Noch keine Anfragen.**

Die **Aufbewahrung der Protokolle (Tage)** unter **Einstellungen** entfernt außerdem alle Zeilen, die älter sind als diese Anzahl Tage, sobald ein neuer Aufruf gespeichert wird.

### 3.11. Updates

Öffnen Sie **Updates**. Diese Seite prüft, ob ein neueres Paket veröffentlicht wurde. Übersetzt wird hier nichts.

![Updates, englisches Backoffice. Manuelle Prüfung, automatische Benachrichtigungen und Produktseite.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-updates.webp)

| Feld | Standard | Bedeutung |
|---|---|---|
| **Manuelle Prüfung** | die Schaltfläche **Jetzt prüfen** | Fragt den Herausgeber einmal ab. **Modul ist auf dem neuesten Stand!** bedeutet, dass diese Installation dem aktuellen Paket entspricht. **Neue Version verfügbar!** bedeutet, dass ein neueres Paket veröffentlicht wurde. Laden Sie es auf der Produktseite herunter und installieren Sie es über den **Modulmanager**. |
| **Automatische Benachrichtigungen** | Aktiviert | **Aktiviert** lässt das Backoffice einen Hinweis zeigen, sobald ein neueres Paket existiert. **Deaktiviert** schaltet diesen Hinweis aus. Klicken Sie auf **Speichern**, um Ihre Wahl zu behalten. Die Deinstallation des Moduls löscht diese Wahl nicht. |
| **Produktseite** | ein Link mit dem Modulnamen | Öffnet die Seite des Moduls. Die Adresse steht in Abschnitt 7. |

Gibt es ein neueres Paket, zeigt das Backoffice unter Umständen zusätzlich **Neue Version verfügbar, weitere Informationen unter http://MyPresta.eu** mit dem Link **Weitere Details im Changelog**.

### 3.12. Schaltflächen unter International → Übersetzungen

Öffnen Sie **International**, dann **Übersetzungen**, und öffnen Sie einen Katalog. Ist **Einzelne Feld-Schaltflächen – International → Übersetzungen** auf **Ja** gesetzt, hat jedes Feld eine Schaltfläche **Übersetzen**. Ein Klick füllt dieses Feld. Gespeichert wird die Seite weiterhin mit **Speichern** von PrestaShop.

Ist **Einzelne Feld-Kontrollkästchen – International → Übersetzungen** auf **Ja** gesetzt, zeigt die Seite außerdem eine Leiste **Grok-Übersetzungen**.

- **Quelle** wird aus der **Quell-Locale** unter **Einstellungen** übernommen. Ist diese Einstellung leer, verwendet die Leiste en-US. Das Feld können Sie ändern.
- **Ziel** ist die Sprache des gerade geöffneten Katalogs.
- **Alle auswählen**, **Alle abwählen** und **Leere auswählen** ändern die Markierungen.
- **Leere übersetzen** füllt leere Felder. **Ausgewählte übersetzen** füllt die markierten Felder.
- Der Hinweis lautet **Füllt die Felder aus. Speichern Sie mit der PrestaShop-Schaltfläche.**
- Während der Übersetzung zeigt die Leiste **Übersetze…**. Ist sie fertig, zeigt sie **Fertig**.
- **Ausgewählt** zeigt, wie viele Felder markiert sind.
- **Markieren Sie mindestens ein Feld.** erscheint, wenn Sie auf **Ausgewählte übersetzen** klicken, ohne dass etwas markiert ist.
- **Füllen Sie zuerst das Feld der Quellsprache aus.** erscheint, wenn der Quelltext leer ist.
- **Die E-Mail-Datei der Quellsprache wurde nicht gefunden.** erscheint auf dem E-Mail-Bildschirm, wenn die Quelldatei fehlt.
- **Leere in diesem Bereich übersetzen** füllt die leeren Zeichenfolgen des gerade angezeigten Abschnitts.

Diese Schaltflächen ersetzen das **Speichern** auf der PrestaShop-Seite nicht. **Veröffentlichung / Speichern erlauben** blockiert sie nicht, weil sie nur das Formular ausfüllen.

### 3.13. Schaltflächen auf Produkt-, Kategorie- und CMS-Formularen

Öffnen Sie ein Produkt, eine Kategorie, eine CMS-Seite oder ein anderes Backoffice-Formular mit einem Feld pro Sprache. Ist **Einzelne Feld-Schaltflächen – Shop-Formulare** auf **Ja** gesetzt, hat jedes dieser Felder eine Schaltfläche **Übersetzen**. Ein Klick füllt das Feld aus der Quellsprache desselben Formulars.

![Produktformular, englisches Backoffice. Die Leiste Grok-Übersetzungen unter den Beschreibungsfeldern.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-product.webp)

Ist **Einzelne Feld-Kontrollkästchen – Shop-Formulare** auf **Ja** gesetzt, zeigt das Formular außerdem die Leiste **Grok-Übersetzungen**.

- **Quelle** beginnt mit der **Quell-Locale**, oder mit en-US, wenn diese Einstellung leer ist.
- **Ziel** listet die übrigen Shop-Sprachen und **alle anderen Sprachen** auf.
- **Alle auswählen**, **Alle abwählen**, **Leere auswählen**, **Leere übersetzen** und **Ausgewählte übersetzen** funktionieren wie auf der Übersetzungsseite.
- Der Hinweis lautet **Füllt die Felder aus. Speichern Sie mit der PrestaShop-Schaltfläche.**
- **Markieren Sie mindestens ein Feld.**, **Füllen Sie zuerst das Feld der Quellsprache aus.** und **Das Feld der Quellsprache befindet sich nicht auf dieser Seite.** sagen Ihnen, was zu korrigieren ist.
- **Das Ziel ist keine Sprache dieses Shops.** bedeutet, dass das Ziel zu keiner Sprache des Shops passt.
- Die Zeile über einem Feld kann **Übersetzen von** dem Quellnamen **nach** dem Zielnamen lauten.

Klicken Sie in diesem Formular auf **Speichern** von PrestaShop, um die ausgefüllten Felder zu sichern. Die Leiste speichert das Produkt nicht selbst.

## 4. Shop-Frontend

Das Shop-Theme zeigt dieses Modul nicht. Kunden sehen keine Übersetzungsschaltfläche, kein Formular und keine Statusseite.

Die einzige Adresse außerhalb des Backoffice ist die **CRON-URL** unter **Einstellungen**. Sie wird auch unter der Abdeckungstabelle im **Dashboard** wiederholt. Kopieren Sie diese Adresse in den Zeitplan des Servers. Jeder Aufruf verarbeitet einen Teilstapel des ersten wartenden oder laufenden Jobs und beendet sich dann. Das Öffnen der **Einstellungen** ruft die Adresse nicht auf.

| Was Sie sehen | Was zu tun ist |
|---|---|
| Eine JSON-Zeile mit dem Ergebnis des Teilstapels | Der Teilstapel wurde ausgeführt. Öffnen Sie **Jobs** und lesen Sie die Zeilen. |
| **No pending jobs** | Es wartet kein Job. Legen Sie unter **Stapel** einen an, oder der vorherige Job ist bereits fertig, pausiert oder abgebrochen. Dieser Text bleibt englisch. |
| **Forbidden** | Die Adresse ist falsch, oder der Token wurde bei einer Neuinstallation ersetzt. Kopieren Sie die **CRON-URL** erneut. Veröffentlichen Sie die Adresse nicht. Dieser Text bleibt englisch. |

Fügen Sie keine eigenen Parameter an. Die Adresse, die Sie kopieren, ist genau die, die das Modul liest.

## 5. Probleme

**Kein Grok-API-Schlüssel.** und **Einstellungen öffnen** erscheinen auf jedem Reiter. Fügen Sie den Schlüssel unter **Einstellungen** ein, klicken Sie auf **Verbindung testen** und dann auf **Speichern**.

**Der Shop benötigt mindestens zwei Sprachen.** Legen Sie unter **International → Lokalisierung → Sprachen** eine weitere Sprache an und öffnen Sie das Modul erneut.

**Verbindung konnte nicht hergestellt werden. Es wurde nichts übersetzt.** Der Grund steht direkt hinter diesem Satz. Prüfen Sie Schlüssel und Modell und ob der Server die Grok-Adresse erreicht. Öffnen Sie **Verlauf** und klicken Sie in der Fehlerzeile auf **Ansicht**.

**Monthly API budget has been exhausted.** Diese Meldung bleibt englisch. Erhöhen Sie **Budget USD / Monat** oder setzen Sie es auf 0, wenn Sie keine Obergrenze wollen, und klicken Sie auf **Speichern**. Bereits gespeicherter Text bleibt erhalten.

**Grok rate limit (429). Try again later.** Diese Meldung bleibt englisch. Warten Sie und starten Sie den Teilstapel erneut. Zeigt der Job **Rate limit — job auto-paused. Resume later.**, klicken Sie auf **Fortsetzen** und dann auf **Teilstapel verarbeiten**. Tritt das wiederholt auf, senken Sie die **Batch-Größe** oder vergrößern Sie den Abstand zwischen den Cron-Aufrufen. **Rate-Limit / Min.** ist die eigene Grenze des Shops. Grok kann einen Aufruf trotzdem ablehnen.

**Es wurde nichts gespeichert. Aktivieren Sie „Veröffentlichung erlauben“ in den Einstellungen.** Setzen Sie **Veröffentlichung / Speichern erlauben** auf **Ja**, klicken Sie auf **Speichern** und versuchen Sie es erneut. Die Symbole auf Formularen füllen weiterhin nur das Formular aus.

**Nicht gespeichert wegen fehlerhafter Platzhalter oder HTML: N.** Der Vorschlag hat einen Platzhalter oder ein Tag verändert. Passen Sie den Vorschlag an das Original an oder lassen Sie die Zeile unmarkiert und klicken Sie erneut auf **Genehmigte speichern**.

**Es wurde nichts übersetzt. Wählen Sie ein Theme und klicken Sie dann auf „Filtern“.** oder **Wählen Sie ein Modul.** Der Abschnitt braucht diese Auswahl, bevor die Liste geladen werden kann.

**Keine Zeichenfolgen entsprechen diesem Filter. Es wurde nichts an Grok gesendet.** Deaktivieren Sie **Nur leere**, leeren Sie **Suchen** oder wählen Sie eine andere Domain.

**CSV-Datei fehlt.** oder **CSV-Datei kann nicht geöffnet werden.** Wählen Sie eine CSV-Datei mit den vier Spalten und klicken Sie erneut auf **CSV importieren**.

**Die E-Mail-Datei der Quellsprache wurde nicht gefunden.** Öffnen Sie unter **International → Übersetzungen** den E-Mail-Abschnitt einer Sprache, für die bereits eine Mail-Datei existiert, oder erzeugen Sie die E-Mail-Übersetzungen vorher in PrestaShop.

**Dieser Verlaufseintrag existiert nicht mehr.** Die Zeile wurde geleert oder durch **Aufbewahrung der Protokolle (Tage)** entfernt. Die gespeicherte Übersetzung ist weiterhin im Shop vorhanden.

Der Menüeintrag fehlt, oder das Backoffice meldet, dass der Controller nicht gefunden wurde. Öffnen Sie den **Modulmanager**, suchen Sie **AI Translations with Grok** und klicken Sie auf **Konfigurieren**. Dadurch wird der Menüeintrag unter **International** neu angelegt. Ist das Modul in der Liste gar nicht mehr vorhanden, installieren Sie die ZIP-Datei erneut.

Die Installation bricht mit **Die Modultabellen konnten nicht erstellt werden.** ab. Der Datenbankbenutzer darf keine Tabellen anlegen. Korrigieren Sie die Datenbankrechte und klicken Sie erneut auf **Installieren**. **Der Menüreiter konnte nicht hinzugefügt werden.** bedeutet, dass der Menüeintrag nicht angelegt werden konnte. Klicken Sie nach einer erfolgreichen Installation auf **Konfigurieren** oder installieren Sie erneut.

## 6. Für Entwickler

### 6.1. Überblick

Technischer Name `myaitranslationsgrok`, Version `1.2.0`, Autor MyPresta.eu, Modul-Reiter `administration`. Der Name in der Modulliste und die Beschriftung im Menü **International** lautet **AI Translations with Grok**. Die Klasse heißt `myaitranslationsgrok`. Das Minimum in `ps_versions_compliancy` ist `1.7.0.0`.

`getContent()` ruft `ensureTab()` auf und leitet zu `AdminMyaitranslationsgrok` weiter. Die Einstellungen liest `MyaitgkConfigService` (Schlüssel `MYAITGK_*`). Der API-Schlüssel wird verschlüsselt in `MYAITGK_API_KEY_ENC` gespeichert. Übersetzungsaufrufe laufen über `MyaitgkTranslateService` zu `MyaitgkGrokTranslationProvider`, der JSON per POST an `https://api.x.ai/v1/chat/completions` sendet. Schreibvorgänge im Katalog laufen über `MyaitgkTranslationAdapter`. Schreibvorgänge für Produkte, Kategorien und CMS-Seiten laufen über `MyaitgkCatalogTranslateService`. Nach dem Speichern einer Katalogübersetzung ruft das Modul `Tools::clearCache()` auf.

Das Modul definiert weder `enable()` noch `disable()`. Das Deaktivieren im **Modulmanager** führt keine zusätzliche Bereinigung aus. Erst die Deinstallation entfernt den Menüreiter, die Tabellen und die Schlüssel `MYAITGK_*`.

### 6.2. Dateien

- `myaitranslationsgrok.php` - Installation, Deinstallation, Hooks, Reiter und Konfiguration der Feldschaltflächen.
- `controllers/admin/AdminMyaitranslationsgrokController.php` - jeder Backoffice-Reiter und alle AJAX-Aktionen.
- `controllers/front/cron.php` - verarbeitet einen Teilstapel für die Cron-Adresse.
- `lib/updateChecker.php` - der Reiter **Updates** und die Versionsprüfung.
- `sql/install.php`, `sql/uninstall.php` - erstellen bzw. löschen die Tabellen.
- `src/Admin/MyaitgkForms.php` - HelperForm-Felder und die `desc`-Texte.
- `src/Admin/MyaitgkSectionHelp.php` - das Panel **Hilfe**.
- `src/Service/MyaitgkConfigService.php` - Schlüssel, Modellliste, Cron-Token.
- `src/Service/MyaitgkTranslateService.php` - Budget, Rate-Limit, Glossar, Ausschlüsse und Speichern.
- `src/Service/MyaitgkBulkJobFactory.php` - legt aus **Stapel** einen Job an.
- `src/Service/MyaitgkCatalogTranslateService.php` - Batches für Produkte, Kategorien und CMS-Seiten.
- `src/Service/MyaitgkDashboardService.php` - Zähler für die Abdeckung.
- `src/Service/MyaitgkRateLimiter.php` - Limit pro Minute, gespeichert in `var/rate_limit.json`.
- `src/Provider/MyaitgkGrokTranslationProvider.php` - die Anfrage an xAI.
- `src/Provider/MyaitgkPromptBuilder.php` - System- und Benutzer-Prompts.
- `src/Job/MyaitgkJobWorker.php` - Teilstapel, Wiederholung und E-Mail nach Abschluss.
- `src/Job/MyaitgkJobRepository.php`, `src/Job/MyaitgkJobStatuses.php` - Jobzeilen und Statuskonstanten.
- `src/Quality/MyaitgkPlaceholderValidator.php`, `MyaitgkHtmlValidator.php`, `MyaitgkPsNativeValidator.php`, `MyaitgkEmailHtmlPipeline.php`, `MyaitgkQualityScorer.php` - Prüfungen vor dem Speichern.
- `src/Glossary/MyaitgkGlossaryRepository.php`, `MyaitgkExcludePatternRepository.php` - Glossar und Ausschlüsse.
- `src/Audit/MyaitgkRequestLogRepository.php` - **Verlauf** und der Bericht des Dashboards.
- `src/Audit/MyaitgkSnapshotService.php` - Rollback-Kopien.
- `src/Security/MyaitgkApiKeyEncryptor.php` - OpenSSL-Verschlüsselung des Schlüssels.
- `src/Adapter/MyaitgkTranslationAdapter.php`, `MyaitgkLegacyModuleCatalogue.php` - PrestaShop-Kataloge und klassische Module mit `translations/{iso}.php`.
- `views/templates/admin/configure.tpl` und `views/templates/admin/_partials/*.tpl` - die Reiter.
- `views/js/admin.js`, `admin-help.js`, `history-charts.js`, `translations-tool.js`, `entity-fields.js`, `chart.min.js`.
- `views/css/admin.css`.
- `translations/{iso}.php` - Texte des Backoffice.

### 6.3. Controller

`AdminMyaitranslationsgrok` erweitert `ModuleAdminController`. Die übergeordnete Tab-Klasse ist `AdminInternational` (Ersatz: `IMPROVE`). Der Abfrageparameter heißt `myaitgk_tab` und akzeptiert `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs`, `settings` und `updates`. Unbekannte Werte fallen auf `dashboard` zurück.

Sichtbare Aktionen sind die Submit-Schaltflächen aus Kapitel 3. Zusätzliche Admin-Endpunkte für die Seitenskripte: `ajax=1&action=HistoryDetail` für **Ansicht**, die Statusabfrage eines Jobs für **Automatische Verarbeitung** und die Aktionen zum Übersetzen einzelner Felder aus `translations-tool.js` und `entity-fields.js`.

`MyaitranslationsgrokCronModuleFrontController` (`controllers/front/cron.php`) liest den Parameter `token`. Fehlt er oder ist er falsch, antwortet das Modul mit HTTP 403 und `{"ok":false,"error":"Forbidden"}`. Ein gültiger Token ohne `id_job` verarbeitet einen Teilstapel des ersten Jobs mit dem Status `pending` oder `running`. Mit `id_job` wird genau dieser Job verarbeitet. Wartet nichts, lautet die Antwort `{"ok":true,"message":"No pending jobs"}`.

`job_action` auf dem Reiter Jobs akzeptiert `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback` und `export_errors`. Die Vorlage zeigt alle außer `cancel` an.

### 6.4. Hooks

Registriert in `install()`:

- `displayBackOfficeHeader` - korrigiert die technische Beschriftung des Reiters und lädt die Assets des Backoffice.
- `actionAdminControllerSetMedia` - lädt dieselben Assets.

Auf `AdminMyaitranslationsgrok` fügt das Modul `views/css/admin.css`, `views/js/admin.js` und `views/js/admin-help.js` hinzu. Das **Dashboard** lädt zusätzlich `chart.min.js` und `history-charts.js`. Unter **International → Übersetzungen** kommt `translations-tool.js` hinzu, wenn die Schalter dieser Seite aktiv sind. Auf anderen Backoffice-Formularen wird `entity-fields.js` geladen, wenn die Schalter für Shop-Formulare aktiv sind. Beide übergeben das Objekt `myaitgkTr` an JavaScript.

Das Modul registriert keinen Hook für das Frontend und stellt auch keinen eigenen Hook bereit.

### 6.5. Overrides

Das Modul überschreibt keine PrestaShop-Klasse und keinen Controller.

### 6.6. Datenbank

Die Deinstallation führt `sql/uninstall.php` aus und löscht jede der folgenden Tabellen. Die Installation nutzt `CREATE TABLE IF NOT EXISTS`. Eine Tabelle, die irgendwie übrig geblieben ist, bleibt daher erhalten.

| Tabelle | Inhalt |
|---|---|
| `myaitgk_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, `id_shop`. |
| `myaitgk_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitgk_job` | Ein Stapel-Job: Locales, `scope_json`, `policy_json`, `dry_run`, Zähler, Kosten, Status und Mitarbeiter. |
| `myaitgk_job_item` | Eine Zeichenfolge im Job: Domain, Schlüssel, Theme, Locales, Quelle, vorheriger Text, neuer Text, Status und Warnungen. |
| `myaitgk_memory` | Eine wiederverwendete Übersetzung, identifiziert über `memory_hash`, Modell und `hit_count`. |
| `myaitgk_usage_ledger` | Tägliche Token- und Kostenzeilen, aus denen **Budget USD / Monat** berechnet wird. |
| `myaitgk_snapshot` | Der Text vor einem Schreibvorgang des Jobs, verwendet von **Rollback**. |
| `myaitgk_api_log` | Kurzer Fehlerkontext. Der API-Schlüssel wird vor dem Speichern entfernt. |
| `myaitgk_request` | Die Zeilen des **Verlaufs**: Prompt, Antwort, Token, Modell, Status und Dauer. Das Repository legt die Tabelle neu an, wenn sie fehlt. |
| `myaitgk_review` | Warteschlangenzeilen mit dem Status `needs_review`, `approved` oder `rejected`, außerdem `quality_score` und `flags_json`. |
| `myaitgk_catalog_item` | Zeilen der Katalog-Batches: Entität, Feld, Sprachen, Quelle, vorheriger Text, neuer Text und Status. |

`var/rate_limit.json` ist eine Datei und keine Tabelle. Die Deinstallation löscht `mypresta_updates`, `update_myaitranslationsgrok` oder `updatev_myaitranslationsgrok` nicht.

### 6.7. Schlüssel und Übersetzungen

Präfix `MYAITGK_`. `installDefaults()` schreibt einen Schlüssel nur, wenn er fehlt. Werte für fehlende Schlüssel:

| Schlüssel | Wert, wenn er fehlt |
|---|---|
| `API_KEY_ENC` | leer |
| `MODEL` | `grok-4.7` |
| `EXTRA_MODELS` | leer |
| `PROVIDER` | `grok` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | leer |
| `BATCH_SIZE` | `25` (gespeichert im Bereich 1–100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | leer |
| `TEMPERATURE` | `0.2` (gespeichert im Bereich 0–1) |
| `DRY_RUN_SAMPLE` | `10` (gespeichert im Bereich 1–50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (gespeichert mindestens 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | leer |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (bei 0 wird es nicht in den Übersetzungs-Request aufgenommen; bei einem Wert über 0 als `max_tokens` gesendet) |
| `CRON_TOKEN` | 32 Hex-Zeichen, wird neu erzeugt, wenn leer |

Beim Speichern der **Einstellungen** wird `PROVIDER` auf `grok` gesetzt. Außerdem werden die alten Schlüssel `MYAITGK_DEEPL_API_KEY` und `MYAITGK_CLAUDE_API_KEY` gelöscht, falls sie aus früheren Versionen noch existieren. Ein leeres API-Schlüsselfeld löscht `API_KEY_ENC` nicht.

Die eingebauten Modell-IDs sind `grok-4.7`, `grok-4.6`, `grok-4.5`, `grok-4.3`, `grok-4.20-0309-non-reasoning` und `grok-4.20-0309-reasoning`. Ein fehlender Schalter gilt als aktiviert. Shops, die vor diesen Schaltern installiert wurden, behalten deshalb ihre Symbole.

Die Feldbeschreibungen erstellt `MyaitgkForms::help()` mit den Abschnitten **Was es tut:**, **Wie konfigurieren:** und **Wirkung:**. Die Hilfepanels stammen aus `MyaitgkSectionHelp`. Backoffice-Texte laufen über `$this->l()`. Eine neue Sprache legen Sie an, indem Sie `translations/en.php` nach `translations/{iso}.php` kopieren. Einige Meldungen stehen im PHP fest auf Englisch und erscheinen daher so: `No Grok API key.`, `Monthly API budget has been exhausted.`, `Grok rate limit (429). Try again later.`, `Rate limit — job auto-paused. Resume later.` und die JSON-Meldungen des Cron-Aufrufs.

### 6.8. Erweiterungen

Das Shop-Theme hat keine Vorlage zum Überschreiben. Das Modul rendert keine Smarty-Datei im Frontend. Der Backoffice-Code liegt in `views/templates/admin/`. Die Feldschaltflächen werden von `views/js/translations-tool.js` und `views/js/entity-fields.js` eingefügt. Einen Hook fürs Frontend, an den man sich anhängen könnte, gibt es nicht.

## 7. Hilfe

Modulseite: [AI Translations with Grok](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-grok.html).

Um sich wegen des Moduls an den Support zu wenden, melden Sie sich auf mypresta.eu in Ihrem Kundenkonto an, öffnen Sie das Kontaktformular und wählen Sie das Thema **Support for paid modules**. Das Formular weist darauf hin, dass für kostenpflichtige Module eine Anmeldung nötig ist. Nach dem Login wählen Sie dieses Modul aus Ihrem Kaufverlauf aus.

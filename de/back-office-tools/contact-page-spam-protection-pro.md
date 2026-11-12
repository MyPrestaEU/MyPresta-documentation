---
title: Contact page - spam protection PRO - Dokumentation und Benutzerhandbuch
sidebar:
  label: Contact page - spam protection PRO - Dokumentation und Benutzerhandbuch
description: Anleitung zur Einrichtung und zur Fehlersuche für Shops, die den Spamschutz der Kontaktseite bereits haben.
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Contact page - spam protection PRO auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/contact-page-spam-protection-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/contact-page-spam-protection-pro/)
>
> ---


## 1. Anforderungen

Das Modul läuft in PrestaShop 1.7.7 bis 9. PHP in der Version, die diese PrestaShop-Version verlangt. Die eigene Kontaktseite des Shops genügt. Ein weiteres Modul ist nicht nötig.

Ein Google-reCAPTCHA-Konto brauchen Sie nur für das Kontrollkästchen oder die unsichtbare Bewertung. Nach der Installation ist der reCAPTCHA-Schalter an, die Prüfung bleibt aber aus, bis beide Schlüssel gespeichert sind.

Ein CleanTalk-Konto brauchen Sie nur für die kostenpflichtige API. Die kostenlose Prüfung läuft über den MyPresta-Proxy und braucht kein CleanTalk-Konto. Kostenloses CleanTalk braucht die OpenSSL-Funktionen in PHP. Fehlen sie, wird diese eine Prüfung übersprungen und die Nachricht zugelassen.

StopForumSpam ist eine öffentliche Abfrage. Konto und API-Schlüssel sind optional. Der gespeicherte Schlüssel wird bei der Abfrage nicht verwendet.

Die Abfragen nutzen cURL, wenn PHP es hat. Ohne cURL lesen StopForumSpam, CleanTalk und die Update-Prüfung die Adresse direkt, wenn der Server das erlaubt. Die reCAPTCHA-Prüfung nutzt cURL, wenn es vorhanden ist.

## 2. Installation

Öffnen Sie **Module**, dann **Modul-Manager**. Laden Sie die Zip-Datei hoch und klicken Sie auf **Installieren**.

Im linken Menü erscheint **Kontaktschutz**. Darüber öffnen Sie die Konfiguration. Darunter liegen **Nachrichtenversuche** und **Gesperrte IP-Adressen**.

Die Installation leert den Cache nicht in einem eigenen Schritt.

Zum Abschalten nutzen Sie den Schalter im Modul-Manager. Die Kontaktseite wird nicht mehr geprüft. Einstellungen, Versuche und Sperren bleiben. Nach dem Einschalten werden sie weiter verwendet. Die Menüpunkte sind versteckt, solange das Modul aus ist.

Zum Entfernen klicken Sie auf **Deinstallieren** und bestätigen **Möchten Sie dieses Modul wirklich deinstallieren?** Die Deinstallation entfernt die Menüpunkte, die gespeicherten Einstellungen und beide Listen. Die Dateien bleiben auf dem Server, bis Sie das Modul löschen. Eine neue Installation startet mit leeren Listen und den Einstellungen einer frischen Installation. Alte Versuche und Sperren kommen nicht zurück.

## 3. Konfiguration und tägliche Arbeit

Die Bilder in diesem Kapitel sind das englische Backoffice. Die Namen unten sind die des deutschen Panels.

Öffnen Sie **Kontaktschutz**. Die Register sind **Übersicht**, **Flood-Schutz**, **CleanTalk**, **StopForumSpam**, **reCAPTCHA**, **Nachrichtenfilter**, **Whitelist**, **Schutz** und **E-Mail**. **Updates** steht am Ende der Reihe. **Speichern** auf einem Register speichert es und bestätigt mit **Einstellungen gespeichert.** Das Update-Register bestätigt mit **Update-Einstellungen gespeichert.**

Solange die Bedingung gilt, kann eine Konfigurationsseite zeigen:

**reCAPTCHA ist aktiviert, aber der Website-Schlüssel oder der geheime Schlüssel ist leer. Das Captcha bleibt deaktiviert, bis beide Schlüssel gespeichert sind.**

**Die kostenpflichtige CleanTalk-API ist aktiviert, aber der Zugriffsschlüssel ist leer.**

Die zweite Warnung erscheint, wenn der kostenpflichtige Schalter an ist und der Schlüssel leer ist. Nach einer frischen Installation ist dieser Schalter aus, die Warnung also erst sichtbar, wenn Sie die kostenpflichtige API ohne Schlüssel einschalten.

Eine Nachricht wird in dieser Reihenfolge geprüft. Der erste Treffer entscheidet.

1. Eine Adresse auf der Whitelist und ein angemeldeter Kunde, wenn **Prüfungen für angemeldete Kunden überspringen** an ist, geht zum Kontaktformular. Der Versuch wird nicht unter **Nachrichtenversuche** geschrieben.
2. Sind alle Prüfungen aus und die Adresse steht nicht auf der Sperrliste, geht die Nachricht weiter und wird nicht protokolliert. Der reCAPTCHA-Schalter allein zählt nicht als Prüfung, solange beide Schlüssel leer sind.
3. Danach: aktive Sperre, Honeypot, Mindestzeit, leerer Browser-Kennung, Flood-Schutz, Duplikat einer Nachricht mit mindestens 20 Zeichen, zu viele Links, gesperrtes Wort, Wegwerf-E-Mail, reCAPTCHA (nur wenn beide Schlüssel gespeichert sind), StopForumSpam, kostenloses CleanTalk, kostenpflichtiges CleanTalk.
4. Trifft nichts zu, wird der Versuch als zugelassen gespeichert und das Formular sendet die Nachricht.
5. Eine Sperre **Zu schnell** oder **reCAPTCHA** stoppt nur diese Nachricht. Sie sperrt die Adresse nicht, schickt keine E-Mail an den Shop und leitet nicht weiter. Bei reCAPTCHA sieht der Kunde **Die Captcha-Prüfung ist fehlgeschlagen. Bitte versuchen Sie es erneut.** Bei zu schnellem Senden sieht er **Ihre Nachricht konnte nicht gesendet werden. Bitte versuchen Sie es in ein paar Minuten erneut.**
6. Jede andere Sperre kann die Adresse sperren, den Shop mailen und weiterleiten, je nach den Feldern unter **Schutz**. Sind mehrere Weiterleitungen angehakt, gilt zuerst die Startseite, dann die CMS-Seite, zuletzt Google. Ohne Weiterleitung bleibt der Besucher auf der Kontaktseite und sieht **Ihre Nachricht konnte nicht gesendet werden. Bitte versuchen Sie es in ein paar Minuten erneut.**

Der Flood-Schutz zählt jeden Versuch im Zeitfenster, auch bereits blockierte. Mehrere Captcha-Wiederholungen können das Nachrichtenlimit also erreichen.

Ein Duplikat sieht frühere Versuche mit demselben Text. Versuche, die nur an **Zu schnell** oder **reCAPTCHA** gescheitert sind, zählen nicht als frühere Kopie.

StopForumSpam und beide CleanTalk-Prüfungen lassen die Nachricht zu, wenn der Dienst nicht antwortet. reCAPTCHA macht das Gegenteil: antwortet Google nicht, wird die Nachricht blockiert.

### 3.1 Übersicht

![Übersicht](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-overview.webp)

Die **Übersicht** zählt Kontaktnachrichten, blockierte Nachrichten und aktive Sperren für die Daten unter **Analyseparameter**. Ein Kunde, der durchkommt, zählt als Nachricht. Ein Besucher, der eine Prüfung nicht besteht, zählt als blockiert und steht unten mit dem Grund.

Die Karten sind **Nachrichten**, **Zugelassen**, **Blockiert**, **Sperrquote**, **Blockierte IP-Adressen** und **Aktive Sperren**.

Das Diagramm **Blockiert und zugelassen** zeigt **Täglich** und **Wöchentlich**, wenn der Zeitraum mehr als 7 Tage hat. **Wöchentlich** fasst die Tage zu siebt ab dem Beginn des Zeitraums. Die letzte Gruppe kann kürzer sein. Die Legende ist **Zugelassen**, **Blockiert** und **Gesamt**. Ohne Zeilen im Zeitraum steht dort **Keine Nachrichten in diesem Zeitraum.**

**Blockiert nach Grund** zeigt, wie viele Sperren jede Prüfung erzeugt hat. Die Namen auf dieser Seite sind **Gesperrte IP**, **Honeypot**, **Zu schnell**, **Leerer User-Agent**, **Flood-Schutz**, **Doppelte Nachricht**, **Zu viele Links**, **Gesperrtes Wort**, **Wegwerf-E-Mail**, **reCAPTCHA**, **StopForumSpam** und **CleanTalk**. Ein leerer Grund erscheint als **Unbekannt**.

**Zuletzt blockierte Nachrichten** hat die Spalten **Datum**, **IP**, **E-Mail** und **Grund**. Wurde nichts blockiert, sagt die Tabelle **In diesem Zeitraum wurde nichts blockiert.**

Die Schaltflächen **Nachrichtenversuche** und **Gesperrte IP-Adressen** öffnen diese Listen.

Die farbigen Plaketten unter dem Diagramm zeigen, welche Prüfungen an sind. **reCAPTCHA** ist nur grün, wenn beide Schlüssel gespeichert sind. Der Schalter allein färbt diese Plakette nicht. Nach der Installation sind **Flood-Schutz**, **Honeypot**, **Mindestzeit** und **Linklimit** an.

Die Zeile unter den Plaketten hat die Form **Nachrichten: 0 zwischen 2026-10-13 und 2026-11-11. Blockiert: 0, zugelassen: 0. Neue Sperren in diesem Zeitraum: 0.** Die Daten folgen dem gewählten Zeitraum. Ein rollierender Zeitraum endet heute. Die Daten sind das aktuelle Fenster dieses Shops, kein fester Wert des Moduls.

### 3.2 Analyseparameter

![Analyseparameter](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-overview-analytics.webp)

Öffnen Sie das geschlossene Feld **Analyseparameter** in der **Übersicht**.

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **Statistikzeitraum** | Letzte 30 Tage | **Letzte 7 Tage**, **Letzte 30 Tage**, **Letzte 90 Tage**, **Letzte 180 Tage**, **Letzte 365 Tage** oder **Benutzerdefinierter Zeitraum**. Karten, Diagramm und die letzte Liste nutzen dieses Fenster. Der Start ist die letzten 30 Tage. Die letzten 7 Tage zeigen einen kurzen Stoß und nehmen ältere Sperren aus dem Diagramm. Die letzten 365 Tage decken ein Jahr ab, ein einzelner starker Tag ist dann ein kleines Stück. Der benutzerdefinierte Zeitraum nutzt **Von** und **Bis**. Die anderen Werte ignorieren diese Daten und enden immer heute. |
| **Von** | Beginn des aktuellen Fensters | Datum als JJJJ-MM-TT. Genutzt, wenn der **Statistikzeitraum** **Benutzerdefinierter Zeitraum** ist. Ein Datum nach **Bis** wird mit **Bis** getauscht. Ein Bereich länger als 366 Tage wird von dieser Seite gekürzt. Ein Datum in der Zukunft wird auf heute zurückgesetzt. Ein leeres oder ungültiges Datum wird durch das Datum vor 30 Tagen ersetzt. Rollierende Zeiträume ignorieren dieses Feld. |
| **Bis** | heute | Datum als JJJJ-MM-TT. Genutzt, wenn der **Statistikzeitraum** **Benutzerdefinierter Zeitraum** ist. Ein Datum in der Zukunft wird auf heute zurückgesetzt. Liegt **Bis** vor **Von**, werden die Daten getauscht. Ein leeres oder ungültiges Datum wird durch heute ersetzt. Rollierende Zeiträume ignorieren dieses Feld und enden immer heute. |

**Speichern** speichert den Zeitraum. Die Seite bestätigt **Einstellungen gespeichert.**

### 3.3 Flood-Schutz

![Flood-Schutz](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-antiflood.webp)

Der Flood-Schutz zählt, wie viele Kontaktnachrichten eine IP-Adresse im Zeitfenster sendet. Ein Kunde, der ein paar Mal schreibt, kommt noch durch. Die nächste Nachricht über dem Limit wird abgelehnt, und **Schutz** kann diese Adresse sperren, wenn die Sperre angehakt ist.

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **Flood-Schutz aktivieren** | Ja | An: jede IP wird im Zeitfenster gezählt, die nächste Nachricht über dem Limit wird blockiert. Aus: ein Skript kann von derselben IP ohne Limit dieser Prüfung weiter senden. Ein niedriges Limit blockiert auch einen Kunden, der eine Korrektur aus demselben Büro schickt. Lassen Sie es für eine öffentliche Kontaktseite an. Schalten Sie es nur aus, während Sie Testnachrichten von einer Adresse senden. |
| **Zeitfenster** | 10 Minuten | Minuten. Nur Kontaktnachrichten der letzten X Minuten zählen zum Limit. 1 oder 2 Minuten fangen einen Stoß und vergessen ihn dann, ein langsames Skript kann also weiterlaufen. 60 Minuten oder mehr zählen auch einen Kunden, der schreibt, wartet und von derselben IP erneut schreibt. Eine gespeicherte 0 wird als 1 behandelt. |
| **Erlaubte Nachrichten** | 5 | Wie viele Kontaktnachrichten eine IP im Zeitfenster senden darf. Die nächste wird blockiert. 5 lässt eine Korrektur und ein erneutes Senden zu. 1 blockiert das zweite Senden, also Skripte und auch einen Kunden, der zweimal auf Senden klickt. Ein hoher Wert wie 20 lässt viele Nachrichten durch. Der Zähler umfasst frühere Sendungen dieser IP, auch blockierte, mehrere Captcha-Wiederholungen können das Limit also erreichen. Eine gespeicherte 0 wird als 1 behandelt. |

### 3.4 CleanTalk

![CleanTalk](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-cleantalk.webp)

CleanTalk prüft IP und E-Mail gegen eine Spam-Datenbank. Schalten Sie die kostenlose Option ein, um den MyPresta-Proxy ohne CleanTalk-Konto zu nutzen, oder die kostenpflichtige, wenn Sie einen eigenen Schlüssel haben. Eine unbekannte Adresse wird angenommen. Eine bereits als Spam gemeldete Adresse wird abgelehnt. Antwortet der Dienst nicht, wird die Nachricht zugelassen.

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **Kostenloses CleanTalk aktivieren** | Nein | Fragt den MyPresta-CleanTalk-Proxy, ob diese IP oder E-Mail schon als Spam bekannt ist. Ein CleanTalk-Konto ist nicht nötig. Aus überspringt die Prüfung. Antwortet der Proxy nicht, oder PHP hat keine OpenSSL-Verschlüsselung, wird die Nachricht zugelassen. Ein Bot, der nicht in der Datenbank steht, kommt ebenfalls durch. Einschalten, wenn Sie keinen kostenpflichtigen Schlüssel haben. |
| **Kostenpflichtige CleanTalk-API aktivieren** | Nein | Nutzt den Zugriffsschlüssel Ihres CleanTalk-Kontos. Einschalten, nachdem Sie den Schlüssel eingefügt haben. Aus lassen, wenn Sie kein Abo haben. Ein leerer oder abgelehnter Schlüssel blockiert niemanden, Spam, den nur diese Prüfung fangen würde, wird angenommen. Eine Adresse auf der Liste wird abgelehnt, ein Kunde auf derselben IP kann ebenfalls abgelehnt werden. |
| **Zugriffsschlüssel** | leer | Fügen Sie den Schlüssel aus Ihrem CleanTalk-Konto ein, ohne zusätzliche Leerzeichen. Die kostenpflichtige Prüfung läuft nur, wenn dieses Feld einen Schlüssel hat. Leer, bei angeschaltetem kostenpflichtigem Schalter, bedeutet keine kostenpflichtige Prüfung, und die Seite zeigt **Die kostenpflichtige CleanTalk-API ist aktiviert, aber der Zugriffsschlüssel ist leer.** Ein widerrufener Schlüssel gilt als fehlgeschlagene Prüfung, die Nachricht wird zugelassen. |
| **Schwellenwert für Spamrate** | 1 | Ein Wert von 0.0 bis 1.0. Eine CleanTalk-Spamrate gleich diesem Wert oder höher gilt als Spam. Eine Adresse, die CleanTalk als in Spam vorkommend markiert, wird bei jedem Wert blockiert. 1 blockiert Adressen, bei denen CleanTalk sicher ist. Ein niedrigerer Wert wie 0.5 blockiert auch unsichere Ergebnisse und kann einen echten Kunden an einer gemeinsamen IP stoppen. Eine gespeicherte 0 wird als 1 behandelt, die Prüfung bleibt streng. |

Der Link **CleanTalk-Kontoseite öffnen** öffnet die Kontoseite in einem neuen Tab.

### 3.5 StopForumSpam

![StopForumSpam](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-stopforumspam.webp)

StopForumSpam ist eine freie Datenbank von IP-Adressen und E-Mails, die wegen Spam gemeldet wurden. Die Prüfung braucht keinen API-Schlüssel. Ein Kunde, der nie gemeldet wurde, wird angenommen. Eine Adresse mit genug Meldungen wird abgelehnt. Antwortet der Dienst nicht, wird die Nachricht zugelassen.

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **StopForumSpam aktivieren** | Nein | IP des Besuchers und E-Mail aus dem Formular werden abgefragt. Aus überspringt die Prüfung. Antwortet der Dienst nicht, wird die Nachricht zugelassen: ein Netzproblem blockiert keine Kunden, Spam, den diese Prüfung gefangen hätte, kommt aber ebenfalls durch. Für eine öffentliche Kontaktseite eingeschaltet lassen. |
| **Mindestanzahl Meldungen** | 1 | Blockieren, wenn StopForumSpam diese IP oder E-Mail mindestens so oft erfasst hat. Bei 1 blockiert eine einzelne Meldung die Adresse, auch einen Kunden, der einmal irrtümlich gemeldet wurde. Bei 5 oder mehr kommen Adressen mit wenigen Meldungen durch, es kommt also mehr Spam an. Eine gespeicherte 0 wird als 1 behandelt. |
| **API-Schlüssel** | leer | Optional. Die öffentliche Abfrage funktioniert ohne Schlüssel. Leer lassen, oder einen Schlüssel speichern, wenn Sie schon ein StopForumSpam-Konto haben. Das Modul nutzt trotzdem die öffentliche Abfrage, ein falscher Schlüssel ändert nicht, wer blockiert wird. |

Der Link **Registrieren** öffnet die StopForumSpam-Registrierung.

### 3.6 reCAPTCHA

![reCAPTCHA](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-recaptcha.webp)

Google reCAPTCHA läuft im Browser auf der Kontaktseite. Nutzen Sie es, wenn Bots Nachrichten schicken, die wie gewöhnlicher Text aussehen, und wählen Sie denselben Typ, der zum Schlüssel in der Google-Konsole gehört. v2 zeigt ein Kontrollkästchen. v3 bewertet den Besuch ohne Aufgabe: ein bestandener Wert wird angenommen, ein nicht bestandener lehnt die Nachricht ab und sperrt die IP nicht.

Der Text **So erhalten Sie den Website-Schlüssel und den geheimen Schlüssel** sagt: Schlüssel in der Google-Konsole anlegen, dann Website-Schlüssel und geheimen Schlüssel unten einfügen. Der hier gewählte Typ muss derselbe sein wie beim Schlüssel. Ein abweichender Typ lässt jeden Besucher scheitern, auch einen echten Kunden.

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **reCAPTCHA aktivieren** | Ja | Die Kontaktseite verlangt reCAPTCHA, bevor die Nachricht angenommen wird. Bei leeren Schlüsseln bleibt das Captcha aus, auch wenn dieser Schalter an ist, und die Seite zeigt **reCAPTCHA ist aktiviert, aber der Website-Schlüssel oder der geheime Schlüssel ist leer. Das Captcha bleibt deaktiviert, bis beide Schlüssel gespeichert sind.** Ein Kunde, der scheitert, kann es erneut versuchen. Dieses Scheitern sperrt die IP nicht. |
| **reCAPTCHA-Typ** | reCAPTCHA v2 | **reCAPTCHA v2** zeigt ein Kontrollkästchen. **reCAPTCHA v3** bewertet den Besuch im Hintergrund und zeigt keine Aufgabe. Denselben Typ wählen, der zum Schlüssel in der Google-Konsole gehört. Eine Abweichung lässt jedes Senden scheitern, auch bei echten Kunden. v2 ist klarer, wenn Sie eine sichtbare Prüfung wollen. v3 ist unauffälliger und nutzt den Schwellenwert unten. |
| **Website-Schlüssel** | leer | Der öffentliche Schlüssel aus der Google-reCAPTCHA-Verwaltung für die Domain dieses Shops. Den Website-Schlüssel einfügen, der zum oben gewählten Typ gehört, ohne Leerzeichen. Beide Schlüssel sind nötig. Ein leerer Website-Schlüssel lässt das Captcha aus. Ein Schlüssel für eine andere Domain oder einen anderen Typ lässt echte Kunden scheitern. |
| **Geheimer Schlüssel** | leer | Der geheime Schlüssel bleibt auf dem Server. Er wird nie an den Browser gesendet. Den geheimen Schlüssel aus demselben Paar wie den Website-Schlüssel verwenden. Ein leerer geheimer Schlüssel lässt das Captcha aus. Ein geheimer Schlüssel einer anderen Website lässt Google jeden Besuch ablehnen, Kunden können das Formular nicht senden. |
| **v2-Design** | Hell | **Hell** oder **Dunkel** für das v2-Kontrollkästchen. Hell auf einer weißen Kontaktseite, Dunkel auf einer dunklen. v3 ignoriert diese Einstellung und nutzt die Standardplakette von Google. Das Design ändert nicht, wer blockiert wird. Ein dunkles Widget auf einer weißen Seite ist schlechter zu sehen, mehr Leute überspringen das Kästchen und die Nachricht wird abgelehnt. |
| **v3-Schwellenwert** | 0.5 | Ein Wert von 0.0 bis 1.0. Genutzt, wenn der Typ v3 ist. Google bewertet den Besuch, ein Wert unter diesem Wert wird abgelehnt. Der Startwert ist 0.5. Ein höherer Wert wie 0.9 ist strenger und kann Kunden in einem gemeinsamen oder ungewöhnlichen Netz ablehnen. Ein niedrigerer Wert wie 0.1 lässt mehr automatische Besuche durch. Eine Ablehnung sperrt die IP nicht. Fehlt der gespeicherte Wert, wird 0.5 verwendet. |

### 3.7 Nachrichtenfilter

![Nachrichtenfilter, erste Felder](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-filters.webp)

![Nachrichtenfilter, weitere Felder](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-filters-content.webp)

Die Filter laufen im Shop, vor einem externen Spamdienst. Für eine öffentliche Kontaktseite lassen Sie Honeypot und Mindestzeit an, und ergänzen Links, Wörter, Wegwerfadressen oder Duplikate, wenn die Sperrliste ein wiederkehrendes Muster zeigt. Ein Kunde, der das Formular gewöhnlich ausfüllt, wird angenommen. Ein Skript wird abgelehnt. Ein fehlgeschlagenes Captcha oder ein zu schnelles Senden sperrt die IP nicht. Die anderen Filter können sie sperren, wenn die Sperre unter **Schutz** angehakt ist.

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **Honeypot-Feld** | Ja | Fügt ein verstecktes Feld hinzu, das Menschen nicht sehen. Der Kunde lässt es leer, die Nachricht geht weiter. Ein Skript, das jedes Feld füllt, wird blockiert, und **Schutz** kann diese IP sperren. Ausschalten, wenn eine Autofill-Funktion das versteckte Feld füllt und Ihre Kunden blockiert. |
| **Mindestzeit auf der Seite** | Ja | Blockiert ein Senden, das schneller ist als das Limit nach dem Start des Seitenskripts. Ein Kunde, der liest und schreibt, braucht mehr als ein paar Sekunden. Ein Skript, das sofort sendet, wird blockiert. Ein fehlender Zähler wird angenommen, ein Browser ohne JavaScript kann also noch senden. Diese Sperre sperrt die IP nicht. Aus lässt sofortige Sendungen durch diese Prüfung. |
| **Mindestsekunden** | 3 | Sekunden. Genutzt, wenn die Mindestzeit an ist. 1 Sekunde fängt ein sofortiges Skript und trifft einen Kunden selten. 15 Sekunden oder mehr blockieren einen Kunden, der den Text schon kennt und schnell sendet. Der Zähler startet, wenn das Seitenskript läuft. Eine gespeicherte 0 wird als 1 behandelt. |
| **Links in der Nachricht begrenzen** | Ja | Zählt http://, https:// und www. in der Nachricht. An, wenn der Spam vor allem Links ist. Aus, wenn Kunden oft eine Produktadresse einfügen. Aus nimmt eine Nachricht voller Links an. An, mit einem niedrigen Maximum, blockiert auch einen Kunden, der mehrere Adressen einfügt. |
| **Maximale Anzahl Links** | 3 | Eine Nachricht mit mehr Links wird blockiert. Gezählt nur, wenn das Linklimit an ist. 3 lässt ein paar Adressen zu. 0 blockiert jede Nachricht mit einem Link, auch zu einer Produktseite. Ein hoher Wert wie 20 lässt eine typische Link-Spam-Nachricht durch. |
| **Gesperrte Wörter** | Nein | Suche ohne Groß- und Kleinschreibung in der E-Mail und in der Nachricht. Einschalten, nachdem Sie Phrasen aus echtem Spam eingetragen haben. Aus, oder an mit leerer Liste, blockiert nichts. Ein kurzes, häufiges Wort blockiert auch einen echten Kunden, der es benutzt hat. |
| **Wörter und Phrasen** | leer | Ein Wort oder eine Phrase je Zeile. Genutzt, wenn gesperrte Wörter an sind. Leer lassen, bis Sie Phrasen aus echtem Spam kopieren. Eine Phrase trifft irgendwo in der E-Mail oder der Nachricht, ein kurzes Stück wie win trifft also auch window und blockiert eine gewöhnliche Frage. Eine lange, konkrete Phrase blockiert nur diesen Text. |
| **Wegwerf-E-Mails blockieren** | Nein | Blockiert eine eingebaute Liste temporärer Postfach-Domains und die Domains darunter. An, wenn Sie keine Nachrichten von Wegwerfpostfächern wollen. Eine gewöhnliche Adresse wird angenommen. Ein temporäres Postfach auf der Liste wird blockiert, und **Schutz** kann diese IP sperren. Domains, die nicht auf der Liste stehen, kommen durch, bis Sie sie ergänzen. Aus nimmt jede Domain an. |
| **Zusätzliche Wegwerf-Domains** | leer | Eine Domain je Zeile, zum Beispiel dropmail.test. Genutzt, wenn Wegwerf-E-Mails blockiert werden. Leer lassen, bis eine Domain in der Versuchsliste auftaucht. Eine hier eingetragene Domain blockiert auch ihre Subdomains. Kein @ eintragen. Ein echter Mailanbieter blockiert jeden Kunden, der ihn nutzt. |
| **Doppelte Nachrichten blockieren** | Nein | Blockiert denselben Nachrichtentext, der im Zeitfenster erneut gesendet wird, von jeder IP. An, wenn dieselbe Werbung von vielen Adressen kommt. Nachrichten kürzer als 20 Zeichen werden übersprungen, eine kurze Begrüßung kann also erneut gesendet werden. Ein Captcha-Wiederholversuch gilt nicht als Duplikat. Ein Kunde, der dieselbe lange Frage zweimal im Fenster sendet, wird beim zweiten Mal blockiert. Aus erlaubt denselben Text erneut. |
| **Duplikat-Zeitfenster** | 60 Minuten | Wie lange der Text gemerkt wird. Ein kurzes Fenster wie 5 Minuten vergisst den Text schnell, derselbe Spam kann zurückkommen. Ein langes Fenster wie 1440 Minuten (ein Tag) blockiert auch einen Kunden, der dieselbe Frage später am selben Tag erneut sendet. Nur genutzt, wenn die Duplikatsperre an ist. Eine gespeicherte 0 wird als 1 behandelt. |
| **Leeren User-Agent blockieren** | Nein | Blockiert eine Anfrage ohne Browser-Kennung. Aus lassen, außer die Versuche zeigen Spam mit leerer Kennung. Echte Browser senden eine. An blockiert auch Datenschutzwerkzeuge, die die Kennung entfernen, diese Kunden können nicht senden. Aus ignoriert eine leere Kennung. |
| **Prüfungen für angemeldete Kunden überspringen** | Nein | Ein angemeldeter Kunde überspringt jede Prüfung, auch eine aktive Sperre. Aus lassen in einem Shop, in dem sich jeder registrieren kann. An, wenn Ihre Kunden Konten haben, denen Sie vertrauen. Gäste werden weiter geprüft. An lässt einen angemeldeten Bot durch. Aus prüft angemeldete Kunden wie Gäste, eine gesperrte Büro-Adresse bleibt also auch für ein Konto gesperrt. |

### 3.8 Whitelist

![Whitelist](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-whitelist.webp)

Die Whitelist sind IP-Adressen, die jede Prüfung überspringen, auch eine aktive Sperre. Tragen Sie Ihr Büro, eine Agentur oder ein Überwachungswerkzeug ein, das eine Testnachricht sendet. Alle anderen werden weiter geprüft. Eine leere Liste bedeutet, dass keine Adresse übersprungen wird. Eine versehentlich ergänzte Zeile lässt diese Adresse durch, auch einen Bot, der sie nutzt.

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **IP-Adressen** | leer | Eine Adresse je Zeile. Eine Zeile, die mit * endet, trifft den Anfang der Adresse, zum Beispiel 192.168.1.*. Leer lassen, außer eine Adresse muss immer schreiben können, etwa Ihr Büro. Eine volle Adresse überspringt die Prüfungen nur für diese IP. Ein Präfix mit Stern überspringt den ganzen Bereich, einschließlich jedes Bots darin. Ein Tippfehler trifft nichts, dieser Besucher bleibt geschützt. IPv4 und IPv6 genau so vergleichen, wie der Shop sie zeigt. |

### 3.9 Schutz

![Schutz](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-protection.webp)

Eine fehlgeschlagene Prüfung lehnt die Nachricht immer ab. Die Felder unter **Was mit Spam geschehen soll** sind zusätzliche Schritte für eine Sperre, den Honeypot, Flood, die Nachrichtenfilter, StopForumSpam und CleanTalk. Sie laufen nicht, wenn das einzige Problem das Captcha oder ein zu schnelles Senden ist. Ein Kunde, der die Prüfungen besteht, ist davon nicht betroffen.

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **Zusätzliche Aktionen** | nichts angehakt | **IP-Adresse sperren**: an, wenn dieselbe Adresse wiederkommt. Die nächste Nachricht von dieser IP wird abgelehnt, bis Sie die Sperre ausschalten. Eine gemeinsame Büro-IP blockiert dann jeden Kunden, der sie nutzt. **Shop per E-Mail benachrichtigen**: an, wenn Sie eine Nachricht im Posteingang wollen. Eine E-Mail je IP, dann 30 Minuten Ruhe. Aus lässt den blockierten Spam nur in der Versuchsliste. **Zur Startseite weiterleiten**, **Zu einer CMS-Seite weiterleiten** und **Zu Google weiterleiten**: aus lassen, damit der Besucher auf der Kontaktseite bleibt und den Fehler liest. Sind mehrere Weiterleitungen angehakt, gilt zuerst die Startseite, dann die CMS-Seite, dann Google. |
| **CMS-Seite** | die erste Seite in der Liste des Shops | Genutzt, wenn **Zu einer CMS-Seite weiterleiten** angehakt ist. Eine kurze Seite wählen, die sagt, dass die Nachricht nicht gesendet wurde. Hat der Shop keine CMS-Seiten, enthält die Liste **Keine CMS-Seite**. Ohne gewählte Seite wird die CMS-Weiterleitung übersprungen. Ist **Zu Google weiterleiten** ebenfalls angehakt, wird danach Google genutzt. Sonst bleibt der Besucher auf der Kontaktseite mit dem Fehler. Ein Kunde, der die Prüfungen besteht, sieht diese Seite durch das Modul nicht. Die Seiten in der Liste sind die CMS-Seiten des Shops. Hat der Shop schon Seiten, steht die gespeicherte leere Wahl nicht in der Liste, es erscheint die erste Seite. Klicken Sie **Speichern** nur, wenn das die gewünschte Seite ist. |

### 3.10 E-Mail

![E-Mail](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-mail.webp)

Das Feld **E-Mail an den Shop** setzt den Betreff der E-Mail an die Shop-Adresse, wenn eine Nachricht blockiert wird. Die E-Mail geht nur, wenn **Shop per E-Mail benachrichtigen** unter **Schutz** angehakt ist, und nur für Sperren außer einem fehlgeschlagenen Captcha oder einem zu schnellen Senden. Eine E-Mail geht bei der ersten Sperre einer IP. Weitere Sperren dieser IP senden 30 Minuten lang keine Mail. Ein angenommener Kunde löst diese E-Mail nicht aus. Ist die Shop-E-Mail in den Shop-Parametern leer, geht keine Mail.

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **Betreff** | Contact form spam blocked | Betreff der Shop-Benachrichtigung. Der kurze Prüfname wird angehängt, zum Beispiel [flood]. Die Nachricht geht an die Shop-E-Mail aus den Shop-Parametern. Ein kurzer Betreff, den Ihre Postfachregeln erkennen, für jede Sprache des Shops ausgefüllt. Ein leerer Betreff wird durch Contact form spam blocked ersetzt. Der Betreff ändert nicht, wer blockiert wird. |

Die Sprachschaltfläche wechselt den Betreff in eine andere Shopsprache. Der Text der Mail ist die Mailvorlage des Moduls für diese Sprache. Der englische Text beginnt mit **Contact form blocked.** und nennt dann die Prüfung, die IP, die E-Mail, das Datum und den Anfang der Nachricht.

### 3.11 Updates

![Updates](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-updates.webp)

Diese Seite fragt MyPresta.eu, ob eine neuere Modulversion vorliegt. Die Einstellungen hier betreffen nur die Update-Prüfung. Sie ändern den Schutz der Kontaktseite nicht.

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **Nach Updates suchen** | — | **Jetzt prüfen** fragt MyPresta.eu sofort, ob eine neuere Version vorliegt. Nutzen Sie es nach der Installation und erneut vor einer starken Phase. Die Schaltfläche lädt keine Datei herunter und installiert keine. Erreicht der Shop-Server MyPresta.eu nicht, zeigt der Klick keine neue Version. |
| **Update-Benachrichtigungen** | Aktivieren | **Aktivieren** prüft MyPresta.eu und zeigt einen Hinweis im Backoffice, wenn eine neuere Version erscheint. Die automatische Prüfung läuft etwa alle 3 Tage, während Sie im Backoffice arbeiten. **Deaktivieren** stoppt diese Prüfung und den Hinweis. Eine neue Version bleibt dann unbemerkt, bis Sie **Jetzt prüfen** klicken. Diese Wahl ändert den Schutz des Formulars nicht. |
| **Modulseite** | Contact page - spam protection PRO | Ein direkter Link zur Modulseite auf MyPresta.eu. Das Änderungsprotokoll dort zeigt, was sich geändert hat. Öffnen Sie sie vor einem Update. Der Link installiert keine Datei. Lädt die Seite nicht, öffnen Sie die Adresse in einem neuen Tab. |

**Speichern** bestätigt **Update-Einstellungen gespeichert.**

Liegt eine neuere Version vor, kann das Backoffice zeigen **Neue Version verfügbar, weitere Informationen auf http://MyPresta.eu** und **Weitere Details im Changelog**. **Jetzt prüfen** antwortet **Neue Version verfügbar!** oder **Das Modul ist aktuell!**

### 3.12 Nachrichtenversuche

![Nachrichtenversuche](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-attempts.webp)

Öffnen Sie **Nachrichtenversuche** unter **Kontaktschutz**, oder die gleichnamige Schaltfläche in der **Übersicht**.

Der Shop schreibt eine Zeile, wenn eine Kontaktnachricht geprüft wird. Es gibt keine Schaltfläche zum Hinzufügen. Aus dieser Liste bearbeiten Sie eine Zeile nicht. Sie können eine Zeile löschen.

Die Spalten sind **ID**, **IP**, **E-Mail**, **Grund**, **Blockiert** und **Datum**. Die neueste Zeile steht oben. Eine leere Liste sagt auf dem englischen Bild **No records found**.

**Grund** in dieser Liste ist der kurze Name, nicht der lange Name aus der **Übersicht**:

| In der Übersicht | In dieser Liste |
|---|---|
| **Gesperrte IP** | ban |
| **Honeypot** | honeypot |
| **Zu schnell** | timing |
| **Leerer User-Agent** | user-agent |
| **Flood-Schutz** | flood |
| **Doppelte Nachricht** | duplicate |
| **Zu viele Links** | links |
| **Gesperrtes Wort** | keyword |
| **Wegwerf-E-Mail** | disposable |
| **reCAPTCHA** | recaptcha |
| **StopForumSpam** | stopforumspam |
| **CleanTalk** | cleantalk |

Eine zugelassene Nachricht hat einen leeren Grund und **Blockiert** auf Nein.

Die Zeilenaktion ist Löschen. Markieren Sie Zeilen und nutzen Sie **Ausgewählte löschen**. Der Shop fragt **Ausgewählte Einträge löschen?**

### 3.13 Gesperrte IP-Adressen

![Gesperrte IP-Adressen](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-bans.webp)

Öffnen Sie **Gesperrte IP-Adressen** unter **Kontaktschutz**, oder die gleichnamige Schaltfläche in der **Übersicht**.

Die Spalten sind **ID**, **IP**, **Datum** und **Aktiv**. Die neueste Zeile steht oben. Eine leere Liste sagt auf dem englischen Bild **No records found**.

Das Plus öffnet das Anlegen. Der Formulartitel ist **Gesperrte IP-Adresse**.

![Neue gesperrte IP-Adresse](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-ban-form.webp)

| Feld | Am Anfang | Was es tut |
|---|---|---|
| **IP-Adresse** | leer | Eine IP-Adresse. Pflichtfeld. Solange die Sperre aktiv ist, werden Kontaktnachrichten von dieser IP abgelehnt. Fügen Sie die Adresse aus der Versuchsliste ein, genau wie protokolliert. Eine falsche Ziffer sperrt einen anderen Besucher oder niemanden. Eine gemeinsame Büroadresse sperrt auch echte Kunden auf dieser IP, bis Sie die Sperre ausschalten. |
| **Aktiv** | Nein | **Ja** hält die Sperre in Kraft, das Formular lehnt diese IP ab. **Nein** behält die Zeile und stoppt das Sperren, die Adresse kann also wieder schreiben, außer eine andere Prüfung stoppt sie. Wählen Sie **Ja**, solange diese Adresse noch Spam schickt. Wählen Sie **Nein**, wenn ein Kunde an dieser IP durchkommen muss und Sie den Eintrag behalten wollen. Eine Sperre aus **Schutz** wird bereits aktiv gespeichert. |

**Speichern** speichert die Zeile. Abbrechen kehrt zur Liste zurück, ohne zu speichern.

Bei einer bestehenden Zeile öffnet **Bearbeiten** dasselbe Formular, Löschen entfernt die Zeile, und das Symbol **Aktiv** schaltet die Sperre an oder aus. Markieren Sie Zeilen und nutzen Sie **Ausgewählte löschen**. Der Shop fragt **Ausgewählte Einträge löschen?**

Eine Sperre aus **Schutz** lehnt die nächste Kontaktnachricht dieser IP mit dem Grund **Gesperrte IP** (kurz ban) ab und legt für denselben Treffer keine zweite Sperre an.

## 4. Shopfront

Das Modul arbeitet nur auf der Kontaktseite des Shops. Auf anderen Seiten fügt es nichts hinzu.

Mit den Einstellungen nach der Installation, bevor Sie beide reCAPTCHA-Schlüssel speichern, sieht der Kunde das gewöhnliche Kontaktformular des Themes. Auf der Seite gibt es nichts Zusätzliches aufzunehmen: das Honeypot liegt außerhalb des Bildschirms, der Zähler ist verborgen, und das reCAPTCHA-Kästchen wird nicht gezeigt.

Nachdem Sie beide Schlüssel gespeichert haben und **reCAPTCHA aktivieren** auf Ja lassen:

- **reCAPTCHA v2** fügt das Kontrollkästchen hinzu. Sendet der Kunde ohne Haken, sagt die Seite **Bitte bestätigen Sie, dass Sie kein Roboter sind.** und das Formular geht nicht.
- **reCAPTCHA v3** zeigt keine Aufgabe. Die Google-Plakette kann erscheinen. Ein Wert unter dem Schwellenwert wird auf dem Server abgelehnt.

| Was geschehen ist | Was der Kunde sieht |
|---|---|
| v2-Kästchen nicht angehakt | **Bitte bestätigen Sie, dass Sie kein Roboter sind.** Das Formular bleibt auf der Seite. |
| Captcha fehlgeschlagen, oder Google nicht erreichbar | **Die Captcha-Prüfung ist fehlgeschlagen. Bitte versuchen Sie es erneut.** |
| Jede andere Sperre, und keine Weiterleitung angehakt | **Ihre Nachricht konnte nicht gesendet werden. Bitte versuchen Sie es in ein paar Minuten erneut.** |
| Weiterleitung zur Startseite angehakt | Die Startseite des Shops. Kein Fehler auf der Kontaktseite. |
| CMS-Weiterleitung angehakt, eine Seite gewählt, Startseiten-Weiterleitung nicht | Diese CMS-Seite. |
| Google-Weiterleitung angehakt, die anderen werden nicht genutzt | https://www.google.com |

Eine Nachricht, die durchkommt, sendet das Kontaktformular wie sonst. Das Modul ändert diese Bestätigung nicht.

Das Theme kann das Stylesheet und das Skript des Moduls für die Shopfront ersetzen. Eine Modulvorlage für das Formular kann es nicht ersetzen, weil das Formular das Kontaktformular des Shops ist. Entfernt das Theme die Senden-Schaltfläche dieses Formulars, werden Honeypot, Zähler und Captcha nicht angehängt.

## 5. Probleme

**Der Kunde sieht „Bitte bestätigen Sie, dass Sie kein Roboter sind.“**

Das v2-Kästchen war nicht angehakt. Bitten Sie den Kunden, es anzuhaken und erneut zu senden. Das sperrt die IP nicht.

**Der Kunde sieht „Die Captcha-Prüfung ist fehlgeschlagen. Bitte versuchen Sie es erneut.“**

Das Captcha ist nicht bestanden, oder der Shop hat Google nicht erreicht. Prüfen Sie, ob der **reCAPTCHA-Typ** zum Schlüssel in der Google-Konsole passt, ob **Website-Schlüssel** und **Geheimer Schlüssel** das Paar für diese Domain sind und ob der Shop-Server Google erreicht. Ein fehlgeschlagenes Captcha sperrt die IP nicht. Der Kunde kann es erneut versuchen.

**Der Kunde sieht „Ihre Nachricht konnte nicht gesendet werden. Bitte versuchen Sie es in ein paar Minuten erneut.“**

Eine andere Prüfung hat die Nachricht abgelehnt, und keine Weiterleitung ist angehakt. Öffnen Sie **Nachrichtenversuche**, suchen Sie die IP oder die E-Mail und lesen Sie **Grund**. Dann:

- flood: **Erlaubte Nachrichten** oder **Zeitfenster** erhöhen, oder warten, bis das Fenster vorbei ist.
- honeypot: ein Skript oder Autofill hat das versteckte Feld gefüllt. **Honeypot-Feld** ausschalten, wenn Ihre eigenen Kunden blockiert werden.
- timing: das Formular ging schneller als **Mindestsekunden**. Die Zahl nur erhöhen, wenn echte Kunden blockiert werden. Diese Sperre sperrt die IP nicht.
- user-agent: **Leeren User-Agent blockieren** ausschalten, wenn ein Datenschutzwerkzeug beteiligt ist.
- duplicate: derselbe Text mit mindestens 20 Zeichen wurde im **Duplikat-Zeitfenster** erneut gesendet.
- links: die Nachricht hat mehr Links als **Maximale Anzahl Links**.
- keyword: eine Zeile in **Wörter und Phrasen** trifft E-Mail oder Nachricht.
- disposable: die E-Mail-Domain steht auf der eingebauten Liste oder in **Zusätzliche Wegwerf-Domains**.
- stopforumspam oder cleantalk: die Adresse steht in diesem Dienst. **Mindestanzahl Meldungen** oder **Schwellenwert für Spamrate** erhöhen, oder die Adresse in die **Whitelist** setzen, wenn es ein Kunde ist.
- ban: die Adresse steht unter **Gesperrte IP-Adressen** mit **Aktiv** auf **Ja**. Auf **Nein** setzen oder die Zeile löschen.

**Der Kunde landet auf der Startseite, einer CMS-Seite oder bei Google.**

Es gab eine harte Sperre und unter **Schutz** ist eine Weiterleitung angehakt. **Zur Startseite weiterleiten**, **Zu einer CMS-Seite weiterleiten** und **Zu Google weiterleiten** abwählen, wenn der Fehler auf der Kontaktseite bleiben soll. Sind mehrere angehakt, gewinnt die Startseite, dann die CMS-Seite, dann Google.

**Ein ganzes Büro kann nicht schreiben.**

Das Büro teilt eine IP. Diese IP ist gesperrt, über dem Flood-Limit oder in einem Dienst gelistet. Öffnen Sie **Gesperrte IP-Adressen** und setzen Sie **Aktiv** auf **Nein**, oder tragen Sie die Adresse in die **Whitelist** ein. Eine Whitelist-Zeile überspringt jede Prüfung, auch die Sperre.

**reCAPTCHA bleibt aus.**

Die Warnung sagt **reCAPTCHA ist aktiviert, aber der Website-Schlüssel oder der geheime Schlüssel ist leer. Das Captcha bleibt deaktiviert, bis beide Schlüssel gespeichert sind.** Beide Schlüssel einfügen und **Speichern** klicken.

**Kostenpflichtiges CleanTalk blockiert niemanden.**

Die Warnung sagt **Die kostenpflichtige CleanTalk-API ist aktiviert, aber der Zugriffsschlüssel ist leer.** **Zugriffsschlüssel** einfügen und **Speichern** klicken. Ein abgelehnter Schlüssel lässt die Nachricht ebenfalls durch. Antwortet der Dienst nicht, wird die Nachricht zugelassen.

**Keine E-Mail kommt im Shop an.**

**Shop per E-Mail benachrichtigen** muss angehakt sein. Die Sperre muss etwas anderes sein als Captcha oder zu schnell. Dieselbe IP sendet nur eine Mail in 30 Minuten. Die Shop-E-Mail in den Shop-Parametern muss ausgefüllt sein. Der Betreff bekommt den kurzen Prüfnamen, zum Beispiel [flood].

**Jetzt prüfen zeigt nichts Neues.**

Der Shop-Server hat MyPresta.eu nicht erreicht, oder das Modul ist schon aktuell. Die Antwort **Das Modul ist aktuell!** bedeutet, dass keine neuere Version gemeldet wurde. **Jetzt prüfen** lädt die Datei nicht herunter.

**Die Listen sind nach einer erneuten Installation leer.**

Die Deinstallation löscht Versuche und Sperren. Eine neue Installation bringt sie nicht zurück.

## 6. Für Entwickler

### 6.1 Überblick

Hauptklasse `mycontactprotectionpro`, Version `1.0.0`, Autor MyPresta.eu, Tab `administration`. Der Listenname ist **Contact page - spam protection PRO**. Die Kompatibilität in der Datei ist PrestaShop 1.7.7.0 bis 9.99.99.

Einstellungen werden mit `Configuration::get` im Shop-Kontext gelesen, der beim Klick auf **Speichern** aktiv ist. Ein POST der Kontaktseite mit `submitMessage` führt `hookActionFrontControllerInitAfter` aus. Ein Treffer schreibt eine zugelassene Zeile und lässt das Formular senden. Eine Sperre schreibt eine blockierte Zeile, ein harter Grund kann eine Sperre anlegen, die Shop-Mail senden und weiterleiten.

`install()` ruft die Elterninstallation, schreibt die Konfiguration, legt die beiden Tabellen an, legt das Menü an und registriert die drei Hooks. Es leert den Cache nicht. Es gibt kein eigenes `enable()` oder `disable()`. `uninstall()` löscht die Schlüssel aus 6.7 sowie `update_mycontactprotectionpro` und `updatev_mycontactprotectionpro`, löscht die Menü-Tabs, führt DROP beider Tabellen aus und ruft die Eltern-Deinstallation. `mypresta_updates` wird nicht gelöscht. Die Dateien bleiben, bis das Modulverzeichnis entfernt wird.

### 6.2 Dateien

| Datei | Rolle |
|---|---|
| mycontactprotectionpro.php | install, uninstall, Hooks, Formulare, Prüfreihenfolge, Dashboard, Shop-Mail |
| controllers/admin/AdminMycontactprotectionpro.php | Menü-Elternteil; Weiterleitung zur Modulkonfiguration |
| controllers/admin/AdminMycontactprotectionproAttempts.php | Versuchsliste und Löschen |
| controllers/admin/AdminMycontactprotectionproBans.php | Sperrliste, Anlegen, Bearbeiten, Löschen, Schalter active |
| models/attempt.php | Versuchstabelle und Zähler |
| models/ban.php | Sperrtabelle und `banIp()` |
| lib/sfs.php | StopForumSpam-Abfrage |
| lib/ctalk.php | kostenloses und kostenpflichtiges CleanTalk |
| lib/updatesChecker.php | Update-Prüfung, Klasse `mycontactprotectionproUpdate` |
| lib/recaptcha/ | vom Modul genutzte reCAPTCHA-Bibliothek |
| views/templates/admin/configure.tpl | Registerleiste und Übersichtsmarkup |
| views/css/admin.css | Layout der Konfiguration im Backoffice |
| views/css/front.css | setzt das Honeypot außerhalb des Bildschirms |
| views/js/front.js | Honeypot, Zähler, v2-Kästchen und v3-Token am Formular |
| mails/{iso}/mcpp_merchant.html | HTML-Text der Shop-Mail; kein `$this->l()` |
| mails/{iso}/mcpp_merchant.txt | Text der Shop-Mail |
| translations/{iso}.php | Backoffice- und Kundentexte |
| key.php | Wert der kostenlosen CleanTalk-Anfrage |

Es gibt keinen Front-Controller und keine Front-Vorlage für das Kontaktformular.

### 6.3 Controller

| Klasse | Menü-Elternteil | Was sie annimmt |
|---|---|---|
| AdminMycontactprotectionproController | id 0, Icon security, Titel Contact protection | Weiterleitung zu AdminModules mit `configure=mycontactprotectionpro` |
| AdminMycontactprotectionproAttemptsController | AdminMycontactprotectionpro | Tabelle `mcpp_attempt`, Ordnung `id_mcpp_attempt` DESC, `list_no_link`, Zeile löschen, Massenlöschen. Kein Anlegen. |
| AdminMycontactprotectionproBansController | AdminMycontactprotectionpro | Tabelle `mcpp_ban`, Ordnung `id_mcpp_ban` DESC, Zeile bearbeiten und löschen, Massenlöschen, Status auf `active`. Formularfelder `ip` (Pflicht) und `active`. |

Die Konfiguration ist `getContent()` des Moduls, kein eigener Controller. Das Register steht in `mcpp_tab`. Die Absende-Namen sind `submitMcppAntiFlood`, `submitMcppCleanTalk`, `submitMcppStopForumSpam`, `submitMcppRecaptcha`, `submitMcppFilters`, `submitMcppWhitelist`, `submitMcppProtection`, `submitMcppMail`. Das Update-Formular sendet `submit_settings_updates` und `submit_settings_updates_now`.

Es gibt keinen Front-Controller. Die Kontaktseite ist der `ContactController` des Shops.

### 6.4 Hooks

| Hook | Wann er läuft |
|---|---|
| actionFrontControllerSetMedia | auf der Kontaktseite, wenn Honeypot, Zähler oder ein bereites reCAPTCHA an ist; lädt front.css und front.js und gibt dem Skript die öffentlichen Einstellungen |
| actionFrontControllerInitAfter | bei einem Kontaktseiten-POST mit submitMessage; prüft und kehrt zurück, stoppt das Formular oder leitet weiter |
| displayBackOfficeHeader | lädt views/css/admin.css |

Das Modul registriert keinen eigenen Display-Hook. Die Kontaktseite wird an `php_self` gleich `contact` erkannt, oder an der Klasse `ContactController` oder `ContactControllerCore`.

Im Backoffice ruft der Konstruktor `runUpdateSetUp()`. Die Methode fragt MyPresta etwa alle 259200 Sekunden, wenn `mypresta_updates` nicht 0 ist, speichert das Ergebnis in `updatev_mycontactprotectionpro` und hängt eine Controller-Warnung an, wenn die gespeicherte Version neuer ist.

### 6.5 Überschreibungen

Das Modul liefert keine Klassen- und keine Controller-Überschreibung.

### 6.6 Datenbank

Das Präfix ist das Shop-Präfix. Beim Öffnen einer Seite wird keine Spalte ergänzt. Die Deinstallation löscht beide Tabellen.

| Tabelle | Inhalt |
|---|---|
| mcpp_attempt | `id_mcpp_attempt` int Primärschlüssel, `ip` varchar 64, `email` varchar 255, `message_hash` varchar 64 (MD5 der Nachricht in Kleinbuchstaben), `reason` varchar 255 (kurzer Name, leer wenn zugelassen), `blocked` tinyint, `date_add` datetime. Schlüssel `ip_date` (`ip`, `date_add`) und `hash_date` (`message_hash`, `date_add`). |
| mcpp_ban | `id_mcpp_ban` int Primärschlüssel, `ip` varchar 64, `date_add` datetime, `active` tinyint Standard 1. Schlüssel `ip_active` (`ip`, `active`). Das Anlegeformular öffnet mit Aktiv = Nein. `banIp()` fügt die Zeile mit `active` 1 ein oder aktualisiert sie. |

### 6.7 Konfigurationsschlüssel und Übersetzungen

Wert, wenn der Schlüssel fehlt:

| Schlüssel | Wenn fehlend |
|---|---|
| mcpp_af | 1 |
| mcpp_time | 10 |
| mcpp_atmpt | 5 |
| mcpp_ct | 0 |
| mcpp_ct_paid | 0 |
| mcpp_ct_key | leer |
| mcpp_ct_rate | 1, eine gespeicherte 0 wird ebenfalls als 1 behandelt |
| mcpp_sfs | 0 |
| mcpp_sfs_key | leer |
| mcpp_sfs_freq | 1, eine gespeicherte 0 wird ebenfalls als 1 behandelt |
| mcpp_rc | 1 |
| mcpp_rc_type | 0, das ist v2; 1 ist v3 |
| mcpp_rc_site | leer |
| mcpp_rc_secret | leer |
| mcpp_rc_theme | light, außer der gespeicherte Wert ist dark |
| mcpp_rc_score | 0.5 |
| mcpp_hp | 1 |
| mcpp_tg | 1 |
| mcpp_tg_sec | 3, eine gespeicherte 0 wird als 1 behandelt |
| mcpp_links | 1 |
| mcpp_links_max | 3 |
| mcpp_kw | 0 |
| mcpp_kw_list | leer |
| mcpp_disp | 0 |
| mcpp_disp_extra | leer |
| mcpp_dup | 0 |
| mcpp_dup_min | 60, eine gespeicherte 0 wird als 1 behandelt |
| mcpp_ua | 0 |
| mcpp_bypass | 0 |
| mcpp_ptype_1 | 0, IP sperren |
| mcpp_ptype_4 | 0, E-Mail an den Shop |
| mcpp_ptype_7 | 0, Weiterleitung zur Startseite |
| mcpp_ptype_6 | 0, CMS-Weiterleitung |
| mcpp_ptype_5 | 0, Google-Weiterleitung |
| mcpp_cms | 0 |
| mcpp_wh_ip | leer |
| mcpp_mtitle | Contact form spam blocked, je Sprache; ein leerer Betreff nutzt diesen englischen Satz |
| mcpp_dash_preset | 30; jeder andere Wert als 7, 30, 90, 180, 365 oder custom fällt auf 30 zurück |
| mcpp_dash_from | leer, bis die Übersicht das Fenster baut |
| mcpp_dash_to | leer, bis die Übersicht das Fenster baut |

`mypresta_updates` ist gemeinsam. Fehlt er, gelten Benachrichtigungen als aktiviert. Die Deinstallation löscht ihn nicht. `key.php` setzt `mkey`. Ist es leer, nutzt die kostenlose CleanTalk-Anfrage `nlc`. Die Update-Prüfung nutzt `nokey`, wenn der Wert fehlt.

Eingebaute Wegwerf-Domains, auf der Domain und ihren Subdomains: mailinator.com, guerrillamail.com, guerrillamail.info, guerrillamail.biz, guerrillamail.de, guerrillamail.net, guerrillamail.org, guerrillamailblock.com, sharklasers.com, grr.la, yopmail.com, yopmail.fr, yopmail.net, trashmail.com, trashmail.de, trash-mail.com, tempmail.com, temp-mail.org, 10minutemail.com, 10minutemail.net, throwawaymail.com, getnada.com, dispostable.com, maildrop.cc, fakeinbox.com, mailnesia.com, mohmal.com, emailondeck.com, tempail.com, moakt.com, spam4.me, byom.de, mintemail.com, mytemp.email, tmpmail.net, tmpmail.org, discard.email, discardmail.com, inboxkitten.com, getairmail.com, generator.email, mailcatch.com. Domains aus `mcpp_disp_extra` kommen auf dieselbe Weise dazu.

Beschriftungen, Feldbeschreibungen und die drei Kundensätze sind `$this->l()` in `mycontactprotectionpro.php`, `lib/updatesChecker.php` (Quelle `updatesChecker`), `AdminMycontactprotectionproAttempts.php` (Quelle `AdminMycontactprotectionproAttempts`) und `AdminMycontactprotectionproBans.php` (Quelle `AdminMycontactprotectionproBans`). Eine Sprache ergänzen Sie mit `translations/{iso}.php`. Die Feldbeschreibungen stehen im `desc` der HelperForm-Felder in der Hauptklasse und im Sperr-Controller.

Die Mailtexte in `mails/{iso}/mcpp_merchant.html` und `mails/{iso}/mcpp_merchant.txt` laufen nicht über `$this->l()`. Der englische Text beginnt mit `Contact form blocked.` Der Betreff ist `mcpp_mtitle` der Mailsprache, mit angehängtem kurzem Grund, zum Beispiel ` [flood]`. Die Mail geht an `PS_SHOP_EMAIL`. Eine leere Shop-E-Mail sendet nichts. Im Text stehen die ersten 500 Zeichen der Nachricht ohne Tags.

### 6.8 Erweitern

Ein Theme kann `views/css/front.css` und `views/js/front.js` überschreiben. Eine Front-Vorlage für das Formular gibt es nicht, das Theme hat also keine Modul-Formularvorlage zum Überschreiben. Das Markup ist das Kontaktformular des Shops. `front.js` sucht `form [name=submitMessage]`. Fehlt diese Schaltfläche, kehrt das Skript zurück und fügt nichts hinzu.

Der Honeypot-Name ist `mcpp_website`. Der Zählername ist `mcpp_ts`. Ein gefülltes Honeypot ist ein Treffer. Ein fehlender Zähler ist keiner. Ein Zähler in der Zukunft ist ein Treffer. reCAPTCHA v3 nutzt die Aktion `contact`.

Die Prüfreihenfolge ist fest: ban, honeypot, timing, leerer User-Agent, flood, duplicate, links, keyword, disposable, recaptcha, stopforumspam, kostenloses CleanTalk, kostenpflichtiges CleanTalk. Der erste Treffer gewinnt. Whitelist und die Ausnahme für Angemeldete kehren zurück, bevor eine Zeile geschrieben wird. Ist `protectionEnabled()` falsch und die IP nicht gesperrt, kehrt der Hook ohne Schreiben zurück. `protectionEnabled()` ist wahr, wenn eines von `mcpp_af`, `mcpp_ct`, `mcpp_ct_paid`, `mcpp_sfs`, `mcpp_hp`, `mcpp_tg`, `mcpp_links`, `mcpp_kw`, `mcpp_disp`, `mcpp_dup`, `mcpp_ua` 1 ist, oder wenn reCAPTCHA bereit ist (Schalter an und beide Schlüssel nicht leer).

Harte Gründe sind jeder Grund außer `timing` und `recaptcha`. Nur ein harter Grund kann eine Sperre anlegen, die Shop-Mail senden und weiterleiten. Die Weiterleitungspriorität ist `mcpp_ptype_7` (Startseite), dann `mcpp_ptype_6`, wenn `mcpp_cms` größer als 0 ist, dann `mcpp_ptype_5` (`https://www.google.com`). Sonst entfernt das Modul `submitMessage` und setzt den Fehler. Eine Recaptcha-Sperre nutzt den Captcha-Satz. Jede andere Sperre, die auf der Seite bleibt, nutzt den Satz über ein paar Minuten.

Kostenloses CleanTalk wird übersprungen, wenn `openssl_encrypt` nicht existiert. StopForumSpam und CleanTalk lassen die Nachricht zu, wenn der entfernte Aufruf scheitert. reCAPTCHA blockiert die Nachricht, wenn der entfernte Aufruf scheitert. Flood nutzt `countByIpSince`, das jeden Versuch im Fenster zählt. Duplicate nutzt `countDuplicateSince`, das Zeilen mit dem Grund `timing` oder `recaptcha` ignoriert, und läuft nur, wenn die Nachricht mindestens 20 Zeichen lang ist.

PHP-Aufrufe: `curl_init`, wenn es existiert, sonst `file_get_contents` für StopForumSpam, CleanTalk und die Update-Prüfung, wenn `allow_url_fopen` an ist. `openssl_encrypt` für die kostenlose CleanTalk-Anfrage. `json_decode` für die Antworten von StopForumSpam, kostenpflichtigem CleanTalk und reCAPTCHA. Ein weiteres Modul ist nicht nötig.

## 7. Hilfe

Modulseite: https://mypresta.eu/modules/administration-tools/contact-page-spam-protection-pro.html

Zu diesem Modul melden Sie sich im Kundenkonto auf [https://mypresta.eu/](https://mypresta.eu/) an und öffnen das Kontaktformular. Wählen Sie das Thema **Support for paid modules**. Das Formular sagt, dass die Anmeldung nötig ist. Danach wählen Sie dieses Modul aus der Kaufhistorie. Die Seite ist [https://mypresta.eu/contact-form](https://mypresta.eu/contact-form).

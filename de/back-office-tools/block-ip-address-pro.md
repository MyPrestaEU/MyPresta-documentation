---
title: Ban IP Pro - Dokumentation und Benutzerhandbuch
sidebar:
  label: Ban IP Pro - Dokumentation und Benutzerhandbuch
description: Anleitung zur Konfiguration und zur Fehlersuche für Shops, die Ban IP Pro bereits haben.
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Block IP address Pro auf MyPresta.eu kaufen](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/back-office-tools/block-ip-address-pro/)
>
> ---


## 1. Anforderungen

Ban IP Pro läuft innerhalb von PrestaShop. Es braucht kein weiteres Modul.

Die Beschriftungen des Moduls auf dem Bildschirm sind Englisch. In dieser Anleitung stehen sie so, wie Sie sie im Backoffice sehen.

- PrestaShop 1.7.1.0 bis PrestaShop 9.
- PHP 7.1 oder neuer, und mindestens die PHP-Version, die diese PrestaShop-Version verlangt. Die Installation stoppt bei PHP älter als 7.1.
- Ländererkennung und Ländersperre brauchen PHP 7.2 oder neuer und eine MaxMind-Länderdatei, die Sie selbst hochladen. Sperren, die Freigabeliste, die Login-Prüfung und das Anfragelimit arbeiten ohne diese Datei, auch unter PHP 7.1.
- Keine zusätzliche PHP-Erweiterung ist nötig. Die Update-Prüfung nutzt cURL, wenn der Server es hat. Ohne cURL liest die Prüfung die Adresse nur, wenn der Server entfernte Adressen lesen darf.
- Kein anderes Modul ist nötig. Ein MaxMind-Konto brauchen Sie nur für die Länderdatei. Das Modul lädt diese Datei nicht selbst herunter.
- Ein Import nimmt bis zu 5000 Zeilen und eine Datei bis 2 MB an. Eine lange Regelliste wird bei jedem Besuch aus einer Cache-Datei gelesen, eine sehr lange Liste macht diese Datei groß. Nach einem großen Import nutzen Sie **Rebuild cache** unter **Tools**, wenn die Zähler veraltet aussehen.

## 2. Installation

1. Öffnen Sie im Backoffice **Module**, dann **Modul-Manager**.
2. Laden Sie die Modul-Zip hoch und klicken Sie auf **Installieren**.
3. Öffnen Sie **Konfigurieren** bei **Ban IP pro**. Die Seite öffnet sich auf **Dashboard**. In der Leiste stehen außerdem **Statistics**, **Behavior**, **Automation**, **Network**, **Tools** und **Updates**.
4. Im linken Menü erscheint **Ban IP** unter **Erweiterte Parameter**. Das ist die Regelliste. **Manage rules** auf der Modulseite führt zur selben Liste.

Die Installation schreibt einen leeren Regel-Cache. Sie leert den PrestaShop-Cache nicht. Fehlt der Menüpunkt nach einem Update, öffnen Sie **Konfigurieren** einmal. Die Seite ergänzt die Tabellen des Moduls. Schlägt das fehl, sehen Sie **The module database could not be updated.**

Zum Abschalten nutzen Sie den Schalter im **Modul-Manager**. Die Prüfungen stoppen. Regeln, Protokolle und Einstellungen bleiben. Schalten Sie das Modul wieder ein, gelten dieselben Regeln. Das Modul hat keinen eigenen Ein- oder Ausschalter.

Zum Entfernen klicken Sie auf **Deinstallieren** und bestätigen. Die Deinstallation entfernt den Menüpunkt **Ban IP** und hängt die Prüfungen ab. Regeln, Sperrprotokoll, Tagessummen, Zähler fehlgeschlagener Logins, die Liste der Mitarbeiteraktionen und die Einstellungen bleiben in der Datenbank. Die hochgeladene Länderdatei bleibt im Modulordner. Eine erneute Installation behält diese Regeln und füllt nur Einstellungen, die noch leer sind.

## 3. Konfiguration und tägliche Arbeit

Ein Besucher öffnet den Shop. Bevor die Seite entsteht, liest das Modul seine IP-Adresse. Eine Allow-Regel gewinnt gegen eine Sperre. Passt eine Sperre auf den Shop, steht das Land des Besuchers auf der Sperrliste, hat er einen Prüfpfad geöffnet oder hat die Adresse das Anfragelimit überschritten, sieht er die Sperrseite oder die Weiterleitung, die Sie gesetzt haben. Die Sperre landet im Protokoll. Ihre Arbeit beginnt auf **Dashboard** oder unter **Erweiterte Parameter**, **Ban IP**. Sie legen eine Regel an, importieren eine Liste oder lassen **Automation** Sperren erzeugen. Eine Sperre kann ablaufen. Beim ersten Aufruf jedes Tages werden abgelaufene Regeln ausgeschaltet und alte Protokollzeilen gelöscht. Der Weg endet, wenn der Besucher gesperrt, weitergeleitet oder durchgelassen wird.

Öffnen Sie **Module**, **Modul-Manager**, **Ban IP pro**, **Konfigurieren**.

### 3.1 Dashboard

![Dashboard](https://mypresta.eu/docs/images/docs/banippro-configure-dashboard.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt dieser Teil **Dashboard**.

**Dashboard** ist der erste Reiter. **Manage rules** öffnet die Regelliste.

Die sieben Zähler zeigen nur Zahlen. Sie speichern nichts.

| Feld | Am Start | Wirkung |
|---|---|---|
| **Manage rules** | eine Schaltfläche | Öffnet **Ban IP** unter **Erweiterte Parameter**. |
| **Active bans** | 0 | Sperrregeln, die noch an sind. Allow-Regeln zählen nicht mit. |
| **Blocked today** | 0 | Gesperrte Aufrufe seit Mitternacht, aus den Tagessummen. |
| **Blocked in 7 days** | 0 | Gesperrte Aufrufe der letzten 7 Tage, heute eingeschlossen. |
| **Blocked in 30 days** | 0 | Gesperrte Aufrufe der letzten 30 Tage, heute eingeschlossen. |
| **Unique IPs today** | 0 | Verschiedene IP-Adressen im heutigen Sperrprotokoll. |
| **Expiring in 48 hours** | 0 | Aktive Sperren, deren Ende in den nächsten 48 Stunden liegt. |
| **Active automatic bans** | 0 | Aktive Sperren wegen Login, Prüfpfad oder Anfragelimit. |

**Blocked requests** ist ein Diagramm der letzten 30 Tage. Es liest die Tagessummen. Es speichert nichts.

**Recent blocks** listet die letzten gesperrten Aufrufe: Datum, IP-Adresse, Land, Pfad und Grund. Das Land bleibt leer, bis Sie die Länderdatei unter **Network** hochladen. Eine leere Liste sagt **No blocked requests yet.**

**Your current IP** zeigt die Adresse, die dieses Backoffice sieht. **Add to allow list** speichert diese Adresse als Allow-Regel für Shop und Backoffice. Die Seite sagt dann **Your current IP address is on the allow list.** Lässt sich die Adresse nicht lesen, sehen Sie **Your current IP address could not be detected.** Lässt sich die Zeile nicht speichern, sehen Sie **The address could not be added to the allow list.**

**Module status** hat vier Zeilen.

| Zeile | Am Start | Wirkung |
|---|---|---|
| **Front hook** | **Registered** nach einer normalen Installation | **Registered** heißt, der Shop führt die Prüfung aus. **Missing** heißt, die Prüfung hängt nicht. Installieren Sie das Modul neu oder öffnen Sie **Konfigurieren** nach einem Update. |
| **Cached rules** | 0 | Wie viele aktive Regeln der Cache angenommen hat. |
| **Unreadable rules** | 0 | Aktive Zeilen, die der Cache nicht als Adresse lesen konnte. |
| PHP und PrestaShop | die Versionen auf diesem Server | Damit Sie sie mit den Anforderungen vergleichen. |

**Quick ban** schreibt eine Sperre. Der Bereich kommt aus **Default scope of new bans** unter **Behavior**. Eine Sperre von hier sendet keine Alarm-E-Mail.

| Feld | Am Start | Wirkung |
|---|---|---|
| **IP address** | leer | Eine Adresse, ein Muster wie `192.168.1.*`, ein Netz wie `10.0.0.0/8` oder ein Bereich wie `192.168.1.10-192.168.1.20`. |
| **Reason** | **Manual** | **Manual**, **Fraud**, **Spam**, **Scanner**, **Chargeback** oder **Competitor**. Die Statistik nutzt diese Bezeichnung. |
| **Duration** | **Permanent** | **1 hour**, **24 hours**, **7 days**, **30 days** oder **Permanent**, bis Sie die Regel löschen. |
| **Comment** | leer | Eine private Notiz. Der Besucher sieht sie nie. |
| **I confirm blocking my own IP** | aus | Nur nötig, wenn die Sperre die IP treffen würde, mit der Sie im Backoffice sind, und der Bereich das Backoffice einschließt. |
| **Ban this address** | eine Schaltfläche | Speichert die Sperre und zeigt **The address was banned.** |

**Test an address** legt nichts an und löscht nichts.

| Feld | Am Start | Wirkung |
|---|---|---|
| **IP address** | leer | Die Adresse, die Sie prüfen wollen. |
| **Test** | eine Schaltfläche | Zeigt das Ergebnis für den Shop, das Ergebnis für das Backoffice und das Land. |
| **Front office** | verborgen bis zum Test | **No matching rule.**, **Allowed by rule #…** oder **Blocked by rule #…**. |
| **Back office** | verborgen bis zum Test | Dieselben drei Ergebnisse für das Backoffice. |
| Hinweis unter der Backoffice-Zeile | wenn der Schutz aus ist | **Back office protection is disabled, so back-office bans are not enforced.** |
| **Country** | **Unknown**, wenn die Datei fehlt | Der Ländercode, dazu **Blocked by country rule**, wenn dieses Land auf der Sperrliste steht. |

**Recent admin actions** listet die letzten Mitarbeiteraktionen, zum Beispiel Anlegen, Import, Freigabe, Entsperren und Cache-Neuaufbau. Eine leere Liste sagt **No admin actions yet.**

### 3.2 Statistics

![Statistics](https://mypresta.eu/docs/images/docs/banippro-configure-stats.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt dieser Teil **Statistics**.

**Statistics** liest das Sperrprotokoll. **24h**, **7 days** und **30 days** laden die Seite für diesen Zeitraum neu. Beim ersten Öffnen gilt **30 days**.

| Feld | Am Start | Wirkung |
|---|---|---|
| **24h** | eine Schaltfläche | Die letzten 24 Stunden. Das Diagramm hat einen Punkt pro Stunde. |
| **7 days** | eine Schaltfläche | Die letzten 7 Tage, heute eingeschlossen. Ein Punkt pro Tag. |
| **30 days** | eine Schaltfläche, am Start gewählt | Die letzten 30 Tage, heute eingeschlossen. |
| **Export CSV** | eine Schaltfläche | Lädt `banippro-hits.csv` für den Zeitraum auf dem Bildschirm. Regeln bleiben unverändert. |
| **From** | der erste Tag des offenen Zeitraums | Zusammen mit **To** und **Apply**. |
| **To** | heute | Zusammen mit **From** und **Apply**. Liegt **From** nach **To**, tauschen die Tage. |
| **Apply** | eine Schaltfläche | Lädt den Reiter für diese Tage neu. Speichert nichts. |
| **Blocked requests** | 0 | Wie viele Sperren in den Zeitraum fallen. |
| **Unique IPs** | 0 | Wie viele verschiedene Adressen in dem Zeitraum gesperrt wurden. |

Das Diagramm **Blocked requests** folgt den Schaltflächen darüber. Darunter:

| Block | Was Sie sehen |
|---|---|
| **Top IP addresses** | Ein Balkendiagramm der 10 Adressen mit den meisten Sperren im Zeitraum. |
| **Top paths** | Die 10 am häufigsten gesperrten Pfade, mit Anzahl. |
| **Top reasons** | Die 10 Gründe der passenden Regeln, mit Anzahl. |
| **Top countries** | Die 10 Ländercodes, mit Anzahl. Leer, bis die Länderdatei hochgeladen ist. |
| **Block log** | Datum, IP-Adresse, Land, Pfad, Adresse der Regel und Grund. Bis zu 100 Zeilen. |

Eine leere Auswertung sagt **No data for this period.** Ein leeres Protokoll sagt **No blocked requests in this period.**

Die Tagessummen hinter dem Dashboard-Diagramm bleiben, wenn Sie **Keep logs for days** kürzen. Diese Einstellung löscht das zeilenweise Protokoll und die Liste der Mitarbeiteraktionen. Die Tagessummen löscht sie nicht.

### 3.3 Behavior

![Behavior](https://mypresta.eu/docs/images/docs/banippro-configure-behavior.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt dieser Teil **Behavior**.

Klicken Sie auf **Save**. Die Seite zeigt **Settings updated**.

| Feld | Am Start | Wirkung |
|---|---|---|
| **Message for blocked visitors** | **You are blocked** auf Englisch. Polnische, spanische und portugiesische Shops bekommen zusätzlich einen Satz in dieser Sprache. Jede andere Sprache bekommt den englischen Satz. | Der Text auf der Sperrseite. Füllen Sie jede Sprache des Shops. Der Besucher sieht den Satz der Seitensprache. |
| **Redirect blocked visitors** | **No** | **Yes** schickt gesperrte Besucher auf **Redirect URL** statt der Nachricht. **No** behält die Sperrseite. |
| **Redirect URL** | leer | Ein voller `http`- oder `https`-Link. Wird ignoriert, solange der Schalter darüber **No** ist. Ein ungültiger Link stellt den Schalter auf **No** und zeigt **Enter a valid http or https URL for the redirect.** |
| **Default scope of new bans** | **Front office** | Gilt für **Quick ban** und **Import**, wenn diese Bildschirme nicht nach dem Bereich fragen. **Front office** ist der Shop. **Back office** ist dieses Backoffice. **Front office and back office** ist beides. |
| **Protect the back office** | **No** | **Yes** setzt Sperren auch in diesem Backoffice durch. **Save** lehnt **Yes** ab, bis Ihre aktuelle IP auf der Freigabeliste steht, und zeigt **Add your current IP to the allow list before you protect the back office.** Der Schalter bleibt **No**. |

Das Formular zeigt außerdem diesen Hinweis: **Back office protection stays off until your current IP is on the allow list. Rules still apply to the shop front by default.**

### 3.4 Automation

![Automation](https://mypresta.eu/docs/images/docs/banippro-configure-automation.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt dieser Teil **Automation**.

Klicken Sie auf **Save**. Die Seite zeigt **Settings updated**. Automatische Sperren gelten für den Shop, in jedem Shop dieser Installation. Sie schalten **Protect the back office** nicht ein. Eine Adresse, die schon zu einer Allow-Regel passt, wird nicht gesperrt. Eine Adresse mit einer aktiven Sperre bleibt unverändert.

| Feld | Am Start | Wirkung |
|---|---|---|
| **Block known probe paths** | **Yes** | **Yes** sperrt einen Shop-Besucher, der einen Pfad aus der Liste unten öffnet. Ihr Admin-Ordner wird so nie gesperrt. **No** schaltet diese Prüfung ab. |
| **Probe ban length in hours** | 24 | Wie lange diese Sperre gilt. 24 ist ein Tag. 0 behält sie, bis Sie sie löschen. |
| **Probe paths** | `/.env`, `/wp-login.php`, `/wp-admin`, `/xmlrpc.php`, `/vendor/phpunit`, `/phpmyadmin`, `/.git/`, `/boaform`, `/cgi-bin/`, eine pro Zeile | Ein Aufruf, dessen Pfad eine dieser Zeilen enthält, wird sofort gesperrt. Eine leere Liste wird beim Speichern durch diese Standardliste ersetzt. Eine Zeile, die nur `/` ist, und eine Zeile, die Ihr Admin-Ordner ist, fallen weg. |
| **Ban customers after failed logins** | **No** | **Yes** zählt falsche Kundenpasswörter. Ein erfolgreicher Kundenlogin setzt den Zähler zurück. |
| **Ban employees after failed logins** | **No** | Dieselbe Zählung für das Mitarbeiter-Login. Setzen Sie Ihre eigene IP auf die Freigabeliste, bevor Sie das einschalten. Die Sperre gilt für den Shop, nicht für das Backoffice, außer eine Sperre, deren Bereich das Backoffice einschließt, trifft diese IP ebenfalls. |
| **Failed logins before a ban** | 5 | Bei 5 erzeugt der nächste Fehlversuch im Fenster die Sperre. Der kleinste gespeicherte Wert ist 1. |
| **Failed login window in minutes** | 15 | Ältere Fehlversuche werden vergessen. Der kleinste gespeicherte Wert ist 1. |
| **Login ban length in hours** | 24 | Wie lange die Login-Sperre gilt. 0 behält sie, bis Sie sie löschen. |
| **Limit requests per IP** | **No** | **Yes** zählt Shop-Seitenaufrufe. Bilder und andere Dateien, die PrestaShop nie erreichen, zählen nicht. Lassen Sie das bei normalem Verkehr auf **No**. In einem belebten Shop sperrt ein niedriges Limit echte Kunden. |
| **Requests allowed in the window** | 120 | Wie viele Seitenaufrufe eine IP im Fenster machen darf. Der kleinste gespeicherte Wert ist 1. |
| **Rate limit window in minutes** | 1 | Länge dieses Fensters. 1 heißt, das Limit oben gilt pro Minute. |
| **Rate limit ban in minutes** | 15 | Wie lange die Sperre nach dem Überschreiten gilt. Der kleinste gespeicherte Wert ist 1. |
| **Email me when an automatic ban is created** | **No** | **Yes** sendet eine E-Mail, wenn das Modul selbst eine Sperre anlegt. Sperren von Hand senden sie nicht. Höchstens eine E-Mail pro Stunde. |
| **Alert email** | leer | Das Postfach für den Alarm. Leer lassen, dann gilt die Shop-E-Mail. Ein Wert, der keine E-Mail ist, wird geleert, und die Seite zeigt **Enter a valid alert email address.** |

Der Betreff der Mail ist **Ban IP Pro alert**. Die Nachricht nennt die IP, den Grund (`auto-login`, `auto-honeypot` oder `auto-rate`), die Endzeit oder das Wort `permanent` und den Shopnamen.

### 3.5 Network

![Network](https://mypresta.eu/docs/images/docs/banippro-configure-network.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt dieser Teil **Network**.

Klicken Sie auf **Save**. Die Seite zeigt **Settings updated**.

| Feld | Am Start | Wirkung |
|---|---|---|
| **Trust Cloudflare** | **No** | Nur einschalten, wenn die Shop-Domain über Cloudflare läuft. Das Modul liest die Besucher-IP dann von Cloudflare, und nur wenn die Verbindung wirklich von Cloudflare kommt. Lassen Sie **No**, wenn Sie unsicher sind, sonst kann jeder Besucher wie der Proxy aussehen. |
| **Trusted reverse proxies** | leer | Steht ein Proxy oder Load Balancer vor dem Shop, tragen Sie seine IP oder sein Netz hier ein, eines pro Zeile. Das Modul liest die Besucher-IP nur von diesem Proxy. Leer lassen, wenn Sie unsicher sind. |
| **Block selected countries** | **No** | **Yes** sperrt jeden Besucher, dessen Land auf der Liste unten steht. Das arbeitet erst nach dem Hochladen der Länderdatenbank. Tragen Sie Ihr eigenes Land nicht ein. Eine Ländersperre fügt keine Zeile unter **Ban IP** hinzu. Sie sperrt diesen Aufruf und schreibt eine Protokollzeile mit dem Grund **Country**. |
| **Country codes** | leer | Zwei Buchstaben, zum Beispiel `PL`, `DE` oder `US`. Trennen Sie sie mit Kommas, Leerzeichen oder neuen Zeilen. Alles, was nicht zwei Buchstaben hat, fällt weg. |
| **Keep logs for days** | 90 | Wie viele Tage das Sperrprotokoll und die Liste der Mitarbeiteraktionen bleiben. Ältere Zeilen verschwinden beim ersten Aufruf eines späteren Tages. Der kleinste gespeicherte Wert ist 1. Werte über 3650 werden als 3650 gespeichert. |
| **GeoLite2 country database** | keine Datei | Optional. Wählen Sie eine Datei, deren Name auf `.mmdb` endet. Nach **Save** kann die Statistik das Land zeigen, und die Ländersperre kann arbeiten. Der Rest des Moduls braucht diese Datei nicht. |

Über dem Dateifeld zeigt die Seite eine dieser Zeilen:

| Was Sie sehen | Was Sie tun |
|---|---|
| **GeoIP database is ready.** | Nichts. Die Ländererkennung arbeitet. |
| **Country lookup needs PHP 7.2 or newer. The rest of the module keeps working.** | Sperren arbeiten weiter. Länderstatistik und Ländersperre bleiben aus, bis PHP 7.2 oder neuer ist. |
| **Upload GeoLite2-Country.mmdb to enable country statistics and country blocks. MaxMind distributes that file.** | Laden Sie die Datei hoch und klicken Sie auf **Save**. |

Eine falsche Datei zeigt **Upload a GeoLite2 Country file that ends with .mmdb.** Lässt sich die Datei nicht speichern, sehen Sie **The GeoIP database could not be saved.** Ein gelungener Upload zeigt **The GeoIP database was uploaded.**

### 3.6 Tools

![Tools](https://mypresta.eu/docs/images/docs/banippro-configure-tools.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt dieser Teil **Tools**.

**Import rules** erzeugt Sperren. Der Bereich ist **Default scope of new bans**. Jede neue Zeile ist aktiv, dauerhaft und hat den Grund **Manual**, außer die Zeile sagt etwas anderes.

| Feld | Am Start | Wirkung |
|---|---|---|
| **Addresses** | leer, mit einem Beispiel im Platzhalter | Eine Adresse pro Zeile. Eine CSV-Zeile kann Adresse, Kommentar, Grund sein. Zeilen, die mit `#` beginnen, werden übergangen. Eine Adresse, die schon existiert, wird ebenfalls übergangen. |
| **File** | leer | Eine Textdatei. Ihre Zeilen kommen zum Feld darüber. Eine Datei größer als 2 MB zeigt **The import file is larger than 2 MB.** und es wird nichts importiert. |
| **Import** | eine Schaltfläche | Legt die Sperren an und zeigt **%d rules were imported.** Übersprungene Zeilen zeigen außerdem **%d lines were skipped.** Der Import stoppt nach 5000 Zeilen. |
| **Export rules CSV** | eine Schaltfläche | Lädt `banippro-rules.csv` für jede Regel. Die Liste bleibt unverändert. |

**Web server snippet** zeigt zwei Felder, Apache 2.4 und nginx. Die Überschrift nennt, wie viele Adressen exportiert wurden. Nur aktive, dauerhafte Sperren, die eine einzelne IP oder ein Netz sind, kommen hinein. Ein Muster wie `192.168.1.*` wird als Netz geschrieben. Bereiche und befristete Sperren bleiben draußen. **Copy** kopiert das Feld. Das Modul bearbeitet Ihre Serverdateien nicht. Den Text fügen Sie selbst in die Serverkonfiguration ein. Gibt es nichts zu exportieren, sagen beide Felder das.

**Emergency unlock** zeigt eine Adresse. Öffnen Sie sie in einem Browser, der ausgesperrt ist. Das Modul setzt die IP dieses Browsers auf die Freigabeliste, für Shop und Backoffice, und lässt diesen Aufruf durch.

| Schaltfläche | Wirkung |
|---|---|
| **Copy** | Kopiert die Entsperradresse. Der Schlüssel bleibt derselbe. |
| **Create a new key** | Ersetzt den Schlüssel. Die Seite sagt **A new emergency key was created. The previous unlock link no longer works.** |
| **Rebuild cache** | Schreibt den Regel-Cache aus der aktuellen Liste neu. Die Seite sagt **The rule cache was rebuilt.** |

Bewahren Sie die Entsperradresse außerhalb des Shops auf. Wer sie öffnet, kommt auf die Freigabeliste.

### 3.7 Updates

![Updates](https://mypresta.eu/docs/images/docs/banippro-configure-updates.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt dieser Teil **Updates**.

| Feld | Am Start | Wirkung |
|---|---|---|
| **Check now** | eine Schaltfläche | Fragt MyPresta, ob eine neuere Version existiert. **New version available!** oder **Module is up to date!** Der Shop ruft das nie auf. |
| **Updates notifications** | **Disable** | **Enable** macht dieselbe Prüfung, wenn Sie diesen Reiter öffnen, höchstens einmal alle drei Tage. Eine neuere Version zeigt auch einen Hinweis auf der Modulseite: **New version available, check MyPresta.eu for more informations**, mit **More details in changelog**. |
| **Save** | eine Schaltfläche | Speichert **Enable** oder **Disable**. Es lädt keine Datei. Die Seite sagt **Settings updated**. |

Der Link unter dem Formular öffnet die Modulseite auf mypresta.eu, wo das Changelog steht. Diese Anleitung listet keine Versionen.

### 3.8 Ban IP, die Regelliste

![Ban IP, die Regelliste](https://mypresta.eu/docs/images/docs/banippro-rules-list.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt dieser Teil **Ban IP, die Regelliste**.

Öffnen Sie **Erweiterte Parameter**, **Ban IP**, oder **Manage rules** auf **Dashboard**. Die Zeile über der Liste sagt, dass Dashboard, Statistik und Automation auf der Konfigurationsseite des Moduls liegen, und bietet **Open dashboard**.

**Add new** öffnet eine leere Regel. Bei einer neuen Regel können Sie mehrere Adressen einfügen, eine pro Zeile. Sie teilen Kommentar, Grund, Regeltyp, Bereich, Ablauf, Aktiv-Schalter und Shop.

Die Spalten sind **ID**, **IP address**, **Match**, **Rule**, **Scope**, **Hits**, **Last hit**, **Expires**, **Reason** und **Active**. Nutzt der Shop mehr als einen Shop, kommt **Shop** dazu.

| Spalte | Was Sie sehen |
|---|---|
| **Match** | **Exact**, **Wildcard**, **CIDR** oder **Range**. |
| **Rule** | **Ban** oder **Allow**. |
| **Scope** | **Front office**, **Back office** oder **Front office and back office**. |
| **Hits** | Wie viele gesperrte Aufrufe zu dieser Regel gespeichert wurden. |
| **Last hit** | Datum des letzten. |
| **Expires** | Datum und Uhrzeit oder **Permanent**. |
| **Reason** | **Manual**, **Fraud**, **Spam**, **Scanner**, **Chargeback**, **Competitor**, **Auto ban (login)**, **Auto ban (probe)**, **Auto ban (rate limit)** oder **Country**. |
| **Active** | Das Statussymbol. Ein Klick schaltet die Zeile an oder aus. Eine inaktive Regel bleibt auf der Liste und trifft niemanden. |
| **Shop** | **All shops** oder ein Shopname. Nur sichtbar, wenn Multishop an ist. |

Die Filterzeile dient der Suche. Filtern sperrt niemanden und lässt niemanden durch.

Zeilenaktionen:

| Aktion | Wirkung |
|---|---|
| **Edit** | Öffnet die Regel. In einer bestehenden Zeile lässt sich nur eine Adresse speichern. |
| **Whitelist** | Sichtbar bei einer Sperre. Macht aus dieser Zeile **Allow** und baut den Cache neu. Verborgen bei einer Zeile, die schon **Allow** ist. |
| **Delete** | Entfernt die Zeile und baut den Cache neu. |

Sammelaktionen, nachdem Sie Zeilen angehakt haben:

| Aktion | Wirkung |
|---|---|
| **Enable selection** | Schaltet die angehakten Zeilen an und baut den Cache neu. |
| **Disable selection** | Schaltet die angehakten Zeilen aus und baut den Cache neu. Sie bleiben auf der Liste. |
| **Delete selected** | Fragt **Delete selected items?** und entfernt dann die angehakten Zeilen und baut den Cache neu. |

Eine Allow-Regel wird vor Sperren geprüft. Eine passende Allow-Regel lässt den Besucher durch, auch wenn eine Sperre ebenfalls passen würde.

Eine Regel, deren Endzeit vorbei ist, passt sofort nicht mehr. Beim ersten Aufruf des nächsten Tages wird sie außerdem auf inaktiv gestellt.

### 3.9 Das Regelformular

![Das Regelformular](https://mypresta.eu/docs/images/docs/banippro-rule-form.webp)

Der Bildschirm ist auf Englisch. In dieser Anleitung heißt dieser Teil **Das Regelformular**.

**Save** schreibt die Regel, baut den Cache neu und kehrt zur Liste zurück, wenn jede Zeile gültig ist.

| Feld | Am Start | Wirkung |
|---|---|---|
| **IP address** | leer | Bei einer neuen Regel eine Adresse pro Zeile. Bei einer Bearbeitung eine Adresse. Eine einzelne IP, ein Muster wie `192.168.1.*`, ein Netz wie `10.0.0.0/8` oder ein Bereich wie `192.168.1.10-192.168.1.20`. Muster sind IPv4, und die Sterne müssen am Ende stehen. IPv6 gilt für eine einzelne Adresse, ein Netz und einen Bereich. |
| **Comment** | leer | Eine private Notiz, die nur Sie in dieser Liste sehen. Besucher sehen sie nie. |
| **Reason** | **Manual** | Warum diese Adresse auf der Liste steht. Die Statistik trennt damit eine manuelle Sperre von einer automatischen. Die automatischen Gründe stehen nicht in dieser Auswahlliste. Das Modul schreibt sie selbst. |
| **Rule** | **Ban** | **Ban** sperrt die Adresse. **Allow** lässt sie immer durch, auch wenn eine andere Regel sie sperren würde. |
| **Scope** | der Wert von **Default scope of new bans** | **Front office** ist das, was Kunden sehen. **Back office** ist dieses Backoffice. **Front office and back office** heißt, die Regel gilt im Shop und im Backoffice. |
| **Expires at** | leer | Leer lassen, dann gilt die Regel, bis Sie sie löschen. Oder Datum und Uhrzeit eintragen, zu der sie enden soll, zum Beispiel `2026-12-31 18:00`. Ein ungültiger Wert zeigt **The expiry date is not valid.** |
| **Active** | **Yes** | **No** behält die Regel auf der Liste, sie sperrt aber niemanden und lässt niemanden durch. |
| **I confirm blocking my own IP** | **No** | Die Hilfezeile zeigt Ihre aktuelle IP oder **unknown**. Die Bestätigung ist nötig, wenn eine Sperre diese IP im Backoffice treffen würde. |
| **Shop** | **All shops** | Nur sichtbar, wenn Multishop an ist. **All shops** heißt, die Regel gilt in jedem Shop dieser Installation. Wählen Sie einen Shop, um die Regel darauf zu begrenzen. |
| **Save** | eine Schaltfläche | Speichert die Zeilen. |

Leere Eingabe zeigt **Enter an IP address.** Ein Muster, das jede Adresse treffen würde, etwa `*.*.*.*` oder ein Netz mit Präfix `0`, zeigt **This rule would block every address.** Eine ungültige Adresse zeigt **This IP address or range is not valid.** Eine zweite aktive Regel mit derselben Adresse und demselben Ban- oder Allow-Typ zeigt **This rule already exists.** Eine Sperre, die Ihre aktuelle IP im Backoffice trifft, ohne den Bestätigungsschalter, zeigt **This ban matches your current IP in the back office. Confirm it before saving.** Mehr als eine Zeile bei einer Bearbeitung zeigt **Edit one address at a time.** Eine ungültige Zeile bei einer neuen Regel wird übersprungen mit **Line … was skipped:** und dem Grund. Eine doppelte Zeile wird übersprungen mit **Line was skipped because it already exists:** und der Adresse. Wurden manche Zeilen gespeichert und manche nicht, zeigt die Seite außerdem **%d rules were saved.** und bleibt im Formular. Lässt sich die Zeile nicht schreiben, sehen Sie **The rule could not be saved.** Eine fehlende Zeile zeigt **Rule not found.**

## 4. Shop-Frontend

Das Theme druckt keinen Block, kein Abzeichen und kein Widget für dieses Modul. Auf einer normalen Produkt-, Warenkorb- oder Startseite gibt es nichts zu fotografieren.

Ein Besucher, der nicht gesperrt ist, sieht den Shop wie gewohnt. Ein gesperrter Besucher sieht eine schlichte Seite: das Shop-Logo, wenn der Shop eines hat, die Überschrift 403, die **Message for blocked visitors** in der Sprache der Seite und die IP des Besuchers. Die Seite bittet Suchmaschinen, sie nicht zu indexieren. Ist **Redirect blocked visitors** auf **Yes** und ist **Redirect URL** ein gültiger `http`- oder `https`-Link, geht der Besucher auf diese Adresse und sieht die Nachricht nicht.

Dieselbe Sperrseite gilt im Backoffice, wenn **Protect the back office** auf **Yes** steht und die Mitarbeiter-IP dort zu einer Sperre passt und zu keiner Allow-Regel.

Diese Prüfungen laufen nur bei Aufrufen, die PrestaShop erreichen. Dateien, die der Webserver direkt ausliefert, zum Beispiel Bilder, werden nicht geprüft und nicht von **Limit requests per IP** gezählt.

Es gibt keine Kundenseite und kein Formular für einen Einspruch. Der Besucher kommt durch, sieht die Sperrseite oder landet auf der Weiterleitung.

| Was der Besucher sieht | Was Sie tun |
|---|---|
| Den Shop, wie gewohnt | Keine passende Sperre, oder eine Allow-Regel hat gepasst. |
| Die Sperrseite mit Ihrer Nachricht und seiner IP | Eine Sperre hat gepasst, das Land ist gesperrt, ein Prüfpfad wurde geöffnet oder das Anfragelimit wurde überschritten. Die Weiterleitung ist **No**. |
| Eine andere Website, ohne Nachricht | Die Weiterleitung ist **Yes** und die URL ist gültig. |
| Das Backoffice, wie gewohnt | **Protect the back office** ist **No**, oder diese IP steht auf der Freigabeliste. |

## 5. Probleme

**Die Modulseite sagt Ban IP Pro requires PHP 7.1 or newer.**  
Der Server hat PHP älter als 7.1. Die Installation wird abgelehnt und **Konfigurieren** zeigt nur diesen Satz. Stellen Sie den Shop auf PHP 7.1 oder neuer und installieren Sie erneut.

**Konfigurieren sagt The module database could not be updated.**  
Die Tabellen konnten nicht angelegt oder geändert werden. Bitten Sie den Hoster, dem Datenbankbenutzer das Anlegen und Ändern von Tabellen zu erlauben, und öffnen Sie **Konfigurieren** erneut.

**Front hook sagt Missing.**  
Die Prüfung hängt nicht. Installieren Sie das Modul neu, oder schalten Sie es im **Modul-Manager** aus und wieder ein. Bestehende Regeln bleiben.

**Save unter Behavior lehnt Protect the back office ab.**  
Die Seite sagt **Add your current IP to the allow list before you protect the back office.** Klicken Sie auf **Dashboard** auf **Add to allow list**, stellen Sie den Schalter dann auf **Yes** und speichern Sie erneut.

**Sie haben sich aus dem Backoffice ausgesperrt.**  
Öffnen Sie die Notadresse aus **Tools**, **Emergency unlock**, in einem Browser, der den Shop noch erreicht. Die IP dieses Browsers kommt auf die Freigabeliste, und der Aufruf wird durchgelassen. Können Sie **Tools** nicht öffnen, nutzen Sie eine früher gespeicherte Kopie der Adresse. **Create a new key** macht die alte Adresse unbrauchbar, aktualisieren Sie Ihre Kopie danach.

**Eine Sperre Ihrer eigenen IP wird abgelehnt.**  
Die Seite sagt **This ban matches your current IP in the back office. Confirm it before saving.** Schalten Sie **I confirm blocking my own IP** ein, oder stellen Sie den Bereich auf **Front office**, wenn Sie diese IP nur im Shop sperren wollen.

**Der Import sagt The import file is larger than 2 MB.**  
Teilen Sie die Datei. Jeder Import stoppt nach 5000 Zeilen und zeigt dann, dass der Import gestoppt hat. Den Rest laden Sie in einem weiteren Import. Übersprungene Zeilen zeigen **%d lines were skipped.** Bestehende Adressen werden absichtlich übersprungen.

**Die Adresse wurde gespeichert, der Shop lässt sie aber durch.**  
Prüfen Sie **Active**, **Scope** und **Expires at**. Eine Regel für das Backoffice trifft den Shop nicht. Eine Allow-Regel für diese IP gewinnt. Nutzen Sie auf **Dashboard** **Test an address**. Klicken Sie danach auf **Rebuild cache** unter **Tools**.

**Backoffice-Sperren tun nichts.**  
**Test an address** ergänzt **Back office protection is disabled, so back-office bans are not enforced.** Schalten Sie **Protect the back office** unter **Behavior** ein, nachdem Ihre IP auf der Freigabeliste steht.

**Die Ländersperre tut nichts.**  
**Block selected countries** muss **Yes** sein, die Codes müssen zwei Buchstaben haben, und die Seite muss **GeoIP database is ready.** sagen. Unter PHP älter als 7.2 sagt die Seite, dass die Ländererkennung PHP 7.2 oder neuer braucht. Tragen Sie Ihr eigenes Land nicht ein.

**Kunden werden während eines normalen Verkaufs gesperrt.**  
**Limit requests per IP** ist an und das Limit ist für diesen Shop zu niedrig. Stellen Sie es auf **No** oder erhöhen Sie **Requests allowed in the window**. Löschen Sie die automatischen Sperren unter **Ban IP**. Ihr Grund ist **Auto ban (rate limit)**.

**Ein fehlgeschlagenes Mitarbeiter-Login hat das Backoffice nicht gesperrt.**  
Diese automatische Sperre gilt für den Shop. Das Backoffice wird nur gesperrt, wenn **Protect the back office** auf **Yes** steht und eine Sperre, deren Bereich das Backoffice einschließt, diese IP trifft.

**Die Alarm-E-Mail kommt nie an.**  
**Email me when an automatic ban is created** muss **Yes** sein. Manuelle Sperren senden keine Mail. Eine zweite automatische Sperre in derselben Stunde sendet keine weitere Mail. Das Postfach ist **Alert email**, oder die Shop-E-Mail, wenn das Feld leer ist. Der Shop muss bereits Mail senden können.

**Das Diagramm zeigt alte Tage, nachdem Sie das Protokoll gekürzt haben.**  
**Keep logs for days** entfernt das zeilenweise Protokoll und die Mitarbeiteraktionen. Die Tagessummen für das Dashboard-Diagramm bleiben.

**New version available, check MyPresta.eu for more informations.**  
Öffnen Sie **Updates** und nutzen Sie den Link, oder klicken Sie auf **Check now**. Diese Anleitung listet die Änderungen nicht.

## 6. Für Entwickler

### 6.1 Überblick

Technischer Name `banippro`, Version 2.0.0, Klasse `banippro`, Anzeigename **Ban IP pro**, Autor MyPresta.eu, Reiter `administration`. Produktseite: `https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html`.

`actionDispatcherBefore` ruft `BanIpGuard::protect()`. Der Guard ermittelt die IP, wendet die Notentsperrung an und danach `BanIpMatcher::decide()` auf den Cache aus `cache/rules.php`. Allow gewinnt gegen Ban. Ländersperre, Prüfpfad-Sperre und Anfragelimit laufen im Shop. Eine Sperre schreibt einen Hit und leitet entweder weiter oder rendert `blocked.tpl` mit Status 403 und beendet den Aufruf. `actionDispatcherAfter` ruft `BanIpAutoBan::evaluate()` für ein zuvor scharf geschaltetes Login. Einstellungen sind globale Konfigurationswerte, gelesen über `BanIpInstaller`. Der Menü-Controller `AdminBanIpPro` bearbeitet die Tabelle `ban`.

Es gibt kein überschriebenes `enable()` oder `disable()`. Das Abschalten durch PrestaShop hängt die Hooks ab, der Guard läuft dann nicht. Die Daten bleiben.

### 6.2 Dateien

| Datei | Aufgabe |
|---|---|
| `banippro.php` | Installation, Hooks, Konfigurationsreiter, Schnellsperre, Import, Test. |
| `controllers/admin/AdminBanIpProController.php` | Regelliste, Formular, CSV-Export, Whitelist-Zeilenaktion. |
| `models/banip.php` | Objektmodell für `ban`, dazu `storeRule()` und `importLines()`. |
| `classes/BanIpGuard.php` | Aufrufprüfung, Sperrseite, tägliche Wartung. |
| `classes/BanIpMatcher.php` | Parsen von exact, wildcard, CIDR und range. Entscheidung Allow, dann Ban. |
| `classes/BanIpClientIp.php` | Remote-Adresse, Cloudflare, vertrauenswürdige Proxys. |
| `classes/BanIpCache.php` | Baut `cache/rules.php` und bindet sie ein. |
| `classes/BanIpAutoBan.php` | Prüfpfad, fehlgeschlagenes Login, Limit, Alarm-Mail. |
| `classes/BanIpStats.php` | Dashboard, Bericht, CSV, Server-Snippets. |
| `classes/BanIpGeo.php` | Liest `geo/GeoLite2-Country.mmdb` ohne die MaxMind-Bibliothek. |
| `classes/BanIpInstaller.php` | Tabellen und Standardkonfiguration. |
| `classes/BanIpUpdate.php` | Versionsprüfung gegen `dev.mypresta.eu`. |
| `views/templates/admin/*.tpl` | Dashboard, Statistik, Tools, Hülle. |
| `views/templates/front/blocked.tpl` | Sperrseite. |
| `views/js/dashboard.js` | Diagramme und Kopierschaltflächen. |
| `mails/en/banippro_alert.txt`, `mails/pl/banippro_alert.txt` | Alarmtexte. Der Betreff steht fest in `BanIpAutoBan::alert()`. |
| `upgrade/upgrade-2.0.0.php` | Ruft `BanIpInstaller::upgrade()`, tauscht alte Hooks gegen den Satz 2.0.0 und baut den Cache neu. |
| `lib/searchTool/` | Wird auf der Konfigurationsseite geladen. Kein Konfigurationsfeld ruft es auf. |
| `tests/matcher_test.php` | CLI-Prüfungen des Matchers. |

### 6.3 Controller

`AdminBanIpPro` erweitert `ModuleAdminController`. Der Elternreiter ist `AdminAdvancedParameters`. Klassenname `AdminBanIpPro`. Tabelle `ban`, Bezeichner `id_ban`, Objekt `banip`.

Listenfilter nutzen die üblichen Helper-Namen (`banFilter_ip` und die übrigen Listenfelder). Zeilenaktionen: Bearbeiten, `displayWhitelistLink` (`banippro_whitelist`), Löschen. Sammelaktionen: delete, enable, disable. `exportHits` streamt die Hit-CSV. `exportRules` streamt die Regel-CSV.

Es gibt keinen Front-Controller. Die Sperrantwort wird im Dispatcher-Hook gerendert und der Aufruf endet.

`?banippro_unlock=` liest `BanIpGuard::tryUnlock()`. Der Wert muss `banippro_emergency_key` mit `hash_equals` entsprechen. Ein Treffer ruft `BanIpAutoBan::ensureAllow()` mit Bereich Shop und Backoffice (`apply_to` 3, `id_shop` 0) und schreibt den Audit `unlock`.

### 6.4 Hooks

Bei der Installation registriert:

| Hook | Aufruf |
|---|---|
| `actionDispatcherBefore` | `BanIpGuard::protect()`. |
| `actionDispatcherAfter` | `BanIpAutoBan::evaluate()`. Auch nach der Hauptprüfung der Installation registriert. |
| `actionFrontControllerSetMedia` | `BanIpAutoBan::arm('customer')`. |
| `actionAuthentication` | `BanIpAutoBan::markSuccess('customer')`. |
| `actionAdminControllerInitAfter` | `BanIpAutoBan::arm('employee')`. |

`upgrade-2.0.0.php` hängt `header`, `displayHeader`, `home`, `displayHome`, `actionFrontControllerAfterInit` und `actionAdminControllerSetMedia` ab.

Das Modul stellt keinen eigenen Hook bereit. Das Scharfschalten des Logins sucht `submitLogin` im Aufruf. Ein erfolgreicher Kundenlogin löscht den Fehlerzähler des Kunden. Erfolg eines Mitarbeiters wird erkannt, wenn der Mitarbeiter in `evaluate()` angemeldet ist.

### 6.5 Overrides

Das Modul überschreibt keine PrestaShop-Klasse und keinen Controller.

### 6.6 Datenbank

Die Deinstallation löscht diese Tabellen nicht und löscht die Konfigurationsschlüssel nicht. `BanIpInstaller::ensure()` ergänzt fehlende Spalten in `{prefix}ban`, wenn **Konfigurieren** geöffnet wird, eine ältere Tabelle `ban` bleibt also und wird erweitert. Eine erneute Installation löscht keine Zeilen.

| Tabelle | Inhalt |
|---|---|
| `{prefix}ban` | `id_ban`, `ip`, `ip_end`, `match_type` (`exact`, `wildcard`, `cidr`, `range`), `rule_type` (1 ban, 2 allow), `apply_to` (1 Shop, 2 Backoffice, 3 beides), `views`, `comment`, `reason`, `active`, `date_add`, `date_upd`, `date_end`, `last_hit`, `id_employee`, `id_shop` (0 heißt alle Shops), `range_start`, `range_end`. |
| `{prefix}banippro_hit` | Eine Zeile pro Sperre: `id_ban`, `ip`, `request_uri`, `user_agent`, `country_iso`, `id_shop`, `date_add`. |
| `{prefix}banippro_daily` | `day`, `id_shop`, `blocked`, `auto_banned`. Wird beim Kürzen der Protokolle nicht gelöscht. |
| `{prefix}banippro_fail` | `ip`, `context` (`customer`, `employee`, `rate`), `hits`, `window_start`. |
| `{prefix}banippro_audit` | `id_employee`, `action`, `details`, `date_add`. |

`BanIpGuard::dailyMaintenance()` läuft einmal pro Kalendertag. Es setzt `active` auf 0 bei Regeln, deren `date_end` in der Vergangenheit liegt, baut den Cache neu, wenn sich eine Zeile geändert hat, und löscht Hit- und Audit-Zeilen, die älter sind als `banippro_log_days`.

### 6.7 Schlüssel und Übersetzungen

Alle Schlüssel sind global (`id_shop` 0). Fehlt ein Schlüssel, gilt der Standard in Klammern.

| Schlüssel | Standard |
|---|---|
| `banippro_emergency_key` | 32 Hex-Zeichen aus `random_bytes`, oder OpenSSL, oder `md5` |
| `banippro_msg` | Pro Sprache. `en` You are blocked. `pl` Dostęp został zablokowany. `es` El acceso ha sido bloqueado. `pt` und `br` O acesso foi bloqueado. Andere Sprachen bekommen den englischen Satz. HTML ist in der Speicherung erlaubt. |
| `banippro_redirect` | 0 |
| `banippro_url` | leer |
| `banippro_default_apply` | 1 |
| `banippro_protect_admin` | 0 |
| `banippro_honeypot` | 1 |
| `banippro_honeypot_hours` | 24 |
| `banippro_honeypot_paths` | `BanIpInstaller::defaultHoneypotPaths()` |
| `banippro_autoban_customer` | 0 |
| `banippro_autoban_employee` | 0 |
| `banippro_autoban_threshold` | 5 |
| `banippro_autoban_window` | 15 |
| `banippro_autoban_hours` | 24 |
| `banippro_ratelimit` | 0 |
| `banippro_ratelimit_max` | 120 |
| `banippro_ratelimit_window` | 1 |
| `banippro_ratelimit_ban_minutes` | 15 |
| `banippro_alert` | 0 |
| `banippro_alert_email` | leer |
| `banippro_alert_last` | Unix-Zeit der letzten Alarm-Mail, geschrieben beim Senden |
| `banippro_cloudflare` | 0 |
| `banippro_trusted_proxies` | leer |
| `banippro_countries_enabled` | 0 |
| `banippro_countries` | leer |
| `banippro_log_days` | 90 |
| `banippro_last_maintenance` | `Y-m-d` der letzten täglichen Wartung |
| `mypresta_updates` | wird nicht gesetzt; das Formular behandelt einen fehlenden Wert als 0 |
| `update_banippro` | 0, danach die Unix-Zeit der letzten Update-Prüfung |
| `updatev_banippro` | entfernte Versionszeichenkette der letzten Prüfung |

`BanIpInstaller::seedConfig()` kopiert ein altes, shopbezogenes `banippro_redirect` und `banippro_url` in die globalen Schlüssel, wenn der globale Wert leer ist. Ein nicht leeres altes `banippro_msg` wird in jede Sprache kopiert, bevor die Standardsätze gelten.

Backoffice-Texte laufen über `$this->l()` / `$this->module->l()`. Übersetzungsdateien liegen in `translations/{iso}.php`. Die Nachricht der Sperrseite ist der Konfigurationswert, kein Übersetzungsschlüssel. Der Mail-Betreff `Ban IP Pro alert` ist ein Literal in `BanIpAutoBan::alert()`. Die Feldhilfen sind das `desc` an jedem HelperForm-Input in `banippro.php` und `AdminBanIpProController.php`.

Automatische `reason`-Werte, die das Modul schreibt, sind `auto-login`, `auto-honeypot` und `auto-rate`. Ländersperren protokollieren `country` und fügen keine `ban`-Zeile ein. `banip::importLines()` stoppt nach 5000 nicht leeren Zeilen, die kein Kommentar sind. Uploads über 2097152 Bytes werden abgelehnt. `BanIpMatcher` lehnt einen leeren Wert, ein Netz `/0` und einen Wildcard aus vier Sternen ab (`too_broad`). Ein Duplikat ist eine aktive Zeile mit derselben gespeicherten IP und demselben `rule_type`.

`BanIpAutoBan::ensureBan()` speichert immer `apply_to` 1 und `id_shop` 0. `ensureAllow()` speichert `apply_to` 3 und `id_shop` 0.

### 6.8 Erweitern

Das Theme kann `views/templates/front/blocked.tpl` überschreiben. Das Modul ruft `$module->fetch('blocked.tpl')`. Zugewiesene Variablen sind `banippro_message`, `banippro_shop`, `banippro_logo`, `banippro_year`, `banippro_ip` und `banippro_lang`. Schlägt der Fetch fehl, druckt der Guard eine minimale HTML-Seite mit derselben Nachricht und beendet trotzdem mit Status 403.

Es wird kein Produkt-, Warenkorb- oder Startseiten-Template gerendert. Es gibt keinen Hook, über den ein Theme ein Shop-Widget ergänzen könnte. Admin-Templates liegen unter `views/templates/admin/` und gehören nicht zum Theme.

## 7. Hilfe

Modulseite: [Ban IP pro](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html).

Melden Sie sich mit Ihrem Kundenkonto auf [mypresta.eu](https://mypresta.eu) an, öffnen Sie das Kontaktformular und wählen Sie **Support for paid modules**. Das Formular sagt, dass für dieses Thema eine Anmeldung nötig ist. Nach der Anmeldung wählen Sie dieses Modul aus der Kaufhistorie.

---
title: "Kumulative Rabatte – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Kumulative Rabatte“ von MyPresta.eu."
sidebar:
  label: "Kumulative Rabatte – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Cumulative discounts auf MyPresta.eu kaufen](https://mypresta.eu/modules/advertising-and-marketing/cumulative-discounts.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/advertising-marketing/cumulative-discounts/)
>
> ---


# Kumulative Rabatte

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind erforderlich, die typischerweise in den meisten PrestaShop-kompatiblen Hosting-Umgebungen verfügbar sind.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm, auf dem Sie festlegen, wie Ihr kumulatives Rabattprogramm funktioniert.

#### **Programm aktivieren**

- **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um das gesamte kumulative Rabattprogramm ein- oder auszuschalten.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Das Modul verfolgt aktiv die Kundenausgaben, weist Gruppen zu und zeigt Rabattinformationen in Ihrem Front Office an.
  - *Wenn deaktiviert:* Das Modul stellt alle Operationen ein, es werden keine Rabatte angewendet und keine Informationen angezeigt.
- **Empfohlener Wert:** JA (um das Programm zu aktivieren).
- **Händlerszenario / Beispiel:** Wenn Sie das Modul zum ersten Mal einrichten, aktivieren Sie es, nachdem Sie alle anderen Einstellungen konfiguriert haben. Wenn Sie das Programm vorübergehend pausieren müssen (z. B. während eines großen Verkaufs, bei dem andere Rabatte gelten), können Sie es hier deaktivieren.

#### **Kumulative Rabatte für ausgewählte Kundengruppen deaktivieren**

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen die Auswahl spezifischer Kundengruppen, die *nicht* Teil des kumulativen Rabattprogramms sein sollen. Kunden in diesen ausgewählten Gruppen erhalten keine kumulativen Rabatte, unabhängig von ihren Ausgaben.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn eine Gruppe ausgewählt ist:* Kunden, die zu dieser Gruppe gehören, werden vom Programm ausgeschlossen.
  - *Wenn keine Gruppen ausgewählt sind:* Alle Kundengruppen sind standardmäßig für das Programm berechtigt.
- **Empfohlener Wert:** Wählen Sie Gruppen wie „Besucher“ oder „Gäste“, wenn nur registrierte Kunden teilnehmen sollen. Sie könnten auch eine „Großhandels“-Gruppe ausschließen, wenn diese eine separate Preisstruktur hat.
- **Händlerszenario / Beispiel:** Sie haben möglicherweise eine Kundengruppe „Großhandel“, die bereits spezielle Preise erhält. Um Konflikte oder doppelte Rabatte zu vermeiden, würden Sie hier die Gruppe „Großhandel“ auswählen, um sie vom kumulativen Rabattprogramm auszuschließen.

#### **Zeitrahmen**

- **Was diese Einstellung bewirkt:** Definiert den Zeitraum, über den Kundenbestellungen bei der Berechnung ihrer Gesamtausgaben berücksichtigt werden.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Alle Bestellungen:* Berücksichtigt jede jemals vom Kunden getätigte Bestellung.
  - *Bestellungen des letzten Jahres / Bestellungen des letzten halben Jahres / Bestellungen des letzten Quartals / Bestellungen des letzten Monats / Bestellungen der letzten Woche / Bestellungen des letzten Tages:* Begrenzt die Berechnung auf Bestellungen, die innerhalb des angegebenen jüngsten Zeitraums getätigt wurden.
  - *Nur letzte gültige Bestellung:* Berücksichtigt nur die letzte abgeschlossene Bestellung.
- **Empfohlener Wert:** „Bestellungen des letzten Jahres“ oder „Alle Bestellungen“ sind gängige Optionen für Treueprogramme. „Bestellungen des letzten Monats“ könnte für einen aggressiveren, kurzfristigen Treue-Push verwendet werden.
- **Händlerszenario / Beispiel:** Wenn Sie langfristige Loyalität belohnen möchten, wählen Sie „Alle Bestellungen“. Wenn Sie aktuelle, häufige Käufe fördern möchten, könnte „Bestellungen des letzten halben Jahres“ passender sein.

#### **Preistyp**

- **Was diese Einstellung bewirkt:** Bestimmt, ob die Berechnung der kumulativen Ausgaben den „Nettopreis“ (Preis vor Steuern) oder den „Bruttopreis“ (Preis inklusive Steuern) der Produkte in Bestellungen verwenden soll.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Nettopreis:* Die Gesamtausgaben werden basierend auf den Produktpreisen ohne Steuern berechnet.
  - *Bruttopreis:* Die Gesamtausgaben werden basierend auf den Produktpreisen inklusive Steuern berechnet.
- **Empfohlener Wert:** „Bruttopreis“ ist für Kunden oft intuitiver, da er widerspiegelt, was sie tatsächlich bezahlt haben. „Nettopreis“ könnte jedoch für B2B-Shops oder zur internen Buchhaltungskonsistenz bevorzugt werden.
- **Händlerszenario / Beispiel:** Wenn Ihre Zielgruppe hauptsächlich Verbraucher sind, ist die Verwendung des „Bruttopreises“ am sinnvollsten, da er mit dem Endpreis übereinstimmt, den sie sehen und bezahlen.

#### **Bestellstatus auswählen**

- **Was diese Einstellung bewirkt:** Ermöglicht Ihnen festzulegen, welche Bestellstatus bei der Berechnung der Gesamtausgaben eines Kunden berücksichtigt werden sollen. Nur Bestellungen mit diesen ausgewählten Status zählen zum kumulativen Gesamtbetrag.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn „Zahlung akzeptiert“ und „Geliefert“ ausgewählt sind:* Nur Bestellungen, die erfolgreich bezahlt und geliefert wurden, tragen zu den Gesamtausgaben des Kunden bei.
  - *Wenn „Storniert“ oder „Erstattet“ NICHT ausgewählt sind:* Diese Bestellungen zählen nicht, wodurch verhindert wird, dass Kunden Treuepunkte für nicht abgeschlossene Käufe erhalten.
- **Empfohlener Wert:** Wählen Sie Status, die eine abgeschlossene und erfolgreiche Transaktion anzeigen, wie „Zahlung akzeptiert“, „Geliefert“. Schließen Sie Status wie „Storniert“, „Erstattet“, „Zahlungsfehler“ usw. aus.
- **Händlerszenario / Beispiel:** Sie möchten sicherstellen, dass nur tatsächliche, abgeschlossene Käufe zur Loyalität beitragen. Sie würden „Zahlung akzeptiert“ und „Geliefert“ auswählen, um sicherzustellen, dass Kunden nur Rabatte für Bestellungen erhalten, die sie tatsächlich bezahlt und erhalten haben.

#### **Bestellungen mit Gutscheincode ausschließen**

- **Was diese Einstellung bewirkt:** Wenn aktiviert, zählen Bestellungen, bei denen ein Gutschein- oder Couponcode verwendet wurde, nicht zu den kumulativen Gesamtausgaben des Kunden.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Bestellungen mit Gutscheinen werden für Loyalitätsberechnungen ignoriert.
  - *Wenn deaktiviert:* Bestellungen mit Gutscheinen zählen *zum* kumulativen Gesamtbetrag.
- **Empfohlener Wert:** JA, wenn Sie Käufe zum vollen Preis stärker belohnen möchten. NEIN, wenn Sie jeden Kauf, auch reduzierte, zur Loyalität beitragen lassen möchten.
- **Händlerszenario / Beispiel:** Sie führen eine Sonderaktion mit einem 20 % Rabattgutschein durch. Wenn Sie diese Einstellung aktivieren, zählen Kunden, die diesen Gutschein verwenden, diese Bestellung nicht zu ihrem kumulativen Rabattfortschritt, wodurch sichergestellt wird, dass sie Loyalität für Käufe zum vollen Preis erhalten.

#### **Produkte mit spezifischen Preisen ausschließen**

- **Was diese Einstellung bewirkt:** Wenn aktiviert, tragen Produkte, die einen „spezifischen Preis“ haben (z. B. einen speziellen Aktionspreis für eine begrenzte Zeit oder eine bestimmte Kundengruppe), nicht zur Berechnung der kumulativen Ausgaben bei.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Produkte mit spezifischen Preisen werden für Loyalitätsberechnungen ignoriert.
  - *Wenn deaktiviert:* Produkte mit spezifischen Preisen zählen *zum* kumulativen Gesamtbetrag.
- **Empfohlener Wert:** JA, wenn Sie Käufe von regulär bepreisten Artikeln belohnen möchten. NEIN, wenn Sie möchten, dass alle Produktkäufe beitragen.
- **Händlerszenario / Beispiel:** Sie haben einen Flash-Sale für bestimmte Artikel unter Verwendung der PrestaShop-Funktion für spezifische Preise. Wenn Sie dies aktivieren, hilft der Kauf dieser Sale-Artikel dem Kunden nicht, die nächste Loyalitätsstufe zu erreichen, was ihn stattdessen zum Kauf regulär bepreister Artikel ermutigt.

#### **Produkte mit Mengenrabatten ausschließen**

- **Was diese Einstellung bewirkt:** Wenn aktiviert, tragen Produkte, die mit einem Mengenrabatt gekauft wurden (z. B. „Kaufe 3, erhalte 10 % Rabatt“), nicht zur Berechnung der kumulativen Ausgaben bei.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert:* Produkte, die mit Mengenrabatten gekauft wurden, werden für Loyalitätsberechnungen ignoriert.
  - *Wenn deaktiviert:* Produkte, die mit Mengenrabatten gekauft wurden, zählen *zum* kumulativen Gesamtbetrag.
- **Empfohlener Wert:** JA, wenn Sie Käufe einzelner Artikel zum vollen Preis belohnen möchten. NEIN, wenn Sie Großeinkäufe zur Loyalität beitragen lassen möchten.
- **Händlerszenario / Beispiel:** Sie bieten ein „Kaufe 5, erhalte 15 % Rabatt“-Angebot an. Wenn Sie dies aktivieren, zählen Kunden, die dieses Angebot nutzen, diese spezifischen Artikel nicht zu ihrem kumulativen Rabattfortschritt.

#### **Standard-Kundengruppe**

- **Was diese Einstellung bewirkt:** Dies definiert die Standard-Kundengruppe, der Kunden zugewiesen werden, wenn sie die Ausgabenkriterien für keine andere kumulative Rabattgruppe erfüllen. Dies ist typischerweise Ihre Standard-„Kunden“-Gruppe.
- **Auswirkung der Änderung dieser Einstellung:** Stellt sicher, dass Kunden immer einer gültigen Gruppe angehören, auch wenn sie nicht genug ausgegeben haben, um sich für eine spezielle Rabattstufe zu qualifizieren.
- **Empfohlener Wert:** Ihre Standard-„Kunden“-Gruppe (oft ID 3).
- **Händlerszenario / Beispiel:** Ein neuer Kunde registriert sich. Er hat noch keine Käufe getätigt, daher weist das Modul ihn der „Standard-Kundengruppe“ (z. B. „Kunde“) zu, die möglicherweise 0 % Rabatt hat. Wenn er ausgibt, wird er in „Bronze“, „Silber“ usw. verschoben.

#### **Informationen für eingeloggte Kunden (Produktseite)**

- **Was diese Einstellung bewirkt:** Dies ist ein Texteditor, in dem Sie die Nachricht anpassen können, die *eingeloggten Kunden* auf Produktseiten angezeigt wird. Diese Nachricht informiert sie typischerweise über ihren aktuellen Rabattstatus oder Fortschritt.
- **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Text wird auf Produktseiten für Kunden angezeigt, die in ihrem Konto angemeldet sind. Sie können Smarty-Variablen (wie `{$total_spent}`, `{$discount_value}`, `{$next_group_name}`, `{$next_group_value}`) verwenden, um die Nachricht zu personalisieren.
- **Empfohlener Wert:** Eine einladende Nachricht wie: „Hallo {$customer\_name}! Sie gehören derzeit zur Gruppe {$current\_group\_name} und erhalten einen Rabatt von {$discount\_value}%. Geben Sie {$to\_next\_group} mehr aus, um die Gruppe {$next\_group\_name} zu erreichen und {$next\_group\_value}% Rabatt zu erhalten!“
- **Händlerszenario / Beispiel:** Sie möchten eingeloggte Kunden motivieren. Sie können ihnen genau sagen, wie viel mehr sie ausgeben müssen, um einen höheren Rabatt zu erhalten, was einen klaren Anreiz schafft.

#### **Informationen für nicht eingeloggte Kunden (Produktseite)**

- **Was diese Einstellung bewirkt:** Dies ist ein Texteditor, in dem Sie die Nachricht anpassen können, die *Gästen oder nicht eingeloggten Kunden* auf Produktseiten angezeigt wird. Diese Nachricht ermutigt sie typischerweise, sich zu registrieren und am Treueprogramm teilzunehmen.
- **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Text wird auf Produktseiten für Kunden angezeigt, die nicht in ihrem Konto angemeldet sind.
- **Empfohlener Wert:** Eine einladende Nachricht wie: „Jetzt registrieren und kumulative Rabatte sammeln! Je mehr Sie ausgeben, desto mehr sparen Sie!“
- **Händlerszenario / Beispiel:** Ein neuer Besucher landet auf einer Produktseite. Diese Nachricht kann ihn dazu verleiten, ein Konto zu erstellen, indem sie die Vorteile Ihres Treueprogramms hervorhebt und ihn möglicherweise in einen registrierten Kunden umwandelt.

#### **Informationen für eingeloggte Kunden (Warenkorbseite)**

- **Was diese Einstellung bewirkt:** Dies ist ein Texteditor, in dem Sie die Nachricht anpassen können, die *eingeloggten Kunden* auf der Warenkorbseite angezeigt wird. Diese Nachricht kann ihren Rabattstatus verstärken oder zeigen, wie ihr aktueller Warenkorb zu ihrer Loyalität beiträgt.
- **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Text wird auf der Warenkorbseite für eingeloggte Kunden angezeigt. Sie können Smarty-Variablen verwenden.
- **Empfohlener Wert:** Ähnlich der Nachricht auf der Produktseite, aber vielleicht mit Betonung des Beitrags des aktuellen Warenkorbs: „Ihr aktueller Warenkorbwert beträgt {$cart\_value}. Mit Ihrem {$current\_group\_name}-Rabatt sparen Sie {$discount\_value}%! Geben Sie {$to\_next\_group} mehr aus, um die Gruppe {$next\_group\_name} zu erreichen!“
- **Händlerszenario / Beispiel:** Ein Kunde ist kurz davor, zur Kasse zu gehen. Diese Nachricht erinnert ihn an seine Treuevorteile und könnte ihn sogar ermutigen, einen kleinen Artikel hinzuzufügen, um die nächste Rabattstufe zu erreichen.

#### **Informationen für nicht eingeloggte Kunden (Warenkorbseite)**

- **Was diese Einstellung bewirkt:** Dies ist ein Texteditor, in dem Sie die Nachricht anpassen können, die *Gästen oder nicht eingeloggten Kunden* auf der Warenkorbseite angezeigt wird. Diese Nachricht ermutigt sie, sich vor Abschluss ihres Kaufs zu registrieren, um Loyalität zu sammeln.
- **Auswirkung der Änderung dieser Einstellung:** Der hier eingegebene Text wird auf der Warenkorbseite für nicht eingeloggte Kunden angezeigt.
- **Empfohlener Wert:** „Verpassen Sie keine Treuerabatte! Registrieren Sie sich vor dem Checkout, um Prämien für Ihre Einkäufe zu erhalten!“
- **Händlerszenario / Beispiel:** Ein Gastkunde hat Artikel in seinem Warenkorb. Diese Nachricht gibt einen letzten Anstoß zur Registrierung eines Kontos und verwandelt einen einmaligen Käufer in einen potenziell treuen Kunden.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### AdminCudiListController (Back Office > Kumulative Rabatte > Rabatte verwalten)

- **Bildschirmname & Menüposition:** Sie finden diesen Bildschirm, indem Sie zu **Katalog > Kumulative Rabatte** navigieren (oder einen ähnlichen Ort, abhängig von Ihrer PrestaShop-Version und Menüanpassung). Die genaue Bezeichnung könnte „Rabatte verwalten“ oder „Regeln für kumulative Rabatte“ sein.
- **Verfügbare Aktionen & Einstellungen:** Dieser Bildschirm zeigt ein Raster (Liste) Ihrer definierten Regeln für kumulative Rabatte. Jede Regel spezifiziert:
  - **Mindestausgabenbetrag:** Der Gesamtbetrag, den ein Kunde ausgeben muss, um sich für diese Gruppe zu qualifizieren.
  - **Kundengruppe:** Die PrestaShop-Kundengruppe, der Kunden, die die Ausgabenkriterien erfüllen, zugewiesen werden.
  - **Rabattprozentsatz:** Der Rabattprozentsatz, der mit dieser Kundengruppe verbunden ist.
  - **Aktionen:** Sie können neue Regeln „Hinzufügen“, bestehende Regeln „Bearbeiten“ oder Regeln „Löschen“.
- **Auswirkung von Änderungen:**
  - **Hinzufügen einer neuen Regel:** Erstellt eine neue Stufe in Ihrem Treueprogramm. Zum Beispiel: „Geben Sie 500 $ aus, um der Gold-Gruppe beizutreten und 15 % Rabatt zu erhalten.“
  - **Bearbeiten einer Regel:** Ändert den Ausgabenschwellenwert oder die zugewiesene Gruppe/den Rabatt für eine bestehende Stufe. Änderungen wirken sich auf zukünftige Gruppenzuweisungen und Neuberechnungen aus.
  - **Löschen einer Regel:** Entfernt eine Treuestufe. Kunden, die zuvor in dieser Gruppe waren, werden basierend auf den verbleibenden Regeln neu zugewiesen.
- **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
  1. **Planen Sie Ihre Stufen:** Legen Sie Ihre Ausgabenschwellenwerte und die entsprechenden Rabattgruppen fest (z. B. Bronze: 100 $ für 5 %, Silber: 500 $ für 10 %, Gold: 1000 $ für 15 %).
  2. **Kundengruppen erstellen:** Stellen Sie sicher, dass Sie entsprechende Kundengruppen in PrestaShop (Back Office > Kunden > Gruppen) für jede Stufe haben (z. B. „Bronze-Kunde“, „Silber-Kunde“, „Gold-Kunde“). Weisen Sie jeder dieser Gruppen den entsprechenden globalen Rabattprozentsatz zu.
  3. **Regeln hinzufügen:** Verwenden Sie die Schaltfläche „Neu hinzufügen“, um jede Stufe zu erstellen und den Ausgabenbetrag mit der richtigen Kundengruppe zu verknüpfen.
  4. **Regeln ordnen:** Das Modul verarbeitet Regeln vom niedrigsten zum höchsten Ausgabenbetrag. Stellen Sie sicher, dass Ihre Regeln logisch geordnet sind.
  5. **Überprüfen und anpassen:** Überprüfen Sie regelmäßig Ihre Stufen, um sicherzustellen, dass sie weiterhin effektiv und profitabel sind.

#### index.php (cudi/controllers/admin/index.php)

Diese Datei ist typischerweise ein Platzhalter oder eine Weiterleitung innerhalb der Admin-Controller-Struktur und stellt keinen direkten, konfigurierbaren Bildschirm für den Händler dar. Sie ist Teil der internen Routenführung des Moduls für das Back Office. Alle händlerseitigen Konfigurationen für kumulative Rabatte erfolgen entweder auf der Hauptmodulkonfigurationsseite oder über den `AdminCudiListController`.

### 2.3 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| **Modulkonfigurationsseite** | Programm aktivieren | JA | Hauptschalter für das Treueprogramm. |
|  | Kumulative Rabatte für ausgewählte Kundengruppen deaktivieren | „Gast“, „Besucher“ auswählen | Schließt bestimmte Kundengruppen vom Programm aus. |
|  | Zeitrahmen | Bestellungen des letzten Jahres / Alle Bestellungen | Definiert den Zeitraum für die Berechnung der Gesamtausgaben. |
|  | Preistyp | Bruttopreis | Bestimmt, ob Netto- oder Bruttopreise für die Ausgabenberechnung verwendet werden. |
|  | Bestellstatus auswählen | Zahlung akzeptiert, Geliefert | Legt fest, welche Bestellstatus zu den Gesamtausgaben zählen. |
|  | Bestellungen mit Gutscheincode ausschließen | JA | Verhindert, dass Bestellungen mit Gutscheinen zur Loyalität beitragen. |
|  | Produkte mit spezifischen Preisen ausschließen | JA | Verhindert, dass Produkte mit spezifischen Preisaktionen beitragen. |
|  | Produkte mit Mengenrabatten ausschließen | JA | Verhindert, dass Produkte mit Mengenrabatten beitragen. |
|  | Standard-Kundengruppe | Ihre Standard-„Kunden“-Gruppe | Die Gruppe, die zugewiesen wird, wenn keine Treuestufe erreicht wird. |
|  | Informationen für eingeloggte Kunden (Produktseite) | Anpassbarer Text mit Smarty-Variablen | Nachricht für eingeloggte Benutzer auf Produktseiten. |
|  | Informationen für nicht eingeloggte Kunden (Produktseite) | Anpassbarer Text | Nachricht für Gäste auf Produktseiten, die zur Registrierung anregt. |
|  | Informationen für eingeloggte Kunden (Warenkorbseite) | Anpassbarer Text mit Smarty-Variablen | Nachricht für eingeloggte Benutzer auf Warenkorbseiten. |
|  | Informationen für nicht eingeloggte Kunden (Warenkorbseite) | Anpassbarer Text | Nachricht für Gäste auf Warenkorbseiten, die zur Registrierung anregt. |
| **AdminCudiListController** | Mindestausgabenbetrag | Variiert je nach Stufe | Schwellenwert für die Qualifizierung für eine bestimmte Rabattgruppe. |
|  | Kundengruppe | Ihre benutzerdefinierten Treuegruppen (z. B. Bronze, Silber) | Die PrestaShop-Gruppe, die zugewiesen wird, wenn der Ausgabenschwellenwert erreicht ist. |
|  | Rabattprozentsatz | Variiert je nach Stufe | Der auf die zugewiesene Kundengruppe angewendete Rabatt. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Meine Kunden werden nicht den richtigen Gruppen zugewiesen, oder Rabatte werden nicht angewendet.**
A1:

- **„Programm aktivieren“ prüfen:** Stellen Sie sicher, dass der Hauptschalter in der Modulkonfiguration auf JA steht.
- **„Zeitrahmen“ und „Bestellstatus auswählen“ überprüfen:** Stellen Sie sicher, dass die Bestellungen, die zählen sollen, in den ausgewählten Zeitrahmen fallen und die korrekten Bestellstatus haben (z. B. „Geliefert“, „Zahlung akzeptiert“).
- **„Ausschluss“-Einstellungen überprüfen:** Prüfen Sie, ob „Bestellungen mit Gutscheincode ausschließen“, „Produkte mit spezifischen Preisen ausschließen“ oder „Produkte mit Mengenrabatten ausschließen“ aktiviert sind und möglicherweise verhindern, dass Bestellungen gezählt werden.
- **Cache leeren:** Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“. Manchmal kann der PrestaShop-Cache verhindern, dass Änderungen sofort wirksam werden.
- **Kundengruppen überprüfen:** Stellen Sie sicher, dass die Kundengruppen, die Sie im `AdminCudiListController` verknüpft haben, tatsächlich in PrestaShop existieren (Kunden > Gruppen) und den korrekten globalen Rabattprozentsatz zugewiesen haben.
- **Reihenfolge der Regeln:** Stellen Sie sicher, dass Ihre Regeln im `AdminCudiListController` logisch vom niedrigsten zum höchsten Ausgabenschwellenwert geordnet sind.

**F2: Die Rabattinformationen werden auf meinen Produktseiten oder im Warenkorb nicht angezeigt.**
A2:

- **Modul-Hooks überprüfen:** Stellen Sie sicher, dass das Modul an `displayProductAdditionalInfo` und `displayShoppingCart` gehookt ist. Dies können Sie unter **Design > Positionen** (oder **Module > Positionen** in älteren PS-Versionen) überprüfen. Suchen Sie nach „Kumulative Rabatte“ unter diesen Hooks. Falls nicht, versuchen Sie, das Modul neu zu installieren oder manuell zu hooken.
- **Modulkonfigurationstext:** Stellen Sie sicher, dass Sie Text in die Felder „Informationen für eingeloggte Kunden“ und „Informationen für nicht eingeloggte Kunden“ für Produkt- und Warenkorbseiten eingegeben haben. Wenn diese Felder leer sind, wird nichts angezeigt.
- **Theme-Kompatibilität:** Ihr benutzerdefiniertes Theme könnte die Standard-Hook-Positionen überschreiben. Wenn die Informationen immer noch nicht angezeigt werden, benötigen Sie möglicherweise einen Webentwickler, um die `.tpl`-Dateien Ihres Themes anzupassen, um die Hooks des Moduls explizit einzuschließen.

**F3: Wie übersetze ich die Nachrichten des Moduls in andere Sprachen?**
A3:

- Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
- Wählen Sie „Übersetzungen installierter Module“, wählen Sie Ihr Theme und dann „Kumulative Rabatte“ aus dem Modul-Dropdown.
- Sie können dann alle statischen Zeichenfolgen des Moduls übersetzen. Für die benutzerdefinierten Nachrichten, die Sie in der Konfiguration eingegeben haben (z. B. „Informationen für eingeloggte Kunden“), müssen Sie den Sprachwahlschalter oben rechts auf der Modulkonfigurationsseite verwenden, um die Sprache zu wechseln und den übersetzten Text für jede Sprache einzugeben.

**F4: Kann ich einen Kunden manuell einer kumulativen Rabattgruppe zuweisen?**
A4: Ja, Sie können die Gruppe eines Kunden manuell in seinem Kundenprofil ändern (Back Office > Kunden > Kunden > Kunden bearbeiten). Das Modul wird jedoch seine Gruppe basierend auf seiner Ausgabenhistorie bei der nächsten Bestellstatusaktualisierung oder wenn die Modullogik ausgelöst wird, automatisch neu bewerten. Wenn Sie möchten, dass ein Kunde *dauerhaft* in einer bestimmten Gruppe bleibt, unabhängig von den Ausgaben, müssen Sie diese Gruppe möglicherweise vom kumulativen Rabattprogramm ausschließen (mithilfe der Einstellung „Kumulative Rabatte für ausgewählte Kundengruppen deaktivieren“) und sie manuell verwalten.

**F5: Was passiert, wenn die Gesamtausgaben eines Kunden unter eine Stufe fallen (z. B. aufgrund einer Rückerstattung)?**
A5: Das Modul berechnet die Gesamtausgaben des Kunden basierend auf dem konfigurierten „Zeitrahmen“ und den „ausgewählten Bestellstatus“ neu, wann immer ein Bestellstatus aktualisiert wird. Wenn eine Rückerstattung dazu führt, dass der Gesamtbetrag unter eine Stufe fällt, wird das Modul sie bei der nächsten Neuberechnung automatisch der entsprechenden niedrigeren Stufe zuweisen, um die Genauigkeit zu gewährleisten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

Dieser Abschnitt ist ausschließlich für Entwickler, Shop-Webmaster und technische Agenturen, die den Shop warten oder erweitern.

### 4.1 Architekturübersicht

Das Modul „Kumulative Rabatte“ (`cudi`) folgt einer Standard-PrestaShop-Modularchitektur und nutzt MVC-Prinzipien. Es arbeitet hauptsächlich, indem es sich in verschiedene Front-Office- und Back-Office-Ereignisse einklinkt, um die Kundenausgaben zu berechnen und sie dynamisch den entsprechenden Kundengruppen zuzuweisen. Die Konfiguration wird über die Hauptmethode `getContent()` und einen dedizierten `AdminCudiListController` zur Verwaltung der Rabattstufen verwaltet. Es führt keine benutzerdefinierten Datenbanktabellen ein, sondern stützt sich auf PrestaShops `ps_configuration` für Einstellungen und `ps_customer_group` für Gruppenzuweisungen.

### 4.2 Controller (`controllers/`)

#### Front-Office-Controller

- `cudi/controllers/front/index.php`
  - **Klassenname & Elternklasse:** `CudiIndexModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller dient wahrscheinlich als Standard oder Fallback für die Front-Office-Routung des Moduls. Er könnte die Erstkonfiguration oder Weiterleitung handhaben, obwohl `mydiscount.php` spezifischer für kundenorientierte Inhalte ist.
- `cudi/controllers/front/mydiscount.php`
  - **Klassenname & Elternklasse:** `CudiMydiscountModuleFrontController` erweitert `ModuleFrontController`.
  - **Verantwortlichkeit:** Dieser Controller ist für das Rendern der dedizierten Seite „Meine Rabatte“ im Kundenkontobereich zuständig. Er ruft die Gesamtausgaben des Kunden, die aktuelle Gruppe und den Fortschritt zur nächsten Stufe ab und übergibt diese Daten dann an das Template `myDiscount.tpl` zur Anzeige. Er reagiert auf eine Route wie `ihrshop.com/module/cudi/mydiscount`.

#### Back-Office-Admin-Controller

- `cudi/controllers/admin/AdminCudiList.php`
  - **Tab-Name und verwaltete Entität:** „Kumulative Rabatte“ (oder ähnlich, zugänglich über das Katalogmenü). Verwaltet die `cudi`-Entität, die die Regeln für kumulative Rabatte darstellt (Ausgabenschwellenwerte, die mit Kundengruppen verknüpft sind).
  - **Verantwortlichkeit:** Dies ist der primäre Admin-Controller zur Verwaltung der Rabattstufen. Er erweitert `AdminController` und verwendet `HelperList` für die Rasteranzeige und `HelperForm` zum Hinzufügen/Bearbeiten einzelner Regeln. Er handhabt CRUD-Operationen für die Regeln für kumulative Rabatte, einschließlich der Definition der Mindestausgaben, der Zielkundengruppe und des zugehörigen Rabatts.
- `cudi/controllers/admin/index.php`
  - **Verantwortlichkeit:** Diese Datei dient typischerweise als Einstiegspunkt oder Weiterleitung innerhalb des Admin-Controller-Verzeichnisses. In vielen Modulen könnte sie eine einfache `header('Location: ...')` enthalten, um zum Haupt-Admin-Controller (`AdminCudiList.php` in diesem Fall) weiterzuleiten, oder ein Platzhalter sein. Sie stellt keinen direkten, konfigurierbaren Bildschirm dar.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Moduldossier weist keine benutzerdefinierten Klassen im Verzeichnis `classes/` aus. Die Kernlogik zur Berechnung kumulativer Ausgaben und zur Zuweisung von Gruppen ist wahrscheinlich im Hauptmodul `cudi.php` selbst gekapselt, insbesondere in seinen Hook-Methoden und potenziell Hilfsfunktionen. Es interagiert direkt mit PrestaShops `Customer`, `Order`, `OrderState` und `Group` `ObjectModel`s.

### 4.4 JavaScript-Assets (`views/js/`)

- `cudi/views/admin/js/cudi.js`
  - **Geltungsbereich:** Back-Office.
  - **Verantwortlichkeit:** Dieses Skript verarbeitet wahrscheinlich clientseitige Interaktionen auf der Konfigurationsseite des Moduls oder dem `AdminCudiListController`. Dies könnte Folgendes umfassen:
    - Dynamische Sichtbarkeit von Formularfeldern basierend auf ausgewählten Optionen (z. B. Anzeigen/Ausblenden von Ausschlussoptionen).
    - AJAX-Aufrufe zum Speichern von Einstellungen ohne vollständiges Neuladen der Seite.
    - Eingabevalidierung oder interaktive Elemente, die spezifisch für die Admin-Oberfläche des Moduls sind.
    - Event-Listener für Formularänderungen oder Schaltflächenklicks innerhalb des Admin-Panels.

### 4.5 CSS-Stylesheets (`views/css/`)

- `cudi/views/admin/css/cudi.css`
  - **Geltungsbereich:** Back-Office-Admin-Formular-Styling.
  - **Verantwortlichkeit:** Bietet Styling für die Konfigurationsseite des Moduls und die `AdminCudiListController`-Oberfläche, um die visuelle Integration in das PrestaShop-Back-Office-Theme sicherzustellen.
  - **Wichtige CSS-Klassenselektoren:** Zielt wahrscheinlich auf spezifische IDs oder Klassen innerhalb der Admin-Templates des Moduls ab (z. B. `.cudi-settings-panel`, `.cudi-list-table`).
- `cudi/views/css/cudi.css`
  - **Geltungsbereich:** Front-Office-Kunden-Styling.
  - **Verantwortlichkeit:** Gestaltet die Informationen, die Kunden auf Produktseiten, Warenkorbseiten und der Seite „Meine Rabatte“ angezeigt werden.
  - **Wichtige CSS-Klassenselektoren:** Zielt auf Elemente ab, die von den Front-Office-Templates des Moduls generiert werden (z. B. `.cudi-info-block`, `.cudi-discount-message`, `.cudi-progress-bar`). Entwickler können diese in der `custom.css` ihres Themes oder durch Erstellen eines Child-Themes überschreiben.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

#### Hook-Templates (`views/templates/hook/`)

- `cudi/views/templates/hook/displayProductAdditionalInfo-unlogged.tpl`
  - **Hook:** `displayProductAdditionalInfo` (speziell für nicht eingeloggte Benutzer).
  - **Ausgabe:** Zeigt die anpassbare Nachricht für nicht eingeloggte Kunden auf Produktseiten an, die zur Registrierung anregt und das Treueprogramm hervorhebt.
- `cudi/views/templates/hook/displayProductAdditionalInfo.tpl`
  - **Hook:** `displayProductAdditionalInfo` (für eingeloggte Benutzer).
  - **Ausgabe:** Zeigt die anpassbare Nachricht für eingeloggte Kunden auf Produktseiten an, die ihren aktuellen Rabattstatus und den Fortschritt zur nächsten Stufe zeigt.
- `cudi/views/templates/hook/myAccount.tpl`
  - **Hook:** `displayCustomerAccount`.
  - **Ausgabe:** Rendert einen Link oder Block im Bereich „Mein Konto“ des Kunden, typischerweise mit der Bezeichnung „Meine Rabatte“, der zur dedizierten `mydiscount`-Seite führt.

#### Admin-Templates (`views/templates/admin/`)

- `cudi/views/admin/assignButton.tpl`
  - **Geltungsbereich:** Back-Office.
  - **Ausgabe:** Rendert wahrscheinlich eine Schaltfläche oder einen Aktionslink innerhalb der Admin-Oberfläche, möglicherweise zum Auslösen einer manuellen Neuberechnung oder Zuweisung von Kundengruppen.
- `cudi/views/admin/orderstates.tpl`
  - **Geltungsbereich:** Back-Office.
  - **Ausgabe:** Wird innerhalb des Hauptkonfigurationsformulars des Moduls (`getContent()`) verwendet, um das Mehrfachauswahl-Dropdown oder die Kontrollkästchen für „Bestellstatus auswählen“ zu rendern.

#### Front-Office-Templates (`views/templates/front/`)

- `cudi/views/templates/front/myDiscount.tpl`
  - **Geltungsbereich:** Front-Office.
  - **Ausgabe:** Dies ist das dedizierte Seitentemplate für den `CudiMydiscountModuleFrontController`. Es zeigt eine umfassende Übersicht über den Loyalitätsstatus des Kunden, einschließlich der Gesamtausgaben, der aktuellen Gruppe, des Rabattprozentsatzes und des Fortschritts zu höheren Stufen.

### 4.7 Datenbankschema & Hooks-Map

#### Datenbanktabellen

Das Modul erstellt keine benutzerdefinierten SQL-Tabellen. Es speichert seine Konfigurationseinstellungen in PrestaShops `ps_configuration`-Tabelle, wobei Schlüssel wie `CUDI_ACTIVE`, `CUDI_ORDERSDATE`, `CUDI_PRICETYPE`, `CUDI_ORDERSTATES`, `CUDI_EX_SP`, `CUDI_EX_SP_QTY`, `CUDI_ORDERCOUPON`, `CUDI_DEFGROUP`, `CUDI_GROUPSNOT`, `CUDI_SHOWINFO_PRODUCT`, `CUDI_SHOWINFO_CART`, `logged_cudi_contents`, `unlogged_cudi_contents` verwendet werden.
Die Regeln für kumulative Rabatte (Ausgabenschwellenwerte und zugehörige Kundengruppen) werden wahrscheinlich als serialisierte Daten innerhalb eines `ps_configuration`-Eintrags gespeichert oder direkt vom `AdminCudiListController` verwaltet, der möglicherweise eine benutzerdefinierte Tabelle verwendet (obwohl nicht explizit in `classes/` oder `sql/` aufgeführt). *Selbstkorrektur: Angesichts des `AdminCudiListController` und seiner Verwaltung der `cudi`-Entität ist es sehr wahrscheinlich, dass eine benutzerdefinierte Tabelle `ps_cudi` existiert, auch wenn sie im bereitgestellten Dossier nicht explizit in `classes/` oder `sql/` aufgeführt ist. Diese Tabelle würde die `id_cudi`, `min_spend`, `id_group`, `discount_percentage` für jede Regel speichern.*

#### Registrierte Hooks-Tabelle

| Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- |
| `displayHeader` | Rendert im `<head>`-Bereich aller Front-Office-Seiten. | Wird verwendet, um CSS/JS-Assets des Moduls für das Front-Office einzubinden oder globale JS-Variablen zu initialisieren. |
| `displayProductAdditionalInfo` | Auf Produktseiten, typischerweise unter der Produktbeschreibung oder dem In-den-Warenkorb-Button. | Zeigt Kunden Informationen zum Treueprogramm (aktueller Rabatt, Fortschritt) an. |
| `displayCustomerAccount` | Auf der Seite „Mein Konto“ des Kunden. | Fügt einen Link zur dedizierten Seite „Meine Rabatte“ hinzu. |
| `displayShoppingCart` | Auf der Warenkorb-Übersichtsseite. | Zeigt Kunden Informationen zum Treueprogramm (aktueller Rabatt, Warenkorbbeitrag) an. |
| `updateOrderStatus` | Wird ausgelöst, wenn der Status einer Bestellung im Back Office geändert wird. | **Entscheidend für die Neuberechnung der Gesamtausgaben des Kunden und die Neuzuweisung seiner Gruppe.** |
| `actionOrderStatusUpdate` | Ähnlich wie `updateOrderStatus`, bietet nach einer Bestellstatusaktualisierung eine granularere Kontrolle. | **Ebenfalls entscheidend für die Neuberechnung der Gesamtausgaben des Kunden und die Neuzuweisung seiner Gruppe.** |
| `actionAdminControllerSetMedia` | Im Back Office, wenn ein Admin-Controller geladen wird. | Wird verwendet, um CSS/JS-Assets des Moduls für das Back-Office einzubinden (z. B. `cudi.js`, `cudi.css`). |

## 5. Offizieller Support & Updates

Für die neuesten Modul-Updates, Fehlerbehebungen und offiziellen Support melden Sie sich bitte in Ihrem Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/) an. Dort finden Sie Ihre gekauften Module und deren Download-Links. Für technische Unterstützung nutzen Sie bitte die auf MyPresta.eu bereitgestellten Supportkanäle.

---
title: "Letzte Produktbewertungen – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Letzte Produktbewertungen“ von MyPresta.eu."
sidebar:
  label: "Letzte Produktbewertungen – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Last product reviews auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/last-product-reviews.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/last-product-reviews/)
>
> ---


# Letzte Produktbewertungen

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 5.6 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind typischerweise ausreichend für dieses Modul.

## 2. Vollständige Konfigurationsanleitung (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modul-Konfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Letzte Produktbewertungen“. Hier finden Sie alle Einstellungen, um zu steuern, wie und wo Ihre Bewertungen angezeigt werden.

#### **Bewertungen anzeigen in**

- **Was diese Einstellung bewirkt:** Diese Option bestimmt, wo der Block „Letzte Produktbewertungen“ auf Ihrer Website erscheint. Sie können aus mehreren Standard-PrestaShop-Hook-Positionen wählen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf „Header“ eingestellt:* Der Bewertungsblock erscheint ganz oben in Ihrem Shop, oft über oder unter Ihrer Hauptnavigation. Dies bietet maximale Sichtbarkeit.
  - *Wenn auf „Linke Spalte“ eingestellt:* Der Bewertungsblock erscheint in der linken Seitenleiste Ihres Shops, falls Ihr Theme eine solche hat.
  - *Wenn auf „Rechte Spalte“ eingestellt:* Der Bewertungsblock erscheint in der rechten Seitenleiste Ihres Shops, falls Ihr Theme eine solche hat.
  - *Wenn auf „Produktseite“ eingestellt:* Der Bewertungsblock erscheint auf einzelnen Produktseiten. Dies ist großartig für Cross-Selling oder um allgemeine soziale Beweise anzuzeigen, während ein Kunde einen Kauf in Betracht zieht.
  - *Wenn auf „Footer“ eingestellt:* Der Bewertungsblock erscheint am unteren Rand jeder Seite, typischerweise über den Copyright-Informationen.
- **Empfohlener Wert:** „Linke Spalte“ oder „Rechte Spalte“ für allgemeine Sichtbarkeit, oder „Produktseite“, wenn Sie Bewertungen während des Kaufentscheidungsprozesses hervorheben möchten. „Header“ kann sehr wirkungsvoll sein, aber je nach Ihrem Theme zu viel erstklassigen Platz einnehmen.
- **Händlerszenario / Beispiel:** Wenn Sie möchten, dass Kunden aktuelle Bewertungen sehen, egal wo sie stöbern, wählen Sie „Linke Spalte“. Wenn Sie Käufe auf Produktseiten fördern möchten, wählen Sie „Produktseite“.

#### **Anzahl der anzuzeigenden Bewertungen**

- **Was diese Einstellung bewirkt:** Dies steuert, wie viele einzelne Produktbewertungen im Block „Letzte Produktbewertungen“ angezeigt werden.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf eine niedrige Zahl eingestellt (z. B. 3):* Der Block wird kompakt sein und nur wenige Bewertungen anzeigen. Dies ist gut, um Platz zu sparen, vermittelt aber möglicherweise nicht so viel Social Proof.
  - *Wenn auf eine höhere Zahl eingestellt (z. B. 10):* Der Block wird größer sein und mehr Bewertungen anzeigen. Dies bietet mehr Social Proof, erfordert aber mehr Bildschirmplatz.
- **Empfohlener Wert:** 3-5 für Spalten, 5-8 für Header/Footer, abhängig vom Layout Ihres Themes und dem verfügbaren Platz.
- **Händlerszenario / Beispiel:** Wenn Ihre linke Spalte schmal ist, stellen Sie dies auf 3 ein, damit der Block nicht zu lang wird. Wenn Sie einen breiten Footer haben, können Sie ihn auf 6 einstellen, um mehr Feedback zu präsentieren.

#### **Kundennamen anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Schalter bestimmt, ob der Name des Kunden, der die Bewertung abgegeben hat, im Bewertungsblock sichtbar ist.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Jede Bewertung zeigt den Namen des Kunden an (z. B. „Bewertung von John D.“). Dies erhöht die Authentizität und Personalisierung.
  - *Wenn deaktiviert (NEIN):* Der Name des Kunden wird ausgeblendet, und nur der Bewertungsinhalt und das Produkt werden angezeigt. Dies kann aus Datenschutzgründen oder für ein minimalistischeres Design bevorzugt werden.
- **Empfohlener Wert:** JA. Die Anzeige von Kundennamen erhöht die Glaubwürdigkeit und lässt die Bewertungen echter wirken.
- **Händlerszenario / Beispiel:** Um das Vertrauen zu maximieren, aktivieren Sie dies. Wenn Sie Bedenken hinsichtlich der Kundendaten haben oder ein sehr sauberes Aussehen bevorzugen, können Sie es deaktivieren.

#### **Produktnamen anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob der Name des bewerteten Produkts zusammen mit dem Bewertungstext angezeigt wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Jede Bewertung gibt klar an, auf welches Produkt sie sich bezieht (z. B. „Produkt: Super Widget“). Dies hilft Kunden, den Kontext der Bewertung zu verstehen.
  - *Wenn deaktiviert (NEIN):* Nur der Bewertungstext und der Kundenname (falls aktiviert) werden angezeigt, ohne explizite Erwähnung des Produkts. Dies macht den Block generischer.
- **Empfohlener Wert:** JA. Es ist entscheidend für Kunden zu wissen, welches Produkt bewertet wird.
- **Händlerszenario / Beispiel:** Wenn ein Kunde eine begeisterte Bewertung sieht, möchte er wissen, um welches Produkt es sich handelt. Wenn dies aktiviert ist, kann er darauf klicken und möglicherweise diesen bestimmten Artikel kaufen.

#### **Bewertungsinhalt anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Schalter bestimmt, ob der eigentliche Text der Kundenbewertung im Block angezeigt wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Der vollständige oder gekürzte Text der Bewertung wird angezeigt. Dies bietet potenziellen Käufern detailliertes Feedback.
  - *Wenn deaktiviert (NEIN):* Nur die Bewertung (Sterne), der Kundenname und der Produktname werden angezeigt, ohne die schriftliche Bewertung. Dies erzeugt einen sehr kompakten Block, der sich nur auf die Sternbewertungen konzentriert.
- **Empfohlener Wert:** JA. Der Bewertungsinhalt ist der wertvollste Teil des Social Proofs.
- **Händlerszenario / Beispiel:** Um Kunden einen schnellen Überblick darüber zu geben, was andere sagen, aktivieren Sie dies. Wenn Sie nur Sternbewertungen als schnelles Vertrauenssignal anzeigen möchten, könnten Sie es deaktivieren.

#### **Bewertungssterne anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob die Sternbewertung (z. B. 5 von 5 Sternen), die mit jeder Bewertung verbunden ist, sichtbar ist.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Die Sternbewertung wird für jede Bewertung prominent angezeigt. Dies ist ein schneller visueller Indikator für die Produktqualität.
  - *Wenn deaktiviert (NEIN):* Die Sternbewertung wird ausgeblendet, und nur der Textinhalt (falls aktiviert) wird angezeigt. Dies wird im Allgemeinen nicht empfohlen, da Sternbewertungen ein universelles Vertrauenssignal sind.
- **Empfohlener Wert:** JA. Sternbewertungen sind unglaublich effektiv, um die Produktzufriedenheit schnell zu vermitteln.
- **Händlerszenario / Beispiel:** Aktivieren Sie dies immer, um Kunden einen sofortigen visuellen Hinweis auf Produktqualität und Kundenzufriedenheit zu geben.

#### **Produktbild anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Schalter bestimmt, ob das Hauptbild des bewerteten Produkts neben der Bewertung angezeigt wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Ein kleines Vorschaubild des Produktbildes erscheint bei jeder Bewertung. Dies macht den Block optisch ansprechender und hilft Kunden, das Produkt schnell zu identifizieren.
  - *Wenn deaktiviert (NEIN):* Es wird kein Produktbild angezeigt, wodurch der Block textlastiger wird.
- **Empfohlener Wert:** JA. Produktbilder verbessern die visuelle Attraktivität und Klarheit des Bewertungsblocks erheblich.
- **Händlerszenario / Beispiel:** Um Ihren Bewertungsblock ansprechender zu gestalten und Kunden zu helfen, Bewertungen schnell bestimmten Produkten zuzuordnen, aktivieren Sie Produktbilder.

#### **Produktpreis anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob der aktuelle Preis des bewerteten Produkts im Bewertungsblock angezeigt wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Der Preis des Produkts wird angezeigt. Dies kann nützlich sein für Kunden, die preissensibel sind oder schnell sehen möchten, ob ein bewertetes Produkt in ihr Budget passt.
  - *Wenn deaktiviert (NEIN):* Der Preis wird nicht angezeigt, wodurch der Fokus ausschließlich auf der Bewertung und den Produktdetails bleibt.
- **Empfohlener Wert:** NEIN, es sei denn, Sie möchten Produktpreise im Bewertungsblock explizit hervorheben. Es kann manchmal die Anzeige überladen.
- **Händlerszenario / Beispiel:** Wenn Sie einen Sale durchführen und bewertete Produkte hervorheben möchten, die derzeit reduziert sind, könnten Sie dies aktivieren. Andernfalls ist es oft besser, den Fokus auf die Bewertung selbst zu legen.

#### **Produktlink anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Schalter bestimmt, ob der Produktname (oder das Bild, falls aktiviert) im Bewertungsblock ein anklickbarer Link ist, der den Kunden direkt zur Produktseite führt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Kunden können auf den Produktnamen/das Bild klicken, um zur vollständigen Produktseite zu navigieren, wo sie mehr erfahren und möglicherweise einen Kauf tätigen können. Dies ist entscheidend, um Traffic auf Produktseiten zu lenken.
  - *Wenn deaktiviert (NEIN):* Der Produktname/das Bild ist statischer Text/Bild, und Kunden können nicht durchklicken. Dies reduziert die Fähigkeit des Moduls, Konversionen zu fördern.
- **Empfohlener Wert:** JA. Aktivieren Sie dies immer, damit Kunden bewertete Produkte leicht erkunden können.
- **Händlerszenario / Beispiel:** Ein Kunde sieht eine großartige Bewertung für einen „Bluetooth-Lautsprecher“. Wenn der Produktname anklickbar ist, kann er sofort zur Seite des Lautsprechers gehen, um ihn zu kaufen.

#### **Datum der Bewertung anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Schalter steuert, ob das Datum, an dem die Bewertung abgegeben wurde, angezeigt wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Das Datum (z. B. „Bewertet am 26.10.2023“) wird angezeigt. Dies erhöht die Transparenz und versichert den Kunden, dass die Bewertungen aktuell und relevant sind.
  - *Wenn deaktiviert (NEIN):* Das Datum wird ausgeblendet.
- **Empfohlener Wert:** JA. Aktuelle Bewertungen sind wirkungsvoller und vertrauenswürdiger.
- **Händlerszenario / Beispiel:** Die Anzeige des Datums hilft Kunden zu sehen, dass Ihr Shop aktiv ist und ständig neues Feedback erhält, was Vertrauen schafft.

#### **Bewertungstitel anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Schalter bestimmt, ob der Titel der Bewertung (falls Kunden einen angeben) angezeigt wird.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Wenn eine Bewertung einen Titel hat (z. B. „Erstaunliches Produkt!“), wird dieser angezeigt, oft fett gedruckt, und bietet eine schnelle Zusammenfassung der Stimmung der Bewertung.
  - *Wenn deaktiviert (NEIN):* Nur der Hauptbewertungsinhalt wird angezeigt, ohne einen separaten Titel.
- **Empfohlener Wert:** JA. Bewertungstitel eignen sich hervorragend, um schnell Aufmerksamkeit zu erregen und die Essenz der Bewertung zusammenzufassen.
- **Händlerszenario / Beispiel:** Ein Kunde, der schnell Bewertungen scannt, kann die Essenz aus Titeln wie „Großartiger Wert“ oder „Enttäuscht“ entnehmen, bevor er den vollständigen Text liest.

#### **Mindestbewertung zum Anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Filter ermöglicht es Ihnen, eine Mindeststernbewertung für Bewertungen festzulegen, die im Block „Letzte Produktbewertungen“ enthalten sein sollen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn auf 1 Stern eingestellt:* Alle Bewertungen (1-5 Sterne) werden angezeigt.
  - *Wenn auf 3 Sterne eingestellt:* Nur Bewertungen mit 3, 4 oder 5 Sternen werden angezeigt. Bewertungen mit 1 oder 2 Sternen werden ausgeschlossen.
  - *Wenn auf 5 Sterne eingestellt:* Nur perfekte 5-Sterne-Bewertungen werden angezeigt.
- **Empfohlener Wert:** 3 oder 4 Sterne. Obwohl Transparenz gut ist, möchten Sie in diesem prominenten Block möglicherweise hauptsächlich positives Feedback hervorheben.
- **Händlerszenario / Beispiel:** Um sicherzustellen, dass Ihr Block „Letzte Produktbewertungen“ immer positives Feedback zeigt, stellen Sie dies auf 4 Sterne ein. Dies hilft, ein positives Image zu bewahren und gleichzeitig authentisch zu sein.

#### **Nur Bewertungen aus ausgewählter Kategorie anzeigen**

- **Was diese Einstellung bewirkt:** Diese Option ermöglicht es Ihnen, die angezeigten Bewertungen so zu filtern, dass nur solche angezeigt werden, die Produkten aus einer bestimmten Kategorie zugeordnet sind.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn „Nein“ ausgewählt ist:* Bewertungen aus allen Kategorien werden zur Anzeige berücksichtigt.
  - *Wenn eine bestimmte Kategorie (z. B. „Elektronik“) ausgewählt ist:* Nur Bewertungen für Produkte innerhalb der Kategorie „Elektronik“ (und ihrer Unterkategorien) werden angezeigt.
- **Empfohlener Wert:** „Nein“ für allgemeinen Social Proof. Wählen Sie eine Kategorie aus, wenn der Bewertungsblock in einem Kontext platziert wird, in dem nur bestimmte Produkttypen relevant sind (z. B. auf einer Kategorieseite).
- **Händlerszenario / Beispiel:** Wenn Sie den Bewertungsblock auf Ihrer Kategorie-Seite „T-Shirts“ platzieren, könnten Sie hier die Kategorie „T-Shirts“ auswählen, um sicherzustellen, dass nur relevante Bewertungen angezeigt werden, was das Kundenerlebnis verbessert.

#### **Nur Bewertungen von ausgewähltem Produkt anzeigen**

- **Was diese Einstellung bewirkt:** Diese Option ermöglicht es Ihnen, die angezeigten Bewertungen so zu filtern, dass nur solche angezeigt werden, die einem bestimmten Produkt zugeordnet sind.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn „Nein“ ausgewählt ist:* Bewertungen für alle Produkte werden zur Anzeige berücksichtigt.
  - *Wenn ein bestimmtes Produkt (z. B. „Mein tolles Gadget“) ausgewählt ist:* Nur Bewertungen für „Mein tolles Gadget“ werden angezeigt.
- **Empfohlener Wert:** „Nein“ für allgemeinen Social Proof. Wählen Sie ein Produkt aus, wenn der Bewertungsblock in einem Kontext platziert wird, in dem nur die Bewertungen eines einzelnen Produkts relevant sind (z. B. auf einer benutzerdefinierten Landingpage für dieses Produkt).
- **Händlerszenario / Beispiel:** Wenn Sie eine spezielle Aktionsseite für Ihre „Bestseller-Kaffeemaschine“ haben, könnten Sie diesen Block so konfigurieren, dass auf dieser Seite nur Bewertungen für diese spezielle Kaffeemaschine angezeigt werden.

#### **Bewertungen als Slider anzeigen**

- **Was diese Einstellung bewirkt:** Dieser Schalter aktiviert oder deaktiviert einen dynamischen Slider (Karussell) für den Bewertungsblock.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Die Bewertungen scrollen automatisch oder ermöglichen Kunden die Navigation durch Pfeile/Punkte. Dies ist großartig, um viele Bewertungen auf kompaktem Raum anzuzeigen.
  - *Wenn deaktiviert (NEIN):* Die Bewertungen werden als statische Liste nacheinander angezeigt.
- **Empfohlener Wert:** JA, besonders wenn Sie mehr als 3-4 Bewertungen anzeigen oder wenn der Block in einer schmalen Spalte ist.
- **Händlerszenario / Beispiel:** Wenn Sie 8 Bewertungen in Ihrer linken Spalte anzeigen möchten, aber nicht möchten, dass die Spalte übermäßig lang wird, macht die Aktivierung des Sliders sie kompakt und interaktiv.

#### **Slider automatisch abspielen**

- **Was diese Einstellung bewirkt:** Wenn „Bewertungen als Slider anzeigen“ aktiviert ist, steuert diese Einstellung, ob der Slider automatisch zur nächsten Bewertung wechselt, ohne Benutzerinteraktion.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Der Slider wechselt nach einer festgelegten Verzögerung automatisch zwischen den Bewertungen.
  - *Wenn deaktiviert (NEIN):* Der Slider bewegt sich nur, wenn der Kunde auf Navigationspfeile oder Punkte klickt.
- **Empfohlener Wert:** JA, aber stellen Sie sicher, dass die „Slider Auto-Play-Geschwindigkeit“ auf eine angemessene Dauer eingestellt ist.
- **Händlerszenario / Beispiel:** Um den Bewertungsblock dynamisch zu halten und sicherzustellen, dass alle Bewertungen sichtbar werden, aktivieren Sie die automatische Wiedergabe.

#### **Slider Auto-Play-Geschwindigkeit (in ms)**

- **Was diese Einstellung bewirkt:** Wenn „Slider automatisch abspielen“ aktiviert ist, bestimmt diese Einstellung, wie lange (in Millisekunden) jede Bewertung angezeigt wird, bevor der Slider automatisch zur nächsten wechselt.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Eine niedrigere Zahl (z. B. 2000ms = 2 Sekunden):* Bewertungen wechseln schnell.
  - *Eine höhere Zahl (z. B. 5000ms = 5 Sekunden):* Bewertungen bleiben länger sichtbar, was Kunden mehr Zeit zum Lesen gibt.
- **Empfohlener Wert:** 4000-6000 (4-6 Sekunden), um Kunden genügend Zeit zum Lesen einer Bewertung zu geben, ohne sich gehetzt zu fühlen.
- **Händlerszenario / Beispiel:** Stellen Sie dies auf 5000ms ein, damit Kunden ausreichend Zeit haben, jede Bewertung zu lesen, während sie vorbeigleitet.

#### **Slider-Steuerelemente**

- **Was diese Einstellung bewirkt:** Wenn „Bewertungen als Slider anzeigen“ aktiviert ist, steuert dies, ob Navigationspfeile (links/rechts) für Kunden sichtbar sind, um Bewertungen manuell zu durchsuchen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Pfeile erscheinen auf dem Slider, die eine manuelle Navigation ermöglichen.
  - *Wenn deaktiviert (NEIN):* Es werden keine Pfeile angezeigt. Kunden können sich nur auf die automatische Wiedergabe (falls aktiviert) oder Touch-/Wischgesten verlassen.
- **Empfohlener Wert:** JA. Die Bereitstellung von Steuerelementen verbessert die Benutzererfahrung, auch bei automatischer Wiedergabe.
- **Händlerszenario / Beispiel:** Um Kunden die volle Kontrolle über das Durchsuchen von Bewertungen zu geben, aktivieren Sie die Slider-Steuerelemente.

#### **Slider-Pager**

- **Was diese Einstellung bewirkt:** Wenn „Bewertungen als Slider anzeigen“ aktiviert ist, steuert dies, ob kleine Punkte (Paginierung) sichtbar sind, die die Gesamtzahl der Bewertungen und die aktuell angezeigte Bewertung anzeigen.
- **Auswirkung der Änderung dieser Einstellung:**
  - *Wenn aktiviert (JA):* Punkte erscheinen, die den Fortschritt anzeigen und direkte Sprünge zu bestimmten Bewertungen ermöglichen.
  - *Wenn deaktiviert (NEIN):* Es werden keine Punkte angezeigt.
- **Empfohlener Wert:** JA. Pager bieten eine klare visuelle Anzeige, wie viele Bewertungen verfügbar sind und wo sich der Kunde in der Reihenfolge befindet.
- **Händlerszenario / Beispiel:** Um Kunden zu helfen, zu verstehen, wie viele Bewertungen im Slider sind und einfach zu einer bestimmten zu springen, aktivieren Sie den Slider-Pager.

### 2.2 Konfigurations-Kurzübersichtstabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Bewertungen anzeigen in | Linke Spalte / Rechte Spalte | Steuert die Position des Bewertungsblocks in Ihrem Shop. |
| Modulkonfiguration | Anzahl der anzuzeigenden Bewertungen | 3-5 (Spalten), 5-8 (Header/Footer) | Legt fest, wie viele Bewertungen im Block sichtbar sind. |
| Modulkonfiguration | Kundennamen anzeigen | JA | Zeigt den Namen des Rezensenten für Authentizität an. |
| Modulkonfiguration | Produktnamen anzeigen | JA | Verknüpft die Bewertung eindeutig mit ihrem Produkt. |
| Modulkonfiguration | Bewertungsinhalt anzeigen | JA | Zeigt den eigentlichen Text der Bewertung an. |
| Modulkonfiguration | Bewertungssterne anzeigen | JA | Visueller Indikator für die Produktbewertung. |
| Modulkonfiguration | Produktbild anzeigen | JA | Macht den Block optisch ansprechender und identifizierbarer. |
| Modulkonfiguration | Produktpreis anzeigen | NEIN | Zeigt den Produktpreis an (kann überladen, meist nicht nötig). |
| Modulkonfiguration | Produktlink anzeigen | JA | Ermöglicht Kunden, zur Produktseite zu klicken. |
| Modulkonfiguration | Datum der Bewertung anzeigen | JA | Zeigt an, wann die Bewertung abgegeben wurde, beweist Aktualität. |
| Modulkonfiguration | Bewertungstitel anzeigen | JA | Zeigt den Titel der Bewertung für schnelle Zusammenfassungen an. |
| Modulkonfiguration | Mindestbewertung zum Anzeigen | 3 oder 4 Sterne | Filtert niedriger bewertete Bewertungen für eine positive Anzeige heraus. |
| Modulkonfiguration | Nur Bewertungen aus ausgewählter Kategorie anzeigen | Nein | Filtert Bewertungen nach Produktkategorie. |
| Modulkonfiguration | Nur Bewertungen von ausgewähltem Produkt anzeigen | Nein | Filtert Bewertungen nach einem bestimmten Produkt. |
| Modulkonfiguration | Bewertungen als Slider anzeigen | JA | Präsentiert Bewertungen in einem dynamischen, scrollenden Karussell. |
| Modulkonfiguration | Slider automatisch abspielen | JA | Bewegt den Slider automatisch vorwärts. |
| Modulkonfiguration | Slider Auto-Play-Geschwindigkeit (in ms) | 4000-6000 | Legt die Dauer fest, für die jede Bewertung im Slider angezeigt wird. |
| Modulkonfiguration | Slider-Steuerelemente | JA | Zeigt Navigationspfeile zur manuellen Slider-Steuerung an. |
| Modulkonfiguration | Slider-Pager | JA | Zeigt Punkte für die Slider-Paginierung an. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F: Ich habe das Modul konfiguriert, aber der Bewertungsblock wird in meinem Shop nicht angezeigt.**
A:

1. **Modulposition prüfen:** Gehen Sie im Back Office zu **Design > Positionen** (oder **Module > Positionen** in älteren PrestaShop-Versionen). Suchen Sie nach `displayLastReviews` (oder dem Hook, den Sie in der Modulkonfiguration ausgewählt haben). Stellen Sie sicher, dass das Modul „Letzte Produktbewertungen“ für diesen Hook aufgeführt und aktiviert ist. Falls nicht, klicken Sie auf „Modul transplantieren“ und fügen Sie es dem gewünschten Hook hinzu.
2. **Cache leeren:** PrestaShop speichert Inhalte oft im Cache. Gehen Sie zu **Erweiterte Einstellungen > Leistung** und klicken Sie auf „Cache leeren“ (oder die Schaltflächen „Smarty-Cache leeren“ und „Cache leeren“).
3. **Auf Bewertungen prüfen:** Stellen Sie sicher, dass Sie tatsächlich genehmigte Produktbewertungen in Ihrem Shop haben. Das Modul kann nur Bewertungen anzeigen, die existieren und sichtbar sind.
4. **Theme-Kompatibilität:** Obwohl das Modul auf Kompatibilität ausgelegt ist, können einige stark angepasste Themes geringfügige CSS-Anpassungen erfordern. Überprüfen Sie die Entwicklerkonsole Ihres Browsers auf JavaScript-Fehler.

**F: Die Bewertungen werden angezeigt, aber sie sehen nicht richtig aus (z. B. schlechtes Styling, Bilder zu groß).**
A:

1. **Theme-Konflikte:** Das CSS Ihres Themes könnte die Stile des Moduls überschreiben. Sie können versuchen, benutzerdefiniertes CSS in die `custom.css`-Datei Ihres Themes (falls vorhanden) hinzuzufügen oder direkt `lastreviews/views/css/lastreviews.css` zu bearbeiten (obwohl dies nicht update-sicher ist).
2. **Bildgrößen:** Wenn Produktbilder zu groß sind, überprüfen Sie die Bildeinstellungen Ihres Themes oder das CSS des Moduls. Das Modul verwendet eine Standardbildgröße, aber Ihr Theme könnte es anders rendern.
3. **Slider-Probleme:** Wenn der Slider nicht funktioniert, stellen Sie sicher, dass „Bewertungen als Slider anzeigen“ aktiviert ist. Suchen Sie in der Browserkonsole nach JavaScript-Fehlern, da andere Module oder Theme-Skripte Konflikte verursachen könnten.

**F: Kann ich Bewertungen nur von einem bestimmten Produkt oder einer Kategorie anzeigen lassen?**
A: Ja! In der Modulkonfiguration haben Sie Optionen für „Nur Bewertungen aus ausgewählter Kategorie anzeigen“ und „Nur Bewertungen von ausgewähltem Produkt anzeigen“. Verwenden Sie diese Dropdowns, um die im Block angezeigten Bewertungen zu filtern.

**F: Meine Bewertungen sind in mehreren Sprachen. Zeigt das Modul sie korrekt an?**
A: Das Modul stützt sich auf das Standard-Bewertungssystem von PrestaShop. Wenn Ihre Bewertungen in PrestaShop korrekt mit Sprachen verknüpft sind, sollte das Modul die Bewertungen in der aktiven Front-Office-Sprache anzeigen. Stellen Sie sicher, dass Ihr Theme und PrestaShop korrekt für mehrsprachige Inhalte konfiguriert sind.

**F: Wie erhalte ich mehr Bewertungen zur Anzeige?**
A: Dieses Modul *zeigt* nur vorhandene Bewertungen an. Um mehr Bewertungen zu erhalten, müssen Sie Kunden dazu ermutigen, diese abzugeben. Erwägen Sie die Verwendung eines separaten Moduls für Bewertungserinnerungen, das Anbieten von Anreizen oder die sehr einfache Gestaltung des Bewertungsprozesses auf Ihren Produktseiten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Letzte Produktbewertungen“ ist ein Standard-PrestaShop-Modul, das einem MVC-ähnlichen Muster folgt. Es fungiert hauptsächlich als Front-Office-Funktion, die sich in verschiedene Anzeigepunkte einklinkt, um einen Block der neuesten Produktbewertungen zu rendern. Es nutzt die Kernfunktionalität von PrestaShop `ProductComment` (oder ähnliches), um Bewertungsdaten abzurufen. Die Hauptlogik des Moduls befindet sich in `index.php`, wo die Konfiguration und Hook-Registrierung gehandhabt werden, während Templates und Assets die Front-End-Anzeige verwalten. Es verwendet eine JavaScript-Bibliothek eines Drittanbieters, `lightslider.js`, für die Karussellfunktionalität.

### 4.2 Controller (`controllers/`)

Dieses Modul enthält keine benutzerdefinierten Front-Office- oder Back-Office-Admin-Controller. Die gesamte Konfiguration wird direkt innerhalb der `getContent()`-Methode der Hauptmodulklasse gehandhabt.

### 4.3 Kernklassen & Modelle (`classes/`)

Dieses Modul definiert keine benutzerdefinierten Klassen oder `ObjectModel`s in einem `classes/`-Verzeichnis. Es stützt sich auf PrestaShops Kern `ProductComment` (oder Äquivalent, abhängig von der PrestaShop-Version und ob das offizielle Produktkommentar-Modul installiert ist), um Bewertungsdaten abzurufen.

### 4.4 JavaScript-Assets (`views/js/`)

- **`lastreviews/lib/src/js/lightslider.js`**
  - **Umfang:** Front-Office.
  - **Zweck:** Dies ist die zentrale JavaScript-Bibliothek zum Erstellen responsiver Inhalts-Slider/Karussells. Sie bietet die Funktionalität für die Funktion „Bewertungen als Slider anzeigen“.
  - **Funktionalität:** Bindet an ein `<ul>`-Element (oder einen ähnlichen Container), um es in einen responsiven Slider zu verwandeln. Es verwaltet die automatische Wiedergabe, Navigationssteuerelemente (Pfeile), Paginierung (Punkte), Touch-/Wischgesten und responsive Größenanpassung.
  - **Abhängigkeiten:** Benötigt typischerweise jQuery.

### 4.5 CSS-Stylesheets (`views/css/`)

- **`lastreviews/lib/src/css/lightslider.css`**

  - **Umfang:** Front-Office-Kundenstyling.
  - **Zweck:** Bietet das Standard-Styling für die `lightslider.js`-Bibliothek, einschließlich grundlegendem Layout, Navigationspfeilen, Pager-Punkten und Animationsstilen für den Slider.
  - **Wichtige Selektoren:** `.lightSlider`, `.lSAction > .lSPrev`, `.lSAction > .lSNext`, `.lSPager` usw. Entwickler können diese überschreiben, um sie an die Ästhetik ihres Themes anzupassen.
- **`lastreviews/views/css/lastreviews.css`**

  - **Umfang:** Front-Office-Kundenstyling.
  - **Zweck:** Enthält benutzerdefiniertes Styling speziell für den Anzeigeblock des Moduls „Letzte Produktbewertungen“. Dies umfasst das Styling für den Bewertungscontainer, einzelne Bewertungselemente, Produktbilder, Sternbewertungen und Textelemente.
  - **Wichtige Selektoren:** `.last-reviews-block`, `.last-review-item`, `.review-product-image`, `.review-stars`, `.review-customer-name`, `.review-product-name` usw. Diese Selektoren sind so konzipiert, dass sie leicht durch das CSS eines benutzerdefinierten Themes zur Integration überschrieben werden können.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

- **Hook-Templates (`views/templates/hook/`)**:
  - **`lastreviews/views/templates/hook/admin-tips.tpl`**
    - **Zweck:** Dieses Template wird wahrscheinlich auf der Back-Office-Konfigurationsseite (`getContent()`) verwendet, um administrative Tipps oder Anweisungen für den Händler anzuzeigen. Es wird nicht im Front Office gerendert.
    - **Inhalt:** Enthält typischerweise HTML für Informationsmeldungen, Links zu Dokumentationen oder Warnungen.
  - **`lastreviews/views/templates/hook/last-reviews.tpl`**
    - **Zweck:** Dies ist das Haupt-Front-Office-Template, das für das Rendern des Blocks „Letzte Produktbewertungen“ verantwortlich ist. Es ist in verschiedene Anzeigepunkte (z. B. `displayLeftColumn`, `displayFooter`) eingehängt.
    - **Daten:** Empfängt ein Array von Bewertungsdaten (Kundenname, Produktname, Bewertung, Inhalt, Datum, Bild, Link) von der PHP-Logik des Moduls.
    - **Struktur:** Iteriert durch die bereitgestellten Bewertungen und zeigt Elemente bedingt basierend auf der Modulkonfiguration an (z. B. Kundenname, Produktbild, Slider). Es enthält die notwendige HTML-Struktur für die Initialisierung von `lightslider.js`, wenn die Slider-Option aktiviert ist.

### 4.7 Datenbankschema & Hooks-Map

- **Datenbanktabellen**:

  - Dieses Modul erstellt keine eigenen benutzerdefinierten Datenbanktabellen. Es stützt sich auf die Kern-PrestaShop-Tabellen für Produktbewertungen, typischerweise `ps_product_comment` und verwandte Tabellen (wenn das offizielle Produktkommentar-Modul installiert und aktiv ist).
  - Konfigurationseinstellungen werden in der Tabelle `ps_configuration` gespeichert, wobei die Schlüssel typischerweise mit `LASTREVIEWS_` beginnen (z. B. `LASTREVIEWS_DISPLAY_IN`, `LASTREVIEWS_NUM_REVIEWS`).
- **Registrierte Hooks-Tabelle**:

  | Hook-Name | Ausführungszeitpunkt | Technischer Zweck |
  | --- | --- | --- |
  | `displayHeader` | Im `<head>`-Bereich aller Front-Office-Seiten. | Wird verwendet, um CSS/JS-Assets einzubinden und den Bewertungsblock möglicherweise oben auf der Seite zu rendern. |
  | `displayLeftColumn` | In der linken Seitenleiste von Front-Office-Seiten. | Rendert den Bewertungsblock in der linken Spalte. |
  | `displayRightColumn` | In der rechten Seitenleiste von Front-Office-Seiten. | Rendert den Bewertungsblock in der rechten Spalte. |
  | `displayFooter` | Im Footer-Bereich aller Front-Office-Seiten. | Rendert den Bewertungsblock im Footer. |
  | `displayProductAdditionalInfo` (oder ähnlicher Produktseiten-Hook) | Auf der Produktseite, typischerweise unter den Hauptproduktinformationen. | Rendert den Bewertungsblock auf einzelnen Produktseiten. |
  | `actionFrontControllerSetMedia` | Wird ausgeführt, wenn ein Front-Controller seine Medien (CSS/JS) setzt. | Wird verwendet, um die CSS- und JavaScript-Dateien des Moduls (`lightslider.js`, `lastreviews.css`) für das Laden im Front Office zu registrieren. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Letzte Produktbewertungen“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/my-account/orders/). Unser Support-Team steht Ihnen bei allen Problemen oder Fragen bezüglich der Funktionalität und Kompatibilität des Moduls zur Verfügung.

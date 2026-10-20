---
title: "Zwei Preise anzeigen – inkl. / exkl. Steuern – Händlerhandbuch & Konfigurationsanleitung"
description: "Vollständiges Benutzerhandbuch, schrittweise Einrichtungsanleitung und Entwicklerreferenz für das PrestaShop-Modul „Zwei Preise anzeigen – inkl. / exkl. Steuern“ von MyPresta.eu."
sidebar:
  label: "Zwei Preise anzeigen – inkl. / exkl. Steuern – Händlerhandbuch & Konfigurationsanleitung"
---

> ⚠️ **Notice:** This is the offizielle Dokumentation für das PrestaShop-Modul.
> - 🛒 **Die vollständige kommerzielle Spezifikation, den Changelog und die Kaufoption finden Sie auf der offiziellen Produktseite auf MyPresta.eu:** [Modul Show two prices - tax included / excluded auf MyPresta.eu kaufen](https://mypresta.eu/modules/front-office-features/show-two-prices-tax-included-excluded.html)
> - 🌐 **Offizielles Online-Dokumentationsportal:** [Interaktive Dokumentation auf MyPresta.eu lesen](https://mypresta.eu/docs/de/front-office/show-two-prices-tax-included-excluded/)
>
> ---


# Zwei Preise anzeigen – inkl. / exkl. Steuern

## 1. Anforderungen & Kompatibilität

- **Unterstützte PrestaShop-Versionen**: PrestaShop 1.7.x, 8.x, 9.x
- **PHP-Kompatibilität**: PHP 7.1 - 8.5
- **Hosting-Anforderungen**: Standard-PHP-Erweiterungen (cURL, JSON, OpenSSL) sind für PrestaShop selbst und generell für den Modulbetrieb erforderlich. Keine speziellen Hosting-Anforderungen über eine standardmäßige PrestaShop-kompatible Umgebung hinaus.

## 2. Vollständiger Konfigurations-Walkthrough (Jede Einstellung nach Bildschirm gruppiert)

### 2.1 Modulkonfigurationsseite (Back Office > Module > Konfigurieren)

Dies ist der Hauptkonfigurationsbildschirm für das Modul „Zwei Preise anzeigen – inkl. / exkl. Steuern“. Sie können darauf zugreifen, indem Sie zu **Module > Modul-Manager** navigieren und neben dem Modulnamen auf „Konfigurieren“ klicken.

#### Allgemeine Einstellungen

-   **Aktiviert / Deaktiviert (Globaler Schalter)**
    -   **Was diese Einstellung bewirkt:** Dies ist der Hauptschalter, um die gesamte Funktionalität des Moduls in Ihrem Shop ein- oder auszuschalten.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Das Modul beginnt, beide Preise (inklusive und exklusive Steuern) gemäß Ihren anderen Einstellungen anzuzeigen.
        -   *Wenn deaktiviert:* Das Modul stoppt die Anzeige der zusätzlichen Preisinformationen, und Ihr Shop kehrt zu seinem Standard-Preisverhalten zurück.
    -   **Empfohlener Wert:** Aktiviert (um die Funktionen des Moduls zu nutzen).
    -   **Händlerszenario / Beispiel:** Wenn Sie Wartungsarbeiten durchführen oder die doppelte Preisanzeige vorübergehend ausblenden möchten, können Sie sie hier deaktivieren.

#### Produktseiten-Einstellungen

-   **Auf Produktseite anzeigen (BF\_PP)**

    -   **Was diese Einstellung bewirkt:** Steuert, ob sowohl Preise inklusive als auch exklusive Steuern auf einzelnen Produktdetailseiten angezeigt werden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Beide Preise erscheinen auf den Produktseiten.
        -   *Wenn deaktiviert:* Nur der Standard-PrestaShop-Preis (normalerweise inklusive Steuern) wird auf den Produktseiten angezeigt.
    -   **Empfohlener Wert:** Ein (um volle Transparenz zu gewährleisten).
    -   **Händlerszenario / Beispiel:** Wenn Sie doppelte Preise nur in Kategorielisten anzeigen möchten, aber die Produktseiten übersichtlicher halten wollen, könnten Sie dies deaktivieren.
-   **Preis inkl. Steuern auf Produktseite ausblenden (BOTH\_HIDE\_P)**

    -   **Was diese Einstellung bewirkt:** Wenn „Auf Produktseite anzeigen“ aktiviert ist, können Sie mit dieser Option den Preis inklusive Steuern ausblenden, sodass effektiv nur der Preis exklusive Steuern neben dem Originalpreis (falls nicht ausgeblendet) angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Der Preis inklusive Steuern wird auf den Produktseiten ausgeblendet.
        -   *Wenn deaktiviert:* Der Preis inklusive Steuern ist auf den Produktseiten sichtbar (wenn „Auf Produktseite anzeigen“ aktiviert ist).
    -   **Empfohlener Wert:** Aus (es sei denn, Sie haben einen spezifischen Grund, ihn auszublenden, z. B. ein B2B-orientierter Shop).
    -   **Händlerszenario / Beispiel:** Ein B2B-Shop möchte möglicherweise Preise exklusive Steuern hervorheben und den Preis inklusive Steuern ausblenden, um die Ansicht für seine Geschäftskunden zu optimieren.
-   **Benutzerdefiniertes CSS für Produktseite (BF\_PPC)**

    -   **Was diese Einstellung bewirkt:** Ermöglicht das Hinzufügen benutzerdefinierter CSS-Regeln speziell für die doppelte Preisanzeige auf Produktseiten. Dies ist für fortgeschrittene Benutzer oder Webmaster.
    -   **Auswirkung der Änderung dieser Einstellung:** Jeder hier eingegebene CSS-Code wird auf die Preiselemente des Moduls auf den Produktseiten angewendet, sodass Sie Farben, Schriftarten, Größen oder Positionierung ändern können.
    -   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Styling-Anforderungen.
    -   **Händlerszenario / Beispiel:** Sie möchten den Preis exklusive Steuern kleiner oder in einer anderen Farbe als den Preis inklusive Steuern darstellen, um sie visuell zu unterscheiden.
-   **Produktseite erzwingen ausblenden (BP\_FORCE\_HIDE)**

    -   **Was diese Einstellung bewirkt:** Dies ist eine aggressivere Option, um die Ausgabe des Moduls auf der Produktseite auszublenden. Sie kann nützlich sein, wenn die Ausgabe des Moduls mit Ihrem Theme oder anderen Modulen kollidiert.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Das Modul versucht, seine Preisanzeige auf Produktseiten zwangsweise auszublenden, unabhängig von anderen Einstellungen.
        -   *Wenn deaktiviert:* Das Modul zeigt Preise gemäß anderen Einstellungen an.
    -   **Empfohlener Wert:** Aus (nur aktivieren, wenn Anzeigeprobleme auftreten).
    -   **Händlerszenario / Beispiel:** Wenn die doppelte Preisanzeige ein anderes Element auf Ihrer Produktseite überlappt, kann das Aktivieren dieser Option den Konflikt lösen.
-   **Label für Preis inkl. Steuern (BP\_TIN)**

    -   **Was diese Einstellung bewirkt:** Definiert den Textlabel, der neben dem Preis inklusive Steuern auf Produktseiten angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:** Ändert den Labeltext.
    -   **Empfohlener Wert:** „inkl. MwSt.“ oder „inkl. USt.“
    -   **Händlerszenario / Beispiel:** Sie könnten dies in „Preis mit MwSt.“ ändern, um in bestimmten Regionen Klarheit zu schaffen.
-   **Label für Preis exkl. Steuern (BP\_TEX)**

    -   **Was diese Einstellung bewirkt:** Definiert den Textlabel, der neben dem Preis exklusive Steuern auf Produktseiten angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:** Ändert den Labeltext.
    -   **Empfohlener Wert:** „exkl. MwSt.“ oder „exkl. USt.“
    -   **Händlerszenario / Beispiel:** Sie könnten dies in „Preis ohne MwSt.“ ändern, um Klarheit zu schaffen.
-   **Label für Originalpreis inkl. Steuern (BP\_O\_TIN)**

    -   **Was diese Einstellung bewirkt:** Definiert den Textlabel für den *ursprünglichen* Preis inklusive Steuern, besonders nützlich, wenn spezifische Preise oder Rabatte angewendet werden.
    -   **Auswirkung der Änderung dieser Einstellung:** Ändert den Labeltext.
    -   **Empfohlener Wert:** „Original inkl. MwSt.“
    -   **Händlerszenario / Beispiel:** Wenn ein Produkt im Angebot ist, möchten Sie möglicherweise den Originalpreis mit einem spezifischen Label anzeigen.

#### Produktlistenseiten-Einstellungen

-   **Auf Produktliste anzeigen (BF\_PL)**

    -   **Was diese Einstellung bewirkt:** Steuert, ob sowohl Preise inklusive als auch exklusive Steuern auf Produktlistenseiten (Kategorien, Suchergebnisse, Startseitenmodule) angezeigt werden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Beide Preise erscheinen auf den Produktlistenseiten.
        -   *Wenn deaktiviert:* Nur der Standard-PrestaShop-Preis wird auf den Produktlistenseiten angezeigt.
    -   **Empfohlener Wert:** Ein (für konsistente Transparenz).
    -   **Händlerszenario / Beispiel:** Wenn Ihre Kategorieseiten sehr dicht sind, könnten Sie dies deaktivieren, um die visuelle Unordnung zu reduzieren.
-   **Preis inkl. Steuern auf Produktliste ausblenden (BOTH\_HIDE\_PL)**

    -   **Was diese Einstellung bewirkt:** Wenn „Auf Produktliste anzeigen“ aktiviert ist, können Sie mit dieser Option den Preis inklusive Steuern auf Listenseiten ausblenden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Der Preis inklusive Steuern wird auf den Produktlistenseiten ausgeblendet.
        -   *Wenn deaktiviert:* Der Preis inklusive Steuern ist auf den Produktlistenseiten sichtbar.
    -   **Empfohlener Wert:** Aus (es sei denn, Sie haben einen spezifischen Grund, ihn auszublenden).
    -   **Händlerszenario / Beispiel:** Ein B2B-Shop möchte möglicherweise nur Preise exklusive Steuern auf allen Produktlisten anzeigen.
-   **Benutzerdefiniertes CSS für Produktliste (BF\_PLC)**

    -   **Was diese Einstellung bewirkt:** Ermöglicht das Hinzufügen benutzerdefinierter CSS-Regeln speziell für die doppelte Preisanzeige auf Produktlistenseiten.
    -   **Auswirkung der Änderung dieser Einstellung:** Jeder hier eingegebene CSS-Code wird auf die Preiselemente des Moduls auf den Listenseiten angewendet.
    -   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Styling-Anforderungen.
    -   **Händlerszenario / Beispiel:** Sie möchten, dass der Preis exklusive Steuern auf Kategorieseiten kleiner und ausgegraut ist, um den primären Preis (inklusive Steuern) stärker hervorzuheben.
-   **Label für Preis inkl. Steuern (BP\_TINL)**

    -   **Was diese Einstellung bewirkt:** Definiert den Textlabel, der neben dem Preis inklusive Steuern auf Produktlistenseiten angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:** Ändert den Labeltext.
    -   **Empfohlener Wert:** „inkl. MwSt.“ oder „inkl. USt.“
    -   **Händlerszenario / Beispiel:** Sie könnten ein kürzeres Label wie „inkl.“ auf Listenseiten verwenden, da der Platz begrenzt ist.
-   **Label für Preis exkl. Steuern (BP\_TEXL)**

    -   **Was diese Einstellung bewirkt:** Definiert den Textlabel, der neben dem Preis exklusive Steuern auf Produktlistenseiten angezeigt wird.
    -   **Auswirkung der Änderung dieser Einstellung:** Ändert den Labeltext.
    -   **Empfohlener Wert:** „exkl. MwSt.“ oder „exkl. USt.“
    -   **Händlerszenario / Beispiel:** Sie könnten ein kürzeres Label wie „exkl.“ auf Listenseiten verwenden.

#### Sichtbarkeitsregeln

-   **Sichtbarkeitsregel (bp\_visibility\_rule)**

    -   **Was diese Einstellung bewirkt:** Bestimmt, wie sich die doppelte Preisanzeige basierend auf Kundengruppen, spezifischen Produkten oder Kategorien verhält.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Immer anzeigen:* Doppelte Preise werden immer für alle Kunden, Produkte und Kategorien angezeigt.
        -   *Für ausgewählte Gruppen/Produkte/Kategorien ausblenden:* Doppelte Preise werden für spezifische Auswahlen ausgeblendet.
        -   *Nur für ausgewählte Gruppen/Produkte/Kategorien anzeigen:* Doppelte Preise werden nur für spezifische Auswahlen angezeigt.
    -   **Empfohlener Wert:** Immer anzeigen (für maximale Transparenz) oder „Nur für ausgewählte Gruppen anzeigen“, wenn Sie speziell B2B-Kunden ansprechen.
    -   **Händlerszenario / Beispiel:** Sie könnten „Nur für ausgewählte Gruppen anzeigen“ wählen und dann Ihre Kundengruppe „Großhandelskunden“ auswählen, um doppelte Preise nur für Ihre B2B-Kunden anzuzeigen.
-   **Sichtbarkeit für Kundengruppen (actionAdminGroupsControllerSaveAfter)**

    -   **Was diese Einstellung bewirkt:** Ermöglicht die Auswahl, welche Kundengruppen die doppelte Preisanzeige sehen sollen, basierend auf der oben genannten „Sichtbarkeitsregel“.
    -   **Auswirkung der Änderung dieser Einstellung:** Nur Kunden, die zu den ausgewählten Gruppen gehören, sehen die doppelten Preise (wenn die Regel „Nur für ausgewählte Gruppen anzeigen“ ist) oder sehen sie *nicht* (wenn die Regel „Für ausgewählte Gruppen ausblenden“ ist).
    -   **Empfohlener Wert:** Wählen Sie „Alle Kundengruppen“, wenn Ihre Regel „Immer anzeigen“ ist. Andernfalls wählen Sie die relevanten Gruppen aus.
    -   **Händlerszenario / Beispiel:** Wenn Sie möchten, dass nur Ihre Gruppen „Gast“ und „Kunde“ hauptsächlich Preise inklusive Steuern sehen, aber „Großhandel“ beide, würden Sie die Regel auf „Nur für ausgewählte Gruppen anzeigen“ setzen und „Großhandel“ auswählen.
-   **Sichtbarkeit für Produkte (bp\_visibility\_products)**

    -   **Was diese Einstellung bewirkt:** Ermöglicht die Angabe einzelner Produkte, für die die doppelte Preisanzeige gelten (oder nicht gelten) soll, basierend auf der „Sichtbarkeitsregel“. Dies verwendet ein Autocomplete-Suchfeld.
    -   **Auswirkung der Änderung dieser Einstellung:** Die doppelte Preisanzeige wird für die ausgewählten Produkte gemäß Ihrer gewählten Sichtbarkeitsregel aktiviert oder deaktiviert.
    -   **Empfohlener Wert:** Leer lassen, wenn es für alle Produkte gelten soll.
    -   **Händlerszenario / Beispiel:** Sie haben möglicherweise einige spezifische Produkte, bei denen die Anzeige beider Preise verwirrend ist, daher würden Sie die Regel auf „Für ausgewählte Produkte ausblenden“ setzen und diese Produkte hier hinzufügen.
-   **Sichtbarkeit für Kategorien (bp\_visibility\_cat)**

    -   **Was diese Einstellung bewirkt:** Ermöglicht die Angabe von Kategorien, für die die doppelte Preisanzeige gelten (oder nicht gelten) soll, basierend auf der „Sichtbarkeitsregel“.
    -   **Auswirkung der Änderung dieser Einstellung:** Die doppelte Preisanzeige wird für alle Produkte innerhalb der ausgewählten Kategorien gemäß Ihrer gewählten Sichtbarkeitsregel aktiviert oder deaktiviert.
    -   **Empfohlener Wert:** Leer lassen, wenn es für alle Kategorien gelten soll.
    -   **Händlerszenario / Beispiel:** Wenn Sie sowohl physische Waren (wo Steuern relevant sind) als auch digitale Produkte (wo Steuern anders gehandhabt werden könnten) verkaufen, könnten Sie doppelte Preise für Ihre Kategorie „Digitale Downloads“ ausblenden.

#### Anzeigeoptionen

-   **Preistypen anzeigen (BF\_SHOW\_TYPES)**

    -   **Was diese Einstellung bewirkt:** Bestimmt, welche Preistypen angezeigt werden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Inkl. Steuern und Exkl. Steuern:* Zeigt beide Preise an.
        -   *Nur inkl. Steuern:* Zeigt nur den Preis inklusive Steuern an (Modul verarbeitet weiterhin, zeigt aber nur einen an).
        -   *Nur exkl. Steuern:* Zeigt nur den Preis exklusive Steuern an.
    -   **Empfohlener Wert:** Inkl. Steuern und Exkl. Steuern (um die Kernfunktion des Moduls zu nutzen).
    -   **Händlerszenario / Beispiel:** Wenn Ihr Hauptziel darin besteht, B2B-Kunden Preise exklusive Steuern anzuzeigen, könnten Sie „Nur exkl. Steuern“ in Verbindung mit einer Sichtbarkeitsregel für Kundengruppen auswählen.
-   **Classic Theme CSS verwenden (BF\_CLASSICCSS)**

    -   **Was diese Einstellung bewirkt:** Wenn Ihr Theme auf dem Standard-PrestaShop Classic Theme basiert, wird durch Aktivierung dieser Option spezifische CSS-Regeln angewendet, die für eine reibungslose Integration mit dem Styling dieses Themes entwickelt wurden.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Wenn aktiviert:* Das Modul lädt ein dediziertes Stylesheet (`classic.css`), um eine bessere visuelle Integration mit Classic-basierten Themes zu gewährleisten.
        -   *Wenn deaktiviert:* Das Modul verwendet sein Standard-Styling, was möglicherweise benutzerdefiniertes CSS für eine perfekte Integration mit Nicht-Classic-Themes erfordert.
    -   **Empfohlener Wert:** Aktivieren, wenn Ihr Theme Classic-basiert oder ein Child-Theme von Classic ist. Andernfalls deaktivieren.
    -   **Händlerszenario / Beispiel:** Wenn Sie das Modul gerade installiert haben und die Preise auf Ihrem Classic Theme falsch ausgerichtet aussehen, könnte das Aktivieren dieser Option das Problem beheben.
-   **Eigenes CSS (BF\_OWNCSS)**

    -   **Was diese Einstellung bewirkt:** Bietet ein Textfeld, in das Sie Ihren eigenen benutzerdefinierten CSS-Code eingeben können, um Stile der Modulausgabe zu überschreiben oder hinzuzufügen. Dies ist für fortgeschrittene Benutzer oder Webmaster.
    -   **Auswirkung der Änderung dieser Einstellung:** Jeder hier eingegebene CSS-Code wird global auf die Preisanzeigen des Moduls angewendet, was eine vollständige Kontrolle über das Styling ermöglicht.
    -   **Empfohlener Wert:** Leer lassen, es sei denn, Sie haben spezifische Styling-Anforderungen.
    -   **Händlerszenario / Beispiel:** Sie möchten die Schriftgröße der angezeigten Preise ändern oder einen Rahmen um sie herum hinzufügen, um sie prominenter zu machen.

#### Erweiterte Einstellungen

-   **Steuerprozentsatz auf Produktseite (BP\_PP\_TPERCENT)**

    -   **Was diese Einstellung bewirkt:** Ermöglicht die Anzeige des Steuerprozentsatzes auf Produktseiten.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Ein:* Der Steuerprozentsatz (z. B. „20% MwSt.“) wird neben den Preisen angezeigt.
        -   *Aus:* Der Steuerprozentsatz wird nicht angezeigt.
    -   **Empfohlener Wert:** Aus (es sei denn, Sie möchten den Steuersatz explizit anzeigen).
    -   **Händlerszenario / Beispiel:** In Ländern, in denen Kunden sehr steuerbewusst sind, kann die Anzeige des Prozentsatzes eine weitere Ebene der Transparenz hinzufügen.
-   **Steuerprozentsatz auf Produktseite (exkl. Steuern) (BP\_PP\_TPERCENT\_TEXL)**

    -   **Was diese Einstellung bewirkt:** Ähnlich wie oben, aber speziell für die Preisanzeige exklusive Steuern auf Produktseiten.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Ein:* Der Steuerprozentsatz wird neben dem Preis exklusive Steuern angezeigt.
        -   *Aus:* Der Steuerprozentsatz wird nicht angezeigt.
    -   **Empfohlener Wert:** Aus.
    -   **Händlerszenario / Beispiel:** Nützlich, wenn Sie den Steuersatz hervorheben möchten, der ausgeschlossen wird.
-   **Steuerprozentsatz auf Produktliste (BP\_PL\_TPERCENT)**

    -   **Was diese Einstellung bewirkt:** Ermöglicht die Anzeige des Steuerprozentsatzes auf Produktlistenseiten.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Ein:* Der Steuerprozentsatz wird neben den Preisen auf Listenseiten angezeigt.
        -   *Aus:* Der Steuerprozentsatz wird nicht angezeigt.
    -   **Empfohlener Wert:** Aus (um Listenseiten übersichtlicher zu halten).
    -   **Händlerszenario / Beispiel:** Wenn Ihre Produktlisten nicht zu überladen sind, kann die Anzeige des Steuerprozentsatzes informativ sein.
-   **Steuerprozentsatz auf Produktliste (exkl. Steuern) (BP\_PL\_TPERCENT\_TEXL)**

    -   **Was diese Einstellung bewirkt:** Ähnlich wie oben, aber speziell für die Preisanzeige exklusive Steuern auf Produktlistenseiten.
    -   **Auswirkung der Änderung dieser Einstellung:**
        -   *Ein:* Der Steuerprozentsatz wird neben dem Preis exklusive Steuern auf Listenseiten angezeigt.
        -   *Aus:* Der Steuerprozentsatz wird nicht angezeigt.
    -   **Empfohlener Wert:** Aus.
    -   **Händlerszenario / Beispiel:** Weniger verbreitet, könnte aber verwendet werden, um die Steuerkomponente hervorzuheben, die entfernt wird.

#### Spracheinstellungen (Intern)

-   **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**
    -   **Was diese Einstellung bewirkt:** Dies sind interne PrestaShop-Einstellungen, die sich auf die Standardsprache und die Sprache des Mitarbeiterformulars beziehen. Sie werden hier zu Informationszwecken angezeigt und sind nicht direkt über das Modul konfigurierbar.
    -   **Auswirkung der Änderung dieser Einstellung:** Nicht zutreffend, dies sind schreibgeschützte Werte aus Ihrer PrestaShop-Konfiguration.
    -   **Empfohlener Wert:** N/A
    -   **Händlerszenario / Beispiel:** Diese Werte helfen dem Modul zu bestimmen, welche Sprache für Labels verwendet werden soll, wenn Sie diese nicht explizit für alle Sprachen festgelegt haben.

### 2.2 Dedizierte Admin-Bildschirme & Controller-Ansichten

#### AdminBothpricesSearchController (Back Office > Module > Zwei Preise anzeigen – inkl. / exkl. Steuern > Produkte suchen)

Dieser dedizierte Admin-Bildschirm wird zur Verwaltung der Einstellung „Sichtbarkeit für Produkte“ verwendet. Er bietet eine Schnittstelle zum Suchen und Auswählen spezifischer Produkte, die von den Sichtbarkeitsregeln des Moduls betroffen sein sollen.

-   **Bildschirmname & Menüpfad:** Sie können auf diesen Bildschirm zugreifen, indem Sie auf den Link oder die Schaltfläche „Produkte suchen“ auf der Hauptkonfigurationsseite des Moduls klicken, normalerweise neben der Einstellung „Sichtbarkeit für Produkte“.
-   **Verfügbare Aktionen & Einstellungen:**
    -   **Produktsuchfeld:** Ein Texteingabefeld, in das Sie Produktnamen oder IDs eingeben können, um bestimmte Produkte zu finden.
    -   **Suchergebnisraster:** Zeigt eine Liste der Produkte an, die Ihrer Suchanfrage entsprechen.
    -   **Hinzufügen/Entfernen-Schaltflächen:** Ermöglicht das Hinzufügen oder Entfernen ausgewählter Produkte aus der Liste der Produkte, die von der Sichtbarkeitsregel betroffen sind.
    -   **Liste der ausgewählten Produkte:** Zeigt alle Produkte an, die derzeit für die Sichtbarkeitsregel konfiguriert sind.
-   **Auswirkung von Änderungen:**
    -   Das Hinzufügen eines Produkts zur Liste bedeutet, dass die doppelte Preisanzeige des Moduls entweder *nur* für dieses Produkt angezeigt oder *für dieses Produkt ausgeblendet* wird, abhängig von Ihrer allgemeinen Einstellung „Sichtbarkeitsregel“.
    -   Das Entfernen eines Produkts bedeutet, dass es nicht mehr spezifisch von der produktbezogenen Sichtbarkeitsregel betroffen ist und zu den allgemeinen Moduleinstellungen zurückkehrt.
-   **Empfohlener Workflow für die tägliche Shop-Verwaltung:**
    1.  Gehen Sie zur Hauptkonfigurationsseite des Moduls.
    2.  Legen Sie Ihre „Sichtbarkeitsregel“ fest (z. B. „Für ausgewählte Produkte ausblenden“).
    3.  Klicken Sie auf den Link/die Schaltfläche, um den Bildschirm „AdminBothpricesSearchController“ zu öffnen.
    4.  Verwenden Sie das Suchfeld, um die Produkte zu finden, die Sie in die Regel aufnehmen möchten.
    5.  Fügen Sie sie zur „Liste der ausgewählten Produkte“ hinzu.
    6.  Speichern Sie Ihre Änderungen auf der Hauptkonfigurationsseite des Moduls.

### 2.3 Konfigurations-Schnellreferenztabelle

| Bildschirm / Ansicht | Einstellung / Option | Standard / Empfohlen | Zweck & Auswirkung |
| --- | --- | --- | --- |
| Modulkonfiguration | Aktiviert / Deaktiviert | Aktiviert | Hauptschalter für die Modulfunktionalität. |
| Modulkonfiguration | Auf Produktseite anzeigen (BF\_PP) | Ein | Zeigt doppelte Preise auf Produktdetailseiten an. |
| Modulkonfiguration | Preis inkl. Steuern auf Produktseite ausblenden (BOTH\_HIDE\_P) | Aus | Blendet den Preis inkl. Steuern auf Produktseiten aus. |
| Modulkonfiguration | Benutzerdefiniertes CSS für Produktseite (BF\_PPC) | Leer | Benutzerdefiniertes CSS für die Preisanzeige auf Produktseiten. |
| Modulkonfiguration | Produktseite erzwingen ausblenden (BP\_FORCE\_HIDE) | Aus | Blendet die Modulausgabe auf der Produktseite zwangsweise aus. |
| Modulkonfiguration | Label für Preis inkl. Steuern (BP\_TIN) | „inkl. MwSt.“ | Label für den Preis inkl. Steuern auf der Produktseite. |
| Modulkonfiguration | Label für Preis exkl. Steuern (BP\_TEX) | „exkl. MwSt.“ | Label für den Preis exkl. Steuern auf der Produktseite. |
| Modulkonfiguration | Label für Originalpreis inkl. Steuern (BP\_O\_TIN) | „Original inkl. MwSt.“ | Label für den Originalpreis inkl. Steuern auf der Produktseite. |
| Modulkonfiguration | Auf Produktliste anzeigen (BF\_PL) | Ein | Zeigt doppelte Preise auf Kategorie-/Listenseiten an. |
| Modulkonfiguration | Preis inkl. Steuern auf Produktliste ausblenden (BOTH\_HIDE\_PL) | Aus | Blendet den Preis inkl. Steuern auf Listenseiten aus. |
| Modulkonfiguration | Benutzerdefiniertes CSS für Produktliste (BF\_PLC) | Leer | Benutzerdefiniertes CSS für die Preisanzeige auf Listenseiten. |
| Modulkonfiguration | Label für Preis inkl. Steuern (BP\_TINL) | „inkl. MwSt.“ | Label für den Preis inkl. Steuern auf Listenseiten. |
| Modulkonfiguration | Label für Preis exkl. Steuern (BP\_TEXL) | „exkl. MwSt.“ | Label für den Preis exkl. Steuern auf Listenseiten. |
| Modulkonfiguration | Sichtbarkeitsregel (bp\_visibility\_rule) | Immer anzeigen | Definiert, wie Sichtbarkeitsregeln angewendet werden (anzeigen/ausblenden für ausgewählte). |
| Modulkonfiguration | Sichtbarkeit für Kundengruppen | Alle Kundengruppen | Wählt Kundengruppen aus, die von der Sichtbarkeitsregel betroffen sind. |
| Modulkonfiguration | Sichtbarkeit für Produkte (bp\_visibility\_products) | Leer | Wählt spezifische Produkte aus, die von der Sichtbarkeitsregel betroffen sind. |
| Modulkonfiguration | Sichtbarkeit für Kategorien (bp\_visibility\_cat) | Leer | Wählt spezifische Kategorien aus, die von der Sichtbarkeitsregel betroffen sind. |
| Modulkonfiguration | Preistypen anzeigen (BF\_SHOW\_TYPES) | Inkl. Steuern und Exkl. Steuern | Bestimmt, welche Preistypen angezeigt werden (beide, nur inkl., nur exkl.). |
| Modulkonfiguration | Classic Theme CSS verwenden (BF\_CLASSICCSS) | Aus (Für Classic Themes aktivieren) | Wendet Classic Theme spezifisches Styling an. |
| Modulkonfiguration | Eigenes CSS (BF\_OWNCSS) | Leer | Globales benutzerdefiniertes CSS für die Modulausgabe. |
| Modulkonfiguration | Steuerprozentsatz auf Produktseite (BP\_PP\_TPERCENT) | Aus | Zeigt den Steuerprozentsatz auf Produktseiten an. |
| Modulkonfiguration | Steuerprozentsatz auf Produktseite (exkl. Steuern) (BP\_PP\_TPERCENT\_TEXL) | Aus | Zeigt den Steuerprozentsatz für den Preis exkl. Steuern auf Produktseiten an. |
| Modulkonfiguration | Steuerprozentsatz auf Produktliste (BP\_PL\_TPERCENT) | Aus | Zeigt den Steuerprozentsatz auf Listenseiten an. |
| Modulkonfiguration | Steuerprozentsatz auf Produktliste (exkl. Steuern) (BP\_PL\_TPERCENT\_TEXL) | Aus | Zeigt den Steuerprozentsatz für den Preis exkl. Steuern auf Listenseiten an. |
| AdminBothpricesSearchController | Produktsuche / Hinzufügen/Entfernen | N/A | Verwaltet die Produktliste für Sichtbarkeitsregeln. |

## 3. Händler-Fehlerbehebung & Häufig gestellte Fragen (FAQ)

**F1: Das Modul ist aktiviert, aber ich sehe keine zwei Preise in meinem Shop.**
A:

-   **Globale Aktivierung prüfen:** Stellen Sie sicher, dass der Hauptschalter „Aktiviert / Deaktiviert“ oben in der Modulkonfiguration auf „Aktiviert“ steht.
-   **Seiten-spezifische Einstellungen prüfen:** Überprüfen Sie, ob „Auf Produktseite anzeigen“ (BF\_PP) und/oder „Auf Produktliste anzeigen“ (BF\_PL) aktiviert sind, je nachdem, wo Sie die Preise erwarten.
-   **Sichtbarkeitsregeln prüfen:** Wenn Sie eine „Sichtbarkeitsregel“ festgelegt haben, stellen Sie sicher, dass Ihre aktuelle Kundengruppe, Ihr Produkt oder Ihre Kategorie in der „Anzeigen“-Regel enthalten oder nicht durch eine „Ausblenden“-Regel ausgeschlossen ist.
-   **Cache leeren:** Leeren Sie immer Ihren PrestaShop-Cache (Erweiterte Einstellungen > Leistung > Cache leeren), nachdem Sie Modulkonfigurationsänderungen vorgenommen haben. Leeren Sie auch den Cache Ihres Browsers.
-   **Theme-Konflikte:** Einige stark angepasste Themes können Konflikte verursachen. Versuchen Sie, vorübergehend zum Standard-PrestaShop Classic Theme zu wechseln, um zu sehen, ob die Preise erscheinen. Wenn ja, handelt es sich um einen Theme-bezogenen CSS- oder JS-Konflikt.

**F2: Die Preise werden angezeigt, aber sie sehen falsch ausgerichtet aus oder haben ein falsches Styling.**
A:

-   **Classic Theme CSS verwenden:** Wenn Ihr Theme auf dem Standard-PrestaShop Classic Theme basiert, versuchen Sie, die Option „Classic Theme CSS verwenden (BF\_CLASSICCSS)“ in der Modulkonfiguration zu aktivieren.
-   **Benutzerdefiniertes CSS:** Wenn Sie ein benutzerdefiniertes Theme haben, müssen Sie möglicherweise benutzerdefiniertes CSS hinzufügen. Verwenden Sie die Entwicklertools Ihres Browsers (F12), um die CSS-Klassen der Preiselemente des Moduls zu identifizieren. Verwenden Sie dann das Feld „Eigenes CSS (BF\_OWNCSS)“ in der Modulkonfiguration, um Ihre Styling-Regeln hinzuzufügen.
-   **Modulposition:** Stellen Sie sicher, dass das Modul korrekt eingehängt ist. Obwohl das Modul die meisten Hooks automatisch verarbeitet, können manchmal Theme-spezifische Hooks erforderlich sein.

**F3: Die Preise werden nicht aktualisiert, wenn ich Produktattribute (z. B. Größe, Farbe) auf der Produktseite ändere.**
A:

-   **Modulkompatibilität:** Stellen Sie sicher, dass Ihre PrestaShop-Version innerhalb des unterstützten Bereichs liegt.
-   **JavaScript-Konflikte:** Dies wird oft durch JavaScript-Konflikte mit Ihrem Theme oder einem anderen Modul verursacht. Überprüfen Sie die Konsole Ihres Browsers (F12 > Registerkarte Konsole) auf JavaScript-Fehler beim Ändern von Attributen.
-   **Theme-Overrides:** Wenn Ihr Theme das Standard-JavaScript der PrestaShop-Produktseite stark überschreibt, kann dies das Modul daran hindern, Preisänderungen zu erkennen. Wenden Sie sich an Ihren Theme-Entwickler oder einen Webmaster, um Unterstützung zu erhalten.
-   **Cache leeren:** Leeren Sie den PrestaShop- und Browser-Cache.

**F4: Wie übersetze ich die Preisbezeichnungen (z. B. „inkl. MwSt.“, „exkl. MwSt.“) in andere Sprachen?**
A:

-   Gehen Sie in Ihrem PrestaShop Back Office zu **International > Übersetzungen**.
-   Wählen Sie „Übersetzungen installierter Module“.
-   Wählen Sie Ihr Theme.
-   Wählen Sie Ihre Sprache.
-   Suchen Sie das Modul „Zwei Preise anzeigen – inkl. / exkl. Steuern“ in der Liste.
-   Sie finden Felder für „Label für Preis inkl. Steuern“, „Label für Preis exkl. Steuern“ usw. für Produkt- und Listenseiten. Geben Sie dort Ihre Übersetzungen ein und speichern Sie.

**F5: Ich möchte Preise exklusive Steuern nur bestimmten Kundengruppen (z. B. B2B) anzeigen. Wie mache ich das?**
A:

-   Stellen Sie in der Modulkonfiguration die **„Sichtbarkeitsregel“** auf „Nur für ausgewählte Gruppen anzeigen“.
-   Wählen Sie dann die spezifischen Kundengruppe(n) (z. B. „Großhandel“, „B2B“) aus, die die doppelten Preise sehen sollen.
-   Optional können Sie **„Preistypen anzeigen“** auf „Nur exkl. Steuern“ setzen, wenn Sie den Preis inklusive Steuern für diese Gruppen vollständig ausblenden möchten.

## 4. Entwickler- & Webmaster-Handbuch (Technische Architektur & Code-Map)

### 4.1 Architekturübersicht

Das Modul „Zwei Preise anzeigen – inkl. / exkl. Steuern“ (`bothprices`) ist ein Standard-PrestaShop-Modul, das dem MVC-Muster folgt. Es erweitert hauptsächlich die Klasse `Module` und nutzt das PrestaShop-Hook-System, um Preisinformationen einzufügen und die Anzeige zu ändern. Es verwendet einen dedizierten Admin-Controller für die Produktsuchfunktion und Front-Controller für AJAX-Interaktionen. Das Modul basiert auf Smarty-Templates für das Rendering und benutzerdefiniertem JavaScript/CSS für dynamische Updates und Styling. Die Konfiguration wird in `ps_configuration` gespeichert.

### 4.2 Controller (`controllers/`)

-   **Front-Office-Controller**:

    -   `controllers/front/ajax.php`
        -   **Klassenname & Elternklasse**: `BothpricesAjaxModuleFrontController` erweitert `ModuleFrontController`.
        -   **Verantwortlichkeit**: Verarbeitet AJAX-Anfragen vom Front-Office, hauptsächlich zur dynamischen Aktualisierung von Preisen, wenn Produktattribute geändert werden. Es ruft wahrscheinlich Produktinformationen ab und berechnet Preise basierend auf ausgewählten Attributen und dem Kundenkontext, wobei JSON-Daten zurückgegeben werden.
    -   `controllers/front/index.php`
        -   **Klassenname & Elternklasse**: `BothpricesIndexModuleFrontController` erweitert `ModuleFrontController`.
        -   **Verantwortlichkeit**: Dies ist ein Platzhalter- oder Fallback-Controller. In vielen Modulen werden `index.php`-Controller für grundlegendes Routing oder zur Verhinderung von Verzeichnislisten verwendet. Er hat möglicherweise keine signifikante benutzerdefinierte Logik über die grundlegende Weiterleitung hinaus.
-   **Back-Office-Admin-Controller**:

    -   `controllers/admin/AdminBothpricesSearchController.php`
        -   **Klassenname & Elternklasse**: `AdminBothpricesSearchController` erweitert `ModuleAdminController`.
        -   **Tab-Name und verwaltete Entität**: Dieser Controller verwaltet die Produktsuche und -auswahl für die Sichtbarkeitsregeln des Moduls. Er verwaltet nicht direkt eine spezifische `ObjectModel`, sondern interagiert mit `Product`-Daten zur Auswahl. Er bietet eine gitterartige Oberfläche zum Suchen und Hinzufügen/Entfernen von Produkten aus der Konfiguration `bp_visibility_products`.

### 4.3 Kernklassen & Modelle (`classes/`)

Das Modul scheint keine benutzerdefinierten `ObjectModel`-Klassen im Verzeichnis `classes/` zu definieren. Es stützt sich wahrscheinlich auf vorhandene PrestaShop `Product`- und `Configuration`-Klassen.

### 4.4 JavaScript-Assets (`views/js/`)

-   `bothprices/lib/searchTool/views/js/autocomplete.js`
    -   **Geltungsbereich**: Back-Office.
    -   **Beschreibung**: Bietet Autocomplete-Funktionalität für das Produktsuchfeld innerhalb von `AdminBothpricesSearchController`, sodass Administratoren schnell Produkte für Sichtbarkeitsregeln finden und auswählen können.
-   `bothprices/views/js/both-hide-p.js`
    -   **Geltungsbereich**: Front-Office (Produktseite).
    -   **Beschreibung**: Enthält JavaScript-Logik zum Ausblenden des Preises inklusive Steuern speziell auf der Produktseite, basierend auf der Konfigurationseinstellung `BOTH_HIDE_P`. Es zielt wahrscheinlich auf spezifische DOM-Elemente ab, um `display: none` oder ähnliches Styling anzuwenden.
-   `bothprices/views/js/both-hide-pl.js`
    -   **Geltungsbereich**: Front-Office (Produktlistenseiten).
    -   **Beschreibung**: Ähnlich wie `both-hide-p.js`, aber für Produktlistenseiten, blendet den Preis inklusive Steuern basierend auf der Konfiguration `BOTH_HIDE_PL` aus.
-   `bothprices/views/js/bothprices-admin.js`
    -   **Geltungsbereich**: Back-Office.
    -   **Beschreibung**: Enthält allgemeines JavaScript für die Back-Office-Konfigurationsseite des Moduls. Dies kann Logik zum Anzeigen/Ausblenden von Konfigurationsfeldern basierend auf anderen Auswahlen (z. B. Änderungen der Sichtbarkeitsregel), Formularvalidierung oder AJAX-Aufrufe zum Speichern von Einstellungen umfassen.
-   `bothprices/views/js/bothprices.js`
    -   **Geltungsbereich**: Front-Office (Global).
    -   **Beschreibung**: Dies ist die Haupt-JavaScript-Datei des Front-Office. Sie ist verantwortlich für:
        -   Das Abhören von `prestashop.on('updateProduct', ...)` oder ähnlichen Ereignissen, um Änderungen an Produktattributen zu erkennen.
        -   Das Ausführen von AJAX-Aufrufen an `controllers/front/ajax.php`, um aktualisierte doppelte Preise abzurufen.
        -   Das dynamische Aktualisieren der angezeigten Preise inklusive und exklusive Steuern auf der Produktseite und möglicherweise auf Listenseiten.
        -   Das Anwenden von benutzerdefiniertem CSS oder Klassen basierend auf Moduleinstellungen.

### 4.5 CSS-Stylesheets (`views/css/`)

-   `bothprices/lib/searchTool/views/css/autocomplete.css`
    -   **Geltungsbereich**: Back-Office.
    -   **Beschreibung**: Stile für das Autocomplete-Dropdown und die Suchergebnisse innerhalb der `AdminBothpricesSearchController`-Oberfläche.
-   `bothprices/views/css/admin.css`
    -   **Geltungsbereich**: Back-Office.
    -   **Beschreibung**: Allgemeines Styling für die Konfigurationsseite des Moduls im PrestaShop Back Office, um ein konsistentes Erscheinungsbild mit dem Admin-Panel zu gewährleisten.
-   `bothprices/views/css/bothprices.css`
    -   **Geltungsbereich**: Front-Office (Global).
    -   **Beschreibung**: Enthält die Standard-CSS-Regeln für die Anzeige der doppelten Preise auf Produktseiten und Listenseiten. Dies umfasst grundlegende Formatierung, Positionierung und Differenzierung der beiden Preiselemente.
    -   **Wichtige CSS-Klassenselektoren**: Entwickler können nach Klassen wie `.bothprices_price_tax_incl`, `.bothprices_price_tax_excl`, `.bothprices_wrapper` suchen, um sie zu überschreiben.
-   `bothprices/views/css/classic.css`
    -   **Geltungsbereich**: Front-Office (Classic Theme spezifisch).
    -   **Beschreibung**: Enthält zusätzliche oder überschreibende CSS-Regeln, die speziell entwickelt wurden, um die visuelle Integration mit dem Standard-PrestaShop Classic Theme oder darauf basierenden Themes zu verbessern. Diese Datei wird bedingt basierend auf der Einstellung `BF_CLASSICCSS` geladen.

### 4.6 Smarty-Template-Struktur (`views/templates/`)

-   **Hook-Templates (`views/templates/hook/`)**:
    -   `bothprices/views/templates/bothprices.tpl`
        -   **Hook**: Wahrscheinlich in Hooks wie `displayProductPriceBlock`, `displayProductListReviews`, `displayProductPriceBlock`, `displayProductPriceBlock`, `displayAfterProductThumbs` oder ähnlichen auf Produkt- und Listenseiten gerendert.
        -   **Ausgabe**: Dieses Template ist für das Rendern der tatsächlichen HTML-Struktur der doppelten Preisanzeige (Preise inklusive und exklusive Steuern) zusammen mit ihren Labels verantwortlich. Es empfängt Preisvariablen aus der PHP-Logik des Moduls.
-   **Admin-Templates (`views/templates/admin/`)**:
    -   `bothprices/views/templates/admin/configure_shell.tpl`
        -   **Hook**: Wird innerhalb der `getContent()`-Methode des Moduls für die Hauptkonfigurationsseite gerendert.
        -   **Ausgabe**: Dies dient als Wrapper oder Shell für das Konfigurationsformular des Moduls, das möglicherweise Tabs, Header und Footer für die Admin-Oberfläche enthält.
    -   `bothprices/views/templates/selectedProducts.tpl`
        -   **Hook**: Wird von `AdminBothpricesSearchController` verwendet.
        -   **Ausgabe**: Rendert die Liste der Produkte, die für die Sichtbarkeitsregeln ausgewählt wurden, typischerweise in Tabellen- oder Listenform innerhalb der Admin-Suchoberfläche.
-   **Front-Office-Templates (`views/templates/front/`)**:
    -   `bothprices/views/templates/bothprices-product-page.tpl`
        -   **Hook**: Wahrscheinlich auf der Produktseite gerendert, möglicherweise innerhalb von `displayProductPriceBlock` oder ähnlichem.
        -   **Ausgabe**: Ein spezifisches Template für die doppelte Preisanzeige der Produktseite, möglicherweise mit detaillierteren Informationen oder einem anderen Layout im Vergleich zu Listenseiten.
-   **Bibliotheks-Templates (`lib/searchTool/views/scripts.tpl`)**:
    -   `bothprices/lib/searchTool/views/scripts.tpl`
        -   **Hook**: Wahrscheinlich in der `AdminBothpricesSearchController`-Ansicht enthalten.
        -   **Ausgabe**: Enthält JavaScript-Initialisierungsskripte oder Konfigurationsvariablen für das Autocomplete-Suchwerkzeug.

### 4.7 Datenbankschema & Hooks-Map

-   **Datenbanktabellen**:

    -   Das Modul verwendet hauptsächlich die PrestaShop-Tabelle `ps_configuration`, um seine Einstellungen zu speichern. Konfigurationsschlüssel umfassen: `mypresta_updates`, `update_`, `updatev_`, `BOTH_HIDE_PL_CSS`, `BOTH_HIDE_P_CSS`, `BF_PP`, `BF_PL`, `bp_visibility_rule`, `bp_visibility_products`, `bp_visibility_cat`, `BF_SHOW_TYPES`, `BF_PLC`, `BF_PPC`, `BP_FORCE_HIDE`, `BP_PP_TPERCENT_TEXL`, `BP_PP_TPERCENT`, `BP_PL_TPERCENT_TEXL`, `BP_PL_TPERCENT`, `BOTH_HIDE_PL`, `BOTH_HIDE_P`, `BF_OWNCSS`, `BF_CLASSICCSS`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `BP_TIN`, `BP_TIN_L`, `BP_TEX`, `BP_TEX_L`, `BP_TINL`, `BP_TINL_L`, `BP_TEXL`, `BP_TEXL_L`, `BP_O_TIN`, `BP_O_TIN_L`, `BP_O_TEX`.
    -   Es scheint keine benutzerdefinierten SQL-Tabellen zu erstellen.
-   **Registrierte Hooks-Tabelle**:

| Hook-Name | Geltungsbereich | Ausführungszeitpunkt | Technischer Zweck |
| --- | --- | --- | --- |
| `ActionFrontControllerSetMedia` | Front-Office | Vor der Controller-Ausgabe, nach der Medieninitialisierung. | Fügt die CSS- und JS-Assets des Moduls in das Front-Office ein. |
| `ActionAdminGroupsControllerSaveAfter` | Back-Office | Nachdem ein Administrator eine Kundengruppe gespeichert hat. | Wird möglicherweise verwendet, um den Cache zu leeren oder Sichtbarkeitsregeln in Bezug auf Kundengruppen neu zu bewerten. |
| `ActionAdminControllerSetMedia` | Back-Office | Vor der Admin-Controller-Ausgabe, nach der Medieninitialisierung. | Fügt die CSS- und JS-Assets des Moduls in das Back-Office ein (z. B. für die Konfigurationsseite, den Such-Controller). |
| `updateproduct` | Back-Office | Nachdem ein Produkt aktualisiert wurde. | Leert relevante Caches, bewertet produktspezifische Preisdaten neu. |
| `ActionProductDelete` | Back-Office | Nachdem ein Produkt gelöscht wurde. | Bereinigt alle modulspezifischen Daten, die mit dem gelöschten Produkt zusammenhängen (z. B. aus `bp_visibility_products`). |
| `displayUpdateProduct` | Back-Office | Auf der Produktbearbeitungsseite. | Fügt möglicherweise benutzerdefinierte Felder oder Informationen in das Produktbearbeitungsformular ein. |
| `actionProductUpdate` | Back-Office | Nachdem ein Produkt aktualisiert wurde. | Ähnlich wie `updateproduct`, stellt sicher, dass die internen Daten des Moduls Produktänderungen widerspiegeln. |
| `displayHeader` | Front-Office | Im `<head>`-Bereich jeder Front-Office-Seite. | Fügt die CSS- und JS-Assets des Moduls für die globale Verfügbarkeit ein oder rendert ein kleines Snippet. |
| `displayCategoryUpdate` | Back-Office | Auf der Kategoriebearbeitungsseite. | Fügt möglicherweise benutzerdefinierte Felder oder Informationen in das Kategoriebearbeitungsformular ein. |
| `ActionCategoryUpdate` | Back-Office | Nachdem eine Kategorie aktualisiert wurde. | Leert relevante Caches, bewertet kategoriespezifische Preisdaten neu. |
| `actionProductAdd` | Back-Office | Nachdem ein neues Produkt hinzugefügt wurde. | Initialisiert modulspezifische Daten für das neue Produkt. |
| `actionObjectSpecificPriceUpdateAfter` | Back-Office | Nachdem ein spezifischer Preis (Rabatt) aktualisiert wurde. | Stellt sicher, dass dynamische Preisberechnungen neue spezifische Preise widerspiegeln. |
| `categoryUpdate` | Back-Office | Nachdem eine Kategorie aktualisiert wurde. | Alias oder Duplikat von `ActionCategoryUpdate`. |

## 5. Offizieller Support & Updates

Für die neuesten Updates, Fehlerbehebungen und offiziellen Support für das Modul „Zwei Preise anzeigen – inkl. / exkl. Steuern“ besuchen Sie bitte Ihr Kundenkonto unter [MyPresta.eu](https://mypresta.eu/). Unser Support-Team steht Ihnen bei technischen Problemen oder Fragen zur Funktionalität des Moduls gerne zur Verfügung.

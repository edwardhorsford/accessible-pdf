---
ID: 21940
post_title: 'PDF-<em>Tags</em> in Word festlegen'
author: Stefan Brechbühl
post_excerpt: >
  Wenn die verfügbaren Werkzeuge in Word korrekt verwendet werden, verbessert sich die Ausgabequalität des exportierten PDF-Dokuments. Die Nachbearbeitung des PDFs wird dadurch reduziert. 
layout: basics
permalink: >
  https://accessible-pdf.info/de/basics/pdf-tags-in-word-festlegen/
published: true
post_date: 2018-06-19 17:24:08
---
Die Barrierefreiheit sollte bereits zu Beginn der Dokumentherstellung und nicht erst nach der PDF-Herstellung beachtetet werden. Um die Ausgabequalität eines aus Word exportierten PDF-Dokuments zu verbessern, ist es wichtig die verfügbaren Werkzeuge in Word korrekt zu verwenden. Damit erreicht man, dass eine elementare *Tag*struktur erzeugt und der Nachbearbeitungsaufwand im PDF reduziert wird.

Folgende semantische Strukturinformationen können in Word automatisch in das PDF übertragen werden:

- [Überschriften](#ueberschriften)
- [Listen](#listen)
- [Tabellen](#tabellen)
- [Fuss-/Endnoten](#noten)
- [Weitere Auszeichnungen](#weitere)

Damit diese Strukturinformationen übernommen werden, folgen am Schluss noch Informationen zu den [Exporteinstellung](#export).

## Überschriften {#ueberschriften}

Eines der wichtigsten Strukturelemente sind hierarchische Überschriften, siehe auch [„Strukturieren mithilfe von hierarchischen Überschriften“](https://accessible-pdf.info/de/basics/strukturieren-mithilfe-von-hierarchischen-ueberschriften/). Solches Strukturieren kann durch die bewusste Verwendung von Absatzformaten in Word erreicht werden. Die korrekte Verwendung führt dazu, dass Überschriften automatisch mit dem passenden *Tag* in das PDF exportiert werden.

<iframe width="750" height="422" title="YouTube video tutorial: PDF-Tags in Word festlegen" src="https://www.youtube-nocookie.com/embed/ahD5WYjfuLE?hl=de" frameborder="0" allow="encrypted-media" allowfullscreen></iframe>

Word bietet bereits einen umfangreichen Formatvorlagenkatalog, einschliesslich „Überschrift 1“ bis „Überschrift 9“. Derzeit sind in PDF nur `<H1>` bis `<H6>` als nummerierte Überschriften-*Tags* verfügbar. Daher werden die Absatzformate "Überschrift 7" bis „Überschrift 9“ mit dem allgemeinen Absatz-*Tag* (`<P>`) *getaggt*.

Wenn du möchtest, kannst du auch deine eigenen Absatzformate verwenden und ihnen die entsprechende Gliederungsebene vergeben. Somit werden auch eigene Formatvorlagen als hierarchische Überschriften *getaggt*. Werfen wir einen Blick auf diese Option.

1. Öffne den Bereich Formatvorlagen. Windows-Benutzer müssen auf ein kleines Symbol unten rechts in der Liste der Schnellformatvorlagen klicken.
2. Fahre mit der Maus über die Formatvorlage, die du ändern möchtest und klicke auf das erscheinende Dropdown-Menü.
3. Klicke auf “Formatvorlage ändern”.
4. Im Dropdown-Menü unten links kannst du zu den Absatzeinstellungen wechseln.
5. Die zweite Option unter „Allgemein“ ist die „Gliederungsstufe“. Diese wird verwendet, um das PDF-*Tag* für die Überschrift zu generieren: 
	- Textkörper = `<P>`
	- Ebene 1 = `<H1>`
	- Ebene 2 = `<H2>`
	- Ebene 3 = `<H3>`
	- usw.

![Absatzformateinstellungen mit markierter Option Gliederungsebene. Bildschirmfoto von Word.](https://accessible-pdf.info/content/uploads/word_gliederungsebene.png)

## Listen {#listen}

Listen sind ein weiteres wichtiges Strukturierungsmittel. Damit werden mehrere Dinge ungeordnet oder in einer definierten Reihenfolge aufgelistet. Damit Listen aus Word auch automatisch als Listen *getaggt* werden, müssen die dafür vorgesehenen Listenwerkzeuge verwendet werden.

Mit folgenden Schaltflächen kannst du das tun:

![Listen Werkzeuge in Word.](https://accessible-pdf.info/content/uploads/word-list.png)

1. Die erste Schaltfläche erstellt eine ungeordnete Liste mit Aufzählungszeichen,
2. die zweite eine nummerierte Liste und
3. die dritte gibt dir die Möglichkeit eine Liste mit mehreren Ebenen zu verwenden.

Unter dem dritten Button zur Erstellung einer Liste mit mehreren Ebenen versteckt sich die Möglichkeit eine eigene Listenformatvorlage zu definieren. Klicke dazu auf den letzten Eintrag mit der Bezeichnung „Neuen Listentyp definieren“ oder „Neue Listenfomatvorlage definieren“. Damit können das Aufzählungszeichen / die Nummerierung und dessen Einzüge definiert werden. Zudem können die einzelnen Ebenen mit **einem Absatzformat verknüpft** werden.

<aside class="note-block" markdown="1">
Abhängig von deinen Word Einstellungen wird ein Bindestrich gefolgt von einem Leerzeichen automatisch in eine korrekte Liste umgewandelt. Man sollte sich jedoch nicht darauf verlassen und eine Liste bewusst formatieren.
</aside>

Die automatisch generierten Listen-*Tags* sind: 

- `<L>` = Container des ganzen Listenblocks
	- `<LI>` = Container eines Listeneintrags
		- `<LBody>` = Inhalt eines Listeineintrags

PDF sieht eigentlich noch den *Tag* `<Lbl>` für das Aufzählungszeichen / die Nummerierungsziffer vor. Dies wird mit Word bisher nicht verwendet und es wird ebenfalls in `<LBody>` integriert. Die automatische Ausgabe ist daher nicht korrekt aber brauchbar. Die Verwendung von `<Lbl>` ist gemäss Standard nicht obligatorisch.

## Tabellen {#tabellen}

Wenn Daten sowie horizontal wie auch vertikal angeordnet sind, gehören sie in eine Tabelle. Eine Tabelle soll nicht nur visuell sondern auch maschinell als solche erkennbar sein. Sie muss daher mit dem dafür vorgesehene Tabellenwerkzeug und nicht mithilfe von Leerzeichen und Tabulatoren erstellt werden.

Um eine Tabelle hinzuzufügen, kann im Menüpunkt „Einfügen“ auf „Tabelle“ geklickt werden. Das erscheinende Raster kann verwendet werden, um auszuwählen wie viele Spalten und Zeilen die Tabelle haben soll.

![Wo in Word eine Tabelle hinzugefügt werden kann. Screenshot.](https://accessible-pdf.info/content/uploads/word_tabelle.png)

Wenn sich der Cursor irgendwo in der Tabelle befindet, werden zwei zusätzliche Registerkarten in der Menüleiste angezeigt. In diesen kann eine Tabelle näher konfiguriert werden.

Eine Tabelle enthält immer Zellen die als Überschriften gelten und anderen Zellen übergeordnet sind. Das korrekte Werkzeug um solche Überschriftenzellen in Word hinzufügen sind die Tabellenformatoptionen. Dort befinden sich die Optionen 

- Überschrift
- Erste Spalte
- Ergebniszeile
- Letzte Spalte

![Tabellenformatoptionen in Word. Markiert sind die Optionen Überschrift, Erste Spalte, Ergebnisspalte und letzte Spalte.](https://accessible-pdf.info/content/uploads/word_tabellenformatoptionen.png)

Leider haben diese Optionen bis und mit der Version 2016 nur Einfluss auf die visuelle Formatierungen, jedoch nicht auf die PDF-Ausgabe. In der 365-Version werden die Überschriftenzellen dann automatisch korrekt *getaggt*. Diesen `<TH>` *Tags* fehlt jedoch das *Scope* Attribut, welches angibt ob es eine Überschriftszelle für die Spalte oder Zeile ist.

<aside class="note-block" markdown="1">
Eine Anleitung um das *Scope* Attribut hinzuzufügen ist noch offen.
</aside>

In früheren Word-Versionen gibt es eine Möglichkeit um die erste Zeile automatisch mit `<TH>` *Tags* auszeichnen zu lassen. Dafür muss

1. der Cursor in eine Zelle der ersten Zeile gesetzt werden;
2. die Tabelleneigenschaften geöffnet werden (z.B. via Rechtsklick);
3. in das Register „Zeile“ gewechselt werden;
4. und die Option „Gleiche Kopfzeile auf jeder Zeile wiederholen“ aktiviert werden.

Auch bei diesem Lösungsweg fehlt das *Scope* Attribut im erzeugten PDF.

### Layout-Raster {#layouttabellen}

Eine Tabelle sollte nicht als Layout-Raster missbraucht werden. Falls mehrere Spalten benötigt werden, steht im Menüeintrag „Layout“ die Option „Spalten“ zur Verfügung. Mithilfe eines Spaltenumbruchs („Layout“ → „Umbrüche“ → „Spalte“) kann in die nächste Spalte gewechselt werden. Durch einen Abschnittswechsel („Layout“ → „Umbrüche“ → „Fortlaufend“) kann ein anderes Spaltenlayout angewendet werden.

## Fuss-/Endnoten {#noten}

Im Menüregister „Verweise“, respektive „Referenzen“, befinden sich die Befehle für das Hinzufügen von Fuss- und Endnoten. Der Befehl für das Hinzufügen einer Fussnote sorgt dafür, dass Fussnote und die Fussnotenziffer immer dynamisch auf der gleichen Seiten sind.

![Wie in Word eine Fussnote oder Endnote hinzufügen. Screenshot.](https://accessible-pdf.info/content/uploads/word-fuss-endnoten.png)

Die Verwendung der korrekten Befehle sorgen jedoch auch da
für, dass die Fuss-/Endnoten innerhalb eines `<Note>` *getaggt* werden. Leider lässt die Ausgabe aus Word aber noch sehr zu Wünschen übrig. Bisher werden alle Fuss-/Endnoten einer Seite innerhalb von einem `<Note>` *getaggt* anstatt jede für sich. Zudem wird der `<Note>` *Tag* nach dem Absatz, indem das erste Fussnotenzeichen erscheint, aufgeführt. Dies kann dazu führen, dass eine Fussnote vor der dazugehörigen Fussnotenziffer platziert wird. Obwohl PDF 1.7 nicht genau vorgibt wo eine Fussnote platziert werden soll, entspricht dies nicht einer verständlichen und logischen Reihenfolge.

<aside class="note-block" markdown="1">
Um es genau zu nehmen, platziert Word die Fussnoten nicht innerhalb eines `<Note>` *Tags*, sondern innerhalb eines nicht-standardkonformen `<Footnote>`. Es wird jedoch automatisch eine Rollenzuordnung mitgegeben, welche auf den standardkonformen *Tag* verweist. Erfahre mehr in [„Generelles Arbeiten mit PDF *Tags* in Acrobat“](https://accessible-pdf.info/de/basics/generelles-arbeiten-mit-pdf-tags-in-acrobat/#rollenzuordnung)
</aside>

Weiter wird auch die Fussnotenziffer nicht automatisch innerhalb eines `<Reference>` *Tags* ausgezeichnet.

## Weitere Auszeichnungen {#weitere}

Weitere semantische *Tags*, wie sie in [„Übersicht der PDF-*Tags*“](https://accessible-pdf.info/de/basics/uebersicht-der-pdf-tags/) aufgeführt sind, können aktuell nicht automatisch aus Word erzeugt werden.

## Exporteinstellung {#export}

Damit die gewünschte *Tag*struktur beim PDF-Export erstellt wird, müssen die Exporteinstellunge beachtet werden.

### Word für Windows

1. Wähle „Datei“ → „Exportieren“ → „PDF/XPS-Dokument“ erstellen 
2. Klicke auf „Optionen“
3. Aktiviere die Option „Dokumentstrukturtags für Barrierefreiheit“ falls diese nicht bereits aktiviert ist

### Word für Mac

1. Wähle „Datei“ → „Speichern unter“
2. Wähle im Dropdown „Dateiformat“ die Option „PDF“
3. Aktiviere die Option „Optimal für elektronische Verteilung und Barrierefreiheit“
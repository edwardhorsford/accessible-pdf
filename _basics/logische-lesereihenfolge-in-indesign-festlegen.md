---
ID: 58008
post_title: >
  Logische Lesereihenfolge in InDesign
  festlegen
author: Stefan Brechbühl
post_excerpt: >
  PDF-Tags werden nicht nur benötigt um
  Inhalten eine semantische Bedeutung zu
  geben, sondern auch auch um die logische
  Lesereihenfolge festzulegen. In InDesign
  kann die Reihenfolge der Tags festgelegt
  werden, sodass beim erzeugten PDF die
  logische Lesereihenfolge bereits korrekt
  ist.
layout: basics
permalink: >
  https://accessible-pdf.info/de/basics/logische-lesereihenfolge-in-indesign-festlegen/
published: true
post_date: 2019-02-28 17:26:29
---
PDF-*Tags* werden nicht nur benötigt um Inhalten eine semantische Bedeutung zu geben, sondern auch auch um die logische Lesereihenfolge festzulegen. In InDesign kann die Reihenfolge der *Tags* festgelegt werden, sodass beim erzeugten PDF die logische Lesereihenfolge bereits korrekt ist.

<aside class="note-block" markdown="1">
Was bedeutet [logische Lesereihenfolge](https://accessible-pdf.info/de/glossar/#logische-lesereihenfolge)? Erfahre mehr im Glossar.
</aside>

## Artikel Bedienfeld

Um die logische Lesereihenfolge bereits in InDesign zu bestimmen, wird das Bedienfeld „Artikel“ benötigt. Alle relevanten Inhalte müssen in einen Artikel verpackt werden. 

1. Zuerst muss ein Textrahmen (oder ein anderes Objekt) ausgewählt werden
2. Falls noch kein Artikel existiert, kann direkt ein neuer Artikel mit dem ausgewählten Objekt erstellt werden. Klicke dazu auf das kleine Seitensymbol unten rechts im Bedienfeld. Danach wirst du aufgefordert dem Artikel einen Namen zu geben. Hier wird am besten ein passendes und beschreibendes Wort verwendet.
3. Falls bereits ein Artikel existiert, kann es mit dem Plussymbol, unten rechts im Bedienfeld, einem Artikel hinzugefügt werden.

<p class="warning-block" markdown="1">
Bevor das Dokument exportiert werden kann, muss zwingend noch die Option „Für Leserichtung in PDF mit Tags verwenden“ in den Bedienfeldoptionen aktiviert werden.
![Screenshot von Bedienfeldoptionen mit aktivierter Option für Lesereihenfolge](https://accessible-pdf.info/content/uploads/indesign-artikel-reihenfolge.png)
</p>

### Nachträgliche Anpassungen

Falls ein Objekt verschoben werden muss, lässt sich dies bequem per „Drag&Drop“ tun. Klicke und verschiebe ein Objekt mit gedrückter Maustaste an die korrekte Stelle im selben oder in einen anderen Artikel.

### Verhalten bei Textverkettungen

Wenn Textrahmen miteinander verkettet sind, fliesst der Text dynamisch in den nächsten Rahmen. Dies ist nicht nur praktisch, sondern macht auch technisch Sinn. Sie werden so nämlich in einem gemeinsamen Container *getaggt*.

Im Artikel Bedienfeld werden verkettete Textrahmen als ein Objekt behandelt. Fügt man also den ersten Textrahmen hinzu, sind alle verketten Textrahmen inklusive. Die Reihenfolge ist durch die Verkettung vorgegeben.

<aside class="note-block" markdown="1">
Mehr zu [„Verketten von Textrahmen“](https://helpx.adobe.com/ch_de/indesign/using/threading-text.html) kannst du im offiziellen Onlinehandbuch nachlesen.
</aside>

### Verankerte Objekte

Grafiken oder andere Objekte können ebenfalls in einen Artikel integriert werden, sodass diese in der richtigen Reihenfolge *getaggt* werden.

Um eine Grafik an einer bestimmten Stelle in der logischen Reihenfolge zu platzieren, muss diese meist innerhalb eines Textrahmens verankert werden. Wird dies gemacht, kann man die Grafik als Bestandteil des Textrahmens betrachten. Sie erscheint nämlich nicht mehr separat im Artikel Bedienfeld.

Um ein Objekt zu verankern wird im Rahmen an der oberen Kante auf das gefüllte, kleine Quadrat geklickt. Mit geklickter Maustaste wird dann der Zeiger an die gewünschte Stelle innerhalb eines Textrahmens verschoben und die Taste losgelassen.

<aside class="note-block" markdown="1">
Mehr zu [„Verankerte Objekte“](https://helpx.adobe.com/ch_de/indesign/using/anchored-objects.html) kannst du im offiziellen Onlinehandbuch nachlesen.
</aside>

<aside class="note-block" markdown="1">
Da Grafiken Nicht-Text-Inhalte sind, muss ein Alternativtext hinterlegt werden, sofern sie inhaltlich relevant sind. Falls sie nicht relevant sind, gehören sie nicht in einen Artikel. Für weitere Informationen, siehe auch [Alt-Text](https://accessible-pdf.info/de/glossar/#alt-text) im Glossar oder [„Alt-Texte hinzufügen“](https://accessible-pdf.info/de/basics/alt-texte-hinzufuegen/).
</aside>

## Formularfelder und Tab-Reihenfolge

Auch Formularfelder sind Objekte, die ebenfalls am besten innerhalb eines Textrahmens verankert werden. Beim PDF-Export als „Adobe PDF (Interaktiv)“ kann die Option „Struktur für Aktivierreihenfolge verwenden“ aktiviert werden und die Tab-Reihenfolge wird korrekt, gemäss der logischen Lesereihenfolge, übernommen.

![Screenshot der Exportoptionen im interaktiven PDF-Format.](https://accessible-pdf.info/content/uploads/indesign_pdf_export_interaktiv.png)

## Zusätzliche Features mit MadeToTag

Das kostenpflichtige InDesign Plugin [MadeToTag](https://www.axaio.com/doku.php/de:products:madetotag) von Axaio kann bei der Arbeit mit dem Artikel Bedienfeld unterstützen. 

Im zweiten Aufgabenschritt des Plugins lassen sich sämtliche Inhalte eines Artikels oder aller Artikel ein- und ausblenden. Dies hilft um noch fehlende Inhalte zu finden, welche noch in einen Artikel aufgenommen werden müssen. Umgekehrt können auch Objekte, die nicht *getaggt* werden sollen, besser identifiziert werden.

![Screenshot des Plugins MadeToTag im 2. Aufgabenschritt](https://accessible-pdf.info/content/uploads/mtt_artikel.png)

Ähnlich wie in [„Semantik und logische Lesereihenfolge prüfen“](https://accessible-pdf.info/de/basics/semantik-und-logische-lesereihenfolge-pruefen/) gezeigt, kann mithilfe des Plugins eine Vorschau der Tags und deren Reihenfolge innerhalb von InDesign angezeigt werden.
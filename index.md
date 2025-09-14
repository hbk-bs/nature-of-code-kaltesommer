# Nature of Code

Die Aufgabe besteht darin, Muster, Verhaltensweisen und Systeme in der Natur genau zu beobachten.  
Ich habe beobachtet, wie die Ringen eines Baums aussehen.  
Dazu habe ich eine kurze Animation gebaut, jeder Ring beschreibt ein Jahr des Baums.

---

![Tree Rings](Tree+rings-+LaurieKehler.jpg)  
![Child Holding Ring](kid-ring.jpg)

---

1. **Wie es funktioniert:**  
   Am Anfang definiere ich einige Variablen:  
   - `rings` ist eine Liste, in der alle Baumringe gespeichert werden.  
   - `numRings` gibt an, wie viele Ringe entstehen sollen.  
   - `maxRadius` bestimmt, wie groß der äußerste Ring wird.  
   - Mit `currentRing` verfolge ich, welcher Ring gerade gezeichnet wird.  
   - `hasStarted` steuert, ob der Sketch schon gestartet wurde.  

   Im `setup()`-Teil erstelle ich das Canvas und stelle sicher, dass alles richtig initialisiert ist.  
   Wichtig ist hier: Ich verwende `noLoop()`, damit der Sketch nicht ständig neu gezeichnet wird – das mache ich manuell.  
   Außerdem verknüpfe ich einen Start-Button, damit der Nutzer die Animation selbst starten kann.

2. **Die draw()-Funktion: So wachsen die Ringe.**  
   Sobald man den Button klickt, wird `hasStarted` auf `true` gesetzt, und dann beginnt die Zeichnung in `draw()`.  
   Pro Frame wird ein Ring erzeugt, der mit Perlin Noise unregelmäßig geformt ist – also nicht perfekt rund, sondern organisch.  
   So sieht es natürlicher aus. Alle bereits erzeugten Ringe werden ebenfalls jedes Mal angezeigt.

3. **Wenn alle Ringe gezeichnet sind, stoppt der Loop erneut.**  
   An jedem Punkt des äußersten Rings wird noch die äußere Seite des Baums gezeichnet.  
   Dazu benutze ich eine rekursive Funktion namens `drawTree()` – sie zeichnet einen Ast, der sich immer wieder teilt.

4. **Die Klasse Ring: natürliche Formen mit Noise.**  
   Jeder Ring ist eine eigene Instanz der Klasse `Ring`.  
   Dort wird ein Kreis erzeugt, aber der Radius wird mit Perlin Noise verändert – das ergibt Unregelmäßigkeiten, wie bei echten Baumringen.  
   Statt einem perfekten Kreis entstehen Formen, die wirken, als wären sie natürlich gewachsen.

5. **Die Funktion drawTree(): fraktales Wachstum.**  
   Die kleinen Bäume werden durch eine rekursive Funktion erzeugt.  
   Sie zeichnet einen Hauptast, und dann zwei kleinere Äste, die sich im Winkel unterscheiden.  
   Das Ganze wiederholt sich mehrere Male – dadurch entsteht fraktales Wachstum, das wir bei echten Bäumen oder Pflanzen finden.

6. **Fensteranpassung & Bedienung.**  
   Wenn das Fenster neu geladen oder in der Größe verändert wird, passt sich das Canvas automatisch an.  
   So bleibt das Ganze auf allen Geräten gut sichtbar.

---

[zum Ergebnis](rings.html)

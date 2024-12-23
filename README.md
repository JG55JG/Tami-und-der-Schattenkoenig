> [!NOTE]  
> Laden und Speichern funktioniert jetzt über das Erstellen von Savegames im Speicher des Tiptois. Es ist nicht mehr notwendig eine Zahlenfolge aufzuschreiben und einzutippen :smile: :metal:. Möglich wurde das durch [tt-homebrew](https://github.com/GauiPower/tt-homebrew). 

> [!CAUTION]
> Bis jetzt nur mit einem Stift der 4. Generation getestet. Nutzung auf eigene Gefahr. Für die alte Speichermethode gibt es einen Legacy-Branch.

&nbsp;

# Tami und der Schattenkönig
Tami und der Schattenkönig ist ein Rollenspiel für den Tiptoi. Es handelt sich um ein Custom/Fan-Projekt auf Basis des grandiosen [tttools](https://tttool.entropia.de/) ([tip-toi-reveng](https://github.com/entropia/tip-toi-reveng)). Das Spiel kombiniert (hoffentlich) ein echtes Rollenspiel-Erlebnis, wie man es aus Computerspielen kennt, mit der eher analogen und bildschirmfreien Tiptoi-Spielmechanik. Das Geschlecht von Tami ist nicht festgelegt, so dass sich Mädchen und Jungen gleichermaßen mit Tami identifizieren können. Du wirst erfahrener und lernst wie du deine Fähigkeiten verbesseren kannst. Irgendwann kannst du sogar deine eigene Burg mit eigener Schmiede errichten.
Tami erlebt eine spannende Geschichte, löst dabei Rätsel und erlernt mächtige Zauber, Spezialattacken und Rezepte. Tami besiegt Gegner und erkundet gescriptete und zufällig generierte Rogue-like Dungeons.
Das Ziel bei der Spielentwicklung war, das der Tiptoi durch Soundeffekte und die Art der Eingabe fast wirklich zu einem Zauberstab, einem Schwert oder zu einer Angel wird. Neben Stärke- und Geschickwerten sollen aber auch Reaktionsschnelle und die richtigen taktischen Entscheidungen wichtig sein. Es handelt sich noch um eine Alpha-Version mit einigen bekannten Bugs und sicherlich ziemlich vielen noch nicht bekannten Bugs, sowie einem noch nicht optimalen Stärke Balancing. Um einen Eindruck von dem Spiel zu geben sind hier Links zu einem kürzeren Teaser-Video und einem längerem Gameplay-Video. 

&nbsp;

<p align="middle">
    <a href="https://youtu.be/sRXvWUkbedM">
      <img src="https://markdown-videos-api.jorgenkh.no/url?url=https%3A%2F%2Fyoutu.be%2FsRXvWUkbedM" alt="Teaser" title="Teaser"/>
    </a>
    <a href="https://youtu.be/zWo0tseTU6E">
      <img src="https://markdown-videos-api.jorgenkh.no/url?url=https%3A%2F%2Fyoutu.be%2FzWo0tseTU6E" alt="Gameplay" title="Gameplay"/>
    </a>
</p>

<p align="center">
  <b>  Teaser   &nbsp;  &nbsp;  &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Gameplay</b>
 </p>


- [Hintergrundgeschichte](#Hintergrundgeschichte)
- [Bugs](#Bugs)
- [Tag und Nacht](#Tag-und-Nacht)
- [Zufallsbegnungen](#Zufallsbegnungen)
- [Kampfsystem](#Kampfsystem)
- [Tagebuch Zauberbuch Kampftechnikbuch](#Tagebuch-Zauberbuch-Kampftechnikbuch)
- [Spielstand speichern und Spielstand laden](#Spielstand-speichern-und-Spielstand-laden)  
- [Meditieren Stufenaufstieg](#Meditieren-Stufenaufstieg)
- [Dungeons](#Dungeons)
- [Die Sümpfe-Swampsweeper](#Die-Sümpfe)


# Das Spiel
Nachfolgend kommt eine kleine, nicht volständige Beschreibung der wichtigsten Spielfunktionen.


## Bugs
Neben den tatsächlichen Bugs im Code kann es durch die beiden unten genannten Gründe zu Fehlfunktionen kommen. Zusätzlich gibt es noch einige Typos in der Srachausgabe.

1. Fehler durch schlechte Druckqualität: 
Eine falsche OID wird erkannt. Wenn die OID zu einem im Spiel vorhandenen Script gehört, kann es zu einer unerwarteten Sprachausgabe führen. Falls die OID nicht vergeben ist kommt die Sprachausgabe: "Tippe zuerst auf das Anmeldezeichen, dann kann es losgehen". In seltenen
Fällen kommt es dabei zu einem Absturz und das Spiel muss neu gestartet werden. 

2. Tippen bevor ein bestimmter Ablauf fertig vom Stift abgearbeitet ist. Viele Abläufe im Spiel bestehen aus einer Abfolge von mit `J()` verketten Funktionen. Der Großteil der verketteten Funktionen (soweit bisher möglich) ist geschützt und es sollte nicht möglich sein sie durch tippen auf eine andere OID zu unterbrechen.
Trotzdem kann das Problem ab und an auftretten. Am besten immer warten bis alle Sprachausgaben und Abläufe fertig sind.

3. In einigen Fällen kommt es zum Abbruch von Funktionen ohne das die Variable zum "Schutz" von Funktionsketten zurückgesetzt wird. Dann kommt es beim Tippen auf die meisten OIDs zu keiner Reaktion mehr. In einem solchen Fall
kann man auf die "10" unter dem "Laden" Feld tippen. Die Variablen werden dann zurückgesetzt und man kann weiterspielen.


## Hintergrundgeschichte
Du lebst mit deinen Eltern auf einem kleinen Bauernhof in einem fruchtbaren Tal. Es ist ein hartes aber glückliches Leben – während des Tages. Doch sobald die Sonne untergegangen ist erheben sich die Schatten, Geisterwesen schweben körperlos durch das Land und unterhalten sich wispernd in einer unbekannten Sprache. Zu dieser Zeit verstecken sich alle Menschen in ihren Häusern und schützen sich mit magischen Talismanen und Kräutern. Als wäre das noch nicht genug wuchs kurz vor deiner Geburt eine undurchdringliche Hecke um das Tal. Seit dieser Zeit hat kein Fremder mehr das Tal betreten und auch kein Bewohner des Tals dieses verlassen. Für dich ist das jedoch alles ganz normal, du kennst es ja nicht anders. Keiner kennt das Tal besser als du. 
Finde im ersten Kapitel des Spieles heraus was es mit den Schatten auf sich hat und wie du durch die verwunschene Hecke aus dem Tal kommen kannst. Auch wenn du es noch nicht weißt, du bist die letzte Hoffnung deiner Welt.


[![up](https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/icon_up.png) nach oben](#Tami-und-der-Schattenkönig)


## Tag und Nacht
Es gibt einen Tag/Nacht Zyklus. Nach jeweils 12 Stunden wechselt die Tageszeit. Anfangs ist Tami noch nicht erfahren genug und zu schwach um sich in der Nacht ausserhalb des Hauses aufzuhalten. Später wirst du feststellen das in der Nacht vieles anders ist (du könntest schwören, dass der Brunnen am Tag noch völlig intakt war). Manche Ereignisse finden nur zu bestimmenten Uhrzeiten statt und manche Orte lassen sich nur zu bestimmten Tageszeiten erreichen. 


[![up](https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/icon_up.png) nach oben](#Tami-und-der-Schattenkönig)


## Zufallsbegnungen
Wenn du durch das Tal streifst kommt es oft zu zufälligen Begnungen oder du entdeckst Orte die dir vorher noch nicht aufgefallen sind. Abhängig davon ob du dich im Wald der z.B. am Wasser aufhältst und ob es Tag oder Nacht ist gibt es monentan ~70 zufällige Ereignisse. Manchmal findest du einen Pilz oder ein Stück Stoff im Baum, manchmal entdeckst du eine Höhle zum erkunden oder du musst einem Steinschlag entkommen. Noch ein letzter Tip: Falls du in den Bergen bist, pass auf, dass du nicht von einem Troll entführt wirst.

[![up](https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/icon_up.png) nach oben](#Tami-und-der-Schattenkönig)



## Kampfsystem 

<p align="middle">
  <img src="https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/kampf.png" width="25%" />
  <img src="https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/code_panel.png" width="22.5%" /> 
</p>
<p align="center">
  <sub> (links) Kampfpanel  (rechts) Zauber + Spezialattacken + Codepanel
  </sub>
</p>

### Nahkampf
Der Nahkampf findet in Echtzeit statt, man muss schnell reagieren und trotzdem die richtige Taktik für bestimmte Gegner finden. Ist der Gegner im Angriff, wird die Richtung des Angriffs angesagt (z.B. 'unten'). Tami kann mit einer entgegengesetzten Bewegung ausweichen ('oben') oder in der gleichen Richtung parieren ('unten'). Bewegt sich Tami in eine der anderen Richtungen (z.b. 'links') oder wartet zu lange mit der Reaktion (> 2Sekunden), trifft der Gegner automatisch. Ausweichen hat den Vorteil, dass die Trefferwahrscheinlichkeit durch den Gegner sehr viel kleiner ist als bei einer Parade. Allerdings bleibt der Gegner beim ausweichen in der Initiative und kann weiter angreifen. Mit einer kleinen Wahrscheinlichkeit kann der Gegner bei einer Ausweichaktion von Tami straucheln (25%). 
Tami erkennt im Angriff die beste Angriffsrichtung (z.B. 'rechts') oder bei stärkeren Gegnern nur Zone in der die beste Angriffsrichtung liegt (z.B. 'rechts-oben', inkludiert: rechts, oben und springen). Wartet man zu lange oder tippt auf die falsche Richtung wechselt die Initiative zum Gegner. Die Treffer- und Parade-Ergebnisse werden vom Tiptoi basierend auf den Geschick/Stärke Werten von Tami und dem Gegner ausgewürfelt. **Nach der Richtungsansage** kann Tami 1) in die angesagte Richtung schlagen, 2) einen Zauber starten, 3) einen Spezialangriff starten oder 4) einen Gegenstand antippen und auf sich oder den Gegner benutzen.


**Angriff von Tami**



```mermaid
graph TD;
    D[Initiative Tami]-->E[Ansage der Angriffrichtung];
    E--2 Sekunden-->GG[Spezialattacke];
    E--2 Sekunden-->GGG[Zauber];
    E--2 Sekunden-->GGGG[Gegenstand benutzen];
	E--2 Sekunden-->G[tippen auf Richtung];
    E-- zu langsam -->C[Initiative Gegner];
    G--vorbei-->C
    G--getroffen-->II[Auswertung];
    II--Parade Gegner-->C;
    II--Treffer-->J[Schaden];
    J-->E;
    J--Gegner besiegt-->K[Belohnung]
```
[![up](https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/icon_up.png) nach oben](#Tami-und-der-Schattenkönig)

&nbsp; 


**Angriff des Gegners**

```mermaid
graph TD;
    D[Initiative Gegner]-->E[Ansage der Verteidigungsrichtung];	
	D-->EE[Spezialattacke Gegner\nSerie vorgeben\nEinfrieren\nFeuerball\nGiftattacke\n...];
	EE-->F[Serie nachtippen\nGegenzauber\n Gegenaktion];
	F--erfolgreich-->A[Initiative Tami];
	F--fail-->H;
	E--2 Sekunden-->G[Parade];
	E--2 Sekunden-->GG[Ausweichen];
	E--2 Sekunden-->GGG[falsche Richtung];
	G-->I[Auswertung];
	E--zu langsam-->H[Schaden Tami];
	GG-->I;
	I-->H;
	EE-->H;
	I-->A;
	I-->D;
	H-->D;
	H--Tami wurde besiegt-->J[zu Hause aufwachen]
	

```
[![up](https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/icon_up.png) nach oben](#Tami-und-der-Schattenkönig)


**Initiative:**
Ist der Geschick/Stärke-Wert des Gegners größer, hat der Gegner am Anfang des Kampfes die Initiative, ansonsten Tami. 

**Kampf-Vergleichswert:**
Dieser Wer bestimmt ob eine Parade, ein Ausweichen oder eine Attacke erfolgreich ist. Der Wert wird für jede Aktion neu bestimmt und besteht 1) aus einer zufälligen Komponente, die abhängig von der verwendeten Waffe ausgewürfelt wird, 2) dem Geschick/Kraft-Wert von Tami und dem Gegner und 3) einem Modifikator der abhängig davon ist ob Tami in die richtige Richtung getippt hat. Ist der Kampf-Vergleichswert von Tami größer oder gleich dem Wert des Gegners, gewinnt Tami.
```
Kampf-Vergleichswert = (W(Waffenwert) + Geschick/Kraft-Wert) * Modifikator
```

| Aktion            |  Modifikator | Bemerkung |
:-------------------------:|:-------------------------:|:-------------------------:
| Defensiv - Parade (gleiche Richtung) | x 1.2 | |
| Defensiv - vorbei (vorbeigetippt) | x 0.4 | |
| Defensiv - Ausweichen (entgegengesetzt) | x 4.0 | bei Gewinn nur in 25% Initiativewchsel <br> (Straucheln des Gegners) |
| Offensiv - Perfekter Treffer | x 1.2 | |
| Offensiv - Trefferzone | x 1.0 | |
| Offensiv - Fehlschlag | | direkter Initiativewechsel zum Gegner |
| Offensiv - zu langsam | | direkter Initiativewechsel zum Gegner |

**Waffen**

| Waffe           |  Würfel für Kampf-Vergleichswert | Schaden |
:-------------------------:|:-------------------------:|:-------------------------:
| Holzschwert | W6 | 2 + Stärkewert/2 |
| Magisches Schwert | W8 | 3 + Stärkewert/2 |

[![up](https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/icon_up.png) nach oben](#Tami-und-der-Schattenkönig)


### Fernkampf
Fernkampf ist nur auf dem Dungeonplan relevant. Für Fernkampf benötigt Tami einen Bogen + Pfeile oder einen Stein zum Werfen. Auch einige Gegner können auf Distanz angreifen. Fernkampf ist nur in direkter, nicht durch Mauern unterbrochener Sichtlinie möglich. Die maximale Distanz ist abhängig von dem Intelligenz-Wert.

<p align="middle">
  <img src="https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/zielscheibe.png" width="35%" />
</p>
<p align="center">
  <sub> Zielscheibe für Fernkampf, Angeln und weiteres
  </sub>
</p>

**Fernkampfangriff von einem Gegner**

Macht dein Gegner einen Fernkampfangriff wird der Fernkampf-Vergleichswert des Gegners ausgewürfelt und angesagt. Zur Verteidigung muß Tami auf den Würfel tippen. Danach wird Tamis Ferkampf-Verteidigungwert ausgewürfelt und
es wird ausgewertet ob der Gegner getroffen hat.

Fernkampf-Vergleichswert (Fern<sub>Gegner</sub>) = W(6) + Geschick/Kraft-Wert

Ferkampf-Verteidigung Tami (Fern<sub>Tami</sub>) = W(6) + Geschick/Kraft-Wert

Fern<sub>Gegner</sub> > Fern<sub><Tami</sub> :arrow_right: Gegner trifft

Fern<sub>Gegner</sub> $$\leq$$ Fern<sub><Tami</sub> :arrow_right: Tami weicht aus

**Fernkampfangriff von Tami**
Tippe auf den Bogen oder den Stein und dann auf den Gegner-Token. Danach wird die Angriffsrichtung auf der Zielscheibe in Grad und Meter angesagt. Tippe auf das richtige Feld (bei einem höheren Geschickwert werden auch Nachbarfelder akzeptiert).
Falls du in der gegebenen Zeit gut gezielt hast, wird der Angriff wie oben ausgewürfelt. 


[![up](https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/icon_up.png) nach oben](#Tami-und-der-Schattenkönig)


## Tagebuch Zauberbuch Kampftechnikbuch

Manchmal ist Tami nicht ganz bei der Sache, überhört eine wichtige Information oder vergisst wie genau dieser eine Zauber funktioniert hat. Aber kein Problem wichtige Dialoge und Ereignisse
werden automatisch im Tgaebuch festgehalten und können später nachgehört werden. Tippe auf das Tagebuch um den letzten Eintrag nachzuhören, über die Pfeile kannst du zu älteren eintragen und zurück zu neueren Einträgen navigieren.


<p align="left">
  <img src="https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/erinnerung.png"/ width="50%" >
</p>


[![up](https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/icon_up.png) nach oben](#Tami-und-der-Schattenkönig)


## Spielstand speichern und Spielstand laden
Das Speichern und Laden funktioniert jetzt ganz komfortabel über Savegame-Files auf dem Tiptoi. Es gibt 10 mögliche Speicherplätze (0-9), nach dem Tippen auf Speichern oder Laden wird man aufgefordert über die Zahlenfelder ein Savegame auszuwählen. Falls der Spielstand schon vorhanden ist muß man noch mit tippen auf **JA** bestätigen, dass man das Savegame überschreiben will. Im Gegensatz zu vorher kann man jetzt auch in Dungeons speichern.

<del>Die Spielzeit der Hauptquest ist (geschätzt) mindestens 5 Stunden. Das ist zu lang für eine einzige Tiptoi Spielsession, darum ist es wichtig den Spielstand speichern zu können. Tippt man auf den 'Speichern' Button wird eine Zahlenreihe angesagt, die man aufschreiben muß. Der komplette Spielfortschritt, inklusive aller gefunden Gegenstände, erlernten zauber u.s.w. ist in der leider sehr langen Reihe (bis zu xx Zeichen) kodiert. Tippt man auf den 'Laden' Button kann man einen Speichercode eingeben. Die ganze Prozedur ist leider etwas mühsam aber wahrscheinlich die einzige Möglichkeit zum Speichern mit dem Tiptoi. </del>


    
 [![up](https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/icon_up.png) nach oben](#Tami-und-der-Schattenkönig)

## Meditieren Stufenaufstieg

Mit der Zeit erlebt Tami immer neue Abenteuer, lernt und erhält Erfahrungspunkte. Ab einer gewissen Stelle im Spiel erfährt Tami von dem Geheimnis der Meditation, das es ermöglicht die Erfharungspunkte für einen Stufenanstieg zu verwenden. Für jeden Stufe erhält Tami eine Punkt Lebensenergie mehr und einen Punkt der für die Verbesserung der geistigen oder der körperlichen Fähigkeiten verwendet werden kann.

<a href="https://youtu.be/hpkKJMFcSH0">
  <img src="https://markdown-videos-api.jorgenkh.no/url?url=https%3A%2F%2Fyoutu.be%2FhpkKJMFcSH0" alt="Meditieren" title="Meditieren"/>
</a>

<p align="left" >    Videoerklärung Meditieren   </p>
   
 [![up](https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/icon_up.png) nach oben](#Tami-und-der-Schattenkönig)

## Dungeons
In Tami und der Schattenkönig gibt es gescriptete Dungeons und nach gewissen Regeln zufällig generierte Dungeons, mit Fallen, Gegnern, Schätzen und Rätseln. Ein Dungeon kann jede beliebige Form auf dem 10 X 10 Dungeonplan einnehmen und aus bis zu 4 Räumen bestehen. Tami kann Barieren bauen, damit ihn seine Gegner nicht mehr verfolgen können oder mit Magie und Fernkampf kämpfen. Doch auch die Gegner können sich mit Fernkampf, Eis, Gift oder Feuerzaubern wehren. Später kann sich Tami inerhalb von Dungeons teleportieren. Neue Dungeons können leicht in einem Baukastensystem erstellt werden.

<p align="middle">
  <img src="https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/dungeon.png" width="35%" />
</p>
<p align="center">
  <sub> Der Dungeonspielplan
  </sub>
</p>


 [![up](https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/icon_up.png) nach oben](#Tami-und-der-Schattenkönig)


## Die-Sümpfe

An einigen Stellen kommt Tami freiwillig oder unfreiwillig in tückische Sümpfe und Moore. Um da herauszufinden muß man die tiefen Sumpflöcher umgehen. Das Gameplay ist an Minesweeper angelehnt. Bei jedem 
Betreten des Sumpfes wird ein neuer Spielplan generiert. Ein Beispiel findet sich im Gameplay Video nach 7 Minuten.

[![up](https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/icon_up.png) nach oben](#Tami-und-der-Schattenkönig)

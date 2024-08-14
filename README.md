# Tami und der Schattenkönig
Tami und der Schattenkönig ist ein Rollenspiel für den Tiptoi. Es handelt sich um ein Custom/Fan-Projekt auf Basis des grandiosen [tttools](https://tttool.entropia.de/) ([tip-toi-reveng](https://github.com/entropia/tip-toi-reveng)). Das Spiel kombiniert (hoffentlich) ein echtes Rollenspiel-Erlebnis, wie man es aus Computerspielen kennt, mit der eher analogen und bildschirmfreien Tiptoi-Spielmechanik. Das Geschlecht von Tami ist nicht festgelegt, so dass sich Mädchen und Jungen gleichermaßen mit Tami identifizieren können. Du wirst erfahrener und lernst wie du deine Fähigkeiten verbesseren kannst. Irgendwann kannst du sogar deine eigene Burg mit eigener Schmiede errichten.
Tami erlebt eine spannende Geschichte, löst dabei Rätsel und erlernt mächtige Zauber, Spezialattacken und Rezepte. Tami besiegt Gegner und erkundet gescriptete und zufällig generierte Rogue-like Dungeons.
Das Ziel bei der Spielentwicklung war, das der Tiptoi durch Soundeffekte und die Art der Eingabe fast wirklich zu einem Zauberstab, einem Schwert oder zu einer Angel wird. Neben Stärke- und Geschickwerten sollen aber auch Reaktionsschnelle und die richtigen taktischen Entscheidungen wichtig sein. Es handelt sich noch um eine Alpha-Version mit einigen bekannten Bugs und sicherlich ziemlich vielen noch nicht bekannten Bugs, sowie einem noch nicht optimalen Stärke Balancing. Ein Gameplay Video mit den wichtigsten Features gibt es hier. 

- [Hintergrundgeschichte](#Hintergrundgeschichte)
- [Tag und Nacht](#Tag-und-Nacht)
- [Zufallsbegnungen](#Zufallsbegnungen)
- [Das Userinterface](#Das-Userinterface)
- [Kampfsystem](#Kampfsystem)
- [Gegner](#Gegner)
- [Dungeons](#Dungeons)
- [Das Tagebuchsystem](#Das-Tagebuchsystem)
- [Items & Crafting](#Items-&-Crafting)
- [Meditieren (Stufenaufstieg)](#Meditieren-(Stufenaufstieg))
- [Schlafen](#Schlafen)


# Das Spiel
Nachfolgend kommt eine kleine, nicht volständige Beschreibung der wichtigsten Spielfunktionen.

## Hintergrundgeschichte
Du lebst mit deinen Eltern auf einem kleinen Bauernhof in einem fruchtbaren Tal. Es ist ein hartes aber glückliches Leben – während des Tages. Doch sobald die Sonne untergegangen ist erheben sich die Schatten, Geisterwesen schweben körperlos durch das Land und unterhalten sich wispernd in einer unbekannten Sprache. Zu dieser Zeit verstecken sich alle Menschen in ihren Häusern und schützen sich mit magischen Talismanen und Kräutern. Als wäre das noch nicht genug wuchs kurz vor deiner Geburt eine undurchdringliche Hecke um das Tal. Seit dieser Zeit hat kein Fremder mehr das Tal betreten und auch kein Bewohner des Tals dieses verlassen. Für dich ist das jedoch alles ganz normal, du kennst es ja nicht anders. Keiner kennt das Tal besser als du. 
Finde im ersten Kapitel des Spieles heraus was es mit den Schatten auf sich hat und wie du durch die verwunschene Hecke aus dem Tal kommen kannst. Auch wenn du es noch nicht weißt, du bist die letzte Hoffnung deiner Welt.

## Tag und Nacht
Es gibt einen Tag/Nacht Zyklus. Nach jeweils 12 Stunden wechselt die Tageszeit. Anfangs ist Tami noch nicht erfahren genug und zu schwach um sich in der Nacht ausserhalb des Hauses aufzuhalten. Später wirst du feststellen das in der Nacht vieles anders ist (du könntest schwören, dass der Brunnen am Tag noch völlig intakt war). Manche Ereignisse finden nur zu bestimmenten Uhrzeiten statt und manche Orte lassen sich nur zu bestimmten Tageszeiten erreichen. 

## Zufallsbegnungen
Wenn du durch das Tal streifst kommt es oft zu zufälligen Begnungen oder du entdeckst Orte die dir vorher noch nicht aufgefallen sind. Abhängig davon ob du dich im Wald der z.B. am Wasser aufhältst und ob es Tag oder Nacht ist gibt es monentan ~70 zufällige Ereignisse. Manchmal findest du einen Pilz oder ein Stück Stoff im Baum, manchmal entdeckst du eine Höhle zum erkunden oder du musst einem Steinschlag entkommen. Noch ein letzter Tip: Falls du in den Bergen bist, pass auf, dass du nicht von einem Troll entführt wirst.

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
Tami erkennt im Angriff die beste Angriffsrichtung (z.B. 'rechts') oder bei stärkeren Gegnern nur Zone in der die beste Angriffsrichtung liegt (z.B. 'rechts-oben', inkludiert: rechts, oben und springen). Wartet man zu lange oder tippt auf die falsche Richtung wechselt die Initiative zum Gegner. Die Treffer- und Parade-Ergebnisse werden vom Tiptoi basierend auf den Geschick/Stärke Werten von Tami und dem Gegner ausgewürfelt.

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

**Fernkampfangriff von Tamir**
Tippe auf den Bogen oder den Stein und dann auf den Gegner-Token. Danach wird die Angriffsrichtung auf der Zielscheibe in Grad und Meter angesagt. Tippe auf das richtige Feld (bei einem höheren Geschickwert werden ach Nachbarfelder akzeptiert).
Falls du in der gegebenen Zeit gut gezielt hast, wird der Angriff ausgewürfelt. 


[![up](https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/icon_up.png) nach oben](#Tami-und-der-Schattenkönig)


## Das Userinterface

suchen, sprechen, essen, benutzen

## Tagebuch, Zauberbuch, Kampftechnik-Buch

Manchmal ist Tami nicht ganz bei der Sache, überhört eine wichtige Information oder vergisst wie genau dieser eine Zauber funktioniert hat. Aber kein Problem wichtige Dialoge und Ereignisse
werden automatisch im Tgaebuch festgehalten und können später nachgehört werden. Tippe auf das Tagebuch um den letzten Eintrag nachzuhören, über die Pfeile kannst du zu älteren eintragen und zurück zu neueren Einträgen navigieren.

[![up](doc/figures/icon-up.28.png) back to overview](#overview)

<p align="left">
  <img src="https://github.com/JG55JG/Tami-und-der-Schattenkoenig/blob/main/figs/erinnerung.png"/ width="15%" >
</p>
<sub>Abbildung 2: Dungeon 1
</sub>

## Spielstand speichern und Spielstand laden

Die Spielzeit der Hauptquest ist (geschätzt) mindestens 5 Stunden. Das ist zu lang für eine einzige Tiptoi Spielsession, darum ist es wichtig den Spielstand speichern zu können. Tippt man auf den 'Speichern' Button wird eine Zahlenreihe angesagt, die man aufschreiben muß. Der komplette Spielfortschritt, inklusive aller gefunden Gegenstände, erlernten zauber u.s.w. ist in der leider sehr langen Reihe (bis zu xx Zeichen) kodiert. Tippt man auf den 'Laden' Button kann man einen Speichercode eingeben. Die ganze Prozedur ist leider etwas mühsam aber wahrscheinlich die einzige Möglichkeit zum Speichern mit dem Tiptoi.  

## Gegner
Baukasten aus Eigenschaften, Spezialfertigkeiten und Belohnungen


## Meditieren und das Levelsystem

## Höhlen Räume
Scripted nach Baukastensystem oder zufällig generiert mit Gegnern, Schatzkisten und Fallen.
Rouge-like (4 zufälllige Räume gleichzeitig, dann neue Ebene)
Schatzkisten
Barieren
## Sümpfe

## Zauber und Spezialattacken
## Portale und Teleportzauber

## Laden und Speichern

## Schlafen

## Level up und Einfluß von Werten

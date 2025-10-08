# Intelligente-Systeme

# Multisensorik

# Laser scanner
### Ein Laserscanner (oder  LIDAR) ist ein Sensor, der Entfernungen zu Objekten misst, indem er Lichtimpulse aussendet und die Reflexion (also das zurückkommende Licht) misst. 

## Entfernungsmessung mit Laserlicht
### Der Scanner sendet Laserstrahlen aus. Diesen treffen auf ein Objekt und werden zurückreflektiert. Aus der Zeit, die der Lichstrahl braucht, um hin und zurück zu kommen (Laufzeitmessung), wird die entfernung berechnet. 

## Entfernung = c x t / 2  
### c : Lichtgeschwindigkeit (~300.000 km/s) , t: gemessene Laufzeit. 


## Öffnungswinkel vernachlässigbar
### Das bedeutet: Der Laserstrahl ist sehr schmal (nahezu punktförmig). Er hat also kaum einen Öffnungswinkel wie z. B. Radarwellen — dadurch ist die Räumliche Auflösung sehr hoch (präzise Messung kleiner Details).

## Reflektor erkenung 
### Der Scanner kann Reflektoren (z. B. Spiegel, reflektierende Markierungen) leicht erkennen, weil sie besonders starkes reflektiertes Signal zurücksenden. Das wird z. B. genutzt zur Positionserkennung oder Navigation in Robotern (sie erkennen ihre Umgebung über fest installierte Reflektoren).


## Wie funktioniert er allgemein
### Der Laser schickt mehrere Strahlen in verschiedene Richtungen (meist durch rotierende Spiegel oder Drehbewegung). So wird die gesamte Umgebung Zeile für Zeile abgetastet und eine 3D-Punktwolke erstellt, die die Umgebung beschreibt.

## Begrenzungen des Laserscanners
### 1-Leistung des Lasers (Stärke)
#### Wenn der Laser zu schwach ist, kommt zu wenig Licht zurück → Entfernungsmessung wird ungenau.
#### Zu stark → kann blenden oder Reflexionsfehler verursachen.
### 2- Glas oder transparente Oberflächen
#### Glas reflektiert und bricht Licht gleichzeitig → der Laserstrahl kann „verloren“ gehen oder doppelt reflektiert werden. Deshalb erkennt LIDAR Glasflächen oft nicht oder falsch.
### 3- Cross Talk (Signalüberschneidung)
#### Wenn mehrere Laserscanner in der Nähe arbeiten, können ihre Signale sich überlagern. Dieses Problem ist geringer als bei Radar, weil Laser sehr gerichtete Strahlen haben.

### Wie kann man das Reflektionsproblem lösen?
### Filterung und Signalverarbeitung: Software kann schwache oder doppelte Reflexionen erkennen und herausfiltern.
### Neigung des Sensors ändern: Ein leicht schräger Winkel reduziert Reflexionen auf Glasoberflächen.
### Kombination mit anderen Sensoren: LIDAR + Kamera oder Radar → Sensorfusion hilft, Glas oder transparente Objekte besser zu erkennen.
### Wellenlänge anpassen: Bestimmte Wellenlängen (z. B. im nahen Infrarotbereich) haben weniger Probleme mit Reflexionen.

# 🚗 Fahrkamera (Vehicle Camera)
## Fahrkameras sind Kameras, die in Fahrzeugen (z. B. Autos, Roboter, autonome Fahrzeuge) eingebaut werden, um die Umgebung visuell zu erfassen. Sie sind ein zentrales Element für Umfelderkennung, Spurhaltung, Hinderniserkennung und vieles mehr.

## Fahrbilder, Pendeln–Tilten–Zoomen: Fahrbilder → Das sind die Bilder, die die Kamera während der Fahrt aufnimmt.
## Sie dienen zur Analyse der Straße, Objekte, Verkehrsschilder usw.
## Pendel–Tilten–Zoomen (PTZ) → Das beschreibt die Bewegungsarten einer beweglichen Kamera:
## Pendel (Pan): Drehung nach links und rechts
## Tilten (Tilt): Neigung nach oben und unten
## Zoomen: Veränderung des Sichtfeldes (Vergrößern oder Verkleinern)
## ➡️ Eine PTZ-Kamera kann also den Bereich dynamisch anpassen, den sie überwachen möchte — z. B. einem Objekt folgen oder ein Verkehrsschild näher heranzoomen.
## Mehrkamerasysteme, Erkennungsfachbereiche und Kanten
### Mehrkamerasysteme: Moderne Fahrzeuge haben mehrere Kameras (z. B. vorne, hinten, seitlich, oben) : Dadurch entsteht ein rundum-360°-Blickfeld.
### Die Daten mehrerer Kameras werden kombiniert („Sensorfusion“), um ein vollständiges Bild der Umgebung zu erhalten.

### Erkennungsfachbereiche: Jede Kamera deckt einen bestimmten Erkennungsbereich ab (z. B. Frontkamera für Spur und Verkehrsschilder, Rückkamera für Einparken). Zusammen decken sie alle wichtigen Sichtfelder ab.
### Kanten: In der Bildverarbeitung sind „Kanten“ die Übergänge zwischen hell und dunkel, also Objektgrenzen. Kanten werden erkannt, um Formen, Fahrbahnmarkierungen oder Hindernisse zu identifizieren.

### Entefrnungskammera, Stereokammera

## Distanzkammera
### 3D- Absandsprofil
### Time-of-Flight messung mit laser. 
#### Alternativ dazu :
### Mustererkennung : spielconsolen, 

## Radar: 
### Entfernungsmessung mit Elektromagnetischen Wellen.
### Variation der Frequnezen, 
### nicthvernachlässigbar klein Relativgeschwindigkeit: Erkären Sie ....


## GNSS
### Sattelatennavigation, 
### Genauigkeit Ohne Referenzenstation 2m mit 2cm 

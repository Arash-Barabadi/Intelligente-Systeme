# Intelligente-Systeme

# 2.3 Multisensorik

# Bunper
# Sonar
## 



# Laser scanner (LIDAR)
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

<img width="500" height="375" alt="image" src="https://github.com/user-attachments/assets/71d9bb67-77e9-4f5d-9844-a5c02c1a5f18" />

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

## Entfernungskamera / Stereokamera :
### Eine Entfernungskamera misst, wie weit ein Objekt entfernt ist. Eine Stereokamera besteht aus zwei Kameras, die wie menschliche Augen leicht versetzt angebracht sind.

<img width="540" height="540" alt="image" src="https://github.com/user-attachments/assets/2cb21311-7760-42c6-a2bc-4a59a1ca9d7b" />
<img width="850" height="567" alt="image" src="https://github.com/user-attachments/assets/07e5fc21-c480-4455-aaa8-911b2216a06f" />


## → Durch den Vergleich der beiden Bilder (Disparität) kann die Tiefe (Abstand) berechnet werden.
### → Anwendung: Abstandserkennung, 3D-Rekonstruktion, Hinderniserkennung.

## Distanzkamera
### Eine Distanzkamera (oder Tiefenkamera) liefert ein 3D-Abstandsprofil – also ein Bild, in dem jeder Pixel nicht nur Helligkeit, sondern auch Entfernung enthält.
### 3D-Abstandsprofil: Jedes Pixel gibt an, wie weit der Punkt in der Realität entfernt ist. Ergebnis: Eine Punktwolke (Point Cloud) oder Tiefenkarte (Depth Map).


## TOF Kamera: Time-of-Flight messung mit laser. 
### Bei der Time-of-Flight-Technik wird ein Laserimpuls ausgesendet. Die Kamera misst, wie lange das Licht braucht, um vom Objekt zurückzukommen. Aus der Laufzeit des Lichts wird der Abstand berechnet. Distnaz = c x t / 2
####  → Vorteil: Sehr genaue und schnelle Tiefenmessung. 
#### → Nachteil: Funktioniert schlechter bei sehr heller Sonne oder spiegelnden Oberflächen.

<img width="640" height="640" alt="image" src="https://github.com/user-attachments/assets/ad707860-f261-4fd5-a01f-66529c2430e9" />

<img width="410" height="320" alt="image" src="https://github.com/user-attachments/assets/4aaca847-43be-45cd-b6fa-b6ebc4918604" />
<img width="540" height="360" alt="image" src="https://github.com/user-attachments/assets/c9ea8aca-eba3-42be-ab04-23c3372f9626" />


## Mustererkennung (Structured Light) Kamera
### Hier wird kein Zeitunterschied gemessen, sondern ein Lichtmuster (z. B. Punkte oder Gitter) auf die Szene projiziert.
### Eine Kamera beobachtet, wie sich das Muster verformt → daraus wird die Tiefe berechnet.
### Anwendung: z. B. bei Spielkonsolen (Microsoft Kinect, PlayStation Camera) zur Bewegungserkennung. 

<img width="370" height="370" alt="image" src="https://github.com/user-attachments/assets/92ace76c-0d5e-4a56-bd58-5046aa5c8bb6" />
<img width="618" height="410" alt="image" src="https://github.com/user-attachments/assets/48132701-c6f4-4d3d-8b0c-a32ee209160e" />
<img width="250" height="202" alt="image" src="https://github.com/user-attachments/assets/e3a0e736-d1e9-47b7-bbc5-ec53e4e87f8d" />


## Zusammengefasst:

<img width="1582" height="480" alt="image" src="https://github.com/user-attachments/assets/eadfb59a-1150-4f9a-87c5-cd50f3800e3b" />

# Radar: 
## Ein Radar (Radio Detection and Ranging) misst die Entfernung (Distanz) zu einem Objekt, indem es elektromagnetische Wellen (meist im Mikrowellenbereich) aussendet und das Echo misst, das vom Objekt zurückkommt.
## Das Radar sendet eine Welle aus.
### Diese Welle trifft auf ein Objekt und wird reflektiert. Das Radar empfängt die reflektierte Welle. Aus der Laufzeit zwischen Senden und Empfangen kann man die Entfernung berechnen: d = c x t / 2.
### In modernen Radarsystemen wird oft die Frequenz der ausgesendeten Wellen variiert – z. B. bei FMCW-Radar (Frequency Modulated Continuous Wave). Dabei wird die Frequenz der gesendeten Welle kontinuierlich verändert (z. B. in einer Sägezahn- oder Dreiecksform).Wenn das reflektierte Signal zurückkommt, vergleicht man seine Frequenz mit der gerade gesendeten Frequenz. Der Frequenzunterschied (Beat-Frequenz) ist proportional zur Entfernung. So kann man Entfernung und Geschwindigkeit gleichzeitig bestimmen.
### Wenn sich das Objekt auf das Radar zubewegt, steigt die empfangene Frequenz. Wenn es sich entfernt, sinkt sie. Diese Frequenzverschiebung nennt man Doppler-Shift.
### nicthvernachlässigbar klein Relativgeschwindigkeit: Wenn sich das Zielobjekt relativ zum Radar bewegt (z. B. ein Auto, Flugzeug, Drohne), ändert sich die Frequenz der reflektierten Welle durch den Doppler-Effekt.
#### 1-Wenn sich das Objekt auf das Radar zubewegt, steigt die empfangene Frequenz.
#### 2- Wenn es sich entfernt, sinkt sie. Diese Frequenzverschiebung nennt man Doppler-Shift.
<img width="487" height="231" alt="image" src="https://github.com/user-attachments/assets/2c7b19bd-a9f9-41b7-ad60-ceab79404657" />


# GNSS (Global Navigation Satellite System)
## (z. B. GPS, Galileo, GLONASS, BeiDou).
## Das System besteht aus:
### 1- Satelliten im Weltraum,
### 2- Bodenstationen,
### 3- und einem Empfänger (z. B. im Auto, Smartphone oder Messgerät).
### Grundprinzip: Entfernungsmessung
### 1- Der GNSS-Empfänger misst die Entfernung zu einem Satelliten, indem er die Laufzeit des Funksignals bestimmt:
### Entfernung = 𝑐 × 𝑡
### Damit weiß der Empfänger: „Ich bin irgendwo auf einer Kugel mit Radius = dieser Entfernung um den Satelliten.“ Ein Satellit → Eine Kugel Mit nur einem Satelliten weiß der Empfänger: Er befindet sich irgendwo auf der Oberfläche dieser Kugel. Aber nicht wo genau auf der Kugel. ➡️ Unendlich viele Möglichkeiten.
### 2- Zwei Satelliten → Schnittkreis zweier Kugeln. Wenn du zwei Satelliten hast, schneiden sich ihre Kugeln → Du befindest dich irgendwo auf dem Schnittkreis dieser beiden Kugeln.➡️ Immer noch nicht eindeutig.
### 3- Drei Satelliten → Zwei mögliche Punkte. Bei drei Satelliten schneiden sich die drei Kugeln in zwei Punkten. Einer dieser Punkte liegt meist weit außerhalb der Erde, der andere liegt auf oder nahe der Erdoberfläche. ➡️ Der Empfänger kann so deine Position (Länge, Breite) bestimmen.
### 4- Vier Satelliten → Eindeutige 3D-Position, Damit der Empfänger auch die Höhe und vor allem seinen Uhrenfehler (die Empfängeruhr ist nicht so genau wie die Atomuhr der Satelliten) bestimmen kann, braucht er mindestens vier Satelliten.
#### Drei Satelliten → theoretisch Position auf der Erde (2D)
#### Vier Satelliten → zusätzlich Höhe und Zeitkorrektur (3D)
## Darum misst der GNSS-Empfänger die Signallaufzeit von mehreren Satelliten gleichzeitig – in der Regel mindestens vier, oft 6–12 gleichzeitig, um die Position möglichst genau zu berechnen.
## Zusammengefast:
<img width="712" height="192" alt="image" src="https://github.com/user-attachments/assets/90ae347c-70c4-4cd1-a24a-6ea5d26790c3" />



<img width="526" height="430" alt="image" src="https://github.com/user-attachments/assets/dda588ba-b71e-4c79-be0e-cda161ecf18f" />

## Genauigkeit ohne Referenzstation: ~2 m
### Wenn man nur die Satellitensignale verwendet (also keine zusätzliche Korrektur bekommt),
### liegt die Positionsgenauigkeit typischerweise bei etwa 2–5 Metern.
### Grund: Satellitenuhrenfehler, Ionosphären- und Troposphäreneinflüsse (Verzögerung des Signals in der Atmosphäre), Kleine Bahnunterschiede der Satelliten, Mehrwegeffekte (Signalreflexionen an Gebäuden usw.) ➡️ Diese Fehler führen dazu, dass die berechnete Position leicht verschoben ist → Genauigkeit ca. 2 m.
## Mit Referenzstation (Differential GNSS / RTK): ~2 cm, 
### Wenn man zusätzlich eine Referenzstation verwendet (z. B. bei Vermessungssystemen), kann man die Genauigkeit stark verbessern. Wie?
### Eine Referenzstation steht an einem bekannten, festen Ort. Sie empfängt dieselben Satellitensignale wie dein Empfänger. Da ihr Standort genau bekannt ist, kann sie den Fehler zwischen berechnetem und tatsächlichem Standort bestimmen. Diese Korrekturen werden an deinen Empfänger gesendet (z. B. über Funk, Internet). Dein Gerät gleicht damit seine Messung ab → Fehler werden kompensiert. ➡️ Ergebnis: Positionsgenauigkeit bis zu 2 cm! Diese Technik nennt man: DGPS (Differential GPS) oder RTK (Real-Time Kinematic)

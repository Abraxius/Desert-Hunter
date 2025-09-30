<p align="center"> <img width="512" height="512" alt="Logo" src="https://github.com/user-attachments/assets/b7a47f05-94e8-4501-ab5c-0f3dc5291e5e"/> </p>

# Desert Hunter

Ein UE5 Projekt für den Kurs "Computer Games" an der HS Fulda.
Von Juan Pablo und Alexander Jost

## Was kann der Spieler alles machen?

In "Desert Hunter" tauchst du in eine spannende Jagd ein, bei der dein Hauptziel ist, innerhalb einer vorgegebenen Zeit möglichst viele Tiere zu erlegen, um dabei die höchste Punktzahl zu erreichen. Doch sei auf der Hut – die Tierwelt ist vielfältig und voller Überraschungen!

Jage eine vielfältige Tierwelt:
Dein Jagdgebiet beheimatet eine Reihe unterschiedlicher Tiere, die alle ihre eigenen Verhaltensweisen haben:

Raben: Diese flinken Himmelsbewohner reagieren empfindlich auf Geräusche und können bei einem Schuss schnell die Flucht ergreifen.

Füchse: Gerissene Jäger, die sich an ihre Umgebung anpassen und sowohl patrouillieren als auch sich unbemerkt ausruhen können.

Wölfe: Aggressive Raubtiere, die bei Sicht- oder Hörkontakt sofort in den Angriffsmodus übergehen.

Stickmans: Diese besonderen Gegner stellen eine zusätzliche Herausforderung dar und erfordern taktisches Vorgehen.

Begegne intelligenten Gegnern:
Die Tiere in "Desert Hunter" sind keine einfachen Ziele. Sie verfügen über unterschiedliche Routinen und Aggressionsstufen. Manche Tiere patrouillieren auf festgelegten Wegen, während andere sich entspannt in der Umgebung aufhalten, bis sie gestört werden.

Sei besonders vorsichtig bei den aggressiveren Tierarten:

Sie können dich angreifen, sobald sie dich sehen oder hören.

Jeder Angriff durch ein Tier führt zu einem Punktabzug, was taktisches Vorgehen und vorsichtiges Jagen belohnt.

Selbst scheinbar friedliche Tiere werden gefährlich, wenn du sie attackierst, und wehren sich vehement.

Dein Ziel:
Plane deine Jagd geschickt, nutze die Umgebung zu deinem Vorteil und behalte deine Punktzahl im Auge. Nur wer die Verhaltensweisen der Tiere versteht und präzise handelt, wird zum erfolgreichsten "Desert Hunter" aufsteigen!

## Spielbare Anwendung

Google Drive Ordner 
https://drive.google.com/drive/folders/1I3CtBBThj1Ybz90qsS_D30olLyEEX41g?usp=drive_link

Gezipter Ordner
https://drive.google.com/file/d/1eQGpSIOHs6QBpbMo-xqs2cmrhQh7BRw9/view?usp=drive_link

## Gameplay Video

https://drive.google.com/file/d/1T4G0pYN5Oz_aaj9HPmJzEc6k02wmkkwM/view?usp=drive_link

## Was gibt es für Eingabemöglichkeiten?

<img width="280" height="338" alt="image" src="https://github.com/user-attachments/assets/7c052bab-93cb-46ed-9643-191420bba37e" />

## Umgesetzte Features und Implementierungen
Im Rahmen der Entwicklung unseres Spiels haben wir eine Reihe von Features implementiert und bestehende Assets angepasst, um ein immersives und technisch solides Spielerlebnis zu gewährleisten. Unsere Hauptentwicklungsbereiche umfassen:

---

### 1. Ladebildschirm
Der Ladebildschirm wurde mittels des AsyncScreenLoading Assets implementiert. Dies ermöglicht die Anzeige von Spieltipps und anderen Informationen während des Ladevorgangs. Ein angepasster Screenshot aus dem Spiel dient als Hintergrundbild, um die Immersion zu fördern. Die notwendigen Einstellungen wurden direkt im Package konfiguriert.

---

### 2. Bildmaterial
Für die visuellen Elemente des Spiels wurden sowohl KI-generierte als auch lizenzfreie Bilder verwendet. KI-generierte Grafiken (z.B. für Projektile, UI-Symbole) wurden anschließend in GIMP nachbearbeitet, um deren Qualität und Passform zum Spielstil sicherzustellen.

---

### 3. Tutorial-System
Ein kurzes Tutorial führt Spieler in den ersten 30 Sekunden nach Spielstart in die grundlegende Steuerung ein. Die wichtigsten Tasten werden am linken Bildschirmrand visuell dargestellt. Hierfür wurde ein KI-generiertes Tastenbild als Basis verwendet und anschließend bearbeitet, um optimal ins UI zu passen. Die Integration erfolgte über ein UI Widget.

---

### 4. Akustisches Design
Es wurden lizensfreie Musik und Soundeffekte ausgewählt und in Animationen sowie Blueprints integriert.

Gegner-Sounds: Jeder Gegnertyp besitzt spezifische Sounds für Treffer, Tod, Angriffe und Bewegung. Diese sind als 3D-Sound implementiert und nur innerhalb eines definierten Radius hörbar, was zur räumlichen Wahrnehmung beiträgt.

Waffen-Sounds: Die Waffe verfügt über entsprechende Schuss und Ladegeräusche.

Spieler-Sounds: Der Spielercharakter ist mit eigenen Laufgeräuschen ausgestattet.

---

### 5. Künstliche Intelligenz (KI)
Die Gegner-KI basiert auf einem flexiblen Behavior Tree System.

Behavior Tree Basis: Ein Behavior Tree Base wurde entwickelt, der alle grundlegenden Funktionen wie Sterbelogik, Angriffslogik, Erkennungslogik, Passive Logik und Idle-Logik enthält. Von diesem können leicht modifizierte Behavior Trees für spezifische Gegnertypen abgeleitet werden.

Gegner-Basisklasse: Eine Enemy Base Klasse als Blueprint dient als Vorlage, von der individuelle Gegnerklassen (Childs) effizient erstellt werden können. Diese Basisklasse stellt zahlreiche Variablen zur Verfügung, die eine flexible Anpassung der Gegnertypen erlauben.

Animationen: Jeder Gegner verfügt über spezifische Animationen. Ein Animation Blueprint pro Gegner steuert die korrekte Wiedergabe basierend auf variablen Zuständen wie Speed und OnFocus. Animation Montages werden zur Steuerung von bestimmten Animationsabläufen innerhalb der Blueprints verwendet. Die Animationen und Meshes der Gegner stammen aus externen Assets; die Implementierung der Logik und deren Verdrahtung erfolgte jedoch intern.

Patrouillen-Systeme: Für Bodeneinheiten wurden Patrol Routen erstellt, die die Gegner ablaufen können, unter Verwendung von NavMesh. Flugeinheiten folgen fest definierten Pfaden, da sie kein NavMesh nutzen.

Intelligentes Verhalten: Spezifische Verhaltensweisen, wie das Ausruhen von Füchsen oder Wölfen bei längerer Inaktivität, wurden über Variablenlogik integriert.

AI Controller & AI Perception: Gegner sind mit einem AI Controller ausgestattet und nutzen AI Perception. Sie können den Spieler in einem bestimmten Sichtbereich erkennen und angreifen (Wolf, Fuchs, Stickman). Ihre Lebenspunkte und Punktwerte variieren je nach Stärke. Gegner reagieren auch auf Schussgeräusche; Raben fliegen beispielsweise erschrocken weg. Wird ein Gegner angeschossen, wechselt er in den Kampfmodus und greift den Spieler an.

Vielfältige Angriffe: Gegner können zwei unterschiedliche Angriffsarten nutzen, die zufällig wechseln.

Differenzierte Idle-Zustände: Es wird zwischen einem Kampf-Idle und einem normalen Idle Zustand unterschieden.

Spawning-Management: Eine maximale Anzahl von Gegnern pro Typ kann gleichzeitig auf der Karte existieren.

Bestrafungssystem: Wird der Spieler von einem Gegner getroffen, erhält er Minuspunkte.

Spezialeffekte für Raben: Abgeschossene Raben zeigen eine realistische Fallanimation, gefolgt von einer Aufprallanimation bei Kollision mit dem Boden.

Benutzerdefinierte KI-Komponenten: Für die Behavior Trees wurden eigene Tasks, Enums und Decorators entwickelt, um spezifische KI-Verhaltensweisen zu ermöglichen.

---

### 6. Waffen-System
Die Standardwaffe wurde durch ein angepasstes Asset ersetzt. Die Projektilfunktion der Waffe wurde durch ein Linecast-System modifiziert, was ein direkteres Shooter-Gefühl vermittelt. Ein integriertes Schadenssystem löst je nach getroffenem Material (Gras, Holz, Stein, Gegner) unterschiedliche Partikel-Effekte aus. Zusätzlich wurde ein Muzzle-Effekt (Mündungsfeuer) als Partikel-Effekt in die Waffe integriert.

Munition und Nachladen: Die Waffe verfügt über zwei Schuss. Nach dem Verbrauch der Munition ertönt ein "Waffe leer"-Sound, und der Spieler muss die Waffe manuell mit der Taste "R" nachladen.

Schuss-Cooldown: Ein Cooldown-System reguliert die Feuerrate der Waffe.

---

### 7. Spielkarte
Die Spielkarte wurde aus einem externen Asset entnommen und dient als Umgebung für das Spiel.

---

### 8. Spiellogik
Die Spiellogik ist bewusst einfach gehalten, sorgt jedoch für einen hohen Wiederspielwert.  
Vom Hauptmenü aus kann der Spieler eine neue Runde starten. In dieser hat er **2 Minuten Zeit**, um durch das Erlegen von Gegnern möglichst viele Punkte zu sammeln.  
Sollte der Spieler merken, dass die Runde schlecht läuft, kann er jederzeit **neustarten** und von Null beginnen.  
Nach Ablauf der Zeit wird das erzielte Ergebnis und der **High Score** gezeigt. Die höchste Punktzahl wird gespeichert, sodass der Spieler motiviert bleibt, seine eigene High Score zu übertreffen.

---

### 9. UI
Das User Interface umfasst verschiedene Bereiche:  

- **Hauptmenü**  
  - Startmenü  
  - Optionen  
  - Credits  

- **Während des Spiels**  
  - Anzeige der verbleibenden Zeit  
  - Aktuelle Punktzahl  
  - Waffe mit sichtbarer Munitionsanzeige (verbliebene Patronen werden ausgegraut)  
  - Fadenkreuz (Crosshair) zur Zielerfassung  
  - Kurzzeitige Darstellung der Steuerung als Tutorial  
  - Aufruf des Pausenmenüs über die Taste *ESC*  

- **Spielende**  
  - Automatisches Öffnen des Game-Over-Bildschirms mit Endstand  

---

### 10. Menü
Es gibt insgesamt **vier Menüs**:

- **Hauptmenü**  
  - *Start*: Spiel starten  
  - *Options*: Optionen öffnen  
  - *Credits*: Credits anzeigen  
  - *Quit*: Spiel beenden  

- **Optionsmenü**  
  - Einstellung der Renderqualität: *Low, Medium, High, Epic, Ultra*  
  - Aktivieren/Deaktivieren von **VSync**  
  - Zwei Audio-Slider:  
    - Musiklautstärke  
    - Soundeffekte  

- **Pausenmenü**  
  - *Resume*: zurück ins Spiel  
  - *Restart*: Runde neustarten  
  - *Main Menu*: zurück ins Hauptmenü  
  - *Quit*: Spiel beenden  

- **Game-Over-Menü**  
  - Anzeige der aktuellen Punktzahl  
  - Anzeige der High Score  
  - *Restart*: neue Runde starten  
  - *Main Menu*: zurück ins Hauptmenü  
  - *Quit*: Spiel beenden  


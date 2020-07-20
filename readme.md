# Orion 🪐

Orion ist ein Voice User Interface, welches dir ermöglicht mit Sprachbefehlen intuitiver und interaktiver durch deine Keynotes zu navigieren. Über die Erkennung von Keywords merkt die AI wann der richtige Zeitpunkt ist, um beispielsweise Videos abzuspielen, Datengrafiken anzuzeigen, oder Stichpunkte auf Folien zu ergänzen.



## Base Setup

Unser HTML/CSS JavaScript Prototyp besteht aus einer vorgefertigten Präsentation, welche auf das durchnavigieren mit Orion optimiert ist. Der Prototyp ist für Chrome optimiert, in anderen Browsern könnte es sein, dass gewisse Dinge nicht funktionieren. Ist die Präsentation in Chrome geöffnet, muss noch Zugriff auf das Mikrofon gewährt werden und die Präsentation ist bereit gestartet zu werden.

Die momentan aktuellste Version kann hier abgerufen werden: "!!!HIER AKTUELLSTEN LINK EINFÜGEN!!!"



## Interface

#### Play Button
Über den Play Button wird die Präsentation gestartet. Die Slides wechseln in den Fullscreenmodus und die Spracherkennung fängt an deinen Worten zu lauschen.

![play-button](/Users/swirth/Documents/Websites/VoiceControlledPresentation/voicerecognitionfinal/material/play-button.png)



#### Commands Index

Im Commands Index-Slider befindet sich eine Übersicht über alle Keywords/Commands, die von der Spracherkennung momentan erkannt werden. Dieser Slider dient als Gedankenstütze für den Fall, dass einmal ein Keyword/Command in Vergessenheit geraten sollte. 

![commands-index](/Users/swirth/Documents/Websites/VoiceControlledPresentation/voicerecognitionfinal/material/commands-index.png)



#### Overview Button

Klickt man den Overview-Button, zoomt der Viewport so weit heraus, dass man alle Slides in der Übersicht sehen kann. Klickt man in dieser Ansicht auf einen Slide, wird dieser herangezoomt.

![overview-button](/Users/swirth/Documents/Websites/VoiceControlledPresentation/voicerecognitionfinal/material/overview-button.png)



#### Folienübersicht

In dieser Leiste sind alle Slides der Reihe nach aufgelistet, ähnlich wie in Programmen wie Powerpoint oder Keynote. Klickt man auf eines dieser Vorschau-Bilder, wird dieser   Diese Leiste kann mit einem Klick auf das Icon oben rechts versteckt werden.

![folienuebersicht](/Users/swirth/Documents/Websites/VoiceControlledPresentation/voicerecognitionfinal/material/folienuebersicht.png)



#### Erkannte Keywords

Im Footer wird bei aktivem Präsentationsmodus angezeigt, was unsere Voice-Recognition verstanden hat. So lässt sich nachvollziehen was möglicherweise schief gelaufen ist, falls nicht der gewünschte Befehl ausgeführt wird.

![erkannte-keywords](/Users/swirth/Documents/Websites/VoiceControlledPresentation/voicerecognitionfinal/material/erkannte-keywords.png)



#### Voice Feedback

Unten Rechts befindet sich eine Visualisierung des Mikrofon-Inputs. Wenn der Präsentationsmodus aktiv ist, startet auch diese Animation und signalisiert damit, dass die Voice Recognition aktiv ist.

![voice-feedback](/Users/swirth/Documents/Websites/VoiceControlledPresentation/voicerecognitionfinal/material/voice-feedback.png)



## Commands

#### Navigation
Teil der grundlegenden Navigation ist “next slide” um eine Folie weiterzugehen, “previous slide” um eine Folie zurück zu springen. Außerdem gibt es einen “Overview” bei dem das ganze Canvas mit allen Folien sichtbar wird. Man kann jederzeit die Präsentation von neu starten wenn man “Start from the beginning” sagt. Die letzte Folie wird mit “bring me to the end” oder “last slide” aufgerufen. Man kann die Präsentation abbrechen in dem man “stop presentation sagt.



#### Specific Navigation
Spezifische Navigation besteht daraus gezielt Slideinhalte zu nennen wie “go to the Quote”.



#### Speak
Bei Kommandos wie “read the quote” ließt Orion dir Folieninhalte oder Stichpunkte zu. Er kann auch Denkanstöße während des Präsentieren geben durch “tell me something”.



#### Assist
Orion schreibt Gedanken und Stichpunkte auf die ausgewählte Folie durch “please write down_" und löscht Stichpunkte von den Folie mit “delete_”.



#### Find
Durch die Suchfunktion “search for_” kann Orion die Präsentation auf geschriebenen und bildlichen Inhalt durchsuchen.
Um innerhalb der Suche zu Navigieren gibt es die Kommandos “next result” oder “previous result”. “Exit search” beendet den Suchmodus und die Ansicht ist wieder auf Standart. Oben rechts wird angezeigt wie viele Suchresultate gefunden wurden und bei welchem Resultat, dass man sich gerade befindet.

![search](/Users/swirth/Documents/Websites/VoiceControlledPresentation/voicerecognitionfinal/material/search.png)



## Code

#### HTML

Alle Slides werden im HTML index.html erzeugt.
Das <div> der id=“impress” beinhaltet alle Slides. Um einen neuen  Slide zu generieren füge ein neues Div innerhalb von id=“impress” hinzu. 

Das jeweilige Slide-DIv bekommt eine individuelle ID sowie die Klasse “step box”. Mithilfe der Attribute “data-x” und “data-y” plazierst du den Slide auf dem Canvas.

Innerhalb des Slide-Divs können Tags wie <h>, <p>, <img> usw. eingefügt und verwendet werden.

Erzeugung eines Beispielslides:

```html
<!-- all slides -->
<div id="impress" data-max-scale="4" data-width="1000" data-height="650">

  <!-- new slide -->
  <div id="slidename" class="step box" data-x="0" data-y="0">
    <p>Title</p>
    <img id="titleimage" src="images/title.png" width="100%">
  </div>
</div>
```



#### JavaScript

Alle Befehle werden in JavaScript bzw in der Datei vocerecognition_script.js erzeugt. 

Die Variable “myGroup” beinhaltet dabei ein Array aller definierten Voice Commands. 

Jeder einzelne Command besteht dabei aus einem Objekt.

In diesem Bespiel nennt sich das Objekt bzw. der Befehl “nextSlide”.

Jeder Befehl benötigt indexes, welche die Keywords des Befehls definieren. In diesem Beispiel sind das “next slide please”, "next slide" und “next please”. Mithilfe dieser Keywords wird der Befehl getriggert und die Aktion ausgeführt.

Unter action: wird die, beim Befehl jeweils auszuführende Funktion, notiert.

```javascript
// all voice commands
var myGroup = [

  //one specific voice command
  nextSlide = {
    indexes: ["next slide please", "next slide", "next please"],
    action: function() {
      var api = impress();
      api.init();
      api.next();
    }
  }
]
```



## Ressources

**Impress.js** *Impress.js is a presentation framework based on the power of CSS3 transforms and transitions in modern browsers and inspired by the idea behind prezi.com* (link: https://github.com/impress/impress.js/ text: https://github.com/impress/impress.js/)

**Artyom.js** *Artyom.js is an useful wrapper of the speechSynthesis and webkitSpeechRecognition APIs. Besides, artyom.js also lets you add voice commands to your website.*
(link: https://sdkcarlos.github.io/sites/artyom.html text: https://sdkcarlos.github.io/sites/artyom.html)

**HR.js** *HR.js is a tiny JavaScript plugin for highlighting and replacing text in the DOM* (link: https://mburakerman.com/hrjs/ text: https://mburakerman.com/hrjs/)

**Ml5 Image Classifier** *With the ml5 Image Classifier you can use neural networks to recognize the content of images. ml5.imageClassifier() is a method to create an object that classifies an image using a pre-trained model.*(link: https://learn.ml5js.org/docs/#/reference/image-classifier text: https://learn.ml5js.org/docs/#/reference/image-classifier)

**Fuse.js** *Fuse.js is a powerful, lightweight fuzzy-search library, with zero dependencies.* (link: https://fusejs.io/ text: https://fusejs.io/)

**Lodash.js** *Lodash.js is a modern JavaScript utility library delivering modularity, performance & extras.* (link: https://lodash.com/ text: https://lodash.com/)

**Teachable Machine** *Teachable Machine is a fast and easy way to create machine learning models for your sites, apps, and more – no expertise or coding required.* (link: https://teachablemachine.withgoogle.com/ text: https://teachablemachine.withgoogle.com/)
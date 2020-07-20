# Orion 🪐

Orion ist ein Voice User Interface, welches dir ermöglicht mit Sprachbefehlen intuitiver und interaktiver durch deine Keynotes zu navigieren. Über die Erkennung von Keywords merkt die AI wann der richtige Zeitpunkt ist, um beispielsweise Videos abzuspielen, Datengrafiken anzuzeigen, oder Stichpunkte auf Folien zu ergänzen.



## Base Setup

Unser HTML/CSS JavaScript Prototyp besteht aus einer vorgefertigten Präsentation, welche auf das durchnavigieren mit Orion optimiert ist. Der Prototyp ist für Chrome optimiert, in anderen Browsern könnte es sein, dass gewisse Dinge nicht funktionieren. Ist die Präsentation in Chrome geöffnet, muss noch Zugriff auf das Mikrofon gewährt werden und die Präsentation ist bereit gestartet zu werden.

Die momentan aktuellste Version kann hier abgerufen werden: "!!!HIER AKTUELLSTEN LINK EINFÜGEN!!!"



## Interface

#### Play Button
Über den Play Button wird die Präsentation gestartet

#### Commands Index

#### Overview Button

#### Folienübersicht

#### Erkannte Keywords

#### Voice Feedback





## Commands

Navigation

Specific Navigation

Speak

Assist

Find







## Code

Alle Slides werden im HTML index.html erzeugt.
Das <div> der id=“impress” beinhaltet alle Slides. Um einen neuen  Slide zu generieren füge ein neues Div innerhalb von id=“impress” hinzu. 

Das jeweilige Slide-DIv bekommt eine individuelle ID sowie die Klasse “step box”. Mithilfe der Attribute “data-x” und “data-y” plazierst du den Slide auf dem Canvas.

Innerhalb des Slide-Divs können Tags wie <h>, <p>, <img> usw. eingefügt und verwendet werden.

Erzeugung eines Beispielslides:

<!-- all slides -->

<div id="impress" data-max-scale="4" data-width="1000" data-height="650">

  <!-- new slide -->
  <div id="slidename" class="step box" data-x="0" data-y="0">
    <p>Title</p>
    <img id="titleimage" src="images/title.png" width="100%">
  </div>

</div>

CSS

JS





## Ressources

**Impress.js** *Impress.js is a presentation framework based on the power of CSS3 transforms and transitions in modern browsers and inspired by the idea behind prezi.com* (link: https://github.com/impress/impress.js/ text: https://github.com/impress/impress.js/)

**Artyom.js** *Artyom.js is an useful wrapper of the speechSynthesis and webkitSpeechRecognition APIs. Besides, artyom.js also lets you add voice commands to your website.*
(link: https://sdkcarlos.github.io/sites/artyom.html text: https://sdkcarlos.github.io/sites/artyom.html)

**HR.js** *HR.js is a tiny JavaScript plugin for highlighting and replacing text in the DOM* (link: https://mburakerman.com/hrjs/ text: https://mburakerman.com/hrjs/)

**Ml5 Image Classifier** *With the ml5 Image Classifier you can use neural networks to recognize the content of images. ml5.imageClassifier() is a method to create an object that classifies an image using a pre-trained model.*(link: https://learn.ml5js.org/docs/#/reference/image-classifier text: https://learn.ml5js.org/docs/#/reference/image-classifier)

**Fuse.js** *Fuse.js is a powerful, lightweight fuzzy-search library, with zero dependencies.* (link: https://fusejs.io/ text: https://fusejs.io/)

**Lodash.js** *Lodash.js is a modern JavaScript utility library delivering modularity, performance & extras.* (link: https://lodash.com/ text: https://lodash.com/)

**Teachable Machine** *Teachable Machine is a fast and easy way to create machine learning models for your sites, apps, and more – no expertise or coding required.* (link: https://teachablemachine.withgoogle.com/ text: https://teachablemachine.withgoogle.com/)
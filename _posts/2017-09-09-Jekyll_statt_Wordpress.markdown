---
layout: 	   post
title:  	   "Jekyll statt Wordpress"
date:   	   2017-09-09 14:45:12
duration:	   3
categories:  [Blog]
tags: 		   [Blog, Wordpress, Jekyll, Staticman]
---

`Am Anfang war die Idee … und weil die Idee so "innovativ" war, fand sie im Cyberspace ihre Schöpfung.`

* Braucht das Internet noch einen Blog?
* Braucht Internet meinen Blog?

Wie dem auch sei, jetzt sitze ich hier und tippe, wie es dazu kam ...   

Da mich ein paar Gedanken verfolgten und ich diese online nicht vorfinden konnte, kam ich dazu, einen eigenen Blog zu eröffnen. Die Zeit, auf die ich sehr gespannt bin, wird den Eindruck offenbaren.

Also los geht es.   

## Die Themen ...
... waren durch die o.g. Gedanken gesetzt:
* IT-Architektur
* BPM
* Enterprise Architecture
* Java


## Technologieauswahl
[Wordpress][wordpress] ist quasi der Standard für Blogs und ich habe mich für [Jekyll][jekyll] entschieden. Ungefär aus folgenden Gründen:
* Kein Datenbank-Server notwendig
* Phänomenal einfacher Template-Mechanismus
* Nur statische Inhalte
* [GitHub Pages][githubpages] und [GitLab Pages][gitlabpages] unterstützen [Jekyll][jekyll] jeweils mit eigener Deployment Pipeline

Online gibt es etliche Artikel, die Argumente pro [Jekyll][jekyll] bringen. Zum Beispiel vom [smashingmagazine].  

## [Discus][discus] vs. [Staticman][staticman]
Doch wie sieht es mit den Kommentaren aus? Sind Kommentare nicht DER Grund, einen Blog aufzusetzen – um die Rückmeldungen auf eigene Gedanken von der Community zu erhalten?! `Web 2.0`.  
Aber nur wegen der Kommentarfunktion doch [Wordpress][wordpress], das dynamische Inhalte ermöglicht, zu betreiben ...?  

Die nächste Recherche folgte: `Kommentare für Jekyll Seiten`.  
Treffer:
* [`Discus`][discus]
   * Speichert über eigenes SAAS in USA die Kommentare in Übersee je Seite (URL) und lädt diese innerhalb eines eigebetteten Div.
* [`Staticman`][staticman]
   * Betreibt einen Git Push Dienst bei dem jeder Kommentar als neue Datei auf die entsprechenden Pfade im Seiten-Quellcode auf GitHub Repository der Seite gespeichert wird. GitHub realisiert Änderungen und startet ein neues Deployment.

Ich bevorzuge [staticman] weil es `cool` ist. ITler mögen komplexe Abläufe! Außerdem liegen alle Kommentare dann in Sourcecode, was im Vergleich zum [discus] tatsächlich um ein Vielfaches besser ist.  

## [GitLab Pages][gitlabpages] vs. [GitHub Pages][githubpages]
Interessant ist, dass im [GitLab Pages][gitlabpages] vs. [GitHub Pages][githubpages] eigentlich GitLab weitaus mehr Funtkionen und eine moderne CI-Pipeline anbietet, aber dafür im Zusammenspiel mit [staticman] nicht in Frage kommt, da ein neues Deployment aufgrund des gesamten Docker-Containers mehrere Minuten benötigt.  
Beim [GitHub Pages][githubpages] sind es nur wenige Sekunden.  

Probiere es mal aus, und hinterlasse einen Kommentar.
1. Im Hintergrund wird [staticman] public Service mit dem HTTP POST Formular aufgerufen, das wiederum per `git push` für deinen Kommentar eine neue Datei ablegt. Siehe [GitHub Comments Repository][githubcomments].
2. GitHub startet ein neues Deployment und ...
3. ... wenn du die Seite neu lädst, sollte dein Kommentar erscheinen.

## Fazit
Nachdem die Kommentarfunktion eingebettet war, ist der Rest schnell erledigt. Mir hat das Aufsetzten Spass bereitet und der Gedanke, wie einfach ein neuer Blog-Post (nachdem der Blog steht) hinzugefügt werden kann, bereitet mir umso mehr Freude. Ich hoffe, dass auch für Dich etwas Lesenswertes dabei zu finden sein wird.

[smashingmagazine]:   https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/
[discus]:             https://disqus.com
[staticman]:          https://staticman.net/
[githubcomments]:     https://github.com/azabdi/azabdi.github.io/tree/master/_data/comments/
[githubrepo]:         https://github.com/azabdi/azabdi.github.io
[githubpages]:        https://pages.github.com/
[gitlabpages]:        https://gitlab.com/pages
[wordpress]:          https://de.wordpress.com/
[jekyll]:             http://jekyllrb.com/

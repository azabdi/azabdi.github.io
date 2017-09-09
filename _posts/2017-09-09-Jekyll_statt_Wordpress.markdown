---
layout: post
title:  "Jekyll statt Wordpress"
date:   2017-09-09 14:45:12
categories: [Blog]
tags: [Blog, Wordpress, Jekyll, Staticman]
---

`Am Anfang war die Idee … und weil die Idee so innovativ war fand sie im cyber space ihre Schöpfung.`

* Braucht Internet noch ein Blog? 
    * Hm. 
* Braucht Internet mein Blog? 
    * Hm?!  

Wie dem auch sei, jetzt sitze ich hier und tippe wie es dazu kam ...   

Da mich paar Gedanken verfolgten und ich diese online nicht vorfinden konnte kam ich auch dazu eigenes Blog zu eröffnen. Die Zeit, auf der ich sehr gespannt bin, wird den "Schaden" offenbaren.

Also log geht es.   

## Themen 
... waren durch die o.g. Gedanken gesetzt:
* IT-Architektur
* BPM
* Enterprise Architecture
* Java 


## Technologieauswahl
[Wordpress][wordpress] ist der quasi Standard für Blogs und ich habe mich für [Jekyll][jekyll] entschieden. Ungefähr aus folgenden Gründen:
* Kein Datenbank-Server notwendig
* Fenomenal-einfaches Template-Mechanismus
* Nur statische Inhalte
* [GitHub Pages][githubpages] und [GitLab Pages][gitlabpages] unterstützen [Jekyll][jekyll] jeweils mit eigener Deployment Pipeline

Online sind etliche Artikel die Argumente pro [Jekyll][jekyll] bringen. Zum Beispiel vom [smashingmagazine].  

## Discus vs. Staticman
Doch wie sieht es mit den Kommentaren aus. Sind Kommentare nicht DER Grund ein Blog aufzusetzen – um die Rückmeldungen auf eigenen Gedanken von der gequellten community zu erhalten?! `Web 2.0`.  
Aber nur wegen der Kommentarfunktion doch [Wordpress][wordpress], das dynamische Inhalte ermöglicht, zu betreiben?  

Also die nächste Recherche: `Kommentare für [Jekyll][jekyll] Seiten`.  
Treffer:
* [`Discus`][discus]
   * Speichert über eigenes SAAS in USA die Kommentare im Übersee je Seite (URL) und lädt diese innerhalb eines eigebetteten Div‘s. 
* [`Staticman`][staticman]
   * Betreibt ein Git Push Dienst bei dem jeder Kommentar als neue Datei auf das entsprechende Pfade im Seiten-Quellcode auf GitHub Repository der Seite gespeichert wird. GitHub merkt Änderung und startet neues Deployment. Quasi vom Hinten durch die Brust.

Also doch [staticman] weil es sehr `cool` ist. IT’ler mögen komplexe Abläufe! Und, alle Kommentare liegen dann in Sourcecode was im Vergleich zum [discus] tatsächlich um vielfaches besser ist.  

## [GitLab Pages][gitlabpages] vs. [GitHub Pages][githubpages]
Interessant das im [GitLab Pages][gitlabpages] vs. [GitHub Pages][githubpages] eigentlich GitLab weitaus mehr Funtkionen und eine moderne CI-Pipeline anbietet, aber dafür im Zusammenspiel mit staticman nicht in Frage kommt da neues Deployment aufgrund des gesamten Docker-Kontainers mehrere Minuten benötigt.  
Beim [GitHub Pages][githubpages] sind es nur wenige Sekunden.  

Probiere es mal aus, und hinterlasse einen Kommentar. 
1. Im Hintergrund wird staticman public Service mit dem HTTP POST Formular aufgerufen das wiederum per `git push` für dein Kommentar neue Datei ablegt. Siehe [GitHub Comments Repository][githubcomments].
2. GitHub startet neues Deployment und ... 
3. wenn du die Seite neu lädst sollte dein Kommentar erscheinen. 

## Fazit
Nachdem die Kommentarfunktion eingebetet war ist der Rest schnell erledigt. Mir hat das aufsetzten Spass bereitet und der Gedanke wie einfach ein neuer Blog-Post nachdem der Blog steht hizugefügt werden kann, bereitet mir umso mehr Freude. Ich hoffe das auch für Dich was Lesenswertes dabei zu finden sein wird.


Vielen Dank für deine Zeit und viele Grüße,  
[Azmir Abdi][about]


[smashingmagazine]:   https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/
[discus]:             https://disqus.com
[staticman]:          https://staticman.net/
[githubcomments]:     https://github.com/azabdi/azabdi.github.io/tree/master/_data/comments/
[githubrepo]:         https://github.com/azabdi/azabdi.github.io
[githubpages]:        https://pages.github.com/
[gitlabpages]:        https://gitlab.com/pages
[wordpress]:          https://de.wordpress.com/
[jekyll]:             http://jekyllrb.com/
[about]:              /about/
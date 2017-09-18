---
layout: post
title:  "BPM und Microservices"
date:   2017-09-17 18:57:07
categories: [BPM]
tags: [BPM, Microservices, Enterprise Architecture, SOA, Reverse BPM, BPM Reverse Engineering]
published: true
---
Steht klassisches Business Process Management (BPM) im Wiederspruch zu der IT-Architektur nach dem Microservices-Ansatz? Der korrekte Microservices-Ansatz erlaubt keine zentrale unternehmensweite Prozesssteuerungskomponente!  

## BPM und SOA
Business Process Management (BPM) ist ein vollumfänglicher Ansatz der Unternehmensorganisation konzentriert auf die kontinuierliche Optimierung und damit auf die Gewinnmaximierung des Kerngeschäfts. Dabei wird das Kerngeschäft in die End-To-End Geschäftsprozess(e) gegliedert die komplette Eigenleistung von dem Kunden-Auftrag bis zu der abschließenden Kunden-Lieferung umfasst.  

Die IT gestützte Lösung des BPM’s sind die BPM-Systeme (BPMS) bei denen die End-To-End Geschäftsprozesse durch integrierte zentrale Business Process Engines (BPE) automatisiert gesteuert werden.  

BPM Ansatz spielt hervorragend mit der Serviceorientierten Architektur (SOA) als Enterprise-SOA zusammen wie im Artikel der computerwoche vor über 10 Jahren beschrieben wurde. Mittlerweile wissen wir das SOA in der ursprünglichen Form bereits veraltet ist. Das neue maßgeblich vom [Martin Fowler][martinfowler] entworfene Microservices-Ansatz ist die nächste Evolutionsstufe der Enterprise Architecture.

## SOA vs. Microservices
>Sind Microservices keine SOA?   

SOA ist, genauso wie die Microservices, eine Antwort auf unwartbare komplexe monolithische IT. Im Vordergrund bei SOA steht die Beherrschung der Komplexität durch Strukturen.  Auch im Fokus ist die Optimierung der IT durch Eliminierung der Verschwendung mittels mehrfacher Problemlösungen. Jedes Problem soll unternehmensweit einmalig zentral gelöst werden. Die Lösung wird intern publiziert und es wird geachtet das diese wiederverwendet wird. 
SOA setzt auf Wiederverwendung. Wiederverwendung von Services. Zentrales Domain Model. Enterprise Service Bus (ESB) als zentrale intelligente Integration verbindet die Services. Die gesamte Unternehmensarchitektur ist im Schichten Organisiert wie von Herrn Slama im [computerwoche] Artikel dargestellt:
 
![Enterprise SOA][soa][`Quelle  computerwoche Dirk Slama`][computerwoche]


BPMS als Zusatz übernimmt Teilweise die Serviceorchestrierung die gewöhnlich über ESB stattfindet. BPM kann damit als erweitertes SOA betrachtet werden.

Die Unterschiede des SOA-Ansatzes zu den Microservices sind signifikant!   
Matt McLarty hat in seinem [Artikel][mattmclarty] die Abgrenzung der Microservices zu SOA in unterschiedlichen Perspektiven sehr detailliert dargestellt. Einer der Widersprüche von SOA und BPM zu den Microservices-Ansatz liegt genau beim ESB. Microservices-Ansatz setzt auf leichtgewichtige Integration. *smart endpoints and dumb pipes Prinzip wird als Folge der Anwendung des [Conway’s Gesetzes][conway]  vorgeschrieben. 

Nach [Conway][conway] werden die IT-Systeme unweigerlich nach den Kommunikationsstrukturen des Unternehmens organisiert. Wie oft kommt es vor das ein Unternehmen eine Organisationseinheit hat die in der IT vom ESB abgebildet werden kann. Ein Team mit Aktentransportwägen ausgestattet mit einem mobilen Arbeitsplätzen (Laptop + Drucker) wobei die Akten unterwegs für die nächste Abteilung im Zielformat übersetzt werden.
… tbd …


> Ein kulturelles Umdenken (in BPM) ist notwendig  

Sowohl SOA als auch BPM gehen von der zentralen Planung und Steuerung aus. Nun, was soll schon daran falsch sein ein Unternehmen zentral zu planen und zu steuern? Schließlich haben alle Unternehmen genau hierfür das Management das zentral plant und steuert!
Ist es so? Steuern die Manager die Umsetzung direkt? Ohne der Zwischenebenen?
Oder ist es nicht so dass bei erfolgreichen Unternehmen das Management die Leitplanken mittels der Vision und der Mission setzt. Daraus folgen Ziele die durch die Teams angegangen werden. Wie viele Pläne werden in einem Unternehmen erzeug um diese Ziele zu erreichen? Die Ziele werden, und damit auch die Pläne, herunter auf die fachliche Einheiten gebrochen, die man besser greifen kann? 
Erfolgreiche Unternehmen leben es vor. Agile Teams versuchen eigene abgeleitete Ziele mittels eigener Planung und mit der integrierten Optimierungsbestrebung (Retrospektive, … todo) diese optimal zu erreichen. Das Management begnügt sich mit dem regelmäßigen Rückmeldungen der Ergebnisse aus den Teams heraus (Reporting) um zu prüfen ob sich das Unternehmen im Gesamtsicht (Big Picture) auf dem richtigen Kurs befindet. 
Andersherum betrachtet könnte man sagen dass SOA und BPM richtig am Platz sind im Unternehmen bei denen jeder Schritt nach der zentralen Planung haargenau umgesetzt werden muss. Wo keine ungeprüften Optimierungsaktionen der Einzelnen zugelassen sind. Vielleicht in der Nuklearindustrie?!
Die meisten Unternehmen wollen eigentlich von der Erfahrung eigener Mitarbeiter profitieren.  Für die IT heißt dies mehr Agilität zulassen. Änderungen schneller zulassen. 

>Die Antwort auf die Veränderung-Anforderung ist der Microservices-Ansatz.  

Keine zentrale monolithische IT sondern kleine sauber nach Fachlichkeit getrennte Applikationen die zu den Umsetzungsteams genau passen und auch in der heutigen Welt der Agilität auch im Stande sind im Gleichschritt mitgehen zu können.
* Microservices-Ansatz ist die Antwort auf die NFR Anforderung: Änderungen schnell umsetzen.
Dieser Artikel möchte sich nicht damit befassen wie diese Agile Architektur erreicht werden kann, dafür gibt es bereits einige Veröffentlichungen. Zum Beispiel das Buch vom Eberhard Wolff aber auch die Artikeln über die Self-Contained Systems die eine konkrete genauere Umsetzung des Microservices-Ansatzes beschreiben. Das neue Organisationsstichwort hier ist BizDevOps. 
In diesem Artikel geht es um BPM. Wo bleibt BPM in dieser neuen agilen Welt der Microservices?


> Genauso wie die Staaten erkannt haben das die zentrale Planung noble Ziele verfolgt, in der Umsetzung aber niemals gegenüber der freien Wirtschaft ankommen kann.  So müssen auch die IT Strukturen frei werden. 

Für BPM würde das bedeuten dass es keine zentrale Steuerungskomponente der End-To-End Prozessen geben darf. Wo möglich auch keine zentrale Planung. 
BPM besagt das die End-To-End Prozesse in einem Unternehmen analysiert, erfasst, gesteuert, überwacht und optimiert werden. Die Unternehmen die dies IT gesteuert umsetzen werden nach ISO-9000 oder nach CMMI auf dem höchstem Level zertifiziert. Wie die Umsetzung aussehen soll ist es frei überlassen, dennoch belehrt BPM das die Prozesssteuerung aus einem BPMS System das eine BPE integriert erfolgen soll.

> Hier muss BPM umdenken und der IT die Konzeption der Umsetzung überlassen. 

Die Forderung nach einer zentralen Steuerung soll der Forderung nach einer zentralen automatisierten Prozessauswertung weichen. 
Wie gesagt, dem Management reicht es in regelmäßigen Abständen die Ergebnisse zu berichten. BPM soll die Umsetzung der Prozessdigitalisierung frei stellen. Lediglich die Berichterstattung soll verpflichtend sein. 
Für gewöhnlich werden die Projekte höher Priorisiert die dem Kerngeschäft dienen. Somit konzentriert sich ein Unternehmen an sich bereits mit der Optimierung des Kerngeschäfts. BPM kann unterstützen wenn die Prozesstrasparenz aufgrund der Komplexität und der Unternehmensgröße leidet. BPM soll die Prozesse sichtbar machen und die Optimierungspotentiale im Sinne der Unternehmensziele aufdecken. Aber auch die unnötige Verschwendung die nicht diese Zielen dient aufdecken. 
/// Aufgrund dessen ist die Umsetzung der Optimierung ein quick win. 


## Reverse BPM
Genau die Schritte (Tasks) die in der manueller BPM Analyse-Phase (IST Erfassung) geschehen sollen, sollten automatisiert werden. Die IT Systeme sollen die fachliche Events melden. Und das nicht einmal, sondern ständig, für jede Prozessinstanz. Für welches Prozess wird gerade was gemacht und für welche Prozess-Instanz in welcher Version.
BPM Reverse Engineering
Genauso wie [Operational Intelligence] nur an BPM angewandt soll BPM nicht mit die IT steuern, sondern die Informationen sammeln und reagieren. Es ist nicht tragisch wen kurzfristig Prozesse nicht vollkommen nach dem zentralen Plan laufen. Oft ist der Plan einfach nicht vollständig. Dadurch dass die IT auf Veränderung ausgelegt ist lässt sich diese IST-SOLL Diskrepanz schnell beseitigen.
•	IT Datenquellen und fachliche Events erzeugen
o	Eventuell. Daten aus Big-Data Speichern
•	Mit Operational Intelligent in fast Echtzeit Prozessinformationen generieren
•	BPM Reverse Engineering aus Prozessinformationen Prozessmodel nach BPMN generieren
•	Mit der Streaming Technologie in fast Echtzeit sowohl Prozessinformationen als auch Modeldarstellung live darstellen 
•	Bei der SOLL-IST Abweichungen sollen fachliche Benachrichtigungen erzeugt werden können
Folgende Antworten soll BPM Reverse Engineering geben:
•	Welche Prozesse existieren im Unternehmen
•	Wie laufen diese ab
o	
o	Graphische Darstellung nach BPMN ausgehend von den Daten
•	Die gesamte Statistik über die Prozesse
•	Prozessbewertung nach KPIs
Die Optimierung geschieht in dem die durch BPM aufgezeigte Schwächen und Potentiale einfach in dem Änderungsprozess aufgenommen werden.

Der Prozessowner kann das neue SOLL Model im BPM System für den SOLL-IST vergleich aufnehmen.
Die Entwicklung und Test können diesen Vergleich als Akzeptanzkriterium nutzen. Die Angleichung von IST und SOLL, soll auf Entwicklungs- und Testumgebung erfolgen. Produktiv sollten dann keine größeren Überraschungen erfolgen.
Der Unterschied liegt darin das beim Reverse Engineering BPM das BPM System die Prozesse nachgelagert nach dem Ablauf ständig analysiert und falls vorhanden mit einem SOLL/PLAN Model vergleicht. BPM ist nicht führend bei der Prozesssteuerung sondern dafür sind die jeweiligen beteiligten Fachapplikationen allein zuständig.

Wie beim klassischen BPM wäre beim Reverse BPM die Auswertung der Testergebnissen der End-To-End Prozesse in einer Testumgebung innerhalb des BPM-Systems möglich. Lediglich die das antriggern der manuellen Tasks für Tests müsste über einen gesonderten Test-Trigger erfolgen. 

Für die IT Architektur würde das bedeuten das die Implementierung der einzelnen Prozessschritte/Tasks in den Microservices frei jedem Team überlassen werden kann, just nach der Empfehlung von [Martin Fowler][martinfowler}. Keine Vorgaben der Technologien. Freie Umsetzung der Optimierungen und freie Entwicklung der ... tbd
  






[computerwoche]:     https://www.computerwoche.de/a/soa-und-bpm-wachsen-zusammen,1219234 
[soa]:               /images/posts/2017-09-17-BPM-und-Microservices/EnterpriseSOA_DirkSlama_20170508.jpg
[martinfowler]:      https://martinfowler.com/
[mattmclarty]:       https://www.infoworld.com/article/3080611/application-development/learning-from-soa-5-lessons-for-the-microservices-era.html
[conway]:            https://de.wikipedia.org/wiki/Gesetz_von_Conway
[scs]:               http://scs-architecture.org/
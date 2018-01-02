---
layout: 	  post
title:  	  "BPM und Microservices"
date:   	  2018-01-07 10:57:08
duration:	  15
categories: [BPM]
tags: 		  [BPM, Microservices, Enterprise Architecture, SOA, Reverse BPM, BPM Reverse Engineering]
published: 	false
---
Steht klassisches Business Process Management (BPM) im Widerspruch zur IT-Architektur nach dem Microservices-Ansatz? Der korrekte Microservices-Ansatz erlaubt keine zentrale unternehmensweite Prozesssteuerungskomponente!  

Dieser Post schildert, wie eine korrekte Implementierung von BPM Systemen nach Microservices-Ansatz aussehen müsste. Um darauf eingehen zu können wird im ersten Teil auf die Begriffe BPM, SOA und Microservices, deren jeweilige Motivation sowie die Unterschiede zwischen SOA und Microservice eingegangen. Im zweiten Teil wird das auf Microservices-Ansatz angewandte, leicht angepasste BPM als ***rBPM*** präsentiert.   

## BPM, SOA und Microservices
Business Process Management (BPM) ist ein vollumfänglicher Ansatz der Unternehmensorganisation, konzentriert auf die kontinuierliche Optimierung und damit auf die Gewinnmaximierung des Kerngeschäfts. Dabei wird das Kerngeschäft in die End-To-End Geschäftsprozess(e) eingegliedert, die komplette Eigenleistung vom Kunden-Auftrag bis zu der abschließenden Kunden-Lieferung umfasst.  

Die IT-gestützte Lösung des BPM sind die BPM-Systeme (BPMS) bei denen die End-To-End Geschäftsprozesse durch integrierte zentrale Business Process Engines (BPE) automatisiert gesteuert werden.  

Der BPM Ansatz spielt hervorragend mit der Serviceorientierten Architektur (SOA) als Enterprise-SOA zusammen, wie im Artikel der [computerwoche] vom Herrn Slama vor über 10 Jahren beschrieben wurde. Mittlerweile wissen wir, dass SOA in der ursprünglichen Form bereits veraltet ist. Der neue, maßgeblich von [Martin Fowler][martinfowler] entworfene Microservices-Ansatz ist die nächste Evolutionsstufe der Enterprise Architecture.

### SOA vs. Microservices
* `Sind Microservices keine SOA?`   

SOA ist, genauso wie die Microservices, eine Antwort auf die nicht wartbare komplexe monolithische IT. Bei SOA steht im Vordergrund die Beherrschung der Komplexität durch Strukturen. Auch im Fokus ist die Optimierung der IT durch Eliminierung der Verschwendung durch mehrfach implementierte Problemlösungen mit Hilfe der Wiederverwendung. Jedes Problem soll unternehmensweit einmalig gelöst werden. Die Lösung wird intern publiziert und es wird geachtet, dass diese wiederverwendet wird.  

>SOA setzt auf Wiederverwendung.  

Die Wiederverwendung von Services, die ein zentrales Domain Model nutzen, ist bei SOA maßgeblich. Enterprise Service Bus (ESB) als zentrale intelligente Integrationskomponente verbindet die Services. Die gesamte Unternehmensarchitektur ist in Schichten organisiert, wie in der folgenden Abbildung beispielhaft dargestellt:

![SOA][image_soa]  
`Abbildung 1. Serviceorientierte Architektur (SOA)`

BPMS als Zusatz übernimmt teilweise die Serviceorchestrierung, die gewöhnlich über ESB stattfindet. BPM kann damit auf SOA nativ angewandt werden.

Die Unterschiede zwischen dem, wie SOA zuletzt verstanden wurde und dem Microservices-Ansatz sind signifikant! **Matt McLarty** hat in seinem [Artikel][mattmclarty] die Abgrenzung der Microservices zu SOA sehr lesenswert geschildert. Einer der Widersprüche von SOA und BPM zum Microservices-Ansatz liegt genau beim ESB. Microservices-Ansatz setzt auf leichtgewichtige Integration. Mit dem **smart endpoints and dumb pipes** Prinzip soll statt monolithischer EAI, wie ESB bei SOA angewandt wird, die im SOA angepriesene Abkapselung der Systeme endlich Wirklichkeit werden. Dafür spricht auch der [Conway’s Gesetz][conway] an dem sich der Microservices-Ansatz orientiert.

Nach [Conway][conway] werden die IT-Systeme unweigerlich nach den Kommunikationsstrukturen des Unternehmens organisiert. Das bedeutet, die Organisation und die IT sollten gleich strukturiert sein, um eine optimale Kommunikation zu gewährleisten. Wie oft kommt es vor, dass ein Unternehmen eine Organisationseinheit hat, die in der IT vom ESB abgebildet werden kann?! Ein Aktentransportwägen-Team ausgestattet mit einem mobilen Arbeitsplatz, wobei die Akten unterwegs für die nächste Abteilung im Zielformat übersetzt werden (Transformation und Mapping).

> SOA heißt zentrale Planung und Steuerung

Sowohl SOA als auch BPM gehen von der zentralen Planung und Steuerung aus. Nun, was soll schon daran falsch sein, ein Unternehmen zentral zu planen und zu steuern? Schließlich haben alle Unternehmen genau hierfür das Management, das zentral plant und steuert!  

Ist es so? Steuern die Manager die Umsetzung direkt? Ohne die Zwischenebenen?  
Oder ist es nicht so, dass bei erfolgreichen Unternehmen das Management die Leitplanken mittels der Vision und der Mission setzt? Daraus folgen Unternehmensziele. Die Ziele werden gewöhnlich, und damit auch die Pläne, herunter auf die fachlichen Einheiten gebrochen. Die Teams der Fachbereiche erarbeiten für sich selbst daraus detaillierte Pläne und sind selbst für die Umsetzung verantwortlich. Es existiert kein bis zum letzten Detail ausgearbeiteter zentraler Masterplan.  

Erfolgreiche Unternehmen leben es vor. Agile Teams versuchen, eigene abgeleitete Ziele mittels eigener Planung und mit integrierten Optimierungsbestrebung (wie Sprint-Retrospektive beim Scrum) optimal zu erreichen. Das Management begnügt sich mit regelmäßigen Rückmeldungen der Ergebnisse aus den Teams heraus (Reporting) und prüft regelmäßig, ob sich das Unternehmen in der Gesamtsicht (Big Picture) auf dem richtigen Kurs befindet.  

Bei Enterprise SOA wird aber genau mit der zentralen Steuerung der Prozesse durch BPM dieser zentrale Masterplan aufgebaut, gesteuert und kontrolliert. Durch **SOA Governance** kontrolliert ein Gremium die IT-Änderungen und stellt sicher, dass diese zentral abgestimmt sind. Zentrales Domain Model, Implementierung der Integration und die Technologieauswahl sind stark reguliert.
Andersherum betrachtet könnte man sagen, dass SOA und BPM richtig am Platz sind in Unternehmen, bei denen jeder Schritt nach der zentralen Planung haargenau umgesetzt werden muss. Wo keine ungeprüften Optimierungsaktionen zugelassen sind. Zum Beispiel bei der Pharmaindustrie.
Die meisten anderen Unternehmen wollen agiler werden und von der Erfahrung eigener Mitarbeiter profitieren.

>Die Antwort auf die Veränderungsanforderung ist der Microservices-Ansatz

Für die IT heißt dies, mehr Agilität zuzulassen. Änderungen schneller zuzulassen. Die IT auf Änderungen ausrichten. Keine zentrale monolithische IT, sondern kleine, sauber nach Fachlichkeit getrennte Applikationen, die zu den Umsetzungsteams genau passen und auch in der heutigen Welt der Agilität im Stande sind, im Gleichschritt mitgehen zu können.
**Der Microservices-Ansatz ist die Antwort auf die NFR Anforderung: Änderungen schnell umsetzen.**

![Microservices][image_microservices]  
`Abbildung 2. Enterprise Architektur nach Microservices Ansatz`

Dieser Artikel möchte sich nicht damit befassen, wie diese agile Architektur erreicht werden kann. Dafür gibt es bereits einige Veröffentlichungen. Zum Beispiel [das Buch von Eberhard Wolff][ewolff_microservices], oder von [Matt McLarty][mattmclarty_microservices] aber auch [die Artikel über die Self-Contained Systems][scs] die eine konkrete genauere Umsetzung des Microservices-Ansatzes beschreiben. Das neue Organisationsstichwort hier ist **BizDevOps**.
In diesem Artikel geht es primär um BPM. Wo bleibt BPM in dieser neuen agilen Welt der Microservices?

> BPM soll sich auch an Conway orientieren

BPM besagt, dass die End-To-End Prozesse in einem Unternehmen analysiert, erfasst, gesteuert, überwacht und optimiert werden. Die Unternehmen, die dies IT gesteuert umsetzen, werden nach ISO-9000 oder nach CMMI auf dem höchstem Level zertifiziert. Wie die Umsetzung aussehen soll steht den Unternehmen frei, dennoch besagt die BPM Lehre, dass die Prozesssteuerung aus einem BPM-System erfolgen soll.

Diese Forderung des BPM nach einer zentralen Steuerung soll der Forderung nach einer zentralen automatisierten Prozessauswertung weichen. Wie gesagt, dem Management reicht es, in regelmäßigen Abständen die Ergebnisse zu berichten. BPM soll die Umsetzung der Prozessdigitalisierung frei stellen.

Genauso wie die Staaten erkannt haben, dass die zentrale Planung noble Ziele verfolgt, in der Umsetzung aber niemals gegen die freie Wirtschaft ankommen kann. So müssen auch die IT-Strukturen in SOA Konzernen freier werden.

**Für BPM bedeutet das, dass es keine zentrale Steuerungskomponente der End-To-End Prozesse geben darf. Auch keine detaillierte zentrale Planung.**

BPM kann unterstützen, wenn die Prozesstransparenz aufgrund der Komplexität und der Unternehmensgröße leidet. BPM soll die Prozesse sichtbar machen und die Optimierungspotentiale im Sinne der Unternehmensziele aufdecken.

## Reverse BPM (rBPM)
Das hier als **Reverse BPM (rBPM)** betitelte BPM versucht, die beschriebenen Eigenschaften des Microservices-Ansatzes einzuhalten. RBPM verfolgt weiterhin die gleichen Ziele wie BPM, indem die Unternehmensprozesse analysiert, erfasst, gesteuert, überwacht und optimiert werden. Der Unterschied liegt in der Prozesssteuerung. Wie der Name *Reverse BPM* besagt, wird die Idee des Reverse-Engineerings angewandt, indem die Prozessabläufe mittels *[Operational Intelligence][operational_intelligence]* rekonstruiert werden.

### Prozessanalyse, -erfassung und Überwachung
Mit Operational Intelligence (OI) wird die Prozesstransparenz erreicht, indem die Daten aus der Verarbeitung (Operations) gesammelt und zu der Informationen interpretiert (Intelligence) werden. Das Vorgehen ist vergleichbar mit Business Intelligence (BI), jedoch unterscheidet es sich in der Geschwindigkeit der Bereitstellung der Informationen. Im Gegensatz zu BI, wo Informationen im Form der Reports frühestens am Folgetag, gewöhnlich aber nach Monats-, Quartals- oder Jahresabschluss berichtet werden, ermöglicht die OI die Gewinnung der Transparenz über die Geschäftsprozesse in nahezu Echtzeit.

Die operativen IT Systeme sollen die fachlichen Events an OI melden. Und das nicht einmal, sondern ständig, für jede Prozessinstanz. Für welchem Prozess wird gerade was gemacht und für welche Prozess-Instanz in welcher Version? Ein Reverse-BPM-System (rBPMS) soll diese explizit gesammelten OI Prozessinformatinen ständig auswerten. Das System soll imstande sein, einen Prozessablauf vollständig nachzukonstruieren und diesen auch nach *Business Process Modelling Notation* (BPMN) darstellen zu können.

Unter der Vorgabe, dass alle fachlichen Prozessschritte an OI gemeldet werden sollen, wäre damit die Prozessanalyse und -Erfassung teilautomatisierbar. Die erfassten Abläufe würden in allen Fällen immer den IST-Zustand abbilden. Neue erfasste, noch unbekannte Abläufe könnten dem Prozessowner zur Review gemeldet werden. Er könnte diese quittieren oder durch einen *Change Request* (CR) korrigieren lassen.

### Prozesssteuerung und -ausführung
Bei rBPM wird die Ausführung der Services und der Human Tasks durch den jeweiligen Microservice, implementiert nach eigenen Teamvorgaben, umgesetzt. Falls der Microservice selbst eigenen internen Status über den langlaufenden Prozess verwalten muss, spricht hier nichts dagegen, eine eingebettete Business Process Engine wie zum Beispiel [camunda BPMN Engine][camundaBPM] einzusetzen.  

Der Prozessowner kann das neue SOLL Model im BPM System für den SOLL-IST-Vergleich aufnehmen. Die Entwicklung und Test können diesen Vergleich als Akzeptanzkriterium nutzen. Die Angleichung von IST und SOLL, soll auf Entwicklungs- und Testumgebung erfolgen. Produktiv sollten dann keine größeren Überraschungen erfolgen.
Der Unterschied liegt darin, dass beim rBPM das BPM System die Prozesse nachgelagert nach dem Ablauf ständig analysiert und falls möglich mit einem SOLL/PLAN Model vergleicht. BPM ist nicht führend bei der Prozesssteuerung, sondern dafür sind die jeweiligen beteiligten Fachapplikationen allein zuständig. Damit steuert der rBPM nur indirekt den Prozessablauf.

Für die IT Architektur würde das bedeuten, dass die Implementierung der einzelnen Prozessschritte/Tasks in den Microservices frei jedem Team überlassen werden kann, just nach der Empfehlung von [Martin Fowler][martinfowler]. Keine Vorgaben der Technologien. Freie Umsetzung der Optimierungen und freie Entwicklung.

### Prozessoptimierung
Beim Klassischen BPM erzeugt der Prozess Owner ein SOLL-Prozessmodell, das durch Aufnahme im BPMS zum IST wird. Der BPMS steuert die Ausführung der Prozessinstanzen nach dem IST-Modell.

Die BPM Prozessoptimierung beim rBPM geschieht, indem der Prozessowner als Teil von BPM auf die Echtzeit Prozessanalyse reagiert und beim Änderungsbedarf einen CR stellt. Der Prozess Owner stellt die CRs für die jeweiligen SOLL-Prozesssegmente der zugehörigen Microservices-Domänen. Die Microservice-Teams implementieren die CRs nach eigener Vorstellung.  

### rBPM Architektur
Die End-To-End Geschäftsprozesse durchlaufen operativ mehrere fachlichen Domänen im Unternehmen. Nach Conway sollten daher diese nicht in einem operativen System implementiert werden.

> BPMS nicht als operative sondern als unterstützende Querschnitt-Domäne implementieren.

Durch die Überlassung der Task-Ausführung der eigenen Domänen können diese die Entkapselung als das Hauptziel des Microservices-Ansatzes einhalten.

![Enterprise Microservices mit BPM][image_microservices&BPM]  
`Abbildung 3. BPM als Reverse BPM (rBPM) nach Microservices-Ansatz`

Die *Operational Intelligence* des rBPM muss alle notwendigen Daten für die vollständigen Rekonstruktion des Prozessablaufes erhalten. Um die Entkapselung der operativen Systeme zu gewähren, müsste dies asynchron erfolgen.

## Fazit
Es können weitere Vorteile des nach rBPM implementierten BPM-Systems, zusätzlich zu Architektur Kompatibilität zum Microservices-Ansatz, aufgelistet werden. Als erstes spricht die einfache Einführung in die existierende IT-Landschaft dafür. Dadurch, dass ein rBPMS die Prozessausführung nicht direkt steuert, müsste diese aus der bestehenden operativen Systemen nicht herausgelöst und nach BPMS migriert werden. Ein rBPMS müsste als IT-Anwendung der eigenen unterstützenden Querschnitt-Domäne abgekapselt von dem operativen Domänen agieren. Dadurch entstehen keine Performance-Einbußen da die operativen Systeme die Events asynchron verschicken können.

Wie der Microservices-Ansatz selbst, mangelt es rBPMS gegenüber den klassischen BPMS wie alle dezentrale Systeme gegenüber den zentralen, an der Eleganz und bei der Handhabung. So wäre keine unternehmensweite zentrale Taskliste für die Human-Tasks mehr vorhanden. Die Prozesstransparenz wäre nur dann vorhanden, wenn die Informationen hierfür korrekt eingesammelt wurden. Die Gefahr, dass wichtige fachliche Schritte von den operativen Systemen nicht gemeldet wurden, immer vorhanden sein.

Beim testen wäre die automatisierte Durchführung der Tests nicht ohne Erweiterungen möglich. Wie beim klassischen BPM wäre beim Reverse BPM die Auswertung der Testergebnissen der End-To-End Prozesse in einer Testumgebung innerhalb des rBPMS umsetzbar. Das Ausführen der Start-Events und der Human-Tasks für Tests müsste gesondert erfolgen.

Unter dem Strich könnte man mit rBPM ein weiterhin vollumfängliches Business Process Management mit allen Vorteilen die es mitbringt, auch in der neuen agile IT der Microservices, erhalten.

[computerwoche]:         	  https://www.computerwoche.de/a/soa-und-bpm-wachsen-zusammen,1219234
[image_soa]:             	  /images/posts/2018-01-07-BPM-und-Microservices/BPM_und_Microservices_AzmirAbdi_SOA.svg
[image_microservices]:    	/images/posts/2018-01-07-BPM-und-Microservices/BPM_und_Microservices_AzmirAbdi_Microservices.svg
[image_microservices&bpm]:	/images/posts/2018-01-07-BPM-und-Microservices/BPM_und_Microservices_AzmirAbdi_Microservices&BPM.svg
[martinfowler]:          	  https://martinfowler.com/
[mattmclarty]:           	  https://www.infoworld.com/article/3080611/application-development/learning-from-soa-5-lessons-for-the-microservices-era.html
[mattmclarty_microservices]:http://transform.ca.com/API-microservice-architecture-oreilly-book.html
[conway]:                	  https://de.wikipedia.org/wiki/Gesetz_von_Conway
[scs]:                   	  http://scs-architecture.org/
[ewolff_microservices]:		  https://www.dpunkt.de/buecher/12181/9783864903137-microservices.html
[operational_intelligence]:	https://en.wikipedia.org/wiki/Operational_intelligence
[camundaBPM]:				        https://camunda.com/products/bpmn-engine/

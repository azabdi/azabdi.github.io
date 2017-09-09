---
layout: post
title:  "BPM und Microservices"
date:   2017-09-09 18:57:07
categories: [BPM]
tags: [BPM, Microservices, Enterprise Architecture]
---
Steht klassisches Business Process Management (BPM) im Wiederspruch zu der IT-Architektur nach dem Microservices-Ansatz? Der korrekte Microservices-Ansatz erlaubt keine zentrale unternehmensweite Prozesssteuerungskomponente!  

Business Process Management (BPM) ist ein vollumfänglicher Ansatz der Unternehmensorganisation konzentriert auf die kontinuierliche Optimierung und damit auf die Gewinnmaximierung des Kerngeschäfts. Dabei wird das Kerngeschäft in die End-To-End Geschäftsprozess(e) gegliedert die komplette Eigenleistung von dem Kunden-Auftrag bis zu der abschließenden Kunden-Lieferung umfasst.  
Die IT gestützte Lösung des BPM’s sind die BPM-Systeme (BPMS) bei denen die End-To-End Geschäftsprozesse durch integrierte zentrale Business Process Engines (BPE) automatisiert gesteuert werden. BPM Ansatz spielt hervorragend mit der Serviceorientierten Architektur (SOA) als Enterprise-SOA zusammen wie im Artikel der [computerwoche] vor über 10 Jahren beschrieben wurde.  
Mittlerweile wissen wir das SOA in der ursprünglichen Form bereits veraltet ist. Das neue maßgeblich vom [Martin Fowler][martinfowler] entworfene Microservices-Ansatz ist die nächste Evolutionsstufe der Enterprise Architecture.  

Sind Microservices keine SOA? Die Unterschiede sind sogar signifikant!
SOA setzt auf Wiederverwendung. Wiederverwendung von Services. Zentrales Domain Model. Enterprise Service Bus (ESB) als zentrale intelligente Integration. Die gesamte Unternehmensarchitektur ist im Schichten Organisiert wie von Herrn Slama im [computerwoche] Artikel dargestellt:
![Enterprise SOA][soa]

BPMS als Zusatz übernimmt Teilweise die Serviceorchestrierung die gewöhnlich über ESB stattfindet.
Matt McLarty hat in seinem [Artikel][mattmclarty] die Abgrenzung der Microservices zu SOA in unterschiedlichen Perspektiven sehr detailliert dargestellt.
Einer der Widersprüche von SOA und BPM zu den Microservices-Ansatz liegt genau beim ESB. Microservices-Ansatz setzt auf leichtgewichtige Integration.
*`smart endpoints and dumb pipes` Prinzip wird als Folge der Anwendung vom [Coway’s Gesetz][conway] vorgeschrieben. 
Nach Conway werden die IT-Systeme unweigerlich nach den Kommunikationsstrukturen des Unternehmens organisiert. Wie oft kommt es vor das ein Unternehmen eine Organisationseinheit hat die in der IT vom ESB abgebildet werden kann. Ein Team mit Aktentransportwägen ausgestattet mit einem mobilen Arbeitsplätzen (Laptop + Drucker) wobei die Akten im Zielformat unterwegs für die nächste Abteilung übersetzt werden.  

… tbd …

[computerwoche]:     https://www.computerwoche.de/a/soa-und-bpm-wachsen-zusammen,1219234 
[soa]:               https://images.computerwoche.de/images/computerwoche/bdb/918472/890x.jpg
[martinfowler]:      https://martinfowler.com/
[mattmclarty]:       https://www.infoworld.com/article/3080611/application-development/learning-from-soa-5-lessons-for-the-microservices-era.html
[conway]:            https://de.wikipedia.org/wiki/Gesetz_von_Conway
[scs]:               http://scs-architecture.org/
# 4 Wie weiter?

Diese Broschüre kann nur eine kurze Einleitung in Microservices geben. Daher ist eine wichtige Frage, wie man nach dem Studium der Broschüre weitermachen kann.

## 4.1 Microservices: Nur ein Hype?

Microservices sind mehr als ein Hype. Amazon setzt die Trennung in
Teams mit ihren jeweils eigenen Technologien schon seit 2006
ein. Diese Architektur und diesen Ansatz kennen wir heute als
Microservices. Pioniere wie Netflix versprechen sich von diesem
Architektur-Ansatz so große Vorteile, dass sie selber erheblich in den
notwendigen Infrastrukturen investiert haben. Heutzutage stehen diese
Technologien allen offen, so dass der Einstieg und die Nutzung
einfacher und auch weniger kostenintensiv sind.

Auch der Trend zu Agilität, Continuous Delivery und Cloud findet in
Microservices eine Entsprechung bei der Architektur. Auch darüber
hinaus gibt es viele gute Gründe für Microservices – seien es die
individuelle Skalierbarkeit oder die Robustheit. Microservices sind
also nicht nur eine gute Ergänzung zu einigen anderen Trends, sondern
sie sind vor allem eine Lösung für verschiedene Probleme. Der Trend
basiert also auf einer ganzen Reihe von Gründen. Daher ist es
unwahrscheinlich, dass nur ein kurzlebiger Hype ist.

## 4.2 Beispiele

Die Broschüre betrachtet das Thema Microservices nur theoretisch und
zeigt auch keine Technologien, um Microservices umzusetzen. Unter
<http://ewolff.com/microservices-demos.html> finden sich einige
Beispiele, die verschiedene Optionen für die Implementierung von
Microservices zeigen:

#### Synchrone Kommunikation

Für synchrone Kommunikation gibt es folgende Beispiele:

* Die [Consul-Demo](https://github.com/ewolff/microservice-consul) ist
in Java mit Spring Cloud / Boot geschrieben. Die Demo nutzt Consul für
Service Discovery,  Apache httpd für Routing, Hystrix für Resilienz
und Ribbon für Load Balancing Es gibt auch eine
[Prometheus-Installation](https://github.com/ewolff/microservice-consul#prometheus)
 für das Monitoring und einen
  [ELK-Stack](https://github.com/ewolff/microservice-consul#elastic-stack)
 für die Analyse der Log-Dateien.

* Die [Netflix-Demo](https://github.com/ewolff/microservice) ist
ebenfalls in Java mit Spring Cloud / Boot geschrieben. Die Demo
verwendet Netflix Eureka für Service Discovery, Netflix Zuul für
Routing, Hystrix für Resilience und Ribbon für Load Balancing.

* Kubernetes ist eine Umgebung für den Betrieb von Docker im
Cluster. Auch die
[Kubernetes-Demo](https://github.com/ewolff/microservice-kubernetes)
ist in Java mit Spring Cloud / Boot geschrieben. Sie verwendet
Kubernetes für   Service Discovery, Routing und Load Balancing. Die
Demo benutzt auch  Hystrix für Resilience Der Code hängt nicht von
Kubernetes ab.

* Cloud Foundry ist ein PaaS (Platform as a Service). Der PaaS kümmert
sich darum, eine Anwendung zu deployen und zu
betreiben. [Das Cloud-Foundry-Beispiel](https://github.com/ewolff/microservice-cloudfoundry) ist in Java
geschrieben mit Spring Cloud / Boot. Es verwendet Cloud Foundry für
Deployment, Service Discovery, Routing und Load Balancing. Die Demo
 nutzt ebenfalls Hystrix für Resilience. Der Code hängt nicht von
Cloud Foundry ab.

####Asynchrone Kommunikation

Asynchrone Kommunikation macht den Umgang mit unzuverlässigen Services
oder Netzwerken einfacher:

* [Kafka](https://github.com/ewolff/microservice-kafka) verwendet Kafka für
Kommunikation, eine Message-oriented Middleware, die Nachrichten
verschicken kann.

* [Atom](https://github.com/ewolff/microservice-atom) verwendet REST / HTTP
zur asynchronen Kommunikation mit dem Atom-Format.

#### UI Integration

Die Integration auf Ebene der UI führt zu einer sehr losen Kopplung:

* [ESI](https://github.com/ewolff/SCS-ESI) zeigt, wie Edge Side
Includes (ESI) verwendet werden können, um die Benutzeroberfläche von
Microservices zu integrieren. Ein Microservice ist in Java mit Spring
Boot geschrieben, der andere mit Go. Der Go-Microservice wird
mit Multi Stage Docker Containern gebaut.

* [JQuery](https://github.com/ewolff/SCS-jQuery) zeigt, wie jQuery kann
zur Integration der Benutzeroberfläche von Mikroservices genutzt
werden.

Jedes dieser Beispiele hat eine umfangreiche Dokumentation, die auch
erläutert, wie man die Beispiele laufen lassen kann.

## 4.3 Weitere Literatur

Die Broschüre kann nur einen groben Eindruck von Microservices
geben. Sie kann nur eine Einleitung in Microservices
geben. Weiterführende Literatur [^MS1] kann nützlich sein. Dieses Buch
gibt es auch in [Englisch](http://microservices-book.com/).

[^MS1]: Eberhard Wolff: Microservices - Grundlagen flexibler Softwarearchitekturen, dpunkt Verlag, 2015, ISBN 978-3864903137

Für die technische Implementierung von Microservices bietet die
kostenlosen
[Microservices Rezepte](http://microservices-praxisbuch.de/rezepte.html)
einen guten Startpunkt. Sie zeigen verschiedene
Implementierungsalternativen auf Basis der bereits erwähnten
Demos. Auch diese Broschüre gibt es auf
[Englisch](http://practical-microservices.com/recipes.html).

Eine umfangreiche Darstellung technischer Implementierungsmöglichen
für Microservices bietet das
[Microservices-Praxisbuch](http://microservices-praxisbuch.de/), das
es ebenfalls auf [Englisch](http://practical-microservices.com/) gibt.

## 4.4	Loslegen

Das Risiko bei Microservices ist jedoch gering: Man muss lediglich
einen Microservice entwickeln und in Produktion bringen. Der Service
kann auch einen vorhandenen Deployment-Monolithen ergänzen. Und wenn
der Ansatz nicht funktioniert, kann man den Microservice auch recht
einfach wieder entfernen.



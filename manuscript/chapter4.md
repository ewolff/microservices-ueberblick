#4 Wie weiter?

Diese Broschüre kann nur eine kurze Einleitung in Microservices geben. Daher ist eine wichtige Frage, wie man nach dem Studium der Broschüre weitermachen kann.

##4.1 Microservices: Nur ein Hype?

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

##4.2	Ein Beispiel

Die Broschüre betrachtet das Thema Microservices nur theoretisch und
zeigt auch keine Technologien, um Microservices umzusetzen. Unter
<https://github.com/ewolff/microservice> findet sich ein Beispiel, das
Java, Spring Boot, Spring Cloud und den Netflix-Stack nutzt, um auf
einer Docker-Umgebung eine Microservices-Architektur laufen zu
lassen. Um eine Idee von den Technologien für Microservices zu
bekommen, lohnt es sich, dieses Beispiel anzuschauen.

##4.3	Loslegen

Die Broschüre kann nur einen groben Eindruck von Microservices
geben. Sie kann nur eine Einleitung in Microservices
geben. Weiterführende Literatur [^MS1] kann nützlich sein.

[^MS1]: Eberhard Wolff: Microservices - Grundlagen flexibler Softwarearchitekturen, dpunkt Verlag, 2015, ISBN 978-3864903137

Das Risiko bei Microservices ist jedoch gering: Man muss lediglich
einen Microservice entwickeln und in Produktion bringen. Der Service
kann auch einen vorhandenen Deployment-Monolithen ergänzen. Und wenn
der Ansatz nicht funktioniert, kann man den Microservice auch recht
einfach wieder entfernen.



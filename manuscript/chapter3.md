# 3 Warum Microservices? {#chapter3}

Es gibt mehr als einen Grund, Microservices einzusetzen. Je nach
Einsatzkontext können die Architekturentwürfe völlig unterschiedlich
aussehen. Es ist also nicht nur wichtig, die Vorteile zu kennen,
sondern sie auch für das konkrete Ziel abzuwägen und eine passende
Architektur umzusetzen.

## 3.1 Agilität skalieren {#section3-1}

Wie schon in Abschnitt 2.3 erwähnt, können Microservices Auswirkungen
auf die Organisation haben. Idealerweise sollte jeder Microservice von
einem Team weiterentwickelt werden oder es sollte zumindest genau ein
Team zuständig sein.

Das eröffnet Möglichkeiten für die Skalierung agiler Projekte:
Normalerweise müssten alle Teams sich abstimmen und gemeinsam an den
Features arbeiten. Wenn jedes Team einen eigenen Strom von
Anforderungen hat und sie durch Änderungen am eigenen Microservice
umsetzten kann, können die Teams weitgehend unabhängig voneinander an
Features arbeiten. Damit können auch größere Projekte agil angegangen
werden. Im Prinzip wird das System nun in mehrere kleine Projekte
aufgeteilt, die jeweils unabhängig arbeiten können. Neben der
fachlichen Aufteilung hilft es auch, dass Microservices Features ohne
eine Beeinflussung anderer Microservices in Produktion bringen
können. So ist eine weitgehend unabhängige Weiterentwicklung möglich.

Neben der fachlichen Unabhängigkeit bieten Microservices auch eine
technische Unabhängigkeit: Technologie-Entscheidungen können auf einen
Microservice begrenzt werden. So wird die Unabhängigkeit der Teams
erweitert: Sie können nicht nur weitgehend unabhängig Features
umsetzten, sondern auch jeweils eigene technische Entscheidungen
treffen.

So ermöglichen Microservices die unabhängige Entwicklung der einzelnen
Microservices und damit ein einfaches Skalieren agiler Prozesse auf
größere Projekt-Organisationen.

## 3.2 Legacy-Anwendungen migrieren {#section3-2}

Die Arbeit mit Legacy-Code ist oft schwierig: Das ist System ist
schlecht strukturiert, so dass es schwierig ist, sich einen Überblick
zu verschaffen. Ebenso ist die Qualität des Codes niedrig und
schließlich fehlen Tests. Oft ist dann noch die technologische Basis
veraltet, so dass moderne Ansätze nicht genutzt werden können.

Einige dieser Probleme sind lösbar, wenn man den Ansatz für die
Modifikation des Systems etwas verändert: Statt den Code des
Legacy-Systems zu modifizieren, wird das System an seinen externen
Schnittstellen durch Microservices ergänzt oder teilweise
abgelöst. Der Vorteil: Statt den Legacy-Code zu editieren, wird dieser
Code praktisch gar nicht modifiziert, sondern nur durch externe
Systeme ergänzt.

Das Fernziel ist die vollständige Ablösung des Legacy-Systems durch eine Menge von Microservices. Aber man kann das Legacy-System durch Microservices ergänzen, ohne dabei zu viel Zeit in Vorbereitungen zu stecken und den Weg einfach ausprobieren. Wenn die Microservices keine sinnvolle Lösung sind, können sie auch aus dem System recht einfach wieder entfernt werden.
Die einfache Integration von Microservices ist ein Grund, warum
Microservices so interessant sind. Die Ablösung eines Legacy-Systems
durch eine Menge von Microservices ist für viele ein guter Weg, um
Vorteile wie Continuous Delivery möglichst schnell in einem System zu
realisieren.

## 3.3 Nachhaltige Entwicklung {#section3-3}

Durch Microservices wird ein System in mehrere, getrennt deploybare
Dienste aufgeteilt. Die Aufteilung des Systems in Microservices ist
eine wichtige Architektur-Entscheidung. Sie legt die Zuständigkeit der
Komponenten fest.

In einem Deployment-Monolithen gibt es eine solche Architektur
auch. Aber in einem Deployment-Monolithen geht sie oft nach einiger
Zeit verloren. Es ist nämlich sehr einfach, neue Abhängigkeiten in
einen Deployment-Monolithen einzubauen: Es muss nur eine Klasse neu
referenziert werden. Die Architektur eines E-Commerce-Systems
definiert beispielsweise, dass der Bestellprozess die
Rechnungserstellung aufrufen soll. Die Rechnungserstellung darf aber
den Bestellprozess nicht aufrufen. Abhängigkeiten in nur eine Richtung
haben den Vorteil, dass Module änderbar bleiben. Im Beispiel würde ist
eine Änderung des Bestellprozesses möglich, ohne dass der
Rechnungsprozess geändert werden müsste. Eine Änderung des
Rechnungsprozesses hingegen kann den Bestellprozess beeinflussen, da
der Bestellprozess den Rechnungsprozess nutzt.

Bei der Implementierung eines Features im Rechnungsprozess hat ein Entwickler dann doch Funktionalitäten aus dem Bestellprozess genutzt. Das passiert recht schnell. Die Erfahrung ist, dass auf diese erste Abhängigkeit bald weitere folgen und irgendwann können die beiden Komponenten nicht mehr unabhängig voneinander weiterentwickelt werden, weil sie sich wechselseitig benutzen.
Bei Microservices ist es nicht so ohne weiteres möglich, ein anderen
Microservice zu nutzen. Die Microservices haben eine Schnittstelle, so
dass die Nutzung nur möglich ist, wenn man diese Schnittstelle
verwendet. Dazu muss die Schnittstelle mit Technologien wie REST oder
Messaging angesprochen werden. Das passiert nicht einfach aus
Versehen.

Wenn der zu verwendende Microservice von einem anderen Team
weiterentwickelt wird, kann es sogar notwendig sein, mit diesem Team
zu sprechen. Letztendlich ist also die Aufteilung der Architektur in
Microservices relativ stabil und im Gegensatz zu Deployment Monolithen
kann es nicht so ohne weiteres zu einem Verlust der Architektur
kommen. Ähnliche Ergebnisse lassen sich natürlich auch erzielen, wenn
andere Maßnahmen ergriffen werden, um die Integrität der Architektur
zu erzwingen. Beispielsweise gibt es Architektur-Werkzeuge, die
Entwickler auf die Verletzung von Architektur-Regeln hinweisen. Bei
Microservices sind diese Maßnahmen aber schon in das System
integriert.

#### Ersetzbarkeit

Eine weitere wichtige Eigenschaft von Microservices ist die
Ersetzbarkeit: Ein Microservice kann ohne großen Aufwand durch eine
Neuimplementierung ersetzt werden. Damit ist ein weiteres Problem der
Legacy-Systeme lösbar: Wenn ein Legacy-System nicht mehr gewartet
werden kann, kann es oft auch nicht neu geschrieben werden, weil der
Aufwand dafür zu hoch wäre. Microservices zu ersetzten ist hingegen
nicht sonderlich schwierig.

#### Fazit

Innerhalb eines Microservice sollte es auch langfristig einfach sein,
neue Features zu implementieren, da der Microservice klein ist. Wenn
er doch nicht mehr wartbar ist, kann er ersetzt werden. Die
Architektur im Zusammenspiel der Microservices sollte auch langfristig
erhalten bleiben. Damit kann die Wartbarkeit des Systems auch
langfristig gewährleistet werden. Microservice-Systeme versprechen
also eine langfristige gute Wartbarkeit und Änderbarkeit der
Software-Systeme.

## 3.4 Robustheit {#section3-4}

In einem Microservice-System ist die Robustheit für bestimmte Probleme
sehr hoch: Wenn in einem Deployment-Monolithen eine Funktionalität
sehr viel CPU oder Speicher verbraucht, werden andere Module ebenfalls
beeinflusst. Wenn im Extremfall ein Modul das System zum Absturz
bringt, sind alle anderen Module ebenfalls nicht mehr verfügbar.

Ein Microservice ist ein eigener Prozess oder sogar eine eigene
virtuelle Maschine. Ein Problem in einem Microservice beeinflusst
einen anderen Microservice also nicht, weil das Betriebssystem oder
die Virtualisierung die Microservices gegeneinander isoliert.

Dennoch sind Microservices ein verteiltes System. Sie laufen also auf mehreren Servern und nutzen das Netzwerk. Server und Netzwerk können ausfallen. Also sollte ein Microservices-System als ganzes nicht sehr robust sein, weil es diesen Gefahren verstärkt ausgesetzt ist.
Microservices müssen daher gegen den Ausfall anderer Microservices
abgesichert sein. Man spricht von „Resilience“. Die Implementierung
von Resilience kann sehr unterschiedlich sein: Wenn der Bestellprozess
nicht abgeschlossen werden kann, ist vielleicht ein erneuter, späterer
Versuch eine Option. Wenn eine Kreditkarte nicht verifiziert werden
kann, wird vielleicht bis zu einer gewissen Obergrenze die Bestellung
dennoch durchgeführt. Welche Grenze das genau ist, müssen dann
Fachexperten entscheiden.

Durch Resilience kann also ein Microservice-System sehr robust
werden. Die Basis legt dazu die strikte Trennung in Prozesse oder
virtuelle Maschinen.

## 3.5 Continuous Delivery {#section3-5}

Continuous Delivery [^CD] ist ein Ansatz, bei dem Software regelmäßig in
Produktion gebracht wird. Basis ist dabei vor allem ein weitgehend
automatisierter Prozess, wie [Abb. 4](#Abb4) ihn zeigt:

[^CD]: Eberhard Wolff: Continuous Delivery: Der pragmatische Einstieg, dpunkt Verlag, 2016, ISBN 978-3864903717

* In der Commit-Phase werden Unit Tests und statische Code-Analyse
ausgeführt.

* Die automatisierten Akzeptanztests garantieren, dass die Software
Features korrekt umsetzt.

* Kapazitätstest hingegen überprüfen, ob die Performance stimmt und
die erwartete Last abgedeckt werden kann.

* Manuelle Tests können neue Features aber auch Fehlerschwerpunkt
untersuchen.

* Schließlich kommt die Software in Produktion.

{id="Abb4"}
![Abb. 4: Continuous Delivery Pipeline](images/04-ContinuousDeliveryUebersicht.png)

Continuous Delivery ist mit Deployment-Monolithen nur schwer
umsetzbar:

* Die Automatisierung der Tests und der Deployments ist aufwändig,
  weil Deployment-Monolithen schwierig in Produktion zu bringen
  sind. Eine Rolle spielt beispielsweise die Datenbank, die recht groß
  sein kann und viele Daten enthalten kann. Ebenso müssen viele
  Drittsysteme integriert oder zu simuliert werden.
  
* Die Tests sind aufwändig. Gerade bei einem Deployment-Monolithen
  können Änderungen leicht Nebenwirkungen haben, die nicht
  beabsichtigt sind. Daher muss für jede Änderung ein umfangreicher
  Regressionstest durchgeführt werden. Das ist aber aufwändig und
  macht die Continuous-Delivery-Pipeline langsam.
  
* Schließlich ist es aufwändig, eine Release abzusichern. So wäre es
  denkbar eine zweite Umgebung aufzubauen, in der Umgebung die neue
  Version zu deployen und erst auf die neue Version umzuschalten, wenn
  sie beispielsweise noch einmal durchgetestet worden ist. Ebenso ist
  dann ein Rückfall auf die alte Version machbar. Bei einem
  Deployment-Monolithen sind solche Ansätze nur schwer umsetzbar, weil
  die Umgebung zu groß und zu komplex ist.
  
Microservices sind unabhängige Deployment-Einheiten. Daher können sie
auch unabhängige Continuous-Delivery-Pipelines haben. Diese Pipelines
sind relativ einfach aufzubauen und die Microservices werden auch
relativ schnell durch die Continuous-Delivery-Pipeline in Produktion
gebracht. Auch sind die Deployments von Microservices einfacher
abzusichern. Alle oben genannten Probleme der Deployment Monolithen
sind durch die geringere Größe von Microservices lösbar und Continuous
Delivery wird dadurch wesentlich vereinfacht.

Natürlich sind dazu einige Vorkehrungen notwendig, um das unabhängige
Deployment tatsächlich zu ermöglichen. Dennoch sind gerade die
Vorteile bei Continuous Delivery ein wichtiger Grund, warum sich viele
für Microservices interessieren.

## 3.6 Unabhängige Skalierbarkeit

Jeder Microservice läuft als ein eigener Prozess, gegebenenfalls sogar
in einer eigenen virtuellen Maschine. Wenn also eine bestimmte
Funktionalität besonders stark genutzt wird, kann nur der dafür
notwendige Microservice skaliert werden, während die anderen
Microservices weiterhin mit derselben Kapazität laufen.

Das hört sich zunächst nach keinem besonders großen Vorteil an, aber
in der Praxis ergeben sich dadurch erhebliche Vorteile, weil die
Skalierung einfacher ist. Im Allgemeinen sind die
Performance-Anforderungen nur für bestimmte Fälle wirklich
anspruchsvoll. Die unabhängige Skalierbarkeit erlaubt es, sich auf
diese Fälle zu konzentrieren und zwar mit weniger Aufwand, als dies
bei einem Deployment-Monolithen der Fall wäre. Also kann dieser Grund
schon wesentlich für die Einführung von Microservices sein.

## 3.7 Technologie-Wahlfreiheit

Im Prinzip kann jeder Microservice in einer anderen Technologie
umgesetzt sein. Das macht natürlich das System insgesamt komplexer,
wobei dem beispielsweise durch Standards für den Betrieb, das
Monitoring, die Log-Formate oder das Deployment begegnet werden
kann. Dann ist zumindest der Betrieb weitgehend einheitlich.

Dennoch kann beispielsweise für die Produktsuche nun eine eigene
Such-Technologie genutzt werden, ohne dass dazu eine umfangreiche
Koordination mit allen anderen Microservices und Teams notwendig
ist. Wenn ein Team ein Bugfix in einer Bibliothek benötigt und daher
eine neue Version nutzen will, ist die Änderung ebenfalls auf das eine
Team beschränkt und kann daher auch von diesem einen Team durchgeführt
werden, das dann auch das Risiko trägt. Bei einem
Deployment-Monolithen wäre eine umfangreiche Abstimmung notwendig und
auch entsprechend mehr Tests.

Schließlich können neue Technologien ohne einen großen Migrationsaufwand ausprobiert werden. Das Risiko und der Aufwand sind begrenzt: Es kann zunächst ein einziger Microservice migriert werden. Wenn das nicht funktioniert, fällt nur dieser aus und bei einem großen Problem muss nur dieser eine Microservice neu implementiert werden.
Ein Projekt, um den Deployment-Monolithen auf eine neue Technologie zu
heben, ist bei Microservices nicht notwendig und die Migration ist
viel einfacher. Das hat auch andere positive Konsequenzen: So können
Mitarbeiter eher neue Technologien ausprobieren, was meistens die
Motivation hebt.

## 3.8 Fazit

Microservices haben sehr viele Vorteile. Welche Vorteile tatsächlich
die wichtigsten sind, hängt vom konkreten Kontext ab. Bei vielen
Projekten steht die Ablösung eines Deployment-Monolithen im
Vordergrund. Dann ist der einfache Umgang mit Legacy-Systemen ein
wichtiger Vorteil bei der Migration. Grund für die Migration ist in
solchen Fällen oft die Skalierung agiler Prozesse und die einfachere
Umsetzung von Continuous Delivery.

Aber es gibt auch ganz andere Szenarien, in denen beispielsweise eine
Anwendung im Betrieb stabiler werden soll. Dann ist die Robustheit ein
wichtiger Treiber und die unabhängige Skalierung kann ein weiterer
wichtiger Vorteil sein.

Also hängen die wesentlichen Vorteile vom jeweiligen Kontext ab. Von
den erwarteten Vorteilen hängt auch ab, wie Microservices bei dem
System genau genutzt werden sollte.

# AI-Code-Gen-Articles




Agentic Engineering in der Praxis



Was ist Agantic engineering.
- "agentic" because the new default is that you are not writing the code directly 99% of the time, you are orchestrating agents who do and acting as oversight.
- "engineering" to emphasize that there is an art & science and expertise to it. It's something you can learn and become better at, with its own depth of a different kind.
Twitter Post of Andrey Kapathy

 Im Gegensatz zum Vibe Coding stellt diese Variante die professionelle Nutzung von Agenten da Software zum bauen, die nach Software engineering Maßstäben entwickelt wird.



Zur meiner Person
 Ich bin freiberuflicher Softwareentwickler und Architekt seit über 20 Jahren und arbeite überwiegend für große Konzerne in der Softwareentwicklung. Ich arbeite seit über drei Jahren mit KI im professionellen Kontext und seit über zwei Jahren sehr intensiv mit Agenten. Ich setze Agenten zur Code-Generierung und für viele andere Prozesse ein – unter anderem betreibe ich einen persönlichen Assistenten, über den ich wiederum viele Projekte steuere und auch private Aufgaben löse.





Vorbedingungen
Ich werde in diesem Dokument überwiegend von Agenten sprechen, damit meine ich dann immer die Kombination eines LLM mit einem coding Agenten wie z.B Claude Code, Kiro, Cursor, Windsurf …



Strategische Überlegungen
Verantwortung im Umgang mit KI-generiertem Code
Entwickler müssen sich mit dem, was sie an Code generieren lassen, aktiv auseinandersetzen. Wichtig ist, dass Entwickler verstehen, was das LLM an Code erzeugt, und dass sie sich darauf committen können. Diese Interaktion mit dem LLM ist eine gute Chance, das eigene Wissen aufzubauen, zu erweitern, kritisch zu hinterfragen und in den Diskurs mitzugehen. Auf keinen Fall darf man an eine Aufgabe mit der Haltung herangehen, das LLM löse das Problem, und man selbst könne sich davon distanzieren. Das Schlimmste, was passieren kann, ist wenn ein Nutzer sagt: „Das hat das LLM so erzeugt."
Warum Agenten Menschen (noch) nicht in allen Bereichen ersetzen können
Dies ist dieselbe Frage wie jene, warum LLM-Modelle bei der Code-Generierung noch nicht immer sofort und hundertprozentig die richtige Lösung liefern.
Die Antwort lautet: Kontext. Theoretisch besitzt das LLM das gesamte Wissen der Menschheit und kennt jeden Aspekt eines Themas – aber welches Wissen für eine konkrete Aufgabe relevant ist, ist dem LLM nicht bekannt. Daher ist es entscheidend, einen möglichst präzisen und vollständigen Kontext bereitzustellen.



Arbeite immer kleine Task (context window)
Kleine Änderungen , reviewbar
Wie bearbeitet große Task?
Plan ertsellen und abarbeiten bedeutet in kleine Task runter brechen 





#Die Bedeutung von Kontext beim Arbeiten mit Agenten
Beim Arbeiten mit Agenten sollte man so viel Kontext wie möglich bereitstellen: Fachlichkeit erklären, User Stories teilen, Coding Guidelines liefern sowie Architekturvorgaben definieren.
In der Regel starte ich so, dass der Agent das Projekt zunächst selbst für sich erarbeitet. Ob das Wissen korrekt konsumiert wurde, überprüfe ich anschließend durch gezielte Testfragen an den Agenten.
Das setzt voraus, dass der Agent die Möglichkeit hat, Wissen zu speichern. Da Wissen nicht im Agenten selbst abgelegt werden kann, muss dies über Dateien geschehen – bevorzugt natürlich über ein RAG-System. Die Konversationen werden dann im Verlauf ebenfalls im RAG gespeichert, ebenso wie alle Informationen, die ich dem Agenten für die Aufgabenlösung bereitstelle.
Ich stelle fest: Je mehr Informationen dem Agenten zur Verfügung stehen, desto unpräziser kann ich ihm Aufgaben übergeben – und er versteht dennoch, was gemeint ist. Wenn ich in einem Projekt merke, dass der Agent tief in der Materie ist, bin ich immer wieder überrascht, wie gut er mich versteht. Ich provoziere das bewusst, indem ich ihm möglichst unpräzise Aufgaben gebe – und bin oft erstaunt, dass er genau weiß, was ich meine. Diese Qualität schreibe ich dem Kontext zu, den ich ihm zur Verfügung stelle.
 bei einem konsistenten Einsatz von Agenten sollten auch Refactorings durch den Agenten gemacht werden denn diese Information ist wichtig für den Kontext. Man müsste die Information an den Agenten über eine erneute Analyse eh hinzufügen in dem Fall dass man eine Factoring über die IDE macht. Erfahrungsgemäß sind Agenten extrem gut in solchen Aufgaben so dass es hier eigentlich keinen Zweifel daran geben sollte ob diese Aufgabe nicht lieber mit der IDE gelöst werden sollte.

#Große Aufgaben mit Sub Agenten lösen





#Steps im Entwicklungsprozess dokumentieren
konledge wikie Andre Kapathy




Warum der Kontext die Grenzen von Agenten definiert
Um die obige Frage noch einmal aufzugreifen: Der Grund, warum Agenten Schwierigkeiten haben werden, Menschen in bestimmten Bereichen zu ersetzen, liegt genau darin, dass dieser Kontext fehlt. Das LLM hat zwar alle Informationen, aber welche davon relevant sind, ist dem Agenten nicht bekannt.
Was wäre hier notwendig? Im Grunde müssten alle Kollegen ihren Arbeitskontext – also ihre Konversationen mit anderen Kollegen und die Ergebnisse, die sie liefern – dem Agenten zur Verfügung stellen. Solange das nicht passiert, werden solche Agenten den Menschen in vielen Bereichen nicht ersetzen können.
Ein weiterer Aspekt ist die Fähigkeit zur eigenständigen Initiative: Zu überlegen, welche Aufgaben man angeht, ohne dass sie sich direkt aus einer vorherigen Aufgabe ableiten lassen, ist etwas, das einem Agenten schwerfällt.


Agenten als Werkzeug – nicht als Ersatz
Zu viel Autonomie verhindert Kontrolle. Derzeit sind Agenten Werkzeuge, die Menschen bei ihrer Arbeit unterstützen. Es wird auch nicht so sein, dass Agenten Menschen grundsätzlich ersetzen – wahrscheinlicher ist, dass die Produktivität einzelner Menschen so stark gesteigert wird, dass Unternehmen Kollegen entlassen. Das ist die eigentlich relevante Frage: Wie setzen wir Agenten ein?
Machen Agenten uns produktiver, bringen sie mehr Qualität und mehr Freude bei der Arbeit? Oder führen sie dazu, dass einzelne Menschen so produktiv werden, dass sie ihren Kollegen quasi die Arbeit wegnehmen – also eine negative Skalierung stattfindet?
Aus meiner Sicht sollten Agenten eingesetzt werden, um die Qualität zu verbessern und Menschen bei der Arbeit zu unterstützen – nicht um sie zu ersetzen. Wer die entgegengesetzte Denkweise einschlägt, befindet sich bereits jetzt in einer Sackgasse.

Agenten um Agenten zu entwickeln



Agenten anlernen
Viele denken mit so Agenten kann man keine bestehenden   Softwareprojekte weiterentwickeln  insbesondere bei Legacy Systemen die zum Teil stark von heutigen architekturkonventionen weichen.

 dem muss ich vehement widersprechen. Wenn wir hier in ein Projekt eintreten das für den Agenten neu ist dann muss er wie jeder andere Kollege der an ein Projekt kommt angelernt werden. Dazu gebe ich dem Agenten den Auftrag zu analysieren und Dokumentation bereitzustellen. Anhand der Dokumentation kann ich erkennen ob er das Thema richtig  er fast hat. Ich kann jetzt Fragen stellen und verifizieren ob die Analyse erfolgreich war.

Beispiel





Konversationen

Konversationen speichern
claude wiki

Produktivität & Qualität

Fokus auf architektur
Visualisierungen
validierung der architektur
 	generieren von übersichten Clean Code diagram
Testprotokolle und visualisierungen
 






Vibe coding
kontrolle verlieren - fähigkeit problem zu lösen ode fehler zu fixen





Konsitente nutztung
agent ist in alle entwicklungsschritte immer eingebunden kenn daher den aktuelle stand


Software engineering  & 
Context engineering


Plan mode

Beginnen mit der requirement also fachlichen Anforderungen wie z.b user Story daraus wird erstmal eine Spezifikation entwickelt das heißt es wird geschaut was technisch bereits vorhanden ist und was noch implementiert werden muss um das Ziel zu erreichen bei dem technischen Konzept was erstellt wird sollte ein Dokument rauskommen dass man reviewen kann und gegebenenfalls interaktiv mit dem Agenten verfeinern kann das kann man auch mit grill-me skill machen

Das Dokument für den Agent im Project gespeichert und dient dem Agenten für zukunftige implementieren als Orientierung bzw permanente technische Anforderung 

entwickeln kleiner module die klar definiert und getestet und gereviewed werden können







TOOLS & MCP





Meine Projekte



Context engineering





Senior Code lesen statt schreiben 
https://www.heise.de/blog/Code-lesen-statt-Code-schreiben-Die-unterschaetzte-Senior-Disziplin-11288309.html






Erfahrung welche Modelle und Agenten kombination 


Grundlagen & Einstieg
Was ist AI Code Generation – ein ehrlicher Überblick
Die wichtigsten Modelle und Tools im Vergleich (Copilot, Cursor, Claude, etc.)
Prompt Engineering für Entwickler – die Kunst der präzisen Aufgabenstellung
Praktische Anwendung
Workflows und konkrete Setups für den täglichen Einsatz
Code Reviews mit KI – wie man generierte Code-Qualität bewertet
Debugging mit KI-Unterstützung
Testing und Testgenerierung
Refactoring und Legacy-Code modernisieren
Agenten & Automatisierung
Architektur von Coding-Agenten
RAG-Systeme für Entwicklungsprojekte aufbauen
Multi-Agenten-Systeme – wann sie sinnvoll sind
Kontext-Management in komplexen Projekten
Qualität & Verantwortung
Sicherheitsrisiken bei KI-generiertem Code
Intellectual Property und Lizenzfragen
Wann man dem Agenten vertrauen kann – und wann nicht
Unternehmenskontext
KI-Code-Generierung in großen Konzernen einführen
Change Management – Entwickler mitnehmen
Kosten-Nutzen-Analyse
Zukunft
Wohin entwickelt sich die Technologie?
Die neue Rolle des Softwareentwicklers



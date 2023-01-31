# Einsatzbereich Git - Weshalb Git ein *must use* ist.
![XKCD 1597](https://imgs.xkcd.com/comics/git.png)

Wer gemeinsam eine Software entwickelt, mit [*Infrastructure as Code*](https://en.wikipedia.org/wiki/Infrastructure_as_code) arbeitet, eine wissenschaftliche Arbeit mit [LaTeX](https://en.wikipedia.org/wiki/LaTeX) schreibt oder Modulunterlagen für den Unterricht entwickelt, braucht Tools für Versionsverwaltung, Sharing, Backup, Organisation usw. [*Git*](https://en.wikipedia.org/wiki/Git) (zusammen mit einem Git-Repository Service Provider der Wahl) gilt aktuell als Tool der Wahl. Für Git-Neulinge kann das Erlernen dieses Tools eine Herausforderung sein.

In diesem Abschnitt wird mithilfe einer kleinen Geschichte von Luca und Charlie der Sinn und Zweck von Git dem Leser nähergebracht. Mithilfe der Geschichte und den Fragen lernen Sie, weshalb Git ein unerlässliches Tool ist und es in das Repertoire jeden Informatikers gehört.


## Vorbereitungen
Kopieren Sie dazu diese Markdown Datei in ihr persönliches Repository. Ihre Antworten und Erkenntnisse können Sie gleich an den entsprechenden Stellen einfügen.

 - Kopieren Sie diese Markdown-Datei in ihr persönliches Repository.
 - Öffnen Sie die Datei mit einem geeigneten Editor (z.B. Visual Studio Code)
 - Tipp: Öffnen Sie gleich ihr gesamtes Repository mit Visual Studio Code.

---

## Kapitel 1 - Die gemeinsame Quiz Applikation
![Luca und Charlie Teil 1](/05_Einfuehrung-Versionverwaltung/images/LucaCharlieTeil1.PNG)

Luca und Charlie wollen gemeinsam eine Quiz Applikation entwickeln. Charlie hat bereits begonnen und seinen Quellcode als ZIP Datei an Luca geschickt. Charlie programmiert am Quellcode weiter. Inzwischen programmiert auch Luca weiter. Als sich die beiden bei einem Meeting treffen, zeigen sie sich gegenseitig ihre Weiterentwicklungen. Luca erklärt sich bereit die beiden Varianten zusammenzuführen. Für diese Arbeit benötigt Luca jedoch ein paar Stunden. Charlie ist ungeduldig und möchte weiter programmieren.

Welche Funktionen (Eigenschaften) von Git könnten Luca und Charlie bei Ihrem Problem helfen, sodass Luca die Änderungen nicht manuell zusammenführen muss und Charlie nicht auf Luca warten muss?

---

Sie können Git benutzen um gleichzeitig an ihren Code zu arbeiten und mithilfe von Commits, Pushes/Pulls, Merges und Branches dran zu arbeiten.

---

## Kapitel 2 - Die Diskussion
![Luca und Charlie Teil 2](/05_Einfuehrung-Versionverwaltung/images/LucaCharlieTeil2.PNG)

Charlie möchte gerne Git einsetzen. Doch Luca findet Git doof und will unbedingt mit Boxdrop (Platzhalter für *Filesharing*-Dienste wie Google Drive, Dropbox, OneDrive, usw.) arbeiten. "Das sei viel einfacher. Man müsse nicht ständig wie bei Git *commit messages* schreiben und die Dateien werden automatisch synchronisiert.", argumentiert Luca. Luca schlägt vor, dass er einen Ordner einrichtet und dort den Quellcode der Applikation ablegt. Charlie findet das eine doofe Idee und möchte viel lieber auf GitLab ein gemeinsames Repository erstellen. "Dieses Tool wird von Softwareentwicklern weltweit eingesetzt", meint Charlie.

Mit welchen Sach-Argumenten könnte Charlie versuchen Luca zu überzeugen? Listen Sie entsprechende Argumente auf und belegen Sie Ihre Aussagen mit Quellenverweisen (Links).

---

Mithilfe von Git kann man gleichzeitig am Code arbeiten, und Code zusammenführen mit Merges. Commit messages sind zwar "aufwendig", aber so ist auch der alte Code archiviert und man könnte besser verstehen, was man früher gemacht hat.

---

## Kapitel 3 - Das Fiasko
![Luca und Charlie Teil 3](/05_Einfuehrung-Versionverwaltung/images/LucaCharlieTeil3.PNG)

Luca hat bei der Diskussion *Gitlab vs Boxdrop* gewonnen. Die beiden arbeiten nun mit Boxdrop. Charlie ist überhaupt nicht glücklich damit, aber sie hat es aufgegeben mit Luca zu streiten. Für sich selbst hat Charlie sich ein Git-Repository eingerichtet und kopiert die Änderungen von Luca manuell in ihr Repository. An einem Abend erhält Charlie einen Anruf von Luca. Er ist völlig verzweifelt und erzählt ihr, dass er eine Änderung vorgenommen hat und nun das ganze Programm nicht mehr funktioniert. Er könne zwar die alten Dateien aus dem Dateiversionsverlauf von Boxdrop wieder herstellen, aber er habe die Übersicht verloren. Er möchte einfach wieder auf alten Stand vor seinen Änderungen zurück. Da Charlie schon länger lokal mit einem Git-Repository arbeitet, gibt sie ein paar Befehle in ihr Git-Bash Terminal ein und schickt Luca eine funktionierende Version als ZIP. Luca ist verblüfft wie schnell Charlie das hingekriegt hat.

Welche Git Befehle hat Charlie höchstwahrscheinlich verwendet und was bewirken diese Befehle?

---

Mit git revert (commit id) kann man zu einem älteren Commit reverten (zurückgehen) und dieses exportieren, mit <br>
`git archive --format zip --output "/path/" "branch"`

---

## Kapitel 4 - Git the Power Toy

![Luca und Charlie Teil 3](/05_Einfuehrung-Versionverwaltung/images/LucaCharlieTeil4.PNG)

Nach dem Fiasko hat sich Luca von Charlie überzeugen lassen, doch ein gemeinsames Repository auf GitLab zu erstellen. Seitdem arbeiten Luca und Charlie mit dem gemeinsamen Repository. Beide erstellen für jede Änderung (Funktionserweiterung, Bugfix, usw.) einen *Commit* und *pushen* ihre *Commits* auf das Repository. Teilweise müssen Sie zuerst die Änderungen des anderen *pullen* und die Änderungen *mergen*. Charlie hat nun eine neue Idee für die Quiz Applikation. Die neuen Funktionen haben aber fundamentale Änderungen mit vielen Umstrukturierungen zur Folge.

Welche Funktion von Git kann Charlie dabei helfen?

---

Sie können einen neuen Branch erstellen und mit git checkout (Branch name), den Branch wechseln. <br>
So kann man zwei komplett verschiedene Codes, die mit dem Code zu tun haben, im gleichen Repository speichern.
Mit Forks kann ich an einem Repository arbeiten und mit hilfe von Push Requests diesen im originalen Repository anfordere, dass man meinen Code benutzt.

---

## Kapitel 5 - Organisation

![Luca und Charlie Teil 3](/05_Einfuehrung-Versionverwaltung/images/LucaCharlieTeil3.PNG)

Die Quiz Applikation gibt viel Aufwand und die beiden haben grosse Pläne. An den gemeinsamen Meetings halten sie ihre Ideen auf einem Notizzettel fest. Diesen fotografieren sie anschliessend und schicken den in ihren Gruppenchat "The super Quiz Gang". Jedoch haben die beiden Mühe eine Übersicht über die vielen geplanten Erweiterungen zu behalten.

Welche Funktion von den Git Hosting Providern (GitLab, GitHub, usw.) könnten Luca und Charlie dabei unterstützen?

Wie würden Luca und Charlie diese Funktion konkret verwenden?

---

In GitHub kann man "Projects" brauchen, um zukünftige Features hinzuzufügen oder um Fehler zu beheben. <br>
"Issues" sind auch möglich, diese können auch von externen Benutzer erstellt werden.


---

## Hinweise
Beachten Sie folgende Dinge:
 - Begründen Sie jeweils Ihre Antworten möglichst genau.
 - Formulieren Sie alle Texte (ausser natürlich Gesetztestexte und ähnliches) selbst.
 - Eine direkte Übernahme von Text (bspw. aus dem Internet) gilt nicht als Antwort!
 - Arbeiten Sie mit Screenshots und Bildern.
 - Geben Sie an, wo Sie die Beispiele gefunden haben (Quellen).


## Quellen
 - [Why Use Git for Your Organization](https://www.atlassian.com/git/tutorials/why-git)
 - [Why You Should Use Git](https://www.webfx.com/blog/web-design/why-you-should-use-git/)

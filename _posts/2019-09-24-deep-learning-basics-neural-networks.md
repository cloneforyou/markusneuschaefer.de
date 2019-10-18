---
layout: "post"
# "post" oder "no-title-post" (keine Überschrift)
title: "Erste Schritte mit Deep Learning"
date: "2019-09-24 15:05"
description: 'Deep-Learning-Grundlagen mit praktischen Anwendungen: Schon mit einfachen Tutorials lassen sich brauchbare Prognosen entwickeln'
image: "/assets/img/2019/09/2019-09-Neural-Network-Homer.png"
twitter-large-image: "/assets/img/2019/09/2019-09-Neural-Network-Homer.png"
# large image = 2:1 ratio (w:h)
insert-toc: true
categories:
- 'Essays'
tags:
- 'Deep Learning'
- 'Machine Learning'
- 'Tutorials'
- 'Weiterbildung'
permalink: "/deep-learning-basics-neural-networks"
published: true
---

<figure class="aligncenter">
	<img width="200" src="/assets/img/2019/09/2019-09-Neural-Network-Homer.png" alt ="Homer Simpson und Neural Networks"/>
</figure>

*TLDR: Grundwissen zu Machine-Learning lohnt sich für alle, die mit Daten arbeiten: Bereits mit einfachen Tutorials lassen sich erste Anwendungen und Prognosen erstellen. Der Beitrag stellt ein Tutorial vor und einige ML-Grundlagen mit Beispielen aus Bank, Bürokratie und Simpsons*

Ich beschäftige mich gerade mit dem Thema Machine Learning und bin überrascht, wie schnell man von den Grundlagen zu ersten Ergebnissen kommt. In einem [Blogartikel](https://medium.com/@pushkarmandot/build-your-first-deep-learning-neural-network-model-using-keras-in-python-a90b5864116d) erstellt man zum Beispiel Prognosen, mit welcher Wahrscheinlichkeit Kunden abwandern, Schüler durchfallen, oder Besucher einer Website abspringen. Dies lässt sich sofort in der Praxis einsetzen und ich kann nur empfehlen, diese Schritte auch einmal durchzugehen, die Möglichkeiten und Grenzen dieser Techniken zu verstehen. Wer Deep Learning aber schon kennt, kann auch direkt zu den möglichen <a href="{{page.url}}#anwendungen-abwanderungsquote-und-prognosen">Anwendungen</a> springen.

<!-- more -->
* TOC
{:toc}

## Probleme lösen mit Deep Learning und künstlichen neuronalen Netzen

Im Bereich des Machine Learning ist der Ansatz des Deep Learning ein guter Einstieg. Diese Verfahren bewähren sich besonders in solchen Fällen, wo viele verstreute, "unpräzise" Daten zu einem Ergebnis verarbeitet werden sollen, ohne dass ein bestimmter Lösungsweg bekannt wäre. Bekannte Beispiele sind etwa die Bild- oder Spracherkennung, aber auch Frühwarnsysteme oder Prognosen.

Ein neuronales Netz wird zuerst mit einem Beispiel-Datenset trainiert. In vielen Wiederholungen und Korrekturen entwickelt es ein Modell, wie die verschiedenen Variablen in jeder Zeile zusammenwirken, damit das Ergebnis zustande kommt. Wenn das Modell mit den Variablen im Trainingsset zu annähernd ähnlichen Ergebnissen kommt, ist das Training abgeschlossen. 

## Lernende Organisationen als Analogie für Deep Learning  

Wie lässt sich das arbeitsteilige "Lernen" in neuronalen Netzen in etwa vorstellen? Der Ablauf erinnert an das Lernen in großen Organisationen, zumindest in sehr bürokratischen Organisationen: Abteilungen schreiben Berichte, aus denen andere Abteilungen dann wieder neue Berichte erstellen. Wenn die Berichte der leitenden Stelle nicht gefallen, erhalten die Berichtersteller neue Vorgaben und das Ganze beginnt wieder von vorne.
 
Ein anderes Beispiel für solche arbeitsteilig-lernenden Prozesse wäre die Produktion nach bestimmten Kundenvorgaben. Dies wird sehr schön in einer Simpsons-Folge illustriert, in der ein Auto genau nach Homers Wünschen gebaut wird:


<iframe width="560" height="315" src="https://www.youtube.com/embed/WPc-VEqBPHI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
 
In diesem Clip entwickeln die Vertreter der Abteilungen bestimmte Vermutungen, wie sich Homers Wünsche erfüllen lassen. Dieser lehnt viele Vorschläge ab, und die Ingenieure passen ihre Pläne immer weiter an, bis das Resultat schließlich Homers Vorstellungen entspricht. Leider teilen die meisten anderen Kunden Homers Ideen nicht, so dass das neue Auto ein Flop wird. 
 
Übertragen auf Deep Learning ist dies keine Überraschung: Trainiert man ein neuronales Netz mit zu wenigen und den falschen Daten, wird das Ergebnis ebenfalls nicht überzeugen. Im besten Fall merkt man dies noch rechtzeitig, statt auf dieser Grundlage wichtige Entscheidungen zu treffen ("die KI will es so"). Hätte man das Produkt neben Homer noch mit tausend anderen Kunden getestet und weitere Variablen wie die Produktionskosten herangezogen, wäre das Ergebnis vermutlich besser ausgefallen. 
 
In realen Produktionsabläufen ist es natürlich kaum möglich, die Prioritäten mit tausenden von Rückmeldungen immer wieder anzupassen. Mit neuronalen Netzen gelingt dies aber ganz einfach. 
 
## Wie künstliche neuronale Netze arbeiten 

Ähnlich wie die Abteilungen und Ingenieure in dem vorherigen Beispiel nimmt das neuronale Netz verschiedene Variablen in sogenannten "_Neuronen_" (auch "Units" oder "Knoten") auf. Diese können Informationen von außen oder von anderen Neuronen aufnehmen, nach bestimmten Gewichtungen modifizieren und weitergeben. Dies geschieht in verschiedenen Schichten; neben dem _Input-_ und dem _Output-Layer_ gibt es mehrere _Hidden Layers_, welche die Berechnungen der vorherigen Schicht aufnehmen.

<figure class="aligncenter">
	<img width="200" src="/assets/img/2019/09/2019-09-Neural_network.png" alt ="Bild: Künstliche neuronale Netze"/>
	<figcaption>Bild: Künstliche neuronale Netze, Quelle: <a href="https://commons.wikimedia.org/wiki/User:Dake">Dake</a>, <a href="https://commons.wikimedia.org/wiki/User:Mysid">Mysid</a>, <a href="https://commons.wikimedia.org/wiki/File:Neural_network.svg">Neural network</a>, <a href="https://creativecommons.org/licenses/by/1.0/legalcode" rel="license">CC BY 1.0</a></figcaption>
</figure>

Die künstlichen "Neuronen" nehmen die Werte aus anderen Layers nicht einfach nur auf, sie verarbeiten sie auch nach bestimmten Aktivierungsfunktionen. Wenn das neurale Netzwerk etwa in der Wettervorhersage eingesetzt wird, kann ein solches Neuron zum Beispiel die Werte für den Niederschlag und die Luftfeuchtigkeit und den Temperaturwert des Vorjahres berücksichtigen, während ein anderes Neuron die Werte für aktuelle Temperatur, Luftfeuchtigkeit und Jahreszeit mit aufnimmt. Diese Werte werden in der nächsten Schicht dann zusammengeführt und in neue Berechnungen aufgenommen.

<figure class="aligncenter">
	<img width="200" src="/assets/img/2019/09/2019-09-Artificial-Neuron-Model_deutsch.png" alt ="Bild: Künstliche Neuronen"/>
	<figcaption>Bild: Künstliche Neuronen, Quelle: 
<a href="https://commons.wikimedia.org/wiki/User:Chrislb">Chrislb</a>, <a href="https://commons.wikimedia.org/wiki/File:ArtificialNeuronModel_deutsch.png">ArtificialNeuronModel deutsch</a>, <a href="https://creativecommons.org/licenses/by-sa/3.0/legalcode" rel="license">CC BY-SA 3.0</a>  
  </figcaption>
</figure>

## Training eines neuronalen Netzwerks

Ein neuronales Netz muss zunächst trainiert werden. Dazu braucht es ein Trainingsset an Daten mit bestimmten vorgegebenen Ergebnissen, mit denen das "Training" des Netzes möglich wird. Wie aussagekräftig die Ergebnisse des neuronalen Netzes sind, hängt von der Qualität und Menge der Daten im Trainingsset ab.

Zeile für Zeile spielen die künstlichen Neuronen die verschiedenen Variablen durch und versuchen, sich den vorgegebenen Ergebnissen im Trainingsset anzunähern. Falls der Output der letzten Schicht nicht dem erwarteten Wert entspricht, werden die Gewichtungen angepasst und der Prozess beginnt von vorne. Auf diese Weise testet das neuronale Netz immer wieder neue Kombinationen und Gewichtungen der verschiedenen Variablen, bis seine Ergebnisse schließlich den vorgegebenen Werten entsprechen.

<iframe src="https://giphy.com/embed/4LiMmbAcvgTQs" width="480" height="327" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/neural-networks-4LiMmbAcvgTQs">via GIPHY</a></p>

Das automatische 'Lernen' der künstlichen 'Neuronen' läuft in mehreren Schichten ab. Es gibt mindestens drei Schichten: Den **Input Layer**, in dem die Daten aus dem Trainingsset aufgenommen werden und dazu einen oder mehrere **Hidden Layers**, in denen die Daten weiter verarbeitet werden. Die Neuronen nehmen Werte auf, passen diese mit unterschiedlichen Gewichtungen an, und geben sie an die nächste Schicht weiter, bis sie schließlich im **Output Layer** – der letzten Schicht – ausgegeben werden. 

Wie in der Animation deutlich wird, ist der Lernvorgang mit dem Output noch nicht beendet. Der Output wird mit dem vorgegebenen Wert im Trainingsset verglichen. In dem Beispiel mit der Wettervorhersage könnte das neuronale Netzwerk mit den Werten der Vorjahre gefüttert werden und die errechnete Temperatur dann mit der tatsächlichen Temperatur abgleichen.

Bei Abweichungen von dem vorgegebenen Wert werden die Gewichtungen der vorherigen Schichten nach unterschiedlichen **Backpropagation**-Verfahren angepasst. Nach einigen tausend oder einigen zehntausend Durchläufen ist das Modell schließlich so weit, dass es mit einer hohen Wahrscheinlichkeit ähnliche Ergebnisse produziert, wie sie im Trainingsset angelegt sind. 
 
## Anwendung: Welche Kunden sind bald weg?

<span id="anwendungen"></span>Mit Deep Learning-Verfahren lassen sich in komplexen Datensets Muster herausarbeiten, die man sonst nicht bemerkt hätte. Ein Beispiel aus einem [Udemy-Kurs](https://www.udemy.com/deeplearning/) zu neuronalen Netzen: Eine Bank stellt fest, dass viele Kunden abwandern und möchte wissen, woran das liegt und ob sich der Trend fortsetzt. Es gibt einen Datensatz mit 10.000 Kundendaten, in denen verschiedene Faktoren erfasst sind wie z.B. Credit Score, Wohnort, Kontostand, geschätztes Einkommen. Es gibt also eine große Tabelle mit zehn unabhängigen Variablen und einer abhängigen Variable: der Frage, ob der Kunde in den nächsten Monaten wechselt (true / false).

<figure class="aligncenter">
	<img width="200" src="/assets/img/2019/09/2019-09-Churn_Modelling.png" alt ="Bild: Churn Modelling"/>
	<figcaption>Bild: Beispieldatensatz zu Churn Modelling, gefunden bei<a href="https://medium.com/@pushkarmandot/build-your-first-deep-learning-neural-network-model-using-keras-in-python-a90b5864116d">Pushkar Mandot </a></figcaption>
</figure>

In wenigen Minuten (na gut, eher eine Stunde) hat man mit TensorFlow, Theano und der Keras-Library ein neuronales Netz trainiert, mit dem man die Wahrscheinlichkeit vorhersagen kann, dass Kunden die Bank verlassen ("churn rate"). Eine ausführliche Anleitung mit Schritt-für-Schritt-Videos gibt es in dem [Deep-Learning-Kurs von Kirill Emerenko auf Udemy](https://www.udemy.com/deeplearning/), wer sich mit Python schon ein wenig auskennt, kann das Beispiel auch mit der Zusammenfassung in einem [Blogartikel von Pushkar Mandot](https://medium.com/@pushkarmandot/build-your-first-deep-learning-neural-network-model-using-keras-in-python-a90b5864116d) durchgehen. 

Dieses Verfahren lässt sich leicht für andere Datensätze und Fragestellungen anpassen. Einige Beispiele:

- Banken und andere Finanzdienstleister: Bei welchen Kunden gibt es ein hohes Risiko, dass sie abwandern? Hier lassen sich viele Parameter aus dem Tutorial übernehmen. 
- Online-Shops: Wie wahrscheinlich sind Reklamationen je nach der Interaktion der Kunden auf der Shop-Seite? Welche Kunden kaufen wahrscheinlich wieder etwas?
- NGOs und Non Profit-Organisationen: Welche Spenden könnten künftig ausfallen? Wo ist ein größeres Engagement wahrscheinlich?
- Schulen und andere Bildungseinrichtungen: Welche Schülerinnen und Schüler sind besonders versetzungsgefährdet? Bei welchen Kursteilnehmern gibt es ein hohes Risiko, dass sie abbrechen?

## Neue Perspektiven, aber keine automatischen Entscheidungen
 
Machine-Learning-Verfahren wie Deep Learning wirken geradezu magisch: In einer chaotischen Datenmenge entdecken sie neue Muster; sie generieren nützliche Prognosen und weisen auf unerwartete Zusammenhänge hin. Wie an dem Beispiel mit der Autoherstellung nach den Vorgaben des 'Trainingssets' Homer Simpson deutlich wurde, hängen die Ergebnisse von vielen Entscheidungen ab. Neben der Auswahl der Trainingsdaten sind auch Faktoren wie die Anzahl der Datensätze, die Auswahl der Aktivierungsfunktionen oder die Netzwerkarchitektur entscheidend für das Ergebnis. 
 
Wichtige und folgenreiche Entscheidungen lassen sich daher nicht einfach automatisieren, schon gar nicht auf der Grundlage einiger Onlinekurse und vordefinierter Frameworks. Bei folgenreichen Prognosen wie Aussagen über den Bildungserfolg wäre es zudem fatal, wenn der Hinweis einer 'künstlichen Intelligenz' das Ergebnis negativ beeinflusst. Wenn ein Bildungsanbieter die Kursteilnehmer zum Beispiel mit einem solchen Algorithmus bewertet, kann es zum sogenannten Pygmalion-Effekt kommen: Wenn alle annehmen, dass der Schüler schwach ist, sinken auch dessen Leistungen. 
 
Ähnlich ist es bei unternehmerischen Entscheidungen: Lässt sich allein mit Machine-Learning-Verfahren erkennen, mit welchen Bewerbern eine Stelle besetzt wird? Hier gibt es das Risiko, dass das neuronale Netz Diskriminierung der Vergangenheit wiederholt und auch für die Zukunft festschreibt – "[discriminatory bias](https://towardsdatascience.com/machine-learning-and-discrimination-2ed1a8b01038)" bleibt ein Problem.  Wie jedes Tool haben auch Deep Learning-Verfahren ihre Grenzen. 
 
Um neue Erkenntnisse zu gewinnen oder neue Muster in komplexen Daten zu erkennen, um bessere Fragen zu entwickeln und Zusammenhänge zu verstehen, ist dieses Verfahren äußerst praktisch. In dem obigen Beispiel mit der Bank lässt sich auf diese Weise eine begründete Vermutung aufstellen, welche Kunden bald abwandern könnten. Wenn man diese Gruppe nun genauer untersucht, findet sich im nächsten Schritt vielleicht eine bessere Strategie, wie man der Abwanderung vorbeugt. In dem Beispiel mit dem schulischen Erfolg könnte eine derart begründete Prognose helfen, bei Lernschwierigkeiten rechtzeitig Unterstützung anzubieten. 
 
Wichtig ist in beiden Fällen, dass das Ergebnis des Deep Learning-Verfahrens als Hinweis behandelt wird und die Grenzen des Verfahrens für alle transparent sind. Ähnlich würde die Einschätzung einer Unternehmensberatung oder eines Mitarbeiters behandeln: Eine neue Perspektive, um neue Aspekte zu erkennen und Entscheidungen mit einer besseren Grundlage zu treffen. Die Vorteile sollte man aber auch nicht unterschätzen: Deep Learning ist ein äußerst nützliches Werkzeug für alle, die sich mit Daten beschäftigen. Schon nach einer kurzen Einführung lassen sich erste Prognosen in künstlichen neuronalen Netzen entwickeln: Die ML-Frameworks dürften in den nächsten Jahren noch zugänglicher werden. Der Einfluss automatisierter Prognosen und Entscheidungsverfahren im Alltag wird damit ebenfalls zunehmen.

*Kennt ihr weitere Tips, ML-Links oder andere Tutorials, die sich sofort anwenden lassen? Ich freue mich auf einen Hinweis.*

## Links

Udemy-Kurs von Kirill 

[Udemy-Kurs von Kirll Emerenko zu Deep Learning mit Python und Neural Networks](https://www.udemy.com/deeplearning/). 

[Beispiel-Tutorial aus dem Kurs: Abwanderungsquote (Churn Rate) mit Tensorflow und Keras berechnen](https://medium.com/@pushkarmandot/build-your-first-deep-learning-neural-network-model-using-keras-in-python-a90b5864116d)

*Hinweis zu dem Tutorial*

*Der Code wirft erstmal Fehler aus, da sich die Libraries seit 2017 ein wenig verändert haben. Auch bei der Installation des Frameworks ergeben sich manche Fragen für die Suche bei Stackoverflow. Solcherart Fehler zu beheben, ist natürlich auch eine Methode, sich etwas Python anzueignen 🙂. Freundlicherweise werden die nötigen Korrekturen aber direkt in der Konsole angezeigt, statt*

`classifier.add(Dense(output_dim = 1, init = 'uniform', activation = 'sigmoid'))`

*schreibt man in der Version von 2019 nun*

`classifier.add(Dense(activation="sigmoid", units=1, kernel_initializer="uniform"))`
 
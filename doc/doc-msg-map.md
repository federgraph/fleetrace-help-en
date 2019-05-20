---
layout: default
lang: de
title: Nachrichtenplan
---

<h1>Nachrichtenplan</h1>

<h2>Das Bild zum Nachrichtenplan</h2>
<p>Die obere Zeile im Bild ist die Hauptachse des Nachrichtenverkehrs zwischen 
Inputclient, Serveranwendung und Output-Klient.
</p>

<p>Ebenfalls dargestellt/angedeutet sind interne Verbindungen (gekennzeichnet 
mit #).
</p>
<p>Die Punkte B und C sind abstrakte Verbindungs-Punkte. Real existieren externe 
und interne Verbindungspunkte. Es gibt einen Softwareschalter zwischen den 
internen und externen Punkten (Operation Connect/Disconnect).&nbsp; Im Zustand 
Disconnected ignoriert der Server den externen Nachrichtenverkehr.
</p>

<p>Unterhalb der Hauptachse ist die Switch Anwendung dargestellt. Mit Hilfe der 
Switch Anwendung können Serverdaten synchronisiert sowie Switch Klienten indirekt 
angeschlossen werden.
</p>

<p>Ähnlich wie mit dem Switch können zwei Server über eine Bridge synchronisiert 
werden. Bridgeverbindungen sind im Bild nicht dargestellt. Wegen der Umkehr der 
Initiative beim Verbindungsaufbau sind beim Einsatz der Bridge in der Regel 
keine Firewall Einstellungen notwendig. Silverlight Anwendungen werden zum 
Beispiel über eine Bridge angeschlossen.
</p>

<p>Nachrichten können auch über eine eventuell im Server eingebettete Website 
gesendet werden. Dies betrifft sowohl Eingangsnachrichten (Ajax), die 
Anforderung von Reports und Steuerkommandos.</p>

<p>Die Anbindung von Bridge/Website erfolgt über die (internen) 
Verbindungspunkte B und C. Die externen Verbindungspunkte B, C und H sind in 
jedem Fall TCP-Server Sockets (Orange). Punkt V (Switch) ist ein 
Http-Verbindungspunkt.
</p>

![RiggVar MsgMap drawing](../images/MsgMap.png)

<h2>Verbindung AB</h2>
<ul>
<li>B1 im linken oberen Kasten bedeutet, dass eine Message von A nach B gesendet 
werden kann. </li>
<li>Der Buchstabe bezeichnet das Ziel. </li>
<li>Die Herkunft kann durch die Verbindungslinie eindeutig zugeordnet werden.
</li>
<li>Die Ziffer nach dem Buchstaben kennzeichnet die verschieden Fälle. </li>
<li><strong>B1 Input (1)</strong> - eine einzeilige Message kann vom Input zum 
Server gesendet werden. </li>
<li><strong>B2 Input (n)</strong> - der Server kann mehrzeilige Messages vom 
Input empfangen.
</li>
<li><strong>B3 Request (1)</strong> - die Message enthält einen einfachen 
Request. </li>
<li><strong>B4 Request (n)</strong> - die Message enthält einen mehrfachen 
Request (n-fach).
</li>
<li><strong>B5 Request + Input</strong> - die Message enthält neben Input 
mindestens einen Request.
</li>
<li><strong>A1 Receipt</strong> - steht für die optionale Quittung auf eine 
einzeilige Message.
</li>
<li><strong>A2 Response</strong> - bezeichnet die Antwort auf einen einfachen 
Request (mit oder ohne Input) </li>
<li><strong>A3 Response (n)</strong> - bezeichnet die zusammengesetzte Antwort 
(xml CDATA) auf einen mehrfachen Request am Input.</li>
</ul>
<h2>Verbindung CD</h2>
<ul>
<li><strong>D1 Multicast</strong> - jede einzeilige Message vom Input wird an 
alle am Output angeschlossenen Systeme weitergesendet. Dies erfolgt nach 
Verarbeitung und Neuberechnung (unter Verwendung der internen MessageQueue). </li>
<li><strong>C1 Request</strong> - ein Output Klient fordert am Verbindungspunkt C 
(Server Output Socket) einen Report an, der unverzüglich generiert und 
zurückgesendet wird.</li>
<li><strong>D2 Report</strong> - ein zuvor angeforderter Report erreicht den 
Client-Socket D der Output Anwendung. </li>
</ul>
<h2>Verbindung #B </h2>
<ul>
<li><strong>B6 Calc Stateless</strong> - Mehrzeilige Message, gesendet über 
interne Verbindung an Input B. Enthält die vollständigen Eventdaten, identisch 
mit einem Backup. Enthält weiterhin einen oder mehrere Requests für 
zurückzuliefernde Reports. Das primäre Anwendungsobjekt (BO) wird neu erzeugt 
und nach dem Methodenaufruf (Calc) wieder freigegeben. Es ist der typischer Fall 
bei einer Webanwendung. Es wird aber auch beim statuslosen 'Test/Calc-Server' 
verwendet. </li>
<li><strong>B7 Calc Statefull</strong> - Mehrzeilige Message, gesendet über 
interne Verbindung an Input B. Enthält einen Request für den zurückzuliefernden 
Report. Das BO wird nicht neu erzeugt, der Status des BO wird beibehalten. </li>
<li><strong>B8 Event Type ID</strong> - markiert eine interne Verbindung mit der 
Eventtyp-ID. Dies hat eine Bedeutung in einem Multieventtypserver, der über 
einen vorgeschalteten Messagerouter verfügt. Damit ist dieser in der Lage die 
Nachrichten über die richtige interne Verbindung weiterzuleiten, d. h. die 
Message zur Verarbeitung an das BO vom richtigen Typ zu senden. Jedes BO hat die 
Verbindungspunkte B und C. </li>
<li><strong>#2 Response (1)</strong> - wie A2, nur über interne Verbindung </li>
<li><strong>#3 Response (n)</strong> - wie A3, nur über interne Verbindung </li>
</ul>
<h2>Verbindung C#</h2>
<ul>
<li><strong>#1 Multicast</strong> - steht für ein Messagemulticast über interne 
Verbindungen. # kennzeichnet interne Verbindungen. Interne Verbindungen werden 
zum Beispiel aufgebaut, wenn in einer Serveranwendung Input-&nbsp; und/oder 
Output Klienten integriert wurden. </li>
</ul>
<h2>Verbindung XY</h2>
<ul>
<li><strong>Y1 Plugin</strong> - ein Switch Klient fordert den Aufbau von (ein 
oder zwei) Verbindungen an. Dazu wird Verbindungspunkt Y verwendet, den der 
Switch bei Programmstart öffnet. Daraufhin wird der Switch die Verbindungen EB 
und/oder FC herstellen, wie angefordert, wenn es sich um einen Server handelt. 
Im Falle eines Switch Klienten wird stattdessen die Verbindung GH aufgebaut. Es 
sind in jedem Fall ganz normale Socket Verbindungen zum jeweiligen Partner. </li>
<li><strong>Y2 Plugout</strong> - Umkehr von Plugin, der Switch schließt 
daraufhin die Verbindungen. Ein Switch Klient sollte bei Programmende automatisch 
die Verbindung schließen. Normalerweise ist das Schließen eine manuelle Aktion 
(z.B. verfügbar über das Hauptmenü).
</li>
<li><strong>Y3 Synchronize</strong> - Falls der Switch über einen eingebauten 
Cache verfügt können damit alle im Cache vorhandenen Reports als ungültig 
markiert werden (Age+1). Dies kann einen automatischen&nbsp; Aktualisierungsdurchlauf 
starten. </li>
<li><strong>Y4 Upload</strong> - Ankündigung eines Uploads, unmittelbar 
nachfolgend wird Y5 gesendet. Im Switch wird ein Flag gesetzt, so dass die 
nachfolgende Message abweichend vom normalen Modus als Backup gespeichert wird. </li>
<li><strong>Y5 Upload Data</strong> - Senden eines Backups zur Speicherung im 
Hauptspeicher der Switch Anwendung. </li>
</ul>
<h2>Verbindung UV</h2>
<ul>
<li><strong>V1 Download</strong> - Anforderung eines Downloads. </li>
<li><strong>U1 Download Data</strong> - die Antwort, also die Kombination aus 
gespeichertem Backup und Log. Das Log kann, je nach Event Typ, mit einer 
Merge-Funktion automatisch komprimiert werden, so dass sich nur das jeweils 
letzte Telegramm der jeweiligen Adresse im Log befindet. </li>
</ul>
<h2>Verbindung GH</h2>
<p></p>
<ul>
<li><strong>G1 Cache Request</strong> - der Switch Klient fordert einen Report 
an, der aus dem im Switch eingebauten Cache stammen soll. </li>
<li><strong>G2 Live Request</strong> - der Switch Klient stellt eine Report 
Anforderung, die sofern möglich, an einen Server durchgestellt wird. Ein 
eventuell vorhandener Cache wird nicht benutzt. Wenn mehrere Server am Switch 
angeschlossen sind so wird der als Masterserver gekennzeichnete Server den 
Request erhalten. Falls kein Server als Masterserver gekennzeichnet ist wird 
automatisch mit einer einfachen Methode ein Server bestimmt. </li>
<li><strong>G3 Current Request</strong> - die Anforderung verlangt, dass ein 
Report nur dann aus dem Cache gezogen wird, wenn der Report im Cache als aktuell 
gekennzeichnet ist. Sonst wird die Reportanfrage synchron von einem Server 
bearbeitet.
</li>
<li><strong>G4 Input (1)</strong> - ein einzeiliger Input wird vom 
Switch Input Klient an den Switch übergeben, der diesen über Punkt E an einen 
Server weiterleitet. Die Bestimmung des Servers erfolgt wie bei G2. </li>
<li>Die Message <strong>F1</strong> zum Switch wird an alle Switch Output Klienten 
weitergeleitet. Eine Switch Verbindung GH ist entweder als Input oder als Output 
gekennzeichnet. Nur die Outputs erhalten Multicastmessages. Ein am Switch 
angeschlossener Output Klient verhält sich damit genauso wie ein am Punkt C 
angeschlossener normaler Output Klient. Lediglich der Socket Typ (Client oder 
Server) sowie die Initiative beim Verbindungsaufbau dreht sich um. 
Switch Klienten sind nur mittelbar verbunden, können aber den Cache abfragen.</li>
<li><strong>H1 Multicast</strong> - die Multicastmessage erreicht einen 
Switch Output Klienten.
</li>
<li><strong>H2 Report</strong> - ein angeforderter Report erreicht den 
Switch Klienten. </li>
</ul>
<h2>Verbindung WB</h2>
<ul>
<li><strong>B2 Blocking Request (1)</strong> - eine Anfrage G2 oder G3 kann vom 
Switch mit Hilfe eines blockierenden Requests B2 an einen Server gestellt 
werden. </li>
<li><strong>W1 Response (1)</strong> - die Antwort auf B2. Da die Anforderung 
blockierend ist kann die Antwort leicht an den anfordernden Switch Output 
zurückgeliefert werden. Die Antwort wird in der Regel zusätzlich im Cache 
gespeichert. Normalerweise wird der Cache mit asynchronen Requests über Punkt E 
gefüllt. </li>
</ul>
<h2>Verbindung FC</h2>
<ul>
<li><strong>C1 Request</strong> - ein weitergeleiteter Request von Punkt G, 
siehe C2. </li>
<li><strong>C2 Blocking Request</strong> - Es ist der Switch Implementierung 
überlassen, ob sie Anforderungen von Punkt G als C1- oder C2-Message 
implementiert. </li>
<li><strong>F1 Multicast</strong> - einzeilige Message, die mit Multicast vom 
Server weitergesendet wird.</li>
<li><strong>F2 Report</strong> - die Antwort auf einen Request für die 
Auslieferung eines Reports. </li>
</ul>

# BrushlessSewingMotor_Extension
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)


contact: github@brandtner.net

## 11/2022  ! Project is in progress, ask before you order PCB or other things. !

## INTRODUCTION

This is a extension for a cheap chinese 550/750W brushless servo motor for external control of speed, direction, etc.
to use in in e.g. Mini Lathe


first test with switch and potentiometer:
https://www.youtube.com/watch?v=qao7Rex1lZU

![SMC_Motor](https://user-images.githubusercontent.com/60114001/165738964-6df24e4b-6300-4330-b555-efc8d85aca5b.jpeg)

## STATUS

21.03.2023

the new ISO interface can optionally be equipped with an interface for speed control with 0-10V (Mach3) or 0-5V (Poti). The direction of rotation can also be changed and the spindle enabled via a Mach3 port or manual switch.

14.2.2023

![20221109_094954](https://user-images.githubusercontent.com/60114001/218690523-8f5d8bdb-bbb6-4eb8-ab9b-2e0aafa90d3a.jpg)

RPM Sensor

![20221109_094759](https://user-images.githubusercontent.com/60114001/218690800-126212ed-7c39-4500-b9d5-149846461a36.jpg)



05.09.2022

Beim Einbau in das Steuergehäuse habe ich nun festgestellt das es Änderungsbedarf gibt, es ist ziemlich eng und die Anordnung der Anschlüsse passt nicht so wirklich gut.
![Eingebaut_V1](https://user-images.githubusercontent.com/60114001/188422338-6319277f-3bb1-4920-8500-ef5a7ccae4dd.jpg)

Deshalb wird es eine zweigeteilte Lösung geben, 1. das Iso Ínterface, montiert auf dem SMC Controller, 2. davon getrennt die Steuerungsplatine, dann neu mit einem Ardunino Nano wegen der USB-Schnittstelle für einfache Updates.
Durch die Trennung ergibt sich auch die Mögichkeit eine andere Steuerung zu verwenden, z.B. Blackpill STM32F411. Der Ardunio ist schon arg an der Grenze des Flashspeichers.
![Steuerung_geplant](https://user-images.githubusercontent.com/60114001/188422512-2a967d47-297b-4406-8f3c-a5c5030f87ce.jpg)

Next Version (11/2022):

![IsoInterface_geplant_v16](https://user-images.githubusercontent.com/60114001/188422517-5289c238-f3bb-43c3-985c-c34c5e609fae.jpg)


08.07.2022

Die ursprüngĺiche Planung auf eine Hardwaredrehzahlmessung zu verzichten werde ich nicht mehr weiterverfolgen.
Die Softwarelösung funktioniert zwar zufriedenstellend, auch unter berücksichtigung des Getriebeschalters und der Untersetzungen von Motor und Getriebe, aber der Atmega ist durch die vielen Einstellungsmenüs am Ende der Kapazität.
Deshalb ist ein Drehzahlsensor an der Spindel erforderlich, damit entfällt die ganze Software für die Drehzahlberechnung und es ist Platz um die Schnittgeschwindigkeit für den Werkstückdurchmesser anzuzeigen.
Das finde ich nützlicher als den Drehzahlsensor einzusparen.
An der Hardware der Platine ändert sich nichts, war alles schon vorgesehen.


07.07.2022

Version 14.5

Änderungen an der Platine
Grund:
Einfügen eines optionalen ISP-Steckers.
Anschluss der RPM Sensors nach PB0 (ICP1) verlegt.
optinonal weitere Anschlussbuchse für den Pedalanschluss vorgesehen, zum direkten Kabelanschluss des Pedalkabels
an den originalen Stecker des SMC. Kein zusätzlicher JST Stecker J9 auf dem SMC Board notwendig. 

22.6.2022

Version 14.2

Änderungen an der Platine
Grund:
JST Stecker J3 Fehler in der Ausrichtung beseitigt


20.6.2022

Version 14.1

Änderungen an der Platine
Grund:
OK2 Anschlüsse vertauscht, optionale Widerstände R6,R30,R31
JST Stecker J3, Ausrichtung getauscht damit fertig konfektionierte Kabel zum SMC verwendet werden können.
Schaltung getestet (ohne RPM-Sensor und analog 0-10V Eingang, alles optional)

Wesentliche Funktionen der Software funktionieren:
Drehzahlregelung, Richtungsumschaltung, Drehzahlanzeige

03.06.2022 New PCB Version 12.2, Errors in PCB layout fixed. Basic software in progress.

12.05.2022 PCB Version 11.5 with galvanic isolation is in production 

30.04.2022 The goal is to fit the SMC controller board and everything else into the existing lathe front casing.

29.04.2022 optoisolation with separate powersupply is in work.

28.04.2022 under construction and brainstorming.


## PREVIEW

![Display3](https://user-images.githubusercontent.com/60114001/174744652-ce5d3712-e71a-4233-8b9c-0a11667b0ed3.jpg)
![Display4](https://user-images.githubusercontent.com/60114001/174744656-8c1be3cf-0af7-4bf9-b2b0-32b9f43f2d71.jpg)


## TODO

TODO: finalize software

## Features

- no changes on Controlerboard or Panelboard needed; 
- can be installed in the housing on existing attachments; 
- speedcontrol, rotary encoder;
- start/stop control,  button with LED; 
- rotation direction control, button with LED;
- securityswitch input for chuck guard;
- spindel RPM display (calculated and maesured)
- original SMC displaypanel can be used at same time 
- high temperture warning;
- rampup and down at start/stop
- isolated inputs/outputs for galvanic isolation from the mains voltage



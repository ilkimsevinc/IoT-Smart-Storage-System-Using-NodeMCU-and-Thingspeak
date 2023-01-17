# IoT Smart Storage System Using NodeMCU and Thingspeak

1 Introduction to the Problem

Suppose you are a store manager in charge of the
chocolate section. You need to see when there is
not enough chocolate to display. So, you need to
get chocolate from storage and get it to the section.
But if you don’t know the amount displayed, you
need to go to the section and get informed.
Or, you are a storage manager. You need to see
when there is not enough chocolate in the warehouse.
To be informed, you need to go to the warehouse
and inform yourself and order manually.
This will increase time waste and overall cost.
Also, this is not an efficient way to be informed.

2 Our Method to Solve the Problem

We developed a system to measure the weight
of the chocolate storage and calculate how many
pieces exist and visualize the data via Thingspeak.
Thingspeak can be achieved from both computer
and IOS app and uses HTTP protocol. If there
are chocolate pieces fewer than a predetermined
value, the system will inform the user via email
using IFTTT. After that, the user can be informed
of the storage and decide whether to order a new
chocolate package. In the processing part, first,
we assigned our hardware devices. We used Load-
Cell as our main sensor to measure the weight and
ESP8266 NodeMCU as the internet connector. We
also used HX711 Amplifier with LoadCell for calibration.
We added an LCD display to the system to
see outputs. LCD Display will be embedded in the
storage packet to help us inform. In our test case,
we determined one Petito chocolate as 6.5 grams.

2.1 Hardware Design

NodeMCU, Load Cell, HX711 Load Cell Amplifier
Module, Connecting Jumper Cables, 3.3V
Power Source - Computer in our case, LCD
Screen,
We stored 10 Petito chocolates. We coded that if
there are fewer than 5 Petito chocolates, the system
will send an email to the user using IFTTT and its
connection to Thingspeak. We coded the system simple 
so the end-user can change the product to,
for example, Ulker Cikolatalı Gofret, and arrange
the stock system for that product. We tested the
system with both chocolates and also Airpods for
testing if the calibration and measurement are true.
We tested with two different items but our main
case is for Petito chocolate.

2.2 Software Design

We used Arduino libraries:
Wire,
ESP8266WiFi: For NodeMCU connection,
HX711ADC: For calibration,
EEPROM: For storing calibration values.
LiquidCrystal: For LCD methods.
We used Thingspeak as our cloud server, data are
visualized there. It can also be reached from both
computer and IOS App.
We used IFTTT to send an email to the user when
stocks are lower than a predetermined value.

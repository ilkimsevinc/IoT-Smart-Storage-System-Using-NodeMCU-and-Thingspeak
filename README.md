# IoT Smart Storage System Using NodeMCU and Thingspeak

Smart Storage System project done by İlkim Sevinç and Tolga Değirmenci.

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

3 Results and Analysis

In our results, overall we get true values. In the
first several tests, we had issues with calibrating
the LoadCell. We get - values but we solved it by
calibrating it every time before we use the system.
Sometimes the weight is +-0.2, and we get very
little difference. This error is not considered since
it’s a very little error and surface area, the development
of LoadCell balance can be the error reason.
We used LCD Display to show measured values
but because of our lack of equipment, missing
component Potentiometer, and using a different
kind of LCD Display, we couldn’t see the display.
We got a high-resolution display by adding more
resistance to the circuit in one of our tests which
we also recorded as a video but then we changed
hardware and couldn’t get the same result later. If
we used a proper potentiometer and I2C LCD we
would get better display results. In real-life applications,
display on storage would be a good addon.
We calculated the piece value by dividing the total
weight by the initial weight, the weight of one
chocolate. But this part doesn’t work well in our
system because of using float data type and also
because of calibration value errors. We chose the
best result by getting the test with the lowest difference
in math.
We used Thingspeak Cloud Server for data storage
and data visualization. We used this instead
of other apps because we were familiar with it and
also we thought the types of different graphs and
widgets could be useful in our project. Another
benefit is that we can access the cloud via the IOS
app Thingview. We used a numeric display widget
and a total weight graph. These are two userfriendly
GUIs.Our best result is measured value = 61 and piece =
10. One piece of Petito chocolate is 6 grams. In
order to bypass the big difference errors in math,
we didn’t include float or double values.
We tested the measured value = 29 and piece = 4.
In this scenario, the app sent an email to the user’s
mail with the information ”StockLessThan5”. This
trigger occurs when there are 5 pieces present too.
The email is sent every 15 seconds because the
measurement delay is 15 seconds.

4 Conclusions and Future Work
In summary, we understood the method for measuring,
visualizing measured values, and creating
triggers for an unwanted situation. We had slight
hardware-related difficulties, but coding part and
making IoT-related connections were not so hard.
We think that there can be several upgrades for this
project. We think we can add a self-order function
in the future. Now, the system sends an email when
there is less than the wanted value but instead of
only informing the user, we can add an option to
order a wanted amount of packages automatically
or by user confirmation. The system can get input
from the user about how many packages they need,
or even calculate the amount needed and help the
user using data analytics.
We also thought this system can be used for not
only packaged products, like chocolate, crackers,
etc, but can be used for open beans, and legumes
(which are bought by the customer themself). In
this case, the system will tell when there is not
enough food in the container and inform the person
in charge to fill it. Or we can use this in the
textile sector for measuring buttons. There are so
many real-life use cases for this system.
We think that by making most of the storage management
with computer-aided information technologies
and using IoT technologies we can decrease
cost and time waste.



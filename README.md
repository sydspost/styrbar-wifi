# styrbar-wifi
IKEA Styrbar Remote connected to a Wemos D1 mini and controlled by Domoticz

For the full story, check my (dutch) website https://www.sydspost.nl/index.php/2022/01/29/ikea-tradfri-lamp-aansturen-met-domoticz/

In short the steps:
1. Solder jumpercables on VCC, GND and PA01, PA02, PA03 PA04 pins of the MGM210L chip
2. Connect jumpercables conform the following pinout and wiring schema with a Wemos D1 mini
![image](https://user-images.githubusercontent.com/45944257/152873281-58f7aa6a-7c5d-46b2-b611-82b991d261a5.png)
![Wiring schema Tradfri](https://user-images.githubusercontent.com/45944257/152876224-8205941d-667a-43d8-aff0-9a506edf1a15.png)

3. Flash ESPEasy Mega on Wemos D1 mini
4. In ESPEasy configure Domoticz MQTT controller, three dummy devices called on_off, dim and warmwhite. And four switches for GPIO-4, GPIO-5, GPIO-12 and GPIO-14, enable longpress for 500ms on low and high, enable rules.
5. Copy - Paste rules1.txt, rules2.txt and rules3.txt on the rules tab
6. Add a dummy device in Domoticz, type: color switch, subtype: ww, remember IDX
7. Change IDX in rulesset 3 in ESPEasy
8. Import Node-red flow in Node-Red. Change MQTT and HTTP-Request nodes, configure your MQTT server settings and hostnames.
9. Enjoy!

Note: Work in progress: Node-red sending events to ESPEasy based on MQTT, replacing the HTTP-requests

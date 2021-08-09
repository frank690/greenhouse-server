# garden-of-things
I like to be in the garden, but I also like to tinker and code.
This project is meant to combine both and turn my garden into a weired IoT version: the garden-of-things (GoT).
Let us hope that this projects starts off as well as the show but continues steadily instead of ending in a disappointment.

## Hardware
What hardware is used and how is it set up?

### Client(s)
One (or possibly multiple) esp32 units that are equipped with various sensors
(to measure e.g. temperature, sun intensity, humidity, ...). The measured values are streamed via MQTT to a home server (e.g. a raspberry pi).

### Server
A raspberry pi that has a [mosquitto mqtt broker](https://mosquitto.org/) running on it but also listens for incoming data of the client.
Once data is received, it is processed and put into a local postgres database.
The data in said database is then visualized in graphs (e.g. by using grafana, kibana or something DIY).
I also aim to make this dashboard publicly available by using some DynDNS routing.
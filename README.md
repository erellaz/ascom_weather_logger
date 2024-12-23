# Ascom weather logger
This script logs the weather in an astronomical observatory from various ascom compatible devices.

The best is to connect the script to the Observing Condition Hub (OCH), and let the OCH do the aggregation from various weather sources. 
The way I am set up, the OCH pull local temperature, humidity & dew from the Pegasus Power box V3 on the telescope, and the cloud & wind from Openweather Map Service.
It can of course connect directly to the Pegasus box or any other Ascom device with environment data.
Then it creates a log of the weather data, suitable to upload to observatory web page.

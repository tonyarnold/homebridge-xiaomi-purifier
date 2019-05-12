[![npm version](https://badge.fury.io/js/homebridge-xiaomi-purifier.svg)](https://badge.fury.io/js/homebridge-xiaomi-purifier)

# homebridge-xiaomi-purifier

This project is forked from [homebridge-mi-air-purifier](https://github.com/seikan/homebridge-mi-air-purifier.git).

This is the Xiaomi Mi Air Purifier plugin for [Homebridge](https://github.com/nfarina/homebridge). This plugin will add the air purifier and **Air Quality Sensor** to your Home app. This version is working with iOS 11 to add the device as air purifier in Home app.

![mi-air-purifier](https://cloud.githubusercontent.com/assets/73107/26249685/1d0ae78c-3cda-11e7-8b64-71e8d4323a3e.jpg)



### Features

 - Switch the unit on and off.
 - Switch between automatic and manual mode.
 - Change the fan speed.
 - Enable or disable the child lock.
 - Enable or disable the LED light.
 - Enable or disable the notification soun.
 - Display the current temperature.
 - Display the current humidity.
 - Display the current air quality.
 - Display the filter state.


### Installation

1. Install the required packages.

	```
	npm install -g homebridge-xiaomi-purifier miio
	```

2. Make sure that your Homebridge server is on the same network as your air purifier, then run following command to discover the token.

	```
	miio discover --sync
	```

3. You may need to wait for a few minutes until before you will receive a response similar to:

	```
	Device ID: 49466088
	Model info: Unknown
	Address: 192.168.1.8
	Token: 6f7a65786550386c700a6b526666744d via auto-token
	Support: Unknown
	```

4. Record the `Address` and `Token` values - you'll need these for your configuration file.

5. If you are getting `??????????????` as your token value, please reset your device and connect your Homebridge server directly to the access point advertised by the device. Once this is done, go back to Step 2 and try again.

6. Add following accessory to the `config.json`.

	```json
		"accessories": [
			{
				"accessory": "MiAirPurifier",
				"name": "Bed Room Air Purifier",
				"ip": "ADDRESS_OF_THE_AIR_PURIFIER",
				"token": "TOKEN_FROM_STEP_3",
				"showTemperature": true,
				"showHumidity": true,
				"showAirQuality": true,
				"enableLED": true,
				"enableNotificationSound": true
			},
			{
				"accessory": "MiAirPurifier",
				"name": "Living Room Air Purifier",
				"ip": "ADDRESS_OF_THE_AIR_PURIFIER",
				"token": "TOKEN_FROM_STEP_3",
				"showTemperature": true,
				"showHumidity": true,
				"showAirQuality": true,
				"enableLED": true,
				"enableNotificationSound": true
			}
		]
	```

	**Notes:** Set the values for `showTemperature`, `showHumidity`, `showAirQuality`, `enableLED`, `enableNotificationSound` to **true** or **false** to show or hide these sensors in Home.app.

8. Restart Homebridge, and your Mi Air Purifier will be added to Home.app.



### License

See the [LICENSE](https://github.com/seikan/homebridge-mi-air-purifier/blob/master/LICENSE.md) file for license rights and limitations (MIT).

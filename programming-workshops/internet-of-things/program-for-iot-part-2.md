---
description: Getting Started with a Web Interface to the IoT Device
---

# Program for IoT Part 2 ⏱

## Programming for the Web Interface

### Program the Particle IoT Device

#### 1. Create a new program in Particle build.

#### 2. Connect the temperature and humidity sensor to D2, connect the LED to A4, and connect your Argon device to your computer.

#### 3. Include the "**GROVE\_TEMPERATURE\_AND\_HUMIDITY\_SENSOR" and "**Grove\_ChainableLED" **libraries in your program as we have done before.**

#### 4. Copy and paste the code below (except of the #include parts) into your program.

```arduino
// This #include statement was automatically added by the Particle IDE.
#include <Grove_ChainableLED.h>

// This #include statement was automatically added by the Particle IDE.
#include <Grove_Temperature_And_Humidity_Sensor.h>

ChainableLED leds(A4, A5, 1);
DHT dht(D2);
double temp_dbl, humidity_dbl;
bool ledOn = false;

void setup() {
    //for the LED
    leds.init();
    leds.setColorHSB(0, 0.0, 0.0, 0.0);
    Particle.function("toggleLed", toggleLed);
    //for the temp and humidity
    dht.begin();
    Particle.variable("temp", temp_dbl);
    Particle.variable("humidity", humidity_dbl);
}

void loop() {
    float temp, humidity;
    temp = dht.getTempFarenheit();
    humidity = dht.getHumidity();
    temp_dbl = temp;
    humidity_dbl = humidity;
    delay(10000);
}

bool toggleLed(String args) {
    ledOn = !ledOn;
    if (ledOn) {
        leds.setColorHSB(0, 0.0, 1.0, 0.5);
    }
    else {
        leds.setColorHSB(0, 0.0, 0.0, 0.0);
    }
    return ledOn;
}    
```

**5. Save, Verify, and Flash the code to the Argon board.**

**6. Open the Console from particle build, select "my devices", and select your Argon.**

**7. Get the temp and humidity variables to check if all is working. Call the "toggleLed" function to ensure the light toggles.**

### **Program the Web Interface**

#### 1. Create a new replit program for HTML/CSS/JavaScript.

#### 2. Copy and paste the following for your \`index.html\` file.

```html
<!DOCTYPE html>
<html>

<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width">
	<title>IoT Test</title>
	<link href="style.css" rel="stylesheet" type="text/css" />
</head>

<body>
	<div id="login">
		<h3>Sign In to Access the IoT Device</h3>
		<input id="username">
		<input type="password" id="password">
		<button onclick="login()">Login</button>
	</div>
	<div id="iot-control" style="display: none;">
		<div id="temp">Loading...</div>
		<div id="light"></div>
		<button onclick="toggleLight()">Toggle Light</button>
	</div>
	<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/particle-api-js@8/dist/particle.min.js">
	</script>
	<script src="script.js"></script>
</body>

</html>
```

#### 3. Copy and paste the following for your \`script.js\` file.

```javascript
var particle = new Particle();
var token;

function login() {
	particle.login({
		username: document.querySelector("#username").value,
		password: document.querySelector("#password").value
	}).then(
		function(data) {
			console.log('API call completed on promise resolve: ', data.body.access_token);
			token = data.body.access_token;
			document.querySelector("#login").style.display = "none";
			document.querySelector("#iot-control").style.display = "block";
			displayTemp();
		},
		function(err) {
			console.log('API call completed on promise fail: ', err);
		}
	);
};

function displayTemp() {
	particle.getVariable({ deviceId: 'e00fce6872f90e7cbce1b406', name: 'temp', auth: token })
		.then(function(data) {
			document.querySelector("#temp").innerHTML = `The temperature is ${data.body.result} ℉`
		}, function(err) {
			console.log('An error occurred while getting attrs:', err.body);
		});
}

function toggleLight() {
	particle.callFunction({ deviceId: 'e00fce6872f90e7cbce1b406', name: 'toggleLed', argument: null, auth: token })
		.then(
		  function(data) {
				document.querySelector("#light").innerHTML = `The light is ${data.body.return_value ? 'on.' : 'off.'}`
		  }, function(err) {
		    console.log('An error occurred:', err);
		  });
}
```

#### 4. Run your replit.com program.

#### 5. Login to your web app with your Particle account.

#### 6. Confirm that the temperature is displayed on your page.

#### 7. Click the \`Toggle Light\` button and confirm that the light on your device changes and the text on your web app is consistent with the change.

### That's it for our first web-enabled IoT experiment 🎉.&#x20;

#### ★ If you are having any problems, no worry, post in our slack channel. Please share your code when it makes sense or create videos.

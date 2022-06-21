---
description: Getting Started with Programming the IoT Device
---

# Program for IoT Part 1 ⏱

## Introduction

{% embed url="https://www.loom.com/share/0fdf84f422274bb6827421523b66c483" %}

## Claiming Your IoT Device

This video steps you through claiming a particle device and setting up WIFI. You will want your mobile phone to complete this with the Particle App installed. \
Apple: [https://apps.apple.com/us/app/particle-iot/id991459054](https://apps.apple.com/us/app/particle-iot/id991459054)\
Android: [https://play.google.com/store/apps/details?id=io.particle.android.app\&hl=en\_US](https://play.google.com/store/apps/details?id=io.particle.android.app\&hl=en\_US)

{% embed url="https://www.youtube.com/watch?index=2&list=PLIeLC6NIW2tKvC5W007j_PU-dxONK_ZXR&v=xymSayKBGbg" %}

## IoT Tutorial - Programming the Device

We will use the Particle tutorial for the IoT kit linked below to guide us, but the videos will deviate a bit to demonstrate things using the web programming environment. Ultimately we want to get familiar with the hardware, inputs, sensors, and programming. ★ **Post questions and successes in our Slack channel as you move along.**

{% embed url="https://docs.particle.io/quickstart/isk-project/" %}

{% hint style="warning" %}
#### **Understanding LED Status Signals**

**This link comes in very handy for interpreting the different status LED signals you may get from time to time.** [**https://docs.particle.io/troubleshooting/led/argon/**](https://docs.particle.io/troubleshooting/led/argon/)****
{% endhint %}

### **Reading Temperature and Humidity**

We are covering concepts from the _**Particle Variables: measure temperature & humidity**_ section of the tutorial. _****_ [https://docs.particle.io/quickstart/isk-project/#particle-variables-measure-temperature-amp-humidity](https://docs.particle.io/quickstart/isk-project/#particle-variables-measure-temperature-amp-humidity)

{% embed url="https://www.loom.com/share/34d091fc693f443096531d8b050f9b25" %}

#### 1. Create a new program in Particle build.

#### 2. Connect the temperature and humidity sensor to D2, and have your Argon device connected.

![](<../../.gitbook/assets/image (6).png>)

#### 3. Include the "**GROVE\_TEMPERATURE\_AND\_HUMIDITY\_SENSOR" library in your program.**

#### 4. Copy and paste the code below (except of the #include part) into your program.

```arduino
// This #include statement was automatically added by the Particle IDE.
#include <Grove_Temperature_And_Humidity_Sensor.h>

DHT dht(D2);

double temp_dbl, humidity_dbl;

void setup() {
    Serial.begin(9600);

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
```

**5. Save, Verify, and Flash the code to the Argon board.**

**6. Open the Console from particle build, select "my devices", and select your Argon.**

**7. Get the temp and humidity variables to check if all is working.**

![](<../../.gitbook/assets/image (9).png>)

#### That's it for this step 🎉. If you are having any problems, no worry, post in our slack channel. Please share your code when it makes sense or create videos.

### Controlling an LED

We are covering concepts from the _**Particle Functions: controlling a Chainable LED**_ section of the tutorial. [https://docs.particle.io/quickstart/isk-project/#particle-functions-controlling-a-chainable-led](https://docs.particle.io/quickstart/isk-project/#particle-functions-controlling-a-chainable-led)

{% embed url="https://www.loom.com/share/e4a768da42d64a3f8a894f8be689437b" %}

Instructions coming soon...

#### 1. Create a new program in Particle build.

#### 2. Connect the Grove Chainable LED to A4, and have your Argon device connected.

![](<../../.gitbook/assets/image (10).png>)![](<../../.gitbook/assets/image (11).png>)

#### 3. Include the "Grove\_ChainableLED**" library in your program.**

#### 4. Copy and paste the code below (except of the #include part) into your program.

```arduino
// This #include statement was automatically added by the Particle IDE.
#include <Grove_ChainableLED.h>
ChainableLED leds(A4, A5, 1);

void setup() {
    leds.init();
    leds.setColorHSB(0, 0.0, 0.0, 0.0);
    Particle.function("toggleLed", toggleLed);
}

void loop() {
    // toggleLed("");
}

int toggleLed(String args) {
    leds.setColorHSB(0, 0.0, 1.0, 0.5);
    delay(500);
    leds.setColorHSB(0, 0.0, 0.0, 0.0);
    delay(500);
    return 1;
}    
```

**5. Save, Verify, and Flash the code to the Argon board.**

#### **6. Open the Console from particle build, select "my devices", and select your Argon.**

#### **7. Call the** toggleLed function to pulse the LED one time.

![](<../../.gitbook/assets/image (4).png>)

#### That's it for this step 🎉. If you are having any problems, no worry, post in our slack channel. Please share your code when it makes sense or create videos.

### Reference Material for the IoT Kit Hardware

[https://docs.particle.io/quickstart/isk-project/#appendix-grove-sensor-resources](https://docs.particle.io/quickstart/isk-project/#appendix-grove-sensor-resources)

{% embed url="https://docs.particle.io/quickstart/isk-project/#appendix-grove-sensor-resources" %}

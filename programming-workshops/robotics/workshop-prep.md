# Workshop Prep

## Background and Recommended Classroom Approach

{% embed url="https://www.loom.com/share/2c8a04779c174065b6204dfa1682b2b6" %}
✻ NOTE: For those participating in multiple programming workshops, this video is used in all programming workshop sequences. So, if it looks familiar, you may have already seen this.&#x20;
{% endembed %}

### Background on Computing by Design Framework

**This workshop is focused squarely on the programming component of a CxD Project.** For a little bit of background, you will find that the Computing by Design framework is project-centric in the approach.&#x20;

![](<../../.gitbook/assets/image (4) (1).png>)

Each project has three phases, where programming is a very important component of all three. **Our** [**Innovation Workshop**](broken-reference) **covers the breadth of the Computing by Design framework.** We have found that the programming in any project presents a fine line between a wonderfully empowering experience (when students struggle and get things working) and a sometimes frustrating experience that becomes a missed opportunity. Therefore we are offering these programming workshops to provide a solid foundation on building the applications.

![](<../../.gitbook/assets/image (5) (1).png>)

### Learning to Program: A Two-Pronged Approach

**We encourage you to offer students a two-pronged approach to learning to program.** Computing by Design projects provide an _**"application first"**_ approach to programming where students are provided direct guidance on creating a specific type of application through templates and tutorials -- like with trivia , a chatbot, IoT etc. This approach complements the many great tutorials available online that provide a _**"concept first"**_ approach by stepping through concepts in programming. Facilitating both approaches for students provides a varied experience -- strengthening knowledge and offering more opportunities to ignite interests.&#x20;

{% hint style="success" %}
**Identify an online tutorial site that you can use in your classroom to supplement any project work.** Over the course of the workshop try out a few basic online programming tutorials from popular sites to facilitate this _"concept first"_ approach, and consider how you might manage a self-paced assignment based on milestones.  How might you use these self-guided tutorials as "filler time" or dedicate scheduled time to their completion?
{% endhint %}

## Getting Started with Slack

{% embed url="https://www.loom.com/share/351f4100d55045a0a04b3ec078ffaa39" %}

Slack will be our primary communication platform for the workshop. The video above provides a brief introduction on the features of Slack, but more help and tutorials can be found at [https://slack.com/help](https://slack.com/help).

## Getting Started with Arduino Create Editor

{% embed url="https://www.loom.com/share/32e19fbe94fe4d3387032c3420cb4adc" %}

Our robot will be programmed using the [Arduino](https://www.arduino.cc/) programming language. We recommend using the **Arduino Create** web-based programming environment through the browser. There is an option to download a native application as well. This is just a quick intro. We will cover much more later in the workshop.

#### 👉 Use [these instructions](https://docs.idew.org/code-robotics/references/arduino-code-editor#arduino-create-web-editor) to setup your Arduino account for the web editor.

{% code title="Sample Code Used in Video Demo" %}
```cpp
int LED = 13;

void setup() {
  pinMode(LED, OUTPUT);
}

void loop() {
  digitalWrite(LED, HIGH);
  delay(500);
  digitalWrite(LED, LOW);
  delay(500);
}
```
{% endcode %}

# Journal Information
Hi, my name is Andrew and welcome to my project journal! I will be documenting my entire journey right here. 

## Engineering Design Process
Throughout this project, I will be using the engineering design process to iterate on my designs. 

1. Identify the problem
2. Brainstorm Solutions
3. Implement The Best One
4. Build The Model
5. Test For Problems

# Journal Entries
## June 12th, 2026 - Friday
So, for the past year, I've wanted to smartify my house, but most products seemed overpriced and didn't fit my needs. I also didn't have an excuse to spend that much money on smart home products. Well, I realized I was getting to places late because my parents would forget whether or not they'd closed the garage door, and we'd have to go back home when we were already a mile away.

After some research, I've found that all the solutions didn't quite fit my constraints. The simplest solution I found was using myQ. My current garage door even has myQ built in. Now, don't get me wrong, myQ seems very simple to set up, except for the fact that they stopped supporting smart ecosystem software like Home Assistant and HomeKit. From that problem, RATDGO and Open Garage were born. They both essentially hack the garage door opener into letting Home Assistant use it. They're almost perfect, except it's kind of expensive to buy them. 

Now for my idea. I want to make a cheaper version that has all the features I need.

Here's what I want:

- Ability to open and close from my phone
- Ability to see if the door is open or closed

I know that doesn't seem like a lot of features, but we can always add more in v2.

Well the first feature I want to have is seeing if it's open or not. For this, I think we should take some inspiration from security systems. To secure the garage door, companies usually use a reed switch. A reed switch is a switch that switches when a magnet is near. My dad actually has a spare one, so I'll just use that one. 

![image](/assets/reed_switch_1.png)

Before I continue, I want to test the reed switch first. I hooked up an LED to my power supply and put the reed switch in the middle. When the magnet got close, the LED turned on. When I removed the magnet, the L:ED turned off

|Magnet Near|Magnet Away|
|-----------|-----------|
|![image](/assets/reed_switch_3.png)|![image](/assets/reed_switch_2.png)|

Since we now have the first feature covered, lets move on to the next: remote control. At first, I wanted to place the esp32 right next to the wall mounted button and have a servo press the button, but that is not only too far but also would be an eyesore. For this reason, I decided to use the remotes that you place in your car. 

I wanted to break one open to see how it worked. I pried it open with a flathead screwdriver. 

![image](/assets/remote_1.png)

Overall, it seems pretty simple. The remote is powered by 3V CR2032 battery. An IC then detects if the button shorts it to ground, then sends out an encrypted signal. Since I don't want to try and hack the encryption system, I'll just short the pins with a transistor. 

![image](/assets/remote_2.png)

Now, I want to wire and code a test for the remote. I'll tell the remote short the IC to ground for around 200ms through serial. If everything goes to plan, it should open my garage door. Also, it will tell me if the garage is closed or open according to if the sensor senses the magnet

To start, I soldered some jumpers to the remote

![image](/assets/remote_3.png)

I then wired it up to the breadboard with the esp32. I tested if the 3.3v pin from the ESP32 was enough to power it by clicking the button. It opened my garage door so it's a success.

![image](/assets/test_wiring_1.png)

Next, let's write the code! This will be my first time configuring ESPHome so bear with me. 

I started off by flashing ESPHome onto my ESP32 board, and the auto config took like 30 minutes. After it was done, I looked at the [docs](https://esphome.io/guides/getting_started_hassio/) to see what to do next. 

The tutorial taught me how to program the ESP32 reed switch. It was fairly easy since it only required around 10 lines of code. 

Next, I'll program the ESP32 for the transistor circuit. 

At first, I tried programming the ESP32 with the button function, but using the switch function worked out much better. 

I thought my code was completely broken, but turns out I wired everything wrong, so I also rewired it. 

## June 13th, 2026 - Saturday
Since everything works now, I will move on to the enclosure. 

I want to mount it on top the garage door opener. Not only is there a power plug there, but the case won't be as much of an eyesore. 

My garage gets pretty hot in the summer, so I'll print it in PETG. 

My ESP32 board has 2.5mm mounting holes, but I don't own any 2.5mm bolts, so I decided to extrude pins that go through the middle of each hole to keep the ESP32 secure. 

![image](/assets/case_1.png)

I only printed this corner piece because I wanted to test out if the ESP32 would fit. 

After printing it, the shorter axis fit perfectly, but the longer axis was a bit too short so the pins bent when I pressed the ESP32 in. I decided to reprint it with 2mm of extra distance. 

![image](/assets/case_2.png)

Now the pins are too far apart, I will shrink the distance by 1mm and reprint. I hope it'll actually fit now. 

It worked perfectly! Let's move on to designing the rest of this case

![image](/assets/case_3.png)

After the base case was done, I began soldering everything

![image](/assets/finished_wiring_1.jpg)



![image](/assets/finished_project_1.jpg)
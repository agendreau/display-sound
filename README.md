# Sound Sensor Data Display

## Introduction
When you press ``||input: button A||``, turn on ``||Neopixel: blue lights||`` ``||logic: if||`` the ``||gatorMicrophone: sound||`` is ``||logic: less||`` than 750  and ``||Neopixel: orange lights||`` if the ``||gatorMicrophone: sound||`` is ``||logic: more than||`` 750. Things to think about. Which pin controls the Lights on the gator:bit? How mand LEDs are on the gator:bit? Draw a picture to help think about the logic.

## Step 1
``||basic: Initialize||`` the LEDs to that ``||variables: strip||`` can control them.

```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
```

## Step 2 
Code your micro:bit to take a sound reading when ``||input: button A||`` is pressed. Set the ``||neopixel: brightness||`` of the strip to 50, so the lights are not extremely bright.

```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
input.onButtonPressed(Button.A, function () {
    strip.setBrightness(50)
})
```

## Step 3
Now code your micro:bit to display ``||Neopixel: blue lights||`` when  ``||gatorSound: sound intensity||`` 
is ``||logic: less than||`` 750.

```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)
input.onButtonPressed(Button.A, function () {
        strip.setBrightness(50)
        if (gatorMicrophone.getSoundIntensity() < 750) {
            strip.showColor(neopixel.colors(NeoPixelColors.Blue))
        } else {
            strip.showColor(neopixel.colors(NeoPixelColors.Orange))
        }
})
```

## Step 4
Now code your micro:bit to display ``||Neopixel: orange lights||`` when  ``||gatorSound: sound intensity||`` 
is ``||logic: greater than||`` 750 decibles.  


```blocks
let strip = neopixel.create(DigitalPin.P12, 5, NeoPixelMode.RGB)

input.onButtonPressed(Button.A, function () {
        strip.setBrightness(50)
        if (gatorMicrophone.getSoundIntensity() < 750) {
            strip.showColor(neopixel.colors(NeoPixelColors.Blue))
        } else {
            strip.showColor(neopixel.colors(NeoPixelColors.Orange))
        }
})
```
## Step 5
``|Download your code|`` and try it out

## Step 6
Modify the program so that when you press ``||input: button B||``, 
if the ``||gatorSound: sound||`` is less than 400, 
the gator:bit ``||music: plays a song||``. 

```blocks
input.onButtonPressed(Button.B, function () {
    if (gatorMicrophone.getSoundIntensity() <400) {
        music.beginMelody(music.builtInMelody(Melodies.Ode), MelodyOptions.Once)
    }
})
```

## Step 7
``|Download|`` your code and try it out

## Step 8
Modify either the lights or music to ``||Loops: repeat||`` 5 times

```blocks
input.onButtonPressed(Button.A, function () {
    input.onButtonPressed(Button.A, function () {
    for (let i = 0; i < 5; i++) {
        strip.setBrightness(50)
        if (gatorMicrophone.getSoundIntensity() < 750) {
            strip.showColor(neopixel.colors(NeoPixelColors.Blue))
        } else {
            strip.showColor(neopixel.colors(NeoPixelColors.Orange))
        }
    }
})
})
```

## Step 9
``||basic: wait||`` 10 seconds in between each time the sensor takes a reading
```blocks
input.onButtonPressed(Button.A, function () {
    for (let i = 0; i < 5; i++) {
        strip.setBrightness(50)
        if (gatorMicrophone.getSoundIntensity() < 750) {
            strip.showColor(neopixel.colors(NeoPixelColors.Blue))
        } else {
            strip.showColor(neopixel.colors(NeoPixelColors.Orange))
        }
        basic.pause(10000)
    }
})
})
```
## Step 10
``|Download|`` the code and try it out.


```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone
neopixel=github:microsoft/pxt-neopixel
```





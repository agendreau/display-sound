# Sound Sensor Data Display

## Introduction
When you press ``||input: button A||``, ``||logic: if||`` the ``||gatorMicrophone: sound||`` is ``||logic: less||`` than 750 then show a smiley face ``||logic: else||`` show an X if the ``||gatorMicrophone: sound||`` is ``||logic: more than||`` 750. Things to think about. Draw a picture to help think about what you want to happen. When you're ready click the NEXT button to get started.

## Step 2 
Use ``||input: button A||`` to ``||basic: show||`` the ``||gatorSound: sound intensity||``

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorMicrophone.getSoundIntensity())
})
```

## Step 3
Now code your micro:bit to display ``||basic: a smiley face||`` ``||logic: if||`` the  ``||gatorSound: sound intensity||`` 
is ``||logic: less than||`` 750.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorMicrophone.getSoundIntensity())
    if (gatorMicrophone.getSoundIntensity() < 750) {
        basic.showLeds(`
            . . . . .
            . # . # .
            . . . . .
            # . . . #
            . # # # .
            `)
    }
})
```

## Step 4
Now code your micro:bit to display ``||basic: X||`` if the  ``||gatorSound: sound intensity||`` 
is ``||logic: greater than||`` 750. 


```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(gatorMicrophone.getSoundIntensity())
    if (gatorMicrophone.getSoundIntensity() < 750) {
        basic.showLeds(`
            . . . . .
            . # . # .
            . . . . .
            # . . . #
            . # # # .
            `)
    } else {
        basic.showIcon(IconNames.No)
    }
})

```
## Step 5
``|Download your code|`` and try it out

## Step 6
Modify the program so that when you press ``||input: button B||``, ``||logic: if||`` the ``||gatorSound: sound||`` is ``||logic: less than||`` 400, the gator:bit ``||music: plays a song||``. 

```blocks
input.onButtonPressed(Button.B, function () {
    if (gatorMicrophone.getSoundIntensity() <400) {
        music.beginMelody(music.builtInMelody(Melodies.Ode), MelodyOptions.Once)
        basic.showString("Music")
    }
})
```

## Step 7
``|Download|`` your code and try it out

## Step 8
Modify either the lights or music to ``||Loops: repeat||`` 5 times

```blocks
input.onButtonPressed(Button.A, function () {
    for (let i = 0; i < 5; i++) {
        basic.showNumber(gatorMicrophone.getSoundIntensity())
        if (gatorMicrophone.getSoundIntensity() < 750) {
            basic.showLeds(`
                . . . . .
                . # . # .
                . . . . .
                # . . . #
                . # # # .
                `)
        } else {
            basic.showIcon(IconNames.No)
        }
    }
}) }
})
```

## Step 9
``||basic: wait||`` 10 seconds in between each time the sensor takes a reading
```blocks
input.onButtonPressed(Button.A, function () {
    for (let i = 0; i < 5; i++) {
        basic.showNumber(gatorMicrophone.getSoundIntensity())
        if (gatorMicrophone.getSoundIntensity() < 750) {
            basic.showLeds(`
                . . . . .
                . # . # .
                . . . . .
                # . . . #
                . # # # .
                `)
        } else {
            basic.showIcon(IconNames.No)
        }
        basic.pause(10000)
    }
})
```
## Step 10
``|Download|`` the code and try it out.


```package
gatorMicrophone=github:sparkfun/pxt-gator-microphone
neopixel=github:microsoft/pxt-neopixel
```





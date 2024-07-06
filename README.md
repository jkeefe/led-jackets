# led-jackets
Pretty, paired jackets using WLED

## Parts list

- Controller: [QuinLED-ESP32 AE](https://www.drzzs.com/shop/quinled-esp32/?attribute_pa_hardwareplatform=external-antenna) (External Antenna)
- [Flexi antenna](https://www.digikey.com/en/products/detail/molex/1461531200/8543421)
- [Microphone Module I2S Interface INMP441](https://www.amazon.com/dp/B09X3216DN?ref=ppx_yo2ov_dt_b_product_details&th=1)
- [USB-C Breakout Board](https://www.adafruit.com/product/4090) ... so I can still use USB, but route 5v out to the LEDs, too.
- Adafruit Altoids tin [perma-proto breadboard](https://www.adafruit.com/product/723)
- [LED strand](https://www.adafruit.com/product/4917)
- [Membrane buttons](https://www.adafruit.com/product/1332) • [Pinouts](https://learn.adafruit.com/matrix-keypad/pinouts)

## The controller

I needed to switch to an ESP32 board because the ESP32-C3 isn't powerful enough to do the audio tricks.. This one was on the list of [recommended boards](https://kno.wled.ge/basics/compatible-controllers/#raw-esp8266esp32-boards) for WLED.

- [General info](https://quinled.info/quinled-esp32-specifications/)
- [Pinout](https://quinled.info/quinled-esp32-board-details/):
![Screen Shot 2024-07-05 at 8 18 40 PM](https://github.com/jkeefe/led-jackets/assets/312347/c31ae058-a099-4c96-87fe-31a936e46aca)
  

## Interface

Buttons:

**1: Fun lights**
- short press: next
- long press: cycle randomly every 2 minutes

**2: Music lights**
- short press: next
- long press: cycle randomly every 6 minutes

**2: Brighter**
- short press: up
- long press: max

**4: Darker**
- short press: down
- long press: off
  
Button pinouts:

![image](https://github.com/jkeefe/led-jackets/assets/312347/ffce5416-ed5d-4570-93db-e34108d5183b)

[Wiring](https://kno.wled.ge/features/macros/) the buttons.


## WLED





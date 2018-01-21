# Blinkytape (SK6812) FastLED with RGBW
Hack to enable SK6812 RGBW strips to work with FastLED.

 Anyone who has used The [BlinkyTape](http://blinkinlabs.com/blinkytape/) from 
[BlinkinLabs](http://blinkinlabs.com/) knows that it is essentially a ATMega32u4 controller ideally compatiple with the  WS2812B LEDs and SK6812 LEDs.  By default the library taht Blinkytape uses [FAST LED](https://github.com/FastLED/FastLED/releases) does not support RGBW color space, until now.  This is a hack originaly coded by Jim Bumgardner ((http://krazydad.com))(http://krazydad.com).

This works by exploiting the fact that WS2812B LEDs and SK6812 LEDs have similar data timing. It’s not identical, but it’s close enough to make this work. The trick is to tell FastLED that we’re writing to a WS2812B strip, but insert an extra ‘white’ byte between each RGB group.

I simply wrote the functionality to Blinkytape's 'ColorSwirl' example in Ardunio.  I also included a HSV rainbow loop to play with.  

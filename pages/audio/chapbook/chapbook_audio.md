# "Audio": Chapbook (v1.0.0)

!!! Information
    This examples uses two additional files, [testpattern.ogg](testpattern.ogg) and [testpattern.wav](testpattern.wav). Both files need to be downloaded and placed in the same folder as the HTML file in order to work as designed.

## Summary

Chapbook supports both [looping sounds](https://klembot.github.io/chapbook/guide/multimedia/audio.html) (which it calls ambient) and one-off sound (which it calls effects). It only allows playing one sound at a time.

## Example

[Download](chapbook_audio_example.html)

## Twee Code

```twee
:: Start
sound.ambient.test.url: 'testpattern.ogg'
sound.ambient.test.description: 'An audio test pattern'
--

> [[Play sound]]
> [[Stop the sound]]

:: Play sound
{ambient sound: 'test'}

[[Return->Start]]

:: Stop the sound
sound.ambient.test.playing: false
--

[[Return->Start]]
```

[Twee Download](chapbook_audio_twee.txt)

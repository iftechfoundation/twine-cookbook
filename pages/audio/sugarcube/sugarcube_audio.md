# "Audio": SugarCube (v2.18)

!!! Information
    This examples uses two additional files, [testpattern.ogg](testpattern.ogg) and [testpattern.wav](testpattern.wav). Both files need to be downloaded and placed in the same folder as the HTML file in order to work as designed.

## Summary

SugarCube supports audio through multiple macros. For basic playing of audio, resources must be first cached through the [`<<cacheaudio>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-cacheaudio) macro and then can be referenced in others like the [`<<audio>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-audio) macro for playing and stopping.

Audio elements rely on sources either absolutely or relatively located. An absolute reference starts with HTTP or another protocol; a relative reference describes the location of the resource in relation to the webpage. Because audio files are external resources, they must also be accessed from a remote service, file hosting location, or stored separately with the webpage.

Due to browser differences in licensing, some audio formats are not universally supported. For best results in using audio in Twine, it is recommended to use multiple formats, allowing the browser to choose which format is best supported when first loaded.

## Example

[Download](sugarcube_audio_example.html)

## Twee Code

```twee
:: StoryTitle
Audio in SugarCube

:: Start
<<link "Start audio!">>
  <<audio "testpattern" play>>
<</link>>

<<link "Stop audio!">>
  <<audio "testpattern" stop>>
<</link>>

:: StoryInit
<<cacheaudio "testpattern" "testpattern.ogg" "testpattern.wav">>
```

[Twee Download](sugarcube_audio_twee.txt)

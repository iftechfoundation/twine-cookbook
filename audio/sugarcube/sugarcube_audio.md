# "Audio": SugarCube (v2.18)

## Summary

SugarCube supports audio through multiple macros. For basic playing of audio, resources must be first cached through the [&lt;&lt;cacheaudio&gt;&gt;](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-cacheaudio) macro and then can be referenced in others like the [&lt;&lt;audio&gt;&gt;](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-audio) macro for playing and stopping.

Audio elements rely on sources either absolutely or relatively located. An absolute reference starts with HTTP or another protocol; a relative reference describes the location of the resource in relation to the webpage. Because audio files are external resources, they must also be accessed from a remote service, file hosting location, or stored separately with the webpage.

Due to browser differences in licensing, some audio formats are not universally supported. For best results in using audio in Twine, it is recommended to use multiple formats, allowing the browser to choose which format is best supported when first loaded.

<div class="alertbox information"><strong>Note:</strong> This examples uses two additional files, <a href="testpattern.ogg">testpattern.ogg</a> and <a href="testpattern.wav">testpattern.wav</a>. Both files need to be downloaded and placed in the same folder as the HTML file in order to work as designed.</div>

## Live Example

<section>
<iframe src="sugarcube_audio_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_audio_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Audio in SugarCube

:: Start
<<cacheaudio "testpattern" "testpattern.ogg" "testpattern.wav">>

<<link "Start audio!">>
	<<audio "testpattern" play>>
<</link>>

<<link "Stop audio!">>
	<<audio "testpattern" stop>>
<</link>>
```

Download: <a href="sugarcube_audio_twee.txt" target="_blank">Twee Code</a>


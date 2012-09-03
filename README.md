love-pd-audio
=============

audio module for love2d (win.dll/linux.so) using puredata for interactive manipulation/generation<br>
(not functional yet, just started experimenting)

2012-09 ghoulsblade@schattenkind.net

* http://love2d.org
* http://puredata.info
* https://github.com/libpd/libpd

see above for licensing details since code from there was used, they all use BSD/MIT style or similar, so even binary distribution should be ok, as long as the copyright notices are included.

NOTES
-----

Interfacing directly into the love audio via sounddata in love 0.8.0 will not work properly due to lack of buffering/streaming api for runtime-generated audio-data.<br>
Instead the love2d code for openal audio source with streaming will be used as basis, and a new openal-instance will be opened by the module, independent from l�ve, to avoid needing a modified love2d binary.<br>

PureData files should make it possible to play midi files using sampled instruments, do realtime audio-generation and modification with configurable effect pipes like reverb etc, <br>
as well as all do advanced audio feedback like modifying music dynamically based on game happenings, and using the current point in the music to customize sound effects to fit in better.<br>

Even without using the PureData part it will probably make sense to expose an api for buffered/streamed realtime data that can be generated by lua.<br>

Porting to webplayer might be possible on firefox and maybe also chrome using the raw audio api extension, but that's low prio for now, and won't work for standard html5 audio. 
* https://wiki.mozilla.org/Audio_Data_API 
* http://chromium.googlecode.com/svn/trunk/samples/audio/index.html

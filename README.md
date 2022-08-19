# Incredibox-IOS
An Incredibox's IOS Progressive Web App made from a source code hacked from the Incredibox Android version. It supports `IOS`. 

You can run it on apache, nginx and any other web server. 

Except for the audio assets, the IOS version looks similar to the PC version and the Android version. 

All the differences seem to be just `js/main.min.js`, `js/index.min.js` and all audio assets. 

# Why we can't use the [Incredibox](https://github.com/DarkReaper231/Incredibox) on Safari for IOS? 
Because Safari for IOS doesn't support to decord `.ogg` files. In Incredibox Android version, the audios files are `.ogg`. Safari won't play it normally. 

## But why it work on `Wiktionary.org`? 
`Wiktionary.org` actually load the `.ogg` files along with these two scripts: 
~~~
ogv-worker-audio.js
ogv-decoder-audio-vorbis.js
~~~
The scripts are part of the [`ogv.js`](https://github.com/brion/ogv.js/) JavaScript library. It use `JavaScript` to decord the `.ogg` files. So we can play it on `wiktionary.org`. You can read more on [there](https://stackoverflow.com/questions/38581887/safari-doesnt-play-ogg-files-so-how-does-it-work-on-wiktionary-org). 

I didn't learn to use it in the source code, so I changed the audio assets type to `.mp3` by the [`FFmpeg`](https://github.com/FFmpeg/FFmpeg) and these in `js/main.min.js` and `js/index.min.js`. 
~~~js
target = "mobile",
sndtype = "mp3",
osname = "ios",
appTotalVersion = appCN && "ios" == osname ? 4 : 8,
~~~
Safari supports `.mp3`, so you can play Incredibox on Safari and IOS PWA by it. 

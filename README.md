# gstmic

_Play audio from local microphone with GStreamer without network streaming_


## 1 Description

TODO


## 2 Usage

TODO


## 3 Alternatives

The following application provide alternatives to gstmic but might have more
requirements or dependencies for installation. The directory test has scripts
to start these alternatives.


### 3.1 ALSA command-line PCM loopback (alsaloop)

[ALSA](https://alsa-project.org/wiki/Main_Page) command-line PCM loopback can
be run with:

    alsaloop
    alsaloop -Cdefault -Pdefault
    alsaloop -Cdefault:CARD=sndrpihifiberry -Pdefault:CARD=sndrpihifiberry
    alsaloop -c2 -fS32_LE -t200000


## 4 Inspection

The following command can be used to list which playback devices are available:

    aplay -L -l

Playback can be tested with:

    speaker-test
    speaker-test -Ddefault
    speaker-test -Ddefault:CARD=sndrpihifiberry
    speaker-test -c2

The following command can be used to list which capture devices are available:

    arecord -L -l

Capture can be tested with:

    arecord -d5 -Vmono /tmp/tst-none.wav
    arecord -d5 -Ddefault /tmp/tst-default.wav
    arecord -d5 -Dpulse /tmp/tst-pulse.wav
    arecord -d5 -Ddefault:CARD=sndrpihifiberry /tmp/tst-srhb.wav
    arecord -d5 -c2 -fS16_LE -r48000 /tmp/tst-stereo.wav

and played back with:

    aplay -Ddefault /tmp/tst*.wav
    aplay -Ddefault:CARD=sndrpihifiberry /tmp/tst*.wav
    aplay -Vstereo /tmp/tst*.wav


## 5 Building

TODO


## 6 To do

TODO


## 7 License

For this application the MIT License applies, see also the file
[LICENSE](LICENSE). The author of this software is
[Stichting z25.org](http://z25.org).

[![Logo z25](images/logo-z25.png?raw=true)](http://z25.org)

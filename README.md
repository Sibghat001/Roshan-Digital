
### VLCPlayer Props

| Prop                | Description                                                                                                                                          | Default |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| `source`            | Object that contains the uri of a video or song to play eg `{{ uri: "https://video.com/example.mkv" }}`                                              | `{}`    |
| `subtitleUri`       | local subtitle file path，if you want to hide subtitle, you can set this to an empty subtitle file，current we don't support a `hide subtitle` prop. |         |
| `paused`            | Set to `true` or `false` to pause or play the media                                                                                                  | `false` |
| `repeat`            | Set to `true` or `false` to loop the media                                                                                                           | `false` |
| `rate`              | Set the playback rate of the player                                                                                                                  | `1`     |
| `seek`              | Set position to seek between `0` and `1` (`0` being the start, `1` being the end , use `position` from the progress object )                         |         |
| `volume`            | Set the volume of the player (`number`)                                                                                                              |         |
| `muted`             | Set to `true` or `false` to mute the player                                                                                                          | `false` |
| `audioTrack`        | Set audioTrack id (`number`) (see `onLoad` callback VideoInfo.audioTracks)                                                                           |         |
| `textTrack`         | Set textTrack(subtitle) id (`number`) (see `onLoad` callback- VideoInfo.textTracks)                                                                  |         |
| `playInBackground`  | Set to `true` or `false` to allow playing in the background                                                                                          | false   |
| `videoAspectRatio ` | Set the video aspect ratio eg `"16:9"`                                                                                                               |         |
| `autoAspectRatio`   | Set to `true` or `false` to enable auto aspect ratio                                                                                                 | false   |
| `resizeMode`        | Set the behavior for the video size (`fill, contain, cover, none, scale-down`)                                                                       | none    |
| `style`             | React native stylesheet styles                                                                                                                       | `{}`    |
| `autoplay`          | Set to `true` or `false` to enable autoplay                                                                                                          | `true`  |

#### Callback props

Callback props take a function that gets fired on various player events:

| Prop                 | Description                                                                                                                                                                                                          |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `onPlaying`          | Called when media starts playing returns eg `{target: 9, duration: 99750, seekable: true}`                                                                                                                           |
| `onProgress`         | Callback containing `position` as a fraction, and `duration`, `currentTime` and `remainingTime` in seconds <br />&nbsp; ◦ &nbsp;eg `{  duration: 99750, position: 0.30, currentTime: 30154, remainingTime: -69594 }` |
| `onPaused`           | Called when media is paused                                                                                                                                                                                          |
| `onStopped `         | Called when media is stoped                                                                                                                                                                                          |
| `onBuffering `       | Called when media is buffering                                                                                                                                                                                       |
| `onEnded`            | Called when media playing ends                                                                                                                                                                                       |
| `onError`            | Called when an error occurs whilst attempting to play media                                                                                                                                                          |
| `onLoad`             | Called when video info is loaded, Callback containing VideoInfo                                                                                                                                                      |
| `onRecordingCreated` | Called when a new recording is created as the result of `startRecording()` `stopRecording()`                                                                                                                         |
| `onSnapshot`         | Called when a new snapshot is created as the result of `snapshot()` - contains `{success: boolean, path?: string, error?: string}`                                                                                   |

#### Methods props

Methods available on the VLC player ref

| Prop                                | Description                                                                                                       |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| `startRecording(directory: string)` | Start recording the current video into the given directory                                                        |
| `stopRecording()`                   | Stop recording the current video. The final recording file can be obtained from the `onRecordingCreated` callback |
| `snapshot(path: string)`            | Capture a snapshot of the current video frame to the given file path                                              |

VideoInfo example:

```
 {
    duration: 30906,
    videoSize: {height: 240, width: 32},
    audioTracks: [
            {id: -1, name: "Disable"},
            {id: 1, name: "Track 1"},
            {id: 3, name: "Japanese Audio (2ch LC-AAC) - [Japanese]"}
    ],
    textTracks: [
        {id: -1, name: "Disable"},
        {id: 4, name: "Track 1 - [English]"},
        {id: 5, name: "Track 2 - [Japanese]"}
    ],
}
```

## More formats

Container formats: 3GP, ASF, AVI, DVR-MS, FLV, Matroska (MKV), MIDI, QuickTime File Format, MP4, Ogg, OGM, WAV, MPEG-2 (ES, PS, TS, PVA, MP3), AIFF, Raw audio, Raw DV, MXF, VOB, RM, Blu-ray, DVD-Video, VCD, SVCD, CD Audio, DVB, HEIF, AVIF
Audio coding formats: AAC, AC3, ALAC, AMR, DTS, DV Audio, XM, FLAC, It, MACE, MOD, Monkey's Audio, MP3, Opus, PLS, QCP, QDM2/QDMC, RealAudio, Speex, Screamtracker 3/S3M, TTA, Vorbis, WavPack, WMA (WMA 1/2, WMA 3 partially).
Capture devices: Video4Linux (on Linux), DirectShow (on Windows), Desktop (screencast), Digital TV (DVB-C, DVB-S, DVB-T, DVB-S2, DVB-T2, ATSC, Clear QAM)
Network protocols: FTP, HTTP, MMS, RSS/Atom, RTMP, RTP (unicast or multicast), RTSP, UDP, Sat-IP, Smooth Streaming
Network streaming formats: Apple HLS, Flash RTMP, MPEG-DASH, MPEG Transport Stream, RTP/RTSP ISMA/3GPP PSS, Windows Media MMS
Subtitles: Advanced SubStation Alpha, Closed Captions, DVB, DVD-Video, MPEG-4 Timed Text, MPL2, OGM, SubStation Alpha, SubRip, SVCD, Teletext, Text file, VobSub, WebVTT, TTML
Video coding formats: Cinepak, Dirac, DV, H.263, H.264/MPEG-4 AVC, H.265/MPEG HEVC, AV1, HuffYUV, Indeo 3, MJPEG, MPEG-1, MPEG-2, MPEG-4 Part 2, RealVideo 3&4, Sorenson, Theora, VC-1,[h] VP5, VP6, VP8, VP9, DNxHD, ProRes and some WMV.

## Got a few minutes to spare? Please help us to keep this repo up to date and simple to use.

#### Our idea was to keep the repo simple, and people can use it with newer RN versions without any additional config.

1. Get a fork of this repo and clone [VLC Media Player test](https://github.com/razorRun/react-native-vlc-media-player-test)
2. Run it for ios and android locally using your fork, and do the changes. (remove this package using `npm remove react-native-vlc-media-player` and install the forked version from git hub `npm i https://git-address-to-your-forked-repo`)
3. Verify your changes and make sure everything works on both platforms. (If you need a hand with testing I might be able to help as well)
4. Send PR.
5. Be happy, Cause you're a Rockstar 🌟 ❤️

## Known Issues

### iOS 17 Simulator Crash

It is a [known issue](https://code.videolan.org/videolan/VLCKit/-/issues/724) that apps can crash on playback in iOS simulator with `EXEC_BAD_ACCESS` errors. This appears to only be on certain iOS 17.x versions (17.4, 17.5).
If this happens, try running on an iOS 18+ simulator instead.

## TODO

1. Android video aspect ratio and other params do not work (Events are called but all events come through a single event onVideoStateChange but the JS side does not implement it)



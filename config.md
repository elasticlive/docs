# Config

## Overview

RemoteMonster receives the config value prior to creating an object.

## Basics

It is essential to designate View, Service Id and Key to be displayed.

### View

This setting configures Video for displaying the video and Audio for setting off sound.

```markup
<video id="remoteVideo" autoplay controls playsinline></video>
<video id="localVideo" autoplay controls playsinline muted></video>
<audio id="remoteAudio" autoplay controls>
<audio id="localAudio" autoplay controls muted>
<script>
  const config = {
    view: {
      video: {
        remote: '#remoteVideo', local: '#localVideo'
      },
      audio: {
        remote: '#remoteAudio', local: '#localAudio'
      }
    }
  }
</script>
```

### Service Id, Key

This essential step sets up Service Id and Key. You can view Id and Key from console.

```javascript
const config = {
  credential: {
    serviceId: 'myServiceId', key: 'myKey'
  }
}
```

{% embed url="https://console.elasticlive.io/" %}

## Media

More diverse options are offered regarding sound and video. They have the same specifications as constraints of WebRTC.

{% embed url="https://developer.mozilla.org/en-US/docs/Web/API/Media\_Streams\_API/Constraints" %}

### Select Video, Audio

By turning on and off a video, you can create video broadcast/call or sound broadcast/call contents.

```javascript
// Audio Only
const config = {
  media: {
    audio: true,
    video: false
  }
}

// Audio, Video
const config = {
  media: {
    audio: true,
    video: true
  }
}
```

## Debug

You can configure SILENT, ERROR, WARN, INFO, DEBUG and VERBOSE, and you can view more detailed logs toward the end.

```javascript
const config = {
  sdk:{
    logLevel: 'INFO'
  }
}
```




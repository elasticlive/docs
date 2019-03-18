# Getting Started

## Preparations

* Web browser and frontend development environment
* Modern browser supporting WebRTC

## Creating and Configuring Project

elasticlive runs in a browser environment. What you need to do is simply preparing to develop a general web frontend.

```bash
npm init
npm i http-server
touch index.html
npx http-server
# Open browser "localhost:8081"
```

## Installing SDK - npm  <a id="installing_sdk_npm"></a>

You can easily install by using npm.

```bash
npm i @elasticlive/sdk
npm i webrtc-adapter      #Optional lib for lagacy WebRTC API support
```

```javascript
import ELive from '@elasticlive/sdk'
```

{% code-tabs %}
{% code-tabs-item title="index.html" %}
```markup
<!-- Optional lib for lagacy WebRTC API support -->
<script src="node_modules/webrtc-adapter/out/adapter.js"></script>

<script src="node_modules/@elasticlive/sdk/dist/ELive.min.js"></script>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Installing SDK - Static Import  <a id="installing_sdk_static"></a>

You can use [jsDelivr CDN](https://www.jsdelivr.com). Please insert in the HTML file as follows.

{% code-tabs %}
{% code-tabs-item title="index.html" %}
```markup
<!-- Optional lib for lagacy WebRTC API support -->
<script src="https://cdn.jsdelivr.net/npm/webrtc-adapter/out/adapter.js"></script>

<!-- Latest -->
<script src="https://cdn.jsdelivr.net/npm/@elasticlive/sdk"></script>

<!-- Specific version -->
<script src="https://cdn.jsdelivr.net/npm/@elasticlive/sdk@3.0.0/dist/ELive.min.js"></script>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Developing

The actual running code is provided as follows. Check it out now.

{% embed url="https://codesandbox.io/s/l7k87490n9" caption="" %}

### Service Key

You need Service Id and Key. You may skip this step to simply test and demonstrate. In order to actually develop and run services, issue and apply Service Id and Key by referring to the Credential of the console.

{% embed url="https://console.elasticlive.io/" caption="" %}

### 1:N

#### Broadcasting

```javascript
<video id="localVideo" autoplay muted></video>
<script>
const config = {
  view: {
    local: '#localVideo'
  }
}

const live = new ELive({ config })
live.cast('myBroadCast')
</script>
```

#### Watching

```javascript
<video id="remoteVideo" autoplay></video>
<script>
const config = {
  view: {
    remote: '#remoteVideo'
  }
}

const live = new ELive({ config })
live.watch('myBroadCast')
</script>
```

### 1:1

```javascript
<video id="localVideo" autoplay muted></video>
<video id="remoteVideo" autoplay></video>
<script>
const config = {
  view: {
    local: '#localVideo',
    remote: '#remoteVideo'
  }
}

const live = new ELive({ config })
live.call('myCall')
</script>
```

### Methods

#### close\(\)

Disconnect the return resources.

```javascript
live.close()
```

#### search\(\)

Import the list of current broadcast and communication.

```javascript
live.search()
```

#### switchCamera\(\)

Change over the camera.

```javascript
live.switchCamera()
```

#### captureScreen\(\)

Capture the screen.

```javascript
live.captureScreen()
```

#### sendMessage\(\)

Send a message to another user.

```javascript
live.sendMessage()
```


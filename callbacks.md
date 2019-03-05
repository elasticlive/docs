# Callbacks

### Init

Initialization is complete through `new ELive()`.

```javascript
live.on('init', () => console.log('init'))
```

### onComplete

Successfully connected via `cast()`, `watch()`, and `call()`.

```javascript
live.on('init', id => console.log('complete', id))
```

### onLocalMedia

User’s media have been imported.

```javascript
live.on('init', stream => console.log('onLocalMedia', stream))
```

### onSearch

Current broadcasting/communication list or id of designated broadcast/communication has been imported via `search()`.

```javascript
live.on('init', ids => console.log('onSearch', ids))
```

### onMessage

The sender has sent a message via `sendMessage()`, and you successfully received the message.

```javascript
live.on('init', msg => console.log('onMessage', msg))
```

### onError

An error occurred.

```javascript
live.on('onError', e => console.log('onError', e))
```


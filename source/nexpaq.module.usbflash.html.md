---
title: nexpaq.module.usbflash Driver

language_tabs:
  - javascript

toc_footers:
  - <a href='https://moduware.github.io/developer-documentation/module-drivers/'>Drivers list</a>

search: true
---

# Driver: nexpaq.module.usbflash

**Type**: nexpaq.module.usbflash

**Version**: 1.0.2
# Commands 

## Checks the status of USB flash module

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'StatusCheck', []);
```

Command Name | Message Type
-------------- | --------------
StatusCheck | 2702

To work with USB flash module and read data, USB flash module must be plugged in.

## Connects to the USB flash

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'Connect', []);
```

Command Name | Message Type
-------------- | --------------
Connect | 2700

Connects to the USB flash that is plugged in.

## Disconnects from the USB flash

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'Disconnect', []);
```

Command Name | Message Type
-------------- | --------------
Disconnect | 2700

Disconnects from USB flash that is plugged in.
# Data 

<aside class="warning">If you want to work with received data you need to listen for <code>DataReceived</code> event after Api is ready</aside>
> When Moduware API is ready start listening for received data

```javascript
document.addEventListener('WebViewApiReady', function() {
  Moduware.v0.API.Module.addEventListener('DataReceived', function(event) {
    // we don't care about data not related to our module
    if(event.moduleUuid != Moduware.Arguments.uuid) return;

    // ... handle specific received data here ...

  });
});
```
  

## State Change Reponse

```javascript
if(event.dataSource == 'StateChangeResponse') {
  // ... work with data variables here ...
}
```

Data Name | Message Type
-------------- | --------------
StateChangeResponse | 2701

Response to state change command
### Variables 

```javascript  
switch(event.variables.result) {
  case 'success':
  // ... handle the state here ...
  break;
  case 'failure':
  // ... handle the state here ...
  break;
}
```

Name | Title | Description | States
-------------- | -------------- | -------------- | --------------
result | Result | Result of connect or disconnect request | success / failure

## Status Request Reponse

```javascript
if(event.dataSource == 'StatusRequestResponse') {
  // ... work with data variables here ...
}
```

Data Name | Message Type
-------------- | --------------
StatusRequestResponse | 2703

Response to status request
### Variables 

```javascript  
switch(event.variables.status) {
  case 'disconnected':
  // ... handle the state here ...
  break;
  case 'connected':
  // ... handle the state here ...
  break;
}
```

Name | Title | Description | States
-------------- | -------------- | -------------- | --------------
status | Status | Indicates if module mounted as USB device | disconnected / connected

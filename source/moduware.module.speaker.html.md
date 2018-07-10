---
title: moduware.module.speaker Driver

language_tabs:
  - javascript

toc_footers:
  - <a href='https://moduware.github.io/developer-documentation/module-drivers/'>Drivers list</a>

search: true
---

# Driver: moduware.module.speaker

**Type**: moduware.module.speaker

**Version**: 1.0.0
# Commands 

## Turn on speaker

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'Connect', []);
```

Command Name | Message Type
-------------- | --------------
Connect | 2700

Turns on speaker module.

## Turn off speaker

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'Disconnect', []);
```

Command Name | Message Type
-------------- | --------------
Disconnect | 2700

Turn off speaker module

## Status Check

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'StatusCheck', []);
```

Command Name | Message Type
-------------- | --------------
StatusCheck | 2702

Checks the status of Speaker module, to work with Speaker module, speaker module must be turned on.

## Ask Bluetooh Name

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'AskBluetoothName', []);
```

Command Name | Message Type
-------------- | --------------
AskBluetoothName | 2704

Ask for module bluetooth name

## Set Default State As On

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'SetDefaultStateAsOn', []);
```

Command Name | Message Type
-------------- | --------------
SetDefaultStateAsOn | 2706

Set module to turn on when powered

## Set Default State As Off

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'SetDefaultStateAsOff', []);
```

Command Name | Message Type
-------------- | --------------
SetDefaultStateAsOff | 2706

Set module to stay off when powered
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
  

## State Change Response

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

## Status Request Response

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

```javascript  
switch(event.variables.defaultState) {
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
status | Status | Indicates if module is turned on or not | disconnected / connected
defaultState | Default State | Indicates default state for module when it is connected | disconnected / connected

## Bluetooth Name Request Response

```javascript
if(event.dataSource == 'BluetoothNameRequestResponse') {
  // ... work with data variables here ...
}
```

Data Name | Message Type
-------------- | --------------
BluetoothNameRequestResponse | 2705

Response to request of bluetooth name of speaker module
### Variables 

```javascript      
console.log(event.variables.bluetoothName);
```

Name | Title | Description | States
-------------- | -------------- | -------------- | --------------
bluetoothName | Bluetooth Name | - | *

## Default State Change Request Response

```javascript
if(event.dataSource == 'DefaultStateChangeRequestResponse') {
  // ... work with data variables here ...
}
```

Data Name | Message Type
-------------- | --------------
DefaultStateChangeRequestResponse | 2707

Response to request of configuring new default state
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
result | Result | Result of changing default state | success / failure

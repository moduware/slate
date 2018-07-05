---
title: moduware.module.led Driver

language_tabs:
  - javascript

toc_footers:
  - <a href='#'>Drivers list</a>

search: true
---

# Driver: moduware.module.led

**Type**: moduware.module.led

**Version**: 1.1.0
# Commands 

## Set color in RGB

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'SetRGB', [<Red>, <Green>, <Blue>]);
```

Command Name | Message Type
-------------- | --------------
SetRGB | 2702

Changes color of module to specified RGB color, takes 3 integers
### Arguments 

Name | Description | Validation
-------------- | -------------- | --------------
Red | - | (**value** >= 0) and (**value** <= 255)  

Name | Description | Validation
-------------- | -------------- | --------------
Green | - | (**value** >= 0) and (**value** <= 255)  

Name | Description | Validation
-------------- | -------------- | --------------
Blue | - | (**value** >= 0) and (**value** <= 255)  

## Turn off module leds

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'TurnOffLeds', []);
```

Command Name | Message Type
-------------- | --------------
TurnOffLeds | 2700

Turns off all led elements on module

## Flash LED Red And Blue

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'FlashLEDRedAndBlue', []);
```

Command Name | Message Type
-------------- | --------------
FlashLEDRedAndBlue | 2700

Flashed LED elements with red and blue color

## Set One LED in RGB

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'SetOneLEDInRGB', [<LedIndex>, <Red>, <Green>, <Blue>]);
```

Command Name | Message Type
-------------- | --------------
SetOneLEDInRGB | 2708

Set particular LED in mudule to specific RGB color
### Arguments 

Name | Description | Validation
-------------- | -------------- | --------------
LedIndex | Integer made of byte where bits indicate leds to set 0-5, like 00001001 | (**value** >= 0) and (**value** <= 5)  

Name | Description | Validation
-------------- | -------------- | --------------
Red | - | (**value** >= 0) and (**value** <= 255)  

Name | Description | Validation
-------------- | -------------- | --------------
Green | - | (**value** >= 0) and (**value** <= 255)  

Name | Description | Validation
-------------- | -------------- | --------------
Blue | - | (**value** >= 0) and (**value** <= 255)  

## Set Flash brightness

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'SetFlashes', [<Flash 1 Brightness>, <Flash 2 Brightness>]);
```

Command Name | Message Type
-------------- | --------------
SetFlashes | 270A

Configure brightness of flash elements
### Arguments 

Name | Description | Validation
-------------- | -------------- | --------------
Flash 1 Brightness | - | (**value** >= 0) and (**value** <= 9000)  

Name | Description | Validation
-------------- | -------------- | --------------
Flash 2 Brightness | - | (**value** >= 0) and (**value** <= 9000)  

## Make flash with delay

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'FlashWithDelay', [<Power>, <Delay>]);
```

Command Name | Message Type
-------------- | --------------
FlashWithDelay | 270A

Flashes one time with specified power after delay
### Arguments 

Name | Description | Validation
-------------- | -------------- | --------------
Power | - | (**value** >= 0) and (**value** <= 15)  

Name | Description | Validation
-------------- | -------------- | --------------
Delay | - | (**value** >= 0) and (**value** <= 1280)  

## Turn off module flashes

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'TurnOffFlashs', []);
```

Command Name | Message Type
-------------- | --------------
TurnOffFlashs | 270A

Turn off all module flash elements

## Start Flashing RGB LEDs

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'StartFlashingRgbLeds', [<Interval>, <Duration>, <Red>, <Green>, <Blue>]);
```

Command Name | Message Type
-------------- | --------------
StartFlashingRgbLeds | 270E

Flashing RGB LEDs with specified duration and interval
### Arguments 

Name | Description | Validation
-------------- | -------------- | --------------
Interval | - | (**value** >= 0) and (**value** <= 65535)  

Name | Description | Validation
-------------- | -------------- | --------------
Duration | - | (**value** >= 0) and (**value** <= 65535)  

Name | Description | Validation
-------------- | -------------- | --------------
Red | - | (**value** >= 0) and (**value** <= 255)  

Name | Description | Validation
-------------- | -------------- | --------------
Green | - | (**value** >= 0) and (**value** <= 255)  

Name | Description | Validation
-------------- | -------------- | --------------
Blue | - | (**value** >= 0) and (**value** <= 255)  

## Stop Flashing RGB LEDs

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'StopFlashingRgbLeds', []);
```

Command Name | Message Type
-------------- | --------------
StopFlashingRgbLeds | 270E

Flashing RGB LEDs with specified duration and interval

## Start Flashing Flash LEDs

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'StartFlashingFlashLeds', [<Interval>, <Duration>, <Flash Brightness>]);
```

Command Name | Message Type
-------------- | --------------
StartFlashingFlashLeds | 2710

Flashing Flash LEDs with specified duration and interval
### Arguments 

Name | Description | Validation
-------------- | -------------- | --------------
Interval | - | (**value** >= 0) and (**value** <= 65535)  

Name | Description | Validation
-------------- | -------------- | --------------
Duration | - | (**value** >= 0) and (**value** <= 65535)  

Name | Description | Validation
-------------- | -------------- | --------------
Flash Brightness | - | (**value** >= 0) and (**value** <= 9000)  

## Stop Flashing Flash Leds

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'StopFlashingFlashLeds', []);
```

Command Name | Message Type
-------------- | --------------
StopFlashingFlashLeds | 2710

Stop Flashing Flash Leds

## Turn On Rgb Led Temperature Protection

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'TurnOnRgbLedTemperatureProtection', [<Timer Value>]);
```

Command Name | Message Type
-------------- | --------------
TurnOnRgbLedTemperatureProtection | 2712

Turn On Rgb Led Temperature Protection
### Arguments 

Name | Description | Validation
-------------- | -------------- | --------------
Timer Value | - | (**value** >= 0) and (**value** <= 65535)  

## Turn Off Rgb Led Temperature Protection

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'TurnOffRgbLedTemperatureProtection', []);
```

Command Name | Message Type
-------------- | --------------
TurnOffRgbLedTemperatureProtection | 2712

Turn Off Rgb Led Temperature Protection

## Turn On Flash Led Temperature Protection

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'TurnOnFlashLedTemperatureProtection', [<Timer Value>]);
```

Command Name | Message Type
-------------- | --------------
TurnOnFlashLedTemperatureProtection | 2716

Turn On Flash Led Temperature Protection
### Arguments 

Name | Description | Validation
-------------- | -------------- | --------------
Timer Value | - | (**value** >= 0) and (**value** <= 65535)  

## Turn Off Flash Led Temperature Protection

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'TurnOffFlashLedTemperatureProtection', []);
```

Command Name | Message Type
-------------- | --------------
TurnOffFlashLedTemperatureProtection | 2716

Turn Off Flash Led Temperature Protection

## Request Status

```javascript
Moduware.v0.API.Module.SendCommand(Moduware.Arguments.uuid, 'RequestStatus', []);
```

Command Name | Message Type
-------------- | --------------
RequestStatus | 2714

Request status of the LED module

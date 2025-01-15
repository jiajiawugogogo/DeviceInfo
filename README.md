# DeviceInfo
Integrating Device Info to your App, Let you get these device information to better serve the game

This plugin allows you to get device info, such as CPU/Mem/Disk/OS Information, Let you better understand the current player's hardware environment, so as to give full play to your game performance

You can use it to detect the player's current hardware quality, recommend the player's appropriate configuration options, use the device information to generate a unique code, and so on.

# Setup
Put the DeviceInfo directory into the Plugins directory. After starting UE, you can refer to the UDeviceInfoDemo.cpp file, which demonstrates how to use the DeviceInfo project.

# Interface
### 1、Use these codes to register the callback method of DeviceInfoWrapper
```
UDeviceWrapper::DeviceInfoEvents.AddStatic(&UDeviceInfoDemo::OnDeviceInfoEvent_StaticCallback);
```
Or
```
UDeviceWrapper::DeviceInfoEvents.AddUObject(this, &UDeviceInfoDemo::OnDeviceInfoEvent_Implementation);
```

### 2、Call the following interface to initiate a request to obtain device information
```
UDeviceWrapper::RequestDeviceInfo(ExtraJson);
```

### 3、You will get callback information, the details are as follows:
```
   "winDeviceInfo": {
        "videos": Array[],  Graphics card information
        "disks": Array[],    Disk information
        "memory": Array[],   Memory information
        "processor": Array[],   Processor information
        "network": Array[],   Network card information
        "os": Object{...},    Operating system information
        "baseboards": Object{...},  Motherboard information
        "bios": Object{...},    BIOS information
        "methodId": 0,
        "retCode": -1,
        "retMsg": "",
        "thirdCode": -1,
        "thirdMsg": "",
        "extraJson": ""
    }
```

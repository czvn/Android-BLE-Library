# Android-BLE-Demo && Android BLE Library
This project includes two modules.It makes two Android Device to communicate with Bluetooth Low Energy. It can only run in  Lolipop devices(API 21+).

------

#Demo Module
##Usages
* Need two Android Device.
* One as Peripheral by click "StartGattServer", maybe  you should click "TestAdvertise" to make it works well.
* And the other device as Central by click "Scan" to scan the Peripherals, and then you can click the result to connect the Peripherals.
* After the toast "ConnectSuccess", you can send Message.

------

#Android BLE Library
##Installation
You can get the compiled library on [Jcenter](https://bintray.com/czvn/maven/blelibrary/view).

Throw this in your `build.gradle `.


```
compile 'me.czvn:blelibrary:1.1.0'
```

##Usages
### As Peripheral
* Start Advertise


```
BLEAdvertiser bleAdvertiser = BLEAdvertiser.getInstance(context, BLEAdvertiser.IAdvertiseResultListener);

bleAdvertiser.startAdvertise();
```


* Start GattServer

```
BLEServer bleServer=BLEServer.getInstance(context, IBLECallback);

bleServer.startGattServer();
```
* Send Data


```
bleServer.sendData(byte[] data);
```

###As Central
* Start Scan


```
BLEScanner bleScanner=BLEScanner.getInstance(context, BLEScanner.IScanResultListener);

bleScanner.startScan();
```
On Android M device,you need required the `ACCESS_COARSE_LOCATION` permission before the scan;
* Connect


```
BLEClient bleClient=new BLEClient(context,IBLECallback);

bleClient.startConnect(String address);
```

* Send Data

```
bleClient.sendData(byte[] data);

```



License
------

    Copyright 2015 czvn.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.






# react-native-usbserial

This wrapper implementation is totally based on [usb-serial-for-android](https://github.com/mik3y/usb-serial-for-android). Thanks [mik3y](https://github.com/mik3y) for the awesome project.

## Installation

```
npm install react-native-usbserial-cvk --save
```

## Integrate module

To integrate `react-native-usbserial` with the rest of your react app just execute:
```
react-native link react-native-usbserial-cvk
```

### Android

To integrate it with your android application you also need to add these following lines on your `android/app/build.gradle`:

```gradle
repositories {
        maven { url 'https://jitpack.io' }
        maven { url "https://oss.sonatype.org/content/repositories/snapshots/" }
}
```

## Usage

```javascript
import { UsbSerial} from 'react-native-usbserial-cvk';

let usb = new UsbSerial();

// get usb device list
usb.getDeviceListAsync()
   .then(data => {
      console.log(data);
     });
   });
   
// write data to usb device
usb.openDeviceAsync(this.state.usbDeviceList[0])
   .then(usbDevice => {
     usbDevice.writeAsync(this.plt);
   });
```

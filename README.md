# Flutter GoogleMaps

พัฒนาโดย 

[อาจาย์พิศาล สุขขี](https://www.facebook.com/numvarn)

phisan.s@sskru.ac.th

สาขาวิทยาการคอมพิวเตอร์, คณะศิลปศาสตร์และวิทยาศาสตร์ มหาวิทยาลัยราชภัฏศรีสะเกษ

**Packages we are using:**

- google_maps_flutter: [link](https://pub.dev/packages/google_maps_flutter)
- geolocator: [link](https://pub.dev/packages/geolocator)

**Description:**

โมบายแอปพลิเคชั่นนี้พัฒนาขึ้นเพื่อใช้เป็นสื่อการเรียนการสอน และตัวอย่างในกรณีศึกษาการพัฒนาโมบายแอปพลิเคชั่นด้วย Flutter ในรายวิชาการพัฒนาโปรแกรมบนมือถือ

เพื่อให้นักศึกษาได้ใช้สำหรับการศึกษา ทดลองปฏิบัติตาม ให้เกิดความรู้ ความเข้าใจ และทักษะในการพัฒนาโปรแกรมบนมือถือด้วย Flutter

## เพิ่ม Dependencies ใน Flutter
```yaml
dependencies:
  flutter:
    sdk: flutter
  ..
  cupertino_icons: ^1.0.0
  geolocator: ^6.1.14
  google_maps_flutter: ^1.1.1
```

**การใช้งาน**
```dart
import 'package:geolocator/geolocator.dart';
import 'package:google_maps_flutter/google_maps_flutter.dart';
```

## เพิ่ม Google Maps API key ในโปรเจค

### สำหรับ Android

พอได้ api key แล้วก็ไปที่ android/app/src/main/AndroidManifest.xml เอา API key ไปใส่ไว้ในนี้ โดยเพิ่มเป็น <meta-data> และเพิ่ม permission สำหรับใช้งาน geolocator

```xml
<manifest ...
 
   <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
   <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
 
  <application ...
    <meta-data android:name="com.google.android.geo.API_KEY"
               android:value="YOUR KEY HERE"/>
```

### สำหรับ iOS

สำหรับ iOS จะเพิ่ม API key ที่ ios/Runner/AppDelegate.swift

```swift
GMSServices.provideAPIKey("YOUR KEY HERE")
```

โดยเพิ่มที่

```swift
import UIKit
import Flutter
import GoogleMaps
 
@UIApplicationMain
@objc class AppDelegate: FlutterAppDelegate {
  override func application(
    _ application: UIApplication,
    didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?
  ) -> Bool {
    GMSServices.provideAPIKey("YOUR KEY HERE")
    GeneratedPluginRegistrant.register(with: self)
    return super.application(application, didFinishLaunchingWithOptions: launchOptions)
  }
}
```

ปล. ห้ามลืม import GoogleMaps

```switf
import GoogleMaps
```

เพิ่ม permission ที่ ios/Runner/Info.plist

```swift
<plist version="1.0">
<dict>
	...
	<key>NSLocationWhenInUseUsageDescription</key>
	<string>This app needs your location to test the location feature of the Google Maps plugin.</string>
	<key>io.flutter.embedded_views_preview</key>
	<true/>
</dict>
</plist>
```

## แหล่งข้อมูลอ้างอิง

- Flutter : การใช้ Google Maps ใน Flutter [link](https://benzneststudios.com/blog/flutter/using-google-maps-in-flutter/)
- Working with Geolocation and Geocoding in Flutter (And Integration with Maps) [link](https://medium.com/swlh/working-with-geolocation-and-geocoding-in-flutter-and-integration-with-maps-16fb0bc35ede)

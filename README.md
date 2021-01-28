# Flutter GoogleMaps

A new Flutter project.

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

## เพิ่ม Google Maps API key ในโปรเจค

พอได้ api key แล้วก็ไปที่ android/app/src/main/AndroidManifest.xml เอา API key ไปใส่ไว้ในนี้ โดยเพิ่มเป็น <meta-data> และเพิ่ม permission สำหรับใช้งาน location

```
<manifest ...
 
   <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
 
  <application ...
    <meta-data android:name="com.google.android.geo.API_KEY"
               android:value="YOUR KEY HERE"/>
```
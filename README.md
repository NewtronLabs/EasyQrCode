# EasyQrCode

Library for creating and scanning QR codes for Android.

---

## How to Use 

### Step 1

Include the below dependencies in your `build.gradle` project.

```gradle
buildscript {
    repositories {
        jcenter()
        maven { url "http://code.newtronlabs.com:8081/artifactory/libs-release-local" }
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.5.2'
        classpath 'com.newtronlabs.android:plugin:4.0.0'
    }
}

allprojects {
    repositories {
        jcenter()
        maven { url "http://code.newtronlabs.com:8081/artifactory/libs-release-local" }
    }
}

subprojects {
    apply plugin: 'com.newtronlabs.android'
}
```

In the `build.gradle` for your app.

```gradle
dependencies {
    compileOnly 'com.newtronlabs.easyqrcode:generator:4.0.0'
}
```

### Step 2

**Simple Logging**

```java
IQrCodeBuilderBluetoothDevice builder = (IQrCodeBuilderBluetoothDevice) BuilderFactory.getInstance()
                    .get(IBuilderFactory.Builder.BT_DEVICE);

IQrCode qrCode = builder.setAddress("10:20:30").build();
Bitmap bitmap = qrCode.generateBitmap(1000);
qrImageView.setImageBitmap(bitmap);
```

### Supported Types

```java
IQrCodeBuilderBluetoothDevice
IQrCodeBuilderEmail
IQrCodeBuilderEvent
IQrCodeBuilderRaw
IQrCodeBuilderText
```

**Encrpted Logging**

```java
// Example Cipher and Key.
DESKeySpec keySpec = new DESKeySpec("Your secret Key phrase".getBytes("UTF8"));
SecretKeyFactory keyFactory = SecretKeyFactory.getInstance("DES");
SecretKey key = keyFactory.generateSecret(keySpec);\
Cipher cipher;
cipher = Cipher.getInstance("DES");

// Switch To Secure Logger
SLog.setLogger(new SecureLogger(cipher, key));
SLog.v("Test", "This is now encrypted!");
```

---

## License

https://gist.github.com/NewtronLabs/216f45db2339e0bc638e7c14a6af9cc8

## Contact

solutions@newtronlabs.com

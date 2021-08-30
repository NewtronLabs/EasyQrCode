# EasyQrCode

Library for creating and scanning QR codes for Android. Fully supports encryption.

---

## How to Use 

### Step 1

Include the below dependencies in your `build.gradle` project.

```gradle
buildscript {
    repositories {
        jcenter()
        maven { url "https://newtronlabs.jfrog.io/artifactory/libs-release-local"
            metadataSources {
                artifact()
            }
        }
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.5.2'
        classpath 'com.newtronlabs.android:plugin:4.0.5'
    }
}

allprojects {
    repositories {
        jcenter()
        maven { url "https://newtronlabs.jfrog.io/artifactory/libs-release-local"
            metadataSources {
                artifact()
            }
        }
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

---

## Support Us
Please support the continued development of these libraries. We host and develop these libraries for free. Any support is deeply appriciated. Thank you!

<p align="center">
  <img src="https://drive.google.com/uc?id=1rbY8qjxvWU8GQgaqDrOY4-fYOWobQKk3" width="200" height="200" title="Support us" alt="Support us">
</p>

<p align="center">
  <strong>BTC Address:</strong> 39JmAfnNhaEPKz5wjQjQQj4jcv9BM11NQb
</p>

---

## License

https://gist.github.com/NewtronLabs/216f45db2339e0bc638e7c14a6af9cc8

## Contact

solutions@newtronlabs.com

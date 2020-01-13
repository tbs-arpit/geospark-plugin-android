![GeoSpark](https://github.com/geosparks/cordova-plugin-geospark/blob/master/logo.png?raw=true)

[![npm version](https://badge.fury.io/js/cordova-plugin-geospark.svg)](https://badge.fury.io/js/cordova-plugin-geospark)

[GeoSpark](https://geospark.co) is the location intelligence platform.

#### This one is updated from [cordova-plugin-geospark](https://www.npmjs.com/package/cordova-plugin-geospark)

## Documentation

See the full documentation [here](https://docs.geospark.co/cordova).

## Add Plugin
```
cordova plugin add https://github.com/tbs-arpit/geospark-plugin-android.git
```

* Update Your PUBLISH KEY in `plugins/cordova-plugin-geospark/src/android/GeoSparkPlugin.java` and `platforms/android/*/GeoSparkPlugin.java`:
```
 GeoSpark.initialize(application, "YOUR-PUBLISHABLE-KEY");
```

## Prerequisites (Android)
* Platform >= 8.1.0
* Gradle version >= 5.4.1
* MinSdkVersion >= 21
* BuildToolsVersion >= 29.0.3
* Following Lines Should be in `platforms/android/app/src/main/java/com/cordova/development/MainActivity.java` (path will change after package name update, e.g. java/packageName/MainActivity.java)
```
package com.cordova.development;

import android.content.Intent;
import android.os.Bundle;

import com.geospark.lib.GeoSpark;                           //Add this Line

import org.apache.cordova.CordovaActivity;

public class MainActivity extends CordovaActivity {
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        GeoSpark.logger(this, true);                        //Add this Line
        GeoSpark.exportToFile(this);                        //Add this Line
        // enable Cordova apps to be started in the background
        Bundle extras = getIntent().getExtras();
        if (extras != null && extras.getBoolean("cdvStartInBackground", false)) {
            moveTaskToBack(true);
        }

        // Set by <content src="index.html" /> in config.xml
        loadUrl(launchUrl);
    }
}
```

## Support

Have questions? We're here to help! Email us at [support@geospark.co](mailto:support@geospark.co).

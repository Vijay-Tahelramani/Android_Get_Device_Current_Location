# Android_Get_Device-s_Current_Location
This application tutorial is for getting Device's Current LOcation
In this tutorial I have used location services to get users current location.
Location services are of two types.
1) Network Location provider
2) GPS Location Provider

Network location provider uses our mobile connectivity provider and will give the nearest tower location. 
GPS gives the exact location. In in-door situations gps does not works accuratly.

To use this Location services add these below lines in your Android menifest file.
```
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission. ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.INTERNET" />
```

ACCESS_FINE_LOCATION gives us the exact location using using both network and gps provider.
ACCESS_COARSE_LOCATION uses network provider and gives us the nearest tower location.

To get our device's current location in android LocationListener interface is used like i have done below.
```
class MainActivity extends Activity implements LocationListener
```
As you create the interface you need to override some methods which are required to be implemented to get device's location.
Here there are four methods..
```
onLocationChanged(Location location);
onProviderDisabled(String provider);
onProviderEnabled(String provider);
onStatusChanged(String provider, int status, Bundle extras);
```
Now Create LocationManager instance as reference to the location service. 
Location service reference will be created using ```getSystemService()``` method.
After creating the location service reference, location updates are requested using ```requestLocationUpdates()``` method of LocationManager.
See ```OnCreate()``` Method in ```MainActivity.java```

To implement above four methods and to get current location see the code of ```MainActivity.java```

# Essentials — How to access User Location

How to get your geolocation coordinate from your phone.

![loca](http://i.giphy.com/HzMfJIkTZgx8s.gif)

**1) Create new single view application.**

**2) Add the CoreLocation library at the top of your ViewController.  This will give you access to the set of functions and atrributes related to location.**

```swift 
        import CoreLocation
```

**3) Add CLLocationManagerDelegate to your class header**

```swift
        class ViewController: UIViewController, CLLocationManagerDelegate
```

**4) Add the following property to our ViewController class:**

```swift 
        var locationManager = CLLocationManager() 
```

This creates a new CLLocation manager instance.


**5) Let’s edit our viewDidLoad method to get our location manager instance started!**

```swift

        override func viewDidLoad() {
                self.locationManager.desiredAccuracy = kCLLocationAccuracyBest
                self.locationManager.requestWhenInUseAuthorization()
                self.locationManager.requestAlwaysAuthorization()
                self.locationManager.startUpdatingLocation()
```


**6) We need tell swift what to do when we call our locationManager.  In this case, we want it to print out "locations."**

```swift
 func locationManager(manager: CLLocationManager, didUpdateLocations locations: [CLLocation]) {
        print(locations)
 }
```

**7)** Go into your Project Navigator, find the ```info.plist``` file.  Hover your mouse over any of the triangles at the end of the first column until you see a plus sign.  Click the plus sign, and you will see a text box. Enter *NSLocationWhenInUseUsageDescription*.  Do the same thing again but this time enter *NSLocationAlwaysUsageDescription*.  Adding these will prompt your user with an alert asking if it is ok if the app gets their current location.


**8. Last step!**  In your Project Navigator, click on the name of your app, at the top.  On the top menu bar, select *Build Phases*.  Select **Link with Binary Library** and add the *CoreLocation.framework.*

Now run your app!

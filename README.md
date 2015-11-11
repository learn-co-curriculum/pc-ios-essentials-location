# Essentials 

How to get your geolocation coordinate from your phone.

[loca](http://i.giphy.com/HzMfJIkTZgx8s.gif)

1. Create new single view application.
2. Add the CoreLocation library.  This will give you access to the set of functions and atrributes related to location.

```swift 
import CoreLocation
```

3.  We are going to starting adding the following property to our ViewController class:

```swift 
private var locationManager = CLLocationManager() 
```

4. Let’s edit our viewDidLoad method to get our location manager instance started!

```swift

override func viewDidLoad() {
    super.viewDidLoad()
    self.locationManager.delegate = self
    self.locationManager.requestAlwaysAuthorization()

```

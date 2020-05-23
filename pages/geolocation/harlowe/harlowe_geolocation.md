# "Geolocation": Harlowe (v2.0)

## Summary

Many browsers allow access to the current location through the [Geolocation property](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation) and associated functions. This functionality is subject to the user agreeing to allow access. Until the functionality is unlocked, or if the user declines, default values will be returned.

Functionality availability and their results should always be tested against other location services or information. Most browsers will return results through the fastest and sometimes least-accurate methods possible.

Harlowe does not have an easy way to bridge the gap between its macros and JavaScript. In this example, the `<script>` element is used to test for, run, and show an **[alert()](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert)** with data from the JavaScript functions.

## Example

[Download](harlowe_geolocation_example.html)

## Twee Code

```twee
:: StoryTitle
Geolocation in Harlowe

:: UserScript[script]
(function () {

  window.geolocation = {

    available: function() {
      return ("geolocation" in navigator
        && typeof navigator.geolocation.getCurrentPosition === "function");
    },
    getLocation: function() {

      // Create initial values
      var location = { latitude : 0, longitude : 0 };

      // Create success callback to store values
      var  positionSuccess = function (position) {

        location.latitude = position.coords.latitude;
        location.longitude = position.coords.longitude;

      };

      // Create error callback
      var positionError = function (error) {
        /* Code that handles errors */
      };

      // Create initial options
      var positionOptions = {
        timeout: 31000,
        enableHighAccuracy: true,
        maximumAge : 120000
      };


      // Ask for location based on callbacks and options
      navigator.geolocation.getCurrentPosition(
        positionSuccess,
        positionError,
        positionOptions
      );

      // Return location found
      // If not location, will return initial (0,0) values
      return location;

    },
    approximateLocation: function (a, b, allowedDiff) {
        // allowedDiff must always be > 0
      if (a === b) { // handles various "exact" edge cases
        return true;
      }

      allowedDiff = allowedDiff || 0.0005;

      return Math.abs(a - b) < allowedDiff;
    }

  };
  
}());

:: Start
[[Ask for permission]]

:: Ask for permission
<script>
if(window.geolocation.available() ) {
  var geolocation = window.geolocation.getLocation();
  alert("Latitude: " + geolocation.latitude + " Longitude:" + geolocation.longitude);
}
</script>

```

[Twee Download](harlowe_geolocation_twee.txt)

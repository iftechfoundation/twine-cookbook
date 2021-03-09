# "Geolocation": SugarCube (v2.18)

## Summary

Many browsers allow access to the current location through the [Geolocation property](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation) and associated functions. This functionality is subject to the user agreeing to allow access. Until the functionality is unlocked, or if the user declines, default values will be returned.

Functionality availability and their results should always be tested against other location services or information. Most browsers will return results through the fastest and sometimes least-accurate methods possible.

This example uses [`<<linkreplace>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-linkreplace) and [`<<script>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-script) macros to run JavaScript in passages in SugarCube. The *[State.variables](http://www.motoslave.net/sugarcube/2/docs/api-state.html#state-api-getter-variables)* object is used to store the results of running JavaScript functions and using those values in TwineScript.

## Example

[Download](sugarcube_geolocation_example.html){: target="_top" download="sugarcube_geolocation_example.html"}

## Twee Code

```twee
:: StoryTitle
Geolocation in SugarCube

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
<<linkreplace "Ask for permission">>
  <<script>>
  
  State.variables.geoLocationAvailable = window.geolocation.available();
  
  if(window.geolocation.available()) {
    State.variables.location = window.geolocation.getLocation();
  }
  <</script>>
  [[Show results]]
<</linkreplace>>
  

:: Show results
<<script>>
  
  State.variables.geoLocationAvailable = window.geolocation.available();
  
  if(window.geolocation.available()) {
    State.variables.location = window.geolocation.getLocation();
  }
<</script>>

Is geolocation available? $geoLocationAvailable

If so, what is the current location?

Latitude: $location.latitude

Longitude: $location.longitude

Are we in the approximate location of Stonehenge (51.1788853, -1.828409)?

<<set $approxLat to  window.geolocation.approximateLocation(State.variables.location.latitude, 51.1788853) >>

<<set $approxLong to window.geolocation.approximateLocation(State.variables.location.longitude, -1.828409) >>

Latitude: $approxLat
Longitude: $approxLong

```

[Twee Download](sugarcube_geolocation_twee.txt){ target="_top" download="sugarcube_geolocation_twee.txt"}

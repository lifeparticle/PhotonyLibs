# AstroJava [development in progress]

AstroJava is a Java library for Android which provides access to Sunrise, Sunset, Moonrise, Moonset information.

```java
// Sydney, Australia
double latitude = -33.92;
double longitude = 151.1852;
```

To access today's data for **Sun** in Local time zone
```java
Sun sun = new Sun();
// for a specific city
sun.getSunrise ("Sydney", "Australia", "LOCAL"); // 06:27:53 AM AEST
sun.getSunset ("Sydney", "Australia", "LOCAL");  // 05:17:08 PM AEST

// for latitude and longitude
sun.getSunrise(latitude, longitude, "LOCAL"); // 06:27:53 AM AEST
sun.getSunset(latitude, longitude, "LOCAL");  // 05:17:08 PM AEST
```
To access data for a specific date
```java
// format for date is dd-MM-yyyy
sun.getSunrise ("Sydney", "Australia", "28-04-2019", "LOCAL"); // 06:27:53 AM AEST
sun.getSunset ("Sydney", "Australia", "28-04-2019", "LOCAL");  // 05:17:08 PM AEST

sun.getSunrise (latitude, longitude, "28-04-2019", "LOCAL"); // 06:27:53 AM AEST
sun.getSunset (latitude, longitude, "28-04-2019", "LOCAL");  // 05:17:08 PM AEST
```

To access today's data for **Sun** (UTC in milliseconds)
```java
sun.getSunrise ("Dhaka", "Bangladesh", "28-04-2019", "UTC"); // 84426509
sun.getSunset ("Dhaka", "Bangladesh", "28-04-2019", "UTC");  // 44708333 
```
**Errors**
```java
/* If you're getting error like 'city not found' that means it's not in the city list
* either use latitude and longitude or create an issue */
sun.getSunrise ("Avalon", "Earth", "28-04-2019", "LOCAL"); // city not found

/* If you're getting error like 'unparseable date' that means you're not
* providing the date in a correct format */
sun.getSunrise ("Sydney", "Australia", "28/04/2019", "LOCAL"); // unparseable date
```
___

To access today's data for **Moon**
```java
Moon moon = new Moon();
moon.getSunrise(latitude, longitude);
moon.getSunset(latitude, longitude);
```
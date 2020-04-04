BYU/BYUI Ride Board App
=======================

Problem
-------
The ride board is very nice to use bc you can always find rides for the low. The problem is that one
has to scroll all the way down for a while just to find what you're looking for.

Solution
--------
It would be nice to have an app that allows the user to filter, sort, and compare rides instantly.


UX
--
Display a feed that lists posts depending on the user filter options.  There are two modes, offering
or asking, and each have slightly different options.  Each representation of the post should display
all of the filter option info if available along with author name, and other nice-to-haves.  There
should also be a link to the original post to allow the user to message and book a ride.
 Note: the app will not handle messaging or booking of rides.  Leave that to FB.

### Filter Options

* offering
  * origin
  * destination
  * leave date
  * return date
  * price for one-way
  * price for two-way
  * no. of seats available

* asking
	* origin
	* destination
	* leave date
	* return date
	* no. of seats to occupy

Authorization
-------------
* the app should be available to anyone that has access to the FB group

Authentication
--------------
* TBD

Prerequisites
----------
* make sure the FB API gives us access to
  1. a private group (assuming an admin accepts)
  2. the complete feed of the group
  3. a machine-friendly representation of text with background images
  4. the following post info
    * date posted/updated
    * link to the original post on fb

NLP Parser
----------

### Example Posts
![alt text](https://github.com/baaae/Ride-Board/blob/master/screenshots/Screen%20Shot%202020-04-04%20at%203.59.07%20PM.png "Logo Title Text 1")

1. Determine if offering or asking?
Offering

2. Extract data.
```
  {
    origin: "Salt Lake",
    destination: "Rexburg",
    leaveDate: "Saturday April 04",
    returnDate: null,
    priceOneWay: null,
    priceTwoWay: null,
    seatsAvailable: 3
  }
```

![alt text](https://github.com/baaae/Ride-Board/blob/master/screenshots/Screen%20Shot%202020-04-04%20at%204.01.41%20PM.png "Logo Title Text 1")

1. Determine if offering or asking?
  Asking

2. Extract information.
```
  {
    origin: "Utah",
    destination: "Rexburg",
    leaveDate: "this week",
    returnDate: null,
    seatsNeeded: 2
  }
```

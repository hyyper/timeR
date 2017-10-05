# TimeR

TimeR is a modern countdown script that is built for initalizing multiple types of countdowns based on server or client's local time. Housing multiple features that include countdown cycling without the need of jQuery.

## Getting Started

These instructions will get you a copy of the TimeR project up and running on your local machine for development and testing purposes.


### Dependencies

```html
<!-- Include the Moment library -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.10.3/moment.js"></script>
  ```


### Quickstart

Instantiate a new TimeR object.

 with a css selector for the div that should become the editor.


```html
<!-- Include TimeR default stylesheet -->
<link href="css/default-style.css" rel="stylesheet">

<!-- Create a container for the TimeR to insert into -->
<div id="TimeR"></div>

<!-- Create a container for the date of the countdown to insert into -->
<div id="until"></div>

<!-- Include the Moment library -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.10.3/moment.js"></script>

<!-- Include the TimeR library -->
<script src="js/TimeR-2.0.1.js"></script>

<!-- Initialize TimeR countDown -->
<script type="text/javascript">
	window.addEventListener("load", function() {

		var t = new TimeR({
			id     : "TimeR",
			now    : "02/18/2017 8:00:00",
			end    : "03/17/2017 1:00:00",

			unitNames : {
				"minutes": "MINS", //End with Plural
				"seconds": "SECS",
				"years"  : "YEARS",
				"days"   : "DAYS",
				"hours"  : "HOURS"
			}

		});

		t.countDown();


	});
</script>
```


### CSS

Styling Sheets follow Block Element Modifier naming convention,

```css
.countdown {
	float: left;
	margin-top: 5px;
}

.countdown--digit {
	font-size: 2.5em;
	font-weight: bold;
	background-color: #ffda00;
	padding: 5px;
	width: 80px;
	text-align: center;
	display: inline-block;
	border-radius: 4px;
	margin: 5px 3px 0 0;
}

.countdown--unit {
	font-size: 0.37em;
	font-weight: 100;
	color: #ffffff;
	background-color: #000000;
}
```

### Default Options

```html
this.defaults = {
    id        : "TimeR",
    message   : "All Sold Out!",
    now       : moment(),
    end       : moment(),
    dateFormat: "MM/DD/YYYY HH:mm:ss"
};
```


### Options

```html
<!-- Initialize TimeR countDown -->
<script type="text/javascript">
	window.addEventListener("load", function() {

		var t = new TimeR({
			id        : "TimeR", // Optional, defaults 'TimeR'
			message   : "All Sold Out!", // Optional, default 'All Sold Out!'. Displays when ended.
			now       : "02/18/2017 8:00:00", 
			end       : "03/17/2017 1:00:00",
    		dateFormat: "MM/DD/YYYY HH:mm:ss" // Optional

    		/** 
    		 * Optional
    		 * Used to translate Unit Names to any wording,
    		 * make sure to end iwth Plural as system will
    		 * automatically remove the 'S' on 1's & 0's.
    		 */
			unitNames : {
				"minutes": "MINS", // End with Plural
				"seconds": "SECS",
				"years"  : "YEARS",
				"days"   : "DAYS",
				"hours"  : "HOURS"
			},

			/**
		     * Optional
		     * Used to created your own formating and structure.
		     * time object - {days, hours, minutes, months, seconds}, units {days, hours, milliseconds, minutes, months, seconds, years}
		     * until string - Month Dayth 
		     * complete boolean, true when countdown is complete.
		     */
			format(time, until, complete) {

			}

		});

		t.countDown();


	});
</script>
```

## License

This project is licensed under the BSD 3-clause.
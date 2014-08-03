# How to do Javascript at Social Tables

This is a living doc. As we decide on more principles and rules we will open issues, discuss the changes and improve.

## Principles

These our are guiding principles. If anything goes against these principles it should be challenged.

* Code should be descriptive

	```js
	//good
	function turnToPointsIntoAnSVGLine(pointOne, pointTwo){}

	//ok
	function pointsToLine(pointOne, pointTwo){}

	//bad
	function makeLine(a, b){}

	/*************************/

	//good
	var usersName = "Rami";

	//ok
	var name = "Yalcin";

	//bad
	var n = "Matthew";

	/*************************/

	//good
	var thereAreResults = (results.length > 0);
    var resultHasUserField = (results[0].user != undefined);
    var errorMessageAvailable = (results.error && results.error.message);

    if ((thereAreResults && resultHasUserField) || errorMessageAvailable) {

	//bad
	if (((results.length > 0) && (results[0].user)) || (results.error && results.error.message))
	```

* Functions should `do` a single `thing`

	```js
	//good
	var game = { /* some game object */ };
	var user = {
		score: 10,
		positionInGame: 3,
		givePoint: function(){
			user.score++;
		}
	}

	//bad
	var game = { /* some game object */ };
	var user = {
		score: 10,
		positionInGame: 3,
		givePoint: function(){
			user.score++;
			game.rankUser(user);
		}
	}
	```

## Rules

None for now. Lets put these guidelines into practices and start finding rules.

## Reading

* [Airbnb](https://github.com/airbnb/javascript)
* [Node Style Guide](https://github.com/felixge/node-style-guide)
* [Google's Guide](https://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)

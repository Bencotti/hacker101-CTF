# Flag 01 - A little something to get you started

The only information we get to work with is this static page.

![challenge overview](/screenshots/01_1.JPG"info given")

The next thing to check is the page source code, to see if there is any helpful information we can use. 

``` HTML
<!doctype html>
<html>
	<head>
		<style>
			body {
				background-image: url("background.png");
			}
		</style>
	</head>
	<body>
		<p>Welcome to level 0.  Enjoy your stay.</p>
	</body>
</html>
```

Notice that the background image has a path we can further explore: background.png
Usually, the more efficient method of setting a plain background (i.e. white in this example) would be to use the built in functionality in HTML / CSS, which makes this png suspicious.

![challenge overview](/screenshots/01_2.JPG"info given")

True enough, the url contains our flag!

**Flag:** ^FLAG^c0b2e356a7ab6f65e9ac7ff154b156c934671836d31996ee3cb801a99a529211$FLAG$
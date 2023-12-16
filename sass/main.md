# Sass

Sass is a preprocessor for CSS that's been active for 17 years now. It is similar to CSS but with a lot of quality improvements for better workflow and styling.
Some cool features to note:
* [Better Variables](sass/variables)
* [Class Nesting]()
* [Partials](Sass/Partials) (files that contain a single class or purpose)
* [Operators](Sass/Operators)
* [Mixins](Sass/Mixins)

Read more about it on the [official website](https://sass-lang.com/).

An example of a scss file:

`navbar.scss`
```css
$primary-color: #dc7633;
$secondary-color: #82e0aa;
$backdrop-color: #a2d9ce;

$base-size: 2;

.navbar {
	display: flex;
	background-color: $backdrop-color;
	&_logo {
		width: 4vh;
		height: 4vh;
	}
	&_slider {
		background-color: $primary-color;
		@include transition-ease;
		&:hover {
			background-color: $secondary-color;
			transform: scale("(2 * base-size)"em)
		}
	}
}

@mixin transition-ease {
	transition: all 0.5s ease-in;
}
```

# Sass or Scss

Sass has two file extension types. That gives the user a different kind of code writing style.

One is `.sass` and the other is `.scss`.

> I usually use `.scss` 

The difference between them is how you write the file. Sass is more like python where you don't have to put the semicolon in the end of a line and don't have to use parenthesis. While scss is more like CSS.

Sass is written like this:

```css
$primary-color: red

.container
	display: flex
	flex-direction: column
	Button
		background-color: $primary-color
```

Scss in the meanwhile is written like this:

```css
$primary-color: red;

.container {
	display: flex;
	flex-direction: column;
	Button {
		background-color: $primary-color;
	}
}
```

##### Most stuff will be written in `.scss` if you want to do it in `.sass` then just remove the semicolon and parenthesis.
# Installation

It can be [installed onto the command line](https://github.com/sass/dart-sass/releases/tag/1.69.5) for compiling `.sass` and `.scss` files to `.css`.
This can be done with:

`sass source/stylesheets/index.scss build/stylesheets/index.css`

You can install Sass onto most JavaScript frameworks via the `npm install` command. It works natively on frameworks like vue.js, react.js and next.js.

`npm install sass`

If you want it to be globally available you can put the `-g` tag onto the `npm install` command.

`npm install -g sass`

To install Sass with an alternative installer other than npm, like for choco or brew you can install them this way.

choco:
`choto install sass`

brew:
`brew install sass/sass/sass`

---

If you are not using a JavaScript framework, Sass also has support for
* [Ruby](https://github.com/sass-contrib/sass-embedded-host-ruby#readme)
* [Swift](https://github.com/johnfairh/swift-sass#readme)
* [Java](https://mvnrepository.com/artifact/de.larsgrefer.sass)
	* [Gradle](https://docs.freefair.io/gradle-plugins/current/reference/#_embedded_sass)
	* [Maven](https://github.com/HebiRobotics/sass-cli-maven-plugin)

# Usage

To use Sass you need to create a file with the extension of `.sass` or `.scss` . 
After making the file it will be auto compiled if you are using a framework with native support for Sass. If else you will need to set up a compiler or manually compile it.

`sass source/stylesheets/index.scss build/stylesheets/index.css`

## React.js

In React you can import the file directly into an react component as a module or file. You don't need to import directly into the file either you can just keep those files outside in a style category.

`npm install -s sass`

then:

```js
import './Navbar.scss'
or
import './Navbar.module.scss'

export default function Navbar() {
	return(
		<div class="navbar">
			
		</div>
	)
}

```

React auto compiles the `.sass` and `.scss` files when you start or build the website.
## Vue.js

In vue you install Sass with a loader attached to it and configure your webpack config with the sass ruleset.

`npm install -D sass-loader node-sass`

```js
module.exports = {
  module: {
    rules: [
      // ... other rules omitted

      // this will apply to both plain `.scss` files
      // AND `<style lang="scss">` blocks in `.vue` files
      {
        test: /\.scss$/,
        use: [
          'vue-style-loader',
          'css-loader',
          'sass-loader'
        ]
      }
    ]
  },
  // plugin omitted
}
```

After that you can even use it natively inside of a vue template.
## Next.js

Installing Sass in next.js is similar to the others.

`npm install --save-dev sass`

> For some reason it is installed only on the dev side.


After installing Sass you can customize it's options inside of the `next.config.js` file.

```js
const path = require('path')
 
module.exports = {
  sassOptions: {
    includePaths: [path.join(__dirname, 'styles')],
  },
}
```
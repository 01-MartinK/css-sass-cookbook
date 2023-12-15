# Variables

The makers of Sass greatly improved the declaration and usage of variables in sass.
[CSS variables](CSS/Variables) were a hassle and could not be declared outside of a class.

?> How did they improve the variables in Sass?

They can now be declared outside of a class and instead inside of the file.

`_variables.scss`
``` scss
$new-variable: red;
$bg-color: #111eee;
$borderS: 2px;

.container {
	background-color: $bg-color;
	color: $new-variable;
	border-radius: $borderS;
}

```

When using a variable you must use the dollar sign `$custom-var: red;` 
instead of the double `--my-var: red;`.

With the addition of custom variables you can declare whole lines with it.

``` scss
$box-shadow: 0 0 8px black;

.container {
	box-shadow: $box-shadow;
}
```

## Built-in Variables

Sass also has built-in modules for math and other things. To use those built-in modules you use the `@use` as an import statement for the built-in properties.
``` scss
@use "sass:math" as math;

// This assignment will fail.
math.$pi: 0;
```
[Straight from Sass website](https://sass-lang.com/documentation/variables/)

Sass provides the following built-in modules:
* sass:math
* sass:string
* sass:color
* sass:list
* sass:map
* sass:selector
* sass:meta

?> You can also make modules for Sass yourself but that's another thing for another night.

### More

- You can read more about variables at the [official website](https://sass-lang.com/documentation/variables/).
- You can read more about build-in modules at the [official website](https://sass-lang.com/documentation/modules/).
# Partials

With Sass you don't have to write all of your styling into 1 file. You can separate them as separate distinct files or as modules. You can also separate them as components if needed.

---

You can separate the files as modules or separate page styling.

```
- _config.scss
- _navbar.scss
- _variables.scss
- main.scss

or module
- Navbar.module.scss
```

To use those other files, we import them into the main file or into a JavaScript component file. If it is supported.

``` scss
@import '_config';
@import '_navbar';
@import '_variables';

.container {
	&_novelty {
		background-color: red;
		color: $main-text-color; // taken from the _variables.scss file
	}
}
```

Importing starts from the folder where the file is. We don't have to mention the extension of the file because it already knows if it is a `.scss` or `.sass` file.

---

This is especially good if you are using a javascript framework that supports Sass imports directly in it's components. 

Like:
* React
* Vue
* Next

### More

- You can read more about partials at the [official website](https://sass-lang.com/guide/#partials).
- You can read more about importing and partials at the [w3schools website](https://www.w3schools.com/sass/sass_import.php).
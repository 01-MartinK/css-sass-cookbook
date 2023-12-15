# Class Nesting

[Sass](Sass/What-is-Sass) parses selectors differently than [CSS](CSS/CSS). You can nest selectors and extend them with ease.

?> A thing to note is that selectors are parsed after interpolation is resolved.

In CSS you can't edit a selector inside of a selector without writing a new line and declaring both selectors.

```css
.container {
	background-color: red;
}

.container .flex {
	display: flex;
	flex-direction: column;
}
```

In Sass you can declare a selector inside of a selector henceforth nesting. Which in return greatly increases the workflow of styling.

```css
.container {
	background-color: red;
	.flex {
		display: flex;
		flex-direction: column;
	}
}
```

## & operator

It has some special typing sign-s for better workflow in different situations. You can extend the selector name with the `&` sign. In extending it you can get better naming conventions or provide functionality to selectors more easily.

```css
.btn {
	padding: 1em;
	height: 3em;
	&_wide {
		padding: 1em 2em;
	}
	&:hover {
		cursor: pointer;
		box-shadow: 0 0 8px black;
	}
}
```

Now selector lists are comma-separated.

```css
.list, .group-side {
	display: flex;
	li, a {
		padding: 1em;
	}
}
```

### More

- You can read more about nesting at the [official website](https://sass-lang.com/documentation/style-rules/).
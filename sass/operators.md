# Operators

CSS doesn't allow operators in selectors directly while Sass does.

In Sass you can directly play with operations.

```css
.container {
	background-color: red;
	border-radius: (5px / 2);
}
```

?> An impressive thing in Sass is that it automatically converts between value differences.

```css
.container {
	border: (2px / 1em) solid red;
}
```

Sass allows these operational types:
- Numeric
- String
- Boolean
- Relational
- Equality

With Sass you can even to color operations. Like adding or mixing colors. To use these coloring operations you need to use the [built-in](Sass/Variables) module named `sass:color`.

```css
@use 'sass:color';

@debug color.adjust(#6b717f, $red: 15); // #7a717f
@debug color.adjust(#d2e1dd, $red: -10, $blue: 10); // #c8e1e7
@debug color.adjust(#998099, $lightness: -30%, $alpha: -0.4); // rgba(71, 57, 71, 0.6)

```

### More

You can read more about operators at the [official website](https://sass-lang.com/documentation/operators/)
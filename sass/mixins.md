# Mixins

Mixins area a way to allow you to define styles that can be re-used throughout your stylesheet.

So if you have a class like `.rounded-corners` that you use everywhere. You could instead use a mixin that you call inside of a selector with the `@include` function.

Mixins are initialised with the `@mixin` function. Mixins should be created before being called in a selector.

```css
@mixin round-corners {
	box-shadow: 0 0 8px black;
	border-radius: 4px;
}

.container {
	@include round-corners;
	
	display: flex;
	flex-direction: column;
}
```

?> There is a weird bug (maybe only on my side) where you create a mixin, it can't be above the inclusion but below instead

## Arguments

When creating a mixin it can take in [arguments](Sass/Variables) that can be used inside of it. Arguments can have default values, if you don't want to have to declare a variable each time.

```css
@mixin trans-ease($time: 5s) {
	transition: all $time ease-in-out;
}

.btn {
	color: red;
	@include trans-ease(5s);
	&:hover {
		color: blue;
	}
}
```

Mixings also include operations like if statements.

```css
@mixin borderize($border-size: 1px, $border-color: black) {
	border: $border-size solid $border-color;
	@if $border-color == black {
		border: ($border-size + 2px) solid red;
	}
}

.container {
	@include borderize(2px, black);
}

```

If you want to give mixins the ability to give an entire selector. You can give it a `@content` function.

```css
@mixin action-resize {
	&:not([disabled]):after {
		@content
	}
}

.after-image {
	background-color: red;
	@include action-resize {
		transform: scale(1.2, 1.2);
	}
}
```

?> Mixins can also be used for easing and animations

### More

- You can read more about nesting at the [official website](https://sass-lang.com/documentation/at-rules/mixin/)
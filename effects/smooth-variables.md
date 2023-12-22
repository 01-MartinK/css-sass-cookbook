# Smooth between variables

To smooth between different variable values like height or color, you can use [mixins](Sass/Mixins) as a way of smoothing them.

A simple mixin for smoothing between the default button values and then the hover values would be:

<!-- tabs:start -->

#### **Sass**

```css
@mixin smooth($time) {
    transition: all $time ease-in-out;
}

.btn {
	background-color: greenyellow;
	border: 1px solid black;

	box-shadow: none;
	border-radius: 4px;
	@include smooth(0.5s);
	&:hover {
		border: 2px solid gray;
		box-shadow: 0 0 4px gray;
	}
}
```

> You can give the mixin a time, ease or value argument for better control.
#### **CSS**

With CSS you will have to call a the variable change directly in the css selector.

```css
.btn {
	background-color: greenyellow;
	border: 1px solid black;

	box-shadow: none;
	border-radius: 4px;
	transition: border 2s, box-shadow 2s;
}

.btn:hover {
	border: 2px solid gray;
	box-shadow: 0 0 4px gray;
}
```

<!-- tabs:end -->

[](../examples/smooth-button.html ':include :type=iframe width=100px height=70px')

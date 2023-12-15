# Variables

Variables in pure CSS is kind of wonky. You can only declare them inside classes or properties.

``` css
.container {
	--main-bg-color: wheat;
}

@property --logo-color {
	syntax: "<color>";
	inherits: false;
	initial-value: #c0ee21;
}
```

You can reference the property with the `var()` field.

``` css
.logo {
	background-color: var(--logo-color);
}
```

When declaring a variable you must keep in mind that if the variable is declared in an elements child the parent can't access it. 

```
- Container (Can't Access It )
	- Element1
	- Element2 (Declare Variable)
		 - Element5	(Can Access It)
	- Element3
```

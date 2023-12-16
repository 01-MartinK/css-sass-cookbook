# Fade-In-Out


## Fade

To fade in from a certain point you can change the opacity dynamically. To call the animation you can make a class or a separate mixin.

<!-- tabs:start -->

#### **Scss**

In scss you can skip the class entirely with a custom mixin that contains the class data originally.

```css
@mixin fade-anim {
  animation-name: fade-top;
  animation-fill-mode: both;
  animation-duration: 0.5s;
  visibility: visible;
}

.fade {
    @include fade-anim;
}

@keyframes fade-in {
  0% { opacity: 0; transform: translateY(-32px); }
  100% { opacity: 1; transform: translateY(0px);}
}
```

?> You could animate the whole thing in a mixin aswell

#### **CSS**

In css you should have a class to put on the element that toggles the animation.

```css
.fade-class {
  animation-name: fade-top;
  animation-fill-mode: both;
  animation-duration: 0.5s;
  visibility: visible;
}

@keyframes fade-in {
  0% { opacity: 0; transform: translateY(-32px); }
  100% { opacity: 1; transform: translateY(0px);}
}
```

<!-- tabs:end -->

[](../examples/fade.html ':include :type=div width=180px height=120px')

## Fade when on Screen

The element automatically fades the moment the page loads. If for example you want it to fade when it is visible you could use a module, if you are using a js framework.

If you are not using a [framework](../sass/main.md/Usage) this should also work even though it is extremely simple. It uses the BoundingClientRect to get the position of the element.

```js
function checkVisible(elm) {
  var rect = elm.getBoundingClientRect();
  var viewHeight = Math.max(document.documentElement.clientHeight, window.innerHeight);
  return !(rect.bottom < 0 || rect.top - viewHeight >= 0);
}
```
!> It may be broken here due to it being a iframe!

[](../examples/fade-on-screen.html ':include :type=iframe width=180px height=120px')

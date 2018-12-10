# About

- Super lean CSS grid system based on floats
- Strong cross browser support
- Tested on IE9+, floats work as far back as IE6, but you still need media queries to make the grid responsive
- This is **not** meant to replace CSS Grid/Flexbox, but rather offer a solution for rapidly developing responsive layouts when support for older browser is required.

-------------
Working [demo](https://codepen.io/railaru/pen/yGyBmq?editors=1100 "demo")

-------------

### SCSS setup
```css
$columns: 12;
.row:after{
    content: "";
    display: block;
    clear: both;
}
@mixin generate-spans($device-size){
    @for $i from 1 through $columns{
        .span-#{$i}-#{$device-size}{
            width: 100% / $columns * $i;
            float: left;
        }
    }
}

$columns: 12;
.row:after{
    content: "";
    display: block;
    clear: both;
}
@mixin generate-spans($device-size){
    @for $i from 1 through $columns{
        .span-#{$i}-#{$device-size}{
            width: 100% / $columns * $i;
            float: left;
        }
    }
}

//mobile
@media (max-width: 640px){
    @include generate-spans(s);
}
//tablet
@media (min-width: 640px){
    @include generate-spans(m);
}
//desktop
@media (min-width: 1024px){
    @include generate-spans(l);
}

```

### HTML example usage
```html
<div class="row">
	<div class="span-6-s span-4-m span-4-l">

	</div>
	<div class="span-6-s span-4-m span-4-l">

	</div>
	<div class="span-6-s span-4-m span-4-l">

	</div>
</div>
```

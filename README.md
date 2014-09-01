# SassyBreakpoint

A simple ***breakpoint mixin*** is just all you need!

### Required

- Sass 3.3 and up
- Bower `npm install -g bower`

### Installation
```ssh
bower install sassybreakpoint
```

### Settings
```scss
// _Variables.scss
// based on Foundation 5 Framework

$sf-screen: "only screen" !default;

$sf-small-up: $sf-screen !default;
$sf-small-only: "#{$sf-screen} and (max-width: #{upper-bound($sf-small-range)})" !default;

$sf-medium-up: "#{$sf-screen} and (min-width:#{lower-bound($sf-medium-range)})" !default;
$sf-medium-only: "#{$sf-screen} and (min-width:#{lower-bound($sf-medium-range)}) and (max-width:#{upper-bound($sf-medium-range)})" !default;

$sf-large-up: "#{$sf-screen} and (min-width:#{lower-bound($sf-large-range)})" !default;
$sf-large-only: "#{$sf-screen} and (min-width:#{lower-bound($sf-large-range)}) and (max-width:#{upper-bound($sf-large-range)})" !default;

$sf-breakpoints: (
    "small": $sf-small-up,
    "small-only": $sf-small-only,

    "medium": $sf-medium-up,
    "medium-only": $sf-medium-only,

    "large": $sf-large-up,
    "large-only": $sf-large-only
) !default;

```


### How to use

Scss:
```scss
// create 3 breakpoints for aside
aside {
  @include sf-breakpoint("small-only"){
      width: 100%;
      content: "small-only";
  }
  @include sf-breakpoint("medium-only"){
      width: 80%;
      content: "medium-only";
  }
  @include sf-breakpoint("large-only"){
      width: 30%;
      content: "large-only";
  }
}
```
Output:
```css
  @media only screen and (max-width: 40em) {
    aside {
      width: 100%;
      content: "small-only"; 
    } 
  }
  @media only screen and (min-width: 40.063em) and (max-width: 64em) {
    aside {
      width: 80%;
      content: "medium-only";
    } 
  }
  @media only screen and (min-width: 64.063em) and (max-width: 90em) {
    aside {
      width: 30%;
      content: "large-only";
    } 
   }
```

### SassyBreakpoint + SassyPlaceholder
You can extend any placeholder within a @media directive when combining it with [SassyPlaceholder](https://github.com/SassyFramework/SassyPlaceholder).


### License

The SassyBreakpoint is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)
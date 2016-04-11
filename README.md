# bootstrap-bidirectional
> Bi-directional Bootstrap SASS port supporting ltr, rtl and bidi without the need of alternative stylesheets or double-targetting styles.

## Features

- Configurable LTR, RTL or BIDI output.
- No style-sheet swapping when using Bi-directional support.
- No additional output when choosing LTR, minimal file-size growth on RTL/Bi-directional selection.
- Built upon [bootstrap SASS] (https://github.com/twbs/bootstrap-sass) enhanced with bi-directional functionality for LTR and RTL language support. 
- Fully compatible with [TWBS](http://getbootstrap.com/) `v.3.3.5`

![Sample output file](https://raw.githubusercontent.com/jbokkers/bootstrap-bidirectional/master/output.png)

## Usage

1. Open **_variables.scss** in `\assets\stylesheets\bootstrap`
2. Edit `$text-direction` variable on 2nd line
3. Select value either `LEFT` or `RIGHT` or `BIDI`
4. That's it.

### Usage
For the following css properties, we keep the phrasing `left` and `right`.

```
.testclass {
    // left or right are still used as they are used to signify the position
    @include clear(left);
    @include float(left);
    @include text-align(left);
}
```

For all others, `left` become `push` (pushing against the box-model) and `right` become `pull` (pulling away from the box-model)
```
.testclass {
    @include push(0); // 
    @include pull(10px);
    @include padding-push(10px);
    @include padding-pull(5px);
    @include padding-horz(5px, 6px);
    @include margin-push(5px);
    @include margin-pull(5px);
    @include margin-horz(5px, 6px);
    @include border-push(1px solid);
    @include border-push-color(red);
    @include border-push-style(solid);
    @include border-push-width(1px);
    @include border-pull(1px solid, 2px dashed);
    @include border-pull-color(red, blue);
    @include border-pull-style(solid, dotted);
    @include border-pull-width(1px, 2px);
    @include border-top-push-radius(2px 1px);
    @include border-top-pull-radius(2px 1px);
    @include border-bottom-push-radius(2px 1px);
    @include border-bottom-pull-radius(2px 1pxm);
    @include background-position(20%, 50%);
}
```

### Sample input
The following example shows the output of below sass (for example purposes, variable is scoped).

```
.testleft {
$text-direction: "left";
    @include margin-push(5px);
}
.testright {
$text-direction: "right";
    @include margin-push(5px);
}
.testbidi {
$text-direction: "bidi";
    @include margin-push(5px);
 }
```

The output generated:

```
.testleft {
  margin-left: 5px; }
  
.testright {
  margin-right: 5px; }

[dir="ltr"] .testbidi {
  margin-left: 5px; }

[dir="rtl"] .testbidi {
  margin-right: 5px; }

```

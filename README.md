# bootstrap-bidirectional
Bi-directional Bootstrap SASS port supporting ltr, rtl and bidi


## Bootstrap

[bootstrap SASS] (https://github.com/twbs/bootstrap-sass) enhanced with bi-directional functionality for LTR and RTL language support. 

[TWBS](http://getbootstrap.com/) used as a core for grid and components v.3.3.5.

## Features

- Fully compatible with Bootstrap v3.3.5
- Configurable LTR, RTL or BIDI output.
- No style-sheet swapping when using Bi-directional support.
- No additional output when choosing LTR, minimal file-size growth on RTL/Bi-directional selection.

## Usage

1. Open _variables.scss in \assets\stylesheets\bootstrap;
2. Edit `$text-direction` variable on 2nd line
3. Select value either `LTR` or `RTL` or `BIDI`
4. That's it.

![Sample output file](https://raw.githubusercontent.com/jbokkers/bootstrap-bidirectional/master/output.png)
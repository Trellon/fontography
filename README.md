# fontography
SASS font registry. Stores a precise list of fonts for use in a project.

The font registry allows you to apply set of styles across an entire project efficiently and manage all of them in a single location.

# Usage

    // Declare a font style.
    @include fontography-register-style(
      $fonto-style-name:  'some-style',
      $fonto-style-color:  #CCC,
      $fonto-style-size:   1em,
      $fonto-style-lines:  1,
      $fonto-style-family: 'sans-serif',
      $fonto-style-weight: 500
    );
    
    // Use it in your stylesheets.
    div.some-text {
      @include fontography('some-style');
    }
    
    // This will generate the identical font styles whenever the name is called.
    div.some-other-text {
      @include fontography('some-style');
    }

    // This will fail without error since the font style does not exist.
    div.some-other-text {
      @include fontography('style-some');
    }

# Default variables

<table>
  <tr>
    <th>Variable</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>$fonto-engine</td>
    <td>Sets the engine. Tells fontography to use sass-maps or extend statements for generating the maps. Valid values are 'maps' and 'extend.' Defaults to 'extend.'</td>
  </tr>
  <tr>
    <td>$fonto-name</td>
    <td>Default name for styles when calling fontography. Defaults to 'normal.'</td>
  </tr>
  <tr>
    <td>$fonto-color</td>
    <td>Override the color of a font when called fontography. Defaults to false.</td>
  </tr>
  <tr>
    <td>$fonto-debug</td>
    <td>Print the name of the selected font style in the CSS every time fontography is called. Useful for debugging. Defaults to false.</td>
  </tr>
  <tr>
    <td>$fonto-style-some-CSS-style</td>
    <td>Used to set font properties in fontography-register-style. Each value defaults to false.</td>
  </tr>
  <tr>
    <td>$fonto-style-hover-some-CSS-style</td>
    <td>Used to set font properties in fontography-register-style when an element is hovered over. Each value defaults to false.</td>
  </tr>
  <tr>
    <td>$fonto-style-active-some-CSS-style</td>
    <td>Used to set font properties in fontography-register-style when an element is in an active state. Each value defaults to false.</td>
  </tr>
  <tr>
    <td>$fonto-style-focus-some-CSS-style</td>
    <td>Used to set font properties in fontography-register-style when an element is in in focus. Each value defaults to false.</td>
  </tr>
</table>

# Supported Font Properties

Each property is supported in hover, focus and active states.

* color
* size
* lines
* family
* weight
* text-decoration
* text-transform
* letter-spacing
* font-style
* padding
* margin
* text-align
* text-shadow
* border-top
* border-bottom
* border-left
* border-right

# FAQ

### What is the benefit of organizing all your font styles in a single file?

It means you only have to go one place to change the way fonts are handled in a project.

### Why not just use extend statements?

Giant blocks of selectors in SASS makes it unreadable. The sass-maps engine consistently applies styles to multiple places in the stylesheets.

### But you do use extend statements, by default.

Yep. But it's easy to switch to sass-maps, when you have a rendering engine that supports them. 



    
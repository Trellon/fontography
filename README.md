# fontography
SASS font registry. Stores a precise list of fonts for use in a project.

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
</table>

# Supported Font Properties

    
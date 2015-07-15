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
    
    // Use it in your theme.
    div.some-text {
      @include fontography('some-style');
    }

    
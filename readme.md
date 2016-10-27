#SASS

##Variables

Example variable declaration:

$nameofvar: value;

value can be colors units or lists

##Operations

Example font-size: 4px + 4;   

// 8

works intuitively and follows PEMDAS

##Color Functions

Example lighten

color: lighten(10%, color);

##Other Functions

Example quote

$quoted: quote($sometext)

##String Interpolation

Example

$root: '/images/'

\#form{
  background: url('#{$root}background.jpg');
}

background becomes url('/images/background.jpg')

Example2

$name: 'my-class';

.#{$name}{
  color: blue;
}

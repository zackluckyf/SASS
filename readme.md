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

Example 2

$name: 'my-class';

.#{$name}{
  color: blue;
}

##Nested rules

Example

nav{
  font-size: $base-font-size;
  font-weight: bold;
  float: right;
  ul{
    list-style-type: none;
    li{
      float: left;
      margin: 2px;
    }
  }

Example 2 with & for parent selector to attach to parent

a{
  text-decoration: none;
  &:hover{
    text-decoration: underline;
  }
}

Example 3 with nested properties
.button{
  font:{
    family: Verdana, Helvetica, sans-serif;
    size: 14px;
  }
}

##Extend

Example

.button {
  color: Black;
}

.submit-button{
  \@extend .button;
  border: 1px Black solid;
}

##Mixin

Example

\@mixin font-large{
  font:{
    size: 14px;
    family: sans-serif;
    weight: bold;
  }
}

\#form{
  \@include font-large;
}

Example 2 with parameters, supplied with optional default values

\@mixin rounded-corners-all($size: 5px){
  border-radius: $size;
  -webkit-border-radius: $size;
  -moz-border-radius: $size;
}

##Value Calculations

Example

$app-width: 900px;
\@function column-width($cols){
  \@return ($app-width / $cols) - ($cols * 5px);
}

##\@if

Example

h1{
  \@if $size > 14px{
    color: Blue;
  }
  \@else if $size < 14px{
    color: Red;
  }
  \@else{
    color: Green;
  }
}

##\@for

Example

$page-width: 1000px;

\@for $col from 1 through 4 {
  .col#{$col} {
    width: $page-width / $col;
  }
}

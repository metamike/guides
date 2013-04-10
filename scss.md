SCSS
====
The syntax for the CSS extension of SASS

Syntax
------
* Nesting

    ```
    #main p {
      color: black;
      .redbox {
        background-color: red;
      }
    }
    ```
* Reference parent selectors:

    ```
    a {
      &:hover { text-decoration: none; }
    }
    ```
* "Namespaces" are expanded:

    ```
    .funky {
      font: 2px/3px {
        family: fantasy;
      }
    }

* Basic arithmetic:

    ```
    1px + 1px -> 2px
    #777 + #888-> white
    ```
* Variables (scoping rules apply):

    ```
    $width: 5em;
    #main { width: $width; }
    ```
* Datatypes: numbers, strings, colors, booleans, null, and list (space- or comma-separated)
* Standard arithmetic expressions are fine (parens, etc), but beware of division since it's special in CSS
* Strings can be interpolated:

    ```
    $selector: something;
    body.firefox #{$selector}:before;
    ```
* Only assign a variable if it has not been assigned:

    ```
    $content: "First"; -> "First"
    $content: "Second" !default; -> "First"
    ```

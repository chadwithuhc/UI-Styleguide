# Modifiers

Components may have modifiers. Elements may have modifiers, too.

![](images/component-modifiers.png)

<br>

## Naming modifiers
Classnames for modifiers will be prefixed by two dashes (`--`).

  ```scss
  .like-button {
    &--wide { /* ... */ }
    &--short { /* ... */ }
    &--disabled { /* ... */ }
  }
  ```

## Element modifiers
Elements may also have modifiers.

  ```scss
  .shopping-card {
    &__title { /* ... */ }
    &__title--small { /* ... */ }
  }
  ```

## Dash prefixes
Dashes are the preferred prefix for modifiers.

  * It prevents ambiguity with elements.
  * A CSS class can only start with a letter, `_` or `-`.
  * Dashes are easier to type than underscores.

How do you deal with complex elements? Nest them.
[Continue →](nested-components.md)
<!-- {p:.pull-box} -->

# CSS structure

## One component per file
For each component, place them in their own file.

  ```scss
  /* css/components/_search-form.scss */
  .search-form {
    &__button { /* ... */ }
    &__field { /* ... */ }
    &__label { /* ... */ }

    // modifiers
    &--small { /* ... */ }
    &--wide { /* ... */ }
  }
  ```

## Use glob matching
In sass-rails and stylus, this makes including all of them easy:

  ```scss
  @import 'components/*';
  ```

## Avoid over-nesting
Use no more than 1 level of nesting. It's easy to get lost with too much nesting.

  ```scss
  /* ✗ Avoid: 3 levels of nesting */
  .image-frame {
    &__description {
      /* ... */

      &__icon {
        /* ... */
      }
    }
  }

  /* ✓ Better: 2 levels */
  .image-frame {
    &__description { /* ... */ }
    &__icon { /* ... */ }
  }
  ```

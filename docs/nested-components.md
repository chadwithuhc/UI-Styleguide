# Nested components

![](images/component-nesting.png)

```html
<div class="article-link">
  <div class="vote-box">
    ...
  </div>
  <h3 class="article-link_title">...</h3>
  <p class="article-link_meta">...</p>
</div>
```

Sometimes it's necessary to nest components. Here are some guidelines for doing that.

## Modifiers
A component may need to appear a certain way when nested in another component. Avoid modifying the nested component by reaching into it from the containing component.

```scss
.article-header {
  .vote-box__up { /* ✗ avoid this */ }
}
```

  Instead, prefer to add a modifier to the nested component and apply it from the containing component.

```html
<div class="article-header">
  <div class="vote-box--highlight">
    ...
  </div>
  ...
</div>
```

```scss
.vote-box {
  &--highlight {
   .vote-box__up { /* ... */ }
  }
}
```

## Simplifying nested components
Sometimes, when nesting components, your markup can get dirty:

```html
<div class="search-form">
  <input class="search-form__input" type="text">
  <button class="search-button search-button--large"></button>
</div>
```

You can simplify this by using your CSS preprocessor's `@extend` mechanism:

```html
<div class="search-form">
  <input class="search-form__input" type="text">
  <button class="search-form__submit"></button>
</div>
```

```scss
.search-form {
  &__submit {
    @extend .search-button;
    @extend .search-button--large;
  }
}
```

What about repeating elements like lists? Learn about Layouts.
[Continue →](layouts.md)
<!-- {p:.pull-box} -->

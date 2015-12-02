# Component File Structure

Components should be stored under a single components folder. This rule is true for all HTML, CSS, and JS files, in their respective folders. Different naming conventions apply based on file type.

  ## Basic Rules
  Before we get into each file type, let's talk basic rules.
  
  __✓ Each component has its own file__  
  We allow only one component per file. Modifiers are still considered part of one component.
  ```scss
  // Block
  .media-block {
  
    // Elements
    &__title { /* ... */ }
    &__body { /* ... */ }
    &__image { /* ... */ }
  
    // Modifiers
    &--card { /* ... */ }
    &--horizontal {
    
        // Modifier overrides
        .media-block__body { /* ... */ }
    
    }
  }
  ```
  
  __✓ Avoid over-nesting__  
  Since we want to be able to move elements around without requiring too much refactoring, a two-level nesting solution works best. More levels implies multiple nested elements.
  ```scss
  /* ✓ Better: 2 levels */
  .image-frame {
    &__description { /* ... */ }
    &__icon { /* ... */ }
  }
    
  /* ✗ Avoid: 3 levels of nesting */
  .image-frame {
    &__description {
      &__icon {
        /* ... */
      }
    }
  }
  ```

  __✓ Site specific components get their own folder__  
  Site specific components are defined as code that would not be reused on another site. For example, a component that is a locations list, directly calling the Locations model since it is on every page. Other examples could be reusable footers, disclaimer blocks, etc.
  ```
  // Site: Acme Corp
  components/acme/_locations_list.scss
  components/acme/_footer.scss
  components/acme/_disclaimer.scss
  ```
  
  __✓ Third-party specific components get their own folder__  
  Third-party component overrides should be included in a subfolder. A great example is MagnificPopup which has it's own styling, but we often create custom instances that need to be reused.
  ```
  // Third-party Module: MagnificPopup
  components/mfp/_infographic.scss
  components/mfp/_slideshow.scss
  ```


  ## CSS
  _SCSS_ files start with underscores. Dashes are ok if allowed.
  ```
  css/components/*
      _media_block.scss
      _boxed_container.scss
  ```
  Importing:
  ```scss
  /* Subfolder globbing */
  @import 'components/**/*';
  
  /* Fallback: Including each folder */
  @import 'components/*';
  @import 'components/mfp/*';
  ```
  
  ## JS
  Normal file naming. A file is not required if it's empty.
  ```
  js/components/*
      media_block.js
      block_container.js
  ```
  Importing:
  ```ruby
  # Rails Asset Pipeline
  //= require_tree ./components
  ```
  
  ## HTML
  The idea of separating the views is passing in pure data so we can include as partials.
  ```
  views/components/*
      media_block.html
      block_container.html
  ```
  Usage:
  ```ruby
  <%= render "components/badge", icon: "camera", text: "#{photos.size}  View All" %>
  ```

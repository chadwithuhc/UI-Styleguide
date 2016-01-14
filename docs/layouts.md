# Layouts

![](images/layouts.png)

## Positioning Properties

Components should be made in a way that they're reusable in different containers. For that reason, we want to reserve positioning properties for Layouts:

  * Positioning (`position`, `top`, `left`, `right`, `bottom`)
  * Floats (`float`, `clear`)
  * Margins (`margin`)
  * Dimensions (`width`, `height`)
  * Media Queries (`@media (...)`)

This allows our components to be reusable in various layouts without excessive overrides since positioning is most commonly overridden CSS style.

A few __Exceptions__ exist though:

__Margin__  
Basic margins for stacked items in a normal page flow. For example, a bottom margin on a button, unordered list, etc.

__Fixed Dimensions__  
Elements that have fixed width/heights, such as **avatars** and **logos**, are allowed to have set values.

## Define positioning in parents

If you need to define positioning, try to define them in whatever context they will be in. In this example below, notice that the widths and floats are applied on the *list* component, not the component itself.

  ```scss
  // In this example, `.article-list` is considered a container component
  //   It can have it's own positioning properties in a layout if needed
  .article-list {
    .article-card {
      width: 33.3%;
      float: left;
    }
  }
  ```

Now if we needed to adjust positioning on the list component, we can do it in the layout styles. Changes made to layouts will be stored in the page-specific CSS (E.g.`articles.css`).

These are still written in BEM style with the page name as the root element:

  ```scss
  .articles-page__recent-articles {
    /* ... */
    
    .article-list {
      width: 25%;
      float: right;
    }
  }
  ```

Just want to add a quick change to color, spacing, etc.? Try it with Helpers.
[Continue →](helpers.md)
<!-- {p:.pull-box} -->

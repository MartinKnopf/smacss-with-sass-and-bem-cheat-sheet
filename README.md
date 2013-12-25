cheat sheet for smacss with sass
==================

## Pattern

  ```html
  <div class="base-block--specific-block">
    <div class="specific-block__element">
      <div class="element">...</div>
      <div class="element is-active">...</div>
      <div class="element--is-last">...</div>
    </div>
  </div>
  ```
  
  **state.scss**
  ```css
  .is-active {
    /*general state style*/
  }
  ```
  
  **base-block.scss**
  ```css
  .base-block {
    ...
  }
  
  .specific-block {
    @extend .parent;
    ...
  }
  
  .specific-block__element {
    /*layout of sub module '.element'*/
  }
  ```
  
  **element.scss**
  ```css
  .element {
    /*style of sub module '.element'*/
  }
  
  .element--is-last {
    /*element specific state*/
  }
  ```

## File structure
  ````
  style
  ├── base
  │   ├── fonts.scss
  │   ├── colors.scss
  ├── states
  │   ├── states.scss
  ├── modules
  │   ├── block.scss
  │   ├── element.scss
  ```

## sources
  * [SMACSS](http://smacss.com/)
  * [BEM](http://bem.info/)
  * [How to Scale and Maintain Legacy CSS with Sass and SMACSS](http://webuild.envato.com/blog/how-to-scale-and-maintain-legacy-css-with-sass-and-smacss/)
  * [Objects in Space - A style-guide for modular SASS development using SMACSS and BEM.](https://medium.com/objects-in-space/f6f404727)

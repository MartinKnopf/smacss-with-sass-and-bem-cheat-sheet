smacss with sass and bem
=========

##pattern
```html
  <div class="vehicle--car">                  <!-- the style of a module -->
    <div class="vehicle--car__engine">        <!-- the layout of a nested module -->
      <div class="engine">...</div>           <!-- the style of a module -->
      <div class="engine is-active">...</div> <!-- module with global state -->
      <div class="engine--is-last">...</div>  <!-- module with module-specific state -->
    </div>
  </div>
```

##rules
* separate layout and style
* a module name contains the name of its base module
* a module is defined in its base module's css/sass file
* modules define **their own style** and the layout of nested modules
* global states are defined globally
* module specific states are defined inside the module

##what belongs where
```
css/
|-- base/
    |-- base.scss     body { ... }                              /*element styles*/
                      h1 { ... }
    |-- _fonts.scss
    |-- _colors.scss
    |-- _mixins.scss
|-- states/
    |-- states.scss   .is-active { ... }                        /*global state*/
|-- modules/
    |-- vehicle.scss  .vehicle { ... }                          /*style of module*/
                      .vehicle--car { @extend .vehicle; ... }   /*style of specific module*/
                      .vehicle--car__engine { ... }             /*layout of nested module*/
    |-- engine.scss   .engine { ... }                           /*style of another module*/
                      .engine--is-last { ... }                  /*module specific state*/
|-- main.scss                                                   /*imports all necessary sass files*/
```

##sources
based on [this article](https://medium.com/objects-in-space/f6f404727) by [Andrew Colclough](https://twitter.com/wtc) which refers to the following sources:
* [http://smacss.com/](http://smacss.com/)
* [http://bem.info/](http://bem.info/)
* [http://webuild.envato.com/blog/how-to-scale-and-maintain-legacy-css-with-sass-and-smacss/](http://webuild.envato.com/blog/how-to-scale-and-maintain-legacy-css-with-sass-and-smacss/)
* [https://medium.com/objects-in-space/f6f404727](https://medium.com/objects-in-space/f6f404727)

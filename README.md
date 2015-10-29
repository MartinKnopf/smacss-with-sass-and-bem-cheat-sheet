[cheat sheet for smacss with sass and bem](http://horsed.github.io/smacss-with-sass-and-bem-cheat-sheet/)
=========

#pattern
```html
  <div class="vehicle--car">
    <div class="vehicle--car__engine">
      <div class="engine">...</div>
      <div class="engine is-active">...</div>
      <div class="engine--is-last">...</div>
    </div>
  </div>
```

#rules
* a module name contains its base module's name
* a module is defined in its base module's css/sass file
* modules define their style and the positioning of nested modules
* global states are defined globally
* module specific states are defined inside the module

#directory structure
```
css/
|-- base/
|   |-- base.scss
|   |-- _fonts.scss
|   |-- _colors.scss
|   |-- _mixins.scss
|-- states/
|   |-- states.scss
|-- modules/
|   |-- vehicle.scss
|   |-- engine.scss
```

#file contents
```
states.scss
  .is-active { ... }                          /*global state*/
```
```
vehicle.scss
  .vehicle { ... }                            /*style of a module*/
  .vehicle--car { @extend .vehicle; ... }     /*style of a specific module*/
  .vehicle--car__engine { ... }               /*positioning of a nested module*/
```
```
engine.scss
  .engine { ... }                             /*style of another module*/
  .engine--is-last { ... }                    /*module specific state*/
```
#sources
based on [this article](https://medium.com/objects-in-space/f6f404727) by [Andrew Colclough](https://twitter.com/wtc) which refers to the following sources:
* [http://smacss.com/](http://smacss.com/)
* [http://bem.info/](http://bem.info/)
* [http://webuild.envato.com/blog/how-to-scale-and-maintain-legacy-css-with-sass-and-smacss/](http://webuild.envato.com/blog/how-to-scale-and-maintain-legacy-css-with-sass-and-smacss/)
* [https://medium.com/objects-in-space/f6f404727](https://medium.com/objects-in-space/f6f404727)

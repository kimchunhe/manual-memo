You can use this binginHandlers :

``` js
ko.bindingHandlers.readOnly = {
    update: function (element, valueAccessor) {
        var value = ko.utils.unwrapObservable(valueAccessor());
        if (value) {
            element.setAttribute("disabled", true);

        } else {
            element.removeAttribute("disabled");
        }
    }
};
```
In my html :
``` html
<input type="text" id="create-finess" class="form-control" data-bind="readOnly: _locked" />
```
Finaly in my JS :
```js
//Constructor of my view model

  function ViewModel(resx) {
       this._locked = ko.observable();
}

  // on init of the page i lock the input
 this._load = function () {
  this._locked(true);
}
```
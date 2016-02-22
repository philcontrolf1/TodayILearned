# How to upload a file in Angular

HTML:

```html
<input type="file" custom-on-change="uploadFile" />
```

JavaScript:

```javascript
angular.module('MyApp', [])
  .directive('customOnChange', function () {
    return {
      restrict: 'A',
      link: function (scope, element, attrs) {
        var onChangeHandler = scope.$eval(attrs.onCustomChange);
        element.bind('change', onChangeHandler);
      }
    };
  })
  .controller('MyController', function ($scope) {
    $scope.uploadFile = function (event) {
      var file = event.target.files[0];
      var reader = new FileReader();
      reader.onload = function (evt) {
        // File contents available as evt.target.result
      };
    };
  })
```

(Not my original work, but can't find the source right now).

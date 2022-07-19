# AngularJS

## Incluir em uma página HTML

```<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular.min.js"></script>```

## Diretivas

- ng-app
- ng-controller
- ng-model
- ng-bind
- ng-init

## Diretiva ng-bind

~~~html
<div ng-app="">
    <input type="text" ng-model="texto1"/>
    <p ng-bind="texto1"></p>
</div>
~~~

## Expressões

~~~html
<div ng-app="">
    <input type="text" ng-model="texto1">
    <p>{{texto1}}</p>
    <p>{{5 + 5}}</p>
</div>
~~~

## Modulos

~~~html
<div ng-app="myApp" ng-controller="myController">
    {{firstName + " " + lastName}}
</div>

<script>
    var app = angular.module("myApp", []);
    app.controller("myController", function ($scope) {
        $scope.firstName = "Maurício";
        $scope.lastName = "Rocha";
    });
</script>
~~~

## Controllers

~~~html

~~~

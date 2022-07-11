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

## Controllers

~~~html
<div ng-app="minhaAplicacao" ng-controller="minhaController">
    <input type="text" ng-model="texto1"> <br>
    <span>{{'Bom dia ' + texto1}}</span>
</div>

<script>
    var app = angular.module('minhaAplicacao', []);
    app.controller('minhaController', function ($scope) {
        $scope.texto1 = "Mauricio";
    });
</script>
~~~





## aaa

~~~html

~~~

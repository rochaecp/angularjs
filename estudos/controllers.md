# AngularJS - Controllers

- Adicionando uma Controller

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
	
- Adicionando uma Controller e uma Diretiva

    ~~~html
    <div ng-app="myApp" ng-controller="myController">
        <minha-diretiva></minha-diretiva>
    </div>

    <script>
        var app = angular.module("myApp", []);

        app.controller("myController", function ($scope) {
            $scope.firstName = "Maurício";
        });

        app.directive("minhaDiretiva", function () {
            return {
                template: "<p>Bem vindo <b>{{firstName}}</b></p>"
            };
        });
    </script>
    ~~~

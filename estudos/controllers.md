# AngularJS - Controllers

## Exemplos

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
    
- Adicionando Métodos

	~~~html
    <div ng-app="myApp" ng-controller="myController">
        <h1 ng-click="changeName()">{{firstName}}</h1>
    </div>

    <script>
        var app = angular.module("myApp", []);

        app.controller("myController", function ($scope) {
            $scope.firstName = "Maurício";
            $scope.changeName = function () {
                $scope.firstName = "Rocha";
            };
        });
    </script>
	~~~
	
- Controllers em arquivos externos

	- Arquivo: index.html

		~~~html
		<div ng-app="myApp" ng-controller="myController">
		    <p>{{fullName()}}</p>
		</div>

		<script src="controller.js"></script>
		~~~	

	- Arquivo: controller.html

		~~~html
		var app = angular.module("myApp", []);
		app.controller("myController", function ($scope) {
		    $scope.firstName = "Maurício";
		    $scope.lastName = "Rocha";
		    $scope.fullName = function () {
		        return $scope.firstName + " " + $scope.lastName;
			};
		});
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

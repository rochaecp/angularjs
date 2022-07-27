# AngularJS

## Exemplos

- Diretiva ng-bind

    ~~~html
    <div ng-app="">
        <input type="text" ng-model="texto1"/>
        <p ng-bind="texto1"></p>
    </div>
    ~~~

- Expressões

    ~~~html
    <div ng-app="">
        <input type="text" ng-model="texto1">
        <p>{{texto1}}</p>
        <p>{{5 + 5}}</p>
    </div>
    ~~~

- Repetindo elementos HTML

    - Lista de Strings

        ~~~html
        <div ng-app="" ng-init="names=['Mauricio', 'Maria', 'Joana']">
            <ul>
                <li ng-repeat="x in names">{{x}}</li>
            </ul>
        </div>
        ~~~

    - Lista de Objetos

        ~~~html
        <div ng-app="" ng-init="pessoas=[
                {nome: 'Mauricio', idade: 30},
                {nome: 'Maria', idade: 27},
                {nome: 'Joana', idade: 22}]">
            <ul>
                <li ng-repeat="x in pessoas">{{x.nome + ' ' + x.idade}}</li>
            </ul>
        </div>
        ~~~

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

- Adicionando uma Diretiva

    - Com Nome do Elemento e com Atributo

        ~~~html
        <div ng-app="myApp">
            <minha-diretiva></minha-diretiva>       <!-- Nome do Elemento -->
            <div minha-diretiva></div>              <!-- Atributo -->
        </div>

        <script>
            var app = angular.module("myApp", []);
            app.directive("minhaDiretiva", function () {
                return {
                    template: "<h3>Diretiva criada com AngularJS</h3>"
                };
            });
        </script>
        ~~~

    - Com uma Classe

        ~~~html
        <div ng-app="myApp">
            <div class="minha-diretiva"></div>      
        </div>

        <script>
            var app = angular.module("myApp", []);
            app.directive("minhaDiretiva", function () {
                return {
                    restrict: 'C', // permite invocar a diretiva a partir do nome da classe
                    template: "<h3>Diretiva criada com AngularJS</h3>"
                };
            });
        </script>
        ~~~

    - Com um Comentário

        ~~~html
        <body ng-app="myApp">
            <!-- directive: minha-diretiva -->
            <script>
                var app = angular.module("myApp", []);
                app.directive("minhaDiretiva", function () {
                    return {
                        restrict: 'M', // permite invocar a diretiva a partir do nome da classe
                        replace: true, // torna comentário visível
                        template: "<h3>Diretiva criada com AngularJS</h3>"
                    };
                });
            </script>
        </body>
        ~~~

- Adicionando uma Diretiva e uma Controller

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

- Validação de E-mail

    ~~~html
    <form ng-app="" name="myForm">
        E-mail:
        <input type="email" name="myEmail" ng-model="email"/>
        <span ng-show="myForm.myEmail.$error.email">E-mail inválido</span>
    </form>
    ~~~
    
- Application Status

    ~~~html
    <form ng-app="" name="myForm" ng-init="email='mauricio@gmail.com'">
        E-mail:
        <input type="email" name="myEmail" ng-model="email" required />
        <h4>Status:</h4>
        <p>Campo válido:            {{myForm.myEmail.$valid}}</p>
        <p>Campo foi modificado:    {{myForm.myEmail.$dirty}}</p>
        <p>Campo em foco:           {{myForm.myEmail.$touched}}</p>
    </form>
    ~~~
    
- CSS: classe ng-invalid

    ~~~html
    <style>
        input.ng-invalid {
            background-color: darksalmon;
        }
    </style>
    <body>
        <form ng-app="" name="myForm">
            <input type="text" name="myText" ng-model="firstName" required>
        </form>
    </body>    
    ~~~
    
    

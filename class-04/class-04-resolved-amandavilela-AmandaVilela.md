# AngularJS 1 - Aula 04 - Exercício

Nome: Amanda Vilela

Github: amandavilela

Data: 03/07/2016 - 17:18

## 1- Adicionar mais 1 campo em todos os Controllers e utlizar ele em orderBy.

## 2- Utilizar esse valor adicional no ng-init para cada ng-repeat da View.

## 3- Criar um filtro para cada ng-repeat.

```
<!DOCTYPE html>
<html data-ng-app="BeMEAN">
  <head>
    <meta charset="utf-8">
    <title>Exercicio 4</title>
  </head>
  <body>
    <section data-ng-controller="UserController as User" data-ng-init="predicate = 'id'">
      <h1>{{ User.titulo }}</h1>
      <label><input ng-model="searchUser" placeholder="Busca"></label>
      <table>
        <thead>
          <tr>
            <th data-ng-repeat="(key, value) in User.users[0]">{{ key }}</th>
          </tr>
        </thead>
        <tbody>
          <tr data-ng-repeat="user in User.users | orderBy:predicate | filter:searchUser">
            <td data-ng-repeat="(key, value) in user"> {{ value }}</td>
          </tr>
        </tbody>
      </table>
      <div data-ng-controller="CursoController as Curso" data-ng-init="predicate = 'id'">
        <h2>{{ Curso.titulo }}</h2>
        <label><input ng-model="searchCurso" placeholder="Busca"></label>
        <table>
          <thead>
            <tr>
              <th data-ng-repeat="(key, value) in Curso.cursos[0]">{{ key }}</th>
            </tr>
          </thead>
          <tbody>
            <tr data-ng-repeat="curso in Curso.cursos | orderBy:predicate | filter:searchCurso">
              <td data-ng-repeat="(key, value) in curso"> {{ value }}</td>
            </tr>
          </tbody>
        </table>
      </div>
      <div data-ng-controller="ProfessorController as Professor" data-ng-init="predicate = 'id'">
        <h2>{{ Professor.titulo }}</h2>
        <label><input ng-model="searchProfessor" placeholder="Busca"></label>
        <table>
          <thead>
            <tr>
              <th data-ng-repeat="(key, value) in Professor.professores[0]">{{ key }}</th>
            </tr>
          </thead>
          <tbody>
            <tr data-ng-repeat="professor in Professor.professores | orderBy:predicate | filter:searchProfessor">
              <td data-ng-repeat="(key, value) in professor"> {{ value }}</td>
            </tr>
          </tbody>
        </table>
      </div>
  </section>
  <script type="text/javascript" src="js/angular.min.js"></script>
  <script type="text/javascript">
  angular.module('BeMEAN', [])
    .filter("maioridade", function() {
      return function (age) {
        if (age) {
          if (age >= 18) return "maior de idade";
          if (age < 18 ) return "menor de idade";
          else return "idade inválida";
        }
      }
    })
    .controller('UserController', UserController)
    .controller('CursoController', CursoController)
    .controller('ProfessorController', ProfessorController);

    function UserController() {
      var vm = this;
      vm.titulo = "Be MEAN - Listagem dos usuários";
      vm.users = [
          {name: 'Suissa', email: 'suissera@manoveio.com', id: 1}
        , {name: 'João', email: 'joao@macioesedoso.com', id: 2}
        , {name: 'Franciele', email: 'fran@quimica.com', id: 3}
      ];
    }

    function CursoController() {
      var vm = this;
      vm.titulo = "Be MEAN - Listagem dos cursos";
      vm.cursos = [
          {name: 'Be MEAN', teacher: 'Suissa', id: 1}
        , {name: 'Learning Machine', teacher: 'Ivan Gustavo', id: 2}
        , {name: 'Laravel', teacher: 'Michael Douglas', id: 3}
      ];
    }

    function ProfessorController() {
      var vm = this;
      vm.titulo = "Be MEAN - Listagem dos professores";
      vm.professores = [
          {name: 'Suissa', age: 28, id: 1}
        , {name: 'John Papa', age: 34, id: 2}
        , {name: 'Nicholas Zakas', age: 35, id: 3}
      ];
    }
  </script>
  </body>
</html>

```

## 1 - Explique qual é a definição de MVC, MVVM e MVP

MVC: Model View Controller - Model é a camada de dados, Controller manipula os dados
e a View apresenta os dados.
MVVM: Model View ViewModel - ViewModel disponibiliza para a view uma lógica de
apresentaçao. As camadas Model e View se comunicam através da camada
ViewModel. ViewModel recebe notificaçao de eventos e realiza alguma açao.
MVP: Model View Presenter - Presenter faz a comunicaçao entre Model e View

## 2 - Crie uma aplicação com um nome e um form onde os dados colocados neles sejam mostrados logo abaixo, formatados.

<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.5.5/angular.min.js"></script>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" integrity="sha384-1q8mTJOASx8j1Au+a5WDVnPi2lkFfwwEAa8hDDdjZlpLegxhjVME1fgjWPGmkzs7" crossorigin="anonymous">
  <title>Ex 2</title>
</head>
<body data-ng-app="BeMEAN">
  <div class="container">
    <form class="">
      <div class="form-group">
        <label for="name">Nome: </label>
        <input type="text" class="form-control" name="name" data-ng-model="name">
      </div>

      <div class="form-group">
        <label for="postalCode">CEP: </label>
        <input type="text" class="form-control" name="postalCode" data-ng-model="postalCode">
      </div>

      <div class="form-group">
        <label for="street">Rua: </label>
        <input type="text" class="form-control"name="street" data-ng-model="street">
      </div>

      <div class="form-group">
        <label for="streetNo">Número: </label>
        <input type="text" class="form-control"name="streetNo" data-ng-model="streetNo">
      </div>

      <div class="form-group">
        <label for="complement">Complemento: </label>
        <input type="text" class="form-control"name="complement" data-ng-model="complement">
      </div>

      <div class="form-group">
        <label for="neighbourhood">Bairro: </label>
        <input type="text" class="form-control"name="neighbourhood" data-ng-model="neighbourhood">
      </div>

      <div class="form-group">
        <label for="city">Cidade: </label>
        <input type="text" class="form-control"name="city" data-ng-model="city">
      </div>

      <div class="form-group">
        <label for="state">Estado: </label>
        <input type="text" class="form-control"name="state" data-ng-model="state">
      </div>
    </form>

    <label>Endereço: </label> <br />
    {{name}} <br />
    {{street}} {{streetNo}} {{complement}} <br />
    {{neighbourhood}} <br />
    {{postalCode}} {{city}} - {{state}} <br />

  </div>

  <script>
    angular.module("BeMEAN", []);
  </script>
</body>
</html>

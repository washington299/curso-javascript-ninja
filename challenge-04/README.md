# Desafio da semana #4

```js
/*
Declare uma variável chamada `isTruthy`, e atribua a ela uma função que recebe
um único parâmetro como argumento. Essa função deve retornar `true` se o
equivalente booleano para o valor passado no argumento for `true`, ou `false`
para o contrário.
*/
var isTruthy = function myFunction(a) {
  if (a) {
    return true;
  } else {
    return false;
  }
}

// Invoque a função criada acima, passando todos os tipos de valores `falsy`.
isTruthy(null);
isTruthy(undefined);
isTruthy(0);
isTruthy(-0);
isTruthy('');
isTruthy(false);

/*
Invoque a função criada acima passando como parâmetro 10 valores `truthy`.
*/
isTruthy('0');
isTruthy('Washington');
isTruthy(1);
isTruthy(-1);
isTruthy(true);
isTruthy('true');
isTruthy('false');
isTruthy(99999);
isTruthy(-99999);
isTruthy('99999');

/*
Declare uma variável chamada `carro`, atribuindo à ela um objeto com as
seguintes propriedades (os valores devem ser do tipo mostrado abaixo):
- `marca` - String
- `modelo` - String
- `placa` - String
- `ano` - Number
- `cor` - String
- `quantasPortas` - Number
- `assentos` - Number - cinco por padrão
- `quantidadePessoas` - Number - zero por padrão
*/
var carro = {
  marca: 'Honda',
  modelo: 'Fit',
  placa: 'QWE1234',
  ano: 2015,
  cor: 'Cinza',
  quantasPortas: 4,
  assentos: 5,
  quantidadePessoas: 0,
};

/*
Crie um método chamado `mudarCor` que mude a cor do carro conforme a cor
passado por parâmetro.
*/
function mudarCor(cor) {
  carro.cor = cor;
};

/*
Crie um método chamado `obterCor`, que retorne a cor do carro.
*/
function obterCor() {
  return carro.cor;
}

/*
Crie um método chamado `obterModelo` que retorne o modelo do carro.
*/
function obterModelo() {
  return carro.modelo;
}

/*
Crie um método chamado `obterMarca` que retorne a marca do carro.
*/
function obterMarca() {
  return carro.marca;
}

/*
Crie um método chamado `obterMarcaModelo`, que retorne:
"Esse carro é um [MARCA] [MODELO]"
Para retornar os valores de marca e modelo, utilize os métodos criados.
*/
function obterMarcaModelo() {
  return 'Esse carro é um ' + carro.marca + ' ' + carro.modelo;
}

/*
Crie um método que irá adicionar pessoas no carro. Esse método terá as
seguintes características:
- Ele deverá receber por parâmetro o número de pessoas entrarão no carro. Esse
número não precisa encher o carro, você poderá acrescentar as pessoas aos
poucos.
- O método deve retornar a frase: "Já temos [X] pessoas no carro!"
- Se o carro já estiver cheio, com todos os assentos já preenchidos, o método
deve retornar a frase: "O carro já está lotado!"
- Se ainda houverem lugares no carro, mas a quantidade de pessoas passadas por
parâmetro for ultrapassar o limite de assentos do carro, então você deve
mostrar quantos assentos ainda podem ser ocupados, com a frase:
"Só cabem mais [QUANTIDADE_DE_PESSOAS_QUE_CABEM] pessoas!"
- Se couber somente mais uma pessoa, mostrar a palavra "pessoa" no retorno
citado acima, no lugar de "pessoas".
*/
function adicionarPessoaNoCarro(pessoas) {
  if (carro.quantidadePessoas === carro.assentos) {
    return 'O carro já está lotado!';
  } else if (carro.quantidadePessoas + pessoas > carro.assentos) {
    var acentosVagos = carro.assentos - carro.quantidadePessoas;
    var pessoasQueCabem = acentosVagos === 1 ? 'pessoa' : 'pessoas';
    return 'Só cabem mais ' + acentosVagos + ' '+ pessoasQueCabem + '!';
  }
  carro.quantidadePessoas += pessoas;
  return 'Já temos ' + carro.quantidadePessoas + ' pessoas no carro!';
}

/*
Agora vamos verificar algumas informações do carro. Para as respostas abaixo,
utilize sempre o formato de invocação do método (ou chamada da propriedade),
adicionando comentários _inline_ ao lado com o valor retornado, se o método
retornar algum valor.

Qual a cor atual do carro?
*/
carro.cor // Cinza

// Mude a cor do carro para vermelho.
mudarCor('vermelho');

// E agora, qual a cor do carro?
// vermelho

// Mude a cor do carro para verde musgo.
mudarCor('verde musgo');

// E agora, qual a cor do carro?
// verde musgo

// Qual a marca e modelo do carro?
obterMarcaModelo();

// Adicione 2 pessoas no carro.
adicionarPessoasNoCarro(2);

// Adicione mais 4 pessoas no carro.
adicionarPessoasNoCarro(4);

// Faça o carro encher.
adicionarPessoasNoCarro(3);

// Tire 4 pessoas do carro.
carro.quantidadePessoas -= 4;

// Adicione 10 pessoas no carro.
adicionarPessoasNoCarro(10);

// Quantas pessoas temos no carro?
// 1
```

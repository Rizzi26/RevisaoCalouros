# Questões objetivas

**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro 

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log


**A alternativa correta será a letra a. Isso se dá pelo fato da  a variável x não ser definida anteriormente, gerando a saída "undefined"; portanto, a ordem em que a variável e o console.log são colocados faz total diferença. Algo parecido acontece com a segunda saída, porém, é apresentado um erro, pois não é possível acessar a definição de y, já que o console.log é colocado anteriormente ao let, que por sua vez, depende de informações em bloco para que funcione.**


**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

**A alternativa correta é a letra b, pois ela faz com que, se a for igual a 0 e b também for igual a 0, a resposta seja "Erro: número inválido", pois a soma de a e b seria igual a zero, e o objetivo dessa consicional é evitar exatamente que isso ocorra. Antes, apenas b foi definido, e por isso não atingia seu objetivo.**

______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

b) O código imprime 200.

c) O código imprime 50.

d) O código gera um erro.

**A resposta é letra b, pois há um erro na digitação: falta o elemento "break" para que a máquina entenda que, caso o console.log seja "eletrônico", como é pedido, a resposta "pare" no preco definido, ou seja 1000. Pela falta desse elemento, a próxima resposta que possui o break é apresentada no terminal, sendo ela 200.**

______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

d) 24

**Ao executar o código, é perceptível que são aplicados filtros para computar a resposta. O array conta com os números possíveis para serem colocados em x. Então, inicialmente todos números são multiplicados por dois, e aqueles que obtiverem como resultado um número maior que 5 passam para próxima etapa, sendo o caso de (3,4,5), que possum como resultado da multiplicação, respectivamente (6,8,10). Por fim, esses números são reduzidos à letras, que decretam o que será feito com os próximos números, que, no caso, será uma soma de (6,8,10), com o resultado 24.**


______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"]

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

**A resposta será letra c. Isso acontece porque a definição de list.aplice(1, 2, "abacaxi", "manga"); faz com que a variável de lista definida anteirormente seja modificada, de maneira que 2 elementos sejam substituídos por outros dois a partir do termo 1. Dessa maneira, ao reproduzir o console.log, aparecerá no terminal banana, abacaxi, manga e laranja, visto que abaxi e manga substituírmas os termos 1 e 2, que antes eram maçã e uva.**

______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.


**A resposta é a letra b, pois ambas as afirmativas estão corretas, mas a segunda afirmativa apenas explica a meneira como essa hereditariedade funciona no código, e não o porque da herança compartilhar métodos. Nesse sentido, a herança é um método de poo, que evita a repetição de códigos. as "classes filhas" são um compilado de informações da primeira classe, de maneira atualizada e com novas informações.**


______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

a) I e II são verdadeiras.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

**A reposta desssa questão é letra a, visto que quando "Class Funcionario extends Pessoa" é colocado no código para criar uma extensão (extends) à partir da classe mãe, denominada "Pessoa", e assim é feita uma relação que chama o método e acessa os atributos definidos em "Pessoa".**

______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

**A resposta é a letra b. Isso se dá a partir do estudo de Programação Orientada à Objeto, o qual conta com esse conceito de polimorfismo, que permite tratar objetos de diferentes classes de maneira semelhante. Portanto, a asserção é verdadeira.**

______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

**Resposta:**

```javaScript
function somaArray(numeros) {
    let soma = 0; // Não havia sido declarada a variável soma 

    for (let i = 0; i < numeros.length; i++) {  //Declaração da variável i, que lê todos números do array a partir das definições
        soma += 2 * numeros[i]; // Acumula as somas dos elementos de [i]
    }

    return soma;
}

console.log(somaArray([1, 2, 3, 4])); 
```




______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

```javascript
class Produto { //Criar classe mãe : Produto
  constructor(nome, preco) { //Criar parâmetros
    this.nome = nome; //Criar variável
    this.preco = preco;
  }

  calcularDesconto() { //Criar método para calcular desconto
    const novoPreco = this.preco * 0.9;  //Criar constante de novoPreco e definir modo a ser calculado
    console.log(`O produto ${this.nome} teve um desconto de 10% e agora custa R$ ${novoPreco.toFixed(2)}.`); //Resposta
    return novoPreco;
  }
}

class Livro extends Produto { //Criar classse filha: Livro
  calcularDesconto() {
    const novoPreco = this.preco * 0.8; //Criar nova maneira de calcular preco
    console.log(`O livro ${this.nome} teve um desconto de 20% e agora custa R$ ${novoPreco.toFixed(2)}.`);  //Resposta
    return novoPreco;
  }
}

const produto1 = new Produto("Amor às cegas", 40); //Definir o produto a ser analizado
produto1.calcularDesconto();
```
**Nesse contexto, a classe livro é uma extensão da classe produto, pois é um produto, mas com novas especificidades. Nesse caso, possui um novo desconto, de 20%. Ao nomear produto1, são definidos seus parâmetros, sendo eles o nome e o preço, Amor as cegas e 40 reais, respectivamente. Por uma questão de polimorfismo, o calcular desconto instanciado na classe Livro, sobrepõe o calcular desconto que foi colocado dentro de Produto. Por esse motivo, o console.log puxa a última vez em que calcularDesconto foi definido.**
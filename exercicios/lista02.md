# Questões objetivas

**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let p = 10;
let q = 3;
let r = 6;

let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado);

const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
}

console.log("O produto dos valores é:", produto);


```
Qual das seguintes alternativas melhor descreve o que o código faz?

**A) O código avalia a expressão booleana, imprime `true`, calcula o produto dos números na lista e imprime o resultado no console.**

B) O código avalia a expressão booleana, imprime `false`, calcula o produto dos números na lista e imprime o resultado no console.

C) O código avalia a expressão booleana, imprime `true` e, em seguida, verifica se o número 6 está na lista.

D) O código avalia a expressão booleana, imprime `false` e ordena os valores em ordem crescente.

**A resposta correta é a letra A, visto que, ao declarar a variável, colocou-se condições de verificação, e ao verificar e definir o console.log(resultado), sendo o mesmo nome da variável, será imprimida a resposta de "true" ou 'false", para caso as condições sejam cumpridas ou não. Nesse caso, as condições foram atendidas, e a impressão será true. No segundo caso, é declarada uma constante com um array de valores numéricos, e posteriormente, declarada uma variável produto, com o valor 1. O "for" foi utilizado para declarar uma função de contabilidade, que passa por todos números do array, e os multiplica, um a um, e o console.log imprimirá esse valor.**


______

**2)** O código a seguir contém duas funções que calculam o limite de crédito de um cliente com base nos seus gastos e na renda mensal.

```javascript
// Versão 1 da função de análise de crédito
function analisarCredito1() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    do {
        totalCompras += compras[i];
        i++;
    } while (limite >= totalCompras && i < compras.length);

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```

```javascript
// Versão 2 da função de análise de crédito
function analisarCredito2() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```
Se ambas as funções forem executadas com os valores fornecidos, qual será a saída exibida no console?

**A) Ambas as funções exibirão: 'Seu crédito foi aprovado. Saldo disponível: 400.'**

B) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -600.', enquanto analisarCredito2() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.'

C) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.', enquanto analisarCredito2() exibirá: 'Seu crédito foi aprovado. Saldo disponível: 100.'

D) Ambas as funções exibirão: 'Seu crédito foi aprovado Saldo disponível: 500.'

**A resposta é a letra A, visto que ambas funções possuem o memso objetivo, mas utilizam ferramentas diferrentes de loop.**
______

**3)** Considere o seguinte trecho de código em JavaScript:
```javascript
//EX03
const idade = 21;

if (idade >= 18 && idade < 60) {
  console.log("Você é um adulto!");
} else if (idade < 18) {
  console.log("Você é menor de idade!");
} else {
  console.log("Você está na melhor idade!");
}
```
Qual das seguintes alternativas melhor descreve o comportamento do código?

A) O código verifica se a idade indica um adulto ou um idoso e exibe a mensagem correspondente.

**B) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".**

C) O código verifica se a idade está entre 18 e 60 anos e, se for, imprime "Você é um adulto!". Se não estiver nesse intervalo, imprime "Você está na melhor idade!".

D) O código verifica se a idade é menor de 18, entre 18 e 60 ou acima de 60, imprimindo uma mensagem específica para cada caso.

**A alternativa correta é a letra B. Isso acontece pois são feitas condicionais em cadeia, então, caso a primeira condicional não seja atendida, outra condição é colocada, e caso ela não seja atendida, o valor será encaixado em "else", ou seja, todos núemros que não se enocntraram nas cindições anteriores obterão a mesma resposta.**
______

**4)** Qual será o resultado impresso no console após a execução do seguinte código?
```javascript
//EX04
var energiaDisponivel = 1200;
var bateriaExtra = 400;
var consumoDispositivos = [300, 600, 500, 200, 400];

for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];

    if (consumo <= energiaDisponivel) {
        console.log("Dispositivo " + (i+1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo;
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log("Dispositivo " + (i+1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo));
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel);
    } else {
        console.log("Dispositivo " + (i+1) + " não pode ser ligado. Energia insuficiente.");
    }
}
```

Escolha a opção que responde corretamente:

A)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 ligado com bateria extra. Energia restante: 0

Dispositivo 5 ligado. Energia restante: -200

B)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

C)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 400

Dispositivo 4 não pode ser ligado. Energia insuficiente.

**D)**
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado. Energia restante: 300

Dispositivo 3 ligado com bateria extra. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

**A resposta será letra D, visto que ela atende os requisitos apresentados, em que o consumo e a energia restante estão corretos e as condicionais são aplicadas da maneira que devem ser, então, quando a energia disponível se esgota, é ligada a bateria extra e quando a energia se esgota, aparece uma resposta de que a energia é insuficiente.**
______

**5)** Qual é a principal função do método update() em um jogo desenvolvido com Phaser.js?

Escolha a opção que melhor descreve seu propósito:

A) O método update() é responsável por carregar os assets do jogo antes da cena ser exibida.

**B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.**

C) O método update() renderiza todos os sprites na tela e garante que a física do jogo seja processada corretamente.

D) O método update() é chamado apenas uma vez após a criação da cena, sendo utilizado para configurar variáveis iniciais do jogo.

**A resposta é a letra B, já que o update serve exatamente pra isso: rodar enquanto a lógica for utilzada e até que haja algum evebto de parada.**
______

**6)** Qual é o principal objetivo do módulo Matter.js Physics em Phaser.js?

Escolha a opção que responde corretamente:

**A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.**

B) Gerenciar eventos de entrada do usuário, como cliques e toques na tela, permitindo movimentação de personagens.

C) Renderizar gráficos otimizados para jogos 2D e garantir uma taxa de quadros estável.

D) Criar animações automáticas para sprites e objetos interativos sem necessidade de programação de movimentação.

**A respota é a letra A, já que o módulo permite a utilização da física e seus parâmetros ou requisitos de aplicação.**

______

# Questões dissertativas

**7)** Uma loja online deseja implementar um sistema de classificação de pedidos com base no valor total da compra. O sistema deve determinar a categoria de um pedido com as seguintes regras:

```javascript

Pedidos abaixo de R$50,00 → "Frete não disponível!"

Pedidos entre R$50,00 e R$199,99 (inclusive) → "Frete com custo adicional!"

Pedidos de R$200,00 ou mais → "Frete grátis!"
```
Implemente um pseudocódigo que receba o valor total da compra e exiba a classificação correta do frete para o cliente.

```javascript
Frete(valorPedido)

If valorPedido <= 0 {
    retornar: "Valor Inválido!"
}
Else if  valorpedido < 50 {
    retornar: "Frete não disponível!" }
Else if valorPedido >= 50 e valorPedido <= 199.99 {
    retorna: "Frete com custo adicional!" }
Else{
    retorna: "Frete grátis!" }
```
______

**8)** Considere a implementação da classe base Veiculo em um sistema de modelagem de veículos. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Carro e Moto, que herdam da classe Veiculo, adicionando atributos específicos e métodos para calcular o consumo de combustível de um carro e de uma moto, respectivamente.

``` javascript
Classe Veiculo:
Atributos:

modelo
ano
Método Construtor(modelo, ano):

Define os valores dos atributos modelo e ano com os valores passados como parâmetro.
Método CalcularConsumo():
```
Implementação genérica para cálculo de consumo, a ser sobrescrita pelas subclasses.
Agora, implemente as classes Carro e Moto, garantindo que ambas herdem de Veiculo e possuam métodos específicos para calcular o consumo de combustível com base na quilometragem e eficiência do veículo.

``` javascript
Classe Carro que herda de Veeiculo:
Atributos Novos:

consumoKmPorL //Criei o parâmtro de quantos km por litro o carro faz

Método Construtor(modelo, ano, consumoKmPorL): //Chamar os parâmtros criados na classe mãe e o parâmetro criado na classe filha

Método CalcularConsumo(kilometragem):

kilometragem dividida pelo consumoKmPorL //Cálculo de consumo existente dentro do método calcular consumo


Classe Moto que herda de Veeiculo:
Atributos Novos:

consumoKmPorL //Criei o parâmtro de quantos km por litro a moto faz

Método Construtor(modelo, ano, consumoKmPorL): //Chamar os parâmtros criados na classe mãe e o parâmetro criado na segunda classe filha

Método CalcularConsumo(kilometragem):

kilometragem dividida pelo consumoKmPorL //Cálculo de consumo existente dentro do método calcular consumo
```
______

**9)** Você é um cientista da NASA e está ajudando no desenvolvimento de um sistema de pouso para sondas espaciais em Marte. Seu objetivo é calcular o tempo necessário para que a sonda reduza sua velocidade até um nível seguro para pouso, considerando uma velocidade inicial de entrada na atmosfera marciana e uma taxa de desaceleração constante causada pelo atrito atmosférico e retrofoguetes.

Entretanto, a sonda não pode ultrapassar um tempo máximo de descida para evitar desvios orbitais, nem pode desacelerar além de um limite mínimo, pois isso poderia causar instabilidade no pouso.

Implemente a lógica dessa simulação em pseudocódigo, considerando a seguinte equação para atualização da velocidade:

Considere a fórumla de atualização velocidade:
``` javascript
    velocidade = velocidadeInicial - desaceleracao * tempo
```
Seu programa deve determinar quanto tempo será necessário para que a sonda atinja uma velocidade segura de pouso, sem ultrapassar os limites estabelecidos.

```javascript
Criar variáveis:

velocidadeInicial = 900 m/s
velocidadeSeguranca = 10 m/s
desaceleracao = 20 m/s²
tempoMaximo = tempoMaximo
tempo = 0

update(){ // função de looping

    Se velocidadeInicial > velocidadeSegura e tempo < tempoMaximo deve ocorrer: {
        velocidadeInicial ← velocidadeInicial - (desaceleracao * 1)  // Atualiza a velocidade a cada segundo
        tempo ← tempo + 1  //Atualiza o tempo de 1 em 1 segundo
    }

        Se velocidadeInicial <= velocidadeSegura deve ocorrer: {
            Resposta: "Pouso seguro ocorreu em " + tempo + " segundos."
        }
        Senão ocorrer: {
            resposta: "Deu ruim!"
        }
}

resposta  oficial: Pouso seguro alcançado em 44.5 segundos.


```
______

**10)** Em um sistema de análise financeira, as operações de investimento de uma empresa podem ser representadas por matrizes, onde cada linha representa um tipo de investimento e cada coluna representa um período de tempo.

A seguir, é fornecida a implementação da função SomarMatrizesInvestimento(matrizA, matrizB), que soma os valores de duas matrizes de investimento. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação das matrizes de investimento, determinando como os investimentos afetam os resultados ao longo do tempo.

``` javascript
Função SomarMatrizesInvestimento(matrizA, matrizB):  
    # Verifica se as matrizes têm o mesmo número de linhas e colunas  
    Se tamanho(matrizA) ≠ tamanho(matrizB) então:  
        Retornar "As matrizes não podem ser somadas. Elas têm dimensões diferentes."  
    Senão:  
        linhas <- tamanho(matrizA)  
        colunas <- tamanho(matrizA[0])  
        matrizResultado <- novaMatriz(linhas, colunas)  

        # Loop para percorrer cada elemento das matrizes e calcular a soma  
        Para i de 0 até linhas-1 faça:  
            Para j de 0 até colunas-1 faça:  
                matrizResultado[i][j] <- matrizA[i][j] + matrizB[i][j]  

        Retornar matrizResultado  

# Exemplo de uso da função  
investimentosAno1 <- [[1000, 2000], [1500, 2500]]  
investimentosAno2 <- [[1200, 1800], [1300, 2700]]  

totalInvestimentos <- SomarMatrizesInvestimento(investimentosAno1, investimentosAno2)  
Escrever("Total de investimentos acumulados:")  
ImprimirMatriz(totalInvestimentos)  
```
Agora, implemente a função MultiplicarMatrizesInvestimento(matrizA, matrizB), que multiplica as duas matrizes, simulando o efeito de diferentes fatores de crescimento e impacto financeiro nos investimentos ao longo do tempo.

```javascript
Função MultiplicarMatrizesInvestimento(matrizA, matrizB)
#Verificar se o número de colunas da matrizA é igual ao número de linhas da matrizB

Se colunas(matrizA) ≠ linhas(matrizB) então:  
        Retornar "Impossível multiplicar, o número de colunas da matrizA deve ser, obrigatoriamnete, igual ao número de linhas da matrizB"
         Senão:  
        linhas <- linhas(matrizB)  
        colunas <- tamanho(matrizA[0])  
        matrizResultado <- novaMatriz(linhas(matrizB), colunas(matrizA))  

# Loop para percorrer cada elemento das matrizes e calcular a soma  
        Para i de 0 até linhas-1 faça:  
            Para j de 0 até colunas-1 faça:  
                matrizResultado[iB][jA] <- matrizA[j][i] * matrizB[i][j]
```
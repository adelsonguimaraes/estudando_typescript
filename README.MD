# Estudando TypeScript 😶‍🌫️
Neste projeto inicio o estudo mais focado de TypeScript, onde acompanho o curso da b7web e outros materiais como ferramenta base de conhecimento.


## O que é o TypeScript
TypeScript é um ``superset`` do ``JavaScript``, ou seja, com ele adicionamos novas funções ao ``JS``, para uma maior produtividade ao desenvolvimento, o ``TS`` não é reconhecido pelo navegador, foi criado apenas com o foco em desenvolvimento, então seu propósito maior é ser uma ferramenta de desenvolvimento e após o desenvolvimento estar finalizado proporcionar a ``transpilação`` para a linguagem ``JS`` proporcionando a leitura e interpretação do navegador ao que foi desenvolvido.

## Qual a vantagem de usar TypeScript
Se todo o código desenvolvido em ``TS`` no fim será transformado em ``JS``, então qual a real vantagem de utilizar?

A principal vantagem que o ``TypeScript`` se propoem a trazer é a ``Tipagem Estática``, quando falamos em ``JavaScript`` falamos de uma linguagem poderosa, porém, que possui uma tipagem fraca, ou seja, podemos atribuir multíplos valores a uma variável, a qualquer momento, então a linguagem não se preocupa em verificar qual o valor aceito na variável, o que acaba causando vários problemas durante e após o desenvolvimento.

É nessa ``fraqueza`` do ``JS`` que o ``TS`` foi criado, assim para suprir a necessidade de tipagem forte que faltava na linguagem, com isso, agora podemos desenvolver código com muito mais segurança e certeza de que ocorreram menos problemas derivados do tipo de valor atribuído a variável.

## Tipos de variáveis
Aqui vamos ver os principais tipos de variáveis que podemos utilizar no desenvolvimento com o ``TypeScript``

* ``any`` Utilizado para qualquer tipo de valor, utilizado geralmente quando o valor que será atribuído não possui um valor definido.
* ``string``: Utilizado para valores de texto
* ``number``: Utilizado para valores numéricos inteiros e decimais
* ``boolean``: Utilizado para valores de verdadeiro e falso
* ``array``: Utilizado para receber arrays como valor

## Atribuindo tipagem
Vamos entender agora como podemos definir um tipo de uma variável.

Para defiinir um tipo de variável é bem simples, inicialmente a variável deve ser criada de forma natural como já é feito em ``JS``
```javascript
let variavel
```

Em seguida vamos definir seu tipo, para isso de forma muito simples precisamos apenas colocar ``:tipo``, vejamos a baixo como funciona
```javascript
let variavel:string
```

Podemos também atribuir o valor que vai inicializar a variável caso seja necessário, o que podemos também fazer de forma muito simples
```javascript
let variavel:string = 'iniciando'
```

## Criando um array tipado
Vamos ver agora como criar um array com tipagem o que pode ser muito últil em determinados casos.

Para criarmos um array tipado baseado no que já vimos anteriormente basta adicionar ao lado do nosso tipo sinais de colchetes ``:tipo[]``, com isso todos os valores deveram obedecer a nossa tipagem, vamos ver um exemplo.
```javascript
let alfabeto:string[] = ['A','B','C','D']
```

Como vimos acima, todos os itens do nosso array devem obedecer a tipagem definida, qualquer valor que não obedeça essa tipagem irá gerar um erro.


## Comandos do transpilador TSC
Para transpilar um arquivo do tipo ``TS`` utilizamos os comandos do transpilador ``TSC``, abaixo vamos ver os principais comandos.

>Comando para transpilar um arquivo no mesmo local do ``.ts``

    tsc caminho/arquivo.ts

>comando para alterar a pasta onde o arquivo ``.js`` será gerado

    tsc caminho/arquivo.ts --outDir caminho_novo

>comando para transpilar apenas arquivo sem erros

    tsc caminho/arquivo.ts --noEmitOnError

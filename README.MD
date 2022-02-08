# Estudando TypeScript 😶‍🌫️
Neste projeto inicio o estudo mais focado de TypeScript, onde acompanho o curso da b7web e outros materiais como ferramenta base de conhecimento.


## 💣 O que é o TypeScript
TypeScript é um ``superset`` do ``JavaScript``, ou seja, com ele adicionamos novas funções ao ``JS``, para uma maior produtividade ao desenvolvimento, o ``TS`` não é reconhecido pelo navegador, foi criado apenas com o foco em desenvolvimento, então seu propósito maior é ser uma ferramenta de desenvolvimento e após o desenvolvimento estar finalizado proporcionar a ``transpilação`` para a linguagem ``JS`` proporcionando a leitura e interpretação do navegador ao que foi desenvolvido.

## 🤔 Qual a vantagem de usar TypeScript
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

## 🙃 Atribuindo tipagem
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

## 😯 Criando um array tipado
Vamos ver agora como criar um array com tipagem o que pode ser muito últil em determinados casos.

Para criarmos um array tipado baseado no que já vimos anteriormente basta adicionar ao lado do nosso tipo sinais de colchetes ``:tipo[]``, com isso todos os valores deveram obedecer a nossa tipagem, vamos ver um exemplo.
```javascript
let alfabeto:string[] = ['A','B','C','D']
```

Como vimos acima, todos os itens do nosso array devem obedecer a tipagem definida, qualquer valor que não obedeça essa tipagem irá gerar um erro.

## 🥸 Utilizando o tipo Any
Como vimos lá na área de tipos, temos um tipo chamado any que basicamente assume qualquer tipo, então quando utilizamos esse tipo, não precisamos nos preocupar em que tipo de valor estamos atribuindo a determinada variável pois ele irá permitir qualquer tipo de valor.

Mas quando devemos utilizar o tipo ``any``? 

Bem, o tipo ``any`` é uma forma de você poder permitir adicionar qualquer valor a uma variável tipada, ou seja, mesmo seguindo o padrão do ``ts`` que são variáveis tipadas, você pode ter uma variável que aceita qualquer valor.

No entanto, é importante impor o esforço de tipar as variáveis de forma correta a sua necessidade, o máximo possível, ainda assim, em alguns casos, acontecerá que não teremos como definir o valor exato que irá ser atribuído a uma variável, nesses casos extremos, podemos utilizar o tipo ``any`` para resolver.

## 😏 Tipando parâmetros de funções
Quando trabalhamos com funções também podemos tipar os parâmetros que iremos receber nessa função, para que os valores sejam atribuídos corretamente e nossas funcionalidades dentro do escopo da função funcione corretamente.

Novamente para atribuirmos um tipo a um parâmetro de uma variável é muito simples, praticamente identico ao que já vimos anterior mente, mudando apenas que agora adicionaremos o tipo após cada parâmetro da função, vejamos abaixo um exemplo.

```javascript
function concatenar(nome: string, idade: number) {
    return 'Nome: ' + nome + 'idade:' + idade
}
```

## 🤫 Tipando retorno de funções
De forma simples também podemos definir o tipo do retorno que uma determinada função deve ter, para isso apenas precisamos adicionar após o fechamento dos parênteses da função dois pontos seguidos do nosso tipo ``:tipo`` exatamente igual como definimos os tipos de variáveis, vejamos abaixo um modelo.
```javascript
function soma(n1:number, n2:number):boolean {
    return (n1+n2>0)
}
```


## 🤤 Tipagem Múltipla
Podemos também definir para uma determinada variável ``multi-tipagem``, ou seja, definir que a mesma variável aceita mais de um tipo de tipagem.

Diferente do tipo ``any`` que vimos anteriormente que aceita qualquer valor e que deve ser usado em casos onde não se sabe o tipo do dado que será atribuído, aqui, sabe-se bem o tipo ou os tipos de dados que será atribuídos a variável, e assim temos como atender a necessidade de uma variável aceitar mais de um tipo, vejamos como isso fica no modelo a baixo.
```javascript
let dados:string|number
```
De forma simples, para definir mais um tipo aceito pela mesma variável, basta adicionar após o primeiro tipo um sinal de pipe seguido do segundo tipo ``|number``, a partir de então a variável aceitará valores dois dois tipos, porém, continuará gerando erro em dados de tipos diferentes dos definidos.

## 😉 Tipando objetos - Type e Interface
Para tipar objetos não há segredos, tudo segue a mesma linha de reaciocínio que traçamos até agora, a grande diferença é que temos duas formas de tipar um objeto a primeira delas é criando um tipo personalizado, vamos ver um modelo.
```javascript
type User = {
    nome: string,
    idade: number,
    telefone: string|number
}
```

No modelo acima criamos um tipo personalizado onde nosso tipo ``User`` tem os atributos com sua tipagem definida, o a outra forma e a mais usada para definir a tipagem de um objeto é por ``Interfaces``, vejamos um modelo.
```javascript
interface User = {
    nome: string,
    idade: number,
    telefone: string|number
}
```

É idêntico ao ``type``, mudando apenas a definição para ``interface``.

## 🤯 Tipagem inteligente
O ``TypeScript`` possui inteligência o suficiente para saber qual tipo deve definir para uma variável de acordo com sua inicialização, mesmo que não seja sinalizado o tipo da variável.

Então com isso podemos entender que mesmo que não chegue-mos a definir um tipo pra uma determinada variável, o type script irá analisar nossas atribuições a está variável e automaticamente irá definir um tipo pra ela de forma intríseca, vamos ver um exemplo abaixo pra entender melhor.

```javascript
let numeros = ['dez', 'vinte', 30, 40]
```

Veja que no exemplo acima não definimos um tipo para a nossa variável ``numeros``, que recebe um array de valores que variam entre números e texto, baseado nessa atribuição de valores o ``TS`` será capaz de saber qual tipo ele deve definir pra nossa variável.

Analisando esse cenário podemos afirmar que nossa variável ``numeros`` aceita apenas array com valores tipados ``string`` ou ``number``.

Isso é muito legal, porém também pode se tornar um problema, por isso o recomendado é sempre definir qual o tipo é desejado em cada variável.

## 🤓 Especificando tipos - Type Assertions
Em alguns casos com o contexto inteligente do ``TS`` ocorrerá de ele assumir um tipo para um determinado objeto, porém que não conterá o atributo desejado a ser consultado.

Nesses casos precisamos informar ao ``TS`` o tipo exato que está manipulando para ele não gerar um erro, um exemplo disso é quando utilizamos o ``document.getElementById``, nesse caso ele intrinsecamente assumirá que o tipo será ``HTMLElement``, porém esse tipo não possui todos os atributos ou atributos específicos por exemplo o campo ``value``, isso porque este tipo pode ser qualquer elemento, por exemplo uma div.

Diante disso é necessário iformar o tipo correto para a sua definição e assim poder acessar os campos certos, ness exemplo temos que usar o tipo ``HTMLInputElement``, para fazer isso demos após o fim da função adicionar ``as Tipo``, vejamos como fica.
```javascript
let nome = getElementById('nome') as HTMLInputElement
```
 
## 🤭 Comandos do transpilador TSC
Para transpilar um arquivo do tipo ``TS`` utilizamos os comandos do transpilador ``TSC``, abaixo vamos ver os principais comandos.

>Comando para transpilar um arquivo no mesmo local do ``.ts``

    tsc caminho/arquivo.ts

>comando para alterar a pasta onde o arquivo ``.js`` será gerado

    tsc caminho/arquivo.ts --outDir caminho_novo

>comando para transpilar apenas arquivo sem erros

    tsc caminho/arquivo.ts --noEmitOnError

# Typescript Generics

## O que vamos aprender

Fala tryber, tudo certo? Hoje vamos aprender sobre uma das coisas mais legais do TypeScript: os tipos genéricos! Com eles, vamos poder deixar o nosso código mais flexível, mais seguro e mais fácil de reutilizar. E o melhor de tudo, vamos poder aplicar esses conceitos em situações do dia a dia, para tornar o nosso código melhor e mais eficiente. Então, vamos lá!

### Tópicos

- Introdução a tipos genéricos
- Utilização de tipos genéricos em funções
- Exemplos de tipos genéricos em arrays

## Você será capaz de

- Entender o que são tipos genéricos e como eles funcionam no TypeScript
- Criar e utilizar funções genéricas
- Aplicar conceitos de tipos genéricos em exemplos práticos

## Mas por que isso é tão importante?

Bem, os tipos genéricos são uma das ferramentas mais poderosas que temos para desenvolver software. Eles nos permitem escrever código mais flexível e mais seguro, evitando erros comuns e tornando o código mais fácil de manter. Além disso, como o TypeScript é baseado em tipos, entender como utilizar os tipos genéricos é fundamental para escrever código TypeScript de qualidade.

## Conteúdo

### Introdução a tipos genéricos

Mas o que são tipos genéricos? Basicamente, eles são tipos que podem ser aplicados a vários tipos diferentes. Isso significa que podemos escrever uma função genérica e, depois, utilizá-la com vários tipos diferentes. Isso é incrível, pois nos permite escrever código mais flexível e mais fácil de reutilizar.

Vamos começar com um exemplo simples, onde você deseja imprimir o valor de um argumento passado:

```typescript
  function print(valor: number) {
    console.log(valor);
  }

  print(5); // 5
```

Suponhamos que você queira tornar a função `print` mais flexível, permitindo que ela possa lidar com vários tipos de argumentos, como number, string e boolean. Uma forma de fazer isso seria escrevê-la da seguinte maneira:

```typescript
  function print(valor: number | string | boolean) {
    console.log(data);
  }

  print(5); // 5
  print("trybe"); // "trybe"
  print(true); // true
```

Imagine agora que você queira imprimir um array de números. Se você adicionar mais tipos diferentes a sua `print`, ela se tornará complicada de ser mantida. Aqui é onde os tipos genéricos se tornam úteis. Eles permitem que você escreva uma função flexível e fácil de ser mantida, que possa lidar com vários tipos de dados.

Mas como funcionam os tipos genéricos no TypeScript? Bem, é simples. Quando você cria uma função genérica, você define um ou mais parâmetros de tipo genérico. Esses parâmetros de tipo genérico são indicados com o símbolo <>.

Em outras palavras, os tipos genéricos funcionam como variáveis de tipo, armazenando o tipo de dado (como number, string ou boolean) que será usado. Dessa forma, você pode usar tipos genéricos para resolver o problema mencionado anteriormente, da seguinte forma:

```typescript
  function print<T>(valor: T) {
    console.log(valor);
  }

  print(5); // 5
  print("trybe"); // "trybe"
  print(true); // true
  print([1, 2, 3, 4, 5]) // [1, 2, 3, 4, 5]
  print({ musica: "Equalize", artista: "Pitty" }) // { musica: "Equalize", artista: "Pitty" }
```

Outro exemplo:

```typescript
  function maiorValor<T>(valor1: T, valor2: T): T {
    return valor1 > valor2 ? valor1 : valor2;
  }
```

Nesse exemplo, estamos usando o caractere `<T>` para especificar que essa função é genérica e pode ser usada com qualquer tipo. Depois, estamos usando esse tipo genérico T como o tipo dos parâmetros valor1 e valor2 e também como o tipo de retorno da função.

Agora, vamos ver como essa função pode ser usada com diferentes tipos. Por exemplo, podemos usá-la para comparar dois números inteiros:

```typescript
  const maiorNumero = maiorValor(10, 20);
  console.log(maiorNumero); // 20
```

Ou também podemos usá-la para comparar duas strings:

```typescript
  const maiorString = maiorValor("css", "styled components");
  console.log(maiorString); // "styled components"
```

E essa é a mágica dos tipos genéricos no TypeScript! Com eles, você pode escrever código mais flexível e mais fácil de reutilizar. E o melhor de tudo é que, como o TypeScript é baseado em tipos, você pode ter a certeza de que seu código está sempre correto.

### Utilização dos tipos genéricos em funções

Dando continuidade à nossa jornada de aprendizado sobre tipos genéricos.

Você deve se lembrar que tipos genéricos são aqueles que podem ser aplicados a vários tipos diferentes. Isso significa que podemos escrever uma função genérica e, depois, utilizá-la com vários tipos diferentes.

Vamos dar uma olhada em um exemplo simples de uma função genérica que recebe dois valores, a e b, e retorna um array com eles invertidos. O código abaixo mostra como essa função pode ser escrita usando tipos genéricos:

``` typescript
  function swap<T, U>(a: T, b: U) {
    return [b, a];
  }

const result = swap<string, number>("Olá", 123);
console.log(result); // Output: [123, "Olá"]

const result = swap<boolean, string>(true, "Uva");
console.log(result); // Output: ["Uva", true]
```

Nesse exemplo, temos uma função swap que utiliza dois tipos genéricos: T e U. Ela recebe dois valores, a e b, e retorna um array com eles invertidos.

Ao chamarmos a função com um valor string e um number, os tipos genéricos são inferidos como string e number respectivamente, e o resultado é o array [123, "Olá"].

Viu só como é legal e prático? Com tipos genéricos, você não precisa escrever uma função diferente para cada tipo. Além disso, a função garante que os tipos passados são os tipos corretos.

E essa é só uma das vantagens, é claro. Ainda temos muito o que aprender sobre tipos genéricos e suas aplicações.

### Exemplos de tipos genéricos em arrays

Agora vamos dar uma olhada em uma função bem legal e útil, que é capaz de procurar um elemento específico dentro de um array. É como se fosse um superdetetive dos arrays! Vamos ver essa função em ação e entender como ela funciona. Preparem-se para uma aventura cheia de mistérios e surpresas!

```typescript
  function contains<T>(array: T[], element: T): boolean {
    const isContained = array.some((item) => item === element);

    return isContained;
  }

  console.log(contains([1, 2, 3, 4, 5], 3)); // true
  console.log(contains([1, 2, 3, 4, 5], 6)); // false
  console.log(contains(["Pastel", "Coxinha", "Pizza"], "Coxinha")); // true
  console.log(contains(["Pastel", "Coxinha", "Pizza"], "Uva")); // false
```

Essa função é um superdetetive do mundo dos arrays! Ela procura um elemento específico no array e diz se ele está lá ou não. O tipo de elementos que o array pode ter é determinado por um parâmetro de tipo T, que é como um capacete de proteção para a função.

A função percorre o array, olhando para cada um dos elementos, até encontrar o elemento que você está procurando. Se encontrar, a função diz "Eureka, encontrei!" e retorna "true". Se não encontrar, a função diz "Desculpe, não encontrei" e retorna "false".

No exemplo acima, a primeira chamada da função resulta em "Eureka, encontrei!", o que significa que o número 3 está presente no array [1, 2, 3, 4, 5]. A segunda chamada resulta em "Desculpe, não encontrei", o que significa que o número 6 não está presente no array.

## Vamos Praticar

### Exercícios

1. Crie uma função genérica chamada "identity" que aceita um parâmetro genérico e retorna esse mesmo  parâmetro.
2. Escreva uma função genérica que possa retornar a soma de dois objetos de tipos diferentes (por exemplo, número + string), onde o tipo de retorno é uma string. (Dica: [Array.from](https://www.javascripttutorial.net/es6/javascript-array-from/), [Set](https://www.javascripttutorial.net/es6/javascript-set/))
3. Crie uma função genérica chamada "reverseArray" que aceita um array genérico e retorna esse array invertido.
4. Crie uma função genérica chamada "isEqual" que compara dois valores genéricos e retorna true se forem iguais ou false se forem diferentes.
5. Escreva uma função genérica que possa retornar uma nova array sem elementos duplicados.
6. (Bônus) Crie uma classe genérica chamada "Pair" que aceita dois parâmetros genéricos e fornece uma propriedade "first" e "second".

#### Gabarito

1. Crie uma função genérica chamada "identity" que aceita um parâmetro genérico e retorna esse mesmo parâmetro.

```typescript
  function identity<T>(arg: T): T {
    return arg;
  }
```

2. Escreva uma função genérica que possa retornar a soma de dois objetos de tipos diferentes (por       exemplo, número + string), onde o tipo de retorno é uma string:

```typescript
  function sumAsString<T, U>(a: T, b: U): string {
    return `${a} + ${b} = ${a + b}`;
  }

  const num = 2;
  const str = "hello";
  const result = sumAsString(num, str);
  console.log(result); // "2 + hello = 2hello"
```

3. Crie uma função genérica chamada "reverseArray" que aceita um array genérico e retorna esse array invertido.

```typescript
function reverseArray<T>(array: T[]): T[] {
  return array.reverse();
}
const array = [1, 2, 3, 4, 5];
const reversedArray = reverseArray(array);
console.log(reversedArray); // Output: [5, 4, 3, 2, 1]
```

4. Crie uma função genérica chamada "isEqual" que compara dois valores genéricos e retorna true se forem iguais ou false se forem diferentes.

```typescript
function isEqual<T>(a: T, b: T): boolean {
  return a === b;
}

```

5. Escreva uma função genérica que possa retornar uma nova array sem elementos duplicados:

```typescript
function removeDuplicates<T>(arr: T[]): T[] {
  const uniqueArray: T[] = [];
  arr.forEach((value) => {
    if (!uniqueArray.includes(value)) {
      uniqueArray.push(value);
    }
  });
  return uniqueArray;
}

const arr = [1, 2, 3, 2, 1];
const uniqueArray = removeDuplicates(arr);
console.log(uniqueArray); // [1, 2, 3]
// Resposta Alternativa 

function removeDuplicatesBonus<T>(arr: T[]): T[] {
  return Array.from(new Set(arr));
}

const arr = [1, 2, 3, 2, 1];
const uniqueArray = removeDuplicatesBonus(arr);
console.log(uniqueArray); // [1, 2, 3]
```

#### Bônus

6. Crie uma classe genérica chamada "Pair" que aceita dois parâmetros genéricos e fornece uma propriedade "first" e "second".

```typescript
  class Pair<T, U> {
    first: T;
    second: U;

    constructor(first: T, second: U) {
      this.first = first;
      this.second = second;
    }
  }
```

## Recursos Adicionais

- Documentação do TypeScript sobre tipos genéricos:
[https://www.typescriptlang.org/docs/handbook/2/generics.html](https://www.typescriptlang.org/docs/handbook/2/generics.html)

- TypeScript Generics
  [https://www.typescripttutorial.net/typescript-tutorial/typescript-generics/](https://www.typescripttutorial.net/typescript-tutorial/typescript-generics/)

- Genéricos do TypeScript – Caso de uso e exemplos
[https://www.freecodecamp.org/news/typescript-generics-use-case-example/](https://www.freecodecamp.org/news/typescript-generics-use-case-example/)

- How To Use Generics in TypeScript
[https://www.digitalocean.com/community/tutorials/how-to-use-generics-in-typescript](https://www.digitalocean.com/community/tutorials/how-to-use-generics-in-typescript)

- How To Easily Understand TypeScript Generics
[https://www.telerik.com/blogs/easily-understand-typescript-generics](https://www.telerik.com/blogs/easily-understand-typescript-generics)

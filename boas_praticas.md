# Boas Práticas na programação

- Escrever código é como como escrever um livro. Só com a prática teremos um bom resulado.


- Este guia reúne as melhores metodologias de progrmação em um único lugar. 
Na listagem abaixo, comentamos o padrão **SOLID** criado por [Robert C. Margin](https://en.wikipedia.org/wiki/Robert_C._Martin), falamos sobre o livro **Clean Code** e suas recomendações, além de abordar a  **programação funcional** e apresentar os conceitos do object calisthenics.

## Index

* 1. [SOLID](#SOLID)
	* 1.1. [Single Responsibility Principle](#SingleResponsibilityPrinciple)
	* 1.2. [Open-closed Principle](#Open-closedPrinciple)
	* 1.3. [Liskov Substitution Principle](#LiskovSubstitutionPrinciple)
	* 1.4. [Interface Segregation Principle](#InterfaceSegregationPrinciple)
	* 1.5. [Dependency Inversion](#DependencyInversion)
* 2. [Clean Code](#CleanCode)
* 3. [Object Calisthenics](#ObjectCalisthenics)
* 4. [Programação funcional](#Programaofuncional)
* 5. [Bônus: ES6](#es6)



##  1. <a name='SOLID'></a>SOLID

- SOLID é um conjunto de 5 princípios, conforme a imagem a seguir:

![](https://cdn-images-1.medium.com/max/1600/1*yO6YGExWLJl5VOUL61xXvQ.jpeg)

###  1.1. <a name='SingleResponsibilityPrinciple'></a>Single Responsibility Principle 
	
- Cada classe ou função deve ter uma responsabilidade única no sistema

- Crie classes e funções que fazem apenas uma única terefa, e não várias.


###  1.2. <a name='Open-closedPrinciple'></a>Open-closed Principle 

- Objetos e entidades devem ser abertos a extensão, e fechados a modificação

- Se for necessário adicionar uma funcionalidade no sistema, esta funcionalidade deve ser adicionada através da criação de novas classes ou funções, e não da alteração das mesmas.

###  1.3. <a name='LiskovSubstitutionPrinciple'></a>Liskov Substitution Principle

- Se a *classe B* herda da *classe A*, então você deve ser capaz de usar *classe B* no lugar de *classe A* sem quebrar a funcionalidade

- Ou seja, as funcionalidades da classe filha não podem quebrar as funcionalidades da classe pai. 
Se uma classe `People` que possui o método `save` e retorna o `ID` gerado é pai da classe `Student`, e se esta classe `Student` também possui o método `save`, este método deve obrigatoriamente retornar o `id` gerado, e não outro tipo de informação.

###  1.4. <a name='InterfaceSegregationPrinciple'></a>Interface Segregation Principle

- Clientes (nesse caso, vc) não deve ser obrigado a implementar métodos de interface que não vá usar

- Se uma classe possui uma interface que que possui métodos nos quais não são necessários, então esta interface deve ser quebrada em 2, ou mais.

###  1.5. <a name='DependencyInversion'></a>Dependency Inversion

- Módulos de alto nível não devem depender de módulos de baixo nível. Ambos devem depender de abstrações;
- Abstrações não devem depender de detalhes;
- Detalhes devem depender de abstrações

* Neste último principio, uma classe deve ser a mais abstrata possível, e não deve depender de outras classes. 
Não instancie classes dentro de outras classes, use interfaces e repasse suas referencias.

##  2. <a name='CleanCode'></a>Clean Code 

[Fonte](https://medium.com/trainingcenter/c%C3%B3digo-limpo-vers%C3%A3o-javascript-80adecafdbec)

Clean code é um [livro](https://www.amazon.com.br/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882) com diversas especificações  para que você escreva código melhor. 
Algumas delas:

- **Variáveis**: use nome de variáveis auto explicativas. Nada de usar `x` ou `i` ou `item`, ou `foo`. 

- **Nome de métodos**: use nome de métodos que sejam pesquisáveis, e que não necessitem de comentários. Por exemplo `getInfo` é um mau nome, mas `getPersonInformation` é melhor. Evite nomes como `saveRecord`, ou `getClientData`, ou `send`. Ao invés de `sabeRecord`, pode-se utilizar `savePerson`.  

- **Faça o uso de constantes, sempre**! Evite algo do tipo `setTimeout(blastOff, 86400000);`, prefira `setTimeout(blastOff, MILLISECONDS_IN_A_DAY);`

- **Explícito é sempre melhor**! Defina variáveis com nomes explícitos, evite por exemplo:

```js
const locations = ['Austin', 'New York', 'San Francisco'];
locations.forEach((l) => {
  doStuff();
  doSomeOtherStuff();
  // ...
  // ...
  // ...
  // Espera, para que serve o `l` mesmo?
  dispatch(l);
});
```

- Evite passar muitos parâmetros em uma função. Se possível passe um objeto;

- Crie funções que façam uma única coisa (SRP aqui);

- Nome de funções devem ser o mais explícitas possíveis. Por exemplo `function addToDate(date, month) {` é ruim, pois apenas olhando o nome da função não sabemos o que é adicionado a data. Use então o nome `addMonthToDate(month, date)`

- Funções devem conter no máximo 1 nível de abstração. Não use ifs encadeados, gerando o famoso efeito haduken; 🤣

![](https://www.codigofonte.com.br/wp-content/uploads/2014/09/hadouken.jpg)


- Evite código duplicado o máximo possível

- use <code> Object.assign </code> para novos objetos que possuem como fonte outros objetos:

```js
const menuConfig = {
  title: 'Order',
  buttonText: 'Send',
  cancellable: true
};
function createMenu(config) {
  config = Object.assign({
    title: 'Foo',
    body: 'Bar',
    buttonText: 'Baz',
    cancellable: true
  }, config);
  // .........
}
createMenu(menuConfig);
```

- Não use `flags`, principalmente que desviam o fluxo de código de uma função

Ruim:
```js
function createFile(name, temp) {
  if (temp) {
    fs.create(`./temp/${name}`);
  } else {
    fs.create(name);
  }
}
```

Bom:
```js
function createFile(name) {
  fs.create(name);
}
function createTempFile(name) {
  createFile(`./temp/${name}`);
}
```

- Evite efeitos colaterais em funções. Uma função não deve alterar o estado de qualquer coisa fora dela. 

- Não crie funções globais, por exemplo:

```js
Array.prototype.diff = function diff(comparisonArray) {
  const hash = new Set(comparisonArray);
  return this.filter(elem => !hash.has(elem));
};
```

- Encapsule condicionais o máximo possível. Exive o uso de:

```js
if (condicao1 && condicao2 && condicao3)
```

Use:

```js
if (userHasEmptyAccount)
ou
if (user.hasEmpptyAccount)
```

- Não negue condicionais. Ao invés de usar o método `formIsNotValid`, use `formValid`. 

Ruim:

```js
function onButtonSaveClick() {
	if (formIsNotValid) {
		// show error
	}
	else {
		// save.....
	}
}
```

Bom: 

```js
function onButtonSaveClick() {
	if (formIsValid) {
		// save
		// return
	}
	
	// show error

}
```

- Evite checar tipos

- Use encadeamento de métodos 
Ex:

```js
class Car {
  constructor(make, model, color) {
    this.make = make;
    this.model = model;
    this.color = color;
  }
  setMake(make) {
    this.make = make;
    // NOTA: Retorne this para encadear
    return this;
  }
  setModel(model) {
    this.model = model;
    // NOTA: Retorne this para encadear
    return this;
  }
  setColor(color) {
    this.color = color;
    // NOTA: Retorne this para encadear
    return this;
  }
  save() {
    console.log(this.make, this.model, this.color);
    // NOTA: Retorne this para encadear
    return this;
  }
}
const car = new Car('Ford','F-150','red')
  .setColor('pink')
  .save();
```

- Prefira composição a herança


##  3. <a name='ObjectCalisthenics'></a>Object Calisthenics

Este padrão foi criado por [Jeff Bay](http://www.xpteam.com/jeff/) para que possamos ter um código mais limpo. 
Ótimos progradores estão sempre com estas regras na cabeça, usando-as constantemente em seus códigos.

As **regras** são:

- Um nível de recuo por método.

  Não usar mais que dois ifs, ou outros laços. Sempre quebre em mais funcoes.

- Não use a palavra-chave ELSE.

  Negue as condições antes, para não ter else

- Envolver todos os primitivos e Strings em classes. 

  Sempre que possível não use tipos primitivos

- Funções de primeira classe

  Sempre que houver uma classe com coleções, esta classe deverá manipular apenas a coleção e mais nenhuma outra variável. Assim comportamentos relacionados à coleção serão implementados por sua própria classe da coleção.

- Um ponto por linha.

  Não encadear vários métodos em uma mesma linha

- Não abrevie.

  Já discutido, de o nome das variáveis o mais completo possível.

- Mantenha todas os módulos com menos de 50 linhas.

  Mantenha classes pequenas

- Nenhuma função com mais de dois parâmetros.

- Sem getters ou setters. 

  Cuidado ao usar setters e quebrar o princípio Open/Closed do SOLID.

##  4. <a name='Programaofuncional'></a>Programação funcional

leia: https://medium.com/@leandrotk_/princ%C3%ADpios-de-programa%C3%A7%C3%A3o-funcional-com-javascript-37ec5d6afab9

## 5. <a name="es6"></a> Bônus: Para javascript, aprenda ES6

leia: https://gist.github.com/danielschmitz/c6f471491c320577be5c2c55a438170e

todas as regras com exemplos em: http://es6-features.org


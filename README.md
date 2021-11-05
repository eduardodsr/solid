## Aprenda Design Patterns com SOLID

- Aprenda a utilizar o SOLID para organizar e otimizar seus códigos
- Rating: 4.3 out of 5 (290 ratings)
- 5,205 students
- Last updated 10/2019

```Link: ``` https://www.udemy.com/course/aprendasolid/

### Sobre

Aprenda Design Patterns com SOLID

O SOLID é um Design Pattern voltado para linguagens orientadas a objetos e assim como qualquer Padrão de Projeto de Software ele veio para ajudar a organizar, estruturar e otimizar seus algoritmos, fazendo com que seu código ganhe:

– Credibilidade;

– Otimização;

– Organização;

– Estabilidade;

– Facilidade de entendimento;

– Facilidade de manutenção e atualizações;

– Preparação para reutilização de código em futuros projetos.

Neste curso iremos aprender os 5 princípios do SOLID e como utilizar corretamente cada um bem como o benefício ganho em cada um deles, através de aulas práticas e teóricas.

### Info

Autor: Felipe Cabrera / ByLearn Cursos
Gênero: Programação
Ano de Lançamento: 2019

## Course content
9 sections • 22 lectures • 1h 36m total length

1. **Introdução**   :white_check_mark:
2. **Crise do Software**    :white_check_mark:
3. **Introdução ao Solid**   :white_check_mark:
    3.1. Criação do Solid
    3.2. Benefícios do Solid
    3.3. Significado do Solid
4. **S - Princípio da Responsabilidade Única**  :white_check_mark:
5. **O - Princípio do Aberto/Fechado** :white_check_mark:
6. **L - Princípio da Substituição de Liskov** :white_check_mark:
7. **I - Princípio da Segregação de Interface** :x:
8. **D - Princípio da Inversão de Dependência** :x:
9. **Conclusão** :x:

<br>

## Resumo

### SOLID - Padrões de Projeto de Software

 - Foi pensando nessa necessidade de melhorar e organizar os códigos que começaram a se pensar em padronizar os códigos.
- Desenvolvendo de um jeito consciente de forma com que a equipe consiga entender o que está fazendo
    - Pensando sempre no projeto como um todo, do início ao fim;
    - Gerando assim os **Design Patterns**


### SOLID - Benefícios

- Os princípios **SOLID** devem ser aplicados para se obter os benefícios da **orientação a objetos**, tais como:
    - Seja fácil de se manter, adaptar e se ajustar às alterações de escopo;
    - Seja testável e de fácil entendimento;
    - Seja extensível para alterações com o menor esforço necessário;
    - Que forneça o máximo de reaproveitamento;
    - Que permaneça o máximo de tempo possível em utilização.

* Utilizando os princípios SOLID **é possível evitar problemas muito comuns**:
    - Dificuldade na testabilidade / criação de testes de unidade;
    - Código sem estrutura ou padrão;
    - Dificuldades de isolar funcionalidades;
    - Duplicação de código, uma alteração precisa ser feita em N pontos;
    - Fragilidade, o código quebra facilmente em vários pontos após alguma mudança.


### SOLID - Significado

| Inicial  | Abreviação  | Significado  |
| ------------ | ------------ | ------------ |
| **S** |  SRP  | Princípio da Responsabilidade Única (Single Responsibility Principle) |
| **O** | OCP  | Princípio do Aberto/Fechado (Open/Close Principle)   |
| **L**  |  LSP |  Princípio da Substituição de Liskov (Liskov Substitution Principle)  |
| **I**  | ISP  | Princípio da Segregação de Interface (Interface Segregation Principle) |
| **D** | DIP  | Princípio da  Inversão de Dependência (Dependency Inversion Principle) |

### SOLID - Resumo

|  Inicial | Significado  |
| ------------ | ------------ |
| S  | Uma classe deve ter uma, e somente uma responsabilidade  |
| O | O código deve ser aberto para extensão, mas fechado para alteração  |
| L | Objetos devem poder ser substituíveis com instancias de seu tipos base sem alterar o bom funcionamento do software  |
| I  | Várias interfaces específicas são melhores que uma única interface genérica  |
| D |  Devemos depender de classes abstratas, não de classes concretas |


### SOLID

Princípios Básicos de Arquitetura

#### Objetivo
- Informar a necessidade de se estudar/praticar SOLID; possuir essa base é mais importante que saber qualquer tecnologia. 

#### 1. - S - Princípio da Responsabilidade Única / SRP
Uma classe deve ter apenas uma razão para mudar;

"There should never be more than one reason for a class to change" - **Robert C. Martin**

* Primeiro princípio do SOLID, sendo considerado por muitos a base para o restante
    - Uma classe deve ter uma, e somente uma responsabilidade.
    - Uma classe nunca pode ter responsabilidade de outra classe.
    - Toda classe deve ter um inicio e fim conhecido.
    - Busca-se a alta coesão de código-classe.
    - A responsabilidade deve estar totalmente encapsulada na respectiva classe.
    - Onde se tem muita generalização não é possível ter especialização. 

#### SRP - Argumentos 
- Torna a classe mais reusável e consequentemente o sistema mais flexível;
    - Uma God Class não pode ser reaproveitada, pois não se encaixa em nenhum contexto devido as múltiplas responsabilidades.

* Facilita a manutenção, pois tendo apenas uma responsabilidade é possível atacar cada questão isoladamente, de forma mais simples;

- A quebra de apenas uma responsabilidade afeta menos a aplicação, essa quebra isolada é mais simples de tratar;
    - Mais fácil de debugar a funcionalidade.
* Maior legibilidade e compreensão da classe;
- Torna possível ser mais assertivo nos testes unitários.

#### SRP - RESUMO:

- Em resumo, o **SRP** tem como base principal o príncipio de que cada classe tem apenas uma responsabilidade.
    - Classe venda só cuida de vendas;
    - Classe produto não pode cuidar de vendas;

* Além disso possui um secundário que é um dos pilares da OO (Orientação a Objetos), o Encapsulamento.
    - Tudo o que não for de uso público obrigatoriamente, deve ser mantido em segredo dentro de uma classe;
    - Uso de get e set para retorno e atribuição de valores;


#### 2. - 0 - Princípio do Aberto/Fechado / OCP
- "Software entities (classes, modules, functions, and so on) should be open for extension but closed for modification." - **Bertrand Meyer**

* Isso significa que quando criamos uma classe devemos ter em mente que seus comportamentos public/protected permitam alteração pelo "lado de fora" sem alterar o código original, (evitar a alteração do próprio método da classe), ou seja, minimizar a necessidade de revisitação e alteração de métodos internos de uma classe base.

- Existem várias formas de se resolver uma violação do OCP, depende muito do contexto, que pode ser:

    - Injeção de dependência;
    - Utilização de Extension Methods;
    - Utilização de virtual methods, abstract methods.

#### OCP - Argumentos
- Quando o OCP é violado muito provavelmente a aplicação entrará num ciclo de "Corrige um problema, causa um novo..."

#### OCP - RESUMO:

- Tem como princípio que o código deve estar aberto para **extensões**, porém, **fechado** para alterações:
    - Toda atualização/adição de funcionalidade que **modifique** um código existente é chamada de **alteração**.
    - Toda atualização/adição de funcionalidade que **não modifique** nenhum código existente é chamada de **extensão**.
- Conseguimos obedecer esse princípio por meio de **abstração**:
    - Toda interface ou classe abstrata possui apenas uma abstração da função a ser implementada, sendo assim, ela nunca é alterada, apena extendida.



#### 3. - L - Princípio da Substituição de Liskov (LSP)
- O princípio estabelece que um objeto do tipo T deve ser substituível pelo tipo S, onde o tipo S é um subtipo de T. Uma violação mais comum do LSP seria a checagem, a partir da classe base, de seus subtipos, se for necessário fazer isso é melhor não existir essa herança. Sugiro ler mais sobre isso na internet.

#### LSP - RESUMO:

- Tem como princípio que classes derivadas devem poder ser substituídas por suas classes base.
- Considerado uma extensão do **OCP**.
* Em resumo, diz que toda classe filho deve poder ser substituída pela pai sem problemas, seja o pai uma interface, classe ou classe abstrata.
    - Não devendo ser necessário alterar o pai para isso
- Também liga-se as boas práticas de **POO** onde a classe que herdar de uma abstração (interface ou classe abstrata) deve ter função para tudo o que foi herdado, não tendo heranças desnecessárias.


#### 4. - I - Princípio da Segregação de Interface / ISP
"Many client-specific interfaces are better than one general-purpose interface." - **Robert C. Martin**

O princípio estabelece que é melhor depender de várias interfaces pequenas e coesas do que de uma mais abrangente e menos coesa, sendo que, o propósito de uma interface deve ser único, coeso e pequeno. Quando temos interfaces grandes, na maioria das vezes elas determinam responsabilidades muito extensas.

#### ISP - Argumentos
- Não força classes a implementar funções das quais elas realmente não precisam;
    - Caso a classe precisar de mais funcionalidade ela pode implementar múltiplas interfaces.
- Ajuda a estabelecer contratos mais comprometidos com o princípio SRP.

#### 5. - D - Princípio da Inversão de Dependência / DIP
- "One should "depend upon abstractions, [not] concretions." - **Robert C. Martin**

* O princípio estabelece que devemos depender de abstrações e não de classes concretas. Isso quer dizer que devemos depender de interfaces e não de classes concretas e existem muitos benefícios em atender esse princípio. Utilizando esse princípio conseguimos injetar as dependências, o que também facilita os testes unitários.

- É importante informar que esse princípio também se aplica a objetos .NET e não apenas custom objects, o correto é utilizar IList e não List, ou mesmo IEnumerable, tudo depende das suas necessidades.

* Quando aplicamos o DIP devemos lembrar do ISP, pois uma classe concreta na maioria das vezes implementa várias interfaces, então, devemos escolher a abstração que atende as nossas necessidades mais restrita possível àquela tarefa.

#### DIP - Argumentos
- Quando dependemos de interfaces podemos criar novas implementações sempre que for necessário atender modificações;

* Podemos testar novas implementações mais eficazes;

- Podemos testar mais facilmente;

* Atendemos melhor o SRP e ISP.
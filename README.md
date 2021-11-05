## Aprenda Design Patterns com SOLID



- O **SOLID** é um **Design Pattern** voltado para linguagens orientadas a objetos. 
- Assim como, qualquer **Padrão de Projeto de Software** ele veio para ajudar a organizar, estruturar e otimizar seus algoritmos, fazendo com que seu código ganhe:

    – Credibilidade;
    – Otimização;
    – Organização;
    – Estabilidade;
    – Facilidade de entendimento;
    – Facilidade de manutenção e atualizações;
    – Preparação para reutilização de código em futuros projetos.


## SOLID - Padrões de Projeto de Software

 <p align="center">
  <img src="https://i.imgur.com/y08c31P.png" width="800px" />
 </p>

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


# S - O - L - I - D

- Princípios Básicos de Arquitetura de Software.

* ## 5 Princípios ( S - O - L - I - D ) :

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

#### SOLID - S (SRP) - RESUMO:

- Em resumo, o **SRP** tem como base principal o príncipio de que cada classe tem apenas uma responsabilidade.
    - Classe venda só cuida de vendas;
    - Classe produto não pode cuidar de vendas;

* Além disso possui um secundário que é um dos pilares da OO (Orientação a Objetos), o Encapsulamento.
    - Tudo o que não for de uso público obrigatoriamente, deve ser mantido em segredo dentro de uma classe;
    - Uso de get e set para retorno e atribuição de valores;

<br>

#### 2. - 0 - Princípio do Aberto/Fechado / OCP
- "Software entities (classes, modules, functions, and so on) should be open for extension but closed for modification." - **Bertrand Meyer**

* Isso significa que quando criamos uma classe devemos ter em mente que seus comportamentos public/protected permitam alteração pelo "lado de fora" sem alterar o código original, (evitar a alteração do próprio método da classe), ou seja, minimizar a necessidade de revisitação e alteração de métodos internos de uma classe base.

- Existem várias formas de se resolver uma violação do OCP, depende muito do contexto, que pode ser:

    - Injeção de dependência;
    - Utilização de Extension Methods;
    - Utilização de virtual methods, abstract methods.

#### OCP - Argumentos
- Quando o OCP é violado muito provavelmente a aplicação entrará num ciclo de "Corrige um problema, causa um novo..."

#### SOLID - O (OCP) - RESUMO:

- Tem como princípio que o código deve estar aberto para **extensões**, porém, **fechado** para alterações:
    - Toda atualização/adição de funcionalidade que **modifique** um código existente é chamada de **alteração**.
    - Toda atualização/adição de funcionalidade que **não modifique** nenhum código existente é chamada de **extensão**.
- Conseguimos obedecer esse princípio por meio de **abstração**:
    - Toda interface ou classe abstrata possui apenas uma abstração da função a ser implementada, sendo assim, ela nunca é alterada, apena extendida.

<br>

#### 3. - L - Princípio da Substituição de Liskov (LSP)
- O princípio estabelece que um objeto do tipo T deve ser substituível pelo tipo S, onde o tipo S é um subtipo de T. Uma violação mais comum do LSP seria a checagem, a partir da classe base, de seus subtipos, se for necessário fazer isso é melhor não existir essa herança. Sugiro ler mais sobre isso na internet.

#### SOLID - L (LSP) - RESUMO:

- Tem como princípio que classes derivadas devem poder ser substituídas por suas classes base.
- Considerado uma extensão do **OCP**.
* Em resumo, diz que toda classe filho deve poder ser substituída pela pai sem problemas, seja o pai uma interface, classe ou classe abstrata.
    - Não devendo ser necessário alterar o pai para isso
- Também liga-se as boas práticas de **POO** onde a classe que herdar de uma abstração (interface ou classe abstrata) deve ter função para tudo o que foi herdado, **não** tendo heranças desnecessárias.

<br>

#### 4. - I - Princípio da Segregação de Interface / ISP
"Many client-specific interfaces are better than one general-purpose interface." - **Robert C. Martin**

- O princípio estabelece que é melhor depender de várias interfaces pequenas e coesas do que de uma mais abrangente e menos coesa.

- Sendo que, o propósito de uma interface deve ser único, coeso e pequeno. 

- Quando temos interfaces grandes, na maioria das vezes elas determinam responsabilidades muito extensas.

#### ISP - Argumentos
- Não força classes a implementar funções das quais elas realmente não precisam;
    - Caso a classe precisar de mais funcionalidade ela pode implementar múltiplas interfaces.
- Ajuda a estabelecer contratos mais comprometidos com o princípio SRP.

#### SOLID - I (ISP) - RESUMO:

- Tem como princípio que todas as interfaces implementada **não devem** ter funções que não são utilizadas pela classe que a implementou.
- Em outras palavras “uma classe consumidora **não deve** conhecer (depender) métodos que não necessitam.”
* Em resumo, diz que toda classe que herde de uma interface **não pode** ter métodos que **não são usados**.
- Usando a lógica, podemos ver que na maior parte dos casos, caso o **ISP** não seja respeitado, teremos problemas com o **OCP** e o **LSP** também.

<br>

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

#### DIP - RESUMO:

- Tem como princípio ser uma maneira específica para desacoplar as dependências entre os objetos.
- Componentes (Classes) de mais alto nível **não devem depender** de componentes (Classes) de níveis mais baixos, mas ambos devem depender de abstrações.
* Abstrações **não devem depender** de detalhes (implementações), mas os detalhes (implementações) **devem depender** de abstrações.
- Inverter a dependência faz com que um cliente não fique frágil a mudanças relacionadas a detalhes de implementação.
- Isto é, alterar o detalhe não quebra o cliente. 
- Além disso, o mesmo cliente pode ser reutilizado com outro detalhe de implementação.

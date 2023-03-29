## Design Patterns

> **Fonte primária:** GAMMA, Erich et al. Design Patterns: Elements of Reusable Object-Oriented Software. 1. ed. Massachusetts: Addison-Wesley Professional, 2009

Padrões de design são soluções reutilizáveis para problemas comuns no desenvolvimento de software.
Existem muitos tipos diferentes de padrões de design, mas eles podem ser amplamente classificados em **três categorias**:

- **[Padrões Criacionais](#padrões-criacionais)**
  - Esses padrões são usados para criar objetos e gerenciar seu ciclo de vida. 
    Eles fornecem maneiras de criar objetos sem especificar a classe exata do objeto que será criado.
    - [Singleton](#singleton)
    - [Abstract Factory](#abstract-factory)
    - [Builder](#builder)
    - [Factory Method](#factory-method)
    - [Prototype](#prototype)

- **[Padrões Estruturais](#padrões-estruturais)** 
  - Esses padrões são usados para criar relacionamentos entre objetos, garantir que as mudanças em um objeto não afetem outros objetos e 
    fornecem maneiras de organizar objetos e classes em estruturas maiores e mais complexas.
    - [Adapter](#adapter)
    - [Bridge](#bridge)
    - [Composite](#composite)
    - [Decorator](#decorator)
    - [Facade](#facade)
    - [Flyweight](#flywight)
    - [Proxy](#proxy)

- **[Padrões Comportamentais](#padrões-comportamentais)** 
  - Esses padrões são usados para gerenciar a interação entre objetos e definir como os objetos se comunicam entre si.
    - [Chain of Responsibility](#chain-of-responsibility)
    - [Command](#command)
    - [Interpreter](#interpreter)
    - [Iterator](#iterator)
    - [Mediator](#mediator)
    - [Memento](#memento)
    - [Observer](#observer)
    - [State](#state)
    - [Strategy](#strategy)
    - [Template Method](#template-method)
    - [Visitor](#visitor)
    
# Padrões Criacionais
___

# Singleton
O padrão Singleton é um padrão de design criacional que permite garantir que uma classe tenha apenas uma única instância em todo o sistema. Isso é útil em situações em que é importante que apenas uma única instância de uma classe exista, como em um gerenciador de configuração ou em uma conexão de banco de dados.

O Singleton é implementado criando uma classe que contém um método para criar uma única instância da própria classe, se ela ainda não existir, ou retornar a instância existente se já foi criada. O construtor da classe é definido como privado, para que não seja possível criar instâncias adicionais diretamente.

O acesso à instância única é geralmente feito por meio de um método estático, que retorna a única instância da classe. Esse método pode ser chamado de qualquer lugar do sistema, sem a necessidade de criar uma nova instância da classe.

O padrão Singleton tem várias vantagens, incluindo economia de recursos do sistema, garantia de que apenas uma única instância da classe é usada e facilidade de acesso à instância única. No entanto, é importante lembrar que o Singleton pode ser mal utilizado e causar problemas de teste unitário e dependência excessiva em todo o sistema. Por isso, é importante avaliar cuidadosamente se o padrão Singleton é a solução adequada para o problema em questão.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/singleton

# Abstract Factory
O padrão Abstract Factory é um padrão de design criacional que fornece uma maneira de encapsular grupos de fábricas relacionadas sem especificar suas classes concretas. Em outras palavras, o padrão Abstract Factory fornece uma interface para criar famílias de objetos relacionados sem se preocupar com as classes específicas desses objetos.

O padrão Abstract Factory é usado quando um sistema precisa ser independente das classes concretas dos objetos que ele cria, ou quando um sistema precisa ser configurado com uma das várias famílias de objetos relacionados em tempo de execução.

Para implementar o padrão Abstract Factory, é necessário criar uma interface abstrata ou classe abstrata que define as operações que criarão os objetos. Em seguida, devem ser criadas classes concretas que implementam essas operações para criar objetos concretos. Finalmente, deve ser criada uma fábrica abstrata que encapsula um grupo de fábricas concretas relacionadas, cada uma responsável por criar uma família de objetos.

O acesso à fábrica abstrata é geralmente feito por meio de uma interface ou classe abstrata que define as operações disponíveis para criar os objetos. O cliente que usa o padrão Abstract Factory não precisa se preocupar com a classe concreta das fábricas ou objetos que ele cria, pois isso é tratado pela fábrica abstrata.

O padrão Abstract Factory tem várias vantagens, incluindo a criação de famílias de objetos relacionados de forma consistente e facilidade de substituição de famílias de objetos em tempo de execução. No entanto, a implementação do padrão Abstract Factory pode ser complexa e pode exigir uma compreensão detalhada do sistema e dos objetos envolvidos.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/abstract-factory

# Builder
O padrão Builder é um padrão de design criacional que permite separar a construção de um objeto complexo de sua representação, permitindo a criação de diferentes representações do mesmo objeto. Isso é útil em situações em que a criação de um objeto envolve vários passos complexos e diferentes configurações.

O padrão Builder é implementado criando uma classe Builder que contém métodos para construir cada parte do objeto complexo. O Builder tem métodos para configurar diferentes opções do objeto e, finalmente, um método que retorna o objeto criado.

O objeto complexo que está sendo construído é representado por uma classe Product. Essa classe é construída por meio do Builder, que chama os métodos relevantes para criar cada parte do objeto.

O padrão Builder tem várias vantagens, incluindo a separação da construção de um objeto de sua representação, a facilidade de adicionar novas opções ou partes ao objeto e a possibilidade de criar diferentes representações do mesmo objeto. Além disso, o padrão Builder permite que o código de construção seja reutilizado para criar objetos semelhantes com diferentes configurações.

No entanto, a implementação do padrão Builder pode ser complexa e pode exigir uma compreensão detalhada do sistema e dos objetos envolvidos. O uso do padrão Builder também pode aumentar a complexidade do código, pois é necessário criar uma classe separada para representar cada opção ou parte do objeto.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/builder

# Factory Method
O padrão Factory Method é um padrão de design criacional que define uma interface para criar objetos em uma superclasse, mas permite que as subclasses escolham qual classe concreta instanciar. Isso permite que as subclasses alterem o tipo de objeto que criam, sem modificar o código da superclasse.

O padrão Factory Method é implementado criando uma interface ou classe abstrata que define o método de criação, mas não implementa a criação do objeto. Essa interface ou classe abstrata é implementada por várias subclasses, cada uma responsável por criar uma instância de um objeto específico.

O método de criação abstrato definido pela interface ou classe abstrata da fábrica é então chamado por uma classe cliente, que passa informações sobre o tipo de objeto que deseja criar. A classe cliente não precisa saber a classe concreta do objeto que está criando, apenas a interface ou classe abstrata da fábrica que está sendo usada.

O padrão Factory Method tem várias vantagens, incluindo a separação da criação de objetos da lógica do cliente, a facilidade de adicionar novas subclasses para criar novos tipos de objetos e a capacidade de controlar a criação de objetos em toda a aplicação. Além disso, o padrão Factory Method permite que o código de criação de objetos seja reutilizado em diferentes partes da aplicação.

No entanto, o padrão Factory Method pode aumentar a complexidade do código, pois é necessário criar uma classe separada para cada tipo de objeto que está sendo criado. Além disso, a escolha da classe concreta para criar um objeto pode ser determinada em tempo de execução, o que pode aumentar a complexidade da lógica de criação de objetos.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/factory-method

# Prototype
O padrão Prototype é um padrão de design criacional que permite criar novos objetos duplicando objetos existentes, sem depender de suas classes concretas. O padrão Prototype é útil quando a criação de um objeto é muito complexa ou custosa em termos de recursos, ou quando um objeto precisa ser personalizado em tempo de execução.

O padrão Prototype é implementado criando uma interface ou classe abstrata que define um método de clonagem. Cada classe que precisa ser clonada implementa essa interface ou classe abstrata, e o método de clonagem cria uma cópia exata do objeto. Em muitos casos, o método de clonagem é implementado usando a linguagem de programação de recursos nativos, como o método clone() em Java.

A classe cliente que precisa criar novos objetos pode chamar o método de clonagem em um objeto existente, em vez de instanciar uma nova classe concreta. A classe cliente pode personalizar o objeto clonado, alterando suas propriedades, antes de usá-lo.

O padrão Prototype tem várias vantagens, incluindo a redução da complexidade do código e a facilidade de criar novos objetos personalizados. Além disso, o padrão Prototype ajuda a reduzir o tempo de inicialização do sistema, porque os objetos clonados podem ser pré-carregados e armazenados em cache, tornando-os disponíveis para uso imediato.

No entanto, o padrão Prototype também tem algumas desvantagens. Um objeto pode ser complexo demais para ser clonado, especialmente se contiver objetos internos que não podem ser clonados. Além disso, o padrão Prototype pode criar muitos objetos em cache, ocupando espaço de memória desnecessário.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/prototype


# Padrões Estruturais
___

# Adapter
O padrão Adapter é um padrão de design estrutural que permite que objetos com interfaces incompatíveis trabalhem juntos. Ele converte a interface de uma classe em outra interface que o cliente espera encontrar. O padrão Adapter é útil quando se deseja usar uma classe existente, mas sua interface não é compatível com a interface necessária pela aplicação.

O padrão Adapter é implementado criando uma classe intermediária, chamada de adaptador, que converte a interface da classe existente para a interface necessária pelo cliente. O adaptador implementa a interface necessária pelo cliente, mas delega o trabalho para o objeto existente, que não precisa ser alterado.

O adaptador pode ser implementado como um adaptador de objeto, que encapsula o objeto existente dentro do adaptador, ou como um adaptador de classe, que herda da classe existente e converte sua interface para a interface necessária pelo cliente.

O padrão Adapter tem várias vantagens, incluindo a possibilidade de reutilizar código existente, a capacidade de adaptar classes de bibliotecas de terceiros sem modificar o código-fonte e a capacidade de fornecer uma interface unificada para objetos com interfaces incompatíveis.

No entanto, o padrão Adapter também tem algumas desvantagens, como a introdução de um nível adicional de complexidade e sobrecarga, além do risco de criar muitos adaptadores desnecessários que podem complicar a arquitetura do sistema. Além disso, o padrão Adapter pode afetar o desempenho do sistema devido ao tempo de execução adicional necessário para a conversão da interface.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/adapter


# Bridge
O padrão Bridge é um padrão de design estrutural que permite desacoplar uma abstração de sua implementação, de modo que as duas possam variar independentemente. Ele permite que a abstração e a implementação possam ser alteradas e estendidas independentemente, sem afetar uma à outra.

O padrão Bridge é implementado criando uma classe abstrata que contém uma referência a uma interface ou classe abstrata que representa a implementação. A classe abstrata fornece uma interface para o cliente e delega o trabalho para a classe de implementação por meio da referência. A classe de implementação é escolhida em tempo de execução e pode ser trocada sem afetar a classe abstrata ou o cliente.

O padrão Bridge tem várias vantagens, incluindo a capacidade de desacoplar abstrações complexas e a implementação, a possibilidade de estender as abstrações e implementações independentemente umas das outras e a capacidade de melhorar a flexibilidade e a escalabilidade do sistema.

No entanto, o padrão Bridge também tem algumas desvantagens, como a introdução de uma camada adicional de complexidade e o risco de criar muitas classes adicionais que podem complicar a arquitetura do sistema. Além disso, o padrão Bridge pode afetar o desempenho do sistema devido à sobrecarga adicional de chamadas de método necessárias para delegar o trabalho da abstração para a implementação.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/bridge


# Composite
O padrão Composite é um padrão de design estrutural que permite compor objetos em estruturas de árvore para representar hierarquias de parte-todo. Ele permite que os clientes tratem objetos individuais e composições de objetos uniformemente, permitindo que os mesmos sejam tratados de forma polimórfica.

O padrão Composite é implementado criando uma classe abstrata que representa os elementos da estrutura de árvore. A classe abstrata define uma interface comum para todos os objetos na estrutura, incluindo métodos para adicionar e remover elementos da árvore e métodos para percorrer a estrutura.

As classes concretas representam os elementos individuais da estrutura, enquanto as classes compostas representam as composições de elementos. As classes compostas mantêm uma lista de seus filhos e implementam os métodos de adicionar e remover elementos, além de delegar as operações aos seus filhos.

O padrão Composite tem várias vantagens, incluindo a capacidade de tratar objetos individuais e composições de objetos de maneira uniforme, a possibilidade de adicionar novos tipos de objetos à estrutura facilmente, a capacidade de simplificar o código do cliente e a possibilidade de implementar operações recursivas na estrutura.

No entanto, o padrão Composite também tem algumas desvantagens, como a introdução de uma camada adicional de complexidade e a possibilidade de criar estruturas de árvores muito grandes e profundas, que podem afetar negativamente o desempenho do sistema. Além disso, o padrão Composite pode ser difícil de implementar em sistemas com requisitos complexos ou em sistemas que não seguem uma estrutura hierárquica clara.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/composite


# Decorator
O padrão Decorator é um padrão de design estrutural que permite adicionar comportamento a um objeto dinamicamente, sem afetar o comportamento dos outros objetos da mesma classe. Ele permite que os clientes adicionem novas funcionalidades a um objeto existente sem modificar sua estrutura original.

O padrão Decorator é implementado criando uma classe abstrata que define a interface para o objeto original e para os decoradores. Em seguida, são criadas classes concretas que implementam o objeto original e os decoradores. Cada decorador é uma classe que implementa a mesma interface que o objeto original e contém uma referência ao objeto original.

O padrão Decorator permite que os clientes adicionem novos comportamentos aos objetos existentes, criando instâncias de decoradores e envolvendo-as em torno do objeto original. Cada decorador adiciona um comportamento específico ao objeto original sem afetar os outros decoradores ou o objeto original.

O padrão Decorator tem várias vantagens, incluindo a capacidade de adicionar novas funcionalidades a um objeto existente sem modificar sua estrutura original, a possibilidade de combinar vários decoradores para criar funcionalidades complexas, a capacidade de adicionar funcionalidades aos objetos em tempo de execução e a possibilidade de criar hierarquias de decoradores que correspondam a hierarquias de objetos.

No entanto, o padrão Decorator também tem algumas desvantagens, como a introdução de uma camada adicional de complexidade, a possibilidade de criar muitas classes adicionais que podem complicar a arquitetura do sistema e a necessidade de garantir que a interface do objeto original seja suficientemente flexível para permitir a adição de novos comportamentos por meio de decoradores.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/decorator


# Facade
O padrão Facade é um padrão de design estrutural que fornece uma interface simplificada para um conjunto de interfaces mais complexas. Ele permite que os clientes interajam com um sistema complexo de maneira mais simples e intuitiva, escondendo a complexidade do sistema subjacente.

O padrão Facade é implementado criando uma classe que contém métodos que encapsulam a lógica do sistema subjacente. Essa classe atua como uma fachada, fornecendo uma interface simplificada para os clientes que não precisam conhecer os detalhes internos do sistema.

Os métodos da fachada podem chamar vários métodos do sistema subjacente e manipular seus resultados para fornecer uma resposta mais simples e direta aos clientes. A fachada pode fornecer um conjunto limitado de funcionalidades ou uma interface mais abrangente, dependendo das necessidades dos clientes.

O padrão Facade tem várias vantagens, incluindo a possibilidade de simplificar a interface do sistema, reduzir o acoplamento entre os componentes do sistema, melhorar a legibilidade e a manutenibilidade do código e fornecer uma interface unificada para clientes de diferentes níveis de experiência.

No entanto, o padrão Facade também tem algumas desvantagens, como a possibilidade de adicionar uma camada adicional de complexidade ao sistema, a necessidade de atualizar a fachada sempre que o sistema subjacente mudar e a possibilidade de tornar a fachada muito grande ou complicada, o que pode dificultar sua compreensão e manutenção.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/facade


# Flyweight
O padrão Flyweight é um padrão de design estrutural que permite a criação de objetos compartilhados para reduzir o consumo de recursos do sistema. Ele permite que várias instâncias de um objeto compartilhem os mesmos dados, em vez de criar uma nova instância de cada vez que o objeto é necessário.

O padrão Flyweight é implementado criando uma classe que armazena os dados compartilhados e uma classe de fábrica que cria novas instâncias do objeto compartilhado. Quando um objeto é necessário, a fábrica verifica se já existe uma instância do objeto com os mesmos dados e a retorna em vez de criar uma nova instância.

O padrão Flyweight tem várias vantagens, incluindo a redução do consumo de recursos do sistema, a possibilidade de armazenar um grande número de objetos em memória com um custo mínimo e a capacidade de melhorar o desempenho do sistema. Ele também pode ser usado para implementar caches de objetos e para gerenciar recursos compartilhados em sistemas distribuídos.

No entanto, o padrão Flyweight também tem algumas desvantagens, como a possibilidade de tornar o código mais complexo e difícil de entender, a necessidade de garantir que os objetos compartilhados sejam imutáveis e a possibilidade de reduzir a flexibilidade do sistema ao restringir a criação de novas instâncias de objetos.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/flyweight


# Proxy
O padrão Proxy é um padrão de design estrutural que permite controlar o acesso a um objeto, fornecendo um substituto ou representante para esse objeto. O Proxy atua como uma camada intermediária entre o cliente e o objeto real, permitindo que o cliente interaja com o objeto indiretamente.

O padrão Proxy é implementado criando uma classe Proxy que implementa a mesma interface que o objeto real. Quando o cliente faz uma chamada ao objeto através do Proxy, o Proxy redireciona a chamada para o objeto real e retorna o resultado para o cliente.

O padrão Proxy tem várias vantagens, incluindo a possibilidade de controlar o acesso a objetos sensíveis ou restritos, a capacidade de adicionar funcionalidades adicionais ao objeto real, como cache de resultados ou validação de entrada, sem modificar o objeto real e a possibilidade de melhorar o desempenho do sistema, reduzindo o número de chamadas ao objeto real.

No entanto, o padrão Proxy também tem algumas desvantagens, como a possibilidade de adicionar uma camada adicional de complexidade ao sistema, a necessidade de atualizar o Proxy sempre que o objeto real mudar e a possibilidade de tornar o código mais difícil de entender ou depurar, especialmente se vários proxies são usados em cascata.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/proxy


# Padrões Comportamentais
___

# Chain of Responsibility
O padrão Chain of Responsibility é um padrão de design comportamental que permite que uma solicitação seja tratada por vários objetos, criando uma cadeia de objetos que podem processar a solicitação. O padrão é baseado na ideia de que cada objeto na cadeia é responsável por uma parte específica do processamento e pode passar a solicitação para o próximo objeto na cadeia se não puder lidar com ela.

O padrão Chain of Responsibility é implementado criando uma classe abstrata que define a interface para lidar com a solicitação e uma cadeia de objetos que implementam essa interface. Cada objeto na cadeia tem uma referência para o próximo objeto na cadeia e tenta lidar com a solicitação, passando-a para o próximo objeto se não puder lidar com ela.

O padrão Chain of Responsibility tem várias vantagens, incluindo a possibilidade de criar cadeias dinâmicas de objetos que podem processar solicitações de forma flexível, a capacidade de adicionar ou remover objetos da cadeia sem afetar o resto do sistema e a possibilidade de simplificar o código, separando o processamento da solicitação em vários objetos.

No entanto, o padrão Chain of Responsibility também tem algumas desvantagens, como a possibilidade de que uma solicitação não seja processada se nenhum objeto na cadeia puder lidar com ela e a possibilidade de reduzir o desempenho do sistema, especialmente se a cadeia for muito longa ou houver muitos objetos na cadeia.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/chain-of-responsibility


# Command
O padrão Command é um padrão de design comportamental que permite encapsular uma solicitação como um objeto, tornando possível parametrizar clientes com diferentes solicitações, enfileirar ou registrar solicitações e suportar operações que podem ser desfeitas.

O padrão Command é implementado criando uma interface comum para todos os comandos, que inclui um método para executar o comando. Em seguida, cada comando é implementado como uma classe que implementa essa interface e inclui os dados necessários para executar o comando. Finalmente, é criado um objeto Invoker que mantém uma lista de comandos e é responsável por chamar o método execute() de cada comando.

O padrão Command tem várias vantagens, incluindo a capacidade de desacoplar o objeto que invoca a operação do objeto que realmente realiza a operação, tornando o código mais flexível e fácil de manter. Além disso, o padrão também permite enfileirar ou registrar solicitações e fornece uma maneira de suportar operações que podem ser desfeitas.

No entanto, o padrão Command também tem algumas desvantagens, como o aumento da complexidade do código, especialmente se muitos comandos diferentes forem necessários. Além disso, o padrão também pode levar a um aumento no uso de memória, especialmente se muitos comandos estiverem sendo mantidos na lista de comandos do Invoker.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/command


# Interpreter
O padrão Interpreter é um padrão de design comportamental que define uma representação para gramáticas e interpretações de linguagens. O padrão é útil para criar interpretações para diferentes tipos de linguagens, como expressões matemáticas, consultas em bancos de dados ou linguagens de programação simples.

O padrão Interpreter é implementado criando uma classe abstrata que define a interface para a interpretação da linguagem e uma série de classes concretas que implementam essa interface para interpretar diferentes partes da linguagem. Em seguida, é criada uma classe Context que armazena informações sobre o estado atual da interpretação e é usada pelos objetos de interpretação para obter informações sobre o contexto atual.

Quando um programa é interpretado usando o padrão Interpreter, a entrada é dividida em tokens ou símbolos que representam elementos da linguagem. Esses símbolos são então passados para os objetos de interpretação, que usam a gramática da linguagem e o estado atual do contexto para interpretar os símbolos e gerar uma saída.

O padrão Interpreter tem várias vantagens, incluindo a capacidade de interpretar diferentes tipos de linguagens, a facilidade de adicionar novos recursos à linguagem e a capacidade de simplificar o código, separando a interpretação da linguagem em vários objetos.

No entanto, o padrão Interpreter também tem algumas desvantagens, como a possibilidade de tornar a interpretação da linguagem lenta e a complexidade do código, especialmente se a gramática da linguagem for muito complexa.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/interpreter


# Iterator
O padrão Iterator é um padrão de design comportamental que permite acessar os elementos de uma coleção sem expor a sua estrutura interna. O padrão Iterator é usado para percorrer coleções de objetos sem expor a sua implementação subjacente.

O padrão Iterator é implementado criando uma interface comum para todos os iteradores que inclui métodos como next(), que retorna o próximo elemento da coleção, e hasNext(), que verifica se há mais elementos a serem percorridos. Em seguida, cada classe de coleção que deseja ser iterada deve implementar essa interface e fornecer um objeto iterador que permite percorrer seus elementos.

O padrão Iterator tem várias vantagens, incluindo a capacidade de percorrer uma coleção de objetos sem expor sua implementação interna, o que torna o código mais modular e mais fácil de manter. Além disso, o padrão Iterator também permite percorrer a coleção de forma flexível, em diferentes direções e com diferentes iterações.

No entanto, o padrão Iterator também tem algumas desvantagens, como a possibilidade de ter um overhead de performance, especialmente se a coleção subjacente for grande. Além disso, o padrão Iterator pode levar a uma maior complexidade do código, especialmente se vários iteradores diferentes forem necessários.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/iterator


# Mediator
O padrão Mediator é um padrão de design comportamental que permite a comunicação entre diferentes objetos de um sistema de forma mais organizada e com menor acoplamento. O objetivo do padrão é definir um objeto que centralize a comunicação entre outros objetos, reduzindo a complexidade e o acoplamento entre eles.

O padrão Mediator é implementado criando um objeto Mediator que possui uma lista de objetos que precisam se comunicar. Cada objeto registrado na lista deve conhecer o objeto Mediator, e o Mediator deve conhecer cada um desses objetos. Quando um objeto precisa se comunicar com outro, ele envia uma mensagem para o objeto Mediator, que encaminha a mensagem para o objeto de destino.

O padrão Mediator tem várias vantagens, incluindo a capacidade de reduzir a complexidade do código, diminuir o acoplamento entre objetos e simplificar a comunicação entre eles. Além disso, o padrão Mediator torna o código mais modular e mais fácil de manter.

No entanto, o padrão Mediator também tem algumas desvantagens, como a possibilidade de criar um objeto Mediator muito grande e complexo, que pode ser difícil de manter. Além disso, o padrão Mediator pode adicionar uma camada adicional de indireção na comunicação entre objetos, o que pode afetar a performance do sistema.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/mediator


# Memento
O padrão Memento é um padrão de design comportamental que permite a captura e restauração do estado interno de um objeto, sem quebrar a encapsulação. O objetivo do padrão é permitir que um objeto possa voltar a um estado anterior sem expor sua implementação interna.

O padrão Memento é implementado criando um objeto Memento que contém o estado interno de um objeto em um determinado momento. Esse objeto Memento é armazenado em um objeto Caretaker, que é responsável por manter a lista de estados anteriores. O objeto Originator, que é o objeto que tem o estado interno a ser salvo e restaurado, pode criar o objeto Memento e fornecer o estado atual ou restaurar o estado a partir de um objeto Memento.

O padrão Memento tem várias vantagens, incluindo a capacidade de salvar e restaurar o estado interno de um objeto sem quebrar a encapsulação, tornando o código mais modular e mais fácil de manter. Além disso, o padrão Memento permite que os estados anteriores sejam armazenados em um objeto externo, o que pode ser útil em situações como desfazer e refazer operações.

No entanto, o padrão Memento também tem algumas desvantagens, como o aumento do uso de memória devido à necessidade de armazenar estados anteriores. Além disso, o padrão Memento pode tornar o código mais complexo, especialmente se vários estados precisarem ser armazenados e restaurados.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/memento


# Observer
O padrão Observer é um padrão de design comportamental que permite a comunicação entre objetos de forma que um objeto possa ser notificado quando ocorrer uma mudança de estado em outro objeto. O objetivo do padrão é criar um mecanismo para notificação automática, permitindo que objetos possam ser informados sobre mudanças sem a necessidade de que esses objetos sejam explicitamente acoplados ao objeto que mudou.

O padrão Observer é implementado através da criação de dois tipos de objetos: o Subject e o Observer. O Subject é o objeto que é observado e o Observer é o objeto que está interessado em receber notificações do Subject. O Subject mantém uma lista de Observers registrados e, quando ocorre uma mudança no estado do Subject, ele notifica todos os Observers registrados. Os Observers, por sua vez, recebem a notificação e podem executar uma ação com base na mudança de estado do Subject.

O padrão Observer tem várias vantagens, incluindo a capacidade de desacoplar objetos, tornando o código mais modular e fácil de manter. Além disso, o padrão Observer permite que os objetos sejam notificados automaticamente sobre mudanças em outros objetos, o que pode ser útil em situações como atualizações de interface do usuário.

No entanto, o padrão Observer também tem algumas desvantagens, como o aumento da complexidade do código devido à necessidade de manter a lista de Observers registrados e notificar todos eles quando ocorre uma mudança de estado. Além disso, o padrão Observer pode ter um impacto negativo no desempenho do sistema se muitos objetos estiverem registrados como Observers.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/observer


# State
O padrão State é um padrão de design comportamental que permite que um objeto altere o seu comportamento quando o seu estado interno é alterado. O objetivo do padrão é separar a lógica de estado em classes separadas e permitir que um objeto mude de estado sem alterar a sua interface.

O padrão State é implementado através da criação de duas interfaces principais: a interface State e a interface Context. A interface State define os possíveis estados que o objeto pode ter e as ações que podem ser executadas em cada estado. A interface Context é o objeto que mantém o estado atual e delega as chamadas de método para o objeto State apropriado.

Quando ocorre uma mudança de estado, o objeto Context altera o objeto State atual para o novo estado apropriado. Em seguida, todas as chamadas de método são delegadas para o objeto State atual. Dessa forma, o objeto Context pode alterar o seu comportamento sem modificar a sua interface pública.

O padrão State tem várias vantagens, incluindo a capacidade de simplificar o código ao separar a lógica de estado em classes separadas. Além disso, o padrão State permite que objetos mudem de comportamento com base no seu estado atual, o que pode ser útil em situações como a criação de um fluxo de trabalho dinâmico.

No entanto, o padrão State também pode ter algumas desvantagens, como a criação de muitas classes adicionais para representar os diferentes estados possíveis e a necessidade de coordenar a mudança de estado entre objetos diferentes. Além disso, o padrão State pode ter um impacto negativo no desempenho do sistema se muitas mudanças de estado ocorrerem frequentemente.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/state


# Strategy
O padrão Strategy é um padrão de design comportamental que permite que um objeto altere o seu comportamento dinamicamente, escolhendo entre diferentes algoritmos ou estratégias que realizam a mesma tarefa de forma diferente. O objetivo do padrão é fornecer uma maneira de mudar o comportamento de um objeto em tempo de execução sem modificar a sua estrutura.

O padrão Strategy é implementado através da criação de uma interface comum para todos os algoritmos ou estratégias possíveis e uma classe que mantém uma referência a essa interface. O objeto que utiliza o padrão pode escolher qual estratégia utilizar dinamicamente, simplesmente mudando a referência da interface para a nova estratégia.

O padrão Strategy é útil em situações onde há muitas variações em um algoritmo ou onde diferentes algoritmos precisam ser utilizados em diferentes situações. O padrão permite que os algoritmos sejam facilmente trocados ou adicionados sem modificar o objeto que utiliza o algoritmo.

O padrão Strategy tem várias vantagens, incluindo a capacidade de simplificar o código ao separar a lógica de negócios em classes separadas. Além disso, o padrão Strategy torna o código mais flexível e extensível, permitindo que novas estratégias sejam adicionadas facilmente.

No entanto, o padrão Strategy também pode ter algumas desvantagens, como a criação de muitas classes adicionais para representar as diferentes estratégias possíveis e a necessidade de coordenação entre objetos diferentes que utilizam o padrão. Além disso, o padrão Strategy pode ter um impacto negativo no desempenho do sistema se muitas trocas de estratégia ocorrerem frequentemente.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/strategy


# Template Method
O padrão Template Method é um padrão de design comportamental que define o esqueleto de um algoritmo em uma classe base, delegando a implementação de algumas etapas específicas para subclasses. O objetivo do padrão é permitir que as subclasses possam redefinir ou estender partes específicas de um algoritmo sem alterar sua estrutura global.

O padrão Template Method é composto por uma classe abstrata que define o método principal do algoritmo (o "template method"), bem como os métodos auxiliares necessários. Algumas etapas do algoritmo são definidas na classe base, enquanto outras são delegadas às subclasses através de métodos abstratos ou virtuais.

Ao usar o padrão Template Method, as subclasses podem personalizar ou estender partes específicas do algoritmo, mas ainda assim manter a mesma estrutura global do algoritmo definida na classe base. Isso permite que o código seja mais modular e reutilizável, pois as partes comuns do algoritmo estão centralizadas em uma classe base.

O padrão Template Method é particularmente útil em situações em que há vários algoritmos semelhantes que compartilham uma estrutura semelhante, mas têm diferenças específicas em algumas etapas do processo. Ele permite que essas diferenças sejam tratadas de forma modular e flexível.

No entanto, o padrão Template Method pode ter algumas desvantagens, como a necessidade de criar várias classes adicionais para cada variação do algoritmo e a falta de flexibilidade para alterar a estrutura do algoritmo em tempo de execução. Além disso, o padrão pode ser complicado de implementar em casos em que a lógica de negócios é complexa e variações específicas são difíceis de definir.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/template-method


# Visitor
O padrão Visitor é um padrão de design comportamental que permite adicionar novas operações a uma estrutura de objetos existente sem alterar a própria estrutura de objetos. Ele separa os algoritmos de uma estrutura de objetos dos objetos em si, permitindo que diferentes algoritmos operem nos mesmos objetos, sem alterar os próprios objetos ou as operações que eles suportam.

Em geral, o padrão Visitor envolve a criação de uma classe separada chamada "visitor" que contém os algoritmos que serão executados nos objetos da estrutura. A estrutura de objetos possui um método "accept" que chama o método correto no visitor para cada objeto na estrutura. O visitor, por sua vez, contém métodos sobrecarregados para cada tipo de objeto na estrutura, que executam as operações relevantes nos objetos.

O padrão Visitor pode ser útil em situações em que há uma estrutura de objetos complexa com muitas classes e é necessário executar algoritmos em subconjuntos específicos dessa estrutura. Ele permite que diferentes algoritmos sejam adicionados à estrutura sem alterar os próprios objetos da estrutura ou as operações que eles suportam.

No entanto, o padrão Visitor pode ter algumas desvantagens, como a necessidade de modificar a estrutura de objetos para adicionar o método "accept" para aceitar o visitor e a criação de uma classe separada para cada algoritmo, o que pode levar a um grande número de classes adicionais. Além disso, ele pode ser complicado de implementar em situações em que a estrutura de objetos é dinâmica e pode mudar durante a execução do programa.

**Fonte auxíliar:**
- https://refactoring.guru/design-patterns/visitor













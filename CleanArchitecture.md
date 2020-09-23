# Clean Architecture

## I - Introdução

### 1 - O que são Design e Arquitetura?

A **arquitetura** reflete os componentes do software (bem como suas macro-interações) em um alto nível de abstração. Aqui vemos as camadas do software, classes abstratas e interfaces.

Os detalhes de implementação, frameworks, bancos de dados, cache... estão em um baixo nível de abstração. Eles são encaixados no software de maneira a fazer toda a macro-estrutura funcionar.

A junção de tudo isso faz parte do **design** do sistema como um todo.

"O objetivo da arquitetura de software é minimizar os recursos humanos necessários para construir e manter um determinado sistema."

### 2 - Um conto de Dois Valores

Software deve ser "*soft*", fácil de mudar, desacoplado usando abstrações e interfaces.

## II - Começando com os Tijolos: Paradigmas de Programação

### 3 - Panorama do Paradigma

Estruturado, Orientado a Objetos e Funcional.

Os paradigmas tiram coisas do programador, restrigem o que ele pode fazer.

### 4 - Programação Estruturada

### 5 - Programação Orientada a Objetos

Uma mistura apropriada de **encapsulamento**, **herança** e **polimorfismo**.

**Inversão de Dependência**: O fato de que linguagens OO oferecem um polimorfismo seguro e conveniente significa que qualquer dependência de código fonte, não importa onde esteja, pode ser invertida.

Para o arquiteto de software, a OO é a habilidade de obter **controle absoluto**, através do uso do **polimorfismo**, sobre cada **dependência** de código fonte do sistema. Ela permite que o arquiteto crie uma **arquitetura de plug-in com módulos** que contêm políticas de alto nível, **independentes** dos módulos que contêm detalhes de baixo nível. Os detalhes de nível mais baixo são relegados a módulos de plug-ins, que podem ser implantados e desenvolvidos de maneira independente dos módulos que contêm políticas de alto nível.

### 6 - Programação Funcional

Lisp e Clojure.

O software — a matéria vital dos programas de computadores — é composto **apenas** de sequência, seleção, iteração e indireção. Nada mais. Nada menos.

## III - Princípios de Design: SOLID

### 7 - Single Responsibility Principle
### 8 - Open-Closed Principle
### 9 - Liskov Substitution Principle
### 10 - Interface Segregation Principle
### 11 - Dependency Inversion Principle

**Abstract Factory**

## IV - Princípios de Componentes

### 12 - Componentes

Componentes são **unidades de implantação**. Eles são as menores entidades que podem ser implantadas como parte de um sistema.

Em qualquer caso, quando efetivamente implantados, componentes bem projetados sempre retêm a capacidade de serem implantados de forma independente e, portanto, desenvolvidos independentemente.

Deve ser fácil plugar e desplugar um componente em software bem feito.

### 13 - Coesão de Componentes

**Reuse/Release Equivalence Principle**: as classes e módulos formados em um componente devem pertencer a um grupo coeso e devem ser passíveis de *release em conjunto*.

**Common Closure Principle**: um componente não deve ter várias razões para mudar.

"*Reúna em componentes as classes que mudam pelas mesmas razões e nos mesmos momentos. Separe em componentes  diferentes as classes que mudam em momentos diferentes e por diferentes razões.*"

**Common Reuse Principle**: devemos ter certeza de que as classes que colocamos em um componente são  *inseparáveis* - que é impossível depender de umas e não de outras. As classes que não têm uma forte ligação entre si não devem ficar no mesmo componente.

"Não force os usuários de um componente a dependerem de coisas que eles não precisam."

### 14 - Acoplamento de Componentes

**Acyclic Dependecies Principle**: não permita ciclos no *grafo de dependência* dos componentes. Directed Acyclic Graph (DAG). Utilize interfaces para inverter as dependências.

**Stable Dependecies Principle**: dependa na direção da estabilidade. Um componente que seja difícil de mudar não deve ser dependente de qualquer componente que esperamos que seja volátil. Caso contrário, o componente volátil também será difícil de mudar.

**Stable Abstractions Principle**: para que um componente seja estável, ele deve consistir de *interfaces e classes abstratas*, de modo que possa ser *estendido*. Os componentes estáveis extensíveis são flexíveis e não restringem demais a arquitetura. Logo, as dependências devem apontar na direção da abstração.

## V - Arquitetura

### 15 - O que é Arquitetura?

A arquitetura de um sistema de software é a **forma** dada a esse sistema pelos seus criadores. Essa forma está na *divisão* desse sistema em componentes, na *organização* desses componentes e nos modos como esses componentes se *comunicam* entre si.

O software foi inventado porque precisávamos de uma maneira rápida e fácil de **mudar o comportamento** das máquinas. Mas essa **flexibilidade** depende crucialmente da forma do sistema, da organização dos seus componentes e do modo como eles estão interconectados.

Para manter o seu software **soft**, deixe o máximo de opções possíveis abertas, pelo máximo tempo possível. Quais são as opções que precisamos deixar abertas? Elas são os detalhes que não importam.

Todos os sistemas de software podem ser decompostos em dois elementos principais:
    - **política**: engloba todas as *regras e procedimentos de negócios*. É onde está o verdadeiro *valor* do sistema.
    - **detalhes**: são itens necessários para que os seres humanos, outros sistemas e programadores *se comuniquem* com a política, mas que *não causam impacto* algum sobre o comportamento da política. Eles incluem dispositivos IO, banco de dados, cahe, sistemas web, servidores, frameworks, protocolos de comunicação e assim por diante.

O objetivo do arquiteto é criar uma forma para o sistema que reconheça a política como o elemento mais essencial do sistema e torne os detalhes irrelevantes para essa política. Isso permite que as decisões para esses detalhes sejam adiadas e diferidas.

Se desenvolver uma política de alto nível sem comprometer os seus respectivos detalhes, você poderá adiar e diferir decisões sobre esses detalhes por um bom tempo. E quanto mais você esperar para tomar essas decisões, mais informações terá para tomá-las adequadamente.

"*Um bom arquiteto deve maximizar o número de decisões não feitas.*"

**Independência de Dispositivo**: abstrair a interface de comunicação entre aplicação e dispositivo de IO. Existe um conector universal em ambos os lados. É como um USB.

### 16 - Indepedência

**Casos de Uso**: a arquitetura do sistema deve suportar a intenção do sistema, seus casos de uso.
**Operação**: a arquitetura do sistema deve apoiar a operação do sistema.
**Desenvolvimento**: a arquitetura deve facilitar o trabalho das equipes, particionando adequadamente o sistema em componentes independentemente desenvolvíveis (developable) e bem isolados.
**Implantação**: uma boa arquitetura ajuda o sistema a ser imediatamente implantável depois do build.

Uma boa arquitetura faz com que o sistema seja fácil de mudar, de todas as formas necessárias, ao deixar as opções abertas.

**Desacoplando os Casos de Uso**

Os casos de uso são uma maneira muito natural de dividir o sistema. Ao mesmo tempo, eles são fatias verticais estreitas que cortam através das camadas horizontais do sistema. 

Cada caso de uso usa um pouco da UI, um pouco das regras de negócio específicas da aplicação, um pouco das regras de negócio independentes da aplicação e um pouco da funcionalidade do banco de dados. Assim, quando
dividimos o sistema em camadas horizontais, também o dividimos em finos casos de uso verticais que passam através dessas camadas.

Observe o padrão presente aqui. Se você desacoplar os elementos do sistema que mudam por razões diferentes, poderá continuar a adicionar novos casos de uso sem interferir com os antigos. Se você também agrupar a UI e o banco de dados em suporte a esses casos de uso, para que cada caso de uso use um aspecto diferente da UI e do banco de dados, então adicionar novos casos de uso provavelmente não afetará os antigos.

### 17 - Fronteiras: Estabelecendo Limites

"A arquitetura de software é a arte de **estabelecer limites/fronteiras**."

Essas fronteiras *separam* os elementos de software uns dos outros e evitam que os elementos de um lado da fronteira *conheçam* os que estão do outro lado. Alguns desses limites são estabelecidos logo no início da vida de um projeto - até mesmo antes de qualquer código ser escrito. Outros são estabelecidos muito mais tarde. Os limites estabelecidos inicialmente atendem aos propósitos de adiar as decisões pelo máximo de tempo possível e evitar que essas decisões contaminem a lógica central dos negócios.

Que tipos de decisões são prematuras? Decisões que não têm nada a ver com os requerimentos do negócio - os  casos de uso - no sistema. São, entre outras, decisões sobre frameworks, banco de dados, servidores web,  bibliotecas de utilitários, injeção de dependência e similares. Em uma boa arquitetura de sistema, essas decisões são auxiliares e adiáveis. Uma boa arquitetura de sistema não depende dessas decisões, permitindo que elas sejam tomadas no último momento possível, sem impacto significante.

Estabeleça limites entre coisas que importam e coisas que não importam:
    - A GUI não importa para as regras de negócio, então deve haver um limite entre eles. 
    - O banco de dados não importa para a GUI, então deve haver um limite entre eles.
    - O banco de dados não importa para as regras de negócio, então deve haver um limite entre eles. 
    
Tudo o que as regras de negócio precisam saber é que há um *conjunto de funções* que pode ser usado para buscar ou salvar dados. Isso nos permite *colocar o banco de dados atrás de uma interface*. Ou seja, a decisão do banco de dados pode ser adiada, e você pode se concentrar em escrever e testar as regras de negócio antes de tomar essa decisão.

**Arquitetura Plug-In**
A história da tecnologia de desenvolvimento de software é a história de como criar plug-ins de maneira  conveniente para estabelecer uma arquitetura de sistema escalonável e sustentável. *As regras centrais de negócio são mantidas separadas e independentes desses componentes*, que podem ser opcionais ou implementados de muitas formas diferentes.

### 18 - Anatomia do Limite

### 19 - Política de Nível

Sistemas de software são declarações de política. Em essência, isso expressa o que um programa de computador realmente é: uma descrição detalhada de uma política que coordena a transformação de entradas em saídas.

Na maioria dos sistemas não triviais, essa política pode ser dividida em muitas declarações de política menores e diferentes. Algumas dessas declarações descreverão como regras de negócio específicas devem ser calculadas. Outras descreverão como certos relatórios devem ser formatados. Outras ainda descreverão como os dados de  entrada devem ser validados.

### 20 - Regras de Negócio  -> RELER COM ATENÇÃO

Estritamente, regras de negócio são regras ou procedimentos que **geram ou economizam o dinheiro** da empresa.

**Entidades**: *Dados e Regras Cruciais de Négocio*, que existem independentemente do software.

Uma **Entidade** é um objeto contido em nosso sistema de computador. Ela incorpora um pequeno conjunto de Regras Cruciais de negócios que operam com base nos Dados Cruciais de Negócios. O objeto Entidade contém os Dados Cruciais de Negócios ou tem acesso muito fácil a esses dados. A interface da Entidade consiste em funções que implementam as Regras Cruciais de Negócios que operam com base nesses dados.

Quando criamos esse tipo de classe, estamos reunindo o software que implementa um **conceito crucial** para o negócio e separando esse software de todas as outras questões do sistema automatizado que estamos construindo. Essa classe é **independente como representante do negócio**. Ela não está sujeita a questões relacionadas ao banco de dados, interfaces de usuários ou frameworks de terceiros. Poderia servir à empresa em qualquer sistema, sem restrições quanto à apresentação do sistema, ao armazenamento dos dados ou à organização dos computadores no sistema. **A Entidade é puro negócio e nada mais**.

**Casos de Uso**: regras de negócio que geram ou economizam dinheiro para a empresa ao *definirem e restringirem* a forma como um sistema automatizado opera. Elas não seriam usadas em um ambiente manual, pois só fazem sentido como parte de um sistema automatizado.

Um caso de uso é uma **descrição** da maneira como um sistema automatizado é usado. Ele **especifica** a entrada a ser fornecida pelo usuário, a saída a ser retornada para o usuário e os passos de processamento envolvidos na produção dessa saída. Um caso de uso descreve as regras de negócio específicas da aplicação,
diferentes das Regras Cruciais de Negócios contidas nas Entidades.

Os casos de uso contêm as **regras** que especificam como e quando as Regras Cruciais de Negócios dentro das entidades serão invocadas. Os casos de uso controlam a dança das Entidades, são maestros.

Os casos de uso não descrevem como o sistema aparece para o usuário. Em vez disso, descrevem regras específicas da aplicação que **regem a interação** entre os usuários e as Entidades. O modo como os dados entram e saem do sistema é irrelevante para os casos de uso.

Um caso de uso é um objeto. Ele tem uma ou mais funções que implementam as regras de negócio específicas da aplicação. Também tem elementos de dados que incluem os dados de entrada, os dados de saída e as referências para as devidas Entidades com as quais interage.

As entidades não conhecem os casos de uso que as controlam. Os conceitos de alto nível, como as Entidades, não sabem nada sobre os conceitos de nível mais baixo, como os casos de uso. Mas os casos de uso de nível mais baixo sabem sobre as Entidades de nível mais alto.

**Modelos de requisição e resposta**

Os casos de uso recebem dados de entrada e produzem dados de saída. Contudo, um objeto de caso de uso bem-formado não deve ter nenhum conhecimento sobre a **forma** como os dados são comunicados aos usuários ou a qualquer outro componente.

A classe de caso de uso aceita estruturas de dados de aquisição (request) simples como entrada e retorna estruturas de dados de resposta (response) simples como saída. Essas estruturas de dados são totalmente **independentes**. Elas não derivam de interfaces de framework padrão como HttpRequest e HttpResponse. Elas não sabem nada sobre a web nem compartilham nenhuma das armadilhas encontradas nas interfaces de usuários.

### 21 - Arquitetura Gritante

"*Arquiteturas de software são estruturas que suportam (GRITAM) os casos de uso do sistema.*"

Os frameworks são ferramentas à nossa disposição e não arquiteturas a que devemos nos resignar. Se a sua arquitetura é baseada em frameworks, ela não pode ser baseada nos seus casos de uso.

Uma boa arquitetura enfatiza os casos de uso e os desacopla das preocupações periféricas.

### 22 - Arquitetura Limpa

Características de sistemas com arquitetura limpa:
    - Independência de frameworks;
    - Testabilidade;
    - Independência da UI;
    - Independência do Banco de Dados;
    - Independência de qualquer agente externo;

As **Entidades** reúnem as Regras Cruciais de Negócios da empresa inteira. Elas podem ser usadas por muitas  aplicações diferentes na empresa.

O software da camada de **Casos de Uso** contém as regras de negócio específicas da aplicação. Ele reúne e implementa todos os casos de uso do sistema. Esses casos de uso *orquestram o fluxo de dados* para e a partir das entidades e orientam essas entidades na aplicação das Regras Cruciais de Negócios a fim de atingir os objetivos do caso de uso.

**Adaptadores de Interface**
O software da camada de adaptadores de interface consiste em um conjunto de adaptadores que *convertem* dados no formato que é mais conveniente para os casos de uso e entidades, para o formato mais conveniente para algum agente externo como a base de dados ou a web.

Também deve haver outro adaptador nessa camada para converter dados de forma externa, como um serviço externo, para a forma interna usada pelos casos de uso e entidades.

**Frameworks e Drivers**
Todos os detalhes ficam na camada de frameworks e drivers. *A web é um detalhe*. A base de dados é um detalhe. Mantemos essas coisas dolado de fora, onde não podem fazer mal nenhum.

**Quais dados cruzam os limites?**
Normalmente, os dados que cruzam os limites consistem em *estruturas de dados simples e isoladas*. Você pode usar estruturas básicas ou objetos de transferência de dados simples se quiser. Por outro lado, os dados podem ser apenas argumentos em chamadas de função. Não queremos trapacear nem transmitir objetos Entidade ou registros das bases de dados. Não queremos que as estruturas de dados tenham qualquer tipo de dependência que viole a Regra da Dependência.

Por exemplo, muitos frameworks de base de dados retornam um formato de dados conveniente em resposta a uma consulta. Podemos chamar isso de "estrutura de linha". Não queremos que essa estrutura atravesse o limite para dentro. Isso violaria a Regra da Dependência porque forçaria um círculo interno a saber algo sobre um círculo
externo.

Portanto, quando passamos os dados por um limite, eles devem sempre estar na forma mais conveniente para o círculo interno.

### 23 - Apresentadores e Objetos Humble

Os apresentadores são uma forma de padrão de Objeto Humble que ajuda a identificar e proteger os limites arquiteturais.

### 24 - Limites Parciais

Um limite arquitetural totalmente desenvolvido usa **interfaces recíprocas de limites** para manter o **isolamento** em ambas as direções. Manter a separação em ambas as direções é **caro** tanto na configuração inicial quanto na manutenção contínua.

Patterns: Strategy, Facade.

### 25 - Camadas e Limites

Há limites arquiteturais em toda parte. Todos tem um custo associado. Cabe ao arquiteto ponderar se vale a pena desenvolvê-los.

### 26 - O Componente Main

Componente que cria, coordena e supervisiona os outros.

É o detalhe final - a **política de nível mais baixo**. É o ponto de entrada inicial do sistema. Nada, além do sistema operacional, depende dele. Seu trabalho é criar todas as Factories, Strategies e outros **utilitários globais** e, então, entregar o controle para as porções abstratas de alto nível do sistema.

É nesse componente Main que as dependências devem ser injetadas por um framework de Injeção de Dependência. Uma vez injetadas em Main, o Main distribui essas dependências normalmente, sem usar o framework.

Aqui, o ponto é que Main representa um módulo sujo de baixo nível no círculo mais externo da arquitetura limpa. Ele carrega tudo para o sistema de alto nível e, então, entrega o controle para ele.

Pense em Main como um **plug-in da aplicação** - um plug-in que configura as condições e configurações iniciais, reúne todos os recursos externos e, então, entrega o controle para a política de alto nível da
aplicação. Por serem plug-ins, é possível ter muitos componentes Main, um para cada configuração da sua aplicação.

### 27 - Serviços: Grandes e Pequenos

**Benefícios dos Serviços ?**
    - Desacoplamento: os serviços são *fortemente acoplados* ao registro de dados e, portanto, indiretamente acoplados uns aos outros;
    - Desenvolvimento e Implantação Independentes: os serviços são todos acoplados e não podem ser desenvolvidos, implantados e mantidos de forma independente.

### 28 - O Limite Teste

Os testes são parte do sistema e participam da arquitetura como todas as outras partes do sistema.

Os testes, por natureza, seguem a Regra da Dependência. Além disso, são muito detalhados e concretos e sempre **dependem internamente** do código que está sendo testado. De fato, você pode pensar nos testes como o círculo mais externo na arquitetura. Nada dentro do sistema depende dos testes, e os testes sempre dependem internamente dos componentes do sistema.

Sua função é apoiar o desenvolvimento, não a operação. 

Projete o sistema e os testes de modo que as regras de negócio possam ser testadas sem a utilização da GUI. Crei uma super API de testes.

### 29 - Arquitetura Limpa Embarcada

## VI - Detalhes

### 30 - A Base de Dados é um Detalhe

A base de dados é um pedaço de software, uma **utilidade** que fornece acesso aos dados. Do ponto de vista da
arquitetura, essa utilidade é irrelevante porque é um **detalhe de baixo nível**, um **mecanismo**. E uma arquitetura boa não permite que mecanismos de baixo nível poluam a arquitetura do sistema.

Faça essa pergunta: quando não existirem mais discos, e todos os seus dados forem armazenados na RAM, como você organizará esses dados? Organizará em tabelas e acessará com SQL? Em arquivos acessíveis por meio de diretórios?

É claro que **não**. Você organizará os dados em listas encadeadas, árvores, tabelas hash, pilhas, filas ou qualquer outra das inúmeras estruturas de dados, que acessará usando ponteiros ou referências - porque *é isso que os programadores fazem*.

### 31 - A Web é um Detalhe

GUI é um detalhe, um dispositivo IO. E, como arquiteto, você deve colocar detalhes como esses atrás de limites que os mantenham separados da sua lógica de negócios central.

### 32 - Frameworks são Detalhes

Não case com o framework!

Não deixe os frameworks entrarem em seu código central. Em vez disso, integre-os em componentes que operem como plug-ins no código central, de acordo com a Regra da Dependência. Talvez você possa encontrar uma maneira de conseguir o leite sem comprar a vaca.

# Como identificar os Casos de Uso?
1 - Identifique quem são os **atores**, quem executa os casos de uso. **Role matters**.
    - Em um sistema de faturamento:
        - Customer, Subscriber, Accountant, Treasurer, Employee;
    - Em um blog:
        - Editor, Reviewer, Guest, Author;
    - Em uma plataforma de recrutamento:
        - JobSeeker, Employer, Interviewer, Recruiter;
    - Em uma companhia de makething de emails:
        - Contact, Recipient, Sender, ListOwner;
2 - Saiba que eles são **comandos ou consultas**
    - Command-Query Segregation:
        - um método é um COMANDO que executa uma ação OU uma QUERY que retorna dados ao chamador, mas nunca ambos;
        - COMMANDS executam alterações no sistema, mas não retorna nenhum valor;
        - QUERIES extraiem dados do sistema, mas não produzem efeitos colaterais;
        - Eles devem ser SEPARADOS!
3 - E que pertencem a um **subdomínio específico** que pode ser implantado em **bounded contexts** separados;
    - A parte de login/logout pertence a um subdomínio genérico. 
        - Podemos usar ferramentas externas para fazer isso, como o Auth0;
    - A camada de Aplicação contém os Casos de Uso (funcionalidades / recursos / serviços disponibilizados pelo app) de um determinado Subdomínio da aplicação;



# DDD Distilled

**Models are everywhere. They help us to simplify things and understand it.**

## 1 - DDD for Me

"DDD is a **set of tools** that assist you in designing and implementing **software that delivers high value, both strategically and tactically.**"

### Strategic Design
First you will learn how to **segregate your domain models** using the strategic design pattern called **Bounded Contexts**. Hand in glove, you will see how to develop a **Ubiquitous Language** as your domain model within an explicitly **Bounded Context**.

You will learn about **Subdomains** and how these can help you deal with the **unbounded complexity** of legacy systems, and how to improve your results on greenfield projects.

You will also see how to integrate multiple **Bounded Contexts** using a technique called **Context Mapping**. Context Maps define both team **relationships and technical mechanisms** that exist between two integrating Bounded Contexts.

### Tactical Design
Tactical design is like using a thin brush to paint the **fine details** of your domain model.

One of the more important tools is used to **aggregate entities and value objects** together into a right-sized cluster. It’s the **Aggregate pattern**.

DDD is all about **modeling your domain in the most explicit way possible**.

Using **Domain Events** will help you both to model explicitly and to share what has occurred within your model with the systems that need to know about it. The interested parties might be your own local Bounded Context and other remote Bounded Contexts.

## 2 - Strategic Design with Bounded Contexts and the Ubiquitous Language

In short, DDD is primarily about **modeling a Ubiquitous Language in an explicitly Bounded Context**.

**Bounded Context** is a semantic contextual boundary. This means that within the boundary each component of the software model has a specific meaning and does specific things. The components inside a Bounded Context are context specific and semantically motivated.

**Ubiquitous Language** is a language that is developed by the team working in the Bounded Context and is spoken by *every member* of the team that creates the software model that functions within that Bounded Context. Thus, it is necessary that she be rigorous, strict, exact, stringent, and tight.

When the Bounded Context is being developed as a **key strategic** initiative of your organization, it’s called the **Core Domain**.

Focus on Business Complexity, Not Technical Complexity.

Use **Event Storming** sessions for discovery the Ubiquitous Language.

Technology-Free Domain Model.

Architectures or architecture patterns
- Event-Driven Architecture;
- Command Query Responsibility Segregation (CQRS);
- Representational State Transfer (REST);
- Service-Oriented Architecture (SOA);
- Microservices;
- Cloud;

## 3 - Strategic Design with Subdomains

Simply stated, a Subdomain is a **sub-part** of your overall business domain. You can think of a Subdomain as representing a single, logical domain model.

There are three primary types of Subdomains within a project:
- **Core Domain**: This is where you are making a strategic investment in a single, well-defined *domain model*, committing significant resources for carefully crafting your *Ubiquitous Language* in an explicit *Bounded Context*.
- **Supporting Subdomain**: This is a modeling situation that calls for custom development, because an off-the-shelf solution doesn’t exist. However, you will still not make the kind of investment that you have made for your Core Domain. You may want to consider outsourcing this kind of Bounded Context to avoid mistaking it for something *strategically distinguishing*, and thus investing heavily in it. This is still an important software model, because your Core Domain cannot be successful without it.
- **Generic Subdomain**: This kind of solution may be available for purchase off the shelf but may also be *outsourced* or even developed in house by a team that doesn’t have the kind of elite developers that you assign to your Core Domain or even a lesser Supporting Subdomain. Be careful not to mistake a Generic Subdomain for a Core Domain. You don’t want to make that kind of investment here.

## 4 - Strategic Design with Context Mapping

A **Context Mapping** is a diagram that represents the **relationships and integrations** between Bounded Contexts.

Kinds of Mappings
- **Partnership**: exists between two teams. Each team is responsible for one Bounded Context. It is said that the two teams will succeed or fail together;
- **Shared Kernel**: describes the relationship between two (or more) teams that share a small but common model;
- **Customer-Supplier**: describes a relationship between two Bounded Contexts and respective teams, where the Supplier is **upstream** and the Customer is **downstream**. The Supplier holds sway in this  relationship because it must provide what the Customer needs;
- **Conformist**: exists when there are upstream and downstream teams, and the upstream team has no motivation to support the specific needs of the downstream team;
- **Anti-Corruption Layer**: is the most defensive Context Mapping relationship, where the downstream team creates a *translation layer* between its Ubiquitous Language (model) and the Ubiquitous Language (model) that is upstream to it. The layer *isolates* the downstream model from the upstream model and translates between the two. Thus, this is also an approach to integration;
- **Open Host Service**: defines a *protocol or interface* that gives access to your Bounded Context as a *set of services*. The protocol is "open" so that all who need to integrate with your Bounded Context can use it with relative ease. The services offered by the *application programming interface* (API) are well documented and a pleasure to use;
- **Published Language**: is a well-documented information exchange language (XML, JSON) enabling simple consumption and translation by any number of consuming Bounded Contexts. Consumers who both read and write can translate from and into the shared language with confidence that their integrations are correct. This combination makes the translations between two Ubiquitous Languages very convenient;
- **Separate Ways**: describes a situation where integration with one or more Bounded Contexts will not produce significant payoff through the consumption of various Ubiquitous Languages. Perhaps the functionality that you seek is not fully provided by any one Ubiquitous Language. In this case produce your own specialized solution in your Bounded Context and *forget integrating* for this special case;

**Big Ball of Mud**
- A growing number of Aggregates cross-contaminate because of unwarranted connections and dependencies;
- Maintaining one part of the Big Ball of Mud causes ripples across the model, which leads to “whack-a-mole” issues;
- Only tribal knowledge and heroics - speaking all languages at once - save the system from complete collapse;

**Making Good Use of Context Mapping for Integration of Bounded Contexts**
- Remote Procedure Call (RPC) with Simple Object Access Protocol (SOAP);
- RESTful HTTP;
- Messaging;

## 5 - Tactical Design with Aggregates

Each Aggregate is composed of one or more **Entities**, where one Entity is called the **Aggregate Root**. Aggregates may also have **Value Objects** composed on them. Value Objects are used inside **both** Aggregates.

Each Aggregate forms a **transactional consistency boundary**. This means that within a single Aggregate, all composed parts must be consistent, according to business rules, when the controlling transaction is committed to the database. This doesn’t necessarily mean that you are not supposed to compose other elements within an Aggregate that don’t need to be consistent after a transaction. After all, an Aggregate also models a conceptual whole.

**Rules of Aggregate Design**
1. Protect business invariants inside Aggregate boundaries;
2. Design small Aggregates;
3. Reference other Aggregates by identity only;
4. Update other Aggregates using eventual consistency;

## 6 - Tactical Design with Domain Events

Is a record of some **business-significant occurrence** in a Bounded Context.

## 7 - Acceleration and Management Tools




0 - Strategic Design
    1 - Abstrair/modelar o domínio real e complexo
        2 - Dividir esse modelo do domínio em subdomains
            - Core Domain;
            - Supporting Subdomain;
            - Generic Subdomain;
                3 - Cada subdomínio é formado por Bounded Contexts, que contém sua própria Ubiquitous Language
                    4 - As relações existentes entre os Bounded Contexts são mostradas em Context Mappings

# Resumo do DDD

Awesome DDD
https://github.com/heynickc/awesome-ddd

Monolito com DDD
https://github.com/kgrzybek/modular-monolith-with-ddd

PalyList do Elemar Jr
https://www.youtube.com/watch?v=2X9Q97u4tUg&list=PLkpjQs-GfEMN8CHp7tIQqg6JFowrIX9ve&index=1

Trazer para dentro do sistema as operações do negócio.
Os processos feitos no negócio devem ser contemplados nos casos de uso.

Value Objects
https://enterprisecraftsmanship.com/posts/value-object-better-implementation/

https://khalilstemmler.com/articles/domain-driven-design-intro/

https://khalilstemmler.com/articles/software-design-architecture/full-stack-software-design/

- Criar uma **Rica Camada de Domínio**, utilizando os princípios **SOLID** de design.
- Utilizar **dependency inversion and injection** e **interface adapters** para conectar tecnologias externas (banco de dados, frameworks, caches, web servers, UI...) à aplicação. A infraestrutura não deve sujar o domínio.

**Building Blocks**
- Entities:
    - Domain objects that we care to uniquely identify.
    - User, Job, Post, Comment, Video, Lesson...
    - Status: created, updated, persisted, retrieved from persistence, archived and deleted.
    - Entities are *compared* by their unique identifier (usually a UUID or Primary Key of some sort).
- Value Objects:
    - They have no identity. They are *attributes* of Entities.
    - Name as a Value Object on a User.
    - JobStatus as a Value Object on Job.
    - PostTitle as a Value Object on Post.
    - Value Objects are compared by their *structural equality*.
- Aggregates:
    - These are a collection of entities are that bound together by an *aggregate root*.
    - They dispatch Domain Events which can be used to co-locate business logic in the appropriate subdomain.
- Domain Services:
    - This is where we locate domain logic that doesn't belong to any one object conceptually.
- Repository:
    - We use repositories in order to retrieve domain objects from persistence technologies.
    - Uma abstração/interface, para permitir que a base da dados seja mudada sem muito esforço.
- Factory:
    - para criar objetos de várias maneiras diferentes.
    - ORM tools (like Sequelize or TypeORM).
    - Prototype Pattern, Abstract Factory.
- Domain Events:
    - Domain events are simply objects that define some sort of event that occurs in the domain that domain experts care about.
    - **Registro** da ocorrência de um evento significativo para aquele contexto delimitado:
        - Acarreta na mudança de estado de alguma parte do sistema;
        - Exemplos:
            - Mudar o endereço do cliente;
            - Aumentar o salário de um funcionário;
            - Registrar um novo pedido;
    - É representado como uma classe:
        - Seu nome é o mesmo do evento, descrito no passado;
        - Contém um atributo com o instante no tempo onde o evento ocorreu;
        - Além de outras propriedades que possam ser relevantes no contexto do evento;
        - Esse classe DESCREVE o evento / mudança de estado;
    - Geralmente esse evento é convertido em menssagem em um mecanismo de mensageria (RabitMQ...);
        - Usar uma interface para desacoplar a ferramenta da política de alto nível;
    - Ele também pode ser persistido em um Banco de Dados;
        - Event Sourcing;

Padrão Repository
    - É como se fosse **coleção** em memória de todos os objetos de um determinado tipo;
    - Uma abstração que permite:
        - Adicionar objetos;
        - Retirar objetos;
        - Alterar objetos;
        - Acessar/recuperar objetos via id;
        - Um interface que abstrai o banco de dados de quem o usa;
        - Acarreta no uso do princípio de Inversão de Dependência;
        - Em geral, cada agregado possui seu próprio repositório;



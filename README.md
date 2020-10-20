# Implementing-DDD

Principais tópicos cobertos no Implementing Domain-Driven Design, do Vaughn Vernon.

## Chapter 1 - Getting Started with DDD





O DDD serve para nos ajudar a desenvolver softwares de alta qualidade, que realmente modelam o domínio do negócio e agregam valor de forma significativa, estratégica e táticamente.

Para isso, o entendimento do negócio é fundamental. Todos devem falar a mesma **Ubiquitous Language**.

Como desenvolver a Ubiquitous Language?
- Falar com os **Domain Experts**, para que descrevam **processos** que ocorrem no negócio. Extrair daí os casos de uso. Usar diagramas, UML ou similar para representar esses processos.
- Perceber que cada **contexto** do negócio têm sua própria linguagem, para se referir às mesmas **entidades** às vezes.
- Criar um glossário de termos para cada contexto, com cada significado explicado, além de exemplos.

DDD Scorecard: tabela com necessidades da aplicação, associadas a pontuações, para decidir se vale a pena usar DDD no seu projeto. Basicamente, não use DDD em projetos simples.

## Chapter 2 - Domains, Subdomains and Bounded Contexts



## Chapter 6 - Value Objects

São um **bloco de construção fundamental** do DDD. Podem ser números, textos, moedas, telefones, endereços, documentos... enfim, qualquer *`Valor`* que modele *`conceitos do domínio`*, usando sua *`Linguagem Ubíqua`*.

Eles são **fáceis** de criar, testar, usar, otimizar e manter.

Geralmente são usados como **atributos** para as *`Entidades`*.

Reduzem a **complexidade** da integração entre conceitos.

Evitam que conceitos do domínio sejam modelados como **entidades anêmicas**, frutos de um design voltado para o banco de dados.

Pense em uma *`String`* ou uma *`Data`*: ambas são modelos de conceitos, armazenam dados internamente e expõe operações através de suas interfaces. A ideia aqui com os Objetos de Valor é criar tipos diretamente ligados ao domínio, que também possuam essas características.

Podiam ser chamados de *`Domain Types`*.

### Características
- Mede, quantifica ou descreve alguma *coisa do domínio*.
- Pode ser mantido como *imutável*.
- Modela um *todo conceitual*, compondo atributos relacionados como uma unidade integral.
- É *completamente substituível* quando precisa ser mudado.
- Pode ser comparado com outros usando apenas a *igualdade de valores*.
- Fornece aos seus utilizadores um *comportamento livre de efeitos colaterais*.

### Integre com minimalismo


### Tipos Padrão expressos como Valores


### Testando Value Objects

### Implementação

### Persistindo Value Objects

### Wrap-Up



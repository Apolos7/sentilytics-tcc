## Tecnologias e Ferramentas

O desenvolvimento da aplicação de análise de sentimentos envolveu o uso de diversas tecnologias e ferramentas que possibilitaram a implementação eficiente da solução. A seguir, são apresentadas as principais tecnologias utilizadas, bem como as ferramentas empregadas no processo de desenvolvimento.

### Python

O Python é uma linguagem de programação amplamente utilizada para tarefas de Processamento de Linguagem Natural (PLN) devido à sua sintaxe acessível e ao amplo suporte de bibliotecas voltadas para esse domínio. Entre os recursos disponíveis, destacam-se ferramentas como o Natural Language Toolkit (NLTK), que fornece funcionalidades para tokenização, remoção de stopwords, stemming e lematização, e o Enelvo, uma biblioteca voltada para a normalização de textos em português \cite{bertaglia2016exploring}. Essas bibliotecas possibilitam a manipulação eficiente de textos, sendo frequentemente aplicadas em soluções que envolvem análise automática de conteúdos.

<!-- Além disso, o Python é amplamente utilizado em sistemas que exigem integração entre diferentes serviços, sendo compatível com diversas abordagens para processamento assíncrono e comunicação entre módulos. Esse suporte permite que a linguagem seja empregada em arquiteturas distribuídas, especialmente em aplicações que realizam análises em grande volume de dados. -->
### Spring Boot

O Spring Boot é um framework Java voltado para o desenvolvimento de aplicações web e serviços backend, oferecendo uma abordagem simplificada para a configuração e execução de sistemas baseados no ecossistema Spring. Ele possibilita a criação de aplicações modulares e escaláveis, reduzindo a necessidade de configurações manuais extensivas e proporcionando integração com diversas tecnologias, como bancos de dados, filas de mensagens e processamento em lote.

Além do suporte para APIs REST, o Spring Boot conta com o Spring Batch, uma extensão projetada para lidar com grandes volumes de dados por meio de processamento assíncrono e em lote. Esse módulo é amplamente utilizado em cenários que exigem a importação e transformação de grandes conjuntos de informações de forma eficiente e estruturada.

<!-- A flexibilidade do framework também permite sua integração com soluções de mensageria, como o RabbitMQ, e sistemas de banco de dados relacionais, como o PostgreSQL, facilitando a construção de arquiteturas distribuídas e escaláveis. -->
### Angular

O Angular é um framework front-end baseado em TypeScript, desenvolvido e mantido pelo Google, voltado para a criação de aplicações web dinâmicas e escaláveis. Ele adota uma arquitetura modular baseada em componentes reutilizáveis, proporcionando um desenvolvimento estruturado e facilitando a manutenção do código. <!-- Além disso, seu sistema de data binding permite a sincronização eficiente entre a interface e os dados da aplicação, tornando a experiência do usuário mais fluida. -->

No desenvolvimento de interfaces, o Angular pode ser combinado com bibliotecas de estilização como o Tailwind CSS, um framework CSS utilitário que permite a criação de layouts responsivos e altamente customizáveis, reduzindo a necessidade de estilos manuais.

### RabbitMQ

O RabbitMQ é um sistema de mensageria de código aberto utilizado para comunicação assíncrona entre serviços, permitindo a troca de mensagens de forma eficiente e desacoplada. Ele funciona como um intermediário que gerencia filas de mensagens, garantindo que os componentes de um sistema possam se comunicar sem dependências diretas, o que contribui para a escalabilidade e resiliência da aplicação.

O RabbitMQ opera por meio do modelo Produtor-Consumidor, onde mensagens são publicadas em filas e processadas por serviços que as consomem conforme sua disponibilidade. Essa abordagem permite a distribuição de carga e melhora o desempenho em aplicações que lidam com grandes volumes de processamento, evitando bloqueios e garantindo que as solicitações sejam tratadas de forma ordenada.

Além disso, o RabbitMQ pode ser integrado a diferentes tecnologias, oferecendo suporte para diversos protocolos e padrões de comunicação, como AMQP (Advanced Message Queuing Protocol). Sua arquitetura permite o gerenciamento de múltiplas filas e consumidores, otimizando o processamento paralelo e a distribuição eficiente de tarefas.

### PostgreSQL

O PostgreSQL é um sistema de gerenciamento de banco de dados relacional (SGBD) de código aberto, reconhecido por sua conformidade com padrões SQL e suporte a transações ACID (Atomicidade, Consistência, Isolamento e Durabilidade). Ele oferece mecanismos para garantir a integridade dos dados e eficiência na execução de consultas.

Além de suas funcionalidades relacionais, o PostgreSQL permite o uso de índices personalizados, replicação e extensões para aprimoramento do desempenho e escalabilidade. Sua compatibilidade com diversas linguagens e frameworks possibilita a integração com diferentes tipos de aplicações.

### Intellij IDEA

O IntelliJ IDEA é um ambiente de desenvolvimento integrado (IDE) voltado para a criação de aplicações em Java e Kotlin. Desenvolvido pela JetBrains, oferece suporte a diversas tecnologias e frameworks, além de ferramentas de depuração e controle de versão que auxiliam no processo de desenvolvimento.

A IDE conta com recursos como autocompletar código, análise estática e refatoração, proporcionando um ambiente estruturado para a escrita e manutenção de código. Sua compatibilidade com frameworks como Spring Boot e ferramentas de automação como Maven facilita a configuração e o gerenciamento de projetos Java.

### PyCharm

O PyCharm é um ambiente de desenvolvimento integrado (IDE) voltado para aplicações em Python, desenvolvido pela JetBrains. Ele oferece suporte a frameworks e bibliotecas da linguagem, além de ferramentas de depuração, análise de código e controle de versão.

A IDE conta com recursos como autocompletar de código, refatoração automatizada e suporte a testes unitários, facilitando a escrita e manutenção de código.

<!-- Além disso, sua compatibilidade com bibliotecas voltadas para machine learning, análise de dados e processamento de linguagem natural (PLN) torna-o adequado para projetos que envolvem manipulação e análise de textos. -->
### Visual Studio Code (VS Code)

O Visual Studio Code (VS Code) é um editor de código-fonte desenvolvido pela Microsoft, amplamente utilizado devido à sua leveza, extensibilidade e suporte a diversas linguagens de programação. Ele conta com recursos como realce de sintaxe, IntelliSense (autocompletar inteligente) e integração com ferramentas externas, facilitando o desenvolvimento e a depuração de código.

### DBeaver

O DBeaver é uma ferramenta universal de administração de bancos de dados, compatível com diversos sistemas de gerenciamento de banco de dados (SGBDs), incluindo PostgreSQL, MySQL, SQL Server e outros. Ele fornece uma interface gráfica para executar queries SQL, visualizar e editar tabelas, além de gerenciar conexões com diferentes bancos de dados.

A ferramenta também permite a exportação de dados em diferentes formatos, facilitando a análise externa e a validação das informações armazenadas. Além disso, oferece suporte a diversos recursos avançados, como modelagem de dados, execução de scripts e monitoramento de desempenho das consultas.

### Vertabelo

O Vertabelo é uma ferramenta online para modelagem de bancos de dados, permitindo a criação de esquemas relacionais de forma visual. Ele fornece suporte à modelagem Entidade-Relacionamento (ER), facilitando a definição de tabelas, chaves primárias e estrangeiras, além da geração automática do código SQL e dicionário de dados correspondente.

A plataforma possibilita ajustes no modelo sem a necessidade de instalação de software adicional. Ainda mais, a plataforma oferece a exportação de diagramas para diferentes formatos, auxiliando na documentação e na comunicação entre equipes de desenvolvimento.

### Postman

O Postman é uma ferramenta utilizada para desenvolvimento, teste e documentação de APIs, permitindo a realização de requisições HTTP de maneira prática. Ele suporta diferentes métodos de requisição, como GET, POST, PUT e DELETE, possibilitando a verificação do funcionamento dos endpoints e a validação das respostas retornadas pelo servidor.

A ferramenta também permite a visualização de dados em formatos como JSON e XML, além de oferecer recursos para organização de coleções de requisições e automação de testes. Outra funcionalidade relevante é o gerenciamento de variáveis de ambiente, facilitando a adaptação de requisições para diferentes contextos, como desenvolvimento e produção.

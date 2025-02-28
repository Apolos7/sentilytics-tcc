## Tecnologias e Ferramentas

O desenvolvimento da aplicação de análise de sentimentos contou com o uso de diversas tecnologias e ferramentas, as quais foram essenciais para a implementação eficiente da solução. A seguir, são descritas as principais tecnologias empregadas e os respectivos papéis que desempenharam na construção da aplicação.

### Python

O Python[^python] é uma linguagem de programação amplamente utilizada para tarefas de Processamento de Linguagem Natural (PLN) devido à sua sintaxe acessível e ao amplo suporte de bibliotecas voltadas para esse domínio. Entre os recursos disponíveis, destacam-se ferramentas como o *Natural Language Toolkit* (NLTK), que fornece funcionalidades para tokenização, remoção de *stopwords*, *stemming* e lematização, e o Enelvo, uma biblioteca voltada para a normalização de textos em português \cite{bertaglia2016exploring}. Essas bibliotecas possibilitam a manipulação eficiente de textos, sendo frequentemente aplicadas em soluções que envolvem análise automática de conteúdos.

No desenvolvimento do Sentilytics, o Python foi utilizado para implementar o serviço responsável pelo pré-processamento e pela análise de sentimentos das postagens coletadas. Esse serviço é projetado para funcionar de forma assíncrona e escalável, utilizando o RabbitMQ como sistema de mensageria para gerenciar os processos. Dessa forma, é possível processar grandes volumes de dados de maneira organizada.

O pré-processamento é iniciado quando o serviço recebe uma mensagem pelo RabbitMQ, indicando que deve buscar na base de dados os textos brutos e as tarefas de pré-processamento configuradas pelo usuário. Após essa busca, o serviço aplica as tarefas selecionadas aos textos coletados. Essas tarefas podem incluir:

- Remoção de stopwords: Eliminação de palavras irrelevantes para a análise, como "de", "o", "para".
- Normalização e lematização: Ajuste dos textos para uniformidade e redução de palavras à sua forma base.
- Correção ortográfica: Identificação e ajuste de erros ortográficos nos textos.

Essas etapas garantem que os dados sejam limpos e livres de ruídos, tornando-os adequados para a análise de sentimentos. Após o término do pré-processamento, o texto resultante é salvo na base de dados e uma mensagem é enviada via RabbitMQ, notificando o término do processo.

A análise de sentimentos também é gerenciada por meio do RabbitMQ, que envia uma mensagem para iniciar o processo. A partir dessa notificação, o serviço recupera as postagens pré-processadas da base de dados e aplica o modelo de análise de sentimentos VADER, fornecido pela biblioteca NLTK. Esse modelo, por sua leveza e facilidade de implementação, foi escolhido para esta versão do Sentilytics. Após a análise, os resultados são armazenados na base de dados, e uma mensagem é enviada pelo RabbitMQ informando o término do processo.

Embora atualmente apenas o VADER esteja integrado à solução, a arquitetura do Sentilytics foi projetada para permitir futuras expansões. Isso inclui a possibilidade de integrar novos modelos de análise de sentimentos e oferecer ao usuário a opção de selecionar o modelo desejado, da mesma forma como ocorre com a configuração das tarefas de pré-processamento.

[^python]: O site do python está disponível no link: <https://www.python.org/>

### Spring Boot

O Spring Boot[^spring_boot] é um framework Java voltado para o desenvolvimento de aplicações web e serviços backend, oferecendo uma abordagem simplificada para a configuração e execução de sistemas baseados no ecossistema Spring. Ele possibilita a criação de aplicações modulares e escaláveis, reduzindo a necessidade de configurações manuais extensivas e proporcionando integração com diversas tecnologias, como bancos de dados, filas de mensagens e processamento em lote.

Além do suporte para APIs REST, o Spring Boot conta com o Spring Batch, uma extensão projetada para lidar com grandes volumes de dados por meio de processamento assíncrono e em lote. Esse módulo é amplamente utilizado em cenários que exigem a importação e transformação de grandes conjuntos de informações de forma eficiente e estruturada.

No desenvolvimento do Sentilytics, o Spring Boot foi utilizado para construir dois serviços principais, cada um desempenhando um papel fundamental na arquitetura da aplicação:

1. Web API (Spring Boot REST API) – Esse serviço atua como o núcleo de comunicação da aplicação, centralizando todas as operações e integrando os diferentes módulos do sistema. Ele expõe os endpoints REST que permitem a interação com o frontend em Angular e gerencia a inicialização dos serviços oferecidos pelo módulo em Python, como o pré-processamento e a análise de sentimentos, utilizando o RabbitMQ para troca de mensagens.
Além disso, a API é responsável pela coleta de dados no Bluesky, lidando com a autenticação necessária e garantindo a ingestão segura das postagens na base de dados PostgreSQL. A escolha do Bluesky como rede social integrada se deu principalmente devido à política de gratuidade na coleta de postagens, o que viabilizou a realização deste estudo de caso. Apesar de o Bluesky ainda não ser amplamente utilizado no Brasil, sua estrutura e acessibilidade tornam-no uma escolha viável para a demonstração das funcionalidades do Sentilytics.
A API também gerencia os workflows e coordena as operações realizadas dentro da plataforma, garantindo que cada requisição seja processada de maneira consistente.

1. Spring Batch – A segunda aplicação desenvolvida com Spring Boot foi um serviço baseado no Spring Batch, utilizado para a importação e processamento de dados a partir de arquivos CSV. Esse recurso permite que os usuários superem a limitação atual de depender exclusivamente do Bluesky como fonte de dados, possibilitando a análise de qualquer conjunto de textos formatados em arquivos CSV. Dessa forma, a plataforma se torna mais versátil e capaz de atender a diferentes necessidades analíticas, independentemente da origem dos dados.
O Spring Batch garante que a solução lide com grandes quantidades de postagens sem comprometer o desempenho da plataforma, validando e processando os dados de forma eficiente antes de armazená-los no banco de dados.

A utilização do Spring Boot no projeto possibilitou uma estrutura modular, escalável e organizada, facilitando a manutenção e a expansão do sistema conforme novas funcionalidades forem incorporadas.

[^spring_boot]: A documentação do Spring Boot está disponível no link: <https://spring.io/projects/spring-boot>

### Angular

O Angular[^angular] é um framework front-end baseado em TypeScript, desenvolvido e mantido pelo Google, voltado para a criação de aplicações web dinâmicas e escaláveis. Ele adota uma arquitetura modular baseada em componentes reutilizáveis, proporcionando um desenvolvimento estruturado e facilitando a manutenção do código.

No desenvolvimento de interfaces, o Angular pode ser combinado com bibliotecas de estilização como o Tailwind CSS, um framework CSS utilitário que permite a criação de layouts responsivos e altamente customizáveis, reduzindo a necessidade de estilos manuais.

No desenvolvimento do Sentilytics, o Angular foi utilizado como o framework principal para construção do frontend. Para facilitar a estilização e responsividade, o framework foi utilizado em conjunto com o Tailwind CSS, que possibilitou a criação de um design moderno e consistente sem a necessidade de escrever estilos CSS extensos.

A interface foi projetada para proporcionar uma navegação intuitiva, organizando as diferentes etapas do fluxo da aplicação, desde o cadastro da pesquisa, passando pela coleta e processamento dos dados, até a visualização dos resultados da análise de sentimentos.

Além disso, para garantir uma experiência em tempo real, foi implementado o protocolo Server-Sent Events (SSE), que permite a comunicação assíncrona entre o backend e o frontend. Esse mecanismo foi utilizado para notificar os usuários sobre o andamento de processos demorados, como o pré-processamento dos textos e a execução da análise de sentimentos. Dessa forma, os usuários podem acompanhar o progresso das operações sem a necessidade de recarregar a página ou realizar requisições manuais para obter atualizações.

[^angular]: A documentação do Angular está disponível no link: <https://angular.dev/>

### RabbitMQ

O RabbitMQ[^rabbitmq] é um sistema de mensageria de código aberto utilizado para comunicação assíncrona entre serviços, permitindo a troca de mensagens de forma eficiente e desacoplada. Ele funciona como um intermediário que gerencia filas de mensagens, garantindo que os componentes de um sistema possam se comunicar sem dependências diretas, o que contribui para a escalabilidade e resiliência da aplicação.

O RabbitMQ opera por meio do modelo Produtor-Consumidor, onde mensagens são publicadas em filas e processadas por serviços que as consomem conforme sua disponibilidade. Essa abordagem permite a distribuição de carga e melhora o desempenho em aplicações que lidam com grandes volumes de processamento, evitando bloqueios e garantindo que as solicitações sejam tratadas de forma ordenada.

Além disso, o RabbitMQ pode ser integrado a diferentes tecnologias, oferecendo suporte para diversos protocolos e padrões de comunicação, como AMQP (Advanced Message Queuing Protocol). Sua arquitetura permite o gerenciamento de múltiplas filas e consumidores, otimizando o processamento paralelo e a distribuição eficiente de tarefas.

O RabbitMQ foi utilizado como broker de mensagens para possibilitar a comunicação assíncrona entre o serviço de pré-processamento e análise de sentimentos em Python e a API REST desenvolvida em Spring Boot. Por meio desse mecanismo, as requisições de processamento são enviadas para filas de mensagens, permitindo que o sistema execute as operações de forma desacoplada e escalável, sem a necessidade de bloqueios ou espera ativa.

[^rabbitmq]: O RabbitMQ está disponível para download no link: <https://www.rabbitmq.com/>

### PostgreSQL

O PostgreSQL[^postgresql] é um sistema de gerenciamento de banco de dados relacional (SGBD) de código aberto, reconhecido por sua conformidade com padrões SQL e suporte a transações ACID (Atomicidade, Consistência, Isolamento e Durabilidade). Ele oferece mecanismos para garantir a integridade dos dados e eficiência na execução de consultas.

Além de suas funcionalidades relacionais, o PostgreSQL permite o uso de índices personalizados, replicação e extensões para aprimoramento do desempenho e escalabilidade. Sua compatibilidade com diversas linguagens e frameworks possibilita a integração com diferentes tipos de aplicações.

O PostgreSQL foi utilizado como o banco de dados relacional da aplicação, armazenando informações essenciais como pesquisas, postagens coletadas, workflows de processamento e resultados das análises de sentimentos. Sendo a principal fonte de armazenamento de Sentilytics.

[^postgresql]: O PostgreSQL está disponível para download no link: <https://www.postgresql.org/>

### Git e GitHub

O Git[^git] é um sistema de controle de versão distribuído, amplamente utilizado para o gerenciamento de código-fonte em projetos de software. Ele permite que desenvolvedores rastreiem alterações no código, colaborem de forma eficiente e revertam modificações sempre que necessário. O Git funciona por meio de repositórios que armazenam diferentes versões dos arquivos, garantindo organização e controle durante o ciclo de desenvolvimento.

O GitHub[^github] é uma plataforma baseada na web que fornece um ambiente para hospedagem de repositórios Git. Além do armazenamento de código, o GitHub oferece ferramentas para colaboração, gerenciamento de projetos e automação de fluxos de trabalho.

No desenvolvimento do Sentilytics, o Git foi utilizado para versionamento e controle das alterações nos diferentes projetos que compõem a aplicação. Já o GitHub foi utilizado para armazenar os repositórios e gerenciar o ciclo de desenvolvimento de forma centralizada.

Além do controle de versão, o GitHub Actions foi empregado para automatizar a geração e armazenamento de imagens Docker dos serviços do sistema. Esse processo nas seguintes etapas:

1. Monitoramento de alterações – Sempre que novas mudanças são enviadas para o repositório em uma branch especifica, um workflow do GitHub Actions é acionado automaticamente.
1. Geração da imagem Docker – O código atualizado é processado para criar uma nova versão da imagem do serviço correspondente.
1. Armazenamento no GitHub Container Registry – Após a construção da imagem, ela é enviada e armazenada no GitHub Container Registry, garantindo que os serviços estivessem sempre prontos para implantação.

O uso do Git, GitHub e GitHub Actions possibilitou um fluxo contínuo de integração (CI), facilitando a manutenção e a implantação do Sentilytics.

[^git]: O Git está disponível para download no link: <https://git-scm.com/>
[^github]: O Github está disponível no link: <https://github.com/>

### Docker e Docker Compose

O Docker[^docker] é uma plataforma que permite a criação, distribuição e execução de containers, que são ambientes isolados que contêm todas as dependências necessárias para a execução de uma aplicação. Ao invés de instalar diretamente os serviços no sistema operacional, o Docker encapsula tudo em imagens, garantindo portabilidade, consistência e facilidade na implantação dos sistemas em diferentes ambientes.

O Docker Compose[^dockercompose] é uma ferramenta complementar ao Docker que permite a orquestração de múltiplos containers de maneira simplificada. Ele utiliza um arquivo de configuração no formato YAML para definir quais serviços devem ser executados, suas interações e configurações específicas, permitindo a inicialização conjunta de diferentes componentes de um sistema.

No desenvolvimento do Sentilytics, o Docker foi utilizado para criar imagens Docker de todos os componentes do sistema, garantindo que cada serviço fosse executado de forma isolada e sem dependências externas diretas. Com isso, cada parte do sistema pôde ser facilmente distribuída e implantada, independentemente do ambiente em que fosse executada.

Além disso, foi criado um Docker Compose de exemplo para facilitar a orquestração e execução dos containers, permitindo que os serviços do Sentilytics fossem iniciados de maneira unificada. Esse arquivo define quais containers devem ser executados, estabelecendo as configurações necessárias para a comunicação entre eles.

A utilização do Docker e Docker Compose no projeto trouxe benefícios como padronização do ambiente de execução e facilidade na implantação, garantindo que todos os serviços possam ser executados de forma consistente em qualquer infraestrutura compatível com Docker.

[^docker]: Para saber mais sobre o Docker acesse o link: <https://www.docker.com/>
[^dockercompose]: Você pode ler mais sobre o Docker Compose no link: <https://docs.docker.com/compose/>

### Intellij IDEA

O IntelliJ IDEA[^intellij] é um ambiente de desenvolvimento integrado (IDE) voltado para a criação de aplicações em Java e Kotlin. Desenvolvido pela JetBrains, oferece suporte a diversas tecnologias e frameworks, além de ferramentas de depuração e controle de versão que auxiliam no processo de desenvolvimento.

A IDE conta com recursos como autocompletar código, análise estática e refatoração, proporcionando um ambiente estruturado para a escrita e manutenção de código. Sua compatibilidade com frameworks como Spring Boot e ferramentas de automação como Maven facilita a configuração e o gerenciamento de projetos Java. O Intellij foi utilizado em todos os projetos java desenvolvidos nessa solução.

[^intellij]: O Intellij IDEA está disponível para download no link: <https://www.jetbrains.com/idea/>

### PyCharm

O PyCharm[^pycharm] é um ambiente de desenvolvimento integrado (IDE) voltado para aplicações em Python, desenvolvido pela JetBrains. Ele oferece suporte a frameworks e bibliotecas da linguagem, além de ferramentas de depuração, análise de código e controle de versão.

A IDE conta com recursos como autocompletar de código, refatoração automatizada e suporte a testes unitários, facilitando a escrita e manutenção de código. No Sentilytics, o PyCharm foi utilizado como a IDE principal para o desenvolvimento do serviço Python.

[^pycharm]: O Pycharm está disponível para download no link: <https://www.jetbrains.com/pycharm/>

### Visual Studio Code (VS Code)

O Visual Studio Code (VS Code)[^vscode] é um editor de código-fonte desenvolvido pela Microsoft, amplamente utilizado devido à sua leveza, extensibilidade e suporte a diversas linguagens de programação. Ele conta com recursos como realce de sintaxe, IntelliSense (autocompletar inteligente) e integração com ferramentas externas, facilitando o desenvolvimento e a depuração de código. Sendo o VS Code a principal ferramenta para desenvolvimento do frontend em Angular.

[^vscode]: O VS Code está disponível para download no link: <https://code.visualstudio.com/>

### DBeaver

O DBeaver[^dbeaver] é uma ferramenta universal de administração de bancos de dados, compatível com diversos sistemas de gerenciamento de banco de dados (SGBDs), incluindo PostgreSQL, MySQL, SQL Server e outros. Ele fornece uma interface gráfica para executar queries SQL, visualizar e editar tabelas, além de gerenciar conexões com diferentes bancos de dados.

A ferramenta também permite a exportação de dados em diferentes formatos, facilitando a análise externa e a validação das informações armazenadas. Além disso, oferece suporte a diversos recursos avançados, como modelagem de dados, execução de scripts e monitoramento de desempenho das consultas.

O DBeaver foi utilizado como ferramenta de administração do banco de dados PostgreSQL, permitindo a execução de consultas SQL, visualização e manipulação dos dados armazenados, facilitando o gerenciamento e a validação das informações durante o desenvolvimento do Sentilytics.

[^dbeaver]: O DBeaver está disponível para download no link: <https://dbeaver.io/>

### Vertabelo

O Vertabelo[^vertabelo] é uma ferramenta online para modelagem de bancos de dados, permitindo a criação de esquemas relacionais de forma visual. Ele fornece suporte à modelagem Entidade-Relacionamento (ER), facilitando a definição de tabelas, chaves primárias e estrangeiras, além da geração automática do código SQL e dicionário de dados correspondente.

A plataforma possibilita ajustes no modelo sem a necessidade de instalação de software adicional. Ainda mais, a plataforma oferece a exportação de diagramas para diferentes formatos, auxiliando na documentação e na comunicação entre equipes de desenvolvimento.

O Vertabelo foi utilizado para a modelagem do banco de dados, permitindo a criação do Diagrama Entidade-Relacionamento (DER) e a geração do Dicionário de Dados. Essa ferramenta facilitou a estruturação das tabelas e seus relacionamentos no PostgreSQL, auxiliando no planejamento e na organização dos dados do Sentilytics, garantindo uma base bem documentada.

[^vertabelo]: O Vertabelo está pode ser acessado no link: <https://my.vertabelo.com/>

### Postman

O Postman[^postman] é uma ferramenta utilizada para desenvolvimento, teste e documentação de APIs, permitindo a realização de requisições HTTP de maneira prática. Ele suporta diferentes métodos de requisição, como GET, POST, PUT e DELETE, possibilitando a verificação do funcionamento dos endpoints e a validação das respostas retornadas pelo servidor.

A ferramenta também permite a visualização de dados em formatos como JSON e XML, além de oferecer recursos para organização de coleções de requisições e automação de testes. Outra funcionalidade relevante é o gerenciamento de variáveis de ambiente, facilitando a adaptação de requisições para diferentes contextos, como desenvolvimento e produção.

O Postman foi utilizado para testar e validar todas as APIs desenvolvidas no Sentilytics, incluindo a API REST em Spring Boot e as integrações com o Bluesky. A ferramenta permitiu a realização de requisições HTTP, validando o funcionamento do serviços criados no backend e facilitando a depuração durante o desenvolvimento.

[^postman]: O postman está disponível para download no link: <https://www.postman.com/>

### Síntese das Tecnologias e Ferramentas utilizadas

A seguir, apresentamos um diagrama que agrupa as tecnologias e ferramentas utilizadas no projeto em suas respectivas categorias. Essa organização facilita a visualização dos principais componentes tecnológicos empregados, permitindo uma compreensão clara da diversidade de soluções adotadas.

![Diagrama das Tecnologias e ferramentas utilizadas](imagens/sentilytics/diagramas/tecnologias-ferramentas.png){#diagrama_tecnologias_ferramentas escala=0.5}

Fonte: Autor (2025).

A categorização das tecnologias evidencia a variedade de ferramentas que compõem o ecossistema do projeto. Cada categoria agrupa soluções com funções específicas, demonstrando a pluralidade de abordagens utilizadas no desenvolvimento. Com essa estrutura tecnológica bem definida, podemos garantir um fluxo de trabalho mais eficiente e uma base sólida para a implementação do sistema.

Finalizada a apresentação das tecnologias e ferramentas, seguimos agora para a próxima etapa, onde abordaremos a modelagem da solução.

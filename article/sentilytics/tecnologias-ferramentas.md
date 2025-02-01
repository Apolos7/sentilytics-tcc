## Tecnologias e Ferramentas

O desenvolvimento da aplicação de análise de sentimentos envolveu o uso de diversas tecnologias e ferramentas que possibilitaram a implementação eficiente da solução. A seguir, são apresentadas as principais tecnologias utilizadas, bem como as ferramentas empregadas no processo de desenvolvimento.

### Python

O Python é uma linguagem de programação amplamente utilizada para aplicações de Processamento de Linguagem Natural (PLN) devido à sua simplicidade, flexibilidade e grande ecossistema de bibliotecas especializadas. Na aplicação desenvolvida, o Python foi empregado no desenvolvimento de um módulo dedicado ao pré-processamento de textos e análise de sentimentos, permitindo a manipulação e classificação automática de postagens recuperadas de redes sociais.

Para realizar essas operações, a linguagem conta com bibliotecas robustas, como o Natural Language Toolkit (NLTK), que oferece suporte para tokenização, remoção de stopwords, stemming e lematização, e o Enelvo, que auxilia na normalização de textos em português. Esse conjunto de ferramentas possibilita um tratamento adequado dos dados antes da análise de sentimentos, garantindo maior precisão nos resultados.

O módulo implementado em Python se integra à arquitetura da aplicação por meio do serviço de mensageria RabbitMQ, recebendo mensagens que acionam o pré-processamento ou a análise de sentimentos. Após ser acionado, o módulo recupera as postagens armazenadas no banco de dados, aplica os processos necessários e envia os resultados para armazenamento.

### Spring Boot

O Spring Boot é um framework Java que facilita a criação de aplicações robustas e escaláveis, reduzindo a necessidade de configurações extensivas. Ele fornece uma estrutura modular e eficiente para desenvolvimento de aplicações web e serviços backend, sendo amplamente utilizado para a construção de APIs REST e processamento de dados em larga escala.

Na aplicação desenvolvida, o Spring Boot foi utilizado na construção de duas aplicações principais:

- Web API: Responsável por gerenciar a comunicação entre o frontend em Angular e os diversos serviços da aplicação. Essa API implementa todas as regras de validação e manipulação dos dados, além de atuar como um ponto central de integração com os demais módulos. Entre suas principais responsabilidades, destacam-se:

  - Comunicação com o módulo de análise de sentimentos em Python, enviando mensagens via RabbitMQ para disparar o processamento.
  - Integração com o serviço de Spring Batch, permitindo o envio e processamento de arquivos CSV para importação de postagens.
  - Conexão com o banco de dados PostgreSQL, garantindo a persistência e manipulação dos dados da aplicação.

- Serviço de Processamento com Spring Batch: Implementado para realizar o processamento assíncrono de grandes volumes de dados. Esse serviço recebe arquivos CSV contendo postagens, processa e armazena os dados no banco de forma eficiente, garantindo que a aplicação possa lidar com grandes quantidades de informações sem comprometer o desempenho.

A utilização do Spring Boot na arquitetura do sistema possibilitou a criação de uma solução modular e escalável, garantindo que a aplicação possa ser facilmente mantida e expandida conforme necessário.

### Angular

O Angular é um framework de desenvolvimento front-end baseado em TypeScript, mantido pelo Google, que facilita a criação de aplicações web dinâmicas e escaláveis. Ele oferece uma arquitetura modular, componentes reutilizáveis e um poderoso sistema de data binding, permitindo a construção de interfaces modernas e interativas.

Na aplicação desenvolvida, o Angular foi utilizado como a principal tecnologia para a construção do frontend, sendo responsável por proporcionar uma experiência fluida e intuitiva ao usuário. Ele se comunica diretamente com a Web API em Spring Boot, desempenhando um papel essencial no fluxo de interação da aplicação.

A interface foi projetada com o auxílio do Tailwind CSS, um framework CSS utilitário que permite a estilização das telas de forma eficiente e altamente customizável. Essa combinação possibilitou a criação de um layout responsivo e visualmente consistente.

Entre as principais responsabilidades do Angular dentro da aplicação, destacam-se:

- Construção das telas e componentes da interface, garantindo uma navegação intuitiva e uma boa experiência de usuário.
- Integração com a Web API em Spring Boot, realizando requisições para envio de dados e obtenção de informações processadas.
- Gerenciamento da pesquisa de análise de sentimentos, permitindo que o usuário defina os parâmetros da análise e envie as solicitações para processamento.
- Exibição dos resultados da análise, utilizando componentes gráficos para visualização das informações processadas.

A utilização do Angular na aplicação proporcionou uma abordagem modular e escalável para o desenvolvimento do frontend, garantindo desempenho, responsividade e flexibilidade na interação com os usuários.

### RabbitMQ

O RabbitMQ é um sistema de mensageria de código aberto amplamente utilizado para comunicação assíncrona entre serviços. Ele atua como um intermediário de mensagens, permitindo a troca de informações entre diferentes componentes de um sistema de forma desacoplada, garantindo escalabilidade, confiabilidade e eficiência na comunicação.

Na aplicação desenvolvida, o RabbitMQ foi utilizado para gerenciar a comunicação entre a Web API em Spring Boot e o módulo de pré-processamento e análise de sentimentos em Python. Esse mecanismo permite que a API envie solicitações de processamento sem precisar aguardar a conclusão da tarefa, melhorando o desempenho e permitindo a execução de múltiplas análises simultaneamente.

O funcionamento da comunicação assíncrona com RabbitMQ pode ser descrito da seguinte forma:

1. A Web API em Spring Boot publica uma mensagem em uma fila do RabbitMQ, solicitando o início do pré-processamento ou da análise de sentimentos.
2. O módulo Python consome essa mensagem da fila, processa os dados e executa as operações necessárias.
3. Após a conclusão do processamento, o módulo Python salva o resultado na base de dados e publica uma mensagem na fila contendo o resultado do processamento.
4. A Web API recebe a mensagem, finaliza o processamento e notifica o frontend da finalização do processo.

Essa abordagem baseada em mensageria desacopla os serviços, tornando o sistema mais escalável e resiliente a falhas. Caso ocorra um grande volume de solicitações simultâneas, as mensagens são enfileiradas e processadas conforme a capacidade do sistema, evitando sobrecarga e perda de dados.

A utilização do RabbitMQ na arquitetura da aplicação trouxe benefícios como melhor gerenciamento do fluxo de processamento.

### PostgreSQL

O PostgreSQL é um sistema de gerenciamento de banco de dados relacional (SGBD) de código aberto amplamente reconhecido por sua robustez, escalabilidade e conformidade com padrões SQL. Ele se destaca por oferecer suporte a transações ACID (Atomicidade, Consistência, Isolamento e Durabilidade), garantindo alta confiabilidade na manipulação de dados.

Além de seus recursos avançados para consultas SQL tradicionais, o PostgreSQL possui suporte a JSON, índices personalizados, replicação, armazenamento de dados geoespaciais (PostGIS) e diversas extensões que ampliam sua funcionalidade. Sua arquitetura extensível permite o desenvolvimento de soluções eficientes para aplicações que exigem grande volume de dados e operações complexas.

Na aplicação desenvolvida, o PostgreSQL foi utilizado como o banco de dados principal para armazenamento e gerenciamento das informações, garantindo a integridade e a eficiência na manipulação dos dados processados. Sua compatibilidade com diversas linguagens e frameworks possibilitou uma integração fluida com os demais componentes do sistema.

A escolha do PostgreSQL se deve à sua estabilidade, segurança e flexibilidade, sendo uma opção altamente confiável para aplicações que necessitam de um banco de dados escalável e com alto desempenho.

### Intellij IDEA

O IntelliJ IDEA é um ambiente de desenvolvimento integrado (IDE) amplamente utilizado para a criação de aplicações em Java e Kotlin. Desenvolvido pela JetBrains, o IntelliJ IDEA se destaca por oferecer suporte avançado à codificação, integração com frameworks populares, ferramentas de depuração e controle de versão, tornando o processo de desenvolvimento mais produtivo e eficiente.

A ferramenta possui um sistema inteligente de autocompletar código, análise estática e refatoração, permitindo que desenvolvedores escrevam código de forma mais rápida e com menos erros. Além disso, sua integração nativa com tecnologias como Spring Boot, Hibernate e Maven facilita o desenvolvimento de aplicações Java modernas.

Na aplicação desenvolvida, o IntelliJ IDEA foi utilizado como a principal IDE para a construção dos serviços backend em Spring Boot e Spring Batch. A ferramenta proporcionou um ambiente robusto para a codificação, depuração e testes dos módulos, garantindo um fluxo de trabalho eficiente durante o desenvolvimento da solução.

A escolha do IntelliJ IDEA se deve à sua interface intuitiva, suporte a múltiplos frameworks e recursos avançados de produtividade, sendo uma ferramenta essencial para o desenvolvimento backend da aplicação.

### PyCharm

O PyCharm é um ambiente de desenvolvimento integrado (IDE) especializado para desenvolvimento em Python, criado pela JetBrains. Reconhecido por sua interface intuitiva e recursos avançados, o PyCharm oferece suporte a frameworks populares, ferramentas de depuração, análise de código e integração com sistemas de controle de versão, tornando o processo de desenvolvimento mais eficiente e produtivo.

A ferramenta se destaca por sua inteligência no autocompletar de código, refatoração automatizada e suporte a testes unitários, garantindo maior qualidade e organização no desenvolvimento de aplicações. Além disso, sua compatibilidade com bibliotecas de machine learning, análise de dados e processamento de linguagem natural (PLN) faz do PyCharm uma escolha ideal para projetos que envolvem análise de sentimentos e manipulação de dados textuais.

Na aplicação desenvolvida, o PyCharm foi utilizado como a IDE principal para o desenvolvimento do módulo de pré-processamento de textos e análise de sentimentos em Python. Ele proporcionou um ambiente otimizado para a escrita e depuração do código, permitindo uma melhor organização do projeto e maior eficiência no desenvolvimento.

A escolha do PyCharm se deve ao seu suporte avançado a Python, integração com bibliotecas específicas de PLN e ferramentas de produtividade, tornando-o uma solução essencial para a implementação e manutenção do módulo de análise de sentimentos.

### Visual Studio Code (VS Code)

O Visual Studio Code (VS Code) é um editor de código-fonte desenvolvido pela Microsoft, amplamente adotado na comunidade de desenvolvimento de software devido à sua leveza, extensibilidade e suporte para diversas linguagens de programação. No desenvolvimento do Sentilytics, plataforma voltada para a análise de sentimentos baseada em pesquisas, o VS Code desempenhou um papel fundamental na escrita e depuração do código.

Uma das principais razões para a escolha do VS Code foi sua compatibilidade com múltiplas linguagens, incluindo Python (utilizado na implementação dos modelos de análise de sentimentos) e JavaScript (utilizado para a interface web). O suporte nativo a realce de sintaxe, IntelliSense (autocompletar inteligente) e integração com Jupyter Notebooks facilitou a implementação dos algoritmos de processamento de linguagem natural.

Além disso, o VS Code oferece um sistema robusto de extensões, permitindo a instalação de ferramentas como:

- Pylance, que melhora a experiência no desenvolvimento em Python com sugestões de código mais precisas;
- Jupyter, utilizado para testes interativos com análise de dados e modelos de machine learning;
- Prettier, responsável pela formatação automática do código, garantindo padronização e legibilidade.

Outro fator determinante foi a integração com o Git e GitHub, permitindo versionamento eficiente do código-fonte do Sentilytics. O VS Code possibilitou a realização de commits, criação de branches e sincronização do repositório diretamente pela interface gráfica, simplificando o gerenciamento colaborativo do projeto.

Por fim, a presença de um terminal integrado e ferramentas de depuração avançadas agilizou a execução dos scripts, reduzindo o tempo de desenvolvimento e facilitando a identificação de erros. A possibilidade de configurar diferentes workspaces também contribuiu para a organização do projeto, permitindo o desenvolvimento modularizado da aplicação.

A escolha do Visual Studio Code se mostrou acertada, pois permitiu um fluxo de desenvolvimento ágil, organizado e produtivo, impactando diretamente na qualidade do código e na eficiência do processo de implementação do Sentilytics.

### DBeaver

O DBeaver é uma ferramenta universal de administração de banco de dados, amplamente utilizada para gerenciar diferentes sistemas de gerenciamento de banco de dados (SGBDs), incluindo o PostgreSQL. No desenvolvimento do Sentilytics, o DBeaver foi essencial para conectar-se ao banco de dados PostgreSQL, que armazena as respostas das pesquisas de análise de sentimentos realizadas na plataforma.

A escolha pelo DBeaver se deu por sua interface intuitiva e suporte robusto ao PostgreSQL, permitindo a execução de queries SQL, visualização e edição de tabelas e inspeção dos dados armazenados. Essa funcionalidade foi crucial para validar os dados coletados, realizar testes de integridade e acompanhar a estruturação do banco durante o desenvolvimento da aplicação.

Adicionalmente, o DBeaver possibilitou a exportação de dados para análise externa, auxiliando na etapa de verificação e validação dos modelos de análise de sentimentos implementados no Sentilytics. Sua capacidade de lidar com diferentes tipos de bancos de dados também representa uma vantagem para futuras expansões do projeto.

### Vertabelo

O Vertabelo é uma ferramenta online para modelagem de banco de dados, amplamente utilizada para projetar esquemas relacionais de forma visual e intuitiva. No desenvolvimento do Sentilytics, o Vertabelo foi empregado para estruturar e organizar o banco de dados PostgreSQL, garantindo que o armazenamento e a manipulação das informações fossem eficientes e bem estruturados.

Uma das principais vantagens do Vertabelo é sua interface baseada em modelagem ER (Entidade-Relacionamento), que permitiu o desenho das tabelas, definições de chaves primárias e estrangeiras, além da geração automática do código SQL para a criação do banco. Essa funcionalidade facilitou a implementação do banco de dados da aplicação, garantindo coerência e escalabilidade do modelo de dados.

Além disso, o Vertabelo possibilitou o trabalho colaborativo, permitindo ajustes e refinamentos na estrutura do banco sem a necessidade de instalar software adicional. A exportação do esquema para diferentes formatos também se mostrou útil na documentação do projeto e na comunicação com a equipe de desenvolvimento.

O uso do Vertabelo contribuiu significativamente para o planejamento e organização dos dados do Sentilytics, assegurando que o banco de dados fosse projetado de forma otimizada para armazenar e processar as pesquisas de análise de sentimentos de maneira eficiente.

### Postman

O Postman é uma ferramenta amplamente utilizada para desenvolvimento, teste e documentação de APIs, facilitando a comunicação entre diferentes partes de uma aplicação. No desenvolvimento do Sentilytics, o Postman desempenhou um papel fundamental na validação e depuração das requisições enviadas entre o frontend e o backend da aplicação.

Uma das principais razões para o uso do Postman foi sua capacidade de testar requisições HTTP de forma prática, permitindo o envio de solicitações GET, POST, PUT e DELETE para a API do Sentilytics. Dessa forma, foi possível verificar o correto funcionamento dos endpoints responsáveis pelo envio e recuperação de dados das pesquisas de análise de sentimentos.

Além disso, o Postman facilitou a visualização das respostas da API em diferentes formatos, como JSON e XML, tornando mais simples a análise e validação dos dados retornados pelo servidor. A ferramenta também permitiu a configuração de coleções de requisições, otimizando os testes automatizados e garantindo que as integrações funcionassem corretamente ao longo do desenvolvimento.

Outro benefício importante foi a possibilidade de armazenar variáveis de ambiente, o que facilitou os testes em diferentes cenários, como ambiente de desenvolvimento e produção, sem a necessidade de reconfigurar manualmente cada requisição.

O uso do Postman no Sentilytics proporcionou agilidade e confiabilidade na comunicação com a API, tornando o processo de testes mais eficiente e contribuindo para a estabilidade da aplicação.

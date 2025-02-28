## Modelagem da solução

A modelagem da solução é uma etapa fundamental no desenvolvimento de sistemas, pois permite a representação visual e descritiva dos componentes, fluxos de dados e interações entre os elementos da aplicação. Através dessa modelagem, é possível compreender a estrutura da solução proposta, identificar os requisitos essenciais e garantir que a implementação esteja alinhada com os objetivos do projeto.

A aplicação desenvolvida para análise de sentimentos em redes sociais exige uma modelagem robusta que aborde tanto os aspectos funcionais quanto os estruturais do sistema. Para isso, são utilizados diferentes diagramas e especificações, que descrevem desde os requisitos funcionais e não funcionais até a arquitetura dos componentes e o fluxo de processamento dos dados.

Inicialmente, são definidos os requisitos funcionais e não funcionais, que estabelecem as funcionalidades esperadas e as restrições técnicas da aplicação. Em seguida, o Diagrama de Caso de Uso apresenta as principais interações entre os usuários e o sistema, facilitando a compreensão das funcionalidades disponíveis.

Para representar o fluxo de execução dos processos dentro da aplicação, são utilizados diagramas BPMN (Business Process Model and Notation) e diagramas de sequência/atividades, que detalham as etapas do pré-processamento e da análise de sentimentos. Além disso, a estrutura de dados e as relações entre entidades são documentadas por meio do Diagrama Entidade-Relacionamento (DER) e do dicionário de dados.

A organização dos componentes do sistema é descrita no Diagrama de Componentes, que ilustra a arquitetura da aplicação, destacando a comunicação entre os módulos do backend, frontend e serviços externos. Complementarmente, o Diagrama de Classes define a estrutura da lógica de programação, detalhando as principais classes e seus relacionamentos.

Por fim, as interfaces gráficas são apresentadas para demonstrar a experiência do usuário e a forma como as funcionalidades da aplicação são disponibilizadas. Essas interfaces são projetadas para garantir usabilidade, responsividade e uma experiência intuitiva, permitindo que os usuários explorem as análises de sentimentos de maneira eficiente.

Com essa modelagem, busca-se garantir que a aplicação seja bem estruturada, escalável e de fácil manutenção, possibilitando futuras melhorias e adaptações conforme novas necessidades forem identificadas.

### Requisitos Funcionais e Não Funcionais

Para garantir que a aplicação de análise de sentimentos em redes sociais atenda aos objetivos propostos, é essencial definir os requisitos funcionais e não funcionais. Os requisitos funcionais descrevem as funcionalidades que o sistema deve oferecer, especificando as interações entre usuários e a aplicação. Já os requisitos não funcionais estabelecem critérios de qualidade, desempenho, segurança e usabilidade. A \autoref{requisitos_funcionais} apresenta os principais requisitos funcionais que orientaram o desenvolvimento da solução proposta.

: Requisitos funcionais. \label{requisitos_funcionais}

| Código | Requisito                                                                                                                                                                                                            |
|--------|----------------------------------------------------------------------------------------------------------------------------|
| RF01   | O sistema deve permitir a coleta de postagens da rede social Bluesky, respeitando parâmetros de data inicial, data final, query de busca e linguagem.                                              |
| RF02   | O sistema deve permitir como forma alternativa a importação de postagens no formato CSV para análise de sentimentos, utilizando Spring Batch para processamento da importação. |
| RF03   | O sistema deve permitir que o usuário configure workflows e escolha quais tarefas de pré-processamento serão aplicadas aos dados coletados.                                              |
| RF04   | O sistema deve possibilitar a limpeza e normalização dos textos coletados, incluindo remoção de stopwords, lematização e tokenização.                                                   |
| RF05   | O sistema deve calcular a pontuação de sentimentos de cada comentário, classificando-os como positivos, negativos ou neutros com base em regras de pontuação composta.                      |
| RF06   | O sistema deve armazenar os resultados da análise de sentimentos em uma tabela de banco de dados, incluindo a quantidade total de comentários e a distribuição de sentimentos.         |
| RF07   | O sistema deve permitir a consulta dos resultados da análise de sentimentos, filtrando por período, rede social e sentimento predominante.                                                  |
| RF08   | O sistema deve permitir a comunicação entre o backend em Spring Boot e o serviço de análise de sentimentos em Python por meio de RabbitMQ.                                                |
| RF09   | O sistema deve permitir que usuários se autentiquem utilizando suas credenciais da rede social Bluesky, sem a necessidade de cadastro adicional.                                        |
| RF10   | O sistema deve fornecer uma interface web baseada em Angular para que os usuários possam interagir com as funcionalidades de análise de sentimentos.                                                 |

Fonte: Autor (2025).

Com os requisitos funcionais definidos, podemos visualizar como os usuário interagem com o sistema e quais as funcionalidades deveram estar disponíveis para o usuário. Para isso, vamos utilizar o diagrama de casos de uso.

### Diagramas de Caso de Uso

Os diagramas de caso de uso são representações gráficas que demonstram as interações entre os usuários e um sistema, destacando as principais funcionalidades disponíveis. Seu objetivo é ilustrar, de forma simples, como os diferentes atores interagem com o sistema em cenários específicos, auxiliando na compreensão dos requisitos e no planejamento da aplicação. A seguir, apresenta-se um caso de uso relevante do Sentilytics.

![Diagrama de Casos de Uso do Sentilytics](imagens/sentilytics/diagramas/usecase.png){#usecase escala=0.3}

Fonte: Autor (2025).

Como podemos visualizar na Figura \ref{usecase}, o diagrama apresenta as interações entre o usuário e o sistema Sentilytics, destacando as principais funcionalidades disponíveis. Cada caso de uso representa uma ação que pode ser realizada dentro da aplicação, organizando de forma clara os processos fundamentais do sistema.

O usuário pode realizar operações relacionadas à gestão de pesquisas, como cadastrar, excluir e importar postagens diretamente via CSV e realizar a busca de postagens na plataforma Bluesky. Também há funcionalidades voltadas para a administração de workflows, permitindo o cadastro, configuração das tarefas de
pré-processamento e seus parâmetros e exclusão desses componentes, que são essenciais para a organização do processamento das postagens.

Ademais, o diagrama evidencia os processos de pré-processamento e análise de sentimentos, que representam etapas centrais para obtenção dos resultados. Após a execução do pré-processamento das postagens e em seguida a análise do sentimentos, o usuário pode visualizar os resultados gerados para aquele workflow processado, facilitando a interpretação e análise das informações processadas pelo Sentilytics.

Com o diagrama de casos de uso definido, foi criada a modelagem do principal processo da aplicação para estabelecer quais passos o usuário deve seguir para criar uma pesquisa de análise de sentimentos.

### BPMN

A Business Process Model and Notation (BPMN) é uma notação padronizada para modelagem de processos de negócios, utilizada para representar o fluxo de atividades dentro de um sistema ou organização. Seu propósito é fornecer uma visão clara das etapas envolvidas em um processo, facilitando sua análise e compreensão. A seguir, apresenta-se um diagrama BPMN relacionado ao funcionamento do Sentilytics.

![Modelagem BPMN do Processo de Pesquisa no Sentilytics](imagens/sentilytics/pesquisa_sentimentos.png){#bpmn_pesquisa escala=0.3}

Fonte: Autor (2025).

A Figura \ref{bpmn_pesquisa} apresenta o fluxo principal para a realização de uma pesquisa completa no  Sentilytics, representado por meio do  Diagrama BPMN. Esse fluxo descreve as etapas envolvidas desde a criação da pesquisa até a visualização dos resultados da análise de sentimentos.

O processo inicia-se quando o usuário decide realizar uma nova pesquisa, cadastrando-a e configurando os parâmetros necessários. Em seguida, é necessário definir o  método de coleta de dados , onde duas abordagens podem ser utilizadas de forma independente ou simultânea: importação de dados via arquivo CSV ou a busca automatizada de postagens na plataforma Bluesky .

Após a coleta dos dados, o próximo passo envolve a criação de um workflow, que organiza o processamento dos textos coletados. O usuário, então, inicia a fase de  pré-processamento, na qual o sistema aplica as tarefas configuradas no workflow pelo usuário, preparando os dados para a análise.

Com os dados pré-processados, o usuário pode acionar a  análise de sentimentos naquele workflow já pré-processado, permitindo que o sistema classifique os textos e gere os resultados. Após a execução desse processamento, os resultados são disponibilizados para visualização, possibilitando a interpretação dos dados analisados.

Vale notar que o usuário está livre para cadastrar diversos workflows, cada um com suas particularidades na configuração, possuindo diferentes tarefas de pré-processamento e parâmetros. Por fim, o fluxo se encerra quando o usuário finaliza a pesquisa, consolidando os resultados obtidos.

Com o processo definido, foi necessário estruturar a modelagem dos dados. Para isso, foi elaborado o Diagrama Entidade-Relacionamento (DER), que representa a estrutura do banco de dados e suas interações com os elementos do sistema. Além disso, foi desenvolvido um dicionário de dados para detalhar cada entidade e sua finalidade dentro da aplicação.

### Diagrama Entidade-Relacionamento (DER) e Dicionário de dados

O Diagrama Entidade-Relacionamento (DER) é uma representação visual da estrutura do banco de dados, destacando as entidades, seus atributos e os relacionamentos entre elas. Ele permite compreender a organização dos dados e a forma como as informações são armazenadas e manipuladas dentro do sistema. No Sentilytics, o DER foi desenvolvido utilizando a ferramenta Vertabelo, garantindo uma modelagem estruturada e alinhada com os requisitos do sistema.

![Diagrama Entidade Relacionamento](imagens/sentilytics/diagramas/DER-sentilytics.png){#der escala=0.5}

Fonte: Autor (2025).

A \autoref{der} apresenta o Diagrama Entidade-Relacionamento, demonstrando a estrutura do banco de dados da aplicação. A modelagem foi desenvolvida com base nos requisitos funcionais e processos definidos, garantindo que a estrutura de dados suporte corretamente as funcionalidades do sistema.

Complementando essa modelagem, o Dicionário de Dados fornece uma descrição detalhada das tabelas, colunas, tipos de dados e restrições aplicadas, servindo como uma referência essencial para o desenvolvimento e manutenção do banco de dados. Esse recurso documenta a estrutura do banco de forma organizada, facilitando a compreensão da modelagem e assegurando a consistência dos dados ao longo do ciclo de vida da aplicação.

![Dicionário de Dados](imagens/sentilytics/diagramas/dicionario_dados.png){#dicionario_dados escala=0.3}

Fonte: Autor (2025).

Assim como o DER, o Dicionário de Dados do Sentilytics foi gerado na ferramenta Vertabelo, que permite a exportação e documentação estruturada dos elementos do banco. A \autoref{dicionario_dados} apresenta esse documento, refletindo a modelagem realizada e consolidando a documentação do banco de dados. Após a modelagem da base de dados, foi possível avançar com os diagramas de sequência/atividade dos principais fluxos que foram mostrados nos requisitos.

### Diagrama de Sequência/Atividades do pré-processamento e análise de sentimentos

Os diagramas de sequência são utilizados para representar a interação entre diferentes componentes de um sistema ao longo do tempo. Eles detalham a ordem das mensagens trocadas entre os elementos envolvidos, permitindo a visualização do fluxo de execução de um processo específico. Essa abordagem facilita a compreensão da dinâmica do sistema e auxilia na identificação de dependências entre os componentes.

No contexto do Sentilytics, foram elaborados três diagramas de sequência que descrevem processos essenciais para o funcionamento da aplicação:

- Figura \ref{seq_pesquisa_coleta_dados}: Cadastro da pesquisa e coleta de dados.
- Figura \ref{seq_cadastro_configuracao_workflow}: Cadastro e configuração do workflow.
- Figura \ref{seq_processamento_analise}: Sequência de processamento, incluindo o pré-processamento do workflow e da análise de sentimentos.

Cada um desses diagramas detalha a troca de informações entre os elementos do sistema, evidenciando os passos necessários para a execução dessas funcionalidades. A seguir, apresentam-se essas representações gráficas.

![Diagrama de sequência do cadastro da pesquisa e coleta de dados](imagens/sentilytics/diagramas/sequencia-cadastro-pesquisa-coleta-dados.png){#seq_pesquisa_coleta_dados escala=0.4}

Fonte: Autor (2025).

A Figura \ref{seq_pesquisa_coleta_dados} apresenta o Diagrama de Sequência que descreve o fluxo de criação de uma pesquisa de análise de sentimentos e a coleta de dados a partir da plataforma  Bluesky. Esse diagrama detalha a interação entre o usuário e os principais componentes do sistema durante esse processo.

O fluxo se inicia quando o usuário solicita a criação de uma nova pesquisa. Essa requisição é recebida pelo PesquisaAnaliseSentimentoController, que encaminha os dados para o PesquisaAnaliseSentimentoService, responsável pelo gerenciamento da lógica de negócio associada à pesquisa.

Em seguida, o serviço aciona o BlueskyService, que realiza a busca de postagens na API do Bluesky com base nos parâmetros definidos na pesquisa. Os dados coletados são então enviados de volta ao serviço principal, que procede ao armazenamento das postagens. Para isso, a lista de postagens é encaminhada ao  PostRepository, que realiza a persistência das informações no banco de dados.

Após a conclusão do armazenamento, o PostRepository confirma a operação, retornando uma notificação ao PesquisaAnaliseSentimentoService. O serviço, por sua vez, informa ao controller que a pesquisa e os posts foram armazenados com sucesso. Por fim, o usuário recebe uma confirmação da criação da pesquisa, sinalizando que o processo foi concluído corretamente.

Esse diagrama ilustra de forma clara a sequência de interações entre os componentes do sistema, destacando como a pesquisa é cadastrada e os dados são coletados e armazenados para posterior análise.

![Diagrama de sequência do cadastro e configuração do workflow](imagens/sentilytics/diagramas/sequencia-cadastro-configuracao-workflow.png){#seq_cadastro_configuracao_workflow escala=0.4}

Fonte: Autor (2025).

A Figura \ref{seq_cadastro_configuracao_workflow} apresenta o Diagrama de Sequência referente ao processo de cadastro e configuração do workflow dentro do Sentilytics. Esse diagrama descreve a interação entre o usuário e os principais componentes responsáveis pelo gerenciamento dos workflows de processamento de dados.

O fluxo se inicia quando o usuário solicita a criação de um novo workflow. Essa requisição é encaminhada ao WorkflowProcessamentoController, que repassa os dados ao WorkflowProcessamentoService, responsável por registrar o workflow no banco de dados. Após a conclusão dessa etapa, uma confirmação de criação é enviada ao usuário.

Após o cadastro, o usuário pode prosseguir com a configuração do workflow, definindo as funções de pré-processamento e análise de sentimentos que serão aplicadas aos dados coletados. Essa configuração permite que o usuário ordene e selecione diferentes tarefas de pré-processamento, como capitalização de texto, conversão para caixa baixa, remoção de stopwords, correção ortográfica, entre outras. A ordem dessas tarefas é um fator determinante para o processamento, pois impacta diretamente os resultados da análise de sentimentos.

Quando o usuário finaliza a configuração, o WorkflowProcessamentoController encaminha os dados ao WorkflowProcessamentoService, que atualiza as informações do workflow no banco de dados. Após essa operação, uma confirmação é enviada ao usuário, indicando que o workflow foi configurado e salvo com sucesso.

Esse diagrama demonstra a estrutura do processo de cadastro e configuração do workflow, garantindo que o sistema ofereça flexibilidade na definição das etapas de processamento. Dessa forma, os usuários podem ajustar o fluxo de análise de acordo com suas necessidades específicas.

![Diagrama de sequência do pré-processamento e análise](imagens/sentilytics/diagramas/sequencia-pre-processamento-analise-sentimentos.png){#seq_processamento_analise escala=0.2}

Fonte: Autor (2025).

A Figura \ref{seq_processamento_analise} apresenta o Diagrama de Sequência que descreve o fluxo de execução de um workflow de processamento, que representa o fluxo utilizado tanto para o pré-processamento do texto quanto para a análise de sentimentos dentro do Sentilytics. Esse diagrama detalha a interação entre o usuário e os serviços responsáveis pelo envio, processamento e retorno dos dados.

O fluxo inicia-se quando o usuário solicita a execução de um workflow. Essa requisição é encaminhada ao WorkflowProcessamentoController, que direciona o processamento ao WorkflowProcessamentoService, responsável por gerenciar a execução. Para iniciar o processamento, o serviço encaminha a solicitação ao MessageBrokerProducer, que publica uma mensagem na fila do RabbitMQ contendo a identificação do workflow a ser processado.

O RabbitMQ então encaminha essa mensagem ao PythonService, que é responsável por executar as tarefas associadas ao workflow. Dependendo do tipo de processamento solicitado, esse serviço pode realizar etapas de pré-processamento, como remoção de stopwords, normalização e correção ortográfica, ou realizar a análise de sentimentos, atribuindo classificações às postagens processadas.

Após a conclusão do processamento, o PythonService retorna os resultados ao RabbitMQ, que os repassa ao MessageBrokerConsumer. O consumidor, então, encaminha os resultados ao WorkflowProcessamentoService, que processa e armazena as informações conforme necessário. Uma vez finalizada essa etapa, o controller notifica o usuário informando que os resultados foram processados com sucesso.

Esse diagrama destaca a estrutura assíncrona e desacoplada do processamento dentro do Sentilytics, garantindo que tanto o pré-processamento quanto a análise de sentimentos sejam executados de maneira escalável. O uso do RabbitMQ como intermediário permite que as solicitações sejam distribuídas e processadas conforme a capacidade do sistema, evitando sobrecargas e garantindo a confiabilidade das execuções.

### Diagrama de Classe

O Diagrama de Classes é uma representação da estrutura estática do sistema, demonstrando as classes que o compõem, seus atributos, métodos e os relacionamentos entre elas. Esse modelo auxilia na compreensão da arquitetura do sistema, permitindo uma visão clara da organização do código e da interação entre os componentes.

Devido à complexidade da aplicação e à quantidade de classes envolvidas, o diagrama de classes foi dividido em cinco partes, cada uma focada em um pacote específico da Web API desenvolvida em Spring Boot. Essa divisão facilita a análise dos diferentes níveis da aplicação, proporcionando uma visão mais segmentada e compreensível.

Os diagramas são organizados da seguinte forma:

- Visão Geral dos Pacotes: Exibe a estrutura principal da aplicação, destacando os pacotes e suas respectivas classes.
- Pacote Model: Representa as entidades do domínio, definindo os objetos que compõem o modelo de dados e seus relacionamentos.
- Pacote Repository: Demonstra os repositórios responsáveis pela persistência dos dados, conectando a aplicação ao banco de dados.
- Pacote Service: Contém as classes que implementam a lógica de negócio, garantindo o processamento e a manipulação dos dados conforme as regras da aplicação.
- Pacote Controller: Representa os controladores da API, responsáveis por expor os endpoints e intermediar a comunicação entre o frontend e a lógica de negócio.

A seguir, cada diagrama será apresentado e analisado individualmente, detalhando a estrutura e os relacionamentos das classes dentro de cada camada do sistema.

![Diagrama de classes com visão geral dos pacotes](imagens/sentilytics/diagramas/classes/diagrama-classe-visao-geral-pacotes.png){#diagrama_classe_geral escala=0.2}

Fonte: Autor (2025).

A Figura \ref{diagrama_classe_geral} apresenta a visão geral dos pacotes da Web API desenvolvida em Spring Boot, destacando sua estrutura modular e a organização das classes. Esse diagrama ilustra a separação dos componentes do sistema, facilitando a compreensão das responsabilidades de cada pacote e a interação entre eles.

A arquitetura segue uma estrutura organizada em camadas, conforme descrito a seguir:

- Pacote controller: Contém as classes responsáveis por expor os endpoints da API, intermediando a comunicação entre o frontend e a lógica de negócio da aplicação. Cada classe representa um controlador correspondente a um serviço específico.
- Pacote service: Implementa a lógica de negócio do sistema, processando dados e aplicando as regras definidas. Essa camada interage diretamente com os repositórios para manipulação dos dados e com a camada de controle para fornecer respostas às requisições.
- Pacote repository: Define os repositórios da aplicação, responsáveis pelo acesso e manipulação dos dados no banco de dados. As interfaces dessa camada utilizam o Spring Data JPA para abstrair operações de persistência.
- Pacote model: Contém as entidades do domínio, que representam as tabelas do banco de dados e seus relacionamentos. Essa camada define a estrutura dos dados utilizados na aplicação.
- Pacote config: Reúne configurações essenciais da aplicação, incluindo segurança, serialização e tratamento de exceções.
- A comunicação entre os pacotes ocorre de forma estruturada: a camada de controle interage com os serviços, que, por sua vez, realizam operações no banco de dados por meio dos repositórios. O pacote de model é utilizado pelos repositórios para representar os dados persistidos, garantindo uma separação clara das responsabilidades dentro da aplicação.

A seguir, será apresentada uma análise detalhada do Diagrama do Pacote Model, que contém as entidades responsáveis pelo armazenamento e manipulação dos dados no sistema.

![Diagrama de classes da camada Model](imagens/sentilytics/diagramas/classes/model-classes.png){#diagrama_classe_model escala=0.3}

Fonte: Autor (2025).

A Figura \ref{diagrama_classe_model} apresenta o Diagrama de Classes do Pacote Model, que define as entidades utilizadas na Web API Spring Boot do Sentilytics. Essas entidades representam as tabelas do banco de dados e são responsáveis pelo armazenamento das informações essenciais para o funcionamento da aplicação.

As classes do modelo seguem uma estrutura relacional, onde cada entidade contém atributos que refletem as colunas da respectiva tabela no banco de dados. Entre as principais entidades, destacam-se:

- PesquisaAnaliseSentimentosEntity: Representa uma pesquisa de análise de sentimentos, armazenando informações como nome, idioma, período de análise, critérios de busca e o usuário que criou a pesquisa.
- PostEntity: Contém as postagens coletadas para análise, armazenando dados como conteúdo do post, quantidade de interações (curtidas, respostas, reposts) e data de criação.
- PostProcessadoEntity: Armazena as informações das postagens após passarem pelo workflow de pré-processamento, incluindo o texto processado e as pontuações de sentimentos atribuídas.
- WorkflowProcessamentoEntity: Define um workflow de processamento, armazenando seu nome, status e associação com uma pesquisa de análise de sentimentos.
- TarefaPesquisaEntity e TarefaPreProcessamentoEntity: Representam as tarefas associadas ao workflow, incluindo ordem de execução, tipo de entrada/saída e descrição das operações.
- ResultadosAnaliseWorkflowEntity: Armazena os resultados obtidos após a execução do workflow, categorizando os tipos de análise realizadas.
- UsuarioEntity: Representa os usuários do sistema, armazenando informações como login e identificador descentralizado (DID).
- ParametroEntity e ValorParametroTarefaEntity: Permitem a configuração dinâmica de parâmetros para personalização do workflow, garantindo maior flexibilidade na execução das análises.
- PromptAIEntity e PromptResultadoAnaliseEntity: Armazenam os prompts e os resultados gerados por inteligência artificial durante a análise dos textos processados.

As relações entre essas entidades são fundamentais para garantir a integridade e a consistência dos dados dentro da aplicação. Cada entidade se relaciona diretamente com outras por meio de chaves primárias e estrangeiras, refletindo a estrutura do banco de dados relacional utilizado.

Para possibilitar a manipulação e persistência dessas entidades no banco de dados, são utilizados repositórios, que fornecem uma interface para a realização de operações como inserção, consulta, atualização e remoção de dados. A seguir, será apresentado o Diagrama do pacote Repository, que detalha esses componentes responsáveis pelo acesso aos dados da aplicação.

![Diagrama de classes da camada Repository](imagens/sentilytics/diagramas/classes/repository-classes.png){#diagram_repository escala=0.2}

Fonte: Autor (2025).

A Figura \ref{diagram_repository} apresenta o Diagrama da Camada Repository, responsável pelo acesso e manipulação dos dados no banco de dados dentro da Web API Spring Boot do Sentilytics. Essa camada implementa interfaces que utilizam o Spring Data JPA, facilitando a execução de operações de persistência sem a necessidade de implementar consultas SQL manualmente.

Cada repositório representa uma interface que permite a consulta, inserção, atualização e remoção de registros no banco de dados, fornecendo métodos específicos para manipulação das entidades da aplicação. Entre os principais repositórios, destacam-se:

- PesquisaAnaliseSentimentosRepository: Gerencia as pesquisas de análise de sentimentos, possibilitando operações como busca por usuário, exclusão de pesquisas e recuperação de registros específicos.
- PostRepository: Manipula os dados das postagens coletadas, permitindo verificar duplicações, realizar exclusões e consultar postagens associadas a uma pesquisa.
- WorkflowProcessamentoRepository: Responsável pelo armazenamento e recuperação dos workflows de processamento, permitindo buscar registros vinculados a um usuário ou pesquisa, além de verificar a existência de análises finalizadas.
- ResultadosAnaliseWorkflowRepository: Garante a persistência dos resultados gerados pelo workflow, oferecendo métodos para calcular métricas, como engajamento médio e frequência de palavras, além de realizar consultas sobre o desempenho da análise de sentimentos ao longo do tempo.
- PromptAIRepository e PromptResultadoAnaliseRepository: Permitem a recuperação e exclusão de prompts de IA e seus respectivos resultados de análise, utilizados na interpretação automática dos textos processados.
- TarefaPesquisaRepository e TarefaPreProcessamentoRepository: Fornecem métodos para gerenciamento das tarefas do workflow, permitindo a exclusão de tarefas e a listagem das configurações associadas ao processo de pré-processamento.
- UsuarioRepository: Responsável pela recuperação das informações de usuários, permitindo buscas por identificador descentralizado (DID) ou login.
- ValorParametroTarefaRepository: Manipula os parâmetros personalizados das tarefas do workflow, possibilitando consultas e exclusões de valores associados às configurações definidas pelo usuário.

A separação da camada Repository garante que a lógica de persistência dos dados fique desacoplada das demais partes do sistema, facilitando a manutenção e reutilização do código.

Para processar os dados e aplicar as regras de negócio da aplicação, os repositórios são utilizados pela camada Service, que implementa a lógica necessária para a manipulação dessas informações. A seguir, será apresentado o Diagrama da Camada Service, detalhando os serviços responsáveis pelo processamento e gestão das regras de negócio do Sentilytics.

![Diagrama de classes do pacote Services](imagens/sentilytics/diagramas/classes/service-classes.png){#diagram_service escala=0.2}

Fonte: Autor (2025).

A Figura \ref{diagram_service} apresenta o Diagrama da Camada Service, responsável por implementar a lógica de negócio da Web API Spring Boot do Sentilytics. Essa camada é responsável pelo processamento das operações da aplicação, garantindo a manipulação dos dados, a aplicação das regras de negócio e a interação entre os controladores e os repositórios.

As classes de serviço estendem a classe BaseService, que fornece funcionalidades comuns para gerenciamento de usuários autenticados e outras operações compartilhadas. A seguir, destacam-se algumas das principais responsabilidades dessa camada:

- PesquisaAnaliseSentimentosService: Gerencia as operações relacionadas às pesquisas de análise de sentimentos, permitindo cadastrar, atualizar, listar e excluir pesquisas, além de executar buscas de postagens vinculadas.
- PostService: Responsável pela manipulação das postagens coletadas, oferecendo funcionalidades para listagem, exclusão de duplicatas e importação de posts via CSV.
- WorkflowProcessamentoService: Controla os workflows de processamento, permitindo cadastrar, atualizar e excluir workflows, além de iniciar as etapas de pré-processamento e análise de sentimentos.
- ResultadosAnaliseWorkflowService: Gerencia a recuperação dos resultados das análises, fornecendo consultas sobre frequência de palavras, engajamento e posts processados.
- TarefaPreProcessamentoService: Implementa as regras para gerenciamento das tarefas dentro dos workflows, permitindo o cadastro, atualização e exclusão de funções que compõem o pré-processamento de textos.
- UsuarioService: Gerencia a autenticação de usuários e a integração com Bluesky, permitindo que os usuários recuperem perfis e autentiquem suas sessões.
- Interfaces de Comunicação: Além dos serviços internos, a camada inclui interfaces, como BlueskyService (para comunicação com a API externa do Bluesky), MessageBrokerProducer (para publicar mensagens no RabbitMQ) e MessageBrokerConsumer (para processar eventos de mensagens recebidas).

A camada de serviços é essencial para garantir que a lógica da aplicação esteja desacoplada da camada de persistência e dos controladores, promovendo organização, reusabilidade e escalabilidade.

Para expor essas funcionalidades aos usuários e ao frontend da aplicação, a camada Service se conecta diretamente com a Camada Controller, que será abordada a seguir. O próximo diagrama apresentará os controladores da API, responsáveis por receber requisições, validar os dados de entrada e encaminhar as chamadas aos serviços apropriados.

![Diagrama de classes do pacote controllers](imagens/sentilytics/diagramas/classes/controller-classes.png){#diagram_controller escala=0.2}

Fonte: Autor (2025).

A Figura \ref{diagram_controller} apresenta o Diagrama da Camada Controller, responsável por gerenciar as requisições HTTP e expor os endpoints da API. Essa camada atua como intermediária entre o frontend e a lógica de negócio, direcionando as requisições recebidas para os serviços apropriados e retornando as respostas processadas ao cliente.

Os controladores seguem a estrutura RESTful, organizando os endpoints de acordo com as funcionalidades da aplicação. A seguir, destacam-se os principais componentes dessa camada:

- PesquisaAnaliseSentimentosController: Gerencia operações relacionadas às pesquisas de análise de sentimentos, permitindo ao usuário criar, atualizar, listar e excluir pesquisas, além de buscar postagens associadas e importar dados via CSV.
- PostController: Responsável por excluir postagens específicas, garantindo a manutenção dos dados armazenados na plataforma.
- WorkflowProcessamentoController: Controla a execução dos workflows de processamento, possibilitando cadastro, atualização e remoção de workflows, além de iniciar as etapas de pré-processamento e análise de sentimentos. Esse controlador também fornece endpoints para consulta e manipulação das tarefas dentro de um workflow.
- ResultadosAnaliseWorkflowController: Disponibiliza os resultados gerados pela análise de sentimentos, incluindo frequência de palavras, análise temporal, engajamento médio e posts processados por sentimento.
- TarefaPreProcessamentoController: Permite a gestão das tarefas de pré-processamento, fornecendo operações para cadastro, atualização, listagem e remoção de tarefas associadas ao processamento textual.
- UsuarioController: Gerencia a autenticação de usuários e a integração com a plataforma Bluesky, possibilitando o login e a recuperação de perfis.
Os controladores utilizam ResponseEntity para padronizar as respostas da API, garantindo que cada requisição retorne um código de status adequado, além dos dados processados.

### Diagrama de Componentes

O Diagrama de Componentes é uma representação da estrutura da aplicação, destacando os principais serviços que a compõem e suas interações. Ele permite visualizar a separação dos módulos, auxiliando na manutenção e na compreensão da arquitetura do sistema.

No Sentilytics, a solução é composta por diferentes serviços que atuam de forma conjunta para viabilizar o fluxo de análise de sentimentos. A Figura \ref{diagrama_componentes} apresenta essa composição:

A Figura \ref{diagrama_componentes} a seguir apresenta a organização e a comunicação entre esses componentes.

![Diagrama de Componentes da Solução](imagens/sentilytics/diagramas/diagrama_componentes.png){#diagrama_componentes escala=0.4}

Fonte: Autor (2025).

Cada um dos componentes desempenha um papel essencial dentro da arquitetura do Sentilytics. A seguir, são apresentados detalhes sobre o funcionamento e a responsabilidade de cada módulo:

- Aplicação Python – Responsável pelo pré-processamento e análise de sentimentos das postagens, recebe as mensagens da fila do Message Broker para processar e envia mensagens para a fila quando um processo finaliza.
- RabbitMQ – Atua como broker de mensagens, permitindo comunicação assíncrona entre a aplicação Python e a Web API Spring Boot.
- Aplicação Spring Batch – Processa o arquivo CSV que contem as postagens em lote e faz a carga das postagens importadas no banco de dados.
- Web API Spring Boot – Exposição dos serviços da aplicação via API REST para o Angular, interligando todos os módulos.
- Frontend Angular – Interface do usuário para interação com a plataforma.
- Banco de Dados PostgreSQL – Armazena pesquisas, postagens e resultados da análise de sentimentos.

### Interfaces gráfica

A interface gráfica é um dos principais pontos de interação entre os usuários e a aplicação, sendo responsável por garantir uma experiência intuitiva na utilização do Sentilytics. Para o desenvolvimento da interface, foi utilizado o framework Angular.

A interface foi projetada para oferecer um fluxo de navegação claro e acessível, permitindo que os usuários cadastrem e configurem pesquisas, acompanhem o processamento dos dados e analisem os resultados da análise de sentimentos.

Nesta seção, são apresentadas as telas e componentes principais da interface do Sentilytics, detalhando a funcionalidade de cada interface e a forma como os usuários interagem com o sistema.

O primeiro ponto de contato do usuário com a aplicação ocorre na tela de login, que possibilita a autenticação no sistema. A seguir, é apresentada essa interface, destacando seus principais componentes e funcionalidades.

![Tela de Login do Sentilytics](imagens/sentilytics/interface-grafica/tela-login.png){#tela_login escala=0.2}

Fonte: Autor (2025).

A tela de login é a porta de entrada para o acesso ao Sentilytics, permitindo apenas a autenticação. Para manter a segurança e a simplicidade no gerenciamento de contas, o sistema utiliza o serviço do Bluesky como principal método de autenticação. Dessa forma, toda a criação ou administração de contas ocorre diretamente no Bluesky.

Ao inserir as credenciais corretas, o sistema valida as informações diretamente com a API do Bluesky, garantindo a autenticação segura. Caso as credenciais sejam inválidas, o usuário recebe um aviso para revisar os dados informados.

Essa abordagem proporciona uma experiência simplificada para o usuário, eliminando a necessidade de criar e lembrar novas senhas, ao mesmo tempo em que mantém um padrão seguro e confiável de autenticação. Após a autenticação, o usuário é direcionado para a tela de listagem de pesquisas, onde pode visualizar todas as análises de sentimentos já criadas.

![Tela de Listagem de Pesquisas](imagens/sentilytics/interface-grafica/listagem-pesquisas.png){#tela_listagem_pesquisas escala=0.2}

Fonte: Autor (2025).

Após a autenticação, o usuário é direcionado para a tela de listagem de pesquisas, onde pode visualizar todas as pesquisas de análise de sentimentos já criadas.

Nesta tela, o usuário tem a opção de cadastrar ou deletar uma pesquisa, onde ao clicar no botão "Cadastrar Pesquisa", uma janela modal é exibida solicitando o nome da pesquisa e a query inicial de busca. Após a confirmação do cadastro, a nova pesquisa é adicionada à lista.

Para acessar os detalhes de uma pesquisa já cadastrada, o usuário pode selecioná-la na listagem, sendo automaticamente redirecionado para a tela de visualização da pesquisa, onde poderá acompanhar e gerenciar os dados coletados.

![Tela de Exibição da Pesquisa](imagens/sentilytics/interface-grafica/dados-pesquisa.png){#tela_dados_pesquisa escala=0.2}

Fonte: Autor (2025).

A tela da pesquisa mostrada na figura \ref{tela_dados_pesquisa} é a interface central para o gerenciamento de uma análise de sentimentos dentro do Sentilytics. Essa tela organiza o fluxo do usuário em quatro etapas, representadas por botões dispostos em sequência:

1. Dados da Pesquisa;
1. Coleta de Dados;
1. Pré-processamento;
1. Resultados;

Cada etapa pode ser clicada para alternar os elementos exibidos abaixo, permitindo que o usuário navegue entre as diferentes fases do processo de análise. Para facilitar a visualização do progresso, as etapas são coloridas conforme seu estado atual:

- Verde – Etapa concluída, indicando que todas as ações necessárias foram realizadas.
- Amarelo – Etapa pendente, sinalizando que há ações a serem executadas antes de avançar.
- Cinza – Etapa inacessível, indicando que ainda há pré-requisitos a serem cumpridos antes de prosseguir.

No primeiro acesso, o usuário visualiza a aba "Dados da Pesquisa", onde pode configurar ou alterar as informações utilizadas na busca de postagens, caso a coleta de dados via Bluesky seja ativada.

Cada uma das próximas etapas é liberada de acordo com a sequência do fluxo, garantindo que o usuário siga um processo estruturado para a realização da pesquisa.

A etapa atual exibida na figura \ref{tela_dados_pesquisa} é a "Dados da Pesquisa", nesse momento o usuário pode visualizar e modificar as informações da pesquisa. Esses dados serão utilizados caso o usuário opte por realizar a coleta automática de postagens através da rede social Bluesky. Essa configuração permite definir os critérios de busca que serão aplicados na obtenção dos posts, garantindo que a análise de sentimentos seja realizada com base em conteúdos relevantes.

Após definir os dados da pesquisa, o próximo passo é a coleta de postagens, onde o usuário pode importar dados manualmente ou realizar a busca automática via Bluesky.

![Etapa de Coleta de Dados](imagens/sentilytics/interface-grafica/coleta-dados.png){#tela_coleta_dados_pesquisa escala=0.2}

Fonte: Autor (2025).

Na figura \ref{tela_coleta_dados_pesquisa} é mostrada a etapa de coleta dos dados, nessa fase o usuário pode gerenciar as postagens que serão analisadas no Sentilytics. O usuário pode visualizar os posts já armazenados no sistema e optar por adicionar novos dados por meio de duas opções de coleta:

- Busca automática no Bluesky – O sistema realiza uma pesquisa na rede social Bluesky, coletando postagens conforme os critérios definidos na etapa anterior.
- Importação via CSV – O usuário pode carregar um arquivo contendo postagens previamente coletadas. Para auxiliar nesse processo, a interface exibe um tutorial explicativo, orientando como preparar o arquivo corretamente.

Além da adição de novos posts, a tela também oferece a opção de excluir postagens específicas, permitindo ao usuário refinar os dados que serão utilizados na análise.

Com os posts devidamente coletados e organizados, o usuário pode avançar para a próxima etapa: o processamento, onde os textos serão preparados para a análise de sentimentos.

![Etapa de Processamento](imagens/sentilytics/interface-grafica/processamento.png){#tela_processamento escala=0.2}

Fonte: Autor (2025).

A figura \ref{tela_processamento} mostra a etapa de processamento, onde o usuário pode configurar e executar as etapas necessárias para preparar e analisar as postagens coletadas. Nessa passo, o usuário pode criar um workflow, que define a sequência de tarefas de pré-processamento aplicadas aos textos antes da análise de sentimentos.

As principais ações disponíveis nesta etapa incluem:

- Criar um workflow – O usuário pode definir um novo fluxo de pré-processamento, adicionando as tarefas que serão aplicadas às postagens antes da análise de sentimentos.
- Excluir um workflow – Caso um workflow não seja mais necessário, ele pode ser removido do sistema.
- Executar o pré-processamento – Após a criação do workflow, o usuário pode iniciar o pré-processamento, que realiza transformações nos textos coletados, como normalização e remoção de elementos indesejados.
- Executar a análise de sentimentos – Quando o pré-processamento é concluído, o usuário pode prosseguir com a análise de sentimentos, onde as postagens processadas são classificadas de acordo com suas emoções ou polaridade textual.

O pré-processamento e a análise de sentimentos podem ser repetidos quantas vezes forem necessárias dentro de um workflow, permitindo ajustes na configuração e refinamento dos resultados.

É importante pontuar que caso novas postagens sejam adicionadas após um workflow já ter sido executado, elas não serão automaticamente refletidas nos resultados anteriores. Para incluir as novas postagens na análise, o workflow precisa ser processado novamente, garantindo que todas as postagens passem pelas etapas de pré-processamento e análise de sentimentos.

Com o workflow finalizado, o usuário pode avançar para a última etapa do processo: a visualização dos resultados, onde os *insights* extraídos das postagens processadas são apresentados de forma estruturada.

![Etapa de Resultados](imagens/sentilytics/interface-grafica/resultado-graficos.png){#etapa_resultados escala=0.2}

Fonte: Autor (2025).

A etapa de resultados mostrado na figura \ref{etapa_resultados} permite ao usuário visualizar e interpretar os dados processados a partir da análise de sentimentos. Para acessar essa etapa, é necessário selecionar um workflow que já tenha passado pelo processo completo de pré-processamento e análise de sentimentos. Após a seleção do workflow, o restante do conteúdo da tela é exibido, oferecendo três abas principais para exploração dos resultados:

1. Aba de Gráficos
Essa aba apresenta quatro gráficos interativos, que auxiliam na compreensão da distribuição dos sentimentos e do impacto das postagens analisadas:

- Quantidade de Comentários por Sentimentos – Um gráfico de pizza que exibe a porcentagem e o número total de postagens classificadas em cada sentimento.
- Média de Engajamento por Sentimentos – Um gráfico de barras verticais que relaciona a média de curtidas, reposts, respostas e citações para cada tipo de sentimento identificado.
- Total de Engajamento por Sentimentos – Um gráfico de barras verticais que exibe o total acumulado de interações (likes, reposts, respostas e citações) para cada sentimento.
- Análise Temporal de Sentimentos – Um gráfico que acompanha a variação dos sentimentos ao longo do tempo, permitindo identificar tendências e padrões emocionais nos dados coletados.

1. Aba de Nuvem de Palavras
Nesta aba, é exibida uma nuvem de palavras gerada a partir dos textos processados. Essa visualização destaca as palavras mais frequentes nas postagens analisadas, permitindo uma análise rápida dos termos mais relevantes dentro do contexto dos dados.

1. Aba de Top Posts Engajados
Essa aba apresenta uma listagem dos posts mais engajados, ranqueados com base no número de curtidas, respostas, reposts e citações. Além disso, há um filtro por sentimento, permitindo que o usuário explore os posts de acordo com suas classificações emocionais.

Cada post exibido nesta listagem pode ser visualizado em sua forma original e após o pré-processamento, permitindo que o usuário compreenda como as transformações realizadas impactaram o conteúdo analisado.

![QRCode com link para o vídeo](imagens/sentilytics/qr_code.png){#qrcode escala=0.6}

Fonte: Autor (2025).

Para complementar o entendimento do processo descrito, a \autoref{qrcode} apresenta um QR Code que direciona para um vídeo demonstrativo. No vídeo, é possível acompanhar de forma prática e detalhada todas as etapas da criação de uma pesquisa de análise de sentimentos no Sentilytics, desde a autenticação até a visualização dos resultados.

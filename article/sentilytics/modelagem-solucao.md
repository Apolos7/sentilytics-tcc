## Modelagem da solução

A modelagem da solução é uma etapa fundamental no desenvolvimento de sistemas, pois permite a representação visual e descritiva dos componentes, fluxos de dados e interações entre os elementos da aplicação. Através dessa modelagem, é possível compreender a estrutura da solução proposta, identificar os requisitos essenciais e garantir que a implementação esteja alinhada com os objetivos do projeto.

A aplicação desenvolvida para análise de sentimentos em redes sociais exige uma modelagem robusta que aborde tanto os aspectos funcionais quanto os estruturais do sistema. Para isso, são utilizados diferentes diagramas e especificações, que descrevem desde os requisitos funcionais e não funcionais até a arquitetura dos componentes e o fluxo de processamento dos dados.

Inicialmente, são definidos os requisitos funcionais e não funcionais, que estabelecem as funcionalidades esperadas e as restrições técnicas da aplicação. Em seguida, o Diagrama de Caso de Uso apresenta as principais interações entre os usuários e o sistema, facilitando a compreensão das funcionalidades disponíveis.

Para representar o fluxo de execução dos processos dentro da aplicação, são utilizados diagramas BPMN (Business Process Model and Notation) e diagramas de sequência/atividades, que detalham as etapas do pré-processamento e da análise de sentimentos. Além disso, a estrutura de dados e as relações entre entidades são documentadas por meio do Diagrama Entidade-Relacionamento (DER) e do dicionário de dados.

A organização dos componentes do sistema é descrita no Diagrama de Componentes, que ilustra a arquitetura da aplicação, destacando a comunicação entre os módulos do backend, frontend e serviços externos. Complementarmente, o Diagrama de Classes define a estrutura da lógica de programação, detalhando as principais classes e seus relacionamentos.

Por fim, as interfaces gráficas são apresentadas para demonstrar a experiência do usuário e a forma como as funcionalidades da aplicação são disponibilizadas. Essas interfaces são projetadas para garantir usabilidade, responsividade e uma experiência intuitiva, permitindo que os usuários explorem as análises de sentimentos de maneira eficiente.

Com essa modelagem, busca-se garantir que a aplicação seja bem estruturada, escalável e de fácil manutenção, possibilitando futuras melhorias e adaptações conforme novas necessidades forem identificadas.


### Requisitos Funcionais e Não Funcionais

Para garantir que a aplicação de análise de sentimentos em redes sociais atenda aos objetivos propostos, é essencial definir os requisitos funcionais e não funcionais. Os requisitos funcionais descrevem as funcionalidades que o sistema deve oferecer, especificando as interações entre usuários e a aplicação. Já os requisitos não funcionais estabelecem critérios de qualidade, desempenho, segurança e usabilidade, assegurando que a solução seja eficiente, escalável e de fácil manutenção.

A seguir, são apresentados os requisitos funcionais e não funcionais que orientaram o desenvolvimento da solução proposta.


- RF01 - Coleta de Dados: O sistema deve permitir a coleta de postagens da rede social Bluesky, respeitando parâmetros de data inicial, data final, query de busca e linguagem;

- RF02 - Importação de dados via Arquivo CSV: O sistema deve permitir como forma alternativa a importação de postagens no formato CSV para análise de sentimentos, utilizando Spring Batch para processamento da importação;

- RF03 - Configuração de Workflows: O sistema deve permitir que o usuário configure workflows e escolha quais tarefas de pré-processamento serão aplicadas aos dados coletados;

- RF04 - Pré-processamento de Dados: O sistema deve realizar a limpeza e normalização dos textos coletados, incluindo remoção de stopwords, lematização e tokenização;

- RF05 - Análise de Sentimentos: O sistema deve calcular a pontuação de sentimentos de cada comentário, classificando-os como positivos, negativos ou neutros com base em regras de pontuação composta;

- RF06 - Armazenamento de Resultados: O sistema deve armazenar os resultados da análise de sentimentos em uma tabela de banco de dados, incluindo a quantidade total de comentários e a distribuição de sentimentos;

- RF07 - Consulta de Resultados: O sistema deve permitir a consulta dos resultados da análise de sentimentos, filtrando por período, rede social e sentimento predominante;

- RF08 - Integração entre Módulos: O sistema deve permitir a comunicação entre o backend em Spring Boot e o serviço de análise de sentimentos em Python por meio de RabbitMQ;

- RF09 - Autenticação e Autorização: O sistema deve permitir que usuários se autentiquem utilizando suas credenciais da rede social Bluesky, sem a necessidade de cadastro adicional;

- RF10 - Interface Web: O sistema deve fornecer uma interface web baseada em Angular para que os usuários possam interagir com as funcionalidades de análise de sentimentos.

- RFN01 - Não funcional:


### Diagramas de Caso de Uso

Os diagramas de caso de uso são representações gráficas que demonstram as interações entre os usuários e um sistema, destacando as principais funcionalidades disponíveis. Seu objetivo é ilustrar, de forma simples, como os diferentes atores interagem com o sistema em cenários específicos, auxiliando na compreensão dos requisitos e no planejamento da aplicação. A seguir, apresenta-se um caso de uso relevante do Sentilytics.

![Diagrama de Casos de Uso do Sentilytics](imagens/sentilytics/diagramas/usecase.png){#usecase escala=0.1}

Fonte: Autor (2025).

Como podemos visualizar na figura \ref{usecase}, o usuário

### BPMN

A Business Process Model and Notation (BPMN) é uma notação padronizada para modelagem de processos de negócios, utilizada para representar o fluxo de atividades dentro de um sistema ou organização. Seu propósito é fornecer uma visão clara das etapas envolvidas em um processo, facilitando sua análise e compreensão. A seguir, apresenta-se um diagrama BPMN relacionado ao funcionamento do Sentilytics.

![Modelagem BPMN](imagens/sentilytics/pesquisa_sentimentos.png){#bpmn_pesquisa escala=0.1}

Fonte: Autor (2025).

Como podemos visualizar na figura \ref{bpmn_pesquisa}, o usuário

### Diagrama de Sequência/Atividades do pré-processamento e análise de sentimentos

Os diagramas de sequência são utilizados para representar a interação entre diferentes componentes de um sistema ao longo do tempo. Eles detalham a ordem das mensagens trocadas entre os elementos envolvidos, permitindo a visualização do fluxo de execução de um processo específico. Essa abordagem facilita a compreensão da dinâmica do sistema e auxilia na identificação de dependências entre os componentes.

No contexto do Sentilytics, foram elaborados três diagramas de sequência que descrevem processos essenciais para o funcionamento da aplicação:

Figura \ref{seq_pesquisa_coleta_dados}: Cadastro da pesquisa e coleta de dados.
Figura \ref{seq_cadastro_configuracao_workflow}: Cadastro e configuração do workflow.
Figura \ref{seq_processamento_analise}: Sequência de processamento, incluindo o pré-processamento do workflow e da análise de sentimentos.

Cada um desses diagramas detalha a troca de informações entre os elementos do sistema, evidenciando os passos necessários para a execução dessas funcionalidades. A seguir, apresentam-se essas representações gráficas.

![Diagrama pesquisa](imagens/sentilytics/diagramas/sequencia-cadastro-pesquisa-coleta-dados.png){#seq_pesquisa_coleta_dados escala=0.1}

Fonte: Autor (2025).

O diagrama na figura \ref{seq_pesquisa_coleta_dados} mostra o processo de cadastro e coleta de dados, abaixo o diagrama exibe os próximos passos.

![Diagrama pesquisa](imagens/sentilytics/diagramas/sequencia-cadastro-configuracao-workflow.png){#seq_cadastro_configuracao_workflow escala=0.1}

Fonte: Autor (2025).

O diagrama da figura \ref{seq_cadastro_configuracao_workflow} descreve o processo de cadastro e configuração do workflow, abaixo o diagrama exibe os próximos passos.

![Diagrama da sequencia](imagens/sentilytics/diagramas/sequencia-pre-processamento-analise-sentimentos.png){#seq_processamento_analise escala=0.1}

Fonte: Autor (2025).

O diagrama da figura \ref{seq_cadastro_configuracao_workflow} descreve o processo de cadastro e configuração do workflow.

### Diagrama de Classe

Como já vimos, os diagramas auxiliam na construção

### Diagrama Entidade-Relacionamento (DER) e Dicionário de dados

O Diagrama Entidade-Relacionamento (DER) é uma representação visual da estrutura do banco de dados, destacando as entidades, seus atributos e os relacionamentos entre elas. Ele permite compreender a organização dos dados e a forma como as informações são armazenadas e manipuladas dentro do sistema. No Sentilytics, o DER foi desenvolvido utilizando a ferramenta Vertabelo, garantindo uma modelagem estruturada e alinhada com os requisitos do sistema.

Complementando a modelagem do banco de dados, o Dicionário de Dados fornece uma descrição detalhada das tabelas, colunas, tipos de dados e restrições existentes. Esse recurso facilita a documentação do sistema, servindo como referência para o desenvolvimento e manutenção do banco de dados. Assim como o DER, o Dicionário de Dados do Sentilytics foi elaborado no Vertabelo, permitindo a exportação e documentação estruturada dos elementos do banco.

![Diagrama Entidade Relacionamento](imagens/sentilytics/diagramas/DER-sentilytics.png){#der escala=0.1}

Fonte: Autor (2025).

A Figura \ref{der} apresenta o Diagrama Entidade-Relacionamento, demonstrando a estrutura do banco de dados da aplicação.

### Diagrama de Componentes

O Diagrama de Componentes é uma representação da estrutura de uma aplicação, evidenciando os principais serviços e como eles se relacionam para compor a solução. Ele permite visualizar os módulos independentes do sistema e suas interações, auxiliando na compreensão da arquitetura e na manutenção da aplicação.

No contexto do Sentilytics, o diagrama de componentes apresenta os serviços essenciais que integram a solução, incluindo processamento, armazenamento e interface com o usuário. A Figura X ilustra essa composição, destacando os seguintes elementos:

- Aplicação Python – Responsável por executar o pré-processamento e a análise de sentimentos nas postagens.
- RabbitMQ – Utilizado como broker de mensagens para comunicação assíncrona entre os serviços.
- Aplicação Spring Batch – Responsável pelo processamento em lote de workflows e análise de sentimentos.
- Web API Spring Boot – Exposição dos serviços da aplicação via API REST.
- Frontend Angular – Interface do usuário para interação com a plataforma.
- Banco de Dados PostgreSQL – Armazena os dados da aplicação, incluindo pesquisas e resultados das análises.

A Figura \ref{diagrama_componentes} a seguir apresenta a estrutura desses componentes e suas interações dentro da arquitetura do Sentilytics.

![Diagrama de Componentes da Solução](imagens/sentilytics/diagramas/diagrama_componentes.png){#diagrama_componentes escala=0.1}

Fonte: Autor (2024).

testando aqui o funcionamento dessa parte

### Interfaces gráfica

Como já vimos, os diagramas auxiliam na construção

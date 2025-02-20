As redes sociais é o ambiente, no meio digital, em que os indivíduos expressam suas percepções e sentimentos sobre temas variados, desde questões cotidianas até debates complexos de relevância nacional, como mudanças trabalhistas ou propostas legislativas. É um espaço que possibilita diferentes formas de socialização, no qual os participantes são emissores e receptores no processo de comunicação. No Brasil, as redes sociais desempenham um papel crucial como meio de comunicação e tem se resignificado como um espaço ativo para compreensão da opinião pública e articulação política.

Além de seu papel na articulação política, as redes sociais também exercem um impacto significativo na economia e no comportamento das novas gerações. No campo econômico, esses espaços têm sido utilizados por empresas para monitorar tendências de mercado, analisar a receptividade de produtos e serviços, e engajar diretamente com consumidores, moldando estratégias de marketing e consumo. Por outro lado, para os jovens, as redes sociais representam não apenas um canal de entretenimento, mas também um espaço de mobilização e conscientização social. Esses espaços permitem que eles se envolvam ativamente em discussões sobre temas globais, como mudanças climáticas, direitos humanos e questões trabalhistas, como o debate em torno da escala 6x1, ampliando o alcance e a visibilidade dessas pautas.

A análise desses sentimentos é essencial para compreender tendências, identificar polarizações e auxiliar na tomada de decisões estratégicas em áreas como comunicação, política e negócios.

Entretanto, a análise de sentimentos em redes sociais apresenta desafios significativos. Muitas ferramentas existentes não oferecem uma solução integrada e intuitiva para o processamento completo, desde a coleta de dados até a classificação dos sentimentos. Frequentemente, esses processos exigem que os usuários utilizem terminais e comandos técnicos para aplicar funções básicas, o que pode dificultar o uso por parte de profissionais ou pesquisadores com pouca familiaridade técnica. Além disso, essas ferramentas muitas vezes não permitem personalização ou integração direta com redes sociais.

Diante desse cenário, foi desenvolvido o Sentilytics, uma aplicação para automatização da análise de sentimentos personalizadas em redes sociais. O Sentilytics automatiza o processo desde a coleta de dados até a análise final, com uma personalização completa que permite aos usuários criar *workflows*[^workflows] configuráveis com diferentes funções de pré-processamento. Além disso, a ferramenta possui integração direta com a rede social Bluesky, garantindo que o fluxo de trabalho seja otimizado e acessível, mesmo para usuários com pouca experiência técnica. Essa abordagem automatizada e personalizável busca atender às demandas crescentes por análises eficientes e adaptadas à realidade brasileira.

Para validar a aplicação, foi realizado um estudo de caso utilizando o Sentilytics para analisar sentimentos relacionados ao fim da escala 6x1, uma pauta atual e polarizadora no contexto trabalhista brasileiro. O tema foi escolhido pela relevância, atualidade e quantitativo de interações entre os usuários da rede, permitindo a identificação de padrões de engajamento em um debate de grande impacto social.

[^workflows]: Workflow pode ser definido como um conjunto de tarefas organizadas.

## Objetivo Geral

O presente trabalho tem como objetivo geral desenvolver uma aplicação para automatizar o processo de análise de sentimentos personalizada em redes sociais, denominada Sentilytics. A aplicação busca oferecer um fluxo completo, desde a coleta de dados até a análise dos sentimentos, com funcionalidades personalizáveis e acessíveis, permitindo a criação de *workflows* configuráveis para atender diferentes necessidades analíticas.

## Objetivos Específicos

Para alcançar o objetivo geral proposto, o presente trabalho foi estruturado em etapas especificas necessárias para a construção e validação da solução desenvolvida. A seguir, são apresentados os objetivos específicos que direcionaram o desenvolvimento da solução e realização do estudo de caso.

- Implementar funcionalidades de coleta automatizada de dados em redes sociais integradas à aplicação.
- Desenvolver um módulo de pré-processamento customizável, permitindo que o usuário configure *workflows* com diferentes tarefas, como normalização e remoção de *stopwords*.
- Integrar a aplicação com o modelo de análise de sentimentos VADER para classificar sentimentos em positivo, neutro e negativo.
- Criar mecanismos para exibir os resultados da análise de forma visual, como gráficos, tabelas e nuvens de palavras, facilitando a interpretação dos dados.
- Realizar um estudo de caso para validar o Sentilytics, analisando sentimentos relacionados ao debate sobre o fim da escala 6x1.

## Relevância do trabalho

A análise de sentimentos é um campo de pesquisa em constante crescimento, especialmente no contexto das redes sociais, que são ricas em dados emocionais e opinativos. Este trabalho contribui para a área acadêmica ao propor uma solução integrada e automatizada, o Sentilytics, que possibilita a coleta de dados diretamente do Bluesky, uma alternativa viável em um cenário onde muitas plataformas tornaram o acesso aos dados mais restrito ou pago. Além disso, a criação de *workflows* configuráveis oferecem uma abordagem prática para superar as limitações técnicas frequentemente enfrentadas por pesquisadores, simplificando etapas complexas e manuais.

O desenvolvimento do Sentilytics introduz uma abordagem modular da arquitetura, construída com tecnologias como Spring Boot, RabbitMQ e PostgreSQL, garante escalabilidade e flexibilidade para a incorporação de novos modelos de análise de sentimentos ou tarefas de pré-processamento, evidenciando o potencial de expansão da ferramenta para diferentes contextos.

No contexto das redes sociais, que hoje são fundamentais para a formação de opiniões e debates públicos, a análise de sentimentos desempenha um papel central na compreensão de tendências e polarizações. Este trabalho contribui diretamente para esse campo ao oferecer uma ferramenta que possibilita a análise automatizada de dados emocionais expressos em postagens. O Sentilytics pode ser utilizado para identificar sentimentos predominantes, compreender padrões de engajamento e fornecer informações úteis para tomadores de decisão, pesquisadores e organizações que desejam entender a dinâmica social em torno de temas complexos.

A relevância deste trabalho vai além de seu impacto imediato, demonstrando como soluções tecnológicas inovadoras podem ser aplicadas para explorar questões sociais e emocionais em um ambiente digital cada vez mais complexo. A flexibilidade e escalabilidade do Sentilytics abrem espaço para sua aplicação em diferentes áreas, como marketing, economia, política, psicologia social e ciência de dados, tornando-o uma ferramenta promissora tanto para estudos acadêmicos quanto para aplicações práticas.

## Estrutura do Trabalho

Este trabalho está organizado em 5 capítulos, além desta introdução, que apresenta o contexto do problema, os objetivos e a relevância do estudo. No capítulo 2, é apresentada a fundamentação teórica, abordando temas como a influência das redes sociais na sociedade, conceitos sobre  análise de sentimentos e sua realização em redes sociais. O capítulo 3 detalha a construção e a modelagem do Sentilytics, desde a definição dos requisitos, diagramação até as interfaces gráficas. O capítulo 4 discute a metodologia adotada no estudo de caso, incluindo a coleta de dados, pré-processamento, análise de sentimentos, resultados obtidos. Por fim, no capítulo 5, são apresentadas as conclusões do trabalho, bem como as limitações encontradas e sugestões para trabalhos futuros.

## Análise gráfica e textual do Sentilytics

Nesta seção, são apresentados os principais resultados obtidos com o Sentilytics na análise de sentimentos sobre temas políticos no Bluesky. A ferramenta gerou diferentes representações visuais, incluindo gráficos de distribuição de sentimentos, nuvens de palavras e os posts mais engajados. Além disso, *insights* gerados por inteligência artificial auxiliaram na interpretação dos dados, fornecendo resumos e tendências detectadas automaticamente. A seguir, cada gráfico é analisado individualmente, seguido de uma discussão geral sobre os padrões observados e suas possíveis implicações.

![Gráfico de Número de Comentários por Sentimentos](imagens/sentilytics/estudo-caso/quantidade_comentarios_por_sentimentos.png){#grafico_numero_comentarios_por_sentimento escala=0.3}

Fonte: Autor (2025).

O gráfico apresentado na \autoref{grafico_numero_comentarios_por_sentimento} exibe a distribuição dos sentimentos nas postagens analisadas. Observa-se que a maioria das postagens foi classificada como **neutra**, representando 87,3% do total. Já os sentimentos **positivos** correspondem a 10,5%, enquanto os **negativos** representam apenas 2,2% das postagens.

No contexto político, o debate sobre a escala 6x1 ganhou destaque no último ano, impulsionado pela apresentação de uma Proposta de Emenda à Constituição (PEC) que propõe seu fim. A análise dos comentários coletados revela que a maioria das postagens apresenta um tom neutro, sugerindo que grande parte das discussões tem caráter informativo ou analítico. No entanto, entre as postagens que expressam um viés emocional, observa-se uma predominância de sentimentos positivos em relação ao tema. Esse resultado indica que há uma inclinação favorável da opinião pública quanto à possibilidade de alteração ou extinção da escala 6x1, refletindo um possível apoio da população a mudanças na organização da jornada de trabalho.

O Sentilytics também gerou um insight baseado em AI para analisar o resultado do gráfico, interpretando a predominância do sentimento de neutralidade da seguinte forma: "Em suma, a análise de sentimentos revela uma necessidade de explorar mais a fundo as razões subjacentes ao otimismo ou pessimismo contidos nos 512 comentários positivos e nos 105 negativos, bem como entender como estimular uma participação mais ativa do público que se mostrou neutro.".

Esse resultado sugere que, apesar da predominância de comentários neutros, ainda existe a necessidade de entender melhor os sentimentos positivos e negativos expressos pela população. O alto número de postagens neutras pode ser interpretado como uma cautela do público em relação ao tema, especialmente considerando que mudanças trabalhistas costumam gerar incertezas.

Embora os resultados apresentados forneçam uma visão geral sobre a distribuição dos sentimentos, é importante considerar as limitações inerentes ao modelo de análise utilizado. A predominância de comentários classificados como neutros pode indicar uma limitação da ferramenta, decorrente do uso de um modelo baseado em léxicos.

![Gráfico da Média de Engajamento por Sentimentos](imagens/sentilytics/estudo-caso/media_engajamento_por_sentimento.png){#grafico_media_engajamento escala=0.3}

Fonte: Autor (2025).

Na \autoref{grafico_media_engajamento}, é apresentado um gráfico de barras que ilustra a média de engajamento por sentimento, considerando as interações dos usuários, como likes, repostagens, respostas e citações. Cada barra no gráfico representa a média calculada para um tipo específico de interação, agrupada de acordo com os sentimentos Positivo, Negativo e Neutro.

A análise desse gráfico permite identificar qual categoria de sentimento gera maior engajamento geral, bem como tendências específicas por tipo de interação. Por exemplo, é possível observar se posts com sentimentos negativos recebem mais repostagens, indicando maior disseminação de conteúdos críticos, ou se postagens neutras geram mais respostas, sugerindo uma maior propensão ao debate e à troca de informações.

A análise do gráfico da \autoref{grafico_media_engajamento} revela que os sentimentos negativos geraram o maior engajamento geral, destacando-se especialmente pela média de likes e reposts. Esse padrão sugere que conteúdos críticos ou de tom negativo tendem a atrair mais atenção e interação do público, possivelmente devido à inclinação dos usuários em amplificar mensagens com caráter negativo ou polarizador.

![Gráfico da Total de Engajamento por Sentimentos](imagens/sentilytics/estudo-caso/media_engajamento_por_sentimento.png){#grafico_total_engajamento escala=0.3}

Fonte: Autor (2025).

O gráfico apresentado na \autoref{grafico_total_engajamento} exibe o total de interações por sentimento, podemos interpretar esse gráfico observando quais sentimentos geram o maior volume absoluto de engajamento, bem como identificar padrões na distribuição das interações por tipo. ao contrário do gráfico da \autoref{grafico_media_engajamento} que mostra a média, este gráfico analisa o impacto acumulado das interações em cada categoria de sentimento.

Os resultados apresentados no gráfico mostram que postagens com sentimento neutro tiveram um engajamento significativamente maior em todas as métricas analisadas. Esse padrão indica que conteúdos classificados como neutros possuem um impacto acumulado mais alto, possivelmente devido à maior quantidade de postagens nesta categoria. Por outro lado, ao comparar os sentimentos negativos e positivos podemos notar que o sentimento negativo gera um volume maior de repostagens.

![Gráfico da Análise Temporal de Sentimentos](imagens/sentilytics/estudo-caso/analise_temporal_sentimentos.png){#grafico_analise_temporal escala=0.26}

Fonte: Autor (2025).

O gráfico apresentado na \autoref{grafico_analise_temporal} exibe a evolução dos níveis de sentimento (Positivo, Negativo e Neutro) ao longo de um período de dias. Cada ponto no gráfico representa o valor médio do sentimento para aquele dia, variando entre 0 e 1, onde valores mais próximos de 1 indicam uma maior intensidade do sentimento correspondente nas postagens analisadas.

Esse tipo de gráfico é útil para identificar tendências temporais no comportamento emocional das postagens, permitindo observar oscilações nos sentimentos predominantes durante eventos específicos ou mudanças graduais no tom das interações ao longo do tempo.

A partir da análise do gráfico da \autoref{grafico_analise_temporal}, podemos identificar que o sentimento neutro se mantém em uma linha estável, possuindo menos variações, o que é coerente com o que vimos em análise anteriores. Em relação a análise dos sentimentos positivos e negativos, podemos visualizar mais variações marcadas e pontuais, com picos em alguns dias específicos.

![Nuvem de Palavras](imagens/sentilytics/estudo-caso/bag_of_words.png){#nuvem_palavras escala=0.4}

Fonte: Autor (2025).

Na \autoref{nuvem_palavras} podemos visualizar a nuvem de palavras gerada na aplicação, ela mostra as palavras mais frequentes nos textos analisados, sendo baseada no texto pré-processado. Isso significa que elementos irrelevantes foram removidos (como stopwords), e apenas os termos significativos foram mantidos. A frequência de cada palavra determina o destaque que ela recebe na nuvem, permitindo identificar rapidamente os principais tópicos e padrões debatidos pelos usuários.

A análise da nuvem de palavras reforça que a discussão sobre o fim da escala 6x1 é central e polarizadora, com "escala" (5.365 ocorrências) e "6x1" (5.020 ocorrências) sendo os termos mais frequentes, seguidos por "fim" (2.229 ocorrências). Isso demonstra o foco principal no impacto e nas mudanças associadas à proposta.

Os termos "contra" (894 ocorrências) e "pra" (982 ocorrências) sugerem uma oposição ou apoio ativo à pauta, indicando que a comunidade está dividida entre grupos que defendem ou rejeitam o fim da escala. Além disso, palavras como "trabalho" (529 ocorrências), "trabalhadores" (268 ocorrências) e "jornada" (134 ocorrências) indicam que a discussão também foca nos impactos diretos sobre a rotina e os direitos dos trabalhadores.

A presença de palavras como "governo" (257 ocorrências), "direita" (230 ocorrências) e "esquerda" (256 ocorrências) sugere que o debate não é apenas técnico ou econômico, mas também politizado, com diferentes ideologias influenciando as percepções públicas sobre o tema.

Por fim, termos como "luta" (243 ocorrências) e "vida" (253 ocorrências) reforçam o caráter emocional do discurso, destacando que essa proposta é vista como algo que impacta diretamente a qualidade de vida e as condições de trabalho da população. Diante desse cenário, a análise gerada por IA (Inteligência Artificial) na aplicação oferece uma interpretação dos dados, ajudando a contextualizar esses padrões e fornecendo *insights* sobre como o público está reagindo ao debate.

![Top posts Engajados](imagens/sentilytics/estudo-caso/top_posts_engajados.png){#top_posts_engajados escala=0.2}

Fonte: Autor (2025).

A tela apresentada na \autoref{top_posts_engajados} exibe os top posts com maior engajamento, permitindo uma análise detalhada das postagens mais populares no contexto da pesquisa. Essa funcionalidade organiza os posts ranqueados com base na soma total de interações realizadas pelo usuário, apresentados de forma decrescente para destacar os conteúdos que mais mobilizaram o público.

A aplicação também oferece a funcionalidade de aplicar filtros por sentimento (Positivo, Neutro e Negativo), permitindo que o usuário identifique facilmente quais tipos de conteúdos geraram mais interação em cada categoria emocional. Além disso, é possível visualizar tanto o texto original do post quanto sua versão pré-processada, facilitando a compreensão de como as etapas de processamento (como remoção de stopwords ou normalização) impactaram a análise. Essa funcionalidade possibilita que o usuário valide os resultados obtidos e compreenda de forma mais aprofundada os padrões de engajamento associados a cada tipo de postagem.

A funcionalidade de top posts engajados, com a visualização do texto original e pré-processado, representa uma ferramenta importante para analisar como a audiência responde a conteúdos emocionais, informativos ou polêmicos, oferecendo uma visão prática e direta dos dados processados pela aplicação.

### Limitações do Estudo de Caso

Embora o presente estudo tenha alcançado seus objetivos principais, é importante reconhecer algumas limitações que podem ter impactado os resultados e a abrangência da análise. Essas limitações estão relacionadas tanto à aplicação Sentilytics quanto ao escopo do estudo de caso, e incluem:

1. Integração limitada à rede social Bluesky: Atualmente, o Sentilytics está integrado apenas à rede social Bluesky, uma plataforma que ainda não possui grande relevância no Brasil e é pouco utilizada em comparação com outras redes sociais, como X (Antigo Twitter) e Facebook. Essa limitação reduz a representatividade da análise, já que os dados coletados refletem um público menor e potencialmente menos diversificado.

1. Opções limitadas de pré-processamento e análise de sentimentos: O Sentilytics oferece atualmente um número reduzido de tarefas de pré-processamento e utiliza apenas o VADER como modelo de análise de sentimentos. Embora o formato atual da aplicação permita a adição de outras funções sem a necessidade de alterações significativas, essas limitações podem impactar a qualidade dos resultados, especialmente para textos em português, onde o VADER tem dificuldades em captar nuances emocionais, como ironia e sarcasmo.

1. Tamanho da amostra de dados: O estudo considerou uma amostra de 4.880 postagens coletadas no Bluesky. Embora seja suficiente para uma análise inicial, um número maior de postagens poderia fornecer uma visão mais abrangente e robusta sobre os padrões de engajamento e os sentimentos expressos pela audiência.

1. Viés na análise de sentimentos: O modelo de análise de sentimentos utilizado, o VADER, apresenta limitações conhecidas, como dificuldade para interpretar ironias, sarcasmos e textos altamente subjetivos, o que é comum em postagens de redes sociais. Isso pode ter levado a uma classificação imprecisa em alguns casos, especialmente nas postagens que dependem de contextos mais complexos para serem interpretadas corretamente.

Essas limitações não comprometem os objetivos gerais do estudo, mas indicam possibilidades de melhoria para pesquisas futuras. A ampliação da integração do Sentilytics para outras redes sociais, a implementação de modelos mais robustos de análise de sentimentos, como redes neurais treinadas especificamente para o português, e o aumento do volume de dados analisados podem contribuir para resultados ainda mais precisos e abrangentes.

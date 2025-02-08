## Análise gráfica e textual do Sentilytics

Nesta seção, são apresentados os principais resultados obtidos com o Sentilytics na análise de sentimentos sobre temas políticos no Bluesky. A ferramenta gerou diferentes representações visuais, incluindo gráficos de distribuição de sentimentos, nuvens de palavras e os posts mais engajados. Além disso, insights gerados por inteligência artificial auxiliaram na interpretação dos dados, fornecendo resumos e tendências detectadas automaticamente. A seguir, cada gráfico é analisado individualmente, seguido de uma discussão geral sobre os padrões observados e suas possíveis implicações.

![Gráfico de Número de Comentários por Sentimentos](imagens/sentilytics/estudo-caso/quantidade_comentarios_por_sentimentos.png){#grafico_numero_comentarios_por_sentimento escala=0.3}

Fonte: Autor (2025).

O gráfico apresentado na Figura \ref{grafico_numero_comentarios_por_sentimento} exibe a distribuição dos sentimentos nas postagens analisadas. Observa-se que a maioria das postagens foi classificada como **neutra**, representando 87,3% do total. Já os sentimentos **positivos** correspondem a 10,5%, enquanto os **negativos** representam apenas 2,2% das postagens. A **\autoref{mytable}** detalha essa distribuição de forma quantitativa após interagirmos melhor com o gráfico:

: Distribuição de Sentimentos nas Postagens Analisadas. \label{table_distribuicao_sentimentos}

| Sentimento | Percentual (%) | Total de Postagens |
|------------|----------------|--------------------|
| Neutro     | 87,3%          | 4.254              |
| Positivo   | 10,5%          | 512                |
| Negativo   | 2,2%           | 105                |
| **Total**  | 100%           | 4.871              |

Fonte: Autor (2025).

No contexto político, o debate sobre a escala 6x1 ganhou destaque no último ano, impulsionado pela apresentação de uma Proposta de Emenda à Constituição (PEC) que propõe seu fim. A análise dos comentários coletados revela que a maioria das postagens apresenta um tom neutro, sugerindo que grande parte das discussões tem caráter informativo ou analítico. No entanto, entre as postagens que expressam um viés emocional, observa-se uma predominância de sentimentos positivos em relação ao tema. Esse resultado indica que há uma inclinação favorável da opinião pública quanto à possibilidade de alteração ou extinção da escala 6x1, refletindo um possível apoio da população a mudanças na organização da jornada de trabalho.

O Sentilytics também gerou um insight baseado em AI para analisar o resultado do gráfico, interpretando a predominância do sentimento de neutralidade da seguinte forma: "Em suma, a análise de sentimentos revela uma necessidade de explorar mais a fundo as razões subjacentes ao otimismo ou pessimismo contidos nos 512 comentários positivos e nos 105 negativos, bem como entender como estimular uma participação mais ativa do público que se mostrou neutro.".

Esse resultado sugere que, apesar da predominância de comentários neutros, ainda existe a necessidade de entender melhor os sentimentos positivos e negativos expressos pela população. O alto número de postagens neutras pode ser interpretado como uma cautela do público em relação ao tema, especialmente considerando que mudanças trabalhistas costumam gerar incertezas.

Embora os resultados apresentados forneçam uma visão geral sobre a distribuição dos sentimentos, é importante considerar as limitações inerentes ao modelo de análise utilizado. A predominância de comentários classificados como neutros pode indicar uma limitação da ferramenta, decorrente do uso de um modelo baseado em léxicos.

![Gráfico da Média de Engajamento por Sentimentos](imagens/sentilytics/estudo-caso/media_engajamento_por_sentimento.png){#grafico_media_engajamento escala=0.3}

Fonte: Autor (2025).

Na figura \autoref{grafico_media_engajamento}, é apresentado um gráfico de barras que ilustra a média de engajamento por sentimento, considerando as interações dos usuários, como likes, repostagens, respostas e citações. Cada barra no gráfico representa a média calculada para um tipo específico de interação, agrupada de acordo com os sentimentos Positivo, Negativo e Neutro.

A análise desse gráfico permite identificar qual categoria de sentimento gera maior engajamento geral, bem como tendências específicas por tipo de interação. Por exemplo, é possível observar se posts com sentimentos negativos recebem mais repostagens, indicando maior disseminação de conteúdos críticos, ou se postagens neutras geram mais respostas, sugerindo uma maior propensão ao debate e à troca de informações. Na \autoref{tabela_media_engajamento} temos uma visualização

: Media de engajamento. \label{tabela_media_engajamento}

| Sentimento | Média de Likes | Média de Reposts | Média de Citações | Média de Respostas |
|------------|----------------|------------------|-------------------|--------------------|
| Negativo   | 15.23          | 4.07             | 0.32              | 0.95               |
| Neutro     | 12.43          | 2.71             | 0.41              | 0.63               |
| Positivo   | 9.86           | 1.76             | 0.19              | 0.48               |

Fonte: Autor (2025).


![Gráfico da Total de Engajamento por Sentimentos](imagens/sentilytics/estudo-caso/media_engajamento_por_sentimento.png){#grafico_total_engajamento escala=0.3}

Fonte: Autor (2025).

Gráfico da Média de Engajamento por Sentimentos, Gráfico da Média de Engajamento por Sentimentos,Gráfico da Média de Engajamento por Sentimentos Gráfico da Média de Engajamento por Sentimentos,Gráfico da Média de Engajamento por Sentimentos,Gráfico da Média de Engajamento por Sentimentos,Gráfico da Média de Engajamento por Sentimentos,Gráfico da Média de Engajamento por Sentimentos.

![Gráfico da Análise Temporal de Sentimentos](imagens/sentilytics/estudo-caso/analise_temporal_sentimentos.png){#grafico_analise_temporal escala=0.26}

Fonte: Autor (2025).

Gráfico da Média de Engajamento por Sentimentos, Gráfico da Média de Engajamento por Sentimentos,Gráfico da Média de Engajamento por Sentimentos Gráfico da Média de Engajamento por Sentimentos,Gráfico da Média de Engajamento por Sentimentos,Gráfico da Média de Engajamento por Sentimentos,Gráfico da Média de Engajamento por Sentimentos,Gráfico da Média de Engajamento por Sentimentos.

Fonte: Autor (2025).

### Limitações do Estudo de Caso

Sentilytics posssui integração apenas com o Bluesky(rede social baixa relevância);
Atualmente o Sentilytics não oferece muitas opções de tarefas de pré-processamento;
Amostra de dados – O estudo considerou apenas 4880 postagens no Bluesky; um número maior poderia fornecer uma visão mais ampla.
Bias na análise de sentimentos – O modelo VADER pode ter limitações para captar ironias ou sarcasmo, comuns em redes sociais.

### Pré-processamento dos Dados

Após a coleta, os textos das postagens passaram por uma sequência de tarefas de pré-processamento para garantir maior qualidade na análise. Para isso um workflow foi criado com as tarefas que serão usadas para realizar o pré-processamento, que podemos visualizar na \autoref{pipeline_processamento}.

![Workflow de pré-processamento](imagens/sentilytics/estudo-caso/workflow.png){#pipeline_processamento escala=0.35}

Fonte: Autor (2025).

A \autoref{pipeline_processamento} mostra um conjunto de tarefas organizadas em ordem, cada postagem vai passar por essas tarefas em sequência, as tarefas são:

1. Minúsculas: Transformação de todo o texto para minúsculas, garantindo uniformidade;
1. Removedor URLs Regex: Remove URLs do texto;
1. Normalizador Enelvo: Normalização do texto para corrigir erros ortográficos e abreviações comuns;
1. Tokenização por Palavra | NLTK: Segmentação do texto em palavras individuais (*tokens*);
1. Removedor *Stopwords*: Remoção de palavras irrelevantes que não contribuem para a análise do sentimento;
1. *Tokens* para Texto: Os *tokens* são unidos novamente formando uma frase novamente com os *tokens* separados por um espaço em branco.

### Análise de Sentimentos

Após o pré-processamento, as postagens foram submetidas ao modelo de análise de sentimentos do Sentilytics, que utiliza o VADER[^VADER] (Valence Aware Dictionary and sEntiment Reasoner), uma ferramenta da biblioteca NLTK[^NLTK] (Natural Language Toolkit). O VADER é um modelo baseado em regras e léxicos, projetado especificamente para a análise de sentimentos em textos informais.

Cada postagem recebeu uma pontuação de polaridade, categorizada em:

- Positivo: O quanto a postagem é positiva;
- Neutro: O quanto a postagem é neutra;
- Negativo: O quanto a postagem é negativa;
- Composta: A pontuação composta consiste em um valor que representa a polaridade geral do texto, onde esse valor varia entre -1 (muito negativo) e +1 (muito positivo).

A pontuação composta é calculada a partir da soma das valências das palavras presentes no texto. Essas valências são determinadas por um léxico de sentimentos, que associa palavras ao score de polaridade positiva e negativa. Além disso, a análise considera uma série de heurísticas que ajustam o impacto dessas palavras com base no contexto em que aparecem, como a presença de negações ou intensificadores.

Para garantir que os valores fiquem dentro do intervalo de -1 a +1, a soma das valências é normalizada usando a seguinte fórmula:

\begin{equation}
    compound = \frac{sum_s}{\sqrt{sum_s^2 + \alpha}}
\end{equation}

- sum_s é a soma das valências das palavras no texto;
- $\alpha$ é um fator de suavização que evita que textos muito longos tenham scores excessivamente altos ou baixos (o valor padrão no VADER é 15).

Com base nessa normalização, o sentilytics consegue interpretar o sentimento predominante na postagem da seguinte forma:

- Se o score composto for maior ou igual a 0.05: O sentimento da postagem é considerado positivo;
- Se for menor ou igual a -0.05: O sentimento é negativo;
- Se estiver entre -0.05 e 0.05: O sentimento é neutro.

[^NLTK]: O site do NLTK está disponível no link: <https://www.nltk.org/>
[^VADER]: A documentação do VADER está disponível no link: <https://www.nltk.org/_modules/nltk/sentiment/vader.html>

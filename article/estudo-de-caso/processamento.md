### Pré-processamento dos Dados

Após a coleta, os textos das postagens passaram por uma sequência de tarefas de pré-processamento para garantir maior qualidade na análise. O pipeline de processamento incluiu as seguintes etapas:

1. Lowercase: Transformação de todo o texto para minúsculas, garantindo uniformidade;
1. Remove URLs: Remove URLs do texto;
1. Enelvo Normaliser: Normalização do texto para corrigir erros ortográficos e abreviações comuns;
1. Word Tokenizer: Segmentação do texto em palavras individuais (tokens);
1. Stopwords Remover: Remoção de palavras irrelevantes que não contribuem para a análise do sentimento;
1. Join Tokens: Os tokens são unidos novamente formando uma frase novamente com os tokens separados por um espaço em branco.

### Análise de Sentimentos

Após o pré-processamento, as postagens foram submetidas ao modelo de análise de sentimentos do Sentilytics, que utiliza o VADER (Valence Aware Dictionary and sEntiment Reasoner), uma ferramenta da biblioteca NLTK (Natural Language Toolkit). O VADER é um modelo baseado em regras e léxicos, projetado especificamente para a análise de sentimentos em textos informais.

Cada postagem recebeu uma pontuação de polaridade, categorizada em:

- Positivo: O quanto a postagem é positiva;
- Neutro: O quanto a postagem é neutra;
- Negativo: O quanto a postagem é negativa;
- Composta: A pontuação composta consiste em um valor que representa a polaridade geral do texto, onde esse valor varia entre entre -1 (muito negativo) e +1 (muito positivo).

A pontuação composta é calculada a partir da soma das valências das palavras presentes no texto. Essas valências são determinadas por um léxico de sentimentos, que associa palavras a escores de polaridade positiva e negativa. Além disso, a análise considera uma série de heurísticas que ajustam o impacto dessas palavras com base no contexto em que aparecem, como a presença de negações ou intensificadores.

Para garantir que os valores fiquem dentro do intervalo de -1 a +1, a soma das valências é normalizada usando a seguinte fórmula:

\begin{equation}
    compound = \frac{sum_s}{\sqrt{sum_s^2 + \alpha}}
\end{equation}

- sum_s é a soma das valências das palavras no texto;
- 𝛼 é um fator de suavização que evita que textos muito longos tenham scores excessivamente altos ou baixos (o valor padrão no VADER é 15).

Com base nessa normalização, o sentilytics consegue interpretar o sentimento predominante na postagem da seguinte forma:

- Se o score composto for maior ou igual a 0.05: O sentimento da postagem é considerado positivo;
- Se for menor ou igual a -0.05: O sentimento é negativo;
- Se estiver entre -0.05 e 0.05: O sentimento é neutro.

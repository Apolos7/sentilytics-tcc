---
marp: true
theme: academic
paginate: true
math: katex
---

# **Sentilytics**

## Análise Automatizada de Sentimentos em Redes Sociais

Autor: José Alessandro Santos Santana
**Bacharelado em Sistemas de Informação**
Orientador: Prof. Dr. Gilson Pereira dos Santos Júnior

<!-- _footer: '12 de março de 2025' -->

---

<!-- _header: SUMÁRIO -->

- Introdução
  - Contextualização do Tema
  - Problema de Pesquisa
- Objetivos
  - Objetivo Geral
  - Objetivos específicos
- Fundamentação Teórica
  - Análise de Sentimentos
  - Análise de Sentimentos em Redes sociais
  - Processo de Análise de Sentimentos em Aplicações

---

<!-- _header: SUMÁRIO -->

- Sentilytics
  - Técnologias e Ferramentas
  - BPMN: Do Cadastro da Pesquisa à Visualização dos Resultados
  - Dicionário de Dados
  - Demonstração Visual da Aplicação
  - Vídeo Demonstrativo
- Estudo de Caso
- Conclusão
- Trabalhos Futuros
- Referências

---

<!-- _header: CONTEXTUALIZAÇÃO DO TEMA -->

As redes sociais são um ambiente digital dinâmico, onde milhões de pessoas expressam opiniões e sentimentos diariamente.

- Expressão de **opiniões**, **sentimentos** e **tendências**;
- Compreensão da **opinião pública** e **articulação política**;
- Monitoramento de mercado por empresas;
- Entretenimento, mobilização e conscientização social.

---

<!-- _header: CONTEXTUALIZAÇÃO DO TEMA -->

A análise de sentimentos permite interpretar emoções expressas em textos, identificando padrões e tendências.

- Compreensão de tendências e comportamentos;
- Identificação de polarizações em debates públicos;
- **Apoio à tomada de decisões** em comunicação, política e negócios.

---

<!-- _header: PROBLEMA DE PESQUISA -->

A análise de sentimentos em redes sociais enfrenta desafios significativos.

- Volume de dados torna a análise manual inviável;
- Soluções desenvolvidas geralmente não são intuitivas;
- Não oferecem processamento de ponta a ponta;
- Falta ou dificuldade na personalização;
- Muitas vezes não possui integração direta com redes sociais.

---

<!-- _header: OBJETIVOS -->

Analisar sentimentos de forma automatizada em redes sociais por meio de uma solução integrada denominada Sentilytics.

- Implementar a coleta automatizada de dados em redes sociais integradas à aplicação.
- Desenvolver um módulo de pré-processamento customizável para normalização e remoção de stopwords.
- Integrar o modelo de análise de sentimentos VADER à aplicação para classificar sentimentos.

---

<!-- _header: OBJETIVOS -->

- Exibir os resultados da análise de sentimentos por meio de gráficos, tabelas e nuvens de palavras.
- Avaliar a aplicação por meio de um estudo de caso sobre o debate do fim da escala 6x1.

---

<!-- _header: ANÁLISE DE SENTIMENTOS -->

**Identifica emoções em textos**: Positivo, negativo ou neutro

**Principais técnicas**:

**Baseadas em léxicos**: Dicionários de palavras categorizadas

**Aprendizado de máquina**: Modelos treinados para prever sentimentos

**Abordagem hibrida**: Combina técnicas baseadas em léxicos com o aprendizado de máquina

---

<!-- _header: ANÁLISE DE SENTIMENTOS EM REDES SOCIAIS -->

A **análise de sentimentos** em **redes sociais** enfrenta desafios significativos.

- **Volume de dados** torna a análise manual inviável;
- **Soluções pouco intuitivas** dificultam o uso;
- **Falta de processamento de ponta a ponta**;
- **Limitações na personalização** do fluxo de análise;
- **Dificuldade de integração** com redes sociais.

---

<!-- _header: PROCESSO DE ANÁLISE DE SENTIMENTOS EM APLICAÇÕES -->

![bg w:1200 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/processo_analise_sentimentos.png)

---

<!-- _header: TECNOLOGIAS E FERRAMENTAS -->

![bg w:470 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/sentilytics/diagramas/tecnologias-ferramentas.png)

---

<!-- _header: BPMN: Do Cadastro da Pesquisa à Visualização dos Resultados -->

![bg w:1200 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/sentilytics/pesquisa_sentimentos.png)

---

<!-- _header: DIAGRAMA DE COMPONENTES -->

![bg w:1000 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/sentilytics/diagramas/diagrama_componentes.png)

---

<!-- _header: DIAGRAMA ENTIDADE RELACIONAMENTO -->

![bg w:670 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/sentilytics/diagramas/DER-sentilytics.png)

---

<!-- _header: DICIONÁRIO DE DADOS -->

![bg w:800 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/sentilytics/diagramas/dicionario_dados.png)

---

<!-- _header: DEMONSTRAÇÃO VISUAL DA APLICAÇÃO -->

![bg w:1000 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/sentilytics/interface-grafica/tela-login.png)

---

<!-- _header: DEMONSTRAÇÃO VISUAL DA APLICAÇÃO -->

![bg w:1000 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/sentilytics/interface-grafica/listagem-pesquisas.png)

---

<!-- _header: DEMONSTRAÇÃO VISUAL DA APLICAÇÃO -->

![bg w:1000 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/sentilytics/interface-grafica/dados-pesquisa.png)

---

<!-- _header: DEMONSTRAÇÃO VISUAL DA APLICAÇÃO -->

![bg w:1000 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/sentilytics/interface-grafica/coleta-dados.png)

---

<!-- _header: DEMONSTRAÇÃO VISUAL DA APLICAÇÃO -->

![bg w:1000 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/sentilytics/interface-grafica/processamento.png)

---

<!-- _header: DEMONSTRAÇÃO VISUAL DA APLICAÇÃO -->

![bg w:1000 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/sentilytics/interface-grafica/tarefas_workflow.png)

---

<!-- _header: DEMONSTRAÇÃO VISUAL DA APLICAÇÃO -->

![bg w:1000 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/sentilytics/interface-grafica/resultado-graficos.png)

---

<!-- _header: VÍDEO DEMONSTRATIVO -->

![bg w:500 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/sentilytics/qr_code.png)

---

<!-- _header: ESTUDO DE CASO: ESCALA 6x1 -->

O Sentilytics foi aplicado para analisar a percepção da escala 6x1 em redes sociais, identificando sentimentos e padrões de engajamento sobre o tema.

Objetivo: Analisar sentimentos e tendências sobre a escala 6x1
Dados coletados: 4.880 postagens no **Bluesky**

Metodologia:

- Coleta de dados no Bluesky via Sentilytics;
- Pré-processamento e classificação automática dos sentimentos;

---

<!-- _header: ESTUDO DE CASO: ESCALA 6x1 -->

Objetivo: Analisar sentimentos e tendências sobre a escala 6x1
Dados coletados: 4.880 postagens no **Bluesky**

Resultados:

- **87,3%** das postagens foram classificadas como **neutras**.
- **10,5% positivas** | **2,2% negativas**.
- **Sentimentos negativos geraram maior engajamento** (mais likes e reposts).
- **Tendência favorável** à mudança da escala 6x1.
Sentilytics: Automatizou coleta, pré-processamento e análise dos dados.

---

<!-- _header: CONCLUSÃO -->

**Sentilytics:** Solução **integrada e automatizada** para análise de sentimentos.

**Diferenciais:**

- **Coleta, pré-processamento e classificação** personalizáveis
- **Integração com redes sociais** (Bluesky)
- **Acesso intuitivo**, mesmo sem experiência técnica

**Impacto:** Monitoramento de redes, pesquisas acadêmicas e decisões estratégicas.

---

<!-- _header: TRABALHOS FUTUROS -->

O Sentilytics pode ser aprimorado e expandido para tornar a análise de sentimentos ainda mais eficiente e abrangente.

- Integração de **novos modelos** de **análise de sentimentos**;
- Inclusão de **novos algoritmos** de **pré-processamento**;
- Incluir o suporte a múltiplas sociais;
- Painel administrativo.

---

<!-- _header: REFERÊNCIAS -->

BERTAGLIA, T. F. C.; NUNES, M. d. G. V. Exploring word embeddings for unsupervised
textual user-generated content normalization. In: *Proceedings of the 2nd Workshop on Noisy User-generated Text (WNUT)*. [S.l.: s.n.], 2016. p. 112–120.

BILO, H. A. Ferramenta para análise de sentimentos em postagens no moodle. 2023.

CARVALHO, L. B. d. D. A democracia frustrada: fake news, política e liberdade de expressão nas redes sociais. *Internet e Sociedade,[S. l.]*, v. 1, n. 1, p. 172–199, 2020.

---

<!-- _header: REFERÊNCIAS -->

GAMALLO, P.; GARCIA, M. Linguakit: uma ferramenta multilingue para a análise linguística e a extração de informação. *Linguamática*, v. 9, n. 1, p. 19–28, 2017.

JESUS, E. L. de; FERREIRA, D. C. M. Aplicando pln para análise de sentimentos do twitter. 2020.

LIMA, P. R. S. et al. Redes sociais como ferramentas de transparência em tempos de covid-19: uma análise das publicações dos boletins epidemiológicos do estado de alagoas. *Logeion: Filosofia da Informação*, v. 7, n. 2, p. 88–107, 2021.

---

<!-- _header: REFERÊNCIAS -->

LOPES, A. C. Otimização de aplicações de processamento de linguagem natural para análise de sentimentos. Universidade Estadual Paulista (Unesp), 2024.

MALHEIROS, Y. Emotte: Uma ferramenta de análise de sentimentos para o twitter. In: SBC. *Anais Estendidos do XX Simpósio Brasileiro de Sistemas Multimídia e Web.* [S.l.], 2014. p. 62–65.

MALHEIROS, Y.; LIMA, G. Uma ferramenta para análise de sentimentos em redes sociais
utilizando o senticnet. In: SBC. *Simpósio Brasileiro de Sistemas de Informação (SBSI)*. [S.l.], 2013. p. 517–522.

---

<!-- _header: REFERÊNCIAS -->

MIGUEL, R. dos S.; BARBOSA, Y. d. A. M. Uma ferramenta para análise de sentimentos de tweets em português. 2018.

MOREIRA, B. G. et al. Análise de sentimentos e emoções com o uso da ferramenta orange datamining: uma avaliação a partir da tradução dos textos do português. *Anais do Computer on the Beach*, v. 15, p. 352–354, 2024.

POMPEI, T.; GOUVEIA, L. M. B.; RAMOS, P. F. M. d. S. Redes sociais: influência,
identidade e diferença na contemporaneidade. *Revista em Sociedade, Belo Horizonte*, v. 3, n. 2, p. 93–111, 2021.

---

<!-- _header: REFERÊNCIAS -->

SANTANA, B. S.; FREITAS, L. A. de. Capítulo 23 pln em redes sociais. 2023.

SILVA, N. G. R. da. *Bestchoice*: Classificação de sentimento em ferramentas de expressão de opinião. Tese (Doutorado) — Tese de graduação, Universidade Federal de Pernambuco Recife, 2010. 7, 17, 2010.

SIQUEIRA, L. F. et al. O impacto das mídias sociais na saúde mental de adolescentes e jovens adultos. *Brazilian Journal of Implantology and Health Sciences*, v. 6, n. 10, p. 1384–1390, 2024.

---

<!-- _header: ACESSO AO DOCUMENTO E APRESENTAÇÃO  -->

![bg w:550 drop-shadow:0,5px,10px,rgba(0,0,0,.4)](imagens/qr-code-link-trabalho.png)

---

<style>
.center-text {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  font-size: 80px;
  font-weight: bold
}
</style>

<div class="center-text">
  Obrigado!
</div>

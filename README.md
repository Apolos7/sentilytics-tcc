<div align="center">

<img src="https://www.logolynx.com/images/logolynx/a9/a98355315595fe5800b326aac90744f5.png" alt="ifs-logo" width="10%">

# Sentilytics: Análise Automatizada de Sentimentos em Redes Sociais

Este repositório contém meu Trabalho de Conclusão de Curso (TCC) desenvolvido durante minha graduação. Aqui você encontrará o documento final do TCC, além de possíveis materiais complementares utilizados ao longo da pesquisa, como referências, gráficos, códigos e outros arquivos relevantes.

![Author](https://img.shields.io/badge/Autor-José%20Alessandro%20Santos%20Santana-green)
![Orientador](https://img.shields.io/badge/Orientador-Gilson%20Pereira%20dos%20Santos%20Junior-green)
![Data](https://img.shields.io/badge/Publica%C3%A7%C3%A3o-31%2C%20Fev%20de%202025-green)
![Linguagem](https://img.shields.io/badge/Linguagem-Portugu%C3%AAs%20brasileiro-green)

[O documento e o slide estão disponíveis aqui](https://apolos7.github.io/sentilytics-tcc/)

</div>

## Resumo

As redes sociais tornaram-se ambientes fundamentais para a disseminação de opiniões e sentimentos, impactando áreas como política, economia e comportamento social. No entanto, a análise automatizada desses sentimentos ainda apresenta desafios, como a necessidade de ferramentas intuitivas e capazes de lidar com grandes volumes de dados. Diante desse cenário, este trabalho propõe o Sentilytics, uma aplicação desenvolvida para realizar a análise automatizada de sentimentos em redes sociais. A aplicação foi construída utilizando Spring Boot, Angular e Python, integrando a coleta de postagens, pré-processamento textual e classificação de sentimentos em um fluxo único e personalizável. Para avaliação da aplicação, foi realizado um estudo de caso sobre o debate do fim da escala 6x1, onde foram analisadas postagens coletadas do Bluesky. Os resultados demonstraram que o Sentilytics é uma solução eficiente para análise de sentimentos, proporcionando visualizações gráficas e *insights* interpretáveis. Como limitações, a versão inicial da aplicação utiliza apenas o modelo VADER, que apresenta dificuldades na detecção de ironia e ambiguidade, e da coleta restrita ao Bluesky, reduzindo a diversidade de dados. Para trabalhos futuros, propõe-se a expansão para outras redes sociais e a inclusão de modelos mais robustos de análise de sentimentos.

**Palavras-chave**: Análise de Sentimentos, Processamento de Linguagem Natural, Redes Sociais, Bluesky.

## Abstract

Social media has become a fundamental environment for the dissemination of opinions and sentiments, impacting areas such as politics, economics, and social behavior. However, the automated analysis of these sentiments still presents challenges, such as the need for intuitive tools capable of handling large volumes of data. Given this scenario, this study proposes Sentilytics, an application developed to perform automated sentiment analysis on social media. The application was built using Spring Boot, Angular, and Python, integrating data collection, text preprocessing, and sentiment classification into a unified and customizable workflow. To evaluate the application, a case study was conducted on the debate surrounding the end of the 6x1 work schedule, analyzing posts collected from Bluesky. The results demonstrated that Sentilytics is an efficient solution for sentiment analysis, providing graphical visualizations and interpretable insights. Regarding limitations, the initial version of the application relies solely on the VADER model, which has difficulties detecting irony and ambiguity, and its data collection is restricted to Bluesky, limiting the diversity of datasets. For future work, it is proposed to expand the application to other social networks and include more advanced sentiment analysis models.

**Keywords**: Sentiment Analysis, Natural Language Processing, Social Networks, Bluesky.

## Agradecimentos

A jornada até a conclusão deste trabalho foi desafiadora, mas também repleta de aprendizados, crescimento e apoio de pessoas especiais. Sem elas, esse momento não teria o mesmo significado.

Primeiramente, agradeço à minha família, que sempre esteve ao meu lado, me incentivando e me dando forças nos momentos mais difíceis. O apoio incondicional e a paciência foram fundamentais para que eu pudesse chegar até aqui.

Aos meus professores, que desempenharam um papel essencial na minha formação acadêmica e profissional, transmitindo não apenas conhecimento, mas também valores que levarei para toda a vida. Em especial, gostaria de expressar minha gratidão ao professor George Leite Junior, que foi muito mais do que um professor dentro da sala de aula. Seu exemplo e ensinamentos ultrapassaram os limites da universidade, tornando-se um verdadeiro mentor.

Não poderia deixar de agradecer também aos meus amigos Kamille Gomes Bezerra e Ítalo Martins de Deus, que estiveram comigo durante toda essa jornada na faculdade. Compartilhamos desafios, noites mal dormidas, risadas e conquistas. Sem vocês, esse percurso teria sido muito mais difícil.

Por fim, mas não menos importante, expresso meu profundo agradecimento ao meu orientador, Gilson Pereira dos Santos Júnior, por toda a paciência, dedicação e incentivo ao longo da elaboração deste trabalho. Sua orientação foi essencial para que este projeto se tornasse realidade.

A todos vocês, meu muito obrigado!

<hr>

> Este projeto foi escrito utilizando [limarka-template-tcc](https://github.com/ReinanHS/limarka-template-tcc).
> Essa ferramenta é responsável por contém os arquivos do esqueleto (modelo) para iniciar a escrita de um trabalho acadêmico com o limarka. Além disso, este projeto contém várias outras novidades que facilitam a escrita de um trabalho acadêmico.

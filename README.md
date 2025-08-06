# Análise Multifacetada de Comunidades Online no Reddit

Este repositório apresenta uma análise de dados completa de uma comunidade online, demonstrando um pipeline que integra **KDD (Descoberta de Conhecimento em Bases de Dados)**, **Processamento de Linguagem Natural (PLN)** e **Análise de Redes Sociais (SNA)**. A partir de dados do subreddit `r/faculdadeBR`, a análise mapeia a estrutura de interações dos usuários, identifica comunidades e caracteriza o foco temático de cada grupo, revelando as "bolhas" de discussão sobre o tema "TCC".

![Grafo de Comunidades](http://googleusercontent.com/file_content/0)
*Visualização do grafo de interações com as comunidades de usuários destacadas por cor.*

## ✨ Habilidades Demonstradas

Este projeto destaca competências práticas nas seguintes áreas de Ciência de Dados:

* **Coleta de Dados via API:**
    * Extração de dados complexos (posts e comentários em árvore) do Reddit utilizando a biblioteca `PRAW`.

* **Análise Exploratória de Dados (EDA):**
    * Manipulação, limpeza e enriquecimento de dados com `Pandas`.
    * Criação de visualizações para análise de distribuição e correlação com `Matplotlib` e `Seaborn`.

* **Machine Learning (Não Supervisionado):**
    * **Clustering:** Aplicação do algoritmo **K-Means** (`Scikit-learn`) para agrupar dados numéricos e textuais.
    * **Detecção de Comunidades:** Uso do **método de Louvain** para identificar grupos em redes complexas.

* **Processamento de Linguagem Natural (PLN):**
    * Técnicas de limpeza e normalização de texto não estruturado com expressões regulares (`re`).
    * Uso de `NLTK` para tratamento de *stopwords*.
    * Vetorização de texto com a técnica **TF-IDF**, incluindo a captura de contexto com n-grams.
    * **Modelagem de Tópicos** para caracterização de corpus textuais.

* **Análise de Redes Sociais (SNA):**
    * Construção, manipulação e análise de grafos de interação social com `NetworkX`.
    * Visualização de redes para apresentar a topologia e as comunidades.

## 📂 Estrutura do Projeto e dos Códigos

Os scripts neste repositório representam uma jornada analítica evolutiva, onde cada um aprofunda a investigação sobre o mesmo conjunto de dados.

* **`1_kdd.py`:** O ponto de partida. Este script realiza uma análise de KDD sobre os **metadados** das postagens (score, número de comentários). O objetivo é encontrar padrões de engajamento utilizando clustering com K-Means.

* **`2_text_mining.py`:** A segunda etapa foca no **conteúdo textual** das postagens. Este script aplica técnicas de PLN para limpar o texto, vetorizá-lo com TF-IDF e, novamente com K-Means, realizar uma modelagem de tópicos para descobrir "o que" está sendo discutido.

* **`3_comunidade.py`:** O script principal e mais avançado. Ele eleva a análise para o nível de **rede social**, coletando não apenas posts, mas também as **interações** (comentários). Com `NetworkX`, ele constrói o grafo de usuários e aplica o método de Louvain para responder "quem" está falando com "quem", identificando as comunidades.

* **`4_caracterizacao.py`:** A etapa final de integração. Este script pega as comunidades descobertas pelo `comunidade.py` e aplica as técnicas de mineração de texto para **caracterizar tematicamente** cada grupo, respondendo "sobre o que cada comunidade conversa".

## 🚀 Como Executar

Siga os passos abaixo para replicar a análise principal (SNA).

### 1. Pré-requisitos
* Python 3.8 ou superior
* Credenciais de desenvolvedor para a API do Reddit ([link para criar](https://www.reddit.com/prefs/apps))

### 2. Instalação
Clone este repositório e instale as dependências a partir do arquivo `requirements.txt`.
```bash
git clone [https://github.com/seu-usuario/seu-repositorio.git](https://github.com/seu-usuario/seu-repositorio.git)
cd seu-repositorio
pip install -r requirements.txt
```
*(**Nota:** Para gerar o arquivo `requirements.txt`, execute `pip freeze > requirements.txt` no seu ambiente virtual).*

### 3. Configuração
No script `comunidade.py` (ou em um arquivo de configuração), insira suas credenciais da API do Reddit:
```python
client_id = 'SEU_CLIENT_ID'
client_secret = 'SEU_CLIENT_SECRET'
user_agent = 'script:analise-comunidades:v1 (by u/SEU_USUARIO_REDDIG)'
```

### 4. Execução
Execute o script principal para rodar o pipeline completo de análise de redes sociais. Os resultados, incluindo a visualização do grafo e a análise textual das comunidades, serão exibidos na saída.
```bash
python comunidade.py
```

## 📈 Principais Achados
* A análise da rede revelou a existência de **múltiplas comunidades** com perfis de interação distintos.
* A caracterização temática mostrou que diferentes comunidades se especializam em diferentes tipos de discussão, como **grupos de apoio emocional**, **nichos de debate técnico** por área de estudo e **redes de ajuda prática**.
* A integração das três abordagens (KDD, PLN e SNA) forneceu uma visão muito mais rica e completa da dinâmica da comunidade do que qualquer uma das técnicas isoladamente.

## 👤 Autor

* **[Luis Felipe Marques Silva]**
* **LinkedIn:** [www.linkedin.com/in/luisfelipemsilva]
* **GitHub:** [www.github.com/Felipao98]

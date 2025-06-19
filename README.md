# Segmentação de Clientes para Marketing com K-means 🎯

[Clique aqui para executar o App no Streamlit](https://rodrslv-aplicacao-previsao-de-agrupamentos.streamlit.app/)  <img align="center" alt="Rod-Python" height="20" width="26" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/streamlit/streamlit-original.svg">

Este projeto apresenta uma aplicação interativa desenvolvida em **Streamlit** que utiliza o algoritmo de **clusterização K-means** para identificar e prever grupos de interesse de usuários. O objetivo principal é capacitar equipes de marketing a direcionar campanhas de forma mais eficaz, através da segmentação de público em "bolhas de interesse" baseadas em padrões de comportamento e preferências.

Com esta ferramenta, é possível:

* **Personalizar Campanhas:** Criar mensagens e ofertas sob medida para cada grupo.
* **Otimizar Canais de Comunicação:** Identificar os melhores canais para alcançar cada segmento.
* **Desenvolver Produtos Estratégicos:** Informar a criação de produtos e serviços que atendam às necessidades específicas de cada grupo.
* **Gerar Conteúdo Relevante:** Produzir materiais que ressoem diretamente com os interesses de cada segmento.

---

## 🚀 Como Funciona

A aplicação permite que você faça upload de um arquivo CSV contendo dados de novos usuários. O modelo de K-means previamente treinado processa esses dados e atribui cada usuário a um dos grupos de interesse identificados.

**Descrição dos Grupos:**

* **Grupo 0:** Focado em um público jovem com forte interesse em moda, música e aparência.
* **Grupo 1:** Associado a esportes (especialmente futebol americano, basquete) e atividades culturais como banda e rock.
* **Grupo 2:** Mais equilibrado, com interesses em música, dança e moda.

---

## 📊 Dados Utilizados

Os dados para treinamento do modelo são simulados e provêm de um curso da Alura, disponíveis publicamente em: `https://raw.githubusercontent.com/Mirlaa/Clusterizacao-dados-sem-rotulo/main/Dados/dados_mkt.csv`.

O dataset original contém as seguintes características:

`sexo, idade, numero_de_amigos, basquete, futebol_americano, futebol, softbol, voleibol, natacao, animacao, beisebol, tenis, esportes, fofo, danca, banda, marcha, musica, rock, cabelo, vestido, shopping, compras, roupas, nossa_marca, marca_concorrente, bebidas`

---

## ⚙️ Metodologia e Tecnologias

1.  **Pré-processamento:** As colunas categóricas (`sexo`) foram codificadas usando `OneHotEncoder` e as características numéricas foram padronizadas usando `StandardScaler` para preparar os dados para o K-means.
2.  **Clusterização K-means:** O algoritmo K-means foi aplicado para agrupar os usuários com base em suas características. A definição de 3 clusters foi feita através da análise de métricas como o **Silhouette Score**, que ajuda a determinar o número ideal de grupos.
3.  **Interpretação dos Clusters:** Cada grupo foi interpretado e nomeado com base na análise da **média das características** de seus membros, revelando os interesses predominantes em cada segmento.
4.  **Implementação:**
    * **Python:** Linguagem principal do projeto.
    * **Streamlit:** Para a criação da interface web interativa.
    * **Pandas:** Para manipulação e análise de dados.
    * **Scikit-learn:** Para as implementações de `OneHotEncoder`, `StandardScaler` e `KMeans`.
    * **Joblib:** Para persistir e carregar os modelos pré-treinados (`encoder.pkl`, `scaler.pkl`, `kmeans.pkl`).

---

## ⚠️ Limitações do Modelo de Clusterização

É importante estar ciente de algumas limitações inerentes a modelos de clusterização sem rótulo, como o K-means:

* **Interpretação Subjetiva:** A nomeação e interpretação dos clusters dependem da análise humana das características, podendo haver diferentes perspectivas.
* **Sensibilidade a Ruídos e Outliers:** Dados ruidosos ou outliers podem distorcer a formação dos clusters.
* **Número de Clusters:** A escolha do número ideal de clusters (`k`) é crucial e, embora métricas ajudem, pode não refletir perfeitamente a realidade dos dados.
* **Não Supervisionado:** Não há "resposta correta" ou "verdade fundamental" nos agrupamentos, pois o modelo não foi treinado com rótulos pré-existentes.

---

## 🛠️ Como Executar o Projeto Localmente

Para rodar este aplicativo em sua máquina, siga os passos abaixo:

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/rodrigorosalvos/aplicacao-previsao-de-agrupamentos.git](https://github.com/rodrigorosalvos/aplicacao-previsao-de-agrupamentos.git)
    cd aplicacao-previsao-de-agrupamentos
    ```
2.  **Certifique-se de ter os arquivos do modelo:**
    Garanta que os arquivos `encoder.pkl`, `scaler.pkl` e `kmeans.pkl` estejam na mesma pasta do seu script principal (`App.py`).
3.  **Crie um ambiente virtual (recomendado):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # No Windows: venv\Scripts\activate
    ```
4.  **Instale as dependências a partir do `requirements.txt`:**
    ```bash
    pip install -r requirements.txt
    ```
5.  **Execute o aplicativo Streamlit:**
    ```bash
    streamlit run App.py
    ```

Após executar o comando, o Streamlit abrirá o aplicativo em seu navegador padrão.

---

## 💡 Próximos Passos e Aprendizados

Este projeto serviu como um importante **teste e consolidação de aprendizado** em clusterização e desenvolvimento de aplicações interativas. Embora exista margem para futuras melhorias, tanto na interface quanto na sofisticação do modelo, o foco principal foi solidificar o entendimento e a aplicação prática de técnicas de Machine Learning para segmentação.
